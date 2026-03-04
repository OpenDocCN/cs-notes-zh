# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p08 P8 mar05 -BV1Dao8YQEEn_p8-

Right。Put it right in the。All right， well， I'm extremely sorry to everyone。

I had a little emergency to deal with it him。U。Let's see。

 so last time Robin told you about computability。So about reucibility。😊。

A concept of a touring degree。😊，Ithich is like a set of all of the languages that are interreducible to one another。

Let's see。Recognizable languages， you know ones for which there's a touring machine that will halt and accept if the answer is yes。

 but if the answer is no， if your string is not in the language， then it might run forever。

So problems you know that are touring equivalent to the halting problem， okay。

 and there are some very non-obous examples of such problems。

 so you know the solve you know I give you an equation and I ask you does it have an integer solution or not。

 right I mean people this was another one of Hilbert's problems but it was shown you in 1970。

 finally that for any touring machine， for any computer program。

 really it is possible to construct an equation that has an integer solution if and only if the touring machine holds。

Whi is a very cool fact。So。By the way。You know， we started the whole。

Discussion of computability by talking about the Hilbert's Enshidings problem right which is just is there a sort of general purpose way to automate mathematics is there a machine where you you could feed it any mathematical statement and it will just tell you whether it's true or false okay so what's you know the answer that we get from this is no because you know okay I give you an equation。

 does it have an integer solution or not， that's certainly that sounds like a mathematical question okay but you know that already can you be at least as hard as the halting problem。

Okay。Okay。And then。Robin also told you about you that the halting problem is by no means the hardest problem okay that you can have。

 in fact， given any language whatsoever， it is possible to define an even harder language and what do we mean by even harder know if something's already oncomputable isn't that hard enough but we mean that even if so given any language L。

 you can define another language where even if you had an oracle for L。

 the new language would still be uncomputable and how do we define that well。

 we can just consider the halting problem for touring machines that have oracles for L？Okay。

 so you can just sort of repeat everything you know just another level up okay and you know exactly the same argument that we already saw that told us why the halting problem is undecidable by a normal touring machine will also tell you why the halting problem for touring machines with L oracles is undecidable by a touring machine with an L oracle okay know so no matter how powerful you are。

 you still can't solve your own halting problem okay it's one thing you can't do。😊，All right， so so。

So this concept of an oracle， you know， which we use in reducing one problem to another one or sort of。

 you know seeing like what is the structure of the different problems。

 how do they relate to each other， you know， and this is a concept that will show up again and again in the course。

Okay。U。So。So the touring degrees that we've seen are there's the touring degree of all of the computable languages。

 and that's at the very bottom。Computability theorists actually call it zero okay and then there's the touring degree of everything that's equivalent to the halting problem which includes you know a lot of interesting mathematical questions。

 you know solvability of equations， this matrix mortality problem Robin also showed you okay and then。

😊，You can keep going up higher and higher， you know the super hot， degree， you know super duper halt。

 you know super duper， pooper halt， whatever， so you know now you know you the I'm not sure if Robin told you this you know one of the first questions you know like a mathematician you know I'd ask looking at this picture is well you know great so you know is there anything in between this and this okay so。

You know， just like when we saw you know the infinity of the integers and then the even greater infinity of the real numbers。

 you know I asked， okay， is there anything in between and we saw in that case that was a big open problem called the continuum hypothesis and the answer turns out to be well in some sense there is no answer okay。

 either answer you want is you know equally consistent with the axioms of theory。this。

 but in the case of computable versus the halting problem。😊，So。

The question of whether there's any touring degree in between the two was called a post problem。

 a mill post was actually a high school teacher in New York who invented came up with computability theory basically independently of touring and church this is true so you know and he first raised this question and was unsolved until the '50s and。

Finally， Queenie in post， he and Steve Queeny solved it。And then there was a。

If you so Queenian Post showed that yes， yes， there are such touring degrees in between。

 and then Friedberg and Muchnick showed that you can even get recognizable languages that are in between okay。

So what exactly do we mean by in between， right， we mean a language L。

Which is touring reducible to the halting problem。which is not computable。

 so we could phrase that by saying that。U。Sorry， L is not touring reducible to zero。

 that's just another way of saying that it's not computable and what would be the third requirement？

Yeah。Excuse me。Okay， well， we want that the whole thing problem is not touring reducible to it。Right。

