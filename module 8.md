EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    switch(n){
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    // Step 4: Exit the program
    return 0;
}
```


Output:


![8pg1](https://github.com/user-attachments/assets/5593f255-fd50-4c7f-b9aa-4429938c8d18)




Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>
int main() {
    int freq[10] = {0};  
    char ch;
    printf("Enter digits (end with non-digit character): ");
    while ((ch = getchar()) >= '0' && ch <= '9') {
        int digit = ch - '0';
        if (digit >= 0 && digit <= 3) {
            freq[digit]++;
        }
    }
    for (int i = 0; i < 10; i++) {
        printf("%d ", i <= 3 ? freq[i] : 0);
    }
    printf("\n");
    return 0;
}
```



Output:

![8pg2](https://github.com/user-attachments/assets/1e306ad4-54f3-4df6-9d60-cbd747a29da4)



Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
void swap(char *a, char *b) {
    char temp = *a;
    *a = *b;
    *b = temp;
}
int cmpfunc(const void *a, const void *b) {
    return (*(char *)a - *(char *)b);
}
void reverse(char *str, int start, int end) {
    while (start < end) {
        swap(&str[start], &str[end]);
        start++;
        end--;
    }
}
int next_permutation(char *str, int len) {
    int i = len - 2;
    while (i >= 0 && str[i] >= str[i + 1])
        i--;
    if (i < 0)
        return 0;
    int j = len - 1;
    while (str[j] <= str[i])
        j--;
    swap(&str[i], &str[j]);
    reverse(str, i + 1, len - 1);
    return 1;
}
int main() {
    char str[100];
   printf("Enter a string: ");
    scanf("%s", str);
    int len = strlen(str);
    qsort(str, len, sizeof(char), cmpfunc);
    do {
        printf("%s\n", str);
    } while (next_permutation(str, len));

    return 0;
}
```


Output:

![8pg3](https://github.com/user-attachments/assets/82c22707-439c-47e6-8d97-a52d34fb6f18)





Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```
#include <stdio.h>
int main() {
    int n, i, j, num = 1;

    printf("Enter the value of N: ");
    scanf("%d", &n);

    for (i = 1; i <= n; i++) {
        for (j = 1; j <= i; j++) {
            printf("%d ", num++);
        }
        printf("\n");
    }

    return 0;
}
```


Output:

![8pg4](https://github.com/user-attachments/assets/ed429fe5-9fe6-4f45-9b9c-6d2d58a76fa9)





Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}
int main() {
    int result;
    result = square(); 
    printf("Square of the number is: %d\n", result);
    return 0;
}
```



Output:

![8pg5](https://github.com/user-attachments/assets/669b8886-0a37-4f03-be10-b8c76a4f9ced)





Result:
Thus, the program is verified successfully



























