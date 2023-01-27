---
title: "Pipeline operator"
date: 2023-01-22T22:06:09-03:00
weight: 10
---

F# also has pipeline operators, or pipe operators, which allow us to chain function calls together in a readable way. The pipeline operator `|>` takes the output of the expression on the left-hand side and uses it as the input for the function on the right-hand side.

For example, let's say we have a function `f` that takes an integer as input and returns an integer as output. We can call this function and pass in the result of another expression using the pipeline operator:

```fsharp
2 |> f
```

This is equivalent to:

```fsharp
f 2
```

We can also chain multiple function calls together using the pipeline operator:

```fsharp
2 |> f |> g |> h
```

This will take the integer 2, pass it through the function `f`, take the output and pass it through the function `g`, then take the output of that and pass it through the function `h`.

## Backward pipeline

This operator is used to compose functions from right to left. It takes the output of the function on the right side and uses it as the input for the function on the left side. For example, the following code composes the same two functions as before, but in reverse order:

```fsharp
sin <| 2. + 1. // result is 0.1411200081
```

## Pipeline with multiple arguments

For to be possible pipe the output from a funtion or values to another function is necessary it have only one argument or it will give us an error:

```fsharp
3 7 |> min // Error
```

For this function we have to use the double pipe operator:
```fsharp
(3,7) ||> min // result is 3
```

If the function has three operators you have to use the triple pipe operator:
```fsharp
(6,5,2) |||> (fun x y z -> x + y * z) // result is 16
```

If your function needs four or more arguments its a better idea compose it in smaller parts to them work togheter than use piping.