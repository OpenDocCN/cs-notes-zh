# 009：UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p09 -09--CS161 FA23- Lecture 9 - Cryptographic Hashes and MACs.zh_en -BV1YGbceREDs_p9-

She。

![](img/23981ee3dd35023bf744f233f084ec0a_1.png)

Okay， welcome back， so。We're going continue our exploration of crypto and from last time we already saw I think these slides might be duplicates。

 but we already saw from last time that we designed schemes for confidentiality and that was great I gave us a scheme where we could take a message and encrypt it and anybody reading our message over the insecure channel has no idea what we're saying and we can prove that from their perspective even if we give them the power to encrypt any messages that they want us to encrypt the message that we send is going to be completely indistinguishable from random that was the NCPA definition so we like that but at the very end of last time you might remember we said actually all these themes are great for confidentiality but we have not actually talked about whether they provide integrity and we actually saw an example where Maory could take a message and change one of the bits and suddenly the message that Bob gets is different and he has no idea whether the message was intentionally changed or whether someone changed it or whether All sent to send it so when。

Took the message like pay $100 change it to $900 Bob has no idea that the 900 was changed so that's our goal for today Okay so we saw this demo from last time we changed the message with did some clever exoring and suddenly Bob got a different message and he had no idea what the original message was okay。

So that's I guess from last time， but for today we're going to start looking at kind of this corner of things so if this works we're going to start living in this corner so we're still going to be in the symmetric key setting so for the next day or two we're still going assume that Alice and Bob have magically arrive at a shared key that nobody else knows but today instead of using that key to encrypt messages and make it so that other people who can't read it。

 we are going to use that secret symmetric key to tag messages so that an attacker can't modify messages without being detected so that's our goal for today and before we can do that we're gonna to lower about hash functions first which are our building block and then we're going to use it to build up the max algorithm that we're about to see at the very end so that's the goal for today we're gonna to live in that bottom left corner for today and then we'll move on so that's all of the things we're going to see today so before I can tell you about max and how to provide integrity I first have to tell you about hash functions and maybe you've seen these。

Other classes， but we're going to define it in a cryptographic sense so this isn't just any hash function you like。

 This is a cryptographic hash function and so this is the formal mathematical definition and then we'll break down why these are properties that we like to have so the hash function it takes in one argument right there is one argument and the single argument that it takes in you can think of it like a message but it can really be like any sequence of ones and zeros you pass it in and it can be any length so this is different from block cphers or other things that we've seen so far this M it could be a single bit it could be a million bits anything goes into this M and this hash algorithm will accept it so it's different from block cypherpers where if you passed in 129 bits a block cpher would reject and say no I don't know how to deal with this this hash function can deal with any length message。

However， no matter what length you pass in， the output is always going to be fixed n bits and n is is defined by whatever hash function you're using so view use a particular hash function that says outputs are 256 bits。

 you can pass in one bit or you can pass in a million bits no matter what the resulting output is going to be 256 bits or whatever the value of M is okay if you want to write a fancy weight you can pass in any arbitrary lane string that's what the star is for but the output is always n bits。

Okay so what are the properties that make a hash function correct at least in our definition So in this case hash functions are deterministic so in this case if you pass in the same hash function twice you do get the same output hash functions are efficient in the sense that again we are shuffling the bits around so you could write a hash function that does all sorts of ridiculous CS70 map that's really slow but at least most hash functions out there they shuffle the bits around the do some maxhor and that generally is considered pretty efficient so that's as far as we're going to talk about efficiency and then there's these three security properties that we're gonna to dig into and at first they kind of seem similar we're going to like tease apart why they are slightly different and subtle ways but all of them come down to kind of the same intuitive idea which is if you take some input M and it hashs out to some output。

 if you change a single bit in the inputs that's this point down here if you change just a single bit and you pass that slightly different message into the hash function the results would be completely different it should be unpredictably different。

So changing one bit there's no patterns as to how that causes the output to change So it's not like oh。

 I'm gonna add one to the input and suddenly the output has one added to it not really in a hash。

 if we change one bit of the input， the output just becomes completely unpredictable In fact almost all the bits will probably change like half the bits will change so that's the rough idea and that we're gonna to dig into how you can define more precisely what it means and I change the input the output becomes unpredictably different okay I guess before we do that I will kind of give you another way of thinking of hash function so sometimes when we think about cryptographic hash functions。

 people think of them like a fingerprint so we all have fingerprints they're all unique and so one way you can think of a hash function is that it's like a fingerprint over the sequence of bits it's 256 bit fingerprint it's always the same length and somewhere in that fingerprint it kind of encodes something that's like unique to this sequence of bits why is that because if you change that sequence of bits just a little bit。

The fingerprint comes out completely different so that's one way of thinking of it doesn't have to be and there are lots of different ways you can use it so here's an example if you want to read through it but that's kind of one way of thinking of has functions okay。

So let's talk about those three properties and like what they actually mean so I'll give it to you in like kind gory detail math and I'll also give you kind of an informal version of thinking of it。

 So this one's called one wayness sometimes's called preimage resistance and so here's how I think about it like the informal way of saying it which is okay so we' think of it again kind of in terms of a game if you want so I'm going to take some input X you don't know what it is I turn I'll turn around I will think of my secret message I will hash it and the result is some output 256 bits or end bit whatever the fixed output sizes and then I'm going to present that output to you so I'm going give you the output of the hash and now your goal is to come up with any input that if I pass your input through the hash function I get the same output Y so you as the people trying to solve my challenge you receive a single hash output you have no idea what I pass in as the input and you're looking for something that hashes the same output so you're looking for some。

It could be the same X that I used maybe I hash the word potato and I gave you the output and you're like this dude really likes potatoes so you're gonna try potatoes。

 you try it and you get the same output and you win my challenge right so you could use the same X you could also use a different X that you want to all you have to do is provide some X that hashees to the output that I provided and if you do that then you as the attackers win and the scheme is not one way but if you can not find that you just have no way of finding it then this scheme does have the one way property so that's one way of speaking of it I give you an output and your challenge is to find any X such that H of X is able to my output。

Okay， so sometimes people will think of this as like given y you can't go back to X and like that's mostly correct you can also think of it that way like I give you the y which is the output and you can't find the input but that's a little bit dishonest just because you don't have to find the exact input that I used so just because I hashed the word potato does not mean you have to you just have to come up with any input that hashees to the same y okay that's all that this nonsense sense。

😡，One way is， all good， I give you some hash output。

 you got to find something that hashees to the same output， okay？

So now there's another property which again it's gonna to feel closely related but it turns out that they are very subtly different。

 so again I'm gonna phrase this to you as a game， I guess before I do that one thing I will notice if you think about how many possible inputs are there to the hash function so well the hash function it takes in M message M could be any link so how many possible inputs are there to the hash function like infinite you can pass in anything you want could be of any link that you feel like as long as it doesn't like destroy your computer's memory you can pass in any input you want and it's a valid input to the hash function how many possible outputs are there say like n is equal to 256 well how many possible 256 bit strings are there there's like 256 of them so essentially what you're trying to do or what the hash function does is it takes like infinitely many inputs because your message could be any link and it has to map them to a space of two to the 256 possible outputs so yes。

of these are humongous numbers but I think about which one is bigger is two to the 256 bigger whereas like infinity bigger so hopefully we agree infinity is bigger and so if you're trying to map infinity number of inputs to 256 outputs Im trying to drop those zeros and if we have been but you're going notice and this is CS70 concept pigeonhole principle if you remember that but it seems like since I have way more inputs it's not going to be the case that every input has a unique output there's just way more stuff on the input side than there is on the output side so for a hash function there's always going to be cases where two different inputs map to like the same output that's always going to happen because there are simply way more inputs than there are outputs okay。

