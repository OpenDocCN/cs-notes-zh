# 卡耐基梅隆【中英⚡离散数学｜21-228 2023, Discrete Mathematics】 p18 P18 -BV1sFibBkEj7_p18-

![](img/25e5bdfb4e52a50f3a947044f3e66b94_0.png)

Hello everybody。 How are you， I decided to try to be on time today。 So let's go ahead and start。

 and we want to talk about this generating generating functions idea。

 Last time we were doing something where I lost my pen。 here it is。

 Last time we were doing something where we managed to figure out interesting expression for for the two term linear recurrence somebody commented I got a haircut。

 Yes， I think the more appropriate thing is not nice haircut。

 but it's at least you don't have to stare at that horrible like ridiculous hair that used to be there。

 So anything is better than that。 But anyway， we were doing something with this like Fibonacci recurrence。

 and we found out that oh， you can use these things called generating functions。 Okay。

 now let's go and use this to get a general form for like how you could solve these linear recurrences。

 All right， so let's just dig right in。 So now last time we did something with the exact Fibonacci。

 And so with that we were able to talk about these precise numbers。 but now let's do it in general。

 And what they want to emphasize here is that it's going to look actually like what we're doing。😊。



![](img/25e5bdfb4e52a50f3a947044f3e66b94_2.png)

Easier than this stuff we did with matrices。 but unfortunately， the reason why I used the matrices。

 Well fortunately， the reason why matrices are first is because they are like rock solid and rigorous。

 And there are some points in here that will be a little bit funny sometimes okay。

 let's let's remember where we are at。😊，Suppose we have AN equals a times capital A times A n minus1 plus capital B times A n minus-2。

Alright， so that's our goal。 We want to be able to solve these things。 And the idea was， oh。

 let's go and create some kind of a generating function。 We let。😊，F of Z。To be equal to a 0 plus a1。

 z plus。A 2， z squared plus dot， dot， dot。And this is this thing called the generating function。

Which is sort of like a zipping together the sequence of the the sequence， like the a 0， A1。

 A2 and so on。 together with these different powers of Z。 It's like an infinite power series。😊。

I actually use the word zip。 and then I just realized that in Python。

 that's actually what it's called。 I think that if you zip two arrays。

 you sort of end up comparing combining them pair by pair。 But anyway。

 so we're doing this zip zip of these two things。 And the the important thing is it's a little bit fishy。

 What does it really mean to evaluate， right， Because you see。

 there are sometimes when if you look at the Fibonacches。 Like this is a really weird sequence。

 this this generating function。 What is F of one for the Fibonacci sequence。😊。

If I decided to take the Fibonacci sequence， which is a 0 is 0。 A 1 is 1。 A 2 is 1 and so on。

 And let's plug in one， What do you get。Oh oh。You get something like infinity thing。

 which is the same thing you get if you plug in like 5 and don't even try plugging in like -3。

 Like what happens with -3。 Well， it's。I's horrible because if you plug in a negative number， right。

 all the coefficients are positive。 and you're gonna to be like flinging back and forth in these like crazy。

 positive and negative directions。 Is it plus infinity or minus infinity。 it's none。

 It doesn't even converge。 So that's actually why this is a little bit weird。

 We're only going to be doing stuff where we write this stuff down and we do things that seem like they might make sense。

 Okay， and that's why I gave the linear algebra thing earlier。 But anyway， it's。

 it's pretty efficient that， I quickly finding out formulas。

 So now I've gotten this for the Fibonacci sequence。 Sorry for the。

 I've gotten this generating function for the general general recursion。 So now let's proceed。

 What do we do， Can we try to use the same ideas that we had with the Fibonacci。

 Can someone tell me what I might want to do with this。😊，I'll know that F of Z equals。

 We need to take some step。 What do I do。Just feel free to type raise hand in the chat。Brayden。Yep。

Yep。So， that's good。I'm just looking for patterns here， and I'm always using columns。

I like arranging my stuff in columns because I can see what they mean。 So if I look at this column。

 for example， that's just going to be the z squared coefficient。 And I have the a0 plus a1。 Yeah。

 that's a2。 And the next one is the Z cubed coefficient。 I have an a1 plus A 2。 Y。

 that's a 3 And it just keeps going。😊，And exactly， as Braden said。

 now we go and identify that we have some kinds of now we go and identify that we have some things that have Fs in them。

 Can someone else help me， I want to make sure that everyone's on the same page here。

 What's this top one， Someone else， What's this And is's sort of like F， but not really。Wait。

 I screwed up。 It's not Fiubbonacci。 Oh， no， this is wrong， wrong， wrong。 You need like A's and B's。

Sorry， guys。 these As and V's here。 This is just wrong。 It's not the Fibonacci sequence。 Okay。

 I'm going to go and erase this because I want some more space to write it properly。 I。

 I was writing it for Fibonacciches， but it's not。 So actually。

 what's going on is that it's going to be capital， Oh now have to be careful。

 Is it capital A or a capital B。 Can someone help me up。

 I want to make sure everyone's on the same page。 I want the first row。

 The first row is going have something times a 0， Z squared， but there's something in front。

 Is it capital A or capital B。😊，Which one。We got somebody with an A。Okay， so if I look at this。😊。

