# Count file lines

This program, counts the lines of count.go file. It uses `os.Open()` and `os.Close()` to open and close the file. Also, uses `bufio.NewScanner(fileHandler)` and retrieve a file content available for "`Scanner`". Instead `input.Scan()` read each lines of file.

```go
package main

import (
	"bufio"
	"fmt"
	"os"
	"strconv"
)

func main() {
	fileName := "count.go"
	lines := countLines(fileName)
	fmt.Println("File " + fileName + " has " + strconv.Itoa(lines) + " lines")
}

func countLines(fileName string) int {
	numberOfLines := 0
	fileHandler, _ := os.Open(fileName)
	input := bufio.NewScanner(fileHandler)
	for input.Scan() {
		numberOfLines++
	}
	fileHandler.Close()
	return numberOfLines
}
```