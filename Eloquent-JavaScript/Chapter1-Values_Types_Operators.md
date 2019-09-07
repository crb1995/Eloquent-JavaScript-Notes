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
* Strings are used to represent text. They are written by enclosing their content in quotes:
<br>
` Hello `
<br>
'Hi there'
<br>
"Howdy"
* 
