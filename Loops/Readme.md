<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#the-while-loop'>The while Loop</a>
  </li> 
  <li>
    <a href='#the-do-statement'>The do Statement</a>
  </li> 
  <li>
    <a href='#the-for-statement'>The for Statement</a>
  </li> 
  <li>
    <a href='#exiting-from-a-loop'>Exiting from a Loop</a>
  </li> 
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>
</ol>
</details>

## The while Loop
<ul>
  <li>
    <a>Here is the syntax for a while loop: while (expression) statement;</a>
    <ul>
      <li>
        <a>The expression inside the parentheses is the controlling expression</a>
      </li>
      <li>
        <a>The statement after the parentheses is the body of the while loop. Note that the parentheses are mandatory for the encapsulation of the controlling expression</a>
      </li>
    </ul>       
  </li>
  <li>
    <a>When a while loop is executed, the first step is evaluating the loop's controlling expression. If its controlling expression evaluates to a nonzero number, the loop's body is executed; otherwise, the loop's body is skipped</a>
  </li>
  <li>
    <a>Similar to conditional statements, the braces that enclose the body of the while loop are optional--only if the body of the loop is only one line long. If the loop's body is more than one line long, its body needs to be encapsulated in braces</a>
  </li>
  <li>
    <a>Since the controlling expression is evaluated first in the execution of the while loop, there is a chance that the while loop may never run at all. This is because if the controlling expression of the while loop evaluates to false its first time, the loop is skipped entirely</a> 
  </li>
  <li>
    <a>Another scenario is that if there is no functionality to make the controlling expression evaluate to false at some point, then the loop iterates repeatedly</a>
  </li>   
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int input = -1, sum = 0;
    //
    printf("This program sums all the user's integer inputs.\n");
    printf("Enter integers (0 to terminate): ");
    //
    //loop to continuously read and add user inputs until 0 is entered
    while (input != 0)
    {
        scanf("%d", &input);
        sum += input;
    }
    //
    printf("The sum of all entered integers is: %d\n", sum);
    //
    return 0;
}
``` 
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter integers (0 to terminate): <u>5 6 7 8 9
0</u>
The sum of all entered integers is: 35
          </code>
        </pre>  
      </details>
    </ul>  
  </details>     
  <li>
    <a>Putting a semicolon after the parentheses following an if, while, or for statement creates a null statement</a>
  </li>  
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declaration and initialization
    int i = 3;
    //
    //while loop which iterates while i is greater than 0
    while (i > 0);
    {
        printf("%d ", i);
        --i;
        }
        return 0;
}
```
<ul> 
  <details>
  <summary>Output</summary>
    <pre>
      <code>
