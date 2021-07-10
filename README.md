# An Introduction to Canvas
### Project done in course Principles of Programming Languages under Prof. Ramakrishna Upadrasta
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



# Language evolution 
* The first step towards designing the language for our team was deciding what will it achieve differently from existing languages that already saturate the market. Although a specialized language could have been the answer we did not have enough knowledge of the market. So we decided to make a language that students and young code enthusiasts would enjoy using.
* All the languages that we had encountered till date did not support any kind of graphics. And using game engines is not possible for everyone as they require powerful hardware. For building even a simple game like snakes in c you have to manipulate characters which is a tedious task and does not feel natural. So we decided to design a language that despite being simple and not requiring powerful hardware, would be able to deliver proper graphics while maintaining the closeness to hardware as we see in c/c++ and java.
* We also tried to incorporate certain features found in python that we felt would be essential for a programmer. We decided that the language will be able to give output onto both a console and a specialized screen we call 'canvas', the canvas will be used to show graphics whereas the output to the console will help the programmer to find and isolate the source of error.
* At this time we realized that this language could be used to debug codes by displaying how a code is manipulating the memory and displaying the data blocks as different shapes on the screen. We also decided to give the programmer the power or authority to decide how many bits were to be allocated to integer data types as there are strict integer restrictions when data is manipulated for a game. We also incorporated the feature wherein the language automatically decides suitable data type for a given data ,thus reducing the number of segmentation faults that would be encountered .
* We also realized that the language needs a function to print characters to the canvas screen so that the programmer could display some messages. So we added the feature of a macro that can display messages. The language was also decided to be object oriented and imperative. It did not make sense to make this language declarative as we hoped that it would interact with the processor on a low level. 
* The language was decided to be object oriented to support the various entities that the programmer creates in the program to support the application such as the character that the user plays, the npc that the user could interact with and the objects of the environment. 
* Normal 'for' and 'while' loops exist in almost all languages that we studied for constant and variable iterations respectively. Although these are very basic and all programmers are familiar with them, we have also added a loop type named “loop” which allows for a better interaction between the language and the programmer allowing him/her to name the loop and terminate them with more control. 
* We have provided basic 'if-else' statements and made our own version of the 'switch' statement which is more flexible and supports adding statements and multiple variables to the syntax thus reducing the need to add tediously many if-else' statements to the language. 
* The image adding process was streamlined and attributes were added that can be manipulated while adding the image, although this programing language does not offer editing tools which are as powerful as a game engine, we think, the tools that we offer to manipulate image while importing and the pre-defined functions that it supports would allow user to make 2-D and pseudo 3-D games easily.
* We also thought of adding asynchronous programing to the language as there may be times when two process may not be dependent on each other, thus allowing the user to utilize the hardware to its utmost capacity thus increasing the language's throughput.
* Many languages also support the feature to define user type data types, which our language, being an object-oriented language, of course offers but as we have given the user control over how many bits of memory has to be allocated, the user can be much more creative with the use of resources.
* We have also added the control to catch errors when they are discovered so as to empower the programmer to debug the code easily and allow for better control over unexpected occurances during execution.
* The language has various logical operators, we wanted to keep them to a minimum but have followed the universally accepted paradigm, making this language feel natural to new users. We also included all the basic features we think a language must have such as relational operators and differentiated between line terminators and case terminators, a feature not readily available in C.




# Language Tutorial
## Part A: Data-types And Variables <h2>
* Scalar Types:
1. Signed: i8, i16,  i32, i64, i128
1. Unsigned: i8, i16, i32, i64, i128
1. Floating: i8, i16, i32, i64, i128
1. Pointers: *f32, *u64  (the default size is machine dependent)
1. Pointers(storing image address): *k64
1. Character: One byte Character : ‘a’ , ‘A’ , ‘%’
1. String: 
1. Bool: true , false
* Compound Types: Arrays and Tuples
	1. Array: [5;i32]=[1,2,3,4,5]
	1. Tuples:(‘a’,32,true)
* Custom Types:
	1. Objects
  1. Enums
  1. Constants
	
## Variable Declaration <h3> 
__let__ keyword is used to create variables from expressions.
Generally the let keyword automatically gets data types based on inputs.
Ex: 
	
	```let a=32;//Here a is type inferred as integer of 32 bits```
