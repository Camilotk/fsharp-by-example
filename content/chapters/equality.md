---
title: "Structural Equality"
date: 2023-03-18T17:04:26-03:00
weight: 29
---

## Structural Equality in F# vs. Referential Equality in C#

In F#, values are compared using structural equality, which means that two values are considered equal if they have the same structure and contain the same data. This is different from the referential equality used in other languages such as C#, where two objects are considered equal only if they refer to the same memory location.

To demonstrate this difference, let's compare two F# records using the `=` operator:
```FSharp
type Person = { Name: string; Age: int }
let person1 = { Name = "Alice"; Age = 30 }
let person2 = { Name = "Alice"; Age = 30 }
let areEqual = person1 = person2 // true
```

In this example, `person1` and `person2` are two different instances of the `Person` record type, but they have the same structure and data. Therefore, when we compare them using the `=` operator, we get true.

On the other hand, in C#, two objects are considered equal only if they refer to the same memory location, as shown in the following example:

```CSharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

var person1 = new Person { Name = "Alice", Age = 30 };
var person2 = new Person { Name = "Alice", Age = 30 };
var areEqual = person1 == person2; // false
```

In this example, `person1` and `person2` are two different instances of the `Person` class, even though they have the same structure and data. Therefore, when we compare them using the `==` operator, we get `false`.