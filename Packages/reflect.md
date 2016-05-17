# Package reflect

Go Programming language provide a library for the reflection. Go `reflect` package has some useful methods. For example methods that provide type object information.

```go
package main

import (
  "fmt"
  "reflect"
)

type anObject struct {
}

func main() {
  var anObject anObject
  fmt.Println(reflect.TypeOf(anObject).Name()) // will return "anObject"
}
```