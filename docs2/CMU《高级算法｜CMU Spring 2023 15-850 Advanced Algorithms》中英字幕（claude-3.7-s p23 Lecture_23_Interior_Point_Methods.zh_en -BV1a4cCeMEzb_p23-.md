# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p23 Lecture_23_Interior_Point_Methods.zh_en -BV1a4cCeMEzb_p23-

So。Welcome back， guys。Interpoint。This is pretty much the last lecture on solving LPs we've seen how to solve LPs using multiplicative weights。

 we saw how to solve LPs using ellipsoids and centroids。😊。

And I'm not going to talk about perhaps the most widely used LP solver， the Sx method。😊。

It's you can do this in Excel， you can do this you know their online software not。😊，Great in theory。

 excellent in practice。Understanding the behavior of Excel you know being able to say why Excel behavior of Excel you know we won't say anything more but behavior of synx would be awesome and there's some some directions on that smooth analysis is one way of doing this maybe another lecture。

😊，Today we'll talk about interior point methods so actually maybe a very quick word about the history of LP solving so we saw 76 Kachan gave maybe I right out here。

 76， maybe 40 something I forget 46 47 Danzig。😊，Gave the simplex algorithm。嗯。Is used for a long time。

 then people gave examples where the simplex algorithm performs arbitarily bad。In theory。In fact。

 the simple yeah， long story again， so in 76 the first polytime algorithm was giving this was the kon algorithm。

😊，And then in '81， I think 82。Car marker。He was just finishing his PhD to Berkeley。

 he gave an algorithm， he called it an interior point algorithm the algorithm had been around for a little while but he actually showed polynomial runtime he also made you know strong claims about the practicality of the algorithm。

😊，Which were perhaps optimistic。But then over time。

 people realize that actually these interior point algorithms are very powerful。😊，And so。

You know this is some of the technology that that's actually used in some of the past disk。😊。

LP solvers out there and I'll give you maybe a high level idea because you know。

 there's there's a lot to do and。😊，The fastest in theory， they're actually pretty good in practice。😊。

So it's a good combination， it's good in theory and good practice。And it depends if you try Gurobi。

And you can set the parameters and often it will do simplex and dual simplex and various other things。

 but it will try with interview point methods as well。😊，啊啊。

Okay so so today I'm going to tell you at least the main idea behind solving LPs using interview point methods they are also used for convex optimization it's a very general idea so you'll see what's happening and basically I'll draw one picture which will be you no pun intended guiding principle for the rest of it。

😊，So， here's the。Here's the picture， okay， so what's the picture？😊。

I want to optimize this I want to optimize over this。Only top。And I want to maximize。Minimize。

C transpose x x belongs to and I'll call this P today just just for you know。So what do I want。

 I have a direction。I want to go as fast far as I can in this direction， I want to get to this point。

What I'm going to solve instead is I'm going to solve a so called regularized problem。

Where I'm going to take this problem。And I'm going to add in。I'll call this one over8。嗯。Thanks。嗯。

8 at times。A function B of x。Which is so so this is often called。😊，A barrier。And what this function。

 the property that will have is that this d of x will go to infinity at the boundaries of this poly。

😊，So you should think of this function as just heading off to infinity， okay。For instance。Be of x。

Could be。Let's say， some of it。Log off， there are all these constraints I going from one to M。AI X。

Minus B。Okay， ignore that， tell people's moment， just look at this now。😊。

So suppose I wanted a constraint。AI X， okay， maybe I'll just flip it along B minus AI。Transpose X。

 I wanted AI transpose X to be less than equal to B。So as long as。You know。

 once once AIX starts getting close to BI， this thing is going to zero。The denomininate is going to0。

 this term is going to infinitefinity。😊，So if you were satisfying this constraint and you started getting closer to that particular constraint。

😊，This this term。Willll stop you， it's a barrier。And that's the whole thing all these guys are barriers one of these terms is going to go off to infinity now on each phase。

😊，So。If eight are large。Then essentially this term does not matter really what you are trying to do if you are trying to minimize the barrier。

😊，You're trying to just stay away from the corners。

 you'll probably be somewhere in the middle of this polytop。You at some point， which we can call。

嗯 various names， I think。Analytics center with respect to this barrier。Different values you can have。

 you know， why did I put a log， maybe you shouldn't have a log there。😊。

Maybe you can put a square there if you want to know various barrier functions。嗯。So when it is large。

You are really focusing on this part。And then you can say， well， suppose datata changes slightly。

 then maybe finding the best solution for some value of Eta。

And finding the best solution for some value of Eta minus epsilon。You know， given this solution。

 maybe I can find a solution like this quickly。Nicely， whatever efficiently。And so as I reduce ata。

To0。I can define the optimum of this thing， so I could just say x sub Eta is equal to r min。

For a particular era。E are being large， it's got nothing to do with the problem itself as in nothing to do with the objective function only to do with the polyto。

You're sitting in the middle。And as I'm dialing aer down， you are getting closer and closer。

 finally when a is0， this is not important， it's only C transpo。😊。

And the whole goal is I'm going to start walking along this path。

That path is called the central path。😊，The central point。And I'm following this part。

 hence part following methods。😊，诶。That's going to be the whole goal。

 this is going to be the picture you keep in mind and we'll see how to make this work out。😊。

