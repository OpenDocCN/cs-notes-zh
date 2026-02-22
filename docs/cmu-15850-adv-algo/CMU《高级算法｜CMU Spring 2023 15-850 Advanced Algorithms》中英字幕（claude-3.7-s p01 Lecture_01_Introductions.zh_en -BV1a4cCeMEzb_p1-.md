# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p01 Lecture_01_Introductions.zh_en -BV1a4cCeMEzb_p1-

啊。Welcome， everybody。And how are you guys doing？Thank。ok。啊。So welcome to 15 A 50 advanced algorithms。

 Anopam Gpta， Anopam G at CS， also A G at Andrew if it is easier。😊，嗯。

So you can send me mail if you want to get in touch with me。

 piazza is the easiest way really because so if you have something to do with the course just posting piazza and we'll be monitoring it。

 I'll be helped with by my T Madu Suan he's not here today he's coming back and I've forgotten his email ID which you can look at her。

😊，Computers do wonderful things nowadays。诶。The course web page is 15850 That's0。

 All the lecture notes are going to be there。 I'm going to try to put put out lecture notes for all the courses。

 the lecture notes for lecture one are already there。 These are based on。😊。

Describe notess and other material that people have written over the past few years。

Previous incarnations of this course， so if you see problems， bugs， ambiguities。

 please let us know and we are happy to fix things。😊，because， you know。

 this is a resource that will be useful for students like you for the future。😊。

So and I will also put a whole bunch， you know， okay， not a whole bunch。

 but a number of links to various things to original papers to other sources for the same material。😊。

You're not supposed to read all of that。So don't worry you aren' supposed to read all the 20 papers I put on there。

 but you can if you want。You know， this is a graduate course I'm expecting you to be。

Kind of matureier about it。 You know how to learn things， right， And I'm just here to help you learn。

😊，So if you you know， figure out the best way you can learn the material。

Or to go beyond the material， because really， this is an advanced class。 and I want you to learn。

 you know， this is for people who want who love theory。😊，And who want to know more about algorithms。

 more about theory， this is in some sense， okay class started because we wanted to come up with an algorithm with the algorithms course that was the theoreticians algorithm course。

😊，If I am a graduate student or an undergrad wanting to do theory。

 what kind of algorithm should I learn？So that's the philosophy behind the course。

So that also means that， you know， I'm probably not going to give you a whole bunch of motivation why are algorithms important。

 I assume you know algorithms are important。😊，I'm just giving you the algorithm。

 I'm giving you ideas as many as I can。Some of these ideas are very old today's lecture is going to be a material that started in almost 100 years back。

 1927。😊，Some of the ideas are very new， so in four lectures we'll talk about the best paper winner from the Fox 2022 conference。

And you know， I'm hoping that you'll understand it because it'll build on ideas that well have seen in the first four lectures。

So very new， very old。All， you know， between classic algorithms。Modern algorithms。

 combinatorial algorithms，2 algorithms， all kinds of algorithms， really。

 its algorithms that I think are important and algorithms that I find fascinating。😊，At some level。

 that's the best I can hope。So， that is the course the course web page is there materials are there look at it if links are broken chances are you know sometimes links get broken between years and sometimes I screw up just let me know I'll fix things。

😊，The lecture， as you know， are Monday， Wednesday， Friday， it is three days a week。

 one and half hours each。😊，And we learn after 27 lectures because， you know， I'll run out of steam。

 You'll run out of steam， probably。But but we'll see how it goes。

There is one week where I'm traveling， so we might have a little break in the middle。😊，嗯。

Theyre going to be about six homeworks， homework0 is already on the web page。

And some of these will be solo， some of these will be collaborative。😊，There are， you know。

 detailed policies written， you know， how how do you submit this grade scope。

 this that and the other， just look at the web page。

 hopefully it'll answer your questions otherwise ask compared answer。😊，对人。What else？Questions。

Yeah we thes purely on the six homework the gradings purely on the six homeworks and in some sense class participation a little bit so oh I do would I would like you to come to lectures we are taping so there is a temptation to just sit in your you know in your room and watch the thing but it's less interactive because you can't ask me questions if you get lost you get lost if you you know zone out for a little bit you get lost you can't turn to the person next to you and ask hey what what's happening out here。

😊，So。😊，I'm not going to be very sort of particular about taking attendance， but if need be。

 we take some attendance。 we'll figure it out。What else？We good。的。

And if you can't understand what I am writing because you know， I tend to scrub this let me know。

 And also if if this， if this thing preventing you from seeing stuff， let me know okay。😊。

So let me get started and in fact let me just tell you what's going to happen there's going to be like 27 lectures or so。

 so what's going to happen is about the first 10 lectures are going to be classical algorithms。😊。

And by classical algorithms， I mean these are algorithms that probably you know your standard algorithms textbook covers。

 what I should say。😊，The standard algorithms textbook will cover the problems， not the algorithm。

For the problems that youve seen for minimum spanning3 I not Im going to talk about the algorithms that are there in your standard textbook。

 but Im going to talk beyond that。😊，For matchings， I'll give you five different kinds of power。

Things like this。Then there's going to be about 10 what I'll call sort of modern algorithms。

