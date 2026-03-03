# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p30 09_04_01_在C语言中实现封装和接口.zh_en -BV1v2421P7pt_p30-

![](img/7a771e5aa6bb626d7d626912680634da_0.png)

Hello and welcome to our continuing series of lectures on improving our implementation of a Python object。

 so what we've been doing is we have been building a series of implementations of approximate implementations of some of the things that we find in Python like the Python Dictionary。

And so the last thing we worked on with is Python dictionary class and the previous implementation was just a linked list with a key。

Now we're going to eventually have to build all kinds of different implementations and so the part of what we're doing is we're working toward abstraction where we're separating what the object is that we're interacting with from how we build it underneath and so we're going to do things like move our methods into the structure instead of just using prefixile naming conventions and just。

Reduce the need to look inside the class or inside the structure that is holding our class for code that's in our calling code。

 so we don't want to have to look at the class。

![](img/7a771e5aa6bb626d7d626912680634da_2.png)

TheThe class values inside the class。 So this is just continuing along understanding object or principles。

 the three implement the three principles of object orientations are encapsulation。

 abstraction inheritance and polymorphism。 And so for now we're bundling more things together。

 that's encapsulation。 and we're working on abstraction， and that is thinking about。

Separately how we are going to use this。Object from how we're going to build the object we're going to。

Reveal less and less of our implementation details to the caller。Okay。😊，And so for a while。

 we just said， well we'll just take the class and add like an underscore and name it， et cetera。

 et cea， and it seems absolutely simple enough and in some ways you see that C++ does exactly that when it's compiling C++ to C code。

But it just， it seems like it's simple enough and it seems like you would keep it straight。

 but it turns out to be a bad idea in practice， so Python strings。

 which I can write Python code and not have to look up documentation。

Are real objects that follow the principle of encapsulation。

 everything that you touch is inside of the object， like uppercase， searching for something。

PHP strings are。Kind of。More archaic in that PhP is more of a C like way of thinking about things in their type。

 and there's a bunch of libraries that know how to use this type。

And so I'm going to show you some ickiness in PhP， but I do love PhP。

 so don't I'm not just criticizing PhP。 PhP has a lot going for it。

 but in the language and the library there are some annoyances So let's take a look at a little bit of Python and some equivalent PhP and so you sort of see this notion that naming convention seems tempting。

 but it's not necessarily a great idea。 So in Python we say x equals a string we call x got fine and the first parameter the thing we're looking for。

 and then we have y equals x dot replace old new and so the first parameter is the old string and the second parameter the new string and then we say how long this thing is and so everything's very consistent。



![](img/7a771e5aa6bb626d7d626912680634da_4.png)

![](img/7a771e5aa6bb626d7d626912680634da_5.png)

But if we look at PhP， it's almost identical except it's calling libraries right so Do x equals a string with old in it and then we're going to use stirpose。

 that is the position in a string and the first parameter is what they call the haystack and then the second parameter is with which we call the needle。

 so then we look at the replacement which is equivalent of Xdot replacement Python。



![](img/7a771e5aa6bb626d7d626912680634da_7.png)

And it's not stir replace is stir underscore replace。

 so do we use underscores or we not use underscores and then the thing that just drives me crazy is what is the what would you expect。

 the first， second and third parameter of PP stir replace well if I was writing it， it would be。

The source string， the old search string， and the new thing to replace it with。

But that's not what it is。 The stir replace says old string， new string。

 and then the string we're doing the searching in。 you can go look this up。

 But PP talks about how there were generations of things like Stpo， I think。

 is one of the earlier ones。 Stlin basically is as one of the new that's one of the older ones。

 And so it's consistent with stirpo， but not consistent with stir replace。

 And so the naming conventions is just less than ideal。

 And and you can just see from a programmer understanding is just really simple that if we look at the Python says y equals Xdot replace old new。

 I can remember that calling sequence。 And I can never remember the stirR underscore replace in PP。



![](img/7a771e5aa6bb626d7d626912680634da_9.png)

![](img/7a771e5aa6bb626d7d626912680634da_10.png)

So the thing we're going to do here is we're going to put the methods in the structure and so that we see some of our C code before and after。

And so we create a pie di。And then you'll notice that just like what PhP did。

 I called those P dick underscore put。Pidict underscore L and Pic underscore get I was consistent because Iya was used underscores and Pic is the name of the structure。

 Pict underscore Dell。 and so I was pretty consistent with that。

 But now what we're going to do in the name of encapsulation is we are going to take all those methods。

 make them be part of the structure。 We're going to find that they're just pointers to the methods。

 but we are going to have global methods。We're just not going to access them through their global names。

 so we're going to create a new P deck saying Picck underscore new。

But then we're going to call to put something in， we're going to call DCT arrow put。

 and remember we have to make this first parameter like the self parameter DCT that's just always going to be that first parameter because we're sort of doing it Python style。

 and then you kind of know that Z is the key and catchphse is the value。



