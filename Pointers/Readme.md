<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#pointer-variables'>Pointer Variables</a>
  </li> 
  <li>
    <a href='#the-address-and-indirection-operators'>The Address and Indirection Operators</a>
  </li> 
  <li>
    <a href='#pointer-assignment'>Pointer Assignment</a>
  </li> 
  <li>
    <a href='#pointers-as-arguments'>Pointers as Arguments</a>
  </li> 
  <li>
    <a href='#pointers-as-return-values'>Pointers as Return Values</a>
  </li> 
</ol>
</details>

## Pointer Variables
### Declaring Pointer Variables
<ul>
  <li>
    <a>A pointer variable is declared very similarly to a normal variable, the only difference with a pointer variable is that the name of the pointer variable is preceded with a asterisk, *</a>
  </li>
  <li>
    <a>Here is an example of declaring a pointer variable: int *ptr;</a>
  </li>
  <li>
    <a>Pointer variables can be declared on the same line as other variables: int *ptr, num = 1, array[100];</a>  
  </li>  
  <li>
    <a>To print a pointer variable, the %p conversion specification can be used</a>
  </li>  
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initialization
    int arr[] = {5, 8, 2, 9}, *ptr, n = 9;
    ptr = &n;
    //
    printf("The memory address of ptr is: %p\n", &ptr);
    //
    //for loop which displays the memory addresses of each index of an array
    for (int i = 0; i < 4; i++)
        printf("Memory address of arr[%d] = %p\n", i, &arr[i]);    
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
The memory address of ptr is: 00000023E07FF978
Memory address of arr[0] = 00000023E07FF980
Memory address of arr[1] = 00000023E07FF984
Memory address of arr[2] = 00000023E07FF988
Memory address of arr[3] = 00000023E07FF98C
        </code>
      </pre>  
    </details>
  </ul>  
  </details> 
</ul>

## The Address and Indirection Operators
<ul>
  <li>
    <a>To find the address to which a pointer points to, the & operator can be used. If y is declared, &y is the address in memory to which y is stored</a>
  </li>
</ul> 

### The Address Operator
<ul>
  <li>
    <a>To initialize a pointer, the following can be done:<br />
    int i, *ptr;<br />
    ptr = &i;</a>
  </li>
</ul> 

### The Indirection Operator
<ul>
  <li>
    <a>Once a pointer points to an object, the value of the pointer can be dereferenced using the indirection operator, *. For instance, if ptr points to i, then the value of i can be printed to the screen with the following statement: printf("%d\n", *ptr);</a>
  </li>
  <li>
    <a>As long a ptr points to i, *p is simply an alias for i. Furthermore, any alteration to *p changes i and vice versa</a>
  </li>  
</ul>    

## Pointer Assignment
<ul>
  <li>
    <a>An example of pointer assignment is the following:<br />
    int i, j, *p, *q;<br />
    The statement p = &i; is a pointer assignment as p now points to the memory address that i is stored in<br />
    q = p;<br />
    Now, q is a pointer that points to the same memory address as p. q and p are pointers to i. Any alterations to either one of these three variables will be reflected in *p, *q, and i</a>
  </li>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initialization
    int arr[] = {1, 2, 3, 4, 5};
    int *ptr = arr;
    //
    printf("Initial: *ptr = %d\n", *ptr);          
    printf("Next: *(ptr + 2) = %d\n", *(ptr + 2)); 
    *ptr += 2;                                     
    *(ptr + 3) -= 1;                               
    //
    printf("After modification: *ptr = %d, *(ptr + 3) = %d\n", *ptr, *(ptr + 3));
    //
    ptr++;
    printf("Pointer moved: *ptr = %d\n", *ptr);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Initial: *ptr = 1
