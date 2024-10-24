<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#integer-types'>Integer Types</a>
  </li> 
  <li>
    <a href='#floating-types'>Floating Types</a>
  </li> 
  <li>
    <a href='#character-types'>Character Types</a>
  </li> 
  <li>
    <a href='#type-conversion'>Type Conversion</a>
  </li> 
  <li>
    <a href='#type-definitions'>Type Definitions</a>
  </li> 
  <li>
    <a href='#the-sizeof-operator'>The sizeof Operator</a>
  </li> 
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>
</ol>
</details>

## Integer Types
<ul>
  <li>
    <a>C supports two different types of numerical data types: integers and floats. Numbers of <em>integer type</em> are whole numbers with no radix point unlike floating type numbers who can have a radix point and numbers to the right of the radix point</a>
  </li>
  <li>
    <a>Integer types are split into two categories: signed or unsigned</a>
    <ul>
      <li>
        <a>The leftmost of a <em>signed integer</em>, also known as the <em>sign bit</em>, is 0 if the integer number is positive or is 1 if the number is negative</a>
      </li>
    </ul>      
  </li> 
  <li>
    <a>When declaring a variable of type int, it will be signed automatically. There are four keywords that help in creating an int that meets the needs of the programmer: long, short, signed, and unsigned</a>
    <ul>
      <li>
        <a>Because of all variables of type int being signed by default, there are six unique combinations of different variables types, all being of type int:</a>
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
</ul>    

| Type | Smallest Value | Largest Value |
| :--- | :------------- | :------------ |
| short int | -32,768 | 32,767 |
| unsigned short int | 0 | 65,535 |
| int | -2,147,483,648 | ,147,483,648 |
| unsigned int | 0 | 4,294,967,295 |
| long int | -9,223,372,036,854,775,808 | 9,223,372,036,854,775,808 |
| unsigned long int | 0 | 18,446,744,073,709,551,615 |

<ul>
  <li>
    <a>In later versions in C, there was the creation of two additional integer types: long long int and unsigned long long int. These types were added because of the need for storing larger integers</a>
  </li>
  <li>
    <a>To force the compiler to treat a constant as a long integer, add either a L or l after the integer such as in the following: 15L</a>
  </li> 
  <li>
    <a>To indicate that a constant is unsigned, add either a U or u after the integer such as in the following: 15U</a>
  </li>
  <li>
    <a>The L and U may be used in conjunction to show that a constant is unsigned and long. The order in which L and U are written does not matter and the case likewise does not matter</a>
  </li>     
  <li>
    <a>To indicate the a constant is a long long int, LL or ll can be added after the constant. Additionally, the U or u can be combined with the LL to indicate that the constant is a long long unsigned int</a>
  </li>  
</ul>        

### Reading and Writing Integers
<ul>
  <li>
    <a>Using unsigned, long, and short integers for scanf and printf require some additional format specifiers:</a>
    <ul>
      <li>
        <a>Use %u for reading and writing unsigned integers</a>
      </li>
      <li>
        <a>Use %hd for reading and writing short integers</a>
      </li>
      <li>
        <a>Use %ld for reading and writing long integers</a>
      </li>
      <li>
        <a>Use %lld for reading and writing long long integers</a>
      </li>      
    </ul>    
  </li>
</ul>    

## Floating Types
<ul>
  <li>
    <a>There are three types of floating-point formats:</a>
    <ul>
      <li>
        <a>float</a>
      </li>
      <li>
        <a>double</a>
      </li>
      <li>
        <a>long double</a>
      </li>
    </ul>        
  </li>
</ul>    

| Type | Smallest Positive Value | Largest Value | Precision |
| :--- | :---------------------- | :------------ | :-------- |
| float | 1.17549 x 10 ^ -38 | 3.40282 x 10 ^ 38 | 6 digits |
| double | 2.22507 x 10 ^ -308 | 1.79769 x 10 ^ 308 | 15 digits |

