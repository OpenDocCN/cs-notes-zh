# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p03 Lecture_03_LPs_and_MCAs.zh_en -BV1a4cCeMEzb_p3-

Hey， everybody， welcome back。And。Questions。Anybody。You guys have questions， comments。

So a couple of announcements to make。Homework Ze is new tonight。And as you guys know。

 there you do get extensions for every homework。 So if you want a couple days extra。

 you do have a couple days。 you don't have to ask us。 you don't have to say anything。

Gcope is open until Wednesday night，1159。嗯。And other than that somebody asked do you need to latex or can you write it by hand and scan it hands as long as it is legible we don't really have a problem if there is a problem later on well let you know。

 but as it goes right now I think I'm perfectly happy with having it handwritten or latex。

Whatever helps。And。We'll put out homework one at some point， maybe tomorrow。

And it'll be a group homework。 so you can work in groups of two or three。And in fact， if you can。

 you should work with other people and well make it will will set the thing on piazza so that you can find partners using piazza。

Okay。Other questions。so in that case let's get started today we have a this is the menu for today we want to finish off Mincos arbescences。

 we saw this last time we saw very elegant algorithm given by Jack Edmonds actually the same algorithm was given by Chu and Liu by Jack Edmonds and by a gentleman called Boch around the same time and unfortunately I don't have PDFs of the other papers so if you do have PDFs or if you can find PDFs somewhere on the internet I'd be very grateful might even get you a couple of points here and there。

😊，But because， you know， it's kind of fun to look at these papers to see what people are doing。

 How did they come up with this， what what insights did they have。But anyway。

 we saw this algorithm and the algorithm was very nice。 It said， look。😊，Let's do the following。

 let's repeatedly do the following inductive。Step， remember in a Minco arbescence。

 you are given a graph， it's a directedive graph， so it's there arts。Each arc has weight。

And you want to find an arborescence with a minimum weight and what we said was， well。

 if there is a verortex which has a bunch of outars。Reduce the weight of all these arcs uniformly。

As in you know， two， three， five， and seven， reduce it by the minimum amount until one of them becomes zero。

So now every every vertex has a0 weight are going out of it， every vertex except the root。

 the root you know doesnt need to have an arc in fact， it shouldnt have an arc going out of it。😊。

Everybody else has a0 radar going out of it。 So that's step one。So reduce it so that this becomes0。

 one， three，5。and now they have the 08 arcs so for every verex pick one of the 08 arcs and look at the resulting structure if this is an arbescence thats great。

 it is a 08 arbescence so it is optimal。😊，If it's not， then you must have a zero weight cycle。

 so if you have a zero weight cycle there edges going in and out。

 it doesn't really matter edges in the original graph going in and out， it doesn't matter。

These were the zero weight side inches。In this case， you took this cycle， you contracted it。

You recursed。And then you lifted the solution back。跟么。So that was the main idea。 And we showed。

 you know， its a simple inductive argument that this is optimal。

So we have an optimal algorithm for Minco arbvariescence。

 and now I just want to do the same argument， but we are linear programs。😊。

And this will be convenient because going forward， there will be more complicated problems that you want to deal via linear that you won't be able to maybe give such simple proofs of correctness。

 but linear programming will give you this very powerful hammer that you can use。😊。

So since we use linear programs a lot， you might as well get know used to this。

 you might as well get familiar with the idea of linear programming。

And I'm sure all of you have seen this before。 it might be a little rusty。 So let's go over it again。

 I want to spend a little more time and then well we take it from there。😊，跟。So far so good。

 Do you remember this？So what's a linear program you remember this and I'm going to do a very quick primer of linear programming duality。

😊，啊。And this is purely mechanical primer pointed to books， they are very nice books。

 there is a very beautiful book called using an understandingstand and using linearar programming by Mattuschegartner。

 the PDFs available to you as C students it's a Springr book and you can download it it's very readable you can like bedside reading。

😊，SoIf won't even put you to sleep， I mean， it's so thrilling you， I want to read some more。呃。Good。

 so duality， you know what what is an LP and LP looks like this linear constraints， linear objective。

😊，Given such a linear program， you can mechanically come up it's do a linear program and let me just go through the mechanics very quickly once。

😊，This is a minimization linear program。😊，And I have written it in。

 I think this is called the general form。😊，there's various names or there's the standard form。

 general form， you know， whatever。 I never remember these names。

 I don't know if you should remember these names except for when you're writing a paper。

 you can look it up。 but the thing that you should remember is。

Suppose I have a minimization linear program。I have written this linear program so that the constraints are all greater than equal to constraints。

😊，And the way I think of this is always that look， these constraints are making the value high。😊。

And the minimization， there is this tension， minimization is pushing it down。😊。

So this is some canonical form of a linear program。😊，And its's dual。

 is that linear program out there。And the way you get it is purely mechanical。

 You can come up with this。 There is a method behind this madness。

 but Im not going to go over it right now。😊，You can read it and we can discuss this later on by the way I have office hours I will have office hours every week today I had it just before this lecture but in general i'll put up a post and Piazza feel free to come by office hours even if you just want to chat。

😊，No， that's totally fine。 You don't have to ask the homework question。啊。

Good okay so in any case a prim linear program and the way I think about this very quickly if Im in a hurry I don't want to interpret things。

 I just say well， this is like this this whole series of matrices and vectors。😊。

These coefficients were written in this matrix。 These times x1 x2 is the right hand side。😊。

Thats that's the objective function。 That times this is the objective function。 X is non negative。

And in my mind， I'm already saying， oh， by the way， this is a minimization， andm in my mind。

 I'm saying minimize C transfers x such that Ax is at least B x。😊，嗯。

