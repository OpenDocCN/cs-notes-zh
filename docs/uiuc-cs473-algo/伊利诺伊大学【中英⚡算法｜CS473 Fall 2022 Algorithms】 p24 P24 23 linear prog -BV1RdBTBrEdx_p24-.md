# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p24 P24 23 linear prog -BV1RdBTBrEdx_p24-

Okay。

![](img/6a2a3637d5894f98d1b4e12c1e529328_1.png)

你还。All right， so welcome to Winter。Okay。Um。It's not too bad yet hopefully it'll just stay like this。

 maybe with more sun。So this is the last。Weat eggss。Sort of real content that isn't just reviewed。嗯。

There is homework due Thursday that's going to use some of the stuff i'm talking about in class today I'm going to continue talking about this stuff into Thursday but。

嗯。The kinds of things， the kinds of things that we're going to ask about。

On exams are more going to be like modeling questions similar to things that you see in that。

And less about the technical details， so i'll say more about that。

When we get further into the material。There will be a homework 10。😡。

Bad news is it'll be twice as long as you usual homework and the good news is you don't have to come anything in。

So the idea is homework tends going to be a few more exercises mostly on the material from the last chunk of the course。

 but maybe with one or two things that call back to earlier in the semester。

We will release solutions。For homework 10。Not the Monday immediately after break。

 but the following Monday。😡，Today， after that， I'll walk through。

A sample final exam or at least as much as we can do in an hour and 15 minutes。

That will not be from that set of things， but will be even more problem。

So the idea here is just to give lots of opportunities to practice with the problems。

 ask questions and office hours， ask questions online。嗯。啊。And on that Tuesday， I what file。Okay。

 but the work that's up now is the last point we're going to grade the material that we're talking about。

Really today。Is the last of the material that will solve？All right。嗯。

The term term two is still not quite graded， but I've extracted a promise that everything will be graded by。

Tomorrow， so on Thursday， I can come in and say these are having exam。嗯。Eliminary numbers look。

A bit better than mid one。but it's still preliminary because we're still waiting for one。O。Yeah。So。

Today I want to talk about。Then you' programming。喂。So。嗯。Over the past several weeks。

 we've been talking about family of problems involving graphs where largely the types of things that we've been asking to do are modeling questions。

😡，How do I take this question about committees and so on and model it as some kind of problem where。

Things are representative as vertics in the edges in the graph and some things postpone close through that graph。

In a way that allows now all kind of black box。It。M clothes， for example。

You've seen this before if you took 374 where。You need to figure out what the graph is and then compute shortest paths within that graph or compute a topological order within that graph compute do connectedive components within that graph。

That's the same way that we're going to approach this family problems called linear programming。

I am going to spend some time on Thursday talking about how to actually solve these things。

 but the most important thing to internalize is the vocabulary。

And to try to get a little bit of practice of how you would model optimization and problems as linear programming。

😡，So this on the screen is a linear programming problem in kind of full abstract generality。

so you're。Inputs。To the problem are various。Coefics。嗯。So you see the A。

 B's and C sprinkled throughout here， there's a big matrix。A two by two sorry。

 a two dimensional array of entries AIJ， there's a one dimensional array of B。

Listed here is a subject because I'm writing this back in sort with algorithms。

And there's an array of sea。Again， we're using subscripts instead of brackets because I'm using mathematical notation to write down that for loop。

And。The outputs。Are variables。Okay， so I have variables x1， x2 up through Xd。

 these are the values that I'm trying to compute。Now。What I want to find are values。😡，Real numbers。

Excellent through SD。嗯。That satisfy a bunch of strengths。So。

What the first line after subject to says。Is I'm going to take some weighted sum of the variables and that needs to be at most。

Some constant be subject， so this constraint might be x1 plus 5 x3 minus 7 x42 is less than April to 19。

It' just a linear combination is less than or equal to some number。And I really。

 I've only broken it up into these three lines because there are three different ways that you can compare。

😡，Real numbers you can say one is less than equal to the other one is equal to the other one is greater than or to the other and you might have have all of these different types of constraints showing up in your program and and so。

On top of this。There's a bunch of constraints that you want to satisfy and then among all。😡。

Vectors x1 x D。Did it satisfy these constraints？I want to maximize the dot product。😡。

Of that vector with some other vector， I want to maximize this weight sum of CJH。

And so maybe I want x1 minus x3 plus 7 x5 to be as large as possible。系。The word linear here。

Refers to the fact that。These are linear combinations of the variables。😡。

Every expression that you see here that involves variables is。😡。

Constant times variable plus constant times variable plus constant times variable plus constant times variable。

The function that we're trying to maximize is a linear function of the variables。

The constraints are on linear combinations of the variables。

You never multiply two variables together， you never square a variable。

 you never take the absolute value of a variable， you never take the sine of the log or an exponential function of variable。

 variables can only be weighted and added， that's it。😡，嗯。Programming。

Means the same thing it meant in dynamic programming。😡，Building up a table。