but yeah， some those be。So what is it， It' it A orRP。Okay， so now we have the two two votes for B。

 So we're just going here。 So it's actually going to be B。 because if you look at what's going on。

 it's going to be B times the thing that's2 before。 And don't worry if you got it wrong。

 because I was about to write an A there。 Okay， I was about to， well， okay。

 I didn't even write anything there。 That was totally wrong。 But anyway。

 the other thing is that then you have an a capital A times an A 1 Z squared。

 And the way you can see this works is you just kind of focus on one of these columns。 Yes。

 capital A A 1 plus capital B A 0， But look at this thing is's gonna give me little A2， okay。😊。

And then I have another B。Plus， B， capital B， A 1， Z cubed。And so on。

And the other guy is plus capital A。Little a2 Z cubed。And so on。Now， can someone help me。

Figure out what this top thing is。If you raise hand， I'll call on you。 And what do we write here。

Christopher。Okay， you said F O Z。Times B， Z squared。Just staring at that。 I'm like， yes。

 there's definitely a B that comes out because the F of Z had no B。 And indeed。

 it F of Z would have started from a 0 with no Z's， but there's two extra Z's。 So that's good。

How about the second one。What's the second。啊，charles叫charlie Charlielie。D out the。

Subtract out the a n term。 How do you want to subtract out the A n term straight up just like this。あ。

Yes， a not times A Z。 you know what。 this actually works。 Yes， this is good。

 So are people okay with this is like this thing here would be， yes， it looks like I just get an A。

 and it looks like I upgrade all the powers of the Z by one。 That's true， except that if I did that。

 I would need one more term， which has the a not times capital A times Z， which is missing here。😊。

Right， because it only starts from a1 times capital A times Z squared。 So that's okay。

 We got the right hand side。 We got the left hand side。

 So now I need to just go and solve for F of Z。So I have F O Z here。

Of F of Z there and a F of Z there。 These are the three things I'm putting in boxes。

 because that's what I'm trying to solve for。 And I can just like put all the F of Z stuff on one side and put all the non f of Z stuff on the other side。

 And once you put all the F of Z stuff on one side， I'm going do a factoring on this。 if I do that。

 all the F of Z stuff throws onto one side。 And over here， I got。😊，Over here， I got。One of them。

Minus。呃。Capital A Z。Minus capital B， Z squared。That's how many F of Zs I get is equal to。

 I'm gonna write a box around the F of Z。Because that's what I've factored out， okay？

If you can see what I just did， I just went and grabbed everything which has F of Z。

 I shoved them all to the left side。 The initial F of Z。

 That's the one because that's times the1 over here。 I have to have the， you know， B， Z squared。

 but I move over this side。 So it gets a minus sign。 That's why it's B Z squared， minus B Z squared。

 And over here， I had an A Z。 So when I move over here， It has to have a minus sign。

 minus A Z equals some stuff。 what's left。 So I have a 0。😊，Plus。😊，A 1， Z， I'm with the factor here。

 A1。 minusus。A 0， A capital。See， I think。Hopefully， I didn't make a mistake。

Which is possible to happen。Looks good。 Look good。 Okay， so I think this is okay。

 So I have this thing here。 I have the FMC with factored stuff is equal to some other stuff。

 And so what you do is you then just say， okay， then I can divide out this stuff on the left。

 And I got FMC。😊，F of Z。Is equal to。Well， it'll be some number。 Blob math returns blob。plus。

Some other blob Z。Divided by now， these， I'm not going to leave as blobs。 I actually want them。

 A 1 minus capital A Z minus capital B， Z squared。The reason I put blobs on top is because I'm not actually going to care too much about those。

 because what's the main technique we used to go and take this and try to find the coefficients？

Partial fractions。 Yes， thank you very much， Trisciia。

 So since we're going to do partial fractions anyway， the important thing is if you look up here。

 there's no z squared power。 And so since everything here is a polynomial of degree less than 2。

 then when I partial fractions it， it's going to end up being blob math returns。

 It'll be like blob over。 Now， the partial fractions we're going to do is1 minus blob Z。😊，Plus。

 blob over 1 minus blob Z。That's our goal， right， Our goal is to take something like this。

 and we have to go and figure out what the blobs are。

 but we're going to use the only things we're going to really need are actually these these capital A and capital B。

 because that's how you factorize the denominator。😊，Okay， so now we need to find these bbs。

 By the way， I just want to talk about why we're doing this。 The reason we're doing this。

 there was somebody who stayed afterwards last time and asked a very deep question。

 which I want to highlight to everyone。😊，You know， we were going to somehow say。

 I'm going to write another power series to represent F of Z。

 I'm going to use this information to say， oh， by the way。

 F of Z can also be written in this way with all of these coefficients for all these powers of Z。

