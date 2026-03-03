# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P17：-17-Advanced Algorithms (COMPSCI 224), Lecture 18.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/19a15c787940d783b2d5fdf1f66197fe_0.png)

Okay， I guess I'll just get started。🤧。So yesterday I gave you the outline of Inter point and then I started。

Discussing。诶。Some optimization tools such as gradientding Descent， which is a first order method。

Meaning that it has access to some function F as well as its gradient on any query point。

And we'd like to minimize the function F。Today I'm going to tell you about a second order method。

 this is called Newton's methodod。And Newton's， in the second order method。

 you're not only allowed query access to the function and its gradient。

 you're also allowed query access to the hessian of the function。ok。

And I will show you an analysis of。Of Newton's method that will be relevant for， for interior point。

 Okay， so just a recap。嗯。Some things I want you to remember， so our goal of Interior Point was。

To minimize C transpose x， such that Ax is at least B。Any LP can be written this way。And we。

Repeatedly。Approximately minimized。F of lambda。We're F lambda x。

Is defined to be lambda C transpose X。Minus the sum arguinggling from 1 to M。Of lawn， of slack of X。

Where。The slack vector。Is defined as Ax minus B。So we're going to use Newton's method。

To get better and better solutions to F lambda。I want to tell you a little bit about New's method。So。

Second order。Optganization。second order methods。We want to minimize。Some function。F。

 which maps Rn to R。And we are given。Orracle access。To F。The gradient of F and the hessian of E。

And what I mean by that is give it a point x。There is some way for us to get our hands on F of x。

 the gradient of F of x and the hessian of F of x。🤧嗯。So as usual。We start。With some。Initial。呃。

Excell it。Let's say NRN。And repeatedly。Apply。Some update rule。

And what we want to understand is how much does our error decrease as we do some number of updates？

Okay。Set up clear for people。So this is Newton's method。We we're at some current iterate。

 So we have some current。X0。In Rn。And what's the update rule？And。SoWe set x1。系。To be。

X0 minus the Hessian inverse。Apped to the gradient of Fx0。Okay。

 so that's going to be the update rule that we're going to analyze。Okay。And。

Where does that come from？Well， remember what gradient descent did？

Graadient descent wrote basically the first order Taylor approximation。Of the function。

Plus some error bound that comes from Taylor's theorem。Okay。

And then gradient descent just tried to minimize that expression。

So what Newton's method is doing is it's taking the second order。Expansion， Taylor expansion of F。

 And it's minimizing that second order expansion， right so。So Taylor's theorem。Says。That。You know。

 if you look at F of X1。Well， let's say F Y。Just some F Y。

Approximately up to some arrow that comes out of Taylor's theorem。This is equal to。F of x0。Plus。

The gradient of f x0。Dotted with y minus x0。And。Plus， one half。Y minus x0 dotted with the Hessian。

Of y minus x0。Okay。So。This is what Taylor's theorem says in terms of approximating F by its second order expansion。

And。Newton's method is basically just assuming that this is inequ and then just tries to minimize the right hand side。

And the minimum of this right hand side is exactly this。If you do calcus。All。

 so we just need to understand。How well Newton's method does。 So are there， are there any questions。

So far。Okay。It's only right down a theorem。So again， for tea。In01。Define。XT。

To be x0 plus t times x1 minus x0。Where。By x1， I mean that x1 and by x0， I mean our initial。

 the point that we're currently at。うんううん。Suppose。There exists in epsilon。A positive epsilon。

 such that。For all t in the interval from 0 to1。We have that the following is true。One minus epsilon。

Times the hessian of F。At a zero。Is that most in the loaner ordering？The Hessian。At X T。

Is that most of the loaner ordering？One plus epsilon。The hasian at x0。I suppose that that's true。

 So remember when we're analyzing gradient descent。It was， it was a first order method。

 We only had access to the gradient。 We couldn't actually compute the Hesian。

 but we had a promise about the Hesian。 right， We were told that the hessian is well conditioned。

There's some small gap between its largest and smallest singular values。So again。

 for Newton's method， we need to have some kind of promise to say that Newton's method does well。

And the promise that we're going to make use of is that the Hessian doesn't change too much。

On the line that connects x0 to the next iterate。Okay。Just a recap when I say that。

A matrix A is that most of matrix B， remember that means B minus A is positive sub definite。

So suppose that's true then。I want to measure progress。

 and the way that I'm going to measure progress is that。Okay， so。Is to， is to say this。

So the norm of the gradient of f and x1。Under。This。嗯。I'll say what this means in a second。Okay。

So this is our progress theorem。Okay。🤧。嗯。So。So just a definition to make sense of the progress theorem。

For positive semi definite matrix A。When I say the norm x of a。That means， by definition。

 what I mean is。X transpose A X square root。Okay。嗯。So。

