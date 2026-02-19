# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p06 06 - Machine Prog_ Control -BV17jcReyETC_p6-

まね。

![](img/e0108a6152d68a9bb5b6e57eaca70513_1.png)

![](img/e0108a6152d68a9bb5b6e57eaca70513_2.png)

![](img/e0108a6152d68a9bb5b6e57eaca70513_3.png)

Okay， why don't we go ahead and get started？那。So it's good to see that at least some of you must have。

Pretty good copies in how you're doing data ats。いうことありま。快。But I guess you have some midnight。

 so you have some time still。啊。Have people had a chance to watch any of the videos。

 are they coming across， okay？So everything' seen me working watching the videos。

 those of you to watch it。I mean， most of the people here probably don't be able to need to watch the video because you're here。

But like I noticed that it's because this camera only has so much a feel of view。

 and sometimes I like to move around I'll wander off camera。

But I think that my talking head is the least important part of see what the video sees。

 so more important to get the slides and what I write the slides。

So today is going to be our second of five lectures on machine level programming。

 and today we're going to talk about control。In particular。

 we're going to talk about condition codes， conditional branches， loops。

 and then how switch statements， C Sw statements are handled。So as a couple slides we do。

 just remember that what we're talking about now is the assembly or machine or sometimes called object code。

View of what the processor is providing。And that's what's called the ISA。

The instructions on architecture is the abstraction API that。A architecture。

Supports that you program to。And if you program to that API。

 then no matter which variant of the processor underneath you use， whether it's something simple。

 maybe on a cell phone or on a desktop or even more complicated something running on a server。

 it doesn't matter， those are just performance issues shouldn't affect the correctness at all if you program to this API correctly。

Okay， and we had a picture like this before where they includes things like the program counter。

 which is the pointer to where the instruction you're currently to execute。啊。

The side of Manchesterchess。Condition Co we going talk about those today and then what goes on in memory。

If you want to take your seat program and look at what the assembly code or the machine code looks like。

 then you can compile it with the right set of flags， for instance。

 this dash S flag here will produce assembly readable text assembly like the Kay Show in class。

You can convert that to a binary， which is just a whole bunch of bytes， it's really hard to read。

 but that's actually what the machine will see。We talked about you can actually go back and forth through different tools。

 you can go for logic back to assembly， you can go even from executables back to objects and so forth。

And eventually when you go to run the program， it all gets linked together and execute。

And there's various types of instructions， all architectures have a set of them， as I mentioned。

 some ISIS like Rik five have tried to be minimal in the set of instructions they provide just what they view as the key ones。

X 86， because it's sort of evolved over three decades， four decades。

 has sort of accumulated instructions。嗯。Collgue mine once said that。啊。

If you work for an intel and you。Create a new instruction。

 so that means you propose something that's considered valuable enough to add to the existing instruction set。

 then you can become an Intel fellow because of that。

But no one ever ever ever became an Intel fellow because they removed an instruction， Okay。

 so the reward system says add add a， nothing ever says removed。

We have two types of similar instructions， Mo Q and LAAQ。

 and remember the queue just stands for the size。Okay。

 so that's a quad if you do Alex it's going to be 64 bits， if you do Alex， 32 bits and so forth。

Does anybody remember the difference between these two， what's the difference between moving and LEA？

LA stands for load effective Ad in case that triggers something you memory。Yes。え武きを持った。Your。Exactly。

 okay。That's the difference for。In both cases you can also move a constant。

 so if the source could be， and that's indicated by dollar sign。

 the source could be know dollar sign， Xerx。F， whatever。Okay， or dollar sign。3。Okay。

Then you have a whole bunch of athmetic instructions。

 the important thing to realize is that again the source is before the destination and it's a。

It's accumulate into the destination， so what an add instruction this form will do is it will take the current value of the destination。

 add on the value of the source， and store it back in the destination。Okay。

 and there's a whole bunch of them there sort of correspond to some of the operations you've been looking at for dataL。

 all these different types of things。可以。😊，And there's， you know also inter operations and so forth。

 but this is just a。highlightighlight。We also talked about adjusteding modes。

 this is something you're going to need to understand quite well when you're writing assembly code。

The most general form is what's shown here。Right， which is。

has a lot of different fields and the way that gets calculated is that you take the this is a register。

 you take the value in that register， this is another register。

 you take the value in that register and you multiply it by this S。And you add those two。

 and then you also add on the D。Okay and this D is restricted to no。You know。

 a certain number of bytes and s is also highly restricted， it can only be 12，4，8。Well。

 you'll rarely see this extended version， and you'll more typically see some of the special cases。

Like this one here。Just as the location is some base plus some index。In that。All right。

 so we'll go to the next slide a little detail。In this lecture。In particular。

 we're going to start off by looking at these condition codes。Okay so again。

 recall that we have these registers in。X 86，64 bit architecture， that we're using in this class。

 there are 16 of them， 864 bits long， and they're named as John， okay and there's a separate。

Register that you can't use as a programmer sorry that has a specialized。Use as a programmer。

 that's the instruction pointer， and also the percent RSP is dedicated to be the stack pointer。

We'll talk more about that when we talk about procedure calls in the next slide。

But what I want to focus on today is really these guys right here。So there's four condition codes。

 the first one is CF， it's called Car Flag。And I'll give examples of each of these。

 then there's a sign flag， so far a sign number that tells you whether it's one for a negative number and zero for a positive number。

