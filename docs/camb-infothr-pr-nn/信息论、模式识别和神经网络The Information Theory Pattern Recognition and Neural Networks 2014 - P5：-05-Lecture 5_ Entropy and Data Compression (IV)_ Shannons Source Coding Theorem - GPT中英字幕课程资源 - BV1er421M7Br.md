# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P5：-05-Lecture 5_ Entropy and Data Compression (IV)_ Shannons Source Coding Theorem - GPT中英字幕课程资源 - BV1er421M7Br

![](img/476a1edd69e61529c60ad32a5d83441e_0.png)

Welcome to Lecture 5。In the last lecture， we defined symbol codes。

 and we asked theoretical and practical questions about symbol codes。

And that gave us even more evidence for these claims， which we've now proved sufficiently。

 I'm going to take them as true。 So the claim was that the right way to measure information content is with log base to of1 over P of an outcome。

 And that is not only a sensible measure of information content。

 It is how many bits you should expect to be able to encode that outcome into if you're using a good compression method。

The entropy is the average of the information content。And the source coding theorem says。

 if you've got a source with entropy H， you can compress N outcomes comes into N， H bits。

We looked at symbol codes where without punctuation， you give binary strings。

 strings of zeros and ones to each letter in your alphabet。

 And we established some theoretical results about them， some of them without proof。

So we came to an understanding of how unique decodability constrains the length。

 You can't make all the lengths really short。 You have to， if you make some length shorter。

 you have to make other lengths of your code words longer。We introduced the notion of prefix codes。

 which are easy to decode codes that are associated with binary trees。And we noticed that。

If you had code length equal to the information content， then you got the best possible compression。

 and the average length per symbol was the entropy。

And we stated without proof that with the optimal symbol code。

 you can get within one bit of the entropy。 And finally， we saw the Huffman algorithm。

 which is an algorithm extremely simple for making optimal symbol codes。

 So let's just recap that with these examples here。😊，So if the probabilities are。A fifth inch。

The Huffman algorithm says combine the two with smallest probability， you can take your pick。

It gives you two fifths。Combinine the two with small probability。

Then combine the two with small probability， again， take your pick。

And then combine these and we've got one， and then by putting zeros and ones on the edges。

We we can define codes。 This one is 0，0。 This one' is 0，1 coming down the tree。 This is 1，0，0。

 This is 1，0，1。And this one is。1，1，1。 What have I done wrong， I should say 1，1。Okay。Any questions。

So let's do another example。 So if the probabilities are proportional to 1，2，3，4，5，6，7。eight。9。

And 10。Huffman says。Combine these。And combine these to get six and combine these to get nine。

 then take the two sixes。You can get 12。Then，7 and the 8。To make 15。Then what？ carefully。

 we take the two nines。And get 18。Then who does 10 go with，10 goes with the 12。1822。

And then the two smallest are 15 and 18。Sing us 33。能力。Gives us 55。

And then we slap on zeros and ones anywhere you want。

 And we've got ourselves the optimal symbol code。For ensemble why。Any questions？Yes。

 so the question was， does the Huffman algorithm ensure that we've got a prefix code。

 And the answer is yes， because when we put the labels on， we're making a binary tree。😊。

And we're defining the code words from the root of the tree outwards。

 What we will get is a prefix code。 There's no way that one code word can be a prefix of another if they're defined in terms of a binary tree。

 So the Huffman algorithm always gives you a prefix code。And it's optimal。

 You can't make a better symbol code。 And you might think that that then wraps up compression。

One thing you might ask in addition about prefix codes is， is it sufficient to make a prefix code。

 If someone said， I've got a really cunning idea， I'm going make a code that is not a prefix code。

 and it's going to be better。 Can we prove that that is untrue。And the answer is， yes。

 we can prove it's untrue by the following fairly simple argument。

 Imagine that someone has made a symbol code， which they claim is wonderful。

 and it's not a prefixed code。 You say， okay， please tell me the length of all of your symbol codes。

 starting with the shortest length。😊，Up to the longest length。 Give me them sorted by length。

Then I'm going to go to the symbol code supermarket， which we introduced last time。

 and I will walk across it from one side to the other。 And I will buy the shortest code words first。

 And then having bought some short ones， I'll move across to the next aisle by some of the next length and so forth。

 in accordance with the shopping list that you have given me。

 And as long as you have given me a shopping list that doesn't exceed the budget。

 the craft budget of one。 Then I will be able to buy your lengths of。😊，Of codes。

And because Ive stepped across from one aisle to the next， as I went across。

 maybe I should make clear what I mean。 So let's say I had to buy two of length 2。

 And then you wanted one of length 3。 I'd get this one。 And then some the rest of length 4。

 Ill buy all these。As an example。 And because I'm moving across and never overlapping with myself。

 I'll end up with a prefix code because the only way you would violate the prefix property is if you bought two that are on the same vertical coordinate in the supermarket。

