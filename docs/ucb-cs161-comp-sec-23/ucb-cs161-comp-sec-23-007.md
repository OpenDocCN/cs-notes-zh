# 007：UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p07 -07--CS161 FA23- Lecture 7 - Block Ciphers.zh_en -BV1YGbceREDs_p7-

他到时候。

![](img/5c9628945c4fc9b7ead83711245d97e6_1.png)

。Okay， let's do the thing。All right， so I got to finish up。One section from last lecture。

 so these are the lectures that from last time for your reference and as soon as I get this done。

 I will keep going onwards to today's content。Okay。

 that's the plan Okay so this is the second of many cryptography lectures lastly moving through a bunch of definitions and today the goal is to start with a couple of cryptographic schemes okay。

Soello。This is the roadmap you've seen before we saw it last time you'll see it over and over again and so for almost all of today we're gonna be in this top left corner and what it means to be in this top left corner so what it means to be in this top left corner is well we are using symmetric key so that means that for all of today we're going to assume that Alice and Bob people trying to communicate they know a secret that nobody else knows how they get that secret is not our concern for today and the other thing about being in this top left quadrant is that we're dealing with only confidentiality today so our goal is just to make sure attackers don't read our messages and we are not so concerned about what they are not attackers can modify our messages that'll be a later date okay so that's our setting for today so we'll get started with our very first scheme which is onetime pads so to tell you all about one time pads I have to give you a quick review of bitwise Xor which you may or may not have seen from our previous class so bitwise XO takes。

In two bits like it is a zero or one outputs a bit outputs one of the two bits are different outputs zero up they're the same and here are some useful properties most of these again they either seem familiar or you can just prove them based on the definition of x or but there is one that's kind of handy that I'll all attention to you down here which is this one so if I say X X or y x or x turns out the two xs they cancel so we see it that X x or with x is zero and so this ends up being y so this last property is kind of handy if you're not convinced you don't have to believe me you can prove it yourself by using the definition of x or on the left but those are the properties we're gonna to see a couple times today so good to have them in mind。

Okay。Something else pretty cool about XOs is that you can do algebra on them and again you don't have to believe me you can go and try this yourself on some examples and you'll see that this always holds but something pretty cool is if you have some expression with Xors and you want to solve you can actually x or both sides and the equality still holds so if I x or both sides by one this equation still holds and I know thanks to my handy property from before that if I have one x or1 it cancels out and on the left hand side I've just left with y and on the right hand side and I'm left with zero x or1 which is one okay。

So hopefully not boring you too much if this is all review。

 but that's the extra algebra you have to know for this unit， at least， okay。

Great so here's our onetime pad scheme is our very first scheme and remember for all of our schemes we have to decide a couple things so one thing we have to decide is what is that secret key what's the secret value that Alice and Bob both know but we said that in the symmetric he' setting we're going interpret everything the key the messages everything as ones and zeros and I don't know maybe it's an image but we can always interpret the image as some sequence of ones and zeros so the secret that Alice knows there it is it's sitting right in front of us it's that sequence of ones and zeros how is it chosen for today we'll say it was chosen randomly Alice and Bob both know okay great。

So Ali Bob would know this key how was it generated we flipped the coin okay it came up head so we said this is zero。

 we flipped it again we came up tail so we said one we did it over and over again we got this long string of zero on ones that's totally random could have been anything okay。

Next， we have to come up with how do you encrypt messages I have a key I'm given a message How do I scramble up that message using the key to produce the cipher textex that's our encryption algorithm so let's do it here's the message there's the key and you can imagine there's so many different things you can do here to combine these sting output something。

 some of them are secure some of them aren't here's what one time pad decides to do so we decide remember that like Xor thing that you just saw that's pretty useful so let's use that to scramble up the bits so we're gonna do an xor on every single one of the bits one by one so the first bit of M Xor with the first bit of K that's the first bit of your output ciphertext do it again for the second bit and the third bit and every bit gets an independent xor and our result is this cipher textex out here it's totally scrambled up okay great we have our encryption scheme。

Now let's come up with our decryption scheme so remember that in our setting and the story between Alice and Bob Alice now takes this hyperphertext。

 sends it over to Bob over an insecure channel， which means that other people including the attacker they can see this value of C and now it's up to Bob to decrypt it so let's see if that works。

Okay， so what does Bob have Bob knows the key whenever you're thinking of cryptography sometimes when these schemes get really complicated。

 one thing that always helps us to think what values do you know， but what values do you not know。

 especially if there are a lot more symbols than just K and C and M you might have to start thinking to yourself what does Bob know this case Bob knows K why because K is that secret symmetric key that Alice and Bob both know Bob also knows C why because Alice passed it over to Bob over the insecure ch So Bob knows both of these values That's great what does Bob not know Bob doesn't know M I almost sent by Alice so we have to figure out as Bob what's the value of M So let's do it so I'm gonna propose and I haven't proven it to you I'm gonna propose that the decryption algorithm is to do another Xs So take K X for it with C and do it for every single bit and the result I'm gonna claim the M I've proven it。

 but that's where we're gonna try and people with really good memories might remember。

This was the value of M1001 something something and it does seem at least that when I decrypted I got the same value back so at least in this case it worked but I've proven it to you how do we know this is going to always work so let's go through this scheme in more detail now that we've seen what it looks like unless you're to prove some properties about it is it always going work is it secure can you've learned something about the message so here it is in text I'm going go through it in all the great detail but we generate the random key and to encrypt we do a bitwise xor on every single bit of M and to decry we do a bitwise xor with K and every single bit of C the cyber textex that you receive。

A couple of things I will highlight here are that we're going to assume at least for today that the message is the same length as's the key and also that every single time you encrypt a new message you're going to come up with a new key that's what the rules of this scheme say if you have different schemes they could have different rules so the rules for this scheme say for every new message you encrypt you got to come up with a new key Alice and Bob have to know that new key and the key is the same length as the message that's how the bitwise X works out。

Okay。So now let's prove things about it well one thing we'd like to prove is like does it actually work we saw in the example we got the message back but how do we know that always works so here's the algebra for it。

So what do we say， we know this thing， how do I know this like what's justifying this line of。

Algebra well that's the definition we had from earlier how do you encrypt something you explore the key with a message bit by bit okay what happens when you decrypt something well this is the definition of decryption right so Bob takes K which he knows he takes in this thing which is the value that Alice gave to Bob thats C。

Right and well what do we know about decryption We know that decryption is just exoring this thing with this thing so let's do it Okay。

 I guess before we do that we can take this encryption。

 we know what it is it's K X orm so we plug it in and then now we know the definition of decryption is just xoring the first argument with the second argument so we do that then using that little handy Xor property that I told you about five minutes ago the case cancel out and we get M so we proved that it doesn't have to be that message I chose on the previous slides any message M that you pass in。

It's good to go when you encrypt it and you decrypt it。

 you get the original thing back intuitively all of this proof it's just saying that the case cancel up。

So you encryptpt， you extra with K decrypt， you extra with K again， case cancel out， okay。Great。

 so we know that it works。 Now the question is when Alice takes this ciphertex that's all I sort up with Ka and we send it across the channel。

 what can Eve learn can Eve learn anything about it Well let's find out and we know our definition from last time which is that someone who sees the ciphertex should not learn any more information that they didn't know previously so we even design an experiment or a game to test this out so let's try that out so this was our experiment it's not going to exactly work in onetime pads and I'll explain why a little bit more later but let's take this version of the experiment that you're seeing on this live and let's play the same game using the one-time pad and let's see what happens so we know so I guess let's see I guess you will be Eve and I'll be Alice just like last time okay so you Eve and you have chosen two messages M0 and M1 and you've presented them to me and you know that I' I've turned behind your flipped to coin and then I encrypted either。

