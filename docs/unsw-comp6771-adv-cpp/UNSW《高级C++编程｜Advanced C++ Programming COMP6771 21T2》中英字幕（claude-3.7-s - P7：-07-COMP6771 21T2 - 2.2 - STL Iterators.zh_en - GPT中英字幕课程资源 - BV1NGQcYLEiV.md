# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P7：-07-COMP6771 21T2 - 2.2 - STL Iterators.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

🎼The。Hey， hi， everyone。 So there's a good question posted in the chat about。Should。Should people。

 was it？Should people can I share my。Can I post the output of my program for assignment 1 and Ed？

The answer I have to this question is basically yes， because。Iは。If I said no。

What people would do is share it privately with their friends。And。If that happened again。

 I'm basically going be punishing people without friends like rather than say no and try and make you all do your own work。

 I'd rather just say yes so that people share it in a more public forum so that people。

 I when I say without friends， I just mean like without friends in this course kind of thing， right。

So yeah， that people without friends in this course can you know。Just like。嗯。

Everyone's sat in the chat。And posting me like， hii。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_1.png)

Yeah， it's just I don't like inequity where we can avoid it easily so yeah。😊。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_3.png)

Let's get on， let's get on to the next part， which is STL its， SL itators。

 which is a fun little topic。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_5.png)

![](img/6ddd54b810e188f793bbd6c0bf09a40e_6.png)

嗯。Okay。All right， so STL iters。We understand what a pointer is because of a basic sea knowledge an iterator though。

 is something in the past you might have referred to as a variable called I that was an endt that you iterated through an array with or something right but in C++ and many other languages an iterator is an abstract notion of a pointer Now what that means is that。

We its effect it it feels it behaves it like sounds it smells like a pointer。

 but it's still an abstraction of a pointer and and we'll get to that more。

 But at its most fundamental level， iterators are types that abstract containers have。

 basically all those containers we talked about that try and abstract that container to a linear sequence of objects。

 So what I mean by that is that。Whether you have a vector or a linked list or a doubly linked list or a map。

 which is a binary tree or an unordered map， which is a hash map。

 it's trying to reduce all of those containers down to a common type， which is a sequence。

 It is like behaves like a lister array that you go tick tick tick tick tick tick through in like a linear fashion。

 So it's a common， it's a nice common generic abstraction with that。

 And what this allows us to do is to basically take an algorithm like， say a search algorithm or say。

You know an algorithm search algorithm that would like a linear search。

 say and we can do a linear search， we can use the same algorithm on a vector。

 we can use it on array， we can use it on some kind of hash map， some kind of tree structure。

 we can use it on all of those things， so it's trying to standardize how all of that works。嗯。

Elon says point of it an object form。 I guess so。 like in a lot of ways， is， it is an object。

Kind of like a pointer， but like we'll get to that。How this actually works in C++。

 we talked about this before is that。😊，When you have a container where in this case， a is like I say。

 a vector， right， The vector array doesn't matter。 When you ask for a dot begin。

What you're asking for is an abstract pointer to the first element of that container as you're iterating through it。

 when you ask for a dot end， what you're asking for is for an abstract pointer to one after the end of that structure。

Okay。U。And。It's not actually pointing to a real value， that's like the most important part here。

Now the iterators that you deal with behave like pointers。

 so you have to claw back to your pointer brain for a second here to figure that out and as you loop through this you'll see that we have these variables here like iter we say that our iterator is equal to names dot begin and we're going to loop while our iterator is not equal to names do end and each time we loop we're going to increase that iterator by one。

And you can see here every time we loop we're printing our star it。 So what does star it mean。

 Well star it as de referenceence It。 So if you are using rural pointers it would be we're going to take our pointer and we're going to dereence it。

 I get the value at the address that that pointer points to。And that's how we get the value。

 And you can also increment it。 So what we're actually doing here is in theory。

 like incrementing a pointer， like moving it up one memory address。 And here we're saying， oh。

 we're going to get the value at that pointer。 The difference is this is not an actual pointer。

 It's not a literal address in memory， It's an object， as Elon kind of said， which abstracts it。

 which gives us a couple of protections and a few useful things。

 but generally speaking you should you should assume its behavior is like a pointer。嗯。Using iters is。