So that's a collision。 collision is a fancy way of saying there are two different inputs and they hash with the same output and collisions there're always going to exist because there are infinitely many inputs。

 a limited number of outputs， so you are always going to have to map multiple inputs to the same output there's no way around it there's always going to be collisions however we don't want attackers to be able to find collisions and we'll see y and a little bit but this creates a property called collision resistance and again at first it's going to feel like smell really similar to one way this but it's a little bit different so maybe one way to make sure that it's different is I will pose the same challenge to you but this time I'm going to pose differently so remember the one way challenge I hash a secret value I gave you the output and I challenge you to find an input that produces the same output but this time I'm not going to do that I'm going say I'm not going to provide you with anything so I'm not gonna give you a hash output or anything I'm just going say can you find any two inputs that you're choosing you can think any two inputs you like as long as the output is the same。

So your job is to find a collision any collision you want it doesn't have to match with whatever input I provided。

 whatever output I gave to you because it didn't give you one so the difference between one wayness and collision resistance is that with one way with the one way property。

 I give you an output and challenge you to find something that collides with that output or find my original input but with the collision resistance property。

 I don't give you anything I just say give me any two inputs can give me the same one twice it's cheating but give me two different inputs that hash the same thing and if you can do that and this is not collision resistance it's not resistant to attackers like you finding a collision however。

 if you have no way to do this in any reasonable amount of time as in like lathe of the universe like if you're not gonna get this done then we can say that a hash function is collision resistant。

So those are the two properties， okay。And throughout today， we'll see how they're useful。

 but the goal is you cannot find two things that hash to the same output， okay。啊。

Whereas like okay I don't know why that like faded in so fancyly。

 but okay so all that this slide says is that usually if you want to find a collision。

 it takes like exponential time there are ways to do it and there's like a birthday attack from CS70 that we're not going to talk about in like any sort of detail but just know that in for like functions that are clinical resistant usually the best known algorithms to find a collision are like。

Exponential， so to the n over two for n equals 256 like not happen right length of the universe never going to happen。

 okay。Great， so those are the properties of a hash function like what make it good and again in general。

 like if you've seen a hash from know 60 and me or whatever other prerequisite class。

 they probably didn't have these two security properties but those properties we do want and so that's the hash function anything that satisfies those is a valid hash function and so here are some examples that have been invented like over the years so the most classic one that people still use sometimes it' called MD5 this is like 1990 s hash function the output is 128 bits and in terms of like how secure this is the answer is it is not sort of the 90s and people have broken it over and over again and at this point is like totally busted so for MD5 is not one way if someone gives you an output you can actually find an input that matches if someone challenges you to find the collision you can do it MD5 is broken people have figured out how to do it。

Then there's a new family of functions that are more modern so they're called Sha one Sha2 and shot three and all of them use slightly different constructions underneath you'll get to play with it a little bit in your homework or probably but all of them have different output sizes so for example for Sha2 this is a family of algorithms and you can choose to use the one that outputs to56 bits of by 12 bits you can pick your favorite output size and again over the years people try start and learn ways to break these so Sha1 is now broken so people don't use it anymore Sha2 is not totally broken but sometimes it's vulnerable to a fancy thing called a length extension attack which you get to see in your homework so I'm not going to spoil the fun for you and kind of the modern data of the other is called shot three that's the fancy name of I think this might be the person who invented it I don't know but they gave it a fancy name that's kind of a modern standard questions。

Thats to the question which is what happens if you hash it multiple times So I'd say at least for cryptographic hashes。

 people tend not to hash things multiple times because if you already have those properties of I give you the output。

 you have no idea what I hash to get the output or you can't even find any sort of collision and whether you hash once or twice or 10 times the outputs the same if you want to sometimes some of these underlying algorithms already repeat a bunch of steps for you so you don't have to to increase their own security but we're not gonna talk about like what's going on underneath these except you'll get to see it briefly and homework which is kind of fun so those are the type of hashs。

 you don't have to memorize them but know as you go in real life I think it's nice to know things like you seeMd5 don't use it for any secure purposes and so forth another extremely out of scope a random thing that I found out recently is that you can imagine not a lot of people have my name but apparently the guy who like helped rich Shaw one his last name is apparently my first name so I find that pretty funny because I was like destined to show you this like anyway。

This is the length extension attack again you will see it more in your homework but the idea is that if I give you the output。

 but I don't tell you the input so just like before I turned around I picked my own secret input and I gave you the output even though you don't know my input you actually might be able to give me the hash of my input concaten it with your favorite word so you'll see that more in homework input just to give you a bit of a flavor okay。

Great， interesting， the name Kac from before is a variance spelling of kcak。

 a type of Balinese dance， thank you Z。Interesting okay so at this point。

 we've created our building block just like when we created a block hackers last time And so the first question you might ask is。

 are we done can we go home do hashs provide integrity And the answer is that very often is in this class is it depends so what do I mean Well depends on what the attacker't isn't able to do So here's an example where hashs maybe they do provide integrity So this is something that people actually do a lot in real life。

 which is you can imagine you know Mozilla， which is the people who publish Firefox maybe they publish a new version and they put it on a lot of different servers so that people can download their new shiny version of Firefox okay and so Alice download that program like Firefox EX and Alice is not sure is this the real Firefox like if I run this program Well I get Firefox web browser or am I going to get some like now where that someone installed I have this Firefox EX I'm not really sure what it's gonna be And so one way you can solve。

Alice when we can solve this problem and Alice can be confident that she has figured out or downloaded the correct version of Firefox is we can use hashs so there's only thing you can do so before publishing Firefox E Mozilla can take that thing and hash it and publish the hash on its website for everybody to see and now everybody in the world knows from Mozilla's secure website that if you download Firefox from anybody out there like I go on my torrenting website and I torrent Firefox E if I want to verify that is correct all that I have to do is I just have to hash my copy of Firefox。

 E and check that it matches the hash of Firefox。 E that the real publishers came up with so why does this work well there's a couple reasons why this works so one of them is remember when we said what makes a hash function correct a hash function is correct if you get the same output when you hash the same input twice so if the real Firefox developers hash Firefox。

and got some output and then Alice hases spur really suspicious you know sketchy download a Firefox。

 e and gets the same hash well we know that from like the correctness property that these two are。

It's expected that if you ask them the same legit Firefox that E， I get the same output。However。

 if Alice's super sketchy version of Firefox that EX is tampered with it's malicious。

 then what's gonna to happen is when she hashes it。

 she's going to get a different arm that's the property of hashes when you pass in something different even by a little bit a alpha is completely unpredictably different and so he's going to take that compare it to mozllilla's Firefox hash and be like wait a minute these don't match I probably have a busted version of Firefox okay。

That's one thing she can do and we relied on the correctness properties to ensure that Alice has the right version of Firefox so then now you might start asking well wait a minute what if the attacker tries to be smart like instead of just taking Firefox adding their own little viruses inside what if the attacker says I'm actually going to try and find some way to come up with this Firefox E that's tampered with that has the same hash because if they hash for the same thing。

 I can trick Alice into thinking that this is the real Firefox so can an attacker take the real Firefox EX change it up so that the hash stays the same well no they can't do that why is that because now they have to find a hash or find an input that matches the same output hash and we already said from the one way property and the collision resistance properties that you cannot do that there is no way on a secure hash to find another input or any input at all that hashees with the same output。

