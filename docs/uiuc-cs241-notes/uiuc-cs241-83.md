# C 编程：复习问题

## 警告-问题编号可能会更改

## 内存和字符串

## 问题 1.1

在下面的示例中，哪些变量保证打印零值？

```cpp
int a;
static int b;

void func() {
   static int c;
   int d;
   printf("%d %d %d %d\n",a,b,c,d);
}
```

## 问题 1.2

在下面的示例中，哪些变量保证打印零值？

```cpp
void func() {
   int* ptr1 = malloc( sizeof(int) );
   int* ptr2 = realloc(NULL, sizeof(int) );
   int* ptr3 = calloc( 1, sizeof(int) );
   int* ptr4 = calloc( sizeof(int) , 1);

   printf("%d %d %d %d\n",*ptr1,*ptr2,*ptr3,*ptr4);
}
```

## 问题 1.3

解释下面尝试复制字符串的错误。

```cpp
char* copy(char*src) {
 char*result = malloc( strlen(src) ); 
 strcpy(result, src); 
 return result;
}
```

## 问题 1.4

为什么下面尝试复制字符串的尝试有时成功有时失败？

```cpp
char* copy(char*src) {
 char*result = malloc( strlen(src) +1 ); 
 strcat(result, src); 
 return result;
}
```

## 问题 1.4

解释下面的代码中尝试复制字符串的两个错误。

```cpp
char* copy(char*src) {
 char result[sizeof(src)]; 
 strcpy(result, src); 
 return result;
}
```

## 问题 1.5

以下哪个是合法的？

```cpp
char a[] = "Hello"; strcpy(a, "World");
char b[] = "Hello"; strcpy(b, "World12345", b);
char* c = "Hello"; strcpy(c, "World");
```

## 问题 1.6

完成函数指针 typedef 以声明一个接受 void*参数并返回 void*的函数指针。将您的类型命名为'pthread_callback'

```cpp
typedef ______________________;
```

## 问题 1.7

除了函数参数之外，线程的堆栈上还存储了什么？

## 问题 1.8

使用`strcpy` `strlen`和指针算术实现`char* strcat(char*dest, const char*src)`的版本

```cpp
char* mystrcat(char*dest, const char*src) {

  ? Use strcpy strlen here

  return dest;
}
```

## 问题 1.9

使用循环和无函数调用实现`size_t strlen(const char*)`的版本。

```cpp
size_t mystrlen(const char*s) {

}
```

## 问题 1.10

识别以下`strcpy`实现中的三个错误。

```cpp
char* strcpy(const char* dest, const char* src) {
  while(*src) { *dest++ = *src++; }
  return dest;
}
```

## 打印

## 问题 2.1

找出两个错误！

```cpp
fprintf("You scored 100%"); 
```

## 格式化和打印到文件

## 问题 3.1

完成以下代码以打印到文件。将名称、逗号和分数打印到文件'result.txt'

```cpp
char* name = .....;
int score = ......
FILE *f = fopen("result.txt",_____);
if(f) {
    _____
}
fclose(f);
```

## 打印到字符串

## 问题 4.1

如何将变量 a，mesg，val 和 ptr 的值打印到一个字符串？将 a 打印为整数，mesg 打印为 C 字符串，val 打印为双精度值，ptr 打印为十六进制指针。您可以假设 mesg 指向一个短的 C 字符串（<50 个字符）。奖励：如何使这段代码更健壮或能够应对？

```cpp
char* toString(int a, char*mesg, double val, void* ptr) {
   char* result = malloc( strlen(mesg) + 50);
    _____
   return result;
}
```

## 输入解析

## 问题 5.1

为什么应该检查 sscanf 和 scanf 的返回值？

## 问题 5.2

为什么'gets'很危险？

## 问题 5.3

编写一个使用`getline`的完整程序。确保您的程序没有内存泄漏。

## 堆内存

何时使用 calloc 而不是 malloc？何时 realloc 会有用？

（待办事项-将此问题移动到另一页）程序员在下面的代码中犯了什么错误？使用堆内存可以修复吗？使用全局（静态）内存可以修复吗？

```cpp
static int id;

char* next_ticket() {
  id ++;
  char result[20];
  sprintf(result,"%d",id);
  return result;
}
```
