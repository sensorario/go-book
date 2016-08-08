# Command-Line

## Read from command line

This is a little example that read a string value from console. The syntax to send to this program is

    $ go run console.go -foo=42

And the program will output `foo` value.

```go
package main

import (
	"flag"
	"fmt"
)

func main() {
	read := flag.String("foo", "bar", "the foo value")
	flag.Parse()
	fmt.Println(*read)
}
```

## Print command line arguments

Here we introduce the `os` package. This package provides functions and other values for dealing with the operating system. Command line arguments are available in a variable names `Args`.

First element of this variable is the name of the command itself. Other elements are the arguments presented to the program when it started.