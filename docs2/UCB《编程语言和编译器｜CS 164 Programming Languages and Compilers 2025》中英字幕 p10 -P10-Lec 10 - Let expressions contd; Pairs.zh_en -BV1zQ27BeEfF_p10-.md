# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p10 -P10-Lec 10 - Let expressions contd; Pairs.zh_en -BV1zQ27BeEfF_p10-

![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_0.png)

![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_1.png)

Alright， hello everybody。 H Tuesday。 I hope everyone is excited for what I'm sure is the best part of y's Week。

 where we get to explore programming languages and compilers land。

 I am certainly excited for what we're about to do。 I hope it will be just as fun for y'all。😊。

We are in the very exciting situation of adding pairs to our language today。

 So I think we'll have a blast with that。 But before we dive in on that。

 I want to real quick reflect on drill。😊，Huge， huge。 Thank you。

 As always so helpful for understanding what folks are struggling with not so much。

 understanding quite yet。 the big one this week， the stack still new totally makes sense。

 How are we interacting with it。 What are we doing with it。 All checks out， right。

 We are gonna keep thinking about the stack。 We are gonna keep thinking about how are we specifically interacting with the stack。

 So don't worry， we're not leaving that topic。 We're gonna keep getting practice with that even today。

 So hopefully that will feel more comfy soon， I want to quickly。😊。

Remind folks about a few things based on again， what came up in the drills。

 So one is everything that we are doing here in the class。 I know it can move a little bit quickly。

 Don't worry， you can revisit it any time we have the repository where you can just pull pull the compiler down and play with it on your own machine。

 do whatever you want with it。 it is available to you if there's something that you missed in class。

 you can go back and rewach the lecture video that's totally fine。

 but you can also just go back and look at what was the di Like what are the changes that we actually made in the class compiler。

 So if any point， you're like， I missed just that one bit。 don't worry about it。

 go back revisit that All good。 I also wanted to let's actually let's jump one down from this for a moment。

 Let's go to this one。 I know I mentioned this last week。

 But I know some folks are still like oh man， I Google for these X86 instructions。 There's so many。

 I don't know what to do。 And like on the one hand。

 it is super interesting to go see what the Internet has to say about X86 instructions。

 like you can end up on some really weird YouTube videos that are like 10 weird X 86 instructions。

 you've never heard。And those are fun YouTube videos。

 And you will probably have a good time watching those。 However。

 you do not need to do any of that for the purposes of this class for the purposes of this class。

 it is totally fine to just look at the reference that we have available to you on the webp page。

 You can just look at that。 You never have to Google for any of them。

 Never have to think about what other instructions might be out there because there are a lot。😊。

So feel free to ignore all that other internet information about posts。Okay。

 and now I'm going to talk briefly about our upcoming homework。

 which I am personally very excited about。 I think it's a lot of fun。 I will warn you all。😊。

So I have had people come up to me and say this is the hardest thing we do in this class。

 I've had folks come up to me and say this is the funest thing we do in this class。

 So like I hope that this homework is gonna to be an absolute blast for all。

 but we do have that little red flag next to it to warn you。 That is one of the harder ones。

 I know you're looking at it and you're like， oh man。 well that says two weeks。

 I'm not gonna think about that this week。😊，I understand I get you Nevertheless。

 maybe think about it this week， I think you're gonna have a better time。

 a happier time if you maybe start looking at it this week and in particular。

 that very last component of it is the thing that you will see folks say hey。

 you know what that was the hardest thing that I thought about the entire time I totally get it just maybe knock out all the other parts of the homework other than that last one this week just so you get a little head start and don't end up confused at the end so that's one thing that I would recommend。

😊，We will talk real briefly about that last section in a moment。

 But the other thing that I wanted to mention is that we have the courts provided reference interpreter。

So if you're playing around with his homework， like， man。

 I don't actually understand what should be the semantics of this construct。

 What should this language feature do。No worries。 You can find out。 Go ahead。

 write your test program， Send it off to the course infrastructure。 Find out right。

 You can submit it on the gradecope， and it will show you what the reference implementation says it should do right And so I know there are a bunch of classes like okay。

 like don't don't submit to gradecope too much。 Like don't overload the course infrastructure。

 Please overload the course infrastructure。 We' love that。 Send more test program。

 So the course infrastructure。 That's awesome。 It would be great to use that when you're。

 what should this construct。 Do we need to support that， You can come， you can chat with us。

 We're certainly happy to talk about it， But probably we'll just tell you to go ahead and test it out on the reference implementation。

😊，Does that all kind of make sense so far？Okay， cool。

 just to quickly sort of talk through the thing that folks end up。

strugglingling with I just want to like I want to tell you that this is coming up。

 I want you to be thinking about it。 This is what we are going to be introducing that ends up being one of the really hard parts of this homework right And so you can look at this and you can say。

 okay， well， it kind of looks like okay， maybe we could just have this be an if oops this could be an if and then that's another if and we just sort of go through and we could do that。

But then we would have a linear time solution to this process where， in fact。

 we are going to want something constant time。Pretty weird， Pre wacky。

 So that's the thing that's gonna make it a little bit hard。

 And we're not gonna ask you to do any of the stuff that a real optimizing compiler would do， right。

 So a real optimizing compiler might say， okay， well。

 we're gonna go ahead and have all of these work in the constant time way。

 but we're gonna go ahead and carve this off to be done with an if It is gonna be a special case。

 And then all the others are going work a different way。 Like it might make some kind of nice。

 fancy idea about what is going be the most efficient way to implement this。

 We're not gonna be doing that。Right，We're just going to ask you to go ahead and I。

 I'm not telling you anything that's not already on the reference， right。

 So you're gonna to be able to read all of this on the specification。

 I'm just trying to call your attention to it early in the hopes that you actually start early。Okay。

 I think those are all the sort of logistically random things that I wanted to call people's attention to。

 but let me make sure I haven't forgotten anything， let's see。嗯。Yeah。

 don't hesitate to run stuff on gradeco。 Red flag emoji to remind you that it is going to be。 I mean。

 there's， there's， there's multiplication division。

 Those are both gonna to be a little bit tricky because of negative and positive。

 So there's gonna to be various things that I think you're going to need to think about， so。

