# 073：在没有闭包的情况下使用 C 语言

在本节课中，我们将学习如何将 ML 语言中的列表库移植到 C 语言中。C 语言本身不支持对象或闭包，因此我们需要采用一些高级的 C 语言技巧来实现类似的功能。我们将重点介绍如何使用函数指针和额外的参数来模拟闭包的行为，并处理 C 语言中缺乏泛型的问题。

## 移植列表库到 C 语言

上一节我们介绍了课程的目标。本节中，我们来看看如何在 C 语言中定义基本的列表类型和辅助函数。

首先，我们定义一个通用的列表类型。由于 C 语言没有泛型，我们使用 `void*` 类型来存储列表元素。

```c
typedef struct list {
    void* head;
    struct list* tail;
} list;

list* cons(void* head, list* tail) {
    list* ans = (list*)malloc(sizeof(list));
    ans->head = head;
    ans->tail = tail;
    return ans;
}
```
在这个定义中，`list` 结构体包含一个指向任意类型数据的 `head` 指针和一个指向下一个列表节点的 `tail` 指针。`cons` 函数用于构造新的列表节点，它分配内存并初始化字段。我们使用 `NULL` 来表示空列表。

![](img/72567dfaabc2794f5ed841177f94b753_1.png)

## 实现 Map、Filter 和 Length 函数

现在我们已经定义了列表结构，接下来需要实现 `map`、`filter` 和 `length` 这三个核心函数。由于 C 语言没有闭包，我们需要调整函数签名。

以下是 `map` 函数的实现。关键点在于，传递给 `map` 的函数指针需要接收一个额外的“环境”参数。

```c
list* map(void* (*f)(void*, void*), void* env, list* x) {
    if (x == NULL) {
        return NULL;
    } else {
        return cons(f(env, x->head), map(f, env, x->tail));
    }
}
```
`map` 函数接收一个函数指针 `f`、一个环境参数 `env` 和一个列表 `x`。函数 `f` 的类型是 `void* (*)(void*, void*)`，这意味着它接受两个 `void*` 参数（环境和列表元素）并返回一个 `void*`。递归地，`map` 对列表的每个元素应用函数 `f`，并使用 `cons` 构建新列表。

`filter` 函数的实现遵循类似的模式，但函数指针返回一个布尔值（或整型）来决定是否保留元素。

```c
list* filter(int (*f)(void*, void*), void* env, list* x) {
    if (x == NULL) {
        return NULL;
    } else if (f(env, x->head)) {
        return cons(x->head, filter(f, env, x->tail));
    } else {
        return filter(f, env, x->tail);
    }
}
```
`filter` 函数接收一个谓词函数 `f`、环境 `env` 和列表 `x`。如果 `f` 对当前元素返回真（非零），则该元素被包含在新列表中。

对于 `length` 函数，由于不需要函数指针，我们可以使用更传统的迭代方法。

```c
int length(list* x) {
    int ans = 0;
    while (x != NULL) {
        ans++;
        x = x->tail;
    }
    return ans;
}
```
这个函数使用一个 `while` 循环遍历列表，计数节点数量。

## 函数指针与额外参数的重要性

上一节我们实现了库函数。本节中，我们来深入理解为什么函数指针需要额外参数，以及这在 C 语言编程中为何是一种通用模式。

在 C 语言中，函数指针本身只包含代码，不包含定义时的环境（即闭包的数据部分）。因此，为了模拟闭包，我们必须手动传递环境数据。通用的做法是让所有作为参数传递的函数都接受一个额外的 `void*` 参数，用于接收这个环境。调用方（如 `map` 或 `filter`）负责在每次调用时将这个环境传递回去。

这种做法虽然需要大量的类型转换，但它是实现可复用回调函数和模拟高阶函数功能的基石。即使在某些不需要环境数据的简单情况下（例如一个简单的加倍函数），我们也应该遵循这个模式以保持接口一致。

## 客户端代码示例

理解了库的实现原理后，现在我们来看看如何使用这个库。客户端代码需要处理大量的类型转换。

![](img/72567dfaabc2794f5ed841177f94b753_3.png)

首先是一个使用 `map` 函数将列表中所有整数加倍的例子。

```c
void* double_int(void* ignore, void* i) {
    // 将 void* 转换为 int*，解引用，计算，再转换回 void*
    int val = *((int*)i);
    int* ans = (int*)malloc(sizeof(int));
    *ans = val * 2;
    return (void*)ans;
}

list* double_all(list* lst) {
    // 调用 map，对于不需要环境的函数，环境参数传递 NULL
    return map(double_int, NULL, lst);
}
```
`double_int` 函数忽略其环境参数 `ignore`。它首先将元素指针 `i` 转换为 `int*` 以获取整数值，计算加倍后的值，分配新内存存储结果，最后将结果指针转换回 `void*` 返回。

![](img/72567dfaabc2794f5ed841177f94b753_5.png)

接下来是一个更复杂的例子，它使用 `filter` 和 `length` 来计算列表中等于某个值 `n` 的元素数量，这模拟了 ML 中需要从闭包环境捕获 `n` 的情况。

```c
int is_n(void* env, void* i) {
    // 将环境（要查找的值 n）和列表元素都转换为 int 进行比较
    int n = *((int*)env);
    int val = *((int*)i);
    return n == val;
}

int count_n(int n, list* lst) {
    // 为环境参数分配内存并存储 n 的值
    int* env = (int*)malloc(sizeof(int));
    *env = n;
    // 调用 filter，传递环境指针
    list* filtered = filter(is_n, (void*)env, lst);
    int ans = length(filtered);
    // 释放环境内存
    free(env);
    // 注意：这里简化了，实际还需要释放 filtered 列表占用的内存
    return ans;
}
```
在 `count_n` 函数中，我们动态分配了一个整数内存来存储要查找的值 `n`，并将其作为环境指针传递给 `filter`。在 `is_n` 函数内部，我们将环境和列表元素指针都转换回 `int*` 进行比较。使用完毕后，需要记得释放为环境分配的内存。

![](img/72567dfaabc2794f5ed841177f94b753_7.png)

## 总结与最佳实践

本节课中我们一起学习了如何在缺乏闭包支持的 C 语言中模拟高阶函数的功能。

我们实现了一个简单的通用列表库，包含 `map`、`filter` 和 `length` 函数。核心技巧是让所有作为参数传递的函数指针都接受一个额外的 `void*` 类型环境参数，并由调用方负责传递该环境。这允许函数访问其所需的“私有”数据，从而模拟了闭包的行为。同时，由于 C 语言没有泛型，我们不得不大量使用 `void*` 类型和显式的类型转换。

这种模式在 C 语言的回调接口设计中非常常见。记住以下最佳实践：
*   **设计库时**：如果您的接口接受函数指针作为回调，请总是为其添加一个 `void*` 环境参数。
*   **使用库时**：如果看到回调函数有 `void*` 环境参数，请利用它来传递您回调函数所需的数据。
*   **类型安全**：频繁的 `void*` 转换会绕过编译器的类型检查，因此需要格外小心以确保类型的正确性。

虽然这个过程有些繁琐，但它清晰地展示了拥有自动管理闭包的语言（如 ML、Java、C# 等）所带来的便利性。通过手动管理环境和类型，我们在 C 语言中实现了类似的功能。