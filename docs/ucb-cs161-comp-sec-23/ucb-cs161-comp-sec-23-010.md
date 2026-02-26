# 010：UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p10 -10--CS161 FA23- Lecture 10 - PRNGs and Diffie-Hellman Key Exchange.zh_en -BV1YGbceREDs_p10-

对。

![](img/9d6dd1e820560a2bf6b7c455f586d69c_1.png)

Okay so last time we talked about hashes， we talked about Max and we talked about how maxs are a way to make sure that someone can't t with our message so I'll leave that for you to look over and then finally we talked about ways to combine cryptography that cryptographic schemes that give us confidentiality and cryptographic schemes that give us authenticity but we also saw how you have to be a little bit careful about how you combine them where else things could go horribly around we talked about that one time okay so today we're gonna to take a break from seeing cryptographic schemes that give us confidentiality and integrity and we're going to solve kind of two questions that have been rooming over our head for the past two weeks and I kept telling you if you come back next week if you come back next week I'll tell you the answers so today we're finally going to solve those two problems and then we'll move on to some more cryptographic schemes so the two problems that we' are finally going to solve today after spending like two weeks kicking these problems down the can is well there's all this randomness that's needed in cryptographic schemes。

Seeing like IVs have to be random values keys are generated as random values how do we generate random numbers securely what does it even mean to generate random numbers securely and what happens if an attacker knows how we're generating random numbers that's like the first half of today and in the second half we're going to switch gears and talk about another problem that we've been kicking down the can forever and we're finally going to solve which is how did Alice and Bobbb get that secret key anyway we kept saying that Alice and Bobbb magically share a secret value that no one else knows and today finally we will discover the secret behind how they do that so it's like a twopart lecture and we're answering two major questions that we've been putting off for quite a while okay。

So first up we have to talk about how do we generate random numbers so it's kind of a side topic it's not a scheme that provides confidentiality。

 it's not a scheme that provides integrity， but we still have to know how to generate random numbers so that's what we're going to do now weve already talked about how there's all these different places where randomness is needed for cryptography we're even going to see more places where randomness is needed later but overall randomness is really important and we also noted that values have to be unpredictable so when I generate a random number and attacker should not be able to guess what the random number is because if they can then things can go horribly wrong we already saw like if an attacker knows the value of you your secret key things could go wrong okay so how do we generate random numbers securely that's our problem for today。

So to do that I first have to specify what this word random means。

 so we roughly know what random means it means they're unpredictable。

 but let's be a little bit more specific and give a formal mathematical definition to what random actually means okay。

😡，So the example that we've been using this whole time as like the example that I've been saying is well one way to generate things randomly is to take a coin that's fair so it turns of heads half the time tails half the time I flip it it comes up zero that's a bit of my secret value or my random value I flip it again comes up tails if I write a one comes up heads I write a zero and so I could just generate this thing by flipping this coin over and over again and somehow no one challenged me that this was a valid way to generate random numbers we were all like that seems pretty reasonable so why do we all feel that this was a reasonable thing to do well it seems reasonable because an attacker is gonna have a hard time guessing what the outcome of my 5050 coin is they don't know whether it's heads。

 they don't know whether it's tails if I generate the outcome of 128 coin tossses to get my 128 bit secret key the attacker has a hard time guessing what that value is and we were all pretty convinced of that but now this try to formalize that for real。

So to formalize that， we have to introduce a new term， it's called entropy。

 maybe you've seen it before in some other classes。

 but this is a way of measuring how hard it is for an attacker to guess something。

And we're not going to talk about it in too much detail in this class。

 but the idea is that if something has a high entropy。

 so like some random event has very high entropy and the idea is that it's very hard for someone to guess the outcome and if something has low entropy that means that it's easier for someone to guess the outcome so for example。

 a coin that has a 50% probability of coming up heads and a 50% probability of coming up tails that has high entropy it's really hard for an attacker to guess whether it comes up heads or tails but consider a coin that comes up like 99% heads and 1% tails well now the attacker could just say it's probably heads because it comes up heads 99% of the time that would be a random event that has low entropy so this somehow is a measure of how hard it is for an attacker to guess。

And what's like the unit of measurement here， the unit of measurement is usually in bits。

 so when we say three bits of entropy， that's the equivalent of the attacker having to guess three random fair coinintasses okay。

So one random coin toss is like one bit of entropy， if I have something。

 some random event that has like eight possible values。

 that's roughly three bits of entropy if they're a likely， okay。

Great so that's entropy here's an example of what happens if you use bad entropy so apparently someone went and like made this commit that says like they made an improvement to the random order generator and apparently this like destroyed the Bitcoin protocol in some way that we'll talk about later but yeah that was something that happened apparently so now you know so be careful use goods sources of entropy don't commit improvements that like great things okay。

😊，Great， so how do I generate things that have high enthtropy。

 I want things that act like random coin tosses that are truly random and hard to guess like if I can toss this random coin that's 5050。

 then I get good sources of randomness but like in a computer you can't ask the computer like like please take a coin and flip it like computers can't do that So how do I generate true randomness in a computer。

 Well it turns out to generate truly random numbers。

 you have to have some physical source of entropy。 We have to rely on something in the real world that is unpredictable like computers they're just circuits and circuits through predictable things So somehow I need to rely on something in the real world that is unpredictable So what could that be Well there's a couple ways to do this So one possible way is you can build a circuit that is specifically designed to do random things like you can ask the circuit give it some like error tolerance that's like really high or something and it's gonna to do unpredictable things's like beyond this。

Of our class， but that's no impossible way to do it。

 you can make a circuit whose whole job is to be very unpredictable and give you like garbage output。

Something else you can do which is pretty funny is you can measure things that really fine time scales so for example if I press a key on my keyboard right now like what times did I press it that's kind of predictable predictable in some senses you can probably guess that like I press the key on a certain date or like at 5 pm a certain hour but what if I asked you a question like what microsecond that I press this key that's a pretty unpredictable thing if I asked you a microsecond I don't know like 10 to the six or something like what microsecond that I press this key it's very hard to guess it's more or less unpredictable so that's another way you can use physical things to get true randomness something else that some older softwares do is I don't know if anyone's experienced this but if you open like an olds SSH terminal the way that they ask you to generate a random key is they give you a box and they say please wiggle your mouse of the box and then you wiggle your mouse in the box is anyone like actually played with one of those before。

Maybe I'll pull it up after lecture we're board， but what they do is they ask the user please wiggle in the box with your mouse and then once you wiggle on the box they use your mouse wiggling as the randomness for the key so you know be careful and wiggle very aggressively right but that is how you another way to generate randomness okay。

Now there is one slight problem which is that sometimes these physical sources of entropy are biased so for example if we use that like wiggling example like maybe a lot of users tend to wiggle like left to right and that's on how bias is the random members that come out right that could possibly be something and so sometimes your sources of entropy and the real world they're biased it's like our biased coin they're easier for the attacker to guess because they more often come out to one than zero or they more often come out to be zero than one so if you have a source of entropy that is biased then that might not be good enough you need more entropy and so the idea is that every random event has like some measure of how unpredictable it is and if you have an event that's kind of predictable and you don't like it maybe you have to throw in more entropy and the more slightly predictable events you throw in the more unpredictable for like some of all the events becomes maybe that was kind of a random way of saying it but basically the idea is that if I have multiple random。

Events and I combine all of them together to generate randomness then I ultimately get the sum of all of their entropy so if i'm like let me take this coin that's super biased and also this coin that's fair and also this other coin that's kind of biased and I combine all of their results into my final source I can sum up the entropy and get a rough measure of how hard is it is for the attacker to guess my final value given that they have to guess some things that are easy to guess and some things that are hard to guess we can like some things together get we can combine entropy sources okay。

