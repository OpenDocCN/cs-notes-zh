# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P26：lecture 26.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/89c95edfd59ce96739719d1e17124521_0.png)

Welcome and welcome everyone to the last lecture of this course。你てし on。So today， we'll talk about。

Lowash lolemma and an algorithm for constructive low wash lolemma。So， today's lecture 26。

So all right， so this is a。Final lecture。 So we're going to look at a very cute and very simple to describe algorithm and quite elegant analysis of the algorithm。

 Allright， so what what is the。く。So as they said it will be。

Talking about Lo local lemma and an algorithm proof a constructive version of it。For the most part。

 we'll be working with an example， so lets let's start with the example right away and we'll get back to the general low as local andma later。

In the lecture。Okay， so here's an example。So here's a problem， I guess。

 so example problem we'd be looking at this caseat。So what is Kat。

 well we know what it's basically three set。嗯。With k you know， with k in place of sleep。Right。

 so essentially you have。Variables。X1 through xn。hi are布连。Okay， and。You have clauses。

Cls are let's say C1 through CM。And each clause is a disjunction is an R of k literals。

 so if I look at the clause C， it looks like some variable X1。系 know or。You know， maybe not exc too。

哦。Xite 3。Not Xi 3 or Xi 4。Up to X I K。Okay， so this is familiar to you if k equal to three。

 you know every clause looks like x or not y or z， and if k equal to2， it's too set。Okay。😊。

So those are the variables and clauses and of course， the goal is always find X。

Satisfying all the clauses。So here， what does satisfying mean。

 it's just that when you substitute the Boolean values x。

The clause is true so C you know CI is true if clear you know， for example CI is true or satisfied。

You know， as if and only either X one is true or。Not Xi2 is true or not X 3 is true or not X 4 is true and so on。

 So that's the。Okay that's what K set is it's basically you know we're all familiar three set with k instead of three。

Okay， and。So you know， one thing for example， if I look at a clause， let's look at foressat。

 let's say if I look at foressat and we look at a clause like x or y or z or not W。Okay。

 if I look at a clause like this， the only way that I will violate this clause is。

If I assign all the literals to zero， so there's exactly one assignment that you violate this class。

 so in order to violate this class I have to set x equal to 0。Y equal to 0。

Z equal to0 and w equal to1。So0，0，01。That's the only violating clause。

Violating assignment to this clause whatever else you assign it's okay you satisfy it except for one assignment so similarly。

 if I look at let's say I look at X i1 or know a caseat clause that looks like。X I。

 some case at close。Basically， there is exists exactly。1， unique。

Because one and unique are the same one unique violating。Assignment to this class。

Out of the two to the K assignments， exactly one way to violate it every other way would satisfy okay。

 something to sort of keep in mind。Okay， in particular。In particular， if I just。

Pick an assignment at random to this clause to this formula。

 every clause will be satisfied with probability1 minus1 over two to the K。其实。

The probability that random assignment。Satisfies a close seat。Some close。Cluse CI， the Kat clause。

Like case like class CI is basically you know。There's2 to the k minus1 satisfying assignments or the two to the K different satisfying assignments to that clause。

 so it's1 minus1 over2 to the K。so this is how case Act behaves。Okay， so that's caseat。

 So what's the。Theem that we're going to prove。So。Here's a theorem。For every Ksat formula。Wt。

Variable degree。Smaller than two to the K。Minus let's say， 100 or 20 for some constant。

 some large constant。嗯。There exists a satisfying assignment。And。One can find it in polynoment time。

One can efficiently find it。So。What is variable degree？Here， variable degree。By variable degree。

 I just mean the number of clauses in which any variable participates。Okay。

 this is the maximum number of clauses。嗯。In which a variable participates。其实。

The statement says if every variable participates in less than two to the k。Cls。Oh， Al， sorry。

 let me。 I think I got this number wrong。 So it's true to the K。Divided by key。

Less than2 to the K divided by k。Cluses the 20 is just for safety says say2 to the k minus 20 by2 k clauses then there is a set swing assessment and you can efficiently find it that's the theorem we' prove okay and this is actually just an exam consequence of a more general fact which is the lowest local lema I'll state that later on the class that's a more general fact。

This is quite nice to know。Okay。All right， so， so let's see what what is the。Okay。

 how do we show this theorem so we'll a describe an algorithm。

 which is a very simple algorithm to state。Okay， so here's the。嗯。I， so what。Okay， so what do you do？

要。So I'm going to write I guess， some kind of pseudo code here。So your input。I some casesat instance。

 caseat formula fee。Okay， and then what is your algorithm going to do so solve a phi。

