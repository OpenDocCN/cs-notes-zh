# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P19：-19-Advanced Algorithms (COMPSCI 224), Lecture 20.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/bac2cd1f3df7c048a60b6bbc5a90f2ba_0.png)

あはささか。嗯。Okay， so today we're going to。Finish multiplative weights。

 I just want to show you how you would apply it to linear programming to solve linear programs or approximately solve them。

And then after that， we're going to。Switching to a new topic， namely Fs。So。呃。

So right now I'm going to talk about， oh， and someone， yeah。

 so Eric just asked me when you're going to get， are you going to get feedback for。

Your project proposals， Yes， you will。 So I think I should be done by the end of Sunday。

Like into the weekend， let's say， okay so。I'm looking through those to give people feedback。Okay。

 yeah， so applying。Multipplicationative weights。To let's say， LPs。

So let's just remember the theorem from last time。So theorem。We said that if you。嗯。

Use multiplicative weights to come up with the probability of vectors in each iteration。

 You get the guarantee that。Yor。Some have expected costs over all the days， so this is M。Qi。Dot P T。

 So P T is the probability vector you output over the experts in day T。

 M T is the cost vector on day T。 Remember， M T， the I coordinate of M T is。The cost of the I expert。

嗯。On d t。This quantity is at most。The min over all I。From one to n。So there are N experts。

Of the sum over T。Of the cost of that expert on day T。Plus。Epsilon。So this is for all for any。

For any epsilon？Between zero and a half。Epsilon times the sum of MIT absolute value。Plus。Yes。

 lawn Ed。Over Epsilon。对。That was the theorem from last time。Okay， and remember。

 we assumed that all our costs。These entries of these cost vectors。

 we assume they're all between 1 and 1。Okay。So in particular， this sum is over all the days。

So this sum is at most t。So you could also say this is at most of the min over eye。Of some over T。

 MIT。Plus， epsilon T plus lawn n over epsilon。Okay。And。Right， so this is true for all epsilon。

 So you can true， you can choose Epsilon however you want as long as T is like。

 say bigger than two long n， for example， you can pick。嗯。You can pick， for example， T2 B。

Se these two things equal by choosing Epsilon appropriately。

And this thing will be at most the min over eye。S over T。MIT plus Ro of Law end。Over tea。Okay。So。

 if you choose。Epsilon。To be。Root。诶。Law N over T。That's all right。I seem to be。Off somewhere。Sorry。

In the definition of Epsilon。Here。No， I mean， I want to say that if I play for a lot of days。

 my air goes down， right？を出すように。Right。Oh， I see， okay。嗯。Oh right。 then yeah。

 So I guess normally people， people talk about maybe the average regret。

 And then that decays like1 over T。 So for example， if you look at the average。

The average thing here。The average。We'll go down like then I think this is okay。嗯。

So you'll often hear people talking about like， so this quantity here。

 the stuff beyond kind of the optimal bound you want。It's called the regret in some literature。

So people talk about trying to minimize regret。 So you'll often hear people talking about kind of the square root T and。

Loss and regret。 Okay， so that's where this comes from。

 It's my particular choice of epsilon running multiplicative weights。So there good。嗯。So now let's。呃。

Let's apply this to LPs so LPs。I want to have。So I want to check feasibility。These our ability。Of。

X and P and AX is at least B。Where。P is some convex set。And a。Is an M by a matrix？

And I want to give a definition。So we will be considering。呃。Sub problems。Of the form。

Does there exist？An X such that P transpose A X is at least P transpose B。For P。

 a probability vector。A rowe bounded。Orracle。Is an algorithm？Which， when given。

When given this problem star。Either。Okay。If such an x exists。Output。An X such that。嗯。For all， I。

AI dot x minus B should be at most row。If no such X exists。You know， outputs。Infeasible。Okay。

So notice that。If the actual feasibility problem， if this problem is actually feasible。

Then because the entries of P are non negative。This problem will also always be feasible。

 and also P transfer actually should be greater than P transfer B， and X is also in P。

So this feasibility problem is what the oracle should decide。And I just said if that's feasible。

 then certainly this is because take an x， which is feasible for this。

 and then just put P transpose on both sides and by non negativity of P。This。Inequality will hold。

Questions。Yeah， we assume that the oracle given so the Oracle is given P。The Oracle knows， oha。

 so it knows capital P， the convex set， it knows A， it knows B， and it knows little P。

