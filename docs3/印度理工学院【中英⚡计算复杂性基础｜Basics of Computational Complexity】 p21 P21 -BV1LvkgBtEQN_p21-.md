# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p21 P21 -BV1LvkgBtEQN_p21-

![](img/2d1958155f57de7e2a04db488b308500_0.png)

So in the last class， we proved savage's theorem。So， end space。Cllaus is really。

Simable by efficient space， S becomes a square。In particular， N p space is equal to p space。

So non determinism doesnt really help。If you are。In a class。As big as piece piece or bigger， and。

Yeah， so we also looked at this configurations tree。

And this will give us a new way to define small complexity classes like Nl。

So this configuration tree is you start with this。Start configuration。 and then。

You proceed downwards from the root of this tree。In each step， obviously。

 you have two possible configurations because of non determinism。

So I left as an exercise to compute the size of this configuration tree and to actually。

Check or test reachability in2 race2 s time。And that much of space。Okay。What we have shown above。

Is actually just a space in a space， we can。Solved reachability。 Sorry， a square space。

 we can solve reachability。But for a square space， how much will be the time So time in the worst case can be tourist risk to a square。

RightSo if you want to reduce the time by increasing the space。

 that question is the space time trade of question。For the reachability problem。In directed graphs。

 because this graph is directed。So let us look at N L now。 I don't remember whether we define it。

 Let's define it here。So an is the class。In space。Loin。Okay， it's non deterministic space login。

So which you know， is contained in。Space lock square in。That much we know， but。

We are actually more interested in comparing it with space login。Okay。

 so how does n space compare with space。Loan。Without。Without this blow up， is this blowup necessary。

That's the question we are interested in。 Also， another thing that you can see。

Is that lock space is in nL that is immediate by I mean。

 that is by definition because space login is obviously an end space login。And。

This Nl is actually in。But로 밀다。Why， because it's simply a question of reachability， right。

Or maybe I should not， I should put it differently。 So what is the number of configurations。

So number of configurations is。Do this do。B go of login， which is。Enre 2。

Constant so number of configurations is only polymial right So whatever you can do you can do in polymial time。

So this means polyan time。So。It's solvable in polymial time。So N L is in P。

 this also follows from the， the relationship between。Space and time。

we had shown at some point that space translates to spaces translates to tourist to us。Time soup。

This is a similar。Argument。So N L is somewhere between lock space and polymial time and probably much closer to lock space than polymial time。

 but we don't know by how much。So for let's now study problems。A problem that is the hardest in N L。

Sou。For a meaningful notion of hardness。In Nl。We need。Lock space reductions。

And not polymial time reductions。Right why not polymial time reductions because polyial time reduction polymial time is bigger than。

Mil， so。Obviously， every problem in L can reduce to any other problem。In Nl by polynomial time。

 because everything you can solve independently in polynomial time。

 So to have a notion of hardness here， which is more meaningful that is within the word of Nl。

You have to actually de restrict your reductions and we re restrict them to all the way to lock space。

It lock space is smaller than it is contained in NL。

 so that will be a more useful notion of production。And based on that。Let's do the definition。

So call a function。Stringings to strings。Implicitly illcomputable。Psitly ill comfortableut if。

So intuitively， you want to call a function call F。Implicitly illcomputable if the Iath bit。

I is in lock space。Wait。So， that is what we will see。If the language a。Which is input。String x， I it。

Location。Is one。😔，And。The language， E prime。Which is。Again， in put string X I location。

The length of effects。Is at least I。So LF prime is test checking the length and LF is checking what is the。

Kind of think of the last bit。Okay， so if in the case， when the length is less than9 then。

 there is no point asking for right bit。So you can think of this as checking the length。

 whether it is at least I and then asking for a bit， both these problems are solvable in lock space。

When this happens， then we say that f is implicitly illcomputable because I every bit can be computed。

In lock space。 Okay， So this is something very natural。Tings surprising here。

And we call now we define reduction。 So we call。E reduces in lock space to B。If there exists then。

Implicitly。L computable。If。Such that for all input strings。X is an E， if I only leave。F4 x is in B。