Well what do you do start with some assignment。嗯， big。Random assignment。You，X。

K pick your random assignment， that's your starting assignment。Okay， then what。Of course。

 it's going to violate some clauses。 so we'll just。

Look at clauses that are violated and try to fix them。Okay， so we' say while。

Some clause C is violated。If there's some clause that's violated， you try to fix that clause。

Okay that's that's the algorithm so what how do you fix a class？Okay。

 so so now you have a clause which has so let me。嗯。Okay， let me draw。I。Pind of a picture here。

 So you have。These are my clauses。Each clause is on K variables。

 right so there are K variables inside a clause。And they share these clauses share variables and everything。

 okay， and so there's some clause that needs to be fixed， so let's say this clause is violated。Okay。

 so what do you do。First。Rerandomize the variables in the clause。

Meaning assign a random value to all the variables in the class。Assign random values to waves in C。

Okay， so now。Okay， so each time you assign a random values to a clause。

 you will satisfy it with probabilityty 1 minus1 over2 to the k you probably satisfied that clause but then in the process of course you messed up other clauses nearby right maybe this clause was satisfied let's say this is C1 its say C2 was satisfied early on but now you modified some of its values。

So maybe it's violated。And maybe someone else is violated， right so the neighbors。

 you will violate in the process of changing these values。So what do you do you you just。诶。

But just you just pick a neighboring clause that's been violated and you sort of re randomdomize that。

 like call fix of that。Okay， so what you're saying is。So it's basically。

As long as there's a neighbor which is violated， you go and fix that。While。That is。Some close deep。

Some clause D。Some neighboring cly。Neighbouring as in it shares a variable with C。

ClusD that is violated。What do you do， you call fix of D。是。That's the algorithm。

And when I say neighboring。I guess one thing is that it could also be C itself。Right， so。

D might be equal to C。Doesn't matter Basically you read random I see and maybe see still unsatisfied。

 So you just fix call fix again on it。 So it's like a recursive algorithm。 All right。

 so as of now this is like what you would。Sort of first try to implement and it looks hopeless that this thing should work because。

Yesす。We just start with a random assignment， you fix something and you recursively fix all its neighbors and repeat right so I think this sort of a general heuristic was around for a while and nobody thought it could prove it or it would work and it's surprising that you can actually analyze it and prove that this works。

At least in this setting where they were a low degree。嗯，其实 from了。Good。Okay。

 so let's see why this works。Any questions on the， is the algorithm clear？

So basically we're solving K Act you have all these clauses and your algorithm is just this simple algorithm。

 you pick a random assignment。See if a clause is violated。Call fix of C and fix of C。

Just reassigns all the values insides the class C。And in the process it might create violations or some neighboring clause might be violated。

You call fix of D。喺要逼。ok。Okay， so that's the。All right， so firstly。嗯。嗯。

So let me call this the I guess the。I guess I'll call this the outer loop。Or the top level loop。

So the algorithm and the way it's working， this outer loop will pick a clause and call fix of C in that and fix of C goes into recursion and returns back。

All right， so now the the first claim is。A simpleimple one。each time you。

Like for each execution of the outer loop。あ the。The number of clauses satisfied keeps increasing。

So the number of satisfied clauses。Increases。With。Each I each。Each iteration of the Out。

Outer loop as in basically whenever you call fix of C。

You know you call fix of C and it does something and you return back。The number of clauses that。

A satisfied has gone up。Okay， why is this true？ Well， it's true because of a more。Simple reason。

 if you look at any clause， if it was satisfied before you call fixie。

 it will also be satisfied after you finish fixie。Like let's。You know， fix， consider。

Some clause case， consider some。Clus D。Okay， D is satisfied before fix C。

And then D is satisfied after fixie returns。Okay。Okay。

 so basically why is that well you know you can look look I mean it's sort of the following thing right if you know all right。

 so what's happening so D look at the state of D。Okay。

 maybe it is satisfied soiv was satisfied before fixie and then you start。You know。

 as you as you run this fix of C routine， it you know D goes D keeps changing。

 maybe at some point it is unsatisfied。As the execution of fix C proceeds at some point unsatisfied and again。

 it's satisfieded and again， it's unsatisfied and so on Okay。

 and at some point fix stops and you return Okay， so look at the last。

Time when it moved from satisfied。To unsatisfied。It is the last time it moved from satisfied to unsatisfied what happened here well this clause D was happy on its own。

 it was satisfied。And then the algorithm came and messed up one of its variables。

That's the only way it got unsatisfied if you didn't touch it if if the algorithm didn't touch these variables。

