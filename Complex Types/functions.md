# Functions

A function is a section of code that maps zero or more input parameters to zero or more output parameters. Stars with keyword `func` followed by function's name. Agter function's name, are defined parameters defined by name and type. After parameters, there is the return type. Function name, parameters and return type are knowns as *function's signature*.

Parameters namex ca be different when a function is called.

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

## Variadic functions

////// Variadic

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

## Defer, panic and recover

Go has a special statement called `defer` that schedules a function call to be run after function completes. `defer` is often used when resources need to be freed.

////// panic and recover

## Pointers

A pointer is represented using an asterisk followed by the type of the stored value. We use & operator to find the address of a variable.

### New

Funftion `new` takes a type as argument. It allocate memory for the type, and return a pointer to it. In other languages we need to free memory. Go is a garbage-collected language. This means that is cleaned up memory automatically when nothing refers to it.