# P7：05-01-relational-algebra-1.mp4 - 哈库那玛塔塔i - BV1R4411u7dt

这是我们学习关系代数的两部视频中的第一部。关系代数是一种形式化语言，它是一种代数，构成了像SQL这样的实现语言的基础。在这部视频中，我们将学习关系代数查询语言的基础知识，以及一些最常用的操作符。在第二部视频中，我们将学习一些额外的操作符和关系代数的其他表示法。

![](img/735696dfc3f70f4297457a50431c1618_1.png)

现在，让我们先回顾一下我们之前视频中关于关系查询的内容，查询关系型数据库时，查询操作是作用于关系的，并且查询的结果也会是一个关系。所以，如果我们写一个查询，假设是作用于这里描绘的三个关系，那么这个查询的结果将会是一个新的关系。事实上，

我们可以对这个新关系提出查询，或者将这个新关系与我们之前的关系进行组合。所以让我们从关系代数开始。在本视频中的示例中，我们将使用一个简单的大学招生数据库，包含三个关系。第一个关系是大学关系，包含大学名称、州等信息。

和大学的注册信息。第二个关系是学生关系，包含每个学生的ID、姓名、GPA以及他们所就读高中的规模。最后，第三个关系包含关于学生申请大学的信息。具体来说，

学生的ID、他们申请的大学名称、他们申请的专业，以及该申请的决策。我已经在这三个关系中标出了键。提醒一下，键是一个属性或一组属性，其值是唯一的。所以在我们的示例中，我们假设大学名称是唯一的，学生ID是唯一的，

并且学生只会在某个特定专业上申请每所大学一次。所以在整个视频中，我们会在幻灯片的底部展示这三个关系的图示。关系代数中最简单的查询是仅仅查询一个关系的名称。所以，例如，我们可以写一个查询，student，这在关系代数中是一个有效的表达式。

如果我们在数据库上运行这个查询，我们将得到学生关系的副本，作为查询的结果。非常简单。接下来发生的事情是，我们将使用关系代数的操作符来过滤关系、切片关系和组合关系。接下来，让我们通过这些操作符。第一个操作符是选择操作符。选择操作符用于从关系中选择某些行。

选择操作符用希腊字母σ表示，带有一个下标，表示用于过滤行的条件。我们从关系中提取数据。这里我们通过三个示例来说明。第一个示例表示我们要找出GPA大于3.7的学生。要用关系代数表示这个表达式，我们写出σ。

这是选择操作符，带有我们要过滤的下标：GPA大于3.7，以及我们应用该选择谓词的关系。因此，这个表达式将返回一个包含GPA大于3.7的行的学生表子集。如果我们要筛选两个条件，只需将条件在σ的下标中进行与运算（AND）。

所以，如果我们想找出GPA大于3.7且高中规模小于1000的学生，我们会写：选择GPA大于3.7。我们使用逻辑与操作符（^），高中规模小于1000。然后我们将其应用于学生关系。最终结果将是一个包含满足条件的行的学生关系的子集。

如果我们想找出申请斯坦福大学计算机科学专业的学生，我们将对申请关系应用选择条件。我们再次写出σ，接下来下标会是学院名为斯坦福，专业是计算机科学，再次使用与操作符（AND）。这个条件将应用于申请关系。

它将返回作为结果的申请关系的子集。选择操作符的一般形式是我们有σ，一个条件作为下标，然后是关系名。结果返回的是关系的子集。接下来是投影操作符。

所以选择操作符挑选出某些行，而投影操作符挑选出某些列。假设我们对申请感兴趣，但我们只想知道这些申请的ID列表和决策。投影操作符是用希腊字母π符号表示的。

现在，下标是我们想提取的列名列表。我们写出ID，抱歉，是学生ID和决策，然后我们再次应用于申请关系。最终返回的将是一个只包含两列的关系。它将包含所有申请的元组，但仅包含学生ID和决策这两列。

所以投影操作符的一般形式是投影符号，后面跟着一系列属性，可以是任意数量，然后是关系名。如果我们想同时选择行和列呢？

所以我们只想要一些行，也只想要一些列。现在我们将组合运算符。记住，关系查询会产生关系。所以我们可以写一个查询，例如，使用选择运算符选择那些GPA大于3.7的学生。这就是我们如何操作的。现在我们可以取出整个表达式，它会产生一个关系，然后我们可以对其应用投影运算符，从中提取出学生ID和学生姓名。

好的，实际上我们现在看到的是选择和投影运算符的一般情况，并不完全是我最初告诉你的那样。我稍微欺骗了你。当我们写选择运算符时，它是一个带有条件的选择，适用于关系代数的任何表达式。如果它是一个大的表达式，我们可能需要加上括号。类似地，投影运算符是从关系代数的任何表达式中提取出的属性列表。

