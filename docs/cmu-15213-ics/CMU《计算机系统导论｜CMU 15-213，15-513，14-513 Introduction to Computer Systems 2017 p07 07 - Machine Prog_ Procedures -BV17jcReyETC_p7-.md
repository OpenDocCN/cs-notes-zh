# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p07 07 - Machine Prog_ Procedures -BV17jcReyETC_p7-

Okay， and the different branches。And the first thing we did was a exclusive war between the。啊。

Between register itself， so regardless of what the contests of the register are。

It's the if you take the exclusive order with the same thing， you get zeros。So this is clear。

 the zero flag gets set， this is what gets stored in REX。And since it's a non negative number。

 the sine sine bit is zero and so forth， all is good。So then we go to subtract one from that value。

We' get negative one， which looks all absolutely looks familiar。Okay so we're not。

 it's no longer zero， there wasn't the overflow that's now a negative number。

 and this was the one we had the question on the last time。So here。

 the way to think about this is that the。For unsigned arithmetic。There's a notion of a carry both。

Carry out on like an addition and a borrow on subtraction。

So the fact that we had to borrow off the edge of zero in order to have something to subtract one from meant that the cur。

Where I guess the currie borrow flag you could call it is set to one。

And then we do this comparison instruction where we compared two to here， and as it says here。

 that's the effect of that is to take the context of RX and subtract off two。Okay。

 and so you get minus1 minus2。So get minus three。Now because it's the compare instruction and not actually a move。

 it doesn't alter the destination， so REX stays the same。Okay， but now we have this s flag set。

And the sign condition for like and all the rest attorneys zero。And then we go and we do this test。

 so a set L is less than comparison。And it's satisfied when the assignment is set。

And not the overflow or vice versa， in this case， that's true。Okay。

 and the set instruction puts the result in。AL， which is the lowest lower to by of REX。

 so you can see that's why there's a 01 right here。Okay。

 but important property is that these instructions are for sort of。

Taking advantage of the condition codes， they don't set the condition codes themselves。Therefore。

 none of the condition codes are changed， they're left。As they were here。

 it's similar to like I said， an LEA instruction doesn't affect the condition codes。

 so if you had an LEA instructions say after this compare。

 the condition codes would remain what they were as a result of compare。All right。

 and then we have this。This zero byte extension instruction， which zeros out on the remaining bytes。

And again， it does not change the condition code。可以。谁的快系上来？Yes。

Ale is if you remember our register picture。So like if you have REX。好 you。And this lower half is EAX。

And the lowest bite of that is。The same。Okay， so it's specific to REX。哎呀 what。The A。

 I'm not exactly sure you question is， the A only overwrites this last bitete。Okay。

 and then this this instruction here moves that basically what's there， the01 into EX。

 which is the lower bits here and the also zeros out the rest so you get all these zeros here and you get the。

This biteてま。Any other questions， yes。おさんの。どですか。So CL is shown here in this table。It's a based on。

Whether this condition is satisfied or not， the exclusive or the sign flag and the overflow flag。

 it puts either a zero for false or a one for true in whatever the destination is。

 in this case it's a。没有。Okay， so that's why you see it over right。

 it's just that one last bite of the REX。Yes。No， no。It only overwrites the lower the bite。

 so whatever's here， the rest of it is unchanged。Good。And return to our。Thank scheduled programming。

 here we go。

![](img/e471d22333d51ce3504428899066e191_1.png)

![](img/e471d22333d51ce3504428899066e191_2.png)

All right， so this is the third of five lectures on machine development programming。



![](img/e471d22333d51ce3504428899066e191_4.png)

And we're going to talk today about procedures。Specifically。

 we're going to talk about the mechanisms， sort of the big picture mechanisms involved the procedures。

 if you've thought about languages like C， you have sort of a notion about how procedures work。

 this is going to look at what's going to happen at the assembly code level。

A key component of this is going to be the stack。Okay。

 so we'm going to talk about the structure of stack in the X8664 architecture。

We're going to talk about the various calling conventions。

 how some of which we've seen in lectures so。But here we're going to give sort of the overview of how it works altogether together。

Passing control to precision that arere called passing data。Arguments and so forth。

 managing local data， that's data that the procedure you've called is allocating。

And then we'll look closely at the cursion。All right。

 so if you kind of list all the things that need to happen in order to call a procedure。

