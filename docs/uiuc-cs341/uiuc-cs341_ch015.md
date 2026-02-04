# 复习

以下是一个非详尽的主题列表。

## C

### 内存和字符串

1.  在下面的示例中，哪些变量保证打印出零的值？

    ```c
    int a;
    static int b;

    void func() {
     static int c;
     int d;
     printf("%d %d %d %d\n",a,b,c,d);
    }
    ```

1.  在下面的示例中，哪些变量保证打印出零的值？

    ```c
    void func() {
     int* ptr1 = malloc(sizeof(int));
     int* ptr2 = realloc(NULL, sizeof(int));
     int* ptr3 = calloc(1, sizeof(int));
     int* ptr4 = calloc(sizeof(int), 1);

     printf("%d %d %d %d\n",*ptr1,*ptr2,*ptr3,*ptr4);
    }
    ```

1.  解释以下尝试复制字符串的错误。

    ```c
    char* copy(char*src) {
     char*result = malloc( strlen(src) );
     strcpy(result, src);
     return result;
    }
    ```

1.  为什么以下尝试复制字符串有时工作有时失败？

    ```c
    char* copy(char*src) {
     char*result = malloc( strlen(src) +1 );
     strcat(result, src);
     return result;
    }
    ```

1.  解释以下尝试复制字符串的代码中的两个错误。

    ```c
    char* copy(char*src) {
     char result[sizeof(src)];
     strcpy(result, src);
     return result;
    }
    ```

1.  以下哪个是合法的？

    ```c
    char a[] = "Hello"; strcpy(a, "World");
    char b[] = "Hello"; strcpy(b, "World12345", b);
    char* c = "Hello"; strcpy(c, "World");
    ```

1.  完成以下函数指针 typedef，以声明一个接受 void* 参数并返回 void* 的指针。将你的类型命名为“pthread_callback”

    ```c
    typedef ______________________;
    ```

1.  除了函数参数外，线程的堆栈上还存储了什么？

1.  仅使用和指针算术实现一个版本。

    ```c
    char* mystrcat(char*dest, const char*src) {

     ? Use strcpy strlen here

     return dest;
    }
    ```

1.  使用循环和没有函数调用实现 size_t strlen(const char*) 的版本。

    ```c
    size_t mystrlen(const char*s) {

    }
    ```

1.  以下实现中存在三个错误，请识别出来。

    ```c
    char* strcpy(const char* dest, const char* src) {
     while(*src) { *dest++ = *src++; }
     return dest;
    }
    ```

### 打印

1.  找出两个错误！

    ```c
    fprintf("You scored 100%");
    ```

1.  完成以下代码以打印到文件。将姓名、逗号和分数打印到文件“result.txt”

    ```c
    char* name = .....;
    int score = ......
    FILE *f = fopen("result.txt",_____);
    if(f) {
     _____
    }
    fclose(f);
    ```

1.  你会如何将变量、、和的值打印到字符串中？将打印为整数，mesg 作为 C 字符串，val 作为 double val，ptr 作为十六进制指针。你可以假设 mesg 指向一个短 C 字符串（<50 个字符）。加分：你将如何使这段代码更健壮或能够应对？

    ```c
    char* toString(int a, char*mesg, double val, void* ptr) {
     char* result = malloc( strlen(mesg) + 50);
     _____
     return result;
    }
    ```

### 输入解析

1.  为什么你应该检查 sscanf 和 scanf 的返回值？## Q 5.2 为什么‘gets’是危险的？

1.  编写一个完整的程序，使用 。确保你的程序没有内存泄漏。

1.  你会在什么情况下使用 calloc 而不是 malloc？realloc 何时有用？

1.  在以下代码中，程序员犯了什么错误？是否可以修复它？

    i) 使用堆内存？ii) 使用全局（静态）内存？

    ```c
    static int id;

    char* next_ticket() {
     id ++;
     char result[20];
     sprintf(result,"%d",id);
     return result;
    }
    ```

## 进程

1.  什么是进程？

1.  在 fork 时，哪些属性会从进程继承过来？在成功 exec 调用时呢？

1.  什么是 fork 炸弹？我们如何避免它？

