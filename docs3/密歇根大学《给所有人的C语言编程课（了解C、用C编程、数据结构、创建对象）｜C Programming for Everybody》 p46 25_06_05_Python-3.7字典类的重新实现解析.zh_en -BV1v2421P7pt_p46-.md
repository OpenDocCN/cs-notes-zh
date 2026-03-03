# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p46 25_06_05_Python-3.7字典类的重新实现解析.zh_en -BV1v2421P7pt_p46-

![](img/a689400ab23fb72a2ae6bf8e08302bc2_0.png)

So now let's talk about what happened between Python 3。6 and Python 3。7， where dictionaries。

Began to maintain insert order， not key order， but insert order。

 So it really what the the basic idea here is is that the hashing is a。

Quick way to find a starting position in an array。 But it doesn't necessarily mean that everything has to be stored in hash list。

 So， so now what happens。 And you you saw this， the code we wrote with trees， The tree map exercises。

 You can have sort of more than one data structure that you're maintaining at the same time。

 And so that's what's happening in Python 3。7。 Now on Python 3。6。

 we made a big fuss about how there was no order。And when you when。

 when you go through the code walkthroughs， you'll see that sometimes the order changes at the moment of rehashing。

 So the order is pseudoor random， as it were， but the order can then change at any moment。

Because of rehashhing and but the pseudo randomness is because of hashing and the it's not even consistent from insert to insert because rehashing and not database hashmap reorganization。

So。Like I said， Python 3。7 separated the notion of the hash index from the key value store。

And so this leads to the fact that iterators that go through Python 3。

7 dictionaries function much more like Python lists， which are iterated in key order。 Now。

 you don't have a sub0 or sub 1， because that。Dictionaries don't want to give you that semantic。

 but it basically is a Python list plus a hash index for quick lookup。

Quick for inserts and gets and iterating through the dictionary is just like the Python 1。

0 list and key insert key look up by key and insert by key is still very quick。 Now。

 I have a whole long walk through that goes through all this。

And I'll just kind of give you the high level picture。



![](img/a689400ab23fb72a2ae6bf8e08302bc2_2.png)

And that will help you when you go through the walkthrough。So if we look at struct P diict。

 it's got an allocation and it's got a length and it's got a struct。Dode that is an array of items。

Okay。But now we have an integer array， this index。 And in the code that I wrote。

 I just made index be twice as big as。The number of items in index was twice as big as the number of items and items。

And that basically meant that I。Alls had space。 And so I end up with a load factor of 0。5。And so。

 if you look at。Items， it's a list， meaning that we insert Z equals。Catchph Z equals W。

 Y equals B and Ss 42， and they maintain insert order， And a new insert is just done at the end。

 So what we're seeing here is a list that's  three/ quarters full。

But we don't care about that in the same way as we did in the Python1 because the load factor of the items is irrelevant。

 It's the load factor of the index that matters。 And because I'm making the index twice as large as items。

 it never reaches a load factor above 50， meaning we reallocate when we need to make the list bigger。

 but then we also make index bigger too。 And so we never exceed a load factor of 50%。

 which makes things really smooth and really easy。Now。

 the key thing is the index is an array of integers。And what's stored in each integer。

 as you can see with these arrows， is simply the index that the key value pair lives in the items。

So again， this is kind of two simultaneous data structures。The index is a hash。Items is a list。

An index points to the offset within the list。 Now， I didn't do it， but Gito could easily have。

They could easily have shared some of the code between。And some of the optimizations between list。

And the items。In aict。So I'm not going to go into it。

 I do have a code walkthrough that takes a good bit of time that goes through all this code。

 just remember this picture， but it's really kind of extracting the hash index into its own table。



![](img/a689400ab23fb72a2ae6bf8e08302bc2_4.png)

So in summary。We learn from Gio， surprisingly。That he loved Rialc an expandable arrays of strs with pointers to his objects。

Liinked list is not hardly used in Python's core data structures， and it turns out to be a really。

 really good choice in retrospect。 The code is surprisingly simple once you start taking a look at it。

 and you're kinda glad I is kind of glad to leave linked this behind。

 even though I'm pretty good at Li list。And moving memory management into Python from Reelic was something that happened like 10 years later that youto mentioned。

嗯。Because the realallic wasn't as predictable as he wanted it to be。

 and eventually there's this concept of garbage collection， which is underneath Riallic。

 and it was too difficult to hope that Realick was going to do the things that Python wanted had done。

