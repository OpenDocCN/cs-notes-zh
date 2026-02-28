# 《计算机科学教育中遗漏的一学期｜The Missing Semester of Your CS Education 2020》中英字幕 - P9：-09-.Lecture 9_ Security and Cryptography (2020).zh_en - GPT中英字幕课程资源 - BV1Y3yhBHEip

Okay， so let's get started with today's lecture， so today we're going to be talking about security and cryptography。

AndToday's lecture is going to be a little bit different than our treatment of this topic in last year's class。

 so last year we focused a little bit more on security and privacy and from the perspective of a user of a computer。

 but today we're going to focus a little bit more on security and cryptography concepts that are relevant in understanding some of the tools that we talked about earlier in this class so for example。

 we talked about hash functions or cryptographic hash functions like Sha1 in the Git lecture or we talked about public keys when we talked about SSA and the command line environment command line environment lecture。

 and so today we'll talk about those different cryptographic primitives in more detail and get an understanding of how they work and how they're used in these different tools that we're teaching in this class。

This lecture is not a substitute for a more rigorous class in security so there are a bunch of really good classes at MIT like 6858 which is on computer system security or 6857 and 6875 which are more focused on cryptography so don't do security work without formal training in security from these classes or elsewhere and unless you're an expert don't roll your own crypto don't build your own crypto implementations or protocols and the same principle applies to computer system security this lecture is not about building your own stuff。

 it's about understanding what's already out there and so this lecture will have a very informal but we think practical treatment of these basic cryptography concepts。

And yeah， hopefully it'll help you understand some of the tools we talked about earlier in this class。

questions about the plan for today's lecture？Great。

So the first topic for today is something called entropy entropy is a measure of randomness and this is useful for example。

 when trying to determine the strength of a password， so let's take a look at this comic from XKCD。

 we're a big fan of XKCD comics， so this comic raise your hand if you've seen this before。😊。

I have a good number of you， so this comic is complaining about this common pattern that's been taught to users of computers that when you design passwords。

 there should be things like that TR 0， UB4DR Ampersand 3 string in the top left。

Like we should design passwords that are full of funny characters and things like that to make it hard for attackers to guess。

And yet， it turns out that passwords like that are actually pretty weak and guessable by computers that can guess passwords really fast and brute force attacks。

 And on the other hand， passwords which maybe intuitively don't look as secure like the one on the bottom left。

 correct H battery staple。😊，That one turns out to be way more secure。

So how do you actually quantify the security of these different passwords。

 it's by measuring the amount of randomness in the password。

 how many bits of randomness are in there。Entropy is measured in bits。

 this is like the same bits from information theory。And。

We're only going to talk about the simple case where you're trying to measure the amount of randomness when you're choosing from a set of things uniformly at random。

 so for example， when you're constructing a password that's in the format of four random words。

 you're kind of considering all possible sequences of four random words maybe from some dictionary you have。

 you might have a dictionary it would say 100，000 words and you're selecting each word uniformly at random。

How many possibilities are there， Well， you can go and figure that out in that example。

Once you know how many possibilities there are， the measure of entropy is longway two of the number of possibilities。

And as that comic suggests， this is related to how long it'll take an attacker to try to brute force through your different passwords。

 like if you have 1 thousand0 possibilities in you're guessing passwords at 100 passwords a second。

 that's not a very good password。So this is a couple quick examples。

A coin flip has two possibilities。 And let's assume we have a fair coin and so。

A coin flip has log base2 of two is one bit of entropy。

 and another thing we might look at is something like a dice roll。

So theres six possibilities and logways 2 of6 is something like 2。6。Bits of entropy。

So that's how we quantify the amount of randomness in something。

So now going back to that example in the XKCD comic。

 when we want to figure out how much entropyies in a password。

 we have to consider the model for how the password was generated。 For example in the top left。

 you could consider， okay we take one dictionary word。

 make some substitutions of some of the characters with numbers that look similar to that character。

 add one punctuation mark at the end and add one numeral after that and we can take that model and then use commonins to figure out how many possibilities there are。

 and from that we can derive how many bits of entropy in that password so in that particular example I don't know exactly what model they were using for the password。

 but they calculate there are 28 Bs of entropy。Whereas in the bottom left example。

 that correct horse battery staple。They assume that you are working from a dictionary of about 2。

000 words， and so when you combine four of those words together。

 you get about 44 bits of entropy from that， so it's much more secure than the example before it。

So any questions about this definition of entropy or why it's useful？

And so when you're generating your own passwords， keep this in mind。

 you want a high entropy password and the exact number you need depends on exactly what you're trying to protect against like in general。

 a concept in securities you have to keep in mind what your threat model is like what attackers you're concerned about what kinds of technique the attackers might be using。

 So for example， this comic refers to an attacker that can guess a0 passwords a second this might be something that's possible for say a web service that allows people to try to log in with your email and then random passwords that the attacker is trying but this thousand passwords a second model might not be accurate for other scenarios for example。

 an offline password cracking scenario or maybe the attacker has broken into a website and download their database and they have some obfuscated form of your password and they're trying to figure out what the password is。

 maybe they can parallelze this attack and make it go a million guesses a second and so exactly how much entropy you need depends on exactly what you're trying to protect against but roughly 40 bits of entropy might be good enough for a password which is protected by web。

And you're concerned about online password guesses。

And then maybe something like 80 bits of entropy might be good if you're concerned about offline attacks and you want to be really。

 really secure。 So there are rough guidelines you can use。