And that person asked the deep question。 How do you know that the coefficients of the new power series that you wrote just so happened to match the coefficients of the previous power series that you wrote。

 And the answer to that is actually that's from complex analysis。 This is this is deeper。

 deeper stuff。 And so that's what I mean by this is like we don't expect this class to explain the heart of that piece。

 which is why we did the linear algebra。 But it is true that for the principles of what we're doing in this class。

 There are ways to go and explain why just because we got some coefficients here。

 And we started with some coefficients， which were just the original recursion。

 That's why they match。 it is not the same as saying if I have two polynomials。

 which match all the values， then the coefficients match。

 polynomials are easier than infinite power series。😊，And also。

 you may be wondering what kind of crazy person uses Z as the variable。 Doesn't everyone use X。

 The answer is because to me， these are all complex numbers。 because in my head。

 that's actually how I think about the theory for why you can match these things。

 Complex numbers are just better than real numbers。 Okay， They're just better。

 You can't square root a real number， but you can square root every complex number。

 Complex numbers are where you can do all of the polynomial arithmetic。 They are far superior。

 It's just that usually they're complex。 And so people are not comfortable dealing with them anyway。

 So Z， if you do complex analysis is the main letter for complex variable。😊。

The reason is because Z usually write as x plus Y I。 And so you need to have some other letter。

 Anyway。 So that's why it's the Z。 And and I I I you'll see me use Z everywhere here。

 because that's my knee jerk reaction。 If you read other books on generating functions。

 they usually will use an X。 But I prefer Z because it's a complex number。 Eric。

 you had raised your hand。 where you're trying to answer the partial fractions。

 So do you have something else you wanted to add。😊，Are you saying like these blobs。

 which are here in the denominators， You're asking like， are they like the factors。

 Is that what you're saying。I think we're having a little bit of trouble hearing you。

 Can you get a bit closer to your microphone。こた。Oh， oh， you're like。

 what if you can't factor it like， for example， what if when you try to factor it。

 your roots are like 3 plus or -2 I。 That's why I use complex numbers。The only place you did。

 You did get on something， by the way， What if there's a repeated route， We'll see that today。 Okay。

 so， so actually， there's a， there's a problem here。 This actually doesn't always work。

 Thanks for bringing it up。 This is like。😊，Only。If。No， repeated。Root。Now， what do we mean by root。

 I haven't even talked about what a root is yet。 We'll have to talk about these things。

 These two blobs， it should feel very similar to what we had been doing of this like issue of repeated roots that we had before。

 Also， when you look at this， you should be like， my gosh，1 A Z minus B Z squared。

 that looks like it must have something to do with that polynomial we had before。

But if you look at this， this is where it was a little bit fuzzy。 Last time when we dealt with this。

 we were like， oh， no， But when you actually go and figure out what the roots are of this thing。

 they weren't the they weren't the golden ratio。 It was like a little bit off。 And then in the end。

 we took the reciprocals of them。 And that's actually what I'm going to show you。

 I'm going to show you why in this particular factoring。

 It just so happens to match with this reciprocal business。 So again。

 the roadnap of what we're doing is like， oh， great。

 this is the generating function for that recurrence。 Great， so I could， in theory。

 partial fractions the thing out。 And then we're gonna to compare coefficients。

 We'll do that in a moment。 But first， let's go and decide how I would find these two these two roots。

 They're not eigenvalues。 These are roots of like some polynomial here。 Okay。

 so let's think what would partial fractions require。

 partial fractions means that I need to find a factorization of this quadratic denominator。

 in terms of1 blob Z times 1 blob Z。 That's what I actually what， right。

 I want to factorize this guy。 In terms of1 blob z times 1。😊。

That's not how you usually factorize things。But our goal， in order to do the partial fractions。

Go for partial。Fraactctions， actually， the goal is for partial fractions。

That give infinite geometric series。Thatt give。Infinite。Geometric series。Right。

 in for the geometric series。 that was the one over like。1 minus blob times Z。

 That's an infinite geometric series because that's like one plus blob Z plus。B squared the squared。

That was supposed to be a squared。Plus do do。Right， that's what I want。

 I want to get this infinite geometric series。 in order to do that。

 What I need to do is I need to be able to show that 1 minus capital A Z minus not no I don't need to show。

 I need to find a way to express this as1 minus。 Oh， let's give these some names。

 Let's call them Lambda 1。😊，Zi。Times 1 minus lambda 2， Z squared。Okay。

 lambmbda is just used because I guess that's， that's a nice Greek letter。

 but this has nothing to do with linear algebra anymore。 there's no matrix involved。

 It just there will be a correlation with that。 So does anyone know good ways to solve for Lambdas。

Oh， what's this。Shouldn't it be Z。 Oh， no， Did something go。Shouldn't be Z， not Z squared Oh。

 probably because I screwed up。Did I scrub up。And might have screwed up。Whoa， whoa， whoa。

 what is this。 Okay， yeah， yeah。 that's wrong。Thanks， guys。 Okay， thanks guys。 very helpful。😊，Okay。

I am very liable to do these kinds of things。 So thank you very much for jumping right in。😊，Okay。

 now does anyone have any good strategies for how you might figure out the land this for this。Well。

 you could just like compare coefficients and solve stuff。 right。

 one way to do this is just called foil the right side out。 And if you foil the right side out。

 you go and got some， you got some equations about lambdas。 Do you know what， I mean， you could。

 in theory do this。 You could just like foil this thing out。

 And just to show you how painful that would be。 If you foiled it out。

 you'd end up getting1- lambda 1 plus lambda 2 times Z。 And then plus lambda 1， Lada 2， Z squared。

 And then you'd like solve systems of equations。 You'd be like， okay。

 so now I need lambda 1 plus lambda 2 equals capital A。

 And I need to have lambda 1 Lada 2 equals negative B。

 And then you go and try to solve this whole thing。 that's one way， don't do it。 It's painful。

 And not only does not only is it painful。 It doesn't reveal the magic。😊。

