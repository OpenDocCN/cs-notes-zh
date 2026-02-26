# 005：CSE 12 - Basic Data Struct & OO Design - LE -A00- - Lecture 5.zh_en - GPT中英字幕课程资源 - BV1zJQHYcE8g

![](img/a6ae58fe820288ff02cd4b2a5c333f8b_0.png)

嗯。I think that's the first thing。The second thing is this week。

 we're going have our first quiz during the discussion。So make sure that you show up on time。

Our T A Brenan， he will。Kind of administer the quiz and also stay behind。

 if you say I finished the quiz early， you can turn in your quiz。 That's fine。 And I I， we。

 we would like everyone to stay behind and well talk about the solution to the quiz。 Okay。

 So that's kind of the thing， okay。嗯。Third thing is， I think last week， for some reason。

The J unit test demo was not working， and I checked it。Still。

 I think V S code is giving me some warnings on these imports。

 but the tester seem to be working fine。 It just is complaining all these tests。Normally。

 if you run the testers in here， you should see。All the green arrows， it means the。

The test cases they passed without any issue。 But if you see any cross。

 that means there is an issue with a certain tester。 You should go there and check it out。

I think there another thing that I find out is， I think in one of the session that I may have。

Udated the the tester。 Ba forgot update the。C， S E power class。

 So that may have caused potential issues， so。I， I believe probably if this is something that actually runs on my machine。

 there shouldn't be any general issues with J unit test on your machine。

 Are there any concerns of J unit tests on your machine that people are struggling with。我。O。

All right。So。What we'll do this week is we will look at Java collections a little bit more and then review exceptions。

And also， can start with a radar。A real list is the topic for the next assignment。

 that's what we'll be looking at this week。So first thing。Java collections。

The reason why Java and C plus plus or Python are popular languages nowadays is because， I mean。

 they provide basic computing utilities， but also they give us many free stuff that you can use directly。

 right， So in Java， the collections is basically a collection of data structures that you can use for free。

Right， that's what it is。 So if you look at the hierarchy。

 this is the hierarchy of the collection framework。If you look at it。So it'。什ma么。嗯。

The overallal parent。Is over here。 This is a collection。 A collection is the interface。 And， in fact。

 everything to the left side of this doted line， they are all interfaces。They serve as the parents。

 right。 So they specify the abstract data type to say， okay， what a collection should always have。

 And from the collection， you have a set， lesson Q from here， you have a sorted set。

 you have a navigable set in here， you have a attack double ended Q。 So in here。

 this is what you have。 And for map， it is a separate inheritance hierarchy。

So all of them are interfaces， and they are all available in Java， okay。

And then the things in the middle。In between these。2 dotted lines。 The things in the middle。

 they are the abstract classes。So what they do is they implement part of the functionalities specified by these interfaces。

 but not of them。They leave some of the things to be implemented by the concrete classes。 Okay。

 so you have the abstract collection。 This is abstract class。 It has a few children。

The things on the rightmost region。In here， you have a tree set all the way to the maps。

These are the concrete classes that we can use directly。 So you say I need to create a set。 Oh。

 you can create a tree set， a hash set。 You can create a queue。You can create a deck， right。

 array rate deck。 You can create a read， link list， trim map and sector。

 So all these are concrete classes。 Okay， I don't know if Ive written them down。

 Let me write them down here。So these are interfaces。And alwaysway give me that。Zhong。

So these are interfaces。These are abstract classes。These are concrete classes。O。嗯。

I do want you to review a little bit。 Can you talk to a neighbor a little bit。

 Can you tell each other what's the difference between those three concepts。

When do I create the interface？When do I need abstract class。Right。What's the difference。

 What can I do with the interface， What I can't do， How about abstract class。

 How about concrete class。Can you have a discussion， talk to your neighbor。

 just move your chairs around， you can move the chairs， right？So what would you say。

