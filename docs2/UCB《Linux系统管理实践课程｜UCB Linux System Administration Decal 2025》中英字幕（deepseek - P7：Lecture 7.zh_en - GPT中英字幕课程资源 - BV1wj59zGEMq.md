# UCB《Linux系统管理实践课程｜UCB Linux System Administration Decal 2025》中英字幕（deepseek - P7：Lecture 7.zh_en - GPT中英字幕课程资源 - BV1wj59zGEMq

![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_0.png)

Okay， can you hear me？

![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_2.png)

Yeah。没事。hello啊 perfect。是。你那个叫什么意思，哎你。

![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_4.png)

Okay， for the people in the decal， let's get started Sorry for the delay。

s like minutes it's possible be， but。Okay， let's get started。

 today's lab is going to be security fundamentals and。😊。



![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_6.png)

Slide credits to JA。Let's get started， so security basics。



![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_8.png)

So the first thing is why do we care about security right I know it's like kind of rhetorical question but it's kind of interesting to think about why do we care about security and why is it important to us so big thing is irresspective like how you've stre your data like you know your information is out there in the real world like your healthcare information。

 your financial information and your wording information and so many things are you know tracked by general public entities and all of them have to like create some kind of like a security system and if these things don't work properly then your data is going to be vulnerable and it's going to be out there for like other people to look at which is kind of problematic and if you remember a lot of like in recent days you can like look at like。

Many examples of different security breaches， for example。

 UC Berkeley itself had one a couple years ago， which is why they sort given us I think last pass as a password manager that you could use and then last spa had a security breach so this thing happens quite a lot and it's very important for you to think about how you're dealing with your own security especially when you're going to be managing your own Linux server right you're going to be having information that's not only yours。

 you're also going to be having information that's from other people so it's very very important that you think about this。

And kind of have this in the back of your head every time when you're designing systems or processes or like just maintaining your own the next server see。

 so it's very important to think about security。嗯。So we'll talk about some of the basic principles。

 so the first point in security is securities is economics let me just check。O。Yeah。

 security is economics。 And what do we mean by that right So security systems are usually kind of pricey to implement So let's say I have like a bike which costs 100 bucks。

 I'm not gonna to go outside and buy a very fancy lockin mechanism that costs like $200 right that really doesn't make sense。

 So every time you're thinking about security， you have to keep in mind that your security system is only as valuable enough or should only be as valuable enough as like the thing you're trying to protect It really does not make sense to like use an overtly expensive thing or like an overtly expensive security system like protect something that is nowhere near as important。

The second thing that we think about is this privilege so usually the idea is you don't want people who should not have access to the data to have access to the data right so you won't like give the least or like the smallest access possible without giving too much away so if some kind of app only requires access to like two different folders you only give as much and the rest you kind of like don't give it access to so that the idea of least privilege defense is depth is basically you can have multiple layers so you have like into something or like you can have a two factor so that's kind of defense and depth。

 you have like multiple steps along the way so that even if one of those steps are compromised you won't have multiple ten compromised in the middle and then complete mediation is just you know you have control over the entire pipeline rather than like it being some unsecurure element in the middle or like someone you don't trust the middle you have control over the entire change。

And finally， accountant for human factors and one of the common things for this is let's say you have like a system where you get like people to create their own passwords。

People might create bad passwords right so you have to account for like situations where like hey maybe some people might reuse passwords people might create bad passwords and there's like different ways to account for these things when you design like a security model so the most important thing is you need to know what your threat model is so we'll talk a bit about that in a second and you have to like kind of create like or like do your best like minimize the risk based on your threat model。

So what do we mean by threat model， so threat model is kind of thinking about。If you have a service。

Who is going to like attack that specific service or like what are the exposed spots and what are you protecting from So the threat model for me as an individual person is going to just be like hey some random bot is going to like someone is going to like be doing like a random like massive attack across like multiple things it's not going to be specifically targeted so as long as I account for that I should most likely be fine but let's say I was like a billionaire or something like very high profile and I have like industry secrets that I'm keeping track of then my threat model is going to be very different right so I might be getting people who like targeted specifically me and they might have a lot more like research and background on like what my services are or like what I have or like what password with them might be using So in that case the threat model is going to be significantly different or if let's say you're working for like a government institution the NSA or something those people might be targeted by like other governments who have like different interests and so on and they might have like a lot more resources pooled towards attacking you。

