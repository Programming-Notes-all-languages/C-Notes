<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#compiling-and-linking'>Compiling and Linking</a>
    <a href='#integer-types'>Integer Types</a>
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
    <a href='#floating-types'>Floating Types</a>
  </li> 
  <li>
    <a href='#introduction-to-stdioh'>Introduction to stdio.h</a>
  </li>  
    <a href='#character-types'>Character Types</a>
  </li> 
  <li>
    <a href='#constant-variables'>Constant Variables</a>
    <a href='#type-conversion'>Type Conversion</a>
  </li> 
  <li>
    <a href='#escape-sequences'>Escape Sequences</a>
  </li>
    <a href='#type-definitions'>Type Definitions</a>
  </li> 
  <li>
    <a href='#arithmetic-operators'>Arithmetic Operators</a>
  </li>  
    <a href='#the-sizeof-operator'>The sizeof Operator</a>
  </li> 
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>    
  </li>
</ol>
</details>

## Compiling and Linking
## Integer Types
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
    <a>C supports two different types of numerical data types: integers and floats. Numbers of <em>integer type</em> are whole numbers with no radix point unlike floating type numbers which can have a radix point and numbers to the right of the radix point</a>
  </li>
  <li>
    <a>To compile code within the terminal of an IDE, proceed with the following. The file that contains the program is called main.c; therefore, its compilation can be accomplished with the following command: gcc -Wall main.c</a>
    <a>Integer types are split into two categories: signed or unsigned</a>
    <ul>
      <li>
        <a>The Wall addition enables all warnings; if there are any warnings, they will be printed on the screen</a>
        <a>The leftmost of a <em>signed integer</em>, also known as the <em>sign bit</em>, is 0 if the integer number is positive or is 1 if the number is negative</a>
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
    <a>It is important to note that the main function does not have to be of type int. The main function can be of any data type and can return any value</a>
  </li>  
    </ul>      
  </li> 
  <li>
    <a>Before a program can be compiled, it needs to be edited first by the preprocessor. The code that is used by the preprocessor is called directives. One very common directive is the <a><</a>stdio.h<a>></a> directive which contains information regarding C's standard input and output processes. By including the line #include <a><</a>stdio.h<a>></a> within a program, the information that is associated with stdio.h library is added to the program before compilation</a>
    <a>When declaring a variable of type int, it will be signed automatically. There are four keywords that help in creating an int that meets the needs of the programmer: long, short, signed, and unsigned</a>
    <ul>
      <li>
        <a>Directives will always start with the # symbol; they will always be only one line long; and they do not need any special marker at the end of the directive (like a semicolon)</a>
        <a>Because all variables of type int are signed by default, there are six unique combinations of different variable types, all being of type int:</a>
        <ul>
          <li>
            <a>short int</a>
          </li>
          <li>
            <a>unsigned short int</a>
          </li>
          <li>
            <a>int</a>
          </li>
          <li>
            <a>unsigned int</a>
          </li>
          <li>
            <a>long int</a>
          </li>
          <li>
            <a>unsigned long int</a>
          </li>
        </ul>
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
    </ul>
  </li>              
</ul>    
| Type | Smallest Value | Largest Value |
| :--- | :------------- | :------------ |
| short int | -32,768 | 32,767 |
| unsigned short int | 0 | 65,535 |
| int | -2,147,483,648 | ,147,483,648 |
| unsigned int | 0 | 4,294,967,295 |
| long int | -9,223,372,036,854,775,808 | 9,223,372,036,854,775,808 |
| unsigned long int | 0 | 18,446,744,073,709,551,615 |

## Comments
<ul>
  <li>
    <a><em>Comments</em> are notes created by the programmer that are included within the program. The compiler ignores these comments as they are only there for the programmer's use</a>
    <a>In later versions in C, there was the creation of two additional integer types: long long int and unsigned long long int. These types were added because of the need for storing larger integers</a>
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
    <a>To force the compiler to treat a constant as a long integer, add either an L or l after the integer such as in the following: 15L</a>
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
    <a>To indicate that a constant is unsigned, add either a U or u after the integer such as in the following: 15U</a>
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
    <a>The L and U may be used in conjunction to show that a constant is unsigned and long. The order in which L and U are written does not matter and the case likewise does not matter</a>
  </li>     
  <li>
    <a>If multiple variables need to be declared of the same type, their declarations can be combined as shown in the following: int height, length, width, volume;</a>
    <a>To indicate that a constant is a long long int, LL or ll can be added after the constant. Additionally, the U or u can be combined with the LL to indicate that the constant is a long long unsigned int</a>
  </li>  
