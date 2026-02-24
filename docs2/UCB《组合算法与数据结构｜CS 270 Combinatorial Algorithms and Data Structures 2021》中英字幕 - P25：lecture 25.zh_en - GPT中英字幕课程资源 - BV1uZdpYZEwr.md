# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P25：lecture 25.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/2d451cf3f6ffc2b807fbc7ce5efa52e3_0.png)

Today。Today is I guess officially the final lecture we have we promised ourselves that we missed a lecture earlier we'll do one more so we'll do one more lecture on Monday and that'll be I guess the truly final lecture but。

Let's begin okay。So here's what we'll talk about today， we'll talk about。

 I guess we'll see a couple of examples from this area of algorithm slash complexity called property testing。

So I guess this is lectured。20s。5。Okay， so what is property testing？

So property testing is the is a following idea well you have some object， you know。

 think of it as let's say a string。我的 function。On a list。And you want to， you know。

 usually these things are of length then， right？Of London to。Okay。

 there are an end string or something like that， and you want to know if this object satisfies some property。

So， you want to test。The goal is。Best。If the object satisfies the property。So for example。

 if it's a list。嗯。Some property P okay， and so if it's a list of elements。

 you want to know if it's sorted。So let's say this is a list and for example。

 it could be whether the list is sorted right or whether it could be you have a graph and you want to know if it is bipartid。

Okay， and of course you can all me the algorithms to do all of these things。

 but what we're interested in now is to sort of do this test much more quickly than it would take to read the entire input we want to do a test。

By randomly reading only a little bit of input， like we want to query or we want a run time。

Either the number of queries and the。Like total， like total run time。We want it to be。

Much smaller than N。Right， like we want it to be order log n。

So think of it as a randomized algorithm that tests a few locations and finds out if what the answer is and of course。

 when you have such a randomized algorithm， you will not have。

You'd not have the answer with certainty， most cases。

 it would be something like you do a test and the test accepts with probability 0。

99 if the property is satisfied and if the property is not satisfied。

 then you detect a violation with probability 0。99。あ。So。

So I guess the guarantee that you want is something like this。

 the guarantee that you want is if object let。Satisfies P。If it satisfies the property P。

 then you want test accepts with property 。99。LikeVery high property。Or even let's say probability1。

 okay， depends on the test。On你在太里。If the object violates the property。

 you want to be able to catch the violation。But this is where things get a little subtle。

Because well let's do an example and if you are testing if a list is sorted， okay。

 you have a list and you want to know if it is sorted。Okay here's an example。

 we will see an algorithm for this。So。The input is a list of numbers。Okay。

 these are numbers in regular integers。And you want to test like to test。Is it sorted？

And you don't even want the key is that you want to do it by in time， which is sublinear in hand。

 meaning you don't even want to read the entire input。

 you want to sort of test by reading only a part of the input， like randomly checking somewhere。Okay。

And the key is that if it is sorted， you want to accept it probability 0。99。If it is not sorted。

 you want to reject。But since you're reading only a part of the input。

It's highly unlikely that you'll be able to detect a violation if it's not sorted。So for example。嗯。

Like if the list was sorted， except for let's say， some pair of elements somewhere in this list。

 there's just one pair of elements that you swap around。Okay， so it's basically sorted。

Maybe some pair in the middle， like I don't know which pair。

 but AI and AI plus one are not sorted they're flipped。Okay。😊，Suppose this you had a list like this。

 then if you query only a small number of locations， it's unlikely that you'll catch this violation。

So it's too much to expect that you'll read only， let's say login numbers here and actually conclude that the list is sorted or are not sorted。

So instead， what will。Look for is。That if the list is far from sorted。Then we should reject。

So we say the guarantees if object satisfies P， then the tester accepts at probability 0。99。

With the object。Violets are。So let me say object is far from satisfying P。

Intuly we like and well define what far is， but。Intuitly think of it as you knows。

Like you it's you know intuitivetu， you have a notion of what is this far from being sorted， right？

If it is far from being sorted， then you must violate test violates。With Pro 。99。

The test rejects probably 。99。As you said， not Lex rejects， just rejects at 4 0。9。Okay， so。

That's what property testing is about so now you can ask this question about basically any you know can could be graphs or functions or strings or lists or whatever it is and you can and it could be any property that you can calculate in let's say in polynmal time or not and you can ask this question can you。

