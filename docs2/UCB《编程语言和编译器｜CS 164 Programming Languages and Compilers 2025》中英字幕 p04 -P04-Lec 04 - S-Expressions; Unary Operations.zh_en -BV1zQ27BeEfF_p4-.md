# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p04 -P04-Lec 04 - S-Expressions; Unary Operations.zh_en -BV1zQ27BeEfF_p4-

![](img/fe80c520e68686f852e656c733f267ed_0.png)

All right， happy Tuesday everybody， I hope everyone enjoyed this beautiful rainy day and got to get out in the rain this morning。

 What a lovely way to start the day。A couple of quick notes today。

 number one is massive thank you to all of you seriously for doing the drill。

 I cannot overstate how important that is for us for figuring out what concepts y'all are struggling with what things are still confusing what things are going smoothly is really。

 really helps us figure out how to shape both sections and in particular what we're doing here in our class sessions。

 So we really， really appreciate you'all filling those out。

 I'm going to quickly reflect on some of the things that I noticed from the drill。

 We'll go through those。 So one thing that I thought was really interesting was over 95% of you all have never touched O Caml before。

 I thought that was really cool。 That was not unexpected。 That is what we normally expect。

 but it is totally normal to be in this class and never have used O Caml。

 even for a single moment before。 And so just if you're trying to get a sense of where other folks are at with that。

 that's the situation there。😊，In fact， very few had actually used functional languages before。

 so I thought that was also quite interesting。😊，A couple of questions about the collaboration policy that I just wanted to make sure we're all on the same page on。

 Most people were totally on the same page about this。

 but I just wanted to double check and check in about it。

 So particularly the stuff that people seem to struggle with this idea of looking over a friend's shoulder and when that's okay or not。

 I totally get that。 And it is kind of complicated。

 And so obviously the safe answer is to just not do it right like that is sort of the easy way to make sure you're on the safe side。

 but in particular， if you are not writing code at the same time， it could be safe。

 So especially like if you have already submitted your homework。

 And so there is no way that you might see something over your friend's shoulder that would then change how you are actually going and writing your own code that would be an example of a quite safe situation。

And then also folks who are curious about snippets from stack overflow。

 It is fine to put in small snippets right if you are copying over large chunks。

 we start to get worried， but if it's just a couple lines， we're not too worried about that。

 And then a quick note on how to prevent autograder runs。

 So if you know something happened and you're like， oh man。

 I shouldn't have done that I want to withdraw my homework assignment。

 The way that you do that is you go ahead and you overwrite what you had submitted with the original starter code and we will treat that as a withdrawal。

 So that's the thing that you can do to actually prevent your code from getting graded。Okay。

 in terms of the things that are confusing to folks right now。

 it's basically exactly the things that we would have expected。

 So the main thing that's coming up is， okay， well， it's still really weird and confusing。

 And that's totally natural。 And I think as we're getting more hands on experience with it。

 it's gonna get less and less confusing。 But that seems to be the main thing that's tripping people up right now。

 To makes sense。 we're gonna keep getting more practice with it。 So hopefully。

 that's gonna get smooth out of it over time。😊，Okay。One more logistics note。

 and then we'll dive in on content for the day。 So apparently。

 Github Github classroom specifically is having some issues。 We are so sorry。

 we wish we controlled Github classroom。 we do not control Github classroom。

 But what this means in the meantime is that I'm going to ask you all to please make sure that you have access to the starter code as early in the week is possible。

 So， in fact， maybe today， go ahead and try to check out the next homework。

 make sure you have access。 if you do not have access our very kind Gsis have done an awesome thing and gone up a special form that's just for please make me have access to this homework。

 And so you can go ahead and use that form if you are lacking access。

 but we do want to make sure that people are checking early because it does seem like at least for now。

 until Github classroom fixes whatever this issue is。

 there's still some amount of manual work for the Gsis to make sure that everyone has access。

 Hopefully most people are getting access by default。 But if you are running into problems。

 There are some manual fictions that the GS can do。😊，Okay。

That's our general logistics update for the day。Cool， so in that case。

 we have a couple of exciting topics for today， and I'm going to introduce us to a new slide from our slide deck。

 How am I going to do this。 Let's see。😊，Oh'll look at the compiler for a second， no， we won't。

 that's not mirroring。Great， we can look at our compiler for a second while I get us looking at the right slide。

😊，嗯。So here。We have our great big CS164 summary slide。

 we actually have two of these and this is touching on basically all of the topics that we are excited about getting to over the course of the semester。

 the kinds of topics that we are going to see on the exam。

 and occasionally I will take a moment to just stop and highlight the ones that we are going to tackle for a given day just so you have a sense of what's coming up。

😊，And so here are the things that we are tackling today so were going to go ahead and you remember we talked about interpreters versus compilers last time today we are going to be talking about this。

 what are the various components of a compiler we're going to talk a lot about syntax versus semantics we're going to talk a bit about assembly as we often do。

 and we're also going to talk a little bit about intermediate representations although we are not today going to talk about LLVM like lowlel intermediate representations。

So those are our general topics for the day today。

![](img/fe80c520e68686f852e656c733f267ed_2.png)

So far so good。 Okay， so let's go ahead and swap back just long enough for us to get to。



![](img/fe80c520e68686f852e656c733f267ed_4.png)

The slides we are mainly dealing with。

![](img/fe80c520e68686f852e656c733f267ed_6.png)

Today， we're going to be doing unary operations。 They are going to look something like this。

 But before we dive in on that， I'm going to ask you to go ahead and consider。These two programs。

And the thing that I want you to consider。Is with someone nearby。

 go ahead and chat about based on sort of the programming languages you know。

 the programming language you're familiar with， would you expect that these two programs are going to behave the same？

Go ahead and chat for 30 seconds to a minute。All right。

 I want you to go ahead and hum if you think these programs are going to behave the same。

