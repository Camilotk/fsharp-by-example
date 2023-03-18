---
title: "Arrays"
date: 2023-02-17T22:26:54-03:00
weight: 25
---

Arrays in F# are similar to lists but have different performance characteristics and the ability to index any value directly in the array. In this chapter, we will cover the syntax of arrays and how they differ from lists.

## Creating Arrays

To create an array, we use the same syntax as for lists, but with pipes instead of square brackets:

```fsharp
[|1; 2; 3|]
// Output: [|1; 2; 3|]
```

The result of the code above is an array containing the values 1, 2, and 3.

## Accessing Items in an Array

To access an item in an array, we use the syntax of square brackets and the position of the item we want to access:

```fsharp
[|1; 2; 3|].[1]
// Output: 2
```

The code above will return the second item in the array, which is 2.

## Adding Elements to Arrays

Unlike lists, arrays don't have a head operator (::) to add elements. However, we can use array slicing to add elements to an array.

```fsharp
let arr = [| 1; 2; 3 |]

// Adding an element to the end of the array
let newArr = Array.append arr [| 4 |]
// Output: [|1; 2; 3; 4|]

// Adding an element to the beginning of the array
let newArr2 = Array.append [| 0 |] arr
// Output: [|0; 1; 2; 3|]

// Adding elements at a specific index
let idx = 1
let newArr3 = Array.concat [ arr.[0..idx-1]; [| 10; 20 |]; arr.[idx..] ]
// Output: [|1; 10; 20; 2; 3|]
```

## List Comprehensions in Arrays

Arrays support list comprehensions in the same way as lists. We can use the for...do or for...yield keywords to generate an array. Here's an example:

```fsharp
[| for x in [1..3]
     do yield 2 * x |]
// Output: [|2; 4; 6|]
```

In this example, we create an array of doubled values from the range 1 to 3.
