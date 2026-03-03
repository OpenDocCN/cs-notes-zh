# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P15：-15-Advanced Algorithms (COMPSCI 224), Lecture 16.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/9bd8c167b575ae00fe30ad99d1983db2_0.png)

Oh， okay， how many get started？呃。Let me wait so that the camera's not locked。😀Yeah。Okay， good。

 so last time。So okay， so today。What say today。We're going to finish simplex。And then。

And then I'm going to say things about strong duality。And complementary slackness。

 you'll see what I mean what that means。诶。I'm going to sort of tell- so the simplex algorithm。

 unfortunately， there are no known polynomial time implementations of it。

 they all take exponential time。嗯。So the first polynomial time algorithm for linear programming is the ellipoid algorithm。

But I don't want to get into。I think to properly cover all details of ellipsoid would take me maybe a lecture。

 and I don't really want to spend too much time on ellipsoid。

 I think it's not used that much in practice anyway because it's kind of slow。Okay， but I'll just。

 you know。Say some words， I guess， about it。Roughly what it does。And then in the notes。

 I'll add a link to。To something that says more， if you really want to know about it。And then。

Either at the end of this lecture or next lecture。We'll start interior point。

 so path following interior point methods。Okay， so。

This is also a polynomial time algorithm for solving linear programs。And it's more。

It's faster in practice than ellipside。I mean， it's already fast and in practice it's even faster than what people prove about it。

Even with pathon Inter point。I won't cover every single detail because there are many details to make it cover all cases。

 but I think I'll tell you enough that you'll understand what's going on。Yeah。So my understanding is。

They use。Both simplex and interior point are used in real life。And I think ellipoid is not used。

Really。好。I think it's not just about ease of implementation。 I mean， it is is easy to implement。

 but I think also it's just these pathological cases that these cases that make you take a lot of time are pathological。

So in practice， you run it for some number of iterations and it finds opt。Yeah。But yeah。

 I don't take my word for practical things， but that's at least what I hear。对。Okay。

 so let's finish up with simplex， so simplex。Remember the basic idea was。🤧嗯。Vertices， okay。

We saw that Well， we gave one definition of vertex and we saw it was equivalent to another one。

 So we want to minimize。C transpose x。Such that Ax is equal to B and x is at least zero。

 coordinate wise。Okay。And we can define this polytope P， which is the set of all points。

 x that are feasible， so x such that。AX is equal to B， and x is bigger than equal to 0。嗯。Right。

We started that。A vertex。X and P。Okay。Is a point。Such that。AX。The sub matrixx AX。

 I'll say what this meansX。Has full column rank， so it has linearly independent columns。

And we said that AX。Is a。Is sub matrix of a。Specified。By the indices。J， such that xj is not0。

 it's strictly positive。Okay。And remember that we're in the situation where。A is M by N。

And C are n dimensional vectors。Okay， so this already tells us that， and let me call this thing here。

 let me define this to be B sub x， the basis for x。 That's what we called it last time。

This implies that B sub x。Has size at most M。Right。Because。Column rank equals row rank。

 and the row rank is definitely at most M。Okay， so。The basic idea of simplex was then。嗯。So， for each。

Vertex X。Assign。A basis。B of x。Which is a subset of1 to n。So that the size of Bx is exactly M。

Okay so。Maybe I let me call this B prime of x to distinguish。

So this is the set of indices that are strictly positive， and then I'm going to extend it。

 possibly extend it to a set that has size exactly M。

 because it might be the case that the set has size at most M。Okay。Such that。Let me call it a sub Bx。

 the columns are indexed by B of x。Has rank。Exactly M。

So the point is that if B prime X had size less than m。

That means I can augment it by adding more columns to make it have full rank。Okay。

 I'm assuming that A has full row rank。Because there's no point in having redundant rows in A。

 this would be redundant constraints。And you can filter that out in preprocess it。

Either redundant constraints or obvious infeasibility。Okay， so。Good。Other questions at this point。

 So AB is a square m by M matrix， it's invertible。A。And what we said last time was。So， now。Will。

 always。We start。At some vertex。Let's call it x0 is the initial point。

 I mentioned how to get an initial point to start with simplex last lecture by basically running simplex on another LP。

Okay， so we started some initial vertex x0。And。Greedily。move。To subsequent vertices。

Until some halting condition。Which I said last time and I' read it again。So。At any time。We represent。

Our current vertex。By some basis。And we also defined N to be。The set went to end without B。

 the compliment。So with simplex at every step， we write our LP。We say， look。

 so C transpose is the same thing。 So this is our LP here， right， this is our LP。

 I'm going to rewrite it as。Minimize C transpose。嗯。X， B plus C， N transpose X。

 N subject to the constraints that A， B， X B。Is equal to。Plus A and XN。Is equal to B。And X v。

Xn are bigger than equal to0。WhenWhen I put a set as a subscript。

 I just mean projected to those coordinates。And what we did last time was we multiply both sides of this equality by AB inverse。

