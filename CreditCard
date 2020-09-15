#include <stdio.h>
#include <cs50.h>
#include <stdlib.h>

int main(void)
{
    long n = get_long("Number: ");
    long t = n;
    int s1 = 0, s2 = 0, l = 0, c;
    //Calculate sum1 and sum2
    while (n > 0)
    {
        //l denotes number of digits
        s1 += n % 10;
        n /= 10;
        l++;
        if (n == 0)
        {
            break;
        }
        c = 2 * (n % 10);
        while (c > 0)
        {
            s2 += c % 10;
            c /= 10;
        }
        n /= 10;
        l++;
    }
    //Use Luhn's Algorithm
    int sum = s1 + s2;
    //Check validity
    if (sum % 10 != 0)
    {
        printf("INVALID\n");
    }

    //Check card type if valid
    else
    {
        //Get first 2 numbers
        for (int i = l; i > 2; i--)
        {
            t /= 10;
        }
        //Finalize card type
        if (l == 15 && (t == 34 || t == 37))
        {
            printf("AMEX\n");
        }
        else if (l == 16 && (t > 50 && t < 56))
        {
            printf("MASTERCARD\n");
        }
        else if ((l == 13 || l == 16) && (t / 10) == 4)
        {
            printf("VISA\n");
        }
        else
        {
            printf("INVALID\n");
        }
    }
}
