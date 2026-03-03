# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p09 -09-Lecture 9_ Linear Programming Duality --- Part 2).zh_en -BV14CAUeUEPj_p9-

I this go ahead and get started？So this is our third lecture on linear programming a week ago。

 I tried to convince you that linear programs model lots of different problems that we care about。

 so we should care about understanding them， we should care about algorithms for them。

And then on Thursday we started our discussion of linear programming duality。

 which we're also going to be discussing all day today and really LP duality。

 you know I think in hindsight after you finish the course。

 you'll recognize it as really sort of the heart and soul of CS261。

 really kind of the concept that binds an enormous。

 overwhelming majority of the concepts that we're going to discuss。So， you know。

 I know that was five days ago， and it was a pretty conceptually rich lecture on Thursday。

 so let me help you page back in sort of where we left off。

So if you have a linear program of the following form。

So maximization linear program subject to inequality constraints with non-ne random variables。

 we talked about the idea of generating upper bounds on the best possible objective function value of this linear program by taking suitable linear combinations of the constraints and then we noticed that looking for the tightest upper bound of this form is itself a linear program and that linear program is called the dual and in general what happens when you pass to the dual。

 min goes to max max goes to min variables turn into constraints， constraints turn into variables。

 the objective function in the right hand side gets swapped and the constraint matrix gets transposed that's sort of what's happening here so。

You can see some of it more clearly in the vector matrix notation， which I've listed in pink。

 So for example， you can see here that the constraint matrix gets transposed when you pass to the duall。

So。This is just one particular form of a linear program。 And as we've discussed。

 there's many forms you could have equality constraints， instead of inequality constraints。

 You could have general real valued variables instead of nonne variables。

 you could have a min instead of a max。 And last time we talked about how to take the duall of any linear program。

' actually use that general recipe today。 when we return to bipartid matching。All right， so。

Once we understand the meaning of the dual linear program。

 once you understand that every feasible solution to the dual is by construction。

Gives you an upper bound on the primal objective function value， at least for the maximization case。

 Then weak duality is selfe。 So basically， every dual solution has an objective function value。

 which upper bounds， the objective function value of every primal solution。

 feasible primal solution that holds in particular for the optimal solutions to the primal in the dual from which we can conclude that the optimal。

Solution of the primal is at most the optimal solution of the dual。 Okay。

 If the primal is a minimization linear program rather than maximization。

 then this inequality goes the other direction。So just to remind you， and also for reference。

 here's the proof of weak duality。And so again， what this is showing， it's saying take anything。

 any x feasible for the prim will take any y feasible for the dual。

 let's show the objective function value of x， which is this。

Is bounded above by the objective function value of the dual solution Y， which is this。 and again。

 it holds in particular for the optimal x and the optimal Y。And so how do you do this。

 while you just invoke for this inequality， you invoke。That。Why is feasible for the duel？

So these linear combinations a transpose y if the constraints dominate the objective dominates C。

 We're also using here that x is not negative， so by making this bigger。

 we only make the overall quantity bigger because all these are not negative。

This is just association。And over here we have we're using similarly that x is feasible。

And that y is non negative， okay？So we did that derivation last time this is just a succinct reminder and again that picture you might want to have in mind is the same one I drew when we talked about the value of a flow being at most the value of a cut so again this is for the case of a maximization primal otherwise it would be reversed so we can plot on a line sort of of objective possible objective function values。

 the x's or the objective function values that can be attained by feasible solutions to the primal。

 the O's are the objective function values in the dual that can be obtained by feasible solutions for the dual weak duality says all the O's are only to the right of all the x's。

And one thing that gives us immediately is a sufficient condition。For optimality。

It's not clear if it's necessary yet， but it will be necessary in the end。

So a sufficient condition for optimality would be that you have a superimposed X and a no。

 that is that you can find feasible solutions with equal objective function value。

This proves that both x and Y are optimal for their respective linear programs。 Y， well。

 no x can be strictly to the right of any O。 So if you have an x exactly with an O。

 then that's got to be as right most as any X could be。 It's got to be an optimal primal solution。

 Similarly， you know can be the left of an X。 So if you can actually superimpose within an x。

 you got to be optimal。And then， the last。The thing that I left you with on Thursday was complimentary slackness conditions。

So let me remind you about those and also explain why they're true。

Or why there are sufficient conditions for optimality？So complementaryary slackness。

It's sort of a corollary of that corollary。So the compliment is slackness conditions。So again。

 suppose you have Xy feasible。For the primal one do respectively， and suppose it's the case。

That over in the primal， the only time you give a non-zero value to a decision variable is when the correspondingent constraint in the dual is tight。

 meaning holds with the quality so remember every variable in the primal corresponds to a dual。

 a constraint in the dual， every constraint in the primal corresponds to a variable in the dual。

 so you can talk about saying a primal variable xj， it is only non-zero。

When the corresponding constraints or the JF constraintsstraint。Of the dual is tight， Ie holds。

With quality。Okay。So that one of the two conditions。

 primal variables are only non zero when the corresponding dual constraints are tight。

And then we also have a second condition which goes the opposite direction。

Which says that a dual variable should only be non zero。

When the corresponding con of the primal is tights。Okay。So again。

 the I decision variable in the duall is in correspondence with the I constraint in the primal。

 so we can talk about the corresponding constraint in the primal being tight。All right。

 so that's the hypothesis。 Suppose you have feasible solutions that satisfy one and2。

Then we get the same conclusion as before。Then X Y， both optimal。

So what I want to do next is prove this before that。

 So this brings us back up to date with where I left off on Thursday。

 So any questions about the recap or about the big picture。Correct。So the proof of this is actually。

Staring at us。On the top board。So suppose x and Y are feasible and suppose1 and2 hold。

Let's stare at that circle derivation up there。That proves that the objective function value of the primosal was at most out of the duall。

I claim that the points of conditions one and two， what it buys us。

This allows us to conclude that both of the inequalities in the circle derivation are actually equalalities。

So in the week duality proof。1 plus 2， imply。That both inequalities are actually。Aqualities。

So this might be a little bit easier to see if I switch back from matrix vector notation back to the sums。

 So for example。Focus on this first inequality here， so transpose x is at most， this other thing。

