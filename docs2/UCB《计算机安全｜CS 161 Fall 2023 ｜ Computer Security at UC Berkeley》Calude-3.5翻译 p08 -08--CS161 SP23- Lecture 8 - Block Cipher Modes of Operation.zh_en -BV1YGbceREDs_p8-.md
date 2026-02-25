# UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p08 -08--CS161 SP23- Lecture 8 - Block Cipher Modes of Operation.zh_en -BV1YGbceREDs_p8-

啊关。

![](img/1d1524668e03d5d63cc837748a0f7698_1.png)

Okay， welcome back so I'm going to finish up block samples first from last time we might end up a little bit behind。

 but that's okay we plan for it so we should be all right okay so last time we saw the block with going on people in person can't see this。

ButNow they can。Okay， so this is what we saw last time that was the block cipher remember that it took in key and some plain text the key has to be k bit long and the plain text has to be M bits long K andN are both fixed it runs some sort of shuffling on the K and the n input and then outputs cipher textex that's one way to look at it and we saw how you can implement this using something like AES that shuffles all the bits around another way to look at this is you can also think of this as like a family of functions once you choose a key it's now a mapping of plain text to cipher textex where you have all the plain text on one side all the cit on the other side and the block cipher encryption function with a certain key as the setting mapped all the inputs to one unique output so that's what we saw from last time now something that people asked last time afterwards which I figured I should clarify real quick is that block ciphers have a good security property which we saw so that was here。

So this was the security definition of block Cypers and so we said that if blockypher is secure。

 if these arrows are indistinguishable from arrows that you drop at random。

 so if an attacker cannot tell whether the arrows came from the block cipher with a certain key setting or if they were just dropped in at random and we say this blockypher is secure。

 however， just because a blockypher is secure using this definition。

 oh interesting speaking language is shiny simplified。

So just because the block sign for secure using this definition does not mean that it's secure using our inPAA definition。

 so while this。Definition of security is a nice building block for making our block Cy for secure it doesn't by itself imply that we have NCPA security which is what we ultimately want so these are two different definitions of security this tells us whether a block cypher is secure or not using this particular definition but just because a block Cypher satisfies this definition which is that it behaves like a random per mutation it does not mean that block cypherpers actually solve the problem of allowing us to communicate between two parties the reason why we saw last time it' because block Cypherpers there's no randomness if you encrypt the same thing five times you get the same output five times so that's where we're going to spend all of today or most of today solving。

So what we already saw there was one possibility from last time， which is。If my message is longer。

I could simply use the block cpher twice。 we already saw this from last time This is called ECB mode。

 we use the same key。 we take the message we split it up into chunks passes through the block cipher multiple times take all the cipher text concatenate them together and we get our final cipher text So this works but it's notncCPA secure why is that because we talked about how they's still not randomness if you encrypt the same thing 10 times you get the same output 10 times we saw it with the penguin if you encrypt this penguin 10 times you get the same output 10 times if you use a block cipher that's deterministic penguin is still visible so we don't like that we got to fix it So let's fix it today So we've already seen that schemes that are deterministic。

 they don't work because if you encrypt the same thing twice you get the same output twice and by definition that fails the NCPA game the attacker wins that game the schemes not secure so let's fix it Here's what I'm going do I'm going to start introducing randomness into the scheme。

And so what I mean by that is I'm going to make it so that if you encrypt the same thing twice。

 the output looks different each time that's what I want， so let's try and make that happen。😡。

So here I go I'm going to take some random bits this initialization vector that's a fancy term for a bunch of random bits Okay so I'm gonna pick a bunch of random ones and zeros。

 I'll flip a bunch of coins， get a bunch of ones and zeros and here's what I'll decide to do I'm going to say this plain text instead of passing it directly through the blocks actually encryption because if I do that I'll get the same output every single time I am first going to x or it with this special initialization vector and then encrypt it and then the result and now it's going to be different Rv time so if I encrypt the same message twice and I'm going to pick a different set of random bits every single time X or it and then the result is my cybertex okay。

So that looks good I haven't proven to you that you can decrypt this or that this is secure yet。

 but at least I've done something so that when I encrypt the same thing twice I don't get the same output twice does it totally work well not quite we have to think about how the decryption works and all that but I've heard in some randomness so you know i've taken the first step。

Okay， so does this mean that if I encrypt the same thing 10 different times like if I encrypt the penguin or something。

 is the penguin going to be completely indistinguishable from random now， am I all set well？

Let me think about this。 Well， if I pass in you know some message。

 remember that the overall message is this entire thing and I'm splitting it up into chunks So yeah。

 even if I pass into the same message twice， this first chunk is going to be different because even if I pass in the same message a second time it's going to get Xort with a different piece of randomness and so this piece of Cyphertext will look different Okay that's great。

 but what about this one， this is also a part of my message's like the middle third of my message。

 what's happening over here， I'm taking the message I'm passing it straight through the block Cypher encryption it's the same message I' encrypt it get the same output So this part of the plain text。

 there's no randomness if I encrypt the same thing twice or if I encrypt a message twice that middle third it ends up looking the same and same thing over here at the end this last block when I encrypt it I still get the same Cyphertext so I introduce randomness but not to the whole thing so we need to do a little bit better let's add some more random。

Okay。So one thing I could do is I could say well maybe I'll throw in some more random values。

 that's one possibility， but I'm going to do something a little bit smarter so instead of saying you get a random value and you get a random value because now I have to come up with all these different random values that's a lot to keep track of。

 I'm going to notice something kind of clever which is this cipher textex from an attacker's perspective because this is message that I'm sending over the insecure channel。

From the attacker's perspective what does the cyberphertext look like to them it looks completely random to the attacker how do I know that because if the attacker doesn't know the key what do we know about block cphers block cyphers look like a random permutation so from the attacker's perspective this cybertext down here it might as well be a random ones and zeros for them okay so if this is as good as ones and zeros that are completely random for someone who doesn't know the key then instead of coming up with another initialization vector or another set of randomness I'm just going to say this thing down here from the attacker's perspective is basically random so let's just use that instead so there it is instead of passing in a new initialization vector here or instead of passing in the same one that I was already using I'm just going to take that cyberphertext which I know the attacker thinks is basically random looking it's unpredictable can't really tell what it means and I'll use that to introduce randomness into the second。

ば？Okay。Well that's nice， but still haven't solved the problem of my third block third block still looks the same if I encrypt something the third block still looks the same one after I encrypt it okay。

 so I solve that problem too I will repeat this over and over again and every single time I encrypt something before I encrypt it。

I will first exor it with some randomness and then pass that block into the block stack encryption and get some output。

ok。So all that I've done is I've decided my original scheme， it was deterministic， I didn't like it。

 I had to introduce randomness so this is what I came up I just came up with some way to stick some randomness into the scheme I haven't told you that it works yet but it looks like at least some way to introduce randomness okay so it turns out we invented something new that's great so we invented something called CBC mode stands for cipher block chaining and don't have to remember what it stands for but the chaining comes from the fact that I'm chaining all these blocks together and so that's nice so now let's think about we can think about a couple things so one of the things we can think about is what is the encryption equation remember even as we're drawing these pictures which are nice ultimately we can always write these as expressions like what is the encryption expression what is the decryption expression so let's do that so I guess I've already kind of spoiled it here but we can try to write this too so we could say well first of all my message is no longer。

Just one message I realized that I have to split the message up into a bunch of chunks that is what I see down here。

 so the first thing I have to do is I have to say my whole message it is not just one m it's like m1 and2 m3 sometimes people call it P1 p2 p3 that's what this slide says but the idea is you're taking your message and you're splitting it up into chunks that's the first thing we have to do and so i'm going to use subscripts to denote splitting the message up because I cannot encrypt the entire message in one block I encryption I had to divide it up so let's do it so I'll say。