So it's it's not just you know so it's genuinely intermediate okay you can get that via you know but it's via a very complicated construction where you basically define the language stage by stage by like killing out every possible touring machine that could compute it you know it's a diagonalization as we call it killing out every possible reduction that could reduce the halting machine to it and so this is not a problem that you're likely to encounter in practice and you know since then computability theorists have found that you know there're actually infinitely many touring degrees in between computable and the halting problem you know and there's a lattice you know like multiple ones that are incomparable to each other so meaning there's A and B where if you had an oracle for A it still doesn't let you solve B。

 but if you had an oracle for B， it still doesn't let you solve a you can have that and you can have you know。

Structure that's been sort of studied in more detail than you can possibly imagine and yes。

 there are。There're also touring degrees that are not touring reducible to the halting problem at all or to any of these problems up here that are just off to the side somewhere and in some sense most touring degrees or like that because there's an uncountable infinity of touring degrees。

 most of them are just like you know if you just defined a language completely at random by just flipping a coin infinity times。

 you know that would probably just give you， you know。

 and then you took the set of all the languages that are touring equivalent to that language。

 that would be another touring degrees。Okay。So。Okay。

 so what's on the agenda for today so the first thing I want to do is。

Tell you about the technique of dovetailing， which is a very useful technique in computability。

 for example， for showing things are equivalent to the halting problem。

 and then we're going to talk about girdle's incompleteness theorem。😊，All right。So。So all right。

 so so you saw on Tuesday that you can give reductions you know to show other problems or equivalent or touring equivalent to the halting problem okay like for example。

 you know the halting problem for touring machines to take input is equivalent to the halting problem for touring machines that don't take input。

 you know that's a very simple example， or you know the halting problem for two tape touring machines is equivalent to the halting problem for one tape touring machines。

 right you can if you had an oracle for one， you could use it to solve the other okay so here you know let me give you a slightly less obvious example。

Okay， so let's consider the language that consists of all descriptions of touring machines。

 for which there is an input that causes them to halt。Okay。

So all the throwinguring machines that haul on some input。So。嗯。

So now we would like to understand this language， it shouldn't surprise us much if it's that this language is uncomputable。

So so I claim that the halting problem is reducible to L， how do we do that。

 let's say that I've got a touring machine and I just want to know。

 all I want to know is just does it halt on a blank input， okay， you know。

 but now I've got an oracle for deciding this L， how do I reduce the one to the other？Anyone。いや。嗯哼。😊。

嗯哼。😊，200块。Perfect yeah， you can just design a so given you know a touring machine M let's say for what you want to know whether it halts or not on a blank input。

 so now just design modify it to get a new touring machine say M prime that when you run it it just deletes its input you know' just you know wipes you know wipes the board clean okay and then starts running M you know doing whatever M would do from that point forward all right easy all right so now you know a little less obvious is the the other direction so。

So if we had an oracle for the ordinary halting problem， then could we decide L？Okay。

 so the question here is， you know， you've got like you know， you've got this program。

 you want to know whether there's any input that causes it to halt， right， but now you know。

 can you design， say， just a single touring machine， you know， like with no input， which halts。

 if and only if there exists in input that causes M to halt？Can anyone think of how to do that？Yeah。

You can make it like go for every single possible。Yeah， and you know in some sense。

 you know yeah that's on the right track we got to be a little careful about how we do it right you know so the issue is you know you know we would like to say is just like try the first input。

 see know see if it runs wherever it halts， try the second input you know try the third input and so forth and then you know see if we ever find an input where it halts and if we do then halt the problem is that you know just for each individual input just deciding whether it halts already。

 you know already require solving the halting problem just for each individual stage so then what we're really asking for you know if we want to just do this over all inputs is not to solve the halting problem for an ordinary touring machine but to solve the halting problem for a touring machine with a halt oracle you see there's like another there's like a second layer in here and。

You know and we've seen that the halting problem for touring machines with halt oracles is actually harder than the halting problem。

 that's the super halt problem okay so if we just do it like that it's not going to work so here's a picture to have in mind so imagine that we just listed all the possible inputs。

😊，Okay， and here's like the amount of time that they run for， you know。

 the amount of time that M runs for if you feed these inputs to M， okay。

knowSo for a whole bunch of them， you know， M runs forever， okay， at least for a really。

 really long time， you know， it runs forever， okay， but then there you， there's one input。

 let's say somewhere where it halts。Okay。U。So you know we can't， you know。

 just you if we try to like simulate for the earlier inputs， you know until they halt。

 you know we're just going to get stuck there forever and we're never even going to find out that there's this later input where the thing does halt okay。

