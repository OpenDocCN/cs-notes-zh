# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P15：15_04_06_分析.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/7f62cb03173810bd7dfe28cc8cbc0347_0.png)

So the last step is to study our implementation for the kinds of applications that we face and see what happens with the performance。

This is more complicated than other things that we've considered because the cost depends on something pretty complicated。

 the order in which the keys are inserted。We looked at a typical case which is words coming off a text。

 the best thing that could happen would be the tree is perfectly balanced。

 but there's also a bad thing that could happen if the keys come in in order then it's no better than a linked list and this is a situation and has to be reconciled when working with binary search trees。

But when the keys come in in random order， the tree stays roughly balanced and it tends to stay that way。

 as you can see from this simulation。This is 255 random keys getting inserted into a binary search tree。

It's not perfectly balanced， but it's pretty well balanced。

And in plenty of applications like the words in the text。

The model that the keys are coming in random order is not necessarily so bad。

So there's lots of applications where we get pretty well balanced trees in this way。

So let's look at that situation。So。Let's take a model where we say we're going to insert the keys in random ordertar。

While it's possible to prove that if the keys are randomly ordered。

 the cost of building a binary search treat with those keys is about2 n natural log n or 1。

39 n log based 2 of n compares if it were perfectly balanced。

 it would be exactly in log based 2 of n， so it's only about 40% worse than perfectly balanced。

 if the keys are randomly ordered。This is an interesting exercise in discrete math that's beyond our scope。

 but it's right in the sweet spot for a course on algorithms。So with randomly ordered keys。

 we get our logarithmic performance， the time to search or insert any key in that tree that's going to be proportional to log in。

So we can say that first of all we implement the API exactly for random keys。

 we get our logarithmic performance and we'll talk about app that in a second。

 we have the linear memory use and we have no limits within the code on the collection side and that's all made possible by the binary tree data structure。

So that's a pretty good outcome and we can run empirical tests to try to validate that mathematical analysis and so we'll do frequency count without the output just for our empirical tests and run it and we can definitely do a frequency counter for large numbers of keys in our doubling ratio is about two。

 which means that we can even do a billion in a couple of minutes and that confirms the hypothesis that this method scales for this kind of application。

呃。Which is。Way better than we were able to get with elementary eras or linkedless implementations that were quadratic and did not scale。

So pretty easy to do that 21 million word corpus and easy to do even a billion things off the net。

And again， without this kind of algorithm， it's not possible to address this problem。

So it's definitely a contribution of algorithmic technology to give us the efficient performance that we have for so many symbol table implementations。

Now， in practice， it could be that the keys are not randomly ordered and the running time would be quadratic and in fact。

 this happens in practice people try to。Work with keys that are already in sorted order， for example。

 so in an industrial strength implementation， BSTs not going to work。

But remarkably we have algorithms that are not that much more complicated than binary search trees called balance trees that perform simple transformations that guarantee the balance this has been known for a long time since the 60s and right after graduate school of fellow graduate student and I developed an implementation called Red Black trees that are found in most modern systems including Java。

 the Java symbol table is built on red black trees， here's a simulation of red black tree。

For the 255 keys， so the idea is that some of the links are red and some are black and there's a restriction that there's never two red links in a row and just maintaining that restriction and that the number of black links from the root to the bottom is always the same。

Just maintaining that restriction turns out to be not so difficult to do。

 and the tree is very nearly balanced almost exactly low again， and it's guaranteed to stay that way。

So this really does implement the performance benchmark and no matter what order the keys come in。

 we can guarantee logarithmic performance for all the symbol table operations。

 and not only that the keys are it's based on ordering in the keys so we can do more sophisticated extensions to the basic API like finding the Kate's largest keys and other things like that。

 So and that's again what's used in Java T map library， So this is。

Implementing our API using red black trees using Java's library。

 just slightly different names for the methods。

![](img/7f62cb03173810bd7dfe28cc8cbc0347_2.png)

And so again， it's possible to prove that all the operations are guaranteed to use fewer than two log based 2N compares。

Which is really an amazing result when you think about it。

 So proving this is definitely stuff for an algorithms course。

 And you'll certainly learn that if you take an algorithms course。

But our summary is we have with BSTs a pretty simple。

 simple table implementation that's usually efficient。

There's an alternative that we haven't talked about called hashing。

 which is a bit more complicated and it can be efficient。

 and it doesn't support ordered operations and it's got other different performance characteristics that again you can learn about it in a course on algorithms。

With red black trees， that's a variant that's guaranteed to be efficient。

 so it's industrial strength implementation of symbol tables， and there's many， many。

 many applications that are enabled by efficient symbol tables。

So our basic question at the beginning， can we implement associative arrays with just a log factor extra costs。

 the answer is definitely yes， and Alice who took our algorithms course， is quite convinced of that。

And so when you think about what that means is if you manage to get a trillion customers。

 which might be difficult， you could search among them in less than 80 compares。

 that's kind of amazing when you think about it， or even if you had all the atoms in the universe。

 it would only take 200 compares and we can guarantee that。That's truly awesome in Bob's language。



![](img/7f62cb03173810bd7dfe28cc8cbc0347_4.png)

![](img/7f62cb03173810bd7dfe28cc8cbc0347_5.png)