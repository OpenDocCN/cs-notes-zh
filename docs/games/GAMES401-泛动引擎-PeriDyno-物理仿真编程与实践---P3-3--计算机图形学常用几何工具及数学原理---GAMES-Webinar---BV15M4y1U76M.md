# GAMES401-泛动引擎(PeriDyno)物理仿真编程与实践 - P3：3. 计算机图形学常用几何工具及数学原理 - GAMES-Webinar - BV15M4y1U76M

那我们开始吧。

![](img/5575232c48126af6375bca201651ce6b_1.png)

就是这次的话主要讲一些，就上节和我们把编程什么相关的一些基础讲了一下，然后这次的话因为主要还是讲那个，因为是想去仿真里边还是包含大量的，跟几何相关的一些基础的一些内容，然后呢。

所以这次呢会跟仿真相关的一些几何啊，就一些东西会这次会讲一下，当然这里边有几何包含的东西其实比较多啊，所以呢也不可能把几何所有东西都讲一遍，然后主要还是后面跟后面，比如因为后面会有三次课。

主要是比如讲脏体，然后呢讲SPH流体，然后当然还有就是做一些弹性体相关的一些内容，跟这个相关的一些几何，这里这节课主要会基本都会过一下，哦这个我好像时间是不是又标错了，这应该2023年，我回。

然后今天这次的大纲是这样，主要分为几个部分，就是首先是史良代数跟张亮分析的一些内容，但这个因为这样就是这两个，学科其实无论哪个单独讲的话，其实估计都能讲一节课，所以呢这次的实际上不会说展开去讲太多东西。

然后呢主要是还是把一些，有可能后面会碰到的一些计算啊，或者符号什么的过一下，然后呢其这样的话就是其他的反正到时候如果碰到，有些不懂的就是可以具体的再找，比如说对应的一些书。

然后今天重点要讲的主要是几个东西，一个是那个三维，因为咱们现在这次就是这期课的话，主要还针对三维的一个计算，所以呢讲一些跟三维里边常见的一些几何通源，然后还有就是两个专题就是主要是讲。

距离的一个计算以及一个相交的一个测试，到最后呢有几个场景，然后我现在先到时候会展示一下，但因为整个这个东西啊就是，无论这个计算的距离还是这个相交计算，整个还是都就是里边还是会包含大量的数学相关的东西。

所以可能会比较枯燥，所以这样我先演示一个程序吧。

![](img/5575232c48126af6375bca201651ce6b_3.png)

就是大概是做一个什么内容，就是这样的话有一个直观的一个感觉，然后后面具体讲的时候呢有一个感性的一个认识吧，然后这里边是这样就是我们搭了，主要也是为了便于大家理解，然后呢这样就是搭了一个程序。

就是比如像这个主要是做一个距离计算的，然后呢打开之后呢实际上就是，因为本身如果直接是打个比方就是，你做一个点到一个几个图源的一个计算的话。



![](img/5575232c48126af6375bca201651ce6b_5.png)

你实际上相当于你要去设置各种各样的一个参数。

![](img/5575232c48126af6375bca201651ce6b_7.png)

然后呢相互之间可能整个实际上还不太好配置，所以因为还有可能各种的极端的条件需要去考虑到，所以这里边呢就是搭这么一个辅助场景的一个好处是什么呢。



![](img/5575232c48126af6375bca201651ce6b_9.png)

是因为这样的话你整个可以通过UI去调这个，比如这里边这个场景是做什么事情呢，实际上就是算一个比如这右边有个点啊，然后呢左边呢是有一个叫OBB，后面我们会讲到实际上就是叫，它是有向的。

然后比如说你可以通过调它的一个方向啊，然后改变它的那个一个朝向，然后呢整个这个是实时计算的，然后你发现就是比如这个朝向改了之后呢，当然就是因为它整个算的实际上是就这个点，到这么一个OBB的一个距离。

然后呢就是因为这个程序里边把，计算出来那个距离的两个端点，因为你相当于比如是这个点到这个OBB的一个距离的话，其实包含两个点一个是这个点其实点，还有这个是打到那个OBB上的一个点。

然后这样的话整个实际上是把这个，两个端点跟一个它们中间的一个线段，实际上可画出来了，所以这样的话就是也比较方便就是，比如说你写的算法不对的话，就可以比较方便的去调试。

因为比如像这种它其实包含的场景可能性会比较多，就比如假如你这里去旋转的话，因为它有可能是比如说它跟这个边，有可能是最近的，当然它也有可能是比如跟这个，它的角离的是最近的，所以它的距离计算的话。

当然这里可以把那个平面关了，这样平面不显示了可能更清楚一点，然后当然也有可能比如说，它的那个最近的那个点，可能就是在一个它的最，比如它的一个平面上的某一个位置中的一个点，所以这样的话就是实际上就是这种。

用这种直观的方式去相当于去，测试整个你的计算的距离对不对，这样会比较方便，所以整个我先讲一下，就现在我先不讲这个场景怎么去搭的，就是我在最后会去讲就是说，因为这里实际上包含几个节点。

然后这里边就可能会涉及到我们第一时刻讲的，整个框架里边的一些东西，这样的话就是最后我会讲，就是说比如说针对一个简单的，这么一个场景怎么用可视化的一个手段，然后或者是用更方便的带交互的这个手段。

然后把这个场景搭出来，然后呢就是更方便的去测，你比如说你写的算法到底对不对。

![](img/5575232c48126af6375bca201651ce6b_11.png)

所以这个我先简单的展示一下，然后后面会就是到最后。

![](img/5575232c48126af6375bca201651ce6b_13.png)

我再回过来来去讲这个，实际上就是实现上应该怎么去做，然后这样的话我后面。

![](img/5575232c48126af6375bca201651ce6b_15.png)

接下来还是先把理论的一些东西先过一下，就是主要这几部分，然后刚才讲就是其实它的基础是两个，一个是史上代数，然后另外一个是张亮分析的相关的一些内容，然后这两部分呢实际上是这样。

之前王鹏斌老师应该已经设计过了，然后包括这里边就是每一个运算，它到底代表什么，直观的一个从几个上怎么去解释，就是这个应该王老师的那个课里边，应该也提过了，然后呢这里边我就不展开讲了。

就是这里边需要大家注意一点，就是因为所有的这里边，比如说你看到的，比如现代数里边的东西，最好是这样能跟几何的直观能联系起来，这样的话就是有助于你去理解，因为你比如你直接看这个符号的话很抽象。

比如这个当然就A加B，但如果你用几何的这个直观的那个去理解，这个东西实际上就是可能就两个向量，求和然后呢去算出它的一个对角线，当然比如求差的话，就两个向量的端点一减，比如类似用这种形式。

然后去辅助你理解会比较容易一些，然后当后面的还有比如说像点击，然后当然还有叉击还有三角击，然后这些呢是这样，就是一定要记得这些符号啊，就是代表什么意思，就是如果是初学者的话。

可能这个东西有些可能不一定熟，比如像这个叉乘的实际上代表的是，它的两个计算的，比如说是相当于它的一个新的方向，就沿着两个跟这两个AB都垂直这么一个方向，然后像后面那三重机的话，实际上就是会比较常见的是。

比如你算一个，比如说是一个平行的问题的这么一个体积，比如这样的话会很常见的用这样的一个计算公式，当然这里它满足还有一些额外的定律了，比如说它交换率啊，或者是那个这个结合率等等就这些。

然后每一个运算符号可能会不太一样的，因为就有些符号的话，它其实是不符合交换率的，比如像这里边前几个呢，就前三个实际上都符合交换率的，但是最后一个，比如最最后两个实际上都不是不符合交换率，所以这些呢。

实际上在计算的时候一定要注意啊，然后这个是常态数的，最常见的这么几个运算，然后当后面就是讲距离计算，包括跟相交运算的时候呢，也会也会用到一些这个这几个符号，然后还有一个就是。

大家可能看反正的paper里边会用，涉及到大量的一个张量的一个这么一个概念，然后这个张量直观的怎么去理解呢，实际上就是，你如果因为张量实际上是一个通用的这么一个叫法，如果你按照以往你们比如说，初中啊。