N0 or M1 and I sent it back to you and you don't know which one I sent so it's your job to guess so I'm showing you the Cyphert C and I'm telling you I either encrypted M0 or I encrypted M1 but you don't know which one and it's your job to figure out which one and you can do anything at your disposal so do whatever strategy you feel like try to figure out what I encrypted and then take a guess and we can play this game over and over and over again and anytime you guess right you win and so if you win more than half the time that means that I must be leaking some information because that's C that I'm giving you it must be giving you some clue as to whether I'm picking M0 or M1 to encrypt that's how you're winning with probability greater than a half but if I keep giving things to you and your win probability just cannot exceed a half that means what are you doing you're basically guess you have no idea which one I'm sending you're guessing every single time that's why your win probability is a half and no greater So if you are as Eve win with probability a half and no greater。

Then I think this scheme is confidential because you have no idea what you're doing for any Eve out there。

But if you're able to come up with some strategy that lets you win more often that means that you must have broken something about my scheme。

 So my scheme， this onetime pad probably not confidential。 So let's write out this game in some math。

 This is the experiment The experiment is you told me M0 and M1 I turned around I flipped a coin and I sent you back one of these two things either this or this So there are two possible worlds that we have split into there's one possibility where we're in the world where you got this value and you're looking at it right now there's another world in which you got this value and you're looking at it right now and you don't know which world you're in and it's George out to figure out which of these things actually happened It's not both it's not like we did both these things only one of these two things happen you got to figure out which one So let's think about in the expressions what exactly happens in each of these worlds So in like you know multiverse number zero。

If the message that I encrypted was M0。Then you received this value okay and if we do a little bit of rearranging using Xor algebra。

 then we can actually derive an expression for k that's pretty cool So that means that you as E you know C。

 why do you know C because I've supplied it to you and you know n0 why do you know n0 because you told it to me remember and so if you know both these values then you can actually derive what you think K is that's pretty useful So if you know that you're in world number0 you can take the C that I've given to you and the n0 that you've given to me and you can come up with your guess as to what that secret or k is that I'm using you don't know the K that I'm using but according to this you might be able to derive it what about the other world because this is not the only world in which you can be in you might also be in this world and in this world things are basically the same but instead of n0 I encrypted M1 you can play the same game or do the same strategy of you know C。

I told it to you， you know M1， you chose it and gave it to me， so if you ex those values together。

 that's your guess for K， okay？😡，And you can compute this in fact you can compute both of these you know see。

 you don't know which one it is is it that one or that one but whichever one it is you can exor it with M0 and you can exor it with M1 you can get two guesses for K that's great so as the attacker you can see well K could be this thing or it could be this thing and so now your strategy is which of those case was it can you tell well K was chosen randomly so。

You look at these two ks and I ask you which one is the real k you're like I don't know K was just a bunch of random coin tosses random ones and zeros so even though you were able to come up with the two possible values of k you have no idea which is the right one why because I chose K totally at random so both of these are equally likely in the space of all the possible ks out there in the world。

Okay， so all of this proof boils down to the fact that there's two possible worlds in both possible worlds you can come up with a guess for what k is however。

 once you do come up with that guess， you have no idea which K is more likely because K is just a random sequence of aquiintasses so this strategy it doesn't help me at all with a one- time pad and so if you tried this strategy no matter what you do sorry。

No matter what you do， turns out you're just going to be guessing with random probability because even if you come up with these two expressions for a K。

 you have no idea which one is more likely than the other so you just have to guess zero or1 and the odds of you guessing correctly 50% it's like a random coin toss so that's our rough sketch of proof。

 this is not a totally rigorous proof for this to be rigorous we would have to explain why other strategies out there don't work but this is one possible strategy that you could use we've shown that it doesn't give you any extra information and if you extend this proof sketch a bit what you'll notice is that the one time pad if we use it correctly it doesn't leak any information so we use our experiment to proof to ourselves or at least give ourselves a sketch of proof that no matter which world you're in or if I tell you that you're in one of these two worlds the M zero world or the M1 world you have absolutely no idea which is which。

You know， you can go home， dry out other strategies to come up with which world you're in is not going to happen。

 you're not going to come up with something that's going to help you with greater than one half probability。

 okay？That's the onetime patent。 It's wonderful。 Like look， it says perfectly secure。

 So why don't we just go home right now Well there is one problem which is remember how we said Alice and Bob have to use a different key every time they encrypt that's kind of annoying I don't like that because now Alice and Bob have to figure out a whole bunch of different keys and that's kind of annoying so we'll talk about why it's annoying it a bit but one possibility is to say well why bother with a bunch of different keys。

 why not just use the same key on the second attempt or on my second encryption so let's do that So in this case I've got two messages and this time we're not playing the game so when we say M0 and M1 it's not to plug it into this experiment I'm just reasoning about what happens if I take a message and I encrypt it twice with the same key so let's try it Alice takes a message any old message uses the same key encrypts it we know the encryption algorithm as that bitwise Xor and we get this thing as the output。

And remember the output of the encryption that's the ciphertex that's something that Eve sees so Eve can see everything outside this Alice box including this value Okay so Eve observes this value Okay fair enough and then sometime later Alice is like you know what I have something else I want to send to Bob so I'm going to take that something else I'm going to encrypted but instead of following the rules and using a brand new key like this probably should have been you know K2 or something but instead of using a brand new key Alice says you know what I'm kind of lazy I'm just going to use that same key that I used last time and I'm going to feed it into the same encryption algorithm I'm going to get K X or M1。

And Alice is going to send this over to Bob， so in other words。

 Eve as the person observing the insecure channel sees these two values。Okay well。

 these values by themselves maybe they don't tell me anything about M and we saw before that if only one of these was sent just knowing K X or n0 tells you nothing at all about M but what if I see both of these properties well what can I do well now there's lots of things you can do so you can try and ponder and think if Eve has these two values available to her can she learn anything about m0 and M1 can she remember confidentiality is the property that Eve can learn nothing So if she learns anything at all about these messages then we're in some trouble So what could Eve do well I could think about it and ponder here's one possible thing Eve can do Eve could take these two ciphertexts and she could x or them together that's a sequence of ones and zeros and so is that one so I can perform a bit wise X or and if I do that I get this expression which is the bitwise xor of those two things remember our handy little x or properties or something Xor with itself。

Cancels out and why learned this thing。So somehow Eve was able to compute M0， x or M1。

Is that useful yeah it's pretty useful because now Eve knows whether two bits of M0 and M1 are the same are different that's pretty useful and okay。

So it turns out if you use two timepas， you learn something about the message。

 you learn which of the bits of the two messages are the same and which of the two bits of the messages are different and depending on what the messages are。

 sometimes that can actually give you a lot of information。

 but even if it doesn't give you a lot of information， the fact that it gives you some information。

 namely which bits of the messages are the same and which bits of the messages are different。

 that alone already tells us that this two time pad scheme where I reuse the key not secure。

Because E've learned something。If I wanted to formalize this。

 I could play the NCPAA game from before I run the experiment。

 we have Eve send messages we have Alice and cryrypto one I could go through the whole game and show you through that proof that this game doesn't work and it's leaking information but intuitively I can also work it out just by noting that hey as an attacker there is a strategy to learn something that's not trivial about the messages and so that's another way to show that this thing it's not secure okay。

Great。And if you are curious why it is that this is not secure。

 you can even imagine that if Eve learns one message。

 you can guess the other and if you learns the other message， you can guess the first one。

 that's pretty bad， okay。So takeaway from this section is that if you reuse the same key twice a lot of things break so we can't do that we have to use a different key every single time is that easy well not really and so even though we haven't told you how Alice and Bob share a secret it turns out that takes some time So if Alice and Bob have to come up with a different secret every single time that's kind of expensive we don't really have time for that that's the first problem the second problem is like think about what's happening in this case if Alice and Bob want to know a brand new endB secret key。

