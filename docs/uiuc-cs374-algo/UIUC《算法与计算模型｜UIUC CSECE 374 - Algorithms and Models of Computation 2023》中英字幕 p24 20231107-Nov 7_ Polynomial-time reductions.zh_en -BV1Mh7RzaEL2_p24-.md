# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p24 20231107-Nov 7_ Polynomial-time reductions.zh_en -BV1Mh7RzaEL2_p24-

![](img/5185d70d8db0b63317db9ccaf3573080_0.png)

Yeah。

![](img/5185d70d8db0b63317db9ccaf3573080_2.png)

嗯。我呢个。我睇睇佢。

![](img/5185d70d8db0b63317db9ccaf3573080_4.png)

I。对。那你你开。Don嘅系。Okay， thanks everybody for coming。Especially it's such a nice day out。

 I know everybody would rather be outside in sun。apologies for the usual stack of hopefully ultimately harmless mistakes。

 in particular question1 B， everybody's just going to get full credit for that the committee buttons to explain the in the middle of an exam。

U。As it turned out。If you for both recurrences。For 1 B。

If you read the recurrences literally the way they were written on the answer booklet。

 both of them infinite looped。So the answer was no， the correct answer for 1 B was no。呃。

That's a bit too subtle for an exam question， so just fine。嗯。So we are。

I know is going to sound this is going to sound a little bit frightening perhaps we're done with the easy part of the class。

 we're now going to the hard part of the class and what I mean by that is we're done showing that things are easy to compute。

We're now going to start showing that things are hard to compute and when I say easy to compute。

 I mean everything that we've done， everything that you did on the midterm。

 everything that you've done in the last several homeworks。

 most of what you did actually for the stuff leading up to midterm one is saying， oh。

 there's a problem， here is an algorithm for that problem and moreover。

 here's a reasonably efficient algorithm for that problem。So occasionally you run into。

U problemsble involving， you know several layers of the graph or multi dimensional linear programming things where you get a running time like end cubed or end of the fourth。

But that's still。Within the realm of。Something that's reasonable to run on moderately large inputs。

So in the in the 19。50s in the Soviet Union。There was a。I a a。Fairly， I mean。

 the mathematics has always had a healthy culture in Russia。But in particular， Russia was very。

 very strong in studying logic。And one of the research thrusts that people started working towards in the 1950s is what they called the Noa Peterbar。

Which in English would be translated to brute force。This was the sort of background。When。

W was at Kmogorov had this seminar where who said， I'm going to we're going to try to work out a proof that you can't multiply two inngigit numbers in less than n squared steps。

It was sort of like brute force is really the best we could hope for and Ktsa came along and as students usually do show up their advisor。

嗯。But really the thing that people studying Petervo were interested in。

Is like brute force backtracking。Where。啊。The running times of these sort of obvious brute force algorithms are exponential。

So a good example of this， although not one that the Russians themselves studied is the so called traveling salesman problem。

 I have a graph with weighted edges。That represent cities and roads and salesman wants to visit each of the cities。

 but wants to drive as little as possible， so his goal。

Is to find a cycle in the graph that is as short as possible。And visits every city。All。

 so this is this is an example of。呃。Find。The shortest。细个。In a graph。That visits。Every。😔，Vertex。engng。

And because this is the 1950s， all salesmen are men。And's he。So。For a very long time。

The only way that we knew how to solve the traveling salesman problem was a brute force。

And what bruforce means in this case is try every permutation。Of the vertices。

So you literally just go okay， maybe I visit cities one2，3， four， five six up to n in that order。

 maybe I visit two then one then 3，4， five67 up to n in that order。

 maybe I visit one then three then two and four， five six in that order and you loop through all n factorial permutations and。

That's each one you measure the length of that cycle and you take the shortest squad。诶。

Don't do this on an exam because you haven't explained how to actually enumerate all the permutations by brute force。

 but let's sort of imagine there's a way of doing that it's not terribly difficult to get the next permutation and some like linear time。

 but the running time of the algorithm is really just going to be dominated by the number of options。

That we are。Have to explore。Another version， which is a little bit closer to the examples that the Russian paraorists。

Studdiied is the bullolean satisfiability problem。So this is find。Inputs。That。没。诶。Booolean formula。

Meaning a formula where the variables are true false and you combining those with ans or's not implies if and only if that sort of thing。

嗯。Evaluate。2。😔，True。So if I give you a formula with a bunch of booleian variables in it。Can I？

Assign values to those variables in a way that will make the formula come out to be true。

 or is this complicated formula that you've handed me just a really weird way of saying false？😡，Yeah。

佢知道乜诶。So I take up。You're trying to solve the problem。

In a context where I'm about to explain that the only thing we know how to do is try every assignment。

So brute force。The only thing we know how to do here is try all possible。Values。For the inputs。

So let me plug in true true true true true true true okay great let me plug in false true true true true true true true okay that didn't work let me plug in true false true true true true true true and you basically using a binary counter loop through all two to the whatever possibilities for the input and then for each one evaluating the formula can be done just by like you know you've got a formula you know how to turn it into some sort of expression tree and you can evaluate that by by post order or traversal but the the the。

