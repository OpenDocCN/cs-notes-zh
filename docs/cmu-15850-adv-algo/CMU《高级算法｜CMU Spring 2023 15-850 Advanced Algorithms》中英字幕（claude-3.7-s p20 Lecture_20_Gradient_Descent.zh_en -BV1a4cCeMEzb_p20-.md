# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p20 Lecture_20_Gradient_Descent.zh_en -BV1a4cCeMEzb_p20-

So welcome back and today we'll talk a little more about gradient descent。😊。

And if you remember the gradient De framework， we said it's a framework because there are many different little parameters that can change we start off from an initial point and then a whole bunch of times we。

😊，Take a step in the direction of the negative gradient。And this data is the step size。

 which of course， determines。The convergence rate， this eta needs to be chosen carefully。

 x1 needs to be chosen。And then finally， we'll return a point。

 which is the average of all the points we've seen。😊。

There are variants of this where you don't return the average point but the last point。Before today。

 I'll return the average point and actually because I I'm considering the constrained version。

What might happen？Is that the step that we take might actually take us outside the convex body。

 so then we say x t plus1 is the projection。😊，There's a projection on to k。Of x。B plus one。可了。

So I'm taking the closest point so so this is just。你。Augments。Of x belonging to k。Of x minus x。

Minus X d plus one Twitter。And I'm using the Euclidean norm out here。

And we'll change all these things as time goes on， but right now this is what I'm going to do。

 I take a step， I project back onto the body and then I do this some number of times and then finally I return。

The average part。不对。😊，And the theorem says， suppose。That。Good， suppose X is convex。

And the gradients of faith。Are bounded by some G。Then。诶 setting。Eta to be O N， and suppose。嗯。

That the distance between x1。And some point X star， this is some reference point X star。I at most D。

Then by setting ata。To be something like。G over。B times square root t。Will ensure。That。

F of the X act。Where that most half of things start。嗯。Plus， epsilon。 Okay， I haven't。God。

 absolutely on， yeah。When。呃，When。第一。Is at least G over epsilon。咁俾啲咩。Okay。

 let me just pass that for you F is a convex function， its gradients are bounded。啊。

There is the reference point which belongs to my convex set okay。

So the picture is really my convex sec is something。X star is the point I'm looking for。

I start off with X1。The distance between these。Is the。The gradients are bounded by G。

Then there is a setting of parameters such that if I set。

The time time period long enough I be within epsilon of the optimal。Remember。

 we are trying to minimize this convex function here。这。Okay。Now， this theem I going to prove。

By actually proving。A result about the online version。

And it turns out that basically the result for the online version will follow。

Just know the same steps， in fact， a subset of the steps。So here's the setting。嗯。你是的啊。

The proof of the online。I'll give you the proof of the online and then the result of that one more step will give you the proof of the online。

So here here's the setting at each point in time I have a different convex function empty。😊，诶。😊。

My body remains the same， though。And the theorem here is going to be。Suppose。F1， F 2。FP are all。

Conveyx。With the gradients of FT。It bounded by。じ。And let's say that。

You pick any reference point again， x1 minus message start。Is bounded by de for some。The reference。

Ex start。嗯。Then。Here's what I'm going to show。F T of X P。Some of loyalty。They lack most。Smed over T。

 F T。我 next done。Plus。Okay， plus plus what？Plus， there's going to be a couple of terms。

 There's going to be。A的。Dmes。The。The gradient times t。Plus。呃，呢。我 ada。

Maybe I'll just put it to there do it。Okay。Here's what I'm saying。This algorithm。

With with learning rate Eta with step size E is going to guarantee the following。

 I'll feed you with different convex functions at each point in time。😊，You run the三个。

And then I'm going to look at the sum of the total loss that I've suffered。😊。

I'll compare that to the total loss that。😊，My favorite point in K would have suffered。

This is the loss of my favorite point， maybe the best loss， whatever that means。

This is the loss eye suffer。My loss is comparable to the best loss plus some garbage factors。哎。

And this will call the regret of Al。在啊。So this is theorem 1 and this is theorem 2。

And what I'll show to you is I'll show you theorem two and then you know， in fact。

 maybe let's prove theorem1 from theorem two and then we'll prove theorem two。How about that。

Questions about the theems。I forgot my up。Yes。😊，Some of this seems a global screen。

So it seems like XxT doesn't depend on FT at all， absolutely。So in fact。

 what I'm doing is I'm playing X first and then you're giving me FT and so yeah， it's magic。😊，Okay。

 okay。One thing to emphasize further is that。The comparison is to any fixed point。

So I'm not comparing myself to somebody who knows Ft and then plays Xt that would be too much to hope。

😊，I'd be predicting the future， so this is just saying nobody should be able to come and say。

 look I always play extra and I'm doing much better。😊。

