# Functions

A function is a section of code that maps zero or more input parameters to zero or more output parameters. Stars with keyword `func` followed by function's name. Agter function's name, are defined parameters defined by name and type. After parameters, there is the return type. Function name, parameters and return type are knowns as *function's signature*.

Variable must be passed to the function. Depending on the function position. If the `scope` of the variable is the same of the function, function can access to the variable. Must be passed instead.

Function form call stacks: each time a function is called, we push it onto the call stack. Each time we return from a function, we pop the last function from that stack.

Return types can have a name.

```go
func function() (result int) {
  result := 42
  // some other code here
  return
}
```

Multiple values can be returned.

```go
func completeName() (string, string) {
  return "Simone", "Gentili"
}
```

### Parameters

Function can have zero or more parameters. In this example we have zero parameters in main function. But also two parameters in sum function.

```go
package main

import "fmt"

func sum(firstAddend int, secondAddend int) int {
	return firstAddend + secondAddend
}

func main() {
	fmt.Println("Sum is " + string(sum(42, 13)))
}
```

### Type omission

When two or more parametr has the same type, you can omit all but the last. Go undertand type when omitted in this case. This may be not good for the readability of the code.

### Return

A function can return any nymber of variable. Here an example, where a function returns same variable taken in input.

```go
func doNothing(x, y int) (int, int) {
	return y, x
}
```

### Named returned value

Value returned can be named. This means that we must just set them inside the function. To return them we just need to declare what function want return. Finally, once variable are valorized, we can just use return statement.

```go
func sum(a, b int) (result int) {
	result = a + b
	return
}
```

When return is called, Go autmatically knwos that variable to return is the `int` variable called `result`.

## Closure

It is possible to create a function inside a function.

```fo
func function() func() int {
  return func() (ret int) {
    ret := 77
    return
  }
}
```

## Defer

Go has a special statement called `defer` that schedules a function call to be run after function completes. `defer` is often used when resources need to be freed.

## Pointers

A pointer is represented using an asterisk followed by the type of the stored value. We use & operator to find the address of a variable.
