# Testing {#testing}

This chapter is not about testing in general. This chapter is about testing with go. In go we can execute our program running `go run` command. But we have to know that`go run` ignore file that ends with `_test.go`. The code inside this files, is considered by **go test** command. All files whose name ends with `_test.go` are not considered part of the package using **go build**. Are part of it, instead, using command `go test`. Files whose names begin with "\_" are ignored.

But all `_test.go` files are not only for test purpose. Can also contain benchmarks and examples. Test function is the effective test code. This kind of function is called by command `go test` that reports the result. Function should return PASS or FAIL. Generally FAIL means that `t.Error()` function is called.

Running `go test` tool, all `_test.go` files are scanned for all function whose names starts with Test. It generate a temporary main package that calls all of them. Command build all functions. Run all the code. Finally report the result. After execution clean up all temporary code.

## Write first test

To create a test suite, we need to import special **testing** package.

```go
import "testing"

import (
    "testing"
)
```

All test file must import this package. All functions that stats with Test are considered our tests. `Test` prefix is followed by an optional suffix. Suffix name must starts with capital letter. Name should describe what test is written for.

```go
func TestSomethingMustHappen(t *testing.T) {
  // ...
}
```

To signal error to _go test_ program, we can use t.Error function. There is also an `Errorf` function. It has the same behavior of `Printf` one.

Here an empty example that shows minimal statements of a testing package. This code just import _testing_ package, and create a TestSomething. Actually this test just show an error message.

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

Test should be written before production code, following the test driven development methodology. This practice is called _test first_. This makes developer confident that whatever fix this test, is carefully descrive with a good `t.Error` message. This can also help to fix bugs and errors quickly.

## Usage

```
usage: go test [-c] [-i] [build and test flags] [packages] [flags for test binary]
```

When executed, `go test` print prints a summary of the test results.  in the format:

```
PASS
ok _/path/to/package 0.052s
```

By default, go test needs no arguments, but the flags handled by 'go test' itself are:

```
-c
    Compile the test binary to pkg.test but do not run it
    (where pkg is the last element of the package's import path).
    The file name can be changed with the -o flag.

-exec xprog
    Run the test binary using xprog. The behavior is the same as
    in 'go run'. See 'go help run' for details.

-i
    Install packages that are dependencies of the test.
    Do not run the test.

-o file
    Compile the test binary to the named file.
    The test still runs (unless -c or -i is specified).
```

## Table driven testing

In Go Programming Language is very common to write test _table-driven_. In other languages and/or test frameworks, like `phpunit` for php, exists data providers. Instead of write more tests with different input/output, a table reuse same test with different sources. In this trivial example, we dont need to write two tests: we should write one single test, and iterate on it using a table. Add new line to the table as needed is straightforward.

```go
package main

import "testing"

func Double(input int) int {
        return input * 2
}

func TestTableDriven(t *testing.T) {
        var tests = []struct {
                input  int
                output int
        }{
                {2, 4},
                {5, 10},
        }

        for _, test := range tests {
                if got := Double(test.input); got != test.output {
                        t.Error("Double(%d) = %d", test.input, got)
                }
        }
}
```



