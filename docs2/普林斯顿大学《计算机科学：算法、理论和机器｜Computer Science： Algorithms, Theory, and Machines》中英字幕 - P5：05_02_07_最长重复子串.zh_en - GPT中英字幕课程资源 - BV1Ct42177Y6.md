# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P5：05_02_07_最长重复子串.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

We're going to finish by looking at an application of sorting。

 solving a more difficult algorithmic problem to illustrate how sorting can play a role in so many important applications。

So the idea is you've got a string， it might be a very， very long string。

 millions or billion of characters， and what you want to do is find the longest substr in that string that appears at least twice。

 it's the longest repeated substr problem。And one motivation for this is from genomics where we have a long string taking from the ACGT alphabet。

 so in that case there's a substring of length five that appears twice in that string and that's the longest one。

So maybe you saw that one here's another one， you can see that this can be a challenging problem to even for human to solve and even for computers it's a challenge in this case they overlap and maybe we want to not allow overlaps but will allow it so there's two examples of finding the longest substr that appears at least twice。

Here's the first 100 digits of pi， or there long repeats in that。

In this case not too many the longest repeat in the first 100 digits of tie is just three so those are some examples to illustrate this problem here's another example people study music to understand the repetitive structure and perhaps compare different musical compositions so this one's there's an arc connecting parts that repeat this is Mary had a little lamb。

 if you hone that to yourself you can recognize these for repetitive structure。

Here's another one that's much more intricate and maybe if you study that for a while。

's pretty interesting the way that it builds， there's the big arc across。

 but the long ones in the middle are kind of build up quite interesting。

 that one's fair Lisa and so you can understand how this idea of things repeating is important in lots of context。

But really， the reason that people look for repeated sequences in the real world is that it has something to do with causality。

 it means there's maybe something there。So for example。

 is there a difference between the digits of pi and random digits that's kind of an interesting philosophical question you know we know it's not rational it incidentcendal。

 but is that the same as random the answer is no but we can't tell the difference any tests that people have performed or the digits of pi would pass the test of randomness。

 so for example if you build a mathematical model for the length of the longest repeated sub sequenceequence。

 say it should be about 14 for 10 million digits and that's what it is for pi？

Cryptography longest repeated subsequence is important if you have data that's supposed to be encrypted。

 one thing that crypt analysts do is find the longest repeated subsequence。And why do they do that。

 well sometimes the people doing the encryption make a mistake and repeat certain header information and if you read about cryptography。

 you can learn about famous examples of this， so you find that repeat assuming something about the header information。

 that's one way into break a code。And the other example is DNA， if you've got in that case。

 if you've got a really long repeated thing then people assume it's kind of junk and really we want to look somewhere else for what matters。

呃。And these strings can be really long， so just one chromosome might have millions of nucleotides。

 so we want to be able to have an algorithm that scales for solving this problem for all three of these exam applications。

All right so let's take a look at it so here's a simple warmup called the longest common prefix problem。

 so we have two strings and we want to find the longest substr that appears at the beginning of both of those strings and we'll call that LCP。

And this one's really easy， you just compare character by character until you find a thing that's not equal。

 so here's the code for that， whichever is the shorter string。

 you use that as the termination of U for loop and you just go through if you find a place where they're a character where they're not equal the first time that's the substring you return and if you get through the whole thing then you just return the smaller the two substrings。

So that's the LCP takes two strings as argument and returns a string。

 which is the longest common prefix of the two strings。

 and we'll use that as a helper method in our solution to longest。Common substr。So。

Just building on that， just our first approach to solving the longest repeated substream problem is a brute force method。

 and again often we solve problems with simple methods to make sure that we understand them and also to check on small cases or more sophisticated algorithms。

Or maybe we have small cases that we need to solve in the first place。

So what do we want to do to find the longest repeated sub sequenceequence we take our string that we take as input and we're supposed to return a string which is the longest repeated sub sequenceequence and we pick off the length of the string and N and what we're going to do is for every position in the string。

We're going to compare。For every position later in the string。

 we're going to test whether the substring starting at I and the substring starting at J have a longer common prefix than what we've seen before so we compute the longest common prefix of the substring from I to the end in the substring from J to the end。

And so that's x and again that's easy to compute and then we just check if the length of x is bigger than the length of the longest that we've seen so far and if it is。

 we save x as our longest repeated subsequence， so we're trying all pairs of positions in the string to see the length of the longest common prefix starting at those positions and those are subsequences of the real string。

So a straightforward method， try all possibilities。And that certainly works for our simple example。

I call it LRS brute just to distinguish it from later methods。So。

The analysis of this is that it's going to take about n squared over2。

 it's got nested for loops for INJ， there's going to be about n squared over two calls on the longest common prefix method and that method takes time proportional to the length of the precept so the prefix so it obviously doesn't scale。

 so we can't consider using this method for something that's got millions of characters in it as in the genomics application。

Need a method， the scales。Well， it turns out that there is a very efficient solution that was discovered decades ago that uses sorting。

And here's the idea。It's called suffix sorting， so the idea is that we're going to form what's called suffolix strings。

 which is string the substr that you get by starting at each position。So position zero。

 that's the whole string， position one， it's the string that you get starting at。

 position one in the original string and so forth。So theres strings of length n。

 there's n suffix strings， just starting at the sposition 10。

 it's the five characters at the end of the string， CA GC。So there's andotes in suffk strings。

So that's first step in this solution， and then what we're going to do is sort them。

