# 卡耐基梅隆【中英⚡离散数学｜21-228 2023, Discrete Mathematics】 p25 P25 -BV1sFibBkEj7_p25-

Hey， guys， hey guys。 I'm very， very sorry about that。 Good to see you all。

 and I'm amazed that there are still people here。 I am somewhat late for class today。

 but I was getting a vaccine in case some of you know， the solution is to not do delivery。😊，Yes。

 okay。 so， so， so in any case， I just just letting you know what happened。

 I was getting a vaccine because somehow we're able to get vaccinated now。

 And then when I was getting the vaccine， it said， you can make an appointment for， you know。

 a particular time。 and it'll take 10 minutes。 And I was like， I can do that。😊。

And then it turns out that it's more than 10 minutes because it's like a huge number of people out there。

 And of course， the biggest mistake is like。You know， whenever you go and do something。

 you'll probably notice that whenever you are in the line。

 it seems like there's tons of people in the line。 And that's because there's a correlation between times that are convenient to you and convenient to other people。

 And so I made the mistake of being like， yeah， sure， lunchtime works for me。Oops。

 everyone on their lunch break was at the place。 anyway， so I'm here。

 Let's go and talk about graph theory。 Here we go。😊。



![](img/751025f818331d6e60970565ac3d31eb_1.png)

Back to what we were doing last time。 Well， a new thing now， a new thing now。

 So we're moving to a new topic now。 So last time we talked about this Hamiltonian cycle thing。

 and we found out that there are ways to know that a Hamiltonian cycle exists。😊，Well。

 now at this time， I'm going to talk about something that seems different and it is different。

 but at some point， like later on， maybe next week。

 the whole things will connect together in an unexpected way。But today。

 I want to talk a little bit about a notion of， you know， we talked about connected graphs， right。

 And we were like connected graphs。 if they have no cycles， they're trees， right？

 And so I'm just going to remind some things that we had here。 Remember that if you had a connected。

😊，A cyclic。Gras。That's the definition of a tree。 Okay， now。

 we also had all this interesting stuff where we were like， oh， by the way。

 the number of edges is the number of vertices -1。 So that we we knew that we knew that somehow the number of edges。

Was equal to number of vertices。 and then -1。 We also found somehow they're like minimal in some sets。

 It's actually， we also found out that if you have a connected graph and its like minimally connected。

 So if you have connected graph。Such that。Deleting。Any edge。Disconnects it。Well。

 that actually tells you that you have a tree also。 We kind of talked about some things around this。

 if you don't remember exactly saying this is because I'm not sure I don't remember if I exactly said this。

 but the kinds of things we thought about are the kinds of ways you'd prove this thing。Now。

 why I gave that sentence is because， and this is also useful， perhaps on some of the homework。

 it's that if you have anything about， hey， I have a graph that's connected。Well。

Every connected graph contains some kind of a minimum， a backboneat。

 some kind of a a tree that's inside it。 I， I'm not saying that's the whole graph。

 But if you have a connected graph， it always happens to contain a tree that goes through every vertex。

 And that's the important definition we're going to use today。A spanning tree。In a graph。

What that is， is that's a collection of， well， all of the vertices are in it。

 And it's like a collection of some of the edges， possibly all。 It's all the vertices。And a subset。

 possibly all。Subset always includes possibly all。Of the edges。Such that。They make a tree。Now。

 not every graph has a spanning tree inside it， because， for example。

 if the graph you started with was not connected， well。

 there's no way you could make a spanning tree inside it because that connects everything。

But a nice fact， I'll just call it fact that doesn't deserve to be called a theorem。

 The fact is that every。T， no， every connected graph。 Every connected graph。Contains。A spanning tree。

Okay。Now， I called it the fact because if you wanted to prove it。

 it's relatively easy because you're like， well， I need to show that every connected graph contains a graph that's connected and has no cycles。

 How might I do that just so that I'm not the only guy talking here。

 How might you try to prove this fact。It's not crazy。Breden。one of the。Yeah。Bre a cycle。By deleting。

1 edge。So it's just like， it's a wild loop。 I just go and say， okay， do I have a cycle。

 I have a cycle。 Okay， break it， Do I have another cycle。 Okay， break it。

 And the important thing is that this keeps。Connected。All the time。Okay。

 and that's because if I had a cycle， then， you know， breaking one thing here。

 I can go around the other way if I had to。Okay， so now I know that every connected graph contains a spanning tree。

 This fridgenge is making a noise。 Let me just。There was just some funny noise from there。 Okay， so。

 so， so I know， I know that every， every graph has a， every connected graph is a spanning tree。

 And I'm putting that down because if you ever are thinking about something which is about a connected graph。

 Well， it's always useful to go and say， let me grab a spanning tree inside and see if I can argue about anything in there。

 And sometimes that's all you need because that serves as a backbone of the of the whole graph。

 Notice I use the important word here。 spanning tree。😊，is not the same as the。

 because there could be lots of different spanning trees。

