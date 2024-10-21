<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#string-literals'>String Literals</a>
  </li> 
  <li>
    <a href='#string-variables'>String Variables</a>
  </li> 
</ol>
</details>

## String Literals
<ul>
  <li>
    <a><em>String literals</em> are a sequence a characters that are enclosed within double quotes</a>
  </li>
  <li>
    <a>Strings are essentially character arrays. Each character within a string is stored into an index of the char array. The name of the string is the char array</a>
  </li>
  <li>  
    <a>When the compiler encounters a string literal of length size, the program sets aside size + 1 amount of memory for the string</a>
    <ul>
      <li>
        <a>A string literal contains all the characters within string, plus a single \0 character called the <em>null character</em>, which is an escape sequence, is appended after the end of the last character</a>
      </li>
      <li>
        <a>For example, the string literal "abc" is stored into an array of type char in four characters in the following order: 'a', 'b', 'c', and '\0'</a>
      </li>   
    </ul>
  </li>   
</ul>  

### Operations on String Literals
<ul>
  <li>
    <a>Like with arrays, string literals can be pointed to by pointers. Pointers that point to string literals are of type char * and can only point to one index, one character, within the string literal</a>
  </li>
  <li>
    <a>Unlike with arrays, string literals following declarations cannot be modified. Any attempt to modify a string variable will result in undefined behavior</a>
  </li>  
</ul>   

### String Literals versus Character Constants
<ul>
  <li>
    <a>The difference between a string literal and a character constant is the following: a string literal is represented by a pointer where the content of the string is stored in memory and a character constant is where a character is represented by an integer</a>
  </li>
</ul>    

## String Variables
### Initializing a String Variable
<ul>
  <li>
    <a>In C, there is no data type for a string; instead, an array of characters are used to create a "string variable"</a>
  </li>
  <li>
    <a>Here is the syntax for creating a string variable:</a>

```c
int length = 12;
char variableName[length + 1] = "Garrett Ellis";
```
  </li>    
  <li>
    <a>If the length of the char array is longer than the string literal assigned to the character array, then the remaining indices of the array are simply assigned a null character</a>
  </li>
  <li>
    <a>The size of the char array can be omitted, just like with any other arrays that are initialized. The array's size will be one greater than the number of elements within the char array because the last element of a character array must be a null character</a>
  </li>    
</ul>   

### Character Arrays versus Character Pointers
<ul>
  <li>
    <a>There are a few key differences between character arrays and character pointers:</a>
    <ul>
      <li>
        <a>Character arrays can have its contents be modified just like any other array</a>
      </li>
      <li>
        <a>Character pointers that point to a string literal cannot modify the string literal</a>  
      </li>
      <li>
        <a>Regarding character arrays, the declared character array is simply the name of the array whereas a character pointer can point to an indefinite number of string literals</a>
      </li>
    </ul>
  </li>
</ul>   