I want you to go ahead and hum if you think they're going to behave differently。Okay， cool。 Yeah。

 so I actually like both those answers。 The first answer I like a lot because based on all of the programming languages I have interacted with。

 my first prediction， my initial prediction of what is likely to happen if the languages that I'm seeing is similar to the languages I've seen before。

 is that these will behave the same。 So that seems like a really good answer。

 I also like the second answer， And that's because nothing about what we're seeing actually tells us anything without knowledge of the language we're working in。

 actually tells us anything about what these programs will do for all I know that when you see this program。

 it could be that the language is implemented in such a way that it's going to print out the string unicorn。

 And that's totally fine， right like that could be the correct behavior for this program depending on what the language has chosen to do with this program。

 And so this gets in an idea that we are going to be thinking about over the course of today。

 which is the difference between syntax and semantics。 So syntax is what。😊。

Program looks like right these two programs are using different syntax。

 We can see that in order to write down something that could be the same program。

 theyve written down different strings of characters。 So're using different syntax。

 but if they behave the same if they do the same thing then it is possible that the underlying language actually is using the same semantics。

 So the behavior of the programs could be the same。

 And so this is going to bring us to talking about the components of a compiler And it' a little weird in some ways that we're only getting to this right now。

 This is often what you will see the very first day of a programming languages and compilers class is sort of this diagram and you'll see sort of the various different components of a compiler and often that's happening because the first thing you're going to do is build this arrow。

 And then the second thing you're gonna to do is build this arrow and then you'll build this one and then you'll build this one right that's how they're often structured whereas in fact。

 what we have chosen to do is always have this full pipe。line available to us。

 but we'll start with a very small language。 We're going to start with something small。

 and we're going to add another programming language feature and then another programming language feature and another programming language feature。

 And so we will be able to run this entire pipeline the entire time。

 but we'll be expanding the language for which we can do it。

But I do still want to talk through what's actually happening at each of these。

 So let's put some names on each of these arrows。 And let's actually go ahead and figure out what is happening inside。

 So the first thing we need to do is go from the source code。

 which is coming to us as a string and turn it into tokens Now we're going to talk a lot more later on about what we mean what we say tokens。

 but basically individually meaningful components of our program right if we see the number one in our program。

Then one could be a token。If we see the number 13 in our program。

 then one on its own within the context of that 13 is not going to be a meaningful token。

 but 13 would be。 so let's go ahead and call this the tokenizer， as you might have guessed。

And you may also hear this called the Leer。Then the thing that's in charge of going from this list of tokens。

 this unstructured list of tokens， to some kind of representation of the program that we can freely manipulate。

 which we will be calling the abstract syntax tree， that is going to be the parser。

And in addition to going from that list of tokens to that tree representing the program structure。

 the other thing that will be happening there is we'll be figuring out if the list of tokens we've got is actually a thing that is allowed to exist in our language or not。

 So that's the other thing the parser is going to be in charge of for us。

So we'll go ahead and call that entire thing all of this is going to be the front end right。

 so this is the thing that is in charge of going from the syntax， right。

 that particular character set that the programmer wrote down。

 turning that into some kind of structured representation of the program that is the front。And。

Of the compiler。So far， so good。Cool， in that case。

 let's turn to what you have probably guessed based on what I just wrote。

 what you've probably guessed is called the back end of our compiler。 And here we've got code。😊。

Generation。Right， so this is where most of the stuff that makes compilers hard。

 That makes compilers interesting lives。 And so we are going to spend。At least the first half。

 maybe even a little bit more of our semester on this。

 because this is where the core challenges live。And we will eventually be shifting over to。Let's see。

 can me highlight to this portion at about the halfway mark。

 and then we'll explore some other topics as well， but a huge amount of the time is actually going to go to this where the really big challenges live。

And then。This next arrow isn't actually super interesting， but someone's got to do it。

 So we've got the linker。 We've got the asmbler。And all of the stuff that's going there is turning something that's already quite low level。

 right so our assembly instructions are already pretty low level into something even more low level。

 which is to say ones and zeros。 That process is basically mechanical。

 So none of the hard stuff really lives there。 And we won't actually bother to make our own thing for turning things into ones and zeros。

 But if you're interested in it， please do come chat。

And so this on the surface of it looks like a complete compiler。 right， If we can go down this path。

 we can follow all these arrows。 We have everything that we need in order to go to from a program that the programmer has written。

 They've typed it into their text editor。 Everything we need to go from that to something we can run on the machine。

 But actually， this is not all that we have in your average compiler。 Well， okay。

 maybe not your average compiler， I wouldn't want to talk about the average compiler。

 But in your production compiler that you have all used。 So you're gonna to have something else。

 So you're going go ahead and have optimization。 So let's go ahead and write opt1。😊。

And maybe up to two。And maybe， in fact， up to  three。

 So often you have a bunch of optimization passes that you are running on some structured representation of your program and you're doing all kinds of transformations at that stage with the intent that the program that finally comes out the other side is going to run faster or it's going to run with a lower memory costs doesn't necessarily。

 you know， do the same thing depending on what kind of thing you are trying to optimize。

 right there are multiple different things you might be kind of trying to optimize and you might then choose to run different optimizations as a result。

But this is sort of what's happening on optimization， and in fact。

 even once we have generated instructions， we're not necessarily done with optimization even then。

 because it turns out that we can do something called people optimization。

Which is actually going to do optimization on sequences of assembly instructions， right。

 so we can go ahead and do a bunch of things。 And all of these together right， are going to be。

Optimization。So typically you are going have some kind of optimization in a realistic real world compiler and so what we are going to be doing over the course of the semester is spending a bunch of time here。

 basically throughout we're never going to get away from needing to do interesting things on the cogeneration side and then for a little while and sort of the middle part of class well switch over to talking about tokenization and parsing and how we can actually get from the surface syntax of the language。

 the thing that the programme is actually typing into their program editor to the structured representation of the program that we're actually going to want to play around with。

And then once we've covered those topics， we'll switch on over to optimization。

 we'll talk about what's happening inside the optimizer。

 but I want to emphasize here that the only thing we actually need in order to actually run programs is this path。

 right， if we've got this path covered， we don't actually need optimization。

 we can go ahead and actually run programs just based on having those arrows that I highlighted available to us。

So are there questions about these overall components？Of our compiler， yeah。不是那个。