And that let us write X B in terms of X N。And then we substituted Xb in this expression here。Right。

Right， so this implies that。X， B is equal to。Something。Right。

 which implies that what we're really doing is minimizing some other cost function。

 Let me write it down again。You can write this thing as C transpose， AB inverse。B。嗯。Plus。CN。Minus。

 I believe， AN transpose or AN and transpose。AV inverse。Transpose。CB。Transpose。C X n。

This is what you get after you substitute this expression for XB in here。And then subject to。

Those same constraints。And this thing here。Is some new cost vector。 So this is a constant， right。

 This doesn't depend on the variables at all。So the only thing that depends on the variables is this thing。

 which I'm going to call C， N tilde。Is the reduced cost。And。Now。At at first pass。Assume that。X，b。呃。

So let's say the current vertex， let's say， is V。Asse that VB。Is strictly positive。

 meaning that B prime and B were the same， right， we didn't have to actually add more columns to make it full rank。

So in this case。What can we do？If any of these， if any of the entries in so。If。

There exists a J in capital N such that C tilde J is strictly negative。Questions， any questions。

I know I've been writing a lot of symbols。So the point is that if any of the reduced cost entries are strictly negative in capital N。

Then what I can do is I can take this vertex and start incrementing the Jth coordinate。Okay， notice。

 though， that。If I actually wrote this out。Oh let me actually write it so X。Xb is equal to。AB。

 inverse。Applied to B minus A Xn。So the point is， the variables in B actually depend on the variables in in n and capital n。

 Okay， so if I take this vertex。And I start incrementing the J coordinate and Js in capital N。

What that means is I'm implicitly adjusting some of the variables that are also in B。Okay。

And so some of them are going to start maybe decreasing。

And I can only increment this Jith coordinate a certain amount before one of them becomes zero。

And then I can't increase the JF coordinate anymore。Right。To maintain feasibility。

 and then what I have is a new vertex。Right， I've incremented one guy to be He used to be 0。 right。

 This was， this is capital N。 This is a set of0 coordinates。 So the J coordinate of V used to be 0。

 Now it's positive。 but then I've made something else0。 So I've moved to another vertex。

 So simplex basically moves from vertex to vertex by doing this。Okay。And the point is， if。

 if VB is strictly positive， that means I can move， I can move some amount。

 So if there existed today。 so then。Increment。Increment。VJ， until。Some I and B。Has X equals 0。

And the point is， the amount of increment I can do before this happens is positive。

Because they all started strictly positive。And they move continuously when I increment this coordinate。

But。So V is my current vertex。So yeah， so I just wanted to differentiate between this is like the LP and then V is the point that I'm currently working with。

Okay， so okay， good。Otherwise。If CJ tilde is greater than equal to0 for all。呃。For all J。Then halt。

And declare。Optimality。喂。And why can I do that？I can do that because。Look at my objective。

 There's a constant term。 plus there's the reduced cost transpose Xn。 Now， Xn， remember。

 there's this constraint。 Xn is a non negative vector。So if XN is non negative。

RightThis is true in the entire polytope。 So if X n is not negative and this reduced cost is also non negative。

 then this can only go up。Right at the current vertex， this is0。

 this whole thing is0 at the current vertex， but this can only go up for any other point。

 which means that this current vertex is better than everyone else。Okay。But there's， okay。

 so this is， this is the first pass， right， assuming that V。

 assuming that V V is strictly positive in reality， because of this augmentation。

Some entry in VB can actually be 0。In which case。There's a problem here。😡。

Which is that even if there is a C tillilde J， which is negative。

We might not be able to increment the JF coordinate at all because it might instantly saturate a non negativity constraint。

Okay， so I don't。 I'm not going to give the details on that， but I will tell you。

Basically how it's fixed。So， if。VB。So it doesn't hold。Well， if that doesn't hold。

 this case is still fine， right， If the reduced cost is not negative， we know we're still done。

 The problem is， what do we do if the reduced cost has a negative entry。It doesn't hold。

And there exists a J， such a JN。Such that。C tilla J is negative。Then。We need。2。Or we will。Add。J to B。

And kick out。K from B。But the question is， which J do you add to B and which K do you kick out？诶。

And if you're not careful about this。You might get into， as I mentioned before。

 you might get into an infinite loop where you keep replacing the same variables with each other and never actually make any progress。

Okay， but it turns out that。There is a way to decide which J to put in because there might be multiple Js which have a negative cost。

 reduced cost， and there might be multiple k's which are already zero。Where VK is already0。

So it turns out that there is a way to do this， which probablyvably never has an infinite loop。

I'll tell you what the rule is， and then I'll put a link in the notes to a proof。

 I don't want to get into the proof。But。So this thing is called Blands rule。So。

Multiple pivoting rules。Ruleles。For choosing。J and K。Exist。

some don't terminate if you're not careful。But Bland's rule。Terinates。So what is Bland's rule？Pick。J。

 to minimize。C tilde J， less than zero。If multiple such J exist。Then you take the first one。Okay。

 now what do you do about？What do you do about choosing K？Well。So define this vector R。😡，Where。

