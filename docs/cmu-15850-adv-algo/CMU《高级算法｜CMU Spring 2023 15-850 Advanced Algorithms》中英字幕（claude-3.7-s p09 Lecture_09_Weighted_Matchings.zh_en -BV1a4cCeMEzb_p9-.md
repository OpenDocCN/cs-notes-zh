# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p09 Lecture_09_Weighted_Matchings.zh_en -BV1a4cCeMEzb_p9-

还一个就。你 ok。对。So a couple of announcements sorry I'm the person responsible for the slow release of homework zero grades I meant to have one quick look over it and the weekend got away from me so in any case once I get back to my office I'm going to release homework zero the graded versions some of you you know some of the answers we might say oh we don't quite understand what you are doing feel free to come back to us and explain it to us if you think that we've been too harsh。

😊，homeworkomework  one， I guess， was due yesterday。

Hopefully that went okay and homework too is going to be released。Pretty much again。

 when I get back to my office。做啊。So those are the things which have to do with the mechanics of the course。

As than that。We're going to。Okay， we' are going to talk some more about matchings。

 So thats the that's the fun part。 And this is going to be the third lecture in matchings。

 They probably will be a fourth lecture on matchings。😊。

Just because you know there are so many different techniques I want to tell you in the context of matchings we have seen purely combinatorial algorithms just augmenting paths。

 we saw how to find large matchings， we saw an algorithm last time using matrix methods。😊，You know。

 the determinant of a graph。The determinant of the adjacency matrix with suitably you know added variables is is a non zero polynomial and you can use that so that's low versus idea。

Today， they're going to see。We're going to see some linear programming based techniques。But。

 before that， I will。Yeah嗯。Review some linear program ideas just to make sure that youre all you have it fresh in your minds and we'll see。

We'll see arguments based on linear programming。In the next lecture。 So this is。Today and Wednesday。

 in the next lecture chances are well talk about ideas using markets。So， you know。

 I'll define a market and people will come and make bids and then prices will rise and eventually goods will get sold and goods will get sold from a matching and you'll somehow find a matching that way。

Good， but today let's just start talking about linear programs and for the first you know15 20 minutes or so I'll just remind you of some very you know basic facts about linear programs maybe I'll even just follow my notes。

😊，嗯。Okay， so I'm not going to。Actually， you know what， more， yes。就。Let me just draw some pictures。

Yeah。So I'm always going to be talking about linear programs in our。嗯嗯。

And so remember what a linear program is， it's a object of the following form。

 minimize a transpose x where a。嗯。Is， you know，'m sorry， C transpose X， such that A X。

 A X is greater than equal equal to B， let's say。X is not negative。And here， x is a vector。啊And。

So is A， so is C。嗯嗯，没。And E， the matrix。Then R n across N。And the picture， of course， is I have。

M rose。And goes。What happened？The is。嗯嗯有人按自6有。And I'm going to multiply it。那得。Vectctor x。

 so this is A X。Is a key。B。And I have。C sitting out here， C transpose x is my objective function。

 A x is at least for B。😊，So basically， I'm taking the first column of。A and multiplying it with x1。

 the second column with x2， the last column with x n， summing it up， and it must dominate。

And often I will say x is my negative and this is just its a vector inequality。😊，没有。

What is this really？😊，You know。This is， this is a bunch of。Ha half space constraints。

 So if I look at the first row， the first row of A I'll often write as little a1。

 So I'm really saying A1 transpose x is at least B1 A2 transpose x is at least B2 A M transpose x is。

Yeses。So n x is non negative， let's say， so what I'm saying is if this is my space。

 then I want to be in the positive a。And then， maybe I want to be。On this side。Of dis inequality。

 So maybe this is a1 transform x that least B was。 Maybe I want to be on this side of this inequality。

 And， of course， the non negative。Constraints say， I want to be on that side。

So a bunch of half space constraints。Each half space is a convex region。

Intersection of convex regions is convex。 This is a convex body。In particular。

 this is actually a pony。He准。A polyhedron is just the intersection of a finite number of half spaces。

A finite polyhedron， a bound poly sorry， a bounded polyhedron。It's called the poly。Poornycle is just。

唔啱这。玻璃手机。아。That there is some big enough ball such that this polyhedron is completely contained inside that。

Yeah。H。I'm just going fast because I'm assuming that you guys know this and this is just a refresher of the terminology。

But slow me down if you， and if you， if you。Unfamiliar with any of this。So， this。Reion。

This thing is defining。A body heat。And what am I saying， so， you know。

 another way of writing this is。Another way of writing the LP is I'm saying minimize C transpo x。😊。

X belongs to K。The case in general， I will always use K for convex K the convex body and in this case this is the polyhe。

😊，Given by。At least B。咩。对。So amongst all these points。

 I want to find the one which minimizes this cost。And how do I do that。

 La uses algorithmal linear programming。嗯。Now， one thing that will come up again and again is that in order to find。

