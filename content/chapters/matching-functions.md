---
title: "Pattern Matching Functions "
date: 2023-03-18T17:50:11-03:00
weight: 30
---

Pattern matching functions are an alternative way of writing match expressions in F#. With this syntax, instead of using the `match...with` structure, you can create a function that takes a value and pattern matches on it using the `function` keyword.

For example, let's say we want to create a function that prints the value of an integer option. We could write it using the pattern-matching function syntax like this:

```FSharp
let isPositive = function
    | x when x > 0 -> printfn "The number %i is positive" x
    | 0 -> printfn "The number is zero"
    | _ -> printfn "The number is negative"
```

In this example, we define a function called `isPositive` that takes one argument. Instead of explicitly defining the argument, we use the `function` keyword to indicate that we are defining a pattern-matching function. We then define three patterns that are matched against the input value: one for positive numbers, one for zero, and one for negative numbers.

We can then call this function with different inputs to see the different results:

```FSharp
isPositive 10
// Output: The number 10 is positive

isPositive 0
// Output: The number is zero

isPositive (-5)
// Output: The number is negative
```

The advantage of using pattern-matching functions is that they are more concise than regular functions that use match expressions. They also allow you to pass them as arguments to higher-order functions, as shown in the previous examples.