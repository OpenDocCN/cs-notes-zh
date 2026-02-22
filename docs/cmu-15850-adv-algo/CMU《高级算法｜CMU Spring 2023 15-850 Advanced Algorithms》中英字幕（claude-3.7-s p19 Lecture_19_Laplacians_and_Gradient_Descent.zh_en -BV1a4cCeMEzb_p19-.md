# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p19 Lecture_19_Laplacians_and_Gradient_Descent.zh_en -BV1a4cCeMEzb_p19-

嗯。Good， so。Welcome back and。15850， the course number is still the same and today we'll talk a little bit about so first maybe we'll talk a little bit about Laplaces。

So at least I want to introduce this notion and correctly introduce the last time I kind of messed it up and then maybe we'll talk a little bit about gradient Biang。

And I know that people might have seen some or both of these things。

 so hopefully you can help me when I start goofing off。ok。Good， so so for the setting of Laplaceians。

 this is。😊，The Laplaceian matrix of a graph。And in general， this。

 apparently you can define Laplaceian operators on manifold and stuff like this。

 but we are working with the matrices， we are working with graphs。

And so here's what the La Plaian matrix is。Here's the easy way of getting it。

 this graph had an adjacency matrix， a， so this is the adjacency matrix。Offf the graph。嗯。

You can define a matrix。Let me call it D。which is the diagonal matrix where the the diagonal entries are d1。

 the degree of the first vertex d2 up to dn， these are the degrees， these are the vertex degrees。

And now the Laplin。Is d minus。哎。So， for instance， in this graph on six verticcs， it will be。😊。

some6 by6 matrix and let me just write down let's say that the vertic see that numbered you know this is the first vertex second。

 third， fourth， fifth and sixth vertex， so s the first vertex has edges。Going to vertices two and5。

So， maybe it has a。It'll have a negative one。Corresponding to the second vertex out here and to the fifth vertex。

 it' will have a negative one， it'll have zeros corresponding to the other vertices。

And on the diagonal is going to be the degree of this lowtex which is two。Okay。😊。

And this the same thing for verortex to， it has。It has an edge going to vertex 1。

 so it's a symmetric matrix as you see this is symmetric， this is symmetric so there。😊。

And I'm talking about。G is an undirected graph， let's say。And now the degree of two is。Three。

 and it has an edge going to six， it has an edge going to three， and it has no other edges。个人。

This is the Laplaceian matrix of a graph。😊，Now， in general， you could have weighted graphs。

In which case the adjacency matrix will be await weighted adjacency matrix， so for instance。

 if this add if。Okay， yeah， let me just do it very quickly if this edge had weighted let's say seven and this edge had weighted three。

😊，Then I would put a negative7 out here。A negative  three out here。

 and I would put the weighted degree of the guy， which is going to be 10。

This would be in the weighted setting。The love bs。Fact。😡，嗯。The link。

Of the Laplaceian is at most same minus。喂hy。Look at every road， it sums to zero。诶。So in particular。

 you know， the proof of this just says l times the all one factor is equal to 0。Okay。😊。

The rank of the lapplin in that most n0 minus1 is another fact this requires a little bit of work。😊。

Rannk。Of L。Is equal to the n minus the number of connected components。Offf the graph chain。

Is equal to。There's two directions you can show that the rank of L is at most the number of connected n minus the number of connected components。

😊，So it's ranked deficient by exactly the number of connected components of the graph。😊，But in fact。

 the rank yeah， is equal to that。Yeah。And so this， this immediately implies that。Okay。

We will come to what it can play in just。Here' is another way of getting this leplaceine I mean this this is。

😊，啊。对。So the lappline comes up a lot and in fact if you pick up a book on spectral graph theory basically theres this sort of thing that we always say look we usually view the graph as being represented as an adjacency list but if you view it as an adjacency matrix then it's a matrix and this matrix as nice matrix theoretic properties in particular it has eigenvalue eigenvectors and stuff like that and you can start reasoning about them。

😊，And the lapplian is just a transformation of the adjacency matrix in a form that's particularly nice。

And you'll see let me show you a few things I'm just I'm not even touching the tip of the iceberg。

 it's just like beautiful vast area。Okay。So let me write down。😊，The Laplian。Of a single。Edge。

 you know， this is a graph and maybe I'll do it out here。

 This is a graph with a single edge on it between the verticess i edge。😊，What is its lapplaceian。

 it's lapplaceian， it still is an N vertex class。Remember。

 what's going to happen is the degree of I is going to be one。

So in the IIS location there's going to be a 1， the degree of J is going to be 1 and there's going to be negative ones out here and zeros everywhere。

This I can write as。The outer product。Of this matrix or of this vector。

 which is going to be one here and negative one here。Withage。This is really EI minus EJ。

Times Ei minus Ej transpose wherever where all the vectors are really column vectors。Okay。😊。

And this I did not as a。The lapplaceian of a single edge Ij。This is an undirected edge。😊，You know。

 I could have flipped J and I， it didn't really matter， you would get the same answer。

So this is a single Laplium。The lapplian of a graph。I equal to the sum over all its edges。

Of the single processians。Okay， just a fact。Now， the single laser Laplian， by the way。😊，Is it nice。

It's the outer product of a vector with itself。嗯。So let's look at a single ofpl。嗯。嗯嗯。

