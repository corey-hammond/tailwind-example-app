# Tailwind CSS Example App

A simple web application to demonstrate the Tailwind CSS framework features

## Dependencies

```
npm install -D tailwindcss postcss-cli autoprefixer
```

## Configure Tailwind CSS

The following steps will set up and configure Tailwind CSS to work with your React application. Create your React application using create-react-app and follow the next steps.

### Generate a Tailwind config file

```
npx tailwind init tailwind.js --full
```

### Create a Post CSS config file

```
touch postcss.config.js
```

Add the following to the new config file:

```
const tailwindcss = require("tailwindcss");

module.exports = {
  plugins: [
    tailwindcss("./tailwind.js"),
    require("autoprefixer")
  ]
};
```

### Create src/assets/(main.css, tailwind.css)

Add imports to tailwind.css:

```
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
```

### Edit scripts in package.json

Add scripts for compiling tailwind:

```
"build:css": "postcss src/assets/tailwind.css -o src/assets/main.css",
"watch:css": "postcss src/assets/tailwind.css -o src/assets/main.css"
```

Edit "start" and "build" scripts to include "watch:css" and "build:css":

```
"start": "npm run watch:css && react-scripts start",
"build": "npm run build:css && react-scripts build",
```
