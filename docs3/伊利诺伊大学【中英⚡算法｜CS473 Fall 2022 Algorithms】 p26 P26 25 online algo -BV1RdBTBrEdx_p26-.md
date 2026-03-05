# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p26 P26 25 online algo -BV1RdBTBrEdx_p26-

![](img/cca5c0f21180c80d19b6e9e1483ee7bf_0.png)

All right， let's go ahead and get started so just a reminder。That。Were now in the。

Whose line is it any phases the semester？Everything's made up from the points that matter nothing i'm going to talk about this week is on any homework or any exams probably not also relevant to any upcoming 598 classes at least that i'm aware of so this is just。

Jeff talks about cool algorithms for a couple of days。

 so I you know I do recognize that you all have you know other classes and homework and projects and stuff。

 so I do appreciate。The fact you're here。So。What I want to talk about today。

 and to some extent what I want to talk about on Thursday is a different kind of algorithm called an online algorithm。

So the。You've seen online algorithms before。😡，But you've seen them。Under a different name。

You've seen them called data structures。So a data structure is a box that you feed instructions to and the box responds by doing some computation and giving you data back。

UHere， here store these values here， tell me if this value is in the set that I gave you。嗯。

But for an online algorithm。The goal is slightly different。Okay， so it's still that I need to manage。

Sequence。Of operations。And I want to minimize。The total cost。But。啊。对。Comparison that I want to make。

Isn't absolute？But rather， I want to compare the performance over the entire sequence of operations。

Against an all powerful all knowing clairvoyance adversary。Okay， so。

I the online algorithm gets a request they have to handle it immediately。

 they get another request they have handle immediately。

 they get another request they have to handle it immediately the adversary on the other hand gets the entire sequence of requests in advance。

😡，And has to answer them all at once。Okay， so you're comparing against a clairvoyant。嗯。optimalpt。

 you know， optimal algorithm。To an optimal。Clairvoyant。Algorithm。So。The idea is。

If the problem is fundamentally hard。😡，I don't penalize you for taking a long time or incurring a large pass。

😡，To handle the operation。It's more well do the best that you can and with the cost basically you're looking at the cost of nearightedness。

The cost of not being clairvoyant now the word cost here doesn't necessarily mean running time。😡。

So I'm to just。Give a sort of canonical example。This is not one of the examples that I'm going to analyze just because it's limited time。

 but this is something that you've seen before。Which is paging cash maintenance。

so the idea is I have。嗯。ACash。That can hold K items。So K memory addresses。

And the operations that I need to perform are。😡，Go tell me what's at this address in your global memory space。

😡，Now， the way caches work is。If the item is in your cash。

 then you get the item essentially for free。😡，If the item is not in your cache。

 then you have to go out to remember and get it and put it into the cache。😡，Um。

 but then when you ever you put something into the cash ship just throw something else out。Okay so。

Request。AMemory address。Let's say address x。If x is in cash。The cost is zero。Else。Move X。

Into the cash。But eject。Something else。Yes。And now the cost is equal to one。Okay。Great， so you pay。

Or patrons。Or cashs。系。嗯。Now。There are standard picking algorithms that you may have seen in some earlier classes。

 the two that people talk about the most are ciIO。The cache is a first in first step queue。

When you bring something in for memory， you stick it on the left end and you eject the thing that's on the right end。

The second most popular and number the one that everyone actually uses is LRU， least recently used。

 the cash is a priority queue。U，h， when you eject something， you eject when you use something。

 you increase the counter。Or you set a timer like when that was last touched and the thing you eject is the thing that was touched firstthest in the past。

系。It turns out that。Both LRU and FiIO。Are what are called k competitive。What this means is that。

The cost incurred。So for。Any access sequence？The costst incurred。Is at most k times the optimum。

Where the optimum， you look at a trace of all memory accesses。😡。

And you figure out what the opt you know when you need to e something。

 what is the best thing to eject and it turns out the optimum is you e the thing that's going to be brought back into the cash furtherthest into the future。

😡，So it's the climb reverse of LRU'。I took at what it's called。Fthest into the future， right。

So you look you know whichever one is going to be used for this in the future if something's not going to be used developed and you can be objective and it's fine so optimum is。

Eject item。Used。Again。Fthest in the future。嗯。So the competitive ratio of these paging algorithms is k。

 this is the ratio for an upper bound and the worst pay for ratio。For。

The performance of the algorithm versus the performance of the optimal offline episode。😡，There's a。

Fluush when full is another taking positive algorithm。

 which is you empty the cache at the beginning of time， whenever you grab an item。

 if there's facing in the cache， you put it in the cache， if the cache is full， you flush it。

This is also k competitive。All of these have the same in terms of sort of worst case behavior because you're optimizing for arbitrary access sequences。

