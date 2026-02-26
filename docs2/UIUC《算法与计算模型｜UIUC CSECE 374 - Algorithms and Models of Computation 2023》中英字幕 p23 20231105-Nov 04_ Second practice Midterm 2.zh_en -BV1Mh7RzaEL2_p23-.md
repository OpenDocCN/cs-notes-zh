# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p23 20231105-Nov 04_ Second practice Midterm 2.zh_en -BV1Mh7RzaEL2_p23-

![](img/1cb082ea6517d0543c57124bee31fe54_0.png)

Okay， folks， there was a problem with my previous video。

 which is somehow completely screwed up quick time on my Mac。So I am going to run through this again。

😔，This is the second practice midterm to this will pretty much follow the same format as the first practice midterm I ran through in class on Thursday。

 I'll spend a few minutes walking through the entire exam just like you would at the actual exam。

 and then we'll start solving the problems one by one。So problem one。

 the short answer version of the question is this time a question about a graph。

 so I'm given a specific directed graph and I'm supposed to clearly indicate the following structures in the director graph below。

Or write none if the indicated structure does not exist。There's an important comment here。

 don't be subtle to indicate a collection of edges。

 draw a heavy black line along the entire length of the edge。

 so please don't use a light pencil and make marks that look like this that's too subtle what we want is to see big fat lines like this that we can see from across the room。

All right， so the structures we're looking for are a depth for search tree rooted vertex A。

 a B search tree rooted at vertex C， the strong components of the graph circle each one。

And then the strong component graph of G is drawn separately on the question hand that there's only one copy of the graph and there's not a lot of space to indicate these things。

 but there'll be multiple copies of the graph on the eventual answer booklet that you'll be able to work with and even a couple of extra copies in case something screws up。

Question 2。Suppose we're given an end digit integer X。

 repeatedly remove one digit from either end of x your choice until no digits are left。

 The square depth of x， the maximum number of perfect squares that you can see during this process。

For example， the number 32492 has squared depth3 by the following sequence of removals， 32492。

 I'll first remove the number two， that leaves me with 3249。

 then I'll remove a 9 that leaves me a 324， then I'll remove a  three。

 that leaves me with 24 then I'll remove the  two， and finally I'll remove the four。

And three of these numbers are perfect squares， 32 49 happens to be the square of 57。

 324 happens to be the square of 18 and four happens to be the square of2。

So this gives me squared depth at least three， maybe there's some other sequence that gives me more。

 but you'll have to trust me that this is the best one。

Describe and analyze algorithm to compute the square depth of a given integer x represented as an array of n deciminal digits。

 assume you have access to a subroutine is square that determines whether a given k digit number represented by an array of digits is a perfect square in K squared time okay so we don't need to think about how do we decide whether something is a perfect square or not。

 got we've got a black box subroutine that will do that for us。

 we just need to concentrate on the order to remove the digits。Question 3。

 suppose you're given a directed graph。 Each of whose edges is colored， either red， green or blue。

 edges in G do not have weights。 G is not necessarily a dag。

A rainbow walk is a walk iny that does not contain two consecutive edges with the same color。

Describe and analyze an algorithm to find all vertices in G that are reachable from a given vertex S through a rainbow walk。

Okay you。Problem 4。Suppose you're given K sorted arrays A1。

 A2 of through AK all with the same length N。Describe an algorithm to merge the given arrays into a single sortded array。

Analyze the running time of your algorithm as a function of both n， the size of each array and K。

 the number of arrays that you're merging。Finally。After moving to a new city。

 you decide to walk from your home to your new office。To get a good daily workout。

 you want to reach the highest possible altitude during your walk to maximize exercise while keeping the total length of your walk below some threshold to get to your office on time。

Describe and analyze an algorithm to compute the best possible walking route。

Your input consists of an undirected graph G where each vertex has a height。

 each edge has a positive length along with a start vertex S， a target vertex T。

 and a maximum length L。Your algorithm should return the maximum height reachable by a walk from S to T and G whose total length is at most L。

All right。So spend a few minutes thinking about each of these problems。

 I think each of the questions is okay。🤢，Do you have any questions， now is the time to ask them。

passs out the answer booklet okay， first thing obviously that I need to do is write my name and my net ID on the answer booklet so I can actually get credit for the work I'm about to do。

嗯。I remembered this time to put the boxes around the pages。One thing to notice。

 this will be emphasized in the actual exam。These don't take the extra pages off out of the answer booklet these are intended for overflow work if you run out of space。

 we ran into several instances with mid termm one where pages got disconnected or people used blank pages that we gave them to answer questions。

We really prefer that you try to keep as much as possible everything within the answer butlet if you need extra blank pages to do scratch work on。

 we can give you those blank pages， but again， keep those as scratchwork and anything you want to submit。

