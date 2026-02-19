# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P3：-03-3. Induction and Recursion _ - GPT中英字幕课程资源 - BV12VChY2EF4

Cool， okay， I guess we'll get started then we're running four minutes behind schedule。

 but that's how how that's how it goes when you're live welcomel to class。

 welcome in Today we'll be talking about induction and recursion， but prior to that。

 I want to show you something because I've got this， whoops， not that one， whoops， whoops。

 not that one。We've got the house points list right now Blue teamam is in the lead with 30 points and then we've got yellow and I love Brandon at 10 so if you're not blue team you're losing you have the opportunity to make it up in today's house quiz so just letting you know that's coming up All right we will be taking a quiz later in fact you're probably gonna to move spots because you're probably not seated in the right arrangement right now。

Okay， but any burning questions prior to us getting started with this lecture here。

 basics homework is you tonight。 That's something you have to do。 Please do that。

 In addition on Piazza， there is a note I published about。😊。



![](img/8c8904319d292851c0f31f5c3c3501b0_1.png)

Your grading schemes because you need to do that so remember I was saying that you select your own grading scheme for this semester there's a piazza note it's at 34 there's a handy formula here but you need to fill out Currently I have 41 people filling it out and there's like 60 people in the class so if you have not filled it out please do and if you've not filled it out and you're not in this room。

We have another problem。 but hopefully， if you're watching this later on you， you get that cool。

 Okay， so I assume that we're all good to go。 today， we're talking about induction and recursion。

 Now， I hope that everyone here knows what both of those two components are individually。 And if not。

 we have a problem because concepts was a prere as well as， I guess。😊。



![](img/8c8904319d292851c0f31f5c3c3501b0_3.png)

Knowing how to program。 But， but we're gonna put the dual two together because induction is great and incurion is great。

 but we're gonna put them together， so。😊，Or like for today。

 we're going to talk about recursion and induction independently。

 We're going to talk about proving correctness because why programmatic thinking is mathematical thinking。

 We want to produce code that doesn't just isn't just written that we know works。

 We're in the business of producing correct code， and this will not be the first time I say this you this semester。

😊，I'll show you some more language features in SML。

 and then we'll do a case study on fast exponiation。

 which is a way of implementing exponiation but fast。Okay， so let's go ahead with that。

 So last lecture。 Remember that was Thursday。 It was so long ago。

 you had a whole weekend to do fun things。 But remember that we learned about some new types。 right。

 we learned about tuples， we learned about function types。

 All these are pretty cool things that we can use in SML。 and we also talked about variable binding。

 We talked about how we can bind a variable and that changes our environment and how that's different than assignment Because something like to actually hazard guess why is binding different than assignment。

 What is one way。😊，我 thankか。Yeah。We can't change it， we can only shadow it， absolutely。

One one feedback I got from last lecture was more high choose， so I'm trying my best。

 We also learned how we can prove stuff。 We learned about extensional equivals。

 which gave us the property of referential transparency equals for equals。

 I can refactor my code for free and we fixed some poor fruit trees intern for some poor fruit tree interns code using this technique Okay we'll see more of that today Allright。

😊，But actually knew stuff， there was some stuff I didn't cover last lecture that I wanted to get to。

 but we didn't have time。 So now I gotta talk about it now。 So this is part zero equivalence。

So I mentioned to you that in the first lecture， a value is a kind of final answer。

 When I have a value， I just have a value。 I can't simplify。 I just have the value。

And that makes sense for things that are like two， for things that are like the bully and true。

 But what about functions， How do I simplify a function？ It's not necessarily clear。

 A question might be like， if I have something like F N X comma int。



![](img/8c8904319d292851c0f31f5c3c3501b0_5.png)

Goes to x plus X。Can I simplify this or better yet， actually， let's make it。We，2 plus2。

Can I simplify this function value， this， this lambda， Well maybe not necessarily value。

 but can I simplify it， And I'm going to tell you the answer is， no。



![](img/8c8904319d292851c0f31f5c3c3501b0_7.png)

The answer is no， because of a property。 but this is called a suspension。

 This we'll talk about this more。 It's not super important to know now。

 But the basic idea I'm trying to tell you is that any lambda expression。

 any lambda expression doesn't matter what's inside。 It must be a value。 It always is a value。

 This 2 plus2。Never happens。It never happens until I get the input argument。

 So when I give it this X， then we do the  two plus 2。 Okay， this is kind of a side note。

 but I just wanted you to know that。 So basically， functions are values。

 But something else we want to say about values is that it should be obvious when they're equal。

 So like we know that two is extensionally equivalent to2， that's very clear， right？

 And we know that you know， one comma 2 is extensionly equivalent to one comma 2。

 and that's very obvious， But what about when it's less obvious。

 How do we talk about the extensional equivalentence of functions。

 What does it mean for two functions to be extensionally equivalent so。For instance。

 I have there up there。 I take an a lambda or I have a lambda that takes an X and then adds it to itself。

 and I have a lambda that takes an x and then multiplies it by two。

 Now these should be the same thing， right， But can we say that these two functions are extensionly equivalent。

 And it turns out that we can， because our definition of extension equivalentence is different for functions。

 So we say that if I have a function， two functions， f and G， theyre from of types T1 to T2。

 I say that they are extensionly equivalent。 if for all values that they could take as input for all inputs。

 they are extensionally equivalent。 So the question is then suppose I went back to that thing I just told you。

😊，These two functions。Is it the case that for every possible。Value I give。

 I should get the same value back。 At least I should get extensionly equivalent values back for these two functions here。

What do you think。I'm seeing some nods。 So， yes， that is， in fact true。 Okay， remember， there is no。

 there's no like random gles about arithmetic。 There's no gles about like how it's implemented。

 math is math。 X plus X is always the same as two times X。 So， yes， we have this equivalent。

 therefore。😊，These two things are extensionly equivalent。

 that's our rule for equivalentence of functions， functionss are equivalent when they behave equivalently is another way of thinking about it。

 we reason about functions for how they behave， we reason about values for what they are okay that's kind of one way to think about it。

Okay， and another thing， as I said in this definition， I say that for all input values， you know。

 X FX is essentiallyly equivalent to GX。 Why did I not say that FX and GX reduces the same value？

Was that血实得。Oh， because they don't F X， the application of F。 So like this。

 these two functions are not just essentiallyly equivalent because they reduce the same value。

 but they might be essentiallyly equivalent， yeah。还有。Yes， if they never reduce to a value。

 we still want to be able to say whether or not they're equivalent。

 It doesn't matter if they don't reduce the value sometimes like the factorial function we'll find。

 doesn't always reduce。This one's very smashed， but get anyways。Okay， so yes。

 if Fx and G X loop on some value， I want to still be able to say whether they're equivalent。

 In fact， we might say that two functions that always loop on every input are extensionally equivalent because they exhibit the same behavior right。

 doesn't matter if the behavior is reducing to a value。

 The behavior might be looping forever or raising an exception。 I that clear to everyone。😊，系。对吧嗯。Yes。

 I talked about all this。 So yeah， as small functions can be partial。 It basically the idea， yes。

