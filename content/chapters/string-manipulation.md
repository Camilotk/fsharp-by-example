---
title: "String Manipulation"
date: 2023-02-02T23:43:23-03:00
weight: 20
---

F# provides several functions and methods for string manipulation.

### Split

The `split` function splits a string into an array of substrings based on a specified separator:

```fsharp
let sentence = "OCaml, Standard ML, F#"
let names = sentence.Split ","
// val names: string array = [|"OCaml"; " Standard ML"; " F#"|]
```

### Replace

The `replace` function replaces all occurrences of a specified string with another string:

```fsharp
let sentence = "OCaml, Standard ML, F#"
let updatedSentence = sentence.Replace("Standard ML","Haskell")
// val updatedSentence: string = "OCaml, Haskell, F#"
```

### Substring

The `substring` function returns a substring from a specified starting index to an optional ending index:

```fsharp
let sentence = "OCaml, Standard ML, F#"
let subSentence = sentence.Substring(0, 5)
// val subSentence: string = "OCaml"
```

### Trim

The trim function removes all leading and trailing white space characters from a string:

```fsharp
let sentence = "  F# is awesome.   "
let trimmedSentence = sentence.Trim()
// val trimmedSentence: string = "F# is awesome."
```

> **Obs**: The F# standard library provides a module `System.String` that contains a variety of functions for working with strings. 

### Concat

The `String.concat` function is used to join a sequence of strings into a single string with a delimeter:

```fsharp
let strings = [ "OCaml"; "Standard ML"; "F#" ]
let fullString = String.concat ", " strings
// val fullString: string = "OCaml, Standard ML, F#"
```

### Length

The `String.length` function is used to returns the value of length of the string:

```fsharp
let content = "F# for fun and profit"
let strSize = String.length content
// val strSize: int = 21
```
