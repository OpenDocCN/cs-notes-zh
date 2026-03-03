# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p19 19_04_03_JavaScript面向对象-类.zh_en -BV1rNibBuEwD_p19-

So now I want to show you a little bit about how we build classes in JavaScript。

 how we build our own classes and how classes work internally。

 you may have noticed that the coffee cup that I'm using during this JavaScript lecture has code on it and the code is somewhat JavaScriptpy。

 I think it's JavaScript， it's C Java I think this would be C or JavaScript or Java because again these are all related languages。

So let's take a look at a sample class here and so the first thing to notice is that it uses function as the keyword to define a class now you might see what's called ES6 classes and it's a like syntactic sugar that layers on top of this that makes the syntax look more like the other languages。

And so this is kind of like vanilla， the underlying actually how they work。

 and so I guess I'm glad that they've made syntax that looks like everything else。

 but it really belies the elegance of the original way it works。

 the syntax doesn't change how it works， this is how it really works。



![](img/16fad4d178a71749f2d47b9e5a440cb0_1.png)

And the things that's super excellent about this is that it uses the function keyword。

 there's not a different keyword Okay， every other programming language。

 pretty much when they go into an object， they use a different than they're in their procedural so a。

And a class is a specialized function that as a side effect of its execution returns code and data Okay now we'll see that we invoke it a little bit differently so let's start and take a look at what we got here we got this function party animal right so party animal is the name of the class but it's code and again we have a curly brace to start it。



![](img/16fad4d178a71749f2d47b9e5a440cb0_3.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_4.png)

And the thing that's different is there's this notion of this。

 so we make sort of an empty vessel that is going to be the object that we're going to use this class to populate and then by running the code we're actually populating that empty vessel so this dot X is going to create a member variable called X inside this。

 which is the empty vessel object that we're creating and then we're going to fill up and then we have this dot party。



![](img/16fad4d178a71749f2d47b9e5a440cb0_6.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_7.png)

This top party is also a piece of data in this object that we're about to create and you'll notice that we're saying equals and then function。

 but this one is a little different， you'll notice the function is unnamed。

 it is what we call an anonymous function because it doesn't have a name。So this。

 the function's name is actually called party， but it just happens to be call Vardi because we're storing the functions code in a instance variable called party。



![](img/16fad4d178a71749f2d47b9e5a440cb0_9.png)

But that's how we're going to call it。 So in the party variable。

 we have the code that is those two lines。

![](img/16fad4d178a71749f2d47b9e5a440cb0_11.png)

And then within that method now I'd call party a method to use the terminology。

 within the party method， this is the instance that we're talking about in Python。

 we use self for this right in different languages have this concept of the current object that we're part of。



![](img/16fad4d178a71749f2d47b9e5a440cb0_13.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_14.png)

This dot X is referencing， remember how we talked about global and local inside of functions。

 well this x is actually outside of the function， so this is an advantage that this dot x is defined inside the function and because this is defined before the function definition。

 it sees that， right？And so we're going to add one to that member variable。

 and then we're going to put out a console log message and that's our entire object it's got one attribute called X and one method called party。



![](img/16fad4d178a71749f2d47b9e5a440cb0_16.png)

Okay。😊，So we could just call this this function party animal， but that's not what we do。

 we have a new keyword called new and it says， look， don't just run this code。



![](img/16fad4d178a71749f2d47b9e5a440cb0_18.png)

Create an empty object and then use the party animal code to sort of fill out that object with a bit of code and a bit of data。

 and so that says， run all this， but instead of just running it。

 give me back the thing that eventually it produces it's as if there's like a return statement at the bottom of this thing。



![](img/16fad4d178a71749f2d47b9e5a440cb0_20.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_21.png)

At the bottom of party animal function。And then give me back the object。 and now I have an object。

 and it's got an X in it， and it's got a party in it。 Then AN is where I store that object。

 So AN is my first instance of a party animal object。



![](img/16fad4d178a71749f2d47b9e5a440cb0_23.png)

But now I can talk to A&O party。And and called again and again。

 that's so I call andO party three times so I call the method party。



![](img/16fad4d178a71749f2d47b9e5a440cb0_25.png)

Okay。

![](img/16fad4d178a71749f2d47b9e5a440cb0_27.png)

So that is the basic mechanism。And so if we were to somewhat trace through this。This this part here。

 the function just as a template that it's remembering the template naming it party animal。

 and at the point where we have AN equals new party animal，Javascript constructs this object。

 and it's got two things in it。 It's got an X in it， and it's got a party in it。

 X is data and party is code。 And then that's what it looks like。 But it's got， well。

 actually no the construction， I me got to change here。 The construction also put。

A 0 into this dot x。 And so as a part of the creation。

 you ran all this code to construct party animal。 And this got set to 0。

 So when we're at this next line of code before we call A and dot party for the first time。

 A dot X is got a0 in it。 Then we call an dot party。 and it runs the code， A dot party。

 this A N is an alias for this。And so in a sense， when it says this dot x。

 it really is A dotX Now we'll see in a second how when we do multiple instances， how that works。

 so it runs the code， and then it adds this to be one and then it prints out the first line。

 and then it does it again， and then it becomes two。

 and it prints out the second line and it does it again， prints out three。

 makes it three and prints out the third line。So that's how this code works。

 This is the constructing。Or creation or taking the little cookie cutter and poof making a cookie out a cookie dough。

 you got a bunch of cookie dough that's like a little object that doesn't exist it's got no form and then we take the template。