There's the notion of passing control so you're you're flow along in the program and suddenly see this procedure call and so now you' got to move jump control to where that。

Thecure starts。So thats of the arrow shown in red， and then after that function。

 that procedure completes， you want to return back to right where you left off okay so it's the very nice instruction after the call and that's the arrow。

In terms of data， there's the argument that get passed。Any procedure？Into the function。

 and that's in showing who they are in blue and then if it returns something。

 there's the return getting passed back to the regional collealie。There's memory management。

 so notice that this procedure allocates some local。St。And we need to handle that carefully because。

 particularly in cases of recursion， this exact same procedure is going to be called again and again and again。

 and so you want a separate iniation of this local state。Okay。

So those are three components they're all going to be done and we'll show how they're all done in machine instructions。

Now， one thing to note is that the not surprisingly。

Compilr writers try to use as few instructions as they can。

 and so any part of a general calling convention is not needed that can be shortcuted without affecting correctness。

Will be done， okay so the only parts that's actually needed will be materialized。

And this whole API that we're to talk about is called the applicationp binary interface or ABI。

 and it's just a convention。All right， stacks。So if this is our memory。

 we have a big long chunk of memory。Then different segments of memory are going to be allocated for different purposes。

 okay there's going to be memory that where the code resides。

 there's going to be memory where he data where globals reside and so forth。

 but today we're going to talk about the stack。So if we look at the stack。

We see that in the way we think about。X8664 stack， the top of the stack is actually down here and the bottom is up here。

Okay。And this arrow in the case at the top is the direction you go。 So this is sort of a。

 you this boundary here。Is once it's set up， it's fixed。And basically stays there。

Unless there's some issue where you run out of memory for your stack then you have to relocate the whole stack。

 but in 99% of all your programs， that's not going to be issued as plenty of space for your stack and so that part will stay anchored。

 stay fixed and what happen is the top will jump up and down。An important register is the RSP。

 which points to the current top of the stack。Okay， so as I mentioned， the stack goes down。Okay。

 and if you think about the address space， it's important to note that the address increased going up Okay so if we were draw all of memory that you know the 0。

0，0 address would be down way down here off the page and you know the。

The maximum adjust would be way up here。Okay， and the reason that's important to know the convention of the machine is because that tells you whether you want to subtract from the stack。

Point to register。Or add in the stack point of register。All right。

 so there are two instructions in X86 that are specifics for stack， a push and a pop。

 as you can imagine。So push instruction takes a register。And it fetches the opera at that source。

And have an animation here？So if there's a value that that say it's a register or whatever it is。

 but there's a value in that register， it gets put where。第一。

The stack is advanced by one broad word and the value gets placed there。Okay。So you fetch the value。

 you decrement the stack pointer by eight， so it went from here to here。

And then you write the address at where the stack pointer now points。

And the notion is that basically where the stock pointer points on this way is all in scope valid values for the executing code and everything on this side of it is garbage。

Not to be used。嗯。Without serious correct his concerns。All right， the opposite of push is the pop。

 so it's supposed we have this value here on the stack and it's a top if you call the pop instruction。

Then it takes that value。嗯。The value is there and increments the stack point by eight and so again。

 because there are increasing addresses， incrementing will push it this way。Okay。

 so pushes it that way。And then that's effectively saying now the stack point points here and the top of the stack is now。

Here。Okay。All right， and that destination should get the value it's put in the destination。

 which is typically a register。Okay。Okay， so notice that you know， as I mentioned。

 the stack point of changes， but you didn't you know this。Stuff in here。Is left alone， Okay。

 it's viewed as garbage， but it's still there okay and so this is。嗯。有。

Something to be watched before when you're programming。

 it's also something that can be used in attacks against the machine if you're not careful。All right。

 so that's talk about the stack。All right， so we're going to go through the assembly code for some very simple functions。

And this will be， one of them， we'll go through this in some detail。

 so we have this procedure function boltt store。That takes three arguments。And calls mot2。

 And here's Mo2。Mter takes us two arguments， multiplies and returns to the result。

 and then mold stores stores that result in the destination at the address point past to。

Okay and what this gets translated into is these five six instructions。

The mole store and these three instructions for Mo。And will。You know。

 if you haven't seen this before， it's kind of a mystery， you know， doing we're pushing something。