So this is one possible way to do it， you can even be more exotic and use like laval lamps to generate randomness。

 but all of these have a problem， which is that it's expensive。

In order to rely on things that are in the physical world like cicus that are unpredictable。

 you randomly cosmic noise， lava lamps， these things are expensive and there's load degen like randomness just does not appear that much and in order to get random numbers it takes time it takes effort you have to ask the user to wiggle their mouse or press and keys and sometimes these sources aren't even great they might be biased so true randomness is great we love it because it actually is random and heart for de attacker to guess but it's expensive I want something cheap imagine how many random things they have to generate like IVs keys I want cheaper ways to generate all that stuff so how do I do it without relying on true physical randomness well this is where we're going rely on not randomness but pseudoranness this is a funny word and so pseudo randomness is a word for algorithms that are actually deterministic they run imppred ways so sometimes we call them this fancy。

Little name DBGs but basically the idea is that these things are deterministic algorithms so if you look under the hood they are shuffling bits around in some predictable way。

 however the output of these random number generators or pseudo random number generators from an attacker's perspective they look random so this is something that's cheap to implement because we can implement an algorithm when we know that our computers are really good at running deterministic predictable algorithms like shuffling bits so somehow I want to be able to use these algorithms to generate output that looks random so that's our goal。

Okay so these are algorithms they are deterministic and we'll talk about that more。

 but ultimately Michael is to find a cheaper way to generate randomness。

 I don't want to rely on physical randomness like cosmic noise or lava lamps。

 I want something that is cheap and deterministic that is as good as random for our purposes okay。

Great， so we're gonna look for algorithms that do this for us that are cheap to implement。

 They work fast。 but the things that they generate。 They are like random looking。

 and what that means is something we'll have to define。 Okay so let's define it。

 So this is one possible way to define PRNGs I will say that this is not the only way to define them depending on what like cryptography paper you're reading。

 there are different ways to define these things。 but the way that we will define them in this class is we'll say that a PRNG is like an object。

 like think Java objectoriented programming So I can instantiate an object called PRNG and this object has three methods available to it in case you can't tell I'm almost teaching 601 B。

 So like all this like Java stuff is like back in my brain so sorry if it's bringing back memories。

 but anyway， consider PRNG is like a mathematical object or like an object in memory and it has three methods available So one method is called or seed sorry I can't read it's called seed。

 So when you call the seed。You enter some randomness and this should be truly random bits and the idea is that you're throwing actual randomness into the myth so this PRNG object is's running some deterministic algorithm but you can feed it randomness you can like here have some randomness and the seed function gives it some true randomness to start up the PRNG the reseed function is for later so if you want to add in more randomness at some later date you can call the reseat function and this will pass an even more randomness into the PRNG so seed and reseed are ways to take truly random bits and pass them into our PRNG。

And once our PRNG has swallowed up all this true randomness and we've created some unpredictable state of the PRNG by giving it all this true randomness。

 we can now tell the PRNG please generate bits that are pseudo random and so here what the PRNG going to do is's going to take the truly random bits that we've provided it's going to run some deterministic algorithm on these bits that are truly random and it's going to get a whole bunch of bits like way more than we provided as input and all of these bits are going to look random。

😡，So that's the idea the PRNng we feed it of initial randomness that's like it doesn't have to be a lot just has to be some randomness and then now we can ask this PRNG for a whole lot more stuff that looks random and the PRng is going to take our initially random input and generate a whole lot worse of output that basically looks random is it actually random well not really because it's running some predictable bit shuffling algorithm that's deterministic but because the input that we passed them was truly random and because this algorithm is carefully calibrated to do a lot of unpredictable things even those deterministic。

 the resulting output's going to look random that's our hope okay。

So what makes a PRNG correct as we said PRNGs they are ultimately algorithms that don't involve randomness we give it randomness but the algorithm itself is shuffling bits in some deterministic way in fact if I pass them the same randomness twice and ask the TNG please generate bits it will generate the same output every single time that's what it means to be deterministic I pass them the same input and here the input is the randomness I ask it to generate the same output bits you get the same output is it efficient it's doing some sort of bit shuffling as we'll see soon and what's the security there's two security properties that we like one of them is that the output is indistinguishable from random and as always we'll come up with a game for that and there's another nice property that we'll talk about called rollback resistance but this is the definition of PRNG for this class it's like an object that you create and you can call these three methods on it。

ok。Cool， let's talk about seeding really quickly oops okay so as we said。

 the way that you see it is you take true random bits and you shove them into your PR PR or yeah PRng So what do you shove in as true randomness this is the true randomness that comes from like a user wiggling their mouse or typing on their keyboard or like random noise that you detect or your unpredictable CPU output that true randomness goes into your PRng and when you're using these in practice。

 you can pass in as much randomness as you have available to you So if you have a lot of different versus of entropy like you have the noise and you have the user wiggling their mouse you can pass all of that into the PRNng and the PR if it's design well should be able to combine all of those sources and use all of that randomness to as advantage So any entropy that you have you might as well throw it into the PRNG right。

Even if you throw in something that's really low entropy like somehow you have access to the output of like a 99% heads 1% tails coin。

 that thing is pretty low entropy attackers are going to have a pretty easy time guessing that thing but I can still pass that output into my PRNG because that's at least going to make whatever the PRG starting state is it's going to make it a little bit harder for the attacker to guess because now they have to also know the output of my 99% heads 1% tails coin output so any entropy that I have available I might as well throw it into like my PRNG soup so whatever is going on inside this thing I will take any true randomness available to me and just shove it into my PRNG and now the attacker in order to figure out what my PRNG is doing and to get the same output that I'm getting they have to guess all of the input that I passed it the more input I pass in better even if some of that input is low entropy and kind of predictable okay。

一视。Okay let's talk about that indistinguishable property so I guess the first question is can PRNGs be truly random like can these things be completely random Well we already said kind of by definition note we already said that these algorithms they are deterministic if you pass in the same C twice you will get the same output twice and in fact for like some definitions of the PRNG like if you consider a PRG that takes in maybe like a fixed length input and some like output so this is not how we define PRNGs but you could in theory define something like let me take a PRNG I'll use the fancy math indext that you saw a couple lectures ago。

 I could say let me take a PRNG that takes in S bits and it outputs two S bits and in fact if you look at like cryptographic papers this is kind of common。

Let me write this as a little bit nicer， okay。So this is some function that takes in S bits outputs to s bits right and so the question is like how many possible input outputs are there well if my input's an s bit input there are only two to the s possible different inputs and for each of those inputs I have exactly one and only one two s bit output so this pseudo random number generator as defined on this slide it's deterministic and it only has two to the s possible input sequences and two to the s possible output sequences why because it's deterministic so for every input that I pass in of which there are two to the s possible I only have two to the s possible outputs one per input right？

So the total number of possible outputs here is like2 to the S possible outputs。

And that is not the entire set of all random 2S bit strings， okay。

So if that didn't totally make sense， that's okay， you don't have to know this in too much detail。

 but basically the idea is that this PRNG has defined it has two to the s possible outputs。😡。

But if I were generating things truly at random there would be two to the two S possible outputs and2 to the S it's less than two to the2S。

 So this PRNG is not actually covering all the output space it's not truly random that was a long way way to prove that but it's like a rough sketch of so things can't be truly random that's a fancy way of saying it a less fancy way of saying it is just say PRngGs are deterministic there's a limited number of outputs because there's a limited number of inputs also a way of saying it So how do I say a PRNG is secure then well the rough intuitive picture is that a PRG is secure if it is indistinguishable from random to an attacker So if an attacker does not know what I passed into the PRG from their perspective the output is more or less random that's our model So our model is that the attacker doesn't know the input to the PRNG why is that Because if the attacker knew the input to our PRNG they would know the exact output。