1.  wait 系统调用用于什么？

1.  什么是僵尸进程？我们如何避免它们？

1.  什么是孤儿进程？它们会发生什么？

1.  我们如何检查已退出的进程的状态？

1.  进程的常见模式是什么？

## 内存

1.  C 语言中分配内存的调用有哪些？

1.  malloc 分配的内存必须对齐到什么？为什么这很重要？

1.  Knuth 分配方案是什么？

1.  你会如何处理伙伴分配方案中的请求？

1.  什么是空闲列表？

1.  有哪些不同的方法可以将元素插入到空闲列表中？

1.  首次适配、最差适配、最佳适配有什么优点和缺点？

1.  何时一个简单的 malloc 实现是足够的？

    ```c
    void *malloc(int size) {
     return (void *)sbrk(size);
    }
    ```

    是否可接受？

## 线程和同步

1.  什么是线程？线程共享什么？

1.  如何创建一个线程？

1.  线程的堆栈在内存中的位置在哪里？

1.  互斥锁（mutex）是什么？它解决了什么问题？

1.  什么是条件变量？它解决了什么问题？

1.  编写一个线程安全的链表，支持插入前、插入后、弹出前和弹出后。确保它不要忙等待！

1.  Peterson 的临界区问题解决方案是什么？Dekker 的呢？

1.  以下代码是否线程安全？重新设计以下代码以使其线程安全。提示：如果消息内存对每个调用都是唯一的，则不需要互斥锁。

    ```c
    static char message[20];
    pthread_mutex_t mutex = PTHREAD_MUTEX_INITIALIZER;

    void *format(int v) {
     pthread_mutex_lock(&mutex);
     sprintf(message, ":%d:" ,v);
     pthread_mutex_unlock(&mutex);
     return message;
    }
    ```

1.  以下哪个可能导致进程处于运行状态？

    1.  在最后一个运行的线程中从 pthread 的启动函数返回。

    1.  原线程从 main 返回。

    1.  任何导致段错误的线程。

    1.  任何调用。

    1.  在主线程中调用，而其他线程仍在运行。

1.  为以下程序打印的“W”字符数量写一个数学表达式。假设 a、b、c、d 是小的正整数。你的答案可以使用返回其最低值参数的“min”函数。

    ```c
    unsigned int a=...,b=...,c=...,d=...;

    void* func(void* ptr) {
     char m = * (char*)ptr;
     if(m == 'P') sem_post(s);
     if(m == 'W') sem_wait(s);
     putchar(m);
     return NULL;
    }

    int main(int argv, char** argc) {
     sem_init(s,0, a);
     while(b--) pthread_create(&tid, NULL, func, "W");
     while(c--) pthread_create(&tid, NULL, func, "P");
     while(d--) pthread_create(&tid, NULL, func, "W");
     pthread_exit(NULL);
     /*Process will finish when all threads have exited */
    }
    ```

1.  完成以下代码。以下代码本应打印交替的和。它代表两个交替执行的线程。向添加条件变量调用，以便等待的线程不需要不断检查变量。问题：pthread_cond_broadcast 是否必要，还是 pthread_cond_signal 足够？

    ```c
    pthread_cond_t cv = PTHREAD_COND_INITIALIZER;
    pthread_mutex_t m = PTHREAD_MUTEX_INITIALIZER;

    void* turn;

    void* func(void* mesg) {
     while(1) {
     // Add mutex lock and condition variable calls ...

     while(turn == mesg) {
     /* poll again ... Change me - This busy loop burns CPU time! */
     }

     /* Do stuff on this thread */
     puts( (char*) mesg);
     turn = mesg;

     }
     return 0;
    }

    int main(int argc, char** argv){
     pthread_t tid1;
     pthread_create(&tid1, NULL, func, "A");
     func("B"); // no need to create another thread - use the main thread
     return 0;
    }
    ```

1.  识别给定代码中的临界区。添加互斥锁以使代码线程安全。添加条件变量调用，以便永远不会变为负数或超过 1000。相反，调用应该阻塞，直到可以安全进行。解释为什么是必要的。

    ```c
    int total;
    void add(int value) {
     if(value < 1) return;
     total += value;
    }
    void sub(int value) {
     if(value < 1) return;
     total -= value;
    }
    ```

