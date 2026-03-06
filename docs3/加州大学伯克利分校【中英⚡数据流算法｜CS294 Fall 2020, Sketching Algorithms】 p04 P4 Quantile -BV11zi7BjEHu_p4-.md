# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p04 P4 Quantile -BV11zi7BjEHu_p4-

![](img/d4a509324399607834dd917a6ca8ec99_0.png)

Hey hellello， everybody。I did promise myself and you all that I would start not on Berkeley time。

 but five minutes past， given that people don't have to。Commute far anymore， so let's get started。嗯。

I did want to talk about lower bounds， but before we talk about that。

 I want to present one more thing that's sort of related to accounting。Another algorithm。

 and then we'll start talking about lower bounds。So the next next maybe took this lecture and the following lecture。

One is quantiles。This is also known as like an approximate rank and select。

And then I want to talk about lower downs。And when we talk about lower bounds。

 we'll talk about we'll do it for both quantiles as well as distinct elements。

And you'll see some commonlogy in the and the techniques that we use and we're going to lower bounds are going to actually mean recur actually throughout the semester。

 so this will be the first。Introduction to them， but well keep talking about ways of improving them。

So let's start off with quantiles。So what's the setup， Okay， so we see a stream。Of comparable。



![](img/d4a509324399607834dd917a6ca8ec99_2.png)

Items。Oh I forgot to。I have two Wifi networks and I forgot to put my iPad on the more stable one just give me one second while I fix that。

嗯。

![](img/d4a509324399607834dd917a6ca8ec99_4.png)

Good， we're back。Okay， so this should be stable so we're going to talk about quantiles first。

 so we have a stream of comparable items。You can think that they're integers from some universe1 to U。

 or you can think they're strings or whatever other comparable。And。We want to know what we want to。

We want to answer。You know， the following kinds of queries。嗯。It's a rank。Of x。

And let's say we see a stream of n comparable items， n is the length of the stream。No。What is。

The rank。Of x in the sorted。Order。Of all the stream items seen。So for example， if our stream。

our our stream of course， might not come in sorted order。

 so our stream looks like you know we see three， then we see three again then we see5，1，17，4 right。

And then now， you know， imagine sorting it， of course， we don't。

We're trying to use low memory here so we don't have room to store the whole sorted order。

 but sorted this would look like。1，3，3，4，5，17。And then if someone says， you know， they want a query。

Rannk of。Of let's say six。The question is， if six were in this list。

 what would the sorted order of it be and the answer is well it would be right here。

 which is position number one， two， three，4，5， okay so it's also six。Okay， if someone queried rank。

If someone periodod rank， let'd say。Have of 18。Then I guess we would say that should be eight， right？

One， two， three， four， five，0， seven。18 would be here， that's position eight。Position 7。对。

So that's rank。And select。Select here takes as position， I mean。

 takes as input some integer n between one and n， some integer R between one and n and returns。嗯。

An element。Of rank。Are in this sorted order。Okay。Now， as you might imagine， these problems are hard。

Um， so we'reel for some approximate version if we wanted to get away with low memory。

 hard in the sense of， you know， in terms of the memory conception。

 it's hard to get something that's similar linear your memory。

So the way we're going to settle for approximation is as follows。For rank。

 we're going to be willing to return the rank of x plus or minus an additive error term of epsilon times n。

Okay。Epsilon is some parameter that's given up front。Before the stream starts。And similarly。

 for select， it's going to return an element of rank R。Paulse or minus epsilon n。

 So the element that's returned is not necessarily going to have rank exactly R just to rank approximately R in this additive sense。

对。Notice that we're not returning an approximation of the value。Of the number at rank。

 let's say it's their numbers we're not returning an approximation of the number that has that rank。

We're just returning something that approximately has that rank。Okay， so for example。

 if the stream looked like。One， two， three， and then a billion。A billion here has rank four。

RightBut I'm allowed to return， even in the non approximate version。If someone says select 4。

 I am allowed to return 4 or 5 or 6， or basically anything that would have rank four in the sorted order。

 it doesn't have to be。Close to the to the number a billion。 Okay。

 so we're just trying to approximate the rank， not the actual number that has that rank in the stream。

 if that makes sense。So if you return for in this case would that be like correct that would be exactly that be exactly correct Okay yeah that would not be an approximateimate answer that would be an exactly correct answer and then for the bounds would it would be inclusive at the endpoints including three and a billion to be correct sorry say one more time Yeah for the bounds could returning anywhere from including three to including a billion be correct。

Well， like if you return three， that would also be that would also be exactly correct， Yeah， Okay。

 and then turning a billion， be correct， too， Yes， I'd be correct， Okay。

 anything between three and a billion would be exactly correct。

So there's been a lot of could you restate the error condition for rank？Yeah二。So。

You so you know X has some true rank in the sorted order I mean okay。

 so it might be so plus minus epsilent is added to the rank of whatever Yes that's right that's right and you know like in this example there are multiple items that have the same value three。

So you know it's correct， even in the exact even even in the exact problem it's correct to say that the rank of three is either two or three because it's both the second smallest and the third smallest either of those is an acceptable answer and rank needs to be returned the correct thing not just on elements that have appeared in the stream but on other elements as well that's right the query the query X here need not be something that appeared in the stream。

呃。Okay， sorry Gelani yeah， so so if you get like 10 threes and then five， for example。

 and you asked for the rank of five， it would be 11 maybe 11 that's right Okay。

 and if you ask for the rank of three it could be anything between anything between one and 10 would be a perfectly exact answer okay。

Okay， good。U so。There's been a lot of work on this problem and this is actually I would say one of the streaming problems that is for which algorithms are widely used in practice okay distinct elements is another one you know there's this algorithm hyperlo log that is used all over the place in industry algorithms for for quantiles are similar in fact if I share my screen。

Yeah， so if you go to this， this is kind of one of the。嗯。

One very popular open source library for the implementation of various sketching algorithms and one of the things that they that they implemented is a version of the KLL sketch from it's actually a very new algorithm it's from 2016。

 it's a randomized sketching algorithm for the quantntiles problem。