Okay， this might， I think this is probably the supposed to say along ways。

 and I will fix it afterwards， but that's a okay。So the reason why this is relying on the one way property is because we have provided the attacker like here it is。

 here is the you know here's the output hash of Firefox。 EX。

 can you find any input that does not match the one that I passed in that also hashees to the same thing and the answer is no。

So relying on the one wave front here。I guess you could technically say it also relies on collision resistance and that we cannot find two inputs to hash into the same output but in either case we're using the secure properties of a cryptographic hash so that an attacker can't be sneaky and be like well I'm going to create a different version of Firefox。

 with the same hash so why did this whole thing work like it seems like we're all done cant we just go home well the reason why we can't go home is because we made an assumption in this question so in this particular example we assume that when Firefox publish the hash that nobody can change it so Firefox they put the hash on their real website they sent it into the world and we assume that everyone knows the true hash of Firefox E and there's no way to tamper with the hash itself we use that assumption to make this whole scenario work。

Okay what if we get rid of that assumption and so in this case hashes do provide integrity but let's try a different scenario in fact。

 let's try the classic scenario we've been doing over and over again what Alice and Bob want to communicate let's see what they can do so maybe let's say I think hashes they might work they have these nice cryptographic properties let's see if it works so Alice is gonna take her message and she's gonna to send message followed by the hash of the message those two things get sent over to Bob and what can Bob do Bob can check hash the message again see if the output matches the hash that Alice sent and if it does then maybe Bob is convinced maybe he's not convinced but that's how Bob could possibly check that this works okay so we could do that well one like side note I will make before we keep going is you might stop and be like wait a minute are you telling me that Alice just sends the message with like no encryption whatsoever for this lecture yes because in this lecture。

care about so far as just the integrity of the message we're not concerned about confidentiality of the message we just want to make sure someone cannot tamper So in this case。

 yes， we're just gonna send the entire message in plain text okay for now you don't like it we'll fix it at the very end so we send a message which is okay because we're not trying to keep it secret we send the hash of the message so that nobody can tamper with it and like are we good can Bob just checked this and when Bob checks that the hash matches like is he done can we all go home well what if mallory does this mallllory says okay Alice you sent this you sent pay mallory $100 and we sent the hash of that So what if mallory swaps this M out and she picks her own like evil M prime or something now if she send M prime and the hash of the original message these are not gonna match when Bob hashees this thing it's not gonna match the hash to Alice because those two messages are not the same and we already know mallllory cannot come up with another message。

That has the same hash So is mallllory doomed is she out of luck Well can mallory change this This is also send heridec channel So what if mallllory says I don't want to send H of M to Bob I want to send H of M prime can Mallory compute this Well yeah。

 mallory knows the hash algorithm remember soon the attacker knows the algorithm And if you know the algorithm you can compute m prime So now Bob gets M prime the evil message the hash over the evil message Bob hashes the message it matches the hash that was sent by mallllory and suddenly。

Bob accepts this evil message as if Alice absent it。

 so still no integrity in our classic setting of Alice and Martin。So yes。

 in some settings it might work， but in this setting。

 it still doesn't work and the key reason why it doesn't work。

 most important reason why this totally failed is because。

There was no key there's no secrecy going on here anybody can compute that hash because all you have to know is the hash algorithm which everyone knows and all you have to know is what to pass in and in this case we're not passing in anything secret anybody can pass in whatever they want to this hash function so there was no secrecy and maybe it makes sense that like well Alice and Bf had that secret key I never use the secret key so far so maybe it's not super surprising that hashes at least in this particular model no integrity okay we finished our discussion at hashes just like before when we talked about block ciphers no integrity。

 but maybe we can use it as a building block could give us something that does provide integrity so that's our next goal okay anything want to know about hashes before we're done with them for。

little bit。O。Any want to zoom， nope， okay。All right so let's try to use that and build something a bit smarter so again we're in this bottom corner for today we don't care about the confidentiality of messages for now and we're just trying to make sure an attacker cannot mess with a message or tamper with it without being detected okay so again we remember Alice and Bob have still magically gotten a secret key that no one else knows and just like before you've already seen this slide but I'm going to bring it back one more time remember that the way that we're gonna do this is we're gonna to add that secret little tag on the message and so we talked about physically you can think of it as like adding some super special sale on the message but if you don't like that or if you've ever like sent a mail in your life before you can also use the cryptography version of it which is what we'll be using so our goal today is we want to build this algorithm in the box here this algorithm should take in a message and the secret key because that's what E mallllory doesn't know and I want to take the message and the key and I want to output a unique tag on this message and now instead of。

Sending just the message by itself I send the message and the tag and then later we need to write an algorithm for Bob to verify that the tag is correct and if the tag is correct Bob accepts the message and if the tag is not correct then Bob does not accept the message we think it's been tampered with so from a correctness standpoint those are the two algorithms we have to come up with we need to figure out a way to generate new tags on messages hopefully using the secret key to our advantage to make it hard for mallllory and we also need to come up with an algorithm to verify those tags have not been tampered with。

And then from the security standpoint， we hope that Mallory has no way of breaking the tag if she modifies the message。

 the tag gets messed up， she modifies the tag， the tag gets messed up， she tries to modify both。

 she has no way to modify both so that they both match up or that they correctly verify。

 that's our goal， okay。So we've already seen roughly what the definition is from the picture I'll show it to you again in some math so we already know for most of these algorithms we need to specify how to come up with the key and promise you it's coming soon for today Alice and Love have a secret magical key that no one else knows and this is the algorithm we want the algorithm we want is takes in a key the secret key takes in the message outs the tag that's our goal and the message can be any length and the tag has to be a fixed。

Why is it like that well it kind of matches the hashes that we've seen before that's how we defined it so kind of up to you put in this class or at least the most settings that I know of the input can be any length you want and the output is some fixed length tag okay。

So what makes them correct for this class， we're gonna assume Mac are deterministic which means that if you pass in the same Mac twice。

 you get the same output twice there are actually more fancy ways of doing Macs that don't that are not deterministic but for this class we'll just stick with the deterministic version because it gets you most of the way there and again Mac should hopefully be doing things that are not super expensive so that's the properties that we want now let's think about the security of the Mac so once again whenever we think about security I need to introduce to you a new game so let's talk about the EUuc CPPA game a lot of the letters and the letters stand for existentially unforgeible and you're like what is this and so all of this slide it's just a really fancy way of saying we do not want to attackers to be able to generate their own tags on a message it's like all of this slide basically so we already said from before if you modify the message we hope that the tag no longer checks out if you modify the tag the tag no longer checks out okay。

We don't want Mallory to be able to generate a new message for herself like she picks her own evil message。

 we do not want her to be able to generate a new Mac for her own evil message and remember she doesn't okay so the goal is that somebody who doesn't okay should have absolutely no way of generating a valid tag okay。

😡，Another equivalent way of saying this and we're not going to show that they're equivalent here。

 but it turns out that they are Another equivalent way of saying this is that if I give you a Mac output。

 there's no way for Maory to come up with another input that maps to the same output so this second way of phrasing it is like Maory from before trying to change like Firefox EX so this is saying that if I tell you what the Mac on like Firefox EX is you mallllory without knowing the key。

 you have no way to come up with a different modified Firefox E that has the same output so that's an equivalent way of stating this definition okay so that's the definition again it's kind of math and hard to think about so another way you can think of it is through a security game and just like in the symmetric key setting we are going to continue to assume that mallory has the chosen plain text attack available to her which means that mallllory can always walk up to Alice and say here's a message please generate the tag for it and Alice will have no choice but to faithfully generate the tag every single time。

