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
    <a href='#function-pointers'>Function Pointers</a>
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
  <details>
    <summary>Example Program</summary>

```c
//Suppose you have just opened the file text.txt and execute the statements shown below:
char buffer[6];

fscanf(pFile, "%s", buffer);
printf("%s", buffer);

//File text.txt consists of a single line of text:
The quick brown fox jumped over the lazy dogs back.
//What will be the output from the printf?
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
        The
        </code>
      </pre>        
    </details>
    </ul>  
  </details> 
</ul>    
  <details>
    <summary>Example Program</summary>
    
```c
//Write a statement that declares a dynamic allocated array a of integers of size n using malloc function
```  
<ul>
  <details>

```c
int *a = malloc(sizeof(int) * n);
```       
  </details>
    </ul>  
  </details>      
</ul>       

### Null Pointers
<ul>
  <li>
    <a>When one of the above memory allocation functions is called, there is always a possibility that the compiler will not be able to allocate a block of memory. If this is the case, the function will return a <em>null pointer</em>. A null pointer is a pointer that points to nothing</a>
  </li>  
  <li>
    <a>To test if the memory allocation function returned a value other than null, the following can be used:</a>

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
    <a>Data that is not freed at the end of a program is said to be <em>garbage</em>. Programs that leave behind garbage have <em>memory leaks</em></a>
  </li>
</ul>    

### The free Function
<ul>
  <li>
    <a>The free function has the following prototype:</a>

```c
void free(void *ptr);
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
  <details>
    <summary>Example Program</summary>

```c 
//Assume that the node structure is declared as:
struct node {
    int value;
    struct node *next;
};
//The following function returns the number of nodes that contains n; it returns 0 if n does not appear in the list. The list parameter points to a linked list
int count_n(struct node *list, int n) {
    struct node *p;
    int count = 0;
    for (p = list; p != NULL; p = p->next)
        //missing statements

    return count;    
}
//Write statements in place of missing statements that will compare the value of the nodes in the linked list with n and update count if the value equals to n
```
<ul>
  <details>
    <summary>Output</summary>

```c
struct node {
    int value;
    struct node *next;
};

int count_n(struct node *list, int n) {
    struct node *p;
    int count = 0;
    for (p = list; p != NULL; p = p->next)
        if (p->value == n)
            count++;

    return count;    
}
```
  </details>
    </ul>  
  </details> 
</ul>       

### Declaring a Node Types
<ul>
  <li>
    <a>To make a linked list, the first thing that is needed is a structure to represent a single node in the list. Here is what a node structure looks like:</a>

```c
struct Node {
    int value;         //data stored in the node
    struct Node *next; //pointer to the next node
};
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
    
    //freeing dynamically allocated memory
    for (struct Node *p = head; p != NULL; p = p->next)
        free(p); 

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
  </li>
<details>
    <summary>Example Program</summary>

```c 
//Given a linked list of node declared as follows, how would you know if a linked list of node named list is an empty list?
struct node {
    int number;
    struct node *next;
};
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
The first and only item in the linked list would be of type struct node * and would have a value of NULL        
        </code>
        </pre>  
      </details>
    </ul>  
  </details>
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

    //freeing dynamically allocated memory
    for (struct Node *p = head; p != NULL; p = p->next)
        free(p); 

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

    //freeing dynamically allocated memory
    for (struct Node *p = head; p != NULL; p = p->next)
        free(p);     

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

    //freeing dynamically allocated memory
    for (struct Node *p = head; p != NULL; p = p->next)
        free(p);    

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
  <details>
    <summary>Example Program</summary>

```c 
//Write a program that includes a function that deletes a node from a linked list that has an integer value of 1
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int value;
    struct Node *next;
};

struct Node *delete(struct Node *);

int main()
{
    struct Node *head = malloc(sizeof(struct Node));
    head->value = 0;
    head->next = NULL;

    struct Node *second = malloc(sizeof(struct Node));
    second->value = 1;
    head->next = second;
    second->next = NULL;

    struct Node *third = malloc(sizeof(struct Node));
    third->value = 2;
    second->next = third;
    third->next = NULL;

    head = delete(head);

    for (struct Node *ptr = head; ptr != NULL; ptr = ptr->next)
        printf("%d\n", ptr->value);

    return 0;
}

struct Node *delete(struct Node *head)
{
    struct Node *cur, *prev;

    for (cur = head, prev = NULL; cur != NULL && cur->value != 1; prev = cur, cur = cur->next);

    if (cur == NULL)
        return head;
    if (prev == NULL)
        return head->next;
    else
        prev->next = cur->next;    
    
    free(cur);
    return head;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
0
2
        </code>
        </pre>  
      </details>
    </ul>  
  </details>
  <details>
    <summary>Example Program</summary>

```c 
//Complete the function clear_list to release all nodes from a linked list

