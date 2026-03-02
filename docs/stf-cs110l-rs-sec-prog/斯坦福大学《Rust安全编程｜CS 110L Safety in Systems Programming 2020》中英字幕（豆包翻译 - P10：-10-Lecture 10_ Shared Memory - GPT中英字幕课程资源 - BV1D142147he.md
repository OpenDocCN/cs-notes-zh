# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P10：-10-Lecture 10_ Shared Memory - GPT中英字幕课程资源 - BV1D142147he

Okay， great。 we're gonna do a lot of context switching today between slides and examples。

 but hopefully we have time for all of it。 So welcome back to lecture， everybody。

 It's a pleasure to have you all here。 Thank you for coming Today。

 we're gonna be talking about multithreading and rust with shared data And you might be wondering。

 okay， like is there any other way to do this other than shared data。

 Turn out there are other exciting models for concurrency that we'll talk about next week。

 But today we're talking about shared data， which is hopefully。😊。



![](img/05280f21c18e7a2d58614225a7ec8600_1.png)

Familiar to you from CS 110。 so at the end of last lecture。

 Ryan brought this example of the extroverts demo and can somebody quickly recap what this demo was about and what it was showing。

Like what was the weird issue that we saw at the end when like， you know。

 Jerry's name just kept on popping up， like what was wrong with this？And Courtney。

 how would we fix that？Exact exactly right， And we're gonna see an analog of that in rust， right。

 So in rust， if we try this out， I'm going to quickly， let's see。

 I think I have to swap my screen share now。 I have to open the link for Oh my God， okay。

 so many things that have to happen if I open it and then I will share bam bam one second。 Oh my God。

 too many windows。

![](img/05280f21c18e7a2d58614225a7ec8600_3.png)

![](img/05280f21c18e7a2d58614225a7ec8600_4.png)

Get right back there。 okay so now I'm gonna open the playground people see that right So if we try to compile this if we try to run it it says closure may outlive the current function。

 but it borrows I which is owned by the current function right and wow。

 the rest compiler even like tells us what we can do to avoid this issue right So it's essentially complaining that we are trying to pass a reference into the thread and we don't know how long this thread is going to live right this remember this kind of goes back to the lifetimes issue that one of the first things we talked about in this class and it's something that you should constantly be thinking about how long is I going to live right sounds like incorrect grammar doesn't it。

 how long is I going live but right so how do you like how do you know that your main thread。

 how do you know that you won't just spawn a bunch of threads and this function is just gonna like you know die right and and you're referring to something that lives inside of this function and now you have a dangling reference right Like that would be really bad。

So what Ru is telling us is we have to use a special syntax of the closure if I type in move here。

 what it's going to do is it's going to take the captured variables。

 So okay I should rewind a little bit in a closure。

 you have this idea of the arguments to your function go inside those two you know kind of like pipes those two like absolute value signs in a way these vertical bars everything that's referred to in here is sort of captured by reference in a way right so the nice thing here is that this has like a static lifetime presumably so it's gonna to like live forever in some sense or as long as it's the longest lifetime of the program so we don't have to worry about like like referencing that but this I write here if we say move what it's going to do is it's gonna to move I into the loop and you might be wondering okay isn't that bad isn't it bad that we're moving our counter variableable into the loop。

 what if we tried to reference it at some other point Well。

 it turns out that's okay because remember I。Is a U size right it's an integer type and integer types implement the copy traits and the copy trait means that the move semantics like when you move an integer。

 when you take ownership of an integer， it's going to produce a copy。

Are there any questions about that so far， I think I said a lot。Any clarifying questions？Exactly。

 yes， yes， so these are all references， by the way。

 so we're not moving the so in a way you can think of this as like we're sort of like moving the references inside。

 but we're not moving the strings themselves， the strings live over here and we can refer to them freely but this eye right here this eye is a local variable defined here and we want to make sure we can actually move it into this into this context so that we don't end up having a reference to something that might have been dropped。

Does that answer your question， tripp？Okay， so let's run this and let's see what happens。 Okay。

 lovely。 So we see what we So we see Frank， Patty， Julie。

 Marco and Lauren and John and we run it again。 and we get to see their names in a different order。

 So there's some sort of nondeterminism here， which is exciting。

 We don't know what the thread schedule is gonna do。 It's kind of a fun game to see what's going on。

 Looks like there's a question。 Okay， great， awesome。 thanks， Ryan， So that was that example。

 So I'm gonna swap back over to the slides。 we're gonna context switch back there。

 And then let's continue taking a look at what other examples we might want to see， right。

 So any questions about move before I continue forward or about how closures work and rust。

 This syntax right here with the two vertical bars。 that's a closure。 That's an anonymous function。

 You might have heard of this idea of a lambda function before。 in Cs110。

 you probably use this in the first assignment for Kevin Bacon。

 you have to define a comparator function for lower bound。😊。



![](img/05280f21c18e7a2d58614225a7ec8600_6.png)

![](img/05280f21c18e7a2d58614225a7ec8600_7.png)

![](img/05280f21c18e7a2d58614225a7ec8600_8.png)

