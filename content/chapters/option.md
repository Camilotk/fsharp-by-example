---
title: "Option"
date: 2023-05-27T18:43:20-03:00
weight: 41
---

In functional programming, handling optional values and potential absence of data is a common scenario. F#, a functional-first programming language, provides a powerful type called Option to address this need.

Imagine that you have created a function that searches for a user in the database, and there are only two possible outcomes:
1. The user was found.
2. The user was not found.
If the result of our function needs to be fully included in the return type of the function, then we need a type that represents this optional value.

In F#, this type is called Option, for create an Option Type:
- Use `Some` constructor with some value;
- Use `None` constructor.

For example we will create **firstOdd** function that takes a list of integers **xs** - a list of integers - as input and returns the `Option` containing: 
- `Some` containing first odd number found in the list. 
- If no odd number is found, it returns `None`.
```Fsharp
let firstOdd xs =
    List.tryPick (fun x -> if x % 2 = 1 then Some x else None) xs
```
This will works as:
```FSharp
firstOdd [2;4;6]     // will return => int option = None
firstOdd [2;4;5;6;7] // will return => int option = Some 5
```
Note that Option is the generic `'a option` that was infered as `int option`.


