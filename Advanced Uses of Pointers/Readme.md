<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#dynamic-storage-allocation'>Dynamic Storage Allocation</a>
  </li>    
  <li>
    <a href='#dynamically-allocated-strings'>Dynamically Allocated Strings</a>
  </li>    
  <li>
    <a href='#dynamically-allocated-arrays'>Dynamically Allocated Arrays</a>
  </li>  
  <li>
    <a href='#deallocating-storage'>Deallocating Storage</a>
  </li>  
  <li>
    <a href='#linked-lists'>Linked Lists</a>
  </li>  
  <li>
    <a href='#Function Pointers'>Function Pointers</a>
  </li>  
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>    
</ol>
</details>

## Dynamic Storage Allocation
### Memory Allocation Functions
<ul>
  <li>
    <a>To allocate storage dynamically, one of the three following functions needs to be called within the stdlib.h header:</a>
    <ul>
      <li>
        <a>malloc: allocates a block of memory but does not initialize it</a>
      </li>
      <li>
        <a>calloc: allocates a block of memory and clears it</a>
      </li>
      <li>
        <a>realloc: resizes a previously allocated block of memory</a>
      </li>
    </ul>
  </li>
</ul>       

### Null Pointers
<ul>
  <li>
    <a>When one of the above memory allocation functions is called, there is always a possibility that the compiler will not be able to allocate a block of memory. If this is the case, the function will return a <em>null pointer</em>. A null pointer is a pointer that points to nothing</a>
  </li>  
  <li>
    <a>To test if memory allocation function returned a value other than null, the following can be used:</a>

```c 
int *array, size = 10;
array = malloc(size * sizeof(int));

if (array == NULL)
    printf("Memory allocation function failed\n");
```
  </li>
</ul>

## Dynamically Allocated Strings
<ul>
  <li>
    <a>The malloc function has the following prototype:</a>

```c
void *malloc(size_t size);
```
  </li>
  <li>
    <a>The malloc function allocates a block of memory, in bytes, and returns a pointer</a>
    <ul>
      <li>
        <a>To allocate space in memory for a string with n characters and store it in a variable of type char *, the following declaration can be made:</a>

```c
p = malloc(n + 1);  
```
  </li>
  </ul>
  </li>
</ul>  

## Dynamically Allocated Arrays
<ul>
  <li>
    <a>The malloc function can be used to allocate memory for an array the same way it was used to allocate enough memory for a string</a>
  </li>
  <li>
    <a>Here is the syntax for creating a dynamically allocated array of size n:</a>

```c
int *a = malloc(n * sizeof(int));
```
  </li>
</ul>    

### The calloc Function
<ul>
  <li>
    <a>An alternative to the malloc function is the calloc function which too is used to dynamically allocate memory for an array. The difference is that calloc clears the memory that it allocates</a>
  </li>
  <li>
    <a>The calloc function has the following prototype:</a>

```c
void *calloc(nmemb, size);
```
  <ul>
      <li>
        <a>Here, calloc allocates space for an array with nmemb number of elements where each member is size number of bytes</a>
      </li>
    </ul>  
  </li>
  <li>
    <a>For example, the following call of calloc allocates memory for an array called a of size n integers:</a>

```c
a = calloc(n, sizeof(int));
```
  </li>
</ul>    

### The realloc Function
<ul>
  <li>
    <a>The realloc function is used to resize an array that has been dynamically created</a>
  </li>
  <li>
    <a>The realloc function has the following prototype:</a>

```c 
void *realloc(void *ptr, size);
```
  <ul>
      <li>
        <a>When the realloc function is called, the ptr must point to a block of memory that was obtained by a previous call of either malloc, calloc, and realloc</a>
      </li>
    </ul>    
  </li>
  <li>
    <a>The realloc function returns a null pointer if the function cannot enlarge the memory block of ptr, then the function returns a null pointer</a>
  </li>  
</ul>    

## Deallocating Storage
<ul>
  <li>
    <a>The memory allocation functions obtain blocks of memory from a storage pool known as the <em>heap</em></a>
  </li>
  <li>
    <a>Data that is not freed at the end of a program is said to be <em>garbage</em>. Programs that leave behind garbage have a <em>memory leaks</em></a>
  </li>
