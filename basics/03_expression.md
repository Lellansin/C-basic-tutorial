运算符以及表达式
==========

```cpp
// 算术运算符

#include <stdio.h>
int main()
{
    int i = 7, j = 8;

    printf("i+j=%d\n", i + j ); //15
    printf("i-j=%d\n", i - j ); //0
    printf("i*j=%d\n", i * j ); //56
    printf("i/j=%d\n", i / j ); //0
    printf("i%%j=%d\n", i % j );//7

    i++;
    printf("i++后i的值为%d\n",i);  //8
    printf("++i后i的值为%d\n",++i);//9

    printf("j--后j的值为%d\n",j--);//8
    printf("--j后j的值为%d\n",--j);//6
}
```



```cpp
// 关系与逻辑运算符

#include <stdio.h>
int main()
{
    int Alan = 18, Sam = 18, Jack = 16;

    printf("%d\n", Alan > Jack ); // 1
    printf("%d\n", Sam  < Jack ); // 0     
    printf("%d\n", Alan != Sam ); // 0
    printf("%d\n", Alan == Sam ); // 1
    printf("%d\n", Alan >= Sam ); // 1
    printf("%d\n", (Sam>Jack) && (Sam>Jack) ); //1
    printf("%d\n", Alan > Jack );//1
    printf("%d\n", ! Sam );    //0
}
```

&nbsp;


```cpp
/*
    数据类型转换
    形式：
    (类型) (表达式)
*/

#include <stdio.h>
int main()
{
    int chinese, math, english, sum;

    printf("请输入语数英三科的成绩：(以空格隔开)\n");
    scanf("%d%d%d", &chinese, &math, &english);

    sum = (chinese + math + english);

    printf("平均分为%d\n", sum/3);
    printf("平均分为%f\n", (float)sum/3);
}
```

需要注意的是“=”与“==”之间的区别：
“=”是赋值运算
“==”是逻辑运算


```cpp
#include <stdio.h>
int main()
{
    int i = 5, b = 10;

    printf(" a=b 值为 %d\n", a = b ); //10
    printf("a==b 值为 %d\n", a == b); //0

}
```

