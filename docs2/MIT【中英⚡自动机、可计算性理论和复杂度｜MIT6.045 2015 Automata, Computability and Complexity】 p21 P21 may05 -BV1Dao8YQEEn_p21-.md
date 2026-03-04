# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p21 P21 may05 -BV1Dao8YQEEn_p21-

212，1 two。All right， let's start。Okay， so welcome to。Today's lecture。

Today we're going to be talking about zero knowledge proofs and quantum computing。

Two exciting topics， two interesting applications of all the stuff you've learned so far。

So last time saw we did some more cryptography， we did some public key cryptography。

 and Scott ended with this dating game。And we're going to get back to the dating game a little bit。

In the middle of this lecture。But let me start with zero knowledge proofs。Okay。

 so zero knowledge proofs of this。Almost counterintuitive idea that。

It doesnn't even sound plausible when you first hear it。

The traditional idea for proof is you want to convince me that something is true。You know。

 maybe youve。You have a solution to a sudoku puzzle or maybe you have a proof for one of the problems on the assignment。

 and the way you would convince me is you would write down this proof on a piece of paper and then I would read this proof and then I would go through the proof and'd be like。

 okay this proof checks out and then you've solved the problem。But in doing so。

 you've given me this proof for this piece of paper。

 and one thing I could do for example is I can now convince other people that the problem has a solution by showing them this piece of paper。

 so not only have you convinced me， but you've also given me the means to convince other people that this problem is whatever solvable or that we know a solution to this problem。

Now， what if you could convince someone？About the possibility of something maybe that this Sidoku puzzle has an assignment or that you know the solution to a problem without giving them any additional information like all you want to do is you just want to convince them that something's true。

 you just want to convince someone that，You have a solution to this problem on the assignment。

 but you don't want to tell them the solution， maybe because you're not supposed to share answers on this assignment or whatever or you just don't want to tell them the solution to your sdoco puzzle。

 you just want to convince them of the fact that you know a solution without them knowing anything other than this one bit of information that you know the solution so this is what the idea of zero knowledge proofs is going to capture。

Trying to prove something with us。Giving the other person any more knowledge then。

Then the one thing that you're trying to prove。 I mean， you're trying to prove something。

 So you're going to tell that person something， but you don't want to tell the other person anything more than what you need to。

 So this is kind of weird， but。Let let's start with an example。Like a not computer science example。

 just an everyday life kind of example。So say someone comes up to you and says that。

Coke and Pepsi tastes the same， and another guy says， well， Coke and Pepsi tastes different。

And I don't know how many of you have strong opinions on this。

 but some people feel that Coke Pepsi basically taste the same and some people have really strong opinions on this。

And okay， so let's say， okay， let's say I believe that Coke and Pepsi tastes really different。

Now how can I convince you of this fact， so the traditional proof analogy would be that I get the chemical formulas of Coke and Pepsi now I have no idea how I would do that I to break into Coke's headquarters in Atlanta and steal their stuff and whatever and they would probably kill me and then I would have to go。

 I don't know to a chemistry lab or something and then this guy would have to check that these chemical formulas correspond to Coke and Pepsi respectively and then you'd see these formulas and you'd see that they're different and then you'd be like okay。

 find Coke and Pepsi or do different things。But I mean， this is a really infeasible。And。B。

 I've done a lot more than just tell you Coke and Pepsi are different。 know， for example。

 you've seen the chemical formulas of Coke and Pepsi， these are like trademark secrets and so on。

You've learned more than this just this one bit of information that I wanted to convey。

 which is that co Pepsi tastes different。So instead， we can do the following thing。

 which is a peer sort for zero knowledge protocols， which is what you can do is just。

Just take an empty glass and fill it either with Coke or Pepsi without telling me which one and give it to me and ask me to distinguish whether it's coke or Pepsi。

If I can reliably do this， like we play this game over and over again and I always get this game right。

 so you give me one of coker Pepsi and I don't know which one it is。

 maybe I'm blind forward and maybe youve filled up this glass outside the room， whatever。

 and I'm always able to tell you correctly whether it's coker Pepsi then you're pretty convinced that well coke and Pepsi do taste different。

 well at least to me because I'm able to distinguish them。

So this is the idea of a serial knowledge proof， you see。

 I haven't really told you anything like you haven't learned the chemical formulas of coke or Pepsi。

 you haven't learned anything about cokeine Pepsi other than this one fact that they taste different to me。

😊，And in particular you haven't learned anything that you can go and now show to your friend。

 like you go home and you talk to your roommate and your roommates like well I think Coke and Pepsi tastes the same too and then now there's nothing you can do like you cannot perform the Coke Pepsi taste test I did this with you so it's an interactive protocol that we did together。

And you've been convinced。 And now you have learned nothing more than this one bit information。

 You cannot go home and convince somebody else。 So this is like the。

The least helpful form of proof ever because like all you did is you learned that this is true。

 but you learned nothing more in particular you cannot convince other people that it' is true。

 but it's also like the minimal form of proof this is the least you can do in a proof you can convince the other person that the statement is true without doing anything else so that's what zero knowledge proofs are all about。

😊，And they're interesting because as we'll see。They're going to be really cool for cryptography applications and so on。

 anyway， any questions about this。this example of a Coke and Pepsi。Yes。

 in the sense that this protocol has to be probabilistic yeah if there weren't any probabilities then what you could do is you could just give me the entire transcript of the protocol that we were going to have that you can just the prover the guy was trying to convince me can just be like this is the entire conversation that we are about to have and here's the proof and now you know there's no need for any interaction I mean there's no need for this back and forth and so on so thatsre always probabilistic。

Anyway， yeah， any other questions taking on other proofs？So let me show you a really nice example。😊。

Of a zero knowledge proof。 Now， this isn't a problem that you。

Probably want to have zero knowledge proofs for in your everyday life。

 but we'll get to a more interesting application after this one。

 but this is a great problem to start out with。And this problem is the problem of checking whether two graphs are isomorphic。

So let's start with a graph。Okay嗯。Let's say。Okay， this is a graph and the vertices have labels。

 this is  one， two， three，4。And say this is another graph。Okay。

So these two graphs are said to be isomorphic so what isomorphism means is that know essentially the graphs look the same up to changing the names of all the vertices so in this graph this was called vertex 1。

 this was called2 this cell3 this is called4 here that the names are different but essentially they're the same graph right so that's the property isomorphism they're technically different graphs because if you were to describe both of these graphs maybe by an adjacency matrix or so you would see that vertex 3 here has degree 3 whereas here vertex3 has degree2 so they're not the same graph but they're isomorphic graphs。

So this is the concept of graphite ofmorphism。And this is a really interesting problem that。You see。

Frequently in computer science， and it's called the graph Semorphsome problem and just sometimes you should be related to GI。

It's interesting because。Firstly， so what is the problem more formally you're given two graphs。

 you say the input is two graphs， G and H。And then the question is。Is G isomorphic to H。

 which Ill denote like this with this equals with a little sququiggly thing above it。

 so is G isomorphic to H。So what does that mean， Is there I there a way to relabel all the vertices so that G is now equal to H。

 So is there a way to。Just pere the names of allive vertices so that these two graphs are now equal。

Okay， so I claim this problem is an NP。Can anyone tell me why。

 if you claim that two graphs are isomorphic， how can you convince me that this is indeed the case that these two graphs are isomorphic？

Right， so you provide the isomorphism and what does that mean。

 you just tell me what numbers each of these numbers match with so in this。

 the isomorphism would be let's say one maps to three。Two maps to four。Three maps to one。

And four maps to too。So once you give me this list。

 I can perform these substitutions on this guy and then I can see， well， yep。

 they look the same and this is something we can do in polynomial time because this is a list of size n the number of emergetic is N。

 that's fine that's polynomial， I can do this。 all of this is straightforward to this problems in NP so that's great。

😊，This is an NP。So graph isomorphism is an NP。Well what's interesting about this problem and one of the reasons that people like this problem and I've studied it a lot is the fact that it's in NP。

 but we don't have a polynomial time algorithm for。

Nor do we know that it's NP complete so it's one of these rare problems that's between P and NP complete you know pretty much every problem you've seen in this class well you know if it's an NP it's either NP complete or it's polynomial time and I think the only exception you've seen so far is the factoring problem that we don't know whether that's NP complete or not。

