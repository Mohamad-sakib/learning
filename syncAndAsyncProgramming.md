## js

is single thread programming language === one call stack === one peice of code executes at a time

### call stack

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
