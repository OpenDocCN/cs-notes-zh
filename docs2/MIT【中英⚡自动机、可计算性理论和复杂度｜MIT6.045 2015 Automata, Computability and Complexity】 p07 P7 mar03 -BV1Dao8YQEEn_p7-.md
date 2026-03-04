# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p07 P7 mar03 -BV1Dao8YQEEn_p7-

Can people hear me is the mic on？All right， let's start。So。Right， my names Robin， as Scott mentioned。

 I'm going to be lecturing a couple more times in this course。嗯。All right， so let's see， okay。

 what did you guys see last time？Last time Scott talked about。University of tuuring machines。

 he talked about the halt problem， we showed that the holding problem is undecidable。

Which means there's no algorithm to solve the halting problem。

 there's no algorithm that decides whether an arbitrary program halts or not。And。

We talked about cardinalities of sets， so we talked about sets and sizes of sets。

 especially infinite sets， and how you can have。Two sets that are both infinite。

 but of different sizes。So maybe let's just start with a quick recap of this last part of our sets。

And sizes of sets。Okay so。So we essentially talked about two different sizes of sets。

The first was the size of the set of natural numbers， which。Is usually denoted。I left zero。

So an example of this set is the natural numbers。We also talked about how。N squared。

 which is just pairs of natural numberss， also has the same cardinality， for example。嗯。Similarly。

The set of rational numbers has the same cardinality。And the other cardinity we talked about was。

Two to the LF0， and this was the cardinality of the real numbers。And。Importantly for us。

 this was the cardinality of the set of all languages。And。

So this was one way of showing that there exist problems that cannot be solved by any algorithm because。

The set of all problems or the set of all languages is of this cardinality。

 whereas the set of all algorithms or the set of alteruring machines is of this cardinality。

As we know from Can's Theorem， these two are not the same。

 this one is strictly smaller than that one and hence there has to be some problem here that's not solvable by。

An algorithm。So right， so let me just write that down。Could it be important？Sa of all。2。

Turing machines。Okay。Right。And because the set of altering machines has thisinity。

The set of decidable。Is also here， for example。The set of recidable languages。Okay。Okay。

 so this is just a recap of what you guys did last time， any questions about this？

Why things are in these sets。Okay， everyone remembers what it means for two sets to have the same size。

 it means there's a bijection between them。Okay。And yeah， so this is really。

Nice definition of cardinality。And I guess it was not obvious back in the day when Cantor was working on these things。

 how you would define the sizes of infinite checks and how you could have different setss that are all infinite。

 but still have different sizes and so on。It's a nice notion， and you can try to prove for yourself。

 for example， that r squared is also here， so points in a plane， pairs of real numbers is here。

And similarly， you， just did。Part of the K is also of this cardinality。

And here you have the natural numbers and squared， but also。Enter the cases over here as well。Yeah。

 you can just try a couple of sets。See which where they fall。

 they may not even fall in any of these two cardinalities。

 but usually most of the infinite sets you come up with should be in one of these two cardinalities。

Okay。All right， let's move on to something new unless there are any questions about this material。No。

 good。Okay， so let's start with。Curing recognizability。Turing recognizable languages。All right。

So last time we。We saw the definition of her。A decidable language。And a decciable language is one。

For which there exists the turing machine M so that if x is in the language。

 the turing machine will halt and accept， and if x is not in the language。

 the Tring machine will halt and reject。We say that this steering machine decides the language。

And now I'm going to talk about a slightly different notion， which is called touring recognizability。

 And for this， we say that。嗯。So it's the same thing that needs to be a tuuring machine M so there should。

Existed during machine M， such there。So for all x in the language。We wanted that。

M halts and accepts M。Htson accepts X。But that's it， there's no other conditioning。

So this is different from。What we saw last time， which was decciable languages。Right， okay。

Is that clear or yeah？No， yeah。 that's a good question。 So that's right。

 So this means the definition is incomplete So for。I guess we should say。

Let me spell out the two possibilities， which is。And can。哇。It can halt and reject。Or。诶。

Or loop forever。let us get stuck into an infinite loop。so that's a good question。

 so the difference between recognizable languages and decidable languages is this part over here。

 the loop forever part， so for decidable languages you wanted that when x is in the language M halts and accepts。

 when x is not in the language， M halts and rejects。😊，So。

In recognizable languages we are also allowing it to loop forever。

 so all we're saying is if x is in the language you need to halt and tell me that x is in the language。

 if x is not in the language you can do any of the other things but of course it shouldn't halt and still tell you that X is in the language because it's not。

😊，Okay， yeah， any more questions about this definition？What it is for。

 what it means for a language to be recognizable。All right， so。Let's see。Okay。

 let's go back to the halting problem， for example。That we saw last time。

And I guess Scott mentioned there's two different versions of the halting problem that you can both refer to as a halting problem。

So let me call this one the halting problem。You're given the description of a Turing machine and an input X。

And you're asked。Whether M halts on this input。Right okay， so this is the holding problem， let's say。

And what we showed last time was that this problem is undecidable， which means there's no。

There's no tearing machine that decides it。Which means， as we discussed。

 there's no tiing machine that can take this input and halt on all inputs in the language and reject all inputs that are not in the language。

Right。All right， but I claim that。Even though halt is not a decable language。

 it's still a recognizable language， it's still possible to come up with this kind of algorithm for the halting problem。

Does。Does anyone see how？ep各 ahead。Right， right， okay， so the answer was， well。

So what do you do you just well you have a program and you have an input to just simulate this program on this input and just keep simulating it。

 if it halt and accepts， then you halt an accept。呃。And in that case。

 you've decided the halting condition。And。If it goes on forever， that's okay。

 you're allowed to just look forever， because that would mean it's not a program that halt on X。

 And if it halt and rejects， then you' still figure out that it holds。

So whatever this steering machine does on X， so there's three possibilities it halts and accepts so then it's halted and then you can say yes。

 the program halt， it halts and rejects， then it's halted and you can say yes the program halts。

 or it just goes on forever， but that's okay it's a program that's not in the language anyway。

 and for programs that are not in the language inputs that are not in the language are allowed to look forever。

 so you're just going to be simulating this thing that's going to look forever， but that's okay。

So this problem is indeed a cururing recognizable language。Okay， does that make sense？Okay。All right。

 so this was the。This is one of the versions of the halting problem we saw last time。

 you can also define this slightly different version， which I'm going to call say。Healt epsilon。

 which is just。You're just given a turing machine and he asks。Mhals on the blank tape。Yeah。

Or you know。The empty input。Okay， so。Similarly， this problem is also。Teruring recognizable。

 obviously the same algorithm still works。 You just simulate the steering machine on the blank tape。

 There's no input。And。If it halt。You say yes， it holds， if it doesn't hold， you look forever。

 and that's okay。Right。Okay， so what have we seen so far？嗯。So so far in this course。

 we have an idea of what this。These languages look like these classes of languages that we've studied。

 So the smallest one。Is this？This class of regular languages that we。

We talked about a couple of weeks ago。And then we saw that the regular languages are contained in。你。

Cont free languages。And。And now what we're talking about is decciable languages。

And what I just introduced。It's a set of recognizable languages。All right。Okay。

 I didn't mention this。Decidable languages are a subset of the recognizable languages。

 So if you have a tuuring machine that decides a language， it also recognize the language。

Is that clear？And that's because。You，The definition of recognizable languages is。

