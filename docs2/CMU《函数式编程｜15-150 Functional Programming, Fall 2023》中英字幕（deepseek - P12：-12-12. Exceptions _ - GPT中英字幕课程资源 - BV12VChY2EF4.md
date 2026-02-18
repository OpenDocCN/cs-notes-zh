# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P12：-12-12. Exceptions _ - GPT中英字幕课程资源 - BV12VChY2EF4

Hello functional programmers the next thing I wanted to say was usually I play a song that has something to do vaguely with the title of the title of the presentation that was somewhere only we know and that was because and that one didn't because it was an exception to that rule so anyways the other thing I have to tell you is that we have these feedback forms that people put on Piazza in particular these midsster feedback forms are for the course as a whole and the TAs。

😊。

![](img/55e9d026d4209566a1c0b5fe115b4b2a_1.png)

You were given five minutes in the lab to fill this out explicitly and not all of you did， in fact。

 not even half of you did So please do fill this out if you're upset of me for my polls okay don't take it out on the Ts because this is the only time that Ts get feedback so they really want to hear from you and they're really excited to so please please please take the two minutes or however long it is to fill this out because it will not take very much of your time and it will make the day of the Ts who have been working on this for almost six weeks at this point or it won't make their day depending on what you say about them but don't say anything things cool。

😊，Okay， yes， and I think that's the last thing I want to say， okay， cool。

So today we're talking about exceptions。 if you thought the last lecture was hard。

 then you're gonna think this one is not hard because it's not。 we went up。

 we went up in difficulty all the way and now we're going way down this one's chill by my reckoning but still new content some of you are not happy about the last lecture and that's okay but something I have to tell you is if you were confused please again I will say this again and again until I have to the end of time look at the slides after the fact if you were confused over the previous lecture I very carefully structured it so that if you read it like you should be able to get the same content out roughly they're structured in a way that you should be able to follow along So if you read them and you still don't understand come see me or read it again。

😊，Before starting my homework， I highly recommend you get the concept down， okay？Cool， alright。

 that's my three minute diattrobe。 We're gonna go ahead and get started with exceptions。

 Then this image is also AI generated。 I like it a lot。 And you'll see why。

 why this I chose this in a bit。😊，Soment code as usual。 Allright， so on our docket。

 we've got exceptions， we've got using exceptions， custom exceptions。

 and then this thing I'm going to introduce called exceptional control flow previously。

 we had continuation passing style now we're gonna have something called exception handling style but we're gonna see that in a second here but moving on last time we learned about the CP thing。

 which is kind of。😊，The motivation was sort of， let's make tail recursive functions automatically。

 Okay， the compiler can do this。 And that's not quite the right motivation in terms of like。

 you don't really care about that。 The first motivation is that it's really good practice。

 It's really， really good synthesis of everything you've learned this entire semester。

 is that it makes control flow explicit。 It's interesting to see different ways that you can structure control flow。

 And what I mean by that is a different way of doing instructions in SML than just go compute value and then come back to me。

 continuations are kind of a disruption to the idea or a refinement on the idea。

 So what we're doing today is gonna be the same deal where we're kind of treating control flow differently and seeing how control flow can be different。

 And then the next thing， this is just reapping CP。

 So I don't really care about that for this lecture。😊，All right， exceptions， What are exceptions。

 Well， I think you already know the answer to that。

 Remember the definitions for the behaviors of an expression。 What are they。 Shot them out to me。

Value evaluates to a value， right， what's2？Loops forever。

 thank you for saying it because this is exactly the order I wanted it in。

 and then what's the last one？Raise's exception and raise's exception is in Time new Roman caliri 12。

5， because today we're talking about raising exceptions primarily。 Okay。

 this third behavior that we haven't really talked about a whole bunch。

 but today we'll give more detail we've been， I mean intentionally not telling you about it。

 But now is the time to peel back the curtain， which is the theme in this course。

 Okay recall the expression 1 div0。 What does that expression do， Please tell me。What do you think？



![](img/55e9d026d4209566a1c0b5fe115b4b2a_3.png)

It loops forever， no， it does not。If you type1 give0 into the SML andJ top level where you're going to get。

Is the uncut exception div， which is a kind of explosion conceptually。

 but it's not exactly an explosion， because you divide by 0， and that wasn't a great thing to do。

 So that's one example of an exception we've seen so far。😊。



![](img/55e9d026d4209566a1c0b5fe115b4b2a_5.png)

But we're going to see some other examples that are also reasonably interesting because these exceptions are actually not special。

 they're very common to a lot of things at the NJ top level including div。

 including modD and there are a few more that are a little bit more fundamental to how we use SML okay and I put my chalk somewhere and I can't remember whoa。

😊，Okay， well， it'll turn up， oh， here it is。Allright， so Dave is specific to a certain function。

 the division and modulus operators respectively， but here's a two more for you okay and you may or may not be familiar with these one is the exception match。

😊，Match is an exception that is raised on a certain circumstance， and the other one is called bind。

 Okay match you get when you try to use a non exhausthaive match or you enter a non exhausthausive match。

And then or a non exhaustive match that the case of a non exhaustive match that you didn't take care of。

 and then bind is raised when you try to bind to a value something that doesn't match。

 so I'll show you an example of that okay so。😊，If I， I'm gonna do the board for now， if I do this。



![](img/55e9d026d4209566a1c0b5fe115b4b2a_7.png)

So I define F to be a land expression that does this， right？The NJ top level will yell you。 Hey。

 that was an non exhausthaive match， right， Because why。What's wrong with this function。

 what am I not taking care of？好。Any case other than one。

 anything that's not that will not be matched properly。 So oops， that was a really bad one。

 You have to be careful when you're defining these functions。 So if I did Fn1 goes to2。😊，Boom。

 match non exhaustive， and in particular if I bind it。😡，FN1 goes to two。

 what's going to happen if I do this？Boom， uncutaught exception match。 Oh boy。

 you didn't match properly。 The match was non exhaustive。 So you got an exception。

 but it says uncutaught， okay， which signals you might people to do stuff with that leader。

 The second example for bind is right up here。😊，If you try to do so an archaic way of doing tests is that we used to do something like this。

 We would say vow， like one equals。Something， okay， some expression。

 And then it would try to bind to this thing on the to this thing on the left hand side。

 And if it pattern matches， then it binds， then it matches rather。 and if not， then you get an error。

 right， which is this。So boom we have another bind which is or another exception bind because 1 plus1 evaluates sit2。

 which does not match one， so therefore there's no way that this pattern matching can match， yes。😡。

Yep。It's I shouldn't say buying I say match because this does not produce a binding。

 This pattern is not does not have any variables in it。 therefore does not produce any bindings。

 I would say that I tried to match one to one， and then I succeeded with zero bindings。

On a conceptual level， this is kind of the difference between some or none and then some of nil。

 if that makes sense。 But this doesn't really matter。 Okay， but yes， these are two examples。

 One way you can think about it is that if I define Fn1 goes to 2。

 this is kind of implicitly a function which says this。Any other case goes to raise match。

