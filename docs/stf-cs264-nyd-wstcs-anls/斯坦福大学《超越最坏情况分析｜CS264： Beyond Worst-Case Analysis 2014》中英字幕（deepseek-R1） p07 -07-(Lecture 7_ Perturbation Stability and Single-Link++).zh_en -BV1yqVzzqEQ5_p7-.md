# 斯坦福大学《超越最坏情况分析｜CS264： Beyond Worst-Case Analysis 2014》中英字幕（deepseek-R1） p07 -07-(Lecture 7_ Perturbation Stability and Single-Link++).zh_en -BV1yqVzzqEQ5_p7-

Pick up where we left off on Wednesday。 That was a long time ago。 What were we doing。

 We were trying to prove senses in which clustering。

Grouping points meaningfully is hard only when only when it doesn't matter， meaning when it matters。

 it's easy， right， That's the contrapositive。 What does that mean， Well， by mattering。

 it means there's sort of some clustering， some meaningful groups that is there to be found。

 And maybe if we really articulate that assumption precisely。

 it will imply structure about the input， which we can then actually provably make use of in an algorithm。

 okay。So we executed that on Wednesday， and we're going to do it again today。 Okay。

 so it's going to be a different model。 It's going to be a different algorithm。

 And I'll explain in a second， why we might want to do this exercise twice。

 because there's a lot of different reasons。We're going to study the exact same clustering problem even as Wednesday。

 although let me say now almost everything we say today carries over to other popular clustering objectives as well。

 like K means， but I just want to keep things focused。

 we're going to keep talking about the K median problem to remind you the input is a metric space finite。

 So n is the number of points X。 What does it mean is the metric。 Well。

 the biggest thing is that D this distance function satisfies the triang inequality。

 So we use that over and over again on Wednesday， we're going to use it over and over again today So D satisfies the triequality。

 shortest distance between two points is a straight line。

 intermediate destinations only makes it longer。What's the objective function。

 Your responsibility is to choose K centers。 So K out of the end points。

 And want to and then what you think of is you think of every point in the metric space being assigned to its closest center。

 and you want to minimize the sum of everybody's nearest neighbor distances。 Okay。

 so sum over the end points for each point X， you look at which of the K centers as closest to it。

 You look at that shortest distance and you sum up those n numbers。 so that's what we want to do。

 to choose the K points to make that as small as possible。So I was doing this Wednesday。

 but let me just sort of remind you， I'm gonna be a little sloppy about talking about clusters or clusterings and talking about a choice of centers。

 Okay， so in the camedian problem， if we choose centers that obviously induces clusters。

 according to who gets assigned to which center， when we assign them to their shortest centers。

 so a cluster is just around center I is just the points for whom center I is the closest。

 Similarlyly， if I give you clusters， you can easily just pick which the best center separately for each cluster。

 Okay， so you can go from clusters to centers and back。 So I'm just gonna be sloppy about that。Okay。

So let me tell you about the restriction on input， the stability notion that we're going to be doing today。

 and it shares some of the spirit of Wednesdays， but it comes from a slightly different motivation。

 and it is technically different。So here's what it is。So we're just going to assume， first of all。

 that our target clustering， what we want is the numerically optimal solution to this objective function。

 Okay， that's the first thing。So last time I made a distinction between a target clustering and the one which happens to optimize the objective function here。

 we're definitely to assume they're the same。And actually。

 we're going to assume something much stronger than that。We're going to assume。

But the target clustering and college clusters。C star1 up to C star K。Remain optimal。

Under many different perturbations of the input。 Okay， remember。

 the input is really this distance function D。 So not only is it optimal for the distance function D。

 but also for many other nearby distance functions。So， precisely。Under any。

 what I'm going to call a gamma perturbation。And in general。

 I'm going to call this notion gamma stability。And by gamut perturbation， I just mean for each。

Real distance， DxY。For the purposes of thinking about whether this clustering remains optimal or not。

 you're allowed to perturb the distances。Where here sigma。Is some number between one and gamma。Okay。

So if gamma is three， for example。When a gamma perturbation for each of the N choose two distances。

 you're allowed to independently make a choice of how much to blow the distance up。

 I'm not going to allow you to shrink it， but you can blow it up。

 you can blow it up by most a factor of gamma。 Think of gamma equal 3 okay。One comment。

So for the original input， we're assuming it's a metric space。 So desatiisfies the trilineequ。

 after you do some perturbations， it might not satisfy the triang lineequ。 Indeed。

 just think about a triangle 1，1，1。 if you make one of those a three。

 of a sudden it's not satisfied anymore。 That's okay， we're going allow that。

 So we insist that opt remains optimal。 Even under gamma perturbations。

 but do not result in a distant metric distance function。So that's an assumption。 So an instance。

 a canian instance， which satisfies this property， is called Gamma stable。

So as we take gamma bigger and bigger， does this constraintsstraint get more or less stringent。

 more or less demanded。我。More demanding， right？ So we're asking more from the instance。

 So in other words， fewer instances will satisfy this property as we take gamma higher and higher。

 So the computational problem is easier and easier for bigger gamma。 Okay。

 so what we're wondering is if there is some， you know。

 magic value of gamma that's sufficiently large that we can actually solve these problems in polynomial time。

😊，And that's where we're going to quantify today。 Look at the gamma。

 which is sufficiently large so that camedian goes from NP hard。

 which we know it is in general to polytimeollvable。So that's the technical problem。

Let's talk a little bit about motivation。So， I mean， just like Wednesday。

 the authors were intending to articulate assumption。

 which is generally implicit when you run clustering algorithms and then make it precise and ask if taking that assumption literally results in easier instances。

 But they're doing it for a slightly different， implicit assumption than on Wednesday。

 So we're getting a slightly different mathematical definition。So on Wednesday。

 we had this C epsilon notion of stability。 And there。

 the implicit assumption was that if you ran a good approximation algorithm。

 a C approximation algorithm， you'd be happy with the result in the sense that it was almost the target cluster。

 So that resulted in this formal definition saying numerical approximation of the objective function better imply structural approximation of the target cluster。

 Okay， So that was the implicit assumption we were formalizing on Wednesday。

 here it's a different one。 here， really， the motivation is， well， you know。

 think about cluster think about these candian problems。

 Okay they specified by this distance function D。 Where does D come from，😊，You know。

 sometimes maybe you're literally thinking about points in three space or end space。

 and Euclidean distance is exactly meaningful。Often in say unsupervised learning applications。

 that's not what D is， X and y are not points in space， X and Y are images or documents or proteins。

 and there isn't some canonical， obviously correct way to assign distance or dissimilarity between two objects。

 you probably came up with a formula or an algorithm。

 which when you run it on two images or two proteins or two documents gives you a number。