Same principle as this online you know learning that we were doing。

 this expert stuff that we were doing。😊，Great enough。Good。嗯。Okay， so so let's just。Prove Theem1。

 So so let's let's prove。呃。Let's show that theorem two。Ily Sta one。So of course。

 in order to use it to prove theorem1， I'm just going to F1， F2， FT are all f。Okay， so start。F1， F2。

F probability would be equal to f。So then。What do I want to show。

 I want to show F of x hat is something。What's there of x side？It's f of the average point。

The function is convex。Function on the average is at most。The average of the function values。喂了。Okay。

That conveniently is the left hand side out here。So I can just rewrite the right hand side out there。

So this is act most now notice that if all the f's are the same the right hand side。😊。

Is like F of X star every single time。And so I'm summing that t times and then I'm dividing by t。

 so really this is at most step of x star。😊，Plus one over three times。Something。A G。Ata G啊。Be overdo。

Plus daily over to wait。 I might have to fix those things。 I， you know。

 I was reading them off from memory， so。啊。Okay。Good。So let's just look at this portion。

 this is just ata G over2。Plus。Be over 2，8。B or听。I'm just I don't know why I even did that。嗯。And so。

I should balance these two terms。So I should set them equal to each other so a。

Squared is equal to D over G T。Something like this。So Eta should be square root of the over GT。

So I should fix something up there， let me just look at my notes so that I'm not taking us on a wild goose chase。

I hate doing these parameters， but。Let's just。I don't want to。O。Let me fix those things。

G squared D squared。Betting。I just hold on to this。你出嚟噶。😔。

D d squared over to8 Okay good So this is G square t d squared t this this。

 So therefore a is equal to D over G square root something like this。Not important， but。Okay。

Now if I plug this back in。😊，I'm getting。You， I can take Ada and just plug this back into this。

So I get Eta。Both these terms are equal to each other。Okay。😊。

So if both these are equal to each other， then you know their sum is equal to twice the first term。😊。

So的那在在。This term becomes equal to。A or G squared， which is equal to。你。G overテ。S路地。

And now I'll say this is equal to epsilon。I just want it to be equal to epsilon。

 I will set it equal to epsilon。If people is at most epsilon， if P is at least DG over epsilon。

Square。Again。Just just doing the calculation。 there's nothing out here。

 There's no smarts in this thing。In fact， there's dumb mess。Yes。Good all I did was I just said， look。

 if S are the same， then I can the average point is at most the function value the average of the function value。

😊，And then I just use my guarantee， and I said parameters， whatever they are。忘了吧。ok。😊。

So I made a mistake somewhere out there so I should fix that。

This is going to be B and this is going to be G。I think that's pretty much。诶。What if。The online guy。

Imp playeded the offline。Okay， so I should prove to you the online。

The online guy is the one which is sort of more interesting， maybe。So let me。But， this's okay。

There's just some okay， let me prove for you the online right。So what's the online。

 so now I need to prove hereem。one。嗯吧。This is going to be a potential function proof。对不去。

K to thank you。There is going to be a potential function proof remember what a potential function proof was。

I'm going to define a notion of phi of P。And in fact， there is no suspense what I'm going to define。

 let me just define it for you。So this is equal to my point。X sub T minus x star。Squared。

Divided by28er， this happens to be the right quantity。When we first sort of came up with this proof。

 essentially we didn't have all this， we just said， oh。

 it must be the distance and then you go back and you say， oh。

 there must be a factor sitting out there and that happens to。😊。

And here's what I'm going to show you， I'm going to show you。Oh， so what is the initial potential？

The initial potential is going to be。Well， this is conveniently x1 minus x star。Squared over2 a。Okay。

Which in my language？Is equal to D is at most d squared over28。诶。

What I'm going to show you is that F。😊，嗯。At point Xt。

How much loss will it suffer it's going to suffer this much loss plus the change in potential。

Is less than equal to。我我 to show you。FB。Of X Scott。Plus。不点。I don't know what blessed be。Its bding。

I want to show you this quantity。And so what happens if I show this for every time。

 I'm going to sum this over all times。So I'm going to get summation Ft， x1。Thus， the final potential。

Minus the initial potential is at most the sum of Ft of x star。Plus， some。Black。对。The potential。

Is always not negative。So if something plus a non negative term is less than this。

 then clearly I can drop this and I'm not suffering。😊，Im even better。

So really and I can move this guy。😊，Do个 right。来啦。😊，All valid moves。O。This guy is the left hand side。

This guy is the first step one that I can say。This guy is the second term on the right hand thing。

This guy is the third tone that I。In fact。Blay is not even， you know。

 I'm going to show you that this is at most G squared A or v squared over to whatever。

So this is not even really black T， it's going to be T times black。喂。能装毕。No magic。哎。😊。