It wouldn't have gotten unsatisfied。So basically， the last time D moved from satisfied to unsatisfied add the algorithm fix C。

knowThere is some recursive call a fixie。What it did was this was D。You know。

 it took some neighboring class C prime。And it modified the values there。O。But the algorithm。

 by definition， whenever it modifies a clause， it looks at all the neighbors and calls fix on them。

So after it modified C prime。It would have looked at D and were called fixed D。

So there's no way the algorithm would return。After it changed D from satisfied to unsatisfied。Right。

So in some sense， if a clause was satisfied before you call fixy if it got messed up in the middle。

 the algorithm will try to rectify it because thiss recursively doing that anyway。

 so it would rectify it so therefore if a clause was satisfied it will continue to be satisfied at the end。

Okay， and what else because you started the fix， you started， you know。

You started the algorithm by saying calling fix of C for some C that clause。

Will be satisfied at the end of the cieration。嘅 c。Visby。Satisfied。At the end of fixie。Therefore。

 you know， basically it means that you have at least one extra class satisfied each time the whole thing represents at least。

One extra clause every time。So this is easy so this just says that you know this outer loop。

 every time you run it you have one extra clause that's satisfied。

 so therefore a corollary is that the outer loop you know cannot run for more than m times。

Outer loop runs。For less than any time。Less than the number of clauses times right if you have M clauses。

 it can't run MM is the number of clauses here。Okay， this makes sense。

Okay and this is I mean not very surprising also， I mean what's really the crux of the matter is the way this algorithm is defined。

 this recursive inner loop。That's the part which is more suspicious because it。

Like don't we're not even sure if this terminates ever， right？LikeDoes this even terminate？Okay。

 it's not clear， so that's the more interesting part。O。But if it does terminate， you know。

 like every time then。The outer loop will execute and you'll end up with an assignment that such as all the classes。

So we're in good shape so let's suppose the only thing that can happen is you run this algorithm and it doesn't terminate at all。

 it just keeps running forever。All right， and we'll see why that doesn't happen。

 we'll see a proof of that， so that's the next part。Okay。Okay， so let's see this is。

So we want to prove that this algorithm that we describe terminates。就。So it's a very clever proof。

 it's really， really clever。嗯。And。嗯。So here's the sort we want to prove that the algorithm terms。

Here's the idea behind the proof or the overall structure of the proof。

So the proof idea is something goes something like this。Okay， so what we'll do is the following will。

We will have our algorithm execute。This are algorithm， it executes on fee。

Execute on some formula fee。Okay， and you know as a as we as it's a randomized algorithm。

 it's going to need random bits right， so in fact， when does it need a random bit whenever like the random bits it needs are。

Firstly。嗯。Firstly， the assignment X， right the initial n bit random bits n random bits like initially。

And this is the initial assignment text。And then every time。

Cllaawuse needs a particular clause needs to be resampled every time you want to re randomize a clause you need cablebits right so for every。

Cluse。C， if you call fix of C。When you re randomize this， you need k bits， need K bits。

But these are just random bits right so let's think of these random bits as something that the algorithm sort of generates in the beginning at the very beginning or basically it has a big long stream。

 let's just think of a long stream of random bits。Like a really long stream the you know the first n bits are x like it's x and the next like this is n bits and then they form x and then you know every K bits afterwards you use it for。

Closes and so on。Okay。So okay， that's what the algorithm is doing。What well do is。嗯。

We will simulate an interaction between an algorithm and another party， let's call him the debugger。

Okay。And。So here's a debugger and the algorithm。5。We will have the algorithm communicate with the debugger。

Communicate as in actually just send bits， send something to the debugger。

 like communicate one way to the debugger。嗯。And we will set up the communication in such a way that the debugger receives。

Some number of bits。Debugger receives， let's say L bits。He receives Ls。But。Is able to。诶。

Reconstruct the algorithm's random bits more than L bits。But can。Reconstruct。

Much more than L bits of algorithm's randomness。Okay。

 and that's the contradiction that will be the contradiction proof the proof by contradiction will be that algorithm will do this execution。

 it'll use some random bits from some sequence。But as it is doing the execution。

 it will make the algorithm communicate something to a debugger。

And what will happen is if this algorithm doesn't terminate for a while。

If the algorithm takes too long to terminate。Then。It will so happen that the debugger receives L bits。

 but can reconstruct much more than L bits of the algorithm's randomness。Okay， and。So， therefore。嗯。

Like it's a contradiction， like you cannot communicate much more than L bits of randomness using only L bits。