We'll get into where this is why this is going to be useful for us in Interior point in the second。

 But ignore this thing over here。 It's telling us that the norm and the norm is changing。Okay， but。

The norm isn't changing too much because。These matrices are very similar。

All across the line in particular， the the Hesiannet X1 is very similar to the Heschenet X0。

 So pretend for a second that these are the same matrix。Okay。So in other words。

 these are the same norm。 It's telling us that our new norm of the gradient is at most the old norm of the gradient times roughly epsilon。

And the minimizer is when the gradient is0， right， so we're getting closer to having zero gradient。

So that's how you should interpret this。Okay。Are there questions before I actually approve this？

So let me give you a proof。I should confess I'm not an optimization expert， so I don't know。

The proper citation for this proof， but this is a proof that anyway， Aaron Sidford。

Was kind enough to share with me， So I'm just going to show you this proof。So。First thing。

 I want to make an observation。What does it mean？😡，To say that。1 minus epsilon A is at most B。

Is that most one plus epsilon A？How can I rewrite this？So that's the same thing as saying。

Minus epsilon A。Okay。Is that most？B minus a。Is that most？Epsilon A。All right。And what does this mean。

 Remember what the definition of。Remember what the definition of。An operator norm is， right？So okay。

 this means， well， okay， So what does this mean， This means that for all X。For all x and Rn。

Minus epsilon x transpose AX。Is that most x transpose Bx？

Is that most epsilon x trans this is b minus a。And that's at most epsilon， x transpose Ax。Okay。

So in our case， we're going to be working with real symmetric matrices like Kesss。

And the spectral theorem says when you have a real symmetric matrix。

 write you can write a real symmetric matrix as u times lambda u transpose where lambda has the eigenvalues。

 right？And these are going to be PSD matrices。 So these。So Lambda has some non negative eigenvalues。

And U is an orthogonal matrix。So when I talk about F of lambda， when I talk about。

 or I'm really already using F， When I talk about some function G applied to a。What I really mean is。

Take this decomposition and take G and apply it to lambda。

And what I mean by that is apply that transformation to every single one of the eigenvalues。

So then if you do that， then what is x transpose AX？That's just。

The L2 norm squared of a to the 1/2 x。😡，Right。Same thing here。So now we can write。

We can write y as a to the1 half x。And。That implies that for all why。Minus epsilon， y transpose y。

Is that most？Y transpose y or what's x now， What's x。

This implies that x is equal to a to the minus12 y。Right。So this X。Is。嗯。

We can write and this as y transpose8 to the minus12。B minus a。A to the minus12 y。

Is that most epsilon y transpose y？And that's the same thing。

As saying that minus epsilon times the identity matrix。Is that most in the loaner ordering？

8 to the minus12。B minus a， a to the minus12。Which is at most in the loner ordering Epsil times the identity。

Okay。So。You know， when we go through the Newtons， you're going to see this come up in the proof of Newton's method。

All right， the question。Yeah， so we're going to。So for Rf， it always is。I mean。

 we're going to apply this with F lambda， you can compute what the hesian is。嗯。But yeah。

 so those pretendance in verbal。Okay。Right。Another thing I think you can say is for this inequality to even be true。

It has to be the case that A and B have the same column space。Okay。And。

And then what you could imagine is just kind of restricting。Instead of a。

 really work with a times UX where U has orthoormal columns that form a basis for that subspace。

Right and then。This composition of first you multiply by U， and then you compose with F。

 that will then have。Eld Indian bird。Well， okay， so sorry， but okay for us， it's invertible。

 so don't worry。Okay， so I'm going to kind of use these。Use these things interchangeably。Okay， so。

So our proof。Of。Theorem。The analysis of Newton's method。So we can write。Delta of f at x1。

 or its not delta， the gradient of f at x1 as the gradient of f at x 0。Plus。

 an integral from0 to1 of the hessian。嗯嗯嗯。Right so for example， if you just。

I guess this is the fundamental theorem of calculus or you can just view this as zero order tailor approximation with explicit error。

And this thing- so now we're going to use what x1 actually is。This thing is equal to。The integral。

From zero to1。Of the Hessian。At a 0。Minus。The Hessian at XT。X1 minus x0 Dt。Oh， wait， sorry。

 this is not right。To many symbols。Okay， so I。I brought in the Heshen at X0。

 but then I killed it here。 Okay， so this is just an identity。嗯う。And then。What about when I erase。

 I'll erase this？So what's the thing that I want to bound， I want to bound this thing。

And I'm going to plug in what I wrote for the the gradients of F X1 as that。So that implies。That。

This thing。对。Is equal to。The integral of that。嗯。嗯。You can write the same norm。Okay。

But now because we know that。The Hessians are spectacular similar along the entire line。