So the general way to deal with this sort of problem is was a useful technique called dovetailing。

 you know， it's almost too obvious to need a name， okay， but it's。But I'll show you， you know。

 it hasn't you know there's a nice picture， remember， okay， and the basic idea。U。

Is this that you first simulate running M on the first input for one step。Okay。Well。

 it hasn't halted， okay， then you know you run M on the first two inputs for two steps each， okay。

 then you run it on the first three inputs for three steps each right and so on。Okay。

 so you know this is what some people apparently thought that this looks like a dovetail。

 okay so you keep going like this until up， you know lo and behold， after a finite amount of time。

 you know， you found this that。It's actually kind of similar to how one shows that the set of rational numbers is countable。

😊，Okay。All right， so now let me do a still more interesting example。So all right。

 so the conclusion is that， know indeed this language is touring equivalent to the halting problem。😊。

Okay。Okay，Let's consider the language that consists of all descriptions of touring machines for which you know they let's say touring machines with an oracle。

 you know， so that can read an oracle， which you one way to think of an oracle is just as an infinitely long input it's an input that never ends because you know it has a bit for every possible question that you could ask it so so now we consider the。

😊，The language consisting of all programs for which there is some oracle that causes them to run forever。

Okay， that sounds like a weird thing to wrap your head around， right？😊，All right。Once again。

 you know。I claim that this language is uncomputable， can anyone tell me why？

If we had an oracle for this language， how could we solve the whole thing problem？Well。

 the ordinary halt thing problem。Yeah。嗯。Yeah I mean I mean。

 you know look the ordinary halt problem is for touring machines that don't even access the you know an oracle at all right I doesn't say anything about it so you know so you have some M that never queries an Oracle right and then you know you just you know if it never even uses the oracle then it's going to be an L if it only if it runs forever so that's already the halt problem okay so all right so that's easy。

So once again， the more interesting direction is， yeah。Yeah， you're right， it is。

 so it's very convenient for us that we're talking here about touring reucibility。

 right where you know if you have an oracle， you could always just get whatever answer it spits out and then just negate it。

right， so actually you raise a good point which is that if we were talking about many one reducibility which Robin also defined on Tuesday。

 then this would not be true okay a halt is not many one reducible to L because there's no direct mapping from yes instances to yes instances and from no instances to no instances but there is a mapping from yes instances to no instances and from no instances to yes instances and that's enough for it to be touring reducible。

😊，Okay good， so all right， so how about you know how on earth， you know now here's the question。

 we have a touring machine that you thatqueries some oracle， you。

 and now I would like to design a new machine， say M prime， you know not involving any oracle。

 okay which runs forever and say if and only if there exists some oracle that causes M to run forever。

😊，Okay。So how could I do that？Mmh。Well。So let's imagine that we've got。You know。

 our oracle touring machine。 So you can think of that as just a two tape touring machine。

You know that's got some memory that it you know uses to compute with and it also has this oracle tape a let me just you know think think of a as infinite in one direction so it's just an infinite string you can think of an oracle as really just an infinite string of zeros and ones that you have that you're able to access at any bit that you like right so think of you can think of the oracleles as just an infinite set of zeros and ones that are you know written onto this tape right and you know containing the the infinite wisdom of the oracle you can consult as needed right and you know these are。

These are its answers to every possible yes or no question you might want to ask it listed in mexiographic order and when the machine can answer any question by just moving to the appropriate place on the oracle tip right so the machine。

Starts out in the leftmost position let's say on the tape you know and as far as the machine is concerned right you know it doesn't know yet what the oracle is going to say that that's why it needs an Oracle say you know it could be a zero and it could be a one right and the question that interests us is going to be whether there exists any way of setting the zeros and ones on this oracle tape that causes the machine to run forever so。

嗯。So how are we going to deal with this， given that now we're constructing a machine that has no oracle to help it。

 and we just need our new machine to run forever， if it onlyly if there is any way of setting this oracle tape that causes M to run forever。

Okay， so what can we do given that we don't know the first bit yeah？Just try it。Creing different。

Those and even。Exactly， we can just try them both， you know， we can branch okay。