And then it wants to know the Oracle will tell you whether or not there exists in X such that this thing is to make this feasible。

The first point。ToE fruit Iowa。サ。啊嗯。어 constraints。Oh， I see。そでおいしいく。No， no， no， no。

 but this is an absolute value， right？It could be the case that AI。tX is less than B。

But the Oracle just guarantees that the difference in magnitude is small。Yeah， yeah。 So， I mean。

 you're right。 So if I had said that。So really， if I had said， you know this。Where Roe is positive。

Then this this would have been feasible。But I put absolute values here。

I'm not telling you anything about which one is bigger between these two。Does that make sense？Yeah。

 so this X doesn't have to necessarily be feasible for。The original problem。More questions？Okay。So。

Okay， so now I want to tell you that if we had such an oracle。Then， we could。

We could get an approximate LP solver using multiplicative weights。

And I'm going to describe that now and then I'll go back to。

 I'll say just a few more sentences afterward about the example I gave last time with set cover to tell you how you could get such an oracle for a set cover。

 for example。Good。嗯。Yeah。Okay。どスタエンと。far away。ほいと？梅こ。No visible point will you closed。

But said so you said add a constraint， which what， which is far away from the feasible region？Okay。

Yeah。That the whole piece up。So。Point first for whatever。Understanding means that。对。

There exists feasible point X， returns， it outputs point which is close to。So wait。

 so when I say if such X exists， if an x exists， which is feasible for star。Yeah， okay。あウこ。Yeah。都哦。

This社把 you。Yeah， yeah。Right。ages。Yeah。我得ぶ。Then your row might be terrible。Yeah。

 so you just get a bad rub。Yeah， I mean， so， you know like。

We're going to end up thinking of this T as being the number of iterations of。

The number of iterations of multiplicative weights。

To get some good error So as T gets bigger and bigger。

 our error in violating feasibility will shrink。And the number of iterations we need will depend on row。

 So in your example， if， you know， if you're。If you're coming up with a polytope such that the row has to be very large。

 it just means that multiplicative weights will run for more stepss。

DoesDoes that answer your question Okay， good， any more questions。Yeah。Yeah， so sorry。

 this capital P is the convex set， this little P is the probability vector。

 probability distribution over experts。Yeah， yeah， yeah。

 so exactly it should both be in capital P and this inequality should hold。Does that make sense？Okay。

 and notice。You intuitively， this seems well， seems like an easier problem than that because this has M constraints and this has one constraint。

I mean， aside from the capital P business， right？嗯。These are just numbers。Okay。So good。

 so what are we going to do？So。In each。So now let's。Analyze。Multipplicationic weights。For。嗯。

For LP and the theorem。Is that？If。We have。A row bounded oracle。For row bigger than epsilon over2。

Then。We can。呃。Use multiplicative weights。To find。X and P， such that。呃。

AX is greaterd than equal to b minus epsilon times the all1s vector。In。Oh， of。R squared。呃。

I think row squared。D row squared let me think， Law n。Lun M over Epsilon squared。Iterations。Or days。

T。So let's see how to do that。So I need to tell you what the actual algorithm will be， so proof。

So what are we doing， multiplicative weights on， what are the costs， what are the experts？So。

The experts。AAre the constraints？So they're M of them。Okay， the next thing is， what are the costs？So。

On day T。We have。Some pity。Remember how multiplicative weights works。

 So we've gone some number of days initially on the first day。

The first AP is just the uniform distribution on all the experts， right， And then gradually。

 as we've been running multiplicative weights。呃。We change this PT vector。

 and now we're at some dayT and we have some PT。I want to tell you how I'm going to define the cost vector。

So remember the theorem from multiplicative weights。嗯。

MT can be chosen arbitrarily or adversararily after you choose。

 just like before when we're talking about learning from experts， after you make your decision。

 the costs are revealed to you like who's wrong and who's right was revealed to you right So the same thing here after you choose your your P vector。

 your PT vector M is revealed to you。So I want to tell you。How we're going to define M。

To ensure to make it do what we want to prove our theorem。A。We define the cost vector。To be。M T。

Is1 over D or one over row， sorry。Times。A。AX minus B。Or Xd。Where。X T。Is the output。Of the oracle。

So we give the Oracle PT。And we tell the Oracle to give us back XT。