So the way linear programming is normally presented and not the way I'm going to present it。

 you get these big tables of numbers called tableaus and you do pivoting operations that look like Gaussian elimination and there's a sea of numbers flying at you I'm going to try as much as possible to avoid。

😡，That picture of linear programming because it has never made sense to me。😡。

Instead to try to get some intuition about what this is， I'm going to show you。😡，A geometric picture。

Of linear programming。喂。😊，No。This is an example of a linear program with two variables。😡，X and Y。

Okay， let's stick to the notation， x1 and x2。so this is a constraint。Which might be of the form。😡。

Let's say a1 x1 plus a2 x2 less than or equal to B。可。😊，Now， the constraint is not just the line。😡。

The constraint in this case is。UmAny point that you want to think of。

 any point x1 and x2 you want to think of needs to be below the one。😡，喂。

Maybe here I have a similar constraint with the greater than or equal to that indicates the point to be above that one。

I don't have any equality constraints here that would mean the point has to lie on the line。😡，对。😊。

But I've got a bunch of inequalities。😡，Every one of these lines is just writing down an inequality of the form a1 x1 plus say 2 x2 is greater than or less than or equal two。

😡，S number B。Depending on which side of the line you want greater than a less than。

And I've got different A1s， A2s and B's for everyone。

So the set of all points that satisfy all of those。😡。

Inequalities is called the the feasible region or the。对啊。

You want to be fancy about the feasible polyhedron。Of the the linear program。This is just。

The intersection of all of the things。😡，Geometrically in two dimensions。

 a constraint is a half plate， it's everything on one side of the lung。Including the wine itself。

So the feasible region is an intersection of urban。😡。

If I'm dealing with a three dimensional linear program。A constraint is a plane and one side of that。

So I'm only going to consider points x1x2x3 that are above this plane and below that plane and above this plane。

In front of this plane。The feasible region。Is those of you who are watching this online don't get see you wave my hands。

 there's a big sort of chunky box like thing called the apolohedron that is the intersection of all these constraint a spaces。

对。It all of。All points that are on one side of the plane， including the plane itself。

 it's called the half space。😡，The intersection of all these half spaces gives you a all of。

Now it's relatively rare that the LP that you're going to be solving are only dimensional。😡。

And so you need to approach this geometric intuition with a little bit of skepticism。

But I personally。Find this picture infinitely more illuminating。😡。

Then the big tables of numbers that you would see in a typical class。

 you would take a linear programming and say ISE。我咩啊。啊。So you're going to get my bias take on it。

I apologize for that for those of you who are more used to seeing this in。That was that arrow。

That's the objective function。😡，I want to minimize some linear combination of x1 and x2。😡，Now。

 the lovely thing about coordinates is that they're mere convenience。

The thing about geometry and to some extent about linear algebra。Is that？

I don't really care about coordinates。So I don't actually think I can root it snow， I can't， sorry。嗯。

啊。I can take a linear program described as a bunch of halfline sorry halfline。

And I can rotate the entire day。And I've changed。Coordinate systems that haven't really changed any fundamental way what the feasible region is。

😡，A linear function。😡，He's just a direction。so for those of you who are used to thinking about linear algebra。

 a linear function just means I specify a vector and I want to maximize the dot product of the vector of variables with this vector vector。

Now vector， again， this is a direction and magnitude。

But I'm free to rotate my coordinate system until that vector points in a convenient direction。

 which I will call down。😡，Yeah。And so without loss of generality。

What a linear program is always asking。Is in some convex polyhedron。😡，Find the lowest。Point。

Find the point that is furthest down within that feasible region。😡，Now。

Given that this is the definition really with what you programming。

It's no surprise that the most common algorithm。😡，For solving linear programs called simplex algorithm works as follows。

 you hold a marble up inside the feasible region and you drop it。😡，The marble falls。

Eventually it settles somewhere， that's the answer。

Okay that's literally what the algorithm is doing now i'm hiding a lot of implementation detail in that one sentence description and in particular when the linear program is 17042 dimensional。

😡，It's maybe not quite so clear what it needs to fall down。😡。

I'll try to give you some more intuition about that on Thursday。😡，But嗯。

The basic linear programming problem is。You specify a convex polyhedron as the intersection of a bunch of linearing qualities。

And France。And within that feasible region， you want to find the point that is furthest in some direction。

 which intuitively you should just think of as gravity。😡，Okay， so。

This is the form where we actually want to write things down。😡，嗯。Now。linearar programming is really。

 really powerful because there's a lot of flexibility in the way that you write things down and linear programming is really confusing because there's a lot of flexibility in the way you write things down。

It's hard to sort of nail down the right way to do this。

 the right way to write things down and especially for talking about dynamic programs sort of as a class of problems。

 I don't want to deal with this whole generality。😡，So instead， oh。

 maybe I should slow down a little and just give you an example。😡，U。

This is maximum flow problem written as a media permit。😡。

The variables are the flow values through the edges。😡，The variables。R S from U to B。For each edge。以为。

