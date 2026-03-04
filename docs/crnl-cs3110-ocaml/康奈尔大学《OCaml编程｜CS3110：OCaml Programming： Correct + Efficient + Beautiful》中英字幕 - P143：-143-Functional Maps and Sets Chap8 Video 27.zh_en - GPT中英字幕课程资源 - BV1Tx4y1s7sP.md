# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P143：-143-Functional Maps and Sets Chap8 Video 27.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've now implemented the map ADT with three different data structures， association lists。

 direct address tables， which are really just as， and hash tables with chaining。

 which combine both of the above。The three important operations for those insert， find， and remove。

 have had different asymptotic efficiencies。

![](img/373c5e5fb83b1f157ba28420c441c207_1.png)

For association lists， those operations were slow。 The find and remove， in fact， were linear time。



![](img/373c5e5fb83b1f157ba28420c441c207_3.png)

Now this was a functional data structure so it had that going for it and it's easy to code up yourself。

 but beyond that， it's not a great data structure for implementing maps if you want really great performance Arrays were fast。

 they had constant time operations for insert， find and remove。

 but they came with a rather severe limitation that the keys had to be integers。

 we'd like more flexible maps than that。

![](img/373c5e5fb83b1f157ba28420c441c207_5.png)

![](img/373c5e5fb83b1f157ba28420c441c207_6.png)

They're also mutable。 That's neither here nor there。 Hah tables are also fast。

They require a good hash function that gets you the expected constant time performance for find。



![](img/373c5e5fb83b1f157ba28420c441c207_8.png)

For insert or remove， they had worst case linear time performance， which at first looked pretty bad。

 But after we studied amortized analysis， we realized that we could say that they had amortized constant time performance。

 Sometimes they're really slow， but most of the time they're really fast。 and on average。

 it works out there fast。

![](img/373c5e5fb83b1f157ba28420c441c207_10.png)

Hash tables are also mutable。Could we do at least as well or better with a functional data structure？

Well， we're probably not going to do any better than constant time performance。

But how efficient could a functional map be？That's what we're going to explore next。😡。

We're going to do it in the context though of sets。

Let's think about maps versus sets for just a minute。Abstractly。

 a map is really just a set of bindings， in fact that's the abstract notation we've been using for it is set notation。

A map might bind a key K1 to a V1， a key K2 to evaluate V2 and so forth。Well。

 if you just ignore the values， you've got a set， it's just a set of keys。So right away。

 maps and sets are pretty closely related。In fact， data structures for them are largely interchangeable。

You might waste a little bit of space by representing a set as a map， but not that much。

And so to simplify what we talk about next， I'm going to develop functional sets first。😡。

It will be a very， very quick tweak at the end just to make it functional maps。😡。



![](img/373c5e5fb83b1f157ba28420c441c207_12.png)

We'll start off with a very small interface for sets。

Alpha T is the type of sets whose elements have type alpha。Empty as usual， will be the empty set。

Insert will add an element to a set， so it will be the set containing X。

 as well as all the elements of S。This is therefore a functional data structure you can tell from the type it's not returning unit。

 it's taking in an old set and returning a new set。And finally。

 we'll have a find or a membership operation， Me XS is whether X is a member of S L set is a module that represents sets as lists that contain no duplicates。



![](img/373c5e5fb83b1f157ba28420c441c207_14.png)

![](img/373c5e5fb83b1f157ba28420c441c207_15.png)

So the list x1 through Xn represents exactly the set x1 through XN。The empty list is the empty set。

Membership we can just implement in terms of the list modules Mem function and insert the only wrinkle with that is we have to check and see whether the element is already a member of the set。

 if it is we don't change it， otherwise we conit onto the front。



![](img/373c5e5fb83b1f157ba28420c441c207_17.png)

So both of these latter operations have an efficiency that is linear in the size of the set because we have to look through all of the set elements that are currently members。



![](img/373c5e5fb83b1f157ba28420c441c207_19.png)

![](img/373c5e5fb83b1f157ba28420c441c207_20.png)

![](img/373c5e5fb83b1f157ba28420c441c207_21.png)