Right I guess let's start with Alice and Bob want to know a secret endbit message So Alice says a message is end bits long。

 she wants to send it to Bob okay and so before I can send the end bit message what do I have to do first Alice and Bob first have to figure out and agree upon an end bit key which means that Alice and Bob somehow have to secretly communicate endbits of the key between each other and so if you're already going through the trouble of communicating the end bit key why not just communicate the endbit message at that point and so this seems a little bit silly if I have to figure out an end bit key before I can send an endbit message while then。

You know why not just do the thing I did to send the end key and just stick the message in there instead right so we'll talk about this a bit more as we talk about key distributions and how to agree upon keys。

 but the idea is just this takes too much time having to come up with a new key over and over and over again every single time I want to come up with a message is just too expensive。

Okay the only time where this might work is maybe Alice and Bob are hanging out in person and they're like hey I have some keys you have some keys let's share them while we're in person and we have a secure channel between ourselves for now and then once we go our separate ways maybe we'll use the keys later but that's pretty rare in real life that kind of never happens so turns out onetime paths it's a nice idea we saw some applications of those security proofs and how to see if they're secure or not but like in reality people just don't use this because that idea of having to generate a new key every single time it's way too slow okay。

So I mean the only times people users are like in those old-timey spy movies I'm not going to talk about it in too much detail for now。

 but I mean yeah it's not something that people use at least with computers these days but apparently it was used in like World War I Cold War era so' very curious about that there's a slide about it not going to talk about it than too much detail but that's one time path so we saw that if you use a different key every time we can show that the attacker can't learn anything about the message if they only see the Cytext however we also saw that if you reuse the keys then a lot of things go wrong and finally we saw that if you do reuse the keys then it's really hard to come up with or like this scheme is really hard to use okay。

That's it from last lecture， anything else you want to know about one time pass before I abandon this and go to the current lecture。

Question was why not try exorting both possible cases with C and see if either one gives you a message back Okay so the suggestion was to go back to this strategy I'm going to go through it in too much detail right now。

 but the suggestion was well you know maybe what I can do is I can take the cipher text I can try and decrypt it with both of these keys that I came up with and see if one of the messages came out。

Yeah I'll think about it some more， but in theory the idea here is that those two keys are both equally likely。

 at least that's what this slide says and so because I don't know which key is more likely than the other the scheme is secure but I'll come back and think about that some more at the end to your question okay is it didn't make sense don't worry about it as a question on zoom okay。

Alright so let's talk about block cphers， which will fix our problem from earlier and we'll start building our way toward schemes that are used in practice okay so I won't go over the summary in too much detail but it's there if you want it let's talk about block ciphers we're still in the same square as before because onetime pads it did not achieve our goal of giving us confidentiality in a practical weight so we're stuck in the same square we got to finish up the square and then we can move on to some of the other ones all right so to do that I'm going to introduce a new type of function it's going to look kind of similar to the previous one but we'll see how this is implemented and how we can use it as a building block for later okay so I'm going to walk you through some math and then we'll talk about what this thing actually means okay。

This thing is called the block cipher so the block cipher is the algorithm here。

 You can imagine that like living in this block it's some piece of code that's going do something to all the bits and shuffle them around and manipulate them in some way here's how you define a block cipher I haven't told you what's going on inside the box there's many different types of block ciphers but every type of block cipher has to follow this definition that you see on the slide So every block cipher has an encryption algorithm and a decryption algorithm that should feel pretty familiar and in both cases when you encrypt something what do you do you take in a key you've take in a plain text and you put a cipher text just like we saw from before okay the thing that's a little bit different from our one- time paths from before all a couple differences are this thing living in this E box it doesn't have to be x for it can be something else and we'll talk about what those other things are but let's think about the inputs so this thing is gonna to be K bits long and the plain text is going to be n bits long both of these are a fixed number。

So once you choose the value of k and the value of n for your specific algorithm， they can't change。

 so I could say E the code living in this e box is some algorithm that works for 128 bit plane text and 128 bit keys or whatever and once you pick those sizes they are fixed so block cphers are for a fixed size plane text and a fixed size key even though on the slide I said K and okay。

And what's the output， the output is a sitephert of length n bits。

 so if you pass in plain text of n bits， you get sitephertext output of n bits， okay？

And what about decryption， It kind of looks the same。 You pass in a key， It's a fixed length K bits。

 No changing it once you pick K fast Mbit hypertext。

 get out an endbit plain text Okay should you feel pretty familiar And so this is a general class of functions and just like before there are some properties we want but this is not just a specific function like the Xor。

 this is a whole class of functions and so anything that you can possibly think of that goes into ebox or the D box could be Xor could be things that are more complicated。

 they should have some certain properties So one of the properties is that well it better be correct And so if you encrypt something and then decrypt it back you'd better get the same thing and we'll talk about how making e sub K of pernuation is a fancy way of ensuring that when you encrypt something and decrypt it。

 you get it back。Second thing I will notice that we'd also like this thing to be fast and we'll talk about fast in a bit more detail。

 we're not gonna be too rigorous about it but the point is in this E you'd better not be doing something that's like horribly slow because we want this to build or we want to build block hacks and algorithms that are reasonable for people to use in practice so just in the back of our heads efficiency is a nice thing to have even though we won't like prove it okay and the last thing is how do you prove that this thing is secure living in this E is some algorithm we don't know what it does we'll show you some specific examples but the goal is whatever you place in that E or that D box whatever shuffling of bits you choose to do in there it has to behave like a random permutation what the does that mean we'll show it to you in a couple slides so stay tuned but those are the properties that we want and this is the general picture of all the schemes that we're about to see。

Okay， let's do it。So another way of thinking of these schemes is well as we said from before。

 we don't want to change keys all the time because we already know that coming up with different keys over and over is slow it's a waste of time is not practical so another way of thinking of this E sub K of M function right you were like wait why not write this the way that I wrote it from before before I kept writing E of K comma M but another way of thinking of E and this is kind of weird and you know even when I saw the first time took me a bit to wrap my head around it so another way of thinking of E is that E is like a whole family of function。

Okay， and so there's a whole family of functions， for example， there is E of zero comma M。

Okay and once youve fixed k equals zero， this is now a function that maps an end bit input to an end bit output。

 why is that the case because you've already chosen K so the only thing left is to choose M passing in an M and then gets an output。

But there's another function in the same family which is E of you know one comma M this is the function where I chose k equals1 so as soon as I choose k equals1 I lock it in。

 I don't change it and I get a function that instead of having two inputs it only has one input because I already fixed k equals one and now I'm passing in end bit inputs of plain text and I'm getting n bit outputs。

And well you see where this is going， there's another function in this family which is you know two。

 you can imagine that's like some sequence of ones and zeros comma M and you get the idea and so another way of thinking of this E function is not that it's a function that takes in two inputs and outputs one output。

 you can think of it as like a whole family of functions and k varies in each of those functions so what I'm saying here is like as soon as you pick a k you lock it in and as soon as you lock into K instead of looking at this whole family of functions you've zoomed into exactly one of the functions where k is locked into your chosen value and as soon as you use that one where K is locked into your chosen value。

 then you now have a function， you know K is equal to whatever your chosen value is so your function now reduces to just taking an inputs of input and outputting inputs of output。

