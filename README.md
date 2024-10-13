# EX4 - Vigenere Cipher
## AIM:
To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:
### Step 1:
Design of Vigenere Cipher algorithnm

### Step 2:
Implementation using C or pyhton code

### Step 3:
Testing algorithm with different key values.

## ALGORITHM DESCRIPTION: 
The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a repeating keyword.

## PROGRAM:
```
#include <stdio.h>
#include <stdlib.h>  
#include <ctype.h>  
#include <string.h>  
void encipher();
void decipher();
int main() 
{
    int choice;
    while (1) 
    {
        printf("\n1. Encrypt Text");
        printf("\n2. Decrypt Text");
        printf("\n3. Exit");
        printf("\n\nEnter Your Choice: ");
        scanf("%d", &choice);
        if (choice == 3)
            exit(0);
        else if (choice == 1)
            encipher();
        else if (choice == 2)
            decipher();
        else
            printf("Please Enter a Valid Option.\n");
    }
    return 0; 
}
void encipher() 
{
    unsigned int i, j;
    char input[50], key[10];
    printf("\n\nEnter Plain Text: ");
    scanf("%s", input); 
    printf("Enter Key Value: ");
    scanf("%s", key);
    printf("Resultant Cipher Text: ");
    for (i = 0, j = 0; i < strlen(input); i++, j++) 
    {
        if (j >= strlen(key)) 
        {
            j = 0;
        }
        printf("%c", 65 + (((toupper(input[i]) - 65) + (toupper(key[j]) - 65)) % 26));
    }
    printf("\n");
}
void decipher() 
{
    unsigned int i, j;
    char input[50], key[10];
    int value;
    printf("\n\nEnter Cipher Text: ");
    scanf("%s", input); 
    printf("Enter the Key Value: ");
    scanf("%s", key);
    printf("Resultant Plain Text: ");
    for (i = 0, j = 0; i < strlen(input); i++, j++) 
    {
        if (j >= strlen(key)) 
        {
            j = 0;
        }
        value = (toupper(input[i]) - 65) - (toupper(key[j]) - 65);
        if (value < 0) 
        {
            value += 26;  
        }
        printf("%c", 65 + (value % 26));
    }
    printf("\n"); 
}
```

## OUTPUT:

![image](https://github.com/user-attachments/assets/6937de7e-e313-4464-ba9b-fb3079acae81)

![image](https://github.com/user-attachments/assets/c52c6e42-dd00-4f29-8022-df21242ba61b)

![image](https://github.com/user-attachments/assets/0536d5eb-3cda-4efc-8ddd-9585e1dc5dd2)



## RESULT:
The program is executed successfully.
