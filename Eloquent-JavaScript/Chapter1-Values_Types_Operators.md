# Values, Types, and Operators

<hr>

## Values
"*To be able to work with such quantities of bits without getting lost, we must separate them into chunks that represent pieces of information. In a JavaScript environment, those chunks are called values...*" [link](http://eloquentjavascript.net/01_values.html#p_JRdY+sw4TV)

## Numbers
* Values of the *number* type are numeric values. example:
<br>`13`  
  - *Overflow* is not really a thing to worry about anymore with current computers today. It is ok to use 64-bit chunks. [link](http://eloquentjavascript.net/01_values.html#p_WcfWpTcQB6)

* "*Not all whole numbers less than 18 quintillion fit in a JS number though. Those bits also store* **negative** *numbers, so one bit indicates the sign of the number.*<br>*In addition to this,* **nonwhole** *numbers must also be represented, thus using some of the bits to store the position of the decimal point*<br>*The acutal maximum whole number that can be stored is in the vicinity of 9 quadrillion*"

* **Fractional** numbers are written using a dot. Example:
<br>`9.81`
  - For extremely small or large numbers, **scientific notation** is acceptable. Add an `e` (exponent), followed by the exponent of the number. Example:
  <br>`2.998e8` --> **2.998 x 10^8 = 299,800,000**
  - "*Calculations with whole numbers* **(integers)** *smaller than the aforementioned 9 quadrillion are guaranteed to always be precise, however calculations with fractional numbers are generally not. Many numbers lose some precision when only 64 bits are available to store them.*"<br>"*The important thing is to be aware of it and treat fractional digital numbers as approximations, not as precise values.*" [link](http://eloquentjavascript.net/01_values.html#p_8KgYC0F1fX)

### Arithmetic
* Arithmetic **OPERATORS** are represented by:
<br>addition `+`<br>subtraction `-`<br>multiplication `*`<br>division `/`<br>remainder or *modulo* `%`

### Special Numbers
* `Infinity` and `-Infinity`
  - `Infinity` - 1 is *still* `Infinity`. However, be cautious with infinity-based computations as it quickly can lead to `NaN`.
  - `NaN` stands for "not a number", even though it **is** a value of the number type. This result is usually achieved by un-meaningful calculations. Example: `0 / 0` or `Infinity - Infinity`. [link](http://eloquentjavascript.net/01_values.html#p_kS+V22+tDp)

## Strings
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

## Unary Operators
* An *unary* operator is one that takes a single operand/argument and performs an operation.
	* "An unary operation is an operation with only one operand. This operand comes either before or after the operator. Unary operators are more efficient than standard JS function calls. Additionally, unary operators **cannot** be overridden, therefore their functionality is guaranteed."

* Not all operators are symbols. Some are written as words. example: `typeof` operator, which produces a string value naming the type of the value you give it. example2:

`
console.log(typeof 4.5)
// -> number
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

## Boolean Values
* This value distinguishes between two possiblities, like "yes" and "no" or "on" and "off". *Boolean* type, has two values, `true` and `false`.

`
console.log(3>2);
// -> true
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
console.log(true && true)
// -> true
`

* `||` operator: represents logical *or*. It produces true if **either** of the values given to it is **true**.

`
console.log(false || true)
// -> true
console.log(false || false)
// -> false
`

* `!` operator: unary operator that *flips* the value given to it

* "When mixing these Boolean operators with arithmetic and other operators, it is not always obvious when parentheses are needed. In practice, you can usually get by with knowing that of the operators we have seen so far, `||` has the lowest precedence, then comes `&&`, then the comparison operators (`>`, `==`, and so on), and then the rest. This order has been chosen such that, in typical expressions like the following one, as few parentheses as possible are necessary" [link](http://eloquentjavascript.net/01_values.html#p_qSXjNNI5/y)

`
1 + 1 == 2 && 10 * 10 > 50
`

* `ternary` operates on **3** values. This is called the *conditional* operator. It is written with a question mark and a colon. The value on the left of the question mark "picks" which of the other two values will come out. When it is *true*, it chooses the **middle** value, and when it is *false* it chooses the value on the **right**:

`
console.log(true ? 1 : 2);
// -> 1
console.log(false ? 1 : 2);
// -> 2
`

## Empty Values
* `null`, and `undefined` are used to denote the absence of a *meaningful* value. They are values but they carry no information. These two values are largely interchangeable.

* Many operations that don't produce a meaningful value yield `undefined` simply because they have to yield *some* value.

## Automatic Type Conversion
* JavaScript goes out of it's way to accept almost any program you give it, even programs that do odd things.

`
console.log(8 * null);
// -> 0
console.log("5" - 1);
// -> 4
console.log("5" + 1);
// -> 51
console.log("five" * 2);
// -> NaN
console.log(false == 0);
// -> true
`

* When an operator is applied to the *wrong* type of value, JavaScript will quietly convert that value to the type it needs, using a set of rules that often aren't what you want or expect. This is called *type coercion*. The `null` in the first expression becomes `0`, and the `"5"` in the second expression becomes `5` (from string to number). Yet in the third expression, `+` tries string concatenation before numeric addition, so the `1` is converted to `"1"` (from number to string).

* When something that doesn't map to a number in an obvious way (such as `"five"` or `undefined`) is converted to a number, you get the value `NaN`, so if you find yourself getting one of those in an unexpected place, look for accidental type conversions.

* When comparing values of the same type using `==`, the outcome is easy to predict: you should get true when both values are the same, except in the case of `NaN`. But when the types differ, JavaScript uses a complicated and confusing set of rules to determine what to do. In most cases, it just tries to convert one of the values to the other value's type. However, when `null` or `undefined` occurs on either side of the operator, it produces true only if both sides are one of `null` or `undefined`.

`
console.log(null == undefined);
// -> true
console.log(null == 0);
// -> false
`

* This is useful to test if a value has a **real** value instead of `null` or `undefined`, you can compare it to `null` with the `==` (or `!=`) operator.

* What if you want to test whether something refers to the precise value `false`? Expressions like `0 == false` and `"" == false` are also **true** because of automatic type conversion. When you *don't* want any type conversions to happen, use `===` and `!==`. `===` tests whether a value is *precisely* equal to the other, and the `!==` tests whether it is not precisely equal. So, `"" === false` is false as expected. [link](http://eloquentjavascript.net/01_values.html#p_N4OuWeYOwF)

### Short-Circuiting of Logical Operators
* The logical operators `&&` and `||` handle values of different types in a peculiar way. They will convert the value on their **left** side to *Boolean Type* in order to decide what to do, but depending on the operator and the result of that conversion, they will return either the *original* left-hand value or the right-hand value.

* The `||` operator will return the value to it's left when that can be converted to true and will return the value on it's right otherwise. This has the expected effect when the values are Boolean and does something *analogous* for values of other types.

`
console.log(null || "user")
// -> user
console.log("Agnes" || "user")
// -> Agnes
`

* ^^ We can use this functionality as a way to fall back on a default value. If you have a value that might be empty, you can put `||` after it with a replacement value. If the initial value can be converted to false, you'll get the replacement instead. The rules for converting strings and numbers to Boolean values state that `0`, `NaN` and the empty string `""` count as `false`, while all the other values count as `true`. So `0 || -1` produces `-1`, and `"" || "!?"` yields `"!?"`.

* The `&&` operator works similarly but the other way around. When the value to it's left is something that converts to false, it returns that value, and otherwise it returns the value on it's right.

* Another important property of these two operators is that the part to their right is evaluated only when necessary. In the case of `true || X`, no matter what `X` is--even if it's a piece of program that does something *terrible*--the result will be true, and `X` is never evaluated. The same goes for `false && X`, which is false and will ignore `X`. This is called **short-circuit evaluation**.

* The conditional operator works in a similar way. Of the second and third values, only the one that is selected is evaluated.