It cannot compress more than L bits of random L random bits into just L random bits， okay。

 so that's that's going to be the contradiction。O。So that's a little bit abstract。

 let's see what what exactly happens in this communication will be much more clearer as it goes。Okay。

 so that's the idea All right， so let's see what what the communication is going to be。All right， so。

嗯。Maybe。I'm trying to see if I can write here， I guess this is too crowded。😔。

People I can copy some of this。Okay， so。Okay， so this was the algorithm it's executing on some。Okay。

Okay， and then let's say here's a debugger。Debuer is just receiving bits。Okay。

 what does algorithm sent？All right。Okay， what does it send？It sends the following。Send。Okay。

 for every clause。😔，C on which fix of C is called。Whenever fix of C is called。

Albertton sends the name of the clause。Send。nameam of glass。Name or index， right？

Let's say name of Classy for now。Meaning you want to communicate which clause was called fix of Cion。

 algorithm once to communicate it to the debugger。Okay。Okay， and then。诶。Every time。Cluse returns。

Like fix of C returns you。You just say return， right like like a bit or something saying return。

 right？嗯。forever。Returned。For termination of fix of C。Okay， you send like return statement。

Just return。Saying that the call got over。Okay。So it's basically something is what a debugger would see essentially the function calls。

 the fix of C calls and the return statement return， and then what else。

 well let's say the mean we are assumingsuming that the execution goes on for a long long time so after a long time。

 it will just send its current assignment。Like， after。Let's say long time after some。AndN steps。

Actually I use them for a different meaning， so let me say after S steps。S steps。

 let me not say steps after S。After S calls to fix。

After you had too many recursive calls to fix send。Stop and send the current assignment。

His current bullolean assignment is n widths。Okay， so this is all that the debugger receives for every function call he receives the the name of the clause where the function call happen and then whenever a clause returns it says return and then finally after a long number of these fixed C calls。

 it just receives an endbit assignment， which is the current assignment。Okay， okay， so now。Okay。

 the this is all the debu is what I claim that。Like so。诶。So let's go by one step at a time。

 so I claim that the debugger。Like if given the clauses。Cluses on which F C is called。Okay， and。

Final assignment Y。Okay， okay， if I look at the final assignment Y and the clause in which fix is called。

 you can reconstruct。Dbugger can reconstruct X。And every can reconstruct X。

And the initial assignment X。And all the all the。All the re randomdomizing all the clause assignments in the intermediate clause assignments。

Okay， so does it make sense， so why is that？Okay， so basically let me draw。

Let's see what's happening， so you have the endbit assignment。X， right。

 this is your end bit assignment x。Initially， and then what happens is the。

Algorithm starts re randomizing parts of the assignment。 So you know it looks at。

It looks at a clause here。And it reizes it。Okay， and then it looks at a clause here。

 it re randomizes it。And something here red randomize it。Okay and then it does this for a long time。

 and then finally what you have is the assignment of Y。After all this re randomization。

 you have the assignment y。Okay， and you know， the algorithm sent this assignment y to the debugger。

 so debugger has y。And it also knows what sequence of clauses on which you did this re randomization you read C1 first then C2。

 then C3， something， something， right some C10 and then again C1 and then CM CL。Okay， know the order。

 the clause order， suppose you know these two things。

How do you reconstruct the entire sequence of all the bits and even the original x。

 how do you reconstruct it？Well， the idea is just this。Okay， let's look at the law。

 the final clause that the algorithm read randomized C。Okay。

 if you look at the final clause that the algorithm read randomized， well。

 the algorithm only read randomdomizes violated clauses。And therefore。

 before the algorithm re randomize this。This clause is violated。

And there's only one way for a clause to be violated。For a clause to be violated， as we said。

 for the initially， if a clause is to be violated， there's exactly one assignment that will violate the clause。

And therefore， you sort of know the state of the clause before it got randomized。

Okay let me repeat that， that's sort of a critical piece here so if we look at C。

KclL right now it's let's say it's a three sat clause and right now let's say it state is a I don't know。

 101， something， three bits， you can see the state。You know that C was re randomized。

Only because this clause is violated before。Otherwise you wouldn't re randomize。

 which means before it like before it was re randomized， it assignment on that part on this clause。

 the assignment was the unique violating assignment to the clause。

For a three set formula for any particular clause is a unique violated assignment to the clause。

 so it was that so in particular if the clause was x or y or z。Okay。

 then the only violating assignment is 0，0，0。So you know that this clause was at 000 before it got changed to 101。

Okay， and okay， so you've changed that back to 000。

 and then you look at this clause C1 C1 is some other clause here。Okay。

 you know that this clause was a unique violating assignment before。