So there are various questions。How do you find the starting point？Given a solution x Eta。

 how do you quickly find an x theta minus epsilon or some small epsilon， let's say？In fact。

 you would like a epsilon to be large， you are making large steps。😊，Okay so from x theta。

 you want to get to x theta minus epsilon so you you know the question one find。😊，Starting point。

 maybe I can even call the starting point X。Infinity， what对。Secondly， given。X datata。好。Large。

And epsilon。Can we find。X eta minus epsilon4。I would like to make a large step。

How large an epsilon can I handle？Using my technique。And then the third thing will be going to stop。

Okay。😊，So I start off in the middle， I keep making steps each time and then I stop。😊，Okay。对。

So as with the previous lecture I'm going to you know give you a very impressionistic view of maybe you know all these three steps because you know it's somewhat technical。

 but at least I want to give you the main ideas and I want to give you the pictures I have in my mind。

😊，That should be useful。There hopefully should be useful。Questions about this high level。Vaig。

Its a roadmap at least。So why are we doing all this basically projection is hard and in general the ination is these combinatorial constraints are hard。

😊，The structure of the polytop is some combinatorial object， which is hard to deal with。😊。

I want to deal with like smooth versions of these things。And lose some。Great indeent kind of things。

It's another sort of thing to keep in mind。啊。Yeah。Maybe let's just go at that。This this path。

What we find it unique and is there such a unique path if we start with any arbitrary point so here I was defining the points the the starting point as being the point the minimizer of this thing when essentially。

There's no term like this and I'm just minimizing the barrier function so that will give a unique point out there assuming that B is you know strongly convex or something and you know in fact if b is strongly convex and I think this path must be uniquely defined let's。

😊，嗯。Yeah， I guess I'm wondering。In prior and might just am might not have guessed that that finding a particular point and taking a particular path would be so important。

 I might I might have thought of gosh if we have some way to start from the inside and that an interior path that's great that can I just do it from any point so the good yeah okay so so what's what this is telling you is somehow。

This function will be able to guide you you know it's you know I need to somehow end up out there and the good thing is that when Eta equals 0 this is the right ending point so let's just find some starting point。

😊，Wwhichch is just coming out of this barrier function， you change the barrier function。

 you change the analytics center and then this is somehow giving you a gradient in which to move。😊。

So if I just view somehow the gradient of this thing as a function of theta。

 it's kind of giving me a direction in wish to move。😊，Good。O。So let me okay。

 so then let's get to business。😊，And let's talk about this pair of it。I want to solve this therapy。

 this is the problem I really want to solve。😊，Mim my C transpose x， a equals B。😊，So the picture is。

And I have。I have a plane that's cutting the positive quadrant。Possibly working。

And I'm just looking at the positive part that。This is this region。AX equals B。

It's a slice cutting through the。Was it a about thing？And I'm just looking at this positive part。

 x is not negative。And I'll call this region。对。I want to minimize C transpose x over this region。

This sloy barrier。No， not barrier， the sloppy region。

And the dual all of this is this quatic its see it's just you know syntactically I just took the dual and minimize de transpose y the de transpose y is at most c。

😊，These were equality constraints， these are unconstrained。是ir。

For convenience and is this is like a standard trick that you would have seen earlier if I don't like inequalities。

😊，I can throw in。A set of variables called the slackla variables make them zero。

And said the slack variables to be non negative。Kind of a standard trick。LlP 101。

Some of the slack variables are going to be kind of the sort of first class objects class。😊。

So let's keep these guys around。And Ill call this duall。This region。So I can define this thing。

 so p is the set of all axiss。And p is instead of all xs such that ax equals b x is more negative。

And the dual is actually the set of only the slack variables such that there exists a y。😊。

Such that a transpose y plus S is B equald to C。This is not negative。

So I'm looking at just the slap portion of the dualls。And just the x of the prims。

We are two polyto have defined。I听。Polyhedro and I think。没 good。😊。

I can define for each of these things be not。To be the the， you know the。

Thing I'll just write it out it's act such that， you know what？So suppose I were to drop。

The equality part， strict inequality， the open set。Bオか。喂。你我。These are both n dimension。过れ。

So this is a subject of R and this is also a sub of R。😊，Fair enough。sThe goal as it searching。Yeah。

 so so you you look at why。They have many more constraints with the slacks。

There's one constraint out there for every variable out there。

So S and x are in the same dimensional space。And in fact this this will come up again and again。

 you know， again and again， we'll take S and X and we will do something with that and they are the same dimension so it's good they talk to each other。

😊，The P&D， the open sets of those， by the way， one thing I should mention is that my my notes that are there on the webage that I wrote last year wasn't satisfied with them。

 so I'm trying to do something slightly different。And I'm following these sort of newer set of notes that Yenta Lee wrote。

 but I' am also deviating from those so you know we'll see how it goes so please do ask you know it's all kind of fresh off。

😊，Presed， so to speak， not even on the press。That'， okay。The P and D are。Different。Be good so far。No。

 no， no tricks。对。What else。So here's the's the， you know， here's the fact， for instance。

That if suppose。X。Is a primal solution。Why is the。S is。Dual solution。 Okay， what do I。

What all do I want to say？Okay， so let me say。That。Y and S。啊。Lon feasible。Then。C transpose x。

See I'm trying to minimize see so maybe one more picture to keep in mind， of course。

 and this is a picture you always keep in mind。😊，That， I'm trying to。Minimize sea transpo。

