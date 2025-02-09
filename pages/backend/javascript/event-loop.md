# Event loop

## Introduction

The event loop is a mechanism in JavaScript that allows handling asynchronous events.

When an async function executes, the callback function is pushed into a queue (not executed yet). The JavaScript engine continue to execute the code after the async function.

doesn't start processing the event loop until the code after an  has executed. 

It then checks the queue for any pending events. If there are any events in the queue, it will process them one by one.


## Example

Here is an example of how the event loop works:

```javascript
console.log('Hi');

setTimeout(function cb1() {
  console.log('cb1');
}, 5000);

console.log('Bye');
```

The output of this code will be:

```
Hi
Bye
cb1
```

This is because the `console.log('Hi')` and `console.log('Bye')` statements are executed first, before the `console.log('cb1');`

The `setTimeout()` function is called with a callback function `cb1()`. The callback function is added to the callback queue after 5 seconds.

The event loop then waits for the call stack to be empty before executing the callback function. Since there are no other functions in the call stack, the callback function is executed and logs `'cb1'` to the console.