We can replace this norm with the x0 norm right， and pay at most a1 over 1 minus epsilon。Right。

 so the Hesians themselves have this one my sub put up on the gap。 So if you take the inverses。

 the inverses。嗯。You have a similar sandwiching inequality for the inverses。

 where on the right hand side you would have one over one minus epsilon， and on the other side。

 you'd have one over one plus epsilon question。还是。しは。ドライ？いや、モ。Did I write this wrong， Rachel on。

So you're saying， so you mean if I expand this out， what do I get？

So I be more careful in expanding this out。嗯。The integral。

This is the integral from 0 to1 of so there's that inverse of the gradient。

So that just gives you back that。And then there's minus the integral from0 to 1。Of。Oh， I see。Okay。

Yeah， so， oh sorry， this is minus。 Is that what you were saying。 Yeah， so this is minus。呃。Right。

And this， by definition， this is exactly x minus x0。Very good。So this thing here is at most。

1 over1 minus epsilon， where now I can switch the norm to the x0 norm。And also。

 I can bring the the norm inside the integral。And that will only increase things as well。

 So this is at most1 over1 minus epsilon and the integral from 0 to 1。Of the same thing。

Hessian squared， I mean， Hessian of at x0 minus Hessian at x T。 This is a minus sign， sorry。

Hessian inverse at x0。The gradient at x0 Dt。And then I brought the norm on the inside。

With respect to x zero now。Okay。Sorry， I guess this is conceptually。

 there's not really a whole lot going on here， but it's just a lot of symbols。嗯。

Maybe you should definitely interrupt me if something looks fishy。Okay， and then。🤧。

Now the claim is that this is just equal。😡，To1 over 1 minus epsilon。The integral from0 to 1。

Of the norm of。Pasian。Add x0 to the minus a half。うんうん。The gradient of F x0。

now a really long string of things。嗯。Okay。So it's kind of a nightmare。But。Basically。

 remember the definition of the a norm， it's just the square root of x transpose AX。

Okay so I promise you。If you expand this thing out as this transpose， this matrix times this。

And you expand out this transpose times this big matrix times this。 It's exactly the same thing。

 okay。So I don't want to waste time。 I mean， you can， it's gonna to be in the notes。 You can。

 you can verify it for yourself。 Oh do you have a scribe for today。Okay， yeah， sorry。So。Yeah。

 feel free to know， just like take a picture of your phone or something if it's too annoying to type。

嗯。Yeah so。This is just。Writing things down explicitly and observing that they're actually equal。Okay。

 I'm not going to spend time on that。Not something deep。Now， what do we know？

We know that that's true。😡，which I said is the same thing as this being true。

So what does that mean for us？We know。That。Basically， this whole matrix。Call this whole matrix M。谁？😊。

By this。And basically this。If you just combine those two things。We know by。Star and double star。That。

M。Minus epsilon I is at most M。Is that most Epsilon I in the loanner ordering？

But here we have M squared。So that implies。呃。Basically that。M squared- well。

 certainly m squared is at least0。M squared is a PSD matrix。And it's at most Epsilon squared I。Okay。

Good。So this thing。Is there for at most？1 over 1 minus epsilon。嗯嗯。🤢，The integral from zero to 1。Of。

The integral of this thing， f of x0 to the minus12。F of x0。Times。Epsilon squared。Identity。Yeah。Okay。

 so。So we could do the spectral theorem to this real symmetric matrix， right？And what do we get。

 we get u lambda we get forget about the inverse， without the inverse， we get U lambda u transpose。

So what does it mean to apply a function to a matrix。

 it means you take that decomposition and apply it to each of the eigenvalues。

 So what is the inverse of that matrix。It's U lambda inverse U transpose。And we knew that。

All the original eigenvalues。Between。So forget about the inverses。

 all the eigenvalues between these two matrices are the same up to 1 plus or minus epsilon。Oh。Yeah。

 maybe I see what you mean1 over1 minus。Upsilon。Yeah， maybe I' have thinking about what you said。

 maybe but okay， so worst case I'm off by a square root， but in that case。

 the square root of1 over1 minus epsilon is basically the same thing as one over1 minus epsilon。

Right epsilon changed by a constant factor。 I don't。 So I'd have to yeah， let me。

 let me not try and think through this on the fly， but。At most。

 what you're saying would change up slide by a constant。Okay。And now this is just。Right。

 so we have the identity matrix here， a scaled identity matrix。 So this is just。The scaled L2 norm。

Namely， it's the Altoon norm scaled by epsilon。Because of the square root。So this is at most。

Is that most epsilon？Times the norm。Just the normal L2 norm of this thing。These are different lines。

Okay。But what's the L norm of a vector Z， it's z transpose Z。So we going to do z transpose Z on this。