Using her secret key， okay。So all of this boils down to this definition here。

 which we're going to formalize into a game， and so the definition says even if I give Mallorory the superpower where she can walk up to Alice ask for a tag on some message and Alice will always faithfully return the tag。

 even if I give Mallory this superpower which she can use to try and learn something about the key or the algorithm。

 Mallory still has no way she just cannot figure out a Mac on a message that she hasn't seen before okay。

So that's the definition now let's play the game version okay so the game version of it is that your're mallllory and just like we said。

 you have the superpower， you can come up to me and you can say I want to see the Mac of this message and I as Alice I'm just going to be like okay I will take my secret key I will faithfully give you the real correct tag on that message and I'll send it back and you can use that to try and learn something you can try and figure out what kid is you can try and figure out what my algorithm is doing。

 you can try and spot patterns like do what you want to but you can do this as long as you want until you get tired of it so that's your stage you can like play with this algorithm ask me to encrypt things or generate max on things I will always faithfully do it for you and once you get bored of it or you think you figured me out're like I know your pattern now I know your game at some point you're confident you think you know what you're doing and now you're ready to take the challenge so you're like I'm ready for the challenge and so my challenge for you then is like。

Sorry you say to me I'm ready for the challenge I looked at the messages I've seen the Mac that were created I think I know what you're doing and so I'm ready for the challenge so the challenge that I'm going to issue to you is you don't know what the key is unless you figured it out using the scheme but I never told you what the key is and so I want you to generate a message and a tag that you have not seen before now if you can generate a message and attack that you have not seen before then you've broken my scheme because you didn't know Kate but you were able to come up with a new message and a valid tag on it even though I never told you Kate and if you can do that then you win if you cannot do that you lose okay。

So let's talk about a couple of restrictions on what happened here One of the restrictions which we did not have an NCPA is that you cannot cheat and be like oh I asked you for the you asked me for the Mac of potato and then you give me the Mac of potato as the answer to the challenge you can't do that so that's cheating in this particular game you need to come up with a new message that you have not seen before that's what we chose for this one for our threat model if you don't like it you can change the threat model you get a different security game but because we to max in this class to be deterministic and that all Mac have this property where you passing the same input twice and get the same output twice for this class it would be kind of silly if we didn't add this restriction because if we didn't have this restriction then every single Mac out that would be insecure and we would be hopeless so we had this restriction because we are defining max to be deterministic if you passing the same input twice you get the same output so itd be kind a pointless if we didn't have this restriction you could just ask me for the Mac and then give me that。

Mac back and win the challenge it's a little bit pointless so for our threat model we have to add this restriction where the message that you give me as the answer to your challenge has to be different has to be something you've never asked me about before okay and just like before the winning condition is that you give me a valid pair and if you cannot give me a valid pair like I try to verify that this is a valid tag on this and if it does not verify correctly you lose but if you come up with a valid forgery and you win okay。

And so。Again the way that we define security depends on how often you win so if you use the best strategy you can possibly think of and you can use any strategy you want you can try and figure out okay you can try and figure out the Mac algorithm you can go ask chatGT or whatever right and so whatever strategy you come up with you're going to have some probability of winning if we play this game over and over and over again in the long run and so。

😡，We're going to define EUucCPA security to be if your probability of winning is basically zero then this scheme is secure if your probability of winning is even like onefi or 1% and it's not secure okay so why do we use zero here instead of 05 remember the NCPA game we said that the condition for something being secure is that the attacker wins with probability 0。

5 or greater so why am I choosing  zero here instead of 05 well in the NCPA game， the 0。

5 baseline came from the fact that your challenge was guessing like A or B you were guessing one or the other and because you were guessing A or B your probability of winning if you had no clue what was going on 0。

5 So 05 was the baseline in N CPPA because your challenge was guessing A or B and you can always do that with probability of 0。

5 but in this case we're not asking you to guess A or B we're asking you to come up with an actual forgery an actual message in an actual tag So in this case if。

You have absolutely no idea what you're doing and you're just throwing out stuff at random what's the probability that you win like zero like one over one to the two to the 128 something really small so in this case zero is our baseline because someone who has no clue what they're doing and has no idea how to break this scheme it's gonna win with average probability zero so that's why we're using zero here okay that's the game anything you want to know about it it's kind of similar to NCPA if you squint but in this case we're not asking you to break confidentiality and learn the message we're asking you to generate a tag without knowing the key okay and if you can do that then you can tamper with messages so we don't want Maory to be able to win this game Maory cannot win this game and our scheme is secure okay。

So that's what makes the Mac good， we already know what makes the Mac good。

 we've already talked about how to generate the tags we've talked about how to verify them。

 one really brief note I will make is that because we define Macs to be deterministic this verify algorithm。

It really could be anything here， but our verify algorithm will be just to recompute the Mac and check that it matches pretty similar to what you saw in the hashing part。

 we'll recompute the Mac the matches and we're gonna be convinced that the message is good it doesn't match and we're gonna to be convinced that someone messed with the message so just putting that out there so we know what Macs are again anything could have gone in these boxes as long as it satisfies the UCCPA definition but I'm gonna give you one possible thing you can put in those boxes as an algorithm So I'm going to call it n Mac I don't know what the in for you can invent something but I'm gonna to reason that like well we had the cryptographic hashes and those seem kind of nice because they had that property where if you do not know what or if you see the output you have no idea what the input is and like that seem pretty useful if I show you what the output is you have no idea what the input was and also if I change even one bit of the input you got something completely unpredictable so I like that I want to use that property to my advantage to build。

that satisfies this EUuc CPPA existential unibility definition so I'm going to try to do that Okay so here's I'm going to do it and it's gonna to feel a little bit funky at first。

 but hopefully the like base idea behind it we'll seeing pretty natural okay so I'm gonna start by generating two keys for some reason not totally clear why yet but like ultimately it seems like what I've done is instead of just hashing the message which we already know is not secure anybody can hash any message they like instead of only hashing the message I'm gonna hash the message but also like throw in stuff about the key because if I throw in stuff about the key and the message now an attacker is gonna have a really hard time coming up with a forged attack because the attacker wants like hey I want the hash of or I want to figure out what the Mac is of my evil message well then the attacker is gonna have to come up with a hash using this exact same algorithm。

But the attacker is going to have to do with her M prime and kind of the idea is well this time the attacker has to know what K1 and K2 are in'm going to calculate this thing。

 but the attacker doesn't know what K1 and K2 or there're sink keys。

 so for the attacker it's more hopeless this time。Again， not a formal proof。

 but the rough idea is that by throwing the key into the hash function instead of only hashing the message。

 now the attacker cannot compute as many hashes as they like from before， if I just said hash of M。

 the attacker could compute whatever message they wanted that they could hash it。

 but now since computing this N Mac or this Mac requires knowing both the key and the message it's a lot harder for the attacker。

That's the rough idea。If you're curious like wait， why am I adding K1 K2 could I not just have said the hash of k concatenated with M again not going to prove in any detail。

 but the rough idea is that we don't want that length extension attack or we'll see in homework to come back and like buy us as a butt so we're gonna to add two hashes just to defend ourselves against that and it turns out this thing does have approved behind it which is kind of nice so if you take your keys and you hash them with the message in this really peculiar way you do get UCPA security someone who does not know the key has no shot of coming up with a valid tag on the message which kind of makes sense if you don't know the key how the heck are you going to compute that thing you can't okay。

So this construction it's nice it has the proof behind it it's secure but it is kind of awkward for a couple reasons so one of the reasons why it's awkward is I needed two keys like that was annoying like why did I have to use two keys instead of one well the proof required it but kind of like that Alice and Bob now have to use two keys instead of one as confusing to me。

