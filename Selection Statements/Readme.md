<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#logical-expressions'>Logical Expressions</a>
  </li> 
  <li>
    <a href='#the-if-statement'>The if Statement</a>
  </li>
  <li>
    <a href='#boolean-values'>Boolean Values</a>
  </li>
  <li>
    <a href='#the-switch-statement'>The switch Statement</a>
  </li>
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>
</ol>
</details>

## Logical Expressions
### Relational Operators
<table>
    <thead>
        <tr>
            <td><strong>Operator</strong></td>
            <td><strong>Operator Name</strong></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><</td>
            <td>less than</td>
        </tr>
        <tr>
            <td>></td>
            <td>greater than</td>
        </tr>
        <tr>
            <td><=</td>
            <td>less than or equal to</td>
        </tr>
        <tr>
            <td>>=</td>
            <td>greater than or equal to</td>
        </tr>
    </tbody>        
</table>        

<ul>
  <li>
    <a>When relational operators are used in expressions, they produce either 0 (false) or 1 (true). For example, if the expression 10 < 11 were to be evaluated, it results in 1; otherwise, the expression 10 > 11 evaluates to 0</a>
  </li>
  <li>
    <a>Relational operators can be used to compare integers and floats, where operands on either side of the operator can be of different data types</a>
  </li>  
  <li>
    <a>Relational operators have left to right associativity</a>
    <ul>
      <li>
        <a>i < j < k evaluates to (i < j) < k</a>
      </li>
    </ul>    
  </li>  
</ul>  

### Equality Operators
<table>
    <thead>
        <tr>
            <td><strong>Operator</strong></td>
            <td><strong>Operator Name</strong></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>==</td>
            <td>equal to</td>
        </tr>
        <tr>
            <td>!=</td>
            <td>not equal to</td>
        </tr>
    </tbody>        
</table>       

<ul>
  <li>
    <a>The equality operators have left-to-right associativity like the relational operators and produce either a 0 or 1 when evaluated</a> 
  </li>
</ul>    

### Logical Operators
<table>
    <thead>
        <tr>
            <td><strong>Operator</strong></td>
            <td><strong>Operator Name</strong></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>!</td>
            <td>logical negation</td>
        </tr>
        <tr>
            <td>&&</td>
            <td>logical and</td>
        </tr>
        <tr>
            <td>||</td>
            <td>logical or</td>
        </tr>
    </tbody>        
</table> 

<ul>
  <li>
    <a>The logical operators have left-to-right associativity like the relational operators and produce either a 0 or 1 when evaluated</a>
  </li>
  <li>
    <a>!expr has the value 1 if expr has the value 0</a>
  </li>
  <li>
    <a>expr1 && and expr2 have the value 1; both expr1 and expr2 are nonzero values</a>
  </li>
  <li>
    <a>expr1 || expr2 has the value 1 if expr1 has a nonzero value and/or if expr2 has a nonzero value</a>    
  </li>  
</ul>    

### Precedence of all Operators
<table>
    <thead>
        <tr>
            <td><strong>Precedence</strong></td>
            <td><strong>Operator</strong></td>
            <td><strong>Operator Name</strong></td>
            <td><strong>Associativity</strong></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>x++, x--</td>
            <td>(postfix) Increment (++) and Decrement (--)</td>
            <td>Left-to-Right</td>
        </tr>
        <tr>
            <td>2</td>
            <td>!x, ++x, --x, (type)x, *x, &x, sizeof(x), +x, -x</td>
            <td>Logical Negation, (prefix) Increment and Decrement, Cast Operator, Deference Operator, Addressof Operator, sizeof, and Unary</td>
            <td>Right-to-Left</td>
        </tr>
        <tr>
            <td>3</td>
            <td>*, /, %</td>
            <td>Multiplication, Division, and Modulus</td>
            <td>Left-to-Right</td>
        </tr>
        <tr>
            <td>4</td>
            <td>+, -</td>
            <td>Addition and Subtraction</td>
            <td>Left-to-Right</td>
        </tr>
        <tr>
            <td>5</td>
            <td><, >, <=, >=</td>
            <td>Relational Operators</td>
            <td>Left-to-Right</td>
        </tr>
        <tr>
            <td>6</td>
            <td>==, !=</td>
            <td>Equality Operators</td>
            <td>Left-to-Right</td>
        </tr>
        <tr>
            <td>7</td>
            <td>&&</td>
            <td>Logical and</td>
            <td>Left-to-Right</td>
        </tr>
        <tr>
            <td>8</td>
            <td>||</td>
            <td>Logical or</td>
            <td>Left-to-Right</td>
        </tr>
        <tr>
            <td>9</td>
            <td>=, *=, /=, %=, +=, -=</td>
            <td>Assignment</td>
            <td>Right-to-Left</td>
        </tr>
        <tr>
            <td>10</td>
            <td>,</td>
            <td>Comma</td>
            <td>Left-to-Right</td>
        </tr>
    </tbody>        
