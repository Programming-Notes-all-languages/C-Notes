<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#the-printf-function'>The printf Function</a>
  </li> 
  <li>
    <a href='#the-scanf-function'>The scanf Function</a>
  </li>
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>
</ol>
</details>

## The printf Function
<ul>
  <li>
    <a>The printf function displays the contents of a string, which is called the <em>format string</em>, with values that may or may not be inserted within the printf function</a>
  </li>
  <li>
    <a>The format string may contain both strings of characters and <em>conversion specifiers</em> which begin with the % character. The conversion specifiers represent the temporary spot for where a value will be used during the printf function run</a>
  </li>
  <li>
    <a>There are multiple ways to format numbers within C:</a>
    <ul>
      <li>
        <a>printf("%5d\n", 5); --> %5d: displays 5 in decimal form with a minimum of five characters. Since 5 is only one character long and the conversion specifier says that the integer five must be represented using five characters, four white spaces are added in front of 5</a>
      </li>
      <li>
        <a>printf("%-5d\n", 5); --> %-5d: displays 5 in decimal form with a minimum of five characters. Since 5 is only one character long and the conversion specifier says that the integer five must be represented using five characters, four white spaces are added behind 5</a>
      </li>
      <li>
        <a>printf("%5.3d\n", 5); --> %5.3d: displays 5 in decimal form in a minimum of five characters where at least three of those characters being digits</a>
      </li>    
      <li>
        <a>printf("%10.3f\n", 839.21); --> %10.3f: displays 839.21 in decimal form using a minimum of ten characters with three digits to the right of the radix</a>
      </li> 
      <li>
        <a>printf("%10.3e\n", 839.21); --> %10.3e: displays 839.21 in exponential form using a minimum of ten characters overall with three digits after the radix</a>
      </li>  
      <li>
        <a>printf("%-10g\n", 839.21); --> %-10g: displays 839.21 in either decimal form or exponential form using a minimum of ten characters</a>
        <ul>
          <li>
            <a>The g specifier is useful for displaying numbers whose values cannot be predicted before writing the program. This specifier has instructions built in to display numbers in exponential form if the number is either very small or very large and to display the number in decimal form if the number is either moderately small or moderately large</a>
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
    //variable declarations and initializations
    int num = 5;
    float decimalNum = 3.14159;
    //
    //printing statements to screen
    printf("Printing %%5d -->%5d<--\n", num);
    printf("Printing %%-5d -->%-5d<--\n", num);
    printf("Printing %%5.3d -->%5.3d<--\n", num);
    printf("Printing %%5.3f -->%5.3f<--\n", decimalNum);
    printf("Printing %%10.3e -->%10.3e<--\n", decimalNum);
    printf("Printing %%-10g -->%-10g<--\n", decimalNum);
    //
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Printing %5d -->    5<--
Printing %-5d -->5    <--
Printing %5.3d -->  005<--
Printing %5.3f -->3.142<--
Printing %10.3e --> 3.142e+00<--
Printing %-10g -->3.14159   <--
        </code>
      </pre>  
    </details>
    </ul>  
    </details>  
    </ul>  
  </li>    
</ul>    

