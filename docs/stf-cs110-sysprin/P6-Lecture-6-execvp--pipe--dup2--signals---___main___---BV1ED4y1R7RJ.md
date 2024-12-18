# P6：第6讲 execvp, pipe, dup2, signals - ___main___ - BV1ED4y1R7RJ

欢迎，欢迎回来参加周一的 CS 110 课程。我们继续讲解多进程，正如我所说，这是你可能第一次看到你编写的程序中出现并行处理的情况。所以我们将花时间讨论这个内容。今天我们还要讲解这些叫做管道的东西。

这些基本上是两进程通过读写数据交换信息的方式。所以我们会讲到这些内容。然后，如果时间允许，我们会稍微讲一下进程间通信，也就是我们会讨论两个进程如何互相通信，以及你是如何得到消息或信号的，信号是它的另一个名字。

你怎么知道什么时候子进程真正结束了？我们到课程结束时会讲到这个问题。我想。作业进展如何？生物系统做得不错吧？我看到有几个人竖起了大拇指。它确实有很多小的组成部分。刚才有个人在走廊里问我，比如，怎么得到一个信号？

你怎么知道自己在读取什么数据，数据包含什么内容？

除非你处在一个专门从磁盘读取数据的函数中，否则你基本上不会关心。你已经知道，哦，我正在读取一个文件，或者我在读取一个目录，或者我在读取一个块之类的东西。当你调用这些从磁盘读取的函数时，你就知道了。

因为磁盘本身不关心上面存了什么内容，它只对你作为实际操作系统有意义，文件系统已经根据每个块设置了特定的内容。所以你可以通过这种方式了解这些内容。总之，希望一切顺利。

到目前为止关于作业有问题吗？Piax进展如何？有什么评论或问题吗？是的。[听不清]，好问题。问题是，你说你们可以修改某些函数。是指我们已经为你们写好的那些函数吗？之类的吗？不是。

如果可能的话，应该尽量不要修改函数的返回值。我的意思是，尤其是那些函数，通常来说保持它们不变。如果出于某种原因需要修改，你必须有充分的理由。但是不，应该的。我们制定的规范不需要改变返回值。

如果你有具体问题，可以在课后过来告诉我，我们可以聊聊是否需要解决这个问题。但大多数时候，是的。其他人呢？好的。我的办公时间是今天晚上和接下来一周的时间。明天早上我有办公时间。到目前为止没有很多人来，所以我可能会在下午增加一些办公时间。

我在想，可能周三课后更多的人能参加吗？如果我安排了。看看，看到几个人了。好吧，我会根据我的个人时间表看看能不能安排。得查看一下。不过我们会尝试在周四大概相同的时间再安排一些办公时间，也许这样也行。所以我们会这么做。好了，所以下周。

其实我们已经完成了示例，接下来我会再回顾一下。记住，我们之前讨论过一个很有趣的系统调用叫做 `EXE_CVP`，它是 `EXE_C` 或 exec 系列函数中的一部分。它的作用是，它告诉操作系统，我想运行另一个程序，基本上就是替换掉我现在的系统。

然后用那个程序替换我现在的流程。现在，如果你想这么做，大多数情况下你是无法完成程序的。我是说，可能有些情况下是可以的。但大多数情况下，你希望你的程序能派生出另一个进程，这个进程是由其他程序生成的，而你可以使用`fork`来做到这一点。

所以你 `fork`，你得到一个子进程，并保存它为子进程。你会运行这个程序，而在这个过程中，子进程将变成那个程序，就这么简单。现在，子程序和父程序之间是有一些通信的，我们得谈谈这种通信是怎么发生的。所以我们写了一个非常基本的程序，叫做 MySystem。

我们会在几分钟后扩展这个内容，然后你将为第四次作业进一步扩展它。你将制作一个更强大的 MySystem 命令，基本上就是一个小型 shell。我们所讲的就是这个。下面是程序本身做了什么。让我们来看看这个过程，基本上就是这样。

MySystem 函数首先做的是，它接收一个命令，这个命令可能是像 `LS` 或 `cat file.txt` 这样的东西。它只是接收一个命令，然后用实际的 shell 来运行这个命令。我们这么做是为了让解析变得更简单。

当你到达第四次作业时，你将学会如何在不使用 shell 的情况下完成这个任务，作为一种训练。你将看到，稍后我们会解释这是什么意思。然后，它接收那个命令，执行 `fork`。执行了 `fork` 后，MyPen 死掉了吗？

所以它实际上做了 `fork`，因为我们即将调用 `exec CVP`。所以我们不希望它仅仅是程序唯一的函数。哦不，已经完成了。根本没成功。等等。也许我们以后就不再用了。等等，看看。没有。这个不行。再试一次，然后我们就不再用这个了。没有成功。好了。无论如何。

它正在做的是，我甚至会放大这里的内容。所以基本上，它将会分叉，如果是子进程，它会生成另一个进程，就是你要运行的程序。它通过基本上说，“好吧，实际上运行这个叫做/bin/sh的程序”，也就是 shell 程序来做到这一点。

![](img/e8c16a216dab678dec1c79e51f021b08_1.png)

使用 `-c` 选项运行它，告诉系统，“嘿，运行以下程序”。所以这有点像是两级间接调用。然后它会获取你的命令，运行你输入的命令。然后这是一个需要以空值终止的数组。这就是发生的事情。

它基本上是在创建一个参数数组，这是一个字符串指针数组，指向字符的指针。

![](img/e8c16a216dab678dec1c79e51f021b08_3.png)

然后你调用 `exec CVP`，它调用了 `exec CVP` 的第一个参数是直接运行的程序的名称。在这个例子中，它是 `/bin/sh`，这也恰好是参数列表中的第一个参数，就像在 `main` 中一样。然后第二个参数是整个参数列表，第二个参数。如果失败，则返回到这个函数。如果没有失败。

那个子进程的其余部分被销毁了。它被“吞噬”，以便让另一个程序可以运行。记住，你的父进程仍然在运行。但是你刚刚创建的子进程现在被另一个程序销毁了。

![](img/e8c16a216dab678dec1c79e51f021b08_5.png)

好的，这就是发生的事情。现在，我实际上在尝试一些新的东西。我们的一个助教实际上创建了这个小系统，你实际上可以在幻灯片中运行这个，尽管我觉得字体可能有点太小了。但你可以在这里运行它。这就是它运行时的样子。好了，开始了。

![](img/e8c16a216dab678dec1c79e51f021b08_7.png)

它在这里显示了一个小光标。我只是把它做成了这个样子。你可以输入 `ls`。这就是程序正在做的事情。它实际上运行 `ls` 并执行这些操作。然后，看看 `catcode.c` 也应该会输出代码。

![](img/e8c16a216dab678dec1c79e51f021b08_9.png)

所以我们写了一个简单的 shell，最后它总是回到提示符。

![](img/e8c16a216dab678dec1c79e51f021b08_11.png)

![](img/e8c16a216dab678dec1c79e51f021b08_12.png)

好的。子进程的标准输入就是普通的标准输入。稍后我们会看到它如何变化。好了，然后要结束这个过程，顺便说一下。要结束这个函数，我们实际上需要按控制键 D，表示我们已经完成了从标准输入输入内容。

它基本上关闭了正在运行的进程的标准输入。好了，我们来看一下主函数是如何工作的。主函数基本上是说，“哦，好吧”。

![](img/e8c16a216dab678dec1c79e51f021b08_14.png)

我们将做一个 while 循环，因为我们必须不断地显示一个小提示符，也就是这个小箭头。它使用 fgets 从标准输入中获取一行。这就是你输入 `ls` 或 `cat` 等命令时的情况。然后，如果你输入控制 D，它会结束。这就是这里发生的事情。然后它就填充了新行。

将新行更改为零，这样我们就得到了一个普通的旧字符串，没有新行符。然后它实际上调用我的系统命令，获取从我的系统命令返回的返回值。然后它继续查找。好的。你看到这里发生了什么吗？

![](img/e8c16a216dab678dec1c79e51f021b08_16.png)

