# Hello world

This is the simplest example yuo can see in this examples chapter. This is just an hello world program written in go. But this program has a particularity: it contains special characters: "世界".

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, 世界")
}
```

## Imports

The import part, load packages used inside the main function. This section must contain only used packages. Unused packages will cause a build error.

## Main function

Main package must contain a main function. This is the entry point of go programs. If the project not contains main function, maybe the project is a library. To execute library code you need a main function or a test that can execute it.

