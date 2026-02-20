# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p22 Lecture_22_Ellipsoids_&_Poly-Time_LPs.zh_en -BV1a4cCeMEzb_p22-

So the last time we defined something called。So remember， we are talking about。One makes sense。

And occasionally， we'll be talking about convex functions。光的。Functions， and。For much of today。

 we'll be really talking about convets。 You know， these are。

We will always always talk about close conve sets。 and today they'll be bounded。So啊。

We talked about two things and I'll just recap these quickly from last time。A so called strong。

 And most of the time， I won't say strong。And just say， separation。玻狗。我机。So it's a。

The case that takes。Given。X and。RD， so K as always。RV。So give an X。N RD。Out。One of two things。啊。

X does belong to K。That's a happy thing。On。X is not in K or or outputs some a。

Which is another vector in RD。Such that。A in our product with。Y minus。Bang。

Let's say so if its going to output a vector a， such that for all y。

 so maybe I will say a y minus x is less than equal to 0， maybe less than 0。放咗。

Why it actually belongs to K。Some let this。化妆了。Why was。So it's giving a separating hyperplane。

 So this is giving you a vector a such that is inner a product with y。Which is sitting inside here。

Is。Less than the age in my product。So this is a separation oracle per k。😊。

Last time we talked about oh a weak separation articleacle might say this quantity is less than epsilon。

 that is a weak separation oracle and we we get into those issues when we are talking about big complexity and things like this for most and in fact for all of this course I'm not going to talk about weak separation or。

😊，They they add complexity， but。No， I don't know。 There's only so much time in there。Okay。

And we'll always assume for the sake of for the sake of this course， or for the next few lectures。

 at least that we have a separation oracle for the convicx body that we interested。😊，O。And then。

 we said。There is a problem that we define called the feasibility problem。啊。

And we define the slight variant of this problem。So okay。

 so what is the feasibility problem for k So will us okay， so so it just says output。😊，嗯。A point x。

 which belongs to K。哦塞。建去。So， given。O， a convex body K。

Either output a point inside there or correctly say that the body is empty。😊，This is the feasibility。

Fair enough。No， you might。Say， why do we care about the feasibility problem？What we care about。

Is the optimization。Over。Okay。You know， we could say。And given。Okay， again。

 we are a separation Oracle， let's say and a convex function， even a linear function F。Output。

Minimize。Apple fix。Next。哦。四。嗯。We could ask for the optimization problem。Now。

 one thing you could start doing and this is this maybe I'll be a little。嗯。You know， quick out here。

One thing that comes up is very often we will try to move between optimization and feasibility。

We could try to say， you know。Gss。A value呃 V。And then ask the feasibility question。 So。

 so we asked for。Favibility。Of the following problem。So now we are interested in what。

We are interested in。So I'll define a body K prime。Which is all those x's in K。Such that F X。

It less than a。So this is case of Vlets。Fair enough。So these are all the points。

Where the value of the function F is less thanly。And not。That。嗯。嗯。A of the。G of V。Is the empty set。嗯。

When。These less than F。With less than than minimize。off。Next。

So one thing I could try to do is I could try to figure out the largest value v for which kv is not empty。

And so， in some sense， what I am doing is Im just for every value of V， I am saying， oh。

 this is not empty out here。😊，This is empty out here， this is empty out here。This is V low。

 this is V high， I could try a V in the middle， I could start doing binary research。😊。

And try to find the smallest value V for which KV is non empty Id be very happy。By。

 what's the problem out here？靓使。So if F is a convex function and K is the convex set。

 then this set is always。😊，one 괜찮。Just one point。Good， you know。

 but a single point is a convict point，I is a convicxite。 It's like trivial a convicx。

So that is fine。 of course it' is a low dimensional convicx set there are all kinds of issues。

 you know Kegan is worried about lower con if you lower dimensional things we come back to that。

 but right now Im not even getting into that。😊，The real problem is， well， you know。

 this is binary research over the rails， right， binary research of the rail ain't going to work。

Because， you know， what's the smallest number that's non0。

Even over the the rationals is not going to work。So what can we do。So we're going into travel。

And we run into trouble in various ways。So。For right now。

 we are going to punt and we are going to say， look。We want to solve optimization。In some cases。

 we will solve optimization directly。 In other cases， we will try to reduce optimization。😊。

Where in situations where we can。Do this by。So the knifeive idea runs into some trouble。

 but we'll come back to this。 and you'll see that this idea will be important to us。So right now。

 it seems like。This is a much more powerful powerful operation。

 much more powerful problem than the fee。😊，But let's keep both these in mind。

And let's just work on the feasibility problem。So we want get all the flexibilityasibility。

Feaasibility problem for k。And the last time we gave this algorithm。Where we said， oh。

 let's start off with somebody you Okay， so so now we're going to make some assumptions on K。

And then we are going to use that to give a result。 So were going to assume。And often。

 this goes by the name of well described， But let me not do that。 Let me assume that。