Okay okay it's kind of a weird way to look at things you can do the same thing with decryption as soon as you lock in a K instead of mapping two inputs。

 it just maps a single input to a single output， but the reason why we think about this and I guess just for notation purposes that's why I've put the K here as a subscript because now I can write these as an E1 comma M E2 comma M and now even if you look at the notation it kind of looks like they' are a family of functions right the first E。

 the second E the 30， the fourth0 and the difference between each of them is just which key you're choosing to use so that's why I've chosen to write it in this slightly funny way。

But anyway， all of this is to say E E and D instead of thinking of them as two inputs and one output you could also think of them as a family of functions。

 as soon as you choose a k it collapses down to a single input single output function with a fixed k okay all of that said let's think about what happens if you fix a k so let's fix a k so on all of this slide we've decided that we're going to use some k I don't care what value it is but this e sub k of M it's only going to taken a single input n and it's going to output some sphertex that's my fixed e sub k and I can do this whole slide once for every single K that I can think of okay。

So here's the idea。 As soon as I fix the K， I now have a mapping of inputs to outputs right So if I say I would love you know E of some sequence of bits。

 whatever M。 this is one of the functions in the family it's not the only one。

 but it's one of them now what I can do is I can say okay I've already chosen K is 1，2。

40 I Im going to change for my purposes for now and in this M I'm going to pass in all the possible 128 bit or n bit inputs So I'm going to pass an m equals0 M equals1 M equals 2 M equals 3 I'm going to pass in all the possible Ms and what I end up getting if I compute all of those encryptions is I get a mapping of inputs to outputs So this is the input it's the ciphertex or it's the plain text。

 this is the output it's the cipher textex So I get a mapping and so if we say n equals 2 which is what we're seeing on this slide that means that there's two bits in the input that means that for this particular function for this particular。

K setting where I chose k equals 1240 you could have chosen something else it looks like when I pass in 00 it maps the 01 so if I try to encrypt 00 with this specific heat function。

 not any function but the one using the specific key I get 01 if I pass in01 I get 00 passing in 10 I get11 I pass in 11 I get11 that's the mapping that was inferred to me when I took all of the inputs I ran them through the encryption function and I drew arrows to what their corresponding output was。

Okay。And so you can do this for all of the possible settings of E sub K of M right you can pick a K you can draw these mappings and so what does it mean for one of these functions to be correct remember what it means to be correct is that if I take this input I encrypt it it better be the case that I can take the same you know key and decrypt it backwards right but like look at this mapping over here。

Is it the case that I can always decrypt a message well let's see there seems to be a problem with you can think about you know try and predict where the problem is seems like there's a problem down here。

Because when I took this particular function there's a whole family and I chose this one seems like when I passed in 10 and I encrypted it with the key。

 I got11 then I took 11 and encrypted it with the key and I got11 so what does this mean this means that well suppose that I presented to you the Cyphertext 11 and I said here's the key here's the Cyphertext 11 please decrypt well what's the decryption is it 10 is it 11 is it both is it neither I don't know it seems like what's happened here is that because two of the inputs mapped to the same output if I then take that output and I ask you which input or what was the correct input I want to go backwards I want to decrypt。

I can't uniquely figure out what the original plain text was so that's a problem and in math what we're like the mathematical way of saying this is that this function is not by objective because there are two inputs mapping to the same output so the intuition here is that if I have two plain text and they mapped to the same output that's what this expression says。

It's exactly what we're seeing here then if I give you that sideex and I say here's  one1。

 here's the key， please decrypt you're like I can't because one one it could decrypt to 10 or it could be decrypt to 11 I don't know which one you meant it's not unique so if the function is not byjective we have this problem and we're stuck。

😡，Okay so in order for this function to be correct。

 if I decide to map out exactly where the inputs to outputs are。

 it can't look like this picture on the left where there are two inputs mapping to the same output it needs to be what we call a mutation or a byjection and what that means is that each input should have exactly one unique output corresponding to it like look at this one on the right this is beautiful we like this one because for each input there is exactly one output when you encrypt 00 with a given key you get 01 and that's it right there's nothing else mapping to0100 doesn't map to two different outputs it's exactly a one to one mapping if I encrypt 00 I get 01 by decrypt 01 I get 00 beautiful and this holds for all the inputs that I can possibly give okay。

So that's what this slide says we need biions in order for our block samples to be correct so whatever that e subK is doing under the hood it needs to be the case that if I pass on all the inputs each input maps to a unique output。

So one to one mapping I can't have one input mapping to two different outputs that would be too weird I can't have two different inputs mapping to the same output then I can't decrypt so one to one mapping is what I need for correctness okay。

😡，Great， so I've at least proven or at least given a condition for what it takes for one of these E sub K of Ms to be correct。

Okay， and remember， if this is a whole family of functions。

 then this biion has to hold no matter what KI plug it。So however you design this function。

 it needs to be the case that whatever K you plug in， you always get a byjunction。

The idea is you walk in a K and as soon as you lock in a K， you can draw one of these pictures。

 mapping inputs to outputs， or at least imagine drawing one of these pictures。

 and it needs to be the case that the resulting picture is a bijection， no matter what K you choose。

 if so， then this E algorithm that you've written， it's a good block sitepher， okay。

That is our block cipher。 Well， let's keep going。 Let's think about how do you know if this thing is secure so。

Let's think about security Well again we can model security as a game that's what we like to do so i'll give you a definition that's kind of hard to read and then we'll try and think about is there a way to model it as a game that is easier to understand so we already know that there's a whole family of functions and as soon as you pick a K what happens is you can write out the whole mapping of inputs to outputs and that's your encryption function so I'm like Alice and Bob we choose to use key 1240 or whatever and as soon as they choose the key they now have an encryption and decryption function that they can use and the encryption and decryption function it could be some piece of code and it probably is but you can also imagine as being this projection of inputs to outputs okay。

And so。When I know which function I'm about to use。

 I can use that function and using that function I can drop in all these arrows telling me which inputs map to which outputs right and so our goal is that wherever those arrows fall it needs to be unpredictable that's the intuitive idea。

😡，The intuitive idea is that whatever this E algorithm is doing。

 I have no idea what it's doing it' probably running some code。

 but whatever that E algorithm is doing， it should， you know when I see  zero，0。

 it should map zero zero to something totally unpredictable。😡。

So00 to 10 y I don't know it's unpredictable or like01 to 00 and don't know10 to 01 there doesn't seem to be any rhyme or reason as to where these arrows are falling and that's what we want we like that because that's gonna to be hard for attackers to guess if these arrows fall in a really predictable way then this block Cypher is not secure because attackers can figure out where the arrows are pointing and if they can figure out where those arrows are falling。

 they might be able to figure out oh given that this is the input or given that this is the cipher text even if I don't know the key well know maybe they can predict that the arrow came from somewhere else we don't want that so we want this thing to behave randomly and in particular we want it to behave so unpredictable that it looks random so what do I mean by looks random but what I mean by looks random is we want to behave like this so we already know that one way to drop all these arrows is to pick an E function some piece of code walk in a K as soon as you。

K you can run Em inputs to Em outputs， you plug in all the em inputs。

 you get all the embit outputs right and that's your encryption。So well。

 that's one way to draw one of these sets of arrows is to pick the K。

 run all the inputs through E of K， and then get all the outputs and the arrows follow what they fall。

That's one way to do it， but there's another way to draw these arrows which is draw them randomly so let's do that This is another way of drawing the arrows so one way of drawing them is to use the algorithm and run the code of this E function that was given to you but a completely different way of drawing these arrows is to just pick them at complete random so let's do that all right so here we go and I'm going to flip my imaginary point or you can be my imaginary point for me and I'm going to say okay0 zero and needs to map to some value。

Let's do it randomly let's not let's not ask you how to do it you know I could ask you I could pick a key and run it through the E function I'm not gonna do that I'm just gonna choose chaos so 0。