So let's say that we're going to sort of create a giant tree of possibilities。

 where going down the tree， these are the time steps of M of our original touring machine， okay。

 but now any time M reads a new bit of the oracle string that it hasn't read before， you know。

 then we're going to deal with that by just branching on both possibilities。

 okay we're going to you know see what happens if that bit was zero and we're going to see what happens if it's one。

 okay， so there are some steps。Where M is not reading the oracle at all。

 or it's only rereading bits that it already read and know so at those steps we just go straight down。

 okay， but there can be other steps when M does query a new bit and then we branch on you know whether that bit is a zero or a1 okay and。

And now you know it's very you know as we simulate this process， it's very。

 very important that we don't get stuck you know， in any one branch forever。

 does anyone know a technique for searching trees that will let us avoid that problem？BFS， yes。

 breathth first search Okay so we definitely don't want to do DFS Okay because you know because because the D is infinite here could be infinite right So we want to do breadth first search of this tree right so we first you know kind of like dovetail。

 we first run the tree one level down and then we run the whole tree two levels down three levels down and so forth。

 we search the tree like that Okay and now as we go on， some of these paths may terminate well。

 you know， meaning that that at this point， the touring machine halts right so so now it's saying that that if we know we had。

This now is saying that if the first three bits on the oracle tape were zeros。

 then the machine halts all right so so now we've learned something。

 we've learned that if you want M to run forever then the first three bits of the oracle tape cannot be zero okay but you know we want to know is's just is there any way to set the whole tape such that the machine runs forever so we've got to keep going you know we've got to look at the other branches right and so so other branches may continue for a while you know some of them will eventually stop。

But。You know， some of them will keep going down okay， and you know。

 maybe at some point every branch that we've explored， you know。

 every single branch is terminated at that point， what can we say？Yeah， at this point。

 we can say that there is no oracle that causes M to run forever right at this point we're done Okay。

 but now consider the other direction， suppose that this process never halts， okay。

 then what can we conclude yeah。Yeah， sure input。Oh， that's a very good question。

 so I'm just assuming here that the input is empty。Okay， good。

 so we'll assume that the input is the zero string because I'm just worrying about the oracle here。

So all right。😊，So suppose that this process continues forever， if it continues forever。

 then that means that the tree must be infinite， right okay。

 and now there's a slight subtlety which which you could miss。

 you could miss if you blink the subtlety is， well just because the tree is infinite， know。

 does that mean that it must have an infinite path。Okay， well， here's a potential counter example。😊。

Here is an infinite tree but which has no infinite path。Exact just have。

One root vertex and it's got infinitely many children， but nevertheless， I claim that this tree。

 if it's infinite， then it's got to have an infinite path， what's the difference between the trees？😊。

finite degree。 Yeah， so the general statement that we want here。It's called coniglema。

And it says that every infinite tree with finite degree。

I woulds say where every node has only finitely many children。Has。At least one infinite path。Pray。

Can anyone see how he might prove congslemma？Why is it true？yeah。Yep。Yeah。

 that's certainly the intuition right you so if we want to be a little more explicit right we'd like let's say a procedure for finding the infin so we should say that this tree has an infinite path great。

 how do we find that infinite path yeah？😊，Every。Yep。Yeah。What？It yeah， yeah。

 no that's exactly the intuition right you know if we want to be a little more formal， yeah。

 we can argue by induction， we can say look， because the tree is infinite。

 no because the root by assumption has only finitely many， you know。😊，Subtes， you know。

 infinite many children， therefore， at least one of these subtes must itself be infinite。

Otherwise the tree will be finite right so let's suppose this subtree is infinite okay so then traverse this path okay you know go go down to this one all right now you know repeat here right you know because this subt is infinite at least one of its subtes must be infinite right so then suppose this one is infinite then go down here right and so you'll always be you know maintaining that you've got infinite possibilities to your future no matter which way you go so you can continue for infinite time okay so so the tree has an infinite path which in this context means a setting of zeros and ones for the oracle string that causes the touring machine to run forever。

😊， that must exist if our program that we've constructed doesn't halt。Okay， good。So。All right。

 you ready for Gerdel's theorem？诶。All right， so Gerdel's theorem actually predates the unsolvability of the halting problem by five years。

 you know and it was a direct inspiration to touring。

 so but well and the two are closely related to each other and we'll see exactly how they're related but the starting point for Gerirdel's theorem is not computability but it logic right and it's sort of for paradoxes of logic that go all the way back to the ancient Greeks。

You've probably heard this。You know， some people say that the。

