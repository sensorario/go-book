# Concurrency

In this chapter I introduce concurrency with go. Concurrency allow more than one task to progress simultaneously. Go has rich support for concurrency. Tools that Go provide are _channels_ and _goroutines_.

## Goroutines

A gorouting can run concurrently with other functions. To call a goroutine, is necessary `go` keyword.

```go
go functionName()
```

When a function is called, it's code is executed before the program come back to the main. With a go routine, we return to next line. We dont wait for function execution.

