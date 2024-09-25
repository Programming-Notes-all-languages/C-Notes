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
    <a>The <em>scope</em> of a variable is within the function that it was declared in. This means that other functions within the program can share variable names that appeared in other functions</a>
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
        <a>They have scope both within and outside of the variable in which they were declared. They are assessable anywhere in the program</a>
      </li>
    </ul>
  </li>
  <li>
    <a>It is often best practice to limit the use of external variables and have functions communicate via their parameters</a>
  </li>  
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