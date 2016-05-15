# Switch

A switch statement starts with `switch` keyword, followed by an expression. The rest of the switch statement is a block of cases. Expression is compared with all cases. Is executes only the first one that succeed. Also a default case could be added.

```go
three := 3
switch three%2 {
case 1:
  fmt.Println(three + " is odd")
case 0:
  fmt.Println(three + " is even")
default:
  fmt.Println("this should never ever appear!!!")
}
```

Like **if** and **for**, **switch** expression has an init statement thus you can rewrite same code in a shorten syntax. You can remove one line, avoiding the initialization statement line.

```go
switch os := 3; os % 2 {
case 1:
  fmt.Println(os + " is odd")
case 0:
  fmt.Println(os + " is even")
default:
  fmt.Println("this should never ever appear!!!")
}
```