PointAll of these principles， your security or lease privilege and everything will change so it's very important to think about what your threat model is and what you can do to kind of minimize that loss。

Any questions what if we just like talk about， I know we even done like anything really technical。

 we just like talked about the general idea of it， but any questions will have us so far？Okay okay。

 and people in Zoom just throw them in the chat， we have people looking at it and they will either respond to you there or let me know and I'll take them。

Okay， so what are the goals for security right so if you want to implement some some kind of like a secure system。

 what do you want to do so you want to ensure firstly confidentiality so that means only people who have access to that specific data can access and read that data。

So in this case it's like someone who does not have access to it should not have access to that specific piece of information。

 The second is integrity So now in this case it's slightly different from the other one。

 So the first one is talking about read access and the second one is basically talking about either right access or like when you're reading something it should not change so you want to make sure that if someone is trying to go and look at a data it's not changed from like the initial time that it's written So these are like slightly different and it's important to understand the new ones behind it but the idea is like if some data exists on the server and you're reading it especially like go with a network or something it's very important for you to know that nobody is sitting in the middle change in that as you're trying to read it so you want to ensure that that data has not been tampered with even if you have access to read it and second and thirdly you have authentication so you want to say that hey this is the correct person who created the data plus I am the correct person who is allowed to be reading the data So authentication is kind of how you would imply or like how you would。

Ensure the first two points are working and finally availability so even though we're like talking about security。

 it is very important that the service is always available right so in a improve security system we don't want that to be at the cost of general availability so what you mean by this is like let's say you have like some kind of a server and it's like protected by some kind of like a security mechanism and the server can like be up for like 100% of the time but the security system that you've implemented is not as good and it kind of like goes down periodically so you would have this problem where the entire service itself is kind of affected because your security system does not have a pretty good up time so you also have to think about the fact that if you're creating like some kind of a security thing on top of an existing service make sure that it doesn't affect the uptime of that underlying service。

Okay。嗯。So now when we talk about confidentiality， there are like different ways in which you can store some kind of information on file。

 So the very first one is plain text surprisingly in like。Not that long ago。

 this is how people even stored passwords on service so if you created like a user account on a server they will literally just take a username your password and distort it on file and plain text now we know that this is like extremely extremely bad so the problem is if at any point there is like a leak。

All the passwords that are just out there， you don't have to do any work to like correct this thing。

 it just exists。Right over theres like like it's very vulnerable and it's like very bad so in this case plain text is like kind of the worst way to like ensure confidentiality the second one is Cyphertext so Cyphert is basically when you take some kind of like plain text and you encrypt it using what we call a key and what happens is once you encrypt some kind of information it's going to be basically indistinguishable from like random。

😊，Bage， right， so ideally， it's going to be the same as。

Creating a bunch of like random numbers and trying to read from it so that's the idea of like Cytext and what a key does for us is we'll get into the integrity of this either like further in the slides or like probably in the lab itself But what the key does for us is that it'll allow you to take some kind of plain text and then it'll encrypt using the key and it'll give you the Cyphertext and then you can take the Cytex and I can use the key you can decrypt it and get back the plain text when you actually want to read the data now So the idea is you will have like let's say the password you'll encrypt it。

And then write it to disk and then only when you're like， you know kind of like reading from it。

 you're like decrypt it again using side textex okay， any question with what we've just got so。Okay。

 and for people in person， just's like raise hand or something at any point。

 if you have any questions then I'll just take it。Okay。

So kind of taking a look at like what we just talked about so we have a secret that we want to encrypt so we put in the key and then it gives out the Cyphertex which is like kind of basically random garbage and then for decryption it's the reverse process you have the random garbage you put in the key and then after the decryption process you give the actual original text back and that's the idea of you know encryption and decryption we call this specific kind of encryption and decryption symmetric and it'ssymmetric because we use the same key for both encryption and decryption and there is a slightly different version of this called asymmetric and。