Try as much as you can to keep that within the bounds of the answer booklet none of the questions on this practice exam and none of the questions we hope on the regular exam should require much overflow space we won't have anything like the induction question for midterm one。

But if you do， you know， make sure there's a blank page stapled to your answer booklet that you can write on。

Otherwise， this is pretty much what you would expect for midterm one。All right。

 so let's walk through the answer booklet one more time to see which question we want to start on。

Okay， so we have this graph and we want to indicate various structures within the graph。

 depth for search tree， breadth first search tree， circlely strong component。

 draw the strong component graph， I see there's a couple of extra copies of the graph in case something gets screwed up right this shouldn't be too bad。

Question two。I'm given a number， I need to remove vertices from either end of this number and check。

How many of the resulting substrings are according unqud squares？

This is starting to look like other kinds of dynamic programming things I've seen where you're removing stuff from one end or the other and trying to figure out what your best strategy is for doing that。

 so i'm going to guess that this is a dynamic programming problem i'm going to write dynamic programming here just to give myself a reminder。

This is not intended to give partial credits， just this is what I'm thinking。

 but before I go into any any kind of details， I'm going to move on and again see if I can get at least a couple of ideas about each of the problems。

Okay， I'm given a directed graph with colored edges。

Describe and analyze an algorithm to find all vertices that are reachable from a given vertex through a rainbow walk this。

I a term of art， this is a technical term means there's a walk from S to that vertex。

 but now I'm restricting that vertex to the abow walk。

So this is probably going to be some sort of graph reduction or product or。🤢，Transformation。Um。

 where I'm taking the graph G that I'm given and I want to transform it into a different graph。

I think I remember that reachability is something that's done through whatever first search。

Well that's what says on my cheat sheet anyway， so I'm going to go with it and there might be a temptation at this point to start thinking about how you would modify whatever for search to deal with the colors。

 but that's really a dangerous thing to do。UmThat it's much， much easier。

 although even if it doesn't feel as comfortable， it's actually much easier to modify the graph。

And pitch it to the correct algorithm than it is to try to modify the algorithm。

Cha deal with the variation and the definitions。So we're going to try modifying the graph。

But I need to go on with the rest of the exam to see if Im kind of have any ideas。

So I've got these case sorted arrays that I want to merge we can， you know， merge。Two sorted arrays。

嗯。In linear time。That's the basis of merge sort。So the question is how might we extend this to larger numbers of arrays？

U， and well， I just it certainly doesn't look like it's a graph problem here and when we're like trying to merge things。

We're going to be changing the arrays a lot， so it doesn't look like there's repeated some problems here。

🤢，So。It's not going to be anything for me to memorize。

So the only other thing that we've sort of talked about is you， divide and conquer。嗯。WellI mean。

 merge sort after all is a divide and conquer algorithm maybe maybe this is something similar so we'll。

Maybe you think about this a bit more and come back to it， but this is a release least。

Have some ideas。And then finally question five the problem is really kind of saying it's a bit awkward right so on the one hand like every vertex has a height。

Each edge has a positive length。I start vertex， a target vertex and a maximum length L。

 So this is a lot more parameters than I'm used to dealing with。

But the idea is I'm going to start at S and I'm going to follow some vertex， you know。

 vertices at different heights。And I want。嗯。To maximize the height。

 given that this length is is at most all？佢。So doesn't look like a shortest path problem。

 I mean it kind of does in the yes I've got I've got it。Distances there。

 but I'm not looking for a shortest path。I'm looking for a path that maximizes this maximum body and I've got some distance constraint attached to it。

I'm not directly trying to compute shortest paths， so it's not really a shortest path problem。

But it does seem like maybe shortest paths。Would be useful。To solving this problem。嗯。I don't。

 it's not。NothingNothing's jumping out at me immediately。

 that's exactly how shortres paths are going to be useful。This is good enough。

 I think I'll just set this one aside for a bit and let it stew in the back of my head and move on。

So the last two problems， my brain's a bit fuzzy about what to do。

 so lets let's see if we can make progress on one of the other ones。And honestly。

 I think the one that's going to be easiest to make progress on is is the first one。

 the short answer questions。So I want to compute a depth for search tree rooted today。Okay。

 so I'm going to run up for search， remember the ideas， I'm going to put something onto the stack。

So I'm going to go ahead， you know。😔，I'm going to put my stack over here and then when I when I。

Pop something off the stack。I market。And then I look at my outgoing edges。And I。

Stick them onto the stack。 So in this case， I actually really only have one outgoing edge。

 There's only one， one vertex that's going to be on the stack。 and that's D。

Okay I popped D off the stack， I remember that it was a that forced me onto the stack so I'm going to blame a by naming it my parent of I need to mark D and then I need to push all of D's outgoing neighbors onto the stack well the only one that I haven't seen before is B there's only one out neighbor it's just it's B。

