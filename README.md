<div align="center">
  <h1>React Native Boilerplate for iOS, Android, and Web</h1>
  <a href="https://david-dm.org/ethanneff/react-native-boilerplate">
    <img src="https://david-dm.org/ethanneff/react-native-boilerplate.svg" alt="Dependency Status" />
  </a>
  <a href="https://david-dm.org/ethanneff/react-native-boilerplate#info=devDependencies">
    <img src="https://david-dm.org/ethanneff/react-native-boilerplate/dev-status.svg" alt="devDependency Status" />
  </a>
  <a href="https://travis-ci.org/ethanneff/react-native-boilerplate">
    <img src="https://travis-ci.org/ethanneff/react-native-boilerplate.svg" alt="Build Status" />
  </a>
  <a href="https://coveralls.io/r/ethanneff/react-native-boilerplate">
    <img src="https://coveralls.io/repos/github/ethanneff/react-native-boilerplate/badge.svg" alt="Test Coverage" />
  </a>
</div>


## Status

* Super beta proof of concept. Still a work in progress.

## Purpose

* Faster development for all platforms ![image](https://i.imgur.com/sa5z3DR.gif)

## Vision

* Useful
  * React Native everywhere
* Simplicity
  * No task managers (`create-react-app` and `create-react-native-app` instead
    of Webpack, Gulp, and Grunt)
* No web hosting (A static Github Page instead of a web service)
* Scalability
  * Decoupled
  * TDD
  * Offline first
  * DX
  * Redux
  * Component hierarchy (bottom-up development)

## Methodology

* #### clone

  ```
  git clone git@github.com:ethanneff/react-native-boilerplate.git
  cd react-native-boilerplate
  npm install
  ```

* #### run

  ```
  yarn ios
  ```

  ```
  yarn android
  ```

  ```
  yarn web
  ```

* #### test

  ```
  yarn testing
  ```

  ```
  http://localhost:3000
  http://remotedev.io/local/
  http://localhost:8081/debugger-ui/
  ```

* #### publish

  ```
  yarn deploy
  ```

  * or merger into master (via TravisCI)

## Status

* Stable, but work in progress

  * [x] android
  * [x] ios
  * [x] web
  * [x] github pages
  * [x] testing framework
  * [x] linting
  * [x] continuous integration
  * [x] navigation
  * [ ] status bar handler
  * [x] redux
  * [ ] router redux
  * [x] reducer injector
  * [ ] test driven development
  * [ ] component example
  * [ ] desktop sizing
  * [ ] development flow documentation
  * [ ] fix routing again
  * [ ] fix ios console errors
  * [ ] figure out semantic release
  * [ ] add flow type

* Additional

  * remove all `// TODO:`
  * fix react router redux
    https://github.com/ReactTraining/react-router/blob/master/packages/react-router/docs/guides/redux.md
  * update redux saga injector
    https://github.com/GuillaumeCisco/redux-sagas-injector/pull/3

## Resources

* #### references

  * scalability https://github.com/react-boilerplate/react-boilerplate
  * multiple platforms https://github.com/react-everywhere/re-start
  * example https://github.com/grigio/HAgnostic-News

* #### tools

  * sublime linting
    https://medium.com/pvtl/linting-for-react-native-bdbb586ff694
  * sublime prettier https://packagecontrol.io/packages/JsPrettier

    ```sh
    # dependencies (global)
    npm i -g yarn
    # code quality (linting)
    yarn add -D husky # pre github hooks
    yarn add -D lint-staged # auto format hook
    yarn add -D prettier # format
    yarn add -D @commitlint/{config-conventional,cli} # forced commit messages
    yarn add -D semantic-release # auto release version
    yarn add -D coveralls # testing
    # debugging
    yarn add -D react-devtools
    yarn add -D remote-redux-devtools
    # create react native app (mobile)
    yarn add expo
    yarn add react
    yarn add -D react-native-scripts
    yarn add -D react-native-scripts
    yarn add -D react-test-renderer
    yarn add -D jest-expo
    # create react app (web)
    yarn add react-dom
    yarn add -D react-native-web
    yarn add -D react-scripts
    yarn add -D gh-pages
    # navigation
    yarn add react-router-dom
    yarn add react-router-native
    yarn add react-router-redux@next
    yard add history
    # data and business logic (redux)
    yarn add prop-types
    yarn add react-redux
    yarn add redux
    yarn add redux-thunk
    # soon
    yarn add immutable
    yarn add redux-immutable
    ```

* #### reset

  * update dependencies

    ```sh
    yarn npm-update-dep
    ```

    ```sh
    npm i -g yarn npm-check-updates depcheck react-native-git-upgrade
    depcheck
    ncu -a
    rm -rf ~/.rncache/
    rm -rf ./ios/build
    watchman watch-del-all
    yarn install
    yarn upgrade
    npm update
    react-native-git-upgrade
    yarn start --reset-cache
    yarn ios
    yarn web
    yarn test
    ```

  * whenever you update dependencies (optional)

    ```sh
    watchman watch-del-all
    rm -rf ./node_modules
    rm -rf $TMPDIR/react-*
    npm cache clean
    yarn cache clean
    yarn install
    yarn start --reset-cache
    ```

  * no bundle url present

    ```sh
    rm -rf ./ios/build
    yarn ios
    ```

  * Print: Entry, ":CFBundleIdentifier", Does Not Exist

    * make sure nothing is running on port :8080
    * make sure `app.json` and `index.js` have the same app name
    * mare sure `index.js` at root level
    * `rm -rf ~/.rncache/ && rm -rf ./ios/build`
    * `rm -rf ./ios && rm -rf ./android && react-native-git-upgrade`
    