So there's a general class of online algorithms for page that Apple property。嗯。

You'll notice there's a discrepancy between the competitive ratio and real world behavior。

In the real world， flush windfall is just stupid。In the real world。

LRU is much better than PIO because LRU takes advantage of temporal coherence。

 if you access a memory address， you're likely to access that memory address again soon PIO doesn't take advantage。

And there are actual theorems that say， if your memory addresses are guided by walking along a series parallel graph that's supposed to represent track code。

 then provably with that restriction on the input the request sequences。

 LRU is more competitive than P。没。嗯。But。As usual。诶。Um， there's， you know。

 this is a fight between designing an algorithm and comparing again。

 it's an all powerful malicious a。The all powerful malicious a is designing the request sequence。Now。

 real world code isn't actually all powerful， adversarial yes， but not all powerful。😡。

So the usual way of getting around pathological inputs designed by a worstspace， you know。

 all powerful adversary is to use randomization， and so there's another class of aging algorithm called randomized parking。

😡，Um， so roughly it goes like this at the beginning of time。

 your passion is empty and nothing is marked。😡，When you put something in。

 you reject a randomly chosen unmarked item from your cache。😡。

If everything in your cache is marked because you' filled it up by bringing things in。

 you clear all the marks and you start a new phase of the algorithm。

 so you don't it's like flush while flush wind， you don't flush the actual data。

 you just flush the marks。😡，And then you choose a random unmarked thing to reject it turns out that the expected ratio of。

Expected number of。Cash misses。Over optimum is always at most。啊。Case harmonic number。Oh。

So you get an exponential speed up。By doing random。Those speed up， I mean。

 an exponential performance of Christmas by doing random things。对。U。I actually don't know。

I think the answer is it depends depends。It also， I mean。

 one of the problems is that real caches aren't the simple。

Cashs have you know multiple layers and and several layers of cash involved and it also I think depends on。

Whether this works better in practice is going to depend on the kind of access sequences you're looking at。

If you're caching， say。Uh， IP addresses from watching the internet back bug， yeah。

 Google is going to sit in your cash。Other things are going to be more or less random if you're doing some very。

 very long complicated code， it doesn't actually have that much temporal coherence。😡，Then yeah。

 it's going to be better。Or actually， everything's going to suck， this is been to suck。

So like I said， for the interest of time。啊。I'm not going to walk through the pre of all these。Um。

 but this is the kind of problem that gets described by online algorithms and analyzed in terms of this thing called the competitive ratio。

😡，Is the cost incurred by the online algorithm versus the optimal cost？

Incurred by the best possible portfolio Bel。You can imagine other kinds of things that fall into this category。

 scheduling is a big one。I've got lots of processes that I need to schedule if I know when jobs are going to end then I can schedule in advance。

 I know I can schedule better， if I know when jobs are going to come in to the request queue。

 I can schedule them better if I know how many processors I have。

 if I know how busy things are going to be， if I know more about the future than I can schedule better。

 but in fact I know none of these things and so I'm going to design scheduling algorithms that get do as well as it can given the state of ignorance of the algorithm。

嗯。啊啊。You know， any lots and lots and lots of sort of system level things involving。嗯。You。

Managing threats and parallel cost substance。Netflix Ts and things like。Thanks。Okay。But。

I'm going to start with something much simpler。And it's not going to look as much like a data structure thing where I can put some information and answer requests。

 but it is going to kind of give you some idea about some simple tools for doing competitive analysis。

😡，So。There's a cow。It's asleep。It wakes up。Somewhere。啊。On the middle you know， middle of the road。

Doesn't know where it is。Somewhere else on the road， there's a barn。Uh that has， you know。

 hay and and other stuff in it it really like fun the barn， but Cal doesn't know where they are。

All they know is they're on the right road。Somewhere。Yes。Now the cow wants to find the barn。

 also it's foggy， so in order to find the barn the cow actually has to walk actually into it cant just see it from far away。

Okay。嗯。If you want， it's in the middle of a forest in the cow can seafood and trees until it's close enough。

Okay， so。There's some distance D， but I don't know the cow doesn't know D in advance。😡。

What strategy can the cow use to find the barn？😡，Walking as little distance as possible。😡，Now。

 if the cow knew。😡，The barn is to the east。Then there's a very simple。Optimmal algorithm。

 which is walked east。How does it know that？So。觉得。No。There's no， I mean。

 there's no upper bound given on。Again， just to simplify the problem， maybe the barn is on the moon。

Maybe the barn is over the moon。How is the job？我应该是。我度嘅。Okay。

 so it's sort of very natural to imagine the kind of exponential strategy。Where。

I search to the right。Some distance， and then I search to the left some distance。And。

Sort of oscillate until eventually I find。对，不道。Okay。