The paradox of the liar is that a Cretan says all Cretans are liars and then you know should you believe them or not。

 I claim that this is actually not a paradox at all okay。

 why is there no paradox if accretan says that all Cretans are liars？What？Anyway？Yeah， you know。

 I mean， it could be that well look， yeah。Yeah， you know， and well he's you know， okay， yeah。

 there are several ways to do it right， but let's let's even suppose that he said all Cretans lie all the time。

 claim that there's still no necessary contradiction here yeah。Yeah。

 the negation is that some tell the truth， right？Yeah。Yeah。Exactly。Exactly， that's exactly right。

 yeah， it could just be that some cretans are liars， you know including that one， okay。

 the one who you're talking to， right you know and then you know。

 and then he you know he is indeed lying and you know so there's no problem okay so let's do a better example。

😊，Okay， so， you know， a pure form of the problem。Comes in the famous sentence this sentence is false right and you you know you know okay the sentence is false then you know that means it's false that it's false right but that means that it's true but if it's true then it's false know and so forth you know so so now the question that we face is why did my writing the sentence on the board not just cause the universe to explode you or why did this not you know why did this not create a contradiction in mathematics the challenge here is to know explain sort of what is it that sort of rules this sentence out as an illegitimate sentence like what are the rules for constructing sentence or let's say mathematical sentences or something that will prevent us from constructing this。

😊，Sentence because if we did construct it， then it's clear that we would have a problem。

Okay so that's sort of the way I want to frame the issue of what it looks like a perfectly grammatical sentence。

 but there's got to be something wrong with it。Yeah。Yeah。

 well okay so a lot of you know people you know like the first sort of instinct we have is that you know that well just that the fact that the sentence is self referential。

 right， you could say maybe we should just disallow sentences that talk about themselves because that just seems like a recipe for disaster okay you know。

All right， but very interestingly， and this is going to be important for Gerdel's theorem。

 claim that that doesn't actually solve the problem at all。 Okay， let me show you why。嗯。Right。

 actually， you know， this will involve a little digression， does anyone， I mean。

 probably some of you have seen this before， how do you write a program that when you run it its output is itself as its own source code？

嗯。😊，Yeah。I this language。All right。嗯hu。All right。All right， good。 So in that language。

 it's quite easy。 yeah， so let's say that you're using Java or you're using you know， you know。

 I've given a programming language， it doesn't have this functionality built into it。

 I claim you can still do it。😊，know telling me in pseudo code， how to， okay and by the way。

 no fair to just have a blank program。There was actually in this international obfuscated C code contest。

 they had like a competition for years to write the smallest C program that prints its own code。

 you know whose output is itself and then there's one that's only like 31 characters long。

 I think you can do like ridiculous stuff in C okay but then one year someone just submitted a blank file。

 which is technically not a C program but some C compilers will compile it to a program that does nothing okay。

😊，So at that point they ended the contest， I think， so all right。

 but a non empty program that prints its own code。😊，嗯。So basically。

 what you want to do is in whatever programming language you want。You know。

 sort of do the following type of thing， write a program that basically says。

 print the following thing twice the second time with quotes。And then you have end quotes。

Print the following twice。The second time in quotes。Okay。

Everyone see that that's a program that prints itself。Yeah， okay。

 it's apparently the name for such a thing is called aqui。Okay。And in recitation tomorrow。

 you may talk about there's a generalization of this called the recursion theorem。

 which is a fancy name for a very， very simple observation。

 it basically says that any whenever you are writing a computer program。

 you can always assume if you like that that program has access to its own code。😊，you know。

 which like it sounds like maybe you know a paradox if you think about it right because you know if this program is accessing its own code right then what it does depends on its code。

 but I'm writing the code right now， so I was like what you know。

 but you know you can always you know get around this problem with this sort of trick you know you basically you have a program that sort of you know the code of the program you know actually contains two copies of the code。

 you know and one of them is in quotes， okay yeah？😊，There should be period。Yes， thank you。Excellent。

 excellent， excellent catch， okay， if good。😊，Now it works。Right， good， all right， all right， awesome。