you know modern as you know in the eye of the beholder and and then after that there are a few lectures towards the end there are going to be three or four lectures where its listeners's choice so I'll ask you guys what you want to listen to I can do a variety of topics well see which ones you are most excited about and we can go from there。

😊，Now， some of these sort of answers that you give me will be guided by what you've seen in the course。

So， you know， I， I won't ask you right now。 I'll ask you in a few weeks from now。嗯。So with that。

 if there aren't any other questions。They are very quiet。Perfect， but please do ask questions。

I do best when people are asking questions。So today's lecture is going to be about。

Minimum spanning to talk。咩你冇唔。Wait。Also known as MSPs。

How many of you have seen an algorithm for minimum weight spanning trees？

 How many of you have not seen an algorithm for minimum weight spanning trees。O。

So if somebody tell me the name of an algorithm for MDs。Crasical sound。Brims。rovka。Other랑。Any others。

ok。These are six classic algorithms， almost all algorithms textbooks were their salt well talk about these three algorithms and these algorithms were developed almost you know 75 years back50 years 75 years back I would say Borovka's algorithm was developed and I even looked looked it up 1936 so that is almost 100 years of Bfka's algorithm。

😊，Brims algorithm actually was developed by Yns。😊，That's an odd。In 20。No，30。

This gentleman saw Booff Kaazal and said it's too complicated。Let me give a different algorithm。

 actually， it was just that Borovka presented his algorithm in a very complicated way。

 The algorithm is very simple。 We will see this in a moment if you don't remember。😊。

but Yni gave a simpler algorithm， which later on came to be known as Prim's algorithm in 1930。

 Rusll gave an algorithm in 1956， I think。😊，And each of these algorithms probably has been reinvented by other people so I'm not going to go into the history。

 you know I talk about it a little bit in the notes， you can look it up on Wikipedia。

 you can do a much better job with this in my it's actually kind of fascinating how algorithms keep getting reinvented good ideas。

😊，呃，不。So all these algorithms， by the way， do you have a sense of how fast these algorithms run？😊。

More or less okay so maybe I should give some notation right before if you are going to talk about maths we better give some notation Im going to assume that we are talking about graph G。

 it is an undirected graph。😊，Undirected graph G， ver0 season edges。

 Im always going to assume that the number of ver season and the number of edges is M。😊。

I'm going to assume that the edges have weights。😊，The weights are not negative。

 this is without loss of generality for this lecture， the weights are what else do I need to assume？

😊，Oh， so I'm going to make two assumptions and these are also without loss of generality pretty much。

 but yes they will make my presentation much easier。 Im going to assume that the graph is simple。😊，啊。

So a graph is simple， there are no parallel edges。Because if there are tinyal edges。

 you're going to throw away all the edges except the minimum weight edge。

And there are no self loops because youre going to throw away self loops。Okay。

 this is a simple graph。 And I'm going to assume that the weights。I distinct。

All the numbers are distinct。Okay。And。对。So far the burn。By the way。

 I am not giving an example of minimum weight spanning tree。 I'm almost not defining it right now。

So given a graph， I am interested in the tree such that the edges of the tree are a subset of the edges of the graph T is connected。

😊，So。And spanning。So T has n -1 edges。I'm summing up the weights of all the edges in T。

 I want to minimize that object。Right， we all know what an MST is。 If not， please ask。

 and I'm not trying to。Pro my intimidation is not my intent。good。OK对。😊，What else。

 So that's the that's the object we are interested in。 And all these three algorithms give or take。

 I'm going to maybe go into the details of the running times of these algorithms。

 These algorithms run in approximately order M。😊，老下。



![](img/f722401047b71d6015311d113f16e804_1.png)

We will look more carefully at this， but M log n time。And for a long time until you know。

 about 20 years or so， people were not worried about this and log in time was perfectly fine。😊。

Then in the 70s people started looking at， oh， can we do better？😊，You know。

 clearly I have to look at all the ages at least once。

So that's a linear amount of time that I need to spend on this。Actually。

 when I say clearly it is not completely clear， maybe you know you can do something smarter。

 but if you think about it， you have to look at all the edges。😊。

You have to look at linear number of pages。

![](img/f722401047b71d6015311d113f16e804_3.png)

So good。 So they the lower bound of omega M。With an upper bound of M log N， where is the truth。

So in the 70s， some progress was made and yeah， this is not the best use of the board。😊。

But let's go with this。 So Andy Ya in 70 something came up in an order M。Log， log， and。

I'm not going to talk about this。You're going to solve this。In your homework， next homework， I think。

 probably。Okay。啊。And then people said， oh， can we do better。And then。啊。Fredman。And Dent。

Gave an order， M。long。Start。What's long Star？Log star of n is the number of times you will apply log。

Until the， you know， the result becomes less than 2。So， you take log， then you take log of that。

 then you take log of that， and you keep applying log until the number becomes smaller than two。😊。

Log style is the number of times you did that。Very tiny number。So the log of the log star of two。

It's about seven or eight， whatever it is， right。老见。That's a huge number。 logg star of this is7。

 I think。对。The fragment intelligent showed how to get Ms to。

Some of the dudes actually came and showed M log of log starren。😊，In case you're wondering。

 but you know， that's not important then。😊，The current world champion is something else， but。