So I'm going to show you， yeah， so this is I'm going to claim it。一걸都话。Let's just prove this you know。

 sort of prolonging this makes it seem more mysterious than it is。

So it's a classic potential function proof。😊，So let's just do this guy。啊。

So let's first just take care of the change in potential。😊，And I should do this。

I should write alemma because。You'll see where this will come back。So I I'm claiming that fee。

B plus one。Minus the。嗯。We act most。Yeah。Bh。Plus。And this term will seem to come out of nowhere。

 but you'll see in a moment。哦，XD。X star minus X。Yeah。This remember is the inner product。

This is the gradient of f at xt and this is external minus xk whatever。😊。

This is just a lemma that I'm cleaning。诶。😊，So course they prove this level。

Let's prove the rest of the terror。嗯，Let's let's do it here。So what is f t of x t？Plus。

 the change in potential。This is equal to Ft of xt。Plus。啊。Graadient of test， F P。没法定。Add X。Heep。X。

Star minus X。点。Some of my Ts are moving up and down， but don't let that confuse you。

 superscripts and subscripts are fungible today。不用。I just wrote the second。

 the inner product term first and then G later。But what do we know， we know the function is convex。

there and that's the firstThis is， I just applied the language。😊，Thank you。外来吗？个人。

What's happening my function is convex。Oh。The definition of convexity says。

The function value at the point。X地。Plus。The the difference between Xt and X star。Times the slope。

Gives you a point， this is the linear approximation to F。

This should be lower than the function value a at X。Right。

This is just the linear approximation at the point Xt。Oh。Yes， no， maybe。Good。

We approve what we wanted to prove。FP extra， plus b。So it's just the land。Dlemma is a little linear。

 not even linear， right it's just algebra。😊，Okay。😊，'sWhat's happening？1 over data。

I'm just writing down a one over two acre I'm just writing down the definition of this thing and really I'm going to follow my nose there' is no place I can I can do wrong。

X。B plus1 minus x star。Squared minus x D minus x star。Square。This is the definition of the potential。

诶。😊，Good人。Now， if we ever see。This kind of thing， I want to use the fact。That okay。

 let me even just write it down。So this is equal to。Let me just look at this quantity。

The one over two eight are， you know， just carrying it around not a big deal， right？

So this is equal to xt plus 1 minus xt。Plus x minus x star。Square minus xd minus looks gone。Square。

And subtract nexting。Now， I do't know。That a plus B。

Quantity squared is equal to a squared plus B squared plus y。明咩。So a plus b squared minus。

B squared is equal to that。So let's just do that。Is equal to a plus b squared minus a minus b squared。

Is equal to。X B plus1 minus X B。Squared。Plus， twice。X d plus1 minus X X t minus X。

And now we are in this mess。What's the only piece that's missing？Yeah。

 we haven't used gradient descent so far we've been doing algebra without even looking at gradient descent。

😊，Okay。So let me。Just for a moment， forget about the projection business， suppose K is all of space。

Case like R。So then there's no projection。嗯ello。诶。So let's do this thing。This is equal to。Xt minus。

 you know， this difference is exactly negative of the gradient。😊，So this is。

Eta times the gradient of Ft and Xt。Plus。Twice the， twice later。Times the gradient。

But there was a negative sign out there。I can move the negative signs。Into the second part。

OkaySo I'm just I guess see you're sort of like pretending that you don't need to protect back in right with this why can't you just because I feel like the unprojected point is going to be further away so just that's exactly what we're going to do in 30 seconds。

You're one step ahead of me。O。So， but this one is just。You know。

 just algebra this is just substituting this is the first time the only time we are going to use the fact the gradient indescent step。

😊，你。😊，Now， what is left？Eta just comes out， its a norm， so Eta squared just comes out。

 this is v equal to eta squared and maybe less than equal to each of these gradient is bounded by our assumption。

So this is ata squared G squared。Plus。Two aer times this garbage。Well， it's not garbage。

 it's what exactly what we wanted。And there's a conveniently one over two eight are sitting out there。

So that's going to kill this， giving you the second term here。

And that one over two aer will hit this， giving you bout here。So I can just write as。Eta G squared4。

对。With that。😊，Ah but there one over two eight are sitting here。

 which is multiplying this whole stuff out here so that gives you this and that one over two8ta kills this one over two8 at。

😊，And really， you know， what you are seeing is we did this proof and then we say， oh yeah， okay。

 you know， I really need to kill this one over to8 so we should just kill by1 over two。😊。

And basically I'm stepping you guys through you know you probably never yeah wanted to sort of know about how to rederiveve this proof right it's like five years back I didn't know how to sort prove anything would great this so we just sat down and then the proof seemed a little mysterious to us and we sat and scratched our head and we said there is a potential function proof we got to prove it using potential function what it is。