</ul>    

### The free Function
<ul>
  <li>
    <a>The free function has the following prototype:</a>

```c
void freeI(void *ptr);
```
  </li>
  <li>
    <a>Calling the free function releases a bloc of memory that ptr points to</a>
  </li>  
</ul> 

## Linked Lists
<ul>
  <li>
    <a>A <em>linked list</em> consists of a chain of structures, which are called <em>nodes</em>, where each node contains a pointer to the next node in the chain</a>
  </li>
  <li>
    <a>A linked list is an alternative to an array as it is more flexible. Nodes can be easily inserted and removed from a linked list whereas the elements of the array cannot be removed or have elements inserted</a>
  </li>  
</ul>    

### Declaring a Node Types
<ul>
  <li>
    <a>To make a linked list, the first thing that is needed is a structure to represent a single node in the list. Here is what a node structure looks like:</a>

```c
struct Node {
    int value;         //data stored in the node
    struct Node *next; //pointer to the next node
}
```  
  </li>
  <li>
    <a>Next, a variable will be needed that always points to the first node in the list. The following declaration can be made:</a>

```c
struct Node *first = NULL;
```
  </li>
  <li>
    <a>Here are the steps involved in creating a node:</a>
    <ul>
      <li>
        <a>Allocate memory for the node</a>
      </li>
      <li>
        <a>Store data in the node</a>
      </li>
      <li>
        <a>Insert the node into the list</a>
      </li>
    </ul>        
  </li>
  <li>
    <a>When creating a node, a temporary variable is needed to point to the node temporarily: struct Node *newNode;</a>
    <ul>
      <li>
        <a>The malloc function is used to allocate memory for the new node: newNode = malloc(sizeof(struce Node));</a>
      </li>
      <li>
        <a>newNode now points to a block of memory that is just large enough to hold a Node structure</a>
      </li>
    </ul>    
  </li>  
  <li>
    <a>The last node in the list contains a null pointer (NULL)</a>
  </li>  
  <details>
    <summary>Example Program</summary>

```c 
#include <stdio.h>
#include <stdlib.h>

//structure definition for a Node in a linked list
struct Node
{
    int value;
    struct Node *next;
};

int main()
{
    //initializing head node
    struct Node *head = malloc(sizeof(struct Node));
    head->value = 1;
    head->next = NULL;

    //initializing second node
    struct Node *second = malloc(sizeof(struct Node));
    second->value = 2;
    second->next = NULL;
    head->next = second;

    //initializing third node
    struct Node *third = malloc(sizeof(struct Node));
    third->value = 3;
    third->next = NULL;
    second->next = third;

    return 0;
}
```
  </details>
</ul>   

### The -> Operator
<ul>
  <li>
    <a>The <em>right arrow selection</em> is a minus sign followed by the >. The -> operator is a combination of the * and . operators. Essentially, this operator dereferences the node while selecting one of the structure's members</a>
  </li>
  <li>
    <a>Using the -> operator, newNode->value = 10; is equivalent to (*newNode).value = 10;</a>
  </li>  
  <li>
    <a>Here is an example of using the scanf and the -> operator: scanf("%d", &newNode->value);
</ul>

### Inserting a Node at the Beginning of a Linked List
<ul>
  <li>
    <a>An advantage of a linked list is that nodes can be added at any point in the linked list. The below is an example of how to add a new node to the beginning of a linked list</a>
  </li>
  <details>
    <summary>Example Program</summary>

```c 
#include <stdio.h>
#include <stdlib.h>

//structure definition for a Node in a linked list
struct Node
{
    int value;
    struct Node *next;
};

//function to insert a new node with a given value at the beginning of the linked list
struct Node *insertFirst(struct Node *, const int *);

int main()
{
    //initializing head node
    struct Node *head = malloc(sizeof(struct Node));
    head->value = 1;
    head->next = NULL;

    //initializing second node
    struct Node *second = malloc(sizeof(struct Node));
    second->value = 2;
    second->next = NULL;
    head->next = second;

    //initializing third node
    struct Node *third = malloc(sizeof(struct Node));
    third->value = 3;
    third->next = NULL;
    second->next = third;

    //inserting a new node with value 4 at the beginning of the linked list
    struct Node *first = insertFirst(head, 4);

    return 0;
}

//function to insert a new node with a given value at the beginning of the linked list
struct Node *insertFirst(struct Node *head, const int *intValue)
{
    //allocating memory for the new node 
    struct Node *first = malloc(sizeof(struct Node));
    first->value = *intValue;
    first->next = head;

    return first;
}
```
  </details>
