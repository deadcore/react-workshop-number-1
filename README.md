# React workshop 1

In this workshop we focus on setting up our [React](https://reactjs.org/) as well as setting up a basic todo app

Use and understand why we use the `create-react-app` cli to bootstrap our application

Begin creating a `MaterialUi` themed todo app

## NPM
NPM stands for Node Package Manager.
The package manager for Node based environments

## Babel
As any language, Javascript also has versions named ECMAScript (short for ES). Currently, most browsers support ES5. ES5 used to be good even though it was painful to code in it. Remember, this not reading from inside callback functions? The new version of Javascript, ES6, also known as ES2015 (specs of the language were finalized in June 2015) makes Javascript great again. If you want to learn about ES6, check out the links at the end of this article. All the great features of ES6 come with one big problem — majority of browsers do not fully support them. That’s when Babel comes to play. Babel is a JS transpiler that converts new JS code into old ones. It is a very flexible tool in terms of transpiling. One can easily add presets such as es2015, es2016, es2017, so that Babel compiles them to ES5.

Here is an example — a code written in ES6:
```
class Test {
  calculatePowers() {
    return [1,2,3].map(n => n ** 2);
  }
}
```
Babel will transpile this code to the following, given the presets es2015:

```
"use strict";
var _createClass = function () { function defineProperties(target, props) { for (var i = 0; i < props.length; i++) { var descriptor = props[i]; descriptor.enumerable = descriptor.enumerable || false; descriptor.configurable = true; if ("value" in descriptor) descriptor.writable = true; Object.defineProperty(target, descriptor.key, descriptor); } } return function (Constructor, protoProps, staticProps) { if (protoProps) defineProperties(Constructor.prototype, protoProps); if (staticProps) defineProperties(Constructor, staticProps); return Constructor; }; }();
function _classCallCheck(instance, Constructor) { if (!(instance instanceof Constructor)) { throw new TypeError("Cannot call a class as a function"); } }
var Test = function () {
  function Test() {
    _classCallCheck(this, Test);
  }
_createClass(Test, [{
    key: "calculatePowers",
    value: function calculatePowers() {
      return [1, 2, 3].map(function (n) {
        return Math.pow(n, 2);
      });
    }
  }]);
return Test;
}();
```

This is an example of how Babel allows us to have a clean, maintainable code using the latest JS specifications without needing to worry about browser support.

## Webpack

Webpack is a modular build tool that has two sets of functionality — Loaders and Plugins.
Loaders transform the source code of a module. For example, `style-loader` adds CSS to DOM using style tags.
`sass-loader` compiles SASS files to CSS. `babel-loader` transpiles JS code given the presets.

Plugins are the core of Webpack. They can do things that loaders can’t. For example, there is a plugin called `UglifyJS` that minifies and uglifies the output of webpack.

## Flexbox
* Easier to reason with
* The old way was `margin 0 auto` which when you wanted to extend or even add margins to the element it would cause problems
* Margins were never meant for centre aligning things in the DOM

## Floats
* Floats were never meant for layout.
* wrapping text around an element.

They’re simply meant to take an element, put it to one side, and let other content flow around it. That’s all.

So why are we using them for layout?

Because you can clear a footer below two floated columns, float layout came into being. If there had ever been a way to “clear” elements below positioned elements, we’d never have bothered to use floats for layout.

## Citation
* [What are NPM, Yarn, Babel, and Webpack; and how to properly use them?](https://medium.com/front-end-hacking/what-are-npm-yarn-babel-and-webpack-and-how-to-properly-use-them-d835a758f987)
