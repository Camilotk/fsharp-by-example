---
title: "Pattern Matching"
date: 2023-03-18T16:53:06-03:00
weight: 33
---

Pattern matching is a powerful feature in functional programming languages that allows you to match a value or data structure against a set of patterns and execute the corresponding code block based on the match. It is a declarative and expressive way of branching code based on data values, and it can be used to simplify complex conditional logic.

In F#, pattern matching is a first-class citizen, which means it is deeply integrated into the language syntax and semantics. F# provides a rich set of pattern matching constructs, such as matching on values, tuples, lists, arrays, discriminated unions, and more.

## Matching Values

Matching on values is the simplest form of pattern matching, and it involves matching a single value against one or more patterns. Let's say we want to write a function that takes an integer and returns a string representing the parity of the number (even or odd). We can use pattern matching to achieve this as follows:

```FSharp
let parity x =
    match x % 2 with
    | 0 -> "even"
    | _ -> "odd"
```

In this example, we define a function `parity` that takes an integer x. We then use pattern matching to match the result of `x % 2` against two patterns: `0` and `_`. The first pattern matches `x % 2` when it is equal to `0`, and the second pattern is a wildcard pattern that matches any other value.

## Guard Clauses

In addition to matching values against patterns, F# allows us to further refine each case through guard clauses. Guard clauses let us specify additional criteria that must be met to satisfy a case. These criteria can be expressed as Boolean expressions that are checked after a successful match of the pattern.

To illustrate, consider the following example, which uses guard clauses to distinguish between positive and negative numbers:

```FSharp
let testNumber value =
    match value with
    | v when v < 0 -> printfn "%i is negative" v
    | v when v > 0 -> printfn "%i is positive" v
    | _ -> printfn "zero"
```

In this example, we have two cases with identical patterns, but different guard clauses. Even though any integer will match any of the three patterns, the guard clauses on patterns `v < 0` and `v > 0` cause the matching to fail unless the captured value meets their criteria.

We can also combine multiple guard clauses with Boolean operators for more complex matching logic. For example, we could construct a case that matches only positive, even integers as follows:

```FSharp
let testNumber value =
    match value with
    | v when v > 0 && v % 2 = 0 -> printfn "%i is positive and even" v
    | v -> printfn "%i is zero, negative, or odd" v
```

In this example, the guard clause `v > 0 && v % 2 = 0` checks whether the value is positive and even. If the guard clause is true, the first pattern is matched, and the corresponding message is printed. Otherwise, the second pattern is matched, and the corresponding message is printed.

Guard clauses are a powerful feature of F# pattern matching that allow us to add additional conditions to our matching logic, making it more precise and expressive.