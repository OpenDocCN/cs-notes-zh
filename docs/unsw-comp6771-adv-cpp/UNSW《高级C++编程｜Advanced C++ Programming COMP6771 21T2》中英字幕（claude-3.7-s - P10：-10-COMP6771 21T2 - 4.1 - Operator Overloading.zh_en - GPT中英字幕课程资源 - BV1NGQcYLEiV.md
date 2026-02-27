# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P10：-10-COMP6771 21T2 - 4.1 - Operator Overloading.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

う。O operator overloading topic 4。1。I don't know if anyone has any preconceptions about what they think operator overloading is。

 but essentially it's a really key part of the language， and it's very powerful in C plus plus。

 So you've probably already dealt with some kind of operator overloading and other programming languages。

 right， Like if you've worked with Python or Java， you've used the。诶。The two string， you know。

 like the two string syntax or the string syntax where you could override what exactly like。

Something is to like turn it into a string。 You' probably over in the the dot equals in Java。

 for instance， where， you know， you redefine what it means for two things to be equal。

 And it's basically that topic， except everythings being taken and put on steroids， so。



![](img/52d03b547472f794a9e3ad7b22d66390_1.png)

What the aim of learning about this is right like we don't just learn about language features randomly。

 the aim of learning about this is because operator operator overloading allows us to dramatically decrease the complexity of our code。

By reusing very well defined semantics because this's the funny thing about programming when someone writes in a programming language。

 they already know what plus and minus and times and equals and plus equals like they know what all these things mean and we're going to try and reuse those same semantics to make our code a lot simpler。



![](img/52d03b547472f794a9e3ad7b22d66390_3.png)

So the first thing is that。I have a little example piece of code here and what this is is this is a point class。

嗯。Up here。Where it's got a constructor that essentially just a uniform initializes x and y。

 it's got two different getters， one to get x and1 to get y they are both constant methods and they return a constant integer so they not only return a constant thing but you can you can call them on constant and non-cons objects and then I have a static function here。

 which returns a point and it's called add and what it does is it takes in a reference to a cons point P1 and then a reference to a cons point P2 and it's going to add them together。

 So they're kind of like that's kind of the interface of my class type。

 I then store an x and y inside to actually you know。Deal with the X and Y that is the point right。

 because it's like an XY point。But here's the thing。

 if I wanted to print out the sum of these two points。

 the way I have to do this currently is to use this line here now。

Im I know that's not a real like that kind of looks a bit weird。

 but essentially I have to use a print function。Which what it does is takes in an output stream。

 which in this case will be standard C out and it takes in a point that I want to print。

 but that point that I'm going to try and print is the return of this function here。

 So I have a static function that takes in two points P1 and P2 And what it does is it constructs a new point like a third point which is the sum of the X and the sum of the Y right so it's basically just adding。

Two different points together。 That's how you sum two points together。 So we take our P1 R P2。

 We add them using the static function。And then we print it by saying take this point and print it to standard C out。

 Now what the thing is is let me just pull this code up in VLb， right？嗯。So the thing is。

 is that you might be thinking， oh， that's really weird to have this kind of like print function thing。

You know， like why， why don't we just， you know？Well， sorry。

 that one lines missing from this example。Why don't we just do u instead of all this stuff？

Why don't we just like do like standard C out point add or something， You know。

 let's just like print the point out like that。 And the reason you can't do that。

 right is because again， and we've kind of seen this in other things。

The compiler has no idea how to print a point out。 It's like what the hell do I do with that。

 It's like you ever tried to print out a vector or an unordered set or some of these other STL containers。

 The compiler doesn't have this inherent sense of like， oh， that's what a point is so。

You essentially have to give it a away to understand that。

 And we've done this here by defining our own。Function now in this sample piece of code。

 we've done this thing here called friendsend， right。

 So I've kind of updated this one a little bit since I put the lectures together。

 And it's a little bit different， but kind of the same。 And we're going to keep talking about this。

 So there's kind of two different ways you can understand this。 This one's a bit more complicated。

 though。but kind of like if we wanted to right now print out a point。

 we would have to print it out like this。Right， you would give it an output stream。

 which is standard at C out and you' would give it a point。

 And then we'd be relying on this a god damn it， what have I。



![](img/52d03b547472f794a9e3ad7b22d66390_5.png)

That's okay。 We'd be relying on this， Let me just copy this one。



![](img/52d03b547472f794a9e3ad7b22d66390_7.png)

So we have our print， and this should work in theory， like if we try and build this 401。

Let's have a look at a couple of these。Strange occurrences here。

It the one thing I didn't check silly， silly me， but it mostly compiles Kant's type quaifier on return type has no effect。

Oki doki。 So my guess is here is that the compiler probably like。

Everything that gets returned from a con member function is constants anyway， probably my guess。

So we can just try that out。 Yeah， Okay， so that's just a little funny thing。

 must added that in when I was just looking at the notes and didn't run it again。

 So if we build and run that， right， lectures， lectures 4。



![](img/52d03b547472f794a9e3ad7b22d66390_9.png)

401 or demo 401。 It actually does sum up the points。 Now。

 the reason I want to start with these examples is to really show you that there's actually a couple of straightforward steps you can take to turn this from something like this where you have to use this semantic to something like this where you just say standard。



![](img/52d03b547472f794a9e3ad7b22d66390_11.png)

Our P1 plus P2 like that done。 And to do that， we just have to make some very slight modifications to our code。

And again， the， the stuff I have in the code base is slightly different to this， which I'll。

 I'll tidy that up after， but。Have a look at a key word that's existing now in this code and that key word here is operator。

🤢，So in C++， you can redefine what an operator。Type an operator operation is for any given type that you like a custom defined type。

 like a class you make， simply by putting operator and then some kind of。

Of the actual operator overloading。Here I've got operator plus。

 here I've got operator output stream right as in like you know going from the right streaming to the left。

And I've got these two things here that I'm overr and what I'm basically saying here is instead of just doing some random static function like add that I'm overriding。

 I'm actually going to override the plus operator for this class and here I'm going to override the output operator for this class and now these are just declarations here I've just got two declaration lines。

And here's the actual definitions。 Now， ignore the friend part for now。

 Don't think too much about the friend part because we'll keep coming back to that， but。

Pay attention to how pretty much everything else is the same as in the previous example。

So in the previous example， we have。This first function， the add function took in two points。

 and it returned a new point， and the the print function took in an output stream and a point。

 and it returned a an output stream。 Now， that's exactly what was happening in this first example here。

嗯。Well， the print didn't return an output stream， but that's okay， it's nearly the same。But yeah。

 same thing here， two points in point out。And， yeah。What this allows us to do。

 which is super exciting is this allows us to actually use the standard C art here。

 So we can actually say standard C art P1 plus P2。 and those two things get added together and then it gets printed and why that is so important to us is because it's clearly understood。

 right， you don't need to know anything about this class to understand that like you're going to print the sum of these two objects are。

 You might not know what the sum of two points is。 you might have to go you know go back to like first year maths or something but you understand like the semantic really clearly now。

😊，In terms of these operators。You have to think about the operator words like functions。

 So previously here we had the name print。 and here we had the name add， right。

 But in this case here。This is the function name。 So don't think of this like some really random syntax。

 It's actually just a function name。 And what I want you to think about is what the C plus plus compiler actually does implicitly without you realizing is that when you say when you give it an expression like P1 plus P2。

And it evaluates that what the compiler actually does is it goes and looks through its bank of libraries。

 you know， maybe SL libraries， maybe ones you've defined in the source code and it says。

 do I have any functions？That take in two points。That are an operator plus。

 So this plus here tells the compiler it's addition。

 So I'm going to look for a function that's name is operator plus It's kind of like a reserve word。

And I'm going to look if there's any instances of that function where it takes in two points and the compiler goes。

  aha， I found it here。So it finds that there and then it works with it。

Pink Oomega says't why don't those STL containers overload the print operator so like why don't stand a vector and stand it unordered set？

I don't know why。 My guess is because there would be no real logical。

Universal idea of what printing means。 So why implement it。You know， like。

PriPri like what printing should do is not really。Does not really have a truth to it。

 So that's my guess as to why it's not done because like you print a string。

 You know what a string looks like， right， Like a string is a series of characters， You print it， it。

 prints out a series of characters。 But for like containers and stuff， it's like。嗯。

Like should should should there be braces up front， should they be comma separated。

 space separated like you could probably make a very diverse print function。

 but that's kind of why we have STL algorithms right so you can easily take an algorithm。

 iterate over it and print it out。Ryan says is it because vectors can hold many different types Well not so much because everything in C plus plus is somewhat recursive so that if you have a type like a vector that can print and it tries to print the underlying types it'll just called the underlying types print thing that's kind of how you can just print out a string because the string is printable and an integers printable right and you've probably seen this in Java too right like if you print an array list of a custom class it just prints out this little nice list of memory dress or reference reference addresses。

 whatever whereas if the underlying type it's being stored in the array list is actually printable then it prints that out。

嗯。Gurt says， can you assign precedentnce to operators？No。

 not that I know of And last question for now， Sam says， could you explain。

 why do we need to return OS for the operator less than less than。

 is it just for standardacy art purposes， So that's an excellent question。

 What this entire lecture is about is looking at a handful of the key operators。

