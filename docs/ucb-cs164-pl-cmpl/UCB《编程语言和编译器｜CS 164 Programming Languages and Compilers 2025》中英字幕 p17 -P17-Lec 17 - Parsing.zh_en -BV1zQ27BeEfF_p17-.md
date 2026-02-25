# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p17 -P17-Lec 17 - Parsing.zh_en -BV1zQ27BeEfF_p17-

![](img/164923be3a91684d6afc6d4acd011d5e_0.png)

Alright， hello， everybody。 Happy Thursday。 we have。😊，A fun day planned。

 we've spent so much time ignoring parsing， being like， yeah， yeah。

 Something's gonna to give us these S expressions。 And today， at last， we will find out what that is。

 So that's gonna be exciting。 But as I promise， y'all。

 we are going start off today by reminding ourselves what we've learned so far And therefore。

 what is going to be on the midterm。 So let's turn to our big slide of everything that we like to look at。

😊，So here's summary slide number one。 All of these things that we have highlighted in yellow are things that we've already talked about。

 So I'm going to talk us through。 we also have a couple on the next slide。

 I'm just going to talk us through just to remind ourselves real quick。

 what is it that we've been going over all this time。

 So interpreters versus compilers that very first day we talked about what is the type of an interpreter。

 what is the type of a compiler， we talked about how we can tell the different behaviors of an interpreter versus a compiler。

 how is our interpreter versus our compiler going to behave differently We talked about the various compiler components。

 which is something we're also going sort of revisit today。

 We've talked about syntax versus semantics syntax。

 the thing that we use to write down a program versus semantics。

 what that program actually means there's a difference between okay these are the characters we're allowed to use to express something。

 that sort of a different choice that we make separately compared to。When we are deciding okay。

 and this is what that if expression that we've written down with these particular characters。

 this is what that's going to actually mean that's how it's going to behave。

 so how does it look versus how does it behave？Assembly。

 we've thought a lot about how to generate assembly， how to work through assembly。

 We're constantly going and actually walking through what is happening as we execute assembly。

 So hopefully folks are starting to be pretty comfortable with that general space。

 We have talked about the stack and what we put on there。

 We have talked about the heap and what we put on there。 We have talked about control flow。

 especially jumps now recently calls， we have talked about symbol tables， environments and scope。

 and here's where I start drawing our attention to the fact that even though all these things that we see on the left are sort of okay。

 we're thinking about being in compiler's land， sort of the things we use to implement a given programming language。

 we are also thinking about some important programming language design decisions。

 So here jumping off from symbol tables environments and scope， Lexical versus dynamic scope， right。

 that was really important for us to figure out which of those were we going use。

And that was a really big important design choice for us。And then we can go on we can see。

 okaymable versus immutable， we've talked about that a fair number of times。

 we've talked about reasoning about side effects very related to the above。

 we've talked about reasoning about correctness that led us to thinking about undefined behavior right for something that is undefined behavior that we the designers of the programming languages choose not to commit to a particular strategy for something。

 that's undefined behavior。And then we've talked about reasoning about compile time versus runtime。

 Again， this is something that we return to over and over and over again。

 What's happening when we are doing just the compilation process。

 What's happening only after compilation once we reach the point of actually running the program。

 What are the things that are happening at those two different parts of our process。

 and that connects， again， falling one these lines to static versus dynamic types and more broadly to the idea of static versus dynamic right So in general。

 when we are talking about something being static， we are talking about something that is happening at compile time。

 when we are talking about something being dynamic。

 we are talking about something that is happening at runtime。

 So anytime you get confused about whats static would mean。

 what dynamic would mean probably probably， we are talking about the difference between something happening at compile time。

 something happening at runtime。So that's the general idea there of course， static and dynamic types。

 same deal， right， Can we check whether the types are right at compile time， static typing。

 Can we check whether the types are correct at runtime， amazing dynamic typing。Okay。

 next one functions， function calls。 We can also use this to think about lazy versus eager evaluation。

 although， of course， folks will probably remember we first started thinking about that way back when we decided how to let bind names。

 So when we added our let expressions。 That was the first point where we decided， okay。

 what is it that's going in our symbol table。 Are we in our symbol table。

 Are we going to be putting in the S expression ready to evaluate it later when we need it。

 or are we just putting in the value。 We've already done the evaluation at the time that the let binding is occurring。

 we can do the actual evaluation at that time and then put in the value associated with it。

 That decision tells us whether we were doing our our lazy versus our eager evaluation。

And then tail calls reusing stack frames。 I think I actually repeated that up here。 Yeah。

 tailca optimization。 So tail calls and reusing stack frames。

 that's exactly the stuff that we talked about last session。

 So hopefully we haven't forgotten that yet， but don't worry。

 I never like us to leave a topic after only one class session。

 So we will have a nice review activity on that later today。

 And then the semantics of language features in our scheme。

 So remember C16 S orlang is basically just a little scheme。

 we are only doing portions of scheme at a time。 and we're sort of incrementally building it out piece by piece。

 So we are not necessarily all the way to a fully functioning version of scheme。

 But the design decisions that we're making are the design decisions associated with the scheme language itself。

 And then also， of course， we have been working with Ocal。

 And so we learned a bit about the semantics of various language features in Ocal。😊。

Tale call optimization， we just mentioned， I'll mention one more thing。

 We do already know something about dynamic type checking right。

 so we've already had that thing that we've been doing where we are going ahead and we are checking at runtime。

 Does this have the type tag I am expecting。Okay， that was my brief sort of whirlwind reminder of what we've gone over。

 And now is a great time。 if you all have questions。What's coming up for y'all？

