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
</ul>

## THe Address and Indirection Operators
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
    The statement p = &i; is pointer assignment as p now points to the memory address that i is stored in<br />
    q = p;<br />
    Now, q is a pointer that points to the same memory address as p. q and p are pointers to i. Any alterations to either one of these three variables will be reflected in *p, *q, and i</a>
  </li>
</ul>    

## Pointers as Arguments
<ul>
  <li>
    <a>Pointers offer a solution to the problem where C is by default a pass by value language. This is accomplished by passing the memory addresses of variables as arguments to the function's call rather than the variable itself. Now, modifications the variables declared in main within functions outside of main will be reflected within main after the outside functions' termination</a>
  </li>
  <details>
    <summary>Example program</summary>
      <ul>
        <pre>
          <code>
            #include <a><</a>stdio.h<a>></a><br />
            #define MAX 10<br />
            //function prototype for arrayFun
            void arrayFun(int[], int *, int *);<br />
            int main()
            {
                //variable declaration and initialization
                int input, array[MAX], iterations = 0, max, min;<br />
                printf("Enter 10 numbers: ");<br />
                //do-while loop which iterates until 
                do
                {
                    scanf("%d", &input);<br />
                    array[iterations++] = input;
                } while (iterations < MAX);<br />
                //calling arrayFun function
                arrayFun(array, &max, &min);<br />
                printf("Maximum: %d\n", max);
                printf("Minimum: %d\n", min);<br />
                return 0;
            }
          </code>
        </pre>    
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
</ul>    

### Using const to Protect Arguments
<ul>
  <li>
    <a>To ensure that a function does not modify an arguments passed into the function's call, the const modifier can be used. Here, const is placed in the parameter list just before the parameter's data type such as in the following example</a>
  </li> 
</ul>  

## Pointers as Return Values
<ul>
  <li>
    <a>Functions can too return types that are pointers</a>
  </li>
</ul>    