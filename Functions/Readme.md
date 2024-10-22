<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#defining-and-calling-functions'>Defining and Calling Functions</a>
  </li> 
  <li>
    <a href='#function-declarations'>Function Declarations</a>
  </li> 
  <li>
    <a href='#arguments'>Arguments</a>
  </li> 
  <li>
    <a href='#the-return-statement'>The return Statement</a>
  </li> 
  <li>
    <a href='#program-termination'>Program Termination</a>
  </li> 
  <li>
    <a href='#recursion'>Recursion</a>
  </li> 
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>
</ol>
</details>

## Defining and Calling Functions
### Function Definitions
<ul>
  <li>
    <a>Here is the syntax for a <em>function definition</em> in C:</a>

```c
returnType functionName (parameters) 
{
    statements;
}
```
</li>
    </ul>    
  </li>
  <li>
    <a>Here are a few rules governing the return type of a function:</a>
    <ul>
      <li>
        <a>Functions cannot return arrays but can return any other data types</a>
      </li>
      <li>
        <a>Having a return type of void means that the function does not return a value unlike a function of type int and char</a>
      </li>
      <li>
        <a>In older versions of C, if the return type of a function was omitted, then the return type defaulted as int; however, in newer versions of C, a return type is required when writing the definition of a function</a>
      </li>    
    </ul>
  </li>   
  <li>
    <a>After the return type and name of the function comes the function's parameters. Each parameter needs a data type and a name. If there is more than one parameter, each parameter is separated by a comma</a>   
  </li>
  <li>
    <a>If a function has no parameters, then the word void should appear where the parameters of a function would normally appear</a>
  </li> 
  <li>
    <a>A function can have variable declarations like within the main function. However, the variables declared within the function belong exclusively to that function and not other functions</a>
  </li>      
</ul>    

### Function Calls
<ul>
  <li>
    <a>A function call contains the name of the function followed by the names of the parameters, just their names and not their return type, enclosed in parentheses</a>
  </li>
  <li>
    <a>A void function is always followed by a semicolon to turn the function's call into a statement</a>
  </li>
  <li>
    <a>On the other hand, a function with a return type other than void can be stored in a variable to save the value being returned by the function</a>
  </li>
  <details>
    <summary>Example program</summary>
      <ul>
        <pre>
          <code>
            #include <a><</a>stdio.h<a>></a>
            #include <a><</a>stdbool.h<a>></a><br />
            //isEven function definition which returns a boolean value indicating whether its parameter is even or not
            bool isEven(int n)
            {
                //conditional statement which checks if n is not even
                if (n % 2 == 0)
                    return false;
                else
                    return true;
            }<br />
            int main()
            {
                //variable declarations and initializations
                int input;
                bool isPrimeFlag = true;<br />
                printf("Enter a number: ");
                scanf("%d", &input);<br />
                //conditional statement which prints whether input is a even or not
                if (isEven(input))
                    printf("%d is even\n", input);
                else
                    printf("%d is not even\n", input);<br />
                return 0;
            }
          </code>
        </pre>    
      <details>
      <summary>Output</summary>
        <pre>
          <code>
            Enter a number: 3456345
            3456345 is even
          </code>
        </pre>  
      </details>
    </ul>  
  </details>     
</ul>    

## Function Declarations
<ul>
  <li>
    <a>C does not require that the definition of the function come before main. It is good practice to declare all functions before main and then define them after main</a>
  </li>
  <li>
    <a>Here is the syntax for a <em>function declaration</em>: returnType functionName(parameters);</a>
  </li> 
  <li>
    <a>Function declarations are also known as <em>function prototypes</em>. Function prototypes do not have to include the names of the function's prototypes. Only the data types of the function need to be in the function's declaration. For example, if a function has four parameters of type double, then double, double, double, double needs to be within the parentheses in the function's declaration</a>
  </li>  
  <details>
    <summary>Example program</summary>
      <ul>
        <pre>
          <code>
            #include <a><</a>stdio.h<a>></a>
            #include <a><</a>ctype.h<a>></a><br />
            //function prototype for isEven function
            bool isEven(int);<br />
            int main()
            {
                //variable declarations and initializations
                int input;
                bool isPrimeFlag = true;<br />
                printf("Enter a number: ");
                scanf("%d", &input);<br />
                //conditional statement which prints whether input is a even or not
                if (isEven(input))
                    printf("%d is even\n", input);
                else
                    printf("%d is not even\n", input);<br />
                return 0;
            }<br />
            //isEven function definition which returns a boolean value indicating whether its parameter is even or not
            bool isEven(int n)
            {
                //conditional statement which checks if n is not even
                if (n % 2 == 0)
                    return false;
                else
                    return true;
            }
          </code>
        </pre>    
      <details>
      <summary>Output</summary>
        <pre>
          <code>
            Enter a number: 3456345
            3456345 is even
          </code>
        </pre>  
      </details>
    </ul>  
  </details>  
