# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p44 23_06_03_解读Guido在Python-0.0.9中的字符串和列表类实现.zh_en -BV1v2421P7pt_p44-

![](img/d5e770fed875305deec5c481e737e881_0.png)

So I hope you watch that interview carefully。 One of the things that I do when I edit the interviews that I have with luminaries is that it's not uncommon that the questions that I ask them are not perfect questions。

And then you kind of what I do at that point is I'm like， whoops， my assumptions were incorrect。

And and so one of the things I did in the editing of the interview that you just watched。

 and you'll see it in the interview the next one is that I didn't cut out all of my confusion。

 And that the reason for that is， is that I wanted you to see the moments where I had an assumption that turned out to be wrong。

And then I'm kind of mentally scrambling to ask a good question。 And Im。

 and I'm asking for clarifications。 And so during that video， you can see me learning from Gio。

 The summary of this is that Gio really didn't use the linked list much at all。

 You didn't use the linked list for the list object and didn't use the linked list for the string object and didn't use the list linked list for the dictionary object。

 Surpri， surprise。

![](img/d5e770fed875305deec5c481e737e881_2.png)

I was completely wrong。 The Python 1。0 list and dictionary objects were extendable arrays of pointers and not linked list at all。

 While Gito was an expert in K And R Chapter 6， like most of us were。



![](img/d5e770fed875305deec5c481e737e881_4.png)

His much more recent work was。In ABC and C plus plus and so he really wasn't looking at K& R for his data structure implementation。

 and more importantly， he was looking at ABC for his data structure implementation or more specifically he was looking at ABC and saying I don't like the way ABC did its data structure implementation。

 but he didn't then go back to chapter 6 of Carnegan and Richitchie and say， well。

 I'll just do it this way， which is a guess， I'm a computer scientist and my instinct is like。

Chapter 6 of Carnegie and Ritchie is just the ground truth， why wouldn't you do that？

So I think he started with lists as simple， extendable arrays。

 which makes a lot of sense because you're either linearly looking them up。

 which is not the fastest way or you're looking them up by position like sub 5。

 And why not use array。 So that just， you know， once you talk to him。 And he walks you through it。

 And you're like， oh， yeah， I get it， I get it。But then the other thing is。

 as he didn't even use link lists and dictionaries。 And you can see me as I'm asking that question。

 like incredulously saying like。

![](img/d5e770fed875305deec5c481e737e881_6.png)

Please tell me that use linkednk list in dictionaries and buckets。

 like like all the interview questions for the last 35 years。And the answer is， no。

So he looked at an earlier document， and this was the truth of algorithms for all of us in the 70s。

 And that is Donald Nuth， volumes 1，2， and 3 and。Heres here right here is Donald Nuth Volume 3。

 the one that I scan to get what's in there。Here in。Where are we。

Collission resolution by open Hahing。 So what he was doing was what good computer scientists did of the day。

 And that is read through this kind of a book。

![](img/d5e770fed875305deec5c481e737e881_8.png)

And found inspiration for how to build。A hash map， because he knew we wanted to do hashing。 So we we。

 we did hashing in Kainar Chapter 6， and he wanted to do hashing， but he did it a very different way。

 And it has do with the collision resolution and the linear probing。And so， again。

 there were no real link lists in the core data structures。 It turned out that。

And we talk about this a little bit in the video that。

There are performance advantages to not using link lists and the interesting thing is if you look at when Gito is actually building。

嗯。Python， we were all using computers that didn't depend heavily on cached memory architectures。

 meaning that the CPUs that we were using and the memory that we're using had a speed match much better。

 and that's because all of it was in refrigerator size computers。

And things were just slow enough that the CPU was not that much faster than the memory。

But when this CPU became a single chip CPU in sort of in the late 1980s and early 1990s。

 when the floating point， fast floating point even ended up on a single very large， very hot chip。

 the memory could never keep up because what happened inside the chip， which is， know。

 maybe three/ quarters of inch to an inch or more likely more like a half inch。

 that was so fast inside the CPUus that the memory just couldn't keep up。

 And so they put caches inside the CPUs that could keep up with the CPUus。

But link this caused this bouncing， bounce， a bounce， a bounce， a bounce， a bounce。

 bouncing through memory that would that blew the cash。And so if， if you were to。You know。

 try to run a pure linked list based operation with， you know， a 10，000 long list。

It would perform terribly on a 1992-9394 computer。But Quito wrote this thing in 19 like89 and 90。

And so he wasn't like thinking I got to make a cash efficient。Data structure。 He's just like。

 I like as， but they turn out to be really good for cash architectures。 And so to some degree。

 if you were to go back and look at it and say， well， let's go back and add Li list， you'd say no。

 because Link list would have a really bad performance impact。 if we did them， in a sense。

 the way I did them when I was teaching you， Chapter 6 of Knegan and Richie。

 And so that's why it was， you see the delight。 I mean， I'm wrong。 when I'm talking a gio。

 I'm wrong the whole time。😊，But I'm learning。And I'm like， oh。That's so cool。

 so let's do a little bit of a review and this sample code is available to you。

