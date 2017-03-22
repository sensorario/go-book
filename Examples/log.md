# Log

Log with date and time and log without.

```go
package main

import (
	"log"
	"os"
)

func main() {
	logger := log.New(os.Stdout, "", 0)
	logger.Print("foo bar")
	anotherLogger := log.New(os.Stdout, "", log.LstdFlags)
	anotherLogger.Print("foo bar")
}
```