We suspect it's not incomplete。Graphiteymorphism is another example of such a problem。In NP。

 but we don't know a polynomial time algorithm for it。

 Some people believe that it is solluvable in polynomial time some people。

I think that's not the case， Well， anyway， we don't know。Okay。So that's where somemorphism。

What about。The following problem， which I'm going to call a graph non isomorphism， which is just is。

G not isomorphic to H。So same input， I'll give you two graphs。But I'm asking you。

 are they not isomorphic， now， is this problem an N。

 like can you convince me that two graphs are not isomorphic？With the proof of polynomial science。

Does anyone want to take a shot at that or any questions about the problem？

Any ideas for how you were trying to convince me that two graphs are not isomorphic？Yep。で。

That they are isomorphic。That's right， yeah， so I mean yeah， that's right。

 so it has this interesting asymmetry， but if you could provide an isomorphic symbol well。

 then it's clear that the graphs are isomorphic。😊，But now I'm this allpower prover and I'm trying to convince you that the graphs are not isomorphic and it's really not clear what I can do I can be like like seriously。

 believe me， they're not isomorphic and then you're like， well that's not proof I'm like cabra。

 they're not isomorphic， but then you're like no， give me some proof。😊。

And I could list out all possibleomorphisms of this graph， but that's huge， right？😊。

How many ways are there to permute n numbers and that's like n factorial so there's like n factorial different isomorphs into this graph and if I can write them all down。

 but this is going to be an exponential size proof and then that's almost pointless。😊。

You could have just done this yourself。It's not clear to do this in Pnomial time。

 Sometimes you can do it。if I give you two graphs and in one of the graphs。

 there's a vertex that has degree 10 and in the other graph there's no vertex with degree 10。

 then it's clear that there cannot be isomorphism between these two graphs because you know where did the degree 10 vertex get mapped to in the isomorphism。

 but there's no known general procedure for coming up with a short proof of two graphs being not isomorphic。

So what do we do now， problem。knownown to be an NPP。

 so how does someone convince you that do we haveson not isomorphphy and what we're going to do is we're going to come up with a zero knowledge protocol for this。

 which is going to be very similar to this cult versus Pepsi game。All right。Let me。

Let me describe the protocol。 It's actually very straightforward。 So let's say。Let's say okay。

 who am I， let's say I'm the one who needs to be convinced that they're not isomorphic and let's say you're trying to convince me that these two graphs are not isomorphic。

ok。So you believe they're not isomorphic， so what I do is I say， okay。

 I'm going to take one of these two graphs at random。

 I'm not going to tell the prover which one of these two graphs I've chosen。

And I'm going to apply a random permutation of the labels on this graph。

 so maybe I choose this one and then I pere these labels randomly。

 so I choose one of the inial permutations at random and I provide this permated graph to the prover and say。

 which one did I start with？So did I start with this one or did I start with this one if the two graphs are not isomorphic。

 the prover can always figure out which one I started with right because all the graphs isomorphic to this guy are different from all the graphs isomorphic to this guy like these two sets of graphs have no intersection whatsoever so given any one of the graphs that isomorphic at this guy the proveer can tell me100% that this is the graph you started with or this is the graph you started with depending on which one I started with。

😊，On the other hand， if these two graphs are isomorphic。

 then a graph that's randomly chosen to be isomorphic to this guy has exactly equal probability of being isoopmorphic to this guy。

 like the prover has no idea which graph I started with an applied random permutation to。😊。

So in this case， we provide the graphs。😊，Like in this exact case here， but these two are isomorphic。

 if I randomly choose an isomorphicmorphism for one of these guys。

 the distribution in graphs is exactly equal， you know each of the isomorphisms of this graph or this graph is chosen with equal probability and the prove has no idea which one I started with the way I started with this one did I start with that one。

😊，And the prover can add best to win this game with 50% probability。

 and then you just repeat the game over and over again。

 and then you've reduced the prover success probability due to like one over two to 100 or something if you just play the game 100 times。

So that's a zero knowledge proof for graph non isomorphism。Did that make sense？

I know no question yet， great。B and N。Yes I mean do you mean like the person who's trying to figure out he has to solve a hard problem like he has to solve the problem of graph iomorphism that's true yeah so this version of the game we're thinking of the prover as being this allpower entity who can solve pretty much anything Yeah later on we're going to relax that assumption because that's kind of well that's kind of not cool because I was thinking I motivated this with this real life scenario where you know the solution to Sudoku puzzle and you want to convince your friend you don't happen to be an all powerful prover who can solve graph Iomorphism but for this example let's just think of the case where it' just an allpower guy who's trying to convince you the two graphs are are isomorphic。

And so that person in particular can solve graph iymorphosis and that person can solve anything。

And so he gives you this one bit， he just tells you which of the two graphs you started off with and you play this game 100 times if you see he keeps winning then you're pretty convinced that。

YouThey're not isomorphic， any more questions。You just asked the Al。Like as he can travel all。

Right you don't trust the prover so that's the problem so in computational complexity theory we always have this prover and the prover is always a bad guy like there's almost never a case where you trust the prover because if you trust the prover then all computational problems are trivial because you just tell the prover just give me the answer and then there's no interest in computer science you can do from that point on you can just you're always just like well give me the answer it gives you the answer then you write it down to hear them。

😊，Always， whenever we introduce these all powerful provers and if you take advanced complexity theory courses。

 you'll see the provers have interesting names and attributes。

 the most common culprit is a guy called Merlin， he's an all powerful prover who knows a lot of things。

 but he's trying to deceive you。😊，But if you take more courses you might even see Yoda。

 he appears once in a while， he's also an allpower approvalr， he's not trying to deceive you。

 but he's really forgetful and he tells you confusing stuff and there's a bunch of interesting guys。

 but they're never completely trustworthy otherwise the problem kind of gets trivial because it's just like。

 well， he just told me the answer。Right， okay， so does the。Does the protocol make sense just。

So the verifier。He， you know。He picks GRH at random。Then， you know。So this is step one。A play。

Random permutation to the vertices。And then send this to the。Send this to the prover。Okay。

 so this is the protocol the prover has to respond with。G or H。

 the progress has to tell you whether you start with G or H。 so let's analyze this product。Oh。

 this is a little more formally。So what is the completeness of this protocol so completeness is what is the probability that the prover wins in the yes case。

 the graphs really are not isomorphic， so what is the probability that the prover wins this game if the graphs are not isomorphic and the prover of course is all powerful。

So yeah， what are you guessing， what's the probability that the prove wins the case in the yes case？

Anyone。Just。Guess。One， okay， yeah， that's right， so one。

Why is that because if they really are not isomorphic， the prover can always win this game？😊。

If you apply a random permutation。On the vertices of G and apply random permation， the vertices of H。

 So this is G。And this is the set of all graphs。That are isomorphic to G， and this is H。

 and let's say they're not isomorphic to each other。

This is the set of all graphs that are isomorphic to H。 There is no intersection between these two。

 The set of all graphs isomorphic to G are over here。

 the cent of all graphs isomorphic to H are here。They're completely different graphs。

If the prover gets one of the graphs from this set， he's going to say G。

 if he gets one of the graphs from this set， he's going to say H。

 the prover is all powerful so he can eliminateuminate the set。He can check if they're equal。

 it can do whatever he wants，So the prover is always going to win if the two graphs are isomorphic。

 that's good， that's something we usually want from these games， if the prover is telling the truth。

 he should be able to convince you。Ideally with probability one， so that's really nice。

And then the question is what is the soundness of this protocol。

 So the soundness of the second parameter that we usually always check， which is。嗯。

If it's a no instance， that means if GNH are not not isomorphic so that means if they are isomorphic。

 what's the probability that the prover can convince you that they are not isomorphically。

 what's the probability of you getting fooled essentially is always the soundless question。So OK。

 does anyone want to take a stab at that， what's the probability of getting fooled if the graphs are isomorphic？

And what's the probability that you declare that they're not isomorphic？That's right。

 one or two to the n or let's say one or two to the K where k is the number of times you repeat this protocol。

 so if you just run this protocol exactly once， then it's a half because the prover is exactly half probability of guessing whether it was G orH。

You know he can just randomly pick either GRH and say that and with probably half he's correct。

 but he just run this game K times and the prover wins only if he wins all K relations of the game and the probability of that happening is one or two to the K。

 So it's very unlikely that the prover wins， especially if you play this game like100 times or something know one or two to the 100 is。

