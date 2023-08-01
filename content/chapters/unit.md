---
title: "Unit"
date: 2023-02-02T19:36:07-03:00
draft: false
weight: 16
---

F# is a functional programming language that is commonly used for developing applications in a wide range of domains. One of the core concepts in F# is the concept of a unit type, which is represented by the type `unit`.

# Unit

```fsharp
// The Unit Type in F#

let myUnit : unit = ()

// It's important to note that the `unit` type only has one possible value, which is `()`.
// Declaring a variable of type `unit` is not very useful in practice, but this code demonstrates how to do it.

// The `unit` type is a special type in F# that represents the absence of a value. 
// It is used to indicate that a function returns no meaningful value and is typically used in functional programming 
// when the purpose of a function is to perform some action, such as printing a message to the console, rather than to return a value.

// The `unit` type is a singleton type, which means that there is only one instance of it. 
// This instance is represented by the value `()`, and it is used to indicate that a function has completed its work 
// and has no meaningful return value.

let printMessage message = 
    printfn "%s" message
    ()

// This will print the message "Hello, World!" to the console and return unit
printMessage "Hello, World!"

// In F#, functions that return `unit` are often referred to as "procedures." 
// Procedures are functions that perform some action and return `unit` as a result. 
// They are used to implement side effects, such as printing a message to the console, 
// and are typically used in combination with other functions that return meaningful values.

// One important thing to note about the `unit` type is that it is not equivalent to `void` in C# or other programming languages. 
// In C#, void represents the absence of a return value, but in F#, `unit` is a value type with a single instance, `()`.

// The `unit` type is particularly useful in functional programming, as it allows developers to write code that is free of side effects 
// and is easy to reason about. For example, if a function returns `unit`, it can be guaranteed that the function has no side effects, 
// and that it only performs the actions that it is intended to perform.
```
⬇️ [unit_type_example.fsx](#)
```
$ dotnet fsi

> #load "unit_type_example.fsx";;
> open Unit_type_example;;

> myUnit;;
val it : unit = ()

> printMessage "Hello, World!";;
Hello, World!
val it : unit = ()
```