[![Build Status](https://travis-ci.org/MicheleBertoli/react-fix-it.svg?branch=master)](https://travis-ci.org/MicheleBertoli/react-fix-it)

# React Fix It
Automagically generate tests from errors.

Follow the flow:

- Enhance your components with `fixIt`
- Write some bugs (or wait for your components to fail)
- Open the console and copy the test snippet
- Paste the code to reproduce the error
- Fix the bugs and celebrate

:warning: This package uses [react-component-errors](https://github.com/staxmanade/react-component-errors) to wrap the lifecycle methods into a try...catch block, which affects the performance of your components. Therefore it should **not** be used in production.

They easiest way to patch automatically all the components in development mode is by using [babel-plugin-react-fix-it](https://github.com/MicheleBertoli/babel-plugin-react-fix-it) with the following configuration:
```json
{
  "env": {
    "development": {
      "plugins": ["react-fix-it"]
    }
  }
}
```

## Demo

![Demo](demo.gif)

## Installation

> You can either install it with [npm](https://nodejs.org/en/) or [yarn](https://yarnpkg.com/)

```sh
npm install --save-dev react-fix-it
```
or
```sh
yarn add --dev react-fix-it
```

## Usage

```jsx
import React, { Component } from 'react'
import fixIt from 'react-fix-it'

class MyComponent extends Component {
  render() {
    return <div>Hello ⚛</div>
  }
}

export default fixIt(MyComponent)
```

## Test
```sh
npm test
```
or

```sh
yarn test
```