That uses O of one of's long words of memory for this。

 for the problem that I told you just now on the whiteboard and actually。

 the dependence on the failure probably is also very good。 It's log log whenever Delta。

 So one interrupts on log log whenever Delta。Although the version that they implemented uses a little more space in the theory sense in the Big O sense。

 but you know。Getting the exact optimal right space in biggo notation leads to some impracticities。

 which。You'll get a sense of why as we go throughout lecture and explain how these algorithms work。

So it's connected with everywhere。Okay。So。There's a natural lower bound。For let's say。

 comparison based algorithms。Yeah。Comparison based， what does it mean， it means that。

What you're storing in your memory is a subset actually I'll use a definition that is from a paper of Cormo and Valli actually this year essentially what it means is you're storing a subset of the items that you saw。

Okay。And whenever you see another item， you're allowed to do equality tests with things in memory and also comparisons。

And you know， based on that， you're allowed to store。嗯。I think。Some auxiliary metadata like。

 you know， the result， you' you're allowed to even store the results of all comparisons you've seen for free。

But at the end， you're only allowed to store， you know。

 so you have basically two parts up to your memory， one part is storing a subset of items。

 k items okay， where K is like your memory footprint and the other part of your memory is allowed to store the results of comparisons with things you've seen before in the stream。

 comparisons and equality tests。Okay。嗯。And they said that， you know。

 even in this model where that other part of your memory is allowed to store quite a lot of stuff。

 that you still have a lower bound where k， just the number of items you store has to be at least one of epsilon。

嗯。So。A lower bound。And one of our epsilon。Words。For any deterministic comparison based algorithm。

And also in this model， whatever you answer a query。嗯。

What you're allowed to do is you're allowed to look at。

 you're allowed to compare the query item to all the items in the stream or to all the items that you're storing these K items and you're also allowed to look at the metadata。

But I mean， essentially the lower bound is somewhat trivial and why does it come。

 it comes because imagine you take the KIs that you're storing， let's say you're storing Z1。

 Z2 up to ZK。And you're storing them in an arbitrary。

You're starting them and let's say this is the sorted order of those items。Right， so。

If if you're not so basically the point is。There are N items you saw on the stream。

 you're only storing K。 So in this sort of order。 and let's as a hard instance。

 we're only going to give items that in the stream that are different。

 we're never going to give duplicate items。Which means you know all the items that are missing here that you didn't store。

 there's basically， there's some ZI and ZI plus one。😡，Wherere the gap between them。Ha size， this gap。

Has size at least and a roquet。Right。So if you have a deterministic algorithm。

 then the only thing that it's allowed to do to answer queries is do comparisons。

Then any item that it's queried that's in this range is going to have the same exact answer because all the comparisons to the items you're storing are the same。

😡，Right。And if this gap is too big， then you know that you're not allowed to give the same answer to everything in that range in particular。

 if the gap， let's say the gap is bigger than。嗯。You know， well， actually。

If the gap is bigger than say Epsilon times N。Right。Then that means that。

The thing that's immediately after。ZI that you saw on the stream versus thing that's immediately before ZI+1 in the stream are getting the same answer。

嗯。But these things are more than epsilon and apart from each other。Okay， so therefore。

 one of the answers is wrong。 It's not an additive epsilon and approximation。

 So this basically implies。就日家。So I want to say the gap is bigger than Epsilon N unless less。嗯。

K is bigger than whatever esilon。So this is a lower bound for comparison based algorithms。

kindind of more recently， actually， this paper is just from this year。There's a paper by core mode。

And Vai， more stated， you can go read it' it's a 20 page paper I'm not going to cover to court in the course。

嗯。But they show that actually there's a lower bound of omega one over epsilon log of Epsilon n words。

For comparison based algorithms。And this， by the way， is optimal， there was an algorithm from 2001。

Which actually achieved this bound。So they got the actual type。

 the type bound for deterministic algorithms。That are comparison based。And there are algorithms。

 as we'll see today， which are neither comparison based nor deterministic， so you know it's not。

And that's not to say you can't beat this bound， but to beat this bound。

 you cannot be both deterministic and comparison based。嗯。

So let's say let's see first some deterministic algorithms for this problem。Yeah。

The optimal algorithm。Is due to Greenwald and Kaana。In 2001 and as I mentioned。

 it achieves the same bound in Corormo and Vascei's lower bound。

 one of Epsilon times log of Epsilon N。Words。I had this plan of。Covering this algorithm today。

But you know， as I was。Unfortunately， you know， as I was you know reviewing the the algorithm details more I realized it's it's quite complicated there are a lot of just。

Details that。It would take probably on the order of two lectures just to cover this algorithm in full。

 so i'm not going to cover this algorithm， but I will cover algorithms that do decently。

Like for example， instead of log Epsilon N， log squared of Epsilon N。

 one on log squared of Epsilon N。嗯。And kind of actually an open problem。That was posed by core mode。

If anyone's looking for project ideas。Come up。With a simpler。Optimmal algorithm。

So we already know the optimal bound。This is that unfortunately it's kind of complicated to get it。

The algorithm is actually not too complicated， maybe at the end of lecture if I have time。

 I'll try to tell you what the algorithm is。😡，It's just that the it's a funny algorithm where when you see the algorithm just by construction。

 the algorithm is like obviously correct。What's tricky is bounding the memory consumption of the algorithm。

 not it's not at all obvious from seeing the algorithm that is low memory。You know。

 it wants to store basically the whole stream， but it has some pruning procedure that it does periodically to trim down what it's storing and that pruning procedure is designed in such a way that you guarantee correctness。

But if you want to prove that you're using low memory。

 you have to prove that no matter what the string looks like。

 the prune operation will cut out a lot of stuff。And that's the part that's not so obvious as to why that's true。

嗯。So。I you I will show you two determinacy algorithms today， one is called the Q digest algorithm。

And this algorithm is from 2004。This is due to。处八死啦。嗯。

I'm going to let me not say this name because I'm probably going to say it wrong。

Agerwell and Surreri。And actually is not this is not a comparison based algorithm。It assumes。

That the stream values。Our integers between one and U。U as the universe size。

Oh and you know I meant to say when we started off。

 you know I showed you this webage from data sketchtes that the implemented quantiles。

 why is quantile so useful in practice， I think you know a lot of the applications of quantiles in the real world are you can imagine you built some system。

And you want to understand its performance， you know， at the tails， I want to say like 99。