To solve linear programs。Instead of looking over all the continuum of points inside there。

 I can look only at the corners。😊，And the cos are exactly these points and you know in two dimensions the the optimal solution you can even geometrically view this thing that the optimal solution should be at one of these。

😊，Locations。And these corners， there are three ways in which you can define them。😊，And we will call。

 so this is called a verortex。Or sometimes it's called an extreme point。

Or sometimes it's called a basic。工资中心。Maybe I'll give you the three definitions。

There are three ways of defining the corners of this。我的。So me let me give you these definitions。嗯。

Let it start with the extreme point。So maybe I moved this up。Actually， yeah。

 I have to move this down。ごな。走。X is an extreme point。哦。Okay。If。For all X。Which can be written as So。

 So if， if， if。For all ways。All writing。X as lambda times x1 plus。And slammed back。と。With lambda冇咩。

With calendarda。And one。Every way of writing X is a convex combination of two points。Mt mean。X in。

Basically， the only points whose convex combination。So if I can write。

X as a convex combination of two other points in my convex set， then x is not extreme。Yeah。

There's an extreme point。X is。So the picture is pretty much what you。I think it is。

This point is not extreme because it can be written as a convex combination of this point on this。

This point is not extreme because it can be written as a convex combination of these two points but this point is extreme because how else are you going to write this this point of the convex combination if you choose any two points out here it is not going to give you the point。

By the way， why am I giving you these definitions because these definitions， by the way。

 those three concepts are exactly the same。😊，There are just three different ways of defining corners of the polytop。

And in different situations， youll use different of。And sometimes you'll be like， oh。

 I want to argue something about the corner of this polytop。

 How do I argue which definition should I use。And you'll use one or the other。

Let me give you another one， X is a verortex。If they exist。A cost vector C。Such thing。See。

Brons space x。It's strictly less than。C transport joy。我打开喂。To k x is the verortex。哦，对。

If there exists cost vector。Such that C transpose x is less than c transpose y for all y N k。

X is a unique minimizer。Of the linear form， C transpo x。What points。This guy。

 if I were to take the cost vector going in。That direction， lecture。The cost is increasing。

You knowSo so the image I have in my mind I you know。

 I always keep telling you what's the image that I have in my mind whenever I say， you know。

 this is C。😊，Really。All the points。On the Hyclaim or terminalmil to C。Have the same cost。

 Their C transpose x is the same。SoEverything on this hyperplane is exactly the same cost。

And so as I am sweeping this hyperplane orthogonal to see。😊，The cost is increasing。

I want the least cost， so I want the hyperplane that is orthogonal to see thats for this to the left。

That contains the point。应该。응 몇 수 분。回开。😊，不。X is the alert。These are like generalized。

Like I guess we're giving them different names， but like it caves like an arbitrary set of points。

而对拿。哇。Think about that。The next definition definitely will you know is very specific to linear programs。

 but I have to think about。😊，think they should generalize nicely， but。啊。

So let me give you the third one。啊。X。Its。你不会思的。一直都分6。对对要对。就啊。就。Okay。We to given。买你。And given by。你有没。

Dstraints。系。嗯。A。可以看。So I'm talking about polyhedron。Given by a bunch of linear constraints。嗯。

That exist。Okay， X， remember， belongs to R N。Let's look at this picture。I want to say， look， X。Ls on。

This is this was some constraint A1 transpose x was at least B1。This constraint was saying， oh。

My feasible region lies to the right。Here is another constraint。E2 transpose x is at least B2。

The constraint was saying my physical region lies to the right。

The other three were three other constraints。The good thing was， x。

Satisfied these two constraints with equality。And it satisfied all the other constraints。

So I want to say x is a basically visual solution if that exists n。😊，Pnially independent。Constraints。

In this system。嗯。Let's call this。给啊。A1 transpose x is equal to B1。

So there exist and linearly independent constraints in this system。That。啊。Satisfied。嗯。你过了。Often。

 these things are。The jargon is their tight。嗯。嗯。啊，哼。😊，哎哎。Break down， not to icy。Interesting。

 so definitely they do seem to generalize the convict that you're absolutely right。😊，嗯。Yeah， okay。

This one is very specific to linear programs。 so let me yeah that makes it easy for me Okay。

 so Im saying there are linearly independent constraints that are satisfied at equality。

 So basically there are constraints of the form AI1。😊，Transpose x is equal to bi 1。Et cetera。

 AI N transpose x is equal to BI N。And， of course。嗯。哦，系的。Contrain。A side的 friend。

better satisfy all the constraints。But their N linearly independent constraints are satisfied as equal。

 that they are tight。In this case， these two linearly independent constraints were satisfied that equal they were tied。

😊，嗯。Baically information。Feaasible just means it satisfies all the constraints。

 The basicness is just coming from this。And all this is saying is that， look。

 what I can do is remember that that the drawing that I made of a。😊，X is equal。 A was at least2。