It's also okay if you want to come in and bring your questions to office hours。

 I think you' all have probably seen if you go on the course website and you scroll down to that little Bcal Gcal thing that we have down there。

 we have a bunch of office hours that we've piled in for this coming week。

 so you do have extra access to all of us。Any questions about these topics？big topic。I。まジな。Yeah。

 it's a really good question。I think the thing is that each of these different things。

 even though they're all sort of on the same bulleted list。

 And so there's no sort of implied hierarchy。 If you look through them。

 you'll see that a lot of these were sort of treating as table stakes， right。

 Like you have to understand assembly because you have to be able to read assembly and you it's not that we're keen for you to memorize the particular role that a particular assembly instruction does。

 which is why we have on the cheat sheet。 Okay， here's the reminders of the assembly instructions that we have available and sort of what they do and we're trying to sort remind you of all that stuff。

 it's not like we're trying to。Make you wrote memorize， right。 Yeah。

 So there's some stuff that we're sort of expecting because it lets us explore the deeper topics。

 So something like。What is this tech， What is the heap， right？ That lets us do broader questions。

 Ask deeper questions because we don't have to sort of remind you what that is， right。

 And so something like assembly or knowing the difference between compile time and run time， right。

 that lets us ask these deeper questions。So。Does that make sense， yeah。Yeah。

That's the other thing is like a big part of this slide is really just trying to remind you the things that will be helpful for you to feel comfortable with so that if we。

 you know， say we pick a question to be about one of these big programming language design decisions。

 then it's really helpful if we can， you know， talk about assembly in the midst of that so that it's not confusing。

It's hard， they are intermingled， it all kind of builds on itself。Are there。

 But there are prior mentors still'll get for sure。 I think that's sort of the best guide。

The other thing is honestly， like everyone in this room is probably fine。

 right like if you've been doing activities with us during all of the sessions。

You're probably going to be fine right， like in general。

 all the times in class when we stop and we have a little chat。

 it's to get you to think about exactly these things。我是个。じ接束。I love this question。

 So we have been using just a C program， runtime dot C as our runtime。

 but that's written in a language。 The C language。 Does C itself also have a runtime。 Yes， it does。

 Yes， it does。 Most of the， I mean， there are some very。

 very early programming languages that really were just straight up。 This is just a translation pass。

😊，But really， you know， for a modern compiler， almost all of the time。

 it is convenient to have some kind of runtime available。

 This is just a convenient way to implement some things。Yeah， so in general， you directly generate。

If you think about where we are choosing to put things in our runtime versus when we are choosing to actually directly generate assembly。

 it's honestly the same choice that people are usually making when they're designing a real language。

 right When do I need total control over what assembly is going to be generated for a particular construct or when do I want to make sure that a particular construct is going to run very efficiently。

 that kind of thing is the thing that we're thinking about versus when is it going to be just faster。

 more convenient for us to implement this in another language and we don't really care that much about how efficient it is or we don't really need to if we're introducing a new language construct。

 is it going to be plausible to implement that efficiently in a language that already exists。

 maybe maybe not， that's usually the calculation you're making。Yeah， that's a great question。

Do we have other。Questions。Of？明分。Are all of the activities listed on the schedule？

I wouldn't swear to it。 I wouldn't swear to it。Is that something like will？To be。I mean。

 sort of like the worksheets for sure。 But like， I'm talking also about the times that we just like stop in the middle of live coding。

 and we have a little chat right， Like activities are kind of woven through。 Like。

 we don't really have just these free。 We do have some freestanding activities。Yeah。

 I get obviously the one。For sure， yeah。Yeah。Paperwork。that we happened。Some of them for sure。

 are on the calendar。 If there's a particular one that you want that's not on the calendar。

 please feel free to let me know。 I'd be happy to post those as well， yeah。Other question。Okay， cool。

 if other questions come up later， totally fine， come chat with me during the break。

 come chat with me after class。All good。呃。Speaking of paper activities， we have one。

 So we are going to go ahead and revisit our tail hall optimization。

 We're gonna to make sure we understand what we really mean when we say that we are reusing a stack frame。

 Please come grab a worksheet that there's probably enough for everyone willll see。😊，If not。

 we'll have you pair up， we'll figure it out。ice， yeah， I don't know if this one's online。

 it might be。Thanks， y'all。

![](img/164923be3a91684d6afc6d4acd011d5e_2.png)

![](img/164923be3a91684d6afc6d4acd011d5e_3.png)

![](img/164923be3a91684d6afc6d4acd011d5e_4.png)

Okay， I want to call our attention。 There are two this is a two sided activity。

 The one I want us to do first is the one that does not use tail call optimization。

 We're going to do this compare contrast thing。 So first look at the one that actually uses the call instruction。

 not the one that uses the jump instruction。 Look for the side that has the call instruction。

 and we'll do that one first。

![](img/164923be3a91684d6afc6d4acd011d5e_6.png)

![](img/164923be3a91684d6afc6d4acd011d5e_7.png)

かマイナスでて。关。Like like here we-24 right like can you let me this Yeah So like they jump all the way to here。

 right， Then the core instruction will-8 again。 Is there any reason why we can't like jump to here like-16。

 is it because like by alignment Do you remember our 16 by aligned thing for interacting with C issue right Yeah。

 we only have those sort of like you can imagine just alternating address being available to us because we might want to call C in any of these。

Cly function we have to recognize。So the ones that I just highlighted in green are the ones that are 16 by aligned and therefore the ones that are available to us for a story and return addresses。