It's huge， it's more than the number of particles in this universe， so that's good enough usually。

That's a good success problem。Okay， but this protocol has the third and very interesting property of zero knowledge。

And this is why I introduced this protocol。Okay。So as I explained， what is zero knowledge？

So intuitively， what we want to say here is that the verifier。Say I was a awarefaer。

 I played this game with the prover， but I did not learn anything more than the fact that these two graphs are not isoorfic。

I did not learn anything about the graphs， I did not learn something about。呃。I mean。

 any kind of evidence so in this kind of proof system where you try to show the graph isomorphism is an NP。

 the prover is going to provide isomorphism， so he's giving you some information。

 but here I want to argue that you learned absolutely nothing other than this one bit of information that these two graphs are different。

 I mean they're isomorphic or not isomorphic， you learned absolutely nothing else。😊，Okay。

 can someone？Give me an intuitive argument for why this sounds like this is true。

 Like why did you not really learn anything else at all。

 other than the fact that they're not isomorphic。There。Or does that even sound plausible。

 Does anyone have a。Any questions about？Given。Right right right， you're exactly on the right track。

 which is that so this was a great paper like the one that talked about zero knowledge。

 not just because it introduced the concept of zero knowledge。

 but just because how do you even define zero knowledge。

 what does that mean know what does it mean that you learned only this one bit of information and no more？

😊，And the way they made it formal was really nice which is that they said okay so I'm the guy who's playing this game right with this all powerful prover。

 so I have this interaction we play this game for 100 rounds。

 and at the end of the day I'm pretty convinced that the graphs are not isomorphic because the prover has always successfully answered my questions。

😊，And now what I want to say is that。You know me， the verifier after playing this game for 100 rounds。

 I' learned only this one bit of information so what we can do is imagine this guy who's me in the future who has played these00 games。

 100 rounds of this game and iss very convinced that these graphs are not asmorphic。😊。

This guy knows exactly everything that I do。呃。But he knows this one extra bit of information then。

These two graphs are not one more for actually， okay， let me say this again。So this is。

Maybe this is an easy way to think of it，So。This is me。And this is another guy。

Who knows exactly what I know？And he knows that these two graphs are not isomorphic。

So here has my state of knowledge plus。He knows this one fact。

 these two graphs on our writemorphrphy。And。The way I'm going to say that I learned exactly one bit during this protocol is by showing that。

Whatever interactions I had with this prover。 So when I talked to this prover， this is the。

This is the all powerful prover。So I had a bunch of interactions with this guy I asked him questions。

 he gave me answers， I asked him questions， he gave me answers， and so on。

Whatever interactions I had with this prover， instead。

 I could have had the same introduction with this guy。

And this guy would be able to answer all my questions exactly in the same way that the prover would have。

 and I could never tell the difference and how does he do it。

 how does this person who is just me with this one extra bit of information answer all my questions？

😊，呃。So he's me in the sense that he knows exactly what I'm doing。You know。

 when I pick these two graphs of random， I pick one of GRH according to the protocol。

 and I send this over to the prover。If I knew what the answer was。

 if I knew that the graphs are not isomorphic， I know exactly what the prover is going to tell me here。

 I know that the prove is going to give me the correct answer。

 which is whichever one I picked either I pick G or I picked H。

 I know what it is because I picked them， I sent it to the prover and even before the prover sends me a response。

 I can anticipate his response。 I can anticipate it perfectly。

 I know exactly what he's going to send back， he's going to send back the correct answer because these two graphs are not isomorphic。

So having this one extra bit of information that I know for sure that these graphs are not isomorphic allows me to perfectly predict everything that the prove is going to say。

 and if I can perfectly predict everything that the prove is going to say that means he's not giving me new information because I can completely predict everything he says。

😊，And what did I need to do this perfect prediction， I just needed to have。

 this belief this one thing that these two graphs are not isomorphic。So this guys usually in this。

In this field， this guy's called the simulator。Because he simulates the interaction。With the prover。

 And if you perfectly simulate the interaction， then you've learned absolutely nothing more because the only thing the simulator knows more than you is this one extra thing that the graphs on our is amorphic。

😊，So this is how they formalize the notion of zero knowledge。

 They show that you didn't really learn anything because after learning this one thing。

You couldn't learn anything more because this guy can perfectly predict everything that's going to happen in the protocol so the protocol doesn't teach you anything because you could have just simulated this yourself there's no there isn't even a point running this protocol anymore once you know that because。

You know， Howard。How would you learn anything if everything that the prover does is completely predictable by you with 100% certainly。

 provers not giving you any information。Did that make sense at all。

 So this is a counterintuitive notion。 this is zero knowledge and it's not。

It's not something that you would even believe is possible before seeing this。

 but this idea kind of makes sense， this is how we would formally capture the notion of not learning anything。

Anything more than the one thing that you were supposed to learn。

 which is that the graphs are isomorphic。Okay， any questions about this or comments？Yep。after最的。

What what is the knowledge。Right， right。 So after playing the game。

 you learn something because now you have this new ability of。simulating， but。What I'm saying。

 I guess， is that before you started playing the game。Say呃。If you。So before I start playing the game。

 say I make another copy of myself， you know， this person is exactly me and I don't know。

 we cloned me for somehow。And in addition to that， this person。

 we just change one thing in this person's brain and store this fact that these two graphs are not isomorphic。

 like so this person is just completely convinced of the fact that these two graphs are not isomorphic。

 but that's the only extra thing that person knows over me。

And what I'm saying is that this person can completely simulate the behavior of the prover。

Maybe it's more confusing if I introduce a second person。

 let me just say that I can simulate the behavior of the protocol myself。So okay。

 let's say that I really believe that these two graphs are isomorphic and now I start playing this game with the prover so I pick one of these two vertices to one of these two graphs GH at random。

 I apply a random permutation and then I send it to the prover even before the prover response。

 I know exactly what his response is going to be I know that the prover is going to give me the correct answer because I believe that the graphs are isomorphic。

😊，So in a correct execution of the protocol， where the prover gives me the correct answer。

 I know even before the prover has sent me anything， I know exactly what he's going to send me。😊。

And I know this for every single round that we play。 We play 100 rounds of this game。

 And before the prove sends me stuff， I already know what the prove is gonna to send me。

So this is the sense in which I didn't really learn anything because I could completely predict the entire transcript of the protocol that we weren't just about to have even before I started the game。

And the only thing I needed to do this prediction was I needed to have this firm belief that GNH are not isomorphe。

 because if you didn't know that， you wouldn't be able to predict the transcript rate because then。

Well if they were isomorphic， for example， then the prover might just be answering random stuff with 50% probability who would say G orH。

Knowing that they're not isomorphic means that you can exactly predict what the prover is going to say。

😊，So that's。That's the sense in which zero is， that's the sense in which you haven't learned anything other than the fact that DNANH or are perfect。

呃。What are the provers lie， So in this case where you believe that G andH are not isomorphic。I mean。

 the optimal strategy for the prove， I mean， the prover is trying to win this game and when when GH are not isomorphic。

The optimal strategy for the prove is to just give you the right answer at all times。嗯。

So zero knowledge is a property that we define against。 I mean， for the。

 the optimal progress strategy， it's not。A property of provers who deviate from the protocol。

 So the prover is supposed to do this。 He's supposed to give you the right answer。

 If a prover does something else， then。Well， then well then then that's too bad， I guess。

The zero knowledge guarantees only for provers who are following the protocol。

 so what we're saying is that the provers guaranteed to not leak any additional information if he sticks to the script。

 like if we start seeing something different， we start responding with like。

And it starts just giving you more information than like， well， there's nothing really you can do。

Okay， that kind of makes sense， I'll get more questions。This is kind of interesting and confusing。

Thisue and sometimes you might want to think about this later on。Convinnce yoursels that makes sense。

Usually we think of decision problems in computer science that the prove trying to convince you of something yes or no。

 so usually just add one bit， but yeah you could generalize this to the prove trying to convince you something a more complicated then zero knowledge would mean that you've learned nothing more in addition to the bits that you were supposed to learn。

So you could generalize this， I mean this is the most rudimentary version of zero knowledge。嗯。

That's far more complicated versions than youth。If you， yeah。If you're interested。

 there's a very nice survey on Ze knowledgege by Oed Goldroyic， and he goes into a lot of detail。

 explains a whole bunch of interesting things。Yeah， this topic is fascinating and also deep thing。