There's an algorithm due to David Car， analyzed by David Car by client and tar。

They wrote a joint paper。Who gave a linear time randomized。Okay。This was， by the way， in the 90s， no。

 was it in 90s？对对。96。Yeah。This is the current state of the art。Well。

 the current state of the art is a slight improvement on this you to Bernardzell。

 he improves this to some other slightly smaller function， not important right now。😊，嗯边。Good。

 so what this algorithm can do is that it will flip some coins。😊。

It will make some random choices and will output a tree which is guaranteed to be the minimum spanning tree。

 but the amount of time it takes。😊，Is going to be random variable。

And going to depend on the random choices， the order end that I have written is unexpected is the bound in the expected random time。

😊，Good。So one of the things that we will see is that randomization is a big resource。😊。

It can help us solve problems that we don't know how to solve otherwise。

 we currently do not know a linear time。Algorithm for minimum span tree。

You solve it willll give you a PhD right now。Open problem number one。's say tough open problem。

 It's like when I started grad school， or actually， even before that。

 there would be the books of Aho hopcraftft and Alman。 They contain grade open problemsm。

 One of them is the P and P problem。 It's like open problem show that P equal to MP or not。😊。

So this one might not be thated up， but you know it's a worldy problem。A deterministic algorithm。

For MST， which runs in linearium time。Anyway。So， what is the what is the plan for today the plan for today is Im going to tell you。

 Im going to remind you about some of these algorithms。

I want to show you a fragmentman intelligenceence algorithm。

And I'm going to show you the target line tors now。We might not go through all of this。

 but maybe we'll spill over next time。But let me go with this。Revision， fragment Ta。Ggo bank charge。

The plant's good。Questions。It's crazy。Okay。Yeah。We to check whether。Good， excellent question。

 excellent question yes。😊，And it can be done in linear time， but it's not trivial。

 I all to this in just a moment。嗯，嗯 maybe half。So the question in case you missed it was。

 suppose I gave you a graph and I gave you a tree。 And I said， this is a minimum planningning tree。

 guys。😊，You don't quite believe me。 You want to check。You can run the algorithm。

The minimum span algorithm and check whether the answer you get is the same。

 but can you do it faster or can you do it in linear time。😊。

Because if you can't even check whether a given given spanning tree is minimum weight。😊。

How are you going to find it？嗯。So yeah， we don't know。 as in we know。It's a linear time。

But we don't know all linear time algorithm define them。But what else？So far as a good。Good。

So let's just very quickly go over。Some basics。So fact one， by the way。

 if the weights of the graph are distinct， then there is a unique。Anesty。This is an exercise。

 Think about it， if not ask on piazza， really。明啦你即给你交别嘅。So from now on。

 I'm going to talk about the MST instead of AT。对。In order to find minimum spanning trees。

 they are essentially， yeah。回看下。All these algorithms will work without a distinctness。

 just my proofs will become much easier。😊，Or not much easier。 Therell be just， you， less ambiguity。

Good。So there are two rules。That we use to solve the minimum spanning tree problem。

One of them is called the。Go。By the way， very often I won't write down all the text that Im saying because Im not breakfastfa writer。

 but so if something is ambiguous， please ask， slow me down。😊，What's the cut。So the cut rule says。

 take your graph。😊，Take any partition of the vertices。😊。

Look at all the edges with crossover this partition。The least the edge with the least weight。

Is in the。Minimum spending rate。Edge， so I'll call this the lightest edge。Acro。Any你。Cut。对。

And cut is given by S and S complement。As as compliment。边。嗯。

The moment spanning tree contains the lightest edge across any part。This is known as the cut rule。

 some people call it the blue rule as well。😊，不れ。喂。And there's another rule。Go the cycle。

It says you have your graph。Take any cycle in the graph。 This is a bunch of edges in the。

Call the cycle C。The heaviest。Andnge。嗯嗯。晒个。C。Not。硬币。This is all often called the red rule。

So the algorithm， you know， one abstract algorithm is take your graph。😊，Find any cut。

 Find the cheapest edge across the cut， colored blue。Find any cycle。

 take the heaviest edge on the cycle color right。😊，Just keep applying either of these。

Until your graph has only blue edges。Blue and red edges。 Every age is colored。

What you'll be left with is the blue spanning train。Okay。嗯。Let's look at a couple of examples。 okay。

 actually， let's prove these things。Very easy to prove， let's prove。嗯。Let's prove the cut rule。

I want to say the cheapest edge across this cut。Is in the MD。Suppose not。 So suppose the MS3。啊。

Looks like。Theres whatever。It might have several edges crossing this skirt。 It doesn't really matter。

嗯。This is the cheapest edge across the annesty。ok。So add this edge to the MST， it creates a cycle。😊。

B cycle。Is crossing this cut once。It must cross it again because you know。

 if we started on the south side。We crossed over to the north side。 now we are on the north side。

 Eventually we have to end up at the south side。So we must cross over the river one more time。喂。

This edge。Is not the lightest edge across this cut。This edge was right。

 So what you could do is you could add this edge in and remove this edge。

Removing an edge on the cycle is not changing the connectivity。对对对对。啊，没有没。Thank you。20。你个。