9% of the queries that are made to my system are served within you know， 100 milliseconds。Right。

 so that's exactly quantiles that's quantiles at the ends right where basically I'm asking about R。

Being I want to make sure that kind of the vast majority of users don't have a bad experience。

 It's the pro the chance that you'll have a bad experience using my system is like 。

1% or maybe even even less。 So basically， I have this stream of people making queries to my system。

I can see how long it takes for my system to process the query and spit out an answer and you know basically these response times are coming now at a streaming fashion and then whoever is analyzing my system maybe the person who built it。

doing some performance tests wants to make sure that。You know， the 99。

9 percentile response time is not too slow。Right， so you see a lot of。

Kind of applications in industry that are of that flavor。

 which is why it's a popular popular data structure。

Now let's get back can you beat this lower bound in practice if all you care about are。

Like rank queries at those tails toward the sales so so actually there's there's some recent research。

 you know， as recent as this year on instead of additive error quantiles。

 what they call relative error quantiles。Um， basicallys， you know。

 I don't want the rank error up to additive Epsilon N。So I want it instead up to additive Epsilon R。

 where R is the rank that's being queried。😡，And you know， as I said it。

R was very large right R was almost n。 it was 0。999 n but that's basically you know R very large is equivalent to R very small because you could just use the reverse comparator right the reverse sort So basically that what I'm saying is I want my errors to be much better when I'm  queryering things at the tails and in fact。

There are data structures， even new ones that can do something in that space。

 but they're probably not optimal， so getting an optimal such data structure is an open problem。

こ嗯 yeah。O。嗯。So yeah the Q digest， is this is one that's not comparison based。

 Greenwallald Canaw is comparison based， this is not comparison based that assumes that the values that I'm seeing in the stream are integers between one and U。

And I'll explain this algorithm and then I'll explain one more that is comparison based。

 and then I'll tell you about randomized algorithms and then we can talk a little bit about lower bones。

For quantiles and then four distinct elements， if you have time or maybe that will carry into Monday day。

Okay， so this is a very simple data structure， how does it work it is deter deterministic The idea is you build a perfect binary tree over the universe so。

Let me try to do that here。So this corresponds to universal element  one， two， three。Up to you。

And now there's， as I said， there's a tree that you're building over this。et cetera。

 and you there's some root up here。So this is a tree of I log U。Okay。

 and what I'd like to do is I'd like to just store， you know。For every node in here。

 I'd like to store a counter。😡，And that counter is it corresponds to。

 you know how many elements have I seen？In that in that range of。Of the universe space。 So right。

 so for example， this node right here。嗯。Corsponds to the range from one to two。

But I'm not going to store an item in multiple places I'm not going to count an item in multiple places。

 an item is only going to be counted by one node。😡，Okay， ideally I'd like to count it at the leaves。

 but sometimes， you know I can't afford to store counters for every leaf because that would be you counters it's too much memory。

 So at some point， you know， for some items， I'm going to choose to instead store them at higher levels and I'll do it in such a way that。

The number of nodes that I need to keep track of at any given time is small。Okay。

 and I'm only going to keep track memory of the non zero counters。

 and I'm going to basically do this in such a way that I can prove to you that the number of non zero counters will be small。

So。Bas you know， so the picture you shot in mind。Is。You know let's say I see。

 I see in the stream one，1，3，1，1， you know， then what the picture should look like is。

Three we'll have a one in it。One will have a four in it because I saw it four times and then all the others will have zeros in it。

嗯。But of course， as I have longer streams that have more distinct items in them。

 a lot of the counters are going to start becoming non zero。

 I can't afford to store so many non zero counters， what do I do？So I'll have a rule for myself。Okay。

So first of all， I'm going to say that， you know， Cx。Is the counter？That corresponds to node X。

And then。And say P of x。Is the parent， the parent of X。And this S of x is a sibling。

Everyone has a sibling except for the root。So what's the rule？The rule is going to be that。If。嗯。

The counter of x。Plus， the counter of the parent of X。Plus， the counter of the sibling of X。

If that's at most。Epsilon n over log base two of U。Then。All set。The counter X。To zero。

 I'll set the counter of the sibling of x， well， actually I should do it in the reverse。

 I should do in the other order， shouldn't I I want it to be valid to be actually correct。Basically。

 I'm just going to add the children to the parent， that's what I'm going to do。

So I'm going to say the counter of the parent。It getss incremented by。

The counter of x and the counter of its sibling。And then I'm going to set the counter of x to0。

And I'm going to set the counter of the sibling of x to 0。

So this is what I mean by items willll only be， you know， be kept track of in one node because。

 you know， originally in the beginning， you know， whenever I see a node in the stream or whenever I see an element in the stream。

 it's going to be kept track of in the corresponding leaf。

But eventually it might leave the leaf and get merged up into the parent and then maybe eventually the parent itself and its sibling will get mergergd into its parent。

 etcter。嗯。O。Actually， not eventually， but right away。Okay。Illiot right away moved up actually to the。

嗯。I one quick question for this plus equals。 Why is it up plus equals instead of just an assign。

 Is there a case where the parent is not empty and and then we can kind of do this like。

Push up that multiple times。嗯。Where the parent is not well。

Or because I'm thinking like once like go to the parent once， we'll never go to those children again。

Once you go to the parent， well at some point， though， the parent can。嗯。Become full， right， Oh。

 and then itll like go up。 and then you can do like the leak node as it again。Yeah。

 actually give me just one second， of course。Al， so can you ask your question more time。 Yeah， yeah。

 So I'm saying like， okay， so I'm actually okay， we put our values in the leaf nodes。

 and then after they get so big， they go up to the parent node。Yeah。

 so I guess I shouldn't have said so big， right it's it's the。

Immediate it's it immediately go up right because okay you basically apply the rule when whenever you can right so the point is in the beginning everything is small。

Right， so， you know， everything is zero in the very beginning of the stream so you you know basically immediately everything will just get pushed up to the root。

