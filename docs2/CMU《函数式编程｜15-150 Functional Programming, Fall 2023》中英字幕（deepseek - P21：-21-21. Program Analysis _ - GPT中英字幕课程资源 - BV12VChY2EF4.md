# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P21：-21-21. Program Analysis _ - GPT中英字幕课程资源 - BV12VChY2EF4

Okay， so thank you for coming to the second special topics lecture。

 I'm really excited that I was able to give the one Tuesday on compilers it was a lot of fun and I'm hoping this one will be similarly fun One thing to note is I am very。

 very tired so I got to reset the momentum。😊，O。Let's get going。

 I cannot host off the momentum of previous。 All right， program analysis。

 What is program analysis Va， I talked to you about compilers and compilers are pretty cool。

 but they're not as cool as they could be because the thing about a compiler is the compiler is like Staoddgy and dodgy and it has no fun。

 Okay， it doesn't go out on weekends。 It doesn't party program analysis by comparison is hit。

 It's cool。 It has more than two friends。 Okay， so so our metric for program analysis here is going to be what well。

 first of all。

![](img/91940326e45c8c5d137c628535e93796_1.png)

First of all， we have to talk about what program analysis is and then maybe we'll get into why it's cool okay。

 so I have a few things for you， but let's get into it shall we？😡，I am wearing my shirt。

 thank you for pointing that out， all right。I'll clean this up somehow by lesscycl please Okay。

 last time nothing， but last time is like nothing forget everything that happened I'm kidding。

 the last lecture is actually quite quite relevant to this one。 Okay， the state of software。

 well before I can talk about programs and things we want to analyze， I got to talk about。

Programs like software like the real world。 and I know scary。 we live at CMU。

 We're here in our academic bubble， but I come from the industry and I come with tidings from outside。

 Okay so the state of software is long ago， long before you were born on August 20，2011。

 Enprene in Silicon Valley venture capitalist Mark Andson。

 he published this article called software is eating the world。

 and this was mostly focused on like economic and financial reasons such as business oriented reasons I should say。

 which is that at that time， you know software was really starting to take over。

 you started seeing all sorts of economic sectors being impacted by this ease of communication。

 this ease of access， ease of usage， because the internet， by the way。

 is pretty convenient in case you weren't aware so among other things like your ability to reach brand new audiences was unprecedented right。

So nearly a decade after this article， this is not， this is not a surprise to anyone here。 Okay。

 like we are very aware software has already eaten in the world。 Soft has won。

 We are living in the cesspool of software。 Okay， we are in a post software world。

 So the point I'm making to you is simply that Mark Anden， you know。Currently。

 board director for Mepltforms， bless his heart， he was right， okay。

But now what about software engineering， which I know some of you are interested in So engineering is currently and very much is a lucrative job with a lot of jobs available。

 why because everybody needs software， it doesn't matter if you're I think tank you for're a massage parlor。

 if you're a pet store okay you need software， you need a website you have data you have customers。

 which means that everybody， no matter where they work needs software， yeah。Well。

 you would have thought that that would have happened already， but the this demand is still so high。

 you know， like yeah right。I don't know anyways， so the point is that software has embedded itself into every aspect of our lives and that's great news for you studying computer science because it means that you if you want to have a job。

 you're going to have a job at least that's what the class of 2023 thought to but the point is that not every single software engineer in the world was educated at CM not all of them haveve taken 15150 and that means that not all of them know about the importance of writing either take your pick of correct code。

 safe code， good code so on and so forth the things I've been wanting to teach you all semester So we have a little bit of a problem here because there are tens of millions of software engineers out there in the world okay and one thing I've always said to you in this course is I'm trying to produce we're trying to produce as little code as possible why because every piece of code every line of code we has the possibility of a bug there was that one time I literally said like oh yeah know if you write something too many times you you write it wrong and then I wrote it wrong on the board and then if you review the bo。

Do very funny but what do you think we can say then about the overwhelming deluge of software that's being produced by these tens of millions of software engineers everywhere around the world What do you think we can say about all of this code？

😡，Would anyone like to hazard a guess？Yeah， its it is so unbelievably horribly messy and we're in the we're in the trenches right now。

 we are screwed， okay。😡，Unrestricted access to code writing。 And it's。

 it's on a level that's unprecedented， because guess what。

 You to have to at least look on a Python tutorial for 20 minutes online to code。 Now。

 you can plug plug a prompt into chat GT and you can code。

 And guess how many of them are thinking about the correctness。

 the cleanliness or the beauty of their code。 Gu how guess how many times chat E is thinking about that。

 So we're in， we're in a spot where we're reaching more and more importance in terms of being able to make sure that our software is one of these three things。

 We want to make sure that we are producing good software。 We're not in the business of writing code。

 We're in the business of writing correct code again。 So。😊，What do we do about it？Well。

What does it look like when you write a mistake in your code， Okay， for instance。

 it might look something like this。 Maybe you made a typo， Maybe you meant to call fact recursively。

 And then how do I fix this Well like。Call it real right Maybe when you make a mistake。

 you declare a variable and you forget to use it。 Actually， this is a really。

 I have a bone to pick with this one。 I this is a very like really important one。

 Like I what's happening here Basically， I'm showing you Tffold de。 I declare this left folded thing。

 And， I didn't use it。 Al right， SmL and J does not natively give you a book for this but Good compiler as well。

We will replace them with left folded， but this is another classic mistake。

 you know you were just off somewhere else you pushed it on your stack you said， okay。

 I declare left folded and then you were done except that then you forgot about it very classic kind of mistake that you can make raiseise your hand if you made this one。

Right， yeah。So or maybe you just have something as simple as a type error you call foldar and then what did you do。

 you didn't give back all of the arguments， maybe you gave foldar， you didn't give foldar F。

 which you should have done the combining function and then fix files is obviously just to add it back but these kinds of things are errors programmers make errors all the time okay I would say that the main thing that we got out of last lecture with compilers is why do we improve over assemblyly language well first we can write code faster and secondly it'll tell us anything about the code that we're writing right。

😡，So these simple mistakes happen all of the time， all the time of like an SNL andJ won'tn you about this one。

 but that's okay， it could theoretically。😡，So we're lucky to work in a language where it'll warn you about most of them if you misspell。

 it'll warn you if you make a type error， it'll definitely warn you。

 all of you are very aware of that fact right but some languages do not have that privilege Python in particular will literally warn you about none of them okay I'm so serious with that and so what I want to be able to say is I want to be able to catch these errors at compile time and if your language is I' a notion of compile time like before it runs basically but before I run the program before I stumble over it。

 I should be able to say hey like something might actually come up when you executing your program because otherwise what am I executing my program for okay I'm just running over selectagite with with my eyes closed for no reason。

😡，And I always like telling this story when I'm motivating this kind of thing。

 but why do I want to catch arisstically， all right， here's the story for you。

You are a machine learning engineer。A horror and you spent six months working Oh that TVs out just realized you spent the last six months working on this large language model and you're real proud of it and you want to put it to the test So you rename some。

 you leave some comments and then you're like okay。

 it looks good LGTM you push it and then you go on a vacation to France after running it okay and then while you're in France you have a great time you know you come back。

😊，And your model filled with name error， name modley is not defined， did you mean model？😡。

This actually could happen， this actually does happen okay。

 you could be 200 compute hours in and then not know that your program has a simple typo that'll just mess your day up。

😡，SML and jano， though， why， Because what it's doing is the compiler needs to know a lot of things prior to letting you run your coat。

 It's a responsible parent that's not gonna let you run into the play pen with the knife out。 Okay。

 so the point is that this is the knife out。 This is the bad thing。 Okay， so let's try to。

 let's try to do better than this， right。So what's my point here， okay， programmers make mistakes。

 wow， crazy。But's。There's a lot of programmers in the world and these silly mistakes， if there's a 0。

01% chance of it happening， guess how many times it's happening。😡，A lot， okay， a lot of times。

 so we need to be able to make sure that our compilers， our tools， our programming languages。

 are capable of making sure that these errors and more advanced errors even don't happen because the cost of doing so is really。

 really high。😡，Remember Tony Hoor， his billion dollar mistake， we were talking about this battle。

 this uphill slope where there are billions and billions of dollars resting on this because that's just the scale we're talking about when it comes to the software。

 the amount of software being produced in the world。😡，And it' it's not just a wanting to thing。

 it's a security thing it's making sure that we can be be safe about or you know relatively assured that our society will continue to function and the outlook is not looking good at that front okay。