So the places in the code that you've looked at here that use Reallic now use a Python allocator and Reallic is what happens is Realliccus gives us bigger chunks of memory and then Python manages those and garbage collects them and cleans them up。

 etc。And so that's， you know that's。The modern era of Python really depended a lot less on the cleverness of Rec because it just turned out to not always be as clever as we thought。

🎼Yeah。But there's more。Y and I didn't stop talking。After we。Talked about the data structure shape。

 the whole surprise linked list thing， I'm like， oh。And so if you recall， I had this picture。

 which was kind of like not just how。Things worked I was placing in this picture， Im placing C。

In the context of all the languages that influence C。

And all the languages that influenced that see influenced。 right。

 And so this is the you've seen this picture before。

But what I wanted to talk to Gio about is I wanted to talk to him about。

What were the influences on Python？See。C++ ABC。And as you will see in the video， Mola。

 I wasn't expecting that。But I was expecting， I don't know what well I do know what I was expecting。

 I was expecting that he didn't like C++ and he love C。

 and Ive forgotten I didn't know as much how how strongly ABC had influenced him。

 so there was in ABC there was much to like and for him much to dislike。

So C plus plus something Gito used it， he wrote code in it， he wrote a series。

 it sounds like a series of experimentation as though like。To some degree。

 I guess maybe his question was， should I is C plus plus so awesome that I can get done what I want to get done in Python and C plus plus And so he he did some C plus+ experiments so that he found somewhat disappointing。

 And so that's why he used C instead of C++ because he had to he could get done what he wanted to get done and and so Gito chose C as a language to build Python。

 but Gito learned a lot about how to。Layer object oriented concepts on top of an otherwise procedural programming language。

 And so C plus plus had a big influence。 And I bet at some point。

 he thought C plus+ was the answer and then said， no， I got to use C。And of course， ABC。

If you look at the Wikipedia entries like ABC influenced Python， and the answer is yes， but。

Inf it more than you might think。And that is that there were things that Guto liked and things that Gieto didn't like about ABC。

 places he wanted to improve。So it had a lot of ABC had a lot of cool types。

ABC handled allocation and Dallocation using reference counting， he'd liked all that stuff。

But it used bee trees internally， and bee trees are not binary trees。

 Bee trees are a thing that's most commonly done on databases。

 The other thing is it it had no mechanism for user to find classes。

 All the concept of object orientation was in the language itself and in the language implementation itself。

 and there was no chance for users to define their own objects in ABC。



![](img/a689400ab23fb72a2ae6bf8e08302bc2_6.png)

And so I mean， ABC did what it did well and Gito knew ABC well and worked on ABC then knew what he wanted to take from ABC and knew what he wanted to build beyond ABC。

I mean， I think that in some ways， the language。ABC is kind of pretty。 I mean， I can read that。

 And you can see things like split and in and other concepts， the forlo。

 the sort of implicit iteration in the for loop for line in document。

 You can see that that just came straight to Python， except he made it all over case。 Of course。

 ABC was kind of cobolt like where it would wanted you wanted how to return words how to return words。

Document his parameter。 That that first line is a little bit tricky， right。

 He also wanted real object orientation， and he wanted to stay much closer to the C libraries because ABC didn't really care about being able to call like。

 see string libraries or C socket libraries or anything like that。 And he wanted lowercase keywords。

 Another thing that surprised me。

![](img/a689400ab23fb72a2ae6bf8e08302bc2_8.png)

Was the fact that Moular 3 was a significant influence。



![](img/a689400ab23fb72a2ae6bf8e08302bc2_10.png)

So module 3。Was a rather European centered language。 It kind of came from Pascal。

 which came from Zurich， Adeha and Zurich。 And so this was the kind of thing where folks like myself in the United States really didn't think too much a modula。

 but。🎼Gido was clearly investigating how to do things。

 And there were some really good ideas in modular 3。 And he went and talked to the folks at Moular 3。

 And the concept of self as the first parameter is a way to layer an object oriented mechanism on top of a procedural language Really。

 the concept of self that was inspired by Gio's interaction with modular 3。

 I'm going to give Gio the last word here。 So I'm going to put the second half of my interview and just let Gio talk about what inspired him as he was designing object orientation in Python。

😊。

![](img/a689400ab23fb72a2ae6bf8e08302bc2_12.png)

🎼Yeah。

![](img/a689400ab23fb72a2ae6bf8e08302bc2_14.png)

Yeah。