Oh， okay， okay， right， But you know at something you can think later in the stream。

 the only reason that I'm not。Yeah， basically things start getting full from the top down if that makes sense。

 Oh gosh， Okay， I had the different image of my mind。 Yeah， things， yeah。

 so basically the root gets full then some of its children might start getting full then some of its children might start getting full。

 et cetera。Does that make sense？Yep。Okay。🤧。Okay， so so basically just apply this rule whenever you can。

 that's the algorithm。嗯嗯。So now the claim that's。Oops what happened to my pen。Plae one。Number of。

 let's say， nodes。X with non zero counter。Is at most three log U over Epsilon？And remember。

 we're only going to store the ones that have a non zero counter right and so basically for each node that we store。

 we're going to remember the counter value as well as like which node it is in the tree。

So the proof of this。Is。You know， if we sum over。If we sum over all you。Such that C of X， C of O U。

Is not zero。Of。C of U plus C of。Sibling of you。Plus C of the parent of you。And other than the root。

What can we because the root doesn't have a sibling a parent， What can we say you can say that this。

This is bigger than Epsilon N over log U。Times k。We're here by， you know， K is basically。

The number of such you。On the other hand， we know that what is the sum of C over all U in the tree。

 that's N， right？Because each element is kept track of in some node and each node in the stream contract contributes to the count of exactly one node in the tree。

Initially the leaf， but it might get pushed up higher in the tree。Okay。

 so we know that the sum over all U of C is n。😡，And in this sum that we have here。

 each node U appears at most three times because， you know， it's you once right。

 it's you at most once。😡，It's a sibling to exactly one node in the tree and it's the parent to exactly one node in the tree or right most one for some it's zero if it's a leaf。

So this year is at most3N。So you just move this around， this implies that K is at most three log U。

Overover Epsilon。So this says that we're not storing that much stuff。嗯。And then， you。

 why does rank have error Epsilon N？This is also。其首。In the next plane。Is that rank？Of X has error。

At most。I'm slide in。And that's also quite simple， just you know look at the tree。

 so here's the tree。We have some query R， maybe this is R。So just look at the leaf root path of R。

Okay。You know， just thinking about the ideal picture。

 the ideal picture is that like nothing ever got moved to the parents we just have all the information in the leaves if all the counters were just in the leaves we would know the rank of R exactly right it would just be the sum of all the guys here。

ok。The problem is that some stuff got pushed up the tree in particular got pushed up to some of the ancestors of R so now there's some maybe you know from here there's some mass in this counter。

 there's also some stuff in this counter， there's also some stuff in this counter that came from things。

 some of them might have come from things less than R。

 some of them might have came from things bigger than R right in particular here there's some mass that could come from things bigger than R。

😡，So basically the problem is in all the counters that are above R。😡。

There are all these items that are being counted and we don't necessarily know are they less than are they less than the query。

 oh sorry， this is x not R X， we're querying x for its rank。😡。

So all these things in the root to leaf path， all these other counters， we don't know the items。

 the stream items that contributed to those counters were they less than x or were they bigger than x right so they basically contribute to the error。

😡，And。Each counter， you know， how many items does it have participating in it at most Epsilon and over log U？

😡，So the total error。Is the sub over V in the root to leaf？let's say。To leaf。Half of x。

Of the counter V。Which is at most Epsilon n over log U times there are log U such Vs。

 so this is at most Epsilon n。Okay， so that's it， so this is a very simple data structure。

And I will keep sprinkling open problems open。Prove in omega。W over uppsilon log you。Marbound。No。

 this is in words， right？Or come up with a better algorithm。So， you know。

 we don't actually know an algorithm that's better in the model where you actually know that the stream elements are integers from one to U。

😡，We don't have an algorithm， a deterministic algorithm that's better than Q digest。

 and it's been now what 16 years and we don't have a lower bound showing that this is the best you can do。

Okay， so that's Q digest now let me give you another algorithm that actually is comparison based any questions about Q digest。

So algorithm 2。And this is due to Monu。R to goon。And， Lindsay。In 98。Okay。嗯。We're going to get space。

 which is。So this is write deterministic and comparison based。It'seristic。Comparison based。

And the memory usage is one of Epsilon times log squared of Epsilon n。Words， and memory。

So what's the idea of this algorithm？It uses something that actually is used in the optimal randomized algorithm as well。

 which is the notion of a compactor。And it uses a chain of compactors and I'll describe what this means shortly。

Okay， so here it has log。Base two of Annaque。Compactors。And the number of compactors here， mean。

 the size of a compactor is k， a compactor just stores a subset of items。

So we willll store our up to K items。And here is the idea， so let's let's also give these also。

Numbers， which is。Let's say this is compactor number zero， one， two up to。Log of N K 1。

When you see an item in the stream， what do you do， you put it in compactor zero。😡。

So compactor zero will slowly start to fill up。And then now it's full， Okay， so what do you do？

You sort these items。😡，And then you promote， let's say， every other item to the next compactor。

 So all the items at odd indices， let's say so this is full Now you sort them。

 you send every other item to the next compactor。 so the next compactor now becomes half full。😡，哎。

And then you empty out this compactor。So this is empty again， it's ready to receive items。

And then it's going to slowly fill up again。And then now it empties out into the next compactor again。

 so now it goes here。Now this compactor is full so that it promotes every other it sorts itself。

 and then it promotes every other item into the next compactor as well。

 so now this compactor becomes half full。Et cetera， and then this gets emptied out。

And this also gets emed out。嗯。So that's it， that's what you store。唔。

And then I have to tell you how do you answer queries？😡，And。How do I set K to get error epsilon？😡。

And basically that's going to that's going to show up that's going to give us the bound that we told you so what is the space bound here。

 by the way， the space， of course。Is， I guess， K。Times。Mg。Of N。And as you， I guess。

 can probably guess。We will set。Eventually K to be of。One over Epsilon log of Epsilon N。

And that's going to lead to the space bound。J。So。嗯。

how do you answer queries and how do you analyze the error？So answering queries。Okay。

 so the picture you should have in mind is the following。 So let's say that the stream。

The stream has the following， you know sorted order。Of course， it didn't come sorted。

 but let's just say that this is what the items look like if they are sorted。

And then we have some query X and we want to know its rank。😡，Check。Now。Some of the， you know。

 not all these items that are less than it are actually being stored in the compactors。

 some of them got tossed out because we only promoted every other element。😡，So let's you know。

 let's box the elements that we're actually storing， so maybe we're storing this one。

