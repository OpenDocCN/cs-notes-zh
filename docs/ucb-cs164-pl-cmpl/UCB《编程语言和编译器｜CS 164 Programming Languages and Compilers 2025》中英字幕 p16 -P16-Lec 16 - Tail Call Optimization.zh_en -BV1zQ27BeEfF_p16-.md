# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p16 -P16-Lec 16 - Tail Call Optimization.zh_en -BV1zQ27BeEfF_p16-

![](img/0edf4bc4eb79803b33b0c97822c6a273_0.png)

Alright， hello everybody。 We're gonna start off today by talking a little bit about what's happening exactly seven times 24 hours from now。

 which is to say in our usual class session next Tuesday which is going to be our midterm slot。

 all of the details are on the B courses announcement that you all saw a while ago。

 So hopefully none of this is really very surprising。

 but basically is it going to happen right here in the same slot。 but next week。

 you can find a link here， again in the B courses announcement to you're seeing that right you're seeing that great you can see the link to the midterms from three prior years。

 there is going to be extra support from all of us course staff。

 So the Ts and I have all added extra office hours for the upcoming week So if you have questions that you want to run by us absolutely please come do that my number one most recommended way to study。

😊，If you want my advice， obviously do what works for you， but if you want my advice。

 my number one most recommended way to study is to go through and actually pretend to take these midterms right just go through and answer it as though you're actually taking it and then if any of them at the end of them you're like I'm not actually sure if I got that right。

 I'm kind of confused about this。 come to office hours talk to us about the underlying concept。

 talk about what that was actually testing thatll be my number one recommendation for how to study。

Okay。I want to also briefly， briefly mention the fact that we will have a cheat sheet for the exam and I'm gonna to show you that cheat sheet right now again。

 this is linked。 you can look at it at your own leisure whenever So here's the cheat sheet you can see that it is gonna to tell us about the X 8664 instructions that we're gonna expect you to know about obviously if you read through this and you're like oh I still don't fully understand like there's something that I need to remind myself about the move instruction because what is written on this cheat sheet doesn't remind me enough about what's happening hopefully that's not really happening with a lot of these but do take a look through the cheat sheet to make sure that everything that's on there you feel like encapsulates what you need to know about it or if there's anything extra that you need to study about these but this is basically just to remind you like we don't care if you memorize the particular sort of Ocal functions that you might encounter or might need over the course of the exam like we're happy to remind you of all of those we have sort of string things we don't care if you memorize particular tags that we use for things right all of these things。

that are not like the core concepts we don't want you to spend time doing rot memorization on that stuff right so we've got that here for you to look at so please do take a look through this cheat sheet so that you know which stuff you don't have to bother to memorize because it's going to be there for you this will just be printed out with the exam it will be at the back of the exam you can refer to it throughout we will not allow any other cheat sheets so do not write your own sheet sheet and bring that。

Go ahead and just plan that if it's not on this cheat sheet。

 then that is something that we are expecting you to learn。Are there questions。About that。

 we are going to spend the first half hour of next session doing some amount of talking through what are the big concepts that we've covered so far and what should we expect to see on the midterm。

 Obviously， a lot of that you get just from looking through those prior midterms。

 but there's always the possibility that there's a big concept that we've covered that didn't actually show up on prior midterms。

 So it is good to bring any questions that you might have about topics to Thursday's class and we will talk that。

In terms of what is in scope for the midterm， everything through the end of today's class， yes。

 because there will still be sort of a week to study all of that。

 anything that we cover on Thursday no。Midterm logistics question。我 feel。Pretty okay about that。Okay。

 cool。 Yeah， do stop by office hours。 We love to chat with youall。

 We love to talk through the concepts that we think are important about compilers and。

What's sort of exciting about this space。 So come visit， okay。

So that's enough on midterm logistics for now we will revisit this topic on Thursday just long enough for us to go through that big slide of topics that we keep returning to and。

 talk through what you'll be expecting to see on there。Okay， with that。

 I'm going have us dive back in on implementing our compiler。

 Today is going to be kind of a fun one because today is going to be one of those days that we actually don't end up changing that much about our compiler。

 but we end up getting a really much better compiler out the other end after we make those small changes。

 So I think it's going to be kind of a satisfying one。😊。

I do want to quickly make us a little less satisfied with it。

 so in order to get to the point where we are happier， where we have made the thing a bit better。

 we are first going to make ourselves a little bit less satisfied with it。

So I'm going to go ahead and have us look at some interesting functions。

 So here is a function we didn't actually play around with it last session， but we could have right。

 This is one of the programs that we can now run now that we have functions。

And this is basically just a recursive function that is going to calculate the sum of all the numbers from1 until n。

So we pass in the number n and we're just going to sum up。All of the values。

 all of the integer values from one to n。 So how are we actually doing it in this case， Well。

 we go ahead and say， well is it 0， if it's 0， then great， let's go ahead and just give back 0。

 right， Otherwise if it is sorry， if it's 0， then we get back 0。 if it is anything other than 0。

 we're gonna to have to make our recursive call， So here's a recursive call and we'll make the recursive call on n-1。

 And then once we get back the value from link that recursive call。 we will add that together with n。

