# Steps to setup React Typescript Webpack

1. Initialize a `git` repository `git init`
2. create two folders names `src`(house the souce code) and `build`(house the build files)
3. Initialise a `package.json` file using `pnpm init`; accept the default setting.
4. Create a boiler plate code for `html` within the `/src/index.html`; edit and add a `<div id="root"></div>` within the body; this is entry point for the react app.
5. Any package added as a dependencies goes to `node_modules` folder; thus add it the `.gitignore` file
6. Install the packages the we required for building the app; listed below

```bash
react
react-dom
```

- We also need support for typescript; so we install types for `react` and `react-dom` as dev dependencies; apackges are listed below, with `pnpm` use `--save-dev` to save dev dependencies.

```bash
    typescript
    @types/react
    @types/react-dom
```

7. We need to add a configuration for the typescript compiler. The compiler options are based on type-checking and not code transpilation

8. Setup the entry point and root component for the application; create following folder in the `src` folder.

- (root component) export an `App` function from `App.tsx`.
- (entry point) Add `index.tsx` and mount the `App` component to the `React-DOM`.

9. Install `Babel` with necessary plugins as dev dependencies; Now this setup can be rendered in the browser but for that the browser cannot understood by the browser, for that we need `babel` (convert React and typescript code to javascript); we need to add the following plugins

```bash
    @babel/core
    @babel/preset-env
    @babel/preset-react
    @babel/preset-typescript
```

  - add a `.babelrc`file in the root folder for listing the preset config for `babel`; now the project can transpile modern javascript features in to a format that the browser can understand.

10. Add a module bundler; 
  - Use `webpack` to bundle the code of different components; and then referenced in the `index.html` file
  - Add `webpack` related packages as dev dependencies; following
  ```bash
    webpack
    webpack-cli
    webpack-dev-server
    html-webpack-plugin
  ```

  - we also need a `babel-loader` package which allows tranpspilling javascript files using `babel` and `webpack`