Just please， please， please， start early。Okay。Cool， in that case。

 I'm going to go ahead and move on to reminding us what we were doing。Basically last time。

 because we are going to start by running through a couple of examples。

So I'll quickly preview what we're about to run through here。

So this is one of the examples we're going to run through。

 we have our nice little lead expression right here。

 we have another little lead expression right here。

 but I think it's going to be easier for us to understand what this assembly is doing if we first take a look back at the compiler and remind ourselves。

 what are we in fact doing？😊，So let's take a look。That a compiler。

So we had went ahead and added one big new change， which was we made a symbol table available。

And in particular， this was a mapping from names to integers。

 and what I want you to discuss with folks nearby for 30 seconds right now is what does that integer represent？

What does that integer represent？ And you can see everything we're doing with lead expressions here。

 if that helps you remember。What that integer represents。Go ahead and chat for 30 seconds。

The question is in our symbol table， which maps name to integer in the compiler。

 what does the integer represent？All right， so what does that integer that we're mapping names to。

 what does that integer represent？I love it。 So this is the way that we're actually going to be able to access the thing。

 the value associated with that name and how are we going to do it while we're going to go into a particular offset from the stack right And so if we look at how we're actually using that value right what we're doing is we're saying。

 okay， for this name， this particular name that I'm getting as the the thing that we're mapping something to。

 I'm going to go ahead and add to the symbol table， the stack index， right。

 So the offset from the base of our stack where I have previously placed that value。😊。

So the thing that we do is we generate all of the assembly for actually getting the value associated with E into RAX。

 and then once we have that inside RAX， we say， okay。

 take whatever is inside RAX and put it at this offset from the stack from the base of the stack。

And then then after that， go ahead and compile the body of the lead expression。

 but do it with a symbol table that maps the name there。

 the name that maps that to that particular offset from the stack so that now going forward if I try to actually access that name。

 I'm going to go and I'm going to know where on the stack to access it。

 And so in particular we can see down here， that any time we encounter this name。

 and we know that this name is actually inside the symbol table。

 then we know that we can go ahead and find in the stack right。

 based on going to the base of the stack and then counting upwards to the index that was actually stored there。

 I'm going to be able to find the value associated with that name。Oh。

 I think I understand this question。 So this question is about。This， and it's saying， sorry， no。

 it's about this。 It's saying I am able to go ahead and just count upwards from the base of this stack to the stack index。

 right， the thing that was actually stored in the same table in order to find the value。

 And so if we take a look at what stack address is doing。 that's exactly what it's doing。

 It's saying that RP is the thing where we have stored。

 That's the register where we have stored the memory address of the base of our stack。

 And I'm just going to go ahead and offset based on whatever argument I got here。

Does that make sense？It's negligible。Okay。Do we have other questions about what we have done？Yes。😊。

Does this cover。 Oh， I love this question。 Does this cover if our variable isn't in our table。

 So say we try to use a name that we haven't actually mapped to anything。

 So what would happen if we go ahead and we have a program where we've introduced names X and Y。

 and then we try to use something named A。 What will happen。

Go ahead and discuss that with folks nearby for 20 seconds。I think that's a great question。

So why are we getting bad expression when we try to use why？Well。

 if we look through what is the case where we actually do go into this case is the case where we see a name right。

 so maybe we see this name Y it was a case where we see the name but also we are requiring that name is actually a member of our symbol table right so if we see a name but it is not a member of our symbol table。

 we fall all the way down through all the cases right。

 it doesn't match with any of the cases and we raise that expression。That is what actually happens。

Great question。We have other questions about what we're doing here。Okay。

 I'm going to revisit a topic that we considered the end of last class。

 but we were a little bit rushed。 And so what I want us to think about is this error that we just saw。

Is that a compile time error or a runtime error discussed for 30 seconds？All right。

 hum if you think this is a compile time error。H if you think this is a runtime error？Yeah。

 so this is really interesting right So this leads us in fact。

 to a follow up question of when does the symbol table exist because what this is saying is we are going to get this error because we are going to figure out that when we try to run dotmm on our symbol table。

 we actually we don't find that name in our symbol table。

 which means that we fall through to this case where we raise an error。

So this is a check that we are doing either at compile time or at runtime。

 My follow up question to y'all is， does the symbol table exist at compile time or at runtime for a compiler？

Go ahead and discuss for another 30 seconds。All right。

 hum if you think that the symbol table in our compiler that it exists at compile time？

H if you think it exists at runtime？How did you think both？I'm a fuing Niller。

I'm glad no one thinks neither Yeah， so this exists at compile time right。

 We have this file compiled on Ml， just a normal Ocal file when we are running this Ocal program。

 we have access to this thing tab which is our symbol table。

 this exists at compile time right by the time we are actually executing the program which is to say this all of the information we need out of that symbol table has been baked into the assembly right anytime we're going to be using one of those offsets like yeah。

 we see that baked into the assembly but that's not actually going to be represented in anything that is a symbol table that exists at runtime。

😊，What we have is this compile time value tab or symbol table that we are using。

In order to figure out for any given sort of textual section of the program that we are given， right。

 if we're looking at this particular line， are we going to have access to this particular name。

And we can actually make that decision just by looking at the text of the program。

 we don't need to be currently running the program in order to figure that out。

 and so at compile time， when we are actually generating the assembly that will correspond to accessing a given name that is when we figure out if our value is actually going to be available to us and that is the time when we will check if it's in the symbol table and if it's not in the symbol table。

 then at compile time right this is an Ocal error at compile time we will raise a compile time here。

