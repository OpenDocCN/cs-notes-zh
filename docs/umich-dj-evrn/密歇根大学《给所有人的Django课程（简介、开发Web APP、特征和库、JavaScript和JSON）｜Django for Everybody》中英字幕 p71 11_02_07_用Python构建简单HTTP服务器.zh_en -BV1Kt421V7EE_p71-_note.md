# Django for Everybody：11：用Python构建简单HTTP服务器 🖥️

![](img/ff6928b67427fff626520a26f18f8625_0.png)

![](img/ff6928b67427fff626520a26f18f8625_2.png)

![](img/ff6928b67427fff626520a26f18f8625_3.png)

![](img/ff6928b67427fff626520a26f18f8625_4.png)

![](img/ff6928b67427fff626520a26f18f8625_5.png)

在本节课中，我们将学习如何使用Python的`socket`库构建一个最简单的HTTP服务器。我们将从零开始，理解服务器如何监听连接、接收请求并发送响应。

![](img/ff6928b67427fff626520a26f18f8625_7.png)

---

![](img/ff6928b67427fff626520a26f18f8625_9.png)

![](img/ff6928b67427fff626520a26f18f8625_10.png)

![](img/ff6928b67427fff626520a26f18f8625_12.png)

![](img/ff6928b67427fff626520a26f18f8625_14.png)

上一节我们介绍了如何使用Python构建一个简单的HTTP客户端（浏览器）。本节中，我们来看看如何构建一个HTTP服务器。

![](img/ff6928b67427fff626520a26f18f8625_16.png)

## 服务器核心概念

一个HTTP服务器的核心任务是：
1.  **监听**一个特定的网络端口，等待客户端连接。
2.  **接受**客户端的连接请求。
3.  **接收**客户端发送的HTTP请求数据。
4.  **处理**请求并构造一个HTTP响应。
5.  **发送**响应数据回客户端。
6.  **关闭**本次连接，然后回到第1步，等待下一个连接。

## 代码解析：一个简单的HTTP服务器

![](img/ff6928b67427fff626520a26f18f8625_18.png)

以下是构建一个简单HTTP服务器的核心代码结构。我们将逐部分解析其工作原理。

```python
import socket

![](img/ff6928b67427fff626520a26f18f8625_20.png)

def create_server():
    # 1. 创建socket（“电话”）
    serversocket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    try:
        # 2. 绑定到本地地址和端口（“电话号码”）
        serversocket.bind(('localhost', 9000))
        # 3. 开始监听，允许最多5个连接排队
        serversocket.listen(5)
        while True:
            # 4. 等待并接受客户端连接（“接电话”）
            (clientsocket, address) = serversocket.accept()
            # 5. 接收客户端发送的请求数据
            rd = clientsocket.recv(5000).decode()
            # 6. 处理请求（这里只是打印请求行）
            lines = rd.split('\n')
            if len(lines) > 0:
                print(lines[0])
            # 7. 构造HTTP响应
            data = "HTTP/1.1 200 OK\r\n"
            data += "Content-Type: text/html; charset=utf-8\r\n"
            data += "\r\n"
            data += "<html><body><h1>Hello World</h1></body></html>\r\n\r\n"
            # 8. 发送响应并关闭连接
            clientsocket.sendall(data.encode())
            clientsocket.shutdown(socket.SHUT_WR)
    except KeyboardInterrupt:
        print("\nShutting down...\n")
    except Exception as exc:
        print("Error:\n")
        print(exc)
    finally:
        serversocket.close()

if __name__ == '__main__':
    print('Access http://localhost:9000')
    create_server()
```

### 关键步骤详解

![](img/ff6928b67427fff626520a26f18f8625_22.png)

![](img/ff6928b67427fff626520a26f18f8625_24.png)

以下是服务器工作流程中几个关键步骤的说明：

