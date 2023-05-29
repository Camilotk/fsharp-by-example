---
title: "Option Module"
date: 2023-05-27T21:18:11-03:00
weight: 44
---

The Option module in F# provides functions that operate on the Option type, allowing you to handle and transform options effectively.

Let's consider the values:
```Fsharp
let option1 = Some 42
let option2 = None
```

## map

The `Option.map` function applies a transformation function to the value inside an option and returns a new option containing the transformed value.

```Fsharp
Option.map (fun x -> x * 2) option1 

// => val it: int option = Some 84
```

## filter

The `Option.filter` function applies a predicate to the value inside an option and returns the option itself if the predicate is true, or `None` if the predicate is false.

```Fsharp
Option.filter (fun x -> x < 50) option1 // => val it: int option = Some 42
Option.filter (fun x -> x > 50) option1 // => val it: int option = None
```

## bind

The `Option.bind` function, also known as the `>>=` operator, applies a transformation function to the value inside an option and returns a new option. It is useful for chaining computations that may return options.

```Fsharp
let boundOption =
    Option.bind (fun x ->
        if x > 0 then Some (x * 3)
        else None
    ) option1 
    
// =>  val boundOption: int option = Some 126
```

## defaultValue

The `Option.defaultValue` function takes an option and a default value. If the option is `None`, it returns the default value; otherwise, it returns the value inside the option.

```Fsharp
Option.defaultValue 0 option1 // => val it: int = 42
Option.defaultValue 0 option2 // => val it: int = 0
```

## contains

The `Option.contains` function checks if an option contains a specific value and returns a boolean indicating the result.

```Fsharp
let containsValue = Option.contains 42 option1 // => val it: bool = true
```

## get

The `Option.get` function extracts the value from an option if it is `Some`, or throws an exception if it is `None`.

```Fsharp
Option.get option1 // => val it: int = 42
```

## orElse

The `Option.orElse` function combines two options. If the first option is `Some`, it returns the first option; otherwise, it returns the second option.

```Fsharp
Option.orElse option1 option2 // => val it: int option = Some 42
Option.orElse option2 option1 // => val it: int option = Some 42
```

## isSome

The `Option.isSome` function checks if an option contains a value (is `Some`) and returns a boolean indicating the result.

```Fsharp
Option.isSome option1 // => val it: bool = true
Option.isSome option2 // => val it: bool = false
```

## isNone

The `Option.isNone` function checks if an option is empty (is `None`) and returns a boolean indicating the result.

```Fsharp
Option.isNone option1 // => val it: bool = false
Option.isNone option2 // => val it: bool = true
```
