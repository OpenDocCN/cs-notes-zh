# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p11 P11 mar17 -BV1Dao8YQEEn_p11-

All right， so maybe we'll get started just going over things。So PSet3 is due this Friday， let's see。

 PSet two know I think you should be I think is mostly graded but we'll definitely have it back to you by Thursday I'm not sure if the TAs will have it today and then to remind you that the midterm will be in class。

 it'll be the Thursday after spring break， okay。And we will have we'll schedule a review session for the midterm。

 like the week after spring break， you know， so before it， well， not after it obviously。

 and we'll have some practice materials that we'll put online， all right。

So last time we talked about kgra complexity， the length of the shortest program that outputs a given string we saw that we saw why it's uncomputable。

 you know most strings have close to maximal commmographra complexity。

 but there's no general algorithm to tell you which ones do or which ones don't。

And then we started talking about time and space complexity。

 which will occupy us for most of the rest of the course in some sense。

We saw that once you fix a machine model that you're talking about。

 whether it's one tape touring machine， a two tape touring machine， RAM machine， whatever right。

 then these sorts of choices can sometimes make a difference for these sort of questions and we'll have to be aware when they do。

 but you can then talk about like the class of all the languages that is decidable by your machines using a number of steps that grows at most like O of F of N。

 given an input of size N， or the class of all the languages that's decable。By a machine。

 you're a type that uses it most O of F of n bits of memory when given an input of size n。

OkayAnd then at the end of the lecture last time we proved this famous time hierarchy theorem， okay。

 which basically says you know if you have more time you can decide more languages， okay。

 so this is like one of the most basic。Facts that you gives meaning。

 I guess the computational complexity right there is an infinite hierarchy of know harder and harder languages that you know you become able to decide as you have more and more time do them right and this is not something like P versus NP right this is something that we know this is something we can prove so。

Adam， do you know if the PSs are all graded no？Okay， all right。

 well we'll try to get them back by Thursday then all right good。Okay， so for example。

 you know just as one example， we prove that time of n squared is a strict subset of time of n cubed okay and the way that we proved that。

 you know was by really just a scaled down version of you know touring's proof of the unsolvability of the halting problem okay you know our example of a language that was solvable in n cubed time but not in n squared time was just you know the language like basically consisting of descriptions of touring machines that halt and you know。

😊，Some intermediate number of steps like N to the 2。

5 okay and certainly that language is decidable in N cubed time because you just simulate the machine for the requisite number of steps and you see if it halts but then what we argued is that you know if it were solvable and n squared time then essentially we could have a machine just simulate itself and do the opposite of whatever it does and that would create a contradiction okay so it's。

😊，No I always found it very cute right it's sort of like you know this sort of argument you know this informal argument that you could make for you know why you know you cannot predict what you yourself were going to do you know 10 seconds from now right by any procedure that will you run in only five seconds。

 okay well why not because if you could do it， then you would just commit to you know whatever the prediction was as soon as you found it out。

 you would do the opposite。Okay， you know if the prediction was that you would raise your left hand then you'll raise your right hand instead。

 so you know maybe maybe someone else could predict what you're going to do before you do it if they had a complete model of your brain and if they had a powerful enough computer you know you to simulate your brain faster than it runs itself then maybe they can generate very good predictions of everything you're going to do but even then they'll have to be careful not to tell you the predictions beforehand because if they did then you could do something different unless they gave you the predictions in the form of a computer program and then you know by the recursion theorem that would actually work but if they gave you the prediction if in some sense and the time hierarchy theorem is sort of the formal analog of this if a machine could predict what you a machine like itself would do。

you know， you know， in a longer amount of time than it itself has to run for then it can you know just make itself do the opposite of whatever it does。

 okay so you know this is saying in some sense that there's no general way to sort of speed up time in computation。

So you might wonder， you know do we have any natural examples of problems that let's say we can prove require n cubed time you but that cannot be solved in n squared time for example that would be like the most natural question that we could ask here you know and I'm not talking once again I'm not talking about problems like where the input has size n cubed come on know we're defining the size of the input to be n okay and then the question is you know are there natural problems that we can prove you know inherently require let's say n cube time something like that okay there's certainly problems that we don't know how to solve in linear year time you know matrix multiplication is a good example。

 maximum flow is a good example， people are working on that one you know but。

When I last chat that one is not yet solvable in linear time， linear programming， maximum matching。

 okay so a huge number of the problems you study in an algorithms course we know pretty fast algorithms for them but they're not linear which would be these sort of absolute limit and so the question arises could we prove that any of these problems inherently require more than a linear amount of time。

And occasionally that can be proved， the way it can be proved occasionally is by reduction from the time hierarchy theorem。

😊，So there are certain problems like involving like games played on graphs with black and white pebbles where you know you can prove that you know computing like the best strategy in this game is as hard as simulating a touring machine for N cube time steps you can you you can encode touring machines into this game okay which means that if。

😊，You know which means that if you could you know compute the best moves in this game in less than N cube time then you know you would violate the time hierarchy theorem okay actually like if you generalize chess to an end by end board you know you have to have whatever more pawns。

 more rooks， whatever， but you can show that decide you know and let's say you don't put any upper limit on how long a chess game can last okay so you know I think some some chess tournaments put an upper limit。

 others don't okay but let's say you know you allow the game to continue for an exponential amount of time okay then you can prove that actually deciding you know which whether white or black has the win from a given chess position is as hard as simulating a touring machine for exponential time。