And that would tell you sort of like。Equality in a certain sense when you're looking for someone。

Does that make sense？Great， okay， alright now， I'll pause。 Does that make sense。So yeah。

 it's a great question in Ru the captures are implicit， so whatever variables you use。

 so for instance， I here is captured。Ies captured here because it's just being used here so the compiler can sort of infer what's going on there and if you want you know a reference versus a value versus a copy。

 you can define variables before you create your thread and you can just capture those variables that might be copies of what you care about and we'll see examples of that later。

Does that answer your question， Drew？And by the way， this。

 this N C plus plus is equivalent to self in rest。Right， yeah。

 you might want to capture like if this is in a class right in rest or I don't know if class is the right word。

 but if we're implementing you know functions for a struct and we have access to the self keyword。

 we might want to capture certain attributes of this struct so I don't think we'll see an example of that today but conceivably that's something you can do So this move keyword says capture so everything that I reference right like I because I referenced here this move keyword says I'm just gonna move this I which effectively is a copy here because I implements the copy trait right implicitly figures out what we're capturing you're asking maybe what if I pass in arguments here so in this particular case。

 I don't think you necessarily would win much by passing arguments because then in addition to spawning the thread you'll have to also like figure out a way to supply those arguments in there as well and presumably you need to like make copies of arguments then。

But in later on in the lecture， we'll see an example where you can have closures that take in arguments。

 but that won't be used for this particular context for threading that'll be used for like some more like functional syntax I guess but I guess like when it comes to threading here in general we don't we don't like passing in arguments to it oftentimes it's like you like capture things。

That within the scope of you know， yeah， within the scope of the for loop but also that are referenced within the closure right。

 so if I had like threads notice how threads is not referenced here right threads will not be moved into this closure because I didn't use threads inside of the closure。

 does that make sense？Exactly， okay， perfect。Any other questions。Okay。

 that's the case we'll continue forward So then Ryan was also talking about this ticketing agent demo which is another classic CS110 example I saw that yesterday I think Jerry talked about condition variables so maybe you talked about this last week but the idea here is that we have all these different ticketing agents I don't know if this is a timely example because air travels pretty down recently but you got these ticketing agents right and have they have this shared state the remaining number of tickets and while the remaining number of tickets is nonzero you have to decrement it you have to sell the ticket maybe you'll take a break it's unclear right and can someone I guess articulate what the issue is with the code as it stands。

What could possibly go wrong， yes？Exactly because this decrement operation expands to multiple instructions and because it expands to multiple instructions you can sort of have them interleaved in a really bad way like I can try to decrement like for two ticketing agents right I could try to decrement this count in the middle of your decrement right because you'd never know when you're going to be swapped off the processor and then somebody else is going to get a turn to deal with this shared data。

Does that make sense to people， You saw this in assignment3， you saw this in farm actually。

 but you saw it in a different context， you saw it in the context of signal handling as opposed to multithreading right so in numb available workers。

 I hope I can talk about assignment3 because that was due yesterday I think numb availableil workers you'd have this issue where your signal handler is going to incremented and the rest of your code。

 your main thread is going to decrement it And if you don't block Sig child effectively then you could have these things happening at the same time and they can corrupt state and really bad things can happen similarly doesn't even it's not only the other important thing is that when you're making this check this remaining tickets greater than zero you still need a lock you still need to make sure that that access doesn't get interrupted because theyre funky race conditions that happen if you like make that check you believe it's true and then right after you make that check it's invalidated by another thread doing something So these are like the worst kinds of race conditions because you're just pulling your hair out and you're thinking like why what's going on。

like， I can't even replicate this。So yeah， does that make sense to people what's wrong with this example？

Okay。So then we'll move on to the next one so let's look at our attempt in rust right so I'm going to open up some rest playgrounds agains let's see if we tried to write the same buggy code and rust if it would be as happy with us。

 so I'm going to open up another rest playground。

![](img/05280f21c18e7a2d58614225a7ec8600_10.png)

![](img/05280f21c18e7a2d58614225a7ec8600_11.png)

And then we're going to swap over to there， so I'm going to share that screen。



![](img/05280f21c18e7a2d58614225a7ec8600_13.png)

哦。Okay， great so this is what it looks like in rust and yeah you see we have this V new we push a thread and then we have this amperserson mute remaining tickets seems okay right and this ticket agent function what is it going do it so because this is a reference we have to dereference it while the remaining tickets is non-zero or rather greater than zero we will handle call and then we'll decrement it and yeah you know let's see how rust feels about it right。

And let's see。Great， okay， so it does not feel good about it。 It says， you know。

 the argument requires that remaining tickets is broad for static。 So first of all。

 there's this lifetime issue， right， we don't know if remaining tickets is going to live long enough before。

 you know， when we were just moving the loop counter into the closure， that was fine。

 we were just copying it into the closure， we were just saying， oh， we're on this iteration。

 but now they need access to the same piece of data and that's bad So。Yeah， so it's saying， you know。

 help to force the closure to take ownership of I， use the move keyword。 Interest， Okay。

 do you all think we should use the move keyword？Do you think that'll solve our problem？Why not。

 I see some people shaking their heads no。Why， why would the move key Well， first of all。

 let's try to use the move keyword and let's see how it feels about that。 You know， it's like。

 you know， the Ru compiler told me to do it， it must be right right， I don't even need to learn rest。

 I can just look at the compiler errors and I can just follow the compiler errors and they'll tell me what to do。

