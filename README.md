# An Introduction to Canvas
Project done in course Principles of Programming Languages under Prof. Ramakrishna Upadrasta
>This is an imperative language, allowing the programmer to change the state of the program based on instructions, with focus on Object Oriented Programming. This language is >being developed for general purpose use with an added focus on 2D game development. The use of various resources like a basic output stream focused on the 'canvas' as well as >input features for images and key bindings allow it to perform basic I/O operations directly onto the canvas, a resizable output screen based on the features opted by the user. >A simple syntax without trade-off for performance being a key feature of the language enables new users to get used to this language readily. The closeness of it to the machine >hardware allows it a lot of flexibility like bitwise calculations allowing it to be used for building intensive systems like Operating Systems and device drivers. Being >platform independent it is easily executable on vastly different hardware without any modification to the code, a write-once-run-anywhere feature.

Let’s begin with a simple “Hello World!”

    /* Our first program 
    This is an example of multiline comments */ 
    fn main()
    { \#print(“Hello World!”); //Printing “Hello World!” to the canvas } 
    //END OF THE PROGRAM

>// is used to write single line comments This above program displays “Hello World!” on the blank canvas with the default positioning and features. We break this down and look >into its parts in a little more details. fn -> This is a keyword for declaring functions

>main -> Every program starts with the main function. This is a special keyword used once in every program(In libraries there may be no need to use main). The function’s scope >is declared with the curly braces { } . As soon as an instance of a data type becomes unreachable it is deconstructed and the memory is cleared, scroll down for more on data >types. This syntax of writing might be familiar to people who have used the C language. Everything that starts with # is a macro. As you may recall from C, the # is a >preprocessor. Here macro is used instead of function to achieve better performance since marco’s are preprocessed while functions are not. Both macros and functions however are >precompiled. #print is macro which is used to display output to the output stream The macros will be used to define the canvas size /resolution , they will have a default value >but can be changed by the user if code is being implemented for a different platform.

    #canvas 200*300

>Macros will be discussed later. ; is used for line-break.Similar to C This program just prints the message “Hello World!” to the output stream.

**Arithmetic Operators:** 
>All operators like + - * / % are used in the same way as used in every programming language as well as in mathematics. Numerical Constants: 0 to 9 are numerical constants More >about operators and constants will be discussed later in further chapters.

**More discussion about the canvas :** 
>The origin of the canvas is defined to be the top left of the screen, restricting the values of position_x and position_y as greater or equal to zero . Increase in x-coordinate >shifts the image to the right and increase in the y-coordinate shifts the image down. Images can be displayed on the canvas using the display() function. All images to be >inserted on the canvas will follow the same principle as the origin , with their top left corner being at the position passed with the display function . All images to be used >in the program must be imported before the main function .

    get default.jpeg snake_head

>get is a keyword that imports image default.jpeg which exists in the same directory as the program, if the image does not exist then image can still be imported using its path. >The image is referred to as snake_head for the rest of the program and the word snake_head cannot be used for any other variable name.




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