It's just like there's if you have a bunch of cycles inside it。

 you can decide which way you want to you know， use parts of the cycles。But now today。

 what we want to talk about is the notion of the best spanning tree or the minimum spanning tree。

 Now， usually in life， people are like greedy and they want lots of things。 They want maximum。

 But in the context of graphs， oftentimes you're like， I don't know。 I want to， I guess。

 only pay for the minimum number of roads to connect everything。 Maybe， you know。

 like maybe you're like I'm going to make roads。 I have these different cities I want to connect。

 I just want to put in the minimum number of roads that would connect the cities。

 And that would save a lot of money， right， So minimums better than maximum。

 except that you got the kinds of traffic jams that made me late for the class。 So， in some sense。

 maybe like having more than a spanning tree sometimes useful。

 but I'm still going to focus on the concept here of minimum spanning tree。😊，A minimum spanning tree。

Makes sense in the notion of a weighted， connected graph。In I'll call it a weighted。

We haven't used that word before， so I'm going to describe it。 A weighted， connected graph。

Is what it sounds like。 Okay， I I'm， Im， I'm not even going to well， it。

 it's like least total weight is。The one with least total weight。Le。Totto。Wait。Now， what's the wait。

Well， I need to go and describe what that would be。 I。

 I now will be talking about graphs which are connected。

 and it doesn't have to be like the complete graph。

 It's just like I'm gonna to draw it on the next screen。 I'll have a bunch of vertices。And， you know。

 it doesn't really matter what it looks like， but it's just something。Drew something。

 a bunch of heres， A bunch of edges。 And now every edge has a weight。 also。

 So let's put some random weights on there。 The weights， by the way。

 don't have to be like integers or anything。 but they're usually not negative。

 Theyre they're actually usually positive 1，2， I'm lazy。 They're all gonna be like numbers。4，9，9，9，2。

1 and 3。 I made up some numbers。 Okay， so I just made some random numbers done。

 So if that's my weight on the graph， what would the minimum spanning tree mean。Well。

 I need to find something that。Has to go through all of the vertices。

 That's what the spanning tree would be。And I need to find some way that minimizes all of the weights。

 So I I minimizes the sum of all the weights。 So the weight， the total weight， oops， wrong Pan。

The total。Wait。Of a spanning tree。Is equal to the sum of the weights。Of its edges。Okay。

 so that seems reasonable。 And how would I find one of those， Which is one， Can we see one。

Anyone see a good way to make her。Cheap spinningning tree。 I'm just gonna be like， I Iballed it。

 I'm not even sure this is right， but this looks kind of inexpensive to me。I think。

It just kind of looks good because I don't want the 9，99，9，99 scares me and。Seems like it's right。

 I see a lot of ones in it。 It feels good。 It is like I got ones。 And by the way， I'm lucky。

 I did not know how easy or hard this would be to do。

 I just wrote some totally random graph and put some random edge weights and I hoped that I wouldn't need the pie。

 And somehow， you know， it's like， yeah， this looks reasonable。 But what kind of a proof is that。

 So now we've got to think。😊，Okay， minimum spanning tree。 I have a definition。 So it exists。

 Oh what's this。Minimum as an， yes， yes， yes， yes， yes。 Okay， Thank you for asking the question。

 So what I want to do here is we're not talking about the number of edges because the number of edges will be exactly vertices -1。

 It has to use all the vertices。 And we're not talking about minimum in terms of like the lengths of the paths between vertices。

 We're talking about the actual sums of these things。

 Think of this as saying I have a road network that I've built。 And like these sorry。

 these are only roads I can build for whatever reason I cannot build a road from here to there。

 maybe because there's like a giant mountain in between or something。 But like this thing here。

 you know if you cry really hard， you can build a really expensive road between these two。

 So the notion is that here are all the pairs of cities。

 and here's how much it's going cost me to build all these roads。

 Some of them are not like even possible。 And the minimum weight spanning tree would be a minimum weight spanning tree would be one where I've added up the costs of building all the roads。

 and it's the minimum total cost。😊，And actually， I。

 I realized I also made the as a mention of a or the。 In fact。

 there can be multiple minimum spanning trees， just like。

There can be multiple minimum spanning trees。Can be multiple。Minimum。Spanning trees。

With the same weight。And that's just because， you know， if you had some kind of a graph。

 maybe you could have like， you know， the same weight one way and the same weight in another way。

 Okay， now， actually， it's interesting。 all of these things here for the rest of this， this section。

 maybe today and tomorrow mor or to be today and the next time， we always call them M S Ts。

 because we're tired of writing it all the time。 Of course。

 the annoying thing about that abbreviation is M stands for。😊，Is it minimum or maximum， right？

 So we just will know it's always minimum， minimum spanning tree is always what we're playing with in in this class。

 And if you wanted to find a maximum spanning tree。

 turns out that you can adjust the way of thinking and you'd be able to come up with a way to use these as algorithms to make the maximum spanning tree。

