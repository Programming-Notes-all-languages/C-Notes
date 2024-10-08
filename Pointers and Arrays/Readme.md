<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#pointer-arithmetic'>Pointer Arithmetic</a>
  </li> 
  <li>
    <a href='#using-pointers-for-array-processing'>Using Pointers for Array Processing</a>
  </li> 
  <li>
    <a href='#pointers-and-multidimensional-arrays'>Pointers and Multidimensional Arrays</a>
  </li> 
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>  
</ol>
</details>

## Pointer Arithmetic
<ul>
  <li>
    <a><em>Pointer arithmetic</em> is useful for when a pointer points to an array. Pointer arithmetic in this case makes it so other elements within the array can be easily accessed</a>
  </li>
  <li>
    <a>There are three types of pointer arithmetic: adding an integer to a pointer, subtracting an integer from a pointer, and subtracting one pointer from another</a>
  </li>
</ul>

### Adding an Integer to a Pointer
<ul>
  <li>
    <a>Let's say that there is an array defined along with a pointer and an integer j. If the pointer points to the element at index zero of the array, ptr = &a[0], then ptr + j makes the pointer now point to the array's element j indices after index zero</a>
  </li>
</ul>

### Subtracting an Integer from a Pointer
<ul>
  <li>
    <a>Let's say that there is an array defined along with a pointer and an integer j. If the pointer points to element at index eight, ptr = &a[8], then ptr - j makes the pointer now point to the array's element j indices before index eight</a>
  </li>
</ul>

### Subtracting One Pointer from Another
<ul>
  <li>
    <a>One pointer can be subtracted from another and the result is the number of indices between the two elements that the pointers point to</a>
  </li>
  <li>
    <a>For example, let's say that there is an array that and been declared with a size of eight. There are two pointers, p1 and p2. p1 = &a[1] and p2 = &a[2]. Subtracting p2 from p1, or vice versa, finds the distance between both pointers and in this case, p1 - p2 is equal to -1</a>
  </li>
  <li>
    <a>Subtracting one pointer from another is only defined when both pointers point to elements within the same array; otherwise, this pointer arithmetic will be undefined</a>
  </li>
</ul>         

### Comparing Pointers
<ul>
  <li>
    <a>Pointers can be compared using the relational operators and the equality operators. Using these operators to compare pointers can be meaningful only when the pointer variables both point elements within the same array</a>
  </li>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initialization
    int array[4] = {1, 2, 3, 4}, *ptr1 = &array[1], *ptr2 = &array[3];
    //
    //selection statement which checks if ptr1 is greater than ptr2
    (ptr1 > ptr2) ? (printf("%d ", *ptr1)) : (printf("%d ", *ptr2));
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
4
        </code>
      </pre>  
    </details>
  </ul>  
  </details> 
</ul>    

## Using Pointers for Array Processing
<ul>
  <li>
    <a>Pointer arithmetic enables a pointer pointing to an array to be analyzed as if it were an array</a>
  </li>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initialization
    int arr[9] = {0, 1, 2, 3, 4, 5, 6, 7, 8}, *ptr = arr, sum = 0;
    //
    //for loop which iterates over a pointer to find the sum of an array
    for (; ptr < arr + 9; ptr++)
        sum += *ptr;
    //
    printf("Sum: %d\n", sum);  
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Sum: 36
        </code>
      </pre>  
    </details>
  </ul>  
  </details> 
</ul>

## Using an Array Name as a Pointer
<ul>
  <li>
    <a>The name of an array can be used as a pointer to point to the first element of an array. Remember, an array is a pointer</a>
  </li>
  <li>
    <a>For example, if the following declaration is made, int a[10];, then *a = 7 will store the integer 7 in a[0]. a[1] can be modified by dereferencing a after incrementing a by one: *(a + 1) = 12;</a>
  </li>  
  <li>
    <a>If a pointer is initialized to point to an array, then the pointer can be treated just like an array when using the pointer</a>
  </li>  
</ul>    

