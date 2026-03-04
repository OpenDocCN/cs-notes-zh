# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p09 P9 mar10 -BV1Dao8YQEEn_p9-

All right， good， so let's get started， so PSet three was out yesterday， as you may have seen。

 it is do Friday of next week okay and that'll be the last PSet before the midterm I guess okay we'll talk about the midterm later。

 but so last week we sort of finished on sort of pure computability theory。

 we talked about how do you prove。So that some language is equivalent to the halting problem right and you can do it via a reduction okay using the you know central concept of an oracle right you show that you know if you had an oracle to solve your problem then you could also solve the halting problem you know that's then a proof that your problem must also be uncomputable and you know not only uncomputable but in the same touring degree as the halting problem okay and you know and sometimes you know these proofs can be interesting you know we did a couple examples。

You know okay you know and and the other thing is that you know it may be of interest to know that your problem is at least no harder than the halting problem right and so you know or that your problem is recursively innumerable they say that is you know there exists a program that when you run it for infinite time will list all of the the yes inputs you know of your language will list all of the strings that are in your language that's what it means for a language to be recursively innumerable okay and the halting problem is an excellent example or the halt language it's an excellent example of a language that is recursively innumerable but is not computable okay thereby showing that those two concepts are different from each other and so we saw last week sort of some techniques for showing that a language is recursively innumerable and by the way you know you know if you know that your language is recursively。

numerable and that sort of immediately implies that it's reducible to the halting problem it's a stronger property okay so we saw how you can dovetail you know over all touring machines you know sort of running you keep incrementing tea and then running you the first tea machines for tea time steps okay very useful technique and we saw coninglemma that says that sort of you know you if you can construct sort of arbitrarily long finite strings。

 you know that sort of satisfy some condition in particular。

 if you can construct sort of you know if you have some tree with like a finite branching factor and you can construct arbitrarily long paths。

 finite paths through the tree， then in fact the tree must have an infinite path。Okay， also useful。

 Okay， and then we started talking about self reference， which is know where things really get fun。

 I think， okay。You knowSo you know the issues of know self-reference go back to the ancient Greeks to know the paradox of the liar where you say you know this sentence is false okay but you you know it would be nice to be able to ignore know these sort of puzzles but you're saying well you know we don't care about sentences that talk about themselves and that's it but the problem with that which was you know sort of you know started to be to be realized you know in the early 20th century with people like Tasky and Gardo is that sometimes you know you can you know once you have a powerful enough language then sort of it will be able to express sentences that talk about themselves whether you wanted that or not and so you're going to have to deal with it somehow if you know to be able to say that your whole you know system of reasoning is sound as consistent is whatever。

Okay， so so so in some sense there's no avoiding self-reence okay and you know you know one example is because you you you can always say something like the following sentence repeated twice the second time in quotes is false you know in quotes the following sentence repeated twice the second time in quotes is false right so then you have a sentence that's only talking about some other sentence that's in quotes and yet indirectly it is talking about itself okay and you know and a very you know a concrete analog of that is you know how it's possible to write a program that prints itself as output so the。

so you know， we saw you know how to do that， you can say you know print the following twice the second time in quotes and then in quotes。

 print the following twice the second time in quotes okay。

 it's a very good exercise you know we're not going to put it on a PSap， but if you've never done it。

 you know， just take your favorite programming language and just write a program that does that。

 you know write a non-empty program that you know that when you run it its output as itself。Okay。

 you know， you basically just have to you know implement that you know that pseudocode of you print print the following twice the second time in quotes。

 okay and in recitation， you you heard about sort of the recursion theorem。

 which basically says that given any program whatsoever。

 you know you can always assume without loss of generality that that program takes its own code as an additional input。

 okay， so that's sort of a that's a form of self-reence that you know you can always satisfy。

 okay you can you know， when when you're writing a program。

 you know you're allowed to just say look at the source code of the program。

 even though you know by the very fact of you know writing a program you're modifying the source code。

you know， there's always a consistent way to sort of solve that that you know。

 to sort of unravel that circularity， you know， and the essential idea of it is really just contained in the you know in that print that print the following twice the second time in quotes example。

 or you could say you know take a program that just say print its own source code and then you could compile it into know into that print the following twice the second time in quotes thing。

Okay， so。All right， and then last week we started talking about Gerrdel's incompleteness theorem which is sort of the most you know sort of spectacular demonstration of all these ideas so to say what Gerrdel's theorem is you have to say something。

 at least at an informal level you have to say something about formal systems， okay or proof systems。

 so a proof system is just you know as we said， it's a collection of so it's a formal language for expressing mathematical statements and then a collection of axioms and rules of inference for in the rules of inference you can use to derive new statements。

 typically infinitely many statements by just starting from the axioms and so the various properties that you might want a formal。

System to have so you know you may you know want it to be sound meaning you know everything that it says as a theorem is true okay that sounds pretty obvious right a weaker condition than soundness you know but you know which maybe we would settle for is consistency okay that at least it never says you know it never proves both you know a theorem and and the negation of that theorem right you know the system should never both you know say that both a and not a are true okay。

Then computability means that there should be some touring machine that we could write down that lists all of the theorems of the system。

 that lists everything that the system says is true， or to put it another way。

 the set of theorems of our proof system should be recursively innumerable。Okay。And then know。

 really ambitiously， we might want our system to be complete， okay。

 which would mean that given any sentence whatsoever that you can write in the language of the system。

 the system can either prove it or it can prove its negation。

So sort of it determines the answer to everything and then know subject to all of these these conditions。

 you may want your proof system to be as powerful as possible。

 meaning that it should capture sort of as much of mathematical reasoning as you can get it to。Okay。

 so。So then you know that's sort of the context for you stating Gardle's first incompleteness theorem okay and what it basically says is that if you have you or sort of a weak form that you know I can sort of talk about the proof of here is that if you have a proof system F and it's sound and it's computerutable ands sort of this is a little bit vague but I'll be clear about it。

 it's powerful enough that it is able to encode sentences about arithmetic。

 meaning you like it is able to talk about things like whether or not a given computer program halts。

 okay that's really what I mean you know I mean I I I mean what else is there two arithmetic。

 you besides you computer programs and whether they hold。

 okay I mean powerful enough to to sort of express sentences。