Okay， from which it follows that there cannot be an efficient algorithm to decide who has the win in this generalized version of chess right。

 and once again that's you know that's not like you know assuming P is not equal to NP or anything like that。

 that's proven。😊，Theorem take it to the bank okay so you know that's what the time hierarchy theorem whats you do you know in certain rare cases okay but but in you know as we're going to see that's more the exception than the rule you know in most cases we're simply not able to prove you know that you know unconditional lower bounds on the difficulty of computation okay that's you know one of the。

😊，biiggest open problems that that well in all of human civilization， if you ask me。

 okay but you know and in some sense， the reason for that is that still you after 50 years。

 almost the best thing we know how to do in many cases is this time hierarchy theorem。

 sort of self-reference argument and it just doesn't seem powerful enough to tell us most of the things we want to know。

😊，What one can do is one can apply the time hierarchy theorem to other resources besides time。

So just like there's a time hierarchy theorem， there's also a space hierarchy theorem。

And the space hierarchy theorem just says that know if you have more memory then you can decide more languages than you could with less memory。

 so for example， space and cubed is a strict subset of space into the fourth。And so forth。呃。

Space of n to the E is a strict subset of space of n to the pi。😊。

you know and how do you prove that well exactly the same way that you prove the time hierarchy theorem just like replace time by space throughout okay you say you know define a language that consists of all the touring machines that you know eventually halt and accept having used no more than end the 3。

5 space， something like that， okay certainly we could decide that language and space of end to the fourth you know just you know with plenty of room to spare just you know a little bit of overhead for doing the simulation okay but if we could decide that language in space of N cube then we could create a self-reference paradox okay where a machine simulates itself and then it does the opposite of whatever it does okay。

So in general， for almost every resource we're able to prove some sort of hierarchy theorem like this。

 you know， so all the difficulties in computational complexity in some sense come when you're trying to compare different resources。

 okay when you're trying to compare time versus space or time versus nondeterministic time。

 okay I haven't even told you what that is yet， but that's going to be what leads to the P versus NP question。

Okay so so now you know you'll notice I was a little cooly in stating you know what did the time hierarchy theorem and the space hierarchy theorem even say okay you know I just put in particular examples of numbers here right n squared versus n cubed whatever you know and certainly it works with those numbers okay but you know you might ask what you know what is the general statement right you know is it true that every time you know F of n grows more slowly than G of n that time of F of n is strictly contained in time of G of n right that would be like the strongest statement you could hope for okay well that's not exactly true okay you have to be a little bit more careful in how you state this thing。

😊，There are two reasons for that okay one is that like I said before。

 there's a little bit of overhead that goes into the simulation right that。You know。

 certainly in the case of time okay the other reason is that you know we've got to make sure that the growth rates that we're talking about are somehow reasonable growth rates okay if they aren't then the theorem is actually false can be false all right so let me。

Let me give you a formal statement of the time hierarchy theorem。So first。We need a definition， okay。

 so let's say I have some rate of growth， you know， some function F。

 then we're going to call F time constructible。If there exists a touring machine， M。

It takes n as input， let's say written in unitary notation， this part actually isn't that important。

 you know， that takes zero to the n ass input。And runs。And runs for F of N steps。Their hots。

Okay so you could think of it as like you need a way to compute F of N using about F of N time。

 in some sense。😊，Baically any of the natural functions that will arise in algorithms and complexity will be time constructible and yeah。

Yes， and all。Yeah。Yeah， I mean， it's very easy， you know， if you had a machine that runs forever。

 you could say it passes through every F event， right， but you know。

 yeah we want it to halt after F event steps exactly。😊，Good。So。

So you know exponential function it's time constructible。

 you know by the way you know you know we've talked about polynomial and exponential growth rates that's right but in complexity you also deal with plenty of growth rates。

 so let's say here's two to the n here's n squared。

 you deal with plenty of growth rates that are somewhere in the middle like n to the log n power。

 for example， this we call quasi polynomial right， a little bit more than polynomial。

 this comes up sometimes more rarely you have something that comes up like two to the two to the square root of log n。

OkayAlso intermediate， you know， I mean we have discussed growth rates like two to the n cubed。

 which some people call exponential and other people don't that's others call this subex。

 that's a matter of definition， actually I think my personal favorite growth rates of all in complexity theory are。

There are functions F。Such that F of F of n。Is exponential。

You might have fun trying to think of what such a function would be。

 what's the function that when applied twice to n gives you2 to the end？All right。

 well I'll give you a hint， it's not any kind of function that like you've ever seen。

 you know an explicit name for， okay that you can describe you in sort of any way other than this one right formally they exist。

 you can prove that they exist and they even arise sometimes in complexity theory。

 but these are called half exponential functions。😊，And。you know I think as a kid。

 I once sort of you know just sort of you know wasted a huge amount of time trying to find such a function you annoying myself about it well you know they exist but you know there's no like closed form expression for them so you know I then there are even third exponential function you know or F of F of F of n is exponential all right so there's lots and lots of growth rates and but all of these two are time constructible there's no problem building a touring machine know that does something like this okay so what isn't time constructible。

😊，Well， the busy Beaaver function。Its not time constructible， okay。Well， why not？Well。

 because we already proved that it grows faster than any computable right function by。

You know by you know， and if busy beaver were timeconible that would contradict that okay so you know but that already points to why we have to be careful with the the time hierarchy theorem right because like it's not true that you can do more in busy beaver amount of time than you can do and like a little bit less than that you know square root of busy beaver time right because like you're way up in the stratosphere you know。

 like it's not true that you know like there are more birds you know100 miles high than there are 500 miles high right there's just no birds that either either height okay you've just gotten too high they're just you know。

 so it's no longer true that with more running time you can do more because you've passed the limit of where you know of the running times that they're achievable by any algorithm okay but even down what's weird。

