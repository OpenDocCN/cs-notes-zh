# 【计算机组织与系统 cs107 2016】斯坦福—中英字幕 p09 【Lecture 09】CS107, Computer Organization & Systems -zrun2KpTwDk- -BV1Nr421c7YB_p9-

All right。Welcome back everyone， guess the crowd is thinning a little bit as midterm weak and such approach。

Nevertheless， we've got。Back into things here， welcome back。

Co of things before we get before we get started here， just a couple announcements。

 I'm I'm not going have slides today because I'll be doing everything with through code and Gcc。

 So so the announcements for today we have assignment three came in on Tuesday。

 hard deadline was last night。 hopefully that all kind of。You all saw that through。

 lots of practice on void stars， lots of pointers and memory management。

Now we are into assignment four， which has been up for a little while。

 already got a few questions on that， which is always good to see students starting early and getting a good head start on that that's coming in。

In Tuesday of next week。And while you are allowed to use the normal hard deadline for that assignment。

It is the more time you take working on assignment four is going to ultimately mean less time for working studying for your exam that is coming up。

A week from today that exam is in class。 Hopefully， this is not， or it's during class。

 that will be split between two rooms。 The information is on the website， and。

There's a practice exam in the back printed out also that is posted on the website。

So that should give you a sense both for the material on the exam and for what the logistics are going to be。

It's kind of， I guess just a quick kind of。Brief sort of focus on what we' what we're looking for with the exams。

 We're hoping that the exam is going to look a lot like the kind of work that you've been doing on the assignments and the lab so far。

 We're not going to try to pull our goal is to have for there to be no surprises。

 right It's not going to be that you will show up。 and there will be suddenly this function that you've never heard of and you've never used before thatve nothing to do with thus far。

 the code， the code that you will be writing and the pointers that you'll be working through。

The concepts that you'll be tested on are hopefully going to be very familiar because they are precisely the things you've spent so much time on throughout the quarter。

So hopefully you will see that from the practice exam。You。

 feel like this is something that you can walk in to the exam next week， kind of ready for。Okay。So。

 all right， let's get into it for today。 So last time we started talking about assembly and we talked about。

The move instruction。 First， we introduced the the notion of assembly at all。

 We introduced our and our particular assembly language and our system， our X 86，64。

 We talked about registers， and then we spent the majority of our time last time talking about the move instruction。

 And we saw a variety of ways to access。😊，Data to access our memory。 So we saw。

 you'll recall the moves of immediate and addressing modes。And so today， we're going to kind of。

We're gonna keep that going。 We're gonna look at a bunch of different instructions。

 a bunch of different translations of C code。 So recall that our。

 our ultimate goal with assembly isn't gonna be to sit down and just crank out a bunch of assembly ourselves。

 But we really want to be thinking about how does C code translate to assembly and vice versa。

 How can I look at a piece of C code and know what will happen on the machine when that code is executed。

 And how do I look at a piece of assembly and know what kind of C code went into generating that。

So today we're going to look at kind of a few operations。

 we're going look at arithmetic and logical operations。

 we're going to look at some of the control structures。

 and the next time we will continue and talk about function calls and other C construct。哎。

So I'll kind of be switching between GCC Explorer and actually showing you the code live。

 but for now let's go ahead and start back up in。In Gcc Explorrs。

So last time we ended our discussion with a little bit on Tcast， and I want to review that。Here。

So let's just get into it。Soright function， oops， I mean。Oh wow， hold on。Hello， here。One second。

 what's going on？That's unfortunate。嗯，别。Oh， you know what it's going to be？Yeah， I did。Hs。

Here you know what it's going to be is， it's going to be this。Yeah。Hey on， sorry。W哦。ど可。I'm typing it。

But it's not。It's not respecting my caps lock。There we go， sorry about that。Where are we here？

Sorry about that， that was unfortunate。Do you know one more normally？Okay。All right。

 let's get back into it， talk about that。So here we've got a function。

 we're going to have it take a pointer。And then we started talking。

 so here's just a quick review of the move instruction that we were seeing last time。Where。

So we've got we're gonna access now this this instruction might look a little wacky right。

 It's star of pointer plus 3。 And if you recall from our discussions of pointer arithmetic。

 this is actually just an array access。 This would just be equivalent to pointer bracket 3 but know but I'll show you why I'm doing it I'm writing it like this on purpose in a moment。

 So here we've got a function it takes a long star and returns along and it's going to return star of pointer plus3。

And so hopefully this looks somewhat familiar for last time we have a， we're doing a move。

 it's an eight by move because we have a Q suffix here。And then starting with the first parameter。

 RDI， we add 24 and dereference it， remember this wacky syntax where we put the 24 outside of the parentheses。

 and that means that we add 24 and de referenceence it。Okay。

And then we moved the value into return our return value location， which is RAX。You get on this。

 is there any。Follow up from us。Okay， so the question that I want to ask here is。Right now。

 we're doing pointer arithmetic and a D reference on a。On a long star。And。

And the question I want to ask is actually， whoops， I to。I'm not actually going to return it。

 I'm going to actually just set it to zero。That's fine we're going to do this。

 we're just going to say equals zero， so same move of the 24， but now we're moving a zero into it。

 right？And then my question is going to be， what if I take pointer and I cast it as a carestar？

What will change about the assembly， So now we're doing point arithmetic on a care star。

 and now we're dereferencing a care star。😡，And you'll notice that there are two things that did change。

 the two things that I pointed out， actually， now， instead of moving a。An8 byte value。

 we're moving a single byte value。 So that's a move B instead of a move Q。And instead of adding 24。

 which was three times 8。Right， which is how we do point Earththetic on along， we add。

We add three bytes。But in general， nothing really changed about the assembly in terms of we're still looking at RDI for the first parameter and we're still going to move a0 there。

 and more generally， the typecast itself does not get its own instruction。😡，Right。

 all the typecast does is it causes。The compiler to interpret our code a little differently。😡，Yeah。

And so you can imagine kind of。Looking， so you can imagine kind of putting and so this applies so this example applies to pointers。

 but we can think of this happening for and we'll see a few of later where if depending on the type information is largely lost when I go to assembly and all we really have left in assembly are the actual mechanics of moving around in memory。

In increments of bys and how you know， accessing， accessing different pieces of memory in 1，2。

4 or 8 B chunks。 And that's all that's going to be left over。Of our。

 of the type system when we finally get down to assembly。哎， any歌程状态。Okay， so。

