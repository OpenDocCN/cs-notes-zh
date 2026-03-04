# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P19：19_05_01_符号方法.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/086d8d8812da7f87d1079896072e3dcb_0.png)

Today we're going to talk about an introduction to analytic combinatorics。

 it might seem a bit strange in a course entitled analytic combinatorics to not get to this topic until the middle of the course。

 but as you'll see it builds upon all the things that we've talked about to this point and gives us a coherent starting point from where we can go forward in the analysis of algorithms and the analysis of combinatorial structures and I hope by the end of this lecture you'll have a pretty good idea of what analytic combininatorics actually is。

We'll just start with a brief overview it's the analytic combininatorics is a calculus for the quantitative study of large combinatorial structures and most of the work behind analytic combinatorics is set forth in our bookAnalytic Comininatorics thatll be the basis for part two of this course。

 but it also plays an important role in the analysis of algorithms and a tie between elementary combininatorics and the kind of analysis that we need to really study computer programs。

So the features， the basic features of analytic combinatorics is that we begin with formal combinatorial constructions。

 so that is we have a mathematical way to specify what it is that we're studying。

The generating function that we've talked about in the third lecture is really the central object of study in analytic combinatorics。

Number one， because we have transfer theorems that can immediately give us generating function equations from the combinatorial constructions。

 and number two， because we can take transfer theorems to give us estimates of the values of things right from the generating function。

As I mentioned last time， our asymptotic results are going to extend in principle to any desired precision on the standard scale。

And most important is that it's a calculus that is we can handle variations on fundamental constructions very easily in those kinds of variations help us cover a very broad variety of problems for study。

So this is just a graphic depiction。 We start with combinatorial constructions。

 and we use a symbolic transfer theorem to get a generating function equation。

 and that process is sometimes known as the symbolic method。

Then from the generating function equation， we use analysis and we use analytic transfer theorem to get our coefficient asymptotics directly。

Essentially， this process allows us to avoid a lot of the detailed calculations that we've been doing in the analysis of algorithms and combinatorial structures for example。

 in analytic combinatorics if you want to know the number of binary trees within nodes。

There's a combinatorial construction and we'll go through the details of this that immediately transfers to a generating function equation that immediately transfers to coefficient asymptotics for the result。

 without going into all of the detail。 That's the overview。

 We'll end the lecture with this slide too， and you'll understand everything that goes behind the transfers。

So the beginning point is the symbolic method， so we'll start by talking about the symbolic method。

Now it's an approach for number one， for defining combinatorial constructions。

 but mainly for translating them to generating function equations。

And the way that we do that is define a class of combinatorial objects。

Toine some notion of what the size of an object is。

Then define a generating function whose coefficients count objects of the same size。

 That's what we've been doing in generating function counting in several examples already。

Then we're going to define operations that allow us to give constructive definitions of objects。

And then from those operations， we're going to have translations for each operation that defines a construction to an operation on a generating function。

And this is just the kind of notation that we use upper uppercase letters for combinatorial objects。

 some notation like absolute value for size and then the generating function we have the same letter as as the class except it'll be a function of a variable usually Z and then the operations actually will involve familiar symbols so now we have to get started somewhere so there's a very formal basis that and after these definitions we'll do examples and you'll see the need for these but it's a good thing to talk about them right at the beginning so what is a combinatorial class is just a set of objects and a size function。

Now we have to have something to begin with， and we call those atoms。 Those are objects of size one。

We also for convenience， have a atom of size zero， which is a neutral object and that's useful for describing。

 you'll see that's useful for recursive definitions。

So a combinatorial construction uses the union product and sequence operations that I'll talk about in a minute to define a class in terms of atoms and other classes and we start with the very basic building blocks over on the right where the notation capital Z contains a single atom。

 then there's notation capital E， which is a neutral class that contains an atom a size0 and then also there's an empty class and again。

 not worthwhile to spend time in these definitions right now but to refer back to them when we use them later on if necessary。