😊，Actually， if you look at the old exams。 you can go and play with some question。

 I think that I think there's some question playing about maximum spanning trees。Alright。

 so now we have this notion。 We want to find a minimum spanning tree。 Well， let's see， at first。

 actually， it looks like it could be hard。 I mean， if what you're gonna to do is you're going to try every possible tree。

 which is sort of what I maybe was brain doing a little bit It's like， what if I use this。

 What if I use that。😊，That's a lot of compute。 Like。

 if I have to go and check every possible spanning tree that would take forever。

 So I'm going to say would take。Crazy。Amount of time。To just。Consider。Every spanning tree。

While you're hunting for the minimum， okay， because there's like tons of different spanning trees that you could put here。

 In fact， we might even talk a little bit about what we will talk about the way of counting how many there are later in this class。

 And there's like an enormous gigantic number of them。

 It's more than exponential in the number of vertices。 If you have enough edges going on。😊。

So that's highly impractical。 Now， the next thing is like。

 is there any dream of getting a practical algorithm， Because， as we said before。

 like finding this kind of Hamiltonian cycle or even knowing if one exists。

 that turns out to be an extremely hard problem to do。😊。

And to give a sense of why this thing could be a hard problem to do。

 if I just changed the statement of the problem very little bit to say。

What if I wasn't interested in the minimum spanning tree， I mean。

 what if I wanted to know what's the cheapest。That's the shortest total cost it takes to start from one vertex and walk through every other vertex exactly once。

 And I don't even care about coming back home。 Okay， it's just like I'm going to go from somewhere。

 I need to go to somewhere else。 And I want to cover every vertex exactly once。

 Doesn't that sound like the same kind of difficulty， Same kind of problem， right？

 So I'm just going to say like。😊，Compared to。The problem， which is， let's write。

 let's write a colon versus the problem， which is called minimum。Total。Wait。Of a path。Visiting。

Every vertex， exactly once。I don't really need to write the word exactly once。

 because if I visit every vertex and it's a path， Pa is not allowed to visit the same vertex more than once。

 but I'm still just going to write it anyway just to emphasize。Exactly。Once， well。

 doesn't that sound like the same kind of problem。Like over here， I've got minimum spanning tree。

 I have to go through every vertex exactly once， and I'm allowed to make a tree。 And over here。

 I have to go through every vertex exactly once。 and it has to be a path。 I mean， come on。

 this is easier。 There are less of these to worry about。Right， like if you think about it， if。

 if my goal was to find the cheapest total thing， if I only have to consider paths。

 I've got less things to consider。 So this should be easier， right。Well。

 the only problem is this is an extremely famous problem。Is spanning path a thing。 Well， okay。

 so you're right。 Is there such a thing as a spanning path。Well， there is。

 It's actually called a Hamiltonian path。Which sort of makes sense because we were talking about the Hamiltonian cycle before us going through everything。

It's also sometimes called the。Travellling。Salesman。Salesperson。

And that should make you scared right away。 if you see there's some traveling salesperson involved。

 Well， first of all， that's like a acute sounding name。 So it's probably some really hard problem。

 And it is the traveling salesman problem traveling salesperson problem is this question of how do you find this thing。

 And by the way， it's like extremely practical that Amazon guys have to do it all the time when they go and drive around delivering the packages。

 It's like extremely important problem。 There's only one issue。😊，Nobody knows a good solution of it。

Nobody knows a fast solution to this problem with the path。 And if you did。

 you'd get really rich because， for example， Amazon would， would pay you。

 everyone would be able to do things better。 this problem is solved is needed everywhere。

 but nobody knows a good solution for it， And it's related to this thing of P versus NP P。

 So unfortunately， this is hard。In the sense that nobody。Noose。How to do it。In time。

 in an amount of time that grows polynomially with the number of vertices。 That's actually what。

 what the technical thing is in computation time。That。Gross。Plynomily。In the number of vertices。

 let me explain briefly what polynomly means。nomial polynomly means like。

 if I double the number of vertices。Does my compute time just multiply by 2 to the some reasonable power。

 like two to the power 3， It's like if I double my number of vertices。

 do I need two cubed times as much time。That's polynomial。 Or if， if， if I。

 if I like multiply the vertices by 10 is the amount of time I need like。10 cubed times as much。

 That's a polynomial to the third power。 The problem， I mean， that sounds like a lot。

 but it actually isn't for computers。 The problem is。

 if you have what's called an exponential time algorithm or worse。

 It's like if you look at the function。10 to the power N。 and you double N。It gets like crazy。

 It doesn't just multiply by。2 to some power。 it squares。 So， so that's just why this is。

 this is bad。 So all this set up is like， this is a really hard problem。 Oh， question here。

