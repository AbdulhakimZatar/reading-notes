# The Call Stack
A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions

The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.

## How does the call stack handle function calls?

```js
function firstFunction(){
  console.log("Hello from firstFunction");
}

function secondFunction(){
  firstFunction();
  console.log("The end from secondFunction");
}

secondFunction();
```

![example](https://cdn-media-1.freecodecamp.org/images/oEp65Ec9CD4CnL7t0uSPoyzrkA1i1BR-Ij1n)

This is what happens when the code is run:

1. When secondFunction() gets executed, an empty stack frame is created. It is the main (anonymous) entry point of the program.

2. secondFunction() then calls firstFunction()which is pushed into the stack.

3. firstFunction() returns and prints “Hello from firstFunction” to the console.

4. firstFunction() is pop off the stack.

5. The execution order then move to secondFunction().

6. secondFunction() returns and print “The end from secondFunction” to the console.

7. secondFunction() is pop off the stack, clearing the memory.

## What causes a stack overflow?
A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.


# Debugging
Most of your time as a developer is spent reading code followed by debugging that same code, most likely to be able to read it or solve an “unexpected feature” (which, joking aside, is more correctly known as a “bug”).

To debug your JS code, the easiest and maybe the most common way its to simply console.log() the variables you want to check or, by using chrome developer tools, open your page with your JS code (press cmd+o in macOS or Ctrl+o in Windows) and choose your file to debug, click the line you wanna debug and refresh your page again (F5).

## Types of error messages

1- **Reference errors:**

This is as simple as when you try to use a variable that is not yet declared you get this type os errors.

2- **Syntax errors:**

I know it’s in the name of the errors, but like it says itself, this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

3- **Range errors:**

Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.

4- **Type errors:**

Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.