K is lies in a ball。Of previous art。And there exists center point C。Such that。

A ball at sea of radius little art lies in K。So I lies somewhere out here。

 it lies in some gigantic ball， and there is a smaller ball R。😊。

Of radius little r which lies inside K。And then we said， well， you know， so given these。

The little R and capital art， and a separation article。for。Okay。We showed how to solve or we said。

 okay， we we gave an algorithm。 It wasn't completely sort of it wasn't poly time。 We didn't。 We said。

 okay， so we are given this thing。 And now we want to solve the feasibility problem。So we said。

 suppose let epsilon not。Be the。Bd， the big bond。And now， say。啊。啲0。And so on so forth， at every step。

Let's see T。Be the center。The sameroidroid。Of epsilon。f d。You know。

T C at the separation Oracle if C belongs to k。And I'll stop。They're happy， we found a point and say。

 okay。Else。Beefine E P plus one。두び끼。그。E plus 1 to the E。Intersect。嗯。没必要每一D。Interssect。

The set of all points x such that so if c did not belong to k， if this point， you know。

 if I gave this point C。And it didnt belong to K when I got at separating hyperplanes。

Which is defined by 80。 And I'm saying， this is 80。Y minus x。喂喂是啲。嗯。lessia。So。

 I know that my center of this polytop this of this body did not belong to k so now look at。

The工 sign。And go with that。So the image we have is we have an ellipse， ellipoid。

 we looked at the centroid of the ellipoid。😊，If it belong to K， we are happy， if not。

We want to take the half ellipsoid。And we don't like half es。 So what we do is we say， okay。

 we're going to try to find the minimum。Volume aipide that contains the suck。We have an e。

 We tried this center。 It didn't work out。We know that the， that gate。

 if it's non empty lies somewhere out here。This body is getting more complicated。

 It looked like half an egg。 It's not the whole egg。let's make it a whole leg。系。欢的呃。

Ellipoid that contains the sign。How do you find a minimum volume episode？ Good question。

Does the volume go down。Does is the volume of E plus 1 become smaller than ET， good question。

And we are the sort of two essential questions to ask。啊。And indeed， so here was the piano。So。

 firstly。Can find。This minimum volume volume eipoid of E intersect this half space。

 This is just a half space。You in different colors。We can find this efficiently。And one second。

And then， secondly。The volume。2，2 plus one。做 the volume用。行て。Is less than equal to e to the。

Negative1 over two times1 plus one。 If we are being pedantic， this is really。1 minus。可的。

No you have question。Oh呀还。So the feasibility。就是这么。跟住靠我咪我喺度啦吓。啊 good。Good， so。

 so here I'm going to run this for some number of steps。And I'm going to run this for how many steps。

 I'm going to run this for P， which is going to be the off。And squared。

Lob capital art over little art set。今系な。あ、こ。So， let's do the following。

Let's assume that K is contained in the big ball。And either this。哦。借点。If it's non empty。

 it contains a ball。If it's empty， I don't know。And you'll see almost nothing changes。 Basically。

 I'm going to keep reducing。😊，This for some number of gaps。And then at the end of this。

 I run out the space。If I don't find。A point inside my magical said， Kay， what should I say。아 진짜 싫어。

아 올 것 같아。I'm just scribbling something or that way， maybe I should write it。嗯。Did not。欢。呃诶。关。嗯。对。啊，对。

第 sex。四。Does this make sense？Eipoid， hac， make a new eipoid， hac， making newipoid， ha it。

 keep doing this for some number of steps。 You will see where this number comes from。

And there's going to be three lines of calculation that's。And then you know， you keep having it。

 the volume keeps reducing。The volume can't reduce too much。You know。

 the volume must be at least the volume of the littlearrow board。어 empty。

So if the volume is too small， came must be empty。You know。

 when all other explanations have been thrown away， what remains must be the truth。

And that's pretty much。This is the ellipoid algorithm。Modular。对。

Does the algorithm at least make sense。Please ask questions。嗯，还有何。ok。据于。おてます。你这个本体。I think so。啊。

I'm quoting from memory， but actually on one of the piazza posts。

 I pointed to a book by Yuri Nessterov。Where it talks about a lot of sample complexity questions。

And I think he shows that。Linear sample complexity in the dimension is the best you can do。

But have a look at Netro's book。 and if not， please post， and I'll try to find more。One thing， okay。

 so maybe let me just let me just show you at least step two out there。

So item number two out there was。That oh， okay， so I'm not going to show you。

Let me assume you more come into。You can find the minimum volume eipse， sorry。

 And that the volume goes down by whatever，1 -1 over。So， so the volume。哦二。D。

Is that most1 minus-1 over n，1 minus constant over n。就个D。Thankss volume of。Be not。

Just using fact2 repeatedly。So。Therefore。After capital P is n squared。

Lob base capital R over little large steps。1 minus。Constant overran。do theD do the加等于D。

