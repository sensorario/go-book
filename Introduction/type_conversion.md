# Type conversion

Sometimes we need to convert integers in strings or vice versa. Boolean in integer. Depending on the purpose of our program, sometimes we need to get a value of a variable, but in another format. Another *type*.

To convert a variable to another type, we can use type as function, passing variable to convert as argument.

```go
number := "56"
integer := int(56)
floatNumber := float64(integer)
```

In other languages assignment between different types automatically cast value. In Go this must be explicit.