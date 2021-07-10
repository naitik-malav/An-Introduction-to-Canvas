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

