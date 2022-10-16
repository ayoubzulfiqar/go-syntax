# ![GO Syntax](https://drive.google.com/uc?export=view&id=1uN6mkxzpGQoF0ATiFkGtu4KpKnqb3T8r)

- Go is an open source programming language supported by Google
- Easy to learn and get started with
- Built-in concurrency and a robust standard library
- Growing ecosystem of partners, communities, and tools

## Variables

```go
// Global variables

var Integer int = 34
var Float32 float32 = 34.54
var isBoolean bool = true || false
var String string = ""

// Direct Declaration
func main() {
    // this type of declaration only work inside functions. No Global values
	item, price, quantity, isStock := "Mobile", 2000, 50, true
    println(item, price+quantity, isStock)
}

// Group of Variables - These have a global Scope
var (
   // access them inside a function
	product  string  = "Mobile"
	quantity int     = 50
	price    float32 = 50.50
	inStock  bool    = true || false
)
```

## Constants

Constants are constants with fix value which can not be changes later. They can't be used inside a functions. Only globally available. but you can access them inside a functions

```go
// Global Scope
const pricing int = 34
const name string = "Name"
const age float32 = 53.23
const isValue = true || false

// OR

const (
	Pricing int     = 34
	Name    string  = "Name"
	Age     float32 = 53.23
	IsValue         = true || false
)
```

## Data Types

Go is a statically typed programming language. This means that variables always have a specific type and that type cannot change. The keyword var is used for declaring variables of a particular data type. Here is the syntax for declaring variables:

```go
var StringType string = "StringType"

// Int types can  have negative values
var IntegerType int = 23
var IntegerType8 int8 = 43
var IntegerType16 int16 = -34
var IntegerType32 int32 = 345
var IntegerType64 int64 = -54

// uInt can't have negative values
var UintegerType uint = 23
var UintegerType8 uint8 = 43
var UintegerType16 uint16 = 34
var UintegerType32 uint32 = 345
var UintegerType64 uint64 = 54

// bool type

var isReallyBoolean = true || false

// float type

var FloatType32 float32 = 345.8
var FloatType64 float64 = -54.5
```

## Operators

An operator is a symbol that tells the compiler to perform certain actions. The following lists describe the different operators used in Golang.

- Arithmetic Operators
- Assignment Operators
- Comparison Operators
- Logical Operators
- Bitwise Operators

```go
func arithmeticOperators() {
	x := 5
	y := 10
	// Arithmetic Operators [+, -, *, /, %, ++ --]

	// addition
	println(x + y)
	// subtraction
	println(x - y)
	// multiplication
	println(x * y)
	// division
	println(x / y)
	// modulus
	println(x % y)
	// incrimination
	x++
	println(x)
	// decremention
	y--
	println(y)
}

func assignmentOperators() {
	// Assignment Operators
	var x, y = 15, 25
	x = y
	// assign
	println("= ", x)

	x = 15
	x += y
	// add and assign
	println("+=", x)

	x = 50
	x -= y
	// subtract and assign
	println("-=", x)

	x = 2
	x *= y
	// multiplication and assign
	println("*=", x)

	x = 100
	x /= y
	// divide and assign
	println("/=", x)

	x = 40
	x %= y
	// 	Divide and assign modulus
	println("%=", x)
}

func comparisonOperators() {
	// Comparison Operators
	var x, y = 15, 25

	// equality
	println(x == y)
	// not equal
	println(x != y)
	// less than
	println(x < y)
	// less than or equal
	println(x <= y)
	// greater than
	println(x > y)
	// greater than or equal
	println(x >= y)

}
func logicalOperators() {
	// Logical Operators
	var x, y, z = 10, 20, 30

	// && AND
	println(x < y && x > z)
	// || OR
	println(x < y || x > z)
	// isNot AND && OR ||
	println(!(x == y && x > z))
}
func bitwiseOperators() {
	var x uint = 9  //0000 1001
	var y uint = 65 //0100 0001
	var z uint

	z = x & y
	// AND	Sets each bit to 1 if both bits are 1
	println("x & y  =", z)

	z = x | y
	// OR	Sets each bit to 1 if one of two bits is 1
	println("x | y  =", z)

	z = x ^ y
	// XOR	Sets each bit to 1 if only one of two bits is 1
	println("x ^ y  =", z)

	z = x << 1
	// 	Zero fill left shift	Shift left by pushing zeros in from the right and let the leftmost bits fall off
	println("x << 1 =", z)

	z = x >> 1
	// Signed right shift	Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off
	println("x >> 1 =", z)
}
```

## Conditional Statements