And the specific patterns you have to follow because one funny thing about operator overloading is it's very boilerplate。

 This is a really easy topic， but it's a very specific topic in terms of the language expects you to kind of follow certain rules。

 like for an addition thing， you know you kind of want to pass into cons things。 Some rules。

 we enforce some rules， the compiler will enforce but it's like you don't want to add two things together that are mutable that doesn't make any sense。

 So you wouldn't do that you know， when you return the operator of a return plus should be the same as the sum of the operator the two returns。

 with with the standard C out stuff like this。The reason that this returns a standard O stream is just essentially how this operator expects to work。

 and I can quickly demonstrate that to you and then we need to move on。



![](img/52d03b547472f794a9e3ad7b22d66390_13.png)

![](img/52d03b547472f794a9e3ad7b22d66390_14.png)

Here。If I copy and paste this then I run our 0。2 example。Right。嗯。

And it doesn't work for me because I got my cons there， silly cons。Apologies。 I do。

 I do actually like rerun all the code before the lecture。 I do like a full sweep of it。

 and then occasionally I tweak and poke things， and I forget to like re clone it and run an N V lab and everything。

 So sometimes I miss something， but。When we look forward to here， this works right， as you'd expect。

😊，But the kind of question is，What do I just copy， Did I copy the wrong thing。哦，那。I'm so confused。

 Did that not actually copy。That's better。A， ya， a， okay， that one worked fine all along。

 So in this case， here is' the question， why does this have to return standard O stream or a reference to a standard O stream。

 And the answer is quite simple。 It's because think about how standard C art works。 Now。

 just to explain standard C， I'll show you this。 what。

 What happens is if I say my point is like this。And you're probably familiar with this。

 You've done something like this， no doubt。The way that the like the compiler and the executable work is very similar to how addition works。

 right like when you say a computer int I equals 5 plus6 plus plus 7 plus8 Now I am I'm not a low level expert so I'm going to get this wrong。

 but you probably remember that what a computer does here is it doesn't just like get all four numbers and just go like。

Bang them together。 It goes， I'm going to get 5 and 6。 and that's 11。 Now I'm going get 11 and 7。

 and that's 18。 And then I'm going to get 18 and 8。 And now that's 26。

 So a computer essentially breaks these things down into a series of what youll call binary operations。

 right， with like binaries in two parts。 So standard C outs actually exactly the same。

 So what happens with standard sea out， for instance， is that you have to think of this。

 And this syntax will hopefully finally click for some of you。 It did for me。

Is that what this actually is， is this is an operation， just like a plus and a minus。

 You're actually saying I would like to operate。 I would like to less than， less than operate。

 I would like to stream。Like output stream operate。These two parameters。

 these two arguments into a function， and what that function is is it looks like this one。

 so there's actually a definition somewhere in the STL in the C plus plus string library that actually defines how a standard C out can be operator left left。

 whatever you call it to a string that's defineds somewhere so that it actually knows how to print that out。

And what happens is that function call to that operator less than less than。

 and just to like be very literal， I'll just point this out here。You know。

 it kind of might look like this， for instance。And it'll do something here。Right。

What this actually does is it returns an OS。 So what happens it returns the O that was given。

 So what happens is is that when this is called， when this operator output stream function is called with these two arguments。

 what does it return， It returns the operating stream it was given at the start。

 so it gets turned into that。And then what happens the same thing here is， again。 So there we。

 we first evaluate this。P1 plus P2 turns into a new point and then we pass it into another operator output stream function which takes an a point and to C out。

 and that's good because we define that right and without this the compiler would fail here and it's like I have no idea how to do that and you can actually see you actually see this in action if I comment out my operator overload for the output stream。

And then I build point2。It says I he very lie。😊，2。

![](img/52d03b547472f794a9e3ad7b22d66390_16.png)

Undefined symbol operate less than less than。This makes a lot of sense now， doesn't it。

 Because think about what this is saying， This is saying that your program used an operator less than less than function。

 where it' expected to take in a output stream and a point reference to a cons point。

 and it could not find it。 It couldn't link it。 It expects it to be defined somewhere in all the compiled files。

 but it's not there。 So that's kind of what the point of operator overloading。 And。

 So some types have some operators overloaded。 Some types have all of them right。

 Like you can't sum two vectors together， but you can sum two it。 You can sum two strings。

 You can't times equal a string。 I don't think maybe you can。 maybe you can。 I don't know。Tried it。

 I know you can in Python， but I don't know if you cant see plus plus probably not。 B yeah。

 you get the point。嗯。I'm just going to move on from this and we might have to cycle back to some of the questions。

 but the reason I want to start with this example is I've thrown all the concepts at you at once so you get why we're doing this and why it's cool and now we're going to go through the details and talk about friends and talk about the different operators but that's all this is about and this is a big part of your second assignment which again I will release tonight。

It's already， I just have to hit deploy after the lecture。So operator overloading。

A bit of a formality just to get through this slide。All operator overloads。

 one of the parameters is a thing of its type， So that means that like the addition operator overload。

 the output stream operator overload， all of these。

 at least one of the parameters in the overload functions will be the same type the benefit。

Of all this is that you can reuse existing code semantics and you don't have to like document stuff。

 right， Like a plus means a plus an output means an output。

 like it all means something to people already。 You're boots strapping off semantics right Now it sounds cool。

 it's two big words that I probably didn't know a few years ago。

 but the only downside of it is that sometimes you lose some context on operations。 So， for instance。

 like。Maybe addition for a point might not be obvious to someone what it does。

 someone who doesn't have a math background， they're like what happens if I add two Cartesian points like you have to go looking for the documentation。

But generally there's not many disadvantages， the one thing you have to keep very close eye on though is that you should only create an overload if your type has a single obvious meaning to an operator and what that means is that。

If you。Like。You know they talk about the pub test and things like that。

 it's like if you overload something like a plus or a minus or a times you' an equal。

If you don't think it is completely common sense。What that operator overload does。

 then you shouldn't do it。 You should go and make your own function for it。

 So the aim here isn't to remove all custom functions。

 The point is if your custom function is demonstrating a behavior that is exactly the same。

As what someone would expect if you just said add two points together， right or if you had。You know。

 like like a word， like if you' had a word letter class， you're probably not gonna overload much。

You can't add two word letters together。 Like what like you're not gonna to times two word letters together。

 So just be careful that everything you do has a clearly defined semantic。 Now。

 this friend's slide is a little bit thick。 Christstabella patted this out last year。



![](img/52d03b547472f794a9e3ad7b22d66390_18.png)

But。And this won't make a lot of sense to sum， but essentially。

 you have to really think back to your basic understanding of class theory to understand。

You know what。A friend is on what the key word means but。Essentially。

 you know that when you define a method for a class or an object。

That you have a notion of a this property。Okay， so what's an example like if I let's take my friend class my point class here。

 if I had a function here that was like I wanted to scale the point right so maybe you have a Cartesian point23 on a graph。

Like graph paper and you want to scale it like multiply the x and the y coordinate by2。

 I don't know what that's called。 I did algebra like seven years ago。

 but let's say I have a function called scale， which is void。

 All it does is gonna to scale it and it's just going to take in an n called you know factor。

 How much you're going to scale it by and all this is going to do is it's just going to go the X coordinates multiplied by the factor and the Y coordinates multiplied by the factor right very straightforward function。

嗯。And then you might just decide to use that one。 Now， this went't。 I have to un comment this。

 You know， and you could try and do this here。 You could say I'm gonna scale 。1 like this。

 Do I say scale， I think it was by4， say。6 and 11， right， so this will now operate on this object。

Essentially。嗯。We learned this last week is that sometimes you have methods that are tied to the object itself that operate on the exact object。

You're calling， so you say like object dot function。

 and then sometimes you have a function like a static function that doesn't actually operate on the object itself。

 It might take in objects。 So consider this for a second。

 there is a very big difference between saying P1 dot add P2。And auto P3 equals。Point。Add P1， P2。

 like this。Because in the second case here， you're essentially doing something static。

 The actual function itself isn't working on an object。

 sure it's taking in point types and point objects， but it's not working on like itself。

 There's no dot something。 So basically。For。For classes， if you have a static。

 like a static is style member that you want to define globally that。

Just doesn't really operate on like the object itself。

 Then that's when it that's kind of when we start getting into like the friends category because you'll notice this with these two operators here and you'll see this in the later examples if this doesn't make sense。

 is that。This operator plus here does not work on the this object doll。 right。

 There is no X underscore or Y underscore of like this object。 It's basically just a global function。

 In fact， I could， I could define this here。Right， just as a global function in theory。

It's just up a plus， which takes in a point and another point that returns another point。

 Does it need to be part of the class。 It could just be a global function and in fact。

I might even be able to make it one。 I might be able to show you this really quick。

 and hopefully this will really drive home the point。That we're trying to make with friends。

 Let me see if this works。 This is impromptu。See how this still works。

 I even' even defined it in the class。 I've literally just written a global like function called operator Plus that takes in these two things and it works。

 There's a four there so I'm not sure why it works。

 Maybe I compiled it before I wrote that for but's hope that's the case。🤢，But。

So there's a bunch of operators like plus and minus and multiplication and output operator that are actually just global functions。

 so all of the output operators for output streams and strings， output streams and points。

 output streams and ints all of these are actually just global functions。

 they're not scoped inside the class they're not you know it's not point colon and colon operator or whatever right it's not dis。

😊，It's not a static function。 It's literally just a global function。

It's not in the class scope and the slightest， totally separate。嗯。However。A problem you run into。

With this kind of approach， which is how operators work。

Is that what happens if as part of your operator plus， you want to access private members。

Because right now this is fine because look at how I'm adding them together I'm kind of using the classes' interface。

 I'm using the classes's API to get what I want， but if I want to say for some reason maybe the API doesn't give me what I want。

 maybe to add two things together I need to go I need to break the abstraction and actually go get some more detail inside the class that would be pretty normal is when I try and do this what happens now is that the compiler。