Well， I want to encrypt， let's say， I want to encrypt。

He is a message so the first thing i'm going to do is i'm going to take that message and i'm going say this message it's really you know m1 concatenated with M2 concatenated with M3 and so on and all that I've done is I've taken the message I've split it up into chunks just like you see in the picture okay that's good and so now instead of writing the encryption as one single expression i'm going to write it in terms of those little chunks because I can look at the picture and know how those chunks work so I will say instead of encrypting oops I will say oops I will say instead of encrypting the entire m。

Let's think about how you encrypt。A specific block So let's say how do you encrypt and sub I Okay well let's see what happens So suppose this block is the I block of cipher text So what do I do with the I block of cipher text or the plain text sorry I take the plain text What do I do I exhor it with what well I exor it with the thing from the previous block what's the thing from the previous block thing from the previous block is C of I minus-1。

you think down here， I could also name C1， C2， C3。So I take my message I exhor it with the thing from the previous block and then what and then I shove it through the blocks sign for encryption so I'll write that as E sub K so now I have my encryption algorithm and the way that I got it is I looked at the picture I thought about what the picture is doing to my input and I wrote it out okay。

And what's the result， the result is the I block of Cyrontex， which is C subI。

 and then ultimately what do you do with all of your C subI， you mash them all together。Okay。

That's great so that's our encryption algorithm you see it there in kind of nicer type setting than my sloppy handwriting so that's great so that's how you encrypt you split it up you encrypt each one block by block but you add this like chaining idea so we add some randomness overall okay。

😊，That's great。 Now let's ask the question which is well。

 how do you decrypt stuff So how do I decrypt something if I give you a piece of citext。

 how do you decrypt Well again， we can look at the picture and we can try and use the picture to reason it out So there's kind of two ways to come up with your decryption algorithm One way is I can look at my picture and I can say okay this is c sub I and I want to know what m sub I is how would I do that I need to write an expression for m sub I so let me try that m sub I is equal to well I know I've got c sub I what do I do with c sub I Well the first thing I should do according to this picture I should run it backwards through the block cipher algorithm to decrypt it So let's give that a shot we'll say I will decrypt the citext I run it backwards and now I am like at this phase up here So now what well now I need to get rid of this X because I want to go all the way back to M sub I so I want to cancel out that x sort that I added in earlier so how do I do that Well after I dec。

😊，I need to cancel out the exO， what did I exort with， I exhorted with， oh， the previous I project。

So if I looked at the picture I could deduce that that's the decryption algorithm。

 that's one possible way to get it if you like pictures that's the method for you trace it backwards through the diagram and think about okay I have to run it backwards through the block cipher encryption so I'm decrypting then I have to get rid of that x source so I cancel it out where do I cancel out I cancel out the C of my minus1。

That's one possible way to do it Another possible way if you like algebra， big algebra fans。

 you could say wait I have an expression right here that relates M and C and this gave me C in terms of M。

 but if I want to decrypt what I really want is I want M sub I equals something some expression that tells me how to decrypt so maybe I'll just do some algebra to solve in terms of M so I can also take this expression and do some algebra。

Hopefully I havent on the slide so I don't have to draw it for you so we already saw the picture version which is what you see on this slide。

 I believe there's an algebra version Okay so there is we have this expression it relates M and C and I can just run a bunch of algebra steps to solve this thing for M that's another way to do it so valid operations are you can decrypt both sides that works And if you're not convinced that it works Think about the fact that it's byche and because it's a byche decrypting both sides will give you the same result okay。

😊，Once I decrept both sides， I realized that。If I encrypt something and I decrypt something what's the definition of a block cipher encryption and decryption they are inverses So if I encrypt something and decrypt something that goes away gives me the line over here okay but still not in terms of M I want something in terms of M because that tells me how to decrypt so I realize I want something in terms of M but there's this S key term right here that I want to get rid of so how do I get rid of it I exhort both size with c sub i minus1 now these cancel thanks to my handy canceling property of x source and then finally I get an expression in terms of M sub I it's the same expression from before so I'm also。

So how do you come up with decryption algorithms if you know how to encrypt you can either stare at the picture that was this slide。

 I stare at the picture and think about how do I run the picture backwards。

 you can even draw the decryption diagram like we did here。

 that's running the decryption or running the encryptption backwards， take the ciphertex。

 run it through decryption， run it through decryption and then Xor with the previous Cyphertex。

 you can draw it out or feel like algebra， you can write out the expressions and say I have something that's C in terms of M。

 I want something that's M in terms of C， I do a bunch of rearranging。

 these are all valid operations you can do and you come up with your decryption algorithm。

Okay before I take questions， one more thing I want to note。

 which is a pretty common piece of confusion when we see these for the first time is this initialization vector。

 this is something that was on this slide but I haven't called attention to yet it's part of the cipher text and at first you might be like wait wait why is that the case So there's a couple ways to think about this Well one way to think about it is suppose you just send the cipher text and you do not send the initialization vector。

Well then if you don't send the initialization vector if someone receives the cipher textex。

 how are they going to know how to decrypt it Well we can look at the decryption algorithm。

 but what you'll eventually notice is that if you don't have the randomness that the person introduced while they encrypted the message you're not going to be able to get the original message back so that's the intuitive way of thinking of it。

 we have to include the randomness oop we have to include the randomness as part of the ciphertex because whoever is decrypting they need to know what randomness I introduced in order to like get rid of the randomness and find the initial cipher text or sorry the initial plain text that's one way to think about it if I introduce randomness the other person has to be able to get rid of it。

Another way to convince yourself is to look at the decryption picture or the equation and you might see over here how do I arrive at the first block of plain text on the right we have the decryption diagram Well the way that I arrive at it and you can look at these two diagrams and convince yourself is I have to take the sign for textex。

 the first block of sign for textex I have to decrypt it and then I have to exhor it exhort it with what well when I encryptpt it I exhort with the initialization vector but when I decrypt I have to cancel that out and I have to extort again with the initialization vector to get the original plain text back。

So if you're someone decrypting， you need to know what this value is in order to get the original plain text back。

 if you don't， then you're kind of out of line， okay？So you can look at the equations。

 you can look at the picture， you can think about it and realize that if someone introduced randomness into the scheme。

 they need to also tell you what randomness they introduced so you can pull out the randomness and get the original message back Okay now I can take some questions yeah yeah diagrams。

If the initialency method is in present， we can still decrypt all the other blocks， right？Yeah。

 I we have a question， which is what happens if there's no initialization vector。

 it is true that you can still dery a lot of the other blocks。

 but the first block would not be decible。Other questions so。Yeah， that's a great question。

 which is if if you tell the attacker you're passing over the insecure channel that initialization vector。

 does that defeat the point of randomness， that's a great great question and to answer we're going to have to try and reason about the security of this thing。

 which is hopefully coming up in a slide two okay。😊。

So let's do it okay so I guess before we do that let's just make sure and convince ourselves that this is pretty fast so we already know that block ciphers they just do a lot of xoring bit shifting those are all really fast operations which is great and if we look at what else we have introduced into the scheme it's mostly XOs we introduced a bunch of exOs so not going to add too much extra time so we like that。