😊，So you know， you know but this has some sort of looping you know implications right like you know you might think okay let's say you you know there's some artificially intelligent robot right and you know you know and you know it's a complete code right and so you might think that you know you could okay so just now you know you want to like tell it you know it's behavioral you want to go go to that robot and say you you know since you're a robot I can predict what you're going to do right you know I know whether you're going to you know walk you know out of the room in a minute okay and the robot says well you know that may be you know because it's a smart robot okay it says that that may be true you know but you better not tell me the prediction because know whatever you tell me I'll just do the opposite of whatever you say you know you tell me I'm going to walk out of the room and then I won't。

 you tell me that I won't then I will okay but。What the recursion theorem says essentially is that you could give the robot your prediction in the form of a program you could say what I predict that you're going to do is well whatever this piece of code that I'm going to hand to you。

 whatever output it produces when run， and of course your act of handing that code to the robot will change the robot's behavior because the robot can now look at the code and can do something having looked at it。

 but even then even after the robot has looked at the code that you've handed it。

 your prediction as embodied in that code will still be correct。Okay， it's like the you know。

 if you see， you know， I guess you know theyre like this is the way Greek tragedies work right where you you know the hero you know you know or Edipus you know like you know finds out know the prophecy that he's going to you know kill his father or you whatever it is。

 I don't really know you know no Greek tragedies okay but you know。

 and then he does everything he can to try to avoid that coming true。

 but then always his attempts to avoid it just cause it to come true， right it's kind of like that。

 okay you know you can。You know， you can give the robot a piece of code know that the robot can take his input process。

 you know， do whatever it wants to to try to avoid doing what that code says， but after all。

 it can't I I mean it could just just simulate the code forever。

 but then that's just an infinite loop if it ever halts then it will turn out that that running the code would run for a would involve running for a longer time then the robot ran for and it would have just output the correct prediction of what the robot actually did do when it halted。

Okay。So that's the recursion theorem。😊，So all right。

 so what does this have to do with this sentence as false， well。

 what could we do if we wanted to eliminate the self referentiality from this sentence？😊，Yeah。

Oh yeah， you can always do that that's true you can you know you could always do like sentence one says that sentence two is true。

 sentence two says that sentence one is false right but all right。

 but let's say that you know when we prohibited selfreence right our prohibition was actually broader than that okay it actually you know prohibited you know any kinds of you know cycles of sentences talking about each other okay you know if。

😊，You know， you you know， we were， we're just gonna say， you know， a sentence is， you know， you know。

 like， you know， these are privileged objects。 You know， they get to talk about other things。

 but they don't get to talk about themselves。 Okay。

 the problem is that sort of you can't really prevent sentences from talking about sentences that are in quotes。

 right， because something that's in quotes is just kind of a string of symbols， right， You know。

 it could be anything， right， you know， we can always talk about strings of symbols。 right， so。呃。

All right， you know what？So yeah， you could do them like the following sentence repeated twice the second time in quotes is false。

QuoteThe following sentence repeated twice the second time in quotes is false all right so know this sentence is not talking。

 you know directly about itself， it's not talking about any other sentence that has sort of you know。

 first level status on the page it's just talking about the string of symbols that you know that is between quotation marks who say you know that ought to be okay okay and yet implicitly it is talking about itself okay you know when interpreted it is saying that it's false。

You know， and so then we're back to the problem we had before。 Incidentally， you know。

 I can't resist pointing out that。You know this trick。

 print the following twice the second time in quotes。

 print the following twice the second time in quotes， this is basically how we work。

 this is basically how DNA works， this is how reproduction works okay know we are basically these you know machines that you know that carry code you know the DNA code that says make a you know make a copy of this organism and then make sure that the copy also contains you know。

The code for making a further copy， in other words， it's its own DNA， you know。

 you can think of you know describing an organism by its DNA as like putting the organism in quotes okay。

😊，So。So yeah， so it's a useful principle All right。

 so now you know what this tells us is that the problem with this sentence is false is not actually self reference right。

 you know， it's got to be something else Okay， and the thing that。😊。

That sort of logicians zeroed in on in the 20th century as sort of really being the problem is。

Its the concept of true and false itself。Okay。😊，You know。

 it's not that there aren't things that are true and other things that are false， okay， but you know。

 there cannot， you know， and this was the conclusion of。Of Alfred Tsky， the indefinability of truth。

 it's called。あ。And actually， Gerdo also observed this in the way to the incompleteness theorem。

 but he didn't publish it， Tsky liked to call himself the second greatest logician of the 20th century and the greatest sane one sort of a mean thing to say about Gardo。

 I guess， but。😊，But what Tsky showed is， well， know what Trsky said is that there is no。

There can be no mathematically definable function， F。Whi takes as input， you know a sentence。

 you know， like of arithmetic a sentence about mathematical objects like integers。

 written out as a string of symbols， and which outputs one， if s is true。And zero ofs is false。Okay。

 so in other words， there can be no。Mathematically definable， truth predicate。 Okay。

 and why can't there be， Well， precisely， because if there was one， then we could construct。