Is that even down lower， so even like way below the busy beaver function。

 you know within the computable growth rates， it was proved in the '60s that there are gaps， okay。

 so like you can have gaps you know between like time time constructible function and the next time constructible function where there is no touring machine that runs for that amount of time。

 okay， so in other words， there are functions F，Such that。You know， these are going to be very。

 very large， very， very fast growing functions， but still computable okay you know there will be computable functions F such that there's a desert between F of N and2 to the F of N meaning you know there is no touring machine that takes you know that halts in any amount of time that's more than this and less than this okay so within that region the time hierarchy theorem you know is just false。

 there's you know like it's not true that going from F of n squared time to F of N cube time lets you compute more know there's there's nothing there to be found can you know within the computable functions you can find these arbitrarily large deserts where there's no where there are no you know no running times of any touring machines and the fact that you can find such such deserts is called the gap theorem。

😊，Okay。That's the theorem that know there exists arbitrarily large deserts。呃。But what the the？

So the formal statement of the time hierarchy theorem is basically that as long as F is time constructible then the theorem goes through。

嗯。So it says if F and G are both time constructible and F of n is little O of Gn over log GN。

 so it's sufficiently smaller than G of n you know then。

Then what you can do in F of N time is a strict subset of what you can do in G of N time。This is the。

This is a general statement of the time hierarchy theorem Now here's a little question for you in the proof of the time hierarchy theorem。

 where did we ever use the assumption that F was time constructible？We must have used it somewhere。

 because I just told you that with no such assumption， the theorem is false。

 where did we use that assumption？I snuck it in somewhere without telling you。Anyone。Well。

 let's let's go back to the very first step the step where I said you know just consider the language where the language consisting of all touring machines that halt after about F of N time steps and I said clearly we can recognize clearly we can decide that language and a little bit more than F of N steps obviously we can do that and if F of n is n squared or n cubed that is indeed obvious but if I gave you a touring machine and I ask you does and an n and I ask you does this machine halt after busy beaver of N steps then you you can't do that because you can't compute busy beaver of N so just in order to compute to set up the alarm clock that's the technical name for it by the way。

 just to set the alarm clock that tells you how long the touring machine is allowed to run for。

You're going to cut it off and say， okay， it has not halted in the requisite amount of time that already requires F to be time constructible。

Okay。So that is where we use the assumption。Yes。Yes， that's a little that is a little O。

 little O means F of n has to grow at a slower rate asymptotically than GN over G ofN。😊，嗯哼。😊。

GN over log GN has to grow asymptotically faster。No。That big A means at least as fast。

 little L means strictly， okay， we talked about this like n is big O of n。

 but n is not little O of n。And is little of n squared。And is little of n to the 1。01。

But n is not little L of n， because it means the one has to grow faster than the other。Yeah。Yes。

 it's a subset， this notation means it's a strict subset。

If I wanted to say that it's not contained in， then I would write that。All right。

 and then the statement of the space hierarchy theorem would say that。

If F and G are space constructible。All right， what does space constructible mean it just means you know you're given there is a touring machine that takes0 to the n as input。

 you know， goes and uses F of n tape squares and then halts or you know like thelim F of n tape squares。

 you know thelim of territory that takes F of n tape squares and then it halts， all right。

 so if FG you know once again any natural functions you can think of will be space constructible once again you know one can make up weird ones that aren't so if F andG are space constructible。

And sorry， an F of n is a little L of G of n， so the space hierarchy theorem turns out to be tighter and you don't even need the log factor for it。

 okay then space of F of n is a strict subset of space of G of n。Okay。All right。So。

So another kind of a funky question that people can studied in the prehistory of complexity theory and which you I think is really cool is is this。

 know we've been talking about like know I've been talking loosely about sort of the complexity of a problem meaning like is this problem you solvable and squared time you know is it solvable in linear time does it require two to the end time。

 okay but you know we could ask the question does every problem have to have a single complexity so for every language know there have to be one fastest touring machine for that language？

Or could there just be an infinite sequence of faster and faster ones。

 with no one of them being asymptotically the fastest？Okay， so you know。

 so this is like another kind of basic conceptual question that we should get clear about and you know that may sound like something weird okay。

 but but actually you know something sort of like that is often what happens in practice in algorithms research okay often what happens is that you know you have like there's some really simple algorithm you know that works pretty well in practice for solving your problem right and then。

😊，You know but then if you look in the textbooks， you know there's a theoretically more efficient algorithm you know that people thought really hard and discovered okay and so why doesn't everyone use the more efficient one well you know first of all it just more know it more complicated it's harder to implement whatever but you know and usually the other one is fast enough in practice right but secondly you know usually the sophisticated algorithm doesn't even start outperforming the naive algorithm until you get up to inputs of a certain size right if you're below that size then you might as well just use the crudeer algorithm okay so integer multiplication is a good example right we all you know we know。

I'm going to assume you remember from first grade or whatever you know how to。呃。

You know how to multiply two integers right and this is a quadratic time do they still teach that in element elementary school this is a quadratic time algorithm that we all learn right you compare because you have because each digit here gets multiplied against each digit here and then we do you know a series of additions and then carries and so forth okay so we all learn a quadratic time algorithm for multiplying integers you know multiply two n digit integers in n squared time okay but you know some of you probably know that there are more efficient algorithms that have been discovered right there's this carrotsubba algorithm that takes time to like n to the what is a log based two of three something yeah and then there are algorithms based on the fast four year transform which take。

