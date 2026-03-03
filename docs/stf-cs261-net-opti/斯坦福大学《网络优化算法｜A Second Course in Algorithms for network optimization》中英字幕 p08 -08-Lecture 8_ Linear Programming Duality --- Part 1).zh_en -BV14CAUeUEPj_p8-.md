# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p08 -08-Lecture 8_ Linear Programming Duality --- Part 1).zh_en -BV14CAUeUEPj_p8-

Okay。So just a quick reminder to recap of where we left off on Tuesday。

 so Tuesday we introduced linear programs and so we talked about a language for encoding problems as linear programs we did a toy example we also did many real examples max flow Min cause flow fitting a line learning linear classifiers gives the toy example from last time actually I tweaked it a little bit last time this four was a two and this two was a one I wanted to break symmetry so I modified it slightly。

 but the picture is almost the same I really just took one of the constraints and kind of lifted it up a little bit。

And so this intersection of four/ half planes， you want to find the best point， what's best。

 maximize the sum of the two coordinates just like on Tuesday that corresponds to moving northeast as far as possible。

 and so here last time it was one excuse， one third。

 one third with the tweaks constraint the new optimals， 37，27s so you can check that this point37。

27 satisfies both of these constraints with a and it achieves a objective function value of57s okay。

And so in general what is a linear program what's the recipe well there are decision variables like here x1 and x2 there are linear constraints。

 linear meaning the decision variable can't be multiplied against everything anything else nor can you apply any nonlinearar function to it you can just multiply it by a constant and then add up a bunch of those terms the constraints are allowed to be either inequalities or equalities。

 remember that was one of the points of linear programs if you only have equalities you can use Gaian elimination to look for solutions but lots of problems like all of the ones we saw on Tuesday naturally have inequalities so those are also allowed okay。

So any questions about that， Any questions about。Where we left off on Tuesday。

So the plan for today is we're going to start talking about linear programming duality。

 so last lecture， oh question。I mean excellent plus。Going in the direction of the vector 11。

Does seemed like I could draw a different graph。Does not have rights in which that is not。

Just dont have lunchca。So I would again think about the level sets of the objective function。Well。

 so if you prefer， think about it this way， think about。The subset of solutions。

 just think about the subset of the plane that has a given value of x1 plus x2 like x1 plus x2 equals 1。

Okay， so that's going to be a line 45 degree angle going from southwest to south sorry northwest to southeast so I just look at so basically the plane gets chopped up into these parallel lines。

 each one corresponding to a particular objective function value and the objective function value is getting bigger as I go northeast。

So it's almost just。You， I mean， whether you I mean。

 we're really just trying to maximize the dot product of， you know， x1 comma x2 with the vector 1。

 comma 1 So that's just the definition。 What is x1， Think of x1 plus x2。As。11 dot product， X1 x2。

It's the same thing，Okay。Okay。Good。So the topic for today's lecture is linear programming duality and LP duality honestly it's really the heart and soul of this entire course of CS261 we'll talk about it all lecture today。

 we'll talk about it some more on Tuesday I want to spend some quality time with LP duality so that you have a sense to really kind of absorb it at more than just a superficial level and at some point it'll be clear that actually all of the last three weeks I was also teaching you about LP duality that won't be obvious immediately but it'll become somewhat clearer through the lecture today。

So to start the story， let's just look at this toy example。So we solved it by inspection。

 right it's just in the plane and it's a simple one。 So we just said， oh。

 let's move as farest way as possible， that's the right point。

 But you know as we scale the number of decision variables， the number of dimensions。

 we're not just going to be able to eyeball some picture。

 So how can we get a handle on what the optimalum might be。And so， you know。

 stopping shy of actually computing it， let's actually just think about how would we convince somebody so given a feasible solution。

 what would convince you that it actually is an optimal solution。

 just like when we talked about flows， what we convince you that a flow is actually maximum。

 when we convince you that a matching is actually a maximum cardinality or minimum cost。

So let's think about this。 Let's suppose we didn't know what the optimum was。

 we were just staring at this linear program。 We wanted to understand upper bounds on how big the optimal solution could possibly be。

So。So one kind of very trivial ever bound to be an ever bound of two。How can we derive that？Well。

 if you have a feasible point。Okay， x1 x2， so feasible meaning satisfying all four of these inequalities。

And we look at the objective function value。IEX1 plus x2。Well， certainly that's。

Bounded above by 4 x1 plus x2。Actually， I'm using something here。What am I using？

X1 is non negative so if x1 was negative， this would be wrong。

 but with x1 non negative a bigger coefficiently makes it a bigger quantity。

And so this is by the first constraint。😊，And now using the third constraint。

 just sort of by definition of feasible。We find that it can't be bigger than two。Okay。

So this guys kind of an obvious argument about whatever the optimal solution in this linear your program is。

 it's not going to be bigger than two。Okay， everyone clear。

So hopefully you found that sort of trivial。Actually， if you think about it， this was really stupid。

 It'd bed better to use the last constraint instead。That gives us another round of one。

On the optimal solution。So this is a tighter upper bound， better upper bound。

 this is a stronger statement than the last one。But actually， if you think about it。

 there's no reason to just use a single constraint to derive upper bounds on the optimal solution。

 We should feel free to blend them as it suits our purposes。So to see what I mean。

Notice that I can write X1 x2 as a convex combination of the two constraints。So I take one seventh。

Time's 4 x1 plus x2。Plus37s。Times x1 plus 2 x1。This holds with a quality。Okay， it's just algebra。

I actually only need an inequality， like in the first two cases， but I happen to have equality。

So again， this is just algebra。And now because assuming the next one and next two is feasible。

By the third constraint， we know this number cannot be bigger than two。No matter what。

By the last constraint。And feasibility， we know this cannot be bigger than one。

So that gives us an upper bound on five/ sevenths。Okay。So this。

 you should find a quick and convincing proof that whatever the optimal solution to this linear programming is。

 the objective function value is definitely not bigger than5/7s。Okay。All right。

Now in this particular case， we actually know this is a tight upper bound because we know there's a feasible solution to this linear program。

