---
title: "Composition"
date: 2023-01-22T22:06:09-03:00
weight: 9
---

Function composition is the process of combining two or more functions to create a new function. 

## Composition operator

```fsharp
// Lesson: Composition Operator in F#

// Introduction to Composition Operator
// In F#, we can use the `>>` operator to compose functions. The `>>` operator takes the output of the left-hand function
// and uses it as the input for the right-hand function.

// Function Composition Example
// For example, let's say we have two functions, `f` and `g`, that take an integer as input and return an integer as output.
// We can create a new function, `h`, that is the composition of `f` and `g` by using the `>>` operator:

let f x = x + 1
let g x = x * 2

let h = f >> g

// Explanation:
// In this lesson, we will learn how to use the composition operator `>>` in F# to create new functions by composing existing functions.
// The composition operator allows us to chain functions together, with the output of the left-hand function becoming the input of the right-hand function.

// Interactive Exploration for Function Composition:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with function composition interactively in the REPL.

// Interactive Example 1: Composing functions `f` and `g` into `h`
// > let f x = x + 1;;
// > let g x = x * 2;;
// > let h = f >> g;;
// > h 3;;
// Output: val it: int = 8


// Backward Composition Operator (<<)
// The backward composition operator `<<` is used to compose functions from right to left.
// It takes the output of the function on the right side and uses it as the input for the function on the left side.

// Backward Composition Example
// For example, the following code composes the same two functions as before but in reverse order:

let evens numbers = numbers |> List.filter (not << fun n -> n % 2 = 0)

// Explanation:
// We also learned about the backward composition operator `<<`, which composes functions from right to left.
// This operator allows us to chain functions in the reverse order, with the output of the right-hand function becoming the input of the left-hand function.

// Interactive Exploration for Backward Composition:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with backward function composition interactively in the REPL.

// Interactive Example 2: Using the backward composition operator to compose `not` and a lambda function
// > let evens numbers = numbers |> List.filter (not << fun n -> n % 2 = 0);;
// > evens [2; 3; 5; 6; 9; 12];;
// Output: val it: int list = [3; 5; 9]
```
⬇️ [composition.fsx](#)
```
$ dotnet fsi

> #load "composition.fsx";;
> let f x = x + 1;;
> let g x = x * 2;;
> let h = f >> g;;
> h 3;;
val it: int = 8

> let evens numbers = numbers |> List.filter (not << fun n -> n % 2 = 0);;
> evens [2; 3; 5; 6; 9; 12];;
val it: int list = [3; 5; 9]
```