Yeah， it's it's。So。There' a couple of questions about like， or like I can feel the tone as like。

 and this kind of seems very like anti pattern， seems very like C style。

 Can we use references as this really good practice。

 So first thing I'd say is if you are just looping through an array to print something out。

 you're probably just gonna use a four range loop， or you're gonna use an algorithm。

 generally speaking， you don't actually interact much with the pointer directly。

But so this kind of example is not the best one to explain a common case。But。

We'll kind of we'll keep talking about that。That's， that's an important thing。

 Now we're going to look at this piece of code because this demonstrates it really well。

 You can also see here that names do't begin。When we use auto on that。

It actually like the type that it is set to is actually not it's it's a standard vector of standard string。

 which is what the containers type is iterated type。

 so that iterator type is defined in the vector library and typically you never really define those explicitly。

 it's always kind of defined through auto。嗯。And then Quijion says。

 how do we retrieve the index using the iterator。 That's a great question。 So you can't。

 And the reason you can't is because。An index， when you're iterating through something。

 an index kind of implies a location like。If you're iterating through an array。

 an index means something because the array is contiguous。If you're it through a linked list。

The index doesn't really mean a lot because。The link this might be implemented really differently or a tree。

 Like what's the index of a tree node， What's the index of a hash mount thing like。

It doesn't always mean something like it might mean something in the case of this vector sure。

 but for all the other types of containers that don't have contiguous memory。

 an index doesn't really mean a lot， so that's what I mean about an iterator as a way to abstractly linearize a container and just like go through each element one by one。

Even if there's no real sense of。Even if there's no like real sense of order。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_8.png)

Like continuoustiguous order。 So let's go to lecture 2。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_10.png)

Ter4。If you need to use index， you track it separately。 So I've got this vector called names。

 which I didn't populate for some reason。 but let's do that now。 And let's use that。

 let's use the new structure。 auto names equals standard vector standard string， and we'll do like。

You know。Hi。Howo。啊。You like that， right， those four things。Now let's try and build and run this one。

 so we'll build 204。Perfect， then we'll run it。Hi， how are you， Hi， how are you， right。

 So printed it out twice。 Now we don't need this bottom one here， at all。

So here's a few of the things I want to take you through with iterators。

It's actually on the next slide anyway， so I'm kind of jumping slightly ahead here。

 but I think this is an easier way to demonstrate it。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_12.png)

呃。对啊。I guess it's very confusing code that I've called my vector names。

 look I'll just I'll call it words then allright， Oh god， I just close the file。Yep， let's call it。

 Ill call it words for you。 There you go， words。嗯。Now。呃。Sorry， I was just checking something。Okay。

 so you can see when we print this out， it prints out what you'd expect。 It says， hi， how are you。

 Now， there's a few other ways we can。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_14.png)

Use iterated。 So if I go back to Stan vector in Google。You see that。

There's a bunch of iterator methods。Here we have C， we have beginner the C begin。 We have N and C N。

 We have R begin C R begin， and we have R end and C R end。 Now。

 the way that's structured is it might be a little bit confusing。 but generally speaking。

 we have begin and end。 we have R begin。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_16.png)

And R end。We have CvN。And C and， And then we have C R begin and C R and。 Now。

 what all these things mean is pretty simple。 R means reverse。Same means constant， that's it。

When we loop through something in the other direction。We can simply put R begin an R end here。

And I'll build this again 204， and we will run it。And you'll see that it's been printed out now in the reverse order。

Conceptually， what's happened here。 Well， let's go back to our slides。

 What's happened here is that we have。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_18.png)

Now， when we've said Vec dot begin previously， it's given us the first element and then Vdot end has given us one after the end。

嗯。And when we ask for R begin， we actually get the last element and when we give R and。

 the R end is now one before the first element， Now that should probably make some sense， right。

 the diagram is not super complicated， but what I really want to iterate here is no pun intended is that this method。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_20.png)

![](img/6ddd54b810e188f793bbd6c0bf09a40e_21.png)

The loop itself has no real sense that it's going through the container backwards。 right as far。

 like iterators always work the same thing。 It's a linear abstract list that goes from the start to the finish。

 That's all it knows。 That's all it knows here。 It's all it know before。 The only difference is that。

In what way is the iterator quietly actually iterating through it？

So what's happening here is this list kind of has the sense of like， it's going like， you know。

 from left to right， like， you know，But。In reality。Even though it's going left to right。

 the iterator itself is kind of going the opposite direction。