<ul>
  <li>
    <a>A floating constant must have a radix point and/or an exponent. The exponent indicates that the number that precedes the e is being raised to ten times the number following the e. An optional + or - sign may be added immediately after E or e. Both of the following are floating constants: 57E0 and 57.0</a>
  </li>
  <li>
    <a>To force the compiler to store a floating constant as a float, add an F or an f after the constant</a>
  </li>
  <li>
    <a>To force the compiler to store a floating constant as a long double, add a L or a l after the constant</a>
  </li>    
</ul>    

### Reading and Writing Floats
<ul>
  <li>
    <a>Use %lf for reading and writing doubles</a>
  </li>
  <li>
    <a>Use %Lf for reading and writing long double</a>
  </li>  
</ul>    

## Character Types
<ul>
  <li>
    <a>C treats char values as small integers, which variables of type char are in fact integers</a>
  </li>
  <li>
    <a>Just like with integers, variables of type char also can be signed or unsigned. Signed characters have values from -128 to 127 whereas unsigned characters have values from 0 to 255</a>
  </li>  
  <li>
    <a>chars can either be signed or unsigned when declared and initialized. unsigned char and signed char are legal variable types</a>
  </li>  
</ul>    

### Reading and Writing Characters using getchar and putchar
<ul>
  <li>
    <a>There are alternatives to read and write characters instead of scanf and prinf</a>
  </li>
  <li>
    <a>The putchar function writes a single character to the screen. The function takes in a single character within its parentheses and prints that character to the screen</a>
    <ul>
      <li>
        <a>Here is the syntax for the putchar function: putchar(ch);</a>
      </li> 
    </ul>
  </li>   
  <li>
    <a>The getchar function reads in one character from the user. To save this character, the assignment operator can be used to store that value into a variable of type char</a>
    <ul>
      <li>
        <a>Here is the syntax for the getchar function: ch = getchar();</a>
      </li>
      <li>
        <a>This function actually returns an int value rather than a char one</a>
      </li>  
    </ul>
  </li>  
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>

int main()
{
    //variable declarations and initializations
    int len = 0;
    
    //get the length of the input message/
    printf("Enter a message: ");
    while (getchar() != '\n')
        len++;
    
    printf("Your message was %d character(s) long.\n", len);
    
    return 0;
}
```
  <ul>
  <details>
      <summary>Output</summary>
        <pre>
          <code>   
            Enter a message: <u>Garrett</u>
            Your message was 7 character(s) long.
          </code>
        </pre>  
      </details>
    </ul>  
  </details>       
</ul>   

## Type Conversion
<ul>
  <li>
  <a>There are two different types of type conversion in C: <em>implicit conversion</em> and <em>explicit conversion</em></a>
  <ul>
    <li>
      <a>Implicit conversion happens when:</a>
      <ul>
        <li>
          <a>the operands in an expression are not matching</a>
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
      <a>Explicit conversion happens with <em>type casting</em> which is where the programmer has to manually change to the type of a variable to be of another data type</a>
      <ul>
        <li>
          <a>Here is the syntax for manually converting a variable's data type to another type: (typeName) expression</a>
        </li>
        <details>
          <summary>Example Program</summary>

```c
#include <stdio.h>