But there's aspects of that algorithm that are going to be ad hoc。

 Okay that you're not fully confident about。 You can imagine a slightly different algorithm being just as meaningful。

 Okay， So if you have one of these sheurically defined distance functions and then you're solving the induced clustering problem。

you know tacit in your mind for this to be a worthwhile exercise is the idea that the answer to this clustering problem shouldn't be highly dependent on exactly what the distance function is。

 So if you tweak， you know， if you hard code one parameter and your distance heuristic function slightly differently and you start getting 1。

1s instead of 1。05s， hopefully， you get basically the same clustering back。

 So because D is heuristic in these applications， you want the answer to be robust to perturbations in D。

Right，So that's what that's where this comes from。 Okay。

 in clustering problems you really want to solve， that's often where you're sort of hoping is true。

 And again， in the spirit of Wednesday， they're saying。

 let's really write that down as a mathematical definition。

 Look at the instances that conform to it and study the complexity of that special class of instances。

We assume that the exactly the same cluster is still Good question。

 So I'm going to spend the lecture on the simplest version of this definition。

 where unlike Wednesday， where we allowed a few points to be classified and correctly today。

 I'm going to ask you get every single point correctly。 There is a recent work。

 which relaxes this in the way you'd expect。 given what you saw Wednesday and says， well， you know。

 you move the D's by gamma and and opt only it only changes on an epsilon fraction of the points。

Similar statements are true。 via similar algorithm， similar arguments。

 All of it's more complicated than what I're going talk about today。

 But the algorithms are in a similar spirit， the proofs are a similar spirit。

 The constants are worse。 and you need a big clusters assumption like Wednesday。

 which we won't need today。😊，assumption is extremely stringent。 It is stringent。 It is stringent。

 but as we'll see， it's not， you know， it doesn't trivialize the problem。

🎼Especially as you think about varyan gamma， there's actually going to be interesting regimes under which the problem is sort of trivial。

 solvable， but not trivial， and then unsolvable， meaning empty hard so gamma gives us a nice sort of parameter to play with how much stability you need to imp tractability。

 but absolutely， I mean the epsilon equals zero if you like assumption is a strong one。

 but that's going to make it so I can make all the points I want to make in this lecture as cleanly as possible and there is work without that assumption。

O。So， motivation。Distance function。Is often heuristic。And so you want robustness。With respect to it。

Okay。So you're thinking about that being a sort of。

 that's a property you're really hoping your clustering problems possess。 Okay， bless you。Good。

Allright， so why are we doing this twice， Why do we have a second lecture doing kind of the same thing as Wednesday。

 Well， there's a few reasons。So one reason is just that， you know， this is sort of， in every respect。

 a bit different。 Okay， I really think this is a distinct。

 implicit assumption people make when they do clustering。

 And so we get a different formal of definition。 We're going to talk about different algorithms。

 and we'll see some similar things in the analysis。 But the proofs aren't the same either。

 So we'll see a host of new ideas。The second reason is that， you know， just out of academic honesty。

 I want you to be aware that， you know Wednesday's notion is not the only notion of stable clustering。

 Actually， this has been a super hot area for about five years。

 There's at least five different candidates。 They all have roughly the same spirit and you get roughly the same conclusions about strong enough stability implies tractability。

 And I wanted to show you that at least there， there isn't just one。 Okay， there's a couple。 right。

 And on the homework to explore the relationships between some of these。 So that's another reason。

 just so you you have some awareness of that diversity。

Another thing which is kind of cool is that even though this mathematical definition is different than Wednesday。

😊，We'll see that it winds up imposing similar types of structural rigidity on the optimal solution。

 It's again， going to basically imply。 Youll see this in the proofs。

 It'll imply that in stable instances， for big enough gamma opt basically has to be a bunch of tightly knit。

 well separated clusters。 maybe modullo a few outliers。

 that's basically what we proved in the analysis on Wednesday。 We'll see all those themes reoccur。

 So it's kind of cool seeing this different definition lead us to kind of the same point。

 And so relatedly another reason why I want to do this twice。

 is because you know both of the definitions I'm showing you。

 plus the other three or four definitions out there in the literature。 know。

 you look at any one of those definitions。 And you not you're probably not going literally believe any one of them exactly。

 You assume real data might sort of satisfy it， but strictly speaking。

 will definitely violate know some of these definitions。

 at least for the parameters that we're talking about。So， you know。

 if you're trying to reason mathematically about some phenomena。

 like say clustering seems easy in practice， you know， obviously。

 the holy grail would be you just write down this mathematical model。 that's uncontroversial。

 Everybody's like， oh， yeah， you totally nailed what this is really about。

 And then you prove some awesome theem that like exactly matches what people observe。

 that almost never happens once in a while。 once in a blue moon。 But it that's just not how it works。

 Okay， mathematical modeling。 So you have to make some compromises some overly strong assumptions to prove things。

 And so then you get nervous。 You're like， well， you know our conclusions and artifact of our assumptions are they actually sort of uncovering something real。

 So in you of one perfect model， a nice alternative is to have many models that are in perfect in different ways。

 All of which seem to be leading you toward the exact same conclusion。

 then you start having even though each model is highly questionable。

 the overall message from the suite of models starts looking believable。

 you start amassing some confidence in what these modeling these models are saying。

 like clustering is easy in many instances。😊，Of interest。 Okay， And so that's sort of another。

Take away of these couple lectures。 Okay， we'll get basically similar messages。

 takeaway messages from two different models that reinforces our confidence in both of the models and their predictions。

One final reason this is a fun one to do。 on top of the previous one。

 So last time showcased how making explicit an assumption in the data can lead you to exploit an algorithm。

 So we came up with an algorithm on Wednesday。 We really never would have designed had we not written down that stability definition。

 probably the high level ideas were know pretty nice distance thresholdholding and looking for number of common neighbors。

 Those are kind of high level ideas。 But the exact algorithm was definitely driven by the stability condition。

 Today， by contrast， we're going to show that a very nice novel twist on a very simple。

 very well known clustering algorithm actually does get polytime solvability results for stable cable median instances。

 so here we're going to use this definition。 more just in the analysis of a known algorithm as opposed to drive new algorithms。

