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
  - "*Calculations with whole numbers* **(integers)** *smaller than the aforementioned 9 quadrillion are guaranteed to always be precise"
