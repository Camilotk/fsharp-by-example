---
title: "Pattern Matching on Data Structures"
date: 2023-03-18T18:23:02-03:00
weight: 35
---

Pattern matching is a powerful feature in F# that allows you to extract and work with the values in data structures such as tuples, lists, arrays, discriminated unions, and records. In this chapter, we'll explore how to use pattern matching to work with these data structures.

## Matching on Tuples

Matching on tuples allows you to match a tuple against one or more patterns. Let's say we have a function that returns a tuple of two integers, and we want to write a function that takes the tuple and returns the sum of the two integers. We can use pattern matching on tuples as follows:

```FSharp
let sumTuple (x, y) =
    match (x, y) with
    | (a, b) -> a + b
```

In this example, we define a function `sumTuple` that takes a tuple of two integers `(x, y)`. We then use pattern matching to match the tuple `(x, y)` against a pattern of the form `(a, b)`. The pattern binds the values of `x` and `y` to `a` and `b`, respectively, and then returns their sum.

## Matching on Lists

Matching on lists allows you to match a list against one or more patterns. Let's say we want to write a function that takes a list of integers and returns the sum of the even integers. We can use pattern matching on lists as follows:

```FSharp
let sumEvens xs =
    let rec sum acc = function
        | [] -> acc
        | x::xs when x % 2 = 0 -> sum (acc + x) xs
        | _::xs -> sum acc xs
    sum 0 xs
```

In this example, we define a function `sumEvens` that takes a list of integers `xs`. We then define an inner recursive function `sum` that takes an accumulator `acc` and a list `xs`. We use pattern matching to match the list `xs` against three patterns: `[]`, `x::xs when x % 2 = 0`, and `_::xs`. The first pattern matches an empty list and returns the accumulator. The second pattern matches a non-empty list where the head `x` is even, and it adds `x` to the accumulator before calling `sum` recursively on the tail `xs`. The third pattern matches a non-empty list where the head `_` is odd, and it discards the head and calls `sum` recursively on the tail `xs`.

## Matching on Discriminated Unions

Discriminated Unions (DUs) are often used in F# to model complex data structures. One of the most powerful features of DUs is pattern matching. Pattern matching is a powerful tool that allows you to match values against patterns and perform different actions depending on the pattern that is matched.

In F#, you can use pattern matching with DUs to extract the values associated with each case of the DU. Let's take the example of the `Sound` DU:

```FSharp
type Note = 
    | A 
    | ASharp 
    | B 
    | C 
    | CSharp 
    | D 
    | DSharp 
    | E 
    | F 
    | FSharp 
    | G 
    | GSharp

type Octave = 
    | One 
    | Two 
    | Three

type Sound =
    | Pause
    | Tone of Note * Octave
```

We can use pattern matching to extract the values associated with the `Tone` case:

```FSharp
let pause = Pause
let tone = Tone(FSharp, Two)

match tone with
    | Tone(note, octave) -> printfn "Note: %A, Octave: %A" note octave
    | Pause -> printfn "Pause"
// Output: Note: FSharp, Octave: Two
```

In this example, we have defined a value of Sound called `tone`, which is a `Tone` consisting of a F# note and the second octave. We then use the `match` keyword to pattern match against the `tone` value. The first case that we define in the `match` expression is `Tone(note, octave)`, which matches against any value that is a `Tone` case of the `Sound` DU. We then use `printfn` to print out the note and octave values.

If the value of `tone` is a `Pause`, the second case of the `match` expression will match and print out "Pause" to the console.

## Matching on Records

Records are another data structure that can be pattern matched in F#. Let's take the example of the `Card` record that we defined earlier:

```FSharp
type Card = { Suit: Suit; Rank: Rank }
```

We can use pattern matching to extract the `Suit` and `Rank` values from a `Card`:

```FSharp
let card = { Suit = Spades; Rank = Ace(1) }

match card with
| { Suit = suit; Rank = rank } -> printfn "Suit: %A, Rank: %A" suit rank
// Output: Suit: Spades, Rank: Ace 1
```

In this example, we have defined a value of `Card` called `card`, which is a Spades Ace. We then use the `match` keyword to pattern match against the `card` value. The first case that we define in the `match` expression is `{ Suit = suit; Rank = rank }`, which matches against any value that is a `Card` record. We then use `printfn` to print out the suit and rank values.

Pattern matching on records can be useful when you want to extract specific fields from a record and perform some action on them. It is also useful when working with large records that have many fields, as you can extract only the fields that you need.

## Matching on Arrays

Arrays are another data structure that can be pattern matched in F#. Let's say we want to write a function that takes an array of integers and returns the sum of the even integers. We can use pattern matching on arrays as follows:

```FSharp
let sumEvens arr =
    let mutable sum = 0
    for i in 0 .. arr.Length - 1 do
        match arr.[i] with
        | x when x % 2 = 0 -> sum <- sum + x
        | _ -> ()
    sum
```

In this example, we define a function `sumEvens` that takes an array of integers `arr`. We then define a mutable variable `sum` to hold the running sum of even integers. We use a `for` loop to iterate over the array indices, and we use pattern matching to match the value at each index against two patterns: `x when x % 2 = 0`, which matches even integers and adds them to the `sum`, and `_`, which matches all other values and does nothing.

After iterating over all the elements in the array, we return the final value of the `sum`.