0 it maps to any of these four pick one at random Okay one1 first one I heard okay great now this does still have to be a byjection because we're looking for block sampless that are correct or we're thinking of you know the set of permutations which means that we're looking for fiions one to one mappings so01 I need to drop an arrow it can go to any of these remaining three can't go to one1 because that's not a valid byjection so where does it go 161 random numbers generator go。

0， one， okay，arrow， now one zero has two more choices， What do you want？

0 zero zero zero two people that are at the same time， Okay， so that's a really weird arrow Okay。

 so that's my random mapping decided by you know。Reencing the CS161 random number generator okay that's one possibility right and so what we are saying is that if it is the case that the set of arrows that fell out of the encryption function look exactly like or they behave just like this completely random arrow of drawing version that we saw here。

Then it is the case that this boxypher is secure so well how do I what do I mean by that that seems kind of a weird definition so i'm going to formulate it like a game because I think games and experiments are easier to think about than saying something like oh this boxypher behaves like a random permutation it's indistinguishable from a random permutation I think that's kind of hard to think about so I'm going to play a game so here's the game okay you are eve like you always are and so。

Yourre Eve， you don't know K because Eve doesn't know K。 that's our assumption So you are E。

 I present to you two different functions right a function is some mapping of inputs to outputs。

 I present to you the one on the left and I also present to you the one on the right and I tell you I came up with these arrows two different ways So for one of these two I'm not telling you which one but for one of these two I have my K you don't know it。

 but I've chosen a K， I took the encryption algorithm with that fixed K so I use E sub K I plugged in the inputs and I got the outputs that's how I drew the arrows for one of these two but I'm not telling you which one for the other one what did I do I dropped the arrows in at random just like we did together And so as Eve。

 the person who doesn't know K， your challenge in this particular game is to tell me which of these two arrows or sets of arrows。

 which of these two functions is the output of E sub K for some chosen K and which of these two functions is the one where I dropped the arrows at random。

Do you know and if you don't know， in other words， you have no idea how to guess this with probability greater than a half and you don't know Kate。

If you have no way of guessing this with probability greater than a half。

 that means that our block cipher with some fixed K is behaving like a random for mutation because its behavior from the perspective of you。

 someone who doesn't know K， it looks more or less random is it actually random well not really it's a piece of code that's systematically generating these arrows。

 but if it looks from your perspective like it's just total random arrows you have no idea where they're going then it is the case that this block cipher。

 it behaves like random and so Eve has no way of figuring out if the cipher text is  zero1。

 where does it point at Eva has no idea because these arrows。

 they might as well have been dropped in that random。

Okay that is my long explanation for how you show whether a block spher is secure so the shorter version。

 the summary of all this stuff that I just babbled at you is that if it is the case that the inputs to outputs are unpredictable you know given an input without knowing the key I can't really predict where the output is then the block spher is secure the way to make it formal and give it a gain to formally define it is to say if I show you the function and you cannot tell the difference between the function with a K and me dropping in the arrow is at random。

 then it behaves like a random permutation so from your perspective guessing which input maps to which output is basically a random guessing into you so that's how it's secure。

Okay， any questions about this， I know I've talked for a long time so。

Your return to talking me if you want？No， okay， I'll talk some more then。

 So that's the distinguishing game。 let's think a little bit more about well。

 there is one possible way you can break this。 So you know I'm not gonna go into it in too much detail。

 but one possible way you can break this is well you could just try all the k so you could say okay well。

 I know one of these two came out of e sub K and the other one was just dropped at random and I'm not going prove it to you。

 but the set of arrows that you get from dropping at random is way bigger than the set of arrows you get out of a fixed e function So it's pretty likely that one of these two came out of an e function。

 the other one didn't or I know that for sure And so what I could do maybe that didn't totally make sense sorry but what I can do is I could just try all the k So I could say okay you're telling me one of these two came out of e sub K I don't know but all right I accept your challenge So I say all right。

 I'm going to try E sub1。And I'm gonna to draw the picture corresponding to E sub1 and see if it matches one of these two if it does。

 I know which of these two came from the E function and I also know your key okay if E sub1 doesn't match any of these two I go again and I try e sub2 I draw the picture I see if it matches either of these two if it does and I know which one came out of E okay neither one okay and I try e sub3 So one thing an attacker to tries is they could try a brute force attack they could say I'm just going to try all the possible k I'm going draw a picture for all the possible case and see if any of them match one of the pictures that you gave me or one of these bijections that you gave me and when I find one that matches I'm like aha know if I find one that matches this picture I'm like aha this is the one that came out of E with a particular key and this one is not I could even try all the ks and find out that I never get this particular set of errorss okay。

So we could do that， that's a possible way to break this and if you do that what's the probability that you win this game 100% because you can always figure out which of these two is coming out of E and which one's not。

However， how long would that take well let's try plugging in something that people use in real life which is people tend to use k equal goes 128 it's pretty common and so that means if k is equal to 128 how many different eases do we have to try we have to try two to the 128 possible ease is that big yeah that's really big it's so big that it's going to take and there's all this math to prove it i'm not going to walk through it。

Turns out if you want to try all two to the 128 different possible case。

 we would be here until like the sun like burns out okay I don't know how much time that is。

 but it's like astronomically long by the time you're finished trying out all the possibilities of this 128 big key like the universe will have collapse or like the sun will have like swallowed the earth I don't know like astronomical level things will happen and so we don't have to worry about it so yes。

 technically there is an attack on this scheme where an attacker can distinguish but it would take so astronomically long that it is not something that we need to concern ourselves with。

Okay。What if what if you are worried， you're like okay。

 but you know what if my thing is so secure that it needs to be secure。

 even if the sun swallows up the earth okay， fair enough。

 then you can upgrade to a 256 bit key and now I don't even know what this is this is like astronomically astronomically long so it's like know even if after the sun collapses know you're still not even close okay I don't know what this is。

 this is like my brain's gonna like collapse into a black hole thinking about these numbers so I'm not going worry so in general。

 even though brute force attacks are possible with block stackers where you try every key as long as you use a reasonable key size which in today's terms is 128 B or 256 bits or anywhere in between it's going to be the case that nobody's gonna have a shot at bruteforcing it within like the lifetime of the universe okay。

So that's what this slide says in a lot of words。So we figured out blocks we know how they're correct they used to be a byjection we figured out how they're secure the byjection the arrows that pop out of the block cipher need to look random for a given key so how do we know if they're efficient again there are ways to prove this we're not really going to go through it but the key behind block cyphers to make them efficient is well if you think about the inputs of block ciphers they're ones and zeros。

 they are a lot of bits and so how do you implement this block cipher there's a lot of different block ciypher algorithms out there but almost all of them they tend to use things that are cheap like X4 is really cheap on a modern processor and that's like a 16 C topics I'm not going talk about it in huge detail where like bit shifting is really cheap looking at values in a small table these are all really cheap operations on modern processors and so。

In general block cphers the amount of time they take from our perspective and like a modern world basically insignificant okay that's all this slide says so yes you could certainly decide you know what my block cpher is going to take the bits and it's going to compute this like super complicated mathematical formula like sure but that could take a lot of time modern block cphers they tend to use things that are really cheap like repeated applications of xhors bit shifts like little lookup tables because those are fast and we like this okay。

So I told you all about B Is， this category of functions， I have not told you what goes in the e box。

 I've also not told you what goes in a D box yet so let's figure out what goes in those boxes。😡。