😊，If it's not in the slides， Okay， I know I'm seeing like if it's not in the slides quite a bit。

 but that's because like。😊，I have not looked through the slides in a very real sense。

 but if there is asymmetric it's usually going to be a public key and a private key so where you'll take the public key and if you encrypted you'll get something that can be decrypted by a private key and the opposite will be as well so if you have a private key and you encrypt it with that you'll only be able to decrypt it with the public key so instead of having the same key you' will have two different keys where if you encrypt with one you can decrypt with the other and then if you decrypt with one or like encrypt with the other you can decrypt with the original one so thatll be called asymmetric because you'll have like two different keys for encryption and decryption。

But yeah， any questions about how encryption is supposed to work or decryption is supposed to work？😊。

The路圈。Oh， okay。Well。Actually just look at slides yes so for symmetric you have the same key for both encryption and decryption so you have a secret。

 it goes to encryption， you have the same key that's used you get the cybertext and then you decrypt it with the same key and then you get it back this is what we covered and then asymmetric is when you have like a public and a private key pair so by the public key is for encryption and private key for decryption so in this case yes the public key you will give to everyone and the private key you will keep secret kind of key yourself so if you've done like any form of like SSH based like authentication for GiHub or like just access in like tsunami or like your student VM you are basically using public and private key encryption。

😊，So the idea is that if you encrypt any data with the public key so anyone can encrypt it and send it outside。

 but you can only decrypt it with a private key so let's say I have like my public key published outside for everyone to see and you want to send some kind of secret information that only I can read so you'll take about public key you'll encrypt it with that and。

When you try to decrypt it with the public key it will not work。

 but if you send it over and I get it and I have my private key which is not shared with anyone I will be able to decrypt it because you encrypt it with a public key that is like matched with my private key and the same is true where like if you have a private key and you encrypt something with a private key it can be decrypted by anyone who has the public key so now that's not very useful for encryptption but it's useful for something called signing so basically if I have some piece of information that I want to send outside to the real world but there is no way to prove that it's from me so what I'll do is like I'll take it and I'll encrypt it with my private key so when I send it outside to the real world you can try decrypt it with the public key itself and if the decryption works that means you know it is strictly from the person who encrypted it with the private key。

That's a bit more like harder to understand as to the you know but the use case。

 but the idea is that just like allows us to verify that it's coming from the person claims they are sending that information so you can use the public and private keepers for that as well any questions with that。

O。Yeah， so if you take a look at this so you have a secret thingme， so this is the plain text。

 you put in the public key first and then you encrypt it。

 you'll get out a cipher text and then in order to decrypt it you'll have to use the private key and then that will be the decryption and it will get back the plain text and this is asymmetric you know encryptption and decpt encryptption。

Okay。So the next part is integrity so this is to verify if a specific file has been tampered with during transit or not right and for that we use something called a hash function and if you've done 6 and B you kind of would be familiar with this but the idea is hash functions basically take some arbitrary length of data or like any kind of data and it converts it to a unique fixed length string of bits known as a hash so basically it'll take any form of like in this case of stick a dog and then you have this hash function in this case M5 and it spits out a fixed length string of like random typess that's going to be unique for that specific input so every time you give a specific input as long as the same input it's going to give out the same output even if the input changes by a tiny amount the output is going to be vastly different and the idea is when you did something like6q and B you usually wouldn't worry about what we call hash collisions that means like you might have two pieces of。

Inputs that might have the exact same output， but when we use hash functions for security purposes it's very important that they avoid these collisions right we're gonna to make sure that the output data is like always very unique so you can like look up hash collisions on like Google and like see like some of the older encrypt standards or like the older hash functions that have kind of become like thecom or like out of use because they had like some collisions that were discovered and we're like okay now we have like create a new hash function that does not have these collisions so you'll have like a lot of different standards so for example M5 had like an older version called M4 that nobody uses anymore I think purely because it's easy to like now go the other way。

But there are different functions that we can use and these standards keep changing as like compute power changes。

Okay， and another small point， let's see if it has。O你。