Another thing that's a little bit awkward is that K1 and K2 have to be some fixed link which I don't like either what if Alice and Bob used to use a different key size so I don't really like that either so in practice。

We're just going to take Mm and again this is not for extra security。

 this is just to make it a little bit more usable， so we're going to make a little bit of a modification。

 make it more usable and invent something nicer called the H Mac。

Now the Hmac is nice because it takes them just a single key instead of two keys and all that Hm does for us is that it takes that one key and creates two different keys out of the one key Why do we do that it's just because I don't want to have to use two keys that's all so HMac it basically is just Nmac but it solves the problem with having to use two keys which was annoying and it also solves the problem with the keys had to be of some fixed length Hmac will solve that for us by either padding the keys until it a certain length or by chopping off the bits that are not needed so it's mostly like bureaucracy there's nothing too interesting between the change of Nmac to HMac but I'm just making it so that instead of using two different keys which is annoying I only have to use one key that's all that we're doing。

Okay。Great now final question you might ask is like how don I come up with Oad and iPad What are those things like do I sh an actual iPad in the algorithm know right so Oad and iPad are just fancy in terms for outer pad and inner pad and basically the idea here is that you have a single key but the Nm algorithm the one that somebody went through all the trouble to prove the secure that one took in two keys and the proof which I have never read I cannot tell you about apparently the proof says like skim but still that proof apparently says that you need two different inputs or the two keys have to be different in some way So we're does it gonna take this key Xora with some bit string that someone decided to use take that key Xora with another bit string that someone else decided those can be public and constant and my only goal here is just to get two different keys out of a single key that's all that I've done here So again mostly bureaucracy but in case you're curious how the sausage is made now you know okay。

And you're like well where did they come up with these patterns so they came up with these patterns because they were paranoid really anything would have worked here but they intentionally show stuff that they think is probably best for security so okay now you know。

So we took NMAC provably secure thing， we made a bit of bureaucracy changes to it， got HMAC。

 but overall like all of this is just a really complicated fancy way of saying that at the end of the day。

 I have this algorithm that uses the property of hashes， but instead of just has a message。

 which we know is pretty pointless because anyone can hash any message they want。

 I hash the message but also something about the key。

 so now the attacker cannot generate HMAC without knowing the key， that's the rough idea。

Okay there was a question about the length extension attacks there would be more about that in the homework so i'm not going to spoil the fun。

 but intuitively we just don't want people to be able to generate the Hm of M。

Concate it with M prime， but more about that in homework I promise okay so。

Cool things about Hmac now that we have it in front of us and again all that you have to know about it is that we've taken the message and the key we have like mixed them together somehow and then hash them both instead of just one So what's nice about this well one really nice thing about it is that Hmac it is just a hash。

 I am just applying a hash function to stub the stuff is a message with the key blended together but ultimately I am just hashing st and because Hmac is a function where I'm hashing stuffub all the properties of a hash function。

 they still apply for example， if I use a crypttograph the hash I have the collision resistant property。

 which is great it means that an attacker cannot come up with two different inputs of this stuff that caused the same Hmac output that's nice also has the one way property where if I tell you the output of this thing which is what we do in the Alice and Bob example we pass the Hmac from Alice to Bob even if we show the attacker the output of the hash they have no hope of ever learning what I passed into the。

To get the output where they have no hope of ever coming up with anything that they can put inside here that hashees to the same output so it is collision resistant it's one way all the properties of a hash that still apply because Hmac it is a hash is just the hash off more stuff not just the message itself that's pretty great and so again there is a reduction proof in here we're not going to talk about reduction proofs here but one way that you can prove that HMac is secure the thing we want to prove is that if the hash is secure in that it's one way and collision resistant that HMac is secure so I want to prove the forward direction the way that you would prove it is you would prove the contrapoitive which is a fancy way of saying if I can break Hmac then I can break the hash function so again not going to talk about it in detail but that's how someone will prove this they would say someone who can break HMac can also break the hash function therefore if the hash function is secure then HMac is secure okay。

That's great so we have HMac like it's wonderful， it gives us all these nice properties and so finally we've designed a Mac that has the EUCPA property we want someone who does not know Kate has no hope of computing this thing okay。

😊，Great so finally we can ask ourselves the question do Mac provide integrity so at least in the setting that we've talked about between Alice and Bob finally the answer is yes so if Mallory takes or sorry if Alice takes the message he generates an H Mac on the message and she sends the message and the Hm together I believe we have integrity and attacker who changes the message is gonna and someone tries to compute sorry let me try that again maybe with pictures this time can I find the picture okay？

Great so we finally found something that works it's HMac right and so what we can do is we can send the message and the Hmac of the message if an attacker tries to change the message and change it to like M prime or something then the tag is no longer going to check out by hash a different message I'm going get a different HMac output it's not gonna to check out if I try to mess with the tag that's going to cause the message in the tag tore not check out and because of the unfordability property there is no way for an attacker to come up with a message and the Hmac of a message together that match no way for them to do it so we know that we have finally provided integrity Bob can verify by rechecking the Hmac and know that the message has not been tmampered with finally questions you say message。

It's the encrypted versionYeah zero question which is here what is this message。

 this is the actual message with nothing of it but plain text message and the reason why is because for all of today we just care about attackers modifying at least for today we don't care whether or not they can read the message and at the very end of today we'll combine them together。

可以。Other stuff so I had a couple of questions one was for our definition of。

That's unfortunatelyability property， yeah。This is technically not for the definition I was wondering if the math leaves like a bit of the key or like part of the key does that break the definition thats a question what happens if the Mac breaks like least one bit of the key。

 I don't think it breaks the definition， assuming that you cannot use it to win this with any nonmligible probabilityability。

 at least for this definition so a question。系你边好事啊嗯。

I was also wondering for the definitioneach just take the the message key and then there's no possible Yeah Is question which is are there other constructions that work there probably are but as far as I know Nmac is the one that's been proven to work so there are probably other constructions but I don't know if they have the same like provably secure properties that this so again like the actual details of the proof of beyond the scope but somebody has proven that this like very specific construction works and I think the paper might be links in our figure is okay I'll take a couple more and then'll keep going my last question why is N。

Yeah again， why do the max require the keys to be the same length it's something to do with this particular algorithm and its proof that we haven't talked about in detail。

 but somewhere in the proof that said that so that's why okay yeah anything else can just。

In this in the forability game you mean sorry yeah so in the forability game there's no Bob right there's only two people there's only Alice the person trying to prove that the scheme is secure that's me i'm Alice I'm trying to prove that this scheme is secure your mallory trying to win the game and the scheme is not secure and who wins the game tell me whether this game is secure or not so there's no bo it's just two people to the question。

Okay so yes， Max provide integrity at long and last in our setting we think Max provide integrity and so now we have to ask about authenticity。

 which is that funny thing that was kind of like integrity。

 but not really so first let's remind ourselves authenticity was the property of do you know for sure that this message came from the person who claims to have sent it So if I send a message and at the very end I'm like love Alice right like does this message come from Alice or is it somebody else pretending to be Alice like sincerely Alice is that from Alice or did somebody else take that message write that message pretending to be Alice that's the authenticity property So the question is do Max provide authenticity and like always the answer is it depends and so specifically the reason why it depends is that anybody with the key can generate a Mac so at least for all of today we could assuming that two people have access to the secret key Alice and Bob but imagine a different setting where like everybody in the。

and it could be like 10 people to a dozen people if everybody in the secret club has access to the secret key and you get a message and you check the Mac and the Mac is valid。

 all that you really know is that it came from somebody in that little secret club with the secret key but you don't know who sent it could have been Alice could have been Bob could have been someone else in the secret club and so。