Again， I'll pop be off the stack， mark it and put in the PowerPoer。UAnd then I'll say， well。

 I've got B actually has two outgoing neighbors， one of them is A， and the other one is F。Okay。

 done A's already been marked so when I take it off stack I have nothing to do F now I'll pull this off the stack and market and。

know remember that E was the thing that pushed it on and then I'll take F off the stack and push on E。

 that's the only outgoing neighbor。And then finally， I'll pop E off the stack market。

 Mark this said it's parent and at this point I could E has one outgoing neighbor that that's B。

 but it's already marked so you know when I know when I pull it off nothing's going to happen。

And at this point I seem to be done now， if I look at the marked nodes。

 I'll notice there's no outgoing edges out of them that except for ones that go to other marked nodes。

So this is it， I'm finished， those other four vertices are simply not reachable for many。

Or part B instead of a stack i'm going to use a queue in this case I'll be writing stuff in you know at the bottom of the queue and pulling it off the top。

 so I'll start with C。I pull the off the Q& I market。And then I push on its neighbors， which are a。

F and I。O。When I pull A off the queue。I said it's parent。

Market and I put its outgoing edges onto the queue that's D。

Then I pull F off and mark at the parent pointer。And then I put its outgoing things on the queue。

 that's that's only E we ran it to last time。Then I' take eye off and mark and set the parent pointer。

And then I has outgoing edges to G and H。In some order。Then I pull a D off the queue market。

 so my parent pointer。And push B onto the queue。Then I pull E off。Market， so parent pointer。

And then I put B onto the queue again， I mean， at this point。

 actually I don't need to put B on there the second time I notice it's already it's already in the queue。

 so it's only the first time it comes out of the queue that matters。but pretty much at this point。

 you can see how the rest is going to go。I'll pull G out market and there's the my parent pointer。

 I pull H out， I market there's my parent pointer。嗯。And oh wait， screwed something up。No。

 I shouldn't have had G there because。The edge going from I to G is in the other direction。Okay。

 so when I pull H out， it's at that point。That I put G into the queue。

I pulled B out and market if I remember correctly， it was put in by by。Like by D。

 before it was put in by knee。And then well the only thing' left to do is this so there is my breadth for search tree this is also to shortest paths so the the shortest path from C here to G down in the corner has link one to three。

Um， that's， in fact， the longest shortest pass in the entire graph。Circlely strong component well。

 I can see， first of all。Vertex C is a strong component all by itself。

 it has no edges coming in so nothing can reach it。But in order to be in the same strong components。

 two vertices have to be able to reach each other， says nothing that C can be strongly connected with because even if C might be able to reach it。

 it can't reach C so okay， so C is all by itself。Now here I see。

A directed cycle and so I just trying to mark everything that is in the same strong component as a。

 I might be tempted to think， oh， well these three things are in the same strong component so I'll just draw a circle around them。

But that's not everything the strong component， so there's also this cycle over here on the right。

And in fact， anything in these two cycles can reach anything else so I can go from a to E。

 I can go from E， to A。The fact that those two paths happen to share this intermediate protect be is completely immaterial。

On the other hand， the only edges from these five vertices that I've got here that connect to other vertices。

 they all come in from outside so the edges into these five I' point in and there are no edges from these five out to any other vertex。

So nothing， these fibertices can't reach anything else。So this is one strong component。

And then if I look down here at the bottom， I see a directed cycle through the last three vertices。

 so that means the last three vertices are strongly connected and there's nothing else to be in their strong component。

 so I'll circle this three。嗯。And that immediately tells me that my strong component graph has three。

Vertices， one that only represents the vertex C in the original graph。

 one that represents the vertices A， B， D， EF。In the original graph and one that represents the vertices GHI in the original graph。

And the way these are connected is C has edges going to the other two components。These correspond。

 for example， to here's an edge going from C to F， so that's reflected in this edge going from the component of C to the component of F。

And I've got this。And here。Going from C to I， that's reflected in this edge going from the component to C to the strong component of I。

And I've also got edges one edge going this way， for all of the different edges going， for example。

 from G to E or from G to A or from I to F， there's any number of edges that would satisfy this condition of going from something in GHI to something in ABDEF。

Okay。😊，So。We seem to be done with problem one， so let's go on to one of the other problems。Right。

We've got a dynamic programming problem。嗯。We've got。This graph reduction kind of thing。

Go something that maybe is a divide and conquer algorithm。

And this weird graph problem that somehow involves shortest paths， but。

I'm not ready to think about that yet。It's at number four。

If any idea how we could make some progress on this well。嗯。Well， one idea。

 one idea is maybe we could take。Some are sorry， let me do this in the right color here。

