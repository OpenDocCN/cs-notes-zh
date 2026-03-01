# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P9：-10-EECS 281_ W21 Lecture 10 - Elementary Sorts.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

All right， yes， indeed this is the right link， sorry， a couple of minutes late there。妈妈。

Can folks hear me out there， can I get a quick mic check， let me stop the music， okay， we'll go stop。

Boom， boom， boom， I hope everything's good。All right。Alright。

 so in this lecture above sort search the selection sort accounting sort will be featured there are some really weird sorts out there that's from one of our staff Thank you staff So before we get to sorting we kind of need to finish up union fine which we didn't get to last time。

That's okay， I think if we cover the first half of elementary sorts， specifically bubble sort。

 maybe we'll get to selection sort， it's completely fine。

 we should still make the schedule before the exam。All right， but let's get started。

Basically this slide is kind of where we left it off last time。

 which is an implementation of set union using ranges okay by ranges we mean pairs of iterators right that tell you a begin and an end to a specific range so we were talking about merging two subsets right set one and set two so therefore we need four iters there to represent the range from the first set and the range from the second set and then an additional iterator。

As the output iterator。And then a comparator， right， which if you started project two。

 you're very familiar with right now。Okay， implementing your own comparators using functionsctors。嗯。

And so this code basically goes over the example that I went over last time is just code that execute the example quite nicely。

 so I'll let you kind of look through the code。To play around with it。It's interesting。

 generalized templated code。But if you recall it basically has pointers， well in this case iterators。

 right the begin iterator for or the start iterator for set one and then the start iterator for set two and then you move them along as you push into the output set。

 which is basically setting the output iterator and so you need to move the pointers level based on what you end up outputting。

So all right， go go back to this example and check it out。

And here's a summary of implementing subset using ranges。

 so you know if we were to implement a bunch of operator operations using ranges as we showed in the previous slide。

 you'd have an initialization， which would be well if you know。

If you don't really care about sorting， then initializing something like that is basically constant time。

 you just you're given the range， you don't really need to do much。

 but if it's looking to maintain some sort of constraint like we saw in the last lecture。

 then it's something like end log end time。Clearing， that's going to be constant time if you know。

Range for the container was declared in the stack。So it lives in the stack， it's constant time。

 but if it's a contains objects that live in the heap。

 then that can take linear time because you have to go over each one of the elements and call the constructor。

嗯。Is member if by binary search right， which is is member is analogous to find look up search。

 whatever you want to call it， that's login time by binary search copying is linear time if you want to copy everything set union is linear time by the previous algorithm that we saw basically is linear where n is really the sum of。

The size of set one and set two okay？Of the elements in set one and set two。

And then set intersections we haven't discussed in detail。

 but similarly is' also linear in the size of the input sets。Okay。😊，All right。

 so we also have in the slide a job interview problem that I will skip in the interest of time it's actually quite interesting。

 it does come up often in interviews as far as you know our experience goes but so don't get too hung up on it being like an interview problem just look at it as a you know challenging problem that you can think about brainstorm and try to come up with a solution and then come to office hours and we can discuss in details excuse me have my son interrupting my lecture get out thank you。

Sorry， apologize for that。All right， so on with specifically Union fine， okay。

 this is rather interesting operation for which we really haven't given you a。

A problem to apply it too。Yet we will later on the semester， which is why we're discussing it now。

Okay and you will implement it in lab okay you will implement Union Fine in lab specifically one of the more performing variants of Union findine Union Fine is the context in which you will see it in this course is in context of graphs right so when you have nodes and you have edges。

But more generally what you're looking to do is represent a bunch of disjoint sets， Okay。

 so everything， every node in some graph can start out as you know being its own set。U。

And then as your graph algorithm goes along， it might start to increase the size of the set by joining other smaller sets。

 well not necessarily smaller， but other sets with other sets， so basically merge them together。

Let's say the you know particular application would be if you have the Mars rover and there's a bunch of like peaks and Mars and you're trying to disperse them so maybe the nodes are the peaks and maybe the edges are kind of whether the rover was able to find a path from one peak to the other right and so let's say the rover was able to find you know I guess a cluster of peaks that it can get to like Alba Patera and tempe and whatever so those are。

Connected by red edges。 And then there might be another cluster。

 There's connected by blue edges there on the slide。

 And then yet another cluster connected by green edges。 right。

 And then all the other ones that don't have edges can just be in maybe independent peaks that the rover was not able to get to。

 right， So they're not connected。 Okay， so there's a bunch of。Disjoin it sets here， right。

 There is kind of the rent。Subset， which contains what，1，2，3，4，5 peaks。

 Then the blue1 has three peaks。 The green one has what is that 6。

 And then all the other ones that are white are just。

This joint sets that just contained a single element， right？嗯。

So that's the representation that we're looking to implement。

 meaning we have these thesejo sets and something might be happening in the example it was the Mars rover trying to get to the different peaks and as the algorithm moves along you want to increase the size of the set right because all of a sudden you've found another node that shares an edge with one of the nodes that's already in the set so that。

Set would grow to incorporate that new node that it has connectivity to。 Okay。

 so the numbers under there are really just labels， integer labels for each one of the nodes。

 because again， we keep using integers because they're simple to use。And so like I said， you know。

 you have the red subset， the blue subset， the green one， and then a bunch of single element sets。

 okay？And usually with these algorithms， like we won't go over it in detail yet。

 we will get to that after the exam， but usually you start out with everything being。You know。

 a single element set， okay， and as the algorithm goes along。

It basically ends up having all the nodes or all the elements in the same set right so you want to get to a point where everything single element set to just having one set that has all the elements or nodes in it。

哎。All right。The two operations that we need to achieve this are fine， which is lookups。

 so fast lookups in union， which is how do I take two particular sets and join them together？

Which we discussed earlier for specifically sorted ranges。So。Oops， then I go back。

So fine is check if the element belongs union is merged two sets together into a single set okay and so this is why we kind of call this union fine right so notice that we're leaving intersection out we're not going to discuss intersection or anything like that。

All we care about is union fine because this is what's going to be relevant for algorithms later in the course。

Okay， so let's look at a quick example， so let's say you have a set of items right here， again。

 we're going to think of them as integers， they're all a different color because they're single element sets。

And here， I mean， the better label here is just set one rather than group just to avoid the mathematical distinction。

 So this is set， so set1 might be 1，4，5，810， and then set  two then might be incorporated as2。