Now the Oracle might say that there is no Xt。😡，The Oracle might say it's infeasible。

 but if it's infeasible。😡，Then if this is infeasible， then as I said， the original is infeasible。

 right， That's the contrapositive of what I said earlier。So if the Oracle says there is no Xt。

 we just halt and we say， sorry， this LP gave me is infeasible。But if it gives us an Xt。

 then we're going to define the cost vector in terms of that Xt。Okay。And。Now， what do I want to say？

嗯。What do I want to say， I't you get。Confusing myself slightly。Okay， so now what I want to say。

 I want to say that。MT。Dot product with PT。What is that equal to？That's equal to。PT transpose。

Times this thing here， went over a row。嗯。A X T minus B。Sorry， this row。

Sor of looks sort of like a pee， doesn't it？Yeah， so。I really don't like that。

 I should have noticed that this might happen。 Let me just call this alpha or let me call this。Yeah。

Okay。Okay。Which is equal to。Oh， and notice， right， so this thing is in minus11 to the M。

Which the theorem needs。I mean， the reason we normalizedize by this gamma was to ensure that。Okay。

 so this thing is equal to。One over gamma， PT transpose。A X T。Minus PT。Transpose B。

And what can you tell me about this quantity？Thing inside of the brackets。Yeah， it's not negative。

I mean that's what the Oracle does， it solves this feasibility problem。

 so we know that this thing is bigger than equal to that。Okay， good。Now， so this is one direction。

 We know that。嗯。This thing， we know that this quantity is bigger than equal to0。

 but we also know that this quantity is smaller than equal to something。

Because of our multiplicative weights theorem。 right， So we know that now0 is at most。

I went over gamma。嗯。P T。哦。Zero is at most， let's say MT。pt。So we can sum over all tea。

And that's still true because each one individually is non negative。And then now。

Let me now apply the MW theorem。Does that most？So let's so for all I。This thing is at most。

The sum T from one to capital T of。MIFT。Plus， and I don't need the stronger version。

 I'll just say that this is at most Epsilon T， plus Epsilon T。Plus， lawn M。Over T， remember。

 M is our number of experts， the number of constraints。And now let's expand this out。

 This is equal to one over gamma times。The sum over T。Of。AI。Dot X。T minus B。

Plus epsilon T plus law and M or T。Yeah， thanks。And actually。I'm actually going apply this。

 So I'm going apply this with。Some。A different epsilon than the final epsilon I want。

 So the final epsilon I want is this one。 I'm going apply multiplicative weights with。

With some other error， let's call it Ada。Right， I can choose。

I can choose this error parameter however I want as long as it's less than a half。

 we'll see what8 is going to end up being。Okay。And then now。What I'm going to do is multiply by。

So now。呃。Multiply。By gamma over t。And what we get is and set also。And set。X tilde to be1 over t。

Times the sum over little T。Of X T。Right。Notice that by the feasibility condition from the Oracle。

 each one of these is in capital P。So this itself， this average is also in capital P by convexity。

 We assume that capital P convex。So then if you multiply both sides of inequality by gam over T。

 what you get。Is that zero， is that most？嗯。AI。Dot x tilde。Minus B。Plus。Gmma8。Plus。

That was sort of been Ada。Lm。Over。Gamma on M。Over A to T。Okay。

Now what I'm going to do is I'm I can set a to me whatever I want。

So I'm going to set aA to make this at most epsilon over 2。

 and then I'm going to set T to make this at most epsilon over  two。Now set。Eda。To be。I guess。

Epsilon over to gamma。And now set T。To make this at most epsilon over two， which means。Gamma。Lwn M。

Two gammalon M over Aa。Which if you plug in what Eta was， there should be4 gamma squared La M。

Oh and let me put also an epsilon here because I want this to be epsilon over two。

Over epsilon squared。So all I did， you can verify this， you know， a line if you want。

 All I did was I I chose。Eta and T。Such that。Let me call this A， and let me call this B。Such that。A。

And B， we're at most epsilon over2。That's all this was。So now， this implies。

That zero is at most AI dot X Telde。Minus B。My plus epsilon。Which implies that AI。Dot x tilda。

Is at least B minus epsilon？Yeah， so。And this is true for all I。So that's it。

So how do you use multiplative weights to get？An almost feasible solution to the original problem。

You keep running this oracle at every step to give you an X T。 and at the end of the day。

 your almost feasible X is the average。Of all the Xts that you've encountered so far。

So this is your final output。So any questions about？But what I just said。you okay。Yeah。That's right。