好的。这就是我们前几天讨论的内容。我们继续。现在这是它的测试。我刚才已经给你展示过了。

![](img/e8c16a216dab678dec1c79e51f021b08_18.png)

我们继续，稍后我们将讨论类似程序的更多细节。

![](img/e8c16a216dab678dec1c79e51f021b08_20.png)

我想介绍一些其他的主题。好的。我们将引入管道的概念，这是我之前提到过的。然后是 doop two。在实验中，你应该已经在某种程度上覆盖了 doop。我们将详细讨论它到底在做什么，尤其是在这里的作用。好的。现在让我们看看更复杂的 shell。好了，实际上，让我们看一下。

我只是想确保我们能看到，因为还没有使用管道。

![](img/e8c16a216dab678dec1c79e51f021b08_22.png)

让我们实际上继续做这个更高级的 shell。

![](img/e8c16a216dab678dec1c79e51f021b08_24.png)

好的。这将是一个简单的 shell dot C。哦，不，等一下。是的，它是简单的 shell。等一下。我想我已经有了简单的 shell。抱歉。哦，好的。我们就看看它吧。我现在不会全部输入。稍后有很多东西要输入。

![](img/e8c16a216dab678dec1c79e51f021b08_26.png)

这是我们要做的事情。看一下它。其实，我可以在这边的东西上做。现在我想起来了。这里的代码在这种情况下会做什么。好的。我们将创建一个实际上允许你执行后台命令的 shell。

![](img/e8c16a216dab678dec1c79e51f021b08_28.png)

那什么是后台命令呢？在传统的 shell 中。好的。你可以执行以下操作。你可以实际输入一个后台运行的命令，这意味着你可以立即拿回提示符，而其他程序仍然在运行。你为什么要这么做呢？嗯，可能有各种原因你需要让某些其他程序运行。

你仍然想使用你的 shell。好的。如果你做一些像 `LS -AL` 这样的操作，然后将它放到后台。顺便说一下，这就是你如何将它放到后台的方式。你加一个 `&`，它实际上会立刻返回到上面，来这里。它立刻会说，“嘿，这是我刚创建的一个进程”。

“然后它会给你一个提示符，剩下的部分会继续执行。我想我前几天给你展示了这个的一个例子，实际上那是……是什么来着？”

它就像是，“哇。实际上，我没想到会是这样。” 所以，“哇一个。Echo。你烦了吗？” 就像那样。“分号睡眠。1秒。完成。” 哎呀。让我们看看。“哇一个。做。做。Echo。好了。” 好的。所以就是这样。我们可以直接运行这个，它会每秒运行一次。如果我把它放到后台，它会每秒告诉我一次。

![](img/e8c16a216dab678dec1c79e51f021b08_30.png)

我可以做其他事情。每秒它就会说，“你知道的，你是新的，然后不管什么。”，而且我仍然可以运行程序。这和今天我给你展示的差不多。它基本上在后台运行。所以我现在已经通过在程序末尾加上 `&` 做到了这一点，它会说，“嘿。”

运行这个程序，然后让我做其他的事情。" 你可能会想到各种原因，为什么你想这么做。

![](img/e8c16a216dab678dec1c79e51f021b08_32.png)

除非你想被反复打扰，否则这样做不好。然后其实你必须输入 `FG` 然后按 `control C`，它就会真正停止程序。`FG` 的意思是，“把它放回前台。” 好的。你其实也可以用不同的方式来做。如果我直接运行那个命令，不加 `&`，让它继续执行。

如果我想把这个放到后台，我只需要输入 `control Z`，不是 `control C`，是 `control Z`，它就会把它放到后台并停止。这可能是我想要的。好的。然后如果我们想继续它，看看。看看。如果我们想继续它。我想，看看。我想如果我们，嗯，不，等一下。作业。嗯，是的。哦。

它可能不小心被终止了。等一下。可能已经终止了。让我们看看。如果我按下 `control Z`，它会停止，然后我可以将它放回前台。哦。我觉得它只会停止我最后的操作，这意味着我的 `while` 循环可能不会按预期工作。不过我可以这样做。我可以说，像是一个恼人的 shell。让我们看看。

我们来检查一下。好了。然后，恼人的 shell。好吧。好了。现在。恼人的 shell。恼人。好了。现在完成了。然后希望这个会持续下去，如果我一直做下去。好了。它会继续。好了，现在它在后台了。所以你基本上做的就是运行一个程序，然后如果你按下 `control Z`。

它会在后台暂停进程。然后如果你输入`BG`，它会继续在后台运行。好的。然后就这样。现在我仍然可以输入`LS`，但每秒它会显示信息。

![](img/e8c16a216dab678dec1c79e51f021b08_34.png)

你烦了吗，等等。如果我想进入前台，我可以做。我可以输入`FG`。

![](img/e8c16a216dab678dec1c79e51f021b08_36.png)

它会进入前台，然后我可以按`Ctrl+C`来去除显示的最后消息。好的。我们接下来要看的就是这个程序，它基本上会使用一个。

![](img/e8c16a216dab678dec1c79e51f021b08_38.png)

后台命令使我们能够运行后台进程。所以它比我们以前的方式更复杂一些。好的。我们来看一下实际的代码。好的。另一个`while`循环，因为我们希望我们的shell能够继续运行，并给我们返回提示符。好的。我们将读取一个命令。

这是另一个函数，它基本上从命令行读取命令。好的。我们将创建一个参数列表，它将包含命令，这样它就可以解析命令。如果你想查看这些函数的所有细节，你可以看到它们。但基本上我们输入一个命令，让它解析。

而这部分对我们要做的事情并不特别重要。好的。接下来，我们要查找一个叫做内建命令的东西，就是这个退出命令。以前我们需要按`Ctrl+D`来结束，现在我们只需要输入`quit`，它就会结束。所以这其实就是一个小的变化。

这里有一个额外的部分，我们说，如果我们输入的参数是`quit`，那么就停止这个`while`循环。那很好。好的。然后，如果参数的最后一个是`&`，我们希望把它放到后台。换句话说，我们希望返回提示符并让它继续运行。好的。那么我们怎么做呢？

我们来看看。好的。我们基本上会做如下操作。我们会看看是否在后台运行。好的。然后我们会去掉那个小的`&`，这样我们就可以正确地运行命令。然后我们会调用`fork`。好的。如果我们是子进程。

记住，如果`fork`的返回值是零，那么我们是子进程。我们将调用`exec CDP`并传递带有参数零的参数。 当然，这将不会返回，因为它是子进程。我们应该对此进行错误检查。如果我输入了一个无效的命令。

它不应该这样做。如果它是在后台，我们只需要打印出实际的子进程。进程PID，然后是我们执行的命令，然后我们将继续返回到另一个提示符。好的。然后我们将，如果不是，如果它不在，那么我们必须做一个等待PID。等待PID做什么？它告诉父进程，在子进程结束之前不要做任何事情。

好的，这就是这里的内容。

![](img/e8c16a216dab678dec1c79e51f021b08_40.png)

再次，你可以查看一些细节。我想我实际上还有另一个，是的。我也可以在这里运行它。

![](img/e8c16a216dab678dec1c79e51f021b08_42.png)

好吗？在这里运行它。好了，这很简单，提示符恰好被叫做。

![](img/e8c16a216dab678dec1c79e51f021b08_44.png)

Simple SH。好了，你将写一个名为 STSH 的程序，代表 Stanford Shell。好的，如果我输入 LS，结果出来了。如果我输入，嗯，输入 L，哦，你知道吗？

![](img/e8c16a216dab678dec1c79e51f021b08_46.png)

我要运行另一个程序，这样我可以展示我们刚才做的那个。简单，可能不是，创建一个 Simple SH。

![](img/e8c16a216dab678dec1c79e51f021b08_48.png)

![](img/e8c16a216dab678dec1c79e51f021b08_49.png)

好了，简单的 SH。好吧，如果我输入 LS，它会给我这个结果。我输入 catmysystem.c，它会给我这个结果。

![](img/e8c16a216dab678dec1c79e51f021b08_51.png)