And then how do you actually generate strong passwords Well you have some model for a password for example for a dictionary words thing and you can actually get a dictionary and then you can use methods like diceware so this is something we link to in the lecture notes where you can actually get physical die and roll them and then map dice roles to dictionary words in order to eventually turn that into a password and doing something like this using some kind of physical token that you know is random like a balanced die or a coin that you know is balanced is a good thing to do because humans are actually not good at choosing random numbers if I just ask you to name a random number for one to 100 chances are that you're probably not doing so uniformly at random very well and so that's why it's actually good to use these physical tokens in order to produce randomness。

So entropy， that's our first concept're coveringing， any questions about that？Or about this comic？

Great， so getting into slightly more interesting and complicated topics。

 the next thing we're going to talk about is hash functions。😊，So hopefully。

 most of you are here during the Git lecture where we talked about the Shaw 1 hash function used in Git。

So now going into that topic in a little bit more detail。

Hash functions at a high level are functions that map a variable amount of data into a fixed size output。

 So， for example， the Shah1 hash functions is one example of a hash function takes in some input of some number of bytes。

And outputs exactly 1，60 bits of output。So that's kind of the type signature of this particular hash function。

 And then these functions have some number of properties that are useful。 So at high level。

 these can be thought about as。hardd to invert functions that have random looking outputs。

 We can actually try this out on some random piece of data。For example。

 if I enter into my terminal print F hello， this does exactly what you would expect it does。

Prince this out to standard out。 and I can pipe this to the Sha1 sum command。

 So this is a command line program that accepts input via standard in and compute this Sha1 function。

 which takes in some variable number of bytes from the input and produces a 160 B output。

 which in this particular case is represented encoded as a hexadecimal string。

 So it's a length 40 hexadecimal string， And you see this output right here。

 This dash just means it took its input from standard in。



![](img/47dd9fa98180a0011233671715eabb0d_1.png)

![](img/47dd9fa98180a0011233671715eabb0d_2.png)

![](img/47dd9fa98180a0011233671715eabb0d_3.png)

So this output just looks like some random number， but one important thing is that this is a deterministic number。



![](img/47dd9fa98180a0011233671715eabb0d_5.png)

If you try the same command on your own computer， print F hello Shao 1 sum。

 you will get the same number out。 So Shao 1 is some wellknown function that people have agreed upon for all its parameters。

 We'll see that if we tweak the input a little bit， like， say change hello to hello with a capital H。



![](img/47dd9fa98180a0011233671715eabb0d_7.png)

Now we get a completely different looking output， and this also looks like some other kind of random issue number。

 even though it is deterministic and you could reproduce this on your own computer。



![](img/47dd9fa98180a0011233671715eabb0d_9.png)

Hash functions have a number of properties that are pretty important。

The first property that cryptographic has functions have is that they're non invertible。

 And what that means is that if you take the output from this function， for example。

 that A A F for blah， blah， blah， 3，4D string shown there from that output。

 it's hard to figure out what the input was that produced that output。So you can go one way。

 compute the Sha one hash easily， but you can't go backwards。

Another property that these functions have is that they're collision resistant。

And what this property means is that it's hard to find two different inputs that produce the same output。

And so this basically describes what a cryptographic hash function is。

So any questions about the kind of specification of a cryptographic hash function？Okay。

 so what are these hash functions actually useful for。

 but we've already seen one application in Git for content address storage。

 so in Git we want some uniform way of naming different objects that are in the object store and it turns out that Git addresses all of them by their Shao One hash so you have the actual data you want to store。

And then to name that particular piece of data， you just name the Shao1 hash。

 and all of that is stored in the object store in that particular way。

We see this when looking at many different parts of Git， for example， right here。

 I'm going to git repository， if I do git log it shows me the commits， and for example。

 this number up here is the cryptographic hash function Shah1 applied to the commit object that describes this particular commit。

So does anybody know why Git uses a cryptographic hash function here as opposed to。

 so you might have heard in your other computer science classes like say。

 your introductory algorithms class， there are things called hash functions without the word cryptographic appended in front of them。

And they have similar properties that they turn a variable sized input into some fixed size output。

But they don't quite have these properties where it's hard to find an input that produces a particular output or things like that。

 it's a kind of weaker definition than this。 So why is it that in Git。

 we care about having a cryptographic hash function as opposed to just a regular old hash function。

 Does anybody have any ideas。Yeah， that's that's basically it that we don't want to have kind of conflicts in the output from this hash function。

 like every commit is identified by a hash function。

 Every file is identified by the hash of that file。 If it were ever the case。

 that two different pieces of content in practice produce the same output。 That is。

 if the function were not collision resistant。 That could be really problematic， right。

 because then you and I， we could have two two git repoos that we think are the same。

 We check out the same commit hash。 and we might end up with different files。

And this is concerning because Git is used to track software， track development of software。

 and it's also kind of involved in making sure that the right people are authoring the software。

 nothing funny has happened in the process。 for example。

 there are all these open source projects like the Linux kernel where development is done using Git。

 It'd be really bad if some contributor to Git could say edit some file and propose some change that looks pretty benign。

 Like let me go and improve this part of Linux。 submit that change request to the Linux developers And then in practice。

 actually supply a Git repository that has the same commit hash and whatnot。

 but actually the file contents are different。 there's something malicious。

 So Git actually relies on。This Sha1 function being a cryptographic hash function in order to achieve security。