By reordering the constraints， I could just imagine。

That the first n constraints that were tied with linearly independent constraints are sitting here。

Well calline。A sub capital B， not to be confused with little B， B for basis。Okay。

So there are n constraints here。 remember， there are n columns and the first n rows。

Are linearly independent。And similarly， you know， whatever reordering I did out here。

 I can do the same reordering out here。😊，我。So what am I saying， I'm saying X。Satisfies。AB。

Times x is equal to B。Okay。And of course， x is also satisfying the rest times x is at least the rest。

😊，But in particular， satisfying this。Atality。Yeah。Give the square matrix。Lly independent roads。

Pull rank。Invertible。So this just means that I can write x as A B inwards times B。

And this the same x is rootd。Heby。英文先。So this fortune a bes。Giving you a basis of the space。

That you can use plain word the system and figure out text。So， for instance， this already gives you。

😊，A polynomial time。なルポリノミイム andあるけれどもァイナイあるけれども。For solving linear programs with a finite number of。

Constraints。You can enumerate over all possible antopus。And use this。To get next corresponding to。

That basis。Check whether this x satisfies all the other constraints or not。

How many possible things So you have to check over M choose n possible basis。

So this gives you an M choose n time sum。我en runtime out。Not the greatest。

 but at least it gets you off the ground。 It's a finite。😊，I was just， you my undergrad class。

 we were just talking about a finitery procedure It was a finite procedure。嗯。哎呀。three definitions。

Useful in three different， I mean， in different contexts。In fact， useful for matchings。Will use。

Each of these to show something worth。So far so good。Nothing's really is happening， right？Oh。

 actually， I didn't mention the sort I mentioned it in passing。

 but I didn't really mention it at the。 So let me just mention this。😊，That all these three are each。

哦，一起来。Good。I'm sorry。M can be way bigger than that。 In fact， today， we will see Ms。

 which are exponential than that。We have already written in previous lecture we wrote an LP for arbor absences where M was you know。

 every possible subset。😊，Actually， this homework that's coming out。Has an exercise that says。

 take that same LP。 You can recastci it and write it as a compact LP。Where M is poly。啊，没。

That's another story。WithPlenty of time for you guys look at that。By the way。

 I've been giving out these exercises as well。 So， you know， if you have time。So all the exercises。

 these are just problems that， you know。Hopefully， will help you。

It's not clear that they are necessary or sufficient for solving the homework problems。

And maybe one final definition let me give you is given a set of points。

The convex hull of these points。Is the set of all possible points。

Obtained as the convicx combination of these points。So given a sec S。S is a subset of product。

Just consider C，Of thanks。Is the set of all points of x。That that x is equal to sumation。

Over all points V and S of lambda v。欢TV。Lalalammbda we are non negative。And sumation of lambda the。

佢啲做佢话。Convictx combination。Of the。这是 the光野。Fact。A polytope。Is the convex hull。Of its low。And often。

 I'll just use vertices when I mean one of these three things。

 unless I want to specifically talk about a certain property。嗯。去。I mean。

 these are not difficult facts， but these are like you know。

 slightly fidly facts to prove look up any book on linear programming。😊，Or you know， on polytopes。

 con polytops。不。So far so good， nothing。对。So given all this。Why are we interested in these things。

 because really I want to understand。A linear programming formulation for。

A linear programming formulation for matching。And often， you know， since I will do this。

 I'll let me talk about。Do things。So， when I sail。So what do I want to understand？

So I want to understand the following。I'll give you a graph。Let's look at matchings of this graph。No。

Given this ground。Each matching。I can be not。By a vector。I'll call it。Guy of M。This is a vector in 0。

1。To the size of the a set。Such that chi M of the coordinate E is equal to one。

If and only if E belongs to the， is just a characteristic vector of that。哦。

Here are a bunch of vectors。I'm going to define。嗯。OK嗯。So yeah， so let me define KE。Of G。

 often I'll start dropping some of the or all of these vectors， except the P。PM for perfect matching。

G for the ground。K for convic this I am refining to be。The convex hull。Offf the set。Guy am。M is a。BM。

去。Im taking the characteristic vectors of all the perfect matches of this graph。😊。

And I'm taking that context。This， I call。The。Perfect。那行。玻璃豆。好。喂。

Its it's an object which depends on G could have exponentially many vertices， one for every matching。

You can convince yourself that no matching is going to be a complexvex combination of two other matching。

no， perfect matching is a convicx combination of two the perfect matching。I在没。Yeah。

So this is the perfect matching point。This is some high dimensional object。可以。不损失。

This is just some abstract object I've defined。It some crazy object。 you know。

 first I looked over all possible perfect matching of G。😊，Exponentially many。

 And then I define the convex cell， which is this curious beast。And I just gave it to name。Yeah。好。

Question。I want to find a min cost， perfect matching。What should I do， So solving。Min cost。