The same type of exception， yes， and we'll talk about that more in five weeks。 yes， but good point。

 okay and then one other definition I want to give you is it's really inconvenient to talk about partial functions because partial functions are not really mathematical I mean some mathematical functions are not defined。

 but it's a lot nicer when we have functions that are defined on their entire range as in every input gives me an output value we call that totality a function from t1 to T2 is total if for every input I can give it for all values。

 v of type t1， there must be a value of type T2 that it reduces to on that input so every single input has an output value and then we call that function total。

 So for instance， div is not total because on0 on the input n comma 0 for any n it returns an exception it raises an exception but for plus or not or a string concatenation they are。

😊，Total because they never raise exceptions。 They never loop forever。

 I always get a value out when I put values in。Does that make sense？Yeah。Yep， yep。

 that follows some chain the definitions， yep， exactly correct。Yeah。

 so that is the definition of totality we will give it a more thorough treatment in the next lecture。

 but that's something to be aware of。 it's really nice when we work with total functions。

 we don't have to deal with any looping forever， we don't have to deal with any exceptions in some sense that makes our like everything feels like math in that case there's some nuances about evaluation that looping forever and exceptions can kind of mess up but total functions are nice。

😊，Cool， okay， I also want to talk about specification。

 I know you saw this on the homework that's due tonight that hopefully all of you have done。

 but we want to be able to specify the behavior of code， right， And if we want to specify something。

 we have to communicate it。 And there's a particular format that we use in this class。

 So we want to write descriptive codela b basically looks like this。 I actually left out one。

 which is the type here。 But what we're going to do is we're going to try and document the preconditions and postconditions of a function。

 What do we need to know about the functions input that satisfies something must be true about the output。

 Okay so here's how we're gonna to do this。 we're gonna to follow something called the five set methodology。

 There are five things that are important about a specification that you should always write when you write a function in this class。

 Okay and oftentimes it will be provided to you in the form of start code。😊。

So one is you should write the functions type。 So actually， let me do this。

 So if we were doing this for like the div function， for instance， we'd say。😊，Comment， give。What。

 wait what was the time？Was my example。 Oh， it was just dividing anything by two by anything。

 Okay sure why not。So this is the type， we would write it like this like an SNL comment。

 and then we'd say， what do I require， what is my precondition that must be true about the argument？

And if we look at the specification of that divide function。

 does anyone notice a problematic input for this function？0， right， Well， okay， actually。

 it's written there。 So I'm not gonna give a high you for that one。 But yes，0 is 0 is problematic。

 So let's say x is not equal to 0。 This is not equals in S and L。😊。

So we require that it's not equal to 0。 And then what do we。

 What do we get out from the input or what do we get out from the function。

 given that we know this is true。 What do we know about。Dive X divide， rather。What do we know？

What should the behavior of this function be？Yeah。嗯。It should always give an output。

 That's so there's， there's varying degrees of post conditions。 always giving an output。 Yeah。

 that's one thing you could say。 Another thing we can also just say is that it always。😊。

Reduces to two div。X。Which is， you know， but kind of by the definition。 It is kind of silly， but I'm。

Another way of saying is like， it's always too divide。 This is a comment。 Nothing is evaluating this。

 It's just for documentation。 So if you put down that it's equal to two div X， Yeah。

 that's good enough for documentation for anyone。 Now I know what the divide function does。

 because it's not very descriptive from the name。 So， you know， yeah。😊，Yeah， sorry。

 I underlined it and then I realized maybe that was a bad move。

 it's literally just two angled brackets。Left angle bracket， right angle bracket。

 you can think of it as is both is greater than or is less than。Sure， it's not， yeah。For the record。

 you can use this on like a lot of things， not just senators。That's a different discussion。 Cool。

 Any other questions。But that's how we're going to be doing specifications type。Requires clause。

 preconditions。 What do I need to know about the input， Post conditions。 What do I get out， What。

 What can I say about the output of behavior， And then we write the function itself。

 So we regular kind a fund divide。So on and so forth。And then finally， we write tests。

 We have to write tests。 So we highly encourage you to write tests。

 We have a nice little testing library that we use。 So， oh yeah， I was' gonna say this。

 These are just comments。 So it doesn't really matter， yeah。😊。

If you're using it to test the output type of your function， then yes， if my function returns an int。

 probably what I'm going to want to do is I'm going to say test dot int。And'll put whatever here。

And then I'll put two int values here。 So I'll probably put like， you know， divide。3。

 for instance here。 and I'll put whatever I expect to receive out here。

 And these can be swapped or whatever。 But， yes， depending on the output type。

 you might want to use a different kind of testing function because you want to test add a certain type。

 So the test function depends on the type of the return。 Yeah， I I'll say I would say that cool。 and。

 and to motivate this this issue a little bit more， right， like。😊。

This is just documenting an API right I'm just saying what do I expect to get。

 What are you going to receive out It's these contracts。

 these you know preconditions and post conditionsitions happen all the time everywhere you see where there are functions。

 there is expected behavior。 There's a range of inputs I shouldn't expect there's a range of behaviors I expect to get out。

 So for instance， I should only call a function with safe values。

 maybe I have a library that can only be used in a non-paralleel program， a single thread of program。

 maybe I have an API that doesn't work with non- askI characters like these are implementation details。

 but these implementation details have to be surfaced to the user the user needs to know So we put them in the form of documentation in the form of preconditions and post conditionsition。

And then retests again this is just covering how you write tests， I know it's not fun。

 but you' got to do it sometimes life isn't fun okay writing tests is important。

 so you should do it you write them like this right there will be more on this in your homework to come but the best one of the best ways to know the best way to know whether or not your function works is to prove it but because not all programmers are mathematicians and some of them don on a time they rely for good test coverage both are important I think but yes。

 so that's that and then we can go on or at least any questions about this。😊，错。

So I showed you the factorial function last lecture， it looks like this。

 but something I want to now talk about is what's the specification of the fact function and one pertinent question is is fact total given the definition of total that I gave you earlier。

 I defined it for you。😊，I'm seeing those， shakes of heads， why。Why is it not at alone yeah？

Negative input causes what behavior？Loop forever， there's no biggest case for negative numbers because we go to negative one and then we don't hit we match against zero。

 we say no， we go to the next one， we match against this， we say know negative2 for instance。

 times factor of negative3 and then negative 3 goes here and the blah blah we keep looping so yes。

 this will loop forever。But fact on negative numbers is kind of a weird thing to ask for， right。

 So probably I should put something in the documentation of this function that says。

 what do I expect you to do， And I don't particularly expect you to do something like give it a negative number。

 So I put in my requires。I'm going to require that n is greater than or equal to zero。

 I'm not going to give you any sensible output otherwise。

 so oftentimes you'll have functions where they exhibit some interesting behavior。

 but the interesting behavior is only on certain inputs so you want to use your preconditions your requires clauses to enforce that your document that you only make promises about what happens on certain inputs outside of the preconditions。

 your function can do whatever it could look forever could you know order a pizza I don't really care as long as it's clear from the preconditions that that shouldn't happen because you are going to break your own preconditions later remember。

 soft defense against yourself yes。I would accept that。 Yeah， yeah， yeah。 given it's precondition。

 Yeah， yeah， total on range of inputs。 I like that。 but yes。

 so sometimes we have to make claims only given restricting our input。 Okay。

 any questions on specification， You probably got some practice with this already。😊。