![](img/7a771e5aa6bb626d7d626912680634da_12.png)

And so that's the calling sequence and again， that DCT comma。

Is just because we're not an object or language and so we put self in there， again。

 homage back to exactly the way that Python did it and why they did it the way they did it because they were creating an object or framework on top of a nonob orient environment。



![](img/7a771e5aa6bb626d7d626912680634da_14.png)

Just like we are， and then you look at DCTarrow L and of course。

 putting DCTN as the first parameter is redundant but necessary。And we can do a DCT get。

And we in effect other than the first parameter which is DCT。

 we are putting the key in and away it goes， and then we could call the Dell method。

 but now you'll notice that every single method that is associated with a pie di is in the P di structure so let's talk about how we're going to do that and why and so this all kind of falls under leaky abstractions。

 meaning that。When we're in the main calling code and we sneak in and peek at the data attributes inside the class we call this leaking and later we'll talk about iterators and why iterators seem inconvenient and clunky。

 but what their whole job really is is to hide implementation details to make a cleaner abstraction when the calling code depends on this the internal implementation names and approaches that's what it is to be leaky so we need to define a contract between the class and its calling code from above that we won't change and we're going to call this contract on interface another kind of word for that is abstraction。

And so if we look at all the code in our earlier implementation， the whole thing is leaky， right。

 especially if you look at that four loop where it says four struct Dode cur equals DCT arrowhead。

cur not equal null， curve equals cur next。Print cur key and curve value。

 and so what happens is that should trigger a little like。This says。

 don't look inside these things and this is what we later we'll talk about iterators how far we go and how we actually。

 what we look at this code we're looking at right here， I think it's pretty。

But it kind of violates the abstraction boundary because we're looking too deeply into what the fact that this is even a linked list。

 we don't know there's a linked list， it may not be a linked list。

 it may be some other kind of a structure， it may be a treaty or whatever。

 and we will later get to the point where we will make these things， different implementations。

 not just a linked list。And so that's that's this idea that like you should be like， oh no。

 there's this little wall， but now I'm looking inside and then when you're looking inside that's when you kind of violating the abstraction boundary or we call it a leaky abstraction what this leads to is the notion of not all object attributes are the same。

And so when we're going to build an object， we are going to decide what parts of these things are the contract and what parts are leave us alone。

 we're going to hide this stuff and so the concepts in object learning programming are that things that the calling code is allowed to see。

 whether they be data or methods are called public。



![](img/7a771e5aa6bb626d7d626912680634da_16.png)

Things that are like reserved for class use only are private。

And then when we start talking about inheritance which we don't talk about too much。

 there is this middle class called protected and that is stuff that classes and derived classes can look at。

 but not the calling code so protected is sort of more like private from the point of view of the calling code So if you look at the abstraction boundary that we have here we see that the place where the abstraction boundary is sort of failing is that is that head and tail we want to make an abstraction boundary and and say that look that the notion of head and the tail that's going to be all hours and that's going to be all inside and that's inside the abstraction boundary and you're not supposed to mess with it So if we look at how we do this in Java there is a keyword called private and so Java we're making a point class and we're making two double values that we're saying X and y are private。

 which means you can't access it outside of this class the constructor。



![](img/7a771e5aa6bb626d7d626912680634da_18.png)

Public and the dump is public and so you see that that just means that you can't access X and Y outside of the class。

 but you can access dump and the constructor in C++ you see a private in a public and so private says this double X and y or things that can only be used inside the class and public is the constructor can be used outside the class and the dump can be used outside the class and this is just syntax that they put in now interestingly access control and Python is a little sort of wonkyier because Python doesn't really put things like public in private so what Python is doing and you've seen these across all the python you've done where you see these double underscores of Ds as it were like the constructor you're not supposed to call the underscore underscore a knit underscore underscore that's just when you create an object that's what happens。



![](img/7a771e5aa6bb626d7d626912680634da_20.png)

🎼And so that in the init is an internal method。 It's a private method。 underscore。

 underscore X and underscore， underscore Y are totally valid variable names。

 except we're marking to the outside world。 Hey， you're not supposed to access these and then def dump The fact that we didn't put double underscore in front of it means that it's public。

 And so double underscore are is the signal inside of Python to do access control And we look at some of the stuff that C++ really does。

 This was borrowed in many ways from how C++ does things internally。 So up next。

 we're going to talk about this map and the abstraction and the kinds of things that we do under the covers of the implementation details of the abstraction。



![](img/7a771e5aa6bb626d7d626912680634da_22.png)

![](img/7a771e5aa6bb626d7d626912680634da_23.png)

🎼。

![](img/7a771e5aa6bb626d7d626912680634da_25.png)

🎼Yeah。🎼嗯。

![](img/7a771e5aa6bb626d7d626912680634da_27.png)