Star star has two constraints。 The first constraint is that X should be in P。

 And the second constraint is that little P transpose A X should be greater than equal to little P transpose B。

So what is this inequality？后s。closeness to constrained R I。 Oh yeah。 So you're saying something else。

So if it's feasible， it'll return in X。And furthermore， the estatic returns。Furthermore。

 the Xit returns will satisfy this property。You have that promise that the oracle behaves this way。

Yeah， it doesn't just find any feasible X， it finds a feasible X that satisfies this property。不了。

So you know just going back to set cover， I mentioned this last time。

 but we hadn't actually proved this theorem yet， so I didn't give you the details。

Let just finish that off and then we can start on flow。Okay， so。Let's finish off set cover。

Remember there we had some collection of sets， and we wanted to choose fractionally sets to cover our universe of elements。

 so we wanted to minimize the sum over s of x of S， such that for all elements B。

 the sum over ss containing E of x of S should be at least one。And also x should be non negative。

And RPp。It going to be the set of all x's such that， first of all， x should be non negative。

And second of all， the sum over x of S is。Should be at most L。Or I think did I say alpha last time。

 whatever？Should have most beta。And the point is we know。That if there are M setss。

We know that optt is somewhere between1 and M。So we could just binary search。So remember。

 multiplicative weights， the multiplulative weights theorem for LPs。😡。

It lets us get something that's almost feasible， right， There's no minimization here。

 It's just a feasibility question。So the feasibility question we're going to answer is whether or not it's possible to get cost at most beta。

 And then if you can do that， you could binary search on beta。

So how would we implement so the question？How do we get？An oracle， right， we need an oracle。

To be able to apply this multiplicative weights idea for set cover。Okay， so。We're given some P。

And we want。To check。Or feasibility。Of。P transpose Ax。Is gradient equal to P。P transfer was B。And。

X has to be in the set。Capital P。Because how are we going to do that？Well， first of all。

What's P transpose B？Yeah， P B is one。B is just the right hand side here。

And so P transpose of this is just the sum of all the P Ps。

 which is one P is a probability distribution。So。What。P transpose Ax either integral equal to1。

Now what's P transpose AX？Well， let's just write this out， this is equal to the sum over all E。P。

 E times the sum over Ss containing E of X S。And we can write this as the sum over all s's。Of excess。

Times what I'll call P of S， where this is just。The sum overees。呃。The sum of Es and S。F P。但是。So。

Forget about。You know， forget about the condition that the X U want has to be in。So okay。

 so ignore this condition for a second and just pretend this condition just says that the sum of the x's has to be beta。

How would would you choose x to maximize the sum？Actually， maybe it'll be more inspiring if I say。

 pretend this beta was just one。Right， so x， x is。X is giving specifying some convex combination。

X is specifying some convex combination of these Ps。

RightSo then what would you do to maximize that convex combination？Yeah， you would。

 you would place all the mass on the S that has the biggest P value。Right， so， you know。

 you can assume that。 And And since x is non negative。I mean， if you normalize it to have。

If you normalize it to have normal like to have sum equal to one， then that argument is a real proof。

 Okay， so if you want to maximize。You know， for x。嗯。For X and P。To maximize。The sum of XS， P of S。

Choose。😔，Yes。Such that P of S。Is maximum？And set。Access to be what， What would you say access to be。

Yeah， you said to be beta。You place all the possible mass you could there。Okay， so。

So that's what the Oracle will do。So when the Oracle is given this P。

It's going to write down this expression， it's going to observe which PS is the biggest。

And it's going to set X to be beta。So the Oracle。Picks。X to be。You know。

 beta times the S standard basis vector， let's say。Yeah， so this is the SF standard basis vector。

Okay， and then that'll give you some value， it'll give you beta times P of S。

And if that's less than one， it's just going to say it's infeasible。

 I maximized it and I couldn't get one， so it's infeasible。Otherwise， it'll give you the point。

If P of S。嗯。Is less than1。We output in feasibleas。Otherwise。What can I say about？About the row。

 remember I want to have a row bounded oracle， what can I say about the row that this thing satisfies？

Otherwise， for all。Constraints。Yi。I want to look at。AI dot x minus B， and I want to bound this。

 right？Or， let's。For all constraints， I， maybe the constraints are indexed by elements of the universe。

 What can I say about this quantity， right， I need to understand this to know how many iterations I need in my able to look at a weights algorithm。

Well， this is one。So what can you tell me about this value？So what is x？

