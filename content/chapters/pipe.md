---
title: "Pipeline operator"
date: 2023-01-22T22:06:09-03:00
weight: 10
---

F# also has pipeline operators, or pipe operators, which allow us to chain function calls together in a readable way. The pipeline operator `|>` takes the output of the expression on the left-hand side and uses it as the input for the function on the right-hand side.

# Pipes

```
// Pipeline Operator

// For example, let's say we have a function `f` that takes an integer as input and returns an integer as output.
// We can call this function and pass in the result of another expression using the pipeline operator:
let f x = x + 1

let result1 = 2 |> f // Equivalent to: f 2

// We can also chain multiple function calls together using the pipeline operator:
let g x = x * 2
let h x = x - 1

let result2 = 2 |> f |> g |> h // f 2 |> g |> h

// Backward Pipeline Operator

// This operator is used to compose functions from right to left.
// It takes the output of the function on the right side and uses it as the input for the function on the left side.
// For example, the following code composes the same two functions as before, but in reverse order:
let sin x = System.Math.Sin(x)

let result3 = sin <| 2. + 1.

// Pipeline with Multiple Arguments

// To pipe the output from a function or values to another function, it is necessary for the functions to have only one argument,
// or it will give us an error. For functions with multiple arguments, we can use the pipe operators with different numbers of pipes.
let min a b = if a < b then a else b

let result4 = (3, 7) ||> min // result is 3

let result5 = (6, 5, 2) |||> (fun x y z -> x + y * z) // result is 16

// If your function needs four or more arguments, it's a better idea to compose it in smaller parts than to use piping.
```
⬇️ [logical_operators_example.fsx](#)
```
$ dotnet fsi
> #load "pipeline_operators_example.fsx";;
> // The code from the file is now imported and executed in the FSI session

> // Result of the expressions:
> val result1 : int = 3
> val result2 : int = 3
> val result3 : float = 0.1411200081
> val result4 : int = 3
> val result5 : int = 16
```