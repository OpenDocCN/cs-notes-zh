# C 编程，第三部分：常见陷阱

C 程序员常犯哪些常见错误？

## 内存错误

## 字符串常量是常量

```cpp
char array[] = "Hi!"; // array contains a mutable copy 
strcpy(array, "OK");

char *ptr = "Can't change me"; // ptr points to some immutable memory
strcpy(ptr, "Will not work");
```

字符串文字是存储在程序的代码段中的字符数组，是不可变的。两个字符串文字可能共享内存中的相同空间。以下是一个例子：

```cpp
char * str1 = "Brandon Chong is the best TA";
char * str2 = "Brandon Chong is the best TA";
```

由`str1`和`str2`指向的字符串实际上可能驻留在内存中的相同位置。

但是，char 数组包含了从代码段复制到堆栈或静态内存中的文字值。以下 char 数组不驻留在内存中的相同位置。

```cpp
char arr1[] = "Brandon Chong didn't write this";
char arr2[] = "Brandon Chong didn't write this";
```

## 缓冲区溢出/下溢

```cpp
#define N (10)
int i = N, array[N];
for( ; i >= 0; i--) array[i] = i;
```

C 语言不检查指针是否有效。上面的例子写入了`array[10]`，这超出了数组边界。这可能会导致内存损坏，因为该内存位置可能正在用于其他用途。实际上，这可能更难发现，因为溢出/下溢可能发生在库调用中。

```cpp
gets(array); // Let's hope the input is shorter than my array!
```

## 返回指向自动变量的指针

```cpp
int *f() {
    int result = 42;
    static int imok;
    return &imok; // OK - static variables are not on the stack
    return &result; // Not OK
}
```

自动变量仅绑定到函数的堆栈内存，函数的生命周期结束后继续使用内存是错误的。

## 内存分配不足

```cpp
struct User {
   char name[100];
};
typedef struct User user_t;

user_t *user = (user_t *) malloc(sizeof(user));
```

在上面的例子中，我们需要为结构体分配足够的字节。相反，我们分配了足够的字节来容纳一个指针。一旦我们开始使用用户指针，就会破坏内存。正确的代码如下所示。

```cpp
struct User {
   char name[100];
};
typedef struct User user_t;

user_t * user = (user_t *) malloc(sizeof(user_t));
```

#### 字符串需要`strlen(s)+1`字节

每个字符串在最后一个字符后必须有一个空字节。存储字符串`"Hi"`需要 3 个字节：`[H] [i] [\0]`。

```cpp
  char *strdup(const char *input) {  /* return a copy of 'input' */
    char *copy;
    copy = malloc(sizeof(char*));     /* nope! this allocates space for a pointer, not a string */
    copy = malloc(strlen(input));     /* Almost...but what about the null terminator? */
    copy = malloc(strlen(input) + 1); /* That's right. */
    strcpy(copy, input);   /* strcpy will provide the null terminator */
    return copy;
}
```

## 使用未初始化的变量

```cpp
int myfunction() {
  int x;
  int y = x + 2;
...
```

自动变量保存垃圾（内存中发生的任何位模式）。假设它总是初始化为零是错误的。

## 假设未初始化的内存将被清零

```cpp
void myfunct() {
   char array[10];
   char *p = malloc(10);
```

自动（临时变量）不会自动初始化为零。使用 malloc 进行堆分配不会自动初始化为零。

## 双重释放

```cpp
  char *p = malloc(10);
  free(p);
//  .. later ...
  free(p); 
```

多次释放同一块内存是错误的。

## 悬空指针

```cpp
  char *p = malloc(10);
  strcpy(p, "Hello");
  free(p);
//  .. later ...
  strcpy(p,"World"); 
```

不应使用指向释放内存的指针。一种防御性编程实践是在释放内存后立即将指针设置为 null。

将免费转换为以下片段是一个好主意，它会自动将释放的变量设置为 null：（vim - ultisnips）