如果我输入带有符号 & 的 catmysystem.c，它就会在后台运行。我的提示符会出现在这里某个位置。它会出现在这里，实际上它会打印出进程号，然后是文件名，或者说后台程序的名称，然后再打印提示符。好了。

所以我们应该能够运行我们那个恼人的程序了。而且，哦不，我忘记了，忘记做了。我们应该能够写一个“知道”的，我已经把它放到后台了。Annoying.sh放到后台了。好了。

![](img/e8c16a216dab678dec1c79e51f021b08_53.png)

然后现在我们已经进入了我们的 Simple SH。

![](img/e8c16a216dab678dec1c79e51f021b08_55.png)

就像这样。现在恰好没有办法终止这个程序。嗯，这不是真的。我可能可以输入 Jaa。我可能可以输入 PS，它会告诉我什么。如果我使用一个叫 kill 的命令，它可能有效，尽管我没有看到 annoying 出现，但是嗯，可能没办法。无论如何，我们怎么做呢？我们会输入 Control C。或者快速终止。

就这样。

![](img/e8c16a216dab678dec1c79e51f021b08_57.png)

但无论如何，重点是现在我们实际上为我们的 Simple SH 增加了一些功能。也就是说，我们现在可以在后台运行一个命令，或者我们所说的在前台运行，这实际上会暂停父进程。是的。[不清楚]，是的，好的问题。所以问题是，嘿，为什么我们要这样做？

![](img/e8c16a216dab678dec1c79e51f021b08_59.png)

等待父进程中的 PID？好的，记住父进程在做什么。父进程会返回一个提示符，等待你输入。如果我正常运行一个程序，而不在后台运行，处于我们所说的前台，那么我们不希望父进程在等待子进程结束之前就显示提示符。

这有意义吗？所以这里发生的事情是，当它在前台时，它会等待子进程结束，因为子进程接管了输入输出。如果它在后台运行，我们就不想等待 PID，因为我们希望能够继续，哦，没问题，它已经独立运行了。让我们给你返回一个提示符，以便你可以做更多的事情。

听起来不错。是的。[听不清]，子进程在传递参数后不会结束吗？或者它们会传递 DEX，DEX，DEX 等等？这是个好问题。问题是，子进程不会在精确的 CBP 结束之前完成吗？是的，精确的 CBP 就是此时的子进程。记住。

整个过程会被那个程序接管，那个程序就是子进程。所以即使你运行了那个其他程序，它也只是一个章节。当那个程序结束时，你的 wait PID 会停止。好问题。是的。子进程是否会到达你现在正在写的那一行？如果命令是合法的，子进程永远也不会到达这里。为什么？

因为精确的 CBP 永远不会返回，如果它正确地消耗进程并正常工作。好问题。还有其他问题吗？好的。让我们——你可以在这里运行，或者你可以在自己的计算机上运行。

![](img/e8c16a216dab678dec1c79e51f021b08_61.png)

使用 MIF 机器。好了，让我们来谈谈另一个系统调用，叫做管道（pipe）。管道系统调用使你能够拥有两个文件描述符，一个用于读取，另一个用于写入，每当你向另一个文件描述符写入数据时，你可以从第一个文件描述符中读取这些数据。基本上，它设置了两个文件描述符。

它们相互通信。那么，让我们看看它实际上是如何工作的。它接受一个小数组，实际上是一个非常小的数组，包含两个整数，FDS 0 和 1。所以它接受一个包含两个整数的数组。当你调用 `pipe` 时，它会将这两个文件描述符填充到该数组中。

你将从一个文件描述符读取数据，另一个则用于写入数据。它的作用是让父进程和子进程能够相互通信。因为记住，当你调用 `fork` 时，所有内容都会被复制，指向打开文件表的指针也会被复制。

所以你会得到相同的数据，这样你就可以写入一个，读取另一个。它们都在父进程和子进程中。我们将在几分钟内看到这个例子的实际应用，你可以这样做。你会明白它为什么变得如此重要。但这就是 `pipe` 的作用。你调用 `pipe`，传入这个小数组。你不需要初始化这个数组。

没关系。你只需要传入它，然后它会用两个文件描述符填充那个数组，一个用于写入，另一个用于从你刚刚读取的文件描述符中读取。

![](img/e8c16a216dab678dec1c79e51f021b08_63.png)

就是这样工作。好了，我们来看一个程序。事实上，我会把这个程序写出来，这样我们可以一行一行地做。这个程序将被命名为pipeexperiment.c。所以在这里，我们将做这个操作，FDS2。那是我们将用管道填充的文件描述符。

然后我们要说pipe FDS。我们现在忽略返回值。先不担心返回值。它实际上是不会返回的——我认为如果不成功，它可能会返回负一。先忽略它。然后我们会做一个fork，IDT。PID = fork。好吧，如果PID等于0，这意味着我们是子进程，我们要做什么？

我们要做的——好吧，这个程序要做什么。我想先告诉你。这个程序将创建一个管道，父进程将写入一些数据，子进程将读取这些数据。所以父进程写入，子进程读取。好了，顺便说一下，这个文件描述符——大家总是弄不清楚，哪个是读取。

哪个是写入？FDS0是读取器。我总是记得这一点，因为你在学写字之前，先学会了读。所以第一个是读取器。所以第二个，FDS1是写入器。这就是我记住它的方式。你可以这样做，因为子进程会从管道中读取，我们可以这样做。

我们可以立即关闭FDS1。无需写入。换句话说，我们要关闭管道。当你创建管道时，它会创建两个文件描述符。当你执行fork时，你现在总共有四个文件描述符，因为所有内容都会被复制。顺便说一下，它也会更新引用计数。所以现在你就有了这样的情况。

你有四个文件描述符在那儿飘来飘去。你其实只需要使用其中两个。读取器会在子进程中，写入器会在父进程中。你可以同时使用两个。但如果父进程和子进程都试图写入写入器，它们可能会被搞乱。因为没有真正简单的方法来确定谁会在某一时刻进行写入。

你可能可以弄明白，但这不是我们在这里要做的事情。我们只是想让子进程从管道中读取，而父进程写入它。所以我们将关闭FDS1，因为子进程不需要写入。好的，我们将使用一个恰好有六个字符的缓冲区。

我们这里只会传入六个字符。我们会在子进程中从FDS0读取。我们会读取到缓冲区，并且会读取六个字符，这基本上是缓冲区的大小。然后我们会打印从管道中读取。连接进程。好吧，百分号S，读取的内容。然后我们会写入缓冲区。

所以就是这样。现在我们已经在子进程中完成了读取。所以我们需要关闭FDS0，因为我们刚完成它。我就标记为“Don reading”。然后我们将返回0，或者我们也可以退出。所以这就是子进程要做的。子进程——有这两个管道部分。它将关闭其中一个，因为它不再使用。

去写它之前有点麻烦。然后它会从另一个文件读取。然后当它完成时，它会关闭文件。完成后你应该总是关闭文件描述符，除了标准输入、标准输出和标准错误。那些不需要关闭。好的，没问题，这就是子进程要做的。父进程会写入FDS1。

那么我们最终要关闭的是哪个文件描述符呢？是FDS0。不需要读取。我们就这样做。我们知道我们在父进程中，因为它——虽然PID不是0，但我们得到了它。好的，我们要做的是——我们将写入FDS1，因为它是管道的写端。

我们将写入“hello”。好的，我们将写六个字节。为什么是六个字节而不是五个字节？因为最后有一个空字符。必须把它写进去。好的，我们然后只需要等待子进程。PID，PID，不，我们可以通过返回值来做这个。现在我们不需要担心这个。

然后我们完成了写入。完成写入。所以我们关闭这个管道，然后返回0。哎呀，里面多了一个。好了，有什么问题吗？是的。你能保证父进程会在子进程之前写入吗？你没有任何保证。这是个好问题。好问题是你是否能保证某些事情。

父进程会在子进程读取之前写入吗？不会。但是记住，读取会阻塞，直到它获得你请求的字节数。所以除非父进程关闭，否则它会等到所有六个字节都进入。通常情况下，实际上——是的，嗯，如果有六个字节可读，它会等待。如果只有四个字节并且关闭了，那么它只会读取四个字节。但在这种情况下。