That's the country。The cycle rules almost exactly the same。So I have， I have the cycle。

 I want to talk about the heaviest edge。In the cycle， this time， red is a good idea。

I want to say this edge。Suppose it happens to be。In the。Suppose it happens to be in the MSD。嗯。

I'm going to delete it from the MD。So the MST was looking something like this。 It had this edge。

 and it had a bunch of other areas。If I delete this edge from the MST。I want to get a cut。

The tree will fall into two parts。Okay。不是。Now， this cycle is this the cycle that I have in mind。

Was going from the north side to the south side。Well， it was actually containing this edge。

But if you remove this edge， the rest of the cycle goes from the knot to the south。

So the cycle must cross。The river at one point。That edge has a weight which is less than this red edge that I just removed。

😊，And if you add that edge in。It's going to connect with two sides。嗯。

And you have a tree of less weight。So the original tree could not have been the MD。Yeah。Thank you。

Good， ok。And once you have these two rules。You're in great shape。In fact。

 all the spanning three algorithms we know， in fact， the ones we see today。😊，Are going to use。

One or both of these rules。Most of the classic ones use the cut rule。

Carter's algorithm is going to use a cycle rule as well。Yeah。So lets look at， lets move this guy up。

And let's do the three classic algorithms。 you know， if you guys have seen this before。

 so I'm going you know over standard materials， but hopefully this will be useful nonetheless。😊。

So the first algorithm let's do is Bka。B as algorithm， if you remember。

 starts off with every verortex being an isolated component。😊，Okay。In general， having done that。

 in general。At any point in the algorithm。You'll have a bunch of components。And what are you doing。

 You're looking at the edges that are coming out of。Each of these components。Actually， you know。

 these edges should really be going between components， right。

Because these are all the vertices of the graph。I've already connected up， and this is where。

Glue would have been useful。These are edges that have already colored blue。They form components。

And now Im looking at all the edges that are coming out of this component。😊，Im going to choose。

The cheapest edge coming out of this component and color it blue。Color the cheapest edge blue， color。

 the cheapest edge blue。嗯做完。Notice that this edge that are colored blue is the cheapest edge going from this component to the outside。

😊，So this is the blue。I'm allowed to do this。Right。So for every component。

 I choose the cheapest edge coming out of it in a colored blue。😊，能。

And now these give me new components。 and I keep going。Clearly。

 this is in RamD because of the blue rule， the cut rule。😊，没。不。How much time does this take。

 by the way。So the observation is the following。 So firstly this is a very good algorithm。

 this is a parallel algorithm for computing MDs。😊，Each time my claim is going to be。 The claim is。

With the number of connected components。Connected components house。At worst。

Each time the number of components。 So each component which is sitting around。

If the next step is connected to at least one other component。So in the worst case。

 these components are going to pair up and well have half the number of components。In the best case。

 all the components will coalesce together in one。So the number of components hal in each round。

Therefore， att most log base to of。Ls。And here is another claim。那 down。Implement。呃一 round。嗯 all的。

Requires a little bit of thought。And requires， you know， just working through the details。

 I'll give this as an exercise in your next homework。嗯。はい。So order M time per round， log n rounds。

 M login。ok。意。没军。Okay。ALo lot of guys allocate in 1926。嗯。Yeah。

 in paper I actually try to some people have done a translation of his paper from the original check。

 it's a complete pain to read it you know。😊，Yeah， I mean， it just comes with。

 we have enough terminology。To read these things。嗯。To to write these things as well。

 to explain these very compactly。He was doing it from first principles。可以。Let's do the next one。

Crascals。You remember what Crco says？Then our sort edges。And。In可以荐。Wait。好的。

So w of E1 is less than in less than W of E2 is less than。W ofPM。系。And then we say for。

I going to from one to M。嗯。F e i。Gect。To distinct。Blue。Components。嗯嗯。哎对对。I in color。Yeah。系。在对。

That's the algorithm。行。What are we doing at each time？We are looking at the E EI。

 and we are seeing does this edge EI。Connect to blue components。嗯。If it does。

Then these two blue components， you know， all the edges that are coming out of this。😊。

Blue components。Have weight because they've not been considered。They have weight EI or higher。

Yeah I have the cheapest edge。That's going across this country。Blu rule again。So by blue rule。

 whatever cut rule， cross scale is correct。😊，How much time does it take， I'm going really fast。

 by the way。Slow me down if you need me。是。But in fact， some of you might think I'm going very slow。

 in which case。Itsありす。啊。OK。Crasll is correct。😊，How much time does it take。Yeah。周。Excellent。

 so the first step itself takes order andgging。😊，Oh an M and N， by the way。

 since the graph is simple。This means that the number of edges is atmost n choose2。

 which is atmost n squared。So log game and log game are pretty much the same。

How much time does it take to do this process？Okay。And as comes in。

 I need to figure out whether it connects to distinct blue components or not。I mean。

 if you use this something like this one set union get excellent， excellent， much less。

Wwhichch is much left than log。 So what you are suggesting is that I should use you know。

 one thing I could do is I could at each point in time look at EI。

 look at the blue components and try to see if。😊，This vertex of EI， U and this vertex v。

 they lie in the same component or not。😊，I could do this from first principles。

 but it will take me too much time， so I should use fancy data or not not even fancy just smart data structures。

