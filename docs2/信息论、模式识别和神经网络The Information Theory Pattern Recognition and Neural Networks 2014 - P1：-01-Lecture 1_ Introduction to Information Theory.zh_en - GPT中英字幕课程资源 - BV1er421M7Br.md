# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P1：-01-Lecture 1_ Introduction to Information Theory.zh_en - GPT中英字幕课程资源 - BV1er421M7Br

![](img/6078f5326165d569bb5df217467acefe_0.png)

Okay， welcome， everyone。 Thank you very much for coming to this。

 the first lecture on a course called information theory， Pat recognitiontion and neural networks。

 This first lecture is an introduction to information theory。😊。

Information theory was invented by Claude Shannon， to solve communication problems。And。

The fundamental problem。That Shannon defined was the task of reliable communication over an unreliable channel。



![](img/6078f5326165d569bb5df217467acefe_2.png)

So that's our fundamental problem。 And I'll give some examples。Alright， now。So。

 some examples of channels。One channel we're using right now is the channel that goes from my voice。

To your ear。 And the medium is。air。Another channel that we may be using is a channel that goes from our eyes up to bits of our nervous system。

And there the medium is sort of bags of cytoplasm and electrical impulses。

Another example of a channel that we're all carrying around with us is DNA。

 We've got about 10 to the 13 copies of our genome on board us in each of our 10 to the 13 cells。

 And every time one of those cells replicates。We send。

Two copies of the genome into those cells Re that 40 times。

 And you've gone from an egg to a human being。 and maybe on to the next generation。And。

Another example is the spacecraft， say the Mars rover or something like that。 You'll have an antenna。

我们呃。And you use the vacuum as your。Transmission， medium， and。Send signals。To the Miles Rover。

 And maybe it's got an antenna and sends back。Signals。

 so this is a channel that can go in both directions。And another example is a phone line。

 So you maybe have a copper wire。If you're old fashioned。Connecting one phone。原纳的很。

Another example is a disk drive。 So the medium is some sort of magnetized film。In a standard。

 hard drive。And in that dis drive。You store a message， which might be your file， and you send it。

To yourself。At another time。 So many of these channels go from one place to another place。

 one place to another place。 But you can have channels that go from one place that describe to the same place。

 But at a later time。 And we're still trying to communicate a message from that one location to another location。

😊，And all of these channels have， in common the property that the received signal isn't identical to the transmitted signal。

 so。Because of noise or。

![](img/6078f5326165d569bb5df217467acefe_4.png)

Other processes， our receive signal is maybe。Approximately equal to。The transmitted signal。

But we've got some noise。Had it as well。 Maybe， some of these channels。

 maybe there's no relationship， no simple equality relationship at all。

 You just have the transmitted the receive signal， depending on the transmitted signal in some way。

 But for a toy channel， we might say， let's assume the receive signal differs by adding some sort of noise。

And in most of these applications， we might say that's bad news because we would really like reliable communication。

 We would like to be able to deduce at the receiver precisely what the original transmitted signal was。

😊，So。We would like。To have communication systems。Where。The received message。你皮。Is equal to。

The original transmitted message。That would make for a better phone call。A better disk drive。

A better communication between lecturer。And audience。So， imagine that。

We're trying to achieve this goal。 We're trying to make a reliable communication system。

 What sort of approaches could we go for， What solutions are there。Well。

 we can perhaps categorize solutions to this goal in two ways。Either their physical solutions。

Where you throw away the lousy disk drive and replace it by a better one that's more expensive。

 that maybe you， you take your copper wires and you put better insulation on them。

 You use a colder magnetic film。 You add cooling。 So you change the physics to reduce the noise。

 So it's physical solutions。Alternatively。We could talk about system solutions。

And the idea of a system solution is we accept the lousy channel as it is。

 and we add encoding and decoding systems around that channel to turn it into a reliable channel。

 So this is a much more exciting approach and the physical approach。 Physics is exciting， too。

 But the system approach accepts the unreliable system as it is and transforms it into a reliable system。

😊，And that's what information theory is about。 We're going to be taking source messages。

And our source message， which we like to call S。Is going to be put through an encoder system。

 an encoder， which we will design。And that encoder will spit out。The transmission， T。