Okay。So the objective function。It's a weighted sumble flow values， the coefficients is plus one。

 if it's an edge coming out of S， minus one， if it's an edge going into S and it's zero if it doesn' edge doesn't involve S at all。

Yes。There are three types of constraints。There are the balance constraintss。

For every vertex that is about to take。Again， those， that's a linear combination of the F values。

Where I have a coefficientient of plus one， if it's an edge coming out of v。

 I have an coefficient of minus one， if it's an edge coming into v and have a coefficient of zero if the x person isn't involved be at all。

Then I have the capacity constraints。FOUD is a linear combination of all of the flow values。

It has one flow value with focusship one and all the other flow values of focusship zero。Similarly。

 I have the non activitygaivity constraints。Again， SQV is a sort of trivial linear combination of all of the flow values。

 Ill give one of them Coship one and the rest of the calculations。So every constraint。

Involves a linear combination of the flow values being equal to something or less than or equal to something or greater than equal to something。

Sometimes that's something is zero， sometimes it's not。

And I'm trying to maximize this linear combination of those for health。😡。

So a linear function of the flow。So that's a polyedron。And that thing we're maximizing is down。

But now it's a e dimensional polyhedra because I have one variable for every edge in my flow network。

And like I said， we're probably not going to be doing too many two dimensional linear programs because a flow network with only two edges。

😡，Pretty easy to figure out。Um， and then I have a constraint for every vertex that is a as and I have another constraint of the edge and then have another constraint。

So in general。I'm going to write D to be the number of variables。This is short for dimension。

And I'm going to write n to be the number of constraints。And is short for number。Thanks。

As it always is。Some bizarre people like to use k for dimension。😡。

Some even more bizarre people like n for dimension。

 which is better than K because at least n is in the word dimension。😡，At the end。

 but same people use D for dimension。And I claim to be saying。Okay， so this is an example。

 and I'll show you more example to。嗯。When we're thinking about linear programs。

 though in sort of the abstract， we don't want to think about them in full generality。

 it's helpful to。😡，Like forced it into canonical form。

 similar to the way that you took all these different variants of maximum flow by massaging the graph and maybe adding emergency that。

😡，We forced it down into the original form that F and Fson talked about in their first paper。

 so linear programs have similarly a canonical or standard form。Which is。啊。Over here， on the。

So again， I'm maximizing the linear function。But now there are only two types of constraints。

There are non trivial constraints， which you're always upper bound。

 you're always less than reach two。😡，And then there's sign constraints to every variable is not negative。

So we can see sort of the non negativity constraints showing up already when we talk about flow。

 but that flow problem that Ive written up there， that is not in this con。嗯。啊。

This is sometimes called， I think the best way to call this is。Standard。Inequality form。In the notes。

 I refer to it as。Canonical form。It's sometimes called standard form。

The problem with standard form is that there's a different way of writing down linear programs that is also called standard form。

Unfortunately， that other one is also sometimes called canonical form。

Notation is a mess standard in quality form， I think is probably what I should be calling it all the time。

 but it basically is you only have upper bounds that are interesting and that every variable means to be non negative。

And now I can express more this whole linear program more compactly using vector matrix sation。😡。

So here this vector C is the one that has coefficients C1 through CP。

Those are the coefficients of my objective vector。Then I have this matrix a。

 this is the one that contains the coefficients AI J I goes。From point N， I have a row for every。

And strengthts。And J goes from one have a column for every variable。U。

Then the right hand side of this inequality is something that I prefer。

Offset vector just the right hand side of the interesting inequalities so this。Is the。

Ojective vector。This is the。S matrix。And this is the offset vector。And。Remember。

 A B and C are actually the input to the problem you writing algorithm that solves within your programming problem。

 assuming you want it and send it in the quality form。😡，You write down。喂。In straight matrix。

 you write down the offset vector， you write down。Yeah。Tical。

Those are the three arrays that you pass in your open。嗯。Okay。So。Again。啊。

It's a little bit difficult to kind of match up some canonical form with picture， the canonical form。

You can always massage things into that form， so for example。

 if you have a linearequality that's a greater than or equal to instead of less than or equal to you could just multiply both sides by negative one。

😡，If you have an equality constraint。You can break it into a less than or equal to a then a greater than or equal。

And then flip the greater energy quickly you around the less available size。嗯。

Getting all the variables be non negative or similar trait。So without going into detail。

 because this is not something I'm going to ask you to do。

 any linear program can be turned into this way。😡，嗯。All right。

So that's kind of not when I talk about matricency vector。

But I do want to go back to this this sort of。Geometric interpretation。

And point out that they're two pathological。Things that can happen with the linear program。So。

I want to find the lowest point。TheIn of all these tests。So can anyone think of a way that？

That question might not have an answer， or the question might not make sense。这个还。对。Okay。

 so the suggestion was suppose one of the spaces is horizontal。Really orthogonal to the objective。😡。

That's still okay， that's an instance where you have more than one optimal solution。😡。

