---
title: "List Comprehensisions"
date: 2023-02-17T22:17:28-03:00
weight: 24
---

List Comprehensions is a more powerful way of constructing lists in F# that is derived from the mathematical concept of "set comprehensions" or "Set-builder notation". A set comprehension is a list defined from a set of rules that define the properties that its elements must satisfy.

Any comprehension has at least three parts:
- **Collection**: the source of the values that will be in the list, in F# usually a range or a list.
- **Identifier or Pattern**: the identifier used to represent each element in the list or a pattern to match elements of a complex type.
- **Output Function**: the expression that maps the values of the collection to the items in the list.

Here is an example of a list comprehension in F# that generates a list of even numbers:

```fsharp
[for x in 1..10 do yield 2 * x];;
```

The above code uses a range of integers `1..10` as the source collection, uses the identifier `x` to represent each element of the collection, and applies the output function `2 * x` to each element to produce a new list of even numbers.

List comprehensions can also be chained together:

```fsharp
[for r in 1..8 do
    for c in 1..8 do
        if r <> c then
            yield (r,c)]
```

The above code generates a list of all pairs of numbers from 1 to 8, except pairs where the numbers are equal.

List Comprehensions are a concise and expressive way to construct lists and can be used in many different scenarios in F#.