I really want to go back there， but I seem to be moving okay。So remember。I want to take an。

I'm going to take the matrix x transpose L J x。This is a vector I'm just writing x transpose Ax。😊。

I want to understand， you know the sort of kind of the eigenvalues of。This matrix I like。

So let's write down x transpose Laplaceian x， this is equal to x transpose。E I minus Ej。Thanks。

 E I minus Ej bronze equal times x。This and this are the same object。There's just， you know。

 one is a transpose， B， one is B transpose a。So this is really。X transpose E I minus Ej。Squad。

Right this is just I can write it as。😊，X the I minus e here。Squared this I'm rewriting it。

It's a square quantity。It's not negative。So what does this tell you about the lapplian。

 the leplin with save x transpose Lx for any graft？Theres not negative。

All its eigenvalues are non negative。废啦。WellPlus and let's write down the fact fact。嗯。on。Eigenvalues。

哦，爱了。A great， I can。Moreover， it actually has a non trivial current。So in fact， we just claimed。

So if I write down its smallest tagig in value， lambda 1， this is equal to0。

And then this will be equal to lambda 2 will be equal to lambda number of components。

Number of connected components in the graph。And then it will be strictly bigger than lambda of。

 let's say， k plus one。Which could be two。If the graph were connected， then lambda 1 would be 0。

 lambda 2 would be non0。Because I'm claiming this fact。

 I haven't proved the hard direction of this fact。😊，对。So。Basically， this fact is same。

That lambda two of the graph。Is greater than zero if and only if the graph is connected。Is connected。

Lambda one of the graph is always0。😊，Lambda 2， the second eigenvalue。If it's non0。

 the graph is connected。即。So this is this is saying， look。

 you can figure out the connectivity of the graph by looking at the second eigenvalue。😊。

Of the Lo plastic。This is like an interesting fact。But actually it gets more and more interesting。

So hass a has。呃，犯。Basically。Actually， I shouldn't even say fact this is。General， you know。

General principle。Wig。The gap， this is often called the spectral gap。Is lambda 2 minus lambda 1。

 which is actually just equal to lambda 2。Tells， you know， tells。要。How well connected。The graph is。哎。

And maybe we'll get to this later on。But essentially here is here is a， for example。😊，If。

 let's say lambmbda2。Well。At least some。Universal constant。Then the graph is called an expanded。该良。

Spectral explain that。we can maybe we'll get to this in future homeworks or lectures things like this it's basically a graph where where every sec so this is my graph and if I look at a set of vertics。

😊，And the set of verte C is not too large。😊，Then this has a lot of ages coming。Every set。

 which is not too large， at least you know at most half the vertices of the graph or something like that has a lot of edges coming。

😊，But I digress。Let's get back to。Facts that we can say about just just。得啦不。Okay。

So what's the lapplian we just said the lapplian is equal to the sum over edges Ij。Of EI minus Ej。

Times Ei minus eger transpose。Okay。😊，This is just， I've rewritten the Laplian in this。Now。

 let me define another matrix that you might have seen before。This is the。Edge， verortex。

Incidentence matrix。And what's this matrix this matrix has。呃。N rows one for each vertex。M columns。

 one for each edge。And each edge E out here， and let's say edge E。Has。Connects ING。

Then it's going to have a one。In the IAT position。And。A negative one in the jail position。

And mentally， we are just orienting this edge one way or the other。

 it doesn't matter which way we oriented。😡，Not important。For our purpose。

We are just in our mind saying， look， I want to keep track of whether the flow will be going。

From five to six or six to five。In order to be able to say that I'm going to say this is a forward direction for the ice edge the flow can go in the reverse direction。

 that's fine。😊，In which case it will be a negative flu。

So the sign of the flow will tell me whether the flow is going this way positive or this way negative。

😊，just for bookkeek。Now， notice that this column is exactly Ei minus ept。😊，我先。😊。

So the columns of this matrix are exactly these vectors。😊，Okay。😊，Now， here is a little。Fact。

But for the longest time I didn't really know this， you know。

 I didn't realize this fact and I've been studying in algebraible for quite some time。

When we take sort of matrix products。Use this as。As my scratch work。When we take matrix products。

 we multiply a times B， right？And then we。What do I do。

 I take the first row of this thing multiplied by the first column。

 this gives me the first entry of the answer， etc。Right instead。What I could start doing。

If I could take the first column of this thing and the first row of this thing。

And take the outer product。And that will give me a matrix of this size。

And then I can take the second column in the second row and take their outer product and they'll give me another matrix of this size。

And then I'll take the last column in the last row and it'll give me another matrix of these size and I'll just sum them all up。

😊，And my claim is that a times B。If equal to the sum over columns。

 let me write it J going from1 to n。哦。Prom aI。但 role。

So Aj sorry call times rh and I'm using little bes to denote rows and capital As to denote columns。

This is A1， this is B1。A22 in of AJ times Bj transpose。再见。Why didn't they teach us this earlier。

 maybe they did， I was just snoing in class。O。So a times B can be written in this way。😊。

But this is exactly this kind of thing that I want。So this implies。

That I'm going to erase this sucker。This is the edge vertex incidence matrix this belongs to。😊。

Let me just write it R N cross M。Back。L is equal to B B times。

I'm just taking a column of this guy and it transpose is giving you the first row。嗯，对。