This is a weakening of the definition of decidable languages。 You need to do something more。

In the definition of recitable language， so whatever tuing machine you had that was deciding the language。

 it's also recognizing the language because it fits this definition as well。So。Right。

 so these are the classes of languages that were not familiar with。And。

I think the Siptra book does not mention this， but these classes have。Have other names that are。

That you'll often see online， especially if you look up these classes on like Wikipedia or something。

 and so it's important to， I guess know these things and the class of decidedidable languages is also known as recursive languages。

So。So a deccitable is also known as。Recursive。And it's often denoted by the capital letter R。So。

And the set of recognizable languages。Is often called recursively innumerable。And it's often denoted。

R一。For recursively innumerable。And you'll actually see on your pieceet why this class of languages is called recursively innumerable。

It has something to do with being able to enumerate all the strings in the language。

With a touring machine。So you'll see this on your PSet。All right， so we have。Right。

 so we have these four sets of languages that we've seen in this course so far。All right。

 so now my question is， okay， let me also just。For completeness， put a box here。

And this is the set of all languages。Sometimes called all。All right， okay。

 so my question is where does the halting problem lie in this Venn diagram over here？

So which of the circles is it inside or is it over here？Or is said outside all four circles Okay。

 any questions yeah。It's an REE， okay。And。食。The holding problem is here， okay， and why is it here？

Well， we saw that at C because。As I just explained， the halting problem is recognizable。

 And last time you saw that the halting problem is not decable。 So that's why。

The problems over there。Okay， that's great。And what about this problem， it's the same thing。

Both the holding problem and the holding problem blank。Live over here。Okay。What about- yeah， okay。

 here's a good question。Let me define。Let me define the complement of language is just。So。

For language， L， L compliment is just。You know， the set of all strings。That are not in L。Right。

 it's just。It's just what you think of when I say complement of a language。

 it's just all the stuff that's not in the language。So now we can define halt complement。

 for example。RightSo this is a language。A language which is just the set of all the inputs that are not there。

 so it's the complement of the holding problem。Okay。

 and where do you think the complement of the halting problem lies in this picture over here？Is it？

Yeah， which one of the four circles is it in or is it outside the four circles？Yeah， any guesses？

Just。Just an attempt。Or an idea。Just。Just throw something at me ahead。Outside elsewhere。In all。

 okay that。That sounds。That sounds reasonable。 Does anybody have another guess or。

Or does someone want to。No， that's a more。Think that maybe it's in recursively innumerable now so he's right。

 it's actually over here。Okay， why is it over here， so we know， for example。

 that the halting problem is not decable， so we know the halting problem is not decdable。

 but I claim that this also means that the complement of the halting problem is not decable。

Does anyone want to explain why that's true？So we saw last time that the halting problem was undecidable。

But what I'm claiming additionally is that even the complement of the language is undecidable。Good。

 yeah。That's right。So I mean， a more。I mean， if you wanted to formally base it on the proof we did last time。

These are almost the same language except except the yes and no are flipped when you're supposed to accept you're supposed to reject when you're supposed to reject。

 you're supposed to accept so if there was a way to decide this language then。

Whatever tuuring machine decided this language at the end of the day when it was about to accept you would just reject instead。

 and whenever it was about to reject， you would just accept。

 so you just take that Turing machine and every time it go the source curve of the Turing machine says accept you replace that by reject and every time it says reject you replace it by accept。

And that would give you a tuuring machine that decides the complement of the language that you're citing。

I guess what I'm saying is that the set of decable languages is closed under complement， which means。

 yeah， if a language is decable， then its complement is also decidable， so for example。

 if halt complement was decable， then that would mean that its complement which is just the halting problem would also be decable but we already know that the halting problem is not decable。

 we saw this last time so therefore。This is not this is not decable。ok。the argument makes sense。

 the complement of the halting problem is not decciable but there's another question。

 which is the better question， which is why is halt complement not here。

 why is it not a recognizable language？So intuitively， it's kind of。It's kind of clear like， well。

 how would you do it， How would you decide。The complement of the holding problem with the tuuring machine with this kind of condition。

And。Well， that's nice that it's kind of intuitively clear that that's not possible。

 but you still need to prove this， and I won't prove this because this is also on your problem side。

 so on your PSet you're going to show that the complement of the holding problem is not recognizable。

嗯。So I won't show this。But what I will do is。I'll define。

A notion that's going to come up a lot in this course， especially when you start complexity theory。

 which is the complement of a complexity class， or the complement of a class of languages。

So if you have a set of languages X。So x can be any set of languages that you like， you know。

 the regular languages， context free languages， whatever， just any set of languages。

Then we define something called。Coex or the co sense for complement， where coX is。Yeah。

 this is important， so I don't want know。So x is a set of languages， right， So X contains languages。

 So co X is a set of all languages， such that。The complement of the language is。In X。Okay。

I'm going to let you stare at this for 10 seconds。Okay。

 so coX is the set of all languages whose complement is an X。

 Coex is not the complement of x X complement is it different。

This would be the set of all languages that are not in x， that's not the same thing as coX。Okay， so。

Yeah， this is an important distinction that you should not confuse these two sets。So for example。

X and co X will have the same cardinality。This is because there's， in fact。

 a bijection between the two， which is just， you know。

 every language here L corresponds to some language here， which is just its complementary language。

But X and X complement need not have a bijection， like this set could be much， much larger than x。Y。

新て？Couldn't coex be smaller than x。 Well， there's a bijection， right， Like for every language here。

 there's exactly one language here， which is its complement。 and for every language here。

 there's exactly one language in X， which is its' complement。 So the co of coX is x。😊，Yeah。

 if you write down the definition of co co x， you'll get by x。Yeah。

 there's a one to one correspondence。And the correspondence is easy to see for every language you just complimented。

 that's the guy there， and this is a unique correspondence。 It's just a one to one mapping。

 It's a project。So this is Coex。And。You're going to see this much more later on in the course once we start P and NP and there's going to be NP completeness and there's going to be co NPP and the reason I mentioned this is just that this is the set REE。

 but there's another set which is the complement of RE coRE， and that looks something like this。

This is Cory。And CoRAA contains halt complement。 and why does CoRA contain halt complement。

 it's pretty much by definition。😊，Because CoX contains all the languages who's complementary in X。

Kri contains all the languages whose compliments are。Recognizable。

And so the complement of halt complement is just halt halt is recognizable。

 so therefore halt complement is inquiry， I mean this is just a definition not。呃。

It's not anything deep， but。I'm just mentioning this to say that。There's some kind of symmetry here。

 like halt is not decidable and it's recognizable whereas halt complement is neither of the two。

 and that's just because recognizable is a class that's not。Csed under complement。

 QR is a different classroom， RE。There are languages that are in this class that are not inrecognizable。

 there are languages that are recognizable，'s not cori。

And what you will show on the problem set actually is that this portion。

 the intersection of QAri and RA is actually just equal to the decideidable languages。

 so there's nothing here， so if I drew a point here that's an RA and in QAri but not decidable。

 that's not a thing， there's no language that exists here。So you're going to show this on them。

On the problem say。Okay， so that's Corey， and that's in general the definition of what the complement of a class of languages is。

Okay， yeah， any questions about this？This makes sense to everyone。Okay， good。Okay。

 so that was the part about recognizable languages。And now I can move on to。Okay， something。

Very interesting and also very。没。Simple and straightforward。But。It appears。

