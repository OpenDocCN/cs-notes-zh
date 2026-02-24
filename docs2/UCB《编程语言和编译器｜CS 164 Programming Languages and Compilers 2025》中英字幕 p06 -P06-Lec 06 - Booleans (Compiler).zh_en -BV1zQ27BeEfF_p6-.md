# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p06 -P06-Lec 06 - Booleans (Compiler).zh_en -BV1zQ27BeEfF_p6-

![](img/604e5d78136eb458656cc38b4ae7cbc6_0.png)

![](img/604e5d78136eb458656cc38b4ae7cbc6_1.png)

![](img/604e5d78136eb458656cc38b4ae7cbc6_2.png)

![](img/604e5d78136eb458656cc38b4ae7cbc6_3.png)

Alright， hello， everybody。 I hope you're having a very beautiful Tuesday。

 I'm certainly enjoying this， this nice weather that we've got。

 I wanted to say another huge thank you to everyone for filling out the drills。

 It really does make such a huge difference to us in figuring out what topics folks are struggling with what's feeling clear what's not feeling so clear。

 So huge， huge thank you。 Also additional huge thank you to those of you using humor and those brightens my day。

 And I appreciate you。 I want to talk quickly about the one thing that gave us a little bit of trouble。

 which was about what is showing up in our language at this point。

 And so this was the only thing that seem to be giving us some problems。

 I totally get why that would be confusing， right， We definitely have， Oh， sorry。

 add one that should be sitting there。 We definitely have things that look quite like that。

 We have add 1，50。 We have add one。😊，Add 1，50， right。

 So we certainly have things that look quite a lot like this one。 But， of course。

 they're not quite like this one because right now， we don't have anything that could be X， right。

 We don't have a way to introduce names in the little miniature listsp that we are building up。

 So we'll get there。 but not quite good。 So that was the same one that seemed to be coming up for most folks。

I also want to touch real quick on sort of reflecting on what was common in the things that are still feeling unclear and overwhelmingly。

 the number one thing that still feels unclear is Ocamel， right Ohamel syntax，el semantics。

 why we're doing things and exactly the way we're doing things in order to communicate with the Ocamel compiler and I totally get it that is totally natural that at this stage that is still going feel very unfamiliar。

 we haven't had that much practice with that yet so far。

 but I want to do really quickly a little thought exercise on what is sort of the mindset that we're bringing to the task we're tackling here in compilers land。

 And so I'm going to set up some false economies， but hopefully they help us sort think through the options here so。

😊，If we think about what is important in 164， is it that we sort of just get Ocael or we find it very natural versus having strategies to build experience。

 build understanding， having ideas for how we can get a deeper understanding what Ocamel is doing if it's a choice between just those two。

 I would much rather we be in position number two here。

 of having strategies for expanding our knowledge of understanding。

 knowledge and understanding of Ocael， rather than having a fixed understanding。

 but a pretty good understanding， like much better to be in the situation where we have some way of expanding that knowledge。

 and then similarly， would I rather we be in the situation of memorizing all the syntax and semantics of Ocael。

 but having no idea how to learn the next language versus having really good strategies for building up understanding and knowledge of new languages。

 I would much rather we have the strategies for building up new knowledge and understanding and new languages。

So just trying to get at basically the idea that it is okay to be making mistakes in our Oaml programming。

 you'll notice when I'm up here doing my live coding on our compiler， I'm making a ton of mistakes。

 and that is not just performative right Like sometimes obviously it's pedagogically useful to make mistakes。

 And then I have us work through them。 And that's great。 And I'm glad we do that also。

 But sometimes it' I make mistakes。 I make mistakes in languages that I use all the time。

 This is totally natural。 and this is totally fine。 and there's nothing wrong with that。

 I know it can feel really weird when a lot of us are sort several classes deep in our our sequence here at Berkeley where maybe not used to making that kind of mistake anymore。

 I can feel really unnerving， but it's totally fine。 It's totally normal。

 We just have to sort of keep going through that process of getting more familiar with the languages that we're working。

So hopefully that gives some idea for how we are thinking about this sort of new language acquisition skill that we are working on right now and the fact that it is totally okay to still find O Caml and natural and totally okay to be making mistakes in okaycal。

Okay， so the main things I wanted to make sure we touch on。Oh， I did also want to talk about， though。

 So we are obviously doing a bunch of Ocal programming up on the screen here。

 And so I want to make sure that if folks are having sort of confusions about what's happening in Ocal land that we have strategies for clarifying that。

 So overall， basically we have about even number of answers of people saying it's going a little too quick in class。

 going a little too slow in class。 So that's about where we're normally trying to land is this sort of even numbers on both sides。

 But if you are finding something confusing that is happening up here when we are building our compiler。

 highly highly recommend a number of possible courses。

 So one thing you can do is refer to our course notes that talk about the compiler construction。😊。

AndThose are specifically about sort of the process that we followed here when we are building up the class compiler and they talk you through every step of it for any of those is great。

 We also have the repository where we actually commit all of the stages of the course compiler that we build up here in class。

 So you can go through and just look at those dips。 say， oh， okay。

 what was the thing that actually change between here。 You can make your own modifications in there。

 You can tweak it。 You can change what it's doing。 Also a great strategy。

 Another thing you can be doing is。😊，When we're here in class and one of these things comes up。

 raise your hand。 Often what happens is I introduce a new concept。

 and I forgot I was supposed to explain it。 So please， please， please just stop me， say， hey。

 that wasn't clear。 let's talk through that again。 and that's totally fine。Okay。

 so those are some of our strategies for making sure that we're falling through。Okay， cool。

In that case， let's go ahead and remind ourselves a little bit about where we were when we left off。

 Oh， sorry， quickly， I'll remind ourselves what our topics are for today。

 So we are going to go ahead and talk again a little bit about compile time versus runtime and also a little bit about compilers versus interpreters。

 Our main task， However， today。 Very exciting。 is buoyance。

 So we are going to finish adding them to the interpreter。

 And we are also going to go ahead and add them in the compiler。 Very exciting。

 It's going to be a big change for us。😊，I wanted to quickly talk through the topics that we will touch on。

 So in our big summary of all the things that are happening。

 we're going to be talking about assembly， we're going to be talking about interpreters for compilers。

 and we are going to be talking about types。