So here's a very simple example of a combinatorial class， the natural numbers。

 so the definition of a natural number is a set of atoms。

 or since you can't tell the difference between atoms。

 that's what we mean by unlabeled and we'll get into that detail and more。Much more detail later。

a setter a sequence， it's the same thing。 So there's only one object of each size。

So we most usually know at the beginning， we're most interested in the counting sequence how many objects of each size there are。

 in this case， there's only one。And we use ordinary generating functions。

 so the ordinary generating function for natural numbers is just one over1 minus E。

So that's a simple example of a combinatorial class and actually that it seems trivial and the base the early ones do seem trivial。

 it's when you put them together that you get interesting and useful mathematical results。

 So for example， this combinatorial class is a basis of studies of things like partitions of natural numbers how many ways can you break them up into somes and compositions and so forth。

 we don't get into that too much in part one， but we will in part2。

Here's something that we study all the time in computer science a bit string。

 a bit string is a sequence of zero or1 bits， and that's very familiar just defining this familiar class。

Not to get used to our notation and conventions。So how many bit strings are there of length n， Well。

 there's 2 to the n。 So what's the OGF， it's 2 to the N Z to the n。

 which is 2 z to the n or1 over 1 minus2 z。So it's another example of a combinatorial class。u。

Here's one familiar one recast in terms of analytic combinatorics。

 so a binary tree is empty or it's a node in two binary trees that are in sequence。

 the order matters。So those are familiar binary trees that we studied before。

 we know the counting sequence is the canalan numbers that was subject of quite a bit of lecture three。

And it's got this OGF and that derivation is all given in lecture three。

So those are three examples of combinatorial classes and now I want to show constructions and how we build those things so for unlabeled classes so that's and again I'll talk about the distinction we' labeled in a minute we're just going to use three different constructions if A and B are combinatorial classes of unlabeled objects。

 then we have the disjoint union a Cartesian product in the sequence operations。

And here's the meaning of each one of those A plus B is just copies of objects from A and B。

 you take one from A， one from B， and that's the disjoint union。

Cartesian product is ordered pairs of copies of objects， one from A and one from B。

 and sequences sequences of objects from A。So those are the constructions。

 and these are just examples of how a construction might work。So for bit strength。

you can use the usual distributive law， so 00 plus 01 is I got copies of 00 and 01 and the same on the right。

 and if we do the Cartesian product of those， we have to take each possibility on the left in sequence with each possibility on the right so there's six possibilities there。

 so that's an example of a use of the Cartesian product and disjoint union operations。

So here's one just with unary numbers， so an atom， a cartesian product with a sequence of atoms。

 gives that list。And there's binary trees， so an external node kind of atom crossed with an internal node kind of atom crossed with a little tree of size1 gives a two tree note that's the kind of constructions that we're going to use and those are interesting and we'll see how to use those to precisely define classes of interest。

But in unlabeled again， we'll talk about later what we mean by that。

But what's most important is the idea of a transfer theorem。

And this is the first basis of the symbolic method， the idea is while we're constructing the classes。

 we're also developing equations for their generating functions because for every operation we have a corresponding operation on the generating function。

And for simple， unlabeled classes， they're quite simple， so for example， for disjoint union。

If we take disjoint copies of objects from A and B， and we form the disjoint union。

 the OGF for that class is the sum of the OGFs of the two classes that were operating。

For Cartesian product， it's the product。 I'll do a proof of this in just a second。 and for sequence。

 it's one over 1 minus。So whatever construction we make。

 we can translate that to an operation on the generating function。 So anything that we can construct。

 we have a generating function for。So and these are the proofs and these are very straightforward from the kind of GF generating function count arguments that we did when we talked about generating functions。

If gamma belongs to a plus B， then they're disjoing copies， so some of them belong to A。

 some of them belong to B， you split the sum in those two ways and you have a of z plus B of Z。