😊，And so that's how we are actually getting the， the total of all the numbers from one through n。

 So let's go ahead。 We have both our compiler and our interpreter available to us。

 Let's go ahead and see what happens when we run this program。

 So let's do it with our compiler first。😊，Okay， it's asking us for the number， Let's put in five。

Okay， that looks good， that is the answer I was expecting。Let's try it with a million。好。Well。

 that was not the answer I was expecting。Let's try it now with our interpreter。Okay， great。

 five so far so good。 Let's try it again this time with a million。好。Well。I don't love that， right。

 obviously， when we are providing a million to either of these programs。

 to either the version that we are running with our compiler or the version that we're running with our interpreter。

 something is going wrong。And so I encourage you to think back to what we were doing last week when we implemented functions。

 and I want you to brainstorm with someone next to you。What's going wrong。

 Why can't we run it with five， but not with 1 million？Go ahead and discuss for about a minute。

Definitely。So here's the function that we are considering。All right， what are we thinking。

 what's going wrong？I'm hearing stack overflow。 Yes。

 so probably a lot of us at various times have heard that term。

 even if we haven't necessarily thought about what that actually means。

 what is actually happening when we get a stack overflow， that is exactly what is happening here。

 And so if we think about Okay， we're going go ahead。 We're gonna have this recursive function。

 we're gonna have one fresh stack frame for each of the numbers from n through one。 Okay。

 if we've got five stack frames， right， So say this is the stack frame for n， here's n minus-1。

 right， Here's n-2。😊，There's n-3。 And then all of a sudden， right， Okay， so this is kind of fake。

 We've got this sort of stack here that only has9 slots。 Okay， probably we've got more than 9 slots。

But do we have 9，000 slots， do we have 90，000 slots if we are making a million stack frames in order to get the sum of one through one million。

That's not going to work for our stack。 Our stack cannot， in fact， fit that many frames。

So this is kind of unsatisfying， right， we should be able to add up the numbers between one and 1 million。

 We should absolutely be able to do this。 We've all probably written programs that have done this。

 and so I'm going to show us another program that we could have written to do the same thing and I wanted us to think about this variant。

 so let's go over here。

![](img/0edf4bc4eb79803b33b0c97822c6a273_2.png)

![](img/0edf4bc4eb79803b33b0c97822c6a273_3.png)

And take a look at example 5。1 here， and I want to be clear that this is going to go ahead and get us that same value。

Right， so it's just going to do it in a different way。 So， oops， let's go back up。

 Let's see what's happening here。The main thing that's changed is we now have two arguments， right。

 we have n， so the n that we are trying to actually use to decide what we mean when we say one through n。

 but then we also have this total parameter。And with total。

 we're actually using that to keep track of the total so far。

So if we take a look at what's happening， well， okay， we check if n is 0。 if yes。

 we no longer produce zero as the output。 Instead， we produce this total value。

 the thing that we've been using basically as an accumulator。

 we've been keeping track of the total so far。 and so we'll go ahead and produce that as the output。

 and then if we're in this recursive case。 then okay。

 we'll go ahead and we'll do this sub1 to get the argument for the next call to sum。

And we will add together the current end with the total so far in order to get the new total。

 and then we will return。The output of this entire recursive call， right。

 whatever we get back from this recursive call is what we will produce as our output for the function as a whole。

Do we get why this is doing the same thing。We're feeling comfortable with sort of how this is also getting that total。

Cool， okay， so let's now try copying that and running that。And let's try it first with our compiler。

All right， let's run it on five。 Great， we got the same answer， right， It is， in fact。

 doing the same work。Y， okay， we've still got a stack overflow that makes sense to me。Let's do。Okay。

 it works with five when we use the interpreter。Wa。

 it works with a million when we do the interpreter。Which means there is something we could do。

That would make this work， despite the danger。Of stack overflows， right。

 there is something we could do， maybe not to make that original version of the program actually not give us a stack overflow。

 but there is something we could do that would make this version， not give us a stack overflow。

So what I want us to now do is brainstorm for， let's give it a solid two minutes， Honestly。

 what can we do。In our compiler， to make it so that even if this program does still give us a stack overflow。

 this one does not。 and partway through your brainstorming。

 I'm going to give you a little extra context to think about。 But for now。

 just take a look at these two programs and brainstorm。So here's what I want to draw attention to。

 this is some extra context that might help you with your brainstorming。

You can see that we've got our function， right， here's the start of this function。

And we can see that there's one position where we do a recursive call for this function。

 which is right here， and we can take a look at what's happening between that recursive call and our return。

Maybe that will help us with our brainstorming。Alright， what kind of ideas do we have。

 What might we do。Okay， I'm going rephrase a little。

 but I think what you're saying is let's reuse that very first stack frame we make is that the yes。

 I love it absolutely so let's get rid of what we wrote there before。

 let's say let's not create all those separate stack frames if we are in the position where all of the computation that we need to do with one of our stack frames is over at the point where we're doing the next call that we can just say I don't need to save what's currently in this stack frame anymore。