The zero flag， surprisingly， does other zero。The overflow tells you whether you've had an assign overflow。

And the important thing to note is that these are implicitly set every time you do one of these arithmetic operations like an ad or a subtract。

It's kind of behind the seas， that get set and they stay set until they're overrit。Okay。

 so when you have things like additional branches that want to branch on one of these conditions。

They look back and you know， logically you look back in the program。

 what was the last instruction that actually set some of these any of these flags and that's what。

Whats出。オッケ。So specifically， if we do this versus add instruction right here。Then。

You know the zero flag if the result ends up being zero。If the result ends up being negative。

 the sign flag gets set。If you。If you have if you can recall from a few lectures back where we talked about what is the symptom of overflow？

😡，In two complement arithmetic， it's where you， for instance。

 add two things that are positive and you get a negative result。

Or you add two things that are negative and you get a positive。

And the OF flag overflow flag gets set when that happens。Okay。Now。

 important thing to note is that although things likerithtic operations and move operations will set these condition codes。

 the LEA， this load effective address instruction that we highlighted a minute ago。

 does not set any condition codes。You' justBecause it's viewed as you're just computing a scalar address。

 it's not something， it's not real value， it's just this address that you're going to use。later on。

But it turns out because it doesn't send me condition codes。

 there are times that the compiler will find this useful。对。

So it may pop up in your code in strange places。Okay， so pictorially。

 the carry flag with something like this for a edition， if you have， you know。

 if you get basically a one off the edge， there's overflow off the side。

 it can only occur when both these are one。嗯。Actually I's not sure this is one of the cases when it occur。

 but anytime if you like carry into this bit and then you can get overflow and so forth。

 but the important thing is that there was this carry that came out the end。All right。Now this is。

TheIt's important to note that these conditions are set no matter whether the same way。

 the absolute same way， no matter whether you're doing。Unsigned or choose compliment arithmetic。

It's just they mean something in one case， so they don't really mean a whole lot in the other case。

Okay， so here in unsine arithmetic， if you recall， since this is not the sign。

 this is actually part of the value， if you get something spilling off the end， that is a overflow。

Okay， so if you're doing unsanrithrimetic and the car fog gets set， it's overflow。

 if you're doing s arithmetic and the car gets set。You know。It's not as informative， right。

 because there's a separate notion of what overflow is in choose complicated andrithmetic because you're trying to protect this assignment。

Okay， so the sign flag just reports what's here。はい。So in again， an unsign orrithmetic。

 it makes no sense， right？The s flag is going to say that number is negative。

 but it's not because it's unsign ametic， so you the compiler or you as the programmer will just know that means nothing right who cares that bit happens to be one。

 that just means it a big unsigned you right its nothing special has nothing to do with it being a negative number。

What's useful for though， of course， is with sine arithmetic。

 where that means that the result is negative。Now the overflow flag is set if you call the conditions I highlighted on the previous slide。

 it's when you know。You're adding two things that have the same sign。

And the result is a different sign， it's a different sign。And so this is overflowed。

 it indicates that when you add these numbers up， the value that you added up kind of spilled into the carry bit。

And the sign things， so that messes everything。可。So again， for unsigned arithtic。

 you're going to get the same flag set it's just going to be kind of meaningless， right？

But for sign arithmetic， it reports over quote and it's very useful。Okay。

 any questions on the kish codes？Okay， and then of course the zero， and that's self evident， all。

So in addition to them being set implicitly by the operations you perform and the moves you perform。

 you can also， as a programmer or the compiler can spinit out an instruction that's going to your sole purpose is to set the condition codes。

Okay， and so there's two flavors that one is this compare instruction， and again。

 the cu is just means the size of it， but the important parts it compare。

And what that is is that it's like computing if you have compare pair of B and A。

 that's like computing a minus B， but without actually producing a result anywhere。

So it's like subtracting a minus B， but the only thing。

 but you don't actually store the result of that computation anywhere。

 the only use is to set these condition codes。So as you can imagine that if the zero flag gets set。

 what that meant was that a would be。so it's a way of that sense is a compare。

 if the sign flag gets set。And these are sine numbers。

 then that means that a minus b is less than zero， so if there wasn't any overflow。

 then that means that a is less than B。Okay。And then the overflow is the rule we just highlighted a minute ago。

 right？That basically when if I did this comparison and I got a signed overflow。

 then I know that I can' basically I can't trust this。Can't trust there's all of that。

And similarly for unsigned comparisons the。Carry flag will be set at this carry out of the last。

And the other form of this is this test instruction。

 and what that does is instead of subtracting A from B， it takes the end of A。Okay。

And so if those two are the same。Then you're going to get zero。Because all the bits will be the same。

嗯。If when you do this， the result ends up being negative， then the sine flag is set。

And whereas it's highlighted than the slide， where this is most useful is if say one of A or B is a mass。

 you want to know is this quantity in the register equal to this mass value？Or if it's a mask of say。

 the lower bits or something， maybe you're interested in whether the value in the register is bigger than this mask。

没效果。Okay。So here's a common use， seems kind of strange， but want to compare。

 you want to compute the and of the same value against itself。Okay。😊。

So that seems like a pretty stupid instruction， but the point is is that they decided that it works just fine。

 if I do the and an of itself， then I just get back the Q REX。

And so I'm just really testing whether this quantity in this register is zero or negative。はい。

And since it worked perfectly really fine， there was no reason to introduce。