So let's see what that does。It's taking its sweet time the rest compilers want to do it's doing lot of a lot of checks right it's actually running it Yeah。

 it actually is running it okay。Great。Wow， what do y'all think about that？

We we don't quite it's kind of sad。 We， we got all these agents selling tickets and nothing is happening。

 right， Nothing's quite happening there。Great， okay， what do people think about this。

 What's what's going on。Exactly exactly it's just taking a copy of it right so basically each thread is getting its own copy and like while it's sitting on the processor it's able to decrement it maybe a little bit or something right。

 but it's presumably not able to do much right its they're kind of like they don't have a shared access to the same piece of data so exactly as you said they each have a copy this is bad。

Right， so it's sort of like， they're not even able to work together。 It's really sad。

 That's the whole reason why we like threads so they can work together。 right。

 So this clearly doesn't work。 So let's maybe look at a different attempt， right。

 So we'll go back here。 Okay， instead of just passing it in， what if what if what if we just try to。



![](img/05280f21c18e7a2d58614225a7ec8600_15.png)

![](img/05280f21c18e7a2d58614225a7ec8600_16.png)

Let's see。What if we try to use ref cell and RC， Okay， I see there's a question。's okay， perfect Yes。

 okay， so you might not remember ref cell and RC and that's okay because we kind of glossed over it。

 we didn't have you like have any practice with it， but just to refresh your memory。

 ref cell lets us delay the borrow checker checks to run time so that we can have potentially like multiple like mutable references but at different times right and RC lets us have。

It'll let us have sort of this so the ref cell gives us something called interior mutability if you recall that and RC will let us have multiple references to the same piece of heap data so it used to be that with box you't only have one single reference but now you can have multiple references so I'm just going to open up this example we don't have to like go too far into the details of how Refel and RC work because that's not going to be the focus of today we're going to be talking about other smart pointers eventually but just to show you what that would look like and how the compiler feels about it we can see this right here do people see that。



![](img/05280f21c18e7a2d58614225a7ec8600_18.png)

![](img/05280f21c18e7a2d58614225a7ec8600_19.png)

So I'm just going to quickly go over this。Actually， let's see。Is this right， Yeah。

 So we have this remaining tickets， right？ And what I do is I'm going to say。

I'm going to clone the remaining tickets right so I have this remaining tickets reference I'm allowed to clone it because it's anC right so this was if you recall our persistent data structure we implemented two weeks ago it was a long time ago totally we understand that that was where we had like the linked list that had multiple things pointing to it at different parts right I think we yeah。

So。Here what we can try is we can try making a new RC， we can put in a new ref cell。

 and then we're going to have them。Have references to the same piece of data now。

 this seems a little bit more reasonable， right。So let's see what the compile thinks。

So it's clearly not happy with us。It says， so what does it actually say？It says。

This R C ref cell cannot be shared between threads safely。 It's like， wow， how did it know that。

 right？ How How is the compiler able to figure that out， right？If we scroll a little bit further。

 we see that it says。This trait called sync is not implemented for this， right。

 So now you're wondering what the heck is this sink thing。

 right and required because the requirements of this thing called send， right， So okay。

 so it's saying， okay， certain traits aren't implemented for this， right。

 So just to foreshadow we'll talk about later is that rest encode codes。

 its notion of like thread safety using traits。 And we talked about traits two weeks ago right or so。

 And it's really， it's a really cool， powerful flexible idea because it's lets you sort of。😊。

Place sort of like markings on different pieces of data and say this piece of data is safe to share across a threat。

 for instance， right， but does this error make sense to people？Like what's going on here。

 like what the issue is， are there any questions about this？Sna pause。

What do these traits bring that is thread safefe？No worries。That's great。

 So these trait that's a great question。 And what I'm gonna to show you is that they bring nothing to show that it's threads safefe。

 Basically these traits are symbolic like they basically say。

 so this is another thing that has to do with unsafe rust So when you're actually implementing things like Mut。

 which we're gonna to see pretty soon you're essentially saying that like trust me I did this implementation correctly and because I did this implementation correctly。

 I'm going to market with this send trait I'm to market with this sync trait to convince you that it is safe and you can't implement this manually yourself for other pieces of data because because that would require using unsafe code presumably does that make sense。

😊，Yeah， so you're asking like what do send and syncnc bring nothing， they're marker traits。

 so this is a concept we didn't talk about yet， buts there's this idea that you can have traits that mark certain properties and they only have symbolic value。

 but this is really cool because this lets you organize things in your type system and this lets you sort of place constraints that you can sort of communicate with with the compiler。

Does that answer your question？Yeah， great question， any other questions？Okay。

 so how do we actually fix this， right？ So， so I， so it looks like。Yeah。

 sort of wondering if I should just like show the finished example or like maybe just like step by step。

 show how we get there。Do people have a good sense of why we need to use RC here？