This touring machine runs forever or this touring machine halt something like that so' if a system can't even talk about statements like that。

 thens sort of it's clear that it's not I hope we agree that it's then not talking about all of math whether a touring machine halt or doesn't halt seems like a perfectly reasonable mathematical question that you could ask so we're saying if your system is。

sound， it's computable， you know， and it captures you know， ordinary arithmetic， you know。

 for example， you know questions about you know whether computable processes halt or not。

 then it cannot be complete， okay， then there must be you know statements that you know it can neither prove nor disprove。

So。So you know it sounds like there's a lot of conditions in this theorem。

 there's a lot of fine print here which by the way know when people popularize Gdel's theorem。

 they often weave out the fine print， but let me you know maybe to help build your intuition about it。

 let me let's convince ourselves that you know if we removed any piece of this fine print then the theorem would actually be false so first of all。

 can we get a computable system that captures arithmetic and that's complete。

 but we just give up on soundness， which doesn't have to be sound。

 can anyone give me an example of that。I'll let you give up on consistency too。excellent。

 excellent example， just say everything is true， you know。know A is true， not A is true。

 but you just proved a contradiction。 that's also true。 there's a classic joke along those lines。

 right。😊，Good， all right。 So obviously， we need to assume soundness。 All right。

 what if we took away the assumption of computability， What then。

Can anyone give me an example of a sound complete proof system that captures all of arithmetic。

 but it just isn't computable？We just give up on there being a computable way to list all the theorems。

Yeah。Deect weather something。You just。Ittererate through。The possible。Of inference and。And。

And you can finally get the sentence to。Yeah， okay， I mean。

 I think you're headed toward the right idea right which is that we can take sort of a platonic proof system right like I will take a proof system whose axioms are are just and which are the same thing as its theorems。

 whose axioms are just all of the true statements of arithmetic there。😊。

I just defined it right I've taken， you know， for Mas last theorem， you tell me it's true， good。

 then that's an axiom right as you know， as soon as I know something is true。

 then then it's an axiom of my system Okay so I just take all the true sentences about arithmetic and none of the false ones as my axioms right。

 you know， I can。😊，I I can talk about that as some mathematical entity。

 the set of all the true statements of arithmetic by definition it will be sound and it will capture arithmetic and it will be complete。

 the only problem quote unquote is well you know I've just defined the problem away how do I actually figure out which sentences are true how know I mean know and this sort of shows us that ultimately you know we want more from a proof system then just that it sort of platonically captures all the true statements。

 you know we need some actual way to derive true statements you know by some computable process you and you know people sort of groped around by what do they mean by a computable process for a long time and then once touring machines were invented in 1936 then people like Gertel said aha this is what we meant okay。

That there ought to be a touring machine that lists the theorems， all right。😊。

How about a sound computable and complete proof system， but that just doesn't capture arithmetic。

Its just to say they capture something weaker。Anyone know an example of that？Sound computable。

 complete， but it's just going to be too weak to talk about arithmetic。Okay。Okay， so。

I'll give you an example of such a system if we just consider you know bulloleyan logic or another。

 you know， which is also called propositional logic。

 okay where you know we don't have any quantifiers like for all or there exists right the only thing that we have are sort of。

You know， we have some set of symbols。X1 up to xn。You know， we're allowed to。

 you know you know a true sentence to something like either x1 or not x1 is true。Right。You know。

 either x2 or not x2 is true。Okay， and you can write down a set of rules of inference for this system。

 for taking true statements and deriving other true statements， for example。

 from these two statements we could derive that either x1 or not x1 or x2 or not x2 was true。

if or in fact that even that。Even that this sentence is true okay so you know and you know this will be sound will only prove true things。

 you know it will you know you can also write down a set of inference rules here that are complete okay that will you know every sort of logical so sort of every true bullolean statement。

 you will be able to derive from these axioms right it's you know it may take an exponential number of steps but you know you'll be able to do it right and and it will be。

😊，You know and it will be computable okay and sort of the only problem want unquote is that this is just a very weak language。

 or this is not powerful enough to say things like you know， this this given touring machine halts。

 you know， eventually you in some amount of time right there's just no facility in this language for making statements like that okay。

😊，All right， so how did Garel prove the first incompleteness theorem？Okay， so basically for you know。

 given any formal， you， given any proof system F， he showed how to construct a purely。

 you know arithmetal sentence， so just a purely mathematical statement。

 but whose meaning is you know this statement is not provable in F。Okay， and。So you know。

 there were two sort of technical issues that you know you have to deal with in order to sort of express this statement right。

 the first one is to get rid of the self-reference， okay。

 but we already saw how to do that you know last week。

 you can basically just say the following statement repeated twice the second time in quotes is not provable in F。

The following statement repeated twice， the second time in quotes is not provable enough right so you can use that same trick that we saw before to sort of get rid of the self-reference okay but then you know there's still the bigger problem of you know how do you express the concept of provability right and so you know what we saw with like Tsky's theorem last week right that there is no mathematical you know you know definition like within a formal system。

 there is no mathematical way that you can define the set of true sentences of arithmetic within the system and the reason is that you know if you could do that then you could actually construct the paradox of the liar and you would actually you know the sentence is not true and you would actually get a contradiction okay but now what Gerdel did you know sort of the key innovation here is to shift attention from truth to provability？

And then what he did is he explicitly constructed how you can construct a mathematical definition purely within the system F for what it means for a given statement to be provable in F。

