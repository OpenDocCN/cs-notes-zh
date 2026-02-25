# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p23 -P23-Lec 22 - First Class Functions Part 3.zh_en -BV1zQ27BeEfF_p23-

![](img/4b9d4a88c5fef29875345b3cb9cd3155_0.png)

![](img/4b9d4a88c5fef29875345b3cb9cd3155_1.png)

Sorry， noises。Can you kind of hear me okay， it's kind of at the wrong angle but it seems like it's a great。

 okay， cool。Hello everybody， Happ Tuesday。 I hope everyone's enjoying the renewed sunny weather。😊。

I don't think we have any logisticy things to go over。

 does anyone have any questions before we dive in on content？Okay， cool。 In that case。

 we are doing what it says right up here。 We are wrapping up closures。 We honestly。

 we don't have that much more to do to actually get them implemented。

 but because we're tiny bit behind schedule， I am doing some cooking show magic。

 I've gone ahead and put in the implemented version instead of doing it in front of you。 And instead。

 we're just gonna sort of talk through it。 But then most of the class we're gonna get to work on the works sheet that you see there before you。

 And then on a couple of other exercises related to closures。

 So're just gonna keep thinking about closures。 And after today。

 we're just going be done with first class functions。

 So get ready all of your questions about first class functions because this is gonna be we're gonna move on to optimization on Thursday。

😊，Alright， in that case， let's go ahead and take a look at。



![](img/4b9d4a88c5fef29875345b3cb9cd3155_3.png)

Our compiler。So as you may recall， well you know what， let's actually。

 let's take a look first at the picture。 So we've been talking already about our scheme for how we are going to implement compilers compilers how we're going to implement closures。

 And this is sort of the picture that we drew for ourselves so we didn't actually draw it out on this image。

 And what we decided was， okay， if we are setting up the stack for this anonymous lambmbda。

 right when we are passing off control to that。 What it should see is something that looks like this right。

 it's return address at the end same as always， nothing unusual there。 First argument again。

 same deal right， we're seeing that three argument， which is why we're seeing that right there。

 same deal。 And then we have one big change， which is now we have this thing pointing off to something that lives on the heap。

 What is that thing that lives over there on the heap。 Well， it's this orange boxed thing a closure。

 And what a closure is。

![](img/4b9d4a88c5fef29875345b3cb9cd3155_5.png)

Closing。Is some kind of representation of the body of the function that's actually going to be used。

 So the way we have chosen to represent that is the address of the first instruction instruction that will appear after this label。

 I will often simply write this label in order to remind ourselves of what it is。 But remember。

 of course， we can't fit that big long string in 64 bits。

 What we can fit is the address of that first instruction that will appear after that label。

 So that's what's actually going into there。 And then we have this idea of free variables。

 So all of the things that are going to be referenced within a given snippet of code that are not also defined in that same snippet。

 right， So if we take a look in here， we can see that we are defining Y， and then we're using Y。

 not a free variable。 because we are defining Y， that is a bound variable。 But in contrast。

 we also have this X thing。 And that when we are looking specifically at the snippet of the program。

Is a free variable， right， That is not something where we can see how we have gotten a value for x。

 and therefore that is a free variable。 And so， in fact， it is X， right。

 the representation for x that we have chosen to put inside this closure。

 because that is the thing that we need to go ahead and package up with the representation of the function body。

 right the representation of the function body。 that is the thing that we need to package up in order to make sure we have all the information we need in order to run that anonymous function when the time comes。

So we have questions about this overall scheme。 I know we haven't actually seen how it gets implemented in the compiler yet。

 but we have questions about this picture。One fun question I got。 Last session was， hey。

 we just wrapped up the entire symbol table in the interpreter。

 Why not do the same thing with the compiler。 Like we we're bothering to do all the stuff with free variables。

 Why not just wrap up the entire symbol table。 And then remember， of course。

 the symbol table exists in the interpreter， easy enough to bundle it up there。

 The symbol table exists at compile time， But no longer exist by the time we reach the runtime for our compiled code。

 So what would it mean to actually bundle up the symbol table， right。

 It would just mean doing all the same work that we're about to do， but doing it for more items。

 right， we would just go ahead and do all the same work that we're about to do。

 But for everything that appears in the symbol table， and we know we don't need to do that。Okay。

 seems like we're feeling comfy with this picture。In that case。

 let's go ahead and see how it plays out。In our compiler。All right。So let's take us through it。

The first thing we're going to want to do is take a look at。This， so this is kind of the boring case。

 right？ We already had dealt with the fact that sometimes we have these top level。

