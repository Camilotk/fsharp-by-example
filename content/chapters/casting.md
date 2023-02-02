---
title: "Casting"
date: 2023-02-02T19:36:13-03:00
draft: false
weight: 17
---

Type casting in F# is a process of converting one type of value to another type of value. This can be useful in situations where the type of a value needs to be changed in order to be used in a specific context. There are several ways to perform type casting in F#, including explicit casting, implicit casting, and type coercion.

## Explicit Casting

Explicit casting in F# involves explicitly specifying the target type for a value, using the `:>` operator. For example:

```fsharp
let intValue = 42
let stringValue = intValue :> string
```

## Implicit Casting

Implicit casting in F# occurs when the compiler determines the target type based on context. For example, when you declare a variable numeric that is bigger but set a value that fits in a smaller type:

```fsharp
type Shape =
  | Circle of float
  | Rectangle of float * float

let shapeValue = Circle 3.14

// shapeValue is a value of type Shape, but it is implicitly cast to the float type in the circleValue variable by using pattern matching.
let circleValue =
  match shapeValue with
  | Circle r -> r
  | Rectangle _ -> failwith "This is a rectangle, not a circle."
```

## Type Coercion

Type coercion is a special form of implicit casting that is used to convert between numeric types in F#. For example, the following code converts an integer value to a float using `float` operator:

```fsharp
let intValue = 42
let floatValue = double intValue
```

<details>
<summary>List of casting operators</summary>
The following table shows some of the most useful conversion operators defined in F#:

| Operator | Description |
|----------|-------------|
| `byte`   | Convert to byte, an 8-bit unsigned type. |
| `sbyte`  | Convert to signed byte. |
| `int` | Convert to a 32-bit signed integer. |
| `float`, `double` | Convert to a 64-bit double-precision IEEE floating point number. |
| `single` | Convert to a 32-bit single-precision IEEE floating point number. |
| `decimal` | Convert to `System.Decimal`. |
| `char`    | Convert to `System.Char`, a Unicode character. |
| `enum` | Convert to an enumerated type. |

</details>