# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p10 P10 mar12 -BV1Dao8YQEEn_p10-

Hi。All right， so PSAT3 is due Friday of next week， so until on Tuesday we talked about Gdle's incompleteness theorem and Rosser's theorem and incompleteness and informal systems and then in the last few minutes we started talking about a kmogra of complexity。

 which is sort of the last computability thing I want to talk about。

 which is sort of a bridge between computability and complexity。

Commora complexity is a striking concept that was invented in the 1960s actually independently by Kamograrov Sallomanov and Chaton Solomanov was first I think Chaton invented it while he was still in high school but Kamogra was the most famous of the three that we call it Kamograrov complexity and basically what it is is that's sort of the ultimate limit of data compression you could think of it that way so given a string of bits X the Kamogra complexity of X is sort the length of the shortest program that there is in some programming language of your choice that went run on a blank input just print X and then Holttz so sort of the length of the。

Shorest computable description of x okay so clearly you know for every string there is some programming language know there is some program that outputs that string namely a program that just sort of says print and followed by the string that just hardwires the string into the code so for any n bit string X K of x will never be much more than n know the most it could ever be is a little bit more than n you know you might worry that K of X would heavily depend on the choice of programming language but on P at3 you'll prove this important invariance theorem which is that really just like a very easy a very simple observation once you have it which sort of shows that the choice of programming language can affect K of X by at most some constant factor which may。

Depend on the programming language， but which doesn't depend on x okay so it only changes kography of complexity by an additive constant。

 that's the invariance theorem I mean that's what you know what makes this a more or less sensible notion。

 you could say。Okay， and then the other thing that we observed on Tuesday is that。

 you know among all of the different strings of n bits。

 there must be some that are incompressible okay， because if every nbit string was compressible。

 Well then you could just you know， keep compressing strings down to nothing right。

 that's one way to say it in fact。You know， a stronger statement is true。

OkayI claim that almost all strings have close to maximal commmorov complexity。

 so if you picked an n bit string at random， you know then almost certainly its comograph complexity would be at least。

 let's say n minus100， okay， can anyone give me an argument for that？Why is that。Well。

This is just yet another variation on Shannon's counting argument，啊哈。

The thing that comes on you running。嗯哼。Yeah， right， you could do an argument like that。

 but now we want a more quantitative conclusion that you know that this is true for almost all strings of。

N bits， you know， but what we can say is simply how many possible programs could there be you that are at most n minus 100 bits long？

Anyone。How many what's an upper bound on the number of such programs？

It it's an upper bound on the number of programs that are K bits long。Two to the K right。

 or you know， if we say it most K bits along， maybe a little bit more than that。

 we have to say two to the K plus1 right because you could have you know。You know。

 if you take programs that are k minus1 bits long， so there's at most two of the K minus one of those。

 Ive got and so forth。Okay， what's this Psalm equal to anyone？Two to the k plus1， well， minus1。

I hope， sorry， yeah。All right。😊，So we can say that the number。呃。

Programs in whatever programming language you want that are at most and to the minus00 bits long is it most。

2 to the n minus 99。Okay， you know， it's probably a lot less than that because most strings of this number of bits will not correspond to programs that compile right。

 but you know， but it's certainly no more than that because that's just how many strings there are okay so okay。

 but now by contrast， how many endbit strings are there。Two to the n， right？

Okay so there's two to the n strings and you know you're asking for you know to represent them by programs of which they're at most two to the n minus 99 okay this is way way less than this in fact its less by a factor of two to the 99 okay so you know there just aren't enough programs to go around okay you know just like you know we saw before that almost every Boolean function must have you know exponential circuit complexity because there just aren't enough circuits to go around right so too here you know most n bit strings must have kmoography complexity that is close to n because you know if we look at programs that are much smaller than n bits along there just aren't enough of them to go around each one can you represent it most one string okay and there's just too many strings and too few programs okay。

So。那。So the conclusion is if this is the set of all strings， you know， the compressible strings。

 the kmorov compressible strings are just a tiny， tiny subset， okay you know， so this is you know。

 you could say that you know because of this， the fact that data compression works。

 the fact that you can actually run GZip or whatever and it actually produces a smaller file is a little bit of a miracle right？

Because I'm tight because you know， almost all strings are incompressible， okay。You know。

 it is this tiny， tiny subset that can be compressed and yet that tiny subset is extremely likely to arise in practice。

So you know basically， you know the types of files that we deal with in practice you know have huge amounts of redundancy in them。

 huge amounts of regularity， you know， from this observation we can conclude that they can look nothing like completely random files。

 a completely random file is almost certainly incompressible。Okay。Good。

 so what's the point of Komoav complexity right why was it defined so the original reason for inventing it was to try to sort of deal with a certain puzzle or paradox。

 which is at the heart of classical probability theory。Yeah。

 it's a puzzle that goes back to the 1700s in some sense， likela talked about it， okay。

 and puzzle is how can you know if a coin is biased or not or if a coin is。

 let's say if a coin is crooked， okay？You know if I。You know。

 let's say that I flipped a coin a thousand times and every single time it comes up heads。

Right then you know we agree that presumably that this is pretty good primafossy evidence that there might be something fishy about this coin right I mean yes。

 you it's possible that that could have happened by pure chance that it would have landed heads a thousand times in a row but you not it is very。

 very unlikely， in fact the probability that we would have seen you know that that would have been two of the mine that's a thousand power if the coin had been fair okay so if we say that you know know we started out with some prior probability for the hypothesis that the coin was fair and then we see you a thousand heads you know out of a thousand flips and then that hypothesis has become massively disfaavvoreed in the Bayesian sense。

