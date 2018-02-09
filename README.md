# How to create a new React project from scratch using TypeScript and webpack


This is a quick walkthrough showing a minimal set of steps to setup a new React project from scratch using TypeScript and webpack. It is assumed the reader is already familiar with basic Node.js and React fundamentals and comfortable working with a command prompt, and that Node.js is already installed.

## Getting started
Open a command prompt, create a new directory for the sample project, and initialize npm...

```
$ mkdir react1
$ cd react1
$ npm init -y
```

## Install required dependencies...
```
$ npm install typescript webpack babel-core babel-loader babel-preset-es2015 babel-preset-react ts-loader webpack-dev-server --save-dev
$ npm install react react-dom --save
$ npm install @types/react @types/react-dom --save-dev
```

## Edit file `package.json` to configure the `npm start` command...
```json
"scripts": {
  "start": "webpack-dev-server"
}
```

## Generate file `tsconfig.json`...
```
$ tsc --init --jsx preserve --module es6 --target es6 --sourceMap --allowSyntheticDefaultImports
```

## Add file `.babelrc`...
```json
{
  "presets": ["es2015", "react"]
}
```

## Add file `webpack.config.js`...
```js
const webpack = require('webpack');
const path = require('path');

module.exports = {
  devtool: 'eval',
  entry: ['index.tsx'],
  output: {
    filename: 'app.js',
    publicPath: 'dist',
    path: path.resolve('dist'),
  },
  devServer: {
    port: 3000,
    historyApiFallback: true,
    inline: true,
  },
  resolve: {
    extensions: ['.ts', '.tsx', '.js'],
    modules: ['src', 'node_modules'],
  },
  module: {
    loaders: [
      {
        test: /\.tsx?$/,
        loaders: ['babel-loader', 'ts-loader'],
        include: path.resolve('src'),
      }
    ]
  }
};
```

## Add file `src/index.tsx`...
```jsx
import React from 'react';
import ReactDOM from 'react-dom';

const App = () => 
    <div>
      <p>Hello world!</p>
    </div>;

ReactDOM.render(<App />, document.getElementById('app'));
```

## Start the webpack development server...
```
$ npm start
```

Navigate browser to http://localhost:3000 to view the **Hello world!** page.

Go back and make some changes to the page and notice the page is automatically reloaded when edited!


## Rererences
* [Getting started with TypeScript and React](https://javascriptplayground.com/blog/2017/04/react-typescript/)