All right。So the Huffman algorithm is already optimal。 It makes prefix codes。

 So we didn't need to worry about this。 But if just in case someone was claiming， aha。

 I want to do something clever， not using prefix codes。 Well。

 whatever expected length they could have got with their non prefix code， we can match it。

 we can just replace their code by a prefix code。😊。

And the code I showed you for English here was indeed a code made with the Huffman algorithm。

 and it's a prefixed code。So have we wrapped up compression by saying。

 here's how to make symbol codes and here's how to make optimal symbol codes。 Well。

 for the rest of today， I want to argue that we're not done with compression。

 And the reason we're not done is because of this lurking plus one in the inequality。So。Are we done。

 no。Let me give you one really simple example to justify this。



![](img/476a1edd69e61529c60ad32a5d83441e_2.png)

And it's the example we started with， the Benco。Let's imagine we have a bentco。

 and its two faces are called A and B。 And let's say they have probabilities，99 and 。01。

And now I say， aha， I will compress it to using the Huffman algorithm because that makes optimal symbol codes。

 And you carefully find the two symbols with smallest probability。 You combine them into one。

 and you put labels on here and you say， I will encode code A as 0 and B as one。

 Isn't that wonderful。 It's an optimal symbol code。 It's expected length。😊。



![](img/476a1edd69e61529c60ad32a5d83441e_4.png)

Is one。And that is， indeed， close to the entropy。Which is 0。08 bits。

It's within one bit of the entropy， but it's actually about about a factor of 12 bigger than the entropy。

 And it's not compressing at all，ca it's just taking a binary alphabet and encoding it directly into binary with no encoding。

So that's a trivial example where simple codes clearly aren't getting us where we really want to go。

 Shannon says we should be able to achieve more than tenfold compression of that bent coin file。

So I'd like to now play a game with you。To help us understand the situations in which we might be dissatisfied about this plus one that's lurking in this inequality。

So。The game is called the guessing game。

![](img/476a1edd69e61529c60ad32a5d83441e_6.png)

And what we're now going to do is I'm going to write on the board。A headline。From a newspaper。

 and I have the headline written here。In front of me。And I'm going to write it with your help。

Because you're going to guess each letter of the headline as we go along。

 And if you guess the first letter correctly， I will write it down。 I will tell you it's correct。

 And then we can move on to guessing the second letter of the headline。

 And the alphabet of legal characters for this headline is on the board  A is Z。😊，And space。

And when we finish the headline， Ill， I'll let you know。 So I'll supply the。The full stop。

At the end of the headline。Okay。You can start guessing the first letter。

 and I will write underneath this line all the guesses that you have made that are not correct。

 And when I write above the line， it tells you that you've got the right letter。 So guessing time。

Not tea。Not a。S is not right。啊。啊。Keep guessing。And。A is right。 Next letter。嗯。He is wrong。A。

Do you say a。8ight。Oh。Iye is correct。 Next letter。Not as。Not tea。It's not L。 And I say again。

It's not G。En。Not I。I wouldn't say anything about ministers。Not B。A。啊。S。Space。It's not S。Notty。啊。

It's not S。Not they。Not an。Not see。Not P， not Q。Not you。Not G， not T。Not I。哎。Not a。Not， I。You。S。诶。

Space。Chief。Oh。Space。Not an。Not p。Not see。Not D。W。Oh。啊。Okay。It's not O。Not I。し。Not W。Was that Sagan？

Not F。Not you。Not tea。Not they。8。Not scarce。Not tea。Not n。哎。Hes right。Okay。

 I think I heard someone say P， and that was wrong。 And I heard someone say D， which is right。嗯。2。Ex。

Gce。Not H。Not a。Not tea。D。Not I， Not a。E。Hey。对。H， and I'll give you the end of file there。 Okay。

 so there are some minorrs who are perhaps reasonably refusing to work after their death。

So there's a headline， and it involved you acting as expert English speakers and using your knowledge about English to make predictions。

And I'd like you to notice some things about the predictions you made。The first thing is。

I think you are well aware that your predictive distribution。

 the predictions you would make at any particular point， change depending on the context。So。

 for example， the second letter， all of your predictions were vowels。

Because you were struggling to think of things that could have come after end that were not vowels。

 It could have been an N or something strange like that。So that's an example。

 And here was a context where you predicted K as your first choice。 whereas in a generic location。

 you say things like T， A， B and so forth。 So your predictions depended on the context。

And that's because there are correlations in ordinary English between the letters。

 You are aware of words and grammar， and so forth。So。I'm asking the question。

 what's wrong with symbol codes。 We could just use the Huffman algorithm if we used it once only and made the optimal Huffman code for the English alphabet。