Okay， and。So， you know his original， you know proof for that， you know。

 it took like 30 pages of just like， you know， you know， in retrospect， know looks like， you know。

 like a CS person might look back on and say this was an incredibly inegant hack。

 okay because basically what he had to do is you know。

 he wanted to sort of reason about computer programs。

 you know before the concept of a computer program existed。Okay you know。

 or this is sort of know an anachronistic way of looking at it okay but this is I think this is essentially what he was doing right he so you know like he didn't have the concept of computer programs that just you know read in a sentence which is like a string of bits and do something with that sentence and so what he had to do is just sort of say。

 well look every sentence can be you know you know the set of all the sentences of the proof system F can be placed in one to one correspondence with the positive integers and then you saying like that a given sentence S you is provable in a formal system is just making some arithmetical claim about the integer corresponding to that sentence okay and so basically to do this he had to sort of construct a programming language that just operated directly on integers。

😊，Okay and you know the way that this language worked is you know basically that you use like prime numbers to correspond to the different elements of your statement and then to put them all together you know you multiply them together in some way to get a composite number it's kind of like you know when I was just learning programming like as a kid you know and like I had a friend you know was also you learning programming you know and he was really extremely good at math okay but didnt he had never learned what an array was okay so at one point you know he needed an array although he didn't know the name for it so he just said you know to each thing that could be in my array I'll associate a different prime number you know two。

3 five，7 and so forth and then I you know multipied them all together and this will give me my array and whenever I need to know what's in the array I'll just factor it back into primes。

This is， you know， you know you I don't you know this is not considered good programming practice you know if you had a quantum computer。

 it wouldn't be quite as bad because at least the factoring would be would be more efficient okay but you know but the point is you know it's terrible programming practice。

 but you know it sort of you it works you know so if you don't care about efficiency you know you know or about memory management or whatever it works Okay so this is essentially what Gerdel did。

 he sort of constructed a programming language just you know using like addition and multiplication of positive integers。

😊，Okay， but with the benefit of hindsight， you know we can be sort of much you know。

 and with the notion of a computer program in hand。

 we can be sort of much more elegant in how we talk about these things okay so what we can do is say well look we you know we have assumed you know as conditions you know the theorem that first of all our proof system F is computable and second of all that it。

That is able to talk about things like weather touring machines halt okay so now under those two assumptions。

 you know what is the mathematical meaning of the statement， S is consistent。

 where s is some sorry sorry is provable， where s is some sentence of the formal system S。

 what does it mean to say that S is provable。Means。It means， you know， let's。

It means that a certain touring machine halts， okay， which touring machine？Well。

 there's a touring machine that searches you， that enumerates all of the theorems of F and that halts if it ever finds s。

Okay。So。You know， we've assumed that touch a machine exists， okay。😊。

So you know and we've also assumed that F is powerful enough to talk about such machines and whether they halt okay so which means that you know under those assumptions。

 you know， within F， we can make a statement like M halts， okay。

 which then amounts to saying that S is provable right it's just saying that if I enumerated。

 you know all you know， starting from the axioms of F， all of the possible consequences， you know。

 you know all the possible results of applying the inference rules of F over and over。

 I would eventually hit S。😊，OkaySo this is the point right， provability， you know。

 unlike truth is not some metaphysical statement， right it's just a statement that know you write a program that derives all the consequences of your axioms。

 that program will eventually halt and find the theorem that you want okays so provability is itself a mathematical question。

Okay。That's the key insight。Okay， and so now what do we do， Well， now we just， you know。

 go through the logic， right， and we ask， okay， this this sentence G of F。

 which is called the gidle sentence， is it itself provable in F。All right， well。

 what happens if it's provable anyone？Yeah。Yeah， well， if it's provable， then it's not true。

 all right？You know， it says that it's not provable， so if it's provable。Then G ofF is false， okay。

 so which means that our system has proved a falsehood， right？It's proved something that's not true。

 which means that f is unsound。Okay。Contradicting our starting assumption。

 we can't yet conclude that F is inconsistent。 Okay， we'll get back to that later。All right。

 so what's the alternative？Well， the alternative is that G of F is not provable in F。Right。

 when I say provable， I really mean just provable in F。

 okay that's important because you know the same statement could be provable from one set of axioms。

 but not provable from another set。Okay， but what can we say about GFF's truth if it's not provable enough？

It's true。Okay， which then you know means that we have an example of a true but unprovvable statement。

 okay and since F is sound， you know it can't prove not G of F right because that would be false okay so F proves neither G of F nor not G of F。

 which means that F is incomplete。Okay。So。So that's the first incompleteness theorem。呃。Yeah。

So let me now show you a really， really pretty connection between Gdel's theorem and the unsolvability of the halting problem。

 okay， showing how you know actually once you know the unsolvability of the halting problem。

 then you can actually derive Gdel's theorem from that or the first incompleteness theorem。

 but in a different way than the way that we just did，So how could we know。

 how do you prove that A implies B， where A and B are both impossibility statements？

Anyone want to just answer that general question？What's the first thing we try？Well， yeah。

 I mean we can right but even more basic than that， we take the contrapoitive。

 right we try to show that not B implies not a okay so what we want to do is to show that suppose that we had a sound computable complete proof system that captured arithmetic。

😊，I'll just call that in all us proof system。I would like to conclude from that。

That then we would have a touring machine to solve the halting problem。Okay， that's my claim。

 so given such a powerful proof system， how could we use it to solve the halting problem anyone see that？

😊，Okay， you've got a system which is able to reason express statements about touring machines， right。

 it's everything that it says is true and given any question that you can put to it。

 it gives it either proves that the answer to that question is yes or no。All right。

 are we getting warmer here？Yeah。Okay right so we're given a touring machine。

 we're given an input a description of a touring machine M right the halting problem is to decide let's say whether M halts on a black input right okay but now。

We've assumed that there is a touring machine， all right， let me call it P， I guess。

 that lists all of the theorems of F， and because F is complete， you know。

 at least one of those theorems must be either MHttz or M runs forever。

Otherwise it wouldn't be complete it would fail to decide the question of whether M halts。

 okay so this means like a logical you know you know this symbol means sort of is something is provable from the axioms of P right so it must either be the case that P proves that M Htz or。

