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



