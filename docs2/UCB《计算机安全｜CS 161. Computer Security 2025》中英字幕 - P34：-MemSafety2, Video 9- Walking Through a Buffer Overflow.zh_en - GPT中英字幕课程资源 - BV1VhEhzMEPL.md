# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P34：-MemSafety2, Video 9- Walking Through a Buffer Overflow.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， so in this section， I'm now going to show you what the buffer overflow actually looks like when the program executes。

 So hopefully from the demos we've seen before， it seems reasonable to say， okay。

 if I overwrite the R with the address of shell code。 then when the program returns。

 It's gonna go to that address， start executing code and find shell code。

 So if you're not totally convinced I'm not gonna walk through the entire demo using the actual X86 instructions that this code would compile to。

 We're gonna walk through the function epilogue， those are the steps that the function takes when it returns。

 and we'll see that when you take these steps， it's going to cause shell code to execute。

 So it's the same ideas before， I'm just really breaking it down by showing you exactly what the function epilogue would do。

 And remember， these are the steps that we saw a couple videos ago when we walk through the steps of calling a function in X 86。

 So here we are in the getS function。 So EIP， the instruction pointer it points at the getS function。

😊，Callling get us the EIP jumps into getdes， and it writes a bunch of user input onto the stack。

 So we're gonna provide the same input as before。 The shell code followed by 12 by of garbage。

 followed by the address of shell code。 And here I'm using the very first approach from earlier where I write the shell code at the very bottom of the name character So the get us function。

 What does it do。 It takes all of the input from the user。 and it writes it onto the stack。

 So the user provides shell code I write some shell code。

 the user provides more shell code so I write a more shell code。

 the user provides 12 by of shell code in total。 So I write 12 by into memory。

12 by is three rows on these pictures。 And then it's time to write the As， and I write 12 of them。

 So I'll write4， I'll write another for， I'll write another for。 And by doing so。

 I've overwritten all of name。 And I've actually also overwritten this value。 the SFP。

 And remember the SFP is what's going to go back into the EBP register。 remember。😊。

EBP tells you where the top of the stack is。 So it used to point over here。

 And that was a reminder to ourselves to say， hey， when you're done with this vulnerable function and when it's time to go back to main。

 the EBP is going to point up here。 That's our little reminder to ourselves。

 Well we've actually cloer that out。 So instead of pointing up here where main stack frame used to live。

 We overrote it with A A A A。 And if you treat A A A A as an address。 I don't know what's there。

 It's gonna be address 4，1，4，1，4，14，1。 That's the A's represented in。1s and zeros。

 Who knows where that is。 I don't know。 So we now have this SFP pointing up into nothingness。

 Turn out doesn't affect this exploit。 So not really a huge deal。

 More difficult exploits might involve exploiting this value。 But for now。

 it just points off into nothingness。 And that's totally okay because what we're really after。

 is this R IP value over here。 if I look at where this R IP is currently pointing。

 I follow this arrow， it's currently pointing in the code section。 It says， hey。

 vulnerable when you're done， please take the EIP and point it right here。

 because these are the instructions of main that need to execute after vulnerable returns。

But the attacker in the getS function， they're gonna say， actually， you know what。

 I'm gonna overwrite this value。 So instead of pointing at the instructions of main。

 which is where it's supposed to point， we're gonna overwrite this with the value B， F， F，FCD 4，0。

 And when I do that， Okay， so R IP is gone。 It all value has been overwritten。

 And now it has this value。And this value just happens to be the address of Shoku。

 like we saw earlier。So our exploit is complete。 The getS function has written all of the malicious data onto the stack。

 and in doing so， we clobbered out the SFP to point to A A A A， whatever that address is。

 And we also clobbed out the R IP to point at the Sheka。

 So the getdes function allowed the attacker to write all this stuff into memory。