Any questions about that？And some other interesting applications of hash functions。So as we saw。

 hash functions turn big inputs into small outputs， and in a way。

 because the hash function is collision resistant， the output can be used to kind of attest to or identify the input。

 and so you can think of a hash as a short summary of a file。For example。

 in this directory I have a bunch of files and I can compute the Sha1 sum of some file in this directory。

 and this is the Sha1 algorithm applied to this readmeet。md file。

And what's interesting is that it is computationally hard or impossible。

 you can kind of think of it as impossible to find any other file to a different file that has the same hash output and one scenario in which this is useful is when you download files from the internet。

For example， there are lots of Linux distributions that distribute large CD or DVD images from their website。

 like I can go to Debion。org and download the latest version of Debian。

The thing is that hosting those files can be expensive and so a lot of people are nice enough to host mirrors of these files。

 so instead of downloading Debian from Deion。org， I can go to one of many other sites and download what are supposed to be the same files that are hosted at Deion。

org， but how do I know that I actually got the correct file？

Like what if I set up a malicious mirror and you go to like Anishsha's evilvildeian websiteite。

com and then try to download Debbie and turns out that your Linux installation is backdoored。Well。

 one thing you could do is download a copy from the original Debian website and then download my version and compare them。

 But that kind of defeats the purpose， right， because we want to avoid downloading things from Debbian do org because hosting these files is expensive。

 And we want all these different people to be able to mirror copies of the files elsewhere。

So does anybody see how cryptographic hash functions could be useful to solve this problem。

 that I want to download a file from an untrusted source？

But and not from like the trusted source itself， but maybe I can get some small piece of information from this trusted source in order to know whether the file I downloaded from the untrusted source is the thing I was supposed to get。

嗯。Yes， like it's basically just a straightforward application of cryptographic hash functions。

 So what Debbian do org can do is they can produce their of correct IO file or whatever they want。

 And instead of publishing the file itself on their website， they can publish a hash of that file。

 So compared to the file itself， which may be many gigabytes。

 this is only like in this particular case，160 B of data right So very cheap to host。

 And then what I can do as a user is I can download that file from any random website。

 it could be an untrusted website。 And after I download it， I just double check the Shaoan hash。😊。

And if the hash matches。Then I know that I have the right file because it's computationally infeasible for somebody to give me some different file that happens to have the same hash because hash functions are collision resistant。

So any questions about that application，And why different people are hosting the same information you like。

Expener。First person the host。And are different people host？That like。Yeah。

 so that's a good question Like why do you need different people to host the information like wouldn't it be equally expensive for everybody So the answer to that question is a little bit complicated。

 but like here's a partial answer。 One thing is that downloading files from a server is affected by how far away the server is from you。

 So for example， if the servers in Massachusetts and you're in say China you have to make a big round trip across the internet and that may be expensive for a number of reasons like the latency is high and the traffic needs to go through lots of different wires to make its way all the way to where you are And so one thing that these websites do is that they distribute their content to servers that are all over the world。

 and then as a user you download from the server that's closest to you like for example。

 MIT maintains Debian package repository and mirrors all the Debian stuff。

 So if you're a Debian user at MIT you can use the MIT copy of everything。

 and then you can kind of access it over our fast local network and that traffic never needs to go to the outside Internet at all。

 so it's very fast。That's a good question， Any other questions？Okay。

 and then one final kind of interesting application of hash functions is something called a commitment scheme。

 so。I want to play a game， and I need a volunteer for this。

 So you don't actually need to get up from your seat or anything。 I need you to talk with me。

 So any volunteers raise your hand。 Yeah， okay， what's your name， Abduliz， great， So Abdul Aiz。

 we're going to play a game， we're going to play a game where I'm going to flip a coin and then you're going to call heads or tails。

 and if you call it right， you win and if you call it wrong， you lose。

 And there are no stakes for this game。 but just the pride of winning。 so。😊，Sadly。

 I checked my wallet， and all I have is dollar bills。 I don't have any coins with me。 So instead。

 I'm going to just flip the coin in my head。All right， so okay， I flip the coin， call heads or tails。

Sorry， you lost， it was heads。I you want to play again。's right。I can cheat， right。

 I can just see what you say and say the opposite thing。 So let's try fixing this game。

 How about you call heads or tails after I say what the coin flip result was。 Okay， Yeah。

 So if I say， oh， the result is tails， what are you gonna say。Or you calltails yeah。So。

Is it possible to play this guess what the coinin fliplip result is game in a fair way without having a physical coin that we share like because I can't really manipulate your physical reality if I flip a coin in front of you。

 you probably trust that it's okay， right？So it turns out that hash functions give us a kind of cool way to solve this problem。

 too through an idea called a commitment scheme。 So I can say here's the construction of the solution。

😊，I can pick heads or tails， and I'm actually going to pick a big random number。

Say like this number here。 And what I can do is compute the。Shaaw wants sum of this number。

 at this moment， you haven't seen this number yet。 I'm just doing all this in my head。

And then what I do is I tell you， okay， I flipped a coin and I'm not going to tell you what the result is just yet because you haven't called heads or tails。

 but I'll tell you what the Shaw one sum of the result is。 Here you go。 And I tell you this value。

 Now， after this， you can call heads or tails。 So what do you say， like say you say heads。Afterwards。

 what I can do is I can reveal to you what my input to this function was。