</ul>
</ul>        

### Initialization
### Reading and Writing Integers
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
    <a>Using unsigned, long, and short integers for scanf and printf require some additional format specifiers:</a>
    <ul>
      <li>
        <a><em>Default initialization</em>: when a identifier is not assigned an initializer by the user. In this scenario, the variable is assigned a garbage value given by the computer</a>
        <ul>
          <li>
            <a>int a;</a>
          </li>
        </ul>    
        <a>Use %u for reading and writing unsigned integers</a>
      </li>
      <li>
        <a><em>Copy initialization</em>: when an initializer is provided after the identifier and assignment operator</a>
        <ul>
          <li>
            <a>int b = 5;</a>
          </li>
        </ul>
        <a>Use %hd for reading and writing short integers</a>
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
        <a>Use %ld for reading and writing long integers</a>
      </li>
      <li>
        <a>Use %lld for reading and writing long long integers</a>
      </li>      
    </ul>    
  </li>   
</ul>
  </li>
</ul>    

## Naming and Using Variables
## Floating Types
<ul>
  <li>
    <a>There are a few rules that need to be adhered to when initializing variables within C:<a>
    <a>There are three types of floating-point formats:</a>
    <ul>
      <li>
        <a>Variable names can only contain the following: letters, numbers, and underscores. Variable names can start with letters and underscores, but not numbers. Do not start a variable, however, with an underscore. An identifier cannot contain the following character: -</a>
        <a>float</a>
      </li>
      <li>
        <a>C does not allow spaces within any portion of a variable's name</a>
        <a>double</a>
      </li>
      <li>
        <a>C is a case-sensitive language that distinguishes between upper and lower-case characters in identifiers</a>
      </li>  
      <li>
        <a>A good practice is to avoid using keywords and function names as variable names. An identifier cannot be one of C's keywords</a>
        <a>long double</a>
      </li>
    </ul>  
    </ul>        
  </li>
</ul>  
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
| Type | Smallest Positive Value | Largest Value | Precision |
| :--- | :---------------------- | :------------ | :-------- |
| float | 1.17549 x 10 ^ -38 | 3.40282 x 10 ^ 38 | 6 digits |
| double | 2.22507 x 10 ^ -308 | 1.79769 x 10 ^ 308 | 15 digits |

## Introduction to Literals and Operators
<ul>
  <li>
    <a><em>Literals</em> are fixed values that have been inserted directly into the source code</a>
    <ul>
      <li>
        <a>Examples of literals are 1, 2.5, "garrett", and 'c'. These are literals because you cannot assign different values to those terms</a>
      </li>
    </ul>
    <a>A floating constant must have a radix point and/or an exponent. The exponent indicates that the number that precedes the e is being raised to ten times the number following the e. An optional + or - sign may be added immediately after E or e. Both of the following are floating constants: 57E0 and 57.0</a>
  </li>
  <li>
    <a><em>Operators</em> are symbols that perform operations on variables and values</a>
    <ul>
      <li>
        <a>Operators can be chained together; the output of one operation can be used as the input for another operator</a>
      </li>
    </ul>
    <a>To force the compiler to store a floating constant as a float, add an F or an f after the constant</a>
  </li>
</ul>   
  <li>
    <a>To force the compiler to store a floating constant as a long double, add a L or a l after the constant</a>
  </li>    
</ul>    

## Atomic Data Types and Type Conversion
### Reading and Writing Floats
<ul>
  <li>
    <a><em>bool</em>: has two possible values and stores one of the following: true or false</a>
    <a>Use %lf for reading and writing doubles</a>
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
    <a>Use %Lf for reading and writing long double</a>
  </li>  
</ul>    