The dominating factor here in the running time is that there are two to the n different possibilities。

For the values of those n variables。And you just have to try them all。Now it turns out that。

The in factorial。Running time for the traveling salesman problem can be improved using dynamic programming to only something like to do the end。

I say only even though that's still exponential because really two to the end is quite a bit smaller than in factorial。

 so there's something you can do for the traveling for salesman problem using the techniques we've seen in this class。

 to bring the running time down but not to a level where it's reasonable to solve the problem for moderately large instances like say。

  a thousand cities， two to the 1，000 nanoseconds is longer than the lifetime of the universe。U for。

诶。Satisffiability。You can save off some tiny slivers。

 but morally the fastest algorithm we know for S really is just try every possibility。

See which ones work。Yep。Do know the expression for the back box。We know the expression。

You're given everything there's no hidden details right so if we had a black box so if I had this boolean expression that built into a circuit and have this black box on the table that had a light bulb on the top and end switches in the front。

Then it's easy to prove that you have to try all two to the end possibilities for the switches。

Because an all powerful adversary can while you're blinking change the circuit to make only the setting of the switches that you didn't try work。

But that's not the game that we're playing the glass the box isn't opaque， it's transparent。

 you can see every detail you can have the plans， here's the formula。

 here's you can play with the box with the box open all you want。Still， the conjecture is。

 and as far as we know this is true， you have to try all two to the impossible inputs。

So remember what the goal of designing an algorithm is。For purposes of this class。

It means it always works when we say that an algorithm is fast， that means it's always fast。😡。

It turns out for both of these problems。For a very large class of real world inputs。

 there are heuristics that solve the problem provably correctly， very quickly。

So it is if you actually use， say， the。500，000 largest cities in the world。

And you use you know actual you know profileflized distances between them as as the edges of your graph。

 it's possible with the right software on your laptop。

To compute a provably optimal traveling salesman in a matter of hours。

But if you allow me the all powerful all-knowing adversary to engineer the inputs。

 then we things are hopeless， similarly for satAT a lot of instances of satAT that come up in practice。

 this is satAT is something that's used quite a bit for verification of hardware in particular。

 so I'm given a small circuit that I want to put into an integrated circuit you know in the chip in my new phone。

 I need to test whether this thing does what I think it's going to do。

 essentially can I set the switches so that the light bulb turns on now turns into can I provide inputs to the phone so to make the phone blow up。

😡，Explode。So you can describe this， you can reduce that problem to an instance of satisfiability。

 and most of the time those instances of satisfiability can be solved using practical heuristics in a reasonable amount of time。

But if you allow me to engineer。the Boolean formula。

 then we also know ranges of various parameters for building these formulas where we have no clue what to do other than brute force。

嗯。U。So I'm going to talk about。How we sort of formalize。This ignorance。

Of we think these problems are hard。As far as we know。We can't do better than exponential time。

We can't prove that it's possible that we're all just stupid。

UHanity simply hasn't evolved to the point where our cranial capacities can can actually think about these problems in any reasonable way and we don't speak dolphin。

So that that's where we are with a lot of these problems we we formalize this。😡。

Into something called the theory of NP hardness or NP completeness and goes to the question。

 is P versus NP， but I want to hold off。On defining what P and NPR and instead talk about。

Sort of equivalence。And say， well。So imagine， you know we can there are thousands of these questions where the best algorithm we know runs an exponential time。

 but we don't have attention enough to spend on a thousand different problems。

 so it would be really nice if we could focus down on just a few target problems and say if you can solve that problem quickly。

 then you could solve all these other problems quickly。

So at some level you've seen this idea before when we were applying the strong components algorithm in the homework。

 you had no idea how the strong components algorithm worked for most of you。

 and that was intentional。But you trust that it works and given that you can compute strong components in linear time。

Then you can collect as much candy as possible from Cherry hells in linear time。

So we're going to play exactly the same game and say u。If X。

 and I shouldn't really call this equivalentvalence。

 what I should really be saying here is reductions。If x is。Soolvable。Quickly。Then so is why？Okay。😊。

So we're going to be talking about。Algorithms that prove statements like this。

And the way these algorithms are going to work is I'm going to imagine for purposes of argument that there is a fast algorithm for problem X。

 you have no idea what that algorithm does， it's a complete mystery to you。

 it came floating down some flying saucers landing in the lawn of the White House two weeks ago。

But now that we trust the aliens that left us this algorithm。

 we're going to apply it to solve other problems。系有。嗯。More likely you inherited this。

From an intern that was at the company three summers ago and wrote their code in fluluent Turkish。

Using a language you've never seen before， but everybody trusts it。Um。

 or you're just looking at your own code from a month ago。不见。

So I'm going to start talking about this with a relatively simple example of three different structures that you can find in graphs since we're kind of used to thinking about graphs。

One is what's called an independent set。And the question is， what's the largest？

Independent set in graph。 So an independent set in the graph is a subset of the vertices。

So that no edge in the graph has both endpoints。😡，In that subset。

 so the four vertices that I've marked here， there are no edges between the marked vertices。

