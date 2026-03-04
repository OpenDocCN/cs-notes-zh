# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P34：34_08_03_字典树.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/6124176be3b8f791e7e2827105410e96_0.png)

Now we're going to look at Tris， which is a class of combinatorial objects that not really has only come into study in recent years due to computer applications and not found in classical combinatorics。

 but actually a very interesting rich combinatorial and analytic properties。

 so I'll spend some time really just talking about what triess are and their applications before we talk about the analysis。

So one way to look at a try is just as a binary tree where the external nodes can be marked。

 black ones are called void nodes， and then the white ones are non void。

So you take a binary tree and mark some of the external nodes to be void now there's a rule and that is that you can never have two void nodes that are siblings of each other in a leaf。

So these of a void node is not void， that's the rule， so that's what a try is。Now。

 that seems kind of arbitrary， but you'll see when we look at applications how these rules play a role。

Actually， for an exercise， you might give a recursive definition of what a try is。

So the most usual way that we think of tribes is as representing a set of bit strings。

Each tri corresponds to a set of bit string where each nonvoid external node represents one bit string and you get the bit string by taking the path from the root to a node taking a0 when you go left and one when you go right。

 for example， if we go 0，0， left left， right， right left。

 we get down to that nonvoid external node and we say that that node represents the bit string that we got that defines the path that we got there。

 0，0，110。Or over here， 0010， I'm sorry， 1010， that nonvoid note represents the bit string 1010。嗯。

The path from the roottua node defines the bit string。

So now the void nodes have a different interpretation that derives right from this definition。

 for example， if we go right four times and then left， we come to a void node。

 what that means is that no string with that prefix is in the set of strings represented by this try。

The tri represents， in this case，  one，2，3，4，5，6， seven bit strings。

 and then the void nodes represent the prefixes of all the bit strings that aren't represented。

So that's what we think of as a tri corresponds to a set of bit strings。

Or another way to look at it is it's all worked out here， so this try represents， as I said。

 seven different bit strings。Those are shown at the top now on the left is the bit strings that from that set that start with zero and on the right。

Try on the right represent the bit strings of that set that start with one with the one stripped off。

And so recursively going down， that's another way to see the sets of brstrs that are represented。

Now this only works for sets of bit strings are said to be prefix free。

 so that is no member of this set of bit strings is a prefix or of another one in that set。

We can handle that by using void and nonvo internal nodes。

 but in applications I'm going to talk about that are typical。

 it's okay to just work with prefix free sets。So like for example， fixed length。

 all the bit strings are the same length and it's prefix free because they're all different。

 they're all the same length and they're different you can't have one being prefix of another and that's a typical and useful application of triess。

This is a try that represents those three strings。There's lots of applications of tries。

 if you look in our algorithms book you'll find TRcode for sorting for simple tables with string keys and for suffix arrays。

 which I'll refer to in a minute， they play a role in classic data compression algorithms。

 hustman's code and Leel of Welsh compression， and we'll look at the use of tries to understand decision making collision resolution leader election algorithms。

 they play a very important role nowadays in network systems and bioinformatics， internet search。

 all kinds of commercial data processing， very important data structure that's often overlook that's why I'm taking the time to talk about some of these applications to motivate the analysis because they're not so easy to analyze as we'll see。

So here's the basic application which is for symbol tables。

 so T represents a set of bit strings so what we have is just going from the definition。

 a search algorithm for determining whether a given bit string is in the set represented by the try and the basic idea is if the leading bit of your key is zero go to the left if it's one。

 go to the right and then use the remainder of the string recursively。

If you get to avoid external node， it means that the one you're looking for is not in the set represented by the try。

 If you get to a nonvoid external node and you're at the end of your bitstr， then you report success。

 You did find a key。So for example， let's say we're going to search for the bit string 0011 in this try。

 start with the0， go to the left， next one's a0， go to the left， next one's a one， go to the right。

 next one's a one go to the right we're at the end of our string and we're on a nonvoid external node so that string is in the set of bit strings represented by our try。

Let's look for 10，110， so start with a1， go to the right，0， go to the left， one， go to the right。

 one go to the right， we hit a void external node， so that string is not in the set represented by our try。

It's a very natural search algorithm to have to try and represent a set of bidstreams。Of course。

 everything can be represented as a bit string， so this is a natural algorithm for anything represented in a computer。

So of course， we're going to to， for an algorithm like this。

 I want to know what's the expected search time under reasonable model of randomness。

 that's the type of thing that we want to analyze。Now。

 what about inserting new keys or a new bit string into the set represented by the try？Well。

 what we'll do is we'll insert by searching until we get to avoid external node。

 so if we wind up at an internal node or nonvoid external node。

 that means if we'll have a prefix free violations and we can deal with that in some way。

 but the insert a new key it's going to wind up at a。Vvoid external node， so to insert 01。

110 we go left for the 0， one right for the one， and now we're at a void external node。