So now it's time for vulnerable to return。 So first， we're gonna return from the getas function。

 Remember， we're in the getas function。 The attacker wrote all this stuff as part of getS。

 Now it's time to return from getS back into vulnerable。 So here we are。

 we returned back into vulnerable。 By the way， this movie ESP up by four， not an important detail。

 but it's because I pushed one argument to the getas function。 If that doesn't make sense。 It's okay。

 The important thing is we are now back in the vulnerable function。

 And so now that we're in the vulnerable function。 And we're done。 we call the getas function。

 that's the last thing to do in vulnerable。 It's time to return。 And remember in X 86。

 when functions return， they always execute the function epilogue。

 Those are three lines of instructions that always run when a function is ready to return。

 And these are the instructions that clean up the stack and put everything back where it's where it used to be all that good stuff。

😊，So there are three instructions we have to run。 The first thing we do is we take ESP。

 and we drag it back up。 And what that does is it basically erases the current stack frame。

 So right now， vulnerable has all this space to hold name。 And we no longer want that。

 So we're gonna take ESP。 drag it up to where the EBP is。 So it used to be down here。

 Now it's up here。 This is the standard step you would encounter in a function epilogue。 So so far。

 nothing really bad has happened。 We just took EP， we dragged it up here。

 you might be worried and say， okay， well， all this stuff is now in the abyss。

 It's below ESP and you're right。 but luckily， when we delete things from the stack。

 we usually don't clear out the memory。 So all this stuff just happens to still be sitting here。

 That's fine。 Also not the most important detail， but wanted to call it out。

 in case you're worried about this stuff being below the EP。So anyway。

 the first instruction of the Eloc has now executed。 the ESP has now moved up and。That's good。

 We don't want the EP at the bottom。 We want it appear so that we've cleared out the stack frame for vulnerable。

 but the actual attack is still sitting there。Okay， so what's the next step in the epilogue。

 The next step is we need to move EBP back where it used to be。

 So right now it's pointing down here at the top of the vulnerable stack frame。

 I want to point somewhere else， specifically the top of the main stack frame。

 So I want this to go back to its original place。 How do I know the original address that I stored in EBP。

 Well， I put that on the stack。 remember the SFP， that's the old value of EBP。 So when I'm done。

 I should take the value in SFP， stick it back in EBP。

 and that's going to restore EBP to where it's supposed to be。 except this time。

 because the attacker messed with the stack and overro what used to be an SFP。

 I'm actually going take a A A and copy those bits into EBP。 So EBP used to hold the address here。

 and we're copying A A into EBP。 It's a register can hold any value at once。

 Now it's holding A A A and where's A in memory if I go to that address。What do I find Who knows。

 I have no idea。 You have no idea。 So now EVP is also pointing at who knows where。

 And turns out not really going to be a problem because we're really after the RP。 So yeah。

 EVP is now pointing who knows where If you actually try to access that memory。

 the program would probably crash。 But luckily， we're not going to access that memory。

 Because here comes the part that we really care about。

 The last instruction in the vulnerable function。 It says Re。 What does Re do Re says。

 take the address on the stack。 The next address on the stack。 And that's the R IP。

 That's the address of where I should return to。 and put that address and EIP equivalently what that means is go to that address and start executing code。

 So another way of saying the red instruction is to say。Take the next value on the stack。

 It's going to be the R IP。 Go to that address。 Start executing code。

 So that's what the program is going to do。 It's gonna take this address。

 Go to that address and start executing code。 So notice EIP used to be here。

 I will now take this address。 copy its bits into EIP。 And now EIP points over here in shell code。

 And the instruction pointer tells us the next instructions to execute。

 So we are now executing instructions that the attacker wrote。And yeah， ESP moved up by four。

 not too important for this exploit， but that's something that it did。

 But the important thing is EIP now points at shell code。

 So the next instruction that executes going to be the attacker's malicious code。

 and probably what's going to happen is you get the shell that pops up。

 and now the attacker can type whatever malicious commands they want。

 And this program is compromised。 Whatever this program used to be doing。

 it's no longer doing that stuff it's now running a terminal for the attacker to type in their own malicious instructions。

😊。

![](img/ba4e9c36944e37057736d27683a42917_1.png)

So those are the steps of the buffer overflow。Sorry。

 it's the exact same thing as what we saw from before， the same exploit。

 but we showed you how it works in the context of the function epilogue that runs in X86。



![](img/ba4e9c36944e37057736d27683a42917_3.png)