We're doing this move and we do a call， then another move and then a pop here and here' got。Well。

 there's our multiply and return and so forth。And what makes us all low overhead is the conventions about how the registers are used to pass the arguments and to return the results。

 so for instance， as we've seen in previous classes， REX is used to store the result。

 so that's why when you pop back out of it，You know that the value that returned from this call from this procedure is in REX。

And similarly by our convention that the first argument is always an RDI。

 and the second argument is always an RSI， and the third image argument is always an RDX。

You can see that。嗯。You know here's your RDX。Get used here。

You can see there's this shortcut here where because x and y are actually passing in the proper order for A and B。

They are already in RDI and RSI form multitu， so we don't have to put them there。Okay。

 so that's why there's very little going on before we make the call and then the stuff is where we want RDI and RSI。

And so forth okay。So that's the kind of thing we're going to talk about today。

And we'll do it in one seven at1。So the first thing， of course。

 is that we talked about is the control flow。So here。The call instruction now， I mean。

 symbolically it's mo2， but once the code is loaded， there's some addressing memory。In this case。

 it's this address here。Where more to the code for that result？Okay。

 so the non symbolic version of this routine says， I wanted to call and this is where the function starts。

 that exact address。Okay。2。So in our current state， before we make that call。

 or we're about to make the call， this remember RIP is the instruction pointer。

 so this says the program is currently executing the instruction at this address or is about to execute instruction this address that's right here。

Okay， and stack pointer is pointing to0 x12， so it's pointing to the bottom element right there。Okay。

 so we're all ready to go。Then what happens？Well what do we want to happen so what we want to happen is we want to take this value here。

Which is where we're trying to jump to。And put it in here， right？So that's where we want to go。

 so this after we're done， should point here。Okay。And。We also need for。Some way to get back。

And the convention on how to get back is that you put the return address， where to come back to。

 you push that onto the top of the stack。Okay， so after we're done with this procedure call。

 the next instruction we want to execute is this one right here。

 and so therefore we want to put no 400549 here。Okay， we want this to now point。谢谢。

And that's basically what this is showing。that the stack pointer now points here as the post up here。

 this new item we just pushed on the stack points to where we're going to jump and turn back to after the procedure is done and the instruction pointer points to the start of this。

Okay。Where is' in that。Yeah。It's that malfunction， so where are the function bolt to？

Happ to replace the another。All right， so now we we chug along through this procedure and we get to the end。

 okay， what do we want to do now？Well， we see this return。This return says， go。

From where you are now to whatever the return address is， which this guy here。 So look at the。

The stack winner。And find this return address， and that's where I want you to jump to。Okay。

 so that's what happens this the instruction pointer now points to where we wanted to go。

 whichs the instruction after the call， and this is back to being at x 1 or 20。O。啊。

AnyAny questions on that， yeah。The the。The return address yet goes on the same。

Same stack as everything else okay and again that's。Potential weakness for attacks。

That you'll see when we get to T La and things like that。嗯。Yeah。The。RBX。Not necessarily， no。

So here we're in a case where RP。Was pointing to the return address。The S winner。

 the church just to the top of the stack。We'll see more general examples。

Maybe you're thinking of R or maybe I missard you're thinking about RBP。So we said。呃。We'll get there。

 We'll get there。So on that first example yeah， so there's no RBI， oh， I said here。下一。

So it turns out that RVx is where we store the。That had to do with the function cell。

 turned out where we stored。The address of where we wanted to put things was an RBX。Okay， so this。

 whatever what this address was。We stored an RBX so that when we returned。

 we would take the return value and store it at that address， so that's happening here。Okay sorryrry。

 I hadn't realize that RVX was on the slide。Okay， so the big picture about arguments looks like this。

 basically the first six arguments we've seen in this case several times we saw this case today。

 after that it goes to RCX， R8 and R9。And as like we said。

 the return adjusted AS So if you have more than six arguments。

 then and only then do you start six in arguments， you start placing them on the step so if there's a seventh and eighth argument。

Up to end。You' place them on the step。Okay， so that's much less efficient。

 but most procedures have six or few arguments， so we're good， yes。What is that what？我生 do。

It's just a chunk of memory。So somewhere in the address space。Memory starting from address to 0。

00 up to。The maximum address。There are regions of memory for things like code， like po code。

 for library code， for memory the operating system uses， there's heEap， memory for the heap。

 which we'll talk about in another lecture， and there's also memory for sexs。Okay。

 and so it's just from where the bottom stack。And it grows down from there。Okay。Good。Okay， so。