Can you give me a brief， okay， so I think this is maybe a question about the fact that there are multiple optimization arrows coming out and going in。

 Oh， I love this question。 Yes， so there are a bunch of different optimizations that we might want to run。

 And this isn't just about the fact that we might want to do some optimizations to reduce memory footprint and some optimizations to make the code run faster。

 even if we only care about something like making the code run faster。

 There are so many different optimizations that we might want to run。 So many that， in fact。

 one of the huge issues in compiler optimization construction is actually figuring out the order in which to rub them because even that can matter。

 And this is one of sort of the big open problems in optimization land is how do we even sequence these。

So this general problem， in fact， this sort of whole section here is sort of the main work that is happening in compilers research right now is how do we make things that are even more optimized。

 There are other things happening， There is a little bit of an oversstatement。

 but this is definitely still a hugely active area of research。

 of how do we make optimizers even better。Hopefully。

 that gives a general sense of why we might have multiple optimizations and why we would be running things through the optimization multiple times。

 We might， in fact， run even the same optimization multiple times， but we'll get to that later。Yes。

Oh sorry AST stands for abstracttract syntax tree and so basically abstract syntax tree。

 the reason we use that terminology is just that we want to talk about the overall structure of the program right so it is going to be actually tree structured right we'll start at some root node。

It is going to be tree structured， and it is going to go ahead and actually represent sort of what we see in that source file。

 The programmer was typing in some kind of a file。 It is going to look pretty close to that。

 but with a lot of the details of the syntax stripped out So something like， okay well。

 all of our statements are ending with semicollons。

 We don't need that information anymore at this stage By the time we are actually trying to manipulate some representation of the program。

 we don't really care how the programmer actually wrote it down。 what syntax they used And in fact。

 later on in the semester， we're going to see that we can use multiple different syntaxes for the same language。

 And in fact， you'all are all going to implement two different syntaxes for the same language。

 And so that is sort of a way of representing the core underlying constructs that exist in the language without bothering to represent and here are the particular characters that the programmer wrote down。

 And so that's why abstract is the first in AsT。 And what was the first part of the question。这。Yeah。

 so I think this question is， do we want to do something like loop unrolling inlining。

 the optimizations that we've probably heard of are those normally happening， oops， sorry。

 didn't mean to you race， Are those normally happening in Ast land or on a representation of the assembly instructions themselves。

 Most of the optimizations that you will have heard of are going to be happening in AS land。

 So in general， we have a lot of information available to us at the stage where we are operating over some representation of the program that the programmer wrote down that we no longer have available to us once we just have sort of this straight line of instructions。

 And obviously there's a lot of other information available instructions like we are going to see things like jumps。

 We're going to have some understanding of how you might move between the various instructions in that sequence。

 but in general， there's a lot of information that gets thrown away when we are going from Ast to instructions about how the programmer actually wrote this thing And so most of the optimizations that you've heard of are probably happening in AsT land。

Yes， so that was such a good question。 so this question was when we say that we're going to have two different syntaxes。

 does that mean we're going to have two different ways for the programmer to write down something that will then get translated to the same AST。

 that's exactly what it means。 And so that could even be for this case that I just showed you you could imagine that we have one AST that represents these two programs these two strings but the user has clearly written down the programs with different syntax。

Yeah， great question， but yeah that would mean taking two different source codes。

 putting them through a different tokenizer through a different parser。

 but then generating that same AST representation。Yeah。他们。Oh， I think I understand this question。

 so I think this is a question about just in time compilation。So。

The answer is gonna be some of the time。 So in general。

 if you are running a program where mostly you're interpreting it。

 but you realize that there's one part that you were running a lot。 you might decide， oh。

 I don't want to do this slow interpretation process for this part over and over and over again。

 I am instead could actually run my compiler just on this snippet。

 And now instead of running the interpreter on this every time I need to execute it。

 I'm just gonna go ahead and run that now compiled code。 So this is basically saying。

 we can mashed together interpreters and compilers in really cool ways。 Yeah。

 just in time calculationlation was one of the really cool things that came out of Pland in the recent past。

😊，Okay， not that recent to yall， it feels recent to me， whatever。Okay， cool。 all right。

 we're not going to like be going away from this diagram。 this diagram is going to live with us。

 so we're going to come back to this。 Don't feel like you have to get all your questions about this for now。

But hopefully， now that we've had that chat， we have some sense of why we are focusing on this difference between syntax and semantics。

 because， in fact， we just talk about the fact that two different syntaxes could lead us to this same AST。

 which means that we can kind of ignore syntax for a pretty long time when we're focusing on cogen。

 What we care about is semantics。 What we care about is the behavior。Of the the program。However。

 having said that， that's not going to mean that it's going to be easy to just mess around with a string representation of the program and so I am going to have a start thinking about something that's more like an AST。

 something that is giving us some tree structured representation of the program that the programmer actually wrote and so I want us to go ahead and together stare。

 contemplate this slide with people nearby and what I'm going to ask you to come up with is if you are trying to break down all these programs and just sort of the fundamental building blocks that are appearing in these strings。

 something that you could use that maybe has not too many components but you could compose all of these programs with them。

What would you point to， what patterns are you observing about what's appearing again and again？

So go ahead and discuss with folks nearby for about a minute。

If I make an announcement at the end of class， there was some disagreement about the homework one due date on grade scopepe in the website。

 Sure， I fixed it。 so I just want to quickly tell everyone when the homework one thing we do。 Yeah。

 totally， yeah。たけまぐい。可能性そ。はあお。在。电我。お系で。えつ分成。So maybe to kick it off。

What name might you give the things that I have currently highlighted up here in green？Okay。

 I'm hearing literals， can we maybe even be a little more specific here？But I love that answer。

I'm hearing numbers。 Yeah， yeah。 So I would say these are number literals。 That's great。

 So let's say numbers。What else are we noticing？What else might we be seeing here。Operators。

 I like it。 I actually， I would love to group together our operators with some other things。

 So what if I highlighted this， this， this， this， this， this， this。

 I'm gonna go ahead and have you discuss for 20 seconds with folks nearby。 What might we call this。😊。

はいがうござ。ます。So I'm going to call that symbols。Not a particularly specific name。

But something that clearly applies to all the things I've highlighted in purple。