Maybe I could take A1 and A2 and merge them and then take A3 and merge it with the result of A1 and A2。

Then take a4 and merge it with the results of A3 and A4 and so on。对。So I'm doing k minus1 merges。But。

You can notice that the just the last。Merge。Takes me order KN time because I'mrg the union of k minus one lists。

 it's about K Kn minus K times it。Sorry， n times k minus one things that emerging with n things。

 right？And。Actually， the last several merges are going to use going to take about k over two or k times a constant。

Times N time so。This seems to lead to something like K squared n time。😔。

That seems a little bit overkill。嗯。And we're not really， oh。

 we're not really doing anything like divide and conquer here。

Where this is just like doing something iterative， but we know we've got divide and conquer in our in our toolbox so。

I think we might be able to do something better。So one thing we could do instead。

 I could merge a1 and A2， and then I could merge A3 and A4。

All the way up to merging a K minus1 to a K。And now I'm left with。I don't know。

This is called them B for lack of a better term。And I find let's for brainstorming purposes。

 let's assume k is even I'm left with k over two arrays each with length。And number two。

So we seem to have made some progress one in one sense and the number of arrays is smaller。

 but we've also。Made the individual arrays longer， so does that count as progress well if I imagine now recursing at this point。

Let's see what I would get。Well let me actually write this down a little bit。呃。

Let's call this merge all A1 through aK。嗯。And so I'm doing is for I goes from1 to k over two。

Beasts of I gets the merge。Of a2 I minus1 and A2 I。So that seems to be the pattern。😔。

And then finally， I'm going to return。哦。Merge all of。B1 through B K over two。Okay。

 that actually seems to be correct。If I imagine like doing this again， that I'm going to have。

Kver four arrays， each size4 k4 n。 and again and again and again， the number of arrays is going down。

 Eventually I'm going to get down to just one array。

 So the base case here is going to be notice K is one。Returned。Just return the only array， otherwise。

Do this recursion。嗯。And I guess I could say something like， okay， you know？If K is odd。And。Dummy。

Aray。8 k plus one， which is just。Infinities。Just to make it even that this rounding ups not really going to make any difference。

So what's the running time well the running time is a function of both n and K。

The non recursive part of this is I'm running k over two pairwise merges。

 but each so this is k over two times big of n。Because each merge is going to take time proportional to the length of those arrays。

And now I'm left with some problem that has a arrays of size 2 n， but they're only K over two。

And the reason why I'm ignoring the parau， even whether K is even or odd。

 is really I should be putting a ceiling on the K over twos on both sides， but as usual。

 we can kind of ignore floors and ceilings because they' all get swallowed up in the big O anyway。

So this doesn't look like a standard divide in conquer recurrence。

SoI'm a little bit unsure about this， but I guess I'll try running the usual recursion tree stuff and see where it goes。

So。Let'll say this is。The root of the recursion tree for t of N K well。

 I guess the first thing is I could simplify this down to just big O n comes K right the two get swallowed up in the big O。

U。And so the the way that I do recursionary stuff is I write the non recursive part without the big O into the into the。

Into the box and then I have one child for every recurs of call that's just one child in this case and then I have a something that represents。

The root of the recursion tree for that recursive subproblem。

Here now I've got K over two arrays of size N over two。So what I need to write in here is the is。

The product of N and K， right？So if I plug in 2 n and k over  two into the recurrence here。

What I'm going to get here is still n times K。This will be2 n times k over two。

 but the twos cancel out so this is again n times k and then I have one child which is the root of 4 n K over 4 and again that's n times k and this will go on for a while。

So we can already see we're in the even every level of the same case of the recursion tree method。

Like merge sort。It looks a little weird because it's really just a recursion list。But fine。

It's still the case that we need to figure out， you know what's the depth of this recursion tree。

And then you look at the part that's going down， the parameter K。

 the number of lists that we're putting together is going down by a factor of two every time we recurse and so after and it bottoms out when that number is equal to one。

So the depth of this is going to be log base 2 of k。

And so we have log of K recursive levels before we bought them out。And at each level of recurrence。

 we're doing n times K work。And so the overall running time。Is going to be。This。

And we appear to be done。哼。Seems it worked。Now there is another way we could have approached this and some of you are probably screaming no no。

 why did you do it this way because there's this other way that works just as well and that's to。嗯。

Split it into。K over two lists， K over two arrays， and then on the left and K over two arrays on the right。

We recursively。Merge the K over two things on the left to get a list B。

 we recursively merge the K over two things on the right to get some list C and then we merge。

These to get the final output， which is just just a by itself。This also works。

 this is also a divide and conquer algorithm and it's much， much more in the spirit of merge sort。

We're taking the first half of the data and sorting it。