You know just restating things that you've already seen。Now， this is for the unweighted second。

If I had weights on the edges。Then I need to introduce weights out here。

And how would I do it so let W be the diagonal。Of the weight on H E1 up to the weight on H E。

And then the weighted Laplaceium will be Bw B。This is just shoving the weights onto the。嗯。

And this is really just some overall Ij edges of the graph， Wyj times Ei minus Ej。😊，VI minus1。

Thatcellent。Its just pushing it。对。Now， you know the Laplace， whatever？Now you've made the Laplia。

Okay so far so good。This。Two more little things that let me show you and then we'll go on from there。

不。好。Yes。I you put a one somewhere and a negative one somewhere else， it's important to always have。

it's okay so for instance， I could， you know， because I put a one in negative one。

The edge is kind of going maybe that direction， this could have an edge going also in that direction。

 but this edge could be going outside that just squares and you know as long as you have EI minus ej and EI minus ej in the second one are you know。

 they have to be consistent。😊，but that's because it's BB transport， so once you fix B， the other Bs。

 it's the same B。S far a learn。And really， you know。

 once you see this thing that L can be written as Bb transpose。

 you immediately say x transpose Lx is x transpose B times b transpose x。😊。

Which is really a square of x transpose B。The square length of x transpose P， so it's not negative。😊。

So this guy is positive feitive。And fact， it's。It's rank deficient， we already know that。

And it's rank deficient by the light amount。Et cetera。All these things are really you know。

 okay let me let me give you a peek of one thing which I won't prove I had full intention of proving it but you know I can't take the whole lecture I can't take the whole lecture but the proof is yeah。

😊，He the fact way。Yeah。This is an easy fact， the determinant of L is。😊，Z， thank you。等下。But。

Do the following。Take care。Remove the first row and the first column。听。Let me call it。L。1。哎。Now。

 by the way。If the graph had。Two components。And this this determinant would also be0。

Because you know the rank would have dropped by at most one or whatever may not have dropped。

 et ceter。But so let's consider a connected graph。This determinant。It's equal。Anybody know this。

 anybody think it are drag？は。Exand。不。是。You can expand exactly and in fact the thing that I'm going to give you is true for all allies。

 it's going to be the same value for all allies。😊，And it's going to be the number。Of spanning trees。

这是。是。This is one proof of Kayle'sterem。Though you know。

 even that is not the yeah it is one proof of calist if you do it for the lapplaceian for the complete graph and you figure out what this quantity is。

 what this determinant is it will come out to be end to the n minus2。😊。

I was hoping that it was a three line calculation， it's a three line calculation。

 but it's yeah well see。😊，But this is this is， this is a tatum， this is known as。

Let me just write it down This is known as the。继做。I never know whether it's Kchsh or Krkkov。

 but any green。Gourch of matrix street。You want to compute the number of spanning trees of a graph。

 you can compute in polynomial type you want to compute the number of perfect matchings of the graph it's sharp P hard if you can solve that problem exactly you can solve NP。

All problems in NP and more。So Sharp means it can。If you can count the number of perfect matchings of a bipartite graph。

In whatever time。You can also count the number of satisfying assignments of a three side formula in the same amount time with counting prompts。

But。Number of spanning trees of the graph， yes， you can go。

And a homework problem that's coming soon to your thing or maybe an exercise。

 this allows you to sample from the set of spanning trees of the graph exactly。I'm so yeah。

So you if you want to pick a random spanning tri of a graph， you can do that in polynomial time。嗯。

Anyways， this one requires a little bit of a proof I'm not going to do this today。不 sorry。不是。对。

So so in this case， L is L is just a， you know， it's a matrix like this。😊，Yeah。Yeah。

 you're thinking of the other the short Zple type thing。😊，Yeah。This one's just a fixed matrix。

 drop the first row first column or the I row at column。😊，So you can take。

 you can drop whichever when you want， it's the same thing yeah。In this case。

 take the unweighted leplusian if you want the weighted leplusian actually that also means something。

😊，In that case， you'll sum overall spanning trees of the graph。Of the weight of the spanning tree。

 where the weight of the spanning tree， the product of the weights of itself edges。

So this is going to be product of EP。Offf the world。Yeah。And I feeling。Okay。So far so good。

Let me go on a little more， just a little more about lapplaceins and then we'll come back to。So。

We saw the laplace of a graph， we saw weighted laplace。😊，Let's go back to electrical networks。

 we talked a little bit about electrical networks but it was very fast and I hurried through it and bad idea always。

😊，So let's go over it。😊，Okay， so we remember Om'sl。What does Oms law say。

 Om's law says that if you look at an edge。And there is some resistance on this thing。

Let me call that RIJ。And there is some potential difference so maybe I'm looking at the edge directed from I to j even though the resist doesn't have a direction right it's a resistor its a unit resist it's a resistor or value Rj and if I send flow5 I5j。

😊，Then how much flow flows on this thing it the amount of flow is equal to let's say Phi。嗯。

J minus phi I divided by R， these are the voltages。I'm writing potentials， potential voltages。

 same thing。So I want to say the amount of flow in this direction。😡。

Is the difference in potentials divided by the resistance？There on。Suppose。You know。There you know。

 you guys know right the inverse of the resistance is the conductance。😊。

So can I can call the conductance instead of talking about resistances。

 I can talk about conductances and I'll call the conductance WI。😊，So嗯。嗯。W E is equal to one over the。