It got re randomized so you can rewind it it's very easy to rewind this whole thing as long as you know which what is the order in which the clauses were re randomized you can rewind it and get all the random intermediate stages that were there。

 including the first one， the very first assignment。Okay。

 so the debugger can recover the original assignment X。Right so let me write debugger can recover。

The original assignment act。The initial legs。And he can also recover all the intermediate clause assignments because。

You know， youre just rewinding the whole sequence， you know。

 the entire sequence of assignments that was there， so you know all。Cluse。Re randomized assignments。

Cluse assignments。At all the bits， basically this is all the random bits used by the algorithm。Okay。

 so as promised。This if the debugger is able to recover all the random bits that are used by the algorithm。

Okay， that's what happened。Okay。Sorry， one question。

 yes will the debugger be able to recover the very last assignment， the one that fully satisfies it？

So what the algorithm sends the very last assignment Oh thank you okay， so in fact。

 it starts with the very last assignment it starts rewinding it。Yeah， that's a good in fact。

 what we are sort of assuming is that the algorithm failed here as in let's assume that the algorithm ran for a long time like S times S called and then it stopped the algorithm and it sends the current assignment Okay and that's what we decided to do and the debugger is able to recover the entire sequence。

Of these random bits。Okay， so D require everything。 Okay， so now。Okay。

 now let's see how many bits the algorithm sent。Okay， how many bits did the algorithm send？

So actually let me do the accounting here so if it's clear so we maybe with a different color yeah allright and let's let's see how many bits style with them sentence Okay。

 firstly， the final assignment。This is endbits。Because it's just an assignment on nbits。

 the algorithm sent n bits。Okay， okay， now。This thing。You know。

 after every you know some sort of a return statement。

 it's like a constant number of bits every you know like a constant number of bits every time like return happens right let's just say it is。

I don't know， let's say order one bits or 10 bits or whatever。

 basically let's call it order one bits。Let's say 10 bits， two bits， whatever yeah。

What are you just order one bit， basically。So this is order 1 bits per fixed call right order  one bits。

Per fixedcon。Okay， so now the key thing is what about the clauses？All right。

 so the clauses are going to be okay。Okay， how does the algorithm send the name of the class？

All right， so let's。Remember that like there is a in our algorithm， there is an outer loop。

That starts off this fix sub C and then once you once you call fix sub C it'll you know it'll call its neighboring clauses fix of B and so on so basically just to if you draw I to draw a picture you know like there'd be。

Some clauses on which the solved routine calls fix of C。Okay。

 and then this fix of C calls maybe another fix of D。And in all another fix of E。And so on。Okay。

 that's how it looks。Now at the very top level for the fix of C clause here。

We'll just send the name of the clause， so if there are M clauses， it is log M bits。logm bits。

If you just send the name of the clause。We just directly just in the name of the class。Okay， okay。

 now for the every subsequent call。It's wasteful to send the name of the clause because the debugger already knows that D is an clause that is neighboring to see。

That once debu once you call C， the next clause you call will be a neighbor of C。

 so T is a neighbor of C。Okay， so we don't have to send the full name of the clause then we just have to send which neighbor of sea it is。

Okay， so if let's say C has the clause C has， let's say， I don't know how many。Okay， suppose。嗯。

Claw each clause。Each clause has how many neighbors。

 let's just say let me I'm just going to use some number， some name here D neighbors。

 suppose each clause has D neighbors。Cap well efficient USD because we are the USD So this class has our neighbors。

Then I just need to specify which neighbor you went to。

 so therefore I should just use log orbit bits here。Should't use more than log orbits。

 so here for each of these subsequent calls， I will use only log orbits。

So this where critically we are using the fact that our formula is low degree。

 so every clause interacts with。Very few every few of the other clauses。

 so therefore if I tell you one class， then one once you know one clause it's much more easier to tell you the name of a neighboring class。

The first clause is log n bits because I tell you which of the n bits or n clauset is or m clause it is。

But then the next clause is only like one off。A choices like one of 00 choices。

 so just need log 100 bits to tell you which which of the neighbors I went to。Okay。

 so this where crucially we're saving on the encoding。Okay， so okay， that's the critical thing。Okay。

 so let's go back and see how many were using for this。定ing。Okay， so the number of top level calls。

Like the number of top level fixed calls is at most M the number of clauses。Right， so this is。我 yeah。

Let me just say this is actually a number of。Top level calls。Times log game。Plus， number of。

Recursal calls。Times log up。Okay， this is this is the number of bits you use for to tell you the names of all the clauses。