There is something really interesting about where these lambmbdas come from。

 The better way to do this is to say， look， if I want to get that。

Let's divide the whole thing by z squared。 It's the same。 Of course， you might be like。

 what about dividing by 0， But in this section， we're doing all kinds of crazy stuff。

 We're taking sums of things to infinity。 We're dividing by 0。

 We are like just messing with things that should be true。 And that's giving us a heuristic for。

 for what might actually be the recur the solution to the recursion。 So let's divide by z squared。😊。

And if you wanted to make it rigorous， you could effectively。

 This is adding what's called a removable singularity。

 And so all of these things that I'm doing can actually be made rigorous。

 but we're not going to do that in this class because that goes way out of the scope。

 But you know what happens when you divide the other one。 You get one over Z minus lambda 1。😊。

Times 1 over z minus lambda2。Okay。不。Whoa， yes， you're right。 Thank you very much。Okay， good。

 And then I can write a bigger B。Thank you。 Thank you again。 Okay， please catch all these things。

All right。So if I have this thing， now what？ Well， I have， first of all， do you guys agree。

 it's like the same， except for this like divide by 0 thing。

 But the reason I say it's a removable singularity is because， look， it。

 if it was true for like all the values of Z except 0。Then， then it should match。 It should be fine。

 if I， if I managed to find a lambda 1 and lambda 2 so that this guy was true， then， of course。

 that has to work。 And that's what I mean by complex analysis， lets you fit this in。

 And I strongly recommend taking this class at some point， iss really interesting。Okay。

 why did I bother to do that， makes it look worse。 Well， sort of。I'm going to make one small edit。

 and I'll write the one over Z parentheses squared。嗯。Actually。

 I'm gonna change the color of the one over。😊，I'm gonna call the one over Z。 this blue thing。

1 over Z is in blue， Okay， and we'll write times one over Z。And over there on the right。

 I'm going to write one over Z in blue。 If you're taking notes， don't worry。

I'm just trying to do this for the visual observation that something interesting is going on。

What have I just done， What was the point of that， Why am I making them blue， Chris。

I made it into a quadratic。 This is a quadratic in one over Z。 Can anyone extend this。

 This is actually a very exciting point you have just made。

 Can anyone extend this a bit more and tell me about Lambda 1 and Lambda 2。😊，And， of course。

 you have a hint， which is called。 We did some linear algebra stuff。

 So we actually know what lambda and 1 lambda lambda 2 better be， because like， that's like the same。

 it will be the same thing， a braon。😊，找一个。Yes。😊，Oh， let's go and use the same blue。 Okay。

 so I'm gonna make the， okay， we call it X Now。 that's fine。 I actually do that in my， my own thing。

 too。 So it's x squared minus a。😊，X。Minus B is equal to。X。inus lambda 1。And then， the same X。

- lambda 2。You've seen that before。 That's called factoring a quadratic。 So effectively。

 what we have just found out is。So the lambda 1 and the lambda 2 are the roots。

Of just the plain polynomial x squared。Oh， let's call it lambda。 Okay， I shouldn't you know what， I。

 I like lambmbda better。 We'll just call it lambmbda。 Lambda squared minus A lambmbda minus B。😊。

Where have we seen that before？That was the thing we just had。

 That was the thing we call the characteristic polynomial。 It's like the exact same thing。

 and of course it should be because you can't have like different bases of the exponentials for your solution for this for this recurrence。

 right。😊，That's the same characteristic polynomiala。Okay， so now I've just， you know。

 we just went around and we just found out that the way you solve the general two term linear recurrence is let's hope that I get two distinct roots for the characteristic polynomial。

 And if I do。Then but now let's go and stare at our generating function with the partial fractions。

Okay， so remember the entire point of this was to make it so that I can write my generating function as the sum of two of these guys。

 which is like blob， which is a number that has nothing to do with N。 is's just some constant like。😊。

1 over Ro 5 or something。 It's like blog over1 minus， and now that's going to be lambda1 z。Okay。

 so let's continue on。 And what I just found out is。F of Z， continuing from where we were before。

Well， that was blob plus blob Z。Divided by 1 minus a z minus b z squared。

 and we have just found out that you can rewrite it as1 over sorry。

 blob over1 minus lambda 1 z plus blob over 1 minus lambda 2 z。For some blobs。

Which are independent of N。Okay， that should look really familiar。Now， if I knew that， actually。

 in this particular， Oh， another thing is like， why does partial fractions always work。 Well。

 it actually works。 If you want to prove why it works。

 is's related to this thing of like actually goes back to linear algebra because then if you want to figure out what the blobs actually are。

 You solve some equations。 You would actually use these blobs。

 And those are like the outputs of what happens when you try to put this thing over a common denominator。

 Like you guys remember this from calculus。 you put it over a common denominator。

 multiply the bottom stuff， you get like blob times 1 minus lambda 2 Z plus blob times 1 minus lambda 1 Z。

 equate coefficients against the blob plus blob Z， figure out what the blobs are。

 So you could figure it out if we wanted to。😊，And the reason you can is because the lambda1 and Lada 2 are distinct。

 That's actually what's important。 If you have Lada 1 equals the lambda 2， good luck， it won't work。

 right， Because if lambda1 and lambda 2 are the same， it's really obvious now。

 don't need any linear algebra。 It's like just kidding。 You just have blob over 1 minus lambda Z。😊。

