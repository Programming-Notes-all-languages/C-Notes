<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#compiling-and-linking'>Compiling and Linking</a>
  </li> 
  <li>
    <a href='#general-form-of-a-simple-program'>General Form of a Simple Program</a>
  </li>    
  <li>
    <a href='#comments'>Comments</a>
  </li>  
  <li>
    <a href='#variable-assignment-and-initialization'>Variable Assignment and Initialization</a>
  </li>  
  <li>
    <a href='#naming-and-using-variables'>Naming and Using Variables</a>
  </li>  
  <li>
    <a href='#whitespace-and-basic-formatting'>General Form of a Simple Program</a>
  </li>  
  <li>
    <a href='#introduction-to-literals-and-operators'>Introduction to Literals and Operators</a>
  </li>
  <li>
    <a href='#atomic-data-types-and-type-conversion'>Atomic Data Types and Type Conversion</a>
  </li>
  <li>
    <a href='#introduction-to-stdioh'>Introduction to stdio.h</a>
  </li>  
  <li>
    <a href='#constant-variables'>Constant Variables</a>
  </li> 
  <li>
    <a href='#escape-sequences'>Escape Sequences</a>
  </li>
  <li>
    <a href='#arithmetic-operators'>Arithmetic Operators</a>
  </li>  
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>    
</ol>
</details>

## Compiling and Linking
<ul>
  <li>
    <a>There are three steps in running C code:</a>
    <ul>
      <li>
        <a><em>Preprocessing</em>: this is the step where the program is given to the preprocessor which obeys <em>directives</em></a>
      </li>
      <li>
        <a><em>Compiling</em>: the code that was just modified by the preprocessor is now modified by the <em>compiler</em>. The compiler translates the code into <em>object code</em></a>
      </li>  
      <li>
        <a><em>Linking</em>: this is the final step in running C code where the <em>linker</em> combines the object code produced through the compilation process with any additional code needed to run the program completely. This combination of code creates an executable file which can be used to run the program</a>
      </li>
    </ul>
  </li>
  <li>
    <a>To compile code within the terminal of an IDE, proceed with the following. The file that contains the program is called main.c; therefore, its compilation can be accomplished with the following command: gcc -Wall main.c</a>
    <ul>
      <li>
        <a>The Wall addition enables all warnings; if there are any warnings, they will be printed on the screen</a>
      </li>
      <li>
        <a>If there is more than one file needed for the execution of the program, the additional file names are listed as alike main</a>
      </li>  
    </ul>  
  </li>  
  <li>
    <a>To then execute the program, type the following command into the terminal: ./a.exe</a>
  </li>  
</ul>    

## General Form of a Simple Program
<ul>
  <li>
    <a>Here is the general form of a C program:

```c
directives
int main()
{
    statements;
}
```
</a>
  </li>
  <li>
    <a>Before a program can be compiled, it needs to be edited first by the preprocessor. The code that is used by the preprocessor is called directives. One very common directive is the <a><</a>stdio.h<a>></a> directive which contains information regarding C's standard input and output processes. By including the line #include <a><</a>stdio.h<a>></a> within a program, the information that is associated with stdio.h library is added to the program before compilation</a>
    <ul>
      <li>
        <a>Directives will always start with the # symbol; they will always be only one line long; and they do not need any special marker at the end of the directive (like a semicolon)</a>
      </li>
    </ul>    
  </li>  
  <li>
    <a>A program can also contain additional functions in addition to the main function. The main function is mandatory and is a special function--it is always called when a program executes</a>
  </li>  
  <li>
    <a>At the end of the main function, it normally returns 0;. This statement has two effects: it terminates the main function which ends the program and upon termination, the main function returns the integer zero. The return of the integer zero determines the normal termination of the program</a>
  </li>
  <li>
    <a>A <em>statement</em> is a command that is to be executed upon running the program. An example of a statement is the return 0; statement</a>
  </li>  
</ul>  

## Comments
<ul>
  <li>
    <a><em>Comments</em> are notes created by the programmer that are included within the program. The compiler ignores these comments as they are only there for the programmer's use</a>
  </li>
  <li>
    <a>In C there are two styles of comments:</a>
    <ul>
      <li>
        <a><em>Single-line comments</em></span>: are denoted with the double forward slash characters, //, and tell the compiler to ignore all code from the two forward slashes to the end of the line of code. Line comments are usually safer</a>
      </li>
      <details>
      <summary>Example Program</summary>