Okay so another small point about hash functions is that it's what we call like a one- way function。

 it's very easy to go from the input data to the output。

 whatever hash that we get but it's extremely difficult to like reverse this process so there is no real way to go from the output to the input itself the only way you would be able to do that is kind of brute voice calculate all different forms of input to get the outputs and see if the outputs match and if the outputs match that's the only way you can kind of like reverse calculate what the input would be so that's the idea of hash functions so that it's very difficult to do this and it's used a lot inse for that specific reason okay any questions about hash functions before we get to the next slide。

ok。O。Lets remove this。Window away。嗯了。那你有没有。あれ。Okay， cryographic have okay。

 so they possess properties that make it difficult for two inputs to have like two inputs of the same as so we talked about like the collisions and they're like different kinds of。

Like hash functions that we use so there's like a hashbased Mac which is like message authentication code So in this case basically what happens is you take a message and then you add the hash to the end of the message so you take some kind of a message and you just add the hash to the very end so now because of that what happens is when someone receives the message they'll know that the first X number of bits is the actual message itself and the last y number of bits are supposed to be the hash so what they'll do is they'll take the first X bits compute the hash and then they'll be like okay the person who sent this information to me said that they calculated the hash to be this and they'll verify if the actual hash comes out as correct if it's not the same they'll know that okay something was either corrupted in transit or maybe there's someone in the middle who's kind of like listening in on the conversation and changing things so you can verify that the message was tamped with so that's one way to do know this hash function comparison so just for message and the next one is called check sums and check sumums are usually used for like file downloads。

So what happens is when a file is downloaded， you can just like take a have hash of it like from the command line。

 there's a command that you can run， usually it's like Shah 256 sum or like Shah 512 sum。

 these are just like hash functions。So you'd basically hash a file and it'll give you an output and usually when you're downloading a file wherever you're downloading it from they'll tell you what the hash is supposed to be so this is like very common when you're like trying to download like Linux distributions from the internet they'll always sell you the file name and the specific hash that you can compare it with to make sure that you got the correct like file without there being some modifications in this case there's no reason to like compare it bit by bit because it'll kind of be drastically different you can just like look at it and be like okay hey it's not the same hash you don't have to compare it like exact every bit it'll be like okay it's not the same hash so it's probably corrupted and we have to like reload the file or maybe someone is like tampering with the actual like website itself。

Okay， any questions about this specific section？Okay， so let's keep going。

Okay yeah so we talked a bit about it's very difficult to revert a hash to its input so usually for password storages in modern day they kind of use hashes to store your passwords that's like kind of simplifying it because that also has other like security flaws if you're interested in reading more about that you can look up like password salts like just like know the table salt that they use so password place and space salt on Google and that'll give you a bit more information about why you don't just store hashes directly these days and you add something else but in the past like that used to be like the call Senator like store and password rather than plain text now we've like kind of move on from that but it's still like much better than stor on in plain text and second a very big use cases verifying downloads so you can like use terminal commands as I talked about Sha over56 sum to ensure that your download is kind of。

For like any of your favorite distributions IO so this can be U to arch feddera Manjaro。

 like any Linux distribution that's out there， Deian'll if you go to your download link。

 they'll always be like a checks or like a Sha file that you can look at and it'll tell you what the Sha 256 sum is supposed to be and once you get the ISO image and if you run Shah 256 sum and then the path to the ISO so maybe it's in your downloads folder it'll be like home your username downloads。

The distribution at ISL and it'll tell you what the hash is supposed to be and you can compare it with the one on the website and see if it's actually correct or not and like I would suggest like try to do it like at some point today just to kind of see what happens。

😊，嗯。Yeah， you'll check some of the downloads is that done as part of the network mayor。

Or is it done like after the network Okay， so for people on Zoom who couldn't hear the question。

 So the question was， is it techam done as part of the network layer or is it done after the network layer。

 And I don't mean the network I mean the else relevant or something why not the。

Oh is it like done Okay， so the thing is usually it's not done by default as part of the network itself。

 so this is something that you will have to manually run by yourself independently。

If that makes sense but I was expecting the network to So okay。That is a fair point。

 so the network does。Do some kind of。An equivalent thing， but for individual packets。

But it doesn't do it for the entire file。Not even at the L7 No so unless it's directly implemented at the L7 layer so you could have a downloader application that will take in a URL to download and the expected hash that will download the file for you and then compared the hash at the end but that's because you created the application discuss specify what you do but by default that hook itself will not worry about making sure that the file is like correctly verified that's something that you will have to add on at the very end a very common thing where this like happens automatically is。