So this is expected if you recall car production。This is exactly the definition A reduces to B。Yes。

 string maps to a yes string and vice versa image if yes， if only。The pre imagess， yes。

Except that F is now very restricted。 F has to be an implicitly illcomputable function。 and finally。

We call B。And he'll complete。If。😔，B is in Nl。And。For all e。In N L， N L E reduces2。B。😔，Just so。😔。

B will be called NL complete if B is an NL and every problem。In N L reduces to B bio implicitly。

L computer。 I mean， there is a lock space reduction， basically from E to B。 Okay， so let's now。

Discuss some quick proper properties。That we can deduce。E reduces to B reduces to C。

Lock space reductions， then e reduces to C。Right， this seems。Ovious from the face of it， but。

Its not completely trivial because remember that its lock space reduction is only implicitly illcomputable。

Su。😔，And it's a very weak kind of reduction。 It's a very restricted risk reduction so。You。

X in E will have to be mapped to first F of x， F1 x。In B， and then F 2， F1。Exll C。

But you don't have enough worktape space to store the whole output。Right。

 so you have to do this bit by bit。 That's the problem。And second property is。If E reduces to B。

And bees in lock space。Then E is also in lock space。Okay， let's prove the first one。As I said。

 it's not completely trivial。So late。FGB。Ilicitly。L computable。Functions。Then the claim is that。

G composed with F。Is。Alsou。Implicitly illcomput。Okay， why is that？

 Why is the composition also implicitly illcomputable， So the proof for this is。So。

 while computing F of x。Or I should say while computing G of F of x。So why computing。Gufei。😔，嗯。

If you need Y， whenever you need Y。呃。Do the F of X computation。Okay， so you think of。Just。

Computing a bit of G of y。And while computing the Gth bit of G of y， whenever you need some bit of y。

 lets say Y I。Then， you do the。F of x computation for finding that bit。Okay。Now。

 each of these computations， they only require log space order login space。

 so order login plus order login is order login。So this means that space needed。Okay。

 so that's the final space。 You can actually compute。I G bit。Of the composition。Also， in lock space。

That's the major idea here。So once you have done composition， then you have reduced a to c。

So this implies that a also reduces to C。Right， and what was the second one。So in the second one。

Bees in lock space。Right so same composition rule tells you。That。

You can actually solve a also in lock space。The composition rule implies。That is in lock space。

Because bees in be is computable， so。You will reduce A to B and then use this subroutine。

To actually solve it。Right， so， so lock space is a very nice。Reduction idea。RightPreviously。

 we had used poly time reduction。 now lock space will。

Be a very good substitute for these small classes like an N L。 So let us now see。Lixien。

An L complete problem now。So， this will be。So remember， the way we motivated Nl。

Was via reachability in a tree。Right， so reachability is the。Is a good candidate。

 So let's define path。To be。Graph and2 vertices S。So that S2 D there is a path。

So this should be called actually directed path， but will continue with this name。

So path is given a directed graph and two vertices source target that there is a directed path。Okay。

 these are the yes。嗯。Instances， so， obviously， this is。I mean。

 practically it' is a very simple problem。 you can actually solve path in linear time。for time wise。

 it is quite easy。嗯。But suppose we want to optimize space。As much as possible。

So is this linear space the best or is there better。Space complexity for this problem。

And that is what we will answer。Or that is what actually will formalize。So， first， we show。

That path is in。Anl。Okay， so actually with non determin guesses， you can solve it in lock space。

Just directed reachability problem， path problem。 So why is that。Well， because you can just guess。

The path from a2。Let you keep guessing。You will only need to get log bits for one vertex。

And with every guess you will move to a neighbor and maybe you will move to you will end up in tea starting from us。

Sot GST。Be an input instance。Each vertex。Can be identified。Bo。In log g space。Right，There are。

Vertices many。I mean， size of G many vertices are there and。So log of that is the amount you need。So。

 I mean。Technically， it's the ceiling of this， but this we generally ignore because of the asymptootics。

But seal of this many bits will be will suffice to。嗯。Index any vertex。

So you just have to guess for a neighbor to guess a neighbor。 You just need this much。

Of non determinism。Then from a vertex， you can move to the neighbor。So this means that N DT him。M。

