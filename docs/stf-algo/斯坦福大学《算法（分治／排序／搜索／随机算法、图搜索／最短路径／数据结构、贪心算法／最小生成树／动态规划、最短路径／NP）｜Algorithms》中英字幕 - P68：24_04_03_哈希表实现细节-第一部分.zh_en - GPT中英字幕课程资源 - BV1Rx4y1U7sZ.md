# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P68：24_04_03_哈希表实现细节-第一部分.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

So in this video， we'll take a peek under the hood of hash functions and I'll discuss some of the high level principles by which they are implemented。

So let's briefly review the ra on detra of a hash table so the purpose in life for a hash table is to support superfat lookups so maybe you're keeping track of the transactions that happened on your website yesterday。

 maybe you're keeping track of your employees， maybe you're keeping track of IP addresses in an internet router maybe you're keeping track of chess configurations in a chess playing program whatever the point is you want to be able to insert stuff into a hash table and later remember whether something's there or whether something's not there so the implementations we'll discuss will generally also support deletions but that's pretty much it it's a very restricted set of operations but the hash table is going to execute them very very well so basically in constant time again subject to some fine print which we'll discuss a little bit in this video but then more deeply in a separate optional video so the two caveats are first of all the hash table better be properly implemented it's actually pretty easy to screw up a hash table to screw up hash functions we'll talk a bit about that in a few minutes and then also the data should in some sense be nonpathological and that will be discussed more deeply。

Separate video。I so let me give you an initial glimpse of some of the magic that's happening under the hood in hash functions。

 so first let me say exactly what the setup is。The first step is to identify all the things that you might want to be storing。

 so in other words， the universe of your application。

So this would be something like all possible IP addresses of which there's  two to the 32。

All possible names you might encounter， perhaps with a maximum of say， 30 characters。

All possible configurations of a chess board and so on and one thing I hope you can appreciate from these examples is that in many cases this universe is really big。

So the number of IP addresses is quote unquote only 2 to the 32。

 the number of all names you're probably talking more like 26 race to the 30。

 all chessboard configurations I don't even want to think about and what you want to accomplish is you want to maintain an evolving subset of this universe you so maybe you want to keep track of all the IP addresses you've seen on your website in the last 24 hours。

 you want to keep track of the phone numbers of all of your friends。

 you want to keep track of the chessboard configurations that you've explored in the past three seconds。

 whatever。And again， what I hope is clear from the applications we've been discussing is that this set S is usually of reasonable size。

 it's something you could store in main memory， maybe it's tens of thousands of IP addresses。

 maybe it's a few hundred names of your various friends。

 maybe it's in the millions of chessboard configurations， but still way， way。

 way smaller than the size of the universe。So without data structures。

 you'd have to resort to rather unsatisfactory solutions to maintaining this set。

So the first thing you could try， as we discussed in the previous video would be you just have an array with one position for every imaginable thing you might want to store in your set。

So this is the solution that's going to work well if all of your friends happen to have names that are integers between one and 10。

000 but doesn't scale when the universe size becomes really big as in most of these applications so the good news is of course it's an array and it's of course fast random access so you can access any position in constant time so if you have an arraybased solution indexed by all the elements of your universe you can do constant time insert delete and lookup the bad news is the space requirement is proportional to the universe and again forget about being unsatisfactory that's just literally impossible infeasible in many applications in which you use hash tables。

Now， of course， to get the memory proportional to the size of the stuff that you're storing。

 an easy solution would just be to use a list， you know， say a wubly link list， something like that。



![](img/66c5cce31ab10350461037c3864c01a1_1.png)

Now with a list-based solution， the good news is is your memory is certainly proportional to the size of the set that you're storing and it's independent of the size of the universe from which these elements are drawn。

 the bad news is is to figure out whether something is or is not in a list。

 you generally have to traverse through most of that list and so that's going to take time proportional to the length of the list。

So really the question we're faced in implementing a hash table is can we get the best of both worlds of these two naive solutions on the one hand we want to have the constant time operations enjoyed by the array based solution。

 but on the other hand we want to have the linear space and the size of the set that we're storing that we get in the list based solution。