All right and then so this is kind of long to look at and annoying for me to type also。

 so sometimes I'll use these special specification boxes。

 these mean the same thing I'm just using them because I like them and I think they look pretty so that's just a remark on side notation okay。

😊，All right。Let's move on to recursion。 your best friend for the next like 11 weeks。

 Recursion is the best。 And we're gonna see why that is。

 Almost as I made the claim to you in the first lecture。

 almost every function you write in this class is going to be recursive。

 And that's a great thing because recursion is the bread and butter of doing anything in a functional language。

 so。😊，Here's the definition of recursion。 We say that a function is recursive if it calls itself fair enough。

 more or more generally something is recursive like you know in language if it refers to itself so for example。

 this sentence is recursive but also one of the best ways to describe recursion I think is from this book about this author called Douglas Hofstter who wrote this book called Gerlesherbach and this book is basically very heavy on recursion and someone said the definition of recursion is if you know where recursion is just remember it otherwise find someone who is standing closer than you to Douglas Hofstter and then ask them what recursion is。

😊，And you see you can iterate this process until convergence。

 I thought that Sck was closed and it is not。Great。Cool。

 so that's's a nice little example for recursion， but we don't have four loops。

 Those don't exist in SML， No four loops whatsoever。 So even if you wanted to。

 you won't be able to do that but you don't want to Okay so we're trying to save you from yourself。

 Recursion will be the preferred method to iterate over something。

 And what we'll find is that it's just more general than four loops。

 It helps us reason about things in conjunction with purity we find that recursion is a really powerful asset。

😊，So usually we say that recursion is something that's taught in programming classes。

 but it's also a math thing and why is it a math thing Well because precisely the function that I just implemented for you。

 the factorial function， we say that the factorial function is a piecewise function right I define it on zero to be1 and then on any other input it's n times fact n minus-1 and by the way。

 this looks exactly like the SNL definition does it not There's something going on there right So it's it's a recursion is a programming thing。

 but it's also a math thing and there's gonna to be a tight coupling here that we're exploring over this lecture recursion and induction and math are not so far apart。

😊，So and we saw that the code looked the same。So。😊。

I'm going to tell you now a secret which you should take with yourself for the rest of the class。

 because this will be how you write any recursive function。

There's a four step formula and what we do is first we identify something called the base case。

 the base case is the case of the function that does not recurse。

 there should always be one and if there is not one， then your function probably would look forever。

So you identify what the case is based on your input， right， and then you write it。

The next step is that you identify the recursive case like identify what input， so for factorial。

 for instance， the base case is when the input is zero， right？😊。

And the recursive case is when the input is literally anything else about in this case is greater than zero。

 So we identify and write the base case， and then we identify the recursive case。😊。

And then we assume the function already works。 We call this the recursive leap of faith。

 This is incredibly important to be able to get right。 If you're thinking about。

 if you have to think about your recursive function， right。

 and you have to like unroll it a billion in times。 like you have to say， okay， fact of4 is blah。

 blah at times factor3 is times factor2， you're doing it wrong。

 The really cool thing about recursion is that you can think about an infinite range of inputs by only thinking about one case。

 because of this thing I just said the recursive leap of faith， assume your function already works。

 and then through magic self self- fulfillfiling prophecy。😊。

It will okay you just have to ensure that it keeps working so long as you assume that it does right and will substantiate what this exactly is in like half a section here okay。

And then write the rehesive case， given that you know that the function already works。

 write the recursive case just do it and hopefully if you're writing a recursive function。

 the answer to the thing you just assumed should help you it should and if it doesn't then maybe you wrote something wrong or you need to alter your code bit。

😊，Okay， and I said this is about the base case。 Any questions on this， and I will show you examples。

😊，系。So let's go through it。 Let's write， let's write a new function。

 I got the specification for you here。 Let's do some pair programming。

 We've got the power function takes in a tuple of two ins and returns to me an int。

 It's supposed to evaluate power and K is supposed to be the power of n to K exponent n to the K right And we require that K is greater than equal to0 right。

 but how might we write this function。 Well， what's the first step， What do we do。😊，Base case。

 I heard mutterings of base cases。 Okay， we're gonna， we're gonna write the base case。

 So if I raise any number to the power of0， I get one。

 This is one of those facts when I was like an elementary school there。

 I love to go around to people like， what do you think the power of0 is。 And they'd be like0。

 And I'd be like， it's one。 You fool。 by the way， there's little reason for a third grader to know that。

 Yeah， I don't recommend this for you， by the way， But if we raise this to the power of 0。

 we get one。 So that sounds like a pretty nice base case for us， So let's write it boom。😊。

I have any N， and I have 0。 I would get one as a return value， right。

 And then this is not real S L code because I haven't written the rest of it for you yet。

 But that's our base case，Okay， on the recursive case。

 what is the recursive case And what what I mean by that is like。

 what input should the recursive case correspond to。Yeah。N N K， just， yeah， just any N N K， yeah。

Yeah， I'll give the high cheek for that one。 I realize I'm wilding and consistentsistent about when I give high choose。

 but I'm， you know， that happens。So that's so one thing to note also is one thing I wanted to define for you。

 It might be unclear because we have two inputs here， right， what is really like the recursive case。

 Well it corresponds to when this k value or this k input is not zero we call that the variable of recurrence and the reason is because if you look at it we case on when it was zero here what the variable of recurrence is basically what you're causing to get get smaller in some sense through every recursive case and eventually you'll end up at0 or something that's your final value and you'll stop So the fact that we don't only care about the n here right what we're recursing on the variable of recurrence is k so I don't really care about the n。

 so therefore in in my recursive case， what I really care about is the k value does that make sense。

So what we're going to do is we're gonna to say that the recursive case。

 we want to be able to do p and K for an arbitrary K。

 Well we're going to use our definition of power to do it。 So recursive leap of faith。

 assume that power already works， but not already works always right because let we be done。

 We want to assume that it works on a smaller input。 So if I have。😊，If I have Po。And。

And this is my variable of recurrence。 My K is the thing that's getting smaller。

 I probably want to assume。When k is smaller， the simplest case for this for natural numbers is the minus-1 case。

 So we assume how of n K -1。Assume that that works And then given n to the power of k -1。

 we should know something about how to solve power N K in general， okay。So。So yes， so basically。

 we already assume that power of n and K -1 already gives us the K -1 the power of n。

 And then I'm sure you know where I'm going next。 How do I get N to the K from n to the K -1。😊。

He's got it。Times end， yes。So our rehecursive cases is literally just take this guy that we knew we assumed already worked and then multiply it by n Okay。

 there's a tight correspondence there。 we are going just down one rung on the ladder because if you think about the recursion n is the next step up from n minus1 okay。

So that's how we implement power at the end of the day。 Any questions on this？

This is a fairly simple example of how we use the recursive formula。

 but I'm telling you that this mindset applies to every function we will write for the next 11 weeks and it will really help you as we get to more complex examples。

😊，All right。Thats the magic， Any questions？好。Okay。But let's look at the formula again。

 So I said this was it， right？But I'm feeling a little sense of deja vu。Noone else feeling dayja。

 this feels like something that I know you will have seen。

 And given if you saw the table of contents， you might guess where I'm going already。

 But this looks something， This looks like something else。 What does it look like， What do you think。

