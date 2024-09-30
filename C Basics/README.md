<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#how-to-run-code'>How to Run Code</a>
  </li>
    <a href='#compiling-and-linking'>Compiling and Linking</a>
  </li> 
  <li>
    <a href='#general-form-of-a-simple-program'>General Form of a Simple Program</a>
  </li>    
  <li>
    <a href='#comments'>Comments</a>
  </li>
  </li>  
  <li>
    <a href='#objects-and-variables'>Objects and Variables</a>
  </li>
    <a href='#variable-assignment-and-initialization'>Variable Assignment and Initialization</a>
  </li>  
  <li>
    <a href='#whitespace-and-basic-formatting'>Whitespace and Basic Formatting</a>
  </li> 
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
    <a href='#introduction-to-stdio.h'>Introduction to stdio.h</a>
    <a href='#introduction-to-stdioh'>Introduction to stdio.h</a>
  </li>  
  <li>
    <a href='#constant-variables'>Constant Variables</a>
    <a href='#arithmetic-operators'>Arithmetic Operators</a>
  </li>  
  <li>
    <a href='#shorthand-assignment-operators'>Shortcut Assignment Operators</a>
  </li>        
  <li>
    <a href='#header-files'>Header Files</a>
  </li>             
    <a href='#programming-projects'>Programming Projects</a>
  </li>    
</ol>
</details>

## How to Run Code
## Compiling and Linking
<ul>
  <li>
    <a>First, go to terminal and within the terminal, type the following command: gcc -Wall fileName.c</a>
    <a>There are three steps in running C code:</a>
    <ul>
      <li>
        <a>The Wall addition enables all warnings, if there are any, will be printed to the programmer</a>
        <a><em>Preprocessing</em>: this is the step where the program is given to the preprocessor which obeys <em>directives</em></a>
      </li>
      <li>
        <a><em>Compiling</em>: the code that was just modified by the preprocessor is now modified by the <em>compiler</em>. The compiler translates the code into <em>object code</em></a>
      </li>  
      <li>
        <a>If there are more than one files associated with a program, the rest of the file names are listed</a>
        <a><em>Linking</em>: this is the final step in running C code where the <em>linker</em> combines the object code produced through the compilation process with any additional code needed to run the program completely. This combination of code creates an executable file which can be used to run the program</a>
      </li>
    </ul>    
  </li>
  <li>
    <a>Then within the terminal, type the following command: ./a.exe</a>
    </ul>
  </li>
  <li>
    <a>Before a program can be executed, three steps are usually necessary:</a>
    <a>To compile code within the terminal of an IDE, proceed with the following. The file that contains the program is called main.c; therefore, its compilation can be accomplished with the following command: gcc -Wall main.c</a>
    <ul>
      <li>
        <a><em>Preprocessing</em> is the first part of a C program's compilation. In this stage, all <em>preprocessor directives</em> are read by the preprocessor. The preprocessor also removes comments from the code and includes and header files associated included in the code</a>
        <ul>
          <li>
            <a>Preprocessor directives usually begin with #. Directives by default are one line long. There are no semicolons or other special markers at the end of the directive. Here is an example of a very common directive: #include <a><</a>stdio.h<a>></a>. <a><</a>stdio.h<a>></a> is a <em>header</em> which contains information about C's standard input and output library. Preprocessor directives are used to include header files and define constants by the preprocessor</a>
          </li>
        </ul>    
        <a>The Wall addition enables all warnings; if there are any warnings, they will be printed on the screen</a>
      </li>
      <li>
        <a><em>Compiling</em> is the second part of a C program's compilation. In this stage, the <em>compiler</em> converts the preprocessed source code into <em>object code</em></a>
      </li>
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
  <li>
    <a>Before a program can be compiled, it needs to be edited first by the preprocessor. The code that is used by the preprocessor is called directives. One very common directive is the <a><</a>stdio.h<a>></a> directive which contains information regarding C's standard input and output processes. By including the line #include <a><</a>stdio.h<a>></a> within a program, the information that is associated with stdio.h library is added to the program before compilation</a>
    <ul>
      <li>
        <a><em>Linking</em> is the third part of a C program's compilation. In this stage, the <em>linker</em> combines object code with any additional code needed to execute the program. This combination of object code is needed to then create an executable file which is done by the linker</a>
      </li>   
    </ul>
  </li>    
        <a>Directives will always start with the # symbol; they will always be only one line long; and they do not need any special marker at the end of the directive (like a semicolon)</a>
      </li>
    </ul>    
  </li>  
  <li>
    <a>A program can also contain additional functions in addition to the main function. The main function is mandatory and is a special function--it is always called when a program executes</a>
  </li>  
  <li>
    <a>The main() function is a mandatory and special function within a C program. The main() function gets executed automatically when the program is run</a>
    <a>At the end of the main function, it normally returns 0;. This statement has two effects: it terminates the main function which ends the program and upon termination, the main function returns the integer zero. The return of the integer zero determines the normal termination of the program</a>
  </li>
  <li>
    <a>The main() function returns a status code, which is a integer as the main() function is of type int. Normally, the return value of main() is zero which indicates that the program terminated normally. If there is no return statement at the end of the main() function, many compilers will produce a warning message</a> 
  </li>     
