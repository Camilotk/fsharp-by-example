---
title: "Pattern Matching with Option"
date: 2023-05-27T19:08:40-03:00
weight: 42
---

Pattern matching is a fundamental technique in F# to handle `Option` values. It allows us to determine whether a value is present or absent and to destructure the value when it is present. Pattern matching helps us handle both `Some` and `None` cases effectively.

Let's take an example:
```Fsharp
let divide x y =
    if y <> 0 then
        Some (x / y)
    else
        None
```
This will work as:
```Fsharp
divide 5 6 // will return => int option = Some 0
divide 5 0 // will return => int option = None
```
This is an example of how it can be convenient to handle errors. Usually `5 / 0` would return a `System.DivideByZeroException` but with **Option** we can handle it without an exception.