So this is just。W。Thanks， WA。Okay。咩来了。对。And this is equal to。LIG。This is a lapplaceian， remember。哦。

 no no no那那再来一点。E Ej minus EI。Ds。对啊。Fing。Mis rewriting。So here's the point I want to make。

Suppose you gave me potential fee at the various ver fee。😊，You said， oh。

 the voltage at this guy is 7， the voltage of this guy is negative 3 and sponsor。😊。

I want to understand what current flows on each of the edges。The current is going to be。W times B。

Times W times， okay， let me just make sure I'm the transpose。

My claim is if these are the various potentials on the edges。On the vertices。

Then the amount of current flow in each of the edges is given by exactly this。

You just apply this to each agent entry。😡，So this is a map。You know， this is equal to。嚟个 flow。

On the edges。B transpose is mapping a vertex vector。Two edges there。The first good。对。There's another。

Ln owners。Gir jobss。Love， you know， whatever， one of culture's laws。

 I never remember which of culture's laws。And it just， you know， it's， it's kind of。Really saying。

On every vertex。The amount of current that comes in。So it's really saying， look。

There's conservation of current at every node。What comes in must go out。So suppose I had。

 suppose I told you that here is the network and I am pulling out。One unit。Of current one amp。

 I guess， of current。A P and pushing in one unit of currente S。

Then what should happen is that at this vertex。The remaining current， you know。

 if one unit of current is going in， then one unit of current must be flowing out from s into the rest of the graph。

And then here one unit of current must be coming into T from the rest of the。

So let's look at a particular vertex v out here。And maybe I'll call it I。

I want to understand how much is the net current coming into eye？It should be0， right。

 but let's sum over all the edges。Okay。😊，So I want to say at I， which is not equal to S or T。

The sum of current。音グ。I， we be important。But I know what the sum of currents into eye are。

The sum of currents into2 I is equal to the sum of flows FJI。Or J， which are neighbors of I。ま是ピす。

But I've just computed these things。What are these guys？This is equal to W。WZI。Times。Be off。J minus0。

唉。微过啲知诶。对。So what is this telling me？有意思。The病都是。That啥也。W。B。Drawn sps。嗯。

But this is a vector which is indexed by edges。对。So maybe let me actually stop at this line。😡，对。

F is a vector， which is indexed by edges。I want to look at verortex i and look at all the edges that are incident to it。

😊，My claim is that is given by。B， S and I。B。Was a matrix that looked like this。What would be？What。

B had。A verortex out here。And edges out here。And this guy had once and negative ones I'm being a little lose out here。

 but you know you have to be a little careful， but you had once in negative ones at all the edges which included I。

😊，即。😊，So if you multiply。An F。Its Bf is going to pick up the coordinates。😡。

The entries of F corresponding to exactly these edges。你 you gonna三 them嘛？

And you're going to set it to there。Kind sorter。Modulular some sort of fixing the signs。

So I want to say B F at I is equal to。The external current。Po。印度。

If I'm pushing one unit of flow into S， taking out one unit of flow from t and0 everywhere else。

Then Bf at each of the locations should be zeros one and negative one。This is taking a flow vector。😊。

If I just take this downhill， basically I'm saying B。Times w times b transpose。

 I'm just taking this flow， which is coming from there。I feet。Is equal。This。

 the IS coordinate is equal to one。If I is equal to S， negative one is。

I equald B and better otherwise。I'm pushing one unit of flow into a as taking out one unit of flow from t0 is everywhere else。

😊，But Bwb transpose is equal to phi so this I'm just saying l times phi is equal to whatever this vector is。

E minus。If you solve for this， these are exactly the potentials。These are exactly the voltages。

That will cause one unit of current to flow from S2。No it's just good。是。Perfect。Perfect。wifi。

So what No is pointing out is that look。😊，L times phi the potentials。If equal to this thing。

 I'm trying to solve a linear system。The solution will not be unique because， you know。

 instead of the voltage it voltage differences that matter。😊，You know。

 the voltage you know zero and five is the same as five and 10。

 the same as  seven and 12 or something like that。😊，So L is ranked deficient。

 it has a non trivial kernel so you can add anything in the kernel basically you can。😊。

What is in the kernel or we already know what's in the kernel， right？😊，This is。

Let's imagine the graph is connected。😊，This is just saying the all once vector can be added。

 any multiple of the all once vector can be added and nothing changes。😊。

Which is just the same as saying if you just raise the potential of everybody by 53。

 nothing's going to change。😊，Good。So things make sense。So you can find the solution， modular。

 this triviality， this degeneracy。Yeah。And really， here my colleague Gary Miller。

 who retired last year， he had this amazing intuition about spectralgraph。😊，And he would say， oh。

 you know the way you should think of this is usual should you are just setting the potential at S and T and let everybody else float he had sort of a nice language as well right and I always think of this thing you just fixing the potential at S and T。

😊，You're saying， well， Emma， you're fixing that you want to push flow from S to T and you let everybody float。

😡，And what will they apply to， they will give you this solution。

And that's the solution you're looking。So this is why solving this is like finding the electrical。😊。

Assuming that you're working with classical everything and Ohm's lawss and Toto laws as that jazz。

If you let everything flow， like you have n-2。So there's only one more thing that you need to worry about is how much current is going。