Next: *(ptr + 2) = 3
After modification: *ptr = 3, *(ptr + 3) = 3
Pointer moved: *ptr = 2
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
int main()
{
    //variable declarations and initialization
    int arr[] = {10, 20, 30, 40, 50};
    int *ptr1 = arr;     //*ptr1 = 10
    int *ptr2 = arr + 3; //*ptr2 = 40
    //
    *ptr1 = *ptr2;       //*ptr1 = 40, arr[0] = 40
    ptr2 = ptr1 + 1;     //ptr2 = arr + 1, *ptr2 = 20
    //
    printf("*ptr1 = %d, *ptr2 = %d\n", *ptr1, *ptr2);
    //
    *ptr2 = 100;
    //
    for (int i = 0; i < 5; i++)
        printf("arr[%d] = %d\n", i, arr[i]);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
*ptr1 = 40, *ptr2 = 20
arr[0] = 40
arr[1] = 100
arr[2] = 30
arr[3] = 40
arr[4] = 50          
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
int main()
{
    //variable declarations and initialization
    int x = 10;
    int y = 20;
    int *ptr1 = &x;
    int *ptr2 = &y;
    //
    printf("Before: x = %d, y = %d\n", x, y);
    //
    *ptr1 = *ptr2;    //*ptr1 = 20, x = 20
    ptr2 = ptr1;      //ptr2 now points to x, ptr2 = &x, x = 20
    *ptr2 = 50;       //*ptr2 = 50, x = 50
    //
    printf("After: x = %d, y = %d\n", x, y);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Before: x = 10, y = 20
After: x = 50, y = 20     
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
int main()
{
    //variable declarations and initialization
    int a = 100, b = 200, c = 300;
    int *ptr1 = &a;    //*ptr1 = 100  
    int *ptr2 = &b;    //*ptr2 = 200 
    int *ptr3 = &c;    //*ptr3 = 300
    //
    *ptr2 = *ptr1;     //*ptr2 = 100, b = 100
    ptr3 = ptr1;       //ptr3 now points to a, ptr3 = &a, *ptr3 = a, a = 100
    //
    printf("After assignments: a = %d, b = %d, c = %d\n", a, b, c);
    //
    *ptr3 = 500;       //ptr3 = &a, *ptr3 = 500, a = 500
    //
    printf("After modification: a = %d, b = %d, c = %d\n", a, b, c);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
After assignments: a = 100, b = 100, c = 300
After modification: a = 500, b = 100, c = 300   
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
int main()
{
    //variable declarations and initialization
    int a = 5;
    int b = 10;
    int *ptr1 = &a;
    int *ptr2 = &b;
    //
    *ptr1 = *ptr2;       //*ptr1 = 10, ptr1 = &a, a = 10
    *ptr2 = *ptr1 + 5;   //*ptr2 = 15, prt2 = &b, b = 15
    //
    printf("a = %d, b = %d\n", a, b);
    printf("*ptr1 = %d, *ptr2 = %d\n", *ptr1, *ptr2);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
a = 10, b = 15
*ptr1 = 10, *ptr2 = 15
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
int main()
{
    //variable declarations and initialization
    int a = 100, b = 200;
    int *p1 = &a;
    int *p2 = &b;
    int *temp = p1;
    //
    p1 = p2;        //p1 is assigned the value stored in p2, *p1 = 200, p1 now points to b
    p2 = temp;      //p2 is assigned the address stored in temp, *p2 = 100, p2 now points to a
    //
    *p1 += 10;      //*p1 = 200 + 10 = 210, b = 210
    *p2 -= 10;      //*p2 = 100 - 10 = 90, a = 90
    //
    printf("a = %d, b = %d\n", a, b);
    printf("*p1 = %d, *p2 = %d\n", *p1, *p2);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
a = 90, b = 210
*p1 = 210, *p2 = 90
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
int main()
{
    //variable declarations and initialization
    int a = 10, b = 20, c = 30;
    int *arr[3] = {&a, &b, &c};
    //
    //printing initial values
    printf("Before modification: a = %d, b = %d, c = %d\n", a, b, c); 
    //
    //modifying pointer array
    *arr[0] = 100;        //arr[0] points to a, a = 100
    *arr[1] = *arr[2];    //arr[1] points to b, b = 30
    arr[2] = arr[0];      //arr[2] points to a
    //
    printf("After modification: a = %d, b = %d, c = %d\n", a, b, c);
    //
    *arr[2] = 200;        //arr[2] points to a, a = 200
    printf("Final values: a = %d, b = %d, c = %d\n", a, b, c);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Before modification: a = 10, b = 20, c = 30
After modification: a = 100, b = 30, c = 30   
Final values: a = 200, b = 30, c = 30          
        </code>
      </pre>  
    </details>
  </ul>  
  </details>
</ul>    

## Pointers as Arguments
<ul>
  <li>
    <a>Pointers offer a solution to the problem where C is by default a pass-by-value language. This is accomplished by passing the memory addresses of variables as arguments to the function's call rather than the variable itself. Now, modifications to the variables declared in main within functions outside of main will be reflected within main after the outside functions' termination</a>
  </li>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
#define MAX 10
//
//function prototype for arrayFun
void arrayFun(int[], int *, int *);
//
int main()
{
    //variable declaration and initialization
    int input, array[MAX], iterations = 0, max, min;
    //
    printf("Enter 10 numbers: ");
    //
    //do-while loop which iterates until 
    do
    {
        scanf("%d", &input);
        //
        array[iterations++] = input;
    } while (iterations < MAX);
    //
    //calling arrayFun function
    arrayFun(array, &max, &min);
    //
    printf("Maximum: %d\n", max);
    printf("Minimum: %d\n", min);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter 10 numbers: <u>43 93 -9 2 3 93 3 23 9 -33</u>
Maximum: 93
Minimum: -33
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
//global variable declaration and initialization
int global_var = 10;
//
//function prototypes for func1 and func2
void func1(int *p);
void func2(int p);
//
int main()
{
    //variable declarations and initializations
    int local_var = 20;
    int *ptr = &local_var;
    //
    //calling func1 and printing variable values to the screen
    func1(ptr);
    printf("After func1: local_var = %d, global_var = %d\n", local_var, global_var);
    //
    //calling func2 and printing variable values to the screen
    func2(global_var);
    printf("After func2: global_var = %d\n", global_var);
    //
    return 0;
}
//
void func1(int *p)
{
    (*p)++;             //p points to local_var, local_var++ = 21
    p = &global_var;    //p now points to global_var
    (*p) += 5;          //global_var = 5 + 10 = 15
}
//
void func2(int p)
{
    p++;                //global_var++, only changes variable outside of main
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
After func1: local_var = 21, global_var = 15
After func2: global_var = 15
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
// global variable declaration
int *global_ptr;
//
//function definition for modifyGlobalPointer
void modifyGlobalPointer(int *p)
{
    global_ptr = p;       //global_ptr now points to local_var
    *global_ptr += 10;    //*global_ptr = 10 + 5 = 15, local_var = 15
}
//
int main()
{
    //variable declaration and initialization
    int local_var = 5;
    //
    //calling modifyGlobalPointer
    modifyGlobalPointer(&local_var);  
    //
    //printing variable values to the screen        
    printf("local_var = %d\n", local_var);    
    printf("*global_ptr = %d\n", *global_ptr); 
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
local_var = 15
*global_ptr = 15
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
//global variable declaration
int *global_ptr;
//
//function definition for setGlobal
void setGlobal(int *p)
{
    global_ptr = p; 
}
//
//function definition for modifyGlobal
void modifyGlobal()
{
    *global_ptr = 100;
}

int main()
{
    //variable declaration and initialization
    int local_var = 20;
    //
    //calling setGlobal function
    setGlobal(&local_var);      
    //
    //calling modifyGlobal function           
    modifyGlobal();      
    //                 
    printf("local_var = %d\n", local_var); 
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
100
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
//global variable declarations
int *global_ptr1, *global_ptr2;
//
//function definition for setPointers
void setPointers(int *p1, int *p2)
{
    global_ptr1 = p1;
    global_ptr2 = p2; 
}
//function definition for swap
void swap()
{
    int temp = *global_ptr1;
    *global_ptr1 = *global_ptr2;
    *global_ptr2 = temp;
}

int main()
{
    //variable declarations and initializations
    int a = 5, b = 10;
    //
    //calling setPointers function
    setPointers(&a, &b);     
    //
    //calling swap function         
    swap();   
    //                        
    printf("a = %d, b = %d\n", a, b); 
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
a = 10, b = 5
        </code>
      </pre>  
    </details>
  </ul>  
  </details>  
</ul>    

### Using const to Protect Arguments
<ul>
  <li>
    <a>To ensure that a function does not modify an argument passed into the function's call, the const modifier can be used. Here, const is placed in the parameter list just before the parameter's data type such as in the following example</a>
  </li> 
</ul>  

## Pointers as Return Values
<ul>
  <li>
    <a>Functions can too return types that are pointers</a>
  </li>
</ul>    