What else have we got here， yell it out for me， What else is happening？I'm hearing lists。

 I totally agree。 And in fact， we've got even nested lists going on here， right， So here's a list。

 We've got this list right there。 We've got this list over there。

 and then we've got this larger list over here。 This entire thing is a list。 That's a list。

 That's a list。 It seems like we've got a bunch of lists going on。 I'm sorry。

 I have not highlighted all of them， but hopefully we get the idea that the other thing that's happening here。

 is lists。 So that looks pretty good to me。 We have managed to sort of boil down all these programs that are doing very different things。

 into a representation that really only has these three ingredients。😊。

And so in case you have not seen these before， which is totally fine。 These are called S expressions。

 So these were actually introduced way back in about 1959。

1960 by McCarthy assistant professor at MIT was starting to try to make this language trying to make it easier to mess around with lists of information that was going to be useful for the research that they were doing there and so they had this idea they were going have this the internal representation This was going to be that thing that was appearing in the middle of our compiler diagram。

 This wasn't going be what the programmer was going write they had this plan that long term in addition to these。

 the S expressions， they were going make this thing called M expressions but at some point down the line。

 someone made a parser that just took in these and started actually you giving that out to people。

 people started getting used to writing these and then they were like well。

 seems like it's good enough， I guess we'll just have people write S expressions and that's why list looks。

The way it does today。 So that's what we're seeing when we see these S expressions。

 This is the structure that they have。Do we have any questions right off the bat about what's going on here？

Yeah。What does the S stand for？What a good question。 I should absolutely know the answer to that。

 and I have no idea。S expressions。 I don't even know what the M stands for either。

 the one that they were gonna show to the programmers。 I'll look it up。What other questions we got？

Okay， cool。 So this is how we are gonna be writing programs in our beautiful language that we're implementing together are once to keep forlay or whatever we may choose to call it。

 This is what our input programs are going look like。 This is what the programmer is going to write。

😊，Oh。It might have been， was it symbolic， symbolic expressions， that might be what it stood for。

I'm not sure， though， I I wouldn't swear to it。So okay。

 this is how our our programs are going to look in our programming language。 So okay。

 we've got these， these common elements that we're seeing now that we know what these expressions look like。

 how will we actually represent these in Ocal。In some ways， a string does feel natural。

 We're programmers， we write our programs as strings。

 we're enteringju a sequence of characters into something， a file， a terminal， whatever。

So let's play around with that， what if we do just do it as strings？

So here we are back in our compiler。That we played around with a while ago。Well actually。

 I'll start by just reminding us what was happening and our compiler。

 because I know it's now been a little time since we last saw this。

 So the main thing that's happening is we have this compile function， right。

 which the only thing that it's in charge of doing is coming up with the。

String that is going to represent our assembly for whatever program we put in and we constrained it very tightly at the start。

 we said， okay， the only program that we're going to accept is going to be a number。

 not a very exciting program but we're going go ahead and make the assembly that puts that number。

 whatever it is into RAX And so if you recall RAX is the name of one of the registers that we have available。

 we only actually have a few registers available about 16 and so one of the things that we're going to be messing with as we are thinking about cogeneration all along is how can we shuffle things in and out of registers in a way that makes things work for us。

RightAnd so if we take a look at what's actually happening in this assembly， it's saying， okay。

 I'm going to make available a thing called entry。 I'm going to make it available to the outside world。

 Well， why did we need that available to the outside world， It's because we have this runtime。

 We implemented our runtime in C and C is expecting that there is gonna to be something called entry available。

 And it says， okay， I'm not writing my entry thing right here？

 Instead I'm expecting that something else externally is going to provide it？ Our assembly code is。

 in fact， the thing that is going to provide it。 whoops。

 this was generated by a later version of the compiler pretendend it looks more like that。

 So we would go ahead and say， okay， I' am expecting to see an entry thing。

 and our assembly code says no worries。 I've got your entry thing。 And then we have this label。

 It turns out we are using that for starting a function。

 We'll later find out that we can use this label for other things。

 but we are using it to represent the start of our entry function。

 And then we have this move instruction。 This is one of the X86 instructions that we are。

GoTo be able to use it just says go ahead and put this value 50 into the register named RAX。

 and then we have this RE instruction， which just says return control to whatever previously had control。

 So what previously had control Well， it was the runtime right we called this entry function right here。

 And so control returns to right here， the C runtime chooses to go ahead and print out whatever it got back from entry。

 What did it get back from entry。 That's a little bit weird。

 We don't necessarily see anything coming back from entry， But in fact。

 what C expects is that it is going to find the return value of whatever it handed off control to inside that register RAX。

 And so what did we choose to do Well we chose to put the value associated with our program inside the RAX register And so when runtime do C or our C program chooses to look inside that register。

 it is going to find exactly what we wanted it to find。And that's how those things all tied together。

And then we had a little helper function that was going to go ahead and pop all of that text associated with the assembly instructions into a file。

 and then we have a little little other helper function that's just putting into a file。

 running the linker and then getting us back the output from running it。😊，So far。

 so good on what our compiler does。Yes。😊，Why R X， yes。

 so we were not actually in charge of what register C is going look at right so we could have chosen to implement our runtime in some other language。

 in which case we would have had to make sure that we were putting that value inside whatever register it is expecting to find the answer in because we chose to implement our runtime specifically in C。

 we had to know where C was gonna to look you know I go look through the documentation。

 I go find where it's expecting to look it says I am looking in RX。 So I say， okay， fine。

 I'm going go ahead and put an RX。 Now， when we are just communicating with our own programs。

 our own assembly that we have made， we do anything we want， right all bets are off。

 but once we're handing back control to see at that point。 we had better make sure to put an RAX。

分 up。Amazing， okay， so that's where we're at。 So now let's go ahead and let's keep thinking about how we actually want to represent these programs because I think that's sort of the。

 the key thing that we're going to wrestle with before we get to unary operators。

 So let's go ahead and look over here。😊，And。Let's write ourselves a little expression。

 So let's do E1。 and let's go ahead and say if。X， Y，z。Not a particularly exciting expression。

It's a string。I guess that's okay。But say I go ahead and have another program。

