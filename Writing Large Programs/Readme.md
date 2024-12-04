<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#source-files'>Source Files</a>
  </li>    
  <li>
    <a href='#header-files'>Header Files</a>
  </li>    
  <li>
    <a href='#dividing-a-program-into-files'>Dividing a Program into Files</a>
  </li>  
  <li>
    <a href='#building-a-multiple-file-program'>Building a Multiple File Program</a>
  </li>    
</ol>
</details>

## Source Files
<ul>
  <li>
    <a>A program can be divided into any number of <em>source files</em>. By convention, source files have a .c extension</a>
  </li>
  <li>
    <a>Source files contain parts of a program, more specifically, the definitions of functions and variables</a>
  </li>  
  <li>
    <a>One source file must contain a function named main, which serves as the starting point for the program</a>
  </li>  
  <li>
    <a>A program containing multiple source files saves time as each source file can be compiled separately</a>
  </li>   
</ul>    

## Header Files
<ul>
  <li>
    <a><em>Header files</em> contain function prototypes, macro definitions, and typedef definitions. By convention, header files have a .h extension</a>
  </li>
  <li>
    <a>The #include directive tells the preprocessor to insert the contents of a specified file</a>
    <ul>
      <li>
        <a>The #include directive is used to bring the file's contents into each of the source files</a>
      </li>
    </ul>    
  </li> 
  <li>
    <a>The #include directive has two primary forms:</a>
    <ul>
      <li>
        <a>The first is used for header files that belong to C's library: #include <a><</a>filename<a>></a>
      </li>
      <li>
        <a>The second is used for all other header files: #include "filename"</a>
      </li>
    </ul>
  </li>   
  <li>
    <a>The file name in an #include directive may include information that helps locate the file, such as the file path</a>
  </li>     
</ul>    

## Dividing a Program into Files
<ul>
  <li>
    <a>Each set of related functions will go in a separate source file. For example, a function named foo could have a source file named foo.c</a>
  </li>
  <li>
    <a>Each source file will have a matching header file. For example, foo.h is the header file for foo.c. foo.h will contain the function prototype for the function defined in foo.c</a>
  </li>
  <li>
    <a>foo.h will be included in each source file that needs to call a function defined in foo.c</a>
  </li>
  <li>
    <a>foo.h will also be included in foo.c so the compiler can check that the prototypes in foo.h match the definitions in foo.c</a>
  </li>
  <li>
    <a>To protect the contents of the header file, a #ifndef-#endif pair can encapsulate the contents of the header file. Here is the syntax for #ifndef-#endif:</a>

```c
#ifndef identifier

#endif
```
  </li>
</ul>    

## Building a Multiple-File Program
<ul>
  <li>
    <a>Each source file in the program can be compiled separately</a>
  </li>
    <a>Header files do not need to be compiled</a>
  </li>
  <li>
    <a>Here is how to compile a multi-file program using Unix: gcc -o executable main.c source1.c source2.c</a>
    <ul>
      <li>
        <a>Here, the executable file is created called executable. To run the executable, do the following: ./executable</a>
      </li>
    </ul>
  </li>      
</ul>    

### Makefiles
<ul>
  <li>
    <a>To make it easier to build large programs, Unix originated the concept of the <em>makefile</em></a>
  </li>
  <li>
    <a>A makefile is divided into three groups of lines. Each group is known as the <em>rule</em>. Each line underneath the rule begins with a tab character rather than a series of spaces</a>
    <ul>
      <li>
        <a>The first line in each rule gives a <em>target</em> file, followed by the files on which it depends</a>
      </li>
      <li>
        <a>The second line is a <em>command</em> to be executed if the target should need to be rebuilt</a>
      </li>
    </ul>
  </li>      

```makefile
project10_registration: project10_registration.o student.o
	gcc -o project10_registration project10_registration.o student.o

project10_registration.o: project10_registration.c student.h
	gcc -c project10_registration.c

student.o: student.c student.h
	gcc -c student.c
```
  </li>
  <li>
    <a>Once a makefile has been created, the make command can be used to invoke the commands necessary to rebuild the program</a>
  </li>
  <li>
    <a>A makefile is normally stored in a file named Makefile</a>
  </li>
  <li>
    <a>There should only be one Makefile in a directory</a>
  </li>      
</ul>    
