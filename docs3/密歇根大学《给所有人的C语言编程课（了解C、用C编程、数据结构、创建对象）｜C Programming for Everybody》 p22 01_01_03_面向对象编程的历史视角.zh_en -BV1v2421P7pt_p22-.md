# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p22 01_01_03_面向对象编程的历史视角.zh_en -BV1v2421P7pt_p22-

![](img/20860be69af1e24ebe32e75fe490899d_0.png)

Hello and welcome to object oriented patterns， a historical perspective。

 We're going to cover a number of different things in this lecture。 First。

 we're going to do a bit of a review of object orientation from previous courses that I're going to take a look at historical perspective across across time and a bunch of different programming languages。

😊，Important important part about that is that object orientation is a concept。

 It's not just a syntax。 And so by looking at different syntaxes。

 will'll have a better understanding of the underlying concept。

Then what we're going to do is we'll look at how one might have used C to build object orin support into a language like say Python。

 for example， or C++， and then we're going to look at building a Python string class in C。

 a Python list class in C， and then a Python dictionary class in C。

 sort of showing how C is also the foundation of most modern object ored languages。

So if you take a look at the other courses that I've taught， I have been teaching object or。

 have you taken my courses， I have been teaching you object orientation for a long time。

One of the things you'll notice is that。I just keep coming back to it。

 If you look at Python for everybody， Chapter 14 is about object orientation。 I。

 I claim that Django for everybody is really a class in object orientation， because Django itself。

Is a。A collection of cooperating objects， you create Django applications by creating objects that are being sent messages。

 which is very much a purely object oriented concept。I cover object running in JavaScript。

 particularly because JavaScript is a little bit different。

 I cover that in both django for everybody and in web applications for everybody and so。

We're going to take a look at all these different syntaxs of object orientation。

 and then we're going to try to build our own objects。 But in a non- objectject learning language。

 IEC。 I am not going to teach you object orientation in this lecture。 I am going to do a very。

 very brief review。 All my other lectures， mostly what I wanted you to know is terminology。

 So the most important terminology is a class。 A class is not an object。

 It's a template to make objects。 It's like the cookie cutter in the cookie methodology。

 An attribute is some data that you can contain in each instance of the class。

 And a method is some code like a function that operates within the context of the instance of the class。



![](img/20860be69af1e24ebe32e75fe490899d_2.png)

![](img/20860be69af1e24ebe32e75fe490899d_3.png)

The object is a particular instance of the class stamped out from the class when a new instance of the class is requested。

 So you have one class and you have many， many instances。

 So if you do a user defined class in Python。 you see that we have a special keyword class。

 which is different than deaf and within it， we have attributes in we have methods。

 So the methods look like functions， but in particular。

 the methods inside of a class always have this first parameter， which by convention we call self。

 you could call literally anything else， but if you did。

 people would be confused because the convention is so strong that S E L F is always the first parameter of every method inside a Python。

 So in it is the instance and then two parameters。 and then we can look at attributes like self dot X and self dot Y。

 and then assign them in this case to the X and Y from。



![](img/20860be69af1e24ebe32e75fe490899d_5.png)

The call。So we have a couple of methods like def dump and again。

 dump itself is a zero parameter method， but it always has the instance and then we look within it。

 we can say self do x and self do y and look at all the attributes and we can use the ID function which we learned in the last chapter on which is kind of like an address lookup function in Python and so what we have here is we have a little method called origin which takes the distance for our point from the origin to our point and takes the square root of the two sides of the triangle squared。

 So if we then get out of the class definition and move into the actual code。

 we call PT equals 04050 that is how we call the constructor point is the class name and then the parameters to the constructor are4 and5 in that example point dot dump that's the dump method inside a point。

And you can pass the parameter PT， which is the instance。

 so PT ends up being the instance of this point object。

 but the more common syntax is to not use the class name and the method name and explicitly pass self in。

 but instead in the next line we see print origin and then PT dot origin。

 well PT dot origin is expanded to point dot origin and then the first parameters kind of added on。

 which is PT， which is the instance。

![](img/20860be69af1e24ebe32e75fe490899d_7.png)

Now I've got a Dell parenthesesis PT close parenthesesis， and that is the destructor。 Now， Python。

 the deor would get run automatically at the end of the program So in this case。

 that deor is a little bit redundant。 So now I want to take a bit of a historical look at object orientation。



