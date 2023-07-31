---
title: "Recursion"
date: 2023-01-22T22:05:57-03:00
draft: false
weight: 7
---

Recursion is a programming technique in which a function calls itself to solve a problem. It is a powerful tool that allows for elegant and efficient solutions to many types of problems. In this chapter, we will explore recursion in F# and how it can be used to solve problems.

## Recursion in F#
```fsharp
// Lesson: Recursion in F#

// Introduction to Recursion
// Recursion is a fundamental concept in programming, and it allows a function to call itself during its execution.
// Recursive functions are useful for solving problems that can be broken down into smaller, similar subproblems.

// Factorial Function
// For example, the `factorial` function below calculates the factorial of a given number and is recursive.
// It uses the keyword `rec` to indicate to the F# compiler that this function is recursive and optimizations are necessary for this case.
// Additionally, the function calls itself with a modified argument in the recursive case.

let rec factorial n =
    if n = 0 then 1
    else n * factorial (n - 1)

// Fibonacci Sequence Generator
// Another example of recursion in F# is the implementation of a Fibonacci sequence generator.
// The function `fib` takes a single argument `n` and uses an if/else statement to determine if the base case of the recursion has been reached.
// If `n` is less than or equal to 2, the function returns 1.
// If `n` is greater than 2, the function calls itself twice with the arguments `n - 1` and `n - 2`, and adds the results together.

let rec fib n =
    if n <= 2 then 1
    else fib (n - 1) + fib (n - 2)

// Explanation:
// In this lesson, we explored recursion in F#. Recursion allows a function to call itself during its execution and is useful for solving problems
// that can be broken down into smaller, similar subproblems.

// Interactive Exploration for Recursion:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with recursion interactively in the REPL.

// Interactive Example 1: Using the 'factorial' function
// > let rec factorial n =
//     if n = 0 then 1
//     else n * factorial (n - 1);;
// > factorial 5;;
// Output: val it: int = 120

// Interactive Example 2: Using the 'fib' function
// > let rec fib n =
//     if n <= 2 then 1
//     else fib (n - 1) + fib (n - 2);;
// > fib 6;;
// Output: val it: int = 8
```
⬇️ [recursion.fsx](#)
```
$ dotnet fsi

> #load "recursion.fsx";;
> let rec factorial n =
    if n = 0 then 1
    else n * factorial (n - 1);;
> factorial 5;;
val it: int = 120

> let rec fib n =
    if n <= 2 then 1
    else fib (n - 1) + fib (n - 2);;
> fib 6;;
val it: int = 8
```