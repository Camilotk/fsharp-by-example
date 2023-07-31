---
title: "Nested Namespaces"
date: 2023-01-27T13:23:31-03:00
weight: 12
---

In F#, it is possible to organize code within namespaces in a hierarchical manner by using nested namespaces. A nested namespace is a namespace that is defined within another namespace.

# Nested Namespace in F#

```fsharp
// Lesson: Nested Namespace in F#

// Introduction to Nested Namespaces
// In F#, a nested namespace is a namespace declared within another namespace.
// Nested namespaces provide a hierarchical structure to organize and manage code more effectively.

// Declaring Nested Namespaces
// To declare a nested namespace, use the `namespace` keyword followed by the identifier of the parent namespace.
// Then, define the nested namespace using the `namespace` keyword followed by the identifier of the nested namespace.

namespace ParentNamespace
    namespace ChildNamespace
        // Code here belongs to ChildNamespace
    namespace AnotherChildNamespace
        // Code here belongs to AnotherChildNamespace

// Explanation:
// In this lesson, we'll explore nested namespaces in F#. Nested namespaces provide a way to create a hierarchical organization of code.
// A nested namespace is declared within another namespace, resulting in a structured way to manage code components.

// Interactive Exploration for Nested Namespaces:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.

// Now, you can experiment with nested namespaces interactively in the REPL.

// Interactive Example 1: Using the 'ParentNamespace.ChildNamespace' Namespace
// Let's declare the 'ParentNamespace.ChildNamespace' namespace and define a value and a function within it.

namespace ParentNamespace
    namespace ChildNamespace
        let childValue = 42

        let childFunction x = x + 1

// To use the value and function defined in the nested namespace, you can do the following in the F# REPL:

// 1. Load the 'nested_namespace.fsx' file to import the 'ParentNamespace.ChildNamespace' namespace
#load "nested_namespace.fsx";;

// 2. Access the 'childValue' from the 'ParentNamespace.ChildNamespace' namespace
let result1 = ParentNamespace.ChildNamespace.childValue

// 3. Call the 'childFunction' from the 'ParentNamespace.ChildNamespace' namespace
let result2 = ParentNamespace.ChildNamespace.childFunction 5

// 4. Print the results
printfn "Result 1: %d" result1
printfn "Result 2: %d" result2

// The value and function declared within the nested namespace are accessible and can be used as shown in the interactive examples above.

// Interactive Example 2: Avoiding Naming Collisions with Multiple Nested Namespaces
// Nested namespaces help avoid naming collisions, especially when working on larger projects with multiple modules.

// Let's define another nested namespace called 'ParentNamespace.AnotherChildNamespace' with its own 'childValue' and 'childFunction':

namespace ParentNamespace
    namespace AnotherChildNamespace
        let anotherChildValue = 100

        let anotherChildFunction x = x * 2

// Now, we can differentiate between 'childValue' and 'childFunction' from different nested namespaces:

// 1. Load the 'nested_namespace.fsx' file to import the 'ParentNamespace.AnotherChildNamespace' namespace
#load "nested_namespace.fsx";;

// 2. Access the 'anotherChildValue' from 'ParentNamespace.AnotherChildNamespace'
let result3 = ParentNamespace.AnotherChildNamespace.anotherChildValue

// 3. Call the 'anotherChildFunction' from 'ParentNamespace.AnotherChildNamespace'
let result4 = ParentNamespace.AnotherChildNamespace.anotherChildFunction 5

// 4. Print the results
printfn "Result 3: %d" result3
printfn "Result 4: %d" result4

// By using nested namespaces, we can keep code organized and avoid conflicts between identifiers with the same name.

// With this knowledge, you can now utilize nested namespaces in F# to create a more structured and well-organized codebase.
```
⬇️ [nested_namespace.fsx](#)
```
$ dotnet fsi

> #load "nested_namespace.fsx";;
> let result1 = ParentNamespace.ChildNamespace.childValue;;
val result1 : int = 42

> let result2 = ParentNamespace.ChildNamespace.childFunction 5;;
val result2 : int = 6

> printfn "Result 1: %d" result1;;
Result 1: 42
val it : unit = ()

> printfn "Result 2: %d" result2;;
Result 2: 6
val it : unit = ()

> let result3 = ParentNamespace.AnotherChildNamespace.anotherChildValue;;
val result3 : int = 100

> let result4 = ParentNamespace.AnotherChildNamespace.anotherChildFunction 5;;
val result4 : int = 10

> printfn "Result 3: %d" result3;;
Result 3: 100
val it : unit = ()

> printfn "Result 4: %d" result4;;
Result 4: 10
val it : unit = ()
```