So more than one maximum foot。That's usually thought of as a degenerate situation in the context of linear programs and the way most linear programming software works is if it sees a degeneracy。

 it basically adds a tiny amount of noise to everything to get rid of it。系。So that's still sensible。

 it's just the answer is no longer unique。哇。What if there's no lower bound？All， so in this case。

The linear program is set to be unbounded。So there is a feasible region。

But there is no lowest point in that Pennsylvania。So the canonical example here is shortest paths。

The shortest cap problem is a linear programming problem， and I'll show you that in a second。😡。

But when there is a negative cycle。In your grass。Shortest pads aren't well defined because I can make longer and longer walks with more and more edges that are shorter and shorter the total length goes to negative infinity。

😡，That's what that looks like in the linear program。

The objective value that I'm trying in this case to minimize is the length of a path or really the length of a walk。

😡，But I can make that length arbitrarily negative by just adding more loos。😡。

So there is no optimal solution。I can get solutions that are better and better and better。

As long as I want。系。嗯。One thing to point out here。Is that this depends on the objective direction。

 so if I choose a different direction。For my LP， if I choose a different objective function。

Then I get a different linear program with exactly the same constraints。

 exactly the same feasible region， but now it is that。😡，嗯。And I'm going to write this down。诶。

It turns out that whether linear Park is unbounded。It clearly depends on the constraint matrix a。

 that's the slopes of the line。😡，But it doesn't depend on the position before。😡，That's the offset。

It tells you breach line how far away it is in the northern。Um。That's a little bit more subtle。

Okay so this is a case where。There are。Pasible solutions。But there is no best feasible seat。

But there is another possibility。No feasible solution at all。So here is a linear program。

With few dimensions for constraints I didn't draw it with the shading because the shading kind of isn't as clearm instead drawing the arrows to indicate which side of the line the feasible point should be on。

 there are no points on the correct side of all four of these lines。So I made。

The three constraints down at the bottom in order to satisfy。This constraint。

 this constraint and this constraint， I have to be inside that blue triangle。

But then I also have to be above this type iron itemagon one。😡，So there's no way to make this happen。

So in this case。Let me just say that the linear program is infeasible。

And the canonical example here is a flow problem where you've got。😡，No zero balances。But。

The balances go add up to zero。There's no way to make a feasible flow。

 there's no way to make a flow function that satisfies the balance of space。Or more suddenly。

 maybe you've got a bunch of positive balances over here， a bunch of negative balances over there。

 but there isn't enough capacity in the edges in between to actually resolve all that supply in the。

So there's no feasible plot。Like that's what that looks like。I there is no feasible region。

 the intersection of the constraint pathway is the empty set。😡，Now， again。

 this clearly depends on the constraint matrix a it also。Depends。On the offset vector。So again。

 the offset vector in this picture tells you how far away the line is from the origin。

 so I could move all of the lines far away from the origin。

 the half space of the pointing into the origin， and then the origin is feasible。😡。

It's changing the offset vector。😡，And so it changes whether the thing is feasible or not。

But it doesn't。Depend。On the objective zone。If it's infe， it's in in every direction。😡。

The empty set is empty no matter which way you look at。😡，系。See some symmetry here。

It's not a coincidence。啊。These are evil twins of each other。

In the same way that maximum flow has been cuts。Okay， we'll see this more by the end。嗯。仔。

So questions about what can go wrong？All right。So I want to just continue with a couple of。Examples。

We saw one example with natural inflows I want to give you a simpler example。So here。My。Variables。

Our。Just V。For all vertices V in some graph。And my givens。

Besides the there's a bunch of ones and zeros hiding in the constraint matrix and the objective vector。

 but the other thing that's given is a link。L of UVV。For all edges。U to be。You want to just that。

What is that。Okay， now immediately， a question mark shape light bulb went off over about 20 of your heads。

哦。Shortest path。Wait a minute。What's this word？嗯。What， okay。

 so let me try to convince you that this is actually shortest patents。

And this is kind of a review about how shortest path algorithms work。

there's this generic shortest path strategy。嗯。Ford's shortest path。Let's call it a meta algorithm。嗯。

Every shortest packed algorithm Paul is decided。😡，Thanks for Goldman for Lloyd Warshll。

 a bunch of others。对。So the idea is that I。Maintain。A value dis V。At every vertex B。Initially。

Distance of S is zero and。Distance at any other node is infinity。Thanks actually。

 remember how thatter works， you're on the same page。Okay， then I'm going to say that an edge。

UV is tense。If。The distance at you。Plus the length of the edge from U to V。Is less than。

The distance would be。So and edge just tense if。What。The distances are obviously wrong。😡。

So that note on the left thinks that its distance from the source is five。

And the note on the right it thinks that its distance from the source is 12。

But there's net between them with weight three。So whatever the path is reading from S up to this note labeled five。

You know， there's some shortest path going over here。

 there's a shorter way to get to the note on the right。

Which is to go through the note on the left and then go across that egg。So an edge is tense if。