### Integer
## Character Types
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
    <a>C treats char values as small integers, which variables of type char are in fact integers</a>
  </li>
  <li>
    <a><em>int</em>: used to store an integer</a>   
  </li>   
    <a>Just like with integers, variables of type char also can be signed or unsigned. Signed characters have values from -128 to 127 whereas unsigned characters have values from 0 to 255</a>
  </li>  
  <li>
    <a>int and char are all signed by default, meaning that the declaration of these variables without the signed qualifier still has the same functionality as if the signed qualifier was included in the identifier's initialization</a>
  </li>   
</ul>  
    <a>chars can either be signed or unsigned when declared and initialized. unsigned char and signed char are legal variable types</a>
  </li>  
</ul>    

### Float  
<ul>  
  <li>
    <a><em>float</em>: used to store a decimal number</a>   
  </li>
### Reading and Writing Characters using getchar and putchar
<ul>
  <li>
    <a><em>double</em>: used to store a decimal number</a>
    <ul>
      <li>
        <a>long doubles exist which store 10 bytes instead of double which is eight bytes</a>
      </li>
    </ul>    
    <a>There are alternatives to read and write characters instead of scanf and prinf</a>
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
    <a>The putchar function writes a single character to the screen. The function takes in a single character within its parentheses and prints that character to the screen</a>
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
        <a>Here is the syntax for the putchar function: putchar(ch);</a>
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
  </li>   
  <li>
    <a><em>scanf()</em>: reads input from the user's keyboard</a>
    <a>The getchar function reads one character from the user. To save this character, the assignment operator can be used to store that value into a variable of type char</a>
    <ul>
      <li>
        <a>The ampersand, &, character, is used in the scanf() function in C. In scanf(), the & symbol tells the compiler to store the new value for the variable directly after the & symbol into the memory address that the variable already contains</a>
        <a>Here is the syntax for the getchar function: ch = getchar();</a>
      </li>
      <li>
        <a>The ampersand symbol is not needed for pointers as a pointer is a memory address rather than a variable which contains a value at a memory address; therefore, for reading in character arrays, no ampersand symbol is needed within scanf()</a>
        <a>This function actually returns an int value rather than a char one</a>
      </li>  
    </ul>    
    </ul>
  </li>  
  <details>
  <summary>Example Program</summary>    
    <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declaration and initialization
    char firstLetter;
    //variable declarations and initializations
    int len = 0;
    //
    printf("What is the first letter of your first name?: ");
    scanf("%c", &firstLetter);
    printf("The first letter of your first name is: %c\n", firstLetter);
    //get the length of the input message/
    printf("Enter a message: ");
    while (getchar() != '\n')
        len++;
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
    printf("Your message was %d character(s) long.\n", len);
    //
    return 0;
}
```
<ul>  
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Your name is: Garrett
        <code>   
Enter a message: <u>Garrett</u>
Your message was 7 character(s) long.
        </code>
      </pre>  
    </details>
  </ul>  
  </details>           
</ul> 
  </details>       
</ul>   

## Constant Variables
## Type Conversion
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
  <a>There are two different types of type conversion in C: <em>implicit conversion</em> and <em>explicit conversion</em></a>
  <ul>
    <li>
      <a>Implicit conversion happens when:</a>
      <ul>
        <li>
          <a>const double SIZE = 3.14; //legal</a>
          <a>the operands in an expression do not matching</a>
          <ul>
            <li> 
              <a>The strategy when implicitly converting an operand to match the other when performing arithmetic is to convert the operand of the smaller data type to be the same data type as the other operand</a>
            </li>
            <li>
              <a>Here is the order of data types listed from greatest in size to least in size:</a>
              <ul>
                <li>
                  <a>long double</a>
                </li>
                <li>
                  <a>double</a>
                </li>
                <li>
                  <a>float</a>
                </li>
                <li>
                  <a>unsigned long int</a>
                </li>
                <li>
                  <a>long int</a>
                </li>
                <li>      
                  <a>unsigned int</a>
                </li>
                <li>
                  <a>int</a>
                </li>
                <li>
                  <a>unsigned short int</a>
                </li>
                <li>
                  <a>short int</a>
                </li>
                <li>
                  <a>char</a>
                </li>
              </ul>
            </li> 
            <li>
              <a>When a signed operand is combined with an unsigned operand, the signed operand is converted to unsigned</a>
            </li>                    
          </ul>
        </li>
      </ul>        
    </li>
    <li>
      <a>Explicit conversion happens with <em>type casting</em> which is where the programmer has to manually change the type of a variable to be of another data type</a>
      <ul>
        <li>
          <a>const double;<br />SIZE = 3.14; //illegal since variable declaration and initialization do not take place on the same line of code</a>  
          <a>Here is the syntax for manually converting a variable's data type to another type: (typeName) expression</a>
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
    //variable declarations and initializations  
    double x = 1.1, y = 7.2;
    int intx, inty;
    //
    printf("The value of x is: %.1f and the value of y is: %.1f\n", x, y);
    //
    //variable initializations
    intx = (int)x;
    inty = (int)y; 
    //
    printf("The value of x is: %d and the value of y is: %d\n", intx, inty);
    //
    return 0;
}
    <summary>Output</summary>
      <pre>
        <code>
PI: 3.141590
The value of x is: 1.1 and the value of y is: 7.2<br />
The value of x is: 1 and the value of y is: 7
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
        <li>
          <a>(typeName) is treated as a unary operator so it often has the highest precedence in the statement</a>
        </li>  
      </ul>    
    </li>  
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
## Type Definitions
<ul>
  <li>
    <a>The backslash, \, is the indicator of an escape sequence</a>
  </li>
  <li>
    <a>Some of the common escape sequences are listed below:</a>
    <a><em>Type definitions</em> are often useful for creating aliases for already established data types in C</a>
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
        <a>Here is the syntax for type definitions: typdef CtypeName createdName;
      <li>
        <a>\": double quote</a>   
        <a>Here is an example of a typedef: typedef float Dollars; Dollars is now an alias for float. Dollars have the same functionality as float--the only difference is that Dollars are called Dollars and not float</a>
      </li>
      <li>
        <a>%%: percent symbol</a> 
        <a>Type definitions are normally inserted outside of main so they are global variables. This means that it can be used in all functions within the program</a>
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
</ul>   
## The sizeof Operator
<ul>
  <li>
    <a><em>Division operator</em>: divides the value on the left-hand side of the operator by the value on the right-hand side of the operator</a>
    <ul>
      <li>
        <a>x / y //divides the x value by the value y</a>
      </li>
    </ul>    
    <a>To determine how much memory is being used by a data type on one's system, the sizeof operator can be useful</a>
  </li>
  <li>
    <a><em>Modulus operator</em>: divides the value on the left-hand side of the operator by the value on the right-hand side of the operator and returns the remainder</a>
    <ul>
      <li>
        <a>x % y //finds the remainder of the value x divided by value y</a>
      </li>
    </ul>     
    <a>Here is the syntax for the sizeof operator: sizeof (typeName) sizeof will return a number of type int which represents how much storage within memory is being used by the variable enclosed within the parentheses</a>
  </li>
</ul>   
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
  <summary>Write a program that translates an alphabetic phone number into numeric form:<br />
  Enter phone number: <u>CALLATT</u><br />
  2255288<br />
  Here are the letters on the keys: 2 = ABC, 3 = DEF, 4 = GHI, 5 = JKL, 6 = MNO, 7 = PRS, 8 = TUV, 9 = WXY. If the original phone number contains nonalphabetic characters (digits or punctuation, for example), leave them unchanged:<br />
  Enter phone number: <u>1-800-COL-LECT</u><br />
  1-800-265-5328<br />
  Assume that any letters entered by the user are uppercase</summary>

```c    
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
    //variable declarations and initializations
    char ch;
    //
    printf("Enter phone number: ");
    //
    //while loop which iterates until the user finishes entering its phone number
    while (ch != '\n')
    {
        ch = getchar();
        //
        switch(ch)
        {
            case 'A':
            case 'B':
            case 'C':
                ch = '2';
                break;
            //    
            case 'D':
            case 'E':
            case 'F':
                ch = '3';
                break;
            //    
            case 'G':
            case 'H':
            case 'I':
                ch = '4';
                break;
            //    
            case 'J':
            case 'K':
            case 'L':
                ch = '5';
                break;
            case 'M':
            case 'N':
            case 'O':
                ch = '6';
                break;
            case 'P':
            case 'R':
            case 'S':
                ch = '7';
                break;
            case 'T':
            case 'U':
            case 'V':
                ch = '8';
                break;
            case 'W':
            case 'X':
            case 'Y':
                ch = '9';
                break;
        }
        //
        putchar(ch);
    }
    //
    return 0;    
}
```
<ul>  
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
        <code>
Enter phone number: <u>1-800-GAR-RETT</u>
1-800-427-7388
        </code>
      </pre>  
    </details>
  </ul>  
</details>   
</details>  

<details>
  <summary>Write a program that computes the volume of a sphere with a 10-meter radius, using the formula v = 4/3&pi;<sup>3</sup><br /></summary>
  <summary>In the SCRABBLE Crossword Game, players form words using small tiles, each containing a letter and a face value. The face value varies from one letter to another, based on the letter's rarity. (Here are the face values: 1: AEILNORSTU, 2: DG, 3: BCMP, 4: FHVWY, 5: K, 8: JX, 10: QZ). Write a program that computes the value of a word by summing the values of its letters:<br />
  Enter a word: <u>pitfall</u><br />
  Scrabble value: 12<br />
  Your program should allow any mixture of lower-case and upper-case letters in the word</summary>

```c    
```c
#include <stdio.h>
//
//defining PI value using preprocessor directive
#define PI 3.141592653589793
#include <ctype.h>
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
    char ch;
    int value = 0;
    //
    printf("Enter a word: ");
    //
    //getting input from the user and calculating the input's scrabble value
    while (ch != '\n')
    {
        ch = toupper(getchar());
        //
        (ch == 'A' || ch == 'E' || ch == 'I' || ch == 'L' || ch == 'N' || ch == 'O' || ch == 'R' || ch == 'S' || ch == 'T' || ch == 'U') ? (value++) : (value);
        //
        (ch == 'D' || ch == 'G') ? (value += 2) : (value);
        //
        (ch == 'B' || ch == 'C' || ch == 'M' || ch == 'P') ? (value += 3) : (value);
        //
        (ch == 'F' || ch == 'H' || ch == 'V' || ch == 'W' || ch == 'Y') ? (value += 4) : (value);
        //
        (ch == 'K') ? (value += 5) : (value);
        //
        (ch == 'J' || ch == 'X') ? (value += 8) : (value);
        //
        (ch == 'Q' || ch == 'Z') ? (value += 10) : (value);
    }
    //
    printf("Scrabble value: %d", value);
    //
    return 0;
}
```
<ul> 
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
The volume of a sphere with a 10-meter radius is: 4188.8m^3 
        <code>
