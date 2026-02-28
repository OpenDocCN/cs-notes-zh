# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P4：-04-Lecture 4_ Entropy and Data Compression (III)_ Shannons Source Coding Theore - GPT中英字幕课程资源 - BV1er421M7Br

![](img/6ca8d674d887e969d661f4ab4a3750b7_0.png)

Thank you all for coming。 Let me recap what we did last time。

We've started talking about source coding， also known as data compression。

We've been looking at toy examples。 One example of a redundant file for us to compress is something that's mainly zeros with just a few ones scattered at random。

 So we call that the bent coin。How should we can compress a file like that。Well。

 when we're thinking about compression， the claims we're examining are Shannon's assertions that if you take log base two of one over the probability of an outcome。

 that tells you how much information content that outcome has got。

 And it's how long the message ought to be associated with that outcome in bits as well。

 It's the ideal message length。The entropy， which is the average of the Shannon information content。

 I claimed to be the right way to measure average information content。

And the third assertion that we've got and that we have sort of proved last time is the source coding theorem。

 which says that if you get a very long string of outcomes from a random source identically distributed。

 then those outcomes can be compressed into roughly n times the entropy bits。

So we sort of proved that last time we did this proof by counting the typical set。

 We didn't actually do a general proof。 That's in the book。

But what we did was we looked at a special case of the bent coin where you to it n times and get mainly zeros and a few ones。

And there we all know what the typical set is。 you expect to get roughly。

 if it was a bent coin with a bias of 10%， you expect 10% ones。

 And the typical set of strings is all the strings that have roughly 10% ones。 So in general。

 what the typical set means。 And this is a defined concept。Is。If you get a string of n。

 independent outcomes from a source， that string。Is very likely to be in a typical set。

 The typical set elements all have roughly the same probability as each other。

 and there are two to the n times the entropy of them。

 So the rough proof of the source coding theorem is n。 Well， just give a name to each of these guys。

 The number of names you'll need is2 to the n times the entropy。

 So the length of all the names will be n times the entropy。

 And they've incidentally all got roughly the same probability as each other。

 which must therefore be two to the minus n times the entropy。

 So that's the very rough outline of the proof of the source coding theorem for a general source。

 And we did it for the bent coin。 looking at a long string of n。Outcomes。

 and the way we found ourselves at the proof was we imagined playing the bentco lottery。

 We wanted to win the lottery for the mafia boss。 How much of his money did we need to spend。

 Which tickets would we buy。 Well we found this big sack full of tickets。

 And then we imagined writing a new name for each ticket on the reverse of the ticket。

 We counted the number of tickets in the bag。 And we found we had two to the end times the entropy。

 So that's what we did last time。 that was our proof of the source coding theorem。

 at least for the bent coin。😊，When I said the number of tickets in the bag is2 to the n times the entropy。

 It's2 to the enpy。2 to the n times the entropy plus a little bit。

 And that little bit is to do with the fluctuations around the mean of the the typical number of of ones。

 Those fluctuations go as square root of n where N is the length of the string。

 So they get relatively small compared to this the main term N H2。

 And here's just a picture reminding you what a Gaussian distribution looks like。

 And you can get the probability down as small as you like。

 The probability of failure as small as you like。 just by adding a few extra square root of ns。

 a few extra standard deviations。😊，To your typical set。Alright。

 so that was a ridiculous way to do compression。 It involved a very large bin bag full of tickets that you wrote things on the two sides of。

 That was our compression and uncompression algorithm。 Now， for the next two lectures。

 we're going to discuss practical data compression。 How would we compress a bent coin。😊，Practically。

 well， that's actually a homework exercise I set for you。 So I'd like you to work on that。

But we'll carry on working on other approaches to related problems。

 And I'm going to talk today about a method of doing data compression called symbol codes。

And the idea of a symbol code is it's something you could apply， for example。

 to English or to any language that involves an alphabet of characters where some characters are more probable than others。

And to make life especially simple to start with， I'm going to pretend that the probability distribution for every character is the same every time and that we know that distribution。

