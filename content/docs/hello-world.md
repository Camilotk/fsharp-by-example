---
title: "Hello World in F#"
date: 2020-11-10T08:47:11+01:00
draft: false
---

## Hello World
Para começar, vamos fazer o tradicional programa 'Hello World', bem simples utilizando qualquer editor texto que suporte UTF-8 e um terminal.
```F#
printfn "Hello %s" "World"
```
Após criarmos esse programa, podemos abrir o REPL de F# usando o comando:
**Windows:**
```powershell
fsc Hello.fs
./Hello.exe
```
**Linux:**
```bash
export DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=1
dotnet new console -lang F# -o Hello
cd Hello
vim Program.fs
dotnet build
dotnet run
```
Importante notar que a interpolação de String "%s" acontece fazendo "World" ser colocado no seu lugar, como %s espera um valor do tipo String, se mudarmos nosso códgo para:
```F#
printfn "Hello %s" 42
```
E tentarmos compilar vamos receber um erro de tipo
 ```error
 error FS0001: This expression was expected to have type    
 'string'    
 but here has type    
 'int' [/home/ccazevedo/FS/Fundamentals/A1/Hello/Hello.fsproj]
```
Isso acontece por que até mesmo a interpolação de Strings possui checagem estática, o que demonstra o poder de checagem do compilador de F#