Yet another instruction that just did a test of a single opera。Right。

So it's like a structure savings， but it looks really strange in your code because you're adding two things that you know are the same。

But it accomplishcompes the same thing， so that's what's used。Okay。So how is condition code used。

 well， one of the important ways they're used is to。啊。Sorry， sorry。 I'll get to that second。

 So this is about the the sad instructions。 So there's a series of。Of set instructions。Where you。

You are either going to return true or false， right one if it's true is or false based on a certain condition。

So if you have a set E， it stands for set equal。because if you do't the compare or set zero。

 then if the zero flag is set， that's going to be true。

 and therefore it's going to storear the value one in whatever the argument of the register that's the argument of this function is。

Okay， and similarly not equal， we'll do the complement and the sign flag and there's some interesting combinations。

that take an account that you want to factor out overflow if you're doing sign and rhythm。

 taking and so forth。可以。So what's interesting about this instruction is it only sets the lower order of bite。

Of the destination and the remaining seven lights are unchanged。Okay， and what it's using。

 if you remember I didn't。spent too much time emphasizing this in the previous lecture。Really。

The background compatibility they allowed you to always reference half of the register or quarter register。

 the low end parts of the register。So the 64， theyre registered， but you're able to reference。

The lower invite by this name。A1 D1 C1 and so forth。

And so if you that that condition code that I was mentioning， if you， if the destination is REX。

 it will get stored right here in this。A1 so that'll end up either there being zero1 and the rest of it is unchanged。

Okay， so let's look at example。Okay。So I's suppose you had this very simple function， right？

It takes two long and just wants to return if x is greater than y。

So if you had use this compare instruction。Right then if you recall the first integer。Operation。

His argument is stored in RDI。Okay， so this is where X gets stored。

And the second argument is sort of RSI is where Y is being stored。Okay and I've done a compare。

 which means Ive， if you call a second ago， it means I've subtracting， it's like I've subtracted。

 let me remind you。If it's compared B and A， it's like a subtracted a minus B。So， I'm doing。

Carib B a was a minus Sp， it's RDI， so it's basically x minus1。Okay， let's second at that backward。

correctectly if you haven't back it sometimes that's hard to do extending up here all right。

 so so this instruction will set。嗯。We'll set a condition code， we'll set all the condition codes。

 but in particular it willll set the condition codes that might say this is zero or this is less than the results less than and so forth。

And this instruction here。Says take the the。You know this particular condition code。

Combinmination and store in A1。All right， so what is that combination？

That combination is the greater。In sine arithmetic2 is complement arithmetic。

 you not zero so they're not equal and when you subtracted the know you wanted both the case that there was no overflow and this s sine wasn't negative and you complement that and so the end result is greater。

Okay， so that's with the G stands for greater。So now you've got a one in here if it's greater and a zero in if it's not。

And that's where we want to return。But we've only populated this one little byte at the end of this register。

At the end of the register RAX， which is our return register。

And so we've got to pad out the rest of the thing， right。

 there may be garbage still in that register everywhere else。And so that's what this weird move Z。

BL instruction does。Okay， it takes some。You knowThat one by and basically zeros out the rest of it。

Okay， and so then when you return， you get。RX with everything else at to zeros。可以。And again。

 it's kind of peculiar because， you know， for whatever reason。

 you know the L here and they use the half version of REX， right if you call REX。

If you have REX overall， then EAX is this lower half。And then， you know。

 and then the lower bites down in here， right？So they did this instruction just in the EAX part。

 but the instruction has the property of also setting the upper 32 bits， so these also becomes in。

All right。All right， so if this is again， the picture of the register and the EAX part actually extends all of the end here。

And if the AL is that one， either zero1 have written here。

 then what this instruction is up doing is zapping the whole thing out to zeros。

 all the rest of them yes。啊。Because。sThe compiler is still stuck in an age。

Where it thinks that every little bite it saves。Is good。And so by using those of the long form。

 instead the quad form of this instruction。That' some goodness it's kind of misplaced in this day and age。

The compilers will uniformly do that， they'll try to use this you know if they can get away with an L formulaly use it and they get away with。

You know， as opposed to Q form and so forth and but these have to match right that basically the destination。

Because this is a long， it's got to be at least the EAX or。Yeah是。It should be the EAX。

 right because that。This says it's 32 bits and the 32 bit version they're interested。Good。

 so any questions so far， another question， yes。こういう勢だ。Get that thing again。Yeah， so you know。

 five and five is five。買だ。那独是要发份。Right， so what happens is if you do。啊。

Like if the value of the register had five， you'd get five and five and that would return five。

 and then because that's a positive number， the sine 5 would not be set and because it's not zero。

 the sine  p would also not be set。So it's a way of going from the value and register to the condition college associated with that value。

So if that guy is zero， those zero flag would been set。Okay， there's another question。嗯。这嘅。三さ。Yes。

 so every one of these rhythmthtic instructions and move instructions。

Resets all the four condition units。Okay， so it's not like， oh。

 this operation only sets a couple of them， this other operation only sets a couple of them。

 it's every single operation will that sets condition code at all will set them all。Okay， and then。

Then the instructions that use condition codes you will use the condition codes as set by the previous the nearest preceding instruction that sets them。

As you mentioned， things like LEA don't set condition codes so it would skip over that one if that was the instruction I before and so forth。

Good。Okay， so this is I started to jump to a second of I'm mistake， but this is。