😊，诶唔なこ。Let's do let's do gigin's idea。Okay， what did we use？呃。About okay。

 so here we said xt plus1 minus x star， you know， we could do the same analysis as we were doing out here。

😊，But we run into trouble out here because xt plus 1 minus xt and xt plus 1 minus xt。

 these things we can't replace by just this gradient。😊，Because you know。

 it's a gradient followed by a projection， you know， some weird shit going on。

So let' us do the following， so this quantity。😊，I want to say。Is at most。The same thing with it Kar。

And this is what Keegan was pointing out， let's look at this picture。😊，I have some convex body came。

X star is the point inside this convex body， this is where I'm using the fact that x star is a feasible point inside the convex body。

😊，X3 plus1 tilde might be outside。I'm projecting it back。On to X t plus one。

What does this projection mean， it means that this is the closest point in this body to xt plus 1 kilde。

 so it's an orthogonal projection。Basically， Ill look at like a perpendicular out here。

 the entire body should lie on one side， xt plus one should lie on the other。😊。

And maybe in order to make this mold where all let's do this thing。And so now。

This first line is looking at this distance。This second line is looking at this distance squared。

The second line is looking at this distance squared。Yeah。This green point must be larger than this。嗯。

Okay。And this is often， you know。Basically。This angle here。

Is an optus sand basically this has 90 degrees right there。So to go inside。

 it must be an obviousio angle。So an opt angle make sure that Pythagoras is working in our favor this squared。

Is greater than this squared plus x squared。😊，So this is you know the kind of inverse pythagore and acute angles would mean you know this squared is less than that obtuse means that the green is bigger than the pink in fact the green squared is bigger than the pink square plus the white square。

😊，So this just says that you know， from here to there I could just replace the Tider and once I have the Tiders。

 then I'm in great shape。Then I'm back to previous mouse。Okay。So far so good。You're mostly happy。

And you might say， why did we do all this work，Sure， it's a good algorithm。

 but is it worth on this time？😊，So the thing is you know， this is sort of a general framework a。

 now you've seen the proof of gradientding descent someday you might use it， I don't know。😊，啊。

LetLet's pull out one more thing out of gradient decent， by the way。Let's pull out another。

 no regret angle。Low regret algorithm， whatever， you know， people call it no regret， right？

But anyway， proof we happy， right？😊，So I'm going to just remove the proof here and this proof was anyways kind of in。

We just use con a couple of times。So。Yeah。So let's just go back to our inner product game。

At each time。We play。A probability vector inside this。Probbilities in。We get back。A loss vector。诶。

With pay。And I'm going to write this suggestively Ft of xftt of P is equal to。

Inner product between LT and ET。And then we rejigger our weights and we go back。Okay。

We start with the probability vector P1， we get loss vector L1。😊。

We pay the inner product between them and then next time we again need to give a probability vector loss vector。

 etter。Theres context function。On a convict thing。We can use theorem too。The theem 2 says。别错了。bye。诶多。

Sumation。你点对机。I that most。So fraud。Any point P star belonging with the probability simplex。

This is at most LP。Be star。Plus。Plus， let's just figure it out。Data over2。

I have to worry about the gradients。We will come to that。呃，DD。Plus。The square over to wait。

This is a regret as before， right？😊，Remember， we had an algorithm which gave log n over aer Eer is the same as epsilon out。

😊，对。嗯。o sorry loggan。哦。Oh yeah yeah， so previously I should this right previously。We had regret。

offff。Eppsilon T， I'll just call it8 or t， maybe I'll just call it epsilon。Plus。Log and。Over Epsilon。

This is our previous regret point we had these two terms， then we balance them out。

 we got square root log n over e or whatever， not important。😊，Now we have instead of this term。

 we have this term， instead of this term， we have this term。

 the ata and epsilons are playing the same kind of role。😊，It is the same road。

 there's no difference and we'll come back to this in a moment。What is this behavior。

 so this is saying a T over 2， the two is again irrelevant， not important。😊，Okay。啊。

What's the gradient， what's the norm of the gradient？

So let's actually say what is the gradient of FT Act？啊。并。I'm just taking the derivative， you know。

It's dis empty， right？LT is the vector which is bounded between0 and 1。

What's the maximum Euclidean normal can have？Square root。Square root and squared is there。那 so呃。Good。

Good， okay。Plus呃。The diameter， what's the maximum， what's the diameter of the probability simplex？

Like squarel two or something like that， right？Probbil simple sum between 01 and 10。no， in this case。

 it should be just like constant。So basically， I'm saying what is the。

Like what's the maximum distance I can get between？Am I fooling myself？

Well the simplex is defined as。All points x in01 to the n， such that the。TheX呃 XI。Inqu。Just one。Yeah。

 maybe two or square root two， something like that， I mean I think will yeah。哦。诶。😊。