![](img/604e5d78136eb458656cc38b4ae7cbc6_5.png)

![](img/604e5d78136eb458656cc38b4ae7cbc6_6.png)

Okay， so far， so good。Amazing， okay， so let's remind ourselves of what we were doing so。

The big thing that had changed last session was instead of always having numbers and having numbers be the only type that was actually supported in our language。

 we had decided that we were going to go ahead and have Booleions。

 And so we were going to be able to say things like。



![](img/604e5d78136eb458656cc38b4ae7cbc6_8.png)

![](img/604e5d78136eb458656cc38b4ae7cbc6_9.png)

Let's try this。Nam。5。Nan。True， right where this first one should tell us yup 5 is a number and the second one should tell us nope true is not a number。

 So that was the kind of thing we had started thinking about adding。

 and this led us to a topic that was quite interesting。

 which was the concept of statically typed versus dynamically typed languages and this was an opportunity for us to remember that when we are talking about static versus dynamic in the context of programming languages。

 This usually have very specific meetings。 So static usually means this is knowledge that we are going to have at compile time。

 and dynamic usually means this is knowledge we are not going to have at compile time。

 We will only end up being able to get it at runtime。

And so the examples that we gave of a statically typed language versus a dynamically typed language were actually the two languages that we have been playing around with ourselves。

 right， so the language in which we are writing our compiler and interpreter， O， Camel。

 is statically typed， which means that when we go ahead and look at a program。

We can just be looking at the program text， let me get rid of some of the stuff that we were playing around with since we're not fully done with that。

 this was sort of where we had left it。If we go ahead and actually hover over something， right。

 so maybe I hover over。That it's going to tell me n is an int， right， It knows the type。

 and I have not run the program， right， There is no execution of this program in process。

 It was able to tell me this information that n is an int purely by analyzing the text of the program。

 So that means it is something that we can know at compile time。😡。

Right so Ocael then is a statically typed language。 In contrast。

 the little scheme that we are implementing is a dynamically typed language。

 meaning there is no way for us to know at compile time right。

 so say that right now we have nu5 nuru as our examples here。

 But eventually we're going to have a way for the user to go ahead and give us some information at the command line。

 right， We're going to use read to refer to that。 We could have that program， and that would be fine。

 right It would be okay for us to get some information from the user。

Which plausibly could be either an inch or a bo， for example。

 And then we might want to check if what we have gotten back is a number。

 which means that at compile time， we will not know what the type is。Now。

 would it make sense for us to add something like this numb question mark operator in oh Camel， No。

 right， because presumably we would want to define it in such a way that say it can only take in numbers。

 in which case we could just replace numb question mark 5 with true every single time because we're always going to be able to know at compile time if we should be getting back true or false for this numb question mark operator。

So are there questions about this idea of static versus dynamic， static typing versus dynamic typing？

Or why it makes sense to have numb question mark in the language we're implementing， but not in Ocal。

Okay， cool， looks like so far so good。 Love that。 In that case。 I'm gonna have us go ahead。 and oh。

 I guess I'll briefly talk about sort of the design considerations because one question you might have is why would we use a statically typed language versus would we use a dynamically typed language。

 And if you get into a room with a bunch of P people， you can start a big fight around this question。

 So some people will say， oh my gosh so it's all got be about statically typed languages because catching it compile time instead run time catching the error you're going catch it before you ever even run the program。

 And maybe you're gonna run the program a million times and it only comes up on a million time。

 But now instead you're gonna catch the error at compile time And so you're gonna catch it you ever run it And we all know that there are a bunch of software engineering studies that show earlier the less sort expensive it is from a variety of different metrics for expensive。

 And so great static typing seems really good on that front But then on the other side。

 you have proponents of dynamic typing basically saying hey， you know。

 this is kind of forcing programmers to commit to。😊。

Part parts of their code only being used in particular things。 This is sort of inflexible。

 They're having to make all these decisions upfront when maybe they're not ready to make these decisions。

 Maybe you can actually make programmers more productive by using a dynamically type language。

 And it turns out that people throw all kinds of different studies at this question trying to figure out if these arguments are true。

 And in some way， they certainly seem like they have to be true， right。

 but we don't actually have very good data for how you can。

Measure this because it's just such different languages in so many different ways that you end up actually varying so many different parts of the language as you try to study。

But you can start lots of fights this way if you're interested。Okay， cool。

 I'm going to go ahead and bring us back into。Our interpreter。

And I just want to remind us real quick of what we had done last time。 So if you recall。

 the big change that we made last time was we went ahead and said， okay。

 we no longer want to have the thing that we're getting back。

Always be a number right previously when we had made the interpreter。

 we're going ahead just always giving us back an int because we only had numbers in our language。

 but now we've decided， okay， we want to be able to produce booleance。

 That's something that we are going to care about。 And so we made this new type value。 we said okay。

 a value can represent a value that has an int or it can be a value that has a pool We have these two constructors for type value。

And so what were we having to do what we were having to go through and make sure that instead of just calculating an int。

 we are calculating whatever the value should be back here。

 And so just as a quick sort of quiz for ourselves， make sure we're all on the same page。

 I'm going to ask us to look at on this line 11 here。

 I want you to go ahead and discuss with someone nearby， it's okay， if you're not sure。

 but discuss with someone nearby， what is the type of arg on line 11。All right。

 does anyone want to shout it out what is going to be the type of Arg on line 11， yell for me？

I'm hearing S expression。 I totally agree。 And so there are a couple of ways that we could know this。

 right， One is we can look at our definition of interx and see that what it takes as inputs。

 right the arguments to inter x are going to be S expressions and we can see that a is being used as an argument to inter X right And so it is。

 in fact going to be an S expression。 The other way we can know this is based on where we got it right so here we can see that we have this S expression where we use the list constructor and we know that the thing that actually。

 because remember this is a recursive type we have the list of being a list of S expressions themselves。

 and so this has to also be an S expression and this has to also be an S expression And so that's two ways that we could have known that this would be S expression。