Representations of right functions that appear at the top level。

 and we're gonna have to go ahead and make function pointers for them。

 Now we're having to go ahead and make a closure。 But we know that because it's at the top level。

 we're really not expecting that to have any free variables。 And so， in fact。

 we're not going to bundle up anything in that closure other than the pointer to that first instruction。

 right， the address of that first instruction。 So we're doing all of the work of making a closure here。

 But again， it's kind of the boring version of making a closure。

 So we are indeed going ahead and getting that address associated with the function。

 we're doing that。 we're saying， okay， once we've got that inside Rx。 Well。

 now we want to go ahead and put that at a particular spot on the on the heap。And then we're saying。

 okay， well now I want to make sure that that pointer to that right。

 the pointer to the closure is going to be appearing inside REX or even applying the function tag。

 I'm actually reusing that same function tag that we were using previously when we were just doing function pointers and not doing closures。

 we could absolutely have had a different one， but since we are no longer doing sort of old school function pointers。

 I'm just reusing the same one for closures。And then saying， okay。

 and now protect that slot on the heap。 So that is all that is happening right here。 So hopefully。

 that one feels pretty straightforward。Questions， it's okay， if it doesn't feel straightforward。Okay。

 well， let's go ahead and tackle the one that's sort of the more interesting version of the same one。

 right， So we still have to create a closure for the case where we're actually trying to create a closure。

 I'm going to take us through this bit by bit。So here we are。 The first thing we do is we say， okay。

 we're going ahead and getting the， the definition associated with。That item， right？

 So when by the time we actually create a closure， we have。Done that work of figuring out， okay。

 yeah， this is gonna be the name。 This is where it's going to be in the， in the definitions。 Great。

 So let's go ahead and then based on knowing that definition， right。

 based on knowing the body of the definition， Let's go ahead and actually figure out what are the free variables in that snippet。

 right？ So when we just went ahead and took a look at。This part of this program。Right。

 we didn't have to look at anything outside of this in order to know that x was a free variable。

 We were able to just look at this and say， okay， well， I'm seeing a no， don't do smart highlight。

 We were able to see， okay， I know that I am using X， and that I'm not defining X。

 that was sufficient to know。What we are actually going to have is our free variable there。

 and so we are doing that exact same thing when we call our free variable helper function on the body of this definition。

So now we know the list of free variables。For this， this thing that we are actually compiling so far。

 so good。 we are going to have to do something with that knowledge。

 And so I want you to take a look at， I'll give you sort of the hint that we are about to apply this on all of the items inside that free variables list。

 I want you to discuss with someone nearby。 Why are we going to the stack。

 and grabbing out something from an index that was given to us by the symbol table。

 discuss for 30 seconds。So。I'm not sure I understand the question， is this about what tab is Sa？

Where are we putting here。Oh， this is about what stack address is。 What stack address us。

That's exactly what I'm asking you to answer， right， like based on what we're doing， right。

 which is using the stack address helper。I'm not trying to understand the question。So。

All the stack address does right is just say I'm going to go into memory。

I'm specifically going to go look for an offset from RSP， so an offset into our stack。

I'm going to go ahead and grab out whatever lives there。 And so the specific thing that is happening。

Let's look at our closure case。The specific thing that is happening right here is we're saying， okay。

 I'm going to use the symbol table to find something that has named there。

And then I'm going to go ahead and retrieve from that stack address。Whatever I find there。

I'm going to ask you to think it through， look at what's happening here。

 we've gone ahead and gotten our list of free variables。And we can actually take a look at。FV。

If we take a look at。F fee。We can see that what's happening here is we're just getting a list of names。

 right Every time we encounter a use of a name and that name hasn't been bound。

 we're going ahead and actually adding that into our list of free variables。

 So that's just going to be a list of names。That's what our FV helper is that we if you recall。

 we developed that last week。So let's go back down to Im going give us one more reminder because I know we might not have have thought about this for a couple days。

 so I want to also remind us of what we do when we create a closure right so this is the spot where we create a closure。

 we're doing it with one of our AST to AST transformations we said okay。

 we're going to go ahead and take in something that has type Exp land and what we want to get back is type Exp and so when we find a use of an anonymous lambmbda。

Inside。RightLike when we see a lambda written out， Lambda， you know it has this arguments。

 that has this body at the point in the program where we see that。 we might not even be using it。

 we might just be defining the lambda at the point where we see that we go ahead and we make a new name for it。

 we use genen。 we make a new name We go ahead and get the appropriate representation of the body that should no longer be an expert lamb。

 It should be an expert and then we go ahead and make a closure with the name and this is the name that we're gonna to use as sort of its top level name because remember the thing we're doing is sort of hoisting it out to be at the top level。

 And so then we go ahead and put it sort of top level name as the thing that we know about it right here in the closure。

 and we've added it into the defenss list so we can access。That body。

Are there questions about this before we return to the original question？

We're feeling sort of okay about how we put a closure into the representation of our program。Okay。

 cool， in that case， let's return to our original question。

 so this is the first part of a slightly longer， but the first part of what we do when we actually encounter a closure and what I want us to focus on is basically why we are doing these two lines for every item inside our list of free variables。

So go ahead and discuss with folks nearby， let's give it a minute since it seems like we're sort of reading back in that context。

Al right， so I'm going to talk us through， so we just saw how we would end up with a closure inside the representation of our program。

That closure would be placed at this spot that I have highlighted right here in red， right。

 Like it's just wherever we have seen。That。Item inside the program text。

 That's where we put the closure。And so at that point。

 we've got to actually make sure that the assembly that we generate is in charge of putting a representation of the closure inside REX。

 right that's what our compiler is always supposed to do。