Is less than equal to。X of minus c over n times n squared。Times R overall。Which is。At most， oh。老完了吗。

Which is at most part of a little lot。嗰个咩地事。嗯。Therefore。volume。Of the자들이 때。The that most。

Volume of the knot。但是。아六 아。그전 날 또。Go sometimes1。But the volume of Eaught is some constant。

 which depends only on n。单 R to变M。Because it's the capital R ball in n dimensions。And so。

you do the thing， this would imply。That volume of E P is less than。

This constant only depends on that。 And this is like。You know。

 pi to the n over two divided by n over2 double factor。 whatever something which depends only on n。

 remember， you know， the volume。Of our ball in three dimensions is four by 3。R Q， right， So this。

 whatever。vololume。4 by three pi a。What that。Yeah， so it's some constant3 argument cube。

And in in two dimensions。诶。我 just。By R squared。 So what。That concept， you know what I'm。

You know what I'm talking？So the volume of ET becomes less than C R to the end， which would imply。😊。

Like게。So each time if we kept having the volume， not having the volume， but reducing the volume。

 the volume would be too small after three steps。😊，Model of the story。

You are dropping the volume by one over11 over n。So， after n steps。

This is dropping like 1 minus1 over。确是没惯性。Up to cheating。So in end steps， you half the volume。

But you need to reduce the volume， you know。And log。Or over large tanks。そういうなとです。

This is n times slower than centroid。But at least， know， there's some chance of making it work out。

所嘅。The whole point is。That you can find this efficiently。And that the volume drops。All brief， okay。

 questions about this。So this whole portion is you know one of those things where it's a little technical。

 So if you ask questions you know。😊，It'll break up the monotony for me。

I'm just showing you at different。John， you have a question。 You're just scratching ahead。

See you underscore subscript。啊，O。All my constants becoming。啊。

This is some constant that's coming from my choice of capital out there。This is some constant。

 Let me， let me call this something else。 Let me call this alpha sub。

This is the constant that's sitting in front of the volume calculu。这。Basically。

 I' amm claim that the volume of a ball of radius r in three dimensions is something which depends only on3 times r cubed。

😊，So that's just thing。Garbish term that sitting out。I can never pull without。

At least when the pressure is on in the class。 I have to remember exactly what it is。More or less。

 be happy。What's happening in Epsy？You don't want to belabor the point too much。

Maybe I'll mention just one last thing。그 is嗯O。I should mention a bunch of other things how do we find know how do we even specify an e sorry？

I mentioned this in the piazza post， but then I realized I should at least do it once。

 how you how do you write Alexex。How do you write an Alex？S。The center plus a covariance。

So in left side。And I always have to think back， oh， you know。

 how do you write ellipoid and so is at least if it's， if it's。😊，You know。

 access the line and stuff like this。 This is simply saying X squared over AI is squared by going from one to D。

😊，So in general， we have a positive。Semi defnet matrix。 This is a covariance matrix。Q。

And what what we have is we have the ellipoid， which is defined by all points x。

 such that x transpose。Inverse。Forト one。And for me， this always used to wonder why。

The Q inverse is that。 And maybe I'll just just say it once， and thenll I'll move on。

Just imagine that what we are doing。😊，Is we are。We are taking points。

 we are taking a linear transformation x is getting mapped to tell of x。Let's say El。嗯。For rank。

And what we want to make sure is that。So what this map？What it's doing is it's taking。

Point so so now the question is， what does this map map the sphere onto map the sphere onto maybe map the ball onto So this is the ball。

 This is the unit ball。 What is this mapping it to And my claim is it's mapping it to an episode。

And what's happening really is is that all the points out here。

So what we are interested in is we are interested in all the points x。Such that。L inverse x。

No squared is at most one。So Im interested in all points out here。

 such that if I take the L inverse map。They should lie the boy。And what is this。This is just X。诶对啊。

L inverse x。supposeupp。诶。And there's X。Yes me equal to one。Actually， forget the less than equal to1。

 I'm just looking at this expression。😊，And this is just x transpos。诶。L inverse。Now L Franpo inverse。

And now if I take。Defin。Q is a transpose。Which is positive to me that。So in this case。

 because L is you know full rank， It will be positive definite。 So I don't come to any part。😊。

Then we have， this is just x。Frans。So that's all I'm doing。That's just that if you have a TD。

Absolutely， so basically， I started off。 you know， I said， oh L was full rank。So。

 you know it has inverses and all that。 So in this case， you know， Q will turn out to be full。F。

So really basically what we are saying is up to linear transformation the L side is just a ball。😊。

So now what we need to do is we need to we can always move back to the space of a ball。

So whenever we want to take。You know， I'll just do the picture， right， you know。啊。

A coupleuple of years back。 I actually， a couple of iterations back。

 we did all the calculations for computing the minimum volume my electrode on the board。 It was。

 you know， I think I， maybe。😊，Two or three of the students I never saw again。