So say maybe I make something called increment， right， and I call it on four。

 and I want to get back five。So say this is what I've got as my two programs that I'm considering。

 what might make these actually pretty annoying to deal with？

If I am trying to process this string character by character。

 if I haven't done any processing to turn it into a nicer form。

 go ahead and discuss with folks nearby。Alright， so what I'm hearing as I'm eavesdropping on you all。

 sorry， is that it just seems kind of messy， right。

 Like say we're going ahead and we're looking at that first character and it's a par。 Okay。

 at that point， we don't really know anything about what to do。

 So maybe we go ahead and we look at that next character。 Okay， well it's an eye。 Well。

 unfortunately， we still don't know what to do， It's an eye here as well。

 And so then it can get even worse， right， because what if we actually have a bunch of space here。

 That's actually fine， right Like they should be allowed to do this， right。

 it just gets pretty messy having to keep track of all of this character by character really just manipulating it as a string。

 We could do it right， There's nothing saying we couldn't do it， But boy。

 wouldn't it be nicer if we had some other representation And so if you remember。😊。

Back during our paper exercises， we had this thing that looked like type project equals sample or dress of int or suit of int star int。

What if。We took advantage of the fact that we can create our own types。

 We can create our own constructors and actually made something that is going to give us a nicer。

 easier to manipulate representation of our programs。 So let's go ahead and do that right now。

 typey S X for S expression。😊，And let's go ahead and give us a number of constructors。

 I bet if you chat with someone nearby， you're going to be able to make some guesses about what constructors we would make available based on what we were just doing on the whiteboard。

 So feel free to turn to someone nearby and make those guesses。

This also gets at some of the questions that I think we ran into last week where folks were asking。

 can our types be recursive， Yes they can， and we asked can we have lists of whatever length？

In there， absolutely， no problem。So okay， this is starting to look pretty good。

 We've got our S X thing， right， It really， it doesn't look that different from the examples we were seeing before。

 right， Like this really does kind of look similar to how we've already made types last week。

 So hopefully this isn't scary terminology。Do we have questions about this SSX type so far？Okay。

 cool， it's okay if they come up later。Now， there is one annoying thing going on here。

 which is that now we have to go ahead and write out this E1 in a totally different way。

 So we're going to have to write it out something like LST。Sim if。Sme X。Sim why。Sim Z， okay。

 I don't love doing that， which hopefully means that all of you can figure out why we might want to have a parsel。

 why that is a part of the compiler that we might be interested in having。

 So we will go ahead and see a bit later how we actually do that for the purposes of today。

 We're actually just gonna use sort of a really simple parsel that is just turning this into turning something like this。

 into something like this， assuming we play nicely according to the rules of our spacing。😊，Okay。

 so that's what we're gonna be doing for now。 Let's play around with this。

 now that we have it later on， you will write your own parsers。 But for now， even for homeworks。

 we're just going to give you a parser that's going to basically take care of turning something like this into something like this。

Let's go ahead and see what we can do if we start representing programs in this way。

 So let's go ahead and do。Let which constructor。Let's have it take an S expression。

And let's go ahead and just use this to figure out which construct we have used to create。E1。

And so based on the activities that you saw last week。

 I want you to take 20 seconds discuss with someone nearby。

 what is the construct we're going to want to put right here， What's that first keyword。

 We're probably going to want to type on line 10。Go ahead and chat。Anyone want to yell it out？

I'm hearing match。 I totally agree， right， This is the the way that we've already seen for how we can check which constructor we use to actually construct。

 So let's go ahead and match E with。😊，And let's consider if it's a symbol。In which case。

 we can print a symbol。Or if it's。A number。Or if it's a list。

And take a moment to now predict which of these we are going to get。For our E1。Let's call it on E1。

Hopefully everyone did predict a list。That's what we can see。

 sort of that outermost thing right here。Okay， so now we figured out which constructor。

 this is kind of a boring thing to do with these exos compressionions。

 but maybe we can start doing something a little bit more interesting。 Let's go ahead and try。

 This is gonna to be a really weird program analysis that wouldn't really make a lot of sense to do。

 Let's try just adding up all the numbers we can find in the program text。 boring， weird。

 but it's going to give us a sense of how we can start messing around。

With this representation of a program。 So let's go ahead and let's still match all of these。

 But now suddenly， we're actually pretty interested in producing a number。

 right We'd like that to be our output。😊，And so what do we want to produce if we see a symbol。

 I'm going argue that's going to be a0。 What about if we see a number， Okay， well， in that case。

 we'd better give it a name because we probably want to produce the number itself as output。

 So let's go ahead and have N be the output there。 What else do we need to do。Well。

 this is the one that's getting a little bit weird。

 go ahead and chat with folks nearby for 20 seconds。 what are we going to do inside this list case？

这个。So I think。I was hearing all the things I was hoping to hear。In your conversations。

But I haven't quite made it happy yet， any guesses about why I haven't quite made it happy yet。

That's right。 I'm trying to call total， but I didn't tell Ocael that I'm allowed to use total recursively。

 So let's just make sure Ocael knows that it's okay to use it recursively。 Okay。

 I want us to write one more of these funny little program manipulation functions before we take our break。

 But first， any questions about this one。Like again， this is a super weird program analysis。

 there's not really any reason why we would write this program analysis， but we can。

Why does Ocal not assume that a function is recursive by default？In general。

 OHael design tends to lean towards let the compile like let the programmer express more about their intent。

 right so you've seen cases we've talked about the fact that you can add type annotations。

 We talked about the fact that you can put pars around things that don't necessarily need Pars in order to communicate with the compiler in general。

 the scientists have tended to air on the side of let the programmer be in charge。

 like there are things we're looking out for for the programmer， So if you think of the match cases。

 right， we're looking out for those cases where those are not exhaustive。

 So there are definitely things that the language is trying to sort of guide you away from。

 but in general， errors on the side of making sure that the programmers in charge the programmer has agency。