So let's take a look at my reimplementation of a Python 1。0 list， not the Kneygie and Richsy Way。

 but the Gio Way。And what you'll find is you look at this code and I'll get some code walkthroughs and you can look at those later。

 but。If you really spend some time and compare the linked list implementation to the extendable array implementation。

 you'll realize it's simpler。

![](img/d5e770fed875305deec5c481e737e881_10.png)

So。For one thing， we only have one structure。 It's the list。 We have， again。

 how many allocated spaces are in the list， much like the string that we did。

 I did the string pretty close to how Gio did the string。 But the list I got wrong。

 So you have an allocation in length， which is very much like the string that I did。

 And then an array of pointers。Okay so that's what this char star star says。 that's an array。

 The first star is an array。 The second star is an array of what it's a pointers to items。

 and that is an array of pointers to characters。 That's what that's saying。

And so if you look at what we do， we allocate the thing。

 we set the a to0 and I mean a to2 and the length is0 and then we allocate a two item array of pointers。

 we know that length is0 so we know that none of them are used and so that's the data structure in a sense。

 it's already simpler than a linked list and if you append first you got to see if you've got space to append right and if you've got space to append。

 Well that's okay you just allocate the new string。

 you copy the parameter into that string and where the end is and length tells you where the end is you put it in that position then add one to the length and so at the end of the first one you've got a half full length list now with a zerowith item pointing at the character array that you just say and then if you put the second one in you do the same thing and we don't have to do anything right now because the length is two in the aoc is 2 we've got a completely full array。

Our list has two items in it。But then the next time you come in。

 self length is greater than or equal to self ac。 So we're just going to extend it。

 So I just added two entries for simplicity。And then I do a realalic。

 And what realelic does is for the things that were in it before we reelic。

 they get copied if we get a new pointer back。 Sometimes you get the same pointer back with a little more space allowed at the end。

 Sometimes you get a new pointer。 you can't tell with Rlic。 Comp scientists like myself。

 who were trained on link lists， really tried to avoid Reallic。 And maybe that was a good idea。

 And maybe that was because Reelic。Wasn't such a great implementation。

 And Gio And I talk a little bit about like Realek let Gito down as Python， you know。

 progressed and became more and more significant。 So he tended to start doing his own memory management and not depending on Riallic。

 which is a combination of the C run time and potentially the operating system。

 But the key to realalik， is if you've got two items in there。 You might get a new pointer back。

 And that's why I've got to reassign it。A new pointer back， but it'll copy the ones that are there。

 But you're responsible for setting up the ones that are new now， for us。

 because length is all we need。 We don't even have to set like 2 and 3 to 0。

 We don't have to do that。So we just now have four spaces and we save the mallik。

 we mallik it again and we copy the saved thing in and we put it in at the end。

 now we have space and then we add one to the length。

 and I have some code walkthrough that goes into this warrant way in more detail。

 but let's just take a quick look at the shapes of these two approaches right And again。

 I just assumed link lists， but I'll tell you that I apologize to you。 I'm like， well。

 some of these four loops and link lists are not the greatest thing blah bh， blah， blah， blah blah。

 right？

![](img/d5e770fed875305deec5c481e737e881_12.png)

And if you just look， you can kind of see how the Python in the lower right that just has an array of pointers is simpler。

Then the linked list on the left。And again， we computer scientists。

Have always liked taken pride in the fact that we understand linkless。

But that doesn't mean that just'ca it's something we know how to use that it's the right thing in all situations。

 and Gito chose to go elsewhere。 And then if we look at the code in the upper left。

 we're dynamically extending the pointers。 There was no reallocation in my K R list of pen because I didn't need to because it would always ac a new node。

 So there's two Malex in here。 In the Knegen and Richitchy one。

 you Malik the node and then you Mal the string。

![](img/d5e770fed875305deec5c481e737e881_14.png)

Whereas in the in the gieto1， you just mall the string。 and every once in a while。

 you relic the items。 The part of linked list that always gets me。

 And I just have to draw a picture every time I do it。

 I that part in the middle of the K R list underscore a pen。 And that's if self head equals null。

 self head equals new。 If self tail not equal null， self tail next equals new。

 And then self tail equals new。 I get it every time， right。

 But those don't roll off the tongue nearly as easily as saying self items self length equals saved self length plus plus。



![](img/d5e770fed875305deec5c481e737e881_16.png)

🎼For all of the years since 1972， we just used Liless almost in some ways as a badge of honour。

 And Gito felt no real urge。🎼To do that。 and inadvertently。

🎼His approach to extendable arrays is great for caching。

 and it's great for fast lookup because you can never look up a linked list by sub27。

 Whereas if you do a gito's way， sub27 is a very cheap operation。😊，So up next。

 we're going to dive into what Gio did as he implemented the Python 1。0 dictionary。



![](img/d5e770fed875305deec5c481e737e881_18.png)

🎼Yeah。

![](img/d5e770fed875305deec5c481e737e881_20.png)

Yeah。