That simulates。Ofvokinji。With origin S。And accepts。On reaching tea。So， this N DTM M。

W just keeps guessing neighbors， neighbor of us， then neighbor of neighbor of us and so on。

Ending up ending up into accepting。So this has space complexity。Big go login。Right。

 which immediately implies that path is in Nl。So， we have shown that directed reachability problem called path is in is in nl so the optimized space will be actually log if we can remove the non determinism。

Then the correct space is log。R， which is an exponential improvement， if we can do it。

So can we do it。That's the question。嗯。So， can this be。Really made。Loin space。So， let me instead see。

Space logging。Unlock space。Great， so then it will be a practical algorithm which will only require lock space。

Time will remain polyial time， but。Space will drasticly improve。 So is this possible。

So keeping this in mind， this motivation in mind， we will show。

That this question really depends on n L equal to L question。

 So we show that for every language in Nl。Actually， E reduces two path。Okay。

 so Nl actually path is Nl complete。So if you can solve path in lock space， then you can solve。

N L in L， N L will become equal to L。Right， so depending on whether or not you believe in the algorithm。

Lock space algorithm for directed reachability。You also have to believe when equal to L or not。

So how do we do this reduction。So this will really go via the configuration tree。Okay。So， let M。

B and DTM。Deciding E。In space。D login。Will die a constant。So， so let us now。On an input GST。

 Gcom comma T。嗯。Or input X actually input x for the problem a lets convert x into a G commerce command to a path instance。

Based on the configurations of M。So， consider an f。That maps。In protectex。Of一。To F of x。

Gcom mass comm T。But instance。Where。G iser。Configuration graph。Of Emex。Yes。

 we are now looking at this configuration graph or also configuration tree。As we saw before。

So what are the details of that？So， vertices of G。Are all the configurations of M X。Right， so M of X。

For example， starts with the start configuration， then moves to two options。对。😔。

Each of those move to two more options and so on。 end up in either。Acept or reject configuration。

Depending on whether x is in E or not。So， that configuration tree。Vorertices。

Become the vertices of G。Second is S， and T。Au。😔，The start。And accept。Configurations。Dpectively。

And when is there an edge。Between two vertices。So。An edge。C2 c， prime。Is there in the。It set of G。

That's the vertex set。And there is an edge C comm C prime of。Basically， CNC prim configurations。

In that set， if。And leave。C to C， prime。Yu。Valid transition step。Of Mx。B single transition。Not bad。

So， there is an edge C2 C prime if and only C to configuration C2 configuration C prime is allowed by the transition function of M on inputex。

So that is the complete description of this directed graph it is obviously directed because c to c prime being an edge doesn't mean that c prime to C there is an edge。

Right this the computation， the transitions may not be。Reeversible。And you can conclude immediately。

That x is an a。If and only leave。This。GS Gcom come instance。Ist pot。It X is in a means that。

There will be an accepting path， which is what G Commerce Committee path sees。This is clear。

 The other important thing is。How fast can you compute F。So， that's the claim。That F is。Implicitly。

L computable。So why is that， Why is F implicitly illcomputable。So， this idea is that。First。

 the list of our diseases。They are allcomputable。So what to see so。The configurations。

 basically right， list of configurations， you can assume in some order。

And when you want the I a bit in a configuration。呃。In that order， you can just assume。

The definition of a configuration for the Turing machine， M of x。Right， so in the configuration。

 you have the you have the state。The tape information and all that。

 So those things can be just encoded。Properly。So， use。Order them。And use。

The definition of configuration。Just by this， you will see you will be able to imp implicitly compute。

The vertices。Indexing a configuration will be easy because the number of configurations is polynomial。

8。😔，So， that's important。And then。Given C commercemer prime。Testing。Weather see to see prime。

Is a transition。Whether this is a transition。Of M X。Requires。Linear space。Right， so C。Is。I mean。

 the configuration space is basically dependent on the work space， which is log。

So this whole thing is in。Is2 billion in lock space。 You just have to compare the entries。

In basically one position to see whether c2 c prime is valid。Right， so that is。Again， log in space。O。



![](img/2d1958155f57de7e2a04db488b308500_2.png)