And then how do I get the the the duall。I take this matrix by transpoic this is just the transpose of this one。

There's one variable out here。For every constraint。Theres one constraint out here for every ver。

The the right side goes to the objective function。 The objective function comes to the right hand side。

 and this becomes a。Maximization problem。The min becomes a max， max B transpose y。

 as I said a transpose y is less than equal to C。What not。半対です。Okay， purely mechanical。

And very often， when we write a primal LP and oh， that's called the primal， this is called the duals。

😊，The name primal is there only because it has to we need a name for the original object sort of this is the dual object。

 and so that's called the primal object。Prial endorse。The dual of the duall is the primer。

And in linear programming， there are two facts that。 you should remember。One of them was weak。

 do Ali？It said that if x is feasible for the primal by feasible。

 I mean it satisfies all the constraints。😊，And why is feasible for the dual？

So if both of them are feasible。Then。Seeve transport is X。This is a minimization。

It at least be transport。嗯。This guy is trying to maximize its objective function。

That guy is trying to minimize the objective function。Every solution to the primers。

Is an upper bound to every solution of the two。This is weak dwell。😊。

The proof of this is one one sentence， really。Next자 we didn。I can do this at some point。

 but let me just know。This is weak duality and strong duality， says。If。X star and Y star。啊。Okay。

Are optimal solutions。For the primal ends， then。C， transpose X star。I we going to be translate。

If you take optimal solutions to the primal end。Then their values are equal to each other。

This is strong duality。Okay。For most of this， you know， we'll talk about strong duality later on。

 today， I just need weak dual。Every solution to the primal is an upper bound to every solution。

In particular， the optimal primal value。Is an upper bound to the optimal dual value。

All this is revision， right， We've seen this before。Baly in the midst of that。对。

So let's just use this fact。工作。Questions。People have questions。 People don't have questions。

 You're happy so far。So whats the plan， So the plan is I gave you an algorithm。😊，Or winco algorithm。

I want to show that the solution it produces is optimal。

And I'm not going to use the inductive structure。 I'm instead going to use a linear program。

So I'm going to write a linear program for Minco Alvares。I'm going to take its do it。

And then I'm going to reason about these two objects。Okay let's see how we。

So first let me write down the linear program for inco aberescence and we wrote this last time it was a little。

 you know it was quick， you hadn't seen some of the terminology before lets do it。😊。

So what what are the variables So in fact， usually I don't even write down the variables well the program they just appear。

😊，Organically， but let me just write it down。 There is a variable x sub a corresponding to every yarc。

In the。Maybe， except。Those leaving。这如何。You should always imagine in Minco aberescence。

 there are no arcs leaving the route。They're just boring us。 they won't help you。

So there' is a variable for everyR， in some sense it's making a choice。😊。

And what I'm really doing is that first I'll write down the integralte linear program。😊。

And then I'll relax it So what's the in linear program I want to minimize summation cost of VR times whether I chose it or not think of this as being0 or 1 such that and then we have these two constraints。

😊，Saying that if you look at all the arcs。This is delta plus of v。

This is just saying all the arts that leave averex。😊，With the outgoing a the vertex。

This mustity is exactly one。I should choose exactly one arc， leaving every vertex。

Definition of arborescence。 And then I want connectivity。So I say X A A in Delta A。Delta plus of s。

 So if I look at any this is a set of all vertices if I look at a subset s at least one arc。

Should be crossing it as long as the roof is on the other side。

Because these vertices need to be connected。So x a plus one must be at least one for all S such that r does not belong to S and S should be non negative S should be non empty。

 but you know， if s is the empty set， then there are no rs medium。 So this is a back。So， for every。

A vertical see， there must be at least one edge leaving it。😊，For every vertex。

 there must be exactly one edge leaving it。那这。X a is in01。I can either not choose the other two。

That's the intelligent linear program。And if I want to make this a linear program。I just say X。对嗯。

Fner。对。Let's write down some facts about。Thisll be right here。So， fact。

If LP star is the optimal solution value。O天。That LP star will act most。Inmedia program。

The optimal solution to the integer program is more constrained。😊，This is a minimization。

That's an LP。 I can write down its duall。let me write down its goal and tell you what it is and you can do this exercise yourself。

 you should do this exercise yourself to be comfortable with taking do fast。😊。

WellAlmost never do you need to do it fast， there is no time pressure， take your time。Okay。Remember。

 min becomesms。😊，啊。Good one variable for every constraint out here， right。

Constraints correspond to sex。So I'm going to have one variable for every set。And in fact。

 you'll notice that the right hand sidess are all one。

 which means that the objective function out here will have coefficient which are one。😊。

So I am summing over all sets and these are all sets that are interesting in some。

 these are all sets s such that S does not contain the root。😊，嗯。Okay。

And then the constraints will look something like this。If I sum over all the sets yes。

Such that one particular arc。Crosses the set。 So this I'm looking at all possible sets such that this arc is leaving that。

This must be at most the cost of that。For all facts。你啲龙住啊。嗯，哦了是。

For some reason my graph has become and last time we mentioned this。

 but the graph is actually the set of Bie seeds and a bunch of arcs。😊。

And I'm writing a just to emphasize the fact that this is a direct。

YouWhat use E less confusion sometimes。O。做奥利。But。Each cut has a well。All the， the cuts。

 the cut values that mean。That these are all the cut。 So this is a art。This cut。Is counted here。

 this cut is counted here， this cut is counted here。 This cut is counted here and so on so forth。

Exponentially， many cut， all of them are counted。What does it even mean？嗯。

We will try to give an intuition。In this case， we succeed。我系。で、すね。And then what else。

Any other constraints？Why is there positive。And actually， in this case。😊。