Computer security people's lives wouldn't be better。 Yes， that's right。 That's right。 So so I mean。

 for all you know they're probably okay， I guess my thing is like if it was solvable。

 surely someone would have figured it out by now， given the amount of potential commercial value there is and the amount of money governments might have been investing in to do it。

 they haven't succeeded as far as I can tell unless theyre just like decrypting everything and listening to everything we're doing right now。

 maybe they are but I don't know I don't think that the secret can be kept that well。

 although I will say by the way， that's why I personally refuse to do research in these areas。

 I don't want to do research in an area where if it's like， my gosh。

 I just figured out something that someone knocks on my door and I disappear。

 that would just be terrible。 You know what I mean， it's just like I don't need to be。

 I don't like to touch these things too valuable， too important。

 let me go and think about some pure math instead。 All so so， so anyway。

 these are hazards of know if you figured out ways to take over the world。

 someone will knock on your door。 Okay， so now now this is bad right we now know this is like a very。

 very。😊，Har problemble。 And here I am trying to teach you how to do an even harder problem。

Looks like we' have to consider even more stuff。 We can't just consider paths。

 We've got to consider crazy things， but it turns out that there is fast ways to do this。Now。

 that's because it's not actually a harder problem， right，m。

 I'm saying I'm allowed to look over more possibilities。

 And if I'm allowed to look over more possibilities。

 it just so turns out it's easier to find some of them that work。

And it might seem at first a little counterintuitive。 Like over here， I'm only looking over paths。

 and here I'm looking over paths and more stuff。 But if I change the problem entirely to say。

 can you find the minimum total weight of any subset of edges at all。Well， yes。

 let's call take nothing。 I'm done。Problem is solved。 I don't have to do anything。

 But the number of subsets I， in theory， had to consider if I said all possible subsets。

 I had to consider way more subsets of edges than even just these paths， right， I I'm saying like。

 just because you allow more possibilities。 doesn't mean that the problem gets harder because I just showed you how to trivialize it by saying。

 I will allow any subset， find the cheapest total thing Don， take nothing。Okay。

 so so that's just why there's some hope that this could be easier。 All right。

 so now let's start talking a little bit about how you might even try to get an algorithm for this。

 And this is remarkable the fact that there is one。 The first thing you'd think of is。

 can I be greedy。 Now， let me talk a little bit about what a greedy algorithm is by trying to do it for the travelling salesman problem。

 trying to like prove that you know， break through history and say。

 we can solve travelling salesman problem with the greedy algorithm， Will that possibly work。😊，So。

 here's the greedy。Algorithm。For attempting， it won't work attempting。To solve。Travellling。Salesman。

 salesperson。Well， what you could do is you could say， I have some， well what would you do。

 You say find the cheapest possible edge， right， you know， we， we can decide where we want to start。

 Find like the cheapest possible edge to start。Find。The lowest weight。

 that I guess I should call it that way。Find the lowest。Wait。Edge。To start。Okay。

 I don't know what direction to go。 Just choose any direction or kind of like go in the direction that there's another low weight。

Go along it。In the direction。Where there's。Another。Cheap， a low， low weight， Lowest or low。 just low。

Wait。And greedy than just means attempt to keep walking。

 always choosing to go along the low weight edge。Ti。To keep。Waling。Always。Going。On the lowest。Wait。

Edge。You can find。Right， so in theory， what's really going on， I have some kind of a graph， right。

 And I found this lowest weight edge。 Oh， look at that。 There's some lowest weight edge here。

 and the lowest weight edge happens to be 5 or something like that。 Okay， and then you， you decide。

 oh， off of off of these two sides。 What did I see， I saw some stuff coming off of each of them。

 And when I saw some stuff coming off of each of them。 What were those weights。

 They were bigger than5， because 5 is the lowest。 So maybe this is 9。 Maybe this is 7。

 Maybe this is 6。 and maybe this is 6。 and maybe this is。14。 And then what you say is， yeah。 okay。

 I'm just going to go along the 5 and then like the6。 And you just keep going， right。

 you go and say from the sixth thing， what happens， You know， you might。

 you might come back to one of the vertices you saw before。 You might fly over here。

 You might go there。 Maybe there's some weights here， like 9，99，9，99 and 9，99。

Now you already see why this is a bad algorithm。It's because if you're just greedy。

 you can get stuck， right， Like if， if all you're saying is I will just attempt to go and if it's like an earthworm crawling or something。

 I'm just going to eat the tastiest food I can find as I keep going。

 you might find yourself running into rocks。 And then that's it。 No more food。 right。

 And that's the problem。 That's why greedy algorithm is a terrible idea， usually。😊，Now。

 you can also sort of see， though， how that's why this Hamiltonian path is traveling salesperson。

 That's why this is harder， because you see worms have heads。 The heads have only one mouth。

 So you only have one way to keep eating。But if you're suddenly going to do the minimum spanning tree。

 you're sort of like one of those crazy， like worms that regenerates things like， you know。

 you've seen those videos， maybe you cut off the head and then the rest of the body regenerates off of the head。

 This is like a， this is like a worm that can regenerate heads off of anything。

 which I've never seen in my life。 But I guess that's called the hydra。 That's right。 It's a hydra。😊。

I guess they don't exist。 But， but in any case， this is like。

 this is basically like a hydra in the sense that when I'm doing a minimum spanning tree。

 I could grow in any direction。So， in fact， there's an idea of a greedy algorithm that we should try。

 and it even has a name because it actually works。 But that's like unbelievable。

 There's no reason why this should work。There's an algorithm。I， I don't wanna call it a theorem。

 I'll call it an algorithm， okay。Algorithm， because we're going prove that it works。Algorithm。

