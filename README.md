# npm-script-naming-ideas

Ideas for `package.json` npm script naming

```
{
  "scripts": {
    "dev": "...",
    "verify": "...",
    "test": "...",
    "lint": "...",
    "build": "...",
    "release": "...",
    "start": "..."
  }
}
```

# `dev`

_Run the main process(es) for developing_

Website example:
```
"dev": "next",
```

Web app example:
```
"dev": "react-scripts start",
```

Service example:
```
"dev:build": "yarn build -- --watch",
"dev:server": "nodemon build/index.js",
"dev:test: "yarn test -- --watch",
```

Library example: 
```
"dev:build": "yarn build -- --watch",
"dev:test": "yarn test -- --watch",
```

Desktop app example:
```
"dev:build": "BROWSER=none node scripts/start.js",
"dev:server": "electron .",
```

# `verify`

_Verify things are working as expected (helpful to run on CI)_

General example:
```
"verify": "yarn test && yarn lint && yarn build",
```

# `test`

_Run tests_

General example:
```
"test": "jest src",
```

# `lint`

_Run linter_

General example:
```
"lint": "eslint src",
```

# `build`

_Create a transpiled directory from source files_

Website example:
```
"build": "next build",
```

Web app example:
```
"build": "react-scripts build",
```

Library example:
```
"build": "babel src -d build",
```

# `release`

_Publish a release_

Website/web app/service example:
```
"release": "git checkout master && git pull && now",
```

Library example: 
```
"release": "git checkout master && git pull && yarn build && yarn version && git push && git push --tags && yarn publish"
```

Desktop app example:
```
"release": "git checkout master && git pull && yarn build && yarn version && git push && git push --tags && yarn icns && yarn bundle && yarn dmg"
```

# `start`

_Start a production service like an API_

Service example:
```
"start": "node build/index.js"
```