Says。Sorry， but X is a private member of point， It's as if you're just trying to use it in the main function right like you know what it's like when you try and take a you print a private member it' just like you can't。

 sorry it's private like you're not in the scope we learned that last week if you're not inside the scope。

 you can't access the private things。So what a friend is。

A friend of a class is essentially a globally。Scoed function。

That is allowed to access the private members。Of any of those types that are passed in。

 So essentially， when I take this global function here， that's just a global function。

And I put it inside my class body， and I declare it as a friend of that body。Of that scope。

 the point scope。Now， that is saying to the compiler， hey。

 if this function tries to access a private member。Of type point。

 then you can let them do it because they're a friend now。Now， the last time， well two times ago。

 we taught this。 I don't think I'd。I think this part was in another lecture I。

I'mSure sure this is around the Internet a lot but you know I was at Matt Star said the old quote that's like do you ever forget what friends are。

 it's like friends are allowed to touch the private parts of other of another type or something like that I can't say it as poignantly as him and it's not strictly appropriate either but you kind of get the point everyone sits there and giggles a bit。

 but it's like it it's literally quite true though right it's like there are private parts of this public class。

And when you declare something as a friend， when you use the friend keyword on a particular global function。

 you are saying to this global function， you can touch the private parts， the private members。

 whatever of the actual type here that you've been friended in。Right， now。

 whichever way you w to remember， it's up to you， but it makes。Pretty straightforward sense。

 with that example， now I'm really stepping through this not longer than I normally would。

 because I think it's a very easily confused part is like what the hell is a friend。

 But just remember， certain operators。A global functions， other operators are class members。

 you'll see this comparison。The global functions， though。If they want to access private parts。

Of a particular class， they're operator overloading like a point， they need to be friend keyworded。

 keyworded inside the class。How do you know whether you should need。

 It should need to be a friend or not。 You'll kind of figure it out。

 You can trust me in that because it just won't work。

 The good thing about operator overloading is generally。If you've done it wrong， it won't compile。

Right， so it's， it's very easy to like。Figure out if you're doing it wrong because they just want to compile。

Okay， in terms of operator overload design， here are a handful of operators you can overload now。

This column in the middle of the operators。You've got input output stream。Plus minus times divide。

 you've got greater than less than greater， you know。

 all of these ones are relational and equality operators， you've got assignment。

You've got compound assignment。You've got subscript。

Increment decreementarrow O D reference call and suddenly types start to make sense， right。

 because you think about what a string is， you can't plus plus a string。 What does that mean。

 That means that a string has no operator overload for plus plus and minus minus。

 but a string did spend the time to operator overload subscript。

 They did spend the time to operator overload assignment， And I believe all of these。

I just don't remember some of them， you can't times and divide， and I know that。

 but I think you can plus and minus strings， I'm not sure。

I just don't keep everything off the top of my head。

 but obviously you can do IO with them with input and output streams， right？

These are all the kind of different types of operators that we're mainly concerned within the course。

 And then some of these are member operators and some of these are friends。 Now。

 it's pretty easy to remember which ones are the friends and which ones are the member operators because a friend operator will take in。

Two different things， two different objects of that type and do something with it。A。

Member operator will use itself and bring something else in。

So you think about what it means when you say like， you know， point P1 equals P2。

 it's P1 saying I want to redefine myself。As P2 and when you say subscript you're saying I'm going to get the subscript of myself and all of this。

 whereas when you look at the relational equality， arithmetic things。

 it's often like a static like function that takes in two things， I'm going to compare A to B。

 you know C to D and everything like that。This will start to make sense pretty quick if it hasn't Now Pin says。

 oh， we have to overload plus equals I thought we would have just overloaded plus now that's something we will talk about because you can actually do that。

 It's totally fine for。Operator overloads to bootstrap each other and what I mean by that is if you define less then。

You can define greater than as just the opposite of that。 Or if you define plus， then you can。

Sometimes just to， like， minus as summing。One thing in the negative version of another。

 stuff like that。 So there's definitely a lot of bootstrapping that goes on here。Now I don't。 Yeah。

 so we're going to get into the examples now。

![](img/52d03b547472f794a9e3ad7b22d66390_20.png)

But I'll just show you this quickly on Google。 That's not C plus plus。

I'm still not really happy about that STD thing that happened a couple of weeks ago。😊，Oh， it was。

 it was tragic。Ego， operator overloading。嗯。So there's actually a list of all the operator overloads here in C plus plus。

 some of them are super obscure。 and you're probably not gonna deal with them much。 You know。

 plus minus times divide mod。I don't know what the name of that is。Poty hat。

Bit wise n bitwise or tilde n equals less you get the point。A bunch of them。

 you would never think about operator overloading。 And most some of these you'll never come across in your life。

 right， Excell。 Thank you。I was like， I'm pretty sure it's some kind of bit wise operator。

And some of them， like in what world， like and some of them， you'd be like。

 why would you ever compare things， right？ So for instance， in my entire life， I've never once。

 never once come across a scenario where I wanted to redefine what ending two types is。嗯。You know。

I guess you could if you needed to reduce them to a true false。

 perhaps that's probably the main thing。I'm not too sure。Someone they said。

 what the hell is output operator equals。I guess that would be reassigning an app I don't know。

 I mean， I kind of know what it is， I don't know why it is though。

 is probably is's probably like an app description。

 but yeah so these are all the different types now we're not going to be focusing on all of these types。



![](img/52d03b547472f794a9e3ad7b22d66390_22.png)

Okay， so now I'm going to run through a whole bunch of examples。Bitwise shift compounding。Oh， sure。

I thought it was something else。 I got it wrong。 So there's like。

 there's like a bunch of slides here， right， And this is all today's about。 We got one to。😊，3，4，5。

 I'm not counting， but it's， you know， it， it's a， it's a bunch。

 So we'll kind of run through these pretty quick。 So the first one is that we have input output with C plus plus Now。

 thankfully， this examples first， because we've kind of really done this a little bit in that first example that I dragged out quite a lot。

 And what this means is that we can define how a type。😊，Can be output streamed， essentially printed。

 maybe printed to terminal， printed to a file， printed to to disk printed to what was the same thing as file。

 But you get the point。 It's just streamed out to something， whatever that thing is。And。

We can also define the input operator as well if we'd like to。 Now。

 this is something we're gonna ask you to do in tutorials。

 So it's kind of like if I look up demo 403， it's like， okay。

 this makes sense because we're output streaming to。



![](img/52d03b547472f794a9e3ad7b22d66390_24.png)

This you can see if I try and build this one and run it。Should work。Oh， my god。Oh， it's。Yeah。

Sometimes some。I think the I think the lectures compiler still has a few extra checks on that I've disabled on some of your work。

嗯。I'm pretty sure I disabled most clang tidy stuff your in your reos。

 but I I think I might serve it enabled on lectures， but if we do 403 here，You see we print out12。

 we've done that already， it's a global function for youll notice is the class definition isn't here because I put it in a dot H file。

 so this kind of ties back into the week three stuff on class types where okay we have a class definition here。

😊，Which has a constructor defined。 It has two operator overloads declared and not defined here。

 and it has two private data members。 And these two。Operator overloads。

Need to be friends in this case because we're actually wanting to print out what the underlying data types are here。

 So you'll see here I've defined my output operator as you take a point。You print bracket X， comma。

 Y bracket。I could not get that X and Y。Without them being a friend。

 because unlike in the previous example here， there is no。What's not even here。

 It was in the other example。 I think， point1， There is no getters here。

 So I need it to be a friend because I need to access the private data members of the point itself。

 So pretty simple。 And if I wanted to read something， and I could just do standard C N。

Like this to point。 Now I'm pretty sure that's in the actual ch。

 So you can play around with that on the ch。 Pson says Fri is basically only used for class overloading。

 right， Look， you can use friends for other reasons。

 I just have never found a particular massive need for it。

 but I'm not gonna to lie my my my commercial use of C+ plus relatively narrower compared to some other languages I've worked with so。

Yeah， doesn't friends break encapsulation， though， Wouldn't it be better to use getters。So。

The short story here is that， and and I'll show you more of this later。

 But the short story is that when you define a friend。Typically， you do it。In the actual class body。

To avoid this kind of。You knowing drifting abstraction and what I mean by that is like I've separated these here mainly for demonstration purposes so that like people can understand。

 okay， this is actually just a global function that has been given special rights if you will here right so that's like it's a very literal understanding of what's happening but in reality and this is true for the assignment and what we expect of all of you in the assignment is you would actually pretty much be defining all these things here is we try and always keep friend definitions inside the actual class body itself。

And this is kind of strange because what's actually happening here is you're defining a global function inside your class body。

 it's just that that global function has special privileges to your types private data members。

 but because it's here， you're right Ka it kind of does break encapsulation。😊。

But only in a compiling sense， I guess。 But like the compiler doesn't care about encapsulation anyway。

 right， like encapsulation is like a。Concept for programmers。

 so this I think that solves that problem。Surush says。

 could you explain why operator functions are global again， Well， what I mean by that is that。

There is no scope。 It doesn't operate on an object。Like when you do this。

 you don't have to say like like if if I had a main function here， I don't have to say point。

Less than。Like I'm not saying point， okay。Let let me take a step back and I'll just show you that soap。

Just to demonstrate， this was still compiled totally fine。Im。Damn falls in the way。Did it go， okay。