That means those marked vertices are independent。So for this particular graph。

The largest independent set in this graph is in fact the one that I've marked as size four。

 so the independent set problem， given this graph， the black box says four。诶。U。

The sort of opposite of an independent set is something called a cleat。

So clique is a word that English is borrowred from French that means， you know。

 a cluster of people who all talk to each other and exclude everybody else。

You've all seen mean girls。Um a clique and a graph is a subset of the vertices where every pairrot is connected by an edge。

Exactly the opposite of independent set where no pair is connected by an edge。And again。

 the question is。What's the largest？Clleique in the given graph。

And the last structure I want to talk about is a little bit different because the question now isn't to find the largest thing。

 but to find the smallest。嗯。And this object is called a vertex cover。

I really wish back in the midsts of time they'd called it an edge cover because it covers the edges。

But it's a cover made of vertices so what can you do a vertex cover is a subset of the vertices such that every edge in the graph has at least one covered end point。

Okay， so you've got different edges in this graph， so this edge for example。

 both endpoints are marked， this edge only one endpoint is marked， but there are no edges。

Where neither endpoint is marked。If I'd added an edge between these two vertices here。😡。

Then that subset that I've marked would no longer be of vertex cover。Um， over here， similarly。

 if I add this edge， those two that that subset of urgencies would no longer be independent。Okay。😊。

So these are three questions where。U。It's not quite completely brute force us。

 you can do a little bit better than the obvious algorithm。

 but the obvious algorithm for maximum independent set is try every subset of the vertices。😡。

And for each subset， check whether that subset is independent。😡，Yeah。

For vertex cover in the same as the。That all all unmarkedtices， neighbor of Mark。Yes。

 so that's an equivalent way of saying that a vertex cover is a subset of vertices to mark them with the property that every unmarked vertex。

Has。In fact， only Mark Des。It's not just that it has a marked neighbor that's something else called the dominating set。

 but has only marked neighbors。Okay。So we can do better than trying all two to the end possible subsets of ver vertices。

 but the best algorithms we know for all three of these problems run in time exponential in the size of the graph。

Okay， so I mark a subset of vertices。That subset is a verts cover if for every edge。

 at least one of its endpoints is marked。I don't have any unmarked to unmarked edges。

Just like independent set， I have no marked to marked edges。Okay， yeah。Yes。

 a clique is just another word for a complete graph。Yeah。Except bus worth covered。A。

 so you're starting to suss out where we're going。Okay so these three problems。

 they're kind of similar to each other， and in fact， we can reduce anyone to any of the others。诶。

So that。😡，The way that these reduction arguments are going to work， again。

 you imagine you have a subroutine for X。But I want you to keep the following joke in mind when you're doing this。

So a physicist and a mathematician are sharing an office。

And the mathematician is very neat and tidy and always keeps things exactly where they go so yes。

 this is a totally unrealistic and the physicist is complete a complete slob he's always losing everything spilling coffee on his papers and leaving his leaving his pipe on his desk and one day。

When the mathematician isn't there， the physicist who smokes， so you know he's a bad guy。

 leaves his pipe on his desk and sets a bunch of paper on fire。

And he panics and after wandering around for five minutes while the flames get bigger and bigger。

 he eventually finds a fire extinguisher。Out in the hallway and puts the fire out and all of his work is ruined。

 he's very sad， but they clean all the mess out of his office。

And then for the next six months the physicist finds。

 oh my god I'm in a clean office I'm so much more productive and then over the next six months the office gets messier and messier a year after the fire the physicist says to to the mathematic oh my God I really miss having a clean office I was getting so much more work done now I'm back to this usual mess and the mathematic quietly wakes stands up walks out to the hallway checks。

 yep， there's a fire extinguisher lights a match drops it on the physicist's desk。There。

 I've reduced it to a problem you know how to solve。嗯。

So I want to show that these these things are equivalent to each other by reducing one to the other。

 so let's describe a reduction。😡，Let's say。From Cleeeek。To。Independent set and both of these。

 really I should put the maps here just to remind you what what we're doing。系。So。

This means I am writing an algorithm to solve the maximum clique problem。Okay， so I'm given。A graph。

G。And that graph it's an arbitrary graph， you know nothing about the graph。

What I want to do is the same thing that we've been doing for graph algorithms all along。

 I want to transform it into a different graph。So that the magic black box that solves maximum In set apply to that new graph gives me some useful information that I can turn into the size of the maximum clickique in G。

系。So I'm going to build。A new。Graph。G prime is v prime E prime。And well。

Can anyone think of how I might transform a graph where I'm looking for a large clique into a graph where I'm looking for a large independence set？

Yeah。是的。你在个不起。Something related to a set difference， I think you're moving in the right direction。

 but give you a bit more specific。So remember， the definition of an independent set is a set of vertices such that no pair is connected by an edge。

The definition of a clique is the subset of otices so that every pair is connected by an image。嗯hm。😊。

Yes， that's exactly right， so the set of vertices is going to be exactly the same。

And the set of edges is going to be all edges UV that were not edges in the original graph。