And you can sort of balance these two things out well okay， let's just balance these two things out。

 right？😊，Is equal to eight or squared no，8 or squared。嗯。SoTherefore。

 you set Eta to be equal to1 over square root p n。To get。Square root of and over。And here。

Se Epsilon2。Sre root log again overD。都。哦。To get。S点。好。So here we were getting a regret。😊。

Which was something like this here we are getting a slightly different respect linear in the number of experts instead of logarithmic。

 but hey。😊，We were using technology from the 1840s。That we should be happy。Good。And moreover。

 the sort of the issue that comes up is that really we are not using， you know。

 this holds true or any convex body you can come up with。

 we are not using anything special about the probabilitybil。😊。

And making this connection was exactly what。LED people to think。

About the next concept we'll talk about， which is mirror descent。

And it's an idea that goes back at least to Neirrovsky and Yuin from '84。

 though if you read that book， its' it's kind of。A little hidden in there。

I in they clearly are talking about this thing and but they quickly move on， theyre like yeah。

 this is all trivial stuff， let's talk about the real stuff。😊，做啊。Okay， but let's talk about。

 you know some of the trivial stuff。😊，So far so good。So let's， let's do。Let's do very de。In fact。

 let's take a two minute break。This theorem， actually I don't even know what I'm going to be raising。

Maybe I'm would just keep that termem for。啊。Maybe I'm gonna keep。No， I don't know I shouldn't。

There's almost nothing I can erase。I'm painting myself into a corner out here。好。

That'll be right backward one a second。来。Yeah， they're catching up with like a next star that serve somewhere and also really inence。

How do you mean catching up so it's like X star here switch so it's like we like think X star the plays that minimize with the sound what about like an X star that like also does the same weight distance so I think that that like all reading the and stars are the same。

Right。last that is so the real issue is that we don't see Xt until we don't see FT until after we play Xt。

 so if we are comparing ourselves to Xt star。whichch can depend on FT then we have no hope like update so the question is how do you how do you constrain yourself to。

Basically， what I can do is I can always give you two convex functions。😊。

Or I can give you many convex functions and each time Xt style is sitting at a minimizer of that。

Oh yeah， you just it over Mexico circle exactly or I'll be going there， but you'll become yeah。

 so so basically it's almost like predicting the future and you won't be able to do that it's yeah in that case the。

😊，What。So good。Let let's get back to business。So you know。

 this is the classical explanation of gradient descent and for the rest of today's lecture I'm going to not talk about the constrained version。

 let's just talk about the unconstrained version， so un'constrained。😊，And I'm going to give you。

A different view of gradient descent it's the it's you know， it's it's the same。

So here's what I'm learning。I'm at Xt， I want to get to Xt plus one。嗯。I will say Xt plus1。

Is the a men。bo。Well。F0。At X， P。Plus， the gradient。Of FT at XT。X minus X。

So this is I'm choosing eggs。This is。A linear approximation。

 this is the same linear approximation that I probably era， right。😊，This is Xt。

 I'm taking a linear approximation of the function FftT。This is the linear approximation。

And I asked for the argument of this thing。Now， this quantity you will say is boring because it's a linear function。

😊，He'll go off to negative infinity。And of course， this approximation is good only in a small region。

😊，Around xt， so let me penalize view for going too far from xt and let me say。X。Minus x。Squared over。

There is a penalty function for going too far from X。Eta is like the step size， right？😊。

But eight is saying， look， if eight is tiny。This is kind of like making this second term very large。

I'm putting more mask on the penalty。 I'm not allowing you to go too far。 You will take small steps。

If 8 our infinity essentially if 8 over 0， this term would be the dominator。😊。

This would go to infinity， you would not move from X at all。So this is some optimization form。

This is often known as。Bocks。Step。I took a linear approximation to my function FT。Plus。

What we call a regular riser。A penator。This seems like a reasonable algorithm， right？😊，Actually。

 it's the same alpha。So let's look at you know this is a convex function。

 this is the linear function plus a convex function is convex。😊，So I know it's optimality conditions。

What are its optimality conditions， I'll take the gradient of this respect with respect to x and set it to0。

😊，The gradient of this thing is it's a constant。Is relevant。So this is just a fixed constant。

 it doesn't depend on x。The gradient of this is really gradient of FT。At X点。

So I'm saying whatever this function is， the gradient of the prox function。Is equal to this。Plus。

 one over theta times。The gradient of。This quantity。Is。This is， by the way， the gradient of。

X squared is equal to 2 x。And we always find this too annoying。

So that's why we always whenever you see， you know， text quantity is squared。

 you always see a little two sitting there。😊，This is just to handle the fact that this gradient becomes x in general。

 if you look at the gradient of。X p to the P。You'll usually divide by p。And so in the end you know。

 this is just， what can we？O。So the gradient of this guy is just。X minus x。