So this is a useful way to think about how this is kind of de sugargged。

 If you ever specify something that isn't matched， It's just gonna go to a wild card that raises match。

 Okay， and that's one way to think about it。 Okay， so this is everything that we just saw。 Okay。

 and these two exceptions are the most。😊。

![](img/55e9d026d4209566a1c0b5fe115b4b2a_9.png)

Pertinent to using S M L in general。 Okay， because they're the ones that arise out of just doing common processes like binding and matching。

 Okay， but there are more specific ones for certain functions like the div exception itself。 Okay。

 Alright， so what else can we do with these exceptions， well。Yeah。

 I I basically just wanted to say that if I don't return a value。

 if I can't return a value in certain cases， I might want to raise an exception because sometimes it's not defined when I need to return。

 div is a partial function。 But I don't want it to loop forever。

 and I sure don't want to give back a value for dividing by0。 So what I'm gonna do is exceptions。

 The whole point of having exceptions is that I can provide a convenient escape hatch。

 So I don't have to give you an answer。 Okay， it's like if you asked me a question in lecture。

 And then I said， raise div。 And then I went on to the next topic。 I completely aborted。 Allright。

But if you've been paying attention， remember that we learned about these things called options。

 right， We learned about options， which are sum of X。Or none。

 And this is itself a way of returning an optional value， right， of giving back no answer。

 because of anything， any function that's marked as a T option returning。

 then it must give me back something or it gives me back nothing。 And it seems like a better way。 In。

 In fact， I will say it is a better way of dealing with this because it's a type level distinction。

 right， Let's look at the， the type of dip， right， div。This sub type insert in to in。Now。

 looking at this divide function as a human， as a SML programmer， like six weeks in。

 you know that div can raise an exception， but if I gave you this information。

 if I told you div is insert to endt， you would have no idea that it could possibly raise an exception because why it's not in the type。

 it's not in the name， nothing about this divide function other than the fact that you know it's the divide function。

Should have told you that it raises an exception。That is really bad because exceptions are really bad because you need to be careful about when you're using them because。

 you know， you're running your long， your long running proxy server。

 and then suddenly you enter a corner case you weren't accounting for an exception gets raised。

 and then you get a 0，1，2，13。 Allright， That's what happens。 Don't do that。 Allright。

 So we got to come up with a better way of dealing with this。 I don't know if my sequencing is right。

😊，Oh， yes。 so man。I must I already， already spell the beans。 Let's go ahead and talk the room。

 We can define a new safety function that has this type signature instead。 Alright。

 so safe will be of type。😊，Int star int to someone tell me what it returns。Into option， right。

 which is a much better type signature because now I look at this and I say， oh， it's an option。

 didn't think of that。 And now I see that if I ever divide by 0， I get none。

 and otherwise I get some， right， that's exactly what I wanted。 All right， now it's safe。

 And now if I'm if I'm using safe， I cannot do something like， I cannot proceed to do something like。

 oh， let me do one safety。😊，Or capital safety X。 And then add that to the two， right。

 I can't just like go on my merry way and then add this。 Why， because this is an optional value。

 And the only as you learned when we did sub list sum。

 the only thing you can do with an optional value。😊，Is you case on it？And then in this case。

 I would like， you know， I would do something for the nun case。 And then in the sum case。

 I would go ahead and like add to or whatever I'm doing。 Okay。

 but you shift the burden of dealing with this who the color versus the burden being。😊，Well。

 sometimes your stuff gets wrecked， right， That's kind of like the the promise of an exception raising function。

 So this then begs the question like， okay， alright， al right， that's cool。

 Why are we even using exceptions at all， Why even have exceptions。 When I do have these very nice。

 optional values。 and the answer is that sometimes it's a pain。 Allright， We're programmers。

 we are lazy， Alright， a non negligible amount of my motivation every day is producing as few as few lines of code as possible in a given day。

 Okay， I'm trying to do my best。 So。😊，Let's look at these two specifications。 Oh here's another note。

 I wanted to say if you look at the full specification right now， our deep function。

 we had this requires n is greater than 0。 right， We had a precondition n is not equal to  zero。

 sorry， N is not equal to 0。 And then otherwise， we're gonna get what we want what wanted。 right。

 we put that in the requires。 the precondition。 But for safety， if we have none， yes。😊。

D is not equal to 0。 Yes， thank you。 D is not equal to 0。 That's a good point。 But for safety。

 we have absolutely none because of the fact that， well， why because I moved it to the type。

 So again， with this parse， don't validate stuff I was telling you about in lecture 4 that comes back where it's like this。

 this dichotomy， this tenuous connection between。😊，Specation between preconditions and types， right。

 we just moved the bird into the type itself， and that's a better way of doing things usually not for today's lecture right。

呃，扣。But。 b， I era this。 Okay， but this might be a little bit of a burden。 So here's。

 here's what I'm to say to you。 suppose that I wanted to compute people's grades and then find the average。

 which is an example I actually already used on the last lecture。

 So we're gonna call it average grade。Average grade。And this is for like a particular student。 Okay。

 let's say， so we have L， which is of type in list。

So let's suppose I have every this particular students like grade on every assignment。

 and I want to compute the average。 What would I do。

What's a handy way I can do this without having to define my sum function？Olold。

 list up hold old list up， old door。Doesn't matter the。Hold L up plus zero， our good friend。

 and then I give it L。Friends。Dive。List Stling。Or just length。

 I think it's also available at the top level L。 fair enough。 this is my average grade function。

 But then well， how much faith do you have in me because if my bookkeeping is correct， this is cool。

 But if my bookkeeping is not Oh not correct。 And for some reason。

 my grade spreadsheet is empty for a particular student。

 that means that my grade calculating program is now going to crash and suppose I'm in the middle of calculating your grades for the midsster and it's like 1159 because I procrastinate And then the registrar needs a grades and in the next minute and then it crashes。

 Why because I use this， wasn't great。 This is actually the opposite motivation。

 which is I'm telling you that I want to use the safety So if I wanted to be rid of exceptions。😊。

I'd say this。Right， and now it returns an option。 now I can go handle that wherever。 And I can like。

 if I， if I happen to get a nu， I'm like， okay， I skip。

 maybe I skip the student rather than a boarding execution entirely。 Those are two options。

 I can skip the student or I can not calculate grades for anyone in the class。 Okay， those are its。

 it's not a great binary， right。😊，Except。Except that's kind of stupid。 I， I， I wager to you。

 If you have some measure of trust in me， you should be able to ensure to， to think that， you know。

 maybe maybe my grade spreadsheetets is not emptyca that's kind of a silly case。

 So having to handle this sexual logic here。 Like when I go and use average grade， when I do my case。

 average grade of。Everage grade。Da da， da of like this kind of thing is kind of painful when I have a fairly good precondition。

 Like I， as myself， I kind of trust， yeah， my grade spreadsheet is not empty because even if it was。

 I'll just put it back in and then be good for the next time I ran the program， Right， Like。

 it's not really gonna take me a very long time to， to compute people's grades， so。In this case。

 what I'm trying to say is that it's kind of silly because we have to acknowledge the failure case。

 and we have to sometimes at a certain point， trust our preconditions。 Okay， I know this whole time。

 I've kind of been telling you preconditions。 I hate preconditions。

 but also preconditions are great because they're better than nothing at all。 So at a certain point。

 you do have to go to the precondition。 And I'm willing to bet that I didn't screw up。

 And that my grade spreadsheet is not empty。 Okay， so in that case， I will be okay with this， right。