Al right， that's， you know， that that's perfectly intuitive。 Now， you know， in， in the same way。

Let's say that you flipped a coin a thousand times and you saw a perfectly alternating sequence of heads and tails。

 okay， heads tails， heads tails， heads tails， you and no deviations from that okay well you could say well in some sense this was a fair coin but there's still something really。

 really fishy about it this is this is almost certainly not a coin which is which is memoryless or which is just landing you heads or tails with independent one half probability at each flip。

😊，Because if it were， you would not expect to see such a regular sequence like that。 Okay Yeah。

 we can make up stranger possibilities， okay， we could say。Okay， what's here。

 what's happening here is that the queen is landing tails on every prime numbered flip。

Okay you know and on every non-prime flip it's landing heads all right that you know again。

 if you saw that that's a pretty strange coin right if you saw the movie contact right this is how the aliens make contact with the humans by sending like a bunch of radio signals that beep but prime numbered intervals and then you you see that and you the humans see that or Jody Foster or whatever sees that and she knows that that's not a random pattern that we must have been produced by some sort of intelligent or purposeful process actually there are situations where prime numbers can just arise in nature without any intelligence behind it。

 but you radio signals that give a sequence of primes probably something fishy about that okay but okay so so these these are all you patterns that if you saw them would cause you to suspect that this is not an ordinary coin right okay？

Then and we can give an argument for that that each of these patterns if the coin had been a normal coin would have been astronomically improbable。

Okay， but then you know， we think about this further and we say， let's say that the pattern was。

Let's say that the sequence of。Of als I don't know heads， heads， tails， heads heads， heads， tails。

 tails， tails， heads， tails， something okay， you know， there's nothing really obvious about it。

 but now someone looks at this， you know this sequence of a thousand heads and tails and says what is the chance that the coin would have produced exactly that sequence。

 it is again two to the minus is a00 power and yet we flipped the coin and it did produce that sequence。

 therefore the coin must be crooked？It's like you know if you were playing poker right you your Delta hand。

 no matter which hand you get， you get say what is the chance that I would have been dealt exactly this hand it is tiny you know and yet I was Dlta this hand right so something must be fishy about the deck。

Okay。So you that sounds pretty strange， right？😊，You know we don't normally say that because you know if you would say that then you could say that no matter what hand you got。

 it's like you know you had to get some hand， you know whatever hand you get is very unlikely but you had to get something so now the question is what is the difference between these cases in this case。

 what is it that you know makes it legitimate to say that the coin is crooked if you get a sequence like this。

 but not legitimate to say that if you get a sequence like this。

 even though all four of these sequences that I wrote down are equally unlikely to occur？Yeah。我当。嗯哼。

😊，youll be able to predict in advance of what will come up with。

That's okay that's an excellent example of a difference right and that gets to you know I think you close to the core of what we're talking about so in the first three cases like we can specify a rule that tells us what the heads entails should be right and once we specify that rule we can then extrapolate that rule into the future the rule one could say takes fewer bits to specify then the sequence of coin flips itself right so can from100 coin flips。

 you can infer what the rule is like maybe that it's you get a tails on every prime numbered flip and then once you've inferred that rule you can use it to predict far more than 1000 coin flips you can use it to predict a number of coin flips that greatly exceeds the number。

😊，Of bits that's needed to infer the rule。Okay but that's not the case with the fourth one right with the fourth one。

 all you can do is just flip the coins and then you know whatever outcome you got you could say well after the fact the rule was that I got this you know I should get this sequence right so to specify the rule just takes the same number of bits as to just write down the sequence of coin flips themselves and because of that because of the lack of compressibility。

 there is also a lack of predictability okay。You know if it takes you know n bits to sort of specify what happens with the first N coinin flips。

 then you you have no basis on which to predict the n plus first coin flip right so you know so I mean in some sense you' you here you in the machine learning people would say you have the problem of overfitting okay you know your class of you know possible patterns is so vast that it can account for any possible data that you would see right。

 but because it could account for any possible data it's completely useless for predicting the next data。

Okay。It's。You know， it's sort of like when people you know look at ancient texts， right。

 there was this you know controversy about the Bible codes right。

 but then you know other people went and you know in fact you that people said that you know you look at every。

40th letter or something and you do some transformation to it and it predicts。

 you know and it predicts the assassination of JFK or whatever。

 you know and then other people said you know know I could also predict the assassination of JFK by looking at you know patterns in like the Australian fisheries regulations you know or in war in peace okay you know and then yous not it's not actually that hard to you know to pick any text you want and you and torture it enough that you can get out a prediction of any you know sort of past event that you like that may have happened because there's just so many ways of torturing a sequence of ones and zeros to you know extract patterns out of it the hard part is to predict the next thing that's going to happen right？

So so this is an example of that okay and you a way that we could formalize this is by saying that you know。

 in these cases， you know these are sequences whose commograph complexity is much smaller than the number of bits needed to specify them right so we could say if I look at an end bit pre。

 you know the first n bits of one of these sequences then commograph complexity is much smaller than N okay。

 in fact， you know in each of these cases it's basically log of N， yes。😊，Yeah嗯。Yeah。Yeah。

 it's basically it's yeah the commmograph of complexity of each of these is basically about log of n okay because a log of n plus a constant because all you need to do is specify n and then specify a constant amount of information about the pattern right you know like I want you to generate the sequence you know of the corresponding to the first n primes or something right and that's just a constant amount of information independent of n okay whereas in this fourth case。

