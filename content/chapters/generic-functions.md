---
title: "Generic Functions"
date: 2023-05-23T16:54:05-03:00
weight: 38
---

In F#, you can define generic functions that operate on different types. By using type parameters, you can create functions that are reusable across multiple data types. Let's take a look at an example:

```Fsharp
type Stack<'T> = 'T list

let push (item: 'T) (stack: Stack<'T>) : Stack<'T> =
    item :: stack

let pop (stack: Stack<'T>) : 'T option * Stack<'T> =
    match stack with
    | [] -> None, []
    | head :: tail -> Some head, tail

let emptyStack : Stack<int> = []
let numberStack : Stack<int> = emptyStack |> push 1 |> push 2 |> push 3

let poppedNumber, remainingStack = pop numberStack
match poppedNumber with
    | Some number -> printfn "Popped number: %d" number
    | None -> printfn "Stack is empty."
 ```

 In F#, the notation `'T` represents a type parameter or type variable. It is a placeholder that can be replaced with an actual type when using the generic type or function. The `'T` notation is a common convention, but you can use any valid identifier starting with a single quote (`'`) to represent a type parameter.

 Another example:

```Fsharp
let findMaximum<'T when 'T : comparison> (list: 'T list) =
    List.max list

let numbers = [3; 7; 1; 9; 2]
let maximum = findMaximum numbers
printfn "The maximum number is %d" maximum
```

In this example, the **findMaximum** function is defined with a generic type parameter `'T`. The `'T` represents any type that satisfies the comparison constraint. By using **List.max**, the function finds the maximum value in the provided list, regardless of the specific type. This demonstrates the power of generics in writing reusable functions.