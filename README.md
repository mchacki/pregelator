# pregelator (experimental feature)

_Note: This Foxx Service is still in development. Currently only tested in Google's Chrome Browser._

Pregel UI IDE to write and execute Programmable Pregel Algorithms,
delivered in a foxx service containing a visual UI to improve the 
development of custom algorithms.

This is an experimental feature of ArangoDB 3.8.

## Storing custom algorithms in a collection

Pregelator will create a collection named: `"<foxx-mount-path-prefix>_userDefinedAlgorithms"`

Documents stored in that collection will be visible in the Pregelator UI.
The format must be:

```
{
  "_key": "<the_name_of_your_algorithm>",
  "algorithm": "<your_algorithm_program>"
}
```

## Creating a new build

Steps needed to create a new build:
```
- Run `yarn build`
- Edit `manifest.json` and increase version number
- Run `make deploy`
- Run `make zip`
- Change the name of the zip-file accordingly.
- Commit and push changes.
```

## Use the build in JS commands:

Prerequisites:
```
cd react
yarn install
```

To build:
```
yarn build
```

To develop:
```
// Needs an ArangoDB instance to be available at http://localhost:8529
// Instance need to be started with flag: --all.http.trusted-origin all 
// Needs also the foxx-service part to be deployed under foxx route: "/pregeli"

yarn start
```

## Using the Makefile:

1. Prepares local build directory structure:
```
make deploy
```

2. Create bundles zipfile:
```
make zip
```

3. Install to ArangoDB:
```
make install // needs environment variables FOXX_CLI and FOXX_SERVER to be set
```

Clean local build:
```
make clean
```

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `yarn build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