## Reading and Writing Strings
### Writing Strings Using printf and puts
<ul>
  <li>
    <a>The conversion specified %s enables the programmer to print a string to the screen</a>
  </li>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initialization
    char str[] = "Garrett is amazing!";
    //
    printf("%s\n", str);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Garrett is amazing!
        </code>
      </pre>  
    </details>
  </ul>  
  </details> 
  <li>
    <a>To print part of a string, the conversion specifier %.ps can be used to display p number of characters from index zero</a>
  </li>
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//
int main()
{
    //variable declarations and initialization
    char str[] = "Garrett is amazing!";
    //
    printf("%.7s\n", str);
    //
    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Garrett
        </code>
      </pre>  
    </details>
  </ul>
  </details> 
  <li>
    <a>The puts function is used to print strings to the screen. The puts functions has one argument of type char array, which is the string to be printed</a>
    <ul>
      <li>
        <a>Here is the syntax for the puts function:</a>

```c
puts(variableName);
```
  </li>    
</ul> 

### Reading Strings Using scanf and gets
<ul>
  <li>
    <a>The conversion specifier for the scanf function to read in a string from the user is still the %s specifier</a>
    <ul>
      <li>
        <a>When scanf is called, it skips white spaces; therefore, a string that is read using scanf will always never contain white space characters</a>
      </li>
      <li>
        <a>scanf will no usually read an entire desired input because the new-line character will cause scanf to stop reading the user's input</a>
      </li>   
      <li>
        <a>The scanf function will always append a null character to the end of the user's string and will not store the new-line character that the user input to terminate the function</a>
      </li>  
    </ul>    
  </li>
  <li>
    <a>The gets function is slightly different than the scanf function:</a>
    <ul>
      <li>
        <a>The gets function does not skip white space characters at any point within getting the user's input</a>
      </li>
      <li>
        <a>The gets function continues to read the user's input until the user enters a new-line character; however, the new-line character, like with the scanf function, will not be an element of the character array. Instead, the null character will be appended to the end of the user's input</a>
      </li>
    </ul>      
  </li> 
  <li>
    <a>When using the gets function, there will often be an error message associated with that function; instead, it is often recommended to the use the fgets function</a>
    <ul>
      <li>
        <a>The fgets function takes in three arguments: the first argument is the string variable that the user's input will be stored in, the second argument is the one less than the maximum number of characters that the user can read in, and lastly the third argument is stdin, which tells the compiler that the function will read in a string from the standard input</a>
      </li>
      <li>
        <a>Unlike C's gets function, the fgets function stores the new-line character that the new-line character that the user input's to terminate the function</a>
      </li>  
      <li>
        <a>Here is the syntax for fgets:</a>

```c
fgets(strVariable, strSize, stdin);
```
  </ul>
  </li>       
</ul>    

## Accessing the Characters in a String
<ul>
  <li>
    <a>Since strings are essentially character arrays, strings can be accessed using subscripting to access each element of the string</a>
  </li>
  <li>
    <a>Unlike with arrays previously in this course, character arrays, when passed to a function via an argument, do not need to include an additional argument that defines the size of the string. Instead, the program can test for the null character, '\0', which will determine that the end of the character array has been reached</a>
  </li>
</ul>   

## Using the C String Library
<ul>
  <li>
    <a>There is a C library with the header name &lt;string.h&gt; that is used for comparing and manipulating strings</a>
  </li>
</ul>    

### The strcpy (String Copy) Function
<ul>
  <li>
    <a>The strcpy function takes advantage of the fact that a string cannot be reassigned using the assignment operator. What the strcpy function does it that it redeclares a string by passing two string into the function where the contents of the second argument are assigned to the string variable passed in the first parameter</a>
  </li>
  <li>
    <a>Here is the syntax for strcpy:</a>

```c
strcpy(str1, str2);
```
  </li>
</ul>    

### The strlen (String Length) Function
<ul>
  <li>
    <a>The strlen function returns the length of a string, not including the null character(s) appended to the end of the string</a>
  </li>
  <li>
    <a>Here is the syntax for strlen:</a>

```c
strlen(strVariable);
```
  </li>
</ul>    

### The strcat (String Concatenation) Function
<ul>
  <li>
    <a>The strcat function appends one string onto another. The strcat function takes in two arguments: the first argument is the string that will have more characters appended to it and the second argument is the string that will be appended to the first string</a>
  </li>
  <li>
    <a>Here is the syntax for strcat:</a>

```c
strcat(str1, str2);
```
  </li>
</ul>    

### The strcmp (String Comparison) Function
<ul>
  <li>
    <a>The strcmp function compares two strings together and returns a value either less than, greater than, or equal to 0. This function compares to strings lexicographically, meaning it compares two strings based on the order in which the string's characters appear in the dictionary</a>
  </li>
  <li>
    <a>The relational operators and logical operators can be used with the strcmp function</a>
  </li>  
  <li>
    <a>Here is the syntax for strcmp:</a>

```c
if (strcmp(str1, str2) == 0)
```
  </li>
</ul>    

## Arrays of Strings
<ul>
  <li>
    <a>The way to create an array of strings is to use a two-dimensional array of characters</a>
  </li>
  <li>
    <a>Here is the syntax for creating an array of strings:</a>

```c
char arrayName[][] = {"str1", "str2", "str3"};
```
  </li>
</ul>    

## Programming Projects
<details>
    <summary>Write a program that finds the "smallest" and "largest" in a series of words. After the user enters the words, the program will determine which words would come first and last if the words were listed in dictionary order. The program must stop accepting input when the user enters a four-letter word. Assume that no word is more than 20 letters long. An interactive session with the program might look like this:<br />
    Enter word: <u>dog</u><br />
    Enter word: <u>zebra</u><br />
    Enter word: <u>rabbit</u><br />
    Enter word: <u>fish</u><br />
    Smallest word: dog<br />
    Largest word: rabbit<br />
    Use two strings named smallest and largest to keep track of the "smallest" and "largest" words entered so far. Each time the user enters a new word, use strcmp to compare it with the smallest string; if the new word is "smallest", use strcpy to to save it into smallest. Do a similar comparison with largest. Use strlen to determine when the user has entered a four-letter word</summary>

```c
#include <stdio.h>
#include <string.h>
//
//macro definition for the maximum number of characters within the user's string
#define MAX 20
//
int main()
{
    //variable declarations and initializations
    char smallest[MAX], largest[MAX], current[MAX];
    int iterations = 0;
    //
    //do-while loop which iterates until the user enters a four character string
    do
    {
        printf("Enter a word: ");
        scanf("%s", current);
        //
        //selection statement which checks if the loop is iterating for the first time
        if (iterations == 0)
        {
            strcpy(smallest, current);
            strcpy(largest, current);
        }
        //
        //selection statement which checks if the loop is iterating for the second time or later
        else
        {
            //selection statement which checks if the current string is less than the smallest string
            if (strcmp(current, smallest) < 0)
                strcpy(smallest, current);
            //
            //selection statement which checks if the current string is greater than the largest string
            if (strcmp(current, largest) > 0)
                strcpy(largest, current);
        }
        //
        iterations++;      
    } while (strlen(current) != 4);
    //
    //printing the smallest and largest strings to the screen
    printf("Smallest word: %s", smallest);
    printf("\nLargest word: %s", largest);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a word: <u>tiger</u>
Enter a word: <u>zebra</u>
Enter a word: <u>cat</u>
Enter a word: <u>dog</u>
Enter a word: <u>goat</u>
Smallest word: cat
Largest word: zebra
        </code>
        </pre>  
      </details>
    </ul>  
  </details>  
<details>
    <summary>Write a program that echoes its command-line arguments in reverse order. An interactive session with the program might look like this:<br />
    reverse <u>void and null</u><br />
    null and void</summary>

```c
#include <stdio.h>
#include <string.h>
//
//macro definition which defines the maximum number of characters within the user's string
#define MAX 1000
//
int main()
{
    //variable declarations and initializations
    char string[MAX], message[MAX][MAX], priorChar;
    int wordCount = 0;
    //
    printf("reverse ");
    fgets(string, MAX, stdin);
    //
    //for loop which iterates over all elements of the user's string and stores the elements into a two-dimensional character array
    for (int i = 0, j = 0; string[i] != '\0'; i++)
    {
        //selection statement which checks if the element of the string at index i is a white-space or a new-line character
        if (string[i] == ' ' || string[i] == '\n')
            j = 0;
        //selection statement which checks if string element at index i is the beginning of a new word    
        else if (string[i - 1] == ' ' && string[i] != ' ' && i > 0)
            message[++wordCount][j++] = string[i];    
        else
            message[wordCount][j++] = string[i];
    }
    //
    //nested for loop which iterates over all elements of the user's message and prints it to the screen
    for (int i = wordCount; i >= 0; printf(" "), i--)
        for (int j = 0; j < MAX; j++)
            printf("%c", message[i][j]);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
reverse <u>Garrett Ellis 1 2 3</u> 
3 2 1 Ellis Garrett
        </code>
        </pre>  
      </details>
    </ul>  
  </details>    
<details>
    <summary>Write a program that accepts a date from the user in the form mm/dd/yyyy and then displays it in the form month dd, yyyy, where month is the name of the month:<br />
    Enter a date (mm/dd/yyyy): <u>2/17/2011</u><br />
    You entered the date</summary>

```c
#include <stdio.h>
#include <string.h>
//
//macro definition which defines the maximum number of characters within the user's string
#define MAX 1000
//
int main()
{
    //variable declarations and initializations
    char string[MAX], message[MAX][MAX], priorChar;
    int wordCount = 0;
    //
    printf("reverse ");
    fgets(string, MAX, stdin);
    //
    //for loop which iterates over all elements of the user's string and stores the elements into a two-dimensional character array
    for (int i = 0, j = 0; string[i] != '\0'; i++)
    {
        //selection statement which checks if the element of the string at index i is a white-space or a new-line character
        if (string[i] == ' ' || string[i] == '\n')
            j = 0;
        //selection statement which checks if string element at index i is the beginning of a new word    
        else if (string[i - 1] == ' ' && string[i] != ' ' && i > 0)
            message[++wordCount][j++] = string[i];    
        else
            message[wordCount][j++] = string[i];
    }
    //
    //nested for loop which iterates over all elements of the user's message and prints it to the screen
    for (int i = wordCount; i >= 0; printf(" "), i--)
        for (int j = 0; j < MAX; j++)
            printf("%c", message[i][j]);
    //
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>

        </code>
        </pre>  
      </details>
    </ul>  
  </details>    