Okay。Okay， and how many top level clause calls are there。

 well we know that like we said the outer loop runs for at most same times。We said that already。

 so therefore the number of top level calls， the number of outer loop executions is at most M。

So this is M。log game。Okay， and the number of recursal calls is what you know is like utmost s or something。

 right？S logar。Actually， I'm being a little bit slopp here， actually I should say S minus M logar。

 but you know it's even， yeah， this is at most。M logm M plus S logger。Okay。

 this is actually S minus M logger。嗯。Because the number of recursal equals a S minus M。Okay。

 so let's count the how like in total how many bits we sent。Okay。

 I think I should do it on the same page。 Okay， I'm going to do it here。 Okay， on， on the first one。

 it is。M log m。Plus， S log R。And the second one。This is the second one is at most like I don't know。

 we said two S。And then the third one， we said n。Enbits。So， in total。We sent。嗯。m log game。Gs。嗯。

I guess。S loggar。Plus，2 S plus n。Okay， that's what we sent。Okay， this is how many bits we sent。啊。就是道。

This is how many bits we send。And how many bits did the algorithm debugger receive？Okay。

 how many bits did that debugger receive or was the debugger able to reconstruct？

Well Dbuer reconstructed the original assignment X。Okay。

 and it reconstructed all the clause assignments on the way it reconstructed all the random bits of the algorithm so debugger reconstructed。

诶。The original assignment X is N bits。Okay， this is a end bits， let me just do it。Yeah。

 the original assignment1 is N bits。Okay， and all the clause assignments。

 so every time a clause is read randomized we got kbits right so debugger reconstructed n plus S times k。

Okay， so you reconstruct deba instrument and n plus S times k。

 So these are the two numbers that are competing with each other is n plus S times k。

 This is the number of bits。嗯，嗯。Of the。This is a number of bits that the debugger reconstructed。

And this is the number of bits that we sent。Okay and you arrive at a contradiction。

As soon as like the number of bits it recons more than the number of bits we sent。

Okay and here in this these two expressions， the key point to remember is everything is the same remains the same S is the only term that keeps growing S is the number of steps okay so n and M and K and R all of those are fixed S keeps growing。

As this like the longer you let this algorithm run， a bigger contradiction you end up with。Okay。

As long as the coefficient of s is you know。Is。Is working for you。So as long as。

Ke is bigger than loggar plus 2。If K is bigger than logar plus2， you have a contradiction。それに。

Okay this。Oh， whatever happened there， Okay， so。So， if。K is bigger than logar plus 2。Then。

For sufficiently larger， like I think for you know let's say S is bigger than m squared。

A contradiction， you have a contradiction。M squared plus n squared， let's say。The contradiction。

This is a debugger three constructs。Outrithm sense。it's a very clever argument。看了吗？

Some sort of very careful， clever counting。Yeah。Any questions on this？

So it just says that your S can't grow too long， you can't have the number of steps be too large。

I said log r plus 2， if k is bigger than log r plus2。Can we work and you can work this out。Well。

 what did we say R was R was the maximum degree of a variable of a clause。Degrreee of a clause。

How many clauses are available？Can be part of sorry。

 how many clauses intersect with a given clause okay？So this is at most the maximum。Dgre。

Of a variable。times。き？Because if a clause has K variables and each of them has a maximum degree。

 whatever degree it has， that times k is the number of clauses which this clause can overlap with。

And you know， okay， we said that our maximum degree， I think in the beginning of this class， we said。

 I guess the theorem， we wanted to prove the maximum degree was set to this number two to the k minus 20 by k。

 so you substitute that， you getta contradict。Okay， just one but I go back， just give me one second。

Sorry about that okay。All right， so we got a contradiction。

 this says that r is like 2 to the k minus 20， and therefore log r is smaller than k。Okay that。

Any questions on this？Yeah， one question， isn't S a randomized variable。

 so does this hold in kind of expectation？Right， okay， so so yeah。

 so I think to do this argument formally we had to say the following， let's say。

That we put in or here， we modify the algorithm to say。

Terminate if you run for more than M squared steps。Termininate。If it's more than m squared calls。

Okay， and then okay， so now we have a situation where this algorithm。诶。Like terminates， right。

 and after M squared times Okay， and then we have situation where。呃。Okay。

 let's say the algorithm terminates a probe。The algorithm fails with probability half let's say the algorithm fails with probability half then we have a situation where you have two parties。

 the algorithm and the debugger and algorithm is able to communicate。A large number of bits。

Using fewer bits with probability a half。And even that is not possible。Next。

