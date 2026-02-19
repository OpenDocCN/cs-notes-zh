# 映射

#### 什么是映射？

为了比较不同的作者，或在网络搜索中识别出一个好的匹配项，我们可以使用文档的直方图。它包含了所有使用过的单词，以及每个单词被使用的频率。

换句话说，给定一个输入文本，我们想要计算一个映射

\[ \textit{words} \rightarrow \mathbb{N} \]将一个单词 \(w\) 映射到其在文本中出现的次数。

因此，我们需要一个数据类型，它可以存储（单词，计数）对，即（String，Int）对。它应该支持以下操作：

+   插入一个新的对（给定单词和计数），

+   给定一个单词，找到当前计数，

+   更新单词的计数，

+   枚举容器中的所有对。

此数据类型称为映射或字典。映射实现了从某种键类型到某种值类型的映射。

Java 库提供了一个参数化数据类型 Map<K,V>，其中 K 是键类型，V 是值类型。我们可以将其视为 (K,V) 对的容器。

我们可以像下面这样创建这样一个映射：

```
>>> val m1 = mapOf(Pair("A", 3), Pair("B", 7))
>>> m1
{A=3, B=7}

```

与每个映射都要编写 Pair 不同，我们可以使用小型实用函数 to。它仅将两个元素组合成一对，并使得创建映射的语法更加美观：

```
>>> 23 to 19
(23, 19)
>>> "CS109" to "Otfried"
(CS109, Otfried)
>>> val m = mapOf("A" to 7, "B" to 13)
>>> m
{A=7, B=13}

```

我们可以使用好看的数学语法 \(m[x]\) 访问映射键 \(x\) 由映射 \(m\) 映射的结果：

```
>>> m["A"]
7
>>> m["B"]
13
>>> m["C"]
null

```

请注意，请求不存在于映射中的键将返回 null 值。这意味着映射访问的结果类型实际上是 V?（参见可空类型）。

这意味着您必须先检查结果是否为 null，然后才能对其进行任何操作：

```
>>> m["B"] + 7
error: infix call corresponds to a dot-qualified call 'm["B"].plus(7)'
which is not allowed on a nullable receiver 'm["B"]'. Use ?.-qualified
call instead

```

或者，您可以使用 getOrElse 方法：如果键不在映射中，则使用提供的代码计算默认值：

```
>>> m.getOrElse("B") { 99 }
13
>>> m.getOrElse("C") { 99 }
99
>>> m.getOrElse("B") { 99 } + 7
20
>>> m.getOrElse("C") { 99 } + 7
106

```

getOrElse 的结果类型是（非可空）值类型 V，因此不需要检查是否为 null。

我们可以使用 in 运算符检查是否为给定键定义了映射：

```
>>> "C" in m
false
>>> "A" in m
true

```

您可以通过 m.size 确定映射 m 中的条目数，使用 m.isEmpty() 确定映射是否没有映射，您可以使用 for 循环遍历映射的所有条目：

```
>>> val m = mapOf("A" to 7, "B" to 13)
>>> m.size
2
>>> for ((k, v) in m)
...   println("$k -> $v")
A -> 7
B -> 13

```

#### 可变映射

我们经常需要一个可变映射，可以添加、更新和删除映射。我们使用赋值语句的左侧的 m[key] 语法来添加或更改映射。使用 m.remove(key) 删除映射。

```
>>> val m = mutableMapOf("A" to 7, "B" to 13)
>>> m
{A=7, B=13}
>>> m["C"] = 13
>>> m
{A=7, B=13, C=13}
>>> m.remove("A")
7
>>> m
{B=13, C=13}
>>> m["B"] = 42
>>> m
{B=42, C=13}

```

另一个有用的方法是 getOrPut。如果给定的键存在于映射中，则从映射中返回该键的值。否则，它执行给定的代码片段，将值存储在映射中（对于给定的键），并返回该值：

```
>>> m.getOrPut("B") { 99 }
42
>>> m
{B=42, C=13}
>>> m.getOrPut("D") { 99 }
99
>>> m
{B=42, C=13, D=99}

```

#### 计算单词直方图

这是我的第一个直方图程序尝试（[histogram1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/30-maps/histogram1.kts)）：

```
fun histogram(fname: String): Map<String, Int> {
  val file = java.io.File(fname)
  val hist = mutableMapOf<String, Int>()

  file.forEachLine {
    if (it != "") {
      val words = it.split(Regex("[ ,:;.?!<>()-]+"))
      for (word in words) {
      	if (word == "") continue
	val upword = word.toUpperCase()
	hist[upword] = hist.getOrElse(upword) { 0 } + 1
      }
    }
  }
  return hist
}

if (args.size != 1) {
  println("Usage: kotlinc -script histogram1.kts <file name>")
  kotlin.system.exitProcess(1)
}

val fname = args[0]
val hist = histogram(fname)
println(hist)

```

