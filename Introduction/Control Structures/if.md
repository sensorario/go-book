# If

An if statement is similar to a for: it has a condition followed by a block. When condition is verified (it returns true) following block is executed. Condition does not require ( ) braces. Code to be executed after the condition is verified must be surrounded by { }.

```go
if true {
  // execute me
}
```

We can have more if statements. Each onw is checked top down. The first one that result true will cause the run of following block.

```go
if true {
  // execute me
} else if true {
  // execute me
} else {
  // execute me
}
```

If statement can execute a little statement before the condition. The scope of variable create here is just the if scope.