And we're also storing maybe that one and that one。Yeah。Now。

These items are living in different compactors right some are living in compactor0 compactor one compactor 2。

 Why it mean that it's living in compactor one， let's say。😡，Not compactor zero。Compactor one。

 what are those items remember， you know we had。In compactor one， we had our k items。

 let's say K is six right now。And we only promoted every other item。Right。

 I can basically imagine that what's real what this really means is。

You know we basically are like merging these two items as one item so like this item that is boxed is like the representative for both items。

😡，That makes sense， but we're only going to store the representatives。Okay， so if you want， you know。

 if you want to think about it， you can think that there's the。

 there are these other items that kind of live inside the representative。As well。

And then maybe actually we had more items here。So we have more here。

And then eventually this level gets compacted into level two。

And then the picture there is basically now。We only store again the representatives。

But there are these other items that were there。I'm sorry， right。So。So basically the thing is。

You know all these items， all these items that aren't stored， they're， you know。

 it's because they're representative somewhere。这。Some of them might be representatives on the other side。

So there are a bunch of representatives in here。Yeah。嗯。Right。So嗯。

This is basically the source of the error because these things that are being kind of merged in。

 we don' we don't actually know how they compare with X。😡。

might they might be less than x or they might actually be bigger than x。

 but they got merged on the wrong side so we're confused。😡，Okay。Or。

 if you want to think about this happening and， you know。

If you want to follow the compactions in real time just in the analysis。

 imagine all these black dots are the stream。And then whenever there are some compactions。You know。

 some of the thing， there's some there's some mergings happening into these boxes。

And there's some error that could be introduced because。嗯。

Someone who was on the left side of x might have gotten merged onto the right side or someone who was on the right side might have gotten merged into someone on the left side。

 and that introduces error。😡，Does that make sense？So to answer a query。Think of x will return。

The sum over J goes from， let's say zero to。Log of N overK minus1。

 this is the number of compactors we have。The subover。Why。In compactor J。Such that。

Y is less than or equal to x。Of。Two to the J。Right because this item Y represents two to the J items right。

 it's a representative of two to the J items。😡，And you know， we're hoping that。

These two to the J items are。All correctly less than equals x。

 but of course we might have had some error because people got moved from the other side。Ored out。嗯。

So yeah， so the compactions， I mean we reduce memory， but。Naturally， as you can see。

 there's error that's introduced from compaction。So this is the same thing as basically。嗯。Yeah， so。

 that's that's we're returning from， that's what we're returning from rank。So now what's the error？

Well。Each compaction。At level J。When I say at level J， basically what I mean is into level J。

Into level J introduces。An error。Of at most two to the J minus1。Right。嗯。你看。Any questions about this？

Because again， you have a compaction， so let's just look at compacting into level one。

So these are the items I'm compacting。You know， here's my query X。And when I compact， you know。

 these two， you know， I sort before I compact so you know， these two get merged。

And then this is the representative。These two get merged and this is representative and then these two get merged。

 and then， you know， this is the representative。 So actually in this case。

 there's no error that's introduced。 You know， there were four elements that were smaller than me。

And they each counted as one element now there are two elements。

 two meta elements that are smaller than me and they each count as two elements。

 so I'll still think that there are four smaller than me。😡。

I guess the bad case is what if instead of that， what instead of X being there？

You actually had Xing here。😡，Kind of in between two elements that got compact two elements that got merged together。

😡，Now。In level one， I'm only going to see one merged element less than me， right。

 The representative from the second merge element is actually bigger than me。

 so I'm not going to count him。Right， so there's basically this kind of one merge merge that's happening at the boundary that includes x。

 which is going to create error。😡，Right。So here I'm going to be off by one。

 I'm going to miss this one element that's lost than me， but you know， at higher levels。😡。

One element that I'm missing actually has weight2 to the J。at level J， it has weight two to the J。

 so it's going to introduce this error of two to the j minus1。Okay。

So every compaction that happens introduces an error of either zero or two to the j minus1。

 so it's at most two to the J minus1。I have a question about these compactions。Yeah。

 so like it seems kind of like this like kind like bit increasing behavior where like at certain points。

 like it kind of could like send all the compactions to the end。

If like the first five of your are half full。And you fill up the first one。 Yeah。

 it will play together。 That's right。 Yeah， and then I'm wondering is like。

Is after this like big chain happens like if you a  query like right before versus like right after。

 is it a lot more coarse right after this big chain and have like maybe like with the air bound its the same。

 But like what。Have I just like。Worse rank approximation。

 like after a big chain versus like right before， like this like big training happens。

Oh you're saying is the quality of your approximation better at sometimes than others that yeah。

 yeah with this like specifically with this like big chains like if I like half full of my first five versus it all kind of gets propagated to my sixth compactor。

嗯。y， so i mean yes稣。Our error bound is going to be precisely even the following thing。

 which is going to be， which is going to be the error all I can say is that the error is at most basically。

The sum over J goes from zero to like， let's say this is the highest level compactor of the number of compactions。

Into level J。Times2 the j minus1 right so that's all I can say。Now， I mean， I guess looking at。

Looking at the state of the data structure and knowing which things are empty and which are half full。

😡，I can infer， I guess。画面。🎼I can infer then what N is， right， how many things there been。

 how many insert there been。 And I basically know how many that implies the number of compactions at every level。

系嗯嗯嗯， ok。 for example， if the very last if the very last level。

Compactctor that has anything in it at all is level L。Then， you know， and it's half full。

 I know that there was one compaction， exactly one compaction at level L minus one。Right。

And then based on whether based on whether level L minus1 is currently empty or halfle。

That can also tell me you how many compactions there were there therefore at level L minus two。

 et cetera。But I mean， I'm going to give a bound on this right now。

 which is equivalent to that so maybe let's。Let me just write this down Okay。

 so does everyone understand now why I'm writing this？Does make sense？Okay。So。

What's a bound on the number of compactions into level J？Well。🤧。嗯。So think about it like this。

 whenever there's a compaction at level J。That means that it got filled up to K items。Okay， and。

Oh yes， actually let me say this。How many compactions could there ever be from level zero into level one？

😡，OkayWell， every time you compact。You throw out K items right half of them get promoted to the next level。

 but you had K items and now you get rid of it， you flush them all out， you flush out K items。😡。

