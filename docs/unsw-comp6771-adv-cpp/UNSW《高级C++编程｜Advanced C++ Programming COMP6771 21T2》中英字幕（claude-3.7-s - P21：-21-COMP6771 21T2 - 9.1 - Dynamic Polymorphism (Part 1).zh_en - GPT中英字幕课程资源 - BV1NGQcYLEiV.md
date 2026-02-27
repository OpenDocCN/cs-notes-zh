# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P21：-21-COMP6771 21T2 - 9.1 - Dynamic Polymorphism (Part 1).zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Nice to see you all Welcome to week9 I can definitely tell based on the attendance rates that everyone's starting to both get very tired of term and also get very into assignment  three so I hope you're all doing okay because I know it can be a very stressful time of term for everyone involved。

😊，They didn't really have any exciting news to tell you。It's just kind of like。Life， as always。

 We're going finish off our。Last major topic this week。Which I'll get to in a bit。

 And your assignments obviously due 7 days from now。 So and then then you're 70% through the course。

 which is something I think you should definitely reflect on because the exam for this course is gonna be quite light。

 I guess like not light like the exam will be hard， Like doesn't matter what percentage it is。

 but it's like it'll be lighter in terms of stress because like many of you will pass have passed the course。

 So the exam is really a question of what grade you get。

 but your life still goes on normally right So that's good news。 I like smaller exams。

 And it's something I'm trying to do more often。😊，In terms of assignment two marks。

 because that's a common question I'm gonna get from people。

 is when do I get my assignment two marks back， The answer is， hopefully Friday， we're intending to。

Release them on Friday。 We're probably like two third of the way through。 So they'll be out soonish。

 Gourt says any plans on extending the deadline for assignment 3。 No， not really。No， I mean。

 I hate that question is it makes me sound like an a hole when I answer that， but。No。

 is the short answer，ca it's it's well signpost。 And actually the older I get the more I kind of don't like extending deadlines because it's it's kind of a disservice to people that like plan their time。

IfThat makes sense， likeca it's basically it's basically a big a you just to all the people that have been organised。

 if that makes sense， I'm not an organised student。 that's not like a， oh， I wna like。

 be nice to all the good students like me。 You know， I was the terrible students， so。You。

 I'm just hurting， I'm just hurting versions of myself that exist within， within your own community。

 but you also often have a ton of other assignments due you and， and whenever you extend deadlines。

 you just you push things back， like there's a big。

 a big conversation I used to have with another academic at UNSW about。

The trouble with extensions in general is like extensions don't necessarily always help because suddenly like you're then weeks behind at everything。

 And it's， anyway， that's a long topic， but。Today， all no is the link wrong。

Just change that to a one。 sorry I'll fix that up now today we're talking about one big topic called runtime polymorphism。

 This is the last major topic we have in the course to go through I don't think it's gonna take us four hours but we'll see how we go and also this is the first time I've taught this content because in like for a long time for the last three years I've taught the most of this course like I've run this course and I've taught the most of it but we had other people taking various lectures like kind of guest lectures。



![](img/b31fc10609875d7fa0dbda4825da5b81_1.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_2.png)

Last year I think I taught two thirds of lectures， this year is the first time I've ever taken some lectures which include dynamic polymorphism。

As well as custom iterators and I think one other lecture that I can't remember。

 so new ground for me as well。 So it's a topic I'm probably like。



![](img/b31fc10609875d7fa0dbda4825da5b81_4.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_5.png)

Probably less familiar with， but still， you know， it all makes sense we taught it before。

Runtime polymorphism emphasis on the runtime word here。

 That's an interesting use of the word polymorphism。According to what CSEs told me again。

 that everyone who does this course has prerequisite knowledge surrounding object oriented programming in classes。

When we say the word polymorphism。Half of you should be going， Yeah。

 yeah I understand the other half should be going。 I used to understand that。

 but I've totally forgotten what that word means。 and that's that's the kind of way we're going approach this whole topic。

 So constructors， destructors， which are already talked about inheritance， polymorphism。

 these are all words we're not going to start from square one covering they we' trying to be helpful。

Exploring the topics。 I think I might have the hiccups， Oh Lordr。Okay， so。A couple of a few。

 I guess three key words that we're going to keep coming back to throughout this entire lecture block The first one being inheritance inheritance this is this idea where you have a class which you know you're familiar with classes you made a class in assignment2 you're making a class in assignment3。

 you can create a new class based on existing one sometimes we call it a subtype you know it's an extension of that class and you see this a lot in I mean we've already seen this when it comes to standard exception or runtime error in C+ plus this is probably one of the obvious examples of inheritance that you've seen in this course whereby you have a class like a runtime error which just inheritance an exception so that means that you have an class and then a runtime error class is that plus more。



![](img/b31fc10609875d7fa0dbda4825da5b81_7.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_8.png)

So。We understand itheritance。 class derivation。 There's lots of different ways you might think about it or words you might use to understand it。

 We're going to be talking a lot about polylymorphism。 Polymorphism is what allows us to use a。

A subclass as if it was a base class。 essentially， La objects of a subclass we use。 Yeah。

 so the most common case， again， if you've done a， if you're an undergrad and you've done a course like 2。

5，1，1， then you'll see inheritance come up by saying things like， you know。

 if you create a class that's like a。

![](img/b31fc10609875d7fa0dbda4825da5b81_10.png)

You know， a car and it has some stuff。 and then you create a class that's a car sorry。

 a class that is like a Toyota。Which inherits。Is that how you do it in Java？

 I've been written Java in like five years。Extends， it extends， and I can feel it。

 you're gonna tell me it extends。You know， you have something like this right and then polymorphism just as really quick recap for people is the idea that you can say things like you know car C equals new car like this and then you can say Toyota T equals new Toyota and then after that you're able to say something like car C2 equals t like this or a car C3 equals new Toyota。

 the idea that you can take something that is like a subtype like a Toyota car and you can have it kind of you know I don't want to use the word wrapped'ca that might give the wrong impression。

 but you can have its type be defined at runtime as like as like a parent type basically so you can treat this like a car now and the whole idea of polymorphism fundamentally was that you could have a few different types of cars like what's what's someone's favorite model a car tell me on the chat or go with that is there other car。

😊，Well， so no one， no one corrected me or confirmed if I was writing Java correctly， but that's okay。

 We'll just pretend this is Java， if it's not。Favorite car brand。 Who's going to win that one。

Wheres everyone。Hope my chat's working。The last few lectures， the chats randomly there we go， Honda。

 Honda， a bus， Honda， two people like Honda， Michael likes buses。嗯。Yeah。

 so we've got like two cars like Honda right and and one of the main purposes of polymorphism is to allow us to do things like this is to take two subtypes or multiple subtypes or even just one like a Toyota car and a Honda car。

 which are all they inherit the properties of a car and the methods and treat them as if it's the part of the it's the base class。

 generalize them。 So it's a form of runtime generalization when it comes to types。



![](img/b31fc10609875d7fa0dbda4825da5b81_12.png)

So that's what polymorphism is， that's a topic we're going to have to keep exploring over today in the next lecture。

 and then we have dynamic binding dynamic binding is probably a new word。😊。



![](img/b31fc10609875d7fa0dbda4825da5b81_14.png)

For like in terms of your Oo toolkit， though essentially dynamic binding is just a mechanism or something we'd use to describe what's actually happening when it comes to a lot of polymorphic behaviors。

 So dynamic binding is actually like this is Java。 So I don't want to like lean too heavily on it。

 but dynamic binding is exactly what is kind of happening here， where at runtime。

 which is what we refer to as dynamic， we are binding one object to another。

 and you should be familiar with the general concept of binding because we've been talking about it since the start of the course from con。

 you can bind a non noncons argument to a con parameter。 you can bind a。



![](img/b31fc10609875d7fa0dbda4825da5b81_16.png)

Our value reference to a contel value reference， right， very， you know， you can。

 you can bind a subtype to a base type， one of its parent types， etc cea。



![](img/b31fc10609875d7fa0dbda4825da5b81_18.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_19.png)

Yes， I am taking this whole thing a little bit slower， I guess too。

 because we we have the the time this week and people might be asking like。

 why do we have so much time this week and like all the other weeks felt rushed。

 It's like one one of the biggest and most relevant things is that I one thing I don't like about trimesters is that it's really hard to teach things at the end of the course because。

