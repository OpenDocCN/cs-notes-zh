# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p24 CS10 Sp22 Lecture 24 (Apr 27)_ Conclusion and Farewell.zh_en -BV1BokLBmEKE_p24-

![](img/03267a86e37c2c37344653a6b9d6d609_0.png)

![](img/03267a86e37c2c37344653a6b9d6d609_1.png)

嗯。See， I need to turn Zoom camera。That didn't work。嗯。All right， there you go。With the final。It is。

 yeah， so please don't discuss anything until until Friday。

 we're not going to turn off Ed since final projects and other assignments are going on。

 but we will either remove or hide any posts reviewing details about the final exam if you have logistical questions whatever。

 but yeah， Nates will give you a link to the assignment。A a lab right when it starts。

You'll work on the directions and you'll upload the file to GrSscapepe。

And that'll basically be how it goes， but the final is set up such that the examples that we give you if you're block。

Ps the same value for the examples that we give you。

Probably means you got full credit unless you're doing something funny， right？

If we tell you that something should report like 100。don't write like if a equals this or part 100。

 that won't count obviously， but if you get 100 trying to solve it sort of the correct way。

 yeah that's how I go， we are going to ask you to use hydro functions to use recursion in a couple spots and that's required for full credit。

If you're like， I don't get this recursively， you can still get partial credit by solving it iteratively without higher order functions。

😡，嗯。You know there's opportunities for partial credit。And then the other final thing is。

 so next week we're going to do review sessions during lecture time。

I believe the Ts are going to do Monday。I will do Wednesdays， my Wednesday session will be review。

And also just wrapping up CS10 since we got kind of off by a lecture。

 normally today should have been a wrap up sort of what's next type deal。

 so next Wednesday I will do some review and some wrap up and TBD whether will be in person or on Zoom。

 but we do have this room。Reserve， so。With that。We're going to continue on from last week so。

We were talking about tractable problems last week， which are problems that we know how to solve。

 that sometimes it can take a little while， but these are things that we say are solvable in polynomial time。

 which means that they're either quadratic， linear they could be cubic。😡，You thingss of that nature。

 but therere problems for which。We can we can find an answer。In a reasonable time on our computer。

 so sorting a list， finding the median value of a list。は。'Doing most kinds of calculations。

Those are types of things that there are many， many。

 many kinds of problems that are totally solvable with computers。

 otherwise you probably wouldn't be here today。However。One of the things about computing。

 which is pretty cool， and this is again， pretty hard to conceptualize because。All of your lives。

 computers have just been there and been doing more and more things。😡，You might not realize。

 but there are an entire class， entire sets of problems that computers really are just not good at solving。

😡，And we sometimes call these intractable。Andnitially we call them hard problems because they are just actually hard to solve so there's a bunch of things that we can think about and what we're talking about here is the exact framing of the question will。

Sort of will matter and whether we mean a problem is solvable because obviously computers can play chess right and so the question is。

Given the test board below， is there a white move， is there a move that white can make that forces a win so you know if we say that's the game is this game is sort of in progress someone the middle the game。

 is there a particular move？😡，That light can make that forces， given all possible moves。呃。

NoW to win this game there is an answer to this right it's either yes or no。

There's a move that will force a win or there's not a move that will force a win。

 but a problem like this is。Actually， for practical purposes， impossible to solve。

And why is that it's because chess is such a complicated game that the space of roof sets is so large that if we say。

 well， okay， so let's see white has。One， two， three， four， five， six，7， eight， nine，10。

 1112 pieces still on the board， so they've lost a few pieces。Presumably。

You know their first move is they could make one of 12 different moves and it's actually if you know the rules of chess there's actually more than 12 possible moves right because there's 12 pieces and a bunch of these pieces can move in move up space so there's probably something I'm discussing like our first move probably has。

20 to 30 possibilities and then if Black makes a move after that。

 there's probably another 20 to 30 additional possibilities and that's already 900 possible moves for just and one of this game。

And if we try and calculate 900 moves times another 900 moves for the second round， times another。

 900 moves for a few more rounds， and maybe then it gets to 800 moves。

And 600 moves as we start knocking pieces off the board。

The space of that right just grows to billions and billions of possible moves that could actually encapsulate the state of a game of chess。

 and so this is a problem， is there a single move that means white is guaranteed to win？

