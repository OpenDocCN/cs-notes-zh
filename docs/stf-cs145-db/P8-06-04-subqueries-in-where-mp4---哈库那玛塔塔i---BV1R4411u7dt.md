# P8：06-04-subqueries-in-where.mp4 - 哈库那玛塔塔i - BV1R4411u7dt

这个SQL视频，和往常一样，主要包括运行实时查询。

![](img/3f7a592b952283e868e586835ed9d075_1.png)

介绍了WHERE子句中的子查询。像往常一样，我们从基本的select from WHERE表达式开始，现在我们将在条件部分添加子查询的能力。子查询是在条件部分内的嵌套select语句，我们将看到它们实际上非常强大。

和往常一样，我们将使用一个示范数据库，包含大学、学生和学生申请大学的数据。像往常一样。

![](img/3f7a592b952283e868e586835ed9d075_3.png)

我们将有四所大学，一堆学生，以及一些记录，显示学生们申请大学的情况。那么让我们直接进入第一个查询，展示WHERE子句中的子查询。这个查询找到了所有申请计算机科学专业的学生的ID和姓名。

这里是WHERE子句中的子查询。这个表达式在WHERE子句中查找所有申请计算机科学专业的学生ID。所以现在我们得到了这组ID。我们的外部查询是说，选择那些ID在这个集合中的学生，并选择他们的ID和姓名。

所以我们执行查询后发现，五个学生申请了计算机科学专业。现在其实我们可以不使用WHERE子句中的子查询来完成这个查询。我们来看看。我们可以通过将学生关系与申请关系连接来完成。因此，我们所做的就是这样。

在之前的视频中学过的内容。我们将学生和申请连接，写出连接条件，确保我们讨论的是同一个学生，确保他们主修的是计算机科学专业，并获取他们的ID和姓名。让我们执行查询。哎呀，出错了。我就知道会出现这个问题。这只是为了提醒你关于消除歧义的属性。

在select子句中的ID可以来自学生或申请，尽管值相同，我们仍然需要通过指定其中一个来消除歧义。所以我们写student.sid，然后执行查询。好，现在我们看到返回的学生比使用子查询时更多了。让我们。

回去看看。我们这里有五个结果，还有更多的结果，但是这些额外的结果实际上是重复的。例如，我们有两个相同的记录，一个是1，2，3，Amy。原因是Amy实际上申请了多个大学的计算机科学专业。所以如果我们回去查看申请数据，我们会看到，Amy的记录有两条，分别是1，2。

三个学生同时申请了斯坦福和伯克利的计算机科学专业。希望她选择斯坦福。无论如何，这就是为什么Amy的记录出现了两次。

![](img/3f7a592b952283e868e586835ed9d075_5.png)

在连接中，因为她申请了两次。回到我们使用子查询的地方，我们只是看学生的ID是否在集合中。好吧，所以当我们使用`join`时，得到的答案基本相同，但我们有一些重复的值。当然，我们可以通过添加`distinct`来解决这个问题。我们运行查询，现在得到的结果和使用子查询时一样。

让我们看看一些其他类似的查询，再次关注重复项的问题，因为这会变得有点棘手，正如我们将要看到的那样。这个查询与之前的非常相似，查找那些申请计算机科学专业的学生，但这次我们只获取学生的。

学生的姓名而不是他们的ID。所以我们执行查询，找到了我们之前的五个学生。我只想提到这两个Craig是两个不同的Craig。如果我们回到原始结果，会看到三个四五Craig和五四三Craig。所以回到这里，我们找到了那些计算机科学专业的学生的姓名。

现在，和我们之前做的类似，让我们用`join`来写这个查询，而不是在`WHERE`子句中使用子查询。所以这里是`join`，我们将学生和申请表通过学生ID连接，计算机科学专业照常，唯一的不同是我们只选择了姓名。我们执行查询，结果又是这样。

我们得到了比之前更多的结果，因为当一个学生同时申请了两个不同的地方的计算机科学专业时，我们会得到两份副本。就像之前做的那样，我们可以通过添加`distinct`来去除重复项。不过这次发生了一些不同的情况。这次，当我们去除重复项时，结果只有四个，而之前有五个。

这是因为我们之前将学生ID包含在结果中，所以Craig的两个实例被认为是不同的Craig，并没有导致重复项被删除。我们可以看到回到这里，Craig和Craig，但在这个结果中，因为我们只保留了姓名，这两个Craig的副本合并成了一个结果。