Like。You it's really hard to assess people except on the exam。 and the exam has some limitations。

 So it's like you can't just like dump a whole bunch of crap at the end of the course。 So you could。

 but then it's all like bonus content。 speaking of that really randomly。

 sorry for the slight tangent here where as far as I know， and I'll send this out in the notice。

 But we have a guest lecture with Opteva next week。 So usually students enjoy that one a lot。

 I've done I do guest lectures with companies sometimes that one's still probably the one students enjoy the most。

 So hold out for that info。 but anyway， back back on topic， sorry。

 when it comes to this like runtime polymorphism stuff。

 one of the the fundamental tens some of the tenets of C plus plus the guiding principles again of that we want C plus plus to support object oriented programming。

 but we want to wherever possible avoid any runtime performance penalty because something about objects and classes and inheritance that exists in languages like Java and Python is that it does a lot of stuff at runtime。

Which can make it really heavyca it has to kind of do lots of checks right。

 And you're familiar with this。 You have languages that do garbage collection and all these other kinds of abstractions that make your code more reliable at the expense of performance。

C plus plus supports polymorphism in two very different ways， right。

 and and polymorphism is a form of generic。 Well， it's not a form of generic programming， but。

The two main ways that we deal with polymorphism and C plus plus are at compile time or static polymorphism。

 which is what we've been talking about in week 7 and 8。

 which is Sl and templates and everything like that。

 And that means that that polymorphic behavior where you can， you know， have a。

Treat a vector of instant， a vector of doubles and a vector of chas， all is the same kind of concept。

 right that you can deal with them generically。That's static polymorphism。

 What we're talking about when it comes to this O O stuff today is more on dynamic polymorphism。

 So that's the idea。When we're talking about inheritance and everything like that。Now。

The way to think about some of this stuff is that。When it comes to。

Like how you program this one's a little bit higher level。

 But when you program often what you're doing when you create classes use you're representing concepts。

 So if you're creating a class for Euclidean vector or a you know。

 general direct way to graph or anything like that， you're trying to represent a concept。

 and generally we relate these concepts either via composition or via inheritance。

 composition is when we include something inside another thing。 So。How would you put it like。

You see this with assignment3 and you see this with your iterator where you have a class like GDWG and it contains another class which is your iterator and that's a composition aggregation if you think back to your UML knowledge and again just as a reminder。

 inheritance is a different kind of thing where we're not saying that a Toyota a car contains a Toyota or the Toyota contains a car we're simply saying a Toyota or a Honda is a car。

 it can do everything a car can do plus potentially more。And， and they're the。

 they're the real differences in those relationships。

I think just a quick comment because this always comes up So this has been added in is that when we talk about C++ and00。

 there's the usual questions of， oh， what about private。

 public protected and people are familiar with those three words in terms of scopes so。In any class。

 and， you know， we。We've seen this already with classes。

 we still do have public and private protected as still a type。

 and we mentioned back in week three with protected that we'd mention it again when it comes to like us dealing with more objects。

 as you know by now， public means that it can be accessed publicly it's part of the public interface and private means that it can only be accessed in the actual scope of the class itself。

 whereas protected as a keyword as something that describes when。

It can only be accessed by the scope of the class。

![](img/b31fc10609875d7fa0dbda4825da5b81_21.png)

Or any parent scope。And that's that's or sorry any subtype， sorry。

 any subclass I got that the wrong way around。 So an example of that obviously is if you have a car and inside of that car。

 if you have this is a mix of Java Z++ but if you have an int here like an int my int in C++ that you can actually reference and access that inside of your Toyota。

 you know so if you have a constructor or something and you were to hear。



![](img/b31fc10609875d7fa0dbda4825da5b81_23.png)

You would hear you know， say standard C might end that would be valid in C plus spots so protected is like private except it's accessible by subtypes as well。

 whereasas if something's truly private， then even subtypes can't access it。

 You're not really going to see a whole bunch of that I don't have any links off the top of my head。

 but I think's there's a lot of great literature out there that shows。



![](img/b31fc10609875d7fa0dbda4825da5b81_25.png)

Like a lot of convincing arguments that protected members or protected functions aren't really a great idea Like I think I think students are not students。

 I think people can get pretty caught up I'm thinking like it's a really cool sneaky idea to have these protected things。

 but if you actually draw a Venn diagram of like you know these are all the use cases where things you need things to be how would you put it。



![](img/b31fc10609875d7fa0dbda4825da5b81_27.png)

Yeah， if you draw like these two Venn diagrams of like。

 here's all the cases where you want something to be public and then here's all the cases where you want something to be like accessible by a subclass。

What you'll often find is that most of these two things kind of overlap totally。

 I can't do transparency with paint。 but it's like pretty much anytime you want something accessible by a subclass。

 If you're doing software design well， there's a good chance it's also going to want to be made public to or vice versa。

 So don't get too caught up on a protected keyword just because you're dealing with O。

 There are there are times that it's no doubt useful， though yes。

 you don't need to get too caught up on it。 Pyn says， well， the finals involve O P。 Well， I mean。

 I think。I think I just want to be clear here too。A。

OO P is a lot of what like it's implicit in most things we've done in this course。

 We've been talking about it explicitly since week 3 and implicit since week 1。

 The real question about this week is we're dealing with dynamic polymorphism this week and dynamic polymorphism is fundamentally a topic on what is inheritance。

And how do you interact with it and what is its behaviour。 And yeah， that'll be。

 that'll be in the finals。The， the idea with the finals is to。

Ideally touch on as many topics as we can， but we'll talk about that next week and also just as a quick comment on the finals as I had written on this page can you can read some information about the finals here and we'll keep touching on this over the next week but generally we won't talk I won't answer any exam questions till next week just so we can do it in one big hit。



![](img/b31fc10609875d7fa0dbda4825da5b81_29.png)

So that's pretty much it unprotected， you won't see that a whole bunch。

 you don't need to stress about it too much now。What exactly like how do you go about inheritance in C plus plus Because。

 you know， I've given these little examples in Java， which is all cute and stuff。

 But how do you actually really work with it in C plus plus。

The short answer is that it's very similar just with some syntactic differences。

 So in Java you're probably used to doing something like I just described here。

 which is where you say again， like class what have we gotten here Yeah。

 you'll say something in Java。 So if we do Java at the top， you'll be like yep。

 we got class which is like a base class and then that has stuff and then we'll have our class。

 which is our derived class， which is going to extend base class。

 which has some stuff like that in C plus plus it's relatively similar。

 you still have your base class like this。 However。

 when you actually derive things you're using a colon here to denote derivations now。



![](img/b31fc10609875d7fa0dbda4825da5b81_31.png)

The thing about this is that it's not too dissimilar from the kind of syntax you're used to with constructors and some of the initialiser lists。

 You know， it's just like we're， we're denoting some name and then we're describing something else about it in this case。

That derived class inherits。Base class， you do need the public part there。

That kind of says that all of the public parts of base class or the public parts of derived class there's pretty much no reasonable circumstance whether you wouldn't meet that public。

 that's just what you' write so don't overthink that too much and then you can go about and keep writing the rest of the class there which is what we'll talk about。



![](img/b31fc10609875d7fa0dbda4825da5b81_33.png)

嗯。The comment I made before about protected。I won't get into that anymorecause we talk about it for a while。

 but that's that's how we do it。 And we're familiar with classes already because whether it's a subclass or a base class。

 we know we've got these things like public and private。 And if we want to make constructors。

 we can do them don't need that in there。 We can do them like this right。



![](img/b31fc10609875d7fa0dbda4825da5b81_35.png)

Pretty much all the same knowledge。嗯。D Au it says， can you derive from multiple classes， no。No。

 and I mean， this gets into an interesting。 These， These are good questions about software design。

 And it's like， why would you want to inherit two classes， right？ And the answer is well。

 I'd like it to have two kinds of capabilities and stuff。 Well， this， this， this is why you。

 you should really always rest heavily on。

![](img/b31fc10609875d7fa0dbda4825da5b81_37.png)

This slot， yeah， I mean， you can， yeah。Don't， don't。

I get so caught up with this stuff because someone's like， someone's always like。You know。

 can we do stuff And it's like there's a lot of things you can do and sometimes we gloss over things that you shouldn't do。

 What I want to kind of point back to is this slide here about inheritance and composition So I like that question can you derive from multiple classes because again before you even get into the question about whether it's something that is appropriate or that you'd want to do you can also get into that question about like what actually makes sense here。

 and whenever you come across these scenarios where you think， okay。

 maybe I have the two classes and I'd really like to get a lot of properties of both。

 I'd really like to know get， I don't know what you'd want to combine you know maybe a vector in a map or something I don't know something like that you could think okay。

 well is this an inheritance relationship， but often if you're getting into more complicated things like that you're actually wanting to get into like the composition realm where you're saying okay。

 I actually gonna create another class like a separate class except it's gonna contain these two classes as well and that's kind of the way to。