😊，Basically n times poly log of n time or it's n times log of n times some I don't know some more cruut over on the side like log log of n log star of n。

 some stuff like that you I forget exactly what the best is that's known but at something like that okay so then know well you you can that's an amazing fact that you can know it is possible to multiply to end digit numbers in almost linear your time you know using the sophisticated method right then why doesn't everyone use them well you for small numbers you know it's faster just to use the grade school method right if you got up to numbers with hundreds or thousands of digits then these other ways start becoming more efficient so like at some point you when you get up to some number of digits I don't know what it is dozens。

 hundreds it's going to depend on your machine architecture little but at some point to carry。

suba algorithm will start out performing grade school multiplication okay but Katsba will still be doing better than the Four year transform method okay and then only when you get out to even more digits will the four year transform method be doing better so okay but then you could say well you know is it really clear that there's a single fastest algorithm right maybe。

As we go up to higher and higher numbers， there's just an infinite sequence of better and better algorithms。

 you know， better and better， you know in the theoretical sense that they start winning you at larger and larger input sizes so for each fixed input size there would be a best algorithm for that input size。

 but as you went out to larger and larger input sizes。

 you know there would be infinitely many better and better algorithms that would start taking over as the best one。

Okay， well， we can't rule out that that happens。Oh。Another famous example where you know。

Where we've seen something like that behavior is the matrix multiplication problem。

 okay where you know you're given。To end by N matrices， you want to multiply them。

 so if we just did this the naive way， what would be the complexity anyone？What？

N cubed exactly right， it's you know every row over here has to get interproed with every column over here and each inner product takes you linear time。

 so that's n cube time overall， or if we were going to write the time in terms of the size of the matrix。

 then what would this be。😊，As a function of what is n cubed as a function of the size of the matrix？

The meaning the number of bits needed to write down the matrix。And to the no， well。

 how many bits does it take to write down the matrices？

N squared- what is n cubed as a function of n squared？

What power do we raise n squared to to get n cubed？

Threehas right so this is yeah so technically we should call this an n to the three/ hals algorithm right because the input size is n squared the algorithm is n cubed Okay。

 you know by convention we call this an n cubed algorithm okay so。😊，嗯。

Okay but in any case you know this is not a linear time algorithm you know even if we measure it this way it's not linear time but it doesn't feel like there's a lot of juice to be squeezed out of it right if you know it feels like this this seems like kind of obviously the best thing that you could do what else is there to do right and you know see like if not this is like like a case story and why complexity theory。

 you know why the subject matter of this course exists in the first place because if we just want it to be informal about it we could just say you know all right well obviously you know you need N cube time to multiply two matrices end of story what else are you going to do you know it's that simple okay but you know today we have the attitude and no you can't just make statements that something is the best possible you have to try to prove them you know even if no matter how obvious it seems to you you know you have to prove。

That your algorithm is the best okay and all you know often it's you know or at least you know if you can't prove it then fine you know admit that you can't prove it you know admit that there that there's a mathematical question there that you haven't answered okay and why do we do that is it just because it's hair splitting it's because you know dotting eyes and crossing Ts and stuff well you know maybe there's some of that but you know the other thing is that sometimes the obvious optimality statements are false okay and that's what happened in this case so Strosin in the late 60s？

Discovered。An algorithm to multiply two end by n matrices at about end to the 2。

78 time okay you know you should see it if you haven't。

 you it's probably done in6 maybe done in 6046， it's very， very clever。

 you do a divide and conquer thing where this is the log based  two of7。

By the way okay you split up your n by n matrix into four and over two by n over two matrices and then you figure out how to like multiply to two by two matrices using only seven multiplications rather than eight by clever rewriting of the problem and then you recurse。

 okay， so。You see you split up your problem into seven problems involving multiplying n over2 by n over2 matrices and then you apply the same algorithm recursively to solve those smaller problems and so forth until you get down to constant sized matrices okay so this is a more complicated algorithm but when you get up to large enough matrices then it's more efficient okay and and and that can even be seen in practice you know strss and multiply is occasionally used in practice you know you know for multiplying large enough matrices it can be a net win okay but then you know this made people really want to know what is the ultimate complexity of mat multiplication could it go all the way down to n squared know which obviously you need at least n squared time to this day no one has proved any level。

bound on the complexity of matrix multiplication that's better than n squared okay you know all we know in some sense is that you have to look at all of the entries of the matrix you know the matrices that if you want to multiply the market which is kind of pathetic okay know in the meantime people have found a sequence of better and better you know asymptotically better and better matrix multiplication algorithms so there's one that takes there was one later that took maybe end to the 2。

7 or 2。6 then there was one that took end to the 2。

5 or so then there was this coppersmith winnegrad result in the early 90s that said that you could。

Biply two end by n major season and end to the 2。376 time okay。

 this was a tremendously complicated you know algorithm and。know the 2。

376 came from solving some massive numerical optimization problem okay and no one would ever want to implement this thing right this has been described as a galactic algorithm in the sense that the smallest matrices where it would start outperforming the quote unquote worsese algorithms would be know like matrices that it would take the entire galaxy to write down。

😊，RightSo you know， you could say like at this point， you know。

 we've maybe passed the point where this is of practical interest right now it's just we want to know the answer。

😊，You know， but you know， then a a good friend of mine。

 Vigie Vasalevska and independently a guy named Andrew Sts in Edinburgh， like four years ago。

 you know， this stood for a very long time as the best anyone could do and then just just three or four years ago you know。

 they improved Coppersmith and Winnerad's analysis。

 they used computer search to automate large parts of the proof and they managed to get it down to wait for it 2。

373。😊，Okay， and so no one knows how far it's going to get。😊，So the picture is， you've got this。

