# Constants

Go also has support for constants. Constants are essentially variables whose values cannot be changed later. They are created in the same way you create variables, but instead of using the var keyword we use the const keyword.

## Types

Like variables, constant can be a value of different type. For example a character, a string, a boolean or a numberic value.

## Declaration

Unlike variables, constants cannot be declared using `:=` syntax. More constant can be delcaring omitting `const` for all constant.

```go
const (
  name := "Simone"
  surname := "Gentili"
)