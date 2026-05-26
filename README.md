# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
## 5. Implementation of one-dimensional array and multidimensional array.
## 6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.
# Date : 12/05/2026
# Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.
### Step 4: 
  Read the decimal number from the user.
### Step 5: 
  Initialize i = 0.
### Step 6: 
  Repeat while num > 0:
  Divide num by 2 and store the remainder in binary[i].
  Increment i.
  Update num = num / 2.
### Step 7: 
  Display the binary digits in reverse order (from i-1 down to 0).
### Step 8: 
   Stop
# Program:
```
#include <stdio.h>

int main() { int num, binary[32], i = 0;

scanf("%d", &num);

if (num == 0) {
    printf("Binary equivalent: 0");
    return 0;
}
while (num > 0) {
    binary[i] = num % 2;
    num = num / 2;
    i++;
}
printf("Binary equivalent: ");
for (int j = i - 1; j >= 0; j--) {
    printf("%d", binary[j]);
}

return 0;
}
```
# Output:
<img width="1050" height="526" alt="{1A1C4F3A-4CA5-467B-9A57-180F67799A5B}" src="https://github.com/user-attachments/assets/6113b571-298a-4afa-ae02-fa0fcf638772" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.
# Date : 12/05/2026
# Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
 Declare variables i, j, k, m, min, max and a position array pos[2][2].
### Step 4: 
 Read the order of the square matrix m.
### Step 5: 
 Declare an m × m matrix and read its elements.
### Step 6: 
 Display the matrix.
### Step 7: 
   For each row `i` from `0` to `m−1`:
- **Step 7.1:** Set `min` as the first element of the row.  
- **Step 7.2:** Scan the row to find its minimum element and store its position in `pos[0]`.  
- **Step 7.3:** Let `j` be the column of this minimum element.  
- **Step 7.4:** Set `max` as the first element of column `j`.  
- **Step 7.5:** Scan column `j` to find its maximum element and store its position in `pos[1]`.  
### Step 8: 
  Check if the row minimum equals the column maximum:
- If `min == max` **and their positions match**, then the element is a **saddle point**.
- Print the saddle point value and its position.
### Step 9: 
  Stop
# Program:
```
#include <stdio.h>

#define MAX_ROWS 10
#define MAX_COLS 10

int main() {
    int matrix[MAX_ROWS][MAX_COLS];
    int rows, cols, i, j, k;
    int row_min, col_idx;
    int found = 0;
    printf("Enter the number of rows (max %d): ", MAX_ROWS);
    scanf("%d", &rows);
    printf("Enter the number of columns (max %d): ", MAX_COLS);
    scanf("%d", &cols);
    if (rows > MAX_ROWS || cols > MAX_COLS || rows <= 0 || cols <= 0) {
        printf("Invalid matrix dimensions.\n");
        return 1;
    }
    printf("Enter matrix elements:\n");
    for (i = 0; i < rows; i++) {
        for (j = 0; j < cols; j++) {
            printf("Matrix[%d][%d]: ", i, j);
            scanf("%d", &matrix[i][j]);
        }
    }
    for (i = 0; i < rows; i++) {
        row_min = matrix[i][0];
        col_idx = 0;
        for (j = 1; j < cols; j++) {
            if (matrix[i][j] < row_min) {
                row_min = matrix[i][j];
                col_idx = j;
            }
        }
        int is_saddle = 1;
        for (k = 0; k < rows; k++) {
            if (matrix[k][col_idx] > row_min) {
                is_saddle = 0;
                break; // Not the maximum in its column
            }
        }
        if (is_saddle) {
            printf("\nSaddle point found: %d at position (%d, %d)\n", row_min, i + 1, col_idx + 1);
            found = 1;
        }
    }
    if (!found) {
        printf("\nNo saddle point exists in the matrix.\n");
    }
    return 0;
}
```
# Output:
<img width="1047" height="444" alt="image" src="https://github.com/user-attachments/assets/1b12d9fd-490c-4eed-9b9e-68d4801679c2" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.
# Date : 12/05/2026
# Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare two character arrays: `s` to store the input string and `d` to store the reversed string.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]s", s);`
### Step 5: 
  Find the length of the string `s` by traversing it until the null character `'\0'` is encountered.