So y transpose AX？I transpose a transpose x。呃。And consider a single term。

 so see transpose x is the sum over J of Cj Xj， just consider some fixed J。So if one holds。

Then I claim that for all J。CJxj just equals。X J times some of our AI J Y I。 So again。

 this is for a fixed J。 that's just one ingredient of each of these numbers， right。

 so these are all scalrs。Right。This is a sum of a bunch of scalar summed over J， same thing here。

 I'm saying coordinate by coordinate the terms match。Okay。And if you look at it this way。

 it should now sort of be obvious？Case1， xj is0。Both sides are zero。No problem。Case 2 xj is not0。

Well， then just the condition tells us that the corresponding dual constraint holds with equality， I。

e。This number actually equals this number。Okay。So either xj is 0 when you're done or the equality or the thing is tight。

 and you're also done。So it's called complementaryary slackness because it's just asserting that you don't have slack simultaneously in the primal and in the dual。

 Okay， if you think about a nonzero value corresponding to having slack in the primal and you think about being strict inequality。

 having slack in the duall， you never see both of those at once。 That's the condition。

 If the condition holds。Then because the circle derivation holds with quality。

That proves that the objective function value of the primal and the objective function value of the dual are the same。

And by our previous corollary， that says they both have to be optimal just by the X's and O's argument。

Okay。So that's complementary slackness， and that's why it's true。Okay。So next。

 I'm going to do a couple different things which are less abstract。

 more concrete should help you understand this better。

 but any questions just about sort of the abstract versions of these concepts before I continue。Okay。

So one thing which I offer to you sort of purely as a metaphor， not as anything formal or precise。

 but that seems to be helpful for students sometimes is a way you can kind of physically think about or interpret complementaryary slackness conditions。

So suppose you have a linear program and you've got some direction， some objective function。

And then you're going to have some optimal solution X star made the point furthest in the feasible region in that particular direction。

So if you want， you can think about the objective function as effectively exerting force。

Force in the direction， C。Okay。And you can think of these as sort of physical walls， right。

 so the sides of the feasible region。Okay。So basically in optimizing this linear program。

 as we sort of discussed before， you're pushing in a particular direction until you can't go any further。

 and in general， except for some edge cases， you're going to wind up at a vertex at a corner。Now。

 at this point， once you get to X star， there's no longer any movement。X star is just holding there。

 despite the fact that the objective function is still exerting force in the direction C。

So if there's no motion， then somehow the sum of the forces acting on this point should add up to zero。

So what else is exerting force on the point other than the objective function？Well。

The sides or if you like the constraints。Can also exert force backward。

Okay in the opposite direction。The direction of that force exerted by one of these walls is going to be given by the normal to that hyperplane。

You can then interpret these yI's。 So previously we're interpreting the dual variables as multipliers of the primmal constraints。

 for this physical intuition， you can interpret the y's as the magnitude of the force being exerted in this particular direction。

 being exerted in the direction of the normal vector of the Ih constraints。 Okay， remember。

 dual variables coursed on to constraints。 So one dual variable for each of these sides。

So if this is motionless， the sum of the forces should be zero。Now。

 what does complementary slackness say okay。So the version I'm looking for is this version。

So let's look the condition2， So Yi is strictly positive only if that corresponding constraint in the primal is tight。

That just says that any of the sides of the feasible region。

 which don't actually touch where the point gets stuck。

 they're not allowed to exert any force on this point。 Okay because they don't touch it。

 On the other hand， anything which is tight。 So those these correspond to tight constraints。

 These two sides of the feasible region。 So anything that is tight can exert force。

 And then you're looking for some of those forces which equals sort of the opposite of the objective function value。

 So if you like， this is one way to think about complementary slackness。 So basically。

 the only things that can exert force on a solution are the constraints that are binding。

The constraints that are touched by the optimal solution。Okay。

So why am I telling you about complementaryary slackness， what are they good for？Well。

If you think about it， if we take a step back。So we talked about when we were solving Maxflow and then again。

 when we were solving matching， how these sort of harder problems in P required sort of discipline。

 they require really a strategy to solve them correctly。

 so you almost have to sort of be thinking about how you're going to prove an algorithm correct when you're designing the algorithm itself。

Commentary slackness provides a very general paradigm。

 really three different paradigms for these kinds of disciplined strategies for solving problems。

So what do I mean？Well， consider three conditions which may or may not be satisfied at any given point。

See if you have a legit， you have some kind of attempted primal solution。You have a why。

And you have the complementaryary slackness conditions。What did we just say。

 we just said if1 through three are all satisfied， then x and Y are both optimal。 Okay。

 so we know that。Now， when you want to solve a problem from scratch。

 you don't expect to just zip straight to the optimum。So the general paradigm would say， well。

Of the three things which together are sufficient for optimality。

 pick two of them that you're going to keep satisfied at all times in your algorithm。

You're going to violate the third one initially and work toward restoring the third condition。Okay。

So the paradigm would say。Pick two to maintain。At all times， so ass invariance。Work toward the third。

Okay。So you could start with a feasible primal and a feasible due， presumably not optimal。

 maybe just sort of initializations， and then work toward complementaryary slackness。

 you could start with a primal solution， that's feasible。

 an infeas due and complementaryary slackness and work toward dual feasibility。

 or you could start by violating the primal feasibility constraints。

 maintain a feasible due and complementaryary slackness as invariance。Okay。

So it turns out an enormous fraction of。The polynomial time algorithms or just the useful algorithms for linear programming and also special cases like we've been talking about are。

 in fact， instantiations of this general paradigm。 That's exactly what they do。In fact。

 maybe one of the most transparent examples of this design paradigmtime is an algorithm。

 you already know， the Hungarian algorithm。So going to show you next is that the Hungarian algorithm。

 indeed。Maintains two and three。It maintains a dual feasible solution at all times。

 it maintains complementary slackness at all times， and it works toward primal feasibility。

 and the reason now in hindsight now that we understand linear programming duality。

 we can say the reason the Hungarian algorithm is correct is because it halts with primal feasibility。

 dual feasibility and complementaryary slackness。So that's really kind of the sophisticated way to think about the Hungarian algorithm。

 and we're now in a position to have that kind of understanding。Okay。2。So。