我们知道我们要发送六个字节。但不，这个问题很好。

![](img/e8c16a216dab678dec1c79e51f021b08_65.png)

好的，没问题。好吧，我们来尝试运行这个。做一下管道实验。

![](img/e8c16a216dab678dec1c79e51f021b08_67.png)

好的，管道实验。这个会有点反高潮。

![](img/e8c16a216dab678dec1c79e51f021b08_69.png)

但是从管道中读取数据，桥接进程打招呼。好的，这就是它所做的。那么到目前为止，你有什么问题吗？还有其他问题吗？是的。[听不清]。如果你将缓冲区设置为12长，然后——但是你只写了六个字节。

![](img/e8c16a216dab678dec1c79e51f021b08_71.png)

我们试试看，看看会发生什么。我们只需尝试看看会发生什么。好的。如果我们将缓冲区设置为12，并且说，嘿，我们读取12个字节。看看。缓冲区的大小是可以的。好了。我们看看。进行管道实验。管道实验。一样的事情。所以发生了什么呢？它试图读取12个字节，实际上只读取了6个。

然后文件结束了。换句话说，输入文件结束了。所以它能够继续。那么，如果我们这样做呢？如果我们说，哦，我忘记关闭我的写入器了？

我们看看这是否真的会改变。可能会，也可能不会。

![](img/e8c16a216dab678dec1c79e51f021b08_73.png)

它可能在实际结束时关闭它。我们先看看。管道实验。然后我们看看。是的，好的。它确实在那种情况下关闭了它。但是我敢打赌，如果我们在Valgrind中运行它——哦，我不知道，如何操作实际文件。在Valgrind中，你可以检查文件是否仍然打开。它会告诉你。最好不要让它们一直保持打开状态，免得浪费资源。是的，好的。

还有其他问题吗？是的。你只能读写两次吗？

这是你多次写入的时候吗？还是可以读取？

你只能一次读写一个文件吗？如果有多个子进程，你只能使用这一根管道吗？你可以使用这根管道做任何事情。只要你的逻辑没问题，你可以让所有的子进程从中读取。但是你需要知道事情发生的顺序，在父进程中怎么做等等。

但通常情况下，如果你想写入多个子进程，你可能会为每个子进程创建一根不同的管道，然后将它们保存在一个数组中。每个子进程都有自己的读取管道，它试图从中读取。顺便说一句，我们也可以交换这两个，让子进程写入管道，父进程来读取。

但那样也可以。[听不清]，是的。[听不清]，哦，好的问题。为什么它是作为一个包含两个文件描述符的数组来实现的？

![](img/e8c16a216dab678dec1c79e51f021b08_75.png)

这是他们写的方式。我的意思是，必须是——他们只是说，不，你必须有一个数组。它确实必须是一个数组。不能是两个。不是两个参数。一个参数，他们指向一个整数数组。

![](img/e8c16a216dab678dec1c79e51f021b08_77.png)

它不能超过两个。管道只在两个之间工作。创建一个读取器和一个写入器。就是这样。是的。你能解释为什么在关闭写文件描述符之前要等待子进程吗？是的，好的问题。那么，为什么在关闭文件描述符之前要等待子进程呢？可能是因为如果你关闭——可能会是——。

我不完全确定，但可能是，如果你在读取器还没读取完之前就关闭文件描述符，它可能会说，哦，写操作已经完成了，我不会再产生任何信息。所以你应该等一等。你肯定不想在确定之前就关闭它。

其他进程已经完成了所有的读取。我认为就这样了。还有其他关于这个的问题吗？

对。[听不清]，在四个--我没有说有四个进程。如果我说了，我向你道歉。现在我们有四个文件描述符，因为父进程有两个文件描述符用于 FDS，子进程也有两个文件描述符用于 FDS。只有两个进程。每当你执行 fork 时，你就会多一个进程。两个进程，但你有一份 FDS 的副本。

所以父进程有 FDS 0 和 1，子进程也是 FDS 0 和 1。这就是为什么我们这里有四个 close 的原因。我们关闭了 FDS 1，子进程立刻关闭它，因为我们不再写入它。我们在完成读取后关闭它，因为我们完全用不着它了。然后父进程做了完全相反的操作。对。

所以问题是--我以为既然它们是副本，它们不会在彼此的帧中更新。好问题。问题是，等等，等等。如果它们是副本，它们不会在每个帧中更新。你执行 fork 时，它们都会指向打开的文件表，实际上只有一个文件被打开，用于实际的文件描述符。而且它确实会更新引用计数。

谁指向它们。所以它做了--它是否--它是不是不再创建新的--不再打开文件了。对。那么子进程的副本如何完成写入呢？好问题。问题是，子进程怎么知道写操作什么时候完成？它读取所有可用的字节。其实就是这样。

所以我让它读取六个字节。如果它们可用，它就会读取六个字节。这就是它如何知道的。它会等到它们都准备好。它们都可用了。[听不清]，不，不，不。孩子进程有可能在写操作完成之前就尝试读取。但它会等到这六个字节都可用。所以它们还不可用。

当生成读取命令时，它们可能还不可用。对，好的问题。对。那么你说的“等待”是指它们只是通过信号通知 read 函数，然后子进程会等待直到收到信号？然后它会执行该子进程的剩余部分，直到读取完成。

![](img/e8c16a216dab678dec1c79e51f021b08_79.png)

就是当它实际上把六个字节传给 raw 读取函数时。所以你问的基本问题是，等一下，这里的等待是如何工作的？

read 是一个系统命令或系统调用。内核会说，哦，好，你要从另一个文件或者文件描述符读取六个字节。它们现在可用吗？不。还没有读取任何数据。哦，好吧。我就让你睡一会儿，直到它们可用。然后当它们可用了，我会把它们交给你。你会把它们全部读取。

然后你会继续执行程序。对。这实际上是一个非常--非常好的问题。因为接下来，我们会看到一个函数，我们会问，等一下，等一下，排序函数是如何知道等待数据的？

它只是说，嘿，把所有数据一直读取到文件结束。如果没有数据——如果文件有结束，它会一直等待，直到数据到来。所以我们稍后再讨论一下这个问题。

![](img/e8c16a216dab678dec1c79e51f021b08_81.png)

是的。如果我们改变整个加载的高度，那我们就永远不会有六个字符，所以我们会……

![](img/e8c16a216dab678dec1c79e51f021b08_83.png)

只需要进行一次读取。是的。让我们试试这个。它实际上可能——哦，是的。如果我们不关闭它，那就是个好问题。问题是，等一下。如果我们把它改成只读高值，并且只读三字节而不是六字节呢？让我们看看。制作，管道实验，管道实验。让我们看看。那样的话，看起来它——让我们看看。

我们改变了其他什么吗？我们还是——哦，我们没做——让我们看看。是的。那样的话，可能是因为我们实际上——父进程结束了，文件自动关闭了。那可能是发生了什么。换句话说，文件——如果我们做像这样的事情——我们来做这个。我们来做这个。while 后面加分号。

就这样永远进行下去。父进程不会结束。而且我无法判断子进程是否结束。啊，是的，我们会知道的。因为它们让我做这些疯狂的事情。这个怎么样？

它可能实际上不会——它实际上不应该，什么也不会返回。但我们只做打印。子进程结束。像这样。制作，管道实验。管道实验在那里。好的。所以它确实似乎读取了字节，可能是因为零在高值的末尾。可能就是这样。我不知道。我们可以再检查一下。这里面有一些细微的差别——。

让我们看看。那个还是。父进程还是三。如果我们只做两呢？等一下。如果我们做六，它会读取超出缓冲区的部分。那可能不是我们想要的。但是我的意思是，那样就像——让我们看看。好了，现在我们只写了两个。所以我认为发生的情况是这些文件描述符，我们称它们为某种缓冲区。