That P proves that M loops。Okay， and furthermore， because F is sound， you know。

 whichever one is as soon as you know， we found a proof of either of these。

 we would know that that thing was true。right， whatever F says is true Okay。

 so now you know our algorithm for the halting problem will simply be， you know。

 just enumerate all of the you know the possible theorems of P you know。

 which because F is sorry and enumerate，enumerate all of the theorems of F。

 which because F is computable， we know that there's a program P that does that okay and then eventually we must halt finding either a proof that M halts or else a proof that M runs forever and then we know the answer。

Okay， so， but we already know that the halting problem you know is uncomputable， okay。

 and from that we conclude that this awesome proof system cannot have existed。😊，Sa that。

Okay you know this algorithm is sometimes called the British Museum algorithm because it's just you know like。

 you know， the British Museum is supposed to have like you know like a sample of everything you know I've been there it doesn't really。

 but you know， but it does have a lot of things okay and so you know you just look through every possible proof and dis proof in your formal system okay all right。

 good so。😊，So。So let me actually ask a more refined question。

 which someone asked me after class last time and it's an excellent question you know and this is also one that Touring answered for the first time in his 1936 paper okay。

 you might say this， okay you might say look we know from Gerdel's theorem that there can't be any。

 you know， sort of。I mean， I mean we know from Gerdel's theorem that given any reasonable you know proof system。

 you know to capture arithmetic right， there are going to be statements that that。

Proof system doesn't decide one way or the other right they'll be undecidable okay but you know the examples that Gerdel's theorem produces are pretty damn artificial right you know I mean it's not you know normally when you're doing math like you're not going to run into a sentence like that one by accident okay that you asserts its own unprorovability right it's the kind of thing that you know you're only going to find if you were looking for it okay so maybe you know we can just sort of cut these out you like a cancer just like just cut them out of math and just get rid of them right and so so a very you a nice goal that you might have is you know couldn't we build a machine so let's say a touring machine you know that's our modern definition of of what a machine means okay couldn't we build a touring machine that takes you know written on its tape an encoding of a mathematical statement。

😊，S， and that then sorts s into one of three categories。Okay。

 it tells you whether S is provable in your favorite formal system， like know。

 piano arithmetic or whatever。It tells you that S is disprovable in that formal system。

 or you know we know that there's a third possibility。

 It could tell you that S is a weird girdle sentence。Okay， and is neither provable nor dispvable。

 Okay， but whichever of the three it is， this touring machine will tell you。All right， well。

 unfortunately， and this probably is not going to shock you at this point。

 I claim that this touring machine cannot exist either。Okay。

 you can't even have this three way sorting machine， okay now why can't you， does anyone see why not？

All right。Let let me give you a hint， Does anyone see how if we did have such a。

 you know even this touring machine， then we could use it to solve the halting problem？So yeah。

 it seems like this almost just is the whole thing problem like。If it's a weird go。

Sentence in there obviously is a tu machine that doesn't hold。

Yeah okay so so we're given okay yeah so I think you got the essential point there so we're given as input a description of I keep flipping between m and P but whatever machine and program they're interchangeable so we're given as input a description of a touring machine P right and and the question that we're you know that we want to know the answer to is whether P halts on a blank input or not okay and we need to use this machine to answer that question okay so what do we do well we just ask the machine you know so what about the sentence that says that P halts is that provable disproable or weird girdle okay and then you know we just go through the three possibilities if it's provable that P halts well you know we've assumed that our system is sound right so then okay P holdss that's fine。

In that case we can even confirm it for ourselves if we want by just simulating P until it does halt right if it says that P。

 you know that is disprorovable that P halts will then you since it sound then you P must run forever okay but what if it says that whether P holdss is a weird girdle sentence。

 okay what can we then conclude about the truth of whether P holdss？

This is sort of the key point here。Okay， well， you know， if it says that it is unprovable。

 whether P holds or doesn't hold， then from that very fact of the unprorovability。

 we can conclude that P cannot halt。Okay why yeah， because if it halted。

 we could just observe ited exactly exactly right， because if it halted。

 then surely there would be a proof that it halts， the proof would simply consist of simulating P for a finite number of steps and just you know doing a trace you know step by step by step until you see that it halts that's a finite you so any in other words you have any you know reasonably powerful proof system you know and know really doesn't have to be very powerful anyone worth it salt you know then any time a touring machine halts。

 that system can prove that it halts because you just say well look at the thing you know here' here's the execution trace go watch it you and you see that that it halts after this number of steps okay which means that if a sentence of the form P halts is formally undecidable then the truth must be that P run。

Forever。which is a cool fact right you know and it's not often sort of missed in you know discussions of logic like you know there was a whole novel called you know Uncle Petros and Goldbox conjecture about you know a mathematician who's obsessed with proven goldbox conjecture and at some point he thinks okay well maybe you it's it's just unprorovvable you know it's just independent of the axioms of set theoryory。

 which is you know that's a logical possibility you over any famous unsolved math problem。

 your choice you yeah maybe it could be like the gurdnal sentence。

 you know it could be just independent of set theory， but but if your question。

 you is like goldbox conjecture that is if it can be phrased in terms of you know whether some computer program halts。

 then you know something very cool which is you that if you could ever prove that it was independent of set theory。

 then by that very fact you would have proved that the statement is true。

You would prove that the program does not halt in this case that that yes。

 every even number is expressible as a sum of two primes。All right。So。

So now you know there are two kind of improvements that I want to make to Gerdel's theorem I mean I mean I mean I'm not the one who made them but you know but two improvements that we should make okay the first one is that you know we had to assume that our system was sound okay and that's kind of unsatisfying because as we discussed last week。

 soundness is you know is this meta mathematicalthematical notion right we can't even define within F what it means for F to be sound you know only sort of looking outside of F can we can we even define that oh what would be much you know more satisfyying would be if we could merely assume that F was consistent。

Okay， because consistency， unlike soundness， can be defined purely within F。

 how do you define you know what is the meaning of saying that F is consistent。

 let's say in terms of touring machines。It means that when you take the computer program that just lists all the theorems of F。

 then that computer program never derives a contradiction or never derives both a statement and its negation。

So again， that's just a mathematical claim about the behavior of the computer program that's not any sort of philosophical claim。