Sort of a case study of LP duality and complementary slackness。A problem we've already seen。Min cost。

 perfect bipartite matching。Example number two， maybe you don't remember example number one。

 So example number one on Thursday was max flow。 Okay， so what we do。

 we show that you could formulate the maximum flow problem as a linear program。

We took the duall of that linear program， and we tried to interpret it。

 and we observed that actually ST cuts of a graph correspond to a special case of dual solutions。

 dual solutions， which are01。And then we interpreted the fact that the max flow and cut theorem is true。

 that gave us two interesting implications back with flows and cuts。First of all。

 it verified strong duality for a particular type of linear program。

 namely flow cut primal dual pairs。And secondly， it gave us an interesting example of a linear program that is guaranteed to have optimal 01 solutions。

 Okay so even though the linear programming relaxation of ST cuts allows fractional solutions。

 they never actually help you。 always is going to be a  zero1 solution， which is optimal。

So that's allll recap from example number one， so now we're going to do example number two。

 and we'll see some of the same themes reoccur。Oh yeah， right。 And so and actually。

 if you think about it。I started with maximum flow because it's almost obvious that maximum flow is a media linear program。

But， but I， I claimed earlier the linear programs generalize everything we've discussed so far。

 And if you think about matching， all of a sudden， that maybe seems kind of weird right。

 because when you have flows， flows are allowed to be fractional。

So no big deal that a linear program might have fractions。

 Matchings are not allowed to be fractional。 right They really have to pick an edge or not pick an edge。

 So it seems kind of doesn't seem to tight check， really。

 to talk about a linear program solving the matching problem because what's up with the fractions。

 But again， you know， we have this sort of inspiration from our work on S T cut showing that sometimes you have a linear program And just there's always going to be an optimal 01 solution。

 So that's also going be what happens here with bipartite matching。Okay。

So what's the relevant linear program。For min cost， perfect biid matching。Well。

 so of course we want to minimize the cost of our solution。In our minds。

 we're thinking of Xc as being either zero or one。One， if it's in the chosen matching zero。

 if it's not in the chosen matching， now， of course this can be a linear program。

 we don't know our priorityity we're going to get zeros and ones。

 but that's the semantics that we have in mind。So what are the constraints。

 how many constraints do we have， One constraint per what。So we have one decision variable per edge。

 right， The decision variable to the Xs。So what are the constraints？C again。关关内。Exactly。

So we're going to have a constraint for vertex。Which enforces it being a perfect matching。对。

So I'm using the same notation as a couple weeks ago。

 it's a bipartite graphs with two sides capital V and capital W with the same cardinality。Delta V。

Deotes the edge's incident to V。So we look at how many edges get chosen。Incident to be。

And this should be equal to exactly。1an。你看。At most one， because it needs to be a matching。

At least one because it's supposed to be perfect。And of course， non negativity。

You might think about also including constraints that say Xie isn't most one。

But those constraints are already implied by the constraints that we have so far。

 So if the x's are not negative and they sum to one around every vertex。

 then automatically each x sub be at any feasible solution will be at most one。And so again。

 just looking ahead to the duall。It might be easier to write this in matrix vector notation。

So this here is the all ones vector because the right hand side is all ones。Okay， so any questions？

 so what happens if the solution is a fractional legislation？Good question。Basically。

 that's kind of like an epic fail for now。Okay， so we're basically hoping that doesn't happen。

so I have to justify， it turns out that's not going to happen。

 but I have to justify that that is far from obvious。Yeah， good question。Other questions。

So what I hope is clear。Is that if I give you a perfect matching。

You can certainly translate that to a feasible solution to this linear program。 Okay。

 just by setting x equal to one for the edges in the matching and x equals 0 for the others。

 And the cost of the in the objective function will be exactly the same as the cost of the matching as the way we normally define it。

Right。So any questions before we move on to the duel？So notice that this dual is not sorry。

 this primal is not in the sort of form， the same form as in the。

 say the max flow problem or the one that we started with on the board of the Beaaning of lecture。

What are the differences， we don't have a max。 We have a min。So that's different than before。Also。

 the constraints are equations， not inequalities。But Thursday。

 I gave you a general recipe for taking the due of any linear program， no matter what the form。

 including this form。 Okay， so I'm going to go ahead and take the duel。

And you may want to double check the recipe I gave you Thursday after a class to make sure that you understand why I did what I did。

Now。When you take the duel， it's nice to try to understand what the dual means。

So it's nice if there's a meaningful interpretation of the duel。And usually。

 the hardest thing to figure out what's going on is what is what happens when you transpose the constraint matrix。

 So remember， the dual has constraint matrix A transpose or as the constraint matrix of the primal。

So what is A？For this particular primal。So the rows the columns are indexed by what， first of all？

Colums are indexed by what？It's kind of two possibilities， right？Vertices or edges。Edges。

So the columns correspond to the decision variables。

 the decision variables for this linear program are the edges。And so the constraints。

 then the rows correspond to the constraints， those are correspond to the vertices。Okay。

So inside this matrix， a generic entry will have the form will be indexed by a vertex and an edge。

 a sub v sub B， the row corresponding to V and the column corresponding to E。So first。

 let's just remember what capital A is。 So in capital A。

 the rows just correspond to these constraints。 So fix a row。That is fix a vertex V。

Where are there zeros and where are there ones， So notice the constraint。

 there's some X's with a coefficient of one， and the rest don't appear。

So the corresponding row of a has zeros and ones in it。

It has a one corresponding to exactly the decision variables that appear in that constraint。

For a given vertex， which variables appear in that constraints， well。

 exactly the edges that are incident to that vertex。Okay。

So if you fix a row this constraint matrix and you scan left to right across all the edges。

 you're going to see a1 exactly when you're looking at an edge which is actually incident to V。Okay。

So this is going to be equal to。1。If。E is incident to V。And zero otherwise。Okay。

And how do we figure this out， we figured this out by looking at the constraints of our primole。

And asking， what do those look like as rose？Okay。Now， taking the transpose of a matrix is easy。 Okay。

 so what have weve done， we've translated the sums into a matrix， looking toward the duall。

 we can easily transpose this matrix。 But now if we want to write out the constraints of the dual in a meaningful way。

 we have to understand what these coefficients are。 That is。

