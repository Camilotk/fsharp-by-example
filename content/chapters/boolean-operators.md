---
title: "Boolean Operators"
date: 2023-02-02T19:36:31-03:00
draft: false
weight: 18
---

Boolean operators are used to perform logical operations on Boolean values (i.e., true and false). F# provides several boolean operators that can be used to test conditions, compare values, and perform other types of operations. In this chapter, we will discuss the different boolean operators in F# and how to use them in your code.

## AND

The logical AND operator (&&) is used to combine two conditions. The result of the AND operation is true if both conditions are true, and false if either condition is false. The syntax for the AND operator in F# is as follows:

```
condition1 && condition2
```

For example, consider the following code:

```fsharp
let x = 5
let y = 6
if x < 10 && y > 5 then
  printfn "Both conditions are true"
else
  printfn "Either condition is false"

// Output: Both conditions are true
```

## OR

The logical OR operator (||) is used to combine two conditions. The result of the OR operation is true if either condition is true, and false if both conditions are false. The syntax for the OR operator in F# is as follows:

```
condition1 || condition2
```

For example, consider the following code:

```fsharp
let x = 5
let y = 6
if x < 10 || y > 10 then
  printfn "Either condition is true"
else
  printfn "Both conditions are false"

// Output: Either condition is true
```

## NOT

The logical NOT operator (not) is used to negate a condition. The result of the NOT operation is true if the condition is false, and false if the condition is true. The syntax for the NOT operator in F# is as follows:

```
not condition
```

For example, consider the following code:

```fsharp
let x = 5
if not (x > 10) then
  printfn "The condition is false"
else
  printfn "The condition is true"

// Output: The condition is false
```