😊，That me actually。I can just cross things off to do what I want。 Okay。

 so there's an improvement to a Gerel's theorem called Rosser's theorem from 1936 and。

And it just says that we can weaken soundness to consistency。Okay。

 so you know Gerdle was part of the way there， but the full， you know， you know。

 it took Rosser to sort of complete the argument， okay。

 so no consistent and computable proof system that captures arithmetic can be complete。All right。

 so how do we prove this？Well。It turns out that we need a little a tweak to this girdle sentence G of F okay we have to go back to it and the problem with the girdle sentence is sort of that there's a big asymmetry in it between provability and unpvability right it says that it's not provable but it doesn't say anything about you know that this sentence is not disprorovable right you know and that asymmetry in some senses is the source of the problems okay so you know you could try to say this sentence is neither provable nor disprorovable enough you know。

 but you can try it that doesn't really work either okay and then Rosser sort of figured out the right way to do it which is。

 it's not what I would have guessed immediately， see if you would have guessed it。You say。

 for every proof of this sentence in F， there is a shorter disproof of this sentence in F。

And that's what we'll call the rostersser sentence of F R of F。😊，Okay。

And you know it shouldn't surprise you that once again you can eliminate the self-reference in the sentence using the recursion theorem trick。

 and once again， you can express the concept of you know having a proof。

 having a shorter disproof and so forth in purely mathematical terms。

 you know using these coding tricks， you know， using the fact that F is powerful enough to talk about computer programs and computer programs are powerful enough to enumerate all of the theorems of F。

Okay， so。So now what all that remains is to walk through the logic of this Roer sentence， okay。

 I know it's early in the morning， but you know， are you ready for this because this is a， you know。

This is a good one，So。Let's first， so I claim that assuming only that F is consistent。

 then this R of F can be neither provable nor disprovable in F。Okay， so it must be independent of F。

Okay， and we're only going to use that F is consistent。Okay， so it'll be approved by contradiction。

We just， you know we just have to consider both cases。 first。

 let's suppose that R of F is provable in F。 Okay， then what can we conclude from that？

Well yeah okay， if R ofF is provable then you it's provable and you we've now proved a theorem that says you know there is a shorter dispro of me so now what can you do right well there you know now here's the key point right however long you know is you know so。

So let's say that R ofF is provable by a proof which is K bits long。Okay。Then here's the key point。

 there are only finitely many possible strings that could be the shorter disproof that's being talked about here right。

 you know， we only have to consider strings of k minus1 bits or fewer okay and there's only finitely many of them okay so now what you could do is just enumerate all of those possible strings you know of length less than k and just check whether any of them is a dispro of R of F okay well you know suppose that one of them is then then then what can we conclude。

That yes， the F is then inconsistent。 Okay， but suppose that none of them is， then。

 then what can we conclude。Yeah， then then it also， in fact， in that case。

 it also follows that F is inconsistent， okay， why because you know。

 not only did F sort of say something that was false。

 but it's something that sort of contradicted a finite number of statements that you know we were able to check for ourselves。

Okay， so you know， the only time you've got to worry about like the difference between consistency and soundness is when like。

 you know， you could have a formal system that says something like you know this program halts right and then in fact it never halts。

 but you know， no matter how long you run it， you know， you still have proved that it never。

 you know， you still have proved that it runs forever， so you're never going to catch it in the lie。

Okay you know， so that you worry about okay but here， you know R ofF said something。

 it said that there's a shorter disproof， you know。

 but there were only finitely many cases to check and we check them and none of them was that disproof okay and that amounts to a contradiction' you know that's now you know we can now just write out a finite proof that you know that R ofF you know because presumably F also proves that none of those shorter sentences were dispros because you know that's just a very you know immediately those are just immediately checkable statements okay but because RF also proves those other statements that means that it contradicts itself。

Okay， it says that there's a shorter dispro。 But then for every particular shorter string it affirms that it was not a dispro。

 okay so。Conclusion， F is inconsistent。All right， let's consider the other case。

Suppose that R ofF is disprovable。Okay， then then what can we conclude know。

 then F has proved a theorem that says what？Well， you know it said that F has then proved that there is a proof of R ofF that has no shorter dispro。

Right。You know that's the opposite， not R of F is there exists a proof of this sentence。

 namely of R ofF that has no shorter dispro Okay so now we have a theorem saying that there is a proof you know that has no shorter disproof。

Okay， so now let's think about this， so let's say that， you know。

 but you know we just found a dispro， know， we just assume that there is a disproof of F right。

So let's assume that that dis proof is Kbes law。Okay， and so now， so there's a Kbit disproof。Okay。

But you know there's also a proof that has no shorter you know that has no disproof which is shorter than it Okay so now you know we can ask well well how long is that proof right it says that there is such a proof okay well there's two possibilities the proof could be longer than Kbits but in that case we've just derived a contradiction right because we have this long proof you know you know because you know the shortest proof let's say of R ofF does have a shorter dis proof okay so you know and that's a contradiction that F itself can see the other possibility。

Is that that shortest proof of R ofF is shorter than k bits long okay you know that's the only remaining possibility okay but in this case we can do the same thing that we did in this other case we can just enumerate every possible string of K of k minus1 bits or fewer and just check whether any of them is a proof of R of F okay if any one of them is then we have derived a contradiction because then we have both a proof of R ofF and a dis proof okay so F is inconsistent but if none of these is a is a proof of R ofF then you know you know then F is just you know li to us and we've caught it in the lie okay it said that there was a proof that had no shorter dispro and we checked you know you know if there was such a proof it had to be one of these strings and we checked all of them and none of them was so。

F has contradicted itself so it's inconsistent so we conclude that no consistent complete proof system can capture no complete consistent computable proof system can capture of arithmetic。

😊，Okay。U。All right， but now there's one other improvement that I want to make to Gerirdle's theorem。

 you know， I wrote before the first incomplete in this theorem。You know， but as。