And so the work that it is now in charge of doing is actually building up this and putting a representation of this inside R X。

 Now this might be a little bit nerve wracking if we weren't sure that we could get the values of all of the things that need to go inside the closure。

 But in fact， we can， because remember， we have something that tells us basically about things like X。

 right， tells us about the values for any names that we have in scope。

 and that is the symbol table itself。 right， So at the point where we are actually seeing this closure。

 the compile time representation of the symbol table is telling us everything that is in scope at this program position。

 which， of course， is going to include X。 And so when we go ahead and have。This line right here。

 right， It is totally fine if our free variables list includes the name X。

 because we can go ahead and use our symbol table to find the offset from the original base of the stack to find that offset that will get us that value right？

 And so when we are actually accessing the stack right here。

 what we are doing if we are running it for that program that I just showed us is getting the value of X。

 putting that inside RX。 Once we have it inside RX。

 We're going ahead and just putting it at the appropriate offset in the heap in order to build up this closure。

 So that is the work that we are engaged in in this spot of the compiler。

 we are building up that representation of the closure。😊。

And so we can see that the next thing that we actually do while we make sure that we actually have access to all of those names。

 that's good。 But then the next thing that we actually do is build up the rest of the closure。

 So here I'll talk us through what each of these lines is doing and then we can see if we have any questions lingering。

So we do the same thing that we saw in sort of the boring version where we didn't have any free variables。

 we say， okay let's go ahead and figure out where that label is。

 what is the address of the first instruction after that label， Great， we've put that inside reX。

 We're now ready to actually go ahead and put it at the appropriate place in the heap next let's go ahead and admit all of that assembly for moving the appropriate items into the closure right so this is the assembly instructions that we generated right here。

 This is where we actually go ahead and admit those assembly instructions and that's just going to go ahead and say okay for X I can see that that appears at this spot in the stack。

 Let me pop it into this part of the closure。 Y appears here。

 let me pop it into this part of the closure。 C appears here。

 let me put into this part of the enclosure for every name that we actually have in our list of free variables。

😊，And then we go ahead and we say okay， let's go ahead and put the representation of the closure。

 so basically that pointer to the appropriate spot on the heap， let's put that inside REX。

 let's tag it with the function tag， and we just got to go ahead and do one last thing take 20 seconds to discuss with folks nearby。

 why are we doing this。😊，Alright， so I'm hearing it in the audience。

 This is just to prevent overriding the parts of the heap where we have now stored that closure。

 right， We want to avoid the situation where we are going in and just clobbering everything we have just painstakingly put inside。

That orange box up on the top right， we don't want to overwrite that。So okay。

 now is a really good time to ask any questions that we have about。

 I know we can't fit at all quite conveniently here。

 but about how we are building up that representation。

Of the closure in the situation where we might in fact。

 have some pre variables in the situation where this is one of those those anonymous lambdas。Yeah。Oh。

 I think I understand this question。 So this question is， hey， right here， we've drawn the value 8。

 which would be the runtime representation of x。 Is it， in fact。

8 in there or is it pointed to a particular spot on the stack。 Is that the question？ Yeah。

 so what would go wrong if we just had it point to a spot on the stack。Right。

 say I return this lambmbda as you know， the return value from some enclosing function。 Suddenly。

 our stack frame goes away， right， It gets clobbered。 We're using the stack for something else Now。

 all of a sudden， if this is just an address pointing to some spot on the stack。Oh。

 so this is actually the value。 This is the value that should be associated with x。

 And it's totally fine for us to do that because remember。

 we should always have that 64 bit way of representing the value that we are trying to represent。

 And so we can always just go ahead and pop that in there and that's。m sense。Yeah。Enclosure。バイ度。

I'm so glad you asked， that's the next thing we're looking at。

That's almost the next thing we're looking at。 We're going to think about that soon。Yeah。Yeah。

In the code， can you。So I think this question is about the fact that we are going through and doing this process for every item inside our list of free variables。

 so for all of the names that get used but weren't bound。

 we go through this process and what this process does is it goes into the stack to grab out the value associated with the name。

 puts it into RX once it has it inside RX， it puts in the appropriate slot of the closure。I get that。

What were doing。Also。They both time。they both the number of three variables？

I think this question is about the particular offset that we are using。

So the particular offset that we're using for each item when we are going sort of from the current next slot in the heap。

 we never write into the zero width element because we want to leave space for that function pointer right at the beginning。

 but then after that， the first item is going to appear in the next slot。

 the second item is going to appear in the slot after that。

 the third item is going to appear in the slot after that。

And then when we actually want to make sure that we don't clobber that。

 we go ahead and make sure that we are accounting for all of the items plus the slot used for the function plan。

G。Okay， other questions about how we are constructing this closure are ready to go on to using one of these。

Maybe ready？Allright， let's move towards towards trying that。 and we are gonna get to your question。

 which is gonna to be a fun one。 Okay， so we are going have to make surprisingly few changes in order to use one of these when we reach a call site。

 So remember that we have two different places where we handle a call site because we have the call that we do when we are in tail position and we have the call that we do when we are not。

 These are gonna to look actually pretty similar。 So this is when we are not in tail position。

 which means that we are， in fact， using a call instead of a jump。

 So that's sort of the main difference that's happening between is tail versus not is tail。

 So we have only actually changed two lines here。 It is specifically this line。And this line。

And so what I want you to do is turn to someone nearby and for about a minute。

 discuss why have we added line 107， why have we added line 109？

I'm going to briefly show us our picture again to help us think about this。



![](img/4b9d4a88c5fef29875345b3cb9cd3155_7.png)

And back to thinking about line 107 and 109。Okay， so when we looked at our picture。

