---
title: "Filter"
date: 2023-02-18T00:05:22-03:00
weight: 27
---

In F#, the `filter` function allows you to remove elements from a sequence that do not match a specified condition. The resulting sequence only contains elements that satisfy the condition.

## Syntax

The syntax for `filter` is as follows:

```fsharp
filter (predicate: 'a -> bool) (list: 'a list) : 'a list
``` 

where:
- `predicate` is a function that takes an element of type generic - we'll see that - and returns a boolean value.
- `list` is a list of elements of type of passed generic type.
- The return value is a new list of elements of the type generic that pass the `predicate` test.

## Example

Suppose we have a list of integers:

```fsharp
let numbers = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

We can use `filter` to remove all even numbers from the list:

```fsharp
let odds = filter (fun x -> x % 2 <> 0) numbers
```

In this example, `fun x -> x % 2 <> 0` is the `predicate` function that checks if a given element is odd. The resulting list `odds` contains only the odd numbers in the original list:


```fsharp
[1; 3; 5; 7; 9]
```

## Using Filter with Arrays

The `filter` function can also be used with arrays. Here's an example:

```fsharp
let numbers = [|1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
let odds = filter (fun x -> x % 2 <> 0) numbers
```

The resulting array `odds` contains only the odd numbers in the original array:

```fsharp
[|1; 3; 5; 7; 9|]
```

The filter function is a powerful tool in F# that allows you to remove elements from a sequence that do not match a specified condition. It can be used with both lists and arrays, and is a great tool for data manipulation and processing.



