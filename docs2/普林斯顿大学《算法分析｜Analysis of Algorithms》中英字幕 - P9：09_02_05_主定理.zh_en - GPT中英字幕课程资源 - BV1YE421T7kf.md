# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P9：09_02_05_主定理.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/a0db0354b8da162361a1ad7183b5a85d_0.png)

Next， to finish off our study of recurrence relations。

 we'll talk about the master theorem for Div and conquer recurrences。

This is very important in the theory of algorithms， and it's all about divide and conquer algorithms。

 so many algorithms gain their efficiency by attacking a problem of size N with the following steps。

First divided into smaller parts， so in the case of merge short it was divided into two parts of size n over2 more generally it might be parts of maybe different size so it'll pick a factor beta so it could be n over three or and over four or whatever and not only that it might not add up to n so there might be multiple parts and say three parts of size n over two or seven parts of size n over8 or whatever。

 so parameters both the number of parts and the size of each part， usually they try to do equal size。

 if you don't have equal size then you have even more complications。So that's the first thing。

 divide into alpha parts of size n over beta， and then solve recursively and then put the solution together somehow with extra cost that is described by a standard function and in the theory of algorithms。

 I remember we don't care about the constant we just want to get the order of growth。

 so we'll say theta of n to the gamma log n to the delta。

So there's a lot of problems that fall within this paradigm and again it's easy to write computer programs that have this kind of behavior just write a recursive program that does the things and so for the theory of algorithms for decades people have been developing computer programs that are gained their efficiency by this strategy and what we want is to analyze them。

 so very early on people started studying general models for computer programs like this and that's what's called the master theorem that we'll talk about next。

So first， here's some examples。 So we did merge sort。 So for merge sort problem size is n over2。

 So that's beta 2， two problems of size n over 2。 So that's alpha is 2。And the extra cost is n。

 so there's no log n so delta equals0， gamma equals 1， so that's merge sort。

Here's another example that's similar， so that's Bacher's network for sorting。

 so that's a different approach to sorting where we don't do it with programs。

 but we do it with hardware and batchs is like merge sort except the extra cost has a log n factor so this deelta equals1 that's batchcher's network so now I'm going to only write the ones that are valid when n is the power of two taking into account the floors and ceilings that are needed for general N takes us to another level that we don't necessarily need to worry about in many cases with the theory of algorithms and so we'll try not to worry about that in this first cut at the analysis。

A famous algorithm that got people interested in this was multiplication。 At the beginning。

 people were wondering how。Difficult is the problem of multiplying two n bit integers。

And it seemed like the best you could do would be the grade school method of multiplying two end bit integers by taking each bit。

 multiplying by all the other bits， moving over one。

 and then adding up a little n by end table of bits that's going to take time proportional to n square。

And then the cartsubba multiplication algorithm came along where they showed how to multiply inputput integers by dividing into three problems of size n over 2。

 and then combining with an extra cost of n， and so that's the number of steps required for that particular multiplication algorithm。

And a related one that's also very famous is the Stros and matrix multiplication algorithm。

 it seemed that matrix multiplication algorithm where you have two n by n matrices that you want to multiply together to get an n by n result。

 it seemed that for every entry in the result you needed to have a dot product of a row and a column which is going to require an n multiplications for each of the n squared entries in the result。

 which would be n cubed。AndBut Strasen showed that you could solve it with a divide and conquer algorithm where you divide into seven problems of size n over two and then。

Get the final solution with extra n。 so there's an algorithm that did matrix multiification in a number of operations described it by this recurrence。

 So these are three examples that divide and conquer algorithms that all have the same general character。

And so what the master theorem says is that gives under the supposition that you have a problem of size alpha parts of size n over verbeta with the extra cost in the ga log n the delta that that's going to lead to a recurrence and the recurrence is going to look a lot like our merge sort recurrence。

 except instead of the floors and ceilings we add little tiny constants to each one of the problem part sizes。

 because n a rebeta when it has to be an integer， so you have to have some floors and ceilings in there somewhere or maybe the problem sizes throughout a few terms。

 so as general as we can do is to get alpha terms of the form nbeta plus o of1。

 and then we add on the extra cost and the master theorem gives the order of growth of the solution。