Primary where these condition codes are used， and that's for jump instructions。

So you have the unconditional jump。which is always going to jump。

But then you have this whole set of other types of junks。

And they're meant to be named in ways that make sense to you， so J E the E are equal。

 so that says that if the。啊。Its if you've done the compare version of it you know and you got the zero flag because you' subtracted。

You get， they would be equal。So I shouldn't have started that one that was kind of confusing okay。

 so let's do like the jump would be greater then。The jump at greater then is the exact conditions you need to do signed greater then。

So if those flags are set， we go on。Jump if the sign flag is set， jump sign。

 will of course jump if it's negative and jump non sign。And I have jumped， it'9 negative。嗯。

Jump less than。You just you know， make sure that after this subion。

 the sign flag was negative and there was been。You know。

And there wasn't issue with overflow and so forth。So you notice that a lot of these are set relative to what you get out of a compare instruction。

 so that's why this is called jump equal， because if you give compare the same argument equal values。

 it will return zero and the zero flag will get set。Okay。

 not equal is the zero flag would not be said。Okay。

And so if you actually one of these structures and those flags are set。

 then there will be a label after that， so maybe your code looks like jump equal to position L2。

And somewhere in the code， there might be a label， it's L2。

 and that says that if this condition code is satisfied。

 you will jump back to that place in the code， otherwise you just dropped through。Okay。

 so you can see already， this is a way， as I've described it to do a loop。

 and we'll talk about loops。It's significant detail later in this class。Laterate in this election。

Okay， so let's look at some more examples。Let's suppose that I wanted to compute the absolute difference of x and Y。

Okay， so one way I could do that is I can do so if C might look like this， you know。

 if x is bigger than y， I want to subtract you know。

 larger minus the smaller and similar here if they're equal or y is less than I want to make sure I subtract。

嗯。Because I want a positive absolute difference if they can have value。

I'm trying to compute absolute value of x。That is why， right。

 and so I'm doing that by first comparing them and deciding which one's going to be the larger and then subtracted important。

Okay。So now if we look at the assembly code， how that gets implemented is you've got again。

 this compare instruction。And then if it turns out that that based on the condition codes that you get less than equal to。

 you're going to jump to this label L4 k， which is right here。Okay。

And so as noted here in this comments， what that's saying is that you jumped here only when x is less equal y。

Okay。Which is this red branch here。This is the red code here。

 so now you just want to implement y minus x so you take Y。

Which is in RSI and you move it into the return register。And then you subtract off from that RDI。

 which is your x。OkayAnd so now when you return， that's what's in this return register and you'll get the proper value。

On the other hand， if you came here and that condition wasn't satisfied。

 you would drop through to here and you would do the subtractions the other way around。

 you'd move the X in REX and would subtract the y from it and you'd have the REX would be similarly correctly populated and then you return。

可你可起上呢。2。嗯。So， that。highlightigh in here， that's old style conditional branch。

And in order to get that， you actually have to set this flag， no if conversion。

 because this is actually not the most efficient way to do this。

Given instructions that have been added to the Act 86 architecture in the last decade and a half。

But it's still one possibility and you'll see there be cases。

Where you're going to want to do this style of thing anyway。

but not for things that are this where the bodies of these loops are this short。Okay， so。Good。

So another way to think about this is。To。呃。To perform this test。Whether x is less equal than y。

 and if the test is satisfied， you're going to go to this red branch。

 otherwise you're going to compute the x minus y and go to Don and return the result。Okay。

So if you think about it， this is sort of the C code equivalent to what I just showed you in assembly。

 right？😔，Because the assembly sort of had this notions of these go tos， right， and so forth， right。

 and it did be。嗯。Did this kind of construction So if you want to think about what this code is really doing and you think better right now and see than you do in assembly。

 this is kind of what that assembly code has been mapped to。オッ。

So the general version then would look like this if you have a value that's a test and depending on whether the past of the test。

 you've got a then expression or else expression， this is the example we just showed you right。

 but this is a generalization。Then the version looks like this。 You say， well， if the test fails。

 so I'm going to do the test， it fails， I'm going to go to the to jump to this part。

 the else expression， right it fails。 I want to jump here。 That's what I do。

 Otherwise I do the then expression。 and then you know then I'm done right。Otherwise。

 drop there and I'm done。So there's separate code reasons for the then and the else expression。

 and you execute the appropriate one。O。So that was the old style。

 but it gets you thinking along in the right directions。The observation was that。The old style。嗯。

Particularly if these expressions were the body of these then clauses and the else clauses。嗯。

We're small， like almost a single couple of instructions only。

That's a lot of jumping around in the program。Okay。And one of the things that。

Prots still to this day， don't do well。Is branches， okay？

They can do well if it's a branch that they can predict。

Based on the of the history of running the program to date。

They run so far that a particular branch is likely to be taken。

 then they can speculate and go ahead and start fetching the instructions as if the branch is going to be taken。

But in a case like this where maybe it's 50，50， whether you do the then of the else clause。

 it means the processor is going to get it wrong half the time， if the processor gets it wrong。

 it's got to roll back all this work because there's a huge stall in what's going on and it's very nonperforming。

And so。About two decades ago， they decided that they need to introduce these what's called conditional move instructions。

And they eliminate these branching altogether。Okay， so how do。So。Okay， so what you do is you say。

So in C， if you want to think about how this works in C， you'd say， okay。

 first I me going do is I'm going to set the result to the den expression。Okay。