</ul>     

### Searching a Linked List
<ul>
  <li>
    <a>To search through a linked list, a for statement is often used</a>
  </li>
  <li>
    <a>This is the syntax used for iterating through a linked list:</a>

```c
for (struct Node *p = first; p != NULL; p = p->next)
    ...
```
  </li>
  <details>
    <summary>Example Program</summary>

```c 
#include <stdio.h>
#include <stdlib.h>

//structure definition for a Node in a linked list
struct Node
{
    int value;
    struct Node *next;
};
int main()
{
    //head node in linked list
    struct Node *head = malloc(sizeof(struct Node));
    head->value = 1;
    head->next = NULL;

    //second node in linked list
    struct Node *second = malloc(sizeof(struct Node));
    second->value = 2;
    second->next = NULL;
    head->next = second;

    //third node in linked list
    struct Node *third = malloc(sizeof(struct Node));
    third->value = 3;
    third->next = NULL;
    second->next = third;

    //printing the values of nodes in linked list
    for (struct Node *p = head; p != NULL; p = p->next)
        printf("%d ", p->value);

    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
1 2 3
        </code>
        </pre>  
      </details>
    </ul>  
  </details>
</ul>    

### Deleting a Node from a Linked List
<ul>
  <li>
    <a>Deleting a node involves the following three steps:</a>
    <ul>
      <li>
        <a>Locate the node to be deleted</a>
      </li>
      <li>
        <a>Alter the previous node so that it skips the deleted node</a>
      </li>
      <li>
        <a>Call the free function to release the memory that was previously occupied by the deleted node</a>
        <ul>
          <li>
            <a>Here is the syntax for the free function:</a>

```c
free(structPtr);
```
  </li>
    </ul>        
  </li>
  </ul>
  <details>
    <summary>Example Program</summary>

```c 
#include <stdio.h>
#include <stdlib.h>

