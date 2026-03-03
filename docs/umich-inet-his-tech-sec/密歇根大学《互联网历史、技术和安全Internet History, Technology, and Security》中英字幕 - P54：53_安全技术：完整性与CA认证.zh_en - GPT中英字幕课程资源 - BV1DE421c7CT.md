# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P54：53_安全技术：完整性与CA认证.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

So now we have a way to ensure the confidentiality using secure socket layer and public private key encryption。

And the only question now remaining is who are we talking to and are we talking to that server that we think we're talking to。

 are we really talking to Amazon， are we talking to Course。

 how do we know now you'll notice if you take a look at the top of your browser perhaps right now even you can take a look at the top of your browser and usually when it's indicating that you have a secure connection。

 you can click on this and see some information， it's called the certificate information。



![](img/e47072a247d63799ae6f2b934ae53511_1.png)

Okay。And so HttPS has the notion of a public key。 We retrieve the public key when we make the connection。

 but there are two kinds of keys， there are public keys that are just made up that are sent to us and then there are public keys that are signed and validated by a third party certification authority so this is a Coursera and it is certified by GoDaddy C authority。

 so it's not just that we're getting the certificate from Coursera we're actually getting the certificate signed by GoDaddy that GoDaddy has has checked the ID of Coursera said okay。

 you must be the CEO of Coursera or I'm not going to give you this signed private key so it's a process to get private keys signed and it's a way to make sure you are talking to who you think you're talking to so this is called digital certificates。

Also known as sort of signed private keys。 Now， if we go back and we talk about the integrity， right。

 we want to know who we're talking about。 And so we had this notion of a signature。

 a signature is a way that you know that you're talking to who you're talking to So for example。

 like if a guy comes to your office and says hi， I'm Dr。

 Chuck've got like a beard and some white here， you can say， hey， if you're really Dr。 Chuck。

 show me your tattoo and now you'll know that very few people will also look like this and have this tattoo right So this is my private key and this is my signature of my private key。

 This is like my message digest。 So so people won't have this tattoo if they claim to be Dr。

 Chuck So this is Dr。 Chuck this is my message digest。

So there's a difference between a private key and a private key that's been certified by one of these designated third parties。

 these designated third parties are called certificate authorities。

Now you could say I'm a certificate authority， well。

 some certificate authorities are more better certificate authorities than others， okay。

 so they're a trusted third party。And so how did they start well。

 Some are more trusted than others and the more we trust them they kind of all work out。

 So it's not everybody。 you can't become a trusted authority。

 So one of the many trusted authorities and one of the oldest ones and one of the more popular ones and one of the more expensive ones。

 It's pretty expensive to get your certificate signed。

 it can be as inexpensive as a couple hundred dollars。

 it can be thousands of dollars to get a certificate signed and Verign is one of the oldest and most well respected of these certificate authorities。

 So the idea is is that。I have this website called online。doctorchuck。

com where I teach Python classes and do various other things。

 and I wanted a secure certificate because I would be handling people's data and I wanted to be respectable and have a secure certificate。

So I had a public in a private key and then I sent it to a certificate authority。

 I paid them money and then they send me back assigned signed private key okay so this is now now you might say oh this is kind of evil or this is really expensive because all they really are doing is like changing a few bits in my private key or're adding few bits to my private key but they have a lot of responsibility and the good ones have a lot of credibility so they don't want to lose information。

 they got to spend some time validating identity saying okay are you really the owner of Dr。 Chuck。

 co they're not going to hand the certificate assigned certificate for Dr。 Chuck。

 co to anybody except the true owner and so they spend some time checking to make sure that it's the true owner and they do this by looking at the registration data and Dr。

 Chuck。 co etca， etc cea， eta so there is a cost of verifying all this identity。

Kind of like the signature track on Coursera。And that's kind of what's going on in the signature track of the Coursera。

 there's a difference between a certificate。And a certificate that Coursera is going to assert that we have verified the identity and the cost is in the verification of the identity。

 so certificate authorities are charging Amazon， but then ensuring that they don't mistakenly give the Amazon。

com certificate to a randomba guy because if they did， that bad guy could pretend to be Amazon。com。

So then you might ask。Who decides which of the certificate authorities to trust。

 We use the certificate authorities to decide whether or not to trust Amazonazon。com or Cosera。

org or Drrchuck。com or whatever how do we decide which of the certificate authorities we're going to trust Well。

 it turns out that Apple， Microsoft and Linux and other operating system vendors。

 preinstall at the moment that you're either purchasing your computer or installing your operating system。

 part of that operating system is actually a list。Of the public keys of the chosen certificate authority。

 So if you look deep enough inside your computer， this is my Mac。

 You can see the companies that have been included。