And so now I want us to take 20 seconds to discuss with someone nearby。 Let's look at that same line。

 line 11。 And I want you to decide what is the type of inter X applied to Arg。

So Arg is part of this slightly bigger expression Inter X applied to Arg， What is the type of that？

All right， yell it out for me， what do we got？I'm hearing value and again。

 I totally agree right so that we can read off from Inter Xs definition。

 It says that it's going to take an S expression as an input。

 and then it is going to produce a value as an output is also the thing that makes sense for us based on what we are doing with that value later so we can see that we are then going ahead and checking if we created this value using the number constructor。

 which we can see as a constructor that is associated with type value And so those are a couple of the ways that we could have figured out that Inter X applied to Arg is going to be it's going to evaluate to something that has type value。

Okay， so far so good。 Or has this raised questions about what we were doing over an interpreter land。

So glad you asked， we could indeed add something for Boolean。 So there's actually， we do already。

 in fact， have something for Booleans here， right， So we have that wild card that's saying if you get any type other than number because eventually。

 of course， we're gonna have more types than just Boolean。 But yes， we are， in fact。

 going to need to know later on in this very session that we might want to actually use the Boolean as well。

😊，All right， we're feeling good so far。 We're read back in on what we were doing with our interpreter。

Lovely。 In that case， let's finish the task we had started last session， right。

 So we had just finished making sure that our add one。

 which we had actually already implemented in the past。

 was going to work now with producing something that had type value。

 Let's do the exact same thing with sub1。😊，Which is going to look really similar， right。

 We're going to go ahead and do -1 there。 But other than that。

 we're going to have something that looks really similar。

But then the real reason we started down this path was because we wanted to have booles。

 And you can see that right now， we don't actually have any booles。

 So I think there are going to be some that are going be really easy for us。

 So I'm going to have you yell out what I should do with this。Please feel free to yell。

I'm hearing Boolean true。 I totally agree， right， This is the classic case where we want to go ahead and create something of type value。

 Boolean is one of the constructors we have available for type value。

 So let's go ahead and say that if we see the symbol true as part of our S expression。

 that is going to mean that we want to have the value that that evaluates to be boole and true。

 So let's do symbol false similarly。B and false。 But now let's start playing around with some of the ones that are a little bit more complicated。

 So you may recall that we had our not that we wanted to be able to introduce。 So let's do。Sim not。

 which of course， is going to be applied to an argument。

 and then what do we actually want to do in the body of this match case？

So that's something I'm going to actually ask you to discuss with the folks nearby。

 And I'm going to remind you while you're doing that of。

What we decided should be the outputs of applying not to a couple of things。



![](img/604e5d78136eb458656cc38b4ae7cbc6_11.png)

All right， I'm going to bring us back to our interpreter。



![](img/604e5d78136eb458656cc38b4ae7cbc6_13.png)

All right， so I have a way to start that feels pretty good to me。

 What do we actually want to compare。The value that results from calling inter X on Arg。

 What do we want to compare that value against。What's the one case that should be pretty differently。

 Yeah， so what we said that the only thing that we're going to get to treat as false。

 that's going to get to behave like false is the value false itself。

 So let's go ahead and compare against Boolean false。And if we got Boolean falls， then。

Not of Boolean pulse is going to be boolean true。 And that's the only thing that gets to produce Boolean true。

 everything else。Should be bulloley and false。Did I misspell？Thank you very much。Okay。

 so there we go， we've got not。Beside that。Anything else should？Pause。Could be like。Great question。

 Yeah， so why did we decide that everything else should behave like true， Like。

 why is that a good thing to do， It's not necessarily a good thing to do， right。

 Like we could make arguments all day of whether that's a good thing to do。

 It is what Lisp does and we are implementing our sort of teeny， tiny little dialect of list。

 And so we are sort of matching what that does。 But yeah。

 we could absolutely have made the call that you should only be applying this when you are confident that the thing you're getting through is going to be a boolean。

 That would be totally fine。Yeah。Yeah， definitely。Alright， okay。

 so we have another case that is going to look relatively similar。

 So you may recall that we have our 0。And we're going to have to compare against something different。

 So we're going to want to compare against。Number 0。 we had my spelling today。 number 0。

 But other than that， the structure is looking pretty similar。

 And then we have one last one that's going be slightly， slightly complicated to introduce。

 So I'm going ask you to start brainstorming with folks nearby。

 You may remember that we had that number question mark。

 That was sort of one of the ones that started us thinking about statically typed versus dynamically typed。

 So I want you to start thinking with folks nearby and just brainstorming。

 How might we go ahead and implement this case in the interpreter for number question mark。

So I'm hearing some keywords I like， I'm hearing that people would like to call interp Xon R。

We're going to have to do some other stuff， but I think that's a solid start。Okay。

 and I'm hearing the other big keyword that I wanted to hear， which is match。

 We can go ahead and match and figure out， okay， what was the constructor that was actually used to make this。

 right， Let's go ahead， oops， sorry， that should be with。Let's go ahead and see， well。

 was it a number constructor number， we don't actually care what the number was。

 We can throw away whatever the actual number was， but then we want to produce Boolean true versus was it anything else。

Then we're going to go ahead and have Boolean false。Okay。

 we have now almost finished adding our yes question。Yes， love it。Oh， great question。 Yeah， Why。

 if instead of match。 So basically， it's just that we didn't need the full power of match， right。

 Mat is very powerful。 We can use it to do things like control flow the way we would use an if expression。

 We can also use it to do all kinds of naming and sort of decomposition of our inputs。

 We didn't need the full power of match。 And so we chose to just use the simpler construct。

 which is if。 But yeah。😊，They could totally have done it with match。 Yeah， programmer choice。

Question。Okay， great。 We are super， super close to having now implemented the Booles and the boolean operators。

 we were excited to add in our interpreter。 What is missing。 Well。

 O Caml is going to tell us exactly what is missing。 It says， hang on。

 you said you were gonna give me an inch。 That's the only way I know to produce a string for this。

 You're gonna have to give me something else to do here。

 If I'm not going be just getting ints out because remember， we're now getting values out。 So let's。

 let's go ahead and real quick。 Just give it the function。

 a helper function that it is going to need。 So here we go。😊。