或高中学的那个实际上这个东西就是你可以看，就张量的话，它其实分0阶张量，1阶张量或者12阶张量，然后所以呢，这里的0阶张量实际上就是我们常常说的这么一个标量，然后呢。

通常你看那个论文里边去标这个符号的话，一般就用小写的这个字母，比如说像abcd啊，然后都是小写的写体，然后这个呢，是代表的一般是标代表了一个0阶张量，然后呢，另外还有就是1阶张量的话。

其实就是所谓的就是史量，然后呢，这个一般用一个大就粗体的这么一个小写的这么一个字母，然后相当于这样的话是代表一个1阶的一个张量，然后它其实也就是一个史量，那还有一个就是2阶张量的话。

其实就是我们所谓的这个，其实就是一个矩阵，然后其实就是二乘比如几乘几，就是它是一个二维的这么一个一个形式，所以它实际上就是一个矩阵，然后当然还有更高阶的，比如3阶的4阶的，因为像3阶4阶上去之后呢。

其实这个东西主要会在比如说你以后会讲到弹性的时候，因为像英里英变张量，它实际上都是一个2阶张量啊，就是它实际上一个矩阵，但是呢，就是比如英里跟英变之间的一个关系啊，它实际上会用一个比如说一个4阶的张量。

去表示他们的一个线性的一个关系，所以你发现其实相当于你可以理解，就是几阶张量的话，实际上就是你往某个维度上再增加一维，比如说你0阶张量它其实没有维度了，然后你1阶张量的话，你增加一个维度。

比如它有一个列也好或行也好，当然这个不同约定可能不一样，就你增加一个维度呢，其实就1阶张量，然后你到2阶的话，实际上再增加一个维度呢，就2阶，当你3阶的话，你就是比如说你沿着那个纵向，然后再增加一个。

那其实就变成一个体，所以类似本账实际上就是张量实际上，这么一个概念，然后这里边其实还有一个非常重要的一个东西，就是因为我们常见的论文里边，一般会以这种就是第一行，我这个写的用标句去标。

这样的话一个好处就是，它整个形式看起来会非常的一个简洁，但是呢，这种形式就是你如果是在做实线，或者做反应计算的时候，这个东西不太适合用来做计算，因为什么意思就是整个的这个东西啊。

你实际上你比如说你用库大写实验也好，我们加加加实验也好，它实际上你要知道就是它里面具体每一项，它实际上是项与项之间的一个计算，就这样呢，针对这种比如说你如果是想实现更方便的话。

所以一般来说会用这种叫Einstein标记法，然后这个标记法也是就是主要是，在做实现的时候，它因为它主要是用下角标来标的，这样的话它比如每一个，你比如说你写个负循环，比如说这样的话。

你比如爱到底是针对的是哪一个下标，J针对是哪个下标，这样的话可以比较清楚，然后呢，就是你实现的时候也比较比较方便，所以整个后面我会讲一些运算的时候，也会对应的讲一下这个这个Einstein标记法。

然后看看就是说它整个是怎么用的，然后另外还讲一下就是这一块，因为主要的话是设计内容实际上是非常的多，然后呢，大家如果有兴趣的话可以推荐一下，就是黄科志老师的这么一个张量分析，他有一本书。

当然黄老师因为主要去年可能因为疫情，他没有没有坚持到今年，但是我觉得他这个书还是非常宝贵的，然后大家有兴趣的话，可以详细的可以去读一下，然后因为他的那个延伸，包括你如果仔细去读的话。

里面包含的东西还是非常多，然后这个有助于对你，比如说整个你要后面要深入学习，整个仿真的一些技术知识的话，整个这个张量分析，这个是一个非常基础的，这么一个一些知识，然后这里边张量的代入运算。

这里我主要是也是这样，还是主要一个目的，列在这还是为了帮助大家，就是有一个感性的一个认识，就是因为这个东西每个展开比较多嘛，所以就是我把这个符号先列在这，就这样的话，就是后面如果碰到某些符号的话。

不至于说，我也不知道这个符号是做什么事情的，就是你就是你有一个概念，就是你发现这个应该张量里边，哪一个运算或者是哪一部分来的，这样的话你可以进一步的去，比如说找相应的书，你看看到底应该是什么概念。

所以这里边典型的你可以发现，它主要是包含一个张量的和差，但这样张量和差这里边，因为这个AB，这个我实际上都是以二阶张量来为例来举例的，所以你发现就是，就是相当于其实都是一个二维的，所以它的角标的话。

其实就主要是IJ两个指标，然后所以这里边你可以看到，就是比如说两个张量求和或者求差的话，实际上就是对应的一个元素，比如说A的IJ，然后它这个元素，然后加上或者减去对应的B的那个IJ的元素。

然后这里一定要注意，就是这里的IJ实际上是一个显示指标，然后这个跟后面那讲到有的K，这个亚指标是不一样的，就是显示指标代表什么意思，就是它这个IJ实际上是固定的，就是你相当于比如说你算左边这个张量。

那你这样的话，你要去算IJ这个指标，后面这两个指标要一定要跟前面，就你这个公式左边那个IJ指标是一样的，就是这个是不能变的，然后对应的其实你可以看到后面，比如说你是标量跟张量相乘的话也是一样的。

就相当于你本账就是你这个标量乘上一个张量，那等效率就是你这个标量，跟张量里边的每一个元素相乘，然后也就是它这个IJ指标是对上的，然后这里边其实有一个比较特殊的，就是这里边有个点击的这么一个概念。

然后这个是张量里边比较特殊，其实你如果以前学过现代数，就是学过这个矩陈运算的话，其实你发现其实就是一个矩陈运算，然后呢当然张量因为它是一个更广义的一个范畴，所以你看从张量里边怎么去定义这个东西。

实际上就是你如果按比如说A点击B这么一算的话，然后实际上就是你要去算它IJ这个下标的，这么对应的一个元素，你会发现它实际上相当于是要把A这个，就A这个对应的元素，然后它有个I然后I是固定的。

然后但这里边会有一个K这个叫亚指标，然后这个亚指标就是要变的，就这个跟你的那个张量的为数是有关系的，比如你一个3乘3的张量，那这里的K实际上是必须得从0到012，相当于是三个元素，然后对应的后面的那个。

比如B也是一样的，就是你要012，所以这里边你会发现就这个，比如我们算一个IJ的这么一个元素的话，实际上这里边会有几项，实际上有相当于是有三项要把它加起来，当然IJ不变IJ跟左边一样，然后后面的话。

这个K必须是从0到2这么一个概念，所以它实际上是一个亚指标，也就是说你后面如果出现的某个，那这个角标跟前面没有的话，那这个必须得遍历所有的那个元素，然后这个元素的个数跟你实际上张量的。

那个每个方向的一个维度是相关的，然后那后面还有一些典型的，比如像那个转制，转制的话实际上就是你发现就下标的，换个方向就是I跟J，然后变成J跟I，然后当然还有一个缩并，就后面两个比较奇怪的这么一个符号。

其实就是这是一个冒号的符号，然后这个叫缩并，缩并有什么概念呢，其实你发现就是，如果是两个二阶张量的缩并，缩并马上就变成一个标量，所以你发现就是它相当于是I跟J，然后所有的这个都加起来。

因为你发现左边实际上是没有这个下下标的，所以这样的话，如果左边没有下标的话，这个I和J在后面实际上就是一个压制标，所以相当需要把所有的这个元素对应的相乘之后，然后再相加，然后当然还有一个就是叫并使。

这个并使比如说我们在做那个计算那个shift tensor，或者是就是说我们根据就是粒子法，然后根据领域去计算它的一个形状，然后这个会比较有用，就是相当于你比如两个向量，然后你怎么合成。

比如其实A跟B实际上是一个一阶的一个张量，然后一阶张量，你怎么变成一个二阶张量的，这样的话就需要相当于从A里边对应的去第二个元素，然后呢从B里边去第J个元素，然后这两个呢呃乘减之后。

然后组成一个二阶张量之后，然后就相当于就把一个呃低位的一个张量，相当于生成一个高位的一个张量，然后这些所有这些运算整个会在后面法轮基算里边，可能都呃都会或多或少都会涉及到。