😊，The kmogara of complexity is really know， almost certainly it's about add。Okay。

 so so we can say that you know you should suspect， you know。

 the sort of modern point of view about this is that maybe you should suspect something is crooked about the coin if and only if you know you look at the sequence of the first N coin flips and you get something you get a string whose comemogra complexity is much less than n。

Okay's that's sort of the， you know， this is sort of a formal way to say something fishy has happened。

 something unlikely has happened， right as we saw over here。

 you know you know you had if the coin flips were truly random。

 then it would be astronomically unlikely that you would have seen a sequence whose comoography complexity was much less than n okay so if you did see one you know。

 then that's pretty good evidence that something fishy is going on。Okay。

 so so you know this sounds like you know a wonderful you know a potentially extremely useful theory right where you know you can tell you you know is there a pattern in your data or not right that sounds like something that could have some applications right so this is great so why don't we you know just go use this in practice right and just you take our data and compute its kography of complexity and then you we'll know if there's a pattern there or not。

😊，Well。All right， now we get to the part that kind of sucks okay turns out that kmograph complexity is uncomputable。

 there is no program that takes a string x and that outputs k of x now to be clear there is well I mean let's be clear about this you could certainly write a program that give an X would dovetail over all possible touring machines。

 you know all possible programs you know that are n bits long or shorter and whenever one of them halts and outputs X you then know what about k of x anyone。

😊，Say some program， which is M bits long， has halted an output at X。

 then what do we know about K of x？Yeah that it's at most anytime we find a program that outputs X that gives us an upper bound on k of X right it says that you know well the Mac the best possible compressibility you know is at least what we manage to achieve by this program okay so we could dovetail over all touring machines。

 you like run run them all in parallel you starting more and more up as time continues and as more and more touring machines halt and and output X。

 you know if they halt and output something other than X we ignore them。

 but as more and more of the machines halt and output X you know and those machines that do so or shorter and shorter machines we will get better and better upper bounds on K of X okay and in fact the。

You know， after some finite amount of time you know this strategy will tell us k of x right because eventually whatever is the shortest machine that outputs X。

 that machine will have halted and output at X right you know。

 we don't know how long it will take to halt， by the way right。

 the shortest program that outputs X might take an enormous amount of time to do it definition of chgraph complexity puts no restriction on the time you know that's important okay so but you know eventually you know whatever is the shortest program that outputs X。

Eventually that program is going to halt an output at X right and so eventually our dovetailing program is going to find that and at that point。

 you know the program will output k of x okay but what's the problem why have we not thereby computed K of x？

Yeah。Yeah， exactly we still don't know if there's a shorter one right you know there are still shorter programs at this point that haven't halted and we still don't know whether one of them is going to halt an output X in which case we would have to revise you know our value of k of x downwards again so even at this point you know our program has now output K of x and it's never going to output anything else right because you know by assumption this is the right value but we still don't know that it's the right value so which means that we still can't halt the program we have to just continue running the program forever okay so what this shows that yes there is a program that runs forever that outputs a bunch of guesses and the last guess that it outputs is the correct value of K of x okay but the problem is that we don't know that it's the last guess that it outputs okay so you so the program will just。

😊，Continue running forever after that， and at no point will it ever have determined for sure that the last thing that it output was the correct thing。

Okay， so so what we want to show is that there is no you know， you know no matter what we do。

 there is no program that's going to always halt after a finite amount of time and have correctly computed the kmogra of complexity K of x okay。

 so how can we show that？😊，Let me。Okay， so it turns out to be true that。

The computing K computing commmoography complexity is touring equivalent to the halting problem okay so it's definitely you know touring reducible to the halting problem I mean I think you prove that on P at3 right that's an easy result to prove that the hard part here is to prove that the halting problem is touring reducible to commmograph complexity so if you had an oracle that computed k of x then you could use it to solve the halting problem that's a hard theorem so I'm not going to prove it in this class okay what I'm going to do instead is just give you a really really simple and you know kind of a slick and you know memorable a nice argument that just shows you that k of x is must be uncomputable you know without showing that it's equivalent to the halting problem。

Okay， and the core of this proof you know， involves yet another logical paradox。

 which is called the Berry Paradox， okay， this paradox was actually first described by Bertrand Russell。

 but he said that he heard it from a librarian named Barrry。

 so that's why it's called the Berry Paradox。😊，And you know， some of you may have seen it before。

 but it says， what's？Okay let's let n equal the smallest positive integer that cannot be described with 100 English words。

 meaning 100 English words or fewer okay now I claim that such an integer must exist why must it exist well so first of all。

 let's you know。Assume that by English words， we mean ones in the Oxford English dictionary or whatever right so so you know which is a large but finite number of words okay so there's finitely many different words we're talking about and presumably any sequence of English words。

 it might not describe any integer if I just say a red rows that doesn't really pick out a positive integer but you know among those that do you know each one should pick out at most one positive integer so we have all these this finite so the number of possible sequences of 100 English words are fewer you is finite and among all the ones that pick out a positive integer you each one picks out only one but there are infinitely many integer so there must be infinitely many integers that are not describe by any sequence of 100 English words and among those。