So you need to make sure that the potential difference between S and T is enough that not only should everything else float。

 but the amount of current going from S to T should be one unit。😊，No， because， you know。

It's like n minus1， I feel。And like two degrees freedom and just everyone vote。So okay。

 so so let's imagine that fixed E0。😊，So I also need to figure out how much toective to be。

Because if I set T to be twice as high， the amount of current going will be twice as much。

But I want one unit on， that's what this is saying。So I have only n minus1 degrees。

So this is exactly what you should solve in order to find electrical loss。How you solve this。

 that's you know， a lecture you can catch， I think Richard's teaching a course next semester on all these sort fast methods for these graph thetic problems。

😊，This is solving a linear system now you might yeah this is solving a linear system where the the constrained matrix or whatever a matrix is a lapplian。

😊，So he'll use the structure of a lappline to solve these things first。Normally。

 you would require Gaussian elimination。That would take n to the omega time。

You want to do faster than that。So Richard will show you how to do faster well you know the rate at which we are going。

 I keep thinking oh I'll do it in one of the optional lectures at the end。

 but you know how things are I get distracted。😊，啊。But you guys good so far。嗯。

Theplace are anyway questions。So by the way， I haven't heard too many requests from people I you know post on Piazza。

 I heard one request for a lecture on Martiningale， I'm happy to give a lecture on Martiningales。

One lecture I wanted to give。Is on these objects called high dimensional expanders。So， you know。

 when people come and give talks at least you know what high dimensional standards are。

 these are really powerful objects that are really taken off and that will give me a chance to also talk about expanders in general。

😊，So maybe I'll talk about that。If you guys have other requests。

 I'm happy to take requests if I can do it， I'll do it。😊，Some of these things。

 if you asked me to talk about algebraic geometry， I might not be able。So yeah。

 feel free to let me know。😊，对。So if not， then lets let's get cracking on。Other things， actually。

 let's take a two minute break and then we'll continue and we'll talk about we'll talk about。😊。

How would you solve this problem？Next' stop。OK没事，如的时候。法律。そう。So I want to solve linear systems。

I want to solve Lx equals p。So how do I solve it as we said， we can use Gaussian elimination。

 but we can use other methods。😊，And let's actually。While we are saying this。

 let me just briefly just talk about one more thing。So we know that oh so my my fee。

 the potential has suddenly become an X because I always get confused fee shouldn't be available and the right hand side had become B。

 whatever it is。😊，Okay， so I want to solve Lx equals b。😊，One thing to note， by the way。

Is that L equals b is the minimizer。哦。Yeah， is the minimizer。off。The expression。啊。

X transpose Lx minus Bx。And I've just defined a function f of x。Which is defined to be this quantity。

L symmetric matrix， B vector， oh then maybe I should say B transpoence。哎。呃 gonex function。

Its minimizer is achieved by setting the gradient to zero。

And you will take the gradient of this thing so the gradient of f， you know。

 I hope you guys I'm sorry I should have posted on pi earlier。

 the gradient of f at the point x is just the derivative of whatever of this guy。

 which happens to be L x minus B。And you have a function。F， you want to minimize it。

 you should set its gradient to0 and its gradient to 0 is exactly at Lx equals speed。嗯。

So this solution that we found， the electrical current that we found is the minimizer of this expression。

😊，And the minimizer of this expression。😡，Let's just look at the minimizer of this expression。

 So if you're trying to minimize。啊。F x transpose zx minus bx。And remember。

 B has a one in one place and negative one in another place。And0 that。So。You could up to scaling。

 just say actually what I want to do is I want to set bx to be equal to one or something like this。

And minimize that quantity。Yeah。Why is this scother。Maybe it's not quother。

Maybe I could figure out Bx is equal to some constantancy。

I want to minimize this quantity so I wanted to get something out of this thing I might have painted myself into a hole here is what I wanted to say I wanted to say that this is why if you look at this quantity。

😊，This。可。But Bx equals some constantency。In fact， I just wanted to set dx equals 1。嗯。

Why let me tell you why I wanted to do this thing I wanted to pull out the fact that this is the flow that minimizes the。

Energy barn。Let me notI've confused myself。嗯嗯，走。Going off of script is a bad idea in lectures。

You should stop me and I'm going lost。Anyways。What do I want to do， I want to minimize this function。

对。Now this function， so the solution of this thing is the minimum to this function。😊。

So given a convet function， I want to minimize it， how well can I do this？Classic problem。

Given a function F， which is convex。F going from RD。You are。So this is unconstrained。

Convex optimization。Just find me。Minimize overall x and RV。Of special。嗯。嗯。

And you can do the constrained versions of these things as well。K is a subset of RD。

It's a convex set。And I'm assuming you guys remember what a convicx set not a convicx site。

 this is a convex set， this is not a convex set。You remember what it gone makes？

Any two points the line segment joining them live within the center。

Convex said what's a convex function actually， you know。

 maybe it's it's a good idea to define convex functions and。We'll define it in。In several ways。

The conve convex function f is convex。If。For all X， Y。啊。You know， it kind of looks like this， right？

At the point X at the point Y。嗯。A off。Lambda times x plus 1 minus lambda times y is at least lambda times f of x plus1 minus lambda times f of y for all lambda in the lamb7。

Yeah。F is context， this is like the zero order definition I'm not using the notion of gradients and stuff like this。