But you can also explicitly declare the datatype.Ex:
```let a:i32;```
```let a=”hello”;//Automatically a is string data type```
```let a:string=”hello”;```
```let a:char=’a’;```
_‘let’_ is used for variable declaration and ’i32’ informs the compiler of the type of data i.e. integer in this case, and it’s size, 32 bit.
**Constant Declaration** 
_‘const ’_ keyword is used to create constants from statements.
```const a:i32;```
_Programming Examples:_
	
```
#canvas 1600*1900
get dot.jpeg dot 1*1
obj point
{
	position_x:i32=(canvas.X)/2;

 /*here we don’t use let keyword since let creates a physical instance of variable. whereas in objects there is only logical implementation.i.e. memory is allocated in the let statement. but for objects memory is allocated when the object variable is declared.*/

	position_y:i32=(canvas.Y)/2;
	image:*k64 = null;
	fn square(&self, a:i32)
	{
		let  temp: i32=0;
		“Loop1”:loop
		{
			if(temp>=a)
				break “Loop1”;
 			display(self.image,self.position_x+temp,self.position_y);
			temp+=1;
		}
		temp=0;

		“Loop2”:loop
		{
			if(temp>=a)
				break “Loop2”;
 			display(self.image,self.position_x+a,self.position_y+temp);
			temp+=1;
		}
		temp=a;
		“Loop3”:loop{
			if(a<=0) 
				break “Loop3”;
			display(self.image,self.position_x+temp,self.position_y+a);
			a-=1;
		}
		temp= a;
		“Loop4”:loop
		{
			if(a<=0)		
				break “Loop4”;
			display(image,position_x,position_y+temp)
 			a-=1;
		}
	}
}

fn main()
{
	let a:point;//Automatically revokes the constructors
	let b:point = point{position_x = 1 ,position_y =2,image = dot};//Assignment to data member without constructor
	let (c,d)=(point,i32)//destructuring the tuple and creating the respective bindings
	let (m,n,o,p)=(1:i32,’c’,2:i64,3.14:f64) // A tuple of different data types
	a.image = dot; //Assigning dot to data-member image
	a.square(6);
}
``` 
## Chapter 3: Flow of Control<h2>
### Expression Vs Statements: <h3>
Expression returns values whereas statements do not return value. Statements always end with ‘;’ whereas expressions do not do so.

__If/Else, Loop, While, In, For, Select__
* if/else: Branching is same as in other languages.The conditional is an expression that returns boolean Value.
_Program to determine if someone can cast vote or not_
```
fn main() {
	let age:i32;		//age of a person
	read(“{}”,age).fail(“Failed to read”);           //scanning age of a person
	if(age >= 18)
    		#print(“You are allowed to caste a vote\n”);

	else
    	#print(“You are not allowed to caste a vote\n”);
}
```
__Program to calculate BMI __
```

fn main() {
              let weight:i32;   
              let height:i32;
              read(“{} {}”,age,height).fail(“Failed to read”);      // scanning age and height
              let BMI:f32;
              BMI  = age/(height*height) {f32}; 
              if(BMI<=18.00)
             		#print(“take care of your health and eat well\n”);
              elif(BMI>18 && BMI<24)
             		#print(“Hurrah ! You are healthy and fit\n”);
              else
             		#print(“start dieting\n”);
}
```
__Program to swap to numbers__
```
fn main()  {                         
	let a:i32;
	let b:i32;
	read(“{} {}”,a,b).fail(“Failed to read”);            // scanning variable a and b
	a = a+b;
	b = a-b;
	a = a-b;
	#print(a);
	#print(“ “);
	#print(b);

}
```
__Calculator__
```
obj calculator {
	a:i32; 
	b:i32;
	fn get(&self){
		#print(“Enter first number\n”);
		read(“{}”,self.a).fail(“Failed to read a”);
		#print(“Enter second number\n”);
		read(“{}”,self.b).fail(“Failed to read b”);
	fn add(&self)->i32 {
		a+b
	}
	fn subtract(&self) -> i32{
		a-b           //Return expression
	}
	fn multiply(&self) -> i32{
		return a*b;// return using statement
	}
	fn divide(&self) -> f32{
		if(b == 0)  {
			#print(“Division by zero\n”);
			return ‘inf’;//inf is special keyword to represent +Infinity.Also there is -inf
		}
		
		else return a/b {f32};			//type-casting it to a floating point
	}

}    
fn main()
{
	let choice: i16;			//choice to perform one of the operations on the calculator
	let cal: calculator;
	#print(“Enter 1 to add two numbers\n”,
		“Enter 2 to subtract two numbers\n”,
		“Enter 3 to multiply two numbers\n”,
		“Enter 4 to divide two numbers\n”,
		“Enter 0 to exit\n”);

	
	“Loop1” loop: 
	{
		read(“{}”,choice).fail(“Failed to read choice”);
		if(choice==0)
			break “Loop1”;
		select(choice) {
			1 => #print(“Result of addition: {0}\n”, cal.add()),
			2 => #print(“Result of subtraction: {0}\n”, cal.subtract()), 
			3 => #print(“Result of multiplication: {0}\n”, cal.multiply()),
			4 => #print(“Result of division: {0}\n”, cal.divide()),
			default => #print(“Wrong choice\n”),
		}
	}
}
```

