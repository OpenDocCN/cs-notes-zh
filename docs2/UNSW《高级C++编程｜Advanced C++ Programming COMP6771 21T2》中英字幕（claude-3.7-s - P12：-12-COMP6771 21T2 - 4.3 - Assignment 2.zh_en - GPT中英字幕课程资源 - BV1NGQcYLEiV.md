# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P12：-12-COMP6771 21T2 - 4.3 - Assignment 2.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Alright， so let's， let's take a really quick look at assignment 2。So。With assignment2。

You're spending all your time writing in class。

![](img/76e53c773e1ddd81397ade36aa5a4121_1.png)

That class is defined。It include。S，7，7，1。Euclidean vectorto。Go damn it。

And this is the whole class as we've given it to you。

 It's wrapped in a namespace just like assignment1。And then we have two classes inside here。

 One is a Euclidean vector error class that inherits。A runtime error。 So this is a custom exception。

And you can see that we have。Essentially said that when you construct it。

With a w that we just delegate that。 it's a delegated constructor to the super types watch。嗯。

So pretty much just a， pretty much just a pointless。 It's nearly like a type def's it's。

It's just here to give your exception and name， even though it just totally inherits the runtime error type。

And then we have an actual class， which is the data type you're working with。

 which has a public section and a private section。And the private section just consists of this one。

Dotta member， you can add more。Which is a unique pointer， which is a topic of next week。

And it's not going to slow you down becauseuse the unique point is are a bit of a separate concept。



![](img/76e53c773e1ddd81397ade36aa5a4121_3.png)

Your job in this assignment is to write a series of constructors。

You need to write a constructor that has no parameters and constructs a Euclidean vector。

 You need to write a constructor that takes in one parameter and constructs a Euclidean vector full of zeros that many times。

 So Euclidean vector 10 would give you a vector with 10 zeros in it。

You need to have a constructor that'll do。Int amounts of doubles。 So if you do 10 and 1。1。

 it'll create a vector with 101。1s in it。We also have other things like。Iterators。

 So we want you to be able to pass in an iterator to the beginning and the end of another。

Container and construct a Euclidean vector。 So if you have a vector or a list or a wubly link list or anything。

 you should be able to give an iterator to the start and the end of that and andly populate your Euclidean vector。

We want you to be able to give your Eucldia vector when you construct it and initialize a list。

 just like a vector， and it will construct it。 This one we haven't done much in lectures on。

 but it's pretty straightforward to figure out if you read through the docs and look at some examples。

 So that one's a little bit of fun。 and then we have copy and move constructors。

So copy and move constructors are。Probably a little bit more of a topic for next week。Yep。

You can do them now， of course， but like that's kind of what we talk a bit more about next week。

There's some information about what we expect you to do for the destruct。

And then we get into a whole bunch of operator overloads。 We have operator equals， operator。

 we have a copy assignment， a move assignment， we haven't done move assignments。

 that's next week as well。 We have subscript， We have unary plus negation， compound edition。

 like all the different kinds of operators on it， and then we have both a vector and a list type conversion。

Right， so these are all different ways of like converting your Euclidean vector to a list or to a vector。

So lots of different operators here。Besides those we also have some member functions that aren't operator overloads。

 they're just functions that includes the dot a operator， which is similar to a vector。

 another dot ad operator which is for noncons， I believe。

 dimensions to figure out the size of the vector， and then we have some other operator overloads that are friends。

 plus minus equals times， output stream， stuff like that。We also have a few utility functions。

 which this part can be a little bit challenging for some。

But these are essentially functions that are kind of like friends。 They're not really， well。

 they're not really friends they're。They're still inside the。The 6，7，7，1 name space。

 but they're not part of the class。 So these are things like finding the Euclidean normal。

 the unit vector， the dot product。 If these are concepts。

 these are concepts that assume from your time doing maths。 But if these things kind of。Elude you。

 because you just don't。Remember them very well。 then you can obviously just touch up on them a quick Google will help with that。

嗯。There's a little bit of information on your data members here。

I'll do a little bit quick demo about that。 just to fill everyone in。 That's just saying。

 what do we expect you to have in your private data members。

 Then we have a bit on throwing exceptions。 So we expect you in this assignment to throw an exception。

 which is your。The custom defined exception that we put in your code。

 and we expect you to throw it in a series of cases， so。The last column in a lot of these tables。

 it's like the name of the thing， the operator。A description of what it does， how you use it。

 And then an exception。 And if it says N A， then it's it doesn't throw any exceptions。

 And if it has stuff， then it potentially throws exceptions。 And you can see that this one。

 let me find an easier one。 something that's really obvious。Yeah。

 so let's say you're trying to add two Euclidean vectors together。

When you try and add two Euclidean vectors together。