And we'll usually assume that it's non uniform。 So here is what that distribution could look like。

 Here's an alphabet of 26 characters plus space， So 27 in all。

 and a probability distribution over those。 And you can see space is the most probable character。

 And then we've got E， T， A， O， I， N， H S， HD L that that sort of stuff。

 So it's this is like an English language distribution。And the task now。

Is to give a code word to each of these symbols in the alphabet。

 to each to each of these elements of the alphabet。

 And here's the example of what those code words could look like。 We're going to encode inter binary。

 and we've given a， the code word 4，0s。 and we've given Z the code word 1，1，0，1，00，1。

 and space has got 0，1。😊，So that's an example of a code。

 And the way you use a symbol code is you take the source file and you replace it by the corresponding code words in order。

 concatenated with no punctuation at all。 So the receiver won't be able to see where the boundaries between the code words are。

Okay。So。A symbol code is going to be a map。

![](img/6ca8d674d887e969d661f4ab4a3750b7_2.png)

From each symbol。X in your alphabet。2， we'll call it C of X And C of X is a binary string。

And as you can see here， it can be of， of any length。 And the way we write that in set notation is。0。

1 is the set with 0 and  one in it。 and 0，1 set with a plus means the set of all strings of any length made up of zeros and ones。

嗯。That may be familiar to those of you who hang out with computer scientists。

 Let me give you another example，0，1。To the power 2 is the same as the set of string 0，0，0，1，1，0。

And won one。Okay， so that's just a little bit of a notation。

A symbol code is a map from symbols to binary strings。

 And then the way a symbol code works is we encode。



![](img/6ca8d674d887e969d661f4ab4a3750b7_4.png)

The string of outcomes， x 1， x 2， x 3。X N by concatenating without punctuation。

The code word for x 1 and the code word for x 2， the code word for x 3。The code red。ExM。So。

I'll just give you an example。If we gave a the code word。Wman。C， the code load 0，0 and C 1，0，1，1。

 then。The file containing C， AB， B would get encoded as 1，0，1，1，1，0，1，0。爆了。0ah。Okay。

So that's a fairly simple idea。 But now we need to get our head round these symbol codes。

 understand them theoretically and understand them practically。 And these are quite important codes。

 They're quite widely used， especially in， in history。

So the questions we want to ask today are the theoretical question。

 how well might a symbol code perform。And what we're anticipating here is maybe the answer will have something to do with the entropy and Shannon information content and that sort of thing。

And that would， again， reinforce the claims we've been asserting。And then the practical question is。

 hey， stuff theory， I just want to know how to make a good one。 How do we make good symbol codes。

And when we say good or optimal。We need to define what we mean by。Opttimal， so let's do that。So。

What do we mean by optimal。 Well， we're after compression。 So we want a short expected length。

 don't we， So we'll use that as our main objective function。 So there may be others。

So we'll define the expected length of。A code。C。For an ensemble。

X on the ensemble being the alphabet with all its probabilities。

Will'll define it to be L of C And X is some overall your elements in your alphabet。

And multiply the probability of。That outcome by the length that you have assigned。

 where L I is the length。Inbits of。The code that you've assigned to the I。Element， okay。

 nothing profound going on here。 I'm just defining the expected length。

And it's probably a good idea to immediately use an example。So let's give ourselves an alphabet。

 and the alphabet is going to be a。The。B滴。And let's have a probability distribution。好。我操。1，8。1，8。

So this is a toy probability distribution with uneven probabilities。

 One thing we might want to know about this。Ensemble is what is its entropy。 And the answer is， well。

 it's a half times 1。Plus a quarter times two。Plus， an8。Times 3， lesson 8。Times。3。These 1，2，3。

 and 3 being respectively the logs base  two of this， this， this and this。And that is。我能听故事。So。So。

Let's give ourselves a symbol code and then try and make it better。

 And we need to pin down what the rules of the game are actually going， going to be here。嗯。

So what do we want， Let's， let's define the。The rules。First， and then look at some examples。

First of all， is it had better work when someone encodes with this and then someone else decodedes。

 They better get back what we first put in。 So what comes out must be what comes in。嗯。