Perfect matching is just the problem I want to solve min。Overall， min C transpose X。X点ケピM。

You give me a graph of G。I should build this beast。And I should optimize this object。

This minimization will give me a verortex of this graph。

 It will give me an extreme point of this graph。 Let's use the right terminology。

That extreme point will be a perfect matching of the graph， and it will have least cost。😊。

This is the problem I want to solve。So I I have written it in this very extravagant form。

I defined this object， and I wrote it in this many extravagant font。So， of course， as stated。

 I would have to， you know。嗯。三号几就轻轮。So how am I going to get a handle on this object？

I'm going to take。I'm going to write this compact。By watch。The right this contact。

Not in this weird or convexhu definition。So let me write it。

And it's actually surprising that one can write it compactly， in fact， I can write it。😊，And here。

 so in fact， all I'm doing is I'm writing down here。 So let me write down the formula。

So here is what I'm going to see。m嘅四。X I J。So it's a perfect matching， right？

Every verortex should have one as hitting it。For right now， let's just look at the bipartite。

Non bypartite， we'll come back later on。bipartite case every verortex should have one edge hitting it and what is the bipartite graph you remember what a bipartite graph is it looks like this and all the edges go between the two cents。

😊，So what I should have is if I look over all the edges。J， such that I a J。毕胜第二。

So I'm summing over all ages。会 out the冇啊 o。This must be one， exactly one age must be chosen。I。

 suspect。 Oh， this is for every eye on the left hand side。あ、でですかね。

We equal once for everything on the right hand side， X J。么？我也对。This is some， some poll。Yeah。Yeah。嗯。

唔唔 sorry。你好。Good， so one thing I could ask is let us look for I could say x is an integer vector。😊。

But here is something I could use。 I could use the fact that this polytop that I defined。😊。

It's vertical。Are all okay so I should be careful so its vertices are all integer vectors。😊。

By construction。So， if I make sure that whatever this solution is returns a vertex of this polytop。😊。

An extreme point of this volatile point。另外 should be方。嗯。But you're absolutely right。

 This is the point I should have made， which is that it's not not sufficient to solve this thing。

 I want an extreme point。Because this extreme point is exactly a vertex， which is 01。一个。我以说。名字。LK嘅嗰个。

Aizer at least， I guess， is the problem that have。Exactly， so if my costs are going like this。

 then it might be the case at every point。Out here is opt， but either you don't to match。So， yeah。

 I should really be careful。It is。Well teaching I should。So here is the set。

Of the here thepoli I've written。One fact you， you know， can somebody just。Convince me。Right。K BM。

 So you know， really this is of G， but from now on I'm going to stop writing G。

 there's a graph fixed now。Can somebody。Argue this inequality。对。Yeah。So I need go back to。

Any perfect matching will satisfy all these constraints。😊。

The perfect matching must have one inch leaving every verortex on the left。

It must have one edge leaving every vertex on the right These a non negative。

So each of these characteristic connectors is going to satisfy these constraints。😊，嗯。

And this is a congress body。So every convex combination out there。

 the entire convex  Hu will be contained。Yeah。嗯。所你嚟你做叫。ok。And just like I did this inequality。

 the first inequality。😊，The second one。Would be implied if I could argue that all the word is saved。

😊，好给。マイナス updateト建。If I could argue that each vertex in。Lies inside that convictxs body。

Then the convex hu of those vertices， is which is K itself would lie inside that。😊。

So if I pick a verortex out here， I just want to argue that it lies in a the perfect matching。😊，嗯。

这类产品。By the way， is this is the sort of name of the game in a lot of these problems where we want to cast a combinatorial problem as a linear program。

For matchings， this is really a canonical well canonical example is matchings。

 but in a lot of different cases。This is the kind of argument you。So here is， you know。

 let's use the first definition and let's do the simplest。So this is the tail。Suppose。X。Is a。Okay。

 which definition should I use？那个。Extreme point。哦，见。Then I want to say X。Is a。

By x is the perfect matching， I really mean。😊，X is equal to pi M。Or M。Yes。

x is the characteristic vector of the perfect match。😊，就比多。OkayOkay。Mster。系。So。

S is an extreme point of K。So one one simple thing。Let me define the support of x。Is the set of all。

It is the set of all edges such that X E is strictly greater。By the way。

 one thing that you will notice is that since the Xs have to sum up to one and the xs are not negative。

 they can never be more than one。😊，So we exit that between0 and1。

I want to look at the support of things this this。So let's look at the support effects。嗯。

So suppose the support of contains a cycle。Yeah。So this is just a subset of agents right。

 the port of X in。Subs。I'm sorry。I think if there's a cycle， just throw the biggest hit。No， no， no。

 See the thing is that if I throw any edge of the way。I don't know what to do about it， I mean。

 there's not a spanning tree remember， doesn't imagine。嗯。So first thing to note is that， you know。

 Ive already restricted myself with bipartite case。😊，So the matching can't be odd。