Now I want to introduce our next kind of major instruction。 So I'm actually going to copy。

So we're going to do something a little bit different here， so we're going to do this。嗯。

I'll call this move， and here I'll actually do。Return。I'll do that one， okay。

 and I'll actually just do it turn off。Plus one， okay， I should try and it。 Okay。

 so here so I'll leave this example here for your reference。

 but now so all the examples that we saw so far were using a move we said。

 and when we accessed to memory， we actually wanted this de referenceence right when we said that when we did a move queue of the。

😊，Oops， oh， it's not going to compile。If we do a move queue and we dereence。

This parentheses implies a dereence。😡，But now I want to see。

 but what happens if I want to return an address instead？So here。

 instead of returning the reference of pointer plus1。😡，I actually just want to say。

Return pointer plus one。The address， right， So I'm going to move one forward。

 Im want to move one long ahead in memory。 So what we see here is we see a new instruction。

This instruction is called LEA。LEA stands for load Effective Address。Load effective address。

 And what this is going to do is it looks just like move。

 Notice the syntax is the same in the same way， but。Now we're not going to dereference。😡。

So this is the kind of one special case where the parentheses here will not actually mean dereference in any other situation when you see this is an indirect with displacement addressing mode。

 that's what we call this because we start with a register and we displace it so we offset it by eight bytes in this case in any other situation we would expect a dereference here we would go to that location and memory and get the value back LEA does not do that。

😡，LEA just adds8 to RDI。😡，8 being the number of flights， and then stores that value in RAX。Okay。

And so here you can see here is another place where we could see that if I cast this pointer。Well。

 if I cast it to a character， I'll probably be get a warning for casting it back。But yeah。

 I'll get a warning for casting it back， but we can see that the change is consistent that casting pointer not really going to have an impact other than。

 well now I have to add one byte instead of adding eight I'll hear that warning。All right。All right。

 so just to kind of。The LEA instruction we'll see it come up again later but。For now it's just。

 it is how we're going to。It's how we're going to compute addresses。

 So in some cases where you have where if we use an ampersands。

ret hard to come to get a good example of this because a lot of stuff is being stored in registers。

 but a lot of times if you need to take the address of something like。

 so I could rewrite this right to Ampersand of Ar bracket one。And that's going to be the same thing。

We know that- and this is actually reminding us that ampersand of pointer bracket1 is the same as just doing pointer+1。

Go。All right， so now， I want to move on and show you just some of the ways that we can do other。

Operations， so just kind of sort of a whirlwind tour of arithmetic and logical operations。

 I'm certainly not going to go through all of them。 That's you know。

 all the or not even all the ones that really kind of。

Are that you'll run into there is a a one sheet on the website that gives you kind of a rundown of the most important instructions。

 So I'll just， but I'll just show you a few。And I'll return local。Okay， so here。

I want to show you the ad instruction， right， So over here。

So we see a so I'm doing everything now I'm mostly going to be doing a lot of stuff on int today。

 I did a lot of things with long last time because I wanted to keep the move constant。

 I just wanted to stay on a move queue， but since most of our arithmetic and most of our interesting kind of code is going to be operating on int。

 I mostly want to stay in the int space， so we'll see a lot of movebells。

 we'll see a lot of E such and such registers。😡，So here you can see that I'm moving。EDI。

 which is my first parameter one of the first parameter in int into EA X。 And then I'm going add。

Dear reference RDx to it， so two things to note。The add instruction， so notice it's at add L。

 just like move， most instructions will take a suffix that so add takes the L suffix。

 meaning we are adding four byte things。😡，And what this actually does is just like move。

 we've got kind of a source destination。Pattern and what that does is it will take destination plus equals the source。

 So this is a little weird。RightThis is not a kind of is know you might expect this to take three arguments and put the destination somewhere else。

That's's not how the hardware。 That's not how our hardware wants to do as it's not convenient for the hardware。

All of the arithmetic and logical units， like all of the instructions are going to look like this。

 It's going to be kind of a plus equals or a minus equals。

The other thing that is noteworthy here that you're seeing is RDX is the third parameter。

So here we do reference。Our pointer， so dereencing RDX means dereencing pointer。

 and we add that to PRm1。And the return value goes in EAX， we're turning in it。你说看。😊，Questions。

Question， what is2 in this case what's PR 2。 So what do you mean。

 What is it in relation to the point Yeah So right now， PRm2 isn't being used at all。

 It would be stored in in E S I。 I'll show you where I'm about to use it。

 But I I just wanted to write the prototype for the whole function。 now。

 does by default returns So the question is， does R by default returns in E X。 No。

 we should be very clear about what RE does。 Re does not do anything with。The return value。The。

 the rule for function calls is that if the function will return a value。

 that value should be an E A X or R A X， if I'm returning along or A X if I'm returning short。

 It should be an R A X or some subreister of R A X。 Re doesn't care。

 All Re does is it says I'm done with this function。 Go back to the the function who called me。

But it's not looking at the RAX。 What will happen， and we'll see this on Monday is that the function that calls Arif will look in EAX after it has called the function to get the value back out。

😡，That kind of makes sense。Yeah， so when we have local variables exactly does like treat it because not it doesn't seem like we're actually making a local variable to hold the result Yeah。

 so the question is how exactly are local variables handled because we declared it local and it's not actually being。

So it' not set aside at all。😡，With more and more complicated functions。

Local variables will need to get some space， and that space could come in the form of a register。

 We could assign some other register that we're not using。 There are， you know。

14 registers that we're not using， or I guess 13 right， that we're not using。

 and we could use one of them to hold our local variable。 But in this case。

 we're basically going to let EA X double as the register to store our local and as。😡，The。

 the place where the return value is going to go， which happens to be convenient because if I look at the code。

 I'm returning local。 So if I just put local in EAX， I'm done。

RightSo the compiler is smart enough to figure out where it should put the locals to kind of optimize。

 optimize for that， like， oh， you're just going return the value。

 then I'll just calculate it into EAX。 Oh， you need the value for some other function call down the road。

 then I'll put it in some other register。😡，And then if you have， for example， an array。

 we'll see that later， then you'll put it on a stack or something。Anything else？Great。😊。

So now' let's look at another operation where I'll do local two equals。 I'll do local minus。Pm 2。