RB is0。And RN is basically this reduced cost。And define。Define a prime。To be a。AB inverse。Of a。

And B prime to be A B inverse。B。And define Q。To be the men。Over all I。Of。B prime I。Over a prime Ij。

Such that a prime IJ。Positive。And then what you do。Is。You pick。Well。

 let me write this as I said K before， let me write this as K。You pick K。To minimize Q。

If there's a tie。You pick the first queue。The first K。Minimizing Q。Okay。

 and it's possible to prove that this thing actually doesn't terminate。 I'm not going to do it。So。

 that it does terminate it doesn't。 Yeah， that it terminates。 And when it terminates。

 you will be in this case where the reduced cost will be non negative。O。So， okay， good。Yeah。

 so there are there's this， you know。Annoying case you have to handle where。

Bases don't have size exactly M。And unfortunately， with other algorithms like。

Ellipoid and interior point， there are also these degeneries you have to handle， which yeah。

 so basically I don't want to handle any of these in this class。呃。Otherwise。

 it'll just be too pedantic，So。Good， so now what do I want to say。Wo。

I guess if I just assume that Bsville works， then there's nothing more to say。

 that's the end of simplex。Other there questions about？The simple algorithm。

Before I prove strong duality。Yeah。Oh。Right， so what would you do， I guess you would do。嗯。

You could add the constraints one by one， right， And if the rank doesn't increase。

 then you know that the thing you just added was already in the span of the previous things。

 And then you just。And drop it。How to compute the rank， I mean， you could do。嗯。呃。

One thing is you could just do。This is probably the most efficient。

 You could do the determinant of a transposese and make sure that it's not zero。 But actually。

 there is， there is a paper that talks about how to compute。Rannk in input sparsity time。

 So like the number of non zero entries in the matrix times some log factor。Yeah。

 you can compute rank in that time。And that's due to one of the authors was Lap Chiao。

I don't remember all of them， but that was， I think in 2010， maybe or something。 Yeah。

 maybe I'll I don't remember off top my head。Yeah。But you asked me， how do they do it in practice。

 like in real life， So that I'm not so sure。 but I this is just me。

Saying things off the top of my head。 But yeah， it's definitely in P，Okay。Good， so strong duality。So。

 yes， so。There are a couple ways of proving strong duality。 One is non algorithmic。

 and the other is to sort of get it out of the simplex algorithm。Okay。

So to get it out of the simplex algorithm， I wanted to define what's called the shadow price vector。

Let me and that's why， which is。呃。A， B inverse transpose。Cbi。Okay。So as I iterate in simplex B。

 it changes and the shadow price vector changes。And。🤧。First of all。The claim is that。First of all。

 okay， let's， what is the dual， Forge before we before I say this， what is the duall so。Do all of。

Of LP。You know，M C transpose X。Such that A X equals B。X squared equals to0。Is。

Are people any any takers， have people become fluent in duels？Okay， so first。I'm not going to min。

 I'm going to max， what am I going to max？Yeah， so y transpose B。Right， so。

The right hand side becomes the objective。 and such that。A transpose y is at Mo C。Okay。

 so that's the do。🤧嗯。So I say it again。You don't because this is because you have equality constraints。

 Yeah， so when you have equality constraints， the dual variable。

 corresponding dual variable is unrestricted。嗯。Very good。So the first claim。Is that。呃。C transpose。

 So currently， we have some iterate CB， B， and we have some some vertex V， B， I said。

 is that C transpose V B。Is equal to B transpose y。So VB is the vertex we're currently at。

So this already looks like strong duality， except for one thing， right。

What would we need to do to prove strong duality？Why is this alone not sufficient？Yeah， well。

 V V is definitely feasible。 It's a vertex in the primal。 Yeah， why， why might not be feasible。

 right， In fact， it's not gonna be feasible until the very end。Right， so。So proof of this。嗯。

So remember we have。We have that A B。VB equals B， which implies that Vb is equal to A B inverse B。

So this implies that C transpose VB。Equals。C， transpose。AB inverse B。呃。What's V in Y is AV Trans CV？

Oh well well， first of all， this。Well you right。C transpose Vb is equal to Cb transpose Vb。嗯。

And this is the same thing as B transpose。AV inverse transpose。CB， which is B transpo y。Okay。

So what does it mean to be feasible？We want。Why to be dual feasible？So define the dual slack vector。

Which is R equals。C minus a transpose y。I just subtracted a transpo y from both sides。And so we want。

Are to be non negative。Okay。And。The definition。Of y implies that Rb is equal to0。And Rn。Is equal to。

Something very convenient。 Okay， if you do the calculation， it's equal to C till the n。で。Okay。And。

We halt。When C tilde n is bigger than equal to 0， which implies。Doal feasibility。对。So。Yeah， I mean。

 I guess I swept under the rug。Some of the complication of proving strong dual because I didn't actually prove Bland's rule。