## The scanf Function
<ul>
  <li>
    <a>Unlike the printf function that outputs data to the screen, the scanf function takes in information that is entered by the user. When scanf is called, it begins to read the information within if format string like with the printf function</a>
  </li>
  <li>
    <a>The scanf format string, alike printf's format string, may contain characters along with conversion specifiers</a>
  </li>
  <li>
    <a>The & symbol is often required when using the scanf function, but it is not always required</a>
  </li>  
  <li>
    <a>scanf also ignores <em>white-space characters</em> when the user inputs information to the screen</a>
  </li>  
  <li>
    <a>Since scanf skips over white-space characters, it looks for the beginning of each new number, if requesting the user to enter multiple numbers. If the user inputs multiple lines of input, the character immediately following the new-line character will be the first character read for the next call of the scanf function</a>
    <ul>
      <li>
        <a>When asking the user to enter an integer, scanf first searches for a digit, a plus sign (+), or a minus sign (-). Then, it continues to read digit characters, until it stumbles upon a character that is not valid (either a newline character or a white-space character). Then, scanf will move on to the next conversion specifier. Reading in a character that is not a digit, white-space, +, -, or a new line character will cause scanf to terminate</a> 
      </li>  
      <li>
        <a>When asking the user to enter a float, scanf first searches for a digit, a plus sign (+), or a minus sign (-). Then, it continues to read digit characters, or even an optional exponent character (e or E) with one or more digits following, until it stumbles upon a character that is not valid (either a newline character or a white-space character). Then, scanf will move on to the next conversion specifier. Reading in a character that is not a digit, white-space, +, -, e, E, or a new line character </a>  
      </li>
    </ul>
  </li>   
  <li>
    <a>Sometimes, there can be characters within the format string. If there are white-space characters within the format string, it does not force the user's input to contain white-space characters</a> 
    <ul>
      <li>
        <a>For example, let's say that the format string is the following: "%d /%d". The scanf function is first going to look for a digit, a plus sign (+), or a minus sign (-) while throwing out any white-space characters that the user enters before one of the previously listed characters. Once a digit is no longer entered, then the function will look for the / character. The space between %d and / in this scanf format function enables there to be any number of white spaces between the last digit the user entered and the / character. Then, scanf will read in an integer using the same procedure as outlined above</a>
      </li>
    </ul>    
  </li>
</ul>     

## Programming Projects
<details>
  <summary>Write a program that accepts a date from the user in the form mm/dd/yyyy and then displays it in the form yyyymmdd</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    int month, day, year;
    //
    //getting date information from the user
    printf("Enter a date (mm/dd/yyyy): ");
    scanf("%d /%d /%d", &month, &day, &year);
    //
    //printing user's date information
    printf("You entered the date %d%d%d", year, month, day);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a date (mm/dd/yyyy): <u>03/ 11/2003</u>