Infinite loop
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
    //variable declaration and initialization
    int i = 3;
    //
    //while loop which iterates while i is greater than 0
    while (--i > 0);
        printf("%d ", i);
    //    
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
0
        </code>
      </pre>  
    </details>
  </ul>  
  </details> 
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>
int main()
{
    //variable declaration and initialization
    int x = 0;
    //
    //while loop which iterates until x is no longer less than 3
    while (x++ < 3);
        printf("x = %d\n", x);
    //    
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
x = 4
        </code>
      </pre>  
    </details>
  </ul>  
  </details>        
</ul>    

## The do Statement
<ul>
  <li>
    <a>The do statement is very closely related to the while statement. The difference with the do statement is that the loop body is  executed once before its controlling expression is evaluated. After the body's first iteration, the controlling expression will be evaluated once before every future iteration of the loop</a>
  </li>
  <li>
    <a>Here is the syntax of a do-while loop: do statement while (expression);</a>
  </li>  
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int input = -1, sum = 0;
    //
    printf("This program sums all the user's integer inputs.\n");
    printf("Enter integers (0 to terminate): ");
    //
    //loop to continuously read and add user inputs until 0 is entered
    do
    {
        scanf("%d", &input);
        sum += input;
    } while (input != 0);
    //
    printf("The sum of all entered integers is: %d\n", sum);
    //
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter integers (0 to terminate): <u>5 6 7 8 9
0</u>
The sum of all entered integers is: 35
          </code>
        </pre>  
      </details>
    </ul>  
  </details>  
</ul>    

## The for Statement
<ul>
  <li>
    <a>The for statement has the following syntax: for (expr1; expr2; expr3) statement</a>
    <ul>
      <li>
        <a>expr1 is the initialization step of the for loop which is performed only once during the execution of the loop. expr1 runs before the loop begins its execution</a>
      </li>  
      <li>
        <a>expr2 is the controlling expression that determines when the loop should stop iterating. This happens when expr2 is equal to zero</a>
      </li>
      <li>
        <a>expr3 is the operation that happens at the end of the loop's iteration</a>
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
    int n;
    //
    //for loop which prints value of n when n is not equal to 0
    for (n = 9; n != 0; n--)
        printf("%d ", n--);
    //    
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Infinite loop
        </code>
      </pre>  
    </details>
  </ul>  
  </details> 
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>
int main()
{
    //variable declaration and initialization
    int si, j;
    //
    //for loop which iterates from 0 to 2, inclusive
    for (i = 0; i < 3; i++) 
    {
        for (j = 0; j < 3; j++);
        printf("i = %d, j = %d\n", i, j);
    }
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
i = 0, j = 3
i = 1, j = 3
i = 2, j = 3
        </code>
      </pre>  
    </details>
  </ul>  
  </details>         
</ul>

### Omitting Expressions in a for Statement
<ul>  
  <li>
    <a>The for statements is very flexible as some for loops may not need all three expressions that are enclosed within the parentheses. If the first expression is omitted, no initialization is performed before the execution of the loop. If the third expression is omitted, then the loop's body is responsible for ensuring that the second expression evaluates to false at some point to exit the loop</a>
  </li>  
  <li>
    <a>The second expression in the for loop can be omitted. Doing so defaults the second expression to evaluate to true. A for loop which also omits the first expression and the third expression creates an infinite loop (for;;)</a>
  </li>  
</ul>    

### The comma Operator
<ul>
  <li>
    <a>Sometimes, there may need to be multiple initializations in the first expression of the for statement. This can be accomplished with the comma operator</a>
  </li>
  <li>
    <a>Here is the syntax for the comma operator: expr1, expr2</a>
  </li>  
</ul>    

## Exiting from a Loop
### The break Statement
<ul>
  <li> 
    <a>Just like with the switch statement, the break statement can be used with while, do, and for loops</a>
  </li>
  <li>
    <a>The break statement exits one level of nesting in a switch statement, for loop, while loop, and a do-while loop. The control is then brought outside of the switch statement or loop</a>
  </li>  
  <li>
    <a>The break statement ends control within a single level of nesting in a switch statement and any loop statement. Consider the case below where there is a switch statement that is enclosed within a while loop:</a>

```c
while (...)
{
    switch (...)
    {
        ...
        break;
        ...
    }
}
```
<a>The break statement will exit one level of nesting and will bring control out of the switch statement, to the while loop--not outside of the while loop as break only can leave one level of nesting</a>
  </li>  
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declaration and initialization
    int sum = 0;
    //
    //for loop which iterates from 0 to 2, inclusive
    for (int i = 0; i < 3; i++)
    {
        //conditional statement which checks if i modulus 2 is 1
        if (i % 2 == 1)
            break;
        sum += i;
    }
    //
    printf("sum = %d\n", sum);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
sum = 0
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
</ul>  

### The continue Statement
<ul>
  <li>
    <a>The continue statement does not make control leave one layer of nesting; instead, the control is brought just before the end of the loop's body</a>
  </li>
  <li>
    <a>There are a few differences between break and continue:</a>
    <ul>
      <li>
        <a>break leaves the loop it is embedded in and continue keeps the control within the loop</a>
      </li>
      <li>
        <a>break can be used in loops in addition to switch statements. continue can only be used in loops and not in switch statements</a>
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
    int sum = 0;
    //
    //for loop which iterates from 0 to 2, inclusive
    for (int i = 0; i < 3; i++)
    {
        //conditional statement which checks if i modulus 2 is 1
        if (i % 2 == 1)
            continue;
        sum += i;
    }
    //
    printf("sum = %d\n", sum);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
sum = 2
        </code>
      </pre>  
    </details>
  </ul>  
</details>        
</ul>   

### The goto Statement
<ul>
  <li>
    <a>The goto statement can jump to any statement within a program's function</a>
  </li>
  <li>
    <a>Here is the syntax for the goto statement: goto identifier; At some point in the program, there will be the location in which the control goes to as a result of the goto statement. The syntax for this destination location is following statement: identifier: statement</a>
  </li>  
  <li>
    <a>goto transfers control to that location of the identifier which must be in the same function as the goto statement itself</a>
  </li>  
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int x = 1, y = 2, z = 3;
    //
    //control statements
    if (x == 1)
        if (y == 2)
            if (z == 3)
                goto Garrett;
    
    Garrett:
        printf("Now the control is here!\n");
    //    
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Now the control is here!
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
</ul>

## Programming Projects
<details>
  <summary>Write a program that finds the largest in a series of numbers entered by the user. The program must prompt the user to enter numbers one by one. When the user enters 0 or a negative number, the program must display the largest nonnegative number entered:<br />
  Enter a number: <u>60</u><br />
  Enter a number: <u>100.5</u><br />
  Enter a number: <u>56</u><br />
  The largest number entered was 100.5</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    float input, max = 0;
    //
    //do-while loop which iterates until input is no longer valid
    do
    {
        //getting input from user
        printf("Enter a number: ");
        scanf("%f", &input);
        //
        //conditional statement which checks if user input a new max number
        if (input > max)
            max = input;
    } while (input > 0);
    //
    printf("The largest number entered was %.2f\n", max);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number: <u>56.7</u>
Enter a number: <u>99999</u>
Enter a number: <u>7</u>
Enter a number: <u>-9</u>
The largest number entered was 99999.00
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter two integers, then calculates and displays their greatest common divisor (GCD):<br />
  Enter two integers: <u>12 28</u><br />
  Greatest common divisor: 4</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int int1, int2, GCD = 0;
    //
    //taking input from the user for the two integers
    printf("Enter two integers: ");
    scanf("%d %d", &int1, &int2);
    //
    //for loop which iterates until all factors of the smallest of the two integers have been assessed
    for (int i = 1; i <= int1 && i <= int2; i++)
        //conditional statement which checks if i is a factor of both int1  and int2
        if (int1 % i == 0 && int2 % i == 0)
            GCD = i;
    //
    printf("Greatest common divisor: %d\n", GCD);
    //
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter two integers: 234 584
Greatest common divisor: 2
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter a fraction, then reduces the fraction to lowest terms:<br />
  Enter a fraction: <u>6/12</u><br />
  In lowest terms: 1/2</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int numerator, denominator, GCD;
    printf("Enter a fraction: ");
    scanf("%d /%d", &numerator, &denominator);
    //
    //for loop which iterates until all factors of the smallest of the two integers have been assessed
    for (int i = 1; i <= numerator && i <= numerator; i++)
        //conditional statement which checks if i is a factor of both int1  and int2
        if (numerator % i == 0 && denominator % i == 0)
            GCD = i;
    //
    printf("In lowest terms: %d/%d", numerator / GCD, denominator / GCD);
    //
    return 0;  
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a fraction: <u>4/94</u>
In lowest terms: 2/47
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that displays the reversal of any integer, no matter how large</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int number, originalNum, reversal = 0, numDigits = 0;
    //
    //getting number from user that will be reversed
    printf("Enter a number: ");
    scanf("%d", &number);
    originalNum = number;
    //
    //for loop which counts the number of digits the user's input is
    for (int temp = number; temp > 1; numDigits++)
        temp /= 10;
    //
    //for loop which iterates until each digit of the user's input has been assessed
    for (int temp = 1; numDigits > 0; numDigits--, temp = 1)
    {
        //for loop which iterates to find the position of the next digit
        for (int i = 1; i <= numDigits; i++)
            //conditional statement which checks if i is less the numDigits
            if (i < numDigits)
                temp *= 10;
        //
        reversal += number % 10 * temp;
        number /= 10;
    }
    //
    printf("The reversal of %d is: %d\n", originalNum, reversal);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number: <u>230857</u>
The reversal of 230857 is: 758032
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that prompts the user to enter a number n, then prints all even squares between 1 and n. For example, if the user enters 100, the program should print the following:<br />
  4<br />
  16<br />
  36<br />
  64<br />
  100</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int input;
    //
    //getting input from user
    printf("Enter an integer: ");
    scanf("%d", &input);
    //
    //printing perfect even squares from the given input
    for (int i = 2; input >= i * i; i += 2)
        printf("%d\n", i * i);
    //
    return 0;    
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter an integer: <u>200</u>
4
16
36
64
100
144
196
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that prints a one-month calendar. The user specifies the number od days in the month and the day of the week on which the month begins:<br />
  Enter the number of days in the month: <u>31</u><br />
  Enter starting day of the week (1=Sun, 7=Sat): <u>3</u><br />
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1&nbsp;&nbsp;&nbsp;2&nbsp;&nbsp;&nbsp;3&nbsp;&nbsp;&nbsp;4&nbsp;&nbsp;&nbsp;5<br>
  &nbsp;6&nbsp;&nbsp;&nbsp;7&nbsp;&nbsp;&nbsp;8&nbsp;&nbsp;&nbsp;9&nbsp;10&nbsp;&nbsp;11&nbsp;12<br />
  13&nbsp;14&nbsp;15&nbsp;16&nbsp;17&nbsp;18&nbsp;19<br />
  20&nbsp;21&nbsp;22&nbsp;23&nbsp;24&nbsp;25&nbsp;26<br />
  27&nbsp;28&nbsp;29&nbsp;30&nbsp;31</summary>

```c
#include <stdio.h>
int main()
{
    //variable declarations and initializations
    int days, startDay;
    //getting number of days and starting day from user
    printf("Enter number of days in month: ");
    scanf("%d", &days);
    printf("Enter starting day of the week (1=Sun, 7=Sat): ");
    scanf("%d", &startDay);
    //
    //for loop which iterates until entire calender is printed
    for (int i = 1, j = 1; i <= days + startDay; i++)
    {
        //conditional statement responsible for printing white-spaces and numbers
        if (i < startDay || j > days)
            printf("   ");
        else
            printf("%3d", j++);
        //    
        //conditional statement responsible for printing the newline character    
        if (i % 7 == 0)
            printf("\n");
    }
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter number of days in month: 45
Enter starting day of the week (1=Sun, 7=Sat): 6
               1  2
3  4  5  6  7  8  9
10 11 12 13 14 15 16
17 18 19 20 21 22 23
24 25 26 27 28 29 30
31 32 33 34 35 36 37
45
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that determines which of two dates the user comes earlier on the calendar. Generalize the program so that the user may enter any number of dates. Assume all dates are between the years 2000 and 2099. The user will enter 0/0/0 to indicate that no more dates will be entered:<br />
  Enter a date (mm/dd/yy): <u>3/6/08</u><br />
  Enter a date (mm/dd/yy): <u>5/17/07</u><br />
  Enter a date (mm/dd/yy): <u>6/3/07</u><br />
  Enter a date (mm/dd/yy): <u>0/0/0</u><br />
  5/17/07 is the earliest date</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int inputMonth, inputDay, inputYear, minMonth = 100, minDay = 100, minYear = 100;
    //
    //do-while loop which iterates until the user decides to quit the program
    do
    {
        //getting date input from the user
        printf("Enter a date (mm/dd/yy): ");
        scanf("%d /%d /%d", &inputMonth, &inputDay, &inputYear);
        //
        //conditional statements which check if user's input is the earliest date they have entered
        if (inputMonth != 0 && inputDay != 0 && inputYear != 0)
        {
            if (inputYear < minYear)
            {
                minYear = inputYear;
                minMonth = inputMonth;
                minDay = inputDay;
            }
            else if (inputYear == minYear)
            {
                if (inputMonth < minMonth)
                {
                    minMonth = inputMonth;
                    minDay = inputDay;
                }
                else if (inputMonth == minMonth)
                    if (inputDay < minDay)
                        minDay = inputDay;
            }
        }
    } while (inputMonth != 0 && inputDay != 0 && inputYear != 0);
    //
    printf("%d/%d/%d is the earliest date\n", inputMonth, inputDay, inputYear);
    //
    return 0;
}
```
<ul>    
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a date (mm/dd/yy): <u>03/11/03</u>
Enter a date (mm/dd/yy): <u>2/1/4</u>
Enter a date (mm/dd/yy): <u>0/0/0</u>
3/11/03 is the earliest date
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>The value of the mathematical constant e can be expressed as an infinite series:<br />
  e = 1 + 1/1! + 1/2! + 1/3! + ...<br />
  Write a program that approximates e by computing the value of 1 + 1/1! + 1/2! + 1/3! + ... + 1/n!<br />
  where n is an integer entered by the user</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int input;
    float valE = 1;
    //
    //getting input from the user
    printf("Enter a value to be used to approximate the value of e: ");
    scanf("%d", &input);
    //
    //for loops which approximate the value of e
    for (int i = 1, temp = 1; i <= input; valE += 1.0 / temp, temp = 1, i++)
        for (int j = i; j > 0; temp *= j--);
    //
    printf("Your approximation of the value e is: %.5f\n", valE);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a value to be used to approximate the value of e: <u>18</u>
Your approximation of the value e is: 2.71828
        </code>
      </pre>  
    </details>
  </ul>  
</details> 

<details>
  <summary>Write a program that displays the first 50 palindromic numbers. A palindromic is a number that it's reverse is the same as the number. For example, 11, 181, and 787 are palindromic. However, 13 is not palindromic</summary>

```c
#include <stdio.h>
//
#define MAX 50
//
int main()
{
    //variable declaration and initialization
    int count = 0;
    //
    //for loop which iterates until 50 palindromic numbers are printed
    for (int i = 11, temp = 0, numDigits = 0; count < MAX; i++, temp = numDigits = 0)
    {
        //for loop which counts the number of digits i contains
        for (int j = i; j > 0; j /= 10, numDigits++);
            //for loop which flips i
            for (int k = 0, num = i; k < numDigits; k++, temp += num % 10, num /= 10, temp *= 10);
                //conditional statement which checks if reversal of i and i are the same number
                if (temp / 10 == i)
                {
                    if (count % 10 != 0 || count == 0)
                        printf("%d ", i);
                    else
                        printf("\n%d ", i);
                    count++;
                }
    }
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
11 22 33 44 55 66 77 88 99 101 
111 121 131 141 151 161 171 181 191 202 
212 222 232 242 252 262 272 282 292 303 
313 323 333 343 353 363 373 383 393 404 
414 424 434 444 454 464 474 484 494 505
        </code>
      </pre>  
    </details>
  </ul>  
</details> 
