---
id: installation
title: Installation
permalink: docs/installation.html
redirect_from:
  - "download.html"
  - "downloads.html"
  - "docs/tooling-integration.html"
  - "docs/package-management.html"
  - "docs/language-tooling.html"
  - "docs/environments.html"
next: hello-world.html
---

React is flexible and can be used in a variety of projects. You can create new apps with it, but you can also gradually introduce it into an existing codebase without doing a rewrite.

Here are a couple of ways to get started:

* [Try React](#trying-out-react)
* [Create a New App](#creating-a-new-application)
* [Add React to an Existing App](#adding-react-to-an-existing-application)

## Trying Out React

If you're just interested in playing around with React, you can use CodePen. Try starting from [this Hello World example code](http://codepen.io/gaearon/pen/rrpgNB?editors=0010). You don't need to install anything; you can just modify the code and see if it works.

If you prefer to use your own text editor, you can also <a href="https://raw.githubusercontent.com/reactjs/reactjs.org/master/static/html/single-file-example.html" download="hello.html">download this HTML file</a>, edit it, and open it from the local filesystem in your browser. It does a slow runtime code transformation, so don't use it in production.

If you want to use it for a full application, there are two popular ways to get started with React: using Create React App, or adding it to an existing application.

## Creating a New Application

[Create React App](http://github.com/facebookincubator/create-react-app) is the best way to start building a new React single page application. It sets up your development environment so that you can use the latest JavaScript features, provides a nice developer experience, and optimizes your app for production.

```bash
npm install -g create-react-app
create-react-app my-app

cd my-app
npm start
```

Create React App doesn't handle backend logic or databases; it just creates a frontend build pipeline, so you can use it with any backend you want. It uses build tools like Babel and webpack under the hood, but works with zero configuration.

When you're ready to deploy to production, running `npm run build` will create an optimized build of your app in the `build` folder. You can learn more about Create React App [from its README](https://github.com/facebookincubator/create-react-app#create-react-app-) and the [User Guide](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#table-of-contents).

## Adding React to an Existing Application

You don't need to rewrite your app to start using React.

We recommend adding React to a small part of your application, such as an individual widget, so you can see if it works well for your use case.

While React [can be used](/docs/react-without-es6.html) without a build pipeline, we recommend setting it up so you can be more productive. A modern build pipeline typically consists of:

* A **package manager**, such as [Yarn](https://yarnpkg.com/) or [npm](https://www.npmjs.com/). It lets you take advantage of a vast ecosystem of third-party packages, and easily install or update them.
* A **bundler**, such as [webpack](https://webpack.js.org/) or [Browserify](http://browserify.org/). It lets you write modular code and bundle it together into small packages to optimize load time.
* A **compiler** such as [Babel](http://babeljs.io/). It lets you write modern JavaScript code that still works in older browsers.

### Installing React

>**Note:**
>
>Once installed, we strongly recommend setting up a [production build process](/docs/optimizing-performance.html#use-the-production-build) to ensure you're using the fast version of React in production.

We recommend using [Yarn](https://yarnpkg.com/) or [npm](https://www.npmjs.com/) for managing front-end dependencies. If you're new to package managers, the [Yarn documentation](https://yarnpkg.com/en/docs/getting-started) is a good place to get started.

To install React with Yarn, run:

```bash
yarn init
yarn add react react-dom
```

To install React with npm, run:

```bash
npm init
npm install --save react react-dom
```

Both Yarn and npm download packages from the [npm registry](http://npmjs.com/).

### Enabling ES6 and JSX

We recommend using React with [Babel](http://babeljs.io/) to let you use ES6 and JSX in your JavaScript code. ES6 is a set of modern JavaScript features that make development easier, and JSX is an extension to the JavaScript language that works nicely with React.

The [Babel setup instructions](https://babeljs.io/docs/setup/) explain how to configure Babel in many different build environments. Make sure you install [`babel-preset-react`](http://babeljs.io/docs/plugins/preset-react/#basic-setup-with-the-cli-) and [`babel-preset-env`](http://babeljs.io/docs/plugins/preset-env/) and enable them in your [`.babelrc` configuration](http://babeljs.io/docs/usage/babelrc/), and you're good to go.

### Hello World with ES6 and JSX

We recommend using a bundler like [webpack](https://webpack.js.org/) or [Browserify](http://browserify.org/) so you can write modular code and bundle it together into small packages to optimize load time.

The smallest React example looks like this:

```js
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```

This code renders into a DOM element with the id of `root` so you need `<div id="root"></div>` somewhere in your HTML file.

Similarly, you can render a React component inside a DOM element somewhere inside your existing app written with any other JavaScript UI library.

[Learn more about integrating React with existing code.](/docs/integrating-with-other-libraries.html#integrating-with-other-view-libraries)

### Development and Production Versions

By default, React includes many helpful warnings. These warnings are very useful in development.

**However, they make the development version of React larger and slower so you should use the production version when you deploy the app.**

Learn [how to tell if your website is serving the right version of React](/docs/optimizing-performance.html#use-the-production-build), and how to configure the production build process most efficiently:

* [Creating a Production Build with Create React App](/docs/optimizing-performance.html#create-react-app)
* [Creating a Production Build with Single-File Builds](/docs/optimizing-performance.html#single-file-builds)
* [Creating a Production Build with Brunch](/docs/optimizing-performance.html#brunch)
* [Creating a Production Build with Browserify](/docs/optimizing-performance.html#browserify)
* [Creating a Production Build with Rollup](/docs/optimizing-performance.html#rollup)
* [Creating a Production Build with webpack](/docs/optimizing-performance.html#webpack)

### Using a CDN

If you don't want to use npm to manage client packages, the `react` and `react-dom` npm packages also provide single-file distributions in `umd` folders, which are hosted on a CDN:

```html
<script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
```

The versions above are only meant for development, and are not suitable for production. Minified and optimized production versions of React are available at:

```html
<script crossorigin src="https://unpkg.com/react@16/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.production.min.js"></script>
```

To load a specific version of `react` and `react-dom`, replace `16` with the version number.

If you use Bower, React is available via the `react` package.

#### Why the `crossorigin` Attribute?

If you serve React from a CDN, we recommend to keep the [`crossorigin`](https://developer.mozilla.org/en-US/docs/Web/HTML/CORS_settings_attributes) attribute set:

```html
<script crossorigin src="..."></script>
```

We also recommend to verify that the CDN you are using sets the `Access-Control-Allow-Origin: *` HTTP header:

![Access-Control-Allow-Origin: *](../images/docs/cdn-cors-header.png)

This enables a better [error handling experience](/blog/2017/07/26/error-handling-in-react-16.html) in React 16 and later.