And that's good if the test fails， I'm basically done， I can return at that point。

But I haven't done the test yet。So now I do this。Separate computation of the al expression。😡。

And I store it in a different place， okay so I got a result in a valve。

So now I've got two values ready to go and I want to return one or the other based on the outcome of the test。

Okay， so。The beauty of that is it's just a single instruction。

I perform the test and based on the outcome of that test， I either map the else expression。

 overwrite the else expression on the result， or I don't， and that the way I get the one I want。

And because this is such a simplified thing is actually there's a single X86 instruction that they can do it。

Okay， so in terms of code flow。There's no jumping around， no stalls on nothing， right， Ex this。

 excuses that。 It excuses that， excuse that。 you know， maybe nothing happens， You。

 the move doesn't happen， but excuse that， and excuse that。

 right the pipeline of instructions that the processors executing。

Doesn't have to rely on guessing which way any branch goes。All right so that isn it being a big one。

 Yes， what if the Alice is like super expensive actually actually Alice， Yeah。

 like what if it takes forever to run like？Why we computed that exactly， so that's a bad idea， right？

对。Good， so that's one case in which you don't want to do， right？Its simply for the dead， right？

Suppose that the vent is really expensive to compute。And are beauty。系い。I was kind of watched。Okay。

 so this isn't cure all for everything， but and I'll ask you for a couple more examples where it's a bad idea in a couple of slides here。

 but for a lot of codes， this is perfectly fine。Because the thing is if you do a brain misprodiction。

 mis predictiondiction， it can be 50 cycles， right？You know。You know。

 as long as these are less some of these， you know。

 whatever the waste of work on this is less than 50 cycles as。It can be okay。All right。

 so getting back to our absolute difference example， what we see is that the again。

 we compute the first result。We compute the red part， so now we compute the both， we do our test。

And then we have this condition re restructuring。So it's a condition move on the less than equals to。

Condition right so it's the same the conditions are identical to what they are for the jump instructions right so the JLE instruction has the exact same condition as the CM moveveL instruction it's just what do you do in the one case you jump to whatever the target is maybe it's you dot01 or that is in this case you you actually do a move。

Okay。So it's also one of the few instructions。Remember， most of the instructions。Well， okay。

 so it's more like a move in that that it's a copying of one or the other。

 It's not like an ad where you take what's there and you add on top of it the new stuff and store it the same result。

 it's actually， you know the old value of RX only matters if you don't do this move right So you either get the old value of RX or you get the。

What was in RGX？Okay， any more questions on that？Yes。Nothing think。Replacing what's in。也是。嗯。You can。

The。嗯。Yeah， so once the branch， once this destination has been。

 once this label has been resolved to a actual you know pointer。

To the place of the code you're jumping to， then that's exactly what happens， right？

That instruction point register， which's the RIP register in Intel processors。

 gets updated to be the value of whatever that。Ted is， whatever that L1 is。As you'll see later。

 there's things like indirect branches。If there's a star here。

 what that means is that there's going to be some interaction。

 we'll get to that when we talk about Sw statements。Okay。

 so we already have one example when this is a bad idea。

 right and that's when the then clauses and the else clauses are really expensive。

Can anybody one or the other？没购买会人。so I you do着。Exactly right if it's if I want to check to see my pointer a null。

 if the pointer noll， I want to do one thing if it's not nu， I actually want to dere it。Okay。Okay。

 can anybody think of another case where things could be？啊，Yeses。So there's something that。大丈にさ。

It statement mean statement with。7意。Exactly。下一。Exactly。

 so suppose somewhere in the Ven clause stores into some place of memory and somewhere in the else clauset stores in that exact same location of memory。

 well you know you didn't want both those now good， good good good good good okay。

 so the three cases that we've identified are the expensive when these things are expensive。

Both of these are expensive to do。When they're risky， right？Because you're saying。

 I'm going to compute both of these results before I you to test。

And when there's some sort of side effect。Okay。So for instance。

 it could even be in a register the same even if X is put in register。Okay。

 she must be satisfiedified。All right， so to help you test your understanding of this。

Here's a little exercise， we got our little cheat sheets here。

 this is our cheat seat table of what these。Codes me。

 and here's our cheat seat table of both what a compare structure says and what these flags are。

So I's suppose I do an exor of the same register twice。Okay。嗯。What's the end result of that。

 which conditioned flags gets set？Or first， what's the value in that？End up in the registerster。0ero。

 right。Okay， so given that this is zero。Then which of the flags get set？这。Okay。All right。

 so now I've got zero sitting in REX， and now I subtract one from it。So the value I get in our x is。

us1 and which do the flags get set？Sign flag and the carry flag。Because I've added。2 things that are。

I positiveitive signs and I got something with a negative。嗯。And now I do this compare against two。

 so I'm comparing two against negative one。Which， which。Like you said。嗯。

TheRX Compr doesn't store anything， so RX is unchanged。And we get。Therere still negative。Now， I do a。

A set。One of these fancy set instructions into A1， which is again， the lower byte。And from。好好好。Of RX。

And。And what happens， okay， so I'm looking at the set L as this one here。And so I meet。

much the difference of the sign flag and the。Over说出来。So it's then up being zero1。Okay。

So ends up being one and notice it only overri the last thing， all the rest of this is unchanged。

Okay。And therefore， this。This thing is still negative and so with。

And now I use this strange move ZBL structure that we saw before。

 and what that ends up doing is zeroing out everything else。