What you get is。This you get this is equal to。Eppsilon。Times the square root。Of。

The gradient of f at x0 transpose。呃。And then you get two minus a halves。So you get the Hessian。

F of x0 to the minus1。And then you get the gradient again。Which is exactly that。Oh， there's a。

It's actually epsilon over 1 minus epsilon， right？Because of this one。Okay， so。Enough calculus。

 that's Newton's method。So now。Now we have to go back to。Andter your point。Okay。So。Let's remember。

🤧Yeah。Back to Interor point。So we have our function。F lambda x。

Defined to be this lambmbda c transpose x。Minus the sum i from 1 to M。Of lawn of the slack。

So if you do some calculation， this tells you that the gradient of F lambda x is equal to lambda C minus。

A transpose the slack matrix at x inverse times the all1s vector。Okay。Remember， this is。

Forget about the inverse。 The slack matrix is the one where you just take the slack vector and you write it on the diagonal。

This is a diagon matrix， this is the all ones vector。And if you go and calculate the hessian。

This thing doesn't depend on C at all。 This is just a transpose Sx minus2 a。Okay。Okay。So。呃。So。

Remember that progress in Newton's theorem is all related to。This norm。Right。So。

That's how we're going to measure our progress in IPM。So。so let me give some definitions。

So remember that we start off with some initial lambda。

 I'm going to go back to this toward the end of lecture。

 we start off with some initial lambda lambda knot。

And we assume that we had an approximate optimum for lambda not。And then。

We moved on from Lada not to lambda1， which was very slightly bigger。And then we used。

Our approximate solution for Lada n as a starting point for Newton's method for Lada 1。

 for F sub lambda 1， right we want to minimize F sub lambda 1。 We run a few newton steps。

 and then now we hope that we get to something that's not so bad for F of lambda 1。

And then we increment ada 2， et cetera， right。What does not so bad and approximately minimizing mean？

Well， I mean， Newton's method tells us。One way how we can measure progress。

 So that's going to be our our way of saying that it's a good solution， right， So we're going to say。

We're going to define。呢。Centrality。Of x。For F sub lambda。As。Delta。Sub K of x。Is。

The gradient of F sub lambda K at x。Under the norm specified by the Hessian inverse。At X。对。

So suppose that x were actually the minimizer of F lambda。

What could you tell me about the centrality？It's zero because if you're actually the minimizer。

 the gradient is zero。😡，So this is some measure。That tells you how close you are to in a funny norm。

 how close you are to。To the minimizevis，Let me make two more definitions。Definition。嗯。嗯。X is。

Coursely or refinely central。For F lambda K。エ？Delta k of x is at most1 over 100。And also。X is。

Coursely central。If。Delta k of x is at most， say， a third。So。What we're really going to say is look。

For lambda K。We have for Lada K we have in our hand a finely central point。

And then we want to say is。If lambda K plus1 is not too much bigger than lambda K。😡。

That finely central point for Lada K。Will still be coarsely central for Lada K plus1。Right？

Which means that our measure of progress in Newton's theorem。😡。

Our initial error under that funny norm is a third。And we want to make it finallyly central。 Again。

 We want to get back from coly central to finally central。 We want to get from a third。Down to 100th。

But that's just the constant number of Newton steps。As long as Rohesians are behaving well。

 we're going to roughly have our error in every step or in every constant number of steps to go down from a third to 100 is just a constant number of steps。

Okay。So IPM is' going to always keep a finely central point in hand， increment Lambda。

 run a few newton steps to turn that coarly central point into being finallyly central again。Okay。

 so that's where we're going。 Other questions about where we're going before we actually do some calculations。

And we have to understand。How much we I think I mentioned at some point that we're going to be able to increment lambda by a1 plus1 over a Rum factor。

In every step， as we go from k to K plus1。That one plus one of RuM is going to come from the fact that we want to maintain core centrality。

 We need to understand how big can we make， how big can we give an increase to our Lada to make sure that a fine central point is still coarsely central。

Yeah。Yeah。Epsilon。It will so the epsilon that we're going to get at the end of the day。

Will be just some small constant。Right， but I mean， so when we apply Newton's method。

 our F is actually F lambda K for some K。Right。It's okay if the epsilon does depend on。 I mean。

 the function， because we're we're doing Newton's method over and over and over again in the sense that we have1 f。

 we apply Newton's method。 Now we change F。 Now we run Newton's method again。

 As long as the epsilon for each instantiation of Newton's method is some fixed thing。 that's fine。

Okay。Yeah。嗯其， so。First off。Here's one thing I want to understand。Which is。

How does the Hessian change as you change X？RightBecause if you look at Newton's method。

 it says that the Hessian shouldn't be changing too much on the line that you're optimizing over。

