# 019：UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p19 19 CS169 19.zh_en -BV1UsB7YPEMj_p19-

And depending on how nice I feel， I may or may not actually take off points for selecting option D。

Or maybe。You can weigh against right okay， they're messing with me but they have they messing with me respect to the micro Yeah Yeah that might be too much work。

But。Yeah， cool， so since there's again like five people at the start。

 we'll just go through some things so for micro quizzes and for anyone listening online。😊。

There's going be five more and there's not quite five weeks。

 so I was originally going to do one today， but since there's a midterm， I'll just do it next week。

 probably on Tuesday， but that means one of the weeks will have two micro quizzes just to make it like an even 10 and。

Again， to reiterate， they are like correctness matters for microquizzes a little bit more than it does for clicker questions。

 But as long as you're completing them， you'll get most of the points。

 If you get them about half right on average， you'll get sort of full points for microquizzes。

 but it's not you know， really meant to be that stressful。

 The next few will be a little bit longer since we don't have a midterm。

 So they'll probably be about。F questions or so or five in a couple cases instead of three。

 but similar type of content。And then， yes， I do know that like a few people take them outside of class。

 so if you're taking them outside of class。Things may appear in your microquiz like memes。

 if I can tell that you're not in this room or whatever else。

 but please try and show up for them since they are for your benefit。

The next step I think project grading。For iteration one， while everyone's sort of getting set up。

 we weren't really like push on this， but by the end of iteration2。

 all these sort of automation and hooks that make ideally help make your lives easier， Travis。

 code climate having a Heroku deployment， all those things are part of the grade for iteration2。

 and I guess going forward， if you don't have a Heroku app up then there's no way that your customer can check out your application and see how things are going。

 so that's clearly a big red flag if that's not there at some point very soon。But the。

But Travis and Co Climate should be there as well。They're relatively easy to connect to GitHub if you have questions。

 post on piazza or use your team Slack channels there's a lot of mixed use to each other slack channels and that's totally fine。

 I suspect a lot of teams are using other communication that's cool。

 What I have seen so far in the Slack channels， I'm not like reading them。

 but when I went to add the bots the other night back into everyone's channels like a lot of people are sharing good blog posts and asking really good questions and doing the things that you would expect to do in like a development Slack channel at every real company。

 So there's a lot of good stuff happening there。 I encourage people to keep using it。😊。

You know what I saw like yesterday when I was just adding bots all looked really good。

 So thumbs up on all that on the bots the bot is now named stand up buddy because we've replaced it and then I didn't want to have name conflicts。

 but it should be in everyone's channel。 If you just type start meeting as a message。

 It'll have you go through the meeting。You're required to do this once pre durationration。

 but it is part of bonus points if you have standups more often and part of the thing with standups。

 especially since you are all students and you can't always do things synchronously it's perfectly okay to have a stand up where。

Only like two or three of your team members check in that day and have more of those as long as you always have at least one stand up where everyone checks in。

 So if you're working， you know， on Tuesdays and Thursdays and you want to just add some updates to keep a record of that。

 then that's a really good habit to be in。 this is。You know。

 when you're a professional software engineer， this can happen sometimes， right， you have standups。

 Someone is out， so they miss a stand up， that kind of thing or certain smaller teams may do。

More or less regular meetings， but feel free to check in yourself just as often as you would like to give yourself a sense of how things have been going even on a daily level。

 And of course， this is a class。 So we're not expecting you to go from you know。

 0% to 100% in one day， but。😊，Use that， you know， use that as a tool for yourself and certainly you know when I ask you if you've encountered any problems。

You know it's really up to your team to decide how to use that。

 but definitely feel free to say like I was trying to figure out how to write this query and it was really confusing and active record and that took a while or like I wrote it but I'm having a challenge with this kind of bug and so on you may have already told your team members that privately or just elsewhere in the Slack channel but like those are the kind of things that are really helpful in a standup because they show you as a team。

 what sort of challenges or what sort of recurring issues you might want to work on or you know if you are running tests and you're having challenges with flaky tests hopefully there aren't too many of those but all sorts of good things to list in your daily ish but not really daily standups and so there's that so。

😊，Today's lecture is continuing on our solid design patterns。

 we will probably get through the lid in solid， and then Tuesday we'll have a little bit more of just some of the theory。

 some additional tools a little bit again about the plan and document view of design patterns source agile。

 but we're going to continue on with our L in solid。So the L is the listov substitution principle。

If you've never heard of her， Barbara Liskov is a really amazing woman。

 she went to Berkeley for her undergrad in the 50s and 60s。

 got a degree in math because the CS department was not really a thing then。😊。

Or there may have been like the Es department as Eke started in the 70s so pre-es。

 but she did go to Berkeley， she then did her PhD at Stanford， but we don't need to talk about that。

 but she won a Turing award about if I can do math 11 years ago for her contributions not just the list of subution principle。

 but object oriented programming， she is one of the original inventors of the idea of data abstraction。

So a whole bunch of amazing contributions to the field of computer science。

 how we think about programming， and there's a pretty good Turing lecture online， it is 11 years old。

 so it's not like HD or anything， but the content is still good。😊，So if you're interested。

 I encourage you to find that。 So the lowov substitution principle seems fairly simple， but。

It has some implications。All right。A method which works on an instance of type T should also work on a subtype of T。

 So this is applied more generally than just the classes that we're talking about。

 But what this is saying is that if we have。A class。Let's call it car。

 we should be able to always replace a car in our application with a subclass of car。

 so maybe that's a sedan or a truck， and it should semantically still make sense。

What does this look like in practice？And why does this matter， So we have a rectangle。

 So in an application， maybe something that involves drawing or geographic coordinates。 you know。

 a rectangle is a pretty primitive shape type。And we know from geometry that a square is you know just a special kind of rectangle。

 right， it's a rectangle where the length and width are the same。

 but otherwise a square is a rectangle but a rectangle is not a square。

 and so it's like maybe natural to think that a square in our object oriented design should inherit from a rectangle that a square is a subtype of a rectangle。