Buy Apple as the manufacturer of the operating system。

 And so you see that Verign is one of those companies that has been preinclude in Apple Macintosh。

 which means that a certificate from Verign is going to be known， right。

 So let's so let's look a little bit more。 So， so these come your browsers and your operating systems come with prebuilt in public key certificates for certain certificate authorities like Verign。

 Now that's a lot of trust that Apple， Microsoft and Linux have placed in Verign。

 And that's because over the years， Verign has earned that trust。

It says Verign doesn't just get out certificates without checking right if the Verign gave out an Amazon。

com certificate to somebody without checking。They would lose a lot of credibility and then Microsoft would like take them out right。

 say well， Verign seems to become kind of sleazy， they seem not to be able to handle their security。

 but they have， and so they remain in there and so it's kind of an interesting thing where they are motivated to keep their security high。

 they're motivated to do a good job because the moment that they sort of fail。

 they lose a lot of credibility and respect and their value of Verign brand and is all of the respect that we have for Verign。

so。So。So we mentioned public private key encryption。 We have the public key that goes across。

And I'm about to type my credit card in， and so the problem now that we're going to solve is。

Is this really Amazon's key， is it really Amazon's public key。

 I mean I got a public key from across this connection I made to a server and it claims that it's Amazon。

com， but。Do I believe that it says it's Amazon。 co and so that's the integrity thing that's the secure that's the do I believe it is it really got the Verign tattoo in addition to the Amazon。

 com that it represents that it's Amazon。 co's public key。

So we can also use public keys to do signing and basically Verign has a public and private key for Vericign。

 the public key for Vericign is sitting in your browser right now and they use they do an encryption much like the message digestig。

 they do an encryption of Amazon's certificate and then sort of create a digest and then add that digest to it so a certificate says I'm Amazon。

 co and later it says， oh yes and Verign signed this with Verign's private key okay so Verign's private key is used to sign Amazon。

 thiss probably easiest if I just show you sort of a video。Wait， oop， I'm going the wrong way。

 am I going the wrong way？What's going on here。 I come on going the wrong way。Yeah。

 I'm going the wrong way。 Okay， so here we go。Going backwards。 So here's how it works。嗯。

This is how Amazon gets a public key signed by Vericon right so in the beginning。

 Vericign makes a public and a private key somewhere in a bunker and they store the private key and they you can sometimes read up on how many how much effort they go to storing the private key and then they hand the public key to Apple。

Microsoft。And Linux。And then they bundle that in with your laptop。 So your laptop that you buy。

 you walk out and you have a laptop， and it's got public keys in it。From the vendor。Now， Amazon says。

 you know what， I'd like to do some commerce， and I would like to be able to use SSL and and have a certified private key。

 So then what Amazon does。Is Amazon inside of its servers， generates a pair。

 a public private key pair。So this private key is not leaving Amazon servers， it takes a while。

 it takes minutes， sometimes generate the right random， sufficiently random public and private key。

By looking at all the large prime numbers and then picking one and then bang。

 making a public and private key。Then what Amazon does at that point is it transports its public key to Verizon Now during that transport it might have seen it but it's okay because it it's just the public key right so it's just the public key and so it actually can be sent across the internet and it's most commonly sent across the internet like when I got the online。

Drchuck。com certificates， we just typed it in and send it because if you get a hold of the public key。

 all it means is you can encrypt it doesn't mean you can decrypt。

So then what happens is inside of Verizon's servers。

Theizon computes a message digest using its private key， right。

 and then it adds basically a signature。That says， oh。

Here' is Amazon's public key that I received from Amazon verified the identity of the person。

 and now I have signed it， Mr。 Verign， I've signed it。

 and that of course is just like message digestig like information that is appended to the bits of the public key。

 then that public key with signature is sent back。Bundled together and sent back to Amazon and now Amazon has not just any old public key。

 it has a public key that saysI am Amazonaz。com and Vericign is now asserting that I am really who I am。

那N。And。Again， so Eve saw that one。Who cares？It's just a public key。

 there's nothing about the Vericign private key it never left the Vericign servers。

 the signature is public information， you can use the Vericign public key to verify that the signature is right。

 but you can't forge the signature。So Eve can look at that， Eve could look going this way。

 Eve can look that way， Eve gets nothing。He gets nothing。 So Amazon now has a signed。

And certified private key。Then what happens？Is。Sooner or later， many hours， many days。

 many months later， you decide on your laptop， remember this is you， oops。This is you。