Our picture was representing how the stack should look when control passes to the lambmbda， right。

 It's expecting to find its normal arguments in the normal spot。

 We always put the arguments right over the return address。

 And then we talked about adding this weird extra thing， which is to say the closure。

 almost as though it is an extra final argument， right？

 And so that's the first thing that we're doing right。

 that very first line that we added is just saying， okay， yeah， I've got that pointer to the closure。

 Let's put that in the spot where the function body is expecting to find it。



![](img/4b9d4a88c5fef29875345b3cb9cd3155_9.png)

So that's change number one。So that's what's happening inside line 107 here。

 We're just putting that in the appropriate spot on the stack。 This is saying， okay。

 what I have inside RX right now is not the thing that I want to actually call the thing I want to jump to。

 remember like the next thing we're going do down here is actually do this computed call and that's not the thing I want to jump to if I suddenly jump to this heap address。

 That's not an instruction。 What are we going to do right so this is then saying， okay。

 go ahead and get me whatever is sitting in the address that is currently sitting inside RX。

 So go follow that pointer to the closure。 grab out what's in there。 put that inside RX。

 And now you can do your computed call So that's what's happening in that line。

And then we have actually done the exact same thing for this next one。

 you can see that we have sort of the comparable things here。

 we put it in a slightly different spot on the stack because of course we are using the stack in a different way when we are doing our is tail situation and again。

 we do the thing of getting the appropriate thing into RX before we do the compute jump。

 So that's all pretty comparable。Questions。About either of these， actually。Okay， in that case。

 I have a question for y'all。 Go ahead and discuss for 30 seconds with someone nearby。 Are we done。

Do we have closures implemented now or are we ready to go？

You can kind of guess since I'm asking the question， huh。All right， go ahead and hum if you think。

 yep， good to go。H， if you think there's something else here。I agree。 There's something else here。

 right？ So it's all well and good that we have made sort of this picture happen， right， We have。

 We do now have this sort of representation of the closure in here。 And， you know。

 the closure itself is in the heap。 That's good。😊，But by the time we reach the body of this lambda。

 right， how are we actually going to access x？Right we have one way or sorry。

 how are we going to Yeah X， How are we going to actually access that。

 We have one way of accessing names so far。 All we've ever done is look inside the symbol table。

 get an offset out of the symbol table， bake that into the assembly。 And then the assembly says。

 yeah， I'm going to this offset from the stack。And that's how we've always accessed names。

So suddenly we're in this situation where yeah， the closure actually does represent this information in some way。

 but we do not have our symbol table for actually compiling our function definition set up in such a way that we could access any of these names。

So we are now ready to actually revisit how we compile the function definition itself。



![](img/4b9d4a88c5fef29875345b3cb9cd3155_11.png)

So， let us turn。

![](img/4b9d4a88c5fef29875345b3cb9cd3155_13.png)

To compile oftenin。Been a while since we looked at compiled Dein。Okay。So。Big changes。

 This line is a big change， right， So this is now。 There have been a couple of questions， I think。

 about， hey， how do we know in which order we're having these values， And like over here。

 we've done this free variables calculation。 and then we've piled them into the closure in a particular way。

 And this is where we take a look again at the the free variables helper？

 And I want you to take a look at this with folks for maybe 20 seconds and tell me is this deterministic or is this not deterministic。

All right， if we think deterministic？How if we think not deterministic？Yeah， this is a herministic。

 right， We're going to put in the same body。 We're going to get out the same answer， right。

 There's no randomness in here， nothing。 as long as we're feeding in that same piece of code。

 we're going to get back the same list in the same order。

 And so we get to take advantage of that down here in compiled Din because what we are going to do。

What we're gonna to do is go ahead and just get back that same list。 right。

 We generate it somewhere else， we can generate it again here。 And now。

 instead of only building up our symbol table for the function。

 instead of only building it up based on the arguments of the definition。

 which is what we always previously did， we now also have access to those free variables。

So if you remember way back when the first time we talked about lexicalco said， okay， well。

 this is going to be about just having those function arguments for the values that are going to be available inside the function。

 This is more complicated now because it is not just about only those function arguments。

 but it is still just about okay， what are the arguments that are available within the particular zone of the program that I am in right now。

 So the source code where I'm at， what are the things that are available So yeah。

 maybe some other point earlier in execution， there was some value Z that was available that's still not available。

 but because I am within this lead expression that makes x available than the body of this function should indeed have access to X。

Obviously， that's something that we touched on sort of Lst。Last session as well。So okay。

 those are sort of the， the big changes。 So we are now setting up our symbol table based on knowing that we're going to need both the arguments of the function and the free variables that are available within the scope in which we were defined。

But then we did have to do a bunch of extra moving， right。

 So now we have to make sure that we are remember that the arguments were already put on the stack in the appropriate spots at the call site。

 right That's how we set it up。 The caller right The call site is the thing that's in charge of putting argument 1 here。

 argument2 here。 Ar 3 here。 That is not so for the free variables as we just saw the free variables got put into the closure at some point。

 And then the call site said， okay， here's the closure in the right spot。

 but didn't move all of the free variables into the right spot。

 So now we have to take over for doing that。 And this is basically all of the code that is going go ahead。

 And based on where we have put them in the simple table go ahead and put them into the appropriate slot on the stack。

 So we actually have to emit code in order to move things out of the closure put them into the appropriate spot on the stack。

 so we can just reference them like normal names。This is a great opportunity for questions。

So basically， we just expanded the symbol table。Can you say more about what you mean by expanded the symbol table in？