```go
func conditionalStatements() {

	// if statement
	var age int = 25
	if true {
		println(age)
	}
	if false {
		println(false)
	}

	// if else statement
	if age == 25 {
		print(age)
	} else {
		println("Not Young Enough")
	}

	// if else - else if statement
	if age == 2 {
		println("Your age is Low")
	} else if age == 25 {
		println("Perfect")
	} else {
		println("Go Home Son")
	}

	// The if statement supports a composite syntax where the tested expression is
	// preceded by an initialization statement.

	if x := 10; x == 10 {
		println("WOW: You are 10")
	} else if x == 100 {
		println("WOW: You are too OLD")
	} else {
		println("Congratulations")
	}
}
```

## Switch Case

```go
// Switch with single case
func switchSingleCase() {
	// to get the latest time
	var today = time.Now()
	// getting the todays date
	switch today.Day() {
	//if the date is 5
	case 5:
		println("Today is 5th of the month")
	case 10:
		println("Today is 10th of the month")
	case 15:
		println("Today is 15th of the month")
	case 20:
		println("Today is 20th of the month")
	case 25:
		println("Today is 25th of the month")
	case 30:
		println("Today is 30th of the month")
	default:
		println("Today Date is ", today)
	}
}

// Switch with multiple cases
func switchWithMultipleCase() {

	var today = time.Now()
	switch today.Day() {
	case 5, 10, 15:
		println("Clean your house.")
	case 25, 26, 27:
		println("Buy some food.")
	case 31:
		println("Party tonight.")
	default:
		println("No information available for that day.")
	}
}

func switchFallthroughCaseStatement() {
	// The fallthrough keyword used to force the execution flow to fall through the successive case block.

	today := time.Now()

	switch today.Day() {
	case 5:
		println("Clean your house.")
		fallthrough
	case 10:
		println("Buy some Soda.")
		fallthrough
	case 15:
		println("Visit a doctor.")
		fallthrough
	case 25:
		println("Buy some food.")
		fallthrough
	case 31:
		println("Party tonight.")
	default:
		println("No information available for that day.")
	}
}

func switchConditionalCasesStatement() {
	today := time.Now()

	switch {
	case today.Day() < 5:
		println("Clean your house.")
	case today.Day() <= 10:
		println("Buy some wine.")
	case today.Day() > 15:
		println("Visit a doctor.")
	case today.Day() == 25:
		println("Buy some food.")
	default:
		println("No information available for that day.")
	}
}

func switchInitializerStatement() {
	switch today := time.Now(); {
	case today.Day() < 5:
		println("Clean your house.")
	case today.Day() <= 10:
		println("Buy some wine.")
	case today.Day() > 15:
		println("Visit a doctor.")
	case today.Day() == 25:
		println("Buy some food.")
	default:
		println("No information available for that day.")
	}
}
```

## For Loop

Golang has no while loop because the for loop serves the same purpose when used with a single condition.

```go
func forLoop() {
	// traditional for-loop
	for i := 0; i < 10; i++ {
		println(i)
	}

	// for loop with single statement - just like while loop
	var k int = 1
	for k <= 10 {
		k++
		println(k)
	}
	// for loop with if statement
	for i := 0; ; i++ {
		println(k)
		if k == 10 {
			println("Reached 10")
		}
	}
	// Infinity loop -- Go will automatically tells you unreachable CODE
	v := 5
	for {
		println("Hello There")
		if v == 10 {
			break
		}
		v++
	}
}
```

## Functions

A declaration begins with the func keyword, followed by the name you want the function to have, a pair of parentheses (), and then a block containing the function's code.

The following example has a function with the name SimpleFunction. It takes no parameter and returns no values.

