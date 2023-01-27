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

## Creating a Namespace

The declaration of a namespace consists of the keyword `namespace` followed by the identifier of the namespace. Everything that is below the namespace declaration will be part of it until a new namespace declaration is reached or the end of the file is reached. 

For example:

```fsharp
namespace MyNamespace

let myValue = 42

let myFunction x = x + 1
```

In the example above, we have created a namespace called MyNamespace that contains a value and a function.

It is important to note that namespaces provide a way to organize code and avoid naming collisions. Additionally, they also help to keep the code more readable and maintainable. Therefore, it is considered good practice to use namespaces in your code to keep it organized and easy to understand.