We variables。II think I mostly agree。 I think this question is about this line and the fact that previously we were just building up the symbol table based on only including the arguments of the function。

 and now we are also providing the free variables。 And yes， I totally agree。

 We then do have to do all this extra bookkeeping of actually for each of those free variables where we're going through for the free variables。

 We're going ahead and making sure that we can， in fact。

 put those in the appropriate spot on the stack so that we can access them in the normal way。

And then we have sort of all the same normal stuff， right， Like we have the。

 so here's the part where we just have the normal body of the function。

 but here's the part where we are first making sure that all of the free variables have been put into the stack in the right spot。

 Yeah， great question。So far， so good。I'll give you a moment to look it over and make sure we're feeling。

Pretty comfy。One thing that many years I forget to put in is to change the or starter stack index right it's very easy to end up having really weird behavior if you let it clobber the free variables。

 don't let it clobber the free variables。All right， in that case。

 let's go ahead and see it run for a couple of things。嗯。

We've been thinking for a while now about this function。

Quickly predict what you want this to put out。I don't think it'll be too surprising。

But it does put out what we want。 And it puts out 5。 So we now have。A lambdas that can， in fact。

Take advantage of information that is available outside of the function body itself。 right。

 It can go ahead and wrap up the fact that y is 3 and make sure that is available even when we are going ahead and running the Lambda later。

Okay， so I'm going to have us take our five minute break if you want to already start working on the worksheet please feel free。

 please do come down and grab a worksheet if you don't have one。

 or we're going to shift into our totally interactive session after the five minute break at 425。

Also， if you want to start thinking about wacky programs， consider looking at this program。



![](img/4b9d4a88c5fef29875345b3cb9cd3155_15.png)

![](img/4b9d4a88c5fef29875345b3cb9cd3155_16.png)

Hello。Absolutely。In line 1 Oh，9， you show what that many meant on the diagram。The one that said。

 move Ra X。what事。Okay， this was saying that is this the one you actually want to know about or was it okay。

 Yeah， So we're in the context of actually of actually doing a call。

So let's just see sort of what's happening in the surrounding right so we've gone ahead and made sure that we have stripped off the function tag we're about to want to actually do our call which will be based on what's inside RAX So if you remember what's inside RAX at this point at the point that we're stripping off the function tag it is the point or two to closure。

We don't want to jump to the closure。 We want to jump to the function that is actually that first out。

 exactly。Yep， so at the point that we run that line。

 the thing that is actually represented in the inside REX is this， right。

 the value that is stored here， which is to say sort of that pointer to that is the address zero or whatever zero tagged。

And what we actually want， right， we don't want to do a computed call to that。

 We want to do a computed call to this。In the normal gaze， what used to be in what we used to？

What do we used to have in RAX before we implemented this when we're doing a call？

When we had our anonymous functions， but hadn't actually started using closures yet。

 right so we couldn't actually reference the items from the outside world that we wanted to be able to reference。

 We were still using function pointers， So we had gone ahead and actually used this value directly inside。

 we put that on the stack。 and then we it wasn't even in the stack。 This was just inside RAX。

I got it。 Yeah， and then one call。Where do these like the first this is a pointer to the address for the first instruction Yeah。

 this is just the address of the first instruction after the label Where do these instruction live in terms of memory I it somewhere between the heat and the？

Or is in something else？I think， in general。The most helpful picture for you to have of what is happening with memory is that。

The heap is starting at the very beginning and growing down and the stack is starting at the very bottom and growing up。

Obviously， you know there's a bunch of programs running on your computer that's not actually what's happening right。

 we have in fact carved up the memory for the computer in all kinds of different ways。

 both in that there's this like program running over here and there's another program running over here and there's other program running over here。

So like， even though that is a good， useful idea of what's happening。

 That's not actually what's happening。 In fact， we saw that that's not what's happening when we were going and grabbing the piece of memory that we were going use for the heap。

 right， If you remember inside runtime do see， we were just like， yeah。

 we're just gonna get some memory。 And that's our heap now， right， So that's。😊。

Like even though this is a good mental picture to have this idea。

Not actually what's happening at all in practice， there's all kinds of different spots of memory they're using for all kinds of different things and the place that the program is stored is just one of them who controls。

W controls it Well actually， does it live in that same mallick or is it outside of that mallick。 No。

 it's not as So that is something like the the memory that we claim from runtime do C。

 that is just like。Pull up runtime。c。We are the only ones who are allowed to access this， right？

 That is the only spot that that should be。 and that's just for the heat。 That is just for the he。

W to take more action。Alright， so the the stuff that we have up here on the board。

 there's obviously two sides to the worksheet。 So what I want us to go ahead and start with is this side。

 the side that looks like this。 And up here， I have done a little bit of sort of colorful highlighting to try to indicate。

 okay， this part of the program is going to correspond to this part of the assembly。

 Hopefully that is helpful。 Please do grab a paper worksheet if you don't yet have one。

I think I might not even have a digital version this time。 So if you prefer to do it on your iPad。

 go ahead and just grab a paper where she can take a picture and go from there。超得唔湿。

All right I'm going to quickly run us through the first little bit because it's boring just the pink part and don't worry you'll get to keep going。

 but the first thing we're gonna do is we're going go ahead and put 16 inside REX because it's our runtime representation of that nothing too surprising and then we say。

 okay we want to go ahead and put that in that first available slot on the stack so we put it right here and I will now pass control back to y'all it keep it going。