3/7s，27s that actually does attain this upper bound that actually has objective function value as high as five/7s。

 so clearly we're not going to prove any better upper bound this is the best as it gets。

So any questions about that？All right。So that's more or less duality in a nutshell。

But so let me develop it more generally。 right， So if you think about it， you know。

 nothing about this argument uses the fact that we're in the plane。

Or uses the fact that there's only a very small number of constraints。 We're just saying， oh。

 if you can just use suitable linear combinations of constraints to derive upper bounds on the optimal objective function value。

 So what does that look like in general。 Here's what it looks like in general。

So suppose we have not just。Two decision variables and four constraints， but an arbitrary number。

So consider linear a program of the following form。

 and I'll call this P for reasons that will become obvious。

So maximize a linear combination of decision variables， decision variables are x1 through xn。

Then we have our linear constraints。I show you for one to end。And so let me just go with。

 for the moment， linear programs that have the same form as the one up there where we're maximizing we have inequalities and we have non negativity constraints。

 Okay， we'll talk about other forms in a second。So that's what one linear constraint looks like in general。

 we have M of them。And then again， let's。Think about scenarios where all of the decision variables have to be non negative。

Okay。Now， we talked a little bit on Tuesday about how， you know。

 there's a lot of different forms of linear programs， but they're all equivalent。

 It's easy to go back between one and another。 If you have a minimization linear program。

 you can just multiply the objective coefficients by -1 to turn it into maximization。

 If you have inequalities going the opposite direction， you can flip them by multiplying by -1。

 And if you have equations， you can simulate those with two inequalities。 going both directions。

 So there's a sense in which it's basically without loss of generality to talk about this form。

 But still I'll talk about other forms a little bit later。

So suppose I want so now right so just in this generality。

 there's no way to eyeball anything and just sort of deduce what the optimal solution is。

 So let's again take a step back and say， well what if we at least wanted to just convince ourselves of legitimate upper bounds on what the optimal solution could be？

Okay。So let's just follow the， the previous approach。So suppose。All right。

 so what were we doing in these arguments okay？We were taking a multiple of the first constraint。

 plus a multiple of the second constraint。 and we were playing around with what multiples we should use。

So we're going to have y1 through YM， these are just going to be those multipliers on the constraints。

 so because there's M constraints。There's going to be M multipliers。

So suppose you have non negative multipliers that satisfy。

So what was really driving the argument here right so let's look at those first inequalities。

 what was important was that your convex combination dominated the objective function coefficient by coefficient so four and one or at least one in one。

 one and two are at least one in one， that's what we need。So in general。

 what does it mean that your linear combinations dominate the objective， dominate the CJs？Well。

 what it means。Is that for every coefficient of the objective function， of which there's n。

So for all， I equal j equal 1 up to n。It should be the case that if I look at the coefficient that I get on a given decision variable。

 which in general。He's written like this。This should dominate。That coefficient of the objective。Okay。

It'sre going to call this star。So for example。In the first argument of there。We took y1 equal to 1。

And y2 equal to zero。Okay。And it was the case that， for example， for the first decision variable。

 four was bigger than one。And in the second decision variable， one was bigger than one。

In the second argument， we took y1 equal to zero。And y2 equal to one。Okay。And again。

 this was satisfying。And then the final argument， we took y1 equal to y2 equal to 3/7。

 and actually this round of holding with a equality for both j equal 1 and 2 in that case。All right。

So suppose this is true。From this， we can extract an upper bound on how big the optimal solution to our linear program could possibly be。

And it's just a generalization of this argument here。

So suppose why our non negative and satisfied star？And for all feasible solutions。

 X to our linear program P。We can write， we can write the following。

This is the objective function value of x。 By definition。 Remember。

 we want an upper bound on the optimal objective function value。

 So I'm taking your favorite feasible solution and an upper bound。 It objective function value。

 Here it is。Okay。So now we just follow our nose。 right？ So what do we know。

 What do these y's satisfy？ Well， if we take the non negative linear combination of the constraints as specified by the Y's。

 it dominates the C's。 It's at least as big as the C's。So what that means。And again。

 this is just corresponding to these two lines here。It means I can replace CJ。

By the left hand side of star。That's what star means。 Again。

 I'm using here that each of the x's is non negative。

 So boosting its coefficient only gives me a bigger number。So CJ times sum。

Over I equals 1 to M Y AIJ。Okay。6。 good。Oh。Sorry with that？Okay， so this is star。Plus。

 x non negative。All right， so whenever you have just the general rule。

 whenever you have a double summation and you don't know how to interpret。

 just reverse the order of summation and see if you get something you can make use of。

So we'll do that here， so instead of summing over Jan then I， we sum over I。And then J。

 so let's yank out the part that doesn't depend on J。

So we get a y high there and then a sum over j equal 1 to n。Of AIJ Xj。Okay。

 so that's just algebra rearranging。Well， this is something we know something about。

X is a feasible solution that satisfies every constraint of the linear program P in particular。

This linear combination has to be at most peace subby。Okay， by feasibility。

And so this is using that x is feasible， and we're again using non negativity this time that the y's are non negative。

Okay。So that is the natural generalization of these simple upper bounds for our toy example。

And so again， what is the upshot？The upshot is that for all y， again these are M vectors。

Such that star holds。The optimal solution， the optimal objective function value of our linear program is bounded above。

By the dot product of B with I。Okay。And so if you think about it， you know。

 this right hand side is exactly the upper bounds we were getting on our 20 example when we took。

 so maybe you don't remember， but so B1 was two， B2 was one。

 right the right hand side of linear program was two and then one。

So when we took y1 equal to 1 y2 equals 0， we got an upper bound of 2， when we talk y1 equal to 0。

 y2 equal to 1， we got upper bound of 1， and then the smarter combination， this became57s。Now。

In my experience， by the time computer science students make it to my classes。

 they've totally forgotten any linear algebra they may have once known。