Are there questions about that， yes？Let's take a look at line 47 again， absolutely。So here we are。

 And what's happening is we have seen the usage of a given variable right so maybe it's something like here。

 we are trying to actually just use something that has the name X。

 if that value X does in fact appear in our symbol table， we go into this case if it is。

 in fact a member member is from member if it is a member of our symbol table。

 then we go down this case， and we say， yep， I know the assembly that is going to get that value into RX。

 it's the thing that actually moves from the appropriate offset into the stack moves whatever is sitting there into RAX that will be the assembly that is involved in getting that value into RAX On the other hand。

 if it is not a member or symbol table， that means no one did the let binding that would give us access to that name。

 which means that's the name we shouldn't be allowed to use and we should raise an error。2。

What else are we thinking about？Fantastic， in that case， let's go ahead。

And go through a couple examples of doing this。 So here we are with a relatively simple program。

 It kind of looks like what we were just actually running with the compiler。

 Let's just walk through real quick。 What's going to happen。

 So the first thing we're going to do is we've got our value that represents the value 2， right。

8 is our runtime representation of 2。 Let's go ahead and put that inside R E X。So' far so good。 Now。

 because this is a name and we want to be allowed to use it repeatedly， right。

 this is something we're going to have to keep around for a while。

 we are now going to go ahead and write that into the stack at the next available slot。

 the next available slot is this one， RP -8。 And so we're going to go ahead and write 8 into there。

So far so good。 Now we're ready to move on to our next value。 Let's change our color。

 So we've got this， which is our runtime representation of three。

 Let's go ahead and move that into RAX。Okay， so far so good。

 And now we're going ahead and moving that into the next available slot on the stack。 Now。

 this is a little bit weird because we didn't actually map 3 to a name。

 So what I want you to discuss for 20 seconds right now is why are we moving that into the stack。

It's okay， if you don't know， just think it through。

Okay so hopefully some of us are vaguely remembering that when we implemented edition。

 we figured out that we're gonna have some intermediate values right So if we just tried to save stuff in registers that might work if we only had 16 intermediate values But on the other hand。

 if we have more than 16 we run out of registers and so we figured out that in order to actually implement our addition what we would do is we would figure out the value associated with that left operaand we would get that inside reX and then once we had that in reX。

 we'd go ahead and save that off to the stack so that then we could go ahead and figure out what's associated with the right operaand and we could use all our registers in order to do that。

 And so that's why we were actually saving this value off into the stack。

 not because we were actually binding it to a name， we don't have a name for that value。

 but because that is left operaand for our addition and we want to make sure that we save that we keep having access to that so that when we are ready to actually add together the left operaand and the right operaand of our addition we will have that available So we've save that off into the stack so we can do our addition later。

Okay， what's next。 Well， now we're ready to actually start doing some of that addition。

 So now let's go ahead and take the thing that is associated with our right opera and。

 which is to say。This value， right， the value X。 Let's go ahead and take that and put that inside。RX。

 so let's cross out what we've got in there right now and let's put in what we have right here。

 right？And now we're ready to go ahead and actually cross off that one and now we're ready to say okay。

 and we also want the other opera end available to us。

 so let's go ahead and write 12 into our register R8 and now we are ready to add those two together。

 which is to say we're going to go ahead and get 20 into REX。

 which is of course the runtime representation of5， the answer for our program。

Any questions about how that all worked or we feeling pretty okay？Cool， in that case。

 let's do one that's a little bit more complicated。 So here we've got actually， you know what， let's。

 let's first do a task where I want us to think about where is the the value associated with the name Y。

 What offset in the stack is that going to be stored at So I want you to go ahead and think about this with a partner。

 discuss it for a minute， And I want you to make a prediction is that going be stored at offset negative 8。

 offset negative 16， offset negative 24， somewhere else。 talk it through。All right。

 it's okay if we're not totally sure。But let's hum if we think we'll be at offset negative8。

Let's tell if we think offset negative 16？Well， some of we think offset negative 24？Well。

 some if we think anything else？Okay， cool。 It's all well and good to guess。

 but we don't have to guess we have the assembly for us right here。 Let's take a look。

So we're going to walk through what's happening and why I've tried to highlight this according to the assembly that sort of represents the different parts of the program。

 so here this is the assembly that is or sorry， this is the assembly that's going to correspond with this component。

 this is the assembly that's going to correspond with this component and the assembly that we see in black is the assembly that's going to correspond with the addition that we're doing。

So let's go ahead and walk through step by step and think about what's actually happening。

 So the first thing is we want to get our runtime representation of one in。Okay， so far so good。

 we're gonna go ahead and save that off right， We're mapping that to the name X。

 So let's go ahead and put that in the next available slot on the stack。 makes sense to me。

 We are now ready to go ahead and get whatever we have there back into ourx not super exciting。

 but that's because we need to get it back in order to actually do our add1 operation。

 So let's go ahead and cross out what we had there before and write in the thing that we had stored on the stack。

 And then let's go ahead and add it together with the value for。

 which is going to go ahead and give us 8， which is to say our runtime representation of the value2。

😊，So far so good with our blue colored assembly。We like it。Cool， all right。 so so far。

 we have used one value， one of our slots on the stack。

And that's because we were doing this mapping to the name X。

So what happens now now we're ready to do something that is actually generated when we are generating the assembly for our addition and what is that going to do。

 Well， it's going to say whatever we currently have inside REX。

 which is to say the thing associated with the left opera of our addition right whatever we currently have in there。

 let's write that into the next available slot on the stack and here's where things get a little bit wacky right because what is the next available slot on the stack。

Is it at offset negative 16， I it an offset negative 8？It's at offset N 8， right？

 We have now moved out of the portion where we should be allowed to access the name X， right。

 It is only in this blue highlighted portion that we should be allowed to use the name X。

 which means we're ready to stop saving that on the stack。

 We no longer care about what we have put on the stack before in order to run all of this。

 That's done with now。 That's over。 We now have that slot available to us again。