So these are our procedures again， here's mold store， here's mold two。嗯。And again。

 the convention is that the first argument is in RDI， the secondar side， the destination。Is an RDX？

And when you get back， the return values in REX。Okay。So。So one thing you'll notice here is that。

 and then similar to that， we know that。Is your past year in this is the aspect？So。系い。

So one thing you'll notice here is that。We had this RDX。And we're about to do this call。

And there was concern that this procedurec' callinging may actually need RDX itself。

 maybe it calls something with three arguments so it needs RDX itself。

So to make sure that this value that we're going to need when we get back isn't trampled on。

 we stored in another register。Our RB x。So that when we get back from this call。

 it's safe and hasn't changed。All right， so and we'll talk about the conventions。

 different ventures have different conventions。We know based on the convention around RBX。

 that it doesn't get trampquiled by anything we call it。第 right。Okay， so as I mentioned。

 we want to be able to support and conversionion。Okay。

 so we want to fire functions that define some local variables inside them。

 and we want every time we call that function。We want to make sure it's its own piece of memory right so if it calls itself recursively。

 it's separate allocations。Okay， and again， we're going to do that on the stack。

There's a notion of a stack frame。Which is just， you know， if we've got our stack。

Rrining down and we're currently here with our stack pointer and we stick the return address。

You hear。And now we're getting ready to call another function。

It's going to have some spa and the stack for the stuff it's doing okay and that's called a frame。

All right， and so local variables and such will get populated in this area。And then including。

 you know， if it tries to call things and so forth。

But then what happens is that when this function returns。We just。

Get rid of the whole frame by just moving the stack point back to where it was。

So if the stack pointer is here and we return from this， it pops back way up to here， okay。

 and then we can throw another frame on here and so forth and we'll show an animation of that in a second。

Okay， so let's suppose we have the following routines， call chain example。

 we have a function U that calls who and who makes two calls of AMI and AMI is actually recursive it calls itself。

All right， so what's it going to look like？Okay， so so an example might be you know you calls who。

 which calls MI andcurs calls MI twice， and then stops and you come back up and you get the second call of MI and then you stop。

All right， so we've got this notion of a frame， so this is the previous frame。

 and here's the frame for the procedure we're dealing with now。

And it's going to contain local storage， return information， temporary storage。As needed。

And you're going to set it up。啊。There's going to be some setup involved in terms of pushing arguments beyond argument 6。

 like argument 78 onto this frame。And then you'll do the call and then when you're finished。

 it all unraveled， okay we'll show example here。So we're in you。Okay。

 and now it gets to the point where it calls who and so now we have the frame for who。

And the stack pointers always to the。The top of the stack here。Now theres this。

 there's this another register， which is RBP， which points to sort of the other end。

Of this frame okay， and that register is optional because if you you know it's。

It's typically only needed when there's a variable amount of stuff that's going to be put in here。

Okay， if the compiler can't tell how much stuff you're going to put in here。

 then in order to find this return address that's going to need to jump back to you。

 it needs to know where this frame started。Okay。So if I'm here and I put the return address here。

And now I call，la bh blah blah blah and I get to the end and now I'm ready to return， well。

 I need to get jumped back to this place here。Okay。

 so I want to take whatever the current stack pointer is， and I want to move it to back to here。

If the compiler knows exactly how big the frame is， it's just simple rhythmthtic。😡，I know I' put you。

Eight bytes of stuff on there or 32 bytes of stuff on there。

 so I just wanted to subtract off 32 and I know exactly what it is。

It's primarily in the cases where there's a variable amount of stuff that gets put on here that first weather will do is it will jump back to this。

 it will reference the base pointer to find out where it needs to。To revert the stack point or two。O。

But again， that's typically you won't see it because it's optional。All right。

 then who calls am I and you push that on the stack。

And AMI a cursor calls itself and AM calls itself a gap。And so again。

 if there's local variables to find an MI， you've got distinct copies of it in each of these recursal calls。

Yes。他这些。第二组。Exactly， exactly， so if you， if you need our RBP。

 if you're going to be using RBP more than once， then you want to squirre it away on the stack so you can you can。

Right you need like after you're done with this one。

 you need the RBP for this one up here right and so the place to put that is on the stack itself as well so you squirre it away somewhere here so you can find it。

Re。Yeah。RBX will。So were going to talk about that， we'll talk about the conventions on registers towards the end of class。

