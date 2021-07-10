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