Okay， but that takes some amount of effort。Often what you'll see you know in other gra algorithms courses is that people。

Won't。They won't prove it through simplex。 They'll give like a non algorithmic proof。

Of strong duality， using more convex geometry， okay， but。I think it's。On the one hand。

 I didn't give all the details of the proof because I't improve Bland's rule， but I think。

It's a nice thing to know that it's basically a corrollary of the fact that simplex works。Okay。

Questions。So I wanted to say something about this complementary slackness。嗯。So。We can define。

Complimentarity gap。As basically x transpose R， or this is the dual slack。And those that's just。

X transpose。C minus a transpose y， Where did I put？The dual slack is c minus a transpose y。嗯。

Which is。C transpose X。Minus。呃。Ax。Transpose y。And A x is equal to B if x is feasible for the primal。

And this is just。C transpose x。Minus B transpose y。So at optimality， we know that。This is zero。

So we have。ATheorem， this is called complementaryary slackness。

And if you remember earlier in the course when we were doing online algorithms。

 I called something approximate complementaryary slacklaness。

Which basically said that if you're not quite at， but you have some bounds on。

How how you almost satisfy complementary slackness， which I'm going to say in a second then。

You can say something about。The goodness of your primal solution。Okay。

 so a couple military Stockness says。If。X star。And why star？Are optimal。

For the primal and due respectively。Then。The sum over I from1， then for all I。Either。Xi is equal to0。

Or。嗯。Si。mininus。H or C minus a transpose y， C minus a transpose y。I equal to 0。

 So either the dual slack is 0 or the primal variable is 0。 And the proof of that is。

Basically already written down。Right。At optimality。By strong duality， there is no gap between。

The prim in the duel。 So we have that。C transpose x minus B transpose y is0 at optimality。

But we know that c transpose x minus B transpose y is just equal to the sum of X。Okay。And I mean。

 that's basically all these terms here are not negative。 So for them to sum to 0。

 each sum end has to have either X I being 0 or R I being 0。Okay。So。

That's pretty much everything I wanted to say about。These two things。

Which means now I'm going to move into。The second pair of things。

 So before I switch topics do people have questions。有。Okay。

So let me make sure I write down this reference properly。Or actually。

 I did want to say a few more things about simpleimpx， so what's the runtime？Well， in each iteration。

 to move from vertex to vertex， it's polynomial time。And how many vertices are there？So。

Each iteration。It's polyly time。Number iterations。Is that most number of vertices？Is that most what？

What's the mostive， the crest bound you can think of？Yeah， it's the most entry end。

Because vertices are represented by these basees， which are subsets of Pi M。So this is exponential。

In fact。It's possible。To prove。That the number of vertices。

Is that most n minus M over2 choose M over 2？Okay， and。

The reason you could hope for any better bound at all is that not all choice。

 not all choices of bases like when so what's let me write， let me go back for a second。

Where did I put that thing？呃。Well。Here， so once you have a basis。

 how do you actually get the vertex corresponding to that basis you do A B inverse times B。

Right and the point is。AB inverse times B might not actually be a non negative vector。

And if it's not a non negative vector， then it's not your polytope， it's not feasible。

So if you're careful with that， it turns out that it's actually possible to get a better bound。

And I think more than careful。 I think this is actually。

My understanding is that this is actually kind of hard to prove。 So this。This follows。So I asked。

I asked some Michelle Goman， who's an expert in this about it。 and he said， this follows from。

Something called the upper bound theorem。That's an interesting name for an upper bound。

People prove up arounds all the time， I don't know why this is the upro theorem。

This follows by McMulen。And when I Googled to find out more。

 it seemed like it was a major open problem for a long time than he solved it。

 so I'm not sure that this is actually something very easy to prove。In any case。

 that's still a big number， okay。So。Another thing I want to say about simplex is。

you could ask yourself， well。Okay， sure， the number of vertices could be very large。But。嗯。

Maybe we still can prove that there is some way of navigating this graph quickly， right。

 So at the end of the day。There's a graph here where the vertices of the polytope are the vertices in the graph and the edges are neighboring vertices in the polytope right and you could say。

 well， maybe there's hope that any polytope given by M constraints by M hyperplanes in n dimensions doesn't have that big of a diameter。

 like the graph the graph that this polytope represents doesn't have large diameter。Okay。

 that would be a necessary step。To show that simplex could hope to take less than an exponential time。

Okay， it's not a sufficient step because simple doesn't necessarily find the shortest path。But right。

So，One necessary step。And when I say an implementation of simplex。

 it all comes down to the pivoting rule。Okay， so。There might be many choices of J with a negative reduced cost。

 which one do you actually start incrementing， so that's a pivoting rule。

 And then if there's some zero coordinate and B， which one do you kick out。So one necessary。

When necessary。Condition。To allow。The existence。Of polylytime。Simpplex。Is to show。That。Any polytoe？

In let's say， D dimensions。うんうんん。Defined by M hyperperplanes。Has diameter。I want I say diameter。

 I mean of the graph has graph diameter。You， say， polyly。OfMD。And there was a conjecture。