6 and 7， right so we're just choosing that as an example。So admittedly。

 if they belong to the same set， then maybe we would change all the colors it's not shown here in this slide。

 but if I'm going to group them together belonging to the same set then。

And it would potentially then change all the colors。So the question would be。

 are one and eight connected， right， are they in the same set？😡，Okay。And so furthermore。

 so this would be a question that find will answer。Right。😊，And then the other。

Thing that we would want to do is in the case that say one and six， for example。Have some connection。

RightAnd here connection is in the most abstract sense， right。

 It's really context dependent what we mean by collection again， the previous example was。

Peaks and Mars that have a path。To each other。What do we do and how long does it take to merge the two sets right so if I find that a one and six share an edge。

 then that means that now set one and set two need to belong to the same set。😡，Okay， so。

What is the fastest way that I can merge them together？And that's what we're going to be looking at。

Next， algorithms to perform these two operations。In。So from what we've described so far。嗯。

It would be that union takes linear time。诶。Because in the worst case， I have to。you know， create。

 say some additional container that fits both set one and set two and then copy everything from set one and set two into like similar to what we did it for the sorted ranges。

Set union algorithm。Okay， and then the final algorithm， okay， not being。

Any particularly smart about it。Would be linear time。

 right because you'd have if you have a set and again， it's set in the most general sense so far。

You would have to invest linear time to find whether a particular element is in there and you might say like。

 well， what if we you know maintain sorted ranges， then thatd be log end time， true， yes。

 but we're actually going to describe better algorithms that will'll eventually get to algorithms that run better than log end time and we don't have to worry about maintaining the sets in sorted order。

All the time。Okay。All right， so let's look at these data structures。

What we would want to do is basically maintain representatives for each one。嗯。Of the elements or the。

Or the nodes kind of depends on the context that you're talking about， let me。

 I'll stick to call them elements。Okay。嗯。So every set element K must know its representative of J。

 whatever that is， okay？And so if each element keeps track of its own representative。For kind of。

Which that it belongs to。Then the fine operation is quite fast， right， because I just need to check。

 hey， what's the representative of K and what's the representative of J？Okay。😊。

And if their representatives match， then that means that they belong to the same set and if they don't match。

 they're not in the same set。诶。All right， so let's look at how this would work。So we have。

 say a bunch of items， again， we're keeping it simple， these are just integers。

And so and then each one is going to have their own representative and what we're going to do is everybody's going to start because there。

 again， everything start out as being single element disjointed sets so everyone will have their own representative right here。

Okay。😊，So right now， if I were to check， oh， are two and three in the same set， right。

 I would query the representative of two to just see that it's its own representative。

Which means that。You know， it's its own set， it's a single element。Just join a set。

 and then I would do the same with three。And then compare that the representative for two is two and the representative for three is three。

 they're different representatives， so therefore they're not in the same set。ok。All right。

 so now let's go over a bunch of operations on the right hand side of the slide here。Okay。

 join here and I'm going to note it up here， join here means。😡，That I'm doing first， are you a。

Followed。By union。That's what we mean by joining here。Apologize for the handwriting。Okay。

 so that's what we mean by join down here in this operation right。

 so let's go over a quick example of this。 So in in the first operation here where we're trying to join one and3。

 that would mean that I would do a fine on one。That would just tell me that the representative is one right up here。

Okay。😊，And then also do a fine on what is a three， and that tells me that it's representative。😡。

It's three， okay？So after that， we would do the union of one and three。

Which means that what I would do and this is by convention。Okay。

 so I'm making the assumption that this is what I'm going to do because actually there's multiple ways of implementing this。

Like for example， oh， if I need to pick a representative。

 it's going to be the one that has the lowest integer value。That could be an option。

 but here we're just going to say whatever is。The left element that I'm joining。

That's going to be the representative， or I'm going to pick that as a representative。

 so that would mean that now the representative of three。Is going to be。

I'm goinging to set it equal to one right so up here it would mean that this is the change that I have after the join。

The first joint。Okay， it means I've updated the representative。Of three to be one。滚。All right。

 so that's easy enough， in fact， and for the later。

I'm going to raise some of this to make some space。And for the later operations。

 they're very similar， right， so now I'm looking to join 3 and 8。

 So if I do fine on three by the the last update that gives me a one。Okay。

 because that's the new representative。And then I do a fine on eight that gives me eight。

So that means that union of three and eight。Implies that I'm going to update fine on8 to be one。😡，诶。

And now you can see that so far we have in the same set， we have one， three， and eight。

They belong to the same set， everything else is its own single element disjointed set。All right。

 I'm going to make some space here。Third operation join one in five similar situation the representative of five now that's supposed to be a one。

Let me write that again。So I won't write that one out because it's a mirror of what we've done earlier and so now we have join of seven and four okay。

 they're thisjoin it， I want to connect I'm going to add， I want to union them into their own set。😡。

By convention， because we've chosen to， I would pick seven to be the representative， okay。

 so that means that for four， the representative is now seven。Okay， and then。Join of7 and two。

 I would do a fine on seven to see its own representative。

 a fine on two to see that its own representative， and by convention。

 I would pick seven again the first。Argument to the join。

 that's what I'm going to pick to be the representative。All right， and lastly。

 this last operation is going to be a join on two and five， so let's write this one out。

 it would be a fine on two that gives me seven。Okay。😊，Then a fine on five that gives me one。Okay。😊。

And what would happen now is like， oh。Well， I now have to take。When I do the union。Of two and five。

I now have to take every element。That belongs to the set with Re one。

I'm going to need to change all those representatives to now be7。Okay， so all the updates here。

 all the updates earlier were just simple。 but now this update is going be quite large， right。

 I'm going have to take and the representative one and set it to 7。

 the representative3 because the two is already7， so on and so forth all the way till the representative 8 that I will set to 7 right。

 So everything now。7even。Seven， I think except for six， right。

 because we haven't really done anything with six。So at the end， I've joined together or union。

All the nodes except for six because if you look at the joint operations。

 I never did anything with six。诶。😊，So if you notice in all this example， the fine was fairly fast。

 right， I just needed to look up the representative， that's it。It's basically a constant time lookup。