Allright， I'm gonna take us through this one。 It's okay if we haven't fully finished。

 but this way we'll have a little extra time for the one where we actually have done tail call optimization。

 This is just the assembly that we would have produced if we had run this program last week。

 right before we actually implemented tail call optimization。 This is what we would have gotten out。

 We would have used the call instruction。 It would have been our standard function call。

 So let's go ahead and walk through what happens。😊，First things first。

 we go ahead and we take whatever it is that we have an RP minus-8。

 which is to say the value associated with x。 and we're going to put that inside RA X。

 Why are we doing that， Well， we're doing that because we're gonna to end up doing the the add call on x and then minus0 y。

 So okay， let's go ahead and actually put the right stuff in there。Let's put in 16。Great。

 we've got 16 in there。Now， we're ready to go ahead and say， all right， what next， we've got this。

 value inside R X that we are going to want to use as an argument to add。

 so we are going to have to put it in the appropriate place on the stack so that the body of the add function can use it。

 So let's go ahead and put that at this slot right here。Great， we've put it at that slot。What next。

 well。We know that we're going to have to go ahead and use RAX for our subtraction。

 so let's put zero in there to start great， so far so good。

 Now we're ready to go ahead and say whatever we currently have in RAX。

 let's saveve it off in order to use it right so we know what's the next available slot at which we can be doing computation。

 So let's go ahead and put what we currently have in RAX at the offset negative 48。

Zero goes in there。Fantastic， so far so good。 Now we want to go ahead and get the other thing we're going to be using。

 right？ So the other thing that's going to be part of our subtraction。

 which is to say the thing that is currently at offset negative 16。

 And we want to take that and put that inside R X。 So let's cross out what we had before。

 And let's put in 12。😊，So far so good。 We are now ready to take whatever it is that we have inside R X。

 put it into R 8。 Why are we doing that？ Does anyone remember why that's the thing that we are going to do next。

It's been a while since we talked about this。Do you remember when we talked about having multiple opera？

So the thing that we do is we go ahead and use normal evaluation of this sub expressionpression。

 put that in RX。 save it off on the stack。 We did that。 We put it there。 Great， so far so good。

 And then we use normal execution in order to get the value associated with the second upper end。

 fantasticastic。 We got it there。 right So we gone ahead and put that inside RX。

 But now we're going to have to maybe do something that involves both the left upper end and the right upperand And so that's what we're about to do in order to do that。

 we're going to have to go ahead and have both of those in registers。 So。😊。

Let's go ahead and do that next step where we say， okay， what we currently have in REX。

 let's put that in R8。Great， it's copied over。 And now we're ready to read back in from the stack。

 So over there， we're ready to take that back and put that inside R X so we can use both of these values at the same time。

 cross out 12 put0。 We are now ready to do our subtraction。 We love to do our subtraction。

 We'll get that value inside RA X。 that will give us negative 12。😊。

Everyone with me so far are questions already。It's okay， if there are questions。

 happy to talk through。Okay， cool。 So we have now done the subtraction。

 And now we know something about what we want to actually do with the value we got from our subtraction。

 which is we want to use it as an argument to our call to add。 And again。

 we know where we can put that argument where we want to put it in order to comm appropriately with the function body associated with add。

 which is to say the next available slot and the stack above the first argument。

 right we're expecting get the first argument here， the second argument here。

 If we had a third argument， it would go up above。 So right now。

 let's go ahead and put it in that appropriate slot。

 So we will go ahead and we will cross out that zero that we had put in there when we were using it just as an intermediate position。

 just as a slot that we can use for computation， and we will put our negative 12 in there next。Okay。

 great， now we are finally ready to update RP， so let's go ahead and we'll sort of indicate that we're popping it over to there lovely。

 so that means that we should now have， oh， I didn't put RSP on here but we could go ahead and update that。

 but it's fine for us to just market for now。And then we're ready to actually do our call。 Now。

 our call actually updates RP again， right， so it's going to go ahead and update RP to that next spot。

 and it is going to put the return。Addres。Associated。With sub。

Does anyone remember what that is going to turn out to be。

 because we actually know if we have numbers over here， let's call this Z Oh， sorry。

 this can be z plus1。Right。So that's the value that we had actually put in there。

 And if we had put the sort of instruction numbers all the way down the side。

 we would expect to actually put that in there。 So let's go ahead and put in Z plus1 there。Okay。

 and we don't need to go back through sort of how call works。 I think this is enough for us to see。

 okay， we clearly did not reuse the stack frame in this setting， right。

 So if I now erase these old highlights， incidentdentally these green slots are just the ones that are 16 by lines so those are just the ones that because we are communicating with C we are allowed to put return addresses in。

 you can see that that's one of the slots that we use is one of these green highlighted ones。

 even though we had an empty one available just below it。

 that wouldn't have been 16 by lines that we had to reject that one and go one further。

 So let's go ahead and erase those highlights， and I'm gonna highlight some stack frames for us。

 So here we have。The stack frame associated。With sub。And then。

Up here we have the stack frame associated with add。And of course。

 they might actually do a bunch of other things up above in the stack， right。

 so it could end up using all that kind of area up there。

Do we have questions about how this process worked when we were not reusing the stack frame？

Or feeling okay， yeah。Yes， so if we remember way back when we talked about the three things that the call instruction does。

 the three things it does is it updates RP。 So this change， updating it by exactly 8 byte。

 That's the first thing it does。 The second thing it does is right into that slot that it just updated RP to point to right So it goes ahead and writes into it。

 The address of the instruction after the call instruction。 So here's call。 It's an address Z。

 which means that sub is that address is E plus1 for something like made up。Yeah。

 that is an actual memory address。 So we've been writing this like 0，1，2，3。

 quick because that's easy for us to talk about。 But that would actually be the memory address of this sub instruction。

 That's what it would actually be。 Yeah， And then the third thing it does is actually update the instruction form。

