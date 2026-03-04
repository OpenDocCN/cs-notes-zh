# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P20：20_05_02_带标签对象.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

Next， we're going to talk about another important class of combinatorial classes that has to do with labeled objects and I'll explain the distinction between labeled and the unlabeled ones that we talked about and then look at some interesting problems。

So labeled combinatorial classes， the objects have and atoms。

 but we consider the atoms to be all different， and so just to make that clear， we label them。

 consider them to always be labeled with the integers one through n。So for just schematically。

 for unlabeled objects， you can consider those two objects to be different。

 they have a different structure。But when they're labeled。

 there's different ways to label them that make different objects， for example。

 that's two different ways to label that square。So in the one on the left。

 one's connected to two and four， the one on the right， one's connected to three and four。

 they're different and this one， it's not always clear how many different ways there are to label things in the one on the right。

 then there's three different ways to label that either one to or if three is's actually four ways。

 one， two， three or four are going to be the ones that connected to everybody else。

So there's a big difference in。Studying the number of different objects because the labels provide so many more possibilities。

In fact， when we're working with labeled objects， we use exponential generating functions for that reason。

 and that'll become clear as we move along。All right， so let's look at some basic simple examples。

 again， of labeled objects。So there's what we call an urn， and so an urn is a set of labeled atoms。

 so it the set that orders doesnt make any difference。 So again， there's only one of each kind。

 We could use this definition of unary numbers。And later on。

 you'll see why we use this characterization of it'll be very clear。So there's only one of each kind。

 but now we're going to use exponential generating functions。

 so the exponential generating function for Nns is E to the Z。As one of each kind。

 z to the n over n factorial sum is e to the Z。So that's a first basic example。

Next one is a familiar one， it's permutations， a permutation is a sequence of labeled atoms。

 sequence means the order is significant atoms are labeled。

 so every possible ordering of the atoms is going to give a different object。

 so there's two different objects of size 2， either one，2 or21， six different objects of size 3。

 24 different objects of size 4 and so forth。So what's the exponential generating function for permutations。

 well there's n factorial permutations of size n， and so the exponential generating function is that divided by n factorial times z to the n。

 which just leaves this with sum of z to the n or whatever1 minus C。

That's another basic combinatorial class。The n factorial serves to stop the generating function from blowing up too much because of all the different possibilities induced by the orderings。

Here's another one， a cycle， a cycle is a cyclic sequence of labeled atoms。

So that's everything's connected in the circle， but now there's fewer of each type and in fact。

 actually， if you study it for a minute， if you just fix on the largest or smallest element。

 then you can see that the others are permutation， so actually the counting sequence is n minus1 factorial。

So what's the exponential generating function for cycles？ Well， it's the sum of。

N -1 factorial Z V n over n factorial， which everything cancels but an n。

 So it's natural log1 over 1 minus C。Since another basic combinatorial class。

Now it's very characteristic of analytic combinatorics to start with extremely simple derivations in classes like this。

 but then combine them in interesting ways to provide answers to analytic problems of interest。

So what about the analog to the Cartesian product operation？ Well。

's it's much more complicated for labeled classes。When we take the product of two classes。

 so say this first example， one， we call it the star product， one star product of one，2，3。

 what we're going to get is objects of size 4， but they have to be numbered from one to four。

And what the combinatorics requires is that we do that numbering one to four。

 but we do it in all consistent ways， so in this case the second argument is a sequence that's in increasing order。

 so when we renumber we have to put that in increasing order on each one of the possibilities。

 so we can assign one， two， three and four to the first one and then the remaining labels we assign to the remaining three atoms but they have to be an increasing order。

Here's a more complicated example where we take the star product of a two cycle and a three cycle。

Again， when we do that we get five we have objects that consists of five atoms that have this structure。

 set of two cycle and a three cycle， but the atoms have to all be numbered with one through five。

 and we have to do it in all possible ways。So in this case there's you can choose any labels。

 there's only one way to label the two cycle and then you can choose five choose two or1 different ways to label the two cycle so the row first column is with the top one being one。

 you can have two，3，4， five for the bottom one second columns the top one being two。

 three and4 then after you've labeled the two cycle then you take the remaining labels and assign them to the three cycle。

 but you have to be consistent and maintain the order， so for example with three。

4 in this case with three， four is the labeled two cycle， the remaining labels are one。

2 and5 and they have to go in that order。So that's the star product operation relabeled in all consistent ways。

