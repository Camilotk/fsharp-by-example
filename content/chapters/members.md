---
title: "Members"
date: 2023-03-18T19:45:11-03:00
weight: 30
---

Records in F# are not just simple data structures, but they can also contain functions as members. These functions are called record members and can be used to encapsulate behavior that operates on the data stored in the record.

To define a record member, we can use the `member` keyword followed by the member name and the member definition. Here's an example of a record with a member function that returns a greeting message:

```FSharp
type Person = {
    name: string;
    age: int;
    member this.greet() = sprintf "Hello, my name is %s and I am %d years old." this.name this.age
}

let person = { name = "John"; age = 30 }
person.greet() // Output: "Hello, my name is John and I am 30 years old."
```

Record members can access the fields of the record they belong to using the this keyword, which refers to the current instance of the record. This allows us to define behavior that is closely tied to the data stored in the record.

Record members can also be defined as properties, which are similar to fields but with associated behavior. To define a property, we can use the `member` keyword followed by the property name and the property definition. Here's an example of a record with a property that computes the full name of the person:

```FSharp
type Person = {
    first: string;
    last: string;
    member this.FullName
        with get() = sprintf "%s %s" this.first this.last
}

let person = { first = "John"; last = "Doe" }
person.FullName // Output: "John Doe"
```

In this example, we defined a property called `FullName` that returns the concatenation of the `first` and `last` fields of the record. The `with get()` syntax specifies that this is a read-only property, meaning that it can only be accessed and not modified.

Record members can also be defined as methods, which are similar to functions but with associated behavior. To define a method, we can use the `member` keyword followed by the method name and the method definition. Here's an example of a record with a method that computes the age of the person in dog years:

```FSharp
type Person = {
    name: string;
    age: int;
    member this.AgeInDogYears() = this.age * 7
}

let person = { name = "John"; age = 30 }
person.AgeInDogYears() // Output: 210
```

In this example, we defined a method called `AgeInDogYears` that multiplies the `age` field of the record by 7 to compute the age of the person in dog years.

Record members can also be defined as constructors, which are special functions that create new instances of the record. To define a constructor, we can use the `new` keyword followed by the constructor definition. Here's an example of a record with a constructor that validates the input values:

```FSharp
type Person = {
    name: string;
    age: int;
    member this.NameAndAge(n: string, a: int) =
        if a < 0 then invalidArg "age" "Age must be positive."
        { name = n; age = a }
}

let person = Person.NameAndAge("John", 30)
```

In this example, we defined a constructor called `NameAndAge` that takes two arguments: `n` for the name and `a` for the age. The constructor validates that the age is positive and creates a new instance of the record.