Now we也。Yes， so remember that we， because we are communicating with C。We and see not all C functions。

 but some built in C functions expect that the base of their stack is going to be 16 by lines。

 It's actually even more complicated than that。 It's like 8 offset from 16 by line but whatever is supposed to be sort of aligned with a 16 by slot sort of a 16 offset from whatever we got when we first came in right So we're just alternating slots。

 Like we can use up all those slots in normal situations。

 But if we're in a situation where we're about to start a new stack frame。 And， of course。

 any of those functions might themselves call out to a C function。

 We want to make sure that we are always writing into those 16 by line slots。Yes， so if you recall。

 do you remember how we are keeping track of what is the next available slot in the stack。

Not so much。 So we use RSP to always point to the base of our stack。

We do not use RSP to keep track of what is the next available slot on the stack。

 We have this nice value stack index that we're providing as an argument to all of our calls to compile X。

 and that is actually keeping track statically at compile time of what is going to be the next available offset from RP that we have available。

 And so at compile time， we can bake in to the assembly we generate something that ensures that we're always going to put the address。

 the return address at a spot that is 16 by the line from the base of the stack。Does that make sense。

要。所以。How is that representing having？How is that representing？HI'm not sure I have understood。

The question， so we have。Let me pick a highlighter color。We have the， the place where we sort of。

Update RP in just a normal subtraction。And so the， the question is， how does this represent Oh。

 maybe maybe this is a question about the fact that I sort of drew the arrows that were're starting from the base of the stack。

 so。If we， the way that we're drawing arrows is that this would be sort of slot 1。

 This would be slot 8。 This would be slot， right Like we're always going ahead and using the full 604 bit。

But we could actually carve it up into fewer。 And so our visual language is that zero is starting here。

It's not about that question。 That's， What is the question， Can you give it to me again。

Is zero starting at the top or the bottom？The top， the top。 Yes， the top。Yeah。

 so we should think of RP。Originally pointing to this slot right there。

Which would mean writing into this slot。Thumbs up， great。 Yeah， sorry。

 the visual language was a little unclear there。Other questions about this？Okay， cool。 In that case。

 let's go ahead and turn our worksheets over。 We will now go through the version that does actually include。

Taale call optimization， and so this is the version that would get generated with our current implementation。

 our current compiler。This is going back to the other problem， I just on the Russia。Like between。

Steps steps 11112， like how the RP is actually moving。 So starting right here。

 this gets to-24 jumpps right here。 this call， like for like the safety offset is what puts up here。

 Thats right puts the return address and then does it put it back afterwards or does a return instruction puts it back Okay and then so it stay up here。

 And then but of course， call can't write， because remember。

 once we're transitioning control to the body of the function being called it needs to not overwrite this So it has to stay up there the body of the function And then when we do this RP-24。

 does that mean it lands back。Right here so will the return of the thing that got called happen before or after that subtraction before before and then that's what returns it right there and then it does RSV 24 you got it yep thank you。

工一权。All right， hum， if you feel ready to go through it as a class？If you want a little more time。

Very cool。 Sounds like we're ready。 Do please feel free。 Sho out any questions as we go。

 I won't see you because I'll be looking down， but shout at me。 Okay， great。

 so we're starting out in exactly the same way。 We say， all right。

 we've got to get this value associate rate because remember。 this is the same program， right。

 This is the exact same program。 We've just use a different version of the compiler in order to actually get this assembly。

 So we're starting out the exact same way。 we say that the thing we've got at offset negative 8。

 We've got to put that inside R I X。 Fastic。 we land with 16 in there。😊。

And now already things start to diverge a little bit。 we're still accomplishing the same purpose。

 but we start putting things in different places。 so here we're saying， okay， well。

 I've got to save that off because I've got some other stuff to do。

 but we save it off in a different place so now we're going to put that 16 right there。Next thing。

 great。 we're gonna go ahead and put in0 inside RX。 same deal。 We are now ready to say， okay， well。

 we've currently got an RAX。 again， we've got to go ahead and save that somewhere this again。

 same deal that we were doing before because we have to do our little operations。

 So let's go ahead and move that into there we are now ready to start actually doing some of that subtraction。

 So let's first get the value associated with y right Y。

 let's first get that value into the appropriate slot。 So we take from the offset negative 16。

 and we put that inside RX。 we get 12。😊，We are now ready to grab that。

 put it in RA8 so we can now actually get our other operaand back into RAX。

 Let's take the thing from the offset negative 32。 So right there。

 let's take that and let's put that inside RAX。 We will cross out what we have there right now and we'll put zero。

 We are ready to do our's subtraction again， this looks just like what we did in the last version。

 So let's go ahead and do that。 So we'll cross out that。 We'll get negative 12。😊，Okay。

 we now take what we currently have in reX and we put it at offset negative 32。

 We have now saved the values associated with all of the arguments to add。

 And if you remember one of the things that we realized last session was that we had to build up and save all of these at the top of our stack and only then move them down below because we might keep needing access to these things as we are going off and doing our work and so what we had did。

 we actually set it up so that we were going to build up the arguments that we were going to use for our next call but we were going build them up at the sort of next available slots in the stack。

 we have now saved those on those next available slots in the stack do we have questions about that so far。

We're so far so good。Amazing， alright， thank you。 that was very nice。 That thumbs up。 Okay， great。

 let's go ahead and move some things down。 So now we're gonna go ahead and take what we currently have at offset negative 24。

 right， So the first argument to our， our call。 And we're gonna go ahead and move that into our 8。

 So let's go ahead and cross out what we currently have in R 8， and we will put in 16 there。😊。