N cubed whatever from this the standard algorithm， and then you've got the strauos and multiply which is worse for a while。

 but eventually becomes better eventually there's a crossing point when n becomes large enough right and then you know there's the more theoretical algorithms that。

's you know at some later crossing point maybe become better right and then there's maybe Strs and that or sorry there's copperppersmith Winnerad that you know maybe like way out here。

 there's a crossing point and it becomes better right so you know so you could wonder is there just an infinite sequence of better and better matrix multiplication algorithms you know again。

 I think most people would suspect not but but we can't rule it out it could be for example that for every epsilon greater than zero that there would be an end to the two plus epsilon algorithm？

But that there still wouldn't be an n squared algorithm。Okay， that's a theoretical possibility。Okay。

嗯。Okay， and now。A result from the '60s called the Blum Speedup Theorem says that basically you can construct artificial problems where that behavior actually occurs。

 you can construct problems with the property that they have no fastest algorithm。

Okay and make you can make it as dramatic as you want， so let me give you。

 let me state the theorem in a way that you'll have to do a double take because you know you'll think that I misstateated it or you know that this couldn't possibly be right okay。

There exists a language L。Such that。For every touring machine， M。That decides L。In。L of F of N time。

There exists another touring machine and prime。That decides L。In O of log of F event and time。Okay。

There exists a language such thaturing for every algorithm that there is to solve it。

 there is also an exponentially faster algorithm。Than that one。

Okay so you know now how is that possible well first the first thing to know is that the F。

 you know the F's in question right all of the running times that we're talking about are going to look like stacks of exponentials。

 they're going to be really enormous okay like you know here's a function that like you could take you know let's say we say twoterated to the n so two to the two to the two to the two and so forth n times right you can take logs of that functions。

 any finite number of times you want and you're still going to have a very。

 very fast growing function。😊，Okay so that's the first thing to know right the second thing to know is that as you go to you know the asymptotically faster and faster algorithms。

 you're going to be racking up bigger and bigger constants in the big O okay so the picture is going to look like this right that as you go up to larger and larger ends you know like like at some point you know like you know there's an F of n algorithm than at some point the log F of n algorithm takes over and then at some point you there will be an algorithm that takes log of log of F of n time and then log of log of log of F of n time right all of these are still extremely rapidly growing functions okay but as you go to larger and larger ends you know you know at some point each one will take over from the last okay you can construct。

😊，Languages that have that behavior， I'm not going to go through the proof because it's kind of a nasty diagonalization argument。

 but just to be aware that such things can happen。All right， questions about that。😊，而呀。Okay。

 that's an excellent question how often do we meet it well you know we've essentially never met such a situation or at least we're in real life where we know for sure that it happens we can't rule out that so what I was saying before is that for problems of practical interest like matrix multiplication。

 we can't rule out that there's no fastest algorithm and there's only an infinite sequence of better and better ones。

 but the only problems for which we can prove's how it happens or these artificial ones that we construct to have that property。

😊，Yeah。いや。Yes， yes， you can also get that so in fact， you know you can get。Yeah。

 that's a very good question。You can explicitly construct a language L。Such that L is in time。

Like I was saying before， time of n2 to the n to the two plus epsilon for all epsilon greater than0 but。

L is not in n squared time。You can using the speed up theorem。

 you can construct examples of languages L that are solvable by an n to the 2。1 algorithm。

 and end to the 2。01 algorithm and so forth， but not by an n squared algorithm。

you can do that also right and again， you know some people think that maybe matrix multiplication could be like that。

 but we don't know。All right。So now I want to introduce onto the scene some complexity classes that will play an important role for us。

 okay。And the first of these classes is P P is sort of the one that started at all。

 right and this is sort of our。U。There's P。Say hello， okay， this is our sort of modern， you know。

 well you know， this stood for many decades as our notion of what is efficiently computable， right？😊。

And。I'll simply define it。To be the set of all languages that are decable in some polynomial amount of time。

're decided，So the union over all constants K of time and the K。呃。Okay。

 so you know you could ask several things about this。

 you know you could ask why do we focus on polynomial time as the criterion of efficiency right you know and the short answer is it's mostly a convenience right so last week I told you about sort of the empirical phenomenon right that most of the problems that are sort of efficiently solvable in the real world you know are so sort of because there's some polynomial algorithm for them you know and or n squared or whatever okay whereas you know most of the problems we meet that are intractable know like require an exponential algorithm right and yes sometimes you find something in the middle like an end to the log end time so you you deal with that when it happens but。

Okay， but you could say you know why not take our criterion for efficiency to be you know n squared time n squared time or less and and that would rule out these weird cases like n to the 10 time that actually we don't want to call efficient right okay and then you and then you that would of course be open to the objection。

 someone could say well that's an arbitrary choice。

 why did you pick n squared why not n cubed you know know or whatever and in fact you know what is solvable in n squared time on one machine model might take more than like a RAM machine might take more than n squared time on a touring machine whereas whereas with P we don't have that problem so one advantage of focusing on polynomial time is you know。

This class has a huge degree of robustness。To changes in the machine model okay so almost any reasonable model you can think of for a digital computer turns out to give rise to the same class P and why is that well because the different models can all simulate each other you can simulate a touring machine using a raM machine you can simulate a raM machine using a touring machine。

 you can simulate both of them using a system of billiard balls using Conway's game of life。

 or some cellular automain or know all sorts of things and those you know simulates will incur slowdowns and sometimes they'll be polynomial slowdowns like we saw before to simulate a raM machine on a touring machine incur a quadratic slowdown right but it's extremely rare that you would get an exponential slowdown in simulateulating one type of computer by another type okay。