我们可以根据需要随意组合这些运算符。我们可以有选择运算符叠加在投影运算符上，选择，选择，投影，等等。现在让我们来谈谈关系代数查询结果中的重复值。假设我们请求一个列出所有申请过的专业及其决策的列表。那么我们将它写作在申请关系中投影专业和决策。

你可能会认为，当我们得到这个查询的结果时，我们会有很多重复的值。所以我们会有CS，yes，CS，yes，CS，no，E，E，S，E，E，no，等等。你可以想象，在一个大型现实的申请数据库中，会有成百上千的人申请专业并且有yes或no的决策。

关系代数的语义规定，重复项总是会被消除。所以如果你运行一个查询，结果中逻辑上会有很多重复值，你只会得到每个结果的一个值。这实际上与SQL语言有所不同。SQL基于所谓的多重集合或袋（multi sets or bags），这意味着我们不会消除重复项。

而关系代数基于集合本身，重复项会被消除。也有定义多重集合或袋式关系代数，但我们在这些视频中只需考虑集合关系代数即可。我们用来组合两个关系的第一个运算符是叉积运算符。

也被称为笛卡尔积。这个运算符的作用是它接受两个关系，并将它们“粘合”在一起，使得结果的模式是两个关系模式的并集，而结果的内容是来自这两个关系的每一对元组的所有组合。

事实上，这就是你可能在小学时学过的普通集合叉积。所以我们来谈谈，例如，做学生和申请的叉积。如果我们做这个叉积，为了节省画图时间，我就把这两个关系粘在一起。所以如果我们做叉积。

结果会是一个大关系，包含八个属性。学生和apply关系中的八个属性。现在唯一的小技巧是，当我们将两个关系连接在一起时，有时它们会有相同的属性名。我们可以看到，SID在两边都有。

作为一种记号约定，当进行笛卡尔积操作并且有两个同名属性时，它们会加上它们来源关系的前缀。因此，这个会被称为student.SID，而这个则会被称为apply.SID。所以，再次。

我们将两个具有四个属性的关系通过笛卡尔积连接在一起，得到一个具有八个属性的结果。现在让我们谈谈这些内容。所以假设学生关系中有S个元组，那就是有多少个元组。而apply关系中有A个元组，笛卡尔积的结果将包含S乘A个元组。

它会为学生关系和apply关系中的每一对元组组合生成一个元组。现在笛卡尔积看起来可能没有太大帮助，但有趣的是当我们将笛卡尔积与其他操作符一起使用时。让我们来看一个大的例子。假设我们想要获取高中规模大于1000、申请了计算机科学专业并被拒绝的学生的名字和GPA。

好的，来看看。为了运行这个查询，我们必须访问学生和apply记录。所以我们将以student和apply的笛卡尔积作为起点。现在我们有了一个包含八个属性的大关系，以及之前描述的所有元组。但现在我们要开始让事情变得更有趣，因为我们要对这个关系进行一个大的选择操作。

选择操作首先会确保它只连接那些指向同一个学生的学生和apply元组。所以为了做到这一点，我们写出student.SID等于apply.SID。这样，我们就把笛卡尔积的结果过滤掉，只保留那些有意义的学生和apply元组的组合。现在我们需要做一点额外的过滤。

我们说过我们希望高中规模大于1000，所以我们在高中中做了一个操作。我们希望他们申请了计算机科学专业，所以条件是major等于CS。我们得到了一条很大的查询。最后，我们希望他们被拒绝，所以条件是decision等于，我们就用R表示拒绝。现在我们有了这个巨大的查询，但这正是我们想要的，除了还有一件事，那就是我说我们只想要他们的名字和GPA。

所以最终我们在这里加上一个大括号，并应用投影算符来获取学生姓名和 GPA。这就是关系代数表达式，它生成了我们用英文编写的查询。现在我们已经看到，笛卡尔积允许我们组合元组，然后应用选择条件以获得有意义的元组组合。事实证明，关系代数包含一个称为自然连接的算符，它基本上用于完全相同的目的。

自然连接的作用是执行笛卡尔积，但它会对所有同名的属性强制执行相等性条件。因此，如果我们正确设置了模式，例如我们有学生 ID 和学生 ID，它们的含义相同，那么在创建笛卡尔积时，它只会组合那些学生 ID 相同的元组。

此外，如果我们添加大学关系，我们可以看到这里有大学名称和这里的大学名称。如果我们将大学关系和申请关系的元组合并，它只会合并那些描述相同大学的元组。再者，自然连接还会去除这些烦人的同名属性。所以，当我们将学生和申请通过自然连接合并时，我们只会合并那些学生 SID 与申请 SID 相同的元组，因此不需要保留两列。