Let string of value right instead of string of int， we'll have it take value as input。

We'll have a string coming out the other side。 And what do we actually want to do with it Well。

 let's do our classic。Number N there we can just still use string event。String event。Apply that to N。

 If we're in some other situation， Boolean。Bei。Then， if B。Then true。Else false。

 So now we know exactly how to print out the various values we might have represented our interpreter。

 And so instead of saying string of in， let's just say string of value。And let's see what happens。

 So let's go ahead。You插。What do we do， let's do not true。Let's do not false。Was to not。3。Okay。

 looks like we're getting basically what we would expect。 So it's very exciting。

 We now have multiple types available in our interpreter。

 We're starting to have something that looks like a real language。

 but here's something that we don't have yet。 right， So let's go ahead。😊，Open。

And let's do compile and run that exact same program。So I know this is kind of silly， right。

 Of course， we don't have that in our compiler。 We have not implemented that in our compiler。

 but I'm just doing this to remind ourselves trying to really like keep it top of mind whether we are implementing something in our interpreter。

 interpret M， the place where we are producing values。

 We are just going ahead and executing that program and figuring out what is the value associated with executing that program versus compiled M。

 where our role is something different， instead we are going ahead and actually producing assembly。

 that when it is run， when that assembly is run， that will produce the value This is just a reminder that our compiler interpreter are doing different things。

 And even though it's very helpful for us to build things in the interpreter in order to figure out what are we even trying to do with this construct。

 work through some of those ideas， it is not the same It's actually implementing it in the compile。😊。

Questions about that。Great， in that case， I'm going to bring us back to an exercise that we saw very。

 very briefly on our last session。😊，Where we decide which of these three situations we are in for our interpreter and our compiler。

 it's okay if you don't know， but go ahead and just chat with someone nearby for 20 seconds and then we'll hum。

All right， let's hunt if we think we're in situation A。Let's hum if we think we're in situation B。

Let's hum if we think we're in situation C。Yeah， I agree right our interpreter is not there as a building block inside our compiler。

 our compiler is not there as a building block inside our interpreter。

 we just have these two separate files compiledMl and interpretML。

 two separate OCMl programs that are our separate compiler and interpreter for scheme right so here we go。

 we've got our compiler， it's just this OCMl program we have our interpreter。

 it's just this OCMl program。They are not actually tied together。

Even though we're reasoning them about them together。Okay， cool。 So I know it's wacky。

 It's weird thinking about the difference between compiler and interpreter。

 If you're struggling to wrap your head around those ideas。

 I believe this coming section is going to focus on this。 Check with the Ts for sure。

Is there a question over there。 No， we're good。 Okay， yeah， stretching good。 Okay。

 let's go ahead and talk through then what it's gonna take to make those Booleans available in compiler land。

 So we've done it for the interpreter。 right， we've got them。

 but we don't yet have them in our compiler。 So the big thing that we changed when we were updating the interpreter was we added this type value and we changed what we return the type of the thing that we return when we run interpret X So if we think about okay。

 sort of the parallel structure between compiler and interpreter。

 we might look over here at compiler X and say， okay。

 maybe I want to make something that's sort of that same type。

 and maybe I then want to change the output of compile X to have type value。

So I want you to discuss for 30 seconds with folks nearby is that what we should do。

 should we be changing the output type for compile X。It's okay if you don't know the answer。

 we're just trying to think it through。All right， so hum， if we should change that output type。

H if we should not change that output type？Yeah， I agree， right。

 So the role of our compiler is to produce a bunch of assembly instructions。

And then it is the role of those assembly instructions to actually figure out the value associated with executing the program。

 So our compiler is doing something different。 We're not getting the value out of the compiler。

 instead， we are getting out another representation of the program right this list of assembly instructions and we can then later pass to the processor and the processor can tell you what value is associated with them。

 So we do have this related goal right like we know that we're trying to make sure that the directions。

 the directives， the assembly instructions that would pop out the other side of a call to compile X。

 we want to make sure that when those are executed。

 they will put the value associated with that program inside RX。

 right So we're still thinking about that same target output value。

 but instead we're thinking about generating the assembly instructions that are going to make sure that that value ends up inside our register RAX。

that is the role of Comp X， we have to have thought out what are the assembly instructions that could put that value inside REX。

Now that might bring up another question for you， right which is， okay。

 putting a number inside that register RX seems to have made sense， right。

 we have these representations of numbers， we know how to convert from the representations that you and I normally write on the whiteboard versus the one that sort of represents the exact same information。

 but as a binary number presumably you know the register RAX is just this 64 bit slot right。

 64 slots where you can put either zero or one in it。

 and so what has actually been happening when we put a number in that is just the binary representation of that number got popped into those 64 slots where we can put one or0。

But now I'm saying that， hey， we've got to put the value associated with executing this program inside that register。

How do we do that if it's not a number anymore， right？

 I'm about to ask us to put Boolean true inside that 64 B slot。

 So I want you to discuss with folks nearby。 How can we put a boolean in there。

We're just brainstorming。All right， what ideas do we have yell out？Its weird， right， Like。

 what should we do， It's not actually clear。 We're gonna to have to start making some design decisions。

 So to start talking through the particular design decision that we have made for this course compiler。

 I'm going to start by sort of explaining what the computer has been seeing this entire time， right。

 So let's talk about 0 and1。 So when we talked about putting a value inside R X。

 Here's what was actually happening， right， So we had 0，0， do do do 00，64 of those， right。

 And that's what represented this value 0。Likewise， for one， we had， oh， sorry。

 let me first clarify that when I do a0 B there， that's indicating that I'm about to write something in binary。

And so let's do the same thing。 but for one， so 0，0 dot dot dot except 01。

 And so this time we have 63 zeros right， and again， we're indicating that we're writing in binary。

 So this is what the computer has been seeing the entire time right That's what was actually inside RAX。