😊，All right， so any questions before we begin the technical development for today？O。All right。

 so let me just segue from that until， you know， all right。

 So if we wanted to explain the performance of some simple wellknow clustering algorithm， okay。

 what's a simple wellknow clustering algorithm。So let me tell you about one。

 you might have seen this， I usually teach this in 161。It's called single ink clustering。

Which might well win popularity or at least kind of name recognition contest in cluster and contest。

So it how it work。 It's really nice， actually。 So， so remember we're like K median or something like that。

 So， you give me a metric space。 and you tell me K。😊，So this metric space。

 I want to think of it as a graph。So the nodes are just the endpoints。

And the distances are just edge weights。So it's a complete graph， a clique weighted。

 the distances of the edge weights。Then what I'm going to do is I'm just going to run Cr School's minimum spanry algorithm。

Okay，So hopefully you remember when on span trees。 Maybe you forget which one's crustco。

 which one's prim。 Okay， crustscos is the one where you sort first Okay， from smallest to biggest。

 you do a single pass through the edges。 And if an edge is going to create a cycle with what you've already taken。

 of course， you don't take it because you want a tree。 But if it's not going create a cycle。

 then you include it。 And it  fuses two connected components into one。

 normally in crustsco's algorithm， you want an MT。 So you just run it until you have a tree until you take n -1 edges。

 here， we don't want a tree， we want K clusters。So we're just going to stop it once we have K connected components rather than just one。

Okay， so that single in cluster。So run Crco's MST algorithm。

I'm just going to write on the metric space when I really mean on the complete graph with distances as edge weights。

Stop when K connected components。Okay， so remember when you're co these edges one at a time。

 initially， you have n connected components， just isolated vertices。

 Each new edge replaces two connected components with one。

 So it drops the number of connected components by exactly one。 Okay。

 so each edge edition of Ksco's algorithm derements the number of connectedine components at some unique point。

 we hit K。😊，All right。To questions about the algorithm。Clear what it is。I'll code this up。

T0 lines of python right now。Or you have in the past， probably。O。

So if we wanted to prove that a simple clustering algorithm works well in stable instances seems like the obvious thing to try to prove would just be to say。

 well， as long as gamma is sufficiently big。 we don't really have a feel yet for what gamma needs to be。

 But know， it's easier of gammas bigger。 So somehow， you know。

 for some magical value of gamma sufficiently large just run single and clustering。

 that's gonna give you K clusters as we discuss， given the clusters you can just separately for each one figure out which the best center is。

 And then you're just hoping that's gonna to boom， be the optimal K median solution。

 that would be kind of like the simplest possible thing that could be true。

 Basically about clustering stable instances。😊，All right， well， it's not going to be quite so simple。

Let me show you an example。Which shows we're not quite off the hook。So suppose k equals3。

 So we want three clusters。And M is going to be a parameter and it's going to be big。Okay， how big。

Yeah， a million， whatever you want。And。So here's what it's going to look like， the metric space。

So there's going to be four groups of points。 Okay， and in a group of points and a group of points。

 everybody's going to be basically co located。 Okay。

 so distance like epsilon between everybody in the same group， O。So， endpoints。Distance roughly zero。

 so that's a group。Same thing here。M points， distance， roughly 0。Enpoint。Distance roughly 0。

 The one twist is going to be。 this is going to be a tiny group over here。Tiny mean。

 let's say 10 points。But again， basically co located。Okay。Now， if only we had four centers。

 if only K was four。We'd be golden。Right。We just put one center in each group。

 and everybody would be distance 0 from some center。 So our camedian objective would be like zero。

 right。But the problem is I've only given you three centers， okay？So intuitively。

 you're going to have to merge two of these groups into one。O。

So suppose the edge weights are as follows。10 on top。Two on the left， one on the right。Okay。

So take 30 seconds。And figure out what the minimum objective function value of any K median solution。

 Any three median solution is。 so just stare at the picture for a little bit。他只能。

That's a two on the left。So the way to think of it is you've got these four。

 you've got three super dense cities。You've got one superd town， a really village。

And then you've got kind of this path through them， where the path length are 2，10 and  one。

And basically， you have to， you're allowed to build three。Firehouses。

And you want to minimize sum of people's distances from the nearest firehouse。And again。

 if you could build four firehouses， no problem， just build one in each city and also in the town。

So what seems like， I mean， phrasing it this way， if I only let you build3。

 it probably sounds kind of obvious where you should build them。 right， I mean。

 you've got these like three cities of a million people。

 and then you've got this to town town with 10 people。 Okay， so the town with 10 people okay。

 they'll be like two miles from a fire station。 big deal。So opt， I hope you agree， is like 20。

So zero for everybody there， zero for everybody there， zero for everybody there。

 two for each of those 10 people。So that's the first thing to note。

The optimal came mediaian thing is， like 20。So single min clustering。 Okay， so it has to output 3。

Cluters， which means it's going to output a tree-2 edges， okay。

So another way to think about this single in clustering is you sort of run cross to the end。

 and then you kind of like rewind。The last K -1 steps。

 In case we're going to rewind the last two steps。 So what were the last two edges that Crusco would include in its tree in this instance。

The two and the 10， right because it goes from lowest to highest， right So cross school。

Is going to output the clustering。Then you get after you delete。

These two edges and the one is still in there。Okay， and remember， we're only allowed one。 I mean。

 there's a correspondence between centers and clusters。

So by virtue of fusing the two right hand things， right hand cities into a single cluster now are in huge trouble。

 right， Yeah， there's only a mile between them， but their populations are both a million people。

 Only one of them gets the fire engines。 So now we have a million people a mile from fire engine。

 Okay， so we get a million as our single link clustering objective function value。Okay。

Total disaster。 I hope you heard it。Right， so a single link。Is like M。All right。

 so now I owe you something else。For this to be interesting， right， which， I mean。

 we know camedians hard in worst case instances， right， And implicitly in this I've been saying， oh。

 look how easy it is so obviously tell what opt is bla， blah， bla， b。 But the missing link。

 which I'll put as an exercise， is's just easy to check I that actually this is a stable instance。

 it's actually stable instance for gamma as big as you like。 Okay。

 for every gamma you can take M sufficiently large so that it's gamma stable。 Okay。😊，So upshot。