Or why we need to use something like it？Right， okay， so what does RC give us？Exactly， exactly。

 lets us， it lets us point to like the same piece of shared memory that lives on the heap。Right。

So if we didn't have RC right， this year before was that we were just copying things into these threads。

 we need these threads to be pointing to the same thing。

 and at the same time we need this thing to live long enough right， So if we have something like RC。

 it's going to live as long as there's something pointing to it because it has this reference counting property。

In the very first example， we we put 250， the number 250 on the stack。

 And then we passed references to the threads and， and the rest。Compilr complained because it said。

 well， hey， this。Value is living on this one thread stack。

 But how do we know for sure that this one thread is going to outlive all the other threads。

 If it doesn't outlive all of the a threads， then we have a problem because its stack is going to get destroyed and all these other threads have pointers to its stack。

 And now they're going to try to use that value and it's going to be gone。 and that's not good。

 And and this is different using RC because instead of allocating 250 on the thread stack。

 it's allocating it on the heap and then it's keep keeping track of how many references there are to that heat memory so that it can free the heat memory when the reference count hits 0。

Yeah， so really， you can think of this as like a lifetimes issue。

 right before we didn't know that if it was going to like live long enough， right， now。

 we're ensuring that it lives as long as something is pointing to it， which is good。Great。

That is a good question。 Why don't we just make this a global variable I guess the short answer to that is that global variables are not nice。

 we don't like it's stlistically preferred to just not have a bunch of global variables is like one reason I can think of off the top of my head。

 I guess Ryan is there anything else you'd say to that if you want to have these as global variables you need to know exactly how much memory to reserve in advance and in this particular case this program only has a single counter and so maybe it's not so bad we know that there's a single counter and we can make a single global variable but if we're trying to generalize this into code that can be run multiple times maybe at the same time。

 maybe there are multiple counters for multiple different flights and we don't know what compile time。

 how many different flights there are going to be and so we need to be able to support an arbitrary number of counters then global variables actually fundamentally don't work at all because you have to preallocate。

 statically allocate that memory and we can't do that。Exactly。Does that answer your question？Okay。

 so just for like time constraints， just to make sure that we have enough time so people can ask questions。

 I'm not gonna manually type out everything and I'll just show youall like sort of like the finished example of how we'll do this in rust but before we do that So I'm just gonna to sort of just like go through like piece by piece right here I'm going to introduce you to some new types So there's this thing called an arc and there's this thing called a mutex and Mutex in rust。

 I think it's kind of it's kind of a misnomer because it's a little bit more than a mutex that you might be familiar with or a mutex that Jerry has talked about So the Muex and rust I'm just gonna highlight a piece right here it takes in so it's it's a container type you can think of it as a container type like for instance in the sense that a vector is a container type or box is a container type are really ref cell ref cell I think is the idea that you should compare it to right like before we would have used RC and ref cell here we're using this other kind of RC called。

Arc， which I'm going to talk about a little bit in a little bit and we're using Mutex and what Mutex does is it's essentially it's a container for a piece of memory and it ensures that you can have exclusive access to that piece of memory right a good thing to think about would be okay first of all like why do I need to wrap my mutex in an arc right so before before we jump into that。

 let me just describe the semantics of this a little bit more lock will do when you call lock on a muex is it will return to you a reference to what it contains so you can safely you can safely modify that you can modify you know what it's pointing to you can read that value safely because you have exclusive access to it the way it's implemented uses unsafe rust which we'll talk about later in the course but that's how does semantics work Can somebody explain why we can't just do this like what would happen if I just passed in a mutex。

So recall that this ticket agent function is being called in a loop。

What if I just passed one like so this I think goes back to like， you know。

 it's the previous question of why。Why is it that， you know， we can't why。

 why do we need like R C in the first place， What if I just took away like this reference counted pointer。

 Can you show what the code would look like in Ma if you did that， Yeah， sure。 So yeah。

 So then the code in main would look like this。Instead of a。That's what it would look like。

RightAnd we'd no longer be able to do this clone anymore because or actually would we。

 do you all think Mutex implements clone？Okay， so I see tripp， you're shaking your head， no， why not？

Can even go if I search up like rust met， we can even check on a documentation if it implements clone。

 Wow， that's disgusting what happened there。 That's crazy。 Okay。

 but here we'll do like a little sort of just like you know how do we read the documentation together。

 I don't know if you like explore the docs much， you definitely should it's great。

 It's beautiful first of all， right But they have examples and stuff。

 but if we look at trade implementations， it's great It tells you what traits they implement because we talked about traits you're now an expert right we know what debug is。

 we know what you know default is， what drop is。 actually we didn't talk about default。

 but that just says that there's a way to have like a default implementation of this strap or this object right。

 and notice we have these things called send and sync which you know the compiler was yelling at us about earlier。

 but we don't have clone sadly， right So thats that's unfortunately not a thing So let's go back here then。

😊，I guesss right。So clearly we can't just do so are there any questions about why we can't just have a mute text by itself like this？

