---
title: 'The Javascript Tricky Scope'
date: '2023-03-29'
---

### What is "Tricky" about scope?

Today I came accross a complicated BUG in my job where a pooling that should be happening, wasn't happening in a specific situation. While I was looking and studying the scenario I saw the same call being made in others parts of the code and working as expected. So **why that specific call wasn't working?**... Yeah, scope problem.

It took me a while to understand what was happening. In the other calls that was working the method was defined inside a Vue component and the scope inside the setTimeout are fine, but in the case of the class where the problem lived, things are not same.

To solve the BUG I just need to call the function inside the setTimeout using an **arrow function** like this:

> setTimeout(() => this.myMethod(), timeout)

instead of this:

> setTimeout(this.myMethod(), timeout)

And the tricky part, my friends, is the different between scopes in normal function and arrow functions and the way they handle with **"this"**

### Difference of "this" scope

Normal functions, when called, has the value of "this" defined by the execution context where the function was called. That means that the "this" can have different values depending on how the function was called.

You can see an example in this code:
```
const object = {
  name: 'example',
  func: function() {
    console.log(this.name);
  }
}

object.func(); // print the value 'example'

const func = object.func;
func(); // print 'undefined'
```

But why does that happens? Well, in the first call the function "func" is called from the "object", this makes the "this" to be the "object" itself that has the property "name" and a function "func". In the second case the "func" is called like an function by its own and not as an object method causing the "this" to have the value of "undefined"

When we work with arrow functions the "this" value is defined in the moment where the function is defined, not when the function is called. The value of "this" is defined by the scope where the function was when defined. See the example below:

```
class Test {
  name = 'example';
  
  object = {
    name: 'other example',
    func: () => {
      console.log(this.name); // imprime 'example'
    }
  }
}

const test = new Test();
test.object.func(); 
```

In this example, the arrow function is defined inside of the object "object" and the context or scope of the "this" is determined by where the function was defined. That's why the value printed on the console is "example" because the context of the arrow function in this case is the same of the "name" defined in the class. The value "this" for the arrow function will have the scope of the class where the function was defined.

I hope this explanation was clear and you can solve problems in the future knowning this like I solve the BUG today.