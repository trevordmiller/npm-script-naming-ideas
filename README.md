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
  "stage": "publish the latest version to a test environment",
  "release": "publish the latest version to production",
  "start": "start production process(es)"
}
```

## Examples

### Library

```
"scripts": {
  "dev": "npm run build -- --watch",
  "test:watch": "npm test -- --watch",
  "verify": "npm test && npm run lint && npm run build",
  "test": "jest src",
  "lint": "eslint src",
  "build": "babel src -d build -i '**/*.test.js'",
  "release": "git checkout master && git pull && npm run build && npm version && git push && git push --tags && npm publish"
}
```

### Web App

```
"scripts": {
  "dev": "next",
  "test:watch": "npm test -- --watch",
  "verify": "npm test && npm run lint && npm run build",
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
  "test:watch": "npm test -- --watch",
  "verify": "npm test && npm run lint",
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

- Ensure you have the latest versions of [Git](https://git-scm.com/) and [Node + npm](https://nodejs.org) installed
- Run `npm install` to install libraries
- Run `npm run dev` to develop
- Run `npm test:watch` to update tests
- Submit a pull request to `master`
- Continuous Integration runs `npm run verify` to ensure things are working as expected
- An admin merges your pull request into `master` and releases a new version
```