</table> 

### Precedence Practice
<details>
  <summary>i = 3; j = 2; k = 1;<br />
    What is the output produced by: i < j == j < k</summary>

```c
(i < j) == (j < k)
(3 < 2) == (2 < 1)
0 == 0
```
<ul>    
  <details>
    <summary>Output</summary>
      <pre>
        <code>
1
        </code>
      </pre>  
    </details>
  </ul>  
</details>
<details>
  <summary>What does the following code print to the screen, if anything at all?

```c
int i = 3; j = 2; k = 1;
//
printf("%d\n", i % j + k > 2);
```</summary>

```c
(i % j) + k > 2
(3 % 2) + 1 > 2
1 + 1 > 2
2 > 2
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

## The if Statement
<ul>
  <li>
    <a>The if statement enables a program to evaluate an expression with two differing results that affect the functioning of the rest of the program. If the value of the expression is a nonzero integer, the expression is true and the code associated with the selection statement is executed; otherwise, if the value of the expression is zero, the expression is false and the code associated with the selection statement is not executed</a>
  </li>
  <li>
    <a>The if statement has the following form if the code associated with the if statement is only one line long:<br />
    if (expression)<br />
    &emsp;&emsp;statement;</a>
  </li>
  <li>
    <a>The if statement has the following form; if the code associated with the if statement is longer than one line long:</a>

```c
if (expression)
{
    statements;
}
```  
</li>
  <li>
    <a>The parentheses around the expression following if are required, as this is the syntax of selection statements, rather than part of the expression</a>
  </li> 
  <details>
    <summary>What does the following code print to the screen, if anything at all?

```c
int n = 12;
//
if (n >= 1 <= 10)
    printf("%d", n);
```
</summary>

```c
((n >= 1) <= 10)
((12 >= 1) <= 10)
(1 <= 10)
1 --> true
if (1)
    printf("%d", n);
//Therefore, n is printed to the screen
```
<ul>
<details>
  <summary>Output</summary>
    <pre>
      <code>
12
      </code>
    </pre>  
  </details>     
</ul>  
</details>   
<details>
  <summary>What does the following code print to the screen, if anything at all?

```c
int a = 3, b = 2, and c = 1;
//
if (a > b > c)
    printf("Wohoo!\n");
```  
</summary>

```c
(a > b) > c
(3 > 2) > 1
1 > 1
0 --> false
if (0)
    printf("Wohoo");
//Therefore, Wohoo is not printed to the screen
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
</ul>

### The else Clause
<ul>
  <li>
    <a>An if statement may also have an else clause, which has the following format:</a>

```c
if (expression)
    statement;
else
    statement;
```
</li>
  <li>
    <a>If the expression associated with the if statement evaluates to true, then the code associated with the if statement runs and the code associated with the else clause is skipped; however, if the if statement's expression evaluates to false, then the code associated with the else clause runs</a>
  </li>  
  <li>
    <a>There is no limit as to what code is associated with an if and else statement. In fact, it is not unusual for if statements to be nested within other selection statements. There is no limit on how much nesting can be done within selection statements</a>
    <ul>
      <li>
        <a>Here is an example of selection statements nested within each other:</a>