😡，So how do we fix these mistakes， What do we do， Okay， how why am I saying all this。

 How do we make sure that all this software that exists is going to be okay well？😡。

Software seeing the world。Let's bite back。There's a reason why this is called program analysis。

 we're going to talk about program analysis next and I also I highly recommend this book。

 a coworkerworker recommended it to me， I think it was pretty sobering in terms of the things I've been alleging to。

呃O。😊，Let's fight back。Program analysis what the hell is program analysis well program analysis is the art I'll say of discovering unwanted behaviors in programs usually by automated means as humans we do a kind of program analysis ourselves like you know I see you use be。

😡，Actually， I don't know what to put here。 I was gonna to say something about like style style grading。

 but I don't actually care that much。 But my point is basically。

 I can look at your code and be like maybe you shouldn't have done that。 Oh yeah， if you do this。😊。

Whos ever done this？Don't do this。 This is like things in Sml you shouldt know about。

 but it's the second or last lecture so while to spoil it this is like a terrible primitive that you should instead pattern matching for my point being okay that。

😊，Program analysis is how we find these unwanted behaviors。

 and this might include a lot of things might impact the correctness of our code。

 the performance of our code， the security of our code， which is tied to a correctness。

 but any it's really any property that it' worth noting about the program。

 which are a lot potentially。😡，And at its core program analysis is the art of writing programs that analyze programs I'm big into meta kind of stuff。

 I'm into recursion， so to something like me， this is like catn， okay， I love this kind of stuff。😊。

And usually comes in one of two flavors here， okay， two special herbs and spices， one。

 we've got dynamic program analysis， raise your hand if you prefer this term。😡，Okay。

 that's fine I was wondering dynamic program analysis means I'm going to figure out the properties of this program by running it by at runtime I'm going to instrument it maybe and then discover something about it so there's a technique called fuzzing or basically you throw a bunch of random inputs at a program and you see if it like throws bad or if it doesn't need some kind of specification profiling you might consider as well which is literally just running your code and I measuring how long it takes I might call it that like a dynamic program analysis it involves running the code or even just running test a writing tests that will run dynamic program analysis is pretty cool it goes straight to the point it goes it actually evaluates presumably what the program does。

But that's also not a great thing because it means that the time it takes to run a dynamic program analysis is tied to how long it takes to run the program itself。

 if it takes a really long time， we might have to wait a really long time to evaluate it or if it loops forever or crashes。

 well then we're going to do the same right。So嗯。We're going to there are really good applications for this and generally when you're writing software。

 you want to have a mix of this and the next one'm going to talk about。

 but we're going to focus less on this， this interests me appeal nerd less。😡，ok。And then this。This。

 this is where it's at。 This is static program analysis， which is， as you could probably guess。

 trying to figure out properties of programs without ever running it。 How could I do that？ Well。

 if only there was some kind of funny like tree like form。

 I could put a program into that I can then you know evaluate to find figure out the behavior of Oh wait。

 didn we talk about that last lecture。 Yes we did So programs are trees right。

 which means we can write simple recursive functions that just go down the tree and figure something out。

 maybe they figure out， oh， you could have folded this concept， maybe maybe Val X。😡，Equals 1 plus2。

Maybe this could just be three， but maybe it doesn't need to fix it for you。

 maybe it might warn you on your IDE， that's a static program analysis。😡。

This will be our focus for today and there's a couple of different reasons why this is important one of them is sort of the domain I work in static application security testing that is static program analysis for the purpose of security scan your code to figure out whether or not you are vulnerable to some outside attacker which is really really important okay even though I won't talk about too much today。

😡，Also something as basic as syntax highlightating。

 it can something that might be an incomplete program and try to color it I would call that a kind of program analysis albeit one that's maybe a little less interesting or auto formatting if you run an auto formattter。

 it takes your code。😡，Auto formats I don't think I need to explain that that I would say is also kind of like analysis of what your program looks like of what your program is or type checking even is the most fundamental kind of program analysis that you're very very familiar with a type checker just looks at a program and then figures out what all parts of it have the type of if there are any such things okay I would call that a program analysis of itself。

😊，嘅。😊，三。This is the mission okay， this is where we want to go。

 but before I can talk about the technical details that go with this。

 there's one small tiny bite size you know atomic issue in front of us and that issue is the fact that。

😡，Program analysis is inherently impossible。😡，How many of you have taken 15 to 51？

And you probably know what I'm alleging to， which is that program analysis there's this one nice little theorem in mathematical computability theory which states all non-trial semantic properties of programs are undecidable and if you don't read Rice's theorem okay by the way。

 this is like a real real theorem like this will apply to everything。😊，In English。

 what this means is this。You cannot answer definitively yes or no in a finite amount of time for literally any property of a program's behavior in general。

 you can't do it， it is impossible okay and you might be thinking brand and brandon like what do you mean like like well okay let me give you a concrete example and this comes out of something called the halting problem。

 raise your hand if you've heard of the halting problem。😡，Yeah， okay， the halting problem is this。😊。

You cannot write a program to tell if a program loops forever or not， okay and there's a really。

 really simple demonstration for why this ought to be impossible to determine and it comes out of asking what does this function return？

😡，Suppose so we're going do this by contradiction right suppose youve had a function halts and what this function does is it returns a bull if the function you give it halts okay on any input I guess maybe doesn't really matter coding details anyways。

😡，What is this to well okay？😡，We got to function here that if。Halts is true on itself than it loops。

 otherwise it returns unit。😡，So let me do this my casework， okay， we got case one here。

 we got case one。😡，I don't know whether or not not halts halts or not， right。

 but let's say that not halts。Alsose。Well， let if not halts halts and halts is true。

This should be true， yes。Then I should loop， so if not halts halts。That implies of loops。😡。

And then case two is。If not， halts。Loops。Well， then it means that halts should be false。

 right it's not true that it halts， so this will evaluate to false so we enter here。😡。

But if we enter here， that means that nu halts return to value。

 which means that it definitely halted。So it implies that it halt， what does this remind people of？

Well， it does remind you of the halting problem that's a tautology。

 but one thing I would go for also is if anyone's heard of the epimenidees paradox or the liars paradox okay all crres are liars is sentences false。

 it should feel a lot like that because if basically is that my point is that we're going to find that we cannot have this program halts because if we did we could construct this and then we have a logical impossibility which is that this function somehow both halts and doesn't halt or it does neither it's okay well raising exception is possible but that doesn't matter okay raising exception is not halting。

Do people understand what I'm getting at here？This is just a very simple explanation of the halting problem the point is that paradox means bad means we cannot solve it。

 we cannot write a program to do it。😡，In general， for any program， okay。

 it's not possible and then it turns out because programs can do whatever they like。

 this will taint to everything else that we would like to be able to do。 Nothing else is safe。

 So therefore Rice's theorem， if I ever want to figure out some kind of property of a program about its behavior you're shit out of luck。

 that's exactly what it says。 Okay quotes and everything All right， Rice was the ahead of his time。😡。

ok。😊，So tiny， you know， Ch make really， really small problem， program analysis is impossible。😡。

So that sucks。Lre over。Not quite so lecture is only over if you're a quitter basically all right yeah。

 only 63 sides left this only stops if you're a quitter all right and we don't raise  quitters so remember this idea I've kind of alled to which is either strengthening an implementation or weakening a specification when we want to implement a function basically that means that either we can suck it up and then put more work into our implementation or we can just lower our expectations。

😡，We are dealing with a mathematical impossibility here。

 so it's not a skill issue like we don't need to strengthen our implementation， okay。

 that's not the problem here The problem here is that our expectations are too high。😡。

So it is impossible to definitively answer yes or no for any property in a finite amount of time。

 yes that's true， a， but it's only true。If you insist on being right all the time。