So you can hold off your question until then if it's exactly， yeah。Base pointer。AP。Yeah。Okay。

 so then let's suppose there's no more recursive clause of AMMI， so you just pop this off。

And move on to APII and pop again。Again， and now we get to the second call of MI。

And so you just push it back on。You done with that you done with that。Okay。

So let's look at a little bit more detail what's inside a frame。And again。

 in very simple cases there's almost nothing like an example at the beginning of the class。

 basically we had a return address and that was pretty much it。

 there was no need for any of this other stuff because everything got passed and registered so we were happy and there were no local variables。

Okay， so but the general case is that you have all the arguments beyond the61。

Any local variables that need to be fine， and then this notion of any registers that you need to squirrel away。

呃。So that they they don't get trampled on。We'll talk about that towards the end of class。

 and then as earlier question you have the old value of RVP。If you know， if you're using RVP。

 then you want to scroll away they will value that okay， so we have the return address。

 which is part is it part of the caller frame and then the callee。

 which is what's getting called has。And all the stuff。Okay， because I cover all this。Yes， okay good。

这一块系讼的。All right， so let's look at another example， so this example， you've got two arguments。

And you're going to basically fetch the value in P and add it to this quantity of v and then store the result back in P so basically whatever is stored at location P is going to be increment by the value of v。

Thank。So what does the Senate look like looking like an assembly code， well， again， so RDI。RSI。

 right？So RDIs here saying， are going to move。Fettch what's in RDI and stored in RX okay， so now X。

Whatever is x here is now in REX。Then I want to add。That value to RSI， which is the second argument。

 so that's taking x plus v， and then I'm actually tramppoling on RSI and putting the result in RSI。

Then I'm going to take move from our side。Basically do the store， the store through the address。

Again， okay。So it's just loading the address through the ad in store back。Okay， in return。All right。

 so there's a very simple case， there was no local variables to。呃。To worry about because。

We managed to get everything in registers。OkaySo even though the code shows local variablesable。

 there's nothing to allocate on the stack because we managed to get it all in registers。Okay。

 so very efficient， right？Very efficient call return。All right。

 so let's look at something that calls that procedure， so let's suppose that we have you know。

15 to 13 and。For some unknown reason， we want to add 3000 them。Okay。嗯。And then once we've done that。

 then we actually want to sum those two numbers together。So what do we do？

So the first thing we want to do is we want to you know。Move the stock pointer。Okay。

 put the return address。And。We're going to。Move this value。On to the stack。Okay。

And then in particular， we're going to move it。You know， eight plus the stack point。

So it's kind of first we subtract from the stack pointer so we move in one fell swoop from here to here。

Right from here to here。And then we do arithmetic based on additions off the stack pointer。

 So instead of like a series of。Push， push， push， push， push where the stack point keeps moving。

 we just jump the stack point to a place that's useful。

 and then we do relative addressing off of that。So then we're going to move our 3000 into RSI。

And now， and we're going to put the address。That we want to pass tocrement member increment takes an address and a value。

We're going to use LEA for actually what it's intended for， right to load effective address。

Put that in the register， then we do our call。 and then when we get back we now have。

The result of the increment is in REX from the call and this thing here is 213 is we swirled away on the stack so we have it there。

 and so now we add it。Okay， and then we return this back。All right。

 so I think there's a little bit of innovation on this。So the， the。

So in order to get ready for these two arguments。Again， we put the one argument in。So again。

 it's in RSI， but since this is a small。Valud fits in 32 bits。

 we use the smaller form where we move on a long 32 bit quantity into ESI。So again。

 like the other registers you've got。Our size， the whole thing。And ESi is the bottom part。Okay。

And then we load the effective dress， so now we're good to go。Okay。S， and I already mentioned that。可。

Okay， so now we do this call。Okay。And when we get back， we know that REX holds our return value。Okay。

 and so again， we're going to add。So that's this part we're going to add in。

What we squirreed away on the stack？Did you do。And you can see our answer。

So now we know why we added 3，000 to 15 to 13。And then we have this weird thing that doesn't make any sense for in terms of course numbers that we add those two things together。

And we the stack point of where it was。All right， any questions on that， yes。注意。経済し。嗯。小张。啊。

Because we're dealing with a 64 bit。Sorry。So in this particular example。

 it's not clear why the compiler did this。The codes that are showed in these slides are actually codes you would get on the shark machines。

 right？My guess is that it was。It was for some sort of alignment issue that basically wanted to align the。

