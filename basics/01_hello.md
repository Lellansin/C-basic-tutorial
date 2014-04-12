Hello world
============

压缩版下载地址：<a href="http://www.lellansin.com/wp-content/uploads/2012/10/vc6_cn_setup.exe">vc6_cn_setup</a>
完整版、加强版等下载地址：<a href="http://hi.baidu.com/jsj08/item/fa8ac4c44aafa22947d5c046" rel="nofollow" target="_blank">Visual C++ 6.0</a>

1.下载 vc6_cn_setup.exe 或者是其他版本的vc6 （推荐下载完整版，或者不嫌麻烦的可以去下载 visual studio 2010 或 2012）
2.安装vc 6.0 （一路确定过去就行了）
3.打开安装好的vc 6.0，如果操作系统是win7的话会提示不兼容，这个可以直接忽略，直接运行程序就可以了。

关掉每日提示，文件-&gt;新建-&gt;切换到文件-&gt;C++ source file-&gt;确定

到这里，我们可以先保存一下，保存的时候，劲量新建一个文件夹，保存在新文件夹内。避免编译之类的操作新生成一些文件，使得文件看起来很乱。

接下来开始输入第一个程序的代码：


```cpp
#include<stdio.h>
int main()
{
    printf("Hello world");
}
```

输入完后记得保存（快捷键ctrl+s），然后找到菜单上的 组建-&gt;编译， 组建-&gt;执行

如果运行成功，那么恭喜你，你已经开始了你的编程之旅
如果有报错，可以仔细核对一下你的代码，看看是不是拼写有错