😊，Induction， Oh， you thought it was recursion， but it was induction all time。 It was induction。

 Oh my God， induction and recursion are the same thing。 Let's go。

 There's a foures set for like proving any simple inductionductive theorem。 They're the same thing。

 Let's so we， we take， we take our perspective and we just give it a switch。 So on induction。

 Allright， perfect。 induction。 We're gonna talk about induction Now， your favorite。

 What I love about induction。 I think that the I think the ancient Chinese philosopher Laut put it best when he said the journey of 1000 miles begins with a single step。

 You see， he was talking about induction。😊，You didn't think they had that back then， but they did。

 Oh my God。So anyways induction， so let's talk about mathematical induction。

 shall we everyone does everyone rather does anyone not feel super strong about their memory of induction？

😊，Oh， you're， you're all experts。 Okay， looks like the induction workshop on Friday is gonna be empty then。

 we you should go that。 It'll be helpful。 So mathematical induction is induction on the natural numbers。

 We call it simple induction。 It's a proof technique。

 It's how I prove theorems on the natural numbers。 If I have a predicate or a property P that holds of natural numbers。

 P then I want to prove for all natural numbers。 N。 So I use induction to do it。😊。

And in particular in logic， here's what it looks like。😊。

It's real scaryhu but but here's what it means， Let me let me demystify that for you。

 So we say P of zero logical and for all n。P of n implies p of n plus 1。And then this whole thing。

Implies that for all N。P of N holds。Okay， I just rewrote the same thing that was on the slide。

 But the point is。Right， this is our base case。 We want to prove it for the zero case first。

 Once we prove it for the zero case， we want to show that for all n。

I can get from anything to the next thing。 Alright， I can take a single step， right。

 And then if I can take that step from anywhere， then I can。Go anywhere。 I can。

 I can prove this theorem for any number， for any concrete natural number N。

 the way I always like to think about it or the way I was taught concepts was right if you try to climb a ladder。

You know， you can start at the bottom rung。 And if you can get from one rung to the next rung。

 then you can climb to anywhere on the ladder。 Okay， that's one one way to think about it。

 It's a nice little visual picture。 I didn't fully commit to the bit and bring a ladder。 I'm sorry。

 I thought about it。 So， yes， so any step fall in the previous。

 Then we get a theorem for all numbers。Now let's go through the inductive formula I showed you just a second ago。

 okay I kind of showed it too you fast。We we identifying and the base case where base case is defined as the case of the inductive proof that does not require an inductive hypothesis。

It's kind of a， of similar， similarity and vocabulary there。Identify the recursive case。

 the inductive step， I might say。And then we assume that the induction hypothesis holds。

 which is this guy。Within our quantification for n and this is important， by the way。

 so when I do my base case， I instantiate this n like any kind of variable at some kind of variable right some n。

 and then I say that for that thing I have this this predicate holding， this property holding。

 and then I go improve this。😡，There's a difference in kind。 If I say this， maybe I'll understand。

 But a difference in kind between this and that。If that makes sense。

 like you should never assume that for all NP P event then。

 you should never assume the theorem holds for everything is then you're assuming what you are trying to prove。

 That's a mistake。 right， You will have points taken off of that。

 Your T A will go over this with you in lab tomorrow， Okay， but that's important。 Okay。

 quantification saves lives， right，In some cases， Okay， prove the recurcursive case or， Yeah。

 prove the recursive case， the induct inductive step under the assumption of the inductive hypothesis。

 And then you've got your theorem。 The theorem holds for all natural numbers and okay。😊，Okay。

 and then the base case looks a little different。 Its the case that doesn't require an induction hypothesis。

 This should look very similar to you， right， It feels very similar。 They're just the same thing。

 They' are two sides of the same coin。 Okay， Any questions on induction。 And we will do an example。

Now， I realize that should probably。 I'll leave this up。Cool。Okay， let's do something， so S of N。😡。

Some of first and。And odd numbers。And what I want to prove？Is this theorem？I want to prove that。

S sub n is n squared。 here， the sum of the first n odd numbers is going to be just n squared。

 If you didn't know that today， you're going to learn。Okay。

 but what's the skeleton of an inductive proof。 Well I gave you the formula。 So what's step1。

 What do I do first。Base case， B C， for short。And I'm going to say that n is equal to zero right。

0 is a natural number。 Well， actually， let's not do that。 let's do one。 I chain in my mind。

 Let's not do this some of the first zero odd numbers。😊，B case n is equal to1。 Well。

 what's the first odd number。One， so SN is equal to1。It's equal to one squared。Boom， right， good。

 We got the basic。 It's cool。 Alright， induction hypothesis。😊，We assume the theorem。

 but only for something specific， a specific input。 So this， this property， this hypothesis here。

 this theorem， called it P of N。Well， actually， it doesn't matter。 I'm just going to say that。

 assume that S of n is equal to n squared。For some end。And writing this is the key here。 Okay。

 if you write nothing， Well， you'll be better off than if you wrote for all N。 Okay。

 if you write for all and， you're definitely wrong。 But right， right for some。 Okay， just。

 just do it。 Alright， so we assume that theorem holds for some N。 Alright。

 And then what do we want to show。 Well， we want to show。S of n plus1。Is equal to n plus1 squared。

 right？Well， let's break this apart。 What's n plus one squared。N squared plus 2 n plus1。Okay， great。

Let's keep breaking apart equivalences， what else， where can we go from here？😡。

N squared equals S of n， I like it。 I like it。By induction hypothesis。

 So I'm going to cite my sources here， actually， I'm gonna to say。You know math。By the way。

 that's okay。 you can say that if you' if you're asking for a citation， like， what do I T A。

 what do I write for3 plus four equal 7， Just write math。 Just do it。 It's okay。 We're humans。

 We understand。😊，We have stuff to do other things for radar papers。Well we， But okay， by math。

 And then we got to this step by induction hypothesis， right。

 I said n squared and S sub n are the same。 That was what I assumed right here。 right， Its same N。

 And then what do I do finally。😊，2 n plus1 is odd。 and in particular， it's the next odd number。

 right， Yep， exactly， the n odd number is just 2 n plus1。You can think about that。 It's just true。

 You can just like that。 So this is equal to S sub n plus one， right， rather， it's equal to well。

I seem to have turned this inside out。But assume that we did it this way。Yeah。Yeah。Alright。

 that's proof。We can all like。Like sort of like solve this。到就不是。All number as before。

We also keep it by yeah。 Yeah， yeah， yeah， that's a。 I mean， yeah， lots of ways to do it。 But yes。

 so now we have our proof。 I'll give the hi to you。😊，I have many highes。 Oh my God。

 the pieces of the functions are pointer secrets still here。Okay。

 and what I what I like about this proof is also it's nicely geometric。

 you can think of it as like a square。😊，The first some of the first one odd numbers。

Some of the first two odd numbers because this is three。

And then some of the first three odd numbers is。5， right， and it's just， it's just a square。

 which is n squared。 right， I don't know。 I think it's cute。 I didn't。

 I didn't approach it with that， but you could also do that。 You were。

 very rarely will have the opportunity to picture proof things in this class。😊，But yes， Okay， boom。

 all of that。 So then by the principle。 And then we usually we。

 we end off saying by the principle of mathematical induction by simple induction on N。

 The theorem holds for all natural numbers。 N。 Okay， and usually we want to also specify。

 we proceed by state the kind of induction you're doing。