Another thing that's kind of nice is that while modern computers。

 they often don't just execute one thing at a time， they like to execute lots of things in parallel。

 so say I have a plain text that's like a thousand blocks long million blocks long。

 billion blocks long。Could I encrypt each part of the plain text in parallel because that would be nice。

 I could say processor one， you encrypt the first half and processor two get to work on the second half。

 and that could save me time too。 I want encryption to be fast。 I want people to use my algorithm。

 so I want to make them fast。So can I parallelze， Well， if I look at this。

 say I want to encrypt block three So I'm like processor number5 or whatever。

 please encrypt block three for me。 Well， processor5 is like okay。

 I'm going to start encrypting so I'm gonna to take my plain text I'm going to exhort it with what I'm gonna to exc it with cipher text I have to wait for whoever came before me to finish their block so that they can give me the cipher text I can plug it in and encrypt So can this thing be parallellyzed well。

 not really if I want to encrypt some block， I need to wait for whoever came before me to finish encrypting their block so I can take their cipher textex pull it over and then exor it with my plain text Okay so I can't parallelze encryption。

 which is too bad what about decryption So decryption。

 can I say hey you encrypt or you focus on decrypting this someone on this half of the room and then someone on this half of the room。

 please decrypt this can you each work on these things separately and then give me the result later Well let's look。

So let's pick an arbitrary block There it is What do I need to be able to decrypt Well I need the Cyphertex I have that The Cyphertext is the thing I'm trying to decrypt I have all the blocks of Cyphertext when I start decrypting that's okay I can pass through decryption I can do that myself That's okay and then I have to exhort it with something to get the plain text what do I have to exhort the Cyphert with to get my plain text back I look at the picture I trace it backwards and I need to exhort it with the previous Cyphertex do I have that well yeah I do I have all the Cyphertex available to me when I am beginning the decryption operation So if I need to decrypt something the only things I have to reference are different blocks of the Cypher textex in particular my own block and the block that came before them that's it and because all I have to reference the ciphertex I can do this without waiting for someone else to finish computing plain text because you can think of this as we split the job up everyone's busy computing some part of plain text but when we're doing the computationuts。

We only have to reference Cyphertext so we can all do this in parallel and then when we're done we can combine the plain text together。

 so CBC encryption we can't do that we have to wait for the previous block to finish encrypting to get the cipher text out but CBC decryption we can do in parallel because everybody only needs to know the cipher textex to compute decryption of a specific part of a message。

 so that's great。Okay。So we reason a little bit about efficiency in particular whether or not these things can be parallelzed and by parallelz we mean can you split the message up and have one person encrypt one part。

 one person encrypt the other part， so for encryption。

 no you can't you have to wait for person I to finish before person I+1 can work on block i+ one for decryption。

 yes you can parallelize okay。Now let's look at okay I guess we can't talk about security yet because I have to make sure this thing totally works first so one thing I'm gonna notice is well this works great if my messages are exactly a multiple of the block size so if my message is exactly one block long this works great if my message is exactly two blocks long works great I split it into two blocks I pass it through same thing if my message is three blocks long but what if my message was like two and a half blocks long let's give that a try I take my message which is like two and a half blocks long so if my one block is like 16 bytes。

 two blocks is 32 bytes， maybe mine is like 40 bytes or something not a multiple of 16 so I'll take my first block of message my first block of the message I will stick it right there perfect。

And I'm going to keep splitting， I'm going to take my second block， split it up， put it right there。

 perfect what's left， well I only have half a block left to go so I will take my remaining half block and put it right there。

Perfect。Or is it because now how do I encrypt this thing， Well， let's take a look。

 I can take this full block of plain text Xor with my full block IV。 that works great。

 I can encrypt that。 That's great。 same thing with the second block， but look over here。

 if I only have half a block how am I going to encrypt half a block worth with material with like the full block is cipher test。

 how does that work And even worse， even if you were to figure that out even if the result was like half a block long like what do you pass into block Cy encryption。

 Remember that block Cypher， it takes in exactly n bit whatever the block size is So if the block size is 16 bys。

 you must pass in 16 bys if you pass in anything less like8 or 9 or 10 the block Cypher will say no。

 I refuse to encrypt this I don't know how to do it。

 you need to pass in exactly a multiple is 16 bys So we have a problem here。😊。

Because if we only have a half block of message left at the end we don't know how to pass a half block of a message through a block sample encryption that's expecting a full block that's a problem so how do we fix it well it's not too bad one way to fix it is to say you know what I'm just going to add some extra characters at the end until my message is the right length so if my message only fills up two and a half blocks I will take my message and just add some padding bytes at the end they could really be anything and as soon as I add them now it has a longer message that is a multiple and because this is a multiple the block size it goes right into the block sample for encryption。

So my message is， you know， like。Two blocks plus another like eight bytes。

 I might have to add more bites of padding until I get a multiple of 16， and then I'm good to go。ok。

That's padding fancy way of saying adding those bytes at the end。

 they're not part of my message I don't actually care about communicating those bytes to the other person because what I really cared about was my two and a half blocks of real message so i'm not adding to my message i'm just adding bytes for the sole purpose of making sure that I can pass things through these encryption blocks okay。

😡，So that's padding and turns out padding is one of those things that's like easier said than done and you'll get a chance to explore this in homework 3。

 I believe， And so I'm not gonna talk about it too much。 you can play with it in homework。

 but it turns out if you think of maybe the first padding scheme that comes to your mind is maybe you know what。

 I'll just shove a bunch is zeros at the end turns out that doesn't exactly work same thing with padding with ones and so on。

 So you have to be a little bit careful I'm not going to talk through this entire slide。

 But you have to be a little bit careful with padding because whatever you pa the other person has to be able to remove that pa chop it off and get the original message back。

 And so if you add padding and it becomes ambiguous which parts of the message are padding that you added and which parts of the message were your true original message then you have a problem and you'll get a chance to explore this in homework 3 So I'm not gonna。

So spend too much time on it， but just know that padding， not every type of padding works。

 you have to be really careful and make sure that whatever you add as padding。

 you are able to get rid of it later when the other person decryptps the message， okay。喂以。Finally。

 I can talk about whether the scheme is secure or not。I will tell you。

 I will not prove to you so the proof requires making more assumptions and not something I have time for right now。

 but I will tell you that this thing is secure， but you have to make certain assumptions。

 you have to use it correctly so。What's the assumption Well the assumption is that IV that I claim to be random it better be random in order for this NCPA security to hold that's one of the requirements for NCPA security to hold on this and so how do we know that well let's think about what happens if you use the same IV twice well if you use the same IV over and over again or say something even worse instead of using the IV you just say IV equals five and you just plug in five over and over again then what are you back to you're back to your deterministic schemes and we've already said schemes that are deterministic they're not secure okay so we already know that in order for this scheme to be secure whoever is using it had better remember to change the IV up every single time they encrypt the brand new message because if they encrypt two messages with the same IV then I'm back to deterministic if the message are the same then the outputs the same I'm back to the penguin problem or the penguin is clearly visible okay。

The problem so make sure you use different IVs every single time and intuitively although we don't really have the tools in this class with the time to prove it in great detail right the security proof roughly says and again this is not an actual proof it's like more of a sketch maybe even less of a sketch it roughly says okay well we already know that the block cipher outputs are all indistinguishable from random so that's kind of the property or the building block that I'm using to make this whole scheme secure so again we don't really have the tools to prove it it's certainly not in like an 80 minute lecture but the rough idea is that all of these outputs。

From the attacker's perspective， their outputs of the block cipher and we already know that outputs of the block cipher are as good as random Someone who doesn't know the input of the block cipher and doesn't know the key has no way of knowing what the output of the block cipher is or even someone who doesn't know the key from their perspective this might as well just be total randomness so yeah we don't really have the tools to prove it but that's kind of the sketch is that all these outputs that are falling out of the block cipher they are indistinguishable from random and the question of if you know the randomness does that break security Well we can give it a try so say you're the attacker you don't know K because you're the attacker but you do know the initialization vector this randomness is public it has to be a public so the person decrypting can get rid of the randomness and go back to the original message so if you know this well what can you really do with it and it's not immediately clear you can play around with it think about different strategies but it turns out that even knowing this it doesn't help you。