You this is one of these things。Every variable in the dual corresponds to a constraint in the primal。

 right。So if the if the constraint is an inequality。

 you will get a sine constraint out there its an equality， you won't get a s con。😊。

It's this sort of weirdness with dualls and you have to again think through why what's happening behind taking duals Ys is greater and equal to0 for all sets S。

😊，Such that the size of S is at least。Or single tens。😊，There's no constraint on the sign。

 but for all other sex。This is true。 And you know， S does not come。F。好的。Are we Yeah， sorry。

 I don't know what to do about this， this beast out。If only I could。

There is no allowed movement in that axis。You guys can watch it。I don't know what to do。So。

Is that slightly better？😊，Yeah。もりたいんですか。O。Good。So far， simple。Actually， you know。

 this whole business about Y as being greater and equal to if if the weights were non negative。

 it doesn't even matter。😊，This will be only relevant if the weights are negative the costs are negative。

嗯。You know， theres lots of interpretations of duals。In fact， again。

 the Maussha Gartner book talks about various interpretations of physical interpretation and economic interpretation。

😊，So one interpretation is that these are like prices。This is like money。

 This is the economic interpretation。And why S is how much money is the sec S willing to give me？

Okay。In this constraint， you will see。Will， will correspond to that。

Or at least can be interpreted that way。So， I don't claim that every dual I write down I can interpret what the variables mean。

 but in this case we will be able to interpret it to some extent。😊，What's the plan？So by the way。

 that's the duall and you know that the duall。The optimal value of the dual is at most the optimal value of the prim we dual it。

Yeah。So here' is what we are going to do。We are going to the proof will go in two steps first step I am going to show you well this is almost immediate。

 so in fact lets let's just observe this。 The first step I'm going to show you is that the algorithm。

😊，Gives you a solution to the optimal to the integer program。I mean。

 the algorithm is clearly a  zero1 solution to this inte program。😊。

So the optimal integer program value can't be more than this。哦。

So that that's a fact you've already observed。 this is a solution。

The second fact we're going to show。Is that I'm going to show you a dual solution。

Whose value is going to be equal to the algorithm。嗯。So the optimal dual value can be only higher。

 It's a maximization problem。😊，Al go is that most this， I that mostly。And now you see the plan。

 right？Now， this means everything。Youve just proved strong duality out here Oh sorry out here。

You proved that you come up with an optimal dual solution。

 you will have proved that you have come up with optimal primal solution。😊。

RightAnd you have also proved that the LP and IP have no gap。Everything。

This LP that you are writing is producing solutions which are optimal for the Integer program。😊。

It's America。And theres only one piece missing， which is the piece。So let's go。And in fact， you know。

 proving this formally， itll take me， you know， a little time。 It's induction boring。😊。

Let me give you， let me give you the sort of main idea。 You'll fill in the detail case。

And let's do an example。So what's the example， so here's an instance。Actually， this is you know。

 as I was drawing this the other day， I realized this is actually a sort of an interesting instance by itself。

😊，But if I can remember exactly how。嗯。It goes。Let's do。有啊。going slightly different。都。听。7。11。特电影。

Let's call these P QR。Okay，S is S is the root line。没什 even draw that。Yes。好嘅。

What will the algorithm do lets just run the algorithm very quickly the first thing it will the algorithm will do is P will say look I have a single edge coming out of it it has weigh2 I should just make it weight0。

😊，Q will say， oh， I have two edges coming out of it3 and 11， this makes it0 and this makes it8。😊。

R say the F2 h is 7 and 13， this makes it0， this makes it6。The zero cost agile former。cycle高。

I'm going to shrink these down。And let me not bother drawing it again。

 I'm going to shrink these down and then what's going to happen next。😊，This new working。

As two parallel legends going to the source。不不住。Of six and eight。

How much would we reduce these edges by。6。And now there is a single zero weighttage let me use my blue。

😊，I want to dig advantage page。And then I'm going to pop this cycle back。

 And in order to make this cycle work out， I should use this edge， now I should use this。By the way。

 interesting thing， S had an age of weight 11 and a weight age of weight 13。

Greedy algorithms might have taken away11 edge。Not a good。 greedy is not good for menco We。嗯。要重新吃他就。

The subre paying the cost for the some like just year once step ahead I like it。呃，个人。

This is the prim algorithm， this came up with a solution out here。😊，Let's come up with dual。

Nual values。打嘅。就。Let's look at step one。 P decided it looked out at its outgoing edges and it said the cheapest edge has way two。

😊，I'm going to subtract2， right。Yeah。就。He says， look， I'm willing to pay too for sure。

To escape myself。Hugh said I'm willing to pay three for sure。 Oh， by the way。

 this is when I'm saying why it's a piece， why it's sub single term set。😊。

H is willing to pay three to escape。Q says， look， my cheapest stage coming out of me has weighed  three。

If I want to connect to the route， then come on， I have to pay at least three。

How much is R willing to pay this is terrible notation R is。嗯哎。T， I'm running our letters guys。

 So we'll have to move to a different alphabet。How much is T link of them。在。These guys each said， oh。

 I'm willing to pay two， three，7 to just leave my door。😊，Okay。And then they all left their doors。

 and then they realized they're in a valley。They need to gang up。 They need to collect together。

To work as a team to escape this valley。So they are going to pay。P。

 Q and P are together willing to pay how much。这个。And now they have escaped the valley。Now。

 it might be that they are in another bigger valley and they have to keep on doing this process。😊，滚。

Why for all the other sex is zero。嗯。Not relevant。How much money have I generated。规定。

How much was the cost of my solution？2 plus 3，5，5 plus 38。It's no flu， right， I mean。

 I just created it that way。😊，Let's look at the only constraint I have。For every arc。

 I need to make sure that the total amount of money that people are pulling together。😊。