That's a great question。 So I think we had that over here。 So we tried to use R C。

 And it said it cannot be shared between threads safely， right， And now we want to think about， okay。

 I guess like， could you think of a scenario in which。In which like this makes sense， right。

 so what is an RC doing， for instance， like what does an RC do once it goes out of scope？Yeah。

 it decrements the F count and how many assembly instructions might that expand into？More than one。

 and what does that mean like what if I， what if I have two threads and they both like kind of like die at the same time。

And they both are holding on to an R seat。 What what's going to happen。Well， it will disrupt， right。

 but as you said， that drop is going to cause a decrement， right？

So you have these decrements happening from two different threads going on at the same time。

I think maybe Drew was trying to say that the memory wouldn't free because what could happen is if you decrement at the same time。

 then you might have like the ticket sellers example where it underflows and goes to the top and so now the reference count is huge and the memory never ends up getting freed Sure I mean yeah that's totally something that could happen to I don't know enough about the internal implementation to know if they do like a check for underflow or something like that or if they just assume that it will never happen but。

But the issue here is that this decrement can happen at the same time。

 right and and what and like the fact that this ref count can't be safely， you know。

 there's there's nothing telling us that that this ref count is being updated。

That this ref count update is being protected by a lock。Do you know what I'm saying？

So does that answer your question about why we can't use like a regular RC？

So it wouldn't be so much as like one assembly instruction because we can't really get around the number of assembly instructions you expand to。

 but this has more to do with it protects its update with a lock。

It protects its update with a Mutex and it will do this like the underlying implementation will use some sort of unsafe rust to do that right so that's how we make things atomic because oftentimes we can't control how many assembly instructions things expand out to。

 but we can control exclusive access and we can enforce exclusive access using this lock。

Does that make sense？For sure， for sure。 Yeah， that's a great question。

 Did that make sense to everybody else， Are there any questions about。

 Are there any questions about why。Yeah， that's a great question， so let's go back here。

 so if we just had Mutex， what would happen？Right， okay， great。

 So let's let's look over here what's what's going on here。

 So we have this remaining tickets ref and this remaining tickets thing。 we're gonna clone a mut。

 right， So let's think about So what are what are。😊，That is that， right， yeah。Right。

 that's a great question so if you remember our example with RC when we clone an RSC。

 we're just cloning we're updating a reference count， so the reference count gets bumped up。

 we have an extra pointer to a piece of memory。RightBut that piece of memory。

 it's still one piece of memory。We're still pointing to the same piece of memory。Yeah， in retrospect。

 I should have probably had a diagram for this but。I mean， actually， yeah， I mean， does that。

 I guess does that answer your question？ So like before like we'd have to clone the mutex。

 but now we're clonening a reference to the mutex。 So instead of instead of having like two muexes or actually sorry。

 let me just I'm gonna pull out my iPad real quick and I'll just sketch this out because I think that might actually be better RC and Arc do some funky magic so that when you clone an RC or you clone an arc。

 it doesn't actually clone the thing like you don't get a separate copy。

 what it does is it returns you a handle to the RC， which is linked to the underlying heat memory。

 So it still has the same underlying heat memory。 but it's just bumped the reference count on it and given you a reference to it。

 like before what would happen is you'd have like a mutex。 and then you'd like clone it。



![](img/05280f21c18e7a2d58614225a7ec8600_21.png)

![](img/05280f21c18e7a2d58614225a7ec8600_22.png)

And then you'd have like two mu textes， right， can everybody see this？

Right and that's and that's bad we don't we don't want to have two me Texasexs， right？Like that's。

 that's not good。 But now if we have a mutex， you know。

 we have sort of like a muttex living inside of。So we have like muttex。

 and that lives inside of an arc。You can sort of have。

 we can have like a reference to it in a way so we can have like。You like。

You can have like reference one。 And then if we clone this。And then now the ref counts。Is one。

 the F count is one， okay， and then if we clone that， then we're going to have reference2。

Bam and the rough count gets bumped up to two。 And then if I want to spawn off another thread。

 I can have like reference three。And then this gets bumped up to three。

 maybe this one goes out of scope， so this gets bumped back down to two。

So does the difference between these two pictures make sense so like earlier we would try to clone the mutex and that's bad Now we have one mutex and we have a bunch of references referring to the same mutex。

And because we have a bunch of references referring to the same muttex。We can， can safely。

 you know we can clone these references， we can have multiple things pointing to it。

 but once we actually try to access this Mutex， we'll need to acquire a lock。

 we'll need have in order to have exclusive access to it。I I guess with these two pictures。

 are there any questions about these two pictures？Awe， yeah。

 do you have any other questions about like this in particular or does anybody have any questions about this？



![](img/05280f21c18e7a2d58614225a7ec8600_24.png)

Okay。Okay great in retrospect I should have included something like this in the slides。

 but yeah you know these are great questions so to bounce back to this issue so are there any questions now about why we why we can't just use a mut text by itself。



![](img/05280f21c18e7a2d58614225a7ec8600_26.png)

