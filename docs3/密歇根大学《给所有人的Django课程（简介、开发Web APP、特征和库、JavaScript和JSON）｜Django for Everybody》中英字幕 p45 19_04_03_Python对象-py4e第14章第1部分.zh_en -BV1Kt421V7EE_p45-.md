# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p45 19_04_03_Python对象-py4e第14章第1部分.zh_en -BV1Kt421V7EE_p45-

Hello and welcome to Python objectss， I'm Charles Severance and we're well on our way to get through all this material in the Python。

 so this lecture is in a weird place， I even debated where to put it in the book。

I don't really want to teach you how to write a lot of object running programming。

 but we're going to start using objects。 and I want to be able to use the terminology。

 And so as much as anything， this lecture is about terminology and understanding the words。

 things like methods and methods signatures and variables and inheritance。

 And so think of this as a terminology lecture rather than a learn how to program or learn how to use this。

 It's not something you're going to figure out right away。

 And there'll come a time when you as a programmer really want to start using object running programming。

 It's really a powerful and wonderful technique。 but I think it's too early as a beginning programmer to really say。

 oh， let's write a bunch of objects。 So just relax and enjoy and learn this material and think of it as sort of a。



![](img/7e7816831a9085f7a2b66199be652eff_1.png)

A theoretical thing rather than a how to program thing。

And so part of this is we're going to start reading data structures and I mean data on how to use all these libraries etc cea。

 and we're going to see the word objects right and then we're going to start hearing them and I want you to be able to read the Python documentation so that you understand what's going on and so you know the word objects should make sense to you even though you're not going to write a lot of objects on your programming and so page upon page upon page database stuff which we're going to talk about soon is uses objects all over the place and the beautiful soup talks but uses objects we've kind of been using them and I've been waving my hands and I use the word method without defining it but now it's really time to define it and go to it so。



![](img/7e7816831a9085f7a2b66199be652eff_3.png)

I want to review from the very beginning what we think of as a program， so the classic program。

 my favorite little minimum program is our little elevator floor converter which converts from European elevator floors to United States elevator floors and the key to this is that it's input processing and output and this is a good way to model any program and in that process we've got variables and we've got logic we've got algorithms。

 we've got loops that we write， we've got all kinds of things and we construct a series of steps to achieve some goal。



![](img/7e7816831a9085f7a2b66199be652eff_5.png)

In object oriented， and frankly， you've been using object or it all along。

The program has lots of objects and we're sort of putting stuff into these objects。

 taking stuff out of one object and putting it into another object。

 and you've actually been doing this all along as soon as you're looking at dictionaries and lists。

 you're doing objects and so it' an object is quite a little thing it's sort of its own little space inside of a program that contains code and data and so we're working together。

 all these objects are now working together。 it's a bit of self-contained code and data and it is one way to take a very complex problem and make it easier by breaking into separate things that can be engineered and develop separately。

 and so you could use in string objects or maybe you'd use beautiful soup or something these are powerful capabilities and if you had to look at all of them it's just hey。

 here's a thing use this object it'll do these things for you and there's lots of details inside of it just don't look at it。

 don't worry about it。 and so there's boundaries that things that you can use things that you。



![](img/7e7816831a9085f7a2b66199be652eff_7.png)

and look at and things that really you don't bother looking at。

 you go read the documentation and use it and away it goes。

 but then someone had to write that and so they built an object。

 so we're going to do is look a little bit under the covers of what it takes to build some of these objects。



![](img/7e7816831a9085f7a2b66199be652eff_9.png)

Am。And so if we think of this program that originally just sort of did processing。

 we can think of it as having some kind of an input coming into our program and we have a string object。

 a dictionary object， maybe eventually some objects like a database object or an object that we eventually define and you can think of us we're receiving data it comes in an object which is a string object or start putting the strings in dictionaries and do whatever we pull out a list of them and so you can think of data is moving between these objects。

 and like I say， even strings in the first week， first lecture， first week， first everything， we。

We were using objects， and we've been using them all along。

And so you can think of every string and every dictionary as a little program all by itself that has a bit of code and a bit of data and so a string has the data which includes all the characters that make up the string。

 but then there is a method called upper that does uppercase or our strip that strips off the right a white space from the right。

 and so it's like there' are almost little programs that have inputs and outputs themselves and we can make lots of them and there's lots of cooperating objects that make up an application。



![](img/7e7816831a9085f7a2b66199be652eff_11.png)