😊，So this is the union find data structure。And you find the data structure， you know。

 in the sort of jargon of the day， its API consists of three operations。😊，Make sense。

It creates a set with a single element。😊，Okay。😊，And then you say， find。二。

It returns the name of the set。😡，That contains east。And then you say union。E andF。

It takes the sets that contain E and the set that contains f and unions them together。😊，谁。嗯。

And so really， what I should do is I should， instead of writing。The lines， I could say。If。

Find of you of EI， let's say， EI。Is U V， I say find U is not equal to find。Then。有年。有。

Im maintaining the connected components， the blue connected components。Using this data structure。诶。

How much time does it take？To implement these operations。In our undergrad algorithms class。

 we give some union find data structure that ensures the following thing。😊，If you are doing。嗯。

If you're doing M operations。爱。And elements。Now notice that every time in order to do an operational on an element。

 you better make it with that element。😊，So M is at least n。Then， the total runtime。

Is at most order M。Lm star。Remember， the log star function。It's even slower growing than log。

So this is very small。In fact， one can do better you can replace this by something called M alpha of M。

 this is something called the inverse acromen function。😊，Which maybe well talk talk about two。

That's not really my。This is even better than this。ThereSome very nice properties out here。 Actually。

 why don't I tell you what the inverse attachment function as。So the affcromen function。

We can use this board。对。So let me define the acromen function。So the acroman function is going to be。

It's going to take two arguments AN。Okay。And it's going to fill up this table， right。

 because it's it。都百也不多。So， this。So this this is you know嗯。Entry 1，2，3。

4 in terms of use a different color，1，2。3，4，1，2，3，4。5 and so on and so forth。The first row is2，4，6，8。

What are these the even numbers？啊，对。The first column is all two。嗯。This entry。Take this。2。

And goes to the previous row and looks at the second argument。这在。This entry says four。

Goes to the previous row and takes the fourth argument of it。That's it。16。合力度。What's this。多了地下。

Same principle。This takes this the second entry of the previous row。不。

Fourth entry of the previous row。16。16th century of the previous。It's 2 to the 16。

To the tour the tour the。This is come coming up with two to the two to the two。And dance。

there tower of height and。This guy is growing as fast as this you tower function。

 whose inverse was the log star function。😊，This guy starts to4。What is this， Oh， by the way。

 the fourth entry， this is 65000 something。So this is due to the。啊。this is 6500。s five。

This is going to be a tower of 6500 night。So this is just the fourth row of this。Yeah。😊。

The ackermen function， I mean， there， there isn't the ackerman function。

 There are a class of functions called called ackermen functions。 They are all pretty much same。

The function that we are talking about is a diagonal。It grows faster than any given growth。

So the inverse goes super slow。Slower than log stars， slower than whatever this this next beast is。

That that。For all practical purposes， less than5， I think。嗯。Yeah。But。We have already lost the game。

 We have already spent M log star M out there， and we can spend some order M。😊。

Also we've lost M log M out here， we can lose M log star M or whatever M alpha M。

We've lost the game already。We should do something better。Sadly， Prince is not going to quite cut it。

So let's go， and let's do。Prim out。The grim sound algorithm。

The last of our three classic algorithms I'm going a little slower than I anticipated。

 but it doesn't really matter as long as you guys are following along you aren't bored right。😊。

Not yet。ok。Okay， let's do。What does clean algorithm do， it takes a single verortex。

 let's call it the root。It looks at the cheapest edge coming out of the root and color set blue。

 this is the cheapest edge coming out of the component consisting of the single vertex the root。😊。

At some point in time， it has some component。Which is spanang by the blue edges。

It looks at the cheaperest edge coming out of this component。And colors the。This keeps growing。

By the blue rule， this is correct。GoodHow much time does this take？啊，你。Mloggging。Why。

So the question is， how long will it take to figure out the cheaper edge crossing this cut？😊，Yeah。

 how you can have a heap data structure In general。

 you can have a data structure called a priority queue。

What is the priority Q data structure it contains。😊，You know， what's the operations。

 the operations are insert， insert。An element。 you know， let's say V。Insert an element。E with。Wait。

两辩。Okay。And now I can ask things like fine men。Actually， let's do this operation called deletete Min。

😊，It's easiest to。Delete men just says of all the elements that are being inserted so far。😊，You know。

 remove the element with the least weight。嗯。And let's also have。An operation called decrease key。

 which takes an element and a new weight in W prime and sets the。😊，So the new。

Weight of E is equal to min。Of its current weight。NW。Decrease key just says， you know。

 make the weight of E。Be at most， W。Yeah。If it weight， you know， I say suppose e5。

 if the weight of e currently is 3， this will maintain it to be 3。😊，But if its weight is 20。

 it will make it to be fine。Are the operations clear。야换。一个。I can keep quick， okay。

It is a priority Q data structure。嗯。Let me give you one more because itll be useful for me。Actually。

 do I need it， I don't need it。That forget。You can use a heap data structure。

And do all these operations。In order。Login time， amortized。As then if you do M operations。

It'll cost you about en log。行。And so what are we doing out here？We are saying for every vortex。😊。

Before I did this operation for every verortex out here， lets say this verortex is v。😊。

