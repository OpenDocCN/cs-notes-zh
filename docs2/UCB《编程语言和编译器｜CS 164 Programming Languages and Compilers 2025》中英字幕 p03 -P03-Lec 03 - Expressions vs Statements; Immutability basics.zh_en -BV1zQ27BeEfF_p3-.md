# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p03 -P03-Lec 03 - Expressions vs Statements; Immutability basics.zh_en -BV1zQ27BeEfF_p3-

![](img/3f597cc09a12f90392d9f49f5cc5b682_0.png)

![](img/3f597cc09a12f90392d9f49f5cc5b682_1.png)

All right， hello everybody， H Thursday， I hope everyone is having a good one。

I wanted to check in real quick on where we stand with logisticacy stuff。

 if you can currently run OcaMl programs on your machine， please hum right now。Okay， I'm excited。

 This is good progress。 and we are very happy。 A quick reminder。 at 9 PM tonight。

 we are gonna have that first homework do。 I'm gonna to be honest。

 our goal for that homework is really just that you can run O programs on your own machines。

 So that's the main thing we are trying to accomplish with that homework。

 The other thing that is gonna be do at 9 PM tonight is that first drill。

 Remember that those deadlines are together so that you only have to have one of those deadlines on your on your calendar。

 just mash everything together that all the deadlines happen at that same time。

 So please go ahead and make sure you are taking care of those things。😊，てく。

Were the homework supposed to be graded？number of was really。No。

 you will get scores for the submitted homeworks after the submission deadline。Yeah the the young。

I am saying。レビな。Come follow up with me if you find something about that。 Yeah。

 I'm not aware of any 10 AM things。 Sorry about that。What else might be coming to mine？Okay， cool。

 In that case， we've done logistics chat。 I'm super excited that so many of you can now run Ocal programs。

 That is awesome progress。😊，Another thing I wanted to talk about a bit。

 and this is actually of course related is why we are using O Camel for this class because this's probably one that y'all have not used before。

 And so that's going to be a little bit interesting， a little bit different。

 This is something that actually relates to a topic we'll be thinking about a lot over the course the semester because this is a programming languages and compilers class。

 which is why do we ever choose any particular language for any particular programming task that we might be facing What are the factors that should be influencing that decision。

😊，So as we are building our own languages， when we are doing our design。

 we are thinking quite a lot about what kinds of programs we want to make easy。

 what kinds of programs we want to make hard， what kinds of programs we want to absolutely forbid。

 there's all of these various programs that we think are going to be buggy or unsafe or hard to reason about。

 and we're trying to actually put those off limits。But then we're also thinking a lot about， okay。

 I want this kind of program to be relatively easy for programmers to build as I'm going to try to give them support for doing that kind of thing or doing that kind of reasoning。

 that's the kind of thing that we are thinking about in general as we are thinking about language design。

And so what is it that O Camel is actually good for， What is it that it is good at doing。

 And so quick hummming survey， who here has heard of the programming language rust。Yeah， okay。

 I figured that was probably gonna to be one that folks would have heard of。

 So way back when right Ru was pretty recent actually， but back before we all had heard of Ru。

 before people had actually implemented Ru， Ru was just an idea。

 Someone decided I'm going make this language。 And they wrote the first implementation of rust。

 So does anyone I want to yell out a guess about what that program。

 the program that implemented rust that was a compiler for rust。

 And he guess about what that language was。I hear it Ocal。 Excel， guess， that's exactly what it was。

 Yeah， so now Rus actually has a compiler written in rust， right。

 They are going ahead and having their own compiler written in their own language。

 which is quite popular actually to do。 But before there was a way to run rust。

 they had to write that compiler in some other language and that other language that they chose as Ocal。

 And so if you get a bunch of programming languages folks or compilers， folks in a room。

 and you start talking about Ocal。 One of the first things those people are gonna say is oh man O Caml。

 that's basically the domain specific language that's just perfect for writing compilers。

 writing interpreters， all of the abstractions that it's giving us are just really great for the kinds of things that we want to do when we are actually building a compiler。

 And so in fact， you know the Facebook or I guess it's meta now， whatever。

 the Facebook compilers team is using Ocal， this is just sort of what you use。

 So one of the reasons that we are using it is because it is realistic。😊。

Another big reason why we're using it is it's going to let us write a lot of compilers and interpreters real fast。

 which is important since we have a fixed time over the course of the semester。

 and there's only so much time we can spend on all the sort of fussy stuff we'd have to do to set up compilers quickly in other languages。

 all the various boilerplate and other various stuff we'd have to set up around it in order to then focus on sort the core compiler implementation decisions。

 whereas fortunately with Ocal， we're going get to skip all that fussy stuff。

 skip all the boilerplate dive straight into the stuff that's about the core of how do we implement languages。

So that's a little bit of background on why we are going ahead and using O Caml。

Okay I would like to go ahead and pick back up where we left off on Tuesday。

 so I'm gonna to first remind us what we had gone through so far。

 I guess I have to zoom out so we can see everything。

 So we decided to get out of this computer science racket start taking up dressmaking。

 We had developed some types and we were able to use them just the same as any other types that were built in and so we made this fabric type。

 we figured out what would be the cost per yard for these kinds of fabric。

 we went ahead and made this item type， we had various constructors for things of type item we went ahead and figured out how many yards of fabric we would require for a particular item。

 And if I recall correctly this was the last subactivity that we had been working on and in this we were figuring out how much we were going actually spend to make a summersuit or wintersuit and that leads us up to our next little subactivity in which we are going to do this So I'm going go ahead and leave as much of the prior one up as I can。

 but if you can't see all of this。You want to be able to scroll back。

 you can go ahead and open up that same OamL activity to on your own machines。

 They are linked from the course schedule。 but with that。

 I'm going to ask you to silently reflect for a moment on what will be printed out by lines 1011 and 12 right here。