We want it to decode。Correctly。And we want it to guarantee to decode correctly。

 not just to have a 99。9% chance of working， which was already quite good in our slightly silly approach of last time。

We want it to always decode correctly。So。Let's justify our other rules。

 And then I'll say a bit more precisely what we， what we mean by I M S。Ideally。

 we'd like it to be easy to decode as well。 So we don't want to have the recipient having to spend hours staring at the codebook。

 trying to figure out where the punctuation， where the missing punctuation marks go in the。

 in this received string。So easy to decode would be nice to have。😊，But it's not essential if。

 if we can get a big win on this final objective， which is the small expected length。Small L。Okay。

Okay， let's just be precise about what we mean by is got to decode。 right。

 We want the code to be uniquely decodable。So when you receive an encoded string。

 there should be no ambiguity about what was sent， so。For。Any。String X。And any other string， why。

Such that。X is not the same as y。We want the encoding。Of x。To not equal the encoding。Of why。

So that's the definition of unique decodability。Okay。And just to check， my notation is clear。

 C of AI is the way we encode a particular element of the alphabet。

 And then if we have C of a string like X， that's just the concatenation of X1。2。Okay。

 so I'm overloading the symbol C to mean， either the way that you encode a single symbol or it could be the encoding of an entire string。

Alright， okay， we've got ourselves an ensemble。 Let's define。

Some simple codes and have a think about these objectives。

 What does it mean to say it's got to be uniquely decodable。 What does， what does that imply。

 How do we get a small， expected length。Is this a good start for English。Could it be made better。

 Is it uniquely decodable。Let's look at the simple example。 Let's define a code called C1。

And its code words are going to be。1 and three zeros。0，1，0，0。0，0，1，0。And three zeros and a one。

And I've deliberately made them all four characters long because now we know the recipient will be able to put the punctuation marks in the right place because they're all four characters long。

 What's the expected length of this， Well all code words are four bits long。

 So the expected length is also 4。Right， can we improve on this， Is this， I this the best possible。

codeode for this。Unemble。Any suggestions。It's got rather a lot of zeros in it， hasn't it。

 Should we get rid of some of the zeroes。😊，Would that work。Who you're being China today， yes。

Get rid of the trailing zeroes。 Brilliant。 Thank you。Okay， so if we remove all the trailing zeros。😊。

Then the recipient will still be able to figure out where the punctuation marks ought to be。

 because they can just look for the ones。 And they know that the one comes at the end of any code word。

Alright， so this is still， still self punctuating。 And it's easy to decodeca they just read along to the head of one。

 and then they can spit out。 Okay， it must have been a C or whatever， whatever they have got to。

So what's the expected length of this， Well， I've worked it out for you in advance。 It's 1。

875 or 1 and 78。Okay， that's a nice idea。Can we get the expected length any shorter？ how， How about。

How about this one， How about。That code。What's the expected length of this one？Which rate length is1。

Okay， is it unique to decodable。Maybe not because even very short strings may have the same encodings as each other。

 Okay， so this is not uniquely decodable。 Okay， so the goal is to get the expected length very short。

嗯。Oh， so。Can we do any better than， than this one， well。How about this， We need to have。

 have a bit more length。 They've gotta be a bit code words must be different from each other。 Okay。

 that's one of the rules。 So a deduction from the rule is all。Code words must be different。

And that's a consequence of。You need decoability。Alright， so let's make them different。 Okay。

 how about this sn，0，0，0，1，0， and 1，0。Okay。Expected length of this is 1 and  5，8。Okay。

 the expected length is there's a chance of a half of。This happening， a quarter of this。

And an8 for this， and an8 for this。 So the question was， where does the expected length come from。

 expected length is。There's a half chance of getting a length of one。

There's a quarter chance of a length of two plus a1/8th chance of3 plus a1/8th chance。Of2。

And then I added those up。All right。So it's just the average length of a word。

 given that the length are going to be。A link。One， two， three。And2。Okay， any other questions。

So what do you think of this guy， Let's， let's use him to。En code something。 It's。

 it's got a shorter expected length than。Examples we've looked at so far。

