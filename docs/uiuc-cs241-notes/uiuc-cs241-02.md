# HW0

## 欢迎！

如果你正在上 CS241 课程，你可以在这个[Google 表格](https://docs.google.com/a/illinois.edu/forms/d/e/1FAIpQLScB-OomiGPRm8Q5u3rhDypIuGaOTYFzNqzNTtjs5g7-_1XBTw/viewform)上提交作业。

```cpp
// First can you guess which lyrics have been transformed into this C-like system code?
char q[] = "Do you wanna build a C99 program?";
#define or "go debugging with gdb?"
static unsigned int i = sizeof(or) != strlen(or);
char* ptr = "lathe"; size_t come = fprintf(stdout,"%s door", ptr+2);
int away = ! (int) * "";

int* shared = mmap(NULL, sizeof(int*), PROT_READ | PROT_WRITE, MAP_SHARED | MAP_ANONYMOUS, -1, 0);
munmap(shared,sizeof(int*));

if(!fork()) { execlp("man","man","-3","ftell", (char*)0); perror("failed"); }
if(!fork()) { execlp("make","make", "snowman", (char*)0); execlp("make","make", (char*)0)); }

exit(0);
```

## 所以你想精通系统编程？并且比 B 更好地得到一个好成绩？

```cpp
int main(int argc, char** argv) {
 puts("Great! We have plenty of useful resources for you but it's up to you to");
 puts("be an active learner and learn how to solve problems and debug code.");
 puts("Bring your near-completed answers the problems below");
 puts(" to the first lab to show that you've been working on this");
 printf("A few \"don't knows\" or \"unsure\" is fine for lab 1"); 
 puts("Warning; your peers will be working hard for this class");
 puts("This is not CS225; you will be pushed much harder to");
 puts(" work things out on your own");
 fprintf(stdout,"the point is that this homework is a stepping stone to all future assignments");
 char p[] = "so you will want to clear up any confusions or misconceptions.";
 write(1, p, strlen(p) );
 char buffer[1024];
 sprintf(buffer,"For grading purposes this homework 0 will be graded as part of your lab %d work.", 1);
 write(1, buffer, strlen(buffer));
 printf("Press Return to continue\n");
 read(0, buffer, sizeof(buffer));
 return 0;
}
```

## 观看视频并写下你对以下问题的答案。

[`cs-education.github.io/sys/`](http://cs-education.github.io/sys/)

还有课程 wikibook -

[`github.com/angrave/SystemProgramming/wiki`](https://github.com/angrave/SystemProgramming/wiki)

有问题？评论？使用 Piazza，[`piazza.com/illinois/spring2017/cs241/home`](https://piazza.com/illinois/spring2017/cs241/home)

浏览器中的虚拟机完全在 Javascript 中运行，最快的是在 Chrome 中。请注意，当重新加载页面时，虚拟机和你写的任何代码都会被重置，所以把你的代码复制到一个单独的文档中。视频后的挑战（如俳句诗）不是作业 0 的一部分。

### 第一章

+   Hello World（系统调用风格）

    +   编写一个程序，使用`write()`打印出“Hi! My name is”。

+   标准错误流

    +   编写一个程序，使用`write()`将高度为 n 的三角形打印到标准错误

        +   n 应该是一个变量，三角形应该看起来像这样，n=3

        ```cpp
        *
        **
        ***
        ```

+   写入文件

    +   将你的程序从“Hello World”改成写入文件

        +   确保对`open()`使用一些有趣的标志和模式

        +   `man 2 open`是你的朋友

+   并不是所有的都是系统调用

    +   将你的程序从“写入文件”改成使用`printf()`（确保打印到文件！）

    +   列举一些`write()`和`printf()`的不同之处

### 第二章

+   并不是所有的字节都是 8 位？

    +   一个字节有多少位？

    +   `char`有多少个字节？

    +   告诉我你的机器上以下这些的字节数：`int, double, float, long, long long`

+   跟随 int 指针

    +   在一个有 8 字节整数的机器上：

    ```cpp
    int main(){
        int data[8];
    } 
    ```

    如果数据的地址是`0x7fbd9d40`，那么`data+2`的地址是多少？

    +   在 C 中，`data[3]`等同于什么？

+   `sizeof`字符数组，增加指针

    记住字符串常量`"abc"`的类型是数组。

    +   为什么会出现段错误？

    ```cpp
    char *ptr = "hello";
    *ptr = 'J';
    ```

    +   `sizeof("Hello\0World")`返回什么？

    +   `strlen("Hello\0World")`返回什么？

    +   给出一个例子 X，使得`sizeof(X)`为 3

    +   给出一个例子 Y，使得`sizeof(Y)`可能是 4 或 8，取决于机器。

### 第三章

+   程序参数`argc` `argv`

    +   告诉我两种找到`argv`长度的方法

    +   `argv[0]`是什么

+   环境变量

    +   环境变量的指针存储在哪里？

+   字符串搜索（字符串只是字符数组）

    +   在一个指针为 8 字节的机器上，并且有以下代码：

    ```cpp
    char *ptr = "Hello";
    char array[] = "Hello";
    ```

    `sizeof(ptr)`和`sizeof(array)`的结果是什么？为什么？

+   自动变量的生命周期

    +   哪种数据结构管理自动变量的生命周期？

### 第四章

+   使用`malloc`、堆和时间进行内存分配

    +   如果我想在函数结束后使用数据，那么我应该把它放在哪里，怎么放？

    +   填空。在一个好的 C 程序中：“对于每一个 malloc，都有一个 ___”。

+   堆分配陷阱

    +   `malloc`失败的一个原因是什么。

    +   列举一些`time()`和`ctime()`之间的区别

    +   这段代码有什么问题？

    ```cpp
    free(ptr);
    free(ptr);
    ```

    +   这段代码有什么问题？

    ```cpp
    free(ptr);
    printf("%s\n", ptr);
    ```

    +   如何避免前两个错误？

+   结构体、typedef 和链表

    +   创建一个表示人的结构体并进行 typedef，这样“struct Person”可以用一个单词替换。

        +   一个人应该包含以下信息：姓名，年龄，朋友（指向 People 指针数组的指针）。

    +   现在在堆上创建两个人“Agent Smith”和“Sonny Moore”，分别为 128 岁和 256 岁，并且彼此是朋友。

+   复制字符串，内存分配和结构的释放

    +   创建函数来创建和销毁一个人（人和他们的名字应该存在于堆上）。

        +   `create()`应该接受一个名称并复制该名称，还应该接受一个年龄。使用 malloc 来保留足够的内存。确保初始化所有字段（为什么？）。

        +   `destroy()`应该释放人员结构体的内存，还应该释放存储在堆上的所有属性的内存（如果存在数组和字符串）。然而，销毁一个人员不应该销毁其他人员。

### 第 5 章

+   阅读字符，gets 出现问题

    +   可以用于从`stdin`获取字符并将其写入`stdout`的函数有哪些？

    +   `gets()`存在一个问题

+   介绍`sscanf`和朋友们

    +   编写代码，解析字符串“Hello 5 World”，并分别将 3 个变量初始化为（“Hello”，5，“World”）。

+   `getline`很有用

    +   在使用`getline()`之前需要定义什么？

    +   编写一个 C 程序，使用`getline()`逐行打印文件内容

### C 开发（在这里进行网页搜索很有用）

+   用于生成调试构建的编译器标志是什么？

+   您修改 makefile 以生成调试构建，并再次输入`make`。解释为什么这不足以生成新的构建。

+   Makefiles 中使用制表符还是空格？

+   堆和栈内存之间有什么区别？

+   进程中还有其他种类的内存吗？

### 可选（只是为了好玩）

+   将您的一首歌歌词转换为本维基书中涵盖的系统编程和 C 代码，并在 Piazza 上分享

+   找到您认为是网络上最好和最差的 C 代码，并将链接发布到 Piazza

+   编写一个有意识的微妙 C 错误的简短 C 程序，并在 Piazza 上发布，看看其他人是否能发现您的错误