I don't know how many of you that applies to， but when you're talking about linear programming and duality。

 it's really helpful to also be able to think of linear programs in terms of matrices and vectors Okay so let me just point out what's the vector slash matrix version of everything we wrote on the board。

RightSo for our initial linear program， we can think of the objective function as maximizing C transpose X here。

 C and X are both n vectors。 So we're just taking the dock product of the inner product of two n vectors。

The system of linear inequalities。We might write succinctly。As AX and most B。So what does this mean？

So x here， as you know， is an n vector。A， so the rows of capital A correspond to the constraints。

 so the first row of A are just the coefficients A1 j for all J。So there's M constraints。

 so a has M rows and then there's n columns in one to one correspondence with the variables。

 and then B here is going to be an M vector， notice that there are M entries one for each constraints。

So this is an n vector。That's an n vector， and A is M by n。嗯。Non negativity。

 we might write succinctly by x non negative。Notice these inequalities， they refer to vectors。

 so we always mean it's point wise component by component， one should be at most the other。

So similarly， when we talked about our negative linear combinations of the constraints of this linear program。

We're talking about vectors Y now of length M because they're in one to one correspondence with the constraints。

 one multiplier per constraint。And。How will you write this， this is a little tricky。

So clearly we're writing at least C on the right hand side。

And presumably there should be a capital A and there should be a Y。So what is that exactly？Good。

As many of you said， a transpose Y。Y a transpose， well here we're looking at the dot product of x with rows of the matrix。

 If you think about each of these left hand sides， it's the dot product of x and a row of the matrix。

If you stare at this and you realize you're summing over I rather than J， oh。

 now you're taking the dot products of y with columns of the matrix。 which actually。

 if you think about it， it makes for things to type check that has to be true， right。

 because y is an M vector。A is M rows by n columns。

 So you better be dot prodding Y with columns of capital A。 That's all that would make sense。

 So that's the same thing as just doing a transpose Y。This derivation， I think。

 actually looks somewhat less obscure when you switch to this vector matrix notation。

All we're saying here is that C transpose x。Is it most？A transpose y transpose C。

So this is using that C is dominated component by component by a transpose y。

 remember that's just our conditioned star。This reversal of summations is really just distributing the transpose and then using associivity。

So this is equal to y transpose parentheses， Ax。I screwed this up again， didn't I， sorry about that。

Should be x。Ax。And then the final step is just using that B dominates AX component by component and y is non negative。

So this is a most wide transpo be。Okay。So that's why you should get familiar with or sort of just page back in you know matrix vector multiplication because you can replace this messy board of sums with just actually a very elegant derivation in terms of the matrices and the vectors。

 which I think is much more transparent。Okay。But again， this is the upshot。

 so if you ever have a non negative vector y， such that a transpose y is at least C。

 So these linear combinations dominate the coefficients。

 then you extract from it an upper bound on how big the optimal solution could possibly be。

 What is that upper bound。 It is just the right hand side B that vector transpose with your non- negative linear combination coefficients sort of dot product with a Y。

这。So any questions about that， that derivation？So this is a generic way of proving to you that the optimal solution of a linear program cannot be too big。

Okay。Now， you know， if you recall our toy example， we had some upper bounds initially。

 and they kind of sucked。 actually， right， there were much better upper bounds than the first ones we trot。

 So some of these upper bounds are going to be good or some of the upper bounds are not going to be good。

 Hopefully， some of them will be good。Now， from our perspective。

 which upper bound are we most interested in？Well， obviously， the tightest upper bound， right。

 We want the strongest information possible about how big our linear program solution could be。

 So amongst。All upper bounds， you can derive in this way by choosing multipliers wise。

 subject to the constraints。 among all of those， really the one we're interested in is the one that gives us the tightest upper bound I。

e。 that makes this right hand side as small as possible。Okay。

 that is the most interesting upper bound。 This being as small as possible。So here's the key point。

The tightest upper bound of this type。If I have this type。

 I mean you choose non negative Y's subject to star。The tightest upper bound of this type is itself。

A linear program。Sure。What does the linearium program look like just we should have already know this。

 but just to make sure make it concrete。You sum。BIYI。

 why do you minimize this Because this is our upper bound。 The best ever bound is the smallest one。

 We're searching for the best， so we're searching for the smallest。Subject two。

So we had Y1 through YM。Not negative， and then we have star。Okay。So let me just actually write star。

Because hopefully it's evident， you know？These are linear constraints。So this is called the duel。

Llenning your program。Okay， so D。And again， in matrix notation， what is this？

You want to minimize Y do B transpose y。Subject to A transpose y dominates C。And why non negative？

Okay。So to review。Consider any linear program of the form on the upper left， max C transpose x。

 subject to AX at most B and x non negative。Every linear program of that form has what's called a dual linear program。

What the dual linear program is is it minimizes B transpose y， subject to a transpose y at least C。

 nonne linear combinations to dominate the original objective， and again y non negative。Okay。

So constraints and variables have reversed roles， the right hand side has become the objective and vice versa。

And the constraint matrix gets transposed。So this is the dual LP。Of linear program of this form。

And by construction。By construction。The optimal objective function value of P。

Of the so called primal linear program in the upper left。

Is it most the optimal objective function value。Of the duel。Why。By definition。What is the dual。

 what does it mean， Feas solutions to the dual linear your program correspond to valid upper bounds on the best possible objective of the primal。

That is， every feasible dual solution gives you an upper bound on the value of every primal feasible solution。

So that's true in particular， for the best of all of the dues and the best of all of the primal solutions。

Okay。So we don't know whether this holds with the quality or not， but just by construction。

 but the definition of the dual linear program， it will always be the case that the objective function value of the minimization program is at least that of the maximization part of the primal dual pairer。

So just as a sanity check。For our toy example。The due is going to be minimized。2 y1。Plus y2。

I guess I eraed the original one So the original one was。Max X1 plus x2， subject2，4， x1。

Plus x2 and most 2， x1， plus 2， x2 and most1， x1， x2 non negative。So what's the duall？Well。

 the objective function of the dual corresponds to the right hand side of the primal。

 So the right hand side here is two comma 1。 So we see the two comma1 in the objective function here。