How many items are in the stream n right so there n items you're flushing out k at a time。

 how many compactions are there out level zero into level one at most and over k？😡，Right。Similarly。

 if you're at level J。And you compact if you got level J minus1 and you're compacting into level J。

Okay， well。When you wheneverever you flush items out of level J minus1， there are k of these items。

But each one of those items actually represents two to the J minus one items， right？So。You know。

 the number of the number of items。The number of items that can ever appear。

 right the number of items。Ever living。Incompactor J。Comp factoror J minus-1 is at most。

And over two to the J minus1。Right， because each item that lives there actually represents two to the J minus1 items。

And there are only n items total。So this implies。Now the number of compactions from level J minus1 into level J。

Is at most。And over2 to the J -1 over k。 So there's a K in the denominator。唔。

So all that means basically is this is this。That's this thing right here。

It's n over2 to j minus1 times k， so thes the two of the j minus1 is just basically canceled。

And then this become， this is at most。N H over k and H is log n over K。N log N overquet。Overk。Right。

 and I want this to be at most Epsilon end。So if you solve that， if you solve， you know you want。

En over K log of n over K。To be less than equal goes to Epsilon N。

You'll get that K is then the solution to this is based up a constant factor。

 what of Epsilon log of Epsilon in。And that gives you exactly the bound that I promised to you。Yeah。

 seeing， seeing the this helps。Okay。Any other questions？Okay。

 so now let me talk about randomized algorithms。嗯。Oh and I did mention， of course， keep in mind。

We do we do know what the optimal bound is for comparison based algorithms， and that's this one。

hi i one night。Do today。So basically， what I just showed you now is within a log factor of this instead of log gets loggged squared。

 but you can actually achieve log。Okay， so now let's do randomized。And there's the KL sketch。

K I sketch。Whi they named after themselves。Caran， Lang and Liberty。This is in 2016。

And what it achieves is the memory。Is O of。One over Epsilon log log one over Dlta。嗯。Okay。

 so before I show you that algorithm， I'll show you it's basically builds off an idea from Manku Raja Goppal and Lindsay so I showed you their deterministic algorithm from 98 then they they also had an idea for a randomized algorithm。

嗯。Instead。Of。Promoting。Every， let's say odd index element。You drink compaction？

You could also promote every even indexed element， right？

You would basically have the same kind of error guarantee。

So what they do is they randomly choose whenever they do a compaction， they sort。

 and then they randomly uniformly at random， either promote the odd index elements in the sort or the even index elements in the sort。

😡，Randomly。Promote。Either the odd or even。Indexed。Plements。嗯。Okay， so。How do you analyze that？Okay。

And basically the idea here is。嗯。As follows。So， remember。Remember this picture。Where I want to put X。

 let's say。This is my query X。And then I do a compaction。对。Now。

 when I do this compaction and I query the rank of x。

I'm either going to say two or four right if I choose to promote the I don't know if might do let's do zero based indexing so the first element has index zero。

 which is even so if I choose to promote the even index people。😡。

Then I'm going to think that the rank of x is four。However。

 if I choose to promote the odd index people。Then I'm going to think that the rank of x is two。😡。

So I be I will be off by one， but I'll either overestimate by one or I'll underestimate by one。

Randomly。And the point is。You know， before I was always kind of estimating in the wrong direction and all these errors were just。

 you know， additively accumulating。Okay。And now they're accumulating。

 but with random science as coefficients。So that's and so， you know， ideally。

 then the sum when you put the random signs on them of these errors will be smaller because some of these errors will cancel out because they have random signs。

so你好。The error。Arror basically is equal to。The sum。J goes from0 to H。And the sum。From。Let's call it。

R goes from one。To MJ。TheMR MR is。The number of compactions。At level R。Of2 to the J minus1。Times。

Sigma JR， where。嗯。And you know， let me actually。Let me actually be a little more precise in this。

Ana JR， Sigma JR。Okay， where？Ata JR。Is in0 or1。Remember， we saw we saw， for example。

 if x was not in between those two elements， what was right next to them。

 we would have no error right so if x if x were here instead。😡，We would not have error no matter。

 no matter whether he promoted the odds or evens， we would correctly say that there are four elements less than X。

 So sometimes there's no error。 So Eda is basically zeroing out。

Error that we might have had in that compaction because there was no error， but if we do have error。

 the error will either be plus you know plus two to the J minus or minus2 to the J minus1。😡，Okay。

And then there。That's what sigma is Sigma。Is a uniform random variable that's either minus1 or plus one？

是。So let's call this error， you know。The error is E so E is this basically this random variable that involves some adas and some sigmas。

😡，The As as we're going to see don't matter a whole lot in fact if all the AD's were one。

 you could imagine that's the worst case because all of them are contributing to error。

 but basically no matter what the Adas are we're going to show that the error is bounded。你这。Okay。

 good。So I would like to say， I would like。Would like。

That the probability that this error is bigger than Epsilon N。Should be at most。You know， Delta。喂。

That's what I want。And the question is， what can I tune here， the only thing I can tune is k。

 remember the size of the compactor。So the question is， what setting of K will give me that？

So any questions before we do that analysis and see what K we can get away with？O。

So we'll need a probabilistic inequality。And I won't prove it in class。

 but I will include it in the lecture notes so you can read about it if you'd like to。

It's called kinch's inequality。And what this says is。You know， let's say that Sigma1 up to Sigma T。

Our。嗯。IID plus minus1 uniform。Ranom variables。And let's say that we have numbers x1 up to Xt。

That are real numbers。Then it says that for all lambda bigger than zero， the probability。That。

The sun。Of Sigma I X I。So what is the expectation of this random variable， sum of Sigma Ixii？😡。

It's zero， right？Just by linearity of expectation， each sigma i is a plus minus1。

 it has expectation0， so we'd like to say that it's unlikely that this random variable is large because we expect it to be0。

 so the probability that it's bigger than lambda in magnitude is at most2 e to the minus lambda squared over2 times the L2 norm of x squared。

嗯。So just a comment。嗯。If Sigma1 up to Sigma T。Had been。Independent Galians。G you went up to GT。Then。

Some of G I X I。Is a Gausian。With mean zero on variance equal to L two norm x squared。

