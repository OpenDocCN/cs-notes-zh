# 分布式系统工程笔记（6.824，2015 年春季）

# MIT 6.824 分布式系统工程讲座笔记

来自：[分布式系统工程笔记（6.824，2015 年春季）](https://github.com/alinush/6.824-lecture-notes)

## 讲座

由 [Robert T. Morris 教授](http://pdos.csail.mit.edu/rtm/) 授课的 6.824 讲座笔记。这些讲座笔记稍有修改，与发布在 6.824 [课程网站](http://nil.csail.mit.edu/6.824/2015/schedule.html) 上的笔记略有不同。

+   Lecture 1: 介绍: 分布式系统定义，动机，架构，实现，性能，容错性，一致性，MapReduce

+   Lecture 2: 远程过程调用（RPC）: RPC 概述，编组，绑定，线程，"至少一次"，"至多一次"，"恰好一次"，Go 的 RPC，线程同步

+   Lecture 3: 容错性: 主备复制，状态传输，"分裂脑"，Remus（NSDI 2008）

+   Lecture 4: 扁平数据中心存储: 扁平数据中心存储，二分带宽，分段

+   Lecture 5: Paxos: Paxos，一致性算法

    +   Paxos 算法描述

+   Lecture 6: Raft: Raft，一个更易理解的一致性算法

+   Lecture 7: **Google Go** *嘉宾讲座* 由 Russ Cox 主讲

+   Lecture 8: Harp: 分布式文件系统，"UPS 伎俩"，见证人

+   Lecture 9: IVY: 分布式共享内存，顺序一致性

+   Lecture 10: TreadMarks: 用户空间分布式共享内存系统，向量时间戳，释放一致性（懒惰/积极），错误共享，写放大

+   Lecture 11: Ficus: 乐观并发控制，向量时间戳，冲突解决

+   Lecture 12: Bayou: 断开操作，最终一致性，Bayou

+   Lecture 13: MapReduce: MapReduce，可伸缩性，性能

+   Lecture 14: **Spark** *嘉宾讲座* 由 Matei Zaharia 主讲: 弹性分布式数据集，Spark

+   Lecture 15: **Spanner** *嘉宾讲座* 由 Google 的 Wilson Hsieh 主讲: Spanner，分布式数据库，时钟偏差

+   Lecture 16: Facebook 上的 Memcache: Web 应用程序可伸缩性，旁路缓存，Memcache

+   Lecture 17: PNUTS 雅虎: 分布式键值存储，原子写入

+   Lecture 18: Dynamo: 分布式键值存储，最终一致性

+   Lecture 19: **HubSpot** *嘉宾讲座*

+   Lecture 20: 两阶段提交（2PC）: 两阶段提交，Argus

+   Lecture 21: 乐观并发控制

+   Lecture 22: 点对点、无追踪 BitTorrent 和 DHTs: Chord，路由

+   Lecture 23: 比特币: 可验证的公共分类帐，工作证明，双重支付

## 其他年份的讲座

+   实用拜占庭容错（PBFT）：[[2012]](original-notes/pbft-2012.txt), [[2011]](original-notes/pbft-2011.txt), [[2010]](original-notes/pbft-2010.txt), [[2009]](original-notes/pbft-2009.txt), [[2001]](original-notes/pbft-2001.txt), [[PPT]](original-notes/pbft.ppt)

## 论文

我们在 6.824 中阅读的论文（目录在这里）：

1.  MapReduce

1.  Remus

1.  扁平数据中心存储

1.  Paxos

1.  Raft

1.  Harp

1.  共享虚拟内存

1.  TreadMarks

1.  Ficus

1.  Bayou

1.  Spark

1.  Spanner

1.  Facebook 的 Memcached

1.  PNUTS

1.  Dynamo

1.  Akamai

1.  Argus, 守护者和动作

1.  Kademlia

1.  比特币

1.  AnalogicFS

其他论文：

1.  一个有故障进程的分布式一致性的不可能性

    +   查看这里的第 5 页、第 10 张幻灯片以更快地理解引理 1（可交换性）

    +   参见[这篇文章](http://the-paper-trail.org/blog/a-brief-tour-of-flp-impossibility/)以获取另一种解释。

1.  实用拜占庭容错（PBFT）

    +   参见[PBFT 讨论](http://the-paper-trail.org/blog/barbara-liskovs-turing-award-and-byzantine-fault-tolerance/#more-211)。

## 偶然发现

1.  [共识、2PC 和事务提交的简要历史](http://betathoughts.blogspot.com/2007/06/brief-history-of-consensus-2pc-and.html)

1.  [分布式系统理论适用于分布式系统工程师](http://the-paper-trail.org/blog/distributed-systems-theory-for-the-distributed-systems-engineer/)

1.  [分布式系统：为了乐趣和利润](http://book.mixu.net/distsys/)

1.  [你不能从 CAP 中选择 CA](https://codahale.com/you-cant-sacrifice-partition-tolerance/)，或者“你不能牺牲分区容错性”

1.  [年轻血液的分布式系统笔记](https://www.somethingsimilar.com/2013/01/14/notes-on-distributed-systems-for-young-bloods/)

1.  从头开始解释 Paxos

## 测验

准备测验 1 这里