Can you do it in this way？Let are you。You sort of are quickly able to test it。

And you can imagine that this is extremely useful thing to have， for example。

 let's say you have a list of numbers or something and these numbers are dynamically maintained you know somebody you know there's some functions that keep inserting them。

 deleting them whatever。And then every once's inna， you want to go and sort the list。

So that you want to maintain a sorted list。And before you go and run the sorting algorithm。

 you want to know， is it nearly sorted or is it very far from sorted？

And you don't want this algorithm that tests whether it's nearly sorted or far from sorted to take linear time that would be pointless you as well sort in that case。

 you want to something a quick test that tests whether it's sorted or not and。

That's what like you know that's one application so basically before you run a more elaborate algorithm is a way to test that here。

Input either it satisfies the property or not。And sometimes like this also inspires things where where n is too large。

 but if n is a I guess the keyword is big data， if n is really big。

 then you know it makes sense that you want algorithms to run in sub linear your time。

And subline your space also about subline your time。And this is。

That's that's the motivation of this property testing area。

And there's surprisingly many things that you can actually。Do。Even in this very restricted model。

Okay。Okay， and I guess we're always going to be invariably or all algorithms will be randomized。

I mean， if it's a deterministic property testing algorithm， it's sort of it's mostly useless。O。

All right， so let's look at this example that we started with and see if we can design a property testing algorithm here。

So again， the question is， you have a list of numbers， it's sortedness。And you want to know。

 is this list sorted or close to sorted？Now I need to define what close to sorted is right and so what is close to sorted。

 so here's the most natural definition that well use。So。嗯。Okay， firstly， in our definition。

An increasing subequence is what what you think it is， right，'s it' a。Increasing subsequentence。

If I give you a list of numbers A1 through A an increasing subs some sub。Sequence。

 I guess sublists are like AI 1， AI 2， AI 3， some AI。嗯。I guess T like some subli sub from this。

Such that it's increasing。Okay， so in particular， if you had a sorted list。

 the entire sequence would be increasing。 So that's right And what would you want to know like you would say that a sequence is like。

Let's say distance d away from being sorted if it has an increasing subence of length n minus D。来。So。

 here's a definition。A sequence。A went through A。Is。嗯。你 guess啊。呃L。Away from sorted。

If the largest increasing sub is n minus l。Longest increasing sub is n minus l。我们。不是。

In longest injury subequence is of length and minus。Okay， that's the natural definition。All right。

 so now you want to know if you' given a sequence and you want to know if it's mostly sorted。

 meaning it's longest increasing subequence is roughly n minus like 0。99 n like n minus epsilon n。

 okay that's your goal。Allright， so what is the。Okay。

 what was in the most natural test you would try， the most natural test？啊。You your try is。嗯。

Like one natural test you try is okay， you know。Big。Random eye。And， and check if。

AI is smaller than AI plus one。Okay， so this is like a random pair of consecutive numbers。

 you check if the eye is smaller than a plus one this actually is super easy to。

See that it doesn't work like。I'm going to draw the sequence。😔。

So let's say this is a graph of the sequence， I guess， so here's a graph of the sequence。

So it's like。So if the sequence goes up one， through and over two。

And then it suddenly drops one through and over two。Okay， so if I look at consecutive pairs here。

 most consecutive pairs of elements are in increasing order。Except for one pair。

 just a single pair is off。Right。It's this this sequence， I guess。

 I mean the way I've written this is one，2，3， n over two and then again one，2， three， and over2。

 that's the sequence。The sequence is very far from sorted because if you had to pick an increasing sequence。

 the maximum length you can get is N over2。It's only at most 50% sorted in art definition。

 but this test will catch it with probability one over n because。Only if you test this one。

 So with the pro， so the。So the sequences。In over too far from。Sortted。Very far from sorted， but。

Test reject priority one over。I it mostly accepts this。

So that's phase I guess1 over n or about1 over or the 1 over。Okay， so that's bad all right。

 so then what do you try next？The next thing you try is you pick two random elements in the list and you see VI is smaller than the A+1。

Okay， that's the next thing youll try。So pick Ija at random。And you ask if AI is smaller than， well。

 Ij is at random with the I less than J。And then you ask if FiA is smaller than need。Okay， so。

This also fails， but it's more subtle to see how it fails。So what you have to do here is。