There's no way that's going to have this quadratic thing unless for some odd reason。

 it just so happened that this guy was factorable。 And one of the factors like， was that guy。Okay。

Okay， so now we did this and actually over here， just for the sake of explaining this。😊，Here I。

 I do I have less like blob math that I than I needed for the for the matrix stuff。

 So I'm already gonna give names for these guys。 I'll call it alpha and beta。 Okay。

 so I'm already gonna replace those blobs as alpha and beta。 So I'll just say， okay。

 let the blobs be alpha beta。 Let blobs。😊，Be alpha and beta。 Okay。

 And what I just found out is that F of Z is equal to alpha over 1 minus lambda 1 z。 Okay。

 I'm going to use two colors now， plus beta over1 minus lambda 2 Z。

 I'm using two colors because I now want to go and write these two things out as infinite geometric series。

😊，Okay。So， the first one。If I have alpha over this， that's actually alpha。 Well。

 that's it that't an infinite geometric series。 That's like alpha。 What is it minus。Alpha， no， plus。

 plus alphapha lambda 1 z。Plus， alpha lambda 1 squared。 Z squared。 plus alpha lambda 1 cubed。

 Z cubed。And so on。That was a three， cubed and so on。That's the green thing。

 Is everyone okay with the green thing。I'm gonna to write a plus sign。

 So you know that there's more coming。 Everyone， okay， without that being the green thing。

 This is an infinite geometric series， first term divided by  one minus common ratio。

And so what I end up getting is the。First term。 And then this always got that first term。

 And I keep multiplying by the common ratio。 Common ratio is lambda onezi and then another lambda onezi and another lambda onezi。

 and it goes on forever。And if I do the second one。The same， just with a beta。

So I get beta plus beta times lambda2 z。Plus， beta。

Times lambda 2 squared Z squared plus beta times lambda 2。Cubed， Z cubed。Plus dot dot dot。Okay。

Now what？ Well， now I can actually go and find out what the coefficients are for each power of Z。😊。

So， that's equal to。I have alpha plus beta。Times z to the0。Plus。

 my columns aren't really lining up that well。Well， can I， I guess yeah， they're not。

 they're not lining up so well。 So it's just gonna spread out。

 And so the next one is going to be alpha lambmbda 1。Plus， beta。Lambda 2， these。Plus。

 alpha lambda 1 squared plus beta Lada 2 squared z squares plus dot dot dot。

So here's this step that one of the students pointed out。 Hang on a second。

 So I've just written F of Z。As this infinite power series。

How did you know that that means that the first coefficient matches the first coefficient I had before。

 Because let's write the recall。That F of Z is also equal to a 0， Z to the 0 plus a 1。

 Z to the1 plus a 2， Z squared plus。And the important thing is， well。

 we're going to equate the coefficients because。😊，And now， of course。

 the reason why this is still useful is because if you manage to use these generating functions to go and find the recursion and find a formula。

 you can actually， in theory， prove that the formula works just by induction。

 So we are not even cheating。 It's one of these things where we say， well。

 here's the solution to the recursion formula。 And you could just say。

 let me prove the formula by induction。 P in the first three values observed that it satisfies the recursion thing from I can get the n plus one term from all the previous ones and you're good。

😊，For this class， I won't even ask for you to do that on the exam。 In fact。

 I'm okay with people doing this sort of thing being like equate the coefficients。 It probably works。

 That's actually how a lot of mathematics was done a long time ago， too。

 So it's not like not like you're being any worse than the mathematicians from like a few hundred years ago。

😊，Okay， so so then now we equate all of these things。 And now we just found out that， for example。

 I got that a2 is equal to alpha times lambda1 squared plus beta times lambda 2 squared。

 the punch line。😊，If so。For all N。Well， in this particular one that we did， it's for all and。

 which are in。0，1，2， and so on。What I found out is that a sub n is equal to alpha lambda1 to the n plus beta。

Landda， too， to that。Very satisfying。 That's exactly the same thing we got when we did our eigenvalues。

 when we， when we did our matrix multiplications。😊，So I'm going to pause here。

 Does what we've done make sense？We just took the same thing as one over 89。

1 over 89 had concrete numbers that we played with。 And after we played with those concrete numbers。

 we were able to go and say， okay， great。 Now let's do it with like brand like these variables instead。

 Once you have variables instead。 actually， the transformation part that the key part is actually quite easy。

 It's just called， I don't know what I'm doing。 Therefore。

 all I'll do is replace all the values with the things from before。

 That's the only thing I know anyway。 put them in there。 align with the columns。 So you see patterns。

 find out that， oh， dot dot dots。 I don't like dot dot dots。 I suck that all away。

 That's something with F of Z。 suck that away。 That's something with F of Z。

 Sudden no more dot dot dots solved for F of Z。 get this。 What do you do with this。

 I don't want to take derivatives。 But if I partial fractions。 I'm in good shape。

 because each of those is an infinite geometric series。

 The only trick that we did today that we didn't do yesterday or on Friday。 on Friday。

 we kind of brute forced this whole like partial fractions thing where we actually messed around with。

