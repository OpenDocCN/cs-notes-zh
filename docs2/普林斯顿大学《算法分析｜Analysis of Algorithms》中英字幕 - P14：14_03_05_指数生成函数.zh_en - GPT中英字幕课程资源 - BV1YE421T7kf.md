# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P14：14_03_05_指数生成函数.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/26054ea35e638cd5df94a11fc3e1c16f_0.png)

I just want to briefly mention that ordinary generating functions are not the only way to represent a sequence with a simple function。

 and actually there's an important one that plays a very important role in analytic combatorics that I just want to mention briefly now。

You can define other types of kernels to represent the sequence， so instead of z to the K。

 say we put z to the K over k factorial。If we do that。

 then what we have is what's called an exponential generating function。So for example。

 the sequence of all ones， the exponential generating function that represents that sequence is z to the n over n factorial。

And we saw that's E to the Z and the powers of 2， again。

 just do the math2 to the Nz the N overin factorial， that's 2 to z to the N overin factorial。

 that's E to the 2 z。So same sequence， different functions for representing them in their situations where it's more natural。

 it's better， it's more convenient to use exponential generating functions。

 and many other possibilities have been studied。But for analytic combinatorics we're going to focus on ordinary generating functions and exponential generating functions。

 so it's worth spending。 here's another one， oh n factorctorial itself。

 the exponential generating function for n factorctorial is one over 1 minus E。

So that's an example of when we might need it， if you've got a very sequence that grows very fast like n factorial。

 ordinary generating functions is not going to work。

 some of n factorials z to the n doesn't converge for any Z and it's cumbersome to work with so use exponential generating function that's one over1 minus E。

 it can be a bit confusing because the same functions arise in different contexts。

 but really not it's just a different way to represent the sequence。

And we have the same kinds of operations and you can read in the book about differentiating integrating and so forth and there's one important operation that's what happens when you multiply two EGFs then you get what's called a binomial convolution and that's just applying the same steps that we use when we proving what happens with the product of two ordinary generating functions。

 but we carry through the k factorial in the n factorial so distribute now when we change n to n minus k we've got a k factorial n minus K factorial。

 but then we need an n factorial and the denominator anyway so we multiply and divide by n factorial and now we've got a exponential after we switch orders we get an exponential generating function for this convolved sequence the。

volutionAnd actually there's plenty of applications where these kinds of sequences arise and we'll see them very soon。

So there's recurrences say related to such problems that arise and if confronted with a recurrence like that。

 we'll have to know， naturally from the problem that that one looks like I should use the exponential generating function on。

So this is an example that actually will come up with some similar examples in specific applications related to important algorithms later on。

 so FN equals sum on K of N choose k， FK over 2 to the K。

How we're going to find an equation for that number。Well。

 exponential generating functions will use the same rule。

 except we make an exponential generating function。

 so that is multiplied by z to the N over n factorial and sum on N。Then on the left hand side。

 we get F of Z， and on the right hand side， we get a double sum。

And then what we're going to wind up doing is kind of working backwards for the convolution that we just did。

So switch order summation on that， that's just switching the sums and keeping now if it's all k。

 then and's got to be bigger than k。And then change n to n plus k。

 so that brings us n plus k in the top of the binary coefficient and the exponent to z and n plus k factorial。

And then do some the imp k factorials cancel out， we still have the fK。

 the z to the K and the two to the K absorbed together and the z to the n。

 and now those are independent sums so that's the binomial convolution backwards and so what it says is that F of z equals e to the z that's the z to the n over n factorial sum and the other one is f of z over 2 so f of z equals e to the z f of z over2 and that's something we can telescope and this is a little bit formal it's not necessarily true that it converges but let's。



![](img/26054ea35e638cd5df94a11fc3e1c16f_2.png)

Not worry about that just now and work with the idea that we've shown that f of z equals e of 2 to the z E to the 2 z。

And what's that， what's E to the 2 z， the exponential generating function  for。

 that was one of the first examples that we looked at， it just says that FN equals 2 to the n。

In this case， whether or not the generating function converges。

 we've got an answer that we can check2 to the n definitely equals some K inches k2 to the K or 2 to the K。

 that's the binomial theorem。So looks like a difficult recurrence actually has an easy solution with exponential generating functions so and it works for similar functions too。

 and that's what happens in the practical applications。

 maybe it's n minus 1k or maybe there's an extra term of some kind。

 the same process works to actually tell us the facts that we need to know about the algorithms that we're studying。

We'll see in much more context the important role that exponential generating functions take when we look into analytic combinatorics in a couple of lectures。

 but even in the context of just solving recurrences， they can be important。

 as this example illustrates。

![](img/26054ea35e638cd5df94a11fc3e1c16f_4.png)