😊，F is gone with if F of y。Is greater than equal to f of x。Plus。

 and I'll draw a picture for this thing， the gradient at f of x times y minusx。

what's the picture for this thing？And maybe I'll。This is convenient。Picture says。

This is the function F。I'm taking the point X。And at this point。At this point。

 I'm going to draw the tangent line。Should be drawn with a different color。And now I say， okay。

 this was X。And add the point， why。F of x lies above the tangent line。

This is like the first order approximation。This is a linear approximation。Act the point X。

So if you draw these tangents， you draw these tangent planes， the function lies above the tangent。

F is constant， so this is like a first order。で、すね。It's using the notion of a gradient。

If you guys you know might be rusty on this thing， but it comes back fast， I've posted some notes。

 I'll post some more notes。Zco actually wrote one of her faculty， Zco Colter。

 he wrote these notes when he was a grad student back at Stanford there some very nice you quick notes quick refresher。

😊，然。Which one？Absolutely， absolutely。😊，Absolutely。So in this case， we are just using a positive feda。

In fact。It'll allow us to give good convergence rates。😊，Next homework。O。

You can give a second order definition F is you know you can write down the Hasian。😊，啊，对。

The heN ofF is positive semi defphite this is this is shorthand for positive semi defite all its eigenvalues are greater than equal cur be。

😊，This， you know， a is bigger than zero just means this is just saying that a is PSC。

A is bigger than B just says a minus b is PSB。All its eigenvalues are。No negative。

And this is known asB。The loaner order。哦。Symetric matacy。

I'm sure you can extend it to asymmetric non symmetric man system。O。So if you lay down the Hessian。

You remember the hessian right the hessin is just a matrix full of second derivatives。

 second partials。😊，Is positive then。O。So these are all呃。Con vity。

And these are the kind of problems we want to solve， minimize。It's in here。So。Yeah。

And what kind of guarantees do we want？That really comes down to like it's it's not trivial。

 right because。😊，Are there can I even write down the minimizer。

 is the minimizer writeritable you know compactly？Is it rational， and it might not be rational？

s then how do you write it down， so typically we want so we want。You find。Some extractt。Stlash that。

F of x hat is less than equal to f of x plus epsilon for all。诶。Such that， you know， yeah。

 for all x in K， let's say。And I'm going to use K just for the moment。

 and you can imagine K is all of space。😡，So I want to make sure that f of x hat is no more than the minimizer plus。

😊，Yeah。And ideally， so we want ideally。In time。玻璃。In polyly in log one over Epsilon。

And these will be amazing， these will be essentially poly time these are really。

These are the gold standard that we are looking for。Back。Or weekly。And fine。哦，年。Any one know。

Each of these things I'm not talking about the complexity of various operations。

 you know how long does it take to compute the gradient。

 how long does it take to do what what kind of access do I have to ask we'll just come to that。😊。

But for right now， I'm just saying， you know， these this is the gold standard， this is what we want。

嗯。This is a weaker guarantee。We should be able to get this more easily。

And indeed that's what we will do。 So what I'm going to do is I'm going to do in the next couple of lectures。

 So I'm going to show you a simple sort of gradient desent。

Algothms will achieve this kind of guarantee and the proofs are going to be simple。😊。

And they'll make some nice connections with what we just saw。

 the hedge algorithm and other such things。And then we'll see how ellipoid。Or the centroid methods。

Will give this kind of guarantee or maybe even interior point max。We give this kind of guarantee。

 but that requires more sweatingers。So we do that。对。So that's the plan for the next few lectures。

Convet optimization is really。I is the tool。To use。Now of course。

 a lot of the sort of machine learning that's happened I mean， yeah。

 one doesn't want to always justify things using machine learning。

 but what can one do is that's the cool you know many cool things are coming out。😊，Well。

 how do you train these neural networks you usetochastic gradient in descent。

 you should understand gradient in descent。How do you solve large optimization problems nowadays。

 you know much of machine learning is optimization。😊，If you actually want to solve that exactly。

 you should understand how to use more powerful techniques。看。Good。So having said that。

 let me dive in。Let me give you。Okay。So by the way， you know， I already use this earlier。

 but I use this without actually explicitly saying this， so in unconstrained。😊，Conundex optimization。

I want to find the minimizer of this thing， then x should be a point。

 I should find a point such that the gradient of f at x is equal to 7。嗯。好。TheHave immediate。

Thank you。The function should be below the linear interpo。Thank you。

 where would I be without you guys， thank you。ok。What do I want， I want to find a minimize。

I want to find this point。This is where。The tangent is at Slo zero。I want to set the gradient to be0。

And so we are we really we have just gone back， we said， oh， we defined F of x。

 how do you minimize F of x you solve that？😊，This is kind back and forth， but in some cases。

 you know F is not given explicitly or it's a pain to actually figure out the zeros or rarely you just yeah。

😊，You want a different method of finding that point。

It's useful to keep the optimality conditions I'm just writing down the optimality conditions。😊。

For unconstrained optimization， you just want a point at which the gradient is 0。For constraint。

This is not the case， right？Because what do I want I want？

I want to minimize the function in this range， this is my K。The minimum point is here。

And at this point， the gradient is not 0， but the gradient0 point is outside。