Let look at the following sequence。I'm going to draw it。So this is one through n， right。

 So divide it into groups of root n， one through root n2 root n。And and。

I think if you look at the following sequence。Ex questions。Sorry， yeah。

 when you talk about the longest increasing subsequentence。D调。Yeah。

The omen subsequent don't have to be contiguous， right？right， the sequence need not be coniguous。

 yeah。Yeah it's the it's sort of the reasonable notion where you say， okay。

 have a sorted list and let's say someone came and moved around epsilon and elements。

Anywhere mean however you want however you want you can move around epsilon and elements then you you still have the one minus epsilon n elements which are untouched they'll form the increasing sequence and the remaining things can move around so that's the reason why you sort of look at that definition of how close you are。

Okay， thanks。And so if you look at this sequence， right， this one actually。

It takes a little bit to see that it works， but basically in some sense what's happening is you have these decreasing sequences like like root n to one then two root end to root n and your three root n to two root n and so on。

 you have these decreasing sequences。But overall， these sequences are increasing。

So if you pick two random elements like you know one guy will land here another guy will land you know it's somewhere far away and it'll look like it's increasing but locally it's always decreasing so it's quite far from sorted but when can also check this longest increasing length of the longest increasing sub here it's not that high so it's root end I think so that's right。

This fails。 Okay， so that's good。 So have two examples。 So now let's see the actual algorithm。

 It's quite elegant and simple。 But okay， here's the actual algorithm。 the algorithm is。O， suggest。

We'll repeat some tests like one over epsilon times for。Like me say， repeat repeat。

1 over epsilon times。This is standard you， you only boost the success of some test。 you repeat it。

 you repeatedly test it one or so times。 Okay， what do you do each time you do the following。

 you pick some I。At random。And run。Binary search to find AI。switch。嗯。On like to find AI。I mean。

 yeah is a number and。You just run bio research to find AI。Okay of course we don't have to find AI。

 you know AI is in the right locations， it's not the goal is not to find AI。

 but the goal is that you run the binary search algorithm to find AI and in the binary search algorithm you will actually do some comparisons right you know you will be you checking whether to go left or right or so on and ifs if on one of those comparisons you see an unsorted thing then you reject。

So you find a violation。Thank you， you do about login comparisons。You find a violation。

Or reject if you find a violation in one of the login comparisons。Violation during biore， right？

So that's that little。Kids just act it's really simple。Okay。

 so and of the number of queries it does is like the runtime and the number of queries is order log n by Epsilon。

Because you you do one hour Epsilon binary research and search algorithms and each binary research takes login login reads login numbers essentially okay so why does this work that's a very super nice proof。

So what do I need to prove？I need to prove that。嗯。嗯嗯。If the algorithm。Accept。With probability 。99。

Then。The list is。Epsilon close to sorted， right？Like when I say Epsilon closed， I mean actually。

 I should say Epsilon n close to sortet。Not epsilon， close epsilon n close to sort。

 There are epsilon n elements that are moved around。Okay how do we prove this Okay。

 so here's a very nice definition， so you say let's call it a good element。AI is a good element。

If buying research for AI has no violations。Even you do binary research for AI。

 no violations are detected。ok。So there are some elements that are good and some elements that are bad。

 as in that's like that's the definition。 Okay， so okay， so now。All right so。Firstly。

 how many good elements are there？Well。I guess the let me say， claim one。

If algorithm accepts with probability D。99。Then this implies that the number of good elements。

Is at least one minus epsilon N。那 guess yeah。I mean， I might be missing some constants here。

 but let's say all of one over epsilon times okay so。To claim one if I with the4。

9 good element is one minus n well， this is really。嗯。Easy， well， why why so because you know。

 when you pick an element at random and to do binary search， right if you pick a bad element。

 then you will reject immediately。Because if I pick a bad element。

 then when I do the binary research I will find some violation during the binary research and I would reject。

This is by definition。In fact， a good element is one for which binary research will not find a violation and bad element is one for which biasers will find a violation。

So， you know。This algorithm picks one over epsilon elements and if you。

If it picks a bad element in any iteration， it will reject。So the， so like。It's just that you know。

If there are。Like suppose the number of good elements。Take the number of good。Elements。

Is smaller than one minus epsilon n then in each situation with probability 1 minus epsilon。A we。

Like。With probably at least epsilon will reject in the nutrition， right so with probably。So。