So now I have an entire register that just has the outcome of that condition。嗯。Ws the same5 one。

I think that's a mistake， right， I like she be zero again。All right， so any questions on that， yes？嗯。

Okay， so so we're doing we're subtracting。嗯。Very true to A。So we want to subtract Rx minus2。

 right Rx？-2。Okay， so it ends up being negative1 minus two， negative3。That's why the。相当于是。第二。Yeah。嗯。

两个。位。Because。Let's see， this， this was。A non negative number。Right。And this is a non negative number。

And out。Com is a。其他几。对啊。C。Plus， a negative one。这要什么事请费。So this， okay， good question。 so this is zero。

Now， okay， so。やぱ。I take this number and Itract one， so I'm sort of basically adding minus-1。And。Yeah。

 I think it'。Yeah that是个 question。I excuse decided to make this slide。Sorry。嗯。Okay， yeah， let me。嗯。

I'll clean up this slide and put something on Piazza explaining。我 the呃。

The correct things are before I post this slide。Good。All right， sorry about that， Okay， so anyway。

 now we're going to talk about loops。So once sound loop and C is the do while loop， you do a do。

 and then you have the test of why。So let's suppose that we have this pop count。

 which counts the number ones in an argument in this argument。So how does this work。

 you start off with by zero and then through the loop you do。

This and right which just grabs the last bit of x。And if that's a one。

 you're going to increment result， if that's a zero， it stays the same。

 and then you shift off that bit。And you repeat until the bits x is just zeros。

 in which case that this test fails and you return the result。

 which is the count of the number of ones。Okay， so as a go to version that would look like this right you just have that your test and if you pass the test you go to some header。

Alright。In case we have this。And so once we have this go to version and we can pile it with you know。

Are there minus zero。You know， with the optimization level zero。

Without decision level zero then you'll get code that looks like this code that you started with and will look like this so the first thing you do is you're going to move。

The you know， initialized result， Okay， so we're going to accumulate the result in REX again。

 it does this weird thing where it takes the。The smaller instructor you get away with。

And so you just load in the lower half， that's plenty of room for the zero。

Then you're going to move the argument X into a different register。

And then you're going to do this and， you're going to and。The number one。Same as this。Against that。

Reister again。Knowing that do you only need to worry about the low end of it？Okay， and so that。

 and then you're going to take that and add。To the result。Okay。

 so you compute that bit as either  zero1， and then you accumulate it onto the result。

Then you do your right shift。Okay。Of the argument X。And。Again。

 if it's not equal to you want to go around the loop。So it's not equal to zero yet， so you go back。

Around the loop and so forth， and once that equals 0， you can drop out of the loop。

And Rx will contain the value one。Okay。😊，嗯。Artistact。Okay， it's just showing you how。You know。

 you did an arithmetic operation。That did the right thing。

 but as a side effect it set these condition codes and if this value is not equals zero。

 that means you've got more once accounts， you can loop again， if it equals zero。

 you drop out a loop and you're done yes。最 of会。change。Interchange interchan。

So you've got the full register， which is 64 bits。And that's like REX。And then for each register。

 there's a name that refers to the lower order bits of it for REX。

 the lower order bits are called EX。Okay。And so if you move。You know。

 if you store something in these lower to bits， in this case， it's zero。

Then the whole answerster is 30。And similarly here， because you。You know， RDX。The four edge RDX。

 R dx。Has the half version of O EDX。You know you can get away with， I mean。

 it perfectly fine to say the Q version here and RDX。But the compiler is trying to be clever。

 And so it says， oh， while I know， I'm you know， this is going to work out for me。

 So I'm just going to put。in the lower order part of it。

Into hear and that's where the action is anyway。Yeah。And as they were to meet it。系。Right。

Because basically this， this is either going to be a0 or one。 So there's no reason to。

To use the version instruction that needs all 64 bits。I mean， you don't even need 32 bits。Yes。

이거 hoping you guys been nervous。 So this is。This weird instruction。

That is actually mostly historical legacy reasons。There were some architectures。

 Act 86 architectures that needed to have a sort of a no op instruction， a dummy。

 you know placeholder instruction before any return。And so a compiler just spits it out。

It'For our purposes， you just ignore it。Okay。は，对。All right。是啊我是个开产询。We not have canvas。All right。

 that's how you guys did， All right so。All right， so it looks like a lot of off1 years。

So what happens here if you remember the address mode？This is。You take this timess that。嗯。Yes。

 I items， you take the four times the value of RDI。Which is the first。So R the Is holds feet。

Val the first argument， so that's  four times x， and you add it to the contents of another thing。

 which is also RDI it the end with 5%。Okay。So remember we said that the LEA instruction was a。

A single instruction way to get some interesting modifications done。Not all energygen implicationss。

 but you can get things like。Multiply by five or multiply by nine or multiply by 17 and so forth。

Okay。Okay， so this one hinges on the fact that。Now the LEA does not update condition codes。Okay。

So for whatever reason the compiler did not want the condition codes updated when I did this edition。

 and so by using this instruction it gets the exact same value in REX。

 but without any condition code setting。Okay。嗯。LEA instruction never accesss as a memory that would be like a move instruction would do that。

嗯。The results are the same because it's basically this plus this。First argument。

Since there's no S term， it's just the REX plus D RDX。All right， we got this one。All right。

 the most popular answer was the right one， okay that's good。

 this is hard because you have to kind of you know your own computer， right？And thank God。

 we have computers that we don't have to do things like this， right？