Complicated。Any other questions about this？Now， okay。Okay。

 so this was the serial knowledge protocol for。Graphal isomorphism。Okay。

 hopefully that made some amount of sense。Let me go back to the thing I said before。

Which is what if you know the solution to a Sudoku puzzle， you know the solution to some。

An assignment problem and you want to convince your friend that you have a solution。

 now you are no longer an all powerful prove to just like a normal person who happens to have a solution to a problem that your friend doesn't have a solution to。

Hey， this happens all the time。Right。So essentially， what I'm saying is for any problem in N。

 any problem of the software way， you know。You could in principle。

 just give your friend a certificate that you have a solution to the problem。

 you can show them the proof， you can show them the Sudoku puzzle filled out。

 but you don't want to do that， you want to do the Ze knowledge thing。

But so what I'm saying is any problem in NP as e knowledge protocol， if we assume certain things。

Pretty mild things I guess， just things like public key cryptography works and so on。

 the stuff we've been assuming the last few lectures I guess the stuff you assume every day when you log on to Amazon and like putting your credit card details you assume that public key cryptography works and that your credit card details are not being compromised so you know it's pretty reasonable stuff you assume this every day。

And so based on this assumption， we're going to show that。

All problems in N have zero knowledge proofs。And so you can start with any NP complete problem。

 you we've seen that all NP problems reduce to NP complete。And peak complete problems。

And the problem we're going to start with， which is going to be nice for this protocol。

 is three coloring。So what's the three coloring problem you're given a graph。

 so it seems like all the problems today are about graphs。So you're given a graph。

And the question is， can you color the vertices with three colors so that no two adjacent vertices have the same color。

 so let's say the color set is always red， green， and blue。So you can color it like this。

 for example， red， green， blue， red。Okay， this is a valid coloring of the graph。

 right every pair of vertices that's adjacent， know there's an edge between have different colors。😊。

Okay， so three coloring it's a well known NP complete problem。You can prove that it's NP complete。

I'm not sure if we did this before。Anyway， so now what I want to do is I want to show you that。

There's a zero knowledge proof for this problem， So what does that mean again。

 let's say I'm the verifier and somewhere theres approver。You know three coloring for this graph。

 so the input is a graph。Everybody knows the graph， and someone claims that， hey。

 I know three coloring for this graph。And they want to convince me that this is the case without revealing the three coloring to me。

Okay， so this is the。This is the game。Okay， how do we do this？

Let me first show you a system that doesn't。doesnn't use any public key cryptography or anything。

 it's actually a real life system that we could it's a game that we could play right now。

 and there's no cryptography involved。What you do is okay you take this graph。You。

Write down a valid three coloring in it。 So since you presumably know three coloring。

 you can write this down。 So you know you write this red green blue。Red。And now what we do is。

Let's say we we cover。We cover this up with a post it note or something。

So I stick a piece of paper on the board right here。So these colors are not visible anymore。

So just think of this as just being a large sheet of paper that I paste on top of these vertices。

I can't see the colors anymore， so the way this would work is。You draw the graph。

 you write so what I'm saying you is I mean the prover draws the graph writes down all the colors and sticks a piece of paper on them and now say I was outside the room whether this was happening I come back in。

 I see this graph but all the colors have been hidden they've been covered with these pieces of paper。

Posted notes， maybe。And what I'm allowed to do is I'm allowed to select any two vertices that are adjacent。

 like so either these two or these two or these two or these two。

 and reveal the colors for those two vertices only。

 so maybe I pick these two and you know I take off this thing。And I see，hu。

 this is a red and I take this guy off and I see， well， this is blue。😊。

And red and blue are different colors， so。This could have been a valid coloring because what I'm supposed to ensure is that two adjacent vertices have different colors。

So I say， okay， well， this could have been a valid coloring。And then we play this game again。

 so I leave the room again， you era this。You write this down write down colors again。

I come back in the room， I get to choose two new vertices， I check whether they're different or not。

😊，If they are， then I say， okay， well， maybe they're different。

 and we keep playing this game over and over again。Okay， let's just analyze。This proof system。

 So right now， it's not even zero knowledge。But。Let's just analyze the completeness and soundness proofs of this proof system。

Okay， completeness。If this graph really does have a three coloring and you really do know three coloring。

 what is the probability that you win this game that we play that is what is the probability that whenever I come into the room and I lift these two things。

 I see two different colors and I say， well， that looks good。😊，sorryrry。100% that's right。

 so the completeness is 100% this is a recurring theme that completeness is usually one because the way we design this protocol is that we have a correct strategy in mind and you want the correct strategy to win the game obviously。

😊，Okay， what is the soundness？What is the probability that？

YouSo let's say I play this game exactly once。 So I just come into the room once lift to labels。

 And if they're both different， I say， okay， yes， we're good。 This graph is。😊，Three colorable。Yeah。

 so what does the soundness in that case and what does soundness mean soundness is what is the probability that I say yes。

 that is I accept， even though the graph was a no input even though the graph was not threecolable。

 I said， yep， for good。What is a soundness probability？

And maybe let me give you a hint this is not a very good protocol like the soundness is very close to one like there's a pretty good chance that I'm going to accept a graph that's not threecolable because just because I might just have picked the two vertices that do indeed have different colors I mean you can have a graph that's not three colorable but pretty much every edge is fine like every edge has two different colors on it but there's only like one lone edge that has two vertices of the same color on it。

There's just one problem at the edge， all the other edges are happy。You。

 doing the right thing and so on， this is the only wrong。This is the only bad edge。

Maybe this guy has two。Two of the same color on it， but all the other vertices are fine。

 So there's a very small chance that you're actually going to find the wrong the bad edge。

 So the soundness of this protocol is quite bad。Can someone tell me what it is？Roughly， maybe。

Just a guess。Yep， good。呃。Right， so if you just run this protocol once。

 it's exactly it's not number of edges， minus-1 divided number of edges， which is like one minus。

One over the number of edges。You know， when I come in。There's， you know。

That number of edges that I could choose from to test you what is the probability that it hit the one bad edge。

 it's just one over the size of the edge set right so this is roughly this is at most one over n squared right there's like n squared ish edges in the worst case。

So。There's only like a one over n squared chance that I catch you。

 I catch the one edge that was the bad one。So the soundness probability is pretty bad。

 like it's pretty close to one。But we have a fix for this， right which is the usual fix。

 How do you fix the soundness probability being really close to one。Just。

Right just repeat the game more time， so let's say you repeat。You to repeat。

Let's say repeated N cube times。And what this is going to do is going to bring the soundness really。

 really close to0。You know。Yeah， less than any constant， probably like one hour end or something。

So this is going to make the game legit。 So basically what it means is we keep playing this game over and over again。

Okay， so the protocol makes sense。 The protocol works if we do this over and over again。

 The problem is it wasn't it was not zero knowledge。 and why wasn't it zero knowledge is because。

Well， every time I come to the room。I learned the colors of two vertices and you know if I play this game n cubed times。

 I've pretty much lifted all the posted notes at some point， some version of this game。

 I mean it's one of the iterations of this game and so I've learned all the colors so that's bad like I don't want to learn the colors the whole point of this xeno and knowledge thing is that you don't learn the coloring All you learn is the fact that there's that the person knows the coloring。

So how do we fix that？And。Tns out it's easy to fix that。 And so what the prover does is just。

Randomize the colors before starting。Which means this is a set with three elements。

 just choose a random permutation of this， so there's three factorial six permutations。

So just randomize the coloring of the graph。 So what do you do， you have a valid coloring。

Pick one of the six possible ways to perate the set of red green blue。

 so maybe red maps to green and maybe green maps to blue and blue maps are red。

Change all the colors to this new coloring scheme。 this will also be a valid three coloring or this is a property of coloring so if you just change the names of all the colors。

 this is still a valid coloring。Do this。Now that you've randomized it。

 let's go back to this protocol over here again。So I come into the room。

 I lift I lift these two things， but what do I see I see two random colors right because you know they were supposed to be say blue and red that was the original coloring that you chose。

 but now that you randomize this this pair blue red has you know equal probability like one over sixth probability of being blue red or like red。

 blue or。😊，You know every possible pair of two different colors。So there's， I mean。

 basically what I'm trying to say is that I don't really learn anything。

 like I don't learn the two particular colors that youve chosen because I see just two different colors。