```cpp
snippet free "free(something)" b
free(${1});
$1 = NULL;
${2}
endsnippet
```

## 逻辑和程序流错误

## 忘记 break

```cpp
int flag = 1; // Will print all three lines.
switch(flag) {
  case 1: printf("I'm printed\n");
  case 2: printf("Me too\n");
  case 3: printf("Me three\n");
}
```

没有 break 的 case 语句将继续执行下一个 case 语句的代码。正确的代码如下所示。最后一个语句的 break 是不必要的，因为在最后一个语句之后没有更多的要执行的情况。但是，如果添加了更多的情况，可能会导致一些错误。

```cpp
int flag = 1; // Will print only "I'm printed\n"
switch(flag) {
  case 1: 
    printf("I'm printed\n");
    break;
  case 2: 
    printf("Me too\n");
    break;
  case 3: 
    printf("Me three\n");
    break; //unnecessary
}
```

## 等号和相等

```cpp
int answer = 3; // Will print out the answer.
if (answer = 42) { printf("I've solved the answer! It's %d", answer);}
```

## 未声明或错误声明的函数

```cpp
time_t start = time();
```

系统函数'time'实际上需要一个参数（一个指向可以接收 time_t 结构的一些内存的指针）。编译器没有捕获到这个错误，因为程序员没有通过包含`time.h`提供有效的函数原型。

## 额外的分号

```cpp
for(int i = 0; i < 5; i++) ; printf("I'm printed once");
while(x < 10); x++ ; // X is never incremented
```

然而，以下代码是完全可以的。

```cpp
for(int i = 0; i < 5; i++){
    printf("%d\n", i);;;;;;;;;;;;;
}
```

这种代码是可以的，因为 C 语言使用分号（;）来分隔语句。如果分号之间没有语句，那么就没有要做的事情，编译器会继续执行下一条语句。

## 其他陷阱

## 预处理器

预处理器是什么？它是编译器在**实际编译**程序之前执行的操作。它是一个复制和粘贴命令。这意味着如果我做以下操作。

```cpp
#define MAX_LENGTH 10
char buffer[MAX_LENGTH]
```

预处理后，它会变成这样。

```cpp
char buffer[10]
```

## C 预处理宏和副作用

```cpp
#define min(a,b) ((a)<(b) ? (a) : (b))
int x = 4;
if(min(x++, 100)) printf("%d is six", x);
```

宏是简单的文本替换，因此上面的例子会扩展为`x++ < 100 ? x++ : 100`（为了清晰起见省略了括号）

## C 预处理宏和优先级

```cpp
#define min(a,b) a<b ? a : b
int x = 99;
int r = 10 + min(99, 100); // r is 100!
```

宏是简单的文本替换，因此上面的例子会扩展为`10 + 99 < 100 ? 99 : 100`

## C 预处理逻辑陷阱

```cpp
#define ARRAY_LENGTH(A) (sizeof((A)) / sizeof((A)[0]))
int static_array[10]; // ARRAY_LENGTH(static_array) = 10
int* dynamic_array = malloc(10); // ARRAY_LENGTH(dynamic_array) = 2 or 1
```

宏有什么问题？如果我们有一个像第一个数组那样的静态数组，它就能工作，因为静态数组的 sizeof 返回数组占用的字节数，将其除以 sizeof(an_element)将给出条目的数量。但是，如果我们使用指向内存块的指针，取指针的 sizeof 并将其除以第一个条目的大小并不总是会给出数组的大小。

## `sizeof` 有什么作用吗？

```cpp
int a = 0;
size_t size = sizeof(a++);
printf("size: %lu, a: %d", size, a);
```

代码打印出什么？

```cpp
size: 4, a: 0 
```

因为 sizeof 实际上不是在运行时评估的。编译器为所有表达式分配类型并丢弃表达式的额外结果。