Good question。Okay， cool。 I'm gonna have us write one more of these。

 I also wanted to mention now that we are playing around with this compiler again。

 I want to just remind you all if you go on the website， you can find a link to the class compiler。

 The thing that we are all constructing together。 It's all just going into Github。

 You can look at it at any state。 You can look at it the state right before we start class。

 You can look at the state after we do class。 You're always going be able to actually see this code base if you want it。

😊，So okay， let's go ahead and do maybe a slightly more interesting。Analysis here。

 So let's figure out if the thing that we are actually processing， if it has an if statement inside。

 So let's see if we see a symbol。I'd say lets go ahead and have that be false because we really don't want to see just a variable named if。

 presumably that's allowed right now， a name that is if we actually want to see an if that's actually appearing at the start of one of these lists because we actually want to see if we have an if statement。

Or an if expression， actually， So let's go ahead and say false if we see a number and then again。

 we'll have this actually be the interesting case。 again， please discuss for just like 20 seconds。

 What do we want to have in here。要そけす。O Ocal letting us do some cool stuff right here。

 So we've talked about the fact that Ocal is basically a really convenient language for building programming languages。

 this is one of the reasons right， be able to do something like this where we're able to go in to the structure of the program that we're processing and say。

 okay， let's take a case where the first thing in our list is the symbol if and then I don't care what it's cons to it can be anything。

 whatever， like all I need to know is that that first symbols and if and then I can do true。But。

The a compiler doesn't seem happy with us。 We've gone ahead and created a match case for all three of our constructors。

 Why isn't it happy。Yeah， so what if we still have a list。

 but it starts with literally anything else right， So we have not。

 even though we have made a case that starts with each of those three constructors。

 it is not yet exhaustive because we could have a list that starts with。

 say add one one of our operators that we are going be adding。

 So let's go ahead and do list L And in that case， we just want to go ahead and basically descend into the children。

 So list that exists。 This is just a nice little list function that's going to go ahead and see if any of the things that are being passed as input are true。

 So let's go ahead and do has if。Oh， and this is just gonna to oop， sorry。

 that's exists with an S at the end。 That's just going to check if we can go ahead and get back true from basically exploring any of the children。

 any of the sub expressions。 So let's go ahead and save that。Let's run it on。Our little E1。

 I'm hoping everyone else like me is predicting that E1 is going to give true since we do， in fact。

 have an if in there。But let's find out， let's find out if that's what we get。So， let's do。

And let's do has if。Yin。And it's true。Allright， that's where we have landed on playing around with the slightly nicer representation of our program。

 Let's take our five minute break。 We'll come back together at 436。

 and then we will go ahead and get into our unary operators。

 The reason we have started wanting a nicer representation。 Go ahead and take your stretch break。

 Take your water break。😊，Hello。Sorry， loud。必需要。Oh， right。Oh， I'll try to keep doing it。Okay， cool。Hi。

W of my friends。警 ask you。He has his。Application on September 2。Okay， okay。Is that possible？そとパすの。

I think so， so they did increase the enrollment cap for sure。嗯。

Yeah I guess that might be worth making an announcement to have folks come up and give me their emails。

Let me get a piece of paper。Tiny logistics note， if you are a concurrent enrollment student and you have not yet gotten the official invite into the enrolled class。

 please come give me your email right now just so we can make sure we get you。Get you in。

He hasn't send me his email。哦。Ma I come to the next class session。还可以自己演。多钱全了。Yes。

 if you're a comparative enrollment student and you haven't yet gotten like the official invite to the class。

 just give me your email so I can make sure we get you in。Amazing， yeah。

 I think David can't actually。Push that one through。 I think， we'll check。

 maybe he can I dont have a。 That would be great if they could do it。Okay。

 so I can't put you in until the enrollment form is in， but once it's in then I can get yeah perfect。

 perfect， yeah thumbs up。Oh I don't know， what do you mean by previous occurrence？Or just。Oh。

 it's all on the B courses。Yeah， yeah当 sir。Okay。路费。Yes， yes， thank you。ぱ this。Yeah。

 just go chat with David and they can get you an extension。だけそ。Yeah， yeah。

 just get the extension and that all goes like once you get an extension。

 it's all just graded normally as if you yeah。Uneasing， go ahead and jot that down。

Tell them to start coming to class， though。Tell them to start coming to class。O。All right。

 let's come back together。So I'm hoping that the particularly particularly unary operators that we are adding here today are not going to be super confusing。

 They are unary and that they are taking a single argument's there's one operaand coming in And since what we have right now in our languages numbers It's numbers that are going be going in。

 and the only thing we're gonna be doing is adding one or subtracting one as you may predict from the names。

 add one， add one and subtract one sub1 is going to sub one So hopefully we're pretty much on the same page about how those are going behave let's go ahead and figure out how we can actually make our compiler do this。

 We are finally， finally finally extending our language to do more than just having programs that are numbers。

 So let's go ahead and swap to looking at our compiler We have access to a little convenience thing that is going do our parsing for us as I mentioned。

 I'm just going show off how that works。 So we've got our little opensx thing we can go ahead and say parse this it is really not doing anything particularly interesting in there and as I said we are gonna to get to parsing later in the semester。

😊，We're not even really going to take a look in there。

 but what you can see is that it is going ahead and making things like what I wrote out manually。

 but it is making them automatically for us so that we can continue to write things in this nice familiar way and what we get back to the other end is this nice structured representation so I'm going to go ahead and start having us use that here in our compiler so let's get rid of all the stuff we are playing around with and let's use that same SX thing right there。

So okay， now we have that。The next thing we're going to want to do is make sure that our compile function。

 the thing that is actually generating。Our， our assembly instructions is taking one of these as input。

 So let's go ahead and change that from string to S X。 Okay， now what is going wrong， Well， first。

 we've been expecting。A string there。But also suddenly。

 we're accepting programs where it's not going to be sufficient to just go ahead and pop everything into this one slot in the program。

 But， you know， let's go ahead and start with just first fixing this up to still handle the programs we could fix in the past。

 So I think there's probably an obvious way to start that。

 which is let's add one of those matches that we've been using。

 So match program with and the one that we already know how to handle is if the whole program is just a number。

 So let's start there。 N。Okay， great。 That's the situation where we want to do this。

 We can't just use the entire program。 We're gonna have to use N。

 and we're gonna have to change our string formatting。 And then so far， so good。 Now， obviously。

 okay， Emily is complaining。 This is not exhaustive。

 So let's go ahead and make sure that we can communicate when there's a program that we don't yet know how to handle is input。

 So let's go ahead and add something what we will call a bad expression exception。 So bad expression。

