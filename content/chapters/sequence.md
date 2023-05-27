---
title: "Sequence"
date: 2023-05-27T20:33:40-03:00
weight: 46
---

Sequences in F# are an ordered collection of elements of the same type. They are immutable data structures that can represent both finite and infinite sequences. Sequences in F# support lazy evaluation, which means that elements are computed on-demand as they are needed, leading to memory-efficient processing.

Sequences can be created using sequence expressions or sequence functions. Let's look at some examples:
```Fsharp
let numbers = seq { 1 .. 10 }
// Result: seq [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

In the first example, we create a sequence named **numbers** that contains the numbers from 1 to 10. The `seq { 1 .. 10 }` syntax specifies a range from 1 to 10, and the resulting sequence contains the individual numbers.

One of the key advantages of using sequences in F# is their lazy evaluation nature. This means that elements are computed only when they are needed, allowing for memory-efficient processing. Lazy evaluation is especially useful when dealing with large or infinite sequences.

Let's consider an example where we create an infinite sequence of Fibonacci numbers:
```Fsharp
let fibonacci =
    let rec fib a b = seq {
        yield a
        yield! fib b (a + b)
    }
    fib 0 1
```
In this example, we define a recursive sequence expression to generate Fibonacci numbers. The `yield` keyword is used to generate each Fibonacci number, and `yield!` is used to recursively generate the next number in the sequence. 

We then use the `Seq.take` function to extract the first ten elements from the infinite sequence:
```Fsharp
let firstTen = Seq.take 10 fibonacci
```
This will return a value of type `seq<int>` this mean it is a sequence of numbers still not computed.

If we get the value of **firstTen** we will get:
```Fsharp
firstTen // => val it: seq<int> = seq [0; 1; 1; 2; ...]
```
For get all values they have to be called for example in a loop.


Learning and understanding sequences in F# brings several advantages to developers. By leveraging sequences, you can write expressive and concise code, making your programs more readable and maintainable. The lazy evaluation nature of sequences ensures memory efficiency, allowing you to handle large or infinite collections without excessive memory allocation. By incorporating sequences into your F# toolkit, you gain a powerful tool for data manipulation and processing within the functional programming paradigm.