We want to think about a column of this matrix because that's going to correspond to a constraint in the duall。

So suppose I fix an edge E。So's corresponding to a column of a， and I scan down。

 I scan through the vertices。When do I see a 1 and when do I see a zero？Well， how about this。

 How many ones am I going to see as I scan down？I'm only going to see two for the two vertices for which this edge is instant to i。

e。 the two endpoint of the edge。So each column of a that is each row of a transpose just has two ones corresponding to the two endpoints of the itch。

All right， so now we're ready to just sort of write this down。 Okay， So first， again。

 let me just do it in matrix vector notation。So what's going to happen？

The min becomes a max when you take the duall， the objective and right hand side get exchanged。

 so this is going to be。Let's see。So the right hand side was all ones， so we now have that。

I'm going to use P to denote the decision variables for reasons it will become clear。

So the constraints here correspond to vertices， so over here the dual variables is are going to correspond to vertices。

I'm going write them piece of V。Okay， and so then we have non negativity constraints here。

 so we're going to have inequality constraints in the dual。So we have a transpose as usual。

 decision variables， this is a maximization problem。

 so this it's going to be an inequality because these are not negative。

 and this is the direction of the inequality because this is a maximization problem。

And the new right hand side is the old objective function， so that's C。Okay。

And then the final twist in that recipe would be here， we have equations， non inequalities。

 So what that means in the dual is that the corresponding dual variable can be positive or negative。

 It's not restricted to be non negative。If this was an inequality。

 we would get non negative dual variables with an equation， we would get unrestricted dual variables。

So each dual variable is just a real number。So that's what you get if you apply the recipe from Thursday。

 so again， let's unpack this。All right， so this inner product， this is just the sum of the P values。

So we're maximizing。Okay。Some of the P value， some of the dual variables。Subject two。Allright。

 so let's remember what this is。 So given dual constraint corresponds to a primal variable。

 so it corresponds to an edge， we agreed that in a row of a transpose。

 you only see two ones corresponding to the two endpoints of the edge。

 So we're going to have a constraint。So again to remember constraints correspond to variables here。

 so we have one constraint per edge。Call your favorite edge G comma W。

Which dual variables are going to show up in this constraint。

 It's exactly the ones for which there's a one in a transpose。

 so it's exactly the endpoint of this edge。So we have a piece of V。We have a piece of W。

So that's a transpose P in this particular row。And this is at most the coefficient and the primal objective function。

For the edge。So that is the duel。All right。Any questions about that。

And so I hope in sort of watching me take a do step by step like this。

 you can really sense that it's just a recipe。 It's really a mechanical procedure that you can apply whenever you need to okay。

 and you'll get some practice on that with the exercise sets as well。And again， that said。

 you know it's good to have a syntactic understanding or a syntactic facility with dues。

 but don't ever forget what's the point of the due。

 The point of the due is to upper bound and as we'll see upper bound tightly the optimal objective function value of the primal。

Okay， so I promised connections to the Hungarian algorithm。So how do we interpret this duall？Well。

 these PC of Vs are exactly。The prices we were using in the Hungarian algorithm， exactlyly。

 It's exactly the same thing。 In fact， if you think about it， like， you might have wondered。

 you know， Coon back in like the early 50s。Why did you ever think to like all of a sudden。

 you know you trying to compute to matching， right？

 So everything about your input seems to be just about edges。 you have a graph。

 you have costs on edges。 You want a matching， a matching is a subset of edges。

 Why would you suddenly attach numbers to vertices in your algorithm to make decisions。 Like。

 how would you ever think to do that？ I gave you kind of ahisical story at the time by analogy to push re max flow algorithms but actually push Re max flows from the mid 80s Coon's algorithms from the mid 50s。

 So that was kind of。😊，A little lie back then。So how would you ever come up with the vertex prices in the first place？

If you knew duality。Then it would be clear there's relevant dual variables。

 Duual variables correspond to primal constraints， matching constraints on the vertices。

 So you get dual variables on the vertices。So that's why Coon decided to have these prices。

Linear program duality was actually quite new at that point。

 it was only invented in the late 40s really， but Couing was one of the early experts on it so he certainly knew about LP duality when he was inventing the Hungarian algorithm。

So that's how you should think about these dual variables。

 they're just the prices from the Hungarian algorithm。And。

If we think a little bit about what feasibility means in the duel。

 and then especially if we think a little bit about complementary slackness。

 all of a sudden the Hungarian algorithm does not seem so mysterious。

 it seems like something that would just fall out of the general principles you're learning in this class。

So， note。What does it mean for a vector of prices to be feasible for the duel？

So it just means all those constraints are satisfied。Let me write them in a different way。

 let me subtract the two P's from the right hand side。So that's just by definition。

 that's what it means for P to be feasible。Now， this thing on the left。

 this is a quantity that you have seen before。Remember what we called that？这证据6。Good。

 we call it the reduced cost。In the Hungarian algorithm。And in Hungarian algorithm。

 we had two invaris referring to reduce costs， the first invariant was exactly that the vertex prices should always have the property that all reduced costs are non negative。

Which we now understand is just saying the vertex prices should be feasible for the due。

So first invari。Of the Hungarian algorithm。Not only that。

What does commentary slackness mean for this primal dual pair？Sure。

So Calary Sness always says that if some decision variable has a non zero value。

 then the corresponding constraintsst should be tight， it hold with the quality。

Now here actually there's only one set of nontrivial complementlaments conditions。

 not too like before。The reason is that we always have equations in the primal。

So it's vly satisfied that no matter what you're doing in the duall。

 the corresponding primal constraints are tight just because theyre equations。

So the interesting common sness condition asserts that。Whenever a primal variable is non zero。

 I use strictly positive， the corresponding dual constraint should be tight。

What does it mean for a dual constraint to be tight， it means it holds with equality。

 which means that this holds with equality quality， which means that the reduced cost is zero。

Which is what we are calling tight edges。 And now maybe it's sort of more clear why we were calling them tight edges。

So common slackness then。Translates。So whenever you have a nonze primal variable。