It wouldn't correspond to a changing probability distribution。How could we fix that？ Well。

 in principle， you could fix that by saying， oh， let's run the Huffman algorithm every time。

 So we'll have some sort of process that emulates your expertise when we get to a particular context。

 we could then compress the next character using the probability distribution that is optimal for that context and make the optimal symbol code and then send the appropriate next three bits or two bits or one bit and the person at the receiving end could emulate that process of also figuring out which Hoffman code。

 which symbol code you are about to use for every character。😊，So you could do that。

 but that sounds a bit of a fff。嗯。And。There is a problem。

 which is that if the predictions are very precise。

 you'll still be spending  one bit for every character。So I'll write that down in just a moment。

 What's my second issue， My second issue is that the context dependent predictions。Also， change。

As you learn about。The style of the document that you're compressing。They change。

 We didn't really see this with the headline because it wasn't a very long document。

 But if I'd said here， here's a headline。 And if I'd started off。

 and I'd said I'd started writing out after you've made a lot of guesses。 Nime Fer andweiwe。

 you would have perhaps realized it wasn't an English headline。

 And so you would have then started learning about the predictive distributions that are appropriate for Swwahili。

So。Early on， you might not know Swhili very well。 as you get to the end of a very long document。

 you would have started learning the phrases and words of Swwahili。

 So your predictions would have evolved。 You would have looked back and seen， oh。

 he's repeating this， this long word again。 Let's try using that for our predictions。

So the predictions change in the sense that they become。More precise。And refined。As you get data。

 And then the third thing is what I just said a moment ago。Often。

 the predictions you make are very confident。And this is the most important fact of all。Often。

 your predictive distribution。Is very。Certain。And we could。

Confirm this just by keeping track of how many letters you。Got first time， or。O。

So let's count up how many guesses you made before you got the correct one。 So here you made five。

Guesses， can you see that on the camera， okay。Alright， here you made 1，2，2。

5 again to get the correct 1，1，2，3，4，5。So at the beginning of a word and at the beginning of a phrase。

 it's quite hard to predict what's going on。 There was quite a lot of uncertainty。

 Then we settled down3 guesses，1， guess， one， guess，1，3 again at the beginning of a word and one。

There，1，2，3，4，5，6，7，8， because we're still。At the beginning of the word， o， sorry，8，9，10。

11 is what I mean。 There are 11 guesses to get the F。3 to get the U。 And then it got easy 1，1。

1 guess，1 guess，1 guess，1 guess，1，2，3，4，5 guesses，1，1，1，1， M had 1，2，3，4，5，6，7，8。😊，1，2，3。

4 and two guesses and one， one， one。4，3，1，1，1。 So it would have been fairly extraordinary for you to have so many oneands in there if it weren't actually the case that you really were quite certain about those particular predictions。

 I didn't elicit from you exactly how as you were， but we could have gone through some process of figuring out your odds。

 if I'd offered you money and that sort of thing。😊，嗯。

So often it's the case that the next letter is highly predictable。So what am I saying。

 I'm saying that a typical。Context。Depenent prediction。

That we could then feed into the Huffman algorithm。For example。Looks something like this。

 There'll be some letters that are not very likely。

 There's the one letter that you're pretty damn sure is going happen。

 which maybe has 99% of the mass， and there'll be a load of other letters。

Which have very small probability， so maybe your predictive distribution looks something like this。

So here's a cartoon of a predictive distribution。That。Has 10 letters that are possible。

 but not very likely。 And one has 99% of the mass。Let's run the Huffman algorithm on this。

 You do kju，unk kju。 And at the end， you combine this with all of the others。Like that。

And that gives you your optimal symbol code。 if we were insisting on using symbol codes。

 The length you will get has to be bigger than 1 B。 The expected length， because every。

Code in a symbol code is at least one bit long。 Yet the enpy of this distribution。

A bit like the bent coin we had earlier is 。11。V。So what's the fundamental problem with the symbol code。

If you use a symbol code。😊，You're obliged。Two minutes。At least one。Bit。Her source character。

And that's lausy， because the entropy。May often be much smaller than 1 B per character。

So you have to do this， even if。The enthtropy is much smaller than one。Now。

 one idea for coping with this situation is to say， oh， well， I do love Huffman codes。 Oh。

 I wasn't meaning to write， write this off yet。 Sorry， let's put it back。

Instead of using Huffman codes in this dumb way， I could try and be a bit smarter。 You could say。

 let's encode blocks of characters together。 And so you could take n characters at a time and say。

 I can kill off this problem of one symbol by itself being very probable by having blocks of say。

6 characters at a time or maybe 16 characters at a time。

 And then I list all possible blocks of 16 characters and ask the audience what the probability of all。