😊，You know， with like solving and getting this factored out where it was like Z minus something。

 Z minus something。 Then we took some。 we had to divide by z' in some weird ways。 And today day。

 the trick was， oh， I just want to factorize that thing。1 A Z minus B Z squared。

 If I want to factor it in this form of the1 minus。 If you just divide both sides by the Z squared。

 Then poof， suddenly， I have a normal quadratic that I'm factoring in the normal way。

 So the lambdas are just the roots of that normal quadratic。😊。

And I'm also gonna say now that you've seen this， you can imagine that if I had a three term recurrence。

It be the same。Are people sort of O with that is like， suppose I had a three term recurrence。

 Suppose what I had here is I' had a third thing。 What would happen。I would just get three rows。

 Is that okay， Like， if I had this， this and a third thing， it's like， okay， fine，1，2 and 3。

 because every single value is the sum of three things。I might have another term over on this side。

 which is not split apart。 That's fine。 But then if I look at what else happens。

 I will just get like a cubic in the bottom。 And I just have to， like， factorize that cubic。

Except that how I factorize the cubic， it will always in the be in the form If it'll actually be1 minus A Z minus B Z squared minus C Z cubed。

 It's going to be really obvious。 It's just， it's just that if you， if you， I encourage you， like。

 if you want to get used to this， Just try that on your own。

 you'll see that what' sps out is1 minus A Z minus B Z minus C Z cubed。😊。

And the reason why I showed you this nifty way of factorizing it is because it's really nice。

 What we have done here actually generalizes for that。 too。 So effectively， what we have done。

 if you just try on your own with like three terms。

 you will actually find out that you can follow every step。

 And it just turns out that the roots Lambda 1， lambda 2 and Lambda 3 are just the roots of this particular characteristic polynomial we had before。

😊，Well， then let's do one problem， which has actual numbers。

So now let's do this with another problem。 It's not Fibonacci anymore。

 I want to do it with the problem。 A N equals 6 A N-1。Plus，9， no， no，-9。-9。A N-2。Okay， and just like。

 let's make some simple things。 Okay， I just want to have like a 0 equals。0 and a1 equals 1。

 because I'm lazy。Alright， let's just do this。 Now， now， now。

 this is gonna be very carefully chosen numbers on purpose。 If you try to do this。

 what's going to end up happening？ Well， let's just do this out with these actual numbers just that we're gonna to do it fast because people will get used to this as we go。

 It's like， okay， how does this go。 F of Z is equal to。 Here comes the generating function。😊。

A 0 plus a1， z plus a2， Z squared plus and so on。Hey，3 is you cubed。And so on。

And then the next thing that's going to happen is we'll split it apart。 We got a 0 plus a 1， z plus。

Open the brace。 And， you know， this， I'm doing this because I know that this is not。

 this is usually the first time many people have seen this。

 And I feel that if you see the same thing done a few times， get used to it， this is an a 0。 No。

 it's not。 I did it wrong Again。 It's going to be -9， a2。Z squared。And。-9。A， wait， what did I do。

 Not a 2， A 0 z squared。 I get it wrong， too， A 1 Z cubed。And so on。And the second row is plus 6。A 1。

 Z squared plus 6， A2， Z cubed。Plus da。Pausing for a second。 Does this make sense。

 I'm just doing this with like no letters just because it' it's fine with no letters， too。

And you can see it works because， for example， if I look at this column， what's a2。 Well， A 2 is 6。

 a 1-9，8，0。 It works。 That's exactly what I wanted up there。Okay， let's go and make some lumps。

 So this first one。Can someone tell me what that becomes。We don't have letters anymore。

 We just have numbers。Yes， they same。Excellent，-9 F of Z times Z squared， because there's a -9 there。

 There's a F of Z， but all of my powers are off by 2。

 I have an extra 2 upgradegrade by 2 means times Z squared。Okay， the second one。

Can someone else tell me what this is。charharles呃 chalie chalie chalie。对。一。

And here we're very happy that a0 is 0， right？😊，Because like a0 is0。 So that's why I don't care。

Normally， there's some minus stuff。 but I'll just write here。A 0。A0 is equal to 0。Ye。Okay。

 that doesn't really matter。 But so I don't need to worry about the a0。

 So now I've gotten this thing where， okay， I've got a， I got a formula now。 Oh。

 and also this a 0 and a 1。 I know what they are。 So I， I finally know that this F of Z。

Is equal to a 0 is 0。 A 1 is 1。 So it's just plain a Z-9 F of Z， Z squared plus 6 F of Z， Z。I think。

All I did is I just took this equation and I actually plugged in a0，0， a1 is month。

 and I got this stuff。Okay。Then the let' just go and pull over all the f of z's onto one side。

 And that's going to give you a factor of 1 minus 6 z plus 9 z squared。F of Z。Is equal to z。