Think about a lot of these things is inheritance as a tool that。While。Works。

 it doesn't mean that in every single instance， you'd like to utilize it， right。

 So don't get too caught up on at's some fancy。 Then composition is often still a really nice way to go about solving most problems。

 But not every problem can be solved through composition。 Now， if we ever a look at an actual。



![](img/b31fc10609875d7fa0dbda4825da5b81_39.png)

Piece of memory layout。 And this is where we're really gonna start getting into the lecture today。

 Like， well， this is where we're really gonna start getting into。

 I guess that some of the details of things is that。嗯。When we have two classes here。

 right we've been talking about subclass like base class and subclass you can see on the left here we have a base class which has two public methods。

 we have a get in member method and a standard string get class name which returns us a string。

And two data members。 we have an int member data member and a string member data member now。

We have to be careful here because what's going to happen with this classes itself just as a throwback to some previous weeks is that。

When this is constructed， as you can see， there's no constructor here。

 so we will get a synthesized constructor。The downside is that。

Without any explicit construction of int。Or any default value that's just going to get created and given an initialized memory。

 which willll see this when we run the code， something like standard string though because it's an actual kind of class object here。

 this will this will actually construct to an object so you will get like a nice default construction here。

So。Yeah， that's just something to keep in mind。 If you'll see some strange behaviour soon。

 but fairly standard base class， it's like a little encapsulated class。 It doesn't enter。

 has a string。 And then2， two getters， essentially to get them。 Then we have a subclass over here。

 And that subclass inherits a base class， which means that it has all of the。It has all of the。

 you know， private members and the。The public methods as well。

 and you can see what we're doing here is we are creating two new data members called vector member and pointer member。

 one of those is just a vector of ints with no members and the other one is a unique pointer of an int。

And we have no constructor here， so these two things will be default constructed。

 which means this will be an empty vector， and this means here this will be an int an int will be created on the heap。

I don't know how is unique pointer default initialized？Probably to null， no pointer， I guess。

I was thinking make unique for a second。 I guess that would be not point。

 I can't remember off the top of my head。And yeah， but it inherits the properties。 Now。

 where people can get confused on this is， you know， it's kind of like， well。

 what does that actually look like in， in memory， like in in the literal memory during run time。

 But then also like what kind of functions exist in in the class。

And if you look here for a base class object， when you create an instance of this class。

 when you create an object of it， there will be two items that are stored in memory。

 The first one is the endt member and the other one is the string member。

 these are just be stored as you expect。 you're familiar with this because classes are juststructs with members and you don't store functions on the stack。

 right， Like functions are just functions are stored in the actual。

The the executable part of the code， right， their instructions。Essentially。

 so functions don't take up memory per se at runtime kind of that's a complicated comment。

 but we'll get back to that one。 So this one just has these two data members on it。 Great。

 when we create a subtype what happens is we have to create all of the data members of the parent type or whatever the parent type is but then we also add on our own members that we give it。

 whether the private public， it doesn't really matter。 So now our subclass here。

 actually is going to have four data members。 it'll be the two that we've inherited and then the two here。

Right， the other thing we're then doing is we're then redefining。

What the get class name function does。 And we're redefining it to return sub class as opposed to base class。

 So the kind of。The default on we gave it here。Is that it just returns base class and now we're overriding and say。

 no， no， if someone calls get class name of me， I want to give that a new behaviour which is to just return subclass。

I he says we have a function called get int member。

 Can we also have a function called a set int member。 Yes， you could， if you want。 I mean。

 that would be fine。 These examples are just designed to be quite small。 Natural。

 this this whole thing wouldn't really be particularly useful in itself， but。

That's kind of where we're at。 so we've got our four data members now。

A question that comes up with this is， is people being like， wait， wait。

 if this is private and you said before， how can。You know。Like what's， yeah， someone's like， okay。

 if this is private， then what's the point of including in the subclass object if。

 if I can't access it， because we've learned that subclass can't access private members of their parents。

 And the， the short answer there is that。Just because you can't access it with your code。

That doesn't mean that code you access can't access it in terms of if there was a public or a protected method here。

 like take take get in member， for instance， you could let me just like copy this for a sec。



![](img/b31fc10609875d7fa0dbda4825da5b81_41.png)

You could take this and you could actually。Do something or like if I created an instance of this class。

Down here and I said auto S equals subclass like this， and then I said。Stand at C out S do。

Get class name。 This works because I've called a oh maybe get member。 Was it get member I， sorry。

 get in member。

![](img/b31fc10609875d7fa0dbda4825da5b81_43.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_44.png)

This works。Because when I call get int member here。



![](img/b31fc10609875d7fa0dbda4825da5b81_46.png)

Even though it's not defined in my subclass because I inherit all of the public and protected properties。

 I'm calling the parent version of it which gets the actual int member。

 so it it's kind of private private still means as part of you like if you inherit private things。

 it's still part of your object， it just it changes the way that you interface with it。

 it essentially says that you can't interface with it directly。

 you can't have to rely on you know a parent that actually had that in scope。嗯。Juuan Juan says。

 what is the difference between nested costs and inherited costs， Well， nested costs。



![](img/b31fc10609875d7fa0dbda4825da5b81_48.png)

It's pretty much all just part of composition。 It's what you're doing with。

Unless I'm really misunderstanding something what you're doing with assignment  three。

 where you just have a class within a class or an in a class。

So I think just like your iterator is probably a good example of a nested class that's closer to a composition。

 inheritance classes where you actually are saying I am like that。

 just I have more properties as opposed to like I contain one of these or I have one of these myself。



![](img/b31fc10609875d7fa0dbda4825da5b81_50.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_51.png)

Okay， so that's the really basic idea we're about to get into the code of this。

And think a little bit more about this。Data layout because it's quite relevant so。



![](img/b31fc10609875d7fa0dbda4825da5b81_53.png)

Polymorphism and values when it comes to C plus plus here we have a base class here we have a subclass is the very similar to the previous example。

 the data members are a bit different though we're storing less kind of crap and we're just storing like two inss so we've got like an int for member underscore an in for subclass data underscore Now in our main function we have ourselves a void function that is called print class name and what it does is it takes in a base class type。

And it prints out for that base class type gett class name and get member so if I create a base class and I pass it into this function it's going to call these two functions and then I have a mean function here that will create a base class it will create a subclass and then respectively it'll pass both of them into that print class name function。

So let's pull that up in VS code。

![](img/b31fc10609875d7fa0dbda4825da5b81_55.png)

Okay， so I have this here， there's a couple of differences just to get this to compile。

 like you can see I've avoided that to avoid the unused variable error。And I want to compile this。

 And who's going to tell me what， what's this program going to print out。Someone give me some。

Someone give me some guess on the chat。Have a think you can， I mean， you know。

 I should really just pause the recording when I do this stuff。Okay， so I had one answer。

Which is it'll print。Base class， then subclass。 And two people have said that now。 Yeah。

 so if we compile this one。I mean， all this code is public to you anyway。

 it's not like you can't just get it and run it。And then I run that， I get base class2， base class 0。

So。Really interesting is this like why is this happened now？

I get why people think it prints bass class then it prints subclass because that's kind of the behaviour you'd get in other languages that have simpler polymorphism rules。

 And that makes sense because you look at this and you think sorry。

 I don't know what that was you look at this and you think， oh well， I've got my my base class here。

 Yeah， that is what Java does， it returns when I call when I call it on this type I get。

This result and when I call it on a subtype， I get this result now。

One of the obvious differences here is if I was to create another function called print class name2。

 and I gave it a subclass here。And I called print class name two for subclo。

 what do you think it's going to print out in this scenario？And this scenario。

 it's going to print out。Base class subclass。 So the reason that there's a difference。

 and you're probably aware of this already， the reason that there's even a difference here is because of the parameter type。

 because even though this is a base class and even though this is a subclass。

 they two separate types。 one inherits the other。 We're passing them both into this function。

 which binds it to a base class we're familiar with binding。

 you can pass a non constant thing in a constant It doesn't suddenly make the thing you passed in con。

 but it。You know， it morphs it into that situation。So。

What actually happens here is that because you pass it in as base class， when you take the subclass。