```go
func add(x int, y int) {
	total := 0
	total = x + y
	println(total)
}

// Function with int as return type
func addition(x int, y int) int {
	total := 0
	total = x + y
	return total
}

// float return type
func adding(x float32, y float32) float32 {
	return x - y
}

// string return type
func withString(a string, b string) string {
	return a + b
}

// boolean return type
func isbooling(a bool, b bool) bool {
	return a == b
}

// The return values of a function can be named in Golang
// Golang allows you to name the return values of a function.
// We can also name the return value by defining variables, here a variable total of
// integer type is defined in the function declaration for the value that the function returns.

func rectangle(length int, width int) (area int) {
	var parameter int
	parameter = 2 * (length + width)
	println("Parameter: ", parameter)

	area = length * width

	return // Return statement without specify variable name
}

// Golang Functions Returning Multiple Values
// Functions in Golang can return multiple values,
// which is a helpful feature in many practical scenarios.

func square(length int, width int) (area int, parameter int) {
	parameter = area + area + area + area
	area = length * width
	return // Return statement without specify variable name
}


// Passing Address to a Function
// Passing the address of variable to the function and the value of a variables
// modified using dereferencing inside body of function.

func update(a *int, t *string) {
	*a = *a + 5      // deferring pointer address
	*t = *t + " Doe" // deferring pointer address
	return
}
func mainFunction() {
	var age = 20
	var text = "Small"
	println("Before:", text, age)
	update(&age, &text)
	println("After :", text, age)
}

// Anonymous Functions
// An anonymous function is a function that was declared without any named identifier to refer to it.
// Anonymous functions can accept inputs and return outputs, just as standard functions do.

func anonymousFunctions() {
	// Example - 3 Passing arguments to anonymous functions.
	func(l int, b int) {
		println(l * b)
	}(20, 30)
}

// Example - 1
var (
	area = func(l int, b int) int {
		return l * b
	}
)

// Example - 2 Function defined to accept a parameter and return value.
func an() {
	println(
		"100 (°F) = %.2f (°C)\n",
		func(f float64) float64 {
			return (f - 32.0) * (5.0 / 9.0)
		}(100),
	)
}

// High Order Function
// A Higher-Order function is a function that receives a function as an argument or returns the
// function as output.
//
// Higher order functions are functions that operate on other functions, either by
// taking them as arguments or by returning them.

func sum(x, y int) int {
	return x + y
}
func partialSum(x int) func(int) int {
	return func(y int) int {
		return sum(x, y)
	}
}
func highOrderFunction() {
	partial := partialSum(3)
	println(partial(7))
}

// Returning Functions from other Functions

func squareSum(x int) func(int) func(int) int {
	return func(y int) func(int) int {
		return func(z int) int {
			return x*x + y*y + z*z
		}
	}
}
func returningFunction() {
	println(squareSum(5)(6)(7))
}

// User Defined Function

// Golang also support to define our own function types.
// The modified version of above program with function types as below:

type First func(int) int
type Second func(int) First

func squareSums(x int) Second {
	return func(y int) First {
		return func(z int) int {
			return x*x + y*y + z*z
		}
	}
}
```

## Arrays

An array is a data structure that consists of a collection of elements of a single type or simply you can say a special variable,
which can hold more than one value at a time. The values an array holds are
called its elements or items. An array holds a specific number of elements,
and it cannot grow or shrink. Different data types can be handled as elements in
arrays such as Int, String, Boolean, and others. The index of the first element of
any dimension of an array is 0, the index of the second element of any array dimension
is 1, and so on.

```go
func arrays() {

	// array that store the 5 int values
	var intArray [5]int
	// array that store the 5 string values
	var strArray [5]string
	strArray[0] = "United State America" // Assign a value to the first element
	strArray[1] = "Canada"               // Assign a value to the second element
	strArray[2] = "Japan"                // Assign a value to the third element

	intArray[0] = 12 // Assign a value to the first element
	intArray[1] = 12 // Assign a value to the second element
	intArray[2] = 12 // Assign a value to the third element

	println(strArray[0]) // Access the first element value
	println(strArray[1]) // Access the second element value
	println(strArray[2]) // Access the third element value
	println(intArray[0]) // Access the first element value
	println(intArray[1]) // Access the second element value
	println(intArray[2]) // Access the third element value

	// Initializing an Array with an Array Literal

	// x can hold the only 5 values or less but not more than 5
	x := [5]int{10, 20, 30, 40, 50} // Initialized with values
	// in y if you print the other two value will automatically be zero
	var y [5]int = [5]int{10, 20, 30} // Partial assignment
	println(x)
	println(y)

	// Initializing an Array with ellipses...

	// When we use ... instead of specifying the length. The compiler can identify the length of an array,
	// based on the elements specified in the array declaration.
	m := [...]int{10, 20, 30}
	println(m)      // list
	println(len(m)) // length

	// Initializing Values for Specific Elements

	//When an array declare using an array literal, values can be initialize for specific elements.//
	//A value of 10 is assigned to the second element (index 1) and a value of 30
	//is assigned to the fourth element (index 3).

	n := [5]int{1: 10, 3: 30}
	println(n)
}
```

## Slices

A slice is a flexible and extensible data structure to implement and manage collections of data. Slices are made up of multiple elements, all of the same type. A slice is a segment of dynamic arrays that can grow and shrink as you see fit. Like arrays, slices are index-able and have a length. Slices have a capacity and length property.

