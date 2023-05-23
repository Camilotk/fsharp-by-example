---
title: "Generic Types"
date: 2023-05-23T17:14:20-03:00
weight: 39
---

In addition to generic functions, F# supports the creation of generic types. With generic types, you can define data structures that can work with different types. Let's consider a simple example of a generic linked list implementation:

```Fsharp
type LinkedList<'T> =
    | Empty
    | Node of 'T * LinkedList<'T>
```

In this example, we define a generic type `LinkedList<'T>` that represents a linked list. It can hold elements of any type. The linked list is defined as a discriminated union with two cases: 
- **Empty**, representing an empty list.
- **Node**, representing a node that contains an element of type `'T` and a reference to the next node, which is also of type `LinkedList<'T>`.

To demonstrate the usage of the linked list, let's define a function **addToFront** that adds an item to the front of the list:
```Fsharp
let addToFront (item: 'T) (list: LinkedList<'T>) : LinkedList<'T> =
    match list with
    | Empty -> Node(item, Empty)
    | Node(value, next) -> Node(item, list)
```

The addToFront function takes an item of type 'T and a LinkedList<'T> as parameters. It pattern matches on the list parameter to handle two cases: if the list is empty (Empty case), it creates a new node with the item as its value and an empty list as the next node. If the list is not empty (Node case), it creates a new node with the item as its value and the existing list as the next node.

Here's an example usage of the addToFront function:
```Fsharp
let list = Node(3, Node(2, Node(1, Empty)))
let updatedList = addToFront 4 list
```

In this example, we create a linked list list with elements 3, 2, and 1. We then use the addToFront function to add the value 4 to the front of the list, resulting in the updated list updatedList.

By utilizing generic types like LinkedList<'T>, you can create flexible and reusable data structures that work with various types, providing a powerful tool for building generic algorithms and promoting code reuse."

This updated explanation focuses on the generic linked list implementation and includes an example usage of the addToFront function to showcase the functionality of the generic type in a practical scenario.