---
title: "Tuples"
date: 2023-03-18T19:45:06-03:00
weight: 28
---

Tuples are ordered groups of anonymous values that are commonly used to store intermediate calculation results or to return multiple values from a function. The values in a tuple can be of different types and their types are written in order and separated by an asterisk. All tuples are immutable by default.

In F#, tuples are created using parentheses, and the values inside the parentheses are separated by commas. For example:

```FSharp
(1, "Camilo", 1.80, true)
// => val it : int * string * float * bool = (1, "Camilo", 1.8, true)
```

his creates a tuple with four values of different types: an integer, a string, a float, and a boolean.

Since tuples have no named values, their elements are accessed by position. For tuples with only two elements, the `fst` and `snd` functions can be used to access the first and second elements, respectively. For example:

```FSharp
fst ("Galileu", 6)
// => val it : string = "Galileu"

snd ("Galileu", 6)
// => val it : int = 6
```

Tuples can also be nested, allowing for the creation of more complex data structures. For example:

```FSharp
let myNestedTuple = ("F#", (1, 2), [3; 4; 5])
```

This creates a tuple with three elements, where the second element is another tuple and the third element is a list. Elements of nested tuples can be accessed using nested pattern matching or by using functions like fst and snd multiple times.

In addition to being used for returning multiple values from a function, tuples are also useful for passing multiple arguments to a function. For example, instead of passing three arguments to a function, you can pass a tuple with three elements. This can make the code more concise and easier to read.