And I'm trying to maximize。Be transse fly。The objective function is increasing the objective function is decreasing act by strong duality they'll be the same right that's what we are aiming for。

😊，Okay。So I want to say C transpose x is at most。B transpose y。Plus x transpo S。诶。

And this is the the the proof is， you know， I'll write the proof， maybe I'll really era it later on。

 you know， this is just。😊，嗯。So how do I prove this thing？I say C transpose x is equal to。Now。

 C v equal度。A transpose y plus S transpose x。Just by feasibility out here is equal to y transpose ax。

Plus s transpo x。But a is equal to B， so it's y transpose b plus S transpose x。Okay。Good。

This is a primal solution， this is a dual solution。😊。

We are saying that this primal solution is at most this dual solution plus。Ex transpo。没有。So not。

 by the way。That。You know， I'm assuming strong duality out here， let's say for the moment。

Then this says this is at most， so this is for any two feasible solutions。😊。

This is at most B transpose y star， the optimal dual solution。Plus x transpos。

 this is true for any sort of dual solutions like this。

So if I take the solution that maximizes this quantity， it's only smaller。😊，But I know that you know。

 by strong duality， this is equal to the optimal value of the LP。😊，Plus x transpo。Actually。

 I could have just used weak dual。So point。My solution。If I gave you an X and S pair。

My solution is not too crappy。I'm trying to minimize it， right？

This is the smallest it can be and crappiier by extra transpos。Ex there。Thisは this thisは。Thank。

So basically I'm saying， look。My solution is not much worse than the optimum plus this gap。

And this is often called。The dwell。Gap in this setting is the duality gap means various things in various settings。

In this case。Okay。😊，So I'm coming up with solutions X。If I can show you。啊。And S。

Which such that YS are dual feasible。😊，Then my solution is not too bad， it's close to the opt。

So if I could set x transpose S to 0， I'd be that。And this is really complementary slackness。😊。

So here's what I'm going to do。I'm going to supply of attack。没。嗯 go back to here。啊。Oh。拉了。

I'm going to keep an X and an S。And these are going to be in these open sets。Okay。😊。

I'm going to keep an X and S pair at every time。Remember。

 S just means that there exists a Y that corresponds to it。😊，That is that makes the dual feasible。

W are we using opens like politics？Good， so there is going to be the problem that the barrier that we set and things like that。

😊，It'll all go to infinity at the。And things will become annoying at the boundary itself。

So what we'll try to do is we'll try to stay away from the boundary。We'll get very close to it。

 but we'll you know still stay away from ground we'll always try to stay in the open future。😊。

And in fact， I'm going to assume that both the both these sets have non empty open。😊，Regi inside。

They have interior。B利 what产 to。You say what happens if not， if's complicated enough， we deal。

Those things they're specialists dealing with them。Not to。So here is what I'm going to do。

 I'm going to always stay so really I want to reach this corner but I' will never reach this corner I will just get very very close to it。

😊，And then we'll do some other tricks like snapping to the coronary and the last time we talked about some。

嗯。So we're going to always walk in the open region。And at every point in time。

 I'm want to maintain an x and S pair。And Im going to try to basically。

So maintain Xs investing this at all possible times and then ensure。That x transpos。Decreed。

And the final， you know， final。Ex transspo is less than epsilon for some teeny， tiny epsilon。

 one over polynomial one over you know polynomial largest number that can happen and things like this。

Okay。😊，X will be feasible。As will be feasible。This is what's going to happen。So far so。

 I'm not saying very much， but I'm just setting the stage。😊，好一个。

Maybe I'm belaboing the point you guys might be getting bored。But。Okay。

So let me define the central particle。Do the central part。Two definitions of the central part。

Definition number one of the same group。It's a said， it's bears。X。Yes。It belong to。Sas that。嗯。

One more thing I forgot to mention。Im going to do weird things with vectors。

So I'm going to define a notion given two vectors x and y。

And I'm just going to write x vector y vector。嗯。This is， you know， there's no inner product。

 there's no transpose out here， this is just a new vector。😊，Whose components are X I Y。

 it's just component wise。かなんです。Maybe I forget what it's called for being his product。

 has a mind product， one of these products， not important。This component was。And similarly。

 I'll often say x divided by y is just the same thing。😊，Makes my life easy。

As always the all one vector， this is the all one vector and this t times the all one vector t is going to be a scalar for us is going to be PP。

😊，你嘅。😊，So I'm going to define the central part to be all pair xs such that x vector S vector。

Is equal to。啊。T times the all one vector。Okay， this just means。X times S is equal to T for every guy。

And T is quickly great。This is， I'm defining the central path。I want to stay close to this part。

 you'll see why。Yeah，不知了拜。And take back again to the picture。You know， you know。

 I defined it in some way， I could define it in some other way for every X out here there exists in S。

😊，Which is feasible for the dual。So that x dot x not dot x component y is y S is equal to the same number。

This is is a definition of a central part， here's a different definition of a central path。😊。

Is this old definition of the century part？嗯。Solve the problem。Minimize。C transpo is x。对ます。He times。

一。specificGood， so this is central part with respect to the log band。

And for the rest of the discussion， I'm going to just stick to the log barrier because thats the sort of cleans barrier。