1.  一个线程不安全的数据结构有和方法。使用条件变量和互斥锁来完成线程安全的、阻塞版本。

    ```c
    void enqueue(void* data) {
     // should block if the size() would become greater than 256
     enq(data);
    }
    void* dequeue() {
     // should block if size() is 0
     return deq();
    }
    ```

1.  你的初创公司提供使用最新交通信息的路径规划。你的高薪实习生创建了一个线程不安全的数据结构，其中包含两个函数：（使用但不修改图）和（修改图）。

    ```c
    graph_t* create_graph(char* filename); // called once

    // returns a new heap object that is the shortest path from vertex i to j
    path_t* shortest(graph_t* graph, int i, int j);

    // updates edge from vertex i to j
    void set_edge(graph_t* graph, int i, int j, double time);
    ```

    为了性能，多个线程必须能够同时调用，但图只能由一个线程在没有任何其他线程在或内部执行时修改。

1.  使用互斥锁和条件变量来实现读者-写者解决方案。下面展示了一个不完整的尝试。尽管这个尝试是线程安全的（因此对于演示日来说足够了！），但它不允许多个线程同时计算路径，并且吞吐量将不足。

    ```c
    path_t* shortest_safe(graph_t* graph, int i, int j) {
     pthread_mutex_lock(&m);
     path_t* path = shortest(graph, i, j);
     pthread_mutex_unlock(&m);
     return path;
    }
    void set_edge_safe(graph_t* graph, int i, int j, double dist) {
     pthread_mutex_lock(&m);
     set_edge(graph, i, j, dist);
     pthread_mutex_unlock(&m);
    }
    ```

1.  对于读者-写者问题，以下哪些陈述是正确的？

    +   可以有多个活跃的读者

    +   可以有多个活跃的写者

    +   当有活跃的写者时，活跃的读者数必须为零

    +   如果有活跃的读者，则活跃的写者数必须为零

    +   写者必须等待当前活跃的读者完成

## 死锁

1.  每个 Coffman 条件是什么，它们意味着什么？你能提供每个条件的定义以及使用互斥锁打破它们的例子吗？

1.  给出一个现实生活中的例子，依次打破每个 Coffman 条件。一个需要考虑的情况：画家、颜料和画笔。

    1.  保持和等待

    1.  循环等待

    1.  无抢占

    1.  互斥

1.  确定何时 Dining Philosophers 代码导致死锁（或没有）。例如，如果你看到了以下代码片段，哪个 Coffman 条件没有得到满足？

    ```c
    // Get both locks or none.
    pthread_mutex_lock( a );
    if( pthread_mutex_trylock( b ) ) { /*failed*/
     pthread_mutex_unlock( a );
     ...
    }
    ```

1.  有多少进程被阻塞？

    +   P1 获取 R1

    +   P2 获取 R2

    +   P1 获取 R3

    +   P2 等待 R3

    +   P3 获取 R5

    +   P1 获取 R4

    +   P3 等待 R1

    +   P4 等待 R5

    +   P5 等待 R1

1.  以下 dining philosophers 解决方案的优缺点是什么？

    1.  仲裁者

    1.  Dijkstra

    1.  Stalling’s

    1.  Trylock

## IPC

1.  以下是什么以及它们的目的？

    1.  传输查找缓冲区

    1.  物理地址

    1.  内存管理单元

    1.  污点位

1.  你如何确定页面偏移使用了多少位？

1.  在上下文切换后的 20 毫秒内，TLB 包含了执行主内存访问 100% 的数值代码所使用的所有逻辑地址。与单级页表相比，两级页表的开销（减速）是多少？

1.  解释为什么在发生上下文切换时必须刷新 TLB（即 CPU 被分配到处理不同进程）。

