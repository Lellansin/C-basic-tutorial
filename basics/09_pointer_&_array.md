指针与数组
============

###上节课后作业

现在有一个数组，存储的是一个同学的期中考试成绩。

int score[8] = { 75, 86, 70, 88, 62, 87, 69, 77 };

那么现在我们要做的事情是：

1)求总分，求平均分

2)用指针遍历数组，求最大值和最小值

附加题：
用一个二维数组存储八门课的名称，例如：
char course[8][256] = { "chinese", "English" ... }
再用二维数组，存储多个人的成绩，用指针遍历求出每门课的平均分


```cpp
#include<stdio.h>
#include<stdlib.h>

int main()
{
    // 现在有一个数组，存储的是一个同学的期中考试成绩。
    char course[8][256] = { "语文", "数学", "英语", "物理", "化学", "生物", "历史", "地理" };
    char name[5][256] = {"Alan", "Bob", "Clain", "David", "Elis"};
    int score[5][8];
    int sum[5] = {0};
    float avg[8] = {0};

    int i,j;

    for(i = 0; i < 5; i++)
    {
        for(j = 0; j < 8; j++)
        {
            score[i][j] = rand() % 100;
        }
    }


    for(i = 0; i < 5; i++)
    {
        for(j = 0; j < 8; j++)
        {
            sum[i] += score[i][j];
            avg[j] += score[i][j];
        }
    }


    for(i = 0; i < 8; i++)
    {
        printf("\t%s", course[i]);
    }

    printf("\t总分");

    for(i = 0; i < 5; i++)
    {
        printf("\n%s", name[i]);
        for(j = 0; j < 8; j++)
        {
            printf("\t %d",score[i][j]);
        }
        printf("\t%d", sum[i]);
    }

    printf("\n平均分");

    for(j = 0; j < 8; j++)
    {
        printf("\t%.1f", avg[j] / 8.0);
    }

    printf("\n");
    return 0;
} 
```

字符数组与指针
----------------

字符串 == 字符数组+'\0'结尾


```cpp
// 对于字符串"Hello world"相当于如下的字符数组 
char hi[] = {'h','e','l','l','o',' ','w','o','r','l','d', '\0'};

printf("%c \n", hi[1]);  // e
printf("%c \n", "Hello world"[1]); // e

```
因为字符串相当于字符数组，所以"Hello world"[1]越数组hi[1]的值一样。

数组名 == 起始地址
----------------

学会自己研究各种变量

1)如何研究？
学会善用printf

2)怎么知道变量是不是一个指针(或地址)
学会使用*


```cpp
int a[5] = { 1, 3, 5 };

printf("%d",    a);   // 1638196
printf("%d",   *a);   // 1
printf("%d", *(a+1)); // 3
```
运行成功，表示这个变量的类型即使不是指针，也是一个地址

常见用法：

```cpp
int a[5] = { 1, 3, 5 };
int *p;
p = a;
printf("%d", *(p+1)); // 3
printf("%d", *(p+2)); // 5
```

"Hello world"究竟是？
----------------

有了上面的两个结论之后，我就可以继续使用printf来探讨更多的东西。
比如"Hello world"这个字符串所代表的意义。
我们已经知道这个字符串实际上就是一个字符数组，通过"Hello world"[1]甚至可以取到其中的值。那么对于这样一个字符串而言它的数组名(地址)是什么？
运用以上相同的方法可以看到：

```cpp
printf("%d",   "Hello world" );   // 4337572
printf("%d", *("Hello world"));   // 72
printf("%c", *("Hello world"));   // H
printf("%c", *("Hello world"+1)); // e
```

多个名字如何用char数组存储？
----------------

多个人的名字：

```cpp
char a[256] = "Alan";
char b[256] = "Bob";
char c[256] = "Cici";
```

现在要用数组来存储这三个人的名字。
也就是要用一个数组来存储三个数组，数组的每一个元素是一个数组：


```cpp
char name[3][256] = {"Alan", "Bob", "Cici" };
```

如何使用指针遍历
----------------


```cpp
int arr[8] = { 1, 1, 2, 3, 5, 8, 13, 21 };
int i;
int *p;
// 普通遍历
for(i = 0; i < 8; i++)
{
    printf("%d ", arr[i]);
}
// 指针遍历
for(p = &(arr[0]); p <= &(arr[7]); p++)
{
    printf("%d ", *p);
}
// 数组名获取指针地址
for(p = arr; p < (arr+8); p++)
{
    printf("%d ", *p);
}
```

本讲小结
----------------

1)如何使用指针遍历数组？
使用循环

2)如何研究各种变量？
尝试使用printf

3)数组与指针什么关系?
数组名就是一个地址，指向这个数据的开端


```cpp
int a[] = {1, 3, 5, 7, 9};
int *p = a;

printf( "%d \n",     *p == a[0] ); // 1
printf( "%d \n", *(p+1) == a[1] ); // 1
printf( "%d \n", *(p+2) == a[2] ); // 1
```

可以知道：

```cpp
*(p+n) == a[n]
```

引申推导：

```cpp
a[n] = *(p+n)
     = *(n+p)
     = n[a]
```

即：

```cpp
a[n] = n[a]
```

可以这样理解，下标对于数组来说，就是相对于起始地址的一个偏移量。