Right， so if I'm gonna have any hope of controlling that， I need to understand when I change。

 when I vary X， how' is the hessian changing。Now remember。The hessian， we said， is just this thing。

 F lambda。An X。Is。A transpose Sx minus2A。It doesn't depend actually on Lada at all。So really。

The only thing it really depends on are the slacks。

Because if you take a spectral decomposition of this matrix。The eigenvalues that you're getting。😡。

Correspond to。The oh， what I want to say。Yeah， so okay， so， right， So， okay， so the only。

 the only matrix that's changing as you， as you。As you vary x is the slacks。

 So I want to understand how do the slack eigenvalues change as you change x。So。I want to understand。

For which x prime？Do we have。The slacks don't change by much，1 minus epsilon。S of X。Is that most？

SF x prime。Is at most one plus epsilon？S of x。Okay。First， let's understand this before we continue。

So。What do I want here。1 minus epsilon。呃。I want one minus epsilon。Times the identity。我是那没。

Let me just do what I said before， so let me subtract slack of x from both sides。

 I want minus epsilon and slack of x。To be at most， slack of x prime minus slack of x。Yeah most。

 Epsilon S of X。So minus epsilon times the identity is at most slacklack x inverse。Slackx prime。

Minus slack x。呃。The most epsilon times the identity。🤧。And。So now。

All of these things here are diagonal matrices， right？So。The largest eigenvalue。 So what do we want。

 we want that all the eigenvalues and magnitude are at most epsilon of this matrix。

It's a diagonal matrix。 That means we want all the entries in the diagonal to be at most epsilon in magnitude。

So this is the same thing。As saying that the infinity norm。Of the slackck matrix。Sx prime minus。SX。

 this is now the slackla vector。Was it most epsilon？So。To understand when this holds。

 it's enough to understand when this holds。Okay。But， what do we know？Well。

 we're going to do something very loose right now。Which is that we're just going to bound the infinity norm by the L2 norm。

So this thing。This thing is at most。Slack， inverse。Sx prime minus Sx。L2 norm。Okay。And。Again。

 this is equal to， I think we've seen this trick before。What's the slack x prime minus slack x。

 What is that？What what is the slack at x， What's the definition of Slack。

So remember in our original LP， we're trying to minimize he transpose x subject to AX is at least B。

So the slack is how far away is each constraint from B， from BI。

So the slack vector is just Ax minus B。 That's the definition of the slack vector。

So the bees cancel here。 So this is equal to。Sx。Inverse。A x prime minus x。And。Really。

 actually you know。Remember that。X prime。I really， I shouldn't have。

 I should' have really just said X T。 I'm sorry about that。 So imagine in your mind。

 X prime is actually X T， which is。If you remember。It's。T times it's x0。Plus， T times this。

X1 minus x0 business。Right， so we're imagining that we're looking at how the Slack changes along the line of optimization in Newton's method。

 That's the thing we need to control understand Hesss of to be able to apply the theorem from Newton's method。

So if you just remember what？This thing is。This is minus。Minus Hessian。Inverse。Times the gradient。

This is equal to。Kind of T times。呃。Slack X inverse a。うん。Hasian。X inverse gradient。看。Hel2 norm。嗯。

And this is just equal to。T times。Now， the。A gradient。Of Atic0。So what is。Okay， so good， so this is。

The hessian。I mean， basically this is going to be exactly the centrality at X0 so this is。Sorry。

 I started switching between x and X years in the middle。

So the point is if you're doing a Newton' step starting at a point x。

 an x prime is anything along the line toward the new iterate and Newton's method。Then， the。Good。

This error is at most。😡，Is that most。The centrality， okay。Which we want to be less than epsilon。O。

So the point is。If X is actually sort of right， we updated Lambda and our finally central point became coarsely central。

 I haven't proven that yet。But the point is it is coarly central。

Which means that the centrality at that point is at most a third。😡，Okay。So。This is that most。

 let's say， t over three。对。So in particular。We are satisfying。嗯。We are satisfying the original。

 were satisfying the conditions of Newton's method where Epsil' a third。

I guess that's what I should have said。See a lot of worried faces。嗯。Oh yeah， I didn't。 I didn't。

 Okay， So yeah， I didn't prove that yet。 So suppose that we have a coarly central point now for F lambda K plus1。

And we want to make it finallyly central。 What are we going to do。

 We're going to run Newton's method and hope that the error you know， gets。

 gets killed down back to a one over 1 hundred0 to make it finallyly central。

And in order to apply Newton's method to say that we're knocking down the error by a constant factor in every iteration。

We need to make sure that that epsilon from the conditions of Newton's theorem is something that's。

 you know， at most a constant， like at most a half or something。

Because we're killing the error by epsilon over  one minus epsilon fraction in every single step。

So to make sure that epsilon over 1 minus epsilon is nontrivi。

 Epsilon had better be strictly less than a half。right。

