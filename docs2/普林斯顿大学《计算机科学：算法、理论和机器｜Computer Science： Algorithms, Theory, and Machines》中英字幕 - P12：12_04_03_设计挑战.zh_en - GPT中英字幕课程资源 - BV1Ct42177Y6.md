# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P12：12_04_03_设计挑战.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/c05b59d98dedb7c2b25f8677d3715a7f_0.png)

Just as in the last lecture， we want to make the point that performance matters in these implementations。

 all sorts of the applications we've considered involve huge， huge numbers of key value pairs。

 and so we want to start by specing a performance。Of requirement。So just as an example。

 let's look at a benchmark application， linguistic analysis。

 there's a thing called zip's law for natural language for a corpus or a huge text in a natural language。

And this is a theory that if the most frequent word occurs about t times in that text。

 then the second most frequent occurs about t over two and the third about T over3 and so forth。

Not so linguists are interested in testing that law in real natural language text。

 so that's the goal we want to validate that law well we can use our frequency analysis program that we just considered as a symbol table client。

 but in order for that to complete for a huge text， we need an efficient symbol table implementation。

So for example， here's the result of running this for Moby Dick。

 which has about a million words and so if we have an efficient implementation but that one's going to be difficult to do unless you have a good symbol table implementation and actually nowadays people study much this is a validation of zip's law for Moby Dick。

 it's not too far off， you can see the observation versus the hypothesis and it's pretty close。

People actually study this for huge texts nowadays， so there's a thing called， for example。

 the Works corpus from the Lepszig Project， and that one might have 20 million words。

 maybe half a million of them distinct。So and even nowadays。

 if you look at texts on the web or big sets of texts on the webs， you might even have billions。

So you're not going to be able to study these without an efficient symbol table implementation。

So let's think about the data structures that we've considered so far。 let's see where we are。

 So one idea might be， let's keep the keys in order in an array， keep the values in a parallel array。

 So if we have the index of the key， we have the index of the value。

And use it like we did in the sorting and searching lecture。

 we have the fast sort merge sort and we have to remember whenever we move a key we have to move the associated value and we get fast search with binary search but there's one problem is how big do we make the array so we talked about that in the sorting and searching lecture。

 but there's really a fatal flaw in this even if you address that one is that how do you insert a new key。

If you want to keep the key array in order when you get a new string。

 then you have to move the larger entries over one or down one in the same way as with this insertion sort。

And that's too slow and you can easily see that in our benchmark it's going to take quadratic time every time you get a new key quadratic in the number of distinct keys because every time you get a new one on average you're going to have to move about half down and you can run experiments to validate that but we're not going to take the time to do that right now it's clear from the model。

So what about link lists would that work， so maybe the idea is to keep the keys in order in a linked list and add a value field for each node and so that's going to be good because same way as for text and cues it meets the memory use performance spec。

But that one's got a fatal flaw in is that how do you do the search with binary search。

 we needed that indexed access into the array， need to be able to quickly get to the middle。

 how do you get to the middle of a linked list really the only thing you can do is search sequentially through the list to get to the middle or to search for any specific key。

And again， that's going to be too slow for huge amounts of data。

 pretty easy to hypothesize that our benchmarks are going to take quadratic time and it's just not going to work for millions or billions of words。

 and again you can easily validate that with experiments， but we won't take the time to do so。

So our design challenge is to， of course we want our simple， safe， clear and efficient client code。

 and we want that efficiency to mean that the symbol table is scalable。

 that we can keep up with Moore's law with a symbol table。So now we're going to relax it slightly。

 it's really a lot to expect to expect to get constant time running time for these kinds of operations。

 but we'll relax it to say it's got to be at least logarinmic so since the log of a million is 20 the log of a billion is 30。

 it's only a little bit more costly then constant time and that's what we're going to say if you don't have that kind of performance then you don't have a symbol table。

And again， we want the memory usage to be linear in the size of the collection just as for stacks in Q and it's not empty and no limits within the code on the collection side。

 so that's the challenge can we really achieve such guarantees Can we implement associative arrays with just log factor extra costs that seems to be quite a difficult challenge and the naive programmer might say there's no way that you can do that you can search through a billion keys just looking at 30 things and allow arbitrary insertions。

And that's what this lecture is about， yes， we can achieve that guarantee and that's what we're going to look at next。



![](img/c05b59d98dedb7c2b25f8677d3715a7f_2.png)

![](img/c05b59d98dedb7c2b25f8677d3715a7f_3.png)