😊，And。If this is true and we're following Liov substitution principle。

 then wherever we have a rectangle， we should be able to replace it with a square。

 But sometimes when we're designing our classes， we add additional methods。

 So this rectangle might have a method called make tall and skinny。

 So essentially if a rectangle is very wide and then we want to rotate it。

 so it's like tall and skinny something that a rectangle can do。

 but a square cannot whatops up there's no highlighting here。

 So this method on our rectangle make tall and skinny。Does not exist on square， right。

 because of square。Well a square can't be tall and skinny。

 it can only be square That's sort of the point of a square。 And when we have a method like this。

 this method， if a square inherits from a rectangle is a violation of the listov substitution principle and why does this matter Well this suggests that our square is not actually a subtype of a rectangle it is a very closely related but different type of object in in our system in our design。

 and so when we're thinking about how we design things and where we re them。

 we might want to decouple these to a bit。 So what does this look like in practice。😊，Well， again。

 on Tuesday。We said， you know， composing things is a good way to go if instead of just inheritance。

 and a lot of these object to design principles are about how。When you first learn oop， it's like。

 okay， I've got Java， I've got these like abstract things， I've got interfaces， I've got classes。

 like why don't I just go all the way out and everything is going to be a class and a subclass of another class and it's just subclass all the way down but。

😊，If you're not careful， overusing inheritance gets pretty messy。

One of the goals of thinking about something like substitution is， well。

 can we instead of using specific inheritance， can we decompose things into two classes that share some interface？

We have on the left here a really simple UML diagram that's just a rectangle to a square。

 so an open arrow direct inheritance。This square， if it were inheriting from rectangle。

 would have a make tall and skinny method and。As we said， a square can't be tall and skinny。

 so this method would either be a Nooc where it will call it and it does nothing。

Perhaps it raises an error， but more importantly， if you're reading a code that said square doMake tall and skinny。

As a reader of that piece of code， it wouldn't really make sense because you would be logically trying to do something that even if the code were to run would be probably unclear。

 And so one of the things that we can do，Is in our square class。

 instead of having it inherit from rectangle， it could have。

A property that's called rectangle that is an instance of the rectangle class where it delegates its methods to。

 and then it could define any additional methods。 So what might this look like in Ruby well。

Remember that we have。Or add our accessors and readers and writers， depending what we need。

 we could have a rectangle。 So our initialized function might look very similar or maybe not。

 but that's whoops， that's up to us。 And we could say that。A square has an instance variable。

 that's a rectangle， and we could redefine all of the functions that are in rectangle if we need to。

 or if we're doing sort of。The the rails and ruby idiomatic way。

 we can use our delegate method and say delegate area parameter。

 whatever our functions are to rectangles。 So if I ever do square dot area。

 it calls rectangle dot area。 And this is a way of from a class perspective not necessarily using inheritance。

 but having composition of different types of objects， so that when we read when we read our code。

 it's a little bit more clear， we're not duplicating any work。

 So we're still have code that is very dry， but it doesn't lead us to confusing object hierarchies so。

Let's do a clicker question and then we'll talk about this。so。

Something that we're not talking well let's not cover the entire question So true or false in a statically typed language if the compiler reports no errors or warnings。

 there are no listov substitution principle violations。

 so aesthetic statically type language like Java C++ we could even add fake statically typed languages like Typescript if you're adding that on top of Javascript you know if the compiler says that all of our methods are good。

 are we good from a class design perspective， that is the question and。Let's see， 20 people。

 it's probably not going to get much higher than that， one， two， three， four， six。Oh， not bad， okay。

 cool， almost to 30。And 1 E， so also 1 c。It's good to know。Three state bulls， no。啊。Not， well， okay。

 anyway， I meant to select B as the correct answer。Most people selected B。 So that is correct。

 If the compiler says everything is good， that doesn't necessarily mean that there are no substitution principle violations。

 If we are to go back a couple slides。And look at this UML diagram here。

 we could still define a maketonone skinny method on square such that our compiler would be really happy that our subclass has all the same methods that our parent class has。

 and things would compile， we could maybe perhaps even call that method。

 but list called substitution is not about what happens at just a static。

 does the code compile level， it's really the semantic meaning of your code。

 that when we're talking about the design of our objects。

 doest make sense that this method should exist on the subtype。

Does it make sense that this subtype has all of these methods that its parent has and if all the methods on the subtype have all the methods on the parent than then you're generally good so far list of substitution doesn't say anything about additional methods right our square method could have some additional methods or properties that their parent doesn't have so subclasses can be specialized right。

 they can have different behavior still， but they shouldn't be missing anything that their parents have and so。

Even a function that raises an error， if it's technically defined。

 is still a violation because the rule is not necessarily about what the compiler thinks it's about the spirit of the code and what happens。

 So there was an E， but questions on on this idea so far。Questions。You cool。So， again。

 with each of these， we have of some overview。 So again。

 lists of substitution that says an instance of。A subtype of。Can be safely substituted for。All right。

 I feel like that's reworked up instant， Yeah， an instance of a subtype of class T can can always be safely substituted for T。

 so we can always replace a class with。😊，It's with a parent type of that so one of these symptoms this is a term called refuse bequest。

 which is kind of a funny way of phrasing it， but what it's saying is if I have my square class and someone asked me to to make myself make tall and skinny a refuse bequest is the square saying you have requested that I called that I do this thing make tall and skinny and I'm going to say no I don't know how to do that and if you have a lot of cases where you have a class which is raising errors because things don't make sense for that type to do then this is probably a violation so you have classes where your overriding methods to raise errors is a suggestion that these two classes are too tightly coupled。

 they're not really interchangeable for one another。

And that's one way or one symptom that you should necessarily use a substitution for or refactor。

