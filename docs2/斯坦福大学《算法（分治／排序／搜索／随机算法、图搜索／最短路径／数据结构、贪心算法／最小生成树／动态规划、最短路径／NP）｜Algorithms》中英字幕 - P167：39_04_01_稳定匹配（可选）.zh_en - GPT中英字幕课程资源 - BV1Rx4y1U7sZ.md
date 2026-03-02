# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P167：39_04_01_稳定匹配（可选）.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In the design and analysis of algorithms， both this course and its predecessor。

 we've covered a lots of famous algorithms。 We've covered a lot of fundamental data structures。

 We've covered lots of killer applications。

![](img/92fabc320f0be6a181ab20fa13affba9_1.png)

And despite the fact that I've tried to use our time together in the optimal way。

 giving you the most bang for the buck， there are fundamental topics we have not had a chance to cover。

In these final few videos， I want to talk a little bit about things we didn't talk about。

I have a few goals。 The first goal is to give you a little bit of literacy in a few more techniques。

 so at least you've heard of things like bipartite matching and the maximum flow problem。

 and you're aware that there are good algorithms for those sorts of problems。Secondly。

 I want to get you excited to do a little bit more study。

 either through further courses or on your own， and indeed。

 generally the topics that I'll mention in these final few videos are covered in your more comprehensive textbooks on algorithms。

Finally， I hope to convey something I've mentioned in passing in the past。

 which is that algorithms is not an osified field。 Rather， it's a vibrant area of research。

 There are still lots of things about fundamental problems and models that we don't yet understand。

Let's get the ball rolling with a very fun， classical problem known as stable matching。

We're going to think of stable matching as a graph problem and there's going to be two sets of nodes。

 two sets of vertices， capital U and capital V， for historical reasons we will call these sets the men and the women respectively。

A non essential assumption that well make for simplicity is that these two sets of nodes have equal cardinality。

 called that common size in。So for example， maybe n equals 3。

 and we can call the first set of nodes A， B， and C， and the second set of nodes， D， E and F。Now。

 what's really important about the stable matching problem is that every node has preferences。

 There are things that it wants more than others。 Specifically。

 each node in U has a ranked list of the nodes in V。

 Each node in V has a ranked list of the nodes in U。So in this example， maybe A。

 B and C are all on the same page。 They all agree that D is really the best node， It's better than E。

 but E is definitely better than F。That is， maybe every single node on the left hand side has the ranked list D。

 followed by E， followed by F。By contrast， maybe there is heterogeneous preferences amongst vertices in capital V。

 Maybe D thinks A is better than B is better than C。While E prefers B to C to A。

 and finally F prefers C to A to B。So what might these nodes and these ranked lists represent Well。

 imagine for example， that one set is colleges and the other set is applicants。

 recent high school graduates， each college has a ranking of the applicants based on things like test scores grades and the fit that student is for the college and each student similarly has a ranking over the colleges of which ones it prefers to go to over others as another example you might think about medical residents that is people who just finish medical school looking for a residency and the other side being hospitals again。

 hospitals are going to have a preference over which recent graduates they accept as residents。

 residents， potential residents of course have preferences over which hospital they get assigned to。

So given this data， two sets of nodes and these ranked lists were interested in computing a stable matching。

So what's a stable matching， Well， first of all， it better be a perfect matching。

 and a perfect matching means that each node on the left。

 each node of U is matched to exactly one node of B and vice versa。

In addition to being a perfect matching， it should also be stable in the sense that there should be no blocking pair。

 What that means is that if you look at any pair of nodes， little U from capital U。

 little V from capital V。 If little U and little V are not matched。

 there're better be a good reason for them not being matched specifically little U better strictly prefer who it is matched to。

 Call that V prime to this alternative V， Or if that's not the case。

 it better be that little V strictly prefers the node。

 it's matched to call it U prime compared to the alternative little U。

So what's the motivation for this definition， Well。

 think about any perfect matching that fails this stability property。

 You're really asking for trouble for that kind of matching。 specifically， U with its wandering eye。

 will spy V， and it prefers V over the node V prime to which it was assigned。 Similarlyly。

 V is going to return that gaze V prefers U by assumption that the stability property fails over the node U prime to which it was match。

 So U and V you're going to have an incentive to essentially elope and disrupt this whole assignment。

Imagine for example， that U is a student and V is a college and you have a matching that fails a stability property。

 then this pair， this student in this college has an incentive to do a sort of backroom deal after the fact you might want to withdraw its commitment from its assigned college V prime to try to get into V instead and Vta college actually wants to sort of withdraw its offer from its student U prime to give it to you instead so that's an unstable matching。

 but as long as there's no blocking pair of this form and for every pair which is not matched together there's a good reason for it。

 then we deem it a stable matching。Let me tell you about an extremely elegant and justly famous algorithm for computing a stable matching。

 The Gail Shapley proposal algorithm。 Lloyd Shapley was one of the recipients of the 2012 Nobel Prize in economics。

 in large part for this algorithm。 had David Gail still been alive。

 He surely would have been a co recipient of that Nobel Prize as well。😊。

Let me explain the algorithm in an example。 Then I'll give you the general pseudocode。

 We start with the empty matching with nobody matched with anybody else。

 And as long as there is some man， some note on the left hand side。

 which isn't matched to some woman。 We pick an arbitrary， unattached man。

 And we let her propose to a woman of its choice。 So we might start， for example， with the man C。 C。

 says， well， my favorite woman is D。 So let me start by proposing to the woman D。Now。

 D isn't necessarily very impressed with C。 notice C is last in D's preference list。

 but with a lack of other proposals at the moment， the node D tentatively accepts this proposal from C。

