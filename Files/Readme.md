<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#streams'>Streams</a>
  </li>   
  <li>
    <a href='#file-operations'>File Operations</a>
  </li>   
  <li>
    <a href='#formatted-input-output'>Formatted Input Output</a>
  </li>   
  <li>
    <a href='#character-input-output'>Character Input Output</a>
  </li>   
  <li>
    <a href='#line-input-output'>Line Input Output</a>
  </li>   
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li>   
</ol>
</details>

## Streams
<ul>
  <li>
    <a>Accessing a stream in a C program is done by using a <em>file pointer</em> which are of type FILE *. FILE is a data type that is declared within the stdio.H</A>
  </li>
  <li>
    <a>Here is the syntax for the declaration of a file pointer</a>
    <ul>
      <li>

```c
FILE *fp1;
```
  </ul>
  </li>
</ul>  

## File Operations
### Opening a File
<ul>
  <li>
    <a>Opening a file requires a function call to the fopen function. There are two parameters to the fopen function: the first parameter is a string containing the name of the file to be opened and the second parameter is the <em>mode string</em> which specifies what operations will be performed on the file</a>
  <li>
    <a>The fopen function returns a variable of type file pointer which is often stored in a file pointer variable to be used later in the program</a>
  </li>
  <li>
    <a>Here is a typical call to the fopen function:</a>

```c
FILE = fopen("in.dat", "r"); //opens in.dat for reading
```  
  </li>
  <li>
    <a>To test if a file opened successfully, the file pointer after it is assigned a value from the fopen function can be compared to NULL. If the file pointer is equal to NULL, the file was not opened successfully; otherwise, the file was opened successfully</a>
    <ul>
      <li>
        <a>Here is an example of how to implement the above call:</a>

```c
#include <stdlib.h>

FILE *filePtr;

filePtr = fopen("garrett.txt", "r");
if (filePtr == NULL) {
    printf("The file was not open successfully\n");
    exit(EXIT_FAILURE);
}
```
  </ul>
  </li>
</ul>  

### Modes
<ul>
  <li>
    <a>To open a file, one of the following mode strings below are used:</a>

<table>
  <tr>
    <th>String</th>
    <th>Meaning</th>
  </tr>
  <tr>
    <td>"r"</td>
    <td>Open for reading</td>
  </tr>
  <tr>
    <td>"w"</td>
    <td>Open for writing (file does not need to exist)</td>
  </tr>
  <tr>
    <td>"a"</td>
    <td>Open for appending (file does not need to exist)</td>
  </tr>    
  <tr>
    <td>"r+"</td>
    <td>Open for reading and writing, starting a beginning</td>
  </tr>       
  <tr>
    <td>"w+</td>
    <td>Open for reading and writing (truncate if file exists)</td>
  </tr>   
  <tr>
    <td>"a+"</td>
    <td>Open for reading and writing (append if file exists)</td>
  </tr> 
</table>
</li>
</ul>

### Closing a File
<ul>
  <li>
    <a>The fclose function enables a program to close a file that is no longer needed. The fclose function takes in one argument of type file pointer which is the string name for the file that is desired to be closed</a>
  </li>
  <li>
    <a>The fclose function's return type is of type integer. fclose will return 0 if the function was closed successfully; otherwise, it returns an error code</a>
  </li>  
  <li>
    <a>Here is the syntax for the fclose function:</a>

```c
fclose(filePointerVariable);
```
  </li>
</ul>  

### File Buffering
<ul>
  <li>
    <a>Transferring data to and from sources can sometimes be a slow and tedious operation. To achieve better performance, file <em>buffering</em> is implemented</a>
  </li>
  <li>
    <a>The fflush function can be used to flush the buffer</a>
  </li>
  <li>
    <a>Here is the syntax for the fflush function:</a>

```c
fflush(filePtr);
```
  </li>
</ul>    

### The rewind Function
<ul>
  <li>
    <a>To bring the cursor back to the beginning of a file, the rewind function can be useful. For instance, if the control within the file is at line 5, a call to the rewind function will bring the cursor to line 1</a>
  </li>
  <li>
    <a>Here is the syntax for the rewind function:</a>

