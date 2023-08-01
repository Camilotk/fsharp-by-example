---
title: "Namespaces"
date: 2023-01-27T11:52:52-03:00
weight: 11
---

In F#, a namespace is a container for types, values, and modules. It is used to organize and group related items together, and to prevent naming collisions between items with the same name.

F# uses a hierarchical naming system, where namespaces are separated by dots. For example, the `System` namespace contains the `Console` module, which in turn contains the `WriteLine` function. To access the `WriteLine` function, we would use the fully-qualified name `System.Console.WriteLine`.

```fsharp
// Example call to System.Console.WriteLine
let printString (input: string) (case: string) =
    match case with
    | "upper" -> System.Console.WriteLine(input.ToUpper())
    | "lower" -> System.Console.WriteLine(input.ToLower())
    | _ -> System.Console.WriteLine(input)

printString "F# by example" "upper" // Gives "F# BY EXAMPLE"
```

## Namespaces in F#
```fsharp
// Lesson: Creating a Namespace in F#

// Introduction to Namespaces
// In F#, a namespace is a container that holds a collection of related code elements, such as values, functions, and types.
// Namespaces are used to organize code, avoid naming collisions, and improve code readability and maintainability.

// Creating a Namespace
// The declaration of a namespace consists of the keyword `namespace` followed by the identifier of the namespace.
// Everything that is below the namespace declaration will be part of it until a new namespace declaration is reached or the end of the file is reached.

namespace MyNamespace

let myValue = 42

let myFunction x = x + 1

// Explanation:
// In this lesson, we learned about namespaces in F#. Namespaces provide a way to organize code and avoid naming collisions,
// leading to more readable and maintainable code. A namespace declaration is introduced using the `namespace` keyword followed by the identifier.

// Interactive Exploration for Namespaces:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with namespaces interactively in the REPL.

// Interactive Example 1: Using the 'MyNamespace' namespace
// Let's declare the 'MyNamespace' namespace and define some values and functions within it.

namespace MyNamespace

let myValue = 42

let myFunction x = x + 1

// To use the values and functions defined in the namespace, you can do the following in the F# REPL:

// 1. Load the 'namespace.fsx' file to import the 'MyNamespace' namespace
#load "namespace.fsx";;

// 2. Access the 'myValue' from the 'MyNamespace' namespace
let result1 = MyNamespace.myValue

// 3. Call the 'myFunction' from the 'MyNamespace' namespace
let result2 = MyNamespace.myFunction 5

// 4. Print the results
printfn "Result 1: %d" result1
printfn "Result 2: %d" result2

// The values and functions declared within the namespace are accessible and can be used as shown in the interactive examples above.

// Interactive Example 2: Avoiding Naming Collisions
// Namespaces are useful for avoiding naming collisions, especially when working on larger projects with multiple modules.

// Let's define another namespace called 'AnotherNamespace' with its own 'myValue' and 'myFunction':

namespace AnotherNamespace

let myValue = 100

let myFunction x = x * 2

// Now, we can differentiate between 'myValue' and 'myFunction' from different namespaces:

// 1. Load the 'namespace.fsx' file to import the 'AnotherNamespace' namespace
#load "namespace.fsx";;

// 2. Access the 'myValue' from 'AnotherNamespace'
let result3 = AnotherNamespace.myValue

// 3. Call the 'myFunction' from 'AnotherNamespace'
let result4 = AnotherNamespace.myFunction 5

// 4. Print the results
printfn "Result 3: %d" result3
printfn "Result 4: %d" result4

// By using namespaces, we can keep code organized and avoid conflicts between identifiers with the same name.

// With this knowledge, you can now utilize namespaces in F# to create modular and well-organized code!
```
⬇️ [namespace.fsx](#)
```
$ dotnet fsi

> #load "namespace.fsx";;
> open Namespace;;
> let result1 = MyNamespace.myValue;;
val result1 : int = 42

> let result2 = MyNamespace.myFunction 5;;
val result2 : int = 6

> printfn "Result 1: %d" result1;;
Result 1: 42
val it : unit = ()

> printfn "Result 2: %d" result2;;
Result 2: 6
val it : unit = ()

> let result3 = AnotherNamespace.myValue;;
val result3 : int = 100

> let result4 = AnotherNamespace.myFunction 5;;
val result4 : int = 10

> printfn "Result 3: %d" result3;;
Result 3: 100
val it : unit = ()

> printfn "Result 4: %d" result4;;
Result 4: 10
val it : unit = ()
```