Now you proceed to the next iteration of the while loop， we look for a man that is unattached。

 so maybe we pick B。 B now gets its shot at proposing to its favorite woman， in this case。

 it is also D。So now the node D has a bit of leverage。

 It has two competing offers from the nodes B and C， and of course。

 it retains the offer from the preferred suitor。 in this case， D prefers B to C。

 So the edge between C and D gets delete it and replaced with the edge between B and D。

So now both of them and A and C are unattached， perhaps in the next iteration we let the node A gets its shot。

 it again proposes to the node D and again D prefers A to B。

 so the edge between A and D is going to replace the edge between B and D。

So we now again have two unattached men B and C， let's say we pick C next。

 so C gets to propose to whatever woman it wants， and D is its favorite。

 but it's already been rejected by D and in the algorithm a man will never repproposed to a woman who has previously rejected him so next on C's list is the woman E and so E has not had any other offers so E tentatively accepts the proposal from C。

But now， once B gets a chance， B will also propose next to E。 That's B's next favorite。

 and it's already been rejected by D， and E prefers。B to C。

 so we will replace the edge between C and E with the edge between B and E。And so now finally。

 the man C is the only one that remains unattached and it has no choice but propose to its final option。

 The node F F actually happily accepts that because C is on the top of F's list and that leaves us with the matching that matches A with D B with E and C with F。

 This is clearly a perfect matching， I'll let you check that it's also a stable matching。

Having traced through this example， I hope the pseudocode for the general algorithm will not surprise you。

So we have a meanwhile loop， and in each iteration。

 we pick some man who is not yet engaged to any woman。 Call that man you。

You then proposes to his favorite woman， the top ranked woman。

 with the constraint that he will not propose a second time to any woman whos already rejected him。

Each woman then behaves in the obvious way， which is to keep track of all of the suitors。

 all of the men that have proposed to her， and to retain as a tentative engagement。

 only the proposal from their favorite that is highest ranked suitor。

Notice this algorithm maintains the invariance that the current set of engagements is a matching。

 not necessarily a perfect matching， but a matching。 That is at any given time。

 a man is engaged tentatively to at most one woman。

 and every woman is tentatively engaged to at most one man。

The Gae Shapley theorem states that not only does this algorithm terminate quickly。

 not only does it terminate quickly with a perfect matching， but in fact， it terminates quickly。

 namely in a quadratic number of iterations at most with a stable matching。In particular。

 this theorem， this algorithm provides a constructive proof that a stable matching always exists。

 no matter what the preference lists of the nodes are， a highly non obvious fact。

The proof of the Gail Shapley theorem is as elegant as the algorithm。 Let me show it to you now。

So first of all， why does the algorithm converge in a quadratic number of iterations， Well。

 no man proposes to a woman twice。 therefore， each man makes at most end proposals。

 there are only n men， so that's the most n squared proposals overall。Secondly。

 when the Gale Shay algorithm terminates， it does so with a perfect matching。 Indeed。

 it's a stable matching， but let's just for the moment， prove that it's a perfect matching。To this。

 to see this， let's suppose the contrary。 Let's suppose that when it halts。

 it does not halt with a perfect matching。 That means in particular。

 some man is assigned to no woman。 How could that have happened， Well。

 it must have been that the man fell off the end of his ranked list。

 He proposed to every single one of the end women and was rejected by all of them。

So how could this have happened Well， notice that for a man to be rejected by a woman。

 it must be that the woman has some other offer from some other man that she likes better。 That is。

 rejections happen only by a woman who was engaged to somebody else。

 So by virtue of this man being rejected by all and women。

 all and women got engaged at some point in the algorithm。Moreover， if you inspect the algorithm。

 you'll notice that once a woman is engaged to somebody， she will remain engaged forevermore。

 The only thing that changes is the woman is engaged to men that she likes better and better as the algorithm proceeds。

 So a man rejected by everybody implies that all women get engaged at some point in the algorithm。

 which means that they're all engaged at the end of the algorithm。

 but there's an equal number of men and women。 So there's no way all women are engaged at the end and some man is not engaged。

 If all women are engaged， all men must be engaged as well。



![](img/92fabc320f0be6a181ab20fa13affba9_3.png)

Finally， why is the perfect matching computed by the Gail Shapleley Pro algorithm， not just perfect。

 but more generally stable？To see why this is true， let's prove that there is no blocking pair。

 That is， let's consider an arbitrary unmatched man you and woman V。Now。

 either the man you proposed to the woman V at some point in the proposal algorithm or he didn't。

 let's treat those two cases separately。So let's first suppose that at no point in the algorithm。

 did the man you propose to the woman V。 So what's the behavior of a man in the proposal algorithm。

 Well， a man simply proposes to the woman on his list one at a time， in turn as necessary。

 And the man， the woman to whom a man winds up matched at the end of the algorithm is the last woman to whom he proposed。

 So if the man you never got around to proposing to the woman V。

 that just means he never search that far down in his preference list。

 And he wound up at the conclusion of the algorithm， matched with the woman he prefers to the woman。

And so that's sufficient set to claim that UV is not a blocking pair。Suppose on the other hand。

 you did propose to the woman V at some point in the algorithm。 Why did they not wind up matched。

 Well， it must be because the woman V got a preferred offer。

 an offer from some man she prefers to the man you。 Now。

 something we mentioned earlier is that over the course of the algorithm。

 a woman just winds up being engaged to men that she prefers more and more。

 So if at any point she winds up engaged to a man she prefers to you than at the end of the algorithm。

 she will be engaged， matched with a man that she prefers to you。 And again。

 that implies that U V is not a blocking pair since U V was arbitrary， this is a stable matching。

 That completes the proof of the Gail Shapley theorem。

