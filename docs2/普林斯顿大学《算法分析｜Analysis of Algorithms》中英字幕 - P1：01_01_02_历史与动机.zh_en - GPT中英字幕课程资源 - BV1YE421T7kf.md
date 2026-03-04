# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P1：01_01_02_历史与动机.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/0a5e5c2840a720279ebec52e68c7d156_0.png)

Welcome to Analytic Cominatorics， Part1。Inlytic combinatorics is the quantitative study of the properties of large。

 discrete structures。One of the main applications of analytic comeators is the analysis of algorithms。

So this first lecture in the book on which the course is based is titled The Analysis of Algoriths。

For much more information on the context of analysis of algorithms and analytic combininatorics。

 take a look at the introductory lecture from the analysis of algorithms to analytic combinatorics。

 a journey with Philip Fgelet， which tells the history of how my friend and colleague Philip Fgelet and I developed this material。

So to talk about the analysis of algorithms， we'll begin with some history and some motivation。

First question that we want to ask is why analyze an algorithm at all。

 and the answers to this question are fairly straightforward。

One thing that we want to do is classify not just algorithms。

 but also problems according to their level of difficulty。

Another thing that's very important is we want to be able to predict performance and compare algorithms。

 we want to know how much time our algorithms are going to take and we want to know which algorithm is better than which other one for particular tasks。

Another thing that happens when we analyze algorithms is that we have to closely study them。

 and that helps us better understand and improve the performance of particular algorithms。

But really the reason most people analyze algorithms is because of the intellectual challenge。

 the analysis of algorithms is even more interesting and fun than programming for many people。

 and we hope to be able to convey that sense to you during this course。Now the field goes way back。

 in fact， the first computational device is attributed to Baavage， it was a mechanical device。

 and this quote shows that even Baavage understood that we're going to need to understand something about our methods of computation。

As soon as an analytic engine exists， it will necessarily guide the future course of the science while he was right about that。

Whenever any result is sought by its aid， the question will arise by what course of calculation can these results be arrived at by the machine in the shortest time。

That was very important to baavage because this thing was mechanical。 In fact， if you look closely。

 there's a crank。And the question Babbage was interested in was。

 how many times are we going to have to turn the crank， obviously a very important question。

And really not so different than the kinds of questions that we ask today when we ask whether we can get a task done before our cell phone runs out of battery power or whatever other scarce resource we care about。

Even touring， which many people think of as a theoretician。

 was very practical when it came to actually getting things done with computers。

He says it is convenient to have a measure of the amount of work involved in a computing process。

 even if it has to be a very crude one， we may count up the number of things that various times that various elementary operations are applied in the whole process。

Again， this is 1940s before computers were coming into widespread use。

 but Tring saw that we're going to have to know how our algorithms are performing and we're going to have to be able to count the resources they consume。

But the field really came into existence in the 1960s when Don Canuth published the first of his series of seven volumes。

 four of which have now been published， and he's the one who really put this study of the analysis of algorithms on a scientific basis before Canuth people thought that it was going to be just too complicated to really figure out what kind of resources programs consumed。

 and Canuth simply laid out pretty straightforward steps for what we need to do to analyze an algorithm。

 First， get it running， implement it and understand its performance by running experiments。

 develop a good implementation。Second， abstract the process a little bit by defining some unknown quantities that represent the basic operations。

Then determine the cost of each basic operation and then develop some kind of model for the input and with that model。

 analyze the frequency of execution of the unknown quantities。

 each one of these tests have a little bit of complication to them but still that relatively straightforward and with all that information then we can calculate。

 say the total running time which is for every quantity we just add up its frequency of execution times its cost。

very straightforward process and pretty close to the one that I'll be talking about in the next segment this lecture。

This has great benefits first as I mentioned， it's the scientific foundation for analysis of algorithms。

 it gives us a process whereby we can develop mathematical models。

 develop hypotheses about performance and comparing algorithms。

 and then test those hypotheses scientifically。You certainly can predict performance and compare algorithms if you analyze algorithms on a canoe。

Now it does have some drawbacks the first drawback is the input model might be unrealistic and that's certainly still a problem that plagues people today and the second drawback is that there might be too much detail in this analysis and that is a bigger problem that actually we try to address with analytic combodatorics so that'll be a theme that we'll come back to often in this course is how do we suppress detail while still getting accurate results。

Now in the 1970s and even up to the present day， the study of algorithms has revolved around books by Ajo Hpcroft deouman。

 Corman Lysson Reves and Stein and others， and they try to address canoe drawbacks by first of all。

 just analyzing the worst case costs， and what that does is it takes the model pretty much out of the picture。

 what we want is a guarantee on the worst case running time of an algorithm。

And the second thing is we just use big O notation and just try to get an upper bound on the worst case costs。

 and that's a way to get a lot of the detail out of the analysis so we're looking at a guaranteed upper bound on the cost of an algorithm。

And that addresses both of those drawbacks of canoe and then the idea is to classify algorithms according to this cost。

And that was an extremely successful approach that unleashed really an age of algorithm design where people would be able to try out all kinds of new ideas and drive down these guaranteed worst case costs with the ultimate goal of developing optimal algorithms where the worst case costs is equal to the best possible。

But this approach also has a drawback and the serious drawback of this approach is that you cannot use it generally to predict performance or compare algorithms that's an elementary fact that's often overlooked but in this course it's important to lay out right at the outset。

So here's an example， two very familiar sorting algorithms。We have quicks。

 which I'm sure everybody is familiar with in this course。Quick sort。

 the worst case number compares is quadratic， you can have the algorithm and we'll look at this algorithm in more detail later to make that obvious for those of you that haven't seen it。

So according to the classification from the theory of algorithms。

 itll be classified as an ON squared or a quadratic algorithm。Merge sort。

 we can prove the worst case number it compares is n log n。

 and actually any algorithm has to use that much so you could say that merge sort is optimal and it gets classified as an analog log n algorithm。

And that's where theory of algorithms would leave those。

 but it's a problem because Quicksort actually is twice as fast as merge sort in practice and it uses half as much space。

 so even though the theory of algorithms would classify merge sort is better in practice quick sort is much better and there's many。

 many examples like this， hashing versus balanced binary search trees and many。

 many others examples like this。So how do we know the Quick service twice as fast as Mer sort well we're going to look at that。

 that's what the analysis of algorithms is all about。

 enabling us to make precise quantitative statements about the performance of algorithms that we can test in practical implementations。

So the bottom line is cannot use BigO upper bounds to predict performance or compare algorithms。Now。

 with that background， I just want to take a minute to put analytic combatorics into context。

So as this is a summary of the last couple of slides。

 the drawbacks of canose approaches that the model might be unrealistic and there might be too much detail in the analysis。

The AU or serialRS approach， the worst case performance might not be relevant and can't use BigO upper bounds to predict performance or compare algorithms。

What analytics combinators can provide is number one by the end of part two， you'll see。

calculus for developing models that can help us use more complicated models to help understand algorithm performance and also can provide general theorems that allow us to avoid too much detail in the analysis。



![](img/0a5e5c2840a720279ebec52e68c7d156_2.png)

In this course， in part one， we're going to take a look from the beginning of the underlying mathematics and try to describe just what analytic combinatorics is。

 and then look at a lot of classical results in analysis of algorithms and combinatorics to set the stage for part two where we get to the。

Real recent research and developments in analytic combinatorics。

That's a history and motivation for the analysis of algorithms。



![](img/0a5e5c2840a720279ebec52e68c7d156_4.png)