If the dimensions of those Euclidean vectors aren't the same， I。

 if you're trying to add a Euclidean vector with three items to one with four。

 then it should throw an exception。And what it's saying here is that if。

If a's dimensions is x and B's dimensions is y。Just as variables。

 you throw an exception when they're not the same， when the dimensions are different。

 And then what you throw is dimensions of L H S X and R H S Y do not match。 Now， I make this really。

 really， really clear to everyone。The X and the Y in all of these exceptions。

 any time there's kind of like a wild card here， like index X， they're all pretty much x and Y's。

 Any time you see that。We're actually expecting you to replace that with the number。

 So in this one here， dimensions of LH， LHS and RHS。



![](img/76e53c773e1ddd81397ade36aa5a4121_5.png)

We actually expect you to be like three and four， so the actual exception text we will see from you will look like that LHS 3 and RHS 4 do not match。

That's what we expect。

![](img/76e53c773e1ddd81397ade36aa5a4121_7.png)

So you'll be throwing exceptions in your class， and when it comes to testing。

 you'll be catching and testing exceptions。

![](img/76e53c773e1ddd81397ade36aa5a4121_9.png)

Hia。

![](img/76e53c773e1ddd81397ade36aa5a4121_11.png)

Other notes you can read through these Conness， as I said yesterday。

 we expect all of your member functions to be con。 They should be cons。

 they' got to be constant if they shouldn't be cons。

 they shouldn't be in some cases you'll want to do both。

F I sense says would we just throw the inherited runtime exception， No。

 you throw the exception that we give you in the code。

So we' provided a Euclidean vector expression cost for you to throw when we say you're welcome to throw other exceptions if you feel they're appropriate。

 I mean， I'll clarify this right here and now that sentence isn't actually like you can throw something else if you want to throw it instead of that that's saying。

What they's saying is that if you want to throw exceptions in other cases than the ones we specify。

 you're welcome to do that。So if you want to throw exceptions for。You know。Not allowing， I mean。

 I don't even know。 I think we added that just in case someone asked the question。

 but generally speaking， there's no real cases for that。

But if you want to add an extra exception case in you can， but yeah。

So it is throwing the Euclidean vector exception， which is defined in here。 So that's the error。

 So you'll be throwing Euclidean vector error。Anything that all I'll say about no except is that no except should be put on every single function that has a no thrower guarantee。

We expect you to test。The rest of the criteria is very similar to iteration one to assignment1。

 so I don't think you need to worry too much about that。

The last thing I just want to show you is probably on this smart pointer thing。



![](img/76e53c773e1ddd81397ade36aa5a4121_13.png)

So section 7 here， we talk about。We want you to do this。Now。Let me just find a random。

Let me just make a file here really quickly。Oops。That's just。Yeah。

 this isn't gonna to be anything exciting。 so'll just be like int mean。



![](img/76e53c773e1ddd81397ade36aa5a4121_15.png)

Now let's just add this to the CMake file， I'll call this one。



![](img/76e53c773e1ddd81397ade36aa5a4121_17.png)

Call this one Pacin in， in memory of Pacin。And then I'll just add this to the CMake。

They make it executable， and then we'll just call it via in， and then we'll reload the window。Oops。

 reload window。Okay， so。My P S dot CPP。In C plus plus， I can， I can do this。 I can see， double。

 Oh my God， I've already forgotten how to。Auto vehicles。Double。

I don't even use roa rays in C++ anymore， so I've just totally totally mind blank how to do this。

Let's just try this。Sure that's not the right way to do it。Certain。In fact。嗯。Maybe you just can't。

 I don't know。 How do you construct a double array in C plus plus， Well， I mean。

 you can probably do this， at least， right。I didn't。 I didn't intend to do this。 I just thought。

 let some。Someone probably knows'ca they've tried it out。 This。

 This is what happens when we ban the use of raw C style arrays。In a course， I totally forget things。

H。How do we specify the size。

![](img/76e53c773e1ddd81397ade36aa5a4121_19.png)

C plus plus double array。So， I did。I I don't want to mal something。

 I just want to put it on the stack。

![](img/76e53c773e1ddd81397ade36aa5a4121_21.png)

The weird thing about C++ right is that remember in C++ it's like when you say auto S1 equals standard string like this。

 you are creating a stack object， when you say auto S2 equals new standard string。

 you are malicing a new stack object。Right。So we don't want to go anywhere near the new syntax at the moment。

