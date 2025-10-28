# Variables

### var, const, let
- var
	- is the most common variable. Can be reassigned but only access within a function. Variables defined with var move to the top when code is execute
	- Move to the top - hoisting - when JavaScript runs, it moves all var declarations to the top of their scope, but the values are nor hoisted
		- This:
		 `console.log(a); // undefined
		 `var a = 5;`

		- Is pretty much this:
		 `var a;
		 `console.log(a); // undefined`
		 `a = 5;
- const
	- Cannot be reassigned and not accessible before they appear within the code.
	- No hoisting, so the value isn't moved up
- let
	- Similar to const, however, let variable can be reassigned by not re-declared
	- Block scoped
	- let is technically hoisted, but there's a "temporal dead zone" (TDR) from the start of the block until the line where it's declared:
		- This will produce a reference error
		 `console.log(z); // Reference Error
		 `let z = 7`

### Data Types
- Numbers
	- `var age = 23`
- variables
	- `var x`
- Text(strings)
	- `var a = "init"`
- Operations
	- `var b = 1 + 2 + 3`
- Boolean
	- True or false statements
- Constant numbers
	- `const PI = 3.14`
- Objects
	- `var name = {firstName: "John", lastName: "Doe"}`


### Arrays
`var fruit = ["Banana", "Apple", "Pear"];`
##### Array Methods
- concat()
	- Join several arrays into one
- indexOf()
	- Returns the first position at which a given element appears in an array
- join()
	- Combine the elements of an array into a single string and return the string
	- Default separator is a comma
		`console.log(fruits.join());      // "apple,banana,cherry"
		`console.log(fruits.join(" - ")); // "apple - banana - cherry"
		`console.log(fruits.join(""));    // "applebananacherry"
- lastIndexOf()
	- Gives the last position at which a given element appears in an array
- pop()
	- Removes the last element of an array and returns it
- push()
	- Add a new element at the end
- reverse()
	- Reverse the order of the elements in an array
- shift()
	- Removes the first element of an array and returns it
- sort()
	- Sorts elements alphabetically
- splice()
	- Adds elements in a specified way and position
		`array.splice(start, deleteCount, addItem1, addItem2, ...)`

		`const arr = [1, 2, 3, 4, 5];
		`arr.splice(1, 2, 'a', 'b'); // remove 2 elements at index 1, insert 'a', 'b'`
		`console.log(arr); // [1, 'a', 'b', 4, 5]``
- toString()
	- Converts elements to strings
- unshift()
	- adds s new element to the beginning
		`array.unshift(element1, element2, ...)`
- valueOf()
	- Returns the primitive value of the specified object
		`const strObj = new String("hello");
		`console.log(strObj.valueOf()); // "hello" (primitive string)`
	
		`const arr = [1, 2, 3];
		`console.log(arr.valueOf()); // [1, 2, 3] (arrays usually return themselves)`

---
# Operators

### Basic Operators
- `+` Addition  
- `-` Subtraction  
- `*` Multiplication  
- `/` Division  
- `()` Grouping operator  
- `%` Modulus (remainder)  
- `++` Increment number  
- `--` Decrement number

### Comparison Operators
- `==` Equal to (value)
- `===` Equal value and equal type  
- `!=` Not equal  
- `!==` Not equal value or not equal type  
- `>` Greater than  
- `<` Less than  
- `>=` Greater than or equal to  
- `<=` Less than or equal to  
- `? :` Ternary operator
	`condition ? expressionIfTrue : expressionIfFalse`

### Logical Operators
- `&&` Logical AND  
- `||` Logical OR  
- `!` Logical NOT

### Bitwise Operators
- `&` AND  
- `|` OR  
- `~` NOT  
- `^` XOR  
- `<<` Left shift  
- `>>` Right shift  
- `>>>` Zero fill right shift

---

# Functions

### Outputting Data
- alert()
	- Output data in an alert box in the browsers window (modal/dialog)
- confirm()
	- Opens up a yes/no dialog and returns true/false depending on user click
- console.log()
	- Writes information to the browser console, good for debugging purposes
- document.write()
	- Writes directly to the HTML document
		`window.onload = function() {`
		    `document.write("This will replace the whole page!");`
		`};`
	- Not recommend to be used in modern web dev
- prompt()
	- Creates a dialog for user input

### Global Functions
- decodeURI()
	- Decodes a Uniform Resource Identifier (URI) created by encodeURI or similar
		`const uri = "https://example.com/page%20name?query=hello%20world";`
		
		`const decoded = decodeURI(uri);`
		`console.log(decoded); `
		`// "https://example.com/page name?query=hello world"`
	- Only decode characters that were percent-encoded
	- Does not touch special U