So ways of working around this composition， so like we said using a square who has an instance variable that is an instance of the rectangle class。

 so you delegate all the sensible methods to rectangle， but not necessarily every method。嗯。

And even if you're not using a particular subtype， you could choose you know specific methods to delegate without using rails delegate function。

 so the idea there is that as long as we have classes。

 we should be able to replace that class with a subtype and things should still work out。



![](img/36e9ebdaab989fc67d7b3690b36398f3_1.png)

![](img/36e9ebdaab989fc67d7b3690b36398f3_2.png)

And that is our first of our design patterns。So again。

 as we're going through these and as we're going through these principles。

 remember that the goal here is not to create a gigantic if then chart of like when I see this。

 I automatically have remembered how to you know which thing to look for， which thing to apply。

 especially since we're going through。😊，A half dozen or so of you know the 23 that exist。

 and there's a few more ones that have been sort of added recently。

 The idea is that if you're ever writing code and you see something that feels a little bit funny that you think。

 you know， it's not so clear the way I'm writing this will。A， I think that， you know。

 most code that's written once can be improved by writing it again just at a basic level。

 code is in many ways， no different than revising and editing your essay。

 It gets better with multiple revisions， but。And a meta level that as you go through these things。

 you're aware that there are opportunities and patterns for tools to look for。

What we're using as the I in solid is injection of dependencies。 Again。

 this is traditionally the D in solid， and the I is normally interface segregation。

 which doesn't apply as much。Excuse me， in rails。 So we're going to do injection of dependencies as D or excuse me as I when it would normally be D。

 So what is this so。A depends on B， but the interface B and implementation can change。

 even if they're functionally stable。 So what does this look like。

So dependency injection is a really useful pattern that you've probably used without necessarily realizing it。

 if you've ever done work on things like Angular， both version1 and the more recent versions。

 use dependency injection a lot， it's common， in Java in places。

 but it also makes its appearance throughout。Rils as a framework。

 So one of these things that we might have is our session store。 So we have。呃。

You know sessionsession in our rails apps and also in our Sinatra apps and there needs to be some place that we store that information right。

 if we have a session token for a user to remember who they are。

 we need to know where to save that information， where to get it back from and how that might work so。

Within our session store， there's a lot of different ways that we could store that session。

 so when we create our session store， we can inject a dependency on some type of object or class that defines how that session store should behave so for most rails applications。

 you can get by with not really having a server side session store you can just use a cookie store which says all the information that I need is going to be stored in the cookie and because it's HP we send down a cookie with each request when the server makes or with each response when the server makes or client makes a new request。

 we get that cookie back all the information is in the cookie our sessions work like they should。

But sometimes you need to store more information in a session。then could fit in a cookie。

 So there's things like a database back session store。 So there is。

 I forget if this is in railils by default or if it's a gem。

 but there is a session store that is active record session store。

 which uses active record and a sessions table to manage the state of where the extra information goes。

 if you've ever heard of Redis， which is a key value store。 So a。😊。

In memoryory database where each key would be a session ID and the value is as much information as you need to store about that session。

 there is a Redis session store that you could plug into for the overall session store class in a Rail app and so。

This is called dependency injection and when we implement this。

 there are going to be two very related patterns。Which are called the adapter in the facade。

This is also called inversion because the session store now depends on some additional class being passed in that is sort of unrelated。

 so the session store is now depending on our active record session store or our Redis session store or something like that even though it's not it's called active record session store but it's not going to be a subtype or something like that in a traditional class diagram。

 so note that this is you know just a general arrow pointing somewhere it's not an object oriented type arrow。

And so， in Ruby。These dependencies that are injected are commonly implemented as modules。

 not necessarily as classes， and that's just because in Ruby a module is a really useful way of grouping together a bunch of similar functionality that we're not going to classify as necessarily an instance or we don't need an instance of a class。

 in the same way。Technically speaking， you could implement them as a class if you needed to。

 but most commonly you'll see them as modules and Ruby has some really nice stuff where we can compose modules nicely。

 so what does this look like。And we have。A thing。呃 that。We might。

 if we want to refactor this and pull out， we have we can call this a session manager we can have。

Different types of session stores。 And so if we want to。

 we could add in another level of indirect where。We don't have to do this as a subclass or of a session store。

 but that is also an option here。 So what does this look like in。Some other cases in rails。So。

Active record also makes heavy use of dependency injection。嗯。Let's say in our application。

 we have a series of clients as objects and they might need to interact with different services。

In this case， we're going to be looking at email sending as a fairly common example。

 but there's a few other common scenarios you might think of different payment processors。

 so in your application if you have a bunch of different clients you might need to have different kinds of payment processors that make requests to maybe it's PayPal maybe it's Stripe。

 maybe it's some other just visa directly or something like that so you have a series of related things but different interfaces and so。

That is something that your application might need to handle in active record。

 they use adapters for different database types。 so in in development。

 most of your applications are using SQL light， which is a very lightweight in memory on your computer SQL database。

 but on Heroku you're using Postgres with active record and so each of these things are adapters that。

😊，In the case of rails an active record work completely transparently behind the scenes。

 you don't need to necessarily do anything as long as you say like GeSQL light in your Ge file。

 active record figures out the database that it should connect to and you say like GePG in your production group。

 and then it sets it up as connecting to a Postgres database。

 and so each of these adapters allow us to use an active record interface。

With each different kind of database， and though this doesn't happen very often。

 the really nice thing is if you were to switch your production system from MySQL to Postgres， well。

 its switching databases is always quite a bit of work。

 but you won't have to rewrite any of your active record logic， you just swap out the adapter。

 and your rare queries， your order by， your limits。

 any of the SQL like stuff that you would do in active record should just work。So again， another。

UML diagram， we could have。A client， some target and an adapter。

 which is possibly a subclass of a target and adapting which。

