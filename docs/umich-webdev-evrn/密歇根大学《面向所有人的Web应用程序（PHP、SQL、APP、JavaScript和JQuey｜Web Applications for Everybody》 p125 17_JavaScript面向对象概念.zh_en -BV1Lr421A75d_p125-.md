# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p125 17_JavaScript面向对象概念.zh_en -BV1Lr421A75d_p125-

![](img/ff11cf479560918397d84ef29e08c04a_0.png)

![](img/ff11cf479560918397d84ef29e08c04a_1.png)

So welcome to object oriented programming in Javascript。

 If you've been taking all my classes at this point。

 you will have learned object or programming in Python。

 you will have learned object orient programming in PhP and now you're gonna to learn object orient programming in JavaScript and actually you'll see that I just sort of borrow the same lecture slides for each of them and then change the code and that's because the underlying notion of object orientation。

 sometimes we have a couple different terminologies for it in different languages。

 but the notion that there's this template which we call a class then within the class we define code which is method or message and data which is attributes。

 and then we take this template， the cookie cutter and then make a cookie and cookie cookie cookie and these cookie。

 the real things not the shape of the thing but the real things are called objects or instances So that is to across all object oriented patterns and so you might as well get that that's why I particularly love teaching object orientation in multiple languages because if you。



![](img/ff11cf479560918397d84ef29e08c04a_3.png)

![](img/ff11cf479560918397d84ef29e08c04a_4.png)

le you're like， oh， yeah， okay， this is just a little different syntax。

 Now what we're going to find is that JavaScript tests its own unique and I think very cool spin on object orientation。

 but the basics are still the same。😊。

![](img/ff11cf479560918397d84ef29e08c04a_6.png)

So just like in all object or concept， the class is this template， it's the characteristics。

 it's a blueprint， you know， dog is this generic thing， traitte shared by all dogs， breed， fur color。

 etc。An instance is when we。Stamp something out。 And so in our little cookie model。

 the cookies are all the instances， and you'll notice that some cookies are decorated one way and some cookies are decorated another way。

 But you can see they all eventually came from that template。

 The other word we use for instance is object。 So class and object or class and instance。



![](img/ff11cf479560918397d84ef29e08c04a_8.png)

IProably instance， I think captures the idea better because he's like。

 you can have more than one instance， you have one class and then you can make more than one instance of that class。

 you can have one class or you can make more than one object from that class。 it's very equivalent。

 but I think instance captures the idea a little bit better。



![](img/ff11cf479560918397d84ef29e08c04a_10.png)

Method again， an object is kind of like a program inside of a program。

 We have some data structures inside the program and we have code in the code sort of manipulates the data structures and solving your problem is a combination of building clever data structures and then clever code that makes use of those data structures to solve the problem and sometimes you put more of the cleverness in the data structures and sometimes you put all the cleverness in the code。

 So there's a balance between how you use data structures and how you use code to achieve things。

 and the same is true in an object。 So program is big and an object is kind of like its own little siloed wall of stuff with code inside of it and data inside of it。



![](img/ff11cf479560918397d84ef29e08c04a_12.png)

And ways that we talk to it and get stuff out of it， ettera， et cetera。

 the term of method is a function that lives inside of a class， I。

e also lives inside objects when we create them。

![](img/ff11cf479560918397d84ef29e08c04a_14.png)

So the object or pattern in JavaScript is a little different。It is like a store and reuse pattern。

And the function in core JavaScript is the same， but it's different。The function keyword。



![](img/ff11cf479560918397d84ef29e08c04a_16.png)

Itself is executable。 and it has a return value。 So when you what what you think of normally is when you say function。

 blah， blah， blah， bla， blah， blah， you make this piece of new thing with a name blah。 And that's it。

But in JavaScriptscript， that actual function statement is an executable statement。

 and so you can say。

![](img/ff11cf479560918397d84ef29e08c04a_18.png)

X equals function。P blah bh bla bla bla bla。 The point is， is this is defining a function。

 If we name this this Y， it defines a function， but it also returns the code of the function so that you can put that in a variable。

 And that's really cool。 That is a very different way of thinking of， simply a function。😊。



![](img/ff11cf479560918397d84ef29e08c04a_20.png)

![](img/ff11cf479560918397d84ef29e08c04a_21.png)

I first programmed in Fortran and we called them subroutines and then we called them functions as well。

 and you say subroutine and then it's naming a thing and storing and retrieve as pure store and reuse。

In jascript， it's store and reuse， but you also get a return value from it。

 And so that's what we use to do object orient programming。

 So this is called in computer science first class functions。

 which means that functions are just more data so code and data are more equivalent and first class function is like。

 well， you can take the code of something and you can sign that code into a variable and you can carry that code around And so this is an essential founding architectural concept in jascript。

 And so it actually profoundly changes how you code in JavaScriptscript。

 And like I said before JavaScriptscript is the wrong language to learn as your first language。

 but it's a great language to learn as your fourth language because it's like， oh wow。

 you can understand this kind of stuff because if I just started taking functions and assigning them to variables you'd be like。



![](img/ff11cf479560918397d84ef29e08c04a_23.png)

![](img/ff11cf479560918397d84ef29e08c04a_24.png)

No， I don't understand。I love Python as the first program。 So up next。

 we're going to like take all these ideas and write some sample code and take a look at how objects work in JavaScript。

😊。

![](img/ff11cf479560918397d84ef29e08c04a_26.png)