Times。Rund one， just some little calculations that you can see here and'll return local2 here。And so。

 okay， these two lines stay the same， right， I could even。Let' that's。Let's dabble in the color eyes。

 So this， I'm not gonna to do this too often， but there's a button up here called colorize。 usually。

 if， if I do it too often， it's gonna to be impossible to read。

 So I'll turn it on very sparingly when we just want to see how lines of C mapped to lines of assembly。

 And here you can see that the two lines for。The Declaration of local are the same as they were before。

But now we've got this subtraction and this multiply。

 So we get the sub instruction and the I mole instruction， which are our subtraction are multiply。

 and those are mapping to the same。😡，To this， to this line of C。

 And so the kind of big takeaway point here is that。

One line of C may very well map to multiple assembly instructions。

 and that could just be because one of them needs to dereence a pointer。

 but it could also be because our expression was too complicated to fit into a single assembly instruction。

 We don't have a subtract and then multiply instruction。 We just have a subtract。

 and we have a multiply。And they work the same way as add。

 They work like they're minus equals and times equals。

RightSo the compiler needs to break up this expression and say， okay。

 what does it mean to compute local minus peram2 times per m1， Well。

 it means that first I have to do local minus perm 2， then I multiply by PRm1。😡。

And so it will break that up into these instructions。And it does， again。

 it does all the math on EA X。 I'm to turn off colorize now。

 It does all the math on EA X because it realizes that ultimately。

 that's where I want the return value to go。O。Any questions？I'm actually going to show you this one。

 This is a kind of a good place for me to just show you the how this kind of maps to。

How this maps to GDP here。 So here I've got the same piece of code。

 I hope yeah cool I remember the So here I've got the same piece of code as I wrote in Gcc Explorer。

 And one of the things I just you know our focus being on the translation process。

 GCC explore is very convenient for us to look at the code and look at how changing it changes the assembly。

 But at the end of the day， what we really want to know is I've got real C code， I type make on it。

 and I want to see some real assembly come out of that。 and make some sense of it。😊。

And so the best way we're actually going to do that is to go back into GDP and get that information sort of straight from the source。

So here's the code。 I'll justll。I'll go into GDP with it。

And I'll put a breakpoint on the arithmetic function。And I'll run。

And so here you can see the code running now。😡，This is hopefully familiar to you in debugging C code。

 But now how do we get GDP to tell us information about the assembly？ Well。

 I can use the a new command disassemble。And I can pass it the name of a function。

And it will show me the assembly for that function。

A couple things to note about the assembly that may look a little different from GCC Explorer。😡。

First， we've got these kind of addresses， so these are the actual of addresses of where the code is actually in memory。

And then you'll notice that we don't have the suffixes that we were seeing on the other view。

 We have a move and we have an ad and we have a sub。 but we don't have those L suffixes。

 So what's up with that。Well， if you look at the move， we're moving EDI into EAX。

Both EDI and EAX are 32 bit subregisters。Right，They are， they are4 bys wide。

 So if I'm going to move from one of those two to the other。That move has got to be a 32 bit move。

 If I wanted to move a 16 bit thing， then I would need to use DI。 If I wanted to move a 64 bit thing。

 then I would need to use RdiI。😡，So just from looking at the instruction。😡。

Just for looking at the operas to the move， I can。Dduce what the suffix is going to be。

 I know that this is going to be a move out。And I know that this is going to be atL because the destination is EAX and likewise for all so these other instructions。

😡，So GDP and a couple other tools are probably not going to show the suffixes as much。

 whereas as an Explorer you will see them。😡，你看。😊，The other aspectAnother aspect of this is that we can see that kind of this little arrow thing is telling us what assembly instruction we are currently looking at。

So this is so we are about to execute this move and so we can go to the next line of C code so here we're down here at local2。

 if I do the disassemble again，😡，You'll see that I'm， I've。In fact。

 executed the two lines that correspond to that， that first。That first line of C。And。

I can print out the value of local。But by looking at the assembly。

I also know that local is basically being stored in EAX， right。

 We saw that the calculation of Para1 plus D reference of pointer was being stored in EAX so I can print out the value of a register。

So I'll do that by typing print dollar E A X。 This is really weird， everywhere else。In assembly。

 registers are going to have percent signs in front of them。 And the dollar sign means immediate。

 right， It means it's a constant。In GDP， it is different In GDP。

 if I want to print out the value of a register， then I need to print。

 I need to use a dollar sign in front of the register name。😡，So here I can print dollar sign EAX。

 and we see that in fact， the value of local， which is stored in EAX。Matches here。

 so EAX contains the value 4， which happens to be the value of local。Now why is that important。

 why do we even go through this process， right？Who cares if I can just print out local。

 Everything's fine。 But there are cases where you can't。

 There are cases where you try to print out local。 You've probably run into。

 You may have run into a couple where you print out a variable and it says， oh， I'm sorry。

 that's optimized out。So what do you do Well， now if the function is really complicated。

 maybe you it might be a little harder， but if the function is simple。

 if it's one of your helper functions， if it's just a little point arithmetic。

 you could just you could pretty easily actually just disassemble the function。

Figure out where the value got calculated and just printed out。😡，Straight from the register。

Here's kind of a neat example of that。 Just's kind of，1，1 quick example of that。

 So let's say accidentally， I step through to the end of the function。

 And now I'm at the end of the function。 And I say， oh， shoot。I got to the end of the function。

 and I forgot to check what it returned。Like， what did this function return， You know。

 GDPV didn't print it out。 And I don't know。 Well， I know that whenever a function returns。

 if it has a return value， the return value is in EA X。

So I can just print out the value of dollar EAX， and that is actually you can look at the code and do the math。

 the code is in AS right now。That is actually the correct return value。

So we can use our knowledge of assembly and of kind of how the machine is executing our code to debug it。

 to kind of get pieces of information that asking GDP we won't be able to get。Y。

 is there really only one EAX per sort of computer or does each program kind of create a reing for that So the question is。

 is there only one EAX per computer roughly speaking， the answer is yes。

 but then there's a lot of hardware and software behind the scenes that makes it look like each of our programs has a separate set？

But internally on the machine， there really is one set of registers。

 and those are actually the registers that we're executing on。😡。