```c
if (x == 1)
{
    if (y == 2)
        max = 2;
    else
        max = 1;   
}
else
    max = 0;
```
  </li>  
</ul>    

### The else if Statement
<ul>
  <li>
    <a>The else if statement is useful for  coding instances where there are more than two outcomes. When using if and else statements, either the code associated with the if statement runs or the code associated with the else statement runs. Using the if else statement, there can be more than two scenarios that affect the execution of the program</a>
  </li>
  <li>
    <a>Unlike the if and else statements, where there can only be one if statement and only one else clause per selection chain, there is no limit on how many else if statements can be written within a conditional chain</a>
  <li>
    <a>Here is the syntax for a condition chain that contains else if statements:</a>

```c
if (expression)
    statement;
else if (expression1)
    statement;
else if (expression2)
    statement;
else if (expressionN)
    statement;
else
    statement;
```
  </li>  
</ul>    

### Conditional Expression
<ul>
  <li>
    <a>The <em>conditional operator</em> is a shortcut to an if followed by an else clause, which uses the two symbols ? and :</a>
  </li>
  <li>
    <a>Here is the syntax for the conditional operator: (expr1) ? (expr2) : (expr3). To explain what this conditional operator does, here is a more elaborate syntax for it: (condition) ? value return if condition is true : value returned if condition is false</a>
  </li>  
  <details>
    <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int x = 1, y = 2, z;
    //
    //printing the value of z
    printf("The value of z is: %d\n", z = (x > y) ? (x++) : (y++));
    //
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
The value of z is: 2
        </code>
      </pre>  
    </details>
  </ul>  
</details>
</ul>    

## Boolean Values
<ul>
  <li>
    <a>For many years, C did not have a type Boolean unlike C++; however, boolean values came to C in the library called <a><</a>stdbool.h<a>></a></a>
  </li>
  <li>
    <a>Boolean values have either a true or a false value. The integer representations of true and false are as follows: true has any nonzero value and false has the value 0</a>
  </li>
  <li>
    <a>A common use for boolean values is to create flags, variables that are often of type boolean that control the flow of a program. Flags will hold the value of true or false and are often used in if/else if expressions</a>
    <ul>
      <li>
        <a>When flags are used in selection expressions, they can look like this: if (flag == true)...</a>
      </li>
      <li>
        <a>A more simple expression that has the same meaning as the one above is: if (flag)... What this statement does is insert the value of flag into the expression. If the flag is false, if (false), then the code associated with the if statement does not run; however, if the flag is true, if (true), then the code associated with the if statement runs</a>
      </li>  
      <li>
        <a>If one would like to run a section of code if flag is false rather than true, then the negation operator can be placed in front of the flag in the if expression: if (!flag)</a>
      </li>  
    </ul>    
  </li>   
</ul> 

## The switch Statement
<ul>
  <li> 
    <a>Rather than having a large chain of else if statements embedded within the conditional chain, the switch statement may be handy. A switch statement is often easier to read than a large number of else if statements, and they too are faster than if statements when there are many cases</a>
  </li>
  <li>
    <a>Here is the syntax for a switch statement:</a>

```c
switch (expression)
{
    case constantExpression: statement;
    case constantExpression: statement;
    default: statement:   
}
```
  </li>  
  <li>
    <a>Here are the key elements that go into the creation of a switch block:</a>
    <ul>
      <li>
        <a><em>Controlling expression</em>: this is the expression that follows switch that is enclosed in parentheses. The expression must result in a value of type integer--either a char or an int. The switch statement does not work with strings, floats, and doubles</a>
      </li>
      <li>
        <a>Each case of the switch statement begins with a <em>case label</em> as follows: case constantExpression:</a>
      </li>
      <li>
        <a>The <em>constant expression</em> cannot contain variables or any call to the function. Here are some examples of constant expressions: 5 is a constant expression, even 5 + 10 is a constant expression, and n + 10 is not a constant expression--unless n is a macro that represents a constant. The constant expression in the case label must be an integer value (remember that a character is an integer as a character is represented by an ASCII character)</a>
      </li>  
      <li>
        <a>The <em>statements</em> come after each case label, and there can be as many cases as needed. Unlike with if statements, multiple statements associated with a switch's case do not need to be encapsulated by braces</a>
      </li>  
    </ul>
  </li>     
  <li>
    <a>Duplicate case labels are not allowed, and the cases do not have to follow any particular order. Even the default case does not have to be the last case within the switch's body</a>
  </li>   
  <li>
    <a>The switch statement does not have to have a default statement. If a switch statement is missing the default case and none of the constant expressions match the controlling expression, the computer just moves on to the line of code that is the next statement after the switch's body</a>
    <ul>
      <li>
        <a>The default statement does not need to have a break statement</a>
      </li>
    </ul>    
  </li>  
