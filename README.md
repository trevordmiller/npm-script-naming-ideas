# npm-script-naming-ideas

Ideas for `package.json` npm script naming

## Template

```
"scripts": {
  "dev": "main process(es) for developing",
  "test:watch": "run tests in watch mode",
  "verify": "verify things are working as expected (helpful to run on CI)",
  "test": "run tests",
  "lint": "run linting",
  "build": "create a production build",
  "release": "publish the latest version",
  "start": "start production process(es)"
}
```

## Examples

### Library

```
"scripts": {
  "dev": "yarn build -- --watch",
  "test:watch": "yarn test -- --watch",
  "verify": "yarn test && yarn lint && yarn build",
  "test": "jest src",
  "lint": "eslint src",
  "build": "babel src -d build -i '**/*.test.js'",
  "release": "git checkout master && git pull && yarn build && yarn version && git push && git push --tags && npm publish"
}
```

### Web App

```
"scripts": {
  "dev": "next",
  "test:watch": "yarn test -- --watch",
  "verify": "yarn test && yarn lint && yarn build",
  "test": "jest .",
  "lint": "eslint .",
  "build": "next build",
  "stage": "git checkout master && git pull && now",
  "release": "now alias",
  "start": "next start"
}
```

### Service

```
"scripts": {
  "dev": "nodemon --exec micro",
  "test:watch": "yarn test -- --watch",
  "verify": "yarn test && yarn lint",
  "test": "jest .",
  "lint": "eslint .",
  "stage": "git checkout master && git pull && now",
  "release": "now alias",
  "start": "micro"
}
```

## Related CONTRIBUTING.md

This `CONTRIBUTING.md` will work for any of the examples since it uses the npm script template:

```
# Contributing

- Ensure you have [Git](https://git-scm.com/), [Node](https://nodejs.org), and [Yarn](https://yarnpkg.com) installed on your machine
- Run `yarn` to install libraries
- Run `yarn dev` to develop
- Run `yarn test:watch` to update tests
- Submit a pull request to `master`
- Continuous Integration runs `yarn verify` to ensure things are working as expected
- An admin merges your pull request into `master` and releases a new version
```