And this is exactly the transformation that I used。To go， no， it isn't。

So the idea is if I'm looking for。An independent set in。Sorry。

 I'm looking for a clique in this graph。That's going to be kind of boring， so let's see this。

I'm going to transform it。Okay， so now I have edges here， here， here， and here。

I'll find an independent set。In this graph G prime and that will translate。To a clique。In。J。

The reason it's a clique， if I have a clique over in G。

 every pair of marked vertices is connected by an edge in G and therefore no pair is connected by an edge in G prime if I have an independent set in G prime。

 then by definition no pair of vertices is connected by an edge。

Which means that every pair of vertices is connected by an edge back in G。OkaySo in the end。

 a subset a in sorry， a of V is a clique。In G， if and only if A is independent。In G prime。Yes。

So just make sure to take this。It是。就是。I'm reducing Max clek to max independent set that means I'm trying to solve Max glique。

Using a subroutine for maximum independent set。So I'm always reducing from the problem I want to solve to the problem I know how to solve。

Red cherry hell to strongly connected components。有。Earlier， you said that reduction。

 the process of reduction is。Hes lotep。If actually solve more quickly then so is why is that just if or if an O。

 it's just if。😊，It's just an if then it's not an if and only if， I mean。

 you can prove and if and only if， especially because in this case， the same reduction。

Takes an instance of maximum independent set and turns it into an equivalent instance of maximum clique。

Right， but that's。A lucky coincidence for this particular reduction。系。

So what this means now is if I'm given a graph V， then I want to find a maximum clique。😡。

In a ver in a graph with the vertices， this is at most。Well。

 v squared because that's how many edges they're going to be。

 I'm going to let go of counting E and V separately because we're not interested in fine details。

 we're just like pollin omeule or not。Plus， the time for maximum independent set problem again on a graphic size v。

So。If the maximum and that problem can be solved in polynomial time， then by this inequality。

 the maximum clique problem can also be solved in polynomial time。Yes。All of them。

 I don't include all of them， and I include all of the ones that don't exist。

An edge is a pair of vertices is connected in G prime， if and only if it is not connected in G。

That's why the UV not in E。That's over all pairs of U be。Yes。

Because there might I have v squared pairs of vertices。And for each one， I ask。

 are these connected in G？If they are， I don't do anything， if they are not。

 then I add an edge into U prime。I'm sorry。Yes， V prime is V。Because I have to deal with the edges。

There could be v squared edges， and in fact， the number of edges in E and the number of edges in e prime together is v choose 2。

He squared over two roughly。哎。So I drew the cartoon backwards。

 but this is the cartoon that if I want to do the reduction in the other direction。

 we're going to draw lots of cartoons like this， I'm given a graph G。

 I compute its edge complement in quadratic time that gives me that transforms G into a new graph here I called it G bar。

I pass that new graph G bar to this magic algorithm that finds the size of the maximum clique。

 you can tell it's magic because there's a rainbow on it。Um，And that Mag box gives me a number。

And then I just return that number as the output for the in this case， the maximum independent set。

The correctness of this algorithm。Follows from the correspondence between cliques in the graph and independent sets in the complement or independent sets in the graph and cliques in the complement。

Okay， so there are three things。That I need to show you to convince you that this whole mess works。

One is I need to show you the algorithm。😡，This is you build the new graph that's the algorithm。

The other two。Are this if and only if statement？Which in this case is pretty obvious。

 but most of the time is's going to be a little bit more interesting than that。Okay。

So I need to argue that given a clique in G， the corresponding set of vertices in G prime is an independent set and。

I need to argue that given an independent set in G prime。

 the corresponding set a vertices is a clique in G。Even though I'm only transforming G into G prime。

I have to prove。Both that it works one way and essentially that it works in the other way， yeah。Yes。

 I need one for each F， as they say。Yes， I'm proving the two sides of that if and only approved。对。

Let's see if we can get a similar thing for vertex cover。So。I would。Like to。

Let's see how I'm going to peek here， let's suppose that Jeanie pops out of a bottle and says I know how to solve the minimum vertex cover problem。

Now I would like to solve the maximum independence set problem。Ub。

Can you see anything that I could do？To transform an instance of the minimum vertex cover problem into an instance of the maximum independence set problem。

 one person has already seen what to do。And I'll remind you of the definitions。

A set of vertices is an independent set。If。No edge has both endpoints in the set。

A set of vertices is a vertex cover for a graph if every edge has at least one endpoint in the set。

 in other words， no edge has no endpoints in the set。

No edge has any inputpoints in the set versus no edge has zero inputs in this set。Yes。

Take the complement of the set， so if I look at an independent set and I look at the vertices that are not in the independent set。

😡，They define a vertex cover， and this time I actually got it right。Is it the same graph？

And the set of vertices that are marked on the left are exactly the set of vertices that are not marked on the right。

So this is a case where the transformation of the input is trivial， I pass the same graph。😡。

To my vertex cover。Alrithm。But I need to do some transformation on the output。

