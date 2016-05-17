# Testing

Go compiler ignore file that ends with `_test.go`. The code inside this files, is considered by **go test** command. All files whose name ends with `_test.go` are not considered part of the package using **go build**. Are part of it, instead, using command `go test`.

But all `_test.go` files are not only for test purpose. Can also contain benchmarks and examples. Test function is the effective test code. This kind of function is called by command `go test` that reports the result. Function should return PASS or FAIL. Generally FAIL means that `t.Error()` function is called.

Running `go test` tool, all `_test.go` files are scanned for all function whose names starts with Test. It generate a temporary main package that calls all of them. Command build all functions. Run all the code. Finally report the result. After execution clean up all temporary code.

## Write first test

To create a test suite, we need to import special **testing** package. All test file must import this package. All functions that stats with Test are considered our tests. `Test` prefix is followed by an optional suffix. Suffix name must starts with capital letter. Name should describe what test is written for.

```go
func TestSomething(t *testing.T) {
  // ...
}
```

To signal error to *go test* program, we can use t.Error function. There is also an `Errorf` function. It has the same behavior of `Printf` one.

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

Test should be written before production code. This practice is called *test first*. This makes developer confident that whatever fix this test, is carefully descrive with a good `t.Error` message. This can also help to fix bugs and errors quickly.