And this is called Prim's algorithm， Prim。 And what this is， is it says。

 just do what we just said there。Acept that。You're allowed to kind of go off in any direction。 Okay。

 so again， the goal here is to given a， you're given a connected。Given a connected。Waited graph。Okay。

 now how would you start？ Well， now we， we're thinking of this as like this hydro， which is growing。

So， step  one。Just start from any vertex。 Okay， because we eventually have to connect up every vertex。

 Pick any vertex to start。Okay， and then now the important thing is while you're not done。

 meaning that you haven't gotten all of your vertices into this graph。Well。There。Still。Our vertices。

 not。Yet。In your spanning tree， in your tree， we don't know it's a spanning tree yet in。

The tree we've built。Well， what， what might be good， I don't know why I wrote a one。

 but I'm just gonna write some numbers。 Okay， because then I can talk about the points。

 but the one is somehow do a one。 And then the wild loop is gonna do a bunch of stuff many times。

Well， I've got some vertices， which I've already gotten。 And so we're building a tree， by the way。

 just like how we're built the worm was kind of eating and growing。 We're having this hydra come out。

 which is growing in some crazy way。 We've gotten some tree。 This is what we've gotten so far。

 We've built some tree。😊，Built so far。And then there's like more stuff。

 There's like all this stuff that we haven't gotten。

 So let me just put the built so far into this circle。And then here's the rest。

I don't know what it looks like yet， but there's the rest。There's some more stuff。Okay。

 now I do know one thing。 I know that my graph was connected connected to begin with。

 So there have to be some edges that go between， right， There have to be some edges that go across。

Must exist or else it wouldn't be connected。So there has to be some things that go across。

 there can be multiple things going to the same one。Okay。

 they can kind of go off in all these random directions， but these must exist。

Since we're started off with connected。Does anyone have a suggestion if you were greedy。

What would you choose， I'm trying to build up this tree。

I'm trying to build up this minimum spanning tree。 I' I wanted to eventually eat up all of the vertices Here。

 I have gotten so far， Go the yellow thing。 And it's， you know， what I've gotten so far。 is saying。

 what might you want to do。首はきで。Yeah。Yeah， yeah。 it's like， I need to grow this thing， right。

 It's like my my hydra is growing from every head at the same time。

 And I have a few different possibilities where greedy。 Pick the one that is the cheapest。

I hope that it works。Okay， so the step 2 of the algorithm is。Add。To the tree。We're building。

I'll not call it the。 I'll call it a minimum， because if all three of these were the same weight。

 there's no the cheapest because they're all the same， but it won't matter。

 Just pick any one of them。A minimum。Wait。Edge。From the crossing， I I'll use the same pink color。

From crossing。Okay。And just do it。 So， so it's just like， just do it and do it and do it and do it。

 And somehow it's gonna to work。 promiseise。 Well， that's actually a big promise。

 I'm hoping I've built up by now to make it so people wouldn't believe this because what we just saw with this kind of Hamiltonian path or the traveling salesperson path is that。

😊，How could you hope to be that lucky， Like， what if you just did something and you were greedy and you locked yourself into a bad set of decisions。

 That's actually what we're going to prove next。 What we're going to prove next is it turns out that this choice of grow and always greedily pick a cheapest one that crosses。

Turns out。It's always going to give you a minimum spanning tree at the end。 And that's a。

 that's a minor miracle that you could be this dumb and this greedy。

 And the thing that pops out at the end actually is a minimum spanning tree。So， the theorem。

That finishes the algorithm， by the way， The theorem is this。Always。Mix。minimum spending trip。

 We have to prove that。There is something I want to comment。 I made something about。

 I made some comment about efficiency。Is this like， how how crazy is this algorithm to actually do。

 Do you have to look at exponentially many possibilities， Well， not really。

 because if you think about what's going on， what you do is。You're only going to examine。啊。

Is that true。 No， no， no。 what， what you， what do you can do is， as you grow this。

 right every single step， let's think of it as growing it step by step by step， right。

 I'm good to grow it And steps there and vertices。😊，So the number of steps is N。 Now。

 for each of those steps， I have some stuff here and I have some stuff there。

And I need to go and find out all of the edges that go across。That's at most。

 I'm being very rough here。 That's at most N times n possible edges to evaluate。Probably a lot less。

 but I'm just saying。I have n steps。 Each step is evaluating at most n squared edges and finding the cheapest one。

And I find it。 And I added it。 I'm trying to emphasize that it's like n times n times n。

 It's like n cubed or something。 You can actually do much better than this。

 Maybe you can cut it to like n squared。 But I'm emphasizing that it's not exponential。

 It's not like I have to go through lots and lots of possibilities where the possibilities blow up。

 If I want to do an analogy。 If you were trying to find a Hamiltonian path or a traveling salesperson path。

 And if it was like n vertices。 And you started by saying。

 I want to consider every ordering of in vertices I could walk through。 that's n factorial。😊。