So you can't just write that。So what should you write？So for this， I always have to think about。

 so I want to say for media。The constraint case says。That you know。

 so maybe I'm saying x stars that's I thought x stars whatever this is the optimal point。

 so as a constrained case this will be a point x star。Such that。If I look at the gradient of F。

At start。So I'm sitting at X。I'm claiming this is the lowest point。Everywhere I look。

 the function should be going up。Every feasible point I look was there might be points lower down。

 but they're not in my feability I'm standing at the corner of my。

F of x star in our product with y minus x star。Is greater than equal to0 for all y below。

Every favorable region I look should be upwards。What does the gradient tell you。

 the gradient tells you the direction of increase。😊。

And it's actually telling you how much you're increasing in this direction。😊。

So that's the optimality condition for constraint。You should think about this。At this point。

My gradient is increasing in this direction， the feasible region is still the night。

So for every point in the positive on the positive side。My gradient has a positive impact。

So the picture is exactly this Im standing on the corner and the bottom so everywhere I look。😊。

I should have a positive sort of increase with the positive correlation with the gradient。

The function increasing that direction。Because what the gradients telling you the tangangent plane。

 the function is above the tangangent plane， the function3 are higher。Yes。Okay。Good。Questions so far。

 I'm just throwing out facts past in few years。我得。You guys have probably been taking your machine learning learning courses more recently than I am。

You probably remember all this and you're like， yeah， of course。Okay。Good， so let's do。

 let's at least define gradientd descent。And grading descent isn't one algorithm it's a framework and frankly oh so the gradientding descent goes back to Kohi。

 I think 1840 something like that， I don't know。😊，I'm terrible with the dates。

 but you know for the longest time in CS in theoretical CS we won't study this thing actually back in the 70 we used to have numerical methods courses so people used to study this。

 but then we went more combinatorial。😊，And now we are realizing， oh。

 we are missing out all the school stuff。Getting back to this so this is a great time to pick up again on this stuff。

And so this is gradient descent， and it's really， as I said， it's a frame。

Because it's not really one algorithm， there are lots of parameters that you can play around with。

By the way， somebody knows the difference between a parameter and a hyperparameter you should come and teach me I have no idea why something that hyperparameter yes。

😊，Oh， is there a difference， Okay， you can teach me later。😊，Okay， gradient discent framework。😊。

What does this say， start off with a point which I'll call x not。So its at some point。

Is a starting point？How do you choose X not that's I't know you can think about it this is this is an sort of。

This is part of your design decisions。And then you say this the following thing for or maybe I'll call it X1。

And for p equals12 equal capital t。Xp plus1。If X B。So I'm standing in the point Xt。

And I look at the gradient， the gradient is telling me which direction the function is increasing。😊。

I want to decrease the function， I should go opposite。And how far should I go， well。

 that's another decision you can make。Call the learning rate or step size。Depending on your religion。

You can change the step size with every time T， let me not yeah， let me not worry about it。

Let's say it's fixed learning rate， fixed step size。At every point in time。

 I take a tiny step in the direction opposite with the grid。😊，I get a new point。And just continue。

So I do this for some T steps， what is T that's a design decision。So this is the design decision。

 this was a design decision， this is a design decision， it's already in yellow。

 I don't worry about it。Return。You can return。Many different things， you can return X star。

This is again a design decision you can return x star equals xt if you want it。嗯。

X t plus  one whatever， but for for this current lecture I'm going to return。The average point。对。

The picture is basically you know actually I don't know the many this is best done via an animation I'll post something on Piazza and lots of animations just just look it up on Google it's very pretty animations that come out。

😊，Good。Greating decent。Take a tiny step in the direction opposite the gradient do this for T steps。

 how long the well that's for you to decide。How what step size again you can decide what you return could be the final late rate thats called last it rate convergence。

 some nice results on that or this is like an average it rate convergence。嗯。Good。So first of all。

There's nothing to it， no rocket sciences。How fast does it converge， it does converge？

Maybe let me just mention， you know， since we are here and willll be soon out of time and again。

 I always rush things at the end。😊，U。If I was doing constrained optimization。

I'm sitting at Xt out here。I take a step， I might go outside this body Xt plus one if I just do this thing。

If I take a step in the negative gradient， I might go outside the body， what should I do？

I should project back。So I can define xt plus1。Tinder to be this point。And then I can say。

 and maybe I'm just making this ugly Xp plus one。Is the projection。Onto all you know onto the body K。

Of x b plus one then。What is this， let me just define it。This is the min。Overall points x and K。

Or argument。Overall points x in k of。The distance。Between x and xt plus1。明白。Is the closest point。😡。

2 xt plus 1 kiloilber。Oh， by the way， whatnot？デザインですじゃん。For this lecture is the two norm。But you can。

 you can define。You can choose a different node， depending on your application。

So what happens basically at this point， I say， oh， I stepped outside the body。

Let me project back on。And I call this Xp plus one。喂。对了。Some people call this。😊，With this thing。

 it's called projected gradient design。You might worry oh what if my function is not differentiable it doesnt have gradients you can define a notion of subgras all you needed were these objects these tangents which lay within below the convex function。

So for instance， if your function look like。This。I the auditor。It's not differentiable out here。

 but you know。This is a perfectly reasonable definition of a Italian plane at this point and so is this and so is this and so on so forth all of them have this property that they support the function from Dlo。