I want the minimizer of this function I'll set it to 0 for the minimizer。So what is this saying？

I want to set this to zero。So x minus xt。Eta I should move that guy over and we will see that x is equal to x t minus a times gradient os。

Okay， it is on the final legs of its slide。Same problem。Weer。

So the prox version of gradientd descent is the same as。😊，The standard。

Local search version of creating。And I find this very sort of very useful to think about it's really like。

 you know。😊，I really want to minimize FT。😊，I don't really have a good handle on FT。

But I want to minimize death， you know， FDF， it's not important。

I want to minimize if I don't have a good handle on enough。

 so let me take a linear approximation around what I know， I know the function value。😊。

And I know the gradients so one thing I did not mention was that in all these problems we are kind of assuming access to gradients。

😊，You can give me the gradient at that point。What happens if you don't have access to the gradient。

 we'll talk about that maybe later on。By the way， also these are called first order methods because theyre dealing with gradients。

😊，You can talk about zero if order methods which don't have access to gradient just function values。

😊，You can talk about second order methods which use the gradient and the hessian。

The first and second elevators。Those are typically faster。

But right now I'm talking about first order methods， this is just saying take your function。😊。

App approximateimate it around Xt and add a penalty for not moving too far。

This is just gradient different。Simple。And if you said， well， argument x in k。

 you'll get pretty much the projected gradient that we want。😊，I believe that。Exes。Yeah。

So this leads me。To how I view what what is called mirror riskcent。It'。less mysterious this way。

All it's saying is， look， I'm going to measure distances not according to the Euclidean node。

But according to some other notion of distance， in fact。

 I wasn't measuring according to Euclid didnt know I was looking at the distance squared。

I want to get another notion of distance healthcare care。Which is more suited to my needs。

 whatever my needs might be。So that's what we'll do， so let's let's actually。😊，Do this。

 I'm just kind of asking you to remember this a little bit， I should have。😊，it as about hospital。

Good。So that notion， so in general， here is what's going to be mirrored in this。The name is weird。

 let's not worry about that。XD。Plus one is going to be arg min。Off。You know， FT of XT。

 you I'll write it down， but it doesn't matter， it's a constant。

 so it's not part of the argument anyways。A gradient of F t at xt x minus xt。

 this is just the linear approximation of the function Ft。Plus1 over Eta。

Times the notion of distance。Between。The point x， so we are taking a min over x。Of x from x3 minus-1。

I've defined a notion of distance， it's an abstract notion of distance I'm defining。

And what happens is people change this notion of distance to get back various update rules。嗯。

For example， distance between x and y。Is equal to x minus y。square有嘅度。Cllsastic gradient decent。喂。

有啲过度。The Kl divergence between x and y。This happens to be a perfectly reasonable。

Notion of distance that we can use we'll see some properties that we need from our notion of distance and this will satisfy this for x Y belonging to the probability simple。

😊，So if your points belong to the probabilityba simplex， you can use the KL di versions。对。

And if you use the k divergence， let's see what comes over。😊，So let's do our same analysis。

 this is the prox measure， right？😊，Yes。So I want to take the gradient of the pros。

The gradient of the prox is equal to。FP of X P。Thus。1 over eight are times。

And now I need to take the gradient of the KL divergence。And of course。

 we've forgotten what the K diverg first， let me remind you。The K divergence。Between X and。

X d minus1。Well the sum in fact， let me just define x and y is the sum all overall coordinate I of Xi log Xi over Yi。

Remember， in our minds， x and Y belong to the probability simple。

So what I could do is I could say this is minus X plus Yi。The sum of the Xi will be1。

The sum of the Ys will be one。This is just， you'll see why it comes out。

 it just makes the algebra slightly clear。😊，I want to take the gradient with respect to this， right？

😊，So what's the gradient？So the gradient of this care。

I'm taking gradients with respect to x remember。Of x with respect to x d minus1。Actually。

 let's just do it with respect to why。Is equal to。啊。What's the gradient the gradient vector， right？

I'm looking at the I worked。So I'm taking the partialcel with respect to XI。

What's the partial with respect to Xi， all the other terms will go away only Xi log X over y I and minus X plus Y I will remain。

😊，So I'll get log。Exile over Yi。Mイus。好了。1。Or sorry plus one。M one。Let me do that a little slowly。😊。

Okay。I partial with respect to this， just gives me the second term。😊，Partial with respect to this。

Will， give me。哦好。Plus。Xi。Times。1 over Xi because it's the log X。咁。Yeah。Let's just do x log x over C。

Minus x plus。I'm taking derivatives。I always get this wrong， so I just have to make sure。