If you use torrents。Again I don't condone piracy in this case you can use like completely legal torrents for like your ISOs so usually Linux distribution will also provide torrent downloads for your ISs and when you're doing a torrent download you don't have to manually do this verification process because in the torrent and protocol itself it will actually pull a hash from the website and once all the pieces are assembled。

 it'll verify if the hash of the final resulting file matches the one that the torrent expect to so in that case it's actually going to do it automaticallyically as part of the torrent and protocol itself。

 but it's not really baked into the network layer in any sense it's like part of the application because it's the torrent protocol that does it rather than the network itself that does it if that makes sense。

Okay， any other questions at this point？Okay。Let's keep going， okay。

Next we have authentication and yes， we talked a bit about this again。

 so this is to prove the author or the source of the data so in this case you can use asymmetric cryptography to sign specific files so as you said。

 when we use the public key to like encryptto certain，Piece of text to like file。

 only the person with the private key can decrypted。But when you like sign a file。

 it's the same process you still encrypt in the file but we don't call it encryption because the key to that know encrypted message is like basically public to everyone so it's not really security in any sense so we don't call it encryption so we call it signing but this process or like how it's done is exactly the same way so you'll take a private key and you'll kind of sign some piece of information and anyone that has the public key can kind of just like decrypt that information and see okay so if I can decrypt it with this private with this public key that means it must have been encrypted by the person who had the private key so in that case you can be like okay so I know where this information is coming from so because the private key is kept secret only the person who has that private key can sign the specific data so basically what will happen is you'll take the file you'll encrypt it or like sign it with the private key that's going to give you the signature then you take the signature and then you decrypt it with the public key itself and it's going to verify it for you。

And that can prove that this source of information was specifically signed by that person and when you do SSH connections this is basically what happens right so when you try to like connect to a specific SSAT server using public and private key authentication what itll do is the server will like give a file to you or like give some piece of information to you and be like hey take this if youre this person sign it with your private key and give it back to me so you will sign it and then it willll send that information back to the server and the server will have your public key and it'll be like okay does this match with the public key that I have and if it can decrypt it and if the assignment matches。

 it's going be like okay this person is the person that they claim to be and itll allow them to like log into the server so that's what's very important that you keep your private key secure and you don't like publish it in multiple places or anything and it just like stays in one place。

But yeah， that's the idea of like authentication itself with asymmetric like private keys and public keys。



![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_10.png)

Let's keep going Yeah so just a nice way to look at it So you have this kind of file。

 which is hello Bob and you take Alice's private key so Alice and Bob are trying to communicate So Alice wants to send hello Bob to Bob But before Alice sends it to Bob what they do is they sign it with this private key and you get this。

Enncrypted message， but in this case it's not really encrypted because anyone with the public can decrypt it so you have hello Bob along with。

Like the signature of the message and then once Bob gets the message Bob is going to have Alice's private key so what Bob can do is take Alice's public key and kind of verify if that message was from Alice so if that public key can like successfully decrypt the information that came from Alice so Bob will know okay this message was definitely from Alice and not someone else in the middle who is pretending to be Alice because nobody else but Alice should have Alice's private key so the big part is this all depends on the fact that Alice's private key is secret and no one else has access to it if someone else has access to it。

 this whole thing breaks down so that's why that's like the most important part of this。

And once you verify you'll get back the original source text。

 which was h so now Bob knows that that was a message that Alice sent over and it was correctly like it was from specifically Alice but this only verifies you know the source but it doesn't verify if nobody is stamped with this so if you want to verify that as well you would kind of like in this message you would add like the HM that we talked about so you would have like a hash of this message along with it so you can like verify and then see okay no one firstly it is from Alice and secondly nobody else stamped with that specific information and that will add on like integrity and authentication along with it any questions with that。

No case。Let's keep going then。

![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_12.png)

Okay， finally， we have availability。So now the thing is usually when we talk about availability and in terms of security。

 a big thing is so let's say you have like some kind of a secure server that you have posted on the internet and it's like available to everyone。

But let's say there are like people who are like just like。

