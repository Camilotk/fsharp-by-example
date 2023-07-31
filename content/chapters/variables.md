---
title: "Variables"
date: 2023-01-22T12:22:06-03:00
draft: false
weight: 3
---

In this first part we will be discussing how to create, set, and use variables in F#. Variables are a fundamental concept in programming and are used to store and manipulate data. In F#, variables are immutable by default, which means that their value cannot be modified once they are set. This makes F# a functional programming language and it helps to improve the program's performance and predictability.

## Creating variables

```fsharp
// Lesson: Creating and Setting Variables in F#

// In this lesson, we will learn how to create, set, and use variables in F#.
// Variables are used to store and manipulate data and are fundamental in programming.

// Creating Variables
// In F#, variables are created using the 'let' keyword with the following syntax:
let variable_name = value

// For example, to create a variable called "x" and set its value to 5:
let x = 5

// You can also explicitly specify the type of the variable using the ":" operator:
let x : int = 5

// Setting Variables
// To set a variable's value, use the 'let' keyword followed by the variable name, an equal sign (=),
// and the value to be assigned:
let x = 5

// Once a variable is set, its value cannot be directly modified because F# variables are immutable by default.

// Explanation:
// In this lesson, we introduced the concept of variables in F#. We saw how to create and set variables using the 'let' keyword.
// We also learned that F# variables are immutable by default, meaning their values cannot be changed after being set.
// This feature makes F# a functional programming language, contributing to improved program performance and predictability.

// Interactive Exploration:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with creating and setting variables interactively in the REPL.
```
⬇️ [variables.fsx](#)

```
$ dotnet fsi

> #load "variables.fsx";;
> x;;
val it: int = 5
> let y = 7;;
val y: int = 7
> x <- 10;;
error FS0027: This value is not mutable. Consider using the mutable keyword, e.g. 'let mutable x = 10'.
```