So then you can ask a probability that test succeeds。

Is basically in each iteration you to pick a good element。

 so that's at most one test I shouldn say test succeeds， accepts test accepts。

Test accepts is that at almost one minus epsilon to the power one over epsilon。Okay。

 because you did like about one of epsilon iterations。Let's say， I mean it's a constant right。

 so let me say you did10 over epsilon its just for。Okay。

 then you get1 minus epsilon to the power 100 over epsilon。So that's smaller than e to the minus 100。

About e to the minus100， so it's really low probability that you like at。Okay。Okay， so。

And then the next very nice claim is that， so okay。

 now you know that if the algorithm accepts there are a lot of good elements。

The next good thing is that all the good elements form an increasing sub。Okay， so before I say what。

 how to prove this claim， let me just。More closely say what we mean by finding a violation during biolere。

Okay， so what what happens in binary research Okay， so binary research you， you know you。

Right you started A over2。And either you go left or right。

 then maybe you know you you check a and over four and then you check make some element here a3 and over4 and something like that you you make queries each time well in particular reading numbers right you're reading a and over four you're reading all these numbers a and over2 a and over4 a 3 and over。

Eight and things like that， you're reading all these numbers。

And you expect these numbers to be in a certain order。

 you expect that A and over4 should be smaller than A and over2。

And when you read a3 and over8 this third query， you want it to be larger than A and over4 and so as you read these numbers you have some expectation of the order of these numbers and a violation is when that one of those expectations broken。

So it's just really you're reading login numbers and you expect them to be in a certain order。

LikeIn terms of which is great and which is smaller and if one of the expect like if something unexpected happens。

 then like something that doesn't look like a sortered list， that's a violation。Okay。So that's okay。

 that's easy， right， So all right So why do good elements form a increase in subsequent， that's okay。

 so this is quite nice。So okay let's pick any two good elements， so let's say AI and AJ。

Are good elements。Okay， so when when you do biore for AI。

 you will find AI without any violation and singlely when you do biore for AJ。

 you'll find AJ without noticing any violation okay so that means。So。

 so both the binary searches started N over2， right， If you look at the execution of binary search。

 both of them started N over2 and they， you know， they sort of。

You could imagine them as though they're following some path in a binary tree， right？So。

You follow some part and reach AI。And then you follow different path。And reach AJ。Okay。

 so that's just what it is。 So these two parts and now。There is， look at the。嗯。

Lowest common ancestor of these two parts。2。Let。エケビデ。Le common ancestor of Ya in AJ。

So the parts are the same up to AK and at AK they split， you go left for AI and right for AJ。ok。

So then what's happening at AK and in this picture AK is just the top element。Okay， but otherwise。

 it's some other okay what's happening at A have this path right and you take left for AI and right for Aging。

Okay， and note that every number you see in both the binary researcherses are actually as you expect the numbers to be。

In particular。I in binary research of AI， you didn't find any violation， right everything was fine。

 so which means that AI is smaller than nakedK。Because。At AK you took a left and you went to AI。

 you reached AI， so you expect AI to be smaller than NikA and it is smaller than NikK。Okay。

 similarly。You went right to go to AJ。So， you know。AK is smaller than easy。

Because you went right and everything was as you expected。So therefore。

 if AI is smaller than AK and AK is smaller than majorji， you conclude that AI is smaller than A。

So we concluded that if you give me any。Per of good elements。

If I is smaller than J AI is smaller than agent， so the good elements form an increasing sub and we saw that most of the elements are good elements and therefore you're done。

Okay， so that's the algorithm。So the algorithm runs in log in over epsilon queries and you get this。

Okay， so so that's nice。 Okay， so。All right， so we have let's see。Two choices now。Okay。

 let let's let okay， let me do the this one。 Okay， so let's do。

Not a sublineient time algorithm that is。Kind of close to property testing， but really it's also。

Easily stated as an an approximation algorithm or okay， so here's the question。 So you are given a。

So it's the maximum matchingsion。Okay， here's the。Questions， input is a graph。

And let's say the graph is degree D， as in the maximum degree is at most D。Dgree in G is at most D。

Okay， and your goal。I。Estimate the size of the maximal matching。ok 啊。

This is a little bit subtle the way have say say stated it because what is a maximal matching， Okay。

 let me just say what a maximal matching is a maximal matching is。嗯。It is a subset of edges。