The compiler at runtime in this particular scenario will。嗯。Jesus。Sorry。Live in the southwest。

 everything's crazy here。嗯。Yeah， we have this base class and what happens is that when you see base dot get class name and base dot get member。

 the way that C+ plus is designed， if you're just doing it like this is it goes and says。

 base class okay well I'm going to kind of look here Now there's a particular reason that this is happening It's called the object slicing problem which we're going to talk about in a second but a big mistake we're making before we even really get into the syntax of this language is passing things in by value and Michael's said on the chat does it change if you take reference in the parameter so it doesn't change but the reason it's wrong is different and you're on a better path here。



![](img/b31fc10609875d7fa0dbda4825da5b81_57.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_58.png)

Before we do that， Diamud says， what would happen if we used auto instead of base class。

 That's a good question my。Guess as if we used auto， we'd get the same behaviour we just had。

 because。The compiler will function overload， and it'll generate two different functions in the binary。

 I guessing， no。Oh， sorry， have to do that once。That'd be my guess。

 so this will probably get a similar behavior。Yeah， so in this case。

 it generated two separate functions。 that's really rolling the dice with things。 but you know。

 I dig that attitude。So the real question then is， okay， well， we know if we do base class here。

 then what happens is it all kind of gets coerced to be that type。Which we don't want。

So how do we change that， Well， firstly， we need to add a reference here。

 pretty much any time you're dealing with。Passian classes。

Passing in objects of class types and you're dealing with inheritance and stuff。

 you nearly always want to pass them in by reference or by pointer。

 we'll get to the by pointer stuff later， and I'll give you a bit of a visual demonstration of why that is。

 but。For now， if we do pass in as reference， we do still get the same result。

 Now ignore those numbers because remember this is an uninitialized memory that's come from our our member because whenever we print get member。

 we you know， it's uninitialized memory。But yeah， so references here don't really help that situation specifically。



![](img/b31fc10609875d7fa0dbda4825da5b81_60.png)

But。嗯。One， one particular way that like okay， why are references good in this case。

 Like why do we use references， I think if you go further down。

 you see the same example with a reference here， why do we like these references And the reason is because otherwise we run into what we call the object slicing problem and it's the idea where if if like you're aware of this on a computer right Like you kind of have this intuitive sense where this is the size of an int。

And then this is the size of a double。Doubles roughly doubles exactly twice the size of an inch。

So what happens？When you have some code。And you say， well， you know， I got a double D equals。

 you know，5。5。 and I got an in。D equals D。What happens here Now。

 a lot of things could happen if this was a really slow language like jascript。

 which I think keeps all the stuff as strings or something。 then in some situations。

 the the language would allow you to have an int that is you know as big as the doubles and it takes like an eight byte double and it can you know everything's huge to allow things to be compatible。

 that's kind of the short answer。 So if you make all the data types huge。

 then you make this kind of you know binding easier。

 and we could do a similar thing in C plus plus but it's not how it works。

 And you've seen this in the past too。 if you say double d equals 5。5 and then you make it an int。

 And I mean， even forget that for a second， even imagine it's like five times 10 to the 55 that's a valid double but you that won't work as an int because it's beyond the precision an if you try and put that into an int and you' forced it there。

 you'd have to lose some information。Because it's like。

You would then like there's all this stuff here that might be missing that exists there。

 So if you think about the knowledge you already have and you think about you know trying to turn a double into an int。

 theres there's what we kind of might call slicing which is the idea where you say。

 there's actually too much stuff there。 So I'm actually just gonna have to cut you in half and then we'll just like move up the half that fits Now the int double is not the best example because they're stored differently but I'm just trying to convey the point that you're already kind of aware of this idea where if you move from one type to another that has just less data allocated for it。

 you're gonna lose something And the exact same thing happens with C plus plus when we have say something like a subclass and then we pass it in by value to a type that's like a base class because remember this is passed by value。

 So there's actual copies happening here。 So if you imagine for a second。

 like how big is our base class。 So when when the compiler creates memory for this base class type。

 what's it gonna do。 It's like it's a。

![](img/b31fc10609875d7fa0dbda4825da5b81_62.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_63.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_64.png)

Type。So。For performance reasons， it's not going to make a massive type that's super compatible with everything。

 it's going to make a tie。

![](img/b31fc10609875d7fa0dbda4825da5b81_66.png)

An instance of that type that has the exact amount of memory that we set a base class needs。

 which in this case here is just one int， I'm simplifying some things we'll talk about later too。

 but at the moment it's just one int which is I might make that square a bit smaller。

Which is just like， you know， in member。But how big is our subclass well when we create a type of subclass？

The size of that type。I is a little bit bigger because the subclass actually needs its own int member and then it needs its own subclass data as well。

 so it's got an int member。And then it's also got an int subclass data， that's one variable。

 I'll just make it sub。Subclass data like that。Okay， so this is what a subclass looks like in memory。

 That's what the object looks like。 And then you have a base class up here that looks like that。

 So when you say I would like to copy。My subclass into this base class variable by value which has a fixed amount of space。

 you lose some precision and you get the object slicing problem。

 which essentially slices off and removes anything that's part of the subtype。



![](img/b31fc10609875d7fa0dbda4825da5b81_68.png)

So anything here that was part of subclass that was not already part of base class。

 which is basically all of your data members gets removed。

Because there's only so much storage for it。 We have to slice the object down。

 So that's why we don't like passing things by value。

 That can have a lot of very strange consequences。 And that's why we do like passing things by reference。

 because references are always the same size。 If you know， if we have a base class reference up here。



![](img/b31fc10609875d7fa0dbda4825da5b81_70.png)

For instance， that's just a pointo。So the base class reference doesn't care。

 like if it's just a pointer， it doesn't care whether it's pointing to base class。

 it doesn't care whether it's pointing to this。 It's just a pointer。 it's the same。

 I don't have of your references。 It's probably the size of a pointer， but it's like say8 bytes。

 They're all the same size。 So it doesn't matter what you assign to it as long as it's a combable type as long as it's a type that can be bound to it。

Then it works fine。 And and the types that can be bound to a base class reference are。

Either a base class type itself or any subtype。

![](img/b31fc10609875d7fa0dbda4825da5b81_72.png)

That's the kind of standard rules of polymorphism that you're already used to。

 And and for those again familiar with Java， Java polymorphism。

 because all the objects in Java are references anyway。

 that's kind of the behavior that it's exhibiting。In a in a rough sense。

But I won't get into Javacause I don't care for it too much， but。



![](img/b31fc10609875d7fa0dbda4825da5b81_74.png)

That's what we have to be careful， so we do want to pass things by reference。



![](img/b31fc10609875d7fa0dbda4825da5b81_76.png)

This solves。Chat disconnected， what？This solves the object slicing problem for us。

 but it does leave one more problem。And this other problem that it leaves us is this question of like。

 okay， so I get I get defining base class and passing base class into print class name That makes sense。

 Sure， I just call those exact members there。However。

What happens if I create a subclass which consists of a new get class name？

And then I call print class name on the subclass。' like what happens if I call that and the question is。

 how does the compiler decide sorry that this is Caml case or whatever it's called。Passical case。

 Yeah， How does the compiler decide which version of get class name。It should call。

 should it call this version or should it call this version。Right。Like， that's a good question。嗯。

And when does the compiler decide this， does it decide it at runtime or does it decide it at compile time？

That's a tough one。 How do we ensure that calling G member doesn't have a similar overhead。Sure。

So what what this what this question is kind of posing is that， okay。

 how do we do something that makes sense in his performance？ So it's like。

 how does the compiler decide which version to use here？ Well。

 a solution to that we don't want to make so complicated and so run time heavy that it essentially means that just calling get member is kind of slower so。

That's the question to answer which we're about to get into with virtual functions。

 but before we do that I'm always sure that a couple of people have seen these two different numbers here and tried to think about them in the terminal。

 which is like when we print out base class and subclass we get these two different outputs here now again they are random because they are an uninitialized memory but like what are they actually represent and what they represent is that they represent the member variable。

Because that's what we're doing here， we're printing out Gt memberm。Of each respective object。



![](img/b31fc10609875d7fa0dbda4825da5b81_78.png)

Because。TheThere are a different member variable。for either object， the base class in the subclass。

 Now， for those who are less comfortable with O0 and inheritance。

 I think this is an important point to remember is that class is a template。

 So when you have a base class over here and a subclass over here。

 they're not like intrinsically linked their data。 like all that's linked is that type。

 They're totally separate objects， one object is over here。

 it has all the same you have object A over here， your base class， which has all of its data。

 and then you have object B over here， which has the exact same data as object a totally separately plus more。

 and that's what we're seeing here。 And that's why we're also getting these different outputs here。

 even though we're calling get member on the exact same type。