It'sOr that the slowdown would be more than polynomial。So。Okay。

 so that's one justification for focusing on polynomials。

 another justification is that polynomials have extremely useful closure properties okay so like you multiply two polynomials。

 you get another polynomial， add them same thing， you compose two polynomials still another polynomial okay why is that useful wells say that you know I had like an n squared algorithm you know you know let's say that I had instances of size n and and but then I did a reduction where I produce like instances of some other problem of size n squared and I feed those n squared size instances into an n cubed time algorithm then what's going to be the total complexity that I'm dealing with here。

😊，Well， if I feed an n squared size instance into an n cubed algorithm， then it's going to take。

N squared cube time， right， which is n to the6。Okay， so so yes， you know。

 I can get large exponents by composing things， but you know I'll remain within polynomial time okay so if I just want a reason about like what is efficiently solvable like I'm allowed to compose things I'm allowed to sort of chain a bunch of reductions together and you know as long as each one is individually polynomial you know then I know that the whole thing is polynomial okay so that's a very useful property that polynomials have。

Okay。So。Okay， so there's a general， you know there's a generalization of the church touring thesis that we talked about before that sort of。

 you know， well， we call the extended church touring thesis and this is basically the，Belief， again。

 you know， this is not a theorem that can be proved， but it's a thesis that。

Basically says that what is efficiently computable by any sort of realistic physical means。

 let's say， coincides with the class P。Okay， you know。

 of things you can do in polynomial time on a touring machine。 Okay， so again， you know， you can ask。

 what kind of statement is this， even right， you know。

 like it has something of the character of a definition that， you know， we're just defining。

you know what we mean by efficiently computable to be P okay。

 but but I think that you know that the right way to sort of think about it and this is sort of even clearer with the extended thesis than it was with the original charge touring thesis is that this is really like you know a claim you know this is a falsifiable empirical claim about the physical world you know about the laws of physics right so it is saying that。

You cannot build a physical device that will efficiently solve problems that are not in pig。

That's you know I think that that's really what we should interpret this to be saying okay and the advantage of that way of thinking about it is that that you know encourages you know us to think about well is that really true you know what do we know about the laws of physics you know could we build a physical device that would violate this thesis and it would let us compute something that's not in P you know so like most you know most of the obvious things you would think of don't work because you you just build some some standard kind of digital computer and yeah you know you'll find you can simulate it by a touring machine with only polynomial slowdown there by proving that that device cannot do anything outside of P okay but you know there are。

You know there are various more or less crazy ideas you might have for sort of how to go beyond this extended church touring thesis right so some of my favorite examples or first of all you know you could have the relativity computer right you know this would be a way to actually speed up computation by arbitrary amounts you could just start your computer working on some really hard problem you know leave the computer on earth you board a spaceship you accelerate it to close to the speed of light that you decelerate return to Earth in Earth's frame of reference billions of years would have passed you know all civilization would probably have collapsed you all your friends would be long dead but if within the rubble you can still find the computer it's still running you can read out the answer to your hard problem right。

So it's an interesting question of why doesn't anyone try that and I mean if you're worried about your friends being dead。

 you can bring them with you on the spaceship。😊，I mean， you know it's。

You know it sounds like a way you know that in principle you could accelerate computation arbitrarily right you know I think in this case there's actually a very very interesting thing that physics lets us say about this right which is that you know in this whole discussion we've ignored the amount of energy that you would need to accelerate to that close to the speed of light right so if you really want to get you know to get like an exponential computational speed up this way。

 you know the kind that would violate the extended church touring thesis then you would you know relativity tells you that you would have to accelerate exponentially close to the speed of light like so that the difference between your speed and C would be like2 to the minus n something okay but you then how much energy would you need to get that close to the speed of light well turns out you would need an exponential amount of energy okay so then that sort of pushes the problem back to you know even before liftoff you know you're going to spend exponential time just fueling up your space。

😊，For a takeoff right you know where you're going to get all that fuel you know the world doesn't have two to the annual oil reserves right you know in fact。

 you know even you know you know this is presumably saying your spaceship would have to be you know you know just to store all the fuel would have to be exponentially large you know and therefore it takes you exponential time just to build the thing right so。

😊，and you could say， okay， but couldn't I compress fuel by an exponential amount。

 but well eventually if you compress too much energy and too small of a region。

 what's going to happen anyone？It's going to collapse to a black hole yeah right and then what have you accomplished right so so you know when you look at like one aspect of the laws of physics and you ignore the others it can look like the extended territorying thesis is falsified。

 but you know it's very important to sort of you incorporate everything okay so just I'll do one more example。

 so there's what I like to call the Xenos computer， okay and this is a computer where。😊。

It does the first step of its operation in one second， the next step in half a second。

 the next step in a quarter second， the next and an eighth second and so forth。

 so after two seconds it's done infinitely many steps。Okay。Again， you know。

 I mean this would be a way that you could even solve the halting problem let alone problems outside of P okay so again it sounds like a great idea。

 you know why doesn't anyone build this and once again you know there are people who try to do something very much like this okay have you heard of overclocking right there's like a whole group of people who try to like run their process faster than the recommended speed right they overclock it okay but any of you know the danger and doing that like why doesn an intel just overclock all of its chips by a factor of 10。

Yeah， heat， right， you run it too much faster， it's going to overheat。

 it's going to melt okay that's what happens， right this is why your computer has a fan。