But in that case， no， there's not this just too big。

What we're not going to talk about today is the fact that。😡，Outside of these intractable problems。😡。

We can guess at solutions right， we have computers that can play chess pre d well。

 but they don't guarantee that they don't ever affirm that the computer is guaranteed to win。

They just have some sort of artificial intelligence。Which is relatively good。At playing chess。

What we're going to do is look through a few common classes of problems。

That computer scientists use to classify the types of things。That。That we can solve so。美。

I can sort of do the math of yourself， and I'll take answers from everyone。

 This one is also on great scope。 So if you've already answered it and gone correct。

 you can just answer the correct answer。😊，That's cool。😊，But the question here is。

 suppose you want to take a maximum value。In items， so this is sort of a polite way of phraing this。

The other version of this is suppose you went to ro a jewelry store。

But maybe we should encourage that。And so you may take any number of each item。

 but your bag can only carry at most 15 kilograms， what is the maximum amount that you can get in your bag。

 you're robbing someplace。Why I to the ro example， because the is called the Naps。

 But you want to stuff everything in your bag。 You want to sort of maximize the value that you can carry within。

Some amount of weight。 so given the setup。We have。Un limited number of 4 kilogram blocks that are worth $10。

 unlimited limited number of 1 kilogram blocks with $2。I mean number is two kilogram block。

Worth $2 and a living number of 1 kilogram blocks， also worth a dollar。

What is the theoretically maximum value that we could stuff airb in this example。

 but does anyone want to vote for Can to get？It's the maximum that we can give in our bag $10 so someone want to have a vote for a and if you're on zoom if you want to take a second and just type in a letter A3 E in the chat。

 does anyone want to vote for a？Is the maximum value that we can get in our bag？

So we want to vote for B， can we get  is $15 the most we can get in our back？I vote for soup。没有。

can we get $33， is that the most we can get in our bag？Is $36。

The most that we could get in a bag cool， if few votes for 36。

 and it's $40 to everyone say that we could get $40 in a bag。😊，Cool， and a few more vote for Dean。

So let's see。 Did we。Is that actually now most people voted for D， which why is okay。

 so the way we can do this， so let's solve this correctly because I was thinking at do is the correct answer now the slide says that it's 40。

So。We have。W。Ied e bolded。So how should we think about this problem well。

 this is one of those classic problems where it's going to turn out that solving this in a bunch of ways can be really hard。

 but we about we can think about this question right？I've got 15 kilograms。

What's the general solution here that I think most people did， what block did everyone try and grab？

First to solve this question， like when you thinking about， yeah。

 the four kilogram block right because it's u not only is it worth the most money at $10。

 but if you think about it， each kilogram also happens to be worth。The most amount of money。

 so that gives us。If we grab three of those， that is 12 kilograms。And $30。

Which means we have three kilograms to spare。And I have no idea why the slide says for you the correct answer。

Because。It definitelyite。If I should be， it should be D。Which is。We take three，10 kilogram block。

 34 kilogram blocks， that's 10 times it' $30 that leaves us with。

12 kilograms in our back we have three kilograms to spare now what do we pick well we can pick some one kilogram blocks we've got these。

Gray and red blocks， obviously given the choice between1 kilogram at $2 and 1 kilogram。At $1。

 if you're maximizing the value， we don't really want any of those red blocks。

East thing in this case is just a free$1 kilogram gray box which gives us $ two times three $6 so in this case yes $36 should be our maximum value these are also the same slides the same side deck that was linked on website last week so we're just contained so hopefully Nor was super confused for a week about why the answer was wrong。

😊，But here's another variation of this question， so what if her bag is now 22 kilograms of weight？

And these are our blocks。😡，Just so that we can go through this。I'm not going to take as much time。

 but again here we can think about right that we have an 8 kilogram block with9。

 a 4 kilogram block worth $1， so that's not that much。An 11 kilogram。Worth 1111。

And this one is tricky because。The question is， what is the most value that we can fit in 22 kilograms？

And this starts to raise。Interesting question is。You have to hit exactly 0。2 kilograms。In our bag。

 or is it okay to leave with a lighter a bag which has some room to spare， but has more value？

And technically， the problem itself， this idea of the Napsack problem doesn't specify this。

 but it brings up an interesting question about what we're trying to optimize for or what we're actually allowed to get away with。

 So in this case。If we can leave。With a lighter bag。We can get away with。20。