Matting must have even number of。Yeah。So by the way， all edges have non zero value。

So here is something I can do， so I can write X。As。😊， so let's define a new vector。

Where I'm going to take。Whatever X value was and add epsilon。Do that。Yeah。Subtract Epsilon from that。

 add Epsilon， subtract Epsilon， add Epsilon， subtract Epsilon。Okay。And I'm going to call this。X1。

And I'm going to look at the other thing where I'm going to subtract add， subtract， add。

 subtract add。😊，And I'm going to call this x2。X is the average of these two vectors。Okay。

Think of epsilon as teeny timing。是。So its that theing。Thanks。Does not。Take us negative。嗯。Both means。

Are maintaining non negativity。Because I took Catilon to be teeny tiny。Remember。

 all this was in the support。All these edges were in the support， so they had non zero value or them。

 so I can' choose epsilon to be something any tiny value。那是要。对。Oh。

 I don't really care because the way I defined it， I don't have any upper bounds in them。有。Oh。

 why don't care。Yeah， but you know， youre complicating the matter。

 these constraints never even appear。 They're implied， so it's easy。OK。Secondly。

 what do I want for every vertex？嗯。The sum should be one， right。But notice in every vertex。

 the x values were the same as before， except this guy went up by epsilon and this guy went down by Epsilon。

😊，So the sum of all the edges out of the vortex， there could be other edges out of this vortex。

 I don't know。😊，But the sum of the x values still remains small because I took one edge。

 subtracted epsilon， another edge added epsilon。嗯。So this belongs to their quality。

This also belongs to that。嗯。I got a convex combination。

 actually the convex combination of two points inside the polytop。

Contradicts the fact that X is an extreme point。I wonder know how we write a。没。

So the support cannot have cycles in it。The support has more side。对。So what's remaining。

 what can the support be， it can be a forest。应一调期。Or three in this one。

There is some tree in the forest in the support。A tree must have a leaf。你知佢定。英文的意思。Take that as one。

This edge must be one。有没有什意是吧？But this means that these two edges must be zero。

Your're allologist generous。是是是。The forest that we have looks like this。No forest。

 no tree in this forest can have two edges。So， the forest looks like a。In fact， a perfect magic。

So the support of the graph， the support of x is the perfect matching。😊，And it is the perfect。Yeah。

How do make it from like this set。很那的很难。good， so it's the matching。Look at any working。

Can it have no edge hitting it？It has one edge hitting it。 It has at least one edge hitting it。

 and therefore， it has exactly one edge。But。Yeah。I'm confused by the answer he gave to a question。

 a couple questions ago about why we didn't have to worry about。Exceeding one。

 so the reason is because essentially。The fact， you， we inferred that the x is are between 0 and1。

From the constraints of this L。If there was a one。That's what I was wondering why is that not the answer？

None of these can be exactly at one because they have two。Absolutely， so， so。

 so the answer to his question is really， look， if you， if you had， if you exceeded one。😊，Then， oh。

 O。So maybe。So what it would be that this edge went above one。

But we started off with the sum sum at this vertex being zero sum this vertex being 1 so then this must have become negative。

In order for the sum to be one。But the answer I was giving him is kind of pulling his leg as well。

 but was was the following that。In writing down the LP， I didn't give an upper bond of one。

The way the LP is written， the upper bound of one is implied by the constraints of the LP。

The constraints of the LP， all they say is not negativegativity。😊，And the三十 one。

So in order to show that x 1 and x2 are feasible。All I have to show is non negativity in the sum one。

Any implications that were happening earlier will already happen。

So I can make my life slightly easier。咩走。嗯 being咩。Other questions。He ask questions。

It's so much more fun when you ask。Are we happy with this？All I said was look at an extreme point。

Syntax is an extreme point。The support can't have。サクですね。

Because then you could do this plus epsilon minus epsilon business。

And get two solutions whose convex combination effects X。So it doesn't have cycles in it。

 so it must be a forest， but if it's a forest and there's a leaf， the leaf。

 you know the edge hitting it must be one。😊，And boom， it's just the edge。That's the control。

So you're just healing off faces from。So it must just imagine。And in fact。

 it can't just be any matching， it must be a perfect matching because her constraints say equality。😊。

So x， the support of x is the perfect man。Hence， x must be a perfect magic。

The characteristic vector of the practice。行。몇 제일 좋았。So， you know， in short。

 here is a polytope who vertices a perfect match。So if you optimize over this molecule。

Which has how many constraints。Do end。Or whatever number of words see is many constraints。Plus。

 number of ages many normal negativity。Very competitively about that competitive。

If you optimize over this polytop， so you can instead of saying x disk quantity， this is the same。

As king。哎。I should have given this guy some other name， but in fact。

 you know I can I can do something else instead of crossing that out， I can just call from now on。😊。

系。I can call。This matrix， this， this LP， K TN。Because I know this is the same opposite。Next。

