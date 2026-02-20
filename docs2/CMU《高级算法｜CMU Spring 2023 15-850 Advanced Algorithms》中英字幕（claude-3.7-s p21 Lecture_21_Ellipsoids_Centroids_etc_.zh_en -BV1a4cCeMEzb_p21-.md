# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p21 Lecture_21_Ellipsoids_Centroids_etc_.zh_en -BV1a4cCeMEzb_p21-

Hey， welcomecom back， everybody。And呢。Let's。Get started on the course again， by the way。

 so the midma grades are due and you'll probably receive some there you know there as always they are a noisy predictor of。

😊，The final grade， they depend on know homework  zero1 and2。

There is a you know you haven't really seen the grades for homework too yet so things are you know don't don't stress too much if you're worried about your performance come and talk to me etc cetera。

 but hopefully hopefully you' will be。😊，You you know。

 it won't be unexpected and we can we can discuss more。Good。So good， so convex optimization。

 this is the problem we are trying to solve given F。😊，Which is convex。嗯。And。建。which is是。

Also convex set so F is a convex function J is a convex set， what do I want to do。

 I want to solve the constrained optimization problem minimize x and K f。And often。

 I'll just say that the argument of this thing is x star。And what do I want？

So I would like to find this problem this this point of course。

 but one problem is even writing down this point might not be feasible。This might not be。

 for instance， this might not be a rational number。 How do， how am I going to represent it。

 etc cetera。 So here is what we'll say will want given。F。Okay， and epsilon。Regard。X。Such that FOX。

In that most F of X star。Plus Epsilon。So I'm allowing Epsilon error。

So this is the problem I want to solve。Two things youd be worried about。

 What do I mean by given F and given K， what kind of access F is a function。Okay the convicx sec。

 how am I defining these these objects， So lets let's see how it goes as we develop the algorithm。

Now， one thing that we already saw， we saw gradient descent。Gding descent was an algorithm。That。

Runs in time。Let's say order。I'll write down G over Epson。Squared。Where。No。The function gradient。

 So F of x。The gradients of F of x were at most G for all points X in the convex set。And let's say。

 with the diameter。も好きに。Why I asked be。We saw an algorithm that。

If you started off from any point in k you want to go to k star to x star。As long as x minus。Xter。

 so if x n was the original point， x n minus x rules at most be。Then， then we ran in approximately。嗯。

Tang the sort of。I mean they important the particular expression is not important。

 what' is important is that this was the general in general the runtime like this。😊，And of course。

 this distance is at most。The diameter which is that。So basically under these two conditions。

I was able to find a。MX。Which was。Which satisfied this property。2 things。I assumed。A to。Yes。We are。

What I call a gradient authority。So the gradient tona is a box。Which are plugging a point x。

 and it fits out。 You know， this is the gradient。奥利给。For S， I give it x， and it。The greataving of。

This is my access to。The function。把这个。Yeah， so for right now， let me assume that the gradients exist。

Heth is different。Another thing that I did was， I assumed。Like my access to。き。Was via。我系讲。刚。

Projection audit。So this was a projection Oracle 4 k。I gave you a point x。And then， it either said。

You know， it returned to me the point。X prime belongs to K。Minimizing。X minus x prime。Do not。

So the way I really ran gradient decent was my body K was something I had Xt。

I took a step based on the greatal。I projected back， I call that Xt plus one， and I kept。

This was my algorithm， And so。These two were my ways of accessing E。Now。

 for your applications you might say oh I don't have a gradient oracle for f。

 how do I implement this that is a very valid question wed have to。😊，Or a projection oracle per k。

And I think that pointed out that， look， you know， the projection Oracle might be an expensive object。

 How do I implement it。And is very valid questions。

Some of these questions we are going to deal with in this in the next few lectures。

 some of these questions we are just going to point on will depend on the application。😊，O。

So what is what today's lecture going to be， So today we are going to prove。啊。呃 tell them。

Wch says we will give an algorithm， let's say， I'll say centralroid。

There's an algorithm which will solve。This convex optimization problem and will run in time。Runs in。

但。Or the。something something 啊。Okay。I might have really just。Right and down。So this。阿你咁。

Will run in time， order， and。Ns。어 왜。暂停啊。但是。I'll tell you what B is。我不。

So it's going to solve the same problem。And， in fact， it will。For the moment。

 let's imagine the same oracles。 We will see what oracles will actually mean。

 So F is given via gradient Orle K is given via let's say a projection Oracle。😊。

Epsilon is just a number， epsilon in greater than zero。And Im going to return a point like this。

 but now the runtime is not polynomial in one over epsilon， but polynomial in log of 1 over epsilon。

And this is going to be， you know， this is a polytime algorithm。For convicx programming。

 because now the length of the representation of ppsilon is really love one over epsilon。

So we we are sort of doing things much faster。对。So， maybe I'll。II'll just flesh this out。谁这问。머리 있지？

