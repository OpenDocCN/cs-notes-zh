# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p162 21_19_optional-dynamic-dispatch-manually-in-racket -BV1bw4m1D7MM_p162-

This segment doesn't have any material you need for the homework or the exam。

 but it really helps crystallize what dynamic dispatch is。

 so I hope you'll follow along and at least get the high level idea。



![](img/3c88385e291d5408e13ebe5c1059b71b_1.png)

What I want to do is write racket code that behaves like there's dynamic dispatch that codes up manually dynamic dispatch。

 but we're not going to use anything in racket that has dynamic dispatch given to us as the default。

 Now， racket actually does have classes and objects。

 So this is not something you would actually do in racket。 I'm doing this for a different purpose。

 I'm doing this to demonstrate how the semantics of OO。

 the semantics of one programming language can be coded up in another programming language。

 I always find it helpful to understand the semantics of something。

 by seeing how you could implement it using other constructs。

 So we've actually done this sort of thing before in the course， at least in optional segments。

 For example， when we saw closures in M。 I had some optional material on how you could code up closurelike things in Java or C。

 So now I'm really kind of doing the opposite to show that these languages are not。



![](img/3c88385e291d5408e13ebe5c1059b71b_3.png)

I different as you might think。So there are many ways we might do this。

 I'm going to show you a bunch of code in this segment。

 so let me just jump into how I'm going to do it。 Of course， there could be other ways。

 I'm going to use astruct and racket for objects and I'm going to say that every object has two things。

 It has a list of fields and a list of methods and that's all an object is。

 I won't have any notion of classes so this won't be quite how Ruby does OOP。

 but I will get dynamic dispatch even without classes and that's interesting too。

So both fields and methods are going to be lists， the fields are a list of mutable pairs so that I can update the contents of a field so I can set them。

And the methods will be a list of immutable pairs because the way I'm doing this once we have a method in our object。

 we're not going to be able to update that to a different method。

 Of course you can make other design decisions So for the fields it's just going to be an mcons of some symbol what's the name of the field and then some value thatll be the current contents of the field for methods that will also have a name like a getx method for a getter for the X field of a point object and then the other part is a function but it's a function that takes one more argument than would otherwise need and this is the key trick takes an extra argument where our implementation that is simulating dynamic dispatch will pass the appropriate object for that extra argument So I'm calling itself to remind us that this is the current object from OOP but this is not special in racket。

 This is just variable name that I happen to call。Self。

 I could have called it S or F or X or anything else。 Okay。

 so this is not a particularly efficient implementation using lists for fields and methods is much less efficient than a vector or some sort of hash table。

 It's not class based， but it lets us focus on this key issue， which is this extra argument self。

So you'll probably get a better picture of what's going on if I literally show you a picture。

 so this is a picture of what in a point object bound to a bracket variable x might look like。

 So x would refer to some object that you see here in the middle that just has two fields。

 one called fields and one called methods So fields is a list where the elements in the list are m cons as mutable pairs。

 So for example， maybe you have an X field that holds -4 and a y field that holds zero。

 if you had more fields this would be a longer list that's all there is to it。



![](img/3c88385e291d5408e13ebe5c1059b71b_5.png)

The methods is also a list of pairs and so for each of those pairs。

 you see here getX set X it would be several more and you see disk to origin would be the name of the method and then a racket function。

 a racket Lada that takes one more argument than you would expect。 So both self and Rs。

 and that's the idea。 So now let me flip over to the code and basically show you just a few racket functions that use these objects to implement object oriented programming。



![](img/3c88385e291d5408e13ebe5c1059b71b_7.png)

So here I have the struck definition， just like you would expect。

 I need one helper function that I couldn't find in racket standard library。 Maybe it's in there。

 It's like a so， which we have seen before， takes a list of pairs。

 compares something against the car of those pairs。 the first time it finds something。

 It returns the pair。 but I want this for an immutable list of mutable pairs。

 So something like my field list and I use that right down here。

 But now let's get to the three main functions， get set and send。

 So get is a function that takes an object and a field。

 It's just a racket function and returns the current contents of that field in that object。

 So all I do is get the fields of the object。Call that a soak like helper function I just defined。

 That should give me back a pair。 If I actually get a pair， returnturn its cutter。 Otherwise。

 I didn't find the field。 I got false instead。 And so I just asked for the field of an object。

 doesn't have that field。 And I chose to raise an error rather than Ruby's approach of returning nil。