And this is really cool because this iterator provides a really powerful abstraction where like your code does not need to worry about whether it's going forwards or backwards。

 you're just providing the iterator that will give you the linear abstraction the way you want。😊，嗯。

Sush asks a great question that might be on some people's minds。

 which is if the data structure is not contiguous in memory， maybe like an unaudered sad or a map。

 which we talked about was a tree， how does the iterator make a linear sense of it。

 Well that's a good question。 And we talk about this in week 7 in the course。

 And basically that's actually part of the job of the container So the container implements the iterator So even though we're like containers。

 algorithms and iterators， containers are something on top of iterators or something on top of containers that allow them to be linearized。

 So you know how when you do like again， like data structures and algorithms。

 you get like a binary tree， right。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_23.png)

嗯。And。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_25.png)

They do something like you know， in order traversal， right。

 where you have your binary tree and they oops。And they kind of teach you how to like print it out or in order the wrong in order。

 that's not an in order tra reversal， is it？Or is it。I thought that was pre order。Anyway。

 maybe I'm crazy。Probably crazy。嗯。So what actually happens is if you have a binary tree。

 you know that you can write a really simple recursive traveral algorithm that will print it out。呃。

Oh， oh， I see what you're saying。 Okay， thank you。 I was like really confused。 It is in order。

 It's just not a sorted binary。Yeah， you could write a recursive algorithm that would take a binary tree and just print it out in order by like iterating through it the right way。

 You could write that recursively。 You could write it iteratively。 But what an iterator does for。

 say， a。A map， which we know is a a sorted associative container， which has a。Tree underneath。

 it does that for you， right So instead of you printing that tree out linearly。

 like the container itself， when it gives someone the iterator， it knows how to go through its tree。

 So it hides from the algorithm what's actually happening。

 So as far as the algorithms concerned on the outside， it's like， oh， this is a nice linear list。

 But the container itself is providing it。 So by putting the emphasis to every container that you have to provide me the ability to linearly go through your data structure。

 it then means that we can generalize our data structures across a whole range of algorithms。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_27.png)

So I begin RN moves in the opposite direction。Then you also have C again and C ends now。C。

 begin and C and and whatever。 They're the constant version of it。

 and a constant iterator restricts you。From。Modifying the element that it's abstractly pointing to。

So， for instance， here， this is just a standard R begin N R and。 I could say。

 I can't remember how to do this in C plus plus， but like。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_29.png)

How do you make a string up a case， Is it just string dot offer or something， What is the。

Someone don't know causeuse they have two opera And that's a sea thing。Standard topic， right？Sorry。

 guys， I'm sure some of you have already told me in the YouTube blog and stuff is well behind'cause no one's answered it。

 It'll come。 it always comes through in a sec。 it's like， oh。 So yeah， you know。

 if I want to do this， I can just like， maybe no one told me。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_31.png)

I can just include CC type。On this topic， actually， someone asked earlier in the lecture。

 I never got around to answering the question。 They were like， should I include。

 if I'm using standard pair， should I hash include standard utility。

 The short answer is probably yes， What I would say is that。

Every time you use an STD column column something that you didn't write。

Give it a quick look up on CPP reference。 Look at the library it's from and hash include that in your code。

 And then you're all good。 So I've got CC type here Now， I'm gonna make this standard to upper it。

 So I'm basically saying that it is a pointer。 So D references the value。

 And I'm trying to make them all upper case。 Let's see if this works。😊。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_33.png)

Oh， I have an  error。 What's the error。No matching function called thone to upper。What have I done。

Oh， there no STD。Oh， this is her character。 you guys are meant to look off to me。Damn， okay。

 I'm sure there's a string method。 Let's just look up string。 Maybe there's not。

Probably not actually。 C plus+ has fairly a fairly simple string library compared to other languages。

 but。嗯。That's okay。's let's just app it with something。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_35.png)

We're just reading the chat。 So is this some iterator container begin。

 consider a good way to calculate index when we need to do this， index looping is a better choice。

 If you really need the index， then。You would probably try and iterate through the iterator directly if it was ordered。

Container， I go， sorry， a sequence container。 I can array， but if it was。

Like another type of container， you'd probably just keep an index separately and then just increment it as you loop through it。

 That's probably what you would do。 I would guess。Anyway， what string methods we have。

 Let's just find a random string method I'm on C plus+ dot com， which we know we don't like。

Yeah I would just add something to the end of it。 Can you concatenate with strings。 I can't remember。