What K I'm going to make。An assumption that K belongs to。啊 boys。Cented at the origin。

Of radioius sorry。So I'm also given so hencem given。This particular epi parameter are。

So I am given some convex set K and I am given an n which is essentially the diameter。😊。

OhThis this kind。We just call it that。2是的。What's that。😊，哦呃，啊O。Maybe。呃，O。I I come to that。The。

I don't know why。😔，I might have some。呃。Some bugs in my。对个。Sorry， guys， give me one sec。Okay。

 maybe in this case， I don't need。で。对。That's what I did。Give me one sick。OhYes。这。So apparently。

 according to my notes， there's a proof I had in my mind is slightly different。Given k。

Let me not worry about this for a moment。嗯。I want to try this thing。嗯。Im going to another。That was对。

Okay。K is K， the body， which is in some ball。机心。换です。AndLet's not。啊。Very important。

And then I'm given a function， F。Which maps K。Into negative B to positive。

B is a bound on this function。What am I giving。'm given。诶。The gradient authorities。好了。

I'm also given maybe I'll need this thing。I'm given a value oracle。好的。

A value Oracle is a much simpler object。😊，This is a value Oracle。 It's plug in F X。

 It gives me back F。Okay， so I need maybe a gradientding Oracle and a value Oracle。

What kind of axis I need to K we will see moment。嗯。嗯。What do I want to do。I want。就啊。嗯。그미알。

Will run in in this kind of time。One time。三点。我看看。啊。So。Goodd。

So one thing that's going to happen is that。Suddenly， my dimensions。Let's make it out。

So for the next few lectures， the dimensions are always going to be n。😊，Okay。This will be。

 by the way， you know， not completely unreasonable because well be soon looking at LPs。

And whether LP will be off the form， minimize C transpose X， A X is at most B， let's say， and X。

They all belong to art。These will be M by N matrices。Okay。So n from now on。

 unless otherwise specified is the dementia。等呢。So the algo runs in time， something like this。哦，老子。

I haven't specified the algorithm yet。 I'll do it in a moment Also I noticed this one。可。

Did something because I like so。Exactly， so so what is happening out here is that if the function if the function values are this high。

😊，等啦。This should give me some sense of control over the gradients， right？Well， actually。

 it doesn't really give me much control at the very edge。

Let's see whether we run into this problem or not。你。Yeah。So let me give you the。

SoThe algorithm is going to be the following， and maybe I'll draw the picture out here。M， L， L。

So for simplicity， let me just say K is。😊，This ball。一。I want to figure out。The value at texture。

Let's say I'm going to start off act。So my points will be。

 I'll call them C C n C1 and so on so forth。just for concreteness。Here's what I do。

I'll start off at the origin of the。I'm going to。Look at the gradient at this point of the function。

If the gradient is point thing in this direction。Where should my function minimizer be loosely speaking？

Yeah。So here's what I'm going to do。I'm going to take this point。And I'm going to。Throw away。

This entire。I want to focus on。This portion。I'm going to try to。Minimize my function。In this region。

是。嗯。So what Im going to do is I going to choose another point now， which I'll call C1。

I'm going to look at the gradient at this point。 maybe the gradient goes in this direction。

I'm going to throw away。This portion okay。And I'm going to look at the remaining portion Okay。

 and I'm going to try to minimize my function value in this region。

And I keep on going for some number of steps for pretty much some number of steps right。啊。所以也是。快佢。So。

Why is gradientd descent so much worse than doing this？嗯。very。嗯。我 to。So I don't have an example。

Coite don't mind。 Okay， let me tackle that question。Next。O。So one。

 one reason why gradient descent is not that great is because what we do is that we we are not looking at the space。

Particularly， we are just making steps of a certain fixed size， let's say。

And were slowly moving towards the minimize。I might want to take much larger steps。

If I can be confident that I'm not going outside okay， that I'm not overshooting the。嗯。

So it's a very local process。Well， this is a much more global process。In fact。

 I haven't told you how I'm going to use the global geometry。You know。

 what is this point C n and what is this point C1 O， So let me give you the algorithm。

 This algorithm is called the centroid algorithm。It's due to two guys from the six days。

 I think this。11。Newman。啊。Russia and the US， you know the same old story。 you heard the story in 4。

 let's see， no， okay， So let K not be the original body K。And then I say， while。For B equals 1。

Et cetera， we are going to K1。Okays okay 0，1，2， et cetera。 C sub T。Is the centroid。

Also known as the center of Mars， the center of gravity， the Barrie center。

 various other names for this of the body ca。And now you say。That let us define。ケ ofデ plusワ。

Is case of T interect。All the points x。Such that。The gradient。Of F X CD。X minus。CD。Yes。Me。

I'm throwing away all the points。Which have a positive correlation with the gradient。

 The gradient is telling me which way the function is going up。Andm throwing away with。I saying， oh。

 I want to go back to。Yeah。嗯。Run this for some tea time steps we fix what tea is。And then return。