这两列是重复的，因为它们的值始终相等。所以自然连接算符是使用蝴蝶结符号表示的，这只是一个约定。如果你仔细查看文本编辑器中的内容，你会发现这个符号。现在让我们做一些例子。让我们回到之前的查询，查找那些来自大高中、申请计算机科学专业并被拒绝的学生的姓名和 GPA。

所以现在，我们不再使用笛卡尔积，而是使用自然连接，就像我之前说的那样，它是用蝴蝶结符号表示的。这样一来，我们在进行自然连接时，就不需要再写出那些强制相等的条件，因为它会自动处理。

一旦我们完成了这一点，我们需要做的就是应用其余的条件，即高中人数大于 1000、专业为计算机科学且决定为拒绝。我们再次称这个查询为 R，然后由于我们只需要获取姓名和 GPA，我们会写出学生姓名和 GPA。

好的，这是使用自然连接查询的结果。所以如你所见，这比原始的笛卡尔积查询要简单一些，通过正确设置模式，自然连接非常有用。现在，让我们给查询增加一个复杂条件。假设我们只关心那些申请了大学且录取人数超过 20,000 的应用程序。因此，在我们的表达式中，我们引用了学生关系和申请关系，但尚未使用大学关系。

但是，如果我们想在注册表上进行筛选，就需要将学院（college）关系引入其中。结果证明，这可能比你想象的更容易。我们只需要删去一些括号，接下来我们将把学院关系与我们已经拥有的两个关系进行连接。现在，技术上来说，自然连接是一个二元操作符。

人们经常在没有括号的情况下使用它，因为它是结合性的，但如果我们较为严格地讨论这个问题，我们可以加上括号，这样就没有问题了。现在我们已经将三个关系结合在一起，并且要记住，自然连接强制要求共享属性相等。

更具体地说，这里的学院名称将被设置为与应用的学院名称相等。现在，一旦我们完成了这个操作，我们就得到了所有需要的信息。我们只需要添加一个额外的筛选条件，即学院的注册人数大于20,000。通过这个条件，我们就解决了查询问题。总之，自然连接将关系结合起来。

它会自动设置相同名称的属性值相等，然后删除重复的列。实际上，自然连接并没有为关系代数增加任何表达能力。我们可以通过笛卡尔积来重写自然连接。让我在这里展示一下这个重写过程。如果我们有，并且现在我将使用两个表达式的一般情况。

一个表达式的自然连接与另一个表达式实际上等同于对第一个表达式的模式进行投影。我就称它为E1。现在将第二个表达式的模式联合起来，这才是真正的联合。意味着如果我们有两个副本，我们只保留其中一个。现在在选择操作上，我们将设置所有共享属性，使得第一个表达式的共享属性等于第二个表达式的共享属性。

所以我会写成E1 A1等于E2 A1，并且E1 A2等于E2 A2。现在这些是属性名称相同的情况。我们将这些属性设置为相等，并且这是应用于表达式一与表达式二的笛卡尔积。所以，虽然自然连接没有提供额外的表达能力，但它在符号表示上非常方便。

我将在本视频中讲解的最后一个操作符是θ连接操作符。与自然连接类似，θ连接实际上是一个缩写，它并没有为语言增加额外的表达能力。让我写一下。θ连接操作符接受两个表达式，并通过一个像蝴蝶结的操作符将它们结合在一起，不过是带有下标θ。这个θ是一个条件，它与选择操作符中的条件风格相似，实际上这就是说，它等同于对两个表达式的笛卡尔积应用θ条件。

所以你可能会想，为什么我会提到 theta 连接操作符，原因是大多数数据库管理系统将 theta 连接实现为组合关系的基本操作。因此，基本操作是取两个关系，组合所有元组，然后只保留那些满足 theta 条件的组合。通常，当你与构建数据库系统或使用数据库的人交谈时，当他们使用“连接”这个词时，他们实际上指的是 theta 连接。

总结来说，关系代数是一种形式化的语言，它操作关系的集合，并生成关系作为结果。

![](img/735696dfc3f70f4297457a50431c1618_3.png)

最简单的查询只是关系的名称，然后使用操作符来筛选、切片和组合关系。到目前为止，我们已经学习了选择操作符，用于选择行；投影操作符，用于选择列；笛卡尔积操作符，用于组合来自两个关系的所有可能元组对；以及两个缩写。

自然连接是通过对某些列施加相等性来组合关系的一种非常有用的方式，以及 theta 连接操作符。在下一个视频中，我们将学习关系代数的一些附加操作符以及关系代数表达式的一些替代表示法。

![](img/735696dfc3f70f4297457a50431c1618_5.png)