So to get the best of both worlds we are going to use an array based solution。

 but the array will not be big， itll not be with size proportional to the universe。

 the array will only have size roughly the same as the set that we're storing。

 so somewhere in the ballpark of the Carinality S。So the first thing we do is we decide on how big we want our array to be。

 so that length is going to be called n， we're going to have an array of length n and n is going to be in the ballpark of the size of S。

 It's going to depend on a few things exactly how n compares to S。

 but for now think of n as like double the size of S。

We're going to be calling each entry of the array of buckets。

 so there's n buckets and then the size of S is about 50% of the number of buckets， let's say。

So one objection you might legitimately raise at this point is you I thought I said the set was dynamic。

 the set S stuff can be added， stuff can be deleted， so the size isn't always the same。

 it can fluctuate over time。 So what does it mean to define an array which is roughly the same length of this changing set So for simplicity for the purposes of this video to focus on the key points I'm going to assume that the set size S while S itself can be changing I'm going to assume that the size of S doesn't fluctuate too much So there are additional bills and whistles you can add to a hash table implementation and they're all quite natural。

 I think most of you could probably figure them out on your own to deal with the fact that S might be changing sizes So for example you can just keep track of how many elements are in your hash table and when it exceeds a a certain threshold So when it's too big relative to the size of your array you just double the array and then you reinsert all of the elements into this new double array Similarlyly if you want to if the set shrinks you can have tricks for shrinking the array dynamically as well So I'm not going to discuss these bells and whistles for resizing your hash table。

they are of course important for a real implementation and they are part of the implementations in the standard programming libraries。

 but I view those as sort of a second order point in the implementation of a hash table and I want to focus on the first order points in this video so summarizing think of the set S there are insertions and deletions we have to accommodate but S is going to be roughly the same size and the number of buckets will be within a constant factor of the size of the set。

All right， so now we have our array with totally reasonable space space proportional to the size of the set that we're storing。

 and now what we want is we want some way of translating between the things we care about。

 say our friends names or whatever the elements of the universe are to the positions in this array。

 so the object responsible for that translation from keys drawn from this universe to positions in this array is called a hash function。

So formally， a hash function。Takes as input a key， so this is going to be an IP address or the name of somebody or a chesbook configuration or whatever。

 and it's going to spit out a position in this array。

 so I'm going to label the array entries from zero to n minus1 for this lecture。

Obviously at the moment this is super underspecified。

 there's a zillion functions you could choose which one do you use， we'll talk about that。

 but for now there's just going to be some hash function mapping from elements of the universe to buckets to positions in this array。

Now as far as the semantics of this hash function， what the hash function is doing it's telling us in which position we should store a given key from the universe。

 so if we have some new friend named Alice and we run Alice through the key Alice through the hash function and gives us a 17。

 it says we should store Alice's phone number and position 17 of the array if we have some crazy chessboard configuration we feed it into a hash function and it spits out 172 it says we should remember this chessboard configuration in the 172nd bucket of this array。

So again， given X， which is some key from this universe。

 we invoke the hash function to get a position in this array to get a bucket and that is where we try to store this X in any associated data with it。

So that's the high-leve idea of how you implement a hash table。

 but we're quite far from done and in particular there's a serious issue that we're going to have to deal with that's fundamental to implementing hash tables and that's the notion of a collision So probably many of you have already noticed that this problem might occur which is what happens if we're storing our friends' phone numbers and Alice shows up and we ask our hash function where to store Alice's phone number and it says bucket number 17 and then our friend Bob shows up and we ask our hash function where to store Bob's phone number and what if the hash function also says bucket number 17 for Bob what do we put in bucket 17 do we put Alice there do we put Bob there do we put them both there。

 how do we deal with these so-called collisions So the next quiz is meant to gets you thinking about collisions and in some sense how unavoidable they truly are。

All right， so the correct answer to this question is the first answer。

 believe it or not all you need is 23 people in a room before you're equally likely to have two people with the same birthday as not。

 so if you're looking to skim a little money off of your non-mathematical friends。

 this is one way you can do it， go to cocktail parties with about 40 people and place bets with people that there are two people in the room with the same birthday。

