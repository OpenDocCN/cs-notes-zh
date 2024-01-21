# C 编程，复习问题

## 主题

+   C 字符串表示

+   C 字符串作为指针

+   char p[]vs char* p

+   简单的 C 字符串函数（strcmp，strcat，strcpy）

+   sizeof char

+   sizeof x vs x*

+   堆内存寿命

+   堆分配调用

+   解引用指针

+   取地址运算符

+   指针算术

+   字符串复制

+   字符串截断

+   双重释放错误

+   字符串字面值

+   打印格式。

+   内存越界错误

+   静态内存

+   fileio POSIX v C 库

+   C io fprintf 和 printf

+   POSIX 文件 io（读|写|打开）

+   stdout 的缓冲

## 问题/练习

+   以下打印出什么

```cpp
int main(){
    fprintf(stderr, "Hello ");
    fprintf(stdout, "It's a small ");
    fprintf(stderr, "World\n");
    fprintf(stdout, "place\n");
    return 0;
}
```

+   以下两个声明之间有什么区别？其中一个的`sizeof`返回什么？

```cpp
char str1[] = "bhuvan";
char *str2 = "another one";
```

+   C 中的字符串是什么？

+   编写一个简单的`my_strcmp`。`my_strcat`，`my_strcpy`或`my_strdup`呢？奖励：只通过字符串*一次*编写函数。

+   以下通常应该返回什么？

```cpp
int *ptr;
sizeof(ptr);
sizeof(*ptr);
```

+   什么是`malloc`？它与`calloc`有什么不同。一旦内存被`malloc`，我如何使用`realloc`？

+   `&`运算符是什么？`*`呢？

+   指针算术。假设以下地址。以下移位是什么？

```cpp
char** ptr = malloc(10); //0x100
ptr[0] = malloc(20); //0x200
ptr[1] = malloc(20); //0x300
```

```cpp
 * `ptr + 2`
 * `ptr + 4`
 * `ptr[0] + 4`
 * `ptr[1] + 2000`
 * `*((int)(ptr + 1)) + 3` 
```

+   我们如何防止双重释放错误？

+   打印字符串，`int`或`char`的 printf 格式说明符是什么？

+   以下代码有效吗？如果是，为什么？`output`位于哪里？

```cpp
char *foo(int var){
    static char output[20];
    snprintf(output, 20, "%d", var);
    return output;
}
```

+   编写一个接受字符串并打开该文件的函数，每次打印出文件的 40 个字节，但每隔一次打印都会颠倒字符串（尝试使用 POSIX API 实现）。

+   POSIX 文件描述符模型和 C 的`FILE*`之间有哪些区别（即使用了哪些函数调用，哪个是缓冲的）？POSIX 内部使用 C 的`FILE*`还是反之亦然？

[返回：C 编程，第五部分：调试](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-5%3A-Debugging)