But we're starting off with some quasi I sorted， you know a bunch of sorted little chunks so we're going to sort it by recursively calling the function we're building。

 similarly then we take take the other half of the data on the right and we ask the recursion fairry to sort it and then we merged those two results。

And so this would give you a recurrence。That looks like this， well I've got two recursive calls。

Each with arrays of size n， but only K over two of them。And then at the end。

 I'm merging two lists of total size n times k。So in this case， my recursion tree looks like。This。

And K over two and K over two because。😔，Remember， the thing that goes in the box is the non recursive part。

 it's the product of the two arguments of the function T。

One of those has gone down by a factor of two and the other one hasn't increased to compensate。

 so the product goes down by factor of two。Similarly here， I have N K over4。And K over4。N K over4。

N K over 4。 and these go on。Forever。But now if I look at every level。

Every level is summing up to n times k。What a coincidence。And the depth。Is still。Log base 2 okay。

 but's not going to be oh， it's exactly log based 2 okay。

So I multipied the common level sum by the depth， and I end up with exactly the same running time。

That I did the other way。And there's a sense in which these two algorithms are actually identical。

 it's just that you're looking at the operations in one in reverse order。

 this is actually closer to like bottom up。A bottom up non recursive implementation of merge sort and this is closer to a top down recursive implementation of merge sort but it's the same thing you're merging the same pairs of things just whether there's some stack stuff involved or not is the only difference and so of course it's going to run at the same time。

So great， okay。Now， on an exam， don't do this， don't write down two solutions。

'Only going to grade the first one we see so this is just meant to show you that if you were thinking along a different direction than I was you're also correct so either of these would be worth 10 points but only write down one of them。

嗯。All right。We've got dynamic programming problem。 Yeah。

 that's the one theres a dynamic programming problem。 I remember that okay good。

There's something involving graph and colored edges。There is still this weird thing。C发。啊。

See if I can make any more progress on this。Well。I guess。One thing I might ask。Is。Just。

As a helpful related question， is there a path or a walk？R E to T。That。

Has maximum length l and goes through another vertox。All， so let me just again。

 I'm just brainstorming。The to be accessible。No special meaning。

 I just sort of picked a word out of thin air that meant good。

accessible reach reachable is not a good one。Um， a valid， u nice， pretty coppotic。Whatever。

 whatever word you want that just just gives you the right。The right mnemonics。Excuse me。

 this will come back and yep， good if。There is a walk。R S2 T。Rue thee。With。Total length。At most L。

So here's the crazy idea that if if there was some way of figuring out like for each vertex。

 whether it's accessible or not。Then what this question is really asking for。Is the height？

The maximum height of among all accessible vertices。So every vertex。

 whatever the actual best path is， every vertex on that path。

 every single one of these vertices is satisfies this condition because here is a walk of length that most L and it passes S to v through that vertex and in particular this one up here that has the maximum height。

 it's accessible and so if there were a higher vertex。Somewhere else。

 if there were a higher vertex that was accessible， well。

 then that means there's another path that goes from S to that vertex to T and so that gives me a better way to walk to work okay。

USo we want。The height。Of the highest。Accessible。Retex。Oh。So I'm not really sure。

How we could figure out whether a vertex is accessible or not。Again。

 we're talking about total length， so something involving shortest path seems like it might be useful。

But Ive。It's not coming to me。I don't want to bang my head against the table here。So啊。You know。

 I'm just gonna。I'm going to give myself a note here。To and and and set it set it down again。

 i'll come back to this later， but you know， I think we're might be on to something maybe。

But let's see。All right， so there's two things we haven't tackled at all。

 there's the dynamic programming thing and there's this other graph reduction。

I got to do the dynamic programming first， I'm tired of thinking about graphs。

 so let's stick with something non graphy okay。So don what we programming， so we're going to have。嗯。

You know， some list of。Of。Digits and we're going to be you know removing digits from one end of this thing or the other。

Until we're left with。In the middle of the process。Some substrate。

 some interval going from I to J of these given digits。

And I don't see any reason why we would need to keep track of like any other information about what we got rid of already。

 we don't need to know what order we removed those vertices from either end we really seem think we just need to know about I andJ so。

This suggests that I should be defining a function like this。

 I'll write SD as an abbreviation for squared depth， but I'll just define this。As the squared depth。

Of the subaret starting at I and ending at J。Which is the maximum number of perfect squares you can get by removing one digit at a time starting with this string of digits。

 okay？嗯。Okay， so let's see if we can come up with a recurrence for this。You know， it's going to have。

It's going to have base cases but i'm not going to worry about base cases first I always recommend when you're thinking about recurrences just jump straight into the recursive case first that's the one you really want and then we can fill into base cases later。

So one bit of the answer we can figure out immediately。