You know， we started with the nicest thing that could be true， right。

 which is single inch just works。The guyss false。It's time take a step back。Now， maybe we say， okay。

 well， can we have just like a not to， you know， you know。

 can we have a nice little twist of single link， which always works。

And the answer is going to be yes。And it's both a nice twist on single link。

 So it's kind of a nice extra idea。 And then also it's just cool that this will work。O。

So any questions about the example， Edward Greece， vanilla single link is not good enough。All right。

 then let me introduce you。To what I'm going to call single link plus plus。

The authors don't call it that， probably they should have。

I more people would know it if they called it that， but I'm going to call it that。

Single language plus plus by Bom， Balkan and themala。

They came up with this algorithm in a different context， but it sort of works out of the box here。

 which is cool。So this is just nice， actuallyly。 this is a nice， nice idea。So。

What we do in the first step is we run Crsco till completion。OK。

And what I want to point out to you is there's a really nice way to think about the tree that crustco builds up edge by edge as what's called a hierarchical clustering。

And I think if I show you a simple example， you'll see exactly what I mean。So。

Consider the following five vertex graph。Over the following edge weights。So to run Crsco on that。

So we start from low to high and we let it go， right？

So first thing happens is the one gets chosen by crosscool。 Okay。

 so U and X used to be connected components。 They get fused into one。So now over here。

I'm going to start drawing a tree from the bottom up。So this is U and X。

 These are the two nodes we just fused。They're gonna have a parent， which I'm labeling with the edge。

 or rather the cost of the edge to join them。So the one edge， when crustsco included。

 it fused the U and X into one。What does Crsco do next？ Well next Crsco takes the two。Okay。

Fusing the V and the Y。Okay。Next， it takes the three。

 which fuses together the UX component and the V Y component。

 or equivalently fuses together the two connected components represented by these subtes。

So now these two are going to get a parent， which I'll label with three。So these are just the no。

 these correspond to the edges included by crossco in the order that it took them。

Now when cr gets to the four。Now we create a cycle， so Kesco skips that。

Then Cru goes to the five and it picks the five。Okay。

 and the five joins together the hitherto lonely Z。With this big other component。 so we have a five。

There。So notice， and I think you'll find it very easy to believe that these properties hold。

 no matter what the graph is。 So this hierarchical clustering tree on the right in purple。

 it has exactly N leaves。And the leaves correspond exactly to the nodes of the original graph G。

So let's call this G。Let's call this each。So G has n nodes。H has n leaves。

 which are exactly the n nodes of G。The internal nodes of H correspond exactly to the edge additions by cresco。

 Okay， so each time crustesco has an edge， you add a node to H， which then has two children。 Okay。

 so there's n -1 edges in a tree。 and there's n -1 internal nodes in H correspond to the n -1 minimum spanning tree nodes。

Also。If you look at subtes of H。Subrees of H correspond exactly to。

So if you look at the leaves of a subt， the leaves of a subtre were at some point in the execution of Crcu。

 a connectedtic component。So like here's a subre。It has the leaves U and X。

 So the claim is at some point， U X was a kinetic component in Crusco。

 And it was right after the first edge edition， it was U X。Same thing here。

 If I think of the surgery starting at three， I get UX V Y。

 So the claim is at some point that was a kinetic component in Crco and it was just before the final edge edition。

So there's also a total correspondence between subtes in H and kinetic components that ever showed up in Cruco。

 And the number of these things is exactly 2 n -1。Okay， so here there are n leaves。

 N -1 internal nodes。 That's one way to see it。 Also， if you think about crusticle。 I。

 you start with n kinetic components and each of the n -1 relevant iterations。

 you destroy two old ones that introduce one new one。

 So that's a total of 2 n -1 over the course of the algorithm。So again。

 correspondence between nodes of G， leaves of H， kinetic components of G， subtrees of H。Okay。

 and internal nodes of H and tree edges and G。Is all of that clear？Okay。

 so this is just a really nice way to kind of think about Kscoll's execution。

So how are we going to make use of it？So here's what we're going to do。

So single link without the plus plus， again， I told you one way you could think about it was you run crustcal to the end and then you rewind the final K minus1 iterations and you get K clusters。

But now that we have this tree that we're looking at。

It's going to allow us to visualize many different ways。

 We might delete K -1 edges from the M T and gives various K cluster strings。

 What we did before will be one option out of many。So。By a K pruning。Of H。What I mean。 So again。

 this is H。 I mean， you delete。K minus1， internal nodes。Starting from the top。

I'll say a little bit more what I mean about this。A second。Right， so。If this is a set S。From the top。

 what I mean is that if a given node is an S， it should be upward closed。

 then its parent is also an S。Okay， so S here， the nodes were removing from this tree。Cha。

So let's just start super simple。 Okay， so let's just say K was 2。Okay。If K is2。

 there's actually only one possible two pruning。Okay， because I have to delete from the top。 Okay。

 so that means if I'm gonna take this。Tree hierarchical clustering and get two clusters out of it。

 The only thing， by definition， this is my definition。

 The only thing I'm allowed to do is kill off the five。And that gives me a partition into U X， Y， Z。

 sorry， UX， V Y and Z。Now， if k equals 3 and I'm allowed to delete two nodes。

 then I have two options。 Okay， this tree， actually， I don't have two options。

 But let's say in a balance tree。Like this。If I'm going to delete two nodes from the top。

 I have two options。 Okay， Defly， I'm stuck deleting the root， okay。

But now I can delete either the left child of the root or the right shot of the root。

 O Each of those gives me an induced three clustering。So if I delete this one。

Then that's the induced three cluster。On the other hand， if I delete this one。

Then this is the induced。Three question。So you clear what I mean？So you delete K -1 from the top。

 Notice it's a binary tree。 So every time I do a deletion。

 it shatters the tree into one more component than I had before。

 So K -1 deletions do indeed give me K clusters as desired。Okay。🎼Another way to think about this。

 right， So imagine you delete from the top， right， you keep shattering this tree into subtes。

 At the end of the day， What do you have At the end of the day。

 you have a partition of the n leaves of the tree into K subtrees from the original graph。 Actually。

 that goes the other way， too。 if you think about it， if you show me。

K subtes that are disjoint and that are petition of the leaves by deleting everybody above them。

 That's what I get back。So in other words， what you can get topped down by deleting k minus1 nodes from the top are exactly the partitions of the leaves into K groups that correspond to subts。

A we clear on that？All right， so back to single link plus plus。So， the point is。