and this is why。You know if you look at what supercomputers are you have been for a while now often they're just you know a huge array of you know off the shelf you know intel chips or whatever you know processors but you know often they're cooled you know sometimes you know you know to very。

 very low temperatures so that they can you know be safely run a lot faster okay but you know but now you can you know once again you can ask about what are the fundamental limits as you want to run your processor faster and faster you would have to cool it more and more right more and more cooling requires more and more energy okay eventually you know when we get down to like you know the subatomic level or whatever right you we should no longer even think about it in terms of cooling right we should just think about it directly in terms of the amount of energy needed to you know achieve a given clock rate okay。

So you you can imagine like the simplest type of computer you could have would be like a photon bouncing back and forth between two mirrors。

 let's say， right okay but now you know as the two mirrors got closer and closer together。

 you know so basically you know a cycle， you know the clock time of your computer is faster and faster。

 as these mirrors get closer and closer together and the photon is bouncing back。

 know at a shorter and shorter rate between them， okay。

But let's say that you wanted to run your computer at 10 to the 43 Htz。Okay， what's that。

 that's about one step per planck time。 Okay， this is know so you， and that would mean that the。

That the photon you know is bouncing back and forth， you know。

 between mirrors that are only 10 to the minus 33 centimeters apart okay， at this point。

 you know one can calculate that you've can find so much energy into so small of a region that what happens everyone。

Your computer just collapses to a black hole， but you know I really like is nature's way of repeatedly telling you not to do something so。

Yeah， so there does you know as you know and of course this has not been directly observed。

 this is just inferred from what we know about you know combining the speed of light you know and h bar of quantum mechanics in general relativity you know and you sort of combine them all into one you know unit to get like a unit of time and this is what you get 10 to the 43。

 okay， of course we've never gotten anywhere close to that， but yeah。Yeah， I was just coming to that。

 thank you。So all right， so you know we've seen these sort of you know all science fictiony sort of proposals right and then you know you may have heard about quantum computing。

 this happens to be what most of my own research is about。

 quantum computing at first sort of sounds as science fiction as those other things that I mentioned you know that you would you know harness the exponentiality of the wave function and quantum mechanics to maybe you know get exponential speedups。

 you know if not for all problems， at least for some things， you know。

 but this one you know as far as we know， you know should actually work someday。😊。

So you know there are experimental efforts you know all over the world to try to you know develop the technologies I should say that will eventually lead you know that could eventually lead to a useful quantum computer okay there's also a lot of hype in this field you know a lot of people claiming to be on the verge of having practical quantum computers when they're not okay you know if your question is you know sort of what do the laws of physics ultimately allow then I think that in this case the burden of proof is really on the people who think that quantum computing is not possible sort of they have to explain what is wrong about quantum mechanics or our present understanding of quantum mechanics that would rule it out so so but but in either case you whoever is right you know I really hope that that will find out in some sense if the skeptics are right if quantum computers turn out to be impossible that that will make me way way more。

Excited and thrilled scientifically than if they turn out to be possible。

 because then that will mean we'll have to revise our understanding of physics。😊，Okay。At this point。

 you know believing that quantum computers can be built is just sort of the boring conservative option。

 the one that requires no change to you know what we currently think about quantum physics right I'm going to tell you a lot more about that in the last few lectures of the course。

 but the bottom line，iss that if quantum computers can indeed be built。

 then it looks like the extended church touring thesis is false。

 okay or at least maybe it would be better to say it needs to be revised a little bit。

 okay it should really be the quantum extended church touring thesis and it should say that the limit is quantum polynomial time。

Okay， but you know but that that makes it you know really dramatically clear that you know。

 when we're talking about whether P is the ultimate limit of you know what we can compute in the physical world。

 we're ultimately asking an empirical question right you know and quantum computing may supply a dramatic answer to that question okay so but that's all for later。

😊，For the next few lectures I'm going to tell you about P and NP and the P versus NP problem and this whole structure of classical complexity theory and then by the way when we come to quantum computing we'll find that this structure。

 this whole structure can sort of be adapted to the quantum case remarkably well so that someone who knows like classical complexity theory is like as well placed or in some ways even better placed to learn about quantum computing than someone who knows quantum physics but not classical complexity theory。

看。So。All right， so let's define a few more complexity classes。

 because I'm not happy with having just P。Okay。All right， so first of all。

 you know everything we you know almost everything we do with time， we can also do with space okay。

 so we have a class called peace space， which is just the union over every K of space and to the K okay this is the class of all problems that are solvable with a polynomial amount of memory so you know although possibly an exponential amount of time what's the relationship between P and P space anyone。

Is either one contained in the other？Yeah， exactly。

 we saw last time right that every even for every individual K。

 time of n to the K is contained in space of n to the K。

 from which it immediately follows that P is contained in P space。😊，Okay。All right， good。😊，Okay。

 then you know we can think about larger amounts of time if we want。

 so there's a class called X which is。The union over all k of time2 to the end of the K。Okay。

 so this is you know2 to the n time，2 to the n squared time and so forth。

 now x should not be confused with its close cousin E。😊，B is like truncated X。

 okay and this one is the union over all k。Of two to the k and time。Okay。

So here you know you're not allowed to have like two to the n squared time。

 just two to the some constant times n， I didn't make up these names， by the way， right。😊，And。

What else， you know， I mean we can go further if we want， we could have X space。

This is the class of all the problem solvable in two to the end to the K space possibly requiring doubly exponential time okay so and so forth。

 all right but you know what are some containments among these classes。

 what's the relationship between P space and X， anyone？Well， once again。

 we discussed this question last week， what can we say in general about the containment of space classes and time classes？