Okay， so let's wrap it in this arc thing， so this arc is an atomic reference counted point。

 so we'll do arc。New of Mutex new。And then back here， this is gonna to be an arc again。

 So it's going be an arc of a meattex。 And then I just want to point some things out to you about how this is used。

 So this is us initializing that meattex。 And this is us having a thread threads vector。

 So this is a vector of handles so we can wait on our threads。

 And what I'm saying here is I'm saying I want to clone this reference。

 So this is the second picture that I drew right I want to clone a reference。

 and then I want to push this thread。 and this thread is going to call ticket agent with I and with the remaining tickets ref。

 And notice how I do move right But the nice thing about move is move is not going get rid of this right it's not going to move in anything that we care about anything that needs to be shared。

 It's moving in this cloned reference。 So it's moving in remaining tickets ref。

And then we just wait for all the threads to finish。

About this are there any questions about that highlighted piece of code there about what's going on？

And I totally expect there to be questions， this is super confusing， this is super weird。

You can totally put other data types inside of a mutex right so we'll see an example of that I guess like a little bit later in lecture where you can even putstructs inside of it right so in threading there's a and this is really nice because notice like kind of like the beauty of this approach right it used to be like the hardest thing about multithreading is the fact that muttex is and the data they protect are kind of like disjoint from one another like and I don't know like since y'all just learned this in  one10 this might not be like quite as apparent yet but。

It's like the way a muttex works or like the data it protects is defined by how you use it。

 It's defined by where you lock and unlock， but the beauty of this approach is that that locking your mutex is acquiring the data that it's protecting。

 That's what this line here is showing So I'm going to highlight this line。

 I'm going to break it down a little bit。 remainingin tickets lock is going to return some sort of result type。

 that's why we have to unwrap it and it's essentially going to wait until it has exclusive access to this piece of data and it's going to give to you a reference to that piece of data and now that we have this reference。

 I can say okay if it's equal to0， I'm going to break， I can safely make this check。

 and then otherwise I'll handle the call and I'll decrement the reference。

 I'll say I sold the ticket And if I should take a break， I'll take a break。

So you know early like with C++ and C Mutexes， you know they weren't at all tied to the data。

 but now it's totally tied to the data and the nice thing is there's sort of this sometimes you want one lock to be associated with multiple pieces of data this is I don't know like Jerry's like talked about this is kind of like called like a monitor like model that's like a term you might hear thrown around if that terms like doesn't make sense that's okay but that's essentially saying you know this kind of forces you to program in that style this forces you to make explicit like what data is this lock protecting you know in C and C++ that's just implied by how you're using it where you're locking and unlocking here it's much harder to shoot yourself in the foot because you have to say okay this Mutex is protecting one thing and one thing only it's a U size。

Does that answer your question， Courtney？不 sure。推荐。Exactly， yes。It's exactly like a lockguard。

 so I don't know if the people who are currently taking110 have seen lockguards yet。

 but it's essentially so C++ also has an idea similar to this。

 but it's not as rich as that you can tie your piece of data exactly the Mutex it's that you can define an object that when it goes out of scope it will automatically unlock things for you and this is like a very common area of people make with multithreading。

 they forget to unlock things or they don't like do a bunch like maybe there's like an ifche that happens somewhere and you return from your function but you didn't unlock before you return or something like that。

 so exactly like you're describing trip once this thing goes out of scope and it goes out of scope at the end of this loop iteration it will unlock the muttex and it will allow presumably another ticket agent to have access to this piece of data to read from it and to decrement it as it desires。

So I don't know if like styllistically people use if people like explicitly unlock it。

 I think if you want to minimize your critical section。

 you can define braces and you can force it to go out of scope。

 but we can actually just look at the docs here right so what methods are implemented。

 you have new lock you have trylock which I assume is a nonblocking version of this right which you know could be useful in certain contexts is poisoned is it's interesting get mute so they actually don't it looks like they don't really have a non。

W which I mean could be good right， but like if you want to force your critical。

 but like this is nice because this this makes your critical section explicit。

 you have to denote your critical section with like an open curly brace and a closed curly brace and then you know that I think that you know you can make an argument that stylistically is better yeah。

 I guess Ryan， do you have anything to say that？Yep， no that's a if you want to lock early。

 then you wrap the lines of codes that you want。To have the mutex inside of curly braces so that when you hit the end of the curly braces。

 that remaining tickets ref goes out of scope and so it gets unlocked。Right。Great。

 so are there any questions， any other questions about how this mut text thing works？No。

 I'd say it's actually the loop。 it's this curly brace。's it's this one。 Sorry。

 I can't highlight to save my life that one and that one。That is the scope of this。

So by the end of this loop iteration， it will go out of scope， but that's how it ought to be， right？