Is no more than the cost of this ark。But really， what I am doing is that really I am making sure that the cost of the R minus the pool money is not negative。

😊，Which is what I'm ensuring via my process。Look at any arc。When does its value go down。

Its value goes down when it belongs， when it's the outgoing arc of some。And that said， raises money。

You make one of its outgoing a0， All others are non negative。

Its speaking the least amount of money so that C minus。

The amount of money pulled so far remains non negative。For every ark。So look at this article okay。

This arc of 811。Who are the people who reduce its cost？叫。And the second。When Q reduced its cost。

 it reduced its cost by3。😊，And it gave three to this， this， this left hand side of the constraint。

When this set P Q T reduced its cost by 6， it contributed6 to the left。

So if I maintain that every arc。😊，Has non negative reduce cost。That constraint。

And I am maintaining that。 That's exactly what inductively I'm maintaining。

And so your proof will go exactly like that。关系。A guys is happy with this particular example coming up with the primal end。

😊，So think you know， try， try to come up with a formal proof that indeed that is a feasible solution or yes。

 it's just an inductive proof。😊，On the structure of the algorithm。Do this， if not， ask again。

 you know， the beauty of all this sort of technology thats come up is I can just produce videos act well。

😊，So if if somethings unclear clear， ask me and I'll produce a video and I'll explain it as well。

 So you get two bytes in the app。Okay。So we just gave one example where。

The algorithm's value was upper bound in the primal， but also a lower bound in the。Thank you听。好。没个。对。

Okay。Let me， you know， this economic interpretation， what is this interpretation。

 what is this constraint saying。😊，This edge says， look， my force is C。😡，If you buy me。

All these constraints will be happy。Why would these people。Together， pay more money。

To satisfy themselves， then。The cost of this edge。喂。You can never tax people。

 you can think of why as taxes。You can never tax people more than the cost of some solution that can satisfy。

In this case， we had this very nice interpretation。Of these prices。And this idea will come up。

Repeatedly， not all the time， but very often people just say oh dual prices。😊。

They just mean do variables。And this term price will be used。 you'll see it。 I promise you。

Later on this lecture also you'll see prize。嗯。So more or less that that is pretty much what I wanted to say about getting a primal dual proof a dual based proof of this algorithms optimal I just showed you that this algorithm is equal to the optimal solution is equal to the LP whatever。

😊，Let me mention one other thing。All we do by S R0。W is zero and by we all others， all others。嗯。です。

By the way， one thing， one more thing to remember。What do like non non non zero。Do well say。

Another thing I keep in mind is that the non zero duals。

Tell me which primal constraints are important。So this is somehow saying， look。

 the primal constraint corresponding to the set pq， the set pq。Is not particularly important。

Rarely the sort of the bottlenecks in this thing are the singleton and this valley consisting of peak QT。

😊，Those are like the real bottlenes to this angle。We can kind of make this formal。

 And this idea is the idea behind complementary slackness。😊。

And all these sort of terms come back to you， you might have to go and brush up again， but do that。😊。

Because this is like a beautiful and important theory。That will draw on again。的。So with that。

Let me stop for a second。Actually， let me say one last thing about this whole business。

 and then we'll move on to short spot。So here's another picture I have in mind。 So by the way。

 one more thing， one of my goals in this course is to draw for you the pictures that I get in my mind。

😊，Whenever I'm doing this work。So this， this picture， this is this， you know， matrices， you know。

 taking their trans transpose and stuff like that That's a picture that took took took comes in my mind。

 I see this。 and immediately those those like it's a movie that plays。😊。

So I can tell you what movie plays in your mind may be helpful to you may not。

So here's another movie that playss in my head。啊。This is the inte programming relaxation。

 this is the inte programming relaxation。😊，都啊。또 어。わりですよ。So consider an integer program。

What's an integer program an integer program consists of you know it says something and when I say integer program I really implicitly am already meaning integer linear program。

😊，Minimize t transpose x， a x is at least B x is in let's say the integers。So this portion。

Is drawing some convet。The inality just says I am only interested in the integer programs in this context。

😊，This takes forever to draw I to stop。我。Oh。暂品 like thisす。I'm only interested in these interview。

Indeed， the in points。And then。We often ask what is the convex hull of these in points？This is often。

や话。I'll write case for convex Se， IP。That's this orange beast。

And the linear program that we wrote down is K up1。Yeah。The LP is a relaxation。

 Its this bigger beast。😊，Inian。And there might be a gap， there might be points here in KLP。

 which are not in KG。So KIP， remember， is the con convex health， so it contains all this。Yeah。Okay。

And you can ask the question is。For any integer program， you can ask the question。

 is the integer program is the integer hull equal？Do the contracts。And in general， this is not true。

You can come up with trivial into your programs for which the linear programming relaxation by linear program I just mean I'm going to drop this。

😊，No integrality constraints。嗯。the question is is the picture。

 does it look like this or does it look differently。

 as in is it really that the IP is equal to the LP。😊，So here is one thing you could do。

 You could say， suppose。There is a direction。Well， there are points out here。

 and this will be a red point。There are red points like this。

 which are outside the N programming house。Then if you took， let's say。This direction。

 And you wanted to say。Let me just make this max just so that。我嚟 running。So， if I looked at。This。

 this is a vector C。😊，What is the maximum value that I can get inside the integer h。

 it is probably this point or this point。😊，And whats the maximum value I can get in the linear program。

 Its this point up here。There's a gap。So， if there are points which lie in the linear programming hull。

 but not in the integer programming hull。The value。

You know so does so I'm saying this is the same as asking the question， does there exist a vector C？