如果它得到一个零，它会将其传递给另一个程序，可能会这样做。大概就是这种情况。那是什么？那是什么——哦，嗨，Att。因为我没有把实际的零传递过去。所以哦，你知道吗？那是另外一回事。是的，所以它最终确实得到了一个零。所以它尝试读取。它一定只读取了两个，或者其他什么。

然后最后没有零。实际上这又是另外一回事。所以，嗯，它比那更有些细微的差别。所以这告诉你的是，你确实得确保你的逻辑是正确的，这样你才知道有多少数据被读取和写入。这并不像你想的那么重要。

因为通常我们在完成写入文件时，实际上会关闭文件。所以你应该记得这么做。根据你尝试做的事情，它可能会或者不会起作用。对吗？对吗？抱歉。这个实验是什么？结果这并没有包含任何东西。好问题。是的，我以为它可能会暂停并说，不，我没有得到足够的数据。

但它只写了两个，然后无论如何都关闭了，而且事实证明它并没有真正等待更多数据。是的，我在想是否有办法做到这一点。让我们看看。我不——是的。我不确定我们怎么能让它在子进程中暂停。我的意思是，也许当它到达这个等待PID时，它会做点什么。但我得查一下。

我会尝试找出是否能骗它让子进程暂停以等待更多数据。可能读取时也会有超时。对吗？如果你从未写入任何数据，只是等待读取呢？没有数据。是的，这是个好问题。我们可以试试看如果没有数据会怎样。

![](img/e8c16a216dab678dec1c79e51f021b08_85.png)

我们实际上是在写这一切。进行管道实验。哎呀。好吧，管道实验。是的。如果我们不写数据，它就会显示，我在等待一些数据。可能里面有超时，或者当读/写功能完成时，它就是对的。它告诉读取，去读取任何东西，等等。所以是的。

所以这个告诉了我们一些东西。如果我们什么都不写，我们会——我们会在子进程中停止并等待更多数据。好吧。我想是很多微妙的细节。好吧。不过无论如何，这就是管道的工作原理。管道创建了两个文件描述符。一个你可以写入，另一个你可以读取，无论你写入了什么，你可以从中读取。

从另一个读取。明白吗？这实际上让事情变得非常有趣，随着我们继续进行。

![](img/e8c16a216dab678dec1c79e51f021b08_87.png)

好吗？事实上，在我们进入下一个小部分之前，为什么我不先给你看一些东西。单位中内置了一个叫做sort的程序。sort的作用是它会按行排序你输入的内容。它会排序——做它。所以如果我输入bat和cat、apple和dinosaur以及——让我们再输入一些其他东西。Bling和cool等等。当我结束时，对吧。

如果我按下控制D，它实际上会按排序顺序重写所有输出。这就是sort的作用。好吧？如果我有一个文件，比如unsorted.txt，并将这些单词放入未排序的文件中。我可以做如下操作。我可以说sort unsorted.txt。我也可以做cat unsorted.txt，然后将其通过管道传递给sort。好吧？这就是sort成员如何获取输入。

当你输入时，它会等到所有输入完成，然后对所有行进行排序。然后再把它们全部输出。明白吗？但是这个管道的想法，这个小竖线，是说从cat获取输出，也就是单词。并将它传递给sort的输入。明白吗？

所以你必须考虑一下这里发生了什么。实际上，一个文件的输出成为了另一个文件的输入。我们通过管道来实现这个。好的？

所以，这实际上就是我们现在要看的内容。

![](img/e8c16a216dab678dec1c79e51f021b08_89.png)

好的？好吧。那么让我们看看我们将如何做——。

![](img/e8c16a216dab678dec1c79e51f021b08_91.png)

这是我们可以再次运行的程序。我们已经做过了，好的？

我们已经讨论过了所有这些内容，关于管道是如何工作的。好的？

我觉得这是一个重复的。好的？这是我们将要做的一个例子。你将重做这个函数，并且使它在下一个作业——作业三中更加健壮，作业三将在星期四发布。这是我们将要创建的一个函数，叫做 subprocess。好的？subprocess 使用了所有这些东西——这些管道、fork 和 dupe。

我认为这个叫做 dupe 2，我们稍后会解释它的意思。它使用了 exec CVP 等命令来生成——基本上是在说，我想把我的程序输出发送到另一个正在运行的文件中。明白吗？

所以这有点酷。我们首先需要关注的是这个结构体，我们将要创建的这个结构体。

![](img/e8c16a216dab678dec1c79e51f021b08_93.png)

它叫做 subprocess_t。它包含了以下内容：它有一个 PID，也就是你正在运行的程序的进程标识符；它还有一个供应文件描述符。换句话说，一个文件描述符，如果你写入它，它就成为你——

你正在运行的程序。好的？是的，我再说一遍。它会给你你正在运行的程序的进程标识符。它还会给你一个文件描述符，当你写入它时，它就成为你正在运行的文件的输入。所以，让我们思考一下如何在 sort 中使用它。

这实际上是我们将要使用的例子。发生了那件事之后，我们要做的就是创建一个 sort 程序的子进程。然后我们将传入它一堆字符串，sort 程序将对它们进行排序，并将结果打印到屏幕上。

我们的程序将传入一堆字符串给 sort，我们将让 sort 来进行排序。就是这样。你会看到它是如何工作的。等会儿你会明白的。我看到有些人看起来像是没搞懂。等它发生时你就明白了。问题是，它是新程序的 PID 吗？

你必须在这里提供输入，并且要有子进程的 PID。它是子进程的 PID，例如在这个例子中，就是 sort 进程的 PID。你会明白我们为什么需要它，为什么必须这样做，因为我们需要等待它。好，我们会创建子进程，然后在发送完所有数据后，等待它结束。

![](img/e8c16a216dab678dec1c79e51f021b08_95.png)

你稍后就能看到它是如何工作的。好吗？好吧。所以我们将再次传入一个命令，这个命令在我们的例子中是sort，或者是我们想要运行的任何程序。它将创建那个进程，启动它运行，然后基本上会告诉进程，嘿。

我将给你一堆标准输入，就像你在键盘上输入一样。然后你的任务是随意处理这些输入。在这种情况下，它将进行排序。在我们的案例中，它将对这些内容进行排序。好吗？这就是正在发生的事情。那么我们来实际看看吧。接下来我将做的是，首先输入——我将从main开始。

Subprocess。c。我将在这里从main开始。好了，这就是我们要用的类型。这是我们要使用的结构体。在main中，我们要做的是让这个程序为我们排序一堆单词。我们将把这些单词传给排序程序。所以我们从这里开始。

然后我们会说，好吧，我们还没有写这个函数，但我们会写的。Subprocess。TSP 等于 subprocess。并且排序程序位于 /user/bin/sort。好吗？

我们的子进程将会调用那个排序函数。它将为我们创建这个子进程T结构。它将创建所有必要的小管道，并且会把一切设置好。我们稍后会讲解这些。好吗？但这就是它要做的事情。它将启动排序程序。

等待我们的数据。好了。那么我们将创建——让我们创建一些单词。charge star words。在这个例子中，我们会——我不知道。我们可以用一些像——让我们用——Jerry称之为SAT单词，比如phagicity，umbridge。无所谓，随便你选。Susser，equation。希望我拼对了。Halcyon等等。

好的，我们基本上是创建一堆单词，传递给这个排序程序。因为我们想这样做。Pulperitude，let’s see，evolution，some，not，some。让我们找一个合适的词来划掉。好了，然后怎么写 indivotigable？好的，拼不对也没关系。没错。好吧，无论如何。

我们将创建一堆单词。它们现在还没有排序。好吗？

它们是以这种随机顺序排列的。好吗？然后我们将取出这些单词。I 等于 0。I 小于单词数组的大小除以单词0的大小。这一点应该是你在107课程中学过的。然后 I 加一。好吗？

然后我们将使用一个新的函数，叫做 dprintf。OK，dprintf的作用是将内容打印到特定的文件描述符上。好了，我们有一个文件描述符，因为我们在上面创建了子进程sp。我们将直接写入该文件描述符。并且我们将把每个字符串按换行符分隔写出。好吗？