What's the difference between those three concepts in here？Neighbors， people in front you。

 people behind you， people beside you。啊。Right。All right， so what can I do with the interface？

What can I do with the interface？ Can I create object out the interface。No， you can't。

 You can't instantiate things from interface。 Can I create a reference out of interface。

Can I create a reference out of interface。Yes， you can， right。 How about abstract class。

 Can I create the object out of abstract class。No， you can't。

 Can I create a reference out of an abstract class。Yes， right， so。Conquerete class。

 you can create reference out of them， you can create objects out of them。嗯。

Then what's the point of interface and abstract class。Can someone share。

 what's the point having them。I would assume we have learned about it in CSE 11。

 What's the difference？What's the difference if between interface in abstract class。

 they look similar。Anyone yeah。That's been interview。完了。Willion hair。Okay。

 so I can inherit from multiple interfaces， I can implement multiple interfaces。

 They serve as my parent and also， but I can only implement extend from one class as my parent。

 That's one of the differences。 What's the other difference between interface and abstract class。

Yeah。呃。Abstract class can have constructors， but you can't create objects out of them。嗯。

That's one of the things like in abstract class， you have concrete methods。 right。

 You can implement as many ambasadors as you want to as if it is a regular class。

 But apps interfaces， you only have those method decorations， right， you。

 you don't have anything concrete。That's the difference between interface and abstract class。

In general， if you look at the hierarchy in here。The interface they serve as the parent。

 and then the abstract class is the middleman。 and our goal in January is to have these concrete classes that we can use。

 You do not have to memorize this table。 Okay it's not something you have to memorize。

 It's more about you understand how the hierarchy is made。Any questions about this。

Collections framework。And this framework is being updated every year so。

I think this is the most up to date version I was able to make。If there's no question。

 let's look at the clicker question here based on this Ni Hartan's hierarchy。

 which one of them is correct。We can vote in the frequency is AC， okay， the frequency is AC。

 you can adjust your clicker。can do this。You have to look at the the。

The framework and try to answer these questions。Which one would you vote， Yeah， frequencies， A C。

 frequencies， A C。嗯。嗯。Make sure you have the right frequency， please。

Because if you don't have the right frequency， I don't even know this clicker exists。So。

Your frequency should be AC。Yeah。Alright， a lot of us are saying。E， a lot of us saying E。

Can you have a discussion which， which， which ones you think are， are all correct。

 Like more than one， a lot of thing are more than one。

 Which ones have a discussion with your neighbor。Which one。嗯。Alright， let's， let's。

 let's look at this one， okay。So， we say。The， the questions we have is number one。

Liinnk list is a list。Is that true or false。Link list is here。Here's the link list here。

 Li list is a list。Is that right， this is here？In other words。

 if I say one thing is the other thing is this is the parent that is the child。

 And you can see there is this inheritance relationship that goes like this。So a is right。 O。

 A is right。 Liless is a list。B， a rate list is a linked list， is all right。As， linkers， no。

 they are siblings。 they are。They're not of。Parent child relationship。 A list is a realist。

 It see right。A list is unrealreadist。This list is a radar。No， it's the other way。 right。

 So that's wrong。 A link list is a collection。A linked list is a collection。

 Collect is the overall parent。 So it should be good。 So I would say A and D， they are right。

 right A And D， they are right。当。With the right answer。Any questions for this？Next thing。

Which one of the lines are legal。Assuming that also have the default constructor。

 which ones of them are good。Think about it。 And let's。Bothote on this one。Which ones are good？

Think about it。Alright， again， a lot of us saying E。 a lot of us are saying E。

 more than one looks correct。Can you again tell your neighbor what do you think are the correct ones？

We kind of just share。What other things got correct？What is which ones are correct， right。

 which ones are correct？Move your chair around， talk to other people。嗯。All right。

 let's let's take a look at the first one。 Collect in C equals new list。 Can then do this。