So was this under the assumption that Kat， like the assignment， I mean。

 that the the clauses were given are satisfiable。No this is not under the assumptiontion actually it's a good question we didn't assume anything about the formula。

 we said that every every Kat formula with this many clauses is satisfiable。So in fact。

 we arerov a structural statement by this algorithm， we're saying that if you have a caseat formula。

 if it' variable degrees smaller than this， then it is always satisfiable and you can find that using this algorithm。

 find the solution using this algorithm。Oh wow okay thanks and that's what we proved and so yeah we didn't make any assumptions and basically any low degree kat formula low being this two to the K by K formula is always satisfiable is always a solution and you can find a using this。

Okay， and。Any other question？Okay， so let let me。嗯。Okay， let's see where this all fits at。Okay。

 this is very nice so what this is a special case of is what's called the low arch local lemma。

It's quite an impressive statement when you hear it lower lolema， so what is this situation here？

Okay， so probability。Let's say you have a set of events。So you' a set of bad events。E1 through E。

Okay， so bad events over a probability space。Okay， so just to give a concrete example in our concrete example。

 let's say we pick a random assignment。When you pick a random。X。Okay， what are our bad events。

 well bad event is， you know， a close eyes and violated。Cluse C is violated。

So there are M bad events that can happen when you pick a random assignment。

 there are M bad things that can happen， these are the bad events。Okay。

 and we know that the probability of every bad event。Is kind of small。Let we know that。嗯。

So probability of bad event。二。Is smaller than equal to p for all I equal to 1 through M。

So in our example。Like if you give me a random assignment。

 the probability that it violates a clause 1 over two to the K。It probability that x violates。

Some class CI is at most one over。Toth is， in fact， exactly equal to 1 over twoth to decay。Okay。Okay。

 so。So this is quite a like standard situation you have a bunch of bad events and what you want to know is you like in some sense what you want your goal。

Or want to want to show is that。There's some chance that no bad events happen。

What is like you want to know that。No bad event， probably that no bad event happens is at least something。

I is what you want to know and this is same as you want to know if there's a set swing assignment。

All right， and okay， what are the techniques to do this？Okay， first。

 the most simplest technique that you can have in probability is the union bound。Okay。

 heres the here's how union bond goes， you would say， okay， there are M bad events。Okay。

 so E1 through EM。Okay， the probability of the any of them happening。

Probality of the union of all the things， any of them happening is at most。You know， there's some。

I equal to1 through M is the sum of the probabilities。 This is the union bound。And you know， this is。

 like we said， each of them happens with probability P， so p times M。Okay， and then you say， oh。

 therefore， the probability that none of them happen。Is at least one minus p time limit。Okay。

 that's the this is the union bond。Okay， now this union bound is clearly not sufficient because clearly not good enough。

 For example， in our case， we said p was like one over two to the K。 You know。

 let's say you're doing10 set or something。 So P is like one over。2 to the 10。

 like one over1 thousand。 And you have n clauses， right。

 So therefore p times M is basically super large P times M。Its much larger than one。

 so this bond is sort of useless， Union bond is useless。Okay。Okay。

 so what else can you do in probability well the next thing you can hope for is suppose your events are independent。

In independentdepend events， okay that's tricky， but。But let's say if it's true。Okay。

 independentdepend events。If youre independent events， then you know。

 if we want to know the probability that all of them happen。

Like all of like none like intersection of。None of them have like。One another protein。

 none of them happen， basically it's the product of the property that。Each of them don't happily。

Right， and then， you know， okay， you can just say， oh， therefore。This is at least。You know。

 whatever this probability，1 minus p to the M。それ作れるんですよ。Okay， there' are independent events。

 of course， it's easy。Okay， now the question is。Let's say you don't have independent events。

 but you have mostly independence。And you want to capture this idea。

 So if you look at Kssat formula there。Okay， all the clauses are not independent。

 but not all the clause are dependent on each other， for example。

 if I look at two clauses that have no common variable in them， they're independent。

So you want to capture this idea that variable， your events are mostly independent。Okay。

 so you can do that， so let's let me define。Let gamma I。Be的。Neighborhood， neighborhood。Of event I。

Event EI。In that。In that。U。The event EI is independent of everything outside Gamma eye。

EI is independent。Off gamma5bar。Okay， so what I mean is like formally， when I say independent。

 what I mean is if I ask for the probability of EI。It should be the same as the probability of EI。

Even if I told you something about。Any of these events outside the neighborhood。

 so if I tell you anything， for example， I tell you that some subset of them。Are all true。