Maybe we shouldn do that。But here's good thing。You know， I want to take half this ellipsoid。

So I should move back。Using the sum L inverse transformation to the ball。I want to。

Fig out something about half the buzz。 So what am I going to？But half the boil。

There's an explicit calculation， which I've given in the notess。Of how to compute。

The eipoid the minimum volume eipsoid out care。So this gives you this， I look sorry。You know。

 this is an explicit。Calculation， you can just write down a close form expression。안 몇칠。안 내 소。別に。去。

It contains。If you do the calculation， I urge you to at least read over it once。😊。

I'm not going to do this。 if you do the calculations， you will see that actually you can。😊。

You can get an explicit angle on the volume。More or less。And the issue again。

 I briefly mentioned this last time。 So again， I'm repeating myself。The， the real problem。

Is that the numbers get。Very large because you have to take square roots。And in general。

 the numbers get large as you you're multiplying numbers together， the numbers can get large。

 And how do you control that。So。That that's that's a question that will keep coming up again and again。

 And there's no avoiding talking about it。 So I'm going to talk about it for the next 1520 minutes。啊。

But controlling the size of the numbers was exactly， you know。

 a big contribution of Kachan when he gave his。Polytime algorithm for linear programming using the al。

So this is the general idea of the ellipsoid method。For feasibility。Given a separation article。

 I'm going to point a point inside the context。More or less， okay。There are several issues。

 Let me write the issues here firstly。Big complex。The second is。Low dimensional， you know。

 non full dimensional。What's that's。Good。所。suppose suppose。

Suppose we start off with a linear program。You know how do we ensure it。내的个么。你仔。

Its also related to non full dimensionality。So let's， you know， instead of keeping things abstract。

 let's actually dive in。 Let's let's talk about。Explicit things。



![](img/95a36c2e74ccd2a19994fb6894962b8b_1.png)

Let's take a。

![](img/95a36c2e74ccd2a19994fb6894962b8b_3.png)

![](img/95a36c2e74ccd2a19994fb6894962b8b_4.png)

![](img/95a36c2e74ccd2a19994fb6894962b8b_5.png)

![](img/95a36c2e74ccd2a19994fb6894962b8b_6.png)

![](img/95a36c2e74ccd2a19994fb6894962b8b_7.png)

Let's take a linear program and in fact， let's even look at the feasibility version for linear。😊。



![](img/95a36c2e74ccd2a19994fb6894962b8b_9.png)

Let me define K。Is equal to all the set of points x。In R。Such that AX is less than equal to be。喂 a。

Is a matrix in M cross N。Be the vector。And RM。And this is in end dimension。就发。

Let me make some assumptions， and we'll get rid。Actually， before we do this。😊，Suppose。

Kay has points in there。Suppose K is not empty。Then。Let's try to find one of the then you know。

 let's try to say I want to find one of the solutions to this。This， this L P。Actually。

 let let me work with this for。Then I want to say that what does k look like k looks like a polyhedron。

 it might be unbounded。What do we know about the corner points？What are the corner points。

 Cor points are called verticitude， they are called extreme points。

We called basic feasible solutions。咩。What's a basic feasible solution。There are if you know。

 then suppose x star。Its a basic feasible solution， suppose。

What does the X star look like X there are n， suppose this is x star。That are n。

Tight constraints here。Right。This means。That， if I look at。The constraints out here。

 N of these are going to be。行。So lets let's call these constraints A1 transpose x is equal to B1 up to A and transpose x is equal to B N just by remembering。

 I'm just saying n of these are tight。 Some n of these are tight。 I'm just choosing n of these。我。

They are tight， they are at equality。So this means that some system a a tilde。X is equal to B tilde。

Where this has full rank。They were n tight， and in fact。

 I should have mentioned linearly independent。Constraints， right。So this is a full rank system。

 I've just chosen N inequ N inequality O。 I'm saying they are equality。

And they are really nearly independent。So this is a full rank system。This uniquely specified x。So。

Next done。Is equal to a inverse。Can somebody remind me what how how we could compute the entries of X？

Cousian elimination， but there is even a compact formulation for this。

 Let's not worry about running time。We said x star I is by Kramer's rule。The determinant of a。

Where you remove the I column from here and you add it in the sort of B。

Divided by the determinant of something。Some determinant over some determinant。

The entries of these determinants are given by entries of A and B。😊，So it's some rational。

This is the last。How big is this rational number。suppose。All lane trees。And A and B。Use。En。

Every entry。Suppose every entry is in。Use evidence。

How many bits will the determinant of this beast take？

The determinant is the sum of n factorial terms。So how big can the determinant be， the determinant。

Can be at most end factorial times。Q to the L is the size of。Each。Number。

 because they are L bit long， They are integers。Im multiplying n of them together。

 so Im just looking at the whatever light extension of you know whatever form of the determinant。

It's a sum over n factorial terms， which are each of which are this big。So对。ナンバルでックす。

To write this object。Is that most。And log again。不现下。Its。