We have a lot more options。So single link， again， I was only allowed to go back and delete K -1 things in a unique way。

 I had to rewind Crsco's algorithm。 Now， we see that as long as K is at least three。 I have options。

And the plan of single in plus plus is to optimize over all of those options。So compute。The optimal。

K per。So I'm going leave for you to prove on homework 4 that this can be done in polytime。Okay。

 this is a relatively straightforward exercise in dynamic programming。And again， when I say optimal。

Right， so if you delete K -1 things， you get these K clusters。

 you pick the centers in the obvious best way for each cluster。

 And then you look at the k median objective。 Okay， so when I say optimal。

 I mean the one that induces the best K median solution Okay， with the optimal choice of centers。

So let's go back to our bad example。Which broke the original single in clustering algorithm。

So this is going to look a lot like our balanced tree over here。So now， instead of you know。

 just aorting before the last iterations across school， imagine we run it to completion。Okay。

 so obviously， the first thing Crusco does is it picks all of the zero length edges until all of the cities get fused together and the township gets fused together。

So you've got your M， your M， your M， and your 10。 these are the population sizes。

And then what does Kreesco do， What picks the one。Yeah， that's right。Then it picks the two。

And then it picks the  ten0。Okay。So now remember K equals 3 in this spa example。

 So we're allowed to delete two nodes from the top。 Okay， and one's got to be the root。Now。

 single link where you rerd Cresco that's going to delete just the largest ones。 Okay。

 so it's going to ignore the graph structure or the objective function is's just going to say。

 what are the highest labels I can see。So a single link would delete those。 right。

 And that's why we wound up in this bad case with a single center for two cities of population a million。

In singlelink plus plus， we're allowed to optimize over all of the options。Granted here。

 there's only two options， right， There's that one， and there's that one。 But single link plus， plus。

 will'll consider them both。 and we'll say， hey。That looks a lot better。Okay。

 so that's the one that's going to pick。So certainly it does fine in this example。

 That's all I' convinced you。I mean， it's obvious it could only be better than single linkage because。

 you know， the original single and K pruning is one option that it optimize over。

 So it'll always be better。 The key point of this theorem of this lecture is a theorem that says。

 actually， this recovers the optimal K median solution in three stable instances。 It turns out。

So any questions？是一す。Cl that it would do much better in something like this。

Where you have to take the route and maybe Z is very far away from。Sure， yeah。

 but then then opt is gonna suck too。 So sort of not a problem。 I mean。

 it it's it's someone else's problem。 right， So always， this is always what's funny right。

 So when you have these objective functions and you're talking about， you know。

 computing the optimum or computing something close to optimum。

 an implicit assumption we always make in the analysis is that the optimum is actually useful。

 But you'd be happy to have the optimum。 Not always true， But then that's sort of like upstream know。

 that says add moreesis to the system or like get rid of some of these constraints or whatever。

 So So in this class， we you're just gonna to be happy to get the optimum， whether it be good or bad。

😊，对。Good other questions。So that's going to be our algorithm。 This is our protagonist for the day。

I think it's， I think it's， you know， it's a very nice algorithm。 This has been， you。

You can imagine coding it up other people have certainly code it up。 It's a nice idea。

So rather than just commit upfront to a single K clustering。Generate this tree。

 which implicitly encodes lots of different K clusters， which you can optimize over efficiently。

 Very nice。Okay。So here's the the we want to prove。Swati， Blum and shed。So for all gamma。

 at least three。Single link， plus plus。Compututes opt。And gamma stable instances。

So you should be wondering， you know， is this good or bad， Like。

 should I be impressed with this three。So the homework will have some stuff to you know help answer that question。

 but I'll just tell you the punchline now。 So first of all， this algorithm。

 so single link plus plus does not necessarily recover optimum once gamma drops below three。

 So as far as the analysis of this algorithm， gamma equals three is tight。

 it's the right answer okay。If you change the algorithm， it still has a similar flavor。

 but the linkage step is a little bit smarter。 Then it's known how to get down to gamma equal to one plus square root 2。

Okay， so like 2。414， by a variation of the algorithm。

And it's also known that it's forget about any particular algorithm。

 It's known it' N P hard to recover the optimal solution once gamma drops below2。

So no algorithm can get below 2。 We know algorithms that can get one plus root 2。

 This algorithm gets 3， and that's as good as this algorithm does。

So that's sort of what we know about this question。Good。So let's turn to proving this。

So here's how we're going to prove it。We're gonna look at the algorithm。

 We're gonna to look at the single linkage plus， plus algorithm。And we're going to ask ourselves。

 what has to happen。For this to work， for this to have a chance of working。

What are sufficient conditions on the input are really on sort of the execution of this algorithm that in the second step。

 it'll actually be able to find the optimal solution。

Then once we have a good understanding of sufficient conditions。For。

The success of single linkage plus plus at that point will actually invoke the stability property and show that it implies the sufficient conditions。

So for now， I don't want you to think about stability per se。

 I want you to think about this algorithm。For this hierarchical cluster tree。

 and then among all ways of deleting k minus1 things from the top， compute the optimal k pruning。

 and we're hoping one of those is indeed the optimal k median solution When is that going to happen？

So， sufficient conditions for success。All right， suppose。Okay。

 so now we just have any camedian instance。And we're hoping that。

The best k pruning of this tree is indeed the optimal cluster。s when's that going to happen。

So let C star1 up to C star k denote the optimal cluster。So first allll state something。

 which is really sort of equivalent to it succeed。 Okay。

 The second one is just going to be a sufficient condition。 This one's really an equivalence。

 So what has to happen。So it has to happen。So remember， I told you。That theres。

 so there is a bunch of correspondences between the graph G and the tree H。

 One of the correspondences was the subt， the  two n -1 subtes of H。

Correspond exactly to the connected components that show up at some point in Kescoll's algorithm。Now。

 when we take a k pruning at the end of the day， what are we going to hand back as a clustering。

 It's going to be a collection of subtes of this cluster tree。 O。

 so we've committed to outputting subtes of this thing。

So for us to have a chance of output putting the optimal clustering。

 every optimal cluster better show up as a subt。Industry。

So this is really just sort of rephrasing a little bit what it means to succeed。So every C star eye。

