---
title: "Types"
date: 2023-02-02T19:30:17-03:00
draft: false
weight: 15
---

F# is a statically typed language, meaning that the type of a value must be known at compile-time. F# has several built-in types that can be used to represent values in your programs. We'll explore the basic types in F# and how to use them.

# Types in F#
```fsharp
// Types in F#

// Numbers
// F# supports several numeric types such as integers (int, long, byte), floating-point numbers (float), and decimal numbers (decimal).
// The following table shows the size and range of values for each type:

// | Type    | Size    | Range                                      |
// |---------|---------|--------------------------------------------|
// | byte    | 8-bit   | 0 to 255                                   |
// | int     | 32-bit  | -2,147,483,648 to 2,147,483,647           |
// | float   | 32-bit  | Approximately ±1.5 × 10^-45 to ±3.4 × 10^38 |
// | long    | 64-bit  | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
// | decimal | 128-bit | ±1.0 × 10^-28 to ±7.9 × 10^28             |

// Booleans
// The boolean type in F# is used to represent true/false values. It is defined as bool. The values true and false are the only two valid values of this type.

let booleanValue = true

// Strings
// Strings are sequences of characters used to represent text. In F#, strings are defined using double quotes ".

let stringValue = "Hello, World!"

// Char
// A char type represents a single Unicode character. It is defined using single quotes '.

let charValue = 'A'

// Tuples
// Tuples are a way to group values together into a single value. Tuples in F# can have any number of elements and each element can be of a different type.

let nameAge = ("John", 30)

// Arrays
// An array is a collection of values of the same type. Arrays in F# are defined using square brackets [ ].

let numbersArray = [|1; 2; 3; 4; 5|]

// Lists
// Lists are a data structure in F# that represent a sequence of values. Lists are similar to arrays, but they are immutable, meaning that once a list is created, its values cannot be changed. Lists in F# are defined using square brackets [ ].

let numbersList = [1; 2; 3; 4; 5]

// BigInteger
// The BigInteger type in F# is used to represent arbitrarily large integers. Unlike the int and long types, BigInteger does not have a maximum size, so it can be used to represent integers of any size. The BigInteger type is defined in the System.Numerics namespace and can be used by opening the System.Numerics module at the top of your code.

open System.Numerics

let bigInt = BigInteger(1000000000000000000)

// To see the results in F# Interactive (FSI), run the script in FSI:
// 1. Open a terminal or command prompt.
// 2. Navigate to the directory containing this .fsx file.
// 3. Launch the F# REPL by typing `dotnet fsi` and pressing Enter.
// 4. Load the `types.fsx` file in FSI using `#load "types.fsx";;`
// 5. You can now access and interact with the defined values, such as `booleanValue`, `stringValue`, `charValue`, `nameAge`, `numbersArray`, `numbersList`, and `bigInt`.
```
⬇️ [types.fsx](#)
```
$ dotnet fsi

> #load "types.fsx";;

> let booleanValue = true;;
val booleanValue : bool = true

> let stringValue = "Hello, World!";;
val stringValue : string = "Hello, World!"

> let charValue = 'A';;
val charValue : char = 'A'

> let nameAge = ("John", 30);;
val nameAge : string * int = ("John", 30)

> let numbersArray = [|1; 2; 3; 4; 5|];;
val numbersArray : int [] = [|1; 2; 3; 4; 5|]

> let numbersList = [1; 2; 3; 4; 5];;
val numbersList : int list = [1; 2; 3; 4; 5]

> open System.Numerics;;

> let bigInt = BigInteger(1000000000000000000);;
val bigInt : System.Numerics.BigInteger = 1000000000000000000

> booleanValue;;
val it : bool = true

> stringValue;;
val it : string = "Hello, World!"

> charValue;;
val it : char = 'A'

> nameAge;;
val it : string * int = ("John", 30)

> numbersArray;;
val it : int [] = [|1; 2; 3; 4; 5|]

> numbersList;;
val it : int list = [1; 2; 3; 4; 5]

> bigInt;;
val it : System.Numerics.BigInteger = 1000000000000000000
```