Ddos in your server right they're just like making multiple requests to authenticate against your server。

 And even though they're not getting through， they still are using up a lot of your resources right because usually like taking a password and taking a hash of it and like looking at the results is like an expensive process。

 So usually what would happen is like even though they're not getting through to your server by just making a like huge amount of requests they can kind of just like prevent like actual people from who are supposed to be a lot to reach the resources from not having access to the resources。

 So what can you do to do like to prevent things like this。

 So the first thing is you can do something like filtering。



![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_14.png)

So filteriling is basically you can prevent like a specific request from like reaching this server so one very common way of doing this is like IP or like regionbased filteriling so if you expect your users to be only from let's say the Berkeley area in this case let's say we are doing some service at the OCF and we only expect like all the decal students to be located within California right so we can say if an IP is outside of California just like rejected directly like don't even like given a connection to it。

 don't worry about like authenticated or anything just block it so we can like prevent like any malicious request from coming through another more like better way of doing this is there is something you can look up called fail to ban and what that basically does is it will see like what IPs are like making requests against your server and if it like fails to authenticate multiple times you can configure how many times this is like three to five it'll dynamically say okay this person is like spam does for like three to four times so for the。

Next 10 minutes， I'm just like going to like block any request from the specific I。

 so that's how you kind of do filter。The next one is load balancing so we talked a bit about this I think in the web service lecture so where you have like I think you had some kind of a load balancer that you set up in the previous lab so the idea is you can have like multiple different systems in the backend that you load balance across so that you don't have to worry about like one specific resource or like the same resource getting like saturated so that's like another way in which you can increase availability and then you have redundancies so let's say you have like the same system available in like two places if one fails you can have like the other one takeover so that's one way in which you can have redundancy and these two along with load balances kind of go like and in hand and finally we have backups so basically you take frequent backups to make sure that in the worst possible like case if things go down you have a way to just recover and go back like the latest state that you had rather than like load in all your data or something so backups are like the most important part。

When it comes to like designing any secure system。

![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_16.png)

Okay， any questions at this point？Okay， so if there are no questions， nice think。呃。Okay。

Let's go on to the next stage， so this is security fundamentals which is like file security permissions and ownership so we kind of talked about like you know encryption and decryption from like a security standpoint there is another aspect to it and this is like file security within your Linux distribution itself。

Okay， so background for this is Uni or like Linux in our case is a multiple user environment right so you have your user。

 you have root， you have you could have like multiple other users， for example。

 on the service that the OCF maintains if you have one user or account for basically anyone who uses any service with the OF so they have multiple users away here and if multiple people can log in。

You have like some files that can be accessible to everyone that the user owns。

 but you also need to have like some files that are not accessible to other people except you so let's talk a bit about like what commands you can use to set up up and like see what commissions exist。

嗯。So， we talked a little bit about this like in the very first lecture。

 but basically if you do LS hyphen L， the A is just like lets hidden files。

 but if you do LS hyphen L， it's going to give you a lot more detailed information about the files that you have。

So each file has three different ownerships so the first one is for the owning user so the first list over here that you see that's like whoever owns that specific file so the user that owns the file the second name that you see is a group that owns the file so these two like slightly different so there are multiple users and these users can be a part of different groups and for example for the OCF you can have like every individual person is a user but you have different groups at the OCF like you'll just say OCF user is just like a normal OCF user but they can also have another group which is OCF staff so OCF staff is like a group of strictly people who are on staff and they usually will get expanded access where they'll have like access to a bit more things than normal users and then you will have another group called OCF fruit and that's again a small subset within staff themselves where we have like strictly the people who have access to like root information and can like run like rootot stuff that's。

be like the group so users can be a part of like one group or like multiple different groups as well and finally you have another ownership which is like public right so everyone else who do not belong who not the user and who do not belong to that group did they have access to it or not。

😊，So they're like three different ownerships and。😊，There is like。

Different ways like each part has like a separate thing where it lists out so if you looked at the initial in the previous slide you had like this kind of like a thing that came out so let's talk a bit about that so the very first thing tells us if it's a directory or a file so if it's a directory there will be a D if it's not a directory if it's just a file it'll have like a height there but then we have like three of three like it like a group of threes and each one tells like if that specific person like that specific group has like what kind of access so in this case the very first one represents the user the second one will represent the group and the final one represent everyone who did not does not belong to the group and is not the user。