</ul>    

## Arguments
<ul>
  <li>
    <a>The difference between parameters and <em>arguments</em> is that parameters exist in the function's definition and declaration whereas arguments appear within the function's call</a>
  </li>
  <li>
    <a>In C, arguments are <em>passed by value</em> which means that when a function is called, copies of the arguments' values are passed to the function and any changes made to the arguments' values within the function are not reflected within the function in which the function is called</a>
</ul>    

### Array Arguments
<ul>
  <li>
    <a>Often, arrays are used as arguments when a function is called. Arrays are also often parameters within a function</a>
  </li>
  <li>
    <a>When making an array as a parameter of a function, the data type is needed, then the name of the function followed by []. A second parameter is needed for the size of the array which is just an int parameter</a>
  </li>  
  <li>
    <a>When calling a function with a parameter of an array, the brackets are omitted when passing the array in the function call. For instance, let's say that there is a function called fun which contains two parameters: an int array and an int that contains the size of the array. The call to this function could be as follows: x = functionName(array, arraySize);</a>
  </li>  
  <details>
    <summary>Example program</summary>

```c
//Write a function that reverses the elements of an integer array
//void reverse(int a[], int n)
```
<ul>   
  <details>
    <summary>Output</summary>

```c
void reverse(int a[], int n)
{
    for (int i = 0, j = n - 1; i < j; i++, j--) 
    {
        temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}   
```
  </details>
  </ul>  
</details>
<details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//Write a function that sorts the elements of an integer array a in non-decreasing order using selection sort. For example, if a contains the elements {2, 3, 6, 3, 5}, the function will sort the elements of the array so it contains {2, 3, 3, 5, 6}. The function has the following parameters: a is the integer array, n is the length of a. You are not allowed to use any other arrays except array a to solve this problem
//void my_sort(int a[], int n)
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
void my_sort(int a[], int n)
{
    int i, j;
    for (i = 0; i < n - 1; i++)
    {
        int smallest = i;
        for (j = i; j < n; j++)
        {
            if (a[j] < a[smallest])
                smallest = j;
        }

        int temp = a[smallest];
        a[smallest] = a[i];
        a[i] = temp;
    }
}
        </code>
      </pre>  
    </details>
  </ul>  
</details>
<details>
    <summary>Example program</summary>

```c
//Write a function that rotates an array of integers to the right by a given number of steps. For example, given an array {1, 2, 3, 4, 5} and k = 2, the array should become {4, 5, 1, 2, 3}
//void rotateArray(int arr[], int n, int k)
```
<ul>   
  <details>
    <summary>Output</summary>

```c
void rotateArray(int arr[], int n, int k)
{
    int temp[n];

    for (int i = 0, j = k; i < n; i++, j++)
    {
        if (j == n)
            j = 0;
        temp[j] = arr[i];
    }
} 
```
  </details>
  </ul>  
</details>
</ul>  

### Variable-Length Array Parameters
<ul>
  <li>
    <a>In later versions of C, when arrays are a size of variable length, the variable determining the size of the array can actually be encapsulated within the brackets within the function's definition such as in the following: int sumArray(int size, int array[size])... The parameter specifying the size of the array must come first in the parameter list before the array parameter</a>
  </li>  
  <li>
    <a>When writing the function's prototype for a function that contains a variable-length array as a parameter, the following can be done: int sumArray(int, int[*]); Here, the * notation says that the size of the array is determined by the integer value of the first parameter preceding the int array</a>
  </li>