Perfect matching for it。We'll see two other proof。Because， you know。

 each of these will illustrate a different idea。Because they get three definitions right。

 It's the shame to do three definitions in only one。But I don't know if I'll do all three two days。

There's only tell of these things can this。啊。Good， how are we doing time。

 We are doing very well time。 Let's take a two break。 Let's just stretch and then。

A question that no asked。Was。If I wrote。If快局。This linear program。And I added in a constraint。

 so even if I didn't do this argument， if I just took this linear program and I added in the constraint X I J。

Belongs to the inte。This would be the integral programming formulation of the problem。

And you won't back nightly if I said， oh， the only solutions to this are exactly the perfect matching。

So what essentially。Has happened is that we throw away the integrality constraint。😊，And， magically。

He still got。Apotop whose vertices are integers。If you go back。What are v essenceescences。There also。

 we did exactly the same thing。We cross out the integrality constraints， and we said。

The the political。Was inte。That the vertices of the polytop are exactly the arbescences of the graph。

😊，We didn't quite you know formalize it exactly that way， we didn't really state this as a theorem。

 but this is exactly what's happening。😊，So now question is， you know， what's happening out here。

 why why could you delete the integrality constraints and the polytope remained exactly the same。

And what's that？Exactly， so but you know， what is it what's so special about these two problems？

Bipartite perfect matchings。And。Min cost arb essenceescences or whatever arb essenceescences。

And I have。I can I can say too urgent。And those two words are。Nes。And inter。So here is here， Here is。

 let me just mention。One thing since you guys have just solved homework one。啊。

Consider the following system。I have a bunch of edges。好，对吧。My materoid。

If the ground side of the meteoid are the edges。I allow you to pick one in from all the edges hitting this ver。

One edge from this， One edge from this， one edge from this。What kind of meteroid is this？

Partisition management。Similarly， I'm saying you can pick exactly one edge out of this， I mean。

 one edge out of this， one edge out of this， one edge out。It's another partisition。

I've defined two mes。On the same ground。And Im asking you for an object which is a base of the left metro。

And a base of the。Commonです。This problem is called meteoid intersection。And it's one of the sort of。

Crowing glories of early 1960s comminatorial optimization that this problem is solvable。😊，Okay。

Let me define another problem， another draft。Again， I have edges。And the edges form。

But this time the edges are okay， so the edges are directed， but that's not important right now。

They are edge of a graph。I want to pick a spanning tree of this graph。Let the make correct。In fact。

 I want to pick a foage of this graph。 that's a me right。😊，The spanning tree is the base of it。Now。

 let me direct the edges。And for every vortex。😊，Let's look at all the edges that lead that ver。

Every edge leaves exactly one ver。Now I say， apart from the route， which is boring。829。

Pick a subset of edges。Such that every vertex has exactly one edge leaving it。哦 at most one。

Another partition。Now I suppose I say， okay， find me an object which is both a forest。In fact。

 a base， So a span tree。Such that， every vertex has exactly one actually。It's in the partition metro。

 it's the base of the partition metro。😊，And it's a base of the span of the graphic。

So I'm asking for a common base of a partition matrix and a graphic。Minco arboreescence。

Both are special cases。O maker intersection。If we have time at the end and the you know we have like at least 12 topics listed in the reader choice section and maybe we have three lectures at the end but anyways。

 if you want more lectures， if I have energy， maybe we'll do it。😊。

Metro intersection captures border briefly。And anything which can be written as like major intersection。

 the polytopes are very naturally。 You can remove the integral just。I'm not sure that the。

M cost our birth is exactly equal to the intersection of spanning tree or suchsh forest and。

Partition because you could have cycles your。But see if every verex accept the root， you know。

 there are no ages leaving the route。😊，So if every vertex except the root has degree exactly one。😊。

And it's connected then the company indexax。Because it they can't be any cycles。

So how are the edges going， how are you going to pick at minus1， like if it's a base。

 then it comes to be a expanding tree。😊，So those things nicely get together to give you an arb。😊。

This area is magical。那个你后 thing系。This area some of these things are just so beautiful。嗯哼。Anyways。嗯。

Before I start getting too philosophical， let me let me get back。Other questions。嗯。So， you've seen。

So you've seen that the bipartid。Perfect matching polytop。Has a very compact representation。

It's important that bipartiteness。Is being used out here and maybe。Say a couple words about。嗯。

What happens if you don't have biparttheite？But let me do one of this。Let me give you a proof。

Before it gets too late， because otherwise， at the end， we are all tired。😊。

Let me give you another clue。Of that particle。Be明的。So whenever I say the polytop is integral。

 its vertices are integral。😊，What got it's this。干觉个。

So let me write down number So X is which definition。Basic feasible solution。我了。给。

That that linear program that I wrote on。Basic feasible solution。Then I want to say x is。好的视频。这天确情。