But the union could potentially take a long time because if you saw with the last operation。

 I had to update the representatives for a bunch of elements。 right， if。

 if the set grows large enough， and then I need to update all the representatives for that large set。

 Then that's a lot of updates that need to be done。 In fact， in the worst case， it'd be linear time。

 which is what's shown now on the slide。 Let me make。You know， erase some of this stuff。Okay。

 fine is constant time。Okay， but then union is going to be linear time。

So that's kind of our first algorithm for Union find。That uses representatives。嗯。So far， so good。But。

Can we do better Well， we can do better even with this approach。

 that is if we were to keep track of the sizes of the sets and then say like， oh if the size。

 if I'm going to do updates of the representative， I might as well only update for the sets that are smaller right but then you have to keep track of the sizes of the sets which is also pretty annoying and you know it can lead you into bugs。

系。嗯。So。Can we do better than is there a better way to do this。

 largely because we would want to avoid doing or investing linear time to do a union？Okay。Al right。

 so let's do a smarter union fine。 in this case， what we're going to do is not necessarily store the actual representative for each element。

诶。😊，But instead。Just make sure that I can find the representative quickly。Okay。

 so that means that when I do a union， I don't have to invest my time updating a bunch of representatives。

But then I kind of shift the burden to fine because now we have to spend more time doing the find function to actually find the representative because I have to。

Basically traverse back。Through representatives to find what the parent representative is。

 if you will， All right， let's look at an example of this。Okay。

So the first few joints here are going to look quite similar。 Let me write out1，2，3，4。6。8。

The joints here， the first few ones are going to look quite similar to the previous approach， right。

 Joining one and six means that now one is a representative for。嗯。Six。

 Jo one and eight means this is a representative。Then one and three means。One is the representative。

Now six and five， let's write this one out， so if I did fine on six。

 that gives me that the representative is one。Okay。😊，In fact， notice that really here。

 if I were to write out the traveral to find a representative， it would actually look like this。

 right， it would tell me。😡，F of six leads me to find of one， which gives me one， okay。

 and that's how I would know that the representative is one， right， because。

One was its own representative， so I have you know nowhere to look up further。

 so that's when I say okay， so the representative of six is actually one， right？😡，So in short。嗯。hos。

I'm going to write this as one and then find on five gives me five。

So that means that I I do a union of six and five。That would mean that my update should be that。

The fine on five should be。Wna。Oops， that's supposed to be a one。All right， so did this， the this。

 the this here。All right， now join of four and seven。

 this one's you know fairly straightforward like before right except we would pick this to we would pick four to be the representative of seven。

 then join four and two， we would pick four to be the representative of two again that's by the left opera end convention for the join。

And then lastly， joining a five and four， so we'd have a fine on five right， that gives me one。

Then a fine on four。That gives me。F okay， but notice， let's spell out what the fine on five would be。

诶。😊，The fine on five would be that it goes to six and then it goes to one。Right， so。

Splling it out here。Because of the join number four that I have right here。

 that would mean that strictly speaking， this would do fine five， fine on six。

 which then gives me fine on one and then eventually it gets to one。Okay。😊。

And then the union here would be， oh， okay， of five and4 would just be， I make sure to set。

F for4 to be one。诶。😊，Equals to one。And then if I were to check。Which elements belong to what， right。

 I would check well。嗯。😊，Let's see what element one， it's in a set labeled with one， okay。

 element two。Is in a set that's labeled by four， but I have to follow all the way through and if I go to four。

 then it tells me that the actual set where it's at is one okay？

So that means that two is also in set one。Then similarly for three， it already tells me it's set1，4。

 it already tells me it's set 1，5 already tells me it's set 1，6 already tells me it's set 1。

7 tells me I have to go to 4，4 tells me that it's in set one。

 and then8 it already tells me it's set one so basically this example ran all the way through to merge all the elements into a single set right and if you look at the joins then it makes sense。

诶。Cool， so that's the second example。Here that was a kind of smarter approach than what we had before again what we did is shifted towards instead of always updating the representative when you're doing a union。

 you basically do no updates doing the union other than the elements that you're looking to join。😡。

Right， or a union。But then that means that fine has to invest more work to find the actual representative for that element right because the representative that it has might not necessarily be the ultimate or call it root representative for the set right it has to traverse back representatives until it finds the representative that has itself as its own representative。

 which was the example that we had when we did join number four with join on six and5。😡。

And so that means that now union is constant time， right， Union means I would only do two updates。

To change the representative of the two arguments that the Union operation would have。诶。

But then fine might be linear time， right， you might have to traverse back。

Through all the representatives in order to find the ultimate root representative。

 so basically we shifted the burden from union that was linear time before to fine。

 which is now linear time， but now union is fast okay。

So how about if we come up with something that gives us？The best of both worlds， right， meaning。

A fast union and also a fast fine， okay？嗯。And the answer to that is called path compression Now this is what you were actually going to end up implementing in lab。

Okay。😊，The trick to path compression is the fact that so far we've been talking about。

The find operation has been read only。Okay。😊，嗯。So I just。Look up whatever the representative is。

 but it doesn't update anything。Okay。We're going to change that。

 so now union will be able to make updates to the representatives as I traverse along the representatives to find the ultimate root representative。

诶。😊，嗯。And that's what's actually going to get us。As you'll see to a very fast both union and also fine operations。

Okay， and specifically because。Even though we also we are shifting the burden to find a bit。嗯。

By having it do some updates of the representative， and I'll show you in the example what that means。

哎。We are also going to be able to amortize that operation over the lifetime of the Union fine algorithm。

 and it's going to end up that both operations are going to be amortized constant time just to save you the suspense。

系。But we're actually not going to show you mathematically why at least to that we're just going to hand wave and tell you that it does。

 right， but it's it's， you know， if if you understand immortized complexity， then it's。

Interesting to see， right？So again， we're basically going to mortize。嗯。Any of the union fine。😡，嗯。

Steps。We're going to emortize over the lifetime of those operations and by lifetime here。

 I mean again， remember， you start all single element disjoints and end with a single set that has all the elements right so the lifetime is the starting of all elements being independent and the end time being all elements are interconnected in a single set。

Okay， so that's the lifetime。Okay， and we won't go over the analysis of that。

 but just know that there is some rather surprising pricinging results that this。This。

 if you do that onortization， it means。😡，That it grows really。

 really slowly right in fact it is bounded by the inverse acromen function so that means and I think that value is roughly around5 so it basically means that your' union fine right so this is I think that's five but Doug quote me on it just the point is it's a constant。

