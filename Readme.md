
# Easily build your reprocessing game to mobile & desktop & web!

## Prequisites

[ios-deploy](https://github.com/ios-control/ios-deploy#readme) must be installed globally with `npm i -g ios-deploy@beta --unsafe-perm=true` per [issue](https://github.com/ios-control/ios-deploy/issues/415#issuecomment-617270636).

Installing with `brew install ios-deploy` may not work.

```
Usage:
- rsb all
    builds all targets
- rsb js
    builds js target to `./public`
- rsb js:serve [port: default 3451]
    builds js target and starts a web server in `./public`
- rsb native
    builds macos native
- rsb native:hot
    builds native, runs the server, and starts the app in hot-reloading mode
- rsb native:bundle
    builds native and bundles
- rsb ios
    builds for ios
- rsb ios:full
    builds for ios & runs xcodebuild
- rsb ios:run
    builds for ios & runs xcodebuild & runs it in a simulator
- rsb android
    builds for android & runs `./gradlew assembleDebug`
- rsb android:run
    builds for android & runs `./gradlew installDebug` in the `./android` directory
- rsb android:hot
    builds for android & runs `./gradlew installDebug`, then sets up a hot-reloading server and watches your files.
```

## Future desired changes

Convert the following dependencies to reason:

- webpack
  - use something like https://github.com/prakhar1989/ocaml-js
  - don't need any of webpack's fancy features
- [ios-sim](https://github.com/ios-control/ios-sim#readme)
  - this shouldn't be too hard - just use xcodebuild & parse some things
- [ios-deploy](https://github.com/ios-control/ios-deploy#readme)
  - this has a large native objc component, which might me more difficult to translate
  - on the other hand, we could leave it as objc & just move over any js bits
