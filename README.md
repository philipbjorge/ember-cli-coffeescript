# DEPRECATED
## Use https://github.com/typed-ember/ember-cli-typescript instead

# TypeScript support for ember-cli [![Build Status](https://travis-ci.org/philipbjorge/ember-cli-typescript-compiler.svg)](https://travis-ci.org/philipbjorge/ember-cli-typescript-compiler)
Adds precompilation of TypeScript files while still allowing a mix of ES6 and TS files in your ember-cli project.

Caveats: SourceMaps don't work and errors aren't emitted.

## Why was this created?
All the other addons were either not usable, not production ready, or terribly outdated.
This addon has support for blueprints as well as the latest versions of typescript (1.6, 1.7) thanks to [tildeio/broccoli-typescript-compiler](https://github.com/tildeio/broccoli-typescript-compiler).

### Includes
- Preprocessing TypeScript-files in your app, including tests
- Blueprints

### Install
**Requires that you have ember-cli-babel in your packages.json**

```
ember install ember-cli-typescript-compiler
```

I would also recommend disabling sourcemaps in ember-cli-build as they don't seem to work and it speeds up builds.
```
  var app = new EmberApp(defaults, {
    sourcemaps: {
      enabled: false, // these don't work right now with ts or es6
    }
    // Add options here
  });
```

At this point, you can rename any JS file under the app/ or test/ folders to .ts and expect it to work!

### How to use

Currently there are no options to pass in.

### How it works
Compiles TS files to ES6 => ES6 to ES5 transpilation handled by ember-cli-babel => ES6 module transformation handled by ember-cli