Ex hat。Which is the odd men。T belonging to zero。Of the capital B。Yes yes。Look at all the points。

Which was the centers in the past steps。Choose the best of you。This is my announcement。

It is called the central。그 the 아이 didn't make sense。Every point in time。

I'm looking at this Androidroid of the remaining mass。So， for instance。系你。My， my space。

Was was just interval on the line。 I would pick。 and let's say， yeah， so I would pick the center。

And I would say， oh， my function looks like this。The the gradient out here is positive。

So I'm going to throw away this whole portion， I'm going to focus on this part。

 I'm going to look at the center out here maybe can center this。好听。

I'm going to throw away this portion。And then I'm going to choose this point。

 Maybe I'm going to throw this away。 I'm going to continue。 So it's really doing binary research。

This is just by any research I mentioned。Yeah。So far go。Okay we just。Sory。Good。So this is， yeah。

 I'm assuming a lot， right？😊，So， access to。Andの assume。Sandroid on。

So this is what I'm assuming from my from this trend。这。Thanksbody。S为。Okay。

 so it depends on your bandwidthvic body。Now the real problem is that I am not just asking for a centroid Oracle for my original convex body K。

 I am asking it for all these convex bodies KT， which consists of my original body K followed by a whole bunch of charts。

😊，Just in case。嗯哼。😊，2是。The first question I guess。Mhmmh。😊，Yes， that is a hard problem。

 So so so Noah's question is， you know， maybe for polytopes。

It it's an easy problem unfortunately it turns out to be a hard problem。

 it's actually problem number G on the next homework set， which is on the web page。

So this is actually computing， okay， bad news。😊，嗯。Sentroid。Of。玻lly dogs。Yeah。Is sharp be hard。

Basically， if you can compute the centroid of a polytop exactly。

 then you can count the number of satisfying assignments to a three set formula。

Unlikely to happen at least at least N P。 And it's even you know， more complicated than that。

Good meals。Is that approximate。Sentroid。I。Can be done。

You can approximately compute the centroid and even further good news。嗯，对我才问。Is that the algorithm。

Works。And I'm saying works。 It requires some changes， but this is a paper with。approximate。Sentance。

You will have to you know change this algorithm a little bit。

 but you can make it work out and this is a paper of。😊，バ cinemaます。嗯，晚饭了。OrFrom 2006。

main idea is I am going to give it to you you know in this exact case。

Making this workout requires a little more effort。嗯。就知道。Any。Good。

 so you know how do you represent the convex body now。

 So it's going to come down to again representation， lets say for convex politics。But in general。

 convex bodies assuming a certain you know under certain assumptions about how you are representing the body。

😊，You can actually compute the approximate entry。对。

And just just to somehow give you a sense of what is happening。

 how would you compute the centroid of this， how would you compute the centroid of convex body。

Here' is one thing you could try， you could pick， you could do sampling。

You could pick random point from this convex body。And take their average。

This is an unbiased estimator。You have to worry about the variance of this thing， mean is correct。

 You just have to worry about the variance。Fact。You can actually sample so you can't sample exactly uniform points from a convicx body Again sharp be heard。

 It's the same proof。😊，嗯。But you can approximately sample uniform uniform point from convicx bodies。

 this is a theorem due to Aen freeze and others Aen sits in the math department。

 freeze canon and dire。😊，Theyave this very famous algorithm。

 They won the Paululson Prize for this time。Of approximately sampling from convicx both。So。

 use that use that approach and then carefully control the variance and then see that everything else works out。

But that's the main idea。Other questions about this。对。So for now， I'm going to assume the central。

And don want run 것 같아요。So far of。Okay， so let's do it。I want to show you that under this assumption。

And then I'm assuming a gradient article， and I'm assuming a value。If this average of them will work。

 I have to choose T and I will choose T appropriately。😊，嗯。嗯。嗯。

And the crucial piece here is going to be a theorem， which we will call。it's called。 It's due to。不包。

There's an inload over the you， I think Bru bone Steem。It says K is gonerick。呃，没在。

I think it's technically， I'm saying it's case of compact Con act。忙到嘅。And sees the centralroid。对。

K some convex set， sees the centroid。Take any half space。Actually the hosspice。Through。嗯。The thank。

 Okay， so maybe I should say it is。Hyperplane。Through the center。

Which is a hyperplane that passes through the center。Let's say， H plus。Is the half space defined。

Yeah， it associated hotsp space。H minus is the other half space。 let's not worry about。

Then basically， I'm saying that the volume。Of K intersect X plus。Over the volume of gas。

So how much volume can lie on one side of this？还不对。The gun bomb gives very nice guarantees。

 He says that the volume lies between。1 over 3 and 1 minus1 over3。

Now centroid is beautiful because if you pass any hyperplane through the center。😊。

It's going to cut this conves body。In roughly equal pieces， at least volume wise。定的收到。啊。

What's special about E here is that， basically。It's date。So this is the right answer。