This is the main contribution out of program analysis， let's be wrong， let's be wrong。😡，Sometimes。

 sometimes not all of the time， you know。So we're facing an impossible problem。

 but let's just lower our expectations。So compilers and program analysis are very different because I told you I impressed upon you earlier the importance of a compiler。

 you have to be right， you must be right， you can never be wrong because if you do doomsday。

 but program analysis it's kind of like oh yeah you tell someone oh yeah。

 you might have a vulnerability here and they look at it and they're like what do you mean no we don't and then you're like oh yeah my bad sorry and the people still use them because it's the best we got okay so a compiler can never be wrong。

 but program analysis is okay we can throw up our hands say I don't know we can also give an inaccurate answer or an incomplete answer those are all perfectly valid outcomes for program analysis but we're gonna see how well we can do given that what's there a question？

😡，Oh， I thought sorry。Okay。A fun corollary of this I like is something called the full employment theorem。

 it's like a meta theorem it's like a fun little social experiment。

 but it says there will always be jobs in either program analysis or compiler writing because we're talking about an impossible problem it means that we can always make progress for any program analysis anything that we do we can always do a little bit better if we just do a little bit more casework okay let me demonstrate this to you。

😊，No one's stopping you from running the Hts program。On a few examples， I just case val x equals 1。

 Okay， it returns sum of true。 And if it's not， it means I don't know。 Okay， or I don't care。

 Valal x equals2。 Yeah， it holdss Val x equals 3。 Yeah， holds oh， fun loop X equals loop X。

 And then I call loop。 that one doesn't halt。 I can look at it with my human eyes。

 And I say it doesn't halt at all。😡，No one's stopping you from doing this for the next like 60 years of your career okay like so full employment is always ensuresured we can always add another case to our match and that's okay all right。

 so a team of so basically the point is that a team of monkeys that typewriter could eventually make a program analysis tool that's better than whatever exists currently okay which might be unsettling to you but actually to me it's somehow motivational okay I could be that monkey okay it's me。

😊，Right。So let's try it， okay。Okay， so。We have an impossible task in front of us。

We cannot do anything about the fact that it's impossible to solve。

 but we can stop whining and we can get to work because。

Software is still eating the world and the cost of failing is pretty high。

 We have a lot of consequences for us if we fail to view something about the deluge of software that's crashing into us at breakneck pace。

 okay but program analysis， we're going to do our damnest， all right。😡，Let's get to work。 So next up。

Let's do the impossible。 Shut up and do the impossible。 Someone's like， it's impossible。

 This compiler has a bug， except for the one time I did in lecture。 Okay， no， shut up。

 do the impossible。 Alright， let's talk about a specific example called type checking， okay。😡。

You're familiar with type checking at this point and we're going to talk about it in the context of standard amount type checking always terminates。

 I'll tell you okay even if well it should have been pretty fast for you。

 but it always terminates and it always gives you correct answer if it gives you some type you can trust that it has that type and if it says it's ill type。

 you can trust something is messed up okay。😡，But let's talk about this function right here。

 this fun function that we introduced on the first day of class takes in two in S us back and in。

 What is the remarkable thing about this function you think I'm going to talk about。

 What is the cool thing about div。😡，Dive1。好的。Dve 0。Yeah， okay。Dives zero。

 What happens if we divide by  zero。 Well， oh， raise div， That's a pretty bad thing。

 But it means that SmL will just let me go ahead and run a program that says this。

 It'll just be like， yeah， okay boss， sounds good and then run it And isn't not exactly what I said we shouldn't do。

 we shouldn't have to be able to run into an error at runtime。

 if we can avoid it Okay So what if we could give div a more particular type one that meant that we could never pass in zero here so that if our program ever passes zero into div's second argument。

 we would get a type error。 we would never run the program。 Thatd be pretty cool right。

 that would cover one such use case。 Okay， let's just focus on this for now。Let's try to do it。😡。

Well， okay， so what would we do Well， okay， there are two properties that we won want to have for if I was able to give Daveb this special type。

 Okay， one property is I want to be able to as retain that type in a finite amount of time。

 What I mean by that is the type checker should not loop if I want to do this for div。

 I should not have that my type checker ever loops because。😡。

If I wait around all day for my program to compile I'm going to be sad， okay， I don't want that。

 okay， none of you want that all right， that's a bad thing。😡，Two is。This is wordy。

 but it basically just says it's correct if it says ill typed。

 it should be if and only if either there's zero or I did something else stupid that we know about like I gave it。

 something ill typed。😡，One of these two cases， we would like to see that both of these hold， okay？😡。

But actually based on what I told you earlier， it is literally impossible to have both of these things at the same time。

 you cannot have your cake and eat it too， you cannot eat your cake and have it too， okay。

 whether or not you say it the Kzyski way or not this is still not good okay？😡。

And you get that reference， okay？So looping forever or being wrong pick one。

 pick one okay cope so we're going to have to decide because due to the halting problem if I wanted to be completely correct。

 I would have to accept the fact that I would rather you know I can't have both okay or not both rather okay I cannot both be finishing a finite amount of time and be correct there we go。

😡，So what do we do about it？Turns out actually， there are things that let us do this。

 They're called dependent typed languages and they let us prevent things like this。 like， oh yeah。

 I want to make sure I never get zero into div。 I want to make sure that's a compile time error。

 The tradeoff here is that these things might loop forever at type checking type。

 I'm going to call that a type a program analysis。 Okay I'm going to separate them into a couple。

 but we're gonna to say that I type a program analysis。May loop forever。

Which is something you might be okay with， it depends on your sensibilities。

 but this is a type A program analysis dependent typed languages count， okay？😡。

So the other way we could do it is we could get the first property。

 but not the second we could have it such that we。😡，Are always correct or sometimes sorry， rather。

 we're sometimes wrong， but we always terminate。 So that's going to be what we call a type B analysis。

 sometimes wrong。😡，And I'll just to make sure everyone's on the same page。

 I'm going to put in brands here like it might move forever。But when it gives us an answer。

 it's always right。And then a type B analysis is sometimes wrong。😡，But it always terminates。

I suppose you could have the worst of both worlds and have one that both may loop forever and is sometimes wrong。

 but let's focus on this for now that's obviously not a good thing okay。😡。

Let me give you analogy for this， okay。😡，And you are in charge of security。At an airport okay。

 and you're aware that in the early 200s， someone tried to set up a shoe bomb。 In fact。

 they had plastic explosives concealed in their shoes during a flight from France to Florida。 Okay。

 they snuck it past security and then they tried to light a match on it on the plane。

 and then they got tackled and then thank God， nothing happened。 Okay。

 but you're very aware that this shoe bomber happened。😊，And you， you somehow， you know。

 for some reason you are interested in making sure that shoe bs do not happen， okay， for some reason。

 how do we do that， given that we can't scan the shoes like when they walk to the metal detector。

 you might not find out。😡，Well， you don't have a good way of telling whether or not anyone a priori has explosive to their shoes。

So how do you do this？This is why everyone needs to take off the shoes in the airport。

 okay this is exactly how type B program analyses work， okay？

The point is that if you can't know exactly whether or not who has explosives in their shoes。

 it's actually really easy to get an appxi answer to get an approximate answer。

 assume everyone has explosives in their shoes， make everyone go through the metal detector。

 So scan everyone's shoes。 now you're good。😡，And this is literally how that works。

So for this broader goal I had of typing divb so that we know whether or not divb gets zero。

 let me propose you a method for how we might do this if we don't mind being wrong。😡。

Fun contains unsafe div given a program， simply contains if that program contains the literal string div。

So we will， so we will accept programs like。Val x equals 1 plus 1。

But we will reject programs like Val Y equals 1 div1。第二。Like， yeah。

 if you don't mind being wrong sometimes， I mean， we're guaranteed to terminate， right。

 does this loop， No， it， it just checks the string。 Sure， I don't see the problem。 So type B。

 type E and also， you know， they would also complain if you did this。Of course。Well you know。

 you can't win everything。 All right， what can you do deal with it。All right。

 we have to take extreme measures when we're solving a literally unsolvable problem， okay。

 we' trying our best。So which of these is more preferred do I want to be able to loop forever when I type check my program or do I want to reject every single program that has given it turns out the answer is I want literally none of these I would prefer none of these。

😡，So。With more sophisticated techniques I might be able to reject better programs than this。

 like I could check whether or I had a literal call to div。

 but the point is not like I will never be able to get every use case。

 I will never be able to actually say yes or no on every single proper div call to zero without looping forever potentially okay yeah。

