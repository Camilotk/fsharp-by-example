---
title: "Modules"
date: 2023-01-27T11:52:56-03:00
draft: false
weight: 13
---

Modules are a way to organize and group related functions and values in F#. They are similar to namespaces in other languages, but with some key differences.

# Modules in F#
```fsharp
// Lesson: What is a Module in F#

// Introduction to Modules
// In F#, a module is a fundamental unit of code that can contain type declarations, function definitions, and value definitions.
// Modules provide a way to organize and structure code into logical units, making it easier to maintain and reuse code.
// Additionally, modules can help encapsulate and hide implementation details, enabling easier changes to the implementation without affecting the rest of the code.

// Using Modules
// To create a module in F#, use the keyword "module" followed by the name of the module.

module MyModule

// You can then define types, functions, and values within the module. For example:

module MathFunctions
    let add x y = x + y
    let subtract x y = x - y

// In this example, we have created a module named “MathFunctions” that contains two functions, “add” and “subtract”.
// To access these functions from other parts of the code, you use the module name followed by the function name.

// Explanation:
// In this lesson, we explored modules in F#. Modules provide a way to organize code and create logical units, enhancing code maintainability and reusability.
// Modules can contain type declarations, function definitions, and value definitions. To create a module, use the "module" keyword followed by the module name.
// Inside the module, you can define various components such as functions, types, and values.

// Interactive Exploration for Modules:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with modules interactively in the REPL.

// Interactive Example: Using the 'MathFunctions' Module
// Let's create the 'MathFunctions' module and define the 'add' and 'subtract' functions within it.

module MathFunctions
    let add x y = x + y
    let subtract x y = x - y

// To use the 'add' and 'subtract' functions from the 'MathFunctions' module, you can do the following in the F# REPL:

// 1. Load the 'modules.fsx' file to import the 'MathFunctions' module
#load "modules.fsx";;

// 2. Access the 'add' function from the 'MathFunctions' module
let result1 = MathFunctions.add 2 3

// 3. Access the 'subtract' function from the 'MathFunctions' module
let result2 = MathFunctions.subtract 5 3

// 4. Print the results
printfn "Result 1: %d" result1
printfn "Result 2: %d" result2

// The functions declared within the module are accessible and can be used as shown in the interactive example above.

// With this knowledge, you can now leverage modules in F# to create well-organized and reusable code units.
```
⬇️ [modules.fsx](#)
```
$ dotnet fsi

> #load "modules.fsx";;
> open Modules;;
> let result1 = MathFunctions.add 2 3;;
val result1 : int = 5

> let result2 = MathFunctions.subtract 5 3;;
val result2 : int = 2

> printfn "Result 1: %d" result1;;
Result 1: 5
val it : unit = ()

> printfn "Result 2: %d" result2;;
Result 2: 2
val it : unit = ()
```