😊，It's a。mSo， you know， you could say， look， the central path I define to be pairs， you know。

 one in the primal space， one in the dual space。I could just look at the xs in the primal space that gives me that that curvy line that we draw earlier。

 I want to say that curvy line is given by this parameterization。😊。

I have to show that these two things are equal， I haven't shown that。😊，对。めどました。

Thank you for listening having some。And very function individual right。

I could think of having a value function for the dual。

 don't know how that will play out within this how will use a so the first one would probably have to you know they might not be as clean a description out here。

😊，So I was trying to play with the barrier where I removed the log。

Which is you know it has some other name I forget what barrier it's called and then things became annoying because it became like excess squared and it's not so clean so somehow lock barrier has this sort of clean view out here。

😊，I'm sure things can be done， it's just not my specialty。😊，So first again。

 so I have to show that these two things are the same。😊，We will come in a moment。对。Actually。

 let's show that these two points。Let's try to figure this out。

I want to minimize this function subject to。嗯。Lineary equality。

I'll do it on the side and then we'll quietly era it。😊，So we earlier said that， look， oh。

 if we had a。If we had you know， F of X， if I wanted to。

Fure out the optimality conditions for minimize x F of x unconstrained。

 then you know optimal optimality。Says with the gradient of F atax we take to。

But what I want to do is I want to say minimize f of x subject to a x equals B。

This is what I need to do， so I need to give you a constrained optimization from now okay。

And I need to understand the optimality conditions for this。

Now optimality conditions for these things if you haven't seen this before， I'll just do it。😊，Quly。

 I won't spend too much time on that。So what do I do， I write down the。LaGian for this。

And if you you haven't seen this before， you know it's the pain is limitedll you can take this on faith so you write on the Lagrangian。

 the Lagrangian is going to be。😊，A function of x and some。Why。And this is equal to f of x。

Plus y times。A X minus B。And if you think back to our multiplicative weights。

 what we were doing was we were all we were saying， oh， there are all these equality constraints。

 I want to maintain them。😊，I'm want to take a soft version of these things I'm want to multiply y1 times the first constraint。

 the violation， the first constraint， y2 times the violation second constraint and so on and so forth and just sum them up。

And these wise are telling me which how much weight to put on each of these constraints。

 what is important constraints which are being violated？These are the prices。Going back to。

 even a previous length。I always think of them as taxes。

You violate the constraint I' want going to rail that why。

So these are just telling me which variables are important。

 but in any case this is the laggrangian and you can see。😊。

That the lagangian is always the lower bound on the optum is less than the。呃。

Optimum of the original problem for every y。And the way， you know。

 so so the optimality conditions are called the Kkt， these are the。假如。欢。And tackle conditions。

And you can pick up your favorite book on convictx analysis。What do I need to do？

I need to say that the gradient of with respect to x of Y x y。He's going to put Sarah。

And I'll also make sure that the dragon can respect to lie or addedwana。你为讲不笑。

And then there's some complementary slackness conditions。

Let's just look at what these conditions are saying。

This guy is this guy is easy if I take the gradient with respect to why I just get back。😊。

A minus b equals0。Our original conditions， everything so。If I look at these conditions。

This says the gradient of absolute respect to X。Plus。A transpose y。So actually。

It's more convenient for me to use negative signs out here in this case。

 it doesn't matter where I could have。I need equality， but it becomes cleaner back。嗯。

Graient of F x plus a transpose y。要不。嗯啊。Mus。I just did the flip， thank you。哎。

What was F effects for us？C trans so f of x。Was c transpose x。Plus。Some。电影。Ts log at1 over x。

So the gradient。Is C。Love of X。Is。Log of 1 over X is negative log of Xi。

And log of Xi is derivative is1 over Xi。😊，诶。So this becomes minus three times。A vector。

 what's the vector， the vector is the one vector divided by the x vector。It's1 over x1。

1 over x 21 over xn。Minus。Aronpose y with be equal to0。Just。Did this one， this is a gradient。そですか。

This is very transparent。Nobody sees what what we can do。What is C minus a transpose y？

This is the same。Wch is disre this thing。This is the same as。Yes。Is equal to。

The T times the all one section。Divided by the x vector。bigger个。I just took this guy。

Rewrote it there， c minus a transpose y。I equal to s。对。

So this is the same as saying x vector S vector。Is able to do that on understand。来啦。

Why are we doing this？H was is a slightly related previous question， but you know， I see。

 you notice that the second definition only depends on private variables。

 So there for reasons like hidden definition， which only depends on。Things in the rules space。

So there probably is。We probably can work this whole thing。Based entirely on us。

I have to work this out， but my guess is that you know start solving the sort of dual thing。

 wed have to figure out the right barrier， maybe even the same barrier works， but。😊，Yes。

I think it should be very symmetric， I'd be surprised if one too。😊，So far so good。Just you know。

 this sort of elementary tricks， elementary， you know。

 it wasn't elementary to me the first time I saw this。对。O。So far so good， okay。

 so one minor thing it'll be useful for us， let's generalize this ever so slightly。😊。

Let's look at instead of t times log X， let me throw in。Okay。

A different parameter for every quartert， so mu is now a vector。😊，Okay。

Everything goes through the same way this just becomes the new vector。This is just the meal vector。

 this is just the meal vector。I'm giving different weights to different components of the。

Of that barrier。Okay。走这里。The boy said。This is now no longer the definition of the central park。