嗯。And so the basically is just asymptically going to tend towards five and never get above five Okay。

 so this is。嗯。This means that every single either union or fine operation。

It's going to be roughly constant time。Okay。All right。

 so let's look at how this would work and then we'll take it some time to answer some questions on the chat。

We also need to。Start with our representatives。Right junior join of two and four， right。

 that would mean that。The representative for。4 is now two， join of one and two。

 that would mean that the representative for two is now one。Okay。

 join of five and seven that means all so I'm done this one。

 this one join of five and seven means that now five。诶。Makes sense。 Is the representative for7。

 then join of five and6 now means that five represents。six。Join of eight and five。

Means now that eight represents。All right， so so far all these easy operations。

 I haven't really shown what path compression does， okay。

What pass compression will do is that asset traverses back to find the ultimate。

 call it ultimate representative for a set。It's also going to update the representatives that it saw while it was traversing。

To be that representative right so that next time you call a find。

 you'll basically have the freshest most up to date version of the representative for all the nodes in the set right or all the elements in the set。

😡，Okay， so what would happen here， right？Is that？If I call fine on four。That gives me fine on four。

 gives me and I'm going to spell it out， just gives me fine on two。Which gives me one。Okay。😊。

And just right there， when I did define， and I noticed that I had to go through two to find one。

The fine operation itself is going to say like， all right。

 so as I'm done with this operation just before Im finished with it， I'm going to update directly。

Oops， I dry。The wrong place， I'm going to update immediately the representative of four。To be one。

 right so immediately right there， as I did that first fine， I made it one。😡。

And what that's going to do is that next time I do fine on four。

 I won't have to go through two to find the actual representative。

 it would have already been updated right by the find operation。😡，All right， so now we would do。

A fine on。What is it，7。That basically tells me that I need to go through I need to go through five。

Okay。😊，Which then tells me。I have to go through eight and eight it' its own representative， so boom。

 I found the ultimate representative。Okay。😊，And similarly， what I would do right there， right。

 I haven't even called Union yet， I'm still doing fines， right？Fine would make sure to update。

Seven immediately to make its representative eight。ok。😊。

And that's when fine operations would be done。And then the union is kept simple， right。

 I can just do union of four and and four and seven and like before I would say， okay。

 now the representative seven is just going to be four。Okay，Oh， sorry， not four。

 but one because I made that update in the previous find， right？Just be。1。Okay。

 so here it would be that I set the representative of seven。

To be equal to whatever the representative of four is。Which by this first operation right here？

Should be one。Okay。😊，So again， the key and these are subtle differences which you know。

 if you're watching this in two time speed and I know I talked fast。

 so you might want to put it at regular or even slow it down so we go step by step and you can see the differences between the previous two examples。

 okay。Specifically this one， we were updating as the fine operation was finding the representative。

 the ultimate representative。It was updating the representative all along， all right。

 for each one of the elements that were in that set that I had to traverse。Right。

And that means that next time I do a fine， I won't have to incur that many steps to find a representative。

 so that's why you're amortizing the operation because if you do these updates， then on average。

 yourorization your number of steps that you would do，😡。

For the fine operation and also the union operation is going to be in the order of this acreman function。

 which， as I said， is bounded above by a constant。So that means that they are a mortized constant time。

 so I'll delete all this so you can see。All right。😊，Cool。

 so let me break a second see we do have folks from staff on the chat that is great。

There are a variety of ways。Yes， that is a comment there's actually multiple ways of implementing union fine。

 okay， that's what I said like by there are conventions that say that if I'm going to union。

 the one that I'm going to pick as a representative is whatever integer is lower。

Integer value for the representative right assuming that the representative is an integer because you can totally have representatives that are not integers。

Nothing， nothing in what I described means that they have to be integers。

 but it's just easy easier to think about if they are integers okay we also spoke about there being like I keep track of the size of the set there's implementations that are like that。

 but path compression is really the most efficient way to implement it it is trickier and it can lead to bugs because it'll be updating for the find operation but。

It's still doable， in fact， that's what you're going to do in your labs， okay？Alright。嗯。Yep， correct。

 that's basically what we've been working along， you'd have some item that we're labeling with integers。

And then representatives that we're also labeling with integers right。

 you can think of this behind the scenes as being an array right and yeah your array can start indexing at one here and then forget about a Serth element like we did for heap。

You can think of it that way， right？嗯。All right， so let's move along。

 that's basically it for union find more on it when you get to labs。

 we do have a whole bunch of interesting study questions。For you to look at， make sure that。Do that。

 they study questions for a reason， right， they're good practice for exams and such。Okay。

 so now let me bring up。The lecture。On elementary sorts。



![](img/0567d558cffb0d507667ab6fc2183b83_1.png)

，Excuse me。

![](img/0567d558cffb0d507667ab6fc2183b83_3.png)

All right， elementary shorting methods。Okay， so this is。

You've definitely seen sorting methods before， you've probably seen implementations of sorting。

Algorithms you I mean。Hopefully everyone has made a call to a sorting algorithm before。

 whether it be SDL or some other language。So you've used sorting algorithms in one form or another。

 even in daily life， you would use sorting。Okay， so what we'll do is we're going to actually discuss elementary sorts and they're going to be called elementary sorts because they're not the most efficient sorts。

嗯。But they are useful for studying how one。Can look at an algorithm and basically find ways of improving the algorithm。

Right now most of the things that we will discuss are going to look like kind of micro optimizationtimizations to the algorithm。

 which is true， but what you know， the idea is for you to look at the example of taking some algorithm and thinking about what it does and where things the algorithm can be doing things better。

Okay。And of course， we could try to come up with some really fancy algorithm to do this with。

 but then you'd have kind of to think about what the algorithm actually does and what is it。

 you know， what's the data and what you know， so rather than pick something really complex to analyze and to improve。

😡，Let's pick something that's very familiar with and that people use often in practice。

 which is just sorting algorithms， right？And。So for elementary sorts。诶。Basically。

 those that's your bubble sort， which you probably heard of before selection sort， insertion sort。

 and counting sort。Probably today we're going to cover bubble sort and selection sort。

 and we'll start on Tuesday with selection sort and county sort。I mean， it depends how。

How far we get in the slides， okay？Um，Now， similar toum how we were discussing heaps， we said like。

 hey， really，um， you know， what you're using to store。What you're storing in your heap。