So with this in mind， just another 20 seconds of brainstorming。 what could we do。

 How could we put a boolean in there instead。So here's what we are going to choose to do， right。

 Like previously， every way that we could have filled those 64 slots with ones and zeros represented a particular number。

 right， that makes it really hard to then represent true and false as well。

 we could try to do something like C where we actually use zero to mean false and one to mean true。

 but we've already decided that we want to have that nu construct。

 And so we're going to want to actually be able to figure out， is this thing a number or a boolean。

 if we go ahead and use one of these numbers to represent booleions as well。

 We're not going to be able to answer that question， right。

 We're not going be able to look at0 and say， is that false or is that zero。

 And so we're going to have to go ahead and actually change how we're representing numbers because now some ways of arranging those 64 bits had better represent numbers and some had better represent something else。

 And so we are actually going to reduce the number of bits we can use or represent numbers。

 We suddenly have these shorter integers available。

 We're going to be able to represent as many integers。

But it is going to mean that there is a way for us to go ahead and put other things in a register。

 represent other things in a register other than just numbers。

 And so the particular thing that we are going to be doing is going ahead and saying anything that ends with 0。

0， right， So 0，0 in these last spots is going to be。A number。 I know this is a little bit weird。

 Like， why are we picking specifically 0，0， Why are we picking specifically this 2 B tag， right。

 There's some weirdness going on。 I promise we'll have an activity on Thursday that' wrestling with why this specific tag。

But the thing that we want to be thinking about now is how many values， right。

 64 bit values do we now have available to us to use for representing things other than numbers。

So out of the full space of 64 bit values that we have available。

 what portion of those are now used for numbers versus what portion can we now use for something else。

 Disc with a friend。All right， so anyone want to yell it out， no pressure。

How many are we using for numbers now？What portion are we using for numbers now？I love it。 Okay。

 great。 So， yes。 So we now have 62 B available for representing numbers， right？

 And so we know that the number of things that we can represent using 62 B is2 to the power of 62。

 And so if we think about it， this makes total sense， right。

 Because there are four different ways that we could end these 64 B values。 And now。😊。

All of those ones are being used to represent numbers and the other three quarters of our our various allowable representations of bits are going to be used to represent something else。

 something that does not have type number。So far， so good。A little bit wacky。

 but we'll work through it。Amazing， okay， so let's start actually doing this。 right。

 We're not actually going to put Booleions in yet， but we're just going to make this change to how we represent numbers at runtime。

 So let's go ahead and swap over。😊，To our compiler and start making this change。

So first things first， let's make sure that we actually have access to the sort of special values that we've decided we're going to need。

 which is。Let numb shift。Two， right， we're going to want to go ahead and make sure that we can shift things to。

 You can see that right。 Yeah， okay， good。And we want to go ahead and have a mask and a mask。

 which is going to be。One，1。Just like in when we're writing in sort of the usual ways that we're used to。

 we don't have to write 0，0，0，0，0，3，45 in order to mean 3 45。 We can just write 3，45。

 We're going be doing the exact same thing with binary， right。

 So this means that there's a bunch of zeros in front of this， but we don't have to put the zeros in。

So there we go， that's our mask that's just going mask off those last two bits and we'll see in a moment how we'll use that and then let nu tag right so the actual thing that we'll expect to see in those last two bits is going to be zero and zero and so these are the piece of information we will need to know in order to represent numbers and I'll show you exactly how we're going to use it so over here we have the thing that is actually putting a number in a register。

 let's go ahead and use this information to put the correct representation。Please。Great question。

 So let's talk about how we are actually going to use this mask。 So this question was。

 why is this the right mask for us And basically， we are going to use this mask in order to check if something that we are looking at is。

 in fact， a number， right， So say that we have something like， I don't know。Oh。0，1，0， right。

 if we go ahead and mask off just this， right， we're gonna be able to see that 10 comes out the other side。

 Whereas if we have something that is， in fact， a number， right， 0，0。

 and we mask off just that we get 0，0 out。 We're gonna to be able to see that yep。

 that has the number tag， Where this does not have the number tag。

 So that's why the thing that we're masking out is just this last two bits。Makes sense。C， awesome。

 Okay， yeah， I know it's not clear yet。 how we're actually using the the tag。 So we'll。

 we'll see that in just a second。 So let's go ahead and use this information。

 So let's do left shift left。 This is， sorry， logical shift left。

 This is O camel's implementation of logical shift left。 And let's do numb shift。😊，Okay。

 that is how we're going to use this。 Now， what I want you to discuss with folks nearby for one moment is is this going to be enough。

To make our new representation done， like are we finished changing how we represent numbers in this language。

Discuss with folks nearby for a minute。 And again， it's totally fine to not know the answer。

 We're just trying to brainstorm。哇哦。So what's going on。

 why are we getting this wacky number 17 when we now try to run add14？Well。

 you may recall that shifting left by two is the same as multiplying by4。

 and so we have changed part of our compiler to reckon with that。

 right So this is going ahead and doing the appropriate shift on4。

 giving us our runtime representation of4， which is to say the value 16 right。

 and then we are adding just normal one to it。Okay， so that's probably not feeling so good。

 Let's go ahead and do something that's basically the equivalent here with one。

 We could just straight up， put 4 in here， but we want to sort of represent what we're thinking。

 So we won't just replace it with4。 Let's instead replace it with one。For which we have done our。

 our bitwise shift left， let's do。The same thing here。

 So now things are starting to look a little closer。

 We are shifting all of the things that we might be adding or subtracting。 Let's try this again。Well。

 oh， still not right， right？ So what's going on。 Why is this not working， Well， let's go to our。

 our slides for a moment and think about this program。 right。

 So what's actually happening inside here is add one。4， right？

 So we've got our internal representation of4， which is to say 16。

 We've got our internal representation of one， which is to say 4， and then we are， in fact。

 adding them and producing 20。 So in some sense， we are doing the right thing。

 the problem is that what we actually want out of here isn't just straight up 20。

 we want to have converted out of our runtime representation back to the actual number that it represents for us。

 which is to say5 right， which means we should actually do divide by 4 at this point。

 So what is it that's failing to do divide by 4。 Well， if y all remember。

 way back when we had our runtime。And all it's doing is just popping out whatever it gets back。

 It says， okay， whatever you put inside R X， that's what we want。

 But now that's not quite what we want anymore because we put something inside R X that is using our particular runtime representation。

 And it's not actually what we want to print out to the user。

 So let's think about how to actually change this so that we can get everything to be on the same page。

 So first， let's look again at our compiler。 Let's copy this back over。And。

