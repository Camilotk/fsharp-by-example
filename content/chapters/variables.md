---
title: "Variables"
date: 2023-01-22T12:22:06-03:00
draft: false
weight: 3
---

In this first part we will be discussing how to create, set, and use variables in F#. Variables are a fundamental concept in programming and are used to store and manipulate data. In F#, variables are immutable by default, which means that their value cannot be modified once they are set. This makes F# a functional programming language and it helps to improve the program's performance and predictability.

## Creating variables

In F#, variables are created using the `let` keyword. The basic syntax for creating a variable is as follows:
```fsharp
let variable_name = value
```
For example, to create a variable called "x" and set its value to 5, we would use the following code:
```fsharp
let x = 5
```
You can also create a variable and define its type using the ":" operator, like this:
```fsharp
let x : int = 5
```

## Setting Variables

In F#, variables are set using the "let" keyword, followed by the variable name, an equal sign (=), and the value to be assigned to the variable. For example:

```fsharp
let x = 5
```

This creates a new variable named "x" and assigns the value of 5 to it.

Once a variable is set, its value cannot be modified directly. This is because F# variables are immutable by default, which means that their value cannot be changed once they are set.

## Immutability

In summary, immutability in F# refers to the fact that the value of a variable cannot be changed once it is set. This can help prevent a number of problems that can occur in other languages when working with mutable variables, such as concurrent access, side effects, and debugging.

- **Concurrent access**: When multiple threads have access to a mutable variable, it can lead to race conditions where different threads try to access and change the variable at the same time. With immutable variables, this problem is avoided because each thread can only access a specific version of the variable and cannot change it.
- **Side effects**: Mutable variables can lead to unintended side effects where a change in one part of the code unexpectedly affects another part of the code. With immutable variables, it is clear that the value of a variable can only be changed in one place, making it easier to reason about the code and prevent unintended side effects.
- **Debugging**: When working with mutable variables, it can be difficult to track down the cause of a bug when the value of a variable has changed unexpectedly. With immutable variables, the value of a variable can only be changed in one place, making it easier to trace the flow of data through the code and find the source of a bug.

## Shadowing

Once a variable is created, its value cannot be modified. However, you can create a new variable with the same name and a new value. 

For example, the following code creates a new variable called "x" with a value of 10:
```fsharp
let x = 10
```
The first `let x = 5` creates the variable and assigns the value of 5 to it. The second `let x = 10` creates a new variable also called x and assigns the new value of 10.

Creating new variables with the same name and new values is referred to as "shadowing" in F#.

When you create a new variable with the same name as an existing variable, the new variable "shadows" the existing variable, meaning that it takes precedence and can be used instead of the existing variable. However, the existing variable is still accessible and can be used if needed.

It's important to note that shadowing can make the code more difficult to understand and maintain, as it can be unclear which variable is being referred to at a given point in the code. Therefore, it's generally recommended to use meaningful variable names and to avoid shadowing whenever possible.

## Declaring mutable values

However, there may be situations where you need to work with mutable variables, for example when you need to change the value of a field in a record or when you need to update the state of an object.

To create a mutable variable in F#, you can use the mutable keyword before the variable's name. For example:

```fsharp
let mutable x = 5
x <- 10 // x value change to 10
```

While there may be situations where you need to work with mutable variables in F#, it's important to be aware of the risks and potential problems that can arise from doing so. In general, it's a good idea to use immutable variables as much as possible and to use mutable variables only when necessary.