It is fine for me to overwrite what is in there。 And that means that I can just reuse the exact same stack frame。

 So if we take a look right here where we've got our stack frame 4 N。If by the time we are。

Ready to make that recursive call。 That sort of next call。 If at that point。

 we are already done with all of the computation that needs to happen here。

 If the answer we will get back from the next call。 should also be our answer。 Then we can say， okay。

 I'm going to reuse that for n -1。 Great， I'm done with doing the computation for M -1。

 Let me reuse that for the call related to n -2。 Great， I'm done with all the computation for that。

 let me reuse the exact same space for the call related to n -3 and so on and so on and so on。

 And we can go ahead and make a million conceptually different stack frames that are all using the same spot on the stack。

 All using this space because we just overwrite and overwrite and overwrite。😊。

Are we feeling comfortable with that general idea？Okay， cool。

 So I want to take us back to that assembly that was associated with that second version of our program and the thing I want to call our attention to is basically what is going to happen to the value that's inside RAX between that recursive call and our return which is to say nothing right like because we used call。

 we have to do some sort of updating of RSP right， if we get rid of using call。

 if we get rid of updating RSP， we no longer are going to need to do that right So all we're going to end up having at the end of that recursive call is the return。

Which is to say we're not having to do additional computation with what we get back。

From that recursive call。Are we feeling pretty comfortable with the idea that right and in fact。

 we might even be in the situation where we don't have to touch what's inside RAX。

 but we do have to do something else like maybe print it out。

 that would be an example where we can't get rid of the stuff that's sort of between the call and the return but when we are in the situation where we are done with the function body we are done with the computation that we need to do in the current function body By the time we make another call fantastic we're in the position where we can reuse the stack free。

Are there questions about this overall idea I know we're going to have to make it a little more formal as we move forward。

But we feel good about the general idea of when we can reuse a stack frame so when we don't need its information anymore。

Okay， cool。In that case， I'm going to have us start thinking about this idea a little more formally。

 So what we actually mean here， the sort of official formal way of saying the thing that I just described is we are looking for cases where we're going to have a call in tail position。

Taale position， so let's take a look at some example programs to help us think this through。

So basically， entail position means the only thing。That needs to be completed。

In order to know the appropriate return value for the function were currently in。

The only thing that needs to be completed is the call， right， that call。

 will put something inside REX and putting that inside REX is all that the function needs to do。😡。

That's what we mean when we say entail position。 And so I'm going to have us start thinking this through with some concrete programs。

 and then we'll start actually adding it into the compiler。

 but let's start by just talking through a particular example。

 So here in this top program that we have right here。

 we can see that we have this argument to the function sum F。We can see that some F is a function。

 we have this call， this is one of the arguments to the call。

 I want you to go ahead and talk with folks nearby is this sub1 call。

 this use of the sub1 operator is this entail position go ahead and discuss。All right。

 go ahead and hum if you think， yes， this is in tail position。How if you think no。

 this is not in tail position。😡，H， if you think， I want to keep discussing with folks nearby。Okay。

 it sounds like we're feeling comfortable with the idea that this is not in tail position。

 I totally agree。We are in the situation where this is going to be one of the arguments to a call。

Just getting that argument， right， getting the value associated with that argument and putting that inside R X。

 that would not be enough to call it a day on this function， right。

 That would not give us the right output。Are there questions about that or we feel comfortable with the idea that getting the value of a particular argument that we will use for a call that that cannot be。

Entail position。So far so good， Oh yeah。Itと。在到一。Orrgument to a different。Exactly， yes。

 so we are about to use this argument for something， right。

 We're about to use it to do some other computation。

 and is that other computation that is going to be responsible for putting the appropriate value inside reX。

😡，Yes， great question。So we are going to see other examples。

 We're going to talk through other sub expressions also。Other questions？Okay， let's try another。

 So let's take a look at。Yeah， what do we want to take a look at， let's try。This whole thing。 No。

 you know what， Let's go down here and look at this。If。🤢。

Go ahead and discuss with folks nearby for about half a minute。Is this entail position。

 is this not entail position？All right， how if you think this if is in tail position？

H if you think this if is not in tail position。Okay， sounds like we're not sure yet。

 let's keep chatting。As a reminder， it's in tail position if。

It is the thing that is getting the appropriate value inside REX。Right。

 if evaluating this is going to get what we need inside R E X。

 and we don't need to do anything else in the body of the function in order to actually。Be done。

Fantastic， we are in tail position。All right。H if you think this if expression is in tail position。

H if you think it is not？Y'all are going to have to commit。

 I'm going to keep you thinking about it until you're ready to commit。All right。

 there are only two options。 You have to hum for one。 You don't have to be right。

 but you have to hum for whichever one you think is most likely。 So hum， if you think， yes。

 this is in tail position。Hum， if you think， no， this is not in tail position。Yeah。

 so I agree with the overall hum vibes。 This is entail position， right， If we know what is the value。

 we know what is the value associated with this if expression as a whole， fantastic。

 we know what is the value of the body of the function as a whole， right。

 We're inside this even definition， right And if we take a look at what it would mean to get the value associated with sort of returning from even。

 it is going to be the value associated with having run this whole if expression。

 which means that this if expression is indeed。😊，Entail position。

 are there questions about that because I know we had to think about that for a while。