Um。And one of the nice things about the object orient pattern is that they。

For boundaries and within the boundary if you're inside the object。

 you can say look I'm going to build you a string object or a database object or a beautiful soup object。

 and I'm going to build this capability and I'm going to give it to you in the form of an interface and I'm not really going to care how you use it and so we have this sort of visibility wall where I'm going to make an object and I'm going to let you use it and the maker of the object doesn't necessarily have to know every single thing about the use of that object。



![](img/7e7816831a9085f7a2b66199be652eff_13.png)

But so just like inside the object， they don't have to worry about what you're doing with the object outside of it when you're outside the object。

 you don't have to worry about what's going on inside of it， we as the user of the object。

 we talk to its interface and we get things from it and give things to it and use functionality within that object but we don't have to look inside of this we can just say。

 oh， it's a nice little magical thing。 we read the documentation we read a web page and it told us to do this。

 this and this and a way you go and so it is sort of this isolation boundary that works both for the programmer who's writing the object and the programmer who's using the object and so it's a very nice pattern and so you'll see how we're going to build code and we're going to group it together and then we're going to be using it sort of is a big a blob of stuff。



![](img/7e7816831a9085f7a2b66199be652eff_15.png)

So some definitions in this space， words that I want you to understand。嗯。

When we're going to create one of these things， one of these objects instances that has some data in it and some code in it。

 we have to be able to define the shape of this object。

 What code will each object have in it and what data will each object have in it。

 And that's called a class。 The key to a class and this little picture that I've got up here in all these slides is a key。

 The class is a template。 It's not the thing itself。 So it's a cookie cutter。

 It knows a lot about how cookies are made。 And if you have cookie dough and you hit the thing。

 Then you make as many cookies as you want。 And so this nice little cookie picture is a great。

 you know， mental model of how it works。 The class。The class， oops。The class is the template。

 and then the object。Are all of the cookies that are made from that template。

 but the template defines the shape and the nature of the class。

 So the code that we write is is going of each of the objects。 The code we write is the class code。

 And then later we say， oh， let's take that template and make ourselves an object or an instance。

 Now， as we're defining a class。We have two basic things that we put in the class and there's a couple of different terminologies for this。

 one is method， which is code， it's like a function that lives inside of a class。

 not a function that is，Inside your program， but one that lives inside of a class。

 and so this is a scoping thing， a method is really just a function。But it's lived。

 it lives inside the class and then fields or attributes are data items that are in the class。

 and so there are variables that are defined in the class。

 you can define variables outside the class that you use in your program and you've been doing on it all long。

 but if you're saying I'm going to build this capability and it's going to have data inside of it and code inside of it。

 the code is the method or message and field or attribute and。They're just。There are just two。

Two different sets of terminology method is what I'll probablybable use if you look in some object oriented patterns like small talk or Apple。

 they often I' call these messages so you can either like access a method inside of a class or an object or you can send a message to the object the same is true for field and attribute this's just a chunk of data that's in the object that you may or may not have the right to access。



![](img/7e7816831a9085f7a2b66199be652eff_17.png)

So like I said， a class is a template it defines the characteristics of the objects that we're going to use to make it。

 it is the cookie cutter。

![](img/7e7816831a9085f7a2b66199be652eff_19.png)

So dog is sort of the exemplar， Lasie is a particular dog and so dog has fur and dog barks and dogs do all these things and so we know something about dogs。

 but it doesn't mean we have a dog right and the class is a more abstract concept that when it's time to get a dog。

 we know certain things about dogs。

![](img/7e7816831a9085f7a2b66199be652eff_21.png)

Instances or objects are once we say oh， time to make a cookie from the template， time to get a dog。

 we know something about dogs， that's the creation of an object and that we call them instances。

 instance of a class， so the class is it doesn't exist。

 but we say make me a new object using this class as its template oh and now make me another one and so we can have many。

 many objects from one class， so just like many cookies from one cookie cutter。



![](img/7e7816831a9085f7a2b66199be652eff_23.png)

Method is a bit of code that lives inside of an object， it's like a function。

 but it's scoped to within the object or within the class。Okay。

 so that kind of gets us started on some of the terminology and we'll come back and we'll take a look at how we write code and that's object oriented。



![](img/7e7816831a9085f7a2b66199be652eff_25.png)

![](img/7e7816831a9085f7a2b66199be652eff_26.png)

![](img/7e7816831a9085f7a2b66199be652eff_27.png)