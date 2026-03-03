# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p25 04_01_06_跨语言比较面向对象编程方法.zh_en -BV1v2421P7pt_p25-

![](img/4fe1bf65ae9c6d864e5e696c8936f887_0.png)

So we're going to take a look at some of these object orient implementations over time。

 I've already talked about the Python inspiration， I flip Python in C++ in the early days because at least Python we kind of know C++。

 it is 1980， Java 8 in 95， JavaScript in 95， PhP。In 2000 and then C Shap in 2001。

So here's the example that I showed you before and talked about it before。

 you have a constructor double underscore in it double underscore with self is the first parameter self do X again。

 the key thing is self is by convention self is not a language construct it just so happens that the first parameter of method calls is to the instance and we almost exclusively use the word self for that that is a。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_2.png)

Very early 1991， implementation of an object oriented syntax on top of a mostly procedural language。

 Now， if we take a look at C plus plus C plus plus was initially implemented as a pre processing past。

 and it sort of did sort of one for one textual transformations。

 And so class was not a keyword in the C language public。That's not a keyword in the C language。

 There was syntactic transformation that kind of transformed it into C and then run it through the C compiler。

And so we say， I mean， and this is pretty elegant and you can absolutely see how Python was inspired by C plus plus。

 so class point open curly brace， double x and Y are the attributes and the constructor by convention is the exact。

 it's a function that has no type， the constructor is the exact same name as the class。

 so in this case I've got point with an uppercase P， and then the constructor parameters。Come in。

 Now， the interesting thing is， as you have to declare as double x and y as the attribute variables。

 And then within the function， you can think of the double x Y as almost like x turn scope means they're global across all functions。

 So you have this weird thing where you can't have a parameter like you could in Python。

You can't have a parameter of the same name as an instance variable。

 or you'll be confused and so you'll notice I called the Xc and YC as many parameter variables so that I know that those are parameters in a constructor and so I can copy Xc into X and YC into Y。

And it also means if you look at the dump code， you see like you don't have to say self dot x。

 you don't you just say x and y because x and y are doubles their instance y X variables as it were。

 and the same is true in the origin function that's returning the square root of x squared plus y squared。

 you don't have to have self or this or anything else So if we take a look at the main program on that first line point PT openPn 4。

0 comma 5。0 we are both allocating a point instance and calling the constructor and setting it up。

 then we use the dot syntax PT。 dump openpren close printn semicolon to dump it out and then we can call PT。

 origin and then that will return us a double。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_4.png)

And so you'll see this sort of dot syntax that is become pretty common in every language that comes afterwards。

So let's take a look at Java now recall that Java was inspired both by CNC++ and really wanted to be like the super language。

And you see that it looks a lot like C++， but it does introduce the concept of this so that it scopes the external variables that are the instance variables。

 you access an instance variable by saying this dot x and this dot y rather than just x and y。

 and I think it's actually more elegant this way。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_6.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_7.png)

So we say public class point， and then double x comma Y， which are the instance variables。

 and then the constructor is using the c plus plus convention of point with no type double x and double Y are the two parameters。

 this dot x equals x and this dot y equals y close close curly breaks Now I like this better because the this using this does not keeps me from having to make weird function parameter variable names。

 I can make them what I want to be， and this is the way using this is the way that we contextualize that。

 so if we look at the dump method。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_9.png)

We see the use of this and this is not just by convention， this is a language element。

 so this is the pointer you'll see you can see from the output。

 it actually prints out the class that it is and some kind of reference like ID like thing and so Java actually if you start printing objects out。

 it tells you what its type and what instance it is， it's not necessarily an address。

 but it probably is related to the address somehow。

 but then we print out this dot X and this do y and then if we look at the double origin method we see it's this dot x times this dot x plus this dot y times this dot y so you see the sort of use of this throughout。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_11.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_12.png)

And then if we look at the main program， we see point PT equals new point 4。0， comma 5。0。

This is where we see the use of this new operator where you're saying， look。

 call the constructor and I like this。 I like the sense that you're calling the constructor on purpose。

 you're not calling it implicitly and then you end up with PT as the instance of this object。

 and so for me， this feels pretty good。 PT do dump is a good example of calling a method within the instance and PT do origin is similar。

 If we take a look at JavaScriptscript and recall that JavaScriptscript is the weird one。

 JavaScriptscript did not take its inspiration from C++ C++ is syntax。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_14.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_15.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_16.png)

Was kind of。Influenced by the fact that it was initially a preprocessor to the language C。

And some computer scientists would think that that's a rather impure way to think about object orientation。

And so the JavaScript， when it was created， the idea was is to be more pure in object orientation。

 and so the concept of first class functions， there is because it has first class functions。

 there is no class keyword the class keyword was really useful。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_18.png)

