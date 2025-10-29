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
- `concat()`
	- Join several arrays into one

- `indexOf()`
	- Returns the first position at which a given element appears in an array

- `join()`
	- Combine the elements of an array into a single string and return the string
	- Default separator is a comma
		`console.log(fruits.join());      // "apple,banana,cherry"
		`console.log(fruits.join(" - ")); // "apple - banana - cherry"
		`console.log(fruits.join(""));    // "applebananacherry"

- `lastIndexOf()`
	- Gives the last position at which a given element appears in an array

- `pop()`
	- Removes the last element of an array and returns it

- `push()`
	- Add a new element at the end

- `reverse()`
	- Reverse the order of the elements in an array

- `shift()`
	- Removes the first element of an array and returns it

- `sort()`
	- Sorts elements alphabetically

- `splice()`
	- Adds elements in a specified way and position
		`array.splice(start, deleteCount, addItem1, addItem2, ...)`

		`const arr = [1, 2, 3, 4, 5];
		`arr.splice(1, 2, 'a', 'b'); // remove 2 elements at index 1, insert 'a', 'b'`
		`console.log(arr); // [1, 'a', 'b', 4, 5]``
		
- `toString()`
	- Converts elements to strings

- `unshift()`
	- adds s new element to the beginning
		`array.unshift(element1, element2, ...)`

- `valueOf()`
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
- `alert()`
	- Output data in an alert box in the browsers window (modal/dialog)

- `confirm()`
	- Opens up a yes/no dialog and returns true/false depending on user click

- `console.log()`
	- Writes information to the browser console, good for debugging purposes

- `document.write()`
	- Writes directly to the HTML document
	- Not recommend to be used in modern web dev
		`window.onload = function() {`
		    `document.write("This will replace the whole page!");`
		`};`

- `prompt()`
	- Creates a dialog for user input

### Global Functions
- `decodeURI()`
	- Decodes a Uniform Resource Identifier (URI) created by encodeURI or similar
	- Only decode characters that were percent-encoded
	- Does not touch special URI characters used in the structure (?, #. &, /)
	- If you need to decode components of a URI (like just a query parameter), use `decodeURIComponent()` instead
		`const uri = "https://example.com/page%20name?query=hello%20world";`
		`const decoded = decodeURI(uri);`
		`console.log(decoded); `
		`// "https://example.com/page name?query=hello world"`
	
- `decodeURIComponent() `
	- Decodes **all percent-encoded characters**, including special URI characters.
	- Use it for **parts of a URI**, like query parameters, not the whole URI.
	- If you use `decodeURI()` on a full URI, it won’t break the structure, but `decodeURIComponent()` can.
		`const component = "name%3DJohn%20Doe%26age%3D30"; // Encoded query string`
		`const decoded = decodeURIComponent(component);`
		`console.log(decoded); `
		`// "name=John Doe&age=30"`

- `encodeURI() `
	- Encodes a URI into UTF-8
	- Use for **entire URIs**.
	- Spaces and non-ASCII characters are encoded.
	- Leaves URI structure characters untouched.
	- For **individual components** like query parameters, use `encodeURIComponent()` instead.
		`const uri = "https://example.com/page name?query=hello world";`
		`const encoded = encodeURI(uri);`
		`console.log(encoded);`
		`// "https://example.com/page%20name?query=hello%20world"`

- `eval() `
	- Executes any JavaScript code in the string.
	- Can **access variables in the current scope**.
		`const x = 10;`
		`const y = 20;`
		`const code = "x + y";`
		`const result = eval(code);`
		`console.log(result); // 30`
	- Can be **dangerous**: executing untrusted strings can lead to security vulnerabilities (code injection).
	- Generally **avoid using `eval()`** if possible; there are safer alternatives.

- `isFinite()`
	- Determines whether a passed value is a finite number  
		`console.log(isFinite(-5.5));       // true`
		`console.log(isFinite(NaN));        // false`
		`console.log(isFinite("123"));      // true (string is converted to number)`
		`console.log(isFinite("hello"));    // false`

- `isNaN()`
	- The `isNaN()` function **checks whether a value is `NaN`** (Not-a-Number).
	- Returns `true` if the value **cannot be converted to a valid number**.
	- Returns `false` if the value **is a valid number** (or can be converted to one).
		`console.log(isNaN(NaN));       // true`
		`console.log(isNaN("hello"));   // true (cannot convert to number)`
		`console.log(isNaN("123"));     // false (converted to 123)`
		`console.log(isNaN(123));       // false`
		`console.log(isNaN(true));      // false (converted to 1)`
	- `isNaN()` **converts the value to a number first**, which can lead to unexpected results.
	- For a **more accurate check**, use `Number.isNaN()`:

- `Number()`
	- Returns a numeric value if conversion is possible.
	- Returns `NaN` if the value **cannot be converted** to a number.
	- **fails completely** if the string contains invalid characters:
		`console.log(Number("  3.14 "));   // 3.14 (ignores spaces)
		`console.log(Number(true));        // 1`
		`console.log(Number(false));       // 0`
		`Number("10abc"); // NaN`

