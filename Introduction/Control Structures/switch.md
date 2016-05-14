# Switch

Like **if** and **for**, **switch** statements has an init statement.

```go
switch os := 3; os % 2{
    case 1:
        fmt.Println(os + " is odd")
    case 0:
        fmt.Println(os + " is even")
}
```