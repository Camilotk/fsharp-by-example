---
title: "Strings"
date: 2023-02-02T19:36:40-03:00
draft: false
weight: 19
---

In F#, a string is a sequence of Unicode characters enclosed in double quotes. Strings are often used to store and manipulate text data, such as names, addresses, and messages.

## String Literal

A string literal is a string that is directly specified in the source code. String literals can be defined by enclosing the text in double quotes:

```fsharp
let name = "John Doe"
```

## String Interpolation

String interpolation is a feature in F# that allows you to embed expressions within a string literal. The expression is enclosed in curly braces {} and is evaluated at runtime:

```fsharp
let name = "Don Syme"
let age = 51
printfn $"Name: {name}, Age: {age}"

// Output: Name: Don Syme, Age: 51
```

Interpolated strings can also have F# format specifiers to enforce type safety:

```fsharp
let name = "Camilo de Azevedo"
let age = 27

printfn $"Name: %s{name}, Age: %d{age}"
// Output: Name: Camilo de Azevedo, Age: 27

printfn $"Name: %s{age}, Age: %d{name}"
// Output: Error, type mismatch
```