I tell you some subset of the events outside this neighborhood。Are true。 So you have a E。

EI and its neighborhood and whatever I tell you about events outside the neighborhood。

Whether they're true or false the probability of yeah shouldn't change that's what we mean by independence of course and you can check that this is true in the for clauses as we described if I look at a clause and all the neighboring clause neighboring clauses。

And basically， these are all the clauses that have any variable in common now。

The rest of the clauses don't share any variables with your original clause。So therefore。

 no matter what you assign to the rest of the clauses。

It's not going to affect the probability that this clauses satisfy。So basically。

 there is a sense in which you can look at your bad events here and you can define a neighborhood。

 a small neighborhood for every bad event and say that EI is independent of everything outside the small neighborhood。

几日啊。Okay， so this is the setup for lowest lolemma and the lowest lolema， there one of the。

 I guess the simplest versions of it says。嗯。If the probability of bad event。

EI right towardium body event is smaller than P。Okay。

 and the size of the neighborhood of every event。Gap is smaller than D。Okay。嗯。And。诶你 say。

P times D plus one。嗯。Times E is smaller than one。Here is usually 2。718。对。Then。

The probability that no bad event happens is non zero。So this is true in any probability space。

 basically it's like a general principle just like I guess union bound or inclusion exclusion or all this it it's a law about poverty but you a bunch of bad events or some let's not call them bad there's a bunch of events each one with Pro at most speed。

Each one， depending on at most the other events。Then if p times d is sufficiently small。

 then there's a non zero pro that all of them don't happen。Okay， and in fact。嗯。

Let me get to the bone exactly here。😔，It's D or D plus1 to the M。Just like。It's at least。

D over D plus one。To the end。Yes。Okay， so this is a general statement about probability。

 there's a proof of this statement。Which we won't do today， which we won't do， but。

Like there's a proof of this statement， which is not algorithmic。

Meaning it just proves a statement like a few lines of I mean like a page of manipulation pro。

 it proves that this is true so if you apply it for Kat it tells you that whenever you have a low degree Kat formula there exists a solution to that Kat formula it doesn't tell you how to find it it just tells you that there exists one。

And the beauty of the algorithm that we saw today is that it actually gives you。

Find you a case an assignment。嗯。问で in the数。So it's a constructive proof like when you talk about a proof of a theorem。

Theres a non constructive proof is a proof which proves that something exists without actually giving you a way to find it。

And a constructive proof is something where you prove that something exists by actually giving you a way to find it。

And what we saw today is a constructive proof of this lowest local Emmama in the case of caseat。

 the original proof was non constructive， it just tells you that there exists something。

And this lowest look， this algorithm that I described， you， it's beautiful， it was only discovered。

你嘅事啊。12 years ago， I guess， 12， maybe 13 years ago yeah。

Whereas the lowest local I has existed for a long time。

And it quite often there are many interesting problems for which。

There's a nonconstructive proof that something exists and you know that it exists and you cannot find it and sometimes it's even hard to find it and's lots of examples of this I guess one of the most prominent ones is na Callibria right N equilibriumlibria exists for all the games that you can think of but it's computationally hard to find a na equilibriumria although you can prove that it exists all the time。

And there are many such things where you can prove that something exists。

And yet we don't know an algorithm to find it。嗯。But this is one of the very nice cases where you can find it。

thisす case。ok， so。Yeah， and so so that's a and。That's all I wanted to say about Lo locomlema。Yeah。

 so I guess that wraps up the class so it was。A lot of fun。Lecturing。Of course。

 it would have been way more fun to do it in person， but。Yeah， it is what it is。

But it was a lot of fun teaching the class。There was so much of。Algobuthms are I。

That we didn't cover。A lot of it because I don't know those areas well myself。

But also just because time， but with， for example， we didn't cover any。Real combinatorial algorithms。

Like card， Mintka algorithm or allden。うん。Data structures to compute dynamic algorithms for shortest path and things like that。

 there's a ton of material which we didn't cover and。But诶。

We did cover quite a bit of material too we well we didn't cover a lot we did cover quite a bit and it is quite a lot of challenging material it's really great that you all were。

Hung on the end and able to get through of the quite difficult material that we covered in this class。

嗯。唔大好 about you。You get other opportunities to pursue this。Understand this better。

I think I'll stop here。😔，哦。Thank you， Professor。Thanks。Thank you。Thanks， bunch。Oh， by the way。

 an announcement on Wednesday。Or win' answer， I figured it out to answer。Yeah。

We'll send an email Piazza blast，Yeah。

![](img/89c95edfd59ce96739719d1e17124521_2.png)

我不。