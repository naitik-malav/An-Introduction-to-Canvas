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
