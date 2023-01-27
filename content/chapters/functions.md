---
title: "Functions"
date: 2023-01-21T22:22:09-03:00
draft: false
weight: 4
---

F# is a functional programming language that allows developers to create powerful and expressive code. One of the key features of F# is its support for functions, which are used to perform specific tasks and return a value. In this chapter, we will explore the basics of functions in F# and how they can be used to create reusable and composable code.

## Defining functions in F#

In F#, a function is defined using the keyword `let` followed by the name of the function, a list of parameters, and the value or expression that the function will return. For example, the following code defines a simple function called "add" that takes two parameters, `x` and `y`, and returns their sum:

```fsharp
let add x y = x + y
```

In addition to defining functions in this way, F# also supports curried functions, which are functions that take multiple arguments, but can be called with fewer arguments and return a new function that takes the remaining arguments. For example, the following code defines a curried version of the `add` function:

```fsharp
let add x = fun y -> x + y
```

## Using functions in F#

Once a function has been defined, it can be called by providing it with the necessary arguments. For example, the following code calls the `add` function with the arguments 2 and 3 and assigns the result to the variable `result`:

```fsharp
let result = add 2 3
```

In addition to calling functions directly, F# also supports higher-order functions, which are functions that take other functions as arguments or return them as results. For example, the following code defines a function called "map" that takes a list and a function and applies the function to each element of the list:

```fsharp
let map list f = List.map f list
```

## Multiple argument functions

In F#, functions can take multiple inputs. These inputs are separated by a space and are passed in as a tuple. For example, the following function takes in two inputs, an `int` and a `string`, and returns a concatenation of the two:

```fsharp
let concatFunction (x:int) (y:string) = x.ToString() + y
```

We can call this function by passing in two arguments, like so:

```fsharp
let result = concatFunction 5 "hello" // result is "5hello"
```