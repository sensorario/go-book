# Testing

Go compiler ignore file that ends with `_test.go`. The code inside this files, is considered by **go test** command.

To create a test suite, we need to import special **testing** package. All functions that stats with Test are considered our tests.

To signal error to *go test* program, we can use t.Error function.

Here an empty example that shows minimal statements of a testing package. This code just import *testing* package, and create a TestSomething. Actually this test just show an error message.

```go
package test

import (
	"testing"
)

func TestSomething(t *testing.T) {
	t.Error(
		"Some error occurs",
	)
}
```