😊，50 to the power 16 character sequences of length 16 is assuming an alphabet of size 50。

And then we can use the Huffman algorithm to encode the blocks。Or you could say。

 let's think in terms of runs。 We could say how many runs of ones are there in here。

 We could ask the audience to predict how long do you think you'll get ones for before you get it wrong。

And I could ask you for bets on that number of how long the run is。

 And that'll give an integer that was sort of 0。 And it was 5 guesses 0 from 5。

 And then there was a run of length 3。 And then there were three guesses and so forth。

 So we could encode into a different alphabet where we talk about run lengths。😊。

And then use the Huffman algorithm。 and there would say few。 Oh， yes， we can still use Huffman。

 but maybe。We're finding this all a bit complicated。

 And maybe wed like to move on and say that there's a better way than simple codes。

 And that's the message of this lecture。So。If you were to do what I just described， for example。

 encoding blocks of characters， you would have to compute lots more joint probabilities。 if。

 if we'd got up to this point， I would have been saying you， okay， R E F， now， tell me。

 what do you think the the next five characters might be。 Guess the next five characters。 Okay。

 Gu again， Gu again。 Yes。 And I'd be implicitly running through a great long list of possibilities for the next five characters。

😊，Which you would have to actually compute， even though only one of those five character sequences is actually going to happen。

 So you' would have to think about many more possibilities。So， in summary。

What we would like is a solution for data compression， where we can use。Context dependent， adaptive。

 probabilistic models。 So we want to allow context dependence。 We want to allow for adaptation。

And we want to be able to handle very concentrated probability distributions。So here's my summary。

We want a method that can handle。Context。Depenent。Adaptive。We're allistic。Models。So， we want。To use。

What。And。We want to get rid。Of the symbol codes gap between L and H。By handling strong。

 certain distributions well。Okay。I'm about to tell you how to solve this problem。 But first。

 let's just think of something we can do with this board before we wipe it off。

Here's a game we can play。I'm going to write down the green integers on a piece of paper。

So how many guesses did you need for the first character。5。5 for the next，5 for the next，3，1，1，1，3，1。

11，3，1，1，1，1， and so on okay。And I could write down those integers on a piece of paper。And now。

These integers contain enough information to reconstruct the headline。Sort of。

Imagine that through this wall here， there is another lecture theatre identical to this one。

 identical in the sense that it's got a lecturer in the front。Who's my identical twin。

 And all of you in the lecture theatre are also there in the form of your identical twins with exactly the same thoughts。

 beliefs and predictions。 And we post this。Through the wall into the other lecture theatre。

And now I come in and I say， okay， we've just talked about symbol codes。

 and now we're going to play a guessing game。 And I'm going to tell you a headline that I've got written。

 Thank you very much on this piece of paper here。😊，Okay。

 I've got a headline and it it uses this alphabet here。 and please start guessing。

 And now you make guesses。 and you say T。 and I say no， I say you say a， and I say no， you say S。

 you say And then when we get to the fifth guess because it says5 on this piece paper。

 someone says M And I' say， yeah， that's what it says here。 Okay， and we we get the M。

 And then we keep on going。 And by me stopping you whenever you guess the right number。

 And because we're perfect identical twins of the next door lecture theater。

 we would end up writing down exactly the same set of letters on the board。

 we would go through the the same reasoning process and we would end up with the headline。😊，Okay。

So that's a fun idea that we couldn't quite implement because we haven't all got identical twins。

But it's the， it's at the heart of all state of the art compression algorithms that you arrange to have identical twins at the two ends。

 and those identical twins run for us。 this context dependent， adaptive。

 probabilistic modeling in software。 Yes， question。😊，The question is。

 are we assuming that it's a deterministic universe。

 So the identical twins would exactly replicate us。 Yes， for the purposes of today。

 the universe is actually deterministic and your identical twins would behave exactly the same as you。

 That's the analogy Im， I'm assuming。😊，Okay， for this to work in real life。

 we need to ensure that we have deterministic computers。 So the adaptive。

 probabilistic model that I'm talking about will be a computer program that tries to emulate an expert audience like you。

And we will have one copy of that program at our encoding computer。

 and we'll have an exactly identical， deterministic copy on another computer that will work in exactly the same way so that we can replicate your guesses and your predictions。

😊，Okay， so how do we do that， Well， first， I'm going to introduce an encoding method called arithmetic coding。

And。I'll introduce it to you using several toy examples。One of which will be the。

 the whole identical twin。Scenario， but we'll start with slightly simpler。Examples。

So let's give ourselves three tasks。These are tasks that are simpler than the general desire that we have on the board over here。

They're simpler， but they have the， the essence。Of the problems we're grappling with。

The first example is going to be the bent coin。And we might have a bentco with probabilities， A， B。