![](img/b31fc10609875d7fa0dbda4825da5b81_80.png)

Here。They were both different objects to start off with。

So the subclass still contains those original objects now。How do we deal with this problem。Here。

Because I added that reference to the code。Here， and we still printed out base class twice。

 but I don't want to print out。So Wendy， I don't want to print out base class twice。

 if I'm passing a subclass into my print class name function and I'm passing it by reference。

 I want it to print out。Subclass'ca that's what I'm giving it， right。

 I want to be able to generalize this， but still have it actually use my specific implementation。

 So if I have a base class or other subclass， it's like， okay。I can generalize those。

 that's like what we're aiming for here is a generic style of programming。

And this is where the idea of virtual functions comes into play。

 so in C++ we use virtual functions to help the compiler decide which version to call。

And we do that by any time that we define a function in a class that we think might be overridden through inheritance。

 we give it a virtual keyword and this is essentially an instruction to the compiler to say you know what。

 this function might change by a subtype a subtype might overrule this， they might overwrite it。

And then in the subtype， like the subclass here。When we。Refine something。

 sorry that that name's wrong。' beenen changing over a lot of code。 when we redefine that。

 we have to put the override there。Now one of those things isn't necessary。

 I can't remember which one one of them the compiler figures out for you anyway。

 I think it's the override。I think it's the overr anyway this explicitly tells the compiler that this particular function is designed to be modified by the subclasses and this actually says this is how it's modified。

🤢，And we can try that out so if we go back to our code here and I say， okay。

 well I actually want this one to be virtual here and I want this one here to override that virtual function and then I go and compile that。

Oh yeah， you get， you'll actually get this a lot。 And this is this isn't， this is what， yeah。

 this is part of W error。 This is a warning as an error。When you create。

A class that has virtual functions。 I a class that can be inherited。 You should always。

 you should always define， even if for no other reason than just to。You know。

 stub it a virtual destructor we'll try and talk about this one later。

'cause we're gonna talk about destructors more later。

But now you can see that it actually prints out base class and subclass。 Okay， that's cool。

 So that's kind of how we do it。 So if we wanted this one to be printed out。

 we have to override it after making it virtual in the parent class now。😊。



![](img/b31fc10609875d7fa0dbda4825da5b81_82.png)

Why does C plus+ have this kind of， you know， language asked like。

 why is this a thing and it all really comes back to。Performance。嗯。In the sense that。With。

Without the use of the virtual override。The compiler wouldn't be able to make some decisions to speed things up at runtime and what I mean by that is that。

Because。This inge member is not virtualized。 It means that if you subtype this class。

 the compiler doesn't have to keep track of of subtype implement。

 it's like it doesn't have to figure out which one to use at runtime because as we'll see soon。

 you actually have there's actually more data that needs to get stored at runtime to make this kind of dynamic polymorphism work So it's like just the act of doing this therefore will make the program use more memory because it's trying to keep track of some things if we don't make it virtual。

 then there's no reason to keep that extra memory because it's like there's no chance that this might be inherited and redefined It's just is as it is。

 and that's really helpful which we'll talk about。Vee tables in a sec。Yeah， so one more slide。

 then we'll take a break。So as I said before， override isn't required by the compiler。😊。

It does work without it， but you should always use it。

 And the reason you should always use it is because override fails to compile if it doesn't exist in the base class。

 So it's just another， you know， it's also a clear signal to people working on your。Code that like。

 you know， this is overr a virtual function。 So， for instance， here。If you do this。

Trying to figure out what's different about this。Yeah， so this one validly compile。

 yeah this one validly compiles， even though they're two separate functions。

 So you created this one is virtual， so it's ready to be overwritten if it needs to be。

 And then here you thought you've overwritten it， but you didn't realize that you've made this cons qualifiedalified。

 It makes sense for it to be consqualified。 You it's just a get every getter should be consqualified。

 So this actually compiles validly as two different separate functions and that could give some strange behavior depending on how you use it down the line。

 So it really helps with con noncon staff。 it helps with typos and everything else like that。

 there any questions about this stuff so far I'll give you like 10 seconds to ask any questions otherwise we'll take a break。

Cool， alright， well， if you have questions， we can do them after the break， so。

Let's take a break and keep going and keep talking about virtual function。 So 10 minutes。

 let's start up at 7，7，0，9， something like that， cool。So just before the break。

 we talked about virtual and override。嗯。Some other examples we're going run through。

 So we're going to talk about this example first， and then we're going get onto V tables。

 which is kind of a core way of understanding what's actually going on under the hood here。

 So let's have a look at this example。 we'll pull it up in VS code as well but let's see what happens when we actually start using virtual members。

 So we've got our base class。 It's got a members what we saw before。

 we have a destructor and all that does at the moment as print stuff for us。

 we then have a subclass where we get the name。 we override it。

 and then we have another destructor here。 so pretty much the same as before except we have destructors in both of these cases。

 on the other side we are going to print the base class by reference。

 same thing as we've seen in the other example。 And then here in the main function We're going to create a subclass and this line is a bit of a mouthful。

 but we're creating a unique pointer to a subclass。 So we're creating an actual new。

Heap object is a subclass because make unique。 Like what you give make unique is the actual thing that's created on the heap。

 And then we're starting static casting it to a unique pointer to a base class。

 So essentially now subclass becomes a。Unique point are to a base class。

 but what it's actually pointing to is a subclass itself。 and then we try and print out。You know。

 that object subclass is get class name。 So the question here is what's going to happen。

 What is actually going to get printed out。 Well， we're going to be printing out the destructors。

 But do you think we're going to print base class or do you think we're going to print subclass。

 Well， we can try that out。 So if we open 9，04。

![](img/b31fc10609875d7fa0dbda4825da5b81_84.png)

All that codes here。If I try and build and run this one。No， Lord， what have I。

Have I missed something on this one。Have I missed make unique doft doing。

 I it Nash include notes there。Oh， delete called on non final base class。

That has an non virtual deor。 Oh， no， sorry， I'm meant to。Virtualize this， I think。

Think that's the problem。Yep， okay。Overriding destruct。

 you need to use the virtual keyword when it comes to dealing with de structuresors。 Oh， let's run 9。

0，4。 So what do we get here， We get。Yep， we get subclass destructing subclass destructing base class。

 So a couple of things here， I could probably put in a new line to make some of the stuff easier。

 I might put in a new line after。Or actually is's that going to do a forest authority？No。

 I don't want to put it there， I'll put it here。Just so you can pay attention to what's going on。Yep。

 so we print out subclass， Then we print out destructing subclass and destructing base class。

 So two things to point out here， One is this is an example of us using。D。

Like passing by like dealing with polymorphism through pointers。

 So we said before that you don't want to pass inherited objects when you're dealing with polymorphism by value because you get the object slicing problem。

 In this case， we're not using reference either we're using by pointer。 So this is actually kind of。

Like a type conversion point at a pointer level。 And that also doesn't matter because just like a reference。

 a pointer is just pointing to a thing。 It doesn't care whether like it can be a base class pointer to a real base class or to a subclass that isn't particularly mine。

 So this is also an example of how you might do it if you had to deal with these objects as like heap items with pointers。



![](img/b31fc10609875d7fa0dbda4825da5b81_86.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_87.png)

You'll also see that the destruct is printed out in the order you'd expect。

 which is that whenever you inherit stuff it's always like the top classes construct is called and the next one。

 the next one the next one and your final type is the one that's called last and when you destruct it's in the reverse order So our destructor for the subclass is called first and then after we've destructed our subclass we kind of go up that chain or know up that tower until we get to the very parent class here which is base class So that ordering makes sense as well。

This also only works remember because we have our virtual and our override。

Which we just talked about before， just as an experiment。嗯。Like。

 we don't actually need this print stuff function anymore， by the way， but。Or was I gonna。Yeah。

 just as an experiment。Let's see what happens when we go。

Aut BC equals base class and then we say or sorry auto subclass equals subclass and then we'll say base class BC equals static cost。

Base class。Subclass。I think this will work。 I haven't。 this is very， this is more impromptu。

I just want to see if we can demonstrate。Bc dot get class names so we've got a subclass we've created this。

 then we're casting it to a base class this is by value in this case and then we are trying to print out the the base classes get class names so we'll try this one out。

Yep， and what are we gonna get， We're going get base class。

 And you can see in this case that that so the point I'm trying to demonstrate here is that。To。

 to get any reasonable behavior， you always want to deal with。Polymorphism， you know。

 and this kind of thing where you have a subclass and you're you're having like a parent class manager。

 you're trying to be polymorphic， you either want to always do that by pointer or by reference。