So if you have 367 people， well there's only 366 distinct birthdays。

 I'm counting February 29th here as one of them， so by the pigeonhole principle。

 certainly the probability is 100% by the time you get to 367 Now by the time you're at 57。

 you're already at 99%。So you already have overwhelming probability to have a duplicate birthday with 57 people。

 so of course with 184 you're going to be almost at 100%， 99。99。

 who knows some large number of nines and a 23 year at 50%。

So many people find this quite counterintuitive that you only need 23 people to get a duplicate birthday on average。

 so this is a quite famous example and it sometimes goes by the birthday paradox。

Collling it a paradox is sort of a misnomer， paradox often suggests some kind of logical inconsistency。

 there's no logical inconsistency here it's just that people's brains are not really wired to have this intuition for whatever reason。

 but it's really just math， you can work out the math and you can just solve it。

So more generally the principle behind the birthday paradox is the following。

 so suppose you have a calendar perhaps on some different planet which has K days where everybody's equally likely to have each of the K days as their birthday then it's about the square root of K people that you need in a room before you're equally likely to have a duplicate or not have a duplicate and the reason that you get the square root effect is because if you think about it there's a quadratic number of pairs of people in the room。

 so that's a quadratic in the number of people opportunities to have a duplicate so each pair of people could be a duplicate。

 there's a quadratic number of pairs and so that's why once the number of pairs starts reaching about the number of different days you're going to likely see a duplicate around that point。

So you might be wondering why I'm telling you about the birthday paradox in the middle of the lecture about hashing。

 but really really it's quite relevant。 So imagine。

 for example you defined a hash function in the following way Now to be clear this is not a practical hash function。

 but just for the purposes of discussion imagine you have a hash function which randomly assigned every single key to a uniform bucket so for each of the one over end buckets equally likely then with the birthday paradox says is even for a very small data set you're already going have a pair of things colliding so if you have end buckets so maybe n is like 10。

000 all you need is roughly 100 elements in your data set and despite the fact that the table is only gonna to be 1% full。

 you're already going to see a collision so 99% of them are empty but you're gonna to have one bucket that has two that's sort of annoying So the birthday paradox says you start getting collisions with a hash function even with really tiny data sets So in this sense if you're going to have hash tables。

 you got to you got to deal with collisions there's going to be a fair number of them and you need some method for resolving them。



![](img/66c5cce31ab10350461037c3864c01a1_3.png)

So collisions are a fact of life when you're talking about hashing。Where again， by collision。

 what I mean is two different keys， so two different elements X and Y from the universe that hash to the same bucket who have the same hash value。

 So in general we can think of a hash function as doing a compression of sorts so we have a huge universe U and we have this very modest size array A with only n buckets or N we're thinking of as being much。

 much much smaller than U So of course this hash function has to map various elements of U to the same bucket。

So what are we going to do about it， how are we going to resolve these collisions Well there's two different solutions which are both quite prevalent in practice so solution number one is called chaining or sometimes you'll also see it called separate chaining。

And this is a very natural solution， it's also the one that's relatively easy to analyze mathematically。

What you do is just for elements that hash to the same bucket。

 you just revert to the list based solution that we talked about in a previous slide。

So each of the end buckets will not necessarily contain just merely zero or one elements it will contain a list with an imp principle unbounded number of elements。

Okay， so when we use chaining， it's then quite straightforward to figure out how to implement all of the hash table operations。

 namely insert， delete and lookup， you just hash something to the appropriate bucket。

 and then you just do insert， delete or lookup as appropriate in the list that's in that bucket。

So just to make clear that everything is type checking， so here H of x。This is the bucket for x。

That's what's specified by the hash function， and then in the H of x position of this array A in the H of x bucket is where we find the linked list that is going to contain X。

So just to give a cartoon example， if you had， say four buckets。

 maybe you know the first bucket has exactly one record。Corresponding to Alice。

 maybe the second bucket just has a no pointer， no one's been inserted in the second bucket and then the third bucket we have。

 let's say， both。

![](img/66c5cce31ab10350461037c3864c01a1_5.png)