</ul>      
    <a>A <em>statement</em> is a command that is to be executed upon running the program. An example of a statement is the return 0; statement</a>
  </li>  
</ul>  

## Comments
<ul>
      </li>
      <details>
      <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    printf("Hello world!\n");
    //Everything here is ignored
    //return 0;
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
//
int main()
{
    /*This is a multi-line comment.
    This line will be ignored.
    So will this one.*/
    //
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
        </ul>  
      </details>
      
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
## Variable Assignment and Initialization
<ul>
  <li>
    <a>A <em>variable</em> is a name given to an instance of a data type not defined by the user. The name of this instance is also called an <em>identifier</em>. Variables and identifiers are two words that mean the exact same thing</a>
    <a>A <em>variable</em> is a name given to an instance of a data type not defined by the user. The name of this instance is also called an <em>identifier</em>. Variables and identifiers are two words that mean the same thing</a>
  </li>
  <li>
    <a>Every variable must have a type</a>
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
    </ul>
  </li>   
  <li>
    <a>Multiple variables can be initialized on the same line where commas separate each variable's assignment</a>
    <a>Multiple variables can be initialized on the same line where commas separate each variable's assignment. An example of this is the following: int height = 8, length = 12, width = 10;</a>
  </li> 
  <li>
    <a>A variable that has not been initialized is called an <em>uninitialized variable</em></a>  
    <a>There are a few rules that need to be adhered to when initializing variables within C:<a>
    <ul>
      <li>
        <a>Variable names can only contain the following: letters, numbers, and underscores. Variable names can start with letters and underscores, but not numbers. Do not start a variable; however, with an underscore. An identifier cannot contain the following character: -</a>
        <a>Variable names can only contain the following: letters, numbers, and underscores. Variable names can start with letters and underscores, but not numbers. Do not start a variable, however, with an underscore. An identifier cannot contain the following character: -</a>
      </li>
      <li>
        <a>C does not allow spaces within any portion of a variable's name</a>
      </li>
      <li>
        <a>C is a case sensitive language which distinguishes between upper and lower case characters in identifiers</a>
        <a>C is a case-sensitive language that distinguishes between upper and lower-case characters in identifiers</a>
      </li>  
      <li>
        <a>A good practice is to avoid using keywords and function names as variable names. An identifier cannot be one of C's keywords</a>
      </li>
    </ul>  
  </li>
</ul>   
</ul>  

## Whitespace and Basic Formatting
<ul>
  <li>
    <a><em>Whitespace</em> is a term that refers to characters that are used for formatting purposes; in C++, this refers primarily to spaces, tabs, and newlines</a>
    <a><em>Whitespace</em> is a term that refers to characters that are used for formatting purposes; in C, this refers primarily to spaces, tabs, and newlines</a>
  </li>  
  <li>
    <a>The C compiler generally ignores whitespaces; therefore, C is a whitespace-independent language</a>
      </li>
    </ul>
  </li>
</ul>    
</ul>   

## Atomic Data Types and Type Conversion
<ul>
      </li>
    </ul>     
  </li>
</ul>
### Integer
<ul>
  <li>
    <a>Integer types:</a>
    <ul>
      <li>
        <a>There are two qualifiers that may be applied to C's integer types: signed and unsigned. Identifiers with a variable type of type integer with the signed qualifier represent all positive or negative integers including zero. Identifiers with a variable type of type integer with the unsigned qualifier represent all integers greater than or equal to zero</a>
      </li> 
      <li>
        <a><em>char</em>: typically used to store a character</a>
        <ul>
          <li>
            <a>There are three types of chars which are all the same size of eight bits: char, signed char, and unsigned char</a>
            <ul>
              <li>
                <a>char: is the smallest addressable unit on a computer. char when declared without the signed or unsigned qualifier is NOT by default signed. char can either be signed or unsigned depending on the identifier's initializer</a>
              </li>
              <li>
                <a>signed char: capable of containing the values -127 <= possibleValues <= 127</a>
              </li>
              <li>
                <a>unsigned char: capable of containing the values 0 <= possibleValues <= 255</a>
              </li>    
            </ul>    
          </li>
        </ul>    
      </li>
      <li>
        <a><em>int</em>, <em>short</em>, and <em>long</em>: used to store an integer</a>
        <ul>
          <li>
            <a>short, short int, int, signed, signed short, and signed short int can store integers ranging from -32,767 <= possibleValues <= 32,767. These data types are all 16 bits long</a>
          </li>  
          <li>
            <a>unsigned short, unsigned short int, unsigned int, unsigned can store integers ranging from 0 <= possibleValues <= 65,535. These data types are all 16 bits long</a>
          </li> 
          <li>
            <a>long, long int, signed long, signed long int can store integers ranging from -2,147,483,647 <= possibleValues <= 2,147,483,647. These data types are all 32 bits long</a>
          </li>
          <li>
            <a>unsigned long and unsigned long int can store integers ranging from 0 <= possibleValues <= 4,294,967,295. These data types are all 32 bits long</a>
          </li>    
          <li>
            <a>long long, long long int, signed long long, and signed long long int can store integers ranging from −9,223,372,036,854,775,807 <= possibleValues <= 9,223,372,036,854,775,807. These data types are all 64 bits long</a>
          </li>
          <li>
            <a>unsigned long long and unsigned long long int can store integers ranging from 0 <= possibleValues <= 18,446,744,073,709,551,615. These data types are all 64 bits long</a>
        </ul>    
      </li>   
      <li>
        <a>int, short, and long are all signed by default, meaning that the declaration of these variables without the signed qualifier still have the same functionality as if the signed qualifier was included in the identifier's initialization</a>
      </li>  
    </ul>
    <a>Two qualifiers may be applied to C's integer types: signed and unsigned. Identifiers with a variable type of type integer with the signed qualifier represent all positive or negative integers including zero. Identifiers with a variable type of type integer with the unsigned qualifier represent all integers greater than or equal to zero</a>
  </li> 
  <li>
    <a>Floating point types:</a>
    <a><em>char</em>: typically used to store a character</a>
    <ul>
      <li>
        <a><em>float</em>: used to store a decimal number</a>
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
        <a><em>double</em>: used to store a decimal number</a>
        <ul>
          <li>
            <a>long doubles exists which store 10 bytes instead of double which is eight bytes</a>
          </li>
        </ul>    
        <a>long doubles exist which store 10 bytes instead of double which is eight bytes</a>
      </li>
    </ul>
  </li>   
    </ul>    
  </li>
</ul>
### Size Comparisons of Data Types
<ul>    
  <li>
    <a>SMALLEST --- char << short << int << long << float << double --- GREATEST</a> 
    <a>SMALLEST --- char << int << float << double --- GREATEST</a> 
    <ul>
      <li>
        <a>Smaller data types can be stored in a larger data type. For example, an int can be stored in a float or a double</a>
        <a>Smaller data types can be stored in a larger data type. For example, an int can be stored in a float or a double; however, larger data types cannot be stored in a containers of smaller storage types</a>
      </li>
    </ul>     
  </li>  
  </li> 
</ul>
### Format Specifiers
<ul>   
  <li>
    <a>Format specifiers are needed to print variables to the screen. Here is a list of some of the more common format specifiers within C:</a>
    <ul>
      <li>
        <a>%c for character types</a>
        <a>%c for displaying/reading in character types</a>
      </li>
      <li>
        <a>%d for signed integer type</a>
        <a>%d for displaying/reading in signed integer type in decimal form</a>
      </li>
      <li>
        <a>%e for scientific notation of floats</a>
        <a>%e for displaying/reading in floating-point numbers in exponential form</a>
      </li>
      <li>
        <a>%f for floats and doubles</a>
      </li>
      <li>
        <a>%i for unsigned integers</a>
      </li>  
      <li>
        <a>%li for long</a>
        <a>%f for displaying/reading in floating-point numbers in decimal form</a>
      </li>
      <li>
        <a>%s for string</a> 
        <a>%s for displaying/reading in strings</a> 
      </li>   
    </ul>          
  <li>
    <a>Type conversion:</a>
    <ul>
      <li>
        <a>Can use variable = (dataType)variable; to change the variable's type to dataType</a>
        <details>
        <summary>Example Program</summary>
          <ul>
            <pre>
              <code>
                #include <stdio.h>
                <br />
                int main()
                {
                &emsp;&emsp;//variable declarations and initializations  
                &emsp;&emsp;double x = 1.1, y = 7.2;
                &emsp;&emsp;int intx, inty;
                <br />
                &emsp;&emsp;printf("The value of x is: %.1f and the value of y is: %.1f\n", x, y);
                <br />
                //variable initializations
                &emsp;&emsp;intx = (int)x;
                &emsp;&emsp;inty = (int)y;
                <br />
                &emsp;&emsp;printf("The value of x is: %d and the value of y is: %d\n", intx, inty);
                <br />
                &emsp;&emsp;return 0;
                }
              </code>
            </pre>  
            <details>
            <summary>Output</summary>
              <pre>
                <code>
                  The value of x is: 1.1 and the value of y is: 7.2
                  The value of x is: 1 and the value of y is: 7
                </code>
              </pre>  
            </details>
          </ul>  
        </details>
        <a>%g for displaying/reading in floating-point numbers in either exponential or decimal form</a>
      </li>  
    </ul>     
  </li>                 
</ul>   
    </ul>
  </li>
</ul>

## Introduction to stdio.h
<ul>
  </li> 
  <details>
  <summary>Example Program</summary>    
    <ul>
      <pre>
        <code>
          #include <<a>stdio.h</a>>
          <br />
          int main()
          {
          &emsp;&emsp;printf("Hello World!\n"); //prints Hello World! to the console
          <br />
          &emsp;&emsp;return 0;
          }
        </code>
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
    </details> 
  </ul>   
  </details>  
  <details>
  <summary>Example Program</summary>    
    <ul>
      <pre>
        <code>
          #include <<a>stdio.h</a>>
          <br />
          int main()
          {
          &emsp;&emsp;//variable declarations and initializations
          &emsp;&emsp;unsigned height = 1, weight = 2;
          <br />
          &emsp;&emsp;printf("Height: %d Length: %d\n", height, weight);
          <br />
          &emsp;&emsp;return 0;
          }
        </code>
      </pre>  
      <details>
      <summary>Output</summary>
        <pre>
          <code>
            Height: 1 Length: 2
          </code>
        </pre>  
      </details>
    </ul>  
    
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
  </li>  
  <details>
  <summary>Example Program</summary>    
    <ul>
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
          #include <<a>stdio.h</a>>
          <br />
          int main()
          {
          &emsp;&emsp;//variable declaration and initialization
          &emsp;&emsp;char firstLetter;  
          <br />  
          &emsp;&emsp;printf("What is the first letter of your first name?: ");
          &emsp;&emsp;scanf("%c", &firstLetter);
          &emsp;&emsp;printf("The first letter of your first name is: %c\n", firstLetter);
          <br />
          &emsp;&emsp;return 0;
          }
The first letter of your first name is: G
        </code>
      </pre>  
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
  </ul>  
  </details>  
  <details>
  <summary>Example Program</summary>    
    <ul>
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
          #include <<a>stdio.h</a>>
          <br />
          int main()
          {
          &emsp;&emsp;//variable declaration
          &emsp;&emsp;char message[50];  
          <br />  
          &emsp;&emsp;printf("What is your name: );
          &emsp;&emsp;scanf("%s", message);
          &emsp;&emsp;printf("Your name is: %s\n", message);
          <br />
          &emsp;&emsp;return 0;
          }
Your name is: Garrett
        </code>
      </pre>  
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
  </details>           
</ul> 

        </ul>    
        <details>
        <summary>Example Program</summary>
          <ul>
            <pre>
              <code>
                #include <stdio.h>
                <br />
                #define PI 3.14159
                <br />
                int main()
                {
                &emsp;&emsp;printf("Here is the value of PI accurate to four decimal places: %0.4d\n", PI);
                <br />
                &emsp;&emsp;return 0;
                }
              </code>
            </pre>  
            <details>
            <summary>Output</summary>
              <pre>
                <code>
                  PI: 3.141590
                </code>
              </pre>  
            </details>
          </ul>  
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
      </li> 
    </ul>
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
</ul>    

## Precision Handling
<ul>
  <li>
    <a>To change the number of decimal places that a variable displays temporarily within the printf() function, some alterations to the format specifier can be made. The %f format specifier can be modified by including the following between the percent symbol and the character f: %.1f. Here the .1 signifies to display the float value rounded to the tenths digit</a>
    <a>To change the number of decimal places that a variable displays temporarily within the printf() function, some alterations to the format specifier can be made. The %f format specifier can be modified by including the following between the percent symbol and the character f: %.1f. Here the .1 signifies to display the float value rounded to the tenth digit</a>
  </li>
  <li>
    <a>By default, %f displays a number with six digits after the decimal point</a>
  </li>    
  <details>
  <summary>Example Program</summary>
    <ul>
      <pre>
        <code>
          #include <stdio.h>
          <br />
          //preprocessor directive for constant variable
          #define PI 3.14159
          <br />
          int main()
          {
          &emsp;&emsp;printf("Here is the value of PI accurate to four decimal places: %.4f\n", PI);
          <br />
          &emsp;&emsp;return 0;
          }
        </code>
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
      </li>  
      <details>
      <summary>Example Program</summary>
        <ul>
          <pre>
            <code>
              #include <stdio.h>
              <br />
              int main()
              {
              &emsp;&emsp;printf("This is how to print the backslash key using printf() function: \\");
              &emsp;&emsp;printf("This is how to print the quote key using printf() function: \"This is a quote\"");
              &emsp;&emsp;printf("This is how to print the percent symbol using printf() function: %%");
              <br />
              &emsp;&emsp;return 0;
              }
            </code>
          </pre>  
          <details>
          <summary>Output</summary>
            <pre>
              <code>
                This is how to print the backslash key using printf() function: \<br />
                This is how to print the quote key using printf() function: "This is a quote"<br />
                This is how to print the percent symbol using printf() function: %%<br />
              </code>
            </pre>  
          </details>
        </ul>  
      </details>     
    </ul>
  </li>
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
      </li>
    </ul>     
  </li>
  <li>
    <a><em>Pre-increment operator</em>: incrementing is done before the variable is used within the written line of code</a>
    <ul>
      <li>
        <a>++x; //increases the value of the variable by one integer</a>
      </li>
    </ul>
  </li>
  <li>
    <a><em>Post-increment operator</em>: incrementing is done after the variable is used within the written line of code</a>
    <ul>
      <li>
        <a>x++; /increases the value of the variable by one integer</a>
      </li>
    </ul>
  </li>
  <li>
    <a><em>Pre-decrement operator</em>: decrementing is done before the variable is used within the written line of code</a>
    <ul>
      <li>
        <a>--x; //decreases the value of the variable by one integer</a>  
      </li>
    </ul>
  </li>
  <li>
    <a><em>Post-decrement operator</em>: decrementing is done after the variable is used within the written line of code</a>  
    <ul>
      <li>
        <a>x--; //decreases the value of the variable by one integer</a> 
      </li>
    </ul>
  </li>
</ul>   

## Shorthand Assignment Operators
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
  <li>
    <a><em>Addition assignment operator</em>: adds the value on the right-hand side of the operator to the value on the left-hand side and stores the summation in the variable on the left-hand side of the operator</a>
    <ul>
      <li>
        <a>x += y; //means x equals the sum of x and y</a>
      </li>
      <li>
        <a>--> x = x + y;</a>
      </li>  
    </ul>
  </li>
  <li>
    <a><em>Subtraction assignment operator</em>: subtracts the value on the right-hand side of the operator from the value on the left-hand side and stores the subtraction in the variable on the left-hand side of the operator</a>
    <ul>
      <li>
        <a>x -= y; //means x equals the subtraction of y from x</a>
      </li>
      <li>
        <a>--> x = x - y;</a>
      </li>
    </ul>
  </li>
  <li>
    <a><em>Multiplication assignment operator</em>: multiplies the value on the right-hand side of the operator to the value on the left-hand side and stores the product in the variable on the left-hand side of the operator</a>
    <ul>
      <li>
        <a>x *= y; //means x equals the product of x and y</a>
      </li>
      <li>
        <a>--> x = x * y;</a>
      </li>
    </ul>
  </li>
  <li>
    <a><em>Division assignment operator</em>: divides the value on the left-hand side of the operator to the value on the left-hand side of the operator and stores the division in the variable on the left-hand side of the operator</a>
    <ul>
      <li>
        <a>x /= y; //means x equals x divided by y</a>
      </li>
      <li>
        <a>--> x = x / y;</a>
      </li>
    </ul>
  </li>                  
</ul> 
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