Is if the number we're looking at is a perfect square， no matter how we tear down the the digits。

 we're going to get at least one。In in our square depth， right so。This is。啊。

Just write it as is square x from only to J。So I call this is square oracle。

And imagine it returns either zero or one okay， so they really want to be safe let's say it returns a boole and I'll use this iv and bracket thing so。

It's。Either zero or one just to make it clear。And so if it's not a square return of zero if it is a square or return of one and that's good because the most I know about the square depth is if this is this whole string of digit isn't a square then I don't know anything so I leave my scored at zero。

 but if it is a square then I know I've seen at least one square on any path going down so。

Start with that。And now I have a choice， either can either delete the vertex at position I or I can delete the vertex at position J。

 and I have no idea which one of these is better。So I'm going to try both and take whichever one is larger。

So it's either SD of i+ 1 J。Or it's SD of I J minus1。Okay。😊，So SDI plus 1 j， that's what I get。

 that's the square depth of the string that's left over if I throw out the dig position I。

And SD of Ij plus1， that's what I get if I the squared depth of the string that remains when I throw out the x sub J。

So this seems to be one on want。Now base case， I need to make sure this still makes sense like when I and J are really close together so if。

If if I and J are actually right next to each other， this still seems okay。

 I'm going to check whether 53 is a square and then I'm going to either throw out the five or I'm going to throw out the three either way the re person makes sense。

Um， so what if I is equal to J and they're both pointing the same digit I check to see whether five is a square it's not so I get a zero。

And now I'm recursing on something strange。But now the problem is now that my string is becoming empty。

But there's an easy way to tell whether a pair of。Of indices indicate an empty string。

 that's if the left index is bigger than the right index。Um， so this is， you know。

 x from three to three， that's not an empty strength。

 but x from three to two is there are no indices that are greater than equal to three unless they're equal to two。

In this case the right thing to say is zero， if I start with an empty string。

 I never saw any perfect squares， and if you look at the example on the question sheet。

 it shows that the empty string doesn't count as a perfect square， 3-49 counts， 324 counts。

 four counts， but the empty string doesn't。So I seem to have a recurrence。Com。Okay。

 so it's a two parameter recurrence， so of course I need a two dimensional array indexed by I and J。

And if I'm looking at any particular INJ， and I want to know what be filled in earlier。🤢。

So if I'm trying to evaluate SD of Ij， and it's this white square。

I might need I need to know SDL I plus 1j before that， so that's the next row in the same column。

And I need to know SD of I J minus1， which is。The same row， but in the previous column。

So I need the black squares before I get to the white squares。

And one way to guarantee that is in the outer loop， go in decreasing order and in the inner loops。

 go in increasing order。So this is， remember the double arrow represents the outer loop single arrows or represent the inner loop。

 this is the same as saying for I in decreasing order。And then for J in increasing order。

And then I'll evaluate。S T of I J。看。Um， u no。That's great。

 but now we still have the issue of running time。So I've got n squared。

Sub problems because I've got an end by an array， but each one needs to invoke this is square function and the running time here。

Is order K squared？Where k is the length of the string， which is J minus i plus one。

And so for a significant fraction of the subproblem。K is going to be bigger than an over three。

And over four？ForMost of these subproms K is actually going to be relatively large。

So that means really the most I can say。😔，Is is。I'm going to be spending quadratic time on each subproblem and so I end up with a running time of end the fourth。

Oh， man。That looks so bad， right？There's this。Feeing that any any kind of reasonable problem。

 the running time ought to be n log n or n squared。

 so do I really need to spend that much time calling is square can I just like save something somewhere？

Then I remember， I am taking an exam。So at this point， really what I should do is say， okay。

First question is， do I believe this is correct？This may not be the fastest algorithm。

But the first thing I need to know is whether it's correct or not。

 So let's see I've got a reasonable English description I andJ show up in the on the left。

 I describe exactly what to do with INJ on the right。

I've got a recurrence I have an exhaustive case analysis either the substring is empty or it's not if it's not then I do the right thing a check with it's a square that gives me either is01 and then there are two possibilities I take whichever one gives me the more。

Points， okay。This seems to be right， I've got the right data structure。

 the dependencies giving that right evaluation order。And so， yeah。

 unless there's some secret to like doing the time analysis that I don't see right off the bat。

This all seems to be fine。It's just a little uncomfortable， but I think in the interest of time。

 I shouldn't obsess about this， but just okay， I'll come back to this later and see if I can do better if there's time。

K。😔，So let's for now put that down。We've got this graph reduction question for problem three。

And we've still got this weird accessibility thing。Me think about this。Oh。Let's like。

Is there any way that we can check this or talk about？