They're just strings， so we'll go ahead and sort them。

And we'll keep track of the indices that go with them， but the idea is to just sort the strings。

So now we don't have to check all pairs because the ones that have long the prefixes are going to be together in the sort。

 so what we need to do is just look at adjacent entries。So。

And then find the longest common presect among adjacent entries in the sort。

If they're not together in the sort， they're not going to have as long a prefix as the ones that are together in the sort。

 and that's easy to see when you think about it。So in this case it's the ones AC AAG come together in the sort and that's the longest one we can try all pairs we're not going to see。

Every position we try adjacent entries and we're not going to see a longer one than that。

So that's the longest common prefix applied to the suffixes gives us a solution to the longest repeated substream problem。

So let's look at the implementation in Java， so we're going to create an array of strings called suffixes。

 and then for every position in our string， we're going to take the substr from IDDN and put that in as suffixes of I。

Then use mergech sort to sort it。And then same as before。

 except now we just look at adjacent positions， we pull out the longest common prefix。

 put that in string X， check if it's longer than the longest we've seen so far and set it as before。

 find the longest comma prefix among adjacent entries。

 and that's the implementation of longest repeated subsequence。

AndThe thing about this method is again， works in our small case the thing about this method is it's just got n calls on substr to set up the suffix array and it's got n calls on longest common prefix。

 so at least it's got the potential to scale。And we can test that empirically。

 so and here's the empirical analysis that we used in our course for many years， a couple of decades。

So we're talking about genomics， so we'll use ACTG alphabet。

It'll take random strings so we can use our generator。

 this is a generator that generates a million random string。

 one random string with a million characters in it draw from that alphabet which is the type of thing that the biologists need to find longest repeated subsequences and it took just two seconds and if you've got something that fast you might as well multiply by 10 so for 10 million and it take 20 seconds so problem size increases by 10。

 the ratio of the running times is about 10 that's a method that scales or if you prefer do the doubling and see that the ratio is about two and so that's empirical analysis that confirms the hypothesis that the order of growth of the running time this method is about n log n in that time is for the sort and you can use the highly optimized sort like the system sort if you don't want to use our。

Sorry。This is the way that we taught it for many years and so about why am I bringing that up now。

 well that was really important discovery that you could have methods that allowed scientists to scale their study with the size of the input in the 90s in the early 2000s。

 the amount of data was growing as the technology for bioinformatics was improving and this type of algorithm definitely enabled new research and development。

But a few years ago， something else happened in testing this code for this lecture， it crashed。

R out of memory， so what's going on， we had a change in the system that broke a working program and for all we know。

 broke the working programs of scientists and researchers out there trying to understand more about DNA and the genetic code。

What happened？Well as it turns out， there's two alternatives for implementing substrs in Java。

 there's actually several， but I'll talk about these two。

 so let's say we have this string and there's two substrings。

 so the way that it was done in Java up to 2012 was substrs were created by reference to the original string。

So if genome is our original string， then it would be referenced。

 the actual string would be at some address x， and that memory address would be。

Part of the data associated with genome along with the length。

And then the substrs could just be different addresses within that original string。

 so there's no need when you take a substr to copy any characters。

 it's just a matter of saving away those indices which can be computed in constant time and also take constant space just a pointer in a length。

That's the way that Java strings were designed for first couple of decades。

But since 2012 they decided to change the representation to one where when you take a substring。

 it would copy the characters to make a new string now the reason they did this is people would have huge strings like the contents of a web page and they would take only a small substring out of that huge string and hold onto it。

Even though they only needed a small number of characters。

 Java couldn't reclaim the memory for the original huge string because of this organization。

 so it allowed the potential to free up a lot of memory when the original string is no longer needed。

But unfortunately， what we saw is that this requires linear time and space to implement substr。

 and that's why our programs are broke。So this is not too hard to fix what you can do is implement our own constant time operation which imitates the old implementation。

 we have to implement a Comp two method to enable the sort。

 but that's not too big a deal and the details of this are covered in our algorithms course。

 so Alice， for example， is in good shape。And if we do that， then even today。

 we can find longest repeated substrs in huge strings in a very small amount of time。

So lesson is trust the algorithm， this algorithm was around before Java， it'll be around after Java。

 you want to trust the algorithm， not the system。And people are continuing research and development in these kinds of areas。

Just one final note， we're running this longest common prefix。

 it turns out that the running time is going to be quadratic in the length of that longest repeat and in our model we don't have any long repeats。

 but real data actually has long repeats so people have developed more sophisticated algorithms than this one that are guaranteed to run in linear time even faster than sorting。

Just to indicate the care people are taking and the importance of scientifically and analyzing performance of algorithms in the way that we're doing it。



![](img/67acce79efdf0db26893017d52010bd3_1.png)

So the summary is that we have an efficient algorithm to search a sort an array。

 we have an efficient algorithm to sort an array， and we have many。

 many things that are enabled by fast sort and search。

The important idea is the scientific approach to understand the performance of our algorithms by building a mathematical model and validating it with empirical tests。

 very natural in all kinds of areas of science and it's particularly important in computer science。

 we're not just hacking to get a problem solved， we're understanding performance and performance matters。

So Alice has got her IPO going and Bob is rethinking the idea of a hackathon。

 maybe he'll take a few CS courses。So that's our introduction to a second part of our course。



![](img/67acce79efdf0db26893017d52010bd3_3.png)

![](img/67acce79efdf0db26893017d52010bd3_4.png)