Thing is deterministic if they know my input， they know my outputs that's kind of silly。

 so we're going to assume if the attacker does not know our input， then from their perspective。

 the object is really random。OkayThat's what this intuitive picture says。

So how do we formulate that as like an actual game because we like games so here's a possible game you can use we're not going to show it in all of its story detail。

 but the rough idea is like I'm going to as as I always do i'm the challenger I will like turn around and I will do two things without you seeing so i'm first going to。

Generate a truly random sequence， In other words， I'm going to take my coin。

 I'm going to flip it over and over and over again and I'm going to get truly random output okay and then I'm going to do a second thing which is I'm going to take a secure PRNG give it some input and you don't know what input I'm giving to the PRNG because you can't see but I'm going to take that input feed it into my PRNG and generate the same number of output bits and then I'm going to present those two to you so I'm going to say here are two random bit sequences one of them came from true randomness in other words I flipped a bunch of coins the other one when you don't know which is which the other one came from the PRNG so this other sequence I got by taking some small amount of randomness passing it into my PRNG and then generating a bunch of output and giving it to you and so your goal is to distinguish you need to tell me which is which which of these two came from the coin flips which of these two came from the real PRNG okay and so we say that it is computationally indisting。

If you can't guess if your best answer is just to randomly pick one。

 that means that you don't know which is which， and that means that this PRNG is computationally indistinguishable from random。

😡，So the intuitive picture is that the stuff that comes out of a PRNG from an attacker's perspective is as good as RA。

 and the way that we can actually prove it is to give the attacker a truly random sequence and a PRNG sequence and ask them which is which and if they cannot guess。

 then we know that this is computationally indistinguishable。Okay。

So that's one possible definition it turns out there's actually another definition that is equivalent that we're not going to。

Sp too much time on and you can actually prove that they're equivalent which is pretty cool。

 but another way to phrase the same thing that I think is slightly less intuitive。

 but in some purposes is pretty useful is this one down here which is to say if I tell you I have a PRNG I seeded it with some initial state you didn't see what I seated it with you have no idea what true randomness I passed in and then I generated it some output I call the generate function got some output and then I challenge you to tell me what comes next if I take the same PRNG and I generate again to get some more output what comes next and as an attacker you're gonna have no shot of guessing that and that's another way of saying that this PRNG is secure so both of these actually mean the same thing and depending on your context you can use either property but for this class the important thing is that PRNGs that are secure are as good as random the output from an attacker's perspective if they don't know what the input to this PRNG was the initial seed from their perspective is just a bunch of cointices。

Oh no， okay。Cool so that's one way to define PRGs that are secure if you're wondering what happens if they're not secure turns out PRngGs are used in a lot of places where randomness is needed and that's not just cryptography like if you go play slot machines you know and like I guess we're playing in St。

 Louis here but you go to St。 Louis play their slot machines those also use PRNGs to seed and give you outputs that look random and so apparently you could go and you can do things like apparently the people in the casino were like watching all the people on the floor and they would see some guy with like ability like walk in and they would like go to the slot machine and they would you know normal people they would just start like spinning or whatever what would they do they would like take their hand they would like put it over the spin button and they would just stand there for like 10 minutes and they would have their phone in front of them and then at some point they'd be like okay and then they would suddenly win So what were they doing they would probably taking advantage of the way that the PRG was being seeed and I guess。

Somehow was relying on the current time so they would like wait and wait and wait and like when the time caused the PRNG to be seated a certain way they would like push the spin button and suddenly a bunch of money would fall out so I guess that was bad so you have to be really careful especially if you're designing things where random is important and you want to make sure things are not predictable okay apparently this didn't happen in Vegas so you're gonna have to travel a bit further if you want to try this but I don't know okay。

Yeah， this comes up all the time it's not just slot machines。

 it comes up in here's an actual vulnerability that happened in like SSL which was a networking protocol。

 but basically the idea is that because we use randomness for so much stuff like generating random keys and generating you know IVs if you are using a random number generator that is insecure you might be leaking things like what private key you're using and that could be really bad because now attackers can read your messages。

 they can tamper with your messages so you have to be careful okay。Cool。

 so that's our first property of PRNGs， intuitively it all boils down to we want the output to look as goodta as random if you don't know the input。

Okay there is another property that is not strictly required for security。

 so if someone walks up to you and says this is a secure PRNG for the purposes of this class。

 this property is not strictly required however this is still a nice property to have and so this property is called rollback resistance and this says if hypothetically and so this is like the non-game version and then we'll talk about how you can formulate this as a game so informally what we're basically saying is that imagine if the attacker at some point they like hack your computer and suddenly they know what the PRNG is doing like they figure out at the current moment this is what the state of the PRNG is so the question is can they run this PRNG in reverse and try to figure out what was the random number that you generated previously if they know your internal state and if they are able to do this then we say your PRNG is not resistant to rollback attacks however if the attacker is not able to run this PRNG backwards and figure out what you were。

Generating like yesterday or the day before， and we say this PRNG is rollback resistant。

So remember security of a PRNG sorry to go all the way back security of a PRNG that's talking about predicting future outputs or predicting outputs that come later rollback resistance is not about predicting the future so it's not needed in the definition of a secure PRNG but it is a nice property to have because it says that you cannot even predict things in the past even if you learn what the internal PRNG state is that's what this says and again you can formulate it as a game and again the game has to do with I show you truly random bits and I show you something that was generated yesterday and I ask you which one is which and if you cannot tell me which one came from the PRNG yesterday and which one came from truly random coin flips then we say your PRNG is rollback resistant so again it's not fully required but it is nice because this gives us the property where even if my PR like completely breaks an attacker can see exactly what is going on inside the PRNG they still cannot figure out like what。

V key I generated yesterday or like what secreter values I came up with last week or something so rollback resistance roughly speaking is the property that I can't run this pair in jep backwards and figure out things that were being uploaded in the past。

 even if I learn what the internal state is。Okay。So now that I've told you what a PRNG is and what are all the nice properties of it now I can finally show you an example of a PRNG and again this is not the only PRNG out there。

 but this is one possible PRNG that uses Hmax so we already saw Hmax and the idea here is that do you remember when we said that output of the HMAC it basically looks unpredictable we said that hashes and Hmax their outputs are basically unpredictable if you change one bit of the input the output is more or less completely random so why don't we take that property and let's use this HmAC protocol and let's build something that looks like a PRNG so that is our goal for this light。

Okay so the way that I'm going to do it， it looks kind of complicated when you squinted it at first。

 but all you really have to know from this light like we're not gonna to ask you specifically， hey。

 how does this protocol work but the important thing that you should notice here is that we're basically calling Hmac over and over and over and over again and so every time I want more random output I call Hm over and over and over again and I'm continuously doing something like V equals Hmac of k comma V so I output something and then I reassigned that output to the next time I need something I call Hmac again I reasigned that as the input so I'm like chaining Hmac together over and over and over again to repeatedly generate stuff that's random that's like the rough picture of what's going on here so I can start with all zeros that I want to I hash all these like states in so here this is me taking my seed and using the Hmac property to take my seed shuffle it up and like put it into my Hmac as the initial starting state。

And then eventually if I receiptse it I can throw in more entropy， if I want to generate stuff again。

 the specifics of how this thing works are not important。

 the important thing is that all that I'm doing there's nothing fancy here I'm not doing any other bit shifting or no other fancy things I am simply calling HMac over and over and over again like look at this there's nothing but Hmax over and over and over again and every time I call the HMac I'm getting more and more random out。