### Step 6: 
  Initialize a counter `j` for the reversed string.
### Step 7: 
  Copy characters from the end of `s` to the beginning of `d` using a loop until all characters are copied in reverse order.
### Step 8: 
  Terminate the reversed string `d` with the null character `'\0'`.
### Step 9: 
  Print the reversed string.
### Step 10: 
  Stop
# Program:
```
#include <stdio.h> #include <string.h>
int main() { char str[100]; int i, len;
printf("Enter a string: ");
gets(str);  
len = strlen(str);
printf("Reversed string: ");
for (i = len - 1; i >= 0; i--) {
    printf("%c", str[i]);
}
return 0;
}
```
# Output:
<img width="1049" height="238" alt="image" src="https://github.com/user-attachments/assets/84a11ae2-29bf-4d3d-bb27-248b0d976b15" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.
# Date : 12/04/2026
# Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `s[100]` to store the input string, an integer array `visited[256]` initialized to `0`, and variables `i`, `n`, and `count`.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]", s);`
### Step 5: 
  Calculate the length of the string using `strlen(s)` and store it in `n`.
### Step 6: 
 For each character `s[i]` in the string (from `i = 0` to `n - 1`):
 - If `visited[(unsigned char)s[i]] == 0` (character not yet counted):  
  - Initialize `count = 0`.  
  - Loop through the string again and increment `count` for every occurrence of `s[i]`.  
  - Print `s[i]` and its count.  
  - Set `visited[(unsigned char)s[i]] = 1` to mark it as counted.
### Step 7: 
  Repeat Step 6 for all characters.
### Step 8:
  Stop
# Program:
```
#include <stdio.h>
int main() { char str[100]; int freq[256] = {0}; // ASCII characters int i;

printf("Enter a string: ");
fgets(str, sizeof(str), stdin);
for (i = 0; str[i] != '\0'; i++) {
    freq[(unsigned char)str[i]]++;
}
printf("\nCharacter frequencies:\n");
for (i = 0; i < 256; i++) {
    if (freq[i] > 0 && i != '\n') {
        printf("'%c' : %d\n", i, freq[i]);
    }
}
return 0;
}
```
# Output:
<img width="1044" height="510" alt="{3717159B-D28D-4261-BE3D-65C7F0393DC0}" src="https://github.com/user-attachments/assets/3a9c2234-22ad-4f9b-b06d-be8d604a25c7" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Date : 12/05/2026
# Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `str` to store the input string and a 2D array `words` to store individual words.
### Step 4: 
  Read the input string using `scanf("%[^\n]s", str);`
### Step 5: 
 Split the string into words:
 - Traverse the string character by character.  
 - When a space is encountered, terminate the current word with `'\0'` and move to the next row in `words`.  
 - Otherwise, copy the character into the current word.
### Step 6: 
  Compare each word with all other words to detect duplicates:
  - If a duplicate is found, mark it by setting the first character to `'\0'`.
### Step 7: 
  Print all words that are not marked as duplicates.
### Step 8: 
  Stop
# Program:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

void convertUpper(char str[]) {
    int i;
    if (str[0] != '\0' && str[0] != '\n')
        str[0] = toupper(str[0]);

    for (i = 1; str[i] != '\0'; i++) {
        if (str[i] == ' ') {
            if (i - 1 >= 0)
                str[i - 1] = toupper(str[i - 1]);

            if (str[i + 1] != '\0' && str[i + 1] != '\n')
                str[i + 1] = toupper(str[i + 1]);
        }
    }
    int len = strlen(str);
    if (len > 0) {
        if (str[len - 1] == '\n' && len > 1)
            str[len - 2] = toupper(str[len - 2]);
        else
            str[len - 1] = toupper(str[len - 1]);
    }
}
int main() {
    char str[200];

    printf("Enter a string:\n");
    fgets(str, sizeof(str), stdin);

    convertUpper(str);

    printf("\nConverted string:\n%s", str);

    return 0;
}
```
# Output:
<img width="1047" height="469" alt="{8FFC4DE8-F749-4C81-A8D7-934C2CE7E5D4}" src="https://github.com/user-attachments/assets/0c0e155a-4d6e-42d0-a6d8-31ebeb021424" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