Let's start putting this in here。 Tell you what。 Go ahead and take your five minute break right now。

 I know we're getting close to the end of class。 I will go ahead and start doing some things that are manipulating this runtime。

 but I promise to talk us through them after your break。 See you in five minutes。

Everyone weren't so quiet today。Re tiredired。end of day。还有这个。Alright。

 so we can see I've made a couple changes to our compiler， but only very minimal so far。

 So this is the only stuff that has changed right so I introduced that same numb shift numb mask numb tag that we saw already in the compiler right we saw those。

 I copied that over to here。 and then I've started the skeleton of something called print value right because previously we've only printed numbers and now we're going to start wanting to do something different based on whether we're getting back in number。

So okay， what do we want to do in the case of a number。

 basically the same thing we've been doing before， except that instead of left shifting the way we did in order to create that runtime representation。

 we are now going to write shift in order to get back out of the runtime representation back to the number that we actually want to show to the user。

So we want to go ahead and do our right shift， but other than that。

Everything is basically the same as back over here， right？Now， the question is。

 what do I need to do in order to figure out if this even is a number that I'm trying to print。

 right， I've been handed just whatever is inside R A X。Is it a number， I don't know。

 So I want you to brainstorm with someone nearby about a minute。

 How are we going to figure out if the the sort of 64 bits we've been handled， Is that a number。

 What should we put in this。Wine。Allright， here's what I was hearing from the audience right which is basically exactly the thing we just did on the whiteboard when we got that very prescient question of what should we actually have as our numb mask。

 right So we're just gonna to go ahead and bitwise and with our numb mask。

 which is basically going to say let's go ahead and blank out everything。 except those last two bits。

 go ahead and ignore anything that's happening the whole rest of the 64 Bs。

 I'm only interested in those last two bits And then it's going to say is that whatever we've got in those last two bits matched with what we have in the numb tag。

 which is say00 And so only if we have sort of zeroed out everything and we still have only zeros in those last two bits。

 are we going to go ahead and actually find yep， we should go down this path we know to treat this as a number。

 So this is really just sort of the fancy C way of saying the last two bits or zeros。😊。

Do we have questions about that？Feeling pretty good。Great。

 so this is now what we are actually going to use in order to print our values。

 So instead of doing all of these shenanigans that we were doing before。

 let's do print value applied to entry。 And so now let's go ahead。😊，Recompile our runtime。

What did I do wrong， Did I get it bad。Print F Segan。Comma， thank you so much。Nope， what I do。

Printter。No， that。com was correct there， we want that。I don't think we want a comma there。Let's see。

Myや。我也上班。Oh did I get my prayers wrong？All right， surprise。

 you get an extra one minute break while I debug what's going on here。Oh， I missed a little lie。

 Oh my gosh， okay， okay。Man， oh man。 Okay， allright， we've got it， we've got to compile。 Like。

 sorry about that。 That's my bad。 That's my bad typing。 Okay。

 so this is doing what we actually wanted to be doing。 Let's go ahead and get back into Utah。

And let's see。 we want to go ahead and compile and run that same thing。 And this time。

 we are getting back what we wanted， right， so now we've got five coming out again instead of 20。

 which was just showing us the runtime representation。以此类。I think this question is about。

 is it always going to be okay to operate on multiples of 4 and then later divide by 4。

 And the answer is yes。 So that's actually exactly why we used 0，0 as the tag here instead of like 0。

1。 right， If we had 0，1 as the tag。 all of a sudden， eventually。

 we start getting those ones propagating up and changing our values。 If we're using 0，0 at the end。

 then we're just always operating on multiples of 4 and any of the operations that we're going to do are going to work。

 and we just have to divide by 4 at the end。 So that's exactly why we chose 0，0 as the tag there。

Yeah， great question。Great question。Also， another thing we're actually not going to talk about。

 but it does actually work for negative numbers。 So the same thing sort of applies there that we get to just keep doing all normal operations dividing by four。

 It's going to work out。 We're not going really play around with that， but it's fine。Okay， cool。

 We are gonna also have an activity next session where we're reasoning about why would we pick specific tags。

 And that's something we'll be thinking about。Okay。

 so I'm going quickly talk us through the the kind of assembly that we are actually generating for this kind of program。

 just to sort of really try to make it concrete。 what I mean when I say runtime representation。

 So what is happening is now if we look at the assembly that we have created。

 it is no longer operating on sort of the original values that we saw in the program text。

 So when we take a look at this program， this for corresponds to this 16。 And if we look at。

 let me change the color real quick， this one corresponds to that。 and we can change the color again。

This one corresponds to that， right， So now we are just going ahead and only manipulating this runtime representation of numbers instead of our original。

 And so if we look at what happens when we go ahead and actually run the assembly。 Well。

 the first thing we're going to do is go ahead and put。Binary number。

 this time I'm actually going to write it out， right，1，2，3，4。 That's our representation of 16。

 just to say run time。Val of four， right， That's what we put in R X in order to do that first instruction。

And then at the end of that， we go ahead and say， okay， while we're doing the next instruction。

 let's cross out what we had before。 Let's put in O B1，0，0，1， Oh， did I get that wrong。 Yep。

 I got that wrong， sorry。Let's put that in the right spot。1，0，0， great。

 We've gone ahead and gotten our representation for 20， which is say run time。Bo of5。

And then we can go ahead and cross that all out and put in OB1。1，1，2，3。

 which is to say our representation of 24 or runtime rep of 6。

 which is the answer that we actually want to get out of this。

 And then when we go ahead and hand back control， right because remember that last thing。

 the thing that happens on that very last line is we return control to our runtime。

 The thing that actually called entry， that's the thing that actually goes ahead and actually divides that by four in order to get that our answer is going to be 6。

We feeling pretty comfortable with the fact that we are now generating instructions that use this other alternative representation of numbers。