So I'm trying to emphasize that n factorial， huge。 But this is like N cubed or something or n squared。

 is it won't be that bad。 So that's why this is actually efficient。 In fact， this is so efficient。

 You can even do it by paper and pencil。 That's also a way I often decide like。

 is something efficient or not。 It's like， would I be able to do it。 And yeah， the answer is， yes。

 I would。Okay， so now let's go and prove that this works。 How would you prove that。So you see。

 if I want to prove that something like this works。

 I already sort of was hinting at the the key concept here， which is called。You never get trapped。

 You never go in the wrong direction， because notice with the greedy algorithm。

 there's no taking things back。You can't be like， oh， just kidding。 That was a bad move。

 I changed my mind with the greedy algorithm。 You say， I want that itch。 Okay， you're locked into it。

 I want that 1。 I'm locked into it。If at any point， you lock yourself into some stuff。

 which has no chance of finishing into a minimum spanning tree。 You're dead。 And the proof is over。

 I mean， then then there's no proof。But that gives an intuition for how you could prove this。

 One way to prove this is to show that when you take your steps。

 every step always has a way to finish。I'm going to write that here as a theoretical concept here。

 And then we're going to go to another screen and actually go and prove this。

So the big idea of the proof。Is that we're going to show that at every point。

 the thing that we've built so far。Is contained in some minimum span tree。What with。Built so far。

Is always。Heart。I'm going to be very clear， Always entirely part。 it's a subset。Entirely。Part。

Of some。Minimum span tree。In the original。I'm just emphasizing like minimum spanning tree in original。

 but we really just meant that anyway。 We always met minimum spanning tree in the original graph。

 I'm just emphas because we've got like some stuff we've done so far。 So at least if you read this。

 there's no confusion。 This is just saying I need to show that no matter what。

 as I'm doing this algorithm， this thing I've got so far。

 that's a part of some minimum spanning tree in the end。😊。

And that's like telling you you'll never take a step and be permanently in the wrong track。

Does it make sense that if I could show this， I' would be done。

Because then that just shows every step you make。 You're always going to be on the right track。

 It always is contained in some minimum span tree。 So let take all the steps。 And at the very。

 very end， you got D took everything。That's supposed to be contained in some minimum spanning tree。

 Well， then that is a minimum spanning tree。 Does that make sense。

 It's like that's how you get the end game。 It's like as long as I can show every step of the way。

 I am part of one of the minimum spanning trees， because there could be many different ones。

 Then by the time I actually use every single vertex。 I'm still part of a minimum spanning tree。

 but I am a spanning tree。😊，There's no more I could grow。 Therefore， I am a minimum spanic tree。

 undone。 I Ive proved the whole thing。So that's like the intuition for how we're gonna make the proof。

Okay， how would we prove something like this？ Well， the， the key idea is like。

 you could call it induction。 I also could just think of it as saying。

If you can show it was true at the beginning and it stays true， you're good。 That's called induction。

 So， so let's start at the beginning。 How do we know that at step 1 after doing step 1。

 what we have picked so far as part of a minimum spending tree。Well。

No one's answering because that's like Da。 you have a vertex。 If you just have a vertex。

 that's part of every minimum span tree because it has to contain every vertex。 So the one part。Is。

Obviously， it's like it's do。Okay， they always say you're not supposed to write like obvious or trivial in a math proof。

 So I'll write D instead。 But so this one is is， it's just like， yeah， it's always in that。

 But now is the second one is， is the one we have to think a little bit。 So we have to say。

 while there's still our vertices not yet in the tree we've built。Then by adding one of those。

 I'm still guaranteeing that I'm in a minimum spanning tree for this。

 we have to do a little bit more thinking。So I'm going to redraw the picture for two on the next screen。

 And we're going do some more thinking on it。So for two， what do I actually have， I have some free。

 Okay， so there's some tree we've built so far。That was supposed to close。Okay。So this is the tree。

Built so far。And we've got the rest。And we have a few edges， okay。

 with have a few edges that go across。Oops。I'm just gonna draw a few of them。 I mean。

 there there's many more， but there's like， there must exist some edges that go across because they're connected。

So， these are the edge。Across。Okay， now there is one of them that we decided to pick。

 We decided to pick one of them， which is minimum weight。 So we actually decided to pick this one。

This is one of them， which is minimum weight。 It could have that there are multiple minimum weight。

 but we picked that one。So this one is a minimum。A crosss， a crossing。Okay。

 now how can I show that I'm always going to be part of a minimum spanning tree at the end。Well。

 here's where I need to use the induction hypothesis。 It's like， well。

 here's the thing I've built so far。 I get to know that the thing I've built so far。

 that is legitimately definitely part of a minimum spanning tree In the end。

 There might be many minimum spanning trees in the end。

 but that is part of a minimum spanning tree in the end。😊，So I'm going to use maybe the screen。 Oh。

 maybe use white。 So this is guaranteed。 I know。Fang。The induction hypothesis or the previous。

 the previous。Steps statement， I prefer the use induction hypothesis。Induction hypothesis。This。Is。

