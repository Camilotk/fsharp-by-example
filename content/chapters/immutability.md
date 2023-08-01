---
title: "Immutability"
date: 2023-01-27T13:11:15-03:00
draft: false
weight: 4
---

In summary, immutability in F# refers to the fact that the value of a variable cannot be changed once it is set. This can help prevent a number of problems that can occur in other languages when working with mutable variables, such as concurrent access, side effects, and debugging.

- **Concurrent access**: When multiple threads have access to a mutable variable, it can lead to race conditions where different threads try to access and change the variable at the same time. With immutable variables, this problem is avoided because each thread can only access a specific version of the variable and cannot change it.
- **Side effects**: Mutable variables can lead to unintended side effects where a change in one part of the code unexpectedly affects another part of the code. With immutable variables, it is clear that the value of a variable can only be changed in one place, making it easier to reason about the code and prevent unintended side effects.
- **Debugging**: When working with mutable variables, it can be difficult to track down the cause of a bug when the value of a variable has changed unexpectedly. With immutable variables, the value of a variable can only be changed in one place, making it easier to trace the flow of data through the code and find the source of a bug.

## Shadowing and Declaring Mutable Values

```fsharp
// Lesson: Shadowing and Declaring Mutable Values in F#

// In this lesson, we will learn about shadowing and declaring mutable values in F#.

// Shadowing
// Once a variable is created, its value cannot be modified. However, you can create a new variable with the same name and a new value.
// For example, the following code creates a new variable called "x":
let x = 5

// And eventually we could have another definition as:
let x = 10

// The first `let x = 5` creates the variable and assigns the value of 5 to it.
// The second `let x = 10` creates a new variable also called x and assigns the new value of 10.
// Creating new variables with the same name and new values is referred to as "shadowing" in F#.

// Explanation:
// Shadowing allows creating a new variable with the same name and a new value, which takes precedence over the previous variable with the same name.
// While shadowing can be useful, it can also make the code more difficult to understand and maintain, so it's recommended to use meaningful variable names and avoid shadowing whenever possible.

// Interactive Exploration for Shadowing:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with shadowing interactively in the REPL.

// Interactive Example 1: Shadowing
// > x;;
// Output: val it: int = 10

// Declaring Mutable Values
// However, there may be situations where you need to work with mutable variables, for example when you need to change the value of a field in a record
// or when you need to update the state of an object.

// To create a mutable variable in F#, you can use the mutable keyword before the variable's name. For example:

let mutable y = 5
y <- 10 // y value changes to 10

// While there may be situations where you need to work with mutable variables in F#, it's important to be aware of the risks and potential problems that can arise from doing so.
// In general, it's a good idea to use immutable variables as much as possible and to use mutable variables only when necessary.

// Explanation:
// Mutable variables are created using the mutable keyword before the variable's name, allowing the value to be changed after creation.
// Using mutable variables can introduce complexity and make it harder to reason about the code, so they should be used judiciously.

// Interactive Exploration for Mutable Variables:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with declaring mutable values interactively in the REPL.

// Interactive Example 2: Declaring Mutable Values
// > y;;
// Output: val it: int = 10

// You can proceed to the next part of the lesson to learn more about control flow in F#.
```
⬇️ [shadowing.fsx](#)
```
$ dotnet fsi

> #load "shadowing.fsx";;
> open Shadowing;;
> x;;
val it: int = 10

> #load "mutable_values.fsx";;
> y;;
val it: int = 10
```