😊，So in this case， I'm going to say， okay， because I know myself。

 because I know that I am in a hypothetically impossible case。

 I'm all right with the exceptional behavior。This is exactly what has caused a billion in one bugs in real life code。

 okay？So I want you to be careful with this line of thinking， The line of thinking of， oh。

 I trust myself， Oh， I know what I'm doing。 Oh， I would never have happened that。 Oh。

 that's impossible。 Al right， Ra your hand if you have a written code said that was impossible。

 and then it happened。Yeah， all of you should be raising your hands right now。 Okay。

 I don't believe you if you're not， okay。Trust yourself。 Don't get me wrong。

 But like lesson of the day。 Don't trust yourself too much。

 Okay so what we going to trying to say is that yes， we can use exceptions， but be judicious。

 be aware， be safe。 And this stretch is beyond like this homework。

 Okay I'm saying for the exceptions homework for what you're doing in this next homework。

 please do use exceptions because that's the point。

 but in your real life code when you go off and like become a software engineer or whatever。

 remember what I said and don't use exceptions if you can if you can help it。

 All right I'm contractually obliged to teach you this material。 but I'm not trying to encourage it。

 Okay cool， just checking okay。😊，And and the trade off seems really bad because it's kind of like。

 oh， I can you know risk my writing two extra lines of code for something that might just crash my program and if I have a really longrun program。

 it might make it seem like it's this doing the safety is never worth it。

 It's never worth the amount of code golfing except as you can see on my slide。

 we do have a way of dealing with exceptions which I've been trying not to acknowledge for the first few weeks we can handle exceptions we can recover from a raise exception。

 we can rebuild okay。Alright， so part two of this lecture is going to be on how we can use exceptions in certain ways。

 So let's let's go through this， right so。S，M L， the most important thing to note here。 actually。

 is theres an a type called E X N。 Alright， Oh wow， I didn't realize this wrong here。

 There's a type called E X N。 And that， in fact， is the type of all of these things I just told you about。

 right， match bind or whatever。 So this E X， N type。😊。



![](img/55e9d026d4209566a1c0b5fe115b4b2a_11.png)

You can think of it like this。Data type EXN equals。Dave。Or match。Or bind。All right。

 this is kind of how you can think of it。 it's a sum type。 it's a variant。

 And then I'm going to put an asterisk here。

![](img/55e9d026d4209566a1c0b5fe115b4b2a_13.png)

And I'm going to come back to that， okay。But here are three valid。

 constant constructors of type E X N。 So that means remember that because of this。

 we have that div has type E X N match has type E X N bind has type E X N， right。

 They're all of this type E XN， which you can think of as standing for exception name。

 but at this point， it might be lost to the analysis of history。 I'm not actually sure。

 but that's true。 But also we have。😊。

![](img/55e9d026d4209566a1c0b5fe115b4b2a_15.png)

내요。Of string。 I'm sure you've seen this。 I think it's on your homeworks， right， failil omitted。

 So fail is actually not that type because remember， your data types。

 fail must then be of type string to E X N。 E X N is not special in this case， right。

 It just looks like a regular data type declaration。 So these are all。😊。

Certain exceptions that we have available to us， and we can say raise E。To raise that exception。

 if I ever write raise and then E， which is of type EXN， right？Or E of T X1。

Then it will raise that exception， and then everything will get wrecked okay。So， for instance， like。

 we could do this ourselves。 I don't know if you've done this。 But if I wanted to。

 I could explicitly raise give。Now this would completely wreck my program。

 but I could ignore this like seriously ignore it， it doesn't matter。

 and then I can also raise match and I can raise bind。

 which means I can also define you a de fund function which takes in an input and then it raises div。

😊，Oops， sorry， whoops， that fun function。 X。 Oh， wait， freak。いやそう。还是。In my， in my defense， I。

For my job， I have to work in one of like 20 different languages at the top of the hat。

 the fact that I've made as few language specificific mistakes as I have is honestly impressive to myself。

 But I can make this function fun function。 And what does it do， Let's see what fun function does。

 Let's give it shoot I got div what happens if if I give it one shoot I got Yeah。

 this function just raises which might not seem super useful to you。 And indeed。

 I don't really see why you would ever write that function。

 But there are other functions we can write by raising exceptions。 Yes。😊，Of race。 Yes。

 so that's the next， I I believe that's the next slide。 but I'll say this anyways。So okay。

 let's get rid of this rays is not a function is worth noting okay。

 as in you cannot do like val x equals rays any time you have rays you have to have the argument。

 but rays E for E of type E X n，😊，Is of type alpha。 And I'm going to also put a star here。

 but I'm not going to come back to it because there's a technical detail that might not make this。

100% spiritually correct to say， but conceptually it's correct to say。 All right。

 it has type alphapha。 that's all you need to know。 This thing has type any type， why。

 because if I'm writing a function and I have an exceptional case I want to deal with。😊。

I don't wantan to， if this， I'd like type in。 Now， I have to like do a bunch of like cartwels because live return type might not be end。

 The point is， if I say E is of type T， right， this like judgment。

 this like thing I say this is only true。If only if。If E evaluates to value， then。

V as a type T right， the point of this kind of supposition is that it's predicting the future behavior of the code。

But this might not be true。 It's if it returns to me value， then it should be of that type。

 And ray is never returns to value。 Therefore， why not give it whatever type you like。

 We're not constrained to give it any particular type。 So it has polymorphic type。

And my comment about how race is not a function， it means that it's not correct to say this。

Like you couldn't do this。Right， which you otherwise you might be able to think of it as like it's mapping。

 get the first thing and then apply raise to it。 but you can't do that， yeah。Yeah， other values。

Values， exceptions are values， functions are values， exceptions are values。

 what isn't the value nowadays？😊，We can make it spicier， too。 Give。

 I don't know why printlet looks like that。 That's interesting， but fail high。Hm。

 all these are values of type ExN， why not？one thing you realize is like everything in SMML。

 you can kind of de sugared to like something else because this makes for a really nice thing where like nothing I very few times have I had to tell you something new outside of the first like four weeks。

 It's always been an application of something you've already seen or a natural consequence thereof right So that's just some trivia and I'm only saying it because it's a relatively chill lecture and knock on wood。

😊。

![](img/55e9d026d4209566a1c0b5fe115b4b2a_17.png)