We can get away with $22 of goods， which is two。11 kilogram blocks that is a dollar per kilogram。

And we。We get 22 hours out of that。If we have to hit exactly 23 kilograms。We can get $21。bye。哎。

What is the exact math here？How do we get to eight and eight is 16。And。4our would be 20。

19 so if we take 11。Okay， so we can get。11 and 8 would be。That's 19 kilograms so that would yeah。

 so we can get to 23 kilograms by taking one of each block right， which is 11 kilograms at $11。

We add in an 8 kilogram block at 9， so now we're at 19 kilograms and 20 and we had a $4 kilogram block at $1 and that gives us 23 kilograms。

And $21。One of the things that is tricky about this problem and doing it in a format like this is that you're keeping track of two values in your head right。

 you're keeping track of the sum of the weights of your bag and the sum of the values that you're trying to optimize for。

😡，嗯。So in general， if you're solving a problem like this， it's probably best to use scratch paper。

This starts to give us。An interesting sort of theory， right is that even with relatively few blocks。

 there's a lot of different possible combinations of how we might decide what the best combination is。

And it turns out that these two problems that we've just done with three blocks that all happen to add up oops。

I don't want to write passwords right now。Not what I needed。呃，看看。And。

With four blocks over here that they're simple enough that we can think through the options by just picking generally the most valuable blocks first。

You know， even in this example， 8 kilograms for 9。That's。That seems like it might be。

And the most valuable block。But it turns out given what we've chosen。

 if we start by taking this first， we take two8 kilogram walks that gives us $16 kilograms and 18。

 we have five kilograms left over。We don't actually get the best solution by starting with the most valuable block first。

And so in each of these cases。Why is that yeley should have been removed？In each of these cases。

 the best known solution actually takes exponential amount of time。😊。

I don't remember the full details of the best installation offhand。

 but it generally is pretty close to。Using brute force to solve the question is calculate all the possible combinations of blocks。

Up until we get to some value。And see if， you know， if things fit under under that back。

 so let's say we start with a bunch of 8 kiloigram blocks we compute the options there。

 we then start with a bunch of。4 kg blocks in previous example， Comp the options there。

 start with 11 kilogram blocks， Comp the options there。

 and you see that if you think about the fact that our blocks are unlimited， we have many。

 many kinds of options。 So in practice， we can get a good answer。To the Napsack problem。

By using your heuristic。A tool that lets us sort of approximate the answer to the question。

And this is using just some value that we've learned from to improve the answer。And in this case。

The heuristic that we use is what is often called the greedity approach in solving these questions。

 which is， let me start with the things that are the most valuable so that could be the highest weight。

😊，Or it could be the highest dollars per kilogram as this problem is set up。😡。

But you can kind of think about there's all sorts of ways that you might know use heuristics like this。

 right， like if you're at the grocery store。And you're trying to decide between like two or three similar boxes of cereal。

Yeah， there's a reason it like lots of places。Now put like the price per ounce or like the price per weight。

 because sometimes the more expensive thing that's larger is a better deal。Foo。

 you know like you have the costka problem， you have to assume that you're going to eat all the food that you buy。

 otherwise you did just waste money in food。😡，Using something that gives us an approximation of let me look at the best value and start there is a really common way of solving this question。

We call this an approximation algorithm to solve the Napsack problem。

 what we did was we started by approximating the best solution。

And then we sort of checked yeah does that make sense for three or four blocks and when we give you three or four blocks。

 like in these examples， you can generally assume that yeah， 36 is probably the best I can do。

 but technically you didn't really probably exhaustively compare。

You knowA dozen or so different options of blocks and so approximations are a tool that let us give an answer。

That is good enough， but not necessarily always the exact right answer。And so。嗯。

This makes an algorithm like Napsack pretty fast or a problem like Napsack it's a pretty fast approach to solving question in this case we can actually approximate the。

The answer in roughly linear your time。It may not always give us the most correct or the best answer to the question。

嗯。In the example that we just gave here， right？If we always and only ever started with looking at the most valuable block where we might start with the。

The eight kilogram block。It only ever reach $19 but if we have to start with that block first。

 so we could find the answer that gets us $19。Most efficiently。Wehich is not。

