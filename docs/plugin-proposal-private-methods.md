---
id: babel-plugin-proposal-private-methods
title: @babel/plugin-proposal-private-methods
sidebar_label: proposal-private-methods
---

## Example

```js
class Counter extends HTMLElement {
  #xValue = 0;

  get #x() { return this.#xValue; }
  set #x(value) {
    this.#xValue = value;
    window.requestAnimationFrame(
      this.#render.bind(this));
  }

  #clicked() {
    this.#x++;
  }
}
```

## Installation

```sh
$ npm install @babel/plugin-proposal-private-methods
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": ["@babel/plugin-proposal-private-methods"]
}
```

### Via CLI

```sh
$ babel --plugins @babel/plugin-proposal-private-methods script.js
```

### Via Node API

```javascript
require("@babel/core").transform("code", {
  plugins: ["@babel/plugin-proposal-private-methods"],
});
```

## References

- [Proposal: Private methods and getter/setters for JavaScript classes](https://github.com/tc39/proposal-private-methods)