Mus be a least and that one we define to be N。This has just been described。That is the paradox， yes。

 thank you， that is precisely the paradox。😊，Okay， I have just described Anne using fewer than 100 English words。

 okay。😊，So what gives？So that's the paradox okay you know in the very act of defining and you know I violated its definition okay so once again you know just like you know with this sentence is not true or the liar paradox you know the sort of move that you know logicians would make today would be to say。

 well you know we don't even know exactly what we mean by describing an integer using words okay it is not well you know the English language is not a mathematically precise language and know we haven't even defined what it means you for a sequence of English words to describe a positive integer and you and you might say you know okay well why is that such a big deal。

 well the reason why it's a big deal is that you if you're not careful about it。

 then you run into paradox is like this one。So you so you have to be you know so if you want to avoid this problem then you have to be more formal about what you mean by describing an integer okay what is a more formal way of describing an integer well how about using computer programs right we could say you know the integer has to be described you know using a computer program okay and then you know we could talk about like the first integer know that cannot be described using any short computer program okay well what so that sounds kind of like commgraph complexity so what happens if we do that and how do we then escape this paradox？

😊，Okay， well let me show you the sort of Cabogra of complexity analog of this， Okay。

 so what we're going to do。So we're going to suppose by way of contradiction that Komogra of complexity is computable and then you we're going to show that if it were then we would have a formal version of the Berry Paradox okay so so here here's the idea I claim that you we can then you know I want to write a program that will just output you know that will output a string whose comogra of complexity is at least n okay how could I do that。

Well， let's consider the following program。Okay， let's say I write a program。

That just loops over all strings in lexia graphic order。Meaning， you know， the empty string。

 then zero then one， then 00， then 0，1， 1，0，1，1，00，0 and so forth。

 that's lacking a graphic order okay then。And then as soon as a string X is found whose comogra of complexity is greater than or equal to n。

 then we print that x and halt。Okay。So first of all you know there clearly there must be some string whose commmograph complexity is at least n no matter what n is because the number of strings whose comograph complexity is less than n is finite right but you know at most the number of programs that are you know that long but there are infinitely many strings so eventually this program is going to find such a string X okay and at that point it halts okay so it outputs a string with you know that has this you know commmograph complexity at least this large now you know by our hypothesis that commmograph complexity is computable you know we could write this program we just call our subrout for computing k of X over here okay now now I ask the question how long is this program how many bits does it take to specify this program as a function of n。

How does the number of bits that you would need to write this program grow as a function of n？

Yeah like log n basically okay because you know I just well let's say log n plus l of1 okay once again。

 there's some you know part of the program that I you know there's some program that I have to write you know but it doesn't depend on n right you know that says loop over all the strings for each one compute the chograph complexity blah。

 blah， blah you know that that's the l of1 right and the only part of this program that depends on n is this right here I just have to write down n as a thing to compare k of x to but writing down n takes log of n bits right。

Okay， so what I've now done is I've given a program that was only log of n plus a constant bits long and which searches for and outputs a string whose coography of complexity is at least n。

 What's the problem with that anyone？Well， you know， if n is large enough。

 then certainly n is going to be larger than log of n plus a constant right whatever that constant had been。

 right you agree with that right okay so what this means is that we have just violated you know the assumption that k of x was at least n okay we've just given a program to output x whos you know which was shorter than n bits。

 okay and therefore k of x was not at least n that's a contradiction。

See that just like with the Berry Paradox， this number that required this huge number of bits to describe。

 we just described it with a smaller number of bits。

 so it didn't take a huge number of bits to describe。😊，So what's the only possible conclusion。

 the only assumption that we made here that could be falsified is that k was computable so our conclusion is that k of x could not have been computable。

😊，可以。You like that。All right， so。All right， so now you know I want to so camograph of complexity you know is called。

 you know it's sort of a misnomer， you know like I wouldn't really think of it as a measure of complexity。

 it's more like a measure of algorithmic randomness or entropy or incompressibility right because you know after all the comograph complexity is maximized by just a completely random string okay and I don't know about you。

 you know I don't think of completely random string as something particularly complex okay you know it just random okay but you know but this was you know sort of like a quantitative subject that you know that helped。

Pave the way maybe for a complexity theory， okay which will be sort of our focus for the rest of the course more or less okay so so what we're going to be focusing on sort of the rest of the time is not just what can be computed you know in any amount of time but what can be feasibly computed you know what can be computed with reasonable resources okay so you know a lot of the you know the strangeness of kmogra of complexity you know comes from the fact that you know yes。

 we were concerned here about the length of the program。

 but we weren't concerned at all about how much time the program took right the program could take you know two to the two to the two to the end steps。

 you know to output X okay it could take way way longer than the age of the universe right that。

I mean you know like okay it'll be about 10 to the hundredth years from now until you know the black holes that are at the centers of galaxies will have evaporated into  Hawking radiation but there are functions that are computable which by that time you know the touring machine to compute them would have just barely been getting started it would just be setting up by them okay so you know so and this is something that people realized you know as sort of real computers started being built。

 people started to you know try to solve problems with them that were formally computable and they realized hey you know it would be nice if not only is our function computable but you know but the computer is going to halt you know and give us an answer know while we're still alive know and this is I mean especially so with the computers of the 50s and 60s right but know it's even true with the you compute。

of today because of something if you have a problem that inherently required exponential time to solve or two to the end time to solve inputs of you to solve to decide on inputs of size N okay then you in some sense there's hardly any difference for such a problem between the computers of the 1950s and the computers of today it's the computers of today can handle a somewhat larger range of ends but if n is a million。

 then they're just they're both equally hopeless okay so so it's sort of dawned on people that what we really care about is not just what's computable but what's computable with using an amount of resources that scales at only a reasonable rate with the size of the problem that you're trying to solve okay？

And I mean， this did take some time to be impressed on people like you know probably many of you have seen a Dyktra's shortest path algorithm。

 like in six doubleX or something this is like if you ever use Google Maps or you use ways or whatever。

 know how is it calculating a route from between your start and end points。

 using something like Dyktras algorithm which is an algorithm for finding the shortest path between two points。

 you in a given graph given the distance between every pair of points one of the most fundamental algorithms that there is and it runs in time which is linear in the size of the map but Dyictra at all the story when he invented this algorithm in the late 50s like there were colleagues in the map。