So for the same， okay， so we also know this is going to be a greater than or equal to right A transpose y is at least C component wise。

So the right hand side of the dual is going to be the objective。From the primal。

 so the objective function coefficients here are1 comma 1。So we're expecting two constraints。

That both have one on the right hand side。Okay。So over here， we're going to have some y1s and Y2s。

 We need to understand what their coefficients are。

 Their coefficients are provided by the transpose of the original constraint matrix。

So the coefficients here are going to correspond to the coefficients of x1 in the two constraints so this is the first column in A in the original constraint matrix that's going to become the first row in the duall。

Okay。Sorry there， so it's going to be this four in this one， excuse me。

So 4 y1 plus y2 is at least one because the coefficients of x1 are 4 and 1。

 the coefficients of x2 are 1 and 2。So that's going to give us coefficients one and two here。Okay。

And then we'll have y1 and y2 non negative。Okay。So this is just saying all of the simple upper bounds of the type that we discussed for this particular linear program。

We， in fact， solved it optimally。Because we exhibited a solution to this linear program with value 5/7。

 that was three/ seventh， comma two7s， we also exhibited a feasible solution to this linear program。

With value57， that was1/7 comma3/7。And we know， remember。The optimal solution here。

Can only be bigger than the optimalim solution here。

So I exhibited for you a feasible solution of each so that both have value5， sevenths。

 both of them have to be optimal。So nothing can be higher than five/7s is the prim mo。

 because that would contradict the fact that we have a dual solution with value  five/7s and conversely。

All right， so questions about that next up is an example。

 so I want to make this a little more concrete by applying it to maximum flow。あ。Questions。Yeah。Mh。

Is the far so good？All right， so。I've tried to make this somewhat concrete with our toy example。

 but let's actually apply this theory to a kind of real example。And see what we learn。

So I want to return to the maximum flow problem。Now on Tuesday。

 we observed that the maximum flow problem really by definition。

 translates easily to a linear program with constraints corresponding to conservation and capacity constraints。

Today I'm actually going to work with a different linear program than the one I showed you Tuesday。

 the linear program is going to be bigger， but it's going to be simpler and therefore it'll be easier to take the due。

The idea is rather than working with just flows on edges。

 we're going to work explicitly with a path decomposition with flows on paths。So alternative LP。

So before we had a decision variable for each edge。

 now we're going to have a decision variable for every ST path。もしもしかす。Okay。

So we're going to decision variables indexed by the set script P， indexed by ST paths。Now， mind you。

 a graph can have an awful lot。Of S T paths， an exponential number， in fact。

 But we're not going to solve this linear program。 We're not going to feed it into a linear programming solver。

 We're just going to use this as a thought experiment。 We're going to use it for analysis only， okay。

All right。So what do we do， so we just want to send as much flow as possible。

So we enumerate over every possible ST path flow could be sent on we look at how much flow FP is sent on that particular path。

 and we sum up over all the paths， so that's the flow value。

And now what's nice about this path formulation is conservation constraints are just handled automatically because if you have a path。

 conservation constraints are satisfied。 if you superimpose a bunchs， you still have conservation。

I still do need the capacity constraints， though I still have to encode that。

So we're going to have it most capacity。For every edge， shouldn't be surprised to see that。

So what goes on the left hand side？Well， it should be that the total amount of flow on E E。

 no matter how it got there should be at most the capacity so a given edge is part of many different ST paths in general。

 so we have to nuerate over all the ST paths that include this edge and make sure their total flow obeys the capacity constraint。

So we write some over all paths， ST paths。For which this particular edge E belongs to it。Okay。

 so this is just the。Total flow on E。And then of course， flow should be non negative。Okay。

I hope it's at least plausible that this is for all practical purposes a central equivalent LP formulation to what we had Tuesday。

 So in exercise set number 4， I ask you to think about that carefully。

 that the optimal solution is exactly the same value for either of the two linear programs that we've seen okay。

And again， the idea is really here we're just working with path decompositions in the sense of problem one。

 which you just completed instead of with the flows on edges themselves。

So what I want to do next is I want to apply。 I want to see what the dual linear program is to this linear program。

 Notice this is in the form that we've been talking about right we're maximizing C transpose X wherere。

So let me actually write this out。So we're maximizing。C transpose X。

 but let me write that as one transpose F。 So F will be the variables here。

 Notice every variable is coefficient one in the objective。 So this is just the vector of all ones。

And the constraints have the form。AF and most U。Tk about what capital A is in a second。

 but their inequality constraints going in the right direction。

 and then we have non negative variables。Okay。So this is exactly the type of linear program that we've been talking about this lecture。

 so we know how to take the duel。Now， often the hardest thing about taking dues or at least understanding what you're actually doing when you're taking dues is just actually understanding the meaning of transposing the constraint matrix。

That's usually what's kind of。You know， initially unclear。

 but then you think about it a little while and you're like， oh， okay。

 now I get what this dual is doing。So let me show you， just for example。In this particular program。

So what is this matrix capital A？The constraint matrix here。So what do the rows correspond to。

 remember rows correspond to constraints， So we have one row per what？Per edge。

 You have these capacity constraints， one per edge。 So the rows here。Are indexed by edges。

What are the columns indexed by？So the columns are so the rows are correspond to constraints。

 the columns correspond to decision variables。 We have a decision variable for each path。Okay。

So those are the dimensions of our constraint matrix。What is an entry of the constraint matrix， Well。

 the constrained matrix entries are just the coefficients of your decision variables in your constraints。

We've got actually quite simple constraints。 O， In fact。

 each entry of capital A can take on only one of two values。Zero。Or one。

Whenever a decision variable appears， it's with a coefficient of one。And so when does that happen？

Wops， I shouldn't， not AIJ， Let me write AEP。so the row corresponding to E。

 the column corresponding to P。When is this going to be equal to one？

For which pairs of edges and paths will the corresponding entry of this constrained matrix be1？Yeah。

 he is on Pete， exactly。Why is that true we'll fix a row？So what we're asking is。

 let's fix a row how many of the decision， which decision variables actually show up in this particular constraint。

 So anything that doesn't show up has a 0， anything which does show up has a  one。

