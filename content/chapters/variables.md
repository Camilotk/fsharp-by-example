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