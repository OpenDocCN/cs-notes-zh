# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P44：10_模块3 1 1 类和封装.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 3， object Or and Go， topic 1。1， classes and encapsulation。



![](img/861b85257ecf8d0364cd1659a81abb74_1.png)

So classes are part of object Doed programming paradigm。And this class。

 this whole course is about is for intermediate level people。

 right so I'm assuming that people already have exposure to programming。

So it is most likely that you already understand what object going through the program is。

 although I will sort of redefine it right now， make sure we have a common understanding。

And there's always this question， you know， does golang support object oriented programming。

 I'll say yes， it does。 It doesn't have classes exactly， but it has something equivalent。

 It allows most of the same features。So just to say what a class is， though， to start。

 what a traditional class is that you would have seen in many other languages。

Class is basically a collection of data fields and functions that share a well defined responsibility。

 So is data。Data fields and functions put together usually called methods。

 you call the methods when they're in a class。 So data and methods put together。 So as an example。

 say we want a point class right that represents some point in 2D space。

So using a geometry program I'm making， so the data would might be the x coordinate and the y coordinate of the point。

 and that's the data that you would associate with a point。The functions。

 there might be a variety of functions， but maybe I've got distance to origin quadrant returns the quadrant that the points in add X all set add y I'll set set X set y。

 there are a lot of functions that I I could put in here。

 But the point is though that the data and the functions are all related to the same concept。

 Okay there is a point in two dimensional point and these functions are all things that you do to two dimensional points。

 And the data is all the data that's associated with two dimensional points。

 So that's what a class is。 Now， remember， a class is actually a template。

 So the class contains data fields， but not data。 What that means is when you make this point class。

😊，I am telling you， I'm giving a template on how a point should be created。

 I'm saying here's the data that a point should have and here are the functions that should operate on that data。

 but I am not actually providing the data， so a point class is really a template for a point。

 an actual point has to have data has to have an x coordinate and a Y coordinate associated with it so an object is an instantiation of a class。

 an instance of a class。😡，So it contains actual data。 So as an example。

 say in my geometry program that I'm trying to make。

 I have a triangle and this triangle has three points on it，3 coordinates，0，0。

6055 So there are three point objects that I want to create and three and I call these objects now these objects they're made based on the point class template So they have x coordinate and y coordinate just like the template says but they have actual values for those。

 So the00 point will have 0 and0 for the x and five5 points 5 and 5 and so on。

 So for one class you can have many， many objects of that class that instantiate that class that have actual data in them that fill in the data field。

😊，So I just want to make clear the difference between a class and an object encapsulation is another concept that's often is usually associated with object oriented programming。

Actually， you know what I would say is it's associated with the use of abstraction in general。

 but right now we're talking about it in the context of object oriented programming。

And the idea of behind encapslation is that you might want to protect data。

 you might want to hide data from the programmer so when I say the program。

 I mean the programmer who is using your class。 So the person who's defining the class。

 you can't hide anything from that person。 but if there's a programme who' is using your class。

 you might want to hide some data conceal something。

 So you might want to make the data allow the data only to be accessed using the methods that are part of the class。

 So rather than allowing the programmer to just go straight in and modify， like say it's a point。

 just go straight in and modify the X and the y values of the point。



![](img/861b85257ecf8d0364cd1659a81abb74_3.png)

We might instead say， look， if you want to modify it， you have to use this method to modify it。

 The method is provided in the class。 And why would you do this。

 Maybe we don't trust the programmer to keep the data consistent。 That's the main thing。

 Not that we don't trust the programmer， but the programme has a lot of things on his or her mind might make a mistake。

 So we want to relieve the programmer of that burden of dealing with the consistency。

 the internal consistency of the data。 So we just say， look programmer。

 if you use these methods to modify the internal data。 then we， the people who made the class。

 guarantee that the data will stay consistent。 so you as a programmer。

 you don't have to think about that， just use our methods。😡，So that's encapsulation， where you say。

 look， the internal data can't be accessed directly from the outside or at least part of it can't be accessed directly from the outside。

 you basically put up a wall an abstraction barrier， a hard abstraction barrier。

 which are the methods that you use to access the data。So as an example。

 let's say I want say I've got a point and a function that I want to do to this point is to double its distance from the origin right So I want to double its x and double its y。

 So it's twice as far along the line between it between the origin and the point。

 you want to move that point。 You want to scale it to double it right double its distance。

 So you got to double the x and double the y。So option one is to make a method to encapsulate right so you make a method called double distance and it does exactly that function。

That's a safer way。 Another way is say， look， I don't want to make that method。

 I'll just let the programmer directly access the X and y。

 and the programmer can double the X and y when they want to。

 The problem with that is that what if the programmer makes a little mistake and doubles the X but forgets to double the Y or doubles the X and triples a Y or whatever。

Whatever the mistake。If a mistake like that happens。

 then the X and the y values inside the object are now inconsistent with each other so a mistake was allowed to be made where if you force them to use this double disc function that you made and you know you debug it correctly。

 then they can't make such a mistake。Thank you。