The things which shows up are just the path that contain this particular edge。

So as we go through a row here， we get a zero whenever the path doesn't have the edge。

 we get a one whenever the path does have the edge because those are the variables that appear。

Alright。Questions about that。If you get that， then we're ready to take and interpret the duel。

Alright。So， dual。So what's the recipe？Well， for each constraint of the primal linear program。

 we have a variable in the dual， multipliers for the constraints。

So rather than y I'm going to call them L， I'll explain why in a second。So one variable， L。

For each edge。 so one dual variable for each constraint。And again。

 I think the easiest thing to do here is to actually take the duall using the matrix notation and then sort of unpack what it means as far as。

 you know。More primitive objects。So。We have a max over here that becomes a min。

The new objective function is the old right hand side。So it's going to be minimized。

 so the dual  variabless are L， so L transpose U。The constraint matrix gets transposed。

 this is an a transpose L。The new right hand side is the old objective function。

So this is going to be at least one component wise， and then we have non negativity constraints。

So is everyone cool with what I did on the matrix side？

So this is exactly the recipe that I told you before。All right。

 so let's unpack this in terms of edges and paths and so on。

So minute now transpose you remember the dual variables are indexed by edges。

 so this is going to be a sum over the edges。Of the capacity of the edge， this is fixed。

 this is a constant。Times the dual variable， LCB。So that's the objective。

Obviously down here we have the L's are9 negative。So let's try to understand what this means。 Okay。

 so first， just let's make sure we get it type checked correctly。 So in the dual。

 we're going to have one constraint for each primal that we had。

' for each decision variable that we had in the primal。So in the primal。

 we have a decision variable for every ST path， so over here we're going to have a constraintsstraint for every ST path。

So let me write。For all。ST paths， P&P。So we're going have a family of constraints indexed by the path。

We know。That they're going to be greater than or equal to constraints。

And we know that the right hand side is one。So the question then is。

 what does it mean to talk about a particular constraint of a transpose， what does this look like。

 Okay， so we want to know what the rows of a transpose look like or equivalently。

 what do the columns of a look like？So let's go back to A。So what's a column。

 so column is some fixed path P。So now imagine we just scan up a particular column。 Okay。

 so the path is fixed。 We're now scanning over the edges。

 Okay remember the rows are indexed by edges。We see a zero whenever the edge that we're looking at is not part of this path。

 We see a one for any row where that edge is part of this path。So in other words。

 the column corresponding to the path P is just the characteristic vector of the edges in the path。

One fridges in the path is zero fors out of the path。Okay。So that's the column of a。

 that's the row corresponding to constraint of a transpose in the duall。

So what does it mean to take the inner product of a column of capital A with L？Well。

 for any edges not in the path， they have a coefficient of zero， so they disappear。

And then the other ones have a coefficient of one。So what we get here is just some。

Over the edges in this fixed path pe。Of ElciB。Okay。So that is the due。

Of this Max flow linearar program。Any questions about that？Next， I mean。

 it's not supposed to have meaning for you yet。 I'm going to give you that next。

But are you okay with just the syntactic transformation。

 Do you agree this conforms to what I told you before？All right。So one cool thing。Is that？

Natural problems， when you take their duels， you often get something which is meaningful in its own right。

 And that turns out to be the case with maximum flow as well。So。How should you think about this duel？

Well， so one way I just kind of if you want sort of a physical interpretation。The decision variables。

 I call them L， or why did I call them L， I did that to suggest that there're sort of like a length。

So we're actually computing lengths for the edges。Of this graph。With that interpretation。

There's a very succinct description of these constraints。Do you see what it is？

So if this inequality holds for every path。Then it also holds for the shortest path。

With respect to these edge links that we computed。打开。

So this constraint boils down to saying compute non negative lengths on the edges so that。

If you compute a shortest path， it's going to have length at least one。So that's what you're doing。

Somehow you're pushing S&T sufficiently far apart， shortest path distance， at least one apart。

So that's a physical interpretation of the constraints。 So then what's sort of up with the objective。

 Well， if you like， think about a capacity as the width of a pipe。Okay， so on the objective。You pay。

Proportal to these products of the width， the capacity times the length with which you build the pipe。

And so the objective is sort of like minimizing the volume of this network subject to S&T being sufficiently far apart。

So that's the first thing to say。But so now actually， let's think about cuts。

So when back when we were talking about max flows， it sure seemed like cuts mattered a lot。

So let's observe that there's a connection between ST cuts and this dual linear your program。

So fix your favorite ST cut A comma B。 So remember the source should belong to A。

 the sync should belong to B， A and B partition the vertex set。So as usual。We have our。

Four categories of edges。Those that go forward， those that go back and those that go internal。Sure。

What I'm going to do is I'm going to show you how to take a cut。And from it， extract。

A feasible solution to that dual in your program。So that the objective function value of that solution equals the capacity of the cut that we started with。

So this linear program is actually encoding in it all of the ST cuts of the graph along with their capacities。

Okay， so you gave me the cut， I'm going to give you back a feasible solution to the dual。

 how do I do it？Well， linear programs allow you to assign fractional values。

 but I'm not going to bother。 I'm just going to use ones and zeros。And I'm going to do one。

For all edges sticking out of the cut。so for all edges and Dlta plus of a。Remember。

 Dlta plus of a or the edge is sticking out， okay so the tail is an A， the head is outside today。So。

I claim that no matter which cut you gave me， the result is going to be a feasible solution to the dual linear program。

Do you see why？So if all the links are either zero or1。What do these constraints say。

 These constraints say that for every single S T path。

It better be the case that one of the edges it contains is one of the one edges。

 you cannot have a path which is all zero edges。But if you gave me an ST cut。

And I put one on every edge that goes from A to B。There's not going to be any ST path going from S to T that doesn't cross this cut。

Okay， so by putting a one everywhere across a cut going from left to right。

 I actually put a one in every single SD path。So that's why it's feasible。

