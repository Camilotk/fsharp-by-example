---
title: "Pattern Matching with Option"
date: 2023-05-27T19:08:40-03:00
weight: 42
---

Pattern matching is a fundamental technique in F# to handle `Option` values. It allows us to determine whether a value is present or absent and to destructure the value when it is present. Pattern matching helps us handle both `Some` and `None` cases effectively.

Let's take an example:
```Fsharp
let divide a b =
    if b = 0 then None
    else Some (a / b)
```
This will work as:
```Fsharp
let result1 = divide 5 6 // => int option = Some 0
let result2 = divide 5 0 // => int option = None
```
This is an example of how it can be convenient to handle errors. Usually `5 / 0` would return a `System.DivideByZeroException` but with **Option** we can handle it without an exception.

Then, for we extract the value from the result we can also use Pattern Matching:
```Fsharp
match result1 with
| None -> printfn "Division failed"
| Some x -> printfn "Result = %d" x

// prints: "Result = 0"
```
This is how we usually handle to extract values from `Some` to work with them in our code. 

We can use it to generalize it in a function:
```Fsharp
let printResult option =
    match option with
    | None -> printfn "Division failed"
    | Some x -> printfn "Result = %d" x
```

And use it to work with both variables:
```Fsharp
printResult result1 // prints: Result = 0
printResult result2 // prints: "Division failed"
```