So what I'm showing you is that the rate of change of the Hessian does satisfy that property。

Where epsilon。Where epsilon is the centrality of the point。😡，And the centrality is at most a third。

 because we started off being coarly central。Any other questions？Sure， don't be shy， know。

 you can feel free to ask me anything。Think about it if you want to ask me anything as I start。

Esing the other board。So yeah， you're right。 kind of the last thing that we need to do now is to we need to。

Verify that it's actually the case that if you take a finely central point for Lada K。

 it will be coarsely central for lambda K plus one。Right。

Then you could plug in this argument and say Newton's method will make it finally central in a constant of re iterations。

唉。So。啊， yeah。That's right。嗯。Right， so very good。So what did I？Yeah， so okay。You're saying。The Hesian。

 so what is the Hessian？So， the Hessian。Is this a transpose Sx minus 2 a？系。And。X。Prime。

Is now a transpose Sx minus。To prime A。And we want to say that these things are spectrally similar。

We want。That for all X。Basically。AX。Tranpose。Well， x transpose。A transpose。SX to the minus2。AX。

Want this to be。Up to one plus epsilon， the same thing as oh I shouldn't use。

 I shouldn't use X here because they already have x's。For all z。

This thing should always be close to Z transpose， A transpose S X prime minus2 A Z。

 That's what we want， right。So what is this thing？This thing is。It's SX inverse。Aii。L2 norm squared。

And this thing is。Sx prime inverse， A Z。Ll2 norm squared， right？Yeah， so now maybe know it's clearer。

 so the point is。YouIf if these things have eigenvalues that' are all close to each other， then。

On any vector， in particular the vector A Z， the norms will be roughly the same。Sorry。

 sorry for I guess I。Was hand waving a little bit。Thanks for keeping me honest。 Yeah。

 so really to say that the Hesians are spectrally similar， you can just focus on the slack。

The slackck matrix。Okay， yeah， any other questions？Okay，Let me not erase this yet。So actually。

 if you don't mind， I。I want to erase this as late as possible。 So our people。

 I'm going to erase this now people okay。So。So that board over there。The last word。Says。That。

If we start。With a coarsely。Central point。For lambda K plus1。We can make it。Finally， central。

In a constant number of Newton steps。对。So。Assume。Assume that。The K centrality。

OfSome of our approximate minimizer， X Tilda of Lambda K。Is that most one over 100？So assume we have。

A fine central point。For lambda K。So now the question is。How much bigger。

 remember that as Lada goes to infinity， solving F lambda is getting closer and closer to solving the actual LP we care about。

 So we to， we want to make progress。 We want Lada K plus one to be as big as possible。

But if we make it too big， then this point won't even be coarly central anymore。

Will fall off the central path。 So the question is， how much。Are we allowed？To increase。Lambda K by。

To get lambmbda K plus1。Ss that。X tilde lambda K。Will still be。Finally， central。

For F lambda equal plus1。So。I'm sorry。Yeah， course Lee， thanks。

So let's say that we're going to do a multiplicative increase。So let's say that Lada K plus1。

Is equal to1 plus sum factor alpha times lambda K。And we want to understand。

How much does that change Delta K by？看。嗯。So。Delta K plus1。So。Let me。哎。I'll just write it over。

 I'll write the irrelevant stuff here， so the gradient。F Lada X。Is lambmbda C minus。

A transpo S inverse。Times the O1s vector and the Hessian。Is a transpose Sx minus 2 a？

Okay so that's all we're going to need to remember。So let's compute this thing。

Let's look at S X plus1 of x lambda。So this is our finally central point。

 X di lambda K is our finally central point for Lada K。

And we want to understand now its centrality measure for K plus1。What is that that's equal to？Well。

 but let's just do the definition。 that's equal to the gradient。Of f at lambda K plus 1 at the point。

Of the Hessian。Well， the hessian， the hesian doesn't depend on lambmbda at all， right。

 The Hessian is just。A transpose xx minus 2 a。嗯。That's the definition of centrality。

And then now let me write down。What the gradient is。The gradient is now。Lambda。Xi。Well， lambda K。C。

 well。Lambda K plus1 is just。1 plus alpha times lambda K， So lambda K times1 plus alpha。Time C。

Minus a transpose Sx inverse。All one's vector。Times that same。Ting。うん。嗯嗯。And then now I want to。

Basically， add and subtract alpha times this matrix。So this is equal to。1 plus alpha。Lambda K C。

Minus a transpose sx inverse。All one's vector。But then we just subtracted alpha times this。

 so you better add alpha times it back plus alpha times the same thing。And then， you know。

 the usual Hessian universe over there。And then now we do triangle inequality。So what is this？What's。