This definition of accessibility that takes shortest path distances into account。

 and I think there is。We could say this is true if and only if。😔，Take the distance。

 the shortest path distance from S to V plus the shortest path distance from V to T is less than L。

I give any walk from S to V to T。Is short enough。Then if I replace the part going from S to V with the shortest path from S toV。

That only makes the walk better， and if I replace the walk from Vtaity with the shortest path from V to T。

That can only decrease the length， can only like so yeah， it's enough just to consider， in a sense。

 the shortest walk from S to V and then to T。🤢，Which is going to consist of these two shortest paths。

Okay， so now I think we're on to something， so I know I can compute this quickly， so let's compute。

The shortest path distance from S to V。Or all vertices V。Using。Extra。Okay。

I made some progress and I know this is really just one call to Digtra that computes all these distances。

 single short shortest path algorithms always compute the distance from one source vertex to every other vertex and I can store those distances。

In the vertices themselves or in a parallel array or something I don't need to worry about losing them。

 I don't never need to recompute them I just remember them after they're done and Dytra is the correct algorithm because first of all the edges have lengths right so this is not the realm for breadth for search this is an undirected graph so it can't be a dag so I don't need to do the daAg topological sort stuff。

And it they're all positive， so I don't need to fall back on Belman Ford。

So Dyster is the right thing。Okay， all right。Second thing is now I need similarly to compute the distance from V to T for all vertices。

The， which again， I can do using diktra。😔，嗯。But before I called Dexter once。U at。Yes。

And now it looks like， well， wait， Dyster gives me the distance from a common source to every other destination。

And here。I my destination is fixed。And。Not my source。

So can I do I have to call liketra one at a Rivert V？

That seems a little bit wasteful and I'm already worried about that end of the fourth so let me think about this a little bit more how would I do this well oh wait wait wait wait wait。

Oh， look。Perhaps undirected。So that means the length of the edge is the same in both the oh the length of any path is the same in both directions。

 so this is actually I can cross this out and write distance from T to V and that's the same thing those two distances are equal。

A。So I need to compute the distance。From T2 v for every all vertices V。

Because that's the same as the distance from VT， the distance between these two nodes is no matter which way you measure it it's the same so that means I only need to call Dxter once at T。

And that also takes ULV time。And then finally， I've got all the distances。

 so now for any vertex I can decide in constant time whether the vertex is accessible by just comparing the sum of the distances to L。

So in the end， I want to return。The maximum height。Among all vertices， such that。

Distance from SV plus distance。From T to v is at most L。

And this is literally just look at every vertex， spend constant time doing something。

So's sort order V time。Okay， okay， so the overall running time of my algorithm is， in fact， e log v。

All right。That one was not obvious， but we got there， we got there in the end。Good， okay。

They reasonably comfortable with this。Let's go back and now now that we sort of got got our graph brain on let's go back and look at the last problem about rain rainbow walks so there' is something about reachability but we're going to have to build a new graph okay。

To encode the information we have so I usually you know tell the story about I'm wandering around through my graph and I decide to take a nap and I wake up and I go oh wait。

I was walking along a rainbow walk。What information do I need when I wake up。To know how to continue。

嗯。This is sort of the state of knowledge that I need what do I need to know about。My past。

In order to make decisions about the future and so one of the things that I need to know is where I am。

Uh what vertex am I at， so let' let's say this is me sitting at that vertex？

And I see edges leaving this vertex of all three colors， maybe only one of each color。

 like in this example， maybe more， and I need something that tells me which of these edges I'm allowed to leave the vertex。

Through。If I came into the vertex along the red edge， I can't then take the red edge out。

Because that would be two red edges in a row and the universe would blow up。 So I need to know。What？

UWhat color edge I used last？Right。So， color of。Last edge。Okay， so。

Let's maybe formalize that a little bit we build。A new graph。

G prime with vertices v prime ands E prime。Where V prime equals V cross， and I'm just going to use。

The lower case letters RBG to stand for the three colors。

Butman the semantics of vertex v comma C is I am located at vertex v and I got here by walking through an edge with color Z。

可以。Right right， so。Now I need to figure out what to do with edges。嗯。So。呃。How do I think about this？嗯。

There's。Well， let me think about what happens to red edges okay。

 so just think what red edges in G are going to be represented by some edges in G prime。

So there's I'm going to have something。For each。Is a red edge right， so for each red edge UVv。

 I'm going to have one thing that goes。From some use， some copy of you。To some copy of V， remember。

 V prime contains three copies of every vertex from my original graph， one one red copy。

 one green copy， one blue copy。And it's always going to go to the red copy of V because that's what the color coordinate there means。

 the V comma R means I'm at vertex v and I got here through a red edge so if I followed the red edge from U to V。

Ing prime that my state has changed to V red。And I came here from a vertex U that but the previous color couldn't have been read。