```c
#include <stdio.h>
int main()
{
    printf("Hello world!\n");
    //Everything here is ignored
    return 0;
}
```
<ul>
<details>
  <summary>Output</summary>
    <pre>
      <code>
Hello world!
      </code>
      </pre>  
      </details>
</ul>      
      </details>
      <li>
        <a><em>Multi-line comments</em>: are denoted by the /* and */ set of characters. Everything that is enclosed within the /* and */ set of characters is a comment and therefore ignored by the compiler</a>
      </li>  
      <details>
      <summary>Example Program</summary>

```c      
#include <stdio.h>
int main()
{
    /*This is a multi-line comment.
    This line will be ignored.
    So will this one.*/
    return 0;
}
```
<ul>
<details>
  <summary>Output</summary>
    <pre>
      <code>
      </code>
    </pre>  
    </details>
    </details>
    </ul>
  </li> 
  <li>
    <a>Multi-line comments can be comprised of multiple single-line comments; however, multi-line comments cannot be embedded with any multi-line comments</a>
  </li>       
  <li>
    <a>Comments are useful to explain what certain lines and blocks of code do, especially when other programmers are reading the code</a>
  </li>  
</ul> 

## Variable Assignment and Initialization
<ul>
  <li>
    <a>A <em>variable</em> is a name given to an instance of a data type not defined by the user. The name of this instance is also called an <em>identifier</em>. Variables and identifiers are two words that mean the same thing</a>
  </li>
  <li>
    <a>Every variable must have a <em>type</em> which specifies the type of data that the variable will store</a>
  </li> 
</ul>

### Declaration
<ul>   
  <li>
    <a>A variable must <em>declared</em> before it can be used within the program. To declare a variable within C, two things are needed: first, the <em>type</em> of the variable and then the variable's <em>name</em></a>
    <ul>
      <li>
        <a>Here are two examples of variable declaration:

```c
int height;
float profit;
```
</a>
      </li>
      <li>
        <a>What the declarations above say are that height can store an integer value and float can store a decimal value</a>
      </li>  
    </ul>    
  <li>
    <a>If multiple variables need to be declared of the same type, their declarations can be combined as shown in the following: int height, length, width, volume;</a>
  </li>  
</ul>

### Initialization
<ul>
  <li>
    <a><em>Initialization</em> is the process in which a variable is assigned a memory address</a>
  </li>
  <li>
    <a>After a variable has been defined, it can be assigned a value using the <em>assignment operator</em>. The assignment operator is the equals sign character, =. The process of a variable being initialized is called <em>assignment</em>. Assignment and initialization are two words that mean the same thing</a>
  </li>
  <ul>
    <li>
      <a>int variable = "literal"; //literal on the right side of the assignment operator is assigned to the variable on the left side of the assignment operator</a>
    </li>
  </ul>              
  <li>
    <a>An <em>initializer</em> is the information, whether that be a literal or another variable, that is used to initialize a variable</a>
  </li>
  <li>
    <a>Here are the multiple types of initialization:</a>
    <ul>
      <li>
        <a><em>Default initialization</em>: when a identifier is not assigned an initializer by the user. In this scenario, the variable is assigned a garbage value given by the computer</a>
        <ul>
          <li>
            <a>int a;</a>
          </li>
        </ul>    
      </li>
      <li>
        <a><em>Copy initialization</em>: when an initializer is provided after the identifier and assignment operator</a>
        <ul>
          <li>
            <a>int b = 5;</a>
          </li>
        </ul>
      </li>
      <li>
        <a><em>Copy initialization</em>: when an initializer is provided after the assignment operator within braces</a>
        <ul>
          <li>
            <a>int e = {7}</a>
          </li>
        </ul>
      </li>  
    </ul>
  </li>   
  <li>
    <a>Multiple variables can be initialized on the same line where commas separate each variable's assignment. An example of this is the following: int height = 8, length = 12, width = 10;</a>
  </li> 
  <li>
    <a>A variable that has not been initialized is called an <em>uninitialized variable</em></a>  
    <ul>
      <li>
        <a>Printing out an uninitialized variable to the console causes a random value to be stored in the variable's memory address</a>
      </li>
    </ul>    
  </li>   
