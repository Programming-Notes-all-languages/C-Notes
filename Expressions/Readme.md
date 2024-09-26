<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#operator-precedence-and-associativity'>Operator Precedence and Associativity</a>
  </li> 
  <li>
    <a href='#assignment-operators'>Assignment Operators</a>
  </li>
  <li>
    <a href='#shorthand-assignment-operators'>Shorthand Assignment Operators</a>
  </li>
  <li>
    <a href='#increment-and-decrement-operators'>Increment and Decrement Operators</a>
  </li>
  <li>
    <a href='#expression-evaluation'>Expression Evaluation</a>
  </li>
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>
</ol>
</details>

## Operator Precedence and Associativity
### Operator Precedence
<table>
  <thead>
    <tr>
      <th><strong>Precedence</strong></th>
      <th><strong>Operator</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>(postfix) Increment (++) and Decrement (--)</td>
    </tr>
    <tr>
      <td>2</td>
      <td>(prefix) Increment (++) and Decrement (--) and Unary (+), (-)</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Multiplication (*), Division (/), and Modulus (%)</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Multiplication (*), Division (/), and Modulus (%)</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Addition (+) and Subtraction (-)</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Assignment (= *= /= %= += -=)</td>
    </tr>
  </tbody>
</table>    

<ul>
  <li>
    <a>Here is the associativity of the most common operators:</a>
    <ul>
      <li>
        <a>Left to right:<br />
        --> Addition and Subtraction<br />
        --> Multiplication, Division, and Modulus<br />
        --> Increment and Decrement (postfix)</a>
      </li>
      <li>
        <a>Right to left:<br />
        --> Assignment (= *= /= %= += -=)<br />
        --> Unary<br />
        --> Increment and Decrement (prefix)</a>
      </li>  
    </ul>    
  <li>
    <a>Here is a list of examples that show the precedence of the most common operators:</a>
    <ul>
      <li>
        <a>i + j * k is equivalent to i + (j * k)</a>
      </li>
      <li>
        <a>-i * -j is equivalent to (-i) * (-j)</a>
      </li>  
      <li>
        <a>+i + j / k is equivalent to (+i) + (j / k)</a>
      </li>  
      <li>
        <a>i - j - k is equivalent to (i - j) - k</a>
      </li>
      <li>
        <a>i * j / k is equivalent to (i * j) / k</a>
      </li> 
      <li>
        <a> - + i is equivalent to -(+i)</a>   
    </ul>
  </li>      
</ul>    

## Assignment Operators
<ul>
  <li>
    <a>The assignment operator, =, is a common operator that is used in the initialization of variables</a>
  </li>
  <li>
    <a>Several assignments can be chained together using the assignment operator such as in the following: i = j = k = 0;</a>
  </li> 
  <li>
    <a>The assignment operator is right-associative, meaning that i = j = k = 0; is equivalent to i = (j = (k = 0)); Here, k is assigned the integer value 0; j is assigned to k containing the integer value of 0; and lastly; i is assigned to j containing the integer value of 0</a>
  </li>   
  <li>
    <a>When using the assignment operator, the operand on the left side of the operator must be an object stored in the computer's memory rather than a constant. It is illegal to put any kind of expression on the left side of the assignment operator other than an object stored in memory itself</a>
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

## Increment and Decrement Operators
<ul>  
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

## Expression Evaluation
<details>
  <summary>Evaluate the expression using parentheses for a:<br />
  a = b += (c++) - d + --e / -f</summary>
  <ul>
    <details>
    <summary>Output</summary>
      <pre>
        <code>
a = b += (c++) - d + --e / -f
a = b += (c++) - d + (--e) / -f
a = b += (c++) - d + (--e) / (-f)
a = b += (c++) - d + ((--e) / (-f))
a = b += ((c++) - d) + ((--e) / (-f))
a = b += (((c++) - d) + ((--e) / (-f)))
a = (b += (((c++) - d) + ((--e) / (-f))))
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Evaluate the expression for c:

```c
int a = 5, b;
int c = (b = a + 2) - (a = 1);
```
</summary>
  <ul>
    <details>
    <summary>Output</summary>
      <pre>
        <code>
c = (b = 5 + 2) - 1;
c = (b = 7) - 1;
c = 7 - 1;
c = 6;
        </code>
      </pre>  
    </details>    
  </ul>  
</details> 

<details>
  <summary>Evaluate the expression for x:

```c
int x = 7;
int y = 4;
x = ++x + y++ + ++y;
```
</summary>
  <ul>
    <details>
    <summary>Output</summary>
      <pre>
        <code>
x = 8 + 4 + 6;
x = 18;
        </code>
      </pre>
    </details>      
  </ul>  
</details> 

## Programming Projects
<details>
  <summary>Write a program that asks the user to enter a two-digit number, then prints the number with its digits reversed. A session with the program should have the following appearance:<br />
  Enter a two-digit number: <u>28</u><br />
  The reversal is: 82</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    char first, second;
    //
    //getting digits from the user
    printf("Enter a two-digit number: ");
    scanf("%c%c", &first, &second);
    //
    //printing the reversal of the user's digits
    printf("The reversal: %c%c", second, first);
    //
    return 0;
}
```   
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a two-digit number: <u>91</u>
The reversal: 19 
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter a three-digit number, then prints the number with its digits reversed. A session with the program should have the following appearance:<br />
  Enter a two-digit number: <u>281</u><br />
  The reversal is: 182</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    int numOrig, first, second, third;
    //
    //getting digits from the user
    printf("Enter a three-digit number: ");
    scanf("%d", &numOrig);
    //
    //flipping user's digits
    third = numOrig % 100 % 10;
    second = (numOrig - third) / 10 % 10;
    first = (numOrig - third - second * 10) / 100;
    //
    //printing the reversal of the user's digits
    printf("The reversal: %d%d%d", third, second, first);
    //
    return 0;    
}
```  
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a three-digit number: <u>431</u>
The reversal: 134
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that asks the user to enter a three-digit number, then prints the number with its digits reversed without using arithmetic:<br />
  Enter a three-digit number: <u>281</u><br />
  The reversal is: 182</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    char first, second, third;
    //
    //getting digits from the user
    printf("Enter a three-digit number: ");
    scanf("%c%c%c", &first, &second, &third);
    //
    //printing the reversal of the user's digits
    printf("The reversal: %c%c%c", third, second, first);
    //
    return 0;    
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a three-digit number: <u>456</u>
The reversal: 654
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that reads an integer entered by the user and displays it in octal:<br />
  Enter a number between 0 and 32767: <u>1953</u><br />
  In octal, your number is: 03641</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations
    int baseNum, oct0, oct1, oct2, oct3, oct4;
    //
    //getting user's number input
    printf("Enter a number between 0 and 32767: ");
    scanf("%d", &baseNum);
    //            
    //converting user's input to octal
    oct4 = baseNum % 8;
    baseNum /= 8;
    oct3 = baseNum % 8;
    baseNum /= 8;
    oct2 = baseNum % 8;
    baseNum /= 8;
    oct1 = baseNum % 8;
    baseNum /= 8;
    oct0 = baseNum;
    //
    //printing user's number in octal representation
    printf("In octal, your number is: %d%d%d%d%d\n", oct0, oct1, oct2, oct3, oct4);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number between 0 and 32767: <u>1953</u>
In octal, your number is: 03641
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