Because you had to tracecing the code yourself， right so you had to say that。

I started with four in this register then and this was zero。And then I entered this loop。

 and so I added one， and then I shifted right， so I went from four to two。And it wasn't zero yet。

 so I jumped back up here， I added one again， so now I'm at two， this gets from two to one。

 wasn't done， I go around， added one again， and up to three。

And now I shifted from one to zero and now I could jump off the bottom。

 so reX holds three in this case。可以。😊，Questions on any of this quiz？Questions。All right。



![](img/e0108a6152d68a9bb5b6e57eaca70513_5.png)

Hi， so we did。

![](img/e0108a6152d68a9bb5b6e57eaca70513_7.png)

The simplest dowhile loop。系诶。The general version of do while looks like this， right。

 you take the do while loop。You put the body and you say， have the test， you want to loop back。

 right？And the body can be any number statements。What about a while loop， so a while loop。

 the test comes at the beginning right remember C？So one way you could do it is like this。

 you start off with just a go to that jumps to where the test is。And then you do the test as before。

 and then you come around and do the body to succeeds。Do you see how this is basically equivalent？他。

So if you were to look at and see the version I described went from code that looked like this to code that looks like this。

 right you say go to test。So you only have to write the test code once。And then you loop back。

And then you do the body， the body here， and then you repeat the test。Okay。All right。

 so the general version of the while again looks like this。嗯。You want to do the the。嗯。啊，有个一经。Okay。

 so sorry， we the back soon。Okay， so this works perfectly fine。

 this jump in the middle version of it。But again， it's extra jumping。

Right and you'd like to avoid that if you can， right extra branching。

 so that's what you get with the opposition level， the zero opposition level with opposition level one。

 you get something slightly smarter。Okay， it will take your loop， your wall loop。

 and instead of doing this version it will do。嗯。Sorry you' you'll get from this version to this version。

 so if the test， you check the test ahead of time and you'll if it fails。

 then you go ahead immediately are done， otherwise it's like a due body w， so it's the same。

Transforms before。 Okay， so there's no jumping in the middle。 you do the tests and you okay。

So now this is a bad idea， again， if this test is expensive because now。Sorry。If's。If you care about。

Like in old days where you might have cared about how much code this thing used。

 if this test was a lot of lines of code， then you blew up your code because you repeated the test in two places。

Which we hadn't done before。But in today's world， where we don't。You not just a big deal。

 this is it's a far bigger deal to avoid that jump in the middle。

 and so you get something a list like this。对。All right。So again， in our pop count example。

 you'll test whether the argument is zero， if it's zero， you're going to drop to the end here。

 otherwise you're going to to enter the loop。And do the test the end and so forth。可以。2。

And I talk a little about my this good。All right， what about a for loop？Okay， very popular in C。Well。

 the concept's not that hard at all， if this is your for loop in C。

 then basically if you have the different parts of it， you want to do the code that does anization。

You want to do the test？To see if you should， you know。

 whenever you're in a loop or whenever you loop around， and then there's the update part。Okay。

 and then there's the body， this body just gets translated here。Okay， so again。

 this is the general version of that。And so for particular for this specific function。

It looks like this you do the initialization。it looks like this， you do the initialization。Heres。

Then you want to do the test to see if you should end loop at all。Okay。If not。

 you just skip over the whole loop， otherwise you do the body once， you do the update part。

 plug in whatever update code is， you plug in the test code again， and then you go back on loop。Okay。

And oftentimes， for instance， in this example here。The test is whether I。

 which is initially set to zero， is less than this W size， is word size。

Which is some consonant of it was shown， yeah， here。Okay， eight times the size of this。

 now you know that's bigger than zero。Iiler knows that's big than zero。

 So the good thing is then the compiler could just get rid of this， right？

It knows that test is going to succeed， and so it goes ahead out of the loop and so therefore you save the inefficiency of having this test。

Excute it all and having the code for the test appear twice。可以。Now if you look closely。

 this isn't the exact same end condition we had before right the end condition I had before was let's keep shifting it until at's zero。

 so like if the value only had some lower to bits that are one， everything else was zero。

 you drop out a loop far sooner than waiting to march through the whole word。Okay， but you know。

So but that's just the C code we were know given in this example happened to how a different type of test。

Just to show cases where you can actually eliminate the test right off the bat。Okay。哎 questionsし在だ。

All right， what about switching？Okay， so we have an example have a very complicated switch statement。

 right， that's w to1。And you've got a switch on one of the arguments X， and if that's one。

 you're going store y times Z and then break out of it， if it's two。

 you're going store y divided by Z if you're familiar with how switch statements work and C if there's no break。

 that just means you just keep going， you fall through to what's next。

 so then you do W plus Z and then you break out of it。C three。

 you jump in right here and just do this instruction and pick out it。Case4 doesn't exist。

 so that would be the default， anything that doesn't exist as a separate the anumerated case becomes the default。

 so if x were 4， you'd set w equal to 2。If it's either five or six， you do the same thing。

 you do this operation here and then you break， and if it's anything other than one， two， three。

 five or six， then you do that at full。And in the end， you want to return the study。

So this is a nice example because it has multiple case labels mapping to the same instructions。

 it has fall through cases， it has a missing case。Okay。

 and you want to be able to translate that into assembly code that does all the right things。