Department who has said well but you know you know I don't even understand that that there's a problem at all to be solved here。

 I mean， look， you know you know clearly you know you're never going want to take a path that visits the same place twice right know that would be stupid okay so you know so the number of paths between two points on a map that don't visit the same point twice is finite so just enumerate the paths and take the shortest any finite set has a minimum so just take the minimum of the set and then you're done problem is solved you know it takes you know a little bit of experience probably with programming。

 you to realize you know just how bad of a solution that is so you know and and you the theory of complexity is sort of what enables us to say formally what is bad about that solution what is better about the extrarous algorithm it has the better scaling behavior okay so be a little bit more。

Foral about this。So let's。So we'll have to fix a model of computation for now。

 let's just say two tape touring machines， okay， you know it's not going to matter that much。

 but it'll matter a little bit more than it did in for computability theory。

 okay for reasons that we'll see later。Okay， and then。And then。I could define a class of languages。

 for any given function F， which I'll call time of F of n。Okay。呃。

And actually another name for it is D time of F of N， the D stands for deterministic， okay。

 that's just to distinguish it from nondeterministic touring machines， which we'll get to later。😊。

And what it is is it's the class of all languages， let's say， over the alphabet01。

For which there existsuring a two tape touring machine， M， such that。For all inputs， X。

M of x accepts。If x is in the language。M of x rejects。If x is not in the language。And。M of X halts。

In at most， L of F of the length of x steps。Okay， so it's basically just the class of all the languages that are not only computable。

 but that are computable by some twota touring machine that runs in at most F of N time whenever it's given an input。

 which is N bits long。Okay， so so a few comments to make about this。

 one is you know we've you know this is a worst case notion okay so we've required this machine to succeed you know in the requisite amount of time for every input you know you know of the appropriate length right so for every input of size n。

 it has to halt F of n steps and have decided by then whether x is or isn't in the language okay and you we're ignoring multiplate of constants here okay so whether it takes F of n time or 100 times F of n time or 100 F of n plus a billion or whatever that's all okay okay that's all you know in the class。

😊，Yeah。Oh， and the other thing is you know you could imagine you know counting the running time as a function of something other than the length of the input you say what's so special about the length of the input and indeed you know in complexity theory we sometimes consider the running time as a function of other things like there might be some parameter you know the tree width of your graph or something and you know we study the complexity is a function of that other parameter okay but the length of the input just the amount of data you have just seems like a very。

 very basic you know thing you know to examine the scaling of the running time in terms of right so that's just the most conventional choice that we make okay but it' it's really sort you should think of it as basically just a very。

 very useful convention。Okay， know so essentially you know you know what we're asking here is you know。

 does you know does your algorithm you know you know use an amount of time that scales only linearly with the amount of data that's present like you know if you wanted to compute the sum of all the numbers in your list this you could do with a linear time algorithm find the median know at least using a random access machine that's less obvious but that can also be done in linear time。

 you know if you wanted to sort your data， well you know that you can't do in linear time。

 but that takes n log n time and other things like multiplication division powering it may take more than linear time。

 but know certainly you could do them in in n squared time quadratic time time of n squared okay and then other things you know that we want to do might take time。

To to the end， right they might。呃。So here's linear time。Here's quadratic time。

 here's exponential time。You know， exponential， you know， and usually the type of， you know。

 distinction that we'll want to make。Is between polynomial and exponential time。

you could say the sort of empirical underpinning of complexity theory that sort of makes it useful。

 talk about is that when we look at the problems that are of practical interest to us。

 you whether it's matching or when you're programming or SVD or machine learning tasks or computational geometry tasks。

 most of them tend to sort themselves into the ones that have like a really good algorithm。

 meaning one that takes time you know N or N log N or n squared or N cubed or something like that。

 and the ones for which there's really no good algorithm at all， so they take time。

 something like two to the N or at least maybe something else to the N power or maybe in some cases maybe it's two to the square root of N power。

 okay but。You know， no you know， like it didn't have to be this way， right， like a priority。

 you could have imagined that there would have been lots and lots of problems of practical interest to us that would take time into to the hundredth power。

And then you'd say end to the hundred0th power， you know that's formally a polynomial growth rate。

 but that's you know that really， really stinks in practice and you know and occasionally you do get things like that。

 occasionally you do get， I think the largest one that I ever saw in any paper that was ever published was end to the 60th power approximately okay but it's very very rare and even when it does happen you know what usually happens is okay you know maybe you know you know someone is showing that know some problem is solvable when end of the 60th time that's totally useless in practice okay but at least they've proved the point that this problem does not require exponential you complexity to solve and once that point has been proven then usually we find that sort of the floodgates are opened okay so then if anyone really cares enough about solving this problem in real life。

They could probably think about it more and get it down to end of the 40th power and you know okay and that still sucks。

 but if anyone really cares you know more they can probably think about it more and get it down to end of the 20th and then down to end of the 10th you know and once once it's end to some power right then you know we're really just haggling over the number right so then you know and this has happened again and again like linear programming you know used to you we used to only know how to solve it in end of the sixth time and was very impractical now we know how to solve it you know and cubed or you know in many cases less than un cubed okay so。

😊，So so once you know that something is formally polynomial。

 you you often you're able to make it efficient in practice。

 whereas if a problem requires you know inherently exponential difficulty， then you have a problem。

 okay， and once again， you know， you could say a priorityi， you know。

 it is possible that there could be problems that had exponential complexity， but。