This is assuming a single core machine， I guess if you have a dual core machine。

 then maybe you have more registers and more stuff。That's the model we're working with anyway。😡，Okay。

 anything else？So that's just a quick kind of， you part of the goal here is just to show you that yes indeed。

 like the code that we're looking at in GCC Explorer is real， it's coming out in our programs。

 we can view it in GDPB， I'll come back to GDPB at the end to show you how we can debug something more interesting。

 but just kind of giving you a glimpse of how we can print out registers and kind of move around and kind look at what's happening in the assembly level。

😡，In an environment that you're maybe a little more familiar with。Right。Cool。So let's do。

Another couple of operations， I'm actually going to just to save some space。

 I'm actually going to cut this top。I will put the whole， I'll put the whole。

The whole piece of code up after a lecture， but I'll be a little more aggressive about kind of removing functions that I don't want to look at as much just to see。

So here， let me show you a couple of Biwise operators。Yes。Have it。I'll say Val is。

So I'll use a bit wise and with a bit wise nod， and I'll return vow right shift by two Okay。

 so a couple more instructions to be seen here。So here。

Just a kind of a intro to some more instructions， we've got the not instruction， which is Artilda。

So this is different from the negative。 This is different from taking a negative。 So not is bit wise。

Nigation， that's Tilda。RightThere's another instruction called NeG， which is the arithmetic negation。

😊，But。嗯。And then。And works exactly the way that ads subtract multily did， it's an and equals。

 which I've conveniently written that way。😡，You'll actually notice that the and is going straight into EAX。

 like there's， yeah， so basically。The compiler just decides that it doesn't need to put the value back into EDI just so that it can return it later。

 we're just going to do all the math on EAX again because that that's where the answer needs to go and then here the last instruction that you see here is an SAR that's a right shift。

😡，我看。But now， here's where kind of an interesting。Here's what kind of an interesting issue comes up。

 which is so I've been doing everything in terms of signed in。And you might ask， well。

 what happens if I change some of these variables to unsigned？So I'll change mask to unsigned。

And you'll see that the code did not。😡，Change。And in fact。I'm actually going to go back and change。

I could go back and change these local variables to unsigned。😡。

And you'll see that the code for that is also not going to change。

The reason and this was the motivation behind to's complement。 right。

 We spent this huge lecture talking about this fancy new way of representing sign numbers。

 and one of the big ways we wanted， one of the big kind of benefits we talked about with to's complement was that addition and subtraction。

 multiplication use the same logic as when we were representing unsigned numbers。 We can just。😊，Add。

 and。You know， whether it's signed or unsigned， it doesn't matter because。

that's kind of what two complementment was giving us。So as it turns out。On the hardware。

 there is not a separate instruction for ad signed and ad unsigned。😡，There's just one。 It's ad， and。

Whether you choose to interpret the result as a signed or an unsigned number， that's on you。😡。

That's on， I guess， the compiler， that's on the code。But it's not going to be up to the hardware。

So just another example of where type information gets lost in C， right。

 I don't actually know now which variables are signed and which ones are unsigned。

 I can't even tell if the parameters are signed anymore。😡，Right。But。There were a couple differences。

 recall between signed and unsigned numbers， and one of them was the right shift。

When I do a write shift of a signed number， we said that we wanted to write。

 We wanted to fill with a copy of the signed bit。 But if I write shift an unsigned number。

 we want to fill with zeros。 So if I make a change to unto Val here。😡。

You'll see that the code down here。Does change。That now instead of an SAR。😡，We have an SHR。

So what we actually learned is that SAR is what's called an arithmetic right shift。That is。

 it operates， it does the signed right shift where I fill with a copy of the signed bit。

 and then SHR is a right shift。That depends on that is kind of the logical or unsigned。

Version where I fill with。Zeroes。So in this place， right。

 So the hardware still doesn't know whether the value is signed or unsigned， but the compiler does。

 So GCC looking at this code says， aha， you have an unsigned int that you are right shifting by  two。

 I need to generate an S HRR。 whereas if you had assigned signed int and you write shift it by  two。

 I need to generate an SR。 So when it matters， the compiler will get it right。😡，Questions。ok。

So let's see。And so okay， so there's kind of this follow up to this。

 which is as we keep kind of going down more and more instructions， we're starting to realize that。

 you know the hardware is just operating on bytes， right。

 it doesn't really care whether those bytes are signed in or unsigned in or you longs versus pointers versus any of that and when we start kind of realizing this。

 then we start actually being able to do some really kind of clever things。😡。

So here Im going to actually do。I want to do something， I want to recall our discussion of the LEA。

Instruction。Well， here's something interesting that I could do。

Remember that we used LEA part of our as doing point arithmetic， we said， oh。

 I'm want to do pointer plus3， then will LEA to compute an address that kind of does and it does our point arithmetic。

 but what if I have just two ins？But actually， let's say I do something like PRm2 times4。

And then maybe I do， I'll just do， I don't know，5 plus。

So you can see that I've kind of written the code here in a very specific way。

 but it doesn't actually matter that I wrote it in that way。😡。

But here we can actually see what happened is we do generate an LEA。Now， this should at first。

 is's like， whoa， what happened there， Like how did it decide like why is that okay。

 I thought LEA was all about loading addresses。 We're clearly not working with addresses here。

 We've got two int， and we're turning an int。But what L A is really doing was it was just doing kind of arithmetic on seemingly addresses。

 at least as we presented it。 But addresses are just numbers behind the scenes。

 They're just integers。 Everything that we've been doing so far has just been mathed on integers。

And so we can do math on these integers using the same instruction。 So LEA here is actually going to。

Allow us to compute this。You know， this interesting， this kind of linear equation， right， I can do。

And you can kind of work that out， right， PRm1 plus PRm2 times4， plus this five in front。

And the compiler can to be pretty aggressive about using LEA when it can。

 it's just a really convenient way to just add a couple numbers together。

 and then I should note that it's also technically it's also possible I'm not sure how often it's really going to happen。

 but it's also possible for the compiler to use add instructions and use of the arithmetic and bitwise instructions that we saw to do the pointer R if we had some pointer and we needed to add some amount to we subtract some amount from it。

😡，We could totally be using adds tract。So all these instructions are pretty interchangeable in the sense that。

All I have to think about is what is the computation that I want to end up with。

 I want to end up with a plus B times 4。 Okay， LEA seems pretty good。😡，Yep，I so the question is。

 why does LEA use RDI and RSI here instead of EDI and ESI？LEA。By design this， these addressing modes。

 right， this dis placement and scaled index mode is designed for accessing memory。

 And so when we want to access memory our。Our sort of the。

 we're going to end up needing to use 8 by addresses， right， Our pointers are all 8 by。

 So the hardware is just designed to。To accept。8 by registers when doing any kind of。

