## Declare literal maps

It is possible to declare constants literal in this way.

```
romanNumeralDict := map[int]string{
  1000: "M",
  900 : "CM",
  500 : "D",
  400 : "CD",
  100 : "C",
  90  : "XC",
  50  : "L",
  40  : "XL",
  10  : "X",
  9   : "IX",
  5   : "V",
  4   : "IV",
  1   : "I",
}
```

### Maps

A`map`is an un ordered collection of key-value pairs. Maps are used to look up a value by its associated array.

```
var x map[string]int
x["question"] = 42
```

A very common way of using maps: as lookup tables or a dictionary.