Can be any type of object as long as they're comparable。

We just chose to use integers because that's easy for you know teaching purposes。

 same thing with sorting， right as long as you can compare them， you can compare any type of object。

 it doesn't just have to be integers， but for the most part in these slides。

 it's just going to be integers。But it could be any key as long as you provide a functer to compare the objects。

Now then we have the category of high performance sorts。 It's kind of fancy word。

 also known as efficient sorts， high performance has。I don't know way too many connotations there。

 so I would just call them efficient sorts and that's your quick sort。

 which is very interesting algorithm， meC sort and lo and behold there's heap sort。嗯。

Which we've already covered right so if you go back to the HeapS lecture。

 we talked about the fact that HeapS is an efficient algorithm。

 all these sorts as we're going to see are going to be and login algorithms。

Whereas these over here are all going to be both and squared。Okay。😊，Then there's also RAd sort。

 which we will not discuss， but encourage you to look up， it's a very interesting algorithm。

For sorting。All right， so let's get on with elementary sorts。

 but one thing to note is that elementary does not mean that these sorts are useless and in fact we're going to discuss situations in which。

Sometimes even an if you know， elementary sort might work better than one of the efficient sorts。

And in fact， sometimes you you。There might be situations in which you don't want to rely at all on an efficient sort。

 because even though they might be fast， they would end up doing more work。Then an elementary source。

 and we'll discuss how that can come about。So the idea is to illustrate how to approach a problem。

 this is what I was alluding to earlier， how to compare multiple solutions and how to optimize， okay。

嗯。So we will， for the most part， be talking about。A race。Okay， specifically in this lecture。

And then we're。Some。Some of these algorithms。Are easy to adapt to a linked list。

 some of them are not as easy to adapt to a linked list。 We won't cover the details。

 but we will ask you questions to think about right like from what you know about say bubble sort。

 how would this behave is if instead of an array， it was a linked list right and then there's distort sorting algorithms。

😡，It's actually not plural， it's just mainly one。For which it's specifically suited if you have linked lists。

 if you're trying to sort a linked list。😡，Sa you the suspense it's MERS sort。

 we're going to have a dedicated lecture on MERS sort。

 which is the sorting algorithm that is best suited for linkedlist okay。All right， so for the STL。

 if you haven't used it before， what we would need to do is pound include algorithm。

Then you can declare a vector or an array for that matter and then pass it to the STL sort function。

 which is in the STDA space， just like everything STL。If you recall you know this。

Begin A is syntactic sugar， you could just as well call it with sort。What does it A do begin？A dot n。

嗯。Well， hopefully that makes some sense。Allright so we will use indices and array right so we're not going to be using pointers although indices we're also going to refer to as pointers because that's why they do like an index just points to some specific slot in the array so we will use those names interchangeably and for the most part just using arrays okay so one good exercise that you know。

If you choose to accept the challenge is to rewrite a bunch of the algorithms that we give you here using。

Iters。Okay。😊，Rather than indices。嗯。All right， so before we dig into to the details of the algorithms。

Let's。Get over some nomenclature here。嗯。When we say internal sort。Okay。

It means that your sorting algorithm。I mean。Basically， you're sorting function， if you will， right？

But the function implements an algorithm。It can see all the elements。

 meaning all the elements they fit in memory， you can load your array in memory， all your data。

 you just load it in memory。In fact， all the examples in this lecture are going to assume that it's a type of internal sort because all we're sorting are integers。

 integers are very easy to fit in memory， so even if it's a very large number of them。

 so your algorithm will have all the data available to do the sort。诶。😊，Also。

 we assume by way of the fact that we're using arrays that we have constant time random access。Okay。

😊，Now， then there's indirect sort， okay， which means。I might not be able to fit all my actual data。😡。

In memory。But I can fit like some indices that are keys to identifying the data that might live somewhere else。

Okay， so if I sort and reorder。The indices that's just as good as sorting the data。

OkaySo you would need some prep work right， to you know identify the correct indices for your data that represents your data as you need to in order to compare。

Two different sets of data， just using the indices。😡。

And then that way your algorithm really only cares about these indices。

 as long as that setup is done correctly， your algorithm， your indirect sort。

 we only care about those indices。And then there are external sorts。Okay。

 where really I can't fit anything。In memory。I I have to rely on disc， okay， it might be like。

Oh my God， when would that happen？Actually nowadays this happens quite often right and this is my first shout out to 403 students。

 this is when I would interject with some sort of big data stuff right oftentimes you're doing big data which you're talking terabytes and terabytes of data and you need to sort that data you can't you know if you're going to buy a computer that has you know terabytes of RA。

That would run you a pretty penny， but then if you just have a cluster of smaller machines。

 that is way cheaper。And then how would I go about sorting all this data that lives in a bunch of different machines？

It's a very interesting question that will when we get to merge short。

 we'll see how it could be done。Okay。But if you're talking about a single machine that still doesn't have enough memory。

 what you can do is like just load up chunks of the data that you're looking to sort right and you know。

Sort that sequentially， of course there's a step afterwards that would need to do because the fact is。

 if you have a bunch of sorted chunks， that doesn't mean that together they're going to be sorted。

But。Think about if you have two sorted sets， you already know an algorithm to union the two sorted sets。

Okay so then that's what you would need to apply after you sort the different chunks。

And that algorithm is basically the previous lecture where we talked about merging two sortdid ranges。

Or union to sort ranges。Alright， so a nice exercise that we sometimes do in lecture is to just implement a swap function interest of time will just give you solution right there fairly easy I mean you need to have somewhere to store at least one of the objects that you're looking to swap so this example is just using integers。

 but then the example below is using a template， so it could be of any type of object。Okay。

 and so that's， you know， fairly you've probably written something like this before， but。Ideally。

 you would rather use the swapb that is included in STL， right by doing pound include utility。Okay。

 it already gives you a swap function and that is way。

Better to use because it relies on the move semantics that are available SFC+ plus what I forget which one it is。

 one Z I't。嗯。So just make note of that， okay？All right， so as we analyze these algorithms。

 what is it that we're looking for？Okay well， obviously， we care about asymptotic complexity okay。

 and to save you the suspense。All these algorithms， the asymptotic complexity is， you know。

 on the worst case， is O events square， that's why we're calling them elementary sort okay。

