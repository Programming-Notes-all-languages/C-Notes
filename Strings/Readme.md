<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#string-literals'>String Literals</a>
  </li> 
  <li>
    <a href='#string-variables'>String Variables</a>
  </li> 
  <li>
    <a href='#reading-and-writing-strings'>Reading and Writing Strings</a>
  </li> 
  <li>
    <a href='#accessing-the-characters-in-a-string'>Accessing the Characters in a Strings</a>
  </li> 
  <li>
    <a href='#command-line-arguments'>Command Line Arguments</a>
  </li> 
  <li>
    <a href='#programming-projects'>Programming Projects</a>
  </li> 
</ol>
</details>

## String Literals
<ul>
  <li>
    <a><em>String literals</em> are a sequence a characters that are declared such as the following that are enclosed within double quotes: char *string = "Garrett";</a>
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
  <li>
    <a>char *string = "Garrett"; cannot be modified whereas char string[] = "Garrett"; can be modified</a>
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

int main()
{
    //variable declarations and initialization
    char str[] = "Garrett is amazing!";
    
    printf("%s\n", str);
    
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

int main()
{
    //variable declarations and initialization
    char str[] = "Garrett is amazing!";
    
    printf("%.7s\n", str);
    
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
  </li>
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
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>
//What is the return value of f("cabd", "acad")?

//function prototype for f
int f(char *s, char *t)
{
    //variable declarations
    char *p1, *p2;
    
    //nested for loops
    for(p1 = s; *p1 != '\0'; p1++) {
        for(p2 = t; *p2 != '\0'; p2++)
            if (*p1 == *p2) break;
        if(*p2 == '\0') break;
    }
    
    return p1 – s;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
2
        </code>
      </pre>  
    </details>
  </ul>
  </details> 
  <details>
    <summary>Example program</summary>

```c
//What does the following read_lines function do, assuming that n is larger than the size of the input string?

int read_line(char *str, int n)
{
    int ch, i = 0;

    while ((ch = getchar()) == ' ');
    *str++ = ch;
    i++;

    while ((ch = getchar()) != '\n') {
        if (i < n) {
            *str++ = ch;
            i++;
        }    
    }
    *str = '\0';
    return i;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
This function appends on to an existing string. It will first skip over all white spaces. Once a non-white space character is entered by the user, it will continue to store the remainder of characters to the string. Once the user enters a new-line character, the while loop terminates and the null character is appended to the end of the string. No spaces are added between the existing string and the new characters within the char array
        </code>
      </pre>  
    </details>
  </ul>
  </details> 
  <details>
    <summary>Example program</summary>

```c
#include <stdio.h>

void change(char *s) {
    while (*s) {
        *s = (*s == 'a') ? 'x' : *s;
        s++;
    }
}

int main() {
    char str[] = "banana";

    change(str);
    printf("%s\n", str);

    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
bxnxnx
        </code>
      </pre>  
    </details>
  </ul>
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Complete the function is_all_uppercase so that it checks if all letters in an input string str are uppercase letters. The string str is composed of letters only. It must return 1 if all letters in str are uppercase, and 0 otherwise

int is_all_uppercase(char str[]) {
    int flag = 1;

    return flag;
}  
```
<ul>  
  <details>
    <summary>Output</summary>

```c
int is_all_uppercase(char str[]) {
    int flag = 1;

    for (char *ptr = str; *ptr != '\0'; ptr++)
        if (*ptr >= 'a' && *ptr <= 'z')
            flag = 0;

    return flag;
}  
```
  </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Write the function that shifts a message. The function expects message to point to a string containing the message to be shifted; shift represents the amount by which each letter in the message to be shifted. Lower-case letters remain lower-case when shifted, and upper-case remain upper-case

void shift(char *message, int shift) {
    
} 
```
<ul>  
  <details>
    <summary>Output</summary>

```c
void shift(char *message, int shift) {
    for (; shift >= 26;)
        shift -= 26;
        
    for (; *message != '\0'; message++) {
        if (*message >= 'a' && *message <= 'z') {
            *message += shift;
            if (*message > 'z')
                *message = 'a' + (*message - 'z' - 1);
        }        

        else if (*message >= 'A' && *message <= 'Z') {
            *message += shift;
            if (*message > 'Z')
                *message = 'A' + (*message - 'Z' - 1);
        }        
    }    
}
```
  </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Complete the following function that replaces every occurrence of a character x with another character y in a given string, without using the standard library function

void replace_char(char *, char, char) {
    
} 
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>

void replace_char(char *, char, char);

int main()
{
    char string[] = "Garrett";

    replace_char(string, 'r', 's');

    printf("%s", string);

    return 0;
}

void replace_char(char *str, char x, char y) {
    for (char *ptr = str; *ptr != '\0'; ptr++)
        if (*ptr == x)
            *ptr = y;
}
```
  </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Write a function reverse_string that reverses a given string in place

void reverse(char *str) {

}
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>

void r(char *str) {
    int characters = 0;

    for (char *ptr = str; *ptr != '\0'; ptr++)
        characters++;

    for (char *ptr = str, *ptrE = str + characters - 1; ptr < ptrE; ptr++, ptrE--) {
        char temp = *ptr;
        *ptr = *ptrE;
        *ptrE = temp;
    }    
}

int main()
{
    char string[100] = "Garrett";

    r(string);

    printf("%s", string);

    return 0;
}
```
  </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Write a function is_palindrome to check if a string is palindrome

int is_palindrome(const char *str) {

}
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>
#include <string.h>

int is_palindrome(char *str) {
    int strLength = strlen(str);
    int flag = 1;

    for (char *ptr = str, *ptrEnd = str + strLength - 1; ptr < ptrEnd; ptr++, ptrEnd--)
        if (*ptr != *ptrEnd)
            flag = 0;

    return flag;        
}

int main()
{
    char string[100] = "GaGaG";
    int flag = is_palindrome(string);

    (flag == 1) ? (printf("%s is a palindrome\n", string)) : (printf("%s is not a palindrome\n", string));

    return 0;
}
```
  </details>
  </ul>  
  </details> 
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
  <details>
    <summary>Example program</summary>

```c
//Complete the program below so it calls the swap function and prints the words in the array w in alphabetical order

#include <stdio.h>

void swap(char *a, char *b)
{
    char tmp[4];
    strcpy(tmp, a);
    strcpy(a, b);
    strcpy(b, tmp);
}

int main()
{
    char w[3][4] = {"dog", "rat", "cat"};


    for (int i = 0; i < 3; i++)
        printf("%s\n", w[i]);

    return 0;    
}
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>
#include <string.h>

void swap(char *a, char *b)
{
    char tmp[4];
    strcpy(tmp, a);
    strcpy(a, b);
    strcpy(b, tmp);
}

int main()
{
    char w[3][4] = {"dog", "rat", "cat"};

    for (int i = 0; i < 3; i++)
        for (int j = i; j < 3; j++)
            if (strcmp(w[i], w[j]) > 0)
                swap(w[i], w[j]);

    for (int i = 0; i < 3; i++)
        printf("%s\n", w[i]);

    return 0;    
}
```
  </details>
  </ul>
  </details> 
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
  <details>
    <summary>Example program</summary>

```c
//Write a program that finds the length of the longest word in an array of strings such as the following: char w[5][20] = {"apple", "banana", "kiwi", "grape", "mango"};
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>
#include <string.h>

int main()
{
    //variable declarations and initialization
    char w[5][20] = {"apple", "banana", "kiwi", "grape", "mango"};
    int longest = strlen(w[4]);

    //for loop which iterates through the array of strings and compares the length of each string to the length of the longest string thus far
    for (int i = 0; i < 5; i++)
        if (strlen(w[i]) > longest)
            longest = strlen(w[i]);

    printf("The longest word in the array is %d characters long", longest);        
}
```
  </details>
  </ul>
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Complete the following program to sort an array of strings by their lengths in ascending order. Usee strlen to compare lengths

#include <stdio.h>
#include <string.h>

void swap(char *a, char *b) {
    // Implement the swap logic
}

int main() {
    char w[5][20] = {"banana", "apple", "kiwi", "grapefruit", "mango"};
    // Sort the words by their lengths here
    // Print the sorted words here

    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>
#include <string.h>

void swap(char *a, char *b) {
    char temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    char w[5][20] = {"banana", "apple", "kiwi", "grapefruit", "mango"};
    
    for (int i = 0; i < 5; i++)
        for (int j = i; j < 5; j++)
            if (strlen(w[i] < strlen(w[j])))

    return 0;
}
```
  </details>
  </ul>
  </details> 
</ul>    

### The strcat (String Concatenation) Function
<ul>
  <li>
    <a>The strcat function appends one string onto another. The strcat function takes in two arguments: the first argument is the string that will have more characters appended to it and the second argument is the string that will be appended to the first string</a>
  </li>
  <li>
    <a>The strcat function modifies only the first argument that is passed to its function call. The second argument that is passed to strcat is not modified by the strcat function</a>
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
    <ul>
      <li>
        <a>The strcmp function returns a value of type integer</a>
        <ul>
          <li>
            <a>If the function returns zero, then both functions have the exact same string</a>
          </li>
          <li>
            <a>If the function returns a negative integer, then the first string has a lower ascii value at an index closer index zero. For instance, if strcmp("ab", "aa") where to be written, it would return a value less than one since the second string has a lower ascii value for its second character compared to the first string</a>
          </li>
          <li>
            <a>if the function returns a positive integer, then the second strings has a lower ascii value at an index closer to index zero</a>
          </li>
        </ul>
      </li>
    </ul>        
  </li> 
  <li>
    <a>Here is the syntax for strcmp:</a>

```c
if (strcmp(str1, str2) == 0)
```
  </li>
  <details>
    <summary>Example program</summary>

```c
//What will be the value of string s2 after the following statements have been executed?
strcpy(s1, "Program");
strcpy(s2, "Design");
if strcmp(s1, s2) < 0
    strcat(s1, s2);
else
    strcat(s2, s1);
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
"DesignProgram"
        </code>
      </pre>  
    </details>
  </ul>  
  </details> 
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

## Command Line arguments
<ul>
  <li>
    <a>Programs written in C can accept command line arguments. To do so, the main function of the C file needs to contain these two arguments: int argc and char *argv[]</a>
  </li>
  <li>
    <a>Here is the syntax for this type of main function:</a>

```c
int main(int argc, char *argv[])
{
    return 0;
} 
```
  <ul>
      <li>
        <a>The first argument, argc, defines the total number of command line arguments given, including the name of the program itself</a>
      </li>
      <li>
        <a>The second argument, *argv[], is a string of pointers where each index of the pointer array stores a character array, a string, beginning with the name of the program itself</a>
      </li>
    </ul>    
  </li>    
  <details>
    <summary>Example program</summary>

```c
//Write a program which will echo its command-line argument in reverse order. Running the program by typing, ./a.out today and tomorrow, should produce the following output: tomorrow and today
```
<ul>  
  <details>
    <summary>Output</summary>
      
```c
#include <stdio.h>

int main(int argc, char *argv[])
{
    //variable declaration and initialization
    char **ptr = argv + --argc;

    //iterating through argv until the first argument in argv is encountered
    for (; argc > 0; argc--, ptr--)
        printf("%s ", *ptr);

    return 0;    
}
```
  </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Write a program where the user provides command line-arguments and the program will check if the user's arguments are palindromic. For instance, the command-line ./a.out 1 20 5 20 1 has palindromic arguments, but the command-line ./a.out 1 20 5 20 2 does not have palindromic arguments
```
<ul>  
  <details>
    <summary>Output</summary>  

```c
#include <stdio.h>
#include <string.h>
#include <stdbool.h>

int main(int argc, char *argv[])
{
    char **beginPtr = argv + 1, **endPtr = argv + --argc;
    bool flag = true;

    for (; beginPtr < endPtr; beginPtr++, endPtr--)
        if (strcmp(*beginPtr, *endPtr) != 0)
            flag = false;

    if (flag) 
        (printf("YES\n"));
    else
        (printf("NO\n"));

    return 0;             
}
```
  </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//What is the output of the following program assuming the program is called with ./a.out apple
#include <stdio.h>

int main(int argc, char *argv[]) {
    char *arg = *(argv + 1);         //arg now stores the memory address of argv[1]

    printf("%c ", arg[1]);           //[] operator dereferences arg and we are accessing the second string within the character array which is apple
    printf("%c\n", argv[1][2]);      //[][] operators dereference arg and dereferences the string within index 1, accessing the third character

    return 0;
}
```
<ul>  
  <details>
    <summary>Output</summary>
      <pre>
        <code>
a p
        </code>
      </pre>    
    </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Write a program that takes a series of strings as command-line arguments, reverses each string, and concatenates them into a single string. The output should be printed as a single line. For example, if the command is ./program_name hello world, the output should be olleh dlrow.
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>
#include <string.h>

#define MAX 100

int main(int argc, char *argv[])
{
    char **ptr = argv + 1, finalString[MAX] = {'\0'}, *finalStringPtr = finalString;

    for (; ptr < argv + argc; ptr++, *finalStringPtr++ = ' ')
    {
        for (char *charPtr = *ptr + strlen(*ptr) - 1; charPtr >= *ptr; charPtr--)
            *finalStringPtr++ = *charPtr;

        if (ptr + 1 == argv + argc)
            break;    
    }        

    printf("%s\n", finalString);

    return 0;
}    
```
  </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Write a function that removes all vowels (both uppercase and lowercase) from a given string. Use only pointer manipulation--no indexing with [] or standard library functions.

void remove_vowels(char *str) {
    
}
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>

void remove_vowels(char *);

int main(int argc, char *argv[])
{
    for (char **ptr = argv + 1; ptr < argv + argc; ptr++) {
        remove_vowels(*ptr);
        printf("%s ", *ptr);
    }    

    return 0;
}

void remove_vowels(char *str) {
    for (char *ptr = str, *ptr2 = str; *ptr != '\0'; ptr++, ptr2 = ptr) 
        if (*ptr == 'a' || *ptr == 'e' || *ptr == 'i' || *ptr == 'o' || *ptr == 'u' || *ptr == 'A' || *ptr == 'E' || *ptr == 'I' || *ptr == 'O' || *ptr == 'U') {
            for (; *ptr2 != '\0'; ptr2++)
                *ptr2 = *(ptr2 + 1); 
            ptr--;    
        }              
}       
```
  </details>
  </ul>  
  </details> 
  <details>
    <summary>Example program</summary>

```c
//Write a function that extracts the file extension from a given file name. If no extension exists, store an empty string in extension. Complete the following function:

void extract_extension(char *filename, char *extension) {
  
}
```
<ul>  
  <details>
    <summary>Output</summary>

```c
#include <stdio.h>

#define MAX_LENGTH 100

void extract_extension(char *, char *);

int main(int argc, char *argv[])
{
    char **ptr = argv + 1, extension[MAX_LENGTH] = {'\0'};

    extract_extension(*ptr, extension); 

    printf("Extension: %s\n", extension);

    return 0;
}

void extract_extension(char *filename, char *extension) {
    for (char *ptr = filename; *ptr != '\0'; ptr++)
        if (*ptr == '.') {
            ptr++;
            for (char *ptrExten = extension; *ptr != '\0'; ptrExten++, ptr++)
                *ptrExten = *ptr;
        }        
}   
```
  </details>
  </ul>  
  </details> 
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

//macro definition for the maximum number of characters within the user's string
#define MAX 20

int main()
{
    //variable declarations and initializations
    char smallest[MAX], largest[MAX], current[MAX];
    int iterations = 0;
    
    //do-while loop which iterates until the user enters a four character string
    do
    {
        printf("Enter a word: ");
        scanf("%s", current);
        
        //selection statement which checks if the loop is iterating for the first time
        if (iterations == 0)
        {
            strcpy(smallest, current);
            strcpy(largest, current);
        }
        
        //selection statement which checks if the loop is iterating for the second time or later
        else
        {
            //selection statement which checks if the current string is less than the smallest string
            if (strcmp(current, smallest) < 0)
                strcpy(smallest, current);
            
            //selection statement which checks if the current string is greater than the largest string
            if (strcmp(current, largest) > 0)
                strcpy(largest, current);
        }
        
        iterations++;      
    } while (strlen(current) != 4);
    
    //printing the smallest and largest strings to the screen
    printf("Smallest word: %s", smallest);
    printf("\nLargest word: %s", largest);
    
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

int main(int argc, char *argv[])
{
    //for loop which iterates through argv until the first argument in argv is encountered
    for (char **ptr = argv + --argc; ptr > argv; ptr--)
        printf("%s ", *ptr);
    
    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
./a.exe <u>Garrett Ellis 1 2 3</u> 
3 2 1 Ellis Garrett
        </code>
        </pre>  
      </details>
    </ul>  
  </details>    
<details>
    <summary>Write a program that accepts a date from the user in the form mm/dd/yyyy and then displays it in the form month dd, yyyy, where month is the name of the month:<br />
    Enter a date (mm/dd/yyyy): <u>2/17/2011</u><br />
    You entered the date: February 17, 2011</summary>

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

//macro definition for the maximum number of characters within the user's string
#define MAX 100

int main()
{
    //variable declarations and initializations
    char string[MAX], *ptr = string, temp[MAX], *tempPtr = temp;
    int month, day, year;

    //getting date input from the user and storing it in a string
    printf("Enter a date (mm/dd/yyyy): ");
    scanf("%s", string);
    
    //for loop which iterates through the string and stores the month, day, and year in their respective variables while also converting the string to an integer and storing it in a temporary string
    for (int numBackslash = 0; *ptr != '\0'; ptr++)
    {
        //selection statement which checks if the character is not a backslash and stores it in the temporary string
        if (*ptr != '/')
            *tempPtr++ = *ptr;

        //selection statement which checks if the character is a backslash and stores the temporary string in the month, day, or year variable depending on the value of numBackslash and then resets the temporary
        if (numBackslash == 0 && *ptr == '/')
            month = atoi(temp);
        else if (numBackslash == 1 && *ptr == '/')
            day = atoi(temp);
        else if (numBackslash == 2 && *(ptr + 1) == '\0')
            year = atoi(temp);

        //selection statement which checks if the character is a backslash and increments the numBackslash variable, resets the temporary string, and resets the temporary pointer
        if (*ptr == '/')      
        {
            numBackslash++;
            tempPtr = temp;
            strcpy(temp, "");
        }
    }

    printf("You entered the date: ");

    //selection statement which checks the value of the month variable and prints the corresponding month to the screen`
    if (month == 1)
        printf("January ");
    else if (month == 2)
        printf("February ");
    else if (month == 3)
        printf("March ");
    else if (month == 4)
        printf("April ");
    else if (month == 5)
        printf("May ");
    else if (month == 6)
        printf("June ");
    else if (month == 7)    
        printf("July ");
    else if (month == 8)
        printf("August ");
    else if (month == 9)
        printf("September ");
    else if (month == 10)
        printf("October ");
    else if (month == 11)
        printf("November ");
    else if (month == 12)
        printf("December ");    

    printf("%d, %d\n", day, year);

    return 0;
}
```
<ul>
  <details>
    <summary>Output</summary>
      <pre>
        <code>
Enter a date (mm/dd/yyyy): <u>03/11/2003</u>
You entered the date: March 11, 2003
        </code>
        </pre>  
      </details>
    </ul>  
  </details>    