所以我们要做的是，我们会说，嘿。我将拿到从子进程返回的文件描述符，然后我将向它发送一堆词语。后面跟着换行符，就像我在输入那些词到 sort 函数中一样。好吧？然后在我们完成这部分之后。

我们完成了关闭--，或者说我们完成了写入操作，所以我们应该关闭它。我们会测试这个，看看如果我们不关闭它，排序是否会停止。我怀疑它不会，但也许会。我不知道。然后我们实际上--实际上在这种情况下，嗯。我们不妨--， PIDT，PID 等于 weight，PID4，PID。

我们在子进程中得到的状态和 0。然后我们将要， let’s see。返回 PID 等于--，我们基本上要检查并确认是否得到了一个正确的返回值。如果从 weight PID 中得到了正确的 PID，我们还得检查 W 是否已退出。如果退出了--如果退出正常，我们最好从我们创建的文件中返回退出状态。

![](img/e8c16a216dab678dec1c79e51f021b08_97.png)

或者我们就返回负数 127，这基本上意味着不正常。我们没有返回任何合理的东西。

![](img/e8c16a216dab678dec1c79e51f021b08_99.png)

好的，让我们看一下。这样应该差不多能工作，除了我们还没有创建子进程函数。创建子进程--好的，太好了。

![](img/e8c16a216dab678dec1c79e51f021b08_101.png)

所以在工作中，我们没有--不太好。大家明白这里发生了什么吗？创建一个子进程。它将接收这些词语，我们将把它们发送进去。我们会把 F 打印到我们知道子进程正在监听的文件描述符上。然后我们会等待那个进程，去执行所有的排序。当它执行完时。

我们将结束程序。这就是主函数要做的。好的。

![](img/e8c16a216dab678dec1c79e51f021b08_103.png)

好的，那么子进程函数本身。好吧，我们将在这种情况下使用我们的管道 FDS2，我们会创建它。然后我们会创建一个管道 FDS，就像这样。接着我们将创建一个小的子进程 T，进程--在这里我们称它为进程。这是一个结构体，记住，所以我们可以使用小的花括号来完成这个。

这看起来有点奇怪，但我基本上会调用 fork。然后我将传递它--。我会创建 FDS1，也就是写入端，我们会把它发送回调用函数。这将是从这个函数返回的内容。好的。我们得到了 PID。然后我们还会填充它。

通过写入部分，以便我们能够从我们最初调用的函数进行写入。好的，它会在那里。如果进程.pid，也就是我们刚才创建的，等于 0，那么。我们就进入了子进程。所以我们需要做一些设置，来使得我们能够从文件描述符读取标准输入。这是什么意思呢？好吧。

子进程不需要写入，对吧？所以在设置 FDS1 之前我们先关闭它。没有写入的需求。然后我们将使用一个叫做 `dupe 2` 的函数。我会把整个过程写出来，告诉你我们接下来要做什么。我们将拿到从管道返回的读取器。

我们基本上是要复制它，以便在子进程中每次从标准输入读取时，实际上是从管道中读取。这就是它的作用，它创建了这个 FDS0 描述符的副本，并将其设置为 FDS--，或者说是标准输入文件号，基本上就是这样。

一般情况下是 0--，现在它将指向我们的新管道。所以它基本上是在说，不再进行输入操作。我们将从这个文件描述符获取输入。这就是 `dupe 2` 在做的事情。明白了吗？

一旦我们这么做了，因为已经复制了它，我们可以关闭 FDS0，因为我们已经完成了它的使用，已经复制过了。好吧，基本上，这就是--我们已经告诉过你，嘿，标准输入将来自这个管道。所以我们可以关闭原始的 FDS0，因为我们已经创建了我们需要的副本。然后我们将做一些设置。

然后实际上我们会在这里调用我们的命令，实际上是另一个，比如 `/bin/sh`，并带上 `-c` 参数，这意味着运行即将传给你的程序。接着它会执行，我们可以做一点类型转换，因为它是常量。然后需要在末尾加上 `no`。

这基本上是在创建我们即将使用的命令行，使用 `exact cvpn` 或者 `exact cvpn`。然后我们将使用 `cvpx cvpn`，`rv0`，`rv`。就是这些。如果--就这样，子进程就完成了。子进程永远不会返回，子进程永远不会到达这里。悲伤的表情。好吧，然后--我准备好面对你了。所以这就是我们想要的，在父进程中。

我们不会在父进程中使用它，因此我们也关闭了 FDS0，因为父进程中没有发生读取操作。我们只是让 sort 输出到终端。然后我们需要返回进程。所以这个函数的作用就是这样。它基本上是在做什么？创建一个管道。

所以我们有两个文件描述符，设置了这个包含子进程 PID 的子进程 T 结构，然后是父进程的 FDS1。我们关心的唯一一个是父进程。如果是子进程，我们还需要做更多的设置。我们关闭 FDS1，因为我们不需要写入它。

我们将复制 FDS0，以便能够进入标准输入，这样我们就可以从这个文件中读取标准输入了，然后我们将关闭它，因为已经复制过了。接着我们将设置命令，实际使用 `execcvp`，然后我们将执行 `execcvp`。

如果是父进程，我们关闭读取器，并返回父进程。好吧。问题来了。你会如何关闭你所复制的那个？

你怎么关闭在D2中复制的那个？嗯，我们关闭了那里实际上做的那个。你是指另一个吗？

那个会被我们调用的程序关闭，当它关闭所有打开的文件时。或者它会在标准输入关闭时自动关闭。这时就会发生那样的情况。

![](img/e8c16a216dab678dec1c79e51f021b08_105.png)

好的，让我们实际尝试一下。创建子进程。我们看看是否有任何进展。好的，子进程。我们传入了所有这些单词。子进程应该对它们进行排序。结果是排序了。所以子进程使用了sort来实际完成我们传入的单词排序。这就像是我手里有这些单词——哦，它们现在会被排序。稍等一下。

然后是unsorted.txt。让我们来做这个。可能有一个命令用来打乱你的单词。但是好了，我们完成了。这些单词没有排序。它将完全像这样做。cat unsorted，通过管道传给sort，然后它为我们完成了实际的排序。好了，现在你已经看到了它是如何工作的，而且你已经实际做过了。

![](img/e8c16a216dab678dec1c79e51f021b08_107.png)

你对它还有什么其他问题吗？是的。那是他在子进程开始时做的吗？

啊，真是个好问题。问题是，嘿，确切的CVP会丢弃旧的文件描述符吗？不会。文件描述符实际上会被传递给子进程或者程序，保持原样。这是一个很好的问题，为什么他们选择这样做。可能正是出于这个原因，他们才这么做。但是任何与进程相关的内容。

你大概希望保持它与进程一起运行。你不希望破坏文件描述符和类似的东西。因为其他新的程序可能会用到它。所有的旧内存——对，我不能——在另一个程序中，我将无法访问FDS0和FDS。嗯，它们在那个程序中并不存在。但文件描述符仍然在那个程序中打开。是的。

很好。非常好的问题。你还有什么其他问题吗？

大家明白它是如何工作的了吗？好了，你们明白为什么我们可能想这么做，以及怎么做。

![](img/e8c16a216dab678dec1c79e51f021b08_109.png)

它实际上在进行管道操作。好的。

![](img/e8c16a216dab678dec1c79e51f021b08_111.png)

好的，明白了。那么我们有了这个。我们有了SAT单词。这是一个重要的部分。关闭调用——我们必须检查这个，因为我答应过要检查。当你在实际的父进程中进行关闭时，正是它告诉sort开始排序的原因。因为它不会再给我更多数据了。这是一个我控制的步骤，控制D，在我输入的单词中。

那么让我们在五月尝试一下，具体取决于它是如何写的，实际上是如何执行的。

![](img/e8c16a216dab678dec1c79e51f021b08_113.png)

但如果我们在执行后忘记关闭它怎么办？

![](img/e8c16a216dab678dec1c79e51f021b08_115.png)

创建子进程，然后是子进程。

![](img/e8c16a216dab678dec1c79e51f021b08_117.png)