X is just beta times the S standard basis vector。So I claim there are two cases。 So。

 let's say for all constraints E， I want to。E is an element of the universe， this is in the universe。

So there are two cases， either E is in S or it's not an S。If E is not an S， what's this dot product。

 given the x that we are outputting。It's zero， good， in which case this difference is one。

What if E is in S？What's the stock product？It's beta。So。This thing is at most the max。Of one。

And beta minus1。Actually， yeah， okay， good。Which。Let's just call this what， you know， beta。

 we're binary searching to get beta anyway， right， And we know the answer。

 we know optt is between 1 and M。 So we're going to be binary searching between 1 and M。

 So beta is certainly at least one。 So let's just say this is that most beta。Which is at most M。

 for example。The number of sets in our input。So this tells us if we combine this with our theorem。

 which I think we erased well。嗯。That's the gamma here， right， So the number of iterations we need。

Of the multiplicative weights algorithm is going to be something like M squared log M over Epsilon squared。

So。This implies， O of。M squared log M。Over uppsilon squared。Iterations。Of multiple weights。To。

 to get。A good solution to。Fraactal set cover。 And remember， we said that for a fractional set cover。

If you're violating the constraints by epsilon， you can rescale and get an actual feasible point。

But your cost will increase by a factor of roughly one plus epsilon。

 So you can get a one plus epsilon approximate solution to multiplicative of weight to fractional set cover by just doing this number of iterations in multiplic weight。

Okay。So。That's all I want to say about multiplicative weights besides PSet problems。

But do you have any questions before I change topics？对。Sorry can。You said thatでよ。呃。

I don't like in the proof of the theorem I did。 So before we went moved to set cover and the proof of that general theorem。

 I don't think I ever used。That the entries of A were not negative。I mean。

 sometimes that can help you to implement oracles， right， So at the end of the day。

 you have this general theorem， but to actually make it work for your problem。

 You have to be able to come up with a P， and you have to be able to implement an oracle with a good row。

 right， so。Just because you have the theorem doesn't mean you can always use it effectively。But yeah。

 I guess answer to answer your question， I did mention last time that of this idea was developed。

in a paper by P Kinshmoise and tardo， And they were considering packing and covering LPs。

But if you look in the aurora Haan Kaa。M monograph on。On multipl of weights， yeah， I mean。

ThereThere's no requirement for that theorem that。It'd be a packing or covering LP。Okay。So。New topic。

So， flows。ok。So。So since CS124 is a prereq， I will assume I'm not going it。

You will be able to follow。What I'm going to say without knowing the details。

 but there are certain details I'm not going to prove。I'm just going to assert their true。

And if you know the proof great， if you don't， you can go read about the proof。 Okay， so， so flows。

 So we're given。A directed graph。G equals V E。And。We're also given。Capacities。

And the capacities are all non negative。Okay and。We're also given。A stark vertex。S and N vertex。Qi。G。

Is to output。A flow vector。A flow， I'm going to define what this means， a flow from S to T。呃。

A feasible flow。From S to T。Obeying the capacity constraints。

so let me start defining some of these terms and also drawing pictures。Okay， so definition。A flow。嗯。

It's。So for me， always M。N is the size of V and M is the size of E。

And I'm always just going to assume that the graph is connected。嗯。If not。

 then you can do a DFS in the beginning and。Only work with the connected component that contains both S& T。

So in particular， since the graph is connected， M is at least n -1。

 So I'm always going think of M as being at least n。Whenever I write bounds。Okay， so a flow。

Is a vector。I was say an ST flow。So， one。嗯。F should be non negative。2。

For all V that are neither S nor T。The sum over edges。UV。And E。

Of the flow of E should equal the sum of all the edges。Vu。So this is， I'll say this is。Flow in。

Equals flow out。So it's also called Conserv of flow。Okay。We also want。 So S and T are special。

We want that。So I'll draw a picture soon。 But imagine that。We're trying to ship。Water from S to T。

 Okay， so water is flowing out of S， and then it's landing in T。

So what we want is to say that the amount of water that leaves us is equal to the amount that enters T。

Okay， so that means that the sum overall edges E being S U of F E is equal to the sum overall edges E equals U T。

In， in the Edset E。Of。Okay， so。Flow。Out of S。Equals flow。Into T。Okay， and。We say。F is feasible。If。

For all edges， E and E， F E is at most the capacity of that edge。Okay， and the value， let me write。