Appears。At some point。Incrible。你看。And again， that's really， remember。

 that's really like two statements。 First of all， our outputs， our subtes。 Second of all。

 subtes are going take bonus in crossco， O。So basically， you know， as the analyst。

 we we think about it ourselves as knowing what the optimal solution is， right， And we have。

 you know， there's these like there's this cluster of 5 points， you know，3，7，10，18 and 22。

 And we know what it is。 And we're like watching Crusco run with our fingers crossed。

And we're really hoping that this cluster shows up。What could go wrong？Well， okay。

 so suppose this cluster has five points and suppose his Cru schools like joined three of them together。

Okay。So that sounds good。 But what can go wrong is if all of a sudden to join some point from some other cluster before it gets to those last two。

 re host。Kecttic components only grow over cresco。 So if you get in one cluster points from two different clusters。

 Sorry， two different optimal clusters， C star I and C star J before you get C star I completely done。

 You're never gonna see C star I as a kinetic component in cresco。O。Okay。

 so that's what we're worried about。All， so this is this is what we need。 Oh right。

 So what's the converse。 So I argued that this is certainly necessary for the algorithm to succeed。

 Why is it sufficient， Well， if every C star I appears as a subt。

 we compute the best collection of subtes。 So if the optimal is in there， we're gonna find it。 Okay。

 it's gonna be one of the things we optimize over。 Okay， so this is if and only if。So now let's。

Forgettable， let's just take this on faith。 This is our new goal。Okay。

 this is our new success criterion。 What's a sufficient condition for this to happen for every optimal cluster C our I comprising however many points。

 we want exactly that set to show up as a connected component at some point in Crusco。

 When will that happen。Well。So here's going to be our final condition。

I claim that if this property two holds were golden， O， S link plus plus is going to work。

Consider an optimal cluster， ceased our eye。And consider a strict subset of it。Okay。So like a here。

 those are the three points out of the five that we had so far。 That's what you think of them。 Okay。

 we're really hoping these other two will get joined with this cluster。

 We're really scared that points from some other C star J is going to get joined first。😰。

So for all I， for all strict subsets of the optimal clusters C star I。

 the condition that will be a sufficient condition for correctness。Is that the closest point？

AndI'll draw you a picture in a second。 The closest point to a。Remember， x is the set of all points。

 So the closest point to a， not counting those already in a lies。In C star I。Not outside of CstarI。

Okay， so here's the picture you should have in mind。We've got A。

 these are the three points we've got so far of the cluster。

These belong to some bigger cluster C star I。There are various points， not in A。

 Some of them are in C star I。 Some of them are not。Like for example， maybe this is a C star J。

And this condition says， the nearest neighbor to A。Better lie inside seastar I and not outside。Okay。

So I claim this is a sufficient condition。 If two holds， then one holds。That's what I claim。

Why is that true。So let's say notes。2 implies one。So here we're really going to use properties of crustsco。

 The crustesco really considers the edges from shortest to longest。 So imagine。

 so consider your favorite C star I。O， some cluster and fast forward crustle until the first time that some edge is chosen with exactly one end point in C star I。

 Get one end point in C star I and one end point outside of C star I。That's got to happen sometime。

 right， because Crusco eventually merges everything together。 Okay， so at some point。

 stuff in C Star gets merged to other stuff。 So look at the very first time that that happens。 Okay。

 it hasn't happened yet，Now， what the claim is C star I has to be complete by this point。 O。

 because if it wasn't， then we'd only have some strict subset a of C star I。Okay。

 and instead of joining some point outside of C Star I， we join the closer one。

 which is inside C Star I。 conditionition 2 says that that point must exist。

 If you don't have all of C star I yet， the closest thing to you， Ie。

 the next one considered by Crsco lies in C Star I， not outside。

So that means the very first moment at which you pick an edge that's in and out of C star I。

 C star I has to be complete。 Okay， it must be the case you've already connected all C star I together。

So that's why2 implies one， okay。Any questions about that？All right， so just where we are。

 here's what we want to prove。We want to prove single link computes opt。

What we've shown is that if the input satisfies property to， then single link plus plus computes opt。

 Okay， so stable or not， whatever the instance is， if this is true and notice this is not about the algorithm。

 right， This is a statement just about a metric space。 Okay， some optimal clusterings。

 the C Star eyes， you can just enumerate overall A's and check if this holds or if it doesn't hold。

 if this always holds， boom， we're done。 Our algorithm works。OK。So the missing link。

 all we have to do left in the lecture。Is prove that if an instance is stable， three stable。

Then this condition is guaranteed。That's all the remains。Everyone back。Right。So。To do。Oh。

 this totally goes in the wrong direction， isn't it。No， that's the right direction。 That's the right。

 mind。Note。Oh let's say to do。3 stable。Andlies to。So that's the rest of the lecture establishing that。

Making the link between the stability of comedian instances and the sufficient criteria for success for single link plus plus。

Right。So there's going to be three steps。EachNone of them too bad。

 but each slightly trickier than the first one。Why don't you take a minute。

 I'm going to write down the first step。 Take a minute to think about this and。

Discuss it with your neighbor， if you want。So we're going to do now is we're going start from the stability property。

 we're going have a stable instance。 And so what we're doing now is're going to have the same feeling of the exercise we do on Wednesday。

 We said， okay， we have this instance。 we know it's stable。

 but the stable reference is optimal solution and we can't compute the optimal solution or that sort of circular。

 We're trying to compute the optimal solution。 So how do we actually use this。

 So we're going to start from the stability property assumption and derive a bunch of consequences that are a little easier to work with Okay。

So here's the first one。So suppose you're three stable。 And again， remember what this means。

 This means you're allowed to blow up distances any you want between a factor of one and3。

 and op stays exactly the same。 Okay， That's what three stable means。Evienceence is three stable。

Then， we get。Something which looks a lot like the well separated condition we had on Wednesday， okay。

So for all points in the I optimal cluster。 we don't know what this is。

 This is just for the analysis at the moment for all X and C star I。

If I look at a cluster center for some other cluster other than x's。

 it's going to be way more far away from x than x's cluster in its center I。Specifically。

 it's at triple the distance。Between X and its own center C I。 Okay， so here。

 just to make sure the notation is clear， that is optimal clusters C star1 through C star K。

 C I and C J are the centers of those optimal clusters。

 X is some point in cluster I in the optimal solution。 Okay。

 so this is just saying like well separated。 the centers to which points are assigned are way closer than the second best option。