```c
rewind(filePtr);
```
</li>
</ul>

## Formatted Input Output
### The ...printf Functions
<ul>
  <li>
    <a>To print information to a given file stream, the following function can be used: fprintf. This function is very similar to printf, the difference being that printf writes to stdout wheres fprintf writes to the stream given within the first argument when called</a>
  </li>
  <li>
    <a>The fprintf function takes in two arguments: the first argument is the file stream, also known as the file pointer, and the second argument is a string that the programmer writes. The second argument acts just like the printf function</a>
  </li>
  <li>
    <a>Here is the syntax for the fprintf function:</a>

```c
fprintf(filePtr, "Garrett is %d years old\n", 21);
```
  </li>
</ul>      

### The ...scanf Functions
<ul>
  <li>
    <a>Alike the scanf function, the fscanf function is used to read input from a stream given by the first argument rather than stdin with scanf</a>
  </li>
  <li>
    <a>There are two arguments to the fscanf function: the first argument is the file stream, the file pointer, and the second argument is a string with conversion specifiers that says what information will be written to that file stream. The second argument works just like the first argument within the scanf function</a>
  </li>
  <li>
    <a>Here is the syntax for the fscanf function:</a>

```c
fscanf(filePtr, "%d%d", &i, &j);
```
  </li>
</ul>    

### Detecting End-of-File
<ul>
  <li>
    <a>To check whether the control has reached the end of a file, the feof function can be used</a>
  </li>
  <li>
    <a>The feof function has only one parameter which is of type file pointer. This parameter is the file pointer to a defined file</a>
  </li>
  <li>
    <a>The feof function returns a value of type integer. It will return the value 0 when the end of the file has not been reached; otherwise, it will return a nonzero integer</a>
  </li>
  <li>
    <a>Here is the syntax for the feof function:</a>

```c
intVariable = feof(filePtr);
```
  </li>
</ul>  

### Detecting Errors
<ul>
  <li>
    <a>The ferror function is used to determine if any errors occurred on a file stream. This function is often used after file operations, such as reading and writing from a file to ensure that the operations were successful</a>
  </li>
  <li>
    <a>The ferror function takes in one argument during its function call which is a variable of type FILE pointer. The variable that gets passed to this function is the file pointer to the desired function</a>
  </li>
  <li>
    <a>The return value of the ferror function is of type int. The function will return a nonzero integer if there was an error in the stream; otherwise, ferror will return 0 if an error occured</a>
  </li>  
  <li>
    <a>Here is the syntax for the ferror function:</a>

```c
intVariable = ferror(filePtr);
```
  </li>
</ul>      

## Character Input Output
### Output Functions
<ul>
  <li>
    <a>There are three output functions for printing characters in C: int fputc(int c, FILE *stream);, int putc(int c, FILE *stream);, and int putchar(int c);</a>
    <ul>
      <li>
        <a>putchar writes one character to stdout</a>
      </li>
      <li>
        <a>fputc and putc are more general versions of putchar that write a single character to an arbitrary stream. fputc(ch, fp); writes ch to fp and putc(ch, fp); writes ch to fp</a>
      </li>
      <li>
        <a>Here is the syntax for the fputc function and the putc function:</a>

```c
fputc(character, fp);
putc(character, fp);
```     
  </li>   
  </ul>
  </li>
</ul>        

### Input Functions
<ul>
  <li>
    <a>There are four input functions for writing characters in C: int fgetc(FILE *stream);, int getc(FILE *stream);, int getchar();, and ungetc(int c, FILE *stream);</a>
    <ul>
      <li>
        <a>getchar reads a character from the stdin stream. ch = getchar() reads in a single character from stdin and stores that character in ch</a>
      </li>
      <li>
        <a>fgetc and getc read a character from an arbitrary stream. ch = fgetc(fp); and ch = getc(fp); read a single character from the file pointer fp</a>
      </li>
      <li>
        <a>Here is the syntax for the fgetc function and getc function:</a>

```c
charVariable = fgetc(fp);
charVariable = getc(fp);
```
  </li>
  </ul>      
  </li> 
</ul>