Ipe I'm not in trouble。So slow so slow。Sam says for the initializerer list in the constructor。

 does that make the constructor a definition rather than a declaration？Yes， I mean， but it's。

 it's a mixture of the initialized list and this body here。 Both of those things need to be there。

 But yes， you're， you're essentially。Defining what the function does， not what it is。 And therefore。

 it makes it a definition。嗯。It should be fine in the HP if you also include the body， maybe it got。

Yeah， maybe got annoyed by that。 But so this， this program should still work here。嗯。

It just triple checking。 I did it， O。Fit，I'll show you this as well。 I can also do this。

I might get rid of this new line just for simplicity。



![](img/52d03b547472f794a9e3ad7b22d66390_26.png)

So these two things are same。 These two lines are exactly the same。

 It just so happens that the compiler。Has a bunch of rules which say if someone does this kind of thing。

 you're essentially just going to do this。 You're just going to call the operator output stream with those two parameters。

 So these two lines are equivalent。And my point is， someone says， like， well， why are they global。

 My point is that the operator output stream is not tied to point。

 You don't have to call the operator output stream inside the point scope。 It's not a static。

Function of a class。 It's not a member function of an object。 It is just a function。

That just operates on two things。 and one of them happens to be your type。 So when I say it's global。

 I just mean you don't need to scope this。 It just works。I'm going keep moving on。 So that's。

 that's essentially the I O stuff。 That one's super simple because we looked at it。 Now。

 we're actually going have a look at our first。Member uploadloads， uploadloads。

Our member operator overloads and what I mean by this is that these ones aren't friends。Okay。

 these are actual overloads of。Class of like a certain object operator。 So I have a point class here。

 And what that point class does is it constructs itself。 and then it has five key operators。

I wish you just focus on the first four for now， but the first four are。

Plus equals minus equals times equals divide equals。And essentially these make sense。

 it's like what happens if we plus equals or minus equals a particular point。Same class。

 same X and Y， and when we go to define these， again， these all follow a very similar pattern。

Which is that my operator plus equals。Takes in a reference to a constant point。

 and it returns a reference to a point。ButWhat this means is that if you're defining your own type。

Like a banana。You will it will say banana reference， banana， colon colon operator plus equals。

 banana， constant ampersan。B， p， whatever。It's very boiler platelate。

 That's what I mean about like we're kind of， it's very like this is the way you do it。

 This is the way you do the operator overloading。So what here you're doing is you're defining， okay。

 if Im a point and I would like to plus equal myself to another point。

 which means to take it and add it， and then that's your new assigned value。

 then I'm going to get myself here because X and Y are the objects data members It's operating on the this object like me this is an actual object here。

And I'm going to add the X and the Y。Component from another point that's passed in。

 So we could add this。 So I'm just going to progressively。

 I wonder if I've got the main function written here。Great， I do。 So I kind of have this。

alreadyready written out for us， which is great news。 just going to zoom out slightly， not too far。

That'll do。I know some of you don't have good internet， so you can't get 720p。So here I've got。

 like in my Compassign。h， I've got my class， I got my I've got a couple operators here which you can ignore the only one we really need is the less than operator because we need to actually you know。

I was just comment out the rest， but we only need the not the less than operator。

 the output stream operator because weve got plus equals， minus equals。

 and then we have how to print it out。So inside my actual comp I say okay well plus equals is just going to add the x and y minus equals is just going to subtract the x and y and then when I actually go to use it down here。

 I create 01。2 and then I can plus equals them together。

 I can minus equals them together and in this case I can times equal them with a number and you'll notice that my times equal with a number here is a very similar thing it's just that it doesn't take in another point it takes in a number。

And I could do that for an in， I could do that for a double， I could do that for a char。

 I could make as many of these as I want， you make as many as you can until they don't make sense。

And then I say that my new point is this， which I'm going to comment out for now。

 and we're just going to print this one， like run this one and print this one。嗯。

And you say this works， 100， 200， I printed out my point。

So this thing has nothing to do with friends。The reason is because look at how these operators are different。

 I am actually like when I do P1 plus equals P2， I'm not taking in two separate things and producing a new result。

One of those things is actually something I'm modifying。 It's actually like a this object。

 So P1 here has been operated on P1 is like the center of the universe and your plus equals P2 P2 plus equaling P22 it。

U so。😊，That's why it's written like this， because it's a member function。

 It's just like a normal like。Function in a class。 It's not static。 It's not global with a friend。

 It's just a normal class function。 P Sim says so we can still access private members of the argument with the supply for any class or just the same class。

 So in this case， we can access privates。Because it's the same scope Now what did we learn about classes last week？

You can access。The private。Fields， data members of any class you see in scope or anything you're in scope of。

 So this function here is actually defined inside the point scope inside the scope of the point。

 the class point。And therefore you can access private data members of both yourself and of things that are passed in。

 these are the same rules other OO languages like Java and stuff you cannot access the private members of some other random class unless you're a friend but that gets complicated。

 but the point is here you don't need any friend or whatever because it's just a member of that class type。

Yeah。Fairly straightforward principle。 I the object。Want to take another object and add it to me。

Joel says， would you actually put that in the dot H file， That's an excellent question。

 so I'll spell out the rules for you really quickly。RightAnd really clearly on the dot H stuff。

And like whether you put it in the function， like do you put it here or do you put it separate。

 So essentially。By default， you put everything in the DH， right so that's the place you start。

 you always start with that。So you put everything in the dot H。

 and then you ask yourself a simple question。Is this function definition non trivial， Like。

 is it more than a few lines， and is it not a friend。And if the answer to those two questions is yes。

 you'd probably move it out。So friends for the sake of this course will always define inside of our dot H no matter how big they are。

 generally they're not very big， like the nature of friends tend to be operator overloads which tend not to be that complicated so all of our friends go inside the dot H file small or big and then when we look at all the other methods。

Like all the other member functions， like operator plus equals and stuff。

You'd probably put it there unless it's more than a couple lines of code because， you know。

 things like this are pretty easy to read like this is a simple function。

These are simple functions I've mainly separated them again justca when I write lecture slides I try not to do everything the sameca otherwise like it's like a little bit more consistent for students sure but then they don't understand like the levers you can pull and like what like how elastic something is so I prefer just to give some different examples and make really clear what is。

😊，And then static functions don't ever exist inside the class body， I don't。Do that。 You No。

 they can't。 I'm not sure。 I don't think they do。 but generally， you've probably。I don't know。

 You definitely define static data members out of it， but。Static doesn't really matter。

 Shortt answer is little functions in the body， big functions out of the body。

 all friends in the body， no matter what。Yes， that's compound assignment。 Now。

 the cool thing is you'll notice here that you can do multiple things like we did this in here。

 So remember the compiler is just like function overloading。 The compiler will look at this and say。

 okay， different parameters， different function， totally different function。

 And it will let you do it。 So this here is like one of those scalar things。

 This is basically what we did before。😊，Except instead of the scale function。Think I did it here。

 right， or was it here， I wrote the scale function instead of scale where someone has to be like。

 what the hell the scale mean， And they have to go look up the documentation。

 we make say we make the judgment that， you know what。Taking a point。And multiplying it by two。

Is a really clear mathematical understanding。 So we're just going to override plus the times equals here。

And then like bam， done。嗯。Should you override times。And divide。A。Maybe。Maybe not。A。

It really depends on the type you have。 So some types make sense to multiply。

 Some types don't make sense to multiply。 If your type doesn't make sense to multiply。

Then you shouldn't have a multiplication thing。And if the multiplication is really not trivial。

 like it's like a dot product or something that just doesn't really make sense as like like if you just wrote down again on a piece of paper。

 vector 1 times vector 2， that doesn't make any sense， maybe you could give it a meaning。

 but it's not intuitive and since it's not intuitive， you might not function overload it。

Probably just the last point here， which I guess this will come up in the other slides。No。

 it's not gonna。 The last point here， I'll just， I'll just run through this and we'll take a quick break is that。

When you're doing a plus operator or a minus operator。Actually， let me just show you this。

 So someone asked before， does that mean we have to define plus equals and plus separately。

 And it's like， no， you can actually use them。 So I， I'll show you here。

 I'm going to define my operator plus。 Now， we kind of did this in the。

Previous example right at the start。Do you remember here where we。

Where we defined our own plus operator。 So I'm going to do the same thing here。

 I'm going to say friend。Point operator plus。And then I'll do point con reference， LHS。

 point con reference， RHS like this。Now， in this case here。How can I do this？ Well。

 I could actually say， for instance， I could say auto。P equals。How would you say it， new point。

 What do we do here。that was working on itself so let's say we create a new point that's like empty like there's a few different ways you can do this I'm just keeping it really simple。

😊，Oh， sorry， auto P equals LHS plus RHS。 Now， this doesn't make this。

 You could define this like totally。 in fact， let me just。See how we've like， I'm mincing my words。

See how how we've actually already defined what plus means。Here。

 we don't want to redefine that again， we don't want to do these two operations again because that just makes your code more brittle because you've got two definitions of the same thing in different places。

So ideally here， we would say something like P1 equals LHS。Which is gonna be a。Copy。好的。Right。

 because of copy semantics and C plus plus。 And then we could say return， or we could just say。

P plus equals RHS return P Now this is not my favorite implementation of this just off the top of my head。

 I think I've forgotten something tiny， which is very normal。 but you kind of get the point here。

 I'm not actually redefining here in this function what the behavior of adding two points is here。

 I'm reusing the definition of operator plus equals。

So I've defined what plus equals means and here I would like to reuse that like this Now this probably won't compile because I probably made some kind of trivial mistake but we could try it out。

 I could try printing out P1 plus P2 here。For it for。Perfect。Okay， that works。 and then。

