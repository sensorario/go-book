# Getting started

## Environment

The go toolset uses an environment variable called GOPATH to find source code. GOPATH variable must be configured in your system before start.

### OS X

Update your `~.bash_profile` and enter this instruction:

    echo 'export GOPATH=$HOME\n' >> ~/.bash_profile
    
To check where is your GOPATH, open your terminal and enter the following:

    env
    
This will display your GOPATH value.

## Whitespaces

Are newlines with special or several characters. Newlines, spaces, and tabs are known as whitespaces. Whitespaces cannot be seen. Although whitespaces are useful to make programs easier to read, go doesnt care about them.

## Comments

A comment are those lines that starts with `//`. Comments are ignored by go compiler. Go supports two different styles of comments: `//` and `/* */`. The former is an inline comment, the latter consider a comment everything between `/*` and `*/`.

## How programs begin

All Go programs begins with *package declaration*. Every Go program must start with it. Package Declaration is the way go orgnize and reuse code. There are two way of programs: libraries and executable. Executable applications are those programs that we can start from terminal. Libraries are those collections of code that can be reused. The package fmt starts with *package fmt*.

## Use functions in packages

This is a simple program written in go. It is composed by package declaration, one import and a function. This program uses *Println* function from package fmt. To use this function we needed to import fmt package with `import "fmt"` instruction. And then to use Println function of this package we needed to use statement `fmt.Println()`.

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello, world!!")
}
```

How to use Exit function from os package? Let me check documentation with `godoc` instruction:

    $ godoc os Exit
    func Exit(code int)
        Exit causes the current program to exit with the given status code.
        Conventionally, code zero indicates success, non-zero an error. The
        program terminates immediately; deferred functions are not run.

Here the example that creates an application without output that ends with success.

```go
package main

import "os"

func main() {
	os.Exit(0)
}
```