Let me encode something with it， C， AA B。Encod with。This is code number three。Okay four。

When we encode the A A B， we get。0，1，0。Wang。Huang。And。2。So， is C 4。Easy to decode。

Is it uniquely decodable？What we're trying to do here is sort of sail close to the wind。

 We want to make all the code words as short as possible， because that's good news。

 But we don't want to sail too close and have problems of unique decodability， so。😊。

Is this uniquely decodable？We could stare hard at this and， and try and figure out。

Is there some other interpretation。 So you read along a 0，1。 How could we get 0，1。 It has to be a C。

 doesn't it， So sort think hard and say， okay， that's the thing。Then we look at this bit and1，1，0。

 What could be this。 I were thinking hard， looking at the codebook and we say， well， maybe， oh， look。

 there's another zero here。 It could be an A and an A and then a B。But it could have been。呃。

Maybe it was a。A here。And1 and a0， maybe that was a D here。🤢，And then there was a 0 from somewhere。

 and。So it's difficult to decode because I'， I'm not quite sure especially if we haven't。

Reach the end yet。It's not clear what's going on。 Can anyone give us a proof that it's actually not uniquely decodable。

Pro would mean that you find two strings that have exactly the same。D C， okay， so if you encode。

DC gives you0，1，0，3。D C gives you 1，0，0，1，0， okay and。It had got another string that also encodes as。

A BD is1。0ero，0。1，0， well done。 Okay， so if we call this X。And this why they're different。

 but they've got the same encoding。 So it's not uniquely toable。 Okay， so this is useless， not。

Unly decodable。So what's going on。Let's give ourselves one more example。C5。Here's C5。0，0。0，1。1，0。网络。

Okay， expected length of this is。😊，2。Because they're all length， too。

So that's not as good as this one。嗯。I， I want to give you a few more。

Has anyone got any further ideas， any ways we can improve， yeah。4 c two。啊哈。So you're suggesting T C2。

And tweak the last word。 So we've got C 6 using 1，0，1。0，0，1。

 But you're saying you don't actually need that final punctuation character。

 because once you've seen3 zeros， if you're using C 2， you know a one is coming next。

So you can get rid of it。All right。Great， okay， so the lengths are 1，2，3， and 3。Which incidentally。

The same as the Shannon information contents。 Let's call those H。1 bit，2 bits，3 bits and3 bits。So。

 the expected length。Which is the average of the length is going to be the same as the average of the Shanon information contents。

 which is the entropy， which we've already worked at。 So that's one and three quarter。

 which is the entropy。Right， so that's a fun idea。 We've got a symbol code whose expected length is the entropy。

😊，If we encode C， A， A B。Where this。Then， we get。0，0，1， one。Wang。0，1。No。

interesting thing to notice that this set of coders here has lots of zeros in it and only a few ones。

 Do you think you can make it any better。😊，Is it uniquely decodable？😡。

Can anyone give an argument why it must be uniquely decodable。We've sort of already said it。

 haven't we。Okay， you're being shy。 How'll， I'll help out。

 The receiver can read along and look at the code codebook。

 And once they reach the end of a valid word that's in the codebook， Nothing else will have happened。

 You can't reach。 You can't get through a different code word on the way to the code word you're actually thinking of。

 No code word is a prefix of any other code word。So this code。This is a prefix code is the。

Name we give to this no。Code word。There's a prefix of any other。We don't have to use prefix codes。

 but it makes them easy to decode。Another property of a prefix code is you can arrange the code words in a tree where the branches in the tree are the decision is the next currently gonna be a 0 or a one。

 And at each step in the tree， you either keep going or you stop because you found a code word。

 So in this one， you go down the one branch and you stop and you found the code word for a， which is。

Wang。You go this way， 0 and 1。 you have 0 followed by  one。 Then you've got B。

 which is encoded with 0，1。 the characters that we the。

 the symbols we saw as we went along those branches。 we keep going down here，0 and 1。This is C。

 This is D。All right。I'm gonna give you just one more code。 And unfortunately， I ran out of。Board。

Let's put it。我也为。Let me define another code， C 7。It's gonna look like this 1，1，0，1，0，0。0，0，0。