Bless you。Alright I'm going to walk us through it， so we have enough time for all all of our activities。

 so I've gone ahead and done this first item right here。 I said， okay。

 let's go ahead and read off the address that will represent the instruction that appears immediately after this label underscore lambda underscore 1。

 we will go ahead and pop that inside reX。 I'm representing it as the string， but remember， in fact。

 it is actually going to be the address right， that would be a 64 bit address for a real instruction。

 That's what would actually appear there。😊，And now we're going to go ahead and say， okay。

 whatever that address is， let's pop that into the appropriate slot on the heap， which is to say。

 right。Oh， sorry about that right up。Appear。Lambda。toSre one， great， we've done that。

Probably at this point， you're guessing it looks like we're building up that closure that is indeed what we're actually up to here。

 And so now the next thing we want to do is right the compiler actually figured out at compile time。

 these are the free variables and so it went ahead and actually generated the assembly。

 They will take charge of moving those into the appropriate spots。And specifically this time。

 it said， okay， I can get the value associated with y from a particular slot on these stack right so let's go ahead and cross that what we have in there right now and let's put 16 because we've gone ahead and retrieve that from the stack。

And now we want to pop that into the right place onto the heap again， just building up that closure。

 so we'll go ahead and put that up there。At that point we're ready to say okay。

 I want to go ahead and start representing the closure inside REX because that's sort of our promise to ourselves is that what the compiler is doing when we encounter a particular kind of value is getting some representation of that value inside REX so let's cross out what we have in there right now and instead let's put in 1000 because that is what we have inside RDI right now。

Great， we've got 1000 in there。 We're getting close to having that representation of the closure。

 But， in fact， we actually do want to tag that， right。

 So our tag that we are using for functions is 6。 And so let's go ahead and cross out what we've got there and instead put。

1006。Now were ready to go ahead and protect that spot on the heap because we don't want anything else to overwrite it。

 and so let's replace what we had in there before。With that， which is to say right there， right。

 that's where we want RDI to now be pointing。 And we can see that with this。

 we have actually built up a nice little closure。 So we have now run through the part of this program that would actually build up a closure。

So far， so good。Question。All right， in that case， let's turn to the next part of the worksheet。

 if you flip it over， we will start using it。😊，You can see that the situation that we are sort of leaving this in right here。

 right， everything that we're sort of leaving in place that is all represented here as well。

 so we're just continuing with the exact same program。Again。

 I've tried to use the colors to represent something useful about what part of the program is being compiled。

Alright， I'm going to show us just that first instruction because I think it's cool for us to think about what this is actually doing。

 So oops， sorry， that was the wrong value。 Let me actually write it with the right value in there。😊。

Right， oh， nope， that was the correct value。 Sorry about that。

 So we're copying what we have inside RX， which is to say the representation of our closure。

 We are copying that into a particular offset from RP。

 which is to say we're storing it at a normal space in the stack where we often store things associated with names and that's because we have associated this closure with the name you can see that if we take a look right here。

 we've said I want the name F to be this lambda right to be this closure。

 we've just given it a name like any other thing。 And so now inside you know back during compile time。

 the symbol table said yep F is going be this closure thing。

 And so now we're going ahead and getting that runtime representation of the closure。

 which is to say 1006。 and we're just popping that into the slot on the stack that is going to be associated with the name F。

 So we're just treating it like a normal， normal value。All right。

 keep going to the next instructions。Hum if you're ready to go through it as a class。

if you'd like a little more time。be cool。 Let's go through it。

 So this next instruction is going be pretty straightforward right when we encounter a value。

 we get its representation inside reX。 we have encountered the value 3。

 We're going to put its representation inside reX。 let's cross that what we previously had in there and we're going to have 12。

 which is to say the runtime representation of three。

 But now we're starting to get into something interesting because now we are doing a call。

 We' are going to do a call of F， right， and we have this name for this closure。 It's called F。

 We're going to go ahead and do a call of that。 So the first thing we are going to do。

 We're going to go ahead and take what we currently have inside RaX。

 which is to say the representation of one of our arguments。

 and we're going to put it at a particular offset specifically right here。

 So we have now put that first argument at the appropriate place on the stack to set up for a call。😊。

And then we say， okay， whatever it is that we have at offset negative 16， which is to say this 1，0，0。

6 value。 We're going to want to go ahead and put that inside R E X。 I want you to take。Maybe。

 I don't know， 20 seconds， why are we doing that？Go ahead and let someone know nearby。

I will eavesdrop。So hopefully everyone has come up with an answer that something like， okay。

 we promised that we were going to set up the stack for the functions we are calling in such a way that the closure。

 the representation of the closure is going to appear almost as though it is an additional argument right It's going to appear after the normal argument。

 And so that's exactly what we're doing right here。 as we're saying， okay。

 we've got this 1006 thing which actually represents F。

 It represents the function we're going to be calling。

 Let's go ahead and put that right up here So that's what we actually do in that next instruction is place it in the spot where the function body is going to expect to find that closure representation。

And so now we're ready to start actually taking advantage of the other information that's necessary for that closure。

 which is to say we are going to need to get access to this thing in order to do our computed call。

 This is the address that we're actually going to want to use for that computed call So let's move towards that。

 The first thing we're going have to do is take off that tag so let's strip off that tag now that we have stripped off the tag we're ready to go ahead and actually grab what is at that spot in memory so we can take a look at that spot in memory and we can see that what's actually there is this address of the first instruction which we are currently representing as this。