Equal to， I don't know，99。01。So we already know that symbol codes struggle with this。

 We have to do something clunky with symbol codes to get any compression for the bent coin。

The second example that we'll discuss。Is going be the unknown。Bentcoin。So I could tell you， look。

 I've got a bent coin in my pocket。It has been used to generate a great big file of A's and B's。

 And that's all I'm telling you。 I don't know what the bias is。

 but you do know that it's a biased coin。 You just don't know what P A and P， B are yet。

And nevertheless， on the fly， I want you to start predicting just like the， the headline。

 you didn't know what language you were in。 You didn't know what it was about。

 And as we went along on the fly， you started to figure out what sort of topic it was。

So an unknown Benco。 And so a typical outcome might be lots of A's in just a few B's。

 or it might be lots of B's in just a few A's。 And you don't know in advance which of those is going to be the case。

And the third task we'll discuss is the general。Situation where an oracle is available。

And the Oracle's job is given any context， X1， x2， x3， up to X T -1。

The oracle will supply you with the probability of the next character。

 which you should assume is the correct distribution for the for that next character。

 And there will be an identical twin Oracle at the other end who will produce exactly the same distribution in response to。

That same context。So this is any context。And then the question is。

 how should you compress when you've got that oracle Now， the oracle is actually a complete。

 completely general statement of the compression problem。

 because the bent coin could be produced by the oracle， he just ignores the context。

 And he says A has probability 99%。 and B has a probability of 1%。

 So the oracle has the trivial cases in it as well。

 The way the oracle would do the bent coin thing is given the context。

 he would look at how many A's and B's have happened。

 he would make an inference of what do I think P and P B might be and take into account that uncertainty about P and P B in making his next prediction of whether he thinks the next one is an A or a B。

 So his first guess with no context at all would be well，5050。 I don't know。

 it could be biased to A's or B。 I don't know。 So it would be 5050。 Then when he sees an A。

 he might say， well， that's weak evidence for it being biased towards A's。

 And hed give a slightly bigger probability to A。 And his identical twin would behave in exactly the same way。

Okay， so that's the three tasks that we want to solve。And now， we are going to define。

Arithmetic coding。I should mention in passing that arithmetic coding is not the only other way of doing data compression。

 apart from symbol codes， But in my view， it's the only other one that is really worth devoting a lecture to。

 There are many other algorithm， some of which are quite elegant。 But for me， arithmetic coding is。

 is the king of compression。So do feel free to leave read the。

 the textbook and the literature to learn about other compression methods。

 So here's how arithmetic coding works。😊，Arithmetic coding is based on this idea。

You can view any transmission。In a binary。Alphabet as defining an interval on the real line。So。0，1。

 for example。Is a little binary string。And you can view that as corresponding to the interval from0aught 。

25 to0ughaught 。5 in decimal。1，0，0。We can associate with。The interval from0aught。5 to0aught。6 to5。

What we're doing is we're taking the symbol coding supermarket。Here。And viewing。

The top of the supermarket as being the real number 0 and the bottom of the supermarket is the real number  one。

 And any particular interval， you can see0，1 lives there。

 It goes from quarter of the way down the supermarket to halfway down the supermarket。 Alright。

 so we're just taking the super the supermarket， literally as a real line。😊。

And something you can notice about the supermarket is as you go to the right。

 if you lengthen a string from， say 0，1 to 0，1，0， the interval associated with that lengthened string is a subinval of the interval you started from。

 So as you lengthen a binary string， you're always defining a subinterval。

 You're either halving this way or this way。 and you're going half， half， half， half， half half。

 and you're always ending up inside the place you were a moment before。😊，So what are we saying？

We're saying that you could imagine any binary file having a little dot at the front of it。

Called the decimal point or a binary point。And then。The remaining characters。

The binary expansion of a real number。So， for example。Any one megabyte file。

Which begins 01000 and keeps on going。For8。Million bits， because that's how big a megabyte is。

Any 1 MB file defines a single real number with a precision of about 8 million binary digits or 2 million decimal places。

Any one MB file defines。A real number。To roughly。2 million。That small places。Of precision。

 And if you。Add another megabyte of binary to it。 You've defined it to another 2 million decimal places。

Okay， so an entire file is sending just one number。So what do we need to do next？ Well。

 we're going to use the probabilities produced by our model。Which is either the Bencoin。

 the unknown Bencoin or the oracle。We're going to use the probabilities。From our。Adaptive。

Context dependent， probabilistic model。To subdivide。The current interval。And initially。

 the current interval will be the interval from 0 to 1。 So we'll ask our probabilistic model。

 what's the probability of A， B and C， And it might say 42。5%，42。5% and 15%。Hopefully。

 those add up to 100。For A， B， and C。And then you say thank you very much。 I'm now going to ask you。

 given that the first character in the file was actually a B。

 please tell me the probability of the possible characters in that context。

 And then we will subdivide that interval recursively using the probabilities that come from our expert from our oracle。

