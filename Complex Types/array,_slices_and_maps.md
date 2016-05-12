# Array, Slices and Maps

## Arrays

An array is a numbered sequence of a single types. And has a fixed length. Like Strings, Arrays are indexed starting from 0.

To convert between types, you use type name like a function.

To loop over a variable, you should use range keyword.

```go
var x [3]float64

x[0] = 42
x[1] = 7
x[2] = 23

var total float64 = 0
for -, value := range x {
  total += value
}
```

The underscore `_` tells to the Go compiler that we dont need any iterator variable.

Another way to define arrays is the following. Notice the extra trailing ,. Comma is required by Go. It allow easilly to remove an element from the array by commenting out the line.

```go
var x [3]float64{
  42,
  7,
  23,
}
```