And there's equal probability of getting。Any two distinct colors。So this is if I play the game once。

 but now we're going to play the game in cube time， so every time I leave the room。

 you need to randomize the colors all over again so to have to have the property that every time I。

Open these posted notes。 I see two random colors again that are completely uncorrelated with everything else that I've seen before。

 So basically， I'm not learning anything because every time I enter the room。

 I know what I'm going to expect to see。 I'm going to expect to see two random colors。So there's no。

 this is the zero No property again that if I knew for sure that this graph was three colorable。

 I can perfectly predict what's going to happen， what's going to happen is with equal probability I'm going to see all possible pairs of two different colors。

😊，Okay。Does that make sense somehow that I don't really learn anything about your chosen coloring because you've randomized it at every trial and because I only get to see two things like if I got to see the whole graph then of course I would learn a valid coloring but we have this rule that I can only come into the room and look at exactly two vertices and those two vertices have to be adjacent so so basically in a valid run of the protocol these two have to be just two different colors and I learn absolutely nothing else。

So that's the sense in which this protocol is cedar knowledge。Yeah， any questions about this？Yeah。

 Ze knowledge is kind of tricky， and it's also fun to go through this whole thing with formal definitions of Ze knowledge。

 but that takes like。😊，A couple of hours or so which we don't have and it's probably too much but we sort of just want to get the intuitive idea across of what the knowledge is it's a really fun concept。

 it's really cute and what's happened here I mean this is a physical game like you know you came to the board。

 you put stuck pieces of paper or posted notes on the board I to leave and so on。

 but we can make this into a proper。😊，A proper computational protocol。

 which can be done even if the the two people are not in the same room， you know。

 they're running this over the internet or so on。 but just does this protocol kind of make sense。

 the real life version of it with。People sticking stuff on the board or whatever。

Any questions about this？No question so far， so the only thing in this protocol that was slightly dodgy to do over the internet is this part about writing colors on vertices and then sticking a piece of paper on it。

 how do you do this on the internet？😊，You know how do you and how do you ensure that the other guy who you send this to only lifts up two of them like that what does that mean right。

 if you're not in the same room， you're not able to enforce all of these things。And okay。

 so that turns out to be not so hard， all you need is。Any kind of public key encryption scheme。

 so let's say。Let's say RSA is one of them， so let's say RSA and let's say。

Ennccrypt and decrypt are the two。These are the encryption and encryption functions for RSA。

 This is the thing that's public。 so everyone knows how to。😊，In cryp， but this is private。

 only the person who generated the RSA key can could do the decryption。So okay。

 so how do we run this game with RSA？Instead of the prover writing down the colors on the blackboard。

So the prove follows exactly the same strategy first the prove randomizes all the colors。

 and then instead of writing them down on a blackboard because we don't have any of this anymore but on the internet。

 maybe I'm in a different country， the prove is in a different country。😊。

The prover encrypts all the colors， so there's n vertices and let's say they're colored with colors C1。

 C2。CN， so C1 C to C N are just。These are just red， green， or blue。And one of those three colors。

 he gives me an encrypted list of all the colors。You can cryy1。He encrypts C，2。And so on。Sian。

And just to avoid the fact that identical colors will have identical encryptions。

 you just add some random string here。Some random string doesn't matter why。

It's just to avoid the thing that if C1 and C2 have the same color。

 we don't want that encryptions to be identical， otherwise the verifier will learn something that these two are the same color。

 so you just act on random string， this is going to give you a random output。

The prover gives me these n encryptions， so this is the analog of the prover giving me these covered sheets。

 this whatever， this blackboard with a piece of paper on it。Now， what do I do？

I get to pick two colors。 I mean， I get to pick two vertices that are adjacent。

 So let's say I pick one and2。 So I pick this guy and this guy。😊，And I asked the prover， hey proveer。

 can you decrypt this for me and the prover can do this。

 the prover is the one who knows how decrypt stuff， this was his private key used。

 so the prover gives me this C1R1 and C2R2。And now I can use the encryption myself to verify that he gave me the right answer。

 because the encryption is public。So I encrypted， check that he gave me the right answer。

 and then I just check if these two colors are different， if the two colors are different。

 Im happy the proveer has won this round of the game。😊，And then we play this game again。

And how do you play the game again， so you scratch all of this？

Prover again randomizes all the colors， sends you a new list of n encryptions。

 again you get to pick two， you send it back to the prove prove decions， you get it back。

 you check if the encryptions he's given you， do indeed match the decryptions he's given you if it's fine and the colors are different you accept and so on。

So basically， I mean， the moral of this is， I mean。

 it wasn't really relevant that we were playing this game。

 The point is that this public key encryption can replace this。

This you know someone writing something on a blackboard and sticking a piece of paper over it and only revealing certain things to you system and this kind of whole thing that I described is often called bit commitment so if you want to learn more about it you can Google this it's called bit commitment。

It's where the prover gets to commit to something in such a way that you don't know what he's committed to unless until you choose to reveal it。

And once he choose to reveal it， he has no ability to change the answers。

And that's something you can do with an encryption scheme。

And so this is how you would do this in real life。Right so now coming back to a real world example。

 maybe you have Sudoku or something， you have a Sudoku puzzle solution。

 you want to convince your friend， what do you do first thing。

 Ma Suuddoku to three coloring right Sudoku is an N， everybody knows that right it's an N。

 There's a witness for a correct Sudoku solution so map it to three coloring this gives you some graph and a valid Sudoku solution will get mapped to a valid three coloring of the graph。

And now you play this game with this person who claims to have a Sudoku puzzle you don't need to use this encryption decryption stuff if you're both in the same room。

 you can just do it this way or do this if you're both at home and playing this over the internet and you play this for n cubed number of times so this is going to get really long and really boring。

 but at the end of the day you will be very certain that your friend knows the solution to a Sudoku puzzle or your friend knows how to break RSA which know arguably is even more interesting than him knowing the solution to Sudoku puzzle so assuming the security of RSA or any reasonable public keyrypto system。

You can implement this protocol over the internet。Or in the real world with this thing。

But you need someone to check that。This person only opens two boxes， if he opens anymore。

 you might learn something more。Okay， yep， so this was。This was zero knowledge proofs。

Of like stuff you would actually want to do as a postergraph on online somorphism and with the prover who's not all powerful as a postergraph online somorphism。

 but the prover is all powerful， these guys are not easy to find in the real world。

 all powerful provers， but these guys just know the solution to one particular problem。

 you find them all the time， anyone can have this。😊。

So C is the color of the first C x is whatever the color of the x vertex。

 there's the color of the first vertex color of the second ver vertex and r is just some random string that prover just appended randomly I mean the reason is only that if two colors are the same if this is red and this is red。

 the encryptions will be exactly the same and then you'll learn something and we don't want that to happen just append some garbage at the end so this is a very common strategy。

😊，Every in cryptography that whenever you encrypt something this probably just a good rule of thumb whenever you encrypt something just put some garbage at the end that's going to have the additional property。

 if you encrypt the same messages again and again they have different looking outputs so if I send the same message to two people I'm like hey I'm having a party tonight at five Do you want to come over and I send the exact same message to two people in this room we don't want the eavesdroper and know that I send the same message to two people because that's also leaking some bit of information but the eavdroper now knows I've said the same message so you just append some garbage at the end like hey。

 you want to come over at five garbage garbage garbage garbage and you want to come in five garbage garbage garbage this garbage is different and so the encryption are going look completely different。

If Robert doesn't know anything。 So this is just a very standard thing to do in cryptography。

 You should always do it if you don I mean， implement something in encryption。A couple of years ago。

 there was an interesting story about some company who didn't forgot to do this in their protocol and then their passwords got hacked and they got into a a whole bunch of trouble。

 lawsuits， lost a million dollars， whatever went bankrupt so on so don't do that always random string at the end of encryption。

This idea is called salting， by the way， if you look at it just called salting， I don't know。

 I have no idea why it's like adding salt to your string， I don't know， doesn't make sense。Anyway。

Okay， yeah， any other questions about this？So this is zero knowledge and one of the nice applications of zero knowledge is you know the dating protocol or the dating protocol the protocol where you wanted to set check whether Alice and Bob both like each other or not that Scott talked about last time this had this one weakness that if either Alice or Bob don't follow the protocol there's no way for you to know it could be that one of them is just like。

Not following the protocol and just trying to learn as much as possible。

