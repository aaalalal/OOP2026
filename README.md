## 1. 10x10 텍스트 직각삼각형 네가지 프로그램 작성

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
![실행 결과](Homework/1.jpg)
```
## 2. 피보나치수열 20번째 까지 



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

## 3. 황금비율계산 20번째 까지 

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
## 4. 구구샘표 만들기 

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
## 5. 원주율 계
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
## 6. 이항정리 계수구하기
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
## 7. 소팅(sorting)알고리즘 - selection sorting

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

## 8. 국영수과학성적 

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
```
## 10. 도수분포표만들기 


```java
public class Histogram {

    public static void main(String[] args) {

        int array_count, max_value, bin_size, display_scale, hist_size;

        if (args.length != 4)
            return;

        array_count = Integer.parseInt(args[0]);
        max_value = Integer.parseInt(args[1]);
        bin_size = Integer.parseInt(args[2]);
        display_scale = Integer.parseInt(args[3]);

        hist_size = max_value / bin_size;

        int[] arr = new int[array_count];
        int[] hist = new int[hist_size];

        for (int i = 0; i < array_count; i++) {
            arr[i] = (int)(Math.random() * max_value);
        }

        for (int i = 0; i < array_count; i++) {
            System.out.print(arr[i] + " ");
        }

        System.out.println();

        for (int i = 0; i < array_count; i++) {
            hist[arr[i] / bin_size]++;
        }

        for (int i = 0; i < hist_size; i++) {

            System.out.print((i * bin_size) + "~" + ((i + 1) * bin_size - 1) + "\t");

            for (int j = 0; j < hist[i] / display_scale; j++) {
                System.out.print("#");
            }

            System.out.println();
        }
    }
}
```
## 11. 산술평균(arithmetic), 기하평균(geometric), 조화평균(harmonic), 중앙값(median) 계산하기


```java
import java.util.Arrays;

public class Mean {

    public static void main(String[] args) {

        int array_count;

        if (args.length != 1)
            return;

        array_count = Integer.parseInt(args[0]);

        int[] arr = new int[array_count];

        for (int i = 0; i < array_count; i++) {
            arr[i] = (int)(Math.random() * 100) + 1;
        }

        for (int i = 0; i < array_count; i++) {
            System.out.print(arr[i] + " ");
        }

        System.out.println();

        double sum = 0;

        for (int i = 0; i < array_count; i++) {
            sum += arr[i];
        }

        double arithmetic = sum / array_count;

        double product = 1;

        for (int i = 0; i < array_count; i++) {
            product *= arr[i];
        }

        double geometric = Math.pow(product, 1.0 / array_count);

        double reciprocalSum = 0;

        for (int i = 0; i < array_count; i++) {
            reciprocalSum += 1.0 / arr[i];
        }

        double harmonic = array_count / reciprocalSum;

        Arrays.sort(arr);

        double median;

        if (array_count % 2 == 1) {
            median = arr[array_count / 2];
        } else {
            median = (arr[array_count / 2 - 1] + arr[array_count / 2]) / 2.0;
        }

        System.out.printf("arithmetic mean = %f\n", arithmetic);
        System.out.printf("geometric mean = %f\n", geometric);
        System.out.printf("harmonic mean = %f\n", harmonic);
        System.out.printf("median = %f\n", median);
    }
}
```
## 13. 계산기 프로그램

```java
import java.util.Scanner;

public class miniCalculator {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        while (true) {

            String inputString = scanner.nextLine();

            if (inputString.equals("exit"))
                break;

            String[] arrOfStr = inputString.split(" ");

            double result = Double.parseDouble(arrOfStr[0]);

            for (int i = 1; i < arrOfStr.length; i += 2) {

                String operator = arrOfStr[i];
                double number = Double.parseDouble(arrOfStr[i + 1]);

                if (operator.equals("+")) {
                    result += number;
                }
                else if (operator.equals("-")) {
                    result -= number;
                }
                else if (operator.equals("*")) {
                    result *= number;
                }
                else if (operator.equals("#")) {
                    result *= number;
                }
                else if (operator.equals("/")) {
                    result /= number;
                }
            }

            System.out.println(result);
        }

        scanner.close();
    }
}
```