As the name suggests there's also a second one okay so the second incompleteness theorem。

 sort of the starting point of it is you know something that you if you thought about these arguments that we were making here might have seemed a little bit funny to you okay and and that's that well you know we went through this whole argument to say that you know why G of F is you know cannot be provable in F you assuming that F is is sound or whatever or you know why R of F cannot be provable in F assuming that F is consistent okay but wait a minute。

 you in making this whole argument you know didn't we actually prove G of F。😊。

Because we showed that F we showed that G of F can have no proof， but that's exactly what it says。

 so didn't we just prove it， but you're late， but if we did prove it。

 then then we just right back in the contradiction so what gives， what's going on there？Okay well。

 in fact， you know， there's a little subtlety， in fact。

 you know this argument did not quite prove G of F， okay why didn't it prove G of F？Well。

 because you know， in order to derive from this whole argument that G ofF was true。

 we sort I sort of covertly slipped in， you know， the assumption that F is sound。 if F is not sound。

 then it could very well be that。That you know that F is just wrong about something right like it could you know know if F were unsound you know then it perfectly well could prove G of F okay and in fact if F it was inconsistent an inconsistent system prove absolutely anything right so you know once you know you all know this once you have an inconsistency you can derive anything right you know like Btra and Russell's famous you know example was okay you know you know I can derive anything from one plus one equals one and then someone said okay great prove you're the pope so he said I am one。

 the pope is one I and the Poe are one okay so you know so if F was inconsistent then surely F could prove R of F you know could also prove not R of F。

Okay。So it is only the conclusion that we can derive is only a weaker one， which is that F。

 you know in F， it is possible to prove， so let me introduce a notation。

 con of F means that means the statement that says that F is consistent， okay。

 which again is a mathematical statement that you can formalize purely within F。😊。

It just says that a touring machine that looks for a contradiction within all the theorems of F is never going to halt and find one Okay so F proves that if F is consistent then。

Then the Rosser sentence of F holds okay so if you know right so so you know we can go through the argument right if F is consistent。

 then there can be neither a proof of R of F you nor a disproof of R of F right we just saw that before okay but if there's neither a proof nor a disproof。

 then in particular that means R of F is true。Because it says for every proof， this sentence。

 there's a shorter disproof， but if there's no proof and there's no disproof and that's sort of just trivially satisfied。

And furthermore， that entire argument that you know I just made just now can be formalized within F itself。

 okay assuming you know you know that F is powerful enough to be talking about these things in the first place okay so you know which means that F proves that you know that the consistency of F implies the Rosser sentence of F okay and in fact。

 you know F even proves that these two things are equivalent to each other okay I can leave it as an exercise for you to show how you know assuming oh let's just do it right now。

 why is it true that assuming the Rosser sentence of F F must be consistent。Anyone？Well， once again。

 let's take the contrapoitive， Sose that if we' inconsistent。

 then why would the Rosser sentence be false？2。呃嗯嗯。Oh， I'm sorry， I'm sorry， I'm sorry， I'm sorry。

 that doesn't。This should have been G of F， I' sorry I'm sorry that that actually doesn't work that's okay。

All right， you know， and then I would need a modification of it， all right， you know what， forget it。

 let's just do the arrow in one direction。Okay， so F proves that if F is consistent。

 then the Rosser sentence holds。Okay， but now what does this mean about， you know。

 can F prove con of F， suppose we had a proof of F in con of F then what would we also have？

from this， we see that if F were able to prove its own consistency。

 then F could also prove the Rosser sentence， but then that would mean that F was inconsistent。Okay。

 so。So the second incompleteness theorem。It was a statement that。You know if F is consistent。

 you know， and it satisfies with other conditions that it's computable and that it captures arithmetic。

Then F cannot prove his own consistency。Okay， so it's not just that there are these unprovable sentences。

 you know， at least one of the unprovvable sentences is actually quite interesting。

 it's the one that says that the system itself is consistent。Okay。

 and this is a form of Gerdel's theorem that you know you may have seen before that says that you know no powerful enough formal system is able to prove its own consistency Okay。

 so now you know this is。You know， by the way， you know。

 like even if F had proved its own consistency， like it's not clear why you would want to believe it right because you know if you didn't already believe F is consistent well then you know。

 okay right anyone can say they're consistent right but you know。

 but it would be a nice kind of selfreentiality， you know a nice kind of closure if you had a system that was able to prove its own consistency you know and that is part of what Hilbert hoped for in the you know year 1900 and the second incompleteness theorem says that you cannot have that okay。

😊，By the way， ironically， you can have a system that proves its own inconsistency。😊。

That's totally fine。Okay， so。So what's an example of a system that proves its own inconsistency but is okay Well。

 you know， or I should say is consistent， is nevertheless consistent okay well you can take。

Let's just take any formal system F to which Gerdel's theorem applies。

 you know like piano arithmetic or whatever， and now let's just take what I like to call the self hating theory。

 okay， this is F plus an axiom that says F is inconsistent。Okay， so you just add as an axiom that。

 you know there is a proof somewhere of F's inconsistency Okay。

 so this this is you know this is sort of this is a depressed proof system you know。

 it believes that somewhere out there， there is a proof of its own inconsistency even though it's never found one Okay。

 it takes that as an axiom All right so。😊，So I claim that assuming that F is consistent that this enlarged system is also consistent。

 why is that？Can anyone say why this yes？The accident。Exactly。

 because if you could derive an inconsistency in this system， then from that。

 you know that would amount to a proof of Khannf。RightYou know we would have assumed not Conf and we would have gotten a contradiction so that would have meant that Conf was true。

 but then F would have proved its own consistency and the second incompleteness theorem says that it can't do that if it's consistent okay so which means that the system F plus not Conf you know has to be consistent okay so this is you I feel like there's a moral lesson in here okay you know like the the ones who boast of their own consistency you or the ones who have nothing to boast of and in fact。

 the only belief about your own consistency that can keep you consistent is that you're not consistent。

对。So。Good。Okay， so just a few words about how this plays out in practice。

 so I mentioned before that you know probably the two most popular proof systems know that they're actually are the sort of you know or have been the foundation of math for more than a century are piano arithmetic which is a system for reasoning about you know positive integers。

 basically you know using first order logic and then Zf set theory， which is a more powerful system。

 which is able to reason about sets， okay including infinite sets。

 you know you know different sizes of infinite sets and so forth which would much larger objects than piano arithmetic knows how to talk about okay now。