And then you can crossche this right， you can compute the Sha1 sum on the input to verify that the output is what I said it was earlier。

 and then we can have some way of mapping these numbers to heads or tails so I might have agreed upon beforehand that even numbers are heads and odd numbers are tails and so this is a way of fixing that game so we can actually play this game in our heads。

 right？I can pick a value， but not reveal that value to you， but I can commit to the value。

 So this is a kind of binding commitment scheme that I can't change my mind after I've told you this。

 but it doesn't reveal the original value to you。And so this is one other neat application of cryptographic hash functions。

Any questions about this particular construction？Okay， great， so moving on to the next topic。

We're going to talk about key derivation functions。Often abbreviated as KdFs。

So this is a concept that's very similar to hash functions。

Except it has kind of one extra property that it is slow to compute。For example。

 there's a hash function， a key derivation function known as。Yeah。PBKDF2。P B， K， D。

 F to password base key derivation function 2。That has a kind of similar form as these hash functions we were talking about here。

 that they take in some variable length input and produce a fixed length output。

 but they're meant to be used for one particular purpose。

 the purpose is generally to use the fixed length output as a key in another cryptographic algorithm and we'll talk about those algorithms like what you use the output of this thing for in a moment。

😊，But one property of these things is that they're slow。Does anybody have any idea why you'd want？

An algorithm to be slow， like normally you want algorithm to be fast right。

 So why would we want an algorithm to be slow， Yes。

 because if someone has the database all the hashes and they're trying to brute force it。

 like then they'll have a hard time whereas like if someone types in their right password you'll need if be rank once。

Yeah， that's exactly it。 So I'll repeat。 So it goes into the microphone。

 The reason you want these to be slow is when you're actually using it for something like password authentication。

 where you have the hash of a password saved and then somebody inputs the password。

 you want to know if that corresponds to the hash， it's okay if it's slow because you're only doing this check once。

 But the other scenario in which you're going to be using this function is when somebody's trying to brute force a password。

 say a website has their password database stolen and somebody's going through all the accounts and trying to break all the passwords。

😊，Well， in that case， you want this to be slow because someone's going to be doing this like millions and millions of times。

 and you can slow down the attacker a lot by making this function slow。

 And so it's fine if this takes you like one second upon logging in to compute this function。

 But when you're brute forcing it， we don't go at100 guess a second， like in that XKCD comic。

 we can slow down a little bit。😊，So what is the output of key derivation functions actually used for？

Well，The next topic we're going to talk about。Probably like one of the most classic things when you think about cryptography is encryption and decryption。

The next topic is symmetric key cryptography。嗯。Like the rest of this lecture。

 we're not going to talk about how you implement these。

 We're going to talk about the API for symmetric symmetric key crypto， like how it's used。

 So symmetric key crypto systems have a couple different functions。

They have a key generation function， which is a randomized function that produces。

A thing we call the key。And then they have a pair of functions encryptpt and decrypt。

And Enrypt takes his input， something we refer to as the plain text。

And this is just some sequence of bytes， some data。 and it takes in a key。

 So something that came as an output of this key generation function and produces。

What we call the ciphertex， and then decryptse does the opposite of this。

 so it takes the cipher textex。Along with the key and produces the plain text。And。

This triple of functions has a couple properties。One is that。

Like one thing you might expect is that this thing doesn't really tell you all that much about this input to the end group function。

 So property number one is。Given the ciphertex， you can't figure out the plain text。Without the key。

And the other property is kind of the obvious correctness property that if you。

Take something and you encrypt it。Some message M with a key K。

 and then you decrypt that cipher text using the same key。That gives you back the same message。

This is just the kind of obvious correctness property。So does this description make sense。

 does it fit your kind of intuitive understanding of taking some piece of data and obscuring it so you can't really tell anything about the original input。

 but then taking that obscured result and then passing it through some decryption function given that key to retrieve the original input。

And this isn't really a rigorous definition of what it means for something to be secure。

 but it's a good enough intuitive definition that we can work with it。嗯。

So any questions about that description there？So where can symmetric key cryptography be useful？

 We'll talk about a whole bunch of examples later in this lecture。

 But one example we'll talk about right now is encrypting files for storage and an untrusted cloud service。

So consider， say something like Dropbox or Google Drive or things like that。

When you upload files there， you're trusting the service to not look at your files or do anything malicious with them。

These services like at least the ones I named are not Nend encrypted or anything like that。

 Like in theory， any employee those companies could look at your files。 Now。

 of course these companies have lots of policies and technical controls in place for making sure that that sort of thing doesn't happen。

 but that doesn't mean that it's not technically possible。

 And so one thing you might want to do if you don't want to trust these cloud services to not peek at your data。

 not do like machine learning over them or do other sorts of things that you wouldn't really want is you can just take your files and encrypt them before uploading them to these web services。

So does that idea make sense that I can take my file， likeing pictures or whatever。

 pass it through an encryption function， produce a cipher textex and then place that cipher textex on the web service。

 say for backup purposes or whatever， and if I ever need that I can retrieve the ciphertex。

 then use my key to decrypt it back into the plain text and they can use the result for doing whatever I need to do Does that make sense？

Yeah。Also run it through the same。Yeah， so that's a good question。

 The question is couldn't anybody else run it through the same encryption program？One detail。

 maybe I should have explained in a little bit more detail。

 is this key generation function is randomized。And this key has high entropy。

 So going back to that topic we talked about earlier。 So like an example is we might have AE S 256。

This is one particular symmetric cipher and this， as the name might indicate， has 2。