The stack winner at。It's 16。嗯。Or if this at。嗯。If there had been a。

Return address or something like if this function called something else。

 you would have had a space for it。I don't have a good answer for that。

 but for some reason that's what the compiler does。

A lot of times it's either for alignment purposes or。Or just in preparation for。

For possible other uses。I a question though。Okay以。All right。

 so now let's get to the register saving conventions。So again， we have the notion of a caller。

And colgue。And we have these registers that they both want to use。So here's like a bad example。

 suppose we had moved you know， 15 to 13 into RDX。And then we expected to be there when we got back。

 but for whatever reason this function procedure we call oss RDX。

 so it would trample over what we wrote before and we would get the wrong answer。Okay。

So we need some sort of convention， some sort of agreement。And so there's two choices， right。

 One is that the the if you're。If I'm about to call a function， if the caller。

Once some registers when it gets back， it should do the work。

 of setting those values aside in some place that knows the col not going and all its descendants aren't going to trample。

The other option is that the one you're calling， like if I call the function of food and food is going to trample on some register。

 itd better make sure that it saves the old value and restores it before it returns。

 that's the difference caller saves。And call he。Okay。So again， it's just a convention。But okay。

 so we talked about this， the return value， the arguments。And then there's a couple of caller saves。

Teoughers。So Reg 10 and Reg 11。If if you want those values when you get back from the procedure。

 the caller has to score them away on the stack and then restore them。Okay。嗯。Okay。Similarly。

 for all these guys， if I have something in REX， I'm about to call a procedure。

 call that procedure or one of its descendants is likely a champ in REX。So I have to。

 as a call our safest right and similarly， the function of calling may have arguments and it wants to use these registers。

 it may call other functions and have arguments。So this is also color shapes。

So all of these registers here。If you want their values。You know。

Maintain across the call then the caller has to score them away in the stack and restore them when the gets ready。

 or score them away in somewhere else。And that somewhere else can be these call saved registers。Okay。

 so call say registers are registers that as the caller。

 I don't have to worry about them I could just leave stuff in there and it's the callee's responsibility to store them to restore them to their old values so we had that earlier example of RBX。

 the reason that RBX was chosen as opposed to say scrolling away something on the stack。

 which is the other option。Is that if the call E tramples on RBX it's got a first saveguard value in the restore。

 so from caller's perspective， all these registers are unchanged。Okay。嗯。

And the stack point is sort of a special case in this， right， so we know that。

When you pop back on the stack and it's kind of where you left it。Okay， so it doesn't。嗯。Okay。

 any questions that before the quiz， yes？Instead of having。Well。

 you need a convention because if you remember。Functions can be compiled separately。

And so the compiler may not have the full picture of what's going on。

 the runtime can link in libraries that you didn't write or the compiler had no control over it whatsoever。

 so you need a convention that works globally that all architecture is conform to so that you can do it when you don't have information about the other side。

You're right， if you had perfect information， you could cheat， you could break this convention。

But the general case you don't have perfect information。

 it's just usually to consider good practice to stick to this convention yes。All right。No。So， so。

 so the so。嗯。So these are caller saveds， so if I care about the values of R 10 R 11。

I either put I should score them away either in call save registers or on the stack。系い。

Because there's no guarantee that any of these are going to be the same as they were when I get back So if I care about the value。

 I better stick it somewhere so I。So use our。や生です。They'reRight， so you。You call。If you call multiply。

And then when you return from multiply。嗯。I mean， if they're still squirred away on your stack。

 for instance， you've still got them saved and so when you call the ad。Ad can traple them as well。

 if you don't care。If multiply calls a， again， ads multiply it's got to save these contents of the registers。

Since a caller saved before it calls at。And so it all just sort of works out， right that basically。

你 know这。2。So let's do the quiz。K。The this time。Yes。Yeah， you should read the back point first than。

Yeah， it's just a adventure。Because you want to be able to say that everything from the stack。

I think for the stack pointer。じゃ。那个是啊。This is a business scope and I guess we' didn it work。二搜。

I think people did pretty well in this quiz。Yes， I checked。Person is not love。Okay。Allright， so。

MG的的 good。Right， first six arguments， Jordan registers。O。And。Right。

 so only for the sort the last one is only for the。Callee。

 save registers that the function can assume the value is preserved across the call。

