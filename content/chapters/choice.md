---
title: "Choice"
date: 2023-05-27T19:43:08-03:00
weight: 45
---

The Choice type is built to represent mutually exclusive possibilities. It contains two alternatives that represent the choice between two types. The value can be of either the first type or the second type. The Choice type is commonly used to represent a result that can be an error.

The Choice type in F# allows us to represent choices between two or more mutually exclusive alternatives. It is implemented using discriminated unions, where each alternative represents a different possibility. The value stored within a `Choice` type can be of either the first alternative type or the second alternative type.

For instance, let's consider a simple example where we have a function **validateEmail** that checks the validity of an email address:

```Fsharp
let validateEmail (email: string) =
    let isEmailValid =
        email.Contains("@") && email.Contains(".")
    
    if isEmailValid then
        Choice1Of2 true
    else
        Choice2Of2 "Invalid email. Check if the email contains '@' and '.' symbols."
```
In the above example, the **validateEmail** function returns a `Choice<bool, string>`. It can either return a `bool` value (`Choice1Of2`) representing a valid email or a `string` value (`Choice2Of2`) containing an error message indicating the reason for the invalidity.

This can be called as:
```FSharp
validateEmail "info@fsharp.org" // will return => Choice1Of2 true
validateEmail "contact@fsharp"  // will return => Choice2Of2 "Invalid email. Check if the email contains '@' and '.' symbols."
```

The `Choice` type in F# supports up to seven different alternatives: `Choice1Of2` to `Choice7Of7`. This flexibility allows us to represent a wide range of possibilities and choices in our code. Whether it's representing different result types or managing complex decision trees, the `Choice` type provides a versatile solution.

## Uses

The `Choice` type can be useful in the following scenarios:
- **Error Handling**
    > The Choice type provides a structured approach to error handling. Instead of relying on exceptions, which can disrupt the flow of functional programming, we can use the Choice type to encapsulate both successful and erroneous outcomes. This allows functions to return a result or an error message explicitly.
- **Multiple Possible Results**
    > When a function can have multiple possible return values, and these values are mutually exclusive, the Choice type provides an elegant solution. It eliminates the need for separate nullable types or complex conditional statements. By utilizing the Choice type, we can encapsulate the possible results in a more structured and type-safe manner.
- **Pattern Matching**
    > The Choice type works seamlessly with pattern matching in F#. Pattern matching enables us to handle each possible outcome of a Choice value and perform appropriate actions based on the specific case. This feature allows for concise and expressive code when dealing with mutually exclusive possibilities.