![](img/3c88385e291d5408e13ebe5c1059b71b_9.png)

Let's set a field。 It's just going to be a racket function that takes an object， a field。

 and a new value for that field， do the same computation to find the appropriate pair in our list of fields。

 If we find it you set M couldter bang to update it， otherwise say we didn't find it。

And now the interesting one， let's call a method， which we know is also called sometimes sending a message。

 So here's a racket function that sends the object ob。 the message MSg with the Ags A R GS。

 I'm doing a little convenient racket thing here for multiargument functions。

 you can ignore that for the high levelvel idea。 But now what we do is we get the list of methods out of the object。

 use a so to get the appropriate lambda out。 So this will be a pair of the name of the method we're looking for and the lambda that implements that method。

 So if we don't find it raise an error messages before。 if we do the cutter is the lambda。

And let's call it yes with the as。 But as its first argument， the entire object itself。

 what we are doing here in this send helper method is passing into the lambda as the first special self argument。

 the entire object。 So let me show you back on the slides why that works。😊。

So I have the same object I had before， and now suppose someone wants to send to that object the dis to origin method。

 the message， so it doesn't take any extra arguments， so you would just write this。😡。

Take this object， call its dis origin method。 So what send will do。

 the code I just show you is get the list of methods。 Use a so to find the right pair。

 So that will be this pair right here， Dis origin。Then take the cutter of that pair。

 which is this lambda and call it。With self being the entire object， being X。

 so in the body of this lambda， anytime it uses self， self will be bound to the entire object。

 and that's exactly what we need for dynamic dispatch。So back to the code。

 what have I shown you so far， nothing except a struck definition， which is nothing to that。

 get for getting a field， set for setting a field， and then the key thing of sending where the entire action is because our methods take an extra argument。

 I can pass in that object right there。

![](img/3c88385e291d5408e13ebe5c1059b71b_11.png)

So now let's see how we could use these things to make objects。 So here's a rackcet function。

 it's just called makepoint。When you call it with two things。

 presumably numbers underscore x and underscore Y， it creates an object by calling the object constructor。

 we can see that right here， so when you call the object constructor， you have to pass in two things。

 a list of fields and a list of methods Here's a nice list of fields。

 we say the x field is initialized to the contents of the racket variable underscore X。

 the y field is initialized to the contents of the rack variable underscore Y。

 Our methods list is a little bit longer here it is okay and it's a list where we for each of them give a pair of the name of the method and then a lambda and the lambda always takes this x to argument。

And in fact， this get X method uses dynamic dispatch because when you call this lambda。

We get self and we don't need any of the other arguments。 And so we then use our get method。

 which is our to on self with underscore X。 excuse me。

 this is not dynamic dispatch because it's just getting a field。



![](img/3c88385e291d5408e13ebe5c1059b71b_13.png)

But dis origin is definitely using dynamic dispatch。

 So here I'm going to add a method called dis origin。 I'm going to use this。Lambda。And this lambda。

 when you call it， will send self the get X message， and by sending self the getX message。

 we will get dynamic dispatch。😡，So I can show you a use of make point。

 This is just this function here that's acting like a constructor for point objects。

 kind of like an initialized method。 If I call it right here with -4 and 0。

 I'll get back a point with all those fields of methods with an x coordinatedator -4 and a y coordinateor of0。

 So if I send it the get x message， I'll get -4。 if I send it the get y message I'll get 0。

 if I send it the dis origin method， I'll get message， I'll get4。 I could then set its y field to 3。

 and then I could ask its distance the origin again， and I would get 5。

 turns out-4 comma 3 is distance 5 from the origin， it's a pythagorean triangle。

 And if you look at this code。

![](img/3c88385e291d5408e13ebe5c1059b71b_15.png)

![](img/3c88385e291d5408e13ebe5c1059b71b_16.png)

Except for some slightly strange syntax， it looks like object to in programming。

 create a new object with Makepoint。

![](img/3c88385e291d5408e13ebe5c1059b71b_18.png)

Read， call these methods to get fields， call these other methods， get results。

 call a set method and so on。 So I'd argue this really is object oriented programming。

 especially if I can get subclassing to work。

