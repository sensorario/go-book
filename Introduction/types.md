# Types

Go basic types are the following:

 - bool
 - string
 - int
 - int8
 - int16
 - int32
 - int64
 - uint
 - uint8
 - uint16
 - uint32
 - uint64
 - uintptr
 - byte // alias for uint8
 - rune // alias for int32 represents a Unicode code point
 - float32
 - float64
 - complex64
 - complex128

In mathematic, similar types of numbers, corresponds to a set. Sets are similat to types in programming languages, because all the values of a particular type share certain properties.

Go is statically typed programming language. Variable always have a specific type and that type cannot change. Type help developer to know about what our program is doing and catch a wide variety of common mistakes.

## Strings

A String is a sequence of characters with a definite length. It is used to represent text. Go strings are made up of individual bytes, usually one for each character.

String literals can be created using double quotes or single quotws. Double quotes cannot contain special characters or escape sequences.

String are indexed starting from zero and not from one.

Concatenation is is made with + operator. Is the same addition symbol. Go compiler figures out what to do based on types of the arguments. Because both side of the + are strings, the compiler assumes you mean that you want a concatenation. Not an addition.

## Booleans

A boolean value is a particular integer that can assume only two values: 1 or 0. The former represent true value, and the latter false.

## Integer

Integers are numbers without a decimal component. Unlike base-10 decimal system we use to represent numbers, computers use a base-2 binary system. There are also three machine dependent integer types: uint, int, and uintptr. They are machine dependent because their size depends on the type of architecture you are using.

## Floating-point

Floating-point numbers are numbers that contain a decimal component. Go has two additional types for representing complex numbers: complex64 ans complex 128. Generally, we should stick with float64.