Each of these is polynomial in the length of tang。The length of the input。Was you know。

 end time sale。 This is like polynomial。This is a rationale whose numerator and denominator are both this much。

😊，I can represent a rational other temple。So the number of bits to write down this rationale is like most this much。

Two banks。There are and such rational。So the size of this thing， the size of。Ex star。

 so the save in bits。Aect most， poly。So if I wanted to ease right down。

 I wanted to show you a solution to this LP。I can show it to you by exhibiting polyanol。Bs。

The size of the size of the output is polynomial in the size of the input。

Linear programming lies in M。I can show you a solution。

Which is of size polynomial in length language， you can check it yourself。

So at least I have some hope of writing down the solution。Right， how do I start？So far， so good。

So here's what we。He子。So I said， okay， suppose K was not empty， then there exists a point。😊。

Whose bit complexity is polynomial。I can at least write it down。I want to use eip to solve this。

To solve feasibility， to find a point inside here。아도야 되지。So， first of all。Suppose。へ。Not。볼 내 안。Yeah。

 maybe let's look at the easy case。 Suppose case full dimension。Okay。Is。

The sort of conex hell of points。Of endpoint， which are linearly independent。N plus one points。

 which a linearly in the order。One of them is origin。 Let's say the another point fell element。Okay。

It is full dimension。 So on a claim there exists a tinyy tiny ball which must lie within。😊，Wai。

Each of these points has bounded bit complexity。So if I take a bunch of points。

 which all have bounded bit complexity。They must enclose a reasonable amount of volume within themselves。

And they are linearly independent。So I want to use this to say。They exist。아 안 뭐 하지。Oh various。

At least。1 over two to the body。And add。And。唔细。One has to do the calculations。

 but this is more or less what's happening。😊，If K was full dimension。

 then it must contain know a very tiny ball。But a ball nonetheless。

 which is completely contained within care。People look worried。已经是。

It seems like more of like maybe a fundamental。Yeah like。啊。So， I。

So here here is the sort of question of what is little R。

 I have to express little R in terms of something。😊，Because I could say， you know。

 k consists of all the points，0 and you know，2， the minus2， the2， the2 the n。

Doesn't contain a very large ball。AndYoull say， okay， the ball is tiny。But that's the way it is。

So if I want to show that linear programming is in poly time。Let's say there is my goal right now。

I want to show that there is a ball。Whose volume is reasonable compared to the input length。

Now I'm saying， oh， in this case。Od is this much。So I have some chance。So my body K。

 if it's not empty， it contains this tiny。What can I say about how big a ball？

Can this you know how big a ball would I need to contain all of care。

How large could these numbers be？ We were talking about how small could these numbers be。

How large could these numbers be， these numbers could be this large。So I could take a raius。Which is。

 you know， whatever that much of it， poly and。啊。This contains k for sure。One issue you。

K could be unbounded。病啦。Just suppose。We'll come back to。So the claim one would have to make is， well。

If。You know， K must have at least one corner， which is close to the origin。And really。

 this is saying this has at least one corner， you know， any basic feasible solution， any corner。😊。

Is different like this， right。So any corner is close to the origin and all I want to solve is the feasibility problem K could be going off to infinite。

😊，All I want to make sure is K at least has some non non empty intersection out here。

I looked at a corner of。Its a basic feasible solution。

 And when I said any basic feasible solution has bounded a bit complexity。😊，So if I draw this ball。

 it will contain。我。The basic feasibility solution。It might not contain the extreme ray。

 which are going off the infinity share。 know what the heck。 There's nothing to be done。

But all the corners must be sitting within this one。All I wanted was one corner。

 I'll get all the corners。 It not。系啊。So I can even ignore all this。

 and I could say I'm just interested in this portion of。So king。If case is not length。

 it contains this timing board。And it's contained in this big ball。So the number of steps。

For Lide will be order n squared times log。어夹 loud。But log of capital La over little La is。不。上んですね。

Let me you know let me not talk about the non full dimensional I mean。

 there are two solutions to non full dimensionality one is you could say look。

 k is not full dimensional， find the subspacecing which k lies。😊，Throw that in as constraint。

Now this is your problem。 I mean， just basically rotate yourself， rotate k so that it actually。😊。

You know， this， this key is now full dimensional in that subspace。

 Just restrict yourself to that's subspace and solve the problem。You could say that。

Here's another way you could do this。 You could say， well， K is not two dimensional。

 K is a line in this two dimensional thing。Let's do the following。 Let's ften out。

Let's extend it a little bit。In all the other dimension。This is a dangerous operation。

 You're introducing new points。So it will really come down to how much you fatten this out and what do you do with this factor。

Let me come back。This。Okay。そ所す。Good， so it depends on how you are given the body。

Then you would need something stronger than a strong separation orx。Because otherwise。

 if you're just given a strong separation article， you're like trying to find。

 you're trying to find a line in three dimensions。 You know， you'll be。 you're just you know。

 playing around in the dark， right， It's impossible。So youd need something strong。

