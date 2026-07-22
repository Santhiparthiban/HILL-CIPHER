# HILL CIPHER
HILL CIPHER
EX. NO: 3  IMPLEMENTATION OF HILL CIPHER
## AIM:
 To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To decrypt the message, each block is multiplied by the inverse of the m trix used for encryption. The matrix used for encryption is the cipher key, and it should be chosen
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. 

STEP-2: Split the plain text into groups of length three. 

STEP-3: Arrange the keyword in a 3*3 matrix.

STEP-4: Multiply the two matrices to obtain the cipher text of length three.

STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```
Developed by: SANTHI.P
Register number: 212225040377
```
```
#include <stdio.h>
#include <string.h>

int main()
{
    int key[3][3], plain[3], cipher[3];
    char text[100];
    int i, j;

    printf("Enter the 3x3 key matrix (9 integers):\n");
    for(i = 0; i < 3; i++)
        for(j = 0; j < 3; j++)
            scanf("%d", &key[i][j]);

    printf("Enter plaintext (3 letters): ");
    scanf("%s", text);

    // Convert plaintext to numbers (A=0, B=1, ..., Z=25)
    for(i = 0; i < 3; i++)
        plain[i] = text[i] - 'A';

    // Encryption
    for(i = 0; i < 3; i++)
    {
        cipher[i] = 0;
        for(j = 0; j < 3; j++)
            cipher[i] += key[i][j] * plain[j];

        cipher[i] = cipher[i] % 26;
    }

    printf("Cipher Text: ");
    for(i = 0; i < 3; i++)
        printf("%c", cipher[i] + 'A');

    printf("\n");

    return 0;
}
```
## OUTPUT

<img width="1650" height="776" alt="Screenshot 2026-07-22 113327" src="https://github.com/user-attachments/assets/ffaad4dd-00f0-4aa2-9f0e-b8a700ec79f5" />


## RESULT
The C program to implement the hill cipher substitution techniques is successfully executed