😡，Yeah， but what happens if then I give you this？😡，One div。An arbitrary function F4。Now。

 what if F loops forever？But it's not provable that loops forever。

 have you ever heard of something called the Cololat's conjecture？Yeah。

 the Colx conjecture says Coltx conjecture says that if。😡，X。X is even。Then do 3 x plus1。Else。

If it's odd， do x over two where do by do， I mean I'm doing a recursive call that will make this x equal to that Okay。

 okay， my point being that we don't know whether or not this terminates。😡，Shut up。

 if we don't know whether or not this terminates， is currently a $1 million problem open problem。

 whether or not this termmininates。😡，it's not okay it's not 1 million。

 but the point is that we don't know So what if I put it here and I did something to I added one two I made it sometimes zero right So yes。

 we can find things like。😡，This， I agree with you， you know。

 we could do that and we could not do the super thing where we reject a string of div that's a little better。

 but we can't do it the general case yeah。😡，The programs are trees which means they induce the tree structure。

 but the tree doesn't say anything about how it runs it says something about how it might run what I mean by that is like if I have。

😡，If I gave you a general program， okay， and I didn't know anything about it and I showed you this code if x is even L block。

 you have no idea of telling me whether or not we might enter this case or this case。😡，对对对。对。嗯可。

Without running the program you have no way of knowing which branch is taken but the tree tells you oh you might go here。

 you might go here， but it doesn't tell you which one same idea with the control F from Tuesday it tells you the possibilities of where you may go but you have no idea which path you're going to take if at all right so that's the problem here。

😡，Okay， so the point being basically that I don't care， I simply do not care。

 we're just going to not try to type div at one where we can reject this division by zero case。

 so I'm going to actually call that a type C analysis。😡，A type C analysis。Is where you limpimp out。

You just decide this problem is not worth solving and you decide to solve an easier problem This is what type checking is type checking least said I want to be able to catch one div zero and then we said actually that's too hard let's just not catch one div zero okay let's just do ins and that actually turns out to be tractable turns out to be solvable。

😡，lah， blah， blah， blah， so the question here is basically like does this program divide by zero。

 we decided I don't care because either I have to accept looping forever or I have to accept looping forever or I have to accept rejecting a bunch of programs that are valid。

😡，But what about different problem which is a different question which is does this program divide by a non integer turns out that one's fine we can solve that one。

 it's a type C it's a win out situation like we can solve that one at finite time and we can always be right about it but it's only because people have put decades of research into figuring out which problems can be solved by a type checker okay it happens to be that。

😡，You know us living decades and decades after assembly。

 we can be sure that our programs will not loop when they type check。

And the reason for this in kind of a conceptual way is that non- integer that's app right that's pretty broad。

 it could be zero could be one could be two blah， blah， blah。

 but zero is specific as soon as you start asking any question about a specific value in a program your hosse in general your hose because how do I know without running the program right the Colette conjecture does the Colette conjecture ever reach the number blah。

 blah， blah， we don't know we don't know we can't to know okay。😡，In general， that is。

are people following me on this？Thumbs up， thumbs down， thumbsys， give me a temperature shit。Coactly。

I try not to give away who I'm looking at， like do it。Yeah。I don't want you to feel bad about it。

 Okay， let's recap， All right， let's recap。 So I want to be able to answer specific questions about programs。

 It's the security thing。 It's it's a making sure our programs work thing， which is impossible。

 So I have to give up one of these things I need to either give up guarantee termination give up perfect accuracy or give up the problem I wanted to solve in the first place and type A。

 type B and type C analyses or will correspond to each of those things and me put here in brands solve a。

Different problem。一。😊，Specific examples， as we saw is dependent type checking can loop forever。

 so it's type A。😡，Rejecting literally all programs that have div in it is a type B because we can reject a valid program。

😡，And then regular type checking is type C， give up and then don't care about。

 we don't care about the dividing by zero， okay？😡，And it turns out now so I've talked to you a little bit about the theory of program analysis we're going to talk about in practice because it turns out that people are not super happy when you put things into the build processes and their CI and they're like programs that run on their pull requests when they loop forever people generally do not like that so type A is right out we cannot we cannot have type A in practice usually okay we do not want to loop forever so generally we're interested in either sometimes accepting the probability of being wrong or just solving a different problem an easier problem these are the ones we're going to focus on for the rest of the lecture。

Okay， and I already saw this thing about how like decades work by type theor， bh， bh，lah。😊，嗯。😊。

But for some things so type checking still has this opportunity to be type C。

 but for some problems like oh are you vulnerable to SQL injection。

 is this code reachable by a caller does this program exhibit unsafe behavior。

 we have no guarantees we don't know okay so we have to be in type B for these ones and these are the interesting ones。

😡，So let's try being wrong， okay some of you， some of us don't need to try， okay I don't need to try。

 but let's be wrong， all right。😡，Data flow analysis， this one is conceptually difficult。

 I want you to get the idea as usual and unless you take compilers。

 you will not need to actually know the precise coding details of how it works okay。😡。

Here's how it goes。This is a very， very classic technique。

 this is used in every single compiler every single program analysis it's our bread and butter for how we get factsax about a program Data analysis is a type B analysis it will always always terminate if you set it up right but sometimes it will like over approximate or under approximate or make assumptions that will not always be true because it needs to make assumptions it doesn't know okay。

😡，But before I can define it to you， I got to give you an analogy。😡，Okay and the analogy is this。So。

The analogy is not。Vll x equals string high div 0， alright。I have a question。

 I have a question about programs and I have a certain number of answers， I in fact I have n answers。

 suppose I have finite many of them。😡，And suppose they're all different okay I'm being very。

 very abstract here， but you know like your question might be oh does this program type trick and answers might be yes and no or it might be yes and it might be no because of a type error at line two and it might be no because of a type error at line three so on and so forth my point being that there are a finite number of answers。

Now， the problem with program analysis is that in general。

 these questions if they're about program behavior。😡。

A program can go to literally any state it likes if what what a program does at runtime is completely unbounded。

 so for instance， if I'm asking a question like how much memory has this program taken up at this point in time。

 we might start here and then we go here。😡，And then we go here。And then we go here。 and then we。

 and let me just jump all around and we might do that infinitely long。

 We might keep doing that because our program might not terminate。 Okay。

 memory consumption is a good example。😡，So jumping all around like this。

 we're guaranteed that we might loop forever。But what if we reascher the problem。

 what if I enforce a guarantee the same way that we enforce a guarantee on the associated function to reduce。

 we enforce a guarantee so that we can get nice things out of it。

 what if every single step of my program， every step of my analysis， I always have to go right。😡。

I always， if I put my answers， there's a way of putting my answers on a number line such I always go right no matter what or I say where I am。

😡，Well。Do you believe me？Does it make sense to say？If I always go right or stay where I am。

I can guarantee terminate。I can guarantee termination because as soon as I stop being able to move。

 I know I'm done， that's my answer， but if I always go right， eventually I'll hit the end。😡。

Does this abstractly make sense for everyone？Okay， so lets let's think about it。

 This is the idea of what's called a monotonic function。😡，Oh oops， is yeah， this is what I just said。

This is what's called a monotonic function， a monotonic function always increases by some metric。

 and I'm not going to define that for you because I don't care， okay。

 but the point is that it always increases quotation marks and always has a maximal upper limit。

 a point where it can no longer grow。😡，For data flow analysis。

 what we're going to do is were going to spam that function。

 we're going to spam it and spam it and spam it and keep doing it until eventually it stops and then we know we have our answer yeah。

😡，I'm abstracting over every possible thing you could have asked。

 but like let's suppose the question is。How many。Calls。To F。Okay， we can have zero calls。

We can have one call。And we might， you know， we can have arbitrarily many calls。

 but let's say we cap it out at N， we stop caring after N。😡。

If I can guarantee that my information about this always goes right。

 then I can guarantee that I always terminate if I count the number of calls I do really。

 which essentially amounts to simulating the program， but。😡，You know。

 we we'll cut ourselves off that for a certain amount of time。

So the point is that there are a bunch of questions that this might take the form of and they might have a bunch of different answers。

 I only care that there are answers and there's finitely many of them Okay I mean very very general here I'll show you a specific example soon。