Spoiler alert there's going to be several types of induction you can do。

 and you can also do it on multiple things yeah。I believe there will be all of one proof in this class where you don't necessarily need to do induction。

 and I will leave it as an exercise to you as to which one that is。

 If you can do it without induction， feel free， the opportunity will not come up very often。

 It will quite often be an induction proof。 I'm giving you that for free， but yes。Go for it。

 You can break the laws of the universe and improve something in generality。 Please do。 Allright。

 cool， induction， our favorite， right， let's move on。 So induction recurrosion， not so different。

 Okay， they feel the same。 instead of a rehesal call。 I have an induction hypothesis。

 I'm proving things。 I'm implementing things。 There's actually a tight coupling with implementing something or specifying something。

 And then also proving it。 right， So that's an interesting thing。

 But we'll not go too deep into that。 But this should feel very， very familiar。

 And then spoiler alert， we're gonna take the two， get the best of both worlds when we jam them together。

 and we start proving things about code in this lecture。😊，It's not one of those things where I say。

 oh， we'll explore the next lecture， we're going to do it with this lecture， I promise。Recursion。

 we use the answers to subpro。 If I have power of Nk， I use poweru of N K minus1， right。

 power of N K minus-1。😡，Gets me。To power of N K through some means。 this is not。 this is like。

I don't know。Pretend that's implies。 I'm not， I'm trying to show it's not stepping。 Yeah。

 I don't want you get confused。 but kind of like leads me to power of N K in a inductive proof P of N kind of leads me to P of N plus 1。

 I guess。Or P of n -1 leads me a P of n， whichever。 Okay。

 like there's are different ways of thinking about the same thing。 Okay， the structure looks similar。

In induction， I use the induction assumption inductive assumption to prove my theorem。

 They're not so dissimil。The biggest thing you can take away from the section is the recursive belief of faith。

 have trust in yourself。 It's kind of like a self- confidenceence thing like， yeah。

 does your function work， assume it works， believeve in yourself， and then it will。 All right。

 we don't often say， you know， mind of matter what you think what you believe goes。

 But in this case it's actually quite literally true。 So take advantage of that。😊。

This is not a self hubub class。Allright， so we have a difference between writing and verifying。

 We've seen that we can use induction to help us write recursive functions right we did that when we wrote PA。

 we use inductive reason now it's too far back we use inductive reasoning to implement the power function here right I was a proof never mind。

😊，But what we also can do。Is that we can use。We can use induction to help us prove our code。

 We're not just here to write code。 we're here to write correct code， So let's write correct code。

 We can prove Synmic functions on correct using induction。😡，嗯。Section  three。

 any questions about induction？The type of induction I just did up here is not standard。

 we're not really going to see mathematical induction on numbers for mathematical theorems。

 we're going to see induction on natural numbers for SNL theorems which are much more fun。😊，看。过。

Alright， we just wrote pal， but let's make sure that it's correct。 Now we wrote it。

 and I reasoned about it to you。 and maybe you're thinking， okay， yeah， it's correct。

 and it'd be really cool if I pulled the fast one on you know， I was like actually it's wrong。 No。

 it's right。 But let's prove that it's right。 Let's make sure that it's right。

 So when we're doing an induction proof usually there's something that we should induct on the correspondence to our variable of recurrence。

 So what variable should we induct on if we wanted to try and do this proof。😊。

What is our input that we are inducting on？Okay， I hear from many people。 Okay， K， right。

 It's the same。 It's the same。 the same thing just viewed in different lens。 I put on my。

 my induction glasses one day， and then I， I view it as an inductive proof， right， coolol。

 So the variable of recurrence is going to be typically our our candidate， right。

 So let's prove this theorem。 And I'm not gonna write this one down or yeah。

 I'm not gonna write this one down。 okay。😊，How of N of K reduces to n to the K for all K greater than equal to 0。

 right， It is the same value。 Okay， let's do mathematical induction or simple induction on K。Now。

 base case， let's say that K is equal to 0。 Well， what can I do here and actually let me。

Let me take you brief hiatus because actually I want you to have the。

Function definition in front of you while we do this proof。So remember that pal， we defined it as。

How taking an end inch？And zero takes inch。Returning n equals one。

So for our base case k is equal to zero， what is our claim。

 we want to say something about power of income a K， so if we have power of income。😡，N comm is 0。

 What can we say about this？What do you think？Anyone gun any guesses？

So the structure of a inductive proof on code is that we're just going to try and show this through equivalences。

 we start with our left hand side here， we start with power of N a K in whatever case。

 and then we want to prove that it somehow steps to this。😡，Well。

 what do we have when you're doing an inductive proof， okay you have it in knowledge bank。

 Everything I know about my function is here。 That is the entire sum total of my function。

 nothing else other than like other function definitions is relevant to me here。

 So I consult my knowledge bank。 Well what do I know I want to prove that I want to show right I want to show this。

😡，Right， so let's prove it。 Well， I have power of n comma 0。

 What do I know that power of n comma 0 does， I know that given my function definition。

 given my knowledge bank， it just reduces to one okay so。😡，We say that it goes to one。

And what is one also known as what is also known as n to the zero。

So we say that this is like I lied and said， I wasn't going to write it down。

 I'm going to write it down。So we say that I clause one of p。I have that it reduces to one。

 which is n to the  zero。 I this adequate to prove my case？Yes， this is good enough。

 That's all I need to know。 So then I'm done， okay。So now I just， I literally just cite it。

 and then we know that n to the0 is one。 Okay my induction hypothesis， I want to assume my theorem。

 So I assume that how of n comm a K is reducing to n to the K for some K， right。😊，For some K。Next。

 I want to prove that power of n to the n comma K plus1 works。Alright。

 so what do we think about this。 Let's start from the left hand side。

 So I'm showing you like the algorithm for how you prove these things， right。

 I'm showing you each step。 So we start at how of N comma X K plus1。Where do I go from here？😡，Yeah。

 second clause。 Yep， when you when to be fair， honestly， in the live 1。

50 proofs is very few things that you're actually able to do。 Like。

 you can kind of just search the space and then find some move you can make。

 And usually the move you can make is the right one。 So let's just start signing equis。

 You're exactly correct。 So this reduces to。😊，N times p。And came。

And we're kind of relying on an assumption here， which is that K plus1 is not zero。

 and we kind of just know that because K was quantified a certain way。

 yeah it should be fairly obvious， you don't really have to say anything for that。

I' on one points the website。这会。Like we're assuming that。Yeah。

 so I don't think the Ts will take off for you for that。 But you can say like case assumption。

 for instance， like buying my case assumption， which is that， you know， I have some K。

 I should have written some K greater than equal to 0。 But by that assumption。

 then we know that we're not gonna answer the first case。 Yeah， that would be perfectly fine say。

 yes， so we say。😊，Cluse 2？Pow okay。All right， and what do we know about this， Well。

 I'm you I'm sure you know where I'm going next， but we have our induction hypothesis once we have the smaller input。

 let's break it down so we have。😊，Well， actually is essentially equivalent too。看了么。

N times n to the K。Right， this is by assumption。And then what we know that n times n to the K is while we know that that's。