And this coded transmission then gets sent。Over the channel。The channel will do its thing。

It will add noise， perhaps。And then we'll get a received。Message。

Which is going to be a corrupted version of this coded message。

But then we're gonna to have another system。AndThe system is going to be called a decoder。

And we will invent that， too。And the decoder will try and come up with a guess。For what S was。

 S with a hat on top hat， meaning guests。What's going on here。

 The encoder is going to be some sort of system that adds。Redundancy。And we'll think about that， in。

More detail in a moment。And then the decoder makes use of this known system for adding redundancy to try to infer both。

T and N。 Or if you like both the source message and N。

 So the decoder is going to be a system for inferring。And。And。Yes。Okay。

 let's give ourselves a toy model to think about。The toy model that we'll work with for a while。

 is called。The binary symmetric channel。So， binary symmetric channel。Has got an input。

And willll idealize and assume that that input is。0 or a1。

 So it's a binary input you get to choose each time you use the channel。

 Is it a0 or a 1 that you send。And then。What comes out。Is also either a 0 or a 1。

And we're going to assume。That the probability that what comes out is what you put in。Is1 minus F。

Which might be 90%， e。And the probability。好的。Is not what you put in。Is F， for example，10%。

 So whenever you put in a0， there's a 10% chance， a one will come out。 there's a 90% chance。

 a 0 will come out。 And symmetrically， the other way around， if you put in a one。

 there's a 90% chance， you get a one out， etc。 So that's the binary symmetric channel。

There's probably very few channels in the real world that are the binary symmetric channel。

 but it's a nice， simple model to discuss that has all the essential properties that we need to study this bit of information theory。

So we could think of this as a model for a disk drive。

 Let's say you've made your new startup company。 You've got Cambridge Blue disk drives。

 and you make your first prototype disk drive using your new invented technology， and you test it。

 and you find it flips 10% of the bits。😊，Is that useful this drive。 Well。

 let's just have a quick think。 Let me ask you question number one here。Question one， oh， good is me。

Let's try again。M。Okay。Question one。A file of 10000 Bs is stored on this diskrife。



![](img/6078f5326165d569bb5df217467acefe_6.png)

It's stored on a disk drive that flips。10% of the bits。And then， it's red。Assuming that F is 01。

Assuming that each bit is independently either flipped or not flipped。Roughly。How many bits。

Off flipped。Whatho。How many。对。啊，对来。And I'd like you to discuss this with your neighbor and give the answer in the form。

 roughlyough this many plus or minus。This many。Does everyone understand the question。Okay。

 please talk to your neighbor and then we'll see what numbers going in here。Number of flipped bits。

 anyone。And。1000，1000 plus a minus。看没。We still debating， okay。Anyone else say 1000 plus minus。Plus。

 a minus。100。Plus， -900。对。30。Okay， we've got a few answers there。 Who said。

 who wants to give a reason for their answer。 So anyone who gave an answer give a reason。

900 sounds quite a lot， doesn't it。He said，900。Yeah， y plus -900。The data book， excellent， good。

Because you don't need to understand things if youve got the data book。

And what did the data book say。Okay， and you're looking at the variance of what。

Byinaial distribution， grand， yep。Very good。 So you look up the binomial distribution。

And it's got a mean。Of n times P， where P here is F。And it's got a variance of NP Q。

 where Q is the other thing。 It's 1 minus F。Alright， so you can look that up。

 and then you need to know what variance means， how that relates to well。

 roughly plus a minus you know，1000 plus a minus what。 So this is the mean。 It's 10000 times 。1。

 which is 1000。 The variance is 900。But what does that mean， What's the meaning of the variance。

 It's the square of the standard deviation。 Okay， so this is。The square and the standard deviation。

You take the square root of it， which is。30， and that tells you roughly how many bits either way。

 you'll be flipped。 Okay， now the binomial distribution is pretty much the only bit of mathematics you need to know for this course。

 And I do encourage you to review the binomial distribution and get good at working with it because we are going to use it over and over in this topic and in other topics in information theory as well。

😊，Okay， so we have an answer of。1000 plus or -30。Thanks to Mr。 Biomial。

 the inventor of the distribution that bears his name。Okay， so we've got our disk drive。