The value。Of F。Which we' write v of F。Is equal to the amount of water we ship。So you can imagine。

 for example。We have a graph。So here's an example。This is S， this is T。These are two other vertices。

And let's say all the edges。Sa there's s is like this。They're all directed in this way。

And let me also write down the capacities of these edges。1anwa。One。

 let's say they all have unit capacities here。So。One flow is one feasible flow is the zero flow。

 I won't ship any water。Another flow， for example is。I'll ship one unit of water here。This way。

And then I'll go down here。And then it'll go this way。And I's say I have ship one like that。

That gets me1 unit of flow。Another thing I could do。I I could just。呃。YouGo this way。

 send one that way。And send one that way， is that purple visible， I feel like it's very dark。

RightSo this purple flow has a value of two， whereas the yellow flow has a value of one。

 So if we're trying to maximize the flow， the purple flow would be better。Okay。So。And。Also。

 I should change this goal。 we want F。Has maximum value。So we want to find a max flow。Now。

Pretend you've never heard a flow before。Okay。Given all the things we've been studying so far。

How would you think to？Find a maxflow。Linear programming right。

 so this is exactly a linear programming problem。So LP formulation。We want to maximize。

The sum of all flow leaving S。We have certain constraints， F has to be at least 0。For all E。

 FE has to be at most CE。And then we also have the conservation constraints， right。

 constraints 3 and 2。 but those are all。Those are all linear constraints anyway。Right， so。Plus。

 constraints。For two and three， I guess。Yeah。3。Oh， yeah， yeah， yeah， yeah。 That's yeah right。

That's right。That no flow is entering S。OhI see。You actually need some problem。Oh， I see， okay。As行。

I see， okay， yeah。Okay。So。So we could solve。Uing。Simpplex。Or ellipsoid。Or， you know， interior point。

So， let simplex we know we don't know any polynomial time implementations of simplex。

 we don't know any pivot rules that are guaranteed to run in polynomial time。Ellipsoid。嗯。

Lop soide will run in polynomial time。 It will also depend on。

 So I didn't I don't I don't think I gave the。I didn't write explicitly what you get at the end of the day。

 but remember that you start with some ellipsoid containing it and then you keep shrinking it。

 shrinking the volume of this ellipsoid over various iterations。

The number of innovations you need will depend on precision issues。 I think I did say that in class。

 So it will depend on like the the log of the biggest capacity you have。

So you'll have like poly N times。Some polylo in the largest capacity。Let's look at interior point。

Because I think that's one that we actually some fast algorithm that we actually did go through in class。

So。The number of iterations。I's like Ru M。Up to this log factor。

Let''s let's let L the precision absorbed log factor。 So root M L。Iterations。In each iteration。

O one Newton steps。So what is a Newton step？I mean， do people remember in general Inter point。

 So remember in general Inter point， we want to minimize。F of x。And。We said that the change， x1。

Is going to be。X0 minus some quantity。This is。The current。Ittererate。

This is should think of these as flows。Right， so。I， that's just color Xes。Okay， so next iterate。

Right。Do youll remember you have to， what the step is in Newton's method？

So what overalll is from gradient descent。Yeah， so you take the Hessian inverse。

Applied to the gradient。That's the names method。So。Remember in linear programming。

We said that in linear programming。This Hessian inverse。Was equal to something like， I believe。

 a transpose slack x minus 2a。So。I mean， you can also think of this as like。嗯。Hasian。

The hessian applied to x1 minus x0 should equal some particular vector。

In step in each iteration of Newton's method， when you apply to linear programming。

 you're solving a linear system。Okay。Iterations of Newton's method。For LPs。In point method。2。

Our linear system solves。Check。So。That implies。Total time。Well， rootta iterations。

 each one is a linear system solve。 that's like M cubed time or m to the omega using fast matrix multiplication times L。

So let's call that O of M to the seven halves。L， and this L， you can show for flow problems。 It's。

 it's possible to。for such flow problems， always make this thing polylo。Of the maximum capacity U。

This is the maximum。Capacity。One thing I will say is。Kind of the dominant term here。

 if you notice is these linear system solves。This is for an arbitrary LP。😡。

It turns out that if you write。😡，The linear system solves you have to do for the particular case of the flow problem。

The linear systems you get are a special subclass of linear systems。

 They're not arbitrary linear systems that you have to solve。

