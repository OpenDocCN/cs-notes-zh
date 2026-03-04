# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p71 70_21_optional-closure-idioms-without-closures -BV1bw4m1D7MM_p71-

This segment and the next couple， which are all optional。

 fit together and are about taking some of our closure idioms and porting them to languages that don't actually have closures。

So the idea here is that closures in high order programming programming with functions like map and filter is great and it's particularly easy when your language supports closures because you can very easily create things with private data past them around function types are exactly what we want but if your language doesn't have closures you can still program in this style Now it's often much more painful you often have to create what conceptually is your closure environment manually but by showing you how to do this in languages you might be familiar with we can see some of the connections between different programming styles so one segment is going to do this in an objectoriented style using Java and the key idea there is to have interfaces that just have one method so that's kind of like the function code。

 the call me part of an interface of a closure and then in C where we have function pointers but we don't have closures we can pass the environment explicit。

😊，As an extra argument。So these are optional segments because you need to be a bit of an expert in Java to understand the Java one and a bit of an expert in C to understand the C1。

 even if you do know some Java or C， you may find this a bit over your head that's okay。

 I want to put these segments up so you can refer back to them someday if you're in these languages and you find yourself wanting to program in a functional style。

 then these segments might help you point you in the right direction。

So it shows some connections between the languages and the features。

 it can help you understand what closures and objects are really all about。

 and at the end of the day it is a bit clumsy and so it may make you just wish that more programming languages actually had closures so that we didn't have to simulate them and encode the same idioms in more painful ways。

So this segment just shows the ML code that we're then going to translate。

 which is often called porting to Java orRC， it's just a little list library。

 I am not going to use MLs built in lists because I want to show all the code right and I want to provide a fuller comparison because we're going to write everything ourselves in all three languages and then the next segments are independent you can watch one or the other both or neither and then show how to write the same code in those other languages。



![](img/aabf3798d6aa4ae8384bcbbd84eb0f47_1.png)

So here we are， I'm just going to define my own polymorphic data constructor Al my list。

 two constructors， cons， which has two parts， the head of the list， which is an alpha。

 the tail of the list which is an alpha my list or empty for the empty list is there just plain old constructors so I can write a function map I'm using a cur style here。

 but that's not essential that takes in a function and one of these my lists。

 so not M's built in list but one of these my list if it's empty we return empty if it's non-empty。

 then we cons on F applied to X and mapping F across x's that is map over the my list type。

Filter is similar， it's just the appropriate if then else。

 I to expand this out here so you can see it。Indentted a little more nicely。

 empty list is empty list。 If F of x， then cons x onto filtering F across x's。

 Otherwise ignore x and just filter F across xs。 And finally， length。

 which is easier than any of them。 empty list returns 0。

 Noempty list returns one plus the length of the rest of the list。

Then a couple clients that are using these functions to define their own more specific functions。

 how about something that takes my list of integers and doubles all the elements。

 then we would just use the map function that's no longer quite on the screen but is above。

 remember it took two cur arguments so I'm doing a partial application here。

 I'm just calling it with an anonymous function that takes a number and multiplies it by two。

And then how about another function that just takes a list a my list， of course。

 and an n and returns how many elements of the list RN and so one way I could do this in terms of the functions I've written。

 It's not the most efficient way to compute this， but it does work is the first filter the list so that we only have the elements that are N and then compute its length All right。

 so the result of this called the filter will be a list that has nothing in it bunch a bunch of the number N then over along that number that list is the number of ends are in the original list。

 So we're going to write that code in this style in Java and C in the upcoming segments。



![](img/aabf3798d6aa4ae8384bcbbd84eb0f47_3.png)