Then then strong separation of。But for the moment， let's imagine we had a full dimensional body。

 say it had a tiny ball， it had a big ball。 I start reducing the the。😊，The case。So sooner or later。

 I'll find the point which is either inside k。Or I'll say， cave I empty。Because if k is non empty。

 it contains significant this much volume。So let me raise the stakes。How are we doing， We O so far。

Mostly following。系。です。So I want to go one step further。I don't want to just find a solution。

I want to find an opt。So what do I mean？I have a problem。Minimus c transpo x。A。Yeah。Good。So。

 let me try to do the the usual thing I will say oh what was I trying to do I was minimizing C transpose x。

 so let me try to find solutions。😊，啊。Like this。I have to guess。How large can we be？Well。X。

 each bit of x is that most each entry of x is at most due to the polyanl。

So C transpose x is at most。L times poly Nl。Long。forget the bits， so D。Lies know。

The the absolute value of B is at most。The absolute value of D you know。呃，VX是点有利。Its less than equal。

F enough。the only like forward。Well， there' only that any squared。啊很 good。

So Joey's suggestion is there's only so many things to buy and research over。What's the catch。看这里。

Sub the item them。哦そ we don。Good。So， so let's not worry about that。풀리멘스。The point is， you know。

C transpose x is less than equal to B。So I know。These are all the numbers。You know， this is。

Let me give me a large sounding con， a large sounding letter。And。So I know that B。

Ls between you know， the optimal value lies in this range。There are only so many integers。

In this range， so log of that many integers。😊，Is a reasonable number。How do we done？Can we just say。

 oh， I want to find a solution which is at most。You know， 2372， 2451， etc cetera， et cetera。

 binary research。😊，Over the teachers。IB research over this。Suppose I say， oh， let's try this。 Let's。

 let's try 0。It's feasible Sure， then the optimal solution can't be here。还是你说 that备。

Let's try the midpoint out here。This is non empty sure the solution must be here and so on。

 I'm doing binary research right。The problem is。This solution。Ma need not be increased value。

We just said the optimal solution could be rational。喂。그 같은 더。

I can't do binary any research over the rational。Between every two rationals exist in another rational。

마서시 하는 거。将医生过嚟。Yes。😊，So what do we know， we know that the optimal solution is rational but with bounded entries。

😊，I know。The opt。Thanks。Has nuerated。Deenoinated， bounded by some。诶。And。And。City Cl for X stuff。

A that most M in absolute。So the question then comes。How do you search efficiently？

Over the set of all。Boed， bounded complexity ra。轻心网。We thought and do we do like。Yeah， yeah。

 You can do continue things you。我说さ。Yeah。So here's the thing。

 Let's even forget about everything else。 is our x is one dimensional。😊。

I want to find the best solution， so I know。The best it's the same line。I know that I want to find。

This is X star。 X star is just a scalar。Next， step is。ピ over Q。And P And Q are not too large。

How do I， how do I find？How do I find the same？So I don't know if you guys did。내 한번 들어 먹 됐어。

What was the problem。Shortest path， right。知れフト。民明さ。Okay， those of you who didn't do it。

 you don't know what I'm talking about。But really， you know how do you find this。

 supposeupp the optim solution is one third。😊，I start doing binary research， I'll get half。

 I'll get three quarters， I'll get， you know， whatever。But I'll never get to one third，So I I know。

 you know， whatever。Im doing search between0 and1， half one third is know smaller than this。

 one quarter。 it's bigger than I do。What am I doing now here？Three8。Et cetera。

 but I'm never going to hit one third because I'm doing my research。By。

What you can say is after youve searched。So maybe I'll draw a picture here rather than。

I'm looking for this extra。This is my solution。 It has。Bounded numerators and denominators。Now。

 what I'm going to do is I'm going to look for。A body here。I'm going to say， look。

 I must be so close to X。Like， this ball contains。At most。Wan。Rational。哦。哦。Deenominator。At most。压不出来。

So once I am， you know， I'll find some solution X， which is close enough。To this to， you know。

 in this ball， wherever I am， I am close enough。I can be， you know I'm not too far。

 so here is what I'm going to do。I'm going to show you。 I'm going to find。And x。The。Distance from x。

To x star。His a， actually。C transpose x minus C transpose。Da。This is just a scale of。

Is that most some。am。我文。肚脸了。What am I doing， I'm doing binary research right？

I'm doing binary research。I found an X。Such that C transpo that。Is less than equal to。

C transpose X plus some tiny tiny amount。完了。So， this will imply。How how different is this。

 This is just。哦。C transpose x minus x。Visk quantity。Is that most。

 this is absolute value is at most the length of C。Time the length of x minus X。How large is see。系冇。

Andtime2 to the or something like that。但是人就说。So the point I want to make is that this quantity is timing。

That I am very close。I am sitting at some point which is very， very close to X。😊，And I guarantee。