Actually， I mean， so like， I guess like one thing to consider here is that maybe here we might even want to like minimize this a little bit more because if we're taking a break。

 we don't need to hold on to the ref， right， so I could even say something like，You know。Like that。

 I guess hopefully syntactically， I hope it doesn't get angry at me for saying this。

 but but like this is also like totally allowed， I don't know。Well， let me， okay。

 it doesn't let me auto indent。 There's like this rest format thing。But yeah。

 let's just sort of see how it feels about that。Definitely fix your indentation if you're in a real editor。

 please do。 but this isn't a real editor but yeah， sorry， I just noticed there that this take break。

 it doesn't need the lock there。 So our critical region only needs to be minimized to here while it's reading the value checking it and while it's updating it。

 But this take break doesn't need that。 So before it was actually more sequential than it needed to be。

 But yeah， let's take a look here。 So wow， look at that， it goes from 24924847 wow。

 that's perfect there's nothing nothing crazy going on and then eventually it keeps going keeps going and bam all the tickets are sold and they go home。

 it's the end of the business day right。😊，And yes， in real life。

 we would indent this to make it pretty or you could also just like sort of define this like update function in a separate like if you think that this style is like so egregiously bad that you don't like having braces inside of braces。

 what you should do is you should actually have a decomposed function that will handle this that will so because like I think from a stylistic standpoint that's even better because then this function by itself is atomic right this function by itself will acquire the lock and the nice thing is that the user of your function。

 the user of your function doesn't even need to know that like there's like really they don't have to worry about the fact that there's a lock in the first place right because your function is handling that。

😊，Yeah。Does that make sense to people？Okay。So in the last couple minutes I want to introduce a new example that we won't have time to get to today。

 but just like sort of motivate， so like this is kind of like maybe a little bit of a contrived example。

 but one of the reasons we like multithreading is because it helps us with a lot of IObound operations so like when we're like reading for instance。

 right especially from like network requests so I'm going to switch back to the slides。



![](img/05280f21c18e7a2d58614225a7ec8600_28.png)

I guess something I also wanted to talk a little bit about was this okay another thing I wanted to mention is that there's deadlock danger。

 remember if we had like cycles of references with RC pointers we could have memory leaks if you have similarly if if you do your locks in a bad order you can have deadlocks So Ru doesn't always save you this is one of the ways in which it doesn't save you and we'll review this next time。

 we might we could even show an example of a deadlock that happens in us send and sync。

 this goes back to one of Drew's questions earlier。

 so I don't want to like dwell too much on these two concepts。

 but it essentially says that so Sen says that you can safely move between threads right and this had to do with the fact that you know with RC like if regular old RC。

 we can't safely move that between threads because if you tried to update the reference count at the same time you'd corrupt the state and syncnc lets us have something get reference from multiple threads。

 So the important thing to remember is that。

![](img/05280f21c18e7a2d58614225a7ec8600_30.png)

These are just marker traits， they're symbolic and these safe threading constructs or I guess like these standard library threading constructs that under the hood do unsafe things right they both implement sync and they both implement scent。

嗯。And you know， don't worry， we can like review this next time as well and you're welcome to like ask questions。

 I just want to introduce sort of there's this there's this fun game that people have been playing。

 I think where you're like on a Wikipedia page and you try to like click on links and like you try start it dysentery and get to revolver or something like that。

 Like this is apparently a thing and say we want to do a version of this game where you just started a random Wikipedia page and you try to find a link to another Wikipedia page that is the longest right So like can I find the linked page that's the longest right And you know if you wanted to do this sequentially。

 this is the most straightforward approach， there are no threads。

 there are no race conditions So like let's see how fast it is So just want to do a quick demo here to finish us off。

 Wait a second。 Wait。

![](img/05280f21c18e7a2d58614225a7ec8600_32.png)

![](img/05280f21c18e7a2d58614225a7ec8600_33.png)

Don't wna。

![](img/05280f21c18e7a2d58614225a7ec8600_35.png)

I want to actually open up this one， Oh it not。I have a Tm window open。哦。



![](img/05280f21c18e7a2d58614225a7ec8600_37.png)

Shout out to Ryan to introducing introducing me to the magic of iTm integration with TMs it's quite lovely。

 but so we have this piece of code here that I'll just quickly gloss over it reads from particular so this get it will essentially download a web page it'll download the HTML and this particular one is about multithreading so it's very meta and then what this does it's going to filter out all of the links so don't worry too much about the syntax I'm just gonna describe at a high level this is filtering out all of the links on the web page and then we're going go through each of the links and I'll actually print it out here so you can appreciate how horribly slow it is it's going to go through all of the links and it's going to update a running tally of like okay what has been the like the longest URL what is the longest article so far and what is the length of that longest article and then if the current length is greater than the longest length then we update it accordingly so let's actually just run that so I'm going gonna do cargo run right there。



![](img/05280f21c18e7a2d58614225a7ec8600_39.png)

![](img/05280f21c18e7a2d58614225a7ec8600_40.png)

嗯。And let's just see。Oh， wow， that's even。 okay。 I don't need。

 that's like slower than I was expecting for some。 I。 Oh， yes。 thank you。 That's exactly what it was。

😊。

![](img/05280f21c18e7a2d58614225a7ec8600_42.png)

![](img/05280f21c18e7a2d58614225a7ec8600_43.png)

