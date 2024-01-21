# RPC，第一部分：远程过程调用简介

## 什么是 RPC？

远程过程调用。RPC 是我们可以在不同的机器上执行一个过程（函数）的想法。实际上，该过程可能在同一台机器上执行，但可能在不同的上下文中执行-例如在不同的用户下以不同的权限和不同的生命周期。

## 什么是特权分离？

远程代码将在不同的用户和不同权限下执行。实际上，远程调用可能以比调用者更多或更少的权限执行。原则上，这可以用来提高系统的安全性（通过确保组件以最低权限运行）。不幸的是，安全问题需要仔细评估，以确保 RPC 机制不能被利用来执行不需要的操作。例如，RPC 实现可能会隐式信任任何连接的客户端执行任何操作，而不是在数据的子集上执行子集的操作。

## 什么是存根代码？什么是编组？

存根代码是隐藏执行远程过程调用复杂性所必需的代码。存根代码的作用之一是*编组*必要的数据成为可以作为字节流发送到远程服务器的格式。

```cpp
// On the outside 'getHiscore' looks like a normal function call
// On the inside the stub code performs all of the work to send and receive the data to and from the remote machine.

int getHiscore(char* game) {
  // Marshall the request into a sequence of bytes:
  char* buffer;
  asprintf(&buffer,"getHiscore(%s)!", name);

  // Send down the wire (we do not send the zero byte; the '!' signifies the end of the message)
  write(fd, buffer, strlen(buffer) );

  // Wait for the server to send a response
  ssize_t bytesread = read(fd, buffer, sizeof(buffer));

  // Example: unmarshal the bytes received back from text into an int
  buffer[bytesread] = 0; // Turn the result into a C string

  int score= atoi(buffer);
  free(buffer);
  return score;
}
```

## 什么是服务器存根代码？什么是解组？

服务器存根代码将接收请求，将请求解组成有效的内存数据调用底层实现，并将结果发送回调用者。

## 如何发送 int？float？结构？链表？图？

要实现 RPC，您需要决定（并记录）将数据序列化为字节序列的约定。即使是一个简单的整数也有几种常见选择：

+   有符号还是无符号？

+   ASCII

+   固定字节数或根据大小而变化

+   小端或大端的二进制格式？

要编组一个结构，决定哪些字段需要序列化。可能不需要发送所有数据项（例如，某些项可能与特定的 RPC 无关，或者可以由服务器从其他数据项重新计算）。

编组链表时，无需发送链接指针-只需流式传输值。作为解组的一部分，服务器可以从字节序列中重新创建链表结构。

通过从头节点/顶点开始，可以递归访问简单树以创建数据的序列化版本。循环图通常需要额外的内存来确保每个边和顶点都被处理一次。

## 什么是 IDL（接口设计语言）？

手动编写存根代码是痛苦的、乏味的、容易出错的、难以维护的，难以从实现的代码中逆向工程出线协议。更好的方法是指定数据对象、消息和服务，并自动生成客户端和服务器代码。

接口设计语言的现代示例是 Google 的 Protocol Buffer .proto 文件。

## RPC 与本地调用的复杂性和挑战？

远程过程调用比本地调用慢得多（10 倍至 100 倍），并且比本地调用更复杂。RPC 必须将数据编组成兼容的格式。这可能需要通过数据结构进行多次传递，临时内存分配和数据表示的转换。

健壮的 RPC 存根代码必须智能地处理网络故障和版本控制。例如，服务器可能需要处理来自仍在运行早期版本存根代码的客户端的请求。

安全的 RPC 将需要实施额外的安全检查（包括身份验证和授权），验证数据并加密客户端和主机之间的通信。

## 传输大量结构化数据

让我们通过 3 种不同的格式-JSON、XML 和 Google Protocol Buffers 来检查使用 3 种不同格式传输数据的方法。JSON 和 XML 是基于文本的协议。以下是 JSON 和 XML 消息的示例。

```cpp
<ticket><price currency='dollar'>10</price><vendor>travelocity</vendor></ticket>
```

```cpp
{ 'currency':'dollar' , 'vendor':'travelocity', 'price':'10' }
```

谷歌协议缓冲区是一个开源的高效二进制协议，非常注重高吞吐量、低 CPU 开销和最小内存复制。已经为多种语言实现了协议缓冲区，包括 Go、Python、C++和 C。这意味着可以从.proto 规范文件生成多种语言的客户端和服务器存根代码，以便将数据编组到二进制流中并从中解组。

谷歌协议缓冲区通过忽略消息中存在的未知字段来减少版本问题。有关更多信息，请参阅协议缓冲区的介绍。

[`developers.google.com/protocol-buffers/docs/overview`](https://developers.google.com/protocol-buffers/docs/overview)
