# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p127 19_JavaScript对象生命周期.zh_en -BV1Lr421A75d_p127-

![](img/2fe0bf02b638006f24cc0cbd37248f65_0.png)

![](img/2fe0bf02b638006f24cc0cbd37248f65_1.png)

So now we've talked about how objects work and how we create them and the function keyword and how the first class functions work and now we're going to talk really about how we create and use and discard objects a basic OO concept is the concept of a constructor and the constructor is the code that runs at the moment the object is being created from the class。



![](img/2fe0bf02b638006f24cc0cbd37248f65_3.png)

Okay， destructors are the moment that the data in the object is being thrown away。

 Javascript doesn't have destructors。 That's because everything is quite dynamic。 Destructors are。



![](img/2fe0bf02b638006f24cc0cbd37248f65_5.png)

Unpredictable in in languages like Java， I think C plus plus there are more predictable when a goes out of scope PhP Deors are more predictable。

 but okay the conceptual idea a constructor's code that you can jack into the moment of creation and deors are code that you can jack into the moment of destruction。

 So if we go back to the PP， you see a better example of how deors work that has to do with how the PhP runtime ultimately works because the request response cycle。

 but constructors are the most important deors are of secondary importance。



![](img/2fe0bf02b638006f24cc0cbd37248f65_7.png)

So in JavaScript， the constructor。Is implicit， right。

 because it we're using sort of the essence of first class functions here。

 The constructor is all of this code， and it really is running to define the shape of the class。

 There's a variable X in the class。 There's a function called party in the class。

 But it's also just running code。 So you see when this new happens。 It actually runs all this code。

 Now， it doesn't run this code。 It runs the code to create that the console log in the constructor。

 And then this dot party gets constructed。 And that's the new。

 That's what happens at the moment of new。 It doesn't run this code。

 But it remembers this code and it assigns it into this party for that。 And then， of course。

 we do the a and dot party and a away we go。 And so that the rest of that is exactly the same as the previous example that I showed you。

 So the constructor is。😊。

![](img/2fe0bf02b638006f24cc0cbd37248f65_9.png)

The function itself as compared to a specially named function。

 which in the other kind of objectorient pattern， it's often especially named function。



![](img/2fe0bf02b638006f24cc0cbd37248f65_11.png)

![](img/2fe0bf02b638006f24cc0cbd37248f65_12.png)

So we can create many instances， many objects， in classes， there's only one of those。

 but that's a cookie cutter， we go stamp， stamp stamp and then object object object， right？

And so each one has its own copy of instance variables。 So here's an example of that， right。

 We're going to actually create two instances from one class。

 two objects from one class and work with them。 So the other thing that we're going to see in here is we're going to see the idea of a constructor parameter。

 And so this is a parameter that we're going to pass in。

 and the new is the thing that causes the constructor to run， causes all this code to run。

 but we can pass a variable in right And so we can pass in different moments of construction。

 We can pass different ones in。 So the first time we're going to construct a variable。

With Sally in it。And we're going to copy this constructor variable into an instance variable。

 So this is an instance variable， instance variable， this is a method。

And so this namem is going in there and the interesting thing is this is code。Look at this name。

 this name is coming down from here so that this dot party is actually different code in the S variable than the J variable because it's looking this namem is sort of instance differently inside of it。

 That's kind of amazing how that works， right so。😊，It runs， it creates three things inside here。

And then it gives this back and then points S at it。Okay， and then we call。 So that says built Sally。

 This little message has built Sally， and then we call the party method。 And you see it knows Sally。

 it runs this code。 It adds one to it， prints out the one and the Sally。

 So that prints out there then。Then we're going to do this again。

 We're going to run the constructor again。 And Nam this time is Jim。

 So Jim goes in there and goes in there and goes in there。 So then we end up with a new object。

That is got Jim in it。And then other data in it。 And then when this finishes， it returns this object。

 and we store that into J。 So we have now two instances。 First instance is into variable S。

 The second instances is the variable J。 And so now we call J dot party。

 And so that runs this party code， except that it runs it with Jim equals1。 And S stills there。

 So we'll call S dot party， and that'll go run the code again。

 except that that thealally instance and the variable x is 2。 And so that runs there。

 So we have a situation where we have two instances。Two variables。

 And we're working with them independently。 And that's really kind of the beauty of object orientation is you create this one template。

 one class， and then you go stamp， stamp， and you have two objects， and they function independently。

 They have their own variables， their own code and a away they go。



![](img/2fe0bf02b638006f24cc0cbd37248f65_14.png)

![](img/2fe0bf02b638006f24cc0cbd37248f65_15.png)

So what we've been talking about is we make this template in a class that consists of methods or messages and attributes。

 and then the constructor is the place where we set everything up and the object or instance is what we get back from the constructor。



![](img/2fe0bf02b638006f24cc0cbd37248f65_17.png)

So。This was a really quick and short lecture because I think you know a lot about object orientation in general already。

 and so all we really wanted to do was talk about the real special sauce that JavaScript has and。

Javascript's objects are dynamically extendable。 you'll notice when we said this do X。

 we didn't have to tell it in advance we were going to do that。

 we actually executable code creates the new attributes and at runtime。

 you can actually create new new methods as well。 and so these objects are powerful and if we go all the way back to arrays。

 we kind of without even knowing it you can use objects in JavaScript。

 you can say curly Bras key value key value key value sets up an object in that case with no methods。

 but with a set of attributes。 and so we kind of treat objects as JavaScriptscripts equivalent of an associative array。

So up next we're going to talk about JQuery， which is probably the most powerful object that most of us will use in JavaScript as we write code。



![](img/2fe0bf02b638006f24cc0cbd37248f65_19.png)