The distances evolved。喂。Ford's strategy is find a 1 edge， relax it。

 that thing that I just did so change the distance at V to be distance at U plus L of UVV。All。

 so relax it。That's a distance of V to。Distance of U plus L of UVv。

Then see if there's another 10 edge， you can find another 10 edge relax it。

 you can find a 10 edge relax it， you can find a 10 edge relax it， typically find a 10 edge relax it。

 if you can find a 10 edge relax when there are no more 10 edges。All the distances are correct。Okay。

Now the distances start way way high up， they're almost all infinity。

 in particular the sum of all the distances are infinity。And over time。

 you're lowering the distances until all the edges are relaxed。😡，That secondequ there。

What this says is。UV is not tense。系。So I want to lower the distances as little as possible。

So that none of the evidences are。I'm lowering it as little as I can。

That means I just want the highest possible values to distances that keep all the edges below。

So even though it's normally phrased as a minimization thing in your head。

 even though you algorithm pick something and lowers it until it works。😡。

What it's actually doing what Dykesster's doing what Bel and Ford are doing is they're taking a point that's not feasible。

😡，It wants to be high up， it's way too far up。😡，And it lowers it。

Until it just reaches the people who we itself。😡，So what you end up with is the highest point。喂。

The objective vector is a linear combination of the variables， all coefficient equal to one。😡。

There's one weird constraint。Because the distance at zero， the distance at S is always equal to zero。

And then I have a bunch of inequalities that again。

 those are linear combinations of the distances on the left， one distance has a coefficient of one。

 one distance has a coefficient minus one， the rest have a coefficient of zero。

It's less than equal to some scalar value。Many your combinations。Linear objective。没。

U this is not the only way to phrase the shortest path problem as a linear book。😡。

And you might reasonably ask， is there a way phrasing the shortest path problem as a minimization problem？

😡，And there is。It's just a little bit harder to read this one you book。

So I will tell you what this means。But I don't expect you to be。😡。

I just want to you claim and you can go back and think about it later that it makes sense to think about shortest paths in this。

😡，Okay， so again， you're given the same data。😡，You're given a graph versus season edges and you're given a link for every。

But now the link is showing up in the objective function before it wasn't。😡。

The links are showing up in the objective function， these x's， these are the variables。😡，ok。😊。

And has a variable for every entity。Now， what does this variable mean well， at the end of the day。

I'm going to compute a tree of shortest paths。喂。What this variable means is。😡。

For every edge that's in the tree。😡，The variable tells me how many vertices are beyond。😡，That is。

Okay， so this is my my source for text S so this this thing is going to have a variable。

It's equal to one， there is one shortest path from s that goes through that edge。😡。

There are two shortest paths from s that go through this edge， there are three here， one here。

 one here， six here， one here， eight there。So what X of UV means？

Is how many shortest pads go through the edge you need？So what is that function up there？

Oh and if an edge isn't in the short pad3 x includeatic exchange。So。

What that function there is actually computing is the sum of the lengths of the shortest path。Well。

 behold。That's also what this function is to。系。That's not a coincide。Now。

What is the first piece straight say， it says for every vertex。

The number of shortest paths that go into that vertex is one more than the number of shortest paths that go out of that ver。

😡，Why one more。Does one of the shortest path to any that work。Okay。

 so here I have six coming into the dis vertex and a five going out， I lost one。

 that's because I needed an Detroit Catholic dispute。Except I don't count S。

 S doesn't have this particular balance strengtht。😡，S is allowed- in fact。

 I already know that sum of the x's coming out of S， that's always good to be equal to n minus1。

 the number of variations。Oh， and the last constraint is just you can't have negative problems。系。

This is actually a Min cost flow problem。Where I have a demand of plus one。

At every vertex excepts desk where I have a supply of n minus1。

And I'm sending one unit flow from S to every other vertex and I want the cost of that flow to be as little as possible。

 but if I send one unit to flow on the path to the vertex。

 the total cost is going to be the length of that path。😡。

I'm minimizing the sum of the lengths of the shorts pads。

 but I'm just expressing it in terms of the edges of the。😡，Right， kind of weird。

And there's one really weird part about this。Why are all the excess's integers？😡。

Did I say in the problem formulations that the x's are going to be integers？😡，你好。

Linear programs cannot declare certain variables to be integerents and other variables not to be integers or anything like that the variables are always。

😡，You have real numbers， yeah， they're just real。If all the other values are integers orrations。

 then provably in the solution， all of thexs are going to be rational numbers。

 but it's really unhealthy to think about it。😡，嗯。😊。

It just so happens that this particularly in your program has a property that implies that there is always an optimal solution。

😡，你找。Similar to the way we did loanss with。When you had energy capacity to notice heat。

 the flow will always have energy value at the end。Not about every flow has energyger value。

 which if there is a flow of energyer value， that's the one before focusing five。😡。

Same thing is going on here。There's a subtle property of the Le program that implies an individual results。

系啊。This linear program has said one variable for every。😡，H。One strength for every vertexity is not S。