Now we are ready to go ahead and put it in the spot where we actually want to put it right Because remember。

 our call to add， right， when we are actually in the body of add。

 we are expecting to find that argument at the next available slot above RSP， right？

 So we are now reusing the stack frame。 Here's where we have RP minus-0。

 Here's where we have the return address stored。 So add the body of add is going to expect to find its arguments right above that。

 So now we get to the point of overr stuff。😊，And this is exactly why this is only okay because this call is in tail position。

 right， This is only going to be okay because we're just gonna， we're gonna clobbber this stuff。

 This stuff is going away， and we're gonna have this other stuff in there instead。Allright。

 so we are now decimating the old stack frame。 So let's actually do that。

 We will take what we currently have in R8， which is to say 16。

 We will cross out what used to be there。 And of course， it turns out we get 16 again。

 but that's okay It wouldn't necessarily have been the same thing again。 And in fact。

 we're about to see a case where it's not going be the same thing again。 So okay。

 we've moved that from R 8 into the spot associated with the first argument to add。

 We are now ready to take something from RP-32， which is to say the value associated with the second argument。

 We are going take that and put that in R8 instead。😊，Put negative 12 in there。 fantasticastic。

 Now we are ready to go ahead and move that into the slot where the body of add is going to expect it。

 So we'll cross out what we had in there before， and we'll get negative 12 instead。

 And now we're ready to do our jump。 Now， you can see something we did not do this time。😊。

We did not update RSP。RSP is still pointing to the exact same spot， right。

 Because what's happened here is we said， okay， this is the the stack frame associated。With sub。

As we sort of started this process as we started executing this function。

 that yellow highlighted spot was the stack frame associated with sub and now right when we do that jump。

 what we're saying is， okay， this is now the stack frame associated with add right exact same spot on the stack。

 we have reused our stack frame。Do we have questions about this， yet。Yeah。Yeah。

The reason that we've had。Assume that there's a。呃。Okay， yeah。 So this is a question about， hey。

 when we were doing the version that didn't use tail call optimization， we left this empty slot。

And the question was， why do we not have that here？And why do we have it， sorry。

 Why do we not have it on this version， Why do we have it on this version？

 So it's not that C functions ever expect there to be an empty slot or some padding or anything。

 But what it does expect。 Can you see the yellow highlighting here。 Yeah， you can。

 It does expect that any return address is going to be stored at 16 by aligned slot。 In fact。

 it doesn't even necessarily assume that it just assumes that when control is passed to particular C functions that they are going to get that。

 And since the way that we actually set the return address for when we are using the call functions。

 we are enforcing this in order of enforce that any time we transfer control to C we have left the return address at a 16 by line slot。

Yes。Since we don't have。Like alignment that。thatSo we do have the alignment here， Right。

 So here we have the exact same thing going on with this slot is an allowable slot。

 This slot is an allowable slot。 This slot is an allowable slot。

 We don't have to think about it here because this is the return address。

 It's already in one of the allowable slots。 Were not actually changing RP at all。

 We know that this stack is already set up。 It's already good to go。Sunds up， yeah。

What other questions might we have about this。Yeah。I love this。

 Why do we still have the return instruction， Okay， so I think this actually is， again。

 a situation where it's good for us to look at the past one。

 So is this the return instruction associated with this call。😊，I would say no， right。

 We are going to go ahead and call add。 And somewhere up here， there's going to be an a body。

 And then at the end of that， we're going to see a return instruction。

 That's the thing that's going to get us back to this slot。 And then we're going to keep doing stuff。

 And then this is the return associated with sub。That's the return that we've actually got there。

And so here， the exact same thing is happening。 This is not a return associated with。Add。

 this is a return associated with sub。 Why do we have a return there。 Well。

 we can see that we are going to print whatever we get back from this call to sub。

 which means the entry stack frame is somewhere down here。 right down here。

 we've got an entry stack frame that has set up this sub stack frame for us。 We are using it。

 And at the end of using this。 We will actually call return。

 It will use the return address that we find down here that we will never touch， right。

 It is going to use that address in order to get back to entry。That entry function。

 that is always our starting point。Does that make sense？How we get back to this return instruction。

After we jump to add label。Oh。I think I understand。 Well， let me make sure I understand。

 Can you say the question again。Right， so somewhere else here， there's function add。Something。

 something， something， right。 And then we've got various instructions， and then it has a return。Okay。

 okay， okay。 I think I have understood the the question。 So you are absolutely right。

 That is the return instruction that is going to read from this address。 Now。

 because we have not changed this address， this is the address associated with entry。

Is that the question？ Yeah， so why does that work， right？ Like。

 remember when we were talking last session about the fact that this， this change。

 T C O is only okay when we are not doing anything。Between the end of our。

Call and actually being done。That's exactly what we're saying， right。

 It is okay for this return to jump us directly back to entry and not do anything else associated with sub。

 And that is， in fact， the return that is going to jump us back。This one is not getting used。

Thiss cool， right， Isn't that weird。Yeah， so the address that we see here is getting used， right。

 we've left that in there， and that's still what RSP is pointing to。But yeah。

 that return is not the one that uses it。Yeah， great question。Yeah， yeah， absolutely， absolutely。

 yeah。Other questions。Yeah。見みせ。将。Oh， that's just what was in the compiler。 Yeah， yeah。

 we just generated this with the actual compiler。 Yeah， we could have used R X there。

 It's not like we were overr anything that we were worried about storing。 We just use R8， yeah。Now。

 it's totally fine either way。 If we had been worried about maintaining something in R A X。

 that's when we would have had to avoid that。呀。It just。

Can languages that are more objectoriented make use of this optimization？ I mean。

 you've certainly seen us create data types in Ocaml。 and Ocaml does， in fact use this optimization。

 the real distinction between languages that benefit from tailcoll optimization。

 those that don't are if you are using a language where recursion is the expected way to deal with large volumes of data realistically you're going to need this optimization and optimization and scare quotes because one of the things you can see here is that this is actually more instructions then the version that did not use tailcoll optimization。

 And so this is not a performance optimization right you can think of it as an optimization because you are using less space And so maybe it's a space optimization。

 but it's not really right to think that an optimization。

 We're not going to use this like this isn't one of the things we're gonna to talk about at the end of the semester when we switch into optimization land。

 and we're just think about optimizations。 like this is a necessity。

 This is something that is like this is written in the scheme standard。

 Every single scheme or limit limitation you've worked with has this。