This sentence。The wire paradox and then that would be a genuine mathematical contradiction all that would be just like you know proving zero equals1 okay so you know so the conclusion is just that there is no function。

 you know mathematicalmatics itself is not able to define a function that just takes an arbitrary mathematical statement and that outputs whether it's true or false。

 you know you can believe in the existence of such a function。

 but that's like a metamatheal you know commitment。😊，All right。😊，All right， but that's just you know。

 truth now the main innovation of Gerdel was to concentrate not on truth， but on provability。Okay。So。

So what do we mean by provability？U。Okay so。So， you know， to really like。

Explain this for real you know you know would require sort of a whole course where we talk about you know what is a proof system right。

 a proof system is basically just a completely formal system for you know talking about math so you know it includes a completely formal language for you know expressing mathematical statements okay and you know these languages were invented around you know late 19th。

 early 20th centuries like people like Fredge and Russell Russell and Whitehead。

 okay and you know they say things like。You know， for all X。

 you know for all you know maybe we can you know you know we would have to define what we meant by integers first right but for all the integers。

 you know there exists in other integer y such that some function of Fx and y you know you know equals y and some other function you know y you know equals0 right so it's you know so so you're allowed to have quantifiers like universal and existential quantifiers。

 you're allowed to have logical connectives like Boolean connectives usually there's some equality symbol。

 they are function， you can define functions Okay so you know these are like this is called the language of first order logic right okay and。

And then there are。嗯。proof system also includes inference rules。

 you know inference rules just a way of taking previous sentences that you you know believe are true and deriving a new one okay in some completely mechanical way okay so you know famous example is modus pos you know if you you know you've already deduced a and you've deduced that A implies B then get you get B right you know and that's just a matter of turning a crank。

 it doesn't matter what a means what B means right its just any two things that have this syntactic form you deduce this thing okay and then you know there are you know there are other inference rules like if we knew。

That。F of x equals1 for every x， then we would also know that。F of y is one。

It doesn't matter what y is okay you know its we can you know so we can sort of this is called quantifier illumination all right you know。

 I there's the rules of there are other rules for quantifiers like if it is not true that F of x is1 for all x then it is true that there exists in x such that f of x is not one you know stuff like that all right so we have inference rules and then the third thing that we have is axioms okay so we have certain you know statements that we just accept as true to begin with and。

😊，So so the axioms will depend on know what kind of objects we're talking about， you know。

 you've seen like the axioms of Euclidean geometry。

 you know like you know every two points define a unique line and so forth， okay。

 the axioms of arithmetic of what's called piano arithmetic which say， you know， there exists zero。

 you know， there exists a number， say you know and every number has you know exactly one successor and if two numbers have the same successor then they are equal。

 you， pretty pretty believable sounding things， you know， the axioms of set theory。

 say things like the empty set exists you know you got to start somewhere， you know for you know。

 given any。呃。You know， given any you know， let's see。

 given any two things like you know given any two sets。

 you know there is a union of those you know the union of those two sets is also a set you know the intersection of those sets is also a set know then at some point you have to say that there exists in infinite set okay because you know otherwise。

 you know you might have just only finite sets and that would satisfy all your axioms。

 oh you say for every set， the set of all subsets of that set is also a set。

 okay which you know then let's you starting from the， you know。

 if any of you have seen like you know the way that set theory works is kind of cool you start with the empty set。

 you start with complete nothingness and then you know people say you know you can't you know create a universe out of purely nothing right but you know in set theory what you do is all right we can have a set containing the empty set that's something new。

Right that's a little bit more of something right and you can have。😊，U。Let's say the set。

The set that contains the empty set plus the set containing the empty set， you know。

 and you can keep going like this， and then you can define you know these to be you know one to one correspondence with integers and that gives you numbers。

 yeah。AhSo you're not allowed to say， I define a set that contains you everything except for such and such。

 okay， does anyone know why you can't do that？Yeah， there's an important reason。

 Russell's paradox right， Russell's paradox says， you know。

 consider you know the set of all sets that don't contain themselves。sounds perfectly reasonable。

 but then does it contain itself？Well it does if it only if it doesn't okay so that's a problem right so you another version of it is like you the barber who shaves everyone who doesn't shave himself so does that barber shave himself so because you can run into paradox know and this was actually Fred A wrote a whole book on set theory like not spent like decades working on it not noticing this problem and then Russell sent him a letter saying well you can get a paradox if you just allow the set of all sets that have such and such a problem that's trouble okay so what we do in modern so the modern system for set theory is called ZermoloFranel set theory or ZF and the ZF axioms require in order for a set to exist that you've got to sort of build it up in。