😡，And then one last non negative。Yeah。系。😊，These two linear programs。Our。Lied to each other。

You're what are called duels of each other。And in fact。

 derive either of them mechanically from the other。😡，In the same way。

 you can kind of mechanically derive minimum cuts from ex。So on the slides and in the notes。

I describe， a couple other examples， the， the maximum flow when your' program you've already seen。

 the one at the bottom， that's the minimum cut when your program。

There's a variable for a B vertex s that is one if the vertex is on the S side of the cut and zero。

 it's on the p side of the cut。And there's a variable x of UVV for every edge that is one。

 if that edge crosses to forward and zero， it doesn't。😡。

And I'm trying to minimize the total capacity of that cut。Again。

 these are mechanical dues of each other。系。But in the interest of time。

 I don't want to walk through this example in more detail， I'm going to have to refer back to the。嗯。

What I want to say instead is talk about what this do hours。So every linear program has an evil twin。

😡，And called the two。The definition of due is。If believe or is new canonical。

Stands being called important。As a maximization problem。

With upper bounds defined by the constraint matrix， all variables know negative。

Dual is a linear program that is minimization program。With lower bounds。那个。But again。

 all variables being non negative。Now。Different people will argue about what prim rule will mean。

The reason that I wrote primal on this one and duall on that one。Is because this one is on the left。

Some people will insist that maximization programs or primal LPs， minimization programs or dual LPs。

 no， they're both LPs， duality is a relationship。😡，Clyel just means the one I picked up first。😡。

Dual is the other one。It's all these。I could swap the names primal and duel， perfectly s。

 perfectly fine。喂。It's not that dual is in some way weird or less than or you know more obscure anything and in particular you'll notice that dual LP isn't in the normal canonical form。

 it's not a maximization problem and the inequalities attached to the matrix are backwards and for that matter I've written the matrix vector of things backwards。

😡，Great， I'm really。The duel should be written like this。😡，Okay。It's still a maximization problem。

 it's still economical form， it's just there's a lot of more horizontal lines involved because I need to gate things。

😡，So let me try to give you at least。😡，An intuition about how the syntax works。Okay。

 so this objective vector。In the primal？Becomes the offset vector in your due。😡，Now in the original。

Primal problem。Solution vector。Is a D dimensional vector， a D by one matrix。Checkive vector。C。

I really want to think of that。As a row vector。D by one。Make friends。

And that product up there is just the product of those two make。😡，爱嗯。冇放啊冇放啊。对。

The result is a one by one matrix， otherwise known as a number。Okay。喂。嗯。Okay， similarly， I've got。诶。

嗯。I've got a D N by D。Constraint matrix。It multiply by a5 by one。Variable vector。

Let me see if I can move this。😔，No， sorry。Multiplying this by a。D by one。

Variable x and the results is at most。This offset vector。So the result I imagine nestled in here。

 this is always time to remember how the works。As I take the matrix on the left and in its upper right corner。

 I have the bottom left corner of the from the right and their product falls down underneath。

so the product of this n by D matrix two by one vector is an n by one vector。So here is your matrix。

And。Here is your offset vector。哎。And then finally， everything in that variable vector monitor。

So when I dualize， I'm really just rearranging these books。Okay， so instead of saying。Maximize this。

Now I want to minimize， well， B is a column vector。And so。That means why。Is a row vector again。

 now this is N。By one， and this is the same exacted。Victor。B。😊，And now I need to multiply this。

Re vector。Why。By this constraint matrix， that could be better than that。Hey。😊，This is N N。

By D by one， so this needs to be greater than or equal to this。D by one vector C。So here's your seat。

And here's your word he。Yeah。They literally just moving the pieces around。

The only difference is that I'm sort of swapping what the rows and columns mean。

In the original chial linear program， the rows at the constraint matrix correspond to constraints。

Colins correspond variables。Dual LP。The rows of the constraint matrix corresponds to variables。

 and columns correspond to constraints。Contraints， variables。主。

All that's going on I'm swapping now really if I want to keep this in terms of you know。

 everythingonical， I should also I'm really transposing everything in the game。

Which is why I get this switch from max to min and why I get this switch from less than to the grade binary portfolio。

😡，Um， that's just a syntactical detail that you have to A， remember or be right on your cheat sheets。

嗯。嗯。Now。These two linear programs， the primal LP and the dual LP。😡。

Are related to each other in exactly the same way that maximum flow cuts are related to each other。😡。

So I have an LP in canonical form？And it has an optimal solution。

 meaning it's neither invisible nor unbounded。😡，Doesn't necessarily mean the opposition。

Call that optimal solution at star。😡，That happens if and only if the dual linear program has an optimal solution。

😡，It's not feasible， not infeasible and not unbounded。😡，And moreover。These are。

These solutions are related to each other by this lovely little equation down here at the bottom。😡。

Which says。The primal objective value for the primal LP at the primal optimal solution。

Is equal to the dual objective value dual。Variables at the dual opt。