What zero knowledge now allows you to do is it allows you to prove to other people that you're following a certain protocol without revealing any of your private information。

 because this is also like an NP problem that telling someone that I'm correctly following the protocol is an instance of an NP problem and so you can convince someone of this without revealing revealing any of your private information just。

😊，In a zero knowledge way。 and this is really useful， even in the real world， like。

 two systems are communicating with each other。 they don't trust each other。

 They want to prove to each other that they're following the protocol correctly。

 You could convert convert this NP problem and make it have this property that you have resilience against cheating。

😊，Cheating parties， but I won't go into details for this。 It's interesting to think about。 So I mean。

 once you I mean， you've just seen zero knowledge， maybe you haven't got hang of it if you think about zero knowledge more and once you you know totally feel like you understand it。

Try to revisit the dating protocol and see if you can make it resilient to cheating Alices and Bobs。

Yeah， and if that doesn't help， it's in the lecture notes， it's explain how to do this。

 So if you look it up online， you can see how you can。Guard yourself from。Caters， I guess yeah。

 so you can make everyone prove everything they do without them revealing anything。

 So that's pretty nice。It's great for this cynical world we live in。

 any questions about zero knowledge or should I move on to quantum computing？Nope， no questions。

 okay， quantum computing， okay。Okay， awesome。Yeah， today you're getting all the good stuff。

 all the exciting stuff in this course， quantum computings， E knowledge， yeah。Yeah。

 Scott's going to be sad he didn't give this lecture。Anyway， okay， what is quantum computing？Yeah。

 yeah， question。啊。So I mean， I guess abstractly you can use this in any kind of situation where a bunch of people don't trust each other。

 so that's the abstract version of this， and you want all of them to follow a certain protocol。

 but everybody else might be a jerk and not following the protocol。U。I can give you some。

A couple of real life examples。 There is something called the millionaire's problem， which is。

It's kind of cute， which is like so two millionaires meet at a party。

 and they want to decide which one of them is richer。Okay。

 and they want to do this in a zero knowledge way because obviously none of them want to reveal how much wealth they have to the other guy because I mean。

 one way to do this， of course， you tell me your bank account balance and I' my bank account balance and we just compare which one's bigger。

 But now you've revealed a lot of information。 They don't want to do this。 They're millionaires。

 They're secretive。So there is a way to do this in a zero knowledge way。

So that at the end of the day， both of them learn exactly one bit， which is which one has more money。

 and none of them learn anything more than that。So this would be。You know， yeah。

 this would be the solution to the millionaiaires problem using a zero knowledge protocol。

 So this this whole area of a whole bunch of people getting together and computing stuff without trusting each other and without revealing information it's called multipart。

😊，Multippartly secure computation， yeah， that's right。

So this is also useful if a bunch of parties want to come together and do something like。You know。

 compute something together， a property that's property of all of their inputs。

 you know like maybe five people come together and they want to compute the sum of all their bank balances。

 but no one person， I mean no one should know anybody else's bank balance except everyone at the end should know the sum of everyone's bank balance for some reason maybe the five of them are pitching together or just start a startup or something and they need to know whether they have more than the million dollars so this is something you can do using again the ideas here for public key cryptography。

Any more questions？Yeah， this is really fascinating。

 You can do a whole bunch of stuff that you would have never thought possible， just by using。

Public key crypto and these ideas from zero knowledge。 A bunch of people get together。

Computerute stuff without anyone knowing anything。Yeah， it's fascinating。Yeah， also things like。

 yeah， say you rent out a supercomputer and you want to do some computation。So what would you do。

 you take this computation， you give it to the supercomputer， say， hey。

 can you do this computation for me， the supercomputer sends you back the answer。

 but now the supercomputer knows what you were trying to do right like for example。

 you're trying to break into someone's crypto system。

 you're trying to hack bankss passwords or something。

 The supercomputer knows what you're trying to do and you don't want this property you want to give this guy a task to do without the guy finding out anything about what you're trying to do and give you back the solution So this is also something is possible This is called blind computation also fascinating。

 you can make other people do all your work for you without them finding out absolutely anything about your work。

Yeah， cryptography is really。Fascinating and has like a whole bunch of non intuitivetuitive things。

And yeah， I would encourage you to take a crypto course at some point if you have the opportunity to do like a whole bunch of really great cryptographers work here at MIT。

 like some of the people who invented this stuff， this protocol was invented by let's see Grech。

 McColey and Victorson and MiCley is here， Sylvia MiCley is a prophet here RSA was also invented back up some of them were here when they were working on this I guess R was here and S and A were not already Yeah anyway a a lot of the cool stuff you've seen here in cryptography was invented at MIT so you get a chance to take crypto course here with one of the greats。

Probably do that。Okay， any other questions？Before we move on to quantum computing。

 another great topic。Where a lot of good work has been done also by people at MIT。Okay。

 let's move on to quantum computing。All right， okay， what is quantum computing？Okay， okay。

 so how many of you have heard of quantum computing before？Okay。

 everyone because you're not living under the rock， okay， fine， but okay。

 how many of you know what quantum computing is，Right， okay， good， good。So yeah。

It's my privilege to introduce you to quantum computing。' an awesome topic。 as you can tell。

 it's clear from my bias。 I work in quantum computing。Yeah， I love quantum computing。

What is quantum computing， So let's start with。Okay， let's start with polynomial time machines。

 know we studied P， the complexity class of。Things you can do with polynomial time on a deterministic clear machine。

And we think of this as model for efficient computation。

 you we also talked about this church duringing thesis that says that basically whatever you can compute efficiently it can be computed efficiently on a polynomial time。

Terministic tut machine。Okay， that was great。Aypothesis， and then later in the course。

 we saw this other complexity class BPP， which where you had access to randomness。

And then the class of problem solved in BPPP is。As far as we know probably a little bigger than the class of problems in P。

 I mean， it could be equal， but it could also be bigger。

 And you there are examples of problems that we know how to solve in BPP。

I guess we did one example of this circuit non zero testing problem or whatever。

That you can solve if you have randomness， but otherwise it's not too hard to do this in polynomial time。

 Now imagine you have two guys who are debating whether you know which one is the correct model of efficient。

 feasible computation， you know what should we adopt as our definition of efficient computation。

 So this guy， the guy who's you know。Supporting P， he says that。

 well you know where is this randomness coming from。

 you know a universe doesn't just have randomness from the sky。

 like know the universe follows a set of rules， you Newton's laws and stuff like we studied in high school。

 f equals MA and so on， there's no randomness in that。So there's no randomness in the universe。

 you shouldn't be having this。Extra resource of randomness。 Where would you get it from。

 And then the other guy says that， no， while the universe really does have randomness， know。

 you could just measure something like you know there like photons coming from the sun and you can measure their polarity or something。

 that gives you a random number。And which one of them is right and which one do you want to support。

 And this really kind of depends on what you believe about the laws of physics。

 right like do you believe that the universe gives you a free source of random numbers or not。

And depending on what you believe about this question， you might fall into one of these two camps。

 like if you believe that the world is deterriministic， follows Newton's law and so on。You say， well。

 no， there's no randomness。 like this is just an artifact of some。

 it's just some kind of pseudo random generator that you're running。

You should be able to completely model it as a pseudo random generator。

 whereas the other guy says no the universe is just inherently random。

 you can just get randomness from stuff by measuring things。

 measuring electron positions or like counters of nuclear stuff and that just gives you random numbers and you should be able to use this。

 this is a resource and if it can help you do computation。

 why shouldn't we include this in our model of computation？So anyways。

 what I'm trying to get at is today。Sometimes the laws of physics are pertinent to what you believe to be the best model of computation。

 like you don't want to not exploit a resource that's available in the real world， like if you know。

 if your processor has the ability to do，You get random numbers， then why would you not exploit that。

 know it's like you're just st your hand behind your back for no reason。So yeah。

 maybe another way of explaining it is。Okay， let's talk about a completely hypothetical scenario where someone noticed that。

If you， so you know， the traveling salesman problem。

 this is the problem where you're given a graph and you want to find the shortest path between all the。

Vertices of the graph so that you visit all the vertices once。

 but you want to travel the least amount of distance。

 This is a problem we solved every day by you know。FedEx and DHL and USB and so on。

 they want to deliver packages and they want to minimize。The amount of driving time or whatever。Okay。

 maybe someone notices that if you take the graph you have。

 put it on the table and at all the vertices， you put sugar crystals， I don't know。