If you are in probably a functional language， but any language where the expectation is that you are going to use recursion as your way of dealing with large amounts of data。

 like obviously we care about writing large programs， we just we have to have this。

We have to have that。Does that make sense。But yeah， nothing stops you from your right。

 Like this is really all about。Do you want these function calls that appear in tail position。

 Do you want them to reuse the stack frame， That's the only thing that it's about。

 And so if you have calls that might appear at the end of a function body， fantastic。 Like。

 you might want this。Are there other questions about this。Okay， and that case。

 I have a question for y'all。 I want you to think about the scheme that we just did。

 So let me highlight things in a new way。yeah， that's fine。

 We just did a scheme where we put all of the。Arguments at one spot， and then moved them。down。

And what I want you to answer for me is would this have worked if there were three arguments to add。

 so say I changed add to be something like we also have another X there and it accepts Z whatever right。

 if we had three arguments to add， would this still work， discuss for 40 seconds？小分。All right。

 hum if you think this is going to work fine？H if you think this is not going to work fine？Yeah。

 okay， cool。 Sees like we're on the same page。 This would totally work fine Ca say we had something up here。

 I don't know，32， whatever， right， The order that we do this matters， right。

 So if we go ahead and we move that one first， Okay， yeah， we have now overwritten。 but that's okay。

 We now put this in here。 Okay， we've overwritten。 now we put in here。 Okay， we've overwritten。

 But remember， weve already actually moved that one。 So it's totally fine。 It's totally fine。 Yes。😊。

We wouldn't need a third register for this。 No， that would be okay。

 we're just reusing R8 for all of the arguments here and that's totally fine。

 Yeah because we just put things into the stack when we're worried about running about register later later in the class。

 we are going to talk about register allocation and how we could use registers in a much more smart way and a way that would avoid us having to use the stack quite so much。

 but that's a question for later。Question。Okay， cool， so。Well， let's real quick。

 wrap up talking about tail call optimization。 I am going to keep calling it tail call optimization。

 even though I keep emphasizing that this really isn't an optimization。 This is a necessity。

 And that's just because sort of the standard thing that you call this income compile compilers land is tail call optimization。

 So we will keep calling it that。It's not really an optimization。 It is more a necessity， right。

 it really， this is in the scheme standard。 you have to have it， right， The stack just isn't enough。

 so we have to have it。I want to give us one more quick example to play around with。

 Do we have time for it， I want us to think about。Let's see。

 what's a program that we could use to play around with this idea。I want us to think about， if。

We had。This program， but instead of some F being the thing that we had in there， we had do。1，2，3。

 And I want us to think about if。The do would be in tail position and if the three would be in tail position。

 so go ahead and discuss with folks nearby for really only 30 seconds are the pink highlighted thing and are the yellow highlighted thing are either of them in tail position。

All right， hum if you think the do is in tail position？Hum， if you think it is not。Yeah。

 I agree it's not intail position because we see that we're going to have to actually print whatever we get back from it。

 therefore the do as a whole is not intail position。

So I want you to go ahead and hum if you think that three is in tail position。Hum。

 if you think it is not。Yeah， I agree。 If the parent subexpression is not in tail position。

 then the child certainly is not right， we don't just magically become in tail position。

 And so that's why we have this being is tail rather than false， right。

 that's why we're doing this process of keeping track of that throughout the compilation process。

 because we cannot just magically become entail position。 If the parent is not entail position。

 So that's why we didn't use true here， we used is is tail instead， right。

 So if the do is entail position， then that last expression within the do is intail position。



![](img/164923be3a91684d6afc6d4acd011d5e_9.png)

Question。开清。Inhale position is respect to either the body of the function as a whole。

 so here's the body of the function as a whole right so the question we would ask ourselves is could we now just knock out everything that's in could we just ignore the entry function。

 right？

![](img/164923be3a91684d6afc6d4acd011d5e_11.png)

You do a few0。Is the three。 Oh， I see。 So this is saying， say we didn't have print in the body。

 sayy we just had the do and we didn't have the print。 Yes， then the do is now in tail position。

 right， because as soon as we have done the do， that is the same as doing the program body， right。

 Like once we have that value， there's no extra computation to do。这客。て do。回 down了。

I think this question is。

![](img/164923be3a91684d6afc6d4acd011d5e_13.png)

We would also want to know so if we didn't have this print and we knew that this de was in tail position because it was just the program oh。

 you're not seeing it。 I'm so sorry。If we knew that this do is in tail position。

 then we would want to also know that this is in tail position because maybe there's a call in there。

 and then we want to replace the do as a whole。 Is that the question， Yeah。

 so that is what we're doing when we're keeping track of is tail right。

 we are keeping track of that explicitly so that you know， say that later on， right。

 the only time we ever actually do anything， act on this knowledge of whether something is is tails when we actually hit a call。

 But we are keeping track of it everywhere， right， including when we're sort of looking at the the do or whatever。

 right because。

![](img/164923be3a91684d6afc6d4acd011d5e_15.png)

![](img/164923be3a91684d6afc6d4acd011d5e_16.png)

![](img/164923be3a91684d6afc6d4acd011d5e_17.png)

Right so somewhere down here， we've got do yeah， so we are keeping track and updating here because we do in fact。

 want to make sure that if that call is happening in that final position in a do。

 that we would still be able to do tail call optimization for that sort of subchild of the do expression。