It should be the case that your reduced cost is zero。The second invariant。

 the first invariant of the Hungarian algorithm， was all reduced costs of all edges are always non negative。

 The second invariant was only about the edges in the matching。

 which corresponds to a positive primal variable。 And it said that the edges in the matching better be tight。

That was the second invariion。Okay。So then with respect to our general paradigm。

 where you have these three conditions which together imply optimality。

 and you have the idea of maintaining two at all times and working toward the third。

We now see that the Hungarian algorithm is exactly an instantiation of that paradigm。

 where the constraint， the condition that you drop initially is the first one。Remember。

 the Hungarian algorithm starts with the empty matching， so that's not primal feasible。

 it's not a perfect matching。But the two invaris say that at all times it maintains conditions  two and3。

 it maintains dual feasibility， it maintains complementaryary slackness。

It terminates with primal feasibility， a perfect matching。

 and therefore by just complementary slightness conditions， it's got to be optimal。Yeah。

And so in general， this kind of algorithm where you relax primal feasibility。

 maintain dual feasibility and maintain common slackness， that's known as a primal dual algorithm。

 Hungarian algorithm being possibly the most canonal example。Okay。All right。In our first example。

 with maximum flow， we were able to deduce some interesting properties about linear programs just because we already knew the max flow and cut theorem was true。

 or if you like， we knew the4% algorithm was correct。Same thing here。

 just by knowing that the Hungarian algorithm terminates。

 successfully satisfies all three of these conditions。

 we can do some interesting facts about this primal dual pair。So first of all， just in general。

If we look at the optimal objective function value to the dual in your program。Just by weak duality。

 that's at most the optimal objective function value of the primal。 Remember。

 this is the direction weak duality goes in when your primal is a minimization linear program。

 The min is always at least the max。And then on the other hand。

 the optimal solution to the PR millennium program。Can only be less。

Then the cost of a min cost perfect matchingup。好看。Wai。Well， what is this that says。

 look at every single matching， perfect matching that exists and pick the cheapest one。What is this。

 this says iterate over every feasible solution to this linear program。

 which includes matchings as a special case， plus other fractional stuff and pick the best one。Okay。

 so the linear program is minimizing over only more possible solutions than the perfect matchings。

 so the minimum is only going to be smaller。So that's why this inequality holds。Okay。

On the other hand。We studied the Hungarian algorithm。

And we concluded that that algorithm is guaranteed to terminate as long as the graph has a perfect matching。

And when it terminates， as we now see， it terminates with primal and dual feasibility and complementary slackness all satisfied。

Remember， when complementary slackness is satisfied， everything has equal objective function value。

 Okay， so but differently， theungarian algorithm terminates with a 0。

1 feasible solution to the primal。And with a dual feasible solution with complementaryary slackness holding。

That implies。That de matching is optimal and that the duall is optimal。 So equality always holds。

Okay。So we wouldn't know this if we hadn't analyzed the Hungarian algorithm。Okay。

 we'd only know the inequalities。But the Hungarian algorithm improves， it exhibits。

 no matter what the graph is， a matching and a dual solution that's feasible that have exactly the same value。

 And that can only happen if both of these inequalities are equations。Just like with max flow。

 the fact that both of these inequalities are equations is interesting。

Why is this always being an equation interesting， because that says there's never a gap between the optimal solution of the primal and the dual。

 And that's a special case of strong duality。 Okay。

 so we verified strong duality in a second class of linear programs corresponding to matchings and their dues。

 That's the first interesting thing。 We'll see strong duality holds completely generally。

 But it's nice seeing get in some special cases first。

Why is it interesting that the second inequality is an equation？Well。

 this is just like when we're talking about cuts。The fact that there's never a gap between the linear programming optimum and the best perfect matching that says you're always guaranteed。

To have an optimal solution to this linear program that is 01。

Fraactctionions do not help you come up with a better solution。

So matchings are always optimal amongst。Feaible solutions to the linear program。

 So it's the second natural linear program guaranteed to have optimal integral solutions。K。

So any questions about any of this？So the rest of lecture I want to talk about strong duality。

So any questions before strong duality， the statement and a bit about the proof。Okay。Okay。

So this is a theorem， this is a major theorem。This is really interesting and not particularly trivial。

Suppose you have a primal dual pair of linear programs in any of the forms of linear programs that we've discussed。

 it doesn't matter which one。So whenever a primal dual pair。P in D。Are both feasible。Then in fact。

 there's no gap。So weak duality always holds with equality。

We already know this is true for Max flow Line programs and their dues。

 we already know this is true for bipartite matching and their dues。

 but actually it's true any linear program。There is never a gap。

 so remembering that what the dual means is a particular method for bounding the optimal objective function value of a primal。

 this actually says that you never need bounds other than the ones given by the dual linear program there always will be a proof in the form of a dual feasible solution that actually proves the correct tightest possible bound on the optimal objective function value of the primal so there's never a need in effect to use anything other than dual solutions to derive bounds on the primal there're always good enough。

Okay。So the assumption is that both are feasible。 Of course， if either one is infeasible。

 it wouldn't make sense to talk about the optimal solution we talked about on a Thursday already from weak duality。

 we realize that if the primal is unbounded。Then the duel has to be infeasible。Because again。

 by construction， any feasible solution to the due would give you a bound on the primal。

 So primal unbounded only if the due is in feasible， Similarlyly。

 the due is unbounded only if the primal is infeasible。

 It's also possible that both the primal and due are infeasible， but who cares about that。

 That's sort of not very interesting。But if they're both feasible， they both have a finite optimum。

 and those two optimal objective function values are the same。Yeah。

And based on what we've discussed so far， we can also think of this as generalizing simultaneously the maximum flow minimum cut theorem。

 hall's theorem， and so forth。 it's sort of a very general min max theorem。Alright。

 so before I talk about the proof， let me just。Make it clear why this is interesting。

How you would use it。So the first few weeks of the course。

 I kept asking you over and over again for different problems。 How do we know when we're done。

And I taught you that the formal way to answer that question is to specify optimality conditions for a problem。

That is necessary and sufficient conditions。For a solution being optimal。So from strong duality。

 we get opt conditions at the very general level of just arbitrary linear programs。