Enter a word: <u>pitfall</u>
Scrabble value: 12
        </code>
      </pre>  
    </details>
  </ul>  
</details>   
</details>  

<details>
  <summary>Write a program that computes the volume of a sphere with a r-meter radius that is given by the user, using the formula v = 4/3&pi;<sup>3</sup><br /></summary>
  <summary>Write a program that prints the values of sizeof(int), sizeof(short), sizeof(long), sizeof(float), sizeof(double), and sizeof(long double)</summary>

```c    
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
    //printing sizes of data types
    printf("Size of int: %d\n", sizeof(int));
    printf("Size of short: %d\n", sizeof(short));
    printf("Size of long: %d\n", sizeof(long));
    printf("Size of float: %d\n", sizeof(float));
    printf("Size of double: %d\n", sizeof(double));
    printf("Size of long double: %d\n", sizeof(long double));
    //
    return 0;
}
```
<ul>         
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Enter the radius of the sphere in meters: <u>3</u>
The volume of a sphere with a 3-meter radius is: 113.1m^3
        <code>
Size of int: 4
Size of short: 2
Size of long: 4
Size of float: 4
Size of double: 8
Size of long double: 16
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter a dollars-and-cents amount, then displays the amount with 5% tax added:</summary>
  <summary>Write a program that asks the user for a 12-hour time, then displays the time in the 24-hour form:<br />
  Enter a 12-hour time: <u>9:11 PM</u><br />
  Equivalent 24-hour time: 21:11</summary>