所以这样的话就是我这里先提一下，然后后面如果碰到的话，就大家有个概念，然后就说就可以到前面比如再翻阅一下，或者我其他还有一些不懂呢，也可以去找就对应的一个书籍里边再去看一下，所以这一块主要是呃。

就是快速的这样过一下这两部分的一个内容，因为如果整个讲的话，这个估计得两个学期了，所以主要还是帮大家就是呃相当于是不管是复习也好，或者是你没有以前没有接触过的话，反正有个初步的一个认识了。

然后后面的话主要就是讲就是呃，三维空间里边的就是一些基本的一个集合图源，以及呃，以及相当于就是说我们怎么基于这些集合图源去做，呃距离计算或者是，呃三阶张量也会有转制的概念啊，就我看那个直播里有问了。

就三阶张量实际上什么概念，就是三阶张量的话，其实你发现这跟这个概念是一样的，就是比如这里边当然他的下标只说ijk，然后但是他转制的概念是跟这个一样的，就比如你可以对ijk转制呢。

这样的话就是把ijk这个两个符号相当对调一下，然后当你也可以跟j跟k转制，那这样的话实际上就是i然后kj，然后相当于k跟j两个符号对调一下，所以整个实际上就是转制的概念。

实际上就是你把两个下角标相当于互换，所以这个其实不存，这个不是二阶张量特有的，你不管三阶四阶五阶其实都存在这么转制的一些概念，但是说这里边有些这个运算实际上是可以拓展到高维，当然有些可能比较特殊。

然后有些可能不一定能到高维，有些可能不一定能行，然后那下面的话我们就来看看就是，三维空间里边一些常见的解除原主要包含的就是像这个点，比如点的话其实就是比如粒子法里边，其实就是一个particle。

你其实就是理解为k一个点，当然还有就是比如说线性的结构，线性主要是包含直线射线，或者这个线段，然后还有就是说像平面的结构，一些平面主要是包含平面，当然这个无穷大的一个平面，还有就是比如三角形。

当然就是三角形是因为图形里边用的非常的多，所以这里主要以三角形去讲，但还有其实还有四边形，当然你如果是四边形的话，其实你也可以理解为就是两个三角形，你可以拼成一个四边形，当然还有一种比较体的结构。

就是像球胶囊，然后这些你发现其实都是比较简单，因为整个运算还相对是比较容易，然后可以用这些基本的几何图案，然后去搭一些更复杂的一些结构，然后当然还有体的话，有四面体，然后后面还有包括AABB以及OBB。

然后我们后面来看一下，就是每个其实这样，后面我整个过的时候都会包含三种形式，一个就是它的几何的表示，就是它当然这是一个点，然后还有一个就是我们现在代码里边，去怎么去定义这么一个东西，就是比如对应一个点。

实际上三维空间里边，实际上就对应的一个XYZ的三维坐标，然后它当然还有一个它的一个参数化的形式，参数化的形式其实就是XYZ，这个点其实就很容易了，当然这里边你会发现。

为什么这里边要单独定一个点的这么一个结构，因为其实三维的一个，比如说我们很多vector，它其实也是三维的，但这里为什么要额外定义一个点呢，因为是这样，它实际上就是你大家学过C++的话。

你会发现因为其实这样，C++因为主要还是相当于以封装，包括一些封装啊，面向对象的一个概念，所以点因为它里包含的运算啊，跟我们传统的一个三维向量还是不太一样的，所以这里呢实际上额外定义了一个。

叫点的这么一个结构，这样的话可以用来比如说，额外的去实现一些距离计算的这么一些功能，然后接下来就是一些线性结构，然后像比如像直线，然后直线的话它其实就是，你可以相当于定义一个它的一个原点。

但这个原点其实它在哪个位置是无所谓的，就是你定义比如你往前一点往后一点，这个其实不影响它这个整个定义，然后呢除了这个原点之外呢，实际上还有一个就是它叫一个直线的一个方向，就是当你可以朝这边。

当然也可以朝这边啊，然后当你如果这个方向不一样的话，它对于哪个有参数坐标，那可能就不太一样，然后这样的话实际上整个直线的话，它实际上它的参数的话的一个形式就是，原点加上一个t。

然后乘上一个它的一个方向的一个向量，然后这个t它实际上对于直线的话，因为它是一个无穷，它是不是有限的，它实际上是无论是哪一端，它比如像上也好，像下也好，它实际上都可以延伸到无穷远处。

所以你发现它的那个参数坐标，它实际上就是从负无穷到正无穷，当然就是对应到代码的实现的话，你发现它实际上主要是两两个东西，一个就是对应的一个原点，但还有一个方向，然后你发现这个t实际上是隐含在里边。

因为t实际上是整个在计算的过程中，然后回去计算，实际上你是不需要把这个东西存下来的，然后只有就是后面比如说像，但你但比如你看那个像射线的话，其实，其实整个结构非常像，其实这里唯一不一样的是射线。

因为它只有一半，也就是说它的那个比如从它的参数的那个，就是参数形式的话，你可以看它相当于它的t必须是，比如说大于等于零，然后相当于可以到正无穷，但是不能到负无穷，当然这个是约定啊，你非要如果达标。

你要非要搞成负无穷，当然也没问题，但是一般来说就是我们约定，就是大家都比较容易接受的，实际上就按照正无穷的这个形式，然后呢，当然你看它内部的结构就是它的算法的那个定义啊。

就是它其实你发现跟那个是完全一模一样的，就是相当于一个原点，然后有个方向，然后也就是说其实包括这个t呢，因为也是这样，就是你定的因为这个结构上，你可以通过结构来判定它到底什么类型。

所以实际上你也不需要你显示的去把这个t给定义在里头，实际上所以你需要的这个数字类型，实际上只需要两个三维的一个数量，然后当然接下来还有就是线段，线段的话其实跟那个稍微有点不太一样，当然也有一种方式是。

线段实际上你也可以就说什么意思，就按前面那个参数化的那个形式啊，就是你比如定义一个原点，然后定义一个方向，然后当然它是0-1，你可以这么去定义啊，当然这里边参数就是线段的话，实际上更简单的一种方式。

实际上就定义它的两个端点，就是左端点跟右端点，然后呢，它相当于实际上是包含了两个三维的一个坐标，然后呢，实际上它的参数形式的话，实际上就是你中间任何一个点，它实际上都是用它的两个端点差值差出来的。

然后比如说那个你看就是说中间一个点，然后它两个权重啊，就是左标那个权重就V0对应的一个1-t，这么一个权重，然后呢，V1对应的一个t的权重，然后这两个权重加起来，你发现是始终是等于1的。

然后也就是它的那个t的那个范围，一直是处在左端点跟右端点，一个一个限制的这么一个范围内，然后它是不可能超出去的，所以这是一个端点线段的一个定义，然后总体来说，你发现这几个三个结构非常的相似啊。

然后唯一不一样的是这样，你如果从参数化的那个形式去看的话，它主要是体现在这个t的一个范围，因为像直线的话，其实就是t就从负穷到正负穷，然后射线的话，其实就是从0到正负穷，当然那个如果是线段的话。

其实就是完全就是从0到1的，如果按照这个定义，其实就是0到1的这么一个定义，然后那后面就是有一个平面的一个定义，就是你发现它其实最核心的，主要两个东西，一个就是你定一个原点，这样的话。

然后相当于你就是有个参照的一个标准，然后有了这个原点之后呢，你额外要知道就是整个平面的一个方向，它是朝哪个方向，那有了这个之后，然后也可以计算出平面上任意一个点，因为是这样，因为平面它有性质啊。

就是它任意一个点跟这个原点，它形成的这么一个向量，它实际上跟法向是垂直的，所以也就是说，实际上你任它任意一个点呢，实际上都可以表示成这个比如x-o，乘上它那个法向等于0，因为这是属于这个向量。

实际上在这里点乘的话等于0的话，代表它两个方向是垂直的，所以它任意一点，它实际上都要符合这么一个公式，当然进一步的话，你会发现就是这个东西如果展开之后啊，就你把这个两两相乘。

其实你发现其实这个东西就变成了，我们以前常见的这个平面的一个，就解析几何里面学的，就平面的一个表达形式，就是ax+by+cz+d，这么一个等于0这么一个公式，然后当这里边你发现。