嗯 yeah。我。But it doesn't necessarily need to be bullying， you can have associated data。

 you just need to be monotonic in some sense。Yeah， so this can make her answers wrong。

 I'm going to show you an example， yeah。The program is before the analysis。

 the analysis is running on the program when you pre specifyify the program， yeah。

 yeah I wouldn't worry too much about that。Okay let's look at a specific example。

 so remember control photographs I've got one for you， we start here， we go here。

 we might loop here and then eventually we return apps okay and what we want to know is we're going to do a very classic data flow analysis on this called constant propagation or constant analysis I want to figure out which of these variables is a constant at the end of this function okay。

😡，Here's how we do it we just march through the CFG and we ascertain which of the program points。

 which of the between each instruction what thing is constant okay and I know that you can look at it with your eyes and then tell what the answer is but let's do it programmatically right now so that I can convince you that it's possible to do okay。

😡，So let's do it this way。啊。Im to call the Lupinberry。That's not how I think of it。

Tony Hore actually invented the。The idea like， or like you imagine？Tony Hore， yeah， Tony Hor， yeah。

 Yeah， Sir， Sir， Charles William Tony Hor to you， he's a Sir， Yeah， like the Williams part is wrong。

 The Charles part is right， Okay， Sir to you。Okay， so。All right。

 we're going to do the constant analysis。When you start at the beginning of the program。

 we have no idea what is constant and what is not。 But as soon as I see x gets one， well。

 let me update my set and this is a set。 Okay I'm going to say that now my set is I know that X is constant at one。

😡，And I see Y at  two， so I say， oh， now I know that x is constant at one and y is constant at two。

 this true makes sense to people like this is my advanced knowledge as I go through the program。😡。

One well when I land here， I'm just going to inherit my previous thing right。

 so I that x I still know that x is constant at1 and y is constant at  two。😡，But what happens here。

 oh well x is constant at one and I add two to it， so now it should be constant at three yeah。

This won't change later at all。But hold on I can't go here yet I'm not done because I've got a loop here I might go back to the same block so what do I need to do well what amounts to this is that I need to check all of my entry points I need to consolidate this information。

😡，These sets here are kind of special。😡，We call them outsets。

 these are kind of like the reported state of the world at the time that you leave this basic block and we have two contradictory things happening here。

😡，The state of the world when I go from here to here is that I know that x is constant at 3。

 the state of the world when I go from here to here is that x is constant at one。

Does that sound to you like X' constant？I basically I have two points I can enter with where now x could be two different values。

 so it's no longer valid for me to say that x x is 1 or x is 3 here's what I'm going to invent I'm going to invent a symbol。

😡，It's going to look like a team。Scosly called top， but it means。Not constant， okay？Basically。

 what it means is that I need to follow this loop and reenter here， but with the updated information。

 so with this information and this information I'm going to conclude when I enter here actually。😡。

X is this weird， funny symbol。X is not constant because I could enter at one or three。

 which means that definitionally it's not constant。

 there's more than one definition reaching me here okay and then I do the march again if I feed a non constant into plus two I I get another noncon right？

😡，So this is now non concept。And now I iterate that process again like do I visit here and here。

 well noncon and one， oh that's not constant right so I get here again like it's okay this is perfectly consistent with both of these again my in state here is consistent with both of the outs states that reach me。

😡，So I go through again and I'm done like I converge， I stopped being able to go up。And then I exit。

I skipped a lot of coding details there， like implementing this is quite more subtle。

But this is the idea。 It's simply that if you you don't， you don't know this， you don't see this。

 but what this is， is this is a monotonic function。

 I'm saying that like we can only get certain amounts of information。 And as we get more information。

 we eventually stop when I get an information about it being constant。 That's all well and good。

 That's cool。 I say， hey， it's constant。😊，But then when I get another bit of information。

 now it's not constant。 Now I'm done。 Not constant is the highest I can go。

 I can either know nothing。😡，For a given variable X， I can either know nothing。😡。

I can that I can know that it's constant at some number n。Or I can know it's not constant。

 but I always go up or write it's a monotonic function。

 but I happen to be doing it for every single variable。

 which is fine okay do people kind of spiritually get what I'm saying here？😡。

thumbumbs up thumbs up give me a temperature check。Confuse thumbs up， Confuse thumbs up。Okay， okay。

 just want to make sure。This is a this is a silly example。 Okay。

 you guys looked at this immediately and you were like， yeah， we loop forever X could get。😡。

Added to two by any number of times right but the really cool thing is that this method I'm describing to you data analysis works on any control P when these graphs get big enough that we can't possibly run this on ourselves look at it with our own eyes it's still going to give us the right answer it's going to give us an approximation though。

😡，Like so basically what I'm saying here is that the end result this analysis is we conclude oh X is not constant y is constant。

 so when we return X we know we can't for compilers this is important we know we can't optimize this away right if x were to be constant we would be able to optimize it and say any call to this function would always give back whatever X was so if this was RE y different story we'd be able to optimize but because it's here we know we can't okay but do people see a problem with that like will this always do the right thing。

😡，Or decision to optimize or not， yeah。That's true。 Yeah。

 I was thinking more of the opposite and actually， yeah， yeah yeah。So if immediately after this。

 I put x gets x plus  two and then x gets x minus 2， we'll be fine。Yeah。Like here。

Then we can do a little bit more advanced analysis， but like for this program。

 basically what I'm trying to say is that our inclination that this is not constant was founded only upon the idea that。

 oh， we can go here。😡，But this is a control graph It offers a suggestion， a possibility。

 a probability space of path we might take this program might have a precondition on it where I literally never enter this loop。

 I always go here and then I immediately exit in which case yes。

 it would be constant at two or one rather three actually sorry right if I always go this way。

 I would always have an output of three right？😡，But I don't know。

 I don't know without running the program by looking at the control flow graph， I'm approximating。

 I'm saying okay， assuming that you do exercise every single control flow path。

 then yes we can conclude that X is noncon but it's an assumption okay you know what they say about assumptions it makes your program analysis is sad so。

😡，We're not going to be able to do this in general。😡，People get what I'm saying。Okay。

 so that's why this is strongly terminating， but sometimes it lies yeah。😡，Yeah。

 there were two bits of information， x is one， x is three。

 and they were yelling at us and they were they screamed and then we were like， okay。

 I can't hear you， not constant。X in both contexts words is just a different concept。

 that's what mattered， and then here when we enter， it's not constant。😡。

It's still true that on the outset of this block， x is1 and on the outset of this block。

 we eventually be updated that too。😡，Yeah。The point is just simply that like similarly to polymorphism。

 actually， if I enforce too many constraints on x， if I say x plus one。

 and then I say x string can cat high， I get bad Sam thing here。

 I can only accept two bits of information， one to tell me if it's constant。

 one to tell me if it's wrong or two constant， really okay。Yeah， we'll move on from this。

 I just wanted to give you this a taste of this compilers really drills us into you。And yes。

 this is a prettyified version of everything I just did。😊，Okay。

But this works for any control flow and the reason why it works is that we're really moving up something called the lattice okay。

 and you only know what the lattice is， but it induces this pretty picture。

 but basically it means that remember how I was annotating between every instruction with these sets。

 it turns out that we can only ever go up。😡，If I start here。

 I can only ever go to this this transitly I can go up to at once， for instance。

 but I only ever can go up and that means that eventually either I reach here or I converge somewhere below okay。

😡，So that's why we always terminate it's because of this theory of lattices， okay which is a really。

 really funny way to call it and it's like if you want to sound smart you can be like， oh yes。

 this lattice has finite height， this is a lattice theory problem， but you whatever I don't care。

Okay， and as also this is really pretty pictures， that's pretty much all I wanted to show you here is that the picture looks pretty。

😊，All right。Cool， okay。Okay， and this is kind of just justification for what I told you earlier。

 the point is just that like this is an information thing why can I only go up it's because if I know nothing about a variable and I learn that it's constant I can't go back to knowing nothing about the variable if I have a variable and I know it's not constant I can't go back to knowing that it's constant so we're just structuring our information in a way where we can never go back。