![](img/16fad4d178a71749f2d47b9e5a440cb0_29.png)

And we make the thing。

![](img/16fad4d178a71749f2d47b9e5a440cb0_31.png)

So I mentioned the word constructor because there is this moment where it's actually building the object and filling it up with all the little pieces so objects are created used by us and then discarded and there is this concept of a bit of code called the constructor in object oriented theory that says。

 look I'm going to start an empty object and then I'll fill it with stuff and the constructor is the sort of filling it up so it's ready to do its job once you're done constructing it Destructors are a common concept and we talked about that those when we talked about objects running in Python you don't get to get a hold of the distractor inside of JavaScriptscript that's something that they just don't let you do。



![](img/16fad4d178a71749f2d47b9e5a440cb0_33.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_34.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_35.png)

And I think it philosophically has to do with the idea that you're in a web page。

 you're not going to be there for very long and that's really the earliest of days right。

 these days with things like view and React， some of these JavaScript pages last a very long time and maybe it'd be useful to have deors in there。

 but JavaScript didn't have them in the beginning。Okay， so the constructor is in a sense。

 the moment where we are this new is triggering the constructor and what it basically does is creates basically a blank object that has nothing in it and then runs the code inside a function party animal to give some form。

To that object right and so this right here is the constructor right and so I just put a console log so you can kind of see where that happens。

 it says I'm in the constructor and then this thing works the exact same way It's just a kind of instrumented the moment that we're in the constructor。



![](img/16fad4d178a71749f2d47b9e5a440cb0_37.png)

And the purpose of the constructor and object orientation is to set the initial conditions of the object so that the object is ready to be used and like setting x to0。

 setting x to0 is apparently for this object a necessary condition。So once we have a template。

 cookie cutter。We have a class， party animals are class， then we can make many different objects。

 and then those objects have each independent data that's the key to this right。

 and we call this having multiple instances or multiple objects that implement a particular class。



![](img/16fad4d178a71749f2d47b9e5a440cb0_39.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_40.png)

So here we go。Here's our same old party animal that we've been talking about all along。

The only difference now is we actually give a parameter here and so one of the things that this is going to do is as part of its construction。

 it is going to copy that first parameter into one of the instance variables so we're going have two instance variables。

 this dot X and this dot name and we're going to copy whatever that is now where does that come from Well it comes from the moment of construction when we're saying make me a new port animal oh and here's a constructor parameter so that Sally goes in as nam So this dot name equals Sally。

This dot x equals0 and then this dot party is exactly the same way。And so when we run this。

When we run this， it comes in。It constructs Sally。Setting that and it says built Sally。

 that's that nam， and then we call Sally S dot party。

 So this is the actual object is in the variable S we call S dot party and this dot nam。

Is Sally and it's equal to one， and then we make a new one。We make a new one。

 going to make a new one， but this one's we called gym， so we make a second variable。

A second instance variable iss going to be have a second copy of x on a nam and actually a copy of party right and so then it'll sayB Jim and then we say J dot party and then we set gem to one and then S dot party that sets Sally to two and so now the J variable in the S variable are completely independent variables。



![](img/16fad4d178a71749f2d47b9e5a440cb0_42.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_43.png)

And so halfway through。So when we're down to here， we've got this object。

 St party will x starts out at zero， and the name here is Sally。

And then STt party comes and runs in here and prints out。Sally equals one， right？And then comes back。

 and then we're going to create a second one。Sure。So we've created second one and that'll be in the name J in the variable J。

 right， so we've created one。Oops。We've created one， create G， outcomes built gym， and then we call。

 and then this is zero， this is Sally。This is1， this is zero， this is Jim。And it saysG equals1。

And then we're going to call Sdot party here at the very end。

 and so it's going to run this part code again， except now this。

Well this is an alias of S so you can see how when we call J dot party， this is an alias of J。

 and we call S dot party， this is an alias of S these are instance instance。

 so S is one instance and J is another instance of it and so that's how we take one class and make multiple instances and each instance has their own independent copy of the variables。



![](img/16fad4d178a71749f2d47b9e5a440cb0_45.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_46.png)

So。That's a real quick introduction， mostly to get syntax。

 I'm not going to ask you to write a bunch of objects。

 but we are going to use a ton of them and when you start learning about JQury。

🎼And document object model and all that stuff。 this dot syntax and the methods and the member variables。

 the attributes away you go。 So you got to know all this stuff。

 So class is a template method or messages the code that's inside of objects and classes and then attributes is the data inside objects and classes and。

 and then constructor is the code that runs as one of these things is created。

 So that's a real quick romp through object oriented jascript。'， it's actually in some ways。

 one of the。

![](img/16fad4d178a71749f2d47b9e5a440cb0_48.png)

I debate with myself whether I think that the Python or the JavaScript object Orient pattern is more prettier。

 I mean there's other ones that aren't as pretty as these two。

 so we've in Python and JavaScript I think we're fortunate to have two very mature and very advanced thinking in how to really build beautiful object oriented systems。