So here's loose the thing。Suppose I take a simplex like this。And dimensional simplex， so I say K。😊。

Is this， you know， X。Greatter than equal to 0， such that the L1 norm of x is that small。

So in two dimensions， this is the picture。Whats what's the centroid？

So the centroid in this case will be the 01 over n plus 1 times the all one vector。Yeah。

And now if you've got through here。Let's say this， this cut。Then this portion。On the right hand side。

Is really。Pretty much like1 minus1 over n plus1。Scaling of the original body。

And the amount of volume in there will be scale something like this。Ithich behaves like 100。

So one over these is the correct answer in this case。For a ball， for a centrally symmetric body。

 of course， that's a half。But even if it's not centrally symmetric， it this。Simpx。

that's the right answer。And you know yeah so it' is very beautiful it's not a difficult theorem but it's a very pretty and important theorem and once you have this theorem then it's also very nice because oh even if C is not the centroid but it very close to the centroid and you took a hyperplane through C prime whatever C prime is close to the centroid you put hyperplane through C prime the volume。

😊，Guarante degrades very nicely。So this is why approximate centroids also work out。

So you can you can give robust versions of G mom ster。

 but for today I'm just going to assume exact computation G mom ste。O。对。So。

 what's happening in this picture whats happening is I'm taking a convex body。

 I'm choosing a centroid， I'm making a cut， I'm choosing a centroid again。

 I'm making a cut the volume is dropping by。😊，Constant factor every time。So。

 what I just need to show is after a few steps okay so what I know is after T steps so let me just do some of the calculations out here。

😊，So I started off with some volume。It's dropping by 1 minus1 over E。

Every time it might be dropping even more rapidly。But the volume。用 volume哦机。Sub。later D。

A at most11 over1 minus1 over E of the volume to the T of the volume of。喂。

So the volume is dropping exponentially。Now， I just need to make sure that small volume means that I would have found a good point。

That it can't be the case that I keep reducing the volume。

 but this stupid function value does not decrease trace。😊，Oh， theres one more thing I need to do。

 you know， I've been throwing away all the points which had positive in our product with the gradient。

 I just need to make sure that those those points cannot be the minimized。😊。

So let's just do this kind of。改了东西。And let's just make the proof work。



![](img/3f62d7720610966f9608a71a7c09edbe_1.png)

是。So far， it so good。Thank。So here here's what's going happened。I will say this is my body key。

For some reason， it looks like a sphere， but it need not。And let's say this is X star。

So let me define。A body。Which is。Basically， it's like a scale down version of k。

But close to the external。 So let me define。K epsilon is equal to the set of all points。

Such that all points of the form。X star times 1 minus。嗯。Let me call this deelta。这子。Plus。

X times delta。For x belonging。是。So it's kind of like taking。Okay。

And scaling it down by delta and centering it at text。Maybe X should be。Whatever， it's not。My claim。

嗯。So I'm going to make two claims。Oh， by the way， so what is the volume theres going to be several claims in fact claim1。

 what is the volume of k delta divided by the volume of k。It's actually。嗯。Delta to the。

I have know 1 minus delta mass I'm putting on x star， Dlta mass Im putting on x。

really have taken just delta scaling of the body。So the radius of this body is like only a delta times the one。

对。Plain 2。F of x， for any point， x in k delta。What can I say about its value？So any point， x。In。

 in K Delta。Any point in k delta is of the form f of x star times 1 minus delta plus delta times x。

This is a generic point inside my kid。F is a convicx function。So this is like most。1 minus delta。感。

Plus delta times。喂。This is a generic point inside my kL。Its value by convexity is at most this。Yeah。

This is at most。嗯。Okay嗯。What do I。对哎好。X。Star class。 So how， how small can F of x star be。Minus B。

F of x can be as large as B。So that's just two deelta times b。Right。Good。And let's just define delta。

 so this is equal to f of x star。Plus epsilon， if Delta is equal to2 B over。那呃。Epsilon over to。贷款。O。

So， I chose some Delta。And I chose this body。Around X star。So that all points。In this little body。

Have very tiny value。All these points are points I'd be very happy with if I got a point inside this yellow region。

 I'd be thrilled。Because I would have found。A point with good value。Moreover？嗯。Good。Clame3。

You know after。Love off。1 over deelta。Which is log of 2 B over epsilon。Stamps？Must have got off。

At least。1 point。きなた。어。好问题。Every time。My volume is dropping by。How much。1 minus1 over。喂。So， after。

After T time steps。 So， so let's say that T。So after t time steps。

 my volume should be 1 minus1 over p to the t。RightMy volume should be at most。

1 minus-1 over E to the t times the volume of the original body。

But I know that if I have not cut off any point of k delta。

All of K Dlta should be sitting inside my body。ok。但湿过滤。

This is a lower bound on the volume of k delta。 If none of k delta has been shape。是。

This is an upper bound on the volume of k delta。This is the upper bound on the volume of my my set。