Predict what happens down here if you don't know the key you have no way of knowing what the blocky or output is it's as good as random to you so knowing the random initialization vector it doesn't give you any clues as to what the cyberphertext output is same thing over here just because you know that you're plugging in some known cyber per text doesn't help you at all with what this output is it's basically indistinguishable for random。

Okay to do this formally， you would have to go through and consider like all of the strategies that a tagger can use。

 but we don't really have tools to do that， okay。Questions yeah。

Why I be honest time but why does it need to be random unique Yeah there's a question of is there a difference here between random and unique there is a question in I believe discussion I will talk about this so is it enough for this initialization vector to be just unique or changing every single time I think discussion will talk more about it there is an attack it's pretty subtle so we're not going to talk about it here but in discussion youll get to see an attack where the initialization vector is predictable and not actually causes problemss a question though okay but if we're paranoid we know that if it's completely random and unpredictable every single time things will be okay。

Okay。So that's the rough security sketch。 let's talk a little bit more about what happens if you do reuse the IV so we already know that if you use this thing improperly if someone gives you the tool and you don't use it correctly well we already know that it's not going to hold against our NCPA definition which means that's going to leak information we already know that if you encrypt the same message twice you're gonna to get the same output twice so that's already going to leak information and the attacker could be like oh this thing that you sent today it's the same thing as what you sent last Tuesday that's not good that's leaking information so we don't like it but it turns out even if you don't send the same message things could still go wrong and so this slide with all of its fancy colors is showing you that even if you don't send the same message IV reuse can still leak information about your message so let's consider two messages and this is also a nice sense to remind you that having multiple messages it's not the same as a message being split into blocks so I can actually have two messages which is what。

Have on this slide and each message can be multiple blocks long and I'll split them into blocks okay so this is the first message it's split into three blocks。

 This is the second message it's split into three blocks so just so you're aware having multiple messages is not the same thing as having one message thats split into blocks wanted to get that out there sometimes it trips you okay we have two messages and if we look at these messages it turns out these messages they are different they're not identical but they're similar and what I mean by similar is it seems like they start with the same bites or the same bits in particular the first two blocks are identical So maybe this one says like dear Bob hello and this one says like dear Bob hi something like that sorry that wasn't super creative but maybe the first two blocks are the same and then things start to change in the third block So if I take these two messages and I accidentally or mistakenly use the same IV what happens when I encrypt the two messages。

So let's give it a shot i'm going to encrypt the first message on the left and the second message on the right and I will look at those side by side and see how things are the same and see how things change so here we go。

The first block of plain text is the same on both sides。

 it's the word deer or something I don't know， okay。

The initialization vector is also the same because we've claimed that we are mistakenly using the same one twice okay。

 if I take two inputs that are the same and I exporthor them。

What's the result is the same thing so the thing that i'm passing into this block cipher encryption same okay the key i'm using is the same why is the key i'm using the same because remember what was the whole point of this lecture the whole point is I don't want to do the one time pad thing where I have to change keys every time so we are generally going to use same key to encrypt multiple messages。

So what's going into the block Cypher encryption block， the same input。

 same X input and the same key and what do we know about block Cypher encryption deterministic if you pass in the same things twice。

 you get the same output so this Cyphert block between these two encryptions same right this one equals this one okay。

Sing。Let's keep going and see if right this gets worse well what do I do next I do this extra operation next so I take this plain text。

Same， I take the previous eyephertext on both sides。Same thing， I ex sortt， by ex sort。

 same things twice， what do I get？Same thing here same thing with the blocks after for encryption I know I'm saying the word same a lot but if I take the same input of the block snap for encryption I encrypt twice it's the deterministic I get same output again so it seems like so far IV reuse has already leaked that my two messages start with the same thing so if this were like I don't think those thing was invented and you know World War I or whatever but if you're like in the know minefields or whatever and there are two messages that start with the same two words okay well now the encryption starts with the same two words and whoever's looking at your messages are spying on them they can see that your two messages even if they don't know what they say they must start with the same two words you have leaked information or the same two blocks okay。

And so we keep going， okay， well this time finally something interesting happens and more interesting which is that these two inputs are different and if these two inputs are different。

 well we actually remember the same thing， but this input is still different from this one。

So if these two are different， what happens if you take two different inputs and shove them through the block cycle？

😡，If I take two different inputs and shove them to the block cipher the output is unpredictable remember that's the point of the block cipher the arrows could be anywhere so if I take two different inputs and I shove them into my block cipher then I get the case that this one and this one sorry for super messy okay I'll try to clean it up so we know that this one and this one they are equal because I pass them the same things every calculation that I did was identical between two encryptions same thing over here these two are completely equal however。

Once I get to this third block because the blocks that I'm passing in are different。

 it is now the case that once I pass those different blocks through the block cipher。

 the result of these two is like unpredictably different。Okay。

And so what does that mean for any future blocks， well。

 that means that if I pass this into a future block。😡。

And that future block is going to have unpredictably different inputs past those two blocks I first unpredictably different output so all of this reasoning told us that if you reuse the IV you end up leaking when two messages start with the same blocks so if two messages start with all the same blocks。

 the CVC algorithm does the same thing for all the same blocks all the way up until the first time something is different and as soon as something is different for the rest of time the output' is going to look different。

Because as soon as there's one difference， I am now passing in different stuff to the next box hack encryption。

 that output will be different， pass that to the next one output will be different。

Oh there's the phone， should I pick it up，'s not。嗯。It's okay。

 don't worry about it Okay so that's Ivy reuse。If it's an interesting phone。

 you have to come back and tell us who it is。So what we saw is that CBC mode is in CP secure if you use it correctly。

How does it work we split things up we choose a random idea with compute and again we haven't really talked about why is N CPA secure but we know that if an attacker can break this or I guess the rough proof I guess I will briefly sketch it out just in case you're curious it's not something we're gonna test you on necessarily so if you're getting bored you don't have to totally pay attention to this but it turns out that insecurity I'll just note that a lot of proofs are what we call reduction proofs and so what a reduction proof is the reduction proof says if I can break a then I can break B so。

This is gonna get a little bit into CS70 stuff so again if you're not a huge CS70 fan sure to ignore this okay so if I can break Sche A then I can break Sche B this is something that we've tried to prove a lot in security proofs and the reason I want to prove this is because think way back to CS70 you like dig up in the cobwebs of your brain you might remember that in CS70 there's this fancy thing called contrapositive which means that if I flip this and I invert the clauses that statement almost also and if that doesn't sound familiar don't worry about it it doesn't even sound that familiar to me to be honest but。

Basically， if you take this statement and you flip it around and you invert each of the terms。

 you end up getting this， so this implies this and vice versa。

 so one thing you could prove is I will now plug in actual things for DNA。

So that was just a CS70 review thing and ultimately we'll test you one in detail。

 but it's the sketch proofs if you ever go out in the real way and do these proofs。

 this is what you will see Okay so if I break if I break CBC I'm just plugging in values for A and B here sorry A secure CBC secure okay so I just plugged in things for A and B here okay so I can prove the security of CBC in two different ways I can prove it in the forward direction like this that would be like a direct proof I would say I'm going to assume that the blockypher is secure because it's spend 20 years no one's broken it and here by secure I mean that blockypher definition of security indistinguishable from random。

That's AES being secure so I could say if AES is secure。

 then I follow these steps and that shows me that CBC is secure inP is secure okay that's one way you can prove it。

 but turns out these direct proofs they're kind of hard to come up with it's not immediately obvious how you go from this thing being secure to this thing being secure and maybe if you weren't really convinced by my argument of like oh well hey the attacker can't really tell this apart from random and then they can't tell this apart then you'd be right。

 that's not really exactly how people prove these things the way that people prove this is they realize this line at the bottom that's kind of hard to prove So instead they choose to use this contrapositive which is the exact same statement and logic but it's a lot easier to prove because now you're thinking like an attack and we like that and so now you say suppose theres an attacker out there with the magic power to break CBC I haven't told you how they're going to do it but suppose that you know the like gods of security descend and they give eve the magic power to break CBC。