Hopefully this is now， it's clear what I'm doing here。What's that？Yeah， right， yeah。

 does' if you include the norm with the Hesian inverse， but yeah。

 the point is this is just the gradient at Lada K。So we can do triangle inequality and say， look。

 this is at most。1 plus alpha。Times the centrality measure at lambmbda K or the centrality measure at K is how I defined it。

Of Xelda。Lambda K。I'm， that thing is at most one over 100。So that's fine。

Now we have an alpha out here， a transpose Sx inverse。One vector。And now let me write again。

 this is a transpose。呃S。X tilde lambda k。-2。诶。Okay， so this part is fine， right。

 we're trying to make sure that this thing is at most a third。As long as alpha is tiny enough。

 the one over 100 is going to become1 over 50 or something， we don't really care about that。

But then we need to understand。This thing here。All， so we need understand this thing。So。This thing。

So what is it equal to？Well， let's expand what it means to take a matrix norm like this。

I is equal to。One transpose。嗯。SX inverse。This is all X here， I remember， is x tilde lambda K。

All these x's are external to lambda K。Xt till the lamb decay。呃。And then， A。And then。A transpose。S。

X tilde lambda K。-2。诶。Inverse。And then the same thing。A transpose。Sx Tda lamb decay。Okay。

Looks like a mouthful， but I claim that there's something special about this。About this。This matrix。

There's a minus one here。O so。Whether or not you see this。

 I guess will depend on how much you remember your linear algebra。Okay。

 it's not necessarily the identity。Because。嗯。Right so if everything were full rank would be the identity。

Yeah， in general， what this is is it's a projection matrix。Okay， this is。TheSo this。

This red thingingy。Is equal to the projection。Orthgonal projection。Projection。Onto。The column space。

Of。S minus1 x tilde lambda K。At a。So in general， if you want to project。So you know， the projection。

Onto。Call the column space。I a。Is。A transpose a inverse and then put an A here。A transpose A。I mean。

 the best way to see that is well you can see it by， for example， taking the SBD of A。

And when you expand this thing out， you get。You get UU transpose where U is the matrix with left singular vectors。

But what does that tell us about this thing？This implies that this yellow boxed thing。

Right is that most？One transpose one。Square root。Which is Rum。So really。This thing。

 so really what would be shown。At the end of the day， what we've shown is that。

Delta k plus 1 at x Til de lambda K。Is that most？1 plus alpha。Delta K。X total to lambda K。Plus。

 alpha rootm。嗯。We want this thing to be less than a third。

 And we said that this thing was coly central。 So this was at most。1 plus alpha over 100。Plus。

 alpha root M。We want this thing to be less than a third， so choose。

Alpha to be something like one over Ru N。You know， one over 10 redamm or something。

And then it's coly central。So that's basically it。We。

We can increase lambda by a multiplicative 1 plus1 over rootM at every step。If you remember。

I told you that somehow we get an initial point that's really good forda Lambda initial being roughly exponential and minus the precision。

And we're done when Lada gets to be as big as。Something like M times exponential in the precision。

Right。So。I think I mentioned this last class。 You can look at the notes。 But the point is。

 this tells us we can take roughly RuM There are RuM iterations of step 5 last time。

 where we have to keep increasing lambda。 We have to increase lambda roughly root M root M times L times where L is the precision。

So。That's it for， I guess， the main part of Inter point。

It all just now boils down to how do you get the initial。Finally， central point。Right。

Or even the initial of coly central point， you can make it finally central with Newton's method。Yeah。

 question。 so instead of square root M。Times L， you can get squared rank of a at times L。

Aaron Sidford， Yeah， so that that was a recent paper by Sidford and Lee。 and I'll say。 they they。

 they turned the square root M into square root rank of A。 and the basic idea behind。 So okay。

 there's a lot going on there。 But the the the highest level。

 most basic idea is if you look at the barrier function that we're using。

It's minus the sum over I of log of Slack I。Which is kind of weird because this means that if you repeat the same constraint over and over and over again。

It's getting weighted more and more in the barrier。😡，Right？

But the optimization problem you're solving actually hasn't changed at all。

So what their algorithm does is at every point it maintains kind of a weight vector so that you use the same barrier。

 but a weighted version of that barrier where every constraint is weighted by a certain amount。

And the amount that you have to weight each constraint by in that barrier function depends on some geometric considerations。

 Okay， so that's kind of that's the， the heart of their change。

And then there's a lot then how do you come up with this weight vector and how do you maintain it and analyze things。

 et cetera。The new thing that changed to get down to root rank was that they used some kind of weighting of the constraints in the barrier function。

Does that make sense？Oh yeah， right， so the point is。

The barrier we're using is minus some i from1 to M。Of law and of slack of Xi， right？So what。

 what are the slacks you have， What is the constraint， The constraint matrix is A X is at least B。

 That's the constraint， right。So what is a slack， A slack is the Ither of a dotted with x minus B。