And then we'll have you discuss with someone on your by foot first。

 make your predictions silently to yourself。All right， go ahead and discuss with folks nearby。

I'm going to briefly scroll up to show some information that we might find helpful。

We might be interested in something around here。Round here。And I'll scroll back down。All right。

Let's go ahead and make some guesses what do we think？For line number 10。Yeel it out。哦。

I heard wow why are we making a summer dress out of wool。

 go ahead and hum if you think that's where we landed？H， if you think it's something else？I agree。

 Good job， team。 You have landed in the right spot。

 And so hopefully one of the things that we've started to pick out is all the kinds of cool stuff that we can do with this pattern matching。

 Like we're really digging pretty deep into that structure of the item that's coming in here At first。

 we might have been thinking about this is just glorified ifs and else's。 But now we're finding oh。

 wow， we can go in and we can see that there's gonna be this item。 And if it's gonna be addressed。

 then we're gonna go down this match。 statement if it's not gonna be addressed。

 we're not gonna go down and then we're actually able to access this yards。

 that's very interesting So there are all these things that we can actually be breaking apart。

 we can be giving names by actually using this pattern matching this yard's name was actually introduced right here on the left hand side of this map。

😊，Okay， on to line 11， what do we think is going to come out for line 11？😡。

Nice winter dress sounds good， hum if you think that。Home if you think something else？Nice work team。

 that's exactly right。 Okay， what next， what do we think for 12？😊。

I'm hearing linen suits aren't really in right now， that of course is a lie。

 but who thinks that's what the program would produce for us？Who thinks something else？

I totally agree， right， so this is exactly right and y'all have developed exactly the right model of what Ocal's up to。

 I'll go ahead and just run it real quick just so we can see， oh， did I not paste it in。😊。



![](img/3f597cc09a12f90392d9f49f5cc5b682_3.png)

No， I did paste it， great， we're good， let's run it。



![](img/3f597cc09a12f90392d9f49f5cc5b682_5.png)

All right， we got the exact。Things there。Great predictions， everybody。

 This brings us on to the next part of this activity。

 At which point we are now going to reflect for a moment about the types that we've been working with。

 right， we are using this colon to mean has type as we've talked about。

 We want to go ahead and now indicate what types we are expecting these to have。

 Ocamel isn't gonna to make us do this， right， Like if we take a look back through the programs we've been looking at We really have not been using colon very much in here。

 we have not mostly been talking about， okay， here's the types that we're expecting this to have as we're doing sort of these things。

 But we have the option to do so。 So we are totally free to communicate with Ocael to tell Ocael more about what we are thinking。

 what we are expecting to have there by putting in that colon and then saying a type。

 And so now what I'm going ask you to do with folks nearby is go through lines 5 through 12 and decide what type could we write in this blank。

😊，And feel free to chat with folks nearby right from the start this time。



![](img/3f597cc09a12f90392d9f49f5cc5b682_7.png)

Sorry， wrong playground。All right。Are we ready to start adding them in？

I'm going to ask everyone to yell in harmony。What do we think for this first line？I agree。

What about On6， what do we got here？I'm hearing float。What do we got for Z？Wow。

 y'all are good at harmonizing， what do we got for linen？Agreed， what about sample？Sounds good。

 A line dress。Parallel structure， What do we got for suit？Well bit。

 what about our summer dress right here？Let's see if we got it right。 A， we got it right。

 good work team， fantastic。😊，Okay， so look now that we're in the in the swing of things with putting in type labels。

 we're going to go ahead and do the same thing， but specifically for our functions that we're playing around with。

 So again， go ahead and turn to folks nearby and now let's figure out how to fill that hole and that hole and that hole and that hole Sarah。

 Sarah。

![](img/3f597cc09a12f90392d9f49f5cc5b682_9.png)

![](img/3f597cc09a12f90392d9f49f5cc5b682_10.png)

All right， we're starting to quiet down， so I'm guessing maybe we are ready。

Shall we go ahead and start？Fillling it in。What do we think in this one？Hearing fabric。

What about right here？That feels good。What we got here， yards required for IM， what's the input？Okay。

 it was a little bit tricky， I put that pee there， but that sounds good。

What do we got for the output？Feels good， what about over here， fabric budget？All right。

 the name kind of gave it away for that one， didn't it， what do we got here？And one more here。

 where we got coming in。And we got coming out？Let's see if we got it。Ay， well done， great work team。

 yes。I think I understand。 So in this case， the question is about， hey。

 we don't have this match going on。 So what's going to happen。

If we're trying to use something that isn't going to have item and fab。😡。

Is that what the question is？哪位。Mmhm。Ex。Really not sure。Okay， I think I understand the question is。

 did we cover all these cases？Yes， yes， yes。 I didn't include all the。

 the wild card catching cases in the， in the version in the P D F。 I was， I was compacting。 Yes， no。

 very good question， very good question。 Yeah， this was also mostly intended for type annotations rather than a program that we'd actually run。

 The the earlier version was better for running。😊，Do we have questions about these type annotations？

Yeah。あ後アらみ。When you call it a。I bridge。I think this is a question about constructors， is that right？