Any kind of addressing mode， and that includes for LEA。

So you should not really see any E registers inside of these parentheses。

 inside of an addressing mode。😡，Now then maybe the follow up question is， well， hey。

 how does this work then， you're doing this math on eight byte things and you're storing the result in a4 byte thing。

 How does that have any meaning？😡，Well， what we basically do is we ignore the upper four bytes so we take the RDI and RSI times 4。

 add the five， we get some eight byte result， we throw away the upper four。

 we just stick the value into EAX。And that's going to be okay， might sound a little wasteful。

 but the hardware is really good at that， the hardware is totally good at working through going calculating memory addresses。

 that's like kind of what it's there for。😡，Right。So so it's going to do the math on the eight byte thing and then just throw away the upper floor and we'll be left with the EAX charge。

啊， there question。Re。So kind of the broad point in here again。😡，You know numbersumb are just numbers。

 types are not coming through quite very clearly what are we going to do so look at the context。

 figure out what is actually happening， you know， we could not really tell the difference between this math and then I guess the five kind of gives it away that this probably isn't a point of math。

 but if I change this to a four then it's much less obvious that this is not just some pointer math right？

I should also note there's something you can see in assignment 4 that you're only allowed to scale by so much。

 you're not actually allowed to put an arbitrary number in here。 So you can experiment a little。

 for example， with putting a different constant here。

 what would happen if I didn't have if I didn't have1，2，4，8， which are the only allowed constants。

 It's kind of interesting。 I' would recommend actually putting a 41 there and seeing working out the math。

 It's very surprising what the compiler does and how it gets us to the right answer The compiler is really。

 really smart about looking at your code and saying。

 how should I generate the right set of instructions to get us to the right answer and it's not always gonna be the set of instructions you expect。

 and sometimes you do actually have to just look at the assembly and really convince yourself。 Wow。

 that really does give me the right answer。 who have thought。嗯。Okay。Ai。Couple more things here。

 let's a couple more things on the kind of arithmetic side， so I'm going to。

I'm going to clear the screen and do something kind of shift gears a little bit。

 So if there are any questions about this， now will be a great time too。Yeah。

Oh that you the last athmatictic function giving this quantum term。Oh。

 so the question is like how would the compiler know it whether or not the last？

I guess with this function， the compiler is looking at the C code。😡。

So it looks at this C code and says we're not dealing with pointers。But it can still use the LEA。

 That's kind of the point is even though we're not dealing with pointers。

 we can still use the LEA to do just kind of straight math。😡，If we were dealing with pointers。

 the compiler still could use the LEA or it could use the addd and subtract and multiply instructions。

😡，But in assembly， we would not know。 We would not be able to tell the difference in assembly。

Between whether the function used pointers or not， unless we saw a de reference or something。你看。

All right。So one thing I do have to show you because it will absolutely come up in all of the assembly that we're。

That you're going to be looking at is what happens if I convert？From one type to another。

 So this is similar to the type casting idea， but I'm not going actually use casts because we don't need them。

 We're just generally looking at what do what what do I get when I say， take assigned care C。

 and I assign it。And I return it as an int。 So we need some kind of promotion here。

 We need some kind of conversion from a 1 B thing to a 4 B thing。And here we can see the instruction。

That gets generated。 It's a move， still is a move。And we can see that the move parameters look about right。

😡，Right， so DL is the one byte。😡，Subregister of RDI。😡，And EAX is the。

32 bit with a four byte subregister of RAX， so that's all consistent。

And then the B and the L are also consistent。😡，With what you'd expect。 So this is saying move。

 So move something。 B L means move from 1 by。Two，4 bys。And what's up with that S now， right。Well。

Notice that we have a signed care here。So when we promote it to an int。😡。

We need to sign extend it in those three。😡，Extra bytes that we have。

 you know that we now have space for， we need to put copies of the sign bit， our goal。

 when we promote a sign number to a bigger type， so we want to preserve the we want to preserve the value。

 So if it's negative， we want to keep it negative if it's positive， we want to keep it positive。

 So S means signine extent。😡，So move SBL means。Starting with one by。Sign extend it。😡。

And get me to a fourbte thing。And so we can actually compare。If I use a promotion， you。Oops。

 I always say hell。Look here。Of unsigned care。And if I here instead return an unsigned care to along。

 we can see that there's a similar instruction move ZBL， which is to zero extend。开。Butok。

And so one common place that this is going to come up and part of it is like， okay well。

 how often are we really moving cares to ints， well that's going to come up。

 but another place that this is going to be super， super common is when we do array accesses。

Because last time when I did array axises， I was using longs for my。My index。If I use。And int， oh。

 I even typed along， but I don't want to。I want to use an inse now。Aray of eye。

So if I return an ray of I。We do the。Scaled index calculation that you'd expect。

To get to array bracket I。But。Recall that all pointers are 8 B and that therefore。

 the moves are going to all operate on。Kind of the memory addressing is always done in 8 byte with 8 Bte addresses。

 So if I have。An integer variable and a4 byte int storing the index。

Then before I multiply it by4 and add it to the base address of the array。😡，I need to convert it。

To an8 byte value。 So here we see a move SLQ。Which following the same pattern， move S LQ means move。

4our bys。To 8 B。Let's sign extend。And that means that if I use a negative array index。

That will that it will actually get sine extended， it will stay negative。

 the multiply will continue to work。Alright。😊，All right。One more example。 All right。

 I'm just going to stick with this one。 Let's say I changed this to an unsigned。

Here's where kind of the wheels fall off here。I changed this to an unsigned。

 and you maybe would expect a move ZLQ， and that's not what we got。

And we actually saw this I accidentally stumbled on this last time。We get a move of ESI itself， what？

Right that like that can't be right， right， Maybe the compiler just doesn't know how to do array accesses with unsigned ins。

 Well， turns out， you know， GCC has been developed by you know so many people over a few decades now。

 And sure there could be obscure kind of edge cases that the compilerst know about。

 It's going to get array accesses right right So what is it doing here。As it turns out， if we move。A。

Four byte register。If we move of four byte sub or actually move if the destination。