## Pointers and Multidimensional Arrays
### Processing the Rows of a Multidimensional Array
<ul>
  <li>
    <a>Pointers can also point to multidimensional arrays. To get a pointer to point to a row within a multidimensional array, the following declarations can be made: a[2][3] = {{1 , 3}, {4, 5, 6}}, *ptr = a[0];. Now, ptr points to the first element within the first row of the multidimensional array declared as a</a>
    <ul>
      <li>
        <a>To then iterate through the multidimensional array using a pointer that points to a row within a multidimensional array, the following declarations and code can be written:</a>
        <details>
        <summary>Example program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initialization
    int a[2][3] = {{1, 2, 7}, {1, 2, 9}}, *ptr = a[0], sum = 0;
    //
    //for loop iterating through the first row of the multidimensional array a
    for (; ptr < a[0] + 3; sum += *ptr, ptr++);
    printf("Sum: %d\n", sum);
    //
    //for loop iterating through the first column of the multidimensional array a
    sum = 0, ptr = a[0];
    for (int i = 0; i < 2; sum += *ptr, ptr = a[++i]);
    printf("Sum: %d\n", sum); 
    //
    return 0;
}
```
</ul></li><ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Sum: 10
Sum: 2
        </code>
      </pre>  
    </details>
  </ul>  
  </details> 
  </li>
</ul>    

### Processing the Columns of a Multidimensional Array
<ul>
  <li>
    <a>To get a pointer to point to a column within a multidimensional array is not as simple as it is with an array's rows</a>
  </li>
</ul>    

## Programming Projects
<details>
    <summary>Write a program that reads a message, and prints the reversal of the message:<br />
    Enter a message: <u>Don't get mad, get even.</u><br />
    Reversal is: .neve teg ,dam teg t'noD<br />
    Use a pointer instead of an integer to keep track of the current position in the array</summary>

```c
#include <studio.h>
//
define MAX 1000
//
int main()
{
    //variable declaration and initialization
    char array[MAX], *ptr = array, ch;
    int size = 0;
    //
    //do-while loop which gets the user's message
    printf("Enter a message: ");
    do
    {
        //conditional statement which ensures that the user did not enter a newline character; otherwise, the pointer assigns the user's input into the next element of the array
        if ((ch = getchar()) != '\n')
            *ptr++ = ch, size++;
    } while (ch != '\n');
    //
    //for loop which reverses the user's message
    --ptr;
    printf("Reversal is: ");
    for (; ptr >= array; putchar(*ptr), ptr--);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a message: Garrett!
Reversal is: !tterraG
        </code>
        </pre>  
      </detairls>
    </ul>  
  </details>
<details>
    <summary>Write a program that reads a message, and then checks whether it is a palindrome (the letters in the message are the same from left to right as from right to left):<br />
    Enter a message: <u>He lived as a devil, eh?</u><br />
    Palindrome<br />
    Enter a message: <u>Madam, I am Adam.</u><br />
    Not a palindrome<br />
    Ignore all characters that are not letters. Use pointers instead of integers to keep track of positions in the array</summary>

```c
#include <stdio.h>
#include <stdbool.h>
//
#define MAX 1000
//
int main()
{
    //variable declarations and initializations
    char array[MAX], *ptr = array, *ptr2, ch;
    int size = 0;
    bool palindrome = true;
    //
    //do-while loop which gets the user's message
    printf("Enter a message: ");
    do
    {
        ch = getchar();
        //
        //conditional statement which ensures that the user did not enter a newline character; otherwise, the pointer assigns the user's input into the next element of the array
        if (ch != '\n' && ((ch >= 'A' && ch <= 'Z') || (ch >= 'a' && ch <= 'z')))
            *ptr++ = ch, size++;
    } while (ch != '\n');
    //
    --ptr;
    ptr2 = array;
    //
    //for loop which checks if the user's message is a palindrome or not
    for (int i = 0, j = size - 1; i < j; i++, j--)
        //if the characters at the current positions are not equal, the palindrome variable is set to false and the loop breaks immediately
        if (*ptr-- != *ptr2++)
            palindrome = false;
    //
    (palindrome) ? (printf("Palindrome\n")) : (printf("Not a palindrome\n"));
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a message: <u>lived devil!!!!!!!!!!!!!!!!!!!!!!</u>
Palindrome
        </code>
        </pre>  
      </details>
    </ul>  
  </details>  