Yes， okay， great question。 So here when we are creating type fabric， we have three constructors。

 linen， cotton wool。 When we are creating type item， we have three constructors。

 fabric sample dress suit。😊，And then we only have one way of creating a project。

Is that maybe the question？It's just a constructor， y， the suit thing， the stress thing。

 all of those， just constructors。I'll use it function。Ourre values and functions interchangeable。

 Very interesting question。 So we are going to be able to pass around functions as values。

 So if that was the core of the question， then yes， absolutely。😊，Okay， cool。



![](img/3f597cc09a12f90392d9f49f5cc5b682_12.png)

Amazing， okay， so what the question you just asked is actually perfect。

 perfect setup for what we're about to do because now we're going go ahead and go through this and what I want you to do is you don't have to actually use a highlighter。

 I know you don't have this on paper out in front of you。

 but I want you to go ahead and every time you see a use of a type in these seven lines。

 go ahead and identify that's a type。 every time you see a constructor， go ahead and identify。

 that's a constructor。And then we'll go through it together， go ahead and discuss with folks nearby。

All right。Let's go ahead and reflect together。 So who thinks that this fabric right here is a type。

Who thinks it's a constructor？Who thinks it's something else？Who wasn't sure when to home？Okay。

 fair enough， well let's chat about it more for 10 seconds。All right， let's try it again。

Is this highlighted fabric， is fabric a type？Is fabric a constructor？Fabor something else？Okay。

 I totally agree。 That's a type， right， It says type right next to it。

 Hopefully that one wasn't too sneaky， right， That's how we're making types fabricric is a type。 F。

 What about linen， Hu if you think that's a type。😊，How if you think that's a constructor？

Home if you think that's something else。Okay， cool。

 Looks like we're on the same page about how we're making these， these types of constructors。

 What about item， Hum for type。Home for Conor。I'm for something else。Awesome， same page。

 That's a type， right， That's definitely a type。 What about suit of intstar int， Wow。

 really hard to highlight。 What about suit of instar int。 Is that a type。😊，Is that a constructor？

Is that something else？Oh， I totally agree。 You all are doing great。 Yes， that is a constructor。

 right， We're going go ahead。 We're gonna make it a suit。 It's gonna have some data attached。

 What about ink， Go ahead and hum， if you think type。😊，How if you think constructor？

Hm if you think something else？All right， we were feeling a little hesitant。

 but I liked where most of the humming wass， which was on type， In is a type， feels good。 Yes。

 into is a type。 questionsions about that were so far so good。😊，Yes。😊，Is suit by itself something。

 I guess if I were gonna to ask like in casual conversation， hey， what suit。

 I didn't like say out suit and start in。 I be， yeah， that's the constructor。 right。

 Like that's a convenient name to call the constructor， Yeah。But yeah。

 if we were going to highlight the part of the program that was the so constructor。

 then I would highly hopeful。Other questions， yeah。I love this question。

 So this question is basically what are we doing when we use one of these constructors。

 I think the analogy that has helped me most sort of connected to things that people are already familiar with is when you use the string true in some of the programming languages that you're familiar with or you use the string false。

 right， those are making something of type Boolean。😊，You're doing the exact same thing here， right。

 We have gone ahead and actually made the type ourselves。 We have made the constructor ourselves。

 but this is just the way we make something that has that type。

 that is one of the ways that we can make something that has that type。Makes sense， yeah。Okay， cool。

 so what about this string right here on line4， it says linen hum， if you think that's a type？

How many of you think that's a constructor？Honey， do you think it's something else？Yeah。

 I totally agree。 right， That's a type of organ record。 That's just a name。

 I sneakily called it linen， but that is just a name that we are using inside the program。

 What about here， if you think that's a type。😊，How many do you think that's a constructor？How。

 do you think that's something else？Fantastic， yeah， absolutely that's a constructor。

 we are going ahead and constructing something of type fabric by using the linen constructor and then we happen to also be calling it linen albeit with a lowercase spell。

😊，What about？What about this right here， Is this a type？Is this a constructor？

So there's something else。Absolutely great。 So this is， in fact。

 we you can sort of use our knowledge of Ocanl syntax such that even if we hadn't seen all of this stuff up above。

 we would still know this is a type because it has this colon here， right。

 And we can always read that colon as has type。 So we know that that's gonna be item。

 What about fabric sample， if you think type。😊，How if you think Conor？

How' know if you think something else？Cool， same page。 That feels good。 What about。This right here。

 home if you think type。H if you think constructor？How if you think something else？Yeah。

 awesomewe work。 That's a constructor。 What about boofs that didn't highlight the way I wanted。

 What about this for right here， How if you think type。How if you think constructor？

H if you think something else。Nice， yeah， this is just a value that we're using。 You know。

 depending on how you wanted to think about it， you could maybe try to think of that as that's one of the many constructors for type in。

 But I don't really think that's helpful， right， That's just a value that we're using。 So okay。

 sounds like we're on the same page。Yes， so this question is about linen sample， A line dress suit。

 these things that we are writing here right after let。

 what are those those are names and so in fact one of our bar next activities is going to be thinking a lot more about what we're doing with lead expressions Yeah really good question。

Okay， cool。So it'd see， oh， yeah。Please。Like beyond。