The second incompleteness theorem says that proof no consistent proof system can prove its own consistency if it's above a threshold of power which all of these systems are above so for example。

 piano arithmetic cannot prove its own consistency on the other hand。

 there are axioms that we could add to piano arithmetic such that we could prove that PA is consistent what's a more powerful what's a way that we could strengthen PA so that con PA would be a theorem。

anyoneone have a really， really stupid way to do it， really naive way to do it？

How about if we just tackle on conPA as an axiom？Okay， you can always do that。

You could always just take the system piano arithmetic plus。

I'm just going to assume as an axiom that piano arithmetic is consistent， Okay， now， you know。

 unlike what we did here， this doesn't create a contradiction because it's not that piano arithmetic has proved。

Its own consistency， it's just that we've tacked on the consistency is an additional axiom okay that doesn't lead to any contradiction you know necessarily。

 you know and you know in this system you know whereas by definition is able to prove that PA is consistent okay that's one of its axioms。

 why have we not now contradicted the second incompleness theorem why is this system not now just proven its own consistency in violation of girdle。

Well， not actually， this system as far as anyone knows is perfectly consistent。Consistent。

 even sound， you know， in fact， if you believe piano arithmetic。

 presumably you also believe piano arithmetic is consistent and therefore you also believe in the truth。

 the soundness of this enlarged system， it just you believe piano arithmetic is sound and consistent and all that then you you have to believe in this but why does this system not prove its own consistency in violation of Gertel's theorem。

😊，Well， it's certainly incomplete right okay， but the second incompleteness theorem said something more specific。

 it said that no you know none of these systems can prove their own consistency I'm asking why does this not prove his own consistency yeah。

😊，Yeah。Exactly， that's exactly it This system proves the consistency of piano arithmetic。

 but that is not the same as proving the consistency of itself， okay。

 because itself is no longer piano arithmetic itself is now an enlar system PA plus con PA。😊。

Okay you know， and that is a more powerful system okay if you wanted to you know you know so this system is able to prove the consistency of something weaker than itself namely PA and that's totally fine。

 there's no contradiction with gidle there right a system can prove the consistency of a weaker system you know you know that often happens。

 okay just it can't prove its own consistency so if we wanted to know that this system was consistent then you know what new axiom would we have to add。

😊，Well。We could always just add on another axiom saying。Well， this system was consistent too， okay。

 you know we could say。PA plus you know the axiom of PA's consistency gives rise to a consistent system all right well you know now this system can prove the consistency of PA plus con PA okay it still can't prove its own consistency right you then have to add on the axiom con of PA plus con PA plus con PA plus conPA okay and so forth so the picture that gidel's theorem gives you is an infinite hierarchy of more and more powerful formal systems where each system in the hierarchy is able to prove the consistency of all of the systems lower in the hierarchy than itself okay of all the weaker systems but it cannot prove its own consistency or of course the consistency of any of the higher systems in the hierarchy。

Okay so these are called iterated consistency statements right so so this is you know the picture that Gerd's Theorem you know gives you right it's not that you know like that there you know statements that have to be you know forever unprorovable like no matter what axioms you add in fact given any you know statement of your choice。

 you know there's some axiom that you could add that would decide that statement。

 if nothing else the statement itself or it's negation okay but it's saying that no one proof system is going to be able to capture all of mathematical truth you're always there's always going to be something additional that you have to add on and then even after you've added it then there' theres something additional that you would have to add on you know again you know yeah。

Possibility of just。systemytem to be slightly differently so that it's easy to prove different things。

What do you mean？Incurrent in it so smooth。Yes it can prove a certain percent。

There's surface savings that can't。Yeah right， and then you make another one like G or something。

I can't prove those statements， but I can't prove other statements that are。Yes。

 you know you can have like multiple you know incomparable systems right you can have like two systems where each one can prove statements that the other one can't prove okay on the other hand if you have like one system that you know that proves like the consistency of a different system right then you know then in some sense you know like if a proves that B is consistent right then there's a then there's some sense in which a is like at least as powerful as B like a you know sort of knows everything B knows。

 it's not literally that a can prove everything that B can prove but sort of a can mimic everything that B can do。

Okay， so。So。Yeah okay， so so now another thing that's true is that if you're in set theory。

 then in fact you can quite easily prove the consistency of piano arithmetic。

 okay a way you can do that so know like in order to show that set of axioms is consistent where it always suffices to just give any example of you an object that satisfies all of those axioms we call that a model of the axioms。

 in fact that's what it means for you well Gardle proved another thing called the completeness theorem which was the incompleteness theorem was his PhD thesis。

 the completeness theorem was his master's thesis it was the warmup okay then the completeness theorem basically says that a set of axioms is in first order logic is consistent meaning cannot prove a contradiction。

 if and only if that set of axioms has a model meaning。

Like there is actually an object that satisfies all those axioms and so to prove something is consistent。

 it's a faces to give a model know and now a model of piano arithmetic is the set of all the positive integers you not surprising that's what they're supposed to be talking about so not surprising that they would satisfy the axioms okay and in Zf because Zf is able to construct infinite sets it's able to just construct the set of explicitly the set of all the positive integers and then you just check that that set satisfies all of the axioms of piano arithmetic and then it follows that piano arithmetic has a model and therefore it's consistent you can't carry out that proof in piano arithmetic because piano arithmetic is not able to talk about infinite objects like the set of all integers know it's only able to talk about this or that integer。

😊，you know， integer X， integer y and so forth Okay， so PA cannot prove its own consistency。

 but Zf can prove PA's consistency Okay， can Zf prove Zf's consistency？Well。

 you know we know the answer from Gerdel's second in completeness theorem no it cannot okay there are more powerful set theories that can prove the consistency of Zf set theory okay basically what you can do is you can postly what's called a large cardinal okay when set theorists say large they really mean large okay what is large mean here it means larger than any infinity than all the infinities that could be defined in Zf set theory okay that's their definition of large okay。