So I'm going to imagine a schedule that looks like this。Zero to infinity。

I'm going to imagine just for the sake of of argument that i'm going to call the cow initial position on the road zero and i'm just to refer to positions by distance to the right of where the cow woke up so i'm going to walk to。

😡，Some distance DC sub I and then I'm going to walk。Or some position。

 and I'm going to walk back to zero actually， let me call this xi。

And so a search strategy to cow is a sequence of numbers， x0， x1， x2， x3， and so on。

Different sequences of numbers。We'll give you。Different competitive ratios， okay， so let's say here。

I'll just imagine for the sake of argument that these are going to alternate signs。

This turns out to be the right choice。That's intuitively obvious。啊。That doesn't mean it's trivial。

But it is the right choice to go left， then go right， then go left， then go right。Never go less。

 go back， go less， go back， go less。系。So there's some distance。

Let's say if I start off by going to the right。😡，There's some distance X2 by。At an even iteration。

 I'm going to the right。That is not quite to the barn。

But the next distance x2i plus2 to the right is pass block。I don't know what I is。

I'm making to simplify an assumption here that the barn is at a positive exordant and that the cow is making its first step to the right。

There's symmetry involved here。😡，It's auffices to consider this place。Right right， so。If。The the。

Actually， let me call the target location T。Okay， so assuming that T is non negative。And。

X2 I is less than t is less than x2 i plus2。Then the distance the cow walks。Is。X0 plus。

2 x0 plus 2 x1。Plus 2 x2 I to get to here。Plus2 x and then back to the origin。

Two equal equals1 and then T。Okay， so each of these terms is the cost of going out and back to the starting point。

So what I'm trying to know the goal。Here。Right so this distance is some functional key right the goal is to。

Maximize over all choices of。Sequences。Minimize overall functions of T。

The distance incurred by T for that sequence。by。Okay， so notebook the。Actually， hang on。

I've got these backwards。I'm going to design an algorithm。😡，So the search algorithm is going to use。

that much is going to have this competitive ratio。系。Once I decide on my sequence of values。

 x0 x1 x2 and so on。For any fixed values of。T， the target。I'm going to get this ratio。

 the distance that my search algorithm travels。😡，Divided by the business recovery。

And then the adversary is going to read the cow's mind。😡，And say啊。That's the strategy you're using。

 that means I should put the barn here。😡，And the cow being a cow has no way of knowing that the barn wasn't always。

Yeah。This is the usual game when we think about adversaries is we always design algorithms to run on inputs that are given to us in this case the barn has a position even before the cow workss up。

😡，But we should still imagine that the adversary who's going to choose that input can read our code。

Is to read the cow's mind。So after we've done writing code， it's going to be used later。😡。

By somebody you can actually do it。And so that's why that nin is on the outside。

 the adversary is when to choose。啊，对好。嗯。😊，Okay。So really what I want。Is I want to。Choose。This。

So that。Distance that sequence to T is at most c times t。This is my competitive ratio。For all。See。

Better choice X would allow me to get smaller configurations。Okay。没 you。嗯。

We had one suggestion for a sequence。Other ideas？I mean， for example。

 I could let x sub be plus or minus I。Walk one step to the right。

 then walk two steps to the left then walk three to the right， four to the left， five to the right。

 six to the left。Yes， but why。呃 it sort of but what。Pbinarci is nice， but what makes Fici nice？

What is it about Benacci numbers that are closer than just using closer minus？Okay。Getting close。

It's a word， one word。Not that one， the other one。Starts with an need。Exponential。Okay。

 so what happens if I go one to the left to the right， read the left four to the right and so on？你去讲。

Well， what happens is by the time I reach the target T， I've gone through key phases。

And in at least half of them， I walked at least distance ti over two。😡。

So the total distance that I travel using this arithmetic sequence ends up being t squared。

 which means my competitive ratio。😡，Is tea， which means my malicious adversary will put the barn on Mars。

😡，And that there is no bound。Or the competitiveness of this algorithm is not competitive。喂。But again。

 intuitively， if I let these things grow exponentially。Then。

The time that I spend zigzagging back and forth before the last trip to the right。😡。

Is a geometric series。😡，It's bounded in big O terms by the length of the last step。Which means。

The competitive ratio is going to turn out to be constant。

Now there's a question of what that constant is going to be and that'll depend on the face of the exponential growth。

😡，You'll get one answer for powers of two， we would a different answer for Fipinacti numbers。

 but for both of those， you're going to get a constant competitive ratio。All， so let me。

Just tell you。It turns out that the optimal choice at least up to lower order terms。

 so I'm only interested in the leading term and that ratio。I should set x of I to be minus2 to the I。