O。So that's the rough picture it is deterministic if you pass in the same input twice and you call HMAC over and over and over again。

 you will get the same output， but here the idea is that if the attacker doesn't know the input and I call HMAC on that thing over and over and over again repeatedly chaining the output to the input over and over again like I Hmac value A and I get B then at HMAC B and I get C then I Hm C and then I get D and I output all these things over and over again。

 if the attacker does not know what the inputs are。

 they have no hope of coming up with the outputs okay。

Cool so that's Hmac DRBG and again you can prove that this thing is secure。 we're not going to do it。

 but again you can use reduction proofs and you can say something like I think if Hmac is secure then this PRNG is secure so that's like the forward direction how do you prove that you prove the contrapoitive which is a fancy way of saying you prove this statement instead which says if you break Hmac DBg then you break Hmac itself and if we assume Hmac is secure then Hmac DBG is also secure so it's a fancy way of provinging it using reduction but the important thing is that assuming that Hmax have their security properties like the properties of a hash that we've already seen then this PRNG is as good as range so it has that security property okay。

And what about that final property about rollback resistance so rollback resistance again the rough picture is that you cannot run this PRNG in reverse so imagine that somebody hacks into my HM D orBG random number generator that means they can see the value that I'm using so if they can see the values that I'm currently using to call HM over and over again。

 they can certainly run my PRNG in the forward direction because they can just start calling HM over and over again。

 but that's not what rollback resistances rollback resistance is asking if someone hacks into my PRNG and sees exactly what the current values are of any of these internal variables K and B whatever they mean。

Can they run this Hm DRBG in reverse and find out what was the value that I generated before this Well it turns out for Hmax you can't do that because you cannot run hashes in reverse if I show you the output of the Hm DRBG which is the output of some hash you have no idea what the input I used was so Hm DBGs they cannot be run in reverse so they do have rollback resistance。

😡，But this is not always true there are some PRMngs out there that involve like shuffling bits in some predictable way and you can run that same bit shuffling backwards and figure out what was happening yesterday or the data before okay that's HM T BG it's one of many examples of PRMGs that are out there you can see we kind of went wild with like the amount of example slides here because broken PRngG show up all over the place and we have just had so many examples I'm not even going to talk about this one but if you want to you can read it like these come up over and over and over again。

Since even the same one like I don't even know anymore。

 but there are a lot of these so make sure that use a secure PRNG because so much of cryptography relies on randomness and if your randomness is busted in that an attacker can predict what your future random numbers are like everything is hopeless。

 okay。过。So do be careful that's all the that is you will actually see randomness inside of Project two so just to give you a bit of or like a preview of what you're gonna to get to do in project two and another application of randomness that might not actually come to your mind initially imagine that you had to or imagine that you had a bunch of objects so this could be files like in Project two or maybe you just have like a lot of dogs or something I don't know and you need every object to have a unique name so you know you're the pet sitter and you have like million dogs every dog has to have a unique name because you don't want to call a dog two dogs to come up you don't want every dog has to have a unique name or every file and your file system has to have a unique name so how do you do that and what if you want all the names to be unpredictable you don't want the attackers to know what the names of your files are I don't know if there's a good dog analogy for this you don't want the attackers to know your dog's names I don't know but if you want everything to have a unique and unpredictable name。

There's actually a solution that at first seems completely like backwards and unintuitive。

 but turns out it works really well which is how are you going to assign random names to all of these different files well just pick a random value and that actually works and the first thing that everyone always asks is like okay hang on what if I happen to choose the same random value twice for two files。

 doesn't that ruin my whole plan of coming up with random unique unpredictable values but remember if I crank up the number of bits high enough say like 128 bits then what are the odds of generating the same 128 bit value twice it's like one in two to the 128 that's the probability of generating the same random value twice how often is this gonna happen？

Like zero never like astronomically impossible right so for basically all intents and purposes like for project two。

 you might ask hey when I use this random when I use this random function to generate like unique file names do I ever have to worry about two file names or two file IDs like colliding like it depends right if you're worried about like the sky falling then yeah maybe you're concerned about it。

 but for all practical purposes the odds of this happening zero right so this is actually one real life。

😡，Application of random numbers that might not seem like immediately obvious at first。

 but it turns out random numbers they're everywhere you see them in project two they're not just used for secret keys and Is you can even use them to come up with like unique IDs for everything okay。

Cool you'll get to play with that more in the project so won't ber the point but that's it for the first half of today so we talked about PRNGs they're a way to deterministically generate a lot of stuff that looks random with just a little bit of true random input so this way I only have to generate a little bit of really expensive random input based on physical processes and then I can use my PRNG to get a ton of randomness that has good entropy and it iss hard for the attacker to guess now underneath what I'm actually doing is deterministic algorithms right like the PRG itself is deterministic if I feed in the same seed twice I will get the same output twice but if the attacker doesn't know my input it's as good as random。

Okay， I guess we did not talk about countervo DRBG this time， but if you're curious。

 you can imagine that block cis can also be used for this purpose， okay。Cool。

 any final thoughts on PRNGs before I talk about the second topic of the date？Okay。

 anything on zoom that i'm missing Okay there's some messages on zoom questions there are two to the as possible seedss whose length are S bits yes。

 I think we talked about that so again the proof of that one wasn't too important。

 but the idea was that you know there are only a limited number of PR Nng outputs so。

parents are not totally random because there's a limited set of outputs that are possible。

Should I briefly reex it I can try although like I said the specifics are not too important so don't worry too much about this but the question was how do you prove that PRngs are not truly indistinguishable from random so the way that I can prove it and again this is not totally in scope so if it's not immediately obvious or if you want to break like this is the time to like check out for a bit you know but come back later if you want to you can check out for a bit now okay so question was how do I prove that PRngGs cannot be truly random so suppose that I have a PRG that's a function it takes an S bits of input outputs two s possible bits of output so how many possible inputs out there there are two to thes possible inputs okay。

To this PRNG why is that because this PRNG takes a fixed length input S this is not how we're modeling PRNGs but in this proof this is how we'll model it how many possible outputs are there there's not two to the two S there's only two to the S possible outputs Why is that because every input only has one unique output。

for each input， I run a deterministic algorithm， I get a single output。

 so the number of possible outputs is two to the s okay。

But how many possible random sequences are there of two s bits there's two to the2 s possible。

Random just two s bit sequences。So essentially， what I'm seeing here is that。Like in actuality。

 the number of sequences is more than the number of PRngG's possible outputs so like this is the total space of possible sequences that I can generate by coin tossing so truly random is like this this is the total space of all the possible twoS bit outputs I can get by just flicking my coin over and over again until my finger gets tied and I have two s possible bits but how many of these are actually possible PRNng outputs only a small subset so I'm learning on a space but the only possible outputs or like some subset right so I can use this to win my distinguishing game because what I can do if I have infinite time is I present to you two possible outputs。

 one of them came from the PRNG one of them came from truly random so if you had infinite time you can just come up with all of these possible outputs so you can generate everything in this little square here。

And with some non zero probability like better than 50% probability。

 you're going to be able to distinguish you have a strategy and your strategy is if。😡。

Something is one of these PRNG outputs， it probably came from the PRNG but if something is not one of the PRNG outputs like it falls out here。

 that means that no possible input of the PRNG would have ever given you this output so this one must be the coins this one must be the PRNG so your strategy when I provide to you two different bit sequences is you see which of these two is part of my subset of PRNG outputs I'm going to guess that one's the PRNG and the other one if it's not part of the PRNG then I know for sure it's truly random it's not going to always work but it works well enough that you're going to win with greater than 50% probability。