Have deliberately chosen this one because it's not a prefix code。

 It has the property that the code word for a is a prefix of the code words for B and for C， alright。

So it's not a prefix code， which means it may be a bit of a headache to decode。

If you receive a one and you know some more stuff is coming and you receive a0， what。

 what was going on。 could it be an A could be we start to D， You get another 0。 You still don't know。

 get some more zeros。You still don't know what's going on。

 and you wait and get lots and lots of zeros。 and you still don't know。And maybe when a1 comes along。

 then maybe you can figure out whether the first symbol was an A A B or a C。Okay。

So we don't like G because it's not easy to decode， but is it actually uniquely decodable。Yes， why。

Okay， so if you reverse these four code words， they are the same as the code words of C 6。

 which is uniquely decodable。If this one were not uniquely decodable。

 that would mean it has got two code words， which are， sorry， two strings， X and Y。

 whose encodings are I identical to each other。 You could then reverse the two of those。

And you would have found yourself a pair of strings that have the same code word over here for this code。

And we know that's impossible because that one's uniquely decodable。

 So this one is uniquely decodable。But we don't like it， because it's not a prefix code。So， this is。

Un it to decodable。Right， so one of the ideas we're floating now is easy to decode。Could mean。

 for example， that we'd like a prefix code， please。😊，But we really do want small， expected length。

Okay。Let me suggest an idea now about how we get small， expected length。We found a code here。

 which we're speculating could be the best you can do for this ensemble with a symbol code。

 because it happens to have reached the entropy。 And we've already heard some theorems about not being able to do better than the entropy。

😊，And it has the property。Here's the key intuition of that simple codes and is of all of data compression。

 It has the key property。 You give short code words to the probable outcomes， and longer code words。

To the less probable ones。 Okay， that's what it's all about。

And that's a possible guess about how we might get the smallest possible expected length。

 We could say， oh， you give me a list of probabilities。 I'll sort them。

 and I'll give the shortest possible code word to the most probable one and the and steadily longer code words as we go down the list。

😊，Have a chat to your neighbor and see what you think of of that idea。Okay。

 so I've suggested an idea here。 It's got the right spirit。 It's giving short。Code words。

To the proable outcomes。And long ones for the less probable ones。Is that going to work？

 or can anyone criticize that for us。If you've got a huge number of symbols， then what？😡。

It might not be good。 It's definitely not good。Probably not good， okay。I might agree with you。呵。

Let me give you some backup for your intuition there。

Weve found a case where this proposed algorithm is getting us to the entrypiece。

 So we can't be too critical of it， but maybe we can find a counter examplele where it doesn't。

 It doesn't work。 And it doesn't need to be a monster。Example。

 we can give them all a probability of a quarter。Except just to make life interesting。

 we'll add epsilon。To one of them and add epsilon over 2 to one and subtract epsilon over 2 from this one and subtract epsilon from that one where Epsilon is a billionth。

 Okay， so they're all essentially， they all have a probability of a quarter。Alright。

 And now we apply this suggested algorithm。 And what code do we end up with。End up with C6。All right。

So this is a new probability distribution。 When you use code 6。

 which is proposed by this algorithm here， you get an expected length that is the lengths are 1，2。

3 and3 is the last one in the list。 And the average of those。 since they're all equi probable。

 Give or take epsilon is average here9 over 4， which is 2。😊，And a quarter。Bits。

 is that the optimal symbol code？Can we do better， how。Anyone。是。Use C 5。

 and the expected length will be 2。Okay。Q일이。So。But the length of C5。我要被这个。Right。

 so we can't just use that simple rule。 though。 It's got the right spirit。

 We need to identify some sort of trade off of。When do you give short code words to the most probable guy。

 recognizing that there seems to be some sort of trade off that when we decide to not give them all length to words。

If one of them gets a length 1， then some others sort of get longer。

 It's a bit like when you've got a glove full of water， plastic glove full of water。

 you squeeze a few of the fingers and the other ones have to get bigger。

 Theres some sort of conserved quantity lurking in there。😊。

