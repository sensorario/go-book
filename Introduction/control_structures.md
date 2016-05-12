# Control Structures

## For

For statements allows developer to repeate a list of statements. The following is the shorter syntax.

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

## If

An if statement is similar to a for: it has a condition followed by a block. When condition is verified (it returns true) following block is executed.

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


## Switch