</ul>

## Naming and Using Variables
<ul>
  <li>
    <a>There are a few rules that need to be adhered to when initializing variables within C:<a>
    <ul>
      <li>
        <a>Variable names can only contain the following: letters, numbers, and underscores. Variable names can start with letters and underscores, but not numbers. Do not start a variable, however, with an underscore. An identifier cannot contain the following character: -</a>
      </li>
      <li>
        <a>C does not allow spaces within any portion of a variable's name</a>
      </li>
      <li>
        <a>C is a case-sensitive language that distinguishes between upper and lower-case characters in identifiers</a>
      </li>  
      <li>
        <a>A good practice is to avoid using keywords and function names as variable names. An identifier cannot be one of C's keywords</a>
      </li>
    </ul>  
  </li>
</ul>  

## Whitespace and Basic Formatting
<ul>
  <li>
    <a><em>Whitespace</em> is a term that refers to characters that are used for formatting purposes; in C, this refers primarily to spaces, tabs, and newlines</a>
  </li>  
  <li>
    <a>The C compiler generally ignores whitespaces; therefore, C is a whitespace-independent language</a>
    <ul>
      <li>
        <a>The one exception where the C compiler does not pay attention to whitespace is inside quoted text</a>
      </li>
    </ul>    
  </li>  
  <li>
    <a>Variable names cannot contain whitespaces</a>
  </li> 
</ul>

## Introduction to Literals and Operators
<ul>
  <li>
    <a><em>Literals</em> are fixed values that have been inserted directly into the source code</a>
    <ul>
      <li>
        <a>Examples of literals are 1, 2.5, "garrett", and 'c'. These are literals because you cannot assign different values to those terms</a>
      </li>
    </ul>
  </li>
  <li>
    <a><em>Operators</em> are symbols that perform operations on variables and values</a>
    <ul>
      <li>
        <a>Operators can be chained together; the output of one operation can be used as the input for another operator</a>
      </li>
    </ul>
  </li>
</ul>   

## Atomic Data Types and Type Conversion
<ul>
  <li>
    <a><em>bool</em>: has two possible values and stores one of the following: true or false</a>
  </li>
  <li>
    <a><em>string</em>: used to store a list of characters or a single character</a>
    <ul>
      <li>
        <a>C does not have a string type like C++; instead, the creation of an array of type char can be an alternative to make a string</a>
      </li>
    </ul>     
  </li>
</ul>

### Integer
<ul>
  <li>
    <a>Two qualifiers may be applied to C's integer types: signed and unsigned. Identifiers with a variable type of type integer with the signed qualifier represent all positive or negative integers including zero. Identifiers with a variable type of type integer with the unsigned qualifier represent all integers greater than or equal to zero</a>
  </li> 
  <li>
    <a><em>char</em>: typically used to store a character</a>
    <ul>
      <li>
        <a>According to the ASCII table, each character is assigned to an integer meaning that each character on a keyboard can be represented by an integer. char is an integer, but it also represents the integer form of all characters</a>
      </li>
    </ul>    
  </li>
  <li>
    <a><em>int</em>: used to store an integer</a>   
  </li>   
  <li>
    <a>int and char are all signed by default, meaning that the declaration of these variables without the signed qualifier still has the same functionality as if the signed qualifier was included in the identifier's initialization</a>
  </li>   
</ul>  

### Float  
<ul>  
  <li>
    <a><em>float</em>: used to store a decimal number</a>   
  </li>
  <li>
    <a><em>double</em>: used to store a decimal number</a>
    <ul>
      <li>
        <a>long doubles exist which store 10 bytes instead of double which is eight bytes</a>
      </li>
    </ul>    
  </li>
</ul>

### Size Comparisons of Data Types
<ul>    
  <li>
    <a>SMALLEST --- char << int << float << double --- GREATEST</a> 
    <ul>
      <li>
        <a>Smaller data types can be stored in a larger data type. For example, an int can be stored in a float or a double; however, larger data types cannot be stored in a containers of smaller storage types</a>
      </li>
    </ul>     
  </li> 
