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



```c
#include <stdio.h>

int main(void)
{
    int a = 1, b = 1, c;

    for (int i = 1; i <= 20; i++)
    {
        printf("%d ", a);

        c = a + b;
        a = b;
        b = c;
    }

    return 0;
}
```


```c
#include <stdio.h>

int main(void)
{
    int a = 1, b = 1, c;
    double ratio;

    for (int i = 1; i <= 20; i++)
    {
        c = a + b;

        if (i >= 2)
        {
            ratio = (double)c / b;
            printf("%d/%d = %.3f\n", c, b, ratio);
        }

        a = b;
        b = c;
    }


    return 0;
}
```

```c
#include <stdio.h>

int main(void)
{
    for (int i = 1; i <= 9; i++)
    {
        for (int j = 1; j <= 9; j++)
        {
            printf("%d*%d=%d ", j, i, j * i);
        }

        printf("\n");
    }

    return 0;
}
```

```c
#include <stdio.h>

int main(void)
{
    double pi = 0.0;
    int n = 1000;

    for (int i = 0; i < n; i++)
    {
        if (i % 2 == 0)
            pi += 4.0 / (2 * i + 1);
        else
            pi -= 4.0 / (2 * i + 1);
    }

    printf("pi = %.10f\n", pi);

    return 0;
}
```

#include <stdio.h>

int main(void)
{
    double pi = 0.0;

    for (int k = 0; k < 1000; k++)
    {
        pi += pow(-1.0 / 3.0, k) / (2 * k + 1);
    }

    pi *= sqrt(12.0);

    printf("pi = %.15f\n", pi);

    return 0;
}
