# C 编程，第二部分：文本输入和输出

## 打印到流

## 如何将字符串、整数、字符打印到标准输出流中？

使用 `printf`。第一个参数是格式字符串，其中包括要打印的数据的占位符。常见的格式说明符是 `%s` 将参数视为 C 字符串指针，一直打印到达到 NULL 字符为止；`%d` 将参数打印为整数；`%p` 将参数打印为内存地址。

下面显示了一个简单的示例：

```cpp
char *name = ... ; int score = ...;
printf("Hello %s, your result is %d\n", name, score);
printf("Debug: The string and int are stored at: %p and %p\n", name, &score );
// name already is a char pointer and points to the start of the array. 
// We need "&" to get the address of the int variable
```

默认情况下，为了性能，`printf` 实际上并不会写任何东西（通过调用 write），直到它的缓冲区满或打印换行符。

## 我还可以如何打印字符串和单个字符？

使用 `puts( name );` 和 `putchar( c )`，其中 name 是指向 C 字符串的指针，c 只是一个 `char`

## 如何将内容打印到其他文件流中？

使用 `fprintf( _file_ , "Hello %s, score: %d", name, score);` 其中 _file_ 是预定义的 'stdout' 'stderr' 或者是由 `fopen` 或 `fdopen` 返回的 FILE 指针

## 我可以使用文件描述符吗？

是的！只需使用 `dprintf(int fd, char* format_string, ...);` 只需记住流可能是缓冲的，所以您需要确保数据被写入文件描述符。

## 如何将数据打印到 C 字符串中？

使用 `sprintf` 或更好的 `snprintf`。

```cpp
char result[200];
int len = snprintf(result, sizeof(result), "%s:%d", name, score);
```

snprintf 返回写入的字符数，不包括终止字节。在上面的示例中，这将是最多 199 个。

## 如果我真的非常想要 `printf` 调用 `write` 而不换行怎么办？

使用 `fflush( FILE* inp )`。文件的内容将被写入。如果我想要写入 "Hello World" 而不换行，我可以这样写。

```cpp
int main(){
    fprintf(stdout, "Hello World");
    fflush(stdout);
    return 0;
}
```

## `perror` 有什么帮助？

假设您有一个函数调用刚刚失败了（因为您检查了 man 页面并且它是一个失败的返回代码）。`perror(const char* message)` 将把错误的英文版本打印到 stderr

```cpp
int main(){
    int ret = open("IDoNotExist.txt", O_RDONLY);
    if(ret < 0){
        perror("Opening IDoNotExist:");
    }
    //...
    return 0;
}
```

## 解析输入

## 如何从字符串中解析数字？

使用 `long int strtol(const char *nptr, char **endptr, int base);` 或 `long long int strtoll(const char *nptr, char **endptr, int base);`。

这些函数的作用是获取指向您的字符串 `*nptr` 和一个 `base`（即二进制、八进制、十进制、十六进制等）以及一个可选的指针 `endptr`，并返回解析的整数。

```cpp
int main(){
    const char *num = "1A2436";
    char* endptr;
    long int parsed = strtol(num, &endptr, 16);
    return 0;
}
```

但要小心！错误处理有点棘手，因为该函数不会返回错误代码。出错时，它将返回 0，您必须手动检查 errno，但这可能会导致麻烦。

```cpp
int main(){
    const char *zero = "0";
    char* endptr;
    printf("Parsing number"); //printf sets errno
    long int parsed = strtol(num, &endptr, 16);
    if(parsed == 0){
        perror("Error: "); //oops strtol actually worked!
    }
    return 0;
}
```

## 如何使用 `scanf` 解析输入为参数？

使用 `scanf`（或 `fscanf` 或 `sscanf`）从默认输入流、任意文件流或 C 字符串中获取输入。检查返回值以查看解析了多少项是个好主意。`scanf` 函数需要有效的指针。将错误的指针值传入是一个常见的错误来源。例如，

```cpp
int *data = (int *) malloc(sizeof(int));
char *line = "v 10";
char type;
// Good practice: Check scanf parsed the line and read two values:
int ok = 2 == sscanf(line, "%c %d", &type, &data); // pointer error
```

我们想要将字符值写入 c，将整数值写入 malloc'd 内存。然而我们传递的是数据指针的地址，而不是指针指向的内容！所以 `sscanf` 将会改变指针本身。也就是说，指针现在将指向地址 10，所以这段代码以后会失败，例如当调用 `free(data)` 时。

## 如何阻止 scanf 导致缓冲区溢出？

以下代码假设 scanf 不会读取超过 10 个字符（包括终止字节）到缓冲区中。

```cpp
char buffer[10];
scanf("%s",buffer);
```

您可以包含一个可选的整数来指定多少个字符，不包括终止字节：

```cpp
char buffer[10];
scanf("%9s", buffer); // reads upto 9 charactes from input (leave room for the 10th byte to be the terminating byte)
```

## 为什么 `gets` 是危险的？我应该用什么代替？

以下代码容易受到缓冲区溢出的影响。它假定或信任输入行不会超过 10 个字符，包括终止字节。

```cpp
char buf[10];
gets(buf); // Remember the array name means the first byte of the array
```

`gets` 在 C99 标准中已被弃用，并且已从最新的 C 标准（C11）中删除。程序应该使用 `fgets` 或 `getline` 代替。

它们分别具有以下结构：

```cpp
char *fgets (char *str, int num, FILE *stream); 

ssize_t getline(char **lineptr, size_t *n, FILE *stream);
```

下面是一种简单、安全的读取单行的方法。超过 9 个字符的行将被截断：

```cpp
char buffer[10];
char *result = fgets(buffer, sizeof(buffer), stdin);
```

如果出现错误或者到达文件末尾，结果将为 NULL。请注意，与`gets`不同，`fgets`会将换行符复制到缓冲区中，您可能希望将其丢弃-

```cpp
if (!result) { return; /* no data - don't read the buffer contents */}

int i = strlen(buffer) - 1;
if (buffer[i] == '\n') 
    buffer[i] = '\0';
```

## 我如何使用`getline`？

`getline`的优点之一是它将自动（重新）分配足够大小的堆上的缓冲区。

```cpp
// ssize_t getline(char **lineptr, size_t *n, FILE *stream);

 /* set buffer and size to 0; they will be changed by getline */
char *buffer = NULL;
size_t size = 0;

ssize_t chars = getline(&buffer, &size, stdin);

// Discard newline character if it is present,
if (chars > 0 && buffer[chars-1] == '\n') 
    buffer[chars-1] = '\0';

// Read another line.
// The existing buffer will be re-used, or, if necessary,
// It will be `free`'d and a new larger buffer will `malloc`'d
chars = getline(&buffer, &size, stdin);

// Later... don't forget to free the buffer!
free(buffer);
```


