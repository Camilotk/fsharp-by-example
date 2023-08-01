---
title: "Lambda Functions"
date: 2023-01-22T22:05:50-03:00
draft: false
weight: 6
---

In F#, lambda functions - or if you prefer, anonymous functions - are defined using the `fun` keyword. These functions are useful for creating small, one-time-use functions that don't need to be named. They can be passed as arguments to other functions, and can be used to create higher-order functions.

## Lambda Functions, Currying, and Partial Functions

```fsharp
// Lesson: Lambda Functions, Currying, and Partial Functions in F#

// How to Create Lambda Functions
// A lambda function is a special type of anonymous function that can be used to create higher-order functions.
// Lambda functions are defined using the "fun" keyword, followed by input parameters and the "->" operator, which separates the inputs from the function body.

// Here's an example of a lambda function that takes two integers as input and returns their product:

let multiplyTwoNumbers = (fun x y -> x * y)

// This function can be used like any other function, for example:

let result = multiplyTwoNumbers 2 3

// Explanation:
// In this lesson, we will learn how to create lambda functions in F#. Lambda functions are anonymous functions defined using the "fun" keyword,
// and they can be used to create higher-order functions.

// Interactive Exploration for Lambda Functions:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with lambda functions interactively in the REPL.

// Interactive Example 1: Using the 'multiplyTwoNumbers' lambda function
// > let multiplyTwoNumbers = (fun x y -> x * y);;
// > multiplyTwoNumbers 2 3;;
// Output: val it: int = 6


// Currying
// Currying is a technique in functional programming where a function is transformed into a sequence of functions,
// each taking a single argument. In F#, currying is done automatically when a function takes multiple arguments.

// Here's an example of currying in F#:

let addTwoNumbers x y = x + y
let addTwoNumbersCurried = addTwoNumbers

// Explanation:
// We explored currying in F#. Currying is the automatic transformation of a function that takes multiple arguments into a sequence of functions,
// each taking a single argument.

// Interactive Exploration for Currying:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with currying interactively in the REPL.

// Interactive Example 2: Using the curried 'addTwoNumbersCurried' function
// > let addTwoNumbersCurried = addTwoNumbers;;
// > addTwoNumbersCurried 2 3;;
// Output: val it: int = 5


// Partial Functions
// Partial functions are functions that are applied to only a subset of their input arguments. In F#, partial functions are created using the "partial" keyword.

// Here's an example of a partial function that takes two integers as input and returns their sum:

let addTwoNumbersPartial = (fun x y -> x + y)

// Explanation:
// We learned about partial functions in F#. Partial functions are functions that are applied to only a subset of their input arguments,
// and they can be created using the "partial" keyword.

// Interactive Exploration for Partial Functions:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with partial functions interactively in the REPL.

// Interactive Example 3: Using the 'addTwoNumbersPartial' partial function
// > let addTwoNumbersPartial = (fun x y -> x + y);;
// > addTwoNumbersPartial 3;;
// Output: val it: int = 3
```
⬇️ [lambda.fsx](#)
```
$ dotnet fsi

> #load "lambda.fsx";;
> open Lambda;;
> let multiplyTwoNumbers = (fun x y -> x * y);;
> multiplyTwoNumbers 2 3;;
val it: int = 6

> let addTwoNumbersCurried = addTwoNumbers;;
> addTwoNumbersCurried 2 3;;
val it: int = 5

> let addTwoNumbersPartial = (fun x y -> x + y);;
> addTwoNumbersPartial 3;;
val it: int = 3
```