We feel pretty comfortable with the idea that once we have executed the if。

 we have executed the function。Okay， in that case， let's get rid of that and let's talk about maybe an even harder case。

 So what about。This， I want you to discuss with folks nearby。All right， hum。

 if you think this is in tail position。H if you think it is not。I totally agree。

 This is in tail position， right， We can go ahead and say， yep， if we have gone down this branch。

 if we are in the position of executing this at all。

 then this is going to be the value associated with the body as the whole fantastic。

 This is absolutely in tail position。😊，So let's go ahead and consider this one。

 go ahead and discuss with folks nearby。All right。 hum for， this is in tail position。

Home for this is not in tail position。Alright， I can't totally tell if the coughing disguise。

 but it sounds like we're thinking this is in tail position。 And again， I totally agree， right。

 This is actually the exact same story as the last one。 So we might be tempted to think， oh。

 it's something about appearing towards the end of the program， the end of the body， right， but no。

 right， we are just thinking about is this value right。

 the situation where we are actually evaluating this。

 I this value going to be the value of the expression as a whole。

 So is this value going to be the value of the body of the function as a whole。 Yes。

 if we are going down this path in the if。 absolutely， yes， So this is in tail position。 So okay。

 let's try。😊，I think maybe another two。 So I'm going go ahead and have us look at。This call。

Of some F。Now I want you to discuss with folks nearby for 30 seconds。All right， Hu for， yes。

 I think this is in tail position。😊，Hum for no， I think it is not。Yeah， I totally agree。

 This is in tail position。 And in fact， if we take a look down below。

 this is basically exactly equivalent to when we talked about this， right。

 This is one of the branches of our if， right， It is， in fact。

 the entirety of that branch and therefore， given that the entire function body is just that if fantastic。

 we know that this is going to be in tail position just in the same way that， for example。

 that would have been in tail position right， It's just one of the other branches of the if and the if is the entire body of the function。

 Fastic， let's try one more。😊，So let's go ahead and take a look at this call to E right there。

 I want you to discuss with folks nearby for about 30， 40 seconds。All right。

 go ahead and hum if you think this is intail position。Hum。

 if you think this is not in tail position。I totally agree。

 right we can see that even once we are done executing even we won't actually be done with that branch of the if。

 we therefore won't be done with the if， we have more computation we will need to do before we can return the value of odd right in particular we're going to have to not whatever it is that we get back from that call to even so this is not entail position。

😡，Okay， great。 It seems like overall， our instincts about what's in tail position or not in tail position are exactly right。

 So let's go ahead and formalize this a little bit。 So between last class session and today。

 I've done a little bit of sort of stringing through a new thing in our compiler。

 So we now have this is tail thing So is tail is just a boolean。

 it's another parameter to our compile X function that we've been playing with all along。

 And right now， I have just strung through using false or I actually had to use is tail one so that the compiler didn't complain。

 but mostly I have strung through false everywhere that we actually see a call to compile X。

 But in fact， sometimes false is not the right thing to put in there in order to represent。

 whether the particular subexpression that we are tackling right now is in fact intail position because that's what we want this value to indicate。

 this should be true。 if we are currently evaluating something that is intail position and false if we are。

😊，Currently， generating code for something that is not in tail position。

 So that's the distinction we are going to be trying to draw。Now。

This means that all of the places that we actually need to provide an istail argument。

 there are going to be three things that we might want to place there， right。

 We might want to go ahead and have it be true。We might want to have it be false and we might want to have it be is tail right Basically。

 we might actually depend on knowing whether our super expression right the expression of which we are a sub expressionpression。

 we might depend on knowing whether that itself。😡，Is in tail position。

 So those are going to be our three options。 and basically all of the same intuitions that you just applied for figuring out whether particular expressions are in tail position。

 we are now going to apply those as we basically look through the parts of the compiler where we are having to provide and is tail value and we're going to go ahead and decide。

 So the simplest case for us to look at， we actually already did look at this。

 What if we have the situation we we are providing an argument to a function call。

 What would be the appropriate value to put here in our is tail position right。

What would be the appropriate value to provide to this recursive call to compile X。

 I want you to discuss with folks nearby。 Your options are true。 false is tail。

Are there questions about this， I want you to feel like you have the information you need in order to make this decision。

Okay， great。Sorry， yeah， this is in our function call。Case。

This is the part of our function call that is responsible for getting the value associated with a particular argument to the function into RAX。

H if you think true。How if you think false？Home if you think is tail？Yeah， I totally agree。

 This is going to be false right The value associated with a given argument is just the value associated with that given argument。

 It is not the value associated with the call as a whole。

 so there's never going to be a point where we can say okay yeah now that I've got the value of that argument fantastic。

 we don't need to actually execute the call so this is going to go ahead and stay false we will leave it as it is currently written。