So it's rebuilding。 So we have to wait for so now we have to wait for the slowness of the rest compiler and for okay。

 great， wow look at that。 look at it， look at it， zoom through all those links like wow。

 So there are a lot of links is what I'm saying。 And when I timed this。

 this took roughly three minutes to get through all of them。 that's the sequential version。 Okay。

 now I'm going go over to the multi threadreaded version。 If I go to link Explorer multi。😊。

So it took three minutes sequentially， and now if I run here。So you might be wondering， okay。

 this is pretty slow too。But。Like that it's done and it was able to find out that artificial intelligence you know rightfully so was the longest article with this length right so no matter where you start。

 no matter even if you start multithreading， somehow all roads lead to AI。

 which I think is I mean but I' that idea that everything just like goes it's kind of funny I think but yeah so like the idea here is that we can zip through things really fast by multithreading and you might be wondering what this batch index is because we're at the end of lecture will save that for next time like that explanation there but I just wanted to show you this one last slide just comparing the time because I actually did time it and the times are pretty devastatingvastate like with the multi threadreaded version so sequential was two minutes and 55 seconds multithreaded was nine seconds So that's crazy right so you definitely win a lot by multithreading because you're able to overlap the way。

😊。

![](img/05280f21c18e7a2d58614225a7ec8600_45.png)

![](img/05280f21c18e7a2d58614225a7ec8600_46.png)

Time for all of these IO operations and that's powerful so next time in addition。

 just wrapping up some of these ideas， well talk about other synchronization primitives and then next next time we'll talk about approaches to concurrency that go beyond shared memory。

So yeah， thank you all so much for coming the lecture and please stick around if you have questions。

Great， yeah， okay， so let's talk about that again maybe。

The choice of Arc over RC I'll actually try to draw a picture for that as well。

 I think that might be helpful so I'm going to stop this share and I'm going to go back to my iPad。



![](img/05280f21c18e7a2d58614225a7ec8600_48.png)

嗯。And then let me just do another share right there， okay。



![](img/05280f21c18e7a2d58614225a7ec8600_50.png)

Its always such a process。Right， so here so this picture was justifying why we need to wrap our mutex in arc。

 Let's think about what could happen with RC。 So if we had RC， right。If we had like。

 so what I'm drawing， this box here is like RC's underlying memory on the heap， Okay。

 so this is like the RC and this is like the ref count。Currently there's one reference to it。

 there's this reference one pointing to it， so reference one。Is pointing to it so the F count is one。

 okay， and let's say we generate reference2。Reference2， and then we move this into thread one。

For instance， right， so now the F count is two， okay？And then we have reference3。

 and then we move that。 So and these are generated by cloning。 Okay， and then we move into。Thread。2。

 okay， so we have like。Say like， this is。Thread one。I can't write， okay， this is thread one。

And this is thread2。And then at the same time， because the schedule is just really malicious。

 I guess， they both drop these references this threat so this says ref2。d。

So remember the drop function gets called once it goes out of scope。

 and then thread2 says Re3 dot drop。But this happens simultaneously， right？

Or sorry I don't know if that's like the right way to say it， but like， yeah， like these。

 these two have these two things happen at the same time。And then this drop。

So like this drop is going to do what it does something like。Reth counts。Minus equals1。

So could you see？Something that might go wrong if both of them try to decrement at the same time。

There totally will be a race condition exactly right it's the same race condition that you actually saw in the ticket agent example that Ryan introduced last lecture right because these were there were all these ticket agents trying to like decrement this like shared variable。

 this counter right this ref count is also a counter and if these two threads try to decrement the counter at the same time once they drop these references that were moved into them then we're gonna have a corrupted state and then you know like maybe like the ref count gets really big or something random like that and then we have a memory leak or something of that nature。

So we need this update to happen autoomically。And that's what Arc gives us so like。

 so like to transition， we'd say like， you know。Ark。Does。This update。Atomically。

 do people know what atomic means， by the way， I don't know if Jerry's talked about it yet。

I guess can someone give like a good definition of atomic？

That's exactly right so like it's all all or nothing is the way I like to think about it because this so it's either like this decrement happens or it just doesn't happen right it can't go halfway through and going halfway through is what leads to problems right because that's when you have like two ticket agents trying to like decrement that counter at the same time because one got halfway through its operation and the other one like started while the other was halfway through。

Precisely so when this gets dropped and when this updates this reference count。

 it will acquire a lock before it does the minus equals。

 and then it will release the lock afterwards。Yeah。

 there are also some CPUs such as X86 that have single instruction increments or decrements。

 they're called atomic atomic integer， not integer。

 but atomic number instructions and so because it's just one instruction it can't be interrupted but on systems that don't have atomic instructions than like Arman mentioned it will use a lock to protect but what if it doesn't live in a register run。

 don't you have to like read it for memory and isn't that like multiple instructions Yeah。

 but there's a special instruction for doing an atomic decrement or incrementments on on a memory location and they're slower than using the normal like read into a register increment or decrement and then write back which is why you wouldn't want to use this all the time it's only something you want to use if you actually need to use it but those instructions do exist and so on CPUUs with atomic support they'll use those instructions。



![](img/05280f21c18e7a2d58614225a7ec8600_52.png)