But with sorting。嗯。Because we'd want to consider different kinds of inputs to the sort， right？

We might want to consider what happens with its algorithm in the average case right。

 so not just the worst case， but the average case and also to save you the suspense。

For elementary sorts， the average cases， for the most part。

 in runtime is still going to be O and squared， but there's still interesting situations that arise when you consider different。

Kinds of input to the sorting output。Furthermore， we care about whether it is a sort in place。

 which just means that you basically reuse the same array that you're given its input to do the sorting。

 you don't rely on an additional oh of in sizeized array to do the sorting。😡，Okay。😊。

So that's what so if you have to create， say call it an output array。

 then you're basically incurring O event space。In your algorithm。

Which means that it's not a sort in place， it's a sort out of place。Okay。😊。

Then there is the fact when we get to recursion， which we won't for the elementary sorts。

 but we will for the efficient sorts。嗯。When we do recursion。

 we need to consider what happens with the stack。And if you recall from your 280 right。

 there's tail recursion， if it's tell recursion， then we're all in good。

 but what happens if the algorithm cannot use tail recursion and we'll see examples of that。嗯。

Sorting in place， but have foreigners or indices right it basically comes from what I was mentioning earlier about。

诶。Indirect sort。阿们。And then we'll see an example。Specifically of a sort that uses omega extra memory。

 meaning the algorithm doesn't work。Unless you use extra space， okay， that's again。

 saving the suspense that's going to be merge short。 You might be like， oh， well。

 then why is me sort so good， Well， we'll talk about that later。Yeah， me sort。嗯。In fact， well。

 let me rephrase that because there are ways to implement MEse sort that does not use extra space but it's so convoluted。

 so hard to do it people don't do it right and plus for the specific cases that you want to use MES sort。

 it is considered okay to invest that extra memory。Um， so the mega tells me that I at least need。嗯。

Extra memory that's in the order of N。Okay， so additional desired qualities would be stability， okay。

 so stability basically means。That if you're looking to sort two things that have the same key。Okay。

😊，嗯。And you pass and they come out let's look at this by example。

 right because I have an example and this is much better to see。 it's actually not a hard concept。

 but it's easier to see by an example。 Let's say that we're looking to sort these names right here and we want to sort by last name So our key here。

 So each string is the first name and the last name。

 but the key that we're using to sort is by last name。 So the key is the last name。

 So we see that both Charlie Sheen and Martin Sheen have the same last name。Okay， so in our shorting。

 they would be considered。you know， same key right， so if they come out sorted。

 we know that our shorting algorithm are going to place them both next to each other because they have equal keys。

😡，But stability would mean that even if you play them next to each other。

 they should come out in the same order that they were given as input。

So an example of a stable output would be that because in the input。

 Charlie Sheen came before Martin Sheen， that's the same order in which you will see it in the output when you sort it。

😡，But then an example of an unstable sort would mean that there is a chance。

That Martin Sheen comes before Charlie Sheen。Okay， so， you know， if the algorithm does not guarantee。

The first case， then it's considered to be an unstable sorting algorithm。喂。Does that make sense。

 well， I guess I can。I kind of asked that usually in lecture。

 but it's hard to kind of gather feedback。While doing this。嗯。YouTube lectures。All right。

So types of sorting algorithm and we're often going to see this， there's an non adaptive sort which。

It means that it doesn't take advantage。Of a potential state of the input array。Okay。😊，So basically。

 all the sequence of operations is independent of the order of the data。😡，诶。Conversely。

 an adaptive sort might be able to perform better。If the input array is called somewhat sorted。😡。

Okay。😊，So。Or it's not necessarily that it's somewhat sorted is that it performs different sequences of operations depending on outcomes of comparisons right and one of the examples that we'll show is hey。

 would this algorithm behave better if the input array is somewhat sorted and again。

 I'm handwaving that right now， what do we mean by someone but will？

Definitely describe that in more detail。In the next couple of slides。

And then we have worst case versus best case。And here is one of the examples where actually thinking about a best case of an algorithm is quite useful right for most algorithms when you analyze base case。

 it doesn't really give you much information about the algorithm or its behavior。

 but it turns out that for sorting algorithms， specifically elementary sorts，😊，Considering well。

 not necessarily a best case， but something very close to a base case。

 which again would be that the input array is close to sorted。

Does change the behavior of the algorithm or the expectation of the behavior of the algorithm favorably？

So it's interesting to look at the best case as well。 Okay， all right。

 so on with our first elementary sort， which is bubble sort。Whi you've probably seen it before。

 I always find bubbles are interesting because if you told me like if I didn't know any sorting algorithm and you told me like write code。

 so implement an algorithm and write the code。😡，To sort an array of integers。

 and I didn't know any approach to sorting。I would never come up with bubble sort。

 I really don't know who came up with bubble sword。

It kind of does make sense once you play around with this algorithm。

 but I you know it it's not intuitive to me okay， and it's also one of the worst performing sorts。

 so it's kind of like somebody you know worked really hard to come up with bubble sort。Okay嗯。

So basically the way that this would work it， which is outlined here in the bullet points。

 find minimum element find minimum item or element on first pass by comparing adjacent items and swap item all the way to the left right so this so line2。

 the for loop pin line2 is basically saying for each item in the array。And then lines three，2， five。

 just say like。All right， I'm basically going to bubble down the element。😡。

That should be in the first position or the current position。Referd to go in the Iath position。

Of the array。That's basically what it's doing notice that the inner loop as opposed to the outer loop goes from right to left right so the outer loop goes left to right。

 the inner loop goes right to left。And then basically just comparing the IF element to the one。

 sorry， the JF element to the one that comes。Where J is the index of the interior loop。

And it's just comparing the element right next to it because it's J minus1， and if indeed it's lower。

 then I would swap right。Rinse repeat， right， The first iteration is going to put the smallest element in the first。

Slot in the array。And then the second iteration of the outer loop。

After it's done with all the inter loop iterations， it's going to place the second。

L smallest element into the second spot in the array。

 so on and so forth right so let's look at how this works。

 supposeuppose the input here is the same algorithm。 Suppose the input is right here，4，2，5。

 one and  three。That means that on the first pass。嗯。😊，It would pick， it doesn't specifically pick it。

 but it does so by way of the swaps that you have in that inner loop。

It will take the one and move it to the left all the way down to the first position。Okay。😊。