I'm going to maintain a heap consisting of the cheapest edge going from this blob to V。

The weight of that。So every for every vortex。And maintaining。V， and this is， this will contain6。

 let's say。 So this just say with the cheapest edge going from this blob to V has weight 6。😊。

So for every vertex out here， I am keeping track of the cheapest edge going from here to that vertex。

😊，Some word he see。W， some ver is U might not have any edge going from the blue component in which case they have weight in。

And so when I am asking for the cheapest edge going from the blue component to any of the verortex outside。

 Im just asking you to。😊，Find the minimum out care。All you do is delete men。And then delete them。

な thisがでてね。ok。Now， what do I do。There might be edges going from V to U。

So for all the ages that are coming out of V。I look at its neighbors and I do decrease key corresponding to the rates of the。

😊，How many decrease key operations did I do。One for every age。That's Autogram。Yeah。

How many delete main operations did I do？One for every round， one for every vertex。That's N。

So I spent and。Log n up here。And decrease key I spent M。L and o。

How many inserts did I do linear number， right？Okay对。OK。So。

 overall m plus n log n and maybe implicitly I was already assuming that the number of ages was at least the number of vertices。

😊，这一次。About M log n overall。 So when I sum all these guys up， I get order。M plus N。有的。你看。弄文。

I should do something better。I need to prove fancier results like this， right。嗯。How do I do。

So in order to do this， I need a slight improvement on the data structure。And one of the sort of。

Things that I feel bad about in this entire course is I can't spend too much time on data structures。

 there's just too much other stuff to talk about。😊。

So this lecture is in some sense my one homage to data structure。And Im doing a poor job at it。

 but thats the way it is。 So let me take a two break and then we will come back and Ill tell you how to get this。

😊，And like five minutes and then we take it。So you know， this this is like a two break。

 you can stretch， you can get a sip of water， whatever you feel like， and then we'll start。😊，So。

So where are we？We just saw the three classic algorithms。Borrovka's algorithm。Cros skills algorithm。

 Pri algorithm， all taking approximately m log n time。Let's see， a slight improvement。Do。To诶 print。

And then we'll， we'll see how。Yeah， yeah， naively， you'll see a very slight improvement。

 but then you think about it and you realize， okay， this is， this is amazing thing。😊，Okay。

So let's do the following。We just talked about using a he data structure。

A priority Q data structure for doing print algorithm。

And the priority queue took log n time amortized all these are by the way amortized by amortized I just mean if you do M。

😊，Such operations will take you M times this much。It's just， its a pany word for average， by the way。

But， average in the sense that， you know over M operations， youll just average out of the time。So。

 what fragment intelligent came up with is this idea called Fibonacci heaps。

 a very pretty data structure and what it does is it makes。😊，Inserts constant amortize time。

Deeletement remains at log n amortize time， but decreased key becomes constant amortized。In fact。

 there are a whole bunch of other operations they they can allow all of them become constant amortized。

If you don't like amortized， there are future papers that make it worse case。

Every operation takes constant time except deletema。诶。Let's think back。

This algorithm prints algorithm that we did。😊，嗯。How many deletements did we do？And。嗯。

Decree keys were M。Yeah。The decrease key is now cost one。Delettements cost log n。

 So this already says PR algorithm。Can run in time order M。对吧嗯。Sliding blue。

If your graph is somewhat dense， bless you， if your graph is somewhat dense。😊，Then， en log n。

Is smaller than M。 This is linear。But if your graph is super sparse， then this is n plus N log n。

 still n log n。行。😊，Seems like a small improvement。But let's， let's， let's try to do better。

Let's do the following。 Let's， let's think。You know， these two things might be very imbalanced。

We should try to balance these out。How the heck am I going to balance this The graph。

 my graph is a linear number of edges。How should I balance it。喂。So let's do one thing。

 And this is a beautiful idea of Fman intelligent， same， same， same people。They gave this order and。

Long star。不打。So here's the idea。嗯。They say。Lets let's start off at some verortex。

Let's call it R for root。Let's start running Pri algorithm。行。

one thing I should mention is this is log not just of n， if the log of the number of elements。😊。

In the hipap。If you have a small number of elements in the heap。There's a better。喂。

So what they say is lets start running print algorithm out from here。😊，At each point in time。

 there are some number of edges， there are some number of okay， so this is the component currently。

There are some number of vertic seedss， which I'll call the neighborhood of this。

This is the neighborhood。Of the blue component。These are the vertices。

 which have edges going from the blue component。Suppose this neighborhood is upside that most K for some parameter K。

What is our runtime。And okay。But operation。Sampign log per operation。

So keep doing this process until the neighborhood， the number of vertic Cs in the boundary。

Become more than Ka。So far， for every ver that I've added in。但被动你落嘅。Fair enough。

But the neighborhood suddenly became too big。 What do I do？是道。Take another route。

And start your prim from there。Until this neighborhood becomes too big。

Im paying log cap or operation。是top。Start from somewhere else， start growing here。P。

This neighborhood， you know， this neighborhood is not part of this thing。

 This component was such that its neighborhood became larger than KB stock。

This neighborhood became too large。 We stopped。 This neighborhood became too large。 We stopped。

In fact， let's say this neighborhood， you know， I just added an edge to a previous neighborhood。

