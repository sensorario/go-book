# Structs

This is a simple way to declare an array of items.

```
var content := []struct {
    foo int
    bar string
}{
    {42, "the answer"},
    {0, "non divisible number"},
    {2, "parents"},
}
```

This syntax is very useful in [table driven testing](/Testing/testing/table-driven-testing.md).

