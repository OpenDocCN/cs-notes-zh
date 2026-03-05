# 004：指针进阶与泛型函数

![](img/e93c355aafc72fceea3de4511e8935a6_1.png)

在本节课中，我们将要学习 `sizeof` 操作符的更多细节、类型转换的机制，并重点介绍C语言中实现泛型编程的核心概念——`void*` 指针。我们将了解如何编写和使用可以处理多种数据类型的通用函数。

## `sizeof` 操作符详解

上一节我们介绍了指针和内存的基础知识，本节中我们来看看 `sizeof` 操作符的一些特殊用法。

`sizeof` 可以返回一个变量或类型在内存中所占的字节数。其返回值类型为 `size_t`，打印时使用格式说明符 `%zu`。

```c
int i = 107;
double d = 3.14159;
int* ip = &i;
char* cp = "hello";

printf("sizeof(i) = %zu\n", sizeof(i)); // 输出 4
printf("sizeof(d) = %zu\n", sizeof(d)); // 输出 8
printf("sizeof(ip) = %zu\n", sizeof(ip)); // 输出 8
printf("sizeof(cp) = %zu\n", sizeof(cp)); // 输出 8
```

对于在栈上声明的数组，`sizeof` 有一个特殊行为：它可以返回整个数组占用的总字节数。

```c
int arr[3] = {10, 20, 30};
size_t total_bytes = sizeof(arr); // total_bytes = 12
size_t element_size = sizeof(arr[0]); // element_size = 4
int element_count = total_bytes / element_size; // element_count = 3
```

然而，这个特性**仅限于在声明该数组的同一函数内部使用**。一旦将数组作为参数传递给另一个函数，它就会退化为指针，此时 `sizeof` 返回的将是指针本身的大小（例如8字节），而不是数组的总大小。

```c
void size_params(int arr[], int* ptr) {
    // 在函数内部，arr 和 ptr 都是指针
    printf("sizeof(arr) = %zu\n", sizeof(arr)); // 输出 8
    printf("sizeof(ptr) = %zu\n", sizeof(ptr)); // 输出 8
}
```

因此，除了栈数组这一特例外，我们通常无法通过数组本身获知其长度，必须额外传递一个表示元素数量的参数。

## 类型转换

接下来，我们探讨类型转换。类型转换告诉编译器将某个值视为另一种类型。

简单的值转换会由编译器执行实际的数值转换。

```c
int i = 107;
float f = 3.14159;
float cast_i = (float)i; // cast_i = 107.0
int cast_f = (int)f; // cast_f = 3 (截断小数部分)
```

更复杂（也更危险）的是指针类型的转换。这不会改变内存中的原始数据，只是改变了编译器解释这些数据的方式。

```c
int i = 107;
float f = 3.14159;
float* fp = (float*)&i; // 将 int* 强制转换为 float*
int* ip = (int*)&f; // 将 float* 强制转换为 int*

printf("*fp = %f\n", *fp); // 输出一个无意义的值（非107.0）
printf("*ip = %d\n", *ip); // 输出一个无意义的大数字（非3）
```

这种指针类型转换非常危险，因为它绕过了编译器的类型检查。除非你确切知道自己在做什么，否则应避免使用。我们将在后续课程中解释这些“无意义”数值的来源。

## 引入泛型函数

现在，让我们进入本节课的核心主题：泛型函数。泛型函数是指能够操作多种数据类型的函数。

设想我们需要编写多个功能相同但类型不同的函数，例如计算数组中某个元素出现次数的函数：

```c
int count_int(int key, int array[], int n);
int count_float(float key, float array[], int n);
int count_char(char key, char array[], int n);
```

这些函数的代码逻辑几乎完全相同，只是参数类型不同。复制粘贴代码是糟糕的风格，并且难以维护。我们希望有一个统一的函数来处理所有类型。

## `void*`：指向“任意类型”的指针

在C语言中，实现泛型的关键是 `void*` 指针。`void*` 是一种通用指针类型，可以指向任何类型的数据。

*   **赋值**：可以将任何类型的指针（如 `int*`, `char*`）直接赋值给 `void*` 变量，无需强制转换。
*   **限制**：不能对 `void*` 指针进行**解引用**或**指针算术运算**，因为编译器不知道它指向的数据类型和大小。