And you put an ant on the starting vertex， and someone notices that the ant always seems to take the optimal path。

 Okay， say this was something that Angt did。 like anngt always found the shortest path to traveling salesman problems。

So the first thing you would do you'd like well， this is weird and then you'd run a whole bunch of experiments。

 you'd done it on larger and larger graphs and then after a while you get pretty convinced。

 okay yeah actually really doing this So now there's two things you can do first you can try to understand how ants do this。

 you know try to understand how their brain works and like what they're doing。

 but let's say this is the ant brain is just impervious to our attempts of understanding them you our biologists are just clue this and like we have no idea how ant brains work not what do you do。

😊，This is something that's happening right so we have the ability to solve traveling salesmen problems in the real world。

 you just use these anngs， but we don't know how to simulate this on our deterministic machines like you know your processor at home doesn't have the ability to do this。

 so what do you do now？And I don't know what you guys are thinking about what I'm thinking is that Intel is going to release a new processor that has a little ant form inside it that in addition to doing whatever it does。

 whenever there's an NP complete problem it just releggateates it to the an form and that thing solves it and then it gets the answer back right if you have the ability to solve NP complete problems in the real world。

😊，You wouldn't just be like no well， I'm going to stick with the deterministic tuuring machines because that's my model of computation and this and stuff I don't really understand it。

 now you just you know just exploit that resource， you know like everybody's going to have their own bunch of pet ants solving their MP complete problems for them so this is really what's happening with quantum computing is that。

😊，There's something mysterious happening in the real world that we don't know how to simulate with our deterterministic tearing machines。

 so more precisely。You know if I give you a problem like。嗯。

I guess many of you probably took chemistry in high school。

 I don't know if you do chemistry in high school。😊。

There was like this whole bunch of stuff about you know these electrons going around protons and neutrons and they went in these weird orbitals and stuff。

 so all of this this was governed by the laws of quantum physics there's no way to explain this using classical physics that you probably study in high school。

So if I give you a system like this， I give you a bunch of protons and electrons and ask you what happens to the system after a few minutes。

 like can you predict the behavior of these systems？

The the laws of quantum physics tell you exactly what's going to happen。

 but this is not something we know how to simulate in polynomial time。

 so there's no known polynomial time algorithm know deterministic or randomized that correctly predicts the output of quantum systems unlike classical systems like if I give you a bunch of planets in space and I tell you all the locations and so on and the velocities and then I ask you what's going to happen after a few minutes you can predict this to pretty good accuracy。

In polynomial time， but with quantum systems you know I give you a bunch of hydrogen atoms and stuff and ask you what's going to happen if I give you a couple of molecules you know chemists care about these things a lot。

 know if you have a couple of molecules close together at what point do these molecules react with each other when does this acid and base come together to form something and these are the kinds of questions if quantum physics answers in principle in the sense that there's a solution you solve this Schchrodinger equation that the s Schdinger came up with but this is not something we know how to do in polynomial time unfortunately。

😊，And。In fact， a lot of the world's computing resources today are spent in doing exactly this。

 so people from chemistry， biology， material science。

 physics especially would love to simulate small scale quantum systems to see what happens when certain things react with each other。

 certain things get close to each other but they're not able to do this because we have no efficient classical algorithm for simulating quantum systems so when I say classical I mean not quantum in the sense of either deterministic or randomized。

We have no classical algorithm for simulating quantum systems。

 This is something we spend a lot of money and effort on every day。

But this is like the endform situation all over again。

 There is a way to simulate these quantum systems， which is the systems themselves are doing this。

 right， You can just put a bunch of electrons and hydrogen atoms in a little box together。

 and they will simulate their own behavior。 This is something that's happening in nature。

 Nature is able to solve this problem that we don't have the solution to。

 We don't know how to simulate the behavior or quantum systems in problemial time， But nature can。

 So why don't we use this as a resource。 Why don't we add a little。You know。

 quantum system simulator， subroot， little box on our Intel microprocesors。 It just does this。

 this part of it。 just the quantum simulation part。 it's some problem we don't know how to solve。

 And if you。Add the additional power of solving that problem。

 You've just gotten the ability to solve a strictly larger set of problems。

 So you should just add this ability。 And that's basically the motivation for quantum computing。

 which is that。Quantum mechanics is doing something weird。

And then there's two ways to think about this。 One is it's doing something weird。

 We don't know how to simulate it。 and then you just give up and you're just like， well。

 now we't know how to simulate it。 let's just use our exponential time algorithms to simulate this and declare defeat。

But then there's the lemons into lemonade kind of attitude。

 which is like if it's doing something we don't know how to do， let's exploit that。

 let's make it do stuff for us and that's the whole theme of quantum computing What we're going to do is we're going to take this hard problem that we don't know how to solve and we're going to make it solve problems for us。

And that's really how Richard Feynman came up with the idea of quantum computing。

 He was talking about this， he was like， why can't we solve this stuff on computers like what are you computer scientists doing and computer scientists were like。

 well this is really hard， we don't know how to simulate quantum systems and then he was like。

 okay let's do this okay new idea， let's use quantum computers let's make computers that have quantum this inherent in them so they can they can do this and they can probably do more things you know like。

😊，I mean， it's not clear what additional power you get from the power disim quantum systems。

 like maybe just having this extra power of predicting the behavior of electrons and so on allows you to factor numbers in polynomial time。

 that sounds crazy， doesn't it。Yeah， well， it turns out to be true。

 so quantum computers can factor numbers in polynomial time which was。

hich is one of the strongest assumptions we made all through。

Everything we discussed in the last couple of weeks， we assumed that it was hard to factor numbers。

 but if you have a quantum computer， which we don't have right now， but if you had one。

A fully functioning one。 We would be able to factor numbers in polynomial then。

So that's pretty remarkable， just the ability to simulate these electrons moving around or whatever atoms。

 know chemistry stuff moving around。Gives you the ability to factor numbers， right？

And maybe you can do more stuff， it's not clear， like there's something that you're not able to do。

 and once you add this additional power， you don't know what can happen。

 like these two things can interact and give you more things。

And that's exactly why we study quantum computing。Because it's an interesting extraability that we can add to our computers。

 it can do something more， it can at least simulate physical systems。

 that's the very least it can do， but it can also do other things and one of the great things it can do is factor numbers in polynomial time which is also discovered by somewhere here at MIT who's Peter Sho。

 he's in the App math department。So yeah， so that's the reason why we study quantum computing。Okay。

 that's the end of my。Philosophical introduction to quantum computing and why you should care and why it's totally awesome。

 Okay， Any questions about this or comments。Only。Comments about why you think it's not totally awesome。

No， okay， everyone is totally in agreement， that's great。

It's clearly the best thing since sliced bread。O。Okay， so you guys are going to learn。

Quantum computing today， or at least。Very basic stuff。About quantum computing。All right。

Let me just describe the quantum model to you， so I'm going to describe it in the way that I'm just going to tell you。

How this stuff works。I mean， just what is the mathematical description of quantum computing。

 how it works？Far more complicated and maybe you need to understand physics and so on。

 but we can take all the physics out of it and just make it like a math thing。

And that's nice because the physics is really complicated。Okay。

 so so let's start with deterministic stuff。So this is always the easiest place to start and always the place where not too much interesting stuff is going on。

 you have a bit which I'm going to think of drawing by a wire and a bit is either zero。Or one。

And then maybe you apply a gate to it， maybe you apply a not gate。

This is a knot gate tonerrdle like this and the01， the 0 gets flipped to a1 and。😊。

One gets flipped to a0。That's what a Nge does。嗯。Yeah that's really not that much interesting to say about deteristic computation other than you know bits or bits。

3 either 0 or 1， you can do stuff with them Okay， it's not that interesting let me go on to probabilistic。

😊，Computation， okay， so now I have a bit but。Let's say I don't know what this bit is。

 This bit was generated by some probabilistic distribution。 So some guy。

Fpped a coin and then the coin came up Hes。 he stored the value of zero in this bit。

 so maybe the probability of hedges was。呃， sayP。And if it came tails。

 then he stored a one as sayss one with probability。1 minus p。So this is a bit you haven't。

You don't know the value of this bit， like maybe you haven't measured it。

We haven't talked about how the bit is implemented。

 but maybe it's like a wire in some circuit and whatever one is like5 volts and 0 is 0 volts or whatever。

 it doesn't matter how it's implemented。That's the engineer's problem。