函数 histogram 创建一个从字符串到整数的空映射 hist。然后它查看文件中的所有单词，将它们转换为大写。使用 getOrElse，我们获取单词的当前映射，如果单词尚未存在，则为零。我们将数字增加一，并将新数字存储在映射中。

当我在文本文件[text.txt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/30-maps/text.txt)上运行它时，我得到这个输出：

```
$ kts histogram1.kts text.txt {WHEN=2, I=3, STARTED=1,
    PROGRAMMING=1, THERE=1, WERE=2, NO=1, GRAPHICAL=2, DISPLAYS=2,
    ALL=1, COMPUTER=7, INPUT=1, AND=2, OUTPUT=2, WAS=5, DONE=1,
    USING=1, TEXT=1, A=9, SHARED=1, BY=4, MANY=1, USERS=2, EACH=1,
    USER=2, CONNECTED=1, TO=3, THE=14, FROM=2, TERMINAL=3, WHICH=1,
    IS=2, CALLED=1, THIS=1, WAY=1, BECAUSE=1, IT=1, ENDPOINT=1, OF=4,
    CONNECTION=1, EARLIEST=1, TERMINALS=1, LOOKED=1, LIKE=1,
    COMBINATION=1, PRINTER=1, WITH=4, KEYBOARD=2, IN=1, MIDDLE=1,
    SCHOOL=1, SOMETIMES=1, ALLOWED=1, PLAY=1, THAT=2, USED=1, SUCH=1,
    PRINTING=2, PRINTERS=1, LATER=1, REPLACED=1, CRT=1, COULD=1,
    TYPICALLY=1, DISPLAY=1, MATRIX=1, 25X80=1, CHARACTERS=2, ASCII=1,
    ALPHABET=1, LETTERS=1, DIGITS=1, SOME=1, SPECIAL=1, INTERACTED=1,
    TYPING=1, COMMAND=2, ON=2, RESPONDED=1}

```

输出并不是很漂亮，所以我应该使用更好的方式来打印映射。这可以通过迭代映射的内容来完成，如下所示（[histogram2.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/30-maps/histogram2.kts))：

```
fun printHistogram(h: Map<String, Int>) {
  for ((word, count) in h)
    println("%20s: %d".format(word, count))
}

```

输出要好得多：

```
$ kts histogram2.kts text.txt 
                WHEN: 2
                   I: 3
             STARTED: 1
         PROGRAMMING: 1
               THERE: 1
                WERE: 2
                  NO: 1
           GRAPHICAL: 2
            DISPLAYS: 2
                 ALL: 1
            COMPUTER: 7
               INPUT: 1
                 AND: 2
              OUTPUT: 2
                 WAS: 5
                DONE: 1
               USING: 1
                TEXT: 1
                   A: 9
              SHARED: 1
                  BY: 4
                MANY: 1
               USERS: 2
                EACH: 1
                USER: 2
           CONNECTED: 1
                  TO: 3
                 THE: 14
                FROM: 2
            TERMINAL: 3
               WHICH: 1
                  IS: 2
              CALLED: 1
                THIS: 1
                 WAY: 1
             BECAUSE: 1
                  IT: 1
            ENDPOINT: 1
                  OF: 4
          CONNECTION: 1
            EARLIEST: 1
           TERMINALS: 1
              LOOKED: 1
                LIKE: 1
         COMBINATION: 1
             PRINTER: 1
                WITH: 4
            KEYBOARD: 2
                  IN: 1
              MIDDLE: 1
              SCHOOL: 1
           SOMETIMES: 1
             ALLOWED: 1
                PLAY: 1
                THAT: 2
                USED: 1
                SUCH: 1
            PRINTING: 2
            PRINTERS: 1
               LATER: 1
            REPLACED: 1
                 CRT: 1
               COULD: 1
           TYPICALLY: 1
             DISPLAY: 1
              MATRIX: 1
               25X80: 1
          CHARACTERS: 2
               ASCII: 1
            ALPHABET: 1
             LETTERS: 1
              DIGITS: 1
                SOME: 1
             SPECIAL: 1
          INTERACTED: 1
              TYPING: 1
             COMMAND: 2
                  ON: 2
           RESPONDED: 1

```