😊，So let's show you this now。Okay。Alright， so here we have a little gizmo with two real intervals in it。

 and they are the same real interval， and we can subdivide them in binary。咁撒咁仨咁仨。

So there's a symbol coding supermarket appearing。And we can pick any probabilistic model you want。

 at least within reason。And use it to subdivide this world using the probabilities which here are a 42 and half percent。

 B，42 and a half percent， C，15%。 And if we're dealing with a fixed bent coin。

Or a fixed probability distribution。 You can keep a fixed probability and subdivide a。

A's interval using the same probabilities， A， B， C， and recursively do that。 B。

 subdivided in the same way。 C divided in the same way。And so， forth。So， you can。

Identify on the left hand side。 if you， if someone's given you a file。

 you can ask the oracle for the probabilities。And then you can identify the interval associated with the file that actually happened。

Similarly， on the right hand side， you can then hunt around and to find a binary string。

That lines up pretty much exactly with the interval on the left hand side。

And then the method of encoding is going to be that。We encode the entire file。Not just one character。

 the whole file。The whole file X， which is the first character， second， third， up， up to n。

 which could be millions of characters in length。We encode the entire file， by。Transmitting。

A binary string。Who'se interval。Lice。Within。The source strings interval。So。

In the very simple case where the entire string was just B， followed by C。

That binary string we would find over here。 We would subdivide and subdivide again and then subdivide again either this way or this way。

 we'd look， and we'd find ourselves a binary string。 How about。That one， the。

That binary string lies fully inside that interval。 so we could encode B， C as。

Let's give ourselves all some zeros。ones， zeros and ones， zeros and ones。So it's。

 it's getting encoded as one。1。0，0，0。All right。And I emphasize， we do this for the entire file。

 When you've got the entire file， you find the binary interval。

 And so you find one great long binary string whose interval lies inside。The corresponding one here。

 So let's do this for the bent coin。 So let's give ourselves a bent coin。

 Let's reduce the alphabet size to 2。And let's say that the probabilities。A whoops。M。

The probabilities could be fixed to be。Say0。9。And。Not 。1。 So I've defined my。

Language model to be the first task， Benco。And we revisit this。Okay。How are we doing？啊。

So now I'm using the bentco。 And let's imagine that what happens is。AAAABAA。

We'll talk about the details of exactly how you terminate files at a later date。

 I just want to show you where we find that interval。 So on the left hand side。

 we've used A B to subdivide。 and we can keep on using that。 And on the right。

 we've got ordinary binary land。 and we want4 A's followed by a B and two A's。 So A， A， A， A。

And then we want to be。 And so we go into here， and we go zipy zoom。 and in here。

 we get ourselves two more A's。 And so here's the interval。 It runs from there to there。

 And on the right hand side， here's binary land。😊，And we've zoomed in in exactly the same way。

 into binary land。And so this string here is the sort of thing we're after。

 And if we keep on going and just keep on getting ourselves more A's and B's。

You can see how the string on the left hand side is getting long。 It's now got。

About 100 characters in it。H H。Okay， so up to 92 characters。 And on the right。

 we've got the corresponding binary string， which is only about 48。It it's long。

 What have we have achieved， A factor of two compression。 What's the entropy of。Noe。9，0。1。Well。

 it's about a half。So we are achieving the compression that Shannon said we should be able to achieve。

 We're reducing the number of binary characters by about a factor of two for this bentco。😊，Alright。

 what about the Benco with an unknown bias。呃，这种。We could。Say that we don't know the probability。

So I've pressed the button called adaptive。 And what does adaptive do， Well， it says。

 what should we guess to start off with， Well， it's 5050 because we don't know the bias of the bent coin。

 But once we've seen an A， then that makes it slightly more likely that we'll see an A as the next outcome。

 because it could be a strongly biased coin， or it could still be in favor of B's。

 but that's a bit of an unlikely proposition。And so let's imagine that A A， A， A B A A happens。

So as we keep on going in here， tom to。This is two A's。 This is three A's in a row，4 A's in a row。

 And then we get ourselves a B。日。Let's zoom in a little bit。Wops， too much。Okay。

 so here's the three A's and a B。 I think How many do you mean4 A's and a B， okay。

So here's our adaptive model using probabilities that depend on the context。

 And let's imagine having put in4 a's and a B。 so that it's looking like a as the winner。

 you just keep on going。 It turns out it was an enormous fluke that A was actually the improbable character。

 And so you keep on going。 And you get yourself a load of B's。 then another B and then another B。

 See what's happening to the predictive distribution is's gone back in favor of Bs。😊。

And so even though early on， it looked like a was the winner。 We get lots of Bs， and we end up。