We launched the company。And are we going to have a happy customer when we sell the first disk drive。

😊，Any opinions。No， why。呃。It， its slightly too many flips， isn't it。

If someones storing important information。So， question 2。To have a saleable describe。Saalable，1 GB。

Yes， right。If it were a disk drive that's a binary symmetric channel。

 how small would its F have to be for you to be able to make a successful business。How small？

Does the flip probability。哎。Need。To me。Please turn to your neighbor and have a chat about this question。

Okay。Any the answers， how small do you need your F to be to have a saleable disk drive。

To have a viable company。Yes。😊，310th to-13。Any other answers。10 to，10 to the -5。

I this more I gig about。That's true。 Many people need 20 GB disks。

 These lecture notes are about three years old。 So， yes。We'll put a little star here to say。

 please pretend that you are set in the past three years ago。

We can redo it for for another size of diskri。 But let's stick with gigabyte for a moment。

 People still use gigabyte USB sticks， don't we。Okay， so trying to make a sailable USB stick。

So otherrens。Don't be shy， yes。10th to -3。Wow， any other answers？We've got quite。

 a range of answers there。是啊。1-10， okay， so。Let's have some explanations from the extremes of the range。

 And that's these two。Tings。So where did 10 to -13 come from。

 What was your So this was assuming there was no kind of potential。Give you every roughly about。

Have times you show up the。Mhm。😊，Okay， every thousand times you fill the eye。

And your judgment was 1000 was， was enough。Okay。Right。So where did the -3 come from。And你咁咯。呵。😊，Okay。

 so let's just redo this calculation。 Let's kick the tires on it a little bit。So。

Let's imagine that our customer is going to use the drive every single day。

 They're gonna be an fairly intensive user。 And let's say that they might use the drive for five years because they're stingy。

 and they believe。And sustainable use of resources。So let's say you've got five years of use。

And we're going at a rate of 1 GB per day。Then the number of bits that will be sent through this channel。

Here's five years times 1 GB per day， and 1 GB。Is 8。Times 10 to 9。Bits。

And five years is  five times 365。Jays。So that's our number of bits。That we want to send。

And if you multiply that out， you get 10 to the 13。

 So that's very much on the same page as this sort of number， but。Do we want to sell it and say。

 yeah， we're expecting a failure within five years。 Maybe that's not quite good enough。 we'd like。

It to be quite unlikely that our first customer will ever complain。 Yeah， So if we want a 1% chance。

Of disappointment， disappointment being that any file。A all gets messed up。

Then we need the error probability。To be something like 10 to -15。

And if you want your first 1000 customers all to be happy， then you need to aim for 10 to the -18。

Okay。1000 happy customers。Pushes you towards wanting。10th of -18。

And if you talk to the disk drive industry and you say。

 what is your industry standard for performance of a disk drive， the answer is 10 to -18。

 So that's what they're aiming for。For today， let's accept 10 to the -15 as a reasonable answer。So。

 we're aiming for。An error probability of 10 to the -15 or better。

And we now want to step back to the diagram I just rubbed off that talks about encoders and decoderrs。

 I'd like to discuss ways of adding redundancy。 I'll clean the board。

 And if you can have a chat to each other about how could then encoder work。

 How could we add redundancy to a file。Okay。Now， I'm not asking you to give me an encoder that solves this problem straight off。

 I'm just asking， what are some encoders that add redundancy at all？ Okay。

 so do we have some ideas for how to add redundancy。一样。Pro decoding。 What does paryding mean， Gos。

Okay， so we're taking some string of zeros and ones that we want to transmit。Like this。

 How long is the string that we're gonna to do the parity of。A bite。 So maybe take8 of them。A。This。

That was 8。 That was lucky， And then。That's what the sauce came up with。 And then we add an extra。

Paodity bit here。We will copy。And he's the sum of those。1，2，3，4，5。 So we write in  five here。

 except we're using binary。 So we write  one because one is the same as 5。 Okay， if it had been 4。

 we would have written 0。So that's a parity coding。 That's a way of adding redundancy。Good。

Any other ideas for how to add redundancy。Repeat things multiple times。

 So we'll have what we call a repetition code。 How many times， for example。Would you want to repeat。