Collection equals a new list。Collection is a parent of list。Can say collection equals the new list。

Yeah。This is an interface。 You can't create objects out of them。

 Although the inheritance relationship is good， but A is wrong。 A is wrong， okay。How about B。

 array array list a equals new link list， Does that look right？No。

Because they don't have an inheritance relationship。

 You can all always let parent reference to point to sub objects。Right， that's fine。

 But this is no good。How about this， my list equals the nu rateators， Is that okay？This part is okay。

 right A lot of the time we do this。 So use the least reference to point to a releaseius or linkus。

 So its。Pretty standard way people use it。D list， my link list equals the new link list。

 and then I create a collection reference。And assign my link list to it。 Is this okay。

What is the rule when I I do assignment。You have type on the left side。

The type on the right side was a requirement。The right side must be a easier relationship to the left。

 In other words， the right must be a sub or the same as the left side。

 So there must be some sort of easier relationship。

 And this easier must go from the right to the left。So， the。对于。The type in here is link list。

 This is a list。 So link list is a list。 So that's good。 In here。

 the type of this variable is a list。 The type of this variable is collection。List is a collection。

 That's also O， so。This party is also good。So E， again， is correct， is C andD。Questions for this。

All right。So。The next thing I want to talk about these exceptions。

 We should have learned about the exceptions in CSE 11。

 We probably didn't use a lot of exceptions in 11， right So 11 is。

 when you try to create something that attached to the file。 You have to watch out。

 There may generate some sort of file exceptions in CE 12， we use quite a few exceptions Basically。

Exception is an event that disrupts the normal flow of your application and。Like。

Why do we need exceptions？Why do we need exceptions， Can someone。The explain to the class。

 why exceptions are like， how are they used or why are they useful。It disrupts the normal flow。 Like。

 why do we need that。嗯。Any， yeah。It's， it's a little bit faster at run time。 I。

 I think not necessary， right， not necessary it's。It can terminate things a little bit nicer。

 but it doesn't actually speed up things。 right， It can make things a little bit smoother， though。

 Okay， that's not necessary the the like， for example， right。

 maybe I I should give you a concrete example。 I say have a function。 have a function。

 This function would return some value back as a result。And if something bad happened。

 I can throw an exception。 I can also just return a value。 That is weird。

Why don't I just use a return value。 Why do I have the user exception。Yeah。到企。装。这。Okay。

 so under certain scenarios， you may want to use exceptions instead of some return value。

 like some of the reason is like like one that was mentioned is like you would prefer to use exception。

 The other thing is sometimes you just can't find a weird value。 That that would indicate error。

There's just no such a value that you can find， right， Another way you can think about exception is。

 is another channel that you can communicate in between the functions。

So the functions normally you say you call function， you pass a value to the parameter。

 and then the function will return something back。 That's the normal channel。

 Exceptception is another channel that normally you use to communicate error state。

So it's just like you have a separate lane for the fire trucks。If you can afford it， why not？ right。

 So instead of having everyone using this return value to indicate something bad has happened。

 you just create another channel。 That's the exception。 That's the exception， okay。So in C C 12。

 when you start a P A 2 you say， I'm gonna write a rate list。 But if the user say， hey。

 give me the element at the location negative 5， what do you mean， there's no negative 5。

 You just give them an exception。 And so something bad has happened。

That's the idea of using exceptions in CSE 12。 So you don't have to create your own exceptions per se。

 but you're gonna to use more exceptions in here。 just to indicate whatever the user are trying to do。

 create some sort of error state for the data structure。Okay。Does that make sense。

Let's look at some of the reviews。 So this is more like a review for。Exceptions。

There are two kinds of exceptions checked。And unted。Can you explain to a neighbor。

 what is the difference between those two， What is a track exception， What is the untcked exception。

Oh he said， I have no idea。 I forgot。So what do you remember about the difference between checked and unchecked？