Such that the optimal value for the IP。Is different from。The optimal value for the end。And again。

 you can make this precise。 This is an if and only condition。

The two things are different if there is a direction。😊，Where the two values are not the same。Yeah。

What have we shown， we have shown so far。That at least for positive values， for positive cost。😊。

The IP and the LP have the same value。And in fact， if you work just a little more。

 you use the you can show this for all costs。😊，That that LP and that LP corresponding IP have the same cost。

Okay。Yeah。Please， there a geometric representation？啊， so呃。It's live in a different dimensional space。

😊，So the short answer is， I don't know of a good way of representation。

But lets just look at the primal。 Basically， I'm looking at the inequality Lp star is less than equal to L star。

😊，Just that。But it's a great question。😊，So what we have shown is that the LP and the IP were equal to each other。

 at least so positive。😊，Bosts。And in fact， you know， my claim is you just sit down。

 you'll be able to show the LP and IP are equal to each other for all costs。😊，Negative or positive。

So what that means is that this LP that we wrote down。If you look at the In programming relaxation。

 sorry Inte programming， the In hub。😊，It's actually equal to so so we wrote down an LP。

All my LTs look like this， by the way。The integer programming。

 the integer Hull actually looks like this。All of this， this is equal。And， in particular。

All the corners。Must be the integer solutions。So here is the claim。Take that Lp。We said， oh。

 this LP has two problems。 One is the exponential side。 We won't worry about that。I have superpowers。

 I can solve exponentially I tell too。The second problem was it's an LP relaxation。

 so I might get traction solutions。😊，What we have just proved。

Is that if you solve this LP optimally and you pick a corner point， a vertex of the solution。

 also known as a basic feasible solution， also known as an extreme point。😊，Mr。 out。

You pick corners of this polytop that you get。Youll always get zero1 solutions。

So take your favorite program linear programming solve a Grobi CX Excel ask it to give you a basic solution I don't know if Excel gives you basic solutions。

 but the other guys is you can ask them to give you basic solutions。😊，Basic solution。0。

1 solutions up to round。 I mean， usually there is some numerical error， but of course。😊，You can run。

嗯。Beautiful theory since you want to solve that problem。就 you don't have to逛明里来这个东。Just solve the LP。

 It will give you the right answer，01 answer。In general， please don't give you zero1 answersun。

Into your programming NPhar。So this is this sort of this leads to this sort of big area of integer polyhedra。

😊，And indeed， you know， when are L relaxations in Te。

And we'll see again and again for all a lot of nice problems。Matchings， flows。Inte LP relaxations。

 intel。And then you know， hopefully homework problems will appear。

 which will you know walk you through some of these examples and we'll take them one time。去。

So these are various themes that will come up。In the book。那个呀。

Remind me if you see me doing something like this and I'm not emphasizing it， just remind me oh。

 this is another one of these things whether the polyhedron is integral。😊，Okay。Yeah。Good。So been。嗯。

Let me take a two minute break and then well start again and then。

This is all I wanted to say about Minco avariescence。😊，Maybe there's one， Yeah， okay。

 let me say one more。Today it seems to be a you know slower day I'm philosophing， let me philosify。😊。

So we saw spanning trees， right？Thepanning trees are a special example of something called matteoids。

😊，You probably you know， some of you， if you， unless you've done a course on combinatorial optimization。

 you would have never seen this object called of Mac。😊，But homework one， you're lucky。

 you'll see nitris， you'll work with nitris， you'll start to develop your information。😊。

The greedy algorithm algorithm works for matrixx。 that's minimum fan increase and matrixx。对。

This is not a matteoid。 This is an idea of something called matteoid intersection that two matteoids will define。

😊，I want a spanning tree plus I want only one edge coming out of every vertex。

Two constraints like this， two matrixs， and will formulate。

Machings are also intersections of treatment。Bpartite matching it。

And we'll see a very general theorem actually， I hope you'll see， you know。

 this is one of those things towards the end of the course。

 but this is a very powerful theorem proof back in the before I was born that shows that intersections of two matrixs can dissolved in polyar。

😊，Its one of the more powerful theorems that we know。

And this whole area of meroid meteroid intersection has this sort of beautiful polyhedral structure。

😊，You want geometry， youll get geometry。And catch catch me sometime if we don't taste this。

 I'll tell you more about it。Right down。I should bring the book。 So there's a。

 I'll mention it anyways。 So there's this book by。He doesn't go by Lex。

 his name is Alexander subscriber。He's got a book called I think， combinatorial optimization。

 Cominatorial optimization is just discrete optimization。😊，It's。

So subscriber's book is a three volume collection and if you are interested in this kind of stuff read it books will teach you all you want to know maybe more than you want to know about this area。

😊，Right now。Yeah， that's one of the disadvantages of not being not having my office upstairs from my lecture hall。

 I tryt just bring down books to slap them across campus I'm lazy。😊，Anyways。

 let me stop for two minutes。 And so the setting of shortest parts is going to be。

 Let me just remind you， we want to。There's various flavors of shortest paths。😊。

Will be interested in this problem called。Singer。Source。Shortest paths。

 I'll always write Ss for shortest paths， and in fact I'll write SSSP for single source shortest paths。

😊，And in this case， the problem is this you are given a graph with a source。😊，And then， there's。

Edge is coming out of this and。In the， will there be direct。They might be bidirect， whatever。

And the these have lens and the lens could be negative as well， so this could be two， three。

 negative1， seven，3， etc cea， no negative cycles are allowed。😊，Okay， so。

There are two special cases there is non negative edge lengths。L negative。weights。Lance cost。

 I use all these terms。 So please don't get confused。It's all the same。

 there's only one object out here。If there are two， I'll let you know。

 sometimes there is there are two。 So this is special case one。

 non negative visualilance and possibly。😊，A negative。As length， but no negative cycle。

