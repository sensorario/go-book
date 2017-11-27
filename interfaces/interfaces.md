# Interfaces

In go interfaces are implicit. To implement an interface in go, we just need to implement all method of that interface.

## Example

Here an example of declaration of an interface.

```go
type foo interface {
    fizz()
    buzz()
}
```

Now, we can create a new struct.

```go
type example struct {
}
```

Until now, this is just a struct. In the next section of code, we have two functions. The former is a function that accept as argument an object that implement foo interface. But `example` have no methods. If we try to build this code?

```go
func woof(i foo) {
        fmt.Println("Yay!")
}

func main() {
        o := example{}
        woof(o)
}
```

Trying to build previous section of code happens that `go build` command says that cannot use type `example` as type `foo`. In fact, `example` does not implement yet `fizz()` nor `buzz()` methods.

```
$ go build
# _/Users/sensorario/work/src/github.com/sensorario/interfaces
./main.go:25:6: cannot use o (type example) as type foo in argument to woof:
        struttura does not implement foo (missing fizz method)
```

Two empty methods are enough.

```go
func (s example) fizz() {

}

func (s example) buzz() {

}
```

Now our program compile and this the output:

```go
$ go run *.go
Yay!
```

## Stringers

In `fmt` package there is `Stringer` interface. An object that implement this interface can describe itself as a string. Let's try to use `fmt.Println(o)` with a struct that don't implement Stringer interface.

```go
package main

import "fmt"

type example struct {
}

func main() {
        o := example{}
        fmt.Println(o)
}
```

`Println()` method know how to build the struct. The program can be builded. We can run it and see the following output.

```go
$ go run *.go
{}
```

Now we'll add Stringer interface just with this snipped of code:

```go
func (e example) String() string {
        return "Yay!"
}
```

Et voila!

```
$ go run *.go
Yay!
```

Here the complete source of the example:

```go
package main

import "fmt"

type example struct {
}

func (e example) String() string {
        return "Yay!"
}

func main() {
        o := example{}
        fmt.Println(o)
}
```



