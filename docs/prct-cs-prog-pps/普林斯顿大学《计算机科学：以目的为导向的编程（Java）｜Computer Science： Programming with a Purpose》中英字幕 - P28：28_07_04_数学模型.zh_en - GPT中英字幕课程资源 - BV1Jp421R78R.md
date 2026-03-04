# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P28：28_07_04_数学模型.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/76e2a8d93cb110b8f98b26b6e2c799c8_0.png)

Running experiments is one thing， but now we're going to look at an even stronger idea that we can develop mathematical models that describe the performance of our programs that we can use as a check and ass a better way to understand the programs。

So the question is， can we write down an accurate formula for the running time of a computer program？

For in the 1960s， the prevailing wisdom was， no， it's much too complicated。

 computer is an extremely complicated device and developing such a model would be much。

 much too difficult， but in the late 60s， canoeuth showed that actually it is something that we can do。

 and he wrote a series of four books that did so for many， many important computer algorithms。

And his idea was just very straightforward， we determined the set of operations that the program is going to use to get his job done。

 and then we find the cost of each one of the operations in those days。

 there was a manual that would tell you exactly how much time each instruction would take and nowadays ways to find that out。

 depends on the system software and other things。Then you find the frequency of execution of each one of the operations。

 that's going to depend on what the input is and it's going to depend on the algorithm。

And then you find the total cost by just adding the cost times the frequency for all the operations。

And yes， it can be complicated， but there are also ways to get useful approximations that make it quite feasible and quite useful to develop mathematical models even now。

 and that's what I'm going to talk about next。So just as a warm up for this。

 let's say we wanted to solve the one sum problem。 So that's in the array how many zeros are there。

 So now there's just one for loop。 we're just counting the number of zeros in the array。

So if we look at this program and break down the operation of this program。

 the first thing to note is that the number of times that one instruction executed count plus plus actually depends on the input could be no times if there's no zeros or it could be n times if there's all zeros。

 so that's a complication that for some programs like this one we have to take into account。

 so what's a mathematical formula for the total running time of this program。Well， in this case。

 we break it down to the seven operations， the function call return。

 declaring the variable assignment statement compare that winds up less than equal to compare accessing an array and incrementing and for each one of these we can estimate the actual cost of performing each one of these operations now there is some poetic license here nowadays decades ago you could actually state these costs with certainty because computers wouldn't work unless the things took exactly that amount of time now there can be a little more leeway in some of these numbers but still you can do some study and experimentation to get the exact values if you need to。

So that's the cost of each one of the operations and then over in the rightmost column is how many times each operation is executed。

 There's only one function call return， there's two variable declarations and so forth。

And there's n plus1 less than compares n equal to compares n array axises。

 and then the number of increments， well you have to increment I you have to increment count and count can be between 0 and n so that one is a variable。

 so that's the cost and that's the frequency so the total running time is to go ahead and just multiply these together and atom and the result is that we get C times n plus 26。

5 where C is a number between2 and 2。5 depending on the input。

And if we postulate that zeros are rare in the input， we could say maybe it's about 2 n plus 26。5。

 but that's an example of Canus' methodology of determining the cost of each operation determining the frequency of execution multiply together and add them up。

So now let's look at a slightly more complicated example to some。

So now want to find if there's pairs of numbers that sum to zero。

 so we have a doubleub index for loop， this one we know how to solve much faster， but again。

 our topic is studying the programs， not studying the fastest way to solve the problem。

So let's try to get a formula for the total running time of this TU program。Again。

 this is the same kind of table， but now the frequencies of operation are more complicated。

 so there's n times n minus1 over two different pairs I and J between0 and n。

 so that's the source of these expressions over here for the frequency of operation。

The details of deriving these aren't that important right now。

 but they're tedious to get them exactly right， but so anyway here's the table that we get and once you know that number you can work out the others。

And so we can go ahead and add it up and now we've got a more complicated definition of what the running time is because this variable of the number of times the increment happens affects all the things and so you could come up with a formula but what we need to do is simplify the calculations a little bit and so what we're going to do is where that is we're going to just concentrate on the part of the formula that grows the fastest as the most significant and we're going to ignore everything else。

And to do that， we use a notation known as the Tilde notation。

 and all that means is we write F of n Tilde G of n means that their ratio approaches1 as n approaches infinity。

Now it doesn't precisely say how fast it approaches one and so forth。

 but still it's quite useful for the kind of calculations that we're doing right now。So for example。

 if I have a formula like54 n plus 13 fourth n plus 53 over2。

 that first term as n grows grows very much faster than the other two terms。

 so would just say it's tilde5 fourth n squared。And so just to see how close。

 let's say that n equals 1，000， the thing on the left is 1253，0276。5。

 and the thing on the right is 1250，000， but that's within 0。

3% and that's definitely good enough for our purposes and trying to understand the running time of a program。

So the idea is that if n is large， then the terms that we ignored are negligible， if n is very small。

 then everything's negligible， doesn't matter so much。And by throwing away small terms。

 we're able to more easily work with these formulas。So then for Tsome we can say we can。

Posulate that the count's not large， maybe that's a factor of our application which is often true。

 there's not that many pairs at some to zero， so that's going to be in some low order term and that eliminates our dependence on the input so now we can say that that thing takes a tilde 54 cent squared nanosecond。

That's the kind of expression that we can write down for the running time with just one term。

 the fastest growing term。So finally let's do it for three sum。

 so now we can apply our tilde operations even when counting out the frequencies。

 forget about the lower terms because we now we're going to multiply by a constant and atom together and again assume sum the count is not large to take the input out of the equation。

 it's all based on n choose 3 is tilde n cubed over 6 and then these things are much easier to compute and now multiply an atom。

 we get immediately tilde n cubed over two nanoseconds。

And that's a mathematical formula that we derive just by looking at the program。

 and that model tells us when we looked at the properties of the computer and the program should be till to N cubed over two nanoseconds。

And you may remember that our empirical hypothesis said。Actually， almost exactly that。

484 N cube nanoseconds。So that's a very good situation when we have our mathematical model in agreement with our empirical model。

So let's look at the context of that， this is really what the scientific method is all about。

 developed in the 17th century and later by European mathematicians and scientists whole ideas to observe some feature the natural world。

Come up with a model that's consistent with observations or experiments， and that's a hypothesis。

 predict events using the hypothesis， and then verify those predictions by making further observations。

 and then we validate that and refine until our hypothesis and our observations agreed。

And that model can come from experiments， but it also can be a mathematical model。For programs。

 the feature of natural the natural world that we're studying is the time that it takes the program to run on a computer。

And then we fit our curve to get the formula for the running time and that's useful for predicting。

 but not really for explaining。With mathematical analysis， we study the algorithm。

 we get a formula for the running time as a function of n that really helps us understand what the algorithm is doing and it's also another validation of the model so when we can do what we just did in this case where we can run experiments and develop a mathematical model that agree then we can have quite a bit of confidence in our understanding and in the predictions that we make based on that understanding。

Now it is the case that we might need some advanced mathematics， and we'll talk about that later。

 but the advantage of the mathematical model that really apply is going to apply to any computer at all。

And the good news is that it's often the case that our mathematical models are easier to formulate than in other sciences。

 because really the operation， the object that we're studying or computer programs are built from relatively few primitives like loops and conditionals。

That are put together now its sometimes it can be advanced。

 but usually we can say that it's maybe easier than in other sciences。

 but we'll take a look at that next。

![](img/76e2a8d93cb110b8f98b26b6e2c799c8_2.png)

![](img/76e2a8d93cb110b8f98b26b6e2c799c8_3.png)