For cross product that's a convolution again they break up into independently into the ones from A and the ones from B。

 the size of since you've taken one from each， the size of gamma is the size of the alpha 1 plus the size of the beta1 and those are independent so that's the product。

And sequence follows from the idea that sequence is like the product of two， product of three。

 product of four， it's just the geometric series gives the proof for the sequence。

So that's the transfer theorems， and that's the proofs。

 And from this point forward with the symbolic method。

 we don't have to worry about P sums involving convolutions anymore whereas。

We can get so we can are practiced at doing convolutions and so forth， but with this。

 we can do multiple convolutions and we don't have to worry about carrying around those details。

 We know what the generating function is going to be。

So let's just look at how it applies for binary trees so so every time that we're going to study a combinatorial class。

 we're going to do it according to this rubric here， so we have to articulate what's the class。

 it's the class of all binary trees。What's the size function。

 A combinatorial class is a set and a size function。

 and we're going to use a number of internal nodes in T。

The ordinary generating function is the sum over all trees in the class z to the size。

 and as we discussed when talking about counting with generating functions that for every size n there's going to be T sub N that gives us the counting sequence。

 the coefficient of z to the n in the generating function is the number of trees。

 that's what we're going to be looking for。We need atoms to get going。

 we have internal nodes and external nodes， so we'll denote external nodes by Z subbox and internal nodes by Z sub dot。

 and we want to count according to internal nodes， the size of an internal node is 1。

 the size of an external node is0。So that's the setup。

 That's the building blocks on the generating functions of these little classes。

 since the size for an external node is 0， it's 1。 size for an internal node is1。 It's Z。

 That's the generating function for that little class。Okay， so that's a setup。

 and then here's the construction。And this is just using the union and Cartesian product rules。

 you can read it in English or you can read it in math。

 it says a binary tree is an external node or it's a tree connected to an internal node connected to a tree。

And that's what we mean by a binary tree。 this just makes it rigorous， so that's the construction。

 so that's a description of the class of all binary trees， a recursive description。

 but it's a description of the class of all binary trees and now what's significant is we can use the transfer theorem to immediately translate to the generating function equation。

Z sub box， the generating function is one generating function for Z sub dot is z generating function for the two T's is t of z and your Cartesian product of those is the same as the translates to the product of the generating functions。

 but no sums involved there， we don't have to do sums anymore to get generating function equations of this nature。

Now the next step is to extract coefficients， we're going to talk about that later。

 I'll just remark that this is something that we studied already to finally get out to the answer that the coefficient of Z to the n and that function is。

Asymptotic to for Vienna were a buy in Q。But for now， when talking about the symbolic method。

 we're going to consider how do we get those generating function equations。

 that's the first part of analytic combinatorics， the symbolic method and we'll look at lots of examples of that and then later we'll talk about how do we get the coefficients out。

So that's our binary tree analysis recast in terms of the symbolic method。

 all of the calculations that we did before are in there， but it's a much， much。

 much more general setting and we'll see how important that is as the course goes on。

So what about kind of just as a similar example， what about if we want to count binary trees by external nodes？

So that's a different comb class because it's got a different size function。

 and we didn'ote that with box of tea。And the atoms are a little bit different because we consider external nodes to be size1 an internal node to be a size zero。

 and the generating functions are different。So it's the same construction。

 but the atoms are different， so we get a different generating function equation。

It's a really similar generating function equation Actually， T box of Z is Z T of Z。

 If you plug in Z T of Z in that equation， and then divide by Z， you get the same equation as before。

Well， this is a proof that the number of binary trees within n external nodes is the same as the number of binary trees within n minus1 internal nodes。

 there's easier proof of that， but this is showing the consistency of the analysis in the ease of developing a combinatorial construction to get a generating function equation。

Let's look at some other examples， what about binary strengths？And just as a warm up。

 just to check our understanding of the notation and atoms and constructions and transfers。

 let's try to count binary strengths， we know what the answer is， so our class is。

 the class of all binary strengths。The sizeize is the number of bits in the binary string。OGF。

 same as before， same as always， for every object in the class。

 you add up Z to the size of that object， and that brings the counting sequence as the coefficient of Z to the n in that function。