When it was a preprocessor。The thing that JavaScript does take is the concept of this。Now。

 the interesting thing is if you look at everything on the screen from function point to the closed curly brace。

 this is the constructor。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_20.png)

The constructor constructs everything。 It constructs the attribute variables。

 and it actually constructs all of the methods as well。

 So if we look at the line this dot party equals function open print， close print， open curly brace。

 we are setting in a sense， an attribute variable to source code。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_22.png)

This is an anonymous function。 There's no name to the function。 So most functions are named。

 but this function has no name。 That's a jascript thing。 It's a first class function thing。

 We are basically not running that function with the two lines of this dot x equals this out x plus one and console out log。

 blah， blah， blah Those lines aren't running。 They're being compiled。

 And then there being the code to execute that is being assigned into the。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_24.png)

Attribute variable party。So it doesn't run it， it reads it and stores it in party。

 you can literally later print out this dot party and you will see the source code to that function。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_26.png)

And the same is true for this。 dumb。It's an assignment statement and then similarly this dot origin and you see within those methods。

 you see this dot x and this doy， which is taken directly from job。

 we also see the concept of new in PT equals new 0。4。05。0 we're explicit， I like this。

 I like the idea of saying please call the constructor from the point class and pass these two variables in。

 and then we see the c plus plus inspired syntax of PT。

dump to call a method in the PT instance and PT。orig to call a method in instance。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_28.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_29.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_30.png)

If we look at PhP， now the key to PhP was as PhP is a procedural language。When it was created in '94。

 and then it became an object orient language in PhHP4 and then5。

 it was late to the party so it could be inspired by everything by JavaScript， by Java， by C++， by S。

 by scheme， all of those things， and so the PhP object orientation is kind of pretty as a result of that。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_32.png)

Now one of the things that happens in PHP is it's got some weird language syntax things in that variables have to start with a dollar sign。

 thank you Pearl for that。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_34.png)

And the dot operator is used for concatenation in PhP。

 so we couldn't use the dot operator to look up instance variable or a method inside of an instance PhHP borrowed the C arrow operator。

 which is minus sign gradevan Now， the interesting thing is is if you go back to pointers。

 the arrow operator is what you do when you have a pointer to a structure。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_36.png)

And so in some ways， that is a throwback to see in a beautiful way。

 because I think kind of under the covers and as we shall see。

When we are starting to implement object orientation and see ourselves。

 we're going to see that pretty much we get pointers to an instance is a pointer to something rather than a thing。

 And so we see this， this arrow X equals dollar X and the constructor。

 We see the constructor is a double underscore construct So that PhP kind of use the single underscore and double underscore as sort of metadata about the meaning of things and double underscore or things are're not supposed to call They're supposed to be private。

 And then we have a function dump。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_38.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_39.png)

And you see the concepts of this inside of dump and origin。 you see this in the main code。

 you see Do P equals new 。4050 Well， it's following the new from Java and others。

 And then we call P arrow dump dump and then P arrow origin。

 It pretty much works like most of the other ones except that you'd never use dot because dot is concatenation in PhP。

 And I'll be honest， I love dot for concatenation， except for the fact that Pp is different than every other language that I use Every other language uses plus for concatenation of strings。

 Now C sharpp is 2001。 So C sharpp was inspired kind of by everything。

 And so you see that C sharpp is。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_41.png)

Clearly a very C plus plus oriented， but with some Javavaness to it。

 So you see the double xy in the class， which is the two instance variables。

 you also see that not there's no use of this and so you see that we have to name the parameters differently because x and y are in effect global across the entire class。

 and then we have void dump and then we see that it's just using x and y no need to use this。

 it's tough for me to decide which of these two ways I like better。

 I guess that this is this feels more explicit to me So I like Java and jascript in that respect self I like self also if we look at the origin function。

 we see x star x plus y star y and so we don't need to use this we again see a very Javaoriented point P equals new point openpre 4。

0 comma 5。0 point dot dump or using the dot。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_43.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_44.png)

![](img/4fe1bf65ae9c6d864e5e696c8936f887_45.png)

🎼To look at instance variables and methods within the within the class and end point do origin。

 So now that we've looked at sort of a survey of the different kinds of object oriented languages that are that are today and we can sort of see how they derived ideas from one another Now we're going to actually try to build an object in a non objectject oriented language so we're going to build like a Python object。



![](img/4fe1bf65ae9c6d864e5e696c8936f887_47.png)

🎼InC。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_49.png)

🎼Yeah。

![](img/4fe1bf65ae9c6d864e5e696c8936f887_51.png)

🎼。