I'm not sure about people saying this object word。 We're not talking about objects。 So the。

 the question seems to be， if we're highlighting the string that I have highlighted right now。

 is that the constructor。And， yes， absolutely。 That is us using the constructor。

 That is the constructor。在。At what point does it become the value， Oh， I see。 Yes， So as student。

 right， like the， the part that I have highlighted here in the text of the program， right。

 that is a use of the constructor。 When this gets evaluated， when it is executed。

 we're going to go ahead and get a value back from that。

 And that is going to be a value that has type item。Feels good。Yeah， great question。

 excellent question。Okay， cool， so I'm going to go ahead and start bringing us back to the compiler that we worked on last week。

And。Let's see。Let's look back over it， because I think we now have。

OsI think we now have some more context for understanding what's happening in there。

 so if you recall the thing that we were doing was we were making an implementation for an extremely extremely simple language。

 right， just the language that has ins in it， not super exciting。

 but we were able to go ahead and produce programs that looked like this。

We were going to go ahead and we're going to get out some kind of simple forline assembly program。

And basically what's happening inside this compile function is the process of mashing together the strings to make that assembly program This compile of file was just going ahead and dumping it out into a file that we could then actually use to run it and this compile and run was a little helper function that we made that would go ahead and actually create the assembly using compile the file it would then go ahead and turn that into machine code。

 it's a simple translation， but someone's got to do it。

 it would link it up with our runtime it would actually run it and then it would tell us what is the output from having run it so that's sort of what's happening inside this program right now。

😊，And if you take a look at this， you might be noticing that this looks somewhat different from some of the other programming languages you' used in the past。

I think。Kind of one big reason behind a lot of that。

 And so if y'all have heard about OMl in the past， totally fine if you haven't。

 But if you have probably one of the things that you have heard about it is that it is a functional programming language。

And so I want you to take about a minute to chat with the folks nearby and chat about what could it mean for a programming language to be functional？

What would make a programming language， a functional programming language。

 It's totally fine if you're just guessing。All right。

 so go ahead and just yell out some things at me， I want to hear what you're thinking。需要方式。Love it。

 pure functions， what else we got。In mututable state。 What else we got。No side effects， love it。

Lambda， lambmbda calculus。First class functions。I love it so we've got a lot of stuff in mind and I think all this is absolutely going to be relevant。

 but there's one thing in particular that I really want to draw our attention to because it really changes the shape of the programs that we're building。

And that is， it is going to be expression oriented， right， as opposed to statements。

 a lot of what we're doing。Is built around expressions。 And so what do I mean by that。

 We're gonna dive in it for a moment。 But basically。

 if you look at this function that we've got right here。Right。There isn't a return statement。

 There's nothing saying， oh， return this。 All that's happening is we have this one big expression。

Inside the function that we're going to evaluate。 and whatever we get back。

 that's what we're going to get back。 That'll be it。

That is sort of the expression that is associated。With this function。

And so I want to talk a little bit about the difference between expressions and statements。

 but I also want to talk about how this connects to the idea of being a functional language。

 So in general， I know it's a little bit weird when we're used to having very crisp well definedfined definitions。

 There is no sort of one true definition of what makes a language functional。Part。

 a lot of the features that we might like from functional languages have been making their way into languages that we traditionally would not have called functional。

 It's really getting adopted in a lot more places。 And so it's kind of this weird， fuzzy line。

 It's still useful for us to be able to use this term functional to quickly suggest some of the ideas y'all just shouted out。

 but it isn't really going to be a hard defining line between functional and nonfunction。

But one of the things that is going to be really common here is that we are building up functional programs around expressions。

 So even though the real sort of dividing line between functional programming languages and nonfunctional programming languages is the people who like functional programming languages are going to call the languages that they like。

 they're going to call those functional languages and they're going to call all the other ones nonfunctional languages。

 even though that's sort of the real dividing line in terms of how it gets used in the day to day。

 a lot of what we're thinking about when we are thinking about what determines if a language is functional or not。

 is whether we are building up these expressions and really expression oriented。

And so most of the time。When we write a function in Ocal。

 we really do mean it is a function in the mathematical sense of the word function right so it is a binary relation between two sets。

 it associates each element of the first set with one element exactly one element of the second set and we are going go ahead and be able to call a particular function on value 3 and get back some other value。

 maybe five， which means that if we call that function on three again in the future。

 we' are also going to get five back then right it is just this mapping between those two sets and that mapping stays the same。

So that's one of the things that we're seeing here is we are going ahead and using mathematical functions when we are talking about functions。

But I know this is all still a little bit fuzzy。 And so I want to be a little bit crispr about the difference between a statement and an expression。

 So in particular， what we mean when we say expression。

 is that it's something that is going to resolve to a value。

 So we had that awesome question earlier about when we use a constructor at what point do we actually get something that has the type were expecting it to have。

 right， So when we are executing， when we are evaluating， when we are resolving。

 that's the thing that we are doing there， right when we are executing our program。

 if we are executing it and we are going to get a value back。That is going to be an expression。

On the other hand， a statement is mostly interesting to us because of the effect it is going to have on the world。

 right， You might also have heard this called side effects。 And so something like printing。

 something like putting something in the file， something like going out to a server that then is going to store some state on the server。

 right， all of those things are interesting to us because they are having an effect on the world。

And they're not necessarily going to give us back a value。So in general。

 if you're looking for that really crisp definition of what we mean specifically in Ohamel land when we say an expression versus a statement。