嗯。Yeah， you can do double B 8。 I just， I thought there was a way to do it with auto at the front。

 but I'm probably just。What。Sorry， give me a sec。 Oh， no。

 I have to turn this off in all your code bases。 I'm sorry that I'm sorry that I release this。

 but didn't realize Kang tidys turned on in your sea make list。

 So you're gonna get a whole bunch of random horrible errors。

 I just need to disable this and deploy a change。 So yeah， sorry。

 I'll just do that after the lecture。 But that's why you get these stupid errorsca this is a thing we had last time that we wanted to get rid of。

 So I'm updating all the old packages。 And I think me and Nathaniel just forgot to do that one。

 So that built fine and。This program runs it says hi and then it prints out one because that's what I set it to be。

 I'm pretty sure you're able to do this unless I'm crazy。Let's see if I'm crazy。Probably crazy。No。

 we turn cllink tidy off for the entire course。 It's off all your other reos。 I'm pretty sure。

Pretty sure。Yeah， should be off。That odd'll turn it off。Oh yeah。

 you probably don't need that nolin comment anymore， though it' it's still good practice that。

 I mean， not really， it's still good to make clear that like this is not good。

 but I don't really mind。So I mean， if a compiler compiles， that's as simple as it is。

With double arrays in C++ you can do something like this。

 though what you often want to do is kind of mallic these things。

 but without getting into that because it's all next week's stuff。

 the thing I want to explain to you。Is that if you have something like this way， you have， say， a。

A double array with two items in it。And then on this line， I'm gonna to make another thing called。

AuttoC equals standard and make unique。Double2。I'll keep this even simpler。Like that。

The thing I want to stress to allow you to start the assignment and not worry about this for a week is that。

This here is a very clean abstraction， such that you can work with these two things interchangeably。

So with this simple program I have here。You can treat。This object。

 see here as if it is an actual double array。Okay， so even though the spec has this funny little line here。

 which needs some context， you can treat magnitudes like it's a C style double array。Now， again。

 I'm gonna get this question。 People are like， oh， heyden。

 you didn't let us use C style arrays in assignment1。 and we lost marks on it。

 Why are we using it now， And the answer to that is simply like， you know。

 how do you think vector works， How do you think。String works。

 They're all primitive arrays underneath， because they're fast。

But that's because you're not writing libraries。So there's all these great abstractions out there for you to use。

 so we don't want you using raw arrays， but in this assignment you're actually writing a library。

 you're the library writer in this assignment， So like what are you going to do use a vector。

Vectctor has costs involved。 You know， it's， it's a lightweight abstraction。

 but it's still somewhat costly。 So we're writing that。嗯。

So you're creating this Euclidean vector type。That's actually under the hood。

 G be a sea style primitive array， a double array。嗯。Yes， and we'll talk more about this next week。

 But the point is that this line here， C， just like magnitudes。

 you can treat it like it's a double bit like you can literally treat it like it's a primitive array of doubles。

 You don't need any extra knowledge you can index it。 You can assign to it。

 you can loop through it whatever there's like a few things that you need some context on particularly copy and move assignment and construction。



![](img/76e53c773e1ddd81397ade36aa5a4121_23.png)

that's it。 the rest of this you can just go ahead and do。 so don't feel。

 don't feel handicapped in that way。That's actually pretty much everything I wanted to run through for assignment too。

Are there any last questions people have about assignment to that we quickly answer now。It's not a。

 So the question was， so it's a matrix essentially。 I mean， it's not a matrix。 It's a vector， like。

Different things。 So like。You know。That's a matrix。 This is a vector。 These a vectors。 It's algebra。

 sure。Dvanche says， man， you probably like why are you ignoring my questions tonight， I'm sorry。

 that was just dumb luck。There's no time or space complexity checks for assignment， too。

 I think the only exception to that is。嗯。But sorry。

It's not that there's no time or space requirements， it's that it's very light。

I'm trying to find out where the line is， I think I feel like there was one second。嗯。

Maybe I took it out。The thing is that。第二。WeWe will expect all your tests to complete within a second。

 within one second。嗯。But like these operations are all quick。 they're not MP complete problems。

 They're not n squared problems。 These are just like simple operations。 So yeah。

 there's probably some limit to time。 I don't know what it is。 But the point is like。

 we're going to set a limit where if you， if you hit that limit， you did it really。

 you just did something stupid， you know， And I mean。Is in like we'd look at your code and be like。

 oh， no， that's that's just。You're malacing 7 different things。

 and you got full loops going through it。 Is there a time concerntrain。 I feel like there's a second。

 I feel like we said something like you have a second， but a seconds like like。

 that's like 100 times more time than you'll need。I don't know where it is。Maybe its10 other notes。

I don't know。I， I thought I remember reading it recently。Anyway， like whether it's there or not。

 there's no， there's no。There's no time constraint that requires you to do something special。 I mean。

 in every assignment， there's a time constraint。 Like we're not going to let your assignments run for like。