There is no wood。 I'm probably gonna finish。Yeah， there's okay。ま。Cool， all right， cool。 okay。

 so I already said this but yeah， it never returns， it's okay to give it whatever type I like。

 All right， cool， Any questions on this， any questions on exceptions thus far。😊。

Because this will get。Not actually that much more complicated。

 but it will get a little more complicated。 Okay， All right。

So we also have a language construct called handle。 All right， handle lets us handle exceptions。

 and the way that it works is we can write something like this。😊，All right。

I want you to put yourself in。 Oh， I shouldn't have not I think about it， I shouldn't have raised it。

 But we're gonna go back to the average grade case， okay。All right， we're going to do average grade。

But now we're going to report the grade， like I want to get out a string that I can show to your parents about what your grade wants。

 okay so here's what we're going to do。I'm going to stop writing list because thiss annoying me and we're going to use full R this time because I feel like it。

Addition is commutative， okay。No。Actually。Ex shouldn't have said that for shadowing。 anyways。

 we're to do div。😊，And then we're going to do length of out。 right， This is my thing。

And then I want to say， well， let me， actually， sorry。哦。A V G equals。啊啊。In。Yeah， so I。

 I wanted to actually do something special。 Your grade is。😊。

Is I didn't actually give you the students' name。 So this is the best I can do。

 But I'm a concat into too string。😊，Of ABG。Andd， right。And this whole thing。

 I realized I kind of left the line it there。 But this whole thing is an expression。

 It's essentially equivalent。 not so it's not。 but， it does the your grade strength thing， right。

 It's essentially spiritually the same as before。 except we know that this div might raise an exception depending on whether or not L is empty。

 So we're gonna use our nice handle construct。 And I'm gonna tell you it'll look like this。😊。

I don't think I have to put prints here， but I will。 Brooks' rubber let is an expression。

 I say handle。Do。Go to。Air。No grade。Bound。All right。What this means is。

Candle kicks in on the left here an expression。 and it says if that expression ever raises an exception。

 pattern match it against a certain number of clauses of of exceptions of exception constructors。

 You see the value in having these exception constructors。

 which is that you can pattern match upon them when they're raised。 Okay。

 So when this ever raises div， we will pattern match on it。 And then if it matches here。

 which it does， we will enter error no great bound。

 So that means that I think I give you some examples。😊，Your grade is the average was， oh， and also。

 I guess in this case， it was a shrink star ant list， I don't care cool。

I want to show you some news cases， but basically I'll write it down the board， right？

If I want you to use this function。Oh， shoot。 I delete whatever。If I wanted to use this function。

 I might say average grade。1 comma1。And this will evaluate to da da da da da， your grade is。

 you know， from there one。But if I wanted to do average grade。On the empty list。

 what am I going to get？Air。I'm too lazy at the rest， okay？Yes。😊，That's my average grade function。

 So we can recover from these things。 Okay， and it's all because of the。

 the simple rule that this handle thing obeys。 Okay， and let me。😊，Write it out。

 I'm not sure you to know racist this because I want more vertical height。Okay， the general form。

 which I'm going to write out just so that we're clear on everything is this。😡。

I've got some expression E， I handle it。And I give it some number of patterns， P of one。Or dat dat。

 dot， Or Im sorry， piece of one。Arrow， E sub one。Da da， da， or。啊。It's better way than this actually。

Piece of N，arrow。E sub N。Okay，This should look like a case。 It looks very similar to a case。

 the same way we have like none goes to blah or sum of X goes to blah after the of。

 We have that after the handle， right， and I'll grabroborate it up here。

 But another thing we have to have is that each of these expressions。

Each of these expressions has to have type T where E has type T。That is to say that each handle case。

 each of these has to have the same type as the thing I'm handling， why what is the reason for that？

B， b， like more specifically，I basically told you the typing rule like I I feel like to say like because so it's well typed is like I meant more motivationally like like basically this breaks type safety。

 Okay this means that we might get multiple types out because if E were not to be of the same type as E1。

 then suppose that it didn't raise exception， then this expression would go to E of type inputs say if it did raise exception。

 we'd go to E1 of type string， let's say。😊，Bad， nobueno。 don't do that。 right。 Don't mix your types。

 So therefore， we want to make sure that all these things sort of the same type。

 And each of these patterns， I， I know haven't really said like patterns have types。

 but they kind of do。 if you think about it。 like a constant pattern one has type in。

 So like each of these patterns should have type。EXN。Okay， that's kind of the idea。嗯。

And then we can describe behavior with just these few clauses。If E never raises an exception。

 it's just E， the handle doesn't apply。 The handle only matters if there is an exception。

 and if E raises an exception， then it will go and pattern match to each of these piece of I clauses in order。

 Sam as a case。 But now it'll be not casing on the return value。

 itll be casing on the raised exception we march on linearly。 And then if it reaches one。

 the first one reaches that matches， it will become that And then if it doesn't match any of them。



![](img/55e9d026d4209566a1c0b5fe115b4b2a_19.png)

Then we rerase the exception， we go back up to the next handler， okay？😡，嗯。

So let me give you a concrete example here， I think。

Suppose I wanted to do1 d of0 handle match goes to， I don't know， A。And then I want to handle that。

Dive goes to B。 So I see what I'm doing So the handle applies to this entire 1 dip 0。 Okay。

 I handle it for match， and I go to a。 Otherwise， I handle this whole thing to Dave and go to B。

 What do you think it's gonna be。😊，Oops， it's type bear as one of this。 Maybe it doesn't do that。

Let me put two prints around this， maybe I was wrong about the association。Oh， sorry， you're right。

's I was thinking me let me do a nice example where its returns a string。

 but actually I should do this。 Sorry， you're right。😊，Handle match goes to A， handle div goes to B。

Oh my God。 Okay， Ive， I've， I have un prehees。 Alright， you know what， it doesn't matter。 One div 0。

 handle match goes to 0 or handle。D goes to2。 Allright， there we go。

I wanted to do like a nice all you can see is A or B and the not one and two。

 which are meaningless because there's so many of them， but geez， what can you do？Raiseitive。

Handle that doesn't match the match note。So we rerase， so this becomes raise div， handle div。

And then the div is raised in the handle by this guy。 So then we match the div and we get to。ok。😊。

Yeah。Only if this didn't raise an exception。 If this thing didn't raise an exception。

 what happens is we get the int， we bind it， we go here， we get the string。

And then that truly passes in。 And then that goes into the handle the string。

 And then because it wasn't raising the exception， then we proceedly nearly。

 But this handle is surrounding this entire expression。

 The next component of this I was going to tell you is that exceptions propagate up exceptions。

 If I have a subexpress， which raises an exception。

 That means the whole expression raises that same expression。

So this guy is the subexpression of the greater la， but if if this div in here ever raises a div。

 it'll go out to this， it'll go out to this， and then it'll go to the handle。😊。