It could have been blue。And it could have been green。But it couldn't have been read。Okay。

Those are the red edges， and I'm going to have similar things。For。Ben edgedges。And blue its。

So u to the is green， u to the， it's blue。For green， I'll go from UB to VG and you are。

To V G and for blue， although you are2 V B and U G。To me。So I don't need the third。okay。

 so those are my edges， so I've got actually in the end six different kinds of edges。Um。

W which correspond to legal pairs of colors， blue， red， green， red， blue， green， red， green， red。

 blue， green， blue。Okay。Now。2。嗯。This gives me a reasonable graph。

 but what's now the connection between。This new graph in my original graph。

Is that if I have a rainbow walk。In G， it really corresponds to just a walk。In G prime。

So if I started some vertex and I follow red edge and then I follow a blue edge and then I follow a red edge and if I a green edge and then I follow a blue edge and I follow a red edge。

That's the same in G prime as starting in some copy of the initial vertex。

Then going to the red copy of the next vertex and the blue copy of the vertex after that， so forth。

So I don't need to store colors or anything in G prime G prime is just a graph。

But the way the various copies of the vertices are connected in code。

The color is in the original graph。Okay， so we need to find。To find。All vertices。In G prime。

That are reachable。Wg。S R or。S B or。S， G。 the start verts doesn't have an initial color。

 but I've got three copies， so I have to check which of those three copies。I try all of them。

 I don't know which is the right one， I'm just not going to go by brute force。

Lesson from dynamic programming。So this is whatever first search。From SR。

And G prime and then whatever for search starting at SB。In G prime and then whatever for search。

I by SG。In cheap prime。 And then finally。Turn the set of all vertices such that either VR or the。

She or。The B is marked。嗯。So I guess I'd say unmarked。All season empty be prime。All right。

 so this marks。Vertices。Reachable。对。S， R and so on for the other two。

The overall running time of this algorithm is v plus E。

 and it really is v plus E because the number of vertices in v prime is exactly three times the number of vertices in V and the number of edges E prime is exactly twice the number of edges that are E。

So the three in the two gets swallowed up into the big O notation。

 and so it really is going to be time linear in the size of the original graph。Okay， good。

UNow the the important thing here is to remember， I need to establish the explicitly。

 I need to write something that that gives me。Pcise connection between the graph that I just constructed and the original problem that I need to solve。

So that connection is walks in one correspond to rainbow walks and the other。

 the problem we need to find is reachable from one of these three vertices before we start talking about the algorithm。

And then separately， we give the serrocode for the algorithm。喂。All right， well。

 now at this point I seem to have answers for everything。

 so I'm going to write my name on every page。But there was something that was bothering me。And well。

 you know。We've got a few minutes left to think about this。Before time runs out， so yeah， let's。

 let's， let's go back to。This problem here， the square depth， we got this end the fourth time and。It。

 you know， you don't like it。You know， I don't like him the fourth time。U。

But the only way I can imagine like actually saving some time a year。

Is maybe just maybe the work that I did in one call to squared depth。

I might be able to reuse in different callss to squared depth。I mean。

 we did do this trick and you actually can do this trick if instead of is square。

 I'd ask something like is palind？Though that problem becomes much more boring。So。Yeah。

 maybe I could imagine doing something along those lines。

And kind of I'm kind of thinking oh wait that K squared。

 maybe that that that's from doing some stupid multiplication algorithm。

 it turns out there actually is right there is an algorithm to decide whether something's a perfect square in quadratic time and under the hood what that uns squared time comes from is the schoolbook lattice multiplication algorithm for indiigent numbers。

And if you replace this with something that is based on Ktsubba。

 you can actually get the running time of is square down from K squared to K over three。嗯。

U and in fact， you could even get it down to something that's close to linear if you use an algorithm based on FFTs。

U but working out the details of that that optimization is really beyond the scope of something that you expect to do in 20 minutes。

 I mean that haven't even figured out exactly how is square works using only like one multiplication or the order one multiplications。

So yeah， I can I can imagine maybe getting this down to。You know， into the two plus log three。

Using cartsba。嗯。And in fact， yes， you can。But we would take more than a single page to explain how that actually works。

So yes， I don't really see any any other place where this gives。And in fact。

 this is the target running time that we're looking for in this case because after all this is an exam。

 we're not going to ask， we need to ask things that you know fit on a page like this does。

So at that point， we are finished with the practice exam。

Still you know a couple of things to think about for later if you want to think about things like this for later but that's going to be it hopefully this video will actually work and hopefully。

I will see you or most of you， at least。Or at the exam on Monday。All right。 Thank you very much。

 Good luck。Don't forget about the time change， we'll see you next week。



![](img/1cb082ea6517d0543c57124bee31fe54_2.png)