And so now we're ready to say you know what， ignore whatever we had for x。

 we're not allowed to use x anymore， let's go ahead and put in the value 8 that is what we currently find inside REX。

Are we comfy with that with the fact that we were able to reuse that slot， yes？

Our parentheses is affecting。Oh， okay， so this question is about why do we know that we're able to overwrite this。

 And that's because of the semantics of our let， right the way that our。

 our let works is we know that we are only allowed to use this name X inside the body of the let expression。

 right， That's the only place where we should be allowed to use it。 If we said， you know what。

 if we have introduced X once。 In fact， we will retain the the access to it forever。

 that is a choice we could make。 And then we would not be able to reuse this stack slot。

 But what we said is， no， only inside the body of the let。

And now we're done with the body of the lead， so that suck slot becomes available again。

I love this question。 So this question is here， we're doing all this stuff that's associated with getting the value of our left opera brand。

 And then we have something associated with doing the plus sandwiched in the middle。

 Why did that happen？ So let's go look at our compiler to find out exactly why that happened。

 So here we are in our。😊。

![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_3.png)

![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_4.png)

Implementation of addition， right， we said， okay， I want to get the value associated with E1 inside RX。

 And then I want to go ahead and make sure that I am saving that somewhere where I can't colborate when I do the next thing I want to do。

 which is to say getting the value associated you with E2 inside RX right So this is the left operaand line。

 This is the right operaand line in the middle。 I have to do something that make sure I get whatever I put into RX so far and put it somewhere safe。

 And so this is the line。 that we're actually seeing right now highlighted in black。😊。

I think I understand this question。 So I think this question is saying， hey， in this situation。

 we know that what we're going to be doing is also adding in this value。

 whatever is associated with Y and also adding one so we could just be sort of continuously adding to whatever we have in RX。

 but we don't actually know what is going to be involved in calculating this operaand， right。

 like maybe we're doing something totally wacky out here where we're doing a bunch of random multiplication or the first thing that we see there is something that we're actually reading from the user。

 like anything could be happening inside this right operaand and our strategy still has to apply。



![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_6.png)

And so what we know， the only thing we know is that we want to get the value associated with something that appears on the right of our edition。

 and once we have that value， we're ready to go ahead and add it。

There's all kinds of stuff that we could be doing over on that side。 Maybe we're calling a function。

 we could be doing anything。Does that make sense？Exactly， exactly。 yeah。

 we have this general purpose strategy for how to do addition。So far so good。Cool， okay。

So now we've gone ahead。 We've saved off the value associated with our left opera and We're ready to do the thing associated with saving Y。

 So let's go ahead and do that。 So now， whatever we have an R E X。

 let's cross that out and let's instead get the value 8。

 which is to say our runtime representation of two。 that is coming from。 Let me highlight for us。

 That is coming from right there。😊，That's what's being represented inside R X right now。

 And so what are we going to do next。 Well， we're going to go ahead and say that in the next available slot Now we do still need to preserve that left opera end of our addition。

 So the next available slot is going to be that offset negative 16。 And now we're saying， okay。

 we're ready to do our add1。 Let's go ahead and move what we have at offset negative 16 into reX。

 So let's cross that what we have before。 put in 8 turns out it's the same thing。

 but we don't know that right， we're making the general purpose solution。

 And now we're ready to go ahead and oh sorry， let's cross that out。

 Now we're ready go ahead and add one to that will'll get 12 fantastic we've got that value inside rex。

 Now this is the value that represents the whole right opera end of our addition。

 We are now ready to actually start doing the addition。

 So let's go ahead and look at the spot where we saved the left operaand right， So right here。

 and let's put that value inside R 8。 Now we can go ahead and actually do our addition。 we get 20。

 which is to say the runtime representation of。😊，five。

Which makes sense because what we're doing is we're adding together two and three。

So those of us who guessed aha， negative 16 is the offset where we will say why。

 remember this is why。You are correct。 That is， in fact， where we put why。Okay。

 do we have lingering questions about pairs or sorry about lead expressions or do we feel ready to move on to pairs？

Yes。😊，发生。Like Z was just set there。It would still。We would still only need 6。

I think I understand this question， I'm not totally sure I understand this question。

 so this is saying， what if we had an additional lead expression wrapped around this yellow highlighted lead expression？

Would we still need only the registers that we had available or would we end up using another？

Is that the question， Okay， so let's actually run something in order to see that in action。

 I think that will help us think it through。 So let's say were doing something quite similar to what we are doing right now where we said。

 okay， I'm going to do addition。 and I'm going to do let X1。Add1 x。Ill close that let， and then。

Let Y2。Add1 x。Close that， let's make sure that all oops。What have I done。

 I used X where I should have used Y。Okay， great。 So this produces the program that we just saw。

 And now what is the specific modification to our program that you are interested in。Okay。

 and so we're wrapping a new let around this let。 and what are we doing in that let。

 are we mapping Z to something？Okay， great， let's map Z to three and we're not planning to use Z。

 we just know that we're going to state that onto the stack， we want to have access to it。Okay， yeah。

 So we do， in fact， use another one。 So why is that。

So if we think about what is actually happening in this program。

 even though we as the human programmers， know that we are never going to use this name Z。

That is not a given。 And again， we're trying to make this general purpose solution。

 And so the compiler says， okay， I guess I've got to save this value3 somewhere on the S。

Can we set Z to。I see。 Okay， so we don't want to have it B 3。 We want it to be add one， applied to 2。

Is that right， And so now let's make sure we're closing everything properly。

 So now what do we want to have in the body of that lead because we do indeed need to have something in the body of that lead。

So now this closes the body of this let， and then we're closing mapping Z to the value3。

 and now what do we want to have in the body of this let？

That we actually add to our our left off brand。Another add one。 Add one。five。

 it's getting to be a lot of parentss。Is that what you were or were trying to figure out， okay。

 great， Okay， good， good， good， okay。Other questions about this， or we feeling。Okay。Amazing。

 let's start talking about pes。