## Line Input Output
### Output Functions
<ul>
  <li>
    <a>There are two functions for printing strings to a stream in C: int fputs(const char *s, FILE *stream); and int puts(const char *s);</a>
    <ul>
      <li>
        <a>The puts function writes a string of characters to the stdout stream</a>
      </li>
      <li>
        <a>The fputs function is a more general version of the puts function. The first argument is the string that will be printed to the file stream that is passed to the second parameter of the fputs function</a>
      </li>
      <li>
        <a>Here is the syntax for the fputs function:</a>

```c
fputs(string, fp);
```
  </li>
  </ul>
  </li>
</ul>    

### Input Functions
<ul>
  <li>
    <a>There are two input functions for reading a string to a stream in C: char *fgets(char *s, int n, FILE *sream); and char *gets(char *s);</a>
    <ul>
      <li>
        <a>The gets function reads a line of input from the stdin stream and stores it in the string variable that is passed to its parameter during the function's call</a>
      </li>
      <li>
        <a>The fgets function is a more general version of gets as it can read a string from any stream and store it in the string variable that is passed to its parameter during the function's call</a>
      </li>
      <li>
        <a>Here is the syntax for the fgets function:</a>

```c
fgets(string, sizeof(string), fp); //reads a line from fp
```
  <ul>
    <li>
      <a>This function call to fgets will read characters until it reaches the first new-line character or the character at index sizeof(string) - 1, whichever happens to occur first</a>
    </li>
  </ul>    
  </li>
  </ul>    
  </li>  
</ul>  

## Programming Projects
<details>
    <summary>Write a program that converts all letters in a file to upper case. Characters other than letters should not be changed. The program should obtain the file name from the command line and write its output to stdout</summary>