</ul>    

### The Role of the break Statement
<ul>
  <li>
    <a>Without a break statement, the control may fall through a case x and all cases including case x, and the cases, below it, will run. To prevent this from happening, a break statement can be used</a>
  </li>
  <li>
    <a>Here is a switch statement with no break statement:</a>
    <details>
      <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declaration and initialization
    int number = 3;
    //
    //switch statement to evaluate the number
    switch (number)
    {
        case 4: printf("Excellent\n");
        case 3: printf("Very good\n");
        case 2: printf("Good\n");
        case 1: printf("Satisfactory\n");
        case 0: printf("Failed\n");
        default: printf("Invalid input\n");    
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
Very good
Good
Satisfactory
Failed
Invalid input
        </code>
      </pre>  
    </details>
  </ul>  
</details>
  </li>    
  <li>
    <a>Here is the same switch statement with the addition of break statements in all the case statements:</a> 
    <details>
      <summary>Example Program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declaration and initialization
    int number = 3;
    //
    //switch statement to evaluate the number
    switch (number)
    {
        case 4: printf("Excellent\n"); break;
        case 3: printf("Very good\n"); break;
        case 2: printf("Good\n"); break;
        case 1: printf("Satisfactory\n"); break;
        case 0: printf("Failed\n"); break;
        default: printf("Invalid input\n");    
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
Very good
        </code>
      </pre>  
    </details>
  </ul>  
</details>
  </li>  
</ul>    

## Programming Projects
<details>
  <summary>Write a program that calculates how many digits a number contains:<br />
  Enter a number: <u>374</u><br />
  The number 374 has 3 digits<br />
  Assume that the number has no more than four digits</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    int number;
    // 
    //getting number from user
    printf("Enter a number: ");
    scanf("%d", &number);
    //conditional statement which checks if number has one digit    
    if (number > 0 && number < 10) 
        printf("The number %d has 1 digit\n", number);
    //  
    //conditional statement which checks if number has two digits    
    else if (number > 9 && number < 100)
        printf("The number %d has 2 digits\n", number);   
    //
    //conditional statement which checks if number has three digits
    else
        printf("The number %d has 3 digits\n", number);
    //  
    return 0;
}      
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number: <u>345</u>
The number 345 has 3 digits      
        </code>
      </pre>  
    </details>
  </ul>  
</details>

<details>
  <summary>Write a program that asks the user for a 24-hour time, then displays the time in 12-hour form:<br />
  Enter a 24-hour time: <u>21:11</u><br />
  Equivalent 12-hour time: 9:11 PM</summary>

```c
#include <stdio.h>
#include <stdbool.h>
//
int main()
{
    //variable declarations
    int hour, minutes;
    bool morning = false;
    //
    //getting time from user
    printf("Enter a 24-hour time: ");
    scanf("%d :%d", &hour, &minutes);
    //
    //converting 24-hour time to 12-hour time
    (hour > 12) ? (hour -= 12) : (morning = true);
    //
    //printing the equivalent 12-hour time
    (morning == true) ? (printf("Equivalent 12-hour time: %.2d:%.2d AM\n", hour, minutes)) : (printf("Equivalent 12-hour time: %.2d:%.2d PM\n", hour, minutes));
    //
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a 24-hour time: 2:09
Equivalent 12-hour time: 02:09 AM    
        </code>
      </pre>  
    </details>
  </ul>  
</details>

<details>

| Speed (knots) | Description |
| :------------ | :---------- |
| Less than 1 | Calm |
| 1-3 | Light air |
| 4-27 | Breeze |
| 28 - 47 | Gale |
| 48-63 | Storm |
| Above 63 | Hurricane |

  <summary>Write a program that asks the user to enter a wind speed (in knots), then displays the correct corresponding description of the wind speed</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declaration
    double speed;
    //
    //input from user for wind speed
    printf("Enter the wind speed (in knots): ");
    scanf("%lf", &speed);
    printf("Description of wind speed: ");<br />
    //
    //conditional statements which print a description of the wind speed
    if (speed < 1)
        printf("calm\n");
    else if (speed >= 1 && speed <= 3)
        printf("light air\n");
    else if (speed >= 4 && speed <= 27)
        printf("breeze\n");
    else if (speed >= 28 && speed <= 47)
        printf("gale\n");
    else if (speed >= 48 && speed <= 63)
        printf("storm\n");
    else
        printf("hurricane\n");
    //                
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter the wind speed (in knots): <u>45</u>
Description of wind speed: gale
        </code>
      </pre>  
    </details>
  </ul>  
</details>

<details>

| Income | Amount of tax |
| :----- | :------------ |
| Not over $750 | 1% of income |
| $750 - $2,250 | $7.50 plus 2% of amount over $750 |
| $2,250 - $3,750 | $37.50 plus 3% of amount over $2,250 |
| $3,750 - $5,250 | %82.50 plus 4% of amount over $3,750 |
| $5,250 - $7,000 | $142.50 plus 5% of amount over $5,250 |
| Over $7,000 | $230.00 plus 6% of amount over $7,000 |

  <summary>Write a program that asks the user to enter the amount of taxable income, then displays the tax due</summary>

```c  
#include <stdio.h>
//
int main()
{
    //variable declarations
    float income, taxDue
    //
    //getting taxable income from user
    printf("Enter your amount of taxable income: ");
    scanf("%f", &income);
    //
    //conditional statements calculating amount of tax due
    (income < 750) ? (taxDue = income * 0.01) : (income = income);
    (income >= 750 && income < 2250) ? (taxDue = 7.5 + (income - 750) * 0.02 ): (income = income);
    (income >= 2250 && income < 3750) ? (taxDue = 37.5 + (income - 2250) * 0.03) : (income = income);
    (income >= 3750 && income < 5250) ? (taxDue = 82.5 + (income - 3750) * 0.04) : (income = income);
    (income >= 5250 && income < 7000) ? (taxDue = 142.5 + (income - 5250) * 0.05) : (income = income);
    (income > 7000) ? (taxDue = 230 + (income - 7000) * 0.06) : (income = income);
    //
    //printing amount the user owes in taxes
    printf("Here is the amount of tax due: $%.2f\n", taxDue);
    //
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter your amount of taxable income: 5100
Here is the amount of tax due: $136.50  
        </code>
      </pre>  
    </details>
  </ul>  
</details>

<details>
  <summary>Write a program that finds the largest and smallest of four integers entered by the user:<br />
  Enter four integers: <u>21 43 10 35</u><br />
  Largest: 43<br />
  Smallest: 10</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    int int1, int2, int3, int4, max, min;
    //
    //getting four integers from user
    printf("Enter four integers: ");
    scanf("%d %d %d %d", &int1, &int2, &int3, &int4);
    //
    //finding maximum among the four integers
    if (int1 > int2 && int1 > int3 && int1 > int4)
        max = int1;
    else if (int2 > int1 && int2 > int3 && int2 > int4)
        max = int2;
    else if (int3 > int1 && int3 > int2 && int3 > int4)
        max = int3;
    else
        max = int4;
    //
    //finding minimum among the four integers
    if (int1 < int2 && int1 < int3 && int1 < int4)
        min = int1;
    else if (int2 < int1 && int2 < int3 && int2 < int4)
        min = int2;
    else if (int3 < int1 && int3 < int2 && int3 < int4)
        min = int3;
    else
        min = int4;
    //  
    //printing maximum and minimum integers
    printf("Largest: %d\nMinimum: %d\n", max, min);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter four integers: <u>999 56 4 8</u>
Largest: 999
Minimum: 4
        </code>
      </pre>  
    </details>
  </ul>  
</details>

<details>

| Departure time | Arrival time |
| :------------: | :----------: |
| 8:00 A.M. | 10:16 A.M. |
| 9:43 A.M. | 11:52 A.M. |
| 11:19 A.M. | 1:31 P.M. |
| 12:47 P.M. | 3:00 P.M. |
| 2:00 P.M. | 4:08 P.M. |
| 3:45 P.M. | 5:55 P.M. |
| 7:00 P.M. | 9:20 P.M. |
| 9:45 P.M. | 11:58 P.M. |

  <summary>Write a program that asks the user to enter a time (expressed in hours and minutes, using the 24-hour clock). The program then displays the departure and arrival times for the flight whose departure time is closest to that entered by the user:<br />
  Enter a 24-hour time: <u>13:15</u><br />
  Closest departure time is 12:47 p.m., arriving at 3:00 p.m.<br />
  The table beneath shows the daily flights from one city to another:</summary>

```c
#include <stdio.h>
int main()
{
    //variable declarations and initializations
    int hour, minutes, time, D1 = 8 * 60, D2 = 9 * 60 + 43, D3 = 11 * 60 + 19, D4 = 12 * 60 + 47, D5 = 14 * 60, D6 = 15 * 60 + 45, D7 = 19 * 60, D8 = 21 * 60 + 45;
    //
    //getting time input from the user
    printf("Enter a 24-hour time: ");
    scanf("%d :%d", &hour, &minutes);
    printf("Closest departure time is ");
    //
    //calculating number of minutes the user entered
    time = hour * 60 + minutes;
    //
    //conditional statements which check which departure is next
    if (time <= D1)
        printf("8:00 A.M., arriving at 10:16 A.M.\n");
    else if (time > D1 && time <= D2)  
        printf("9:43 A.M., arriving at 11:52 A.M.\n");
    else if (time > D2 && time <= D3)
        printf("11:19 A.M., arriving at 1:31 P.M.\n");      
    else if (time > D3 && time <= D4)
        printf("12:47 P.M., arriving at 3:00 P.M.\n");
    else if (time > D4 && time <= D5)
        printf("2:00 P.M., arriving at 4:08 P.M.\n");
    else if (time > D5 && time <= D6)
        printf("3:45 P.M., arriving at 5:558 P.M.\n");
    else if (time > D6 && time <= D7)
        printf("7:00 P.M., arriving at 9:20 P.M.\n");
    else
        printf("9:45 P.M., arriving at 11:58 P.M.\n");
    //  
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a 24-hour time: <u>11:20</u>
Closest departure time is 12:47 P.M., arriving at 3:00 P.M.
        </code>
      </pre>  
    </details>
  </ul>  
</details>

<details>
  <summary>Write a program that prompts the user to enter two dates and then indicates which date comes earlier on the calendar (assuming the date is in year 2000 or later):
  Enter first date (mm/dd/yy): <u>3/6/08</u>
  Enter second date (mm/dd/yy): <u>5/17/07</u>
  5/17/07 is earlier than 3/6/08</summary>

```c
#include <stdio.h>
int main()
{
    //variable declarations
    int month1, day1, year1, month2, day2, year2;
    //
    //getting both date inputs from the user
    printf("Enter first date (mm/dd/yy): ");
    scanf("%d /%d /%d", &month1, &day1, &year1);
    printf("Enter second date (mm/dd/yy): ");
    scanf("%d /%d /%d", &month2, &day2, &year2);
    //
    //conditional statements comparing dates to see which date comes first which then prints that information to the screen
    if (year1 > year2)
    {
        if (month1 > month2)
        {
            if (day1 > day2)
               printf("%d/%d/%d is earlier than %d/%d/%d\n", month1, day1, year1, month2, day2, year2);
              else
                  printf("%d/%d/%d is earlier than %d/%d/%d\n", month2, day2, year2, month1, day1, year1);
        }
        else
            printf("%d/%d/%d is earlier than %d/%d/%d\n", month2, day2, year2, month1, day1, year1);
    }
    else
        printf("%d/%d/%d is earlier than %d/%d/%d\n", month2, day2, year2, month1, day1, year1);
    //            
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter first date (mm/dd/yy): <u>7/7/8</u>
Enter second date (mm/dd/yy): <u>8/1/2</u>
8/1/2 is earlier than 7/7/8
        </code>
      </pre>  
    </details>
  </ul>  
</details>

<details>
  <summary>Using a switch statement, write a program that converts a numerical grade into a letter grade:<br />
  Enter numerical grade: <u>84</u><br />
  Letter grade: B<br />
  Use the following grading scale: A = 90 - 100, B = 80 - 89, C = 70 - 79, D = 60 - 69, F = 0-59. Print an error message if the grade is larger than 100 or less than 0</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declaration
    int grade;
    //
    //prompt user for numerical grade and store it in grade variable
    printf("Enter numerical grade: ");
    scanf("%d", &grade);
    //
    //conditional statements which check if grade is valid
    if (grade > 100 || grade < 0)
        printf("Invalid grade. Please enter a grade between 0 and 100.\n");\
    else
       //switch statement which determines the user's letter grade
       switch (grade / 10)
       {
            case 10:
            case 9:
                printf("Letter grade: A\n");
                break;
            case 8:
                printf("Letter grade: B\n");
                break;
            case 7:
                printf("Letter grade: C\n");
                break;
            case 6:
                printf("Letter grade: D\n");
                break;
            default:
                printf("Letter grade: F\n");
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
Enter numerical grade: <u>66</u>
Letter grade: D
        </code>
      </pre>  
    </details>
  </ul>  
</details>

<details>
  <summary>Write a program that asks the user for a two-digit number, then prints the English word for the number:<br />
  Enter a two-digit number: <u>45</u><br />
  You entered the number forty-five.</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initializations
    int number;
    //
    //prompt user for a two-digit number
    printf("Enter a two-digit number: ");
    scanf("%d", &number);
    printf("You entered the number ");
    //
    //switch statement which checks the first digit of the user's input
    switch (number / 10)
    {
        case 9:
            printf("ninety-");
            break;
        case 8:
            printf("eighty-");
            break;
        case 7:
            printf("seventy-");
            break;
        case 6:
            printf("sixty-");
            break;
        case 5:
            printf("fifty-");
            break;
        case 4:
            printf("forty-");
            break;
        case 3:
            printf("thirty-");
            break;
        case 2:
            printf("twenty-");
            break;
        case 1:
            //conditional statements which checks if the user's input matches any of the following conditions if the input divided by 10 is one
            (number == 11) ? printf("eleven.\n") : (1);
            (number == 12) ? printf("twelve.\n") : (1);
            (number == 13) ? printf("thirteen.\n") : (1);
            (number == 14) ? printf("fourteen.\n") : (1);
            (number == 15) ? printf("fifteen.\n") : (1);
            (number == 16) ? printf("sixteen.\n") : (1);
            (number == 17) ? printf("seventeen.\n") : (1);
            (number == 18) ? printf("eighteen.\n") : (1);
            (number == 19) ? printf("nineteen.\n") : (1);
    }
    //
    //conditional statement which checks if the user's input modulus 10 does not equal one
    if (number / 10 != 1)
        //switch statement which prints second digit's value in English
      switch (number % 10)
      {
          case 9:
              printf("nine.\n");
              break;
          case 8:
              printf("eight.\n");
              break;
          case 7:
              printf("seven.\n");
              break;
          case 6:
              printf("six.\n");
              break;
          case 5:
              printf("five.\n");
              break;
          case 4:
              printf("four.\n");
              break;
          case 3:
              printf("three.\n");
              break;
          case 2:
              printf("two.\n");
              break;
          case 1:
              printf("one.\n");
              break;
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
Enter a two-digit number: <u>56</u>
You entered the number fifty-six.
        </code>
      </pre>  
    </details>
  </ul>  
</details>