So that means it's in the phase zero， I go one step to the right and then back to the origin。

 then two steps to the left and back to the origin four to the right， eight to the left。

 16 to the right。😡，Support。Right。And now my distance of T。If might， well， it turns out。

That this simplifies to。Two is two。Then this distance is two plus four plus eight plus。

Plus two times2 to B2i plus2 times2 the2i plus1 plus T。Again， should refer back to this picture。啊。

The last step here that highlighted like a yellow。Um。

 that's when can almost reaching environment quite that's when they have。

Then I'm going to take the next step to the left。And then origin and then the last cell。

 there was one。嗯。Okay。This whole mess。Is2 to the2 i plus3 minus2。Yeah。嗯。嗯。But。

Two to the2 I is less than t， so this is less than 9 t minus2。So my competitive ratio。Its not。

I go about powers two， the competitive ratio is not。嗯。Now， intuitively。

 why did I choose power of two here？At least intuitively。If I choose B to be smaller。😡。

That means the exponential growth is slower。Then I'm wasting more time in the earlier iterations in the adversary and make the ratio go without by putting the barn far far away。

😡，On the other hand， if I grow too quickly， then this last step over to the left。😡。

Dominates everything else。U， and so again， the adversary doesn't need to put it far far away because these need to put it very。

 very close just beyond where it could reach some stuff right。

And then the adversary will waste their time going let's sorry， the algorithm。

 cow will waste their time going too farther of the away。嗯。Or。If you like。

 you can plug in your favorite constant to be here as a variable， figure out what this expected。

 what this competitive ratio is， and then there's a tank derivatives set the derivative to zero。😡。

Figure out the optimal value of B is the turns out exactly two。嗯。Um， okay。So。All right。

ThisThis turns out there's a lower bound argument that Y nine is the best we can hope for。

 no matter what shape your sequence。😡，Not just the things。It is more complicated。U。But I want to。

Do some randomization here。So。It's the simplest thing you can imagine doing that would。不对。

Maybe gives the talent advantage。Using red em。There were some arbitrary choices that I made here or seemingly arbitrary choices。

Okay。So there's one of arbitrs。嗯。Well， it's even simpler than that。

So I assumed throughout this whole analysis。That the first step was to divide。

I could do exactly the same algorithm that the first step didn what。

 so just in the ga all yet since that I said earlier。

 I get some different indices so I get odds your next car instead of even ones。

 but you still end up with 190 minus2 thiss in the worst case。But。

That was kind of an arbitrary choice， I could turn left at the beginning and I could turn right。😡。

And the adversary' positioning of the bar depends on whether。

The cow starts by going to the right or starts by going to the left。

because if I start by going to the right， you know。

 there's some right word jag that ends here and I at the barn just beyond it。

That's the worst possible question for the barn， but if I start by going to the left。

 then these's right where jags end somewhere else。😡。

And so the worst place for the barn is somewhere else。系。And so we're。

We are still imagining that the barn is somewhere before the cow wakes up。😡。

Because we're telling the story that way， the barn is somewhere before the cow wakes up if the cow wakes up and flips the coin the adversary。

😡，Even though they knew the cow's strategy can't move the barn。Based on how the coin flipped。

They have access to the cow's brain， they don't have access to point flip。Okay， so。Um。

With probability one half。嗯。Start with plus one and with probability one half。

Start with minus one and then。Expand by to。At all later steps。No。So this is a subtlety。

I'm assuming here that I have what's called an oblivious adversary。

So this is not a distinction that matters when you're thinking about proistic algorithms at all。😡。

The adversary reach your code designs the works input and goes home。系。

That's also what an oblivious adversary does and you have a randomized algorithm。

 the adversary reacher code， designs the worst case algorithm in goes Hall。

An adaptive adversary changes the operations that you're being asked to perform based on how you perform the earlier operations。

😡，so this this will come up when we start talking about binary search trees as competitive algorithms。

 if I notice that certain searches take a long time。😡。

Then I'm going to ask for those things more often。😡。

Timing denial notable service facts are a real thing， okay， that's an adaptive advers。

An oblivious adversary would say， oh， I see， you're using left leaning red la trees。

 so here is the sequence I'm going to give you。Um that you know。

 this is the worst possible for this algorithm no going。いぱい。

So here I'm imagining an oblivious adversary， not one that watches the cow and based on how the cow moves。

 pulls the barn up and then drops it just the the last minute。😡，计。All right。

 so I've got two choices here。Distance， if I start by going to the right。嗯诶。This is if。

Two to the2 i is less than t' is less than2 to the2i plus2。

This is two to the2i plus 3 minus 2 plus t。On the other hand， if I start by going to the left。

Then I get a slightly different looking bound。For slightly different。嗯。Boundary conditions。