```c
#include <stdio.h>
#include <stdlib.h>

//macro definition for the maximum size of the file string and input string
#define MAX 1000

//function definition for convertToUpperCase function which converts lowercase letters to uppercase
void convertToUpperCase(char *);

int main(int argc, char *argv[])
{
    //variable declarations and initializations
    char **fileName = argv + --argc, string[MAX], fileString[MAX];
    FILE *filePtr;

    //opening *fileName file in write+ mode
    filePtr = fopen(*fileName, "w+");

    //checking if file was successfully opened or not
    if (filePtr == NULL) 
    {
        printf("Error opening file.\n");
        exit(EXIT_FAILURE);
    }

    //reading user input which will be converted to uppercase and added to the file
    printf("What would you like to add to the file?: ");
    scanf("%s", string);
    printf("I will now convert your string to upper case and add this converted string to %s\n", *fileName);

    //converting the input string to uppercase and storing it in the string variable
    convertToUpperCase(string);

    //writing the converted string to the file
    fprintf(filePtr, "%s\n", string);

    //going back to the beginning of the file to read the updated content
    rewind(filePtr);
    printf("Successfully added the string to the file.\n");
    printf("The updated content of the file is: ");
    fscanf(filePtr, "%s", fileString);
    printf("%s\n", fileString);

    //closing the file
    fclose(filePtr);

    return 0;
}

//function definition for convertToUpperCase function which converts lowercase letters to uppercase
void convertToUpperCase(char *str)
{
    //iterating through each character in the string and converting lowercase letters to uppercase if found
    for (char *ptr = str; *ptr!= '\0'; ptr++)
        if (*ptr >= 'a' && *ptr <= 'z')
            *ptr = *ptr - 'a' + 'A';
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
gcc -Wall main.c
./a.out Garrett.txt
----------------------------------------------------------------
----------------------------------------------------------------       
What would you like to add to the file?: <u>Garrettisthebest</u>
I will now convert your string to upper case and add this converted string to Garrett.txt
Successfully added the string to the file.
The updated content of the file is: GARRETTISTHEBEST
        </code>
        </pre>  
      </details>
    </ul>  
  </details> 
<details>
    <summary>Write a program that concatenates any number of files by writing them to standard output, one after the other, with no break between files. For example, the following command will display the files f1.c, f2.c, and f3.c on the screen:
    ./a.out f1.c f2.c f3.c
    The program should issue an error message if any file cannot be opened</summary>

```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[])
{
    //variable declarations and initializations
    FILE *fp;
    char temp;

    //for loop which iterates over each command-line argument (file name)
    for (char **ptr = argv + 1; ptr < argv + argc; ptr++)
    {
        //open the file in read mode and check if it exists
        fp = fopen(*ptr, "r");
        if (fp == NULL)
        {
            printf("Error opening file: %s\n", *ptr);
            exit(EXIT_FAILURE);
        }

        //while loop which reads all characters within the file until the end of the file is reached
        while (!feof(fp))
        {
            fscanf(fp, "%c", &temp);
            putchar(temp);
        }

        //close the file
        fclose(fp);
    }

    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
gcc -Wall main.c
./a.out main2.c main3.c
----------------------------------------------------------------
----------------------------------------------------------------
main2.c     
This came from main2.c
----------------------------------------------------------------
----------------------------------------------------------------
main3.c
This came from main3.c
----------------------------------------------------------------
----------------------------------------------------------------
Output:
This came from main2.cThis came from main3.c
        </code>
        </pre>  
      </details>
    </ul>  
  </details>   
<details>
    <summary>Write a program that counts the number of characters in a text file</summary>

```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[])
{
    //variable declarations and initializations
    FILE *fp;
    char **fileName = argv + --argc, temp;
    int counter = 0;

    //opening file
    fp = fopen(*fileName, "r");

    //while loop which iterates until the end of the file
    while (!feof(fp))
    {
        fscanf(fp, "%c", &temp);
        counter++;
    }

    printf("There are %d characters in the file.\n", counter);

    //closing file
    fclose(fp);

    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
gcc -Wall main.c
./a.out text.txt
----------------------------------------------------------------
----------------------------------------------------------------
text.txt:
Garrett
----------------------------------------------------------------
----------------------------------------------------------------
Output:        
There are 8 characters in the file.
        </code>
        </pre>  
      </details>
    </ul>  
  </details>     
<details>
    <summary>Write a program that counts the number of words in a text file. A word is any sequence of non-white-space characters</summary>

```c
#include <stdio.h>
#include <stdlib.h>

//macro definition for the maximum size of each word in the file
#define MAX 1000

int main(int argc, char *argv[])
{
    //variable declarations and initializations
    FILE *fp;
    char **fileName = argv + --argc, temp[MAX];
    int counter = 0;

    //opening the file in read mode
    fp = fopen(*fileName, "r");

    //error handling for file opening
    while (!feof(fp))
    {
        fscanf(fp, "%s", temp);
        counter++;
    }

    printf("Total number of words in the file: %d\n", counter);

    //closing the file
    fclose(fp);

    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
gcc -Wall main.c
./a.out        
----------------------------------------------------------------
----------------------------------------------------------------
text.txt:
Garrett is the best a a a
----------------------------------------------------------------
----------------------------------------------------------------
Output:        
Total number of words in the file: 7
        </code>
        </pre>  
      </details>
    </ul>  
  </details>
  <details>
    <summary>Write a program that counts the number of lines in a text file</summary>

```c
#include <stdio.h>
#include <stdlib.h>

//macro definition for the maximum size of each word in the file
#define MAX 1000

int main(int argc, char *argv[])
{
    //variable declarations and initializations
    FILE *fp;
    char **fileName = argv + --argc, temp;
    int counter = 0;

    //opening the file in read mode
    fp = fopen(*fileName, "r");

    //while loop which iterates through the file until the end of the file
    while (!feof(fp))
    {
        fscanf(fp, "%c", &temp);
        //incrementing the counter if the scanned character is a newline character
        if (temp == '\n')
            counter++;
    }

    printf("Number of lines in the file: %d\n", ++counter);

    //closing the file
    fclose(fp);

    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
gcc -Wall main.c
./a.out text.txt        
----------------------------------------------------------------
----------------------------------------------------------------
text.txt:
Garrett
David
Ellis
----------------------------------------------------------------
----------------------------------------------------------------
Output:
Number of lines in the file: 3
        </code>
        </pre>  
      </details>
    </ul>  
  </details>         