And when we get to applications， we'll see why that's not just intuitive。

 that's fundamental to working with labeled objects。So with labeled objects。

 since you can tell the difference in the ordering。

 we have more basic constructions and it's a much richer set of operations that we're going to work with and actually the ones that I'm giving both for labeled and unlabeled are only the beginning research is ongoing and people have developed many。

 many more constructions than I'm going to present here。

So we talked about so plus is the same you take copies of objects from A andB。

 but you relabel in all consistent ways， star product is where you take order pairs of copies。

Sequence is。Similar to what we did for unlabeled， it's a plus a star A plus A star star A and so forth。

 but you could have sets of objects like we did for urns and you can have objects arranged in a cyclic sequence。

 for example。So those are the constructions that we can use。

 a richer set of constructions and it leads to much richer set of objects to talk about。And again。

 what's important is that we have a transfer theorem。

If we have combinatorial classes and we know theirre EGFs。

 then the whatever operations weve picked from that list。

 we're going to know the EGF of the result of that operation。As before， if we do disjoint union。

 we have the sum， if we do the labeled star product， we have the product of the generating functions。

If we do a sequence of k objects， it's like A of z to the K。

 a sequence of any number of objects is summing those， it's1 over1 minus。If we have a set。

 it's a to the z to K over k factorial， and sets set of size k and the set of any size is some of those is E to the A of z。

Cycle is a to z the K over k and cycles of any length。

Cyes of size K is that cycles of any like this log of1 over1 minus A Z。

So if we know the generating function for a combinatorial class and we perform one of these operations。

 we know the generating function for the result， and that's extremely powerful。

Transfer theorem that's the basis for the symbolic method。

So let's just look at the basic constructions of the basic objects using these operations。

 So urns urn is a set of atoms。And that immediately translates to E to the Z from the transfer theorem for sets。

And as we saw， that gives the count of sequence un equals1。Cys。

 a cycle is a cycle of atoms and again immediately from the transfer theorem that tells us that the generating function is log of 1 over01 minus C。

 and therefore the counting sequence is n factorial times coefficient z to the n in that which is n minus1 factorial。

Permutations， as with bit strings is two different ways to define permutations。

 You can say a permutation is a sequence of atoms。And then read immediately from the transfer of theorem that the generating function for permutations has to be 1 over1 minus z。

Or you can say a permutation is either empty or the star product of an aomomy a permutation and that will generate all possible permutations that immediately translates to P of Z equals 1 plus z times P of z。

And then solving for a PfZ gives the same result。And then the county sequence is n factorial times the coefficient is z to the n in that。

 which is just in factorial。So those are just a starting point for some basic constructions。

The proofs of the transfer theorems， again， they come just immediately from the definitions and from generating function accounting the way that we talked about earlier。

So a plus again， they separate into the disjoint sets， and that immediately gives the result。

For star， it's a convolution of the type that we've seen before， but let's take a look。

 so to do all different relabelings， so we take one alpha from a and beta from B and to do all different relabelings。

 it's alpha plus beta choose alpha just like with the example I did with the cycles and then。

So that's a number of ways you can relabel and then the size of the an object composed of an alpha the beta is z to the alpha plus beta and a gam of factorials alpha plus beta factorial and then if you take that complicated sum。

 the alpha plus beta factorials cancel and you can separate out z to the alpha over alpha factorials z to beta over beta factorial to get that it's a product again。

 that's a complicated convolution， but this is the only time we have to do it。

And for the other operations， I have a slide that's got lots of dense math on it。

 but it's pretty simple， so as we saw before， A of z to the K is the number of K sequences。

 this is a generating function for exponential generating function for the number of k sequences of size N so and then that's just as we saw several times before。

 and if you add those all up for a sequence of any length you get one over1 minus C。

But if you have all the K sequences of size n， then you're going to have each K cycle of size n appear k times there。

In each cyclic orientation， so that means that A of z over to the K over K is the EGF for K cycles for cycles of K objects。

And then summing all those up gives the result for cycles of any length。Similarly。

 if you have all k sequences of size n， you're going to have all sets appear K factorial times。

So that means that a to the z to the K over k factorial is the exponential generating function for the number of k sets of P N。

 and then it summing all those up， give the result that for any set， it's E to the A of z。

So these are worthy of study， but they're very straightforward and immediate from the definitions and basic ideas of generating function counting。

