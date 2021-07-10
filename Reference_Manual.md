# Reference Manual  
### Keywords:-
* break
* const
* continue
* do
* else
* enum
* false
* fn
* for
* if
* import
* in
* let
* loop
* obj
* pub
* priv
* return
* self
* to
* true
* while
 
### Comments:-
* LINE COMMENT : ```//```
* MULTI LINE COMMENT : ```/*…….*/```
 
### WhiteSpace:-
* horizontal tab, ```'\t'```
* new line, ```'\n'```
* space, ```' '```
 
### Characters And Strings:-
* ASCII_ESCAPE : ```\x``` OCT_DIGIT HEX_DIGIT
* ```\```n new line
* ```\t``` tab
* ```\\ ```backslash
* ```\0``` Null Character or Terminating Character
* *QUOTE_ESCAPE* : ``` \' ```Single Quotes
*	```\"``` Double Quotes
### Numbers:
* Decimal integer ```-45```
* Hex integer ```0xff```
* Octal integer ```0o27```
* Binary integer ```0b1101```
* Floating-point ```1.52E-23```
### BOOLEAN:
* ```true```
* ```false ```
 
 
### Symbols:
* ``` + ```Plus
*  ```- ``` Minus
* ```*``` Star
* ```/ ```Slash
* ```%``` Percent
* ```^``` Caret
* ```!``` Not
* ```&``` And
* ```|``` Or
* ```&&``` AndAnd
* ```||``` Or Or
* ```<<``` SHL
* ```>>``` SHR
* ```+=``` PlusEq
* ```-=``` MinusEq
* ```*=``` StarEq
* ```/=``` SlashEq
* ```%=``` PercentEq
* ```^=``` CaretEq
* ```&=``` AndEq
* ```|=``` OrEq
* ```<<=``` ShlEq
* ```>>=``` ShrEq
* ```=``` Eq 
* ```==``` Assignment
* ```!=``` Ne
* ```>``` Gt
* ```<``` Lt
* ```>=```Ge
* ```<=``` Le
* ```_``` Underscore
* ```.``` Dot
* ```.. ```DotDot
* ```..= ```DotDotEq
* ```,``` Comma
* ```;``` Semi
* ```:``` Colon
* ```->``` RArrow
* ```=>``` EqGtArrow
* ```# ```Pound
### Bracket punctuations:
* ```( )``` Parentheses
*  ```{ }``` Curly braces
* ```[ ]``` Square brackets
### Scoping:
*  ```::``` 
### Block Expression:
Block Expression or block is a control flow expression. A block sequentially executes its component statements. All the data items declared inside the block are not visible outside the block.
Block Format:
```
{
	//Block Body
	Statements or Variable Declarations
}
 ```
Since Block is an expression we can use it to assign data to variables.
Ex:
```
let var={
           	5-61+5*2
};
```
### Parallel Blocks Or Future Blocks:
These blocks are used in achieving parallel programming. These blocks returns an enum .
If block has finished it’s task it returns the value of the overall expression. If not the value returned is void,null or undefined. To check processing of the block use the keyword cpara. All this is included in standard library for parallel processing.
      ```     	para
           	{
Expressions
}```
#### Functions:
It consists of a block , along with a name and a set of parameters. Functions are declared with the keyword fn. Functions may or may not return the value of the block.
There is also para fn which is used for achieving parallelism

### Objects:
It is an abstract data type which is combination of variables, functions or methods, and data structures. All these are called as fields of objects.
There are 2 types of objects:
Objects with visible fields.
```obj coordinate{x: i32, y: i32};
let cor = coordinate{x: 1,y: 2};
let xcor: i32 = cor.x;
```

Objects with anonymous fields. The tuple object.

```
obj coordinate(i32, i32);
let cor = coordinate(1, 2);
let xcor: i32 = select cor { coordinate(x, _) => x };
```
## Methods can be implemented on objects

### Enumerations:
Enumerations are declared with the keyword enum.
	Same usage as in the C language.
Enumeration variants can be constructed similarly to objects with scope operator.
Ex:- 
```enum movement{up, down, left, right, xy{x:i32 , y:i32} }
let moveUp = movement::up;
let moveXY = movement::xy{x:23 , y:24};
```
### Call expression:
It consists of an expression followed by a parenthesized expression-list.It is used to invoke function with 0 or more input variables
Method call expression:
It consists of an expression followed by a single dot. Method call is used in combination with objects.
```
Ex:-
obj qwer{
	a:i32;		//first variable
b:i32;		//second variable
fn add(&self)->i32 {a+b}
	 let cal: qwer{a:32,b:56};
	cal.add();
```
### Pointers And Memory Management:-
Pointers are nothing but a reference to a memory address on the Heap.
In Canvas we can reference and dereference using & and * operators
```
let ptr = alloc(size,type);//ptr of type with size
dealloc(ptr)//deallocation of the heap memory used by pointer
realloc(ptr,size(ptr),4*size(ptr));//reallocation of memory used by ptr
```
