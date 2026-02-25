# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P28：3 - Spring 2023 Exam Level 06 Problem 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

可南家。If one Russia。

![](img/a5ec5085703b9070c01d7254388de26d_1.png)

Everyone， this is Sherry and this is the spring 2023 Ex Mo6 walkthrough in this video we'll be going over problem three asymptotics of weighted Quickuns and what this problem does is it combines the two topics of this week's discussion which are awaited Quickuns and asymptotics。

So let's just jump into the problem and as we go through。

 I'll try to point out some important things and try to guide you through what this problem is asking for。

So part A is a relatively simple question， it asks us what the runtime of is connected and connect are in a weighted quick union without path compression。

 and we have n which represents the number of elements。

So one thing to remember about a weighted quick union is that the height is always。

Is always O of login。So that means the maximum height that our tree have is a logarithmic factor of the number of elements。

And this means that the worst case runtime is also O of log n。

 because at worst we have to go to the bottom of our tree when we do either of these operations is connected or connected。

So our runtime is bounded by the Hearu tree， which is login。And then to think about the best case。

 we could also have a weighted quick union that looks like this where everything is connected to the root and in this case is connected and connected are going to be very efficient because we just have to traverse one level and so everything is going to actually be constant time。

 so the best case for is connected and connect are both constant time。Okay。

 the next couple parts of this problem are a little bit trickier where we have to analyze runtime and some special properties of weighted quick unions。

So first let's start with Part B， which we get this method add to weighted quick union and the problem tells us that it takes a list of elements so these are the elements of the weighted quick union and connects them in a random order stopping when all elements are connected so basically if I have like these elements one two through n I'm going to pick two of them at random connect them I'm going to pick another two at random I'm going to connect them I'm going to pick another to at random I'm going to connect them and we could kind of see this happening in our function here。

Based it reflects the conceptual description where we have elements and we use this pairs function on the elements and what does the pairs function do well the question tells us that it takes a list of our elements and it generates all possible pairs and just for a visual example of this if we have one two and three it might generate this set of pairs or this set of pairs so basically it generates any two possible pairs of elements。

And just one thing to know is that。If we have something like one， two。

 that's a pair and we're not going to generate two， one again， we don't see two。

 one anyone here because the order of the elements in the pairs doesn't matter。Okay。

 so and also the pairs function returns these pairs in a random order so we could get them in a nice order like this where all the pairs of one are first and then all the pairs of two。

 or we could get them completely jumbled like this first example here。Okay。

 and other important things about this function is that we have this if statement and like the question says。

 we stop when size is equal to elements at length， which means it's fully connected。

And the question tells us that the size method calculates the size of the largest component。

 so that just means when the largest component has all the elements in it。

 and we can also assume that pairs and size run in constant time so any of these function calls we can kind of ignore their runtime and just assume that they're constant。

Okay， with that， let's actually jump into answering the question。

 which is what is the runtime of weighted quickun in big omega and big O so what's the smallest runtime that this could have and what's the longest runtime this could have。

So there are kind of two parts to this problem what's the smallest and what's the largest so if we want to terminate this loop as fast as possible。

 we might get lucky and we might have something where it's like connect。Zero1。

 and then we have connect。Zero2 and then connect03 and then connect 04 all the way up until connect0 n。

And the reason that this is a very lucky case is because what's going to happen。

 we're going to connect0 and 1， and then we're going to connect0 and 2。

 and then we're going to connect0 and 3 and everything just gets directly connected to zero because the larger tree is always here because any other element is just going to have size one and this is going to continuously grow so we're just going to keep connecting everything to the root and our tree is always going to height one。

And the other nice thing about this is that this only takes n calls because we add one new element to our main tree each time and then so after n iterations we' done。

So the runtime of this is going to be n times the runtime of connect。

And the runtime of connect is going to be constant because like I said here。

 we're just going to have a flat tree that has one level in it。

 so we're in our best case scenario here where Connect runs in constant time。



![](img/a5ec5085703b9070c01d7254388de26d_3.png)

And so our best case runtime is going to be n iterations each constant time。

 so our best case overall is going to be linear or omega of n。



![](img/a5ec5085703b9070c01d7254388de26d_5.png)

Okay， now that we have the best case， let's analyze what the worst case could be。

And to think about this。Let's consider what our pairs would look like in the worst case。

And what it might look like is we have a bunch of pairars that are like this。And then。

 at the very end。There's one element only appears in the very last n because each element。

Is in n total pairs， right？Because it's going to be connected to we're going to have zero with one。

 we're going to have zero with two， we're going to have0 with three all the way up to zero with n。

And the problem is we might have something where all of the pairs， including zero are at the end。

 so we have01 here，02 here。0ero n here。 So all of these n are at the end。

That means we're never going to incorporate zero to our tree until the very last end calls。

 so connect。0 in last。And cold right， so a tree is going to look something like this。

 maybe two and this's going to have other elements in it， maybe has a certain height we don't know。

 but zero is going to stay isolated。Until the very last end calls。