好的，它在等待。所以，sort程序在那里说，嘿，我还没看到文件的结尾呢，我只会等你结束——等文件结束。所以在这种情况下，我们在暂停sort的时候崩溃了。我们冻结了它，因为它仍然在等待我们的数据。既然我们不能再等待数据了。

或者因为没有更多数据进来了，它就会——它实际上不会结束。所以记得关闭你的文件描述符也是一个很好的原因。对吗？

为什么它会在这里关闭？这是一个很好的问题。为什么它这样关闭会阻止——这也是一个很好的问题。

![](img/e8c16a216dab678dec1c79e51f021b08_119.png)

这个关闭到底在做什么？嗯，记住，我们现在在父进程中。我们已经启动了子进程，sort程序。那sort程序在做什么？

等待我们输入——它在等待我们输入东西，对吧？

所以下面这一点，就好像我们在输入一堆单词。它们会进入我们之前通过管道创建的供给文件描述符。它们被sort的标准输入读取，而sort现在已经被dup，所以它的标准输入是管道的输出部分——或者说是供给端的读取端。

它在等待。Sort会等到文件结束才开始排序。它必须这样做，对吧？

我的意思是，sort不能——你不能排序。我是说，你可以在进行时开始排序，但你不能。正式地打印任何内容，直到你得到最后一个单词。因为如果它是列表中的第一个单词呢？你不能已经打印出什么。所以它需要等到没有更多单词输入为止。在这种情况下。

它知道没有更多单词进入的唯一方法就是当文件结束时。然后它说，好的，没有更多单词进入。然后它就可以继续了。这就是为什么要关闭它。非常好的问题。对，在哪里——是的？好的，让我再说一遍。所以dprintf，正常的打印是指终端。它说我们已经把它输入到子进程。它实际上会进入我们的sort。

Dprintf会打印到一个文件描述符。无论我们给它什么文件描述符。printf通常只会打印到终端。dprintf是新的。它会说，哦，看看，这里有一个参数，就是我们的文件描述符。这个文件描述符就是dprintf和printf打印的地方。所以在这种情况下。

我们将向供给文件描述符打印，它是管道的写入端。读取端现在已经被转变为sort的标准输入。向这一端写入，从这一端读取。进入sort。明白了吗？现在，你有更多的问题吗？没有。好的。是的。那正是你所处的位置。好的，其他人有问题吗？

有更多问题吗？好的，明白了。

![](img/e8c16a216dab678dec1c79e51f021b08_121.png)

好的，你会在下一个作业中有很多练习。好的。

![](img/e8c16a216dab678dec1c79e51f021b08_123.png)

哦，我们已经做过了。Dada-da-da，子进程。好的，剩下大约 15 分钟。让我给你介绍另一个话题。我们现在可能不会实际写代码。假设你有两个进程，你想要它们之间进行通信。一种方法是通过读写实际的数据来实现。

但这不一定是你真正想做的。你其实只是想简单地告诉另一个进程，嘿，我已经完成了某件事情，或者在我的进程中发生了某些你可能在等待的事件。或者，嘿，去做这件事吧，因为该做了。我已经完成了我的任务。

现在轮到你去接收信号并处理它了。好的。我们通过信号的概念来做到这一点。信号其实就是一个消息。事实上，正如后来所发现的那样，你甚至无法随信号一起传递数据。它基本上只是说，嘿，下面这个东西，你可以传递一个数字，表示它是什么类型的信号。它是一个小的消息，允许你表示某个事件已经发生。

信号是由内核不断发送的。每当你在程序中按下 Control C 时，你就向程序发送了一个信号，基本上是终止了它。这就是信号。这里有一个叫做 SIGKILL 的信号，嗯，它会终止程序。接下来我们会讨论很多其他的信号。那么，这些信号是如何被处理的呢？

换句话说，一旦信号到达，哪个函数负责处理呢？嗯，你有一个叫做信号处理程序的特殊函数。信号处理程序只有在某个事件发生时才会被调用。所以内核会等待某个事件的发生。

它意识到需要发送一个信号，然后告诉程序中的那个函数去做这件事。如果你修过 CS107E，你在处理中断时就经常处理信号处理程序等等。你会创建一个函数，当你按下键盘时，假设这个函数会被调用。

这就叫做事件处理。现在我们可以在 C 语言中做到这一点。还有一个叫做 SIGSEGV 的信号，它会在发生段错误时触发。无论你做什么，都会收到一个发送到程序的信号，告诉你发生了段错误，通常会终止你的程序。你可以捕获这个信号并处理它，从而避免程序被终止。

有些程序确实会这样做，这也是我们可以做的一件事。这就是信号处理程序让你能够做到的事情。它们允许你接收这些信号并对其进行处理。有些信号你是无法捕获的。一个是 SIGKILL。你不能说，嘿，不能终止我的进程。另一个是 stop。

我们稍后会再讨论这些。所以基本上我们要做的是，我们试图说，嘿，这是一个进程。当某个事件发生时，调用另一个函数。无论这个函数在代码的什么地方，顺便提一句，其他外部的东西调用我们的函数时，我们的程序会停止一切，跳转到那个函数，开始处理信号。

当它到来时，这有点难处理，尤其是当你深入研究时。我们将详细讨论这个问题。信号有很多细节，其中一种细节是，我们有 SIG 浮点异常，这通常发生在你做诸如除以零之类的操作时。你会收到一个奇怪的信号，告诉你：“哇，你做错了数学运算，这很糟糕。”

我不能处理这个，所以我将发送一个信号。我告诉过你我们有 SIGINT，它是中断信号。我想我叫它 SIGINT，就是 SIGINT。那就是终结者程序。还有 SIGSTOP。每次我按下控制 Z 时，实际上是停止了你的程序并暂停它。

`while` 并会将你带回终端，如果你在终端中。然后你可以收到一个 SIGINT 信号，继续运行进程。我们将看到一些非常有趣的例子，展示这两种信号的使用。顺便说一下，你实际上可以向自己发送信号。你可以告诉你自己的程序，停止。只是等待。你可以告诉你的程序去做。基本上它是这么说的。

等待其他人继续你。我们将在一些有趣的例子中看到这一点。当管道结束时，你会收到一个 SIGPIPE 信号。当子进程结束时，你会收到一个 SIGCHLD 信号，这是子进程结束的信号。这个信号很有趣，正如你想象的那样，我们会使用它。现在我们正在讨论的就是这个。SIGCHLD 是当子进程状态发生变化时触发的信号。

换句话说，你的子进程正在做某些事情。如果它停止，会发送一个 SIGCHILD 消息，告诉父进程：“嘿，你的子进程停止了。你在乎吗？”也许你在乎，也许不在乎。当子进程结束时会发生 SIGCHILD 信号，信号处理程序会被调用。当子进程继续时，它也会被调用。

父进程应该使用 `wait PID` 来处理子进程状态的变化。我们已经做过这个了。顺便说一下，我们在某些情况下忽略了它。如果你回去看看简单的示例，你会发现当你有一个后台进程时，我们实际上忽略了 `wait PID`，并且从未执行它。这其实不是处理的最佳方式。

你应该在某个时刻处理它，尽管我们没有处理。但我们会到达这一点。你可以让一个 SIGCHILD 信号发送到你程序中的特定函数。这就是当你调用 `wait PID` 时的情况。通常情况下，你不会在程序的主循环中处理它。有时你会，但通常不会。你实际上会等到子进程的处理函数被调用。

大多数情况下我们忽略所有的信号。大多数信号我们都会忽略。我们不能忽略 SIGINT，也不能忽略 stop，但我们可以忽略其他所有的信号，通常你会这么做。在 C 和 C++ 中，除非你在 107E 课程中，否则你从未处理过信号。但在 CS107 或 CS106B 中，你只会忽略它们。这些信号发生时，你无动于衷，或者它们就这样发生了。

结束你的程序。所以这里面发生的就是这些。我们将编写一些实际执行这些操作的函数。SIGCHILD 处理程序的目的几乎总是执行 wait PID，可能还要处理一些其他的事情。好了，这里有一些代码。我们快速看一下这个程序。