Well there's a lot of different things you can put in there and so one of the first ones that people use was something called DES this is obsolete now and I mean one of the reasons why it's obsolete is because the key is 56 bits and even though two to the 128 is astronomically big two to the 56 maybe some supercomputers can handle that so this is the older version people don't use it anymore but it is here one thing on this slide is kind of interesting is that the National Security Agency influenced it so who knows what seccy is snuck in there but anyway that's the DES people don't use it anymore and so。

Around like the 1990s or so people kind of realize like okay this thing it's getting kind of old people computers are catching up 56 bits is not enough and so they need to design a better blocky they needed a better algorithm to shove in that little ebox to compute encryptptions and decryptions so here's what they came up with what they did is well they had a race and so they opened this up to the security community and they had this big old competition and whoever won became the like one trueop blocky standard that everybody in the world would choose to implement and one one thing that kind of funny is that one of the finalists there were five finalists out of like hundreds of submissions and one of them was actually co-designed by David Wagner who teaches I think data8 161 a couple times I worked with them before on 161 so pretty cool if you ever see him around asking him about two fish and I'm sure you'd be happy to talk about it that's the fun site so go Berkeley the sad side is that he so he didn't win the competition but hey I'd say one of the five finalists。

For the encryption standard that the whole world uses is pretty good now I'm never getting there so that's pretty good。

 but anyway the takeaways that what they ended up choosing was fast for all platforms。

 it was something that they thought was secure and that became the advanced encryption standard or AE so the name during the competition phase they called it Ryanale I think that was the person who inventeded it maybe but once it got adopted and won the competition now everyone just calls it AE okay so here's AE is this is the thing this is the algorithm that went inside that box and even though you can put lots of different things inside there like if you feel like it big Berkeley fan。

 you can go take Dave Weagner's two fish and shhoov it in there but most people in the world they use AE which is the Rale algorithm and this is what it looks like in the high level there's actually different versions of this algorithm depending on what key size you like so pick your favorite key size there's an AE 128 algorithm AE 192 AE 256 depending on。

Size of your keys Okay， most people 128 ps is enough if you are astronomically paranoid go use the 256 bit version that's all right。

 The block size is 128 bits and so。When this algorithm was designed it was designed for specifically 128 inputs that means that you cannot pass in you know n equals anything else n is fixed at 128 there are three versions of this algorithm fixed with K equals 128 192 to 56 that's it nothing else okay now how does this thing work well it's pretty complicated it's a lot of shuffling I will show you how it works although the slides are all blue so you don't have to know but as you can see it's like the two takeaways that I have from these slides are it is complicated as heck I don't know what half of this stuff is and you know。

That's one takeaway the other takeaway is that all the operations are pretty cheap they're all exors or like shifting bits around there's no like ridiculous mathematical algorithms here where basically you can almost think of what we're doing here as we're taking the input and using the key to shuffle things around in a way that we hope is deterministic and hard for an attacker to guess so for example here we're like swapping bites around like we take the bitetes we form a little grid and then we instead to swap like that one and that one and I don't know okay。

And then you know we it swaps them more and we like shift these over and shift those over and it doesn't really matter how these work exactly。

 but the idea is that with these repeated shifting inputs and outputs ultimately what you're going to do after all these like more cycles and more mixing right and so ultimately where you're going to do right is going have all of those Ms as we saw from before and this algorithm。

 what is all this shifting doing you know when you're shifting and you're like mixing rows I don't even know what that means but when you're doing all this xoring and shifting and mixing the ultimate goal is just to take in some bit of inputs and decide which output of maps to so your ultimate goal is just to decide that arrow and if it is the case that deciding that arrow happens in a very unpredictable way then your as algorithm is secure that's all that we're saying here okay。

There's more okay I'm not gonna to talk about this as you can see it's a lot of stuff So one funny thing I will say though about AES is that it has actually not been proven to be secure so we already saw from before that if I can play that game where I give you a box a permutation。

 a picture of arrows and I say one of these was computed by taking AE you know the AES block cipher so maybe something like that and I chose a specific K I didn't tell you which one but I chose the K I plugged in all the Ms that I drew the picture I drew the arrows and I handed it to you and I also gave you one where I drew all the arrows at random and I want you to know which is which and if I can prove that no matter what you choose to do you cannot distinguish then it's secure turns out for AES there's actually no proof for it which is kind of funny however it's been 20 years since it was invented and nobody has even come close to breaking from this thing the way that these bits are shuffled is just too unpredictable for anybody and so nobody has ever figured。

How to deduce patterns from it， as far as we know， the arrows and the places that they drop in are more or less unpredictable。

I guess since I've said this word unpredictable and random a lot。

 I will briefly mention that when I say that those arrows are dropped in unpredictably it does not mean that you cannot decrept messages right so like if I say you know that's a really weird squiggle so if I say you know like I want E of K of M and I've chosen some certain K and we've seen this picture over and over again know。

Okay， just to be clear here， right？When I choose e sub can I plug in all the ends and even though these arrows are dropping a random so even if I'm using AES。

 you have no idea where those arrows dropped in once I fixed this like it's fixed right so as soon as I encrypt something it moves to some or it maps to some output and I can still decrypt the output right so I am not once I drop in the arrows at random they're fixed for this particular e sub K so it's still decryptible it's still a byject it just so happens that the way that I drop in the arrows is super unpredictable that's what makes it secure okay that's AE that's what people use it's one of many block cpher but it's the one that won the contest it's who use okay。

Great so are we done well let's take this AES block cipher and let's run it against so far we've been running experiments that like for the one time pad we ran it against a variant of this experiment it wasn't exactly this。

 but you know what。You know this slide even tells me no one's broken for 20 years I'm feeling pretty good about AES so i'm going to shove it into the N CPPA block Cypher game or the NCPA confidentiality game that we did from last timem i'm feeling pretty confident you know this I'm going to take this block Cypher scheme and we're going play the game together and let's see if block cphers are secure Okay so here we go。

Let's do it So we're gonna play the game on'm Alice your Eve as you always are and so here we go right as we said from last time because you have the power to trick me into encrypting things you're allowed to before and after the challenge phase you can always tell me hey。

 please encrypt this and I will always faithfully encrypt it for you what function am I going to use I'm going to use E sub K that's the function I'm going to use okay so here I go know I'm going you're gonna have to trust and believe that I'm doing this for real so I'm going to say E sub K that's the AAS vlogy I can't run AES in my net unfortunately but I'll try and simulate it the best I can so I'm gonna to choose a random K you have no idea which K I chose and I've locked it in okay。

So E subK of M I've chosen a K that's my block cipher。

 I'm sticking to it and I know that if I take this block cipher and I run it on all the possible inputs today we're using two bit inputs but you can certainly do this for much larger ends in fact in practice these would be 128 bits there's some arrow mapping corresponding to my E subk I'm not going show it to you because it's my encryption algorithm and you don't know K so you don't know where the arrows are you could be anywhere okay but that's my mapping。

 so I'm not going show it to you but you are now allowed to ask me for encryptions and as soon as you're done as soon as you're confident you can then ask me for you can then send me M0 and M1 I will flip a coin and1 at random and then you will get another chance to ask me for some encryptions and then you're gonna guess okay so let's do it so I'm feeling pretty evil so I'm gonna not let you do this in theory you certainly could but turns out you don't need to Eve is pretty smart in this one。

So I'm going to even though you are technically allowed to do this。

 I'm going to skip to the challenge phase just to save ourselves some time so we are going to start here and technically before this started you could have asked me for a lot of encryptions but in the interest of time we're going to start here so you must provide to me two messages M0 and M1 okay M0 and M1。

And this time we're going to use bit strings in real life these would be 128 bits。

 but in this example we're going to use two bits because my slide doesn't fit 128 bits Okay。

 so what do you want M0 to be？You have four choices， it's stupid message。56万。Anything。

 I realize it's not the most exciting of choices， but you got to pick one。