Do Max provide authenticity depends on your setting in that particular setting if you got a message with the valid Mac and at the very end it was like sincerely I was from Alice you really have no idea whether it's from Alice or from somebody else who had that same secret key so depends on your threat okay。

But at least in art model where we only have two people， Alice and Bob。

 we can say that Max do provide authenticity because if Bob receives a message and at the very end it says from Alice and Bob is like。

 okay well this thing has a valid Mac the Mac etca so that means that somebody with the secret key must have generated this Mac well who has the secret key me and Alice and well I didn't write a message with a from Alice so it's got to be the other person so it's got to be Alice so in the case that there's only two people at least in this particular setting。

 we can say Max provide authenticity there's a little bit of fine print on whether or not a scheme provides authenticity but in this case will say yes final question which is do they provide confidentiality well not really and in fact it's not really even clear what it means to be confidential here because you're not really encrypting or decrypting stuff but in general there's no guarantee that Max don't leak information so you can always construct the Mac that does leak information。

If a Mac can leak information then it doesn't have confidentiality properties so in general。

 if you just send a Mac of a message it doesn't have to be H Mac there are also other Mac algorithms out there。

 but if you send something like this Mac of K comma M you have no guarantees as to whether or not the M is concealed here somebody could even like take this Mac and read off what the value of M is or it could contain information about what M is like so in general Mac of K comma M no guarantees on integrity all bes are off the only property that we have is that somebody cannot generate this for their own message but does this thing contain information about M it could there's no guarantees you go back to the slide on what are all the properties of a Mac nowhere on that slide do we say that Mac cannot leak information about M it could so Max they don't provide confidentiality by themselves。

So if you see Mac K comma M， don't get tempted and be like， oh， well， how could they get M back。

 there could still be information in there that leaks information about them， okay？

So integrity and authenticity， check， confidentiality and not really okay。So that's the end of max。

 we did it， we found our scheme that provides integrity，'s not the only scheme out there。

 but also other ones， but that's the one we chose to use。

Okay so in the last like 30 minutes I'm going to tell you about how do you combine these two because as someone mentioned earlier when we talked about Max to we had like no regard for confidentiality all we cared about was that people couldn't tamper with our message and we got that to work down here lastly we spent all of last week coming up with schemes that give us confidentiality and at the very end I told you that none of those schemes provide integrity someone can always change up the bits and Bob will be none the wiser he has no idea whether the resulting message is truly from Alice or was tamered with someone but we did get confidentiality so it seems like we got both of these things in isolation so at this point you might be tempted to say well what if I want both maybe I don't just want someone to not be able to read my message I also want people to not be able to tamper with my message I want both so in the last 30 minutes we're going try to combine these two and get something that gives us both of these properties but it turns。

We have to do so really carefully， remember cryptography is super fragile and if you do even the slightest things wrong。

 like you end up being an example for other people right of what not to do so don't be the example okay。

So here's our goal for the rest of today which is we like schemes that give us confidentiality。

 we like schemes that give us integrity， we want so I want to design something where I can pass in a message and when I send it to Bob it's got confidentiality and integrity。

 I want both。So there's two ways to do this so one way to do it is to say well I already spent a week talking about schemes that provide confidentiality then I spent like half of today talking about schemes that provide integrity so I'm just going try to combine these interesting ways to give me a scheme that provides both that's what we're going to do today and at the very end i'll tell you other ways to do it which is you could also say forget all the stuff we just talked about I'm going to design a scheme from scratch that gives you both the same time so we'll see that at the very end too。

Okay。So we can either take schemes that provide one schemes that provide the other and combine them in clever ways。

 or we construct start from scratch and design something completely new。

Let's start with the first one so here we go here are all the tools that you have available to you this is your cryptography toolbox so far so we already saw all of those encryption schemes that provide confidentiality for example。

 you saw AES with CDC AES with CTR all these different blog I training modes so you have them available to use there they are they're in your toolbox you can encrypt stuff you can decrypt stuff those algorithms are freely available for you to use as you design something。

You also have the Mac scheme， for example， we saw HMac， other ones are available。

 you have this scheme， this scheme provides what integrity because someone cannot generate their own Mac for their own messages without knowing the key。

 but it does not provide confidentiality because someone who sees the Mac might be able to learn something about M。

And then what about these schemes these schemes give you confidentiality because someone who sees the encryption has no idea what message you sent but they don't provide integrity because if you take the message and shuffle it up Bob has no idea after he encryptrypts that the message was messed with okay so I want to combine this so here's my first attempt at least I'm going say。

 well you've given me a perfectly usable encryption scheme and a perfectly usable Mac scheme so I'm just going to do both instead of sending the message in the Mac like we saw today I'm going to send the encryption of the message followed by the Mac so I'm gonna send two things to Bob so Alice is gonna encrypt the message and also attach a Mac on the message and send this whole thing to Bob and Bob's going decrypt the message check that the Mac is correct if it is Bob is convinced that the message has not been tampered with and hopefully nobody can see over the Instagram channel what the message was so if we do it well is there integrity well it seems like there is because if someone modifies with。

messes with M that's not going to check in so it seems like we have integrity what about confidentiality。

Think about this one under it， does this thing provide confidentiality if an attacker sees this and this。

 do they learn anything about M or is my M always protected？Well。

 remember what we just said about the max。If you get this message， Max don't provide confidentiality。

 there's no guarantee that someone who sees this blue thing Mac of K2 comea M there's no guarantee that they don't learn anything about M so our first attempt didn't work it looks so tempting that it did work but because Macs don't provide confidentiality that second thing in blue might leak information so that didn't work okay we'll try again so this time I'm going to say you know what I realize that anything I pass into the Mac。

 it could be leaked so whatever I shove into this Mac。

 it could be leaked so I am instead of shoving the message into the Mac which causes the message to be leaked I'm going to shove the cipherts into the Mac and why is that because now this Mac the value in blue it can leak all at once because all that is's gonna leak is information about the cipher textex and we already know the ciphertex is not useful for learning the plain text it's secure so even if someone learns。

About the Cyphertext I don't care no one can take the cyber textext and learn when I plain text was so all that I changed between the first attempt and this better one is instead of taking a Mac on the message which causes us to leak information about the message I'm going to take the Mac on Cyphertex。

Because if I take a back on the siteprotext， now if I leak information about the siteprotext。

 I don't care， siteprotext doesn't leak any information， so it's okay。

So I still have integrity why do I have integrity because if someone messes with the Cytext I will find out through this Mac so this Cytext is protected and therefore the thing that antiCs do also protected okay does it have confidentiality yes because I don't care about this Mac it can be as insecure as it as I want it to be can leak everything about the message I don't care because thing that I passed in it's the Cyex that's okay。

Okay， so we did it， we invented our very first scheme where we took these two， combine them。

 but noticed that we had to do it in this clever way or else things could go horribly。Okay。

So that's one possible idea， but it iss not the only idea so another clever idea is remember how we said this Mac might leak information because it's not it doesn't provide confidentiality it might leak information about M so I'm going to say if this thing is not confidential leaks information about M I don't like that so I'm just going to scrub it into the encryption why am I sending this thing over plain text leaks information I'm going encrypt it and then send everything encrypt it so now I take my message and the Mac all of this could be leaking information about M and I encrypt the whole thing I encrypt everything and I send the whole encryption over。