And that conerve quantity is to do with unique decodability。

 If we allowed ourselves to shorten some of the words and didn't make the others longer。

 It looks like we lose uniquely， unique decodability。I've lost board as well。' run out of board。

 Let's play this。I think the time has come for me to reveal how this rubber glove works。

 how the the constraint of unique decodability。Works。

So let's rattle through a way of thinking about this。哎。I only use code words of a particular length。

 How many of them can I have， well。If all my code words。Have length。2。嗯。L 2， then I can have。

4 of them。If all my code wordss have length3， I can have eight。For code re 1。

 I can only have 0 and 1。 so I can have 2。 And in general， I can have  two to the L of them， so。

There I was changing the size of the alphabet and noticing that if I have long words。

 I can have more of them， exponentially more of them。And。

Here is the idea that wraps this up and is consistent with everything we've seen so far。 The idea is。

 you can think of each code word。Of some length L。Has a cost， let's call it。Of2 to the minus L。

And what we're doing is going to the symbol coding supermarket。

Here are the different aisles of the supermarket。 You can go。 You're making a simple code。

 You can pick any code words you want。 So here's the entire set of all conceivable code words。

 but you can't have。😊，Annie's choice because it might not be uniquely decodable。

And I've arranged them in aisles， where each aisle has words of the same length。

 And you can wander through the supermarket， make some choices。

 And the size of the package for each code is indicating how much it'll cost you。

So you've got a budget of one， which is the entire height of the supermarket。

 You can buy these two code words。 if you want the0 and the one， and then you're done。

 you can't add any more code words of any length because they'd be confused with the0 and the one。

Or you can have these four。Or we can have these 8。 Or we've seen a bunch of things you can also have。

 You could pick those4。 That was code number one。And you haven't exceeded your budget。

 And that's uniquely decodable。 The fact that you haven't exceeded your budget doesn't guarantee that it's uniquely decodable。

 But definitely， if you go over your budget of one， then it won't be uniquely decodable。

 So what we've got is the following assertion。That's right it here。 having identified code1。

If a code is uniquely decodable。😊，Then。The cost of all the code words has to be less than your budget。

 Some of2 to the minus L I must be less than or equal to1。 These are the costs of your code words。

 That's your budget。And this is called the craft inequality。And it's true。And we haven't proved it。

 I've just told you it。 And the proof is in the book。 So if you're interested in， a proof。

It's in the textbook。Okay， so this is what unique decodability implies。

 You've got to stay within your budget。So there was code 1， And we had some other ideas。

 Here was code number 5。That was the selection that we made with code。Where was it？2，2。

 That's code 2。Which doesn't go over budget， but it didn't quite use up the whole budget。

 And so on noticed we could。Make a change instead of get buying the 0，0 to 1。

Coode word right at the top。 We could lo off to find the one and buy the 0，0，0 next door instead。

 And that made the expected length shorter， which is good。😊，And then we looked at this guy。

 That was my silly idea。 Sorry about that，1，0，0，0，1，0，1，0， Okay， and that went over the budget。

Alright， and it was a great labor to find a proof that it went that it didn't work。

 We had to think about strings。 But now we've got the craft inequality。

 We could have known straight away。 no point even trying this thing。

 It's violated the craft inequality， so it can't be uniquely decodable。Alright， in blue there。

 we have the optimal code。And here is。C 7， which I wiped off， which is where we reversed all of them。

 So this is also uniquely decodable。 And you can see the difference between the prefix code in blue。

 which is sort of sensible。 It walks through the supermarket from one side to the other。

 buying code words that you won't confuse with each other， whereas the silly back to front one。😊。

C 6 bought 1，1，0 and 1，0，0， which are prefixes of each other。

 and are're on the same Y coordinate in this， in this picture。All right。

So that's the craft inequality。 And a code that。Gets right up to the budget that uses the full budget。

We will call a complete。Code。A complete code is one that has sum of2 to minus L I。Equal to。Wang。

If you haven't chosen yourself a complete code， the advice is。

 you can probably go back to the supermarket， Make some switches and get yourself a shorter code。

 So it's a bit silly not to use a complete code。Allright。And as we've observed。

 easy to decode codes are prefix codes。So。Let's now address the practical question。 or no。

 the theoretical question。 The first practice next。 That's2 5 minutes on each。

