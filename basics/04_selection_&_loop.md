选择结构与循环结构
============

<h1>选择结构</h1>
<pre>
1.if() else
2.switch() case:
</pre>

<h1>循环结构</h1>
<pre>
1.while() 循环
2.do while() 循环
3.for() 循环
</pre>

终止循环：
1.<font color="red">continue</font> 终止该次循环
2.<font color="red">break</font> 终止该循环
<h2>if else</h2>

```cpp
// 形式1
if(条件)
{ /*条件为真执行*/
    ...
}

// 形式2
if(条件)
{ /*条件为真执行*/
    ...
}else
{ /*条件为假执行*/
    ...
}

// 更多形式..
if(条件1)
{ /*条件1为真执行*/
    ...
}else if(条件2)
{ /*条件2为真执行*/
    ...
}else
{ /*条件1、2为假才执行*/
    ...
}
```

代码示例：


```cpp
#include <stdio.h>
int main()
{
    int salary = 2500;
    int rent = 850;
    int life_cost = 1000;

    if( salary > (rent + life_cost) )
    {
        printf("还过的下去");
    }else if( salary < (rent + life_cost) )
    {
        printf("活不下去了！");
    }else
    {
        printf("妈的！");
    }
}

```

<h2>switch</h2>


```cpp
switch(变量)
{
    case 情况1 :
        ...
    break;

    case 情况2 :
        ...
    break;

    case 情况3 :
        ...
    break;

    default :  /* 默认情况 */
        ...
}
```

代码示例


```cpp
#include <stdio.h>
int main()
{
    char cmd;

    printf("确认要删除吗？");
    scanf("%c", cmd);

    switch(cmd)
    {
        case 'Y':
            printf("文件正在删除\n");
        break;
        case 'N':
            printf("取消删除\n");
        break;
        defualt:
            printf("用户未响应，操作取消\n");
    }
}
```

关于case穿透


```cpp
#include <stdio.h>
int main()
{
    int score = 80;

    switch(math/10)
    {
        case 1:
        case 2:
        case 3:
        case 4:
        case 5:
            printf("不及格\n");
        case 6:
        case 7:
        case 8:
            printf("及格\n");
        case 9:
        case 10:
            printf("满分\n");
    }
}

```

<h2>while 循环</h2>


```cpp
#include <stdio.h>
int main()
{
    int i = 0;
    while(i < 10)
    {
        printf("%d ", i);
    }
}
```

<h2>do while 循环</h2>


```cpp
#include <stdio.h>
int main()
{
    char c;

    do
    {
        printf("请问你是⑨吗？(Y/N)\n")
        scanf("%c", &c);
    }while( c != 'Y');

}
```

<h2>for 循环</h2>


```cpp
// 形式
for( 初始值; 条件; 变化 )
{
    ...
}
```

示例:


```cpp
#include <stdio.h>
int main()
{
    int i;
    for( i = 0; i < 10; i++ )
    {
        printf("%d\n", i);
    }
}
```

<h2>continue与break</h2>

终止循环：
1.continue 终止该次循环
2.break 终止该循环


```cpp
#include
main()
{
    int i;
    for( i = 0; i < 10; i++)
    {
        if( i == 3 )
            continue;
        printf("%d ", i);
    }
}
```