Too far off from either 21 or $23。But。It's not quite the theoretical maximum。Approximations。

Are a useful tool。And one thing that is pretty interesting about the NApsack problem that you can show。

 and this is logic， which if you continue on with computer science。

 or we get into in upper division courses like computer Science 170。

 the study of algorithms is that you can actually prove that the grity algorithm。

 is always within at least 50% of the theoretical best answer。嗯。You know。

 getting half the value that you could possibly get doesn't sound good。

 but but do have an answer in some reasonable amount of time， perhaps。Then the best answer。

An infinite amount of time right if you're waiting forever to get an answer。

That answer is probably not useless again， if you take the terrible version of this problem and assume that you're robbing some bank or jewelry store。

Spending an infinite amount of time trying to rug bank is probably not good because it would get caught。

😡，So approximating what you want。😡，That would work again， no。

 I don't think bankrops are actually a like。Being quite disccalalculating。

 but I can't say I know any。嗯。You know that's the case there are other interesting variations of this problem。

 which is if we have a limited number for each block。😊，嗯。

Then perhaps this can do really badly compared to the general solution。

Where you would need to change your heuristic to start with things that you could perhaps grab in most of。

But this is one of those interesting things about problems like this is there's a lot of different ways that that we can solve them。

 So actually， before we， before we continue on questions about sort of the framing of thenapsack problem。

😊，Aside from the otherwise illegitimate framing of the problem。Any questions， yeah。それかついね。So yeah。

 finding finding the most optimal answer is something that would take exponential time。

 so finding the 100% optimal answer is a problem that we say is hard and intractable we're going to talk about what we can do。

😡，With problems like this， but yeah， this is an example of a problem which is actually hard to solve in the perfect scenario。

Yeah， good question， other questions about about this problem。So。All。So on Wednesday of last week。

We said that tractable problems were solvable in polynomial time and we call all of those tractable problems。

P for polynomial。It turns out that we have a class of problems that we're going to call。MP。

And so here is。Another。estionAnd you could actually think about perhaps how this might feel similar。

 but slightly different to the Mapsackack problem。Suppose we have a list of numbers shown here。

 is there some subset that sums to zero， assuming you can use each number once？😡。

Is there a list of values？Of the six numbers that sum up。To。

2 zero so everyone should be able to vote for this if you're not sure please vote for C that's cool so take like let's take 10 or 15 seconds we'll do this one pretty quickly。

😊，Cool we've got some votes in Zoom everyone else in Zoom want to put a BRC folks in the room is there value for a can we sum up to zero cool does anyone think that we can't sum up to zero？

Anyone not sure， not sure iss totally a good answer。Anyone on zoom want to vote for not sure。Cool。

 the answer is correct。😊，C。嗯。There are a few different ways but。

The ordering of numbers here actually kind of helps us think about this right if we start with 15。

We subtract off 10， so 15 plus negative 10。Is five5 plus negative 3 is2 plus negative 2 is zero。😊。

And so those things。Add up to zero。That's probably the the easiest way you could start think about this right like if you if you just good on the line negative two plus negative3 negative5 plus 15 is 10 plus 14 is 27 plus7。

20。10 plus 14 is 24 plus7 like if you start adding up all the numbers。

 you might find that this problem is a little bit tricky， but if you look it in the right way。

 you can actually prove that these values sum up to zero。😊。

And this is an interesting question because it has a property which is really useful for a lot of problems。

A once again， this question happens to have just a yes or no answer。

 so the Napsack problem we're asking for the best most optimal set of things that we could possibly right it was。

What is the best type of thing in this case we're just asking is this combination of numbers？

Possible。And so。Technically， the best known solution to this problem is exponential。

 which is trial the combinations of numbers。Sum them up。See if they get zero。

You could even think about writing this yourself， right。

 repeat while we have some combinations and numbers。If the value is zero， report true。

At the end of our repeat until loop we report falses。

 but it turns out that like that number of calculations is。Is exponential with six numbers。You。

 this is a thing that we could write a problem to calculate because it's not too challenging。

 but if we had hundreds of numbers， we couldn't actually necessarily approve very easily or we couldn't solve very easily whether or not it was guaranteed to be a Susan。

 however。呃呃。There are ways that we could approach。We can solve this。

 but we can't approximate this one right we we can't say。诶。Yeah。

 there's no sort of half version of this problem that answer is either yes or no。OnThe other hand。