//structure definition for a Node in a linked list
struct Node
{
    int value;
    struct Node *next;
};
int main()
{
    //head node in linked list
    struct Node *head = malloc(sizeof(struct Node));
    head->value = 1;
    head->next = NULL;

    //second node in linked list
    struct Node *second = malloc(sizeof(struct Node));
    second->value = 2;
    second->next = NULL;
    head->next = second;

    //third node in linked list
    struct Node *third = malloc(sizeof(struct Node));
    third->value = 3;
    third->next = NULL;
    second->next = third;

    //deleting the second node in linked list
    head->next = third;
    free(second);

    //printing the values of nodes in linked list
    for (struct Node *p = head; p != NULL; p = p->next)
        printf("%d ", p->value);

    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
1 3
        </code>
        </pre>  
      </details>
    </ul>  
  </details>
</ul>    

### Ordered Lists
<ul>
  <li>
    <a>When the nodes of a list are stored by the data stored inside of the nodes, then that is called an <em>ordered</em> linked list</a>
  </li>
  <li>
    <a>Inserting a node into an ordered linked list is more difficult; however, searching through an ordered linked list is faster</a>
  </li> 
  <details>
    <summary>Example Program</summary>

```c 
#include <stdio.h>
#include <stdlib.h>

//structure definition for a Node in a linked list
struct Node
{
    int value;
    struct Node *next;
};

//function prototype for sorting a linked list to be an ordered linked list
void sorted(struct Node *);

int main()
{
    //head node in linked list
    struct Node *head = malloc(sizeof(struct Node));
    head->value = 5;
    head->next = NULL;

    //second node in linked list
    struct Node *second = malloc(sizeof(struct Node));
    second->value = 2;
    second->next = NULL;
    head->next = second;

    //third node in linked list
    struct Node *third = malloc(sizeof(struct Node));
    third->value = 4;
    third->next = NULL;
    second->next = third;

    sorted(head);

    for (struct Node *i = head; i != NULL; i = i->next)
        printf("%d ", i->value);

    return 0;
}

//function definition for sorting a linked list
void sorted(struct Node *head)
{
    //nested for loop for iterating over the list
    for (struct Node *i = head; i != NULL; i = i->next)
        for (struct Node *j = i->next; j != NULL; j = j->next)
            //swapping linked list values
            if (i->value > j->value)
            {
                int temp = i->value;
                i->value = j->value;
                j->value = temp;
            }
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
2 4 5
        </code>
        </pre>  
      </details>
    </ul>  
  </details> 
</ul>    

## Function Pointers
<ul>
  <li>
    <a>Function pointers are common in C as functions can be passed as arguments. When passing a function pointer as an argument, the function pointer must be declared</a>
  </li>
  <li>
    <a>Here is the syntax for the declaration of a function pointer:</a>

```c
returnType (*ptrFunction) (anotherReturnType)
```
  <ul>
      <li>
        <a>returnType: this will point to functions that return a variable of type returnType</a>
      </li>
      <li>
        <a>*ptrFunction: this is the name of the function pointer variable</a>
      </li>
      <li>
        <a>anotherReturnType: this will point to functions that have one parameter of type anotherReturnType</a>
      </li>
    </ul>        
  </li>
  <li>
    <a>Essentially, function pointers are pointers to functions. This enables pointers to call functions rather than just calling the function itself. Below is an example of how a function pointer can be used:</a>
  </li>  
  <details>
    <summary>Example Program</summary>

```c 
#include <stdio.h>

void function(int x)
{
    printf("x: %d\n", x);
}

int main()
{
    void (*functionPtr) (int) = function;

    (*functionPtr) (4);
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
x: 4
        </code>
        </pre>  
      </details>
    </ul>  
  </details> 
  <ul>
    <li>
      <a>An alternative function call for (*functionPtr) (4) is functionPtr(4)</a>
    </li>
  </ul>    
</ul>    

### The qsort Function
<ul>
  <li>
    <a>The qsort function belongs to the stdlib.h header</a>
  </li>
  <li>
    <a>The qsort function purpose is that it is capable of sorting an array</a>
  </li>
  <li>
    <a>Here is the qsort function syntax:</a>

```c
int compare(const void *x_void, const void *y_void)
{
    //converting the type of pointer from void pointer to int pointer
    int x = *(int *)x_void;
    int y = *(int *)y_void;

    //let's say x = 2 and y = 5. Since x - y is less than 0, that tells qsort that x should go before y in the array. That means that the array is being sorted in ascending order
    return x - y;
}

void qsort(void *array, int arrayLength, int sizeof(int), int compare /*function name can be anything but must be of type int*/);

// We need to provide qsort a special function
//
//int comparator(const void *x, const void *y);
//
//return value of the function will affect the sorting order
//
// < 0 if x should go before y
// 0 if x is equivalent to y
// > 0 if x should go after y
//
```
  </li>
  <details>
    <summary>Example Program</summary>

```c 
#include <stdio.h>
#include <stdlib.h>

int compare(const void *, const void *);

int main()
{
    int a[] = {8, 7, 9, 10, 111, 345, 3, 2, 1, 1};
    int length = 10;

    qsort(a, length, sizeof(int), compare);

    for (int *ptr = a, i = 0; ptr < a + length; i++, ptr++)
        printf("a[%d] = %d\n", i, *ptr);

    return 0;    
}

int compare(const void *x_void, const void *y_void)
{
    int x = *(int *)x_void;
    int y = *(int *)y_void;

    return x - y;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
a[0] = 1                                                                                                                       
a[1] = 1
a[2] = 2
a[3] = 3
a[4] = 7
a[5] = 8
a[6] = 9
a[7] = 10
a[8] = 111
a[9] = 345
        </code>
        </pre>  
      </details>
    </ul>  
  </details> 
</ul>      

## Programming Projects