```c
#include <stdio.h>
#include <ctype.h>
#include <stdbool.h>
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
    int hour, minutes;
    char first, second;
    bool flag = false;
    //
    //do-while loop which loops until the flag is no longer false
    do
    {
        //getting time input from the user
        printf("Enter a 12-hour time: ");
        scanf("%d :%d %c%c", &hour, &minutes, &first, &second);
        //
        //converting characters to uppercase
        first = toupper(first);
        second = toupper(second);
        //
        //conditional statement which checks if numerical values for the user's input are value
        if (hour > -1 && hour < 13 && minutes > -1 && minutes < 60)
        {
            //conditional statement which checks if time is valid if hour is equal to 12
            if (hour == 12 && minutes > 0 && first == 'P' && second == 'M')
                continue;
            //    
            //conditional statement which runs if numerical time value is valid    
            else
            {
                //conditional statement if user input PM
                if (first == 'P' && second == 'M')
                {
                    hour += 12;
                    flag = true;
                }
                //conditional statement if user input AM
                else if (first == 'A' && second == 'M')
                    flag = true;
            }    
        }
        //
        //if user input is invalid, print error message and continue to next iteration
        (!flag) ? printf("Invalid time\n") : (flag);
    } while (!flag);
    //
    printf("Equivalent 24-hour time: %d:%d\n", hour, minutes);
    //
    return 0;
}
```
<ul> 
<ul>    
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Enter an amount: <u>100.00</u>
With tax added: $105.00
        <code>