So suppose you just have the same constraint。 Supp someone just gave you the LP with the same constraint written a thousand times。

 you're going to summit a thousand times here。But that's， I mean，'t， that's sort of weird。

 right because the constraint only matters once。So。

They have some way of weighting the constraints in this barrier function。

 So they actually have a minus sum of our I weight I。

And they have some way of figuring out these weights that guarantees faster convergence。

I think they even change they change the weights over time as well。 And when they so you know。

 we had to look at how does the centrality change as you change the lambdas。

 they also have to look at how does it change as you change the Ws as well。

So they also need to be able to compute these ws efficiently because you want a fast algorithm at the end of the day。

So yeah， I'm not。 So I don't know all the details of their paper。 My understanding is that there was。

 there was an existential theorem due to Nestorrov or maybe Nesrov and Nemorrovsky。

 I'm not sure that showed that there exists a weight vector。But it was not algorithmic at all。

And they show that that they can actually algorithmically efficiently maintain some weight vector that does。

Close to as well as that existential result。So。I want to say something I just want to close this lecture with。

You know， how you actually start off？So， again， this is gonna be down to precision issue。

 So I don't wantna。I don't want to give all the calculations， but the basic idea is。So。

How to start the IPM？😡，Right， we need to have some。X tilde lambda 0。To start it off。

 which is coarsely central or finally central initially。So the point is。

 so first what we're going to do is。We're going to alter the LP to be men transpose x plus capital n times Z。

 I'll say in a second what this is， such that。AX plus the all ones vector。Z。

Is it greater than equal to B？Okay。Has an obvious。 Oh， and Z has to be at least 0。 And。

 let me theres some more also。Zero is at most， Z is at most2 toL plus1。And negative to the L plus1。

All one's vector is at most， x is at most。2 to the L plus1。All ones vector。So I'll put a link。

 I'll put a reference in the notes， but you can show。That。If n is big。

 if n is like exponential in the precision， let's say。10 to the L or something or 100 of the L。Then。

Original。LP bounded and feasible。Implies。That LP prime。Optimum。Must have。Z equals 0。在。

So you can prove this kind of theorem by looking at various precision calculations。

And then the point is， so now if you could actually just solve this one。

 well the optimal solution has z equals 0， so you've actually solved the original LLP。

And in the original LLP， you can show that any solution has to have bound precision anyway。

So now we just need to solve this thing。I'm just giving you a sketch of what's going on。

So this is LP prime。So LP prime。Has an obvious interior point。X prime。

Which let's write that as x comma Z。You can set x to be0 and you can set z to be the lfinity norm of B。

So that's an interior point。Are we done？Yeah， finally， What's Lambda， you know。

 and is it finally central for that Lambda， Who knows。So we're not done。But then。

There's one last trick。We don't just need。An interior point。We need。We need a coarsely central。

Interior point。For。For some。Lambda。So what are we going to do？

Here's now a funny thing we're going to do。Set lambda to be1。Now， let's look at the gradient。

The gradients of f of lambda at this x prime。Remember， the gradient is equal to lambda times C。Minus。

I think slacklack。Slack inverse。Right atri will select universal1 vector。Right， when are we optimal。

 We're optimal when the gradient is 0。So here's the funny thing we're going to do。Okay， sure。

Here's the funny thing we're going to do。So， x prime。Is。Perfectly central。

For a different cost function。So this is lambda equal to 1， right？

So it's perfectly central for the cost function。 a transpose X X prime inverse all one。Right。Okay。

So now， the gradient is 0 now for this cost function。 That's not our actual cost function。

 but it's the gradient is0 for this cost function。 So what do we do， So now we。

 we have a point where' just perfectly central for some cost function。😊。

You can basically run all the updates steps I told you in reverse。

 instead of incrementing Lambda by a little， you decremented by a little。And you run Newton's method。

 and then you keep refining going down in Lambda。Until you get to a very， very， very tiny lambda。

 exponentially small in the precision。And now what you have。

 you have a point that's finally central near the analyticslytic center。

And then what you show is that when you have a point that's finally central near the Atlantic center。

 you can basically just switch the cost function to whatever you want。

 and you'll still be finely central。Because once lambda does that tiny。呃。

The cross function basically doesn't matter anymore。So once lambda is that tiny。

 you then switch over the cost function。You'll still be finally central。

 and then you write everything I told you in the forward direction。Now run everything。In reverse。

To get。An approximate。Analytic center。Which is。Basically。You know， finally central。For any。

Cost function。Abounded precision。And now that you have that well。Now you run things forward， okay。

 so that's everything。Does that make sense。Okay。So that's it， I guess so。I'll see you Tuesday。