Twice， okay， so。Will， call repetition codes are。And I'll write out the code。

We're going to take each bit。 And as we send it， we'll repeat it some number of times。

So we could send 0 and then repeat it twice， which I'm gonna from now on call repeating three times。

 okay。That's repeated three times。Im warm。Get sent as one on one。 And we'll call this R 3。

And I accept you could call this repeating it twice because you send it， then you repeat it twice。

 But I'm gonna call it repeating it three times。 Okay， that's my convention。

And I made one of those earlier。And this is what it looks like。

So we've got a file of 10000 bit Bs on the left， and then we repeat it three times。

 I've actually reordered the bit。 So the first bit is sent after the whole file has been sent。

 So we repeat the whole file three times。That that's。Logically， just the same as repeating each bit。

So let's give ourselves a source file。 And the source file could be the string 0，1，1，0，1。

And we transmit。0，0，0，1，1，1，1，1，1，0，0，0，1，1。忘了。Okay， so that's how we encode a file。

And let's now give ourselves some noise and start talking about decoders。

And we'll start with the repetition code。So let's have a noise vector。

 And the way I'll represent noise is it's gonna be 0。

 If no flip occurs and there's gonna be a one if a flip occurs。

So here's a noise vector that our binary symmetric channel could produce for us。

And that would then mean that the received vector differs from t in some of these places。 So 0，0，0。

 This one is flipped。 So we got a 0，1，1，1，1，1，1，0，1，1，1，1。😊，So that's our received vector。

So what did I do there， I added。The transmission to the noise。 And I did the addition， modulo。2。

 so1 and one is 0。Okay， how should we decode this。A decoder is a system that reads in and received。

File and spits out a guess。For S。So。In general。How should we decode。3， have a chat to your neighbor。



![](img/6078f5326165d569bb5df217467acefe_8.png)

Okay， any suggestions of how， in general， Yes， at the back。



![](img/6078f5326165d569bb5df217467acefe_10.png)

Okay， so take the mean of each group of three。 Is that what you mean， So we read it3 at a time。

And you say， is the mean above closer to  one or to 0。 Okay， is。

 did anyone else have another way of putting the same concept， yeah。Best of three or majority vote。

 Yes， so。We reckon that the sensible decoder is。The best of。And here，3。

And the length of this block that we're transmitting。 best of three。Ekoda or majority vote。Decoder。

Alright， so if we receive 0，0，0， we say 0。 If we receive 0，0，1， we say 1。If we receive 1，1，0， we say。

 whoops。I say one。If we receive one or one， we say all or one， do chip in if I make。Eris。Okay。

 so there's 8 possible received vectors。 And here's what we do， according to this decoder。

 And if we apply that decoder here， then our S hat comes out as 0，1。W。1。1。

And what we can notice in this case。Is that some good things have happened。So here， a flip occurred。

That was a flip。And it's being cleaned up because this is the same as this。

 And so that makes us happy。😊，And。Something else has happened。Here， there were two flips in a block。

 and this has been turned into a one。 And that's actually an error。 So that's not good。

 So we're a bit sad about that。But。Fair enough， maybe this decoder does improve things。

So if we apply the majority vote decoder， this is what we get。

And if you compare the floppiness of the source file and the decoded file there。

 you can see it's improved things。 We have reduced the probability of error。

 So this repetition code kind of works a bit， but it doesn't actually get us to 10 to the -15 probability of error。

Now， before we proceed and say。How do make better， better encoders and decoders。

I just want to prove this intuition。 Why is the majority vote decoder the right decoder。

So as I said earlier， decoding is inference。 We want to infer。What the source message was。

And to do inference， we need to use。Inverse。Probability。

And I just want to remind you how inverse probability works， because in due course。

 we're going to do slightly more complicated problems where you may not leap to the correct answer quite so easily。

So inverse probability needs the rules of probability。 The rules of probability are the product rule。

Which says that the probability of two random variables， for example。

 the source bit and the received vector。Can be written as the probability of S times the probability of R given S。

And it can also be written the other way as P of R times P of S given up。

 So that's the probability rule。 That's just the definition of conditional probabilities。

 If you like， it tells you how to get a joint probability from a marginal probability and a conditional probability。