Does this provide integrity， yes， because again there's a Mac and I already know that if someone tambpers with an M they cannot get this Mac to match up。

 does it provide confidentiality， yes because the whole thing M and the Mac。

 everything got bundled into the encryption， so it seems like yes。

 this thing does have confidentiality。None of these are proofs， by the way。

 but they are like intuitive ideas as to why these things provide integrity and confidentiality。

 okay？Cool， so we have two different ideas now let's give them some names so。

The way I'm going to name them is I'm just going to name them in the order of what I did so in the very first idea or that was the one down here where I sent the sign pertext and then I sent a Mac over the sign pretext I'm going to call that one encrypt then Mac it's a really clever name Why is it called encrypt the Mac because I encrypt it first and then I meed brilliant so that's their first scheme the other scheme is called Mac then encrypt why did I call it that because I computed the Mac first then I encrypted the Mac。

Brilliant okay， so those are my two different schemes I gave them names and the names just tell me what order in which I did things。

 but both of these ideas at least from a security standpoint of do they leak information。

 do they let an attacker tama with the data both of them give me the properties that I want。

But I achieved them in slightly different ways。So at this point you might ask which is better and so turns out there actually is an answer here and it's kind of surprising because it seems like I just argue that both these give the same properties so how could one of these be better than the other it turns out there is a really subtle bug just like all of cryptography there's a really subtle bug that actually makes encrypt the Mac the superior version and so the reason why encrypt the Mac is superior and you actually get a chance to play with this a little bit in homework3 which is the batting oracle lab which you will see in detail soon but the reason why we prefer encrypt the neck because think about how someone using Macum encrypt which is this one up here think about how Bob is going to have to take this and decrypt and verify what is Bob going to have to do the first thing that Bob has to do is Bob has to take this entire blob of like whatever data Aliceent and decrypt with the actual secret key faithful and then only after decrypting can I take。

And in the Mac， tear them apart and then check if the message has the right neck。

RightSo that's those are my steps I have to first decrypt whatever the user gives to me or whatever the other person sent to me and then only after I decrypt can I verify that the Mac is correct so I decrypt and then I verify that's the Mac scheme okay so what ends up happening here is that Bob is now forced to decrypt anything right because suppose mallllory goes over the insecure channel tampers with the data and then send it over to Bob Yes Bob is going to eventually find out that the message is taampered with but what does he have to do first he has to faithfully decrypt the cybertext provided by Mallory with the keyK and then only after decrypting can he find out oh this message has an invalid Mac so it's not the right message。

给。So the problem here is that we are giving Maory or anybody using the Insecure channel。

 we are giving them essentially the superpower of giving any message to Bob and Bob has to faithfully decrypt it with his secret key before you can figure out that the message has been tampered with so this creates vulnerab abilitiesities imagine that maybe somehow Mallory can like peek and look at the things that Bob is decrypting maybe now we have just given Maory away to trick Bob into decrypting anything that Mallory wants so if you were kind of skeptical like hey that like superpower that Maory have or you can just trick Alice into encryptpting stuff or trick Bob into decrypting stuff if it didn't seem super like realistic to you。

 here is the case where it is realistic because the only way for Bob to figure out that a message has been tampered with is he first has to faithfully decrypt anything Alice can or Mallory can give any jump anything to Bob and he has to decrypt first before he can find out that the message has been tamampered with。

That's been we've potentially given Mallory the ability to force Bob to decrypt anything and that could be better。

What about decrypted Mac， Why doesn't this one have the same problem Because if you look at the two things being sent which are these two different these of data。

 what is Bob's first step this time this time Bob's very first step is to verify and if the verification doesn't check out he refuses to decrypt So in this case the superpower is gone because Bob is not going to faithfully decrypt anything that is provided to him。

 he's going to check first does the Mac check out on the Cytext or has someone messed the Cyphertext and if that doesn't check out。

 he will immediately quit and say nope I'm not decrypted this and only if nobody is tamper with the Cytext will Bob say okay I want to decrypt and see what it says So the difference between these two if that when you use Mac then encrypt this one up top you're giving someone potentially the ability to force Bob into decrypting anything you can pass in any junk and Bob will decrypted whereas in the encrypted Mac scheme。

 Bob wont decrypt any junk he will only decrypt things that check out first that was a very long winded way of saying。

This stuff agreement so we do not want the attacker to have that superpower where they can just send whatever junk and Bob will faithfully decrypt it because it could potentially lead to further issues okay。

And if you're not convinced well， there are examples out there。

 I don't know if we'll get to them the end of this lecture， but you'll see one in homework。

 there are other examples out there where encrypt or Mac and encrypt does cause problems where we give the attacker that ability to trick Bob into decrypting anything So again。

 both of these do work in theory if you use them correctly they won't have this problem even if Bob can decrypt stuff if you're really careful about it you don't have to worry about that but to me I like encrypt the Mac better because I don't have to think about all that stuff if I use encrypt the Mac I don't have to think about am I giving the attacker a chance to decrypt anything is that a problem like is it okay if I give the attacker that power I don't have to think about any of it if I use encrypt the Mac and I don't like to think about things that are hard so I'm going with the easy one encrypt the Mac。

O。And if you're doing project two or you're doing any sort of cryptography。

 you should go with the easy one too， because we like the ones that are easy。

 we don't have to think about them if we mess up things are still better for us， okay。

Great one last thing I will talk to you about is you might have noticed that through this whole thing I kept using like K1 and K2 so it seemed like I was using two keys why is that does it matter so I'm going to introduce a concept called key reuse and this term is kind of annoying because it pops up like over and over and over again and every time it pops up it's like in slightly different context it's like in project two you'll see key reuse but it's in a slightly different context than this one so key reuse as defined in this lecture and like this lecture only this is like lecture version of key reuse yeah。

The lecture the lecture definition of keyius。I'm going to define lectureversion of key reuse for today as using the same key in two different algorithms。

 so what I mean by that is we've already seen all these different algorithms we've seen ASCBC。

 AES ETR HMAC N Mac we've seen all these different algorithms and they all take in a key and so I'm going to define key reuse today as taking two of those algorithms and giving them the same key okay that's called key reuse for today。

😊，Okay， so for example， if I were to say this K1 and this K2 were the same。

 that's really awkward error， if I choose to use K1 and K2。As the same value here。

 that would be key re that's key reuse because I passed the same k into the encryption algorithm and the same K into the Mac algorithm。

 so same key different algorithms for today is keyares okay。So why might that be a problem？

Turns out that。There's no like formal proof for it， but if you choose to reuse keys。

 you have open up an entire like dimension of the text that you now have to think about because if you pass the same key into two messages or into two algorithms so you could say encrypt k comma N and if you also say like I don't know Mac of k comma N now you have to put your thinking cap on and you have to start wondering things like what if these two algorithms are like both using block Cys I don't know what these algorithms are but like what if one of them is using block Cyphers and the other one is using the block cipher in the other direction so one of them is using block Cys in the forward direction the other one's using blockyphers in like the backwards direction or something。

 could they like somehow cancel each other out and start doing like funny things maybe right or like you know what if the encryption involves I don't know maybe I'll do something like this。

When I have to start thinking like hey， what if the encryption runs the block software in the forward direction and then the Mac runs the block s in the backwards direction and suddenly when I encrypt the Mac each of these schemes by themselves was secure but when I use them together with the same key。

 the block stackpher start like canceling each other out could that happen I don't know I have to think about it or what if like the encryption involved doing some Xor and then the Mac I do another Xer and the Xer cancel out and suddenly like am I leaking things about the message now that I wasn't leaking before。

 I don't know I have to think about it and so if I reuse keys。

 I've open up this whole dimension where instead of thinking of these algorithms like one by one encryption you have the security properties Mac you have the security properties I have to start juggling the encryption properties of algorithm properties and the Mac algorithm properties together I got to think about them both and I got to start thinking is this one gonna cancel out this one if I use them together will they interfere with each other？