其实就abc这几个参数啊，其实你把它单独拎出来的话，实际上就代表这个，整个平面的一个法线方向，然后当它整个算法的话，其实你发现其实就是只需要两个，一个是它的原点，第二个就是法向。

然后也就是这个x的那个任意一个点，它其实都是隐含在，因为你定义它的那个基本数解构，是不需要把那个x定义出来的，然后你相当于也就在计算的时候，你可以影式的去算，就是它到底是每一个点，然后这个在后面讲那个。

包括计算距离啊，相交的时候这个都会去讲这个东西，那还有一个就是三角形，然后这个三角形，因为你发现图形里边，这个用的非常的常见啊，其实因为整个图形包括渲染啊，什么其实都是，最最核心的其实就是三角形。

然后这里边三角形的话，其实最主要你可以发现，其实它就是三个顶点，然后但这里边一定要注意一个地方，就是三角形的三个顶点，它是有方向的，就一般来说就是通常我们约定的，实际上是它是一个逆时针的一个方向。

然后这个东西不能搞错，因为你这种如果搞错的话，就会导致就是你，比如后面你做碰撞检测呀，这个东西很有可能会导致，就是说你正反面搞错之后，你相当有可能会导致，它整个计算的时候相当会发生。

穿透就有这么一个问题，因为你这样的话，因为正常你比如说，你一个体表面的话，你是要通过它的表面方向，然后你判定它到底哪一面是朝外，哪一面是朝里，所以呢，也就是一般来说，你需要通过这个三角形的那个顺序。

就顶点的那个顺序来判定，就是你如果是这样，整个所有的表面的，所有三角形的那个方向，定义都是统一的，比如断顺针，断逆时针，那这样的话，实际上你是可以很容易的去判定，到底哪一面是朝里，哪一面是朝外。

但是如果你是乱序的，比如你搞不好有一些呢，你这个逆时针有一些顺针的话，这个很容易会导致你，后面整个计算的时候会非常容易出错，所以呢，一般来说我们就假设就是所有的三角形，当然其实这里不光三角形。

比如你四边形，或者是这个其他的一个多边形等等，一般来说也是这么一个约定，就是按照逆时针的方向，去定义它的一个顶点顺序，然后当然这里边就是你这样定义完了之后呢，实际上就是比如三角形里边，它任意一个点。

它实际上都可以表示成它的一个参数化的一个形式，然后当然主要是可以通过它的两条边，就是比如V1减去V0，然后V2减去V0，这两条边你可以去计算它内部的任何一个点，然后它这里边就包含两个参数坐标就是ST。

然后ST要符合就是因为这个参数三角形的话，其实它会符合就下面的一个约数，就是首先ST这两个加起来是等于1，然后同时呢ST这两个必须是属于0到1，这么一个范围，然后同时你发现就这个东西如果这么定义的话。

你按照你右手的法则，你可以去算一下就是V就是这个E0跟E1这两个右手法则，你一算它那个法线的话，实际上正好是朝外的，也就是说你可以指示你到底是哪一面是你的，相当于是比如说你一个体的一个外部。

然后它整个呃，代码的话就是你发现就很很简单，其实就是一个三个顶点的这么一个一个数组，然后呢就是有球的，球的话，其实主要是需要定义一个它的，比如它的一个中心点，然后它的一个对应的一个半径。

然后它的球的内部的每一点实际上就符合，就是说相当于你的整个距离要小于这个R的一个平方，然后你看代码的话，其实就是一个中心点加一个一个半径，然后另外这里边胶囊，这里边实际上在好多游戏里边。

游戏引擎里边用的会非常的多，因为它比如说像人体，它可以定义成一个布娃系统的话，它其实比如都是用一堆胶囊体，然后去组成一个复杂的一个人体结构，然后这个因为胶囊的话，你发现呃。

本账还因为它计算起来非常的一个方便，就是你看它整个定义的话，其实主要是定义两个东西，一个就是它的一个中心线，然后这个中心线实际上你发现它其实就前面我们已经定义了一个，比如它一个线段，一个线段的话。

实际上就是比如它的V0到V1，其实就两个端点，然后呢，你会发现它整个胶囊的话，它其实任意一点，就是任意一个表面点啊，到这个线段的一个距离，它实际上是一样的，实际上都是相当于一个它的一个半径。

所以整个它的一个计算就是后面比如说去做球胶计算啊，这个球那个什么，就是球距离计算的时候，其实你发现它跟整个球，因为球最大的一个好处，它实际上你发现它整个计算非常的方便。

就是你实际上只需要跟中心点算一下就行了，然后呢，胶囊实际上你发现相当于是对球的这个定义的一个拓展，就是它相当于把因为原先的话，它中心点实际上就是一个一个点，然后它实际上就把这个拓展成了一个线段。

然后这样的话，整个实际上就是可以用来表示一些更复杂的一个结构，但是呢，同时就整个它的一个计算呢，又没有太多的一个计算开销，然后当然后面就是我们做比如做弹性啊，做有限原理吧，这是这个是比较常见的。

就是像比如四面体的这种结构，然后它主要还是一样的，也是定义四个顶点，然后这里边其实还是一样的问题，就是这个顶点编号一定要注意，就是因为这个东西你顶点编号如果不注意的话。

就是有可能你比如算出来的一个体积可能是负的，然后你这个到时候比如说你整个计算压强啊，那如果体积负的话，你可能会有会出问题，所以就一般来说就是这比如这里画的可能是一个常见的一个标记的一个方式。

当这个你反正你只要按照你自己的形式，然后当然就是你只要保证就是统一的应该问题也不大，然后当这里边整个四面体的话，其实也会有一个参数化的一个表示的一个形式，就是当他这里的四面体的话就会有就会有三个参数。

就是比如UVW三个，然后呢，分别对应的实际上是101112，三个那个它的一个边，然后当它整个UVW的话也要符合，就是一定的约数，就是UVW它们加起来的和必须等于同时。

它们的一个值的范围必须是0到1这么一个范围，然后最后其实就是有两个就是非常就是比如说做碰撞检测呀，或者做那个啥的时候，非常常用的两个结构，一个叫ABB结构，然后这个因为在后面比如讲钢体的时候啊。

就是会会用到这个东西，然后因为它主要原因还就是为什么用这个结构呢，就是它主要原因还是因为它这个，其实你发现从它的定义可以看，其实它其实就需要两个顶面，然后呢也就它整个计算其实是非常方便的。

然后这样的话可以用这个ABB结构，来加速比如说你碰撞过程中，比如你想跟领域做一个查找，比如你预先领域把不太可能发生碰撞的一些物体，你可以用这个ABB的结构，你可以在相当于给它剔除掉。

然后当然ABB的好处就是，就是它实际上整个计算比较简单嘛，当然不好的地方可能就是说它整个，从包围核的角度来讲，它可能没有那么紧致，所以那就是还会有种比较常见的就是叫OBB。

就是OBB的话实际上就代表就相当于，它实际上你发现其实就是把ABB转了一个方向，所以那你发现就是它中心点，它以它那中心点呢，实际上就会有一个新的一个坐标器，然后这个标价呢。

就实际上就定义了一个新的那个一个标价，然后这个标价也就是说它实际上就是，比如说你的物体，你可能是沿着某一个朝向的，比如说它可能不一定是沿着标准的那XYZ的，这么一个方向。

那这样的话你实际上就可以用这个OBB，然后可以定义一个更紧致的一个包围核，那所以它这里边就包含几个东西，一个当然就是你的中心的那个位置，这个跟那个ABB是一样的。

但还有一个就是你发现这里边就必须得定义三个轴，当这个UVW啊，这个必须是垂直的，然后同时呢，一般来说呢，就是它实际上单位向量，也就它实际上你发现就UVW这三个向量组在一起的话。

实际上就变成一个类似于一个旋转矩阵，也就是说你相对于ABB，你旋转什么样的一个角度之后，然后就变成了这个OBB，所以你发现就UVW的最后可以张成一个，就这个新的标价实际就是一个旋转矩阵。

然后当然还有一个就是对应的它的一个长度，然后当然一般来说这个就是定义的实际上是它的一半，也就它以它中心点分别到它的一个各个面的一个距离，就是所以你发现就这个的话，它主要包含的结构，其实就发现有1234。

