<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#how-to-run-code'>How to Run Code</a>
  </li>
  <li>
    <a href='#comments'>Comments</a>
  </li>
  <li>
    <a href='#objects-and-variables'>Objects and Variables</a>
  </li>
  <li>
    <a href='#whitespace-and-basic-formatting'>Whitespace and Basic Formatting</a>
  </li> 
  <li>
    <a href='#introduction-to-literals-and-operators'>Introduction to Literals and Operators</a>
  </li>
  <li>
    <a href='#atomic-data-types-and-type-conversion'>Atomic Data Types and Type Conversion</a>
  </li>
  <li>
    <a href='#introduction-to-stdio.h'>Introduction to stdio.h</a>
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
    <a href='#shorthand-assignment-operators'>Shortcut Assignment Operators</a>
  </li>        
  <li>
    <a href='#header-files'>Header Files</a>
  </li>             
</ol>
</details>

## How to Run Code
<ul>
  <li>
    <a>First, go to terminal and within the terminal, type the following command: gcc -Wall fileName.c</a>
    <ul>
      <li>
        <a>The Wall addition enables all warnings, if there are any, will be printed to the programmer</a>
      </li>  
      <li>
        <a>If there are more than one files associated with a program, the rest of the file names are listed</a>
      </li>
    </ul>    
  </li>
  <li>
    <a>Then within the terminal, type the following command: ./a.exe</a>
  </li>
  <li>
    <a>Before a program can be executed, three steps are usually necessary:</a>
    <ul>
      <li>
        <a><em>Preprocessing</em> is the first part of a C program's compilation. In this stage, all <em>preprocessor directives</em> are read by the preprocessor. The preprocessor also removes comments from the code and includes and header files associated included in the code</a>
        <ul>
          <li>
            <a>Preprocessor directives usually begin with #. Directives by default are one line long. There are no semicolons or other special markers at the end of the directive. Here is an example of a very common directive: #include <a><</a>stdio.h<a>></a>. <a><</a>stdio.h<a>></a> is a <em>header</em> which contains information about C's standard input and output library. Preprocessor directives are used to include header files and define constants by the preprocessor</a>
          </li>
        </ul>    
      </li>
      <li>
        <a><em>Compiling</em> is the second part of a C program's compilation. In this stage, the <em>compiler</em> converts the preprocessed source code into <em>object code</em></a>
      </li>
      <li>
        <a><em>Linking</em> is the third part of a C program's compilation. In this stage, the <em>linker</em> combines object code with any additional code needed to execute the program. This combination of object code is needed to then create an executable file which is done by the linker</a>
      </li>   
    </ul>
  </li>    
  <li>
    <a>The main() function is a mandatory and special function within a C program. The main() function gets executed automatically when the program is run</a>
  </li>
  <li>
    <a>The main() function returns a status code, which is a integer as the main() function is of type int. Normally, the return value of main() is zero which indicates that the program terminated normally. If there is no return statement at the end of the main() function, many compilers will produce a warning message</a> 
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
        <ul>
          <pre>
            <code>
              #include <<a>stdio.h</a>>
              <br />
              int main()
              {
                  printf("Hello world!\n");
                  //Everything here is ignored
                  <br />
                  return 0;
              }
            </code>
          </pre>    
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
        <ul>
          <pre>
            <code>
              #include <<a>stdio.h</a>>
              using namespace std;
              <br />
              int main()
              {
                  /*This is a multi-line comment.
                  This line will be ignored.
                  So will this one.*/
                  <br />
                  return 0;
              }
            </code>
          </pre>  
          <details>
          <summary>Output</summary>
            <pre>
              <code>
                <br />
              </code>
            </pre>  
          </details>
        </ul>  
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
    <a>A <em>variable</em> is a name given to an instance of a data type not defined by the user. The name of this instance is also called an <em>identifier</em>. Variables and identifiers are two words that mean the exact same thing</a>
  </li>
  <li>
    <a>Every variable must have a type</a>
  </li>  
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
    <a>Multiple variables can be initialized on the same line where commas separate each variable's assignment</a>
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
        <a>Variable names can only contain the following: letters, numbers, and underscores. Variable names can start with letters and underscores, but not numbers. Do not start a variable; however, with an underscore. An identifier cannot contain the following character: -</a>
      </li>
      <li>
        <a>C does not allow spaces within any portion of a variable's name</a>
      </li>
      <li>
        <a>C is a case sensitive language which distinguishes between upper and lower case characters in identifiers</a>
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
    <a><em>Whitespace</em> is a term that refers to characters that are used for formatting purposes; in C++, this refers primarily to spaces, tabs, and newlines</a>
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
  </li> 
  <li>
    <a>Floating point types:</a>
    <ul>
      <li>
        <a><em>float</em>: used to store a decimal number</a>
      </li>
      <li>
        <a><em>double</em>: used to store a decimal number</a>
        <ul>
          <li>
            <a>long doubles exists which store 10 bytes instead of double which is eight bytes</a>
          </li>
        </ul>    
      </li>
    </ul>
  </li>   
  <li>
    <a>SMALLEST --- char << short << int << long << float << double --- GREATEST</a> 
    <ul>
      <li>
        <a>Smaller data types can be stored in a larger data type. For example, an int can be stored in a float or a double</a>
      </li>
    </ul>     
  </li>  
  <li>
    <a>Format specifiers are needed to print variables to the screen. Here is a list of some of the more common format specifiers within C:</a>
    <ul>
      <li>
        <a>%c for character types</a>
      </li>
      <li>
        <a>%d for signed integer type</a>
      </li>
      <li>
        <a>%e for scientific notation of floats</a>
      </li>
      <li>
        <a>%f for floats and doubles</a>
      </li>
      <li>
        <a>%i for unsigned integers</a>
      </li>  
      <li>
        <a>%li for long</a>
      </li>
      <li>
        <a>%s for string</a> 
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
    <ul>
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
  <details>
  <summary>Example Program</summary>    
    <ul>
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
        </details>
      </li> 
    </ul>
  </li>     
</ul>      

## Precision Handling
<ul>
  <li>
    <a>To change the number of decimal places that a variable displays temporarily within the printf() function, some alterations to the format specifier can be made. The %f format specifier can be modified by including the following between the percent symbol and the character f: %.1f. Here the .1 signifies to display the float value rounded to the tenths digit</a>
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
