# C 编程，第一部分：介绍

## 想要快速了解 C 吗？

+   继续阅读下面的 C 编程快速入门课程

+   然后查看[C Gotchas wiki 页面](/angrave/SystemProgramming/wiki/C-Programming%2C-Part-3%3A-Common-Gotchas)。

+   并了解[文本 I/O](/angrave/SystemProgramming/wiki/C-Programming%2C-Part-2%3A-Text-Input-And-Output)。

+   与[劳伦斯的介绍视频](http://cs-education.github.io/sys/#)一起放松身心（还有一个可以玩的浏览器中的虚拟机！）

## 外部资源

+   [在 Y 分钟内学习 X](https://learnxinyminutes.com/docs/c/)（强烈建议快速浏览！）

+   [C for C++/Java 程序员](http://www.ccs.neu.edu/course/com3620/parent/C-for-Java-C++/c-for-c++-alt.html)

+   Brian Kernighan 的 C 教程](http://www.lysator.liu.se/c/bwk-tutor.html)

+   [c faq](http://c-faq.com/)

+   [C Bootcamp](http://gribblelab.org/CBootCamp/index.html)

+   [C/C++函数参考](http://www.cplusplus.com/reference/clibrary/)

+   [gdb（Gnu 调试器）教程](http://www.unknownroad.com/rtfm/gdbtut/gdbtoc.html)提示：使用“-tui”命令行参数运行 gdb，以获得调试器的全屏版本。

+   在这里添加您喜欢的资源

## C 的快速入门课程

*警告新页面* 请为我修复拼写错误和格式错误，并添加有用的链接。*

## 如何在 C 中编写一个完整的 hello world 程序？

```cpp
#include <stdio.h>
int main(void) { 
    printf("Hello World\n");
    return 0; 
}
```

## 为什么我们使用`#include <stdio.h>`？

我们很懒！我们不想声明`printf`函数。它已经在文件`'stdio.h'`中为我们完成。`#include`将文件的文本包含为要编译的文件的一部分。 

具体来说，`#include`指令获取操作系统中某个位置的文件`stdio.h`（代表**st**an**d**ard **i**nput 和**o**utput），复制文本，并将其替换为`#include`所在的位置。

## C 字符串是如何表示的？

它们在内存中表示为字符。字符串的结尾包括一个 NULL（0）字节。因此，“ABC”需要四（4）个字节`['A'，'B'，'C'，'\0']`。查找 C 字符串的长度的唯一方法是继续读取内存，直到找到 NULL 字节。C 字符始终每个都是一个字节。

当您在表达式中写入字符串文字`"ABC"`时，字符串文字将计算为 char 指针（`char *`），它指向字符串的第一个字节/字符。这意味着下面示例中的`ptr`将保存字符串中第一个字符的内存地址。

```cpp
char *ptr = "ABC"
```

## 如何声明一个指针？

指针指的是一个内存地址。指针的类型很有用-它告诉编译器需要读取/写入多少字节。您可以声明指针如下。

```cpp
int *ptr1;
char *ptr2;
```

由于 C 的语法，`int*`或任何指针实际上并不是自己的类型。您必须在每个指针变量之前加上一个星号。作为一个常见的陷阱，以下

```cpp
int* ptr3, ptr4;
```

只会声明`*ptr3`作为指针。`ptr4`实际上将是一个常规的整数变量。要修复此声明，请保留指针之前的`*`

```cpp
int *ptr3, *ptr4;
```

## 如何使用指针读/写一些内存？

假设我们声明一个指针`int *ptr`。为了讨论，假设`ptr`指向内存地址`0x1000`。如果我们想要写入指针，我们可以推迟并分配`*ptr`。

```cpp
*ptr = 0; // Writes some memory.
```

C 将执行的操作是获取指针的类型，即`int`，并从指针的起始位置写入`sizeof(int)`字节，这意味着字节`0x1000`，`0x1004`，`0x1008`，`0x100a`都将为零。写入的字节数取决于指针类型。对于所有原始类型都是相同的，但是结构体有点不同。

## 什么是指针算术？

您可以将整数添加到指针。但是，指针类型用于确定要增加指针的量。对于 char 指针，这是微不足道的，因为字符始终是一个字节：

```cpp
char *ptr = "Hello"; // ptr holds the memory location of 'H'
ptr += 2; //ptr now points to the first'l'
```

如果 int 是 4 个字节，那么 ptr+1 指向 ptr 指向的位置之后的 4 个字节。

```cpp
char *ptr = "ABCDEFGH";
int *bna = (int *) ptr;
bna +=1; // Would cause iterate by one integer space (i.e 4 bytes on some systems)
ptr = (char *) bna;
printf("%s", ptr);
/* Notice how only 'EFGH' is printed. Why is that? Well as mentioned above, when performing 'bna+=1' we are increasing the **integer** pointer by 1, (translates to 4 bytes on most systems) which is equivalent to 4 characters (each character is only 1 byte)*/
return 0;
```

因为 C 中的指针算术始终自动按指向的类型的大小进行缩放，所以不能对 void 指针执行指针算术。

在 C 中，你可以将指针算术视为基本上是在做以下操作

如果我想要做

```cpp
int *ptr1 = ...;
int *offset = ptr1 + 4;
```

思考

```cpp
int *ptr1 = ...;
char *temp_ptr1 = (char*) ptr1;
int *offset = (int*)(temp_ptr1 + sizeof(int)*4);
```

要获取值。**每次进行指针算术运算时，深呼吸并确保你移动的字节数是你认为的那么多。**

## 什么是 void 指针？

没有类型的指针（非常类似于 void 变量）。当你处理的数据类型未知或者当你将 C 代码与其他编程语言进行接口时，会使用 void 指针。你可以把它看作是一个原始指针，或者只是一个内存地址。你不能直接读取或写入它，因为 void 类型没有大小。例如

```cpp
void *give_me_space = malloc(10);
char *string = give_me_space;
```

这不需要转换，因为 C 会自动将`void*`提升为其适当的类型。**注意：**

gcc 和 clang 并不是完全符合 ISO-C 标准，这意味着它们会允许你对 void 指针进行算术运算。它们会将其视为 char 指针，但不要这样做，因为它可能无法在所有编译器上工作！

## `printf`调用 write 还是 write 调用`printf`？

`printf`调用`write`。`printf`包括一个内部缓冲区，所以为了提高性能，`printf`可能不会在每次调用`printf`时都调用`write`。`printf`是一个 C 库函数。`write`是一个系统调用，我们知道系统调用是昂贵的。另一方面，`printf`使用一个更适合我们需求的缓冲区

## 如何打印出指针值？整数？字符串？

使用格式说明符“%p”表示指针，“%d”表示整数，“%s”表示字符串。所有格式说明符的完整列表在[这里](http://www.cplusplus.com/reference/cstdio/printf/)中找到

整数的例子：

```cpp
int num1 = 10;
printf("%d", num1); //prints num1
```

整数指针的例子：

```cpp
int *ptr = (int *) malloc(sizeof(int));
*ptr = 10;
printf("%p\n", ptr); //prints the address pointed to by the pointer
printf("%p\n", &ptr); /*prints the address of pointer -- extremely useful
when dealing with double pointers*/
printf("%d", *ptr); //prints the integer content of ptr
return 0;
```

字符串的例子：

```cpp
char *str = (char *) malloc(256 * sizeof(char));
strcpy(str, "Hello there!");
printf("%p\n", str); // print the address in the heap
printf("%s", str);
return 0;
```

[字符串作为指针和数组@ BU](https://www.cs.bu.edu/teaching/c/string/intro/)

## 如何将标准输出保存到文件？

最简单的方法：运行你的程序并使用 shell 重定向，例如

```cpp
./program > output.txt

#To read the contents of the file,
cat output.txt 
```

更复杂的方法：关闭（1），然后使用 open 重新打开文件描述符。参见[`cs-education.github.io/sys/#chapter/0/section/3/activity/0`](http://cs-education.github.io/sys/#chapter/0/section/3/activity/0)

## 指针和数组有什么区别？举一个你可以用其中一个做而另一个做不到的例子。

```cpp
char ary[] = "Hello";
char *ptr = "Hello";
```

例子

数组名指向数组的第一个字节。`ary`和`ptr`都可以打印出来：

```cpp
char ary[] = "Hello";
char *ptr = "Hello";
// Print out address and contents
printf("%p : %s\n", ary, ary);
printf("%p : %s\n", ptr, ptr);
```

数组是可变的，所以我们可以改变它的内容（但要小心不要写超出数组末尾的字节）。幸运的是，“World”不会比“Hello”更长

在这种情况下，char 指针`ptr`指向一些只读内存（静态分配的字符串文字存储的地方），所以我们不能改变这些内容。

```cpp
strcpy(ary, "World"); // OK
strcpy(ptr, "World"); // NOT OK - Segmentation fault (crashes)

```

然而，与数组不同的是，我们可以将`ptr`更改为指向另一块内存，

```cpp
ptr = "World"; // OK!
ptr = ary; // OK!
ary = (..anything..) ; // WONT COMPILE
// ary is doomed to always refer to the original array.
printf("%p : %s\n", ptr, ptr);
strcpy(ptr, "World"); // OK because now ptr is pointing to mutable memory (the array)
```

从中可以得出的结论是指针*可以指向任何类型的内存，而 C 数组[]只能指向堆栈上的内存。在更常见的情况下，指针将指向堆内存，这种情况下指针引用的内存是可以修改的。

## `sizeof()`返回字节数。所以使用上面的代码，`ary`和`ptr`的`sizeof()`分别是多少？

`sizeof(ary)`: `ary`是一个数组。返回整个数组所需的字节数（5 个字符+零字节=6 个字节）`sizeof(ptr)`: 与`sizeof(char *)`相同。返回指针所需的字节数（例如 32 位或 64 位机器的 4 或 8）

`sizeof`是一个特殊的运算符。实际上，它是编译程序之前编译器替换的东西，因为所有类型的大小在编译时是已知的。当你有`sizeof(char*)`时，它会获取你的机器上指针的大小（64 位机器为 8 字节，32 位机器为 4 字节等）。当你尝试`sizeof(char[])`时，编译器会查看并替换整个数组包含的字节数，因为数组的总大小在编译时是已知的。

```cpp
char str1[] = "will be 11";
char* str2 = "will be 8";
sizeof(str1) //11 because it is an array
sizeof(str2) //8 because it is a pointer
```

小心，使用 sizeof 获取字符串的长度！

## 以下代码中哪些是不正确的或正确的，为什么？

```cpp
int* f1(int *p) {
    *p = 42;
    return p;
} // This code is correct;
```

```cpp
char* f2() {
    char p[] = "Hello";
    return p;
} // Incorrect!
```

解释：在堆栈上为包含 H，e，l，l，o 和一个空字节即（6）字节的正确大小创建了一个数组 p。这个数组存储在堆栈上，在我们从 f2 返回后就无效了。

```cpp
char* f3() {
    char *p = "Hello";
    return p;
} // OK
```

解释：p 是一个指针。它保存了字符串常量的地址。字符串常量在 f3 返回后仍然保持不变和有效。

```cpp
char* f4() {
    static char p[] = "Hello";
    return p;
} // OK
```

解释：数组是静态的，这意味着它存在于进程的整个生命周期（静态变量不在堆或栈上）。

## 如何查找 C 库调用和系统调用的信息？

使用 man 手册。请注意，man 手册分为几个部分。第二部分=系统调用。第三部分=C 库。网络：谷歌“man7 open” shell：man -S2 open 或 man -S3 printf

## 如何在堆上分配内存？

使用 malloc。还有 realloc 和 calloc。通常与 sizeof 一起使用。例如，足够的空间来容纳 10 个整数

```cpp
int *space = malloc(sizeof(int) * 10);
```

## 这个字符串复制代码有什么问题？

```cpp
void mystrcpy(char*dest, char* src) { 
  // void means no return value 
  while( *src ) { dest = src; src ++; dest++; }  
}
```

在上面的代码中，它只是改变了 dest 指针指向源字符串。而且 nuls 字节没有被复制。这是一个更好的版本 -

```cpp
 while( *src ) { *dest = *src; src ++; dest++; } 
  *dest = *src; 
```

请注意，通常还会看到以下类型的实现，其中包括在表达式测试中执行所有操作，包括复制 nul 字节。

```cpp
  while( (*dest++ = *src++ )) {};
```

## 如何编写一个 strdup 替代品？

```cpp
// Use strlen+1 to find the zero byte... 
char* mystrdup(char*source) {
   char *p = (char *) malloc ( strlen(source)+1 );
   strcpy(p,source);
   return p;
}
```

## 如何在堆上取消分配内存？

使用 free！

```cpp
int *n = (int *) malloc(sizeof(int));
*n = 10;
//Do some work
free(n);
```

## 什么是双重释放错误？如何避免？什么是悬空指针？如何避免？

双重释放错误是当您意外地尝试两次释放相同的分配时发生的。

```cpp
int *p = malloc(sizeof(int));
free(p);

*p = 123; // Oops! - Dangling pointer! Writing to memory we don't own anymore

free(p); // Oops! - Double free!
```

修复首先是编写正确的程序！其次，一旦内存被释放，重置指针是良好的编程习惯。这确保了指针在没有程序崩溃的情况下不能被错误使用。

修复：

```cpp
p = NULL; // Now you can't use this pointer by mistake
```

## 缓冲区溢出的一个例子是什么？

著名的例子：心脏出血（将一个 memcpy 复制到一个不足大小的缓冲区）。简单的例子：实现一个 strcpy 并忘记在确定所需内存大小时添加一个 strlen。

## “typedef”是什么，你如何使用它？

声明类型的别名。通常与结构一起使用，以减少必须将“struct”写为类型的一部分的视觉混乱。

```cpp
typedef float real; 
real gravity = 10;
// Also typedef gives us an abstraction over the underlying type used. 
// For example in the future we only need to change this typedef if we
// wanted our physics library to use doubles instead of floats.

typedef struct link link_t; 
//With structs, include the keyword 'struct' as part of the original types
```

在这个课程中，我们经常使用 typedef 函数。例如，函数的 typedef 可以是这样的

```cpp
typedef int (*comparator)(void*,void*);

int greater_than(void* a, void* b){
    return a > b;
}
comparator gt = greater_than;
```

这声明了一个接受两个`void*`参数并返回整数的比较器函数类型。

## 哇，这是很多 C 的内容

别担心，还有更多要来的！

[下一步：C 编程，第二部分：文本输入和输出](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-2%3A-Text-Input-And-Output)
