# 伙伴 A 的练习

## 问题 A3

你会注意到，每当一个人去一个新地方时，这个地方会收到一个`'enter`消息。此外，这个人之前所在的地方会收到一个`'exit`消息。当地方收到消息时，它会调用其`entry-procedures`或`exit-procedures`列表中的每个过程。地方有以下用于操作这些过程列表的方法：`add-entry-procedure`、`add-exit-procedure`、`remove-entry-procedure`、`remove-exit-procedure`和`clear-all-procs`。你可以在代码中阅读它们的定义。

Sproul Hall 附有一个特别讨厌的退出过程。修复`sproul-hall-exit`，使其在第三次调用后停止讨厌。

请记住，`exit-procs`列表包含的是过程，而不是过程的名称！重新定义`sproul-hall-exit`是不够的，因为 Sproul Hall 的退出过程列表仍然包含旧的过程。最好的做法是再次加载`adv-world.scm`，这将定义一个新的 Sproul Hall 并添加新的退出过程。

## 问题 A4：第 1 部分

我们已经为人们提供了使用消息`'talk`和`'set-talk`来说话的能力。正如你可能已经注意到的，这个校园周围的一些人在别人经过时开始交谈。我们想要模拟这种行为。在任何这样的互动中，涉及到两个人：一个是已经在这个地方的人（以下简称为`talker`），另一个是刚刚进入这个地方的人（`listener`）。我们已经提供了一个机制，让`listener`在进入时向这个地方发送一个`enter`消息。此外，每个人都准备接受一个`notice`消息，意味着这个人应该注意到有新人来了。`talker`应该收到一个`notice`消息，然后开始交谈，因为我们让一个人的`notice`方法发送一个`talk`消息给自己。（稍后我们会看到一些特殊类型的人有不同的`notice`方法。）

你的任务是修改地方的`enter`方法，以便除了正在进入的人之外，还向该地方的每个人发送一个`notice`消息。`notice`消息应该有新进入的人作为参数。（现在你不会对该参数做任何操作，但以后会用到。）

将以下内容添加到`adv-world.scm`中：

```
(define singer (instantiate person 'rick sproul-plaza))

(ask singer 'set-talk "My funny valentine, sweet comic valentine")

(define preacher (instantiate person 'preacher sproul-plaza))

(ask preacher 'set-talk "Praise the Lord")

(define street-person (instantiate person 'harry telegraph-ave))

(ask street-person 'set-talk "Brother, can you spare a buck") 
```

尝试四处走动到`sproul-plaza`和`telegraph-ave`，看看是否触发了消息。

**你必须包含一个脚本，其中你的角色四处走动并触发这些消息。**

## 问题 A4：第 2 部分

到目前为止，程序假设任何人都可以去任何地方。在现实生活中，许多地方都有上锁的门。

为地方发明一个`may-enter?`消息，它接受一个人作为参数，并始终返回`#t`。然后发明一个`locked-place`类，在其中`may-enter?`方法如果地方是未锁定的则返回`#t`，如果地方是锁定的则返回`#f`。（它应该最初是锁定的。）`locked-place`类还必须有一个`unlock`消息。为简单起见，编写此方法时不带参数，并始终成功。在真实的游戏中，我们还会发明钥匙，并且需要��个机制，要求人必须有正确的钥匙才能打开门。（这就是为什么`may-enter?`接受人作为参数的原因。）

修改`person`类，以便在从一个地方移动到另一个地方之前检查是否有权限进入。如果一个人无法进入，返回一个错误。然后创建一个锁定的地方并进行测试。

**注意：** 一个锁定的地方应该有一个实例化变量，即它的名称。

```
(define warehouse (instantiate locked-place 'warehouse)) 
```

## 问题 A5

四处走动很棒，但有些人从远处通勤，所以他们需要把车辆停放在车库里。车辆只是一个`thing`，但你需要发明一种特殊类型的地方，称为`garage`。车库有两种方法（除了所有地方都有的方法）：`park`和`unpark`。你还需要一种特殊类型的`thing`，称为`ticket`；它的特殊之处在于它有一个`number`作为实例化变量。

`park`方法接受一个车辆（一个`thing`）作为参数。首先检查车辆是否实际上在车库里。（拥有车辆的人会进入车库，然后要求停放车辆，所以在发送`park`消息之前，车辆应该与人一起进入车库。）然后生成一个带有唯一序列号的`ticket`。（序列号计数器应该在所有车库之间共享，这样我们以后不会因为尝试从一个车库取车在另一个车库停放的车辆而陷入麻烦。）每张票据都应该有名称`ticket`。

你将把票据号码与车辆关联在一个键值表中，就像我们在第 6 课中使用`get`和`put`一样。然而，`get`和`put`是针对所有操作使用单个固定表格；在这种情况下，我们需要为每个车库使用单独的表格。文件`tables.scm`包含了表格抽象数据类型的实现：

```
constructor: (make-table) returns a new, empty table.

mutator: (insert! key value table) adds a new key-value pair to a table.

selector: (lookup key table) returns the corresponding value, or #f if
                     the key is not in the table. 
```

你将学习如何在[SICP 3.3.3 (pp. 266-268)](https://mitpress.mit.edu/sicp/full-text/sicp/book/node63.html)中实现表格。现在，暂时将它们视为原始的。

创建一个以票据号码为键，车辆为值的表格条目。然后要求车辆的所有者丢失车辆并带走票据。

`unpark`方法接受一个票据作为参数。首先确保你得到的对象实际上是一个票据（通过检查名称）。然后在车库的表格中查找票据号码。如果找到车辆，要求票据的所有者丢失票据并带走车辆。此外，在该票据号码的表格中插入`#f`，以防止人们两次取车。

一个真实的车库会有限定的容量，并且会收取停车费，但为了简化项目，你不必模拟车库的这些方面。

**一定不要将任何东西命名为"car"！这会搞乱一切！**

注意：

+   一个停车票只有一个实例化变量，即一个序列号。（例如，`(instantiate ticket 120)`）。

+   一个停车票是一个带有名称`'ticket`的物品。

+   一个车库需要一个实例化变量，即它的名称。（例如，`(instantiate garage 'soda-garage)`）。

+   不要为车辆定义一个新的类。你可以假设 park 被正确的参数调用。

+   停放一个无主的车辆应该返回一个错误。

+   解除停车一个未停放的车辆应该返回一个错误。
