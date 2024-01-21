# 内存，第三部分：破坏堆栈示例

每个线程使用堆栈内存。堆栈“向下增长” - 如果一个函数调用另一个函数，那么堆栈会扩展到更小的内存地址。堆栈内存包括非静态自动（临时）变量，参数值和返回地址。如果缓冲区太小，一些数据（例如来自用户的输入值），那么其他堆栈变量甚至返回地址可能会被覆盖。堆栈内容的精确布局和自动变量的顺序取决于体系结构和编译器。然而，通过一些调查工作，我们可以学会如何故意破坏特定体系结构的堆栈。

下面的示例演示了返回地址存储在堆栈上的方式。对于特定的 32 位体系结构[Live Linux Machine](http://cs-education.github.io/sys/)，我们确定返回地址存储在自动变量地址的两个指针（8 字节）以上的地址。代码故意改变堆栈值，以便当输入函数返回时，不是继续在主方法内部进行，而是跳转到利用函数。

```cpp
// Overwrites the return address on the following machine:
// http://cs-education.github.io/sys/
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

void breakout() {
    puts("Welcome. Have a shell...");
    system("/bin/sh");
}
void input() {
  void *p;
  printf("Address of stack variable: %p\n", &p);
  printf("Something that looks like a return address on stack: %p\n", *((&p)+2));
  // Let's change it to point to the start of our sneaky function.
  *((&p)+2) = breakout;
}
int main() {
    printf("main() code starts at %p\n",main);

    input();
    while (1) {
        puts("Hello");
        sleep(1);
    }

    return 0;
}
```

计算机通常有[很多种](https://en.wikipedia.org/wiki/Stack_buffer_overflow)方法来解决这个问题。
