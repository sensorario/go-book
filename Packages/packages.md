# Packages

Each Go program is composed by packages. Program are executed in main package. We can import other packages with `import` keyword followed by package name. If we need to format some string, we should need to import "fmt" package. If we need to generate random values "math/rand". And so on.

Package name is the same of last item of importantion path. This means that if we import `a/b/c/d` package, its name will be considered `d` inside the code.

## Imports

Packages are very important tools to apply Dont Repeat Yourself principle. Packages promote the reuse of code. Following program needs the value of Pi. It is provided by math library. Instead, fmt library provide Println method to show in standard output a string. To work with this fmt.Println and math.Pi (method and constant), we need to import their rispective packages.

```
package main

import (
	"fmt"
	"math"
)

func main() {
	fmt.Printf("Pi value is %g", math.Pi)
}
```

## Exported names

Both Pi and Println have a name that starts with a capital letter. When variable or function names starts with a capital letter are exported. And when something in exported from current package, means that is visible from others. Obviously, unexported names are not accessible from other packages.

    Exercise:
    Try to access to an unexported names.