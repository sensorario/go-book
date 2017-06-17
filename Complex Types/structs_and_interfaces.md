# Structs and Interfaces

## Structs

Is a type that contains named fields.

```go
type Person struct {
  name string
  surname string
}
```

allow simple syntax

```go
type Person struct {
  name, surname string
}
```

Can be initialized empty.

```go
var simone Person
```

We can use `new` keyword to allocate memory.

```go
simone := new(Person)
```

But all this kind of initialization sets all values to zero. We can give each fields the initial value.

```go
simone := Person{name: "Simone", surname: "Gentili"}
```

But if we know all fields and the order, we can omit them.

```go
simone := Person{"Simone", "Gentili"}
```

We can access fields using `.` operator.

```go
simone.name
```

## Method

The difference between function and methods is that a method has a receiver. A receiver is a type.

```go
func (p *Person) completeName() {
  return p.surname + " " + p.name
}
```

## Interfaces

An interface is created using the type keyword, followed by name and interface keyword.

```go
type Person interface {
  surname() string
  name() string
  completeName() string
}
```