Okay so this proves that PRngGs cannot be truly random because it gives you some strategy to distinguish PRNG outputs from random however。

 remember that our goal for PRngGs is not true randomness our goal is computationally indistinguishable from random which is a fancy way of saying we're not worried about all attackers we're just worried about the ones that have a reasonable amount of compute time like in the life of the universe and so in real life that strategy of like trying all the possible PRNG outputs that's going be like exponential time astronomical times and attacker can't do that so in theory is a PRNng random no because of this proof that it roughly sketched out but is a PRNG as good as computationally and a distinguishable for random yes because this strategy does not work it takes way too long。

Hopefully that helped again， not in scope， but I find it pretty interesting so。

If you found it interesting its cool， if not， then I hope you enjoyed your five in app and now let's talk about second part of today。

 unless there are any other questions。Yeah。在。The question was is the fact that it's not truly random wise deterministic I mean you can have things that are not truly random that are deterministic I would say it goes the other direction PRMGs are deterministic so therefore they cannot be truly random I think makes more sense okay good question。

Okay， I guess before I go on， this is like my bridge topic connecting the two parts of today So one final thing I will say about PRNngs is you can do something pretty funny with them which is do you remember how we kept talking about onetime pads and we kept saying like oh if only there was a way to generate the key to the onetime pad differently every single time so it turns out PRngs are a great way to do this because PRngGs only require a small bit of randomness and they give you a huge amount of pseudo randomness that is as good as random so I can actually use stream cipers or notstream cipers I can actually use PRngGs to invent something called stream cipher which is going to unlock the onetime pad for real so yes we use like counter mode as like a kind of workaround way to come up with something that looks like a onetime pad but finally the way that we can finally unlock the power of the onetime pad is to use something called stream cipers so roughly speaking what you're gonna do is。

And Bob， they're going to have one and only one key。

 so we're not going to deal with that one time pad stuff of like Alice and Bob have to come up with different keys every single time。

 they're going to have one key and only one key。😡，And using that one key。

 they can feed that key into a PRngG as the seed they can generate a ton of output like this could be millions of bits or however many Aliceice and Bob want they can generate tons of output and now they can use this output to ex the plain text exhor the side fort text and they can use that as their onetime pad so that's like the highlel idea I finally unlock the one time pad because instead of Alice and Bob having to repeatedly exchange new keys for every single message which we've already said is like really expensive and hard we can instead rely on a PRNG so instead of exchanging truly random keys every single time I can use one key the original key generate a ton of pseudoran output and then use that pseudoran output as the key and I can use that to encrypt a bunch of messages and not have to reuse stuff okay going to be really careful you can reintroduce IVs and stuff and that's another way to be able to encrypt multiple messages so。

That's stream Cys okay I'm not going talk about this one in too much detail either it's not like totally something we're going to test you over and over again。

 but if you need to be able to encrypt multiple messages you can also introduce an IV that's one way to avoid using the same seed twice because in this version if I try to follow this protocol like twice I would passing the same seed I would get the same output and I'd be reusing my one-time pad key so if I add an IV that's one way to avoid that okay。

Cool at stream cipherers， this is a whole category of algorithms because what this PRNG is is up for debate you can use any PRNG you want and you get nice stream ciphers out of them Okay cool turns out if you squint a little bit I even use the word squint how nice if you squint a little bit CTr kind of is a stream cipher all of this stuff up here this is basically a PRN this is a fancy way of generating bits that look basically more or less random but are actually deterministally generate it So that is the PRNG then I use the PRNG to extra with my plain text so you could even say A CTtR it is a stream cipher there's one type of stream cipher okay。

Well let's talk about bluey the security of it so yeah it turns out stream Cypers。

 they do have NCPA secure properties if you assume that the pseudoran output is computationally indistinguishable from random so for the same reason that one time path were secure when you didn't reuse the key stream Cypers they also have those nice confidentiality properties but you do have to be a little bit careful because if you generate too much output things might start repeating like remember in CTR mode if you generate like an ungodly amount of output this counter could like maybe wrap around depending on your implementation so you have to be a little bit careful and you can't generate like ungodly amounts of output but in practice that's usually not going happen so just keep your number of outputs under like2 to the 64 which is a massive number and it should be okay。

Okay， cool so。That's cool One final thing I'll mention about string Cypherers which is pretty cool is that imagine if someone gives you like a 100 gigabyte file and it's all encrypted right and for some reason you're really curious what like the last bit of the file is you're like I want to know this gigantic encrypted file that someone passed to me does it end in a zero or one I don't know why you want to know this but's say you do well in some block cipher is like AS EBC the only way that you're going to be able to figure out what that last bit is of your 100 gigabyte file is to decrypt the entire file and only then can you figure out oh。

 this is the last bit。But the nice thing about stream ciphers is that every single bit is happening independently。

 so depending on what type of peer engine you're using you might be able to kind of like skip to the end and say I'm not going to decrypt this entire 100 gigaby file to figure out what the ending of it is I'm just going to decrypt the last part of it by itself and my encryption algorithm if it does have this property then I don't have to worry about the rest of the file。

 I can just decrypt a certain part of it ands kind that's a nice property to have especially if you have really large files okay。

So there's the example a huge Cy textex like someone like gives you a huge like movie download and it's all encrypt it and you're just like I don't care about this movie。

 I just want to know how it ends I want to see the last bit of it so you can decrypt just the end of it by using stream cpherpress if they have this nice property okay so some stream cpherpress。

 they do have this property， some don't so for example in AE CTtr think about how you would do this like AEStr where's my diagram you have your movie and you're like I want to know the last thing and I want to know how it ends so all you have to do is set your counter to be the like very last block the ending of your movie and you can just decrypt this block in isolation you don't have to touch any of the other ones so in this case with AEEtR you do have this nice property where you can decrypt arbitrary parts of your message without having to decrypt the whole thing That's pretty sweet。

But it's not always true so not all streamcyclpherers have this property for example think about Hmac DRBG remember this is applying Hmac over and over again。

 so if I wanted to do the same trick in Hmac DRBG stream Cypher which means I want to figure out what the last bits of PRNG output are so I can decrypt the last part of my Cytex how do I do it well the only way to do it is to start at the beginning call HM call HM again call HMac and do this over and over and over and over again until you reach the end so in this case you can't really do that you do have to generate the Hmax all the way up because of the way that they're chain together so sometimes this works sometimes it doesn't depends on this PRNG they you're using but possibly a nice property to have。

Okay。Cool okay that's finally the end of stream cycles it's kind of a nice little side topic so now i'm finally going to answer the question of like how did Alice and Bob get this secret key like what were they doing so that's what we're going to figure out now unless there's something else you want to know about stream cycles。

😊，Okay， there is。呃，来公司对。That is involved guarantee that about the same state。Yeah。

 there was a question which is how do Alice and Bob use the PRNG to generate the same keys so remember that Alice and Bob if we're in the symmetric key setting they have a secret key that no one else knows right if they have a secret key that no one else knows they can pass that same key to the PRNG because the PRNG is deterministic you get the same apple twice。

Yeah no question。Anything else yet？然后这个。来设个边话。in the。听一先咗出边嗰个啊。This one， sorry， this one。

Yeah so this is just very generic PRNG so we have not specified any specific PRNG here。

 but the rough idea is that if I just use this scheme right here and I wanted to encrypt multiple messages I would be passing in the same key twice I would be calling the generated function of the same PRNG seed and I would get the same output over here which means that I'm using my one-time pad key so one way to avoid that is Alice and Bob can share an IV and the IV is a public value doesn't have to be encrypted and now instead of just seeding with their key they see with the key and the IV so that this generated output is different every single time。

