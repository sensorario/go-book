# Convert a struct to a string

```
package main

import (
    "fmt"
)

type Person struct {
    surname string
    name    string
}

func (p* Person) String() string {
    return p.surname + " " + p.name
}

func main() {
    sensorario := &Person{
        "Rario",
        "Senso",
    }
    fmt.Println(sensorario)
}
```