This is just I'm looking， I'm giving you a correspondence， so mu xs is equal to some vector mu。

Is the same as。I showed you this kind of correspondence that if you solve this thing。

You would get back this object。And in fact， if you look at this object。

 this exactly satisfies the KKT conditions for optimality of this guy。😊，So in the picture。

And I thank Yinta Lee for this kind of picture。Me。Want to work in this space。

 so there are these two spaces。The space of x comma S， which belong to this。And there is a space。

Of these new vectors。Basically by fixing mu。I got a un point access out here。And I took that point。

 oh， why was it unique because this is strongly convex you know strictly convex？😊。

There' is a unique minimizer to this and that gives me this。😊，And this point， you know。

 if it satisfies that， it satisfies optimality conditions out here， it gives me。😊。

So the sort of the perspective that he has， which now I like it quite a bit。Is that。

This the or this belongs to our。And strictly positive。

Points out here have a correspondence with pairs out here。诶。So when you're moving。

On the central path， somehow you are you are looking at these vectors。

 So this keeping this new vector in mind is useful。😊。

And there'll be various properties that will come up。Of this new vector。

 which will relate back to these pairs。So I'm just saying that there's this correspondence in between。

And I'll move in new space。In fact， we already said I want so the ideal situation is I want to set new to be t times the all one sector。

😊，So this will give me solutions at state S。Here's what I want to do。

 I just want to move to a new new prime， which is t minus epsilon times to all one sector。

I want to come up with X prime or screw。I mean， moving here is dis trivial。

 right I scale everything down， I subtracted epsilon from every coordinate， there's nothing out here。

😊，Getting， these points are the really interesting things。对。And this is our goal。

 our goal is if you gave me a solution corresponding to mu， which was R T vector。😊。

It so the point on the central path。The actual central path， that picture that we wrote。😊。

I want to reduce the speed to t minus epsilon and get another solution， how do I agree this？那不。

I think。I assumeIll start with you in fact， I'm going to start with。D。So I'm going to start with T。

 which is huge。😊，Because then the barrier dominates and I'm at the you know whatever the analytics extent to I've got nothing to do with Cs。

And now I'll take T from some huge quantity。Slowly down， think of infinity。And basically。

 I'll reduce it slowly down towards there。That seemed reasonable。

 at least within the realm of possibility。😊，All I'm doing is I'm taking T and I'm slowly reducing it down。

😊，嗯。Yes。Good， so actually what I will want to do。Is I do want to be multiplicative in each step because I want to make you know geometric progress。

Well I's say p times1 minus epsilon times the all ones factor。Okay。😊。

So I want to start with a solution like this and come up with another solution like this。😊。

And then I'll be I'll be， I'm so happy。And then I'll reduce this by epsilon more and I want epsilon to be large。

😊，So here is what we'll show。Yeah I haven't completed this sentence yet， so ideally I will show。😊，です。

W the Ro will try to discuss it later。😊，So here' is what I want to do。

 I want to say take some value of T and reduce it by this much every time。😊，哎。

So this would give me you know， if I started off with t being some large quantity r which depends on the radius of the big ball and I want to end up with t being some little r which is the radius of the tiny ball when the number of steps I'll need is。

😊，Yesす。This is what I'm aiming for。哎。Multipicative improvement in square root 1 steps I have。

 I have to haveal only so many times。😊，I'll be in great shape。The problem is。That I won't be able to。

 you know， I'll get a， you know， I'll start off with this thing。

 but I don't know how to quickly get to this point。😊。

So here is the cheating I'll do I'll start with something which is close to the all one vector all t vector and I'll end up with something which is close to the all t minus。

😊，De overru dynamics。So the picture really is。This is the path。

 I start with something which is close， I'll end up with something which is close， close， close。

 close， close， close， close。😊，嗯。So before I you know， get， so so basically， you know。

 this is what we're going to do in the rest of that。😊。

Lecture I'm going to start with something which is close。

 I'm going to define what this close means and I'll show you how to get to something which is close。

😊，And those of you who are keeping score at home。Each of these steps will involve one linear system solve。

So you'll write down a linear system and you'll solve it。And theres several ways of seeing this。

 one is the way we will do it， we'll just write down what we want to do and then we'll approximate it。

😊，So if we could， if we were ideal， we would end up there， but we we overshoot we'll end up there。

Another way you could view this is you could say this is one step of Newton's method so those of you who remember Newton's method。

😊，Years past。ThisThis is also related to Newton's method。

And that might give you some idea Newton's method is notoriously bad that it might diverge。

 but if you start close enough to the rot it will converge。😊。

The same same kind of principle out here， you want to be close to the central part。

 then you'll get close to the central。Okay， anyways。

 let's take a two minute break and then we'll come。Then I'll show you how to do this。ok。😊，So。

Here's the important step？Given a solution corresponding to some mu， let's work with the general mu。

I want to imagine this mu is almost uniform， but let's work with the general mume given a solution x comm S。

😊，Which corresponds to mu， I want to get a new solution。Which corresponds to meal plan。A new prime。

As the notation indicates is new plus deellta。😊，All these。

 all quantity that I written down on this board are vectors。

And all multiplication will be component wise， all division will be component wise。O。

So let's just write down what what my goal is my goal is that these two guys should line these faces so what does that mean this means。

That a times。X plus delta x is equal to B。A transpose times y plus delta y that there exist in y and delta y says that a transpose。