That the ball of this radius contains at most one rational。Of this complexity。

So if there's only one rationale of this complexity， I can move to that rationale。So if I just said。

 look， I have found the correct answer， you know， I don't know one third， one， you know。

 whatever I have found the correct answer。Up to an error of one tank let say。And I am at， you know。

 I'm looking for rationale with bounded denominators， denominator bounded by most four。

So then if I am at you know some number like this， I can say， look。

 the closest rational to me is maybe one third。The only rationale in this window is at most one third。

 all other rationals are very large。呃你老。And thats the that is the idea。 and that allows you to say。

 look， once you are close enough。😊，Through the optimal value， you must be at the， you know。

 you are not at the optimal value， but you can just move immediately to the optimal。Yeah对这个。

Thenominator。W， if you take one。まて前。前咩 b m。Maybe I'm doing a little bit of。Okay。

 so how do you jump to the abstract， Maybe I'll， you know， I think。sorry。Yeah。

 let let me let me defer it to a piazza。It''s， you it's fascinating， but it's maybe。对不对呀。😔。

This might be a lot going on already。More or less， okay。系嘅했어요。There's a lot going on。

Let me just very quickly。Sometimes saying it faster is better than saying it。

You want to use the ellpson。What do you need， You need a tiny ball。You need a large enclosing bottle。

Actually， the bond is not important。You know， it could be a tiny ellipa and large ellipsso just you need the volume constraints。

 you need to make sure that that you know， once you have two smaller volume， you can say do。

 it is empty。You need a large enough volume so that not too large a volume， because otherwise youre。

You will take a lot of time to reduce this。Then you start， you know， you start playing the game。

 you find the central， you find the center of the ellipsoid， you slash， you find a smaller ellipoid。

 you slash y ellipsoids。Because you can find a smaller eoid which contains half an eide。

You can't find a smaller ball that contains half a ball。

 because it' the only ball that contains half a ball。 It's a whole ball itself。Good。

So far so good you start walking once the volume is very small， you you are done。

 you can either say its not full dimensional， but actually it can't be full dimensional because it contains a ball inside there。

So it must be empty。So you can solve feasibility。Once you can solve feasibility。

 you can solve optimization。Because of the。But here I used crucially that the numbers were abounded with complexity because I cant do inte I can't do buying research over the reals。

包 over the大。So I said， oh， in teacher sorry。LPs have very nice structure。

 All solutions that Im interested in have bounded with completion。😊，So I can kind of work in this。

Space of bounded with complexity numbers。So this way， I can find。I can reduce optimization。Do。

Feaasibility。이젠 그래。And this is really the approach catch。But then。So， so let me write down the the。

And you now there's going to be no more things being thrown at you。 maybe I'll just。啊。

I will throw something at you。 I'm sorry。啊。Let me just say， okay， so the theorem。Is。唔记婚。And b。喂。

And constraints。And variables。All numbers。Atmost every bits。诶。Eipide。Sos。诶。And well。

 ellipide returns。And optimally。Basic a solution。And time。玻璃。And and。Often， this theem is called。

LP in poly。Good， so there are various algorithms， the the ones for ellipoid。

 I don't remember exactly what the current state of the art is。😊，嗯。

We will see interior point methods a little bit in the next lecture。

And that you can pretty much reduce it down to matrix multiplication time。So is it like on the same？

Like interior。可以。I think。Maybe it's factor of n。I think it's like into the 3。5 or so。

I'll have to double check this。 remind me。 Hey， Mad Susan。

 you got to remind me of a couple of these questions， maam。And in fact， not only him。

 you guys should remind me of questions I didn't to answer。

But the most interesting question that I the most interesting theorem that I find is the following。

So let's go back to just thinking about Alex。So what did he say？未ロ経の。Here is an LP。

 it has bounded complexity。O， what do I mean by bound complexity。

 All numbers have small bit complexity。 so there exists a good solution。😊。

With this kind of argument that we did。Cmer。Good。So let's start running ellipoid。

We need a small ball。 Okay， we got a small ball。 We need a big ball。 Okay， we got a big ball。

What do we need？You need a separation oracle。So all we need to run alexide。Is。

A separation oracle for the polytop。I don't need to know the entire real。I need a magic box。

That when I feed in a solution， it says， aha， you've satisfied all the constraints。😊，好，啊啊。

Here is a const。 You have not satisfied。You are sitting on this side of a constraint。

 The constraint said you should be sitting on this side。So this leads us to theorem2。

 This theorem is often called。Separation。啊。Ins optimism。So suppose I want to solve this。Suppose one。

The size。The LP。诶。Which is let's say I'll just write it out。

 even though I don't really need all the trimmings of this LP， AX is atmost B。Okay。All numbers。

The at a bit long。M constraints。And variables。Right。靓。Anex side。フランス？Oh， we here Dars。And opt。