Who's heard of this， by the way？Yeah， has anyone heard of the Hise conjecture？Okay， so。

Is that the diameter？Is that most M minus D？And I forgot exactly when this conjecture was made。 oh。

 yes， good。So this conjecture was made in 1957。ok。And。In 2010。嗯。Let's San's say Santos。

And the annals of math。In 2011。Disproved。The first conjector。

And he came up with an explicit polytope。Where D was 43。M was 86。And the diameter was at least 44。

So off by one。啊。Right， right？And you conjector。But then he also also showed。He also showed。嗯。

For fixed D。D， as well as an epsilon bigger than  zero。There exists in infinite。Family of polytopes。

With。I'm going to infinity。That哎。Have diameter。At least one plus epsilon。M。Okay。

 this is still pretty far from。Poly M D， right， I mean。

 these are like nearly linear lower bounds in M。Right， I mean， to get Paul long time for simple。

 if you can prove a diameter or upper bound of。M to the 10th D to the fifth， that's perfectly fine。

Again， this is only a necessary condition。For hope for simplex， it's not a sufficient condition， but。

For all we know， there is an implementation of simplex。Which is fast。We just don't know one。

I think we don't know any that。 yeah， I think yeah， we don't know one right。Okay。

The last thing I want to say about simplex is so simplex works well in practice， right。

 so we were asking about this。 So， you know， as a theoretician。

 you want to give some theoretical justification。 why is simplex faster than this exponential bound that we can prove。

And there was some nice work on that by Spielman and Tang。So I mean， this。

 I'm not going to claim that this is exactly what's happening in practice， but at least it。

It shows why simple isn't as hard as it seems， so why。The simplex。Not so slow in practice。So。

Sel in and tang。Well， this is the journal version， but the paper came out earlier。

 it this feeling tang。They define something called smooth analysis， which has been applied。

To other areas as well。Yeah， and when I go off on these tangents， know。

 without actually proving anything and just telling you history， you。

 feel free to pick these up for your project ideas。Okay， so smooth analysis， the basic idea。Is。Okay。

 so there's worst case analysis。 That's what we're all familiar with in， you know。

 this class in CS 124， right， want to say that， no matter what the input is。

Your algorithm will be fast。There is average case analysis， which assumes an input distribution。

And you want to say that your algorithm has an expected running time， which is fast。

 If the input is drawn from this distribution。Okay。

 but then you have to make an assumption on what the distribution on inputs says。

Which might not be realistic。 You might have no idea。 So smooth analysis is something in the middle。

The basic idea behind smooth analysis is。Okay， so my algorithm has to be fast。 you know。

 the expected running time has to be fast on the following kind of input。

You give me a worst case input， like a worst case LP， for example。

 And what I'll do is for every input variable， for every entry in that constraint matrix A and for every entry in the right hand side vector B and in the cost function。

 I'm just gonna to add epsilon random noise， like Gaussian noise。With very small。

 with mean 0 and very small variance。Okay。So it's like a randomly perturbed worst case instance。

And then you ask， what's the expected running time？On the worst case in this setup。

And what Spielman and Tang showed was that for simplex。

 with a particular pivot rule that they analyzed， it's polynomial time。Okay， so basic idea is to。

Take。A worst case instance。Instance。And add。Small random noise。To all entries， independent noise。

Then。Analyze。Expected runningtime。So just to make sure we're all squared away on the quantifiers。

 it says that so we have an algorithm A。Such that for all inputs X。The expected。Run time。

Let's say A on input X tilde。Is something small？Where the expectation is over X Tilde is a randomly。

A termbed。Version of x。So that's smooth analysis。Bounding this thing。

Is what's called smooth analysis。Right so yeah。No， so it's polynomial in one over the variants as well。

这。Okay， now that really is all I wanted to say about simple。

I get questions before I do ilpsoid stuff。Yeah。いや、ベジ政任。Exactly。Just to make sure everyone heard it。

 So in the graph there， two vertices have an edge between them if their bases differ by a single constraint。

Okay。So。So I mentioned simplex came out in 1947。Blandand's rule was in the 70s。Okay。

 so I think before then things just people didn't care about termination， I don't know。

But the first time we had。A polynomial time algorithm。

 probablyably polynomial time algorithm for linear programming。Was also in the 70s due to Kachin。

First， polyly time。Algorithm。For LP。Is。Ellipoid。Now it's due to kch and。

And the journal was a Russian journal， the Qdi。I can't pronounce Russianing， so I won't try。Okay。And。

I am not going to prove basically anything about ellipsoid。

 but I will say a lot more about interior point， but I just want to tell you what thellsoid algorithm is。

 and I want to tell you some properties of it。That。Actually， make it more useful than。

That make it more useful than interior point and other algorithms in certain situations。 Okay。

 so we'll see this in a second。 One nice thing about the ellipsoid algorithm。Is that， in some cases。