主要有四个三维向量，就差不多这么一个结构，然后呢，这样的话常见的一个基本结构，我们实际上就是已经定义的基本差不多了，然后呢，后面的话我们就来看看就是说，利用这些基本结构，然后看怎么计算，比如说计算距离。

或者计算它们之间的一些相交的一个计算，那首先就是这样，我们来看一下就是距离的一个计算，然后距离因为主要是类型的比较多，然后这里的比较常用的主要还是点到其他的一些图源的一个距离的一个计算。

所以这里边就这次课的话，主要会讲就是比如点到点的距离计算，然后呢，点到线条结构就是包含直线射线，比如线段的距离的一个计算，然后呢，另外就是还有点到平面，因为其实这里这个其实就是前面包含讲的这个。

所有的这个三维图源啊，所以呢，就是这里边主要还是讲点到这个前面那个图源的一个距离的一个计算，然后接下来我们就看一下，就是首先是点到点，这个其实就这一部分应该都很简单，因为大家其实都都都应该以前都都学过。

就是相当于两个点之间的一个距离，你实际上就是一个向量，你相当于两个向量相减，减完之后你算一个模，然后这部分其实不需要讲太多东西，然后后面的话，其实主要就讲一下就是点到一个线性结构的一个距离，然后这里边。

因为这样就是前面讲，就是说，不论直线也好，射线也好，或者是线段也好，其实你发现它，它的定义上，你发现它实际上是可以统一起来的，就比如说你如果是一段直线的话，你从参数坐标的角度来讲。

其实就是实际上它是正无穷，负无穷到正无穷，然后呢，你如果射线的话，实际上就是你T大于0，然后呢，线段的话就0到1，所以从这个特点上来讲呢，实际上就是你的点，你不论是算，你算到射线也好，或者直线也好。

或者线段也好，它实际上整个计算上，实际上是可以统一的，所以这里边我们是这样，我们的一个思路实际上怎么做呢，就是你现在就是你先，就你先不管它，比如说你不管是直线也好，或者射线也好，这个你先不管它。

到底是这个T到底是一个什么范围啊，所以我假设我统一的，先去计算这个P到上这个，线意结构上的一个投影点，然后呢根据这个投影点，因为你这个投影点算完之后呢，你实际上就是可以根据这个，就下面那个公式。

就是实际上就P减去V0，就是你会发现就P减去V0，这么一个线段，然后呢点成这个V1减去V0，这么一个线段的话，你可以相当于计算它的一个，T的一个参数坐标，然后呢，接下来你就可以根据这个参数坐标呢。

进一步的去判定，就是说你如果因为这样，你如果是直线的话，那你这个任意的那个参数坐标T，实际上都是符合你的要求的，但是呢如果你现在是射线，那你如果你出现这个T小于等于0的话，你如果小于0啊，所以这样的话。

你实际上可以把你的T给它截断，比如截断到这个0呢，实际上就相当于比如说你这个P，你投影到超出这个V0的这个部分之后，你实际上它离它最近的点，你发现它实际上就是V0，所以呢你相当于需要。

把这个最近点做一下，做一下截断，当然对于线段其实也一样的，如果线段的话，你比如你超出到这个上界，那这样的话你实际上需要，需要把它约束到这个V1的这个位置，所以基于这样的一个思想的话。

实际上整个计算的过程，实际上就比较简单了，就是你发现整个计算，实际上方式是一样的，就相当于你首先计算，就是你有一个原点之后啊，然后当然包含它的那个一个方向，就方向的话，其实就比如V1减去V0。

但这里边其实这样，你发现整个实现的话，这里边你可以不做规律化，就是不做规律化的话，因为其实这里边你发现它整个实际上，就是你如果做规律化的话，会有一个额外的一个开根号的，这么一个操作，然后这个操作呢。

实际上整个计算开销也是蛮大的，所以呢，实际上更方便的一种做法呢，其实你可以不做，就是你计算方向的时候，你不用去做算它的那个，就是实际的一个单位的一个向量，你直接就用V1减去V0，然后呢。

你相当在底下在除上这个，那个V1减V0之后，实际上这样的话，整个就可以避免这个，开根号的这么一个一步计算，因为整个开根号的话，那实际上消耗的那个代价，跟加减，比如跟加减这个。

实际上还是要比那个要复杂很多，所以这样的话，你发现这里边实际上就不存在一个，开根号的一个操作，然后这样的话，整个就是说，实际上第一步，你发现都实际上都是在算一个，参数坐标这个T，然后这个T算完之后呢。

后面就会根据，就是说你是到直线的距离，还是说是到射线的距离，然后呢，相当于对它进一步的去做一个，相当于去做一个截断，所以这里，比如这里是直线的话，其实你不需要做任何截断，实际上它。

你就是它投影过来的那个点，实际上就代表它的一个投影点，然后这样的话，你直接算一下，你这个P跟投影点的一个距离，实际上就代表的这个，P到直线的一个距离，然后当然这里边如果是射线的话，前面就讲了。

如果因为射线要求它的那个T是必须得，大于0的，也就是说这个时候如果，所以这里边额外的，如果对射线的话，要额外增加一个判断，就是如果你T小于0了，你这样的话，你需要把你的T就是截断到0。

然后也就这个直观上怎么理解的，实际上就是把你的位置，比如说你像这个P你截到了，投到了这个V0的，比如说外侧，那这样的话，你实际上就你把投影点给它相当于移到这个V0，也就是V0是你的一个投影点。

然后当然你如果是V0内侧的话，那就还是标准的一个T0点，就标准的一个投影点，然后这样的话就相当于约束完了之后，然后你再进一步的去算这个它的一个距离，所以你发现就是说从这个图上来看的话。

就是如果这个P是处在这个V0的外侧的话，其实它的离它最近的距离，实际上就是从P到V0的这么一个距离，然后当然那个再往里的话，其实就是到投影点的一个距离，然后当然进一步的就是如果去算它的一个。

P到比如说到一个线段的一个距离的话，其实也是一样的，就是如果比如说这两个投影点超出了这个V0，跟V1的这两个边界，那这样的话，其实这样就需要给它做一个截断，就把它分别截断到V0跟V1。

然后这个截断其实也是通过这个T，就是说你超出0了或者超出1了，就把它那个范围就截断到那个0跟1的一个范围，然后这个整个计算，所以你发现就是这样的话，整个形式上基本是差不多是统一的，然后后面的话。

其实就讲那个到平面的一个结构的一个计算，当然平面的话其实比较简单，因为其实也是一样的，因为平面它是一个无穷大的这么一个结构，所以就是说你从P你投影下来之后，你一定可以找到一个投影点，然后这个投影点的话。

下面有公式实际上就相当于是你这个P，然后呢，加上这一段实际上就是你可以看就是这个O减去P，然后呢，再点成一个法项的话，实际上在当然法项，但这里边是这样，为什么要除这个东西还是跟前面一样的。

如果你这个时候你相当于不是一个单位向量，那不是一个单位向量，如果单位向量，你实际上不需要除下面那些东西，但如果你不是单位向量的话，你实际上要除以下面一个东西，因为还是一样的问题。

就如果是很多时候我们为了避免开根号，所以我们一般不去算它的那个具体的，比如不去规范这个单位向量，那这样的话就底下需要除以一个，比如它的一个N的一个平方，然后呢，后面那一项呢。

实际上对应的就是你发现就是相当于是从P到Q的，这么一个那个方向量，所以对应的也就是说，从P到平面上的一个投影点，你就可以看到就是相当于P，然后加上这个对应的一个方向向量，然后呢。

就可以达到它的一个投影点，然后这个投影点，因为对于平面来说，你这个投影点实际上你可以处在任何的一个地方，所以呢，也不需要对它做一个相当于一个截断啊，所以就这样的话，你直接算出那个投影点之后。

你实际上就可以计算它们之间的一个一个距离，但这里边有个需要注意的一个地方就是，你会发现就我们这个实现的话，它返回的一个距离实际上是带符号的，就这个带符号会有一个什么好处呢。

就是因为比如说你正常定义一个平面，如果你一个钢体，比如你掉下来之后啊，你实际上是不希望，你除了判定它们是不是已经比如说发生碰撞了，或者是不已经穿透了，你还要判定一个东西。