What's the objective function？Well， let's just plug in。So all the zeros drop out。

 we're left with just the one edges， and those are the edges sticking out of the source side of the cut。

LE here is one， so I just get the capacity。This is certainly a quantity you're familiar with。

This is just the capacity。Of a comma B。So from every ST cut。

 I can extract a feasible solution to the dual with objective function value。Exactly the same。

 equal to the capacity of the cut。Yeah。So let's put this together。So what we learned？

So we have our flow network。We can think about the value of the maximum flow， whatever it is。

We argued around exercise set four， you'll argue。That the optimal solution to our linear program is exactly the max flow value。

So this is just because we have an LP formulation。Let me stack these under each other。

Do do it this way。This is the most， the optimal solution。Of the dual linear program。Why， remember。

 this is the meaning of a duel。Okay， every feasible solution to the dual provides an upper bound on the best possible object function value in the primal。

So it's what we said was by construction。 Okay， this is also known as weak duality。

 Okay The point is by definition of a duel， this holds。Finally。Only bigger than this。

Is the min cut value？嗯。So why is this true？Why can this quantity only be bigger than this quantity？

Well， think about this dual linear program。It's minimizing。

It's trying to make something as small as possible。

Cuts correspond to a special case of the feasible solutions of the dual linear program。

The min cut value is the best objective function of one of these special types of feasible solutions。

The dual Line program can optimize over all feasible solutions， not just those corresponding to cuts。

 since it's minimizing over a bigger set， it can only come up with a smaller number。

So the dual linear programming optimal solution is not going to be any bigger than the min cut value。

Okay。Has everyone with me so far？Okay， so again， this is weak duality。

 this is because the dual optimizes over a supers set of feasible solutions compared to the cuts。

All right， so cool。 So this says that the value of any flow is upper bounded by the value of any cut。

Okay， we knew that。 We proved that back in lecture 1， maybe lecture 2。 and actually。

You knowNow that we're in lecture at 261 and we're smarter than we were before。

 we know something actually much stronger than this is true， and we even know how to prove it。Okay。

When we prove the correctness of the Ford focus algorithm in lecture2， what do we show。

 we show that the algorithm is guaranteed to terminate， and it will hand you on the one hand of flow。

 on the other hand a cut so that the value of the flow equals the value of the cut。

Proving simultaneously their respective optimality。So Ford Forson tells us for every graph。

 the left hand side is equal to the right hand side。Which means， of course。

 we have throughout this chain of inequalities。Okay。So by max flow， min cut。Ealities hold。So。

 in fact， we can strengthen this to say equal。 We can strengthen this to say equal。Okay。

So you've seen a full proof of all of these facts。So if there's some step which isn't clear。

 let me know。So we use today's machinery， just the definition of a duall。

 to argue the weak direction that the max flow can't be bigger than the in cut。

 and then we're just invoking what we did at the beginning of the class to know that the quality holds。

So why is it interesting that equality holds？Well， there's two reasons， this is interesting。

 each of these is interesting。Let's start with the first one。Okay。

The first one saying that the optimal solution， the Pri mill linearn program actually equals the optimal objective function value of the dual linear your solution。

 why is that interesting？Well， we observe that by definition。Of the dual， we have this inequality。

 The dual optimal can't be any smaller than the primal optimal。

And remember the dual is trying to get the best upper bound of this very limited form where we take these linear combinations of the constraints in the primal。

So that's fine。 The dual is the best possible ever bound。 But the question is。

 how good an upper bound is it Now， in our toy example。

We actually came up with a dual solution with value 57s equal to a primal solution。

 So they both had to be optimal。 But that was just one toy example。 Okay。

 but we proved so calledled strong duality for our toy example that the optimal solutions are equal。

 There is no gap。And so we're interested in understanding when is there no gap？

So that's called strong duality， that'll be the main subject of Tuesday。

But so this first equation is proving a special case of strong duality。It's saying。

 if you consider the linear programs， corresponding Mx flow problems and the corresponding duals for those particular primal dual pairs。

 there is never a gap between the optimal objective function values。 They are always equal。

 never a gap。We'll see that's true for general linear programs。

 but we are now seeing that it's true in a special case， these particular primal dual pairs。

So that's why the first equation is interesting。 It gives us linear programs with no gap between the primal and dual optima。

How about the second equality， Why is this second equality interesting？Well。If you think about it。

 if I told you I was going to solve the ST cut problem。By linear programming。

 it actually doesn't seem to type check。 It seems kind of weird， actually， because what's a cut。

 you make a hard binary decision for each vertex。 Is it on the left。Or is it on the right。 So really。

 it's kind of like you want to assign each vertex to 0 or one。Linear programs， on the other hand。

 by definition， can use fractions。By definition， the variables are just any real number。

 and then you take the intersection with half spaces。

 which maybe sho bring them down into an interval。But they certainly cannot encode integrality constraints into a linear program。

So in general， you have fractions with linear programs。

 so how is it you could solve this linear program with all this fractional stuff and make use of it to compute a cut。

 which doesn't feel fractional at all。So what this first equation， this second equation says。

 it says for this particular linear program。For which cuts are a special case。

 actually fractions aren't helpful。So what is this。

 this says what's the optimal value of this solution if I only use cuts01 solutions。

 this says what's the optimal solution to this linear program if I'm also allowed to use fractions。

And have an equation here says it doesn't matter， or put differently for any fractional solution。

 I can come up with an integer solution， a cut， which is just as good。

So the takeaway here is that while general linear programs have fractions。

 there are some important and natural linear programs where despite the fact in principle you could get fractions。

 there's always an optimal solution， which is 01。Okay。Questions。Yeahep。

be short that the optimal value of。how do we know that the solution accepts the values of。

They set it details in fact。That's a good point， so the question was。嗯。

So certainly I showed you that there exists some solution。Which is 01， namely take the minimum cut。

And run this argument。 so then I'll get a 01 solution whose objective function value equals the min cut value and therefore equals the optimal objective function value for any solution。