So in this case for this example we have the user who gets read permissions。

 write permissions and execute permissions so this person can read the file write to the file and also execute the file like if it's a script you can like run the script right and then the group in this case gets read and execute permissions so anyone who belongs to the group of that file can read the file and execute the file but they can't write into the file and finally anyone else who does not belong to the group only gets read permissions so this is like how graular you can have like。

Useer permission in within Linux itself， but this is like the most default one you can talk like you can look up a lot more about this and you can get like even more detailed but for the purpose of this this is like very handy and like very useful and now let's talk a bit about like how do you actually change these permissions。

嗯。Okay so there are two two ways in which you can modify permissions so the first one you can do is you can change who owns the file so we talked about how there's like a user and a group who owns the file so we have one command called CHO which is like change ownership that allows you to like change who owns that specific file and the second one that we have is change in the permission itself directly so once you can change ownership the other one can change what the specific like rewrite access for that file for different people entails so in that case it's going to be C mod。

I don't know if that has like an expansion it's like change。

 I don't know modifiers or something but I don't know if that's an expansion。

 but that's the command that you use like change permissions I've not really thought about the until now so these are the two commands that you would normally use and we'll see about the syntax for them so the first one is to change file ownership so usually you might have to use suit to run it especially if it's like a root file that you change an ownership to and you have an optional hyphen capital R argument that you can pass in so in that case if you do that and if you changing in the ownership for a directory it's going to recursively change ownership for all files within that directory as well if you don't do that it's only going to change permissions for that specific directory itself and not anything else underneath it so if you want to do it for a folder make sure you use the hyphen R。

😊，And then you can pass in new user and new group and then that will allow you to like to change the permissions from like one specific person to another specific person。

 so if you look at the screenshot over here you initially have a file called important document TxD which is owned by the root user right so in this case the user is be logged in as admin and we look at this specific file important document which has only。

Whose user is root， whose group is also root and it has read permissions for only the user read and write permissions for the user and only read permissions for the group itself and no permissions for anyone else so now when the admin user is going to let go and read that specific file so you're doing't cat important document it's going to say hey you don't have the permissions for this so now what you're going to do is you're going to say a pseudo CH owns or change ownership from root to admin so you're going to change the user to admin and the group alter to admin and you're going to put in the file name and now when we at it we actually have access to it and now if you look at the permissions itself the permissions haven't changed you still have read and writeite access for the user read access for the group and no access for anyone else but the person who owns the file has gone from root to admin so now admin has access to it Any questions with CHN。

Okay。嗯嗯嗯。Next we have CH mod which is going to allow you to like change permissions itself so same setup where we have like a file owned by root but we've not we're not changing the you know ownership of the file you're modifying what the others can do with the file right so in this case the others that is like people who are not root or belong to the root group cannot do anything they can't read the file so what we're going to do is we're going to do pseudo CH mod O so O in this case is for others like so if you do a U that's for the user G is for group and O is for others and you're doing plus R which says add read permissions so you can do like plus R minus r plus w minus w plus x minus X。

So that's like to add or like remove some kind of permission and then you pass in the file name and now in this case what has happened is you still have the same ownership which is root but now the others have read accesses as well so once you do cat important document on TxD so now you can also read some important text in that case。

O， any questions with how CH more has worked。And yeah， in terms of syntax。

 you can do the same thing where you have like hyphen R to recursively go through the directory itself and change the permissions for everything underneath a specific folder。

嗯。O。Okay why is this very important so this is super important because we want like we don't want to leak information。

 especially when someone gets like some kind of access into your system right so let's say we have like the OCF service and we have S logins for like literally everyone who's a student at Berkeley and if let's say one user has the data compromise we don't want some attacker who gets access to that one users like login to be able to like read basically everyone's private keys or something that's like very like very dangerous so what you want to do is we want to like make sure we have like at least amount of like you know privilege given to any specific person so that even if an attacker gains some kind of access to your system it's way too little to do like any real damage。

