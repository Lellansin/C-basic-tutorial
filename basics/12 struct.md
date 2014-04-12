结构体
============

<span style="font-size: xx-large;">结构体</span>

可以将多种数据类型组合起来的结构

<span style="font-size: x-large;">声明方式</span>

struct 结构体名称{
成员1的类型  成员1的名称;
成员2的类型 成员2的名称;
......
成员3的类型  成员3的名称;
} ;

举例：

```cpp
struct time{
	int hour;
	int minute;
	int second;
} ;
```



注意不要漏掉了最后的分号

<span style="font-size: xx-large;">结构体的定义</span>

1)常规定义

```cpp
struct time{
	int hour;
	int minute;
	int second;
} ;

struct time t;
```



	如何定义一个int类型的变量？

```cpp
	int number;
```



实际上来说，结构体变量的定义是跟普通数据类型类似的。
	如，以上两个变量的声明区别，仅在于，一个的类型是struct time 另一个的类型是int


2)声明的同时定义

```cpp
struct student{
	char name[256];
	char sex[2];
	int age;
	int grade;
} Alan, Tom ;
```



3)使用结构体作为成员

```cpp
struct DATE{
	int year;
	int month;
	int day;
} ;

struct person{
	char name[256];
	struct DATE birthday;
} ;

struct time t;
```




4)匿名结构体

```cpp
struct {
	int number;
	char name[256];
	char sex[2];
	int age;
	int grade;
} Alan, Tom ;
```




<span style="font-size: xx-large;">结构体的引用与初始化</span>

使用“.”成员运算符来获取结构体中的成员


```cpp
#include<stdio.h>#include<string.h>

struct student{
	int number;
	char name[256];
	char sex[2];
	int age;
	int grade;
} ;
int main()
{
	struct student alan;
	alan.number = 001;
	strcpy(alan.name, "Allan");
	strcpy(alan.sex, "男");
	alan.age = 18;
	alan.grade = 3;

	printf("学号：%d \n姓名: %s \n性别：%s \n年龄：%d\n年级：%d\n", 
		   alan.number, alan.name, alan.sex, alan.age, alan.grade);
}

```




<span style="font-size: xx-large;">结构体数组</span>

结构体数组的使用：

```cpp
#include<stdio.h>
#include<string.h>

struct student{
	int number;
	char name[256];
	int age;
} ;
int main()
{
	struct student class_02[5];
	int k;

	for(k=0; k < 5; k++)
	{
		printf("Please input number:\n");
		scanf("%d", &class_02[k] .number);
		printf("Please input name:\n");
		scanf("%s", class_02[k] .name);

		printf("Please input age:\n");
		scanf("%d", &class_02[k] .age);

		printf("\n");
	}

	printf("Num\tName\tage\n");

	for(k=0; k < 5; k++)
	{
		printf("%d\t", class_02[k] .number);
		printf("%s\t", class_02[k] .name);
		printf("%d\n", class_02[k] .age);
	}
}
```




```cpp
#include<stdio.h>

struct student{
	int number;
	char name[256];
	char sex[6];
	int age;
	int grade;
} ;
int main()
{
	struct student class1[5] = {
		{ 01, "Alan", "man", 16, 12 },
		{ 02, "Bob", "man", 18, 12 },
		{ 03, "Cici", "woman", 16, 12 },
		{ 04, "David", "man", 11, 12 },
		{ 05, "Elis", "woman", 16, 12 },
	};
	for(k = 0; k < 5; k++)
	{
		printf("\nstudy number: %d \nname: %s \nsex: %s \nage: %d\n grade: %d\n" ,class1[k].number,
		class1[k].name,
		class1[k].sex,
		class1[k].age,
		class1[k].grade);
	}
}
```




<span style="font-size: xx-large;">结构体指针</span>

使用分量运算符“-&gt;”来获取成员


```cpp
#include<stdio.h>

struct DATE{
	int year;
	int month;
	int day;
} *date ;
int main()
{
	date->year = 2012;
	printf("%d", date->year);
}

```




```cpp
#include<stdio.h>

struct DATE{
	int year;
	int month;
	int day;
} date = { 2012, 11, 27 }, *d ;
int main()
{
	d = &date;
	printf("%d", d->year);
}

```



用于函数的参数以及返回值:

```cpp
#include<stdio.h>

struct time add(struct time now, struct time pass);

struct time{
	int hour;
	int min;
} ;
int main()
{
	struct time now = { 3, 55 }, pass = { 1, 33 }, result;
	result = add(now, pass);
	printf("%d:%d\n", result.hour, result.min);
}

struct time add(struct time now, struct time pass)
{
	struct time rel;
	rel.hour = now.hour + pass.hour + (now.min + pass.min)/60 ;
	rel.min = (now.min + pass.min)%60;
	return rel;
}
```