Enter a 12-hour time: <u>22:22 pm</u>
Invalid time
Enter a 12-hour time: <u>-1:00 AM</u>
Invalid time
Enter a 12-hour time: <u>3:11 AM</u>
Equivalent 24-hour time: 3:11
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
</details> 

<details>
  <summary>Write a program that asks the user to enter a value for x and then displays the value of the following polynomial: 3x<sup>5</sup> + 2x<sup>4</sup> + 5x<sup>3</sup> - x<sup>2</sup> + 7x - 6</summary>
  <summary>Write a program that counts the number of vowels (a, e, i, o, and u) in a sentence:<br />
  Enter a sentence: <u>And that's the way it is.</u><br />
  Your sentence contains 6 vowels.</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    double xValue, answer;
    //variable declarations and initializations
    char ch;
    int vowelCount = 0;
    //
    //printing polynomial and getting x value from the user
    printf("Polynomial: 3x^5 + 2x^4 - 5x^3 - x^2 + 7x - 6\n");
    printf("Enter in a value for x: ");
    scanf("%lf", &xValue);
    printf("Enter a sentence: ");
    //
    //calculating the polynomial's value with the given x value
    answer = 3 * xValue * xValue * xValue * xValue * xValue + 2 * xValue * xValue * xValue * xValue - 5 * xValue * xValue * xValue - xValue * xValue + 7 * xValue - 6;
    //read and count vowels in the user's sentence
    while (ch != '\n')
    {
        ch = toupper(getchar());
        //
        //check if the character is a vowel and increment the count
        (ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U') ? (vowelCount++) : (vowelCount);
    }
    //
    //printing the polynomial's value
    printf("The polynomial's value with %0.2lf substituted for x is %0.2lf\n", xValue, answer);
    printf("Your sentence contains %d vowels.\n", vowelCount);
    //
    return 0;
}
```
<ul> 
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Polynomial: 3x^5 + 2x^4 - 5x^3 - x^2 + 7x - 6
Enter in a value for x: -5
The polynomial's value with -5.00 substituted for x is -7566.00
        <code>
Enter a sentence: <u>Garrett is amazing!</u>
Your sentence contains 6 vowels.
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
</details> 

<details>
  <summary>Write a program that asks the user to enter a value for x and then displays the value of the following polynomial: ((((3x + 2)x - 5)x - 1)x + 7)x - 6</summary>
  <summary>Write a program that takes a first name and last name entered by the user and displays the last name, a comma, and the first initial, followed by a period:<br />
  Enter a first and last name: <u>Lloyd Fosdick</u><br />
  Fosdick, L.<br />
  The user's input may contain extra spaces before the first name, between the final and last names, and after the last name</summary>

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
    //variable declarations and initializations
    char ch, firstInitial;
    int count = 0;
    //
    printf("Enter a first and last name: ");
    //
    //while loop which runs until the user enters a newline character
    while (ch != '\n')
    {
        ch = getchar();
        //
        //conditional statement which checks if count is equal to zero
        (count == 0 && ch != ' ') ? (firstInitial = ch, count++) : (count);
        //
        //conditional statement which checks if ch is equal to a whitespace character
        (ch == ' ' && count != 0) ? (count = -1) : (count);<
        //
        //conditional statement which prints the user's name
        (count < 0 && ch != '\n' && ch != ' ') ? (putchar(ch)) : (count);
    }
    //
    printf(", %c.\n", toupper(firstInitial));
    //
    return 0;
}
```
<ul>
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Polynomial: ((((3x + 2)x - 5)x - 1)x + 7)x - 6
Enter in a value for x: 5
The polynomial's value with 5.00 substituted for x is 10004.00
        <code>