Have a discussion。 Have have a discussion。What was that？And what's the difference between them？

Allright， so what what is check the exception， check the exception are those exceptions where if your code has the potential to generate exceptions of those types。

 the compile actually force you to say， you must write code to handle it。

Either you can throw it to the call or use try catch block to handle it。 In other words。

 the convertr would force you to do it。What kind of exceptions are track exceptions。

 and then remembers？Is a reined auto bound attract the exception or no。Its not right， It's not is。呃。

Without the other exceptions， illegal argumental exception is that。I attract the exception I now。No。

 right。 So now how do I tell， In fact， there are very few check the exceptions。

 There are very few check exceptions。 Like， for example， a lot of times， you have the file。

 I O exceptions。You cannot read the form of file， those exceptions that are checked。 In other words。

 there are a lot of common mistakes that people have encountered as they deal with files。

 So competitor is trying to force you to do it。 Basically the other thing is your own exception class。

If you create your own exception， you say， I'm gonna throw those customized exceptions。

 You have to handle them。 You have to handle them。Everything else， they are unchecked。

 In other words， the competitor doesn't care。If you have a indexd out of bound exception。

 be my guess。Why， why， why is the compile so irresponsible。Just like， as the instructor I say。

 you fail the class。 I don't care。 That's not good。 right， The comparison。

 you have an index out bound。 I don't care。Why not？ Why doesn't compile care about that？

The competitor is our friend。 Why doesn it care about our race out of bound。Yeah。Right。

 so the idea of the compiler not caring about those exceptions is not because it doesn't want to be friendly。

 It's just because those errors， those exceptions that are generated by the bugs in our program。

RightIf you say I'm writing a for loop to go through the array and then bang。

 my array is out of bound。 It's because something is wrong with your code。

It's not going to try to force you to say you take care of the error when your code runs。

 you should just fix your code。You should fix your code。 That's the point。

 So for all those uncheracked exceptions， the compiler doesn't give you warning allow you to basically。

 they allow your code to crash。It is because。Those are due to bugs in our program。

 We are supposed to fix them。 We are supposed to fix them instead of hiding them， using handlings。

Okay that's that's why just like sometimes you may see a class that is super hard for you when you're in high school say。

 I hate this class， but several years down the line you think about it。

 maybe you learn the most from that class， you know， so you never know， you never know。

So when we deal with exceptions。You make sure that in general， we try to handle it。

 and you should be comfortable generating exceptions and handling them。

let's look at some of the examples in here。 I will start with some of them。

 and then I will leave you to work with and neighbor to finish the rest。 Okay。

 so let's start this one with a public class。Exception worksheet。 So we have this main method。

 main method。And I would want to generate some sort of arithtic exception。In this trip block。

And now I would try to catch， catch it。What code would generate the arithmetic section？Yeah。The by 0。

 Okay， here we go。 I's say in x equals to 70 by by 0。And the competitor would let you pass。

 In other words， I don't need this try catch。 I'm just trying to demo here。 In other words。

 in your code， you can say in70 by 0， the computer would let you go and your code would crash It's because you are not supposed to write something like this。

And if you're called crashsh， you go back and say， oh。Any need fix this thing。

This one would generate the arithmetic exception。 How should I use catch to catch it。

Or should I write in here。Can I just say arithmetic exception？E， right， That's what I need to do。

Arithmatic exception， E。Does this make sense？Okay， so that's what I want you all to try to do。

 You can work with your neighbor， and let's finish。As much as you can。On this worksheet。

 I'll give you some time。 Okay， I'll give you five minutes。

 Can you try to write it together with a neighbor or by yourself。They say， how about the next one？

The number format exception。 I want to。Okay， all the exceptions we are generating here。

 they are all unchecked。I mean， technically， you don't need to try catchch。

 I'm just trying to ask you to think about when do I see this kind of exception in here。

So what would you write for each of those cases？嗯。Shouldn't take you too long，All right。