😊，Its called a sub gradientant。😊，Subgrading to the set。

 actually of all these possible things you can。Yeah， so you're just making sure that。

These are all the possible supporting hypoplans。😊，At this point， that's is subgrading to that point。

And if the function were differentiable， then the subgradient would contain a single point the gradient。

😊，And essentially for all these things， you can choose any of the sub。😊。

On a subgrading descent projected sub jargon abound， you know， you can just。Generate jargon。过嚟。Okay。

This one， right？Excellent point。How do you solve this problem？We might want to get away from this。

 I'll give you an algorithm which gets away from this is not the Frankquilist method。😊。

But that will reduce it quickly solving。😊，Yeah。对。It will get away from this a little bit。

 but it will really come down to what your body cares so K better will be nice。😊，But excellent point。

 hold that question for a little bit。I'll just give you the serumorem and we deal with it Pat。

 so let Fb conves。And I'm going to assume two things I'm going to say。Suppose。Oh， so Fb convex。

 let's say。over。Some said， okay。And I'm going to assume。That the gradient of f at all points x。

Is bounded by some parameter G。For all x belonging to k。The function has bounded gradients。

I need to assume something in order to show conversionver。

And this is some set of assumptions that work， but we will come back to this。😊，And let's say。Like x1。

 the starting point minus x star。Is bounded by some D。And maybe you know X should。

 you might as well take it within K？You could just say this is at most， you know。

 the diameter of k at most B or something but。Okay。Then。F of x at。A atmost f of x star， so x star。

 let's say is the minimizer。It doesn't matter you can choose whatever x you want f of x star is you know。

 then then。哦。Annie at Scott。Such that this is true F of x hat is that most f of x start plus epsilon。

After。B equals。Order off。GD over epsilon。Square space。嗯。So what am I saying。

 let me just know let's unt the theorem f is a function。

It's got gradients which I kind of reasonably bounded。They're not crazy gradients。Because you。

 if your function looks really like this。Then getting to the minimizer。It's a very finicky operation。

 you need to take very tiny steps。😊，喂。啊，那个。Yeah呀呀。Then。啊啊。播。Step size。Some， some function。

I'll tell you what function of G and Epsilon we'll have to choose。

So I have to choose some function from some step size later。そして thisスですね。嗯。

So as long as we are not very far away from the optimum， if we are far away from the optimum。

 it will take more time， sure。If the function is very steep。

 it might take more time because we just have to take tiny steps。

 we can't afford to be you know taking fast steps。And you want to be close。

 you need to take more steps。没。This is the high level that people you know will immediately say this is the basic gradient descent conversionverence guarantee。

😊，And it takes one over epsilon squared， people don't worry about the G and D thing。

The behavior is like one or whateveron squared。Okay。Often。People call this。1 over square root T。

And versions。In T steps。The error。Is going to be behaving like one over square root epsilon at like one over square root。

Because these is like one over epsilons。And this one over squarerup one is really not one。

 but you know between France again， it's 450。F， okay。

So this is the standard gradient in different conversions。

If you assume more you can get more if you assume the radio of function is nice。😊。

You can get one over Epsilon， you can get log one over Epsilon。All kinds of nice things。But we。

 we'll get to that。But let me。Maybe just mention one last thing。So hit is。An algorithm。

Where you say oh at every point in time， so heres the game。This might seem familiar to you。

At every point in time， I play a。Point X T。Exing。The world gives me a convex function F。😡。

It might be giving me a inner product function， but it might be giving me some other cons。😡。

I play a point XT， the world gives me a convex function FT。I pay FT of Xt。😡， so you know I play Xt。

 the world gives me FT。😊，My cost is this。I want to minimize。My cost， I want to look at my long term。

Cost。😡，And I want to say this is not much more than some of FT of X star。For any。Exter。Les excellent。

The function changes under my feet。But I want to say， look for every X。

 my guarantee should be something like。嗯。You call online convex often。

So let me give you the algorithm， the algorithm is this。😊。

And the only thing that changes is at every point in time T。

You take a step according to the TF function。And let me give you the guarantee。

 the guarantee says summation over Tftt of xt。A that most。Oh， maybe this should be Epsilon T。

should behave like this Ft of xt is at most Ft of x star。Plus， epsilonte。Exactly the same amount。

This algorithm of them gives you essentially another no regret strategy， no regret strategy。

 just like we said before， if I average things out。嗯です。This was like a hedge guarantee that we gave。

It's going to be the same old。So one of the things you know。

 I'm going fast and you know I don't expect you to get this the high level bit was。

Gradient descent is an awesome algorithm， very simple。And we you know， we gave this theorem。

 we can analyze it， maybe we will analyze it， it's not a big term。But the beauty of this is。😊。

That gradient anddesscent also works in an online setting。Every time the function changes。

And what I want to do is I want to minimize my long term cost。And I say， oh， for every other point。

 that single point can have a long term cost， which is that。

My long term cost is this average long term cost， average long term。It's within Epsilon。

Of the best possible long term cost。As long as Steve。我呢噶。

Very beautiful guarantee it came out of again， grad student Marty Vikovi used to be we were back in We Hall。

😊，And Mardi 2003。He proved this term and that time nobody was losing people were like， yeah， I let's。

And then five years later， it just caught fire。But anyway， I'll tell you more about this in Friday。😊。

But for any point。For any this is any target point。

