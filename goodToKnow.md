# Good To Know

- [Good To Know](#good-to-know)
  - [Data Types](#data-types)
  - [Number Types](#number-types)
    - [Integer Precision](#integer-precision)
    - [Floating Precision](#floating-precision)
    - [Numeric Strings](#numeric-strings)
  - [JavaScript Random](#javascript-random)
    - [JavaScript Random Integers](#javascript-random-integers)
    - [A Proper Random Function](#a-proper-random-function)
  - [var, let, const](#var-let-const)
  - [Types of JavaScript Operators](#types-of-javascript-operators)
    - [Assingment Operator](#assingment-operator)
      - [Arithmetic Assignment Operators](#arithmetic-assignment-operators)
      - [Shift Assignment Operators](#shift-assignment-operators)
      - [Bitwise Assignment Operatos](#bitwise-assignment-operatos)
      - [Logical Assignment Operatos](#logical-assignment-operatos)
    - [Bitwise Operators](#bitwise-operators)
  - [What is `this`](#what-is-this)
  - [JavaScript Date() Objects](#javascript-date-objects)

## Data Types

JavaScript has 8 Datatypes

```js
1. string
2. number
3. bigint
4. boolean
5. undefined
6. null
7. symbol
8. object
```

The Object Datatype

```js
1. An object
2. An array
3. a date
```

## Number Types

Most programming languages have many number types:

Whole numbers (integers): byte (8-bit), short (16-bit), int (32-bit), long (64-bit)

Real numbers (floating-point): float (32-bit), double (64-bit).


```md
Javascript numbers are always one type:
double (64-bit floating point).

Unlike many other programming languages, JavaScript does not define different types of numbers, like integers, short, long, floating-point etc.

JavaScript numbers are always stored as double precision floating point numbers, following the international IEEE 754 standard.

This format stores numbers in 64 bits, where the number (the fraction) is stored in bits 0 to 51, the exponent in bits 52 to 62, and the sign in bit 63:
```

| Value (aka Fraction/Mantissa) | Exponent         | Sign       |
| ----------------------------- | ---------------- | ---------- |
| 52 bits (0-51)                | 11 bits (52 -62) | 1 bit (63) |

### Integer Precision
---
Integers (numbers without a period or exponent notation) are accurate up to 15 digits.

Example: 
```js
const x = 999999999999999;   // x will be 999999999999999
const y = 9999999999999999;  // y will be 10000000000000000
```
The maximum number of decimals is 17.

### Floating Precision
---
Floating point arithmetic is not always 100% accurate:
```js
const x = 0.2 + 0.1;
// 0.2 + 0.1 = 0.30000000000000004
```
To solve the problem above, it helps to multiply and divide:
```js
const x = (0.2 * 10 + 0.1 * 10) / 10;
// 0.2 + 0.1 = 0.3
```

### Numeric Strings
--- 
JavaScript will try to convert strings to numbers in all numeric operations:

This will work:
```js
const x = "100";
const y = "10";
const z = x / y; // 10
```
```js
const x = "100";
const y = "10";
const z = x * y; // 1000
```
```js
const x = "100";
const y = "10";
const z = x - y;// 90
```
But this will not work:
```js
const x = "100";
const y = "10";
const z = x + y; // 10010
```
JavaScript uses the + operator to concatenate the strings.

## JavaScript Random
`Math.random()` returns a random number between 0 (inclusive),  and 1 (exclusive):

Note:
```md
Math.random() always returns a number lower than 1.
```

### JavaScript Random Integers
---

Note:
```md
There is no such thing as JavaScript integers.

We are talking about numbers with no decimals here.
```

Examples: 
```js
// Returns a random integer from 0 to 9:
Math.floor(Math.random() * 10);
```
```js
// Returns a random integer from 0 to 10:
Math.floor(Math.random() * 11);
```
```js
// Returns a random integer from 0 to 99:
Math.floor(Math.random() * 100);
```
```js
// Returns a random integer from 0 to 100:
Math.floor(Math.random() * 101);
```
```js
// Returns a random integer from 1 to 10:
Math.floor(Math.random() * 10) + 1;
```
```js
// Returns a random integer from 1 to 10:
Math.floor(Math.random() * 10) + 1;
```
```js
// Returns a random integer from 1 to 100:
Math.floor(Math.random() * 100) + 1;
```

### A Proper Random Function
---

As you can see from the examples above, it might be a good idea to create a proper random function to use for all random integer purposes.

This JavaScript function always returns a random number between min (included) and max (excluded):

Example:

```js
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min) ) + min;
}
```
This JavaScript function always returns a random number between min and max (both included):

Example:
```js
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1) ) + min;
}
```

## var, let, const

|         | Scope | Redeclare | Reassign | Hoisted | Bind this |
| ------- | ----- | --------- | -------- | ------- | --------- |
| `var`   | No    | Yes       | Yes      | Yes     | Yes       |
| `let`   | Yes   | No        | Yes      | No      | No        |
| `const` | Yes   | No        | No       | No      | No        |

## Types of JavaScript Operators

```md
1. Arithmetic Operators
2. Assignment Operators
3. Comparison Operators
4. String Operators
5. Logical Operators
6. Bitwise Operators
7. Ternary Operators
8. Type Operators
```

### Assingment Operator
---

#### Arithmetic Assignment Operators

| Operator | Example   | Same as      |
| -------- | --------- | ------------ |
| `=`      | `x = y`   | `x = y`      |
| `+=`     | `x += y ` | `x = x + y`  |
| `-= `    | `x -= y`  | `x = x - y`  |
| `*= `    | `x *= y`  | `x = x * y`  |
| `/=`     | `x /= y`  | `x = x / y`  |
| `%=`     | `x %= y`  | `x = x % y`  |
| `**=`    | `x **= y` | `x = x ** y` |

#### Shift Assignment Operators

| Operator | Example    | Same As       |
| -------- | ---------- | ------------- |
| `<<=`    | `x <<= y`  | `x = x << y`  |
| `>>=`    | `x >>= y`  | `x = x >> y`  |
| `>>>=`   | `x >>>= y` | `x = x >>> y` |

#### Bitwise Assignment Operatos

| Operator | Example   | Same As      |
| -------- | --------- | ------------ |
| `&=`     | `x &= y`  | `x = x & y`  |
| `^=`     | `x ^= y`  | `x = x ^ y`  |
| `\|=`    | `x \|= y` | `x = x \| y` |

#### Logical Assignment Operatos

ES2022

| Operator | Example      | Same As              |
| -------- | ------------ | -------------------- |
| `&&=`    | `x &&= y`    | `x = x && (x = y)`   |
| `\|\|=`  | `x \|\|= y ` | `x = x \|\| (x = y)` |
| `??=`    | `x ??= y`    | `x = x ?? (x = y)`   |

### Bitwise Operators
---

| Operator | Description            | Example   | Same as        | Result | Decimal |
| -------- | ---------------------- | --------- | -------------- | ------ | ------- |
| `&`      | `AND`                  | `5 & 1`   | `0101 & 0001`  | `0001` | `1`     |
| `\|`     | `OR`                   | `5 \| 1`  | `0101 \| 0001` | `0101` | `5`     |
| `~`      | `NOT`                  | `~ 5`     | `~0101`        | `1010` | `10`    |
| `^`      | `XOR`                  | `5 ^ 1`   | `0101 ^ 0001`  | `0100` | `4`     |
| `<<`     | `left shift`           | `5 << 1`  | `0101 << 1`    | `1010` | `10`    |
| `>>`     | `right shift`          | `5 >> 1`  | `0101 >> 1`    | `0010` | `2`     |
| `>>>`    | `unsigned right shift` | `5 >>> 1` | `0101 >>> 1`   | `0010` | `2`     |

## What is `this`

In JavaScript, the `this` keyword refers to an object. Which object depends on how `this` is being invoked (used or called).

The `this` keyword refers to different objects depending on how it is used:

```md
- In an object method, `this` refers to the object.
- Alone, `this` refers to the global object.
- In a function, `this` refers to the global object.
- In a function, in strict mode, `this` is undefined.
- In an event, `this` refers to the element that received the event.
- Methods like `call()`, `apply()`, and `bind()` can refer `this` to any object.
```

The `this` Keyword
```md
- In a function definition, `this` refers to the "owner" of the function.
- In the example above, `this` is the person object that "owns" the fullName function.
- In other words, this.firstName means the firstName property of `this` object.
```

## JavaScript Date() Objects

Note:
```md
JavaScript Stores Dates as Milliseconds

JavaScript stores dates as number of milliseconds since January 01, 1970.

Zero time is January 01, 1970 00:00:00 UTC.

One day (24 hours) is 86 400 000 milliseconds.
```

```md
Date objects are static. The "clock" is not "running".

The computer clock is ticking, date objects are not.

```