就是你要判定它哪面是它的一个正面，哪面是它的一个反面，所以这样的话，实际上就是你要就是可以通过距离去判定，就比如说你在你假设你定义N的那个方向，是它的一个正向的距离。

那也就是说这个时候你如果是返回的是一个正向的距离，然后呢背面的话，你返回的是一个一个负向的一个距离，那这样的话你可以很容易的通过这个正符号，来判定到底它处在哪一面，所以你发现就是这个代码里面。

你发现它额外的增加了一个符号的一个判定，就相当于实际上返回的，叫做一个有向距离，它不是纯粹的一个绝对距离，因为绝对距离的话，它实际上是相当于是零到正无穷的这么一个量，但是呢有向距离。

它实际上就变成了一个负无穷到正无穷，也就是说下面那部分就是它的储待，它的负平面的话，它所有的距离定义都是负的，然后这个时候呢，是你实际上是可以通过它的符号跟它的那个距离，然后呢来。

比如说来避免它反正穿透啊，这个在后面整个计算的时候会更加方便，然后接下来就是我们看一下，就是点到三角形的一个距离判断，然后这个就是要复杂，就复杂一些，因为你发现整个三角形，它实际上是有界的。

相当于它有三条边，去限制它到底是处在哪个范围以里，然后这样的话就是你后面去算的话，就一定要注意，就是相当于你需要把这个根据你相当于，因为它的整个投影点有可能投影到这个三角形的一个外头。

所以这样的话需要根据它投影在哪个区域，然后去截断，就是跟前面线段也一样，类似的就是你需要判定，就是它到底截断到边还截断到点等等，就这个需要去做判定，所以这里面整个计算的话，你发现就是它实际上就演变成了。

这么类似于一个优化的这么一个过程，就是因为实际上就是你整个P到三角形的一个距离，它实际上就相当于你可以理解，什么意思，就是你比如说你V0V1V2里面，你可以找一个点。

然后那个点离这个P的那个距离是最近的，那这个过程本账其实是一个约束优化的这么一个过程，就是你发现就是比如这个，因为它任意一个点的实际上可以用它的一个参数坐标，就是XT的一个参数坐标，然后表示，然后呢。

它减去P的一个距离的平方，但一般为什么叫平方，还是还是一样的问题，就是我不希望去该根号，然后呢，降低整个计算的复杂度，所以也就整个你算距离的过程等效于，你相当于这么一个距离平方，然后呢。

去求它的一个极小值的这么一个问题，然后当这里面展开之后，你发现它实际上就是变成了一个叫，它是两次的，当然还有两个位置量，然后这样的话实际上对应的实际上是这么一个方程，然后需要去求它的一个极值，然后呢。

这样如果学过最优化的同学呢，其实这里边就是这个问题，求这个极值的过程等效于什么，等效于对这个Q相对相相当于对Q的这个针对TXT，算一个它的一个偏导数，然后呢，也就它的一个偏导数。

比如针对这个S算一个偏导数，针对这个T算一个偏导数，然后呢，整个所有的那个偏导数完了之后，它相当于它的极值那个地方一定是它导数是等于0，它导数等于0的那个地方，你相当于也才有可能取到一个一个极值。

当然导数等于0的地方不一定说你一定能取到极值，因为比如说像有你有些复杂的问题，它有可能有安点，那这那些地方它可能导数也等于0，但是呢，实际上它不是一个极值，但是呢，对于这个问题。

因为这个是一个二次优化的问题，这个问题它导数等于0的那个地方肯定是它的一个极值，这点是没问题的，所以就前面那个求极值的这个问题呢，等效于相当于对它做求导数之后。

然后相当于是解这么一个2元二次的这么一个限应方程组，然后呢，这个方程就很简单了，然后其实就是因为本科里面学的现代理的知识，然后就是相当于你其实有两个方程，然后两个位置量的这个东西，一般来说是。

存在为一解的，但这里边其实你发现就是如果解完之后，它实际上是相当于本质上是相当于这么一个情况，但这里边是不是存在，其实还有一些其他的一个因素在里头，就是这个。

后面会讲就是因为比如这里还得看就是你AC-B的平方，到底是不是等于0，这个东西AC-B这个东西到等于0是什么概念，就是你看一下，可以看一下前面AC这两个什么意思，就AC的话，A代表因为是代表它的E0。

然后呢，C代表的E1，所以这里AC-B如果等于0的话，你发现它实际上就等效于就是这个E0跟这个E1，它实际上是共限的，那这个时候你发现其实这个你说明你输入的这个三角形，距离求偏导的话该怎么做。

我不知道这个什么意思，什么叫对距离求偏导，就是你说这个相当于这个公式怎么求偏导吗，如果是问的是对公式求偏导的话，实际上就是这是高数里面学的那些概念，就是，就空的我们现在这样，我们现在考虑这个问题的时候。

我们先假设的实际上是一个无约数的这么一个问题，就是你现在这里不要去考虑这个ST是有范围的，就是因为这个东西是这样，就是范围我们在后面会进一步的，就是根据这个范围去确定，它到底最近的是点还是在边上。

就是说我们解这个问题的时候，我们假设就是一个无约数的，所以这里边也就是它实际上它任意一点都是可导的，导完之后呢，实际上就变成了就你即使去解这个问题的时候，其实也是一个无约数的这么一个问题。

所以它的那个ST你假设它的范围就是负无穷到正无穷，所以这里边它算的时候，这个你根据这个公式你去算出来的时候，它也有可能就超出啊，就是比如说它这里边ST，当然ST等于它有可能不满足啊。

然后甚至就ST的范围也是超出0~1，然后这个做完之后，我们在后面才会进一步的去根据这个值，然后去判定到底比如它是处在哪一个范围，因为这个因为前面我们相当于假设它是无约数的嘛。

那你这个东西你它的落点它实际上是不好控制的，就是你有可能外投有可能里投，但是呢这样的话对于整个你前面的计算是方便的，因为你无约数的话，你整个等效于一个二元二次方程，所以这个东西是只要AC-B。

就是你只要输入的那个三角形，是相当于是不存在退化的问题，因为你比如你输入就无效，那是另外一回事，那这个时候你要退化成点到边的这个距离计算，对这个因为现在你发现就这个东西。

其实跟那个前面钻平面是你发现其实是类似的，然后但是这里边我们需要有一个什么东西呢，就是必须这里边有两个ST的一个这两个参数坐标，因为前平面里边不存在这个ST的这两个参数坐标。

所以呢有了这两个参数坐标算出来之后，因为这两个参数坐标实际上是三角形特有的，然后有了这两个参数坐标算出来之后，后面我们才会进一步的去判定到底它是属于哪一个，就是跟它离得最近的到底。

比如说它是落在这个三角形一里还是落在外头，然后这样的话就是根据我们需要根据这个ST的这个，这个值去判定它到底是在哪个区域，所以这样比如这个把这个ST这两个东西，这两个参数我们假设把它拉平。

你发现它实际上可以把任意的一个平面，它实际上划分成了几个区域啊，就是0到6它差不多是七个范围，然后这样的话实际上就是我们可以通过这个ST的这个值，然后去判定就这个落点到底在哪个范围。

然后你发现就是在不同的范围，它离它的最近的一个点它是不一样的，就比如你发现如果是它落在它的落点是在，比如在这个0这个区域啊，那离它的最近的一个值肯定是在这个内部的，然后呢那现在我们换一个。

比如如果它的落点是落在了这个1的这个范围，那这样的话你发现它实际上它不可能是，跟内部点不可能是最近的，它最近的点肯定是在沿着这条边上，肯定有一个点离它是最近。

然后所以你发现就是这里边实际上划分这个范围之后呢，就你可以进一步的去确定它到底就这个点，离三角形的哪一部分最近，然后呢进一步的去算它的一个距离，所以这里边就是有这么一个判定的一个条件，就是什么意思就是。

因为S+T它正常你是要求是等于1的嘛，然后这个时候你可以根据这个它的范围，如果S+T因为这条线就是这条斜线啊，代表的实际上就是S+T=1的这么一条线，然后呢如果你比如说小于等于1的话。