So this means that if。Two two to the2 I to sorry。If I look at the intersection of these two boundary conditions。

那。Okay， so for the right strategy and I'm looking at the bars being on the right。

 the range or values to T that I need to look at is between even powers ofivity。

If I'm looking at the less strategy， but it turns out the in odd power security。

So if I'm looking at a mixture of these two strategies。

 let me just take the two consecutive powers of two that fit into both of these ranges。

And then in this case， the expected distance。This is half。Distance R plus half。Distance L。

This comes out to。Well， half of two the2 i+3 plus half of two the two i+ two。What's the minus2？

This is。4 plus two， that's six times two the2 i plus t minus2， which is at most 17 minus2。Okay。

And so the best I could hope for with a deterministic algorithm。Was a committed to ratio of nine。

But if Bessie wakes up immediately puts a point， heads go left tail go right。

That reduces the expected competitor shift in mind。嗯。Yes。嗯。

Now there are more choices that one can make。😡，So。It turns out that this constant two here that was optimal when I was doing things deterministically is no longer optimal if I flip points at the beginning。

😡，Okay， so。Better。Is to set B to I believe it's one plus squared to two。

 and then the competitive ratio comes out to4 plus2 root2， which is about 6。28 something。Okay。

 so it's something that looks。Less light powers of two and more light。You know。

 some tribonacci likelihoods。啊。Okay， so I can improve things a bit more。

 but there's more randomization that I could do。There's another。Very subtle。Arbitrage list。

 but I'm a beginning the decide。是。Well， okay so effectively I have to do that anyway。

 so the answer was I fixed x1x2 and so on ahead of time。The cow is going to walk X0。

 walk back to the origin and says， I didn't see anything。😡，Okay。

 now I have to decide on next morning。It's not really any different from deciding on next one in advance。

 don't have any new information。对。回啥。So what exactly do you want to random？Right对。Okay。

 so so one possibility is instead of fixing that base。

 the growth exponential rate of the growth be2 or to be one plus square of two。

 I could generate it randomly。I believe that does give you slightly better results。

 but now you have the complicated question of so what probability distribution are you going to use？

Yes。And now I need to optimize overall possible probability distributions。😡，Yeah。

So it turns out that there is an optimal randomized strategy here that fits within this exponential search paradigm where you have a fixed in advanced growth rate。

😡，But there's another parameter in here that we can vary。😡，Yeah。

We're always going to walk back to where you look at。对。So again。

 it turns out to always be better to alternate directions than to if I instead of going to the left and left again。

 I should just go to take the second。在报位。How long was our first stage？Okay。1。In what units？

Meters the way God intended。Cows don't know units。this is something I think that sort of meta lesson is that the the algorithm is in some way scale pretty。

If I decide my first step is going to go pi steps to the left and then two pi to the right and then four pi to the left and so on。

 I'm still going to get competitive ratio of nine for the original algorithm。

 it just means that the adversary is going to put the barn pi times further over。喂。😊。

So the sale doesn't matter， but the cow has to choose a scale。😡。

The cow has to choose how long the first step to the left is。😡。

And it turns out that the optimal thing to do is to randomize that。😡。

Randomized the choice of how far to the left to go so it turns out there's a paper by。How and R。Yes。

 last the first author's last name is cow。And yes。Ming tao knows。And that his last name is Po。

And is the paper randomized algorithms to the cowpath problem？

For a long time on his webp page right over his name， he had a cartoon drawing into the cow。啊。So。U。

Walk to。Minus B to the i plus delta。Walk to zero， Okay， so fix be in advance。And then I choose Delta。

Uniformly。嗯。Between zero and one so the choice of this exponential shift。Tme Delta。

This' is exactly the same but choosing periodologies third things and truths。

 I'm going to choose that shift delta uniformly is a real number between zero。

What effect that has is I'm choosing a scale for this picture。

That's basically interpolating between the start strategy except to the left and the start strategy。

😡，对。Um， so I choose within that that uniform range of scales where the first step to the right has length one and the first step to the left has one one。

And then I set B correctly and then it turns out that。The expected competitive ratio is about 4。

61 something。Okay。系我烦你。And much more surprisingly。That's actually that's the best you can do。Oh。系。

So the more freedom you give the cow when they start。😡。

How how far do they step the first time before they come around in which direction the more competitive the algorithm is sort of fuzzing out where the adversarial choice department is。

啊。Now this is most of this stuff was done in the I think 93 is the white time period。

Lo of stuff was done in the 90s。In you know， 20 years later。

It occurs to me to wonder if there's some sort of。Better things can do。If you have a quantum count。

That。To walks to the left to some amplitude to the right of some amplitude and isstruct of their appearance。

I have no idea whether this question even makes sense。

But I wasn't able to find anybody who thought about it。