Let's try these things。So number format the exception。 When do I see number format the exception。

When you try to。For example， read something into your program and whatever the user entered is is wrong in the wrong format。

 or when you try to parse some int。 So there there are different ways you can do it。

 you can say int X equals to integer。Dot parse。Innt。You say water， then you're in trouble。

You're in trouble， you hear？That would give you a number format exception。 All you can just do is。

 throw new。Number format。Exception。You can just generate yourself。

 You do not have to rely on other programs to generate it。So。Either way， right。

 either either one would work。 either one would work。Any questions for this？Then in here。

Capture the number format exception。Are we good。你说。All， next one， a rein out the bound。

 This is where are expert on this one， right， of have made our fair share。Of。Exceptions in here。

In shorter bracket， AR， R equals a new。And。5ve。And I say A， R， R 20 equals to 7。短啊。

Will give me the exception。And then you， you capture it， right。 So rein auto bounds。That would work。

Any questions？So you just use the index that is longer than the array。 You see that exception。No。

If there are multiple exceptions， in other words， this code may generate something。

That may be multiple kinds of exceptions， like you say arithmetic exception。

 if this is the the arithmetic exception or if it's just an exception。 Now， if have these two cache。

 you have multiple cache， how are， how do they work。Multiple catch on the exception。What， what do。

 what does it do， Do I match the first one， And then the second one or it doesn't matter。

Does the order of listing these catch clauses matter？Doesn't matter。I hope we understand this。

 did we learn about this in CSE 11 exceptions？Did we。嗯。You we learn about the exceptions， Yes， no。

Can you give me a feedback because you are give me this blank face。 I have no idea。I have no idea。

We have to make sure that we learn about the exceptions。嗯。Okay。

 it looks like a majority of you have said yes， a majority of you have said yes。In。

 some of us saying no。O。So all right， looks like。We're getting this one were getting this one。

All right。If you look at the boat， a majority of us saying yes， right， So I'm not too concerned now。

Frequencies AC， frequencies AC。We use the same frequency every day so。Changing to other things。Now。

 E5 several catch classes。What's gonna happen is if you throw some sort of exception。

 the first catch will be match。 If the first catch does match， you try to match the second one。 Okay。

 so the order would matter。 So I want to do something that。It is caught in the general exception。

Not by this one。So what， should I throw。I can just do a throw。 What should I do。

Anything that is not arithmetic exception。So it's through new。A raind outer bound。

It just these exception names are too long。It's like you're writing an article。

And you just generate this exception iss going to skip the first catch and then be caught by the second。

Are we good？Alright， so in here， you want to throw your own arithmetic exception。

One thing you can also do is you as you throw these exceptions， right。

 they throw new arithtic exception。You can give some messages， right， You can in here say my own。

 for example。You can attach some messages。As。For the constructor of the exception。

 So when you caught it。You can figure out。 So E dot get message would be my own。

 So you can customize the error message a little bit too。 when you are creating your own exception。

Okay。Are we good？The last part is。Checked exception。So。

What I want to do is I want to generate a code that actually would， would generate this。

Check the exception， okay。So I have this try clause， try I'm calling this function。

Check the exception with throws。 So this is what we have。And。This part is required。 In other words。

 if I'm calling this function and this function has the potential to generate a track exception。

 I must do try catch in here。So as I'm trying to write this one。I， I can just do this， right。

 So track the exception as a new。File， not found。Exception， right I I can throw this one in here。嗯。

What is this plan for？Public safety avoid this function name。 What is this plan for。

 Do I need to fill anything in there。Can you talk to your neighbor。

 What do I need to fill in here or if anything I need to fill in。

This function has a potential to generate a checked exception。 What do I need to fill in in here。

I said you don't need to feeling anything at all。What would you do。Do I have to fill in anything in。