Inside。An MT。Okay， what does it look like， Well， I've got some possibilities。

What if the MST that it looks like。 So it's inside an MST， meaning like there's all of this stuff。

 And there's more stuff that's part of it。 like so suppose suppose I had that the MST that is part of。

 you know， I'm just drawing some stuff。 It has to all contain this and suppose the MST is part of。

 contains this and then does some more stuff。Well， that would be great if the MT that it's part of already includes this edge。

 I've nothing more to prove。 It's like， well， yes， than adding this。

 I'm still going to be part of an MT。 Okay， so that's like the easy case。

 I'm going to remove the highlights。😊，So that I can see my picture again。So， let's put it here。If。

This。Contains， let's give that edge a name。 by the way， let's call that edge E， E for edge。

 If that contains E， if this contains E。You're already done。Already done。

Meaning that if I added that E E， I'm going to be part of a minimum spanning tree。Okay， well。

 why not。 What else might happen。 Unfortunately， what else might happen is it doesn't contain ye。

If it doesn't contain， that's sort of why I drew another edge connecting。

 the key is that remember that its， it's contained in some minimum spanning tree。

 that minimum spanning tree has to get its way across somehow。

 has to be able to get all the way across somehow。So that minimum spanning tree that is part of now I'm going to do the white highlight。

 but a different way。Elf。It crosses。Some other way。And I also want to emphasize when it's crossing。

 it could actually cross over by a few edges。 So I'm going to actually。

 I do want a few more edges inside here。 So maybe yeah this one， this super big flyover， okay。

But that's not really deeply consequential。 I'm just trying to say that what does it mean that it's part of a minimum spanning tree。

 It could look like this。 It could be that the minimum spanning tree。Goes across this way。And then。

 like does more stuff。Okay， and then it's a minimum spanning tree。 so it has to use everything。

And importantly， notice that the white thing this time does not use that yellow edge。

 That's important。Crossses some other way。But doesn't。Use。いい。嗯。

I'm actually not going to say this is definitely a contradiction because I don't need to say that adding this edge E makes the new thing a part of whatever was the old minimum spanning tree that contains this one。

I， as in actually， not， not that there's only one either。 There's like many options， right。

 So the important thing here is I'm saying there's an MST。 So this white thing here。

 it's not like the only minimum spanning tree that contains the， the thing I have here。

 There's many of them。 But I just grew one of them。 And if we're not lucky。

 and that one doesn't contain this edge E。 We're gonna show that there is one that contains the edge E。

😊，Which is at least as cheap as the right one that I've drawn。So， the goal。Is to show。

There's another。MT。That。Actually， I won't call it MT。 I'll just say there's another spanning tree。

 and that's gonna be enough。Another spanning tree。That。Does。Have。All of the previous。And then。

 plus the edge E。And with。Less than or equal to。The cost of that white MT。The， the， the。

 the last we go to the total weight。Of the white MT。

So I'm just trying to use the colors to code things。 The white MST is the one that I'm guaranteed。

 The minimum spanning tree guaranteed to contain the old tree。 That's the one in white。

 And the claim is， well， if that one just doesn't happen to use this edge E， well。

 then I will go and make another spanning tree， and it's going to be less than or equal to the cost of that。

😊，White 1。 But the white 1 is supposed to be minimum。

 And if you've got anything less than or equal to the minimum， you actually are also a minimum。

That will do it。So， also。And minimum Hispanic tree。Okay， so how might we do that。Anyone have an idea。

 Like， we're looking at the picture here。 Suppose what I've got is， you know。

 I'm claiming that the white thing is a minimum spanning tree is the cheapest possible spanning tree is is a cheapest possible spanning tree in the entire graph。

It doesn't contain this yellow thing。Is there a way to make an adjustment so it contains all of the stuff it had before。

 It also contains the yellow thing， and its cost is less than or equal to the white one。Any ideas？

 Remember how you got the， the， the yellow thing， by the way， the， the or the pink or whatever。

 This is the minimum crossing weight。From this side to that side， is the cheapest one。Aha。And住。最ト。

Yeah， thank you。 So the important thing is， remember， now we're using some properties of trees。

 The white thing is a tree。😊，That means it's a minimally。Wait。Yeah， it's a maximally acyclic graph。

 We've talked about that， too。 If you have a tree which has n -1 edges。And it's connected。

 You add any one edge， and that one edge is going to give you a cycle。

 And that's going to be part of that cycle。Right， so the important thing is。

 since we started with this white tree， you added one edge on the white tree bang。

 There is now a cycle that contains that one new edge。So I am running out of space on this。

 I guess I can try to squeeze off to the side。 Maybe this will fit。

 So what I'm what I want to say here is。Okay， very nice。 So now if you。If you add this E to the MT。

 Oh， yeah。 that's white。 So the white MST。Plus， this edge E。Mix the cycle。With it。

And what we just used here is because it's a tree。 If you add any edge to a tree。

 you'll get a cycle using that edge。Now if there's a cycle with the E， look at that cycle。