int main()
{
    //variable declarations and initializations  
    double x = 1.1, y = 7.2;
    int intx, inty;

    printf("The value of x is: %.1f and the value of y is: %.1f\n", x, y);<br />
    
    //variable initializations
    intx = (int)x;
    inty = (int)y;
    
    printf("The value of x is: %d and the value of y is: %d\n", intx, inty);<br />
    
    return 0;
}
```
<ul>
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
        <li>
          <a>(typeName) is treated as a unary operator so it often has the highest precedence in the statement</a>
        </li>  
      </ul>    
    </li>  
  </ul>  
</ul>     

## Type Definitions
<ul>
  <li>
    <a><em>Type definitions</em> are often useful for creating alias for already established data types in C</a>
    <ul>
      <li>
        <a>Here is the syntax for type definitions: typdef CtypeName createdName;
      <li>
        <a>Here is an example of a typedef: typedef float Dollars; Dollars is now an alias for float. Dollars has the exact same functionality as float--the only difference is that Dollars is called Dollars and not float</a>
      </li>
      <li>
        <a>Type definitions are normally inserted outside of main so they are global variables. This means that it can be used in all functions within the program</a>
      </li>  
    </ul>    
  </li>
</ul>   

## The sizeof Operator
<ul>
  <li>
    <a>To determine how much memory is being used by a data type on one's system, the sizeof operator can be useful</a>
  </li>
  <li>
    <a>Here is the syntax for the sizeof operator: sizeof (typeName) sizeof will return a number of type int which represents how much storage within memory is being used by the variable enclosed within the parentheses</a>
  </li>
</ul>    

## Programming Projects
<details>
  <summary>Write a program that translates an alphabetic phone number into numeric form:<br />
  Enter phone number: <u>CALLATT</u><br />
  2255288<br />
  Here are the letters on the keys: 2 = ABC, 3 = DEF, 4 = GHI, 5 = JKL, 6 = MNO, 7 = PRS, 8 = TUV, 9 = WXY. If the original phone number contains nonalphabetic characters (digits or punctuation, for example), leave them unchanged:<br />
  Enter phone number: <u>1-800-COL-LECT</u><br />
  1-800-265-5328<br />
  Assume that any letters entered by the user are upper case</summary>

```c
#include <stdio.h>