Okay。So take a minute and see if you see how to go from the stability assumption to this conclusion。

 It's not， it's not trivial。 It's a few lines， but if not。It's not， not straightforward。All right。

 so let me let me show you the proof。So the sort of the problem we have to solve in come with the proof is how do you invoke the stability condition。

 basically right So that you know sort of gives you this freedom to kind of blow up distances。

 And then you have to start thinking， okay， what would be a useful subset of distances to blow up in some way。

 So it turns out to work well here， especially kind of given the clue of the statement is what we're going to do is we're going to take the cluster C star I And we're just going blow up all the distances inside C star I by a factor 3 by the biggest that we can。

Okay。So。Blow up distances。Inside C star I。By three。Okay。So， for example。

 this distance does not get blown up because CJ is in a different cluster。

 so only if both points are in C star I， you get blown up， So that doesn't get blown up。

 but this does because they're both in C star I。So by stability。Off stays the same。Okay。

 this is actually the only time we'll ever invoke the stability hypothesis in the entire lecture because this's one point。

So op stays the same。So opt is C star1。Up to C Star K。And so the centers， the clusters stay the same。

 The centers also stay the same。Right，Because given a cluster， what's the best center。

 try them all and see which one minimizes sum of the distances inside sea Star aisle。

 the distance is scaled by the same amount。 So same cluster is optimal， namely C I。And， you know。

 because it's optimal， it also means that， you know， you do better assigning X to C I than to C J。

 Okay， What does that mean， That means x's distance to C I。

 even after the blowup is smaller than its distance to C J。 that's exactly what the inality says。

 The inality says that this distance， even blown up by a factor 3。

 still is less than the distance to C J。So that's step one。

And again you saw something like this on Wednesday。 Okay。

 and I I basically think it's a feature that we're that we're seeing similar structural constraints emerge from a different definition。

 Okay， actually， I find this pleasing。Okay， so you're much closer to your center than the second best center。

 is what this says。All right， step two。Yep， so just to be clear that CJs are。

Possibly different for all the X possibly。For all the xs。

 So like x could be one x in C could be closer to。 So I guess I should say for all J not equal to I。

That would certainly be a more precise statement。Does that answer the question or yeah。Yeah。

 so every single center other than your own is far away。So in particular， the second best one is。

Thanks。Okay。Allright， so now， so this is sort of saying everybodys close to their center。

 So now we're going have a step which says points in different clusters are far apart。O， which again。

 is something we we're basically getting at on Wednesday in a different model。

So suppose x is in C star I。And why isn't C star J？With I not equal to J。

The claim is that they're far apart。 How far apart。More than double。

The distance of either of these points to its own center。 Okay， so sort of like Wednesday。

 we're we're kind of like normalizing distances。 So one question with the distance is like。

 what's close and what's far， But is 10 coasts or is 10 far。 All depends。

 What do the other numbers look like。 So we're kind of normalizing by， you know。

Distances between points and their centers。 So relative to。The distance between x and its center。Or。

If you like the distance between y and its center， the distance between X and y is way bigger than that。

 Okay， it's at least double the distances between out of these two points in their respective centers。

So that's the claim for step two。Okay， why is it true？ち。Alright。

 so we' look at the following picture。So remember， x is an ice cluster。Why isn't Jay's cluster？

Allright， so what do we know， What do we just inherit from step 1。Well。

 step one says you're far from a center that's not your own。Okay。So between x and CJ。

That's going to be at least three times the distance between x and C I。Right， that's by step one。

Also by step 1， the distance between Y and C I is going to be at least three times the distance。

Of Y and CJ。So that's just from step one。Re for all， I not equal to j。B。I'm not equal to J。😀呵哈哈。😊，对对。

Okay， so。Now， we also have the triangle equality， which says that if the straight path between C I and C。

 Y is big， then so is any twoha path that starts at C I and ends at Y。 Okay。

 and similarly for X and C， J。So what is that bias？So by step one in the triangle inequality。We have。

Right， so if you go from Y to C via X， that's lower bounded by the distance straight from y to C I。

 which is at least triple the distance between y in its center， C J。Okay。Similarly。

If we go from x to C， J via Y， that's lower bounded by the straight line distance between x and C， J。

 which by step 1 is at least triple the distance between x in its own center C I。

So that's just that picture on the right， plus triality。Okay， and now we're done。Okay。So assume。

Those two cases are're symmetric， so I'm just going to do one of them。So assume， for example。

That this is bigger than that。Okay， the x is closer to its center。Then why its center。O。Thanks as。

You're right。 You're right。 Suppose the distance is bigger between X and C I。

 between X at center and line of center。Then。Let's look at2。

So we're remember we're trying we're trying to lower bound the distance between X and Y。

 X and Y are in different clusters。 We're trying to stay the far apart。 Here are X， Y distances。

 We're trying to get a lower bound。 We have a lower bound。 That's good。 What do we want to do。

 We want to subtract off this term。 Okay so we have triple the distance between x and C I minus the distance between y and C J。

But the difference between YNCJ is smaller。So it's three times something minus something which is less than one time something。

 So we're left with two times that thing， okay。So you get D of X， Y。

 So this is from 2 with the red assumption。I's at least two Dxci。Okay。So， that's this part。Oh。

 but then actually， DX CI was bigger than DY CJ。So I guess we're gonna to put other one， too。

 it's bigger than that。 That's bigger than that， so're done。Tell you know。

 whatever this I'm trying a quality maneuvering in there。 You know。

 I don't expect you to remember the details。 But， you know， what the statement says is nice， right。

Different clusters is you're far away。Okay， so step three。Third and final step， happy to say。Okay。

 so we are going to use this property， so。You are we， I forget。 We already used it。

 Maybe that was good enough。Alright， so we've got。Every point is close to their own center。

Pairs of points in different centers are far apart。 So once again。

 we have derived that optt has to be these tightly knit well separated clusters。 Now。

 let's seal the deal。Let me remind you， you probably forgot about this。

 This is the condition we're shooting for。 We had this part of the lecture where we said。

 when does single in plus plus succeed， we did a little bit of work。 And the payoff was。

 we got this sufficient condition。Okay，This sufficient condition says， oh。

 what we really want to be true about this metric space is if you have an optimal clustering and you have a strict subset of that optimal cluster。

 the nearest point should be something else inside the cluster， not outside。

So now let's verify that fact about three stable instances。So're going prove that this is true。

 Prove that this condition holds。Using what we have in step one and step two。All right。So， step 3。