The y plus delta y plus s plus delta S is equal to c。Okay。😊，Remember。

 I want these to correspond to mu prime， so I want to make sure that x plus delta x。

Y plus delta y oh， sorry， S plus N。Is equal to this is a usual， you know。

 the sort of component of multiplication is equal to mu plus delta mu。😊。

And I want these to be in the open set， so I want x plus delta x and s plus delta s to belong to the reals strictly fored。

Same space。喂。I've just written down primal feasibility， dual feasibility。

This these vectors correspond to mu prime。And they line the open。So first， okay。Then let's go on。

But a times x was equal to b。We started off with a solution。

 so this just says a times s is equal to0 so a times delta x is equal to。Actually， yeah。

So the only thing I want to say is that look， normally we could have written down we could have said。

 oh， this is a linear system， but there are several problems。😊，Firstly。The open set constraint。

 weird。Secondly， I'm multiplying two things together， weird。Thirdly， I don't know what why is weird。

But it's not important， none of these are important。

So a times x is equal to B so I can see things out。A times y plus S was equal to same。

So I can cancel those out so I can cancel out this， this and this。Exent B one An。

So I'm saying a transpose delta y plus delta S with very quick to say。

I don't know how to handle this constraints， so I'm just going to ignore this。

And this guy is x times s is equal to mu， so I can cancel those one。

The x and x times S is being cancelsed out， so basically I'm saying x times delta x plus s times delta x。

Plus delta S， delta x is equal to 0 or is equal to deelta mu。

But I don't know how to handle weird things like this， these X and S were given to them。

That were my starting point。This I don't know， so I just throw it。Yeah。

It's like a first order approximation。Okay， so I'm solving this this。This linear system。In variables。

 delta S， delta y and delta x， delta y and Dlta S。That's a linear system。喂。😊，I get back a solution。

Get back two problems with this。Firstly， I did an approximation out here。

So my new solution does not necessarily correspond exactly to this because I throw away the cross term。

And you know， it really depends on how big a step I can take。So if， of course。Mux is0。

 so I need to choose deelta mu so that this solution that I get back。😊，And shares this product。

So question。好边。第lタ尿。Such that x plus delta x。And S plus delta S lie in。Question one。And question two。

Is you know x plus delta x times y plus you know s plus delta s is is no longer equal to mu plus delta mu so because it's actually mu plus delta mu。

Minus deelta x delta mass。Because of this this cross stone then I threw away。

You know how much is this？How bad is this？I'm throwing this away exactly for computational reasons because if I could solve you know。

 these quadratic problems， I don't know how to solve。😊，This problem， I just have to invert a matrix。

This is just a minute system。One matrix inversion。don't know how to solve the problem or interesting。

Good point。So at the very least， I wanted to say I it takes longer。

 but I actually go off and I don't know how to solve the called writing problem。😊。

It might be possible， but maybe I requires semidefinite programming， in which case it's bad news。

I'm sorry， that would also be an approximation because。好的。

I see so it would be a you know still there would be some tiny amount。

 but maybe I could make this tiny amount yeah so you know one way or the other I have to worry about all these other issues。

😊，好的。😊，So for these things for both of these， I'm going to tell you lemmas。 Okay， so by the way。

 I'm following。😊，The lecture notess due to Yin Tli and Santosh Wmala it iss called a tutorial and the robust interior point methods。

 you can throw away the robust lecture throws away all but the first six pages of this paper。😊。

And you can just follow that first four pages are enough actually。

 but I'll also put my notes my handwritten notes and hopefully Ill type it up。😊，啊。So。

So let me tell you what sample。Okay， how are we doing on， we're doing okay time。But more or less。

 the moral of the story should be clear。😊，That look essentially。If I'm taking tiny steps。

 then the amount of error I'm getting is not too much， hopefully I can control that。😊，And you know。

 it's really going to come down to how well can I control these errors？

So let me try to answer the questions one by one， so firstly how big a delta mu can I take so that both of these lie in the open set。

And this is， I'll call thelemma  one。诶。😊，And this is suppose a is for you。浏览。And。

XS lie in the open sets。嗯。And correspond to。没。诶。😊，Then。Doing this process。If。Delta mu。

 which is a vector divided by mu component wise。The two norm of this。嗯。Notation。

 let's forget this I'll just write down the expression。😊，Anyways， quoting an expression which。😊，嗯。

Delta mu。The highest component of that squared divided by mean y。

 whatever this expression is is at most。咩。Over你は。You know， this is some condition。

You got to do some you got to go through some some amount of linear algebra。

 if this condition is satisfied， then I know that x plus delta s and s plus delta s are good。😊，Deブラト。

Normally， I won't write down this expression， but you know this will help us sort of make sense of。

Tns a little bit， let's just look at this。Yeah。If this delta was0。

 then my problem is easy I mean then I have not changed at all right？😊，So if these deltas are small。

Compared to compared to the original deltas， then I should be fine。😊。

So let's just look at this quantity。So what is this quantity？So suppose。Let me use a different color。

Suppose I'm imagining that my Delta mu。Is some。Epsilon times， you。

I want to reduce new bio constantst factor， Epsilon。But some factor of that。

So let's just make sense of this expression。This is a song。Over。Epsilon。牛孩。Square。The外的 does newは。

三六个来。This is equal to epsilon squared。The L1 norm of mu。 remember， mu is not negative。

