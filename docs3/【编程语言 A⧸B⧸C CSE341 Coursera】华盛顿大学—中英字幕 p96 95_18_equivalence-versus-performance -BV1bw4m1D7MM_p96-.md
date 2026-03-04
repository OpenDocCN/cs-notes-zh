# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p96 95_18_equivalence-versus-performance -BV1bw4m1D7MM_p96-

I want to finish our discussion of function equience by dealing with the fact that we have not been talking about performance。

 that we've ignored any notion of how slow or fast something is when saying the two functions are equivalent。

 this is just the definition from a programming language perspective。

 and that definition by ignoring performance is both a feature and a limitation。

 and I want to talk about the pluses and minuses of ignoring performance when talking about equivalentence。



![](img/ea120a76367aee7fc163aa83442e9e06_1.png)

So just to be clear， this can make a big difference。

 if you remember back that when we studied the necessary efficiencies of lead expressions。

 I showed you an example of computing the max of a list。

 it was before pattern matching so it didn't look quite like this but the idea is the same it turns out the code on the left it sometimes very very slow。

 exponentially slow in the length of certain lists。

 so for a list of length 50 it could literally take centuries to complete。

 whereas the code on the right is always fast， it takes time proportional to the length of the list。

But our definition of equivalentence said same side effects， same termination behavior。

 same result for any argument， and technically the code on the left。

 if you're willing to wait a few centuries， will terminate。 so by our definition。

 these are equivalent to each other。Now， I acknowledge that in the real world。

 these are not equivalent。 One of them is useful in many situations where the other is not。

 but our definition says that they are equivalent。 So why is that a good thing and why is that a limitation。

 Well， the way I like to think of it is that in computer science。

 there are many definitions of equivalentence， And in particular。

 there are three that I use all the time？ And it's okay to have three definitions as long as I'm using them all appropriately。

 and when I need to think at sort of that level。

![](img/ea120a76367aee7fc163aa83442e9e06_3.png)

So the first one is the programming languages equivalentence that we've been studying here。

 it says that given the same inputs you have the same outputs and the same effects。

 this is a feature because what it would do is let us take the bad version of Max on the previous slide。

 replace it with the good one and say it's okay I didn't break any clients because I did an equivalent thing and now it performs better and performance is not part of the definition of two things being the same。

Of course， it's a bad thing because it would let you take the good one and replace it with the bad one。

 So as long as you use the definition appropriately to justify good things and not bad things。

 it seems perfectly reasonable。Now if you take a course in data structures or algorithms。

 you study a different kind of equivalence， this is asymptotic equivalence。

 this is where you look at an algorithm and you decide its running time or its running space or some other property as it relates to its inputs and you're willing to ignore small inputs and just say as the inputs grow very large。

 how does the running time react proportionally to those change in the inputs。

So this is good for studying algorithms， it's good for understanding why one version of Max is better than another。

 it's a very powerful definition of equivalence or one thing being better than another than being tied。

 which is how equivalence comes in， and it's very effective and you should be familiar with that definition as well for studying algorithms。

It's still limiting because it says that if one version of the program is always four times faster or nine times faster than the other one。

 those programs are the same。And the same way we might prefer the nine times faster one。

 but this definition says they're the same， it's limiting the same way the programming language definition is limiting just to a lesser extent。

So there's a third definition that sort of says wait， practical considerations matter too。

 we should account for those things and maybe when I'm performance tuning a system or I care about how it reacts to representative workloads in the real world。

 I should take care to make sure that I don't swap out in implementation that behaves fundamentally differently that maybe being 10% off is okay it's a little faster for some。

 it's a little slower for others， but I expect the system to behave mostly the same。

 and because I'm dealing with a live system or something like that。

 I should only make sort of code changes that are not going to have large effects on performance one way or the other。

The limitation of this more fine grain notion of equivalence is that it tends to focus on inputs you've studied。

 It doesn't study the general algorithm， maybe even for inputs you haven't seen。

 and it doesn't study the general notion of equivalentvalence。

 maybe for clients of your code library that you've never seen。 So for example。

 maybe if you focus on systems equivalentvalence for lists that only have length up to 20 then maybe those two versions of max look the same and it's a limitation of your thinking that you don't realize that they actually behave very differently for inputs you haven't seen yet。

Okay so I love all of these definitions， my claim which you've probably already seen here at the bottom of the slide is that software developers and computer scientists probably use all of these definitions almost every day that when you're thinking about a problem that you are working on you're dealing with abstractions and those abstractions allow different implementations and that's what programming La equivalence is all about。

 you're thinking about algorithms and is something general and efficient in all cases。

 and that's what the middle definition is about， and then you're thinking about how your software will perform in practice。

And are there inputs where you need to tune it and improve it。

 and that's more of a systems perspective， none of these are better in another。

 they are all mental tools， intellectual tools that we need in order to reason about our sophisticated software in today's world。



![](img/ea120a76367aee7fc163aa83442e9e06_5.png)