1.  填空以使以下程序打印 123456789。如果没有提供参数，它将简单地打印其输入直到 EOF。加分：解释为什么下面的调用是必要的。

    ```c
    int main() {
     int i = 0;
     while(++i < 10) {
     pid_t pid = fork();
     if(pid == 0) { /* child */
     char buffer[16];
     sprintf(buffer, ______,i);
     int fds[ ______];
     pipe(fds);
     write(fds[1], ______,______ ); // Write the buffer into the pipe
     close(______);
     dup2(fds[0], ______);
     execlp("cat", "cat",  ______);
     perror("exec"); exit(1);
     }
     waitpid(pid, NULL, 0);
     }
     return 0;
    }
    ```

1.  使用 POSIX 调用来实现自动评分程序。将子进程的标准输出捕获到管道中。子进程应该不带任何额外参数（除了进程名称）来运行程序。在父进程中从管道读取：一旦捕获的输出包含 ! 字符，则退出父进程。在退出父进程之前，向子进程发送 SIGKILL 信号。如果输出包含 !，则退出 0。否则，如果子进程退出导致管道的写端关闭，则退出值为 1。确保在父进程和子进程中关闭未使用的管道端。

1.  这个高级挑战使用管道来让一个“AI 玩家”自己玩游戏，直到游戏完成。程序接受一行输入 - 到目前为止的回合顺序，打印相同的顺序后跟另一个回合，然后退出。一个回合由两个字符指定。例如，“A1”和“C3”是两个对角位置。字符串是 3 个回合/走法的游戏。一个有效的响应是（C1 响应阻止了 B2 A3 对角威胁）。输出行还可以包括后缀或使用管道来控制每个创建的子进程的输入和输出。当输出包含 , 时，打印最终输出行（整个游戏顺序和结果）并退出。

1.  编写一个使用 fseek 和 ftell 将文件中间字符替换为 'X' 的函数。

    ```c
    void xout(char* filename) {
     FILE *f = fopen(filename, ____ );

     // Your code here ...
    }
    ```

1.  什么是 MMU？与直接内存系统相比，使用它的缺点是什么？

1.  什么是管道？

1.  命名管道和无名管道之间的优缺点是什么？

## 文件系统

1.  文件 API 是什么？

1.  文件名存储在哪里？

1.  inode 中包含什么？

1.  每个目录中的两个特殊文件名是什么？

1.  你如何解析以下路径

1.  rwx 组是什么？

1.  UID 是什么？GID 是什么？UID 与有效 UID 之间的区别是什么？

1.  什么是 umask？

1.  什么是粘性位？

1.  什么是虚拟文件系统？

1.  什么是 RAID？

1.  在一个文件系统中，为了访问文件的第一字节，需要从磁盘读取多少个 inode？假设根目录中的目录名和 inode 号已经在内存中（但不是 inode 本身）。

1.  在一个文件系统中，为了访问文件的第一字节，必须从磁盘读取多少个磁盘块？假设根目录中的目录名和 inode 号以及所有 inode 都已经存储在内存中。

1.  在一个 32 位地址和 4KiB 磁盘块的文件系统中，inode 可以存储 10 个直接磁盘块号。需要多少最小文件大小才能需要一个单级间接表？ii）一个双级间接表？

1.  修正以下 shell 命令以设置文件的权限，使得所有者可以读写执行权限，组可以读，其他人没有访问权限。

    ```c
    $ chmod 000 secret.txt
    ```

## 网络连接

1.  什么是套接字？

1.  互联网的不同层次是什么？

1.  IP 是什么？IP 地址是什么？

1.  TCP 是什么？UDP 是什么？它们有什么区别？

1.  创建一个 TCP 客户端，向服务器发送“Hello”。

1.  创建一个简单的 TCP 回显服务器。这是一个读取客户端字节直到它关闭并回显字节到客户端的服务器。

1.  创建一个 UDP 客户端，它会向 argv[1]指定的主机发送大量数据包。

1.  什么是 HTTP？

1.  什么是 DNS？

1.  为什么我们在网络中使用非阻塞 I/O？

1.  什么是 RPC？

1.  监听端口 1000 与端口 2000 有什么特别之处？

    +   端口 2000 比端口 1000 慢一倍

    +   端口 2000 比端口 1000 快一倍

    +   端口 1000 需要 root 权限

    +   无