I'm not claiming there can't be other equally good fractional solutions。

 but there's always going to be one optimal solution， which is 01。

 and that follows from this argumentment。Other questions。 That's a good question。Yep。have不 that。

The solution has to be at next。Okay， so good question So this is so the question was about extreme points。

 so those are the vertices or the corners of the feasible region and it's definitely true that there always will exist an optimal solution at one of these corners。

 and you're right that for this particular feasible region。

 those corners are going to be 01 you might get like a weirded case tie where kind of there's an entire face。

 a entire side if you like of the feasible region which all has the same objective function value。

 so then if I take something from the middle of the side that will have fractional coordinates。

 But Jo here are right that if you restrict yourself to the corners and every linear programming algorithm you might ever use is going to hand you back a corner。

 hand you back a vertex then it's guaranteed to be 01。Good question。Other questions。

The maximum income。Just absolutely bit。Would that be a reasonable thing to even guess？

That's a good question。You could hope。You could cross your fingers I mean。

 basically whenever you have a problem which you know is polynomial time solvable。

 it's reason to hope that there might be a linear program which solves to01 Okay so once you know it's tractable。

Maybe there's a natural LP， which proves that it's tractable。So， so sort of like if if you saw。

 you know， if you， if you already knew Edmund's carp， for example。

 you could imagine sort of guessing this。 Of course。

 then you know the maximum elementman cut theorem， but you get my point。

 So it's a little bit circular because often you know。In solving and I'll show you more examples。

 in solving these problems， you often wind up kind of proving strong duality for a primal dual pair as a byproduct because that's how you knew you were optimal。

Okay。Good other questions， good questions。Okay。Again。

 just to sort of tie this into the earlier theme。 So I kept asking you over and over again every time we studied a new problem。

 How do we know when we're done， given a perfect matching， how do we know if it's minimum cost。

 given a you know flow， how do we know if it's maximum， And in some sense。

 LP duality is like the ultimate version of the answer to this question of how do we know when we're done。

 Okay So that's sort one way to think about it。All right， so what I want to do next。

 so I've only showed you how to take the duall of one particular type of linear program。

 linear programs， which are at the form max， C transpose X。

 subject to AX at most B and x non negative。There's other forms of linear programs。

 you might have a minimization objective， you might have a quality constraints。

 you might have unconstrained variables that can be negative。Now we've talked through the cases like。

 well， all of these things can be converted to each other。

So if you wanted to take the dual of one of these other types of linear programs。

 you could convert it using those tricks to the form you've already handled and take the due。

 which we know how to do， and that's fine， that's totally legit。

It turns out to be more convenient to just have at least for our purposes， to have a general recipe。

 So no matter what form of a linear program is in， I'm going to tell you the recipe for how you derive the due。

Okay。So here's the recipe for duality。Okay。Suppose you have a primal constraintss。With n variables。

And M constraints。So we know， so just like before， so the first several things I'll say just like before。

In the dualo， there's a multiplier for each constraint。 So there's going to be M decision variables。

Y1 up to YM。And over here， there's going to be one constraint for each of the variables。

 so for each of the coefficients in the objective function。To end constraints。If you have。

So for the moment， let me just focus on maximization linear programs。So as we saw。

 when you take the duel， you exchange the right hand side and the objective。

 and also you flip max to min。This is going to be men。B transpose y。Right hand side equals C。看。

And we know that the constraint matrix。It's transposed。Okay。So all that we already knew。

 so now there's a few little bells and whistles I just want to tell you about again。

 depending on if you have a quality constraints on constrained variables and so on。

So if the I constraints is， well， what do we already handle？Okay， so far。

 we handled less than or equal to constraints。 and we argued that each one of these should give rise to。

A non negative dual variable。My eye。So it's just like what we had before。

If this goes the other direction。Then we're going to get a non positive do variable。

And if this is an equation constraint， then we're going to get an unrestricted random variable。

 meaning sorry， not random variable， decision variable。

 meaning meaning it can take on both positive and negative values。Okay。

So these two we didn't see yet， we'll see you in a second， this one is this is what we saw。

 but this is the rest of the recipe。And then similarly。

Whenever you have a non negative variable over here， so this is like in the case we talked about。

 then we know we're going to get a greater than or equal to constraint right that was the greater than or equal to C that we had on a lecture。

So this is going to be greater than constraint。And then。You can guess what's up with the rest。

So if it's non positive。Then you get less than or equal to constraints， and if it's unrestricted。

 positive or negative， then you get equality constraints。Okay。

So is it clear what I mean by this recipe？So the details are just， you know what happens。

 so the two things which might be different， what happens if that's an equation？

Rather than inequality， then instead of being non negative， this is unrestricted。And if you like。

 you can also flip this inequality， and then you also flip this inequality。

The other issue is what if you don't have a non negativity constraint in the primal。

 and that just means that the inequalities and the dues will be equality constraints。Otherwise。

 the formula is exactly the same。So any questions about that？

So this only defines the dual linear program for maximization problems。

And so we're going to define the dual for a minimization LP。To just be the reverse of this operation。

Okay， so if your prime millennar program actually has a form like one on the right。

 you just follow the arrows in the opposite direction to get it dual。

You'll notice that by definition， if you have a linear program and you take the due and you take the dual again。

 you'll get back to the original linear program。You just fall thearrows to the right。

 then you just follow them right back left So the dual of the due is the original primal。

So something I'm not going to prove， well， I guess one case of this will be on the exercise set。

But so for all of these versions， you have weak duality。So in all cases。

So if you have a maximization primal like we did previously in lecture。

 its optimal objective function value will be in most that of the optimal solution to the dual。

And then flipping it around if you have a minimization duel。

Then its objective is going to be a least optimal objective is at least that of the。

Corresponding duall。Okay。So I showed you the proof， actually I've left the derivation。

 I didn't leave the derivation up， that's too bad。呃。Thatす。Okay。

So we derive this for the one particular form of linear programs， max C transpose X。

 ax and Bx non negative， exactly the same kind of derivation verifies a weak duality for every other linear program of all of these forms。

And again， I mean， this is really just by construction。