Then the other rule of probability。 And there are only two。There's a summer rule。

 and the sum rule tells you how to get a marginal probability。By adding up all values。Of a joint。

Probability， so you can sum over all values of S， P of S and R。 And that will give you P of R。

 alright。So if S is a variable that takes on two values。

 this is p of S equals 0 and R plus P of S equals 1。And。2。And we can use。

There rules of probability to then tell us how to decode。For example。

 if someone tells us R and we want to know how probable alternative values of S are。

 that's called the posterior probability。Of S。You get that。By。

Taking the two versions of the product rule over here。

The thing we want is on the right hand side here。 So we'll divide through by P of R。

And we'll get the answer。So， this is。B of R， given S。Minus P of S。Divided by P of R。And P of R。

 we can compute using the sum rule。Which we just wrote down over there。 So I won't write it again。

Well， I will。 actually。 let's write it down。I'll go one extra step。 P of R is。

 We can take each of those terms。Over there。P of R given S equals 0 times p of S equals 0。

 We can use the product rule to write each of them out。Explicitly。Okay。

So that's the rules of probability that tell you how to do inference。

 That tells you how to do decoding。 And we can take an example， R vector， say，0，1，1。

And we can apply these rules。So this will tell us not only that this is a sensible decoder。

 but it'll tell us how probable each of its answers is to be correct。 So， for example。

 if you receive 0，1，1。Then the two things we need to know over here。 We need to know。This thing。

 which is called the likelihood。Of S。And here we've got the prior probability ver of S。😊。

So we need to work out。 what's the probability that。R has that value If S is equal to 0。

And we need to know the probability of R F， S， is it with a one。

So what's the probability of getting 0，1，1 out if the sender was trying to send a single0？ Well。

 there had to be a non flip。Which has a probability1 F，1 minus F。Then there had to be a flip。

 Then there had to be another flip。So that's the probability of getting that value of R， if S were 0。

That's the likelihood of S equals 0。If S were  one。 What's the probability of getting 0，1，1。 Well。

 in that case， it would have to be one flip in the first bit。 And then both of the last two bits。

Would have to be not flipped。 And each of those independently has a probability。

1 minus F of being not flipped。Okay， so that's 1 minus F， F squared。And this is F to the1。

Times 1 minus F。And this exponent here， which in this case， is one。His。

The number of bits that would have to be。Fpped for this hypothesis to be right。Number of bits。That。

Wouldd。Have。Being。Flippped。Well done。 Thank you。And this， too， which is no longer missing。

 is the number of agreements。Between。What the transmitted vector would be for that S and the receive vector that we're actually dealing with。

Okay， and the more agreements you have， the bigger the likelihood is because1 minus F is bigger than F。

Okay， so。Let's now derive this decoder。Let's make an additional assumption。

 We can only answer this question。 if we say what the prior probability of S is。

 then we can get an answer for the posterior probability。And I'm going say the following。

 I'm gonna say if the probability that S is 0 is a half。And。Obviously。

 the probability that S is1 is a half then。We can actually write down the inference。

 The probability that S is 1， given R is 0，1，1。Is1 minus f squared。Times F。

 times a half divided by the same term。Down squares， downstairs like this。Plus。The other term。

The other explanation。And now we can simplify this lot。And when you cancel everything out， you get。

1 minus F。So we've now answered in that table。 We just had going to S hatt。

We've looked at one row of that， The row that says 0，1，1。

 And now what we've worked out is the probability that S is equal to 1， given R is 0，1，1。Is， in fact。

1 minus F， which is 90%。So it was a sensible thing to say， you should guess a one。Alright。

 and now you can repeat that for all8 possible answers。

Almost all of them will come out just the same sort of way this one did。 But if you receive 0，0。

0 or 1，1，1， you'll get a slightly different answer for the probability of what the decoder says。

 you should guess。So。Just to finish this off， I'm laboring it because it's good to be clear on a simple case。

 Then we can go and。Do more complicated ones。The probability that it was a  one is bigger than the probability that it was a 0。

 so。S hat is one， is the best guess。Okay。And it's the best guess because it involved the smallest number of flips。