Maybe quantum cows are more competitive than nearly randomized cows。Don六。系は。

You get a measurement when you hit the barn。Yeah啊。不对。在我们。这个。No， B turns out to be， I think 3。

62 something。It's the actual competitive ratio comes out， I believe to something like。This。

And then you take the derivative second out that。没法确。诶都都即解，我就谂到就瞓咯。All right。好。Okay。对。Okay。

Other questions about cows？Yeah。Okay。All right， so。Okay， so。Okay。

this is an example of something that normally goes under the name rent or buy。😡，Okay so。

I go to a coffee shop every morning， I spend$ five dollars for some。Hipster artisan olds in the Lord。

啊。Bittters the gates of hell， espresso。Um every day，$ five。But you know。

 for a certain amount of money， I could just buy the coffee shop and get the coffee for food。

Turns out you know buying the coffee shop coffee shop make very little margin。

 very little profit margin， so it's not like I would make money by buying the coffee shop。

 it just means that I wouldn't have to pay for coffee anymore anything else for break。😡。

Okay and the question is。When is it worth actually doing it？When should I just buy the property？

Now the thing that makes this intersg is at some point。

I'm going to walk out of the coffee shop and get hit by a bus。😡。

Or meteor is going to come out of the sky and land on the coffee shop and destroy it and that's it in the coffee。

喂。I don't know when this is going to happen so be really kind of stupid to buy the coffee shop in the next day。

😡，The meatte your strengths。And then the dragons arrived。

 that's the next day the dragons arrive and that's the end of the world and no more coffee。

So on the other hand。If， in fact， the dragons are never going to arise。😡。

Then it's stupid for me to go to the same coffee shop every day for the next million years。

And by a $5 present。Okay， so let's you know simplify the game here， so every day。I can either。Rent。

 whatever objects that I want to use for a dollar。Or I can buy。For B dollars and then all。

Future rents。A free。But。啊。The world ends。After three days。The way this is usually expressed。

 remember the back in the 90s， is everyday ego skiing。Okay。So in other parts of the world。

 there are these things called mountains。That you can speak down。

Gravitational gradients are not a thing in this part of the world。

 but in other parts of the world they are so you go to Ss art and for 10 bucks you can rent skis today。

😡，Or you can buy schemes。And you're going to do this every day。

 but at some point the snow's going to melt and you can't just。

So the question is based on what we know， which is the ratio between the rental cost and the purchasing costs should just normalize through D goodbye by。

😡，No beef。But you don't know， see， don't know when the world is born。Where should you buy？

OkaySo the optimal algorithm。Is going to pay the smaller of T and B。

If the world ends in less than few days， then let let wait。

If the world is going to end more than few days in the future， buy on day one。😡。

Okay so this is what the optimal value is going to be。No。

If you want to like describe a deterministic algorithm for this problem。

 I've given you all of the information。😡，The only thing that you get to decide is。

How many days are you going to invest before you buy？Okay， that's it right。

 so when we define cost of i comm T， this is your cost。Your total cost。If you rent。High times。

Before buying。Okay。I'm going to write this in a bit of a funny way here。Okay。

So the brackets is usually one compression back through zero otherwise。嗯。

If if you've decided I'm going to rent I times。😡，And the world ends。But on honor before day I。

Then the amount of money you spend is exactly cheap for every day you spent $1 and then the world ended。

😡，On the other hand， if the time goes on beyond the day when you would buy。Then you rent。

For those eye days。And then you buy。And that's the end of the class。

so either the world has a short fuse or the world has a long fuse and given those two possible needs。

Yes thats。That's your choice and so the question is what's the best choice of that parameter I。

 that's the entire that's all you have control over。😡，What day are you going to buy？系。

It turns out that。The best choice is to set i equal to b minus1。And then cost of b minus1。

T is either2 b minus1。If the world lasts。A long time or it's T if the world doesn't last a long time versus optimum。

 which is B here and T here。And so the ratio you get。Is。2 minus1 over B。The adversary。嗯。

It makes you pay more by lettinging the world， by waiting until you buy and then destroy the world。对。

So roughly speaking。Um， dependingending， I mean， there's there's again， a scale thing here。

 which isn't really scale because mean that B is really your ratio doesn't really have units。

But the larger that ratio is between the cost of rent and the cost of fine。

 the closer the competitive ratio of this algorithm is too。嗯。For the deterministic algorithms。

 this turns out to be optimal and I don't just mean that the two is optimal。

 I mean this is exactly the optimal deterministic algorithm。😡，Um。

 and that's not actually that hard to prove because the deter deterministic algorithm is literally a positive integer。

😡，What do you choose for hire？That's your album。Okay。

 you can just try larger and smaller values and see that you get worse ratios。好。But。