So from weak duality， we had sufficient conditions for optimality。

 but strong duality tells us that those same conditions are also necessary for optimality。Namely。

 X and y are feasible for the primal and duall。Strong duality implies。The X and Y are both optimal。

If and only if。They have equal objective function value。Okay。

So what we knew from weak duality was this direction。If that were true。

 then certainly that were true， that followed from weak dual， sufficient condition for optimality。

But strong duality says， actually， I guarantee you that there is going to be some X Y feasible that have equal objective function value。

 There's never a gap。So if there's never a gap， then the only way to be optimal is if there's no gap between the primmo and the dual。

 Okay if's any gap， you know， you can one of them at least has to not be optimal。Similarly。

When I introduced the complementary slackness conditions。

 I presented them as a sufficient condition for optimality。 But now that we。

 if we assume strong duality。Then in fact， it's a necessary and sufficient condition。

 it's an optimality condition。And that's because complementaryary slackness holds。

 if and only if this holds。 And I ask you to think about that on the exercise set 4。 Okay。

 although it's very simple。Okay。So we've unclear clear on that。

 so these are optimality conditions which in some sense generalize all the ones that we've talked about thus far。

Okay。How do you know you've solved a linear program optimally。

 just exhibit a dual solution with exactly the same objective function value？

One way to do that is to exhibit a feasible due such the complementaryary slaness conditions hold。

 Actually， those are the same thing。So that's how you know you're done， solving linear program。

 you have a dual， satisfying complementary slackness， I。e。 with the same objective function value。

Questions about that？All right so again， so the ultimate answer of how do we know when we're done？

Alright， so this is important enough results that I want to talk about。 It's proof a little bit。

 I don't want to take the time to prove it in its full goy detail。

 That would take me over a lecture to do， But I want to spend the rest of today talking a little bit about。

 about the proof。 and there'll be some further aspects of it on problems at 3。

And so why am I doing this， What's my goal for talking about the proof a little bit。

 The main thing I want to do is demystify for you a little bit。 Str linear programming duality。 Okay。

 at the moment， you know， it just seems kind of。I hope I've motivated why you would want this to be true。

 So I hope you think it's a cool result。But you shouldn' have you shouldn't， have some， you know。

Fundamental intuition about why it should hold， other than the fact that it holds in a couple of examples。

So what I want to do is I want to。Make it develop your intuition so that it just seems super plausible that strong duality actually is true while stopping short of giving a foolproof。

So let me tell you about sort of the ingredients。So I'll introduce these in turn。

So first I'll talk about separating hyperplanes。Okay。

 so the ability to separate con sets from points outside the set。

 this is just a fact that we're going to take on faith， but it's going to be eminently plausible。

 so I think you'll find this very easy to believe。Then what I'm going to focus on。

II'm going to show you how assuming。This separation， separating hyperplane theorem。

 we can derive from it something known as Farku's lemma。

 which is basically like the feasibility version of strong LP duality。

 when I actually spell out Farcus's lemma and talk about it。

 it'll be very clear that it's sort of very similar to what's going on in strong L P duality。

And indeed， from Fars's lelemma， you can derive strong L duality。Without too much trouble。

And this will be on problem at three。So my goals are to explain what is this result that we're going to assume。

 convince you it seems like it's got to be true， and then show you how this implies a feasibility version of strong LP duality。

 so that's the plan for the rest of the lecture。Okay。So I need a new board for this。

Separating hyperplanes， we actually sort of talked about separating hyperplanes a week ago。

It was one of our applications of linear programming。

 If I give you a bunch of X's and a bunch of O's。And I want to know if there's a hyperplan which puts all the x's on one side and all the O's on the other。

And we observe that that can be formulated as a linear program。So now。Instead。

 we' instead of separating x's and O's， we're going to be interested in separating a whole big set。

From some point， not in the set。Okay。So that's the picture you should have in mind。All right。

 so here's the fact。Suppose you have a subset。Of Euclidean space。Think of this if you like。

 as the feasible region of a linear program。And suppose that there are two things true。About sea。

So first of all。Assume it's convex。So what is convex， convex means you're filled in。Okay。

So that's an example of a convex region。A donut。Is a non example。Okay。Formerally。

 a set is convex if it contains all of its chords。 So if you take any two points in the set。

You draw a line segment between the two points and you look at the midpoint of that segment。

 that should also be in the set。So obviously here， if I take any two points。

 the midpoint of the line segment between them was still in the set。Obviously in the donut。

 if I take of these two points， the midpoint of the quarter between them is outside the set。

 so it's not convex。So Con Se contains all of its cordors。Suppose also。But this is closed。

So closed in the topological sense， meaning the set includes its boundary。So。

The unit ball will be an example。And the open unit ball。Would be a non example。看。

So those are the two hypotheses on this set。I want you to notice I'm not assuming that the set is bounded。

And that's important。So suppose you have such a set。And you have a point not in the set。Okay。

 so it's like this picture here。So， think of。That is C， and you have a point not in the set。

Then there exists a separating hyperplane。In the same sense that we were talking about a week ago。

So you've got coefficients。One per coordinate。You've got an intercept。

And it should be the case that all of the set C is on one side of the hyperplane。So we look good。

The dot product of alpha with x， that's at least beta。For all X and C。

And Z should be on the opposite side of the Hyplan。So that's the statement。

You show me any closed convex set， not necessarily bounded， show me any points outside the set。

 I can slice space。So that the sets on one side and the points on the other side。

So in two and three dimensions， I hope you find this intuitively like kind of obvious。

 I guess just seems like it's got to be true， right。

And then if you actually wrote down a formal proof of the fact。

 the formal proof you'd write down actually wouldn't depend on the number of dimensions。

It would hold no matter how many dimensions you had， okay？

For those of you that know sort of a little bit of mathematical analysis， like mathth 115 and 171。

 and no worries if you don't， but if you do， how would you do it？

It's not very hard if you have a little bit of training。You just say， well。

 let's look at the nearest neighbor to Z and C。O。So maybe it's closest to this point here， okay？

This is where you use the fact that C is closed。 By virtue of being closed。

 there exists a nearest neighbor in C to Z。Then you draw the ch。Between Z and its nearest neighbor。

And then you just look at the midpoint of the chor。And you look at the。Perpendicular hyperplan。