😡，And because we can never go back， then we ensure that we always converge this is the theory of dataflow。

 And honestly in program analysis when I took it， we spent four weeks proving that it like terminated on various things and I was not here for it。

 Oh yeah here's a funny story。 I literally got R in program analysis at CMU。

 so maybe I should have opened up this lecture with that before I started talking about it because it was a senior year and I was burned out and I like didn't care anymore and we spent four weeks proving that this terminated and I was like I'm now but that's a fun thing I always get to say to my coworker like yeah what's up I'm a program analysis engineer I failed program analysis at CMU like yeah。

 I told my CEO that on the first day。😊，😀。😊，Cool， okay， right， A said everything here， basically。

 Okay， and then there's a few like analyses that are pretty cool that all fit in this framework。

 Okay， data analysis is a framework。 It doesn't need to solve just this question。

 There's other questions we might solve like available expressions。

 Is there a definition of this expression already。 That means like I can piggyback and use that。

 Do I need to redefine this expression Like I can see， oh， I already did x plus Y Like Valal X。😊，包位啊。

Vals equals x plus y exists so I don't need to recompute x plus y or we might do liveness analysis like I might look forward and say does this variable have a use in the future and if not then I can use my ID and warn you hey。

 you don't use this variable or I might do something called taint tracking and this is a really interesting one Taint tracking is do does data from like a really sensitive call like reading from input go to eV。

😡，You' all take1 and 12， right， have you ever tried doing eval of input， left print， right pre？😡。

Has the 112 T ever told you that's terrible， never do that again？Okay， it's it's incredibly unafe。

 never do that again The point is that ta tracking let's see you find stuff like that Okay I'm going to hurry along here because I don't actually care about the coding details here yeah。

😊，いやいや。No， no， no， you can do this in imperative language too and it becomes significantly harder in a functional language or sorry in a language。

Okay， why the hell did I tell you about the analysis， Well， it's kind of because。😡。

Program analysis and people we have one trick of our sleeves really， which is dataflow。 Okay。

 so I kind of have to tell you data flow。 even though really it has nothing to do with functional programming。

 Okay， the implementation I've done it， it's like it's okay， it's not worse for share。

 but like it is nothing special about doing it in SmL but dataflow analysis is interesting because remember。

 controlflows or at the level of abstract assembly。

 That means I got to break apart all my nice language constructs。 I gotta break apart every for loop。

 every x plus y plus Z and de sugargu it to its constituent commands。

 So I think it's a more imperative approach to program analysis because it's closer to the assembly。

 It's closer to what the program is really doing。😊，What if I wanted to say at the level of the AST。

 what if I wanted to say where all the semantics were。

 we're going to see actually this is a really nice way to do things。😡，Enter somegra。

So here's the idea I want to basically tell you why we should stay at the ASC level because why does it make sense to do program analysis on ASCs ASCs are literally like farther left in the pipeline from the assembly which is God's own truth right but the point is that actually there's a lot of reasons that are not strictly technical for why this is a good idea and before I do that I have to tell you about software engineering and security。

These things do not go together okay in general， software engineers are paid write code and they're judged on the quality of the code and they are judged on how fast they write it。

 They are not necessarily judged on whether or not they write secure code unless it comes back to the butt to bite them So in the general case。

 people don't care about security which is a great thing if any of you are aspiring to do security prepared to be ignored by developers for the rest of your life but so generally security takes a backseat Okay why am I talking about this Well for a compiler being wrong is a really fucking bad scenario It's really hellish because。

😡，We're screwed。Her program analysis its Tuesday okay， being wrong is like。

 that's all what do you expect， an unsolvable problem and then you just say that to your customers isn' like。

 okay， fine。Like to the developers who are getting security notifications like they write code and then their GitHub yells at them like。

 oh you have the vulnerability here， you'd better be right a good amount of the time because otherwise if you're wrong most of the time。

Whatever company or whatever places using your tool is going to rip you out。

 and they're going to have just。Not scan their code I guess or use a different one right so you can't be wrong too often I'm saying that like you can be wrong。

 but like in practice if you want to write a good program analysis tool。

 you can't be wrong all the time。😡，So why am I mentioning this Okay， my point is just that it's very。

 very easy to save labor if we stay at the language level， this is why I like what I do。

 even though those program analysis because I'm have languages I love ASCs。

 I love reccursive functions on trees。😡，But it's really。

 really nice remember that we have a compiler that can turn from token list to an ASC a tree。

 we can turn from a token list to a tree。If I want to write a program analysis tool for Python。

 I got to do this for Python code， I got to turn tokens into a Python AST and then I got to turn tokens into a C AST if I have a program analysis tool for C。

 there's an immense amount duplicated work here I can do this for C。

 I can do it for Python and all the while I have different ASTs for C I have different ASTs for Python I redo my analysis all the time。

😡，So why am I duplicating my efforts here？Almost yeah。This is what the pipeline looks like。

This makes me sad。 Do you see how many purple and blue nodes there are here， That's bad。

 Let's do better。What if we had so all these to be clear， like if I did this in like SML。

 all these ASCs would be different types， we'd have like data type and Java underscore ASC。

 we'd have data type Python underscore ASC and it just becomes a massive pain in the as okay like when Java upgrades to Java 21。

 you're gonna to have to change that when Python adds match statements again you're gonna have to do that like come on。

So what we can do。Well we before I say that most programming languages so okay I know I I love complaining about programming languages too you。

 but it's mostly for communicate that most programming languages look pretty similar。

 a lot of them have four loops， a lot of them have wire loops。

 a lot of them most of them have variable definitions。

 most of them have functions okay so why should I necessarily represent them differently。😡。

They have different idiosyncrasies right like Java does class inheritance and Python doeslah blah。

lah， blah but also we're solving an unsolvable problem so what if we just took all those like many skill differences between languages and we just like like shoved it under the rug and we just were like unsolvable problem it's fine。

😊，For program analysis tools is being wrong this Tuesday。So what SGriP does。

 if SGript just pares every single language to the same type， it represents every single language。

 programming language， every program the same way。And turns out this is actually really really cool and it's why we support over 24 languages because it takes you like three days to add a new language it's like not a big deal and this is why here's the pipeline I take Java code or Python code or C code。

 I turn it to this type that I call the generic AST and then moreover I don't have to do parsing multiple or I don't have to do analysis multiple times I just run an analysis on the AST。

😊，This is actually a really cool idea。😊，No， I't know if anyone else has this。I work there， okay。

So you have to be pragmatic when you're solving an impossible problem， let's move on， okay。😡。

So here's here's some Python forya， thank you here's some Python forya。

 who reads Python who do you have 112 in the room， there's 12 in the room， right？This is 112。

 who's 112 in the room， You are， Okay， what's wrong， what's wrong， what's wrong， what's wrong， is。

 Criry about it， cry about it， cry about， okay， mutability， mutability， mutability， right。😡。

What happens here is that you might think this is going to be default nailil every single time。

 but it's not but it's also not called nailil here's what happens when you call a pen two of two。

 you get the list of two。😡，Cool， sounds good， but you call it pen two of two of the the second time you get two coa 2 Y。

 because this guy is instantiateated once the function is。

 and then it's mutable So every time you append you change this guy and in the background it' kept。

This is a very common thing that people might do。 Okay， like this is， this is stupid。

 But like when you look at it with your human eyes， you you know， bless your heart。

 like you can see this and be like， that's garbage。😡，We're talking about Python here。

 do you expect something better Bless his Go Van Ross bless his horror I love you Guto okay。

The point being that with your human eyes， you know this is wrong。

 but who's got time remember all the tens of millions of software developers out there producing garbage garbage code。

 do you have time to go look at all the code no that's what I thought okay。

 you have better things to do like like read memes on on fun on funny me or whatever okay so my point is that this is bad。

😡，Let's see if we can catch it。In an automated way。

 let's see if we can fix such bugs and oh the other thing I want to say about it is that we don't need to go to assembly to know that this is a problem In fact we only see this because we're above assembly right at the language level this is a bug and most bugs are at the language level at the level of your source text why because developers write source code I don't often write assembly okay。

😡，I did for 213 for a bit。Okay so the point is just that let's not go further down let's stay at the AST Okay all right so probe analysis can do a lot of things I gave you a few examples earlier。

 one such thing is security。 I want to find if there's a vulnerability in my code Another thing is stuff like what I just saw best practices I want to make sure you don't do dumb things like do dumb Python things like default inm mutable arguments okay。