![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_8.png)

So。We are going to be adding。

![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_10.png)

Some exciting。New constructs today。So for those of you who have ever used Lisp。

 I think our new constructs are actually going to look pretty familiar So you will have seen them by other names。

 right so you probably saw this as cons。 probably saw this as car。 you probably saw this as kudar。

 And so these are kind of wacky names。 Cons was for construct right， constructing a pair。

 Probably not super surprising。 Car actually meant contents of address of register。

 That's what car came from。 made a lot of sense to the people who were implementing this language at that time。

 right， they were thinking about registers， right， this was coming from people thinking the way you are all now thinking。

 they were thinking about okay， well， yeah， this is the thing that's going be in there and then Ker came from contents of decrement of register。

Which again is gonna make a lot more sense to yall at the end of today's class session right They were thinking about specifically they were thinking about implementing this on I think it was an IBM 704 with vacuum tubes。

 and they were like trying to figure out okay， how am I actually going be representing these pairs in this。

 How am I going lay things out in memory。 they eventually tried to switch to using the terms first and rest instead of car and cutter And by that point。

 it was too late。 Everyone was already wedded to car and cutter and had adopted that。

 And that's how they thought of it。 And no one was willing to switch to first and rest。

 we are going to be using left and right to refer to those ideas。😊。

And so I don't think pairs are going to be super surprising to us。 We can have a pair。Pair one， two。

We can use left on that， and that should give us one。If we use right on that， it should give us two。

 the really exciting thing for us is going to be that we can now build up。Listists。

 so we can do pair。One pair。To false。And by nesting our pes in that way。

 we now have a representation of the list one， two。Any questions？About these。

This is a representation of the list one too because we are going be using false most of the time as though it is signaling the end of the list。

 but look you， the programmer， can choose to use it however you like。

 right you can absolutely choose to do something else that would just be a convention that you the programmer might adopt。

Yeah， not us the compiler writer， but the programmer using our language。So far so good。

 we feel comfy with this。Amazing， okay， so let's go ahead and implement this really quickly in the interpreter。

 It's actually going to be really fast。😊，And then maybe we'll take our little break。

So here we are in interpret。 Ml， what are we going to actually need to do well？

Who here thinks that what we are going to want to use to represent a pair that we should represent it as a number。

 Hu， if you think we should represent it as a number。Who thinks we should represent it as a Boolean。

Who thinks we should make a new constructor。Yeah， I have to agree， right。

 It's not obvious how wed actually use a number to represent our pair。

 It's not obvious how we would use a Boolean。 I think let's do our standard trick of making ourselves a new constructor。

 So let's do pair of value。Value， which means we now have our nice recursive type。

 we're going to go ahead and actually make this recursive so that we can call that recursively so let's make one case for pair。

Let me remind myself what we actually do in there， so we want to have pair。V1。Fu。

And we're going to want to go ahead and actually call it recursively。 So print F。Dot sprint F。Hair。

And what do we want to call that well string of value applied to V1？

And string of value applied to V2。So hopefully that doesn't look too wacky right。

 we're going ahead and just seeing what will be the string associated with the left item of the pair。

 what will be the string associated with the right item of the pair probably looks pretty okay。Cool。

 now let's actually make one of these。 So over here， we can go ahead and say， all right， if I see。😊。

The symbol pair。I am going to be ready to make one of these things。How will I do it， Well。

 I'm definitely going to want to make something that has this new pair constructor。

 right that's something we've just added for exactly this reason。 Let's go ahead and call Inter X。

 remembering to pass in our new environment thing。 Let's go ahead and call that on E1。

And that will be a good sort of left item of our pair。 And let's also go ahead do the same deal with。

Y2。And then we have a nice representation of a pair。Let's real quick implement left and right。

 I don't think this is going to be super surprising either， but let's go ahead and just see it。So。

 Sim。Left， and that's just going to get applied to a single value， right， because remember。

 we are going ahead and just having the the pair be the only value coming in here。 And， in fact。

 we only actually know what to do with this if it is a pair。

 So I'm gonna have us go ahead and do our match right here。 So let's go ahead and say match。

Interp X applied to E with。If it's a pair， we know what to do。Lii。Undersre。

 we don't care about the thing on the right。 We just want to produce fee。

 if we have anything other than a pair， that's the case where we say。No， thank you。

And we'll apply that to X。Okay， what did I get wrong with my。Syntax here， can y' all see it。

 I'm not seeing it。oh， I failed to pass in my environment。 Remember。

 we must pass in the environment now。 Yeah， okay， good catch。 Great。

 So now we've gone ahead and provided all the arguments that inter wanted。

 And so the thing that this is doing is just saying， okay， whatever we are applying left to。

 Let's figure out what it is。 So let's call our inter X。

 let's make our recursive call to inter X in order to figure out what that is。 If it is a pair。

 we know what to do with it， we just grab out the leftmost thing。 If it's anything other than a pair。

 we don't know what to do with it。 Let's do almost the exact same thing for right， except that。😊。

We're going to go ahead and ignore the thing on the left。And only care about the thing on。Right。

Why are we implementing pairs and not tuples， We could also implement tuples and nothing stops us from doing that。

It's not going to teach us anything particularly more complex about how to write our interpreter and compiler。

 so pedagogically， it's not that interesting。We could。 We totally could。Other questions。Okay， cool。

 let's see a couple quick examples in the interpreter。And。Then we'll take our little break。Okay。

 we've got a pair。Let's call left。How about right？How about if we want to have a whole list？Go。

Any questions about how our interpreter has made pairs happen or were feeling really good？Okay， cool。

 So what I want us to reflect on as we take our break as we grab our water as we you know have a little bit of a stretch is we're now going to try to do something really similar to this in the compiler right。

 We're going to go over here。 We're going to try to do something that looks a lot like that in some ways。