Great， we've gone ahead and put that inside REX。 We are now ready to update RSP。

 ready to do our call and eventually we'll go back from our call。

 I'm not going to walk us through any of that because that's of our normal call stuff。

 What I will actually walk us through is the fact that we are going to update so that right the call is going to leave us in this situation。

With RSP pointing to there， which when we turn to the next thing that I'm about to show us is the situation we're going to find ourse in right there right now when I'm just going to walk us through。

 but are there questions about this one before we move on to actually being inside the function definition and running what appears inside the function definition。

Okay， cool in that case， let's run through what actually happens once we transfer control like once we do that call right because we can see we've got that call right there and that should bring us to inside this function because that's the thing we named F right so it should bring us to the body of the function。

 Let's go ahead。And switch to that。 So now we're just looking at the body of this function， right。

 That is the thing that we have transferred control to previously， we were looking at entry。

 And up here was also entry， right， All of that was sort of stuff that was appearing inside entry。

 But now we see， okay， we've got this lambmbda thing。

 We are ready to actually transfer control to there。😊，So let's go ahead and switch colors again。

 What is the first thing that's going to happen Well we're going to go ahead and take something out of RP-16。

 Now， remember that's not down here anymore， right， It's not that spot。

 RP has been updated because we're inside the function body So that is this spot We're going to go ahead and grabbed that put that inside RAX。

 Now any first guesses about why we might have put that inside RAX。

 Anyone remember what that represents。There's a nice keyword that we keep returning to。Yeah。

 that's our closure right， so we are going to go ahead and do all the work that we promised ourselves we would do with that closure。

 so let's go ahead and take off that tag again fantastic that gets us that。

And now something weird is going to happen。 So now we've taken off the tag。

 And the next thing we do is add。What's going on， why might we do this。

 go ahead and discuss with someone nearby for 30 seconds。Or give us a hint。Okay。

 so probably this isn't super surprising， but we no longer need to get access to that thing that's appearing inside address 1000。

 right， We are inside the body of the function。 We don't need the address of the first instruction inside the function。

 What we do need is those values that are stored inside the closure。

 the values that are associated with names。 We are going go ahead and get those into the right spot based on at compile time where we actually put them inside our simple table and sort of what offset from the S。

 We promise ourselves to use。 So let's go ahead and do that。

 So now we are ready to actually access what appears inside 1008 there， which is to say the value 16。

 we put that inside R 8。 I don't think that should be too surprising。 But now we're ready say， okay。

 what we've got inside address RP-16 right， That is where we actually want to to put it。

 So why is that what we're doing now。 There's a couple of things that I want to draw our attention to right So。

Crossing out this， and we're putting 16 in there， the questions I want you to discuss with someone nearby are one。

 why is it okay for us to cross out this representation of the closure there And two。

 why did we need to put this in the sec。 Go ahead and discuss for half a minute each。All right。

 so the reason that this was okay is because okay， we already actually have this representation of where we have any other values that we might need to retrieve。

 So even if we did in fact， need to keep retrieving values it would be totally fine to overwrite where we have it in the stack because all the information we need about accessing those is now in the register So it's totally fine to overwrite this And the reason we need this right there is that the way we actually use the symbol table。

 the way we use names is we go ahead and pop them into an appropriate space on the stack and our symbol table at compile time kept the mapping from the offset into the stack to the names right and so this means that later on。

 when we go to access y， because it is the second opera end for our addition we are going to be able to just go into the stack and retrieve it as we would any normal name So we've gone ahead and have that symbol table mapping at compile time that represented that this is the place where we are expecting to find the thing associated with why So that's why。

And ahead and did that and so I'm not actually going to take us through all this because it's just normal edition stuff but the thing I really wanted to draw our attention to is the fact that because of the way we have actually moved this。

 set this up and the way that we actually use the symbol table in order to extend it with the additional values as you mentioned before。

 that's why we were able to go ahead and just access the stack as usual when we encounter a usage of why。

Do we have questions。The next thing we do is sort of our same mold。 like we get the left upper end。

 We like store it on the stack to make sure we don't， you know， clobber it。

 and then we grab the right opera end， and then we add them together。 It's like pretty boring。Saもせも。

Okay， cool。 If we're feeling pretty comfy with that。

 I have a couple other reflection questions for us。 So right before the break。

 I showed us kind of a funny program。😊，I want us to go ahead and look at this program。

I've highlighted right here。 I want you to decide what you would like it to produce。

And then I would like you to decide if our compiler is going to produce that。

Go ahead and discuss with folks nearby for a minute on the first question。

 maybe half a minute on the second。Okay， so I'm going to talk us through what this program does。

And then we can decide together if our compiler is ready for this kind of action。 So here we are。

 we've got our RE La function， you can probably guess from its name that it is going to return a lambmbda。

 So here we go， we've got our REt La function。 We go ahead and we do a let expression where we bind the name X to the value3。

And then we say， okay， the， the thing that we should get back from calling this function。

 the return value of this function should be the body of the lead expression。

 So it's going to be a lambda。Right， and interestingly， this lambda is actually going to access。

This value X that was defined inside the ret lamb function。

It is free to actually access this right remember lexical scope you're allowed to access whatever sort of is within scope at the point that you are defining the thing right so this lambda is being defined right here in the source code。

 and so it is totally fine for it to access the value X。That is totally fine。

 And then when we get down here， we say， okay， Im going to go ahead and call Ret La。