You can even solve exponentially sized linear programs in polynomial time。 you might say。

 what are you talking about？You know how can you even look at the input。

 So really what ellipsoid needs to work。Is an oracle。

 which if you give it a point that that's infeasible。It will tell you a violated constraint。Right。

 so for some problems， you can implement that oracle without ever explicitly writing down the linear program。

Right。And then actually ellipsoid makes a polynomial number of oracleoles。Is it clear what I mean？

I mean， I didn't tell what the algorithm is， but。The point is if you can。

 if you can implement this oracle， you don't actually need to write down the LP explicitly。

 Of course， if you write down the LP explicitly， one way to implement the oracle is to loop through all the constraints and see which one you violate。

But if you have some more efficient way of doing that。Then you could plug that into alipoid。Okay。So。

嗯。So， given。呃 some。A in RN。And as well as。A positive definite matrix。The ellipsoid。E of A color A。

Is defined B。The set of all x。Such that x minus a transpose a inverse。X minus a。

Is less than equal to one。So for example， a sphere of radius 1。

 a would just be the identity matrix and A would be the center of the sphere。And in general。

 you can always view ellipsoids as unit transformations of the sphere。

 linear transformations of the sphere， sorry。Okay， so。So the ellipsoid algorithm。Is used。To test。

Feaasibility。Of some polytope。Which is a set of all x such that， let's say AX is at least。嗯嗯。

No may be consistent on my notes。Hey， so。I mean， I'll show you in a second。

 once you can solve feasibility， it implies that you can do linear programming and optimize over this polytope。

But it looks where I just。Let's you do this。 And the basic idea is。So， one。Start。With some ellipsoid。

E not。Which is guaranteed。To contain。To contain。P。Okay。If P is bounded， that is。

So if P is abounded polytope， then remember， I think we I mentioned this very briefly last time。

 right， we know how to get vertices of the polytope。

 You do it by taking subsets of the columns and then solving a linear system right So if you know and if you if you know that all the input numbers to your LP are rational。

You can clear denominators and assume they're all integral。

Then there's some number of bits that are used to specify the input。😡。

And when you estimate bit complexity， right， So how many bits do I need to represent the inverse matrix of in of an integer matrix and then multiply times the right hand side。

 I get， I get a bound on the number of bits I would need to represent any vertex。Right。

So by that kind of bit complexity analysis。You can show that。Just by the big complexity。

 you automatically know that。P has to be contained in a ball of a certain size。Okay， if it's bounded。

 so getting this initial E0 is not that hard。 It's just the sphere of the appropriate radius。Okay。

 so two。Check。So let's say。诶。Check if so let's say it。Let a。The center。Of the current ellipsoid。

And then while。Yes guess I'll put that here。While a is。Not in P。Okay， so。

If the center of the current ellipsoid is in P， we're done。Right， we have our feasible point。

 Ellipsoid is trying to find a feasible point。However。

 the center of the current ellipsoid is not in P。 What do we know， So we have this ellipsoid。E。

 right， I can't draw 3D。And it's not in P， which means there's a violated constraint。

What's a constraint， a constraint is a hyperplane？I'm really bad at drawing this 3D stuff。

So we know that。A。A is the center of the ellipsoid。 And you're telling me that。哦呃。

AYou're telling that a is not feasible， which means that。Our desired polytope。

Completely lies on the others， on the other。Side of the Hyplane。没。So。So， a。Lies on opposite side。Of。

Hyperplane H。From P。So you create a new ellipsoid。And there's a closed form formula for how you get the new。

 So if you're given H and you're given the old ellipoid。 Now what do you want。

 You want a new ellipoid， which is smaller。Which is guaranteed to contain just the other side of that hyperplane。

Create a new ellipsoid。E prime。Which。Still。Contains。Pi。And。Has smaller volume。

And this is the place where。Right， ellipoid doesn't really need to have the LP explicitly。

 It just needs an oracle， which can tell it this hyperplane。Okay， in fact， because of this。

You can use ellipoid algorithm for an even more general class of problems， convex programming。O。So。

Where the feasible region is not necessarily a polytope， but say a convex set。Okay。

And there's a theorem。I think it' sometimes it's called the separating Hyplane theorem。

 and sometimes it's called the Hanbanak theorem。Okay， I think dependence on who you ask。

Which says that for any convex set and any point that's not in the convex set， a closed convex set。

 and the point that's not in it， there's always a separating hybridplan。

So if you're able to implement the separating hyperplane oracle， then you could run ellipsoid。嗯。

And also， depending on what your initial convex set is。

 you need to be able to easily say what E zero should be。嗯。And it's possible to do this。Such that。

The volume。Of。The volume of E prime。Over the volume of E。Is at most， I think something like E to the。

One over2 n or something。Either minus1 over2 on。O。And finally。嗯。I found。An A and P。Return A。Else。Yes。

If。The volume of E。Has become。Too small。 I'll say what that means in a second。declarecl。P is empty。

Basically， to clear in that， your LP is infeasible。Okay。

 so there's already one thing which should alarm you。About this。Right。