And so what we show is that Eve with the magic power to break CBC now has the power to also break AES using that magic power how do they get the power not our problem this statement just says if Eve has the magic power to break CBC then she also has the power to break AES and if we can prove that that statement is true then we have also proven that this bottom statement is true and that tells us that CBC is secure so this is called a reduction proof is not something we're going to talk about in any detail in this class。

 but if you ever go into 261 which is the graduate security class or any like cryptography class。

 this is something we'll be doing a lot of the way that we like to prove things is not directly by saying if A is secure then B is secure。

 we like thinking like an attacker and we like saying if someone has the magic power to break CBC they can use that power to also break AES once I have that statement I flip it around using my CS70 logic and I get the forward direction I was looking for okay。

Just wanted to put it out there you were ever curious。

 but not something we both test in any sort of detail， okay。Cool。

 that's CPC mode and finally I can show you the penguin which now looks totally indistinguishable so looks like we did our job。

Any other questions about CBC before we see our second？

Walksside for Chaning mode of the day yeah I remember。

When one caddy it's not really effective because you need to generate teams order to define a what wing。

ThisC yeah that's a great question so the question was we already saw that one time pads are not practical because you have to come up with a different IV every single time so what makes CBC mode so practical if I have to come up with a different IV every single time that's a great question and i'm glad you brought it up so remember there's a couple things that were really bad about having to generate random keys one of them was that remember that if I have an end bit message my message is like a million bits long I have to generate a million bits of key in order to exhort every bit in the one- time pad scheme but in this case if my plain text is like1 million bits long it goes on and on and on forever。

How many bits of IV do I have to generate just one block So no matter how long my messages。

 I only have to generate this limited number of randomness and then things through this chaining property。

 I can use the chaining property to drive more random basically so that's one nice thing is that instead of having to generate a million blocks of IV or a million blocks of random key for a million block message I can just generate a single block and then use this chaining property to propagate that randomness through the whole message So that saves me on randomness computation the other thing that makes cC better than onetime pad is that this initialization vector is public we don't care if the attacker knows it it doesn't affect our security and in fact we're okay with it being sent in public because that's how Bob the recipient's going to undo the randomness and get the original message back So in one time pad when you generate that secret key。

 you also have to figure out how to secretly share it between Aliceice and Bob which is really tricky whereas in this case when Aliceice generates the IV she can just toss it over to Bob。

Even if Eve sees it， doesn't matter for our purposes。被告して。Okay。

 anything else you want to know about CBC before I'm done with it forever rental next semester？

Okay let's look at our second one， so again we will try to design it together and this time instead of starting with block ciphers and working with lo Cyphers trying to introduce randomness this time I'm gonna go back to the onetime pad so I'm going remember that onetime pad it was actually not so bad as long as I didn't reuse the key so one time pad we saw we all these nice security properties so like I really want to use one time pad I really want to redesign it or give it a little change so that I can actually use it what was the key problem the key problem was that I can't reuse the key okay sorry for saying key so many times so this is our onetime pad we've already seen it and so I can't reuse the key so like what do I do well I really wish that if my message were longer I don't have to generate more keys or if I want to encrypt the same thing over and over again。

I don't want to have to generate more keys So where am I gonna to get keys from I don't want to generate them myself because if I generate keys myself。

 I have to share them with Bob over a secure channel。

 I don't know how to do that that's complicated that's expensive So I don't want to generate keys myself So instead of me generating random keys I'm going go look for something that is usable as a onetime pad key What are the properties of a onetime pad key。

 it just has to be a bunch of random ones and zeros So let me go looking for a cheaper way to generate random ones and zeros Well what do we know we have block ciphers to the rescue So remember if the attacker doesn't know the block cipher key what does this output look like to the attacker random the attacker from their perspective this is just a bunch of random ones and zeros with no meaning to be attacker So I'm going to decide you know what I like one time pads but onetime pads had that problem where key I don't know where to get them I don't know how to generate them or where do they come from。

But then I remember， well hey， these block cpherpers。

 these are kind of nice because this output is completely random to the attacker's perspective so what if I combine these two ideas and I'm like instead of getting those keys from who knows where I'm going to try to use block ciphers to come up with a lot of different keys so that way instead of generating keys myself and trying to share them between Alice and Bob。

 I'm going to harness the power of block ciphers and that indistinguishability from random property that we saw earlier。

 I'm going to harness that power to try and generate a lot of keys for cheap and if I can generate a lot of keys for cheap maybe that onetime path that was so impractical maybe it's going to be more practical。

Let's try it。So we already know that anytime you take something and encrypted through the block cipher。

 it basically looks random， whatever you take if the attacker doesn't know the key。

 whatever this input is， we're going to go through that big table of arrow mappings is going to map to who knows where and we're going to get some random looking output so from the attacker's perspective。

 this is as good as random。And so is this and so is this anytime I take anything and pass it through a block cipher I get something that's as good as random the attacker has no clue what any of this is as far as they know it might as well be someone tossing a bunch of coins and getting zeros and ones Okay so now that I look at this I'm like wait well if I have all this stuff that's random。

Maybe that's my one time pad key， so maybe instead of coming up with a key myself。

 which is super expensive， I'm going to use the block stack for encryptions power to give me all this random looking junk that I could use as a key。

😡，So I'm gonna to do it I'm going say all that stuff that came out of a block cipher is as good as random so I'm going to use that as my one- time pad key I'm going to exor it bit by bit with my plain text and I'm going to get the cpress like output so all that idea to go from the previous slide this slide I'm just observing that hey block ciphers。

 their outputs are basically random for the attacker and then I'm going to observe that if those things are random they can be the input to my onetime pad or they can be the key to my onetime pad so I've taken the block cipher I've taken the one time pad I've like done a mash up and now I get this okay we are almost done because。

If I go all the way back here。I never actually maybe even hear like I never specify what these inputs are right so what do these inputs actually represent or what are they turns out they could really be anything right as long as I pass in something and I encrypt it with a key that the attacker doesn't know this output is as good as random so I just need to put something up there what am I going put I don't know why don't I just put how about I encrypt zero then one and then two that works right because these could be anything。

As long as I put in something here and I pass into the block sign for encryption。

 it's as good as randomly the attacker so I can just pass in01 to like whatever I feel like and from the attacker's perspective as good as random。

 so let's do that。Okay。So I could just pass in01 and2 and so on。

 but there's still one key missing piece to the whole puzzle which is I stare at this scheme really hard。

 still deterministic， I encrypt the same thing twice I never actually introduce random is anywhere so the last thing I have to do to complete my theme is to introduce randomness in the way that I'm going to do it is instead of just saying012 so on as the things that I've encrypting to generate a bunch of keys。

 I'm going to encrypt some random number plus zero some random number plus one some random number plus two and so forth and if I encrypt those things I still get random looking junk and that random looking junk can be my key。

Okay， so that was me introducing randomness and finally we now have something that is a one time pad。

 but instead of the keys being generated each time and we have to share the keys each time。

 maybe now we can generate the keys for cheap。So let's take a look at what that looks like， okay。

So this introduces something totally new， it's still a block stapher chaining mode but this time it's not CBC this time it's called counter so I guess a couple of things I will know the first thing I will notice that you might have noticed that the IV got like a rebranding on this slide we called it IV previously now it's called NoS and so as's a terminology thing for the purposes of this class they basically mean the same thing in real life there are some slightly different properties of each I think the main properties is that IVs are unpredictable and nonsenses can be predictable but for the purposes of this class they're basically the same。

