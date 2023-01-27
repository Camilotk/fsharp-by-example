---
title: "Lambda Functions"
date: 2023-01-22T22:05:50-03:00
draft: false
weight: 5
---

In F#, lambda functions - or if you prefer, anonymous functions - are defined using the `fun` keyword. These functions are useful for creating small, one-time-use functions that don't need to be named. They can be passed as arguments to other functions, and can be used to create higher-order functions.

## How to create lambda functions

A lambda function is a special type of anonymous function that can be used to create higher-order functions. Lambda functions are defined using the "fun" keyword, followed by input parameters and the "->" operator, which separates the inputs from the function body.

Here's an example of a lambda function that takes two integers as input and returns their product:

```fsharp
let multiplyTwoNumbers = (fun x y -> x * y)
```

This function can be used like any other function, for example:

```fsharp
let result = multiplyTwoNumbers 2 3
```

## Currying

Currying is a technique in functional programming where a function is transformed into a sequence of functions, each taking a single argument. In F#, currying is done automatically when a function takes multiple arguments.

Here's an example of currying in F#:
```fsharp
let addTwoNumbers x y = x + y
let addTwoNumbersCurried = addTwoNumbers
let result = addTwoNumbersCurried 2 3
```

In this example, the `addTwoNumbers` function is transformed into a curried function `addTwoNumbersCurried`.

## Partial functions

Partial functions are functions that are applied to only a subset of their input arguments. In F#, partial functions are created using the "partial" keyword.

Here's an example of a partial function that takes two integers as input and returns their sum:

```fsharp
let addTwoNumbers x y = x + y
let addTwoNumbersCurried = addTwoNumbers
let result = addTwoNumbersCurried 2 3
```

In this example, the addTwoNumbersPartial function is a partial function that is applied to only one of its input arguments, in this case the argument 2, this function can be used like any other function, for example:

```fsharp
let result = addTwoNumbersPartial 3
```