```go
func slicing() {
	var intSlice []int
	var strSlice []string
	println(intSlice, strSlice)

	// Declare Slice using Make

	// Slice can be created using the built-in function make. When you use make,
	// one option you have is to specify the length of the slice.
	// When you just specify the length, the capacity of the slice is the same.

	var intSliced = make([]int, 10)        // when length and capacity is same
	var strSliced = make([]string, 10, 20) // when length and capacity is different
	println("intSlice \tLen: %v \tCap: %v\n", len(intSliced), cap(intSliced))
	println("strSlice \tLen: %v \tCap: %v\n", len(strSliced), cap(strSliced))

	// Initialize Slice with values using a Slice Literal

	// A slice literal contain empty brackets followed by the type of elements the slice will hold,
	// and a list of the initial values each element will have in curly braces.

	var initializedIntSlice = []int{10, 20, 30, 40}
	var initializedStrSlice = []string{"India", "Canada", "Japan"}
	println("intSlice \tLen: %v \tCap: %v\n", len(initializedIntSlice), cap(initializedIntSlice))
	println("strSlice \tLen: %v \tCap: %v\n", len(initializedStrSlice), cap(initializedStrSlice))

	// Declare Slice using new Keyword

	// A slice can be declare using new keyword followed by capacity
	// in square brackets then type of elements the slice will hold.

	var newIntSlice = new([50]int)[0:10]
	println("intSlice \tLen: %v \tCap: %v\n", len(newIntSlice), cap(newIntSlice))
	println(newIntSlice)

	// Add Items

	a := make([]int, 2, 5)
	a[0] = 10
	a[1] = 20
	println("Slice A:", a)
	println("Length is %d Capacity is %d\n", len(a), cap(a))
	// using append keyword we can add values inside slice
	a = append(a, 30, 40, 50, 60, 70, 80, 90)
	println("Slice A after appending data:", a)
	println("Length is %d Capacity is %d\n", len(a), cap(a))

	// Access Items

	var b = []int{10, 20, 30, 40}
	// by the index we can access the values
	println(b[0])
	println(b[1])
	println(b[0:4])

	// Change Item Value

	var c = []string{"America", "Canada", "Japan"}
	println(c)
	// based on index we can change the values
	c[2] = "Germany"
	println(c)

	// Remove Item from Slice

	var f = []string{"Pakistan", "Canada", "Japan", "Germany", "Italy"}
	println(f)
	f = RemoveIndex(strSlice, 3)
	println(strSlice)

	// Tricks of Slicing

	var countries = []string{"pakistan", "japan", "canada", "australia", "russia"}

	println("Countries: %v\n", countries)

	println(":2 %v\n", countries[:2])

	println("1:3 %v\n", countries[1:3])

	println("2: %v\n", countries[2:])

	println("2:5 %v\n", countries[2:5])

	println("0:3 %v\n", countries[0:3])

	println("Last element: %v\n", countries[4])
	println("Last element: %v\n", countries[len(countries)-1])
	println("Last element: %v\n", countries[4:])

	println("All elements: %v\n", countries[0:])

	println("Last two elements: %v\n", countries[3:])
	println("Last two elements: %v\n", countries[len(countries)-2:])

	println(countries[:])
	println(countries[0:])
	println(countries[0:])

	// Append a slice to an existing slice
	// The usage of triple-dot ... ellipsis used to append a slice.

	var slice1 = []string{"america", "japan", "canada"}
	var slice2 = []string{"australia", "russia"}

	slice2 = append(slice2, slice1...)

	// Checking if Item Exist
	var g = []string{"America", "Canada", "Japan", "Germany", "Italy"}
	println(itemExists(g, "Canada"))
	println(itemExists(g, "Africa"))
}

// function to remove the Slice based on the INDEX
func RemoveIndex(s []string, index int) []string {
	return append(s[:index], s[index+1:]...)
}

// function to check if item Exists in a slice
func itemExists(slice interface{}, item interface{}) bool {
	s := reflect.ValueOf(slice)

	if s.Kind() != reflect.Slice {
		panic("Invalid data-type")
	}

	for i := 0; i < s.Len(); i++ {
		if s.Index(i).Interface() == item {
			return true
		}
	}

	return false
}
```

## Maps

A map is implemented using a hash table, which is providing faster lookups on the data element and you can easily retrieve a value by providing the key. Maps are unordered collections, and there's no way to predict the order in which the key/value pairs will be returned. Every iteration over a map could return a different order.

