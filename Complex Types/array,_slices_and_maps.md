# Array, Slices and Maps

## Arrays

An array is a numbered sequence of a single types. And has a fixed length. Like Strings, Arrays are indexed starting from 0. To declare a float64 variable you can use different syntaxes. This because length in arrays is immutable and cannot change.

> To check the size of an array or a slice you can use len\(x\) function
>
> Pay attention to the number between squared parenthesis: without this number you declare a slice. The difference between slices and array is in current book in Slices chapter.

Another way to define arrays is the following. Notice the extra trailing "," comma is required by Go.

```go
var x [3]float64
x[0] = 42
x[1] = 7
x[2] = 23

var x [3]float64{
  42,
  7,
  23,
}

x := [3]float64{42, 7, 23}
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

A slice is a segment of an array. Like array are indexable. But unlike arrays, the length is mutable. In declaration, the difference is in the missing length:

```go
var x []float64
```

If we want to create a slice, we could use `make` function or other idiomatic ways.

```go
var slice := make([]float64, 5)

var slice := []float64{1, 2, 3, 4, 5}

slice := []float64{1, 2, 3, 4, 5}
```

Make function accept two parameters: the type of the slice and the lenght.

Another way to create a slice is to use \[low:high\] expression. `low` is the index of where to start. `high` is the index of where to end it. One or both are not mandatory. Omitting one value, is legal. Omitting low means that slice starts from zero. Omiting high means that slice starts from the last element. In the followin g block of code you can find a complete sequence of slice:

```go
s := []float64{42, 7, 23}

fmt.Println(s[:]) // [42, 7, 23]

fmt.Println(s[1:]) // [7, 23]
fmt.Println(s[2:]) // [23]
fmt.Println(s[3:]) // []

fmt.Println(s[:1]) // [42]
fmt.Println(s[:2]) // [42, 7]
fmt.Println(s[:3]) // [42, 7, 23]

fmt.Println(s[1:1]) // []
fmt.Println(s[1:2]) // [7]
fmt.Println(s[1:3]) // [7, 23]
```

### Append

Append adds elements onto the end of the slice.

```go
func main() {
  slice := []int{42, 23}
  slice = append(slice, 7) // 42, 23, 7
}
```



