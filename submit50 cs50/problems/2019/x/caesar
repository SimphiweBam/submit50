#include <ctype.h>
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <cs50.h>

int main(int argc, string argv[])
{
    // Check if argc = 2
    if (argc != 2)
    {
        printf("Usage: ./caesar key\n");
        printf("1");
        return (1);
    }    
    else if (argc == 2)
    {
        // Check key for validity
        // First convert index 1 of argv into int. Use atoi in stdlib.h to return int from string
        const int KEY = atoi(argv[1]);
        // Store a boolean to use as off switch
        bool isKeyValid = true;
        // Store length of key
        int len = strlen(argv[1]);
        
        // Loop to check if each digit is a number
        for (int i = 0; i < len; i++)
        {
            // if is digit (in ctype.h) detects a non-digit set bool to false and end loop
            if (isdigit(argv[1][i]) == false)
            {
                isKeyValid = false;
                i = len;
            }
        }
        if (isKeyValid)
        {
            string plain = get_string("plaintext: ");
            
            int plainLength = strlen(plain);
            
            for (int i = 0; i < plainLength; i++)
            {
                // Check if uppercase or lowercase, with ctype.h
                if (isupper(plain[i]))
                {
                    // 'Z' - 'A'
                    if (plain[i] + KEY > 'Z')
                    {
                        int keyRemainder = (plain[i] + KEY) - 'Z';
                        
                        if (keyRemainder > 'Z' - 'A')
                        {
                            while (keyRemainder >= ('Z' - 'A'))
                            {
                                keyRemainder = keyRemainder - (26);
                            }
                            
                            if (plain[i] + keyRemainder > 'Z')
                            {
                                keyRemainder = plain[i] + keyRemainder - 'Z';
                                
                                plain[i] = 'A' + keyRemainder - 1;
                            }
                            // If keyRemainder is managable number, add to 'a' to shift to encrypted form
                            else
                            {
                                plain[1] = 'A' + keyRemainder - 1;
                            }
                        }
                        // if letter from plain[i] + keyRemainder is not greater than Z
                        else
                        {
                            plain[i] = 'A' + keyRemainder - 1;
                        }
                    }
                    // Simple case, focus letter added to given key to produce encrypted letter
                    else if (plain[i] + KEY <= 'Z')
                    {
                       plain[i] = plain[i] + KEY;
                    }
                }
                if (islower(plain[i]))
                {
                    
                    // 'z' - 'a'
                    if (plain[i] + KEY > 'z')
                    {
                        int keyRemainder = (plain[i] + KEY) - 'z';
                        
                        if (keyRemainder > 'z' - 'a')
                        {
                            while (keyRemainder >= ('z' - 'a'))
                            {
                                keyRemainder = keyRemainder - (26);
                            }
                            
                            if (plain[i] + keyRemainder > 'z')
                            {
                                keyRemainder = plain[i] + keyRemainder - 'z';
                                
                                plain[i] = 'a' + keyRemainder - 1;
                            }
                            // If keyRemainder is managable number, add to 'a' to shift to encrypted form
                            else
                            {
                                plain[1] = 'a' + keyRemainder - 1;
                            }
                        }
                        // if letter from plain[i] + keyRemainder is not greater than z
                        else
                        {
                            plain[i] = 'a' + keyRemainder - 1;
                        }
                    }
                    // Simple case, focus letter added to given key to produce encrypted letter
                    else if (plain[i] + KEY <= 'z')
                    {
                       plain[i] = plain[i] + KEY;
                    }
                }
            }
            
            printf("ciphertext: %s\n", plain);
        }
        else
        {
            printf("Usage: ./caesar key\n");
        }
    }
}