Devootting more of the real line to bees。 And that means that the binary string is getting shorter than what we started with。

Okay， so we can do unknown bent coins， and we can do oracles as well。 So let's rewind。

So let's give ourselves an English language model。 So what's the first character gonna be。

 Well it's a is Z or space。 So we toddle into the box。 and here's A is Z。

 And here's binary land on the right hand side as normal。

 And let's say that we have the quick brown fox jumps over the lazy dog。So we going in here。

 the gick。Q and notice after the Q， the language model says， oh， I've just seen a Q。

 So you must be very probable。And it's devoting about half of the probability distribution to。

 to you。 That's the sort of oracle that we've got。 It looks at the context and modifies the predictions accordingly。

 It also puts quite a lot of probability mass on the space happening after Q。

 because I trained this on a Linux fact。 And it has the word fact in it lot。 F A Q。

 followed by a space。 So that's why that's the second most probable character。😊。

And so we can keep on going the quick。嗯。Where's it gone quick？Brown， fox， and so forth。

 So we zoom in on the left hand side。 And on the right hand side， tied to it is a binary world。

 And if you now send that binary string to someone at the other end。

 they start with exactly the same tool in exactly the same state。 And they just need to memorize 1，1。

0，0，1，1，1， etc ce。Which I can't do， oops。So we initialize the tool in exactly the same state。

 and we go in here and we say what was the message， It was 1，1，0，0，1，1，1。 And we toddle into that 1。

1，0，0，1，1，1， and so forth。 And on the right hand side。

 you can see the quick round Fox should indeed be coming out because we've got identical twin pieces of software at the two ends。

So， that's arithmetic coding。So。Let's emphasize。How wonderful arithmetic coding is。First。

 result that。We should。Give evidence for is that this really is almost optimal。So， let me。

Write down a theorem for you。The length of that binary string。

That I just mentioned a few minutes ago， the one that we send， the length of that binary string。

Satisfies this。 I'll call it the length of the encoding of X 1 to X， N。 It's less than or equal to。

The Shannon information content。Which is what Shannon says it ought to be。

For absolutely perfect compression is less or equal to that， plus 2。

So the entire length of the whole compressed file is only 2 Bs longer than the optimal length that Shannon would like you to have。

And something to really emphasize here is when you compare that with what we could do with symbol codes for symbol codes。

 the length that you got per character was with when one of the entropy。

 And so that means the possible overhead on a file with n characters in it， could be as big as n。

 an overhead of n， which could be enormous。 This is an overhead of only  two bits for the entire file。

 So it's a factor of n smaller than the overhead you get with symbol codes。😊，Why is this the case。

 What， Why is it that we end up with the optimal length。 Well。

 if you just think about the subdivision process that we're going through。The first。

Interval has a size equal to the probability of the first character， given your model。

 Then you subdivide it in proportion to the probability of the second character。

 given the first character。 So here's。That alphabet of possibilities。

 and the product of those two is equal to the joint probability of X1 and X 2。

 just by trivial probability theory， yeah。And then when you subdivide again。

 you take that interval whose size is x1。And next 2， So I'll copy this here， and you subdide。

And you say， this is the probability of。You， you subdivide it in proportion to the probability of x 3。

 given X 1 and x 2。 If you multiply this length by that fraction， you get。The probability of X 1。

 x 2 and X 3， and so forth。 So the size of the interval that you get on the left hand side in the alphabet world is exactly the probability of the string。

Now， when you find a binary interval that lines up with that interval and that fits snugly inside。

 if it fitted perfectly snugly。Then how many bits do you need for that binary string？ Well。

 each time you， you start with one， then you get a half and a quarter and so forth。

 So the number of hlvingings you go through is the log base 2 of the size of the binary interval you end up with。

 So if it fits exactly snugly， then。The length of the binary string will be be exactly equal to the number of factors of 2。

That this。Number here is smaller than one， which is log based  two of1 over P。So， for a snug fit。

You will end up with a binary string of exactly the optimal length。In practice。

 you won't quite have a snug fit， but it's an exercise in the book。

 You can do the exercise and prove that in the worst case。

 the worst non snug fit you can end up with will be that the。

Bary string is a factor of 4 smaller than the alphabet string。

 So you only need an extra 2 Bs to be guaranteed that you found a binary string that lives inside。

Okay， so that's fact number one。Which is brilliant。And note number two。

The other thing I want you to note is， how much work is it to do all this， What did we need to do。

 Did we need to think about all conceivable strings that could happen？ No。

 we only needed to think about the probability of the first character。

 Then the probability of the second character， given that particular first character that had actually happened。

 Then we needed to think about the probability of the third。

 given the actual context of what had happened。 So the work required was only this we only needed to compute。