A lot in computer science and theoretical computer science reductions appear everywhere。

And it's a really nice concept。It's good to understand this well。All right， so what is a auction？

So reduction。Is。A way of showing that you can solve one problem， given a solution to another problem。

So reduction always involves two problems。And what you say is if I can solve the second problem。

 like if there is a way to solve the second problem。

 then there's also a way to solve the first problem。So this is something that you do all the time。

 you probably do this in well proving。You know，Fs and math， maybe you show something。

 you prove something， and then you show that something else that you wanted to prove is true because of the fact that you've already shown this and you show how these two things are related。

This is something you probably just do in life where you know how to solve certain things and you want to solve something。

That's not in the set of things you know how to solve。

 you try to figure out how can I reduce it to a problem that I already know how to solve。You know。

 for example。Let's say I want to。Say I want to get to Harvard Square，My friend calls me up and says。

 let's make for coffee at Harvard Square。 and maybe I don't know how to get to Harvard Square。

 So I'm like。Hey， how do I get to Harvard Square， I don't know how to get there。

 but let's say my friend doesn't know where I live。

 so he's not able to give me directions to Harvard Square and I don't know where Harvard Square is。

 so he says。Well， do you know how to get to Central Square and I said， yeah， sure。

 I know how to get to Central Square， so he says， well。

 just get to Central Square and then take the red line up one stop north and you're at Harvard Square。

So。So what he's done is reduced the problem of getting to Harvard Square to a simpler problem。

 which is a problem of or to a problem， which is the problem getting to Central Square。

 which is something I know how to sell。 So now I can get to Harvard Square because I know how to get to Central Square and he just。

He just gave me the reduction。 He told me how you get to Harvard Square from Central Square。

 So what was important here is that。So for example。

 he doesn't know how to get from my house to Central Square。 He doesn't know what I live for example。

 So he's just providing the reduction， the link between the two problems。

 He doesn't know how to solve the second problem。 He doesn't know how to solve the problem of how I would get to Central Square。

 I know this， and I know now the reduction that's given me。

 So now I can chain these two things together。 and now I have a way of getting to Harvard Square for my place。

So that's the informal notion of what a reduction is。

 you take a problem that you want to solve getting to Harvard Square。

And you show that how you can solve this given a solution to another problem。

 which is the problem of getting to Central Square， for example。

Any questions about this informal notion， I'll give you a better。

 more formal example in just a minute。But this was just like kind of do。

Motivate the idea of what's going on， This is something you do every day。

 even though you don't formally think of it as a de， you don't say， oh look。

 I've reduced this problem to something， but it's just something that is's just the most natural thing to do。

you solve a problem by reducing it to a problem that you already know how to solve。

So let me give you a more formal example。 Let's say you want to solve a bunch of。Linear equations。

So you have a system of linear equations and you want to solve them。

 and one way to write that is you're given a matrix A。And you're given a vector B。

 and you want to find an x that satisfies A x equals B。 So let's say。It is a。A real matrix size。

 n times n and。B is a real vector of size n。And you want to。Find an X that satisfies this。Okay。

 so so let's say we know how to do。The basic stuff with matrices and vectors。

 you know how to add vectors， you know how to add matrices you know how to multiply a matrix of a matrix and you know how to multiply a matrix as a vector。

 but this is a little more complicated right it's like well how do you do this？😊，Okay。

 let's assume this matrix is invertible， so one way to do this is you just write xs。

A inverse times B。Okay， that's great， but how do you take the inverse of a matrix？And。Okay。

 let's say I't know how to do this。Even though I don't know how to take the inverse。

 what I've shown is you can reduce the problem of solving a set of equations to taking the inverse of a matrix。

So what I can do， for example， now I can write a program， which is。Let me write a program in this。

I know this in a made up programming language， I don't know if any programming language is actually like this。

 but let's say， you know the input is A and B。And then you say， let。C。

And now I'm going to assume the existence of some subroutine that allows me to compute inverses。

 so let me call that。Matrix。Inverse。诶。And then I'm going to say let。Xes c times B and。Out put X。Okay。

 so what is this。 So what I'm trying to do is show you how you reduce the problem of solving linear equations to the problem of。

Of matrixtri inversion。So what I've assumed is that there is a way to take the inverse of the matrix。

 So maybe I don't know how this is done， but this is just。And ability I have。

 this is a subrout that I'm allowed to call。And what I've shown you is an algorithm。

 and this would be called the reduction， because what it shows you is this program will correctly solve。

The problem that we started with， the problem of solving a linear system of equations。

Assuming there is a way to take matrix in verses。What we've done is we've reduced the problem of solving a linear system of equations to the problem of matrix inversion so what that means more operationally is that you're allowed to write an algorithm that's just allowed to assume that there such a thing exists。

 you're allowed to assume that a solution to the problem that you're using to exists so similarly in the central square Harvard Square example my friend was able to assume that there's just an algorithm he can call that just gets me to central square and he doesn't have to worry about that part because I told him that I can take care of that part so the reduction doesn't have to worry about how this matrix inversion is happening。

 you just get to assume。For free there's like this magical subrouting called matrixtri Inversion that just does this for you。

And why would you do such a thing， Why would you reduce this because maybe maybe you already know how to do matrix inversion or maybe you already didn' code for this in a previous class you took or maybe whatever programming language you're using already allows this。

 this is just a。You know this is just a feature of the programming language or it's already in a library or whatever。

 but somehow the important thing is this is something you know how to do or you have ability to do。

 maybe you haven't actually written the code， but this is something you just you can do。

In your programming language， say。You can call a subroutine that somebody else has written and now with this program I can now solve a linear system of equations。

 so here I would say I reduced the linear system of equations problem to matrix inversion。Okay。

 does that make sense， so this was a more。A slightly more formal example compared to the previous one of getting to Harvard Square。

Any questions about this？No， okay。Okay， so let me。Let me say something more formal then。Okay。

 so I'm going to say。Okay， so this is called so let's say there's two problems， A and B， and we say。

It it uses to be。And this is denoted。In the following way。And there's a sub T here to mean toring。

 and I'm going to explain why because what I'm talking about is called。turning Reducibility。Later。

 we'll talk about a different notion of reductions。This one。

Its the one I've been talking about so far it's called Tine a disabilityability and we say A reduces to B and in all these examples B was the problem that you're reducing to。

 the thing that you get to assume， so B is matrix inversion here or in my previous example B was the problem of getting to Central square A is the problem that you actually want to solve。

So we say a reduces to B if there's an algorithm that。

Gets to assume that there is a magical subrout that solves B and is allowed to use this subrout as many times as it wants。

 And at the end of the day， the algorithm needs to solve A。😊。

So that's a more formal definition of what it means for a to reduce to B。So or even more formally。

 or if I want to give you some notation for this， which is。

I want to say that there's an algorithm or there's a Turing machine that has access to B somehow。

 it has free access to this magical subroutine that just solves this problem B for you and then is able to solve A。

And the way we denote this。As we say。So let's say M is a Tring machine。And we say it。

M to the B or M with B in the exponent。Is a tuuring machine that has access to this。

This magical subroutine be， and these things are often called oracles。And I'm so an oracle this。

 you know。呃。Someone who knows knows all things or you know。

Theres some way of thinking about how this。Magical submartine happens to be。

 so you're allowed to ask this this articleacle， you know， this all knowing being， hey， what's the。