这仍然不完美，因为很难找到我们要找的单词。如果列表是排序的话会更好。我们可以通过将映射转换为排序映射来实现这一点（[histogram3.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/30-maps/histogram3.kts))：

```
fun printHistogram(h: Map<String, Int>) {
  val s = h.toSortedMap()
  for ((word, count) in s)
    println("%20s: %d".format(word, count))
}

```

现在输出变得更好了：

```
$ kts histogram3.kts text.txt 
               25X80: 1
                   A: 9
                 ALL: 1
             ALLOWED: 1
            ALPHABET: 1
                 AND: 2
               ASCII: 1
             BECAUSE: 1
                  BY: 4
              CALLED: 1
          CHARACTERS: 2
         COMBINATION: 1
             COMMAND: 2
            COMPUTER: 7
           CONNECTED: 1
          CONNECTION: 1
               COULD: 1
                 CRT: 1
              DIGITS: 1
             DISPLAY: 1
            DISPLAYS: 2
                DONE: 1
                EACH: 1
            EARLIEST: 1
            ENDPOINT: 1
                FROM: 2
           GRAPHICAL: 2
                   I: 3
                  IN: 1
               INPUT: 1
          INTERACTED: 1
                  IS: 2
                  IT: 1
            KEYBOARD: 2
               LATER: 1
             LETTERS: 1
                LIKE: 1
              LOOKED: 1
                MANY: 1
              MATRIX: 1
              MIDDLE: 1
                  NO: 1
                  OF: 4
                  ON: 2
              OUTPUT: 2
                PLAY: 1
             PRINTER: 1
            PRINTERS: 1
            PRINTING: 2
         PROGRAMMING: 1
            REPLACED: 1
           RESPONDED: 1
              SCHOOL: 1
              SHARED: 1
                SOME: 1
           SOMETIMES: 1
             SPECIAL: 1
             STARTED: 1
                SUCH: 1
            TERMINAL: 3
           TERMINALS: 1
                TEXT: 1
                THAT: 2
                 THE: 14
               THERE: 1
                THIS: 1
                  TO: 3
           TYPICALLY: 1
              TYPING: 1
                USED: 1
                USER: 2
               USERS: 2
               USING: 1
                 WAS: 5
                 WAY: 1
                WERE: 2
                WHEN: 2
               WHICH: 1
                WITH: 4

```

#### 地图是如何工作的？

地图是使用哈希表实现的，这允许极快的插入、删除和搜索，但不保持键的任何顺序。（来 CS206 学习哈希表。）

#### 一个发音词典

让我们构建一个真正的“字典”，一个将单词映射到其他单词的字典。在这种情况下，我们想要构建一个将英语单词映射到它们的发音的映射（英语发音是如此不可预测，有一个工具来帮助这将是很好的）。

我们将使用数据文件[cmudict.txt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/30-maps/cmudict.txt)。这里有这个文件的一些示例行：

```
## Date: 9-7-94
##
...
ADHERES AH0 D HH IH1 R Z
ADHERING AH0 D HH IH1 R IH0 NG
ADHESIVE AE0 D HH IY1 S IH0 V
ADHESIVE(2) AH0 D HH IY1 S IH0 V
...

```

格式大致如下：以#开头的行是注释。其他行以大写字母开头，然后是特定格式的发音（音素之间用空格分隔，我们不会详细介绍）。

一些单词有多个正确的发音，参见上面的“adhesive”。正如您所看到的，额外的发音在���词后的括号中用数字表示。这里是另一个具有三个发音的单词的例子（并且部分不同含义）：

```
MINUTE  M IH1 N AH0 T
MINUTE(2)  M AY0 N UW1 T
MINUTE(3)  M AY0 N Y UW1 T

```

这里有一个函数，它读取文件并构建映射。它简单地忽略了额外的发音，并且只使用每个单词的第一个发音（请注意，即使它在内部使用可变映射，它返回一个不可变映射）：([cmudict1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/30-maps/cmudict1.kts))：

```
fun readPronounciations(): Map<String,String> {
  val file = java.io.File("cmudict.txt")
  var m = mutableMapOf<String, String>()
  file.forEachLine {
    l ->
      if (l[0].isLetter()) {
        val p = l.trim().split(Regex("\\s+"), 2)
        val word = p[0].toLowerCase()
        if (!("(" in word))
	  m[word] = p[1]
      }
  }
  return m
}

```

这是对函数的一个快速测试：

```
>>> val m = readPronounciations()
>>> m["minute"]
M IH1 N AH0 T
>>> m["knight"]
N AY1 T
>>> m["night"]
N AY1 T
>>> m["weird"]
W IH1 R D

```