If the answer is yes。嗯。And we return a risk。We can very easily check whether or not that list of numbers does sum up to zero。

The answer is no， proving that a no answer is incorrect is a little bit more challenging。

 but if we do get an answer。嗯。We have a way of theoretically checking whether or not the answer is valid。

You in in in an Napsack problem， you can't necessarily prove that your answer is the best one until you've tried theoretically all the possible combinations and proven that other things are out of scope。

 Again， it's easy to think about all the possible combinations with four or six options。

 but if we have hundreds。It gets pretty， pretty complicated so in this case。

The key thing here to subset some problem is that it's what we call decision problem the answer is just yes or no。

 is this possible is this not possible and that gives us。A really nice property。

True police problems easily verifiable and what this means is getting the answer yes or no is challenging。

 but deciding if that answer yes or no is correct is actually something that we could do relatively easily so。

Wecover problems。MP。Does not technically stand for non polynomial， but it's sort of in that vein。

 the actual the actual thing it stands for is kind of stupid but it's computer scienceency。

 but what we say is true about NP problems is that，They have a yes or no answer。

It is possible to check their answers in a reasonable amount of time and this is the cool thing is that we have this whole class of problems where getting the actual answer is hard。

 but telling whether or not and understanding whether or not that answer is correct is very possible。

If I give you。Here。😊，For the subset some problem finding yes or no can be hard。 but if I give you。

 let's say 14，7。Negative three and two。It's very easy for you to take those four numbers on the left。

😡，Say those four numbers do not sum up to zero。Your solution to this question is invalid。

 that's not a sum of something that sums up to zero。

And so what that means is that once we get an hand so we can check in this case。

PtPtty nicely whether or not it all matters， and so this is where things start to get a little mind blowing。

And even then I am not an expert on all the ways that we can measure complexity。

 there's a lot of sort of depth here。The goal is to sort of get a high level sense of。

Of some of that。The reasons why。Here， this matters。嗯。

We could say that many practical problems can be framed。😡。

In this vein is the best solution is hard to find， but we can verify whether or not a solution is correct in a reasonable amount of time。

These problems all similar， so is there a way to route my airplanes？At a total cost of let's say。呃。🤢。

Less than $18 or less than $1 billion a year， so if you're an airline。

 can you devise a rotting formula that costs under a billion dollars well once you sum up the costs。

 you can verify whether or not。That that writing formula fits within that range。

Is there a way to route wires for my power grid with less than 10，000 kilometers of wire。

 so again can I set up some arrangement and verify whether or not it satisfies a condition similar deal。

 given some value Z， but there are two prime numbers such that x times y equals z。😡。

This happens to be a very interesting question。😡，三。For reasons which we unfortunately cannot get to。

In CS10， but this idea are the two prime numbers that map to some question Z is a very hard question to compute all the prime numbers that could satisfy that equation。

All right， but。The fact that this is a hard question to solve is the basis for how a lot of computer security works。

 so if you've ever seen like an HTPS， the lock icon and a web browser，嗯。

Those security encryption certificates that are passed back and forth rely on the fact that you can verify very quickly whether two prime numbers satisfy an equation。

 but it is very hard to reverse engineer that equation and so some of these questions are great for business。

 some of these questions fundamentally let us answer how a reasonable computer security。

We could ask other questions， you know， is there a spatial configuration of amino acid sequences？😊。

X whose total energy is less than y， so if you're a biologist or a chemist and you're trying to。

 let's say， build some drugs or understand something。About amino acids。

 you can test combinations and see whether or not they answer a particular question。

And if you're a mathematician， which we're not coming in today。

 is there proof that the Rman hypothesis is true Again， it is a decision problem。

 given some proof mathematicians can argue about whether or not it is correct。

But solving a question mark is it proof true。呃。Is hard so we can generalize other types of questions。

 so we're not going to get into all of this today， but there are other classes of questions where we can generalize about the no condition。

Today， what we're talking about is generalizing whether or not the yes condition sort of possible。So。

This is kind of interesting。way。T about problems is we have our problems。

Now I'm going to stop for questions in a second because this is。

And one of our mind blowing ideas is that we have a questions that we said are soluble in polynomial time。

 we can generate an answer。And because we can generate that an poll in no time。

 we can verify whether or not it is it is correct and that is a large， you many many。はい。