I will also note that I think nonstand for number used once， not totally sure。

 but that's a very funky acronym if it even is one。 I don't know。

 people come up with flame names Anyway， that's counterm。

 Now let's think about what do we do that actually makes this a more practical version of the one time pad So how do you encrypt。

 Well， we do the same thing as always， take the message we split it up that's what we always do right into blocks。

 But then I mean， maybe you don't have to do that。 But like， okay， let's say let's say's sorry。

 let's say we split it up Okay we split it up and。Then we're going to do the one time pad thing on it so how do we do that well in regular one time pad Alice and Bob have to come up with that long key and share it with each other and make it secure I don't like that that's too much work So instead they're going to do this Alice is going to send。

Al was gonna to pick a nos random number and then she's gonna say nons plus zero use her one and only key this time we're not going to use a bunch of different keys because we know that's wasteful so we're going to say Alice picks a nos she computes Nos plus zero a takes her one and only key encrypts Nos plus zero gets some random junk that random jump that's part of the one time pad key。

what's next if I need more， maybe my message is even longer than one block then I will continue I'll take that no。

 I will stick a one at the end or add a one to it， I'll use my same key。

 the same one and only key that Alice and Bob share I will encrypt with my one and only key and still if the attacker doesn't know that one and only key this output still total random garbage through the attacker still usable as one time pad input we like that and then we keep going if we need more we say counter plus st we use our one and only key we send it to the block sipher and get more pad so in effect what we've done is we've taken a single key just one Alice and Bob only have to share one key for all time。

And by using this and shoving this nons plus counters through the block cipher。

 we've basically given ourselves like infinitely usable key material for use for the onetime pad。

 so this is just us generating lots and lots and lots of onetime pad input as much as we want right we can make this counter go as far up as we need to get as much input as we want。

And then after we're done encrypting all that stuff。

 then we take our resulting pad for the one time pad or the resulting one time pad key。

 which is all this stuff that came out of the blocks after we exhor it bit by bit with the plain text and we finally get the site text okay。

And what if you want to encrypt another message， do you have to come up with a new key， nope。

 all you have to do is come up with a different knots。

 shove it through the box after your encryption， get a completely different output that only Alice and Bob know。

 that's great。So we've taken the block Cy and used it。To allow us to encrypt a bunch of。

There encrypted nouns with a bunch of random counters or encrypts a bunch of random nonsenseuns with increasing counters。

 get a bunch of completely unpredictable output， use it as a one time pad， but okay。

Nows the question how do you decrypt well remember this thing is one time pad inspired so I'm going to take inspiration from one time pads and try to decrypt this onetime pad style well how do you decrypt things in one time pad you take the cipher text and you exit with the pad again and you get the original message back so that means that if someone wants to decrypt they have to regenerate the same pad and then Xa with the cipher textex get the original plain text back。

So Bob receives the cipher text Bob needs to know how to decrypt so how does Bob do that Bob first has to regenerate the pad how does Bob regenerate that pad the key that I used for onetime pad well Bob is going have to take the nos which means Bobs gonna have to know the nos so we have to send the nos over to Bob so we send the nos over to Bob Bob takes the nos and follows the exact same process that Alice did to get the pad out so how did Aliceice generate the pad Alice said Nos plus zero shove it to the block cipher Nos plus one shove it to the block cipher Nos plus two shove it to the block cipher all of this using my one and only key to the block cipher so what's Bob going to do the exact same thing to generate the pad。

And so that's what Bob does up here like look at these two before after saying right like this entire top of the diagram never changed because this entire top of the diagram。

 all of this is just Bob regenerating the pad for the one time pad and then what does Bob do after regenerating the one time pad we take the ciphert Xora with the pad that came out and then plain text pops out。

Okay。Now stare at this really hard because something isnt bold。

 you notice that wait when I encrypt it I use the block cipher in the forward direction。

 the encryption direction， when Bob was decrypting he also uses the block cipher in the forward encryption direction so this is also something that trips people up is like wait how can it be that the decryption algorithm is using the block cipher in the encryption forward direction？

And the reason why we're doing that is because what was the purpose of the block saer in this whole scheme。

 it was just being used to shuffle bits。With the key and get a bunch of random output for use with a one time pad。

So we're not using this blocks after to actually encrypt the messages like look the message never even shows up in the block afterers we're just putting a bunch of random stuff in trying to get a bunch of random unpredictable stuff out。

 use it as a one- time pack so regardless of whether you are encrypting or you are decrypting for a CTR mode or counter mode you're always running blocksaf in the forward direction that's what this slide says。

Okay。So overall it is just one time pad， but instead of feeding in completely random keys。

 we're just going to use a single key and harness the power of nos。

 harness the power of these block ci or encryption blocks to get a bunch of unpredictable looking pads。

 okay， excellent。That's decryption we already saw it you can also write these as expressions i'm not going to do it right now because I think the pictures actually are a little bit more helpful here。

 but if you write it as expressions you will also notice that in both the encryptption and the decryption you don't actually have to use the block for decryption okay。

So now we're going go through and ask the same questions as we always do just to make sure it' the same secure does it work is it fast let's go through and think about all those things and make sure that everything checks out so first question is well can we parallelize and again parallellyzing is nice we like to split up the work so that we can do things in parallel we like encryption to be fast so let's think can I take a message and say you encrypt the first half you encrypt the second half and then we put it all together at the end well what does someone need to know to encrypt some part of the message well they just have to know the nos which we know at the beginning of encryption and they have to know all the counters we know those。

And then we just shoved those 3D encryption and we encrypt every bit one by one。Okay。

 that works out And so turns out there's no like dependence here remember in CVC mode。

 the thing that broke parallelization is the fact that we had to wait for the person before us to finish computing Cyphertext so we could take their output and chain it into our input but in this case we don't have to wait for any of the output all that we need to compute the output is just the nons which we already have and the plain text which we already have so the answer is yes。

 I guess we didn't even bother explaining it but I just didn't okay so the answer is yes。

 because every block basically kind of works in independence。

 there's no dependence on previous blocks we don't have to wait for anybody else to compute something and give it to us we have all the tools we need to make the computation right now so we can parallelze we need the nos we have that we need the countervalue we have both we need the plain text we have。

And decryption kind of the same thing， we have the nos， we have the counter and we have the Cytex。

 so we have everything we need to decrypt， we do not have to wait for someone else to give us something in order to decrypt the message。

That's all that this slide says。Let's think about padding just like before。

 what happens if someone has a message that's like two and a half blocks long well let's give it a try so well。

Let's try it so what happens if I have two and a half blocks well I have a full block here we know how to do with full blocks full blocks are easy we take the nos we shove it through blocks Cyphers the blocks Cy app is exactly one block of data and we do the Xor and we're set on block number one same thing with block number two we run the nos on the counter through the encryption get a full block of random garbage padding bys take those random garbage padding bys x them with our plane text get a full block of Cypher text things are looking pretty good support and now we come to the place where there's half a block of plain text。

So what do we do well， we can still take the nos on the counter。

 we can still shove it through the blocks after encryption and what do we get on this side？

So I will maybe even draw this。More I'll draw this a bit larger just so you can see it so what comes out of the encryption block over here。

N bits of output， why is that because block spherers are fixed size， they give you exactly end bits。

 no more no less okay。What do I want to x the end bits with。

 I want to x the end bits with my plain text， but my plain text is not that long。

 maybe it's like n over two bits or something。Right that's my plain test it's not as long because I have two and a half blocks this last block is a bit shorter so on first glance you might be like oh oh。

 how do I bitwise x or n over two bits with n bits seems like I can't。