😊，So normally what we would do is we would say， okay。

 the role of our new case in compile X is to get the value associated with this thing inside RAX。

So REX is a 64 bit register。And what I want to do is get the pair that represents pairing together E1 to E2 inside that 64 bit register。

Now this is weird because E1 is a value， which means it's something either a boolean or a number so far that takes 64 bits。

 and E2 is another thing that also takes 64 bits。This is going to get weird。

Reflect on that as we take a five minute stretch break。See you at。432。Definitely。No problem。Is this？

やぱそ。Yeah。Where we added our new constructor for the value。We've got pair left and right。哦。😮。

Take talk。是什么么。

![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_12.png)

あ上できたい。All right， so I've gone ahead and written part of our implementation prepare in the compiler。

 it's the very boringest part， but it will help us think about why this is weird right so all is happening so far is we're saying。

 okay， go ahead and emit the assembly associated with getting the value of E1 into RAX。

So we're going to get that 64 bit value that represents the value associated with executing E1。

 We're going to get that into REX。And then we're going to go ahead and save that off to the stack。

 right， because we want to make sure we don't overwrite it。 Sure。

 then we'll go ahead and we'll get that 64 bit value。

That is being used to represent the value associated with executing E2。

We'll go ahead and get that inside RAX。And now what。

Right we can go ahead and grab back what we saved off before。

 so now we have the thing representing the left side of the pair inside R8。

 we have the thing representing the right side of the pair inside RAX right that's okay。

 but what do we do now？And so we have recently been introduced to a new friend in our cast of characters。

 we might think to ourselves， maybe we could go ahead and put this on the stack。



![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_14.png)

RightMaybe we can do something where maybe we're putting that left item at one spot on the sack and we're putting that right item at another spot what I want you to do is go ahead and use these sample programs to brainstorm with someone nearby for about a minute can we put。

Our pairs， in fact， may be， in fact， our lists on the stack。Go ahead and chat about it。 okay。

 if we don't decide， then I want us to chat about it。So what do we think。

 go ahead and hum if we think that we can put this on the stack。

Go ahead and hum if we think we cannot。Okay， so we have some uncertainty I think that makes sense and I want to sort of talk us through what's going on here。

 So for the first two examples that we're seeing， everything basically looks pretty much fine right like you can imagine taking two slots to represent a pair that seems okay but then things start to get a little more complicated around this third example right so depending on which branch of this if we go down。

 we might have a pair that is going to take four slots of our stack。

We're going to have to have one that represents sort of this outer pair and one that represents this inner pair。

Or。We might have something where we're just taking two slots。I guess this might be okay。

 it's a little bit weird because as we've talked about。

 we do need to know what is the next available stack index at compile time and we don't necessarily know at compile time which of these branches we are going to take。

It's actually a little bit complicated at this point。

 Maybe we could do something wacky where we go ahead and we we start actually saving up some kind of analysis that we do of the entire thing and we say。

 okay， well， the biggest amount that it could possibly use is going to be this branch。

 And so let's like carve that out regardless。 Like maybe we could start to do something a little bit wacky。

 We've never done anything like that before。 We've always been able to just sort of consider things locally in the past rather than having to know something else like that。

And then we get into an even worse situation down here， right。

 So here we've gone ahead and we have made this pair。

Using something that we have available during the execution of the body of our let。

 right so we have access to this X thing in there。And then we go ahead and we put that inside the pair。

And this pair is supposed to be our return value， right。

 This is the thing that we are actually getting back as the answer associated with executing our let。

 We should be able to go ahead and access the left thing of whatever we get back from this let。 But。

 oh man， we said we can only actually access this value that we have bound to one inside this body。

 And so if we've gone ahead and actually blown away what is coming out。We're in trouble， right？

And so this really gets at the idea of when should we be using the stack versus when do we maybe want something else？

 And so when we want to be using the stack is when we know exactly how much space we're going to need So that relates back to this idea if we'd better be actually tracking that stack index and when our values are going to be shortlived right。

 if it's going to be a problem， if we blow away this thing。Then we're in trouble。

And so does anyone happen to know another character in our cast of characters we might want to bring into the conversation at this time？

The heap， I love it。 absolutely。 So the heap is a great thing for us to be using when we have something that is gonna to be longerli or we don't know exactly how much space it's going to take。

 And it's going to be a little different right， in the stack。

 We've been able to just track at compile time。 Where are we on the stack。

 What slots are we using for the heap， We are not going to be doing that。

 We are not necessarily going know how much space we are using in advance。

 And so we are actually going be tracking at runtime。

 What is the next available slot on our heap at runtime。😊，It's going to be a little different。

Great question。 So this question is， where is the heap relative to the stack。

 And so we've got low memory addresses up here。😊，Low numbers。 We've got high memory addresses here。

 right， So it's still exactly as though we are looking at our computer's memory just laid out from the low number。

 we're starting counting at 0， all the way down to the highest number available in our memory。

 And so our heap is gonna be growing in this direction。

 If we remember the stack is over here growing in this direction。

 And so you can imagine them meeting in the middle。

 that's sort of the mental model that we want to have in this class。 obviously， of course。

 it's actually much more complicated than that， right because our program must actually live somewhere。

 that's got to be represented somewhere。 There instructions somewhere in the memory of the machine。

 So there is actually more going on。 In fact， when we implement this in a moment in the compiler。

 we're gonna to see a little bit about what's going on where we might actually get our heap。 But yes。

 what we should be thinking about is the heap is growing down and it's growing down that way。

 The stack is growing up that way。 And sort of they might meet in the middle when they run out。😊。

Makes sense， cool。Okay。I'm going to tell us a little bit about how we are going to interact with the Heap。

 which is we are going to go ahead and store the pointer to the next available slot in the heap in a registered named RDI。

So we'll have RDI plus 0 pointing to there。We'll have RDI plus 8 pointing to there right for the stack。

 we're subtracting eight for here， we're adding eight right RDI。Plus 16， pointing to there。