En to the K plus1。I'm kind of mixing math and code here。

 But for these kind of like meta proofs about math， like it's perfectly fine。

 this is just gonna be n to the K plus one， right， By our induction hypothesis。

 By our assumption of what value power of N comma K returns。😊，Is that clear to everyone。Yeah。It does。

 It does matter。 And I kind of was， was， so， okay， we say the steps to this。

 And then I'm perfectly fine with you， like tacitly assuming that this is so okay。

Palll of income a K evaluates to。And to the K。 So actually， this would have been a fine thing to say。

 I wanted to say that these two things were equivalent。

 but also the in induction hypothesis gives us that it steps to， right， actually。

 you might want to write this。Because it might take more than one step or zero or more steps。

 but generally， as I said in the last lecture， right reduction is stronger than equience。

 if I say reduction， I get equivalence for free， but if I say equience， I don't always get reduction。

 so be careful about what you say because you might save reduction。

 but you actually meant equivalents and then the T is going to take points off your homework yeah。😊。

So。There are some cases you could only use equivalents。 Suppose I gave you a lemma that said like E1。

 some E1 is equivalent to E2。 Then you could only use it to see that two expressions were equivalent。

 not that they s to each other。 Like if I gave you a lemma that said， like， you know。Two plus three。

Is extensionally equivalent to1 plus4？And you wanted to cite this。

 You would not be able to say that like F of two plus3 steps to F of one plus4。

 Does that make sense Like I wanted to replace this with that because I knew that they stepped。

 they were equivalent， but it would not be accurate to say that this steps to that。

You can think about it。 And it kind of doesn't make sense， right， It's not a simplifying step， yeah。

はと。喂。Yeah。So we're actually not trying to show that it's we're not trying to show that it's equivalent to。

 We're trying to show that it reduces to this hook right arrow here means reduction。

 It means reduction to a value。嗯。That's a question， which is basically because I said some。

 because the theorem says that we want to prove that it reduces to。

 we don't want to show that it's equivalent to two。 in this case。

 it doesn't really matter because if you're equivalent to a value。

 that implies that eventually you reduce to it by what I said previous lecture。 But in this case。

 like it's rating comprehension。 Basically what what we ask for you to prove， you should prove。

Is basically the idea， yeah。Yeah。That's exactly what we're trying to do。 When we say reduction。

 we mean SML really does this。 Okay， so， so but you can use your intuition。

 but also there are a few rules， right， Like， we know that F applied to a value must always step into the body of F。

 like these are rules that you can just free ci here because it's a fact you know about SL。

 We're taking our SL facts and then signing them here。 So for instance， clause to。

 this citation is my citation that I know in SML fact。

 which is that how of na K plus one must evaluate to this given this code。 Okay， so yeah。

 we're really like syn all of this is just SML reasoning。 cool。😊，啊有。We were doing step2 because okay。

 this implies like this step2 means。This is well by saying Step2 I've also said this。

 but if I only said this， this would not imply Stepps2， but my theorem is asking for Stepps2。

 so if I write this， I have not shown you that power of N comma K+1 steps2 this necessarily。😡。

I've shown you that it's equivalent。 And if you， if you reason about it。

 if you like kind of think with your brain， you say， oh， well， if it's equivalent。

 essentially equivalent to a value， you must step to it。

 But you'd have to justify the reasoning to me， too。And I think we'd accept it if you did。

 like if you said these are essentially equivalent。 by the way， here's the proof that like， you know。

 or like reasoning as to why essentially equivalent think the values must step to it。

 but you'd have to s supply that extra reasoning， right， It's strictly easier to just say， oh。

 let me give you the thing you ask for， which is that it steps to。😊，哎，呀各方成这样。It's sylistic。

 I could have done this from Pu N K and then gone to P Pu N K -1。 and I could have gone to power N K。

 I just chose it to structure differently。 Like it， it doesn't matter， right， So like if I。

 if I had said this， if I'd started from here， I would have quantified that my K is still greater than equal to 0。

 and I would have gone to K plus1， would would have been a fine induction step to have taken still right。

 like going from k plus1， downwards versus going from k to K -1。😊，好。Oh， sure。 this is。Oh， we okay。

 So this one is going from K to K plus one， right because I use K plus one。

 and I use my recursor call to K。😊，What I could have done poweru N K and then called poweru N K minus-1。

 and that would have been fine as well， because I would have said that K is greater than equal to1。

In that case。You have to shift it by one， right， because I don't want to becauseuse if I said that K。

 it was like like I'm actually， yes， if I had said it was this， right。

 I would not want to have like K to be like negative one or something。But if I was， if I was here。

I would not want to assume that K is just one。Because this will not connect with my base case。

 because this will now go to。1， yeah， which is not power then。Ande to 0。 Basically。

 you have to make sure that your induction steps and your hypotheses line up。 If I had assume that。

 for instance， for greater than equal to 2。 Okay， what would I do if I had said that K is greater than equal to 2。

 I get。3。Oh sorry，2， two plus one， and I get two here。

But then this would never actually reach my base case because I have poweru of n comma 2。

 which is not my base case of power n comma 0。 So what I'm trying to show you is that like where where you quantify the bound of your variable。

😡，Interfaces with the casing that's done by the function itself because of the fact that our base case is0。

 we want to quantify our k such that we eventually rely on pu and comma 0。If that makes sense。

 there will be a more detailed treatment of this in lab or the induction workshop。 Oh yeah。

 that's the basic idea。 It doesn't really matter。 Like， these are basically a lot of coding coding。

 and what I mean by coding， I mean， encoding， right。

 It doesn doesn't really matter how you specify it as long as the form。 the content is correct。

That makes sense。对。Alright， let's move on。 So I showed you this kind of connection between induction and recursion。

 and we're gonna to make that concrete because we have kind of this relationship。

 Our base case in the program and our base case in the proof are the same。 My recursive call。

 my induction hypothesis are the same。 My variable recurrence and my induction variable， I'll say。

 are the same。 This is what you should take away from this。 All right。

 programmatic thinking is a mathematical thinking。 I have this here to remind you of an element。😊。

I am actually farther in than I thought。 So what you're gonna to have to do now is you're gonna have to get into your groups。

 All right， can your houses take your quiz， great scope，5 minutes if you're in blue team on my left。

 yellow here。😊，I look Brandon in the back。 Same as last time。 Okay， how do you feel about the quiz。

 Who thinks they won。Well house is， I don't even know why I asked。 Okay。

 hopefully all of you think you won。 What was what's answer the question 6。 Sho it out， shout，3，2，1。

😊，I love the。あし。Wa，aa all right you guys you guys said it and he kept going and I got confused。

 All right， cool all right， we'll see at the end of the lecture。 Allright you are graded quiz time。

 So we're done with that。 let's move on。 I gotta show you this for lab tomorrow I promise unfortunately。

 there was some feedback about how you want me to go slower and I try to go slower unfortunately。

 that means that I have a lot of stuff to cover。 I'm not gonna get to all of it。

 but you can read through the slides on your great time and please do because I worked really hard on them。

 All right so we saw function clauses。 I can do fun fact to zero fun fact N。

 and that's called a function clause。 I match to whatever clause in linear order to pattern match on the value I take his input。

 but we also have these things called case expressions。 a case expression looks like this。

 I case on expression who would have guess and then I go at some at some particular cases So I Prince instance case two of one goes to three or goes to4。

 This is the wild card。😊，RightThe syntax of a case is that we have a bunch of arms。

 We have a bunch of cases Only the first one has has a bar in front of it。

 which was a language mistake by the designers of this language but it is what it is but so don' put don't put a bar here if it's the first case usually we will indent it like this so we'll put on the same indentation level as the case And then does anyone want to hazard a guess as to looking at this like what they think that it does what do you think this evaluates to。