Bob。As well as Daniel。And then maybe in the fourth bucket， we have Carol。Okay。

 so because we have a collision between Bob and Daniel both map to the third bucket。

 and we resolved that just by having a linked list with Bob and Daniel in some order。

So the second solution， which is trickier to talk about mathematically。

 but still quite important practically， is called open addressing and the principle in open addressing is you're not going to use any space for pointage you're not going to have lists。

 so you're only going to have one object per bucket of the array。

So now the question is what happens if you you try and insert Daniel and you go you invoke the hash function on Daniel and it takes you to a bucket that already contains its Bob。

 that means there's no room for Daniel， so what you're going to do is you're going to probe the hash table in some other position so a hash function is now going to be replaced by a hash sequence where you try the hash function tells you the first bucket to try to insert Daniel failing that a second bucket in which to try to insert Daniel failing that a third bucket to try to insert Daniel and so on and you just keep trying until you find an open position somewhere in the array。

So there's various strategies for trying to figure out the probe sequence。

 one strategy is if you fail and say bucket number 17。

 which is where the has function tells you go first。

 you just try bucket number 18 then 19 then 20 and 21 and so on until you find your first open slot。

 so that's called linear probing。And another approach is double hashing。

 So this is a solution where you actually have two hash functions。

 hash function number one and hash function number two。

 And the idea is suppose you're trying to insert， say Daniel into a hash table with open addressing。

 and you evaluate both of the hash functions。 And the first one comes up 17 and the second one comes up 23。

 So as usual， the first hash function will specify where you look first。

 So if it evaluates on Daniel to 17， you look in the 17th position of the red。 And it's empty。

 that's where you insert Daniel。 Now， if it's full。

 What you do is you use the second hash value to be an additive shift。

 So unlike linear probing where after 17， you look at 18 with double hashing。

 if the second hash function gives you 23， that's going to be your offset。 So after 17。

 you look at bucket 40。 if 40 is already full， you look at bucket 63。 bucket 63 is already full。

 then you look at bucket 86。 So you keep adding increments of 23 until you finally find a bucket where that's empty and that's where you insert Daniel。

 Now， of course， if you try to insert some other name if you try to insert Elizabeth。

You're going to get two totally different numbers in general， so maybe you'll get 42 and 27。

 and so here the probe sequence will be 42 failing that 69 failing that 96。

 failing that 123 and so on。So a question you should have at this point is I've told you two solutions to resolving collisions in a hash table and you're probably asking well。

 which one should you use if you have to implement your own hash table and as usual if I present you with two different solutions for the same problem you can probably rest assured that neither one dominates the other otherwise that wouldn't waste your time by presenting both of them to you So sometimes chaining is going to perform better it sometimes open addressing can to perform better and of course it also depends on what kind of metric that you care about So there are a couple rules of thumb that I can tell you so first of all。

 if space is at a real premium you might want to consider open addressing instead of chaining and that's because with chaining。

 you do have this excess know it's not huge but you have a little bit of space overhead in dealing with all these pointers in these linked lists if you want to avoid that you might want to think about open addressing the second rule of thumb is deletion is trickier with open addressing than with chaining deletion is clearly not difficult at all either tocode or to understand when you use chaining because it just reduces the deletion from a linked list which of course you all know how to do open。

Addressing is it's not possible to implement deletion。

 but it's much trickier so if deletion is a crucial operation for you that might skew you toward thinking about chaining。

 but ultimately if it's really kind of mission critical code。

 probably the best thing to do is implement both kinds of solutions and just see which one works better It's a little hard to predict how they're going to interact with memory hierarchies and that kind of thing they're both useful in their own contexts。

All rightSo we've covered the two most prevalent ways of handling collisions and we argue that collisions are inevitable。

 no matter how you is on your hash function， you're stuck with collisions and you can do chaining a link list per bucket or you can do open addressing where you actually have a probe sequence in order in which you look at buckets until you find an empty one。

And the elephant in the room at this point is you know what is this hash function。

 I told you nothing about hash functions， All I told you is that there's some mapping from the set of universe so IP addresses or names or whatever to a bucket number what kind of function should you use。

Excellent question， tons of research on that question， and to this day as much art as science。

 but let's start talking about it。