😊，Of S， X。 And this is just gonna be our way of saying， hey， honestly。

 I don't know what to do with this。 So if we get anything other than a number， a single number。

 as of right now， our compiler doesn't know how to handle it。 And so we'll go ahead and say， raise。

Bad expression for that expression。 We just don't know what to do。Okay。

we're getting pretty close here。 Okay Camel is giving us a little bit of a hint about something else that is not going right So what is that Well we've got this program that's getting the red squiggese why is that Well it's getting a string as input right and so we're going to have to go ahead and make sure that what we are passing to compile is not a string but is one of these S expressions so let's go ahead and just call parse on that。

Okay， now it seems to be happy。So let's just make sure that everything is still working the way we expect it to work。

 Let's try running this。We'll make sure that we can still make our。

 our tiny little programs that just have numbers。 So we'll do。

Open the compiler and let's do compile and run。33。Nice， okay， that still works。

 We've also gotten another little side benefit here， which is， if you remember。

 before we could still run things that shouldn't have been allowed as programs， but now。

A we're getting our little bad expression exception。

 And we get all this other random nonsense as well。 But， yeah， you know。

 we're getting the thing that we wanted。 So basically。

 we've already gotten a little side benefit from having this nicer representation of programs。

 So we seem to be going in a good direction。😊，But。There's still more we want to do because it turns out we want to actually add these other things。

 right， Like we don't just want to handle only numbers anymore。 So let's see what we can do。

 Let's see if we can go ahead and start doing something maybe a little bit like this， right。

 So let me put put a proposal here， right， We can go ahead and have a match that is going to go ahead and actually handle the situation for。

Our add one， right？ we'll have our list。 We'll have our add one appearing first。

 but we go ahead and actually do the addition before we pop in the end。

 So if we take a look at one of the concrete programs that we were looking at over on the whiteboard。

 this would basically be saying that for this program。Add 1，50。

 We could produce assembly that looks something like。Global entry。Entry。Move。R X 51。Rt。

So I want you to discuss with folks nearby is， is this？A nice。

Piece of compiled code to produce for this program。 Do we like that as the output。

 Is this the thing we should make， Disc for about。40 seconds。后呢。そ点。レビられ。All right。

So I want you to go ahead and hum if you think， yes， we are happy with this output。

And how if you think， no， we are not happy with this output。

Yeah okay so we've got some uncertainty and I think that makes a lot of sense。

 so I think the people who are humming for no are probably thinking of a program something like this right so in another few weeks we're going to get to accepting input from the user we're going to have this little read construct and that's going to allow folks to go ahead and enter some input right at the command line and as soon as that is happening trying to produce something like this becomes impossible right we're going to have to go ahead and make sure that the compiled code itself。

 the assembly is in charge of doing the addition for us because we won't know the value in advance right。

Now I also get what folks would hum for yes here because in this case for this particular program。

 we can in fact， figure out at compile time what value is associated with actually doing this addition。

 and so eventually even later in the class， we are also going to see how there are optimizations that will let us change from something that is doing the addition right in the assembly to something that goes ahead and just puts 51 directly in the assembly having figured out that this is one of those cases where we do know all of the values in advance。

 but as a general purpose way of handling it， we don't want to jump straight to just assuming that we can do all of the calculations at compile time。

 we have to assume that we're going be able to we're going to need to be able to do it at runtime。

SoOkay， let's go ahead and look back again at our compiler。



![](img/fe80c520e68686f852e656c733f267ed_8.png)

And basically what this is making me think is we are about to start having to interact with a bunch more assembly instructions right all we've seen so far。

 really， we've seen some directives right this is thing that's declaring that we have this entry available。

 that's a directive， this thing that's just a label that's a directive。

 but we've only actually seen two instructions so far。

 And so I'm going to have us quickly take a glance at this little library that we are going be expanding over the course of the semester of the directives and the instructions that we are going to be allowed to have right so we are going to be able to use this global that we've already seen。

 this label that we've already seen， this move that we've already seen。

 but today we're also going to need to have access to add to sub。 we've already seen RE。

 So these are the X 86 instructions that we are going to be allowed to use over this course。

 and in fact， we are actually going to have more that will be coming in。

 we will have a resource posted for you on the website of this particular subset of X 86 instructions that we are using in this class。

 but these are all the ones we're going to need for today。😊。



![](img/fe80c520e68686f852e656c733f267ed_10.png)

And it turns out that just as we actually used this nice SX library in order to have a nicer representation for S expressions。

 we might want to do the exact same thing for our nasty assembly that we've been building up right  building up this string directly is pretty gross。

 We might want something like this exact library to handle some of that for us and that's exactly what string of directive is going to do that is just going to go ahead and take in some directives and actually produce the kinds of strings that currently we've just been building up manually。

So let's quickly adapt our current compiler to make sure that we can actually do the same thing。

 but with this nicer representation， so let's open。AM， which is just to say。

 open this file that we just looked at。 And let's go ahead and replace what we are doing here with something a little bit nicer。

 So let's have this be global。Entry。Label。Entry。Nove。Register RAX， our immediate N。

And then our return。Now， this isn't quite correct yet， any guesses about why？Please yell it out。Yeah。

 so these are not a string and we promised we were gonna have a string。

 so we had better actually produce the thing that it actually can be consumed by our processor。

 which is exactly why we have this string of directive function here that's just in charge of taking this representation and turning it into the representation that we can actually pass on to our own processor。

 So let's go ahead and make sure that we are calling that。

 We are going to get introduced to something a little bit new。

 We're going have this pipeline right so this is our little pipeline and I'm going show us how we use it and I'm going talk us through what's actually happening here。

 So list map。😊，String of directive right， so that's the thing we just talked about。

 the thing that is in charge of turning things that have this directive type into a string。

We we're going to go ahead and pipe in whatever we get back from that into。