Just as a rule， if you do it by value， then it doesn't matter if you've done the virtuals in the overrides right because you're going to be slicing the object。

 And as far as as far as the compiler is concerned， it sees this。

 And it just says like it doesn't really matter what this is we're going end up cutting off everything that's not actually a base class anyway。

 So when you end up getting to call the class name， it doesn't matter what originally it was。

 It doesn't exist in this object here it's gone at this point of assignment。

 So none of that virtual and stuff or override matter。 So value pretty much always bad。Don't do it。

And then if you're not doing it by value and you actually want to get that polymorphic behaviour working properly where you're actually calling functions of a subclass。

 that's when you need to do the virtual and the override。😊。



![](img/b31fc10609875d7fa0dbda4825da5b81_89.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_90.png)

How does all of this work？ Well， this is where we get into V tables， each class。

Has a V table that is stored in the data segment。 Now， what do we mean by the data segment well。

When your code compiles and it compiles into something。

 it stores information like you have like your actual instructions over here。

 you know which are executed。

![](img/b31fc10609875d7fa0dbda4825da5b81_92.png)

Draw this。 It's like， you know， here's your actual like， you know。

 code and functions and all that stuff that actually， you know， these are the instructions。



![](img/b31fc10609875d7fa0dbda4825da5b81_94.png)

And then you also have your little data chunk and your data chunk isn't full of much one of the most obvious things's example it includes as an example is all of the string literals you have。

 so you know in this particular code we had before the the data piece of memory in the compiled executable would just consist of a base class string and a subclass string like that so those two things would be in that data segment what is also in the data segment is information。



![](img/b31fc10609875d7fa0dbda4825da5b81_96.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_97.png)

About each kind of class。That inherits another class if it has virtual functions。

 if the parent has virtual functions so that it can kind of keep track of what it should point to。

 This is what a V table is。 So V table's information V stands for virtual that is stored in the data segment and it's basically for each class an array of function pointers that say which definition each virtual function points to for that class。

 Now， these are all words and you can go and read this again。

 but I don't think me throwing these words at you right now is going make a huge amount of difference。

 I just want to show you like two really simple examples So。



![](img/b31fc10609875d7fa0dbda4825da5b81_99.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_100.png)

This example firstly， actually， I might start with the second example。 I found this one online。

 which I thought was a really kind of clear example that might demonstrate this。

 I'm just going to find out where it is。

![](img/b31fc10609875d7fa0dbda4825da5b81_102.png)

嗯。Yes， so。Looking at this one， let's say that we have， I mean， can we， can we skip that class A part。

 Yeah， let's have a look at class B here because we only care about class B and C。

 So it's like class B consists of just two virtual functions。 bar N quas。

 I don't know how to pronounce that。か。嗯。So it's just two virtual functions。 they're both void。

 they're defined outside of the class that's not necessary and they're both just print strings so they're both just two separate functions。

 Then we have class C that like that extends or inherits class B and what it does is it has its own implementation of the function bar that overrides the parent's definition and that function prints out this is C's implementation of bar so we only override one of them so we want to inherit one of them and override one of them just because something is marked as virtual in this context。

 it does not mean it has to be overwritten it's just saying that it can be overwritten in these cases so by marking those to as virtual they both can be overwritten and in the case of C only one of them is overwritten and this allows us to do these polymorphic things that we've just talked about in the lectures where you can say that you can create a new C object and you can assign it to some kind of reference or pointer type that's apparent and then you can say you print out the bar method on the B pointer and you will actually get。

This printed out， that's everything we've been talking about for the first hour。For this class。

 when this is compiled。😡，In the actual like executable you get， this is before runtime。

 this is in the compiled executable in the data segment。

 there is a piece of memory that looks like this。And what these are is these are V tables。

Where there's a V table for class B。Just is our first class and what it does is it tells you。

The bar function for class B points to this particular definition。

 so these like four rows here are function pointers， the quas for class B points to B quas。

And then when it comes to class C， the bar functioning class C points to C's bar and the quas。

 hate that word。 Now it points to B's quas。 and this makes sense right because that's actually the behavior you'd expect because we had three functions defined we had B's bar and quas and we had C's bar and you know that if you call quas on C that it should call what was defined in B up here。

 So in that case。That's what this table is here to represent， so that during runtime。

When you do something like you call， say。This， when you say B， B， like B， whatever bar。

 what it does is it looks for what we call the dynamic type which will'll get too soon of C of B。

 which says no no no， I don't care B what you were declared as。I care what you're pointing to。

You know， I don't care。 I understand that you're a pointer to a B， but， you know。

 we have polymorphism in this language and you might be pointing to something that's not a B。

 You might be pointing to a type of B that's a subtype of B。 And then it gets the C and it says。

 okay， I can see that you're pointing to that C and then you're saying you want to get the bar or C。

 Well， I'm gonna go look up the V table to see what I should call and it looks it up and it says okay class C bar。

 I'm going call C slash C you know C scope bar。 Similarlyly， if we called if we called like B。

 like if this was。

![](img/b31fc10609875d7fa0dbda4825da5b81_104.png)

Let me just copy it so I'm not describing text you if we did something like this where we said we create a U C and we say that B is a pointed to a type B that points to the C object which we can do because a polymorphism and then we say B called B's function quacks。

 then what happens is that it's going to look up the V table and it's going to go yeahep okay so C's quax is B's quas。

 it does actually look it up for C。

![](img/b31fc10609875d7fa0dbda4825da5b81_106.png)

Okay， just because it's a B， it's like what is the actual type at point still or references。

 That's what tells you where to look it up in the the V table。

 This example I have here I kind of moved away from this one。

 This is why we used in the previous time。 I wanted to find a better one for this term。



![](img/b31fc10609875d7fa0dbda4825da5b81_108.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_109.png)

This is an example where you have a class polygon， which is just a shape with rigid sides。

 I guess I don't know how you call the polygon shape with straight sides。En。You know。

 it has a V table associated with it。For。Deides an area function。So these are all virtual。

 I don't love this example because I think it's a little bit too much to you brain to figure out。

 but let's say that each class you have like the polygon class has a sides and an area function that tells you how many sides it has and what its area is。

 And it's implemented virtual like this and then you go along and you create a triangle which is a tight polygon and that's going have another V table where like it points to a different function because you can see these are implementations for triangle And then you can see here we have implementations for rectangle Now the only thing missing from these definitions of the word override which we've said you should have on all overriden methods。

 But the point is that each of these classes。Has a V table that tells you how it works。

 So if we come back to this definition again。

![](img/b31fc10609875d7fa0dbda4825da5b81_111.png)

A V table is an array of function pointers that says which definition each virtual function points do for that class。

 that's what we saw on the web page before。Each class has a V table。 So if you have a parent type。

 like a polygon or。Like a be type。 And there like yourself， and then 100。Subtypes。

 there's going to be 101 V tables because there's a V table for yourself。

It's the V table for the class that made functions virtual and then any subt that deals with those functions。

 because you need to be able to you know deal with those effectively if the V table for a class is non emptyty。

 then every member of the class has an additional data member that is a pointer to the V table。

 so that's a really important note because if we come back here。



![](img/b31fc10609875d7fa0dbda4825da5b81_113.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_114.png)

Earlier when we had this int member underscore and then we had a subclass which was an int member and a subda and just to pull that code up so you're really clear what I'm talking about。

 that's this example here。

![](img/b31fc10609875d7fa0dbda4825da5b81_116.png)

Once you mark these as virtual and override， once there's any kind of virtual function inside your class。

 then every single object。

![](img/b31fc10609875d7fa0dbda4825da5b81_118.png)

Of that class type it gets created。嗯。Has a V table pointer。That gets added to it。

And they point to the V table for that particular class now。

Just to maybe really emphasize this clearly in your heads。What that means is that I have。

 that's a terrible colour。 I have， say a class over here like base class。

 and I have a class over here like subclass。 Now， because I made this function virtual。



![](img/b31fc10609875d7fa0dbda4825da5b81_120.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_121.png)

It is now going to appear， so there are is a V table there is a V table in this class here and there is a V table。

 sorry for this class here， and they both specify where does get class name point to。

RightAnd in this case， get class name points to base Class's version of it。

Like that and in this case down here， this one points to subclasss version of it。Like that。

That is totally separate。 These are classes。 This is the data segment。

 This is stuff that happens before your program even runs。

 and this is stuff that happens even if you don't create any objects of that class type。

 but then what happens is when you actually go and create these objects。

 this is now at runtime and this is actual memory When I create an instance of my base class and I create an instance of my subclass because they are of types that have V tables now。

 what that means is that I end up。With at least one data member per object。That points。