And just just so that you have the LP sitting out here。

 remember it's just saying sum X J sum overall J is be equal to1， the all I。😊，And some of so Jさして。I灸。

そじゃねい。Some of our live for that I。Ex。そういうふにそれをあげて。I want to claim x is a basic feasible solution to this。

😊，AndX is the problem。And you'll see， you know， the ideas are very similar， but actually。

 this one is similar to the previous one。😊，The the one you'll see on Wednesday will be eliminate。

So what is the definition of a basic use？It's tight on。Good， so first of all， in all these things。

 let's just be very careful how many edges do I have。😊，So I have。In in a， in a。

So departure from my usual notation。And here is the number of edges of this。

Because I have one variable for every age of the。哎。So for once， n is the number of ages。

 let's not be confused。So I need n constraints out here。And they should be linearing。

Some of those constraints will come from up here， and some of these constraints will come from。

 So maybe I just even write this。Yeah。你看。So there are a bunch of edges for which this constraint will be tight。

 Okay， So， so let's say so。Look at。Tight constraints。Sose。8。Liineally independent constraints。呃。放。

H PCs。啊。L prime subset of L。A prime up5。プさ。喂。So some of these constraints。

 I'm going to pick in my basis。Some of these constraints。

 I'm going to pick in my basis and some of these constraints。Okay。And such that。And Brian。

That's part a crime。Let一 try。S I， you have to start off this way。You're losing what's happened。Lly。

 you know， there's a bunch of edges which are being set to zero by。ささのたで。

I be sure that K is the same as the absolutelyute， absolutely， so you know。

 I could use the fact that basic feasible solutions are the same as extreme points。😊。

And then I be done。But let me not use it。Because tomorrow you might need an argument like this when you don't have an argument the。

So very valid question。😊，But human。Okay。So I want to show this from first know， from the definition。

That x is the perfect。嗯。So I say， okay， I have a bunch of tight constraints out here。It a linear pen。

 let me take。😊，嗯。对。我我是同。这事那了。Okay可。消费。So， so these guys are the unt ones。So naively。

 these guys are the inequalities。 So， you know， I can pick any。

I need to pick some basis all the definition is telling me is that there must be some linearly independent type constraints these guys are of course all tight。

😊，But in my linearly independent set， I don't know which ones of these are there。I don't get to do。

It just， you know， the definition tells me， okay， these guys were tight。 These guys were tight。

 These guys were tight。 Okay， deal with it。我想叫你。So what does this mean？This means that there's some。

Inequality。This is the same thing I'm writing now。As before， you know。

 we wrote down this thing that theres this these tight constraints that come out。

And there's variables out there， That's one。Up do X of the size of。Oh。These are the， you know。

 each of the columns out here corresponds to one，2。开嘅嘢做。

There are some of these constraints which should correspond to L prime。

 some of these corresponding to L prime。And some of these corresponding to people。

What can you say about the constraints corresponding to Eproin？

They are just saying some of these wages are equal to0。Because if these constraints are tight。

 thist equal zero constraints。So this is just saying。This variable is you know。

 every variable in E prime is 0。So you know， maybe I could just say oh E prime。

Conorresponds to the last few edges here。 that by renaming it。

So Im saying there is an identity sitting out here。And that's saying that all these days。Okay。Okay。

没边诶。你ic more。building。So these variables are already equal to zero。So， let's look at。

This sub matrixtri。And let's look at the top of this portion。So I'm saying C times。ですか？Yeah。Sme。

 let's call the top of this guy prime。Its be quality。7。And maybe I'll write it in this sort of math。

Far， so they can use。I also remember that it's the all one thing。How do I solve this？我在。

Allen wordstey， right？Okay。I want to invert C。Morrow。有咩文啫。Lo my chain off。

Maybe this is why I have some notes。咁哋有哋。这事。系搞嘅。Okay， so actually， you know I can do something。

 I can use the trick， which I wanted to use the。😊，真意思。So。Suppose， you， I'm solving any linear system。

 A equals B。Can you tell me what the I coordinate of x is going to be？不。小。确定。If you guys remember。

Cramer rule。So Kma rule says。X I says， you know， a， the n by n matrix x is an n dimensional vector。

 B is an n dimensional vector。 this says it the determinant。😊，O， where you take the I column。

And you replace it AI and you replace it by B。M바 buy。Yeah。Some rules they听。

You pull out of Ha hat once in a while。Once a year， I pull it out of my hand。 today is that。

What did I do， I took a， I took the I column， I threw it away and replaced it by B。

And I took its determinant divided by the determinant of it。😊，Gme。What can you tell me about。嗯。

So here it's sum sum sub matrix C out here and x prime is equal to1。

What do you know about the entries of C？They're intigious。就我。Yeah， but let's say integers。

If I replace you know the Ih column by B， it still remains an intelligent。😊，So the humanators。

Determinant of integer matrix integer。De not I don't know。

But suppose I could show with the denominator out here。 So actually， I should say。你咁呢。哦，C。诶，安。

