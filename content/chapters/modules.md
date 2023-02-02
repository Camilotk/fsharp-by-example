---
title: "Modules"
date: 2023-01-27T11:52:56-03:00
draft: false
weight: 13
---

Modules are a way to organize and group related functions and values in F#. They are similar to namespaces in other languages, but with some key differences.

## What is a module?

A module in F# is a unit of code that can contain type declarations, function definitions, and value definitions. It provides a way to organize and structure your code into logical units, making it easier to maintain and reuse your code. Modules can also help to encapsulate and hide implementation details, making it easier to change the implementation without affecting the rest of the code.

## Using modules

To create a module in F#, use the keyword "module" followed by the name of the module. For example:

```fsharp
module MyModule
```
You can then define your types, functions, and values within the module. For example, consider the following code snippet:

```fsharp
module MathFunctions
    let add x y = x + y
    let subtract x y = x - y
```

In this example, we have created a module named “MathFunctions” that contains two functions, “add” and “subtract”. You can then access these functions from other parts of your code by using the module name followed by the function name.

```fsharp
let result = MathFunctions.add 2 3
```