So I don't know if people have seen this， but if you take independent Gaussians and add them。

What you get back is a Gaussian whose variance is the sum of the variances of the Gaussians that you added right and so GI has variance one。

GI times some fixed constant C has variance c squared， so G times Xi has variance X squared。

So when you sum G X， your variance becomes the sum of the X squares。So， you know。

 if this had been Gaussians instead of plus minus ones， then that sum would just be a Gaussian。

What's the probability that a Gaussian with variance x al of x squared is bigger than lambda。

 it's exactly that it's exactly what I wrote here， this is the tail bound for a Gaussian。Okay。

 so what this kin's inequality is saying is plus minus one random variables have the same kind of tail behavior or their tail behavior is bounded by that of a Gaussian this is also known as you know。

So this is saying that， you know。What was called sub Gaussian。对。

Some of Sigma I Xi is what's called sub Gaussian， it decays you know at least as fast as a Gaussian does。

And in fact， the proof that we're going to put in the notes is a very simple proof that it's going to directly relate the answer to Gaussians。

Yeah。And then you know， there you can just look up what is the tail I for Gausian or you can try to prove it。

 I'm not going to prove it in class。So why is this relevant because in our case， remember for us？

We have this error， which looks like。The sum， you know。

 there was a double sum sum over J goes from zero to H。And then the sum。嗯。I go there are， I said。

Goes from one to M K MJ of。Sigma JR。Times something， something was。Eta JR times2 the j minus1。Right。

This， of course， is my。This is my XJR。喂。So I exactly have the setup of Kinen， I have a sum。

Of independent plus minus-1 random variables， times other stuff。So now what's my。

What's my L2 norm of x squared？嗯。There's equal to。Well， it's at most， you know。

 in the this is why I was saying it doesn't really matter what the Adas are if all the Adas were one。

 the Adas are either zero or one。So the alton norm squared is upper bounded by the case that all the Adas are one。

😡，So this at most the sum j goes from zero to H。Of two to the2 J minus1。Times Mj。

And remember what we bounded MJ before， MJ was at most。Is that most。

 how many is the number of compactions there are at level J？

So this is at most n over k times 2 to the j minus1。That's what we saw before from the MRL analysis。

And then now we get a little bit of cancellation， right， this cancels that。😊。

And then n over K just gets pulled out of the sum。So this whole thing is at most。

N over K times the sum。Two to the j minus1 up to H。Actually。

 this should be j goes from1 to H because we said we're compacting in two level J。

 we never compact in two level zero。Which is less than。N over K times2 to the H。

And H is log at over k。So this is basically。N squared over k squared。Right。

 so al norm squared for us is n squared over k squared。

 so let me actually try to adjust so that you can refer back to the inequality we have here。

This is the inequality we're using。那是定谁。I'll just do it right here this is。This name。😔。

So the probability that our error。Is bigger than what do we want the bound to be epsilon times n？

Is that most？2 E to the minus。Epsilon squared n squared。嗯。Times。K squared over n squared。

 and there's an over2 here。Because we have to divide by the al of x squared。

 so we have to divide by n squared over k squared。So n squared cancels。And we have。

 we basically just have this case squared。So this implies between set K。To be something like。

When epsilon times the square root of log， whenever delta。

We want failure probability det at the end of the day。什份证。So when get here。嗯。

So this we get k to be one over Epsilon， root log， one over deta。The space。

Is k times log of n over k？Which for us then becomes something like。O of what epsilon square root。

 log whatever delta times。嗯。Times log of。Epsilon and overview。行。So that's already something。

Remember that Ml was log squared n。If you think of Delta as being， let's say a constant。

 like one over 100。Then root log whatever adults as a constant。

 so already we've improved log squared of Epsilon n to log of Epsilon n。of course， you know。

 green one can do that termministically， so that's not great。嗯。So how can we do even better？

So one of the ways to do even better， so improvements。

So what ML realized was one way you can improve this is via sampling， so can combine。With sampling。

And the idea there is if you keep。Keep a random sample。

O of one over Epsilon squared log of one over Epsilon Dlta。Elements， let's call this N prime。

From the stream。Then you can show via like the turn off huffing bound that if you then just answer you know。

 rank rank and approximate rank and quantiles rank and quantiles are the same rank is like what's the art's smallest element quantiles is like。

What's the alpha Nith smallest element where alpha is a fraction between0 and1 what's at the 25 percentile what's at the 50th percentile right so those are equivalent just by you can multiply alpha by n that would give you the corresponding rank or you could divide the rank by n that would give you the corresponding percentile or quantile that you want。

And if you just buy the turn off Huffing bound， basically what you can show is that you keep a random sample of this size。

Then。You'll' you'll give that alone will give you an approximate quantile data structure basically when someone asks you what's the median。

 you just return the median from the sample， what someone asks you what's at the 25th percentile。

 you just return what's at the 25th percentile from the sample and you can show that this will actually do that for you。

 okay。😡，嗯。But now what you've done is you've reduced， so let's say you know and in advance。Okay。

 so what you do is each item you see in the stream。

 you you actually just remember it with probability and prime over and otherwise you get rid of it。对。

And then what you do is you feed this sample。Into the intoto the data structure I just showed you。

 right？😡，And the point is that n is now smaller。 n is now n prime。 so this n gets smaller。ok。

In particular， that N is something like R Polly， one of Rpsslaan log one of Delta。Right。

 so this implies a space bound of something like whatever Epsilon root log whenever over Delta times log of epsilon and prime over root log over Delta。

Which is the same thing as whenever Epsilon root log whatever Delta。Times log of。

It should be something like。I think log whenever uppsilon。 is that right Yeah。

 basically log of whenever uppsilon。pl。Log， log， whenever adults says something like that， maybe。

Or another thing you could do is you could then you can then feed the sample into actually。

 a better thing you could do is feed the sample into a deterministic data structure。

 like feed the sample into Greenwall Canana。If you feed it into green Wild Canal。

 that will actually even get rid of the square root log whenever delta。Okay。

But it's you can do better and that's the KL sketch， so what does the KL sketch do？嗯。

It uses first of all， so the first idea that they had was to use geometrically changing compactor sizes。

So your first few compactors are actually going to be quite small， they're going to have size two。