它只可能是在比如下面那个区域，也就是它只可能是0 3 4，这四个区域里边相当于对应的去选一个区域，然后再进一步的去判定，然后当然如果它后面的比如说下面有个S。

然后这个S对应的是如果是S+T如果是大于1的话，那也就是只可能是在1 2 6这三个区域里边去选，然后当进一步的比如说你在里边还有几个，然后这里比如0 3 4 5这里边怎么去判定。

那这里边还要去根据首先我们根据S，比如说S是小于0，那S小于0的话对应的可能就是只有3跟4这两个区域，然后当这两个区域拎出来之后呢，我们再进一步的根据T如果T是小于0。

那这样的话它对应的应该是4这个区域，然后如果你已经选到4这个区域了，你发现你这个点最近的肯定是这个脚点，这个是没问题的，然后当然如果你这个时候你如果是落在。

比如说你落在区域5那这个离它最近的肯定是这条边，所以你发现就需要根据这些不同的一个情况，然后相当于最终去计算它这个点，到这个三角面片的最近的一个点，当这个点确定下来之后。

其实你发现这个参数坐标它实际上也是定下来的，就是ST它到底是就是符合前面规定的，就是S+T=1或者是ST是等，这里有个可能是这样，这里这个可能有点问题，这个应该S+T也不是等于1，这我写错了。

其实S+T应该是大于等于0小于等于1，其实也是这么一个范围，就S+T跟那个后面那个应该是一样的一个范围，这个是我那个BBT的问题，然后后面这样我到时候创创的时候我再改一下吧，这不是严格的等于1。

因为如果严格等于1的话，实际上就你只能约束在处在这么一条，一条它的一个边上的这么一个位置，所以这样的话整个三角形计算的话，实际上就这么一个一个过程了，然后后面的话我们就再看一下就是点到球。

点到球其实就刚才讲就比较简单了，实际上你就可以通过直接通过中心点，然后到那个P的这么一个距离，然后呢再减去一个R，然后这样的话就可以算出它的一个距离，然后你当通过这个公式你会发现。

其实它也是返回的也不是一个绝对距离，它返回的也是一个有向距离，就是什么意思，就是你如果你相当于你这个P如果是落在这个球的里面的话，它实际上返回的是一个负的这么一个距离，然后它这个P如果是落在外头的话。

返回的实际上是一个正的，这个其实主要也是为了后面，比如说你这碰到点侧呀，或者那个当你动力学的时候实际上是更方便一些，找到处，我其实不太懂了，就是就先找到锤珠，你还是说三角形的那个问题吗，这里边是这样啊。

就是可能我画的那个图可能有点歧义，就是这里边是这样，就这个P跟这个这三角形可能不是处在同一个平面，有可能不在同一个平面，所以当你如果立体的话，这个P可能是相当于比如说你这个三角形处在一个平面。

然后这个P呢，处在跟三角形不是在同一个平面上的一个点，所以你也不需要你去先算到O的这么一个点，然后再去因为这样的话，实际上整个计算你发现其实这样的这样开销有可能会更大一些，然后呢。

后面我们接着后面往下讲了，就是接下来主要讲一个就是点跟球，因为讲完了还比较简单的，然后接下来主要讲一下那个点跟这个交囊体，然后点跟交囊体的话，其实刚才前面的话也提了。

就交囊体基本上还是相当于是对球体的一个拓展，也就是说把原先的球体的作为一个中心点变成了相当于变成了一条中心线，所以这里边其实你发现它整个点到交囊体的一个距离计算，其实可以退化成什么呢。

其实退化成就是这个P就是点到这个线段，就这里比如V0V有个线段，因为这个线段的话前面已经介绍过了，就是相当于你可以很方便的，可以算出这个P到线段上任意点的一个，比如最近那个点的一个距离。

然后这个这样的话就是你点到这个线段算完之后，然后呢再减去这个半径R，那实际上就代表了这个相当于这个点到交囊体的这么一个距离，所以也就是交囊体，所以为什么之所以大家用的多实际上本账。

因为它其实就是退化成了一个点到线段的这么一个距离，然后也就是它整个计算量还是比较少，然后呢比较容易，然后整个而且同时加整个形状的也是比较，就是比较适合用来表示，比如像人体这种长条形的这种结构，所以呢。

一般很多游戏领域里面用的会比较多，然后下面的话主要讲一下那个点到四面体的这么一个距离计算，然后其实跟前面的问题还是一样的，就是就你发现跟三角形的问题类似，就是也就是它最近的点有可能发生在。

比如说你有可能是在内部啊，因为你如果这个点是在内部的话，其实就是在内部，但还有可能就比如说它最近的点就是可能是你某一条边上的最近的一点，或者是你整个不是说某一个面上的某一个点。

当然还有可能一种是你相当于是在某一个顶点，相当于离它最近的一个点，所以呢，这种情况实际上都都有可能发生，是这样是吧，然后呢去解决这个问题就是因为是这样，我们实际上如果我们去写CUDA的算法的话。

其实前面我们也讲，就是实际上我们尽可能的要减少这个各种分支结构，因为因为是这样本身那个像分支结构，其实对于CUDA这种并行计算语言的话实际上不太友好，所以呢，实际上这里边整个计算的时候。

我们看有没有可能尽可能的去降低它整个分支判断，然后比如说你前面的你分别的独立的去算，那这个可能就会成问题了，比如我先判定一下它到底是先离边最近的，还说我先离面最近的。

所以这样的话就会导致你实际上就是你会有大量的分支判断，导致你整个CUDA计算的时候，或者GPU你去预算的时候啊，有很多的线程可能是占不满的，所以这样的话就是我们最好是。

相当于整个把这个分支判断的那个去降下来，所以呢，这里边怎么去做呢，一个比较理想的实际上就是我们可以通过，因为整个四面体它实际上是包含四个面，所以就是说我们可以通过这个四个面，然后去判定就是说这个点。

它到底处在哪一个，相当于处在哪一个部分，比如说你相当于你现在这样，就是你如果所有的这个去判定的时候，相当于都处在它的一个负面，比如说你法相的另外一边，那你就可以断定它整个点实际上就是处在。

相当于这个四面体的一个内部，那这样的话，你这个时候你去计算的时候，其实你就很简单，其实你只需要跟四个三角形分别的去做一下那个距离计算，然后你找出最近的那个那个距离。

那实际上就代表它那个跟这个体的体表面最近的一个距离，然后当然如果它处在某些某些面的一个外面，那这样的话实际上怎么需要怎么去做呢，就是实际上你只需要针对，就是说比如说这里边有两个面，你去判定的时候。

比如你有一个一个点处在这个面的外侧，然后呢还处在这个那边的外侧，那这样的话，实际上你发现后面的两个面实际上是不需要去算的，你是只需要相当于这两个面，你跟它算一下这个跟点算一下一个距离。

然后你找一下那个最近的那个点，然后这个就很容易的就相当于就把一个计算量降下来，第二个呢，实际上你整个实际上就减少了整个分支判断的这么一个过程，然后呢，也就整个流程实际上就变成了，那你怎么做。

当然这个代码可能没有没有做到最简单啊，就是这里边，因为为了那个啥的那个简单，就是为了写写的简单，实际上他是做了冗余计算了，就是整个他实际上就按四个四个面分别做了一下距离，然后找了一个最近的。

然后当这个也能实现，但是这里边唯一的就是可能就多了几次，因为实际上我们事先可以前面可以讲到，我们先可以把比如负面的，比如说那个实际上可以给他事先给他剔除掉了。

这样的话就可以进一步的去降低他整个的一个计算的一个开销，当然这样的话，整个你发现，其实这里边因为整个是一个循环啊，所以当这个循环的话，整个分支结构实际上相对来说是比较少的。

然后当整个就也对于这个CUDA，就对GPU来说，相对来说还是比较比较友好的这种计算，然后那后面的话主要是ABB，然后ABB的话，其实跟整个跟那个什么是一样的，就是跟整个四面铁计算，你发现其实是类似的。

但是其实ABB其实更简单，因为ABB为什么更简单呢，就是因为他，其实你发现他可以沿着，根据他其实不需要你去算这个，你不需要这个点算这个平面的距离，因为他其实完全可以通过相当你比如X的坐标轴。

