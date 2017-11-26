# Array, Slices and Maps

## Arrays

An array is a numbered sequence of a single types. And has a fixed length. Like Strings, Arrays are indexed starting from 0. To declare a float64 variable you can use different syntaxes.

> Pay attention to the number between squared parenthesis: without this number you declare a slice. The difference between slices and array is in current book in Slices chapter.

Another way to define arrays is the following. Notice the extra trailing ,. Comma is required by Go. It allow easilly to remove an element from the array by commenting out the line.

```go
var x [3]float64{
  42,
  7,
  23,
}
```

To loop over a variable, you should use range keyword.

```go
package main

import "fmt"

func main() {
        var x [3]float64

        x[0] = 42
        x[1] = 7
        x[2] = 23

        var total float64 = 0

        for _, value := range x {
                total += value
        }

        fmt.Println(total)
}
```

The underscore`_`tells to the Go compiler that we dont need any iterator variable.

## Slices

A slice is a segment of an array. Like array are indexable. But unlike arrays, the length is mutable. In delcaration, the difference is in the missing length:

```go
var x []float64
```

If we want to create a slice, we should use `make` function.

```go
var slice := make([]float64, 5)
```

Make function accept two parameters: the type of the slice and the lenght.

Another way to create a slice is to use \[low:high\] expression. `low` is the index of where to start. `high` is the index of where to end it. One or both are not mandatory. Omitting one value, is legal. Omitting low means that slice starts from zero. Omiting high means that slice starts from the last element.

### Append

Append adds elements onto the end of the slice.

```go
func main() {
  slice := []int{42, 23}
  slice_two := append(slice, 7) // 42, 23, 7
}
```

### Copy

Copy takes two arguments and copy the second to the first.