对。So that's the rough picture。え次貸したな。Okay。Okay let's finally answer this question like you waited weeks and weeks and weeks and finally I can tell you how Alice and Bob come up with the key Okay so the way that they do it is they come up with or they use this theme called the diiffy Heman Key exchange stand that for two guys diiffy and Heman and this is how we're gonna finally unlock all of symmetric key cryptography by telling you Alice and Bob came up with that key in the first place Okay so this is the analogy that I've seen floater around before some people like it and they think it makes a lot of sense some people I guess are like I have really strong opinions about paint and didn't agree with this so I will present it just for completeness but if you don't like this。

 you don't have to agree with my analogy so heres my analogy which is that Alice and Bob they really want to have a secret color that nobody else knows that is their goal they want to have a secret color they don't want anyone else to know what their secret color was but they can only exchange colors and like paint over an insecure channel which means that if they take a color。

Or like some paint color and they pass it over to the insecure channel eve can see what that color is that's the setting you don't like it we'll look at the math version of this a little bit okay。

So here is how they do it right well we already know that the channel is insecure so Alice can't just like take a secret color and pick a secret color pass it to Bob and Bob accepts it because then anybody over the insecure channel sees what the secret color is so here is their trick。

Alice is going to pick a secret color that no one else knows。Okay here it is red。 Alice picks red。

 Nobody else knows that Alice is chosen red except Alice herself Bob chooses a secret color Bob chooses。

 I don't know what this is like teal Bob chooses teal and no one else knows that Bob has chosen this is his secret color okay and they don't exchange the secret color directly right because if I exchange the secret color that other people know what my color is So here's what they do they're going to disguise what secret color they're using And the way that they're going to do that is they're both going to agree I'm going to take my secret color and mix it with something that we both have in common so they're both going to decide the common color is yellow they can tell them they can tell each other is that's okay it's okay if Eve。

The eavesdper knows that the common color is yellow so now they're going to use the common color。

 which everyone knows is's yellow to disguise their colors。 So here we go。

 Aliceice is gonna to take her secret color red， she's gonna combine it with the public color yellow and she's gonna get orange I think so if you combine yellow paint with red paint let's pretend you get orange paint So now this orange it's like a disguised version of her secret if you look at this right it's not immediately obvious that Aliceice used red like it's not obvious what specific red she used So we're gonna assume that this orange。

 it's like a disguised version of the red secret that she used and same thing over here Bob's gonna to use the public color the same one yellow mix it with this secret color teal and he's going to get this like blue looking thing and again the idea is that this is like a disguised version of his secret。

Okay。Great now is sent to exchange so both of them have a disguised version of their secrets so they're going to pass the disguised version of their secret to the other person so Bob takes this disguise secret passes it to Alice now Alice knows about the blue Eve also knows about the blue and we'll see why that's not a problem later but intuitively this is a disguised version of Bob's true secret color so Eve does not know what the secret color is。

Alice is going to do the same thing， which is take her disguise secret。

 which is orange pass it over to Bob now Bob and Eve because he was believe eavesropping they both know that Bob's sorry Alice's disguise secret orange so both of them now know the other person's disguise secret Eve knows both both of the disguise secrets and now here comes like the magic part which is。

Well what is Alice's disguise secret Alice's disguise secret is like yellow plus red that's what we said from before yellow is the public color red is her disguised or her actual secret so sorry yellow plus red is her disguise secret which is over here she gave it to Bob now Bob has access to yellow plus red sorry I put it on the wrong side okay。

There it is。And what about the value that Bob sent to Alice is also a disguise secret So over here what does Bob have Bob has or sorry Bob sent to Alice so now Alice has the public color plus Bob secret。

 which I guess I called it Tels I'll stick with that Okay yellow plus。Tal， okay， great。

So here comes the magic part which is Alice is going to take her secret and blend it in with Bob's disgu secret。

 so if I blend yellow and teal which is Bob's disgu secret that Alice received and I additionally throw in the secret I get yellow teal red which is this like poop looking color right okay。

And then what about Bob， What does Bob do， Bob takes the same disguise secret for Alice。

 which is yellow plus red。 And Bob mixes in his own teal。 And what does he get。

 He gets yellow red teal， the same like goop looking color， right， So now both of them have a secret。

 They have yellow red teal， and that is their shared secret。😊，So how do they do it。

 they came up with a secret， they disguised it， which was this step over here， they disguised it。

 they each sent the disguised version to the other person and then the other person threw in their own color so it was like yellow plus stealls my disguise version throw in red the yellow plus red is my disguised version throw in teal and at the end they both get the same color。

Okay so what about Eve what does Eve see well Eve sees two things Eve sees yellow plus red because that was the disguised value that Alice was sent to Bob Eve also sees yellow plus teal that was the disguised value that Bob said so we're going to assume two things here and for those of you who are like paint purists you have strong opinions about paint you might not believe me in this analogy but in the math version trust me it'll work out okay。

So the two assumptions about paint science that I have to assume here are that one it's not possible to separate out the paint。

 so if I just show you you know like don't look at this and I just show you the orange here and I ask you what two colors I use to create this orange。

 we're going to assume that it's not possible to tell。😡，Or even if I showed you like， you know。

Don't look at the secret and I tell you that I mixed yellow with something to get this what that I mixed you don't know okay we're gonna to assume that separating out the paint is expensive there's no way to take yellow plus red and separate out the yellow to get the original that's our assumption in paint okay same thing with the yellow plus tea if I just show you this and I tell you that I combined yellow with something to get this you have no idea what I can it's disguised okay。

😡，And if that is true， then I don't know what the secrets are and even if I know these two values right try and take these two and combine them to get that secret color from before you're not gonna have a very good time like even if I try to take these two and combine them maybe Eves like I'll just take these two disguise colorsers and put them together whats Eve going to get Eve' is going to get something like yellow and again I'm kind of fudging the rules of paint a little bit here but Eves going to get something like yellow plus yellow plus red plus teal like whatever color this is it's not going to be exactly the same as yellow plus red plus teal because I added in a little too much yellow okay so maybe you're okay with that maybe you have strong opinions about paint but this is kind of the analogy that we're going to use。

To build our key exchange。O。If you didn't like it and I'm going to show it to you in math。

 so here's the math version。Okay， so you saw this from before i'm going to rename the colors a little bit for reasons that i've become very clear in a little bit。

 so instead of using blue or whatever else I use i'm going to use these colors so。Again。

 the idea is basically the same Alice generates some secret color Amber because a for Alice that's her color Bob generates his secret。

 which is going to be B blue for Bob they're both going have some common color green and they're both going mix the secret color with their common color So Alice gets green amber that's the disguised version it's public color green plus amber her secret Bob's gonna get G that's G the public value plus B Bob's secret so I get G and they exchange so Eve knows G and G Eve knows both both of the disguised public values but she's still not going figure out what the ultimate final secret is the final secret is not G it's not G What is it it's the disguised secret GB plus Alice a secret color A So it's G A B what about Bob Bob takes G combines it with B gets G B so you've seen that before again if you're like。

Have strong opinions about paint and maybe you don't agree with this and you're just like there's a bunch of like random colors but now we're going to make it actual math and give it actual like mathematical rigor okay you ready okay。

So somehow I would like a mathematical version of that problem from before I ask you to assume that like if I give you a mixture of paint like yellow plus red。

 you cannot separate it into yellow and red I want a mathematical version of something being really hard to separate there was a question about order from before just really quickly we're just going assume that like mixing paints in different orders which not the same so GB and GA like look the same but that's for paint okay。