1 zero right on okay and M1 you need to choose a different one remember these have to be different messages。

 so pick another one what do you want。11 okay short so there they are okay you've chosen your messages you've locked them in so now it's my turn I'm going to you know turn around you can't see me I'm going to flip my secret imaginary point and I have randomly chosen one of these two two encrypt you don't know which one。

😡，And I'm going to give you back C and I'm going to tell you that I encrypted00 okay。

 and you have no idea00py the encryption of 10 or the encryption of 11。

 you don't know because you don't know K if you knew K you'd know exactly where my arrows fell and you'd know which one I encrypted you don't okay。

 so onwards we go we go down here to this phase and in this phase you are now allowed to ask me for the encryption of anything you like。

Right and I'm going to have to faithfully encrypt it with a key for you so you can ask me for the encryption of anything and I will faithfully give you the answer okay so。

It's all yours， what do you want to do you're trying to win this game right right what do you want you want one zero okay。

 you sure no anything else， you have you have to take one zero。Okay， I'll give you 10。

 so the encryption of 10 is that okay， satisfied want anything else。

You want11 you sure you really don't want00 or something you really won't okay Okay I'll give you one1 so unfortunately I have no choice i'm you have the power right so you're telling me doing cry 11 I have no choice but to take my key faithfully in cry11 and。

Okay。Now are you happy or anything else， or do you think you're ready to guess B？Okay。

Seems like no one else wants me to encrypt stuff so now is your turn to guess B so to summarize what has happened you have provided to me two messages M0 and M1 I turned around flipped the coin I encrypted one at random I did not tell you which one I encrypted it but I did tell you that the encryption was0 zero and then I allowed you to ask me for the encryption of anything you wanted you asked for one0 and I faithfully encrypted it you asked me for the encryption of 11 I faithfully encrypted it as well now it is your turn to guess okay okay Eve don't let me down how many people think I encrypted M0。

Nobody how many people think I encrypted M1 many people Okay so now I reveal to you what am I chose and indeed I chose M1 so you win this time。

 but I'll get you back next to me or will I because if I run this over and over and over again you could probably use the same strategy on me over and over again so just to clarify what happened for those of you who didn't guess M1 don't think it was anyone in person you never know what happened is now I can reveal to you know I don't know what key I chose。

 but it seems like I chose to map 10 to01 I chose to map 11 to00 and the other two I don't think it really matters okay but basically what happened here is that this box Ipher once I locked it in it was what we call deterministic when I encrypt the same thing twice I get the same output twice we saw that here because I chose to encrypt M1 and when I encrypted M1。

Because I've been using E here， sorry when I chose to encrypt M1。I got zero， zero， okay。

 that's what this is。And then you asked me to encrypt M1 again down here and what did I do I went to my mapping of arrows right as soon as I picked the K the arrows are locked in。

 I chose  one1， I looked oh the arrow points at zero zero so I gave you00 again。😡，So in other words。

 you exploited the fact that when I encrypt something twice。

 I get the same output twice and you want this game and it turns out if we do this over and over and over。

 you're going to win every single time because all you have to do is ask me to reenrypt the two messages and see which one matches。

 you could even just ask me to encrypt one of them and see if it matches or not and then deduce from there。

But the whole takeaway from this whole slide， which I will now give to you in slightly nicer hand rating。

 which is that is that as you can always win the game on bloglog cyphers and that's because you're leveraging the idea that if you ask me to encrypt the same message twice。

 I will always output the same Cypher text， nothing in this is changing as soon as I pick K， okay。

So all of this is to say because Eve always wins block cypherers by themselves， not in CPA secure。

 we went through all the trouble of designing this thing and we said， well look。

 you no one's been able to break it， but at the end of the day。

 E still one using this power of asking me to reencrypt stuff。Okay。

 so how am I doing it on time let's reflect on what we learned this will probably spill into next time as well。

 that's okay。So we learned that block cphers are not N CPPA security and the main flaw that allowed you to win this game to be clear is that this game was deterministic when you encrypt it the same or when you ask me to encrypt the same thing five times you will get the same output five times so when I encrypt something mysterious M0 or M1 all you have to do to figure out what I encrypted is to ask me to reencrypt the same messages twice and it turns out that any scheme out there that has the same property where you encrypt the same thing twice and get the same output twice will always fail this NCPAA game it didn't have to be block cphers。

 any scheme out there that has the same property where you encrypt the same thing twice and get the same output twice always loses this game because you can always pick the same strategy which is in this phase down here ask to reencrypt M0 ask to reencrypt M1 see which one matches and Ju knows there will always be one that matches because when I reenrypt M0 M1 I get the same encryptions up。

Okay。So that means that any deterriministic scheme fails this game and if you think about this game as a model。

 that's a good thing right because if a scheme is deterministic what is our ultimate goal like zoom think about the big picture the ultimate goal is confidentiality we want it so that when you encrypt something the attacker has no idea what you encrypted and they can't learn anything about what you encrypted however。

 if you use a scheme that's deterministic then the attacker learned something right because if I send a bunch of cpher text over the channel and some of them are the same and some of them are different the attacker knowsoo Aliceice is sending the same thing right here and now she's sending something different and now she's sending the same thing as what she's in on Tuesday so if you use a scheme that's deterministic you are leaking information because you're telling the attacker or you're giving the attackers signals when you're encrypting the same thing twice we don't like that so it is a good thing that deterministic Cyyphers fail this game because it means that deterministic Cyphers don't pass our confidentiality。

Test and that's what we want because we think deterministic cipers they're not good they allow the attacker to find out if hey。

 the thing that Alice said today is the same thing as what she sent last Tuesday that's we don't want that so it's a good thing as intended it's like built into the system that games or cis better deterministic they fail the NCPAA game Eve can win。

So that's one issue which is after all this trouble we still don't have something deter deteristic okay what else well another problem is that these things don't even encrypt messages of a fixed or of longer messages right we already said that the AES block cipher as designed。

All those bit shifting things that we saw from before that were super complicated they only accept messages that are exactly 128 bits。

 So if your message is 127 bits like good luck right it's not going to happen with the block cipher or if your message is 129 bits you're out of luck block cis do not accept those inputs you're passing in an input that blockys do not support So it's not going right so block ciphers they're good。

 they're a nice building block and we're going to see how to use them to build something better in I guess the last 10 minutes of today and a lot of next time but block ciphers by themselves。

They don't do what we want， so that's unfortunate， but we can use them as a building so that's the end of block cphers and then I'm going to start trying to build something better at it。

If there are no other questions on them，If you are not NCPAA secure， how does Eve win， remember。

 even is the adversary。Oh how did the block cipher win this competition if it's not NCPA secure so that's a good question right and so remember there's two different definitions of confidentiality that we're working with here so for the block cipher we decided that the definition of a good block cipher was on this slide。

The definition of a good block cipher is this。😡，Right and this is not the same thing as confidentiality。

 this just defines what makes a block Cyypher good and what makes a block Cyypher bad and we decided that block cyphers are good if the arrows fall in an unpredictable random like way and so this thing won the competition all the finalists were good because all of them dropped the arrows in a random looking way。

But just because it passes the test to be a good block cipher does not mean that it passes the test to be a fully。

 here is the slide， it doesn't mean it passes the test to be a fully N CPPAA confidential scheme。

So that's the difference I see a question there's a difference between what makes a block Cyyer good and the fact that block Cypherers do not pass our definition of confidentiality right there's different definitions depends on your threat model okay。

More questions yeah。你穿那个比例哎。In this game or。In general。

