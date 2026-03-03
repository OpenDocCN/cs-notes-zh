# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p41 20_06_03_使用链式哈希映射在Python和C语言中统计词频.zh_en -BV1v2421P7pt_p41-

![](img/7d9f74060f2d5183102bee4102cae87e_0.png)

Well， it's been quite a journey。We have。Built in sea。

A whole object oriented pattern reviewed all of object or new programming implemented a number of different。

Python objects in C as a way to understand how C++ works， how Java works， how Python works。

 how they all work under the covers。And so we come to the end of this sort of。

Walk through all these amazing data structures and I hope you've had fun。

But one of the things I like to do at the end is I'd like to go back to the beginning。

 so some of you have been with me from the very beginning。

 Python for everybody may be the first programming class that you ever took。

And I want to now finish by reviewing。The very first program that I ever showed you in Python for everybody。

It is from chapter 1。I love this example， and this is counting the most common word in a file。

So it's in Python， we read a file name， we create a dictionary， we read all the lines， we split it。

I think we don't do conversion to lower case， but then we're going through all the word and words and we're saying we're going to set the counts to counts。

ge word comma0， remember if you when you first saw that zero was the default then we're going to add one and that's the way when we see the first word we sort of bootstrap whatever the word is that we're looking at。

 then we have a max loop。So we're going to iterate with items。

We're going to look for word comm count items， and we're going to do a simple max loop and then when it's all done。

We're going to print out the largest word and count of the number of times that large word was shown。

So's fast forward。

![](img/7d9f74060f2d5183102bee4102cae87e_2.png)

Here we go。Now you by now have built a tree map。Hopefully。

And so now what we're going to do is we are going to use。

Your tree mapap code and we're going to implement this count。

So we're going to have a treem call the constructor for it。

 that's our dictionary we're going to have the treemap entry that we're going to need to use to go through the iterator。

 we're going to have a treemap iterator we're going to create because we don't have strings we're going to create 100 item100 item array name cha array and word and yes it's dangerous we're just not going to be too mean to our code and blow it up but we could and then variables like I and J and count max value and cha max key that's all of our setup stuff。

So。We're going to open the file name using scan F now we're in C， it's not Python anymore。

But you can see this similarity。So then we're going to do an F open of the file using read and again you can see the similarity。

 we're going to do a scan F。Through F scan F with a file pointer and we're going to do a percent S which gives us a word and word there is a pass by reference because it's remember words and array。

 if we don't get an end of file， then we're going to write a four loop to go through word and call2 lower which is in C type。

 H， and then we are going to carefully put a new line at the end of word。

And then we're going to get the current count。We've MapGt。Ask for map， which is like self。

Whered is the key and0 is the default， and then we're going to do a map put。

Into the word position with count plus1。And then we're going to F close it or close the thing and we're going to dump the map。

 Then what we're going to do is write a max loop。Max key equals nu， max value equals negative 1。

It's count， so I guess we can assume that negative one works here because there's only positive integers in our dictionary s tree map。

We're going to ask for an inerator。We're going to create an infinite loop。

We're going to ask for the next item from the iterator if it's now or done。

And if max key is null or the curve value is greater than or equal to max value。

 the one we're looking at is greater than our current max， we， we return。

 we retain max key and max value and when we're done we。

Give back the iterator and we pronounce the max key and the max value。And then we delete the map。

And so that's the miles to go before I sleep。In a long time。But the end is really the beginning。

These are the most basic data structures。 These are the classic data structures。

 These are the data structures from Chapter 6 of Carnegan and Rie。 These are the data structures。For。

40 plus years that people have been learning about。

Once you get good and I hope you have taken the time to get really good at these data structures because what these are is they're like the omelet。

Of cooking。They're easy。It seems like everyone knows how to do them。

But until you know how to do the easy stuff， you can't understand the large， fancy stuff。In a recipe。

 you need foundational notions and you can create something amazing。

If you have done all the work in this course and you've done it well。

 your journey can continue with many great cookbooks。

The one I'm showing you now is what we called CLR。Because of the authors。

 when I did it back in grad school， there was only three authors， not four authors， CLR。

 and this is a thick book， a very thick。🎼And。What you're going to find is this is a very well written book。

🎼And if you know everything in this course， you should be able to open this book up to Wll's algorithm。

And write an implementation of C。F shells operate。Because you know how to。Alllocate things。

 you know how to create structures with pointers in them and you know how to delocate them and if you learn every lesson in this course。

You can start， you can almost open anywhere， alpha beta pruning。

 all kinds of things you can just open it up and go four or five pages。

 look at how they describe the algorithm。

![](img/7d9f74060f2d5183102bee4102cae87e_4.png)

🎼何ゃ不。So I'm not going to teach you every one of the algorithms in this book。What I've taught you。

What an algorithm is。And what the foundational pieces of all algorithms are。🎼Okay。So I wish you luck。

And I encourage you to keep going on your journey， your journey is not ending its beginning。🎼So。



![](img/7d9f74060f2d5183102bee4102cae87e_6.png)

🎼Yeah。Yeah。

![](img/7d9f74060f2d5183102bee4102cae87e_8.png)