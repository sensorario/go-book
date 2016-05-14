# Packages

Each Go program is composed by packages. Program are executed in main package. We can import other packages with `import` keyword followed by package name. If we need to format some string, we should need to import "fmt" package. If we need to generate random values "math/rand". And so on.

Package name is the same of last item of importantion path. This means that if we import `a/b/c/d` package, its name will be considered `d` inside the code.