```go
func maps() {

	// Map initialization
	var employee = map[string]int{"Mark": 10, "Sandy": 20}
	println(employee)
	// empty map
	var emptyMap = map[string]int{}
	println(emptyMap)

	// Map declaration using make function

	var mapping = make(map[string]int)
	mapping["Mark"] = 10
	mapping["Sandy"] = 20
	println(mapping)

	employeeList := make(map[string]int)
	employeeList["Mark"] = 10
	employeeList["Sandy"] = 20
	println(employeeList)

	// Adding Items
	var a = map[string]int{"Mark": 10, "Sandy": 20}
	println(a)      // Initial Map
	a["Rocky"] = 30 // Add element
	a["Josef"] = 40
	println(a)

	// Removing Element
	var b = make(map[string]int)
	b["Mark"] = 10
	b["Sandy"] = 20
	b["Rocky"] = 30
	b["Josef"] = 40
	println(b)
	delete(b, "Mark")
	println(b)

	// Iterate over a Map
	var c = map[string]int{"Mark": 10, "Sandy": 20,
		"Rock": 30, "Brook": 40, "Stacy": 50}
	for key, element := range c {
		println("Key:", key, "=>", "Element:", element)
	}

}
```

## Struct

```go
type Rectangle struct {
	length  float64
	breadth float64
	color   string
}

/*
The rectangle struct and its fields are not exported to other packages because
identifiers are started with an lowercase letter. In Golang, identifiers are
exported to other packages if the name starts with an uppercase letter, otherwise
the accessibility will be limited within the package only.
*/

// Creating Instances of Struct Types

type Rectangular struct {
	length  int
	breadth int
	color   string

	// this is instance of the struct
	geometry struct {
		area      int
		perimeter int
	}
}

// Creating a Struct Instance Using a Struct Literal

type Colors struct {
	green string
	blue  string
	black string
}

// Struct Instantiation Using Pointer Address Operator

type Countries struct {
	firstCountry  string
	secondCountry string
	thirdCountry  string
}

// Nested Struct Type
// Struct can be nested by creating a Struct type using other Struct types as the type for
// the fields of Struct.
// Nesting one struct within another can be a useful way to model more complex structures.

type Salary struct {
	Basic, HRA, TA float64
}

type Employee struct {
	FirstName, LastName, Email string
	Age                        int
	// Upper Struct Inside a Struct
	MonthlySalary []Salary
}

// Add Method to Struct Type

type Money struct {
	Basic, HRA, TA float64
}

type Workers struct {
	FirstName, LastName, Email string
	Age                        int
	MonthlySalary              []Salary
}

func (e Workers) EmpInfo() string {
	println(e.FirstName, e.LastName)
	println(e.Age)
	println(e.Email)
	for _, info := range e.MonthlySalary {
		println("===================")
		println(info.Basic)
		println(info.HRA)
		println(info.TA)
	}
	return "----------------------"
}

func structures() {
	println(Rectangle{10.5, 25.10, "red"})
	// ---------------------------------------------
	var rect Rectangular // dot notation
	rect.length = 10
	rect.breadth = 20
	rect.color = "Green"

	rect.geometry.area = rect.length * rect.breadth
	rect.geometry.perimeter = 2 * (rect.length + rect.breadth)

	println(rect)
	println("Area:\t", rect.geometry.area)
	println("Perimeter:", rect.geometry.perimeter)

	// -----------------------------------------------

	var firstColor = Colors{green: "Blue", blue: "Black", black: "Maroon"}
	var secondColor = Colors{green: "Blue", blue: "Black", black: "Maroon"}
	var thirdColor = Colors{green: "Blue", blue: "Black", black: "Maroon"}
	println(firstColor, secondColor, thirdColor)

	// ------------------------------------------------------
	var firstCountries = &Countries{"America", "Pakistan", "Indonesia"}
	var secondCountries = &Countries{}
	secondCountries.firstCountry = "Australia"
	secondCountries.secondCountry = "Iraq"
	secondCountries.thirdCountry = "Labia"
	println(firstCountries, secondCountries)

	// -------------------------------------------------------

	e := Employee{
		FirstName: "Alisa",
		LastName:  "Jones",
		Email:     "alisa@gmail.com",
		Age:       25,
		MonthlySalary: []Salary{
			{
				Basic: 15000.00,
				HRA:   5000.00,
				TA:    2000.00,
			},
			{
				Basic: 16000.00,
				HRA:   5000.00,
				TA:    2100.00,
			},
			{
				Basic: 17000.00,
				HRA:   5000.00,
				TA:    2200.00,
			},
		},
	}
	println(e.FirstName, e.LastName)
	println(e.Age)
	println(e.Email)
	println(e.MonthlySalary[0])
	println(e.MonthlySalary[1])
	println(e.MonthlySalary[2])
}
```

## Congratulations

## Now you're a Gopher