56 bits of entropy in the key。 And so that means that as long as the attacker。

 like whoever downloads the cipher text from the web service。

 doesn't know your key unless they have some better attack in place。

 they'll have to try all the different possible keys。 And if there're two to the 256 keys。

 that's too many keys to try in a reasonable amount of time。Does that answer the question， Great。

 Any other questions？Yeah let's。Mike key， how can I be with that？My heart laptop died。

 everything in the cloud when I down to his bed。randomize how can I be That's an excellent question。

 And that leads into what I was going to talk about next。 So thanks for that question。

 So as you point out。Like if I lose my key， I'm kind of stuck， right， I need my key to decrypt。

 That's kind of the point of this thing。 Like if I didn't need my key to decrypt。

 then this wouldn't be a very good crypto system。 And so I can combine this idea of symmetric key cryptography with the topic we just talked about key derivation functions。

So instead of having some key that's randomly generated with my key generation function。

 say sampling entropy from somewhere on my machine， I can have a pass phrase。

And pass it through my key derivation function box。And this gives me my key。

And then I can take my plain text。And combine it with my key in my encrypt function。

And this produces my ciphertex。And I store this cipher textex on the web service。

 but now I don't need to save this key instead I can just remember my pass phrase and whenever I need my key。

 I can reconstruct it from the key derivation function question is the key derivation function slow。

这。I guessing different past races because I'm assuming your past races。Yeah。

 so that's a good question。 The question is， is the key derivation function slow enough to prevent brute force guessing And the answer is it depends on how long your passph is So for example。

 if your passph is like the string password is probably going to get broken very quickly。

 But as long as there's enough entropy in your passph this is good enough。

 So like if I was uploading something to Dropbox and I really want it to stay secret。

 I think like a 64 bit passph or like a passph with 64 bits of entropy would be more than enough in that scenario。

 for example。And just a quick demo of this。 So there are tools to make this really easy to do。

 This is actually one of the exercises。But we can take a tool， for example。

 called open SSSL and use it to apply a symmetric cipher to some file。

 So I had my readme dot text here， for example， readme。MD it has a bunch of stuff in it。

 and I can do open SSSL AES 256 CBC。 This is the name of a particular symmetric cipher。

And I can say that I want to apply this to readme。 Md and produce readme。 end domd。

 let's give it some name and then it's asking me for a password so by default this works in this mode where I provide a password phrase。

 it's run through a Kd I have to produce a key and that's used for encryption so I'll type in some password type it in again and now I produce this readme。

 end。M file and if I look at this。It kind of looks like garbage。 And that's at a high level。

 the point of a symmetric cipher。 It produces some cipher text that should be kind of indistinguishable from random data。

And when I want to decrypt this， I can run similar command， open SSL E S 256 CBC， D for decrypt。

Take the input from readme do do MD， and I'll do like readme dot。Read do decrypted。md is the output。

And I can compare these two files。And the correctness property of symmetric cryptography tells me that this should be identical。

 and this indeed is identical。 If I look at the return value， compare return 0。

 so that means they're the same file。So any questions about symmetric T cryptography，いう？

Everything you had in the file with this new stuff， it's not like it made a new。

So this particular command did make a new file， so it took as input， Readme。

md and produces output this file， so that is the encrypted version of the file。

 it left the original untouch， but then of course I could delete it if I wanted to。Yeah。

I said that you've provided。まあ。where is the all starting？That's a good question。

 this is something I wasn't going to talk about in too much detail。

 but the question is I provided the salt argument here and where is that stored。

 so the answer is that that is stored in this output here。

So this output format stores both the salt and the actual output cipher text。

 so it can be used in the reconstruction and decrypt。So it doesn't keep any data that salt used for。

Yeah， that's correct。 It doesn't keep any database or anything。 This is fully self contained。

The salt is done。Yeah， and as John says， the salt is not the secret。

Like the pass phrase is what is the secret thing here？あまテし。Okay so。

Let's go back to- so the question is， what is salt？The idea of a cryptographic salt。

Is probably best explained in the context of hash functions。

So one common application of hash functions is to store passwords in a password database if I have a website and I have logins for users like people log in with their username and password。

I don't actually want to store people's passwords in plain text， just like as is。

 does anybody know why I wouldn't want to do that？Yes。😊。

Exactly what if there was a breach and someone got all your data so it's really bad if you leak all your users' passwords it's especially bad because a lot of people reuse their passwords across different sites。

 so you'll see attackers break into one thing like there was a big Yahoo breach a while ago and they find all these username and password pairs and then they go and try those same login credentials on Google and on Facebook and on YouTube and whatnot because people reuse passwords。

So it's bad to store plain text passwords。So one thing you should do is you should store hashed passwords with a hash function or ideally a password hashing function that's intentionally designed to be slow。

But one thing attackers， one thing attackers started doing once they realized that people started storing hashed passwords is they built these things called rainbow tables。

 What people did was they took。way of generating big password lists like they kind of model what passwords might look like。

 say take all the dictionary words， take all strings of like length from0 to 8 and whatnot。

 take all of those and then hash them and produce a big database mapping hashes back to their pre-image and so given the output of a hash function rather than have to brute forceeset on the fly。

 you can just go look up in this database oh what is the input that corresponds to this output and people have built these for reasonably large password databases。

And so one thing that you can do in reaction to that as a defense is rather than storing in your database。

 let see where to write it。Rather than storing just the hash of the password。

What you do is you compute what's called assault value。And what this is is a large random string。

And then what you do is you store in your password database。The salt， which is not really secret。

 like you can store this in your password database， along with a hash of the password。

With the salt appended to it。Why is this useful， well this salt is a random unique value for every user。

 and so if someone has the password， say password 1，2，3 on one web service。

