---
layout: default
title: Let's get modular
---

## Let's get modular

Now let's use your newly found knowledge about modules.

You will now create a new module and also use some of NodeJS's built-in modules. The module should be able to return a list of all the rows in all the files in a specified folder. Your module should be able to do that Synchronously and Asynchronously.

Your module should:

* find all the files in a folder
* read the contents of each file in the folder
* find each row in each file
* then append each row to a list
* return the list that contains all the lines off all the files.

For example:

* if there are 3 files in the folder
* and each file has 3 rows
* your modules should return a list containing 9 rows

Use the built in node module called `fs` - it stands for File System. The `fs` module handles accessing files from Node.JS.

**You should use these 2 function calls from the fs module in your module:**

* To get files in the folder: [readdirSync](http://nodejs.org/api/fs.html#fs_fs_readdirsync_path)
* To get the data in the files: [readFileSync](http://nodejs.org/api/fs.html#fs_fs_readfilesync_filename_options)

> You will need to pass in the encoding of `utf8` as an option parameter to `readFileSync` otherwise a buffer will be returned instead of the string value.

You can read more about the fs module at [the Node API documentation]( http://nodejs.org/api/fs.html).

The module should be in a file called:

* read-folder.js
* expose 2 methods with parameters:
    * ```linesInFiles``` which takes folderName as a parameter and returns an list
    * ```linesInFilesAsync``` which takes two parameters ```folderName and callback``` - the callback should return 2 parameters ```err``` & ```files```. Calling it should look like this:

        ```
        linesInFilesAsync('/dir/name', function(err, files){
        });
        ```
* use this folder as input: `./files/week1`