To verify this condition too。Pick your favorite optimal cluster， C starI。

 pick your favorite strict subset。Okay。First thing to note。

Suppose the optimal center of this optimal cluster。Is not an egg。好看。Then a claim were done by。Step 2。

Why。The claim is C。 right So what's I should give you a picture here。

What we're talking about right now is we have C star I。And we have our subset A。And at the moment。

 we're thinking about the case where the center。Is outside of it。Okay。Good。it step 2， yes， yes。

 So what did we just prove in step 2， We prove that anything outside of C star I。

Is far away from anything in in C star。 sorry， Any points from C star I and C star J are far apart。

 What is far apart mean， and least double the distance from each of the distances to their respective centers。

 right， well。Everybody here is close to their respective center。 Everybody outside is far apart。

So the point is， if， if the center of the cluster is outside of a， I mean。

 that's already a super nearby point to stuff in A， Okay， because everything's close to the center。

 So that's the easy case， okay。So if C's outside or A。

 that's your certificate that it's closer than anything outside of C Star O。So C close enough done。

All right， so now from henceforth。We'll assume。That C I is an A。 All right。

 And this case is a little tricky。All right， so for contradiction。

But we're ultimately going to contradict as step 1。

 So step 1 says that everybody's three times as far at least from other centers as they are from their own。

 Okay， so thatll be the contradiction。So， for contradiction。We're assuming two is false。

 this is false。So suppose。Cllosest point。To a。Of everybody else。Is why。

Which is in some other C starje。好看。So。We have C star I。We have C。We have a。We have C star J。嗯。

And then suppose x is the closest point to y。Anywhere in A。Suppposed closest。To y and a is x。

 So we have is we have x right here。We've got this allegedly quite close Y over here。Okay。

So we're assuming close， basically。That's how we're starting the contradiction。Now， let' Z。

And I promise this is the last one we need。With Z。Be。

 what we were sort of hoping would be closer to A。 Remember what the condition says。

 The condition says， look at the nearest neighbor to A。 We want it to be in the cluster C star I。

 A' is a strict subset。 So something's not an A yet。 We want that to be the closest。 right。

 we're assuming it's not。 But let's Z be some candidate。So any point of。C star I and minus a。Okay。

 so Z is going to be like， you know， maybe it's all the way over here or something。

So that's the setup。So now we've got all the notation。

 and we just got to kind of get the triangularal， right。Intuitively， here's where we're going。 Okay。

 so this is some distinct cluster。It has some center CJ。Now here's what step one tells us， okay。

Here's what step 1 tells us about every point in particular point Z。

 Step 1 was this well separated condition。 You're way closer to your own center in the optimal than anybody any other center at all。

 In particular， Z， We know this。 Z is much closer to C I。Then to CJ。On the other hand。

 under our current assumptions， we can construct a quite short path between Z and CJ。Why， well。

 we can start。 We can go from Z to C I。 That's close because it's just a point to its center。

 We can go from C to X。 Again， that's between a point in its center。 So that's small。 By assumption。

 x and y are pretty close to each other。 So that's not too big。 But then from Y to C J。

 that's also just from a point to its center。 So we have these four hops。

 all of which we have some control on the upper bound side of Y they're not too big。

 But the other hand， how can to then be that Z and CJ are super far apart。Okay。I mean。

 that is really the proof。 I mean， to see where the three comes from。

 we'll have to actually do the computation。 But conceptually， that's exactly the proof， okay。

So the contradiction is what gives us an upper bound control in the distance between x and Y。

 which is the missing link on this4h path。Good。ほ。So we don't need this condition anymore。 Remember。

 this is what we took the contradiction of。 So the contrapositive of this。

The negation of this shows up on the right board。So all we need to do is exhibit the contradiction。

Which is getting the trigon equalities just so。Okay， so like I said。The contradiction is going to be。

 you know。Z and CJ should be far apart by step 1。 Okay， so to contradict that。

 we're going to take the distance between Z and CJ。

And then we're to construct this four hop path on the right hand side， okay。So we go from Z to C。

Plus C to x。Plus， x to y。Plus y to CJ。Okay， showing inequality， that's the number bound，40 half。Now。

 what's our control over these things。Here's what we're going to do。So。あ。Right。

 so that that I want to leave。 This is going to be for the contradiction。

And these I want to relate in this。 Okay， so we've got these four different terms。

 Let's take these three and collapse them into one。How do we do that， What did step 2 say。

 Step 2 said that the distance between two points in different clusters， such as X and y is big。

 big relative to what， big relative to the distances between x and Y and their own clusters。

 factor two difference， actually。 So here's the distance between x in its own cluster。

 distance between y in its own cluster。 This is twice as big as either of those。 Okay。

 Or if you like each of these is the most half of that。Okay的。So most half。D X， Y。Atmost half。D， Xy。看。

So we can collapse all this into it most too。D， X， Y， okay， this is using step 2。Okay。Now。

 this is sort of a clever bit。 And we're basically done now。 This is the last clever bit。

 So how do we relate the distance between Z。And it's center to the distance between X and Y。

 These don't seem to have that much to do with each other。 Here is where we use the fact that。

You know the definition of why， what is why， y is the closest point to a。

We haven't used that property of w。HowRemember how we do。 We started by contradiction。

 We have this set， what's the nearest neighbor， Call it why。 If it's in C star I， we're done。

 if why is outside of C Star I're in trouble， okay。So it's the closest point to A。 Well。

 here's another point outside of A。Z。We could have chosen Z。 We would have been very happy， actually。

 had we chosen Z because that's inside C Star。 I wish we want。 We chose why instead， why， evidently。

😊，So this is by our initial contradiction。It must have been that the distance between x and y。

Is at most the shortest distance between Z and its nearest neighbor in A。In particular， remember。

 this is the case where the center is an A。So one choice for Z's nearest neighbor in A is the center C。

 I。 Okay， So C I and Z summarizing C， I and Z is a particular choice of a point in A and a point outside of a。

X and y， by definition， are amongst all points in A and outside of A。

 the pair that minimizes the distance。So DxY is at most EZ CI。Okay。So that means。

We can take this double distance， X and Y。Upper bound this by the distance， right， was this say。

 upper bound this by the distance between Z and C。 So that gives us in the right hand side。Triple。

Distance。Between D and C。This is exactly what step  one said could not happen。

 You could not have a second best center。Within a factor three of a second best Senate。Okay。

See you Wednesday。