* _ __loop:__ _
1. loop is a keyword for creating infinite loop.
1. The body of a loop is an expression which returns value.
1. Loops can be nested.
1. Loops can be labelled and we have control over each loop
1. Loop can be better understood as a combination of while and do-while loop,making both of them redundant.

* in: 
1. The in keyword is used to check if a value is present in a sequence (list, range, string etc.).
1. The in keyword is also used to iterate through a sequence in a for loop:
for : for is used to create a for loop like C. But for-in has more functionality than the for loop in C/C++ language.
	for in returns an iterator which iterates over the range or array or vectors etc.
 __Program to print fibbonaci numbers__
```
fn main() {
 	let n1:i32 =1; 
	let n2:i32=0;
	let temp:i32=0;		//printing 10 terms of a fibonacci series
	#print(“10 fibonacci numbers \n”);
	#print(“1 ”);
	for i in 2 to 10 {               //2 and 10 are both  inclusive 
   		temp = n1+n2;
		n1 = n2;
        	n2 = temp;
     		#print(“ {} ”, temp);
	}
}
```
__Program prints 50 numbers__
```
fn main() {
	for number in 0 to 100;2 {// here step is 2
         	#print(“{} is a even number which lies in the range 0 to 100\n”,number);
        } 
}
```
```
fn main() {
 	let n1:i32 =1; 
	let n2:i32=0;
	let temp:i32=0;		
	#print(“10 fibonacci numbers \n”);
	#print(“1 ”);
	for i in 2 to 10 {               //2 and 10 are both  inclusive 
   		temp = n1+n2;//Generates Type Error since temp:i16.temp should be temp:i32
		n1 = n2;
        	n2 = temp;
     		#print(“ {} ”, temp);
	}
}
```

* __select __: Canvas provides pattern matching via the select keyword, which can be used like a C switch. 
```
fn main()
{
	let n1:i32=0 ;
	let n2:i32=0;
	read(“{}”,n1).fail(“Failed to get input)
	n2=n1%2;
	select(n1)
	{
		0 => #print(“Even”); //; is line terminator
        	#print(“\n”), // , is select case terminator
		1 => #print(“Odd”),
	}
}
```

## 5 examples that do not conform<h2>

_Function declaration and it’s return type:_
```
fn divide(a:i32,b:i32) -> i32{
		if(b == 0)  {
			#print(“Division by zero\n”);
			return ‘inf’;//inf is special keyword to represent +Infinity.Also there is -inf
		}
		else return a/b {f32};	//return type mismatch	
}
```
Here, the return type has been declared as i32, but the result which is actually being returned is not an integer, it’s a floating point. 
```
Loop:
“Loop1”:loop
{
 	display(self.image,self.position_x+temp,self.position_y);
	temp+=1;
}
```
An infinite loop. missing the ‘break’ statement
```
fn main() {
 	let n1:i32 =1; 
	let n2:i32=0;
	let temp:i16=0;		
	#print(“10 fibonacci numbers \n”);
	#print(“1 ”);
	for i in 2 to 10 {               //2 and 10 are both  inclusive 
   		temp = n1+n2;//Generates Type Error since temp:i16.temp should be temp:i32
		n1 = n2;
        	n2 = temp;
     		#print(“ {} ”, temp);
	}
}
```
```
fn main() {
 	let n1:i32 =1; 
	let n2:*i32=n1;//Pointer to i32 variable
	#print(“{}”,n2);//print pointer value//i.e. address of n1
	#print(“{}”,*n2);//dereferencing the pointer
	n2 = null;
	#print(“{}”,n2);//pointer is null.So it prints null.
	#print(“{}”,*n2);//pointer does not contain any data so gives null error
}
```
```
fn main() {
 	let n1:i32 =1; 
	let n2:i32=0;

	for i in 2 to 10 {               //2 and 10 are both  inclusive 
   		temp = n1+n2;//Generates Error: Variable not defined
		n1 = n2;
        	n2 = temp;
     		#print(“ {} ”, temp);
	}
}
```