![](img/3c88385e291d5408e13ebe5c1059b71b_20.png)

So in the code here， I do have a color point class but that's not the interesting one。

 so I'll let you study that on your own instead I'll jump straight to our fancy one which is making a polar point。

So a polarPo takes in an R and a theta， we saw a similar thing in Ruby。

 and what I'm going to do here is I'm going to create an object。

 here's my object constructor that uses the fields and methods of point。

 but then adds extra things on the front。So for the fields。

 I'm going to take whatever fields you would get for making a point。

 as I do up here and then add on to the front using a pen in R field and a theta field。

 And for the methods， I'm going to do the same things。 I'm going to start with the methods in point。

Then I'm going to app on all these other things。 And some of these methods are new。

 And so I'm adding them to my list。 And when I look them up， I will find them。

 Other ones like getx are doing the moral equivalent of overriding。

And by putting them closer to the beginning of the list， I will find them first。

 because the way a soak works when it goes to look things up is it starts at the beginning of the list。

 So simply by putting them earlier in the list， they will override anything that was in the list I got from the methods for point。

And as you might imagine， the key thing I do here is I override the getter。For x， the getter for y。

 the setter for x and the setter for y to compute in terms of r and theta instead of in terms of the fields x and y。

And thanks to the dynamic dispatch of the dis origin Lambda defined up here in Makepoint。

 when it now sends to self the getX and getY message on something created by Make Polar point。

We will do the right thing and get the right value。 And I have an example down here。

 If I make a polar point with an R of 4 and a theta of pi。

Then I will have something that should behave like when I made an ordinary point with minus4 and 0 because an angle of pi gives you a y coordinated  zero and I have the same sequence of message sends here and I should get roughly the same answer let me show you that quickly If I just run this you actually get three objects I played around with here。

 This first one is the plain old point and I end up seeing that after I set y to3 and then ask the distance to the origin。

 it's now five the second one uses a color point which I didn't talk about here in the video but you can look at on your own and this third one is where I made a polar point and it actually is right when I ask for get x I get minus4 even though the r is4。

 the x coordinate is minus4 because that's how polar points work in this case get y should be zero and it really is this is just a rounding error it's giving me three times 10 to the minus10th power that's a very small number let's call it zero and declare victory and then the distance to the origin is four after。



![](img/3c88385e291d5408e13ebe5c1059b71b_22.png)

![](img/3c88385e291d5408e13ebe5c1059b71b_23.png)

I set y to 3 when I ask to distance the origin again， I get 5。 So it really is working。



![](img/3c88385e291d5408e13ebe5c1059b71b_25.png)

Okay， back to the slides just to wrap up， I know this has gotten a little long。

 This is the idea of subclassing we saw that because as you see here in the blue。

 when we send a message to self self ends up bound to the entire object because of that send function we wrote it's the send function that binds self to the right thing to implement dynamic dispatch And finally。

 one last thing now that I've shown you all this somewhat clever somewhat illustrative rackcet code is I was very careful not to try this exercise in ML。



![](img/3c88385e291d5408e13ebe5c1059b71b_27.png)

![](img/3c88385e291d5408e13ebe5c1059b71b_28.png)

ML's type system would really get in our way here。The lack of subtyping makes it very difficult to create a polar point object that can use things that assume they're given points that the type you would want to give to the function that we're using for disk origin is not a type you can conveniently write down in ML。

 so we are quite lucky that in racket we did not have a type system to get in our way。

Now there are ways to do this in ML， for example， you could give all objects the same type using a big data type constructor。

 I don't want to say it's impossible in ML， but I do want to say that M's type system is not friendly to coding up your own dynamic dispatch。

 which is why MLlike languages that want to support objects like OcaMl and FSharp add objects as their own thing in the language and Sca does the same thing as well。

 so it's fair to say that ML， as we saw in this course is not friendly to coding up your own dynamic dispatch but it's also fair to say that a language that was focused primarily on types for objects like Java before Java added generics in the version 5 of the language are equally hostile if you will to the sort of generic programming and polymorphic code with function closures that we saw in ML so it's a good example where sometimes type systems prevent switching programming styles。

 but still。Support a particular programming style， very well。



![](img/3c88385e291d5408e13ebe5c1059b71b_30.png)