- `parseFloat()`
	- Parses an argument and returns a floating point number 
	- Reads the string from left to right until it reaches a character that **cannot be part of a number**.
	- Returns `NaN` if the string **doesn’t start with a number**.
		`console.log(parseFloat("3.14"));       // 3.14`
		`console.log(parseFloat("10.5abc"));    // 10.5`
		`console.log(parseFloat("abc10.5"));    // NaN`
		`console.log(parseFloat("   7.5  "));   // 7.5 (ignores leading/trailing spaces)`

- `parseInt()`
	- The `parseInt()` function **parses a string and returns an integer** of the specified radix (base).
	- Reads the string from left to right until it reaches a character that **cannot be part of the number**.
	- Returns `NaN` if the string **doesn’t start with a number**.
		`console.log(parseInt("42"));        // 42`
		`console.log(parseInt("3.14"));      // 3 (ignores decimal part)`
		`console.log(parseInt("10abc"));     // 10`
		`console.log(parseInt("abc10"));     // NaN`
		`console.log(parseInt("101", 2));    // 5 (binary to decimal)`

---

# Loops

- `for`
	- The `for` loop is the most common way to create a loop in JavaScript.
		`for (let i = 0; i < 5; i++) { console.log(i); }`

- `while`
	- The `while` loop sets up conditions under which a loop executes.
	- The loop continues **as long as the condition is true**.
		`let i = 0;`
		`while (i < 5) { console.log(i); i++; }`

- `do...while`
	- The `do...while` loop is similar to `while`, but **executes at least once**.
	- The condition is checked **after each iteration**, so the loop may run even if the condition is initially false.
		`let i = 0;`
		`do { console.log(i); i++; } while (i < 5);`

- `break`
	- The `break` statement is used to **stop and exit the loop** under certain conditions.
		`for (let i = 0; i < 5; i++) { if (i === 3) break; console.log(i); }`
		`// Output: 0 1 2`

- `continue`
	- The `continue` statement **skips the current iteration** of the loop if certain conditions are met.
		`for (let i = 0; i < 5; i++) { if (i === 2) continue; console.log(i); }`
		`// Output: 0 1 3 4`


---

# If - Else Statements

```
if (condition) {
    // what to do if condition is met
} else {
    // what to do if condition is not met
}
```


---

# Strings 

### Escape Characters  
- `\'` Single quote  
- `\"` Double quote  
- `\\` Backslash  

- `\b` Backspace
	- Moves the cursor back one position (rarely used in strings).  
	- Example: `console.log("abc\b"); // outputs "ac"`

- `\f` Form feed  
	- Advances the text to the next page (rarely used, mostly legacy).  

- `\n` New line  

- `\r` Carriage return  
	- Moves the cursor to the beginning of the line without advancing to the next line. 

- `\t` Horizontal tabulator  

- `\v` Vertical tabulator  
		`console.log("Line1\vLine2\vLine3");`
		`Line1`
		    ` Line2`
		          `Line3`

### String Methods  
- `charAt()`  
	- Returns the character at a **specified position** inside a string.  
		`let str = "Hello"; console.log(str.charAt(1)); // "e"`

- `charCodeAt()`  
	- Returns the **Unicode (UTF-16) value** of the character at a specified position.  
		`let str = "A"; console.log(str.charCodeAt(0)); // 65`

- `concat()`  
	- Concatenates (joins) **two or more strings** into one.  
		`let str1 = "Hello"; let str2 = "World"; console.log(str1.concat(" ", str2)); // "Hello World"`

- `fromCharCode()`  
	- Returns a string created from the specified sequence of UTF-16 code units.  
		`console.log(String.fromCharCode(72, 101, 108, 108, 111)); // "Hello"`

- `indexOf()`  
	- Returns the **position of the first occurrence** of a specified text within a string.  
		`let str = "Hello World"; console.log(str.indexOf("o")); // 4`

- `lastIndexOf()`  
	- Returns the **position of the last occurrence** of a specified text, searching **backwards**.  
		`let str = "Hello World"; console.log(str.lastIndexOf("o")); // 7`

- `match()`  
	- Retrieves **matches of a string** against a search pattern (regex).  
		`let str = "abc123"; console.log(str.match(/\d+/)); // ["123"]`
		- `/\d+/g` → all numbers
		- `/[A-Z]/g` → all uppercase letters
		- `/[a-z]/g` → all lowercase letters
		- `/hello/i` → match "hello" (case-insensitive)

- `replace()`  
	- Finds and **replaces specific text** in a string.  
	- Only replaces the first occurrence by default
	- replaces all with g flag
	- case insensitive with i flag
		`let str = "Hello World"; console.log(str.replace("World", "JS")); // "Hello JS"`

- `search()`  
	- Executes a search for a matching text and returns its **position**.  
		`let str = "Hello World"; console.log(str.search("World")); // 6`

- `slice()`  
	- Extracts a **section of a string** and returns it as a **new string**.  
		`let str = "Hello World"; console.log(str.slice(0, 5)); // "Hello"`