But actually the complexity was like 1。001 to the end power and you say that seems perfectly feasible in practice even though it's formally exponential okay and again you know you do sometimes get behavior like this but most of the problems that are you that take exponential time seem to really take you a pretty bad exponential amount of time you there're going to be at least some cases of them that you know we're just not going to be able to handle okay and that's sort of the empirical phenomenon thats sort of you know justifies us to study this but you know you should always be aware you know that you know between the theory and the practice you there are all sorts of issues that can matter like the constants you that are hidden by this big O that can matter you quite a lot okay so you the theory is sort of one part of the picture of you know knowing what you actually can or can't do in practice okay and I should say the reason。

W why we're not going to focus really on the constants that are inside of this big O is that there's really not much that we can say about them theoretically because the constants you and in fact the lower order terms here they're going to depend on what kind of hardware you've got you so like you one hardware there could be a huge constant but with a different hardware that has a graphics accelerator or something it could be a much lower constant and so you we can't you know from our sort of you know Mount Olympus or whatever our theoretical remove we can't really say what a constants are going to be。

 they're going to depend on all kinds of details about the machine model but you we'll be able to make statements about you the rate of growth like you is it n squared or and cubed。

 is it polynomial or is it exponential which are extremely independent？And of the machine model。

 where you know I mean that whole across an enormous variety of machine models and that's sort of what will make it interesting to us。

Good。嗯。I'll say more about that later， but about the。About to what extent do you know。

 our statements about complexity depend on the machine model and to what extent do they not。

 but yeah。Yes， okay good right all right， so I'll tell you why。😊。

The reason has to do with actually the palindrome language that you saw before or examples like that。

So remember you know we saw this touring machine that to decide whether a given string is a palindrome or not okay and that's a really simple problem that's intuitively that should really be a linear time problem okay and yet we saw that any one tape touring machine needs quadratic time to solve this problem because it basically it just has to keep shuttling back and forth and back and forth and back and forth and it just can't move memory around you know in a reasonable way okay you know whereas if we only had a second tape。

You know things would be much more reasonable because what you could do is you could just copy the first half of the string you know onto this tape and then go like forwards on this tape and backwards on this tape and see if they match up right and so with as soon as you have two tapes than it really is linear time and in fact there's there's a more general theorem that one can prove which is that a two tape machine touring machine can actually simulate like a random access touring machine you know with you know a random access touring machine meaning one that's able to jump around on the tape you know without that much further slowdown so basically you know。

You know want to， we don't want things to be sort of quadratic for really stupid reasons，You know。

 I showed you like earlier in the course， we sketched a simulation of two tape touring machines by one tape touring machines。

What that simulation showed was basically， if we really kept track of the running time， right。

 it showed that anything that you can do with a two tapeed touring machine。

In F of N time could be done。Buy a one tape touring machine in F of n squared time。

Right you know exactly for this stling back and forth reason。

 okay it incurred a quadratic blowup in the time， the simulation。

 okay and so you know if we only care about whether something is polynomial or exponential then you know we can live with quadratic blowups that's the square of a polynomial is still a polynomial but you if we want to you know a more refined analysis than then we wanted to really know what is linear time or what takes quadratic time then these blowup stink we don't want it and so then it's much better if we consider you just a little bit more powerful model like a twota touring machine that doesn't sort of you incur these quadratic blowups for silly reasons。

Yeah。Did you generalize this to any？Mmhm。😊，That's an excellent question okay so if you look in the Ssster book。

 I believe that there is a proof there that you know a K tape touring machine can be simulated by a two tape one without uncovering much further blow up。

 so once you have two tapes then you're really in a much better situation。😊，Okay。

I don't remember exactly what the quantitative statement is。

 but I can consult the book and tell you on Tuesday， or you can consult it too。You know。

 so in fact for。You know， I said two tape touring machines。

 but maybe I should have just said RAM machines。In fact， when I you know， I mean。

 it won't really be relevant for most of this course。

 but you know if it ever is relevant right then Ill you know I'll all tend to want to just allow any algorithm that allow you know that includes jumping around in memory and okay。

 so so let me。Although there are a few other things that I want to say that are simpler with touring machines than with RAM machines。

 so that's okay。😊，So。Just like there's time complexity， you know。

 so a second important resource that we can measure is space， okay， there's also space complexity。

OkaySo space F of N is defined exactly this or D space F of N， if you like。

 is defined exactly the same way as time F of N， except that instead of restricting the touring machine M to halting after at most O of F of X time stepss。

 we restrict to halt after having visited at most O of F of x tape squares in total。

 it can have done whatever it wanted for as long as it wanted， on those tape squares。

 but that's the total number of tape squares that it was allowed to have visited。

 so here we limit the memory that we're allowed to use。😊，So okay。

 so so now we've seen our first two examples of complexity classes and now you know we can engage in an activity that we'll do a lot more of。

 which is trying to understand the relationships among these complexity classes okay。😊，All right。

 so let's start with some really obvious things Okay， first of all。

 if we have two functions like F of n and G of n and G of n grows at least as fast as F of n。

 then what can we say？Well。It probably won't surprise anyone that time of F of N is then a subset。

Of time of Jayed。And likewise， space of F of n is a subset of space of G of n。

 which means if I allow you more time， it's not going to mean that you can do less， okay？finine。Okay。

 so so these time classes form a hierarchy， just like the space classes do。

 whether it's a strict hierarchy is a question that we'll come back to。Okay。

 slightly more interesting。I claim that for every F， time of F of n is contained in space of F of n。

 okay， so whatever you can do in F of n time， you can also do with F of n memory， why is that？😊，Yeah。