Because if there is a negative cycle， for instance， if this cycle tu tu tu at 7 minus 10 and1。

 then you know it seems like the problem is not well defined once I get to this verortex I can keep going around and round and getting more and more money out of system。

😊，The part get shorter and shorter that same you， we don't do that。So possibly negative weights。

 no negative cycles。😊，嗯。And in general， okay。This thing also shortest spots and the same thing for all pair shortest spots。

😊，So， oh， by the way， what did I want to do， I wanted to figure out。The shortest path。

 the length of a path is just the sum of the edge length。Going to a particular vertex。

 So if this vertex is you。Suppose this is a part of length 2 plus3 plus6。

That is 11 and so on so forth there are a lot of parts going from S to U there is negative 1 plus 10 that is 9 and so on so forth there is a lot of parts possibly an exponential number of parts going from S to you find me the shortest part。

😊，And in fact， yeah， it's always。Semi regularly， it kind of blows my mind that we can actually find this thing exponential number of parts。

 Gu， we can find the best one。 You， it's like it's not that bad。 di story。 just two。 It's okay。

 single source shortest paths。 So that single source。 You can talk about single source。

 single think shortest paths。😊，you know somebody had asked you know what happens in practice So in practice you want to go from here to home。

 you don't really care about computing shortest parts from CMU to the rest of the world。

 but we are doing worst case analysis out here。And in this case。

 computing singles source shortest path is pretty much the best runtime unless you make specific assumptions graph structure is pretty much the same as computing single source。

😊，To all things。So we just compute single source short parts。Compute for me。

 this shortest parts from S to every other vertex of the graph。And then all pair shortest parts。

 this just says for every pair U and V compute the shortest parts from U to B。😊，What。嗯。

So for the longest time， you know， let me give you the punch line for the longest time。

We have known that if the weights are non negative， this is approximately。😊，Lient。

There is Israeli log term sitting out there and people are worried about getting rid of those lock terms because you know。

 by gum， we are theorists we want to figure out the truth。😊，周。呃。But give or take a log or two。

Actually， one log。诶。This is the right answer， single so short is past non negative attributes。

Possibly negative averages for the longest time for 50 years。

 we have known algorithms that run in this much time。😊。

Last year we came up with an algorithm that runs in。Okay。I mean。

 there were improvements in the middle， I'm not saying that you know we were sitting around dwidling our thumbs。

😊，But。Like， this is amazing。So it blows my mind and it blows my mind in two different ways。

 The first is that we have found it。😊，And secondly。So this this lecture that I give。

 this is lecture number three of our course， right。😊，In lecture number four of our courses。

 I' will teach you something called low diameter decomposition。😊，It's a very simple idea。

 and I'll teach you with。😊，And it turns out that this uses two ideas。

 the first one from this lecture and the second one from the nextect。😊。

So I will try to tell you in the following lecture after that how to get this result。😊，对。

For all pair shortest parts， the situation is kind of interesting。😊。

This is our best run time for all page sort5 order and cubed。And， in fact， you know。

 we are still in this situation where。We don't know what to do。So this is。

 this is like a challenge problem for。嗯。미 don는 같요。We should do better。What the thing was。

is that for only like when it's negative， it's harder， or was that attached to the whole problem？

ButSo when it's yeah， so when it's negative， so it's single or short of paths So it' negative actually like like like negative。

😊，AhaSo so the way I would say is if you're doing homeworkbo zero， for instance。

 there's this sort of question of like ditra fails。😊，And so you have to。

 you might have to do work again and somehow like。Essentially。It's a very good question。

 why does being negative make it harder？😊，And it's not satisfying that。Our algorithms fail。

But to some extent that was the best answer we could give because there were no concrete lower bounds and then the reason why there were no concrete lower bounds。

 right there is an upper bound。😊，We just didn't know how to do it。Now， we do。哦你就停一。

So for the all fars case， that's with non negative points or possible so in this case it。You know。

 then you're possibly negative。Both both。Yeah， if you only have positive edge weights for all page short parts。

 more or less， the best result is order and N。😊，Which is just run anti dis。

And I'm cheating a little bit， you know， there are slight improvements here there。

 but nothing substantial。😊，Good， okay。So let me tell you， you know。

 basically a review these results will come out of the slides。😊。

And most of this I'm assuming is review for you。😊，I'm not going to prove almost anything。

Im just going to remind you what you probably know。So you know。

 classic algorithm is diextra as algorithms。E weights are written as W right now。 Yeah， O， W， good。

And the final distances are I'm going to denote by Dxy。😊。

And sometimes I emphasize that these are distances with respect to the weight w。

 So hence the sub w of。😊，This is the distance between x and y。So in this graph。

 the distance between B and c is2 because of that direct edge。The distance between， yeah， what。

 you guys know what shortest parts。What's Dyexter Dyextra says。Do the following。

Assign everybody a label。Initially the label of the source， the source is s。

 the label of the source is0， the distance， the shortest parts from the source to itself is0。😊。

Everything is not negative， right how mean how can the source get back to itself in short？

And right now， we don't know any of the distances to infinity。

Distances to other ver also LED them to infinite。And what you do is at each point in time。

 you extract the minimum label。😊，嗯。So initially you'll extract that guy。And you'll say， okay。

 its distance is now fixed， we remove it from consideration。😊，And we relax all the other things。

So what's happening？So just before， you know， just think of the movie playing again。Just before。嗯。

The distance from S to B was。Like S was a 0 and B that infinity。

So if you think of this edge from S to B。B is sitting an infinity S at0。The edge。Infinitely stressed。