The collarer ones， they can allow to be trampled，Okay， any questions on the。不。



![](img/e471d22333d51ce3504428899066e191_6.png)

![](img/e471d22333d51ce3504428899066e191_7.png)

Okay。All right， so in this example we have this procedure a 10。Which has 10 arguments。

And so where are those arguments passed？You know， if we look at our。Our cheat sheet of the registers。

They're passed in the first。Six are passed in registers and the rest on the stack。Okay。

 and so we call that and now。Where are these registers？Well， if you look at this。

 what it does is adds the first five of them。 So the first five here。Are still where they were。Okay。

嗯。And so the question is which registers do we need to save？Okay any ideas？Well。

 it depends on what the compiles are doing， okay， so basically。

After making this call on the first five arguments， it's got a setup。For the second five arguments。

Okay。And。Which means that it's going to have to do some shuffling of the arguments， right。

 so basically。Right， you want。Because they're not in the right place， right？One， two， three， four。

 five， so。R nine， for instance， is where。A5 is。可以。So we've got to be able to move that into。嗯。

RDI and so forth， right？呃。You know it's kind of an interesting example and I'm not going to dwell it。

 but you can look at it later because they all come in and registers yet and the first five are perfectly placed but the next five aren't and because of that we're going to have to shuffle them into the right registers and because of that we're going to have to squirrel away some of the values that we don't get trampled and we do that。

And you could take a look at the code later。Although I will point out one thing。

 so remember how I said that you push the。The stack point， and then you reference things。

UpOff the stacks， so you can see we have 24 off the stack， 32， 40 and 48。

For these different things that are being scored away。

So you deced a large amount and then you do reference of positives。

 so you'll see a lot of that in your code。嗯。Okay so we have this X right。

 and we're going to need it when we get back， but it's currently an RDI and RDI is going to be used as for the first argument here。

Okay， and this is one of the the。Okay， so。What's going to happen is that we're going to。

You know push。嗯。RBX。And then do all this。Okay， so we're going to want to squirre away this value of x and RBX。

But since RBX is a callly save Reg。This function has to squirrel it away here and restore it at the end。

Okay。So from the perspective of this function being called。

 it's responsible for the call save registers， so it's responsible for RVx。

So that's why you see that， and so then it's safe to trample it internally and do all the stuff it did before。

Okay。嗯。So that's what happens You do the stack pointer。It gets saved here。

Now you're going to subtract 16 off the stack winner， as we showed you before。Okay。All right。

 and we remove that there， we also have already watched this。嗯。Okay， the attorney result。RX。

And then add 16。To get the stack pointer back there。Okay， now we can restore。

Are the squirre away value of RBX and the RBX？And then we are ready to return。可以。All right。

 kind of went through that a little quickly， but we sort of I went through it slowly。嗯。

At the beginning when I first introduced the example。

But is that too fast or is there questions on that？Yes。よし。他呀。

You're saying that the code here is different from the code editor there。And那你对。

So we returned from anchor。And the value of V2 is an RAX。So we have the value of V2 and REX。

But this ink two。Wants to return the sum of x and B2。So before we had to code for In。

 this is like ink to it， does that and then does the addition。And so that's why we want to add。

Add the RBX onto what we got returned。So the X came in。We save the registered。

 we squirrel away the value。Of x in this Reg RBX。Then we knew it was there and so when it came when this value returned from In。

 we added the two together to get the desired。没。This additional ad here is because of this ad right here。

Other questions？Okay， so。Yeah， it's just showing the。

The before the pop and after the pop that restored RBX。

Re shortd whatever the original value of RBX into the register of RBX。Okay。

 so let's look at app in recursion。So for recursion， we're going to use this example of a。

Of a pop count that donecursly， so if we're at zero， then we would return zero else we。

Take the and so we basically grab the last bit， the least significant bit。

 and add that to the pop count of the rest。so we shift off that bit and we recursively call Pcat and so again。

 if this last bit is a zero， then the popcat does increase， if it's a one。

 then the popcat increases and so as we go through， we will count if the number of wins。

So this is what the code end up looking like。All right， so we start off by saying， well。

 if we're going to return out of this thing， we're going to want a zero to return。

 so let's go ahead and do that。嗯。And now we're going to do this test。

 and so again we do the test instruction。Which。Do you remember what that does？

It takes his two arguments and does watch them。Hands up， okay。So that's。

