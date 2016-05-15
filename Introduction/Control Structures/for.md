# For

For statements allows developer to repeate a list of statements. The following is the shorter syntax. And this is the only loop statement provided by Go Programming Language.

```go
i := 1
for i <= 10 {
  // do something
  i++
}
```

Another syntax is the following

```go
for i := 1; i <= 10; i++ {
  // do something
}
```

Other programming languages have different loops. For example while do, do while, until, foreach, ... Go, instead, has only one loop form: for.

For loop has three components. Each components is separated by semicolons. Three parts are initialization, condition and post statement. Init statement, is executed before first iteration. After initialization we have condition. The condition is evaluated before every interation. And at the end of an iteration is executed also post statement.

In other languages, parentheses surrounds three components. In Go Programming language there are no parenthesis. In other languages { } are not mandatoru. In Go Programming Language are always required.

Loop iterate until the condition return false. Condition must be a boolena expression like `i <= 10`.

Three elements are not all mandatory. For example you can omit init and post statement.

```go
i := 1
for ; i < 42; {
    i += i
}
```

In this case semicolon can be omitted

```go
i := 1
for i < 42 {
    i += i
}
```

When you omit everything, you obtain an infinite loop.

```go
for {
    // code for the loop
}
```

## Range

Go programming language, provide a keyword to iterate an array. Using `range` followed by the name of the variable we want to loop over, we can iterate for all its items.

```go
names := [2]string{
  "Simone",
  "Gentili",
}

for name = range names {
  fmt.Println(name)
}
```