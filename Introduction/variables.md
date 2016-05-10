# Variables

## Create new variable

There are two ways to create a variable. Creating a variable is so common that a shorter statement is available.

```go
var varName string = "value"
```

The shorten way should be used whenever possible.

```go
varName := "value"
```

## Scope

Go is lexically scoped using blocks. This means that the variable exists within the nearest curly braces ({}), or block. Including any nested curly braces, but not outside of them.

## Constants

Go also has support for constants. Constants are essentially variables whose values cannot be changed later. They are created in the same way you create variables, but instead of using the var keyword we use the const keyword.

## Multiple variables

```go
var (
  a = 5
  b = 6
  c = 42
)
```