Yeah， exactly you know if you've got a touring machine right it's only moving one tape square per time step right which means that after F of N time steps you can only have visited F of N tape squares anyway okay so you and that's why this holds now this is an example of one of those things that's a little easier with touring machines with RAM machines you know something close to this is also true but it's a little bit more subtle because then you you could have a machine that uses only F of N time but it jumps around in you many。

 many more than F of N words of memory and then you would have to show that you know nevertheless you know if you have only F of N time than you can only actually use F of N you words of the memory and all those other words you know that are unused in between them。

 you could just sort of get rid of them， you can compress it all down you know using using hashing or something。

😊，So so this is clearly true with one or two tapeed touring machines， with raM machines。

 it's also very， very close to being true， but it requires some more work to prove it。😊，けな人。

Be the same reason why。Why space should be contained in time All right。

 lets do so let's discuss that right now so let's see if we can reverse the argument。So。

So space of F of n， we want to say is contained in time of what？Okay， time of something all right。

 is space of F of n contained in time of F of n right， this is now a question that we could ask okay。

 any machine that uses only F of n space can we simulate it using only F of n time so anyone you dont think so？

😊，政。Yeah， okay so so right， okay， so we have to be careful at the least we could say it is not obvious that space of F of N should be contained in time of F of N。

 because you know even if I only have F of N memory，😊。

I can keep going back and forth on this memory and just rewriting stuff you know in writing more and more different things。

 you know just reusing the same memory okay I can use much more than F of N time because because I'm allowed to reuse this memory okay and so you know now now what was just suggested was that you know there should not be any containment of this form because a space F of N machine could actually run forever right you could just keep looping forever using the same small amount of memory and so a space F of N machine could actually run for infinite time however that does not mean that there could be no containment of this form okay why not because space you know a space F of n and time F of N these are not classes of touring machines。

 they're classes of languages okay remember that okay so and if a given touring machine runs forever。

In particular， doesn't decide any language so never halttz doesn't decide a language。

 so we don't care about it and so the question that's relevant here is just if you decide a language some language L using F of N space。

 then how much what is an upper bound on the amount of time that would be needed possibly by some other touring machine in order to decide that same language？

😊，Okay， so now that's the question that we want to ask here。

 can anyone suggest an upper bound on the amount of time that we would need so suppose I have a touring machine that decides a language using only F of N space okay then we can we put any upper bound on the amount of time that that touring machine must have used yes？

Space times the number of states well actually I think it could use a lot more than that okay for example。

 we could have a touring machine that could just implement a binary counter right so which starts out with all of all of its F of N bits of memory initialized to zero and then it increments this to one you know and it just keep incrementing this viewed as a number in binary you know just like those billboards that say you know the national debt is such and such amount right you know the billboard keep running for quite a while right you know for much longer than the linear in the length of the billboard amount of time okay because you know it can keep incrementing for how much time actually as a function of F of N。

😊，Yeah。No。😀呵。😊，No， because the busy beaver function is going to you， you know。

 if you actually wanted to do a busy beaver， you would need much more than this amount of memory。

Yeah。What？😮，No。Yeah， it would be 2 to the F of n， right？Because you know。

 you exponential in the number of bits， okay。So， so the way that we。With F of n bits。

 you can count numbers， integers， and binary up to2 to the F of n， minus1， right？So。

So the right way to think about this is how many possible configurations can there be for an F of N space touring machine。

 how many different states could it be in at a given time where by state。

 I mean both its internal state and the position of the tape head and everything that is written on on all of its tape squares？

What's the total number of possible combinations for all of that？Yeah， okay。

 so let's say if there's F of N。Possible memory squares right then the number of possible settings of zeros and ones in these squares。

 you know I'll assume we're working over a binary alphabet is2 to the F of n okay but in addition to that the machine itself has some location on the tape you know to specify its location you know there f of n possibilities for that so we'll say2 to the f of n times F of n and then and then the machine also has some internal state right it's internal state you know there's a constant number of possibilities independent of F okay so all in all we get o of2 to the F of n times F of n okay that's the number of distinct configurations that the machine could be in okay but now I claim that that is also an upper bound on its running time if it decides a language。

 why is that。😊，Yeah。And yes， exactly， exactly。 so this is an upper bound on the machine's running time because。

😊，You know， if the machine has not exactly what he just said。

 if the machine is not halted after this number of steps， then by the pigeonhole principle。

 that means that it must have revisited a state that it was already in right because there's you know there's only this number of states in total okay but if it revisited a state that it was already in then that means that it is entered in an infinite loop okay if it's entered in infinite loop。

 then it doesn't halt and doesn't decide a language。

 so if it does decide a language then on every input of size n。

 it must halt after at most this number of steps everyone see that。Yeah。

why do I need this factor because there's some configuration of the tape square。

 the zeros and ones on the tape squares that you know。

 and there's two to the F of n possibilities for that。

 but there's also the position of the tape head。The tape head can be in one of F of N locations。

 we have to keep track of that as well， and then we have to keep track of the internal configuration of the machine。

 and that's this。Okay。So we can say。But this holds。Okay。All right。呃。

All right so the last thing that I want to do today is an important result called the time hierarchy theorem okay fortunately it has a quite simple proof and so the question we're going to ask now is you know we know that time n squared is contained in time n cubed for example right but is the containment strict in other words。

 is there anything that you can do in n cubed time that you cannot do in n squared time okay you know are there problems that inherently require n cubed time that's one of the most basic questions we could possibly ask here okay。

