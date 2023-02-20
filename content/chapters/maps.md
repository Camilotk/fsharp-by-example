---
title: "Maps"
date: 2023-02-17T23:46:46-03:00
weight: 26
---

The `map` function is a common function used in many functional programming languages, including F#. It is used to transform the elements of a collection using a given function, producing a new collection with the same length but with each element transformed by the given function.

## Syntax

The syntax of the `map` function in F# is as follows:

```fsharp
List.map (function) list
Array.map (function) array
```

Here, `List.map` and `Array.map` are the two versions of the function, and `function` is the function used to transform the elements of the collection. The `list` or `array` is the collection to be transformed.

## Example

Let's say we have a list of numbers and we want to transform each element of the list by doubling it. We can use the `map` function as follows:

```fsharp
let numbers = [1; 2; 3; 4; 5]
let doubledNumbers = List.map (fun x -> x * 2) numbers
```

Here, we define a list of numbers and then use the `List.map` function to apply the lambda function `fun x -> x * 2` to each element of the list. This creates a new list, `doubledNumbers`, with each element transformed by the given function.

## Using Map with Arrays

Similarly, we can use the `Array.map` function to transform the elements of an array. For example:

```fsharp
let numbers = [|1; 2; 3; 4; 5|]
let doubledNumbers = Array.map (fun x -> x * 2) numbers
```

In this case, we define an array of numbers and then use the `Array.map` function to apply the lambda function `fun x -> x * 2` to each element of the array. This creates a new array, `doubledNumbers`, with each element transformed by the given function.

The `map` function is a useful tool for transforming collections in F#. By using the `map` function, we can easily apply a given function to each element of a collection and create a new collection with the transformed elements. Whether we are working with lists or arrays, the `map` function can help us write concise and efficient code.