If this were the reason exception is。So only the right hand side needs to be of the same type as the thing being handled。

 The thing being handled in this case， because it's the shrink concatetination has type string。

 And then the thing I produce if I raise an exception is of type string。This one's prototype。Yeah。

With new。Oh， I see。 Okay。 instead of that， what I'm going to do is。啊，就色。1 of 0 handle give goes to。

 And then what I'm gonna go to is now I'm gonna say raise， fail high， handle， fail。

 I'm gonna show you that you can actually bind that constructor。 The thing I get fail。

 you can actually bind when you handle it。 goes to S。 Sorry， I should not do that。 I should do。道。

I want to be well typed。 Okay， basically， I think that this is just a print problem。

 I I So what I meant to say was if indeed， you handled match to go to 0。

 and then this guy was handled to say div no， sorry。

 If this thing was handled to say div goes to this whole expression right associated。

 I think it would be fine because this would be about type alpha handle goes to in。

 But I think I just mess up the print。 and I do not have oral rap on。

 which means I can't go left and right， which is so sad。

But indeed you could raise whatever exception here like another exception。

 and then that handle would be specific to this you just have to be you have to be kind of careful because actually actually it's ambiguous because if you don't put the friends。

 I could proceed this handle modifying just this。😊，Or I could see it modifying this。 Or actually， no。

 I know what happened。 I know what happened。 We to do this。 It， it became this。😊。

Do you agree that this is nonsense？So what？This is a parsing thing when you're doing handles。

 be very careful with your friends， basically what I'm saying is that this thing above。

 which was well illt was because I didn't expect that the pre would associate this way。

 The handle is modifying match， which is nonsense because match doesn't raise match match is match that's another good question I guess which is that。

😊，Dive match div handle div goes to match is going still be div。Becauseuse this is， this is div。

 It's not raising div。 It is div。 Okay， It gets kind of meta。

 But my point is be careful with your friends。 This would have worked that I put a left print here and then kept the the other thing the same。

 okay。😊，And if this is confusing， that's okay， you're going to go through plenty of fun trivia exception examples to our own lab。

 this is so trivia。😊，Any other questions about the trivia。We Iya yeah。

I'm pretty sure in this case you can。 I wanted to be safe， though。 And this is clear。

 good reason for why you should be safe。 So really， I'm teaching you by failing because like。

 be careful。 What can I say， Co， Alright， we're gonna move on。 maybe I should move loop。

 I don't have that much， okay。😊。

![](img/55e9d026d4209566a1c0b5fe115b4b2a_21.png)

So here's some other examples， if I do raise div， that raises div。

 if I do raise div handle div goes to two， that goes to two right because I handle it raise div。

 handle bind just raise this div because we match against this and we fail。Rise div， handle bind。

 goes to one or div goes to two， then we raise the div， we look at bind， we say nope， not the same。

 then we go to div， we say， oh yeah， that is the same and we reduce the two。

And then two handle div goes to three goes to oh what， that should be two， sorry。啊。You know。

 but yeah， any questions on this kind of stuff。 Yeah， it's a simple idea。

 but it composes with this song。 You can make these arbitrarily complex。OK。

And then the other thing I wanted to tell you was that if a sub expressionion raises an exception。

 which I kind of alluded to， then the entire expression does。

 And I'm not gonna write this out because it's kind of not interesting。 But basically。

 exceptions propagate outwards， meaning that if I have a handle。

 if I have the handle surrounding an arbitrary function call。

 that means that if the function call ever raises an exception。

 it will go to that handler provided that there is no handler in between them。

 What I mean by that is if I have F of unit。😊，Let me to be explicit about the trends。Handle， b， b， b。

 b goes to， let's say。 If this function F ever raises an exception， we will go here。 Okay。

 but not if the function F previously catches the exception first， Okay。

 exception handling happens when you reach the handle， and then optionally， it might continue。

 but you only catch it when you reach the outermost handle。 The nearest en closing handle， okay。😊，So。

 for instance， I just wanted to show you this thing。 So， okay。

 this whole nested expression is like big and pretend their print are on this。

 But we know that 4 div 0 raises div， right， So 40 races div。

 But this is a sub expressionpression of this guy。 So this thing also raises div。😊。

But this is the sub expressionion of this guy。 So this also raises div。

 And then because this raises div， then we handle it。Because it's raative。

 then because there's a handle， we match to it and then we get five。Okay， so it just。

 it goes outwards。 All right， think of that as it propagates outwards like that， okay。嗯。Cool， so we。

 this is pretty useful because it lets us essentially jump in our reasoning to somewhere that's very far away。

 but somewhere we were previously。 if I ever see a handle。

 then I know I might come back here at the drop of a hatch。

 If this guy ever chooses to raise an exception， in essence。

 raising an exceptionception kind of lets you fail。 It kind of lets you continue from your failure。

 It kind of lets you failure your continuation。 I'm gonna stop being so waiting about it。 Anyways。

 it's kind of like a failure continuation。 You can think of it that。

 It's also kind of like a go to is bad。😊，Okay， and before we saw theres this kind of relationship。

signal to you that we can have this relationship between returning an option and raising an exception。

 It turns out actually， if I have this function f of type t1 to t2， which might raise an exception。

 I can always define to you F opt like this F opt is such that it goes to sum of as if F of x reduces your value and that value or it goes to none if F of x raises an exception and otherwise e loops forever but I can always do that for you。

😊。

![](img/55e9d026d4209566a1c0b5fe115b4b2a_23.png)

Any would like to actually wager a guess as to how I'm going to define F optt。Well what might I do？

With this specification。It's not obvious。 So it's okay if you don't exactly know。 Alright。

 what we're going to do is I'm in intention， here's what I want to do。 I want to call F X。

And I want to handle。Anything。If I ever get an exception， I want to go to none， right， So I say。

 and this is allowed， right， This is a wild card pattern。 Wild card pattern is a valid pattern。

 and it goes to none。By。Our claim there's a problem， this is not going to satisfy that specification。

Here's why。It's not going to type check actually， or I'm sorry， it is going to type check。

 but it's going to constrain our type。 In fact， let me just write it for you and let's see why。😊。

P F optt to x equals Fx handle underscore goes to none。sorry。

 I'm going to make it polymorphic and that's why I should have done anyways。



![](img/55e9d026d4209566a1c0b5fe115b4b2a_25.png)

F opt or like， yeah， make opt F X equals F X handle， underscore。

Thiss none because I don't have the none VF function available to me。

 I just like made it an argument， which I can do。But note that this function F must be of type alpha the beta option。

 F has to return an option。 I said to you previously， F should be of type T1 the T2。

 Any T went the T 2。 Why it's because。If this thing doesn't raise an exception。

 we get the result of Fx， but that type needs to be the same as this type。

 which is of type alpha option， right？😡，So if this is a type alpha option。

And then this expression we're handling is is of type anything beta， then beta must be alpha option。

 right， so we can train it。 Here's what we should do。Indeed。

That is F opt to make an optional function from any F。 And in fact。

 I could pass in the F as an argument。 that will be strictly more powerful rather than do it for specific F。

 but we can always do this， so we can always go between and you could do the the reverse as well relatively easily。