Is something going to cancel am I going to leak information that was not lateed when I used one like by itself so I have to start thinking about these things and as you know I don't like to think about things that are hard so if I don't want to think about things in our heart and there's a really simple answer which is just don't reuse keys I use a different K1 and a different K2 I no longer have to think about these problems where the keys like start cancelling each other out or doing all these weird things okay。

So here reuse opens up this huge like dimension of attacks that I don't want to think about and I don't like thinking about them so I'm going to pick the easy way out and I'm gonna say I'm just gonna pick a different key every single time I'm using a different algorithm and well like how do I know when I need to use the different key that kind of depends on your setting and depends on your threat so if you're being really paranoid。

 you can simply just go nuts and reuse all the key avoid reusing keys come up with different keys every time sometimes it might be okay to reuse the key like maybe Alice has two different files that she wants to encrypt maybe it's okay to use the same key to encrypt twice like it is the same algorithms I'm not reusing keys in different algorithms so maybe it's okay to use the same key for two of Alice's different files or Alice wants to send two different messages to Bob maybe it's okay to use of the same key or maybe it's okay to use the same key twice if I'm using like ASCBC or something's possible and so this can't。

Tricky sometimes there's a tradeoff right like if you really want to be paranoid in security aware you can use different keys for everything but now you have to come up with all these different keys and you have to juggle like okay Alice has these like 100 key then which is she going to use this time the giant key ring that she has to choose the right key to use every time but if you choose to use the same key every time it's very simple but now the flip side is you have to start thinking about like am I opening myself up to key reuse attacks am I using the same key for two different algorithms so things can get complicated there's a tradeoff and this is something youll get to wrestle with a little bit in project two where you have to think about what cases is it okay to use the same key twice and what cases do I want to actually come up with two different keys so that I'm avoiding these key reuse problems it's a really tricky question and part of what makes project two so tricky is you have to figure out what keys does Alice have the more key she has the harder it is to keep track of them but maybe is relevant at the security maybe it's not it's tricky but one。

general piece of advice that I'll give that's always true for like Project two like for life is that when you have two different algorithms and by algorithms I mean like AES CBBC AES ETR Hmac NM if you have two different algorithms the safest thing to do is to use different keys per algorithm so you don't have to worry about things cancel in so that one is like basically always true in a safe assumption to make but when you get into more fuzzy ones in project two like can I encrypt the same file with different or like with the same key can I encrypt like multiple files with the same key things can get tricky you'll get to wrestle with it but for this lecture the only definition of keyre that I am talking about today is same key different algorithm and by algorithm I mean HMac CBC and so forth so at least for this lecture and the piece of advice that I'm leaving you with is that if you are using two different algorithms like HMac and AESCBC。

Please use two different keys because that saves you the trouble of thinking of the whole class of attacks where keys get reused across different algorithms in start to like cancel that in a weird ways okay that's all we're saying here but know that you'll get to wrestle with this some more once you get to project two so fun with that okay。

There's a really brief slide on why okay I lied when I said briefly。

 but this is a slide that tells you a little bit about a real world attack that actually happened on Mac that encryptpt'm not going to say it all out loud。

 but here is a case where by using Mac that encryptpt we gave the attacker the ability to pass in anything they wanted any junk and this algorithm was forced to faithfully decrypt that junk with a real secret key and that leaked information that should not have been leaked and actually caused this internet protocol to break okay so that's all we're saying here takeaway is please using encryptry than Mac because it's more robust to mistakes like this even if I made this mistake encrypt and Mac things would not have been as bad but it's kind of old so I don't think this exists anymore but it happened it was bad they had to fix it and now they're an example slide for the rest of time okay。

So that is the first approach to authenticated encryption。

 I take my schemes and I combine them in clever ways。Okay but that is not the only way so as we said。

 there is a whole second approach to doing authenticated encryption and this version is to say。

 well forget those like combining two different schemes like that was so hard I had to think about key reuse I don't like that so I am going to start from scratch I'm going say forget all these other I'm going to come up with a brand new scheme from scratch and I'm going to think about all three things at once。

I want to say my brand new scheme provides confidentiality integrity and authenticity and a single scheme okay you can imagine these are more complicated and we're not going to derive all of them in too much detail but they do exist they are used actually in real life they have a really fancy name and I'm not going to say out loud but basically the idea is that in these schemes I can pass in data and the output gives me both confidentiality which means people cannot figure out what the message was and it gives me integrity which means if someone taamppers with it I will find out in the decryption and verification stage that's really great okay。

Great， and if you were wondering from like a couple weeks ago， hey。

 what were those like fancy magic algorithms from pointer authentication like what were they using they were using fancy stuff like this So now you know。

 okay and yes， these are really fancy they have all using math that like even is kind of incomprehensible to me but you can see yeah。

 they're kind of complicated and sometimes when you use them you have to be really careful and so one drawback that I will note with schemes like this is that well the benefit is what I only have to use a single scheme and I get all three properties at once that sounds great like why would I ever not use this thing I can have one scheme instead of two I don't have to worry about key reuse and I get all three at once like why would I not why would I never or why would I use anything else ever right well there is one problem which is imagine if you use the scheme and you mess up if you use the scheme and you mess up what happens you lose all three potentially so that could be So it's nice in that use a single algorithm and get all three properties。

😊，But the downside of using a single algorithm to give you all three security properties at once is that if you mess up。

 you lose all three at the same time， or potentially all three at the same time。

 which is kind of bad okay。So that's the trade off， which one you like is kind of up to you。Again。

 it's blue， you don't have to know how the scheme works。

 but our takeaway at least is that these schemes are nice because they give you all three properties at once。

 but if you use them wrong， for example you reuse the IV or something。

 you could potentially be in a lot of trouble， okay。

So Ill give you a quick summary and then we'll head out so the first building block we did today was hashes right they took any arbitrary input magnitude to a fixed length output we talked about two security properties that make hashs worthwhile there is a third one called second prehuid resistance that I don't think we're covering the semester but it's there if you're curious and again the rough properties that all of these boil down to is that if you change one bit of the input the output becomes completely unpredictable there is an application that I don't think we talked about the semester either so don't worry about the lowest hash scheme if you're interested I believe the textbook talks about it so it is there if you want it we didn't talk about length extension attacks in too much detail but just know that the length extension attack is like I give you H of M even if you don't know what M is you can actually derive H and M concate it with M prime where M prime is something that you choose and again I promised you that only will give you a bit more practice with that。

As do they provide integrity not really they do want a limited a number of cases like the Firefox case but in general they don't and so we had to come up with something better called Max and this time they take in a key and a message a high level idea behind the one Mac algorithm that we saw called H Mac is that I passed in not just the message but also the key and this funky way and thanks to the proof that is out of scope this funky weight guarantees that message in the key it provides integrity so nobody can come up with a message and a key sorry no one come up with a message in a tag that check out but they don't provide confidentiality we talked about that and then finally we talked about all these different ways to come up with authenticated encryption we talked about how encrypt than Mac is better than Mac than encrypt and we also talked about how you have to be really careful with key reuse at least in this lecture keyuse refers to what it refers to using the same key for two different algorithms if you do that you have to think really hard I don't want to think really hard。

Simply don't do。Cool we finished early so that's it for the integrity section and if you come back on Wednesday I will tell you all about。

You can't start me if you one if you come back next time I'll start talking to you about some of the extra topics down here so that is next time okay。

拜拜。

![](img/23981ee3dd35023bf744f233f084ec0a_3.png)