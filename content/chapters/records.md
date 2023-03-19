---
title: "Records"
date: 2023-03-18T19:44:59-03:00
weight: 29
---

Records are similar to tuples in that they are used to group related values together. However, unlike tuples, records allow you to name the fields, which can make the code more readable and maintainable. In F#, records are defined using the type keyword, followed by the record name and the field names and types inside curly braces.

Here's an example of a record definition for a person:

```FSharp
type Person = {
    Name : string
    Age : int
}
```

You can create an instance of a record by specifying the field names and values, separated by commas and enclosed in curly braces:

```FSharp
let person = { Name = "Eduardo Rafael"; Age = 24 }
```

To access the fields of a record, you can use dot notation followed by the field name:

```FSharp
person.Name // => "Eduardo Rafael"
person.Age // => 24
```

Records can also have optional fields and mutable fields. Optional fields are indicated by a question mark after the field name, and mutable fields are indicated by the mutable keyword before the field name:

```FSharp
type Person =
    { Name : string
      Age : int
      mutable TwitchLink : string option }

let mutablePerson = { Name = "Eduardo Rafael"; Age = 24; TwitchLink = Some "https://www.twitch.tv/eduardorfs" }
mutablePerson.Address <- None
```

Records can also be used as function parameters and return types, which can make it easy to work with structured data:
```FSharp
let getFullName { Name = first; LastName = last } =
    sprintf "%s %s" first last

let person = { Name = "Eduardo Rafael"; LastName = "da Silva" }
let fullName = getFullName person

// Output: "Eduardo Rafael da Silva"
```

Records are a powerful tool for organizing related data in F#. They allow you to name fields, which can improve code readability, and they can be used as function parameters and return types.