现在我们可能会想，为什么我们这么在意重复项呢？让我们来看一个例子，看看重复项到底有多重要。我们将再次执行完全相同的查询，查找申请计算机科学专业的学生，但这次我们检索的是这些学生的GPA，而不是他们的ID或姓名。

假设我们感兴趣的是分析选择申请计算机科学专业学生的GPA。那么，像往常一样，我们运行查询，得到五个结果，这五个学生的GPA如下。再一次，我保证这将是最后一次，我们使用`join`而不是子查询来做这个查询。

好吧，我们已经有了学生和申请的连接，基于学生ID，计算机科学专业，返回GPA。再次强调，由于有学生申请计算机科学专业多次，我们得到了比五个结果更多的结果，数量相当大。

我们再次遇到重复的情况。那么问题就出在这里。如果我们用这个结果来计算平均 GPA，我们会把一些学生算多次，显然这不是我们想要的。显然，我们希望每个申请了计算机科学（CS）的学生只算一次，在计算平均 GPA 时就应该是这样。

在我们之前的查询中，得到了五个结果，代表五个申请了计算机科学（CS）的学生。当我们进行连接时，我们得到了太多结果，但这次当我们使用 `select distinct` 时，又会遇到问题，因为其中一些学生的 GPA 是相同的，现在我们只有四个 GPA，而不是五个。

所以我们应该这样做，如果现在计算平均 GPA，就会出现问题，因为我们没有将某个学生的 GPA 考虑进去。所以在这种情况下，无论是使用 `distinct` 版本，还是不使用 `distinct` 的版本，都无法给出正确的 GPA 数量，两个版本都无法给出正确的平均值。唯一的方法是：

要得到正确的重复数，我们应该使用包含子查询的 `WHERE` 子句版本。接下来我们将移到一些不同的例子，这些例子同样使用了 `WHERE` 子句中的子查询。你可能还记得在上一段视频中，我们学习了差集运算符，当时我们有一个查询。

我们可以使用差集运算符来写这条查询，在 SQL 中叫做 `except`，但没有差集运算符我们是无法写出这个查询的。我们尝试写的查询是：找出那些申请计算机科学（CS）专业但没有申请电子工程（EE）专业的学生。现在我们在 `WHERE` 子句中使用了子查询。

我们可以在不使用 `except` 运算符的情况下写这个查询，这就是它。这个查询查找那些其 ID 在申请计算机科学（CS）专业的学生 ID 集合中，但其 ID 不在申请电子工程（EE）专业的学生 ID 集合中的学生。我们来运行一下查询，结果发现：

有三名学生申请了计算机科学（CS），但没有申请电子工程（EE）。顺便说一下，让我向你展示一个稍微不同的写法，实际上是完全相同的查询。你可以看到，我们使用了 `not in` 关键字组合，指定 ID 不在这个集合中。实际上我们可以通过写 `SID` 在集合中，然后对结果应用 `not` 来达到相同效果。

好的，执行后，我们得到了完全相同的结果。在 SQL 中，写同一查询有多种方式是很常见的，稍后我们将看到更多的例子。到目前为止，我们的子查询示例使用了 `in` 和 `not in` 来测试子查询生成的集合中的成员资格。接下来的例子将会...

现在展示的是我们可以如何在子查询中应用 `EXISTS` 运算符，仅仅是为了测试它是否为空。这里是查询。这条查询使用 `EXISTS` 来检查子查询是否为空或非空，而不是检查某些值是否存在于子查询中。这里引入的另一个新结构是：

这被称为关联引用。在子查询内部，我们将引用一个来自子查询外部的值C1。那么我们来谈谈这个查询是如何工作的。首先，让我告诉你这个查询试图返回的内容。这个查询将找到所有符合某些条件的大学。

在我们的例子中，提醒一下，我们有斯坦福、伯克利、麻省理工学院和康奈尔。所以我们应该返回的两个大学是斯坦福和伯克利，因为在每种情况下，都有另一所大学位于同一个州。那么这个查询是如何工作的呢？它表示我们将先获取大学，然后。

对于每所大学，我们将检查是否存在另一所大学，并且我们将称之为C2，其中C2的州与C1的州相同。这有点类似于我们在处理自连接和表变量时看到的情况，但现在变量出现在外部查询和内部查询中。