The definition of a due in your program is define the way that it is so that week dual holds the dual's meaning。

 so again， it's fine if you want to sort of memorize or write down this recipe and when one is confused and when one doesn't understand a problem。

 it's nice to have this to fall back on and just apply that recipe， it's kind of mechanical。

 it always works。But do not forget the true meaning of the dual linear program。

 which is as a certain form of bounds on the optimal objective function value of the primal in all cases。

 that's the meaning of the dual linear program。And once you realize that that's the meaning。

 weak duality is basically toological。 So was basically by construction， by definition。In fact。

I don't know if your math classes were like my math classes。

 but something the mathematicians seemed to never admit in the courses I took， they would。

Write these definitions on the board as if they like fell from the sky。

 you know as if someone like sat down at their desk and said every open cover has a finite sub cover。

 you know， something like this， that's not how mathematics works where do definitions come from。

 they reverse engineered to give you the right theorems to help you understand things So here you start with weak duality。

 you reverse engineer the definition of a duall so that it is true。All right。So as I mentioned。

 there's this thing called strong duality， which we'll do a proof sketch of on Tuesday。

 which just says that there's never a gap that these inequalities always hold with equality。

But actually even just knowing weak duality， which at this point we've proved。

 has some really interesting coroll areas。So quarollary1。

Suppose the prim linearar program has unbounded objective function value。

 That is for a maximization problem， you can have arbitrarily large objective function value for a minimization problem。

 you can have arbitrarily negative objective function value。

What can you immediately deduce about the dual linear program if the primal has unbounded objective function value？

Good。Has to be infeasible， there can't be a solution。Why， well suppose there were a solution。

By the definition of a dual feasible solution， it would give you a bound。

 a finite bound on the best possible primal objective function value。 so if there's no bound。

 there's no dual feasible solution。好看。And similarly， if opt of D is unbounded， oh。

 forgot the conclusion。The infeasible。If D is unbounded， then primal if the dual is unbounded。

 then the primal has to be impfeasable。By the same argument。And there's a part three as well。

So suppose you have feasible solutions。To both the primal and the duall。

And it's also the case that they have equal objective function value。Meaning。C transpose X。

Equals b transpose y。What has to be true about this feasible X and Y？

So think back to like when we were talking about flows and cuts。

 So we deduce quite easily and we deduce it again today。That whatever the max flow value may be。

 it's never going to be bigger than the minimum cut value。

So even if you didn't know the max flow and cut theorem。

 you could at least conclude from that that if I showed you a flow and I showed you a cut and they had the same value。

 they both have to be optimal， a maximum flow and a minimum cut。The same thing is true here。

Given that we have weak duality， if I ever show you a feasible primal X， a feasible dual Y。

 and they have equal objective function value that simultaneously certifies the optimality of both。

So I'll draw a picture that I draw once before when we're talking about max Fing cut。

 but's exactly the same picture here。So if you think about。You know。

 the objective function values of feasible primos is the x's。And the dues is the O's。

We toity says all the x's are lefts of all of the O's， you can never have an x to the right of an O。

So if I ever can show you an X and O is superimposed on each other。They got to be optimal。

 No x can be further to the right because then it would be further to the right of an O。

 which is disallowed， no O can be further to the left because it would be the left of an x。

 which is disallowed。So everyone clear on that？So even without having proved strong duality。

 we can at least say if we're ever so lucky to get our grubby little hands on feasible primal and dual solution so that the objective function values match。

 then we're done。 We know that we're done。 We've solved both problems optimally。😊。

Questions about that？Okay， so one final concept for the lecture。

 which is a corollary of the corollary。So this is something called the complementaryary slackness conditions。

 It's， again， trying to provide a generic answer of how do we know when we're done。 That is。

 it's providing certificates of optimality。So。So it's going to be a corollary of part three。Okay。

So suppose x and Y are again feasible。For the primal in the dual to think about like a flow and a cut if you want。

And the complementaryary slackness condition hold。Okay。C， yes is probably。

Not the right acronym in a class like this。So common slack is one。Suppose that。

Whenever you have an objective decision variable in your primal。With a non zero value。Okay。

Whenever you have a decision variable in the primal with a non zero value， suppose it's the case。

That in the due， remember in the dual constraints correspondent variables。

 So there's going to be some analogous JF constraint in the duel。

Suppose that whenever xj is not zero， that Jith constraint is tight， that is it holds with equality。

So Jade constrain a D。Satisfied with quality。Yeah。And then the other condition is just the reverse。

So whenever y I not equal to zero。X satisfies I constraints。With a quality。Then。X Y， both optimal。

For P And D。Okay。So the point is it's another sufficient condition for optimality。

If you have a primal solution， if you have a dual solution and these complementaryary latticeish conditions hold boom。

 you know you're done。Okay。So I'm not going to have time to give interpretations today。

 we'll pick that up on Tuesday， but so for MaxFlow。

 let me tell you what the complementary s conditions translate to。They say。

 suppose you can find a flow， feasible flow， and an ST cut。

And suppose it's the case that every edge crossing the cut is saturated。

This is fully used and every edge going backward across the cut is zero。

Those are the complementary sinness conditions， just take it on faith for now。

 those are complementary slas for max flow。Whenever you have something crossing the cut forward。

It should be fully saturated， and everything should be zero backward。

If you can find a flow on a cut that have those properties， then they're both going to be optimal。

 And if you look back at our proof of the correctness of Ford Forson， actually。

 we exhibited a flow in a cut with exactly those properties。

What I'll talk about in detail on Tuesday is in the Hungarian algorithm。

You might remember in the Hungarian algorithm for Min cost matching， we had vertex prices。

Where did those come from， those are dual variables。We had these weird invaris with these weird。

 reduced costs。 Where did those come from， Those are just complementary slackness。

So you've already seen all of these concepts in more concrete guises，So the proof is very short。

 but amount of time， so I'll leave that for Tuesday and then I'll give you concrete examples to help reinterpret the algorithms that we've studied in terms of the concepts of LP duality that we've learned today。

 see then。