The solution， this problem。You know， what is B on some input x and this Oracle will tell you it's whatever x is in the language B or x is not in the language B。

And we'll say that。M to the B is a tuuring machine that has Oracle access to B。

And we say A reduceduces to B if a is decided by。I is decided by empty the B for some tuuring machine M。

So here again。A is the problem that you wanted to solve。

 B is the problem that we're assuming the existence of， we're assuming some solution for this。

 and M is the tuuring machine that's carrying out the reduction。

 so M is the Turing machine that's doing this part over here。Right。

 and B is often called this is often called an oracle because somehow it's just。

It's just something you assume to exist， like you don't have to show how B works。

 you don't have to show how there's an algorithm that actually solves B for you。So。嗯。Yeah。

 so for example here we didn't have to actually explain how matrix inversion works。

 this was just something we assumed， and that's central to the notion of reduction that you assume that there's some solution for the second problem and you just show how to solve the first problem。

 given a solution for the second problem。Okay， any questions about this？On the one hand。

 this is just really。Really obvious notion， but on the other hand， it's also kind of confusing。

And often later in the course。嗯。Later， if you take more courses in complexity theory。

 you'll see people do the reduction wrong all the time。 you want to reduce A to B。

 and then you reduce B to A， so just sit down and think about what the reduction means if you're ever confused about which way you need to do the reduction。

Yes， yes， I mean decided yeah。That is true Okay， right， so the question was， so this is decided。

 which means that。A really does halt on all the yes inputs， A halts on all inputs。

 if x is in the language， it says yes， if x is in the language it says no。So right， so as you said。

 if B is decidable， for example。Then this shows that A is also decable because B is decidable and you gave a decider to solve A。

 you gave a tuuring machine that decides this。You can that means you can come up with one tiring machine that just decides A。

 which is you run this steerring machine every time it wants to call B。

 you already know B is decable so you can just do it yourself。

 And so now you have one tiring machine that decides A。 So if B is decideidable。

 this shows that A is also decidable。 However， the notion of reduction even makes sense of B is not decidable。

 It's still it's a valid thing to show。So B could be a problem that's undecidable。

But you're just showing that if you had the magical ability to solve this undercidable problem。

 then you can solve this other problem。so you might think why would we ever want to do this。

 but it's interesting and I'll give you some examples later on。

 but the more practical way of doing this is you take this to be a problem that you actually know how to solve。

😊，You just want to assume its existence because you don't want to。Explain how that's solved。

 or it's already clear how that's solved， that's already a submarine that you've written beforehand or so on。

Yeah， any other questions？About decability， okay， no reductions。Rather， okay。Okay， yeah。Okay。

 so then there's a question of how do you really， really make this formal？

And maybe it's not super important how you make this extremely formal。

One way to think of it is you have just a programming language。

 whatever your favorite programming language is see your Java or whatever and you just have access to the subroutine and this is just something you can call so in your programming language you're just able to ask questions like is X in B or is x not in B for any input that you feel like so it's just a subroutine that you may access as many times if you feel like but if you want to think of it in this steering machine language then you want to think of what does it mean to have subroutines for tuing machines and so on and this is not too complicated but。

It's a little cumbersome to to lie down all the steps and so on。

 but I'll give you an idea of what would happen。 So you have the steering machine。

 you know which has tapes and so on。 This is the finite state machine of the steering machine。

This is the input。Now this is the input tape， this has your input X that you're trying to decide if x is in A or not。

And this is my tu machine I entered the Be I want to show。That is decided by m to the B。

 so this is currently just a Turing machine， but now it needs access to this you know this language B that we've just assumed exists and so one way of making this formal is you say there's some other tape and this is sometimes called the oracle tape。

Right and now what happens you write down an input here and this is where you expect the oracle to solve the input for you。

 and maybe what happens is you write down an input and then maybe you go to some special state where you say。

 well， I'm done writing the input in the oracle tape and then the oracle comes and erases everything and magically writes down the answer here like yes or no。

And then you can read that answer and you can。You can go about your business doing whatever you want to do and you can keep reusing the Oracle tape as many times as you want。

 you just write down an input over here and then just say， hey， Oracle。

 can you come solve this for me so this would be one way of making it formal。

You don't really need to。Actually sit down and formalize this thing。

 it's fine if you just understand the intuitive notion of you have some programming language。

 you're allowed to call the subordine as many times as you want， that's what a reduction is。

But there is a way to make it formal， I'll just mention that。Okay。Okay。

 any questions about that so far？Reductions， okay， let me give you some examples just so to make。

Thisす。Concept somehow。More concrete， I guess。Okay， so let's go back to the halting problem。

And the two versions of the holding problem that I find over there。And okay。

 so I claim that hearts sub epsilon。The halting problem on the blank input or the empty input。

Reduces to the halting problem。 So this is an example of a reduction where。

Both these problems are undecidable。 so as we were discussing before， if B is decciable。

 this also shows that A is decidable， but it's okay。

 you can have reductions between problems that are not decciable。

All this shows is that you can solve this problem if with access to an oracle that's allowed to solve that solves that problem for you。

 and so that is if you just have some subroutine that solves the halting problem。

 you can also solve halts of epsilon。Okay， and so can someone describe for me why this is true？

It's not a trick question。It's。It's not difficult。Sult machine。What to the as story？

Would invert the output the oracle through。也不不。えその？No。

 halt sub epsilon is not the complement of the problem。

 It's this problem over here just does M halt on the blank tap or now Yeah。

 yeah you're getting ahead like you're getting to more complicated reductions。

 This is just a very simple reduction yeah。Okay， sure， correct ahead。That's right， yeah yeah。

 so you want to write program for this guy and you have access to this problem which is actually a more general problem can it decides halting on any input so you just call the subbriine and you just give it the empty input and you say。

😊，Hey， does my turing machine stop on the empty input just a blank tape？

And this guy is able to solve that for you because we've assume this guy can solve the hoing problem and so you can solve this problem in fact。

 I mean it's kind of easy to see intuitively that this problem is simpler than that one。

 but this is a formal way of showing that given the ability to solve this problem you can also solve this problem。

😊，Any questions about this？This is a fairly straightforward thing What's a little less。

Sriview is the opposite direction。the halting problem itself is redducible to this seemingly simpler problem。

 which means if you have a subroutine that solves the seemingly simpler problem。

 you can solve the general halting problem。Okay， does anyone want to。

Have a guess for how this would go？This is also not very difficult。

 but it's less trivial than the one thing we just saw。Great machine that simulates。As well as。Yeah。

 yeah， yeah。 That's basically the idea。 Yeah， So yeah， one way to think about it is just。I mean。

 here you have some。You have a tuuring machine and an input。

 but this guy is just going to get some tuuring machine as an input， say M prime。

AndBut it's not going to get an input or it's going to get， you know。The empty input。

So what do you want M to do， What you want M to do is just。

First write out x on the input tape and then just simulate whatever M would have done so just it's exactly what you said。

 it's a tuuring machine that simulates M， but because it's not allowed to have input。

 what M prime does is it first just writes down x on the input tape and then simulates。

So then if you ask this oracle， what would my machine M prime do and what would M prime do as in does it halt on R。

 and M prime's behavior is exactly M's behavior on X。

 so M prime halts if and only if M would have halted on X so by solving the halting problem for this M prime on the empty input you've solved the halting problem for M on an input of your choice。

 so this shows。This kind of reduction， that this problem that sounds simpler is actually。