And that was exploited in a paper in 2008。By Dicchin Spielman。In stock 2008。Showed。O tilde M。

 O tilde is hiding polylo factors， polylo M factors， O til of M。Any your？Time。When a。Comes。From。

A flow problem。So it's not an arbitrary a。 It's not coming from this。

 Basically it's related to if you've ever heard of Laloian system solvers， so I'm not gonna。

 if you've heard of that great if you haven't， you can go look at their paper。But， yeah。This M cubed。

So， this。This M cubed basically turns into。Turns into that。

Which at the end of the day means they get an m to the three/ halves algorithm times log capacity or poly they get log squared capacity。

 M to the3/ halves times log squared capacity for linear programming， Maxflow。Actually。

 they look at more than just MaxL。 They look at other flow problems as well。Okay， so that's great。

But even without that， even without that。Without dice Spman， you can apply IPms。

 You would just get a terrible。Ponomial， you get。E to the 3。5。Okay， so。Without。Oh， and actually。

 I should mention。嗯。When， when we were covering interior point。

 I mentioned that this barrier function that we were using， it weighted all constraints the same。

 right， We had a sum of。A sum of log of the slack of the I constraint。

And I mentioned that this was kind of weird because if you repeat a constraint multiple times。

 you're counting it more， but really that constraint only matters once。

 and I mentioned that there's this paper by Leean Sidford。

 which figures out weights to apply to that to make it run faster。

And they showed that using their methods for interior point。You can actually。

Turn this root M into a root end。ForFor maxflow。So you get an M root N algorithm as opposed to M root M。

 right， and M could be as big as n squared。But so without， you know。

 let's think purely combinatorially and not use any of this linear programming technology。So。

 without。LP technology。嗯。So Ford and Fulererson。Oh， actually。Yeah， so Ford and Fererson。

I don't remember exactly， I think it's the 50s I figured out exactly which when and where。

Gave an algorithm with time。O of M times。F star， Okay， so I'm gonna abuse notation。If， I mean。

 a flow is a vector。 It's not a number。 If I just write it without the value， I just mean the value。

 So the value of， So F star is the max flow。 It's the flow that achieves a maximum value。

 And this is the value of that flow F star So the running time。Was M times F star。

 which is not great。Right， so for example， imagine。Well。

 their algorithm would actually do great on this graph， but imagine I have。You know。S T。

According to this bound， their algorithm could take time a billion。

 even though the graph has two vertices。It wouldn't take， I'm not going to describe their algorithm。

 It wouldn't take a billion steps on this graph， but， for example。

 if you just modified this graph slightly。And then put one capacity here。Their algorithm could take。

A billion steps if you're not careful。Very good， but you know if your capacities are all one。

 then that's not terrible。And actually， I probably will end up saying what your algorithm is just because I wanted to define find certain terms。

So what does their algorithm do？So this forwardd focused an algorithm。Finds。Augmenting paths。Okay。

 so what's the idea there。So。So we're given G。And。We。Find。Some flow， some feasible flow。Okay。

 so what's。What's a simple way to find， if there is one。

 what's a simple way to find a feasible flow that has strictly positive value。

I guess many people have seen flow。 So maybe people are shy to just。

Say things that are that everyone knows。 but you can just DFS。Okay。So。So， easy G。DFS。From S to T。

Now you've got a path in the graph from S T。Right， and that path has some minimum， when I say。

 DFS only consider the edges that have positive capacity。Do a DFS on that graph。Aeppt for research。

Now you'll find。Some path from S T， that path has a minimum capacity on it。

So just put that minimum capacity on the flow。Right， so。To find some path。Who is， let's say。

 min capacity edge？Is you know， some lambmbda。No。Define F。To be lambda。On that path。And zero。

Otherwise， so like for example。啊 sorry。Yeah， so I guess all I want to say is。So we have some graph。

This is S。 This is T。Okay。There are some capacities。Now I'm just making up numbers。

There are some capacities on these edges。And I just want a DFS from SDT to find some path。

 So maybe I find the path that goes here， and here， then here。So this path has three edges。

The seven capacity， the five and the two。I'd like to push flow along this path。But you know。

 how much flow can I push on this path？Before I become infeasible， well， I can push to。

 basically the minimum， right， So lambda。Here is two， that's what I meant。Right。我。So。So now we def。

 So okay， So now let's say we find some flow in G。We can so given。Flow F。In G。Yeah。Yeah， so I will。

 I'll assume that capacities are always。 So there there are some rational numbers that I'm sting on my computer。

 I clear denominators。And I'll just assume that there integers is between one and U。あJustと。Yeah。