![](img/20860be69af1e24ebe32e75fe490899d_9.png)

So if you've seen any of my other classes， I try to put the programming languages that we're learning in context。

 and these are the common programming languages like Python and PhHP and JavaScript。

And now we're teaching C， and so if you look at this。

 the idea is as you can see that the language C has been the inspiration for virtually all of the modern languages that we use today and that I've taught you Python inspired is while the syntax of Python doesn't look like C。

Python has been inspired， we see things like there's formatted printing that talks directly to the underlying C implementation because C Python。

 not every Python， but the C Python that we normally use is written in C so C。

As we've said many times in this class already is profoundly influential in the syntactical evolution of procedural programming languages。

 So we've seen this before。 but if we think about object orientation。 object orientation。

 the inspiration in evolution of object orientation really took sort of a different path through a bunch of languages that you may or may not have seen or heard。

 So the oldest language on this is Fortn in 1955 and Algll 60， Alg 60。

 I don't have it marked as like that Alg 60 was inspired by Fortn Fortn but probably the better thing to say was that Algll 60 was created in spite of Fortn。

 So Fortn was loved by some and not loved by others and Algal 60 is more what the computer scientists of the day in 1960 decided。

So there's a series of languages that were popular in computer science。

 but not necessarily popular in general purpose programming， like S 67。

 which took a lot of the Ob orient ideas from Al Goal 60。And Pascal， which is a procedural language。

 which is another language that I learned in the '70s when I was going to school。

And if you look for so alcohol and Sim were languages that were mostly procedural but had object oriented concepts in them。

 I always think of the most object orient languages as small talk。

 know it's not necessarily the first one， but it feels like it's the one that developed a notion of object orientation the most。

But it really took inspiration from an earlier language， which was Lisp。

 and so LiISsp was an early early 1960 interpreted language。

 Lisp was often thought of as the foundations of artificial intelligence now scheme in 1975 was a derivative of Lisp inspired by Lisp kind of the next generation of LispP 15 years later。

 and it had a bunch of ob concepts in it as well。And so you can kind of see where。Where they。

Objectoriented notation， the object oriented notions were evolving kind of independently from the preferred syntax。

 And then in the 70s， when C came along， it really changed。The way we think of as syntax。

 and so it inspired C++， inspired Java， JavaScript， C sharpp， and PHP。

But then what happened is each of these things kind of took different inspiration from different object orientation。

 so there's really almost an independent。Inheritance of where the inspiration for the language came from versus where the inspiration for the object oriented pattern。

 and probably the biggest thing that you see is C plus+， which is early 80s。

 took its inspiration both from Sim and from C。 so it was a hybrid language that tried to take the object oriented notations from Sim and layer them on top of the procedural syntax of C。

Now another interesting thing here is that Python in 1991 was quite aware of C++。

 and so if you look at a PhP， which in 1995 was not at all object oriented。

 it wasn't object oriented until 2000。Python was object oriented in sort of almost 1991-92 because the computer scientists of the day were quite aware of these kinds of things。

 and so Python sort of implemented object orientation almost as soon as Python was implemented。

And so like I said， Python 1991 implemented object orientation and I really like the object orientation in Python。

 PhP implemented non object oriented in 95 but then added objects in 2000。

Java took a lot of inspiration from C+ plus Java was trying to be the next C and so it's got a lot from C。

 It's got a lot from C plus plus， And then C sharpp was inspired by C plus+ and Java。

 but then Java is kind of like the outlier。 Javascript even though it came out in 1995 and was very much informed by Java。

 it took its object oriented pattern， more from scheme。

 which is a more pure object orientation rather than an object oriented layer。

 And so JavaScriptscript among all of these things that will look at JavaScript is sort of the outlier in terms of its object and approach。

 And if you taken classes for me in the past。I've mentioned that before because JavaScript has first class functions and the way you create things。

 et cetera， et cetera， et cetera， so we're going to take a look at some of these object orient implementations over time I've already talked about the Python inspiration。

 I flip Python and C++。In the early days， because at least Python we kind of know C++， it is 1980。

 Java in '95， JavaScript in '95， PhP in 2000， and then CSharp in 2001。



![](img/20860be69af1e24ebe32e75fe490899d_11.png)

🎼Yeah。

![](img/20860be69af1e24ebe32e75fe490899d_13.png)

Yeah。

![](img/20860be69af1e24ebe32e75fe490899d_15.png)