Basic is the solution。And但。播鱼。N number of dimensions。A。Yeah。嗯。Strong。Actually。

 the theorem also hurt for weak separation ors， but I not separation。😊，어 알아 저。For the poly okay。

Which is。So if you could give me。A separation oracle for this region。I。

 my dependence is only on the number of dimensions。And on a bit complexity。

Not on the number of constraints。Examples， I mean， the examples are numerous。 and in many cases。

 these are。You know诶。So I think that is so yeah。レです。Give you an example。 So an example is。Min cost。

Perfect matching。Mim my C transpose x。Well x belongs to the space。Of all the edges of a graph。

Main course perfect matching so I am saying x of delta v is equal to1 for all vertices being in the graph exactly one edge incident to every vertex。

And x of Delta S。Is at least one。このエ。Subse divorce seeds。Yes。错。This is the x is non nonlinear。

This is the perfect matching polycop of E。This polytop。We didn't improve。 We claimed。

 We didn't prove it。 this followed with the integrity， all its。Vti see。

A exactly the perfect matchings of the graph。This polytopbe has an exponential number of constraints。

But we can solve it in polyta。好。Given an X， we can find whether all the constraints are satisfied or that exist available。

😊，I'm sorry。Find min cut， but in this case you will have to find min odd cut。It's a little trickier。

 You'll see this in the next one。But here is here is another LP。

 let me go back to lecture number two。I have a directed graph。I want to find a Min cost avariescence。

Sa stand。So， x now belongs。To the set of all directed edges of the graph。

 such that if you look at all the edges which leave a verortex。

 there must be one of them for all vertic Cs V。😊，Which is not equal to the root。X of all sex S。

Must be at least one for all subset， S of ver PC， S。The the flash that。The root。Does not belong to S。

For every vortex。There must be one as leaving。For every cut。

Where the root is outside and there are verticeses here。

 there must be one edge living towards the root， Min cost arbescence。

Exponential number of constraints in this case。It's exactly man。For all these cuts。

 you want to make sure that you one agent。Exponential number of constraints you can solve in poly time。

How you can find a violated constraint。So if you have an exponential number of variables， never fear。

You can 싸。And you know， again。Small time。 But on the homework， you'll see。One more。

Its one extra idea。Once you have this powerful idea。You can combine it with another powerful idea。

And in fact， the idea that I call the secret protagonist of this course， duality。Re fine and hot。All。

 next homework。So the way I always think of this separation implies optimization。

 LP is that the LP looks like this。😊，Number of constraints。And the number of variables is tiny。

And you want to say that this is at least。And all you need to do is give an next point to a constraint and say。

 that's violated。That's violated。 That's violated。 That's violated After polymany steps。

 Nothings violated。 be done。You might be interested in。Solving LPs that look like this。

s fairair enough。ていうことで。Seems slightly under constraint。 Maybe y is greater than equal to0。爱吃秀。つくですね。

Now， it's fine。They areる you know。It's not under constrained anymore。Beauty of this situation。

 This situation arises very often。 And those those of us in operations research。😊，You know that。

 you know how to solve these things。 you use an idea called column generation。Forget the you。

 it's just a name， but here's the main name。This LP has a duall。They do one look。Maybe I got little。

系啦。Suppose you could solve it do。How can you take that dual solution and bring it back to a prim solution。

Soil homework number 4。Homework number 4 problem 4。Something like that。 I don't even remember。

It's exactly this question。 How do you solve。A short fact matrix。E。Well， you solve a you。

 tall skinny matrix。And use to。So really the question will come you know， how do you solve this。

 why do you solve this and here you know as long as you can come up with a separation Oracle for this LP you are in great。

😊，Anyways， let me stop here。If nothing else， you know， there were details。

 And I wanted to give you a sense of how all the issues that come up in solving。Eipso。

 I only talked about maybe 70% of the issues that came up。

 There are some of the issues that we put aside。 or we couldn't do that。

I'll talk about some of these in piazza。But really。

 the things to remember are ellips solve LP in polytime and。😊，Separation implies optimization。

If you can separate， you can optimize。首先样的是。I keep talking about theorems that I tend to use all the time。

This is my。Every so often， I don't know how to solve this L P or I can separate for it。

Or sometimes even better。 I don't know how to solve。 I mean， actually worse。 But anyway， content。

 I can't solve this L P。 or can you separate for it。No， I can't even separate for it。

 Maybe the problem is hard。Often leads you to heart。So it's a simpler problem， given a solution。

 can you check whether it's notifying all the constraints。If you can't even do that。

 maybe you're in trouble。And then let me stop here。On Friday， well do。A short lecture on。

Inter interior point methods。Becauseuse actually， I don't know if any of you saw young Liu's talk So young Liu gave a talk yesterday on。

Using this fast， new， fast algorithm， nearly linear time max slow。What is the crucial ingredient？

The interior point method。So we should understand a little bit of。所 we论你咩 don大同开的。Right。プレー前ンスてよね。

Sorry， this has been a long week。 I'll see that inside。