Or we could replace them， let's just do that hello， we could replace all the words with hello。😊。

And we run it and now they're all heller。So one other useful thing about iterators is， you know。

 you can modify things a bit easier with it sometimes。

You can do that with four range references as well。嗯。You can't hear。 I du'n know why you can't hear。

 I'm sorry。I think everyone can hear。 I'm just going to assume everyone can hear unless more people tell me that so the thing is。

 though if you use C begin。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_37.png)

And C and， this would now not compile， so it will be a compile time error。 you'll see this here。

So do where's the actual error， not the BS that follows it。Here we go。No viable overload equals。 Now。

 this is a really。Obscure kind of error， which will hopefully make more sense when we talk about operator overloading。

 But basically， what this is saying is that every type。Has a set of operators that you can use。

 right， Like an int， you can times and divide and plus and minus， but you can't divide a string。

 right。Like you can't say。My， my name is， is Hayden divided by。Lockland， like you can't say that。

 Similarlyly， a constant iterator。Does not have an assignment type。

 It does not have other types that implied mutation because it's read only。

 So that's what this error means。 It has no viable overloaded equals。

 basically saying that it has no idea how to take this type here， which is a。You know。

 con string because that's what it gives you like when you when you dereference the iterator。

 it gives you a constant version of the data type and therefore you can't do it because the compiler is like。

 I don't know how to actually set a con string to be something else。🤢，So yeah， that's what that is。

 and you can see the S codes picking up on that too。Anyway， you can so con prevents。

Mutation at compile time。 It doesn't do anything during runtime because it won't let you compile because it can tell if you're gonna to mutate something at compile time。

 The other thing to note about it is that some people ask， oh， when should it be constant or not？

 Well， it's like a normal constant if you're not。Modifying it。You should make a con。Now。

 a couple things with that。The reason we like to do that is because it makes it really clear to other programmers what。

Your intentions are。 So if you say C begin， it's clear to someone that you don't want someone to mutate this while you're iterating through it。

 And then similarly， I think there are some instances where compilers will。

Be able to do things faster if they know it's cons。 I don't know the specifics of that。

 but I've also heard people tell me that that's a bit of a red herring because most compilers。

 even if you define something as。嗯。Not cons。 And you don't modify it。

 The compiler actually set it to be a cont iterator anyway。

 So I've heard people tell me that that the compiler in this case will just be like， now。

 now it's not being modified。 or'll just make it a const iterator nice and simple。Great。嗯。

Last thing here is stream iterators。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_39.png)

This one wasn't really an exempt， this was something that we were going to throw out but I wanted to keep it because it was just kind of random。

 I think we need to make a file called Data。t in but。

You can iterate through input streams and output streams and input file streams。

 So like you've probably gotten a sense and C plus plus of these things called streams。

 which are just how you。A。Sorry， I was just reading something。嗯。It's a really good question。

 and I'll come back to that in a sec。Yeah basically when you open a file as well which is essentially a stream like you know imagine opening a file。

 it's not like it's you don't copy the whole file into memory。

 it's like you have a point to the beginning of the file and then you iterate through the file till you get to the end right and similar thing here you can iterate through this。

By it's like let's try this out。 I， I didn't want to do this one， but I've changed my mind。

 So if I make a file called data dot in， I just like one is reveal 5 or something。I don't know。

Let's try that， let's try and compile this。This might go against me。Okay。Oh， no， okay。

 that's not what I hoped would happen。Maybe I， maybe I should have deleted this one instead。

It's probably because I'm running it from the wrong directory。 Let me try that。

Maybe that's the problem。Okay， well， this seemed to work。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_41.png)

Let's try putting spaces there。So。Right。So let's have a look at what this is here， I stream iterator。

And begin。嗯。Now。I don't want to get into this whole stuff because I don't think it's that relevant。

 but essentially an input file stream is a stream here， and then we're trying to create an iterator。

From it。Which。It's kind of like this type here。 This is just the thing is is just very tangential to all the other stuff we're doing。

 But if you just kind of take the code at surface level， we're creating an iterator here。

 a begin iterator for an input stream， and we're creating an end iterator for an input stream。

 Now the begin iterator actually needs the stream because otherwise it doesn't how to do anything and what you can see here is that we are printing the first character one。

 and then we're incrementing it。 So this is a post increment。 So we print it。

 and then we increment it， then we increment it again， but we don't do anything with it。

 which is why the two isn't print out and then we increment it again to get the three after we print it out And then we have a while loop that would just keep going while the iterator at the beginning is not the iterator at the end and it would just keep printing it out。

 Now some people are probably like a bit confused here。

 But like if I could just say rewrite the structure for you。

 I could say something like this instead I could say like Istream。Iterate a begin as that。

 and then I could say。You know。啊。Auto I equals begin。

 But that's basically what happens in the other cases。 And then I could just use the iterator here。

 So this might be more。Visually clear to people what's happening is like just like in the four loops we had。