It does have the E involved as one of the crossings。 but somehow you have to have another one， too。

Because if you think about it， if you're going to walk on a cycle and you' have moved from this piece。

 the stuff you got before to the new frontier， and you will have a cycle at some point you got to get back to the stuff that you were at before。

You might have multiple。 It could like zigzag back and forth a few times。 That's okay。

 But the point is， there is going to be at least one other edge where you go back。And the idea is。

 rip out that edge and put this one in instead。And since。This is， since this would have been a cycle。

 you see， I will still have the property that my final thing is still going to be connected。

So there's a few things which are going on here。 It's like， okay， well， there's the cycle。

 So now now I can stare at the cycle。 and it has， it has like， it's connected。 It's N。 it's yeah。

 So it makes the cycle。 So I can take away any edge from that cycle， and I'll get a tree back。

 That's the important thing。😊，Because I have N vertices， it's connected。

 and there's exactly one cycle。 break that cycle， break the cycle with one one of the other edges。

 which is crossing。So the next thing is to remove。From。The from the MT。Any， any other edge。

That is crossing between the two parts。And add E。Oh I don't need to underline because here。

 I guess I haven't been under the rest of them， so。And add。E， I have actually also been making。

In that pink color， Add。Terrific， so if I do that， now I will actually be able to still have a tree。

Because。I made the cycle， and that I broke the cycle a different way。

 I still have n -1 and vertices -1， many edges， and it's still connected because I just change from one piece of the cycle to the other。

 If I have n-1 edges， vertices -1 edges， and it's connected。 It's a tree。😊，And therefore。

 I have this new tree， and the new tree is still a spanning tree。

 Its total weight is less than or equal to the total weight of whatever I had in the white thing。

 because my substitution went from a possibly more expensive thing to the cheapest。That's important。

 Remember that that was the cheapest。Since Yi。Was minimum。Or has weight。

Less than or equal to the other crossing edge。The trees， this M， S， this the span trees， wait。

Is less than equal to the original minimum spanning tree。And you're done。

 That's actually the entire proof。So I tried to fit the whole thing onto the screen。

 So we have just found out that， O， well， then there's another minimum spanning tree。

 which contains all of the stuff I started with before。 plus that edge。And therefore。

 by doing that step of going to that edge。I'm still on a track。 that could work。

 It's sort of like when I was a college student。 at some point。

 I thought I might be a like math major than I thought I might be a physics major。

 than I thought it might be something else。 But the good thing is I eventually graduated because what was going on was that every path that I was on。

 I sort of knew， yes， there's still a path to graduation that I can use。😊，Don't， by the way。

 get onto a situation where you dont have a path to graduation。 That's a bad situation。 But you see。

 like， you don't know what you're gonna to do yet。 But just make sure that each of your options you're going on could finish。

 That's all that's going on here。 We're just saying like this hydra。

 which is eating through the dirt pile or whatever。 has some path。 Like it when it ate that way。

 That's okay。 There's a minimum spanning tree that does contain that。

 And then that means when finally， you eat all the dirt。 Oh， well， it was a minimum spanning tree。

 it's in one。 And that's it。 It's a spanning tree。 So you're done。 And that's it。

 So this is this remarkable algorithm that's just greedy。 But the proof actually all fits here。 Its。

 it's just a simple idea of youd never get stuck。😊，Okay。And that finishes on a class。

 So I I actually have to go and it's just just like for fun。 I'm giving this talk on the CFA lawn。

 Like， now I'm actually gonna get to go to CMU and give a talk。

 So I don't know if anyone knows if it's is it raining， No， it's not。 So I'm giving the talk。

 But yeah， I'm gonna be doing something。 but you already know what I do。 it's like this no bit stuff。

 But the idea is， I'm super enthused because I finally get to go back on CMU campus and say something。

 So anyway， I've got it for。 So I I will， I will jump on my bicycle probably in about 5 10 minutes together over there。

😊，There's no traffic on bicycles。So is is this， if this is efficient。

 why isn't a solution to So the important thing here is that the traveling salesman is not the hydra。

The salesman cannot be like， hey， just kidding。 I am suddenly going to， you know。

 send my arm that way while my head goes that way。 You can't do that。At least not yet。 Now， now。

 if you're wondering， wait， why doesn't the traveling salesman just like go on a spur and just kind of like go there and back。

 Well， now the traveling salesman， if you go there and back， you pay twice for that road。

Although we are going to talk about something that is based on all this minimum spanning tree that is related to traveling salesmen and is related to what I just said about going there and back。

Yeah。I think I was just trying to emphasize that it's very amazing that there would be an algorithm like this。

Because the other ones don't。 So I don't want people to be like， oh， yeah。

 it's just an algorithm to memorize， Yeah， whatever。 It's like thiss cool。 Like was why why this is。

 why this this exist。 And， and also the proof， like the proof is not even crazy。

 It's just that you never get stuck。 So that's what this is。😊，Good。Mm。



![](img/751025f818331d6e60970565ac3d31eb_3.png)