Enter a first and last name: <u>             Garrett          Ellis        </u>           
Ellis, G.
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
</details> 

<details>
  <summary>Write a program that asks the user to enter a U.S. dollar amount and then shows how to pay that amount using the smallest number of $20, $10, $5, and $1 bills</summary>
  <summary>Write a program that evaluates an expression:<br />
  Enter an expression: <u>1+2.5*3</u><br />
  Value of expression: 10.5<br />
  The operands in the expression are floating-point numbers; the operators are +, -, *, and /. The expression is evaluated from left to right (no operator takes precedence over any other operator).</summary>

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
    char ch, operator = 0, priorOperator = 0;
    float temp = 0, frac = 0, firstTemp, final = 0, divisor = 1, counterOperands = 0, runs = 0, wholeDigits = 0, fractionDigits = 0, dotMarker = 0;
    //
    printf("Enter an expression: ");
    //
    //while loop which iterates until the user enters the newline character
    while (ch != '\n')
    {
        ch = getchar();
        //
        //conditional statement which checks if user entered a whole number digit
        if (ch >= '0' && ch <= '9' && dotMarker == 0)
        {
            temp += ((float)(ch - 48)) / (divisor *= 10);
            wholeDigits++;
        }
        //conditional statement which checks if user entered a fractional number digit
        else if (ch == '.' || (dotMarker > 0 && ch >= '0' && ch <= '9'))
            if (dotMarker++ != 0)
            {
                frac += ((float)(ch - 48)) / (divisor *= 10);
                fractionDigits++;
            }
        //    
        //conditional statements which check if user entered a mathematical operator
        if (ch == '*')
            operator = '*';
        //    
        else if (ch == '+')
            operator = '+';
        //    
        else if (ch == '-')
            operator = '-';
        //    
        else if (ch == '/')
            operator = '/';
        //    
        //conditional statement which checks if the user entered a mathematical operator or the newline character
        if (ch == '+' || ch == '-' || ch == '*' || ch == '/' || ch == '\n')
        {
            runs++;
            divisor = 1;
            //
            //for loop calculating that value of the user's whole number input
            for (int i = 1; i <= wholeDigits; i++, temp *= 10);
            //
            //for loop calculating that value of the user's fractional input
            for (int i = 1; i <= fractionDigits; i++, frac *= 10);
            //conditional statement which adds the user's fractional input to its whole number input if the user input any fractional digits
            if (frac != 0)
                temp += frac;
            //
            //conditional statement which performs the mathematical operation and stores the result in the final variable if this is the first operation performed
            if (runs < 3)
            {
                if (counterOperands++ == 0)
                    firstTemp = temp;
                else
                {
                    if (priorOperator == '*')
                        final += firstTemp * temp;
                    else if (priorOperator == '+')
                        final += firstTemp + temp;
                    else if (priorOperator == '-')
                        final += firstTemp - temp;
                    else if (priorOperator == '/')
                        final += firstTemp / temp;    
                }
            }
            //
            //conditional statement which performs the mathematical operation and stores the result in the final variable if this is not the first operation performed
            else if (runs > 2)
            {
                if (priorOperator == '*')
                    final *= temp;
                else if (priorOperator == '+')
                    final += temp;
                else if (priorOperator == '-')
                    final -= temp;
                else if (priorOperator == '/')
                    final /= temp;
            }
            //
            priorOperator = operator;
            temp = frac = wholeDigits = fractionDigits = dotMarker = 0;
        }
    }
    //
    printf("Value of expression: %.2f\n", final);
    //
    return 0;
}
  <details>
    <summary>Output</summary>
      <pre>
        <code>    