So then this is pass two and this is by pass here is pass of the outer loop， right so。So。Outer loop。

Pass one。Place it there， pass two will。YouBasically see the two and swap it as in the second position right here。

ok。😊，Then pass three。Okay。Pass four。And then at that point it' sorted。

 but if you go with the algorithm step by step， excuse me。Sorry， at past three。

 the algorithm is already sorted， but you see that。😡，The algorithm。

Would not be able to tell that that's the case and it will have to run through the fourth pass to figure out that it's moved everything in its place。

Okay， it's。So you can see that this last pass is always going to be quite wasteful。

 it's kind of it always has to invest one last iteration of the outer loop to determine that there's nothing else that needs swapping down。

 okay or swapping to the left。So this is a non adaptive。Bubble sword。Well， how can you fine tune it。

 well， we just talked about that， right， how about that last pass？

If I can avoid it by somehow detecting。嗯。That I no longer need to do any more passes than I can do that。

It can just break out of my outer loop。And。I'd be done。

So all I need is kind of this Boolean flag that just says whether during the execution of the inner loop。

I've actually done a swap right so if I've done a swap。

 then there's nothing I can do if I've done at least one swap， there's nothing I can do。

 I still need to go to the next pass okay。😡，But if I spent that one pass。

But never end up swapping anything， which would mean that the swapped bullolean would stay false。

 then I'm really done and I can just break。And呢。You know。That's that's a more adaptive bubble sort。

 right， because it's basically with this boolean flag is keeping track of the。The current state。

 if you will， of the array， right by just trying to figure out whether in a particular pass。

 we ended up having to update any of the elements in it。Okay。So bubble sort is you know。

 if you did the math is actually in the order of n squared over  two。

 but you that is that means it's bubble n squared。Okay。😊，come。

Notice that's the in terms of number of comparisons， right。

 in terms of number of times that I need to compare the elements in the array in terms of number of swabs。

Okay， if it were the best case， meaning。The input array is already sorted when you pass it to a bubble sort。

 then it'll be really fast。😡，Right。in terms of number of swaps。

 it won't need to do any swaps because it'll always detect that there's nothing to swap right the left element is always going to be less than the right element and so。

Never am I actually going to end up swapping。Okay。😊，Um。

Now that doesn't still means that you can end up doing roughly O n squared comparisons。

In the adaptive version。We still kind of arrive at an O n squared for runtime， but if it's。

If it's almost sorted or actually if it's the easiest way to see this， if again。

 if the input is an already sorted array， right？Then really。

 you just have to spend one pass to figure out that it's already sorted。

 which is a linear number of comparisons and then you'd be done。😡。

 so it'd be quite fast and also the number of swaps would be。

Roughly linear time if the array is almost sorted。And as few as zero， if again。

 the input array ends up being already sorted。I know that you're probably thinking well what does it mean that it's almost sorted。

 we'll get to that， but not quite yet just bear with me with the notion of having a somewhat sorted array。

Okay。So when we'll discuss that in a lot more detail when we go to insertion sort。

 which insertion sort is， you know， it kind of the better version of bubble sort。

Much better for action。All right， so advantages is very simple to implement。

 although I would argue that to me， insertion sort would be ways here to implement。

Complete some pre sorting while searching for a smallest key， it is stable， right。

 and sometimes that's important。Depending on the context of where you're using your sorting algorithm。

Okay， and then you have that version may finish quite quickly if the input is almost sort。

 So those are some of the advantages of if you thought that bubble sort。It's terrible， well。

 you know， there's some good things about it， although again。

Inserion and sort has those same good things。 and its's。Way better。

 So still what were sort is kind of a gimmicky algorithm that we。You know， teach。

 but we would never in practice use bubbles or for anything。disadvantageiss is an oh n squared time。

And it's quite slower than high performance sorts right or efficient sorts。

 so that's bubblebble sort。Let's move on to selection sort and probably this is where we' end for today and then pick up insertion sort on Tuesday。

Selection sort， again， going back to like if you told me。Go ahead and implement a sorting algorithm。

For this array of integers。I think that insertion search is probably the one that I would come up with。

 right， because insertion insert is the closest to。

If you're given you're playing cards and you're given like a hand of cards and you're told， hey。

 and I mean I do this， I don't know if you do it when you're playing cards。

 but I sometimes sort the cards that I have in my hand。

And the way that I do it is I look at my cards left or right and then say like all right。

 the lowest card in that I see in my hand is I don't know。

 the fifth one so I picked the fifth one and put it as my first one and then what's the next smallest one I don't know it's the seventh card that I have so I picked that one I put it as my second card in my hand。

That's basically selection， sort。So here's the algorithm and the code for it。It's basically。

The way to interpret it is like this for。Each。Spot。In a array。ok。😊，And all this does right here。

Is fine。Next， men。Value。That goes in that slot。And then。Place。Value。In slot。Basically。

 that's what it amounts to in pseudocode。Okay， and also you have the bullet points down there。

But I like kind of the more pseudoish explanation of what it does。

 you see the inner loop right lines four to well， it needs to include line three so lines three to six iss just a min function。

That just searches over the portion of the array。That still contains unsorted elements right so that's why if you see the inner loop starts at J where J is i plus1 right and then I is the current index of the outer loop。

😡，Okay， so that's what it amounts to。 So let's look at the example right with the same code。

 let's say the input is。诶。Right here。喂。Then we have pass one， what it will do is like， oh。

From this entire raid， find a min。Which is one。And then。Place it in that。First。Spot in the array。

Then pass two is going to say， all right， now I'm going to find the min from here to here。

And that man。Is two， so that's where I'm going to place it next。

And then now the next pass we'll look at this part of the array， determine that the min is three。

And so it will be placed here。Rinse and repeat until it's done。Okay， so that's selection sort。

 it's to me the most intuitive sort， to be honest。嗯。And。It has room for improvement。

 you can actually make it adaptive。Um by way of， hey。

 you know need to invest extra comparisons if I determine that I haven't found。U。

An element on the unsorted section of the array that is lower than the current element。

I don't need to do any swabs， so I just specifically avoid it right so if the main index that I found is different than the current slot that I'm at。

Then that's when I would swap， otherwise I don't swap。

 I basically have the men in its rightful position。Okay， so what does that mean。

 it means that it is quite adaptive。In that， in the worst case。嗯。