Sot of problems fit into the space， but there's also this whole other category of problems where finding the answer takes a ton of time。

If we are given some answer。We could determine whether or not it is the best answer or it is a valid answer for that question。

 so we call those problems。Like the subset sun problem。呃。in NP that they take a long time to answer。

 but we can verify their answer there's this whole other subset of problems like thenapsack problem like the best move in a game of chess。

あ。Where。They're not even in this class， we can't even tell you whether or not that is actually the best answer。

😡，If weve said， give me the cheapest routing for a series of planes。

That would be an NP problem because it's asking not just for yes or no。

 but it's asking for the absolute minimal cost and so those problems。

Fit into this class of not even NP there they're not slvable and reasonable amounts of time and given a solution。

 we can't even verify whether or not that solution is actually the best solution to the question because what we're asking for is is something that is the best or the least or the most or something like that。

 So before we talk about other kinds of of problems。Questions about this kind of idea。

 It is definitely a wild。Sort of a kind of interesting mind bend idea to think about。

 there are questions that we really can't。You know， solveve any reasonable amount of time。

Questions on。20点。That a questionnaire。I saw some with their hand。So。

Now that we have these classes of problems。Pter scientists have this idea called reduction。

And this is。The idea of。Trying to reduce or compare one problem to another kind of problem。

 given the subset some problem， can I reformulate that as a similar kind of problem？😡，So。

Funding the median item of an array， the middle value。

 we could say this reduces to just sorting the array right， the median mathematically is the number。

 which is the middle value of a set of numbers。So one way to do that is to just sort the thing first。

 which is a slightly harder problem， and then to divide it into two， take the middle value。

 that means if we know how to sort a list， we now know how to find the median value。So。あ。嗯。Yeah。

So what we're going to say is we can use this term that mostly gets used is cracking a problem is finding a solution where if we find a solution to some problem X。

呃。We can say。That we've cracked the problem if we also have a solution to why and so or sorry I said the backwards。

 by the way。If we crack the why problem。😡，If it's a solution to X， then we also have a solution。

To why。So what we could say is that sorting， cracking， sorting。

 or finding a solution to sorting cracks， finding the median。

 that we find a solution to one kind of heart problem。

Which finds a solution to another kind of heart problem。And。And so。は。E。

In the 197s without getting to logic， because frankly。

 some of the reasons behind all of this are pretty complicated， some computer science research。

ps some problem would give us a solution to all of the other N problems， at least theoretically。は。

And what this means to that we could say subset sum is an NP complete problem that this problem has a verifiable solution。

And if we find。A solution to give us the wheel answer。

 we find a solution to all of those other NP problems。Airline routing， Pegrid cables。You know。

 energy summing。That if we found a solution。We get。We would。

They get a solution to a whole bunch of problems and so researchers kind of think of this as like unlocking。

The key to the universe of all these possible problems。In soon。Conence here is。

We can efficiently solve the subset some problem。 we can efficiently solve thousands if not millions of other problems that have a similar sort of shape or look and feel。

 I mentioned that one of those problems of prime factorization。Was critical for computer security。

 it means that if we found an efficiency solution for。😊，The subset some problem we have to rethink。

The way that computer security works。And so。Today， we don't have an efficient solution。

 but we have identified thousands of problems that we call NP complete that fit into this category。三？

And the key is that solving anys problems solves all of those problems because we can translate subset sum to one of those problems。

 we can translate one of those problems into a subset sum type of idea and so。

The way to think about this sort of graphically is that。😊，We have all these problems。

If we find a solution to these NP complete problems。

 we would essentially turn them into problems that exist in the class of polynomial time。😡。

The question is。Is there an efficient solution to any one of these？NP complete problems。

And the way that computer scientists formulate this question is this is one of sort the largest open questions in computer science is does this P equal NP？

It's a funny way of phrasera this， but it's saying。

 is there a solution to all of these ridiculously hard problems that would turn them into easily solvable problems？

if that is true， it means that we've cracked。We show problems and computer science that we hadn't been able to crack for decades。

So if we find a clever way to solve subset some and let's say end cube time。

We found a solution to a whole bunch of other problems。If that is true。

 it means that N is that P equal is equal to NP and with these classic problems all just one class now the trick is so far。