- `split()`  
	- Splits a string into an **array of strings** at a specified separator.  
		`let str = "a,b,c"; console.log(str.split(",")); // ["a", "b", "c"]`

- `substr()`  
	- Extracts a substring based on a **start position** and **number of characters**.  
		`let str = "Hello World"; console.log(str.substr(6, 5)); // "World"`

- `substring()`  
	- Extracts characters between **two indices** (cannot use negative indices).  
		`let str = "Hello World"; console.log(str.substring(0, 5)); // "Hello"`

- `toLowerCase()`  
	- Converts all characters in a string to **lowercase**.  
		`let str = "HELLO"; console.log(str.toLowerCase()); // "hello"`

- `toUpperCase()`  
	- Converts all characters in a string to **uppercase**.  
		`let str = "hello"; console.log(str.toUpperCase()); // "HELLO"`

- `valueOf()`  
	- Returns the **primitive value** of a string object (the raw string itself).  
		`let strObj = new String("Hello"); console.log(strObj.valueOf()); // "Hello"`

---


# Regular Expressions (Regex)

### Pattern Modifiers
- `e` — Evaluate replacement  
- `i` — Perform case-insensitive matching  
- `g` — Perform global matching  
- `m` — Perform multi-line matching  
- `s` — Treat strings as a single line  
- `x` — Allow comments and whitespace in pattern  
- `U` — Non-greedy pattern  

### Brackets
- `[abc]` — Find any of the characters between the brackets  
- `[^abc]` — Find any character **not** in the brackets  
- `[0-9]` — Find any digit from 0 to 9  
- `[A-z]` — Find any character from uppercase **A** to lowercase **z**  
- `(a|b|c)` — Find any of the alternatives separated with `|`  

### Metacharacters
- `.` — Find a single character (except newline or line terminator)  
- `\w` — Word character (alphanumeric `[A-Za-z0-9_]`)
- `\W` — Non-word character  
- `\d` — Digit  
- `\D` — Non-digit character  
- `\s` — Whitespace character  
- `\S` — Non-whitespace character  
- `\b` — Match at the beginning or end of a word  
- `\B` — Match not at the beginning or end of a word  
- `\0` — NUL character  
- `\n` — New line character  
- `\f` — Form feed character  
- `\r` — Carriage return character  
- `\t` — Tab character  
- `\v` — Vertical tab character  
- `\xxx` — Character specified by an **octal number** `xxx`  
- `\xdd` — Character specified by a **hexadecimal number** `dd`  
- `\uxxxx` — Unicode character specified by a **hexadecimal number** `xxxx`  

### Quantifiers
- `n+` — Matches any string that contains **at least one** `n`  
- `n*` — Matches any string that contains **zero or more** occurrences of `n`  
- `n?` — Matches any string that contains **zero or one** occurrence of `n`  
- `n{X}` — Matches a string that contains a **sequence of X** `n`s  
- `n{X,Y}` — Matches strings that contain a sequence of **X to Y** `n`s  
- `n{X,}` — Matches any string that contains **at least X** `n`s  
- `n$` — Matches any string with `n` at the **end** of it  
- `^n` — Matches any string with `n` at the **beginning** of it  
- `?=n` — Matches any string that is **followed by** a specific string `n`  
- `?!n` — Matches any string that is **not followed by** a specific string `n`  

---


# DOM Node

### Node Properties
- `attributes`  
	- Returns a **live collection** (`NamedNodeMap`) of all attributes of an element. Updates automatically when attributes change.  
		`console.log(element.attributes["id"].value);`

- `baseURI`  
	- Provides the **absolute base URL** of the document that contains the element. Useful for resolving relative URLs.  
		`console.log(document.body.baseURI);`

- `childNodes`  
	- Returns a **live NodeList** of all child nodes (elements, text, comments).  
		`console.log(element.childNodes[0]);`

- `firstChild`  
	- Returns the **first child node** of an element (may be a text node).  
		`console.log(element.firstChild);`

- `lastChild`  
	- Returns the **last child node** of an element.  
		`console.log(element.lastChild);`

- `nextSibling`  
	- Returns the **next node** at the same tree level. May include text or comment nodes.  
		`console.log(element.nextSibling);`

- `nodeName`  
	- Returns the **name of the node** (e.g., `"DIV"`, `"#text"`). For elements, this is the tag name.  
		`console.log(element.nodeName);`

- `nodeType`  
	- Returns a **numeric constant** representing the type of the node.  
		`console.log(element.nodeType); // 1 = Element, 3 = Text, 8 = Comment`

- `nodeValue`  
	- Returns or sets the **value** of a node (for text, comment, or attribute nodes).  
		`textNode.nodeValue = "Updated text";`

- `ownerDocument`  
	- References the **document** object that the node belongs to.  
		`console.log(element.ownerDocument === document); // true`

- `parentNode`  
	- Returns the **parent node** of an element.  
		`console.log(element.parentNode);`

- `previousSibling`  
	- Returns the **previous node** at the same tree level.  
		`console.log(element.previousSibling);`

- `textContent`  
	- Gets or sets the **text content** of a node and all its descendants, ignoring HTML tags.  
		`element.textContent = "Hello World";`

