---
title: "Discriminated Union"
date: 2023-03-18T15:28:23-03:00
weight: 28
---

## Discriminated Union in F#

In F#, programmers are used to defining types to structure data, but what if types could define a set of choices? A Discriminated Union is a type that can have a certain set of cases, and the value of a Discriminated Union must be one of those cases that were defined. Because the representation of a Discriminated Union is the sum of all its cases, it is also known as a **Sum Type**, corresponding to types such as products in tuples. Discriminated Union can have methods and properties.

## Defining a Discriminated Union

A Discriminated Union is defined using the type keyword, followed by the name of the Discriminated Union, and then a vertical bar (`|`) separated list of cases. 

Let's take a look at an example of a discriminated union that represents French playing cards:

```FSharp
type Suit = Spades | Hearts | Diamonds | Clubs
```
> Note that the cases have to be defined using PascalCase.

We defined a discriminated union called `Suit` with four cases: `Spades`, `Hearts`, `Diamonds`, and `Clubs`. We can think of a Discriminated Union as enumerations. A value that is a value of type `Suit` must be one of the possible options defined in its enumeration.

## Adding Data to Cases

Discriminated Union can also have additional data associated with each case. The type of this data can be anything from primitives to tuples, records, and even other Discriminated Unions. Let's take the previous example of defining cards and create our ranks adding additional data to each rank representing the point value:

```FSharp
type Rank =
  | Ace of int
  | King of int
  | Queen of int
  | Jack of int
  | Ten of int
  | Nine of int
  | Eight of int
  | Seven of int
  | Six of int
```

In this example, each case of the Discriminated Union Rank has an additional int value associated with it, representing the point value for each rank. We can initialize a value of Rank by providing the int value associated with the specific rank. For example:

```FSharp
let ace = Ace(14)
let six = Six(6)
```

## Combining Discriminated Unions

Discriminated Unions can also be combined to create more complex data types. For example, let's consider two Discriminated Unions, one defining the card ranks and another defining the card suits, we can now define a Union Type with two cases, where the first case indicates that the card is a joker, and the second case defines that it is a regular card, which is a value consisting of a Rank and a Suit:

```FSharp
type Card =
  | Joker
  | Regular of Rank * Suit
```

In this example, Joker is the first case of the Discriminated Union Card and it has no additional data associated with it. The second case, Regular, has additional data of type Rank * Suit, which is a tuple of a Rank and a Suit. We can initialize values of Card by providing the Rank and Suit values associated with the regular card:

```FSharp
let joker = Joker
let aceOfSpades = Regular(Ace(1), Spades)
let tenOfHearts = Regular(Ten(10), Hearts)
```