😊，こ。All right。And then check your understanding。 except I already told you。

 second thing I gotta tell you， This sucks。 This is terrible。 This is awful。 Don't never do this。

 Never do a handle that catches anything。 I don't care if you never intend to use SL after this。

 if you're using Python， never accept。E never accept all。 Okay。

 like if you handle every possible exception。 Okay， because this would handle any possible exception。

 there might be some exception you were not aware of that gets raised。

 Like you do some red crap like an integer overflow， right， which is really。

 really fri and bad because now you're gonna not know and you're gonna get none， right。

 So it's better to， if I knew what exception F raised。

 I might say like specifically like if it's div raising， let me handle div。 Okay。

 but if there's match or bind or whatever。 And I， I don't want it to go all the way here。

 I want to know about that in that case。 Otherwise， I'm not going know。😊，Okay， this is， again。

 like a common sense tips rather than strictly curriculum。 But please don't do this。 Okay。

 it's a really bad idea。ok。And I'm not going to write this out， but basically。

 I've got this FX function。I do in2 string on this X， and then I concatenate it with this string。

 and I handle div to say divided by 0， okay。Here's my question。Is this true？

Is F given 1 d of 0 going to be divided by 0， It's going to enter this handle case。No， who said it？喂。

You said eager evaluation， yeah。Oops。All right， you can keep that one， you can keep that one。

 take to， take to， take two， take two。Yeah， okay course enough。Eageger evaluation。

 meaning that remember， prior to entering the body of F。

 I'm going to try to evaluate one div0 before I go and meet this handle。

 The handle never happens because this F is just a big lambda that looks like this。

 right The handles inside of the definition of F， but it's not outside of this one de0。

 So one de0 is going to immediately。Race is an exception。 So this is not true。 Okay。

 and I think I actually had a short example for you here。



![](img/55e9d026d4209566a1c0b5fe115b4b2a_27.png)

Yeah， so suppose I've got this function F， basically it just like does one plus it's recursive result and then at 0 it raises div okay let's see what happens if I do sum of f of given4 and I handle div to go to the nu。

 right？😊，Okay so if I expand the definition of F， I get this big case。

 and then I get one plus f of4 minus-1。 Otherwise I go to the three case。

 I get one plus f of2 and I get one plus f of1，1 plus f of0 and now I get this whole thing okay one plus a bunch of things I I'm here like outside of me is a bunch of this random self and I get one div of0。

 what's gonna happen， well， remember， look at this。

 I wanted you to see the way that like this handle is still here。 if。

 if I view programming as just like the text changing。

 this handle is still there and it's a subexpress， This is a sub expressionpression of that。

 meaning that if I raise div， I'm gonna go straight out to this none because div gets raised div div。

 div div， div div。😊，Handled none。 Okay， so just remember that the handles stay around。

 They're persistent， okay。But you can kind of just think of this in terms of the text changing。

 right？

![](img/55e9d026d4209566a1c0b5fe115b4b2a_29.png)

And then last note for the section is exceptions are something we call a side effect。

 basically meaning that it's something that's not just computing a value， like reading from a file。

 printing the console， imperative self。😊，A raising exception is a side effect， so is looking forever。

 So this means that we can this can break some of our nice ideas like I should be able to permute。😊。

Anything that binds wildcard， I should be able to put it in an arbitrary order。

 not true because if I put this first， I raise bind and if I put this first。

 I raise match and those are two different outcomes so I can't freely permute things it means that mathematical thinking is harder that's why we prefer to work with total functions because now I can't arbitrarily rearrange these if I so feel like it。

And then a fundamental little fact about that， which is I alluded to earlier。Is that addition。

A is not commutative anymore。In an exception raising world。

 addition is not communutative because if5 e1 as raised div plus raised bind。

 and this is true because raiseds gives back whatever type， this is a welltaed expression。 This way。

 div is what's raised。 But the other way， bind is what's raised。😊，ok。😊。

Addition is commulative for valuable expressions， but not for arbitrary expressions。

 So this is because our definition of extension equivalentvalence is that you're only equivalent。

 if you raise the same exception。 Okay， that is the a card criteria， Allright。😊。

It doesn't really matter， but it's kind of fun to think about。

 And I have this like little like programmatic thinking is sometimes not mathematical thing。

 Sometimes it usually is。 Okay， but I thought that was fun。😊，Alright， Cl time。 get up。

 It's a new third。 The points have been reset。 Oh， you're all working from 10 points。

 You have this for the second half in the second half。Anyways。

We're gonna be talking about a brand new car if a car is also an exception。

 okay because we can have these nice exceptions that we previously just talked about。

 we can think of this data type exxN in this way。 but it's not actually strictly how it's defined okay and I'm gonna to give you a motivating example first about why that is。

 which is our old friend fact， So fun fact it0 equals one， but also a fun fact。

 this thing loops forever on a negative input that is also a relatively fun fact。

 but I don't really like that right because it's quite difficult to tell if something is looping forever。

 or if it's just taken a really long time， In fact。

 it's impossible to figure out be a mechanical means。

 So we want to do better than a function which knowingly loops forever an input even through its precondition。

 why because people mess up the preconditions。 Okay like you can write this library function and say。

😊，Requires n greater than zero。 and then on your Gitthub page two months later， someone will write。

 hey， my function seems to be looping for everyone。 I give it a negative input and then you're like。

 yes， because you broke the precondition。😊，And not salty。 Okay。

 so we want to raise an exception instead of looping forever。

 And it turns out that what we can do is we can define new exceptions。So Eric told you all this。 So。

 for instance， Os， actually sorry， I was supposed to do this first。 let's rewrite this。 Okay。

 instead of doing n times fact M1， we're going to say if n is less than 0。😊，Then raise something。

 but pretend pretend you forgot about the thing about custom exceptions and then say， we do this。

I say we raise mind。Else， we do n times fact n -1。And now this function no longer loops forever on any input。

 I claim to you。 Okay， But the problem is this phrase is bind。 You're gonna get bind。

 It's not very descriptive If your factorial function gives you bind like what。

 what am I supposed make of that， What does that tell me Nothing because bind is supposed to be for if you failed to bind to some argument。

 realisticistally， no library function should ever raise this unless whoever implemented did something wrong。

 right， So if you do this， your kind of， it's not a good idea， right。

 So back to this idea of custom exceptions。So also another thing I want to say is。😊。

We should change the type then。Oh shoot， we should change the name of this to this。嗯。

Back to underscore E XN in Ocall， it is a common practice that library functions that are possibly exception raising are suffix with underscore E XN。

 I just want to let you know like that's I think that's a really good practice。 Okay， like again。

 exceptions are not evident in the type。 but you do have the name。

 So I think it's a really good idea that if you're going be calling a function that potentially raises an exception on you。

 it should be clear from the name of the function。 Okay， again。

 this is kind of like this is kind of my lecture to give you like random tips that aren't strictly correspondent。