那么我们执行查询并看到得到了错误的答案。那是故意的。问题出在哪里呢？当我们执行这个查询时，C1和C2可能会绑定到同一所大学。所以每个大学都有其他大学在同一个州，如果另一个大学是同一所大学的话。我们需要做的是，在子查询中添加一个进一步的条件，要求C1和C2是。

具体来说，C1.c_name不等于C2.c_name。让我们执行查询，现在我们得到了正确的答案。现在，让我们看看在子查询中使用exists构造的其他用途。如果你已经对C2有所了解，并且有人要求你编写一个查询，用来。

获取某种类型的最大值。你可能首先想到的是使用max操作符，但我们还不知道max是什么。我们将在后续的视频中学习这一内容，事实上，许多计算最大值的查询可以通过子查询来实现，这是我们的第一个例子。这个例子是。

寻找具有最大入学人数的大学，我们将通过子查询和not exists操作符来实现。具体来说，我们将找到所有大学，其中不存在入学人数比第一所大学更多的其他大学。那么我们继续执行查询并。

出人意料的是，我们得到了伯克利作为结果。所以这是我们可以在寻找最大或最小值时编写的一种查询形式。让我们举个例子，寻找GPA最高的学生。所以我们将其修改为学生姓名，而不是大学，我们将关注学生而不是大学。否则，查询将会找出同一州内的另一所大学。

这个查询的形式将保持非常相似。我们也将查询学生，最终我们将以GPA替代入学情况。因此，这个查询的工作方式是，它表示我想找到所有学生，条件是没有其他学生的GPA比该学生高。我们执行查询并得到四个结果。

这似乎很奇怪。实际上，这并不奇怪。让我们把GPA添加到查询中，我们就能确切地看到发生了什么。我们可以看到，这四个学生的GPA都是3.9，因此他们都并列拥有最高GPA，并且非常具体地，它准确地执行了查询。

现在让我们看看是否可以在不使用子查询的情况下写出相同的查询。像往常一样，如果我们想写一个没有子查询的查询，我们需要做某种类型的连接。所以我们要找的是GPA最高的学生，因此我们需要连接两个学生关系的实例，正如我们在这里所做的那样，然后我们将应用一个条件，即第一个学生的GPA高于第二个学生的GPA。

我们运行查询，哇，得到了很多结果。也许我们的问题只是重复数据。所以当结果看起来太多时，我们首先做的事就是加上`select`这个条件。嗯，那样并没有解决问题。

这样做也无法解决问题。实际上，这个查询从根本上是错误的，我们不能仅通过使用连接来写出找到GPA最高学生的查询。这个查询实际上做的是，找到所有存在其他学生GPA较低的学生。换句话说，它正在找到所有

现在让我们看一下在WHERE子句中使用子查询时可以使用的另一种新构造，我们将继续使用找到GPA最高学生的相同查询。这个查询使用了all关键字。all告诉我们的是，代替检查一个值是否不存在另一个学生的GPA高于这些学生。

在`in`或`not in`的结果中进行子查询时，我们将检查值是否与子查询的所有结果具有某种关系。在这里，在这种情况下，我们检查GPA是否大于或等于子查询返回的所有学生GPA的元素。如果某个学生的GPA。

如果确实大于或等于所有GPA，那么该学生在数据库中的GPA是最高的。我们运行查询，将得到相同的四个GPA为3.9的学生。现在让我们尝试以稍微不同的方式写这个查询，只是为了有趣并说明一些概念。再次，我们将尝试找到数据库中GPA最高的学生。

这是我们这次要做的。我们不再使用大于或等于所有，而是使用大于所有。因此，我们将找到所有GPA高于其他任何学生的学生，方法是说GPA大于所有其他学生的GPA，除了那些有最低GPA的学生。

数据库中不是我们正在寻找的学生，通过说ID不相等来排除这些学生。我们运行查询，结果为空。我们再想一想，这实际上是查询的正确结果。查询本身是错误的。这个查询在寻找所有没有相同GPA的学生。

这个学生的 GPA 高于所有其他人的 GPA。记得我们有四个学生的 GPA 是 3.9，所以这些学生都不符合查询条件，其他任何学生也都不符合。所以这是我们想要的查询的错误写法。现在，如果我们知道每个学生的 GPA 都是唯一的，这个查询就是正确的。

学生有相同的 GPA，抱歉，如果我们知道每个学生的 GPA 都是唯一的，这个查询才是正确的，因为那时会有一个学生拥有最高的 GPA。那么我们就修改查询改为寻找那些拥有最高入学人数的学院，因为在我们的数据库中，每个学院的入学人数是唯一的。