And that's how we're going to be interacting。With our heap， do we feel pretty comfy with that so far。

Okay， cool。 So now I'm going go ahead and have us look at how well actually represent pairs on the heap。

 And I don't think this is going be super surprising to y'all right like we're kind of thinking already about the fact that the thing on the left takes 64 bits。

 The thing on the right takes 64 bits。 Maybe we can use two slots for those。

 So let's go ahead and write out our representation of in fact。

 I'm not even going to write out what our actual representation was。 obviously。

 what the computer is actually seeing is just ones and zeros。 but this is going to be runtime。😊。

Reap of one。Run time。Rp。Of。True。And that's what we're going to go ahead and have in there in order to represent this pair。

 Now， I like a lot of what we're doing here。 We have definitely saved the values associated with our left and our right。

 However， the thing that we always promise that our compiler is going to do is make sure。😊。

That we have actually stored a representation。Of the expression inside R X。 And right now。

 I'm not seeing that。 So what is something we might like to put inside RA X。

In order to actually do this， go ahead and chat with someone nearby for about 20 seconds。Yeah。

 an address is just 64 bits of data。Al right。 so I think folks are。

 are landing on what I hoped you would land on。 But does anyone want to shout it out。

I'm hearing address。 I totally agree， right。 We do have something that would tell us how to access this pair。

 We've already， in fact， got it represented right here in RdiI， right。

 That RdiI is pointing to this spot in our memory。 This is just an address is telling us that at that address 0。

 we can go ahead and find the thing that's on the left of our pair。

 and we can know that if we add plus we can go ahead and get to the thing at the right of our pair。

 so that is all good for us， let's copy what we see here in RD I into R X。

 let's go ahead and do one other change here， which is right now I have left it so that remember I said that what we are going be doing with Rdi I is treating it as the pointer to our next available slot in memory。

 If I leave this at0。 I am now going to allow our own selves to later on overwrite what we have in here。

 I would not like that。 I want to keep this pair around。 I would not like it to be overwrittend。

 So let's go ahead and cross out what we currently have in R DI。 And let's replace it with 6。😊。

Which is now the next available slot in memory。Other questions about this？Yes。😊。

Are we ever gonna be able to free that memory。 I love this question。 So way， way。

 way at the end of the semester， we're gonna have a class session on garbage collection。

 which is gonna to be a really fun one。 So actually。

 this is a really good thing to think about because right the way we've been interacting with our stack。

 we have been decrementing that stack index when we sort of go back up through our As T。

 we have been getting back to sort of a higher point of our S expression and going back to a lower stack index and being able to reuse these stack loss。

 the way we are going to interact with the heap， we're not gonna do that。

 so it's not until we get to garbage collection day that we think about that。 Yeah。

 we're just gonna be leaking memory left and right。😊，Okay， allright， so let's， let's start on this。

 we might， we might run into some issues， but let's at least start on implementing this in our compiler。

 So I think we now have a pretty good idea of kind of the first thing we want to do。

 So let's go ahead。

![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_16.png)

And。Start our moves， let's move。Mm offset。 Let's move whatever we have right now inside R 8。

 which is to say the thing associated with the left value of our pair。

 Let's put that at whatever slot is the next slot available to us。 So let's go ahead and do。AD I。

Alsoff that was 0， right， let's go ahead and just say whatever it is that's currently an RDI。

 that's the spot where we want to go ahead and put this。

And remember that we had previously stored the value associated with E1 inside RAX and then we said take whatever's inside REX。

 put it in this spot on the stack and then just recently we read back in from that slot on the stack we put that inside R8 and now we've gone ahead and moved that into the next available slot on the heap so that's what has happened so far。

What next， well， we want to go ahead and do sort of the same thing。

 but with the value associated with the right and we want to do it eight bytes later。

 so let's have that be our offset right there and let's go ahead and copy in the thing that's in RS instead of the thing that's in R8。

What next well？And we want to go ahead and do。So we said that we have to get something inside RAX that is going to represent。

Our value， right， And so our value now is the pair。

 The thing that we've decided is going to be a good representation of that pair is the address and memory where weve stored that pair。

 right， that， again， is just 64 Bs of information。 It's totally fine for us to have that memory address be the thing that is representing that。

 And now let's go ahead and make sure that no one else overwrites the slots on the heap that we have now used。

 And so let's go ahead and do。For RDI， where we are storing the next available slot on the heap。

 let's add 16 to make sure that going forward， we don't try to write over what we have already written in there。

Now we're getting really close here， but there are actually two lingering issues with how we have done this。

I want you to go ahead it's okay if you don't come up with them。

 but I want you to go ahead and spend about the next minute。

Thinking what could go wrong with this representation， what are we doing wrong so far？

I'm going to swap us back to the slides and maybe y'all can keep brainstorming。



![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_18.png)

So does anyone spot？Any issues based on maybe what I have highlighted， for example？Yeah。

It has to do with the tag， absolutely。 So one of the problems that we're going to encounter is if we recall those last two bits being zeros。

 that's exactly the thing we use to represent that this value that we have is a number。

So if we just go ahead and take in this memory address0 and we pop that inside to RAX， RAX says。

 great， we have the value0 inside RAX。Sounds good。 We can do the exact same thing here。

 and we'll get our value。 I guess that would be4 right。

 because we're expecting these two to be the tag。 And then we've got our or actually our value 2。

 Yeah， we've got that represented there。😊，And so why is this happening， right。

 This isn't sort of coincidence that we've got these zeros appearing at the ends of all of these memory addresses。

 It's because they are multiples of8， right， if we are going ahead and having multiples of 8。

 Of course， we are gonna have three zeros at the end， that's sort of the whole thing。

 right And so if you remember a while ago when we enter a little activity。 And we said， okay。

 whatever tags we're going to use for various things。

 we're going to expect that we are going limit it to three slots。

