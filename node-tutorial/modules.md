---
layout: default
---

## Modules

So far all the NodeJS programs your wrote were little islands, the only way they communicated with the end user was through the console. And the only way we were able to test them was using some trickery to track what was logged to the console.

For sharing JavaScript files in the browser one uses the `script` tag, but it is also tricky as these script references needs to be loaded in the right order, etc.

NodeJS has a more sophisticated module system, that is based on CommonJS. Not only can you create your own modules, but NodeJS also has it own built in modules that you can use to access files on disk for example.

To create a module that exports two methods called `high` and `low` you need do the following:

```javascript
exports.high = function(){
  return "high";
};

exports.low = function(){
 return "low";
}
```

Save the above code in a file called `my_module.js`, then create a new file, let's say called `test_modules.js`. You can use it as a module like this:

```javascript
// note the ./ in front of the module name
var low_or_high = require('./my_module');

console.log(low_or_high.low());
console.log(low_or_high.high());
```

If you run `test_modules.js` using `nodejs test_modules.js` then you should see:


```
low
high
```

printed to the screen.

Run `mocha` from the command line. The 'Let's use modules' test should pass.

Why use modules you ask? You use modules to break your program down into more manageable parts, encouraging decoupling of code. Or to break it into logical components that each focus on a specific task. It also makes it easier for one to test each component. Testable code is decoupled code that is properly componentized by using modules.

## More modules:

One can also create modules that export a whole new constructor function of its own. And it can take in parameters at construction time.

It looks like this:

```javascript
module.exports = function(descMap){

  this.high = function(){
    return descMap['high'];
  }

  this.low = function(){
   return descMap['low'];
  }
}
```

Save this code in a file called `another_module.js`

Create another file called `another_module_test.js` and use this module in there:

```javascript
var AnotherModule = require('./another_module');

var anotherModule = new AnotherModule({low : "very low", high : "very high"});

console.log(anotherModule.high());
console.log(anotherModule.low());

```

Running this should print:

```
very low
very high
```

To the screen

If you run `mocha` the 'Constructor module' test should pass.



Now use [your newly found knowledge about modules](lets-get-modular.html).
