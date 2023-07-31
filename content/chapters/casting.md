---
title: "Casting"
date: 2023-02-02T19:36:13-03:00
draft: false
weight: 17
---

Type casting in F# is a process of converting one type of value to another type of value. This can be useful in situations where the type of a value needs to be changed in order to be used in a specific context. There are several ways to perform type casting in F#, including explicit casting, implicit casting, and type coercion.

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

## Casting

```fsharp
// Explicit Casting
// Explicit casting in F# involves explicitly specifying the target type for a
// value, using the `:>` operator. 
let intValue = 42
let stringValue = intValue :> string

// Implicit Casting
// Implicit casting in F# occurs when the compiler determines the target type 
// based on context. 
type Shape =
  | Circle of float
  | Rectangle of float * float

let shapeValue = Circle 3.14

let circleValue =
  match shapeValue with
  | Circle r -> r
  | Rectangle _ -> failwith "This is a rectangle, not a circle."

// Type Coercion
// Type coercion is a special form of implicit casting that is used to convert 
// between numeric types in F#.
let intValue = 42
let floatValue = double intValue

// Printing Results
printfn "intValue: %d" intValue
printfn "stringValue: %s" stringValue
printfn "circleValue: %f" circleValue
printfn "floatValue: %f" floatValue
```
⬇️ [casting_example.fsx](#)
```
$ dotnet fsi
> #load "casting_example.fsx";;
> // The code from the file is now imported and executed in the FSI session

> // You can see the results of the expressions:
> intValue: 42
> stringValue: "42"
> circleValue: 3.14
> floatValue: 42.0
```