So another thing that we suggest doing is like if you have like SSH keys set up。

 try changing your private key permissions to be like。😊，Like fully publicly readable。

 writeritable and executable and try using that like connect to a server if things work correctly。

 the expectation is that your SSH when you try to like login is just going to be like， hey。

 your private key permissions are like kind of stupid go fix that first we're not going to let you use this key without you fixing your commissions。

😊，So if you have like a private keys set up， try doing that and that's something like very interesting to just like look at。

😊，O。Okay， next we have signatures and certificates。

So we've talked a bit about like signatures in terms of like。

If I have like a private key and I can like publish a public key and like people can look at it。

 but there is some kind of a problem where。You know， if I publish a public here outside。

How do we verify that it's actually my public key right like anyone can claim that hey。

 this public key is like someone's like this is like lock its public key and this is the thing that has been signed so there is no real way for us like verify if this public key is coming from the person they claim to be and this is like kind of an nontraal problem to fix and it can create like a lot of。

😊，You know problems like sometimes I might have a public key that I publish but then it might be compromised like let's say my private key gets leaked then I want to like revoke that public key and say hey my private key is leaked I need to like change this so how do I deal with something like that or like how do I deal with things where i'm publish in my public key but。

Something happened in the network， some things went wrong。

 some packets got corrupted and the wrong thing is out there。

 so we need to like kind of fix a lot of these problems so things get really messy and for that specific thing the solution is certificates。

Okay wait let's before we get to the questions I'll just talk a bit about certificates so certificates I would say like we've not talked about it in lecture but the idea is like if you look at like a CTps on websites and you see like a lock sign that comes up you can click on the lock sign in your browser and click like view certificate and it'll actually tell you like who has like approved that this public is coming from the right person so you can just look at the certificate itself and it'll say there's like a chain of trust where it'll like go hey。

 this is the person who has this certificate the person who verified this person is this other person and who verified that other person is this other person and so on and we'll have like a chain until it gets to like some kind of like a root certificate authority so it's called like a CA again you can go stuff like root CA or like TLS certificates or like let's encrypt which is like a common service that you can get certificates from and that's like very handy like look at and see how like。

ickets work for websites， but yeah， any questions so far。

Okay I know that's like quite a bit of information and it's like a lot to like go through。

 but if you have any questions just like let us know and we'll talk to you。😊，嗯，嗯。ok嗯。Yep。So okay。

 I don't know why that was switched up， but okay， so yeah。

 we just talked about this sorry about that and so who sends a certificate and like how do we know like everyone is trustworthy and。

Yes， usually you have these group certificates that kind of are included as part of your operating system itself right so all of those things。

You know ideally these root certificates don't change too much。

 so like usually your distribution or like Windows or like Android or like iOS will have like a specific certificate that it came with so you know like if that specific certificate at the end is valid the entire chain can be trusted this is like not a foolproof system there have been things in the past that could kind of like attack the specific root certificate model and like create vulnerabilities in there like you can look up those different like attack vectors that existed in like in the past and how they were dealt with but the idea is usually either like web browsers or like your operating system itself will come pre-packaged with some specific like roots that it trusts by default and those root certificates and like very。

 very strong like have never changed like for the past that can5 years or something so you can like just see okay that is like something that can definitely be trusted and it will not change for like the foreseeable future。

Okay next we have okay some idea about like zero trust again okay in this case I wouldn't say this is like as important this is just like some cool things that are being done in like the modern day like you know especially when you have like software as a service and like AWS and like other apps coming up so we have like different approaches to like。

You know like more access to like how we give like fine greenax control to like different people and we also have like other ways of like identifying like specific users and device rather than it just being like any kind of like a login yeah you can like just look this up I wouldn't say you have like spend too much time on this this is just like interesting work that has been done like more recently in the space that is more relevant these days but not really too important for our use case。

Okay， finally， I think， I think that should be the last slide I know of like kind of。

Don back for like any question。Okay。I think that should be it see few people like start working on the lab if you have any questions like raise your hand I will come along and help you out and good luck for people in zoom thanks for coming good luck with the lab if you have any questions feel to post on Ed or like on the Discord and we'll help you out。

😊。

![](img/f26a3ec7a759f058aaf2ae9eb216f1e7_18.png)

嗯。