So here my algorithm looks like this。I take my input graph。

 I'm building an algorithm for maximum independence set。

 and I take my graph and I just pump it straight into the minimum vertex cover magic black box。

 you can tell it's magic because it's got a rainbow on it and that magic black box returns a number K。

😡，I claim that k is the size of the minimum vertex cover of this graph。

And then my eventual algorithm just returns n minus K where here n is the number of vertices。

And again the correctness of this algorithm relies on the correspondence between independent sets in one graph and vertex covers in the other graph。

 but in this case that the same graph， so it relies on the statement that the complement of an independent set is a vertex cover and the complement of a vertex cover is an independent set。

 so two things that need to be proved， again in this case that proof is going to follow directly from the definitions。

Yes。This card that I have a on them are what we're trying to reduce down to yes。

 trying to reduce to the rainbow。Okay， we're trying to build an algorithm the big black box is describing an algorithm。

 I mean I could write this if you'd prefer in a pseudocode， so maximum independent set of G。😡。

let's write， you know， n is the number of vertices of G and I'm going to return n minus。

The minimum vertex cover。Of G。Right so。There is a pseudocode。啊。

But the point is that the subroutine that I'm calling there is something I have no idea how it works。

And it' actually pretty important that I have no idea how it works。

But I just assume that it works and I use it。And again。

 exactly the same reduction goes the other way as well。

 going from vertex covered to independence set。Yeah。没在好的。

Like I don't understand the difference I though。Independence of the city automatically have covered。

发现个 that。Okay， so so this is， I've deliberately defined the problem。

 the way we have for like all dynamic programming problems and all like shortest path problems。

 when I say find the minimum sequence of editing operations， I really mean just find the cost。

 when I say find the shortest path usually I really just mean find the distance。

 when I find the maximum clique， I really mean find the number of vertices in the maximum clique。

In the lab tomorrow。You will see why this this is okay。

 so in the lab tomorrow what you will do is reduce finding the actual maximum clique。

To finding the size of the maximum clique。And in fact， it reduce all the way to。

 is there a cl of size k？Just a decision question。Um，So as usual do for these things。

 once you can have an algorithm that can find the size or the cost of the price， the value。

 or the weight of the object。You can use that as a subroutine to actually construct the object that you're looking for。

And again， polynomial time。Yeah。啊，可以。1 draft another。 in this one。it black。讲定不知道。

So the definition of a reduction is I have an algorithm。

 you write an algorithm that calls my algorithm as a subpperoutine。

You have reduced your problem to mine。就快版。So your runtime is going to be bounded by some function of my runtime。

 so a reduction doesn't need to call the black box only once， it could call it more than once。

But you need to argue that， you know， if my black box runs in， say， N cubed time。

 then your algorithm that uses my black box runs in it most end of the seventh time。Yeah， yeah。

 so you're designing an algorithm。So in some sense。

 every algorithm is a reduction to primitive operations that can be performed by the machine。😡。

Arithmetic memory accesses。conditional branches， things like that。

 then we sort of build up on top of that to oh， if I've got a vocabulary。

 a library of graph algorithms， then there are a bunch of algorithms problems that I can solve by reducing them to reachability or reducing them to shortest paths or reducing them to strong components。

系。U so same thing here， reducing problem X to problem Y just means imagine you have a subroutine for problem Y。

 use that to build an algorithm for problem X。And these reductions that we're going to be talking about here tend to be very。

 very simple in the sense that you invoke that black box subrtine exactly once。

And you transform the input on the way in and you transform the output on the way out。

And that's the complete algorithm。But the rules of reduction allow you to do arbitrarily complicated things。

All right。嗯。I want to walk through another example of a structure and graphs that I've referred to in passing already。

 but before I do that， are there any other questions about sort of the basic idea of what we're doing about cliques and independent sets and vertex covers and hopefully it's clear you can bounce around between them。

Okay。So。The next problem that I want to talk about is based on a puzzle。That was produced。

About 30 years or so before Edward Lucca introduced the towers of Han Noi was。A puzzle。

 those of you who are an ECE majors know this name well， introduced by William Rowan Hamilton。

The same guy who， you know。Uh， did all that Hamiltonian stuff before， you know。

 he gave us what physicists call the Hamiltonian。I have no idea what that means because I'm not a physicist。

To me， Hamiltonian means this thing， this is called the Icosian puzzle。And if you look at it。

 it's a board。Where that has the graph on it。And there's a bunch of pegs that are numbered consecutively from one up to 20。

 it turns out there are exactly 20 vertices in this graph。And the goal of the puzzle。

Is to arrange these numbers so that consecutive numbers are always connected by an edge。7。

 eight eight， eight， nine， nine，10， 11， 12， 13， 14， 15， 16，17。18， 19， 20， and then back to one。诶。Um。

There's a version。Of this that was produced a couple of decades later， which goes by the lovely name。

 the Travelerss Go Decahahedron。Here， instead of having pegs with numbers on them。

 you've got the same graph this time made into this nice little cap shape。

 but you've got an actual piece of string that you're supposed to wind around the pegs in that order to connect the vertices up。