And both of these are equal to this threeway vector matrix vector product。😡，So this in another words。

This is very much the same the same。If you have a network that has a maximum flow。

Then it has a minimum cut。And the value of the maximum flow。

Its equal to the capacity of the minimum cut。And that this three way product in the middle。

What this is basically saying is this is equal to value of the total value of the flow through the edges that the minimum that cost the cut。

😡，嗯。This gives you a way of checking whether you have an optimal solution。

If you have an optimal final solution and an optimal dual solution and they satisfy this equation。

 if you have a feasible。😡，Prial solution and a feasible Google solution。

 and they satisfy this equation they optimal。😡，In the same way that it's got a flow that saturates a cut。

 then it's a maximum flow in an minimum cut。😡，嗯。😊，Now。This is great。

If you've got a canonical linear program。But chances are really good。

If you want to feed your linear program to a piece of soccer that solves linear programs。

 you need to go through the exercise of massaging it until it's in the precise canonical form that that software wants。

😡，The canonical form that Pythons。啊。SIP， if we're in SI， if we're in a professional setting。

 skippy if we're being informal。The way Spy once it's one your programs is in canonical form except you can also have some equations。

😡，Do specify an upper bound constraint matrix and upper bound offset vector and the quality straintraint matrix and quality。

And it assumes that all the variables are positive non negative。

So you have to do this massaging if you want to implement it。😡。

But if you want to reason about things。😡，Going through the exercise of non equalizing。

Canonizing canonizing your linear programs is really more troubled than it's worth。

 generally you write down the linear programs in a way that reflects some structure that you want to reason about。

So when you're computing the dual， you want to do it directly in terms of the way that you wrote down the LP。

😡，系。And so there is a dictionary。Every every constraint in the primal corresponds to a variable in the。

 every variable in the primal corresponds to the constraint in the due if the primal is a maximization program。

😡，Then。Upper bound constraints。Turn into non negative variables。😡。

Lower bound constraints turn into non positive variable。

Equality constraints turn into unconstrained variable。😡。

There's no constraint on the variability less than individual。

Every variable in the primal corresponds to a constraint in the dual。😡，Um。

 if that variable in the final is not negative， that corresponds to a lower bound constraint the renewal is greater than or equal to。

If the variable is non positive。😡，That corresponds she would upper bounds in the duel。

If that variable is unconstrained， that corresponds to the equation in the dual。

And if that variable for some reason。😡，Its set to zero。It's not variable。0。

So it corresponds to no constraint at all。😡，盯不住。Because it's not a variable and only variables for。😡。

Um， now。Yes。I don't know how to remember this。In particular。Wing down this table。

tookook me several hours to verify that I got all of the signs right when I was reversing things and similarly if I'm utilizing a minimization program that the rules are very slightly different really what I did to generate this table is I said。

 let me write down a generic LP， an arbitrary LP。😡，Turn it into canonical form。

 dualize that and simplify， what did I get？😡，I do not recommend even trying to memorize this payment。

😡，喂以。Just。Tattoon it on the back of your hand or something。

If you're going to be dualizing things a lot。嗯。It's very easy to get this very slightly wrong because if you'll notice。

 for example。😡，Wait， here， the inequalities are opposite of each other， but here they're the same。😡。

Here， the inequality is the same here that the opposite of each other。But mins and maxes。

 aren't they supposed to be symmetric？What？嗯。If you're good at memorizing things more powers to you。

 bless you， the world needs more of you， that's not me。😡，系。So what I would like to do。

Just walk you through the process， computing the tool of this linear your hook。😡。

This is the original shortest path linear your program。But this is what we want you to do。

In your homework， this is why I wanted to make sure I got to this point。ok。😊，So。

The first thing to do is to make sure that you understand。

Who the various players in the linear program？What are the variables？

What are your constraints because these players are going to swap role？😡，诶。😊，So here I have。Varis。

I have dis of V。4。Every。Vtex。你。So by variable vector is a v dimensional vector。Yes。Wonderful， thank。

My constraints。Now， I don't count this as a constraint because it's just comparing something to zero。

 I only want to count interesting。😡，系。So I have a constraint。4。Every edge。You to。

So that means down here in the dual end。嗯。系。嗯。Above this line， Spock does not have a beard。

Below this line， Spock has a beard。系。😊，So I have variables。Something for each。Edge。

U to theum so for everyB， I have a variable， I need a name。Something else you do。

I don't know what it's going to mean yet。对。我。Yes。对。Yeah。Terrible， yeah。

 so I don't know what to call it， I'll call it X okay。关。I mean yeah， I can call it blob of beauty。

 but then I'm going to be writing blob a lot and then my handkin look。系。And really， I don't want to。

Bas myself in advance of giving this any kind of interpretation。

 so I really want as neutral meaningless variable name。嗯。And now I'm going to have a constraint。For。

Every。Vtex。Great， okay， cool。So let's start with what kind of LP are we doing so the primal LP is a maximization LP so that means the dual LP is going to be a minimum one right so let's write that down so it's going to be min。

