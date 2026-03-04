# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P24：24_06_05_可计算性.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/468af960e0edb7817c688e8f55d7ed75_0.png)

That's only part of the story to show that all the computers we can imagine are equivalent。

 But now we come to the question of。What are the problems that we can solve and are there problems that we can't solve？

And to introduce that， I'll describe a very simple puzzle known as post correspondence problem。

It's a family of puzzles and it's based on a set of cards and you'll see an example in just a minute。

So we suppose we have in different types of cards and we have no limit in the number of cards of each type。

And in each card is characterized by a top string and a bottom string。

 And the question that we have to ask， given the n types of cards is。

 does there exist an arrangement of cards with matching top and bottom strings？

So with a few examples， you'll see。So here's say we have these four types of cards。 and again。

 we have an unlimited number of each type。So the first one has BA B on the top and A on the bottom and like that。

 the last one is BA on the top and B in the bottom and what we want to know is can we take cards from these piles and as many as we want and get an arrangement where the top and bottom strings reading across the cards are the same。

In this case， the answer is easy， in fact， almost every move is forced。

 so let's say we pick Cariff type 1。So it's got A on the top and A B A on the bottom。

So to get the top and bottom strings to match now for our next card。

 we have to pick one that starts with a B。So say we take a cardiff type 3。

So now we have A BA on the top， A BA， and then a B on the bottom。So again。

 to get a match we have to have one that starts with a B on the top。

 so let's say we take one of type 0 for our next one。

 so now we have alternating A's and B's ending with a B on the top and we have the same thing but with one fewer character on the bottom。

 so now we need a card that has a B on the bottom。And in this case， we pick a card of type2。

And now we have six characters on the bottom and we have eight characters on the top。

 so we're going to need after a little analysis to pick one of type1， they both have to be A's。

 and now we've got a match。There are nine characters alternating A's and B's。

 both in the top and the bottom， beginning and ending with A。

So that's a solution for that set of cards。But here's another set of cards。

 Is there going to be a similar solution for this set of cards， which is a little different。

If you look at this one for a while you say obviously there's no solution because you can't even match the first character。

 every one of these cards differ on their first character， so there's no way to even get started。

So that's the question in general， given a set of cards。

 is there going to be matching top and bottom strings？

Here's a much more complicated set I developed my colleague， Andra Pell。

And this one there actually exists a solution that starts with a card of type zero。

 and you're welcome to try it。So but the question is can you write a program that would take as input the sets of cards and then tell you as output whether or not there's an arrangement that does the job。

 you could imagine that we might have crafted this as a programming assignment at first blush it seems not so much more difficult than other programming assignments or programming tasks that you've tried so maybe would be a reasonable thing for us to ask you to do as your learning program。

Does early existing arrangement of cards with matching top and bottom strings。

And it's a reasonable idea。 let's do it， let's take end card types of input。

 easy to do and then solve the problem。And the surprising fact is that it's not possible to write such a program and we can prove that it's a rather amazing fact and so we could give you a job that you can't possibly do and we know it now we're not quite that sadistic with our students but there may be teachers out there who do so let's look at why we can say this Here's another impossible problem。

 a famous one called the halting problem and it's famous because Turing looked at this problem。

So let's say what we want to do is write a Java program that reads in code for a given Java function static method F。

 and it gets the input X and is supposed to decide whether or not F of x results in an infinite loop。

So for example， let's say we had this function as input。And if you study this one for a while。

 you can say， okay， I can look at this and say， yeah， it's going to halt if x is a power of2。

 otherwise it's not going to halt and so you can convince yourself that that's the case。

 and this one doesn't look that much different it's same thing except now instead of multiplying by two。

 x equals 2 x plus 1， we do x equals 3 x plus1。In that one well that's the colot's conjecture。

 we talked about when we did the recursion lecture， no one even knows whether that one halts or not。

 and people have studied extremely long sequences and so forth。

 but there's no proof that that thing halts for all different values of X。

So at least these examples show that it might be a challenge to write a program that reads in code for a Java function and decides whether or not it goes into an infinite loop。

What we're going to talk about next is a proof that it's not possible to write such a program。

 even leaving the Colette conjecture aside。That's called the undecidability of the halting problem。