😊，What。No it's not， no it's not， you can you know， it's not an infinity larger than all infinities。

 it's just an infinity larger than all infinities that are definable in ZF。Okay， so， you know。

 of course， this infinity is not itself definable in ZF。Okay， but fine。

 we can have a more powerful system where we， you know。

 Zf plus large cardinal axiom where we postulate that there is an infinity larger than anything definable in ZF right。

 and then in that new you know more powerful system， Zf plus the large cardinal axiom。

We can actually prove the consistency of Zf。Because using that gigantic you know bigger than ZF infinity。

 we can construct a model for ZF you know that has all of the infinities that ever occur in ZF。

 and then that proves ZF is consistent of course this system can't prove its own consistency you know if you want this。

 you know if you want to know that this is consistent。

 you need to postulate an even larger cardinal okay you know extra large cardinal okay and so forth。

😊，All right。So in the。Remaining five or  ten0 minutes。

I want to do sort of our last topic on logic and this will be a sort of a very。

 very nice transition into complexity theory， which will be our next unit okay and this is a kmorov complexity okay and this is sort of a beautiful notion that was invented in the 1960s and that really sort of you know helps you know is another way of making quantitative you know you know these notions of computability okay by the way。

you know we already saw another way of making these concepts quantitative which was the busy beaver numbers right you know so on your third piece set you're going to have a really fun problem I think which to show that once the busy beaver numbers get large enough once they exceed as some finite value then the values of know busy beaver of n。

 you know whatever the value is it's no longer provable in any you standard system of set theory you know that's how big they are okay you know now we don't know like know a concrete bound on know the value of the least value of n for which busy beaver of n is independent of set theory okay like certainly it's more than four because we know the first four values but it's probably a lot less than a million or something okay Adam your TaA is working on a project right now。

Get the first concrete bound on that end， which I think is a fun thing to do Okay I'm not sure if he agrees。

So okay， but now you know I'm going to talk about another way of making sort of computability theory quantitative and this is Kmorov complexity okay and what we do here is。

😊，Basically， you know if I'm giving a string X。Let's say a string of n bits。

 okay the kmogorov complexity of X is basically just the length of the shortest computer program whose output is x。

嗯。So in other words， it's the number of bits in the shortest computer program。

 P such that when you run P on an empty input， then P halts and outputs the string X。

Okay now you know there is a question here okay you know length of the shortest program that that's great。

 you know well which programming language are we talking about right you know the length of the shortest C program might be different than the length of the shortest you know hasskell program right you if I wrote if I defined a programming language that just had like a command print war and peace you know and you just you know call that and it just prints the complete text of war and peace right then in that programming language war and peace has a really low kmogra of complexity right but you know but it would have a much higher complexity in a language that did not include that command okay so so what makes you know this notion of kmogra of complexity sort of sensible is。

😊，A key result called the invariance theorem， which you're going to prove on PSAT3。

And basically what the invariance theorem。Says that for any two programming languages， A and B。

 there exists some constant C of AB， you know， depending only on the programming languages such that for every string x。

 the length of the shortest program in A that outputs X differs from the length of the shortest program in B that outputs x by at most C of AB。

Okay， so which means that sort of， yes， the choice of programming language can， you know。

 change Komogra complexity by an additive constant factor by an additive constant depending on your choice of programming language。

 but is not going to change it by more than that。Okay， and so you'll see the。

The reason in your on the PAT。佢哋见级会揿米。themI'll see you a couple examples。Perphone。

Let's say that I had a string of just n zero what does anyone think is its comogra of complexity you know roughly again。

 I don't care about like additive constants because you know how does it grow as a function event like what is a short computer program then you could think of writing that would just print n zeros or you know how long would that program have to be？

Yeah， it would have to be about log n bits long right because it basically just have to say for I equals one to n print zero and you know the length of that program asymptotically the limit is n gets larger it's just going to be dominated by the number of bits needed to specify n itself right you know the for I equals you know print zero that's just constant you know that's just a constant amount of overhead so we can say。

But that first time， I don't know。You know this string has low commmogra of complexity or in other words。

 you know we could say this string is highly compressible， okay。

 it's an end bit string but it can be fully described by giving a computer program to output it which is only about log n bits long right namely a program that just says print n zeros okay so we could say you know on this basis the string of all zeros is a highly compressible string。

Over。And this is meant to be a suggestive because in some sense。

 you know what kmograph complexity is， what it's trying to capture is what is the ultimate theoretical limit of data compression。

Okay， it's saying， you know， you know， if you're allowed to use any kind of computer program you want you know to compress X how you know how well can you compress it Okay。

 you know it's the one caveat that the decompression program has to be included as part of your itself has to be included as part of the file sites Okay now what if X is a random string so what if I just pick a completely random string of n bits what will its comegra complexity be roughly most of the time about N so so I claim。

RightThat。I seeBut for most， you know， n bitch strings X。

Their kmogra of complexity is pretty close to N okay， you know， this requires a formal proof。

 but it's you basically just saying you know a random file cannot be compressed。

Okay you know this is a you know principle of data compression that some of you might know right there was a company when I went back when I was in grad school that was like got in the news and on slashshot and stuff for claiming that they could compress a random file you know that had an amazing compression program that could compress absolutely anything and you know and I read an interview with the founder of the company you know where they were asking all these you questions like was but what do you say that these experts didn't validate your technology and blah。

 blah， blah， blah， blah and then finally know after a long interview like the interviewer finally said listen you could compress a random file and why don't you just take the result of the compression and feed it back into your program and just feed it back and back until you would compress any file to nothing and the guys that say know hey that's a trick question。

So all right so you know but that is a proof that you know there must be endbit strings whose combboography complexity is at least that right you know so you know there cannot be a perfect form of compression it would be great if we could at least know which strings or depress you know know the combboography complexity strings fortunate on Thursday we will see that that too oncomputable problem and the proof will involve yet another logical trying get level be treated and then we'll start on complexity which last time didn't notice this bug。

It only gets the finger search bound。