If you were just storing the hash of the password， then the hash would be the same on both web services right because this hash function is a deterministic function。

 but now since we're using this randomized salt value。

We store the hash of the password plus assault salt。

 and so even if someone's using the same password on multiple sites。

This thing looks different in both cases， and it makes it so these big databases。

 mapping these short passwords or hash outputs to the short passwords that they came from。

 those are no longer useful when you have salted passwords。

You kind of need to do the brute force attack for every user once you find their salt value rather than being able to use this big precomputed database。

 Does that answer the question of what assault is。And so that's what that salt argument is related to。

Let's see。So any questions about anything we talked about so far？Great。Okay， so the。

I'm going to go ahead and erase this and then the last。

Topic we'll talk about is one of the most exciting developments of cryptography happened quite a while ago。

 but it's still a really cool concept， something called asymmetric key cryptography。

And so this is an idea that actually enables a lot of the security and privacy related features of basically anything you use today。

 like when you go and type in like www。google。com， asymmetric key cryptography is used as part of what goes on there。

So this is going to look pretty similar to what we talked about in symmetric key cryptography。

 except with a twist。There's a key generation function which similarly is randomized。

 but instead of producing a single key， it produces a pair of keys， two different things。

One of which is referred to as a public key。And the other is referred to as the private key。

And then these can be used for encryption and decryption in a manner kind of similar to symmetric key crypto。

 except these different keys have different uses now， So we have an encryption function。

It takes in the plain textiles right P here， and it takes in the public key。

And produces the ciphertex， and then I have a decryption function。

WStakes in my cipher text and the private key。And gives me back my plain text。

And then similarly to those two properties we had over there。Given just the ciphertex。

 we can't figure out the plain text unless we have the private key and then we have the obvious correctness property that if we encrypt something with the private key encrypt something with the public key and then take that ciphertext and try decrypting it with the corresponding private key that came from this key generation process that outputs these two different things at once。

 then I get the same result back。So。This is very similar to what's above。

 but there's a twist that we have these two different keys that have different functions and it's really neat that this public key can actually be made as the name indicates public。

 like I could be using a crypto system that works like this。

 post a public key on the internet for anybody to see but keep my private key secret and then I have this interesting property that anybody on the internet can take any piece of content and encrypt it for me using my public key and send it over the internet to me and then I can decrypt it using my private key and as long as my private key stay secret。

 it doesn't matter if my public key is available to anybody on the internet so here's where this asymmetry comes from。

Before we were in a scenario where suppose I was on the internet。

 but you weren't like talking to me face to face， and you wanted to send me some data over the internet over some。

Unencrypted channel where anybody could listen on what you were saying。

 and you wanted to use symmetric key cryptography， well。

 we'd need some way of exchanging a key in advance so that you could encrypt some plain text with a key and give me that ciphertext over the internet so that then I could then decrypt it with that key。

In symmetric key crypto， if the key's public， it's game over， like anybody can decrypt your stuff。

Whereas an asymmetric key cryptography， I could take my public key and post it on a bulletin board on the internet。

 and you could go look at that， take some content and encrypt them for me， and then send them over。

 and that would be totally fine。 You can only decrypt it with the private key。

And so one analogy that may be helpful is comparing these mathematical ideas to physical locks so you probably have a lock on your door to your house and you can put in a key and like turn the thing in order to lock the door or you can turn it the other way to unlock the door So there's a single key and it can both lock and unlock the door。

 But now consider this alternative construction which you might use if say I want you to be able to send me a message and I have it be sent over the internet and I don't really need a way to exchange a key with you beforehand I could get a box which you can put a letter inside and you can close the box and I can get one of those padlock things which I can give you I could take this padlock and open it and give it to you and at your own leisure。

 could put your message inside a box and take this padlock which is open and shut it around the box and then send it over to me and then I could put in my key and unlock it So do you see how there's this asymmetry there as opposed to the key that I used to open the door to my house where the same key opens and close the thing Instead I give you this。

Open Palock that you have the ability to close but not open。 and after you close it。

 I can use my key， which I've kept secret in order to open the thing and retrieve what's inside。

Maybe this analogy is helpful， maybe it's not the mathematical construction works just fine if that works for you。

So any questions about。Asymmetric key encryption and decryption and how it relates to symmetric key crypto。

 how it's a little bit different。So before we talk about applications of this idea。

 I'm going to talk about one other set of concepts in asymmetric cryptography。

 so these crypos systemsems give you another set of tools which are related to encryption decryption。

 something called signing and verifying and this is kind of similar to the real world like I can get a document and sign it with my signature except real worldord signatures or I don't think that hard to forge。

 these are pretty hard to forge and therefore more useful。What do signature schemes look like。

 there's a function sign that takes in some message。And the private key。

So notice this is the private key， not the public key， and it produces a signature。

And then there's another function， verify。Which takes in the message。The signature。

And the public key this time。And it tells me it returns to Booley and whether or not this signature checks out。

And then this pair of functions。Has the property that， again， these are。

Kind of properties that follow the intuition that come from physical signatures。That。

Without the private key。It's hard to produce a signature for any message such that you can give the message in the signature and the public key to the verify function to get it to return true。

 Like at a high level， it's hard to forge。It's hard to forge a signature， of course。

 without the private key。And then there's the obvious correctness property。

That if you sign a thing with a public key and then try verifying it with the corresponding sorry。

 you sign a thing with the private key and try to verify it with the corresponding public key。

 it returns， okay， that the verification checks out。