The theoretical question is， how well can we do with。Symbol codes。So if I give you any ensemble X。

 and if you come up with the best symbol code by whatever method。

How small can the expected length be。Okay。So the definition of the expected length is sum over I P。

 I， L I。And。We're now going to show that whatever you do with a simple code。

 you can't beat the entropy。 and we'll also identify what you need to do in order to get。

Close to the entropy or all the way to the entropy。

 And it's all about figuring out what these expected lengths should be。 Let me give us。A clue。

I'm going to define。The ideal。Link。For a code word to be， log waste 2。One over the probability。code主。

So I'm gonna introduce a definition， namely this channel information context。 So I say。

 let's assume that simple code ought to be using those。 I'm， I'm not assuming I'm。

 I'm just making a definition， and then we'll end up with a proof。Okay， so。That。

 that's the ideal length。Now， if you rearrange this and if you imagine that someone has picked。

Some lengths L I that may or may not be the ideal length。 You can use those similarly， to define。

Some implicit probabilities for which those。Chosen length would be the ideal length。Okay。

 so we've defined a relationship between lengths and probabilities in this way。

 And I'm going to call the implicit probabilities Q。

And the implicit probability cu that you can get from whatever length you have come up with。

Will be 2 to the minus L I。Except you maybe didn't choose a complete code。

 So maybe the sum of all of these isn't one， which would mean it's not a probability distribution。

 So I'm gonna divide by the appropriate normal normalizing constant Z。Where。

Z is sum of2 to the minus L I。Which will be one， if it is a complete code。

 So it's one if you've made a sensible trip to the supermarket。But it could be smaller than one。So。

 note。Z will be less or equal to one for any uniquely decodable code。

And Z equals one for a complete code。Right。What does that then mean。Well， it means L I。

 the lengths that you've chosen are log basease 21 over Q I minus log basease 2 Z。

And now I can plug this into。Oh。So L is sum of I P I。 We've got log based 2。One on Q I。

Minus log base 2 of。That。Sorry， my bored hygiene isn't very good today。嗯。Okay。

 wouldn't it be great if this said sum of P log 1 over P。So， let's do that。S over I P log base 2。

1 over P， except that's not true anymore。 So we need to add on the appropriate thing so that it is true。

 Some of P log P over。Q， and then we still have minus log Z。Lurrkking at the end， some of P I is one。

 so we can。Suck the log Zed out of the summation。Right， we've got somewhere。

If you pick any symbol code at all， then its expected length will equal the entropy。Plus， something。

Plus， something else。Let's give this a name。 We'll call this the callback libla divergence。Between P。

And Q。And。Here's a little theorem。Some of P log P over Q for any two distributions， P And Q。

Is greater element equal to 0。 This is called gibbs inequality。

And it's one of the most important inequalities of information theory。With equality。Only yeah。

Q is equal to B。And log Z， we already know。Is less， sorry， Z is all is less or equal to1。 So log Z。

It is less than equal to 0， and minus logs Z is greater than or equal to 0 with equality。Only if。

The code。Is。Complete。So it's greater than equal to 0。 If the code is uniquely decodable。

With the quality， only if it's complete。So this is true for any code， for any symbol code。

And so what we have just proved is that the expected length。Is great Henry equal to the entropy？😊。

Not only that。 So we've shown that the best you can possibly do with the entropy。

 We've shown what you need to do in order to get to the entropy。 You need your P to equal your Q。

 So you should be using implicit probabilities that are equal to the two probabilities。

 So your length should be the information contents。 so you get equality。

If and only if the lengths you're using are。The sharing information contents。

And you've got a complete code。Which will happen for free when you do that。Okay。

 so what have we done， We've sort of proved a source coding theorem for symbol codes。

 We've shown that you should be using the Shanon information code contents to set your code word length if you want to get to the entropy。

 and then you will get to the entropy and you can't get any further。Okay， that was the。