I want this to be less than equal to。咩。咩外。How large an epsilon can I make remember epsilon is the amount of step I'm getting。

😊，So this means that epsilon should be at most。咩。New I divided by the L1 normal。Yeah。

How large can this be？How small can this be zero that's okay， how large can this be？

So we are dividing by the L norm of mu， let's imagine the L norm of mu is one。😊，Thank you。Okay。😊。

And it's one over root end when the mu is almost uniform。😊。

This is why we want to stay close to the all once vector to the uniform vector。

That's when we can make steps of size 1 over root。It's not， you know。

 I'm giving an excuse and not an explanation in some sense， there are other， you know。

 people give reasons for why one over Ro1 is the right answer for this thing。😊。

And Messov and Neirrovski have a theory of self concordance and they explain this all。😊。

I don't understand it well enough to explain it。But at least right now I can try to see where in the proof am I using the various pieces。

 why were all the weights equal well at least as long as I'm using these kind of theorems。😊。

I can't hope for a better than one over root1 step size。

So this says that if my mu was approximately three times the all one vector。

Then the best I can hope for is that new prime is approximately t times 1 minus 1 over root 10 times the oil one vector。

And this kind of sort of technology is only going to give me one over Ro1。

 so that's the best I'm hoping for and that's what I would get。Const say。

And that's why I want everything to be about this。How are you guys， John？More or less， okay。

This stuff is fascinating， I mean， I want to understand more。Good蛋。O。How do you prove this？

The way they prove this the way these guys prove this is they actually figure out what is the right solution or they say oh you know this solution this is a solution basically you can write down an explicit form for the solution and if you write the explicit form for the solution and then theres some violence and bloodshed that I you know I'm not comfortable with I think I can do it on the board when you know what's the point you can read it as well as posture。

😊，U。But you know， there is intuition and I hopefully next time I teach it， next time you teach it。

 you'll have more intuition than I can learn from you guys。😊，But I digress， I have 10 minutes。

So I've kind of said how big deelta mu can can we have so that this happens and we are saying that delta mu as long as mu is more or less balanced deelta mu can be something like mu over the root。

😊，I can take steps of size root， one over route。Good。And then the second question comes。

 you know how much garbage do we get？😊，And maybe for this。

 I'm going to actually quote my second theorem。And that will pretty much wrap it up。

And the second theem says。I red is my second two or the second kid on the right man。ok呃。

This is the part that I am in。好屎啦。Also the first item was this you know itlemma， whatever lemma one。

 and now I'll just take lemma two and we'll just wrap up。😊，It's right。They should have arranged for。

As to go to drinks。Maybe next week。Okay， because I write don let my tongue。When La two says， okay。

Suppose。X， S。Belongs to。And。X S， remember， component wise。Minus t times the all one sector。

We do normal of this。A that most。The 4。咩。射定。Thisすみみ。抱歉。So， so then， then。嗯。Then bake one st。

To get from， you know， to get from excess。2 x prime S prime。啊。Red。The the new you know。

 sort of the T prime you set was like t times 1 minus1 over。

Something like 16 or 10 or something like this not important。

X prime S prime minus this p prime times the one vector。Ava most。B prime six。

Well4 would be enough six you， it's gravy。So all this is saying， you know， ignore the algebra。

 you started off with a solution which was close to the all one vector。😊，In the tu norm。

Then one step ensures that you are close to the t vector in the two。Now you can end up。

You started close to the central path。If you were on the central part。

 then x times s would exactly be the T vector。😊，You started off close， you ended up close。Yeah。So。

That's not like for all experts。It's like only for X S time that result from。

So I started off with excess and I took one step， what I meant by one step is。I did this thing。

And my old mu was this sucker。My new mu is this sucker。So basically each time I'm taking， you know。

 I'm reducing my T by some factor like this。And I'm trying to solve that one step， you know。

 this is a little a newton step。😊，Even though I haven't given you the connection to the new transplant。

But。This is just saying all that linear system， it was an approximation。

 but it is not a terrible approximation if you started off close you ended up。😊，Enless story。

just curious to like as time goes on it's like you're learning more and more about the social path。

 butre next year you're only using like the previous one or can you use all the I don't know。

 I'd have to like to Steve right to。😊，嗯。So if you're interested in books you know maybe even the so Piazza notes I'll write about books there's books by Steve Wright。

 he's the expert he's at Wisconsin he's got books on this there's books by Jim Ranegar at Cornell。

 he's got a more Newton method view of this thing。😊，There are books。

 with like a million books I mean， Inter point methods are a huge， huge area。对。Say， I guess more of。

I dilemmas are both saying something about。Like in any ideal world where we didn't have this delta x kind of deelta x term and we would just follow it path exactly absolutely so what what is is there some sort of k level overview view and what the twos are saying Okay so this lemma is saying that the Dlta S Dlta X。

😊，Is you know， if you started off with being close to the central path。

 then the delta S delta x doesn't take you further away from the central path。😊。

So you are hugging the central path。Lema one is thing。That you can actually， I mean。

 one way of making progress is to make no progress。

So what lemma 1 is saying that at each point in time。

 if you started off with a nearly balanced vector。😊。

Then you can reduce the T by like a one over rootine factor。

1 minus1 over root or whatever you can make it1 minus1 over route 10 and that。Just this LP， you know。

 not LP， this linear system。Would still do the job for you。So。Yeah。