😡，Some combination of the exitods。So the coefficient that I attach to a variable in the objective function in the dual。

😡，Is equal to the right hand side of the constraints。In the primal so this。

Is part of the offset vector， the offset vector as the went to the other。

Okay so that becomes the objective vector。In my dual linear program。

So this is going to be sum over all edges from u to v with L from U to v that's given times x from u to V。

 I don't know what that is yet。😡，OkaySo I take the right hand side。Of the primal constraints。

That becomes effective。All right。Such that。Now。Every。

I have some underlying matrix where the rows correspond to the constraints in the LP at the top。😡。

Okay， so I have some matrix。Where every row corresponds constraint will have a constraint for every edge。

 so my constraint matrix has e rows。😡，And I have a。Column for every variable。

 so my constraint matrix has the columns。Fure out what this is， so the constraint at。The coefficient。

At the row corresponding to some edge U to V。😡，And the column corresponding to some vertex W。😡。

I have to think about this from any edge in any。Well， I look。ItSight。

If you edge and you look at how diversity show up。So in the constraint correspondinging to FGV。

I see vertex V。😡，With a coefficient， the plus one。I see vertex you。😡。

With a core coefficient of minus1 and every other vertex。系 see。With a coefficient zero。

This matrix A is called the directed incidence matrix。Of the grass。是。Basically every。

 it's a matrix representation where every row corresponds to an edge。

 you have a plus one at the head of that edge， and you have a minus one at the tail of it。😡，可。Cool。

Now， somehow down here in the duel， I've got a constraint for every column。

 so I need to think about what in the columns of that nature。😡，And I'm going to have a constraint。

 well for every column that means。For every vertex。喂。😊，So for the。Well， actually。

 maybe before I get to the right hand side of the constraint。

 maybe a little easier to put up the right hand。So the next thing I need to do， I guess。

 is figure out what's going to go on the right hand side of this inequality。

 and that's going to depend on this objective。俾。😊，Every coefficient from the subjective vector is the right hand side of some dual construct。

Now that just looks like a scar， but what that means is I have a zero coefficient for every vertex that isn't t。

😡，And I have a culture one。不对。So。I'll write down zero for every V that's not equal to t。And well。

Eals t， I'll get a one。Then I need to think about what kinds of constraints these are。

 so I look back at the original LP and I notice that only one。😡，Of my variables of the sign spending。

That's the distance of S。The distance at S is constrained to have s zero。😡。

Neither positive nor negative。😡，Every other variable is allowed to be positive negative。

 whatever I don't care， so if I look back at my dictionary。

 an unconstrained variable terms an inequality constraintstrain。😡，So I unconstrained variables here。

 they turn into equality constraints。Except。That's zero。Distance S is a variable。😡。

So I don't actually have a constraint corresponding to S。😡，So I just removed that now。

 so I have some constraints for things that aren't S&T。And then， I have。one concern。Okay。

 so every constraint i'm going to write down the columns。

 remember every row I have a pretty edge I have a plus one at the head， a minus one at the tail。

 so in every column I have a plus one for every edge whose head is here。😡。

And a minus one for every edge whose tail is here。So I can write this as。

Some overall u of x of U to v minus some overall W of x from D to W。And same here except。I go to tea。

And low and behold， I have the same problem。可解。Thanks so。Again。TheThe idea is。Sorry。

 I should do that in the white color。The right hand side of my constraints。

In the original LP become the coefficients of my objective direction。do。The right hand。

 the coefficients of my objective direction， the primal LP become the right hand side of my constraints in the dual LP。

The constraints。Matrix shows up。In two different forms， one by reading off what goes on in the roads。

 the other by reading off what goes on in the columns。😡。

The details about whether it's an equality andequality， whether it should be non negative。

 whether it's be non positive， whether it should not be there at all。

 that you just look at the addiction。😡，你三。And then the fundamental theorem of linear programs says。

Up there，' minimize I'm trying to maximize the distance at a particular value T。

 subject to the constraint that no these pen。😡，That's the same as in this case。

 I'm only trying to compute one path from S to T。And again。

 you can re this as a new possible flow call so x is the flow value from an edge。

 it's balanced at every vertex except the T with consumption and there's no contrain of the desk because I know the balance constraintstrain。

So down at the bottom， I'm finding the cheapest way to send one unit to the flow from ST。

That's the shortest path up there， I'm trying to find the minimum distance at T。

 six fill edges are relaxed， that's the shortest path。

So dual problems have the same solutions just expressed in different。Last question。

How to just give a spot time。Oh。好。LetsIt depends on the problem。

 some LPs are faster to solve in their original form， some LPs are faster to solve。

It's a good question， I'll talk about algorithms more on Thursday。We're a couple minutes over。

 thanks to your patients， I'm happy to answer questions up front。

 but otherwise I'll see you in a couple of days。Oh。有时我呢度。



![](img/6a2a3637d5894f98d1b4e12c1e529328_3.png)

还ello。