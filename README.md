<p align="center"> <h3 align="center"><a href="https://github.com/Showvro/react_workbench_setup">⚡ React Editor Linting and Formatting Setup</a></h3>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [How to clone](#how-to-clone)
- [Editor Setup](#editor-setup)
  - [Plugins](#plugins)
  - [Settings](#settings)
- [Linting Setup](#linting-setup)
  - [Install Dev Dependencies](#install-dev-dependencies)
  - [Lint Configuration](#lint-configuration)
- [Contact](#contact)

<!-- HOW TO CLONE -->

## How to clone

Please follow the below instructions to clone this repo in your computer:

1. Clone this repository

   ```sh
   git clone https://github.com/Showvro/react_workbench_setup.git
   ```

<!-- Editor Setup -->

## Editor Setup

You can use any editor but as I personally prefer VS Code. I will give some instructions about how I prefer VS code to be setup for React applications.

### Plugins

You need to install the below plugins:

- ESLint by Dirk Baeumer
- Prettier - Code formatter by Prettier
- Monokai Pro Theme (optional)

### Settings

Follow the below settings for VS Code -

1. Create a new folder called ".vscode" inside the project root folder.
2. Create a new file called "settings.json" inside that folder.
3. Paste the below json in the newly created settings.json file and save the file.

```json
{
  // Theme
  "workbench.colorTheme": "Monokai Pro", //or your theme name

  // config related to code formatting
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "[javascriptreact]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "javascript.validate.enable": false, //disable all built-in syntax checking
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll.tslint": true,
    "source.organizeImports": true
  },
  "eslint.alwaysShowStatus": true,
  // emmet
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  }
}
```

## Linting Setup

### Install Dev Dependencies

You can add a new script in the scripts section like below to install everything with a single command:

```package.json

"lint": "yarn add -D prettier && yarn add -D babel-eslint && npx install-peerdeps --dev eslint-config-airbnb && yarn add -D eslint-config-prettier eslint-plugin-prettier"

```

Then simply run the below command in the terminal -

```sh

yarn lint #or 'npm run lint'

```

After installing all dependencies, go to your package.json file and change the `"babel-eslint": "^10.0.2"` line to `"@babel/eslint-parser": "^7.5.4"` in your devDependencies section.

### Then copy this command to create .eslintrc file or you can create a file manually

```eslintrc

touch .eslintrc

```

## Lint Configuration

And copy this Lint Configuration to .eslintrc

```json
{
  "extends": [
    "airbnb",
    "airbnb/hooks",
    "eslint:recommended",
    "prettier",
    "plugin:jsx-a11y/recommended"
  ],
  "parser": "@babel/eslint-parser",
  "parserOptions": {
    "ecmaVersion": 8,
    "requireConfigFile": false,
  },
  "env": {
    "browser": true,
    "node": true,
    "es6": true,
    "jest": true
  },
  "rules": {
    "react/react-in-jsx-scope": 0,
    "react-hooks/rules-of-hooks": "error",
    "no-console": 0,
    "react/state-in-constructor": 0,
    "indent": 0,
    "linebreak-style": 0,
    "react/prop-types": 0,
    "jsx-a11y/click-events-have-key-events": 0,
    "react/jsx-filename-extension": [
      1,
      {
        "extensions": [".js", ".jsx"]
      }
    ],
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true,
        "endOfLine": "auto"
      }
    ]
  },
  "plugins": ["prettier", "react", "react-hooks"]
}
```

<!-- CONTACT -->

## Contact

Showvro Roy - [showvro.roy@gmail.com](mailto:showvro.roy@gmail.com)