So let's go ahead and take a look at another case that I think will be pretty easy for us to actually reason through。

 I've actually refactored a little bit in order to make it even easier for us to reason through。

 So here's our implementation of do and we can see that right now we are deciding whether we want to have is tail be different based on whether we are the last item item in the do sequence or any of the other items in the do sequence right so if we are the last one that's going to be this spot if we are the anything but the last one that's going to be this spot So go ahead and discuss both of these with the folks nearby。

Okay， for anything but the very last expression in our due sequence， do we think true？

Do we think false？Do we think is tail？All right， I'm hearing false。 and I totally agree， right。

 If we're not in that last spot， we can't just say， yep， that's going to be it。

 We're done with the computation at the end of that。 That's clearly not going to be it。What about？

This one。 so for this one， we are that last element in the do。

 and I'm going to just quickly flash a program that might help us think about this question。

So here I've just crossed out。That example， that last example where we had that call to En。

 just put in do1，2，3。I want you to use that with your brainstorming。All right， do we think true？

Do we think false？Do we think is tail？I agree that is going to be an is tail situation， right。

 if our parent expression or super expression is in tail position， fantastic。

 that last item in the de is also in tail position。😊，On the other hand。

If the due expression as a whole is not in tail position。

 no component of it can be in tail position either。 So fantastic。

 let's go ahead and have that be is tail。 right， We'll just go ahead and keep basically the same thing that our parent。

😊，Had available to it， right we'll just use that exact same value。Okay。Excellent。

 we' are making progress。 I want us to now consider print。

 So we have this call where we get the value of the thing that we want to print E。

 we get that value into R A X。 And I want us to decide。Should that。Be in tail position。

Go ahead and discuss。Hum， if you think true。How if you think false。Hum if you think is tail。

Interesting， interesting。 Okay， so I was hearing is tail。

 I'm not actually totally sure I understand why I think。The reason I'm hearing that is because we。

 one of the things that we were talking about thinking about was。

 is this getting the value associated with。Sort of the statement as a whole inside REX and in some ways we might think of that as what we're doing when we do this recursive call to compile X。

 of course， actually print returns true。 it doesn't actually return the the thing that we are printing。

And so that wouldn't quite be right。 Maybe let's let's consider this a little bit further。

 but I actually want you to think about the fact that even if we were not always returning true after a successful print。

 even then we would not actually be able to use Itail here。

 And I want you to think a little bit about why。All right， hum， if you think true。

How if you think false？H if you think is tail？Yeah， this is going to be a false situation。

 And that makes sense because， you know， even though a good shortcut for us is is this getting the appropriate value inside Rx。

 it turns out that the real constraint is， do we have to do more computation period。

 And in this case， absolutely right， we still have to actually transfer control to the runtime。

 The runtime has to actually print out this thing， There is still stuff that we need to do once we have actually gotten out the value associated with E。

 So it is not enough to just get the value of E inside R X and call it a day。

 If we have this print statement， We're expecting to print。

 We've got something else that we have to do with the value of E。

 And so we're going go ahead and actually leave this as false。False is correct for this。

 Are there questions about that， See like we were maybe a little more confused about that one。

What it all comes down to is do we need to do more computation？Inside the body of the function。

 once we have done this sort of sub expression within it。And in this case， we need to print。

 so we do have to。Okay， cool， fantastic。 In that case， I want us to go ahead and consider， let's see。

 Let's consider let。😊，So we've got a couple calls to compile X inside Let for this one。

 we are going ahead and figuring out okay， there's a particular name that we've got and we're mapping it to the value associated with E。

 so this one is the one that's in charge of actually getting the value associated with E inside RAX。

 and then later on we have something that's associated with the actual body of the let expression and so we're going to have these two separate answers。

 for now I just want you to think about this one。 go ahead and chat for 30 seconds。Okay。

 hum for true。Hum for falls。Humfer is tail。Yeah， I agree。 this is gonna to be false， right。

 We're never going just call it once we have mapped the value X to the value 3。

 right3 is not necessarily going to be our answer。 maybe what we see inside the body does turn out to be just x in which case。

 great， but we're never going just call it based on， okay。

 now we've gotten the value that we're using inside our let binding。

 We have to actually evaluate the body of the let。 That's what gives the value to the let expression as a whole。

 So use that as you think about this next spot where we are actually calling compile X on the body。

 discuss for 230 seconds。All right， how if you think true？How of you think false。

Hum if you think is tail。Yeah， this is an is tail situation， right。

 If the lead expression itself is in tail position， fantastic， its body is in fact。

 the value that gets us the value of the lead expression as a whole。 So that is going to be is tail。

😊，Now let's take a look at our if。So we're going to see that we have three calls to compile X peer。

 We have the one that is actually getting the assembly instructions associated with the test expression。

The one that is getting the assembly instructions associated with the then expression and the one associated with the else expression。

 And so what I want us to do is jointly discuss these three is tail arguments。

 So go ahead and discuss with folks nearby for 30，40 seconds。Okay， for test expression。

 hum if you think true。How if you think false？H if you think is tail？