This blank。Can I leave just this empty。No， you can't。 You can't， right。

 Because if your function has the potential to generate a check exception， you must specify it。

 You must say。This one。Throws。File， not found。Exception。Because this one' is checked。

If it's unchecked， you can leave it empty。 For example。

 you can say this constructor may throw rein out bound exception。

 You do not have to specify this throat clause as the header in the header of the function。 you can。

 but you are not required to。In here， you have to。Because this exception is checked。系。

Any questions for this？Yeah。5 I O exception is also fine。 You can just say throw the exception。

 That's also fine。 right， So whatever you decide to do。

 it must kind of include this case where your code may throw this exception。

 That's why it's called checked。😊，Right， so when you you have a function that may generate the check the exception。

 when you call it， you have to put it into a tricach， or in the corridor of this function。

 you have the throat clause。Right， so for example， if I remove this try and catch。

 if I get rid of them， I just call this check the exception with throws。

 If I just call this function inside May， My may have to have this throws clause in here。

 My may has to be， say throws file now found the exception。If you don't have the try catch。

 why call this function。Any questions for this。Allright， so this is a quick review of exceptions。No。

We have five minutes。 let's， let's jump ahead a little bit in here， okay。So。

I want to leave the the real list。Maybe on Wednesday in here。So what。

 what I want to do is I want to just practice J unit testing a little bit more because you're gonna start to write it starting on this Thursday or Friday。

 so。We wrote a person class and we have the following methods for person。

 this is on the last page of the handout。嗯。So the field is age in teacherger。 Na is the string。

 heightight is a string in the format of feet。Apostrophe inches。My 5 slash0，3 instance5 feet。

3 inches。Where F is one D number and I is a two dig number。 web a default constructor H is0。

 name is now height is now， and the web a constructor takes in three things and a function called get name length returns the number of characters in the name。

Through the exception， if the name is not。Right， so we just have a bunch of。

Two constructors and a function for this person class。

What we want to do is assuming that class is there or it is to be implemented。

I want us to develop habit of。Writing some testers， writing some testers in here。

So what I want to do is I want to test the default construct。What would you do in here。

 What would you test， I created a person object using the default construct。

 Can you write down what do you want to test on the worksheet in here， Like， what would you do。

We have a name。 We have a height。We have our。Name， height and H。Okay。So what would you test in here？

We should。Test all three of them， right， all the three instance variables。 So if I want to test H。

What should H be。0。RightAnd you want to write the the expected value on the left。

 whatever you get on the right side。 Okay so it should be0 comma reference out H instead of the other way around。

So we say a third。Ecoes。And then， now。Rough dot height。A third equals。No。Rft dot name。

So those are the three things I should definitely verify。Right。So not just one of them。

 all three of them。If you have time after a class today。

 try to finish the rest of this worksheet on J unit。Once we come back on Wednesday。

 we will finish this part pretty quickly， and then we will work on。The the array list。

 which is our first data structure。 Okay， So we are done today。 I would。

 I would turn on the clicker again if you didn't get time to click in， you can click in。 But again。

 I don't think we are counting participation today， right。

 So youll start next week or start next week， okay。😊，All right， we are done this morning all done。

I was having like trouble use。あそね会で。All right， I'm still living confused this is my first time。

It's clicking。 We are not coming yeah。Work。I know， but like my answers couldn't see。だメですね。

We are not we are not counting participation today or We are not not in the first two weeks。

 We'll start next week next week think。That's good。 That's all good。 So my。If you voting， yes。

Oh and how can we see that like you have a weird one so it's an old version right I know。

nots paradigm， right？I've never used this thing before， so yeah。I don't know， I can check。No。

 I don't think it's on。 I don't think it's。Maybe I think people are both you know。

 what's going on with other guys。Did you adjust the frequency？ Yeah， A theory， right。A， yeah。

 think you should be good。

![](img/a6ae58fe820288ff02cd4b2a5c333f8b_2.png)

Then you should。