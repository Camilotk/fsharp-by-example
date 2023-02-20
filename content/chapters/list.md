---
title: "Lists"
date: 2023-02-17T18:59:04-03:00
weight: 21 
---

Lists are a commonly used data structure in F# and they provide a way to store sequences of values. In F#, lists are immutable, meaning that their contents cannot be changed after they are created. This feature makes them well-suited for functional programming.

## Creating Lists

In F#, lists can be created in several ways. The simplest way to create a list is to use square brackets and separate the elements with semicolons. For example:

```fsharp
let numbers = [1; 2; 3]
```

Another way to create lists is to use the `init` function, which creates a list with a specified number of elements. The following code creates a list with 5 elements:

```fsharp
let fiveElements = List.init 5 (fun i -> i + 1)
```

> We'll see more about functions in `List` module next.

## Accessing Elements in Lists

In F#, elements in a list can be accessed using indexing. The first element in a list has an index of 0, and so on. For example:

```fsharp
let numbers = [1; 2; 3]
let first = numbers.[0] // first will be 1
```

In addition to indexing, other functions can be used to access elements in a list. The `head` function returns the first element in a list, while the `tail` function returns the rest of the list. The following code demonstrates how to use these functions:

```fsharp
let numbers = [1; 2; 3]
let first = List.head numbers // first will be 1
let tail = List.tail numbers // tail will be [2; 3]
```

## Adding Values to Lists

In F#, we can add elements to a list using the `::` operator. This operator adds a new element to the head of the list, creating a new list. For example, we can add the element `4` to the list `[1; 2; 3]` as follows:

```fsharp
let myList = 4 :: [1; 2; 3]
```

The resulting list will be `[4; 1; 2; 3]`.

We can also concatenate two lists using the `@` operator. For example, to concatenate the lists `[1; 2]` and `[3; 4]`, we can use the following code:

```fsharp
let list1 = [1; 2]
let list2 = [3; 4]
let concatenatedList = list1 @ list2
```

The resulting list will be `[1; 2; 3; 4]`.

It's worth noting that adding an element to the head of a list can be an expensive operation, especially for large lists, since all the elements of the list have to be shifted by one position. Therefore, it's usually more efficient to build a list by adding elements to the tail and then reversing the list at the end, if necessary.