Such that you can't add any more edges to that matching。Subservs。Such that M is matching。

And you can't add any more register to that matching。for all二。In E minus M。

M union E is not a matching。Its the out like if you had to solve matching by a greedy algorithm you know this is what you get you keep adding edges until you reach a point where you can't okay so clearly this is not a unique quantity right depending on the choices you make you can get different maximal matchings。

So maximal matching is not unique， in fact， the size of the maximal matching is not unique。Right。

 so this is。嗯。It's not the maximumum matching。 Maximum matching is that。

Matching with the maximum number of edges， this is a maximal matching。Okay。So size is not unique。

So in some sense， it's a little bit subtle to say what it means to estimate the size of a maximal matching because it's not a single number。

 let's just say estimate the size of a maximal matching。

 meaning the algorithm is supposed to output a number t。So， so the goal is。

You want the algorithm outputs T。He outputs are number t， there must exist some maximal matching。

 there exists some matching M。Maximum。Sos whose size is roughly t， so M is about T。

Like t plus or minus epsilon n。Okay， and why like you know， this is a little bit odd。

 but if you want to make it more cleaner， you could say， okay。

 instead of talking about maximum matching， I could have started this whole thing by saying， okay。

 you want to solve vertex cover。If you remember from 170。

 the way to solve vertex cover is you pick a maximal matching and you output both the endpoints it gives you a factor to approximation right and so I want I want you to give an algorithm that estimates the size of the vertex cover。

Up to factor2。But I want your algorithm to run in constant time。Right， that's what I want。

 So you can think of as a constant time。Algarton。That gives you two approximation for verortex cover。

Okay， it's the same problem。Okay， so that's the problem so it's a little bit surprising you can do it at all。

 but you can it's a very clever， nice algorithm here。Okay。

 so you want to you want to find a max maximal matching the size of a max matching。 Okay。

 so let's see what's。What's an algorithm for this so here's an algorithm if you didn't care about constant time like what would you do I would sort the edges meaning I would like pick a random let's say random permutation of the edges。

Pick all the ages， right， Pick a random。Do mutation。Of it。是。

So another way to say this is let's say you are sign for every HE and number。Every H in E。

 a number from1 to E。Which is basically the it's an ordering of the edges。 Okay。

 and this is the ordering in which you on your greedy algorithm。 What do you do， you， you know。

 for I equal to one through。Like coordinate your fee， you repeat repeatedly you just。You know。

If you can add the eyete to the matching， you add it， otherwise you throw it out。Add。The I edge so。

At height edge。In this permutation， like。I guess if I have the I， let's say it's EI to M。

If it's allowed。Eltro。thいだ。I mean， discarded， right， That's right。

 So you you it's like it's a bit like。Crystcals algorithm。

 but here we're picking random ordering of the per of the edges and we're adding them one by one to the matching and I that's that's the what what Okay so this is not this construct a matching for the whole graph and its。

It's a greedy algorithm， it constructs a maximal matching by definition because every time you didn't add an like every edge that you discard it was something you couldn't add so it constructs a maximal matching。

就。嗯。This al1 definitely constructs a maximal matching。But it's not constant time。And of course。

 it is not constant time because it is constructing the entire maximal matching。

Your goal was not to do that， your goal was to just estimate the size of the maximal matching。Okay。

 so in particular。You want to be able to。Given an edge， test if it's in this maximum matching or not。

Okay， if you can do that， then you can estimate the size of the maximum matching。Absolutely。So。

 here's。嗯。Here's your。Property testing out too。I guess what is it what does it do， you know。

 it it wants to estimate the size so it says。Pick some one over Epsilon random edges。

1 over Epsilon or one over epsilon squared random images。Okay， and。Test。

Or I shouldn't use the word test， maybe test has other meanings， right。嗯。嗯。

Pick one of represents square random images。And。You know。ok。Let's say these edges are e1 through E。

 where L is1 over epsilon squared。ok。What you do is you。Suppose you could check。If E I。Let me say。

 let me say， let me say， okay， estimate what fraction of EI。Are in the matching， so estimate。

How many of these even through E？Are in the maximal matching M。Okay。

And that's a way to estimate the size of any set right if you want to estimate the size of set you pick random elements and like okay。

 how many of them are in the set， how many of them not in the set and that gives you the size So if you estimate the size of this intersection you know like that gives you the fraction of elements that are in there and then that times。

