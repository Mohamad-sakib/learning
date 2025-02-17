## js

is single thread programming language === one call stack === one peice of code executes at a time

### call stack(data structure)

keep track of which peice of code is currently executing in progarm
blowing of call stack can be done with recursive fns without basecondition.

## java runtime

is environment that allow java code to run and it includes javascript engine that executes js code and many other components that help
code interct with system it is running on.

## blocking

means someting make execution of program slow.

### AJAX

allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes.

## synch fns

- are fns that executes one after another.
- synch fns block the flow of execution of program untill currentely executing - sync executes completely means
- sync don't allow js engine to execute another instruction untile it executes completely.
- fns executes and completes their execution rightaway when they are called in call stack and block the main thread untill it completes its execution.

problem ?

- we are running it on browser for website,
- if fetching data from server had sync task and it had taken too much time that could endup blocking the working(frezing) of wesite untill all it is fetched.

## Soulution?

- async fns that doesn't block the flow of execution of program and let java engine to execute task later to it and async task are done in independently, once they are done , given to main thread.

## Async function

- are those dosen't block the main while executing
- allow java runtime to continue executing other fns while waiting asynch operation to complete.
- once asynch operation is done,its callback is pushed to callback queue
- the event loop look for empty call stack to push callback of asynch fns from callback queue
- then java engine executes them concurrentely.
- async fns take async call backs that are fns that are given to async fns to run later
- async fns's execution always starts immediately but don't block the flow exection and let js run rest of code while async fns's execution is done in background. and thier callback are called once its execution is done, callback are pushed to callback queue, all sync fns are executed ,call stack is empty.
- flow --> js runtime push them to call back queue once async are done with execution and they are later pushed to call stack when event loop finds call stack empty.

## sync callback vs async callback

callback given to async are called asynch callback
callback given to sync are called synch callback

both are executed differetly
sync callback are executed just after the sync function is called, if sync callback are called inside the sync function.
while for it is different since they are called after all sync function are executed.

# great summary

Summary:
JavaScript is single-threaded in that it executes code on a single call stack.
Asynchronous tasks (like setTimeout, network requests, etc.) are handled by the runtime environment (Web APIs in the browser or libuv in Node.js), not the JavaScript engine itself.
These tasks are executed outside the main thread and once completed, their callbacks are placed into the callback queue.
The event loop ensures that callbacks are executed after the synchronous code has finished, without blocking the main thread, allowing JavaScript to handle asynchronous operations efficiently despite being single-threaded.

### what happens in case of setTimeout

Recap of What Happens:
Step 1: setTimeout is called.
Step 2: setTimeout hands the task to the Web API to handle the timer.
Step 3: The ID is immediately returned by setTimeout (while the timer is running).
Step 4: The main thread continues executing the rest of the code.
Step 5: After the timer expires, the callback is placed in the callback queue.
Step 6: The event loop picks up the callback once the call stack is empty.
Step 7: The callback is executed, and the result is logged.

## how async callback is called with fetched data ? like how call back function get the data fetched . however first it passed to callback queue that don't hold fns calls instead only callback itself

## bind , call, apply pratice.

## practice for async fns