In that case， let's start moving towards adding booleans in。 okay so here we go。

 we've decided how we're actually gonna represent numbers。

 The whole reason we did all of this was so that we can go ahead and actually add in Booleans as well。

 So I'm going to write out how we're gonna represent booleans。

 I know it's gonna to be a little frustrating them are're going to tell you a tag that we are going use for booleans right So remember。

 we now have three quarters of our 64 bit things， three quarters of those available to represent things other than booleans。

 we are gonna only need two of those things in order to represent true and false。

 And so we're gonna have a really long tag because we don't want to use up a bunch of the other sort of tag spaces that we could be using。

 So let's go ahead and have true be represented with one followed by our special tag 0，0，1，2，3451s。

 And then we'll have false be the same thing but with0 followed by two0s and then1，23451s。

 And so those are going be our runtime representations of the value true and false。

 What what's the first。we're going to need to change is going to be our runtime。

 We just saw that we have to do something special in order to support new representations in our runtime。



![](img/604e5d78136eb458656cc38b4ae7cbc6_15.png)

![](img/604e5d78136eb458656cc38b4ae7cbc6_16.png)

So let's go ahead and do something that's actually pretty similar to what we just did。 right。

 We're gonna go ahead and use。The same kind of style。

 But we're going to specialize for Booles instead。 So we'll have pool shift， pool mask。Bull tag。 Now。

 I said that we were going to do2 ones followed by5， sorry20s， followed by51s。

 And so that's gonna to have length 7。 Our mask is just going be 1，2，3，4，5，6，7，7，1s。

 And then our tag is going to be 2，0s followed by 1，2，3，4，51s。

 So this is the stuff that I just sort of showed。 And all that's going to change between true and false is true is going to be one followed by this tag and false is going to be0。

 followed by this tag。So that's going to be pretty simple for us to add into print value。

 So let's go ahead and do that。 I'm going to ask you to chat with someone nearby。

 What should go in the。Else if here， I'll start filling in the inerts。

 but I'm going to want you to start talking about what should go here。Yeah。

 so the thing that determines the mask and the shift is the tag right。

 So once we know what the tag is， we also know automatically what the shift and the mask are going to be。

 So we have this seven B tag that we're going to put at the end ofbuoleance。Right。

 we decided that it's going to be two zeros followed by five ones。

 that's going to be the tag we're going to use to mean this thing is a boolean。

 Once we know that we know that we're going to want to mask off all seven of those bits and we know that the thing to shift by when we're saying。

 okay， I want to put one in front of this tag or I want to put0 in front of this tag is going to be7 bits so we're going to want to do this seven bit shift that we see right here in order to get back to 001。

Yeah， so once we have sort of this piece of information， what is the Boolean tag。

 we can go ahead and automatically write down what is the mask。

 What is the shift based on that information。Okay。So what do we think about the idea of doing something really pretty similar？

To what we did here， does that feel okay to us。Home for， yeah。Hum for no。Okay， great。

 We've recognized the parallel structure。 And I totally agree， right。

 This is the exact same thing that we're doing here。 We're basically gonna go ahead and just。

Mask things off with the Boolean mask instead of the number mask。

 And then we're going to compare to the Boolean tag instead of the number tag。

 So we're just doing that exact same process of saying I only care about those last X bits for the number case。

 it was those last two bits for this case， it's those7 bits。

 So I only care about those last seven Bs。 And I want to see if those bits matched the bits that are associated with our boolean tag。

 So has this value previously been tagged with our boolean tag。

 And so then we have everything set up in the runtime and we should be good to go on the runtime。

 Let's make sure we can actually compile the same da。 I do forget my semicolonons。

 Let's put those in。Okay， great。 So this time I think we got it the more or less the first try。

 So now let's go ahead and actually make those available from our compiler， right。

 so we haven't actually tagged anything with that Boolean tag yet。

 We probably want to go ahead and do that。 So let's go ahead into our compiler and start making some。

 oh， actually， before we do that。 You know what， I want to make sure that our runtime is letting us know about cases where things go really。

 really badly。 So let's add in one more case here before we move over to compiler land。😊，So what？

We end up getting a value inside REX， our register RAX that doesn't have either of these tags。

 What does that mean？Chat with folks nearby for a moment。

So I think we've probably got some ideam from the chatter。

 It sounds like we've got some idea that it would be something that we don't want to happen。

 but in fact， it's something sort of worse than our usual errors that we would show to our developers。

 right？Normally if we're showing an error to the developer， it's because they。

 the programmer who's writing something in our language， did something wrong。

If we see a value inside RX that does not have a tag associated with one of the types weve created。

 we， the compiler developers， have done something wrong。 So this is a really。

 really bad error for us to ever see right if we get this happening， something has gone very。

 very wrong。 we should not land in the situation where we're seeing a value inside RX that we're asking the runtime to interpret that isn't actually tagged with any of the things that knows how to handle。

 That would only happen if we， when we are creating the assembly have created assembly that does something pretty bad right。

 So we really don't want to see that coming up。So far so good on that concept。Cool， yeah。

 we should only have values that actually represent real values in our language。 So now， oops， sorry。

 did I go ahead and actually compile that， I think I did。Yeah， compiled great。

 So now let's turn to our compiler。And let's actually make use of the fact that we can now handle that。

 So we're going to do something pretty similar to what we've done before。 But this time。

 we're going to do it for booles。 So again， let's do bull shift。Full mask。Bol tag。 And this time。

 we want 7。We want 1，2，3，4，5，6，7。 I think that was the right number，1，2，3，4，5。 Okay。

 so now real quick exercise for us， this that I have typed here matches with what I have in the runtime。

 right， These look the same。 We've got 0，0，12 3，4，5 once。 What if I mistype and I do this。

 What's gonna happen。Good things。 Homem for good things。Home for bad things。Yeah， right， suddenlyly。

 we don't know how to treat it。 We're going end up going down that bad path， right。

 That is one of the ways that we could create a situation where we go down this bad value。

 extremelyme bad。 Don't do this path， right， is if we go ahead and just sort of go ahead and and add the wrong tag just directly。