# Basic Examples
1. **Animation of a bouncing ball** :The ball starts from the top-left of the screen and moves to the right.
```
#canvas 1600*1900
get circle.jpeg circle 5*5
obj ball
{
	position_x:i32 = 10;
	position_y:i32 = 10;
	image:*k64 = null;
	fn move(&self)
	{
		let x_max: i32 = canvas.X - 10;
		let y_min: i32 = canvas.Y - 10;
		let flag:i32 = 1;
		“Loop1”:loop
		{
			“Loop2”:loop
			{
	if (position_y==y_min || position_y==y_max)
		flag = (-1)*flag ;
	position_y +=flag;
	position_x +=1;
	if (position_x>canvas.X || position_y>canvas.Y)
break “Loop1”;
display(self.image,self.position_x,self.position_y,0.5);
}
}
}
}
fn main()
{
let a:ball;//Automatically revokes the constructors
a.image = dot; //Assigning ball to data-member image
a.move();
return; 
}
```
2. **A square which moves based on the 'WASD' movement keys within the canvas**
```
#canvas 1600*1900
get square.jpeg turtle 5*5
obj car
{
position_x:i32 = 0;
position_y:i32 = 0;
limit_x:i32 = 0;
limit_y:i32 = 0;
image:*k64 = null;
fn move(&self)
{
	let key =’w’;
“Loop1”:loop
{
	read(“{}”,key).fail( break”Loop1”);
	if (key == ‘D’)
		self.position_x +=limit_x;
	else if (key == ‘A’)
		self.position_x -=limit_x;
	else if (key == ‘S’)
		self.position_y  -= limit_y;
	else if (key == ‘D’)
		self.position_y +=limit_y;
	else
		break “Loop1”;
	if(position_x>=limit_x  && position_x<=(canvas.X-limit_x) && position_y>=limit_y || position_y<=(canvas.X - limit_y))
		display(self.image,self.position_x,self.position_y);
}
}
}
fn main()
{
let a:car = car{turtle.X ,turtle.Y ,turtle.X, turtle.Y, turtle};
a.move();
}
```
3. **Here below we are going to find the maximum number present in an array={3,4,99,12,0,10} which is 99.**  
```
fn main()
{
        let Array[6,i32] = [3, 4, 99, 12, 0, 10] ;
let index;i32;
            let temp,i32 = -1;
	for index in 0 to 5: {
		if(temp > Array[index])
temp = Array[index];
} 
#print(“Maximum number in an array is: {}”, temp);
}
```
Logic behind the above program is comparing all the numbers of an array with a constant number temp. Suppose temp is greater than the particular number then swap it with the temp. Print the value of temp at last. Final value of temp is the largest number in the given array. 

4. **Here below we are going to swap the given two numbers a and b using pointers and printing their initial as well as final values.**
```
fn swap( x:*i32, y:*i32) {
temp:*i32 = x;
x  = y;
y = temp;
} 
fn main()
{
	let a:i32=12;
	let b:i32=99;
#print(“Initial Values of a, b = {}, {}\n”, a,b);
swap(&a, &b);
#print(“Final Values of a, b = {}, {}\n”, a,b);
}
```
Here initially ‘a’ is equal to 12, and ‘b’ equal to 99. After printing their initial values we are invoking swap function and pass the address of a and b. Inside the function swap pointer x, y receives the address of a and b respectively. Using the variable temp we swapped them. In this case no need to return anything from the function.