现在让我们将我们的映射用于一些用途。英语有许多同音词：它们听起来相同，比如“be”和“bee”，或“sewing”和“sowing”。我们想找到一些更多的例子。有多少不同的单词具有相同的发音会是最大的数量？

为了确定这一点，我们需要为相反的方向创建一个字典：将发音映射到单词。由于可能有几个具有相同发音的单词，这将是一个 Map<String, Set<String>>，即从字符串到字符串集合的映射。

我们编写一个通用函数来计算地图的反函数：

```
fun reverseMap(m: Map<String, String>): Map<String,Set<String>> {
  var r = mutableMapOf<String,MutableSet<String>>()
  for ((word, pro) in m) {
    val s = r.getOrElse(pro) { mutableSetOf<String>() }
    s.add(word)
    r[pro] = s
  }
  return r
}

```

我们用一些例子进行测试：

```
>>> val r = reverseMap(m)
>>> r[m["knight"]]
[knight, night, nite]
>>> r[m["weird"]]
[weird]
>>> r[m["minute"]]
[minot, minott, minute, mynatt]
>>> r[m["be"]]
[b, b., be, bea, bee]

```

现在我们使用反向映射来显示所有至少有一定数量同音词的单词：

```
fun showHomophones(k: Int) {
  val m = readPronounciations()
  var r = reverseMap(m)
  for ((pro, words) in r) {
    if (words.size >= k) {
      print("$pro (${words.size} words):")
      println("  " + words.joinToString(separator=" "))
    }
  }
}

```

这是\(k = 10\)的输出结果：

```
>>> showHomophones(10)
OW1 (10 words):  au aux eau eaux o o' o. oh ow owe
S IY1 (10 words):  c c. cea cie sci sea see si sie sieh
S IY1 Z (11 words):  c.'s c.s cees saez sea's seas sease sees seese seize sies
K EH1 R IY0 (10 words):  carey carie carrie cary cheri kairey kari kary kerrey kerry
F R IY1 Z (10 words):  freas frease frees freese freeze freis frese friese frieze friis
SH UW1 (11 words):  hsu schoo schou schue schuh shew shiu shoe shoo shu shue
L AO1 R IY0 (11 words):  laurie laury lawrie lawry lorey lori lorie lorrie lorry lory lowrie
M EY1 Z (10 words):  mae's maes mais maize mase may's mayes mays mayse maze
R OW1 (10 words):  reaux rheault rho ro roe roh rohe row rowe wroe

```

让我们尝试另一个谜题：英语中有些单词如果去掉第一个字母会发音相同："knight"和"night"就是一个例子。让我们试着找出所有这样的单词：

```
fun findWords() {
  val m = readPronounciations()
  for ((word, pro) in m) {
    val ord = word.substring(1)
    if (pro == m[ord])
      println(word)
  }
}

```

这是输出结果：

```
>>> findWords()
ai
ailes
aisle
aisles
ar
eau
eaux
ee
eerie
eide
eiden
eike
eiler
eiseman
eisenberg
el
em
en
eng
es
eudy
eula
eury
ex
extra
gnats
gnu
herb
hmong
hour
hours
hwan
hwang
knab
knabb
knack
knapp
knapper
knauer
knaus
knauss
knave
kneale
knebel
knee
kneece
kneed
kneel
kneer
knees
knell
kneller
kness
knew
knicely
knick
knicks
knies
kniess
knight
knight's
knightly
knights
knill
knipp
knipper
knipple
knit
knobbe
knoble
knock
knode
knoell
knoles
knoll
knope
knot
knoth
knots
knott
knuckles
knut
knuts
llama
llana
llanes
llano
llewellyn
lloyd
mme
mmonoxide
ngo
ourso
pfahl
pfarr
pfeffer
pfister
pfizer
pfohl
pfund
psalter
psalters
pty
scent
scents
schau
whole
whorton
wrack
wracked
wracking
wrage
wrap
wrapped
wrappers
wrath
wrather
wray
wreck
wrecker
wren
wrench
wrenn
wrest
wresting
wriggle
wright
wright's
wrights
wring
wringer
wringing
wrisley
wrist
wriston
write
writer
writes
wrobel
wroe
wrona
wrote
wroten
wrought
wrubel
wruck
wrung
wrye
yu

```

你认识这些单词中的多少个？

在英语中有一个单词，你可以去掉第一个字母或第二个字母，它的发音仍然相同。（换句话说，如果整个单词是 XYABCDE，那么 YABCDE 和 XABCDE 的发音与 XYABCDE 相同。）

你能想出这是哪个单词吗？