So， if my set contains k delta， then this inequality should be true。😊。

And I should take logs and if I take logs， maybe I'll get n out here。上层。Did this make sense。

Don't want to confuse you guys。 I mean， there's some algebra going on out here， but I don't think。

Yes啊。We건。对。So basically， you know， all I'm saying is that after the claimed number of steps。

 maybe let me just put。This in a box after so many steps。

I would have at least shaved off some portion of this ca。I have no guarantees that my， my。

 my point C will any of those points will have。Led inside this set。

 but I know for sure that some portion of this K delta would have got shaved off。唔。Now。

 I just need to argue that if some portion of state delta got shaved off because of some center C。

 then c has at least its good volume， at least a good value。So let's just finish that final claim。

So the final claim and this is claim4。Is if。三先。四。Gused。啊。G得的。嗯。呃咩。Shaved off。没。F off。

C is that most F ofx star。Okay。ok。어。This center C caused some point why。To get shaved off。Convexity。

F of y。Is at least。Fle c。Plus， the gradient like apple。See， Y minusナ。This is 유준 급쯤。

This is the convex function。And最。The linear approximation at C， the value at y。

Is only higher than the linear approximation。So first good。Why got shaved off， what did it say？

That means this portion was positive。That's why we savedd it all。So this is at least。F好 c。

But what do we know about why？Why wasnt K Delta。So it's got very good value。

So F of c I value no more than F of y。Which itself had very good value。 So F of C had very good。😊。

Moel of the story。Pick a Androidroid。Take the gradient at that point， throw away half the body。

 not half one overee， but whose count？It's光。Take the take the centroid of the remaining portion。

 take the gradient at that point， throw away half the valve。Half the morning。

Each time you are reducing the volume by half。嗯。So after so many steps。

You will have reduced the volume to such a small amount。

That you would have thrown away at least one good point。Final claim says。

But if your centroid caused a good point to be thrown away， then your centroid also had good value。

This is why we chose the best of all the value of all the centrals。Like had good。

you draw a picture of the case where like the last？So the last one okay so again， you know。

 you guys asking me to draw the difficult pictures today。

 but it could be the case that all these sort of centroids themselves oh I see okay。😊，So。

Let me think about it that， I don't have one off the top of my hand。保险是。Okay。

 so the way I've done it， actually there is no dependence on law。😊，So let's just get off this。嗯。需要。

发了一个。Yeah， so I'm assuming that K is going to be some。后。Yeah， so this is like a。Yeah。

Let me throw this back in， but there's no dependence or that。Cent or green might not yeah， exactly。

Yeah。对。You think。Its a compact convex set， I can compute it， you know it Androidroid is well defined。

By the way I did not define the centroid I should have done this earlier。

 this is putting the cart before the horse， but the centroid。



![](img/3f62d7720610966f9608a71a7c09edbe_3.png)

![](img/3f62d7720610966f9608a71a7c09edbe_4.png)

Of a body K is equal to whatever X。嗯。X and K。Over。Which is really， you know， I always。

 whenever I'm writing down this thing， I'm really writing down summation。😊，Xi。

I going from one to some capital land over cyber。 This is like the centroid of a bunch of。

Points the Android corresponds to the the mean。是。Yeah， it's。This is Vi courttz。算呢。其实。他为什么。他呢个问题。Good。

 so here is what you do。 You just run this for t equals。😊，The parameter that will come from there。

 you know， n log this。Log to be overex。And then you are guaranteed that the volume is so small that you must have shaved off at least one point and you need that。

😊，Other questions。Yeah。ok。So， if not， let's take a。

Pminent break and then well recap what we saw and well relate this to you know a whole variety of algorithms of this form。

😊，Including the ellip or algorithm， which is essentially going to be the same principle。

 just different packaging。And the electrode algorithm will avoid all this sort of bad news good news etc ceter these results are all new right because I forget exactly when Alan and others proved their volume sampling result I think it was in the 90s。

😊，The eippsoid algorithm was shown to be polynomial time back in the 70s。So in order to show。

That we couldn't use the Android based approach the Android based approach was there in the 60s。

 but you know we didn't know how to compute centroid so you know， no go。So。

 what Kaan did in the 70s was he came up with a different approach。

 well it is actually the same approach， but just a different we wont compute the centralroid we just compute something else。

ok。Good， so I come back。The the problem instead of talking about minimizing convex functions for the moment。

 let's just talk about the following problem。It is a generalized binary research I call it the question I'm asking is there is a convex body。

😊，Which lies inside some ball of raius。 So it， it's it's。嗯。It's inside this。

It's inside this big ball。And I guarantee you that this body is not too small， it contains at least。

A smaller one。I want to find a point inside this way。O。This is my guarantee。

You should kind of think of this small ball that I am looking at perhaps as that as that body K delta that we were looking for last time。

