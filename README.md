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

```c
#include <stdio.h>

int main(void)
{
    int n = 7;

    for (int i = 0; i < n; i++)
    {
        int value = 1;

        for (int j = 0; j <= i; j++)
        {
            printf("%d ", value);
            value = value * (i - j) / (j + 1);
        }

        printf("\n");
    }

    return 0;
}
```

```c

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void)
{
    int data[20];

    srand(time(NULL));

    for (int i = 0; i < 20; i++)
        data[i] = rand() % 100;

    for (int i = 0; i < 20; i++)
    {
        int min = i;

        for (int j = i + 1; j < 20; j++)
        {
            if (data[j] < data[min])
                min = j;
        }

        int temp = data[i];
        data[i] = data[min];
        data[min] = temp;
    }

    for (int i = 0; i < 20; i++)
        printf("%d ", data[i]);

    return 0;
}
```

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void)
{
    int score[3][4];
    int sum;

    srand(time(NULL));

    for (int i = 0; i < 3; i++)
    {
        sum = 0;

        for (int j = 0; j < 4; j++)
        {
            score[i][j] = rand() % 101;
            sum += score[i][j];
        }

        printf("%d %d %d %d %d\n",
               i + 1,
               score[i][0],
               score[i][1],
               score[i][2],
               score[i][3]);

        printf("sum = %d\n", sum);
    }

    return 0;
}