Does anyone see why this might be a problem？Yeah。他他。Right so P， I mean， if you have， let's say。

 an equality constraint。Well， here I， here I said that there are all inequality constraints。

 but you could you could use inequality constraints to implement equality constraints， right。

 You could say X is at least。5， and it's at most minus5 or something。Right， so you could。

 you could have anality constraint， which reduces the dimension of the polytope。

 So it's actually a smaller dimensional。It's a polytopken， like a subspace。So in the higher space。

 it has zero volume。Right。So that's。That's a problem。So。

But you actually would do in a preprocessing step。Is so theorem。Let L be the。Bit complexity。Of P。

So L is a proportional like。Log of。So where did I write this polytope， AX is at most B， I think。嗯。

Max over Ij。AIj。Plus， let's say。The largest entry in B。That's plus let's say， M plus n。Okay。Define。

Some P prime。To be a new polytope。Where you say p primes instead of allx。So that A X is at most B。

Plus2 to the minus L。Times the all ones vector。So this is a vector that says one in every entry。

And you also add a constraint that。呃。For all J， minus2 to the L is at most X J is at most 2 to the L。

So now this polytope has some very small volume。 I mean， it's at least it's exponentially small in L。

 but it's bounded from below。 It's not 0。Then。P is empty。Meaning infeasible。Ps infeas。

If and only if P prime。Is in feasible。So I'm not going to prove it。

 I'll put a link in the notes to where if you want to read the details。 I mean。

 this is really fudging with you know precision issues and bit complexity。

 I don't want to spend time on that on the board， but it's not too hard of a proof。

It comes down again to the fact that vertices are specified by a certain number of bits due to inverting linear your system。

 blah，lah， blah。So now， now， you know when the volume has become too small， right。

 if it's smaller than this。Inflated polytope， then you're done。

There's also an issue that if you run ellipsoid on this polytope。Then。

The thing you get might not actually be in P。It might P prime is a little bit bigger than P。

But there's also a way to round it so that you get back to P， Okay。

 so I'm not going to get into that either。Okay， good， but with LP， as I've talked about it before。嗯。

🤧嗯。We don't just want to do feasibility， we want to do actual optimization。So。Suppose。We want。

To solve。Min。Of C transferpose x。Such that。AX is at least B and x equals B， and x is at least 0。Re。

How would we do that with the ellipsoid algorithm？So step one。嗯嗯。Check。If P equals。

Access that Ax equals B。X is greater than 0。Check if it's。Feaible。If not。Output。Not feasible。Okay。

Step2。You write the duel。Which is Max。B transpose Y， such that A X。

A while A transpose Y is at most C。Check。That。Let's say P dual。

Is the set of all y such that a transpose y is at most C？Check out this thing is feasible。If not。

If not， then what do you output？啊。Yeah， unbounded， then the prime was unbounded。Then， output。

Unbounded。Okay， so now we know that after steps1 in two， we know that P is feasible and bounded。

Which means by strong duality， the duall is feasible and bounded and it achieves the same thing。

So step three is now。Just compute something inside of this polytope。嗯。Find。X， Y。That's feasible。

For this polling tip， which is AX equals B。X is at least0。 A transpose Y is at most C。

 and C transpose X equals B transpose y。So for this set of constraints。Right。

 and once you find something feasible for that set of constraints。

You've found the optimal primal end dual solutions。不认。So that's the ill algorithm。

Or that's everything I'm going to tell you about the episodeoid algorithm。

But I will actually tell you。Stuff about Inter point。Right， and yeah， so I guess。

Maybe I should have said this， so this implies that。This volume comparison here。

 this implies that if you look at the volume。Of。The k ellipoid。It's at most。

The volume of the original ipoid。Times e to the minus k over 2N。Right。And。

You know what the original ellipsoid is at some sphere， you can compute its volume。

So as soon as this expression on the right hand side becomes too small， like smaller than。

Smallller than the volume of this P prime here。Then you can just say it's invisible。好是。

Questions about about I mean， I didn't give you， I guess。

I didn't tell you how to update the ellopoid and all these。Things。But I'm not going to cover that。

But aside from that， are the ideas clear of roughly what elllipsade is？Okay。Okay。

 so that's a lipoid when erase that so now just path falling into your point。So I mean。

 I only have about six， seven minutes。So what I'm going to do is I'm just going to give you a flavor。

Of what Inter point is all about。And then next time I'll actually tell you details of interiorPoint。

And really。It's going to look， I think。Pretty different from the kinds of things you。

Have seen so far in algorithms classes because it's really something that comes out of optimization。

You're going to see a lot of， you're going to see gradient descent， Newton's method and。

You're gonna see multivariit calculus， Okay， so， but I mean， the basic idea of。

 of the algorithm is something that。嗯。There's a clean understanding of what the basic idea of the algorithm is。

Okay， so let me set things up。Interior point method。It also。Gives polyly time。