😊，Or， I heard four， who said four？All right， yes， it goes to four because two is not。1， right。

Another thing to realize is that for the same reason as if and else expressions。

 case expressions have the same typing rules， every single expression returned that is these two here have to have the same type because otherwise what do I get type on safety right I could potentially produce a different type in each branch and that's a bad so it won't type check and ill typed programs don't run right so make sure that these are the same type that's important to know。

😊，And we're gonna speed through this， but fact I I wrote with function clauses earlier and equivalent form to it is I could write this。

 This should look pretty similar right It's just I case on n， if it's 0 I go to1。

 if it's anything else， I go to n times fact n minus-1。

Something to know is that I could have written this with N here instead of wild card。

 But what it would have done is it would have done the same thing。 I would have shadowed N with N。

 I would have produced a binding to N that was N。 Does that make sense to everyone。

 I'm kind of like going through this fast。 But it doesn't really matter if I had written wild card here。

 And I did。 I'm using the end that was here。But if I put like x or something here。

 I'm producing a binding by matching n to X。And if I'd match it to n， it'd be the same thing。

 This is just like， kind of like。Syntax， but the point here is not like。

 I could have written either of those things。But case is still an expression。

 so if I'm free to write something like this。😊，And this will evaluate to six， right， eventually。

Because what happens is at first I evaluate the case and I get four and then I get plus two， right。

 and then I get six okay， case expression is everyone cool。Yeah。In SML。

 usually we're going to favor function clauses as opposed to cases。I think it makes， I think。

 I think the reason for that is it makes the proofs easier becauseuse you say by clause  one of by clause 2 of function。

 In reality， I think it makes the code a little bit uglier， but not just me。

 I I work in a language where we don't have function clauses。 It doesn't matter。 But I'm yeah。

 I no real， real reason sistic reference。 Yeah， cool。 So it's totally okay to write this。😊。

Another thing I need to tell you about are lists。 I showed you very basic things。 I showed you ins。

 I showed you bos。 I showed you strings， but sometimes we are interested in keeping0 or more things。

 We're interested in like a list of objects。 you know， Python Python has lists。

 But S MLs lists are a little bit more special。 So before I can define list for you。

 I need to talk about the type。 So we say that there's a type T list。

 this T is code right for any type T。 So if I have int。😊，Which is a type。 I also have。Enlist。

If I have bo。Which is a type， I also have bull list。看两吗。And if I have int list。

 I also have int list list。Okay， this is I can iterate this process， I can get lists out of lists。

 but every element in a list needs to be of the same type is a restriction that I have for you。

 Okay it's not like Python， you can just shove everything in the list。

 they all have to be the same type。😊，So here are some examples and this is the syntax we will use。

 The syntax is square brackets and then stuff in between Allright so this thing here we call nil that's called pronounced nil and it's the empty list and nil is of type int list it's also a type bo list。

 if I have a list that has comma separated values it has the type of what of the entries elements are or a types are So you know square bracket1 comma 2 comma 3 is int list because it's a list of integers in particular it has three in them if I have this one which has high string and then their string in there。

 it's a string list。😊，Okay， should be fair enough， the syn action makes sense。嗯。But what if so yeah。

 yeah， go ahead。Yes， it will， but please type annotate your vow declaration。The yeah。

 so the official answer is the type it interprets it as is don't worry about it for three weeks。 Yes。

 it'll be something called a polymorphic type。 and we'll talk about it in two weeks。 Yes， but yes。

 you you're getting ahead of me。 Yeah， and if you do really special things。

 it'll complain about some question mark X1 nonsense at you。 And if you if you see that。

 you really messed up and really don't think about it。 It's like the wizard vz。

 There's a man behind the curtain。 I'm trying to tell you not to worry about it until we get far enough。

😊，Yeah， yeah。 but good question。 And also， I have a case where I have a list where the entries themselves are in lists。

 So this is a list of one thing where the one thing inside is a list of two things。

 It's the same sort of the same deal as tus， right， Let's move on。

 But I can specify list in line like this。 But what if I want to add to a list。

 I use something called cons using a constructor so。😊，A list is two things。

 this is the one thing you should think about， a list is two things， two possible variants。

 two possible ways a list can appear。One of them is nil。

 which is the empty list of type T list for some type T。 Okay The other thing is that it can be cons。

 This thing is called cons and let's in fix， so it can be for instance， one。Cons， the empty list。

And this is just syntactic sugar。 Or rather， this is just syntactic sugar。For that。ok。😊。

What I mean by that is that cons is like it's like a function， a constructor is like a function。

 it is not a function， but it is like one that takes into two inputs， it takes in in particular。

 something a type T and another list and it is a list So it basically this is like prepen cons takes in an element and puts it into a list except it doesn't do when you work to do it it kind of just is the list so if I say something like well sometimes it does work。

😊，But if I said something like this。This means take two， put it in this list。😡，As the first element。

 and an element， a list can either be empty。Or it can be something in front of another list。

 It's a recursive definition right Are are you fairly convinced that like a list that is nothing or an element con onto to another list。

 like an element in front of another list then you can achieve any list ever。

 right because you can just put whatever elements inside。

 This is a simple recursive definition that suffices to define any list ever Okay。

 and I'm being abstract in the type because this works for any type。 Okay， so like I have， you know。

 I have a。😊，The empty list。And suppose I want to cons on high。

 we say we might describe this as coning。High to the empty list。And this is a tape string list。Okay。

 I can iterate this， I can say。I don't know， hello。And this is right associated。

 That means if I just write this in line， like。Hello， cons， hi cons， noil， this is interpreted as。

This， okay， because otherwise I wouldn't type check， right， because if I did。If I did this。

I would be coning a string onto a string， and a string is on a list。 so this one't type check， right？

So。😊，Anytime I write cons， it's right associative is the point。

This is just syntactic sugar for rather like this stuff。宝。Is just intactic sugar for this？

This is syntactic sugar for that。Okay， it's just a nice shorthand we can use to write it， yeah。

The top the bottom is the top secretly。Yes。Yeah， I think I erased that。 Sorry。

 Im mentioned write this is a typeing list， but yeah， okay， cool question。😊。

Probably gonna to move on here。 You'll get a more detailed treatment of this tomorrow。嗯 okay。

So I talked about that。 Conors are patterns， which means we can case upon it。

 I'm gonna show you a real quick an example。 This is the is empty function。

 I'm talking about a function of type in list to bull that returns true if it's empty and false otherwise。

 because constructors are patterns。 If I case upon a list。

 I get either nil goes to true or I get cons of two things goes to false A list is one of two things。

 It is either empty or it is one thing attached to another list that's a mantra。

 you repeat that to yourself， a list is either empty or it is one thing cons on to another list and that's how we destruct a list。

 by repeatedly consing things off of a list by repeatedly taking things from the front。

 we get to any element in SmL， there is no of one list indexing operator。

 you have to go and retrieve whatever you're looking for。😊，ok ，那么。😊，That's the idea。 yeah。