## 构建泛型函数：`gcount`

为了编写一个通用的计数函数 `gcount`，我们需要解决几个问题：

1.  **传递数组**：使用 `void* arr` 参数来接收指向任何类型数组的指针。
2.  **传递元素大小**：增加一个 `size_t elem_size` 参数，告诉函数每个数组元素占多少字节。这样函数才能在内存中正确“步进”到下一个元素。
3.  **传递键值**：泛型函数不能直接操作数据值，只能操作指针。因此，我们需要传递一个指向键值的指针 `const void* key`，而不是键值本身。

以下是 `gcount` 的原型：

```c
int gcount(const void* key, const void* arr, int n, size_t elem_size);
```

作为客户端，我们这样调用它来统计整数数组：

```c
int scores[] = {85, 92, 76, 92, 95, 92};
int score_key = 92;
int n = sizeof(scores) / sizeof(scores[0]); // 计算元素个数

// 注意：传递的是 &score_key（指针），而不是 score_key（值）
int count = gcount(&score_key, scores, n, sizeof(scores[0]));
```

调用时，我们必须非常小心地确保传递的 `key` 指针类型正确。例如，如果数组元素是 `char*`（字符串），那么 `key` 应该是 `char**`（指向字符串指针的指针）。

```c
char* words[] = {"ABC", "DEF", "ABC"};
char* word_key = "ABC";
// 正确：words[0] 的类型是 char*，所以指向它的指针是 char**
count = gcount(&word_key, words, 3, sizeof(words[0]));
// 这比较的是指针地址是否相同，而非字符串内容是否相同
```

## 标准库中的泛型函数：`qsort`

C标准库提供了强大的泛型函数，如快速排序 `qsort` 和二分查找 `bsearch`。

`qsort` 的原型如下：

```c
void qsort(void* base, size_t nmemb, size_t size,
           int (*compar)(const void*, const void*));
```

参数说明：
*   `base`: 待排序数组的起始地址 (`void*`)。
*   `nmemb`: 数组元素个数。
*   `size`: 每个元素的大小。
*   `compar`: **函数指针**，指向一个比较函数。

`qsort` 函数本身不知道如何比较我们自定义类型的元素。因此，我们需要自己提供一个比较函数，`qsort` 会在排序过程中调用它。这被称为**回调函数**。

比较函数的原型必须严格定义为：
```c
int compare_func(const void* a, const void* b);
```

它接收两个指向待比较元素的 `const void*` 指针，并返回：
*   负数：如果 `a` 应排在 `b` 之前。
*   零：如果 `a` 等于 `b`。
*   正数：如果 `a` 应排在 `b` 之后。

例如，为整数数组编写比较函数：

```c
int compare_ints(const void* a, const void* b) {
    // 1. 将 void* 转换为我们已知的实际类型 int*
    const int* ia = (const int*)a;
    const int* ib = (const int*)b;
    // 2. 解引用并比较值
    return (*ia - *ib); // 升序排序
}

// 使用 qsort
int arr[] = {5, 2, 8, 1, 9};
int n = sizeof(arr) / sizeof(arr[0]);
qsort(arr, n, sizeof(arr[0]), compare_ints);
```

通过改变比较函数内部的逻辑，我们可以轻松实现降序排序、按结构体的某个字段排序等复杂需求，这正是泛型结合回调函数的强大之处。

## 总结

本节课中我们一起学习了：
1.  `sizeof` 操作符对于栈数组的特殊行为，以及其在函数参数中的局限性。
2.  类型转换，特别是危险的指针类型转换，它改变了编译器对数据的解释方式。
3.  泛型函数的概念及其必要性。
4.  使用 `void*` 指针作为实现泛型的基础，它可以指向任何数据，但不能直接解引用或进行算术运算。
5.  如何作为客户端调用泛型函数（如 `gcount`），关键点是传递元素大小和指向键值的指针。
6.  标准库泛型函数 `qsort` 的用法，以及如何编写回调函数来定义自定义的比较逻辑。

![](img/e93c355aafc72fceea3de4511e8935a6_3.png)

理解 `void*` 和回调函数是掌握C语言高级编程和系统编程的关键。在接下来的实验和课程中，我们将获得更多实践机会。