So let's look at a much more interesting example。So the idea is that we have these operations。

 we can combine them in various interesting ways and actually as we'll see in part two。

 there's every way of combining these basic operations leads to combinatorial class that people have studied in detail but there's many more operations we can throw in as well。

 so let's look at this is a famous one how many different sets of cycles are there of labeled atoms for example。

 three atoms you could have a cycle of size3 there's two different ways to label that or you could have one cycle of size1 and another cycle of size two and there's three possibilities for labeling that or you could have three cycles of size1 so there's a total of six。

 sets of cycles of labeled atoms。And if you work it out for four on the right is all the possibilities of sets of cycles of four atoms。

 you can have them before singleton cycles， or you could have one cycle of size4 and there's six different ways to label that one or you could have something in between all the possibilities are laid out here you might recognize the numbers and yes there's n factorial sets of cycles of n labelbeled atoms and what we'll look at next is how we learn that from analytic combinators。

And it's not just instructive。 It forms the basis for us to solve problems that we couldn't otherwise solve。

 as you'll see。So let's use our regular methodology， we have to articulate what our class is。

 so it's P star is the class of all sets of cycles of atoms， number of atoms is the size， the EGF。

 as usual brings together as coefficient E the end ofinectctorial is the number of sets of cycles of and atoms。

The atoms are just labeled atoms for labeled classes， it's always the same。嗯。What's our construction。

A。It's nothing more than saying a set of cycles of atoms is a set of cycles of atoms。

 that's what the math says， and it immediately translates from the transfer theorems to cycle of Z translates to natural log 1 over1 minus Z set of something is E to that power。

And that's just1 over1 minus e。 so therefore the counting sequenceial is in factorial。

 so that's the same as for permutations。And again， that's a very quick result。

 it just comes from the combinatorial description， a set of cycles that we could get the generating function for sets of cycles immediately from the transfer theorem。

Now this is a well-known combinatorial byjection， a permutation is a set of cycles and to see that you start anywhere。

 say was start at 4， so here we have the permutation and then we have the index of the sequence where is it in the sequence。

 so if we start at the fourth thing in the sequence or the fourth entry in the permutation it says 10 so we go to 10 and 10 says the tenth entry sequence is6 so we go to6。

And the sixth entry in the sequence is 15， so we go to 15。

 and the point is as you see from this example， eventually you're going to get back to where you started。

That's a cycle and we could depict that thing just like this just when you go from four to 10 to 6 to 15 back to4。

 and if you do that， if you've already done it， if done an item ignore it， otherwise do this process。

 you can convert any permutation into a set of cycles and it's worthwhile exercise to figure out how to reconstruct a permutation from a set of cycles。

 but that's a well-known byject。So that brings us to our first actual problem that you might not know the answer to or you might because it's a classical problem。

 but we'll get to one that you don't know the answer to。

And that's the derangements problem and this is a famous problem from the 18th century and it's usually。

 well at that time it was cast in this way， so you have N people who go to the opera and they leave their hats on a shelf in the cloak room。

 but they all look the same and so when they leave they each grab a hat at random。

And the question is， what's the probability that nobody gets their own hat？So。In in terms of commons。

 we refer to this as a derangement。Nobody gets their own hat， that means there's no singleton cycle。

 so that means that getting your own hat means if you're in position four， it's the fourth item。

So and that's a singleton cycle so the question is what's the probability that a permutation is a derangement or how many derangements are there now just as an amusing aside this problem has been posed in the centuries since in many different ways。

 that's the classical opera way， so some people say。

 well a professor returns exams to students and by passing them about it random。

 what's the probability that nobody gets their own exam so lots of people use that way of posing the problem in combinatorious classes。

Or a more fun way to do it as the drunken sailor， so you have a group of sailors that are a bit inebriated and whenever when they get back home they wind up sleeping in a random cabin。

 so what's the probability that nobody winds up in their own cabin。

or maybe more relevant to college students is going to end students who live in a single room and they get also in a state of ineviration。

 what's the probability that nobody ends up in their own room that's all the same problem and to solve that problem what we want to do is count arrangementranges。

So derangements or permutations with no singleton cycles。

 so this is our table of sets of cycles which are equivalent to permutations with the ones that have singleton cycles grayed out。

So there's nine permutations of p Pscii4 that have no singleton cycles。Probability that nobody。

Wents up with their own half because only four is9 over 24。

And so this maybe is not a familiar sequence， so let's see how to analyze that with the symbolic method。

Now we'll just go through our。A regular regimen， we're going to define D to be the class of al arrangements。

 sizes number of atoms， standard labeled atoms， generating function is always the same。

 exponential generating function， and so what's the combinatorial construction。

So one way to phrase it is this way a derangement is a set of cycles where the length of the cycle is greater than one。

 and we just indicate that would cycle greater than one。Of atoms。