It added them together， right， because we're， we're bootstrapping。 We're reusing the same。

 same kind of。Commands， the commands functions。 the only thing to be aware of。

 And this is really important。 This is something that someone else pointed out to me previously。

 is that。The the scale。The scale， the what scalar multiplication that we wrote here。

 This one is really easy when you have a。Something like this because you just say PP1 times 100。

Times equals 100 right， but here's a problem。The problem is you might say okay， well。

 I'm going to stand at C P1 times 100 now and you think， okay， that makes sense。 well。

 I need to operator overload times now because this is times equals。 It's a different operator。

 It's a member operator overload， not a friend operator overload。 So I come down here and I do this。

 I say yep。There it is。 I've got my。 It's a friend， because it's。It doesn't operate on itself。

Operated times takes in a point and a scalar and then it multiplies the x and the y by the scalar and it returns a new point there。

 which makes sense because you have to construct a new point because a lot of these things take in two things and produce something new and then I go and I compile and run that 404 should work fine。

But。The problem is， what happens if I swap these around？Now you might think that the compiler。

Is smart enough to figure this out for you， right？ It's smart enough to look at this and say， well。

 I know how to multiply P1 by 100， so therefore I must know the other one， but it isn't。

 It says invalid operates the binary expression。Binary expression is like， you know， two expression。

 two items and it's like I had to't know how to do that。 So you actually have to help it out here。

 You actually might have。 you actually have to say something like this。So you say。

 I'm going to create a new operator overload with different parameters， right。

 becauseuse remember every。You can redefine the same function with different parameters。

 that's what a function overload is。Except I'm going to swap these around and then I'm just going to define it as like the other way around。

And again， you might think what's the point of this。 Well。

 the point of this is there's lots of types out there where you it's not is it associative or communative。

 I'm not a mathematician， but it's like one of those words that's like。

 you know A plus B is not the same as B plus A， And this is true for divide right。

 Like A plus B and B plus A the same thing， but a divided by B and B divided by a at different things。

Commutative。 Yeah， so in this case， multiplication isn't might not be commutative。

 It might not make sense， but in this case， it might。 So you might do something like that。嗯。

And this makes sense because like you don't want the compiler just to assume that this makes any sense。

Otherwise， that's what it would do。 Like， you'd define the output stream and the compiler would be like。

 you know， let's just swap these around。 see what happens。 It doesn't。 That doesn't make any sense。

 You can't out。 You can't take the output stream and。Output stream up to a point。

 It just doesn't make any sense， so。That's kind of all the all those things there and something to keep in mind when it comes to those assignment ones is that。



![](img/52d03b547472f794a9e3ad7b22d66390_28.png)

These are generally the pairings。 So Chris helped write this table out， which is like， you know。

 if you define plus， then。You should try and define the commutator。

 I don't know what you call it the swapppy you do do plus。If you define minus。

 you should already have plus defined。And if you have， you know， divide。

 you should already have times defined。 And if you define modulus。

 you should already have divide defined。Plus， you， you get the point。

 so we'll talk through some of these， but。嗯。This is just a general table。

 if you ever can kind of be like， oh， I feel like I might be missing something。

 So that's just some guidance。 Now， we're gonna take a five minute break because it's 7 o'clock and。

Keep going， so。Take a break。 We'll be back soon。And finish off operator over load。

Moving on from where we were after the break now the rest of what we're going through today should be largely self-explanatory in terms of like if you look at theal irrational relational and equality operator they follow very similar rules Now relational and equality operations。

 So relational is like less than greater than less than or equal to greater than or equal to anequality are all friends because they take in two things and they produce a new result。

 which is typically a true or a false but what's really interesting about relational。

 it's actually kind of new about it to all of you will be or not new。

 but like this reinforces the point of bootstrapping So for instance。

 I'm going to define my operator equals equals。

![](img/52d03b547472f794a9e3ad7b22d66390_30.png)

嗯。As。Checking if the x and the y are the same and if the x and the y are the same。They're equal。

Then I'm going to define my n equals as not the return value。 if they're equal， right。

 So I've only had to actually， you know。Define one kind of rule there。And then when I do less than。

 this one's pretty interestingca， you know， you have to define it explicitly right。 Yeah。

 X1 is less than next。The x1 is less than x2 and y1 is less than y2。

 but then when we do less than or equal to。嗯。Set the right way round anyway， let me just。Yeah。

 so some of these are really interestingca like， for instance。

 when you say like operated greater than。 So if I want to check if P1 is greater than P2。

 I can just flip those around and say， well， that's the exact same as if P2 is less than P1。

 So I've just swapped the two parameters around but reus the less then And then for the less than or equal to and the greater than or equal to I've done very similar things here except。

😊，I have。It's like， like a donut。Explain this from first principles。

 hopefully you get it or you can look at it later and get it， but it's like。

Either P1 is less than P2。Or。This is the tricky part with this is taking into account the zero case because you can't just say like you know less than or equal to is like P2 is less than p1 because that doesn't take into account the equal case。

 so this is essentially saying that if P1 is always less than or equal to P2 if。

It's not true that P2 is less than P1 and again you can write this down with numbers and stuff。

 I don't want to go through it for minutes on end， but the point is we've only actually had to make two definitions。

 two clear definitions here， which is a quality and less than。

 and everything else is essentially again bootstrapped。

hich is really useful now there's some other things to do with the spaceship operator。

 this is a C++ 20 feature where essentially instead of like defining everything we've done here。

 you can actually use a new operator that was introduced which is down。Wait， where is it。

 Did I just go past it。Oh， yes， right here。 where essentially you can just like define a single operator。

And it makes it easier to define。 It， makes it easier to avoid boilerplate code。

 I don't think the resources on the Internet for this topic are。

They definitely weren't there last year， so I kind of regretted teaching it because it confused a lot of students because it wasn't well resourced。

It's probably a bit better this year， and it probably will come into the course core next year。

 But for the meantime， it's very much like this is a cool thing you can use。

 but no one's really expected to use it。 That's kind of true for a lot of C plus plus 20 things。

 to be honest。 But yeah， the point is we have relational and quality operators。

 We also have assignment operator overloads。 These are very similar to compound assignments。

 If you want to assign another point to be。

![](img/52d03b547472f794a9e3ad7b22d66390_32.png)

![](img/52d03b547472f794a9e3ad7b22d66390_33.png)

The same as your point。Then the overload is kind of the same thing。 Now。

 what's the difference between the operator equals and the operator plus equals。

 Not much Like if you look at the operator plus equals， the only difference was the operator。



![](img/52d03b547472f794a9e3ad7b22d66390_35.png)

I don't have the it's not in the slides， but the operator plus equals here。



![](img/52d03b547472f794a9e3ad7b22d66390_37.png)

Just had this。 And it was just plus equals。 So it essentially like me the point。

The plus equals was like I'm going to go get that point and add it on top of me。

The assignment 1 simply says。

![](img/52d03b547472f794a9e3ad7b22d66390_39.png)

I'm going to go get that other point。And make me be equal to it。 So it's a identical kind of thing。

 You'll also notice one weird behaviour that I kind of glossed over just before is。

This like return star this thing。 Now， this is a little bit weird because of how we tell you that we want you to avoid overall pointers in this course。

 but essentially。This is appointed to the object。And often， at the end of a lot of。

Member operator overloads like you know， plus equals or a minus equals or something。

When they return the object itself。You often will return star this。

 which is basically just a way of saying the actual about like this this object。

 not appointed to this object for this object itself， it's not a copy。

 you're not returning a copy because the return type is a reference。

So the compiler basically sees this and is like， a， okay。

 you just want me to return a reference to that same type。And this。

 this makes sense because this is kind of how you end up with these behaviours like。



![](img/52d03b547472f794a9e3ad7b22d66390_41.png)

嗯。I don't have a main function here。 but oh， that's'cause I'm in a dot H file， but that's okay。

 That's how you end up with these behaviors like int a equals。B equals C kind of thing。

 or like if you're in like in B equals1 in C equals2， like B equals C will assign C to B。

 but then it will what it will return B。 That's the return value of that operator。

So that's kind of why we return ourselves because that's just a standard。You know。

 kind of standard semantic。 You can't just return this because this is a pointer to the object that you're working on。

 So this is the same as Java。 It's a， I mean in Java， everything's a reference。

 but it's it's a pointer。 So this is an actual pointer in memory。 So if you return this。

 you would have to return a typethe。Point。Yeah， point star。Because that would be the type。

 And that just kind of goes against you know， that wouldn't。

 that wouldn't fit with the C plus plus standard and expectations。 that wouldn't be useful。

 That would be potentially dangerous。 There'd be very few cost benefits， cost improvements to that。

 so。That's why it's。That's why it's dereferences， it's a little bit ugly， you know。

I didn't make the rules。 that being said， if I did make the rules。

 they'd probably be even worse than this。 So let's be glad for that。 De reference this。



![](img/52d03b547472f794a9e3ad7b22d66390_43.png)

Yep。Stop me at any time， by the way， I mean， I actually think these slides are probably。

Some of the few slides in the course I could just give you like we could have stopped 20 minutes 30 minutes ago and just been like good luck。

 but so I'm just kind of glossing through them a bit and getting to the harder parts So this is an example of actually one of the harder parts and the reason for that is because this is where we start getting into double definitions which I think is very relevant for the assignment So the subscript operator Now we have this file here。



![](img/52d03b547472f794a9e3ad7b22d66390_45.png)

Subscript dot H， which。I should probably make a dot C file for it。But。