So this is just。攞一个。Thanks over。Plus， now I need to take the derivative of x over log x over C right but it's really log x minus log c log C part is。

😊，啊。Not important， so I'm getting x times d d x of log x minus log C。Minus1 from this。Okay。

 DDx of log x minus log c log c is the constant， not important。Log X is。他。Yeah。

 so this is just one over x。So x stands 1 over x is 1 minus1 is0。Okay见。No。Excellent。Long story short。

 this is equal to log X over。😊，Okay， good。Plus one over there yeah。Log， X， I。嗯。

This is a vector where the I coordinate is。X I over x in X T I。It一过就。嗯。对。Good in mind that why。

Hang on this plus one over  eight or times this vector is equal to 0。😊。

So let's look at the I coordinate。And whatever this vector is， let me just suggestively call it L。😊。

It's a gradient factor， but it's just error。😊，Right。😊，L plus this vector equals there。😊。

So what is this saying that the ifF coordinate all plus 1 over8 times？Log of X I over X D I。1 equalゼ。

そう。Log of X， I over X D。Is equal to negative eta。带来。X I is equal to X D。E to the minus ata。

You've seen this before。Okay。This is Hech。Hedge says。The IS coordinate。

You'll multiply by e to the minus theta X。We've just redeiveed hedge。From this general little thing。

It you said。This distance function to be careful， you get hit。If you set it to Euclidean， you get。

A greatd in center。Or you want to work with positive semideite matrices of unit trace。

You choose something called the one Neman entropy and the KL dirgence that comes with that。

 you put that， you get another。诶。Another notion of。Multiply two weeks。

So that's what meritscent this is one view of what mirror disscent is doing。

 I can give you another view， but let's just make sure we are happy with this view。😊，Yeah。

The Ttem says。This function will be a nice function， I'll explain what nice is。

As long as this function is nice。😊，The update rule that comes out of this will have some regret guarantees exactly like this。

😊，So let me write down the guarantee that get for that I'll need a definition。

 let me give you the definition and I'll just write down the guarantee and then we'll be done because we won't have time for anything。

😊，AndI don't have board space， I would have loved to have one more board to keep this around。

 but I don't have gold space such is right。对。呃都可以啊。One definition。

 it's not where at all let me define。This notion of a fragment divergence。Fancy name very simple。

Let H B。A going expansion。Okay， so in my mind， edges like that。What's the pregnant divergence。

 so the pregnant divergence will always be written as D sub h。Of two points， x and Y。It's asymmetric。

The KL divergence was asymmetric。So it could be asymmetric， it may be symmetric， you know okay？😊。

Is defined to be what？So I am going to take。The linear approximation of this function edge。

 this is the function edge， I'm going to take the linear approximation and y and look at the error。

Add X。When。Approoxximating。Next one。What's the error， it edge of x minus。

The linear approximation h of y。Plus the gradient of h at y that's minus y。It's that picture。哎。

That's the bigman name。Fancy names em。不以。What's a。O。So a function is called strongly convex。Okay。

Strongly conx it grows off to infinity fast。How does it grow so this sense。

This is a definition it's equivalent to the standard definition dx of x and y。

So function is called alpha strongly convex， if it's convex and furthermore， actually。

 this implies convexity。The error is at least alpha over 2 times x minus y squared。

This error is at least quadratic。😊，Is growing off fast。Okay， actually。

 I'm sneaking in something out here with respect to norm。😊。

You can choose what norm you want that norm is the one norm。喂。对。

So this function edge is going off to infinity at least quitedraly。It's not flated。

And the theem says。人家不 don the铁冇天。Okay them says。The boys。Edge is alpha。Songly。Gone vi。

With respect to some norm。哎。😊，Then。Mirred descent。因为。呃。Distance。The edge。

This is the function I'm using in that definition out there or wherever that definition was。😊。

So mirror descent with this distance just means。I am。成。啊，可。我X。O。Instead of using the Euclidean norm。

 I'm using this distance。Then mirror descent with this satisfies。Sation F of X。Is less than equal2。

Sation that be of x star。Plus。And now。Remember， our previous things depended on the gradient of the norms of F。

And the distance between x star and x。Now， again， we'll have the same kind of thing。

 so let's do the second term first。This is going to be the edge between x。Stop。And x1。你系你系 a噶。

Notice that if the if we were doing edge， you know the this distance function being Euclidean squared over 2。

 that would exactly correspond to that term。😊，好的。Look at this。でした。那有肯定是的。Okay。😊，Plus， and here。I me。

你 might be啊。😔，There might reason I was not sitting on that。Very quickly。那好，就是的。Plus， pay times。

Now I need to control。The gradients。喂。😊，So I need to control the gradients。

 how should I control them？Well。This time I'm going to control them the following way。

 it's the same idea。啱。唔知。Squared。Gance。嗯。Over。To alpha， remember， alpha is alpha strongly complexex。