You want to buy some shoes。So you connect to Amazon。com。With your browser with an HttP S connection。

 and then what happens is。

![](img/e47072a247d63799ae6f2b934ae53511_3.png)

Amazon sends you its public key and Eve， of course， is eavesdropping all the time。

 Eve sees it goes by。It's worthless， right， it's worthless。Because it's just the encryption key。

 it's not the decion key， the fact that it's signed， it sees that。

 but it can't do anything with that information now。Within your laptop。Within your laptop。

 you have from the vendor the Vericign Public key。From Macintosh or Apple or whatever。

 So you can look with this， go back， you can look with this public key at that signature。

 and just like we did with a message digestig before， you can go， yep。That's good。

 That really had to have been signed by Verign。 And if if your computer is really conservative。

 but it can actually go check with Verign can send it up and say， hey， did you verify this。

 and then Verign can verify it too， but you actually don't need to connect because you have the public key the only way that you know whatever that message digest could be right would be。

 is if Vericign， private key was used to generate the message digest。

 just like we used to do Santa in the other one。 Okay the San is just really simple。

 but it's the same basic mechanism， this is verifiable that it came from this private key。 Now。

 if somebody broke in install the private key， that's a different story。

 But if the private key is safe and secure， hasn't been compromised。

 the only way to generate that message digest is be in possession of the private key。

 So now you are in a position。Where you are in a good mood， right？You see an HTTPS。

 you can pop that little thing and say that was signed by Verign。

 you can be assured that Verign is asserting that that key came really that key came from Amazon and now it is time。

To encrypt your visa card。And send it over an encrypted connection to Amazon。

Because you won't send your encrypttic thing， you won't send it unless you believe that the HTTPS is proper and your browser will pop up a little pop up and say。

 wait a sec， this certificate looks a little funky， claims to me from Amazon。com。

 but it's not signed by one of the signatures that I believe in。So you send your data。

 it is encrypted and Eve is watching right Eve is always watching。

 but because it's encrypted with a public key， unless Eve has supercomputers in a couple of months。

 there's nothing that Eve can do， and then of course Amazon decryptps it using the private key so the private key comes in。

NowLet me redo that。So in it comes， Evewaes， but is helpless。

Because they don't have enough computers， Eve doesn't have enough computers and your key is large enough。

 so Amazon then takes its private key and uses that to decrypt it and ends up with your plain text again。

So if you think this whole thing through， this Eve was watching the whole time， we sent a public key。

 we signed and returned a public key， then we sent the public key to your laptop。

 we verified the public key， and the whole time Eve is sort of watching all this information and she is powerless。

To break it。Pretty dang， clever if you ask me。And we can thank。Diffy Heman and Merkel for that。

 pretty darn clever because Eve sees it all。Just think what would happen if like the Germans had this in World War II。

Would have been pretty cool。Of course， they didn't have computers， so it had been difficult。

I don't know Too much to think about right now。 Okay， continuing on。

 So what we have is we have this thing called the certificate authorityity。

 which is a trusted third party that signs these certificates right And so it's the it's an entity that issues digital Signs on public keys so that we。

 the public have a way of validating that an Amazon co certificate really came from Amazon co So if you then add this all together。

 right， if you add this all together， we have basic public private key encryption。

That make sure that this data can move across the internet out of your computer out back into the next one all encrypted。

 that's just public private that does that and then we have this third-party certificate authority that your application can use to validate the certificate that comes out and so the combination of SSL or the secure sockets layer and a certificate authority gives us high confidence that when we're talking to something we know we're really talking to it so it's pretty nonintrusive security。

 if your browser pops up with a little pop up message that means it's got a certificate that it has no certificate of authority to validate and that's not a good time to be typing in sensitive information unless you know exactly what's going on。

So that sort of brings us to the conclusion of this these last couple of lectures have been about message confidentiality and that is protecting the contents from being revealed we use encrypting and decrypting for that and then we have message digests and to signed things we've signed messages。

 we've signed certificates we've signed many things and those are important and we talked about both sort of shared key and secret key where you have to get together and agree on a key which is a symmetric key that's used for encrypting and decrypting and then you have the public private key which is the asymmetric which is one key is used for encrypting and the other key is used over a decrypting and you can freely show the encrypting key because it gives very little information a lot is mathematically possible but difficult to decrypt public private key message so that kind of sums up that kind of sums up our lecture on public private keys and I hope you find it valuable see on the net。



![](img/e47072a247d63799ae6f2b934ae53511_5.png)

![](img/e47072a247d63799ae6f2b934ae53511_6.png)