Three hours， so。Yeah， there's effectively， there's no time constraint。 Spea of that。

 your assignment ones have nearly finished running。 It's only been three days。

So your tutors are starting to mark those now。Anyway， any last questions？

Can we make an iterator out of the array pointo？嗯。That's an excellent question。A no。

 And I'll add that to the spec becauseuse I remember that some students asked that same question last year。

 So one thing you can't do in this assignment， Maybe I already added it。

 but I didn't think it's there is like。You can't。You're basically banned from using STL containers。嗯。

No， it's not written there。 but this was kind of implied。

 And we never had problems with this for a few years。 And then someone was just like， oh。

 I'm gonna do it this way。 And they were like， you didn't say I couldn't。 But yeah。

 the point is that you can't use S TL containers in this assignment， so。Yes。

 I'll add that to the spec。So you can't use a vector。 You can't just like。

 you can't just like wrap it in a vector。 Can we use standard distance， Yeah。

 you can use standard distance。 You can use anything you want。 We're just gonna ban S TL containers。

 The point is， essentially， you can't use a vector。 Like you wouldn't want to use。

 you'd want to like if you wanted to use a vector for this。 It would be an ordered container。

And V is the only one with random access or Santa Ray， I guess， but。嗯。Yeah， essentially。

 essentially you can use anything。 there's no real constraints besides you can't use the vector and array STL container。

Yep， seastar loops，'cause that that's how it works in。Like the string library and stuff， you know。

So we're getting you kind of familiar with how some of these libraries might be implemented。

To get a better understanding of what's under the hood。Anyway， questions are pretty quiet。

 so let's wrap up。Thank you everyone， for coming tonight。And。I。

You were told in the ch that loops aren't necessary。I mean。

I I'd need more clarification on what that comment meant。 Maybe you should email me。Okay， sorry。

 let me let me let me touch on this point。 So a couple of people have clearly been to Simon's ch today becauseuse Simon has most of the chtes。

It's not bad to use loops。嗯。Loops are fine。You just want to avoid。

I'm just trying to think about how to phrase it。 I'm always。

 I'm always very conscious that I'm being recorded， right。

 Simon has made suggestions to use things like standard span， which is totally fine to do。😊。

But you won't lose marks for iterating with a full loop。It's an idea we've floated around with， but。

It's not something we're putting in the spec this year。

So Simon is probably mainly suggesting that because。If you can use an abstraction。

 generally it's a good idea too， right， like if you can use standard size T instead of unsigned in and if you can use all these things。

 then it's a good idea too because pretty much all abstractions are good。

 particularly if they're common commonplace and well accepted。So， yes。That's you don't。

 you're not going to get punished for using that generally speaking。

 like unless unless something comes up in a lecture and where like you should do it this way。

 it's not really considered。You know。Required。So last thing， Kaya says。

 what about algorithms like standard  for each。 You can use any SL algorithm。

 The problem is that some SL algorithms。嗯。I want you to operate on。

A container or something with iters。And I'm not going to give you all these different rules。

 the main thing I'm just going to say to everyone and put it in the spec is that you're not allowed to use STL containers in this assignment。

I don't care what algorithms you use。 There's some algorithms you won't be able to use。

 There's some algorithms you will be able to use。 You might be able to wrap things into an iterator。

 All these other things。 But the point is that you can't use S TL containers。

 That's the main takeaway from it all。嗯。There's no issue static casting things。

 Sometimes it's unavoidable， but if you have a static casting， you should ask yourself the question。

 is this an avoidable cost， And if the answer is yes， then don't cost。That's the best approach。

Let's let's push other questions on this assignment to the forum。 So if you have any other questions。

 please post on the forum one thing I will do。Cause I've been trying to do this this term。

I tried it with one course previously。 I'll make a。So， and。The C++ farm， I'll make a mega threadread。

Assignment。To。Spect questions。嗯。Signement 2。Please， post。Spect clarification questions here。

Please do not post your specific。These do not post questions pertaining。

To your specific solution issues。So what we'll do is we'll have a mega thread on。Hed。

Where essentially you can all make comments like， you know， can I use SDL containers？

And we can basically say。那儿。And resolve it。That's all， so that's where we'll put that。Please。

 though just post random shit there。 like， read the spec first。 I mean， you know， like， don't。

 don't post things that are already written there， but。



![](img/76e53c773e1ddd81397ade36aa5a4121_25.png)

Yeah， anyway。 thank you for all the hearts。 everyone。

 Let's wrap up if you have any other questions post here， Otherwise we'll chat next week。

 which will allow you to do the last 10，15% of the assignment and hope everyone has a great weekend Other than that。

 I'll I'll send you an email out on Friday。😊，With a little bit of a summary of the week。So。

Thanks everyone， I hope you have a great night。死得。