Not simpler because tutoruring machines can just hardco the input。Yeah。

 the input can just be hard coded， I guess that's the best way to say。第二。Oh， sure， okay。Okay。

 so you have the ability to solve this halt eppsilon。

 which is just a halting problem on a blank input。But you want to solve this one。

You want to solve the problem does M halt on input X so you make up a new Turing machine and the first thing so this new tuuring machine it doesn't look at the input at all and what this newuteruring machine does is first it erases what's on the input tape and it writes down x on the input tape so this is something you can do with the tuuring machine of course you can write a string of your choice on the tape。

And then after it's done writing this， then it just simulates the alter Turing machine aim。That's it。

 so M prime is just basically it's just two different pieces。

 there's the first part which writes sex on the tape。

 and then the second part is just do whatever this guy would have done so just simulate it。

And what I'm claiming is that the behavior of M prime is exactly the behavior of M on input x。

Because now what M prime is doing is after the first part is completed， there's x on the input tape。

 and the way M behaves is exactly the same as M。 So now what's happening is it's just M on the input X。

And if this program halts， that means that M would have halted on inputex， so that's why。

 this is a reduction。其实。Okay。Yeah， any other questions about this？This is a very important concept。

 which also seems simple。But it's subtle and sometimes it's confusing。

 so it's important to ask questions。NoNo more questions， okay。Okay， so as we saw these two problems。

A equivalent sorry， one reduces the other， the other reduces to this。

 and so we say that these two problems are actually equivalent。

So we say equality with the T symbol below。And all this means is that these problems are reducible to each other。

 so we say that one problem is tuuring equivalent to another problem if there's a reduction going both ways like this。

And which which means somehow that theyre。Of equal。Equal difficulty。

 like these two are both undecidable problems， as we saw but。

Reduction going both ways means that there are somehow equally hard problems。

One problem isn't no harder than the other， because given a solution for one。

 you can solve the other。So they are comparable difficulty。Okay， and。How about this？

 So this is a slightly。More。Nontrivial example， maybe。Maybe not so。

And I think maybe this was the question that you were trying to answer before。Which is。

 can you reduce the holding problem to the complement of the holding problem？

Does anyone want to answer this？Now we already saw an answer for this before， which is that okay。

 if you have a machine if you have access to an oracle know know magical subroutine that it decides the complement of the language。

 you just get the answer from whatever this case says and you just flip the answer so if this oracle or the subroutine tells you the answer is yes you just say no if it tells you no you just say yes so that's how you reduce a problem to it' its own compliment and this is just。

Yeah， a general feature， you can always reduce a problem to its own complement。

 So in general you have。As steer noticeable to air compliment。And how do you do that。

 you have a subrout for a compliment， run the subrout， whatever it says。

 output the opposite thing now'。Yourse。Let me un that Okay， any questions about this。

 just how you reduce a problem to its own compliment？Okay。

Maybe this is something really trivial that I did not mention。

 but it's almost too trivial to mention， but let me just mention it。

Wch is you can always reduce a problem to itself。So how do you solve a given an oracle that solves a for you？

Yeah you just call the oracle and ask， hey， what's the answer to my problem and whatever it says that's the answer。

 so this is kind of trivial。😊，嗯。Another thing is okay。

 you might think why do we use this notation of less than equals one reason we use less than equals is to suggest this notion of this problem is no harder than that problem like you know given a way to solve this guy you can solve this guy so this one is in some sense simpler than that。

But it could be equally hard。 So that's why we allow equality。

 But something to check whenever we use the notation less than equal to is。It should。

This is a property that you expect to hold from all relations that have the less than equal symbol。

Just anywhere in life， if you see the less than equal symbol。

You would intuitively expect this as true。Or transitivity， which means if A。

A is less than BB is less than C than A should be less than C。

 This is true for real numbers and whatever kind of numbers， In fact。

 anytime you use the less than equal symbol this property probably just has to be true。

 that's why the person chose the less than equal symbol to denote this concept and this concept is true for your introductions as well。

嗯。And does someone want to give me an informal sketch of why this is true？

Just intuitively why this would be true。So what this means is if there is a deduction from B to C。

 which means there' is a way to solve the problem B， given an oracle for C。

 and theres a way to solve problem A， given an oracle for B， then there's a way to solve a problem A。

 given an oracle for C。any ideas？Does anyone yeah， go ahead。明。The conversion for。C to be。比的A。

Right it's like it's like you're composing these two things exactly it's like you see you run this algorithm for a。

 one way to think of it is you run this algorithm that does a reduction from A to B。

 and every time it needs to solve B， you go and look up this second algorithm that you also have with you which reduces B to C。

 so now you stop executing this first algorithm start executing the second one。😊。

Solve B and every time it needs Oracle access to C。

 you have Oracle access to C you just call C and at the end of this algorithm you've decided B now that you've decided B。

 you go back here and you use the answer to B to solve this guy and then you keep computing this algorithm。

 the reduction and maybe you need to call B again and then you just do this again and as many times as you need to call B。

 you go and run this reduction run this reducing algorithm and this algorithm whenever it needs Oracle access to C you already have C。

That's why it works。嗯。This is something you do when you program as well often that you write one subroutine that uses another subroutine in its execution and then you write another subroutine that uses another subrtin。

 you can chain together subroutines and that's not a problem at well。Okay。That's good。All right。Okay。

Right。And here's another。Let's say。Let's say L is a decidedable language。Dciable。And I claim that。Do。

So I claim that if L is a decidedable language and you can tune and reduce it to anything。

 you feel like any language at all doesn't have to be a complicated language。

 it could just be a simple language， could be the empty language that doesn't do anything。Okay。

 so how how how do you do this？ So how do you solve。L， which is a decable language or a decable。

Problem using isolation solution to something。Something that's not even interesting maybe。

Anyway is yeah， it's not a trick question， some people are looking at me like ah。

What's happening here？No。Yeah， great。That's right。community。

Exactly right so this algorithm that you're allowed to run in this reduction is just you any old Turing machine so you could just run the tuuring machine that solves L you know L is recable so there is a tuuring machine that solves L so you just just solve it like you don't need to you're not forced to access this oracle like you have the ability to call this subroutine。

The subroutine B in a introductionuction。Like no one's forcing you to use it。

 you just ignore that guy， and then you just go about your day and solve L as you would have had you not had access to a subroutine。

 and you know that that's possible because I said L is decidedidable。So right。

 so one interpretation of that is that decidable languages are the easiest things in this tuuring reduction notion because。

Everything just reduces to it。 I mean， a decable language can be reduced to anything。

 So you don't need anything to solve a decable language。 You can just do it yourself。

So that's our notion of reduction， a reduction is powerful enough to solve decidable languages by itself。

 doesn't need anybody's help to solve a decidable language。Right。

Is that confusing or did that make sense？不能。I'm going to go with it made sense。All right， so that's。

Okay， that's decable languages and how you can show that a decable language reduces to pretty much anything。

Or actually anything because he just ignored the oracle。All right， so these are touring reductions。

Let me just quickly talk about another notion of reduction that you will see more of later on in the course and maybe it's not so important right now。

I'll just mention it。AndThis is called a mapping reduction。Okay。

Okay and a mapping reduction is this kind of reduction is a special kind of tuuring reduction where。