</ul>

### Format Specifiers
<ul>   
  <li>
    <a>Format specifiers are needed to print variables to the screen. Here is a list of some of the more common format specifiers within C:</a>
    <ul>
      <li>
        <a>%c for displaying/reading in character types</a>
      </li>
      <li>
        <a>%d for displaying/reading in signed integer type in decimal form</a>
      </li>
      <li>
        <a>%e for displaying/reading in floating-point numbers in exponential form</a>
      </li>
      <li>
        <a>%f for displaying/reading in floating-point numbers in decimal form</a>
      </li>
      <li>
        <a>%s for displaying/reading in strings</a> 
      </li>   
      <li>
        <a>%g for displaying/reading in floating-point numbers in either exponential or decimal form</a>
      </li>  
    </ul>
  </li>
</ul>

## Introduction to stdio.h
<ul>
  <li>
    <a><em>Input/output library</em>: is part of C's stdio.h library and deals with basic user input and output. To use this library, it must be included at the top of the program. This is done by adding #include <a><</a><a>stdio.h</a><a>></a>
  </li>
  <li>
    <a><em>printf()</em>: allows for text and information to be printed to the console. No newline character is printed after printf(); therefore, the newline character would need to be included at the end of the print statement</a>
  </li> 
  <details>
  <summary>Example Program</summary>    

```c  
#include <stdio.h>
//
int main()
{
    printf("Hello World!\n"); //prints Hello World! to the console
    //
    return 0;
}
```
<ul>
<details>
  <summary>Output</summary>
    <pre>
      <code>
Hello World!
      </code>
      </pre>  
    </details> 
  </ul>   
  </details>  
  <details>
  <summary>Example Program</summary>    
    
```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    unsigned height = 1, weight = 2;
    //
    printf("Height: %d Length: %d\n", height, weight);
    //
    return 0;
}
```
<ul>
<details>
  <summary>Output</summary>
    <pre>
      <code>
Height: 1 Length: 2
      </code>
    </pre>  
  </details>
  </ul>  
  </details>  
  <li>
    <a><em>scanf()</em>: reads input from the user's keyboard</a>
    <ul>
      <li>
        <a>The ampersand, &, character, is used in the scanf() function in C. In scanf(), the & symbol tells the compiler to store the new value for the variable directly after the & symbol into the memory address that the variable already contains</a>
      </li>
      <li>
        <a>The ampersand symbol is not needed for pointers as a pointer is a memory address rather than a variable which contains a value at a memory address; therefore, for reading in character arrays, no ampersand symbol is needed within scanf()</a>
      </li>  
    </ul>    
  </li>  
  <details>
  <summary>Example Program</summary>    