How if you think I want more time to discuss this。You just want the answer， too bad。

 you got to commit to one of them， keep discussing。All right。 So here we are。

 We're getting the assembly instructions associated with the test expression。

 the thing that helps us decide whether we're going down the then branch or the else branch。

 Hu if you think true。How if you think false？Home if you think is tail。I totally agree。

 This is false， right， We're not going to be done just because we know which way the condition came out。

 right， The condition is what helps us decide， I the value associated with the if expression as a whole going to be the thing in this branch or the thing in this other branch。

 But it is not itself the value associated with the if expression。

So now let's go ahead and think about those two branches。 So for this one， the then branch。

 go ahead and hum if you think true。Hum for false。Hum for is tail。I totally agree。 That's an istail。

 And， in fact， the exact same deal for the one that follows， right。

 So if we're in either of those branches， then we are in tail position if the if expression as a whole is intail position。

 Okay， I'm going have this thing through one more of these recursive calls to compile X。

 So let's take a look at this， which is actually， let's take a look at this。

 The second operaand to addition。 Go ahead and discuss with folks nearby。Okay， how if you think true？

How if you think false。Hum， if you think is tail。All right， we haven't committed enough。

 so we're going to have to keep thinking。All right， how if we think true。How if we think false？

How if we think is tail？Yeah， I agree， this has to be false， right？

We know that at the end of the day with addition， it's fine to get the values associated with both of our opera。

 but then we have to add them together， right， just getting the value associated with one of those opera。

 that's not going to be enough。 We have to do more work after that。 So yes。

 this is for sure going to be false。 So okay， we've done a bunch of these sort of fixes for our compile all calls to compile X that we are making as recursive calls inside compile X itself。

 right All of those that we have dealt with so far have been recursive calls。😊。

One of the things you might notice， we didn't put true anywhere。

we don't have any of these that we just wrote in true。

That's probably pretty frustrating for us right Like we've gone through all of this trouble because some of the time we want to be able to reuse stack frames like we're thinking about the fact that we're trying to take advantage of things being intail position in order to actually do something smarter with how we use our stack and of course that's actually fine because it turns out we have a couple other calls to compile X So if we take a look at compile we go ahead and call compile X on the body of the program as a whole and if we take a look at compile defin。

 we go ahead and we call compile X on the bodies of each of our definitions in our our function definitions。

 So what I want you to discuss with folks nearby for we'll keep this one pretty short maybe two minutes is what should we use here what should we use here。

Go ahead and discuss with folks nearby。Okay， let's talk about this one first， hum if you think true。

H if you think false。How if you think is tail？Better not be is because we don't have that here。

 Right， That was one of the arguments to compile X， but we better not use that one。 All right。

 Keep chatting。All right， for each of the bodies of the functions we define。

Do we want to have is tail for the body？Be true or false。 So hum， if you think true。

H if you think false？I totally agree。 That's exactly the case where we want true。

 right The whole point of doing this is that some of the time when we're inside the body of a function and we figure out that one of the calls that we're making inside there is going to represent the value associated with the function call as a whole。

 that's exactly the situation where we're trying to say， okay。

 the body of this function doesn't need to do anything else beyond that。

 we are done with what we're trying to do with this stack frame and we can go ahead and just overwrite anything in there。

 So this is exactly the case where we want to be able to reuse a stack frame。

And now we can take a look down here at doing basically the same thing but for the body of the program as a whole right remember we have function definition。

 function definition， function definition， body of the program。

 we can actually do the exact same trick with the stack frame associated with entry remember that we're always starting with the stack frame for entry。

 but if we realize that the value that entry as a whole is going to take on is's just the value associated with one of the calls we're making fantastic right let's overwrite everything that entry was using and just reuse that stack frame too so let's go ahead and put true here。

😊，So we have now worked through not how we will implement the approach where we actually reuse stack frames。

 but we have figured out where we can do it right when we are going to do a function call and that function call is intail position that is exactly where we are going to be able to change our behavior in order to reuse the stack frame So are there questions about where。

 where we are in tail position before we take our break and then finally actually implement the thing that involves actually reusing stack frame。

We're feeling okay about this tail position idea and when we can safely assume we are in tail position when we cannot。

Amazing， in that case， let's go ahead and take our five minute break I will see you back here at 448。

 I'm sorry I got so late in the class session today and then we will finish up this implementation。😊。

I question or something。Please absolutely no problem Where are we allocating the memory for this fact？

In the right time， we only allocate memory to heat。So where is this that。We aren't。Right。

 so we are using the exact same stack that the C runtime is using right。

 so C is going along blithely making this nice stack frame for entry。

 the thing that it doesn't even know about， right so we can take a look at let's open runtime do C。啊。

Yeah， so it doesn't actually know anything about entry。

 we had to say this is coming from somewhere else， someone else is implementing this thing。

But we call it。 And if we call it， that means C is going to set up the stack frame for us。

 And then we say， great， we're going to use the same stack。

 We'll take that next lot and that next slot and that next lot and that next slot。

 And that's fine because the stack is always supposed to go up。

