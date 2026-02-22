# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p19 CMU 15-213⧸513 midterm review session： Assembly.zh_en -BV17jcReyETC_p19-

![](img/f8258147f398ac289f890f23e1c04332_0.png)

그 그냥 거 않은 거。So first thing we see here is a ton of assembly。Well， like I said。

 completely ignore it for now。Let's go down to the actual C code。So we see here we have astruct。

And thisstruct。Means that likely there'll be some sort of memory access。

 so we should expect to see offsets from some variable。

 some pointer in the assembly code we also see two functions， so most likely they're interrelated。

 otherwise both of these functions wouldn't be within the same question part。

So you expect a call from one into the other or a call from one into itself if it's a recursive function。

😡，So let's now go back to the assembly。Okay。Does that know work？こ you主啊。Okay。

 so this why the exam server as a nice built in split feature。 So that way。

 you can bring up the assembly in one section and bring up the C code in the other。Have。타로옥。canどした。

No。

![](img/f8258147f398ac289f890f23e1c04332_2.png)

No。What is that？Yeah， so on the exam， the first time you log in。

 there'll be a pop up that points to this line and I'll tell you， oh， drag this down for a spy。

So on the actual exam， you'll see it'll be very obvious and you'll be able to see it。Okay。

 so now let's look at the function anomy。 So the first thing we see here is we have some sort of input variable。

 right， Where does this variable go When it comes into the function。

 What does the quality color convention say。Into RDI， so let's see where RDI is in the assembly。

So we see the firstvocation or first usage of RDI is right there。And we have a move instruction。

 so we have a move from RDI into some place onto this stack。

We don't have to worry why it's doing that， just know it's there。And we see afterwards。

 the very next instruction， we're taking it out and putting into R A X。

So now RDI and RAX both point to name。 El of us call that。 and so it's for simplicity。

 so I have to keep writing that out。So then next， we'll go back to the Seika。

 So we see here an if statement。Well， when we see that if， what do we expect to see an assembly？

A comparison。 So where is this comparison happening？

Does anyone see a compare in this function at all？So where。Test， right。

 So test doesn't look like your normal compare。 So how come we can use that as a comparison function。

Exactly so what does test do so it'll be really important to understand what assemblymbling instructions do you won't have to know all of them。

 but test is a really useful one that you should know What test does is it adds the two opera together and essentially sets the flags accordingly。

And afterwards， since we're checking jump not equal and the quality jumps check for the zero flag。

All test has to do is say， is this zero or not？😡，So well， what is test comparing， it's comparing AL。

😡，Well， what is AL， This is another thing thatll be useful to have on your cheat sheet。

 AL is the lower byte of RA X。So now what's in RAX？Well， let's move up。

 We see here originally there was n， right， our input， I'll just write it out completely。

 So we have name in RAX。And we have another move into EAX from RAX。

 So does this mean that we're actually doing name， name， So does name go in here into RAX。

Not exactly， so because we have these parentheses。It's equivalent to a de referenceence operation when we use it on move。

 So this is actually equal to。RX。Is equal to star RAX。So now when we dereference that variable。

 and we know RAX is a pointer to name to the name array that was in here。

What do we expect to get out？So which byte does the pointer to the overall array point to？😡，Yes。

To the first character， right， to the first element inside that array。So the address of name， sorry。

 the pointer name is equivalent to the address of the zero element of this array。

So in here we put zero。Because we're accessing the zero element。

And what we're doing is we're checking， okay， does it equal to  zero。

 because that's where our comparison did。So now let's go back to our comparison。

We have our jump nu equal。And if we jump， we're going to go down to 4005，12。Well， that's right here。

So that looks like it's a lot of extra code， so we'll come back to that。So let's say， okay。

 if we don't take the jump， where do we go？We have， instead。A move into RAX。And then， jump into。526。

And 5，26 is the end。So that seems like a quick thing to put in， so let's write that first。

So if it's not equal to zero， which means it's the else case。Oh， is that the？

If it's not equal to zero。We're not going to take the jump。So then we'll return zero here。No， no。

 return 0 here。嗯。Because for us to not take this jump here， we would have to be equal to 0， correct。

Otherwise， we would have taken the jump and gone on to this rest of the code here。Yeah。こらでに。直接吃的外头。

Not always， but 99% of the time， yes。Because what does a comparison do？ So if we have compare。

Becom a。What is that equal to？A minus B， right？And now we do this operation。 and what do we do。

 we set the condition codes。And now all future jumps， all they do are check the condition codes。

 so it doesn't care if there was an explicit comparison beforehand。

As long as the condition codes match， it will assume that the comparison happened。So what test does。

So this test AL。It does AL and A。Well， if it's zero， the zero flag will be set。

And that's what the jump equals， we'll check。So now let's get on to the other part。

So if it's not equal to zero。We're going to go do the else case。Well， what's the first thing we do？

 So we have RA A X here。And we're moving some value from off the step。

 And we know from before that RDI was put into that same location。So， RA X。Will be。Ne。

And then we're adding one to RAX， so they'll become name plus1。And then we're moving RAX into RDI。

Well， is RDI a special register？Yeah， right， it's the same input RDI was the first input argument to this function。

 and later on when we do a call。😡，Thatll be the first input argument to that。

So this return here will be。A recursive call。To Ananni。With。Name plus one。But are we done。

 Is there anything else that it does with this？Well， let's keep going， so after the call instruction。

We get， we do an add instruction here to EAX。Well， why would we do that。

 Where does that end up going over here？Well， exactly。

 so RAX was the return value from this function called annoni。