To the V table。 So let's say I had two subclass objects。

 I created two of them in my code when I ran it Now what we're going to end up with is we're going to end up with this pointing to that V table and we're going to end up with this pointing to that V table and we're going to end up with this pointing to that V table。

 And remember again， that all of this is stored in the data segment of your program。

 This is static information that can be done at the compile time and the way C plus plus is designed is this particular object here has a V table which is just probably a pointer。

 I'm not sure what the size of it is that deals with that。 so。



![](img/b31fc10609875d7fa0dbda4825da5b81_123.png)

Then， when a virtual function。Is called on a reference or pointer type。

 The program does the following。 It follows the V table pointer to get to the V table in the data segment。

 It increments it by an offset， which is constant for each function。

 That's just a lot like how strs work， right， you know with a struck how you relate， you know。

 struck data struck next， whatever the name just refers to an offset from the beginning of the object。

 So it like knows where to look in the V table for the particular reference。

 And then it follows that particular function pointer to call the function。 So when you call， say。



![](img/b31fc10609875d7fa0dbda4825da5b81_125.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_126.png)

In this case here， when you call get class name， it's like， okay。

 well I know the get class name is the second function of my class so it follows the V table up here and then it well in this case the first first virtual function I should say So it grabs the first virtual function and then it says up okay。

 and that's what I'm going to call。 So that's how it then figures out what it is actually going to call。



![](img/b31fc10609875d7fa0dbda4825da5b81_128.png)

Yes， all of this happens quite comfortably。

![](img/b31fc10609875d7fa0dbda4825da5b81_130.png)

Why like so languages like Java and stuff are gonna be doing things like this themselves。

 It's just one kind of key difference is that remember how again。

 one of the principles of C plus plus is that you don't you don't want to pay what pay for what you don't use like you don't want to deal with garbage collection if you don't think you need it。

 you don't want to deal with unnecessary costly abstractions if you don't need it。

 It's a similar thing here where the reason we're marking things as virtual is because if you don't mark them as virtual then no V table is created。

 And again， I'm not familiar with the specifics of other programming languages on this front。

 but it's like a lot of them would have all of this information kind of baked into tons of things just to make it like super。

Super generalised， right，'cause anytime you generalise something is when you're gonna add some overheadad。

 So this is how it's kind of implemented。 It's， that's what you have to think about when you're working with it。

 yeah。

![](img/b31fc10609875d7fa0dbda4825da5b81_132.png)

Okay， last two things， I guess on this topic before we get on to more fun stuff or when I say more fun stuff。

 I mean， more fun stuff as opposed to。😊，Stuff that's more fun because this is delightful， isn't it？

 So we have our final keyword as well， and the final keyword is something that's tied to the override keyword。

 And what happens is if you instead of saying， okay。

 this is a get class name that returns a standard string override final。😊。

bit just override when you put the final here after the override。

 what it's saying to the compiler is this is no longer virtual for any subclasses。

 So when we create a base class here， this is a virtual function which says this can be overwritten And you know what you you can override it and override and keep making them you know virtual as you go down we'll keep overriding them as you go down。

 but if you say override a fine then if you try and inherit it the compiler is going get mad。

 compiler is going to be like no。I don't want to say it's gonna to get mad。

 but if the compiler has a variable of type subclass reference。

 it now no longer needs to look it up in the V table。 So when I say that the compile gets mad。

 what I'm really referring to here is that we said before that a V table is there for virtual function。

 so it knows kind of what to call。That is why something like in get member doesn't have a virtual function。

 and it doesn't matter like。And maybe I can take you back to the really early example because I think that。



![](img/b31fc10609875d7fa0dbda4825da5b81_134.png)

Demonstrates this really well is。If you remember in the really early example where we had to get class name on both of these。

 when these weren't virtual， when these weren't overridden。嗯。

If you remember what happened was when we called to get class name on either of these。

Even when we pass them in by reference。Right， there's no object slicing going on here。

 Even when we pass them in by reference， we still have this problem where it printed out base class twice。

And that's because without the marking of virtual， there was nothing added to a V table here。

 and therefore there's no dynamic runtime look up to figure out what function to actually called when things are referred to by reference or by pointer。

So。When you mark things as final， it's like a way of saying to the。



![](img/b31fc10609875d7fa0dbda4825da5b81_136.png)

To the compiler， it no longer needs to look it up in the V table because it's like this is just the final one。

And I'm just trying to find static binding if you have a subclass reference dynamic binding for a base class reference。

Oh， this。I think binding should possibly be a little bit earlier in this lecture。

 so maybe we'll come back to this particular point at the end here about what that actually means because I think we're going to get to binding after abstract classes。

Yeah， maybe I'll just kinda touch on it now， so。There's these two terms that I've used a couple times in this lecture so far。

 one of them is static binding and the other one is dynamic binding。

Static binding is basically the type of a name at compile time It's actually what you just refer to as the type。

 So when you you know I ask you here's a very what's its type you're like that's its type and you go okay。

 cool dynamic binding is essentially the type of what it points to。For， I guess。

 like of a better description。 So in a piece of code， like。



![](img/b31fc10609875d7fa0dbda4825da5b81_138.png)

I like our 904 actually might be better。What's the original version of this one？嗯。Yeah。

 so let's say for a second that I just clean this up a little bit。

And I'll just separate these lines out here。嗯那你。Yeah， let me just change my mind again。

This is even easier。 I just wanted to make it really， really easy。So。The question here is you know。

 what， like what is static type like what is。Static binding， static binding。

 static binding and dynamic binding。 So static binding is always the the type that it is like at compileant。

 basically， you look at the left hand side is how I think about it。 So in the case of this line here。

 So say we've got these two lines。 It's like what is these like this what is the static type of S。

 And the answer is as well as the subclass。That makes senseca that's what like if you just look at the left hand side。

 you're like S as a subclass and then you're like what is the dynamic type or the dynamic binding of S And the answer is in this case。

 a subclass too， that one's easyca you just created it In this case here。

 what is the static binding sorry， I should say binding of B。

And the answer here is that it's a base class because you just look at the left hand side。

 You're like what is the type literally defined as' it's a base class reference。

 it's dealing with the base class， but the dynamic binding of this。A B is a subclass。

 and this is kind of where the difference occurs。Essentially。

 when you're dealing with things polymorphically。Your static binding and your dynamic binding might be different things。

 so your static binding again is always what the name of the type literally is defined as。

 which is always the left hand side。 It's the easiest thing to figure out because you just look at it you're like。

 oh， that's a base class。Dynamic binding， though， is。What， what the type it actually references is。

 And the reason we call it dynamic binding is because that's the thing that's figured out at runtime。

 Because what do we say about V tables， right， It's like。A V table is looked up。

On the like on the dynamic type here at runtime to figure out what to call and this is why we keep calling this topic runtime polymorphism because。

There are things that you don't necessarily always know at compile time like and you might be like。

 why don't we know that at compile time and it's like well。

Imagine we had another type of subclass or like a。With sub subclass called S S。

Which is equal to sub subclass like this。And。I'm trying to think of a good example for this。

 You know， maybe， maybe you have like a pointer like。

 like you could have an if statement here that's like， you know， if， if， if some condition， if。

 if a user passes in some condition， then I'm gonna set the base class pointer to be to point to the。

To a point to S， otherwise I will have it point to SS like whatever it is， it's like what。

 what B interacts with them when you call B dot get class name here。

Like you can't figure out a compile time what particular class is gonna like what the dynamic type of B is gonna be here。

 Now this isn't quite valid code。 I'm sorry but like it's like you know a compile time what the static type is。

 It's a base class B is a base class it's written there It's a point to a base class。

 but it's like it's right there。 It's known statically。

 what's not known is the type of what it points to because maybe that's variable on some kind of condition。

 again， sorry to reiterate this so much， but it's like that's why we call this topic dynamic polymorphism and that's why we call template static polymorphism because everything about templates。

 you know a compile time。 so there it's all clear everything's good whereas here that's not so much the case here you don't really know what that is anyway。

 that's what static and dynamic binding is dynamic binding is what it actually is referring to。



![](img/b31fc10609875d7fa0dbda4825da5b81_140.png)

Static binding just， you know what？

![](img/b31fc10609875d7fa0dbda4825da5b81_142.png)

It's what the names defined as。Yeah， that was， that was a little bit of a segue， but。Relevant segue。