And then the last one is going to have size K。And then the one before it is going to have size basically。

Two thirds K。And the one before it。Is going to have size2 third squared K。Et cetera。Okay。

At some point， you know。Two first to some power k is going to be less than one。

So what you do you kind of bottom it out at two， so you never let the compactor sizes get less than two。

And then you do exactly know the way that we were doing things before。

 you insert into the bottom compactor when it becomes full， you promote you promote half the items。

 either randomly the odd or the even into the next compactor， etc。嗯。And then。

 you know everyone in compactor J again has weight two to the J that doesn't change all that changes is that the compactors no longer have uniform weight。

Yeah。And then alema。I don't have time， I'll include it in the notes， but I won't show it here。

Is that。嗯嗯。First of all， you still have that kind of。Great， guess you still have that MJ。

 the number of compactions on level J。Is that most well， yeah so。Let me not exit the in a second。

Yeah， so I'm actually like， yeah， I'll just let me prove this in the notes。Is that？

The x al norm squared that you get from this。Because now。You know。

 the sum isn't exactly the same because， you know， you have to you have to again。

 correctly bound the number of compactions that happen at level J。

And then you'll get a sum that looks similar to。Basically， this sun。

You'll get a sum again that looks similar to this sum。Okay。

 but you need to bound Mj appropriately and also bound how big Hms appropriately。

 but the punchline is that if you do that。You can get this thing to be at most。嗯。Still O and square。

🎼嗯。He weird。The of that is you're still getting the same exponent into that tail bound。

 so you can still set K to be the same as before。So what's the benefit， the benefit though， is that。

The compactors are not all the same size， they're geometrically decreasing right so instead of paying a log a log n factor times that in your space you're only paying an additive。

Log in and the reason it's added you know each one of these compactors does have size at least one so you do have to pay an additive log of n over k because theyre rough O of log n over k compactors each one has size at least one so this implies space that's o of one over epsilon square root of log whenever delta。

Basically plus log n over k， which speaks something like a log of Epsilon n over your log over Dlta。

So the benefit that is that this used to be at times， but now it's a plus。And then。嗯。😊。

The kind of the last。The last。Finishing touch to get the space even better。Is。Two things。So。

The final touches。There are two final touches。What are these two final touches one？

You have all these compactors in the beginning。Now just have size two。So what is it really doing。

 so you know some items so let's say that they're L of them that have size exactly two。

em you can think of this as like kind of one big black box。Where you know， two to the so you know。

 two items come in here， the first one。Then when this one gets full。

 that represents basically four items， et cetera。So when the last one gets full。唔使。You know， this。

 this represents like two to the L items and then one gets spit out。

 one item gets spit out during a compaction， and this represents two to the L plus one items。

So you can think that kind of every two to the L plus one items that comes in here to the left of this big circle。

 this big oval， one item gets spit out and which item is it。

 well since you're always promoting a random randomly odd or even here autumn even just means the first element or the second element because there' are only two elements。

😡，The item that gets spit out at the end is actually a uniformly random element amongst those two of the L+ one items。

😡，So what they say is rather than spend L units of memory or two L units of memory with these L compactors of size two。

We can just implement this entire oval as a sampler。😡，That， you know， samples every one over two。

 you know， out of every two of the L plus one adjacent items in the stream。

 it samples one of them uniformly at random。So implement。As a sampler。In just O memory。

So that's the first optimization they do。And the second optimization they do is。

 remember our error is going to look like。This double sum， J goes from1 to H。

R goes from1 to Mj of the sigma JR times7 coefficient。

And this coefficient was to the J minus1 times8 to JR。

So what they do is they actually separate this double sum into two parts。

They say that this is the sum of small J J goes from one to H。Minus S， so don't go to the end。

 go to n of some of our minus1 Mj of all that stuff。Plus。The sum J goes from h minus S plus1。To H。

Of the sum a goes from1 to MJ。Of Sigma J R。8ta JR to the J minus1。

 so they break the sum into two parts。And then they say。

 let's bound the error from this part using kinin， which you've already seen。And for this。

We're going to use a trivial bound。What's the trivial bound。

 the trivial bound is just bound all of the random signs by by one。

So the trivial bound is that this is at most。The sum J goes from h minus s plus1 to H。Of。MJ times。

Two to the J minus1。We don'tWe don't take advantage of the fact that there could be cancellations from the plus minus one。

Okay。And if you do this。And pick the right value of S for the calculation as being something like log。

 log whenever delta。And you also。Make。The last。K compactors。Are the last sorry S compactors？

Have size exactly equal to k， don't make them geometrically decay。

 make them all have the same same size。Then you can show that in fact。

 you can get away with K being even smaller。😡，And that that will give you a bound if you do this correctly of one of Epsilon times。

Log， log， whenever Delta squared。Okay， so I know I'm basically out of time。

 but let me just draw the picture， the picture basically looks like this。

The first few levels all get implemented just as a sampler in constant memory。

Then this gets fed into a sequence of compactors that are geometrically increasing in size。

And then that gets fed into compactors that all have the same size k。AllThere are S of these。

 all of these s have the same skys K， these and then these are geometrically decreasing in size。

These are geometrically decreasing， so there are basically three components you can think there's the sampler。

 there's the part that's geometrically increasing in size and the final S that all have the same size。

That that's the data structure， and you can show that this achieves space whenever of Epsilon times log log whatever delta squared。

 if you analyze this appropriately where s is log log whatever delta。

And to get the actual optimal bound， what you do is you actually cross this part out。

And you just put an optimal deterministic algorithm here， which is， for example。

 the Greenwall canal algorithm from 2001。 So this arrow actually feeds into。The GK algorithm。

And if you do that。That gives you space， log， log whenever deelta。对。嗯。So that's it。

 I know we're slightly over time Any final questions before we。Take a break until Monday。

I know I didn't give all the details for the more sophisticated stuff， but at least I you know。

 you did get to see all the analysis details for some of the simpler variants that still get decent space bounds。

Sorry， do we not have class Wednesday？It is Wednesday。 Today is Wednesday。

Remember there Monday was Labor Day oh god。Another a problem。呵。Okay， so I will see you all Monday。O。

Thanks。

![](img/d4a509324399607834dd917a6ca8ec99_6.png)