</ul>  

### Using static in Array Parameter Declarations
<ul>
  <li>
    <a>In later versions of C, the static keyword can be encapsulated within the brackets of an array parameter in a function's declaration and definition. After the keyword static comes an integer number which represents the minimum length of the array. What this does is that it lets the compiler know to store x amount of data for the array with a minimum size of static x. If an array is multidimensional, static may only be used in the array's first dimension</a>
  </li>
</ul>    

### Compound Literals
<ul>
  <li>
    <a>In later versions of C, an array can be created within a function's call and that array can be an argument that is passed to the function</a>
  </li>
  <li>
    <a>Here is the syntax for a compound literal: variableX = functionName((dataType []){element0, element1, element2, ...}, parameter1, parameter2, ...);</a>
  </li>  
</ul>   

## The return Statement
<ul>
  <li>
    <a>A function that has a return type, other than void, must use the return statement at least once to specify what value will be returned when a function is called</a>
  </li>
  <li>
    <a>Here is the syntax for the return statement: return expression;</a>
  </li>
  <li>
    <a>Sometimes, more complex expressions can be expressions following the return statement, such as a conditional operator: return (n >= 0) ? (n) : (0);</a>
  </li>
  <li>
    <a>If the return type of the function does not match the function's return type, then the value being returned by the function will be implicitly converted to match the function's return type</a>
  </li> 
  <li>
    <a>return statements may appear in functions that are of type void; however, the return statement must not contain an expression, just return alone</a>
  </li>    
  <li>
    <a>The return statement stops the execution of the function immediately and returns control back to the function's call</a>   
  </li>  
</ul>  

## Program Termination
<ul>
  <li>
    <a>To terminate the program in main, the return statement can be used. Another way of terminating the program in main is using the exit function. exit belongs to the <a><</a>stdlib.h<a>></a> library</a>
  </li>
  <li>
    <a>To indicate normal termination of the program, 0 can be passed to the exit function like the following: exit(0);</a>
  </li>  
</ul>    

## Recursion
<ul>
  <li>
    <a>A function is recursive if it calls itself</a>
  </li>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