You're not given to。You decide on your algorithm， and then I'll tell you what key is。😡。

That's the way the game。讲。嗯。So。This means that you know this is it's a funny funny sort of thing。

 so I look at the rules and I go okay。So buying a coffee shop costs me a million dollars。😡。

Buying an espresso cost me $1。This is after the great espresso adjustment of 2024。Um。

 so I should buy 9009099，999 plus。😡，And then I should just pumpunk down a million dollars by the coffee shop。

And then the adversary goes， oh， thank you， good boom meteor。系。嗯。But I want to think that， you。

 meteors don't pay attention to how I spend my money。

I want to think about an oblivious adversary that looks at my algorithm。

 but not at my behavior during the algorithm， then there's a possibility of beating that competitive ratio to using randomization。

😡，So what can I randomize here？What can I do instead of？Choosing how many days to rent。

I can randomly choose how many days to rent okay I can roll an infinity sideed dye with weird weights on it and if it comes up before four then I rent for four days if it comes up at 19 I rent for 19 days and will wheat and I buy immediately。

Okay， so let's。Imagine that I take。The algorithm rent i times and then buy with。Probability。

Pieace of eye。And just I don't know what piece of all is yet， you have to figure that out。系。and then。

The expected cost。Now。For this which depends on the unknown time to you when the world ends。😡。

This is the sum over all I。Have P sub I times the cost of the algorithm that rentsi times。啊。

And you can write this out。Again， as a funny sort of。See that's t minus one。😔，P of I times i plus B。

Plus something like equals t up to infinity of P sub I tos。

And I want this to be less than c timesaught。我好似。Okay。This。

Is what we are trying to optimize and what you choose？valueue线。And it's used the value seeing。

So that for every possible choice of tea， this new quality is satisfied。😡，Yes。

So I have these variables， these things that I don't know。😡，The probabilities P0P1223 and so on。

 and this other variable will see the competitive ratio， I don't know what that is。

And I want to choose。😡，Those variables， oh， and I want to， you know。

 see to be as small as possible subject to these things。That。Well， I is known。

 B is known and for A fits Tt is known。An opt is nothing。So this is a linear。Function。

It's the variables that we don't know。And I have one of these inequalities。😡。

For every positive interview。And I'm trying to optimize one of those variables。😡。

So this is an infinite dimensional。Linear program with an infinite number of constraints。Oh god。Okay。

 it turns out though， thats why。Thinking about how the strategy is going to go， we can simplify。

This downs to a finite dimensional program。So。One of the arguments goes like this。O here。

 that's not as simple as it's either going to be T or B， whichever is smaller。

So for small values of T， the right hand side of that what the adversary pays is T as T increases。

 that's what the adversary has control over， the adversary increases T。

 they pay more and the algorithm pays more。And so it's not really clear what to do。

 but as soon as the number of days that the world lasts exceeds the price of buying。

 the adversary costs stop going up。The adversary just buys on day one。

I decide the world's going to last for a long time I'm just going to buy on day one， that's my cost。

 but the algorithms cost this expression over here on the right continues to go up。😡。

Even this thing on the right， it's not necessarily clear。

 but this thing on the right is increasing frequency。😡，系。This。Increases。With tea。

So the adversary can think， okay， I don't know how long I should let the world last。

But if I'm going to let the world last more than be days。There is no advantage to me。

 the adversary to end in the world。😡，I may as let the world go on forever。

 and I might trick the algorithm into being stupid and renting for even longer wasting more of their money。

😡，Okay， so observation one。The adversary。Once。Either T to be less than B。Or T to the infinity。Okay。

Okay， now I have to be a little bit careful what I really want to do is right this is over opted instead of that now that expression over on the left makes sense in the limit even when she is。

对。Which means now I only have B constraints strengths。Not an infinite number。

But the algorithm knows this。I know that if the coffee shop lasts long enough for me to buy it。😡。

In principle， the world's never going to end。😡，So the moment that I've noticed that the world has lasted few days。

 I should buy now。😡，Rather than rent forever。Okay so there's no advantage to the algorithm。😡，For。

Renting more than b minus1 day。😡，喂。Thean algorithm。啊。iss。Better is。

P of I equals zero for all i greater than equal to B。系。So。This means now。That I can chop off。

This and just turn it into a be。Actually b minus one。And now I have。Be in France。月啲。

Plus sorry B constraints would with b plus one variables so okay so now what I'm left with。

Is a linear program。With。B。Inequalities。Plus。Plus one equation。

 which is the sum of the PIs has to be for the one has to be variables。the probabilities。

Make sure I get this right。sorryrry， B plus1 variables。Okay。

 so the things that I don't know are the probabilities of the algorithm。

 which are only going about to the920。And then what the actual competitive ratio see sits on the right hand side of it。

