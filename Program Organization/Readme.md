<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#local-variables'>Local Variables</a>
  </li> 
  <li>
    <a href='#external-variables'>External Variables</a>
  </li> 
  <li>
    <a href='#blocks'>Blocks</a>
  </li> 
  <li>
    <a href='#organizing-a-c-program'>Organizing a C Program</a>
  </li> 
</ol>
</details>

## Local Variables
<ul>
  <li>
    <a>A variable that is declared within the body of the function is said to be <em>local</em>
  </li>
  <li>
    <a>A local variable will keep its value during the duration of the function's execution. When the function terminates, the variable may or may not retain the value from the previous execution of the function</a>
  </li> 
  <li>
    <a>The <em>scope</em> of a variable is within the function it was declared in. This means that other functions within the program can share variable names that appeared in other functions</a>
  </li>   
</ul>    

### Static Local Variables
<ul>
  <li>
    <a>A variable can have the identifier <em>static</em> in front of it which means that the variable occupies a permanent storage location. For instance, if a static variable is declared in a function outside of main, even after that outside function terminates, the static variable will still hold its value</a>
  </li>
  <li>
    <a>Static variables still have scope which means it is not visible to other functions--only the function in which the static variable was declared and initialized</a>
  </li>
  <li>
    <a>Here is the syntax for a static variable: static dataType variableName;</a>
  </li>    
</ul>    

## External Variables
<ul>
  <li>
    <a>External variables, also known as <em>global variables</em> have two key properties that are different than local variables</a>
    <ul>
      <li>
        <a>They have static variable properties meaning that there is a permanent spot in memory for them</a>
      </li>
      <li>
        <a>They have scope both within and outside of the variable in which they were declared. They are accessible anywhere in the program</a>
      </li>
    </ul>
  </li>
  <li>
    <a>It is often best practice to limit the use of external variables and have functions communicate via their parameters</a>
  </li>  
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

int main()
{
    //variable declarations and initializations
    int arr[] = {1, 2, 3, 4, 5};
    int n = 10;
    {
        int n = 20;
        for (int i = 0; i < 3; i++)
        {
            int n = i;
            printf("%d ", n);
        }
        printf("%d ", n);
    }
    printf("%d ", n);
    
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
0 1 2 20 10
        </code>
      </pre>  
    </details>
  </ul>  
  </details>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

//function definition for test
void test(int a)
{
    printf("%d ", a); // prints the value of 'a' passed to the function
}

int main()
{
    int a = 5;
    test(a);
    {
        int a = 10;
        test(a);
        {
            int a = 15;
            test(a);
        }
        test(a);
    }
    test(a);
    
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
5 10 15 10 5
        </code>
      </pre>  
    </details>
  </ul>  
  </details>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

int main()
{
    //variable declaration and initialization
    int i = 1;

    //nested for loops
    for (int i = 0; i < 3; i++)
    {
        for (int i = 0; i < 2; i++)
            printf("%d ", i);
        printf("%d ", i);
    }
    
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
0 1 0 0 1 1 0 1 2
        </code>
      </pre>  
    </details>
  </ul>  
  </details>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

int main()
{
    int i = 5;
    for (int i = 0; i < 3; i++)
    {
        for (int j = i; j < 3; j++)
        {
            int i = 10;
            i++;
            printf("%d ", i);
        }
        printf("%d ", i);
    }
    
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
11 11 11 0 11 11 1 11 2
        </code>
      </pre>  
    </details>
  </ul>  
  </details>
</ul>     

## Blocks
<ul>
  <li>
    <a>Variables that are declared within blocks, { declarations statements }, have block scope which means they cannot be referenced outside of the block that encapsulates them. Variables declared within blocks can be declared static</a>
  </li>
</ul>  

## Organizing a C Program
<ul>
  <li>
    <a>Here is the proper way to organize a program in C:</a>
    <ul>
      <li>
        <a>#include directives</a>
      </li>  
      <li>
        <a>#define directives</a>
      </li> 
      <li>
        <a>Type definitions</a>
      </li> 
      <li>
        <a>Declarations of external variables</a>
      </li> 
      <li>
        <a>Prototypes for functions other than main</a>
      </li> 
      <li>
        <a>Definition of main</a>
      </li> 
      <li>
        <a>Definitions of other functions</a>
      </li> 
    </ul>
  </li>
</ul>      