So we say that a yes no problem whose answer is yes or no is undecidable if there's no Turing machine that can solve it。

 that is that can be guaranteed to wind up in a yes state or a no state。

The opposite of that is we say a problem is computable if there is a Tring machine that exists that solves it。

And what Tring showed in the same paper where he showed the universality of Tring machines is that the halting problem is undecidable。

And that's got very profound implications， first of all。

 that proves the existence of something that we can't compute。

 there's a problem that no Turing machine can solve。But because of universality。

 that means there's no computer at all can solve that problem and what's worst is there are many。

 many problems that no computer can solve and we need to understand this concept if we're going to be trying to solve problems with computers。

So as a warm up to think about the proof of the undeide believe the halting problem。

 we're going to talk about a logical puzzle called the Liar Paradox that goes back to ancient Greek philosophers。

So what you're supposed to do is divide all statements into two categories， true and false。

So 2 plus2 equals 4， we agree is 2， 2 plus 2 equals 99， we agree is false。Earth is round。

 earth is flat and so forth， earthwors， I guess have more hearts than three。

 so that one's false and Saturn rotates counterclockwise and so forth All statements want to be divided into two categories true and false。

But now consider the statement， this statement is false。Well， can we put it in the true category， no。

 because it says this statement is false， and if it's true， then it's false， that's a contradiction。

Can we put it in the false category， no， because if we put it in the false category。

 it says the statement is false and it's in the false category， so that's true。

 that's a contradiction。So what are we to make of this situation？Well。

 the source of the difficulty is self- reference a statement referring to itself and the logical conclusion that we can draw from this is that you can't label all statements as either true or false。

 here's an example of a statement that can't be labeled either way。

So we made an assumption that's not true and the existence of this statement is false。

 contradicts the assumption and that that's a proof that you can't do it。

 that's a way to think of the proof now that we're going to do for the halting problem it's a little more complicated than this。

 but it's based on the same idea。So this is not tourings proof because we're going to do it in terms of Java programs。

 but by universality， we may as well。So here's how。

 So we're going to assume that there's a function halt that takes the code of a function。

 say it's a string is input and the。An input to that function X and solves the problem。

 So any function， any input to that function， this function halt will tell us whether or not it goes into a loop。

And again， I might as well use Java because we could phrase the same thing on a touring machine。

So this is an amazing function， you have some terribly clever analysis of F and x。

And it can return true or false， either it halts or it doesn't hold。

So the arguments of the function in the input say encoded as strings。

 the return value is true if F of x halts and false if F of x does not halt。

And that function itself is always halt， it's supposed to be able to do this for any function and any input to that function。

And the idea is， like the liar's paradox， we're going to make that assumption and we're going to follow a logical argument。

 and if we get to an absurd statement， then we know the assumption is false。

So here's how the proof goes， again， assume the existence of halt F of x that solves the problem。

So that's our code now within the comments is something terribly clever。

So now we're going to create a new function from that calledSt of F。

 and that takes a function as argument。And what that's going to do is give the function itself as input。

So and they're all strings， so there's no problem with doing that。

 So what St is going to do is if F of F halts， it'll go into an infinite loop。

And if F of F doesn't halt， then it'll halt kind of the opposite and that's a simple code。

 if we have halt， then we can just call it with both its arguments the same and if it's F of F is going to halt just go into an infinite loop so that's strange it's just a client to or assume solution to the problem。

Now， and this is why we call it strange， we're going to call that function with itself as argument。

So the question is， does that thing halt or not halt， let's look at the two cases。



![](img/468af960e0edb7817c688e8f55d7ed75_2.png)

So if strange are of strange halts， then if you look at the code for strange or strange。

 it goes into an infinite loop。Strange or strange halts。 It goes into infinite the loop。

 That's the definition of strange。If it doesn't halt on the other hand。

 then it halts again that's the definition of strange and that's absurd if we were to have a solution to the halting function。

 we can make this call on it's just a client that either if it it doesn't halt or if it doesn't halt it halts and that means that since our only assumption was the solution to the halting problem。

 that thing cannot exist。This is admittedly a little mind bendending for people not used to logic。

 but you can go through and check all the steps of this。

 it's actually pretty simple extension of the Liar's paradox the way we've got it phrased。

But it's very profound consequences。

![](img/468af960e0edb7817c688e8f55d7ed75_4.png)