//function prototype for factorial
int factorial(int);
//
int main()
{
    //variable declaration and initialization
    int number;
    //
    printf("Enter a number: ");
    scanf("%d", &number);
    //
    //calling factorial function and printing result
    printf("%d! is: %d\n", number, factorial(number));
    //
    return 0;
}
//
//recursive function to calculate factorial of a number
int factorial(int n)
{
    //conditional statement which checks if n is equal to 1
    if (n == 1)
        return n;
    //
    //conditional statement which evaluates to true if n is yet to equal one    
    else
        return n-- * factorial(n);
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a number: <u>10</u>
10! is: 3628800
        </code>
      </pre>  
    </details>
  </ul>  
</details>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
//function definition for countUpDown 
void countUpDown(int n)
{
    //conditional statement if n is greater than 0
    if (n > 0)
    {
        printf("%d ", n);
        countUpDown(n - 1);
        printf("%d ", n);
    }
}
//
int main()
{
    //calling countUpDown function
    countUpDown(3);
    //
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
3 2 1 1 2 3
        </code>
      </pre>  
    </details>
  </ul>  
</details>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
//function definition for reversePrint
void reversePrint(int n)
{
    //conditional statement which checks if n is not equal to 0
    if (n != 0)
    {
        printf("%d", n % 10);
        reversePrint(n / 10);
    }
}
//
int main()
{
    //calling reversePrint function
    reversePrint(1234);
    //
    return 0;
}
```
<ul> 
  <details>
    <summary>Output</summary>
      <pre>
        <code>
4 3 2 1
        </code>
      </pre>  
    </details>
  </ul>  
</details>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
//function definition for oddDigitsReverse
void oddDigitsReverse(int n)
{
    //conditional statement which checks if n does not equal 0
    if (n != 0)
    {
        if ((n % 10) % 2 != 0)
            printf("%d", n % 10);
        //  
        oddDigitsReverse(n / 10);
    }
}
//
int main()
{
    //calling oddDigitsReverse function 
    //
    oddDigitsReverse(13578);
    //
    return 0;
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
7531
        </code>
      </pre>  
    </details>
  </ul>  
</details>
<details>
    <summary>Example program</summary>

```c
//Write a function that sorts an array in ascending order recursively
//void mergeSort(int a[], int start, int end)
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
void mergeSort(int a[], int start, int end)
{
    if (end == 1)
        return;

    else
    {
        for (int i = 0, max = a[end - 1], temp; i < end; i++)
            if (a[i] > max)
            {
                max = temp = a[i];
                a[i] = a[end - 1];
                a[end - 1] = temp;
            }

        return mergeSort(a, 0, --end);
    }    
}
        </code>
      </pre>  
    </details>
  </ul>  
</details>
</ul>    

## Programming Projects
<details>
    <summary>Write a program that asks the user to enter a series of integers (which it stores in an array), then sort the integers by calling the function. When given an array with n elements, the function must do the following:<br />
    1. Search the array to find the largest element, then move it to the last position in the array.<br />
    2. Call itself recursively to sort the first n - 1 elements of the array </summary>

```c
#include <stdio.h>
//
//function prototype for sort
void sort(int, int[*], const int);
//
int main()
{
    // variable declaration and initialization
    int array[100], input, iterations = 0;
    printf("Enter a series of integers (0 to stop): ");
    //
    //do-while loop which iterates until the user enters the integer 0
    do
    {
        scanf(" %d", &input);
        //
        //conditional statement which checks to make sure the user did not enter 0
        if (input != 0)
            array[iterations++] = input;
    } while (input != 0);
    //
    //calling sort function
    sort(iterations, array, iterations);
    //
    return 0;
}
//
//function definition for sort
void sort(int size, int array[size], const int firstSize)
{
    //local variable declarations and initializations
    int max = 0, temp, maxIndex;
    //
    //conditional statement which checks if size is equal to 1
    if (size == 1)
    {
        for (int i = 0; i < firstSize; i++)
            printf("%d ", array[i]);
        return;  
    }
    //
    //conditional statement which evaluates to true if size is still larger than 1
    else
    {
        //for loop which iterates through the array
        for (int i = 0; i < size; i++)
            //conditional statement which checks if new maximum found in array
            if (array[i] > max)
            {
                max = array[i];
                maxIndex = i;
            }
        //
        //swapping maximum value to be at end of the array
        temp = array[size - 1];
        array[size - 1] = max;
        array[maxIndex] = temp;<br />
        return sort(--size, array, firstSize);
    }
}
```
<ul>   
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a series of integers (0 to stop): <u>5239 -93 3 8 72 9 0</u>
-93 3 8 9 72 5239
          </code>
        </pre>  
      </details>
    </ul>  
  </details>

  <details>
    <summary>Write a function that computes the value of the following polynomial:<br />
    3x<sup>5</sup> + 2x<sup>4</sup> - 5x<sup>3</sup> - x<sup>2</sup> + 7x - 6<br />
    Write a program that asks the user to enter a value for x, calls the function to compute the value of the polynomial, and then displays the value returned by the function</summary>

```c
#include <studio.h>
//
//function prototype for function
double function(double);
//
int main()
{
    // variable declaration and initialization
    double input;
    //
    //getting x value from the user
    printf("3x^5 + 2x^4 - 5x^3 -x^2 + 7x - 6\n");
    printf("Enter a value for x to compute the value of the polynomial: ");
    scanf(" %lf", &input);
    //
    printf("The value of the polynomial with a x value of %.1lf is: %.2lf\n", input, function(input));
    //
    return 0;
}
//
//function definition for function
double function(double x)
{
    return (3 * x * x * x * x * x) + (2 * x * x * x * x) - (5 * x * x * x) - (x * x) + (7 * x) - 6;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
3x^5 + 2x^4 - 5x^3 -x^2 + 7x - 6
Enter a value for x to compute the value of the polynomial: <u>4.5</u>
The value of the polynomial with a x value of 4.5 is: 5905.59
          </code>
        </pre>  
      </details>
    </ul>  
  </details>