Does that make sense。Okay cool， we have a late break today again I'm so sorry that keeps happening。

 let's take just a little three minute break so we can have a little bit of parser content。

 we'll come back together at 447。 so sorry for the short break。Absolutely， it's just our choice。

 We could totally use R X。Yeah， Ill give look an example。Like。

 for example on this program with the prints do 1，2 the factorial 5。 Yeah。

 starting with like an initial like accumulator of one， right， Yeah， yeah。

 wouldn you want to essentially do this part entail using tail。Recursion or tail optimization。

 And then like， for example， you open a new stack frame for the deal。

So we don't make a new stack frame for the do。We make new stack frames for function calls。 Yeah。

 all right， right， Yeah that' that's okay。 Okay。 Does that make sense I like。

I guess when are we doing the factorial here？Tly， it's not untilposition because we have the print right。

 yeah。And so what would happen if we said， okay， now that this is the the like we've got this fact call。

 let's now just wipe away the entire stack frame for entry right。

 We'll never get back to any of the code associated with entry， we'll never get back to that print。

 Yeah， so since this， we're going to open a new stack frame， right。

There's no new stack frames in this because there's no functional。 Oh， there's。 Yeah。

 so we will make a new stack frame for fact。 Yeah， absolutely And in that case。

 when it calls a factor04。Would that。In this would that stack frame be tail optimized in a current implementation？

Ah， this is about recursive calls so if there is a recursive call inside fact。

 if that call is in tail position， we will only end up with the single fact。Yeah， yeah。

 that's why like sack exactly。 But on the other And。 so， yeah， so that's why if you take a look at。

Yeah wondering where exactly the program do we kind of say that in this kind of news that we opened like fact for the first time any subsequent so there are two places where we have true as our argument for is Ta here when we are compiling the body of the program as a whole and right here when we are compiling the body of a function right when we've got a function definition。



![](img/164923be3a91684d6afc6d4acd011d5e_19.png)

because those are the places where we have stack frames。

 this is the stack frame for entry right that you see label entry right here like that's the stack frame that's going to be associated with entry and then this is going to be about the stack frame associated with a given function Okay so when we enter fact start with a we've got a new stack frame for fact and we get to make the decision about whether we's okay to overwrite that stack frame based on what's intail position for the fact that makes sense yeah。

Thank you。First is one quick clarification for the homework， right， you。

There's only output when we call the print， right， when we call the print function。Other than that。

 right， by default， there shouldn't be output like we just like put in an expression like a string or something like that。

It will just give nothing。 Just run that through the reference in implementation。 right。

You always have the answer to questions like that， run a program on a great scope。

Last example you showed。We just have like the。The statement。Any specific function。

We're in the entry function， yeah。Writing the entry stack frame。That's right。Like。

After the due statement。Complete， we just return control to the O。



![](img/164923be3a91684d6afc6d4acd011d5e_21.png)

We return control to run time。 So remember， we've got runtime dot C。

 And that's the thing that actually calls。Entry， right， so here we call the entry， right。Yep。

 so then control returns to C。Yeah。Yeah。But yeah， if we take a look at one of these programs right we can see that we are making this entry function and there's going to be a stack frame associated with that that was created by runtime。

c when it made that call to entry right that set us up with a stack frame for entry and that's the thing that we're using。

Yeah， yeah。Yeah， and we get to overwrite that one too， like yeah。

 we get to overwrite the stack frames that we've made， but we also get to overwrite that one。Yeah有。

Like I'm assuming that。只要色。So。Andization。So I really like over。

If it knows that this so this is not actually in tail position right because we can see that there's this return zero and we do have to return zero and this would not do that so we're not actually overriding the but I also I actually don't know if C implements tail call optimization。

 I wouldn't swear to it。Yeah， we could look it up， it would be easy to find out。Yeah。All right。

 one last note about tail call optimization as we move on。

 So you might have heard the term tail recursion， which is when we are making a recursive call to a function and we are making that in tail position。

 but as you have seen， we can also do tail call optimization in situations where we are not even doing recursion right So this example is an example where we were calling right。

 we were inside the sub function and we were calling the ad function。

 and we were still able to reuse that stack frame that is totally fine。

 So I just don't want you to get confused when you hear tail recursion and think that this is only for recursive functions。

 It's very useful for recursive functions right， we first talked about this because we were doing the thing where we were trying to provide 1 million and we wanted to be able to actually reuse the stack frame for each of those recursive calls but we can still do this process of reusing stack frames even outside of that context。



![](img/164923be3a91684d6afc6d4acd011d5e_23.png)

![](img/164923be3a91684d6afc6d4acd011d5e_24.png)

Other questions about that？Also， I think a lot of folks had sort of related questions about the idea that hey。

 there are multiple different kinds of stack frames that we might be reusing。

 so if we look at compile that ML， there are a couple of different places where we indicate that something is definitely going to be in tail position right we do it once for if we are compiling the body of a function definition right and so that's a situation where we know there's going to be stack frame associated with that function call。



![](img/164923be3a91684d6afc6d4acd011d5e_26.png)

And then we also provide true if we are actually creating the body of the program as a whole。

 in which case the thing that we would be overr， right the stack frame that we'd be overr is the stack frame associated with entry right and that is a stack frame that was actually introduced when we called entry in our runtime do C right that made the stack frame for entry。

 but we can also go ahead and just reuse that stack frame if we realize that something is in tail position in the body of our program。



![](img/164923be3a91684d6afc6d4acd011d5e_28.png)

Okay。Sounds like we're feeling okay about this。 We will get as far as we can with parsing today。

 which might not be super far， but we we'll do the best that we can fit in。

 We'll get just eight minutes of fun parsing activity。