😊，Okay， and we could raise fail like negative number or facts Go negative number。 right。

 We could do that。 But now if， I want a pattern match on that， I have to write like， you know。😊。

Handle。Bll。Negative number， right， I have to like explicitly write out the message and guess what。

 If I make a typo and I forget this R， now it's not gonna to match， right。

 So I want to do better than that。 Let's do better by making a new exception。 Okay。

 and I don't remember if I put on this like， right okay。😊。

Let's discharge that asterisk I told you about earlier。

 which is that you can think of it as being defined this way。

 but it's also not because it's also defined like this。😡。

EXN is the only extensible type okay you might also think of EXN as standing for extensible type I'm halfway sure that's actually a joke that someone getsed the professor with。

 but the point is that it's called extensible because you can add constructors to it after the data type was declared there are no other types like EXN in standard amount okay it's not special except in this case it is special That means that if I wanted to add a new constructor to the EXN type。

 it would be as simple as me saying。😊，Exception。E， and then somewhere in the back of S M L's brain。

 it'll like remember that， oh， hey， there was an E here。 now。 now there is one。 Okay。

 and along with all of the other exceptions， there are a few I didn't tell you about。 Okay。

 but the point is that this declaration lets you make a new exception。 And now， after the fact。

 I can handle。😊，E goes to da da da。ok。😊，Worth noting that if this is not the name of an exception。

 it's going to be treated as a variable， which means it will be a wild card case。

 So be careful about that if you misspell this， you are in deep water。 Okay。

 but you can have custom exceptions。 All right and that's actually a really cool thing。

 but because now it means what can I do instead of doing this， I'm gonna to say exception。😊。

And I'm gonna have my own exception。 I'm gonna have my own private little exception that I use and that vendors of my function should be wary of。

 And instead of raising bind， I will raise this brand new exception fact。😊，Which is descriptive。

 It's descriptive。 It's easy to pattern match upon。

 And now I don't have to rely on someone else's exception and then possibly get caught up in their handling logic because if this raised is bind。

 but elsewhere were in our code， we had a handle bind and we hit it on accident。

 that wouldn't be good on us。 Okay so don't mix and match your exceptions， okay。嗯。Right， okay。

So this is our new definition， as I just showed you on the board okay？😊，And then if I did this。

 for instance， let's say I did some of fact EXN given negative one。😊。

And I handled fact to go to none。 I would get none， because the exception will be raised from this。

 and then it propagates outwards to the handle， okay。Any questions on this？故。Al。

 we can also have defined exceptions that take arguments。

 I can do exception error of string and then suppose that like I then defined a function F that could raise that function error。

 I'm defining a higher order function for you here called run process。

 It takes in what I call a thk which I'll talk about a little bit more in a few lectures。

 but it's a function that takes in the unit and returns a string， So this function could do anything。

 could raise an exception， could look forever could evaluate to value。😊。

But run process takes in that function and it transforms it into a safe function because if this function specifically raises error。

 I will handle it and give you up this nice formatted error string， or I'll give you output。

 And then whatever string it returned。 Okay， so basically， this is like more transparent that like。

 I now have a function， which goes returns me a string。😊。

And it just runs it and then looks at the output， okay， is that relatively clear？Basically。

 I find a new custom exception that this function might raise and then now I can handle it same as same as anything else you saw because it is just a specific application Okay。

 so if I did run process on unit goes tofu， I would get the string output colon spacefo right because it would take this and then it would concatenate it here。

😊，But if I had FN unit goes to raise error of bad， then run process on that function would give me error called bad because we'd catch the error and then concatenate it here。

 okay？This is like a reasonably common thing you might want to do。 I think it looks pretty clean。对。W。

 did I not tell you I not write anything。Oh， I wrote in the footnote， didn't I， Okay。

 I just want to say that some people， Yeah， Some people say E X and San were sensible。

 but I've never heard that actually confirmed。 It might be a lie。 but you know。

 it's a pretty good one， cool。😊，All right。Last thing we're going to talk about。

 which is exceptional control flow。 I think that on the board in the Citadel Commons。

 somebody wrote something about exceptional control flow at some point。 I don't know who it was。

 but we're going to talk about how we can do instead of continuation passing style。

 something called exceptional handling style。😊，Right， okay。Okay。

 so the point of exceptions is that we can quickly escape from an error case。

 but also if we really wanted to， we could weaponize it because this gives us a kind of control flowability where I can say stop doing what you're doing and go to the nearest handler。

 The key term here is go to， which kind of signals is not a good idea Okay， to be clear。

 I don't endorse anything in the section that I'm actually obliged to teach the so here's what we can do。

😊，I wanted to find a function called search EHS takes in app predicate。

 takes in a tree and returns to be an alpha allright and what it does is it raises a brand new exception called not bound。

 If there's no element that satisfies P or it returns the first element in it's preorder traversal it does so it's kind of like you know option do v or whatever in the sense that like if it doesn't find the thing。

 it doesn't return an option， it just raises an exception， but in this case。

 it's this not bound exception。😊，And actually， I didn't actually define it。

 so purely for my sake of mind， I'm going to put it here。And then pretend that this is below that。

Because otherwise， it would be in SML code And we're in the business of writing code。 Co， right。

 So now I've defined that function。 Let's define the search EHS。 Well， what did we have earlier。

 And I'm gonna show you three implementation。 Oh wow， I like straight up did it。 Okay。

 I thought I show you the CP version first code， So let's start from here and let's do it。 right。

 If I get none， what should I do instead。😊，I should raise， right？Raise。Not found。

 And the name would be search EHS， but I don't care。Okay， and then instead of sum x。

 I would instead return x， so let me get rid of this。But here。

 search no longer returns to me an option because I've defined it to be such。

 so I wouldn't do this actually， I would erase this。But here's what I would do。

Instead of having the sum case， I would simply whoop。You see。

 I'm being very strategically about how I era race here。Ps。Handle。Not bound。Go through this。

And this is my working search EHS。 Okay， here's how you should think about it。 right， Remember。

 our contract， our contract here， our precondition our specification is that search， EHS， search。

 whatever should return ray is not found if it doesn't find the thing。

 So if I don't find it in the left， that is if I get to not found。

 I'm going to go to search the right。😊，It's the same as me casing on the return value。

 but now I give back information， not in terms of the value I return。

 sometimes I give back information in terms of the exception I raise。

 So this exception not found is how I signal to my handler， my recursive call。

 hey you didn't bind it go search the right and now I don't have to deal with the some nonsense because this guy。

 if there isn't an exception， it's just going go to a value and then this whole thing is going to go to a value right so this is how we would do this exceptional handling style where instead of having my noncase and casing on explicitly I just handle okay。

😡，And that is one way to think about it but and let me show you this thing also so by contrast I I'm going to flip around a real fast and go between these really fast do you see sort of the differences here with the CP version。

 which is in the CP version I add my continuations instead of raising not bound I do my FC my fail do continuation instead of returning the value I do SC。

