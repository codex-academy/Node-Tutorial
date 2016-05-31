---
layout: default
---

# Node tutorial

This is a  quick introduction to using JavaScript on the command line using Node.JS.

## Testing what've done

There are some pre-written tests that will track your progress through this tutorial. To test that you have done the right thing you need to have the `mocha` module installed.

Install it by typing this into a terminal window:

```
sudo npm install -g mocha
```

The `-g` is for global package. That means you will be able to run mocha from the command line, from any directory.

You now need to:

* fork the [Node-Tutorial](https://github.com/codex-academy/Node-Tutorial) repository
* clone a copy into your local projects folder
* open a new terminal window and change into the ```node-tutorial``` folder
* run mocha in that folder - type ```mocha``` and press enter - you should a message saying ```0 passing (1ms)```
* you should get messages about some failing tests
* all the work below should be done in the ```node-tutorial``` folder.

You can use the command below to see which tests are passing and which not:

`mocha`

As you work your way through the tasks run the `mocha` command after each test to be sure that your implementation is successful. As you work your way through the tutorial more and more of the tests should pass.

## Hello terminal

Create a file called `hello.js` in the node-terminal folder, in the script write 'hello world!' to the console.

You can run the program from the command line using: `node hello.js`

Run `mocha` from the command line. At least one test should pass.