Is a 4 byte subregister。Like ESI， this will automatically zero out the upper  four bytes。So yes。

 this is moving ESI to itself。😡，But incidentally， because the destination， because E。

 S I destination is。A is before four byte subregister， the upper four bytes get wiped。

 they get zeroed out， so this is essentially equivalent to move SLQ or sorry ZLQ if that existed。

 I'm not sure if it does， I haven't actually seen GCC generate that because it's much rather do this。

😡，Okay。That all right。Okay， any。So that' that's kind of all I have for the arithmetic and logic stuff。

 I'm now going to go on to control structures。 So if there's any questions about kind of just the arithmetic。

 the moves and the ads and all that now would be。It would be ideal for that。看。

So we've done we've we've seen just kind of how to do some straight line code。

 But straight line code is not very interesting in terms of， you know。

 it is not not you wouldn't really get very far writing code if you didn't have the statements and you didn't have loops。

And things like that So now we're going to explore a kind of different we're going to switch gears and talk about the control structures。

 we're going to talk about how to write those kind of classic if statements and while loops and so on。

😊，Now， by way of introduction， not because I think this is good style or anything。

 It's certainly not。 But by way of introduction， I'm going to start with a。What shall the go to loop。

我RPTR。Oh， thank you。So here we've got star PTR as well with that。And so I'm going to say， okay， what？

Cpss' going to get me here。So here you're not going to see this come up very much。

 hopefully at all in real code， that would be very unfortunate。

But what we can do is we can use this wacky statement called Go to。

 we can declare kind of a name with a colon and that will allow us to kind that'll basically make this thing so I can say plus equals one。

What this thing will do is it will。 So in C， I kind of have to introduce what this means in C where so we initialized pointer to 10。

7。 and then we。Execute this line。 pointer plus equals。 star pointer plus equals 1。

 So we incr the value that that pointer is pointing to。

 And then we go back to the top and we do it again and we do it again and we do it again。

 And there's no there's no end in sight。Unless。But so hopefully you'll ever see this actual kind of code in real see。

 but it's a good way for me to introduce a new assembly。Construct， which is a jump。So here I've got。

So on the assembly side， the label， so we don't have the name loop anymore。😡。

We have this thing L2 and what it's going to mean in Explorer。

 we'll see what this looks like in GDP later， but what this is going to mean is this is going to be a location that we will want to go back to later and so the way this assembly works is first we move 107 into into DF RDI and then we add。

😡，1 to it。 And this jump， JMP stands for jump， it says。Now， start executing instructions。😡。

From this label。😡，So we're going go back up and we're going to execute this ad again。

 and then we're going to execute this jump again it says， okay， now go back to that label。

 You're like， okay， back up to the label， do the a， do the jump back up to the label。

So JMP is what we call an unconditional jump。 There's no condition on it。 There's no， hey， I should。

 maybe you know， only do this in certain situations。And so will， and that's how we're going to。

And so this form of kind of jumping to a label with or without conditions is going to be how we move around an assembly。

 We won't just have like an if instruction。 We don't have a while loop instruction really what we have is we have these jumps that say now start executing code from this place。

😡，So let's see that in a much more useful way， the go to loop is not really the greatest example of actual useful sea code。

 so let's do that。😊，Okay， so what I'll do is I'll say。And then we'll go。

So I'll say if per Ramm is 107。Then I'll do。お。I。So here I have a classic just out of your basic C if statement。

And let's see how that's getting generated。Right so here you see the- so okay。

So a couple new instructions right away。 This is a little， alright， right。 So here， let's。

 let's go through it one by one。 So here we've got a compare instruction。 CMP means compare。

 We're comparing E DI to 1，0，7。 This is weird because remember that all of our instruction so far have kind of weirdly flipped like we did source destination when kind of everything else has been in terms of destination source。

 Yeah， we're gonna do that again。 So compare。😊，呃。B comma A is actually going to compare a。To be。

In this kind of direction， and we'll see where that matters now。 in this case。

 it's not a big deal because we're just using equals versus not equals， but。

So here we're comparing the value in EDI， which is per ram to the constant 107。😡。

And then we have a jump。 So if it starts with a J。 It's probably a jump。

 but it's not an unconditional one。 Now， we're not just jumping always。 We are J and E means jump。

 if not equal。Kind of the oddity here is that， of course， there are two separate instructions。

 So what exactly is happening is happening here is that compare will will do this。

 will'll do some of the we'll do the comparison。 It actually subtracts 107 from EDI。

 And based on that result， it will set。Some it'll set some flags。

 It'll just set another register kind of out out somewhere else。

 And then when we come along and do this JN E， we'll say。

 what was the result of the last comparison I did。It was the last comparison a not equals。😡。

And if the answer is yes， it was not equal， then we jump over this line。😡，And finish off here。

 you can see the LEA being used to subtract five before we return。So this is not。

 this is maybe a little different than you might expect if then to come out。

 You might have thought this， maybe you'd expect this to say， if they're equal。😡，Then do this thing。

 right， That's what the C code says。 If they're equal， then do this extra thing。

 But the way we're going to say that in assembly is if they're not equal， skip these things。

 It's much easier for us to skip instructions than it is for us to。

Go to some place and then come back later。 So what we're going to do is we're going to say， if if。

107 is not equal to EDI， then we will skip the ad and start executing down here。Questions about that。

O。Yeah， okay。 so now let's do another thing。 Let's， oops， I do want two parameters on this one。 Okay。

 let's do that。 I probably should have had these for。No。Alright， so I'll return  point2。

So here I want to show you now， Okay， so that was the if if then case， right。

 that was just the if with。Those just the if with。Without an else。

 now I want to show you what it looks like with an else。So let's say I do if PRm1 is， I don't know。

 less than five， so we'll see where that。and then so what did I do here， it doesn't matter。

Or with one， here I think I did an X or。Pround to X or。 Theres more instructions。

 But what's inside the body of the if and the the then and the L sections don't really matter， right。

 We're just kind of seeing the general shape， right， That's the first thing we want to do。

 probably the first thing you're ever gonna want to do when you get into a piece of assembly code is what is the shape of the of the of the code And。

 and we'll ask you for this when we get to the assignment for assembly is just what is in the code。

 What， and generally， what you're gonna be looking for are things like these jumps and these。

And the kind of like where we're jumping to and like， are there if elses， are there loops？

So here we've got。So。We got the compare。Just like before and we have a jump。

 you might expect JG to mean jump greater， but it's a little weird right， instead of doing a jump。

 we're not comparing to five， we're comparing to four。Why？Well， if。Pm。1 is less than 5。

