# P30：p29 2-6c Finite state machines 3 - 加加zero - BV1qotgeXE8D

第一个问题的答案是在重量一，让我们来看看为什么我们从关闭状态开始，然后用户程序调用listen，我们过渡到listen状态，然后socket接收到一个sin，我们过渡到sin接收状态。

在sin接收状态时，用户程序调用close，所以我们沿着带有close的事件边缘遍历。