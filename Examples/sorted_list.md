# Sorted list

The following is a simple example that show how to interact with a sort package. We will use sort.Sort method. We cannot use List(list) (type List) as type sort.Interface in argument to sort.Sort, until until we have not yet implemented some methods.

    func Sort(data Interface)
        Sort sorts data. It makes one call to data.Len to determine n, and
        O(n*log(n)) calls to data.Less and data.Swap. The sort is not guaranteed
        to be stable.
     
We are going to play with lists of node. We we'll need Node elemente that espose Value property. This value will be an integer. The purpose of this example is to create a sorted list of integers. First of all, a list of types that we need to create. The type Node, and a collection of Node: List.

```go
type Node struct {
	Value int
}
type List []Node
```

As said in the introduction, sort.Sort accept only object that implements some methods:

- Len
- Less
- Swap

```go
func (list List) Len() int {
	return len(list)
}

func (list List) Less(i, j int) bool {
	return list[i].Value < list[j].Value
}

func (list List) Swap(i, j int) {
	list[i], list[j] = list[j], list[i]
}
```

We will add some integers to our List collecion of Node elements.

```go
func main() {
	list := []Node{{42}, {7}, {23}}
	sort.Sort(List(list))
	fmt.Println(list) // [{7}, {23}, {42}]
}
```

Complete example

```go
package main

import (
	"fmt"
	"sort"
)

type Node struct {
	Value int
}

type List []Node

func (list List) Len() int {
	return len(list)
}

func (list List) Less(i, j int) bool {
	return list[i].Value < list[j].Value
}

func (list List) Swap(i, j int) {
	list[i], list[j] = list[j], list[i]
}

func main() {
	list := []Node{{42}, {7}, {23}}
	sort.Sort(List(list))
	fmt.Println(list)
}
```