1.  描述 IPv4 和 IPv6 之间一个显著的区别？

1.  在什么情况下以及为什么你会使用 ntohs？

1.  如果主机地址是 32 位，我最有可能是使用哪种 IP 方案？128 位？

1.  哪个常见的网络协议是基于数据包的，可能无法成功交付数据？

1.  哪个常见的协议是基于流的，如果数据包丢失会重新发送数据？

1.  SYN ACK ACK-SYN 握手是什么？

1.  以下哪个不是 TCP 的特性？

    1.  数据包重排序

    1.  流控制

    1.  数据包重传

    1.  简单的错误检测

    1.  加密

1.  哪个协议使用序列号？它们的初始值是什么？为什么？

1.  构建 TCP 服务器需要哪些最小网络调用？它们的正确顺序是什么？

1.  构建 TCP 客户端需要哪些最小网络调用？它们的正确顺序是什么？

1.  在 TCP 客户端上何时调用 bind？

1.  socket bind listen accept 的目的是什么？

1.  哪个调用可能会阻塞，等待新的客户端连接？

1.  什么是 DNS？它为你做了什么？CS241 网络调用中的哪个会为你使用它？

1.  对于 getaddrinfo，你如何指定服务器套接字？

1.  为什么 getaddrinfo 可能会生成网络数据包？

1.  哪个网络调用指定了允许的 backlog 的大小？

1.  哪个网络调用返回一个新的文件描述符？

1.  何时使用被动套接字？

1.  在什么情况下 epoll 比 select 更好？在什么情况下 select 比 epoll 更好？

1.  总是发送 5000 字节数据吗？什么时候可能会失败？

1.  网络地址转换（NAT）是如何工作的？

1.  假设网络在客户端和服务器之间有一个 20 毫秒的单向传输时间，建立 TCP 连接需要多少时间？

    1.  20ms

    1.  40ms

    1.  100ms

    1.  60ms

1.  HTTP 1.0 和 HTTP 1.1 之间有哪些不同之处？如果网络有 20 毫秒的传输时间，从服务器传输 3 个文件到客户端需要多少毫秒？HTTP 1.0 和 HTTP 1.1 之间的时间差异是如何的？

1.  向网络套接字写入可能不会发送所有字节，并且可能会因为信号而中断。检查返回值以实现将反复调用任何剩余数据的函数。如果返回-1，则立即返回-1，除非是-，在这种情况下，重复最后尝试。您将需要使用指针算术。

    ```c
    // Returns -1 if write fails (unless EINTR in which case it recalls write
    // Repeated calls write until all of the buffer is written.
    ssize_t write_all(int fd, const char *buf, size_t nbyte) {
     ssize_t nb = write(fd, buf, nbyte);
     return nb;
    }
    ```

1.  实现一个监听端口 2000 的多线程 TCP 服务器。每个线程应从客户端文件描述符读取 128 字节，并将其回显给客户端，然后关闭连接并结束线程。

1.  实现一个监听端口 2000 的 UDP 服务器。预留一个 200 字节的缓冲区。监听到达的数据包。有效的数据包长度为 200 字节或更少，并以四个字节 0x65 0x66 0x67 0x68 开始。忽略无效的数据包。对于有效的数据包，将第五个字节的值作为无符号值加到运行总和中，并打印到目前为止的总和。如果运行总和大于 255，则退出。

## 安全性

1.  数据安全的三种措施是什么？

1.  什么是堆栈溢出？

1.  什么是缓冲区溢出？

1.  操作系统是如何提供安全性的？从网络和文件系统中举一些例子。

1.  TCP 提供了哪些安全功能？

1.  DNS 是否安全？

## 信号

1.  提供两个通常由内核生成的信号名称

1.  提供一个无法被信号捕获的信号名称

1.  为什么在信号处理程序中调用任何函数（不是信号处理程序安全的函数）是不安全的？

1.  编写一段使用 SIGACTION 和 SIGNALSET 创建 SIGALRM 处理器的简短代码。

1.  处置、掩码和挂起信号集之间有什么区别？

1.  将哪些属性传递给子进程？对于执行进程呢？