So these are two different kinds of things you can do with。Asymmetric key cryptoysems。

An example of an asymmetric key crypto system that you might have heard of is something called RSA。

So RSA is designed by a number of people， one of whom is Ron Ruve， who's a professor here。

So there are a couple interesting applications of asymmetric key crypto actually like tos and tons and tons and we can spent like days talking about this。

 but a couple examples are email encryption so we talked a little bit about sending messages。

 what we can do with asymmetric key crypto is that you can have public keys posted online。

 I think some of the instructors have PGP public keys on their website So for example。

 you go to my website or John's website， you'll find a public key and then what you can do is you can send us an encrypted email And so even if that message goes through Gmail or whatever other mail service through MIT's mail service if there happens to be an attacker snooping on the messages。

 they can't make any sense of their contents because they're all encrypted。

And this is really cool because you can do this without kind of。

Finding us in person and exchanging keys， which you might have to do in a symmetric key crypto system。

 you can just find our public key， which can be posted online without causing any issues and then send us encrypted email。

Another thing asymmetric key crypto is used for is private messaging。

 so raise your hand if you've used anything like signal or telegram or I think WhatsApp is in theory endend encrypted。

 so a good number of you。These private messaging applications also use asymmetric key crypto to establish private communication channels。

 basically every person has associated with them a key pair。

 and so your device has run this key generation function。

 produce a public key in a private key and automatically posted your public key to the internet。

 So for example， if you're using signal， your public keys on the signal servers And then when someone wants to contact you。

 their phone can look up your public key and once it's retrieve your public key。

 they can encrypt information for you。 This is a kind of approximation of how their algorithm works。

 but at a high level， that's what's going on。Another neat application of asymmetric key crypto is。

We were talking about earlier， like making sure you have the right software we downloaded from the Internet。

 Asymmetric key crypto can be used to sign software releases。 And this is something that people do。

 for example。Like Deian packages or whatever things you download from the internet。

 the developer will try to sign their software so that you can make sure that whatever you've downloaded from the internet is actually the right thing that came from the right person。

we talked about in the Git lecture， all the interesting things you can do with Git。

 one thing we didn't cover was signing related functionality in Git。So。Git has commits。

 and you can associate with commits something called tags at a high level。

 You can basically take a git commit and attach a signature to it。

 which binds your public key to this commit。 And then anybody who has your public key can take the commit and your public key and make sure that there's a legitimate signature on the key or sorry。

 on the commit。So let me go to some random repository that I have。

I can look at a bunch of tags associated with this repository if I do。



![](img/47dd9fa98180a0011233671715eabb0d_11.png)

![](img/47dd9fa98180a0011233671715eabb0d_12.png)

Look at the raw data associated with this tag。It has some metadata and then a blob of like ASI encoded information。

That I can use the Git tagag V for verify command。To make sure that， oh。

 this is a good signature from this person who happens to me。

 So I sign the software release so that anybody who downloads it from the Internet can make sure that they actually got an authentic copy。

Yes， question。Checking again。ですね。So the question is。

 what exactly is the verify function doing or what is it checking against？嗯。

The like if you want to know mathematically what's going on， talk to me after this lecture。

 But for from kind of an API perspective， what's going on here is that the signature and also the message here are just a blob of bytes。

 And it happens to be the case that these things are designed， such that。Basically。

 if I take for some particular public key， like if you take my public key。

 it's impossible for you without knowledge of my private key for any message to find a second argument to this function that makes it return true。

You can kind of compare it to signing a document like you don't know how to forge my signature。

 I can take any piece of paper and sign it， and then anybody who knows what my signature looks like。

 I can show my document to and you can be like  yeah， that checks out。

 but nobody without the private key can produce a signature that will make this function return true。

For any particular message。Any related question strategy do you want me to explain in any other way or does that make sense？

嗯。So any questions about signing softwareft or any of the other handful of applications talked about of asymmetric key cryrypto？

Cool， so one final thing I want to talk about or almost out of time is key distribution。

 So is a kind of interesting side effect of asymmetric key cryptography。

 It enables a bunch of interesting functionality like I can post my public key on the internet。

 you can go find it and send me encrypted email， but how do you know that the public key you found is actually my public key。

 It seems like there's a bootstrapping problem here right？

So there are couple- this is like a really interesting and really hard real world problem。

And there are a couple different approaches you might take to this problem。

 One is kind of a lame solution but this thing solves a lot of cryptography problems is exchange the information out of band。

 What that means is you want to send me encrypted email well just talk to me after class。

 I'll give you my public key on a piece of paper and since you were talking to me in person like you know that it's actually my public key not just somebody like hack to my website and stock some random number on there。

That solves the problem， but it's not the most elegant。

 There are a couple other approaches that different applications use。

 So those of you who who use signal。 Have you ever encountered the phrase， like safety number。

 like verify your safety number with so and so， so。With signal。

 they have a way of exchanging public keys， which is through the signal servers。

 whoever runs the signal service， just maintains on their servers basically a mapping from phone numbers to public keys and then when I say。

 oh I want to message this person with this number。

 my phone just goes and retrieves their public key from the internet and then encrypts the message for that public key Now does anybody see a problem with the setup？

Yeah。You could accept like signal servers are。Yeah。

 exactly the signal servers are a point of failure there because if the signal servers give me the wrong public key。

 like suppose signal just produces a new key pair and give me their public key。

 now they can read all my messages and they could even sit in between and transparently decrypt the messages I send them and then reenrypt them and send them onto their final destination like basically I need some way of authenticating the public key I get。

