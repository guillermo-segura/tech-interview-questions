# JavaScript

## What is Hoisting?

Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function).

Variables defined with `let` and `const` are hoisted to the top of the block, but not initialized:

- Using a let variable before it is declared will result in a `ReferenceError`

- Using a const variable before it is declared, is a syntax error, so the code will simply not run.

JavaScript only hoists declarations, not initializations. Hoisting is (to many developers) an unknown or overlooked behavior of JavaScript. If a developer doesn't understand hoisting, programs may contain bugs. To avoid this, always declare all variables at the beginning of every scope.

## Explain what is the JavaScript event loop and how does it work

To be added soon.

[Go back](https://github.com/guillermo-segura/tech-interview-questions)