Perpendicular to the court。Okay。And that works And again。

 the algebra you'd write down to verify this even in two dimensions just works in an arbitrary number of dimensions。

So where do you use conxity of the set C， Well， you want to argue that all of C is on the opposite side。

From the point of Z， right， So if C wasn't convex， then it could sort of wrap back around the other side of the separating hyperplane。

 and it wouldn't be a separating hyperplane。But by virtue of being convex and by virtue of this being the nearest neighbor to Z and how we chose this。

 all of sea lies on the left。So again， the point is not to understand that at a detailed level。

 it's more just to convince you that if you if we really wanted to have a formal proof of this。

 it wouldn't bother us， we could do it， it would just take us yeah， 45 minutes or whatever。

So that's the separating hyperplane theorem。 So for the rest of class。

 we're just going to accept that this is true。So any questions？All right。So this， we just assume。

So I hope you find it eminently plausible。Now I'm going to prove this implication。

 So I need to tell you what Fars's lemma is， how to interpret it。

 and how to derive it from the separating hyperplan theorem。Yeah。All right。

So what's the point of Farku's Lima， so this actually predates linear programming duality。

 this is from somewhere around the turn of the 20th century。

So when Farer's alemma is trying to answer， it says，Supp you have a system。

Of linear equations and linear inequalities。 That is suppose you have like a linear program。

 but you delete the objective function。Okay， so you have equations inequalities。

 And you're trying to understand， does it have a feasible solution or not。Now。

 if i wanted to convince you that this kind of system was feasible。Wouldn't be hard。

 I'd just show you the feasible solution。 You'd verify all of the constraints。

What if I wanted to convince you that this linear system of equations inequalities was not。

Feaible that there is no feasible solution。 I can't very well enumerate every conceivable solution and show you by one by one that each is infeasible。

 So how would I convince you of infeasibility。So Fargus's lemma gives an answer to that question。So。

Suppose you have a matrix A。As usual， M by N。And suppose you have a right hand side B。

Farcus'slemma asserts that exactly one of the following two conditions is true。

So there exists non negative x。So this is in RN。And。

The way I encourage you to interpret one is imagine this was the system we really wanted to know if it was feasible or not。

 Okay， so we have this constrained matrix A， this right hand side B。 We want to know。

 is there a non negative solution to this linear system of equations or not。

And then the point of statement，2。So there exists a Y， this is going to be now an RM。

Such that y transpose A is component Y is non negative。And why transpose bees？Strictly negative。O。

So again， just to be clear。Right， so B and Y are both M vectors。 This is an inner product。

 This is a scalar。 This is just a number we're talking about being less than 0。 A is a matrix， right。

 M by N。 So Y transpose a， That's a linear combination of its rows。 So that's going be an N vector。

So this is really saying component wise， for each of the young components， it should be non negative。

And the way to think about this， I told you one， we're thinking about we want to know whether or not this is feasible or not。

 the way to think about two， and this will become really clear in a second。

 but think about two as being ways of proving infeasibility of the first linear system。

So it's going to be the case that solutions to the second system will give infeasibility proofs for the first system。

So just like with linear programs and linear programming duals， there's lots of different variants。

 spells and whistles， inequalities， equations， non negative variables， general variables。

 same thing with Farargu's limma。Okay so I've given you one version where're in our first linear system。

 we have equations， we have non negativity， but all of the other ones have them as well。

 and given this one farcacious lemma， you can derive the other one's basically black box and you'll get some practice with that on problem set number three。

But this is the one that's easiest to prove from scratch。All right。So proof sketch。Well。

We're asserting that exactly one or two is feasible。So there are two things we have to rule out。

We have to rule out them both being feasible。 That's going to be easy。

 We have to rule out that both are infeasible。 That's where we're going to use the separating hyperplane。

So why can't they both be feasible。So I claim there's no way。

That you both have a solution to one and you also have a solution to two。Why not？Well。

 consider the number of y transpose Ax， where x is the alleged solution to one。

 Y is the alleged solution to 2。So。X is supposed to be non negative。

Y transpose A is supposed to be component Y is non negative。

So this is certainly going to be a non negative number。On the other hand。

If we look at exactly the same number。By this constraintsstrain。This is equal to B。

So this is Y transpose B。Which is by assumption， negative。Okay。

 so this is obviously a contradiction of the assumption that both of them are feasible。 O And again。

 there shouldn't be any mystery here。 This is by design。Okay。

How would you convince someone that a linear system of this form had no solution was' infeas。 Well。

 one way， one convincing proof of infeasibility would be to figure out a way to multiply the rows of the matrix。

So that the resulting n vector you get is non negative。

 and yet that product of Y with the right hand side is strictly negative。Okay。

So you should interpret this as kind of an obvious proof that one is infeasible or conversely if you want。

All right， so this is the easy part。 And this is really just by construction of linear systems。

 Okay so we're not worried about them both being feasible。 That's not going to happen。

What's highly unclear is why it can't be the case that both one and two are infeasible。Okay。

So that's what we have to rule out。 That's what's left to do。How are we going to do that？

So we're going to show。That。If the first one is infeasible。Then the second one is feasible。O。

So that is it's impossible for both to be infeas that will complete the proof。Okay。

And one way to think about this is that， okay， so we asked the question。

 how would you prove to somebody the in peaceibility of a system of linear equations and non negativity constraints。

 you just exhibit the suitable row multiplier。But then you can ask the question is like， okay， well。

 is that good enough， or are therere going to be infeasible linear systems where you can't find such a proof of infeasibility。

 So what we're asserting right now， what this is really saying is that whenever this is infeasible。

 you are guaranteed to have a proof in the form of a Y which verifies its infeasibility。

And I hope phrase this way， the parallel with strong LP duality is very clear。 Okay。

 so what are dues， They upper bounds on the optimal objective function value of the primal。

 What strong Lp duality， It says you don't need any better upper bounds。 Okay。

 Du solutions are always good enough。 They always prove the best possible， tightest upper bound here。

We're not really talking about optimizing， but it's a feasibility version of the same thing。

 Okay So the primal， how do you it's infeasible。You look at these particular types of proofs， again。

 with multipliers on the rows， and the guarantee is that there always exists whenever it's infeasible。

 there always exists a proof of this form。So it's very much in the spirit of strong LP duality。