In Ford Fkerson。So given a flow FNG。We define， we can define。A what are called residual graph。呃，GFF。

On the same。Edgeet。Where。Let's say。The capacity， let's say， capacity prime， this is。The capacities。

In Gf。The new capacity of an E E。Let's say capacity of the edge UV， where say。

We have an edge E is UVv。Is going to be。The old capacity。Minus the flow along that edge。嗯。Plus。

 the flow in the opposite direction。So。嗯。Yeah， so our flow vector。

Let's just imagine that every edge that is in the graph， the reverse is also there。

 So if the reverse was also there， then it was already there， great。

 If it wasn't put it there with zero capacity。系啊。So yeah。

 imagine that we have edges in both directions for for every edge。

And you can imagine if you want even that。呃。It's the complete graph where edges that don't actually appear have capacity zero。

But I don't want to say it like that because I want my I want our running time bounds to depend on Ed。

But yeah， so for every edge that appears， imagine it appears in both directions。

 Maybe one of the directions has capacity 0。Does that make sense？And。So what Ford Fulkerson does。

Yeah。So yeah， I'm defining， I'm defining a new capacity function in terms of my flo。

And this is how I define it。都这个。Or is it。Any more questions？And by the way。

 this flow vector F is remember， it's not negative。

 So I am not imagining that F U V is minus F of V U。

Like it might be the case that F of U V is5 and then F of V is0。In fact。

 you can always assume that one of them is zero。Right。So for example。

 if this were five and this were one。That's the same thing as just saying that this were four and that were zero。

Question。In the sense that it would still satisfy， right。

 if I if any edge and its reverse both had positive flow on them。

I could just make one of them zero and subtract from the other， and it would still satisfy all these。

Constraints。And it would give you the same exact。Yeah， yeah。No why not？Oh， wait， wait， wait。

 let me just be more careful about what I'm。That's what I say again。Yeah。

If the reverse has positive flow， oh， I mean。No， I want。

So my definition of a flow is that it's a non negative vector。Yeah， what you're saying makes sense。

But I wanna， I wanna stick to a particular definition of flow and my definition of flow。It's so yeah。

 you could， so for example。You know imagine you have your pipe with water going in it and the water is going in that direction。

And it's it's going at a rate of， I don't know，5 liters per second， whatever your unit of flow is。

 So let's say it's 5 liters per second。That's the same thing as saying there's actually 12 going this way and there's seven going backwards。

But I mean， both of these are equivalent。 I will always just assume one of them zero or it's the same as saying that5 are going this way and zero is going that way。

Yeah。I hope I didn't create any confusion。 I just want， I'm just trying to state my。诶。

What do you call that。My standards， my not notation， but in my notation， there's always going to be。

Amongst an edge in its reverse， only one of them is going have。

at most one of them can have a nonze flow on it。And。Also， edges appear both forward and reverse。

 one of them might have zero capacity。Yeah， in the beginning anyway。Oh， yeah're good。

That just for the。Just assume it's not going to really， yeah。

 let's say everything I said is always the case。This is most going to double the number of edges in the graph。

RightAnd all our balances are bigger of them something anyway。 So it changes things by a constant。嗯。

Okay， so Aro， everything。So。So for focusing， what it does is is initialize。嗯。F to be 0。And。

GF is just G。Right。By that definition。While there exists， and then there's a loop while there exists。

A path。An augmenting path。In Gf。We're going to let。F prime。Be some flow。In Gf。

And we're going to set our new F。To be our old F。Plus F prime。And then we're going to set Gf。呃。诶。

All me right， G。呃。To adjust。TheGf。这是女儿。So this is For Fulkerson。And。So。It relies on a theorem。

Correctness。Relies on a theorem。Which is as follows。So F star。Is a max flow？If and only if。AGf star。

Has no。Augmenting path。Another meaning that there is S and T are disconnected。

 There's no path from S to T and G。So I'm not going to prove this。 know， it was proven in 124。

 you can find it in any algorithms textbook。Introalm， textbook。But。That's。This is kind of。

 I state this theorem because we're going to use it for other fancy algorithms too。嗯。Oh。Okay。

 and I am， it's exactly 4 o'clock。 So next time， next time we're gonna。Use this theorem。

To show that there are some faster。Paster flow algorithms， than。Then For focus。