😊，So Hartmanis and Stns in 1965 proved。What's called the time hierarchy theorem。

They won the touring Award for it， okay。😊，And basically what it says is you know。

 it allows you to prove statements like this， okay， that using more time。

 you can decide more languages， okay， you know， and you know it's much more the true it's much more refined than this。

 you know， you know， you can do more in time of end the two。😊，3。1 than you can do in time of n cubed。

 you know and it's much more general than this， but just to be concrete， let's just do one example。

 let's just show why can you do more in n cube time than you can do in n squared time so you know and this will illustrate the general idea okay。

So what we want is to give an you know， it suffices to give any example of a language which can be decided in n cube time。

 but which cannot be decided in n squared time okay and how are we going to anyone have an example。

 social language yeah？这是呃。嗯哼。😊，All right， so yes， so that would be an example but what we mean by N cubeubbe time is time cubic in the size of the input so you've sort of violated the rule with that problem right so we need we need it to actually be cubic in the size of the input right and so in this case you know if our input is already N cubebe time then you know you could just do that in time linear or in N cubed right。

😊，Okay， so it turns out that you know the way that we know how to prove this。

 you know ultimately we would like to， you know someday we'd like to be able to do something better。

 but for now what we know how to do is prove this via a sort of scaled down version of touring's proof of the unsolvability of the halting problem okay so let me give you an example of a language L that we can prove is in solvable in n cube time but not in n squared time you might laugh a little when you see it。

I'm going to consider the language L that consists of all。

Descriptions of touring machines together with a list of k zeros and this is by the way。

 this is called encoding the integer K in unary notation just listing K zeros at just a very inefficient way of writing down k that will be useful for technical reasons such that。

😊，M， when given a blank input， halts。And at most， I'll say K to the 2。5 steps。You know。

 this just being something convenient， which is in between k squared and K cubed。All right。

This is going to be our example of a language that we'll use to prove this theorem so we need to verify two things first of all。

😊，That L is decidable in cubic time。 Why is that anyone？Just yeah just pretty much you take M。

 you simulate it， you run it for you know k to the 2。5 steps。

 which you know in terms of the total length of the input is at most end to the 2。

5 steps and you see if it's halted okay and you know the reason you know and that clearly takes less than n cubed steps right the reason why I want it a little bit of wiggle room here is that there's a little bit of overhead when you do the simulation right so that simulation won't take exactly end to the 2。

5 times it'll take a little bit more than that because you know there's overhead involved in simulating one touring machine by another touring machine you know it'll take something like n to the 2。

5 times log n time okay something like that okay if we use you know a RAM machine okay there's a logarithmic overhead that comes from the simulation okay but you know but at any rate certainly it'll take less than N cube time。

All right。 for now， we want to argue that this language is not solvable in n squared time。

 How can we do that， let's。Suppposed by way of contradiction that it was。

Sposed by way of contradiction that L is solvable in n squared time。Okay， then。

Then I claim that there would exist a touring machine， P， such that。Given， you know。

 if you give P description of a touring machine M as well as0 to the K， then P。

We'll do the following， and this should look pretty familiar to you。 P will run forever if。M。

 given its own code as input and given0 to the K halts。After it most。K to a 2。5 steps。Okay， whereas。

P。Should halt？If otherwise。ok。So do you agree that if we could decide L in quadratic time。

 then we could design such a machine and not only would it work but。But P would take， itself。

 it well less than k to the 2。5 steps。Okay for sufficiently large K Okay， well why is that Well look。

 know， you know whatever machine I have to decide L， right。

 I can use that as a subroutine right so I can now you know I'm able to solve the timebounded halting problem deciding whether machine halts in you know K to the 2。

5 steps I'm able to do that in quadratic time by assumption here Okay so now I'm given M I'm given0 to the K So now I can just you know you know run M you know with its own code as input and just like we saw before right there will be one touring machine you know take no input。

 but just the first thing it does is it write a description know of M onto its tape right so。😊。

So we can do that， right， and then you we simulate that machine you know， for it most k to the 2。

5 steps， we see if it halts。Okay and if it halt then we run forever and if it runs forever。

 then we halt okay and I claim you know that all of this right like like running the subroutine you know here take suddenly quadratic time there's again there's a tiny bit of overhead that just comes from the fact that you know that M and you know M zone description has to be counted as part of the input length okay but for you know but certainly all of this you know for K large enough is going to take you know let's say it'll take K plus the length of M squared time which again for K large enough is certainly less than K to the 2。

5 time can anyone finish this off can anyone give me a contradiction now。That yeah， I you know。

 I think Eric was Eric has。How did we do it I'm like Yes。

 now I'm going to run P given its as well as0 to the K and I'm going to ask what this does Okay you know if this thing halts within K to the 2。

5 steps then this runs forever you know by definition if it runs forever then it all you know。

 then it within K to the 2。5 Okay， so our conclusion is that this language L cannot have been solvable in quadratic time given more time you can do more than if you have less time and unfortunately we're out of time so will'll continue talking about time complexity and also about space complexity next Tuesday。

CoolAnd then we'll see P and NP them600。Do you have a Frisbee yet？You need to get one for the。

Theres the real often problem you don't have any a。あ全も。If you knew the I。えとじゃ。But you know。

 a machine that， you know， like， you know。Forever， it used forward。Exact。

 mean you can conclude something this from this， you can conclude that if a machine were to run forever。

In way we couldn't be the。It's the only way you can do。大か。すじゃ。Right。あ場。你这两天不来我约我。Yeah。