When you're programming。It was introduced。By Car Marar。I think in stock 1984。

 the journal version was the same year。 Let me write the journal version， which is combinator。

Combin Toic 84。And it's really been quite influential。

There are entire books written on Interior Point， you can use it to solve other convex programming problems as well。

And。It's sort of。I don't， I don't I't know if opposite is the right word， but let me say opposite。

 It's sort of opposite of simplex。 So simplex is always on the exterior of the polytope jumping around from vertex to vertex。

 squing along edges。Interior point。Tries to stay as far from the exterior of the polyseps as possible。

 Okay， so it tries to stay inside and gradually move toward a vertex from the inside。Okay。So。

Gradually。Tries。To reach。An optimal vertex。All staying。In the。Interior。PSo you might say， well。

 wait a second。 if I can， you know， how do I get in the interior， that means I can test feasibility。

 right。And we we saw with thellipoid with the la right here。 if you can do feasibility。

 you can basically solve problem the problem。 So the very first step of interior point is you actually modify your LP。

 We sort of did this with simplex， right， to get an initial vertex。

 You modify the LP except we're not we're not going to do like two interior points。

 it's all going to be one point， but we're gonna modify the LP so that it has a very obvious interior point。

And。It's also going to be the case that for this modified LP， if the original polytope was feasible。

Then。Kind of a vertex， the optimal vertex to this modified LP will correspond to a vertex of the original one。

Okay， so really， we're just， we're just gonna add actually one like。嗯。I mean。

 I I don't want to get into this detail at this point because there are only a few minutes。

 but you can basically add。One extra variable。Which easily allows you to satisfy constraints。

 But you're going to penalize it very heavily in the objective function。Okay， so for example。

 you know that。Numbers never get bigger than say，2 to the L in your LP。

 So you're gonna to put a weight on this variable that's like， you know。

10 to the L or something so that if your actual thing was feasible。

 you would never use this variable。ok。But now that you have it。

 you can easily come with an interior point。 And then now you try and run the interior point method to eventually get down to a vertex。

You look a little troubled。No。왜で。Yeah， so it's going to be。Right。

 so the number of iterations of interior point is going to be at least L。In fact。

 the best known implementations of Interi point well。Before this year or before last year。

 the best known。The best known implementations of interior point。

 the number of iterations was like L times square root of M， where M is the number of constraints。

Now there was a paper just this year which showed that the square root of M term can be improved to squareir root of the rank of the constraint matrix。

嗯。But yeah， L， you need at least all iterations。Yeah， even the running time of ellipoid depends on L。

In fact。There are no strongly polynomial time algorithms for。For linear programming that we know of。

Okay， and so we're going to look at。So。We're going to look at things of the form min of C transpo x。

Such that AX is at least B。ok。And。We're going to turn this into。

An unconstrained optimization problem。Dine the slacks。Define the slack vector， Sx to be AX minus B。

So for any feasible X， this thing is non negative。Okay。We'll try to optimize。To compute。The minimum。

Over， x and Rn。An unconstrained optimization problem of lambda times C transpose x。Plus。The sum。

I going from1 to M。Of some barrier function。P of well， actually， let me write it like this。Of P。

Of S of X。Where。P。Is a。Barrier function。Such that。P of Z goes to infinity。If Z goes to0。For any eye。

Okay。And。We'll use。The log barrier。Which is P of Z。Is going to be negative sum i from1 to M。Of lawn。

Of ZI。K。So。On the one hand， if you set lambda be 0。And you try and minimize this function。

All you care about is this barrier function， which really is trying to keep you as far。

 So you just don't want any of these constraints to be tight or even near tight。 You。

 you want to be well in the interior of the polytope， right。

 which is obtained by minimizing this barrier function。

 And the point minimizing this barrier function is usually called in literature the analytic center。

 Okay so when lambda is0， you find the analytic center， And then what you do is。

You start off with Lambda small， so you'll actually start interior point off with Lada being1 over 2 to the L or1 over exponential in L。

Okay。And you'll approximately solve there'll be a way to get an initial point for the very small lambda。

And then once you have a solution or a near solution for Lambda。

You're going to increment Lada by a little bit to get a new Lada prime。

And you're going to take your old solution for Lambda and do an iterative algorithm like Newton's method。

To improve it for the Lada prime problem， and now you'll have a good solution for the lambda prime problem。

Now you'll take Lada prime and increment it just a little bit to lambda de prime。

Now you'll take the Lambda Prime solution and run Newton on a few steps。

And get a good solution to the Lambda double prime problem。 And you keep doing this。

 You keep alternating， incrementing Lambda by a little bit。

 running Newton's method to make the old solution good for the new Lambda until Lambda is big enough。

Okay， and big enough is going to turn out to be something like， well， I mean。

 you'll see the details next time once lambda is something like M times 2 to the L。

You can show that a good solution for that problem basically is almost optimal。

 and then you can just round it to a vertex。So。In a nutshell at the very highest level without giving you any details。

 that's how Inter point works， and we'll see details on that Tuesday。Questions。对。