The list following it。 But yes， yeah， essentially， if you look at the memory。

 which you shouldn't have to think about。 But yes， that is what happens yeah。Cool。

 this is the is empty function， very simple。 Okay， let's we were going to write a simple inductive。😊。

Forula on lists。 But I'm look at this in your spare time and convince yourself this is correct。

 It's just finding the list of the element by taking off one element and then adding one。

 The point of this is that you get comfortable with the syntax。 That's what I care about。 Okay。

 be comfortable with using lists。 But I gotta move along because I promise there was one thing I would show you before lab tomorrow。

 And I have sometime， okay。😊，I said something about how I show you fast exponentation I showed you power N K and power of N K that I showed you computed n to the K by multiplying by N K times。

 right I did K multiplications。 If you're really into math， you might know that， in fact。

 you don't need to do K multiplications to do it nothing called repeated squaring and it takes advantage of the fact these two factss here。

 So if I have K is an odd number， then N to the K is just going to be n multiplied by。😊。

And then this is the floor operator， right， So like like if I have k over 2。 and that's like 3。5。

 the floor of that is 3。 So this is equal to n times n to the floor of k over  two squared。

 And then if K is even this should be a little bit more clear。

 It's n to the K over two quantity squared because exponential rules means I multiply this by two。

 So I get n to the K。 and this is basically just because we have to deal with the offset from the odd。

 these are two fun facts。 But if you look at this， this is a mathematical definition。

 and what are mathematical definitions there are programmatic definitions because programs are math of the same。

 So you see n to the K over two squared。 I see two recursive colors Allright。

 So we'll split that technique， one recursive。 We'll see Okay so let's turn the mathematical definition into a program。

 Allright， Let's do it。😊，I'll let you read this for a second。 But the idea is。

 I want a fast power function。 N to the0 is still one。 But if I have n to the K， if K is even。

 that is if k mod 2 is 0， then I'm going to say that it's equal to。😊。

ToN to the K over two multiplied by itself。 right， That's exactly the definition I gave you on the previous slide。

 Otherwise， if it's odd， I do n times。Well， end to the K -1。

 I I change it slightly because this makes the proof easier。 but don't worry about it。 It。

 it still works， right， So this is the definition。 I everyone convinced that this also like works。

 It is a power function。 Like it is the same power function， just implemented slightly differently。

Okay， yeah， I just the study， so yes it works， but I promised you that we would do less multiplications。

😊，Does anyone see a problem here？Do you think that this is actually achieving that yeah？

You can see me preparing the hyp you。 but yes， yes， that is indeed what happens。

 If I'm calling recursive call twice， I'm repeating the same work。

 a really smart compiler could optimize this out。 but what's optimization， Okay。

 you're doing you're doing the call twice。 Okay， we pretend we don't know about that。

 So in this case， we're going to be doing exactly the same or maybe even more， I don't know。

 actually， you know what。😊。

![](img/8c8904319d292851c0f31f5c3c3501b0_9.png)

So I wrote a debugger for SML a while ago and basically here's how it works as a stepper。

 supposeupp I have the old Pow， which is PAO 2 coa4。😊。

Pal 2 comma 4 is equal to casing on two and4 of these two things。

 we step into the second case because4 is not zero， right？So we get two times power of 2 and4 minus1。

And then this， in turn， steps to this thing。 Don't worry about this。 But this steps into that， right。

 And if we iterate this enough， you should see that like this， oops， sorry。

If you iterate this enough， you should see that this number goes down。 right， We're doing 1 -1 now。

 So were you should be convinced like this is what the power function really does in SML， right。

 And we get this。 But let's suppose that we had a really big example。

 So those we were doing power of 2 to the 50 and fast power。

 as I've defined here for you of two comma 50。 this is actually the faster one。

 but don't worry about that。 So if I did mulligan test2 S M L。😊，Let's look at what PAu2coma 50 does。

 let me just hold down the entertro key for you。It's suing 50 multiplications。😡，Allright。

 this is going to take a while。 It's going to take a while and then eventually it'll overflow。 Okay。

 which don't worry about that。 pretend that didn't happen。 But the point is。

 the point is that doing this call twice is going to induce a lot of multiplications。 All right。

 But remember something we learned about。 We learned about referential transparency and purity。

 which means that these two calls， do you believe that fast power is a pure function。

 always the same outputs given the same inputs。😊。

![](img/8c8904319d292851c0f31f5c3c3501b0_11.png)

Then shouldn't we be able to call it just once and reuse that answer So let let's remember that So the thing I have to show you now is to do that we're going to use something called let expressions。

 Some of you ask like how do I declare a variable in an expression we do it using a let expression a let expression says let me declare these variables in this expression and I can use that inside of a function so for instance。

 this is an expression so let value be equal equal to 2 in the expression x plus x and then add that to3 so this whole thing will evaluate22 plus two which is4 plus three is7 I'm kind of speaking through this because I kind' of have to show you this but the point is also that like when you do this let it's what's called lexically scoped so the value the variable you declare here is only visible within here。

😊，If I do let y equals 3 in4 n plus y， this y is not in scope。

 right because I said let y be a thing only in this expression。😡，对。So let's rewrite it。

 So the point is， what I wanted to do is you can write if came mod2 equals 0， then。

Do a let binding to declare this half ends variable that's equivalent to fast power of N K div2 Okay so now I bind it to a variable。

 so now I can reuse it without writing it in line twice。 Allright。

 so I'm going to say half ends times is half ends。 And if you were paying attention。

 this is equivalent to that。 So this is exactly the same code as what I wrote before。

 Why because referential transparency It's pure。 So now we have at maximum1 recursive call to fast p And what I wanted to do was I wanted to prove to you in the next few slides is a proof that like they equivalent。

 I'm not going to have time to do that， but I will have time to show you because if we look here。

 this is the same fast pal I just showed you the one that makes one recursive call。

 We saw this p2 come of 50， which does you know ungodly things。😊。



![](img/8c8904319d292851c0f31f5c3c3501b0_13.png)

Right let's comment that out and try it out。And then， now。Very fast， right， I。

 I'm not gonna step through everything for you， but basically look at this。 Like， we're taking 25。

 and then we have 25-1， and then we have 24。 and then we have。12。12 is here。

 And then we divide by 2 is 6。 basically， if you follow it through。

 you're gonna find that like we're going to be doing less work overall。

 we have and you can see that it takes less time to step through。

 So that's basically what I wanted to show you。 We don't have time to getop What the heck， Okay。

 We don't have time to get to the proof at the end。 But I recommend you look through it on your own。

 This is an essential equivalentence proof that proves that two implementations on the same。

 I can prove to you that power and fast p do the same thing。 modular alemma。😊。



![](img/8c8904319d292851c0f31f5c3c3501b0_15.png)

系。I didn't prove those faster。Three weeks。Three weeks， we will prove that is faster。 Yes。

 you can indeed， yes， please do this lecture survey， it helps me wait T years， you know who one。

Yellow one， good job。Who' who's in yellow， Who's in yellow。I got more high shoes。

 I got more high shoes。Ylow。😊。

![](img/8c8904319d292851c0f31f5c3c3501b0_17.png)

Yeah。H。