And it all has to do with the relationship between this extra power gamma and the extra cost term and the log to the base beta of alpha where alpha is the number of parts and beta is the amount the fraction that you divide n by。

So in what the solution is is three different cases if gamma is small compared to log beta alpha。

 it's n to the gamma， log n to the delta。If it's equal， then there's an extra factor of log n。

 and then if gamma is big， so that means the extra cost is big。

 then that's going to dominate in its end to that power。

And so here's in the book is a little graphic way of seeing how these three cases have to be different。

 so this is the case that alpha equals3 so we have three parts and so it has to do with the relationship between our number of parts and the size of each part and the one in the middle is like what we did with merge sort。

 if you have three parts of size n over three， then the total number of problems that you analyze at every case。

 the size of them is going to about add up to n at every stage is just you divide by three every time and then every time you divide by beta you keep going until you get to one so that's the log beta of n this should say n that alpha。

So that gets you down to a problem size of。With log n steps， you get down to problem size of one。

 so that's where you get the extra log n factor。If， on the other hand， you're。

Dividing into so three parts， but they're small， then what's going to happen is that really all that matters is the first cost and the rest of them become not so significant so really the cost of doing it the first time is what counts。

But if your problem sizes are bigger， then it's all about the number of problems that you get at the end。

 and that's what n to the log beta alpha comes up。So that's the master theorem for divideivide and conquer algorithms。

And so here's the typical applications。This is for merged sort， you get in log n。

 it for Bacher's network， you get the extra factor of log n for carrotsubba multiplication。

 you get this case here， so it's n to the log base two of three。Which is about 1。585， not n squared。

 it's less than n squared。 and for Strosin， you get n to the 2。8， it's less than N Q。

So the basic idea of the master theorem is that it gives us good asymptotic growth rates and very important for the theory of algorithms to help us understand what we can do in terms of asymptotic growth rates。

Now there's a lot of versions that have been studied about the master theorem。

 there's some cases where you can get precise results like we did for merge sort and for the most important algorithms that people use in practice and we want to predict performance and compare algorithms。

 we have no choice but to go there。The more general results in the theory of algorithms go even more general than where we went in terms of the extra cost of doing the combination and those are certainly available。

 and then actually very recently a full solution using aticcomatorques was developed by Spanowsky and Dmta that actually captures in general all the kinds of oscillations as we determine for merge sort。

Now really appreciating how and why this solution works in the way that it does is going to be something that's going to require everything that we cover in analytic combinatorics。

 including Part two， but people will have some idea for how the mathematics manages to model what actually happens in the computer algorithm。

 and this is really an important contribution of analytic combinatorics in this case。

So that's the master theorem for studying divide and conquer algorithms and that'll complete our study of recurrence relations next time we'll move on to generating functions。

So here are a few exercises that will be worthwhile for you to take a look at to cement your understanding of this material in order to be ready for the next lecture。

First one is exercise 2。17。There's a particular data structure called a 2，3 tree。

It doesn't matter too much now what it is， but there was a paper by Yao that proved that certain property of this tree。

Wwhich is described here is described by this second order first order recurrence。

 and so it's a complicated first order recurrence and so problem is to go ahead and solve this recurrence and it's an interesting random process and leads to interesting recurrence that's got a solution that's definitely a practical interest。

Yeah。Here's another one is to。Go ahead and try divide by 3 and conquer。

 so a sub n equals3 a of flu of n over 3 plus n， so maybe merge sort by dividing into three parts and then doing three way merge。

And so what does the periodicity in that thing look like。

 so again using the same methodology that I use for divide by2。

 do this one and try to discover the interesting performance behavior of something like this and think about how we might compare two algorithms like that。

Now， in order to address those， you're going to again want to read the chapter on recurrences in the book and write up the solution to the two。

3 trees， exercise and then set up standard draw or come up with your own way to plot the values of sequences。

 and then go ahead and do that exercise for plotting divide by three and conquer。

I think doing that work will help you make sure that you understand the material that we've done so far and set you up for the next lecture。



![](img/a0db0354b8da162361a1ad7183b5a85d_2.png)

![](img/a0db0354b8da162361a1ad7183b5a85d_3.png)