In Ocal， if a snippet of code resolves to unit， that is a statement， right， And so unit。

 you may remember from when we were chatting before， that's what we say when we mean sort of nothing。

 we got nothing in there。 you might have seen it written unit。

 You might have seen it written with the two pars immediately next to each other。

 So if we're getting back unit， that's a statement。On the other hand。

 if we're getting back any value other than unit， that is going to be an expression。

 And we have this， this nice sequencing operator， the semicolon that we're going to be seeing a bit of。

 and we actually will look back at the program we've already played around with to see examples as well。

 This is just an operator for doing sequencing。 and it is going to give us a warning unless the program snippet on the left is actually giving us back unit right unless the program snippet on the left is。

 in fact， a statement。 So what we see right here， print end line high。😊。

That is going to give us back unit right that print statement that's something we're interested in because of the side effect it has the effect where it prints something out to the screen for the user to look at。

 And then after that we have this value 3 that is going to resolve to the value 3 And so that's totally fine to have the semicolon between those because the thing on the left it's going to go ahead and produce unit On the other hand。

 if we put three first then the semicolon is going to be a problem for us。

 And oh Caml' is going to say no no no， no no， the thing on the left of the semicolon thing on the left and our sequencing had better have unit type unit。

So far so good， I know it's a little bit wacky before we've actually played with it ourselves。

 but hopefully it's starting to come together。Yeah。

 I often explain it to people as think about it like none or Nell or Neil or the various other things you've seen。

 But basically just means no value Like， we don't got a value there。 That's all we're really saying。

 And the way that we pronounce it in Ocamela's unit。

Allright so let's take a look at how this actually played out in this program that we have seen already。

 so you can see that we have been using that sequencing operator。

 but I'm going to point out a couple different ways so right here we've got our sequencing operator right we're going ahead and doing something here that we care about because of its effect on the world we wanted to actually put this particular string。

 the compiled program into this file and we wanted that to actually happen out on the on the some directory in our machine right and so we cared about that because of the site effect it is not going to actually give us anything back we can see from I'm sort of hovering over output string and we can see that what's coming back is unit and so then we go ahead and we actually have our sequencing operator and at the end we go ahead and we close out the file and in fact what we're getting back from that is also unit。

So that's what we're doing there。 I want to quickly mention that this is the semicolon we use for lists。

 So don't mistake that one for the the sequencing one。 And I'll also try to disambiguate one more。

 So we've been using Utop and we've been doing use compileile M L。

And then I use that semicolon semicolon right there different right that two semicolon thing is just for communicating with the Reple and saying I want to go ahead and make something happen right now so as opposed to if I do like if I do three times three right？

Okay， I have told that that I want to get back that value that would be associated with actually running three times 3。

 But if I do three times 3。No semicolonons。 It doesn't know yet to give me the value。

 So that's all that that semicolon semicolon means。 So that is different from the sequencing one。

Okay， yes。What happens if you just do one semicolon in U top So it is the if you then use it as a sequencing operator and you next put something else out。

 then you're going to go ahead and have the same behavior you would have if you use it up here。

 but I think you're asking about this question。Yeah。

 so it doesn't yet know to actually treat that as we're done。 We're ready to get some， some feedback。

 So I have to go ahead and do。And then it gives the syntax error because it's like。

 why are you using this weird sequencing operator in weird ways？

Other questions we're ready for our five minute break。All right， reflect on if you have questions。

 take your five minute break， grab water， we'll be back in five。Hi。Okay。Yeah。Flow the。こpoのです。

And both。Movinging with my book comment I D。我烦 a C1，6，4。That is odd。

 I would say go ahead and go to one of the GSI office hours。They should be able to fix it up for you。

 but yeah， I don't interact directly with the instructional machines。The of about your homework was。

Oh yeah， we can get you an extension， that's fine。But yeah like the goal of this homework is to make sure that everyone can do this kind of stuff right so we're trying to get that out of the way early so that you've gone ahead and actually made sure you can access all this kind of thing but yeah it's fine to get an extension for this one we just want to make sure you have access before the next homework。

I mean this one。おそ。Whats make。Oh。そ。this。My soul is to。嗯。You used to buy my own computer。record。哦，O。

I mean， we're no longer supporting the old 2021 way of。Working。

 but you should absolutely feel free to use that if you prefer it， that's totally fine。

Like if you just want to run it directly on your machine， that's all good。

 we have no problem with that。I'm sorry about that， yeah。I think the imitation doesn't work me。

I guess。In so I can't see the homework very weird， we will get you an extension。

 go ahead and talk to David。Sorry the head GSI who came here at lessso。 Yeah， yeah， the same answer。

 Yeah， you got an。 the form and then talk to them in Everyone who's having this kind of issue。

 We're gonna go ahead and just like automatically get the extension tomorrow。😊，I know。よろしい。重要。でき。

あの次に。Al right， so I want everyone to take a look at this right here。

 We have switched over briefly to Python just for fun E。 Would you call this a statement。

 hum if you think statement。Howome if you think expression。Okay， interesting。

 So let's try maybe a simpler case。 Well， okay， we can go ahead and run that。 What if we did。

 let's see。Expression or statement。I'm hearing expression， cool， what about 18 hum for expression？

Home for statement。Yeah， cool。 I agree。Expression or statement， Hu for expression。Home for statement。

Yeah， I agree。 right。 So， you know， it's certainly true that inside here。

 we are building up something that has a value， right， So we have in this one。

 we have this expression that is happening inside the print statement。But yeah。

 the reason that we are interested in print is because we are interested in that side effect where it prints out to。

For the user to see。 Now it's weird because here we are in the repel and it's going ahead and actually printing out the values。

 even when we're doing an expression。 But the reason we're normally using print inside our Python programs is that we can go ahead and have that side effect of showing something to the user。