String dot concat specialized。With slash N。 Now， this is a little bit weird。

Because if you remember string do conca， you might recall that normally what's happening is we have string do andca and then one character and then a list of strings sorry one string and then a list of strings。

 And we're going to go ahead and sort of join them together with that。 So why is this working。

 We don't have this second argument here。 So this is working because of partial application。

 I'm going to show us another example just so we get a little bit comfortable because this is a trick that we're gonna be using throughout as we are writing programs in Ocael。

 And basically it means that what's happening here is that we are making a specialized version of string do andca where the first argument is assumed to be this slash n。

 So I'm going to show an example that's just with a different function。

 So let's go ahead and do let's take a look at the type of list do map。😊，Okay。

 what we're expecting is we're going to have a function as the first argument。

 The second argument is going to be a list， and then the output is going to be a list。

 but we can go ahead and actually specialize this。 So let's try doing that。 Let's do list map。Fun x。

X plus1。Now the type of this is just a list to a list， right。

 that function is no longer part part of the type anymore because we've gone ahead and sort of baked that in so we can give this a name so let's call this specialized。

And this is just a new function that we have available that is just going to add one to all the items in a list so we can go ahead and say。

 okay， specialized。Specialized if I can spell one， two， three。Great。

 it has added one to each of the items in the list so now that we have seen this example where we're seeing okay。

 we've started with list do map and we know that the type of list dot map is we get a function as the first argument then we get a list and then the output is a list but we are able to specialize it by just providing that first argument in order to make something that is just going to take a list as input and produce a list' as output now I want us to translate that to this string do conca example I'll show you the type of string do concat。

😊，And what I want you to do is with folks nearby， go ahead and predict what is going to be the type of strain dot andca when we're providing that first argument。

Discuss for 20 seconds。Remember that we read this as this is the first argument。

 this is the second argument， this is the return。All right， does anyone want to take a guess？

Fortunately， we don't need to guess okay we will just tell us it looks like that is going take a string list as input and produce a string as output right And so this makes sense because we can take a look at what was happening before。

 we were gonna get that string as our first input。 Then we're gonna get a string list as our second input。

 and then our output was gonna be a string。 And this is doing the exact same thing except that that first string input has been fixed。

 we have fixed it to belash n。 And that's what's happening here。

 We have this weird little specialized function that we've made right there that is just saying。

 okay， I want to go ahead and pipe in whatever I'm getting back from this previous section。

 pipe it into the specialized function that's just gonna match everything together with the slash n。

 And so that's what we're doing when we have the pipeline is rather than putting the list map on the outside when we don't even have the list yet。

 putting the string duck and cat on the outside when we don't even have the list yet。

 We can use this pipelineing， which says whatever happened before。

 go ahead and pipe that into list do map calling it with string of directive and then。😊。

It on this list。 And then whatever we get back from all of that gets piped into string do and cat mashed together with a s。

 So this gives us a slightly more sort of linearized way of looking at what is happening as we go through this sequence。

So okay， this is starting to look a lot cleaner， but we still haven't actually created our had one case。

 so let's start work on that。 We might not actually manage to finish before the end of a class。

 but let's let's see how far we can get。 So if we say list。Sim， add one。A。

What would you and the person nearest you physically closest to you？

 What would you say is the next thing I should write here。Please chat for a minute。

This is not the answer， this is not the answer。So why is what I have just written here not a good solution？

医療は。Yeah， this is all well and good if what we have right here is a number。

 but the whole point of writing these programs is that we can recombine these constructs over and over and over。

 So if I can switch us back to the whiteboard right what I just wrote there is going to work great if we have add one。

50， no problem。 If we have add one。Add one。50。All of a sudden， this is that argument。

 and that isn't just a number。 We can't just pop that whole thing right into the appropriate part of the assembly template that we have made up together。

So what is the right thing for us to do， I'm going to ask you to sort of contemplate it with folks nearby for 20 seconds。

这啊。や。Wantna check it。え number？All right， so I want you to hum if you think that we should do one pattern for add1。

 another pattern for add one add1N， another pattern for add， add one， add1N and hum for that。Okay。

 well， we forgot with one vote， That's great。 What about for maybe this is a case for recursion？Yeah。

 I have to agree。 And so we're gonna to have to do a little bit of refactoring to make that happen in percondicular。

 you can see that we've got this sort of front matter that's happening right we've got this global entry。

 this label entry， those are things that should happen only one time。

 We've got the thing that's actually returning control to our C runtime。

 That should only happen one time。 So let's start in on the refactoring that is gonna make this a lot easier for us when we actually add or add one operator next class。

 So in particular， let's go ahead and have something that's just for handling the teeny tiny component that's specialized for the particular expression we're handling right now。

 whereas we'll have a little wrapper。😊，Then that should take care of putting those front matter。

 that sort of boilerplate together for us that will take in our program of type SX。

And we'll go ahead and have it produce a directive list。 So let's have。Directive list。

 Let's have it produce that。 And then what are we going to want to do。 Well， actually， you know what。

 let's have this produce a string。 We'll have this produce a directive list。Directive list。

 And then this can produce a string。 And that's going to save us some trouble in terms of not having a mash everything together。

 in each of these cases， we can go ahead and have this sort of wrapper function that's in charge of that。

 So let's just real quick see what's going to be happening in here。

 It's going to look a lot like this。We're going to want to have。

The same sort of front matter that we had before。 Now。

 this was specific to the particular instruction we were dealing with。

 So let's go ahead and get rid of that。And let's go ahead and start mashing together these lists。

 right So here we're doing the thing where we turn it into strings。

 Here we're doing the thing where we actually mash it together with our slash N。

 but we do want to have something in the middle here。

 Does anyone have any guesses about what's likely to go in the middle here。I'll give you a hint。

 we've got something else available to us。Yeah， so I think that's where we're actually going to get the code that is going to be specific to the expression that we want。

 So let's go ahead and call compile X。 Let's call it on S X。

 the thing that we're getting in is input right now， we don't have anything that's specific to that。

 And that is what we're gonna to do， which means that next time when we pick up later， oops， sorry。

 we called it program。

![](img/fe80c520e68686f852e656c733f267ed_12.png)