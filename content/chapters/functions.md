---
title: "Functions"
date: 2023-01-21T22:22:09-03:00
draft: false
weight: 5
---

F# is a functional programming language that allows developers to create powerful and expressive code. One of the key features of F# is its support for functions, which are used to perform specific tasks and return a value. In this chapter, we will explore the basics of functions in F# and how they can be used to create reusable and composable code.

## Defining functions in F#

```fsharp
// Lesson: Defining Functions in F#

// In F#, a function is defined using the keyword 'let' followed by the name of the function, a list of parameters,
// and the value or expression that the function will return. For example, the following code defines a simple function called "add"
// that takes two parameters, 'x' and 'y', and returns their sum:

let add x y = x + y

// In addition to defining functions in this way, F# also supports curried functions, which are functions that take multiple arguments,
// but can be called with fewer arguments and return a new function that takes the remaining arguments. For example, the following code defines
// a curried version of the 'add' function:

let add x = fun y -> x + y

// Explanation:
// In this lesson, we learned how to define functions in F#. We saw that functions are defined using the 'let' keyword,
// followed by the function name and a list of parameters. The value or expression that the function will return is specified after the equals sign.
// We also explored curried functions, which allow partial application of arguments.

// Interactive Exploration:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with defining and using functions interactively in the REPL.

// Interactive Example 1: Calling 'add' function
// > #load "functions.fsx";;
// > add 2 3;;
// Output: val it: int = 5

// Interactive Example 2: Using curried version of 'add' function
// > let add5 = add 5;;
// > add5 3;;
// Output: val it: int = 8

// Using Functions in F#
// Once a function has been defined, it can be called by providing it with the necessary arguments.
// For example, the following code calls the 'add' function with the arguments 2 and 3 and assigns the result to the variable 'result':

let result = add 2 3

// In addition to calling functions directly, F# also supports higher-order functions,
// which are functions that take other functions as arguments or return them as results.
// For example, the following code defines a function called 'map' that takes a list and a function and applies the function to each element of the list:

let map list f = List.map f list

// Explanation:
// We explored how to use functions in F#. Once a function is defined, it can be called by providing the necessary arguments.
// We also learned about higher-order functions, which can take other functions as arguments or return them as results.

// Interactive Exploration for Higher-order Functions:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with higher-order functions interactively in the REPL.

// Interactive Example 3: Using the 'map' function
// > let myList = [1; 2; 3; 4];;
// > let double x = x * 2;;
// > map myList double;;
// Output: val it: int list = [2; 4; 6; 8]

// Multiple Argument Functions
// In F#, functions can take multiple inputs. These inputs are separated by a space and are passed in as a tuple.
// For example, the following function takes in two inputs, an 'int' and a 'string', and returns a concatenation of the two:

let concatFunction (x:int) (y:string) = x.ToString() + y

// We can call this function by passing in two arguments, like so:

let result = concatFunction 5 "hello" // result is "5hello"
```
⬇️ [functions.fsx](#)
```
$ dotnet fsi

> #load "functions.fsx";;
> open Functions;;
> add 2 3;;
val it: int = 5

> let add5 = add 5;;
> add5 3;;
val it: int = 8

> let myList = [1; 2; 3; 4];;
> let double x = x * 2;;
> map myList double;;
val it: int list = [2; 4; 6; 8]
```