struct node {
    int value;
    struct node *next;
};

void clear_list(struct node *list) {
    struct node *temp;

    while (list != NULL) {
        temp = list;
        //missing code here
    }
}
```
<ul>
  <details>
    <summary>Output</summary>

```c
void clear_list(struct node *list) {
    struct node *temp;

    while (list != NULL) {
        temp = list;
        list = temp->next;
        free(temp);
    }
}
```
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

    //freeing dynamically allocated memory
    for (struct Node *p = head; p != NULL; p = p->next)
        free(p);     

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
  <details>
    <summary>Example Program</summary>

```c
//Here is a linked list. Implement a function that reverses the list. The node struct is defined as:

struct node {
    int value;
    struct node *next;
}

//Write a function called reverse_list that reverses the linked list, and returns the head of the new reversed list

struct node *reverse_list(struct node *head) {

}
```
<ul>
  <details>
    <summary>Output</summary>

```c
struct node *reverse_list(struct node *head) {
    int nodes = 0, i = 0;

    for (struct node *ptr = head; ptr != NULL; ptr = ptr->next, nodes++);

    struct node allNodes[nodes];

    for (struct node *ptr = head; ptr != NULL; ptr = ptr->next)
        allNodes[i++] = *ptr;

    for (struct node *ptr = head; ptr != NULL; ptr = ptr->next)
        ptr->value = allNodes[--i].value;

    return head;
}
```
  </details>
    </ul>  
  </details> 
  <details>
    <summary>Example Program</summary>

```c    
//Write a function to insert a new node into its proper place in an ordered list, returning a pointer to the first node in the modified list

struct node {
    int value;
    struct node *next;
}
```
<ul>
  <details>
    <summary>Output</summary>

```c
struct node {
    int value;
    struct node *next;
}

struct node *insert_into_ordered_list(struct node *list, struct node *new_node)
{
    struct node *cur, *prev;

    for (cur = list, prev = NULL; cur != NULL && new_node->value > cur->value; prev = cur, cur = cur->next);

    new_node->next = cur;

    if (prev == NULL)
      return new_node;
    else {
        prev->next = new_node;
        return list;
    }  
}
```
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
x: 4  //an alternate call to function is functionPtr(4);
        </code>
        </pre>  
      </details>
    </ul>  
  </details> 
  <details>
    <summary>Example Program</summary>

```c 
//What is the output of the following program?
#include <stdio.h>
int f1(int (*f) (int));
int f2(int i);

int main(void) {
    printf("%d\n", f1(f2));
    return 0;
}

int f1(int (*f) (int)) {
    int n, num = 0;
    for (n = 0; n < 3; n++)
        num = f(n);
    return num;    
}

