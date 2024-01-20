---
title: 'Common performance problem using JavaScript Promise'
date: '2024-01-20'
---

### What I`m talking about?

Working with Promises in JavaScript is a very easy and great way to handle multiple things we use to do in our daily basis. Making API calls, avoid the use of callbacks in some situations and many other things. But there`s a **common mistake** that developers make when working with Promises to handle synchronous executions.

Let`s say that you want to execute some action only when a few API calls finish, but the **calls does not have any dependency between each other**. Sometimes people use to do that in this way:
```
async function synchronousExecution() {
  await apiCallNumber1();
  await apiCallNumber2();
  ...

  executeAnotherAction();
}
``` 

Can you spot the problem with that solution?

### Oh no! Performance problem!

Yeahh... that's the point. The code that I show you earlier has a performance problem. If you notice in my explanation, the API calls doesn't have any depency between then, so, why do I need to wait the end of the first call to make the second one? This doesn't seems right.

Okay, you can simple say that you can remove the **await** and the would work, the two calls would be executed without waiting... Yeah, you're right, but how do I guarantee that my "**executeAnotherAction()**" would be executed only when the two calls finished and receive their responses?

Here is the tricky with this problem. If you're a beginner in JavaScript you could think that there's no solution for this case, but there's a way to solve this. Let me explain

### Promise.all

Did you ever heard about that? Promise.all, by the definition of [Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all) is:

> A static method that takes an iterable of promises as input and returns a single Promise. 

That means: *When all promises passed to the Promise.all method resolves, the Promise.all will also resolve. When any of the promisses reject, the Promise.all would also reject*.

Great! This way we can use that method to rewrite our code like that:

```
async function synchronousExecution() {
  Promise.all([
    apiCallNumber1(),
    apiCallNumber2()
  ]).then(() => {
    executeAnotherAction();
  })
}
``` 

If for some reason you also need the return values passed in the resolve of each promise passed as input, you can do this:

```
  Promise.all([promise1, promise2, promise3]).then(values => {
    console.log(values)
  })
```

This will return an Array containing the values of each promise from the argument list.

### Problems with the solution

This solution won't fit all cases. The fact that if any promise reject would reject the entire Promise.all could be a problem for you depending of your situations. But it's necessary to understand each specific case to determine the best solution for you and increase the performance of your code when necessary.

**That's all folks. Thank you for reading.**