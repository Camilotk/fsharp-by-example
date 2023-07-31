---
title: "Boolean Operators"
date: 2023-02-02T19:36:31-03:00
draft: false
weight: 18
---

Boolean operators are used to perform logical operations on Boolean values (i.e., true and false). F# provides several boolean operators that can be used to test conditions, compare values, and perform other types of operations. In this chapter, we will discuss the different boolean operators in F# and how to use them in your code.

## Boolean Operators
```fsharp
// Logical AND, OR, and NOT Operators

// AND
let x = 5
let y = 6

if x < 10 && y > 5 then
    printfn "Both conditions are true"
else
    printfn "Either condition is false"

// OR
if x < 10 || y > 10 then
    printfn "Either condition is true"
else
    printfn "Both conditions are false"

// NOT
if not (x > 10) then
    printfn "The condition is false"
else
    printfn "The condition is true"
```
⬇️ [logical_operators_example.fsx](#)
```
$ dotnet fsi
> #load "logical_operators_example.fsx";;
> // The code from the file is now imported and executed in the FSI session

> // You can see the results of the expressions:
> Both conditions are true
> Either condition is true
> The condition is false
```