So hopefully that helps us get the idea of expressions versus statements in a slightly more familiar context。

Now let's turn back to O Cammel again。And so we've already sort of talked about this。

 We talked about the fact that there's no return statement here。

 We've just got this one big expression， right We're going to go ahead and mash all those strings together using string and cat。

 That's going to get us back our value or it's going to be a value that has type string。

 so that's just one big expression inside here。Whereas here we talk about。

 you know we're using that sequencing operator， we actually do have this output string statement。

 which we are using to actually get something into a file。

 and then we go ahead and actually put something else after it in sequence。

 which turns out to also be a statement unless we get back unit as the entire type of the function。😊。

Are we feeling pretty okay so far on statements first expressions？

New questions or we're feeling okay， unit versus not unit。Cool， all right， so okay。

 if questions come up later as well。So now I want to talk about some of the other things that are a little bit wacky about O cameel。

 So， or at least that might be unexpected。 So let's say。This。We have made a name。

We've said I want to use x to refer to this value 2。Now。

This is a little bit weird relative to what you might be used to seeing。

 because this does not mean that we can do。Not allowed right and that's because what we have in X is just a let binding。

 It is just going ahead and saying I want to go ahead and use x as a nickname for the value2 in something in this case because we're on the top level it's in the entire rest of the program。

But it is not a variable。😡，It is not a bucket into which we get to put whatever value we want。

 So we can't go ahead and do this thing where now we're saying， oh， okay。

 now go ahead and replace what was in that bucket before with some new thing。 Instead。

 if we take a look at this let binding right here， all that's happening is we're saying， okay。

 I want to be able to use this name file to refer to this thing right。

 whatever we get by evaluating this program snippet。

 I want to go ahead and use that with this name file in right。

 And so here we're being very explicit in this snippet of code。

 So in the body of the lead expression。And that's a little bit different from what we see up here because we don't actually have in written here。

 but all that's happening is when we actually do one of these let bindings at the top level。

 we're actually not bothering to put in because OKM is going to behind the scenes transform it for us so that the in is just the entire rest of the file。

So that's what's actually happening when we make a new name at the top level with our lead expression is behind the scenes that's transforming it so that everything else is the body of this lead expression。

Is there a difference between this and macros， I'm not sure I see the connection。Oh， okay。

 so I think this is asking is any program transformation macro。

 So everything we're doing during compilation， everything we're doing during your interpretation is going to be a manipulation of the program。

 right， We're doing something。 We're choosing to do something。

 We're choosing to make some kind of transformation of some representation of that program。

 Not all of them are macros。 Yeah， lovely lovely question。 Yeah， yeah。😊，Is that also a function？

Can you say more what you mean？The same。only。I got you。

 I think we're gonna to have an example in another few minutes that I think is going to answer that question for you。

 So hold on to that question。 Is there another question down here。No， we're feeling good。Okay， cool。

 so I'm going to show us an example that I want us to look at。

 and I want us to predict what is going to happen because I know it's a little bit weird that we have immutability。

 so let's go ahead and take a look at this program。And I want you to。Turn to。

The folks next to you and start making predictions about what is going to be printed out when we run this program。

I'm just going to zoom out so that we can actually see it all。Go ahead and discuss with folks nearby。

Just to make sure I've been totally clear， I want to be clear that in our lead expressions。

 it is the body of the lead expression， right， so the thing that comes after the in that determines the value that will be associated。

With。The lead expression as a whole。 So when we evaluate this entire lead expression。

 the way that we're actually going to figure out what value is associated with that expression is by evaluating the body。

 and it is inside that body that we get to actually use this new name we have created in this case file。

All right， back to looking at our program。And please do feel free to chat with folks nearby。面器有什么。对。

All right， so we have our answer key right here。So what happens Well first we go ahead and introduce this name X。

 we map it to one， cool。We see that that exists， that that happens。

 We go ahead and make this print X first version thing。 We see that okay。

 we have access to that as well， that is a function maps from unit to the unit great。

 then we introduce this name X， and we give it this value too。

And then we go ahead and make this new function， print X second version。

And then when we actually call them down below， we can see that our second x is2。

Our first x is still one。That is still one， so basically we can actually use our editor to give us some more information about what's happening here。

 so let's hover over this X。 it is going to tell us where else that definition of X is being used right so here we've mapped X to 1 we are using that here right inside this part of the code and then also here right we are accessing that we are reading that value1 from it and then if we take a look at what is associated with this definition of x we can see that it's just this usage。

So the compiler is actually helping us reason about where we can use these names。

And that is where in this text that we are looking at that represents the program， right。

 in where in this program text， we can use that name。SoOkay， I'm going to have us look at this。

 and then we'll come back together and discuss a little bit。

So go ahead and discuss with folks nearby what is going to happen when we run this。Allright。

 so we can scroll down and see that， in fact， we're getting the exact same thing happening right。

 And that's because this is just what Ocal is actually turning this into under the hood right So what's happening internally because we are doing all these let bindings at the top level So it's not inside a function。

 It's not inside some other scope。 It's at the top level because we are doing that is just internally converting it into all of these nested lets where the body of the let is just the whole rest of the program。

 So this is just trying to represent to you what Ocaell is actually doing to this。

 even though we see it as looking rather different。😊。

And so that's why we get those same answers right there。Okay。

 we will come back and talk more about mutability if we have time because I think it's a very fun topic。

 but now we want to talk for a moment about the fact that O Camel is a statically typed language。Oh。

 sorry， were there questions about that unrolling before I move us back to talking about other topics？