5. **Animation of a circle of radius 60 being drawn onto the canvas**
```
#canvas 1600*1900
get dot.jpeg dot 3*3
obj point
{
position_x:i32=(canvas.X)/2;
position_y:i32=(canvas.Y)/2;
image:*k64 = null;
fn circle(&self, a:i32)
{
“Loop1”:loop
{
if(self.position_x==canvas.X/2 + a)
break “Loop1”;
self.position_x+=1;
self.position_y+=1;
 		display(self.image,self.position_x+temp,self.position_y);
}
“Loop2”:loop
{
if(self.position_x==canvas.X/2)
break “Loop2”;
self.position_x-=1;
self.position_y+=1;
 		display(self.image,self.position_x+temp,self.position_y);
}
“Loop3”:loop
{
if(self.position_x==canvas.X/2- a)
break “Loop3”;
self.position_x-=1;
self.position_y-=1;
 		display(self.image,self.position_x+temp,self.position_y);
}
“Loop4”:loop
{
if(self.position_x==canvas.X/2-a)
break “Loop4”;
self.position_x+=1;
self.position_y-=1;
 		display(self.image,self.position_x+temp,self.position_y);
}
}
}

fn main()
{
let a:point;//Automatically revokes the constructors
a.image = dot; //Assigning dot to data-member image
a.circle(60);
}
```
6.**Program to print the input number into character**
```
fn main()
{
        let number:i4;
read(“{}”,number).fail(“Failed to read, you are entering the number greater than 15”);  

select(number):
0 => #print(“{} is ‘Zero’ \n”, number),
1 => #print(“{} is ‘One’ \n”, number),
2 => #print(“{} is ‘Two’ \n”, number),
3 => #print(“{} is ‘Third’ \n”, number),
4 => #print(“{} is ‘Fourth’ \n”, number),
5 => #print(“{} is ‘Five’ \n”, number),
6 => #print(“{} is ‘Six’ \n”, number),
7 => #print(“{} is ‘Seven’ \n”, number),
8 => #print(“{} is ‘Eight’ \n”, number),
9 => #print(“{} is ‘Nine’ \n”, number),
10 => #print(“{} is ‘Ten’ \n”, number),
11 => #print(“{} is ‘Eleven’ \n”, number),
12 => #print(“{} is ‘Twelve’ \n”, number),
13 => #print(“{} is ‘Thirteen’ \n”, number),
14 => #print(“{} is ‘Fourteen’ \n”, number),
15 => #print(“{} is ‘Fifteen’ \n”, number),
}
```
7.**Animation of a square being drawn onto the canvas**
```
#canvas 1600*1900
get dot.jpeg dot 1*1
obj point
{
	position_x:i32=(canvas.X)/2;
	position_y:i32=(canvas.Y)/2;
	image:*k64 = null;
	fn square(&self, a:i32)
	{
		let  temp: i32=0;
		“Loop1”:loop
		{
			if(temp>=a)
				break “Loop1”;
 			display(self.image,self.position_x+temp,self.position_y);
			temp+=1;
		}
		temp=0;

		“Loop2”:loop
		{
			if(temp>=a)
				break “Loop2”;
 			display(self.image,self.position_x+a,self.position_y+temp);
			temp+=1;
		}
		temp=a;
		“Loop3”:loop{
			if(a<=0) 
				break “Loop3”;
			display(self.image,self.position_x+temp,self.position_y+a);
			a-=1;
		}
		temp= a;
		“Loop4”:loop
		{
			if(a<=0)		
				break “Loop4”;
			display(image,position_x,position_y+temp)
			a-=1;
		}
	}
}

fn main()
{
	let a:point;//Automatically revokes the constructors
	let b:point = point{position_x = 1 ,position_y =2,image = dot};//Assignment to data member without constructor
	let (c,d)=(point,i32)//destructuring the tuple and creating the respective bindings
	let (m,n,o,p)=(1:i32,’c’,2:i64,3.14:f64) // A tuple of different data types
	a.image = dot; //Assigning dot to data-member image
	a.square(6);
}
```
8.**Program to calculate BMI**
```
fn main() {
              let weight:i32;   
              let height:i32;
              read(“{} {}”,age,height).fail(“Failed to read”);      // scanning age and height
              let BMI:f32;      //variable for BMI
              BMI  = age/(height*height) {f32}; 
              if(BMI<=18.00) 
             		#print(“take care of your health and eat well\n”);
              elif(BMI>18 && BMI<24)
             		#print(“Hurrah ! You are healthy and fit\n”);
              else
             		#print(“start dieting\n”);
}
```
9. **Calculator**
```
obj calculator {
	a:i32;		//first variable
b:i32;		//second variable
	fn get(&self){
		#print(“Enter first number\n”);
		read(“{}”,self.a).fail(“Failed to read a”);
		#print(“Enter second number\n”);
		read(“{}”,self.b).fail(“Failed to read b”);
fn add(&self)->i32 {
	a+b
}
fn subtract(&self) -> i32{
	a-b           //Return expression
}
fn multiply(&self) -> i32{
	return a*b;// return using statement
	}
	fn divide(&self) -> f32{
		if(b == 0)  {
			#print(“Division by zero\n”);
			return ‘inf’;//inf is special keyword to represent +Infinity.Also there is -inf
		}
		else return a/b {f32};			//type-casting it to a floating point
	}
}    
fn main()	
{
	let choice: i16;	      //choice to perform one of the operations on the calculator
	 let cal: calculator;
	#print(“Enter 1 to add two numbers\n”,
		“Enter 2 to subtract two numbers\n”,
		“Enter 3 to multiply two numbers\n”,
		“Enter 4 to divide two numbers\n”,
		“Enter 0 to exit\n”);
“Loop1” loop: 
{
	read(“{}”,choice).fail(“Failed to read choice”);
if(choice==0)
			break “Loop1”;
	select(choice) {
			1 => #print(“Result of addition: {0}\n”, cal.add()),
			2 => #print(“Result of subtraction: {0}\n”, cal.subtract()), 
			3 => #print(“Result of multiplication: {0}\n”, cal.multiply()),
			4 => #print(“Result of division: {0}\n”, cal.divide()),
			default => #print(“Wrong choice\n”),
}
}
}
```
10. **Insertion sort in canvas** 
```
fn main() {
	let Array[7: i32] = {1, 9, 4, 12, 80, 0, 2};
	let index1:i32 = 0;
	let index2:i32 = 0;
            let key:i32;
	for index1 in 1 to 7
           { 
        key = Array[index1]; 
        index2 = index1 - 1; 
  
        /* Move elements of arr[0..i-1], that are 
        greater than key, to one position ahead 
        of their current position */
        while (index2 >= 0 && Array[index2] > key)
        { 
            Array[index2 + 1] = Array[index2]; 
            index2 = index2 - 1; 
        } 
        Array[index2 + 1] = key; 
    } 
	#print(“Sorted Array is : “);
for index1 in 0 to 6:
#print(“{}, ”, Array[index1]);
}
```
    
	
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


	
# Conclusion 
* We learned team-work, how to work with our friends through an online platform, delineation of tasks and how to better use the cloud for getting work done.
* We learned about the pros of improved time management and the cons of procrastination
* Learned how to use github 
* We learned how to use markdown language and how to effectively present data in it
* We studied manuals of different languages, understood basic concepts involved in all programming languages and their similarities and differences, strengths and weaknesses.
* Improved our concepts about functional and object oriented paradigm and the reasons for their preferences.
* Learnt about how and when to use which particular language for a specific tasks and the different ways the language would strain the hardware resources
* We brushed up our basic understanding of c programming language
* Got a glimpse at the various thought processes that go into creation of large projects in general and the creation of a new language in particular.
* The reasons behind the creation of new languages, why they managed to take the market by storm and how they impacted future language development.
* We also got sneak-peek into the vast amount of techniques and resources that are used for the creation of 2D games, the reasons for the existence of game engines and the hardships one encounters when trying to create a language especially dedicated towards gaming. 
* We also understood why there are so many bugs even after years of development in big games
* We appreciate good languages and software more now that we know the effort it takes just to design them

	

## Shortcomings :
* Though we had tried to make this language easy to understand, a requirement of the basic understanding of oop concepts with amplified image import and other game development features makes it a little harder for the basic user to link with it in comparision to languages like python but still easier to approach than C.
* As the program allows for more efficient and creative use of memory, to access its full capabilities a good understanding of memory is needed.
* Since this language is close to the processor and the programmer has been given access to many different attributes, even simple codes may be difficult to code. 
* As this language has low level abstraction, it is not very secure. If someone opens the code then he can easily manipulate the values and being closer to the hardware it can directly affect it.
* The language does not allow for global variables, the only global trait that can be declared are the attributes of ‘canvas’. 
* The language has a very strict syntax despite our best efforts to try and make it as readable as python.
* A compiler has yet not been designed, but we feel like the language can be slow if the programmer tries to load too many images.