What this really looks like is we have our active record base class。It has an abstract adapter type。

 so we could skip this step depending on what we needed what we wanted to again。

 but the abstract adapter for something like active record just helps all the different possible active record adapters。

 So the MysQl adapter。The Postgress adapter it helps them sort of have a common interface that they should work with。

Each of these adapters then represents a specific database。

 And so the adapter pattern is really useful。 if you have a series of。But。

Types of different interfaces that represent a related concept。 So different databases。

 different email sending APIs， those kinds of things。

Would would be good fits for the adapter pattern and again。

 this is a place where we would delegate and inject our dependency and if we need to we could override behaviors in a subclass of an adapter。

So I mentioned email sending this example yesterday when I was fixing a standup bot。

 it uses this framework called botKt， which is technically JavaScript， but works the same way。

 each of these chat bot frameworks have adapters for the various services。

I have a bot that implements。You know， some stuff that in this case ask questions in Slack。

 But if I wanted to deploy this bot to a service like Microsoft Teams。

 or maybe even if you've ever used it like IRC， or guess now discord。

 all of these different chat services， have adapters where I could replace the adapter that the bot uses so that it connects to a different kind of service。

 And so that is。Another case where we see this pattern so again to continue on with another example email marketing。

 so there's lots of email marketing services you may have seen or received emails from them。

 constant contact and mailChimp are two big ones and for whatever reason you might have an app where the customer specifies how they want to send what service they want to use to send their email。

 maybe they're paying for it in a different way。Or something like that。

A customer in our application might have an email list。

And this could be some instance of an abstract email list where。This class。

Defins all the methods that we might use of sending email to that email list。

And in our setup for our customer， they can have an email sending type。So this could be。

A mail Chilist， or we could have a different customer。

Which has a constant contact email list and by having a general interface that is our email list。

 we can。呃。We can just swap these out when we need to。

 we could support two different kinds of services。That。

All work to that all sort of work in the same way。 So our app doesn't have a bunch of conditionals。

 Like the thing here again is that we want to be able to say。

 you customer do send emails or customer do retrieve email list without having to know or understand in our code which of these services is being used。

 So the adapter will wrap all that stuff up that is specific to each email service and make the interface that our application uses behave the same。

Adapters， good on that so far。Cool， so。A very related pattern。Is the facade pattern。

Fcades behave almost identically to adapters with a small tweak。

 which is that facades are commonly referred to when they are designed to hide or reduce the scope of some implementation。

They look a lot like adapters and they work pretty much the same way。

 but the goal here is that they are limiting the scope。

 so mail chip and constant contact each might do some specific stuff。

Slack has a whole range of crazy APIs that it can handle maybe file attachments or polls or something like that。

 And maybe other chat services don't have that stuff。 So you might also have a facade that。

Reduces the scope of the implementation， and this makes things easier to swap out。And basically。

 the idea here is that。Aapters can also be facades。

They are we're not going to talk about a facade as a subtype of adapter because that just gets weird。

 but they are related concepts in that they work pretty much the same way。

 but the nice thing here is that if we're going to call something a facade。

 what we're saying is we're specifically going to hide and limit the implementation of this external service so that the interface to our application is a little bit simpler。

 it defines only the things that we think we need。And by doing that， you get to say you。

 we have subscribe， unsubscribe and update， these might be our three actions that we care about。

Maybe there's you know one like sent to the entire list or something like that。

 but those three those three actions are a subset of all the possible actions on this API。

 So that means that our facade interface could work with more services because if we had to define something specific to maililChimp。

 which I don't really know offhand， what might be specific to MailChimp。

 but not another service since most of these have。Reports and things。

 but the point being that the facade hides and simplifies that implementation。We've got two things。

 we've got our adapters and our facades。😊，嗯。But in， so let's open this up if oh did that。Oh， no。

 it's open， I don't know where they the little。ATh went on my computer。



![](img/36e9ebdaab989fc67d7b3690b36398f3_4.png)

Or is it not no， it's not open yet， let's see， did it die again， Yes， it did。



![](img/36e9ebdaab989fc67d7b3690b36398f3_6.png)

Good job by clicker。Okay。What no where it did。

![](img/36e9ebdaab989fc67d7b3690b36398f3_8.png)

There you go so in our R spec controller we have it's stubbbing out active record base dot where so this is。

A common method of active record。And we want to fake the results of querying the database。 So which。

Which of these statements are true， the controller that we're testing is tightly coupled to the model。

 so we're stubing out where is this a sign of tight coupling？In a static language。

 we would have to use dependency injection to achieve the same。Task in a testing framework。裤。😔，Nice。

 a few more people have showed up。All right， it seems to be stabilizing there。

 so let's see the results Co， so we have some good distribution。

 Most people do believe that at least one of A and B are true。😊。

So we're going to reopen this discussion。 I'm going to start a new poll。 What I will tell you。

 So take a minute。 what I will tell you is that a is definitely true。

 So focus on whether or not B is true。 and we can talk a little bit about。

What we would be doing here。And how we could resolve this。Yeah。pretty。Or some little set action。

You could just like define the very。do whatever issues。Yeah。This was already。When we do wear it。

Like you have the stone。All right， take another 20 seconds or so and see if we can get up to 30 votes。

Different。All right， we are just shy by a few votes。多谢 al right。Okay。

 cool well there's always like one person who doesn't vote again。So。Let's see， so yeah， so C。

So the first one， why why are we going to say this is tightly coupling So this is one of those things where let's see if the next slide has new。

Okay， so the example that， okay， well。Pretend no one saw that because the example that I wanted to show is later in the slides that has a good example of this。

If a model excuse if a controller knows that it needs to query something with where。

 it does already know quite a bit about the model， like it knows not just that you know this controller has something like let's say orders。

 it knows that orders are a thing that is not just a numerable but has a type that can be passed into active record and that where is one of those those things and that where has some properties which means to not just query where and select a subset。

 it probably then has to know that what the columns and attributes of that model are and so。

