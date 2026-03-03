# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p47 26_06_06_Guido-van-Rossum-Python面向对象模式的设计思路.zh_en -BV1v2421P7pt_p47-

![](img/c9d3b024b23798455495d95b458480ca_0.png)

Can you walk us up to the inspirations and the history of。How perhaps ADC got so good。At Po。Ha so。哎哎。

ABC was actually not object oriented。ABC。Had a fixed set of data types。

 that while the data types were composable。Like。You could have say。

A list of integers or a list of strings。And those would share the the operations on lists。

 but sort of。There was no concept of class。 There was no concept of users。Defining classes。

 there was no concept of subclassing。Either in the implementation or for the built in types。

 that was like ABC had a bunch of really convenient to use primitives。Yeah。

 they did a lot work for you。 but they weren't really。 Oh， oh， that's correct。 And， and。

 and they even。

![](img/c9d3b024b23798455495d95b458480ca_2.png)

They insisted that there was only a single numeric type。So in part so that they could， could sort of。

Not deal with the complicated hierarchy of integers and floats and rationals and sort of。

So thenBut when you started fighting you you had like object orientation， very front of mind。

 not just a convenient set of primitives， but a convenient set of object based primitives。

 where did you read that in it or did you read that somewhere else？I was familiar with C++。Okay，Yeah。

 and I think that。Might have been the only object oriented language that I knew at the time。

 at least I can't think of any， well， I own a big book about Simul。

 which is the sort of the granddaddy of all object oriented languages。

 I don't think I ever managed to get my hands on a sim compiler。And I have to admit。

 I also only skimmed the book because it was was actually。Sort of had you written C++ before yes。

 like what kind of how much have you written C++ enough to invent automatic or what I forget what they're called。

 the pointsers that are like automatically ref counted。So yeah， I forget C+ layer。

 there are standard counting on top of C++ so that you would not lose your sanity while working in C++ No because I was very familiar with Ref counts because ABC's implementation is written in C and all。

Everything uses reference counting。And it works out better in ABC because there are no cycles in possible in the data types。

 because there are no mutable。Data type， you can have。

An object that contains itself or references itself directly or indirectly in ABC。

 I don't think that I sort of。Realized all the details of why that is important and I didn't care because pragmatically those things aren't always as important as they seem to be theoretically。

 but anyway。I was very familiar with reference counting and C。So for Howard was used for ABC。

 I think that that's where I learned about it and I didn't。Sort of hear much about it elsewhere。

 Then at some point when I was teaching myself C++。This must have been in the mid 80s。

One of the things I tried was， I mean， my experience with ABC and reference counts in the implementation was that it was very errorprone。

We regularly。Had to sort of deal with bugs in the implementation。Where we either leaked memory or。

Sort of crashed because we had had free things early and it was always like， oh。

 there's a missing inkcraft or that craft。And of course。

 the missing decre is much harder to debug because。

You leak a bit here and you leak ab there and nobody notices because people didn't write large applications in ABC。

So anyway， someone probably put me on the idea of。In C++。

 you can overrite primitive operations to the extent that you can build automatic reference counting。

And I built that。For some toy application。And played with it。And realized。That it didn't work， right。

The problem was that it was like。And I probably didn't know enough C++ at the time or possibly C++ hadn't developed certain subtle mechanisms like move operations。

🤢，It was very crude。Over overloading assignment that was basically what I did。

And so I found that where。If I had handwritten reference count operations， I would sort of。Now， okay。

 this object is owned here， so we pass it to some function。

 that function doesn't have to increment the reference count just because it's using that object because it's not going anywhere as long as the color of that function has a reference to it on the other hand the automatic reference counting as I had implemented it using C++。

Would say， oh， we're passing this thing as an argument to a function。

 So increment the reference count。 Oh， that function returns， decrement the reference count。

 So there was much， much， much more reference counting activity and。😊。

Sot of that part I didn't like and so Python still does it manually and is written in C。

 not in C+ plus but。Somehow I picked up the idea of V tables， or at least as of pointers2 functions。

As a handy way to implement objects， and actually initially for the first probably six months。

 Python was not object oriented。TheAnd so very few people saw that。

 like a handful of my coworkers saw that。And the sort of the implementation had this notion of。