Instead of being able to call the subroutine as many times as you want and doing whatever you want effort。

 you're allowed to call the subroutine exactly once。

 and you have to output whatever the subroutine outputs， that's the condition。So。

What this means is you're allowed to run some algorithm that you want。

runun the entire algorithm and at the end of the day you have to call the subroutine and you have to call it exactly once you call the subroutine and then if the subroutine answers with yes。

 the input that you have provided me is in the language， then you have to output yes。

 if the subroutine says no， then you have to output no。

So it's a restricted form of a tuuring reduction。And for example。

 these two reductions that we saw these are also mapping reductions because that's exactly what we did to solve this problem we called this oracle exactly once。

 we called it with the input to this problem and with the blank tape and whatever the output of this guy was。

 we just，Were just going to blindly output whatever he said。

 so you're not allowed to process the output of the subrout call and you're not allowed to make the subrout call exactly once。

 so this is a mapping reduction。There's a lot more about mapping reductions in the book。But。

But maybe it's not so important to get it through right now。

 but you'll see more mapping reductions later on when we do complexity T there。

They're pretty interesting。Any questions about mapping reductions？ Yes， so these are。

 these are examples of mapping reductions。 And this is not an example of a mapping reduction。 Yeah。

 that's good。It's always important to see examples that are not examples of the concept you're trying to explain Yeah this is not a mapping reduction why it's not a mapping reduction。

 you call the oracle only once， that part's true， but you did not just outputt the answer of the oracle。

 you would had this thing where you flip the output， so that's not allowed in a mapping reduction。

So this is not a mapping reduction， and in fact you can prove that there's no mapping reduction between these two languages。

So mapping reduction is a more restricted version of achieving reduction。Right。

 any questions about this， why this is not a mapping reduction？い。

Why do people study mapping reductions， that's an excellent question。So with tuing reductions。

 what we saw is that。Let's look at this chart over here。

So we showed that there is a tuuring reduction between halt and halt complement。

So what tuuring reductions do is somehow they're very powerful， but what they do is Ari and QAri。

Problems are reducible to each other。If you want to think of。呃。

Problems that are equivalent to each other under tuuring reductions Rri and Cori would both be the same class so somehow a tuuring reduction blurs the distinction between RAri and Cori and in general a tuuring reduction blurs the distinction between a class and each complement because you can always reduce a problem to a language to its complementary language whereas a mapping reduction does not do this so if you do not have a mapping reduction between heart and hard complement and in general you do not have a mapping reduction between any problem that lives here and a problem that lives here because they're in different classes so a mapping reduction is a very restricted form of reduction and it preserves this distinction between Rri and Cori and that's why we like to use it because later on you'll see there's a whole bunch of classes where we really want to pay attention whether we're talking about the class or the complement of the class and if you want to do that and you don't want to blur the distinction released to classes you should be very careful and only use mapping reductions because if you use tuuring reductions you're going to mix up two classes so。

In some sense， this is one of the reasons you study mapping introductions。

Another reason is just it's a weaker notion， so it's。

It's often just nicer to use a weaker notion when you're proving something because then you've proved a stronger result。

So that would be one of the reason why mapping deductions are steady。

Okay any other questions about this？Mapping reductions。Right， okay。Yeah。

 so as I said a mapping reduction is a special case of a tuuring reduction。

 it's a restricted form of tuuring reduction so whenever there's a mapping reduction between two problems there's obviously a tuuring reduction between those two problems。

 you just use the mapping reduction， but the converse is not true as exemplified by this example over here。

So there are problems that are clearly deducible， but not mapping deducible。All right， so。

Now that we've talked about that， let's talk about something more fun。Which is。

More undecidable problems。Okay， so it turns out I didn't really。Give you a formal definition of this。

Yeah， forget about that。Okay， so we saw an undecidable problem last time， right。

That the halting problem is undecidable， this one。Or this one。

 I forget which ones culture was undecidable， but they're both undecidable。Okay。

 why is that the case so let's say Scott proved this one was undecidable last time。

 so I claim that just because this one is undecidable， this one is also undecidable。

Does someone want to give me an easy argument？That's right， that's right。

That's exactly like if you can one， you canol the other because of this reduction over here。

So because so I mean let's be very explicit and go through the argument right so we showed that this is undecidable and then we' want to show this guy's undecidable so toward a contradiction assume this one is decidable。

 if this was decdable we already showed a reduction from halt epsilon to this so if this is deciddable then that means this is also decidedcidable but then you showed halt epsilon is dedable but halt epsilon is undecidable we proved this last time and therefore this guy has to be undecidable。

😊，So that would be the formal way of saying it， but just more intuitively two problems of equivalent and itary introductions means that they both have to be undecidable or they both have to be decidecidable。

 they're basically of equal difficulty or equal hardness。Okay， so that's a very intuitive notion。

So this is one way of showing a problem is undecidable。

 So last time we proved that the halting problem is undecidable using this diagonalization argument。

But so that's certainly a way of showing something is undecidable。

But what's usually done is you just show something's undecidable using this trick。

 You just show that the halt problem reduces to that problem。 So if you have a language。L。

And you showed that。The halting problem。Any of the versions of the halting problem？Reduce the cell。

 This means L has to be undecidable。 right， This is the argument we just sketched。

Because if L was deciddable and that means the halting problem can be solved with access to an L oracle。

 but L is decdable， so the whole thing is decidable， so a halting problem is decidable。

 but that's a contradiction， so therefore L has to be undecidable。😊，So， this is a。

Classic and time honored way of showing problems to be undecidable。

Start a reduction from the hearting problem and you start a reduction from here to the problem that you want to show is undecidable。

If you control this reduction， then L has to be undecidable。Does this strategy make sense？It's a。

Right。It's pretty。Straightfor strategy， I guess。Okay， and let me give you an example of。

Things that were shown to be undecidable using this strategy。嗯。Okay。

 so here's a nice example which I think Scott mentioned this。呃。Maybe last class or two classes ago。

Let me。Std again， so this was Hilbert's1th problem。

 so Hilbert in I think 1900 or so gave this very influential talk where he listed a whole bunch of important problems for mathematics。

😊，And one of them was the following problem， the tenth one。 and it was the problem of solving。

Diohanantine equations。So。What is a diantine equation。

 it's just a system of polynomial equations with integer coefficients。

A bunch of equations over say a couple of variables， and they all have integer coefficients。

 so I'll give you an example of a diphoning。Equation， which is， let's say x to the n plus。

Y be n equals z to the n。And。N is greater than three。嗯。X， Y and C are not0。O。And now。So this is。

 for example， a diaphraranteine equation and the question is。

Is there an integer solution to this equation， So do that exist integers X。

 Y and Z and N so that this equation is satisfied， So that would be the example that would be an example of。

The question of。The solution to a diecting equation。

We just want to know whether a solution exists or not。So this problem。

 if you've recognized it was very well known， it's called FMA's last theorem or FA's last conjecture。

 maybe because he didn't really prove it and it was proved 3，50 years later， a decade ago。

 two decades ago， in 1995 by Andrew Wils， and he showed that there is no solution to the set of equations。

There are no X， Y， and z in end， so that this set of equations is true。If n was allowed to be two。

 there are solutions， of course， and this is just， you can take three， four， and five。

And if n was one， then of course there are solutions。

 surely you can find3 numbers so the first two add up to the third one。But。

The conjecture was that if n is3 or larger， there's no way to solve this with integers。

And it turns out that it's true， that there is no way to solve integers。