figure outYeah so the question was what is Eve trying to figure out if Eve were to try a brute force attack Well Eve is in general is trying to figure out something about your scheme right and trying to break the confidentiality your scheme so on this slide Eve is trying to figure out her ultimate goal is to figure out B but if it is the case that Eve figures out something about k maybe she figures out the exact value of k if Eve can figure out the exact value of k that could help her learn B so Eve's ultimate goal is to get better at guessing B with better than 50% probability but how she gets to that is up to you she could do it by learning something about k she could do it by exploiting something that's really vulnerable about the encryption algorithm itself she could do it by just getting really good at guessing B was01 or picking special and0 m1 so the strategy is up to you but the ultimate goal is to get better at guessing B on this slide anyway see a question okay。

That's our building block。 So let's try to use this thing， know， awardwin block Cypher。

 let's try to build something better。 Okay so we already saw it。 it works。

 It has this nice security property。 We want to use this as a building block as we said from before。

 This is a great property。 The fact that those arrows are random。 That's really powerful。

 But by itself， it's not enough。 So we need more。 we need that with more stuff to build something that is truly in CP secure。

 So we're gonna take those block cypers and we're gonna to chain them together and combine them to build what we call modes of operation。

 which is some fancy term for making them better。 Okay， I guess we'll do one today。

 and then we'll do maybe a bunch more next。 There's three in total I have to show you。

 Okay here's our first one。 So we'll design it together This is the block cipher。

 we've seen it before。 it's our old friend。But remember there is a problem this input is forced to be exactly 128 bits。

 no more， no less， if you pass in anything else， the blackcyclpher will simply complain and say that input is not valid。

 I refuse to encrypt this thing。Okay。Well that's a problem So say your message is 256 bits okay well if it's 256 bits what's our move well one block cpher is not gonna do it so you can try and think about and predict my next move my message is 256 bits and one of these things encrypts 128 bits you know what I'm just gonna pull out a second block cpher now maybe I can use this to encrypt 256 bit messages so how would I do that well I would take my message which is 256 bits I would chop it in half that first half the first 128 bits I pass it through a block cpher with some fixed key the second one I'd pass it through some block cpher with a fixed key but in both cases I would get some cpher text and once I combine it I get my resulting256 bit cipher text that's my first attempt is it good I guess we'll find out a couple of things I will note is that we could have chosen to use different keys here but we chose to use the same one Why is that because remember。

What was the whole point of block ciphers you know why did we go from or why didn't we just quit at one time pads why did we have to go through all this trouble of building block ciphers because we would like to be able to encrypt long messages and repeated messages with the same key I don't want to have to keep coming up with keys that's expensive so in this case。

😡，I have chosen to use the same key for this encryption， that's what this line says okay。

So what we are done， we've already invented our first mode of operation just like that in this mode all we have to do is say if your message is too long。

 shop it up into smaller pieces， take every piece pass it into each of these little encryption blocks use the same key every time because I don't want to have to think of coming up a different keys every single time I get some ciphertex out。

 remember what is this encryption block doing it's taking the plain text it's using that big lookup table it's really executing code but you can think of it as that big lookup table that has all those arrows that are unpredictable we find the arrow you follow it you get some ciphertex output we do it over and over again for each chunk of plain text and then at the end we take all the ciphertex blocks we mash them all together and we get the resulting ciphertex that's a possibility if we do that we get this thing as a fancy name we call it ECB for short here it is in equations and really all you have to do is take the results in ciphertex and put them together。

That is a concatenation operator so you just take the bits， take the bits， know smash them together。

 and that's it side by side。And so yeah that's basically the algorithm so are we done well can we go home well you can go home in you know six minutes but we can't go home yet because this thing is also not NCPA secure and why am I telling you this without even showing you a proof what's your like one word answer for why this thing can't be there's just simply no possible way that this thing could win the NCPA security game。

Deterministic， exactly， it has to be the case at this thing。

Eve will always be able to win using the same strategy as before because if I encrypt the same thing twice。

 I get the same output twice， this block cipher even though the arrow has fall in super unpredictable ways。

 overall the block cipher itself it's still deteristic once I lock in those arrows by choosing a key。

 if I pass in the same input twice and follow the same arrow get the same output。😡。

Still deterministic， still a feel， okay。In case you're wondering well this is a deterministic thing。

 you know， when you say okay， well maybe the attacker can learn when I have a message and I encrypt it and imagines the message from before I can kind of see how that's bad but like is it really that bad well here's a picture that shows you how bad it could be。

So so what I'm going to do is I'm going to take this image to an image of the Linuxux penguin I believe and we're going to encrypt it so the way we're going to do it is we're going to use ECB mode and the way that we're going to do it is we're going to take every pixel so you can imagine this penguin is like it's a grid of pixels right and each of these pixels I can represent it as a sequence of ones and zeros like this pixel is colored white that pixel is colored black that one's colored orange or whatever I can take each of these pixels turned it into ones and zeros and encrypted and that would be ECB mode because I'm taking each individual pixel like this is pixel zero。

 this is pixel one， this is pixel2 I'm passing each one through by block side for encryption with the same key and I'm getting some output so try and predict what will happen as soon as I do the ECB encryption on the penguin and remember if I pass in the same input twice if I encrypt the same pixel twice I get the same output that's the key of ECB that's the key。

Of all deterministic schemes when I'm passing the same input twice。

 I get the same output okay so this is gonna to reveal to you what happens when B syphas are deterministic so we encrypt the penguin and we really wanted this to be confidential we don't want people to know this is a penguin when I encrypt it and send it over so I encrypt it and I really hope people don't know this is a penguin but we can look at it and we can probably guess so what happened here is that any two pixels that were white they got an encryption that was the same any two pixels that were black。

 they got an encryption that was the same there's a little bit of like image artifact and it's kind of funny but still pretty penguinist to me so this is the problem with theministic schemes that we have to deal with we don't like this and another problem with the deterministic schemes is that if I took this penguin and I encrypted it like 10 times with ECB I get the exact same image other every time also not good okay so B syphas are deterministic that is what caused the penguin to appear and ECB itself was deterministic。

It causes you to get the same penguin every single time if you encrypt this 10 different types。Okay。

That's ECB mode So before you go I guess Ill give you a really brief preview of what we're gonna to start doing next time so what we're gonna to start doing next time is we're going to start adding randomness and one thing I will note just before we get there we're going to do it in more detail next time but one thing I want to note because like super common maybe like the most common thing people mess up in this unit so I'll say it over and over again so I want you to hear it first time today and you'll hear it like 10 more times next time is that adding randomness does not guarantee that your scheme is in CPPA secure I'll say it one more time adding randomness does not guarantee that your scheme as confidentiality it is true that if you have zero randomness the whole thing is tministic there's no confidentiality we already saw that with the penguin you play the game and you want over and over you' win every time so if there's no randomness it's not in CPPA secure however just because you added some randomness does not mean that your scheme is in CPPA secure randomness does。

I give you a confidentiality for free you have to use randomness in an intelligent way to actually get confidentiality and just just to hammer in one more time as you like quietly pack up right imagine if I took ECB and I said you know what I'm going to make ECB random by adding a block of random bytes at the end so here are some random bits。

So my ciphertex now is this whole thing plus the random bits。

I added randomness but is this scheme secured well no because this entire section is still not secure I just added clean garbage at the end that's random so that didn't make sense。

 don't worry too much about it but the key takeaway that I want you to hear now before you hear it again next time is if you add randomness you do not get security for you have to use randomness in intelligent ways so what we're gonna to do next time is try and build randomness in more intelligent ways okay I realize I am slowly falling behind but we will make up for it there's some buffer in the lecture so don't worry about it and I will see on Wednesday。

Okay， take care of y'all。

![](img/5c9628945c4fc9b7ead83711245d97e6_3.png)