So the main thing I want us to think about today is how we get from a flat representation of our programs to a representation that represents something about how we actually think about these programs that has something maybe like a tree structure right。

 we sort of think of of these programs we've been navigating them。

 we've been doing all these recursive compile exp calls。

 we think of them as having a little bit of a tree structure。



![](img/164923be3a91684d6afc6d4acd011d5e_30.png)

Pardon me。So okay we have a couple of things that are going to help us get that sort of nested list or tree structure。

 so we are going to have tokenization， which is just going to be in charge of actually going from the raw string to a sequence of tokens and this is a little bit weird like I've kind of I've done line breaks in a way that represents this as though there's maybe a little bit of structure here。

 but in fact we can see that this is still a flat list right we've still just got okay token token token token token token not really represents that tree structure that we might associate with the program whereas here we can see okay well we've got this outer list。

 but then we've also got this inner list， it seems like the thing that is giving us a less flat representation of our program。

 a program that represents the way that the components。

 the language components are actually interacting it seems like it is the parser that is giving us that。

That is true。Okay。So I am going to introduce us the main thing we need to have for a language in order to write a parser。

That is a grammar。So heres the grammar for S expressions。 We're gonna to be quite concrete today。

 We're only going to talk about how we might write a parser for S expressions and another couple of sessions we will talk about tokenization and another couple of sessions will also talk about how we might write a grammar。

 how we might write a parser for something other than S expressions。 But today。

 we'll just think about S expressions。 And so I'm going to go ahead and write a couple of things about this grammar because I'm not expecting you to already be familiar with how to read a grammar。

 And that might be the main thing that we get comfortable with today since we have so few minutes。

 So let's go ahead and highlight a couple of things here。

 So one is I want us to look at these things that have these braces around them， these angle braces。

 So these are nonters。 I'll write that out for us。 nonterals。😊，As you might guess。

 from the fact that those are called non terminals。

 the other thing we have available here are terminals。So let me highlight those。So， we also have。Num。

 Sim， Elpin， Aproin， and this empty string。 And these are。Our terminals。

 so the reason that we are distinguishing between these is that nonterminals are the things that are not going to actually appear in strings that represent programs right Those are things that we are using to sort of keep track of the structure of our programs。

 but the things that will actually be written down in the string that represents a program that is going to be these terminals and so let's jot down a couple of other things we might notice here right because obviously this is not actually covering all of the characters that we're seeing in this grammar let me swap colors and point out this is just data associated。

With a terminal。Not so exciting， but good to know， we can also figure out that this is the start symbol。

 so if you don't see anything explicitly marked as being the start symbol。

 the first non terminalmin that appears is going to be the start symbol。

And then we've got these like colon colon equals things。 We've got these bars。

 It seems like there's something else that sort of tying all of these things together。

 And that is going to be the idea of a production rule， right So here this is one production rule。

 And in fact， if we look at sort of this tied together with that， that's another production rule。

 If we look at that tied together with that， that's another production rule。

 So let me go ahead and label the S X。Production rules。And that's going to be that， that。 and that。

 And of course， we also have some production rules associated with LST here。

 So those are our production rules， and we call them production rules because of the idea that the thing on the left。

 right？ So in our case， S X here。Is allowed to produce production， produce。

 produce the thing on the right。And so what this means is that this is a way of generating strings that are allowable in our language。

Right， so if we talk through， okay， I'm going to start from my S X， right？That's our starting symbol。

 And I want to go ahead and actually generate a program that is allowable in my language。 Fantastic。

 Let me take this first production rule。 That's one of the production rules I could take。

 I'll go ahead and do none。😊，And maybe I associate that with two fantastic。

 the program two is allowed。As a program in my language。Not a very interesting one to take， but。

 of course， we can take some of these more interesting rules。 as here we see。

A little bit of what that looks like。 So here we can see that we have taken first that Lparn LST Rparn rule。

 right， we can go back and we can see that right here。

 That's the rule that we have clearly taken first。 So we've started from our start symbol。

 We've gone ahead and taken that rule first。 and then we can see that we've followed a bunch of other production rules。

 And we've gone all the way down until all of the leaves are， in fact， terminals。

 So let me again highlight our terminals versus nonters。 So we've got our nonters here。

 You might notice something rather interesting about the placement， right， And we've got our。Sorry。

 the terminals， in case I didn't say that right because sometimes I say the wrong thing。

 the things that the leaves are the terminals， the things that these inner nodes are the nonterals。

 right so we can see that all of those internal nodes are nonterminals。

 meaning they're not ready to actually go into the program yet。

 and all the things that the leaves are the terminals。 And so from looking at this。

 we can actually read off a program that is allowed in our language right。

 And so this would be the program left parn plus12 empty string right parn right So written a more normal way plus1。

2。A nice program。Why do we need the empty string， Yes。

 great question So it turns out that the way that we are going to indicate that we might have nothing left here and we're ready to end right like you can see this is basically recursive right so if we don't have empty string。

 we don't have sort of the base case and we're never going to be able to actually end this has to be an infinite list not so super useful for us we want to be able to write finite program。

Great question。Okay， so this is called a parse tree。And with our very last question in class today。

 our very last little activity， I want you to think about how could we， if we have some new string。

 right， say that we didn't get plus 1，2， we got some other string。

 How could we figure out if that string is in our language。

 Disc for it's 30 seconds because then we're going have to go。😊，All right。

 anyone want to yell it out？How might we tell whether a given string is， in fact， in our language？

I'll give you a hint the answer is written on this slide。If we can generate a parse tree。

 exactly right。 So if we know that we can use the production rules in our grammar to generate a parse tree that produces the string。

 then that string is in our language。 And we'll pick that topic back up after the midterm。

 I hope you'll have a good rest of your week。😊。

![](img/164923be3a91684d6afc6d4acd011d5e_32.png)