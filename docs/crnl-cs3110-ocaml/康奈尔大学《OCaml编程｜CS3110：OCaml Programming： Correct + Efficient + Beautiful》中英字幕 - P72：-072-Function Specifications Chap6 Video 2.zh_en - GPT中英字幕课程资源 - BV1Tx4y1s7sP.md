# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P72：-072-Function Specifications Chap6 Video 2.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's review how to specify functions in OAML。The specification format we use actually comes from a book titled abstracttraction and Specation in Program Development written by Barbara Liskov and John Gutag。

 they later rewrote that book and updated it for Java。

 the title of a rewritten book wasPro development in Java Abtraction Specation and Object Oriented design。

The template for specification that comes from that work has four pieces to it as we use it in OcaMl。

 a line that begins the specification about what the output is in terms of the input。

Perhaps some examples of how to use the function requires clauses， which is the precondition。

 and a raises clause， which really is part of the post condition。

We're going to talk in more detail about each of those pieces next。

The specification is written in a MLI file above the declaration of a name that declaration also provides the type of the function。

 so none of those types needs to be part of the specification itself。

 they're written separately as part of the source code。



![](img/279a091ef5fb525b286f983cbc2e107d_1.png)

![](img/279a091ef5fb525b286f983cbc2e107d_2.png)

Barbara Liskoff， by the way， is a Turing Award winner she won in 2008 for contributions to practical and theoretical foundations of programming language and system design。

 especially related to data abstraction， which we're studying now。

 fault tolerance and distributed computing。She is， by the way， my grand advisor。

 that is to say my PhD advisors PhD advisor。She's also one of the first women ever to be awarded a PhD in Comp science。

One of her major achievements was the design of the language Cl CLU。

 which is a predecessor of many modern object oriented languages and K invented some of the ideas that those languages have that you will now recognize and Cl had them for the first time Iterators and exceptions are some of its noteworthy innovations。

It also had typeSa one of types before the ML family did。

 so sometimes other languages precede functional languages as well。



![](img/279a091ef5fb525b286f983cbc2e107d_4.png)

Let's look at a specification from the OAML standard Library， this is for the list dot sort function。

If you look at this specification， you can see it has the pieces of that template。

The first line is a one line summary of the behavior。Now in this case。

 it's not written exactly as F of x is something about x instead it's a little bit higher level than that。

 which sometimes is necessary for a sorting function。

 we all generally understand what the idea of a sort is so writing down in mathematical detail is not the most helpful way we could begin the specification of this function instead we can just say that it sorts a list。



![](img/279a091ef5fb525b286f983cbc2e107d_6.png)

The second line here， although it doesn't begin with requires colon， it is a precondition。

 it states something that must be true about one of the inputs provided to the sort function。

 which is the compare function that is passed in。The third function here gives a post condition so we could write returns colon in front of us。

 The resulting list is sorted in increasing order。The final sentence actually is another piece of a specification that is about the efficiency of it。

This specification is promising that the sort is going to run in constant heap space and logarithmic stack space。

So efficiency can be a part of the specification of a function， it isn't always， but it can be。

