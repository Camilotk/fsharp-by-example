---
title: "Recursion"
date: 2023-01-22T22:05:57-03:00
draft: false
weight: 6
---

Recursion is a programming technique in which a function calls itself to solve a problem. It is a powerful tool that allows for elegant and efficient solutions to many types of problems. In this chapter, we will explore recursion in F# and how it can be used to solve problems.

## Introduction to recursion in F#

For example, the `factorial` function below that calculates the factorial of a given number is recursive. We can first observe this by the keyword  `rec` which indicates to the F# compiler that this function is recursive and that optimizations are necessary for this case. Additionally, we can see in the third line that the function calls itself.

In this example, the function "factorial" is defined as a recursive function using the keyword `rec`:

```fsharp
let rec factorial n =
    if n = 0 then 1
    else n * factorial (n - 1)
```

When thinking about how to program a recursive function, we typically first consider the base case or exit condition. In `factorial` function it takes a single argument `n` and uses an **if/else** statement to determine if the base case of the recursion has been reached. 

If `n` value is **0**, the function returns **1**. If `n` is not **0**, the function calls itself with the argument `n - 1` and multiplies the result by `n`.

Another example of recursion in F# is the implementation of a Fibonacci sequence generator:

```fsharp
let rec fib n =
    if n <= 2 then 1
    else fib(n-1) + fib(n-2)
```
The function takes a single argument `n` and uses an **if/else** statement to determine if the base case of the recursion has been reached. If `n` is less than or equal to **2**, the function returns **1**. If `n` is greater than **2**, the function calls itself twice with the arguments `n - 1` and `n - 2` and adds the results together.

## Call and Evaluation

When a recursive function is called, it begins by evaluating the base case. If the base case is true, the function returns a value. If the base case is false, the function calls itself with a modified argument and the process repeats.

For example, consider the `factorial` function. When the function is called with an argument of 5, the first thing that happens is the if statement is evaluated. Since 5 is not equal to 0, the else branch is taken, and the function calls itself with an argument of 4. The function then calls itself with an argument of 3, 2, and 1, until the base case of 0 is reached and the function returns 1. At this point, the previously called instances of the function return their results, which are multiplied together and returned as the final answer.

In the case of `fibonacci` sequence generator, when called with an argument of 6, the function will call itself with argument of 5 and 4. Then it will call itself with argument of 4 and 3 and so on until it reach the base case of 2 and 1, then it will return 1.

## Efficiency of Recursion in F#

One of the key benefits of using recursion in F# is its optimized handling of recursive functions. Unlike languages such as C#, F# is designed with recursion in mind and includes specific optimizations to make recursive functions more efficient.

One of the main optimizations implemented in F# is tail call optimization. This optimization allows the compiler to reuse the current stack frame, rather than creating a new one for each recursive call, significantly reducing the amount of memory used and preventing stack overflow errors. This means that the performance of recursive functions in F# is much better than in languages that don't have this optimization.

Another optimization that F# has is the pattern matching feature, which allows for more precise and efficient handling of recursive cases. This feature allows the compiler to match the input of a function to a specific pattern and then execute the corresponding code. This reduces the need for explicit conditional statements and makes the code more readable.

Furthermore, F# has a built-in support for the functional programming paradigm which is a natural fit for recursion. The functional programming approach encourages the use of immutable variables and pure functions, making it easier to reason about the behavior of recursive functions, and leading to fewer bugs and more maintainable code.

The combination of tail call optimization, pattern matching, and functional programming support make F# an excellent choice for implementing recursive functions, especially when compared to languages like C# that lack these optimizations.