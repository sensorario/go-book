# Command-Line

This is a very little example that read a string value from console. The syntax to send to this program is

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