But there is one thing you can do， which is you can say out of these end bits of padding。

 remember what are these end bits， these are like random ones and zeros that you can use as a one time pad。

 you could just say you know what。Those end bits I don't need all of them I just need the first end over two and the rest of them I'm just gonna throw away I don't need them because what am I doing I'm doing one time pad and for one time pad all I have to do is take every bit of plain text and Xera with a random bit of the pad so I'm going say this M bits I don't need all these end bits I'm going to just say just give me the first n over two bits here okay it's a funny two。

Just give me the first n over two bits， I will ex those with P and I'll get n over two bits of output right here。

So I'll throw away the stuff I don't need that works perfectly So when I'm encrypting stuff if I get too much output because my input is not a multiple of the block size。

 I'll just throw away what I don't need， I know with one time pads every bit is expt independently so if I get stuff I don't need forget it right don't need it that's one way to reason through this another way to see that padding wasn't needed for encryption is to note that this plain text which is like a half block long that's my problem block I don't like this half block because it's hard to deal with but I'm never passing the half block through the block cipher in CVC where did the problem come up the problem came up when I took my half block and tried to shove half a block of data through the block cipher it would not accept it but in this case if I look at this diagram this half block it never goes through the block cipher it's on the other side I'm only doing ext operations on it so I can just throw away the bits I don't need from the block cipher output and I'm all set。

Okay。That was this line and you might have a question which is well wait what happens to the person trying to decrypt well now the person trying to decrypt they get two and a half blocks of Cyphert they get my full block here full block here just like before and then they get a half block here so what does Bob do when Bob gets a half block of Cyphert well same thing Bob takes a nos and Bob takes the counter for this particular block shoves it through the encryption scheme with some key we've already seen all this stuff and what does Bob get on this side Bob gets and bits of pad okay what does Bob need to x this with what have I Alice provided to Bob I provided。

And over two bits over here， so what does Bob do？Bob does the same thing Bob says。

 well Alice gave me n over two bits and I have n bits of padding here so what's Bob going to do Bob's going to do the same thing throw away whatever he doesn't need keep the first n over two so Bob's like I don't need all N of this stuff I'm just going use the first n over two bits。

Okay， and then I will take the first then over to Exora with whatever Aliceice gave to me。

 get my output。So mo's encryptption works straight2。

 so the way that we deal with padding on one time pad or sorry。

 the way that we deal with padding in CTR mode is we don't all we have to do is throw away the parts of the pad that we don't need and Alice and Bob can both do that。

Okay， that's Pattting。So we don't need to actually add a bunch of extra bytes after our message to make sure it's the proper length。

CTR mode works with any language which is kind of nice。Finally。

 we deal with security and again there is a reduction proof somewhere in there where you can say， oh。

 if I break CTR I break this other thing， we're not going to do it and we will just roughly say right we've already kind of felt that this thing is basically one time pad because all of this block fipher is unpredictable that's kind of how I like feel intuitively that CTR mode is secure even if we're not going to go through a whole proof of it but again there is one key assumption you have to make and the key assumption you have to make or else is that that knots that better be randomly generated and not reused because what happens if you reuse the knots bad things happen there is also one tiny little ni which is that you can't so much stuff that it counter like rules back to zero but in practice that doesn't really happen so。

That's what that bullet point says， okay。So what happens if you reuse the nuuns。

 we can do the same we can do the same analysis as we did for CBC mode and think well what happens if you take two messages and encrypt them with the same nuuns if the two messages are identical we already know that the output's going to be totally identical is deterministic。

 no randomness， but what if my two messages are different in are reuse the nuuns well I could go through the whole analysis。

 but I could also just remind myself that what is the nouns do in the picture？The nos。

 all that it does is it tells me the output of the one time pad that I'm using the thing that I'm exoring with the plane text of the Cytex that is the output of the block cypherpress that's what the nos is forth so if I reuse the knots same nos both times and I guess these are know encryption and decryption but if I reuse the nos then this output's gonna to be the same every single time right and if I use the same block cpher outputs every single time and I xora with different plane text what am I really doing I am reusing the key to the one time pad that's what I'm doing because the nos it's determining what my one- time pad key is and if I reuse the knots I get the same one time pad every single time Xora with different plane text I'm basically doing two time pad as we saw from last time and we already saw from last time what happens if you use a one time pad it's really bad because now people know a lot of things they know like once' the Xoric or two messages。

You leak all sorts of information。So if you reuse the Nos in a one time pad things go really wrong in fact I would argue they go more wrong than in CVC mode in CVC mode people find out if you have the first couple blocks the same in CTR mode they find out way more they find out exactly what the Xer of your two messages are that's kind of bad okay and in practice usually knowing the Xer between two messages can actually give you the whole plain text so CTR mode if you reuse the one time pad pretty catastrophic okay。

And we already saw the penguin again totally random good for us that's assuming we don't reuse the IV So just to hammer it home and like finally follow up on this infamous life and last time。

 what was the mistake that they made you ask So they were using some Python library to encrypt stuff and they had to call the CTR function So somewhere in Python there was like a library called crypto or something and they were like crypto dot CTR encryption or something and for some reason that CTR library asked you to pick an IV for them So you all being you know good1 61 students that you are what are you going to do they're gonna to pass in a different IV every single time however。

 I guess these 61a folks they didn't think of that And so they just didn't specify the IV left it blank and so what did the Python library to do。

I guess they assume maybe that you know the random IV will be added for them or maybe they just saw the argument that said like IV or not they were like the hell is this I'll even blank。

 I don't know， but for some reason they didn't that they didn't specify an IV and for some reason the crypto library decides if the user doesn't give me an IV I will pick0 I don't know if that's what crypto library should do but that's what the Python one does apparently and so they ended up using the same IV to encrypt multiple exam questions and ends up being like reusing a one time pen so a student gets to know what the X or of two questions is and it turns out in real life it's not that hard to pull that apart and figure out what the questions themselves are So now you know what they did in terms of what mistakes they made'd say as 161 students like they probably shouldn't know what IVs worse that's their first mistake but I would also say like as a Python library。

 it's kind of weird to me that the library just to pulse to zero so I guess it' a matter of what you think but ultimately you don't be a slide in our lectures。

And make sure to use different Is， okay？Great and as we said from before by like don't build your own crypto if you do even a little tiny mistake like forgetting to specify about IVs destroy your system so yes okay so you don't know how to do it I don't know how to do it unless your name is like David Wagner too fish genius you probably don't have the skills to do it okay and that's okay that's not a bad thing crypto is tricky okay。

Great so we already talked about IVs and nonsenses right we already said that they basically are the same thing in real life the terms mean something slightly different but for the purposes of this class。

 we will just say nons or IV interchangeably it's okay for us and we already said that in some schemes reusing IVs is kind of bad like CVC in some schemes reusing IV is really bad like CTR so depends on your scheme you can reason through what happens if you mess up in some schemes messing up is kind of bad and some schemes messing up is really bad in general though the way to not mess up is to pick something totally random totally unpredictable for IVs and nonsenses and you're all set okay。

And so another problem is well maybe you kind of felt this like thinking through this stuff was not easy we' talked it through together but like having to think through what happens if you reuse the IV that was not really easy。

 we have to think okay well this output's the same and then this output's the same and if I do this I get like a one- time pad reuse that wasn't the easiest thing in the world to do and like I don't know about you but I didn't find that the most fun thing in the world to do either and so in real life you basically have two options you can be the 61 ATAs who had to sit down and think really hard about wait a minute when I reuse my IV now I have a twotime pad and now people can reuse people know the Xer of my exam and if someone knows the Xer of the two exam questions can they figure out the exam you can be like them and think about that really hard or one option is you can just use different IVs and if you use different IVs you never have to think about this。

So I like that solution， it's up to you， you can either think really hard about what happens if you reuse IVs or you can simply not reuse them and not think about this。

 okay？On exams you will probably have to think about this， but once you're done with this class。

 go with solution B， right use different IVs， don't have to think about it， okay。Great， and so。