All I did is just shho all the FFC onto one site。Now， you see why I chose the numbers this way。Now。

 now we get some weird stuff。 So now I find out that F of Z is equal to z over 16 z plus 9 z squared。

 which I wrote in such a way that is actually obvious。

 you don't need to like need to do this like funny divide by z squared thing。

 Maybe you see the bottoms a perfect square。😊，The bottom is 1-3 Z。 whole thing squared。Oh， oh， no。

My whole， my whole like thing broke because I wanted to do。

 I wanted to do like this partial fraction thing because I like to have one over1 something times Z。

 I know what that is。 That's an infinite geometric series。 What's this。 Oh， well， you know。

 you just write the infinite geometric series and you square it。😊，Oh， no。 that screws up all of your。

 all of your coefficients。Do you know what I mean， It's like。

 if I try to write down 1 plus 3 z plus 9 z squared and so on。 and then like multiply that by itself。

 you could do that， but it's a mess。So now I have trouble。I guess I should just go take derivatives。

No。That would be very painful， too。 I don't want to just go and take like tons and tons of derivatives with this。

Instead， there's something else we can do。So instead， if I look at this thing， it's like Z over this。

Well。Actually， it turns out that derivatives are related。Let's look at 1 minus 3 z。

And then1 over 1-3 Z。 And I went with squared， okay。We'll do this in two different ways。

 We'll start with one way today and willll continue with another way tomorrow。

 or we might do both today。 Let's see。So my big question is。What。😮，Is a formula。For the coefficients。

Of z over 1 minus-3 z， whole thing squared。That was a script。

That's the deep question we need to answer now。Well， let's start by asking an easier question。

Too hard。So here's an easier question。How about。Let's let's call it G now G of Z。

 which is just plain1 over1 minus3 z。Oh， that's easy。 That's the sum of the geometric series。 Okay。

 I know what that is。 Well， that's G equals G of Z is equal to1 plus 3 Z。😊，Plus， 3 squared。

 I'm going to write it as three square Z squared。 We want to find some formulas， plus3 cubed。😊。

Z cubed， I mean， I want to find some patterns plus 3 to the fourth。

 Z to the fourth plus 3 to the fifth， Z to the fifth and so on。 Hopefully。

 that's enough to find a pattern。Now。Does anyone know a clever way to turn something like 1 over 1-3 Z into something like 1 over 1-3 Zs whole thing square。

There is actually something I can do。I can do something to both sides of this G of Z。😊，Oh， oh。

 just a second。 G of Z is equal to。 Let's put this over here。 The G of Z was this1 over1-3 Z。 Okay。

 I'm just like making using the fact that the equal sign is like transitive。 Okay， so I have this。

 There's something I can do。 Oh， yeah， I saw some ideas。 So I saw Bradn had raised his hand。

 And we got some people saying derivative。 Yeah， and there's this one third。 We'll find out soon。

 So what we can do is we can take a derivative。 Let's derivative both sides。 Yeah。

 that's called differentiate。 So we have a verb for derivativeing。

 but we don't have a verb for determining。😊，But so， so what we do is we。

 we take the derivative of both sides。Derivative。With respect。To z。Okay， and in in general。

 when we're doing this stuff with generating functions， just be like。

 if it seems like it should be legit， it's fine。 Things that are not legit are things like 2 plus 2 equals to 5。

 That's not very legit。 But things like， let's just take the derivatives of both sides。 Yeah。

 seems reasonable。 So if I do that， what happens to the left side 1 over1-3 Z， actually is nice。

 It becomes by this。😊，What chain rule think，1 over 1-3 Z。

Whole thing squared and then times a negative3。 No， no， no， there's a minus in front， too。

 I think it's been a while since I took calculus。 Am I right， Is there a minus sign wrong。

 or is this okay。Think this is okay。Because it should be minus the thing over the thing squared。

 Yeah， times the -3。 I think this is okay。 That's the left side。Equals。The right side。

What happens when you take the derivative with respect to Z on the right side？

 Anyone see an interesting pattern。What's going on。

And that's why I wrote all of these as like three squared，3 cubes，3，4，3 to the fourth， and so on。

What's the pattern， Is there anyone else， I want to see if there are other people I can bring into this。

I'm I'm basically curious， is there a neat pattern for the n coefficient。

 like the coefficient of Z to the n good address。Okay， I heard an n in the front。

 I heard a3 to the power one less than that。 And I heard a Z to the power。 Okay。

 and so let's do that with this and we'll look for that pattern。

 So the key is that the first interesting thing happens with this three。😊。

That's the derivative of 3 z。 The next one is when you take the derivative of 3 squared Z squared。

 I can take the two from the Z squared， two times 3 squared z。😊。

Then the next one is the derivative of z cubed is 3 z squared。 So I'm going to put a3 in front。

3 times 3 cubed Z squared the3 to the fourth Z to the fourth。

 Then I can take the Z to the fourth becomes 4 Z cubed。 So I get a four times。😊。

3 to the fourth Z cubed。 And now I ran out of space。 Yeah， and so I dot， dot dot。

And so what you said is it looks like。The coefficient。Of Z to the power。 Well。

 we care about the coefficient of Z to the power N。I。It's pattern time。 If I look at the patterns。

 I'm like， it looks like if I have a Z to the power N， it looks like I get an n plus1。Is that okay。

 I get an n plus one。 and then times。3 to the power， n plus one。I think。Yeah。Let's separate this。