So we need a mathematical version of the fact that taking a mixture like a disguised yellow plus teal or yellow plus blue or whatever。

 we need a mathematical version of the fact that separating that out is hard it turns out there are actually a lot of different ways to formulate a mathematical problem that does this but the one that we're going to use is a fancy one called the discrete logarithm problem and it's kind of a fancy name but here's the rough idea the rough idea is that everyone's going to agree on the public values this is our public paint the public paint is going to be some prime number very large prime。

Ideally and some generator and we're not going to talk too much about what a generator is。

 but it's some specially chosen value if you're really curious。

 the idea is that like G to the one square G cube etc ceter。

 they all have to be unique mod p that's what a generator is but you don't have to know that it's some specially chosen value okay。

So once you choose these values correctly and properly there is this fact that we call the discrete logarithm problem and it gives us or it's going to unlock the key exchange protocol that we've been seeing so the discrete logarithm problem says in words if I give an attacker these three values I tell the attacker G it's public everyone knows it I tell the attacker P public everyone knows it and I give the attacker this strange value right here which is G to the a mod P and if you don't remember mods from C70 think like remainder so I say G to the a divided by p what's the remainder is G to the a modb P okay and so the idea here is that given G to the a mod P it is basically impossible with like modern computing hardware there's no way to come up with a there's no way to do it if I take G to the a and that's just some number I just give you the number there's no way for you to figure out what I computed to get a that's the。

Loarm okay， another way of writing it if you don't like that or you're not convinced by it is you could also say something like G to the x。

 you know， mod p is equal or congruent to y mod p。And so the idea is that if I give you Y and I tell you what G andR as those are public。

 if I give you y coming up with X is completely hopeless。

 you're not going to figure it out okay so this equation solving it basically impossible。

 that's what this says okay。😡，Now you might be tempted to say。

 well isn't it the case that like in regular math if I tell you like G the axis is equal to y with no modular arithmetic like no remainders。

 this is pretty solvable I can use logars to solve this。

 but it turns out and we're not going to prove it in this class but it turns out that adding this modkey makes this problem really。

 really really hard adding this modkey makes it basically impossible to come up with an X that satisfies this equation if I give you Y that is the discrete log problem okay。

So we assume that it's true， no one has ever found a solution to it， so we're probably all set here。

Another way of phrasing it that's slightly different but is going to make the algorithms that we're about to see possible。

 so it is based on the discrete log problem but we're going to phrase it slightly differently to make a different assumption called the diiffy Hemon assumption and this one it's going to look a little bit familiar from our example from before but this one is going to be phrased a little bit differently which is to say。

I'm going to give you three values so as before I'm going to formulate this kind of like a game。

 so I'm going to turn around and I'm going to pick a random A and B。

 you don't know what A and B are those are my secrets。

 I'm going to compute three things G to the A Mo P I can do that because I have A and everyone knows G and P I can also compute G to the B mo B because I have B so I can compute these exponents and I'm going to give that to you you don't know B。

 but you know G to the B Mo P I'm also going to give you this third one。

 which is G to the A B I can do that too I can take my A and B multiply them together。

 compute G to the AB give it to you and so the diy howmon assumption says that between these three you cannot tell which is which I ask you which is the one that was G to the A B you're like I don't know I ask you hey which one' is G to the A which one's G to the B you have no idea from your perspective they are all just some numbers and you have no idea what the numbers actually mean So that's a stronger assumptions slightly。

 but the reason why it works is because how would you actually。

To solve this in real life like one possible way to solve it is to try and figure out。

 well can I take that discrete log and solve for a， solve for B， solve for AB。

 then I could distinguish but you can't do that because because the discrete log problem is hard so。

That's the diiffy helmetman assumption， it's kind of a variation of the discrete law problem。

 you can prove one from the other， but the whole slide。

 the one takeaway if you' like how tired of listening to me is that given G to the A moP coming up with a is really hard。

Cool， I think in discussion to also show you a little bit of why this is the case and you get to play with the numbers。

 but for now， trust me that coming up with a given G to the AMIP really hard okay。

I don't know why that just disappearing。 What's okay they're disappearing What's okay I don't know Okay so at long last。

 I can show you this slide， which is the math version of the paint example from earlier So it's gonna to look familiar but instead of relying on paint mixing which is not a thing that computers can do I'm going to rely on the discrete log problem So here we go So this is like Alice's domain。

 Alice computing things this is like Bob's domain Bob's computing things anything they send over the channel Eve can read So here we go Alice generates a secret key A there it is and then Alice generates G to the A mod P。

 What is that that's the disguised version of your secret A and we already know the disguised version because someone who sees this value does not know what AI used the compute G to the A and my P So that's the disguised value of A。

Same thing on the other side， Bob computes B， which is his secret key， picks it at random。

Or his secret， and then he calculates you to the bemon and again that's the disguised version of Bob's secret。

And what do they do in the paint example afterwards they exchange their disguised secrets so here we go we exchanged so Alice sends G to the A mod P over Bob sends G to the B mod P and as they exchange they are letting Eve know what G to the A and G to the B are is that a problem well it's not really a problem because they're disguised Eve seeing G to the A does not give her any information about what the A modb P was and Eve seeing G to the B mod p gives her no information about what the original B was so even though I have taken the secret value and exchanged it over an insecure channel and let Eve see them they are disguised using this discrete log problem so that Eve has no idea what the underlying A and B were she doesn't know the secrets。

Okay， now finally I can do that thing from before where i'm going to mix a and B together to get my final shared secret so let's do it what does Alice have available to her Alice has a why does Alice have a so secret she generated it she knows it。

😡，Alice also has G to the B Why does Alice have G to the B because that is the disguise secret that Bob sentto it was disguised Alice has does Alice know B nope because Alice doesn't have B Bob never sent B and Alice cannot calculate B but that's okay because Alice can take these two values and she can calculate G to the B raise to the A power so she can take the value that Bob provided raise it up to the A power and get G to the B to the A power or mo B。

Turns out in modular arithmetic exponents， they were kind of like we expect so we get gta the B to the a power modP。

What does Bob do Bob does the same thing on his side which is what values does Bob know Bob knows B Why does Bob know B because it's his secret Bob knows G to the A Why does Bob know G to the A because he receive this disguised value from Alice so what can Bob do Bob doesn't note A but he can do this he can take G to the A which was something that he receive from Alice he can raise it up to the B power and he gets G to the A to the B power and if we stare at these a little bit well G to the B to the A power G to the A to the B power both of these are just G to the A B mod P so finally they have a shared secret the shared secret is G to the A B it's the public value which is there as a disguising agent and we combine a which is Aliceice's secret and B which is Bob's secret but the way that we combined it is that each side sent a disguised version of their secret and then they combined it with their own secret。

Okay so Aliceice used her own secret disguise version of Bobs gets the secret shared key Bob uses his secret takes the disguise secret from Alice generates his shared key now what about Eve sitting over here Eve doesn't know a E doesn't know B because these two values do not tell Eve what A and B are so what can E do E can try all sorts of different things Eve can try multiplying them together if you multiply them together what do you get E get G to the a plus B that's not the same thing if I multiply them together I don't get the same thing it's like getting yellow yellow teal red not the same thing as yellow teal red okay。

Can Eve try other things like she can't come up with A and B she can't multiply these together and it turns out because of that diiffy Heman assumption from earlier Eve can't do anything here so there's its provable that Eve cannot take G to the A G to the B come up with G to the AB assuming the diffy Heman assumption holds assuming the discrete log problem holds Eve cannot do anything here coming up with A and B is hopeless multiplying them together gives you a different value E is stuck she can't do anything here so we have a secret value no one else knows it okay questions on the scheme。