```c
#include <stdio.h>
//
int main()
{
    //variable declaration and initialization
    char firstLetter;
    //
    printf("What is the first letter of your first name?: ");
    scanf("%c", &firstLetter);
    printf("The first letter of your first name is: %c\n", firstLetter);
    //
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
The first letter of your first name is: G
        </code>
      </pre>  
    </details>
  </ul>  
  </details>  
  <details>
  <summary>Example Program</summary>    

```c
#include <stdio.h>
//
int main()
{
    //variable declaration
    char message[50];
    //
    printf("What is your name: ");
    scanf("%s", message);
    printf("Your name is: %s\n", message);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Your name is: Garrett
        </code>
      </pre>  
    </details>
  </ul>  
  </details>           
</ul> 

## Constant Variables
<ul>
  <li>
    <a><em>Constant variable</em>: a variable whose value cannot change once it is declared and initialized</a>
    <ul>
      <li>
        <a>Must use the keyword <em>const</em> or the define preprocessor directive</a>
      </li>
      <li>
        <a>Must declare and initialize the const variable on the same line</a>
      </li>
      <ul>
        <li>
          <a>const double SIZE = 3.14; //legal</a>
        </li>
        <li>
          <a>const double;<br />SIZE = 3.14; //illegal since variable declaration and initialization do not take place on the same line of code</a>  
        </li>
      </ul>
      <li>
        <a>By convention, the name of all constant variables are uppercase</a>
      </li>  
      <li>
        <a>The syntax for the define preprocessor statement is the following: #define identifier literal and occurs above the main() function</a>
        <ul>
          <li>
            <a>#define PI 3.14159</a>
            <ul>
              <li>
                <a>Now a macro has been defined. The name of the macro is PI and the macro's value is 3.14159</a>
              </li>
            </ul>    
          </li>
        </ul>    
        <details>
        <summary>Example Program</summary>

```c
#include <stdio.h>
//
//preprocessor directives definitions
#define PI 3.14159
//
int main()
{
    printf("Here is the value of PI accurate to four decimal places: %0.4d\n", PI);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
PI: 3.141590
        </code>
        </pre>  
        </details>
        </ul>  
        </details>
        <ul>
          <li>
            <a>When combining macros , the compiler does not compute the embedded macros on the line of declaration; instead, the line of macros, with or without constants, is treated as a line of variables where this line has no greater precedence than the code that comes before or after the macro's call within main or any other function. An example of this is in the following program:</a>
            <ul>
            <details>
            <summary>Example Program</summary>

```c              
#include <stdio.h>
//
//preprocessor directives definitions
#define ONE 1
#define TEN 10
#define HUNDRED ONE + TEN + TEN
#define THOUSAND HUNDRED + TEN
//
int main()
{
    printf("%d\n", THOUSAND * 10);
    //
    return 0;
}
```    
<ul>                 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
121
        </code>
      </pre>  
    </details>
    </ul>  
  </details>
  <details>
    <summary>Example Program</summary>

```c             
#include <stdio.h>
//
//preprocessor directives definitions
#define ONE 1
#define TEN 10
#define HUNDRED ONE + TEN + TEN
#define THOUSAND (HUNDRED + TEN)
//
int main()
{
    printf("%d\n", THOUSAND / 10);
    //
    return 0;
}
```
<ul> 
<details>
  <summary>Output</summary>
    <pre>
      <code>
3
      </code>
    </pre>  
  </details>
  </ul>  
  </details>
  </li>
  </ul>   
  </li> 
  </ul>
  </li>     
</ul>    

## Precision Handling
<ul>
  <li>
    <a>To change the number of decimal places that a variable displays temporarily within the printf() function, some alterations to the format specifier can be made. The %f format specifier can be modified by including the following between the percent symbol and the character f: %.1f. Here the .1 signifies to display the float value rounded to the tenth digit</a>
  </li>
  <li>
    <a>By default, %f displays a number with six digits after the decimal point</a>
  </li>    
  <details>
  <summary>Example Program</summary>

```c
#include <stdio.h>
//
//preprocessor directive for constant variable
#define PI 3.14159
//
int main()
{
    printf("Here is the value of PI accurate to four decimal places: %.4f\n", PI);
    //
    return 0;
}
```  
<ul>
<details>
  <summary>Output</summary>
    <pre>
      <code>
PI: 3.1416
      </code>
      </pre>  
      </details>
    </ul>  
  </details>
</ul>     

## Escape Sequences
<ul>
  <li>
    <a>The backslash, \, is the indicator of an escape sequence</a>
  </li>
  <li>
    <a>Some of the common escape sequences are listed below:</a>
    <ul>
      <li>
        <a>\n: newline</a>
      </li>
      <li>
        <a>\t: tab</a>
      </li>
      <li>
        <a>\\: backslash</a>
      </li>
      <li>
        <a>\": double quote</a>   
      </li>
      <li>
        <a>%%: percent symbol</a> 
      </li>  
      <details>
      <summary>Example Program</summary>

```c        
#include <stdio.h>
//
int main()
{
    printf("This is how to print the backslash key using printf() function: \\");
    printf("This is how to print the quote key using printf() function: \"This is a quote\"");
    printf("This is how to print the percent symbol using printf() function: %%");
    //
    return 0;
}
```
<ul>
<details>
  <summary>Output</summary>
    <pre>
      <code>
This is how to print the backslash key using printf() function: \
This is how to print the quote key using printf() function: "This is a quote"
This is how to print the percent symbol using printf() function: %
      </code>
    </pre>  
  </details>
  </ul>  
</details>     
</ul>
</li>
</ul>

## Arithmetic Operators
<ul>
  <li>
    <a><em>Addition operator</em>: adds the value on the left-hand side of the operator to the value on the right-hand side of the operator</a>
    <ul>
      <li>
        <a>x + y //sums the values x and y</a>
      </li>
    </ul>    
  </li>
  <li>
    <a><em>Subtraction operator</em>: subtracts the value on the right-hand side of the operator from the value on the left-hand side of the operator</a> 
    <ul>
      <li>
        <a>x - y //subtracts the value y from the value x</a>
      </li>
    </ul>    
  </li>
  <li>
    <a><em>Multiplication operator</em>: multiplies the value on the right-hand side of the operator to the value on the left-hand side of the operator</a>
    <ul>
      <li>
        <a>x * y //multiplies the values x and y</a>
      </li>
    </ul>    
  </li>
  <li>
    <a><em>Division operator</em>: divides the value on the left-hand side of the operator by the value on the right-hand side of the operator</a>
    <ul>
      <li>
        <a>x / y //divides the x value by the value y</a>
      </li>
    </ul>    
  </li>
  <li>
    <a><em>Modulus operator</em>: divides the value on the left-hand side of the operator by the value on the right-hand side of the operator and returns the remainder</a>
    <ul>
      <li>
        <a>x % y //finds the remainder of the value x divided by value y</a>
      </li>
    </ul>     
  </li>
</ul>   

## Programming Projects
<details>
  <summary>Write a program that uses printf to display the following picture on the screen:<br />
  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; *<br />
  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; *<br />
  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; *<br />
  &ensp; &ensp; * &ensp; &ensp; &ensp; *<br />
  &ensp; &ensp; &ensp; * &ensp; *<br /> 
  &ensp; &ensp; &ensp; &ensp; *<br /></summary>

```c    
#include <stdio.h>
//
int main()
{
    //code printing checkmark to screen
    printf("       *\n");
    printf("      *\n");
    printf("     *\n");
    printf("*   *\n");
    printf(" * *\n");
    printf("  *\n");
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
       *
      *
     *
*   *
 * *
  *
        </code>
      </pre>  
    </details>
  </ul>  
</details>   

<details>
  <summary>Write a program that computes the volume of a sphere with a 10-meter radius, using the formula v = 4/3&pi;<sup>3</sup><br /></summary>

```c    
#include <stdio.h>
//
//defining PI value using preprocessor directive
#define PI 3.141592653589793
//
int main()
{
    //variable declarations and initializations
    unsigned radius = 10;
    float fraction = 4.0f / 3.0f;
    double result = fraction * PI * radius * radius * radius;
    //
    //printing volume of sphere
    printf("The volume of a sphere with a 10-meter radius is: %0.1fm^3\n", result);
    //
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
The volume of a sphere with a 10-meter radius is: 4188.8m^3 
        </code>
      </pre>  
    </details>
  </ul>  
</details>   

<details>
  <summary>Write a program that computes the volume of a sphere with a r-meter radius that is given by the user, using the formula v = 4/3&pi;<sup>3</sup><br /></summary>

```c    
#include <stdio.h>
//
//defining PI value using preprocessor directive
#define PI 3.141592653589793
//
int main()
{
    //variable declarations and initializations
    unsigned radius;
    float fraction = 4.0f / 3.0f;
    //
    //getting radius of sphere from user
    printf("Enter the radius of the sphere in meters: ");
    scanf("%i", &radius);
    //
    //calculating volume of sphere
    double result = fraction * PI * radius * radius * radius;
    //
    //printing volume of sphere
    printf("The volume of a sphere with a %i-meter radius is: %0.1fm^3\n", radius, result);
    //
    return 0;
}
```
<ul>         
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Enter the radius of the sphere in meters: <u>3</u>
The volume of a sphere with a 3-meter radius is: 113.1m^3
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter a dollars-and-cents amount, then displays the amount with 5% tax added:</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    double amount, tax = 1.05, taxAmount;
    //
    //getting dollars-and-cents amount from the user
    printf("Enter an amount: ");
    scanf("%lf", &amount);
    //
    //calculating the amount accounting for tax
    taxAmount = amount * tax;
    //
    //displaying the final amount including tax
    printf("With tax added: $%0.2f", taxAmount);
    //
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Enter an amount: <u>100.00</u>
With tax added: $105.00
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter a value for x and then displays the value of the following polynomial: 3x<sup>5</sup> + 2x<sup>4</sup> + 5x<sup>3</sup> - x<sup>2</sup> + 7x - 6</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    double xValue, answer;
    //
    //printing polynomial and getting x value from the user
    printf("Polynomial: 3x^5 + 2x^4 - 5x^3 - x^2 + 7x - 6\n");
    printf("Enter in a value for x: ");
    scanf("%lf", &xValue);
    //
    //calculating the polynomial's value with the given x value
    answer = 3 * xValue * xValue * xValue * xValue * xValue + 2 * xValue * xValue * xValue * xValue - 5 * xValue * xValue * xValue - xValue * xValue + 7 * xValue - 6;
    //
    //printing the polynomial's value
    printf("The polynomial's value with %0.2lf substituted for x is %0.2lf\n", xValue, answer);
    //
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Polynomial: 3x^5 + 2x^4 - 5x^3 - x^2 + 7x - 6
Enter in a value for x: -5
The polynomial's value with -5.00 substituted for x is -7566.00
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter a value for x and then displays the value of the following polynomial: ((((3x + 2)x - 5)x - 1)x + 7)x - 6</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    double xValue, answer;
    //
    //printing polynomial and getting x value from the user
    printf("Polynomial: ((((3x + 2)x - 5)x - 1)x + 7)x - 6\n");
    printf("Enter in a value for x: ");
    scanf("%lf", &xValue);
    //
    //calculating the polynomial's value with the given x value
    answer = ((((3 * xValue + 2) * xValue - 5) * xValue - 1) * xValue + 7) * xValue - 6;
    //
    //printing the polynomial's value
    printf("The polynomial's value with %0.2lf substituted for x is %0.2lf\n", xValue, answer);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Polynomial: ((((3x + 2)x - 5)x - 1)x + 7)x - 6
Enter in a value for x: 5
The polynomial's value with 5.00 substituted for x is 10004.00
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter a U.S. dollar amount and then shows how to pay that amount using the smallest number of $20, $10, $5, and $1 bills</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    unsigned total, twenties = 0, tens = 0, fives = 0, singles = 0;
    //
    //getting dollar amount from the user
    printf("Enter a dollar amount: ");
    scanf("%i", &total);
    //
    //calculating the smallest number of $20, $10, $5, and $1 bills
    twenties = total / 20;
    total -= twenties * 20;
    tens = total / 10;
    total -= tens * 10;
    fives = total / 5;
    total -= fives * 5;
    singles = total;
    //
    //printing the smallest number of $20, $10, $5, and $1 bills
    printf("$20 bills: %i\n", twenties);
    printf("$10 bills: %i\n", tens);
    printf(" $5 bills: %i\n", fives);
    printf(" $1 bills: %i\n", singles);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Enter a dollar amount: <u>1297</u>
$20 bills: 64
$10 bills: 1
$5 bills: 1
$1 bills: 2
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that calculates the remaining balance on a loan after the first, second, and third monthly payments</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    float loan, interest, payment;
    //
    //getting information from user regarding remaining balance
    printf("Enter amount of loan: ");
    scanf("%f", &loan);
    printf("Enter interest rate: ");
    scanf("%f", &interest);
    printf("Enter monthly payment: ");
    scanf("%f", &payment);
    //
    //calculating monthly interest rate
    interest = (interest / 12.0 + 100) / 100.0;
    //
    //printing balance information to the screen
    loan = (loan - payment) * interest;
    printf("Balance remaining after first payment: $%.2f\n", loan);
    loan = (loan - payment) * interest;
    printf("Balance remaining after second payment: $%.2f\n", loan);
    loan = (loan - payment) * interest;
    printf("Balance remaining after third payment: $%.2f\n", loan);
    //
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Enter amount of loan: 20000.00
Enter interest rate: 6.0 
Enter monthly payment: 386.66
Balance remaining after first payment: $19711.41
Balance remaining after second payment: $19421.37
Balance remaining after third payment: $19129.88
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