But it's also the return value from this function that we're in right now。So if we add one。

 it's equivalent to this right there。And that's it for the first function。



![](img/f8258147f398ac289f890f23e1c04332_4.png)

But of course， we're not done and there's a second function。

And it's calledSo fun because assembly is always very fun。是ふ。Yeah。

 what does it mean to add one to string？It's onto a string， right so it's a pointer right。

 so when you add one to a pointer， what happens？A pointer is just a number， right。

 So if we have some pointer X， we add one to it and let's say x is 15 to 13。When we add one。

 it's equivalent to saying one， so plus one times the size of whatever the pointer is pointing to and because the pointer is pointing to a character array。

 all we end up doing is pointing to the next element in that array。😡。

So now we have a bit more code to look at。

![](img/f8258147f398ac289f890f23e1c04332_6.png)

So at the beginning， we see。Var again， right， we have some input to this function。

 So let's find out where it sits。It's in RDI， it's being put into some location on the stack。

 We don't care why， and it's being moved into RAX。😡，So RAX is the same thing。So now， what do we do？

We say， okay， t has。We have some call here。And that happens before any comparison。

So this if would have implied a comparison and because our comparison doesn't happen until here。

We know that this。Has to。Crelate to this right there。So Val has to get some sort of value。

And we're going to call Ananni again。嗯。Because our call queue is to a nanny。And well。

 what we going to pass in？Well， can we pass in Vr， So var is what type？Person P， right？

But what type does Anni expect？ACharac， a pointer， right， a pointer to a character array。

So the C code equivalent of this。Would be whatever is there。

Let me see if I can bring up ourstruct at the same time。Okay。All right。

 so I can't break up our truck， but if you remember our first thing was bo， sorry。

 was our character right？Name。Next thing was a field。And the last thing was a double of some sort。

 I forget the exact name。Okay。So we have a call to Annani and we're passing in the first thing。 well。

 the first thing in thestruct is name， right？So that's how we can get away with this assembly of just passing the pointer to this overall struct because that pointer points to the first thing in thestruct。

 which is name。Okay， so now we've done that and we see we have once we return。

 we have a few more instructions here。Before a comparison。So let's try to figure out what that does。

So we're saying， okay， move RAX。😡，So whatever the return value from anmi， which is stored in Bell。

Because that was the return value from ani。And we're going to move that into RSP plus 1c。😡，Well。

 what is one see？What is the decimal equivalent of one seal？28。So let's figure out where it ends up。

So so sorry sorry， this is the stack pointer， so we don't care what that address is。

 We just know we're going to put Val into there。And then， we're going to take。

From some other place on the stack and put that back into RAX。And RAX was our var variable。And now。

 we're going to do。RAX is equal to。Star。Of v plus C。

Because we had those parentheses around the move structure。So what is C？What's the value of C now？

So let's go back to ourstruct。 Well， it's some value。

 I don't want to calculate it off top of my head， but we know name occupies 0 through。I think， none。

And then field occupies 12 through 15。And then this occupies 16 through 24。

Because it's just how astruct is laid out in memory。So now， see。Is 12。

So that means that this instruction is accessing the field variable。😡，So we're essentially saying。

 okay， now we've done that。And we're going to compare 1 c plus RSP with that value。Well。

 what's in 1c+ RSP？We put that value in right there。And that's deal。

And we see here we have a comparison between Do and some other value。Well。

 we know that other value is this。Sup fararrow field。So now we come to a bridge， right。

 Which one do we go， Well， we know at the end。It's a nice， easy return。 if we don't take them。

 if we don't go into the if statement。 So let's try to isolate that first。

So we're saying if it's equal。We're going to jump to 5，66。 That's right here。

And that's just a move1 into RAX。So all this code is accounted for。

 so we don't care about this anymore。So now we just have to understand what this is doing。这。So here。

We have a move of R people say into RA X。So now RAX is equal to。Is equal to var again。

And now we're moving Rs P plus 1 C into EDX。So that is。Where as peoples 1 C。Is Bell right from here？

And then we're moving EDX into RAX plus C。So this is equivalent to star。R A X plus C。

Is equal to some value because it's an assignment。Well， that value is。嗯。About， right？

So here now we have。Var arrowero field。Is equal to the。Well， it looks like we're almost done， right。

 come。This hasn't been accounted for yet。So let's see what this is doing。

So we continue onwards and we see we have these two instructions left。Well， we're jumping someplace。

Does it， are we only in some sort of loop， No， not exactly， because 5。

6 B is right here at the end of the function。And that's just cleaning up at the beginning。

 So we know we have some sort of return here。Because otherwise we won't be cleaning up。

But what we return？Well， the return value is stored in RAX。And we move a0 into RA X。

 because E A X and R X are the same thing。So we're essentially returning 0。So at the beginning。

 all the assembly looked like a lot， right， but once you start decompiling it or I guess compiling it。

😡，And now you have a lot of C code。That maps to small chunks of assembly code。

So once you figure out what the C code maps to， well， once you solve it。

 you never have to look at it again， and you can start crossing out assembly。😡，Yeah。

So at the beginning of our function。We subtracted 28 from RSP。So at the end， we need to add it。

 right？So we can essentially just ignore this as this is part of the cleanup。So this has no effect。

 has no visible C code attached to it。吴丽敏。So yes， but now we have a jump here， right？

We have a jump from here。To there。哎。Yeah。Okay， all right， so if you have any questions。

 please come up， we'll be sticking around to answer anything you have。

Thanks for coming everybody and good luck on your midterms。Oh， excusecuse me。



![](img/f8258147f398ac289f890f23e1c04332_8.png)

What's the type of field， It's an ink。 It's an in。