Enter a dollar amount: <u>1297</u>
$20 bills: 64
$10 bills: 1
$5 bills: 1
$1 bills: 2
        <code>
Enter an expression: <u>1+2.5*3/2</u>
Value of expression: 5.25
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
</details> 

<details>
  <summary>Write a program that calculates the remaining balance on a loan after the first, second, and third monthly payments</summary>
  <summary>Write a program that calculates the average word length for a sentence:<br />
  Enter a sentence: <u>It was deja vu all over again.</u><br />
  Average word length: 3.4<br />
  For simplicity, your program should consider a punctuation mark to be part of the word to which it is attached. Display the average word length to one decimal place.</summary>

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
    //variable declarations and initializations
    char ch;
    float average = 0, numLetters = 0, numWords = 0;
    //
    printf("Enter a sentence: ");
    //
    //calculating the average word length using a do-while loop
    do
    {
        ch = getchar();
        //
        //conditional statement which checks if the user's character input is not a whitespace character or a newline character
        if (ch != ' ' && ch != '\n')
            numLetters++;
        //    
        //conditional statement which runs if the user's character input is a whitespace character or a newline character
        else
        {
            average += numLetters;
            numLetters = 0;
            numWords++;
        }    
    } while (ch != '\n');
    //
    printf("Average word length: %.1f", average / numWords);
    //
    //printing balance information to the screen
    loan = (loan - payment) * interest;
    printf("Balance remaining after first payment: $%.2f\n", loan);
    loan = (loan - payment) * interest;
    printf("Balance remaining after second payment: $%.2f\n", loan);
    loan = (loan - payment) * interest;
    printf("Balance remaining after third payment: $%.2f\n", loan);
    return 0;
}
```
<ul>    
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a sentence: <u>It was deja vu all over again.</u>
Average word length: 3.4
        </code>
      </pre>  
    </details>
  </ul>  
</details> 
<details>
  <summary>Write a program that uses Newton's method to compute the square root of a positive floating-point number:<br />
  Enter a positive number: <u>3</u><br />
  Square root: <u>1.73205</u><br />
  Let x be the number entered by the user. Newton's method requires an initial guess y for the square root of x (we will use y = 1). Successive guesses are found by computing the average of y and x/y. The following table shows how the square root of 3 would be found:<br />
| x | y | x/y | Average of y and x/y |
| :- | :- | :- | :- |  
| 3 | 1 | 3 | 2 |
| 3 | 2 | 1.5 | 1.75 |
| 3 | 1.75 | 1.71429 | 1.73214 |
| 3 | 1.73214 | 1.73196 | 1.73205 |
| 3 | 1.73205 | 1.73205 | 1.73205 |
Note that the values of y get progressively closer to the true square root of x. Have the program terminate when the absolute value of the difference between the old value of y and the new value of y is less than the product of 0.00001 and y.</summary>
```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    double x, y = 1, oldY, xByy, average, absDifference;
    bool flag = false;
    //
    //getting positive number input form the user
    printf("Enter a positive number: ");
    scanf("%lf", &x);
    //
    //do-while loop which iterates until flag is no longer true
    do
    {
        oldY = y;
        xByy = x / y;
        y = (xByy + y) / 2;
        //
        //conditional statements which finds the absolute value of the difference between oldY and y
        if (oldY - y < 0)
            absDifference = y - oldY;
        else
            absDifference = oldY - y;
        //    
        //conditional statement which is responsible for terminating the loop
        if (absDifference < 0.0001 * y)
            flag = true;        
    } while (!flag);
    //
    printf("Square root %.5lf\n", y);
    //
    return 0;
}
```
<ul> 
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
        <code>
Enter a positive number: <u>4.5</u>
Square root 2.12132
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
</details> 