Then the opposite of that。So if it's not less than five， then it's greater than four。Okay。

 so what we're actually doing is we're saying。If。Pm one。Is greater than four。

 this is where the kind of reversed。The reversed compare happens。 If per1 is greater than4。

 then we're going to skip。This section。And then we're going to end up down here。

So you kind of have to follow the labels， right so L6 is right here。😡。

We will skip over the then section into the Elf section。Okay。Now， what if it。

 what if we didn't take the jump。 So what if what if Para 1 was。Less than or equal to 4。

 which is equivalent to less than 5。 right， It's an integer。

 So less than or equal to 4 is going to be equivalent to less than 5 than what we do。

Is we do the ore。From the then case。 But now we don't want to execute the else section。Right。

 we have kind of two pieces here。 So we don't want to execute the L section。

 So we need this unconditional jump。 We're going to skip over the L section down here。

And then we do the eggg， the eggg is。Arithtic negation， so negative of that。

So we can see the difference between the if then and the if else with just a single。

 if then and no else， we can just we can do that with a single jump that just kind of skips over the block of code if the condition is is not met with the if else we've got we've got to kind of do this slightly more complicated thing where I check the condition。

Possibly by changing it up a little。And then I need this unconditional jump to skip over the else。

Question。Yeah so dot L is preserved so the question is is the dot L preserved to you you can't make a name in C that starts with a dot so the compiler just kind of uses anything that starts with the dot as just a way for it to use these are I guess are called labels so it's going to use dot L in some number for labels in GB and I'll show you at the end real quick with in G what it looks like you're not going to see these dot L things you're going see actual addresses but we're looking at it at a point before that so in this case we're seeing the dot Ls when we actually go through the disassemble we'll see what it looks like。

Anything else？你。All right， so now let's。Let's do。Let's do a loop。So let's do a loop。It while loop。

AndAnd。嗯。So here I'm just going to say， so this is just going to be some simple loop that's going to sum up。

呃。And then I'll say， and I。It's equal to one， and I'll just sum up the numbers from one。To N， right。

 So I'll say， well， why， while I is less than n， I'm just going to add。I。

 and then I'm going to increment。Increment it。So you can say， well。

 we could write this as a for loop， I'll show you what it looks like as a four loop later。はい。

So here I've got my while loop， where's just going to sum from the numbers from one to n。Yeah。

So let's look at that over here。So we've got them。 we've got the。Initialization。

 so here's where maybe where the well， okay， let let me just walk through。The idea here first。

We've got the initialization of。The variable sum and I，llistic got flipped。 By the way。

 It gets the compiler gets to initialize these in whatever order it wants。

 So it initialized the I it initialized I first and then initialized sum。Okay， or whatever。

 and then here's the body of the loop oh。I do something different。

 Im I actually have a return sometimes two to get that weird thing。😊，So here is the body of the loop。

H。Right there。Right。This is a little surprising， and。If we have a chance。

 we'll go into what it means， why this is kind of happening。

You might expect the first thing to do that we would want to do with this loop is the condition。

 and so you might expect the condition to show up up here for actually for optimization reasons。

 GCC will never generate that loop what it actually wants to do is it wants to put the condition down here。

😡，So okay， let's just let's trace through it right like the best we can do is just walk through the assembly and see if it's actually doing what we want so we're going to jump。

First， we're going to just unconditionally jump to L 9。 Just boom right down there。 Okay， well。

 so now we compare。呃。EDX， which is where I is stored， right。

 we can see that one got put into EDX at the beginning， so that's where I is。And as long as。

I is less than n。 So there's the jump less than。 We're going to jump back up。To L 10。

I don't know why I put them over。So that's the body of the loop。

 This section is the add and the add of the two values and then。😡，If there's no jump。

 even if you see a label， you're just going to keep going。Right， like the code。

 if there's no instruction that says go somewhere else。

 you just keep going straight like to the next instruction over and over。 So after this ad。

 we will go we will keep on going and hit this compare。Then we'll see this jump less。

 and if it's less again， then we come back up。😡，And then we keep going。 Then when we're finally done。

We've got this jump last if we're not less， if I is not less than N anymore。Then， we。

Don't take the junk。Meaning， we just continue and execute the next line。So I do a little。

 I'll try the colorize and see how that goes， actually enough。そう。Yeah， okay， that's。All right。

 I need to get rid of some of this code is circus。All right， well， then that's too bad。

That I can't get this。So now the color I should be better。Okay， it's a little better。

You can at least kind of see how the lines sort of line up here， you can see the two initializations。

 you can see the test kind of got split here。Right，So， so to do the test at the beginning。

 we need to jump down to kind of we need to jump down here。

 And then here's where the bulk of the test is happening。And then here's where the two ads are。

 right？Now you might say， hey， you know， I mean， you wrote this as a while loop， and that's cool。

 but。This is obviously better as a for loop。😡，Right because， I mean。

 you're just doing a kind of a normal increment and turn off colors will I change it because you're just doing kind of a normal incrementing counter loop like I was taught that four loops make more sense for the kind of normal countercontrol loop。

 So okay， fine， let's change it to a for loop and see what that does to the assembly。😊，对。あ嘟嘟て嘟。

And I'll do this， and I'll actually do it in place because otherwise the colors are going to get messed up again。

Then I'll get rid of this i++ now， right？Hey， look， the assembly didn't change。Right， not all。

As it turns out， there's not any kind of special assembly directive for。

F loop versus wild loop versus anything。If we have a four loop in C。

 it's just going to get translated as you'd expect to the while loop with an initialization of a test and update。

And now if I do the color eyes， it's actually going to be。

 it's a kind of a pretty interesting result here。Where you actually see that a lot of these instructions。

Are because of this forlo。So this line is responsible for quite a few of those instructions。

 but they are not in the same place。😡，Not only is there more than one instruction for this loop。

 it's here and here and down here and in here。😡，But that's what a for loop is， right。

 A for loop is an initialization。 We set I start with I being one。 It's a test。

And then it's an update。And so we can actually see those three pieces kind of split up。

 kind of splitting this。One line of C code into its constituent pieces when we've compiled it to assembly。