If we're ever doing queries in our controllers， there might be a use for that for simplicity。

 and that is a hint for later on one of the questions but。

That does mean that our controllers know quite a bit about what's going on， so a。

 there is some tight coupling there if we wanted to。

 we could solve that by moving some of that query logic back to our model。嗯。

And that would solve the tight coupling issue。But so too， in a static language。

 dependency injection would be the way to teach us。 So if we are not moving logic。

 if we're not moving that where query from our controller to our model。

 then we would need to use dependency injection to replace。

Whatever active record base where is doing to return some different data。 So it wouldn't be。

 it's not up to our model to necessarily stepub out what where is doing because。

That would be a method on active record base。 We would inject some dependency that looks elsewhere for some of that data and。

There are testing frameworks in Java， which sometimes make this easier or harder。 There are。

 know lots of ways to do it。 But the point being that。If we have things that are tightly coupled。

And you're working around that and you're。Depenency injection is one way of working around some type coupling。

 although in this case， later on， we'll see some principles that。

Help us work around dependency injections。This question is definitely a bit of a confusing topic in that comparing static languages。

 which we're not doing， well， we're not doing it all in this course since Ruby and JavaScript。

 neither those are static but。It is a useful thing to think about。 So again。

 we have what is injection of dependencies。 we have a class that depends on the interface but we need to have that could depend on multiple interfaces。

 but we need some common form for that。 So again， this is a level of indirection。

 you may have heard the phrase too that there is no problem in computer science that can't be solved by adding a level of indirection that pretty much holds true for a lot of these challenges。

So the symptoms， if we find that we can't extend。You know。

 some aspect of a class B without modifying the code in A。 So this is。

In addition to possibly being a list called substitution violation。

 it is also very likely a violation of the On solid the open and closed principle。

 which you'll see is that oftentimes code that has design smells has related design smells for multiple reasons that's not always the case。

 but。😊，Oftentimes things sort of travel together。So how might we refactor some of this？

We can insert a new interface that gives us the ability to have an adapter or a facade between that our class and our interface and those adapters will use that common interface to。

To actually do the work of working with whatever external service that we need so again。

 that could be active record adapting to MySQL or Postgres。

 it could be a mail sending service adapting to mailChimp versus constant contact versus another service。

It could be chatbots adapting to different chat type of applications。

There's quite a few places where this pattern。Might be applied。And so。Again。

 it's just another thing to be aware of。Any questions on adapters and facades so far？Cool。

 so adapter like patterns appear in a lot of different places， and again。

 these are all forms of indirection for interacting with a series of objects。And so。

If there is one though， that is probably going to be useful in a lot of applications。😊。

Is the null object pattern， and the null object pattern is。A pattern that。In a lot of ways。

 sounds almost pointless。But really can simplify the logic in certain applications。

 So the idea is that we want an invariant to simplify design， but app requirements might break this。

 So what is a common case if you have an application which has a user that needs to be logged in so most rails applications called this method or use an instance variable current user。

And current user naturally is the current user who is logged into the application。

 the problem is that if we assume that current user is always there。

 what do we do when current user is not existent when they're logged out this is a case for the null object pattern really helps because what we could do is everywhere that the user might be logged out we could say if current user do nll and check for if they're nil and we could do this in 500 places because you're probably checking current user in 500 places in a large application that would kind of suck so how can we solve this in this example app we're calling the current user of the customer。

嗯。So what we do is we have a special instance of our customer type or a user type that we're going to call the null user。

 the null customer。 we could name it something different。

 but essentially being this is an instance of the object or of the class that represents someone who is always logged out this object can be used in a place where there's not something there in reality。

 but logically our code is much simpler。 So if there was if our customer was actually nil。

 than we could do if we did customer dot logged in， well。

 we would get you know method missing because Nil doesn't have a method logged in。 So what do we do。

 we define this null customer， we say logged in is always false。😊，Because， well。

 if you're an non MS user， you're not logged into this application。

In the event that we might access things like first last name。

 we can just replace them with some string anonymous。And if we have any custom attributes。

 so you know， is this customer a VIP？Maybe we have a session count， maybe we have。

 you know something else。 we can define default attributes or values for each of these options。

 so they're not actually user， so they're definitely not a VIP。 They're not log in。

 They're an anonymous user， so the anonymous user might always have a session count of zero。

 You get to define。Whatever logic makes sense for your application here。

 But the idea is that whenever you were to are to access this customer instance variable in your application。

 it is always either a real customer or a noll customer， which has the same methods。

 So in your models， your views， you don't have to do any checking for Nil。

 you check for what is semantically there。 if they are logged in or not。

 And it might be possible that you know who the customer is， but they're not yet logged in。

 maybe by some other reason， But in general， the noll customer or the noll object pattern is really helpful as a way。

Of checking for things so。Don't really know why the mail list thing shows up there。嗯。Oh okay， yeah。

 So one thing that we could do with our mail list， if we might have a customer that doesn't have a mail list。

 we could define a fake mail list that if we were to call those methods they would just do something sensible instead of blowing up。

 this is one option that you could， you can apply this to basically any kind of object and it really just depends on how。

You know， on how often and how widespread this class is， but user， customer。

 what some people sometimes refer to as the God object of your application。

 the one which sort of touches everything， this is a place where having a null object is really useful and that it can simplify a lot of conditional checks throughout your application so。

嗯。This is more of a useful trick than the necessity with the null object pattern。

 but is a cool thing。With a null object， we really only ever want there to be one of these things and no more than one of them right we shouldn't have 30 null users that could be different instances of a null user。

 so one idea is to have what we call a singleton ensuring that there is only ever one of this null user。