You entered the date 2003311
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>Write a program that formats product information entered by the user. A session with the program should look like the this:<br />
  Enter item number: <u>583</u><br />
  Enter unit price: <u>13.5</u><br />
  Enter purchase date (mm/dd/yyyy): <u>10/24/2010</u><br />
  Item&emsp;&emsp;&emsp;&emsp;Unit&emsp;&emsp;&emsp;&emsp; &emsp; Purchase<br />
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Price&emsp;&emsp;&emsp;  &emsp;&emsp;Date<br />
  583&emsp;&emsp;&emsp;&emsp; $&emsp;13.50 &emsp;&emsp;&emsp; 10/24/2010<br />
  The item number and date should be left justified; the unit price should be right justified. Allow dollar amounts up to $9999.99</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    int item, month, day, year;
    float price;
    //
    //getting information from the user
    printf("Enter item number: ");
    scanf("%d", &item);
    printf("Enter unit price: ");
    scanf("%f", &price);
    printf("Enter purchase date (mm/dd/yyyy): ");
    scanf("%d /%d /%d", &month, &day, &year);
    //
    //printing user's information
    printf("Item\t\tUnit\t\tPurchase\n\t\tPrice\t\tDate\n");
    printf("%-d\t\t$%7.2f\t%d/%d/%d", item, price, month, day, year);
    //
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter item number: <u>583</u>
Enter unit price: <u>13.5</u>
Enter purchase date (mm/dd/yyyy): <u>10/24/2010</u>
Item            Unit            Purchase
Price           Date
583             $  13.50        10/24/2010
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>Write a program that breaks down an ISBN entered by the user:<br />
  Enter ISBN: <u>978-0-393-97950-3</u><br />
  GSI prefix: 978<br />
  Group identifier: 0<br />
  Publisher code: 393<br />
  Item number: 97950<br />
  Check digit: 3<br /></summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    int GSI, identifier, code, number, digit;
    //
    //getting ISBN from the user
    printf("Enter ISBN: ");
    scanf("%d -%d -%d -%d -%d", &GSI, &identifier, &code, &number, &digit);
    //
    //printing information that the user input
    printf("GSI prefix: %d\n", GSI);
    printf("Group identifier: %d\n", identifier);
    printf("Publisher code: %d\n", code);
    printf("Item number: %d\n", number);
    printf("Check digit: %d\n", digit);
    //
    return 0;    
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter ISBN: <u>978</u>
<u>- 0 - 393</u>
<u>-97950   -  3</u>
GSI prefix: 978
Group identifier: 0
Publisher code: 393
Item number: 97950
Check digit: 3    
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>Write a program that asks the user to enter the numbers from 1 to 16 (in any order) and then displays the numbers in a 4 by 4 arrangement, followed by the sums of the rows, columns, and diagonals:<br />
  Enter the numbers from 1 to 16 in any order:<br />
  <u>16 3 2 13 5 10 11 8 9 6 7 12 4 15 14 1</u><br />
  16  3  2 13<br />
   5 10 11  8<br />
   9  6  7 12<br />
   4 15 14  1<br />
  Row sums: 34 34 34 34<br />
  Column sums: 34 34 34 34<br /> 
  Diagonal sums: 34 34<br />
  </summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    int num1, num2, num3, num4, num5, num6, num7, num8, num9, num10, num11, num12, num13, num14, num15, num16;
    //
    //getting the user's number inputs
    printf("Enter the numbers from 1 to 16 in any order:\n");
    scanf("%d%d%d%d%d%d%d%d%d%d%d%d%d%d%d%d", &num1, &num2, &num3, &num4, &num5, &num6, &num7, &num8, &num9, &num10, &num11, &num12, &num13, &num14, &num15, &num16);
    //
    //printing user's numbers
    printf("%3d %3d %3d %3d", num1, num2, num3, num4);
    printf("\n%3d %3d %3d %3d", num5, num6, num7, num8);
    printf("\n%3d %3d %3d %3d", num9, num10, num11, num12);
    printf("\n%3d %3d %3d %3d", num13, num14, num15, num16);
    //
    //printing summation information
    printf("\nRow sums: %d %d %d %d", num1 + num2 + num3 + num4, num5 + num6 + num7 + num8, num9 + num10 + num11 + num12, num13 + num14 + num15 + num16);
    printf("\nColumn sums: %d %d %d %d", num1 + num5 + num9 + num13, num2 + num6 + num10 + num14, num3 + num7 + num11 + num15, num4 + num8 + num12 + num16);
    printf("\nDiagonal sums: %d %d", num1 + num6 + num11 + num16, num4 + num7 + num10 + num13);
    //
    return 0;
}
```  
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter the numbers from 1 to 16 in any order:
16 3 2 13 5 10 11 8 9 6 7 12 4 15 14 1  
16   3   2  13
 5  10  11   8
 9   6   7  12
 4  15  14   1
Row sums: 34 34 34 34
Column sums: 34 34 34 34
Diagonal sums: 34 34
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>Write a program that allows the user to enter two fractions at the same time, separated by a plus sign:<br />
  Enter two fractions separated by a plus sign: <u>5/6+3/4</u>
  The sum is 38/24<br /></summary>

```c
#include <stdio.h>
int main()
{
    //variable declarations
    int num1, num2, den1, den2;
    //
    //getting fractions from the user
    printf("Enter two fractions separated by a plus sign: ");
    scanf("%d /%d +%d /%d", &num1, &den1, &num2, &den2);
    //
    //printing result to the screen
    printf("The sum is %d/%d\n", den1 * den2, num1 * den2 + num2 * den1);
    //
    return 0;   
}
```
<ul>    
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter two fractions separated by a plus sign: 1/2 + 1/2
The sum is 4/4  
        </code>
      </pre>  
    </details>
  </ul>  
</details> 