I want to relax。I'm just going to say the label of B will now be。The minimum of a horizontalal label。

And the label of s plus the distance from S to B。When to relax。That's the sort of。

 that's why when you see the word relaxed， that's why they're using the word。😊。

These edges are stretched overtight，So now you've relaxed all these age。 Now， I know the distance。

 I say F is fixed。 S is right there。😊，So all the B c and D will become at 2，6 and6。

 that is what we happen。 I I still don't know way to get to E。😊，ok。

And then I pick the minimum day out here。Minimum label unmarked。I set it this I mark as final。

And then I relax all the other。And so you'll notice that the distance of C went from6 to 4，6 to 4。

Yeah。Because earlier， I knew a part of length 6。 now I know a part of length。

And the distance to E have gone from infinit to4 as well。嗯。Wored。O没 good。嗯。

We don't have to evacuate quite here， okay。And this just goes on，At each point in time。

 I pick the least label of the unlea。the vertex， which is unmarked。

 which has the least label and market。😊，And I relax all the thought going age。And I just keep boomed。

And the proof is an inductive proof。That whenever I mark vertex， its label is correct。😊，Yeah。Also。

 you can implement it like super fast， there are M decrease keys。😊。

Because relaxing is just like decrease key， So you are maintaining a priority Q data structure。😊。

For every age， you have to relax at once。So there are M decrease keys and N extractments。

We have Nazi heap M plus N login， even regular heap M M login is the pillarderity。Yeah， that's next。

This is a you know bread and butter whenever you need fast algorithm， next。😊，Okay。

 this was for non negative ages。 We know an example where negative ages this fails， right。😊。

Let's just move as quick example。S was head。啊嗯。This is， let's say four， this is negative 3。

 this is2 is。W。啊，AB。I'll probably Dytra will mark this guy first。 It'll say， oh， its's distances too。

It's not good。Its distance is one。You shouldn't you。And on homework zero。

 you have this problem it says， you know， run extra one more time， it'll fix it。😊。

India will run extra some number of times， depending on how many negative weightages are there on short of scale。

But Bman Ford is an example is an algorithm that you just take， you know it's kind of built in。

 and it's a very nice algorithm。 It's very decentralized。 its very yeah。😊，Okay。

 so what single source short is path so negative edge lens so now you have a negative edge negative 2。

😊，And the algorithm， all it does is it does the following。

It just says I'm going to relax everybody n minus one times。

So if you just repeat and minus one times， I'm going to relax all the edges coming out of vertexes so pick a vertex。

 relax all its outgoing edges。😊，And do this for every vertex of the ground。

And then do this in minus-1 times。Yeah。The Belman Ford's algorithm actually the notes have some discussion about the fact that Belman Ford。

 the Belman Ford moral algorithm was discovered by a gentleman called Shimbel。😊，And you know。

 this whole area is like， it's just a mess，😊，It's called Belman Ford because Ford had these ideas at some point he didn't really have a paper on it。

 but I mean Ford was。😊，Famous person， also sort of very influential person。

 So I think it's a reasonable thing to have his name out there， but I should really put Shill's name。

😊，Simbi came up with this idea。Okay。the claim is that if the graph has negative no negative cycles。

 then bellman forward。😊，Simble， more algorithm will find the correct answer。

In end the proof is by induction， you essentially prove the invariant that after round5。😊。

All parts using at most five edges are correct。Even though there might be negative issues。

There are n rounds， M time per round order M N there' is no fancy data structures。

 no nothing to be done。Good。诶。And you can also use this to detect a negative cycle。

 so almost all algorithms that correct negative cycles also can detect negative cycles。😊，My by。

 all algorithms that assume that theres no negative cycle， they compute correctly the shortest parts。

😊，They can also detect negative cycles because you know you kind of run it as though you are computing the shortest parts and then after that run it a little more if there are negative cycles other distances will start to go down。

😊，So you can detect negative cycles as well。Okay， so this is the single source shortest parts。

 just very quick recap， diextra M plus N log n。😊，Belman Ford， Shim order I。

And then I just mentioned that Bernstein， Naonkai and Wilk Nielen have this order。m玻你攞嘅。

There is a slight twist out here where youll see a sea sitting out there。😊，That's。

That depends on the the size of the numbers。So this is not true in a certain model， I mean。

 if you are allowed real numbers， this is going to be a problem。😊，But if all numbers use at most。

 let's say are of psi at most c。😊，Then this takes about log C many。Yeah。Kind of， but like for ditra。

 you can imagine Im doing real arithmetic。😊，And it will still be correct。Whereas this one。

 somehow it requires the bit precision to be finite。O。Okay。Oh polylogue is lo to the sum factor。

We know the factor， but we are too embarrassed to say it。It's no， actually， we we know the factor。

 but it's not relevant。 in some sense， in our minds， the log factors are。😊。

And they'll get beaten down。All pay shortest parts。 Okay。

 but so so there single source shortest parts， any questions about single source short parts。

 this is all like basic stuff。😊，And Im I'm obviating Im removing a whole bunch of work that's being done。

 People have really try to get these running time bounds。 you know。

 people don't like this login sitting out there。 They're like no no no， is it linear or not。

 it's just like cargo's algorithm。😊，We try。and we have improvements， there are lots of improvements。

 but I'm not going to go into that。 It's a digress right now。OK。Okay， all pay short spot。嗯。

So here is one way in which you can do this， you can non negative edges， you can run end extras。😊，你白。

Negative graduates， you can do Belmon For and Belmon For。

So if m is like n squared this is like n to the fourth if you thought n cubed was bad enough n to the fourth at like n。