Yeah。You know we get the begin iterator， we get the end iterator， and then we have our itA or our IT。

 which is what we're using to loop through it， and then this should still compile that wasn't the file。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_43.png)

Yeah， so that should still work there。 So there's a lot of things you can do with iterators。

End is like end of file， yeah， that's correct。Charlie asked a great question。嗯。

You can change the begin variable name， yes， these are just variable names。嗯。Sorry。

Just just to really maybe explain this some more because I'm seeing more questions about it。

 this is a default constructed Istream iterator， which will always be equal to the value of end。

This is a constructed eye stream iterator that's given the actual input stream。

 So if you didn't put the I N there， then it would。It would just be another end iterator。

 even if you just called it begin now the。I completely forget what I was going to say， oh， yeah。

 Charlie asked a great question。I think yeah， so let's go back to the previous example because I want to just chat about this a tiny bit more。

 Charlie is a great question， which is like， why is this auto iter when we use C begin Because we know for a fact that if we want something to be const auto strips the constant away。

 So if the right hand side of an assignment is const like C begin。

 then shouldn't we add it to the left because the auto will strip it away。😊，And the answer is no。

 because。The actual actual type that a C begin returns。

Is a cons iterator in the sense that it's not a like the type is not a const iterator。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_45.png)

The type is a const iterator， which is just another type。

 Like the two types are iterator and const iterator。 They're not like there's no const version。

 They're just two nonconst types that one has constant name And the reason that's important is because iter itself is not actually const if it was conant still wouldn't compile because this like we could try it right Like if I actually tried to make this con。

 it would fail to compile because the compiler would see that we're trying to increment it。嗯。

And it would seal my bulls shit。嗯呀。Yeah， so the output here is。Cannot increment value of type cons。

 blah blah blah blah， blah， so。Yeah， so essentially the actual iterator itself is not cons。

 it's just the type of this non con cons iterator。Ensures that when you dereference something。

That what you do reference is a const type。 So the actual iterator here is still nonconst。

 It's just that this iter here has a type const string。And if this is a non constant iterator。

 then the iterator de reference has a type of string。 So it， it really affects what the。呃。

What the type of the dereence of the iterator is， if that makes sense。 So yeah。

 that's the relevance essentially。Is there a type of operator？Probably。I don't know。

 I even really used on thetypo in。Tried out。See what happens， Maybe not， I don't know。

 I'm just trying this so probably doesn't work。New。呃。Is a decoal type， but I don't。

 I think decoal type is a type。 Now decal type value to a type。 How do you go。Value to it。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_47.png)

How do you do type to value。Type I D。Type I D expression。

 What does that actually return that function， Hopefully it returns a string or something。

I don't know， let's just try type ID of itA， is that built into the language？I'm not sure。

I'm worried。 I may not。 I maybe won't go down this rabbit hole。 typed after a different thing。嗯。No。

 I don't know anything about this。I'm not going to get lost in it。Type in for name。I mean。

 we could try something like this。St at the out。Standard type info。Of it a dot name。Maybe。

And we have to actually include type info。 I don't know if this will work。 If this doesn't work。

 I'm going to give up， even if someone tells me the right answer。Type I D Vard name。 sure， okay。

That's all right， I might leave this one alone。Yang。Allright。

 you guys tell me only because we're running quite ahead on this lecture， but。

This doesn't work I out。No， good job， good job， everyone。Let me do 24 again。Oh， I see， okay。😊。

I've always wanted an NT 3，111 rapidpier IPN S。 You can see basic string there。

 but I guess if we make it a consideerator， we might see this change slightly。

 I guess that's the hope。Maybe it'll give us like a better name， like。What do we constierator？At。

There's a cada。Kay for Kst， I guess， let's just pretend that case for const。😊，Cool right。😊。

