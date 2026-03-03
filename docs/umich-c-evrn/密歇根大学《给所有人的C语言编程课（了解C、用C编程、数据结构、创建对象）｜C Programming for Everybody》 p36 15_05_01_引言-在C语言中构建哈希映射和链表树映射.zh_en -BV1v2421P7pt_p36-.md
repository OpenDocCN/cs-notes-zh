# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p36 15_05_01_引言-在C语言中构建哈希映射和链表树映射.zh_en -BV1v2421P7pt_p36-

![](img/3f6e7ed494b3308192134bb97fd32512_0.png)

Hello and welcome to the last lecture in this course。

We're going to talk about tree maps and hash maps up till now we've built a map abstraction。

 we've looked at how iterators work。 we've created a linked list implementation of the hash abstraction。

 and now we're going to go and build a hash version and a tree version of that same thing。

 If you recall some lectures ago， I read a Robert Frost poem。You know， miles to go before I sleep。

 Well， that's where we're at now。 We're coming to the end of this miles to go。

 although as you'll see， the end is really just the beginning of the next phase。

 And with a little foreshadowing。

![](img/3f6e7ed494b3308192134bb97fd32512_2.png)

If you have been with me for a very long time。All the way since Python for everybody。

 which for me was recorded a number of years ago already。

This is the first complete piece of code that I showed you。

 and that was the code to count the number of words in a file by splitting them。

And then creating a dictionary and then counting them。

 and we're going to finish this lecture by implementing this in C， but I'm getting ahead of myself。



![](img/3f6e7ed494b3308192134bb97fd32512_4.png)

So the idea here is we're exploring different key value implementation alternatives where we built a unordered Java space hash map。

 which is like a Python 2 dictionary， if you recall。

Python 2 had unordered hash maps which meant you sort of ended up with your stuff coming out in a random order。

 it was the same order， but every time you inserted something the Earth order might change Now Python 3 they tend to later versions of Python 3。

 they tend to be ordered， which are more like the list map that we did。

We're going to have a map that is sorted that's more like Java's T map。With an iterator。

 and it is sort of chapter 6。5 or section 6。5 of the book。

And it is a combination of a tree map and a linked list map， but Java doesn't have such a thing。

 which really kind of surprises me they got a tree map and they got a hash map。

 but they don't have a linked tree map or a linked map。So。

Here we go now these these the two abstractions were I mean two implementations we're going to build kind of you see them in Python。

 you see them in C plus plus and you pretty much see them in。A job it as well。

 but we're going to do our own thing。So I would say。To you when you're writing this code。嗯。

I don't want you to think that when I wrote this code that I gave you as samples or when I wrote these slides。

 that it was easy for me。嗯。The concept of trees and hashes are pretty straightforward。

 but then you got to solve the little problems of how to take the previous and hook it to the current and hook the next to the next the current next to the next from the previousview。

And so you got to draw pictures and this is actual picture that I drew。

 I really wrote all this code from scratch， I mean I didn't come up with the idea of a tree from scratch。

 but I wrote this code from scratch and you can see that like when I was building the tree map。嗯。

My goal was to find the right place in the tree to insert the next item and so you see I've got this  one3。

57，9，1113 so I kind of constructed this tree that was right it was in order and then I was trying to figure out where I might put four and where I might put8 and where I might put 14 and then。

I kind of had this notion when I was writing the picture that you'll see I had the words lowest node greater than and then cross them all out because that wasn't enough and you'll see when we get there that I have the lowest node greater than and the greatest node less than and I've got to get both of those things and so as we work our way down the tree we got to keep track of this I'm getting way ahead of myself。

Like many data structure。Programming tasks， they if you can draw the picture and it makes a lot of sense。

 you see the hashm， which is the first one we're going to do。

 that's really just nothing more than a bunch of link lists with a hash function picking the head or instead of one head it has in this case four heads。

嗯。So that one turns out to be easy and it's the first one that we're going to do。

But when I wrote this， I mean， I knew what I was doing， I knew what a tree was。

 I knew what a hash was that that's the easy part。 The hard part's write in the code。

 Now taking the code from someone else， like if you're taking it from Python or C++ or Java that's easy。

 Thank heaven they wrote it and they tested it and we have nice tested working implementations。

 so you shouldn't have to write this stuff in most languages。

 and so we're just understanding how to write it， but。If you do it right。

You're going to make mistakes and you're going you're going to be 80% right。

 but then it's going to be real hearted to bug this stuff。

 So part of what you need to figure you need to accept the fact that you will you're not likely。

To write it perfect the first time。And debugging is difficult。

You're going to print out a bunch of like percent P's and hex values and stuff。

And you're going to just go through it slowly like， what did I do wrong？

Because the main programs for the programming assignments that I give you are really kind of like unit tests。

 they're sort of pushing your implementation to see if it's capable of handling all of the common situations。



![](img/3f6e7ed494b3308192134bb97fd32512_6.png)

And so don't。Don't stress if it doesn't work right away， my implementations didn't work right away。

 they failed。You know， if you can go to some website and get the solution， I mean。

 if you're going to do that just。Go to Python and make a dictionary if that's your goal。

 your goal is to struggle with。Doing something that you understand， you know how to do it。

 you know what a tree is， you kind of know that you've got ps and necks and lefts and right。

But you still got to write the code in making one or two mistakes and then fixing those one or two mistakes is essential to understanding。

So with that up next， we're going to talk about the hashman。



![](img/3f6e7ed494b3308192134bb97fd32512_8.png)

![](img/3f6e7ed494b3308192134bb97fd32512_9.png)

🎼Yeah。