😡，嗯。😊，Uh，So this was like， you have to remember in the 1850s。

 the word graph hadn't been invented yet。Um the， you know， the bridges of Kigsberg happened。

 the Euler did that back in the 1730s。Um， that was that's for what's called the Olearian tour there you want to hit every edge at least once。

Or in fact exactly once， that's a different problem。

Here the problem is to find what's called a Hamiltonian cycle。Named after William Roman and Hamilton。

His name was Williamian Rome Hamilton。There's a million things he hadn't done。Hamiltonian cycle。

 eventually one day I might learn to spell。Okay， so this is a cycle that。Visits。Each。Vertex。

And just to emphasize that cycles don't have repeated a vertices， I'll say exactly once。This graph。

 by the way， is the same graph as the platonic solid， the regular Decedron。

 which is made up of 12 regular Pentagons。And。Is the weird platonic solid that the Platonists used that the Greek philosophers used to associate the Platonic solids with the four elements。

 air， earth， water and fire， the things that get bent。There was never a quintesscent spender。

In Avatar， that was really unfortunate I wanted somebody to throw Dedeca he drew around。嗯。

But it was weird because this is the only regular solid that has Pentagons for faces。Um，Okay。

 but the the more general question is。Um。Given。A graph。G。Does she have？A Hamiltonian。Cycle。

This is kind of a 001 version of the traveling salesman problem。

The traveling salesman problem is really asking you， you've got a weighted graph。

 find the Hamiltonian cycle with minimum weight。Here。

 I just want to know whether Hamiltonian cycle exists or not。

So you could think of it as the edges have weight one and all the pairs of vertices that don't have edges think of those as having edges of weight infinity and now I've just reduced the traveling salesman problem。

 I've just reduced Hamiltonian cycle to the traveling salesman problem。

 but let me stick with the Hamiltonian cycle problem。

 but the observe that there are two kinds of graphs。

There are directed graphs and they're undirected graphs。And it's possible in principle。

That someone might come up with an algorithm that finds Hamiltonian cycles in undirected graphs。

But doesn't know how to do it for director Grs。Or they find an algorithm for directed graphs。

 but they don't know how to apply it to under graphs。

So what I want to do for the rest of the lecture is show reductions between these two versions of the problem。

 one of these reductions will be pretty straightforward。

 the other one will require a little bit more cleverness。😡，Yes。Okay， can't you just call DFS， no。

 DFS will find some path。it won't necessarily be anlonian thing。Sorry。Yeah， so your， I mean。

 essentially DFS is the greedy algorithm。It grabs whatever edges it can and whatever it wants and it doesn't care。

It's true that if you order the edges within your data structure。

 if you order the edges in each list of incidences。😡，In the right way。

Then a depth for search will trace out a Hamiltonian cycle。

But you're not guaranteed to be given that right ordering at the beginning。

 you're just given some representation of the graph。一。It's not a Dg。

 so you can't run the longest path algorithm for DAs。DagGs don't have Hamiltonian cycles。

 so for if the input is a daAg， the answer is no and you're done in constant time， well。

 you needed linear time to confirm that it was a daAg。

So it's this question is only interesting if there is a cycle in the graph。Right。

We don't know of any sub exponential time algorithms， I shouldn make this very clear。

 this is one of these problems that on Thursday we'll label NP hard。😡。

We do not know of a polynom time algorithm to solve this question， even though again。

 for practical real world inputs， we do know we can solve it， but if you can engineer the input。

 then we don't。诶。So let me first。Going to reduce。Undirected。Hamiltonian cycle。

To directed Hamiltonian cycle。Okay， so I'm given。An undirected graph。哎。😊。

Now what I want to do is derive。A directed graph。Construct。

Such that G has an undirected Hamiltonian cycle。If and only if G prime has under a directed Hamiltonian cycle。

ok。This is the outlinela of my algorithm。Okay， my reduction。

 I'm just going to try to transform the input and pass the transformed input to my black box that computes finds Hamiltonian cycles in directed graphs。

This one I think you should be able to figure out。So I'm going to give you another example of a graph。

That has a Hamiltonian cycle in it。This is earth。The element， this has a Hamiltonian cycle in it。

 I'll let you think about it， but the important thing is somehow I need to transform this into a different graph。

That's directed。And because this has a Hamiltonian cycle in it， so does the new graph G prime。

 and if I start with a graph that doesn't have a Hamiltonian cycle in it， like say this one。

But then the same transformation will give me a directed graph that has no Hamiltonian cycle。

Any ideas？第二。😡，Yeah， I think you're on exactly the right track。

So the idea is I'm going to keep the same vertices。But for each undirected edge in my original grass。

I'm going to add two。Oppposing directive edges。In my new graph G prime。对。呃。

This is going to get a little crowded。and let's throw this one in for good measure。Okay。

 so that's actually my reduction。Yeah。So could you expect what it means？

She reduced one came two the fun out there。'mIf I'm reducing x to y。

 that means I'm trying to write an algorithm for x， using an algorithm for y is to subppertain。

So here I'm trying to reduce undirected Hamiltonian cycle to directed Hamiltonian cycle。

 that means I'm trying to build an algorithm to find Hamiltonian cycles in undirected graphs。

