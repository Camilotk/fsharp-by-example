---
title: "Pattern Matching Patterns"
date: 2023-03-18T20:12:58-03:00
weight: 36
---

Pattern matching is a powerful feature in F# that allows you to match patterns in your data and execute specific code based on the matched pattern. In this chapter, we will explore some common pattern matching patterns in F#.

## Wildcard Pattern

The wildcard pattern is the simplest pattern and matches anything. You can use the wildcard pattern to match any value or expression. Here's an example:

```FSharp
let matchAnything x =
    match x with
    | _ -> "Matched anything!"
```

In this example, the `matchAnything` function takes a single parameter `x` and uses pattern matching to match any value. The `_` in the pattern is the wildcard pattern that matches anything. If the value passed to the function matches the wildcard pattern, the function returns the string "Matched anything!".

As a more practical example:
```FSharp
let listDescription lst =
    match lst with
    | [] -> "empty list"
    | [x] -> "singleton list containing " + x.ToString()
    | _ -> "list with multiple elements"
```

## AND Pattern

 In F#, the AND pattern allows you to match an input against multiple patterns, by combining them with an ampersand (`&`). The input must satisfy each pattern on both sides of the AND pattern. The types of both sides must also be compatible.

One example of using the AND pattern is to extract values from a tuple when the second or first value is 0, respectively, as shown in the example below:

```FSharp
let locatePoint =
    function
    | (0, 0) as p -> sprintf "%A is at the origin" p
    | (x, y) & (_, 0) -> sprintf "(%i, %i) is on the x-axis" x y
    | (x, y) & (0, _) -> sprintf "(%i, %i) is on the y-axis" x y
    | (x, y) -> sprintf "Point (%i, %i)" x y
```

In this example, the `locatePoint` function uses AND patterns to extract the x and y values from a tuple. If the second value is 0, it matches the first pattern `(x, y) & (_, 0)` and outputs the message `"(x, y) is on the x-axis"`. Similarly, if the first value is 0, it matches the second pattern `(x, y) & (0, _)` and outputs the message `"(x, y) is on the y-axis)"`. If neither value is 0, it matches the third pattern `(x, y)` and outputs the message `"Point (x, y)"`.

## OR Pattern

The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result. The types of both sides of the OR pattern must be compatible. You can combine patterns using the (`|`) operator to match multiple patterns. For example:

```FSharp
let detectZeroOR point =
    match point with
    | (0, 0) | (0, _) | (_, 0) -> printfn "Zero found."
    | _ -> printfn "Both nonzero."
```

In this example, the match expression matches points that have either the first or second value equal to zero or both values equal to zero. If the input point matches any of these patterns, the function prints "Zero found." Otherwise, it prints "Both nonzero."

## CONS Pattern

In F#, the cons operator (::) separates a list’s head from its tail. The Cons pattern allows you to recursively match against a list with an arbitrary number of elements.

The Cons pattern is used to decompose a list into its first element and the remaining elements. It matches a list with a pattern of the form head :: tail, where head is the first element and tail is the remaining list. The head value can be any pattern, including a wildcard pattern, while tail is a list that may be empty.

Here's an example of using the Cons pattern to recursively print the elements of a list:

```FSharp
let list1 = [1; 2; 3; 4]

let rec printList l =
    match l with
    | head :: tail -> printf "%d " head; printList tail
    | [] -> printfn ""

printList list1 // output: "1 2 3 4 "
```

In this example, the `printList` function recursively matches against the input list using the Cons pattern. When the list is non-empty, the head value is printed and the function is called recursively with the tail. When the list is empty, the function terminates.

The Cons pattern is often used in recursive functions that operate on lists. For example, you can use the Cons pattern to implement the `List.length` function:
```FSharp
let rec length l =
    match l with
    | [] -> 0
    | _ :: tail -> 1 + length tail
```

In this implementation, the `length` function recursively matches against the input list using the Cons pattern. When the list is empty, the function returns 0. When the list is non-empty, the function increments the count and makes a recursive call with the tail.