I guess card of E。Sorry， I don't try to look too much in one step。

 so basically estimate the fraction of elements that are in the set。

Ages in this in the matching and you know。Like once I know the fraction。

 the total number of edges in the matching is also easy to estimate right it's just that times the total number of edges right output。

This number。Cognitive E times this number， Okay's just。Okay， so I mean。

 this is just wishful thinking right again， this algorithm is again wishful thinking because what I'm say saying here is something very obvious I'm saying。

If you can had a maximal matching， estimating its size is easy。

 you just have to pick random edge and check if it's in the matching or not。

 and that gives you the size， approximate size okay。But now in order to actually implement this。

 you need to be able to answer this question in constant time that you want to do this in constant time。

The thing that you need is an oracle or a you want to be able to do the following given E E。

Can you test if key is in this max matching M？M that is output。By the algorithm here， this al。Okay。

 of course you don't want to completely run the algorithm one right you know what the algorithm one is going to do it's going to sort the edges and do the greedy algorithm what we're asking is okay that's the algorithm all right it's going to produce a matching a okay that's all right we're not going to run it what you want to know is if I just give you in one edge and I won't tell you can you test if this edge will be belong to the matching or not and you want to do this in constant time。

About constant time， like expected constant time。Okay that's the question， really。嗯。这。

In constant time right so that's the key thing。Well， I shouldn't say constant time。

 it's constant time depending on D and Epson。Right didn maximum degree end epsilon。Okay。

 so how do we do this， So this is quite neat。Okay， so let's see。诶。All right。

 so let's look at this edge E。And we're asking。If this edge。Okay， firstly。

 need to remember how the algorithm is running you have the graph。

The algorithm assigns numbers or it picks a sorted order of the edges alternately it assigns numbers to every edge from one through carbon feet so every every edge has a number on it1。

5，7。1even and you know， it's just every age is a number on it。Distinct number and。It？

Adds edges to the matching in increasing order of these numbers。

That's what the greed algorithm is doing。Okay， so now if I give you a fixed edge E here。

When is E added to the matching？Well， if E E at well。

 E's greedy algorithm will try to add E to the matching at some point and it will add it as long as。

One of the neighbors is not already taken。系。E is added to the matching。Only if。

Like there's no neighboring edge。Which hasn't already been added。ok。Okay， he is。Add it。Only if。嗯。No。

 neighboring。Eddge decided。It E prime。Is added Okay， now， okay， so this becomes a recursive call。

 Now I need to figure out has E prime been added。Well呃。You know， be。You know， okay。

 could recursively say， okay， let's ask whether reprem is added and so on。

When do we know that no edge has been added ever？Well， we know that okay， when do we know？If。

The value that you are assigned to E at if pie of E。This value that you assigned to the edge E。

 the number that you wrote there， if pi of E is bigger than。哦。Pie of E prime。

For every neighboring edge E prime。Sorry it's smaller， right， You'll go in the increasing world。

 Yeah， if pi of fee is smaller then。If P of P is smaller than pi of P prime for every neighboring EG prime。

 then you know that none of the neighboring edges have even been considered so far and therefore you can add AG。

RightIn particular in this graph right when you look at edge which is number one。

 it will always be added to the matching because of course it's the smallest number so that's the edge you first concealular first when you look at the edge number five。

Well， it might or might not be added depending on whether one was added or not right so but when you reach an edge whose number is smaller than all the neighbors。

You don't need to。Like you know that this edge will be added to the matching right if biophy is small enough then。

E is our E is in the matching M。Okay，How if the sum match pi of E prime is smaller than pi of E？

Then you need to test。If啊。You know， of E prime has been added to the matching。Add it or not。

Because if V prime is not added then no no worries。

 V prime has already been added then you can't add right so that's the key。

So it's like a recursive call， if you start an， you look at the neighbors if they're all larger。

 then you stop and say yes， if there's a smaller neighbor， you have to test for that。And then okay。

 test for that again， you have to， you know it's recursal， you check all its neighbors。

 if's a smaller neighbor you to test that first and it's a recursal thing algorithm them。Okay。

 so test of E， we might call test of E prime。And then because E prime is smaller and then it look at all the neighbors of E prime。

