```c
#include <stdio.h>

int main(void)
{
    for (int i = 1; i <= 10; i++)
    {
        for (int j = 1; j <= i; j++)
            printf("#");
        for (int j = i; j <= 10; j++)
            printf(" ");

        for (int j = 1; j <= 11 - i; j++)
            printf("#");
        for (int j = 11 - i; j <= 10; j++)
            printf(" ");

        for (int j = 1; j <= i; j++)
            printf("#");
        for (int j = i; j <= 10; j++)
            printf(" ");

        for (int j = 1; j <= 11 - i; j++)
            printf("#");

        printf("\n");
    }

    return 0;
}
```