😊，And then I added in this kind of like， you know， I added in this success continuation。

 but I wrapped the recursive call in a。😊，I don't know why this prime is here。

 I brought the recursive call on this failure continuation。

And you see how like if you go in your eyes， like they look pretty much the same， Yeah， similar idea。

 okay。😊，So that's exception handling style。 It's a bad idea， don't do it。But you can， all right。

 and if I'm really cruel to you， I'll put on an exam。呃O。The benefits being almost none。

 EHS is really hard to read。 It's really hard to understand because when something raises an exception。

 it just goes out， it just goes， it goes， it goes and it's not it's never clear to you whether or not there's a handler in terms of like this search EHS like what happens if now like called the search EHS doesn't handle not bound Then I crash So the problem with exceptions is that you have to rely on discipline to handle the exceptional cases。

 but you don't have like a type level thing where like you have to handle the option。

 you have to handle the nu case。 Now it just relies on discipline So exceptions again arekin to preconditions as types as options are to。

Not precond， I guess。For a little SAT analogy for you。All right， and then， yeah。

 I think this is again， like my meme warning you again like， it's a nightmare to debug exceptions。

This idea of like nonlocal control flow， which is kind of like I can be here and I can be like miles down。

 I can be like safely here during my little computations and then I get exception and then I just go straight here。

 I just jump out of my context to go to the nearest handler it's very。

 very dangerous it's equivalent to a go to because a go to just says quit what you're doing stop hammer time。

 go to the nearest handler do not pass go， do not collect $200 Sam idea here with handle right so just be wary of that but it's really good for if you like already or in a failure case and you want to like print out some information and then crash so it's good usage for like error recovery like you're running your pro server and then you get malformed data and you need to exit so you raise it and then you print out some information and then you stop but the idea is not like it's better when you exits are clear。

😊，That's kind of an aside。And then the last thing I kind of wanted to talk to you about is the fact that we can go really hard with this exceptional controlflow idea because before we were talking about search。

 which either returns a value or it raises an exception I'm going do one better for you。

 but we're gonna talk about a function which only raises exceptions and that's how it returns data。

 So we're gonna to talk about this function called list max EXN， note the EXN I put on it。

 but we have this what is this we have this exception max。

 which takes an information I forgot to tell you this also I guess exceptions can take in information the same way that you put this in a constructor。

 So let's declare as a constructor max that takes in an int and gives back in EXN。😊。

So Max is of type end to EX。Okay， so I can declare both of these exceptions here。

 the next one is going to be no max， all right。😊，And this is going to be our promise。

List Max EfN can either raise max M or raise no max and nothing else。

 it will never return a value so it has type alpha because it never returns。

 but this is a fun way we can do with Max right so let's define it。😡，So if I had this mass of EXN。

If I had nil， I would then want to raise N max right because I don't find a maximum element because the list is empty。

Otherwise， if I listmax EXN。If I was trying to find the maximum element in a single tin。

 that would just be my singleton item， right， so I would raise。Max of。

 and I'm going to put friends to make it very clear， raise max of X my only element。And in my。

Recursive case， I have x cons。 X is our good friend。What am I gonna to do， Well。

 I kind of want to case on my output， but my output is an exception。 So actually。

 let me just go ahead and do。List Max EXN on X's because Y I don't care， right， why if I ever。

Get an exception from this。 I can handle it because let's suppose that I have。Okay。

Let's suppose I have max like I that means that this thing has some element inside of it， okay？😊。

Well， if I have maps of Y。I would actually raise。I rera because I have to raise massive。

Suppose we have a max function that just like computes the maths。 I don't feel like doing the casing。

That's on why。This is to make sense like if I get a maximum。

 if there is a maximum in the tail of the list， my true maximum is the maximum of those two things。

 it's the same as what you've already seen， but now I put it back in the exception。

 I package it back up。But there's also another case。 What if this thing returns to me none。 sorry。

 not returning to me none， You think of it as returning to none。 It raises to me no max。Well。

 if I have no max in my tail， that is to say this is empty。I would say。No Max。Goes to raise。Max。Of。X。

Actually， sorry。 that's， this is redundant。 I could have。

Put this away or I could have so basically the idea is that this second case or this case。

 these are optional。 you have one or the other， if I didn't have this， I would do this。

 but because I have this， I don't actually need to do this。Sorry。I was thinking in my head， like。

 I know for a fact that that case was not actually on this slide。 And I was thinking。

 why did I do it that way， And it's because it's the right way to do it。 Yeah， okay。Kind of spooky。

 So do you see what's happening here。 This function only ever raises Max or nom。

 And if it raises Max it has that data， which means that any color of list max EF N can handle it to get the value out or can handle no max。

 So equivalently， equivalently， actually， let's， let's go even further。

 Let let me do the whole shoeang with you。 Okay， we can go in between these two things as I alluded to earlier。

 because I can just write my list max function。😊，Let's call it list Max。Opt。L equals。This Maxax E XN。

Give an L。 And then this whole thing is going to handle。 What it going to handle。If I get no maxs。

 I'm going to give back none。And then if I get max of x。I'm going to get sum of X。

We can define our regular optional type returning list max in terms of list maps raising in exception and actually that's a pretty common practice。

 I'll say if you want both versions， you define the exception handling a raising one person and then you handle that to get the option I mean。

😊，You don't divide a function that only returns data via exceptions， okay。

 but if it did raise an exception。Yeah。Any questions on this because this is kind of spooky。

 but and there's really no reason why you should want to do this like literally none。

 but it's kind of fun， I think。😊，Alright， that's listening to EN。 Alright， last remarks here。

Which is that there's nothing inherently wrong with exceptions。 they are gotos。

 which means they are ugly， it means that they are unclear， they are undescriptive。

 you don't want to use them all the time， but there are use cases because you might want to like do some error handling。

 you might want to just quickly write a function which can side effectively sort of get out of its context it's okay to use them when the preconditions are very clear。

 but just be careful because。Sometimes your preconditions like this right are not like this。

 but sometimes your preconditions are worth raising the exception。

 like as in you know very well that it's not going to happen so it's okay to write the exception raising version。

 but when it's less clear，Then just expandend the extra two or three lines。

 write the function that returns the option。 Okay， because an extra two or three lines of casing is going to save you pain later。

 Alright， this is basically the same sort of idea like null pointers。 Okay， It's like。

 use the data that you want to do。 right， Like， don't put it into the data that you return。

 don't rely on this exception stuff。 It's a similar sort of idea， okay。嗯。Yeah。

 and I already told you about the error handling thing， but'm yeah， exceptions are okay。

 don't use them too much， a little bit of a downer ending to this lecture， I think。😊，Yeah。😊。

I'm three minutes early， but I don't really have much else to talk about I'm walking at this point。

 so please fill us out if you have time， takes 30 seconds， I will take questions about CP。😊。



![](img/55e9d026d4209566a1c0b5fe115b4b2a_31.png)