So this is a specific example of a diphonine equation， but what Hilberts asked is。

 is there an algorithm that just accepts as input a diphonine equation and then outputs。

 is there a solution or not， is there an integer solution， this system of polynomial equations？

And maybe it's not too hard to see， but this problem is really hard。Well。

 how do you know if there's a solution to the set of equations？

One thing you could do is you could just like。Run through all possible X， Y， z and N。

 and then if there is a solution you'll find it， and if there isn't a solution your tuuring machine is just going to look forever。

So。That shows that this problem is reducible to the halting problem。 So let me call this problem。

That。The dear Fine equation problem and what I just said。Is it a this way？

Which means if you can solve the halting problem， you can solve this problem and why is that what does the program do is just checks all possible solutions if a solution is found it halts and otherwise it doesn't halt because it keeps looking for more solutions。

And so if you can decide the halting problem， then you can just feed this machine into the halting problem and say。

 hey does this machine halt or not， if it halt that means a solution must be found。

 so there is a solution and so you've solved this problem， and if it doesn't halt。

 then there is no solution。So this is a deduction this way。

So what does it say about this problem it just says that it can be solved given a holding problem oracle？

So this doesn't really say anything。Particularly enlightening about this problem。

What Hilbert wanted was an algorithm for this problem， so what was shown later on is in fact。

 the other way around this is also true， you can reduce the Htic problem to this。

This is a far more non trivial statement because what this says is that you can solve a halting problem given an algorithm that solves this problem。

So if someone， you know。A really smart mathematician comes up with an algorithm to solve these kinds of problems like diinine equations。

 So maybe he just comes up with some kind of algorithm that looks at all the variables。

 looks at something， just some。Crazy math stuff on it， and then decides at the end of the day， yes。

 a solution must exist or solution must。Cannot exist。

 Such an algorithm does not exist because if such an algorithm existed。

 then there would be an algorithm for the ho problem。

 which we know that is not because you know it's undecidable。

 So this means the problem of figuring out whether a diphrarantine equation has a solution or not is undecidable。

 So this was a problem that Hilbert posed， he said。Hey。

 let's come up with an algorithm that solves these things， but there is no algorithm。

 Like this is something that probably。He didn't even think of。

 like this was tiny something he could conceive back then like that what does that mean。

 there's no algorithm， you know， just just come up with an algorithm。

 that's the way you phrase the problem is like， you know。

 come up with an algorithm to solve this problem，What's really interesting is that someone shared that there is no such algorithm for a very reasonable math problem。

 like this problem has nothing to do with tuuring machines and so on。

 like you would think the halting problem for sure like fine。

 that's undecidable because it's so contrived and unnatural and the problem itself is about tuuring machines。

 so sure maybe it's undecidable， but this is just like。A legit math problem。

 and turns out to be undecidable。Yeah， it's pretty cool if you could go back in time and tell Hilbert。

 which would just like blow his mind， probably。是啊所就是。Yeah， this is a nice example of a problem。

That's undecidable and so it's important here that we're looking for integer solutions。

 so we're looking for solutions over Z， and this is undecidable。😊。

What's also really interesting is if you're asked for real number solutions。

Our complex number solutions， then it turns out that this is decidable。And there is an algorithm。

if you're looking for real number solutions or complex number solutions。

 which might be non intuitive to you， I don't know if you're thinking of reals and complexes as being more complex。

 complicated objects。But what's even more surprising is if you think of the actualal numbers。

This is unknown。So no one knows whether it's decidedable， undecidable。Could be， could be anything。

So the answer is known for integers， it's not for real numbers， known for complex numbers。

 it's not known for rational numbers。Yeah， strange stuff can happen， iss basically what I'm saying。

Any questions about this example？没有。I mean all the variables， so this problem has four variables， x。

 Y， z and n， and in this diinine equation problem， all the variables have to be integers and the question is does that exist a solution where all the variables take on integer values。

 but now if you just change the problem too，Does that exist a solution？

Where all the variables take on real values all complex variables。

 not this specific set of equations， I just mean any diphund in equation。

 So the problem is given a set of equations as input and asked。

Are there real numbers that satisfy the set of equations or are there complex numbers。

 this problem is undecidable？So。Yeah， it's pretty。It's pretty surprising if you haven't seen this before。

But。Yeah， that's how it is， any other questions about this？

I'll give you another example that's even more surprising， maybe。I think it's more surprising。

And this is called the matrix mortality problem。So here what I do is I give you a bunch of matrices。

And let's say the integer matrices。Of dimension K。 So I give you n K by K matrices。

 And the question I'm asking you is。Is there a way to multiply these matrices in any order and you're allowed to use any matrix you want as many times as you want so that at the end of the day。

 the product is zero？So is there a way to muzzulate out these matrices。

 you're allowed to reuse matrices， you're allowed to multiply them in whatever order you feel like。

 so that the product is zero。And it turns out that this problem is undecidable。

So what's actually very surprising is it's undecidable even for k equals 3。

Which means I just give you a bunch of three by three matrices， right。

 These are really simple objects， right， just three by3 matrices。 All the numbers are integers。

 There's nothing crazy going on。 There's no real numbers hiding anywhere。Three by3 matrices。

 all of them are integers。And I give you a bunch of these matrices and deciding if there's a way to multiply them to get zero or not undecidable。

😊，M number。No no no the problem is that you can reuse matrices。

 so you can think of all permutations multiple these， but then you can use them over and over again。

 so you might want to do a like a billion times first and then A2 and so on。Yeah。

 but that's a good question， so is n fixed or not？诶。

The problem is it's easier to show the problem is undecidable in this way。

 but actually you can even fix n and you can fix n to be5。😊，There's five matrices。

 just so now I'm going to give you five matrices。Of。3 by three matrices， so 5，3 by three matrices。

This is going to be your input and you just have to decide if there's a way to multiply or these5 guys in any order you feel like and you may reuse matrices as many times as you want。

 so as to get0 or not and even this problem is undecidable。Like this is。Really surprising， I mean。

 especially because the linear algebra problem usually think of linear algebra problems is you think。

 oh， there must be some way to do this， I don't know something。

 write down something about range spaces and whatever， like something span of some vector。

 something will happen and you'll be able to figure it out， but no it's undecidable。😊。

It's really strange and what's also surprising is for k equals2， we don't know the answer。

It's not known if it's undecidable。And what we do know is that for K equals one， it is decidable。

Because。You just check if any of the matrices are zero or not。So that's the state of affairs here。

Very a varied set of problems that have nothing to do with tu machines。Can be undecidable， know。

 problems that are just completely reasonable。 This could have been a problem that you would have thought surely there's an algorithm。

 maybe it's not very efficient， but surely there's a way to do this but。But no， there isn't。Yeah。

 these things happen。So okay， yeah。 So that was some example of。Uncidable problems， just to show you。

A flavor of what kind of stuff turns out to be undecidable。 right。

 So this problem is also Turing equivalent to。嗯。The whole thing problem。So。

So let me do a little diagram of what we know right now。So。So we have these decable languages here。

And here， we have the。The halting problem。The hog epsilon。嗯。This diing equation problem。

This matrix mortality problem。I just talked about all of these at tuuring equivalent to each other。

 which means there's a reduction from between any pair of these problems。

 there's a reduction going both ways， a tuuring reduction。And for decable problems also， of course。

 between any two deable problems there' a tuuring reduction going anyway， any two ways。

 so this concept of where you draw a little circle and put problems inside this。

 this thing is called a tuuring degree。So a tuuring degree is a set of problems that are all equivalent to each other under tuuring reductions。