That's pretty much it on iterators。 The last thing on iterators that I did want to chat about is back to our actual container slides because in the container code we had this map example here and I want to show you another way to like look up if something's in a map。

 So for instance， here I could say if M dot contains cat。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_49.png)

Then。Standard C out。Is there or something like this。Else。Standardacy out。Is not there。Like that。嗯。

Yep， could do something like this and if I build and run that one。

It'll tell us where the cat's in there。Back to three。So yep， it's there。 Cat's in there。

 That's all correct。 The other way that you actually do this is that most containers have a fine function。

 where you can say。Auto iterator equals M dot find。

 And then you can pass in the key or the value that you're looking for。

 And then you say if iter is not equal to。M dot end， that means it's in there。

And then you do a similar thing here。So what you're basic so how this works as that and we're going to talk more about this next lecture is that。

😊，A find function returns you an iterator to the value， and if it can't be found。

 it returns you an iterator to dot end。So in this case， it could be found。

 So it returns an iterator to the value。 Otherwise， it returns it to dot end。

 So that's kind of similar to at。 I guess the difference with at is that。Okay。

 this' is actually a really interesting thing。 Good good thing we're about to wrap up because we can waste time on this。

 So let's compare three methods or two methods， I guess is probably or three。 Yeah， let's do three。

 So the first one is using the iterator。😊，The second method is we're going to do a what we did before。

 which I shouldn't have deleted， which is that if M dot contains CA。Then we want to say print it out。

And the how I'm going to modify this too is I actually want to print out the cap。Like this。

 say like cat is there。But in this case， if it contains CAt， I'm going to use M dot at。cat。嗯。

And then let me just delete this， so I actually buged this explanation， so let me try again for you。

 sorry guys。What I'm doing is I want to look through this map to see if cat's in it and if cat's in it。

 I want to print the value。 So what I'm actually going to say here is value at。Cat， which is the key。

I'll just say value。Scrt， this will be easy。Keep this really， really easy。 So if cat is in there。

 I want to print out 10。157， right。Um，Ben。If cat's not in there， I wantan to say it's not in there。

 In this one， I say M dot contains catt。 And then I say， if it's in there。

 I want to print M dot at cat， or I want to print what I had up here， which is value is。

 is what's at cat， right， Because when you look things up by a key， you get。You get the。Val。 Now。

 Queeny says that。E de referenceence will return a pair。 Yes， you're right， I probably should have。

Probably should have like thought about that， so I'll say。Key value equals it R。

 And then I can do key value dot second。 So what actually happens with maps。

 which is kind of interesting， I don't know if it's dot second。

 I can't remember is that when you de referenceence an iterator to a map value。

 It doesn't give you the value it gives you the key value pair。

 So what this will actually do is it'll actually give me a cat 10。157。

 So we actually have to pull that into a standard pair， that's what this is。

 And then we get the second element from that。 a little bit round about a little bit ugly。

 but it works the same then we have this time where we look up whether the cat's contained in the map。

 And if it is we get the value at the key cat and this we could only do from c plus plus 20 because before that we didn't have dot contains And then what we would do before C plus plus20 if we wanted to avoid iterators。

嗯。Is we would。I will fix that up。 Let me get back to that line is before C++ 20。

 we would actually probably have to say， like try to do this。Oops。

We might have to say try to do that and then otherwise we would say catch。Standard exception。

 I think you can do catch all。 We'll come back to exceptions in week 4。 And then we do that。

 So it's kind of like because previously the only way to actually like tell if it wasn't in there was to try and get it and then it would throw an exception。

 I think they're kind of the three ways to do it。 So let's first get this compiling。A compileild。

 right。And now you can see here that it says I got the three values which means all three of these things work now what is the difference between these three things now？

Naturally this one has exceptions which makes it kind of awful and ugly Excepts are generally something I guess you'd want to avoid if you could because they disrupt the logical flow of your program and they're a bit。

😊。

![](img/6ddd54b810e188f793bbd6c0bf09a40e_51.png)

I don't know， it's just a weird thing to use an exception for。So this one makes more sense。

 I think the downside with this one， though， is that map， as you know， is an ordered。

Adered Associative container， which means that a lot of its performances log in。

So for me to actually。Look that up。 I actually have to do two lookups here So there's actually a cost to look up and then I have to look it all up again because these two things aren't talking right。

 They're two separate statements whereas using the iterator I'm actually able to look it up once and then I've got an abstract pointer to that value I found and then I can use it。

 So in a lot of ways this is actually quicker than the contains one because you're only having to do one lookup。