And so now what we want to do is for each remaining bit in our key that we want to insert。

 we want to add a new internal node and with one void external child and then the other one corresponding to our bit so in this case our next bit is one so we put if the key started 010。

 then it's not in the set of strings， but 011 that could be this one。

AndThen we do it again for another one， and then the next bit is0。

 so we put the void external node to the right and non void to the left。

 so that's how we would insert 01110 into this try。

Now there are variants where you just keep track of the tail in some way with pointers and people and those are well studied and there's lots of reasons to do that sort of thing。

 but the simplest version also is very effective and that's what we'll stick with right now。

So that's a search algorithm and an insertion algorithm that gives the basiss for simple table using the T data structure。

 which is a very useful algorithm。And then a natural question that probably already occurred to many of you is。

 what about these void external nodes， it seems kind of a waste to have all these void external nodes there in this data structure。

And so we're going to want to analyze how many there are to make sure that we understand how much space a tribe takes。

 but it's a very compact data structure and that analysis is certainly interesting and relevant in practice。

Okay so here's another application of triess what we want to do is we have a given string s and just for an example I'll use a genomic string made up of ACs。

 Ts and G's， and these things could be huge， it could be billions of letters。

And we want to know is a particular substr in our string。

 so like if for this string is ACTA in there and the answer is yes starting at zero what about CCT。

 yeah， there's plenty of places where CCT occur in this string。AndWhat about TGA， no。

 there's no occurrence of TGA。So we have a specific string that's huge and we want to be able to quickly do substr search and there's all kinds of applications in genomics where it's important to be able to do an operation like this quickly。

So search and genomic data and this is also usable。

 useful in internet search when you do a Google search。

 you not only get to the page that you're looking for， but you get context。

 you get where the substring is in that page and that uses data structure like this and many other applications。

So the solution method that I'll talk about is a so called suffix multiway try。

 generalizing the try for this problem。And so the idea is to。If you have your given string。

 what we're going to do is work with all the suffixes of the string。

 so the original string A CCTA G G CCT， we leave off the A then we have CCTA and so forth。

 so if the string is of size n we have N strings for all the suffixes and we're going to treat those as different strings and just insert them into the try。

 that's called a suffix try。They now notice that's prefix tree， prefix free。

 none of these is a prefix of another because well theyre。All different lengths。

 it's a prefix free set and they all end， we have them all end with a character that isn't found anywhere else in the tribe。

So then the idea is that every internal node of this tri corresponds to some substring of our original string。

So to answer the question is X a substring of x， we use the characters of our query to traverse the try。

 so for example， if we're looking for A， CA， then we can。

When we get to a nonvoid external node that tells us that that one is in there and it tells us what position it is。

 so we built the T AC， if we see something that starts with AC。

 then we look starting a position zero and continue our search and the ACCTA is there。

If we encounter a void node， then so for example， if we're looking for CCT， then we find a void node。

Sorry CCT is there because we found it in an internal node but something like TGA。

 we end up at an void node and we're out of there， we reach the end of the string then we're fine if we hit a void node node that it's not there。

 so this is a very simple algorithm to answer this is x substring of S question and a fine application of tries and again the number of void nodes and what does it mean to be a random try and how long is a search and so forth all of these kinds of questions are going to be important and relevant in practice。

Here's another application of triess， Tris is a model for an algorithm。

 so called leader election algorithm。This is important in distributed systems。

 so the idea is you have a group of individuals and they would need to elect a leader。

And what they're going to do is flip each flip a coin。

 so it's a distribute that could be a large number of them they'll each flip a coin。

And we' count ones as winners and zeros as losers， so everybody that gets a one when they flip a coin survives for the next round and the ones that got zero are gone。

So now we just worry about the ones that got ones， again， they each flip a coin。In this case。

 the two green ones get a zero， so they're the losers and they're eliminated and only the ones that got one continue to the next round。

They each flip a coin again， two are eliminated and three are left the one they got ones。

 they each flip a coin in this case they all get one so they all advance to the next round and then we have a void note。

And then again they nobody eliminated now they each flip a coin and only the blue one survives。

 so that's the winner， so this is a very simple method for choosing a leader in a distributed manner among and people。

Now there's a possible problem and that is procedure might fail what if they all。Throw zero。

 then in that case they're all losers， there's no winner， procedure might fail。

So obviously we're going to be interested in what's the chance of failure well it's the probability that the rightmost path in a random try ends in a void note。

AndWhat do I mean by a random try， well it turns out that the model that associates with this and also works for symbol tables is it's a try that you get by inserting infinite length random bit strings into an initially empty try。

So there's three diverse applications of the Tri data structure。

 for a symbol table for substring search and for distributed leader election。

 and all of this is to motivate studying this combinatorial structure。

So for distributed leader we might want to know what's the number of rounds。

 well it's the expected length of the rightmost path in a random try so many rounds and then your probability of success from that you can calculate how effective this method is going to be。

So that's a brief description of triess， and next we'll look at analysis of tri parameters。



![](img/6124176be3b8f791e7e2827105410e96_2.png)

![](img/6124176be3b8f791e7e2827105410e96_3.png)