There's a couple different ways to do this in Ruby which will show you some new syntax。

 don't worry about the syntax， it's something that you could look up if you need either by referring to the slides or of course by googling it so Ruby has some nice solutions。

 you can use global variables， you can use a constant although it's hard to control where those are initialized。

 and so。There's an additional the goal here is though is that we have one one instance of this class that is not going to be modified。

 so there's a link to the gist for later， but the slide oh is it。O， the slides do not have the。

 where did that go？

![](img/36e9ebdaab989fc67d7b3690b36398f3_10.png)

So we'll open up this gist。Or pacee bin， not actually just， which yes， so in our customer。

 let's just give this a little bit more room。So in our customer class。

 we have a bunch of general active record attributes， so we might have a name。

 we might be able to set a name。And we can define a class method。

 So by calling customer with a capital C doal customer， this is。A class methods。

 so we're not going to be operating on a particular instance， and if we use a class variable。

 then we'll ensure that we only ever have one of these。😊，Noll customers is in existence on our class。

 so every time we call customernoll customer， we will return the same object and。In， in Ruby。

 we can dynamically define a， a class， which would be an instance。Of the customer。

 but have methods that are redefined。 So this is a class that looks like a customer。

 but we define specific methods， so。Whatever we define here。We could say， customer name is anonymous。

Customer， if we try to assign to the name， this may be a case where it's acceptable to raise an error。

 not everything or not every action will be something that you can handle perfectly gracefully right if you have an instance where。

In your application， something。You might happen that would truly not make sense like trying to save to an object that doesn't exist in the database。

 well you have no choice really but to raise an error there， you know， customer got logged in。

 of course， if this is a no customer should be false since they can't be logged in。

And so this is one way of creating a singleton class。 It is a nice handy thing to do。

 I will also say that some rails applications。Skip the singleleton idea。

 and they might have a guest user， which is just a subtype of user， would be one way of。

Just using a subclass would also satisfy the null object pattern。

 but that might not always be what you want in some cases， so this is some syntax which is useful。

 but not always necessary。 So you have that there， actually before I go back questions on this。

 this idea of a null object。牛裤。

![](img/36e9ebdaab989fc67d7b3690b36398f3_12.png)

So our final idea of， well， for now， of our patterns of indirection is a proxy。And。A proxy。

Is really quite a bit more general。It is a you can think of it as a wrapper for doing the tasks that we want to do。

 so we're going to intercept them and we're maybe going to modify the behavior a little bit。

 so we could proxy something by requiring authentication perhaps so maybe before we call some service we want to actually ask users to log into our application。

Also that we know who they are， we could proxy something by deferring the work so that it could be done lazily。

so。Maybe you have a thing that you want to call do send email， but send email is now。

A proxy because instead of just immediately sending the email right when that action happens。

 it does it in a background process or it does it on a separate server， something like that。

And then the other place where we see proxies， albeit not a case that you think of them this way our active record associations。

 so when we do Mo dot reviews，When we do at Movie。ware。

We use these things like an innumerable object right。

 if we say at movie dot reviews and we get a collection of the reviews。

 if we say at movie do where title is something X， Y Z。

 you know we can do movies do for each reviews do for each。 and so these things look。

And operate like innuable objects。 And they do。 But they are also proxy objects in that。

What active record is doing behind the scenes is it is not creating it is not running that SQL query until the very last second that it needs to actually run that query and return some data。

 So this is why you can nicely and efficiently chain things so you can do at movie do reviews do where review date is greater than you know three weeks ago。

You can do at Mo。t reviews where you know greater than three weeks ago。

 dot and where you rating is higher than three， and in each of those cases we have a proxy object which is adding and adapting our SQL query and then only when we try and access the data。

 does that query get run and so what's happening is there's a proxy behind the query interface。😊。

And for the most part， the cool thing about when these patterns are implemented properly。

Is that especially when they're used for library code。

 you don't have to recognize while you're using active record that this is a proxy pattern that's happening behind the scenes。

You don't have to know or understand that what active record is doing is delaying all your queries until it really needs to。

As the person using active record， in fact， you really don't need to care what it's doing。

 you just get to know that it works and it works in a way that you can change things nicely and it doesn't get slower so proxies are really useful tool and that they encapsulate some logic that might need to happen some behavior that we might need to change or overwrite without exposing that to the person who is reading or reading some code or using a library in those kinds of cases。

 so they are a really useful pattern to be aware of so。Qu about patterns。

And did the eye click app die in。Let's bet that it did， good job by clicker。

If anyone is looking for a business opportunity， here's a great one。😊，啊。

I have probably said that before， but it still hasn't changed。

 There's still a good opportunity there。 So the use of fake web to step out external requests in a service oriented pattern is an example of which design pattern。

 So fake web has been briefly mentioned once or twice before。

 it is also there are other gems like webm and VCR。

 you give it a call to an API So and in your rubby application。

 it will always return a consistent response。 So you don't actually have to use the Internet。

 So when I say。😊，Like in grade scope， a good example would be we have integrations that send grades to B courses。

So we have API calls not to exactly B courses， but to a Canva instance。

 and instead of making those calls on the actual server。

 we have a gem like fakeake webb that just returns a consistent response。

 so which pattern is this in our list of design patterns？So most people have a vote。

 which is pretty good， can we get a couple more？Go1 E， that's good to know。31。No okay。

 we're going to stop at 31 for today。Nice， where are we on time cool we'll just keep going along for time。

 but cool most people are correct。This is a proxy pattern。

 does anyone want to explain why it's a proxy pattern？A lot of you voted for being got it correct。

 So you know that it's the right answer。Some I want to make a case or B， yeah。

