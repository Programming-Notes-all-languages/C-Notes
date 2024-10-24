<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#one-dimensional-arrays'>One-Dimensional Arrays</a> 
  </li> 
  <li>
    <a href='#multidimensional-arrays'>Multidimensional Arrays</a>
  </li> 
  <li>
    <a href='#variable-length-arrays'>Variable-Length Arrays</a>
  </li> 
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>
</ol>
</details>

## One-Dimensional Arrays
<ul>
  <li>
    <a>An <em>array</em> is a type of data structure that contains a set number of values of the same data type</a>
  </li>
  <li>
    <a>Each value within an array is known as an <em>element</em> which has a numerical position within the array</a>
  </li>
  <li>
    <a>It is good practice to use macros for the length of the array</a>
  </li>  
  <li>
    <a>To declare an array, the array's type must be specified first, followed by the name of the array, and lastly the number of elements the array has, which is enclosed in brackets following the name of the array</a>
    <ul>
      <li>
        <a>Here is the syntax for an array declaration: dataType arrayName[integerValue];</a>
      </li>
    </ul>    
  </li>     
</ul>    

### Array Subscripting
<ul>
  <li>
    <a>To access an element of an array, the array's name is written followed by the array's element's index which is enclosed in brackets</a>
  </li>
  <li>
    <a>Array elements start at index 0, up to one less than the length of the array. For example, an array with 5 elements starts at index 0 and ends at index 4, a[0], a[1], ... a[4]</a>
  </li>
  <li>
    <a>Expressions with the form arrayName[index] can be treated as any ordinary variable</a>
  </li> 
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