And so Sign has one solution to this which is also just kind of punting the issue to out of band key exchange。

 you can meet up with somebody and they have a slightly streamlined flow where they show QR codes on the screen。

 you take one phone， take a picture of the other phone screen and vice versa。

 and now you've exchanged public keys in person and from that point on。

 you've bootstrappped your encrypted end to end communication。

It issue also has an approach of pinning a public key。

 so once you know that a particular phone number has a particular public key。

 your phone remembers that and if that ever changes， it'll complain to you。

And then there are a couple other solutions to this problem。

 PGP one Too that used to be popular a while ago has this idea of web of trust。

 So like I trust people who my friends trust。 So if like John has done an out of band exchange with say my professor。

 then I can probably email my professor because I know that John trust my professor and I trust John。

 So you get this chain of trust through there。 That's one interesting approach。

 And then another model that's kind pretty recently is something that a tool called Keybase uses。

 This is really neat。whoops。There's a website called Keyb。

Io and they have a really interesting solution to this bootstrapping problem， which is social proof。

So it's saying you probably have your friends on Facebook and on Twitter and whatnot。

 and it's probably pretty hard for an attacker to break into your friend's Facebook account at the same time as their Twitter account as the same time as their hacker news account and so on。

 and so they have this interesting way of binding public keys to a set of social identities such that you can retrieve a public key once you trust some number of social identities corresponding to your friend。

Since we have links to these in the lecture notes， if you want to see these things in more detail。

So that's it for our security and cryptography lecture。

 and tomorrow's lecture will be on a random collection of topics that your instructors find interesting。

 so hopefully see you in lecture tomorrow。I'll also be here for a couple of minutes after class。

 if anybody has questions。W animation Can you talk about why how asymmetric key crypto is slow and symmetric key crygo is fast and how you bridge them Yes okay。

 so John， feel free to leave if you have to leave， but I think nobody's using the classroom after us I'm going to talk about one other interesting topic。

So John brought up the fact that asymmetric key cryptography is slow and symmetric key cryptography is fast。

And so in practice， you don't really use just asymmetric key cryptography by itself。

 it's usually used to bootstrap。A more sophisticated protocol that you're using。

One thing you might want to do is use asymmetric key cryptography for signing encrypted email。

 right we talked about that example， and the way that works isn't what you might have guessed from our straightforward explanation of asymmetric key cryrypto。

 like you don't just use that encrypt function out there and call it a day。In practice。

 what you do is you use hybrid encryption。To use a combination of symmetric key and asymmetric key cryptography。

What you do is here， I'll draw this as a big block diagram。 You take your message M。

 and then I have my public key。That I want to encrypt for。

 But rather than just take these two things and pass it through the encrypt function up there。

 what I do is I use the symmetric。Keygen function to produce a symmetric key。

I'm going to preend this with symmetric so we can distinguish it from the public key generation function。

And then what I do is I take these two things。Passed them through my symmetric encryption box。

This produces the ciphert。And now this by itself， to the sender sorry， this by itself。

 to the receiver who has the private key corresponding to this public key here。

 This is not really useful， right， because this is encrypted with a symmetric cipher with this key K。

That came from this function that I ran on my local machine。

 So I need some way of getting this to the person who actually needs to decrypt the email。

 And so what I do is I take this thing。AndNow this email might have been big。

 and I use symmetric encryption with that because symmetric encryption is fast。

 but this key is small， like it might be 2，56 B or something。

 so I can take this thing and encrypt it with a symmetric encryption using the public key。

And this gives me an encrypted key。And this thing can be decrypted using the private key corresponding to that public key to reconstruct this。

So this is on the sender's end Now the receiver gets this and this and kind of does these things backwards。

 So you start with the encrypted key。And use asymmetric decryption using your private key that corresponds to the posted public key to reconstruct this key that we use for the symmetric encryption box and then use symmetric key decryption using that key that was reconstructed to take this ciphertex and produce the original message。

This is a kind of interesting example of how in practice。

 symmetric and asymmetric key cryptography is combined。Question，たす？So the question is。

 will you be using the same symmetric key generators？Yes， okay。

 so you need to kind of agree ahead of time which box you're using here so you might be like， oh。

 I'm going to use AS 256 GC out in here。But this is a well known function and it's public。

 like the attacker is allowed to know all the parameters of this function。

 This is the only secret thing that the attacker doesn't know， the key。Any other questions？Yeah。

なんでです。That's a really good question， what kind of data is important enough to encrypt？And。

I think that depends on your threat model， like what kind of attackers are you concerned about。

 what are you trying to protect against？So。You might have the stance that you just don't really care。

 And that like anything you communicate with anybody is allowed to be public。

 I might be willing to like post all my conversations with everybody for。

Everybody is the publicly on the internet， on the other hand。

 maybe you're doing some like security sensitive works here you're working under a contract for the US government developing some sensitive military stuff。

 if you're sending that through the open internet while you're traveling。

 you probably want to be pretty darn sure that no eavesdroppers or anybody else along the way can see what you're sending and that whatever you're sending is in fact going to the right place and that whoever is receiving it can authenticate that it in fact came from you。

So you might be worried about all different kinds of adversaries depending on your scenario。

 from random scriedes who are trying to break into websites to nation state level attackers。

 and you'll need different types of techniques for defending against the different categories of attackers。

Any other questions？Co， so hopefully see some of you tomorrow for a random collection of things that John Jose and I find interesting。