这个程序实际上是一个小迪士尼乐园的示例。杰瑞写了这个程序。它所做的就是基本上设置一堆 fork，进行建模。好的，父亲带着他的孩子们去了迪士尼乐园，并送他们去玩。然后爸爸在孩子们出去玩的时候睡觉，一个接一个地。

当他们回来时，爸爸醒了过来，他说：“哦，我很高兴你回来了。”当所有孩子都回来了，他们就离开了游乐园。这就是这个模型的内容。实际上，它看起来非常简单。你有一个 printf，内容是：“让我五个孩子玩耍，而我去小睡一会儿。”然后它设置了一个信号，指向我们接下来会看到的一个函数。

函数还没有到达。它将设置一个 SIGCHILD 信号，指向一个叫做 REAP Child 的函数。事实证明，这就是我们要编写的函数的名字。然后它将进行一个 for 循环，循环次数为孩子的数量，这个案例中是五个孩子。然后如果是子进程，它将基本上让孩子睡觉。

根据孩子的数量，三个秒的间隔。好的，第一个孩子会立刻回来。第二个孩子会睡三秒钟。所以实际上，不，那不是真的。第一个孩子会睡三秒钟，因为它是第一个要来的孩子。第一个孩子会睡三秒钟。下一个孩子会睡六秒钟。

等等。然后，当孩子醒来，假装他们在外面玩时，它会关闭那个孩子，完成那个孩子。到那时，信号处理程序会被调用。然后就差不多了。好的，实际上父亲那边还有一些额外的内容。在父进程中，你实际上需要等待它们。

在这里，孩子的数量少于你拥有的总孩子数，这个案例中的总数是五个。好吧，printf，至少有一个孩子仍在玩耍，所以爸爸睡着了，打瞌睡。然后爸爸要睡五秒钟。好的，然后在爸爸醒来之后，当孩子处理程序发生时。

![](img/e8c16a216dab678dec1c79e51f021b08_125.png)

爸爸实际上会醒来。睡眠是一个有趣的命令。当你收到任何信号时，sleep 实际上会停止。所以你认为它会睡五秒钟，但实际上它会一直持续到某个信号发生。

![](img/e8c16a216dab678dec1c79e51f021b08_127.png)

好的，这里有一个叫做 reap child 的小函数，基本上是等待孩子结束，使用负一，因为我们不知道是哪一个结束了。我们只知道有某个孩子结束了。然后它增加了已完成的数量。已完成的数量。因为它在一个与主函数不同的函数中，所以我们实际上必须使用全局变量。

这有点可惜，因为我们不太喜欢全局变量，但这是一个例子，在这种情况下你必须使用全局变量，因为没有其他实际的方式可以在两个函数之间传递信息。好的，另外一件事。reap child 函数是在父进程中的。所以父进程会在子进程状态变化时被调用。

![](img/e8c16a216dab678dec1c79e51f021b08_129.png)

好的。那么让我实际上输入这个并运行它。

![](img/e8c16a216dab678dec1c79e51f021b08_131.png)

看，这个叫做五个孩子。实际上，我们来做这个。复制五个孩子到五个孩子。看，好的，生成五个孩子。五个孩子。这就是它的功能。至少有一个孩子在玩耍，所以爸爸打起了盹。第一个孩子三秒后回来。返回给爸爸。第一个孩子六秒后回来，返回给爸爸。

第三个孩子九秒后回来。第四个孩子在下一秒返回给爸爸。第五个孩子在最后一次返回给爸爸。所以实际上，我猜在这种情况下。睡眠并没有真正停止。所以父进程没停止。父进程查了一下。我以为它发生了。我猜只有当它退出循环时，才会停止。我以为它停了。

但这次没有。基本上，这就是发生的事情。孩子三秒后回来，三秒后，三秒后。当孩子完成时，reaped child 函数会被调用。我们再看看代码。如果最后的两分钟或者四分钟，我们可以讨论你们的任何问题。

![](img/e8c16a216dab678dec1c79e51f021b08_133.png)

关于这个代码，你有什么问题吗？这里发生了什么？

也许你刚才没明白。为什么有一个参数是 reaped child？哦，好问题。那是，我认为，是触发的信号。换句话说，它会是“sig child”，结果就是这样。好问题。问题是，“这个参数是什么？”，我们在这里没有使用它，因为我们不关心它。

我们知道只有一个信号能进入这个函数。但如果我们发送多个信号到同一个函数，你可能想知道。好问题。我们之所以有顺序，是因为我们等的时间太长了。

![](img/e8c16a216dab678dec1c79e51f021b08_135.png)

这意味着第一号孩子很可能会先完成，而第二号孩子将完成。

![](img/e8c16a216dab678dec1c79e51f021b08_137.png)

之前。是的，这是一个好问题。问题是，“等等，为什么它是按顺序发生的？”

![](img/e8c16a216dab678dec1c79e51f021b08_139.png)

记得我们是怎么设置的吗？我们说每个孩子根据其编号等待三秒。第一个孩子等三秒，然后六秒，再然后九秒。这就是它们按这个顺序发生的唯一原因。如果它们都在周三发生。我们会看到一个例子，我们试图让它们同时发生。

时间到了，我们来看看这是否真的会出问题，虽然这并不是我们想要的。怎么样？

输出。输出。是的？我在试图证明为什么当父亲熄火时。问题是，“是什么问题？”是的，这是个好问题。为什么父亲会在这里醒来？

父亲睡了五秒。第一个孩子在三秒后回来，而父亲还剩两秒的睡眠时间。对吧？然后再睡五秒，但与此同时，第六秒和第九秒发生了。这是连续两次，父亲才会再醒。我的想法是父亲每次都会醒来，但事实并非如此。是的。对吧？这是个好问题。问题是。

“为什么我们要在 REAP child 中做一个 `weight PID`？”

![](img/e8c16a216dab678dec1c79e51f021b08_141.png)

我们确实需要在孩子结束后进行清理。当一个孩子结束时，我们应该调用 `weight PID` 来进行清理。这个函数负责清理，告诉内核，“去清理这个孩子。”所以我们不妨在 REAP child 中做这件事，因为反正我们得为它清理一些东西，可能。

也可以立刻做。好问题。如果你不等，就会有 REAP 内存泄漏。如果你不等，好的问题。如果你不等，REAP 内存泄漏，它不一定就是内存泄漏，但，它有点像内存泄漏。我的意思是，我想这是内存泄漏，因为当你的程序结束时，所有孩子都会被处理。

与此同时，我们已经不需要它们了，为什么它们还存在？从某种意义上来说，这有点像内存泄漏。存在额外的资源被使用，为什么还要使用它们呢？是的，还有其他问题吗？嗯？抱歉，`weight PID` 也会清理孩子的内存吗？

是的，好的问题。`Weight PID` 会清理孩子的内存，并返回孩子可能正在使用的任何资源。好吧，明白了。[听不清]，所以，REAP child 可能做了任何事情。我的意思是，你可以将那个信号传递给任何程序进程。REAP child，没错，这是个好问题。REAP child 可能做了任何事情。

有任何信号，并且少于 30，但有很多不同的信号。我们可以让这个函数处理任何信号。记住，无论如何这个函数都会被调用。父亲恰好在睡觉。这个函数被调用并开始运行，当这种情况发生时。所以。

现在你的程序有两个部分在同一个进程中运行，它们现在可以同时做两件事。所以，这又是我们需要处理的并行性。好了，最后一个问题，然后我们就让你们离开。是吗？[听不清]。你可以给出，好的问题。当你说信号，信号，子进程，根子进程。

无论你在这里输入什么，这就是你最终得到的结果。

![](img/e8c16a216dab678dec1c79e51f021b08_143.png)

最终得到的结果。那就是 REAP 子进程将要查找或触发的信号。我们传递 SIG 子进程信号，因为我们知道我们正在创建一堆子进程，我们希望处理它们。这就是为什么我们使用 SIG 子进程信号。SIG 子进程信号无论如何都会收到。在这种情况下，我们让它调用我们的函数。就是这样。好了，如果你们有其他问题。

请上前来。我周三见你们。