😊，ok。So there is a nice algorithm out here， and it's got a nice idea behind it。

 So let me tell you this idea and that。😊，And this is an algorithm known as Johnson's algorithm。嗯。

So let me tell you the following idea。So， the main sort of star of this algorithm is the idea of feasible potentials。

 let me just go back and often often people also call these feasible prices。Okay。And you see price。

 your antennatone should be tingling。 Theres some dualls involved out there。😊，And indeed。

 there are duals involved out here， but I am not going to traumat you anymore。

 so we will do that another day。So what are feasible potential。

 feasible potential or prices are just。😊，What know， values assigned to the vertices。Slash that。

What youre going to do is so let's assign values to the word he says。And。

What I'm going to do is I'm going to assign， let's say，0 to S。 I'm going to assign。嗯。对啊。4 to no。

 I'm going to assign 7 to a， and I'm going to assign。2 to B。 And I'm going to assign let's say。

3 to C or something。We are just numbers。 Who cares when they think。So given these prices。😊。

I'm going to write down the reduced cost。Of a verortex of an edge Uv。

To be the potential or the price of you。Plus， the weight of Uv。Minus the potential of the。ok。S。Plus4。

-7。Okay。You how to be -3。This should be feasible if this quantity is not negative for every age。

So this is not feasible， whatever practices I've given you are not feasible because even on this edge。

The reduced price is negative。Let me give it。Or to this guy。So now I'm saying s0 plus 4 minus 4。

 it's reduced weight at 0。4。-34 plus negative 3。-2 is negative one。嗯。4-3 plus-1 is 0。 This negative。

 this reduce cost is 0。It reduced cost will have to be 21 plus 1 minus2。But， you know。

 I could have given some other numbers so here I am saying the assignment of0 to this，4 to this。

 one to this， two to this。Is a feasible potential。Okay。By the way， one thing you'll notice。

What we notice about the feasible potential that I just gave you？We happen to be the shortest part。咩。

In general， you can come up with feasible potential which are not the shortest part distances just on this example I came up。

😊，I hope I have some some examples out here。 No， okay， I don't have examples。 sorry。

 I'll give you examples where feasible potential。没有。So the reduced weights are not negative， right？😊。

Just by definition。Oh。So the claim is。I'm looking for the shortest part distance from x to Y。

My claim is。That this shortest part distance from x to Y。

Is equal to the shortest path in the reduced graph from x to y。Plus。

 something that depends only on y minus something that depends only on x。Okay。

So let's look at why this is true。Actually， yeah， let's look at why this is。😊，Let's look at any path。

And let us look at how these these two you know， this path has some length according to w and something some length according to w hat。

😊，Let's look at how they are related。Its length， according to w is w1 plus w2 plus w。😊。

What is its length according to w hat blah plus blah？Bless습니다。Yeah yeah。

The minus phi of a cancels this phi of a， minus p of b cancels this phi of b。So they just， you know。

 there's some shift towards the beginning and shift towards the end， but the rest is the same。

So if I was looking at the shortest path from x to y。The shifts are the same。So the shortest part。

 according to reduced weights， is the same as the shortest path according to water。😊。

The length is different， depending on this shift taxon。

The shortest spot there is the same as the shortest spot。好的。对。

But the shortest path in the reduced weights are non negative。Dash lines are non negative。

I can run the extra route。So this suggests the following algorithm。And well call this Johnson side。

Fine。F， which are feasible。嗯。W hat is the reduced cost。3。one。That extra。on。You有 questions。嗯。

And remember， we were trying to do all the short spot， right。So once you have reduced costs。

 you can run extra on this from a grid source。行。What's the runtime of this？

Time to find feasible potentials， this is linear time。😊，En extras。我。So the run time of this guy。

Is I'll write it here。啊。Is equal to step one。Plus n times M plus n。Well I'm out of time。

Let me tell you how to find feasible potentials。My claim is， whats that。

 you could do linear programming， but linear programming is slow。😊，So here is。

 how do you find these feasible potentials？😊，So here is a different fact。😊，Actually。

 if you compute shortest parts from S。Okay。And let feed be the shortest parts from it。

So let's look at what's happening。Suppose I define C， can you guys see？

Suppose I define p of V to be the shortest parts from S to V。

My claim is these are feasible potentials。😊，1。Let's do phi of U plus B from U B minusq。Okay。

 I want this。To be not negative。So I'm really saying this is the same distance from S to U。

Plus the distance from u to v is less than equal to the distance from S2。

It's greater than equal to the distance。What is this inequality known as triangle inequality？

So by the triangle inequ， this definition。😊，Ne a feasible potential。没。

So if you can find single source shortest parts， you can find feasible potentials。

 if you can find feasible potentials， you can find single source shortest parts on non negative edge weights。

😊，So the important observations。啊，我对啥都知。So the algorithm says。You Belman Ford。

To find feasible potentials。 How just find the shortest path from S to everybody。

That gives you feel potentials。 This will take one velman forward plus a bunch of di stress to find all pressures。

😊，There's Johnson's algorithm。😊，You can also do， you know。

 you don't have to find the shortest path in this graph。

 You can also find the shortest path in some other auxiliary graph where you just stick on a new vertex with0 weight to everybody。

😊，This also works not important。And there's another algorithm called Floyd Washe。😊。

With several of you reminded me is also cool。 And Floyd Wsshall， the entire code is out there。

 It its an amazing algorithm。 It runs in en cube time， and。😊，It's。It's's， it's very cute。

Also in simple inductive proof， I wont bore you with these things and let me stop here and I'll see you guys on Wednesday we will talk a little more about chart。

😊。

![](img/28cc6e568c4c05d11d45d009a508c498_1.png)

![](img/28cc6e568c4c05d11d45d009a508c498_2.png)