Just a feasibility version of it。Okay。Surely。This is going to bit tough， al right。Let's do this。Okay。

So。Assume one is infeasible。What are we tasked with？We got to find a why。So if one'st feasible。

 we want to prove two is feasible， we've got to find a why。Where are we going to get a why？

We're going to get a Y from the separating hyperplane。All right。

 so to apply the separating hyperplane theorem。We need a close Con set and we need a point not in the set。

So here's a nice definition of a set that's going to work really well for us。So， define Q。

Let me write this down and then I'll explain it。SoThis is an RM。

So here there's two different ways you should think about Q， that are equivalent ways。

 but they're both useful。So first， we have this constrained matrix A。Okay。Now。

 we have this right hand side B that we care about and it's infeasible。 Okay， but so like。

 let's forget about B for a second， okay。So B by assumptions in feasible。 Let's just say。

 you know which right hand sides D。Would give us a feasible linear system。

 A X equal D and x non negative。 So in other words， what are the options。

 What could we replace B with。To recover feasibility in one。Okay。

 and that's the if you just parse this directly， that's how you shouldn't understand this。 right。

 So it's all D so that there's a solution and x non negative A X equald D， right。

That's the first way to think about Q。Here's the second way to think about Q。Okay。

 so which Ds are feasible。 Actually， if you think about it。

 it's easy to figure out which D's you're going to get， right， namely。

Range over all non negative x's。 So now I'm going to hide D。Forget about D for a second。

Range over all non negative x's and look at all the induced Ax's， all the induced。Right hand side。

That's going to give me all of the D's of this form。Okay。So in other words， to each non negative x。

 there is a corresponding right hand side for which it is feasible。

 namely the right hand side D equal to A X。 so each choice of non negative xs gives me a D。Alright。

Okay， so what is that， So what is A X with x non negative， That's just a linear combination。Sorry。

 a non negative linear combination of the columns of a。Right。

So ranging over all non negative x's and looking at AX just says look at all non negative linear combinations of the columns of a。

 that's also called sometimes the cone generated by the columns of a。Okay。All right， so that's Q。

 So again， to apply the separating hyperplane theorem， we also need a point not in the set。

So what's our point not in this set？B， exactly。 So remember， this is all the right hand sides。

 which we actually are feasible。 And by assumption， we're not feasible for B。So， B。

Does not belong to Q。Okay。So that's good。Also note， so to apply the separating hyperplane theorem。

Q has to be conx en closedsed。It's convex just because of equations and inequalities and taking the intersection。

 that's going to be a close set。And also， if you think about it a little bit。

You see the Q is convex and either you can think about this because it's because it's the intersection of conx sets。

 So sort of aine spaces and inequalities and half spaces。 or remember what does it mean to be convex。

 it means if you take two points in the set and you take the midpoint that's still in the set。

What are Q， Q or non negative linear combinations of the columns of A。

 if you take one non negative linear combination and another non negative linear combination and you average them。

 you get another non negative linear combination of A or the columns of A。Okay。

So there should be no mystery about QB and convex either。

So the separating hyperplane theorem applies。Okay so Q is R C， B is ourz。And then what do we get。

 we get an alpha and a beta so that these two things are true。Okay。

So by separating hyperplane theorem。There is alpha。In Rm。Beta in R。Such that。ち。

Alpha transpoposedse D is at least beta for all D and Q， so for all feasible right hand sides。

 alpha transpose D is at least beta， but for our infeasible right hand side。

Alpha transpose B is less than beta。So I haven't anything fancy。 I've literally just。Over here。

 we were just verifying the hypotheses of the separation hyperplan separating hyperplan theorem。

 We just applied a black box。 And by the statement of that separating hyperplane theorem。

 werere assured。Of such an alpha and beta。All right， so just a quick simplification。

 and I'll ask you to justify this。 So I' make sure I set five。Without loss of generality。

 we can take beta equals zero。Okay。In general， in the separating hyperplane theorem。

 beta is just some real number。But if you think about it for a little bit， you realize， oh。

 because Q is a cone。And close under multiplication by positive scalers， actually。

We're basically going to need to take beta equal to 0， but it's not obvious。

 I'm going to ask you to think about that outside of class。So we get the beta is equal to0。

 and then we have some vector alpha so that this is true。Now， compared to what we're looking for。

 what are were trying to do， We're trying to exhibit a feasible solution to this linear system。

 We're trying to exhibit a Y。What are the two properties why' supposed to have。

 why transpose this infeasible right hand side B supposed to be negative。Well， that's kind of good。

 right？So if we identify alpha。Sor of the normal vector of the separating hyperplan。

 we identify alpha。With why。Then this holds。Okay。So if we're so lucky that alpha also satisfies this。

 then we're done。Okay，So what is the feasible solution to the second system。

 It is the normal vector to the separating hyperplane between the infeasible right hand side and all of the feasible right hand side。

All right， so to check， so need to check， and then we're done。You need to check that alpha transpose。

A。There's not negative。O。All right， but let's just remember what this is。So A is n by n。

Right so we're now doing。A linear combination of the rows of a。O。So this is going to be an n vector。

Indexed by the decision variables。So just vector matrix multiplication。

This is Al transpose dot product with the。First column of a。

All the way up to Al transposes an's column of it。So this is a M vector。Okay。No， sorry。Andventor。

So what are we trying to prove， we're trying to prove that every one of these coordinates is non negative。

If we can do that， we're done， we can plug an alpha as y and we're all set。So here's the clam。

First column of A。Totally in queue。Do you see why？But what was one of the ways to think about Q。

 One of the ways as the feasible right hand sides。 But we have a second way。

Non negative linear combinations of the columns of A。Well， column one。

 definitely a negative linear combination of the columns of a。Same thing for all of the columns。

Every column is a special case of a negative linear combination of columns of a。

What do we know about everything in Q， what the separating hyper planee tells us indeed？

All of the columns of A then have to be on the other side of the hyperplane。这。

So this is not negative by virtue of the first column being in Q and the separating hyperplan guarantee。

All the way up。嗯。So that's Fararca's limit。Any questions？See you Thursday。