Is quite sensitive to input right if the array is almost shorted。

 it means you end up doing almost zero swaps， right， that's the adaptive version。诶。Um，Which is good。

Right。But still， in terms of number of comparisons。

 you have nested for loops where in the worst case。It's going to outer loop going to iterate n times。

 inner loop is going to iterate n times So you have。O of n squared。

If you care about doing the actual math， it's roughly a aroundund n squared divided by two。

 but again。Some ta， we just care about all n square。So that is selection short。

One particular advantage of selection short is that there's minimal copying of items。

 right you only move or swap things。Okay well， actually。

 there is a distinction between moving and swapping that we'll get to when we do insertion sort。

In terms of the copying of items that would be needed with each swap。Right。😊。

Because it minimizes the number of swabs that it needs to do。嗯。Again。

 if the element happens to be in its correct position relative to the rest of the elements in the array。

 I don't move it， right， I don't ever move it， that's not necessarily true with bubble sort or even some of the other sorts。

 in fact it's almost it's almost never true for the efficient sorts right you oftentimes even though elements might be in their correct position in the input。

😡，During the efficient sort algorithms， you do end up moving them about just by nature of the algorithms。

 but for something like selection sort， you wouldn't。Okay。😊，So it is fairly efficient for small N。

And this will be a running theme also for insertion sort right that when the array is small enough。

You'd rather do one of these elementary sources rather than using some of the efficient sorts and we'll talk about why。

But just。So you start thinking about it just because they're much simpler than the efficient sorts。

 if the array is small enough， you'd rather use a very simple sorting。

Algorithm rather than the more beefy， efficient ones， right？

So some of the disadvantages are that it is basically O of squared， in fact it is theta n squared。

 right， it means if you look at the loop， you know it's a tight bound on n squared。Runtime。

 it really only slightly changes。If the input is preored。But it does， right， and that's。

Better than bubble sort， for sure。诶。It。Runs about the same if it's already sorted array with all keys or equal randomly arranged array。

 but there are。嗯。If it's almost sorted， it does run a little bit better。

 but the one that shines when it's almost sorted will be insertion sort。

 that insertion sort does behave dramatically better if it's almost sorted。嗯。All right。

 and it's not a stable sorting algorithm。Okay， so that's particularly important。哭。ItActually。

 let me ask this question and we'll probably end with this。Why is selection sort not stable？

And Ill's see if。Anybody want to answer why is selection sort not stable？

And you can figure this out by looking at the code。And I'll give it a minute。

 see if anyone has an answer。Because it is swapping things， no， not。It has to do with swapping。Well。

 actually no。啊。does not have to do with swapping。It does have to do with kind of the code。

That decides when it will。Swab， which is basically that min function。 all right。

 so let's just go over it because you know。Exercises with these， like， YouTube lectures。

I'm not very yet。Pretious。Let's go today。This min function right here。

 which is I call it a min function， but it's just because really these statements all they're doing is computing the next min that should go in that slot。

 right？s。If。嗯。If two elements are equal。Correct， I think Aru just alluded to this。Yep。

 it depends on the implementation of the fine min part that are lines four。

 five and6 right if two elements are both the minimum。

 there's no assurance right that the one that was to the left will come out in that same order。

 it just depends on what that min function sees first。

 that's the one that's going to move to that position right？嗯。

Let see if there are two elements with the same key， the second one would be selected as the minimal。

 so the order of equal key elements would be flipped。 Yep， that's exactly correct， Elliot， thank you。

All right， so that's why selection sort would not be。嗯。Sttable。All right。

 so so far we've discussed bubble sort and selection sort， which are both O and squared。

 the next one that we'll discuss is insertion sort。Whi is also asymptotically slow。

 but there are a ton more opportunities for TY to the point where there are situations in which you'd want to use insertion sort In fact。

 at one of our earlier lectures you heard me allude to intro sort。

 which is short for introspective sort， which is what STL really uses behind the scenes of the sort algorithm。

It basically has and we'll go over any more details later。

 but basically it just picks which sorting algorithm to use behind the scenes。

 that's why it's called intro sort。😡，And one of the things that it checks is whether the array is small enough or is almost sorted。

 and if that's the case， it actually uses，Insertion sort rather than quick sort。

Okay so that's an example of how useful。Insertions or can be。Okay， so I'll just。

knowS you a brief glance of the insertion sort code and of course we'll continue in the next lecture。

 that's insertion sort and you look at it， it's quite similar to bubble sort。Okay， accept that。

I believe the。Outer loop。I exactly the same。I think so yes。but if not。

 it's very close to being the same like maybe in the scene is a little bit different。

 but but the big difference here is。They inner for loop。Right this one goes。

Notice that this one iterates over the。Part of the array that's already sorted。Okay。

 bubble sort that inner loop would iterate over the portion of the array that was not sorted。Okay。

In insertion sort， the inner loops iterating over the part of the array that's already sorted。Okay。

So at all times with insertion sort， you will have the portion of the array that's sorted。

 portion of the array that's not sorted。And all it's going to be doing is look at the next element or the leftmost element in the unsorted section。

And then swap it or bubble it down to its rightful position in the already sorted。

Section of the array。that's what it's doing， so that goes to move items one at a time from unsorted to sorted inserting each into its proper place。

Okay。😊，So at every iteration， the sorted section grows by one， the unsorted section decreases by one。

 right because I've moved one of the elements from the unsorted section into the sorted section in its proper place。

诶。😊，This current version that you have in the slides is not adaptive。

This is where we'll start on Tuesday， I will start with adaptive versions of insertion sort。

That's all for today， I think finished。Right on time。

 I glad we covered at least the beginning of insertion sort。All right remember project two is out。

 I've had folks in office hours so it seems folks are starting early which is good right always refer to the lecture on HeEaps。

 it'll help you a lot for implementing the binary he basically because we give you all the code。

 you just need to adapt it to the syntax for the project okay but the concepts are all there。Okay。

And then of course， you have sixthth versus Jedi so you know。That's great whenever you have。嗯。

We tried to fit a reference to Rogu and Amandalorium。

 but we couldn't do that for the we just left it of Jedi and set。All right。

Catch you all Tuesday have a great weekend， stay warm I you know it's really cold in my basement even though we'll have a space heat right next to me if you're in Texas then。

Hope everything gets better soon and know it's stuff all right， take care， I have a great。

Evening and weekenden， everyone。