So like if I'm trying to visualize the stack overflow that happened earlier， when is it。

 what he is it hitting？Yeah， I mean， if we dug down real deep， we could go ahead and see， okay。

 how is C setting it up。 So if you like。Did you ever have the experience of like going into the Java internals to say。

 okay， I actually want a different stacked up， I really want to be able to go higher than XYZ。okay。

 fair up yeah so we could do that with C right like we could go in and say this is the size of the he that I want this particular program runtime。

 C to have available and that would be the thing that would actually influence us and that's a function of C not OS。

Basically， yes。 so in general， different languages can make different decisions about how to use the stack。

 The reason I sort of hesitate is that we do have this sort of historical view。

 So every time I tell you that sort of visual that's useful to have in your mind of， okay。

 the heap is growing downwards， the stack is growing upwards。The nice visual to have。

 the visual that's going to work for you most of the time is the idea that that's just the memory of the computer and that everyone's just reusing the same stack。

Obviously， again， we actually do know that we are working in the situation I mean many programs running at once and they're doing lots of different things and they're swapping back and forth between them so yes。

 it is C that we would change in order to well how we are running this particular C program that we would change in order to change how much space we have in our stack。

Thank you。 thumbs up。I just want to make sure there is a concrete definition for。Tell is this。

Like you have to make sure。Whatever is in R， Rx is what you are going to return is that。

That's not quite enough because we might need to do something else， right， So specifically。

 if we have a side effect that we need to cause。 So that is exactly the example that we Brian across with print。

So you could imagine that we actually had a different definition for correctness for print and that actually this value E is the value that we want to get from evaluating a print expression as a whole。

And that would be a fine way to define print。 And that would not mean that it was okay to put that this is is tail。

 right， We could not say， yep， that expression is in tail position because we are not done at the end of putting that value inside R X。

 Because we know we need to do other instructions in order to actually print that out。

 So it really is just a matter of， is there other work we need to do before returning control。我。

Rresion is the final thing we have to do。Especial。Exactly， yeah。

 just thinking about what is going to have to happen between call and rent。And in fact。

 we're about to see， because we're about to see how to actually implement this。 We're about to see。

 you know， really what it means。 We're going to sort of understand why what we have threaded through is the thing that makes sense。

All right， so here's our implementation for function calls。 right。

 Here's what we are currently doing。When we encounter a function call。

 we are now going to want to do something different if we encounter a function call that is in tail position。

 And so now finally， we get the name of the thing that we've been spending this entire class session on。

 which is tail call optimization， We'll talk a little bit more about that term and sort of why that's a bit of a weird term but this is what the optimization again a scare quotes that we are about to do is called every single list implementation you have ever interacted with。

Actually implements this。 This is really non-opional。

 Like if you want to be able to do realistic computation with Lisp。

 you have to make sure this is in place， right， your just too easy to run out of stackspace without this。

 So let's go ahead and implement tail call optimization。

 So the first thing we're going to do is we're gonna copy what we are already doing for calls。

 but we're going to specialize this。 So we'll have this first one be just what we're going do in the situation where we are not in tail position。

 So let's say and and not is tail is tail is our thing that's keeping track of whether we are in tail position。

 So we can go ahead and say this is what we're gonna to do in the situation where we cannot reuse the stack frame。

But let's have down here， let's go ahead and say this is what we're going to do in the situation where we can。

Reuse the stack frame， right， What we've been tracking all throughout is。

 is this sort of the last thing we're doing in the body of this function。 So let's go ahead。

And do some changes here。 So the first big change is we are no longer gonna be messing around with what RSP points to right So previously。

 we introduced this whole stack base little helper idea because having a value associated with the new stack base was going help us do a bunch of computations。

 We are no longer going to be changing the stack base。 right RP minus-0 will remain RP minus-0。

 So let's get rid of that。 And that's gonna give us some clues about what we might need to change right。

 This is now highlighting some things that we're probably going need to change Fastic。

 This is clearly the first spot for us to change right we no longer want to be updating RP。

 Let's get rid of how we've been updating RP。 And also。

 we no longer want to use that call instruction， right The call instruction also updates RP。

 That's the last thing we want。 We're trying to keep it the same instead of call。 Let's use jump。

Okay， we're getting pretty close now。 But remember， this is still reasoning about the stack base。

 This is trying to put it in the right spot so that we can then sort of transfer control to some other function。

 It's going to expect things to be in a particular place。

 Our stack frame is now the same stack frame that we have been playing with。

 We want to go ahead and put the arguments right at the base of our stack frame。

 That's what we're going want to do now。We're going to have to be a little bit careful about what part of the stack we use in order to calculate those arguments。

 But that's okay。 Let's try out something first that is going to be a little bit wrong。

 And I'm going to ask you to tell me why it is wrong。So。

Let's go ahead and just use the current stack index。

 So the next available slot in our stack in order to actually calculate the value associated with each argument。

 and then let's move it to the spot where we are eventually going to want it。

 which is to say stack address。So here it is stack。Addres。