😊，We are points， which are good。Yeah。嗯。And and this big ball is just， you know。

 some region of space that I'm starting off with。So I want to find a point inside x。

 this will call the feasibility problem。Now you might say， well， you know， how am I given key？

So home given K is what I call a strong separation oracle。

A strong separation oracle just says if it's a box。So this is SSO for the body K。 I give it X。

 and the answer is either yes。And there's a smiley that goes with it， or it says no。

And then it does the following。 It says， look， here is a， here is a。Ha space。

And your point x is sitting this direction。And the body tail lies in this。

It's a separating hyperplana。And I think it's the Han Bak theorem or something like that。

 which says that if your point is not inside the convex body。嗯。There must be a separ IP。

So this is just saying this is how I'm going to tell you。You could ask for a weaker thing。

 a membership article which just either says yes or says no。That's too weak， you know。

 without further assumptions， that's really just too weak。 its very difficult for us to find。

the convicx et。you can imagine the convex set case， some tiny little itty bitty thing。😊。

You're sitting somewhere O。Its volume is like。Delta to the n times the volume of the whole thing。

 This is like a deelta little bar。If I all I told you is， are you here No， here， here， no。

 you come on。 youll have to do exhaustive stuff。the very least， I have to do binary research， right。

 I have to tell you which direction， you know， or too high， too low。😊，Strong separation。

Every time you are doing binary research， you are using a strong separation oracle for the number you look at。

这么一个。Yes。各政据。Good， so one thing that I could say is that oh， you know。

 really I am asking for this to be a perfect separator。😊，What if you know， things get fuzzy。Id say。

 oh， this is， you know， at least this minus epsilon or something like this。

So there's some phs going on out here。So is sort of in the on the boundary where this point is very close to this convex set。

 things get mess up。😊，This is weak separation Oracle， and。

You have to worry about this because the you know， yeah。

 so all these errors start propagating right now I was assuming I can do perfect arithmetic。😊。

But my you we start worrying about big precision and stuff like that。 So next lecture。那。S。嗯。这是可以。

这个是包括。Below， absolutely yes，'， it's the same as。So， if I just said。

 let us define all the good points to be the points in that previous k whose value was at most f of x plus epsilon。

😊，And its know sort it's convex because the function was convex。 So you know。

 level sets very nice in convex or sub levelve sets， I should say。😊，So that's what I'm in perfect。

So you I guess。奥利水。采方意。No， but because if I knew it。

 then I would just go to the center of the smaller ball and say， you gave me the answer。😊。

It's a trick question， it exists。So algorithm 1， you have already seen it before central。

You you start off with K n being the ball， which is big。😊，And at each point Kp plus1。

 okay so so what do I do， I start off with this ball I use it centralroid。

 you give me a separating hyperplan。😊，Without loss of generality。

 I can assume that the separating hypercoant passes through the centroid。😊，Because， you know。

 I know that K lies is somewhere out here。 I don't know where。

So if you gave me this thing or whatever， not this thing， that thing you would be an。

You give me this thing。I'd say， look， you're giving me more information than strictly necessary。

I want to translate this。Boss with the eyes。Or whatever， you know， I didn't need that。

 So basically I know that the volume of KP divided by the volume of k。😊，I that most1 minus1 over the。

Times。To the D。The volume is dropping exponentially。So， ya。Then。

The fall of ras is to be anywhere Okay， right， Like're here。Yeah。

 it could be this ball could be here。 This ball could be here。

I guess why wouldn't it be a giveaway then a huge。Oh， so。

 so it depends on what you mean by I have to know。A ball。Well， you know， if if。

 if the ball is not known， if its center is not known， then every ball looks the same。

So all this is saying is that exists somewhere。Its center was the crucial thing。

If you told me the center， it's a giveaway。 If you didn't tell me the center。

 this is that's what I mean。We good。嗯。So one thing that now。

 because of this separating hyperplane thing that I know is that I know that。K P always contains。

My magical set。Because I'm always， I'm never throwing away cave。Oh， I didn I did not define it。

 right。Kt is equal to K t minus-1 intersect。All points。嗯。All points are z。

 such that G transpose z is less than equal to G transpose。啊，XB。嗯嗯，XB。Or the same right。That's fine。

 thanks to use the same chair。Whatever my current body is， I look at it centroid。😊。

And then I ask for， I ask my strong separation article。 Is this in the in K。And the guy says， no。

 it's not in K。 So it gives me it gives me a separating heighte。So I asked xd minus1。It said， no。

 it's。Katie was this4。30 minus-1 was this body I asked for its Androidroid， you said no。😊。

The the body lies on this side。I restrict myself to points。Where the body might lie。嗯过。

So I know that the volume is dropping exponentially。So， after。嗯。Loob。哦。

Capital out over a little lot of steps。And times that many steps。vololume。好给对。Is less than。冇可用。

哦怎 morning。哦随变什了是吧。So if at each point in time， you keep kept telling me， no， no， no， no， no。