you know starting from the empty set in some way right you know or you know or you know they allow you to also start from some you know countably infinite set okay and then you can take its power set you know so you can get extremely big sets but every set sort of has to be built up in some way you can't just say the set of all sets such that blah blah。

 blah Okay so anyway so yeah so we have。Axioms and。Okay， so now just some terminology。Okay。So okay。

 and then any any statement that we can derive by starting from the axioms and then applying you know the inference rules any finite number of times is called a theorem okay it's called a theorem of that proof system okay and so now。

JustSome terms that we use， a proof system is sound if all of the statements that it can prove are actually true。

 okay？If everything provable is true okay， as I said。

 truth is not itself you know mathematically definable。

 so you know you could think of this as just sort of a value judgment right this is you know this is not a mathematical definition。

 this is something that you know we you know looking in from the sort of from the outside you know you know with some independent standard of judgment we'll say okay but then something that。

Can be defined， you know， in a much more mechanical way is consistency。 Okay。

 consistency just means that the， you know。呃。The system never proves both a statement and its negation。

 right？So you know at least the system is consistent in what it says right， you know。

 like it doesn't prove that you know that0 equals1 because presumably it also proves that zero is not equal to1 right so that would be an inconsistency you know are these the same thing I mean。

 can anyone give okay， so is any sound system consistent？Well， you know。Presumably so because。

You know， the truth should all be consistent with itself， right， but is any consistent system sound？

WellWhat's an example of something consistent but unsound。Well。You know。

 if I believe that the moon is made of cheese， you know。

 but I also believe that the moon tastes really good， spread on a cracker， you know， you know。

 I have all these beliefs about the moon that are all completely crazy but they're consistent with each other right you know I mean you know actually you know like you over talklk to you know like a conspiracy theorist you know。

 like you know you just you know it's like an incredible real- worldorld example of someone you know with like some network of you know。

 consistent beliefs that you know maybe very very far from being sound right， so。Okay。Okay。

 then there's this notion of completeness， important for Gerirdel's theorem。

Completeness means that for every statement A， or at least every statement like within the domain of discourse that we care about。

 so you know every sentence that you can form using you know every grammatical sentence that you can form using the rules of this formal language。

 the system，Proves。Either a or it's negation。 Okay。

 so completeness says that system renders a verdict about everything。Okay， and then。

And then one final。Definition， we will call a proof system computable。😊。

If there's a program or you know in other words， there is a touring machine。That when you run it。

Lists all the theorems。That are provable in the system。Okay。And。

This this computability condition will also be important。

 okay any proof system that you would naturally think of sort of satisfies that condition because you know in general you'll be able to satisfy it by just sort of saying start with the axioms。

 you then start thriving consequences from them in every possible way you know do again a breadth first search tree where you just take every possible consequence of these axioms by applying inference rules once and then every possible consequence by applying the inference rules you to those new statements you know another time and so on and so on and then you in the limit that that will list all of the theorems of your system yeah。

😊，No， it just means that it can list you all of the theorems that are provable in the system。

 a theorem you know in you if we're talking about a formal language a theorem is going to be a finite string of characters right so in order to even have a state a theorem you're going to have to somehow specify which real number you're talking about right so know so most real numbers there's no theorem about them just because there's no way to write to write that real number down in any finite amount of time the very you if you're proving a theorem about it like you know it's pi or I or something it's because you're able to have have a short formula that specifies that know what number you mean right。

So now I can state with。With this in hand， I can actually state and prove the first incompleteness theorem。

And。俾了我。I'll state it in an informal version。And then we'll see sort of more refined versions of it next week。

Okay， so it says let F be any proof in this version。

 I'm going to say let F be any sound and computable proof system which is sort of powerful enough to express statements about arithmetic okay you know like sentences about integers okay you know I'm being a little bit vague about this。

 but you know most natural proof systems like piano arithmetic or Zerma little fel Z theory。

 you know the all satisfy this， they' all fall under this， okay then。😊。

There exist statements of arithmetic S， which are expressible within the language of F。😊。

Such that F proves。Neither the statement nor its negation。Okay。

 so there are statements that know that F just purely arithmetical statements that F can neither prove nor disprove。

Okay。And the famous example。