Okay。So I'll leave as an exercise doing the case。 R is 111。

 so you can work out the posterior probability。In that case。So now we have a new task。

This was using probabilities to do inference。Now， what I want to work out is how well does this decoder perform。

So this is an example of forward probability。I want to ask the question， if we use a repetition code。

To encode S， we send to over binary symmetric channel with a flip probability F。

 And then we use the majority vote decoder to give us our S。What is the probability。That S hat。

Will not equal。S， where I'm talking here about a single bit。

 So we send 1 bit over the channel using this procedure。

 What's the probability that the S hat we end up spitting out of our decoder will not be the same as the bit that we pin。

 Please have a chat to your neighbor。

![](img/6078f5326165d569bb5df217467acefe_12.png)

Okay。Any answers。The flip probability is F。What's the probability。Of an error of this system。Anyone。

What probability distribution are you thinking about， anyone。The binomial distribution。 Imagine that。

 Okay， so is the binomial distribution and what。what outcomes would cause this thing to happen。

 Which outcomes do you need to look up in the data book。2 or more flips in a block。 Okay。

 so the probability of three flips in a block。Is。F cubed。

That's pretty unlikely for them all to be flipped。The other thing that could happen。

 And these are exclusive possibilities， is that there's exactly two flips。

 And that's the more likely thing。 So we should really focus attention on this term。

 How probable is it that two flips will occur in a block。It's3 F squared。1 minus f。

Which you can read out of your data book on the binomial distribution。Okay。

 there's three ways of it happening。 That's where the three comes from。

 There's three ways of choosing which bits are flipped when you're flipping 2 from 3。嗯，可。And so。

 that's roughly。3 F squared plus some other stuff。 So-2 F cubed。

 This is the dominant term of leading behavior。Al right。So what have we done so far。We started out。

With no code。And we had a probability of bit error。Which was。哎。For example，0。1。

And when we didn't use a code at all。I'll call that communication at rate 1。

 because every time you use the channel， you are attempting to send 1 B。

Then we invented the repetition code， which has got a rate of one third。So， R 3。

Has a rate of one third。You send 1 B for every three uses of the channel。

And its error probability is。Roughly3 F squared。So some good news。Assuming that F is a small number。

 like 0。1， the repetition code is making things better。 But the bad news is the rate has gone down。

Sorry。Remember， what we want to do is we want a system solution that gives us an error probability of about 10 to the -15。

 or maybe even 10 to the -18。We could continue with repetition codes。And a homework problem。

Is to work out。How many repetitions do you need。In order to achieve。10th to -15。

Assuming that we're using a repetition code。I'll call this probability of Bi error P B， for short。

Okay， so that's a homework work problem。 And I'll tell you the answer for free。It's about 61。So。

We wanted a system solution， and here is one solution。Let's say that this is a single disk drive。

 What we do is we package up 61 of them all inside a box。My this。We keep on going。

 And then we end up with this great big stack。 And we put a single wrap around it。

 And we say this is 1 GB disk drive。 It's actually 61 GB of disk drive inside。

 But we say it's a1 GB disk drive。 And now you copy the file。😊，Onto all of the list arrives。

 and you use a majority vote and outcomes， your answer。

 And that majority vote will be right with a probability of 10 to the -15 for each bit。

So you may have one happy customer。But you probably wouldn't have 1000 happy customers。

 And you've got a very big stack of disk drives hidden inside this box。Okay， so that's one option。

 We can repeat lots of times。And we can get the error probability down。 And if your customers say。

 no，10 to the -15 is not good enough， then you just say， oops， okay， we've got to add more cost。

 more disk drives。 So put even more disk drives in the box。 and you can still achieve any target。

 but the cost goes steadily up。Okay， let's now get to the exciting bit。

Where can we get to on this diagram。I'm going to tell you another way of making codes。

Which is to use parity bits， which Gos suggested at the beginning。

 I'm going to tell you about the 74hamming code。And then I'm going to tell you Shannon's result for where we can get to on this diagram。

So here's how the 7，4hammon code works。It's called the 7。

4 hamming code because it takes  four source bits at a time and encodes them into 7 transmitted Bs。

So we're gonna have three extra parity bits， and it works like this。 We write S1， S2， S 3 and S 4。