就你可以他根据X的一个坐标或者根据Y那个坐标，就可以去判定他到底属在哪一面，所以就整个计算的话，其实跟思路跟四面铁是一样的，但是他实际上他计算的话，因为他只需要三个轴XYZ三个轴分别的判断一下。

所以整个计算会更加的一个方便，所以这部分我就不展开讲了，实际上就是有兴趣的话，可以直接去看那个人代码里的一个实现，然后那OBB的话，其实跟ABB是一样的，然后因为他本质上实际上是一个相当于他旋转了。

一定的方向的这么一个ABB，所以你发现其实就是实际去做，比如在点到OBB的距离的计算的时候，实际去做的时候，一般来说你可以把先把这个东西给他转回来，因为那个在ABB上算非常快，然后就这样的话。

你实际上你可以先把比如说这个东西，你做一个T，然后这个T你发现他其实包含几个东西，一个是这个UVW这三个方向向量，然后还有一个就是他的一个平移，然后你发现这个整个T实际上是一个其次。

其次坐标下的这么一个变换矩阵，然后也就相当于你可以把这个你转换成一个标准的ABB，然后呢，你在这个地方你算完这个距离啊，或者算完那个相交测试之后，然后你给他再转回到相当于OBB的所处的一个坐标架。

所以这样的话，整个就是效率上会会比较高，然后当然OBB，所以这其实OBB就整个会在后面，比如做那个方向检测啊，啥的其实就会用，变换点会不会更快一点，变换点会不会更快一点，什么意思就是因为这里面下。

本账实际上就是变换点嘛，你相当于你乘上这个东西的话，实际上就相当于是把它的顶点分别乘上这个旋转矩阵的话，实际上它的顶点就坐标，实际上就是变到了一个，标准的一个坐标系下的这么一个矩阵。

所以这里实际上本账是顶点的一个变换，它也不是说你，我不知道你理解的是那个是其他啥意思啊，然后呢，前面讲完的话，就是，后面的话我们就接着讲那个，香蕉测试吧，然后香蕉测试的话。

主要在哪些场景里用的会比较多呢，主要还是就是像比如放射检测就钢体里边有，其实钢体里边会有大量的那个放射检测，所以这样的话实际上就需要，比如说你一个物体，比如说你穿透到另外一个物体之后。

你实际上就需要判定，就相当于它们出现的，香蕉的比如说的它的一个时刻，然后以及它的一个香蕉的一个点，然后这样的话，其实你发现就是因为复杂的那个放射检测，其实很多时候都可以简化成，比如说点跟。

比如说你点跟一个物体的一个碰撞，但是因为它整个实际上是一个时间的一个，动态的一个过程啊，动态过程是什么意思，就是相当于你比如从这个时刻，你到下一个时刻，也就是你相当于是，比如你即使一个点。

它实际上是连成的一条线啊，也就是你这个时候你要去检测，你相当于一个连续，比如说运动的一个一个线段上，它的某个它是不是存在某一个时刻，然后跟别的物体相当于要发生，碰撞了，所以这个时候也就是实际上你发现。

等效它实际上就是一个线性结构，跟一个其他的一个几个结构，比如说你跟平面也好，我跟你球也好，这个也就相当于退化成，这么一个相交的一个问题，所以就是说整个实际上就是这里，为什么我们要讲线性结构。

跟其他的一些基本结构图源的一个相交呢，主要就是因为这个原因，就相当于你如果是把时间这个维度加上的话，其实很多问题都可以退化成，就是其实一个线性结构跟别的一个，这个图源的一个相交的这么一个问题。

那下面我们就看一下就是，一些典型的比如像线性结构跟平面，它相交应该怎么去计算，然后当然这里边前面已经讲了，就是像直线的话，它实际上就是一个参数坐标，就是就是O加上TD这么一个参数坐标，然后当然平面的话。

其实就是ax+by+cz+b=0，这么一个平面坐标，那如果它们之间存在一个交点的话，是什么意思呢，就是也就是说你存在某一个直T，然后呢，它算出来的那个位置跟平面上的某一个，比如说你这个时候。

你比如说你比如个平面坐标，然后呢，正好跟平面上的某一个点是重合的，所以就相当于它实际上就是你平，这个对于某一个点来说，它实际上同时符合，就是说它平面的那个参数坐标方程，以及它这个它直线的参数坐标方程。

以及它平面的一个参数坐标方程，所以这样的话两个平，就两个这个同时成立的话，因为这个相当于实在也是等于，这个东西相当于它实际上是等效的，也就对于这个点，如果交点上来讲，它们这两个东西应该是等效的。

那这个时候实际上你发现，可以把直线的这个参数坐标，实际上就可以T到这个平面坐标里头，比如说它直线的话，它实际上表示成比如O+TD，然后当然这个T我们现在讲出来不清楚，但是呢就是实际上就可以替换到这里边。

然后它比如说它展开之后，其实就XY+Z，然后这样的话，实际上就我们可以根据这个，平面坐标的那个一个形式，然后这样的话我们可以去进一步的，去把这个T的那个值给它去算出来，也就这样的话就可以计算出它的一个。

参数坐标那个T的那个一个值，然后当这个值的话，其实会有一些问题，其实就是还是前面讲到的，当然这个是对应的是它的一个代码，就是你相当于就是根据前面那个坐标，就前面那个公式，然后就N*O+D然后除以ND。

然后这个你可以对一下，然后在这里边的问题就是还是要，一样的一个问题就是，因为像比如像这个D的那个方向，它有可能是跟平面是平行的，那这个时候你发现就底下那个值，就算底下那个参数坐标，就是那个方向乘上。

就平面的法项乘上它的那个，直线的一个方向，这两个乘起来之后，因为如果你这个直线，你跟那个平面是平行的话，你这样乘起来是零，所以你在代码实现的时候，其实要有个要特别注意的一个地方就是，相当于就变成就是。

代码实现的话，其实这里边有个注意的地方就是，你这个这个除以零要特殊的处理一下，不然的话就有可能会导致，你整个计算的话，直接被零除的话，整个这个结果可能是不对的，就这个因为有可能。

直接就是NAN的这种类似这种报错，所以这里边你看就我们这个代码的话，它其实有个特殊的处理，当然这个处理，你怎么实现其实都可以，就是比如说你这个时候你，如果它出现它是无效的一个值的话。

这里比如像我们这里实际上就反馈零，我们假设判定它实际上直接是，相当于不发生碰撞，但这个东西其实也有歧义就是，如果你这个直线一开始，直接就是在处在平面的内部的话，这个东西实际上这个时候你去判定。

它到底是属于相交还不相交的一个状态，这个时候实际上是有歧义的，所以这个反正取决于具体的一个应用，比如像有些应用的话，你可以假设，它处在一个不发生碰撞的一个阶段，当然也有些应用可能是需要你。

对于那种情况就是，处在发生的碰撞的每个阶段，所以这个实际上有可能需要根据具体应用，去调整这一些极端情况的一些测试，然后接下来的话，实际上就是比如线性结构，跟球的这么一个相交的话，其实也是存在多种情况。

就是比如像最左边那个的话，实际上就是相当于它存在两个焦点，然后像中间那个实际上就是存在，其实就存在一个焦点，然后包括最右边那个的话是存在，其实就可能是没有焦点了，然后当这个我看一下是不是那个网。

是不是不太好，我看一眼，哎，稍等我把网调一下吧，首先，(看錄影中)，(看錄影中)，(看錄影中)，這樣是不是應該好點了，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_17.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。



![](img/5575232c48126af6375bca201651ce6b_19.png)

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_21.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_23.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_25.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_27.png)

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_29.png)

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_31.png)

(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_33.png)

(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_35.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_37.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。



![](img/5575232c48126af6375bca201651ce6b_39.png)

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_41.png)

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_43.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_45.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_47.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_49.png)

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_51.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_53.png)

(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_55.png)

(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_57.png)

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_59.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_61.png)

(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_63.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_65.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。



![](img/5575232c48126af6375bca201651ce6b_67.png)

(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_69.png)

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_71.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_73.png)

(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_75.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_77.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。



![](img/5575232c48126af6375bca201651ce6b_79.png)

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)，(看錄影中)。

(看錄影中)，(看錄影中)。

![](img/5575232c48126af6375bca201651ce6b_81.png)