Permutations is a set of cycles of atoms。 This one excludes the ones of length 1。

that one immediately transfers， so deranges or permutations are no singleness cycles is what it says。

And so set is E to the whatever it is and what's the generating function for the cycles of length greater than1 Well the generating function for all cycles is z plus z squared over tub of z cube over3 like that and we're just leaving out the first term so that's immediate translation and that's the same as log of1 over 1 minus z minus z。

Is that infinite series is exactly log of 1 over1 minus e minus e。 And if we simplify that。

 we get e to the minus z over1 minus E。Imediate translation to the generating function。

 another way to， for derive it， which maybe is even easier to understand is we can say that。

A what is a permutation， A permutation is a set of singleton cycles crossed with a derangement。

 And so that's that's another way to phrase it。 And then that one immediately translates to E to the Z D of Z equals1 over 1 minus Z and solve for D of Z you get the same result。

So symbolic method gives us the generating function。 Now。

 extracting coefficients from this one is a little more complicated。

 We actually did it already in our lecture on asymptotics。

So that's the result is that it's asymptotic to 1 over E and let's just look at each of the elements of that。

 so first of all， we're looking since we want a probability。

 it's convenient that we're using exponential generating functions in our probability denominators in factorial so we're taking advantage of that。

Coincidence， it's not really a coincidence。 but in this case， it it works out。

 So to get the probability， we just look at the coefficient of Z to the n in the generating function。

 not in factorial times Z again， because it's going to divide right out。

So that's a D the n over n factorial So and what's that coefficient。

 Well it's a convolution E to the minus z times11 minus z， you just do the convolution。

 the coefficient is z to the n and that is the sum K from0 to n a minus1 to the K over k factorial。

And that's a straight convolution， and then that's a sum that we looked at as one of our examples for bounding the tail in the asymptotics lecture to show that's asymptotic to1 over E and it's very close to one over E。

We're going to look at an easier way to get this at the end of this lecture。

But the symbolic method gets us there and then provides a practical solution to this kind of problem that actual chance that if you go to a party and get yourself in a state of ineviation and wind up in a random room you've got a pretty good probability that nobody ends up in their own room。

 36% or maybe a way to tell your parents about this problem is when students graduate and throw their hats in the air and everybody catches a random hat。

 36% probability nobody gets their hats back actually your parents probably wants you to get your or the rental company probably wants you to get your own hat back and so there's the idea of generalized your arrangements so if you've got a random hat。

 you can always get your own hat back by following the cycle。So student 4 wound up with 10s hat。

 she can go to 10，10's got six' hat， then she can go to6， six ats 15's hat。

 then she can go to 15 or 15 there's her hat， so following the cycle will get your hat back so then now we have the more general problem。

 what's the probability that all cycles are of length bigger than M。

 that everybody's going to have to would have to follow at least talk to at least M friends or M people and random people to get their hat back so that's a generalized arrangements problem。

 what's the probability that all cycles are of length bigger than M。

Now that problem it's much more difficult to analyze。

 but with the symbolic method we can get right to the generating function。

 so it's just generalizing the argument that I just gave D sub n is the class of all generalized degree arrangements。

 no cycles in the linked less or equal to M， everything else is the same。So the construction is。

 it's a set of cycles that are bigger than M of atoms that translates directly to generating functions。

 you just start at ZDVM plus1， so it's the same series now starting at ZDVM plus1。

Or that's log of one of1 minus z minusd over z z squared over 2 all the way up to zdm over m。

In simplifying that， we have E to the minus z minus z squared over 2 minus e cubed over 3。

 so further up to c the M program over 1 minus z。So that's the generating function that we get immediately from the symbolic method。

And very quite simply， without this symbolic method。

 you might have some trouble getting to this generating function on your own。

 certainly certainly a lot of these things is possible to do because what's behind the symbolic method is so simple。

 but the symbolic method really makes it so that a child can do it。So， that's the。

A generating function equation。 Now to find the answer to this problem。

 we need to extract coefficients from this equation。That one， not so clear。

 that would be an MOA convolution and you know go ahead and try to extract coefficients from that one。

 so that's going to motivate how can we find the coefficient。

 How can we estimate the coefficient of Z to the N in that complicated function that's going to motivate the second part of analytic combinatorics。

 the analytic transfer theorems。But that's a basic introduction to symbolic method for labeled objects。



![](img/e56888a1499772d62135c58875a72d53_1.png)

![](img/e56888a1499772d62135c58875a72d53_2.png)