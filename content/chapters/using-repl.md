---
title: "Using REPL"
date: 2023-01-22T22:01:29-03:00
draft: false
weight: 2
---

We'll have a lot of code examples along this tutorial, for better understanding we recommend you to use the REPL.

## What is REPL?

The REPL (Read-Eval-Print Loop) tool in F# allows users to quickly and easily test code snippets and evaluate expressions. This can be especially useful for new users, as it allows them to quickly experiment and learn the language without the need to write and run full-fledged programs. Additionally, the REPL provides immediate feedback, making it easier to identify and correct errors in code. Overall, the use of the REPL can greatly facilitate the learning process and make it more interactive and efficient.

## How to use it on terminal

You can use it on terminal, even in the integrated terminal of Visual Studio Code following this steps:

1. Open a terminal window and navigate to the directory where you want to run your F# code.
2. Type `dotnet fsi` to start the F# REPL. You should see the F# prompt, which is ">".
3. Type the code you want to execute and press "Enter". For example, to print "Hello, World!" to the console, type:
```fsharp
> printfn "Hello, World!";;
```
> Note that you need to use ";;" to indicate the end of the expression, which is different from the F# Interactive window in Visual Studio.

4. The F# REPL will evaluate the expression and return the result, just like in the F# Interactive window.

## How to use it on Visual Studio

You can use it on Visual Studio following this steps:

1. Open the F# Interactive window in Visual Studio by selecting "View" > "Other Windows" > "F# Interactive" or by using the keyboard shortcut "Ctrl+Alt+F"
2. Type the code you want to execute in the F# Interactive window and press "Enter". For example, to print "Hello, World!" to the console, type:
```fsharp
printfn "Hello, World!"
```
3. The F# Interactive will evaluate the expression and return the result, in this case it will print "Hello, World!" in the console.

## Script files

.fsx files are F# script files, which allow you to write and execute F# code without the need to create a full-fledged project or solution. These files are typically used for small, self-contained scripts or for prototyping and experimentation.

When you execute an .fsx file, the F# compiler will run through the code in the file and execute any statements or expressions that it contains. This allows you to write and run code snippets quickly, without the need to set up a full project or solution.

One of the main advantages of using .fsx files is that they allow for a more interactive and iterative development process. You can quickly test and experiment with different ideas, and make changes to your code without the need to rebuild a full project.

Additionally, .fsx files can be useful for automating tasks, such as data processing or code generation. You can write a script that performs a specific task, and then run it as needed to automate the process.

You can also use .fsx files in conjunction with the F# REPL, by using the "#load" command to load the script file and execute it. This allows you to test and run your code snippets interactively and to test your functions, modules and types before you include them in your project.

```fsharp
> #load "./your_script.fsx";;
```

Overall, .fsx files are a powerful tool that can greatly facilitate the development process in F# and make it more interactive and efficient.