like use it stubs out like you send an actual like API request。

 but instead of it actually going to the real object。Theyig weather like interceptsed。Yeah， yeah。

 the intercepting part here is the key is that it's not doing exactly what the web request does。

 but it is returning some hopefully related data right。

 if you stepub out an API response with just some empty JsonN or some totally incorrect data that would probably be useless but yeah。

 it intercepts that request and it gives you something back。 So this is a proxy。

 the really cool thing about gems like fake web VCR is a really popular one， Webm is another。

 is that。😊，They all intercept the requests at the HtP layer of your rails application。

 So the place where it is actually making。A real HTDP call。

 which means that this happens in such a low level that regardless of how you make that HTDP call from your rails application。

 that JSON response that gets loaded from， well wherever it is。

 usually a file in your test suite works。😊，Pretty much as you would expect if you have an application that does test or that does rely on an external API。

 whether that's like you know a Google API for like getting some information from a Google doc or a Twitter API or a Facebook API。

 these are really useful tools to have to be able to run your tests without being connected to the internet and this is great in general as a tool because if your tests are not connected to the internet。

 they don't you can run them when you're like on a plane。

 which depending on how much you travel may be more or less of an issue but they are faster because they don't make the actual request。

 and they are less dependent on some service you know having needing to have an API token that is always secure or that is shared on your local machine across all the developers so。

😊，They are an excellent use of proxies as a design pattern。Before we continue on。

 any questions on proxies， adapters， facades， anything like that？Cool so。

Composites as a way of dealing with collections。This is another case where。诶。Youll have。Instances of。

 of objects that have。呃。A related subtype， but it's not quite the same。In our application。

 it's probably easy to just think of the actual example first we have regular tickets which again these could just be movie tickets。

 we have VIP tickets， so some movie ticket but with higher privileges maybe better seating probably a higher price and then we have these things which could be subscriptions。

😊，And a subscription is in many ways， like a ticket， right。

 it's something that we can add to our cart。It has a price。

 It probably has some times that it is or isn't valid。

 but what a subscription probably contains is a collection of tickets so。

How would we think about modeling this in an object oriented design that doesn't necessarily shoot ourselves in the foot by being ridiculously complicated？

One of the things that we can do is we can use what we call composite objects。

 So a subscription will be a。A composite of some kinds of tickets， so。

This would be like our base component， this might be a ticket， our leaf might be a VIP ticket。

Another subscription could actually inherit from a ticket。Which is going to sound a little bit odd。

But what it will do instead is it will maintain a list of all the tickets itself。

 so itll inherit from a ticket， but will it will end up containing other types of tickets as instance variables that it stores。

 So what does this look like in practice。So we have our common class。

 we have all the general instances， and then we have our composite which aggregates things together。

 so to continue with our tickets example，We have。Our regular ticket class。

 so this is an instance of a general ticket。We， depending on our application。

 maybe this would just be ticket， but for now let's go with having a really basic ticket parent class。

And this has all the things like add to order a price， maybe we have a way of refunding a ticket。

 maybe that checks whether or not the ticket has been used before it gets refunded。But。

Then we can have not shown here， but we might have a VIP ticket somewhere else， right。

 or any other kinds of tickets， maybe a child ticket， any of those kinds of things。

 and our subscription in this case is called multi ticketicket， we could call it subscription。

But what's different here， so when it initializes， it maintains a list of the things that it is going to contain。

 so in this case tickets。It lets people access those tickets and it defines a couple new methods。

 so it has an ad ticket method so that you know， we can maintain。

The list of tickets that are a part of this subscription。And。

Because this is a subclass of our ticket， it still needs to adhere to the same methods defined in the ticket class。

Otherwise， thatd be a list of substitution violation。

 But what it's going to do with these methods is instead of operating。On just one ticket。

 it's going to operate on the objects that it contains。What is the price of a subscription？ Well。

 this would be kind of an annoying subscription， but the price could just be the sum of all the things that the subscription is contained in。

 if you're giving people subscription as a web app， hopefully that is the sum of all the tickets。

 and then maybe you know some nice little discount for subscribing to things。 that's you know。

 generally how it works in practice。 if you have monthly billing， right。

 your subscription is usually for paying for a year is like the cost of 10 or 11 months。 So you know。

 maybe you're nice and you give some people a discount or maybe you're just like， hey。

 it's capitalism they can pay what they want。 And then you have your same addd to order methods。

 So tickets do each that are in the subscription， you could add them to an order。😊，However。

 this works。 And so a composite class is a really useful tool to be aware of。

 It's a nice way of having things that are coupled together， but not so tightly coupled that。😊。

You know that things get a little bit messy。 So there's a few useful tools that Ruby has。

 one of these is called single table inheritance。 This is useful for more than just composite classes。

😊，It does abbreviate to STI， so if you're immature like some of us at GrScope are。

 you can make jokes about your codeb having STIs， which has happened more than once， but that's okay。

So what single table inheritance does？You give the default is a type column。

 so we might have a tickets table with a type。And the type column in our tickets table might say things like regular ticket。

 VIP ticket， multi ticket， any other kinds of tickets we can think of。

And the cool thing about this is。😊，在。When you do this。

 rails will automatically initialize the right type of object for you。

 so as long as regular ticket inherits from ticket。

 as long as the name of the type column is regular ticket。

Then when that object is loaded when you say ticketsick doware or tickets dot find by。All。

Rails will automatically load the right kinds of objects in memory。

The particularly awesome thing about this。Is that。Let's say I do tickets doware you know date created was like within the past week。

 these could be all different kinds of tickets， you'll get an array or an array like thing right because it's a query that has you know a mix of different types of objects so what rails is going to do for you。

 look at the type column create the right instance and when used appropriately this makes your code a lot simpler。

It is also a case where you could really tightly couple thingst that should not necessarily be coupled together。

But it is a really handy tool for looking for sharing resources。

 sharing methods and properties of objects without necessarily having so many database tables or having them all behave exactly the same way so a really useful example from gradeScope。

 you know we have a regular assignment like and well， they're called PDF assignments， which is。

Another story， but they have a PDF template that gets uploaded and that's one kind of type of assignment。

 there is programming assignments that where you upload code to。