And the way this is done， one key component of it is this jumped in。对。Its right here。

And what this jump table is going to do is you're going to for each of the。

Code blocks in this switch statement。You're going to stick them somewhere in memory。Okay。

 however many there are？And the start of that segment of memory you're is going to have some address。

And those are the addresses you put in this table。And specifically， the place。

 the code you want to jump when the value is zero。You want to put the location I code in the zero slot of this table。

And the code you want to jump to if the value is one， you want to put it here and two and so forth。

All the way down to the largest value have， which in this example is n minus squared。Okay。

 and so then you have an instruction looks like this。That's going to take the value of x。

And use that as where the indirect jump into this table so if x is zero it's like an array addressing right。

 if x is0 you're going to jump into the head of the array， if x is1。

 you're going to jump into the next element in the array to the next element array and so forth。

 and so you jump there， you see what the address is， and because of the star says， oh。

 that's not where the code starts， the code starts at whatever pointer that is so then you go here and you execute the code here。

Okay， so that's the first key component Now the problem with this is that you we have missing cases。

 we have this default you know if you know what if x is bigger than n minus1 or less than zero and so forth so code has to the assembly code has to clean up around that。

And the common trick looks like this。The compiler looks at the Swiss statement and sees that， okay。

 the values that I care about run between you know。One and six， right？Yeah， case one through six。

 okay？So what that tells me is that。If I give you an x that's bigger than six。

 I know it's the default。Okay。So if that's true， then I'm going to not do the indirect jumping at all。

 I'm going to jump to the place where I stored directly to the place where I stored default code right so one of these blocks here。

Our separate block， I guess would be for the default code。It have its own label and own code block。

All right， and anytime a case is default。You'll put a pointer to it like a case of which one was missing。

So like the case of four。Instead of pointing to one of these actual code blocks。

 it would just point to the default， it would just do the indirect jump through that。

And in this case， the case where it's out of range， it just immediately jumps that default code。

Great。嗯。Otherwise， it does the indirect jumping thing。嗯。

So this is just the specifics of it right if you have the different code segments laid out like this。

 if you have two that jumped at the same place like x5 and x6。

 then of course they're going to have the same code label。系。And again， like I said。

 the one is missing。We'll have four and when we go to the fault code and also zero was missing。

 well go to the fault code。So that's the way very cleanly in a single sort of set of instructions。

 you can evaluate a Sw statement because you look at the value， you see if it's out of range。

 it's out of range， you go to the default code， if it's in range。

 you do this like index you do this array it tells you where the real code is right if it's two。

 you get to this position。呃。The table will hold this pointer here and you jump to that code and execute the code block for that。

Okay。Now notice that this trick works for access within a range。So it's。

If like you do a switch statement and you do you know case x equals zero and x equals a million and x equals 10 million。

 this is not a good idea right you don't want to build a 10 million entry table when you going to care about three entries。

But for many cases that people use switch statements for， the things are packed to the tight range。

 okay and this trick is a pretty good one。Now， if it's packed in tight range but doesn't start at zero。

 then you can just subtract off and do the indexing with that， right So if I haven't a packed range。

 it's like between 100 and 100。106 as opposed to be76。

 then what instruction get admitted will first subtract off 100。From the x。

 and then I'll have to put it in the ranges zero to six。

 and then it will do exactly what I showed you。Okay。And again。

 this is just showing for each of the different cases。

 you go to the code that's appropriate to that case。For instance， for KX is a one。

 this is what the code said， and so if you go to that。You know， the the。That entry in the table。

 you see this dot L3 and you say， oh， that's where the code starts and you go to L3 and this is what you see。

 you see Y and then you accumulate y times Z， and so the return value holds y times Z。

And you go ahead in in turn， cause that's what you want for this case。Okay， in terms of fall through。

 it just means that you you want to have the。嗯。You want to break up the case into have another merge label。

 so for case two， you start off you compute y times Z， and then you go to where it's merge in。

Now you would think you could just drop through， but there was a subtle here。That。

If you go back to the be here。啊。There was a snicization of W。To one。

But W is used in all these expressions。Okay，'s using this one， this one。Anmous one right。

 these's the only ones that read W， these other ones just overwrite what's there。

So like a compiler has said， oh， I don't want to execute setting w to to 1 for these cases when I may not need it。

 maybe one of these early ones is the most common case， so why waste is the structure？

So I'm going to move this W equal to1 conceptually into just the place I need it。

 so I wanted to hear。Can I want here。Okay。But if I do that。Then I fall through。I don't want to。

I didn't want to do the W equal was one for the fall through case because I already just set。Right。

And so that's why I have to skip over that and go to this merge statement and then I can do what I want。

So even though it's a fall through and you'd think I'd always come into the start of it。

 I actually come into a little bit past the start because of this tricker then I move the W equals one into the case itself。

Okay， so there's a lot of subtleties here， all right。

 and I recommend you look through this example in the slides more carefully on your own to make sure you get it。

But conceptually it's not that deep。Okay可。Let me just finish by。

Summarize what we've talked about today we talked about。You know。

 we have different forms of control flow and C that you're familiar with。

 how they get translated into assembly control， and some of the same techniques that the machine uses。

Okay， the next time we're going to talk about stacks， the procedures， returns。

 and some of the procedure participants。All right， so good luck finishing at the lab if you haven't finished it already。

呃。

![](img/e0108a6152d68a9bb5b6e57eaca70513_9.png)