Last thing on this like column of slides is just to tie off some points about virtual。

 So we've seen before。These two instances at the bottom， where if you have， say a function。

 just like a void function or any kind of function that has a definition。

 it's what we call a non virtual function， which is where it's not part of any V table and。



![](img/b31fc10609875d7fa0dbda4825da5b81_144.png)

It's， it's what it's the static types being used because that's that's basically what's happening in these earlier examples here because remember how in this one。

 when we ran it without the virtual。It just printed base class， base class。Jesus shit， sorry。

It printed a base class base class and that's because without the virtual keyword。

 it's just printing like what the static type is。 So base class and subclass here。

 once they are passed by reference into this function，While the dynamic。

Binding of what base is is different for each function call because of different actual objects being passed in。

 Its got the same static binding because it's statically binded to base class here。

 So therefore when this is called because because there's nothing virtual it's it's just going call the type in the static binding that's basically why this happened So it's like well okay base has this function here。

 get class name。 okay sure there's nothing virtual about that。

 there's nothing in the V table about it So I'm just going to use my static type because that's quicker because I can just do that I already know that it's all done at compiled time。

 I don't have to look up a V table and figure things out。

 it's just known once we have the virtual keyword there though that's essentially again a signal to say no when you call this function we actually care about it's dynamic binding and what that should be。

 and that's pretty much like one of the fundamental ideas of why that's kind of different。



![](img/b31fc10609875d7fa0dbda4825da5b81_146.png)

So we know these two examples because this is a non virtual。

Function definition on the left here that deals with the static binding。

 This is a virtual function definition that says we got to deal with the dynamic binding。

 But what we're missing from this particular set of information is what we call a pure virtual function。

 which and says which says that I'm not going to give you a definition of this。

 this has to be implemented by like a subtype。 So essentially that would be the equivalent of us。

 for instance。

![](img/b31fc10609875d7fa0dbda4825da5b81_148.png)

Going here and instead of saying up here virtual standard string that and then giving it a definition I could just say equals0 and if I say equals0。

 what that is me saying is that this is this is a function that I'm not going to give you any information about。

 but I expect whoever inherits me to give you some light clarity on like to actually give you that definition of it and if I try to compile this one will probably run into issues。



![](img/b31fc10609875d7fa0dbda4825da5b81_150.png)

Yeah， so here the issue we get is。Variable type base class is an abstract class。 Well。

 what is an abstract class。That's an excellent question。 An abstract class。

 I don't know why it's acronym to ABCs。 This is actually a carryover from previous lecture。

 I don't know anyone that actually refers to as an ABC。

 but maybe I don't know the right people an abstract class in C++ is identical to the notion of an abstract class in any other language which is a class that is a valid type that you never explicitly instantiate so examples of that we saw one kind of earlier actually just in our code。

😊，Where was it。

![](img/b31fc10609875d7fa0dbda4825da5b81_152.png)

Here。嗯。This is actually an example of a whats something you might make is an abstract class。

 So we've got three classes here。 We've got a polygon class， which is a parent。

 and then we've got two children， which is a rectangle class and a triangle class。

 and they both inherit from polygon。 Now， the thing is it makes a triangle makes sense。

 A rectangle makes sense。 But what is a polygon。 Likes， I mean， I know you might think， oh。

 that could make sense because I'll just make it generalize。

 but it's like maybe that just doesn't mean anything to create。

 Maybe there's no such thing as having a polygon that isn't a particular shape。

 So it's what we call an abstract class。 If it's something that we want to kind of have meaning if it's something that we want other things to inherit。

 think of it like a template。But I wna say template， I mean， like， you know。

 a Microsoft Word template， not like a S TL template。Yeah。

 don't don't relate those two concepts is like it's you know。

 a canvas for you to build actual things that can be instantiateated。 And if you create。

 if you try and create an abstract class， you've defined it。

 it won't work because it should just be like that doesn't make any sense。

 an abstract classes are out there for tons of stuff。 You know。

 pretty much anything you could think about in your life could have a generalization of properties to it that just wouldn't make sense by itself。

 You know， like again， a car。 You could have a class that's like a car。

 And all that all that class contains as the number of wheels。

 the number of doors the way to the car。 But it's like if you created that。

 it just would mean nothing really。's， it's too like abstract an idea。

 It needs to be like more concrete。 so。

![](img/b31fc10609875d7fa0dbda4825da5b81_154.png)

That's what an abstract class is。And again， this is a concept that I'm hoping you would have touched on in a previous course unless they've gotten rid of that kind of stuff now but。

And there's some examples here and I've kind of talked to this in my own way already。

 which is just like you might want some default behaviour and data， but without more information。

 it just doesn't mean anything。And the way you make something abstract in C+ plus is that once there is at least one pure virtual function inside your class。

 it is now abstract and it cannot be constructed and we've actually seen that just here with when I've done this because by making this one a pure virtual which if you remember from the previous slide is saying I'm going to say that this is something that exists and needs to be overridden。

As in I don't have any meaning for this， like someone else has to give some meaning for this as long as one of these exists。

 then this becomes an abstract class and it kind of prevents you from instantiating it because you can't because you're saying that。

That， that you're saying that， you know。This is a pure virtual and someone else has to figure that out。



![](img/b31fc10609875d7fa0dbda4825da5b81_156.png)

Fill in the gap， so。That's what an abstract class is I've got these other examples just here which is like。

😊，The difference between a pure virtual function and just a general virtual function。

 If you were to just write this virtual void draw canvas。And percent。

 if you were to try and create a shape object with that。De with that declaration。

 your code would compile， but it would fail at length time because it's， again。

 it's just like a standard function declaration that has no definition。 The first one is what you。

Are used to already from what we've talked about， which is that you can create a function that。

Is virtual。You know it might have a body， it might not have a body。

 and then here you create a pure virtual function which is saying that I'm not going to give you a definition because I expect my subtypes to give a definition。

 which makes it abstract。And the reason that you want to use this is like。

 you don't need this to like inherit。 But if you do something like this with the hope that someone inherits you such as like。



![](img/b31fc10609875d7fa0dbda4825da5b81_158.png)

![](img/b31fc10609875d7fa0dbda4825da5b81_159.png)

Let's say that。You know， I do have this， this space class has like a get member。

Function or a get class name function。 But it just I want someone to override this。

 if I just have this do like a return bar。Then the problem with this is that。

There is no compile time enforcement that someone will actually override this。

 it's possible for someone to not override it， and then the V table will just point to the previous one just like how this here。

 this one this subclass it inherits base class but it doesn't implement get member so pretty much it's a method of enforcement whereby if you say equals0 you're essentially saying that it's now not possible for someone to inherit a default definition because they need to do it too。



![](img/b31fc10609875d7fa0dbda4825da5b81_161.png)

Pson says， why can abstract classes have constructors？To be called by subclass like Java super well。

 subclass can have constructors just like they can have data members it's。It's again。

 it's like a basis of a real class， it's just something that by itself doesn't make a lot of sense。A。

So you could have a shape class what do we got here like a drawing class or a canvas or whatever。

 You could have all these different things that have these core information like width and height。

 but it's like unless like this type itself is too abstract to mean anything。

 So if you actually want to create something and work with it。

 you have to like inherit this and give it these extra features or be more explicit about this abstract classes aren't something we deal with in a great detail in this course。

 So we could obviously talk about it for like another half an hour， but。Yeah， that's。

 that's about as much as we kind of expected to know。

 It's like this is what a pure virtual function is。

 And if you have a pure virtual function in a class。Then it makes it abstract。Sir。Yeah。

I'm just looking at the time。 Let me just see if I think we should。

There's the static and dynamic types。I think we might leave it there for tonight。嗯。

Just because we're approaching the end anyway。Yeah， let's， let's。

 let's wrap up for tonight now and then we'll keep going， going into this stuff tomorrow night。

cause we， yeah， that'll be better。 So that's pretty much it for tonight。 then。

 are there any kind of lingering questions on stuff we've covered so far that people wantan to get off their chest before we wrap up。



![](img/b31fc10609875d7fa0dbda4825da5b81_163.png)

I'll just give you like， you know，10，20 seconds。Okay。

 well how about we just say any extra questions then if people have them just post on the forum or ask them tomorrow night but yeah let's wrap up early。

 I'm aware of late lectures no one really loves。So， yeah， well， thank you for part one of this。

 We'll keep going about this tomorrow and hopefully have some more fun。 And otherwise。

 I hope everyone has a great evening and。😊，stayay safe， ams the Covid ravaged Sydney currently。Yeah。

 have a good night， everyone。

![](img/b31fc10609875d7fa0dbda4825da5b81_165.png)