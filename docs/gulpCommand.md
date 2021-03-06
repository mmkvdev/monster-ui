title: Gulp command

# Gulp Command

`gulp` - Toolkit to manage Monster UI builds and related tasks

* [Synopsis](#synopsis)
* [Description](#description)
* [Commands](#comamnds)
* [Options](#Options)

## Synopsis

```
gulp [serve-dev]            [--pro=<name>] [--require ./.babelregister.js]
gulp build-dev              [--pro=<name>] [--require ./.babelregister.js]
gulp serve-prod             [--pro=<name>] [--require ./.babelregister.js]
gulp build-prod             [--pro=<name>] [--require ./.babelregister.js]
gulp build-app --app=<name> [--pro]        [--require ./.babelregister.js]
gulp lint [--app=<name>]
```

## Description

Build Monster UI for either development, or production environment, the result of which is located in the `dist` folder, at the root level of the project.

## Commands

###### `serve-dev`

Compile SCSS to CSS, launch Web server ([browsersync](https://www.npmjs.com/package/browser-sync)) and serve project at `http://localhost:3000/`, include a CSS watcher that make changes immediate in the browser, UI reloads automatically on file save.

###### `build-dev`

Compile SCSS to CSS.

###### `build-prod`

Compile SCSS to CSS, merge all templates in a single `templates.js` file, run require, minify `main.js` and `templates.js` and minify CSS files.

##### `serve-prod`

Run the `build-prod` task and serves the results at `http://localhost:3000/`.

###### `build-app --app=<name>`

To build an app independently, you will need to clone it inside the `/src/app` folder of `monster-ui` and then run this command while indicating which app you want to build.

##### `lint`

Run the Monster UI linter for the whole project (including apps).

##### `lint --app=<name>`

Run the Monster UI linter for the app specified as `<name>`.

## Options

###### `--pro=<name>`

Some applications might have a pro version. If that is the case and you want to build it with the 'pro' assets, you need to set the `pro` option and specify the name of the application.

###### `--require ./.babelregister.js`

This option [forcefully loads](https://github.com/babel/babel/issues/4082) the list of globs that specify the files to be compiled by [Babel](https://babeljs.io/), from `.babelrc.js`. It is particularly needed when you are using a Node version lower than 6.0.0, in order to process some node modules that use unsupported ES2015+ syntax:

```
gulp --require ./.babelregister.js
```