You can implement an object type by putting a bunch of function pointers and a bit of other information in a standard structure that describes the type I called it a type not an object so in a way that youre emulating C++' way of kind of like creating perception of object or programming without truth Yeah oh and wait a second I。



![](img/c9d3b024b23798455495d95b458480ca_4.png)

There is another step that I just missed。诶。So in around 88， I spent a summer as an intern at DexSRC。

And I talked to the designers and inventors of a language named Moular 3。And they were like。

Puuting the last。Proof reading efforts for the modular3 report， but they had built a modular。

Two and a half compiler， they called it modular 2 plus。啊。And in their documentation。

 either the draft of the modular 3 manual or the internal modular 2 plus manual。

I learned this concept of how modular 2 plus and3 do。Kind of not quite object orientation。

 And I think they meant it as。As sort of a reaction to how it was done in C++。

They said modular 3 is not actually an object oriented language。

 but sort of the key part of object oriented use。Where you， you define。

A class through a bunch of functions and the notation。

Where you say object dot method and then the argument instead of function and then。

The object and then the rest of the arguments， they said， if you use that notation。

 object dot or thing do dot method， per n and then arguments。Thing had to be something that。Thats。

Had a type， I think it was a structure type that had a bunch of function pointers in it。

And so the method names were simply。呃。Fields or members of that structure in in modular 3。

 and so to create。The equivalent of a class， you defined a structure。

You defined a structure that had a bunch of function pointers， they were all typed。

 so you could say this is a function that takes one argument of this type and it returns blah， blah。

 and then a bunch of those with names。And the trick was if the compiler sort of noticed that you were using that and then you were calling it。

 it would say， oh， we're going to insert the thing whose method you just used as the very first parameter to the function。

 this is where Python's explicit itself comes from exactly。😡。

And so that is all modular3's design that I copied。



![](img/c9d3b024b23798455495d95b458480ca_6.png)

And so originally in Python， I didn't have a user level notation to even do that。

The type system was only extensible by writing a C extension。And so。The， the author of class keyword。

 what we think class keyword was not there。 That was month and a half。

In the first probably five or six months， it wasn't there， and I think we had an intern。

Whoho knew C++ better or who somehow had the rights Who knows he was younger than me and he said。

 hey。If you。If you want to give users the ability to define their own classes。

 here's a heck how you could do it， you add this little bit of syntax。

And then you map it to this structure of the implementation time and bar line it all works。

 and that's five months in。And， and， and yeah。And so everything else was working。

 we had like a working interpreter with a rapple and integers and floats and strings and tuples and lists and dictionaries and functions。

And types that were， were sort of internal things。I think even even then you could ask for the type of an object。

Did you at the time？In these first six months of python。Did you feel like you were doing。

Core research on what object orientation was going to mean in the future。No， were you just was。

 I was just。Heacking together an implementation of a language that I didn't know where it was going。

I obviously spent enough time on it that。I。I was hoping it would go somewhere。

But you didn think of yourself as like a that you were going to someday like write a paper about like how object orientation should be done。

 you weren't thinking like a researcher with that Def not that We were just solid I was not a researcher。

 I was a programmer。I do not have a PhD。I was employed by CWI as a programmer。

Do you now even think maybe that you made a profound contribution？

You're the first person to tell me that， and I'm not sure that I totally believe it。

I would say that the modular 3 inventors。Sort of made that contribution。

Because they were much more sort of。Reseearing types。Theory types， they。

 they thought long and deep about all the the sort of theoretical and eventual repercussions of designs like that。

 And I， I was happy to implement something。😊，Even。Even if there were edge cases where it would just not do the right thing at all。

Until we finally， after about a decade or so， added a cyclic garbage collector to the language。

Python would leak memory irretrievably in many situations where you had created a cycle。

And then lost the last pointer into the cycle from outside it。

And it took a very long time before our users convinced us that there were some edge cases where that was actually a real problem and there was no good existing solution。

🎼Yeah。🎼Yeah。

![](img/c9d3b024b23798455495d95b458480ca_8.png)