We could end up with other ways that we could create that， but that's one of the ways。Okay， great。

 So now we're gonna want to do something that's actually honestly pretty similar to this case， right。

 So let's just start from that case and then let's see what changes。 So let's do true， false。 Sorry。

 true first。So let's do Sim true， right？ Okay， so this is not actually what we want to do。

 We want to do something a little bit different， but we do want to put something bless you inside RX。

 and it is going to be an immediate。 So what is the immediate that I want to put inside And here I'll ask you to brainstorm with folks nearby。

 What is the immediate that we should put inside REX。 if we have seen the value true in our program。

Just our quick reminder of how we decided to represent。



![](img/604e5d78136eb458656cc38b4ae7cbc6_18.png)

![](img/604e5d78136eb458656cc38b4ae7cbc6_19.png)

Alright， so it seems like true in some way is associated with one。

 It seems like we're doing something that has to do with one。 So let's go ahead and put that in。

 So we're gonna want to go ahead and do our logical shift left again， right。

 we still want to do that。 but not by the numb shift this time。 Let's do bull shift right。

 because we have to believe space for the entire Boolean tag。 So we had better go7 spots to the left。

 And then right before we didn't bother to actually tag it with the number tag because we knew that the number tag was zeros。

 This time， we're gonna have to tag it with the boolean tag because it's not just zeros， right。

 our shifting was just leaving zeros in that spot。 Now， when we're doing our shifting。

 we're leaving zeros in that spot， which is gonna make it look like a number。

 which is very bad for us。 So instead， let's go ahead and make sure that we are being very clear that we should logical or this with our bo tag。

And then we will have the value that we actually want to have in there。

 We're just going to go ahead and basically add that tag at the end。 this is our way of doing that。

So let's do the exact same thing， but with zero to represent falses。Ohoops。안点。

Let's do false and let's do this with。0。And let's get rid of that weird thing， great。

So now let's see what happens when we go ahead and try using true and false。 So let's do。Nice。

 we've got true。Nice， we've got false。And now this is a little bit weird right。

 because if we've gone into the runtime instead of putting true and false here。

 we'd put unicorn and Bob。 we've gotten unicorn and Bob out the other end， right。

 So like this is the thing that's actually controlling what we see when we run those programs。

 that's totally fine， right， That's all right。O。So this is how we're implementing it。

 and I want to first ask if you all have questions and then if you don't have questions。

 I have questions for you。Great question。 So this is the observation that we can suddenly represent fewer integers than we used to be able to represent。

 We just have 64 bits to represent integers。 And now we only have 62。

 That means that for large integers， it doesn't match anymore with our interpreter。😊。

This is an amazing， amazing observation。 So if we cared about behavior at these know very high integer numbers。

 if we cared about specific features of overflow， absolutely。

 we would now be changing how the interpreter is working to make sure that it matched on every aspect。

 In fact， something that's a little bit weird about the situation where we are using Ocael to write our interpreter is Ocaml integers actually only have 63 bits available。

 So we actually know if we sort of know the compiler implementation for Ocael that we actually have already not had 64 bits available to us in the interpreter land。

 It's actually not using that one bit for type tagging the way we are doing。

 It's using it for something that we'll get to later in the semester called garbage collection。

 So we'll get to that later。 But so yeah， if we look at these high integer values。

 we are going to see diverging behavior。 And if we were going to be really carefully checking to make sure that overflow behavior was going to be exactly the same on both absolutely。

 we would have to now change our interpreter。😊，We're not super interested in that。

 It's all kind of mechanical。 Actually， I thought about having a homework where you all did big numb。

 And that would have been sort of a way to play around with some of those ideas a little bit。

 But I couldn't figure out where to fit in the schedule。But there is some fun stuff to do in this。

Yes。😊，Great question。 So why are we using 7 Bs to represent Booleans instead of two or3 to represent that Boolean tag。

 Hol that question for this next session， because we're gonna to do basically an activity in class where we're just wrestling with。

 why would we make particular choices about tags。 And what kinds of things Are we sort of trading off when we do that。

 This is not like a deep compilers topic of why would we pick particular tags。

 And so I don't want us to spend too much time on it。

 But it is a nice way for us to start thinking about this idea that the decisions we making as。

 we're building these implementations actually have ramifications for then how we can implement other parts of our our programming language implementation。

 And so we are starting to think about how these design decisions sort of interact。

 So that's the main thing we'll be thinking about there。 Great question。😊，Yeahや。Yes， great question。

 For now。 We have just arbitrarily chosen。 Well， we chose zeros as the。

 the ending tag for numbers specifically so that we could still do that sort of thing of addition。

 multiplication， whatever sort of treating everything as multiples of floor。

 and then dividing by4 in the end。 so that that would all play nicely。 But other than that， Yes。

 for now， we are just imagining that the tags are chosen arbitrarily。

 And we're gonna play around with it in an activity next session。😊，Okay。

 so we now have one last minute for me to ask a question to you。

 And the question I'm going to ask to you is this left shift that's happening right here。

 Is that happening at compile time or runtime， discuss for 30 seconds。So Kate， if you don't know。

Think through with the folks nearby。All right， we're coming right up against the time limit。

 so I'm going to go ahead and ask you hum if you think that is happening at compile time。

If you think that is happening at runtime？Okay， cool。 Yeah， I agree。

 That is happening at compile time。 And we can know that that is happening at compile time because it the Oca's implementation that is doing the running。

 right， And O Camel is running at compile time。 If we had instead emitted an assembly instruction that was gonna do the logical shift left。

 then that would be something that was gonna be actually happening at runtime。

 But we know that this is gonna produce the same answer every single time。

 So we don't have to actually leave it till runtime。 We could admit the assembly to do that。

 We don't need to do that。 We can go ahead and just calculate it once that compile time and fake it。

 All right， thank you， everybody。 have a great rest of your Tuesday。😊。



![](img/604e5d78136eb458656cc38b4ae7cbc6_21.png)

Thank you。Hello， of course。BecauseAbsol， yeah。

![](img/604e5d78136eb458656cc38b4ae7cbc6_23.png)

Thanks， have a good one。So what I thought about。