😡，Questions。诶w some。The question is why some set after I。

 because the compiler gets to make that call as long as both of them are initialized before we start doing anything。

 the compiler is allowed to do that it isn't really matter in terms of the functioning of the code。

 this is gonna be something that will address later on， which is， you know。

 at what point is what are the things that the compiler allowed to do。 And the reality is， well。

 if nobody's looking， the compiler gets to kind of assume you're not looking at the assembly。

 So maybe we're you know kind of playing some games behind its back here。

 But the compiler gets to assume that you're not scrutinizing every line of assembly it's generating and that as long as it produces code that is consistent with or it produces assembly that is' consistent with the code that you wrote as long as it does the right thing。

That it's allowed to kind of reorder things。 It's allowed to kind of change stuff up。

And so it just decided that maybe that was more efficient， maybe that it was just， I don't know。

 for some reason， it was easier for us to do that。question。ep， if you pre incr I of post increment。

 will that change the assembly So we can try that in C。

 certainly not in C plus plus pre increment post increments a lot different。但系。Yeah， I mean。

We're not actually using the result， right， So the pre increment post increment wouldn't matter。嗯。

Anything else。So I want to actually show you this in GDP。

 One of the big reasons I want to show you this in GDP is you'll notice。

If we actually tried to line up assembly instructions to line numbers， it's actually pretty hard now。

 right， we have know this， the admit of the for loop happening。

 and then we go back and initialize sum， and then we go back to the for loop。

Let's think how GDPV handles that。So I've got this exact code。

 I'm not going to pull up the code because the code is exactly the same。In the program control。

And what I'm going to do is I'm actually going to do this。

 let me put a breakpoint first on four loop。And I'm actually going to use this really cool layout。

 this is called TUI we'll introduce it to next week in lab。

 you'll get all the chances to play with it， but you actually get to do this in G where it splits up your window。

 showing both it's showing use of assembly down here。

 it's showing you the code up here and we're going to run it。So that we can actually get。

 we can get somewhere and you can kind of see。How this works， right， So here。

 the kind of arrow is telling us where。We are executing the instruction。

 There's a corresponding arrow in the assembly view， and the highlighted line。

 this line has yet to be executed。Okay。So here we can see the actual code that's being run。

 the assembly that that we saw of moving a one into。EEDX there。And presumably。

 that's executing on behalf of In I equals 1。Now， I could use step and next to move in terms of lines of C code。

 but that's not。But if we're trying to look at the assembly。

 we're trying to walk through the assembly instruction by instruction。

 that's not going to be as useful。 So we're going to use a different instruction now， S I or step I。

 they're equivalent， right。😡，It's just a short SI would be a shorthand。

 and what this is going to do is it's going to take me one instruction at a time。

 assembly instruction。So if I do a step I， you see that I' moved。😡，To the next instruction。

 And here's where you get to see kind of the weird thing happening in C code。

 just like we saw in GCC Explorer， we actually jumped back up。In C code。

And so if you were debugging this normally with a step。

 right weren't looking at the assembly and you just hit next and it moved to a previous line。

 You might have thought， what the heck， Like， why did it do that， right。神呢。

The executing mind as my code in the order that it's coming out， but。

We saw that it kind of didn't matter in this case。 So， and we look at the assembly and we see that。

It doesn't- it's generating in a different order。And see so now we can step I again。

And you can see that we we're now back to the for loop。And we're， we're， we're on the。

 we're on the jump。 Okay， so quickly， before I， I talk about the jump and how to read the jump。

 we can print out E D X。 We expect the value to be  one because we just moved one into E D X。

 which is I。And you can see that。The window is getting a little bit garbleled here。

You can see that EDI is one。Our EDX is one， I'm sorry。

So now we can look at this jump and we can say how do we read this jump， there's no convenient label。

 there's nothing that just says， hey， by the way， you know， jump to L， whatever。

 What we're actually saying to jump to is we're saying jump to this address in memory。😡。

So if I look on the left hand side and I look for the plus for the F， that's here。😡，Right。

 so this jump says， jump the next instruction that we should execute。 there's an unconditional jump。

 The next instruction that we should execute is this one。And then moreover， you can over。

 look inside here， this maybe a little bit easier to read the number off of。

 but it's so plus 17 is right there as well， so you can kind of match up either of those。All right。

So if I do the S。You can see that I am now， you know， I did actually take that jump。Oh yes， okay。

 so everything's kind of messed up。 G TI kind of gets into that situation sometimes you just。😊。

Have to do that to get better。 Yeah， good， good。 So sometimes it kind of likes to。

Gble your your window a little bit， maybe if you highlight stuff， I don't know。

 but if it ever gets into that situation， you can type refresh。

 and that'll just kind of redraw the whole screen。Okay。So now， in fact， we did， we did jump。

 We did not continue to the next instruction。 We went down to this4 FE。4 loop plus 17。

 and now we can do this comp and we can kind of keep walking through it so we can see that comparing EDX to EDI。

 so if I SI to allow the compare to happen， then，Wow， it really is unhappy today。

Let's go back into it， I when to get out of that with C X control A。

 and then we'll come back into it and that should actually help。Okay， so here we go， so okay。

 the compare。😊，Was ED X to EDI。 I'm reading it sort of the correct direction， right。

 So if I print out dollar EDX， well， actually， we saw it up there， it was one。

So I'm not going to print that out， but I want to do EDI。 I ran this thing with n equals 3。

So the compare- so EDx。Is less than EDI， so we will take the jump。So if I do an S。We do go back up。

 you see that we came back up to the two where the target was。F 9。And we can kind of keep going。

So here we could look at EdDX again。We see that it's two。Right， we come back up。 now we're at three。

 oops。Oh， okay。Let it go too far。 My God。 So I actually only use an n instead of a an either but。

So what happens after we what happens after jump， less the compare is no longer less than we've got EDX and EDI are both three now。

Right， and so now we just continue to the end and we go through this RE queue。 and then you see that。

 yeah， I know once we hit the RE queue， thats our RE， which is RE queue in GDP。

 then we're out of we will leave this function and then we'll go back to main and I will look at me。

Okay， so hopefully that give you a kind of rough idea of some of the control structures and some of the issues that come up there。

 if we when we come back， we'll talk maybe about a couple more little pieces that I need to get to and then continue with functional goals。



![](img/42523a147e29cdccacfe56fd2def77df_1.png)

Yeah， they should like。

![](img/42523a147e29cdccacfe56fd2def77df_3.png)

![](img/42523a147e29cdccacfe56fd2def77df_4.png)