具有唯一入学人数。所以我们将查询修改为获取学院的 C-name，而不是学生的 C-name，并且我们希望入学人数大于或等于所有其他学院的入学人数。我们接近完成了，只要把这部分修改为 C-name，把另一个修改为 C-name，就完成了。

那么我们在这里问的是什么呢？我们在寻找所有那些入学人数大于所有其他不同学院的入学人数的学院。我们运行查询，结果显示伯克利，这正是我们预期的结果。到目前为止，我们已经看到了关键词 all 的用法。

检查一个值是否与子查询的所有结果有关系。还有一个关键词 any，它是 all 的伴侣，不过它不是要求必须满足所有集合元素的条件，而是要求至少满足集合中一个元素的条件。所以我们现在要做的是，执行相同的查询，但我们会稍微修改一下写法。让我先输入代码，然后再解释。

这里我们要说的是，获取所有学院，这些学院的入学人数不小于任何其他学院。换句话说，没有其他学院的入学人数比它大。我们运行查询，得到伯克利作为结果，这正是我们预期的结果。

想一想，这如果你熟悉谓词逻辑的话，就是一个等价式，当你说“for all”时，它等价于“不存在”，在任何情况下都不成立。如果你没有跟上，不用担心，继续运行查询，我们再次得到结果，伯克利。

再次强调，all 是对子查询结果中的每个元素进行条件测试，只有当条件满足每个元素时才为真，而 any 则只要求条件满足一个或多个子查询中的元素。让我们用 any 再做一个查询。这个查询找到所有不是来自最小学院的学生。

数据库中的高中。那么我们在这里要查找的是所有学生，其中他们的高中规模大于其他任何高中的规模。换句话说，如果有其他学生的高中规模比这个学生的小，那么这个学生会被返回。我们运行查询，结果就出来了。

如果你回顾数据，你会发现，确实有些学生来自人数为200人的高中，所以在我们的结果中，每个来自比这个更大高中的学生都会被包含在内。某些系统，尤其是当前的SQL Light，不支持`any`和`all`操作符。

我们并没有失去表达能力，我们只是需要以稍微不同的方式来写这些查询，通常使用`exists`或`not exists`。那么让我们看看不使用`any`的同一个查询。我们这样做：我们寻找那些存在某个其他学生的记录，那个学生的高中人数比该学生的小。

这将给我们完全相同的结果，我们会看到，得到的学生集合是相同的，没有来自200人以上高中的学生，但我们得到了其余所有学生，而没有使用`any`或`all`。仅为了强调，`any`或`all`在写查询时非常方便，但它们并不是必须的。

事实证明，我们总是可以写一个查询，使用`any`或`all`中的任何一个，或者都不使用。通过使用`exists`操作符或`not exists`来代替。作为一个压轴查询，让我们重新审视一下这个查询，找出那些已经申请了计算机科学（CS）专业的学生，且没有申请电气工程（EE）专业的学生，现在我们将使用`any`来写这个查询。

操作符有两个实例，现在让我们回顾一下我们使用`in`和`not in`写的查询，看看我们得到了三个结果：Helen，Irene和Craig。现在，让我们看看使用`any`和`not equal to any`的查询结果。我们发现，这些学生的SID属于那些申请CS的学生的SID集合。

这些学生已经申请了CS专业，且他们的SID不等于任何已经申请EE专业的学生SID，现在让我们运行这个查询。好吧，我们得到了错误的答案，而这次也是故意的，让我们仔细看一下这个查询请求的内容。这个查询要求找出那些他们的ID在申请CS的学生ID集合中的学生。

这一切都很好，但问题出在这里。这里发生的是，我们的意思是我们希望条件检查EE学生集合中是否有任何元素不等于这个SID，因此，实际上，只要有任何一个人申请了EE，第二个条件就成立。

这与我们正在查找的学生不同，当然这种情况是常见的，因此我们在这里犯了一个错误，实际上使用`any`和`all`操作符并总是得到正确的答案是非常棘手的，尤其是在你不能直接通过目测结果来检查时，正确的答案。

我们希望的公式是，这个SID不等于该集合中的任何成员，换句话说，对于这个EE申请集合中的每个成员，那个值不等于我们将要返回的学生的SID。

![](img/3f7a592b952283e868e586835ed9d075_7.png)

然后我们运行查询，得到了正确的答案。
