---
title: "List Module"
date: 2023-02-17T21:02:03-03:00
weight: 22
---

In addition to the basic list operations that we covered in the previous chapter, F# also provides a List module with many useful functions for working with lists. This module provides a variety of functions for manipulating lists and performing common operations.

## Common Functions

There are many other functions in the List module that are beyond the scope of this chapter, but some notable ones include:

### append
Concatenates two lists together

```fsharp
let list1 = [1; 2; 3]
let list2 = [4; 5; 6]

let concatenated = List.append list1 list2 // => val concatenated: int list = [1; 2; 3; 4; 5; 6]
```

### length
Returns the length of a list

```fsharp
let myList = [1; 2; 3; 4; 5]

let length = List.length myList // => val length: int = 5
```

### exists
Returns true if at least one element in a list satisfies a given predicate

```fsharp
let myList = [1; 3; 5; 7; 8; 9]

let hasEven = List.exists (fun x -> x % 2 = 0) myList // => val hasEven: bool = true
```

### forAll
Returns true if all elements in a list satisfy a given predicate

```fsharp
let myList = [2; 4; 6; 8]

let allEven = List.forall (fun x -> x % 2 = 0) myList // => val allEven: bool = true

let myList2 = [2; 4; 6; 7; 8]

let allEven2 = List.forAll (fun x -> x % 2 = 0) myList2 // => val allEven2: bool = false
```

### sortBy
Sorts a list by a given comparison function

```fsharp
let myList = ["apple"; "banana"; "cherry"; "date"; "elderberry"]

let sortedList = List.sortBy (fun (x : string) -> x.Length) myList 
// => val sortedList: string list = ["date"; "apple"; "banana"; "cherry"; "elderberry"]
```

### take
Returns the first n elements of a list

```fsharp
let myList = [1; 2; 3; 4; 5; 6; 7]

let firstThree = List.take 3 myList // => val firstThree: int list = [1; 2; 3]
```

### skip
Skips the first n elements of a list

```fsharp
let myList = [1; 2; 3; 4; 5; 6; 7]

let afterThree = List.skip 3 myList // => val afterThree: int list = [4; 5; 6; 7]
```