Let me actually change this to a I' do some let's do some random sea make。

 I'm going to change this to 407 subscript。cP。And I'm going to go to my CMake list file。

 and I'm going to actually add it。 Now we normally don't add dot H files here。

 so I'm just going to add another executable。407 subscript。I'll reload the window。

And now I can compile and run it。 Now， it isn't executable， So it needs a main function。

So I will need a main function。And that main function will need to create a point。Autto P equals。

Point1，2 like that。 And what we want to be able to do is we want to be able to print out P0 like this and P1。

 So this isn't this is not a great。 This is not my favorite example of subscripting because。Like。

 sure， this behaves like a tuple or something where it's like0 and one of the two indexes。

 But generally， I don't think you should be subsscripting for things that aren't list types。

 You know， like unbounded list types。 but this this is a neat little example。 So this should work。

 I can't remember if this is something I have to work on work with you on。 I do need to include。

Highre stream。But this one should。血主。I'm just compiling this， right。 So one and 2。 So it。

 it does what I want， which is to like 0 is x and 1 is y。 Now， the way this works。

 forget the second thing here for a second。 The way this works is that。Essentially。

When you call operator。With the subscript brackets。This， this， this。

 this is the function that's called when I do this。 So when I say p0。Like that。

 What C plus plus does is it says， oh， you wanna do the。

You want to do the subscript operator on P with an index 0。 So those two things are the same。

 That's what ends up being called。 essentially。 So I have to define that。

 And the behavior is pretty simple。 It's like， okay， well they're going to pass in an I。

 And if I is 0， then we return X。 and if I is1。嗯。If I' is 1， then we return y。

We're going to put an assert in here now you don't have to do this， of course。

 because like like what do we tell you about？Subscript operators is that they don't do checks。

 So that's kind of the behavior of subscript operators is that we're not doing any exception checking here。

 it's like if someone gives us a two。What's going to happen， We're going to give them the why。

 That's what you might call undefined behaviour。 Now， clearly。

 it's defined because I just defined it for you。 But it's like。

When you give this to a consumer of your library。You give them rules。

 which is like it has to be a valid index。 I'm not going to check it for you。

 That's a performance hit。If you don't do it properly。

 I can't guarantee you what kind of behaviour is going to be exhibited。Now。Here's the weird thing。

If I just define this。This kind of works fine。 I can print it， and I can also， yeah。

 I can print it and I can modify it。 I could say P 0 equals 3。And the reason I can do this。

 which should also make sense is because， well， P0。

 the subscript operator returns a reference to an end。So。And， and just to be clear。

 the interior is could be any type。 this， This will be different types so different。Data structures。

 it's actually this part that's pretty consistent。 So it's like the subscript operator will always be like。

Reference to operator reference to return operator Subscript in I because Is an index， right。

 It's an int。 It could probably be an unsigned in。I don't know。

 I don't know the restrictions of that， but it does return an in type。

 this could be a double that's up to you， there's no standard for it， but it returns a reference。

 that's what a noncons subscript operator returns。And。O， someone said。

Does't that break the fact that x is private？Yes。I guess。No。I don't know， I mean。

 I get what you're saying。But I don't think that's any really different to like。

Some of the behaviors you would have seen with unordered sets and stuff。嗯。I mean I guess literally。

 but again， the point of encapsulation is not to the compiler to be separated。

 the point is for the programmer to be separated。The point is that you， as a programmer。

 should be operating on an interface that isn't interested about how that X is stored。

 or how it came about。Even though， of course， the compiler will literally working with that。 So no。

 I don't think it's a problem。 But here's， here's the actual problem。 Now。

 let's see what happens when I try and make this say。Const， right。 So now my point is gonna be const。

Now， naturally， this isn't going to work。Right， if I。Subscript。This might work， right。

 causeuse it'd be like， oh what the you know， like， what the hell is this， so。

That way like dysfunction。Method is not marked as cons now what did we learned last week？

For a function to be called。By a const object， it has to be const qualified like this。

 It has to be a const member function。This says to the compiler I will not modify anything tick。And。

I will。Allow myself to be called on constant objects。 So we try and do this one now。40，7。

 I think this works for memory。 No， it doesn't。Great， well， I hope it didn't work。😊，Now。

This is problematic because the compiler now is kind of like。

This isn't good because it's like I can't like you're a constant object。

 I can't return you a non constant reference to me。🤢，Cause you might modify me。

 You might try and do this like。That's not。 that's just like not good rules， right。

 Like you don't want to have a constant object returning a mutable reference to to something internally。

 That's not how it works。 So this is actually one of the first examples you'll come across where you need to define a second。

Second function of the same kind of operator in the same parameters， but with different cons。嗯。

So Kaai said， can we just change the return type to int， so Kai's asked a good question here。

 which is can we just do this， can we just say int con reference now you can this will work if you comment out this line here。

Sure this will actually work and compile but the problem is now you don't actually have a function for non cons points to be mutable。

So now if I want to create a point that's not constant。

 I can't mutate it because I have no function that returns me like a mutable reference。

 Like it only returns me like reference to constants。

 So that's actually why we need to because there are just two different use cases here。 Now。

 this is one of those examples where sometimes you're just going to have to write the same code twice。

That's okay。 That happens sometimes and this could also be a constant int reference both as fine In a constant reference is totally fine。

 There's no performance difference in this case， well there's a little bit but not in the way you'd think because the int so small。

 but it was a bigger type then yet you'd probably want to maybe return a reference constant reference。

 but now this will work because for constant objects， you get a。Maybe it does really want it。Oh。

 wait， oop， maybe that wasn't the problem， sorry。I was like。

 I think I didn't think I had a problem with that。It does。Oh， it's'cause they still have that there。

 Y， so this will work now。 So in this case， it's like you have a function to deal with the con object and you have a function to deal with the non cons object。



![](img/52d03b547472f794a9e3ad7b22d66390_47.png)

Yeah。Okay。Main takeaway from this is constant。

![](img/52d03b547472f794a9e3ad7b22d66390_49.png)

Member functions， generally speaking， this will be true for your assignment。

Some operator overloads will only have a non con version。Such as assignment operator。

 How do you have a constant assignment operator， You can't。 Does it make sense。

You can't have something that can't mutate an object assigned to it。Some things would just be cons。A。

I can't think of any examples off the top of my head though I feel like there's one。Anyway。

 or maybe not。 don'tno。 And then some things will be both。

 Some things will be both in circumstances where you don't need to。

And this is only for member functions， not friends， friends。Friends don't really make sense。

 like you can't really have a consquified friend function because the idea of Kantt functions only applies to classes that's why they were talked about in week three because the con says that you can't modify this object but that doesn't make sense for global variables because global variables don't have a sense of state。

 they don't really have an object。Okay， how much I got left increment， increment，2，3，4。

5 will be fine。Okay， so increment decrement。This is an example I wrote。When I was thinking about。

Driving across the country。But before we got to that， the Arord says。

 would it be bad C++ practice to overload the subscript instead of adding a member function？

In this case， I think it would be better at a member function because。

I don't think subscript operators are great on things that aren't less。Because。

X and Y aren't literally ordered。That's just how we display it。You know。

 there's no like inherent kind of universal meaning that it's ordered。So yeah。

 I wouldn' I probably wouldn't use the subscript operator here。嗯。

Operator less than operator output stream is not an example of a cons member function。

 So just to be clear， the cons qualifiedness of things。Can only happen on member functions。

 So there's no such thing as like a cont qualified any of these because they're all friends。

 They're all global functions with like friend。Semi access scope。嗯。

F Pyn says you could subscript string too。 Yes， you could subscript string。

 and that makes sense because string is a list。 It's an ordered list of characters。Take it。

 Sounds good。呃，呀。And yeah， so。Queen John says， how about first and second li in pairs？Yeah， exactly。

For something like a point it's basically a pair， you do something like first and second。

 which is just a lot clearer。 It's just this was a really easy example that I think demonstrates the point without getting too complex or writing like a dynamicist structure。

 so I just say you know。You get the principles， maybe you wouldn't quite do this one。

Increment decrement now increment。Dcrment are pretty straightforward。

 They are obviously member functions because you're operating on yourself。

 you say I plus plus you modify the I。嗯。And there's plus plus I。

 I plus plus and then minus minus I and minus minus now。

I've omted the minus minus from these examples here because it's totally the same， right。

 It's like plus equals minus equals。 I didn't even need to show you that you would have figured it out pretty easy。

 You just replace the pluses with the minuses and everything is fairly consistent。Now。嗯。What。

Is important there' is a difference between prefix and postfix， which is what this example is about。

So prefix increment is where you do++ x and postfi increment is where you do x plus+。

We're going to learn more about some of the stuff in week five。

 but essentially you might have learned this from other language。

 other parts of courses is that a prefix operator。Increments the value， and then returns it。

A post fixed operator value。Returns， boy it。Kind of returns the value then increments it。

 not literally because a processor can't do that， but essentially if we look at like an example like this。

If I was to say auto I equals three。And I was to say。

 in j equals I plus plus j is going to be equal to 3 because the the I value is captured and then it is incremented。

 So after this j is 3 and I is 4 like that。But if I did I minus， if I did plus plus I。

 it's incremented and then captured。 So in this case， J would be 4 and I would be 4。So。

Plus plus I and I plus plus two separate operators。And。Plus plus I is generally a little bit quicker。

Because you're not actually trying to copy anything。 And you can actually see this in the code here。

 So if I look at the code。I've got myself a class called Road positionition。

 it has a uniform initialized that essentially so what this class is。

 is this is a position from kilometers from Sydney。