Divided by de。事咧。Theumminator UV。S poll I could show that the denominator is either plus or minus1。

Id been great shape。The answer would be an integer and the only integers that can be allowed are 0 one。

嗯。はい。So as long as I can show that the determinant of c is plus or minus1 and。😊，不这个。But呃。Yeah， dude。

 I'm， I'm so good。 I'm so good。But let's do it。 Let's。

I want to show you the determinant of some sub matrix like this。😊，It doesn a minus1。First of all。

Yeah。这个钱。是。i'm sorry。We might CI。I have。See。嗯。哦， are you are you。ですけ？Previous。ですね。

So here Im just looking at this this portion of the argument because all these guys are zero。😊。

So they don't really mess things So really all that matters at this times this top is equal to this。

That's really only thing that I。I need to show that， C。As is becoming。0 plus -1。By the way。

 can have C determinants can C have determinants there。往外 not。As the house or the browser linear Yes。

 so you know， these rows are linearly independent， hence columns must be linearly independent because it's full rank matrix。

So C， can't be ranked defic。 I mean， it can't have it can't be singular。So now。I want to show that C。

 okay， C can't have determinive。So， let me show you。呃，系靓吗。The determinant of C。

Is belongs to negative one0。But we already said it can't be0 also plus minus。😊，Get proof induction。

And pull my hand waving now。 I'm going to start waving my。C。Has a bunch of zeros and ones in it。

Let's look at the column to see。If there is a column with a single one，Prove strategy。Induction on。

 you know， I want to show that every square sub matrix of C has determined0 plus minus。😊。

Every square。Prouppa induction on the side of the supplement。Entries。Are all0 one。ベスケ。Inductive step。

Its there is a column of C， which has a single one in it。😊，I can just expand out using that one。

And this day。Has。你ter。0 plus minus1。算了。So every column has two ones in that。

Can it have more than two one。No， because every column， you know， look at the constraints out there。

Every column corresponds to a variable。Each variable appears onces hair and one's hand。

Each edge appears once on the left hand side and once on the right hand side。So this is that you see。

Or whatever sub matrix I'm looking at has two ones in every corner。At most once。

 but if they had a single one， I would expand out by that and just induct。😊。

So every column is exactly two one a。But finally， it's a biparttheite。So if it's two one。

 then there must be a one on the top。看我问没我。Crepon to air time。

But this means that the sum of these rows is equal to the sum of these row。😊。

Not linearly independent。Contradiction。So we'll never get into a situation where you have only two ones in every。

So， you can always。Find a column where there have a single one expand out along that and just keep。

And if you're thinking about this， this is exactly the same argument that we did earlier where we said。

 oh， there's always an edge。 There's always a leaf。😊，That leaf has a single edge。😊，Let's look guy。

That's the other。way。Remember remember last time when we did the cycle。

The determinant just taking a bunch of rank patients。The correct one sit span。完美上。不了。No前もです。挨这呢。

ItIt would be great， I don't know， but we should talk。嗯。De breath where。We said， look。

There are so many types。Yeah。These tight constraints must be setting a bunch of variables to them or just throw them away。

What's happening with the remainder？我听咧。This remainder。You essentially going to give me。You know。

 it's a matrix with determinant plus。And if I can get a determinant plus or minus1。

 then Kmer's rule says。诶。Myitalリーシが screen。And this， you know。

 since we are talking about connections， I know I'm out of time。

 but I'll take one more minute of your time。😊，嗯。Clme through powerful lady。So for instance， if I had。

The course I wanted to say。So suppose I wanted to solve minimize sea transpose such that。

A X is that is to be。Yeah。I want to solve this problem。然后。Suppose C。B A are all individualig。

Entities integer matrix into your light。Actually， C doesn't need to be。 C is whatever。

 A and B are inte of matrix C。Furthermore， suppose every square sub matrix of a。Has。

Determinate0 plus minus1。Then the same kind of argument applies。Because you know。

 what is the optimal solution of this going to be is going to be some set of rows of a。Call like C。

So what well be solving is we'd be saying， oh， there is some set of。Andti constraints outhill。

Satisffiy Cx equals。ライ？行。So this means that X is equal to deterant。学师。B。What have I victim on。お星。可以了？

Object on the in the north， on the top。Indient。Because C and B are both inteent， the inte object。

Object on the bottom。I just said every square sub matrix of a is 0 plus minus1。

So this object has determined0 plus or minus1， but it can't be0 because it's linear independent。

So it's plus or minus So the answer is。This is a theory of total unmodularity。

Another big theory going on。Very nice， rich detail。So like all kinds of starting points。

 if you guys are interested in this stuff。😊，We can talk for hours。

 but we shouldn't because I'm five minutes over time。

 thank you for being patient and I'll see you guys on Wednesday。😊，Well do a little more matching。

 We're almost done with matching。 So if you don't love matching as much as I do。😊。

The suffering is bound。