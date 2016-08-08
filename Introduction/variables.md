# Variables

## Create new variable

A variable can be create using `var` keyword followed by variable name and type.

```go
var hello string
```

You cannot declare variable that you dont use inside your code. Could be a good idea create variables with an initializers.

### Variable with initializers

There are two ways to create a variable with an initializer.

```go
var varName string = "value"
```

When a variable initialized, we can omit the type.

```go
var varName = "value"
```

### Short variable declaration

We can also omit var keyword and just type variable with assignment. Creating a variable is so common that a shorter statement is available. Use shorten way whenever possible. The `:=` symbol is part of a *short variable declaration*. Is a statement that declares one or more variables. The statement gives them appropriate types based on the `initializer` values.

```go
varName := "value"
```

This is the most compact variable declaration. Use it within a function. Not for a package level variables.

### Zero values

A variable can be init as part of its declaration. We can declare a variable within its initializers and assign a value. But we can also declare variables without an explicit initial value. Go compiler will assign to the variable its zero value.

 - 0 for numeric types
 - false for the boolean type
 - "" (the empty string) for strings

## Scope

Go is lexically scoped using blocks. This means that the variable exists within the nearest curly braces ({}), or block. Including any nested curly braces, but not outside of them.


## Multiple variables

Variable can be delcare in different ways.

```go
var a = 5
var b = 6
var c = 42
```

Can be written also omitting var keyword for each statement.

```go
var (
  a = 5
  b = 6
  c = 42
)
```

The var statement could declare a list of variables instead of single one. When we compose function signature, type in argument can be omitted in all parameters but the last. Also in variable declaration Go leave this feature: when var is used to declare more variables, type should be in the last position.

```go
var a, b, c, d int
```