He you have now discovered why we are going to take advantage of the fact that these are always going to have three zeros open to us at the end。

 and we are going to apply the tag there。Now， why can we not do our normal thing of just shifting left in order to make slots on the end。

 right， That was okay when we were doing numbers。 We were like， okay， yeah。

 we're gonna overflow a little sooner。 but that's all right。 we had overflow anyway。

 in this situation。 That is not okay， right， These are memory addresses。

 These are addresses of our particular spot in our computer's memory。

 If we go ahead and shift that left。 And we lose something we need on the other end。 suddenly。

 that pointer doesn't point to the spot that we're actually trying to point to。

 So we cannot do our left shifting trick for this and we're going to have to take advantage of the fact that these are just going to be zeros。

 plus you。Are there questions about that or were feeling kind of okay about this。Yeah。That's okay。

I love this question。 How does it handle having pairs of pairs， So say that instead of。呃。

Say that instead of true being our second thing， What if instead we had another pair there。

 Do we have a way of representing that second pair in 64 Bs。We do now， right。

 So we have this whole trick of saying， okay， yeah， this is fine， right。

 We're gonna go ahead and have our memory address。 We're now gonna add the the tag associated with pairs to that memory address。

 But basically something representing that memory address。

 And that's a way of representing our pair in our 64 B slots。 And so we could go ahead。

 And instead of writing the runtime representation of true， right， the address associated。😊。

With another。Pair。Oh， okay， I think I understand the question。 So this is saying。

 if we went ahead and made a pair in this way， would we have the inner pair appearing first in the heap or would we have the outer pair appearing first in the heap。

 Is that right？ Yeah， it would be the inner pair。 So if you take a look at what we're actually doing inside our compiler。

 you can see that what we are doing is first， we get the values associated with E1 and E2。

And then we go ahead and make a pair out of them using these instructions。

 and so what we would do is in the case that we were just talking about where E2 represented another pair。

 we would first figure out what that value is so we'd get that value inside RAX。

 and then we would go ahead and make a pair using those。

So that means that the one associated with E2 would appear earlier in the heap， great question。

Other questions are so far so good。Okay cool， let's quickly just change this so that we are no longer representing RX representing an R X just this bare address because again。

 that's going to look like the number 0。 So let's go ahead and change it from right before was something like Why is my pen not working。

 something like that。 Let's go ahead and tag it with our pair tag， which is going to turn out to be。

Why isn't this working， Oh， dear。 There we go。 Okay， It's gonna turn out to be that right。

 because it's a pair。 get it， a pair。 So here we go， we'll have， yeah， right， that's plenty， right。

 There we go。 Okay， so that now represents that this is a pair that we've gotten there， okay。😊。

So let's start making the changes we need to make in the compiler in order to make this work。

I've actually， I've hidden one of the other changes a little bit， which is I just said， okay。

 the way we are going to use RDI。Is that we are going to use it to point to the start of our heap。

 right， the next available slot in our heap， in fact。Now。Right now。

 I'm kind of just pretending that that's already happened for some reason， but in fact。

 there's no reason for us to assume that that has happened。 in fact。

 we are going to have to go out and change our runtime in order to make sure that we have some space of memory that we can use to put our heap items in。

 So let's actually go ahead and do whatever we need to do in our runtime to make sure that by the time control comes to us right by the time we are executing this that the thing that is in RDI is。

 in fact， a point or to a slot and memory that we can start using for our heap。

So let's go ahead and make a few changes。 So there's some that's boring。

 I'm not really going to ask you to understand the see that we're going to write here。

 I'm going to just explain what is happening。 That's sort of most relevant to us。

 So one thing is now we're going to go ahead and say， okay。

 this isn't quite the same thing It was anymore。 And also， we are going to need to take。A。

An argument。 Now， this is kind of weird， right， because I'm actually not going to change。

Sort of what's happening over here right Like there's nothing over here that is going to look different。

 There's no sort of obvious argument coming into entry anymore。

 The reason I am doing that change is because I happen to know by looking inside the C implementation that what C does when you get an argument is put the value associated that argument inside RDI right And so if I go ahead and put a pointer to something that we can use as the heap as the argument to our entry。

 I know that when control transfers to us we will have the pointer to that memory as our value that we have stored in RDI。

AndSo that's the thing that we are going to be doing right here。 So let's quickly go through。

That change， we're going to want to go ahead and make something we can use as the heap down here。

Here I am saying how much heat I actually want。And now when we go ahead and actually call entry。

 let's provide the heap as an argument， and this is basically just our way of saying give me some memory。

 give me a chunk of memory。 I'm not going to tell you what I'm going to do with it。

 just give me a chunk of memory and then I can go ahead and sort of use it as I please so that's what's happening inside here。

We also are going to need to actually change print value because we're going to need to start printing out pairs so I think we don't quite have enough time for it。

 but what we'll do is I will go ahead and put that in before our next class session and just talk you through what that is going to do and then we'll see that we're almost almost almost completed with pairs。

 if you have any questions， feel free to come up at the end of class right here。 Otherwise。

 I hope you have an awesome rest of your Tuesday。Hello， hello。

I really should be kept no house ho loanss。现在 you have that like。In the compiler。

 when you like hover over something， it shows like it's the data type。Oh。

 I thought that was actually one of the built in things I really wish I didn't just close it but like that yeah。

Yeah I thought that was one of the built， maybe I had some kind of like supporting thing I can look into it Yeah but yeah I yeah。

 it's very interesting， yeah。I'm curious about how to wetail。Hisstoring the value or。Addres of。

Great question。 Yeah， so that is exactly why we are adding the tags。

 And so if you remember what we were doing previously to figure out， is this a number。

 Is this a boolean， We're going to do that exact same thing again。Yeah， great question。



![](img/e074eeb1eaa5a34cb95cc19e5e9d3ba4_20.png)

You mentioned to represent list。