Into these circles here。 And then we set the remaining three bits， which well call T 5 T 6 and T 7。

 such that the parity in each circle is even。So， let's do an example。I'm going to encode for you 1，0。

0，0。So we send s in the clear 1，0，0，0。 And then we're going send three more bits afterwards。

 And those bits are determined by writing 1，0，0，0 in order。

And then we find the parity in this circle， which is。1。

 and we put a one there so that the total parity is even。 we put a 0 here。 we put a one there。

 and we read them out in the right order，1，0，1。Okay， that's the encoder。Let's do one more example。1。

1，1，0。So， one。1，1，0。Pity in here is  three so far， which is odd。 So put another one。

 And that's now even。 And this is even already。 So we writes 0。 and this is even。 So we writes 0。

So that encodes to 1，1，1，0， followed by1，0，0。Okay。No。That's the encoder。

 And we need a decoder for ourselves。And。Just as for the repetition code。

 the decoder is going to be the decoder that spits out a guess S that differs。Who's transmission。

 Sorry， it needs to spit out the S， Who transmission T of S differs from what we received in as few flips as possible。

Okay。So， the general idea is。P of us given are。Is PR given as。Times P， S over PF R。

 And this likelihood term term here favored Ss where we had the fewest flips。

So we want a decoder that comes up with the hypothesis that involve the smallest number of flips。

 And we'll do that。By writing what we receive into the same diagram that we created over there。

 So we're going to write them in in the same order， R 1。two。All three。And our 4 then R 5 up there。

R 6 and R 7。 Now， because the noises come along and could have flipped anything。

 this R could be any vector at all， and it may not satisfy these rules that we had over here。

 The rule being that the parity in each circle should be even。

 And what we're going to do is identify。Which of those rules are satisfied and which are not satisfied。

And then we'll use that。To identify。Which bits we think， have been flipped。So anything could happen。

 Let's imagine that we send this signal here， this transmission。And let's imagine that。

 along the way。R 2 is received。Fpped。Okay， so what we receive。R。Is。1，1，0，0，1，0，1。

 We don't know what happened。 That's a little secret that we， we will remind ourselves with。

 that actually， this one got flipped。But， we don't know that。So now we write that into。This diagram。

So， we write， and。Wang。1。0，0。1。0。Wang。And now， we。Color these circles in accordance with whether they're happy or not。

 This circle up here is unhappy。 So we'll color that red。 That's a sad。Circle。

 cause it hasn't got the right priority。This circles unhappy because it's only got one，1 in it。

 and it ought to have an even number， this circle。サピ。

That pattern of happiness and sadness willll call the syndrome of the received signal。

And now I'm gonna tell you a rule for coming up with a hypothesis of what happened。

 There are many hypotheses that could account for this syndrome because there's all sorts of flips that could have happened。

But the rule is going be。Find the bit that is inside all the sad circles and outside all of the happy circles。

 and then identify that one as the bit that must have been in flippedlict。Or we're not sure。

 but that's gonna be our guess。 So inside all the sad circles and outside the green circles is this guy。

 So we identify this guy。😊，As our guests。And we guess this was flipped。And so， then， we spit out。

Our guest for t is 1，0，0，0，1，0，1， and our guess for s。Is the first four bits of that， which is 1，0，0。

0， which is the right answer。So in this case， we have succeeded。Now。If actually。

 what had happened was the noise had come along and flipped 2 Bs。

Then this decoding rule is gonna go and find a single bit that it can un fliplip to account for what's happened。

 So we're gonna end up with 3 Bs being messed up。 So this decoder is not infallible。

It is the case that this encodeder and decoder。Can detect and correct any single flip。

 So any single flip。Can be。Tected un corrected。So that's nice， but。If。More than one flip， because。

Then。It turns out， and you can prove this as a homework。Problem， then your guess for S。

Will not be the original S。So this is another code that has the property that。

If there's only one flip in a block， it succeeds just like R 3， the repetition code。

But if there's two flips or more， then we're in trouble。

 And this diagram on the screen shows the performance of the 74hamming code。

A homework problem is to work out。What its probability of error is， What's the probability of a flip。

Of an error occurring。When we use this encoder and decoder。