Then after so many steps， I start off with a volume。You know， I start off with something。

 the volume looks like kind of R to the end。And this volume kind of looks like little art to the end。

And I'm dropping by a quantum factor that datata。Figer。The little has。哦。Yes， yes。

 it's a full dimensional Yeah， I guess like what happens， maybe K。Good， good。

 So hold that question until next lecture。We， we will come back to all these patients。

I just want to do the simplest case first。I'm looking for a full dimensional body。Inside this。

And all this is saying is just I'm throwing away half the volume a greater。

 not half one minus1 overee， but who cares。😊，When over reraction， I'm throwing over cooche。

So the volume is making rapid progress after n steps。My volume will h。Oh， sorry。

 my volume will go down by like。After one step， my volume will more or less h。So after rain steps。

 morally my radius will have。So the important thing is。です。Well， this should be the number of steps。

If I'm having agreed， sorry， log of this should be the number of steps。And this is really end log。

That' that's the main idea。Sorow away concentration volumeator。Central。



![](img/3f62d7720610966f9608a71a7c09edbe_6.png)

Nothing， it's not different at all。是。This is a feasibility problem and we are just casting it in the same way。

But now the problem was finding centroid was difficult。So let's do the following。

So let's run what I'll call or what is known as the eipoid algorithm。有。你。good。

 so the so so heres the thing I'm basically saying I'm starting off with this with this ball。😊。

I asked the centralroid， you said no。I half the volume， not half， but again， between France。Candroid。

You said， no。Of the volume。Central， you said no， half the volume。Suppose you kept saying no。

 suppose at any point that I gave you centroid you said， okay，re done， you are inside the body。

 then you are done。But every time you said， no， you half the volume。😊。

You can't have the volume that many times。Because you know that， you know， K has。都少是。

But it it bears saying。 Yeah， that's all we did。You cant get unlucky too many times because you know。

 there is a non trivial part of gold sitting out there。😊，Because。how we update the。

So right now for that one， I was just assuming that I have a centroid oracle。😊，That is。

 I can give it a convex set。😊，The context set idea。So in this case， I didn't need a projection order。

All I did was， you know， I。I have this magic box， you give it a convex set。

 it gives me back the central。😊，Well， I mean， like you can't give it a set。

 You got to give direction。Make the project。No， so in this case I was imagining that I would describe to it a set and it would tell me the centralroid a little weird。

😊，Bear with me。行。So here was Kachian's idea。He said， look。I started off with。

 let me draw the same ball again。I started off with a nice ball。

 its centroid is very easy to compute， I know exactly what centroid is。😊。

Now you gave me a half space， you know， it turns out that this point was not in K。

 you gave me a half space。Now I know that my k life on out here。 I don't know where。

And computing the centroid of this thing， maybe you know。

 after one cut you can compute the centroid of this this half ball after two cuts。

 its a pain I mean you know you very soon youll run into trouble。😊，这还有什么东？Let me find。

A different convict body。In particular， in ey。Which contains this good heart。Maybe it contains more。

 That's fine。But it contains the good heart。And once I find this ellipoid。You know。

 the e is kind of defined in terms of its center。Ill play center。So， here's what I'll do。

I'll start off with。Okay， not。いこす。Each time， so in fact I won't call it k n。

 let me call it E n suggestively。Is equal to sorry， ball of radius 0。My original space。

E T plus one is equal to。Some eipoid。Eep soil。 I can't spell today。And its side。转电面。

What E T intersect。All the points z， such that G T， which was the gradient at time T。

 not the gradient， whatever， the separating hyperclimate at time T。嗯。Times Z。Is。Let than equal度。没见。

Gs。The point I played， maybe I can call it the centernc。This was the center。系蛋对。This is the。

Separating hypo。I'm looking at all points which lie in the correct half。Interterssect  E。应外呢就放 next。

Is their center。So。8是的。What's that。那。对案没异。Yeah。Ex point， which 알렸 좋아。

I could have taken this to be the previous electoid as well。😊。

When I cut off half the ellip side I can put the half back， this is an elloid。

 this should be what is a reasonable ellipoid to choose。😊，This is a minimum。冇用。嗯。改了。

Why is this the reasonable thing to do， Well， I want to show that the volume of E plus 1 is smaller than the volume of E。

So。电影。Volume of E， P plus 1。欧 morning。雨B。Is。I would like it to be the 1 minus1 over3。😊。

I'd be in great shape。But I don't know how to do it。 In fact， you cant do it in general。

 What you can do is you can show this is。More or less like， and there's some constant sitting1 minus。

我 the个 one over嘅。We are reducing the volume not by a constant， but like 1 minus 1 over n factor。没看。

And you'll see this often written as e to the minus1 over n plus 1 or maybe2 times n plus1。

 I forget exactly what the expression is， I can never remember this， so I always remember this。😊。

아님 뭐 이 거 어떻게해。So， you are not reducing the volume by constant you are reducing it by 1 minus1 over n。

 how many times will you have to do this to reduce the volume by half？😊，So in this case。

 just n just the volume。 you know， if you do this n times， you will get 1 minus-1 over a constant。