Theoretical bottom line for symbol codes。So the ideal code lengths are the Sha information contents。

 But in practice， if I give you some probabilities like the probabilities we had for English a moment ago。

 you take log based two of them， and you're not going to get an integer out， are you。So in practice。

 for any real probability distribution， you typically can't actually get exactly to the entropy。

So there's a a missing result， which is， well， how close can you get。 And here's the answer to that。

 Let's start again on the left hand side。And I'm not going to prove this， but it's in the textbook。

If these ideal lengths L I star， which are bat channel information contents。Are not。Integers。

How close can you get？Answer， well， you can still always get。Within 1 B。Of entropy。So。There exists。

An optimal symbol code。For which。Okay。This is true。 so you can get within one bit。

Which sounds pretty good。Come back next week to hear whether this is good enough or whether， in fact。

 we still want to do better。 The answer is gonna read。

 We want to do better because this isn't going to be good enough。All right。So that's theory。

 What about practice， Wouldn't it be great to be able to just take a probability distribution and work out an optimal symbol code for that probability distribution。

😊，Let me tell you how to do it。How to make optimal。Simple codes。I'm not going to prove it。😡。

You can read the book。To figure out to proof。The method for making optimal symbol codes that I will show you is called the Huffman algorithm。

And it's very elegant。😊，And it's not completely obvious why it should actually be optimal and why it should get you anywhere near the optimal。

 the ideal Shannon information content。Code length。So here's a summary of how it works。

Remember how prefix code could be related to a binary tree。

 What we're going to do is build that binary tree starting from the leaves。

 We're going to start from the smallest， most remote leaves。 So build。A binary tree。Starting。From。

The furthest。Levees of the tree。 And that's essentially the algorithm。 Let you。

 Let me show you what I mean。I'll show you with an example that's usually the easiest way。Let me。

Invent a probability distribution。Okay， here is a six element probability vector。And his。

The statement of the algorithm， combine。The two symbols。With smallest probability。Into a new。

 single symbol。And repeat。 That's the algorithm。Okay， so we look at our list of probabilities。

 and we say these are the two smallest。 So we will combine them。

 and we've defined a little bit of a binary tree here。 We combine them。

 We add up their probabilities， and we get 0。21。 And now we repeat on the set of 5 probabilities that we have here。

 The two smallest ones are these two。 We add them up and we get 0。2。5。

And now we look at these four probabilities。 b， b， b， bp， we find the two smallest， which are。

Point14 and point 21。We combine them。And we get 0 point。3。5。Okay， that was the first iteration。

 That was the second iteration。 That was the third iteration。And then。We've got。25 and 35。

 which are smaller than 40。So we combine them， we get 0。6。The fourth step。

And then we combine buy these， and we get one， and we're done， and that was the fifth。😊。

And now we've made a binary tree。 And so we have made a prefix code because we can just slap label 0。

1，0，1 Any you like 0，1，0，1，0，1。😊，And that defines your code words reading from the root back out to the leaves。

 just as an example，1，0，0。 So the code word you'll give to this one is。1，0，0。

 And you can fill in the others。That's the Hutman algorithm。And it's optimal。Cool， hey。Souck。

Let me summarize what we've said。We used Gibbs inequality。We've talked about unique decodability。

 We've introduced the idea of prefix codes。And binary trees and symbol codes。

 are really all about building nice binary trees。Whenever you get a code that does achieve the entropy。

 the code lengths are equal to the information contents。 That's the ideal code length。

And with a symbol code， you can always get within one B of the entropy。

 And you can do that with the Huffman algorithm。Here are the results we've stated without proof。

 The book has proofs of those results。I've got a few more slides just to keep things moving with some。



![](img/6ca8d674d887e969d661f4ab4a3750b7_6.png)

Things you can be doing for next time。 I already encouraged you to do a project。

 namely invent a compressor and an known compressor for a source file of 10000 Bs from a event coin whose probability of one is 。

01。 Implement them and or estimate how it works。 And the screen has got some other recommended exercises and recommended。

😊，Reading。Thanks very much for coming。 See you next week。😊。



![](img/6ca8d674d887e969d661f4ab4a3750b7_8.png)