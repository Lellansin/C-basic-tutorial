数值、字符与字符串
============

<img class="alignnone" title="第2讲 数值、字符与字符串" src="http://pic002.cnblogs.com/images/2012/401241/2012101700414410.jpg" alt="" width="515" height="370" />

<h1>声明方式</h1>
数据类型 变量名;

举例：


```cpp
// int类型
int  i;           /* 普通声明 */
int  j,k;         /* 同时声明多个 */
int  age = 18;    /* 声明的同时赋值 */
int  Alan ,Sam=16;/* 声明与同时赋值 */

// float类型
float f;          /* 普通声明 */
float q,money;    /* 同时声明多个 */
float v = 2.0;    /* 声明的同时赋值 */

// char类型

char c;               /* 普通声明 */
char zh,text;         /* 同时声明多个 */
char letter = 'A';    /* 声明的同时赋值 */

// char数组(字符串)

char c[20] = { 'H','e','l','l','o',' ','w','o','r','l','d' };
char name[] = { 'A', 'l', 'a', 'n' };
```

<h1>转义字符</h1>

在一段字符串中，不能直接出现，需要转义的字符，例如：

'\n' 换行
'\t'' 水平制表
'\'' 单引号
'\"' 双引号
'\\' 反斜杠


```cpp
#include<stdio.h>
main()
{
    printf("Num\tName\n");
    printf("001\tAlan\n");
    printf("002\tLellansin\n");
}
```


```cpp
输出结果：
Num　　　Name
001　　　Alan
002　　　Lellansin
```

<h1>printf与scanf</h1>

printf 打印，scanf 为输入

形式

```cpp
printf(字符串，... );  // 点点点为多个参数
scanf(字符串，... );
```

<h2>占位符</h2>

对于 printf 输出的情况而言，占位符的意思是先占个位置的符号，至于这个位置将来会放什么还不确定，只能先确定是占位符所指明的类型，具体的值还要等稍后的参数中补充。对于 scanf 来说，则是相反的情况。

常见格式：

%d 　　十进制整数
%i 　　十进制整数
%c 　　单个字符
%s 　　字符串
%f 　　浮点数

如：


```cpp
// 输出字符串要输出的年龄尚未确实值知道是 %d 十进制整数类型, 
// 具体输出来是什么值则看后面 age 的具体值
printf("Alan的年龄是%d", age); 

// 接手用户输入的一个十进制整数，注意输入是要加 & 符号
// 如果用户输入 10.2 则存入变量i中的值是 10，因为格式是十进制整数
scanf("%d", &i);

```

举例：


```cpp
#include<stdio.h>
int main()
{
    int age;
    printf("你的年龄是？\n");
    scanf("%d",&age); // 输入时变量前加上 “&” 符号
    printf("你的年龄是%d",age);
}
```