Could I use M dot count inside the if condition， I guess so。 I'm not sure。

 I don't see a reason why you wouldn't。嗯。Yes， oh， yes。 so that's the other thing。

 I really like this point。 So I've simplified this a little bit just to explain a point。

 And the lawyer has pointed out a really good thing。

 which is that if you actually go and look up standard map， though。😊。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_53.png)

Right。One of the other differences here is that standard map。 if you look at the。

 let's look at the time complexity。 So art has a complexity of logarithmic。

 which makes sense if it's a tree contains will probably have the same thing， I guess。

Where it contains this。Contains will have a complexity of logarithmic。 But when we look at fine。

 what's fine I'm going to have logarithmic so。This is interesting because。Findd is logarithmic。

 which makes sense because you're essentially delegating it to the container。

 If you were to try and use an iterator though to find it like a dot begin dot end。

 a dot begin dot end is is actually asking for you to linearize the entire structure so you can move through it linearly so it would actually be quite slow to go through it with dot begin and dot end。

 that would be a worse case O because you have to do an operation through it。

 But in the case of find， you're not actually asking it to give you a linear representation of the container。

 you're actually just saying you go find it however you think works。

And just give me an iterator to where it is so I can use my iterator semantics and that's a great example too because we'll actually talk about that tomorrow night when we talk about algorithms because the find algorithm is actually slower than the find method。

😊，Which shall hopefully really consolidate that idea。 Anyway， it's 7。

50 and pretty much out of content， even though this was fun to go through， so。😊，Tomorrow。

 we're going go through iters。 I won't lie。 I totally forgot that there's a public holiday in week for on the Monday。

 So we will probably have to。Do operator overloading。Then week， the next， the next few topics might。

End up over multiple lectures， if that makes sense。 So we might be doing a lot of part  one。

 part  two lectures， which is fine。 Last question， Alan says。

 what is the point of returning the iterator rather than a reference to the object itself。



![](img/6ddd54b810e188f793bbd6c0bf09a40e_55.png)

Well， I mean， we already have that with at， right？ And there's no other way to really， there's。

 there's really no way to， to do like a reference look up that doesn't have an exception without making to。

2， to like function calls。 But the reason that iterators are useful here is because。Well。

 it's what I just said。 You can， you can check and look it off in one function call。

 but also sometimes you want to do something like go to that point and then loop through the next three values。

 For instance， Or maybe you want to find all the values in a container that are whatever。

 like it it's。An iterator is like you're reaching your hand into the container and holding it at a certain point。

 and then you can do a lot of things from there， you can go forward。

 you can go back in some instances， you can mutate it， like I mean。

 you can do that with a reference to， but there's a bunch of little things you could do with it。

When you want to loop through structures， it's， it's pretty much like you use a for each loop。

 a four range loop， which actually uses an iterator， to be honest， surprise。 So these。

 these loops here actually。These loops here actually use the iterator。It won't like。

 that's all it does。 That's actually all it does。 which makes sensecause like。

 how the hell does it know how to move through that array like。You know。

 this doesn't just magically figure it out。 it has to use the iterator to figure it out。

 and that's probably why you can use this structure too unlike maps and stuff because I think it just uses the dot begin dot end stuff for you。

But generally speaking， my point is you're not actually going to loop through things that much like this because you're probably loop through it like this。

 The main value of iterators is in more complex stuff， and it's also like for things like find。

 And I don't think you're you're not going to use a ton of iterators in assignment one， probably。

I haven't done it in years。 so I don't know off the top of my head。

 but you probably use the find one a little bit。 I would guess there'll be a bunch a few of you。

 you' probably use find a bit。Would if a bad practice to use contains， no？

I don't know if any of you are actually using an ordered map or not。But unored sets。

 you would probably just use dot find if you need the value， if you don't need the value。

 just use containss。Cause it's cleaner。嗯。But if you do need the value。

 then youd probably want to use find because then you save yourself two lookups。

 which could be costly。Okay，754， I'll see you all tomorrow night and。😊，Thanks for the the fun time。

 That's pretty much your on iters。 Tom， we'll do the last part of ST TL。

 which is algorithms and we'll tie it all together。 So thanks， everyone for being such。😊。

Charming participants as always and。I will， yeah， see them tomorrow。 Have a good day。

 Try not to be too cold。 It's cold。 Winter sucks。