Well， well there's a time hierarchy and there's also a space hierarchy。

 but now we're asking about the relationship between time classes and space classes， okay。

 space of F of N is contained in time of what yeah。😊，Yeah， exactly you know。

 basically like about time of2 to the F of n， okay。

 which means that peace based is going to be contained in what and。😊，Well。

 P space is polydommial space， right， is space n squared。

 so space of n squared is contained in time of 2 to the n squared。

 roughly right space of n cube that's contained in time of  two to the n cubed roughly because it ends again an n cubed space machine can only enter about two to the n cube distinct states before it's going to get into it and a loop。

Okay， so。So what does that mean？Yeah。Yes， yeah exactly。

 it implies that peace space is contained in X。Okay， now what about the relationship between P and x。

 anyway， what can we say about that？Strict upset， why？Yes， exactly。

 the time hierarchy theorem tells us that P is a strict subset of x。😊，Okay。

 now let's look at at this sequence of inclusions， now can anyone here prove that P is not equal to P space？

😊，Seriously， can anyone prove it if any of you can please come talk to me okay that is you an unsolved problem you know like considered like essentially as hard as the P versus NP problem that we' come to this is you know to prove that the discontainment is strict you know that P is strictly contained in peace space you can do things in polynomial space that you can't do in polynomial time if anyone can prove that that will be one of the great discoveries in the history of mathematics okay all right。

 what about P based versus X。😊，Again， if you can separate these two please come talk to me okay this is another huge open problem you know are there things that require you know are there problem solvable in exponential time but where you need more than a polynomial amount of memory okay no one knows the answer you know I mean I mean presumably yes right you we think yes but no one can prove that okay but nevertheless what can we say about the relationship between these two questions anyone。

Yeah。Well， at least solving one of them in one direction would solve the other。

 right so if we prove that P equald P space， then what would follow about P space versus X？😊。

That in that case they would have to be not equal likewise， if we proved that P space equal X。

 then it would follow that p was different from P space so in other words。

 at least one of the two inequ know at least one of these two containments has to be strict。😊。

Because at either end， P is different from x， right？Ahu。Yeah。

 yeah exactly if p is not equal to P space， then P space versus x could still go either way， right。😊。

Yeah， yeah right， I mean it's entirely possible and in fact。

 almost all of us would conjecture that both containments are strict。

 that peace space really is does just sit in between the two and that all three of these classes are distinct。

 but all we can prove using the time hierarchy theorem is that they can't all be equal。

 at least two of the three have to be different。So that's the weird situation that we're in。

All right， so let me。And you know， I should mention that just like the P versus P space question you know is open。

 no one can prove it you know， so is the X versus X space question and so forth。

 you know basically you and anything where the answer doesn't follow from a time or space hierarchy theorem。

 you know， the good money is on its being open， but but let me know now show you another of the things that we do know。

 you know you know that maybe is a little bit weird the first time you say it。Okay。

Okay I claim that if p equaled p space， then x would also have to equal x space okay so these two questions are related to each other okay and you know by the way the other direction no one knows okay it could be that x would equal x space without P equaling P space okay but you know there's you can take collapses of complexity classes and you can translate them model as you not playing okay and the way you do that is using a technique called padding which is also on your p at3 okay so let me let me explain how it works with this example so we're assuming that p equals p space we want to show under that assumption that x equals x together all right so let's let L be some language which is an exponential space we need to show。

ItsThat L is in how are we going to do that actually in right， well。

 what I'm going to do is I'm going to define a new language， so let's say that。

It's letting them be for concreteness， let's say that L was solvable in space know or two to the n to the K I'm going to define a new language L prime which consists of which is a padded version of L so it consists of that is a party X for every x in L L prime contains the input x followed by two to the end to the K trailing zeros it just padded out with a whole bunch of you know useless looking zeros a but what have I done though well what can we say about L prime。

 what is L prime contained in anyone scary。Well， we knew that L prime was solvable in two to the end of the K space。

 but what is2 to the end of the K as a function of two to the end of the K I should buy100 sounds。

Linear， yes， so it's linear which means that this L prime must be decidable in linear space right because you know space linear in the length of the input。

 which I've now patted out so it's enormous because you just ignore all the trailing zeros and just go solve x decide whether x is you is an L using2 to the end of the K space which now counts as linear space and so we conclude that L prime is contained in peace space meets the definition it's in peace space okay but now what else can we say about L prime。

😊，Oh， I see anyone， right？I tried a little bit magic online Yes because P we assume p equals p space which means that L prime is in P okay but now what does that tell us about L itself well let's say you're given an input X you want to know whether x is in L what could you do cents whatever algorithm you had that you know use this huge number of trailing zeros you could now just add those two to the end of the K trailing zeros yourself and then run that algorithm right it's going to take time which is polynomial in 2 to the end of the K but what's a polynomial in two to the end of the K Yeah it's still x but still exponential so we conclude that our original language L was in X。

okay so from P equals P space， we got this higher up collapse。

 x equals x space just by this trick of padding out okay and on Thursday I'll show you some more crazy fun that you can have with padding padding combined with the time and space hierarchy theorems okay and then we'll talk about P and NP P versus NP problem。

 NP hardness， NP completeness， all that fun right。On of money。When it works， it's。

And they live in an interesting age。Mmhm。It's like， I remember。

 you're probably not old enough to remember the days of free internet。I've heard good stories。

It was like ad supported。Dial up internet。See， it's before A。It was， I think， concurrent。

So I was like a competitor， I didn't last very long。It was the early days of free everything。

 I think there were free phone long distance services we you'd like listen to an ad before you made your call。

だいないよ。Yeah， so we're kind of back to that again， it feels like。Exceon。

 and there would it be I don't know。powerま。s some result of that time。the appropriate。He Scott。对起。Oh。

Yeah。