Is that like a lot of people don't actually think that this is possible？

No one is able to prove today。That these things are that it is impossible to find an efficient solution。

 right， proving that we cannot find an efficient solution to a problem。Is。Not strictly impossible。

 it is definitely someone could come up with a proof that says P does not equal1 p that no efficient solution will ever exist to these problems。

 but it is much more difficult prove that an efficient solution is correct。😡，So today。

 this is an open question。嗯。donWe don't know whether or not these two cluster of problems are the same。

 but many people are certain to think that it's very likely that P does not equal NP。

That we will sort of live our lives out with heart problems。That we can't necessarily。あ。

SoSo we can phrase this。Our easily year of high level problems also easily solvable and proving that that is true or false is all right。

 so actually before we continue all questions about。About this idea。So。like you。Yeah。Yeah yes。

 the question is how is this possible？How would this kind of lie that the fact that we say that it be self subset some。

We can solve the other questions it's really on the idea of reducing one problem to another。

The exact steps by which we reduce。Subset some to some other problem。😡。

Are kind of tricky or the exact problem by which we reduce some random problem to subset some that depends on the particular question。

 So how you actually write this reduction。Is not necessarily generic。

 but the idea that we can say that let's say finding the median of a list is a similar problem to sorting a list means that if we can sort a list。

 we can find the median。The idea is that if we can solve subset some。

 we can solve a bunch of these other problems。And in the links here。嗯。One of the links Okay。

 yeah so so this idea on reductions I believe is this the yeah so。

We are not going to talk about this at all because it's been a while since I have reviewed any some stuff。

But there are a lot of theorems in computer science that sort of explain how we could reduce some of these classes of problems and that sort of explain。

What it means for a question to be NP complete， but yeah it you kind of have to sort of take us a word that it is possible to translate。

A bunch of hard questions into this subset some problem。

 which is translates subset some into a bunch of other。Hard， hard ideas。So。😊，嗯。sSo in 2000。

 mathematics Institutes set up a million dollar prize for millennium problems。And one of these。

 some of these are classically hard mathematical problems like solving。The Raymond hypothesis。

 which I should put a link to a YouTube video because there's a few really good ones out there on that it's been a while since。

I believe some of it， but we're the ones。They picked seven different ones。嗯。

And a lot of these are conjectures and math， things that we think are true， but we cannot prove。嗯。

One of the last ones they said is can you prove that p is equal to NP or can you just prove that P will never equal NP in so far？

New one。Has。Has found a way of proving this。If you think that you know this is a good opportunity for moving books。

 you know there's a set of open open ideas to work through so this is where we're going to leave things today except for the last minute I'm just going to introduce one concept but not go through the slides。

Is that。We have these whole class of problems that we can solve easily。

 we have a whole class of problems for which we can solve， but they take forever to solve。

We have this really interesting class of problems for which。We can solve them in a very long time。

 they're still intractable these NP problems。😡，If you gave a solution to them。

 we could check whether or not。That solution is valid and so this is the idea of NP completeness that if we can solve subset some。

 we can solve a bunch of other problems。😊，This is where we're going to leave the limits of computing。

Before we end today， this is not going to be tested at all。it is a pretty wild idea。

 There are some problems which are just theoretically impossible to solve。 So today。

 we're focusing on other problems。That。We can actually solve like it is possible to solve the Mapsack problem。

 it just takes dawn near forever。But there are a whole class of problems。

One of them is called the Hing column， so I'm not going to go through all these slides。

But if you're curious。This is an example of a problem for which it is completely impossible for computer。

The slides go through a loose version of a proof by contradiction that says that it is impossible to solve the halting problem。

 so thanks Google。😊。

![](img/03267a86e37c2c37344653a6b9d6d609_3.png)

![](img/03267a86e37c2c37344653a6b9d6d609_4.png)

For signing out right at the end of class so yeah plenty of problems that we have limits to and if you're curious there are problems that even computer science can prove to itself that it cannot solve every question so that's where we leave CS10 for the semester I will do a wrap up lecture next week since we got off。

😊，But good luck on the online final， hopefully I'll see most people next week。Otherwise。

 good luck on video finals and wrapping things up and it's been fun， thanks everyone。😊。



![](img/03267a86e37c2c37344653a6b9d6d609_6.png)

Thank you， thank you。