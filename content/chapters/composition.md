---
title: "Composition"
date: 2023-01-22T22:06:09-03:00
weight: 9
---

Function composition is the process of combining two or more functions to create a new function. 

## Composition operator

In F#, we can use the `>>` operator to compose functions. The `>>` operator takes the output of the left-hand function and uses it as the input for the right-hand function.

For example, let's say we have two functions, `f` and `g`, that take an integer as input and return an integer as output. We can create a new function, `h`, that is the composition of `f` and `g` by using the `>>` operator:

```fsharp
let h = f >> g
```

`h` will take an integer as input and return the output of `f` when given the output of `g` as input. This can be written as:

```fsharp
let h x = g(f x)
```

A simple example of function composition in F# is composing the delta function to a quadratic function:


```fsharp
let quadratic a b c x = a * x * x + b * x + c
let delta x = x * x
let composed = quadratic 2 3 4 >> delta
printfn "Result: %i" (composed 4)
```

In this example, the `delta` function is being composed with the `quadratic` function using the `>>` operator, which is the forward function composition operator. The `quadratic` function is being called with the arguments 2, 3, and 4, and then the result of that function is being passed as the input to the `delta` function. The final result is being stored in the `composed` composed function and called with value 4 to be printed to the console.

## Backward composition

This operator (<<) is used to compose functions from right to left. It takes the output of the function on the right side and uses it as the input for the function on the left side. For example, the following code composes the same two functions as before, but in reverse order:

```fsharp
let evens numbers = numbers |> List.filter (not << fun n -> n % 2 = 0)

evens [2; 3; 5; 6; 9; 12] // Result is [3; 5; 9]
```

Function composition is a fundamental concept in functional programming, and it is a key feature of F#. By using function composition, you can create complex logic using simple, reusable functions. This makes your code more maintainable and easier to understand.
