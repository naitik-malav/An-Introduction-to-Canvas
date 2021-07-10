# Appendix A - Reference Manual 

## A.1 Introduction
This manual describes the canvas language features. This manual is basically a reliable guide to the readers.

## A.2 Lexical Conventions
### A.2.1 Tokens
There are six classes of tokens which are classified as: identifiers, keywords, constants, string literals, operators, and other separators. white space is required to separate otherwise adjacent identifiers, keywords, and constants. Blanks, newlines, horizontal and vertical tabs, formfeeds and comments are ignored except as they separate tokens.

### A.2.2 Comments
The characters /* introduce a comment, which terminates with the characters */. If you want to write a comment of one or more than one line then we are using /*...*/, otherwise in general for single line comments we are going to use ‘//’ characters. Comments do not nest. Also they do not
occur within a string or character literals.

### A.2.3 Identifiers
An identifier can be a sequence of digits and letters. The first character must be a letter, after that it’s up to you to use numbers or not, while defining your identifiers. The underscore ‘ _’ counts as a letter. Upper and lower case letters are different. Internal identifiers include preprocessor macro
names and all other names that do not have external linkage. Identifiers with external linkage are more restricted.

### A.2.4 Keywords
The following identifiers are reserved for the use as keywords, and may not be used otherwise:
* if
* else
* loop
* in
* for
* select
* let
### A.2.5 Constants
There are several kinds of constants. Each has a data type; Par.A.4.2 discusses the basic types:
constant:
integer-constant
character-constant
floating-constant

#### A.2.5.1 Integer Constants:
 An integer constant consisting of a sequence of digits is taken to be octal if it begins with 0 (digit zero), or otherwise decimal. Octal constants are from 0 to 7. A sequence of digits preceded by 0x or 0X (digit zero) is taken to be a hexadecimal integer. The hexadecimal digits include a/A to f/F with values 10 to 15 respectively.

### A.2.6 String Literals

String Literal / String constant, is a sequence of characters surrounded by double quotes. A string is of type “array of characters” and storage class static, and is initialized with the given characters.

### A.3 Data types
## A.3.1 Basic Types

The basic data types that we have are: 
Scalar Types:
```
(Signed: i8, i16,  i32, i64, i128) 
(Unsigned: u8, u16, u32, u64, u128)
(Floating: f8, f16, f32, f64, f128)
(Character: One byte Character : ‘a’ , ‘A’ , ‘%’)
(String:'Canvas')
(Bool: true , false)
(Pointers: *f32, *u64)  
```
### A.3.2 Derived types
The derived data types are:
* Compound Types: Arrays and Tuples
	* Array: [5;i32]=[1,2,3,4,5]
	* Tuples:(‘a’,32,true)
 * Custom Types: 
	* Objects
	* Enums
	* Constants
* Library Types:
	* Vectors
	* Stack
	* Heaps
	* Dictionary

## A.4.1 Multiplicative Operators
The multiplicative operators *, /, and % group left-to-right.
multiplicative-expression:
* multiplicative-expression * cast-expression
* multiplicative-expression / cast-expression
* multiplicative-expression % cast-expression
The operands of * and / must have arithmetic type; the operands of % must have integral type.
The usual arithmetic conversions are performed on the operands, and predict the type of the
result.
The binary * operator denotes multiplication.The binary / operator yields the quotient, and the % operator the remainder, of the division of
the first operand by the second; if the second operand is 0, the result is undefined.

## A.4.2 Additive Operators
The additive operators + and - group left-to-right. If the operands have arithmetic type, the
usual arithmetic conversions are performed. There are some additional type possibilities for
each operator.
additive-expression:
multiplicative-expression
additive-expression + multiplicative-expression
additive-expression - multiplicative-expression
The result of the + operator is the sum of the operands. A pointer to an object in an array and a
value of any integral type may be added. The latter is converted to an address offset by
multiplying it by the size of the object to which the pointer points. The sum is a pointer of the
same type as the original pointer, and points to another object in the same array, appropriately
offset from the original object. Thus if P is a pointer to an object in an array, the expression
P+1 is a pointer to the next object in the array. If the sum pointer points outside the bounds of
the array, except at the first location beyond the high end, the result is undefined.
The result of the - operator is the difference of the operands. A value of any integral type may
be subtracted from a pointer, and then the same conversions and conditions as for addition
apply.

## A.4.3 Relational Operators:
The relational operators group left-to-right, but this fact is not useful; a<b<c is parsed as
(a<b)<c, and evaluates to either 0 or 1.
relational-expression:
shift-expression
* relational-expression < shift-expression
* relational-expression > shift-expression
* relational-expression <= shift-expression
* relational-expression >= shift-expression
The operators < (less), > (greater), <= (less or equal) and >= (greater or equal) all yield 0 if the
the specified relation is false and 1 if it is true.
## A.4.4 Equality Operators
equality-expression:
relational-expression
equality-expression == relational-expression
equality-expression != relational-expression
The == (equal to) and the != (not equal to) operators are analogous to the relational operators
except for their lower precedence. (Thus a<b == c<d is 1 whenever a<b and c<d have the
same truth-value.)
## A.4.5 Logical AND Operator
logical-AND-expression:
inclusive-OR-expression
logical-AND-expression && inclusive-OR-expression
The && operator groups left-to-right. It returns 1 if both its operands compare unequal to zero,
0 otherwise. Unlike &, && guarantees left-to-right evaluation: the first operand is evaluated,
including all side effects; if it is equal to 0, the value of the expression is 0. Otherwise, the
the right operand is evaluated, and if it is equal to 0, the expression's value is 0, otherwise 1.

## A.4.6 Logical OR Operator
logical-OR-expression:
logical-AND-expression
logical-OR-expression || logical-AND-expression
The || operator groups left-to-right. It returns 1 if either of its operands compare unequal to
zero, and 0 otherwise. Unlike |, || guarantees left-to-right evaluation: the first operand is
evaluated, including all side effects; if it is unequal to 0, the value of the expression is 1.
Otherwise, the right operand is evaluated, and if it is unequal to 0, the expression's value is 1,
otherwise 0.
## A.4.7 Conditional Operator
conditional-expression:
logical-OR-expression
logical-OR-expression ? expression : conditional-expression
The first expression is evaluated, including all side effects; if it compares unequal to 0, the
the result is the value of the second expression, otherwise that of the third expression. Only one of
the second and third operands are evaluated. If the second and third operands are arithmetic,
the usual arithmetic conversions are performed to bring them to a common type, and that type
is the type of the result.

## A.4.8 Assignment Expressions
There are several assignment operators; all groups right-to-left.
assignment-expression:
conditional-expression
unary-expression assignment-operator assignment-expression
assignment-operator: one of
= *= /= %= += -= <<= >>= &= ^= |=
All require an lvalue as left operand, and the lvalue must be modifiable: it must not be an
array, and must not have an incomplete type, or be a function.

## A.4.9 Comma Operator
expression:
assignment-expression
expression , assignment-expression

A pair of expressions separated by a comma is evaluated left-to-right, and the value of the left
expression is discarded. The type and value of the result are the type and value of the right
operand. All side effects from the evaluation of the left-operand are completed before
beginning the evaluation of the right operand.