So like let's say that you're driving from Melbourne to Sydney and you initialize this class with like  a thousand kilometers。

 which is roughly how far away Sydney is from Melbourne then what happens is every time you drive a kilometer you're going to do a plus plus you're going to increment yourself's kind of like a state machine and you keep track of the number of kilometers from Sydney。

That's all the classes， it's basically like a tick class。These two functions down here， though。

 are the two。Increment， like pre increment and post increment。 Now， which one is which。

It's a little bit weird。And I don't really know why the C plus plus language is defined like this。

 but they're both operator plus plus， it's not plus plus operator。 It's operator plus plus。

The reason for that makes sense is because every single operator overload and C++ starts with the keyword operator。

 that's probably easier for the compiler。不然。What distinguishes。Prefix and postfix。Increment。

Is whether there's an in as a parameter or not。 super weird， super random， I know。

 but it's like operator plus plus with no arguments is pre increment operator plus plus with with just an int definition is post increment。

 I assume this is just how the language was defined so that the compiler could figure it out。

 So what I mean by that is like if you。If you do something like this， if you say plus plus I。

 then what the compiler is going to do is it's going to call operator。パスパス。

Well it's going to call like int。It's gonna call J dot operator， plus， plus with。

No arguments like that。And if you do post increment， then it's going to do it like this。

 So that's kind of the two instances that happen now， a little bit strange。

 You also notice here that it's actually J dot operator plus plus and that's because it's a member function。

 So early on when I was like oh， by the way， operator plus like P1 and P2。That looks like that。

 because they were。Like globals and friends and stuff where as， by comparison。

 if I was doing plus equals， it would look like this。😊，The dot is kind of key here。

 it's a member function operating on an object， it's not some global function。Okay， so。

Should make sense。Pre and post。 What's the difference here， They both increase。 or they increase it。

 Oh， sorry， I meant， I meant to be driving away from Sydney， my bad。You are。

Increasing your ticking one， which is saying go another kilometer and then you're returning this in the first case。

 so it's like increment， then return the value， whereas in this case you're doing the standard temp thing。

 you're storing a temporary value。Incrementing it and then returning that temporary value that you captured before the increment。

Now， what's important to note here is that there is a copy that occurs right here。

This is copying the object that we're in to a totally new object。

 And then we're returning that totally new object。 So there is a performance hit because of that copy。

 I think in a lot of instances， compilers nowadays are probably smart enough to see that if you aren't。

Using the return value of a plus plus it'll actually make it a post increment for you。

 So I don't know。 I remember someone told me this once。

 but like if you say like4 and I equals0 I less than 5 and like I plus plus the compiler actually see that you' are doing nothing with this return value and it will just make it a plus plus I because it's like I'm not going to waste all that time copying。

But that's something to keep in mind， you'll also notice that the post fixed increment。

Doesn't return a reference， which makes sense， because like。You cant have it like this。

 it's kind of like a stack object。It doesn't exist， really。You know， like I， I can't。

Like I can say in J reference equals that， I can do this。J is just a reference to a plus plus I。

 which makes sense because I gets incremented from 3 to 4 and then。4， so it's now a pointing to I。

I can't say though， int reference。J equals I plus plus because the I。

 the thing that's returned is kind of like a temporary value， right， Like the。

 the I plus plus will capture the three， increment the I to 4， and then it'll give me the three。

 But it's not really an address anywhere。 We're going talk more about this next week， but。Yeah。

 it's kind of like a temporary variable。 You can't really return a reference to it。Yes， that's， yes。

 You got everything right on the。Post increment slower because the of value first。

 so the copying is what takes the time。嗯。7，40。 And we got。Coup of slides to go。

 I'm not going to talk about the spaceship operator。 These are some slides Chris put together。

They're really interesting， they're not required to be learned。

 it has a lot to do with strong ordering and weak ordering and stuff so I'm not going to talk about these today。

 though please feel free to go look at them。It'll just give you some point as as to what you want to go look at。

 So if you one of those people that's like super keen about， you know。

 learning everything about C plus plus， then I would encourage you to spend your time looking at this。

 But we're just gonna look at these last。Kind of two slides。

So this one's super important and it kind of leads into a topic we're going to talk about next week to do with smart pointers。

 but essentially， let's say for a second。And I shouldn't be doing this because you know we don't like using Malik and free in C++。

 but I'm doing it in this case where what's actually happening is that I'm creating a class called string pointer。

And what's happening is when this string point is created， my class contains a pointer to a string。

 Now， you're going to have to rely on some of your older scene knowledge here。

 because my class contains a pointer to a string。 And upon construction， I'm maliking it。

 So in C plus plus， we don't use malik and free。 we use new and delete。 same concept。

 just a little bit different syntax。 But what's happening here is I'm actually allocating memory on the heap。

 again， we talk more about this next week。 My destructor here。Is freeing that memory。

 which makes sense because my my object goes out of scope。I would like。My string to get deleted。

 the thing I'm mal， otherwise it's a memory leak。嗯。So this is what you will call。

 This is what you will call a resource encapsulation。Grappper。

 where what I'm really doing is I'm using C++s object lifetime rules here。To say， hey， the plus plus。

 I know that you're keeping track of when my object is created and when it goes out of scope。

 you're automatically calling my destruct。 That's really handy。

 I'm going to use that to mal something at the start and then free it at the end。

 So I don't have to worry about it。 So what's really cool about this is that when someone goes to use this string pointer。

What actually happens is they create a new string pointer。They give it some string。

I construct my class。 I Malic a new string with that string。

 And then it exists for this lifetime here。 And then once it goes out of scope on line 24。

 the destructor of my class is called， which frees it for me。 It's really cool idea。

 We're going to talk about the more advanced versions of these in week 5。 But the point is。

 when you make this rapper。😊，You're going to have to overload the D referenceence operator and some other operators as well because。



![](img/52d03b547472f794a9e3ad7b22d66390_51.png)

You're essentially making a string pointer wrapa。So instead of like。

 like what you might do if I just kind of quickly。my ear。it's zero zero hurt。

 probably not because you're not broken。Is。I could， I could kind of do this in a really ugly way。

 don't ever do this where I would say auto S equal standard string。Crarap pointo。In fact。

 I wouldn't even do that。 I would say standard string a pointer to a string is equal to a new string。

Now， this is syntax we haven't talked about in the course， but this is basically Malik。

 This is you maliking something。 And when you're done with it， you need to free it。

 So this is me malicking a string and then freeing a string immediately。Okay again。

 you don't have to overthink this， it's not really that important right now we talk more about it next week。

嗯。Yep， so I have to， I mall it and then free it。 And then if I want to do stuff in the middle， right。

 If I want to print out that string， I have to do that， I have to say， well， yeah。

 I have to dereence the pointer right to get the value。 and I want to print the value。

 And if I want to say get the size of that string。 If I want to say size。

 I have to say S size or alternatively， you know， star R dot size like that。

 I have to do one of those two things。嗯。But the problem is。

 when I wrap my pointer in this slight class here， my class。Has no sense of like。

D referenceence or anything，ca it's just a class。 It's like， I don't know what you want for me。

 So we have to go and overload those things。 And in this case。

 the overloads are really simple because when someone says， oh， can you de referenceence my class。

Like here， my string pointer class。 All I'm doing is actually saying， oh， you want to dereence me。

 I'm just gonna give you the pointer underneath。 So， you know， it's kind of like。Yeah， when。

 when someone wants to dereence it， I'm just like， and I'm just gonna de referenceence what I'm looking after。

 It's kind of like passing it through， right， Like it's， it's like a benign abstraction。

So someone tries to de reference string pointer， I just give them the result of de referencing the underlying pointer I'm managing as part of my class and similarly。

 when someone tries to do the dash arrow syntax I always forget what that's called where they expect a pointer。

Because that's kind of what the dash hour syntax。Does， as it returns a。Pointed to a string。

You just give them the underlying point as well。 So sometimes you'll end up using operator overloads for no other reason than just to like the sta operator for no other reason than to essentially like sometimes you use them just to expose things right so like say you have a class that's abstracting something and you just want to expose it a really classic example of this as you might remember from other another course you might have done where you create a set。

 say in Java I don't know if they still do this， but you might create a set in Java and。

You use an array list to store that set。And when someone says， oh， what's the size of the set。

 you just say or whatever the size of the array list is' because that's what's storing it。

 So it's kind of like a bit of a pass through。嗯。It's like a formality you know that you're exposing certain things in this certain abstract type。

And then last thing。

![](img/52d03b547472f794a9e3ad7b22d66390_53.png)

This 1 I don't want to talk about because it's not super interesting。

 I think it is in your assignment。 So， you know， maybe you can ask questions about it on the farm。

 but there's another operator。Which is a type conversion operator。 And this one's a bit hard to read。

 But what this really is saying here。Because this one looks a little bit different。

 is this one is saying this is the operator to convert my type。To as stand a vector of events。

So if I wanted to convert my point type， for instance， let me open this up in demo 410。

 if I wanted to convert my point type to a double somehow， not that that would make any sense。



![](img/52d03b547472f794a9e3ad7b22d66390_55.png)

I would do operator。Double like this。In the first case， I'm converting it to a vector， though。Now。

This member function is cons qualified， because。I'm happy to convert。Noncon points， con points。

 it's all the same I'm not mutating it so I might as well make it con so that it works and everything。

And then to convert it to a standard vector， I simply create a new standard vector and I give it x1 and y1。

Te， easy。So now like， okay， that makes sense， but how do I use it while using it quite straightforward if I was to create a cons point。

 you know in this case， and then I say I'm going to create a vector， I simply give it P here。