😡，But it all just comes down to finding things that you're interested in。

 which I will call a finding， okay。😡，U， what we're going to do with SDriP is we're going to try and customize and I'm showing you this because you can understand what I'm doing basically。

 okay， you are all capable of understanding what I do at work。😡。

USGP basically will be customized to all of these， some things find security vulnerabilities。

 some things find siaries with some rep you can find whatever you like because you're going to be able to specify it to SGP。

😡，How do we do this so has anyone use GrP？Has anyone use control F？😡，Congrats you've used grab。

 all right， so G is basically just control F okay， and the point is just that if I wanted to define all instances of a call to a function print。

😡，If I control F print in my VS code extension ID， what do you think is going to happen？

It's going to highlight every single call the print， every single print， including French all or。

Printing。So on and so forth， Okay， or if I had， if I， you know， if for some reason I had。

 if for some reason I had a variable named printing underscore square press， Okay， it would like。

 it would like find that。 Okay， the point is。系啊。whatever point no。

 that's still that's still fragile though， because what if there's a new line。

 what if there's anything else right， so the point is we're going to be inundated with results。

 we're going to find every literal instance of this string。😡。

These days is literally just looking at sequences of characters that's super dumb， that's super。

 super dumb， let's doe better。😡，How can we do better well Subgri can understand the semantics of the program we're going to look at the AST remember that midterm one problem I gave you or midterm 2 one problem I gave you about tree matchinging well Sgriip doesn't do text search where it does is tree search I'm going to try and give in an abstract syn tree like Valdeck。

😡，And you know， maybe we're declaring x and we're declaring x to be。1 minus2 okay。

I want to find a subree of this that matches my pattern okay and here's how we're going to it。

 we're going to have two ASCs， a pattern ASc which means the thing we want to match and the target AST which is the things we want to produce matches in and I'm going to give you very concrete pretty pictures。

😡，And this is actually like， so basically you would give some rep this， okay。

 for the next few slides， this is what you'd give to S rep。😡。

This is what the program that you're analyzing is， and these are the ASCs as I have purtified them。

 okay。If I wanted to define， say print。😡，Know that that there's this let's print here。

 if I wanted to match this print on the ASc level， there's only one choice， right this guy。😡。

Any subt of the right tree that matches this， but not this， why because it's not the same color。

 it's not the same， this is a string that's a print call， different things entirely。😡。

So what will happen is that it'll like be like yeah cool and it'll highlighted I very briefly toyed with the idea of adding SML to Sr it would take me like three days it wouldn't be hard for the purpose of this demo and then I realized that I do not have three days so I didn't but one fun thing is that Sre actually works with OMl which is basically the same thing so if I had this on the right hand side。

😊。

![](img/91940326e45c8c5d137c628535e93796_3.png)

Basically， I'm showing you that this is the thing that we're specifying the seminar up we want to find。

So click play。It'll highlight this， but not this okay this is just me justifying to you that I'm not lying about what I'm showing you on the slides。

 okay。

![](img/91940326e45c8c5d137c628535e93796_5.png)

It's better than a redx， yes， it would be actually I'll show you a really cool example here。 Okay。

 I don't care about this。 Yes， okay， but the algorithm is very， very simple。

 it's very understandable right， you just go and find the node that matches。

 I think that's a really cool thing Okay it's it's a kind of an idea in functional programming like simple like beautiful fundamentals leads to good practice。

 This is the fundamentals okay。😊，what if I want you to find calls to ref。

 remember the thing where I told you， one of the good things about an MLL in SML is that you're very explicit about where you use mutability everywhere you say RA。

 that is a call to a mutable thing， but we don't want to control F for the same reasons I gave you earlier。

😡，This is what's called a meta variableable， it means match literally anything here。

 any kind of like ASC node， any expression okay so the tree looks like this it's a function call from ref to this meta variable which is like kind of grayed out because I don't know what it wants to match yet。

😡，Where's the match here？Is there a match here？There's going to be a match here because why this is the same as that。

 this is the same as that， even though I made the colors different for some reason。

 and then this can match the meta variable because the meta variable matches anything okay。😊。

The meta variable is a standard， it's in the same way you say val f equals e right it matches to whatever。

 and I can show this you。😊。

![](img/91940326e45c8c5d137c628535e93796_7.png)

Also。Oh， maybe I should just not do that， okay， whatever。Right。

 but I'm still not going to and if you see let that's thou like congrats， now you know， okay Caml。

 you're welcome， okay， but if I did this it wouldn't happen if I did this it wouldn't happen。

It's open source， it's all open source， you can go see the code that I write actually please don't look at the code I write。

😊，No， I wouldn't feel right about talking about this if it wasn't。

 I wouldn't feel right about working at Send rep if it wasn't open source like I that's just personally me。

 I I'm very grateful that in my lifetime， I've been able to work on。Majority open source projects。

 I like the name is yes， this is open source。 You can just run this and we find the finding and it's doing it via tree matching。

 which is a fundamental thing that you learned。 right What if I wanted to suit it up a bit okay。😊。



![](img/91940326e45c8c5d137c628535e93796_9.png)

What if I want to use a meta variable two times if I do this in SML， okay？😡。

I probably committed a stupid here right because like this is always going to be true。

 So what I'm trying to say is that if I have the equals operator applied to two of the same thing。

Probably something weird is happening here meta variabless can unify when you use them multiple times。

 meaning that whatever they match has to match each other to So if I produce a match here right equals matches here and these meta variables match these。

😡，And because these subre are the same， they also match， yeah。

But the great thing about program analysis is that you can do this in a if this worth C。

 we would still be able to do this and we have options that let you configure it because we can be wrong。

 we're allowed to be wrong。If you do this， it's so kind of a code smell， like like if I do。

What's on this board let's let's run oh， no， it's not something I like in an imperative language。

 any language， if I wanted to do like F。😡，Equals equals F。 Like regardless of if it's imperative。

 like something is weird about this code。 Okay， so you can configure whether or not you want to find that kind of thing。

 But yeah， that's why I love program analysis。 You can just be wrong。

 I can just write code and be like， yeah， like I know this isn't always right。 But like in practice。

 you should be right。 And and then my managers like。Yeah， okay， Fer。Suse， it's Sue。It's Thursday。

But in this case， if I said F2 equals G2。😡，I didn't update this either。

 I'm sorry this would not produce a match because if this were G， these would be different trees。

 thumbs up， thumbs down thumb sideways。F following me here， we're just doing tree matching， okay。

 cool。All right。Oh， I don't know if I happeneds。Yes。

 it's pretty much just pattern matching with extra steps again。

 clean principles lead to good code right the guy who thought of this。

 one of the guys on my team Yoan Pa Pavilo， he is a he's a Ph team program analysis and he's like。😊。

Super good engineer， but here this is his invention and it's like literally the best thing of it。

Yeah， okay， but okay， I' given you some pretty abstract examples。 Let me show you something concrete。

 Remember that part where I was like。June 9。Do this， usually this is a coat smell， why？Why， yeah。

Linear and L and if you're doing this recursively， you're probably you know cruising for a cruising for a linear quadrata cost。

 okay， so we don't generally like this。😡，Hey， wait， it's very。

 very easy to raise a separate pattern for this。 These are two benefit variables。

 I'm saying any expression appended to a list containing any expression。

And the tree is just looking like this right Does everyone understand why this tree should be this so aend here my left argument is E1。

 my right argument is a singleton list of E2 and then if I had rev I the tree is too big to represent but like the point is that this would be the subree here。

😊，And we could go ahead and match it。And I'm going to show you more Ocal， very， very exciting。嗯。



![](img/91940326e45c8c5d137c628535e93796_11.png)

OhO， okay， and what's going to go here。This is revv and Ocal， squinch your eyes。

 it'll look like SNLTU okay and if anyone has a fundamental like complaint with Ocal。

 I don't know what to say okay。But okay， dollar sign e1 append lists of dollar sign E2。

And it matches。But it wouldn't happen if it was like。Sa that there's like an L2 out here。

That wouldn't happen because it' it's not a。It's not a list， it's not a singleton list， right？



![](img/91940326e45c8c5d137c628535e93796_13.png)