For binary strings， we have two atoms， either0 bits or 1 Bs， I will call them Z0 and Z1。

 They're both of size 1， and they both have generating function Z。

So how many binary strings within bits， while a binary string is a sequence of zero and1 bits。

 that's what that says。 that's the definition of binary strings。

And now we go to the transfer theorem， Z0 plus Z1 is2 z。

Sequence of 2 z1 over 1 minus binary strings of sequence is 01 bits。

 and the transfer immediately gives us B of z equals 1 over1 minus2 z。And that checks。

 coefficient of z to the n and b is z is 2 to the n as we expected。Very simple in elementary。

 as we'll see in just a minute， this translates to more interested。

 interesting and much more difficult to solve problems。Just as an aside。

 there's lots of ways to construct any combinatorial class。

 here's an alternate way to do binary strings， the same starting point。

 but we can use this construction。A binary string is either empty or it's a zero or1 bit followed by a binary string。

That leads to the generating function equation direct from transfer theorem1 plus b of z equals1 plus 2 z B of z。

And if you solve for a B of Z， you get the same result。that's another way to do it。So again。

 very simple constructions， immediate transfer to GF equations。

 then it's just going to be a matter of extracting coefficients。呃。

So here's now a first example of a problem that might be more difficult to solve and it's representative of very general treatment that we'll do in chapter eight。

How many inbit binary strings have no two consecutive zeros？

Actually there's lots of practical applications where such questions are quite important if we're looking for lots of consecutive zeros。

 some types of communications devices have problems in such situations and need to have codes that don't do that and so these things are well studied and this is a simple example but it gets to be much more complicated very soon that's what we'll talk about in Chapt 8。

But still。Let's take a look at solving this with the symbolic method。Okay。

 so it's the same it's binary strings， so it's the same setup our classes and the class binary strings that don't have any zero zero。

 we have the same setup for generating function and the atoms are all the same so what does the construction look like？

Well a binary string with no00 is either empty or it's 0 or it's 1 or 01 followed by binary string with no00。

 and you can check that that's a way to describe the class you have to think about a little bit。

 but it's not too bad and what's important though， is that we don't have just an English language description。

 we have a combinatorial construction。Commonatorial construction immediately translates to a generating function equation。

Z0 across z1 is z squared， Z1 general function is z epsillon plus z0。

 generating function is 1 plus z， so put all that together now we have a generating function equation for b00 z that we can solve and that's 1 plus z over 1 minus z minus z squared。

And again， extracting coefficients。These are problems that we know how to solve in this case it turns out and we'll look at the details later。

 in this case it turns out to be Fibonacci numbers。

 one over1 minus MIC squares F sub N z is f over1 minus misc squares fn plus1， if you add fn n plus1。

 you get fn plus2 and that checks with the anthfibonacci number checks with the numbers that we found on the previous slide。

 many of you probably noticed that it was Fibonacci numbers at that point。And it's clear that this。

Argument and this process is going to extend easily for binary strings with other kinds of restrictions。

 The trick is coming up with a construction that precisely describes your class。

 but often that's not difficult。 and again， we'll look at a general treatment of this later on in the course。

So those are just some starting examples， we're going to have many， many。

 many examples to follow all with the same basis in both part one and part two of the course。

We're often asking how many of some type of objects are there with some kind of restriction。

 we need to specify what the class is， we need to specify what the size function is and the atoms and write down the generating function and then we'll do a construction that mirror some English language description usually that'll immediately translate to an OGF equation and then the last step is to extract the coefficients and we'll talk about that at the end。

 so lots of examples to follow but before considering some more I want to talk about labeled objects but that's an introduction to symbolic method。



![](img/086d8d8812da7f87d1079896072e3dcb_2.png)

![](img/086d8d8812da7f87d1079896072e3dcb_3.png)