All the neighboring edges3 prime and if one of them is smaller it might call a test of E double prime and so on until it reaches an edge which is like these recursor call stop when you whenever you query an edge which is the smallest okay and that's the algorithm okay。

Okay， so so now basically this algorithm has lots of recursor calls。

 so to test one edge you're actually going to query a lot of edges and we want to know what's the total number of edges better。

Like query or what's the runtime of this algorithm？Okay， so let's analyze the run time。

So we're going to analyze the expected runtime over the choice of the permutation。

 like the pi permutation was chosen randomly and that's important for us。

So let's say you have a let's look at a single edge E。Okay， it has a。嗯。

Like D neighbors like or at most D neighbors on both sides， D minus1 neighbors on both sides。

 and then it has more like more neighbors here and so on。Okay， now let's ask。On test of E。

 which edges are queried？What are the edges queried on testo free Okay， suppose I query an edge。啊。

E like E prime somewhere。你异。That would if for that to happen。

 I should have queried everything on the path right like it just like a。

So everything on the path from E to E prime， I must have query that on some parts from E to E prime。

给。And moreover， my numbers on this path have to be decreasing。

That we only query things if they're smaller， right？On tester fee。If we query a prime。

Then two things have to be true， I guess one key thing has to be true pi of pi is decreasing。

I guess strictly decreasing on the path from E to E prime。

Only if the permutation has to be strictly decreasing on the parts from E。Okay。

 so if if let's say the part for E to prime is length K， if let's say the part from。E to E prime。

Is land gate。Okay。Now， if you look at the part of length K。Like you picked these numbers randomly。

 right， you picked all of these numbers， the pi fees randomly。So for it to be decreasing。

 the probability is one over k factorial。Right， so the probability that。嗯。Pi is decreasing。

On the spot。On the path is umost one over k factorial because you picked a uniformly random permutation and the probability that it gives you a decreasing sequence is out of the k factorial different。

You know， increasing decreasing sequences that it could have given you is one over k factor。So。

The product this pi is decreasing is one over k factorial。 Al right， so now so the expected。

So therefore the disproity that E E prime is queried at all。

 and so now how many neighbors are at length K？The number of。Edges。At length， at distance scale。

Is less than like you know， two times d to the K。Okay why is this true well because the graph is degree d right the number of neighbors at distance one is d distance2 is d squared you know at most D and the number of edges at distance k is at most two times d to the K2 because you have two endpoint you started with but it's about2 d to the K。

So therefore， what is the expected number of edges that you query overall。

 like if you ran this algorithm forever， the expected number of edgesqueed。Is at most。

 you know you can sum this over all k， so sum over k equal to 1 through infinity 2 d to the K by k factorial。

Okay， and basically the this is。The same as。嗯。This is the same as two times e to the D。Right。

 it's atmost2 to30。Okay， so it's， I mean， if t is a constant， like then this is a constant。

So the expected number of edges squared it is 2 e to the D。 So that's what we control so this。还一个真啊。

To test if a single edge is in the matching， it it， it can make at most like2 D to the。

To eat the decqueries expectation this mix。To e to the D queries。

Proect you for single edges in this matching。And then， you know， you。

You're going to check if one over epsilon squared edges。Random images are in the matching or not。

 so you get2 E to the D。Over epsilence queries right The total runtime of this algorithm is。

2 E to the D or Epsilon squared。This is a constant if D is a constant。So， that's the。还有个证。Okay， so。

So right， so any questions on this？Okay， so。呃。I guess the like the more。Classical work。

 there's a lot of other work on property testing is on property testing of graphs。Right。

 so like the most simplest like one of the simplest questions is I give you a graph and I ask you to find。

Check if it is close to a bipartite graph。Right， or I give you a graph and I ask you to。

Test if it is close to a graph with no triangles。and on graph problems like checking if a graph is bipartite or K color grab。

 we essentially have an almost complete characterization of which problems admit constant time algorithms and which problems don't。

And there's quite an extensive。一 mean。So it's based on the similararire dilemma which。Is a。

is a very nice graph theoreticaltic result know on its own。

 if you look at it it's quite important graph theoreticaltic result and so on so based on the similar there dilemma we for every for basically most lot of graph properties we know I guess in some you have a complete characterization of which graph properties are constant time testable and which are not。

But these constants for graph property testing。嗯。reInly large。So this number is， of course， okay。

28 to the date its sing exponential。But if you ask， I guess。