It's stop。Your previous component。Let's know。Okay。So when do you stop。

 you stop if the blue component。Have the neighborhood， which is too large。

Or it hit the previous previous glcomo。Okay。So far， circle good。

So whenever you have an explored vortex start growing out from there。You'll either stop。

your neighborhood became too large or you'd stop because you hit somebody else。

Suppose my neighborhood became large。What does this mean？There are K vertices in my neighborhood。好。

It means there are at least cages leaving my neighborhood。Okay。Every large neighborhood。

 every large component， large as large neighborhood component。As at least cage is leaving it。Okay。

Every component。That hit a previous component doesn't create a new component。 right。

 It's just become part of the previous component。嗯。So every final component that you get this way。

Is going to arise from at least one large component。Which had the least care just leaving it。Okay。

So the number。哦。Compons。If at most， how much。Let's do M over。

Each edge might be counted from both sides。 Im being pedantic， but。Okay。So what did you do。

 you took your graph， you build a bunch of these blue components。Now， like Borovka。

 you're going to shrink down each blue component。Get a contracted graph and proceed from that。Okay。

 so what what is the picture in your mind the picture is I had this graph I have a bunch of blue components that I found。

😊，I'll contract down each blue component。And work on the contract。诶。Yeah面打事故。Good。

 so the part of the exercise that I am asking you to do is to say given a set of blue edges。😊。

You can do this entire shrinking and turning it into a simple graph in time linear in the total number of edges。

😊，I'm asking you to make a leap of faith out here， but it's a simple leap of faith。I try to think it。

don't worry about it for the moment。 let's imagine that we can do this in linear。Okay。

So what did I do， I came up with a graph。I found some number of。Blue component。

When I come up with a contracted grant。I'll find some number of blue components I'll come up with another contractor。

验说完。So let's actually call the graphs G0， G1， G2， and so on so forth。は。

What is the number of vertices of the next graph， So the number of vertices。At time 3 plus one。

I that most。2M divided by k sub t。We just argued this， right？So for each level T。

 Im going to define a threshold case of T。The number of number of vertices in the next graph are going to be at most 2 m over k。

So let's just rewrite this okay。其实啲。Is less than 2 m。Over end。个出来。Arithmetic。

 I haven't done anything。对。This is one， this is one fact。Look at the graph G sub T。😡。

What should you send K up to。Remember， your running time。Is M。Plus， and。long。对这是这一点。

What should you do， How should you set case up。You should balance them too， right。

You should set M to be equal to anti log。Yeah。I'm sorry。不。停。对。Actually， you know what。

 I'm always going to upper bound this。😊，So let's not even worry about that。And in fact。

 I'm going to upper bound this by M， so I'm not going to worry about it。So， in fact。

 what I'm going to do is I'm going to set。M equals。And the。要。

And because I want the maps to work out nicely， I'm going to extent。

So the total amount of effort I spent in round t is this plus that。

Which is the same as this because I balance the two。嗯。What does this imply？借B。Is equally。哦，这里这 doMO。

2 m over n3 is equal to log。Let's just， I'm rewriting that。next。What is this。Kt plus one。

The log of that。If at least k。So threshold gay。Is increasing exponentially。Suppose I start K at2。

How many rounds until it becomes equal to n。When it's N， you know， this is just premium alcohol。

 I have no bound on the science。How many rounds will it need until Kt becomes equal to M starting at 2。

要求。Long style。Each round， I'm spending linear amounts of time。There are log star many runs。Yeah。Yeah。

Which of these algorithms are used in industry。 Now you're asking the tough questions。I don't know。

I don't know。 Chances are they'll be using an algorithm， which is。

Which has sort various characteristics， which is parallel， which has you know。

 very low overheads on the big O。 These guys have larger bigs。😊，Cubbonacci heaps。

 not so good becauses。 You might not want to use it in。Bomial leapaps， not bad。Yeah。Okay。

 by when you say like for two when people and wide5， does that mean that like it。

The number of edges is larger than that than just from the first Fiinacci deepap south。Its。那是我理害。

So one thing that I hadn't done so what I mean by this is really what I want to do is I want to define Kaie so in the round in round t。

I need to tell you how big are your heaps allowed to be。I should。 I should give you a parameter K。

Kating is the parameter for the theethone。And I'm going to define it exactly by this。

So Kt is equal to 2 to the M。DoM over。And that will guarantee that the total runtime。

Is equal to this plus this， which is really。😊，Up to bigger。啊。Other questions。Yeah。Really。

 the sort of problem with binary heap is that the decrease key。Is killing you。

And you're doing research。 So basically， you won't get this M。 You'll get this M log n。

So you're dead right off the bat。对这个这个这个。Yeah， so， if you work it out。

 somehow the first round itself is going to completely kill you。As always， in worst case analysis。

And we can say， well， how does it do in， you know， practice。 And that's a trickier question。

 Even formalizing the questions become trickyier。😊，Other questions。So okay， you know。

 what was the point， I So there， you know， maybe three points out here I want to make。 One is。

 this is a very slick algorithm。But at a higher level。

 this suggests a way in which you interpolate between Borovka。😊，And prims。

That's what I think they' are doing， right， When K equals 2， let's say。