You know both of these schemes they work， they have nice security properties and so you know which one do you like better well it's a matter of opinion we don't have a favorite。

 maybe you have a favorite， maybe when you go out in the real world you have a favorite and so there's different tradeoffs depending on what you value and so what we say on this slide which is a matter of opinion it doesn't have to be what you say is well if you really need to encrypt stuff fast you're like I have a mountain of data that I must encrypt instantly then maybe CTR mode is what you're going for because CTR mode has that nice property where everything is parallelzable so maybe you like CTR because you really want to parallelze stuff and encrypt stuff fast。

Maybe you're someone who's really paranoid about security you're like。

What if I everuse the IV or what if i'm handing this mode of operation to someone who really doesn't know what they're doing and I really want to make sure that even if they mess up my scheme doesn't break then maybe you're a fan of CBC because we already saw CBC leaks less information if you mess up so which one do you like better it's kind of a matter of what you prioritize what application you're using it for but both of them they work they're both used a lot in practice so which one you like better is a matter of opinion that's what this slide says okay。

😡，Great， but again， do be careful with both of these because again。

 if you reuse IVs like this happens in real life， 61A had it。

 other systems in the real world have happened before， so not good news， okay。

There are also other modes so these are not the only two out there there are lots of others。

 some of them are provably secure some of them aren't so here's a bunch of other ones and for all of them you can ask yourself these questions so you know if you're really bored and you want to go analyze these tradeoffs you can do that all of them have the same properties of is this padding necessary if I mess up and I reuse IVs how bad is it is encryption parallelzable is decryion parallelzable these are all things you can ask yourself it's nice practice for exams and so forth so I'm not gonna to talk about these now but you'll get a chance to practice these in like homeworks if you ever go to like pass exams we have lots of schemes that we make up so know these are all schemes that exist out there and you can see they're all kind of modeled off the same idea which is I have these block ciphers and I'm going to use the block ciphers over and over to encrypt longer messages with the same key okay so you can analyze the tradeoffs I won't right now but if you're curious we can talk about it again in homeworks you'll see them there's the solutions if you're ever curious okay。

There are more schemes that you will see basically。

 so these are the two that we are going to talk about， but just know that there are more out there。

 okay。In the last seven minutes， I want to remind you that I know this is like， you know。

Like days ago at this point， but maybe you remember that when we started this lecture long， long。

 long time ago， remember how we were in this square is like slide number one。

Because we are in this square for the last week we have only been thinking about confidentiality so all the things we've been thinking about the ultimate goal was to stop Eve from reading our messages that was all we cared about and for all of this time we were not actually worried about and it was intentional that we were not thinking about other things like can other people mess with my messages without being detected So the last thing that I want to show you and werenn you about is that even though we just went through all this trouble to build a scheme that is fully confidential that only satisfied the confidentiality security definition that we talked about we've not talked about integrity or authenticity and it turns out that this scheme by itself does not have authenticity or integrity and so what that means is that somebody could change my message while it's in transit between Alice and Bob and when Bob decryps he will not know that it has been tmampered with so I'll show you an example just know that this whole scheme it was designed for。

dentiality and only confidentiality we did not design it for integrity or authenticity it was not built for it right we were not trying to build a scheme that gave us integrity we were trying to build a scheme for confidentiality we did it but just want to remind you that building something for confidentiality does not mean we get the other properties okay and here's an example of how so this example it's a little bit contrived maybe you won't be super convinced by it but just know that these things are possible so。

Let's say Alice sends a message to Bob so Alice takes the message pay mallllory 100 and Alice encrypts it with CTR mode sends it over to Bob so how does Alice encrypt this thing with CTR mode remember she takes the knots and the counters she plugs those into block cphers gets as much onetime pad output as she needs and this is the onetimepa output that Alice generates and then she does the onetimepa xoring that's how CTR mode works and I get some output。

So whatever pay Mal9 $100 was we encrypt it and this is the thing we're going to send to Bob okay so this thing Alice sends it over now it's floating over in the insecure channel and we already know that this thing is confidentiality Eve as much as she tries will never know what this message says even if Eve has that power of tricking Alice into encrypting messages she will never know what C is that's great。

However， suppose we're not dealing with Eve， we're dealing with Mallory。So maybe Maory is like。

 I know the message says payal 100 and I want to get more than $100。

This is an assumption we're making even if you don't make this assumption this attack is still possible。

 but if we assume that Maory knows that this message says pay Malla 100 because maybe she does maybe she knows that this message is coming along at some point well then one thing she could do is she can try and change what this message says so that when Bob decryptps it Bob gets a different message like pay Mal 900 that would be bad and so the way that she can do it。

 I'm gonna to walk through it the whole derivation but it is here for your reference what we can do is we can say this bite we already know from before that onetime pad works on each byte one at a time it's like character by character so I know that if I want the message pay mala 100 to change to pay mal 900 I just have to change that single byte that corresponds to the digit one and make it say nine okay so how does she do that well turns out derivation looks something like this not gonna talk through it in too much detail but if mallory knows the message。

Because we assume she does and Mallory knows the Cyphertex。

 which she does because it's floating over the inure channel。

 Maory can solve for what the block cpher output was and if Mallory can solve for what the block cypher output was。

 then she can use that block cypher output which is the pad and encrypt the number nine herself so she can run her own Xor with the number nine to the digit9 and get some modified C prime so she can take that bit of C。

 she can do some fancy calculation swap it out for a different byte now she's got C prime。

Now when Bob decryptps this Bob now sees $900 okay so that's the rough attack And so what we see here is that Maory was able to change the message and Bob was none the wiser。

 he had no idea that the message changed and Maory did not have to know the key in this case And if you're not convinced you're like I don't like this I don't think Maory should know that the message said pay Mal 100 well that's okay even if Mallory didn't know what the message said。

 she can still do this right she can take the cipher text。

 she can change any bits that she likes and when Bob decryps Bob does no idea that the message has been changed maybe the message looks kind of unintelligible now where it looks like garbage but Bob has no way to prove to himself that Alice wasn't intending to send it So if Bob decryptps maybe he gets garbage。

 maybe he gets pay Mal 900 maybe he gets something else entirely but whatever Bob gets there is no way for Bob to prove to himself did this come from Alice or did somebody tmperered with it in transit Bob doesn't know so we still have to。

Sove this problem we're gonna do it next week but that's it for the confidentiality block we already to talked about CBC as well This is an attack that you will see in homework3 which is that CBC it's more complicated but you can also tmper with messages in CBC okay so these are the two things we saw today and in summary right we finished the top left block we talked about ways that Alice and Bob using a single key can encrypt multiple messages using the power of block cypherpers and chaining them together we saw that we had to introduce randomness and before you go the last thing I will say I repeat it it last time I will repeat it one more time today we introduced randomness and randomness gave us NPA security however introducing randomness does not guarantee in CP security you have to use it in a clever way which we saw today so do know that if you have no randomness it's not NPA secure we already saw how the termministic schemes are not secure if you do introduce randomness maybe a secure。

Maybe it's not it's only secure in a limited number of ways if you use it cleverly but on exams don't be tempted and see like oh it says the word random I'm going to start bubbling in the secure box everywhere I see it just because randomness is been introduced does not mean have security additional analysis is usually needed okay because I wanted to repeat that one last time just to remind you but that's it for today so next time you come back we will talk about the other blocks so next time we'll come back。

Not the other box， but the other squares， so the next time we're going to go to this block and talk about integrity Okay。

 see you next week。Okay。Questions in Zoom chat is nons public yes， all right， see y' all next time。



![](img/1d1524668e03d5d63cc837748a0f7698_3.png)