Using as a black box， an algorithm that finds Hamiltonian cycles in directed tracks。系啊。Now。U。

The the I need to prove that this actually works， so let me start with with an example that does have a Hamiltonian cycle and。

So let's start with your favorite Hamiltonian cycle of the cube。Okay this visits every vertex。

 a Hamiltonian cycle is first of all it a cycle meaning it's a sequence of vertices where adjacent vertices in sequence are connected by edges and the sequence ends where it started so I could say start here this upper left corner I could do the same in G prime。

 I follow this edge back， well there's an edge there I could follow back。

 I follow this edge to the left。I can literally just translate and I'm using the word just， I think。

 justifiably for once I can literally translate。The Hamiltonian cycle I get G into。The same。

Hamiltonian cycle I get in in G prompt， so you would say something like you know A D， C， D， E， F， G。

 H would now go to A， D， C， D， E， F。G。H and then back to a right so every edge that shows up。

In the undirected Hanniboltonian cycle。Also shows up in the right direction in this structure on the right。

 so there's a Hamiltonian thing on the right。Okay， so that's the。I proof。

The only of proof actually goes the same way， if I imagine that I have a Hamiltonian cycle over in G prime。

 I just ignore the edge directions and I get a Hamiltonian cycle in G。So again。

 the proof in this case is pretty straightforward。Did you have a question？Oh。

I more life in previous over days。We talked about Hamiltontonian tab。So is that empty card， yes。

The Hamiltonian path problem is also NP hard unless the graph is a dag and then that for search wins。

Okay， so what this reduction says right， is， well， if you can do the directed case。

 the undirected case is easy。嗯。Let's imagine now going the other way。So if I want to reduce。

The directed Hamiltonian cycle problem。To the undirected Hamiltonian cycle problem。

I need to be given a directed graph。I need to build。An undirected graph。

UG prime such that G has a Hamiltonian cycle， if and only if G prime has。A Hamiltonian cycle。

And one thing that's sort of tempting to do here is to try to mirror the reduction that we already did。

 take your directed graph and just ignore the edge directions。Because after all。

 if I've got a Hamiltonian cycle in the original directed graph， when I ignore the edge directions。

 I still get a Hamiltonian cycle in the new undirected graph。

 the problem is that that simple reduction doesn't work。

For all in both the proof does' not work in both directions。

Here is a directed graph that does not have a Hamiltonian cycle in it。

But when I ignore the edge directions， suddenly the new underdirected graph does have a Hamiltonian cycle in it。

 it just go， b around the square。Okay， so it's very。

 very easy to be misled when you're designing these reductions into thinking the reduction works because all the good instances work。

You also have to remember that the bad instances are supposed to work as well， meaning bad examples。

 things where you want the correct answer to being no actually should answer no。

Okay so I have to do something a little bit more interesting。So this。This idea。

 you know that doesn't work。So what I'm going to do instead。Is I'm going to replace every vertex z。

With three vertices。V0， v minus and v plus。And these are going to be connected into a path of length too。

So v minus is connected to v0， v0 is connected to B plus。And then for every。Edge。

In my original undirected graph。It's from you to the。I'm going to connect。U plus。To v minus。哎哎。😊，So。

This little cartoon here defines my reduction completely。There are three V vertices in G prime。

 every vertex in G has now three copies， which I'm calling the v minus d0 v plus。

Think of it as a product construction if you like， but the edges are not following the product construction。

 instead there are two types of edges， they're edges between the copies of the same vertex。

And they're edges connecting copies of different vertices， but I always connect。Sorry。

 this is a directed edge this is the original graph is directed， so if I have an edge from u to v。

 that's going to correspond to an edge from u plus to v minus。If you prefer。

 think of plus as out and minus as in。So I have an edge going between U out and V in。

Because the original directed edge is going out of you and intoV。So if I apply this reduction。

I get something like this， so on the left I have a lovely little directed graph with 10 vertices and 15 edges。

And on the right， I have the corresponding。Directed graph that my reduction is going to build。系。

So the number of。Vertices in the new graph is three times the number of vertices in the old graph。

 and the number of edges in the new graph is 2 v plus E。ai I can build this thing quickly。

YouBy brute force。Okay。Now， I claim。That this graph on the left has a Hamiltonian cycle。

 if and only if this graph on the right also has a Hamiltonian cycle。

 so one direction of this proof is actually going to be relatively straightforward。

So here is a graph。A Hamiltonian cycle in the original directed graph。

I'm going to mark a couple of these vertices just to give them names。And I'm going to also。

Thiss b minus b0， b plus， this is W。Go from plus to minus， yes。W zero W plus。Okay。

 I'm going to look at a small portion of this corresponding structure that I built over here。

 the way that I've defined this， som given。U VW。Et cetera， eventually back to you。

 this is the Hamiltonian cycle。We have the corresponding structure。

 u minus to u0 to U plus to v minus to v0 to v plus to W minus and so on。

 eventually coming back to U minus。So I traverse each of these little vertex gadgets from one end to the other。

 and then I between one end of one vertex gadget and the other end of another vertex gadget。

 I follow the edge corresponding to you KV。Of。By definition。

 this cycle over here in purple on the left visits every vertex， and so by construction。

 this cycle over here on the right visits all three copies of every vertex。

 which means the cycle actually goes through every vertex in the graphraq prime。Yes。

