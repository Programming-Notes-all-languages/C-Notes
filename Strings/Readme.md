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
