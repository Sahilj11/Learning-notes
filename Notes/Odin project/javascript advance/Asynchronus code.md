## What is it
JavaScript includes support for asynchronous functions, or to put it another way, functions that can happen in the background while the rest of your code executes.

The word 'asynchronous', aka 'async' just means 'takes some time' or 'happens in the future, not right now'. Usually callbacks are only used when doing I/O, e.g. downloading things, reading files, talking to databases, etc.

### Callback
A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.

Callbacks are functions that are executed asynchronously, or at a later time. Instead of the code reading top to bottom procedurally, async programs may execute different functions at different times based on the order and speed that earlier functions like http requests or file system reads happen.

Callbacks are simply functions that get passed into other functions. For example:
```javascript
myDiv.addEventListener("click", function(){
  // do something!
})
```


Usually things that have to talk to hard drives or networks will be asynchronous. If they just have to access things in memory or do some work on the CPU they will be synchronous. The reason for this is that I/O is reallyyy reallyyy sloowwww. A ballpark figure would be that talking to a hard drive is about 100,000 times slower than talking to memory (e.g. RAM).
#### Callback hell
```javascript
downloadPhoto('http://coolcats.com/cat.gif', handlePhoto)

function handlePhoto (error, photo) {
  if (error) console.error('Download error!', error)
  else console.log('Download finished', photo)
}

console.log('Download started')
```

The biggest hurdle people have when trying to understand callbacks is understanding the order that things execute as a program runs. In this example three major things happen. First the `handlePhoto` function is declared, then the `downloadPhoto` function is invoked and passed the `handlePhoto` as its callback, and finally `'Download started'` is printed out.

Note that the `handlePhoto` is not invoked yet, it is just created and passed as a callback into `downloadPhoto`. But it won't run until `downloadPhoto` finishes doing its task, which could take a long time depending on how fast the Internet connection is.

This example is meant to illustrate two important concepts:

- The `handlePhoto` callback is just a way to store some things to do at a later time
- The order in which things happen does not read top-to-bottom, it jumps around based on when things complete

Certainly! Let's walk through the example with actual code to illustrate the concepts of callbacks and asynchronous execution in JavaScript.

```javascript
// Declaration of the handlePhoto callback function
function handlePhoto(photo) {
    console.log('Handling photo: ' + photo);
}

// The downloadPhoto function with a callback
function downloadPhoto(callback) {
    console.log('Download in progress...');
    setTimeout(function () {
        console.log('Download completed');
        callback('Photo123.jpg');
    }, 2000); // Simulating a 2-second delay for downloading
}

// Invocation of the downloadPhoto function with handlePhoto as the callback
console.log('Start of the program');
downloadPhoto(handlePhoto);
console.log('End of the program');
```

Output:

```
Start of the program
Download in progress...
End of the program
Download completed
Handling photo: Photo123.jpg
```

Here's how the code flows:

1. The `handlePhoto` function is defined to handle a photo. It just logs a message to the console indicating that it's handling the photo.

2. The `downloadPhoto` function is defined. Inside this function:
   - It logs a message indicating that the download is in progress.
   - It sets up a timeout using `setTimeout` to simulate the time it takes to download a photo (2 seconds in this case).
   - When the timeout expires, it logs a message indicating that the download is completed, and then it invokes the `handlePhoto` function with the photo name as an argument.

3. The program starts by logging "Start of the program".

4. The `downloadPhoto` function is invoked with the `handlePhoto` function as its argument (callback).

5. The program logs "Download in progress...", then proceeds to the next line immediately without waiting for the download to finish. This demonstrates asynchronous execution.

6. The program logs "End of the program". This further highlights that the program doesn't wait for the asynchronous tasks to complete before moving on.

7. After 2 seconds (simulated download time), the timeout in the `downloadPhoto` function expires, and the download completion message is logged.

8. The `handlePhoto` function is invoked with the photo name `'Photo123.jpg'`. It logs "Handling photo: Photo123.jpg".

In summary, callbacks in JavaScript allow you to define what should happen after an asynchronous task is completed. The program doesn't wait for asynchronous tasks to finish; it continues executing the next instructions. This event-driven and asynchronous behavior is what allows JavaScript to efficiently handle tasks that might take time, like network operations or file reading.

#### Handling error in callback 
There are different types of errors: syntax errors caused by the programmer (usually caught when you try to first run the program), runtime errors caused by the programmer (the code ran but had a bug that caused something to mess up), platform errors caused by things like invalid file permissions, hard drive failure, no network connection etc. This section is only meant to address this last class of errors.

The first two rules are primarily about making your code readable, but this one is about making your code stable. When dealing with callbacks you are by definition dealing with tasks that get dispatched, go off and do something in the background, and then complete successfully or abort due to failure. Any experienced developer will tell you that you can never know when these errors happen, so you have to plan on them always happening.

With callbacks the most popular way to handle errors is the Node.js style where the first argument to the callback is always reserved for an error.
```javascript
 var fs = require('fs')

 fs.readFile('/Does/not/exist', handleFile)

 function handleFile (error, file) {
   if (error) return console.error('Uhoh, there was an error', error)
   // otherwise, continue on and use `file` in your code
 }
```
Having the first argument be the `error` is a simple convention that encourages you to remember to handle your errors. If it was the second argument you could write code like `function handleFile (file) { }` and more easily ignore the error.