But then offset is going to be i plus 1 times negative 8。

 why is that going to be the offset that we want Well。

 remember that we are going to go ahead and expect when we transfer control， what am I doing wrong？

There we go。 No， that's not whatever。 I'll fix the print。

 When we go ahead and transfer control to the next function， even though we're using a jump。

 it is going to expect to have the arguments at the slot right above the return address。

 So that zeroth argument should be at slot one times negative 8。 The second argument， Sorry。

 the one argument should be at the next slot。 The tooth argument， The next slot。

 So I want you to go ahead and discuss with folks nearby。 Why is this not going to work。

 It's not gonna work。 I'll give you the spoiler。Oh， I nested stack addresses。

 that's what I did wrong。Goodness。Go ahead and discuss with folks nearby。All right。

 we're getting close to the end of class so I'm going to talk us through This is saying let's use the top of our current stack in order to calculate it and then let's move it into the bottom of the stack where the next function is going to expect to find it。

 let's see an illustrative example here right so here we are this is sort of set up as though we were doing our standard function calls that we were talking about last week but now what we're saying is okay I'm going to calculate the value associated with M。

 and then I'm going to put it here。Right， which is the spot where the next function is going to expect to find it。

Oh oh， I need why in order to calculate n， right， I had better not actually overrite what I currently have in the stack frame until I am sure I am done with what's in that stack frame。

 right， I still need why。 as I go through and get the next value that I'm then going to put here。

 So let's go ahead and fix that up real quick。 We're just going to do more moves。

 It's going to be sort of annoying， but it's going to be totally fine。

 So let's go ahead and just use instead of stack index。 Let's do。Stack index。inus8 sorry。

 pers8 times I。 So this is basically just saying， okay， that is the next slot that is going， oh。

 gracious。inus8， that's a par。Great， so we're going to go ahead and use that exact same slot in order to。

Store it， right， So once we've actually got。That。Once we have used that stack index in order to calculate the value associated with a。

 we can then go ahead and use that also as the place where we store it。 And then the next argument。

 we will go ahead and use the next slot。 We will then copy this because we're going to have to do another set of booth。

 because remember， this is not where we are expecting to find it in the long term in the long term。

 We need to have it down there at the bottom of our stack。 So let's call this moved as。

Let's make sure that we are actually using it moved as， and what are we going to do in here。

 well we're going to basically do another set of moves so the first move is just going to take what is currently inside that slot。

 right， the slot associated with that argument and we'll put it inside R8。

Get it ready for the next move。 Great， let's do the next move。 We will take what's inside R8。

And put it in basically that slot that we originally tried there， right。

 the slot that is the place where we are expecting to find it when we transfer control to the next item。

 So let's go ahead and do stack address。I plus one。Times negative 8。

 And let's grab out what's currently in R 8 and put it inside that slot。 And now。

 if we go ahead and run this whole thing。And assuming I haven't messed up any of those sneaky pers。

 oops， which I have。 What did I do， Oh， we don't need arg any more。 right， for this one。

 We're really just using that index。 So let's go ahead and tell the compiler that's totally fine。

Let's go ahead and run。Our nicely refactored program。 Remember， we have the two different versions。

 We are not expecting this to make our original sum version work。

 but we should now be able to run our newer， nicer refactored version work。

 Because if we take a look at what was the difference there。 It's the fact that that recursive call。

 that call to some is in tail position。 right， That's why we were talking through all of that。

 So let's go ahead and try out。Open。Compile and run。Let's make sure it still works on five。It does。

And let's try it on a million。And it worked。 We have successfully implemented tail alcohol optimization。

 We now have a practical functioning version of Lisp。😊。

So we didn't quite have time to run through our worksheet today。

 but I will make sure that we carve out a little time for that in our next class。

 This is a really good time if you have questions about tailco optimization。

 the thing that we have just。Implemented。I love this question。

 why did it already work and our interpreter， it's so weird that we were able to run this same version with。

 let's open the interpreter。We are able to go ahead and run interp。

This version and run it on a million。 And it was slower。 Let's see 1，2，3。Slow， slow， slow。

 But we got the answer。 And so yes， exactly what you suggested is exactly the reason that this works。

 So let's look at our interpreter。 So Ocael also implements tail call optimization。

 right that is a useful thing for a representation of an implementation of a functional language to implement。

 And so if we take a look at what we've been doing throughout you can see that every case where a call。

 a recursive call to Inter X， would actually be the results of the super expression。

 I have been putting it in tail position， right， you can just go through and look at all of these cases and every case where it is。

 in fact， the value associated with the superex， you will find that that recursive call to interex is in tail position。

 which means that the Ocal implementation can actually make that work。 it is reusing the ss for us。

 In't that so cool。 Yeah， great question。😊，Other questions。All right。

 we feel good about tailco optimization， I love it。In that case。

 I will see you on Thursday for discussion of midterm topics and some other topics that won't be on the midterm。



![](img/0edf4bc4eb79803b33b0c97822c6a273_5.png)

![](img/0edf4bc4eb79803b33b0c97822c6a273_6.png)

![](img/0edf4bc4eb79803b33b0c97822c6a273_7.png)