Like that。That's the proper way to do it。 That's an explicit type conversion。

 So I say autoveec is equal to a new standard vector event， except I give it type P。

 And what the compiler does is the compiler saysP' a point man。

I don't know how to convert that to a vector。 I'm gonna go look at P's class If P has anything to help me out。

 And then it's like， yeah oh， this is useful。 Okay， so P does have a way that they can convert to me。

 I'm going call that， and then it will return me that。That vector of ins and then great， Good to go。

 S， done， conversion done。I think you might also be able to do some things like this。

Is thatatic cost stand of vector int？That might also work， I guess。🤢。

But and then I think in the in an extreme case， you might be like， oh。

 I think there's some subtlety as well around this where。If I don't have this explicit here。

Then I think this works， let me quickly try this out。No member named at in point。哦。Sure， whatever。

Unused variable V。Yeahan。Bam， okay， so this works。 I'm not actually running the right thing。

 Let me just run the right thing。 It works。 It doesn't do anything， but it works。 Trust me。

 Otherwise， it wouldn't compile， but this is what we call an implicit conversion。Generally。

 when you do tight conversions， you will put an explicit out the front。

 and what do you remember about in explicit， that means that this function needs to be explicitly called。

Because what's actually happening here is it being implicitly called like。

 you're not actually saying here， convert this type。

You'll saying assign this point to this vector and the compile is having to figure out what you mean by that。

 whereas when I do this when I say stand a vector inch。

The right hand side is actually ends up being a standard vector events before it tries to assign it to the left。

 so remember that's the point of the explicit is explicit says that like no， no， no。

 you need to sort everything on the right hand side before you assign anything。呃。Oh， yeah， sorry。

 someone's right。 I really thank you for raising that point。😊，Qunyang says， yeah。

 it's still a pointca of the auto here。 So yeah， of course。

 the compile is gonna look at what's on the right hand side。 So I would need to actually say this。

 And maybe it won't work。 I don't normally do this。 I'm just playing around with you all。

 but I think this works。I have a vague memory of doing this once。 Yeah， so that still does work。

And then if I put the explicit there， it's going to complain。It's going to be like， oh no， no， no。

 no， no， no， no， no， don't do that。Yep， so no viable conversion for Kant's point to that。Yeah。

 so it's like it， it can't convert it on assignment。So it's like if you want this to happen。

 you will have to like， you know， either static cost it or。Do something like this。And then。

 this should work。Yep， so。Thank you for picking up on that Sam says why do you need to return costs are there any reason for you doing that？

I'm not returning const， remember the constant on the right hand side of the parentheses is whether the function is const qualified or not which means that。

It's all that kind stuff I talked about in the last lecture， the return typess all on the left。

And this function you don't specify the return type because the return type is what you're converting to。

 so it's like well the return type is clearly standard vector event。

 you're not going to convert it to a standard vector event then return something else。

 so that's why it's up。

![](img/52d03b547472f794a9e3ad7b22d66390_57.png)

That one's kind of cool， not really super useful， probably only really useful if you're trying to do like converting from from one type to a similar type like。

😊，A。Yeah。Like a forward linked list to a doubly linked list or something。

You wouldn't convert like an uned set to an a vector。It's just different things。 You know。

 let the let the person let the client do that。Sarch says。

 is there a runtime difference between implicit and explicit conversion？I don't think so。

 if there was， often the compile， I'd probably figure it out。嗯。It's mainly a programmer thing。

It's mainly just making it giving clarity to programmers。

There's a comment here about new function syntax。I've just basically， like， again。

 there is a new function syntax we can use for these things。 And this is what it looks like。

 I've just added this here。 So it's kind of clear what this looks like for operator overloading。

 This is just using the C plus plus 20 function syntax。 Again， we haven't enforced a specific thing。

 But if you're curious， you can go look at that slide， we have exactly。



![](img/52d03b547472f794a9e3ad7b22d66390_59.png)

呃。I have exactly five minutes left。 So I want a very。Fy。Quickly。Touch on assignment 2。

 I'm not going to read through the spec。 I'm not going to give you a brief history of anything I do just want to mainly highlight to you right now。

What you are expected to understand or what you can assume you have to figure out later。

 So first thing is。We just spent this lecture。Writing these different。

 we've written a point class and a bunch of operator overloads。

 Your assignment is writing a Euclidean vector class and a bunch of operator overloads。大致。

At the high level， you've got it done。 We're just writing a more complex point class with a whole bunch of different constructors and copy constructors and。

There's just a lot of things to implement。 This is a breadth assignment， right。

 Word letter was a depth assignment， One function， very complicated to solve。

 This assignment is many functions， a lot simpler things。 So it'll feel very different。

Very well prescribed。

![](img/52d03b547472f794a9e3ad7b22d66390_61.png)

All of this。The main things to take note of。Right， is that。



![](img/52d03b547472f794a9e3ad7b22d66390_63.png)

You will see。嗯。Most of this should make sense， some of the things that won't make sense are exceptions。

 which we're talking about tomorrow night， so you probably don't need to worry about that because we'll talk about exceptions that's tomorrow。

And there's actually not much to do with exceptions in this assignment at all。嗯。

And the other thing is this whole idea of a smart pointer。

And unique pointers and stuff which we will talk about next week。

 Now it's same as due at the the start of week seven。

 so it's due in three weeks And what I'm saying to you is that I just need seven days to have taught you everything there is to know about this。

Though in the meantime， the only thing that's probably going to elude you after tonight is what in God's name this whole unique pointer make pointer stuff is。

 and we've actually written this into the spec that says please note the theory for unique pointer will be covered in week five until that point there will be part of the assignment。

That you may struggle to implement。 However， before week 5。

 you' are able to implement many other functions。 That's because the unique pointer is very similar to a raw pointer。

 So what we mean by that is that。In your class。There is a line that says like that has a member function for magnitudes。

 which is some fancy doy dodoy data thing。But it's actually。

 you can think about it just like a primitive double array。嗯。Now。Part of this assignment。

We tell you that we don't want you dealing with raw CRs and raw pointers。

The reason isn't because they don't exist in C++， the reason is because library rid deal with them for you。

 so that their code is complex and your code is simple。

Part of this assignment is teaching you how to deal with some of these raw things。So that。

Other people can use your library without having to deal with all these ugly sea style。

Best like you know practices。So the point is you can basically treat this line as a raw primitive double array。

 Now， if you look at that and your eyes gloss over。

 it's probably because I've just shown it to you like that really quick。

 but it will make a lot of sense and you can post on the forum。

 The other thing I'd say is like sometimes students will say things to me like， ohh， blah blah bh。

I mean I wish we learn everything before the assignment started and it's like， well。

I can't help thatca it trimesters， but also we designed this in a way that like you could。

 you could wake up tomorrow night。You could start tomorrow night。 You could do 80% of this thing。

Without anything from week 5。Okay， there's absolutely nothing stopping you getting started， so。

If you're one of those people who wants to start early， don't sit around moping and being like。

 I haven't learn everything I need to know yet。 It's like。

 you know well more than enough to get this 80% done two weeks before it's due。

 And if you' one of those people who's doing 80% of it， two weeks before it's due。

 you're probably one of those people who like already knows this stuff or is extremely motivated and we'll just read ahead in the lectures and things。

 So I'm not too worried about anyone feeling。You know。Like their handicicapped or。 So yet started。

 make a good lot away。 Most of you aren't going to start till the weekend anyway。

 And then we'll finish off the rest of the content next week。

 But most of this is just operator overloading and exceptions。 That's 80% of this， promise。嗯。

Can you do it all in one night？So this assignment' is different from wordla。 it's nearly 8 o'clock。

 Im gonna have to wrap it up， but。Word letter。Was an easy assignment to understand a hard assignment to do。

Right like it's just lots of logic errors and stuff。This assignment is like。

 you just have to get the syntax。 I I could easily do this。

 I could easily do this assignment before I went to bed。Because I， I know what I'm doing right now。

 But the first time you would have shown me to this if I was a student。

 probably definitely not because I would have got stumped on some random operator or some random like。

I forget how subscript works。 And I will have to like go look up the docs or like。

 I'll you know what I mean， like it's a very boilerplate assignment。

 So what I mean by this is that for those who felt assignment1 was very stressful because you felt like you were getting like really algorithmically challenged。

 It it was a really deep problem。 This one is a lot more of a， you've just got。

20 small problems to solve。 So in a lot of ways， for most of you， it will feel。Slightly more boring。

 I guess。And for most of you， it'll feel。A little bit easier in a very general sense。

 though some things will be harder。 But you get the point。 So I。

 I don't think you need to worry too much。 It's a nice little assignment。

 I definitely start this weekend。You can chip away at it。You can just chip away at it。

 so start it early， just chip away at it， get rid of that stress。 It's getting released at 9 PMm。

 I just have to hit the release button on this。嗯。I'm my night person or a morning person。

 I don't know。I don't know。 I'll think about it。 Do we need to write tests。 Yes。

 it's the same model as assignment as assignment  one， same marking criteria。

 I will release it so you can read these read it yourself and we can chat about it a bit more tomorrow and。

Next week， as well。Yeah， anyway， I want to wrap up becauseuse I don't like taking taking people's time。

 So let's chat tomorrow if there's any lingering questions。 And thanks everyone for coming。

 and I'll see tomorrow or whenever you。😊，See whenever， so。Thanks again，80 people。

 and thanks for the sunset photos， those who sent sunset photos。 That was awesome。

 So have a great night。😊。

![](img/52d03b547472f794a9e3ad7b22d66390_65.png)