哎。Where。What is G G the bound on the gradients？诶。😊，点知。Is an upper bound。On the gradients。

One minor thing。We are working with general norms。Then the gradient is really， it's the derivative。

 right？😊，It's the function in the dual space。Because really the derivative in high dimensional space is basically saying。

 oh， if you go in this direction。😊，How is the function changing limit。If you go in this direction。

 how is the function changing？It's a linear function。

And it's literally this sort of an object in the dual space。😊。

So you always look at the dual norm and if you've forgotten what the dual norm means we will define it moment gradient so right now I've defined it this way but if the gradients are bounded then the function has then the space has to be bounded so there versions of this of this theorem for。

Constrained optimization。But this theorem you're right doesn't make sense in the nonconstrained setting。

 but at least I can state it right now and then worry about it。对。So so far， Midesscent， I'm saying。

 look at the analogies， it's the same。Ping。Two differences。

The distance between an x1 and x star is measured according to this。Is this divergence？And secondly。

 you are measuring the gradients in the du or not。And if you're okay with this。

 let me just give you the punchline。So the punchline is what's the punchline？

So let's look at this theem， in fact， you know， all this garbage you've already there。

 so let's just look at this theem。So let's look at what impact， let's do it here。I use job okay。

微微就分好的。ます。4our minutes， let's use a different amy。Okay。This day。Let's use。The L1 norm。Remember。

 we were working with the probability Sx， we were doing linear optimization， right？😊。

The L1 norm seems more suited。2。Probty vectors。All probability vectors are1 norm more。Back one。

The clear divergence。Is strongly converse， so actually let me not even say that so Kl between P and Q。

I at least some constant times， I forget what this constant we can look it up on Wikipedia p minus q L1 norm squared。

This is known as pinkers inequality。And he's pulling this out of a hat。😊，Wiキピリヘドペジンです。

So it is alpha strongly convex for whatever this alpha is。

 maybe I'll just call it alpha over2 for some constant alpha。So this constant will become a constant。

Good。So now it just comes down to figuring out what this distance is and what this gradients are。

Secondly。What's the dual of the L1？呃 non。Does anybody know of fact？

The dual of the L1 norm will be elements。😊，So I am measuring the functions。

 the gradients of the functions in the L infinity node。Remember what our functions were？把光线出另你了。

And their gradients were just the loss vector。And the loss vectors were bounded between 0 and 1。

So the infinitefin enormous one。So this term is only going to give you A or t over a constant。

Pretty much like8 or three。😊，What will this term give you？

It will give you the KL divergence between x star and x1。嗯。So let me just write things down。啊。

eta g squared t over2 alpha whatever is equal to ata t because the gradients are bounded by 1。

Alpha the constant。Plus the care divergence between。X。Star。And x1。Over a8。Okay。😊，What is x1。

 what did we choose x1 in our standard hedge analysis？好。Yeah。

 we chose it to be the uniform distribution。So what's the KL so it's plus？

X star I log X star I over the uniform distribution。

And you can convince yourself that this quantity for X being a probability。Wector为 Musloggan。哎。

So this when the dust settles， this is all divided by a。So when the dust settles。

 this is saying order ata t plus log n over eta， which is what we had earlier。

It's the same analysis to just repackage in this way。

sorry's the denominator in log so see I was taking the KL divergence between X and x1。

So it's x star I。Xta I over x1， the IF coordinate， but x1 the IF coordinate。

 we chose to be the uniform distribution。So that gives the one over end that and comes up there。

 and now I'm just left with this。XA log X， which you can show that most log。Okay。Good。

Maybe I'll stop there but the sort of point I wanted to make was that this middledesscent framework。

Kind of captures hedge as a special case。 it captures gradient descent as a special case。😊。

And you can use this general idea to sort of then explore further。

 you can change the regular arrival。This， this kind of term。

To different distance functions as long as and if you want to use this theorem， of course。

 you just need to make sure that the distance function you are choosing。

It corresponds to a strongly convex edge。嗯。Yeah。😊，So what I'll do。Let me stop here。😔，嗯。Yeah， will。

We'll see what next to do， theres various directions in which we can go。

 we can try to speed up these things。We can say， look。Right now。

 our convergence guarantees all look like。1 over epsilon squared this kind of guarantees can you do faster if you assume a mold you can do more。

 but maybe what I'm going to do is I'm going to stop with these first order methods which are just using gradient information。

And next time we'll do just minimizing convex functions。Strongly poly， but not strongly poly。

 What a poly diameter us。And then we'll go to linear programming and so on so forth。

 then we will start going more， we'll drill down into maybe higher order。Methods so let me stop here。

 I hope you guys have a good spring break and you get some time off and I'll see you guys on。

Intenious or not。