So we can find very cool stylistic things like and you know I know that I'm just talking about this and I like to talk about because this's what I do for work and it's super cool but this really is a labor saving device because this is so easy to write it's literally a one liner yeah。

This app xs now。 Oh， we would still be up Yeah， because we D sugar those when we go to the A。 Yeah。

 yeah， yeah， yeah， good question。And this because of this thing that all programs parse to the same type。

 we only need one matchinging function， we take an expression on the left an expression on the right and we give back what's called five things。

 but it can happen for Java for C for OK for Python。

 it doesn't matter because they're all the same type okay I get to I don't have to duplicate my analysis per language which is a really really cool thing so remember that default argument Python thing。

😊。

![](img/91940326e45c8c5d137c628535e93796_15.png)

So this one is good， this one's bad， this one is also bad。

This is like some representative thes I don't need to explain it to you。

 you're not going to use some rep but I just want to talk about this school we're going to find these because we have a default instantiation to this list yeah。

😊，That's all it is that's all it is and the real cool thing is that it looks like code here you don't need to have that's kind of the other thing which is like program analysis we're playing a game where like I talk to you a lot about ASCs and control flow graphs and the average developer guess how much they know about ASCs and control flow graphs the answer is frighteningly little okay。

😡，So the fact that you don't have to know anything about ASCs to write this is pretty cool like the tree matching is happening。

 but it's happening behind the scenes like you used to write oh magic magic dollar sign D equals no and then it's like okay。

😊，Sounds good， boss， yeah。This one would only parse as Python。

 but I could definitely do something like what's some language like I vague know Ti。F。Yes。

Let's just say int the。Inch main inch X。C， and if I remember my syntax， yeah， here we go。

What I've done is I've converted this into a rule that just finds C functions that have a argument that's an endt。

So if people read C， I just like context switch to see here。嗯。Yeah， yeah。

 you can write certain things like。😊，Dta sign x plus dollar sign y。

 and this will par in like C or Python。

![](img/91940326e45c8c5d137c628535e93796_17.png)

Right this is usually rules are one language， it doesn't really matter， yeah okay。



![](img/91940326e45c8c5d137c628535e93796_19.png)

嗯。Oh yeah the next thing I want to show you is this taint tracking thing The thing I was talking about about eval of input Yeah。

 it's pretty bad don't do that， by the way， but if you were to do that。

 program analysis tools can occasionally have your back because we can write this this is a taint mode rule it's just saying that like input is bad and if input goes to eval that produces a bad and here。

😊，EBall goes to input or input goes to eBa， yeah。Raceians， races are heard。

Very hard because things you have to specify what you're looking for。

 How do you specify like what a race condition should look like。You know， it's very hard。

 it's very hard to diagnose these things。If you're writing concurrent code and you have a race condition。

 usually means that you're writing mutable concurrent code。

 and remember what I said about how if any of you write mutable concurrent code and then come back to complain at me five years later。

 I'm going to like I'm going to send you back an angry face and then I'm going to no kind of mind。

I was going to make a joke， but it would not be good for me to say that yeah。

We do the same control flow graphing。Yeah， there's actually both the AST analysis and then we also desuggu it to an abstract assembly in IL。

Something like that。 Well， not quite。 Like if you did something in between。

 it would also know about that like pass X equals 3 or actually， no， not x equals。 Actually。

 that's a cool example。 Let me show you this here wait， what happened。 Oh。

 it's cause I shadowed the name。 Sorry， my。😊，Okay， y equals  three， we still get it x equals  two。

 what about this？😊，We no longer get it because x is now no longer input right。

 we killed the definition that was passed into me。yeah， I don't know。Constant propagation。

I just want to show this， I'm just going to keep showing you because I just want to put a lot of time work while I've work into this P of two of two。

 if x equals  two， then this is going to be finding if I say x equals  two and then y equals x。

 p of y is also two， it understands that if I say x is1 is y is x plus1， then p of y is still two。

 otherwise p of1 is not two so。😊，Where？Well the food of one oh probably this would not work。

 I haven't imagine yeah， yeah， yeah。You can run into weird things but like names。

 like names are kind of hard like it's kind of hard to like look at X in two different places in a program and tell if they're the same X。

 but we do it by dream， we try， we try。嗯。But it means that basically like like this this kind of example I just showed you is semantics aware right your analysis should be aware of the flow of code when you say x equals one and y equals x plus  one。

 yeah， it's two。That's what it does。And I'm glossing over this。

 But this is a lot of concentrated work by like a team of like eight people for like two years。 Okay。

 so like。I love you， I， you're doing good， all right。



![](img/91940326e45c8c5d137c628535e93796_21.png)

Okay。嗯。Yeah， okay， wow。Bells and whistles and analyses and looping forever。

 and we are almost at the end。 and I didn't think that I would actually make it to the end。

 but I guess I sp there's some things since I fell like it。What is the point of this lecture。

 why did I give this？😡。

![](img/91940326e45c8c5d137c628535e93796_23.png)

It's not because it's an ad because like。And I know that I'm suspicious of this kind of thing， too。

 but。What I started out I came in hot with this idea this like this like quest right we are solving an unsolvable problem there I truly doly like believe in this idea like there is a large mountain of code that's slamming into us I like rightneck pace and we got to do something about it because go read that book I linked like it' it's a really good book actually。

😡，It is terrifying， it's terrifying how much code is being written and especially by how much code is being written without any care or consideration。

😡，One thing that people always like kind of， I think to myself is like， you know。

 functional programming， I feel very strongly about functional programming。

 shouldn't my goal be to go out and make everyone else do functional programming。I'm a realist。

 I'm not going to do that okay， like I can't make people do that like there's there's applications where functional programming is used theres applications where it's useful。

 I'm perfectly fine with that。But I like to think about it in the sense of like making an impact。

 which is like what I care about like the three things I care about and this is going to develop into a philosophy thing。

 but like I care about three things， I care about solving interesting problems。

 I care about doing it via principal means for me that means functional programming and I care about making a real impact。

😡，And this is something I like struggled with a lot like my senior year when I was thinking。

 do I want to go to do a PhD or not， and I figured out it wasn't for me。

 I didn't enjoy doing the research。And I came I've been thinking about this for a while and I think like to make a real impact and I think this is something that all of you should be thinking about because you're coming out here with this education。

 you're coming out of here like with hopefully your degrees from CMU and you're going to go out and do really really cool things and and only when I got out of CMU did I realize like actually when people tell you you have the potential to do b you can do whatever like yeah yeah only once I got out into the world and was like oh wait hold on I'm like mildly competent I didn't expect that right and you're gonna be hopefully better than mildly competent So when thinking about impact basically there's there's two ways I want to think about it right there's two ways I like to think about it which is。

In terms of numerators and denominators。In terms of like N over D， right。

Now to make this number bigger， to make the impact you have bigger right you could look at it as I want to be a very big numerator。

 I want to be Jeffrey Hinton I want to be you know I want to be this like big person that does everything。

 I want to be pot and low okay there's a way you can you can perceive that and you can look at it that way。

😡，But there's another way you can make a big impact。

 there's another way you can make a real difference。And that's not by making the numerator bigger。

 but hey， math fact。Making the denominator smaller。When I say make the denominator smaller。

 I mean this kind of idea of doing widely ranging things， do things with breadth， affect everyone。😡。

When I'm going here to find a meaningful problem， one of the most meaningful problems I think I could pick in the world that fits me perfectly is program analysis because I get to affect every piece of software ever written。

 every piece of software that's currently being written all of the software that people are writing that is terrible and horrible I don't have to convince them to use functional programming because I still feel good about the fact that at the end of the day。

 well I'm doing this program analysis stuff。😡，Is in my favorite language oh Caml and it's done functionally and it's principled and it's all the better for it。

😡，I guess I just wanted to bring this back to the fact that like for me。

 I think there's nothing cooler in the world than program analysis。

 I think it's the perfect application and I think it has real world impact and I think that all of you can have a real world impact too just like find the problem that interests you and find a way to。

Do one of these two things， either of this fine and it's okay not to care about impacts， but。

I think that we're tackling a really important problem and our model。

 our mission is to profoundly improve software security。

 and I'm really glad that like not only do I have the chance to come here and teach。

 but I've been able to do that at my work。That's it。一叫。