And。Conditional probability vectors， or to describe it in terms of the actual probabilities。

 If I is the alphabet size。We only had to compute n times I。Conditional probabilities。

And then we just had to do a load of zooming and bit shifting in order to keep track of the arithmetic。

So that's a lot less work than the methods we were imagining we might have to use to cope with bent coins using symbol codes。

 when we said， oh， let's put them into blocks。 and you can have a block of 10 possible outcomes。

 Well， then you need to think about two to the 10 strings every time you read it in another 10 characters。

 So there could be very large pre factors here， we only had to think about N I things。

 N I conditional probabilities。 How could it be any smaller。 Well， it can't。 This。

 This is a fairly small amount of work that you have to do。😊，Note number 3。

 another beautiful thing I want you to notice about arithmetic coding is it's compatible with any source alphabet。

😊，And any transmitting alphabet。As we went through the examples， I gave you a ternary alphabet， ABC。

 Then I switched to the Benco， A And B， Then I switched to English with A to Z and space。

 You can use any source alphabet。 And on the encoding side， on this right hand side。

 we didn't have to use。😊，Binary。We could have used。Turernary， so from now on。

 heres a turnernary file that's coming out with some zeros， ones and twos in it。

 So you can encode into any alphabet that you want as well。

 It's a very beautiful framework for doing compression。😊，Arithmetic coding is widely used。

It's not super well known。But it is in many of the state of the art。Compression standards。So。

 algorithm coding is。Used in， for example， J big。Which is a binary image compression。Standard。

It's in a language model called PM， which is very widely used。In text compression。And it's in。

A document compression standard called deja vu。A final thing to notice about arithmetic coding is it completely separates probabilistic modeling modeling from encoding。

 There are many compression algorithms that are sort of computer hacks。 They say， okay。

 look at the source file， do this and do this and do this and list things and alphabetize them and so forth。

 And then there's some rule for converting that into binary。😊，Here。

 the task of probabilistic modeling is a task for oracles。 So you。

 you should do artificial intelligence and make really good oracles。

And then when you've made a really good oracle that understands how to predict your language。

 arithmetic coding steps in and tells you how to turn it into binary。

 So there's a complete separation of the task of artificial intelligence from spitting out binary strings。

 And that feels much more elegant to me than many other compression methods。

 which may have some sort of asymptotic optimality property。

 but they tend to fudge together these two issues。 They fudge together the probabilistic modeling and the coding task。

😊，Next time we will move on to our next topic， which is going to be communication over noisy channels。

 But I will tell you just a few more ideas about arithmetic coding。

 I'll kick off with one which you will no doubt have noticed during this talk。

 which is that you can do other things with this arithmetic coding concept。😊，So what I just did。嗯。

A moment ago there was I was demonstrating an arithmetic coder。

 but it also looked as if I was writing with the mouse。 and indeed， I was。 so we can take。

Athmetic coding concept。And make a writing tool where with my real number generating device called a finger。

 I can generate a real number just by moving the mouse up and down。And I can write English。

 I can write any string that I want in any language at all。 I will write in English for you。

 Pick a sentence。 Let's talk about efficient generation of samples from ensembles。 So off we go。I F。

Oops， I got lost。Forgot my alphabetical order。 That's a lousy demo。 Alright， we go， no， efficient。

Generation。So I'm just moving the mouse up and down。And simply by moving my finger。I can write text。

And this is a writing method that can be driven by any muscle。

 any muscle that can generate real valued signals so I can use my muscles to move the mouse up and down。

 and out English text at the top。This is a record breaking method for communicating English with very small numbers of muscles with just a mouse。

 Some people can write at 40 words a minute。 So 40 words a minute with just one finger。

 It's also possible with a gaze tracker to use no hands at all to just look with your eye in this world where you want to go。

 And again， it's possible to write at about 30 words a minute by gaze alone thanks to the wonders of arithmetic coding that allows you to get the maximum information content out of the gestures that can be quite painful for disabled people to make。

😊，So that is called dashher。 Dher is essentially arithmetic coding turned on its head。And。

So D's free software。 It's available from the Dher website。

 And I encourage you to tell everyone about it。😊，A question that I will ask you next time is a final question about data compression。

 Here's the question。 If we've got an alphabet， ABC D with probabilities a half a quarter an8 and8。

 If we use this symbol code， So going back to symbol codes。

Then what's the probability that a bit plucked out at random from the encoded stream will be a one。

 We'll discuss that question as the first thing we do next time。 And as last time。

 I'll remind you that there's a list of exercises on this slide here。

 which I encourage you to do as part of this course as well。



![](img/476a1edd69e61529c60ad32a5d83441e_8.png)

Thanks very much for coming。 Sorry， I ran over。

![](img/476a1edd69e61529c60ad32a5d83441e_10.png)