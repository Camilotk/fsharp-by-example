---
title: "Hello World in F#"
date: 2022-11-10T10:31:11+03:00
draft: false
---

## Hello World

The first program that anyone will always do first when starting to learn a new programming language is a program that prints "hello world" in a terminal. We'll do that for practice, to get used to the language and environment.

## What you will need for this?

- F# installed on your machine, if you don't have it yet, [this link](https://learn.microsoft.com/en-us/dotnet/core/install/) will help you.
- A UTF-8 compatible text editor for you to edit the code, if you don't have any preference we recommend [Visual Studio Code](https://code.visualstudio.com/download).
- Know how to use the terminal in your operating system, and how to navigate around it.

## Create the project

We will create a console project to do this. To do it we will enter to the folder in our terminal where we want to create this project and enter the command.

```
> dotnet new console -lang F# -o Hello
```

> The `>` marker is to indicate that this command should be run on terminal. It's the same as `$` for Linux and Mac. 

This will create a folder "Hello" with our main project. Inside this folder we will have two files:
- **Hello.fsproj**: That contains the project configuration.
- **Program.fs**: That contains our F# code.

If we open the "Program.fs" file we will see:
{{< highlight "fsharp" >}}
// For more information see https://aka.ms/fsharp-console-apps
printfn "Hello from F#"
{{< / highlight >}}
And that's the code that prints "Hello from F#" in console! The "Hello World" program is also the example of code of every new F# project.

### Understanding this code

The first line is a comment, which means that the rest of the code in the line will not be executed. Any code in a line starting with  `//` or between `(* ... *)` is ignored and not executed. We use it to add information about the code for other programmers that will eventually work in this code. In this case, a message from Microsoft about where we can find more information about console apps.

The second line starts with a function. For now, you can think of it as "commands" as we'll see it next. The `printfn` function receives a message in String (any text between `"..."`) and prints it in console.

### Changing the program

As we don't need the comment since it will not be executed, we can just delete this line. And, as we want to print "Hello World" and not "Hello from F#!", we can change the value to get what we want.

Change **Program.fs** to:

{{< highlight "fsharp" >}}
printfn "Hello World"
{{< / highlight >}}


## Compiling the project

After changing the message and before we execute our program, we have to compile it. You can think of compilation as the process that translates your code into code that the computer understands. To do this, just run the command in your terminal:
```
> dotnet build
```
**For linux users:**
<details>
Add to your .bashrc the flag `export DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=1` in case of some error at build process.
</details>

## Run the project

Now we can run the project, for do it just enter in your terminal the command:
```
> dotnet run
```

And you should see "Hello World" printed in your terminal.

**Congratulations!** You done your first F# program.

## Going to the next level

We did the "Hello World" program, but now we can upgrade it to display "Hello" for any value so it would work with "from F#" or "World" as we want. To do this we will change the `printfn` function to print formatted text passing a specifier that will be replaced for the message we want.

So we'll change our **Program.fs** to:
{{< highlight "fsharp" >}}
printfn "Hello %s" "World"
{{< / highlight >}}

And then build and run it again!

Now if we want "from F#" instead "World" we can change to:
So we'll change our **Program.fs** to:
{{< highlight "fsharp" >}}
printfn "Hello %s" "from F#"
{{< / highlight >}}


Now, if we build and run again, we should see the original message.

### A taste of a statically typed language

F# is different from how some other languages works with Types. This means that each piece of information has to be from the expected type in order to work. For example, the `%s` specifier expects a `String` type (a message between `"..."`) if we try to pass a number, for example `42`, we will get an error.

Try doing this, passing 42 as the message:
{{< highlight "fsharp" >}}
printfn "Hello %s" 42
{{< / highlight >}}


If you try to build this program, you'll get the error:
 ```
 error FS0001: This expression was expected to have type    
 'string'    
 but here has type    
 'int' [.../Hello/Hello.fsproj]
```

The error message is telling us that we should pass a "String" for this function, but we're passing an "int" (an "Integer" number). Our program didn't even produce a new build. We will only be able to execute the code when we fix it by passing the correct value.

This will help us to avoid mistakes and errors in our programs. By checking all our errors and enforcing each command to receive the correct parameters, F# will help us to write programs that have less bugs and errors.
