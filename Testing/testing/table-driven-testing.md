## Table driven testing

In Go Programming Language is very common to write test _table-driven_. In other languages and/or test frameworks, like `phpunit` for php, exists something  similar and it is called "data provider". Instead of write more tests with different input/output, a table reuse same test with different sources. Or same test is used with different inputs and different outputs.

In this trivial example, we dont need to write two tests: we should write one single test, and iterate on it using a table. Add new line to the table as needed is straightforward.

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

## Example

```go
func TestMasterOrFeaturesBranchesAreDevelopment(t *testing.T) {
	tests := []struct {
		branch Branch
		phase  string
	}{
		{Branch{"feature/branch-semantico/master"}, "development"},
		{Branch{"hotfix/branch-semantico/master"}, "development"},
		{Branch{"release/branch-semantico/master"}, "development"},
		{Branch{"master"}, "development"},
		{Branch{"1.4"}, "production"},
	}

	for _, test := range tests {
		if got := test.branch.Phase(); got != test.phase {
			t.Errorf("Oops! Expected " + test.phase + " but got " + test.branch.Phase() + " using branch " + test.branch.branch)
		}
	}
}
```

In the real world example, developing `ff` I used this kind of test to detect branch phase during the gitflow. As you can see, here there are a slice of Branch objects and relative phase. Instead of write each tests separately, abstracting the concept is possible to reuse same test in different context. This reduce test's code to read and improve readability of tests.