int main()
{
    //variable declaration and initialization
    int array[10];
    
    //inputting numbers into the array
    printf("Enter 10 numbers: ");
    for (int i = 0; i < 10; i++)
        scanf("%d", &array[i]);
    
    //printing the array in reverse order
    printf("In reverse order: ");
    for (int i = 9; i >= 0; i--)
        printf("%d ", array[i]);
    
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter 10 numbers: <u>1 2 3 4 5 6 7 8 9 10</u>
In reverse order: 10 9 8 7 6 5 4 3 2 1
          </code>
        </pre>  
      </details>
    </ul>  
  </details>   
</ul> 

### Array Initialization
<ul>
  <li>
    <a>Just like other variables, arrays can be initialized at the time of declaration</a>
  </li>
  <li>
    <a>The most common type of <em>array initializer</em> is a list of constants enclosed within braces, where each element is separated by commas</a>
    <ul>
      <li>
        <a>Here is an example of initializing all elements of an array: int array[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};</a>
      </li>
    </ul>    
  </li> 
  <li>
    <a>If the initializer does not have a constant for each element of the array, the remainder of elements without a constant to initialize them would be initialized to 0</a>
    <ul>
      <li>
        <a>Here is an example of initializing all elements of an array without an initializer for all elements: int array[10] = {1, 2, 3, 4, 5, 6};</a>
      </li>
      <li>
        <a>array[6], array[7], array[8], and array[9] are now initialized with 0</a>
      </li>  
    </ul>    
  </li>
  <li>
    <a>If one would like to initialize all elements of an array to zero, this can be done: int array[10] = {0}; Here, all elements of the array are initialized to zero</a>
  </li>  
  <li>
    <a>If the length of an array is omitted in the array's declaration, yet there is an initializer with x elements, then the array's size is x elements and each element is initialized with its designated initializer</a>
  </li>  
</ul>    

### Designated Initializers
<ul>
  <li>
    <a>If only certain elements of an array should be initialized, then <em>designated initializers</em> can be used. Here is an example of initializing certain elements of an array: int array[15] = {[2] = 29, [9] = 6, [14] = 48};</a>
  </li>
  <li>
    <a>If the size of the array is not present when using designated initializers, then the last index of the array is one less than the size of the array. In this example, int b[] = {[5] = 10, [15] = 29};, the size of the array is 16</a>
  </li>  
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

int main()
{
    //variable declaration and initialization
    char ch;
    int seen[10] = {0}, maxSeen = 0;
    
    printf("Enter a number: ");
    //do-while loop which iterates until the user enters the newline character
    do
    {
        ch = getchar();
        
        //conditional statement which checks if user entered a number
        if (ch >= '0' && ch <= '9')
            //for loop which iterates over all indices of the seen array
            for (int i = 0; i < 10; i++)
                //conditional statement which checks if user entered a number that is the same as i
                if (ch - 48 == i)
                    seen[i]++;
    } while (ch != '\n');<br />
    
    //for loop which iterates over all indices of the seen array
    for (int i = 0; i < 10; i++)
        //conditional statement which is used to find the maximum number of common digits the user input
        if (seen[i] > maxSeen)
            maxSeen = seen[i];
     
    //conditional statement which checks if the user input and repeated digits
    if (maxSeen > 1)
        printf("Repeated digit\n");
    //conditional statement which runs if the user input all unique digits    
    else
        printf("No repeated digit\n");
          
    return 0;
}
```
<ul>  
  <details>
      <summary>Output</summary>
        <pre>
          <code>
Enter a number: <u>123494</u>
Repeated digit
          </code>
        </pre>  
      </details>
    </ul>  
  </details> 
</ul>    

## Multidimensional Arrays
<ul>
  <li>
    <a>An array can have any number of dimensions</a>
  </li>
  <li>
    <a>Here is the syntax for declaring a multidimensional array: dataType arrayName[x][y];</a>
    <ul>
      <li>
        <a>If this declaration were to be made in a program: int array[5][9];, then this array has five elements, where each of the five elements has nine sub-elements</a>
      </li>
    </ul>
  </li> 
  <li>
    <a>Here is an example for initializing a multidimensional array: dataType arrayName[3][2] = {{0, 1}, {1, 0}, {1, 1}};</a>
  </li>
  <li>
    <a>Just like with a single-dimensional array, the same practices apply for declaring and initializing the elements of the multidimensional array</a>
  </li>        
</ul>    

### Constant Arrays
<ul>
  <li>
    <a>One or multidimensional arrays can be made constant which means that its elements' contents cannot be modified throughout the duration of the program</a>
  </li>
  <li>
    <a>Here is the syntax for declaring and initializing the elements of a const array: const dataType arrayName[size] = {value0, value1, ..., valueN};</a>
  </li>  
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

int main()
{
    //variable declaration and initialization
    const int array[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
    
    //for loop which prints the array's elements
    printf("Here are the array's elements: ");
    for (int i = 0; i < 10; i++)
        printf("%d ", i);
    
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number: <u>123494</u>
Repeated digit
        </code>
      </pre>  
    </details>
  </ul>  
</details> 
</ul>    

## Variable-Length Arrays
<ul>
  <li>
    <a>In newer versions of C, a variable, rather than a constant of type integer, can be used when declaring the size of an array</a>
  </li>
  <li>
    <a>When using a variable to declare the size of the array, the array can only be declared on that line--the array can be initialized later on lower lines. The const modifier does not work with variable-length arrays either</a>
  </li> 
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

int main()
{
    //variable declaration and initialization
    char ch;
    int number10;
    
    //prompt the user to enter a number
    printf("Enter the size of the array: ");
    scanf("%d", &number10);
    int array[number10];
    
    //for loop which iterates from 0 to 9
    for (int i = 0; i < number10; i++)
        array[i] = i;

    //for loop which prints the array reversed
    printf("Here is the array reversed: ");
    for (int i = number10 - 1; i >= 0; i--)
        printf("%d ", array[i]);
    
    return 0;
}
```   
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number: <u>123494</u>
Repeated digit
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
</ul>   

## Programming Projects
<details>
  <summary>Write a program that has the user enter an integer and then prints out which digits in the user's number are repeated</summary>

```c
#include <stdio.h>

int main()
{
  //variable declaration and initialization
  char ch;
  int seen[10] = {0};
  
  printf("Enter a number: ");
  //
  //do-while loop which iterates until the user enters a newline character
  do
  {
      ch = getchar();
      
      //for loop which iterates from 0 to 9
      for (int i = 0; i < 10; i++)
          //conditional statement which checks if the character is a digit
          if (ch - 48 == i)
              seen[i]++;
  } while (ch != '\n');
  
  //printing repeated digits to the screen
  printf("Repeated digit(s): ");
  for (int i = 0; i < 10; i++)
      if (seen[i] > 1)
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
Enter a number: <u>389457398745</u>
Repeated digit(s): 3 4 5 7 8 9  
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that has the user enter an integer. Then, have the program print the number of occurrences of each digit in the number like in the following example:<br />
  Enter a number: <u>41271092</u><br />
  Digit: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;0&nbsp; 1&nbsp; 2&nbsp; 3&nbsp; 4&nbsp; 5&nbsp; 6&nbsp; 7&nbsp; 8&nbsp; 9<br />
  Occurrences: 1&nbsp;&nbsp;2&nbsp;&nbsp;2&nbsp;&nbsp;0&nbsp;&nbsp;1&nbsp;&nbsp;0&nbsp;&nbsp;0&nbsp;&nbsp;1&nbsp;&nbsp;0&nbsp;&nbsp;1</summary>

```c
#include <stdio.h<>
int main()
{
    //variable declarations and initializations
    char ch;
    int seen[10] = {0};
    
    printf("Enter a number: ");
    //do-while loop which iterates until the user enters a newline character
    do
    {
        ch = getchar();
        
        //for loop which iterates from 0 to 9
        for (int i = 0; i < 10; i++)
            //conditional statement which checks if the character is a digit
            if (ch - 48 == i)
                seen[i]++;
    } while (ch != '\n');
    
    //for loop printing numbers 0 through 9
    printf("Digit:\t\t");
    for (int i = 0; i < 10; i++)
        printf("%d  ", i);
    
    //for loop which prints the occurrences of each digit
    printf("\nOccurrences:\t");
    for (int i = 0; i < 10; i++)
        printf("%d  ", seen[i]);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number: <u>23478</u>
Digit:          0  1  2  3  4  5  6  7  8  9  
Occurrences:    0  0  1  1  1  0  0  1  1  0
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program where the program can enter more than one number to be tested for repeated digits. The program should terminate when the user enters a number that is less than or equal to 0</summary>

```c
#include <stdio.h>
#include <stdbool.h>

//macro definition for the number of digits in the array
#define TEN 10

int main()
{
    //variable declarations and initializations
    char ch;
    int seen[TEN] = {0}, sum = 0;
    bool flag = false;
    
    //do-while loop which iterates until the user enters a number less than or equal to 0
    do
    {
        printf("Enter a number: ");
        //do-while loop which iterates until the user enters a newline character
        do
        {
            ch = getchar();

            //for loop which iterates from 0 to 9
            for (int i = 0; i < TEN; i++)
                //conditional statement which checks if the character is a digit
                if (ch - 48 == i)
                    seen[i]++;
        } while (ch != '\n');
        
        //summing up the occurrences of each digit
        for (int i = 0; i < TEN; sum += seen[i++]);
            //conditional statement which checks if the user entered exactly one zero digit and no other occurrences
                if (seen[0] == 1 && sum == 1)
                    flag = true;
        
        //conditional statement which checks if the would like to continue inputting numbers
        if (!flag)
        {
            //for loop printing numbers 0 through 9
            printf("Digit:\t\t");
            for (int i = 0; i < TEN; i++)
                printf("%d  ", i);
            
            //for loop which prints the occurrences of each digit
            printf("\nOccurrences:\t");
            for (int i = 0; i < TEN; i++)
                printf("%d  ", seen[i]);
                      
            //for loop which resets the seen array's elements to zero
            for (int i = 0; i < TEN; i++)
                seen[i] = 0;
                      
             printf("\n\n");
             sum = 0;
        }
    } while (!flag);
    
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number: <u>349857394857938475</u>
Digit:          0  1  2  3  4  5  6  7  8  9  
Occurrences:    0  0  0  3  3  3  0  3  3  3  
<br />
Enter a number: <u>394857394875938475938745938745</u>
Digit:          0  1  2  3  4  5  6  7  8  9  
Occurrences:    0  0  0  5  5  5  0  5  5  5  
<br />
Enter a number: <u>394875934758</u>
Digit:          0  1  2  3  4  5  6  7  8  9  
Occurrences:    0  0  0  2  2  2  0  2  2  2  
<br />
Enter a number: <u>0</u>
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>The prototypical Internet newbie is a fellow named B1FF, who has a unique way of writing messages. Here's a typical B1FF communique:<br />
  H3Y DUD3, C 15 R1LLY C00L!!!!!!!!!!<br />
  Write a "B1FF filter" that reads a message entered by the user and translates it into B1FF-speak:<br />
  Enter message: <u>Hey dude, C is rilly cool</u><br />
  In B1FF-speak: H3Y DUD3, C 15 R1LLY COOL!!!!!!!!!!<br />
  Your program should convert the message to upper-case letters, substitute digits for certain letters (A->4, B->8, E->3, I->1, O->0, S->5), and then append 10 or so exclamation marks.</summary>

```c
#include <stdio.h>
#include <ctype.h>

int main()
{
    //variable declarations and initializations
    char message[1024], ch;
    int iterations = 0;
    
    printf("Enter message: ");
    //do-while loop which iterates until the user enters the newline character
    do
    {
        ch = toupper(getchar());
        
        //conditional statement which checks if the user did not enter the newline character
        if (ch != '\n')
            message[iterations++] = ch;
    } while (ch != '\n');
    
    printf("In B1FF-speak: ");
    //for loop which iterates over each character of the user's message
    for (int i = 0; i < iterations; i++)
    {
        //conditional statements which change the value of the user's message according to B1FF-speak
        if (message[i] == 'A')
            message[i] = '4';
        else if (message[i] == 'B')
            message[i] = '8';  
        else if (message[i] == 'E')     
            message[i] = '3'; 
        else if (message[i] == 'I')
            message[i] = '1'; 
        else if (message[i] == 'O')
            message[i] = '0';   
        else if (message[i] == 'S')
            message[i] = '5';
        
        putchar(message[i]);
    }
    
    printf("!!!!!!!!!!");
    
    return 0;
}
```   
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter message: <u>Hey dude, C is rilly cool</u>
In B1FF-speak: H3Y DUD3, C 15 R1LLY C00L!!!!!!!!!!
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that reads a 5 x 5 array of integers and then prints the row sums and the column sums:<br />
  Enter row 1: <u>8 3 9 0 10</u><br />
  Enter row 2: <u>3 5 17 1 1</u><br />
  Enter row 3: <u>2 8 6 23 1</u><br />
  Enter row 4: <u>15 7 3 2 9</u><br />
  Enter row 5: <u>6 14 2 6 0</u></summary>

```c
#include <stdio.h>

//macro definition for the number of rows and columns in the array
#define FIVE 5

int main()
{
    //variable declarations and initializations
    int array[FIVE][FIVE], input, rowTotals[FIVE] = {0}, columnTotals[FIVE] = {0};
    
    //for loop which iterates from 0 to one less than FIVE
    for (int i = 0; i < FIVE; i++) 
    {
        printf("Enter row %d: ", i + 1);
        //for loop which iterates from 0 to one less than FIVE and gets user's input
        for (int j = 0; j < FIVE; rowTotals[i] += array[i][j], columnTotals[j] += array[i][j], j++)
            scanf("%d", &array[i][j]);
    }
    
    //printing the sum of each row
    printf("\nRow totals: ");
    for (int i = 0; i < FIVE; printf("%d ", rowTotals[i++]));
    
    //printing the sum of each column
    printf("\nColumn totals: ");
    for (int i = 0; i < FIVE; printf("%d ", columnTotals[i++]));
    
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter row 1: <u>43 8 3 93 3</u>
Enter row 2: <u>3 8 9 6 0</u>
Enter row 3: <u>3468 43 9 3 3</u>
Enter row 4: <u>3
3 9 32 3</u>
Enter row 5: <u>3 9 8 6 7</u><br />
Row totals: 150 26 3526 50 33 
Column totals: 3520 71 38 140 16
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that translates an alphabetic phone number into numeric form:<br />
  Enter phone number: <u>CALLATT</u><br />
  2255288<br />
  Here are the letters on the keys: 2 = ABC, 3 = DEF, 4 = GHI, 5 = JKL, 6 = MNO, 7 = PRS, 8 = TUV, 9 = WXY. If the original phone number contains nonalphabetic characters (digits or punctuation, for example), leave them unchanged:<br />
  Enter phone number: <u>1-800-COL-LECT</u><br />
  1-800-265-5328<br />
  The program will need to store the phone number (either in its original form or in its numeric form) in an array of characters until it can be printed. You may assume that the phone number is no more than 15 characters long.</summary>

```c
#include <stdio.h>
#include <ctype.h>

//macro definition for the number of characters in the array
#define MAX 15

int main()
{
    //variable declarations and initializations
    char ch, array[MAX];
    int iterations = 0;
    
    printf("Enter phone number: ");
    //do-while loop which iterates until the user enters a newline character
    do
    {
        ch = getchar();
        
        //conditional statement which checks if the user did not enter a newline character
        if (ch != '\n')
            array[iterations++] = ch;
    } while (ch != '\n');
    
    //for loop which converts phone number into numerical representation
    for (int i = 0; i < iterations; i++)
    {
        //conditional statements which converts letters in user's phone number into integers
        if (array[i] >= 'A' && array[i] <= 'C')
            array[i] = '2';
        else if (array[i] >= 'D' && array[i] <= 'F')
            array[i] = '3';
        else if (array[i] >= 'G' && array[i] <= 'I')  
            array[i] = '4';
        else if (array[i] >= 'J' && array[i] <= 'L')
            array[i] = '5';
        else if (array[i] >= 'M' && array[i] <= 'O')
            array[i] = '6';
        else if (array[i] >= 'P' && array[i] <= 'S')
            array[i] = '7';
        else if (array[i] >= 'T' && array[i] <= 'V')
            array[i] = '8';
        else if (array[i] >= 'W' && array[i] <= 'Y')
            array[i] = '9';  
    }
    
    //prints the numerical representation of the user's phone number
    printf("In numeric form: ");
    for (int i = 0; i < MAX; i++)
        printf("%c", array[i]);
    
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter phone number: <u>1-800-COL-LECT</u>
In numeric form: 1-800-265-5328
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>In  the SCRABBLE Crossword Game, players form words using small tiles, each containing a letter and a face value. The face value varies from one letter to another, based on the letter's rarity. (Here are the face values: 1: AEILNORSTU, 2: DG, 3: BCMP, 4: FHVWY, 5: K, 8: JX, 10: QZ). Write a program that computes the value of a word by summing the values of its letters:<br />
  Enter a word: <u>pitfall</u><br />
  Scrabble value: 12<br />
  Your program should allow any mixture of lower-case and upper-case letters in the word. Create an array of 26 elements, corresponding to the 26 letters of the alphabet. For example, element 0 of the array will store 1 (because the SCRABBLE value of the letter A is 1), element 1 of the array will store 3 (because the SCRABBLE value of the letter B is 3), and so forth. As each character of the input word is read, the program will use the array to determine the SCRABBLE value of that character. Use an array initializer to set up the array.</summary>

```c
#include <stdio.h>
#include <ctype.h>

//macro definition for the number of elements in the array
#define MAX 26

int main()
{
    //variable declarations and initializations
    const char array[MAX] = {1, 3, 3, 2, 1, 4, 2, 4, 1, 8, 5, 1, 3, 1, 1, 3, 10, 1, 1, 1, 1, 4, 4, 8, 4, 10};
    char ch;
    int value = 0;
    
    printf("Enter a word: ");
    //do-while loop which iterates until the user enters a newline character
    do
    {
        ch = toupper(getchar());
        
        //conditional statement which checks if the user did not enter a newline character
        if (ch != '\n')
            //for loop which iterates over all letters of the alphabet
            for (int i = 0; i < MAX; i++)
                //conditional statement which checks if the user a certain letter of the alphabet
                if (ch - 65 == i)
                    value += array[i];
    } while (ch != '\n');
    
    printf("Scrabble value: %d\n", value);
    
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a word: <u>Garrett</u>
Scrabble value: 8
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that takes a first name and last name entered by the user and displays the last name, a comma, and the first initial, followed by a period:<br />
  Enter a first and last name: <u>Lloyd Fosdick</u><br />
  Fosdick, L.<br />
  The program will need to store the last name (but not the first name) in an array of characters until it can be printed. You may assume that the last name is no more than 20 characters long.</summary>

```c
#include <stdio.h>

//macro definition for the number of characters in the array
#define MAX 20

int main()
{
    //variable declarations and initializations
    char lastName[MAX], firstLetter, ch;
    int count = 0, iterations = 0;
    
    printf("Enter a first and last name: ");
    //do-while loop which iterates until the user enters a newline character
    do
    {
        ch = getchar();
        
        //conditional statement which checks if the user is entering its first name
        if (ch != ' ' && count == 0 && ch != '\n')
        {
            firstLetter = ch;
            count++;
        }
        //conditional statement which checks if the user is entering the space between the last name and the first letter
        else if (ch == ' ' && count > 0 && ch != '\n')
            count = -1;
        //conditional statement which checks if the user is entering the last name
        else if (ch != ' ' && count == -1 && ch != '\n')
            lastName[iterations++] = ch;
    } while (ch != '\n');
    
    //printing the user's name to the screen
    printf("You entered the name: ");
    for (int i = 0; i < iterations; i++)
        putchar(lastName[i]);
    printf(", %c.\n", firstLetter);
    
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a first and last name: <u>Garrett Ellis</u>
You entered the name: Ellis, G.
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>Write a program that reverses the words in a sentence:<br />
  Enter a sentence: <u>you can cage a swallow can't you?</u><br />
  Reversal of sentence: you can't swallow a cage can you?<br />
  Use a loop to read the characters one by one and store them in a one-dimensional char array. Have the loop stop at a period, question mark, or exclamation point, the terminating character, which is saved in a separate char variable</summary>

```c
#include <stdio.h>

//macro definition for the number of characters in the array
#define MAX 100

int main()
{
    //variable declarations and initializations
    char array[MAX][MAX], ch;
    int words = 0, letters = 0, size[MAX];
    
    printf("Enter a sentence: ");
    //do-while loop which iterates until the user enters a terminating character
    do
    {
        ch = getchar();
        
        //conditional statement which checks if the user input a whitespace character
        if (ch == ' ')
        {
            words++;
            letters = 0;
        }
        //conditional statement which checks if the user did not input a punctuation mark or whitespace character
        else if (ch != '!' && ch != '?' && ch != '!' && ch != ' ')
        {
            array[words][letters++] = ch;
            size[words]++;
        }    
    } while (ch != '.' && ch != '?' && ch != '!');
    
    //for loop which helps to print the user's message in reverse
    for (int i = words; i >= 0; i--)
    {
        for (int j = 0; j < size[i]; j++)
            getchar(array[i][j]);
        if (i > 0)
            putchar(' ');
    }
    
    putchar(ch);
    
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a sentence: <u>Wow Garrett is absolutely amazing!</u>
amazing absolutely is Garrett Wow!
        </code>
      </pre>  
    </details>
  </ul>  
</details>  

<details>
  <summary>One of the oldest known encryption techniques is the Caesar cipher, attributed to Julius Caesar. It involves replacing each letter in a message with another letter that is a fixed number of positions later in the alphabet. (If the replacement would go past the letter Z, the cipher "wraps around" to the beginning of the alphabet. For example, if each letter is replaced by the letter two positions after it, then Y would be replaced by A, and Z would be replaced by B.) Write a program that encrypts a message using a Caesar cipher. The user will enter the message to be encrypted and the shift amount (the number of positions by which letters should be shifted):<br />
  Enter message to be encrypted: <u>Go ahead, make my day.</u><br />
  Enter shift amount (1-25): <u>3</u><br />
  Encrypted message: Jr dkhdg, pdnh pb gdb.<br />
  You may assume that the message does not exceed 80 characters. Characters other than letters should be left unchanged. Lowercase letters remain lowercase when encrypted, and uppercase letters remain uppercase</summary>

```c
#include <stdio.h>
#include <ctype.h>

//macro definition for the number of characters in the array
#define SIZE 80

int main()
{
    //variable declarations and initializations
    char message[SIZE], ch;
    int iterations = 0, shiftAmount;
    
    printf("Enter message to be encrypted: ");
    //reading characters until newline character is encountered
    do
    {
        ch = getchar();
        
        //conditionals statement which checks if the character did not enter a newline character
        if (ch != '\n')
            message[iterations++] = ch;
    } while (ch != '\n');
    
    //getting shift amount from the user
    printf("Enter shift amount: ");
    scanf("%d", &shiftAmount);
    
    //printing encrypted message to screen
    printf("Encrypted message: ");
    for (int i = 0; i < iterations; i++)
    {
        //conditional statements which alter the user's message
        if (message[i] >= 'A' && message[i] <= 'Z' && message[i] + shiftAmount <= 'Z')
            putchar(message[i] + shiftAmount);
        else if (message[i] >= 'A' && message[i] <= 'Z' && message[i] + shiftAmount > 'Z')
            putchar(message[i] + shiftAmount - 26);
        else if (message[i] >= 'a' && message[i] <= 'z' && message[i] + shiftAmount <= 'z')
            putchar(message[i] + shiftAmount);
        else if (message[i] >= 'a' && message[i] <= 'z' && message[i] + shiftAmount > 'z')
            putchar(message[i] + shiftAmount - 26);
        else
            putchar(message[i]);
    }
    
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter message to be encrypted: <u>Garrett is amazing!</u>
Enter shift amount: <u>5</u>
Encrypted message: Lfwwjyy nx frfensl!
        </code>
      </pre>  
    </details>
  </ul>  
</details>  