So the question was what gets exchanged Yeah the values that get sent over from one person to the other。

 the only two values that have to get sent are G to the a modp and G to the B modP I guess you could technically put a modP here。

Okay， any other questions？HowYeah， theres a question， sorry。

Yeah the question was like why are the why is the modular arithmetic necessary and the whole thing Yeah so the reason why the modular arithmetic is necessary is because if I didn't have it this question no longer has this difficulty so you'll see it more in discussion but the difficulty comes from the modular arithmetic and the idea is that the remainders are really hard to calculate but if I just ask you something like g to the x is equal to y this is really easy to calculate。

Because you can just take the log of those sides， if there was no mockP。

 you can take the log of both sides and you'd solve this problem。

But if I throw a modP in there suddenly you cannot take the log of those sites。

 what does it even mean to take the log in modular arithmetic it becomes a lot harder so that's the rough picture I think discussion will give you a more clear picture of what that looks like。

You can also play with it a little bit like you can try this and try solving it yourself and you'll see that like the numbers that pop out of this equation like GVX。

 G to the1， G to the two， G to the three， they're completely all over the place and they're really hard to predict。

え？強かし。O。80块。What are the limitations they generated because it only not like believe in a matter。

Set of a but you can pick you can kind of if they send like a repeated message or repeat A。

 you can probably guess a。Yeah that's good question so the question was what are the restrictions on G and P So P is a random prime that everyone knows it's usually the same prime every single time In fact。

 there is a prime outlet that everyone uses G is a generator mod P and the only reason why that's necessary is to make the mod math workout so we're not gonna to talk about a too much here but there are a lot of choices for G as well but G is also usually constant everyone uses the same one So A and B are the ones that change every single time I repeat this protocol and A and B can be chosen mod p so you have up to P choices P is a gigantic prime so the odds of U getting the same A and B twice or like pretty low if you do this randomly thiss a good question I'm going keep going talk about attacks on this thing but this is the overall idea they both now have G to the AB so that's their secret key so sometimes people call this DH E and the E stands for a fancy word called ephemeral what does that mean ephemeral means temporary and so the idea。

Here is that as soon as you generate G to the AB， you can destroy A and B。

 which is kind of interesting because once you have G to the AB。

 the A and the B are no longer necessary， so I could go on my computer or whatever my code is doing。

 I can destroy A and B forever and the interesting thing about destroying A and B is that once you're done using K if you destroy K as well you can never derive it again you've like erased old traces that you were ever here。

 so if you would like to create a key that is only temporarily used and then you destroy it never to be used again。

 you can actually use Dvi Hemand to get the key， destroy A and B and when you're done with the exchange。

 destroy K when you're done and no one will ever be able to come up with K again。

It gives you a nice property called forwardward Serecy。

 which we will see again in a lot more detail after the midterm。

 but again the idea here is just that if someone comes a along later and hacks into your computer。

 they have no idea how to come up with K because you destroyed it， A and B are gone。

 there's nothing left for anyone that used to derive K。

So it's a nice property and we'll talk about them more after the midterm but the idea is that diiffy Heman can be used in this ephemeral way so if I want a key that i'm only using for like between me and the bank or making like a secure connection we're talking about some stuff that's super secret and then as soon as we're done we can destroy these keys never to be seen again and in the future anyone who even has my encrypted messages they can't decry that's the idea。

ok。Co so that's ephemeral diffy helmetman that's forward secrecy。

 I promise you it'll come back a little bit more after the midterm。

 but there is one problem which we've been talking about Eve this whole time but what about mallory so can Maory do anything weird if we allow Maory the power to modify messages over the channel well turns out she can so this is secure against Eve the passive attack who just looks at the messages and read them but if Mallory is going to tamper she can do this really funny thing and it was a lot of words and you'll get to play with it in homework as well but basically what mallory is going to do here is she's going to intercept messages and change what they say and she's going to create her own handshake with both os and Bob so here's the sequence of steps。

Alice generates a computes G to the A mod P。 We know that that always happens。

 Bob generates B computes G to the B mod P。 that always happens so they have their secret。

 they have their dis secret and here comes the exchange So the exchange goes。

 Alices takes G to the A mod P and she wants to send it to Bob However。

 mallory is gonna take that message and say like stop right there I'm gonna take that G to the a。

 I'm going delete it and I'm going replace it with my own G to the M modps and mallory comes up with her own M she computes G to the M mod P So what does Bob receive Bob doesn't receive G to the A。

 which is what Alice was trying to send Bob gets G to the M because mallory took that message intercepted it。

 changed it up swapped it with her own G to the M。 Bob gets G to the M Mop instead。

Same thing in the other direction Bob takes G to the B and he wants to send this to Alice but as soon as he gets to mallllory she's like nope I'm taking G to the B I'm deleting it I'm swapppping it from my own G to the MP and I'm letting that go to Alice so Alice instead of receiving G to the B which was Bobs secret she received G to the M which is mallllory's secret so Alice and Bob instead of receiving each other's disguised public secrets they now have each received mallllory's secret。

Now let's see what happens when they compute their shared keys。So what does Aliceice do。

 she takes the thing she received which she thinks is coming from Bob but it's really mallllory's secret key and she raises it up to the A power so she gets G to the A times M mob B what does Bob get Bob takes the thing he received which is also G to the M because Mallory messed with it raises it up to his own secret gets G to the B times M mod P that's what they get So we've already ruined things because Alice and Bob now have different keys So mallllory has tampered with the whole scheme such that they have different keys but it actually gets worse because think about these two keys does Mallory know these two keys she actually does because what does she know she knows M why does she know M her secret Mallory knows G to the A why does she know G to the A because it was sent over the channel by Alice Maory also knows G to the B because it was sent over the channel by Bob if she knows G to the A G to the B and M she can compute G to the A times M。

You can also compute g to the B raised up to theM， so not only has Alice and Bob created two different secrets and Mallory has ruined their date。

 but Alice and Bob are actually both using secrets that Mallory knows， which is even worse。

So if Mallory is able to tamper she can actually cause Alice and Bob to get different keys that she knows which is really bad that's what this picture says another way of thinking of it equivalently is that instead of Alice doing a diffyhamman exchange with Bob she has basically completed an exchange with Mallory so Maory Stockman was like don't talk to Bob talked to me instead and they have exchanged the secret key that Alice and Mallory both know Mallory did the same thing to Bob instead of Bob exchanging a key with Alice Mallory stood in the way and said don't talk to Alice talked to me instead and Bob and Mallory exchanged a key that Bob and Mallory both know。

So all this to summarize really quickly Diffy Heman is not secure if someone is tampering with messages because mallory can cause Alice and Bob to get different keys。

 she can causeory sorry Alice and Bob to get keys that mallory knows and essentially what's happening is Mallory is doing an exchange with both sites okay if we want to solve this we you have to come back next time when we'll talk about morekes last couple really quick things I will say and I guess we'll save this for next time really quickly I guess so Dffyman is an active protocol in the sense that Alice and Bob have to exchange things together so we can't just have like Bob sleeping and they can derive the same key they both have to be all and at the same time if you don't like that assumption you have to come back next time and the final thing I'll say is that it doesn't prevent authentication because you don't know who you're talking to so even after you finish deriving the secret with someone else there's no proof that the other person that you derive the secret with this Alice Bob or mallory okay sorry for going over time I'll finish this next time we're。

So yeah see you next time sorry about that。I guess we people on the recording if you're really curious。

 the final slide which I won't talk about in any detail anyway。

 is just that there are other ways to come up with Dy Heman that don't involve discrete log you just need some map problems that's hard so that's that Okay so if're going over I will see you all next time。



![](img/9d6dd1e820560a2bf6b7c455f586d69c_3.png)