int f2(int i) {
    return i * i + i;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
6
        </code>
        </pre>  
      </details>
    </ul>  
  </details>   
  <details>
    <summary>Example Program</summary>
A function named integrate that integrates a mathematical function f can be made by passing f as an argument and a and b are the range for the integration, both a and b are of type double. Function f can be any function that takes a double parameter and returns a double. The function integrate returns a double. Write a function prototype for the integrate function
<ul>
  <details>
    <summary>Output</summary>

```c
double integrate(double (*f) (double x), double a, double b);
```
  </details>
    </ul>  
  </details> 
  <details>
    <summary>Example Program</summary>
Write a program that creates three functions: add(int, int), subtract(int, int), and multiply(int, int); stores pointers to these functions in an array of function pointers; and prompts the user to choose an operation (add, subtract, multiply) on two numbers, then uses the appropriate function pointer from the array to perform the operation
<ul>
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>

int add(int, int);
int subtract(int, int);
int multiply(int, int);

int main()
{
    int (*addPtr) (int, int) = add;
    int (*subtractPtr) (int, int) = subtract;
    int (*multiplyPtr) (int, int) = multiply;
    int (*functionPtrs[3]) (int, int) = {addPtr, subtractPtr, multiplyPtr};
    int numOne, numTwo, selection;

    printf("Enter two numbers:\nNumber 1: ");
    scanf("%d", &numOne);
    printf("Number 2: ");
    scanf("%d", &numTwo);

    printf("Choose an operation:\n1. Addition\n2. Subtraction\n3. Multiplication\nSelection: ");
    scanf("%d", &selection);

    if (selection < 1 || selection > 3) {
        printf("Invalid selection. Exiting...\n");
        return 1;
    }

    else
    {
        if (selection == 1)
            printf("Result: %d\n", functionPtrs[0](numOne, numTwo));
        else if (selection == 2)
            printf("Result: %d\n", functionPtrs[1](numOne, numTwo));
        else
            printf("Result: %d\n", functionPtrs[2](numOne, numTwo));        
    }

    return 0;
}

int add(int a, int b)
{
    return a + b;
}

int subtract(int a, int b)
{
    return a - b;
}

int multiply(int a, int b)
{
    return a * b;
}
```
  </details>
    </ul>  
  </details> 
  <details>
    <summary>Example Program</summary>
Write a function apply_operation that: takes a function pointer as one of its parameters; takes two integers as additional parameters; and calls the function pointer with the two integers and returns the result
<ul>
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>

int add(int, int);
int subtract(int, int);
int applyOperation(int (int, int), int, int);

int main()
{
    int num1, num2, selection;
    int (*addPtr) (int, int) = add;
    int (*subtractPtr) (int, int) = subtract;
    int (*applyPtr) (int (int, int), int, int) = applyOperation;

    printf("Enter two integers:\nInteger 1: ");
    scanf("%d", &num1);
    printf("Integer 2: ");
    scanf("%d", &num2);

    printf("Choose an operation (1. Addition or 2. Subtraction):\nSelection: ");
    scanf("%d", &selection);

    if (selection < 1 || selection > 2)
    {
        printf("Invalid selection. Exiting...\n");
        return 1;
    }

    if (selection == 1)
        printf("The sum of %d and %d is: %d\n", num1, num2, applyPtr(addPtr, num1, num2));
    else if (selection == 2)
        printf("The subtraction of %d from %d is: %d\n", num2, num1, applyPtr(subtractPtr, num1, num2));

    return 0;
}

int add(int a, int b) {return a + b;}
int subtract(int a, int b) {return a - b;}
int applyOperation(int (*operation)(int, int), int a, int b) {return operation(a, b);}
```
  </details>
    </ul>  
  </details>
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

//we need to provide qsort a special function
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
<details>
    <summary>Write a program that sorts a series of words entered by the user:<br />
    Enter word: foo<br />
    Enter word: bar<br />
    Enter word: baz<br />
    Enter word: quux<br />
    Enter word:<br />
    In sorted order: bar baz foo quux</summary>

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

//macro definition for maximum string length
#define MAX 20

//function prototype for compare which is used to compare two strings
int compare(const void *, const void *);

int main()
{
    //variable declarations and initializations
    char **str = NULL, buffer[MAX];
    int count = 0;

    //do-while loop which iterates until the user enters an empty string
    do
    {
        //dynamically resizing the array of pointers to strings
        str = realloc(str, (1 + count) * sizeof(char *));
        
        printf("Enter word: ");
        scanf("%s", buffer);

        //dynamically resizing the array of strings 
        str[count] = malloc((strlen(buffer) + 1) * sizeof(char));    
        
        //if the user enters an empty string, break the loop
        if (strcmp(buffer, "") != 0)
            strcpy(str[count++], buffer);
    } while (strcmp(buffer, "") != 0);

    //sorting the array of strings in alphabetical order using qsort function
    qsort(str, count, sizeof(char *), compare);
    
    //printing the number of distinct words
    printf("In sorted order: ");
    for (char **ptr = str; ptr < str + count; free(*ptr), ptr++)
        printf("%s ",  *ptr);

    free(str);

    return 0;
}

//function definition for compare which returns an integer value from the strcmp function
int compare(const void *a, const void *b)
{
    char *str1 = *(char **)a;
    char *str2 = *(char **)b;

    return strcmp(str1, str2);
}
```
  </details>

<details>
    <summary>Write a program that uses qsort to sort an array of pointers</summary>

```c 
#include <stdio.h>
#include <stdlib.h>

//function prototype for compare
int compare(const void *, const void *);

int main()
{
    //variable declarations and initializations
    int a = 11, b = 22, c = 3, d = 4, *ptr = &a, *ptr2 = &b, *ptr3 = &c, *ptr4 = &d, *array[4] = {ptr, ptr2, ptr3, ptr4};

    qsort(array, 4, sizeof(int *), compare);

    //for loop which prints *array's contents
    for (int i = 0; i < 4; i++)
        printf("%d ", *array[i]);
}

//function definition for compare to be used with qsort
int compare(const void *a, const void *b)
{
    int x = **(int **)a;
    int y = **(int **)b;

    return x - y;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
3 4 11 22 
        </code>
        </pre>  
      </details>
    </ul>  
  </details>   