So maybe let me say one more thing in England， so I started off with an x comm my S pair which corresponded to some mu。

😊，It wasn't really on the you know equal to mu， it was close to meo， but let's not worry about。

Now I want to make progress。So what do I do I reduce mu by deelta mu。And I saw the system。

It gives me some delta as delta x。😊，What Lamma 1 says is as long as this your delta mu was not too large compared to meo。

😊，You don't overshoot your boundaries， you stay within the feasible center。But that's fine。

And the second lemma says that you are not too far from the central path that。😊，So it just says。

 okay， so you were there， you took a step。You might have screwed up in two ways。

 there were two relaxations， remember。😊，Qudratic term gone and we dropped the open set。Lema1 says。

 oh， it's okay， you're still within the open second。Lema2 says， oh。

 you are close to the central path。Each one of these might be either by itself， you know？But really。

 you do want to remain close to the central part because you want to end up close to the central part。

And you want to stay in the feasible region because the feasibility。😊，let's how to work together。

Because so the first level only works if comm is roughly balanced， right？Well， it works in all cases。

 but it makes this huge progress only if muse are roughly balanced。😊。

If you actually do analysis like track how you say that so in general， you know， this statement。

 you know， setting this quantity would screw me up badly。

So I should make sure that this quantity you know， everything， the fact that I am still feasible。

 I need to make sure that I'm still。So to that extent， I think they are working together。Yes。

But that's。Kind of what I have to say。I am out of time， but as is traditional。

 I shall go a couple minutes over。Actually， are there more questions？😊。

And maybe I'll say a couple more things。There is one more view of this thing， which is。

 you know I mentioned， oh that linear system came out of this approximation。😊。

You can also view that linear system as coming out of solving， you know。

 trying to do Newton's method on our。Removed every。

You can say this is a convex function subject to a mean equality constraint， that's okay。

You can run Newton's method。So and if you've forgotten Newton's method。

 at least I have a picture for you to remind you what Newton's method was。😊，Newton's method said， oh。

 I want to find a zero of this function f。😊，So if I'm at point x。

I want to go towards the0 so I should look at the slope。😊，And I should go to this point。

And so this says that the new point x prime。If equal to x minus。This distance。But that distance is。

The。嗯。The height F of x。Over the slope at X。This divided by the slope is this distance。嗯。

So this is to find a0 of f。😊，I want to find a minimized， okay， zero of the function G。

This is a function G。I want to find the minimizer of G。

Well what's the minimizer of G oh sorry so now I have a function f I want to find the minimizer of f。

 but that's the same as finding as0 of f prime of the derivative。😊。

So that just said that the new solution， this is this is not a prime， this is new， whatever。

Is equal to x minus。The first derivative at x over the second derivative at x。😊。

Thats a Newton's method。And it， you know， it's an amazing method or the Newton Rafen method。

 if you wish。In higher dimensions， this just says x new is equal to x bold。

Minus I' will just call it x minus and now this is a derivative that' is like the gradient this is like the second derivative that' is like the Hassian so this is the Hassian。

😊，Of f at x inverse times the gradient of f and。This is Newton's method for high dimensional things。

If I were to hide this thing， it would look like gradient decent。So this is New Man。O。

And now I can apply this method to my function， to that function okay。I mean。

 there's some constraints and I'd need to worry about this。

 but I could apply new to Spanish for this。😊，And once I start doing the algebra， actually you know。

 surprisingly familiar things pop out， you'll start making updates like that。😊，这 say啊哈。Actually。

 I'm doing Newton's method。So， yeah。And then you can view things from that perspective and if you're interested。

 look at Jim Renegar's book， he does everything from that perspective。😊。

But that's pretty much it let me stop here questions from Piazza questions now I'm happy to take questions and otherwise have a good weekend us。

😊，Im sorry。哦哦O， one more。😊，There is a part I you know I only know at a high level。

 so I have explain it at a high level， but okay so there is different ways of finding but here is one way of finding it。

😊，但下我。This is the analyticsnalytic center， let's say， this is called x infinitefin， right？😊。

This was the first point that I needed， this is what I want to find。Suppose。You guys know that。

Like in the simplex algorithm。We have similar problems and in the simplex we walk from vertex to vertex we start with a vertex。

 we walk to another vertex we walk to another vertex actually miniization we only should walk to another vertex and so on so forth。

How do you find the first vertex， you kind of muck around with a polytop and just create some fake ver if you when you start from there。

😊，But suppose you knew a vertex that you wanted to start off from。Okay， suppose I told you， oh。

 here's the vertex of yourpolltop you can start from here。😊，嗯。This vertex corresponds to optimizing。

Some objective function。That has a thank。Starts on the same point and up out here。

And I'll run this process backward once。So you see the thing is that these two sets of parts。

 how do they differ， the first one is c transpo x plus the barrier。😊。

The second one is C hat trans equalse x。不要是 very哦，地毯。I don't know。Sos tea is infinity。😊。

This is just inconsequential。So all of them， the analyticstic center only depends on the barrier。

 nothing。So how do you do it， you start from a corner， you know。

 you work backwards until you' kind of mixed。And then you start from there and you go forward。

It's almost cheating， it shouldn't be correct， but apparently it is correct。😊，都在场里的。Anyway。

 I think it's that。Thank you。