Okay， cool， we'll come back to it if we them， yes。doesn't change。

The value of your expression doesn't change after runtime。 I'm not sure I understand the question。

Let's say between longer。有。导一。I think the question is， what if we do let x equals3 or something。

 And the question is， is that。Is that going to affect anything， that's the question。

Let's go ahead and take a look at what happens we can go all the way and see。

Does that answer the question？Like we do go ahead and make this new name X that gets mapped to three。

 but that's nothing to do with these other x's that we were using when we made print X first version and print X second version。

Right， that's a different X。 And so if we actually， we click on that。

 we can see that that's not getting used anywhere， whereas we can see that this one。

Is getting used right here。Make sense。Theer expression。The value expressions I determined。

Come to chat after， I'm not sure I totally understand the question。

Other questions about immutability？Okay， cool。 In that case。

 let's go over here and let's take a look at what can we call compile on。Right so it turns out。Again。

 O Camel is a statically typed language， meaning that the types will be checked for us before we ever run the program。

 right， in a dynamically typed language， our types are going get checked。 Yes。

 but they'll be checked at runtime。 We are talking about checking the types at compile time。

 which means we can go ahead and say， let's do， let's see。 which shall we do。Let's do。嗯嗯嗯。

And it's already going to know right now we've not run anything。

 It already knows that it's mad about this， right It does not like that we have provided an int for something that it is expecting to take in a string。

 Now what about if we do this， fine， no problem， that's all good。😡，Unless I've messed up our。

Pasing somehow， but that is actually fine。 Oh， I forgot our equals。Okay， so now it is happy。

 and just to show you that it is still unhappy with that， it is unhappy when we've got our in。

It is happy。When we've got our string， because we told it that we are promising compile to have strings and we can tell that even now before we've run anything when we're just sort of here in our editor looking at the program。

 because at compile time， we can go ahead and check our types。

 So that's what we mean when we say that this is a statically typed language。Now。

I want us to think about something that is a little bit wacky if we are thinking about that。

 which is。Let's do。We'll have Fk one take input。And produces output input。

 So this is our our funny little function。 And I want you to talk with the folks nearby。

 What is the type of funk 1。Discuss with folks nearby。No problem， we can call funk one on four。

No problem， we can call if I going on test。Keep chatting。Okay。So this is a polymorphic function。

 meaning it is allowed to take in things with different types。

 And so if we actually take a look at what type it has， it has these little type variables for us。

 It's saying it's going to take in something up type A。

 and it's going to also produce something of that same type A。

 but I'm not going to tell you what a is right， Like I'm going promise that these will have the same type。

😊，But I don't actually know what that type will be。 Now we can choose to restrict it， right。

 that is totally fine。 So if we go ahead and say， no， I actually only want this to be type int。

 right， So now if we go ahead and get the new version and we try again。

 that still works still okay to call it on4， but suddenly calling it on test is not so good。

 right because we said and we want to go ahead and restricted。

 even though nothing about the function is actually causing us to knee to restrict it。

 we have chosen to go ahead and put that type annotation that is causing it to be restricted。

 And now if we actually have variable， we'll see in int。But if we go ahead and leave that。

Unclear in the text。Then it's going to go ahead and just say， we don't know。

Plymorphic can take many types。Okay， we are going to take a real quick tour through oh。

 and I will briefly mention that we are actually going to learn much later in the semester how O Camel is doing this。

 right， like what's going on behind the scenes such that it can figure out what type should be。

 where， even if we don't tell it。 and when we do tell it， how is it checking。

 whether that's allowable。But that's going to come much later in the semester。

Because it is going be useful both for well， for all of the homeworks that y'all are doing。

 we're going to take a real quick tour through list manipulation functions。

 I believe you're also going to be seeing some of this content in section。

 So I'm not gonna actually go super deep on this。 And also。

 there's a lot of resources out there on list manipulation。 But you know。

 let's just see the quick tour。 So first， let's make ourselves some kind of a function that we can use。

😊，So we're going to use this F thing in order to actually double some stuff。

 So let's go ahead and do list dot map。And we will use our function F that we've just made。

 and we will use  one，2，3， Pre boring list， pretty boring output。

 but we can see that we can go ahead and use this map thing in order to apply the function F to all of the items from this list Please remember to use semicolonons rather than commas and stuff here。

 when you are making lists at first， it might look like it's working when you use commas。

 It is not working when you use comms when you're making a list， use your semicoons。

 but this is basically our map， which is going to let us go ahead and do that same process repeatedly over and over for a bunch of items in a list。

 Now it turns out that okaym actually has anonymous functions。

 These are like lambdas that you may have seen in languages like Python。

 so we don't actually have to have something like F that has been named we can go ahead and do something like fun X。

X times 2， that should give us the same answer， and indeed it does。

 we're getting back that same answer。We can have it do something else。

 we can change it right there in line。So okay， so far， so good on using map。

 But what if we don't want to have sort of the same number of items in the list that we're getting out the other end。

 What if we actually want to yank out some of those items， We don't like them no more。

 So let's go ahead and start using our filter。 Now we're just gonna go ahead。

And throw away some things。Oops。Change the wrong thing。So let's do that X。Less than three。All right。

 so now it's saying， okay， we're going to go ahead and filter out all the things that aren't going to pass。

So that's a way of saying， okay， one， less than three will allow it， two。

 less than three will allow it， three， not less than three doesn't appear in the list that we get out the other end。

