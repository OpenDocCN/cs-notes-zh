# 致谢

> 原文：[Acknowledgments](https://sourceacademy.org/sicpjs/acknowledgements)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

《计算机程序的构造和解释》（SICP JS）的 JavaScript 改编是在新加坡国立大学（NUS）为 CS1101S 课程开发的。该课程由 Low Kok Lim 共同教授了六年，他的良好教学判断对课程和这个项目的成功至关重要。CS1101S 教学团队包括许多 NUS 同事和 300 多名本科生助教。他们在过去九年中不断的反馈使我们解决了无数 JavaScript 特定的问题，消除了不必要的复杂性，同时保留了 SICP 和 JavaScript 的基本特征。

SICP JS 是一个软件项目，除了书籍项目。我们在 2008 年从原作者那里获得了书籍来源。早期的 SICP JS 工具链是由刘航开发的，并由冯飘飘进行了改进。Chan Ger Hean 开发了印刷版的第一批工具，基于这些工具，Jolyn Tan 开发了第一版电子书的工具，何欣悦和王倩重新利用这些工具制作了当前的比较版。Samuel Fang 设计并开发了 SICP JS 的在线版本。

SICP JS 和 CS1101S 的在线版本在很大程度上依赖于一个名为*Source Academy*的软件系统，以及它支持的 JavaScript 子语言称为*Source*。在准备 SICP JS 期间，许多学生为 Source Academy 做出了贡献，并且系统将他们 prominently 列为“贡献者”。自 2020 年以来，新加坡国立大学 CS4215 课程的学生们贡献了几种编程语言实现，这些实现被用于 SICP JS：在第 3.4 节中使用的并发版本是由 Zhengqun Koo 和 Jonathan Chan 开发的；在第 4.2 节中使用的惰性实现是由 Jellouli Ahmed，Ian Kendall Duncan，Cruz Jomari Evangelista 和 Alden Tan 开发的；在第 4.3 节中使用的非确定性实现是由 Arsalan Cheema 和 Anubhav 开发的；Daryl Tan 帮助将这些实现整合到了 Academy 中。

我们感谢 STINT，瑞典国际合作研究和高等教育基金会，他们的休假计划使 Martin 和 Tobias 联系在一起，并允许 Tobias 成为 CS1101S 的联合教师，并加入 SICP JS 项目。

我们要感谢 ECMAScript 2015 委员会的勇敢工作，由 Allen Wirfs-Brock 领导。SICP JS 在很大程度上依赖于 ECMAScript 2015 中的常量和 let 声明以及 lambda 表达式，这些都是在 JavaScript 中添加的。这些增加使我们能够在 SICP 的最重要思想的呈现上保持与原版的接近。Guy Lewis Steele Jr.领导了第一个 ECMAScript 标准化，并对第 4 章的一些练习提供了详细和有用的反馈。

—Martin Henz 和 Tobias Wrigstad

## 《SICP》第二版的致谢，1996 年

我们要感谢许多人帮助我们开发这本书和这个课程。

我们的主题是“6.231”的明显的知识传承，这是 MIT 在 20 世纪 60 年代末由 Jack Wozencraft 和 Arthur Evans Jr.教授的关于编程语言学和 lambda 演算的精彩课程。

我们对 Robert Fano 深表感谢，他重新组织了麻省理工学院的电气工程和计算机科学的入门课程，强调了工程设计原则。他带领我们开始了这个事业，并写下了这本书演变而来的第一套课程笔记。

我们试图教授的许多编程风格和美学是与 Guy Lewis Steele Jr.一起发展的，他与 Gerald Jay Sussman 一起初步开发了 Scheme 语言。此外，David Turner，Peter Henderson，Dan Friedman，David Wise 和 Will Clinger 教会了我们许多出现在这本书中的函数式编程社区的技术。

Joel Moses 教会了我们如何构建大型系统。他在符号计算系统 Macsyma 方面的经验提供了一个洞察，即应该避免控制的复杂性，而是集中于组织数据以反映被建模的世界的真实结构。

Marvin Minsky 和 Seymour Papert 塑造了我们对编程及其在我们的智力生活中的地位的许多态度。我们应该感谢他们，因为他们让我们明白，计算提供了一种表达的手段，可以用来探索那些否则太复杂以至无法精确处理的想法。他们强调，学生编写和修改程序的能力提供了一个强大的媒介，其中探索成为一种自然的活动。

我们也强烈同意 Alan Perlis 的观点，即编程非常有趣，我们最好小心支持编程的乐趣。这种乐趣的一部分来自观察伟大大师的工作。我们很幸运能够在 Bill Gosper 和 Richard Greenblatt 的指导下成为学徒程序员。

很难确定所有为我们课程的发展做出贡献的人。我们感谢所有在过去十五年中与我们一起工作并在我们的课程上投入了许多额外时间的讲师、辅导员和导师，特别是 Bill Siebert，Albert Meyer，Joe Stoy，Randy Davis，Louis Braida，Eric Grimson，Rod Brooks，Lynn Stein 和 Peter Szolovits。我们特别要感谢 Franklyn Turbak 在韦尔斯利的杰出教学贡献；他在本科教学方面的工作树立了一个我们都可以向往的标准。我们感谢 Jerry Saltzer 和 Jim Miller 帮助我们解决并发性的奥秘，以及 Peter Szolovits 和 David McAllester 对第 4 章中非确定性求值的阐述所做出的贡献。

许多人在其他大学中付出了大量的努力来呈现这些材料。我们与之密切合作的一些人包括以色列理工学院的 Jacob Katzenelson，加州大学欧文分校的 Hardy Mayer，牛津大学的 Joe Stoy，普渡大学的 Elisha Sacks，以及挪威科技大学的 Jan Komorowski。我们为我们的同事感到异常自豪，他们在其他大学对这门课程进行了改编，并因此获得了重要的教学奖项，包括耶鲁大学的 Kenneth Yip，加州大学伯克利分校的 Brian Harvey，以及康奈尔大学的 Dan Huttenlocher。

Al Moyé安排我们向惠普工程师教授这些材料，并制作了这些讲座的录像带。我们要感谢才华横溢的教师，特别是 Jim Miller，Bill Siebert 和 Mike Eisenberg，他们设计了包含这些录像带的继续教育课程，并在世界各地的大学和工业界教授了这些课程。

许多其他国家的教育工作者已经付出了大量的工作来翻译第一版。Michel Briand，Pierre Chamard 和 André Pic 出版了法文版；Susanne Daniels-Herold 出版了德文版；Fumio Motoyoshi 出版了日文版。我们不知道谁出版了中文版，但我们认为被选为“未经授权”翻译的对象是一种荣幸。

很难列举所有为我们用于教学目的的 Scheme 系统的技术贡献者。除了 Guy Steele，主要的专家还包括 Chris Hanson，Joe Bowbeer，Jim Miller，Guillermo Rozas 和 Stephen Adams。其他付出大量时间的人包括 Richard Stallman，Alan Bawden，Kent Pitman，Jon Taft，Neil Mayle，John Lamping，Gwyn Osnos，Tracy Larrabee，George Carrette，Soma Chaudhuri，Bill Chiarchiaro，Steven Kirsch，Leigh Klotz，Wayne Noss，Todd Cass，Patrick O’Donnell，Kevin Theobald，Daniel Weise，Kenneth Sinclair，Anthony Courtemanche，Henry M. Wu，Andrew Berlin 和 Ruth Shyu。

除了麻省理工学院的实施，我们还要感谢许多人为 IEEE Scheme 标准工作的贡献，包括编辑 R⁴RS 的威廉·克林格和乔纳森·里斯，以及克里斯·海恩斯、大卫·巴特利、克里斯·汉森和吉姆·米勒，他们准备了 IEEE 标准。

丹·弗里德曼一直是 Scheme 社区的领导者。社区的更广泛工作不仅涉及语言设计问题，还包括基于 Schemer's Inc.的 EdScheme 的高中课程和迈克·艾森伯格以及布莱恩·哈维和马修·赖特的精彩书籍等重大教育创新。

我们感谢那些为使这本书成为现实的人的工作，特别是麻省理工学院出版社的特里·埃林、拉里·科恩和保罗·贝斯。埃拉·马泽尔找到了精美的封面图片。对于第二版，我们特别感谢伯纳德和埃拉·马泽尔在书籍设计方面的帮助，以及大卫·琼斯，这位卓越的巫师。我们还要感谢那些对新草案提出深刻评论的读者：雅各布·卡岑尔森、哈迪·迈耶、吉姆·米勒，特别是布莱恩·哈维，他对这本书的做法就像朱莉对他的书《简单方案》所做的那样。

最后，我们要感谢多年来鼓励这项工作的组织的支持，包括来自惠普公司的支持，由艾拉·戈德斯坦和乔尔·伯恩鲍姆实现，以及来自 DARPA 的支持，由鲍勃·卡恩实现。

——哈罗德·阿贝尔森和杰拉尔德·杰伊·萨斯曼

《计算机程序的构造和解释》

JavaScript 版本