But it's a probabilistic bit in the sense that you don't know which what it is。

 it's0 with probability P， and it's one with probability 1 minus P。So。

One way to represent this is the following representation where you just take a vector of two elements and you like p and 1 minus P。

So this is a。Probability of zero， and this is the probability of。1。

So this is one way of talking about a random bit that you don't know the value of， you just say。

 what is the probability of 0 and what is the probability of one？

Does that make sense as a way of describing random bits。

 you just tell me the probability that the bit is a zero or the probability that the bit is1。

That's good。Okay， how do we？How do we represent the bit that comes out of a fair coin？

It's a fair two side coin， you flip it。What would we write here in this vector to represent？

A half and a half， perfect。And why is that， you know， fairco has probably half of coming heads。

 half coming tails。 let's say head is one and tails is0 or whatever。

This is how you represent the a bit that's the output of a fair coin。

 this is how you represent a general bit。😊，Okay， well。

 this is all pretty straightforward stuff right now what happens when you apply a knock gate？

To a probabilistic bit。 So you have this bit， which is either P or 1 minus P。 you apply a not k。

What do you get here？When you play not get to P1 minus p。Yeah。

 perfect so that should be 1 minus p on the top and P at the bottom Why is that so it's0 with probability P you apply to node gates and now it's one with probability P。

 same thing with the one guy。It's now zero probably1 niceB， right？Okay， yeah。

It's pretty straightforward stuff。 I'm just reformulating。

Classical stuff in a way that it's going to make it better for quantum computing later on。So。So。

Now that I've written stuff as vectors， let me keep this up here so you can see this。But。

I said p1 minus p gets mapped to。1 minus p with this not gate， right？

So now since we're thinking about rectors， we're going to think about gates as matrices。😊。

A bit passing through a gate is going to be the matrix vector product of these stitch。

 so I'm going to have a gate here。This is a matrix， and this represents the not gate。

So what matrix should I put here so that when I multipied with P1 minus P， I get 1 minus P。

That's right，0，1，1，0。Someone's been doing a lot of linear algebra recently。Right。

 so this is the matrix you need to put here so that if you multiply these two guys out。

 you get there。😊，So this matrix exactly represents the behavior of the knot gate。😊，Okay。

 so now we have this new formulaism where we think about bits as being vectors。😊。

Gates is being matrices。Okay， let's see another example， what about this gate。

 I'm going to call it the coin flip gate。😊，And what it does is。Whatever your input is。

 it replaces it by a coin flip。You knowEssentially， it doesn't really look at your input at all。

 it just says， yeah， yeah， whatever your input is， it flips a coin and outputs it under bit。

These are the kinds of gates that you might want to use in a randomized algorithm to start up with to get your randomness。

 in the beginning of the algorithm you want to get a bunch of random bits。

 you might just want to feed zeros into this， use a bunch of coin flip gates and now you have a random bit to use as you please。

 so this is a valid gate。So the question is what is the gap so that again， if you have p1 minus p？

You get。So what should I fill in here， this will be a representation of the coin fliplip gate。Okay。

 that's good， half， half， half， half。O， this might not be obvious， but if you just do the math。

 you'll see that this entry over here is half times p plus half times one minus speed that's half and same thing for the bottom row。

This gate represents coin flips。Okay， so now we have this。Yeah， this new perspective of things where。

Let me。Where we have the bit being represented by。A vector。So。So bit is a vector like this。

 let me call it P0 P1。Satisfying the following properties。These are positive。And they sum up to one。

Right。That's what a bit is。Okay， then the question is。

 what are the allowed operations you can do on it？We saw two examples of operations。

 one is the knot gate， the other is this coin flip gate。What more can you do on it？

Read the the most that you could ever do on this is the set of all matrices that。

That preserve probability vectors and the set of all matrices that map。

Stepates like this to states like this， because you still want to output a added probability distribution。

 so you want to。So the set of operations you can think of as just you know。Marices that。You know。

 that。That map。You know， valid states to valid states。So。What is a valid state。

 a valid state is a vector like this where the two entries are positive and they sum up to one。

And we want to think of all possible matrices that do this。 Fortunatelyly。

 there's a nice characterization of these things they are called stochastic matrices。😊。

And you can prove an interesting characterization of them。😊。

Which is that a matrix is stochastic if all of its entries are positive。

 and if the sum of all the numbers in each column is one， so it's a matrix like this。And if you take。

You have some entries here， if you sum up all of these guys， you get a one。

So if you add all these guys up and they should hold for every single column。

So if a matrix has this property， then it has the property that it maps probability vectors to probability vectors and vice versa。

 any matrix that maps probability vectors to probability vectors has to have this form has to be a matrix that's positive entries and so on。

Okay， that's great。So we've talked about how to so this is a random bit， so these are our stakes。😊。

These are the valid operations， and the last thing I want to say is what I'm going to call a measurement。

😊，Which is just。What happens when you finally look at a bit。

 So so far we're thinking of these bits as being unknowns。 and at the end of the day。

 maybe you want to look at the bit， you want to go there and just be like， hey。

 what's the value of a bit？So if you measure piece it up。P1， what happens？

You see zero with probability。P0， and you see one with probability。P1， right， this was almost。

This was the reason why we' these vectors like this， that's what this means。

So now this completely describes。randomandomized computation。

 the valid states are probability vectors。 The valid operations are things that map probability vectors to probability vectors。

 And at the end of the day， you look at look at it a bit。

And what bit do you see you see the bit 0 with probability D P0， you see the bit 1 with probability1。

So this is a description of randomized computation， okay， any questions about this？

And so one way to think about this also is you might say that the one norm of this vector is one。

For those of you who've seen vector norms， that's the vector one norm。

 which just basically means add up the absolute values of all the entries in the vector。

 and these matrices are matrices that preserve one norm。

 they map states of a certain one norm to states of another of the same one norm。Okay。

 that's classical computation。😊，And now we can talk about quantum computation。

So all we need to do is generalize those three concepts， what is a state， what is a valid operation。

 and what is a measurement。Okay， so that's not it's not too hard。

 And turns out all you need to do is change one thing， which is。

A state is now instead of having the one norm B1， we just want the two norm to be1。

So now state is two numbers alpha and beta。And the properties are their two norm is one， which is。

Plus's beta squares 1。So this is the two norm of a vector where you take every entry， square it。

 take the absolute value squared， and I guess I forgot to mention this。

 but alpha made a out of complex numbers。And this makes seem kind of weird that there are complex numbers。

 but you really need this in quantum。So this is how。

We describe states in quantum computing and now this is going to be called a quantum bit。

 which is usually shortened to qubit。So a qubit is a vector， a two entry vector。

 two entries are complex numbers， such that the absolute value squared is 1。

That's all a quantum bit is。Okay， that was pretty straightforward， right？Okay， that's good。Let me。

So that's what a quantum bit is。And let me just introduce some notation that people like to use in this field to make life more convenient。

Which is。So okay， if you have a vector like this， alpha beta。You can certainly write it like this。

 right， alpha 10 plus。Beta 0，1。Of course， you can always write vectors like this。

When you add up these two vectors， you get this guy。

So something that people in quantum computing like to do is give names to these two vectors。

 and this vector is usually called kD0 denoted like this and this vector is called，😊。

Kt one denoted like this， so you would like this as。Alpha Cat 0。Data kit1， and this object is called。

Kt zero。 now you're wondering who in the world came up with this， what does that even mean？

ItDoesn't mean anything right now， but later on。You're going to see something that's related to a cat called a bra。

 and when you put them together， you get a bracket and that's how。They came up with this name here。

 I was a guy called Dak who invented quantum， a lot of the mathematical formulation of quantum mechanics came up with this word。

 and now we're stuck with it。 So this is just another way of representing。😊，This thing。

 it's just shorthand notation because it's much easier to write this or later on you'll see it's easier to write these things than drawing vertical vectors also takes up more space on a piece of paper to draw vertical vectors all the time this is easier。

Okay， so that's what a quantum state， and that's all a quantum status。Just a two dimensional vector。

And then we give names to other special states。One of the states we like a lot is this state that we call the plus state。

 which we do not't like this with a plus。And this is one over square root of to0。

This one was split if you one。Right，This is a valid state because the entries are one over square root of two plus and one over square root of two you squared summons。

