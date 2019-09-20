# Values, Types, and Operators

<hr>

## Values
"*To be able to work with such quantities of bits without getting lost, we must separate them into chunks that represent pieces of information. In a JavaScript environment, those chunks are called values...*" [link](http://eloquentjavascript.net/01_values.html#p_JRdY+sw4TV)

### Numbers
* Values of the *number* type are numeric values. example:
<br>`13`  
  - *Overflow* is not really a thing to worry about anymore with current computers today. It is ok to use 64-bit chunks. [link](http://eloquentjavascript.net/01_values.html#p_WcfWpTcQB6)
* "*Not all whole numbers less than 18 quintillion fit in a JS number though. Those bits also store* **negative** *numbers, so one bit indicates the sign of the number.*<br>*In addition to this,* **nonwhole** *numbers must also be represented, thus using some of the bits to store the position of the decimal point*<br>*The acutal maximum whole number that can be stored is in the vicinity of 9 quadrillion*"
* **Fractional** numbers are written using a dot. Example:
<br>`9.81`
  - For extremely small or large numbers, **scientific notation** is acceptable. Add an `e` (exponent), followed by the exponent of the number. Example:
  <br>`2.998e8` --> **2.998 x 10^8 = 299,800,000**
  - "*Calculations with whole numbers* **(integers)** *smaller than the aforementioned 9 quadrillion are guaranteed to always be precise, however calculations with fractional numbers are generally not. Many numbers lose some precision when only 64 bits are available to store them.*"<br>"*The important thing is to be aware of it and treat fractional digital numbers as approximations, not as precise values.*" [link](http://eloquentjavascript.net/01_values.html#p_8KgYC0F1fX)

#### Arithmetic
* Arithmetic **OPERATORS** are represented by:
<br>addition `+`<br>subtraction `-`<br>multiplication `*`<br>division `/`<br>remainder or *modulo* `%`

#### Special Numbers
* `Infinity` and `-Infinity`
  - `Infinity` - 1 is *still* `Infinity`. However, be cautious with infinity-based computations as it quickly can lead to `NaN`.
  - `NaN` stands for "not a number", even though it **is** a value of the number type. This result is usually achieved by un-meaningful calculations. Example: `0 / 0` or `Infinity - Infinity`. [link](http://eloquentjavascript.net/01_values.html#p_kS+V22+tDp)

### Strings
* Strings are used to represent text. They are written by enclosing their content in **single quotes**, **double quotes**, and **backticks**
* *Newlines* (when you press enter) can be included without escaping only when the string is quoted with backticks.
	* Whenever a backslash (\) is found inside quoted text, it indicates the character after has special meaning.
	* *n* indicates **new line**
	* *t* indicates **tab character**

`
"This is the first line\nAnd this is the second"
`

* Strings cannot be used for arithmetic operations, however you can *concatenate* a string with another. example:

`
"con" + "cat" + "e" + "nate"
`

* *Backtick* quotes are called template literals, they can embed other values as well as span lines. example: `${...}`
	* Whatever is inside of the brackets will be computed, converted to a string, and included at that position in which it's inserted. example: `half of 100 is ${100/2}` = `"half of 100 is 50"`.

### Unary Operators
* An *unary* operator is one that takes a single operand/argument and performs an operation.
	* "An unary operation is an operation with only one operand. This operand comes either before or after the operator. Unary operators are more efficient than standard JS function calls. Additionally, unary operators **cannot** be overridden, therefore their functionality is guaranteed."
* Not all operators are symbols. Some are written as words. example: `typeof` operator, which produces a string value naming the type of the value you give it. example2:

`
console.log(typeof 4.5)
// -> number
|
console.log(typeof "x")
// -> string
`

* Unary operators only take one value, operators that take two values are *binary* operators.
* **UNARY OPERATORS**
	* *Unary plus* (**+**): Tries to convert the operand into a number
	* *Unary negation* (**-**): Tries to convert the operand into a number and negates after.
	* *Logical Not* (**!**): Converts to boolean value then negates it.
	* *Increment* (**++**): Adds one to it's operand.
	* *Decrement* (**--**): Decrements by one from it's operand.
	* *Bitwise Not* (**~**): Inverts all the bits in the operand and returns a number.
	* `typeof`: Returns a string which is the type of the operand.
	* `delete`: Deletes specific index of an array or specific property of an object.
	* `void`: Discards a return value of an expression.

### Boolean Values
* This value distinguishes between two possiblities, like "yes" and "no" or "on" and "off". *Boolean* type, has two values, `true` and `false`.

`
console.log(3>2);
// -> true
|
console.log(3<2);
// -> false
`

* Strings can be compared in the same way, to see if they hold `true`.

`
console.log("Aardvark" < "Zoroaster")
// -> true
`

* "The way strings are ordered is roughly alphabetic but not really what you'd expect to see in a dictionary: uppercase letters are always "less" than lowercase ones, so "Z" < "a", and nonalphabetic characters (!, -, and so on) are also included in the ordering. When comparing strings, JavaScript goes over the characters from left to right, comparing the Unicode codes one by one." [link](http://eloquentjavascript.net/01_values.html#p_No3uOP/bY2)
* Similar operators:
	* **>=**: greater than or equal to
	* **<=**: less than or equal to
	* **==**: equal to
	* **!=**: not equal to

`
console.log("Itchy" != "Scratchy")
// -> true
|
console.log("Apple" == "Orange")
// -> false
`

* There is **ONLY ONE** value in JS that is not equal to itself, and that is `NaN` ("not a number").
* `NaN` is supposed to denote the result of nonsensical computation, and as such, it **isn't** equal to the result of any *other* nonsensical computations.

`
console.log(NaN == NaN)
// -> false
`

### Logical Operators
* Some operations can be applied to Boolean values themselves. JS supports 3 logical operators: *and*, *or*, and *not*. These can be used to "reason" about Booleans.
* `&&` operator: represents logical *and*. It is a **binary** operator, and it's result is true **only if both** the values given to it are **true**.

`
console.log(true && false)
// -> false
|
console.log(true && true)
// -> true
`

* `||` operator: represents logical *or*. It produces true if **either** of the values given to it is **true**.

`
console.log(false || true)
// -> true
|
console.log(false || false)
// -> false
`

* `!` operator: unary operator that *flips* the value given to it