And each of those assignments use single table inheritance because they inherit from a general assignment type。

 and so this is a case where you have。Lots of different possible ways of structuring your data that make use of really handy tools and rails。

 the rails docs online if you just Google rails， single table inheritance are pretty good about this。

It is something that can get messy really quickly， so you might want to be careful with it。

 but it is a really handy tool， so before we continue on any questions so far on this kind of stuff。



![](img/36e9ebdaab989fc67d7b3690b36398f3_14.png)

![](img/36e9ebdaab989fc67d7b3690b36398f3_15.png)

So our last principle for today， we will get through solid and then on Thursday。Thursdayhu。

 on Tuesday， we will continue wrapping up some design patterns。

Our last one is the law of demeor again this is a principle which is relatively easy to check for。

 so if you're using tools like Reek and Ruocop， they will have warnings for this。So。

If you grew up in the 1980s， which probably none of us in this room did。

 don't only talk to your friends， not to strangers is the gist of this rule。

So only called methods that are on yourself that you've defined or that are directly on your friends。

 so what does this look like in practice and so we're calling methods not on the results returned by instances or things that we have。

 so it's easiest if we look at the code that's not very helpful。

 it's easiest if we just look at this code and that we have here so。



![](img/36e9ebdaab989fc67d7b3690b36398f3_17.png)

What does the law of demeor mean？We went to call methods only on our friends。

 so only on objects that we as this class know about so customerwall doc， if I am a customer。

 I should not know about the things that a wallet can do。

 I'm a customer so I might know that I have a wallet。

 but I don't need to know how my wallet operates。If we're like personifying this。

 it's probably a bad operation or a bad example because like money management wise。

 you should know how your wallet works， but that's beside the point for this code。

The law of demeor basically says that if I am doing a。b。c， or really， you know。

 you can imagine that if I know that customer。walllet。c， you could imagine that customer。walllet。c。

ware bills， if you could just continue this on and on。

But why shouldn't the customer know about the things that are in this wallet？ Well。

 that suggests that。We're， we're diving too deep into some abstraction for us。

 We're now making assumptions about。What this wallet is doing， the things that it has。

 and if that wallet implementation ever changes， which it could because it's two or three levels disassociated from this paper boy class。

We might need to。We would then need to update our paper boy class， so by following。

Clicked little too quickly， but by following the law of demeterter。

 we can refactor our code in a way that decouples things and makes it a little bit more clear what we are trying to do and what classes are dependent upon what other classes。

A customer cash customer cash， a customer class could just define a method cash， which is selfwall。c。

This directly addresses the violation because in our paper boy class。

 we can just do customer do cash。 So now the customer knows how much cash it has。

 The paper boy is only directly talking to the customer and asking the customer like， hey。

 how much cash do you have and。We're only just doing A dot B。

 so we have one level of accessing a method。And this is an improvement， because。

If the wallet implementation ever changes， we can just update this method without necessarily having to update our paper boy class and why is this useful。

 well， because if you are designing an application and you're like looking for the wallet and you need to make a change。

 well， you probably will remember or realize that a customer has a wallet if you especially if you're using a UML diagram to aid in what you're doing。

 which some people do， I personally don't， I just use the function。

 but you'll find that the customer has a wallet， you can update those methods。But。If you。

And then once you update the customer that cash method。

 all other locations that use that work correctly， so this is one way to directly satisfy that method。

 here is a slightly nicer way so let's zoom out a tiny bit。

The nicest way to satisfy a log demeteor violation is that。

We ask ourselves what are we actually trying to do in this case。

 Our paper boy class was checking if some cash was greater than some amount。

 what does this represent， Well this represents paying for a paper So how should we actually do this well。

We should have a method on our wallet that's withdraw。

 So we're going to refactor this to add a new method on wallet。

 We're going to add a new method on customer that says pay for something。

 And you can imagine that in our application， a customer could probably pay for more things than just papers。

And then our paper boy is going to ask the customer to pay for something。

 And so it doesn't care how the customer pays for something。

 It just asks the customer to pay for something and so。With the log demeterter。

 there are lots of ways to refactor things simply by just hiding the implementation of something that is always an option。

 it is always at least some level of improvement， but if you're really trying to go all out you might ask yourself what is the goal of this code。



![](img/36e9ebdaab989fc67d7b3690b36398f3_19.png)

And what am I trying to do， and that is one way to address the violation。Let's actually。

 we'll get to the observer on。OhNo， okay。😊，I was going to ask this question until I hit the right arrow key one too many times but。

Since I hit the right arrow key and we've got a couple minutes left。

ButThe question that we have to ask ourselves when we're looking at law of demeanor violations is if we have an order and a customer and we ask it。

 you know， order do customer do name， is this really a violation and most people would agree that if we say you shouldn't do A do B do C。

 this is a violation。 The question is。How should we address this？It is in a lot of cases。

 especially with something like aW。c， especially where that is customer。 name。

You could make a very good argument that says， yeah， this is a violation。

 but like nobody has time to be a pieerist about everything like I've got a whole bunch of code right and my manager is breathing down my neck。

 why don't we just live with it because customer name is pretty clear and for something like customer that's really not a terrible argument。

😊，But what you could also say is I should wrap this method in something simply called customer name and just call customer name in our order model。

It is if you have the time， a really good thing to do this because even something like a name may change in practice more often than you think。

 if you ever want to come to office hours and hear how complicated names have been in grade scopepe。

 I can tell you all the gory details， but suffice it to say things that seem simple at the beginning are liable to change。

 and so when you have options when you do A B。C。Remember that， you know。

 it's not a terrible idea to encapsulate that logic。

 And so we'll leave it at there for today and we'll pick up the last bits of design patterns on Tuesday。

 and then we'll get into some interesting stuff about DevOs。

 deploying applications and all that kind of stuff。After that。



![](img/36e9ebdaab989fc67d7b3690b36398f3_21.png)

![](img/36e9ebdaab989fc67d7b3690b36398f3_22.png)