So I should get back whatever is being returned by RE Lamb， which is to say a lambda， a function。

 I'm going to call that L。I'll get that back。And then whatever that function is that I get back。

 I'm going to call it down here and print out whatever I get back。And so to me。

 looking at this program， I am only happy if this program returns the value 3， prints the value3。

What I am expecting is that what I bind to the name L is going to be this lambda。

 the return value associated with REt lamb， and when I call it。

 what I should get back is what I should get from x， which is to say the value 3。

So I want you to now discuss with folks nearby when we use our compiler to compile this program。

 are we going to see the value 3。 Go ahead and discuss for。I don't know。 Half a minute。All right。

 let's see it run， what do we get back？We got three， we got the thing we want。

 So the thing that maybe you would be a little bit nervous about with this program is， hey。

 what we do when we put names， when we make names available， right。

 what we've always done is we put that name the name inside the symbol table and we put an offset on the stack。

 and then we store that value at that offset from the stack right that's what we've always done。

 which means that when we run this let expression， that is also what we do right。

 we just go into the stack we pop the value 3 into the appropriate offset。

 which is to say the first available slot on the stack。And then we return from Ret La。

 We wipe away that stack frame entirely， right， That's gone。So oh。

 isn't this going to be a problem for us， that stack frame is gone？

What if we don't have access to this X anymore？But it turns out that in this case。

 what we would actually have done is built up this closure。

RightWe go ahead and we build up something on the heap。

 This is why it was important that we put it on the heap， right， We had that question。

 Why is this closure thing going on the heap， We put it on the heap for exactly this kind of thing because it's true that that stack frame is going away and we're still going to want to be able to call this lambda right later down here。

 We're still going want to be able to call this Lada。

 we're still going to need to be able to access three at that time。

 And so we've gone ahead and we've figured out okay yup X is going be one of the free variables。

 let's wrap that right up in the closure and then that goes on the heap so it's totally fine that we have returned from here。

 wiped away that stack frame。 It's no longer in the stack but once we go ahead and actually call it we'll set things up so that we pop it back into the stack and we can access it like normal。

Why does this call the Lambda function as opposed to printing it out itself？

 So I think this question is about whether this is a call of the lambda or returning the lambda。

 Yeah， so you can see that we have sort of the normal pres that are associated with making a new lambda value if we surrounded this with additional pres。

 this would instead be a call。But we're not calling it。 right。

 We are intending that this value L will actually be the lambda so that then we can call it down here。

 So this is where we have put the Pern around L。 So this is where we're calling it。每三次。Yeah， yeah。

 when we introduce the lambmbda， that's just introducing one of these function at least right。

 that is not actually calling the function。Okay， let's see。

 do we have time for multiple extra exercises。Okay。

 let me real quick talk through some fun stuff that you'll find in the versions of the course compiler that I commit。

 and then we'll see if we have a little time for extra reflection。 So the course compiler。

 very exciting， we now have a fully operational functional programming language。

 it has all of the things that were expecting in terms of first class functions first class functions that work the way we want them to work very。

 very thrilling， at least for me， hopefully for you。 In addition。

 there are a couple of things that are a little bit weird。

 This was a very complicated language feature that we just added。 And unless we think really。

 really hard about how this interacts with other things we've implemented in the past。

 we can get kind of weird behavior。 So here's an example of a function that I would not like us to be able to run that is gonna to be able to run。

😊，呃。Yeah， so here's an example， right， this uses B。B isn't defined anywhere。

 This should not be allowed。 but if we actually take a look through our compiler as it is currently implemented。

 we never wrote anything down that says that top level functions shouldn't be allowed to have free variables。

 And so it's like， yeah， I'll compile that for you whatever。

 And it can run as long as sort of nothing bad happens。 So compile and run。Right。

 so I'm gonna go ahead and add something in there。 that's like hang on， hang on， hang on。

 We're not allowed to have free variables。 If we're at a top level function， right。

 Even birds are changed the sky， et。 et ceter。 So we've got to go ahead and like put in some of those checks。

 So you do when you are introducing additional programming language features。

 you have to think about how these are interacting with the things you already implemented this is not something that uses a lambda。

 This doesn't use any of the stuff that we just added。 And so on the surface。

 we wouldn't necessarily think that this is going interact in a bad way。 but it does。

 in fact interact in a bad way。 So we have to think about the sort of things that we are adding and how it might be changing the rest of our language。

 not a deep point。 I'm just going actually add another version of the compiler that's just going do that check。

 I'm gonna add one other version of the compiler that basically prevents us using a bunch of extra memory for making closures for these top levell functions。

😊，It's just getting lucky in terms of so when we actually， okay。

 so this question is about how does this function run。

 basically what's happening is that this is saying， okay， yeah， I guess B is just a free variable。

 I'll go ahead and make a closure that is expecting to put something based on reading from a slot in memory into that spot it happens to find something memory and so it happens to work。

We're just getting lucky。Yeah， so this again， this should not run， this should not be allowed。

 and I'm going to also push the version that would check for that。Okay。

 we're not going to have time for our last reflection item， but that's okay。

 It was just sort of for funsies anyway。 I will see y'all on Thursday。



![](img/4b9d4a88c5fef29875345b3cb9cd3155_18.png)