So that's our filtering。And now let's go ahead and do one more。

 So what if we do want to use all of the values the way we did when we were using map。

 But we want to actually use them in some way that mashes them all together into one output value。

 So let's go ahead and try that out with fold left。

And now because we are mashing together multiple values。

 we're going to have to have our function take two inputs， so we'll have it take x and y。

 and let's go ahead and just do x plus y。 This is pretty boring。

 This is basically just going ahead and doing summing for us。

 We could probably come up with some other thing we could use that would do somethinging for this。

 but we can go ahead and implement it ourselves this way。

 and now we get the sum from adding together those numbers。

So fold left is just saying let's start from this starting value。

 and I'm going to call this function on this starting value and the first item。

 and then that will have been accumulated， right， we'll go ahead and get that one value。

 and that will be here in X， and then we'll call it with the second item being two。

 the second argument being two。 So we'll add that together and we'll get three。

 and then we'll add that together with three and we'll get6。

 and that is our output that we get out together。So far so good on left， we feel okay with that。Okay。

 cool。 So definitely you'll be getting a lot more practice with doing these kinds of listss manipulation functions。

 I want to quickly talk about some things that are convenient for us。

 which is that we do actually have the ability to just use operators here so we can go ahead and do that and get the exact same thing out。

 We can go ahead and do。😊，That and get out， well， it's kind of boring with zero。

 but maybe more interesting with one。Okay， oh yeah， it's actually the same thing。 Okay。

 And now let's go ahead and try something slightly different。好。What's going on。Any thoughts？Actually。

 I got it a little bit。 What I'd really like to show is。This。Well， oh， what's that happening。

 Why won't it show me， Go ahead and brainstorm for 20 seconds with folks nearby。All right， yeah。

 nothing deep there。 It's just that this is how we start a comment。

 And so O Camel thinks that I have started a comment right， We left this parent star。

 Those were right next to each other that sure looks like the start of a comment。

 So unless I go ahead and close it out。op unless I go ahead and close it out。

 it doesn't know what to do with that。 And so the way to fix that is to go ahead and keep those spaces in there。

 it's totally fine then。 So I just wanted to point that out because I've been saying that Ocal is white space insensitive right when we were talking about tabs earlier。

 we were realizing that it was not actually going matter。 And so in general。

 whitespace doesn't matter。 However， if we land in the spot where we have sort of mashed together tokens。

 sorry we're gonna learn later what tokens are where we have mashed together some characters that actually cause Ocael to interpret our program as using a different part of its syntax。

 that's the only time that white space is gonna matter。

 So this is just a little goshcha to be aware of。 but in general。

 it is gonna be white space inensitive。😊，Okay。So that's what I wanted to cover there。

 I think we actually have time to do one more quick activity from this one right here。

 So get ready to chat with folks nearby。 And we're gonna talk briefly， briefly。

 briefly again about immutability。 So oh， no that' statements。 It's not that interesting。

 We can talk about it real quick。 This is basically saying， okay。

 I want to go ahead and use the let binding。 But I know I'm getting back unit。 And so therefore。

 I'm going go ahead and do this let unit be unit。😊，Nothing too exciting there。

 so I'm going to have a skippped at and go look at this example。

 so go ahead and chat with folks nearby， what do you expect will come out of running this program。

All right， I know this is weird， what do we think is going to come out when we run this line。

 anyone want to yell it out？I'm hearing too， home if you think too。How of you think something else？

All right， all right， what about for this print that we've got right here， what do we think？😊。

I'm hearing four。 how if you think four。How if you think something else？All right， cool。

 and then we've got this print right here， what do we think is going to come out？I'm hearing two。

 how if you think too。How if you think something else？Okay， nice work， y'all。

 So we can go ahead and look up and see that that's exactly what happens， right， We go ahead。

 We get our2。 This makes sense because we can see that we're binding Y to 2 immediately beforehand。

 So， yes， absolutely， that's gonna be 2。 And then we can see that in here。

 this seems to extend only through here。 But it does extend through there。

 And so when we access y there， it is indeed going have the value 4。😊，But then。

 then we are done with that lead expression， and we are done with the body of that lead expression。

 which is to say the only part of the program in which y is going to be controlled by this binding。

 And so then as soon as we're back out here， we're still in that body of the lead expression associated with this naming。

 And so here again， we are going to use that why great predictions， everybody。😊。

Do you need the parentheses around the lead expression， Yes。

 so we do in fact need to communicate where the body is going to end。

 there are some cases where it's unambiguous。 so basically in the same way that we add parentheses in math when we want to disobey the order of operations OcaM will also has an order of operations if we want to obey that order of operations fantastic。

 it's gonna to group things for us whatever old way， if we want to do anything else。

 we're going to have to add the print so in general。

 I strongly suggest over communicatingmun to the compiler by adding more parents to be more clear about what you want to be treated together。

All right， thank you everybody， I hope you have an awesome rest of your week。

Where did the 10 come from Where's Se again， Where did the 10 come from？

Where does the 10 come from Oh， that's from up above I'm so sorry， it was just showing like， oh。

 we can have some other binding appearing at the top level and that doesn't matter at all for these because we're inside these lead expressions。

Oh so when we are in the Reple right so we're down in our U thing when we're in the Reple。

 it's going ahead and telling us about anything that it learns about so as soon as we see like in the same way that when we see this function right this unit to unit function。

 we didn't tell it print that out for us but we're in the Reel so it's going to go ahead and just pop that onto the screen。

Like， under the。

![](img/3f597cc09a12f90392d9f49f5cc5b682_14.png)

Shading。That one I did go ahead。