字符串处理
=============

字符与字符串的区别
---------------

1)符号

```cpp
字符	' ' 单引号
字符串	" " 双引号
```

2)内容

```cpp
字符	单个字符
字符串	多个字符
```

3)输入输出格式

```cpp
字符	%c
字符串	%s
```

4)标识

```cpp
字符串	'\0'做结尾
```

字符串的本质是?
---------------

字符串本质上就是一个字符数组

"hello world" 这样的字符串，就是包含其中各个元素的，并且结尾为'\0'的一个一维字符数组

如:

```cpp
char hi[12]={'H','e','l','l','o',' ','w','o','r','l','d','\0'};
```

因为一个字符串要有'\0'作为结尾
所以字符数组的长度要比本身字符数目多一个

如上例中,字符串有11个,但是字符数组长度要达到12


字符串的定义与初始化
---------------

字符串面量:
"Hello world"         注意：字面量(双引号引起来的)是常量

区别举例：

```cpp
"Alan"  常量
char name[20] = "Jack";   // "Jack"是字面量 是常量  name是字符数组, 是变量
```

注：
常量不能被赋值，如讲2的值赋给1这样：

```cpp
1 = 2 是不行的，1是常量不能被赋值
```
"string" 这样的字符串也是不能被赋值的：

```cpp
"string" = "Hello Jack" 这样是错的
```


字符数组
---------------

1)数组形式

```cpp
char hi[3]={'H', 'i','\0'};
char hello[]={'H','e','l','l','o',' ','w','o','r','l','d','\0'};
```

2)直接赋首地址

```cpp
char shool[20] = "第一中学";
```

3)省略长度

```cpp
char name1[] = "Alan";
char name2[] = { "Alan" };
```


字符指针
---------------


```cpp
char *name3  = "Alan";
char *s = "第一中学";
```

思考:
指针能不能直接赋给数组?


字符串的遍历
---------------


```cpp
char hi[] = "I am happy" ;
```

1.for循环遍历

```cpp
for(i=0; i<11; i++)
{
    printf("%c", hi);
}
```

2.直接输出

```cpp
printf(hi);
```

3.字符串格式(%s)输出

```cpp
printf("%s", hi);
```


字符串数组（二维字符数组）
---------------

常见姓名：

```cpp
char name1[] = "张三";
char name2[] = "李四";
char name3[] = "王五";
```

存储多个字符串：

1)二维数组

```cpp
char name[][256] = { "张三", "李四", "王五" };
```

2)一维指针数组

```cpp
char *name[] = { "张三", "李四", "王五" };
```


对于printf，最重要的是？
---------------

对于printf和scanf来说，字符串最重要的是其起始地址

如打印一个字符串：

```cpp
char *text = "hey gays!";

1) pirntf(text);
2) printf("%s", text);
```

对于printf这个函数而言，只要知道字符串开头的地址，
那么就一直打印下去，一直到碰到'\0'的时候停止

如：

```cpp
printf("Hello \0 world"); \\ hello 
```


常见的字符串操作函数
---------------

stdio.h

输入：scanf()、gets()、getchar()
输出：printf()、puts()、putchar()

string.h

连接：strcat()
拷贝：strcpy()
比较：strcmp()
获取长度：strlen()
大小写转换：strupr()、strlwr()
拼接字符串：sprintf()

示例：

```cpp
#include<stdio.h>
#include<string.h>
int main()
{
    char *hi = "hello", s2 = "Alice";
    char str[256], *pstr;
    printf("%s \n", strcat(hi, " world"));//连接
    printf("%s \n", strcpy(str, "come on")); //拷贝
    printf("%s \n", strcmp("你好", "你好")); //比较
    printf("%s \n", strlen(str)); //获取长度
    printf("%s \n", strupr(str)); //转成大写
}
```


学会查询文档：
---------------
1.右键查看定义
2.度娘谷歌
3.手册 
4.自己撰写自己的文档


关于函数传参数
---------------


```cpp
对于：int add(int a, int b);
调用：add(5, 10);

add函数中参数初始化时，相当于：
int a = 5;  int b = 10

对于：int swap(int *x, int *y);
调用：swap(&i, &j);

swap函数中参数初始化时 ，相当与：
int *x = &i;  int *y = &j;
```


strlen()
---------------


```cpp
#include<stdio.h>
int mylength(char *aim);

int main()
{
    char *str1 = "hello ";
    printf("%d\n", mylength(str1));
}

int mylength(char *aim)
{
    int count=0;
    while(*aim++){
    count++;
    }
    return count;
}
```


strcat()
---------------


```cpp
#include<stdio.h>
char * mycat(char *dest, char *src);

int main()
{
	char str1[20] = "hello "; // 要拷贝的话需要有足够的内存
	char *str2 = "world";
	printf("%s\n", mycat(str1, str2));
}

char *mycat(char *dest, const char *src)
{
	char *address = dest;

	while (*++dest) // 加到 '\0' 马上停止
		;

	while (*dest++ = *src++)
		;

	return address;
}
```
(感谢 灬蕾依丽雅 君的提醒, 该函数已修正)

<h1>本讲小结</h1>

一、字符串的本质，与字符的区别
1)本质上是结尾为'\0'字符数组
2)单双引号，书写区别
3)输出格式"%c"和"%s"

二、字符串的定义与初始化
1)字面量
2)数组
3)指针

三、常见的字符串操作，及其操作的实现
连接(strcat)、拷贝(strcpy)、比较(strcmp)、获取长度(strlen)、大小写转换(strupr、strlwr)、拼接字符串(sprintf)

以上部分函数的实现跨越在博主的 string.h 的实现中找到 <a href="http://www.lellansin.com/tutorials/c-standard-library" target="_blank">博主的 C标准库</a>

课后作业 

通过自己查找参考，理解并实现以上常见的字符串操作
注：sprintf()只要掌握，不要求实现