And what you'll find out when you do that homework problem is the probability of a block error。

Is roughly 21 F squared。 You'll find that out， using the binomial distribution。

And the probability of bit error。Is about 9 F squared。To leading order。Okay。

 so Shannon asked the question， if we make encoders and decoderrs。

 where can we get to on this diagram。We've had a few ideas， repetition codes。

 And I've shown you one code using parities。The question is。

 what's the boundary between achievable and unachievable points。On this diagram。

And before Shannon conceived of asking that question。

 I think conventional wisdom was that the boundary between achievable and non achievable points。

Just had to be。Some sort of line going through the origin。

Because Sa's lawsz says if you want a really small error probability。

 then surely you're going to have a really small rate。

 just like our enormous stack of disk drives that we're imagining。😊，So， conventional wisdom。

Knew that points over here were achievable。But conventional wisdom probably was assuming that the boundary。

Went somewhere。Here。And Shannon proved an absolutely remarkable result。

 And this is going to be the the heart of this sequence of lectures to prove this result。😊。

Shan prove that you can get the error probability arbitrarily small without the rate having to go to 0。

 So Shan improve。To the boundary between achievable and nonachchievable points。

Is a line that looks like this。Everywhere here。Is achievable。And excitingly。

 this line meets the rate axis at a non zero rate。😊。

And because that's an exciting place to talk about。 We give it a name， and we'll call it C。

 the capacity of the channel that we're discussing。😊，For example。

The capacity of the binary symmetric channel， with the flip probability F。Is。

1 minus the binary entropy function。Of F， where I will define the binary entropy function for you right now。

There it is。So there is the line between achievable and non achievable points。So what does this mean。

Shannon spots are selling a disk drive， a disk drive。 Here's a1 gig disk drive。 mate。

 He's got 61 drives inside the box。 And he says， you don't need 61 drives in the box to get it and there a probability of 10 to the -15。

 You just need two disk drives。

![](img/6078f5326165d569bb5df217467acefe_14.png)

Because for the case where F is 0。1， the capacity when you work out this formula comes out to 0。53。

 which is bigger than a half。 So you only two disk drives in the box。 and then there exists。

 an encoding system and a decoding system that can correct as many errors as you like， you。

 you whatever error probability you name there exists an encoding in a decoding system that can achieve that error probability。

 So 10 to the -15， no problem，2 disk drives。

![](img/6078f5326165d569bb5df217467acefe_16.png)

10 to-18，2 disk rice，10 to-602 disk rice。 That is Shannon's noisy channel coding theorem。

So for any channel， there are encoders and decoderrs that can achieve reliable communication at any rate up to this quantity called the capacity of the channel。

😊，I'm gonna wrap up now。 I've just got three things to say。 First。

 the lecture notes for this lecture are Chapt 1 in this book， which is a free online book。

 also available from all your favorite bookshops。 You can get it from Amazon。

 You can get it from Cambridge University Press。 And it's free on the website of this course as a P D F。

😊，The lecture notes are Cha 1 for the next lecture。 I recommend that you read Chapter 2。

And the remaining lectures of this course are going to cover information theory。

 We'll continue discussing the noiseil noisy channel coding theorem。 But first。

 we're going to discuss the related task of data compression。 How do you make files smaller。

 Then we'll move on to discussing data modeling， pattern recognition， learning and memory。

 And we'll talk about various inference methods， App inference methods and neural networks。😊。

The final thing I want to say is， please before the next lecture。 have a think about this puzzle。

 This is called the weighing problem， The weighing puzzle。 And it goes like this。

 You're given 12 balls， all of which are equal in weight， except for one。

 and you are told that exactly one of them has got a different weight。

 and it's either heavier or lighter。😊，You're also given a balance。

 and the balance is one way you can put any number of balls on one side and the same number on the other side and then initiate the weighing。

 And it either comes out like this or this or the they balance。



![](img/6078f5326165d569bb5df217467acefe_18.png)

And the task is to identify the odd ball and whether it's heavier or lighter in as few uses of the balance as possible。

So that's gonna be the first thing that we discuss in the next lecture。

 Thank you very much for coming。 Thank you for listening。😊。



![](img/6078f5326165d569bb5df217467acefe_20.png)