How you know it in the second radocent visit？Right， remember what I'm trying to prove。

Right now I'm trying to prove my claim one。If G。Has a Hamiltonian cycle。

 then G prime has a Hamiltonian cycle。So what I'm doing is given a Hamiltonian cycle in G。

 I am going to construct。A Hamiltonian cycle in G prime。

 but I'm in completely control the Hamiltonian cycle in G prime。For purposes is this proof？

And I'm telling you how I'm going to build that Hamiltonian cycle。Does that make sense？看。Um。So。

By assumption， this cycle in purple on the left visits every vertex， so by construction。

 this cycle in green on the right visits every vertex of G prime。

 and you can check that all of the edges that I've put in that green cycle really are edges that are defined by the reduction according to these rules。

So this really is a Hamiltonian cycle in G prime。That's the easy direction for the reduction， yeah。

To make the reduction work in the other direction。Right so the question was why did I bother with G with the middle copy v0 because I could have just gone straight from u minus to u plus why did I introduce the other thing and the answer is the reduction doesn't work if you don't put those in。

 the central vertex v0 actually plays a significant role in the other proof。Okay， so。Claim two。

G prime has a Hamiltonian cycle that implies that G has a Hamiltonian cycle。So it's again。

 tempting to look at this picture over here on the left and go， well， there's a Hamiltonian cycle。

 and I can drag it back， but there was a very important question over here。

 what if the Hamiltonian cycle in G prime doesn't have that structure？😡。

I don't require Hamiltonian cycles， the definition of Hamiltonian cycle just says I have to visit every vertex in the graph。

 it doesn't say I have to follow this particular pattern。

 so what I need to prove is that every Hamiltonian cycle in G prime follows that pattern。😡。

And then I can undo this transformation， so G prime has a Hamiltonian cycle， let's call it C prime。

C prime has to visit。Every vertex and in particular it has to visit v0 where v's your favorite vertex of G。

 so here's v0， it has to visit that vertex。But that vertex only has two edges connected to it。

One going to v minus and the other going to v plus。Okay， so see visits。

Either v minus then v0 then v plus， or if it's v plus then v0， then v minus， I don't know which one。

The graph is undirected so either one could work。Oh wait， the graph is undirected。

 so if there's a Hamiltonian cycle that visit visits the vertices in order plus0 minus。

 I could reverse that Hamiltonian cycle。And get one that visits things in the other order， so this。

 you know， I can assume without loss of generality。Otherwise。Rverse。The cycle。ok。😊。

So I visit v minus v0 v plus， in fact， I visit that for every vertex v， so I've got a u minus。😡，Well。

 okay， let's just say I visit this。系。Now， what are the other edges connected to V+？Well， V plus has。

Edges going to be zero， but otherwise they only have edges of this second type here going to other vertex gadgets and in fact。

 always going to the minus vertex of that other vertex gadget。So after。The plus。

 it must visit some W minus。But then it has to visit at W zero and W+ by the argument that I've given already。

But then it has to visit some x minus。But then it has to visit x0 and x plus and then it has to visit some y minus。

So see crime。Tverses。Every edge gadget。The same way。By induction。

You thought we were going to get away from induction， no。So after traversing one edge gadget。

 v minus v0 v plus。The next edge must lead to a minus vertex。

 and then you're in some other vertex gadget， but you know the Hamiltonian cycle traverses that vertex gadget in one order or the other。

So the next thing it must go to after w minus must be w0 and then w plus but then after that。

You repeat the argument again， I must go to a minus vertex and then I must go through the vertex gadget and I must go through the minus vertex。

 I must go through the vertex gadget。So by induction。

 whenever I leave a vertex gadget through a minus vertex。Through a plus vertex。

 I must go to an invertex in the next gadget。And so that means that the Hamiltonian cycle has exactly the structure。

That I've illustrated here。It's exactly the kind of thing that I would build from a directed Hamiltonian cycle in the proof of Cla one。

And so that means I can pull the Hamiltonian cycle that I found in G prime back to G。

 and now the same arguments from claim1 implied that what I get is Hamiltonian cycle in G。Right。

So this is where what most of our reductions are going to look like。😡，We take the graph。

And we build a new graph by composing a bunch of quote unquote gadgets。

 I have a piece of G prime that corresponds to each vertex of G。

 I have a piece of G prime that corresponds to each edge of G。😡。

And then I have to build those gadgets in a way that force。In this case。

 Hamiltonian cycles to have a particular structure。

That enforces a correspondence with the same the right structure in G。系。

I do recognize at this point this is a firehouse。We will have many more examples of this kind of thing。

In the labs， in the homeworks， on Pra learn， in the lectures， it will get easier with practice。

All right， thank you， see you on Thursday。2。One thing I know this is that I'll be started with。

The claim that。And。

![](img/5185d70d8db0b63317db9ccaf3573080_6.png)