You know that's just going to return the thing again and so basically you just want to know whether this value in RDI is zero or not。

Okay。If it is zero， then the JE condition is satisfied and we will jump。

Out of the loop and return to what we've done。Okay。On the other hand， if it's not zero。

 then we're going to do save RBX。嗯。And we're going to move。The current value of X into RBX。

Then we're going to do this and。Right， end one with。

With EBX and again it's a little bit tricky because they're doing the shorter forms of things right this is equivalent to an and quad of one and RBX。

 but since they don't need to use all 64 bits， they use the shorter form。

Then you've got your shift right， right， which is this here。

And then recursive call based on the now shifted argument。When you return， we have。You know。

 we have the value。That gets returned and we have the value that we score away。

 and so we add those two together。And then we restore what was in RVX。And then。All right。

 then we return。可以。😊，All right， so again， this is the terminal case。

 it just uses that those instructions there。Onces on to red。Otherwise， we save RVX。

I guess I just just gone to the animation as I was talking about this。

And then we've got the two halves of this we've got the。You know， the and part and the shift part。

We got the recursive call。And then we've got this edition here。I mentioned。

And then we restore RBX meter。关系上来。Yes。Do we just。区。That we to RX。So， the。So the RDI here。

For instance。嗯。This is recursive， so we're going to keep calling this thing and it's going to keep。

Wki we。嗯。So we put it in here， which is a call。E save register。

So that means it'll be convincedvin we're guaranteed that it's valuable retain across the call。Okay。

And so that's kind of what happens at every recursive call。If we were to put it in。

 the other place we could stick it is on the stack。

 and then it would just you know be a different place on the stack and then we' cover it from there。

来。最象に。I question。三任な歴。全場し。Well， if I put in a call or save register and I have to save it or it will be tramp。

Right， I mean， if I put it。In some register that's call or saved and in fact。

 what would you have because when I do cur a call， it will try to stick it in another I mean this is one this is the entire segment of code for every time this procedure gets called so it's not like I have multiple copies of this procedure and each one I can sort of select a different register to squ things away yet。

This is the whatever choice I make here is the choice that all implicationss have this met。Right， so。

It's going to trample on itself。If I use a call or something。But I mean like4 weeks。You put the。そ个す代。

策こ。I mean， the value of this's being put here has changed every time because it's a different argument。

Right。There's not like it's a value to scroll away once and they all refer to it there's a different value every time。

 so you need a different location for it。We can talk moreline。

 and we' not understanding the question。Okay， other questions。Yes。そそ。こ80二。Yeah， so again。

 it's this weird。Singmer。If this is RBx， the 64 bit of it version of it， that EBX is the。

Lower to half of it。Yeah， it takes some get it used to。Okay。

 so the nice thing about recursion is that we didn't have to really do anything different。

 right it was basically the same mechanisms that we used for non recursive procedure calls。

We used for recursive position calls。The stack frame ensures that we have private storage。

So we didn't have to do anything fancy for that。You know， the saving convention。

 whether it's call or call in， make sure that you don't trample on each other's registers and so forth。

嗯。The stack discipline works just fine if P calls Q。

Then you know that Q has to return before P can be done， and so it's this perfect last in first out。

It also works for mis incursion right so Pcurs calls Q which recursiveively the cause P。

 which recursively cause Q calls P and so forth， that's fine just the frames just pile up。

 everything works beautifully。Nothing special as we've done。think。得 so on。

Important thing is that you you have the notion to stack。At any point in time。

 there's the notion of the frame that the collar has。

And the last entry of that is always the return address。Okay。And then there's the part that the。

The collie has， which can include。The arguments that the caller places on behalf of the coley， right？

Plus local variables that get allocated。Plus， any push and popping。

 storing squing away of registers that you need to do kind of courageous and that that's frame。

 frame frame and an unroll frame， unroll frame， unroll frame。呃。Good。

 so so it's basically these conventions about the registry usage。

 about calling and call saves that enables。The whole code infrastructure to work and be efficient。

And。 but it was all just conventions right， I mean why six res。

 why are these ones called citizens where these ones call citizens？

There was some logic behind him them， but again， it comes down to just policy。

And a policy that was established and gets it enforce。



![](img/e471d22333d51ce3504428899066e191_9.png)

And that's it， any other questions？All right， so the next lecture you will talk about。可以。

How do structures get laid out of new？

![](img/e471d22333d51ce3504428899066e191_11.png)