Are people okay with this？ So the coefficient of Z to the power N is going to be n plus1 times3 to the power n plus 1。

Okay。So what？ Well， I actually care about this thing。 This is Z over 1-3 z squared。

 Can someone help me finish this？ I want to get the nice expression for all of these coefficients。

 What could I do。😊，I want that one Z over 1-3 z squared。Jack。

It looks like if you multiply like the left side。Yeah， exactly。 So two negatives make a positive。

 And so I just have a3。 and I want a Z instead， right， So let's just go and multiply。😊，Both sides。

By Z over 3。And what you end up getting is exactly Z over。

1-3 Z whole thing squared is equal to What happens when I do that。 I'm a pattern guy。

 Let's just go and do it。 And， of course， if you， if you prefer things of like the anth coefficient is whatever you can do that。

 too。 But as a pattern guy， what I see is I get to get Z。Multiply by Z over 3。 So I got Z。Plus。

 two times 3 to the power 1。Z squared。Plus。Three times 3 to the power 2 Z。Cubed。Plus， four times。

3 to the power 3， Z to the fourth。Plus， dot， dot， dot， run the space。Okay。Interesting。

Does this make you happy？What are we trying to do， We're trying to find a sub n。Aren't we。

 We're trying to find a sub that。But remember， this whole thing was my generating function。

 That's F of Z。So now I should in theory， know what is a sub N。I get to compare coefficients， now。

First of all， are you happy with the way this starts， This starts with no constant term。

 Is that good or bad。I mean， like， come on， this is a weird polynomial。 Why。

 why don't I have a constant term， Shouldn't I have a constant term。

 Most polynomials have a constant term。Yes， is saying。 That's right。 It's because a 0 is 0。 So。

 of course， you better not have a constant term because this is supposed to go and match a 0 plus stuff。

 And that's good。 Good。 There's no constant term。😊，Is anyone happy with the Z， What am I pointing at。

 I don't even know the Z， Is anyone happy happy with the Z。Is he good。What is that a smiley face。

 That's good。 I like it。 So Z is good because a sub 1 is one， right。

 So that's what you exactly what you want。 And then little bits of us should be like。😊。

Do we believe the rest of the formulas， Because it looks like we just found a nice formula， right。

 it looks like。Not just looks like it is。 Okay， so， but I'll just write comparing coefficients。

Comparing。Coics。A sub n is equal to， can you give me a formula for this a sub n。What would this be。

This is why I like patterns。 I just write enough things。 If you see enough things。

 you totally can see the pattern and you won't ever be off by one。啊，bden。よえ。N times 3 to the n -1。

 Do we buy that。 Let's go and find out。 Okay， so like the the moment of truth is n times 3 to the n -1。

 really， A N equals n times 3 to the power n-1。 We could prove this with induction if you wanted to。

 We don't。 We will never need to do that in in this thing， but。😊，The question is， does it work？ Well。

 remember what we had was A N is equal to 6 A N-1-9 A N -2， right？

 So let's go and make a bunch of terms。So a0 is equal to 0。 A 1 is equal to1。

 A2 is equal to6 times the previous-9 times the previous previous。 That's 6。A 3。

Is equal to 6 times the previous， which is 36-9 times the previous previous， which is 27。A4。Okay。

 I'm too lazy。 I'm not gonna do any。 So， so， so， so I did the first three。 I'm。

 I'm already satisfied because the formula I wanted was n times 3 to the n -1。 And like。

 if I look at the a2， that was one moment of truth。 two times 3 to the power 1。 totally right。

 And this looks totally like three times 3 squared。 And the lazy is probably right。 Okay。

 so we didn't screw up。 Actually， whenever you use generating functions or something。

 I strongly recommend， you actually try a few values， it's very easy to just like make a mistake。

 Obviously， you see me make lots of mistakes。 But if you can match a few， it's gonna be fine。😊。

All right。 So this was one way of dealing with this repeated root。

 Because what you actually had here， if you went and used this ABC， A， A B thing。

 there was some A B thing， If you went and wrote this characteristic polynomial。

 that would have been 1-6 x。Plus， 9。Which has a repeated root， not two distinct roots。 And suddenly。

 with the generating functions， we have found out that we have a secret way that can knock into this weird partial fraction type of decomposition。

 wherever a square。 And the way you deal with the square is you use the fact that I know how to do it with no square。

 So you take a derivative。 And if you know how to do it with no square， take a derivative。 It's like。

 oh， look at that。 Some the powers of Z。😊，Shove down into the front。

 So I get some interesting behavior。 It's not just like a constant times 3 to the power N。

 The previous stuff we had was like blob times lambda to the N。 Suddenly。

 this is not a blob because this has an n in it。 It's n times 3 to the n-1。😊。

Which you could also write us one third and times 3 to that。Okay。

 so that's what we saw today next time on Wednesday。

 we're going to go deeper into this and actually give a general form for how to solve every homogeneous。

 linear recurrence in the world。是有的。Thank you。 yep。



![](img/25e5bdfb4e52a50f3a947044f3e66b94_4.png)