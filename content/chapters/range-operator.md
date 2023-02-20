---
title: "Range Operator"
date: 2023-02-17T21:46:45-03:00
weight: 23
---

The range operator `..` is used to declare lists of ordered sequence values.

## Basic Usage

Using the range operator, we can quickly create a list of ordered sequence values with a single line of code. For instance, the following F# code creates a list of integers ranging from 1 to 5:

```fsharp
[1..5]
// => [1; 2; 3; 4; 5]
```

Similarly, we can create a list of characters ranging from 'a' to 'f':

```fsharp
['a'..'f']
// => ['a'; 'b'; 'c'; 'd'; 'e'; 'f']
```

## Specifying a Step Value

By default, the range operator creates a list with an increment of 1. However, we can change the increment by specifying a step value. For instance, to create a list of integers ranging from 1 to 10 with an increment of 2, we can use the following code:

```fsharp
[1..2..10]
// => [1; 3; 5; 7; 9]
```

Here, the `2` in `1..2..10` specifies that we want the range to increment by 2 instead of the default of 1.

## Reversing a Range

The range operator can also be used to create a list in reverse order. To create a list of integers ranging from 10 to 0 in reverse order, we can use the following code:

```fsharp
[10..-1..0];;
// => [10; 9; 8; 7; 6; 5; 4; 3; 2; 1; 0]
```

Here, the `-1` in `10..-1..0` specifies that we want the range to increment by -1, which effectively creates a reversed list.