1.  **创建与绑定Socket**：`socket.socket()`创建了一个通信端点。`bind(('localhost', 9000))`将其绑定到本机的9000端口。这就像安装了一部电话并分配了号码。
2.  **监听连接**：`listen(5)`告诉操作系统开始监听端口。参数`5`表示如果服务器正忙，操作系统可以为其排队最多5个等待的连接。
3.  **接受连接**：`accept()`是一个**阻塞**调用。程序会停在这里，直到有客户端发起连接。一旦连接建立，它会返回一个新的`socket`对象（`clientsocket`）用于与这个特定的客户端通信。
4.  **接收请求**：服务器调用`clientsocket.recv(5000)`来接收客户端发送的数据。根据HTTP协议，**客户端必须先发送请求**。
5.  **构造与发送响应**：服务器按照HTTP响应格式（状态行、头部、空行、正文）组装数据，并通过`clientsocket.sendall()`发送回去。
6.  **关闭连接**：发送完毕后，服务器调用`shutdown()`和`close()`来关闭连接。客户端在接收完数据后也会关闭其连接，完成一次完整的“通话”。

![](img/ff6928b67427fff626520a26f18f8625_26.png)

![](img/ff6928b67427fff626520a26f18f8625_27.png)

---

上一节我们详细解析了服务器代码的每个部分。本节中，我们将看看如何运行并与这个服务器交互。

![](img/ff6928b67427fff626520a26f18f8625_29.png)

![](img/ff6928b67427fff626520a26f18f8625_30.png)

## 运行与测试服务器

要运行这个服务器，你需要在一个终端窗口执行Python脚本。

![](img/ff6928b67427fff626520a26f18f8625_32.png)

### 启动服务器

![](img/ff6928b67427fff626520a26f18f8625_34.png)

在命令行中运行：
```bash
python server.py
```
输出会显示：
```
Access http://localhost:9000
```
此时，服务器已在后台运行并等待连接。

![](img/ff6928b67427fff626520a26f18f8625_36.png)

### 使用浏览器测试

打开你的网页浏览器（如Chrome, Firefox），在地址栏输入：
```
http://localhost:9000
```
然后按回车。

**你将看到**：
*   浏览器窗口显示“**Hello World**”。
*   服务器的终端窗口会打印出类似这样的日志：
    ```
    GET / HTTP/1.1
    GET /favicon.ico HTTP/1.1
    ```
    第一行是你访问根路径的请求。第二行是浏览器自动请求网站图标（favicon.ico）的请求，这是浏览器的默认行为。

![](img/ff6928b67427fff626520a26f18f8625_38.png)

![](img/ff6928b67427fff626520a26f18f8625_40.png)

### 使用Python客户端测试

除了浏览器，我们也可以用Python写一个简单的客户端来测试服务器。以下是两种方式：

![](img/ff6928b67427fff626520a26f18f8625_42.png)

![](img/ff6928b67427fff626520a26f18f8625_43.png)

![](img/ff6928b67427fff626520a26f18f8625_44.png)

**方式一：使用底层socket（模拟原始请求）**
```python
import socket

mysock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
mysock.connect(('127.0.0.1', 9000))
cmd = 'GET / HTTP/1.1\r\n\r\n'.encode()
mysock.send(cmd)

![](img/ff6928b67427fff626520a26f18f8625_46.png)

while True:
    data = mysock.recv(512)
    if len(data) < 1:
        break
    print(data.decode(), end='')
mysock.close()
```

**方式二：使用高级的urllib库**
```python
import urllib.request
fhand = urllib.request.urlopen('http://localhost:9000')
for line in fhand:
    print(line.decode().strip())
```
运行任何一个客户端脚本，你都会在客户端窗口收到服务器返回的“Hello World”响应，同时在服务器窗口看到相应的GET请求日志。

![](img/ff6928b67427fff626520a26f18f8625_48.png)

---

## 总结与展望

![](img/ff6928b67427fff626520a26f18f8625_50.png)

本节课中我们一起学习了如何使用Python的`socket`库构建一个最简单的HTTP服务器。我们理解了服务器从监听端口、接受连接、接收HTTP请求到发送固定响应的完整生命周期。

![](img/ff6928b67427fff626520a26f18f8625_52.png)

这个服务器功能非常有限，无论收到什么请求，它都只会回复“Hello World”。然而，它清晰地演示了Web服务器最核心的工作原理。在实际开发中，我们会使用像Django、Flask这样的成熟框架，它们封装了这些底层细节，让我们能专注于处理不同的URL请求和生成动态内容。

![](img/ff6928b67427fff626520a26f18f8625_54.png)

当你未来运行Django开发服务器时，在终端里看到的那些`GET /admin/`或`POST /submit/`日志，其底层原理与我们今天构建的这个简单服务器是一脉相承的。理解这个基础，能帮助你在遇到更复杂的问题时，知道如何深入探究。