I give you a graph and I ask you to test if it is far from having a triangle。In a dense graph。

 And this。There is a constant time algorithm， but the constant。Will be a tower of exponentials。

 like two to the two to the two to the two to the two to the two to the like a tower。

 which which is length one hour epsilon。嗯。Things like that。

 So these things show up when you try to do this， use semire dilemma。嗯。不得。的。

And then there's a whole other area。Thats property testing， which I won't even want to get into。

 But it's this area of check。 you know， Pro testing is like a。

It's like an offspring of an earlier work on PCPs， probabilistically checkable proofs。

And there I guess so Professor Chisa teaches a class on probilisticical checkable proofs and of course。

Its a whole literature on that， but basically or there you again， want a。Algorithm to test。

Some test of test of proof， like， for example， somebody writes on a proof that a three sat form lies satisfiable or somebody writes on a proof that a graph has a Hamiltonian cycle Okay。

 you have a graph。And write on proof that it's a Hamiltonian cycle， well。

 there's an easy polynomial tank to verify， which we do in our 170 classes。

 you just verify as a Hamilton cycle， but you want。诶。A verifier。

 which reads only a constant amount of the input of the proof constant of bits of input。

 and this is possible， and this is。嗯。That's the PCPT yeah that this is possible and so there's a whole class on let's say you should check that out yeah。

Yeah。Into that， and。Yeah， so it sounds good I guess I didn't have much to say much more to add today the next class I think I'll do lowest local lima on Monday should be fun and hopefully it might even be short so。

Next class it like the last one yes so right so I guess we missed a lecture in the beginning of this thing a few months ago and we promise ourselves so that will make up for it sometime so we will have a lecture on Monday and of course like lots of things in this class it's optional so I understand it's an not a week but yeah let's just do it anyway so i'll be。

What lowest look来ma。Time's good， thank you。Thank you， Profeor。

So this is something interesting that we have this property testing algorithm for a linear time algorithm basically so that we would take linear time firstly is is I could I suppose I could just look this up。

 but as maximal matching P complete， I know that a lot of similar problems are P complete。Oh。

 I don't know actually if it's be complete in any case， I know that a lot of。

Problems like that are P complete。But， you know， maximal independent set and maximal， you know。

 maximal just about anything is is often P complete as if the maximum one is NP complete。

 So I I'm wondering if。If we've established like some or this establishes some large separation between testing。

 whether it's close to a maximal matching and testing。

 whether it is a maximal matching or something like that。Yeah。

 that's a good question I don't know if it's be complete。But the yeah。But but I think you can。Yeah。

 for example， we know that。You can't check if a graph has a perfect matching or not。喂你 you。

We sort of know theorems which are stronger than proper testing lower bounds for that， saying。

 you know， you can't even certain LP hierarchies cannot do it。Which sort of and so in some sense。

 we know that you can construct graphs where by looking at locally， you can't make out of it as a。

And makes perfect matchinging or not。So we know that。So in that sense， yeah。

 maximum matching is there is a separation for property testing algorithms。Gocha， Okay， yeah。

But you know， this thing about P is interesting right so there's a like。Line of work more recently。

 right， I guess from past60 or seven years ago， where the goal is to check the computation。

So you send some computation to the cloud， the cloud computes F of X for you， and you want to know。

 you don't want to run recompute F， but you want to be able to check that it did the computation correctly。

So verify verifying delegated computation。RightYeah， this yeah。

 very interesting things there with log and。longong andqueries and things of that。你看。

我灰色点的一 mentioned真的 about。Like。About graphs。 Yeah， yeah。 the graphs。 Yeah。

 it's called the summary ready。Regularity lemma。Pa爸。Thank you， yeah。It's a。Yeah。Yeah， that's the one。

Yeah it basically says that you can take any dense graph and you can construct a constant size model for it。

Like you can construct a model like a you know constant sizes in like a， you can say。

 oh there are four clusters and then you know there's edges between this or you can say， oh。

 it looks like this。You can construct a constant size model that approximates any dense graph。

And that's basically the gist of the the， it's very useful。And of course， it's only for dense graphs。

 if you have a sparse graphs， you can't really expect to construct constant size models all the time。

Dense graph as in there。Order in square edges。I think， thank you。



![](img/2d451cf3f6ffc2b807fbc7ce5efa52e3_2.png)