So this set of problems is a tuuring degree and this set of problems is a touring degree。

And these are separate circles because we know that there's no reduction from the halting problem to a problem here。

 for example， because that would then mean that the halting problem istable。

 which you've shown it's not。So these circles are equivalentence classes。

 they are problems that are equally hard。During introductions。Right。

 and all of these problems are equally hard。It's easy to show that these two problems reduce to the halt problem。

 the other one is the nontravial direction。Okay， so that's something。

So this is what the picture looks like right now。All right。

So what questions come to your mind when you see a picture like this？

A really natural question that comes to my mind is。Firstly。Okay， these circles。

So how many problems are in each of these little circles like so how many languages are there in a tuing degree？

I'm going to let you think about that for a second， Does anybody want to guess？

Which means how many languages can there be that？Equivalent of the halting problem， for example。Any。

Any guesses here？I love cereal， okay， yeah， why is that？I just guess that's great， that's good。

 it's important to just guess things right。If anybody else want to say why， that's true。Yeah。

 there's basically two options， right L of 0 and L of2 to the L of 0 because we haven't really talked about any other cardinalities。

 Okay， why is that true is because the set of altering machines has cardinality all of 0。😊。

So how would you show a problem is equivalent to the halting problem。

 you would come up with a turing machine that performs a reduction。

 but there aren't that many tuuring machines to go around。

 there are only Llf0 number of turing machines， so there can only be Llf0 problems that reduce to a problem doesn't matter what the problem is for any problem。

There's only all of zero number of things that can reduce to it because that's just the total number of tuing machines that you have。

And。You need a tuing machine to do the reduction。呃。So that shows that。You know。That are love Ze。

Problems。You know， in any of these in any of these little。Circle things question。That's right。

 it's an upper bound， I guess， because。So surely you cannot have more than L because that's just the total number of drilling machines you have available for reductions。

 so at most you can have LF problems that are equivalent to the halting problem what I'm saying。Okay。

嗯。Okay， here's another question。Okay， now you might say， what about problems here？

Is this it like it just thats？The decable problems， then there's like the really hard ones。

 the ones that are equivalent to the halting problem， is there anything here？

Is it a problem that's harder than the holding problem， does anybody have a guess？

Is there something that's so hard that？Even the halt problem can now solve this problem？

Question this。Yes， okay， good， Yes， anyone has a proposal for why this would be true， Sure， go on。

Where保 you。Just see what there。这得意思是。Right， right， so I think what you're saying is that you can come up with harder problems。

And one of them is what Scott likes to call the super halting problem。

This is just the problem of I give you a tutoruring machine。

And this steering machine has access to a halting oracle。

 So this steer machine can call a halting oracle as many times as it wants to。 Another question is。

Does this tuuring machine halt or not， So this is not a standard tuuring machine。

 It's already a tuuring machine that is augmented with the power to solve holding problem。

 the holding problem。 So it's you know this steeruring machine is very powerful。

 and I are asking the question about such tuuring machines， Can such tuuring machines halt。

And it turns out that this problem is even harder。 Like you cannot solve this with a halting problem。

And why is that the case the reason that's the case is that you take the proof that you saw last time for the undecidability halting problem and you repeat the exact same proof。

 but every time you have a tearring machine you just allow it access to this halting oracle。

 so the exact same proof works。😊，But every time you see a turing machine in that proof you just say you know this turing machine is allowed access to the halting problem。

 so you whenever you see a turing machine M you just change that proof and write this little word halt here as the exponent for all the turing machines and that same proof will be completely correct and will prove to you that the halting problem。

This problem， the super holding problem， is not aable to the holding problem。So this is really cool。

😊，The proof that we already did can prove more things for you and in fact。

You don't have to stop here like there's a problem that's above the super halting problem which is like the super duper halting problem。

 which is the problem of steering machines that have access to a super halting problem oracle and then you can do super duper whooper halting problem and that's just like an infinite set of problems like this yeah。

To take advantage of the。You would need to be able。That。That's right。

Yeah yeah so that's one intuitive way of saying that that's right。

 that's something higher degree and yeah， this is just a general construction you can just keep coming up with harder and harder languages we're almost out of time。

😊，And it's really cool that same proof works and you can come up with harder and harder languages。

 and this is a concept you'll see later on in complexity theory as well of the same proof working when oracles are around like for every machine in the language you can just put an oracle and such things are called。

😊，Reltivizing proofs。呃。It's not really important right now， I guess you're not going to。一。

Seeve too much of this in this course， but it's interesting。

 This is a general property of certain types of proofs that you can always just just make them true by putting articlesacles everywhere。

 and you get a new theorem for free。 and you put a different article and you get another theorem for free。

 So you can prove like a whole bunch of infinitely many theorems。😊，From one proof。

About by just putting articles over there。Okay， so maybe is that the last thing， okay。

 maybe another question is so you have an infinite set like this。

 you have each of these blobs contains all of zero problems and maybe the only other thing that I would have thought of is is there a problem here？

Is it a class here that？You know， is of intermediate difficulty between decidable problems and the halting problem。

 and it turns out that the answer is yes， that is indeed a problem here of intermediate difficulty。

So this is not obvious at all， and this was a pretty hard problem。

 it was called post problem and someone proved it in the 50s， I believe， but。If you think about it。

 you might think， oh well maybe the holding problem is like the easiest problem that's not decidable。

 but that's not true， the halt problem is pretty powerful so there's a set here and there's a set here and in fact there's infinitely many sets between this guy and this guy。

So there's infinitely manying degrees of problems that are all intermediate between the side of a problem and all the classes。

It's just a crazy world。All right， okay， that's the end of this and then there's the one that I'm going to hack because I reshot。

Yeah， but I think what what I'm sorry， I forgot the other guy's name not Aquiquino said he was going to do was he was going to concatenate Okay so then and then I'm going I'm going to look at it and then give him the pointers I mean。

 that's not to keep do。It's just's nice to do you know get it out of the way so before we forget。

 awesome。And I know you can do with something you guys have。こ是谁。well， oh， no， no。

 So the quizz is next week， but。The one thing that we need to remind you of is because of the cancellation。

 our schedule has changed slightly， so who should I email to make sure you guys know to come on the one day that we actually said you weren't going to come。

Like next Thursday a week from today， we had canceled the class because of the quiz。

 but we are going to have a class and z No， no， were going to cancel the section。

We are legally bound if we have a quiz， I understand yeah。

 so you have to have a z so you can email Brett， all right， excellent， thank you。ま。Because charity。

setting intermediate sort they're like a like one。come I'm going to start era you get some really neat writing。

 man。Is that you？All right。き。そよ。比生水。Need writing。い。No， no， come on。I think it was this guy。Subidute。

I' better erase the writing before people show up and start comparing it with mine。Right。I asked him。

 how is he？おりさん。You were writing it。no， I'm in charge， yeah。

 I'll take care of it I'm going to seriously next 24 hours I'm going to do a lot。

 but I can do is go over a of it Yeah you should just do your thing。

 Eric should do his thing I'll do I'm waiting for him。Yeah， yeah， no， I mean， I got hung up on。

A whole week of new materials prepare。Yeah， no， no， don't worry about it。