int main()
{
    //variable declarations and initializations
    char ch;
    
    printf("Enter phone number: ");
    
    //while loop which iterates until the user finishes entering its phone number
    while (ch != '\n')
    {
        ch = getchar();

        switch(ch)
        {
            case 'A':
            case 'B':
            case 'C':
                ch = '2';
                break;
            case 'D':
            case 'E':
            case 'F':
                ch = '3';
                break;
            case 'G':
            case 'H':
            case 'I':
                ch = '4';
                break;
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
        
        putchar(ch);
    }
    
    return 0;    
}
```
  <ul>   
    <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter phone number: <u>1-800-GAR-RETT</u>
1-800-427-7388
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>In the SCRABBLE Crossword Game, players form words using small tiles, each containing a letter and a face value. The face value varies from one letter to another, based on the letter's rarity. (Here are the face values: 1: AEILNORSTU, 2: DG, 3: BCMP, 4: FHVWY, 5: K, 8: JX, 10: QZ). Write a program that computes the value of a word by summing the values of its letters:<br />
  Enter a word: <u>pitfall</u><br />
  Scrabble value: 12<br />
  Your program should allow any mixture of lower-case and upper-case letters in the word</summary>

```c
#include <stdio.h>
#include <ctype.h>

int main()
{
    //variable declarations and initializations
    char ch;
    int value = 0;

    printf("Enter a word: ");
    //getting input from the user and calculating the input's scrabble value
    while (ch != '\n')
    {
        ch = toupper(getchar());

        (ch == 'A' || ch == 'E' || ch == 'I' || ch == 'L' || ch == 'N' || ch == 'O' || ch == 'R' || ch == 'S' || ch == 'T' || ch == 'U') ? (value++) : (value);
        (ch == 'D' || ch == 'G') ? (value += 2) : (value);
        (ch == 'B' || ch == 'C' || ch == 'M' || ch == 'P') ? (value += 3) : (value);
        (ch == 'F' || ch == 'H' || ch == 'V' || ch == 'W' || ch == 'Y') ? (value += 4) : (value);
        (ch == 'K') ? (value += 5) : (value);
        (ch == 'J' || ch == 'X') ? (value += 8) : (value);
        (ch == 'Q' || ch == 'Z') ? (value += 10) : (value);
    }
    
    printf("Scrabble value: %d", value);
    
     return 0;
}
```
  <ul>  
    <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a word: <u>pitfall</u>
Scrabble value: 12
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that prints the values of sizeof(int), sizeof(short), sizeof(long), sizeof(float), sizeof(double), and sizeof(long double)</summary>

```c
#include <stdio.h>

int main()
{
    //printing sizes of data types
    printf("Size of int: %d\n", sizeof(int));
    printf("Size of short: %d\n", sizeof(short));
    printf("Size of long: %d\n", sizeof(long));
    printf("Size of float: %d\n", sizeof(float));
    printf("Size of double: %d\n", sizeof(double));
    printf("Size of long double: %d\n", sizeof(long double));
    
    return 0;
}
```
  <ul>
    <details>
    <summary>Output</summary>
      <pre>
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
  <summary>Write a program that asks the user for a 12-hour time, then displays the time in 24-hour form:<br />
  Enter a 12-hour time: <u>9:11 PM</u><br />
  Equivalent 24-hour time: 21:11</summary>

```c
#include <stdio.h>
#include <ctype.h>
#include <stdbool.h>

int main()
{
    //variable declarations and initializations
    int hour, minutes;
    char first, second;
    bool flag = false;

    //do-while loop which loops until the flag is no longer false
    do
    {
        //getting time input from the user
        printf("Enter a 12-hour time: ");
        scanf("%d :%d %c%c", &hour, &minutes, &first, &second);

        //converting characters to uppercase
        first = toupper(first);
        second = toupper(second);
        
        //conditional statement which checks if numerical values for the user's input are value
        if (hour > -1 && hour < 13 && minutes > -1 && minutes < 60)
        {
            //conditional statement which checks if time is valid if hour is equal to 12
            if (hour == 12 && minutes > 0 && first == 'P' && second == 'M')
                continue;
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
        
        //if user input is invalid, print error message and continue to next iteration
        (!flag) ? printf("Invalid time\n") : (flag);
    } while (!flag);
    
    printf("Equivalent 24-hour time: %d:%d\n", hour, minutes);
    
    return 0;
}
```
  <ul>    
    <details>
    <summary>Output</summary>
      <pre>
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

<details>
  <summary>Write a program that counts the number of vowels (a, e, i, o, and u) in a sentence:<br />
  Enter a sentence: <u>And that's the way it is.</u><br />
  Your sentence contains 6 vowels.</summary>

```c
#include <stdio.h>

int main()
{
    //variable declarations and initializations
    char ch;
    int vowelCount = 0;
    //
    printf("Enter a sentence: ");
    //read and count vowels in the user's sentence
    while (ch != '\n')
    {
        ch = toupper(getchar());

        //check if the character is a vowel and increment the count
        (ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U') ? (vowelCount++) : (vowelCount);
    }
    
    printf("Your sentence contains %d vowels.\n", vowelCount);<br />
    
    return 0;
}
```
  <ul>   
    <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a sentence: <u>Garrett is amazing!</u>
Your sentence contains 6 vowels.
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>Write a program that takes a first name and last name entered by the yser and displays the last name, a comma, and the first initial, followed by a period:<br />
  Enter a first and last name: <u>Lloyd Fosdick</u><br />
  Fosdick, L.<br />
  The user's input may contain extra spaces before the first name, between the final and last names, and after the last name</summary>

```c
#include <stdio.h>

int main()
{
    //variable declarations and initializations
    char ch, firstInitial;
    int count = 0;

    printf("Enter a first and last name: ");<br />
    //while loop which runs until the user enters a newline character
    while (ch != '\n')
    {
        ch = getchar();

        //conditional statement which checks if count is equal to zero
        (count == 0 && ch != ' ') ? (firstInitial = ch, count++) : (count);
        //conditional statement which checks if ch is equal to a whitespace character
        (ch == ' ' && count != 0) ? (count = -1) : (count);
        //conditional statement which prints the user's name
        (count < 0 && ch != '\n' && ch != ' ') ? (putchar(ch)) : (count);
    }

    printf(", %c.\n", toupper(firstInitial));

    return 0;
}
```
  <ul>   
    <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a first and last name: <u>             Garrett          Ellis        </u>           
Ellis, G.
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>Write a program that evaluates an expression:<br />
  Enter an expression: <u>1+2.5*3</u><br />
  Value of expression: 10.5<br />
  The operands in the expression are floating-point numbers; the operators are +, -, *, and /. The expression is evaluated from left to right (no operator takes precedence over any other operator).</summary>

```c
#include <stdio.h>

int main()
{
    //variable declarations and initializations
    char ch, operator = 0, priorOperator = 0;
    float temp = 0, frac = 0, firstTemp, final = 0, divisor = 1, counterOperands = 0, runs = 0, wholeDigits = 0, fractionDigits = 0, dotMarker = 0;

    printf("Enter an expression: ");
    //while loop which iterates until the user enters the newline character
    while (ch != '\n')
    {
        ch = getchar();
        
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

        //conditional statements which check if user entered a mathematical operator
        if (ch == '*')
            operator = '*';
        else if (ch == '+')
            operator = '+';
        else if (ch == '-')
            operator = '-';
        else if (ch == '/')
            operator = '/';
        
        //conditional statement which checks if the user entered a mathematical operator or the newline character
        if (ch == '+' || ch == '-' || ch == '*' || ch == '/' || ch == '\n')
        {
            runs++;
            divisor = 1;
            
            //for loop calculating that value of the user's whole number input
            for (int i = 1; i <= wholeDigits; i++, temp *= 10);
            
            //for loop calculating that value of the user's fractional input
            for (int i = 1; i <= fractionDigits; i++, frac *= 10); 
                //conditional statement which adds the user's fractional input to its whole number input if the user input any fractional digits
                if (frac != 0)
                    temp += frac;
            
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
            
            priorOperator = operator;
            temp = frac = wholeDigits = fractionDigits = dotMarker = 0;
        }
    }
    
    printf("Value of expression: %.2f\n", final);
    
    return 0;
}
```
  <ul>   
    <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter an expression: <u>1+2.5*3/2</u>
Value of expression: 5.25
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>Write a program that calculates the average word length for a sentence:<br />
  Enter a sentence: <u>It was deja vu all over again.</u><br />
  Average word length: 3.4<br />
  For simplicity, your program should consider a punctuation mark to be part of the word to which it is attached. Display the average word length to one decimal place.</summary>

```c
#include <stdio.h>

int main()
{
    //variable declarations and initializations
    char ch;
    float average = 0, numLetters = 0, numWords = 0;

    printf("Enter a sentence: ");
    //calculating the average word length using a do-while loop
    do
    {
        ch = getchar();

        //conditional statement which checks if the user's character input is not a whitespace character or a newline character
        if (ch != ' ' && ch != '\n')
            numLetters++;
        //conditional statement which runs if the user's character input is a whitespace character or a newline character
        else
        {
            average += numLetters;
            numLetters = 0;
            numWords++;
        }    
    } while (ch != '\n');

    printf("Average word length: %.1f", average / numWords);
    
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
  Let x be the number entered by the user. Newton's method requires an initial guess y for the square root of x (we will use y = 1). Successive guesses are found by computing the average of y and x/y. The following table shows how thew square root of 3 would be found:<br />

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
int main()
{
    //variable declarations and initializations
    double x, y = 1, oldY, xByy, average, absDifference;
    bool flag = false;
    
    //getting positive number input form the user
    printf("Enter a positive number: ");
    scanf("%lf", &x);
    
    //do-while loop which iterates until flag is no longer true
    do
    {
        oldY = y;
        xByy = x / y;
        y = (xByy + y) / 2;

        //conditional statements which finds the absolute value of the difference between oldY and y
        if (oldY - y < 0)
            absDifference = y - oldY;
        else
            absDifference = oldY - y;
        
        //conditional statement which is responsible for terminating the loop
        if (absDifference < 0.0001 * y)
            flag = true;        
    } while (!flag);

    printf("Square root %.5lf\n", y);
    
    return 0;
}
```
  <ul>   
    <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a positive number: <u>4.5</u>
Square root 2.12132
        </code>
      </pre>  
    </details>
  </ul>  
</details> 