Exactly。So you are just slowing down the process by a factor of n earlier you were taking n times log r over R now you will take n squared times log r over。

😊，明地。Actually it is a big it is a slower algorithm。

 but it is a poly time right now we are back in 1976。 we don't have a poly time now。😊，Great。

And that's Kaian。见。可以。Okay。Yeah， so how do you find this what you know， yeah。

Why this beast etc ceter， and I am almost there， but I am almost out of so let me at least tell you the main idea。

😊，So， the main idea is， look， whats an epsoid， it is a sort of linear transformation ofpher。😊。

And what kind of cut can there be if it is a real， well， you know。

 essentially all cuts pretty much look like， you know this。😊。

I want to find the minimum volume aipoid， which contains， let's say， the right half。嗯。

It's half a box。Where is it center going to be？This ellipsoid。Now。

 if there is any justice in the world， its center should be you know sort of symmetric with respect to all other act except。

😊，It should be， you know， a little scooted out。哦，对。So you say， well， what are you going to do？

Let's just take this center。Look at eoids which contain this right hand side， you know。

 more or less it should touch this right point。😊，Maybe the center should be there。

 it should touch this point， it should be somewhere out there。

 it should contain this entire surface like this it should you know。😊，Just about touch the surface。

Imagining three dimensions。Ellipir should be just touching this。Let's point。这个。Big Silopia。Now。

 you just， you know， you figure out what is this distance。

 this distance was like theta theta is a terrible thing。 Give me a little alpha。那就是 like one啦。

What you guys can do the algebra。So basically， you know。

 you just figure out there are only so many degrees of freedom。😊，Moular， you know。

 once you make the thing that look， it must look like this。 It must be symmetric。

AndYou just sit down and you do it。And you can find the。Now， of course。

 you have to show that this is a minimum volumeide，YeahYeah。听。And this is true for a ball。

 every ellipoid is some linear transformation of a ball so you first take your ellipoid。

 convert it back to a ball， do this do this thing and then convert it back to an ellipoid。😊。

So you had a starting ellipsoid and a cut through it， you said， oh。

 this starting ellipsoid can be transformed into this big ball。😊，This cut corresponds to a slice。

This half thing will now correspond to this new electron。行。So far so good， everything sounds great。

 and this idea was proposed by a guy called Nam Shore in 10 years before Kaya。

 maybe 20 years before Kaya。😊，Problems。All these things， you know are like computations over reals。

And the bit complexity is a complete。How do you compute？

And this really goes back to an question that I'd been avoiding so far。

 so far I was just with the real arithmetic。😊，Completely unreasonable right。

We want polytime algorithms。Polytime means what polytime means polynomial in the bit complexity of the input。

Here I have to take square roots。I'm working over quadratics， I have to take square roots。

Even if your input were just integers， you your dead。So you have to， you have to tru it。

And if you have to tru it。This means that your errors will start adding up。

Your separation articles might not be what。So， you have to keep track of errors and this is the main contribution of Kaan he was able to show that the errors could be controlled。

😊，And actually I it's already there on the web page or I'll put something you know when this came out it wasn't clear because you know Hajiian's paper was apparently a short paper I've never read it myself I should or I should at least look at it but he said。

 oh yeah the bit complexity can be controlled and stuff like this and and people were like oh yeah maybe。

😊，And so apparently there was some workshop going on in some conference center and Lacilos and Peter Gutch you know sat down and you know for two days that's what they did and they came back and said okay I think it's。

😊，But they think it's okay。And then these are nonfi calculation。 so frankly。

 I have never done all the calculations myself when I need to I look at the Bible。😊。

So there's this book it's called the Grocha Lovascribe book。你啲死哦。

How do you know the bit complexity is okay， well， we looked it up in grocery。嗯，那有요。

So so so there is one of these books that actually sort of did an invaluable service to the community by pinning down the details。

😊，And what they did was they realized that a lot of these issues， you know， strong separation order。

😊，If you are using finite precision， then maybe already your numbers are a little messed up。

 you cant figure out whether you are on this side of the ball or not。

So you might have a weak separation on it。Wch has this excellentpsil。How does the error accumulate。

你讲。Chances that， you know， in fact， forget the chances that I'm not going to talk about。

But I am going to assume strong separation orbit and just go on from there。But okay。

 so next time we'll talk about。Big complexity， at least a little bit。

We will talk about some details of ellipoid， not too many details。

 but we will also talk about how you can use ellipoid if you haven't seen this before this is just an amazing idea that you can use ellipoid to solve exponentially large problems。

😊，That's，'s like a miracle。 I think that's perhaps more than the fact that ell episodeoid is polynomial time。

I find this theorem that ellipide can solve exponentially large linear programs。

 assuming strong separation articless。그게。One of the big things。But anyway。

 we'll do that on Wednesday。