Okay。嗯。Well， if I got need variable b plus1 variables in B plus1 constraints。😡。

Now there's an implicit constraint there that all of the piece of I have to be non negative。

 so there are assign constraints attached attach。But it turns out that you can show that in the optimal solution for this one of your program。

 none of the probabilityba is equal to zero。😡，And that means what you actually get is not a set of B in qualities in one equation。

 but the optimal value is determined by a system of B plus one equations。你句话错人呢。そ。对。

Now I'm not going to go through the solution in detail， so optimal。Basis。Has all。

P sub I greater than zero， you know up to。So I solve the B plus one by。Because's one。Mo your system。

And what you end up with in the end。Is that the optimal value of C。Is this monstrosity？Okay。Okay， so。

In particular， the probability that you the best possible choice for the probability of waiting till the very last day to buy。

😡，Is this the thing？And then previous days you're less and less likely to buy so you've geometrically increasing probabilities for when you want to buy very little chance of buying on day day one。

 slightly larger chance of buying on day two， it grows exponentially up to day e minus one where the last term is this divided by B。

😡，系。And then you normalize the sum of those things being for one and you get so E overe minus one。

That's 2。7 over 1。7。Which is。Lessson two。Anyone have a calculator？Yeah， yeah， 1。5 ish。1。58， okay。

So better than a factor two， so what I should do is every day when I go my coffee。U。

I should basically。What is it I should start with a million dice in my pocket and I should leave one die as a tip。

And when I run out of advice， I should buy the coffee。Yes。对。那你是明白。

I'm assuming I can freely generate th。This is actually， I mean， this is this。

This sounds like a silly thing， but it's not so in particular some online algorithms for things related to paging。

嗯。We know the optimal algorithm in terms of the competitive ratio。😡。

But actually running that algorithm requires solving an anti problem。

Because we don't care about running time。😡，I don't actually care about the time to generate these probabilities。

😡，I'm only interested in what to combat des。So you get these weird。

sortrt of caching paging scheduling algorithms where this is the best possible algorithm and you will never。

 ever run it because the time to figure out which page to reject，😡。

Is larger than the time you spend missing the page。😡，And so now you get into slides over。Well。

 I can get a slightly worse competitive ratio， but now the algorithm runs in linear time instead of exponential financials。

嗯。And now we're doing engineering。We've got multiple competing criteria that we use to judge what we're building and we choose the Web tradeoffs。

Based on the tasks that actually got。So sorry， yes， engineering does actually happen even in。Yeah。唔分。

So everything's done in terms of the ratio between the cost remaining cost。

So if I increase the cost rent， but we the pass by fixed， that's the same as even cost rent。不ふ不。

And so that does have an effect here， but as long as the cost of buy is bigger than I don't know。

 three or four。This is within 20% of the blood ratio。And it converges pretty quickly if you days。

Yeah， that' only have a deal with her distribution from like， let's say，5 percent7 and my V is three。

我嚟。So you could play the game in the other direction where the adversary chooses a distribution of the value of T。

And now you want to design an algorithm that will optimize your competitive ratio， knowing that。U。

 so the nice thing about this linear programming formulation is it comes with its own proof of optimality。

So this is the solution to this linear program。The linear program is basically saying。

 what is the best choice for my distribution of piece of eyes？😡。

So that in this game that I'm playing with the adversary， I can minimize my cost that balance。

The dual in your program describes what is the best distribution of values of T that the adversary can choose？

😡，So that if I knew that distribution， that I should pick I so that it minimizes that ratio to be trimist。

😡，And because the duall of any linear your program has the same optimal objective value as the original LP。

But I get exactly the same expected payoff by solving me in the opposite direction。

That gives me a certificate that。There's no better randomized algorithm。

Then the one that follows this。So this is exactly like the setup in the last homework between Alex and Bo。

 where Alex is the algorithm and Bo is deciding when the world is going to end， Bo has the bomb。

And here what I'm analyzing is what probability distribution should Alex use？

Knowing that their distribution will be posted publicly。😡。

And then Bo's best choice is to set the bomb off on a particular day and in fact， for this。

 because all the probabilities are on zero， it doesn't matter when the bomb goes off to commit de gracious descent。

The duel tells you now Bo wants to set the bomb according to some randomized schedule。

 knowing that Alex is going to do something。😡，And you end up with exactly the same competitive ratio。

And that argues that in fact both of these strategies are optimal Alex's strategy is optimal in terms of minimizing this ratio。

 both strategy is optimal in terms of max。对。Please do not blow up any coffee shop。

Any other questions？So on Thursday， I will talk about S trees as a competitive outlook。All right。

 thank you。Thank。Okay。

![](img/cca5c0f21180c80d19b6e9e1483ee7bf_2.png)