All they are doing is they are just picking the cheapest charge coming out of a single vertex。😊。

And then after that already， the heaps are too big。I can't do anything。 Probably too big。

 There might be a single edge coming out， two edges coming out， but。

So Bfka is one extreme of this when K is really tiny。Prim is the other extreme， when K is huge。

And they are seeing， well， these two algorithms are kind of inter， you know。

 this algorithm is interpolating between these two extremes。😊，I find very pretty。Secondly。

 this is somehow showing how sort of powerful data structures。

 just this idea that you look at where you are spending all your time。😊。

You're spending M amounts of time。Only three keys。I want to beat this into the crowd。

It's like profiling， right， You know， some of you have written code， you know， professional code。

 You know， this is what you do。 You look at where your algorithm is spending time。

You improve those steps。This is beautiful book by John Benley John Benley used to be a professor out here a long time back。

 but then he went to Bell Labs and then he went Google， I think maybe he's retired now。😊。

So John Benley has this book called Programming Pearls。And it's， you know， he uses some。

 some archaic language from the 70s。 that's not important。

 The important thing is he takes a piece of code and he shows you how to optimize that。😊，And。

 you know， regardless of whether you do theory or not。If you are writing code。

 you should think about how to optimize。And he says， oh， you know， why is this line inside the loop。

 It should be outside。You' are running it so many times。

 You are redefining pi so many times while you wasting your time。Or， how do I balance this in that？

It's just beautiful。嗯。Yeah， he， yeah， anyways。Good。And in general。

 this also tells the story of the progression of MST algorithms。😊，How it started at timeloggan。

And then theres M log log and M log star。And now you can think about， oh。

 how would I improve this further。Because I do want you to solve that linear time MSD right。

That's the hope。 Anyway， do you have a question。这肯定C交付。

so so I'm being slightly imprecise out here if for a single node you can scan all its incident edges。

😊，We at least have two nodes in every component， absolutely。Good point。Because otherwise。

 we won't even get off the ground。是了。It might be Yeah， anyways。

 there might be a sort of even slicker way of doing this， but just do this part。

 Just have every component having at least two nodes。😊，Other questions。I'm well， out of time。

 But let me tell you。Let me tell you the main idea behind the car intelligent algorithm and we' will talk about it next time。

So one of the things that you have seen is that all these algorithms that I gave you。😊。

Really just use the blue rule。I just added edges。 I just made them blue。I never use the right rule。

I mean， I use the red rule only at the very end when I have a blue spanning tree then Ill say oh every other edge that I'm trying to add I can't really add so you know I'm kind of using the red rule in a degenerate sort of way。

😊，If it forming if an edge is forming cycles。😊，Then it must be right。like， come on， man。

 I knew that that wasn't in the Spanish tree。 Why are you boring me。

So what the car algorithm does is it actually says no， let's do something smarter。😊。

And let's use randomization。 Wells Kegan， this is the way with this place that I wanted to show randomization。

 right。So he says， okay， so so let's do the following。I'm going to find。Let me just script。

If you're tired and you kind of want to rest your eyes。

 you can do that next time we'll do the same thing again， but here's the main idea。I have a graph。

 What I'm going to do is， I'm going to make。I want to farm a tree。嗯。There' is a green tree。

It' is not blue， so it is not necessarily the MD might have some MD angle， but who knows。嗯Okay。

And now he says。Look at any end。 So this is like tree。啊。Look at any image。If this edge。

Is the heaviest edge on this unique cycle。That it。Parms with this green tree。It's red， right。

I can use the red rule and clean it。Okay。So what he'll do is。Step one， we will form。

So what you can do now is you can use。MT verification algorithm。And we talk about this next time。

To find all the edges which are heavy in this sense， which are red with respect to the green tree。嗯。

So， what do I want to do， I want to get rid of all these edges。

 so I would like to find a green trees such that most of these edges get thrown away。

 they become red。😊，Very quick。What's a good green tree？😮，What's the best green tree？The MD。

The chicken and egg， right。So let's do the following。So he says。Sample。好。毕也就是。O the。Then。And MD。

Po these samples。Why do you sample half the edges？😊，Because theyre half the ages。

If it's a linear runtime， then it will take half as much time on that half the edges， right。😊。

So there is some kind of recursion that's going on in his mind， you know， half the edges。

 there should be some geometric some going on out。😊，So let's just sample half the edge billion M。

 It will take half the time。嗯。明隔离。All heavy edges。对。坐等5位。So that you have very few edges remaining。

什不是车。Oh maybe this was间。つります this。And step4 is recur。哦哦。9。Beautiful。Yeah。

I sample half the edges of the graph。 I build an MSD on that recursively。 So I'm recursing。

 I'm recursing here。😊，えとりす。はい。And this is pretty much the algorithm。 I'm not hiding。

Almost anything from you。 I'm hiding a little bit from。And we'll talk about it next time。

And he shows， well， he didn't show this。 So he wrote a paper and he showed that this algorithm ran in M log in time。

And then client went and said， hey， we can do a better analysis。

And so they wrote a paper showing linear expected runtime。

 and then they wrote the journal paper together。So what we will do because I'm out of time today is next time we will make this formal。

😊，We learn like this。Anyways， I'll see you guys on Friday。😊。