And so we're going to have a lot more iterations of this because we don't stop until every element is incorporated into our main tree。

So what is the runtime of this going to be， it's going to be the runtime of number iterations。Times。

 run time。Of connect。Because we're doing this loop and the main operation that takes time is the connect call。

So first let's figure out how many calls are there actually before we reach this call where we finally incorporate zero into the tree。

 and I'm using zero as an example here but you can consider any node being the last node incorporated into the tree and just being isolated。

Well， the first one you have to think about is how many total pairs are there here and the answer is that there's going to be on the order of n squared。

 the actual answer is n choose 2， which is n times n minus1 over2。

 so there's going to be n times n minus1 over two total calls。And。

How many calls are there before we incorporate this isolated node。

 well there's going to be this many minus n because our isolated node is incorporated into our tree at the last end calls。

So in this part of the tree， in this part of our pairs。

 there's going to be n times n minus1 over two minus n iterations。

And then what's the runtime of connect in the worst case。

 well this goes back to part A and we said here that it's log N because again。

 the very worst case our tree has height log n， it can never have height more than that。

So we're going to multiply these two， we're going to multiply and choose two。Times log n。

 and this is theta of n squared log n because this is on the order of theta n squared。

So our worst case runtime is n squared。Log n。Okay， that's it for part C now let's sorry that's it for part B now let's move on to part C which we get a new definition we have a matching size connection and this is defined as connecting to components in a wayed quick union of equal size and what this looks like is for example if we are one and two and we connect these。

This is a matching size connection and we can make either one the root。

 it doesn't matter because these are both size one trees。

Another example of a matching size connection that might be a little bit more clear is maybe if we have one。

 two and three， four and we call connect on these so we might end up with something that looks like this。

And again， those are both size two。So that's an equal matching size connection。

And then the question is asking us what's the minimum and maximum number of matching size connections that can occur after executing weight add to weighted Quick union and again。

 add to weighted quick union， what does that do， it connects。Everything。So it keeps going。

 it keeps calling connect until everything is connected。And again。

 let's think about the best and worst case for this。

 and in this time this time we're going to think about it in terms of the matching size connections。

So let's start off with the minimum。The minimum is kind of similar to our best case for add to weighted quick union where we just keep connecting everything to the root so we first connect0 and1。

 then we connect 0 and2， then we connect0 and3， then we connect 0 and4。

 all the way ands we connect0 and n。And in this case。

 there's only one matching size connection at the beginning where we connect 0 and1。

 which are both size equals 1。 After this， we're just connecting everything。

 We're connecting isolated nodes to the main tree， isolated node to the main tree。

 So none of these are matching size connections。 And so the total number of matching size connections is going to be。

It's going to be one and there's not going to be anymore after the first connection。Okay。Now。

 let's move on to the next part， which asks us for the maximum number of matching size connections。

 And this case is a little bit trickier， but。We should actually think about。

So there's10 total elements， and so maybe instead of connecting everything to the main tree。

 we connect them in pairs。And what does that mean， Well， let's say we first connect zero and1。

So we're going to call connect0 and1。And then we connect two and three。

And then we connect four and five。And then we connect n -1 and n。So this is going to be。

Now we all have size  two trees， and now we connect all the size  two trees to each other。

 So we're going to connect these two。 We're going to connect。Like this。

And then we're going to connect4，5，6，7。 and then the same thing is going to happen to every tree。

 So basically we're just pairing up pair up size one， and then we get to size 2。

 and then we get to size 4。All the way up until we pair up。2。And over two size trees。Okay。

 and the question is， how many matching size connections does this actually make？啊。我。There's。

N over two connections made here right because when they're all size one。

 we connect the pairs to each other， we connect single elements to each other so we're going to connect n over two times and each of those is going to be an equal size connection and then when all the trees are size2 there's going to be n over four total connections that we can make because each tree is size two and we're making size four trees and then when all the trees are size4。

 there's going be n over8 matching size connections and then at the very end there's one matching size connection because each tree is size n over2 so when we connect there're just going to connect to each other in one single call。

And so let's actually add up the number of matching size connections that we make， which is one plus。

Dot dot dot plus n over 8 plus n over4 plus n over 2。And what does this actually sum up to， well。

 this is the geometric sum that we know and the geometric sum adds up to two times the last term minus1。

 which in this case the two times n over two minus1， which is just n minus1。

 so the maximum number matching size connections is going to be n minus1。That's it for this problem。

Here's my weekly exam tip for problems like these where you're asked about like specific cases。

 I really recommend drawing out examples， which is what we did here where we try to draw out the best case in the worst case for all of these questions。



![](img/a5ec5085703b9070c01d7254388de26d_7.png)

And it really helps you if you can think about specific cases instead of like a general idea。

 so make sure to do that on exams。That's all for this problem please feel free to leave any comments or questions below and。

Good luck in the rest of 61b。