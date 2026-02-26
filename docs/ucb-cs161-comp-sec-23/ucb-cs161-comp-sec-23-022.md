# 022：UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p22 -22--CS161 FA23- Lecture 22 - DNSSEC.zh_en -BV1YGbceREDs_p22-

![](img/82d2df7f47e22d165c245fad27d5d270_0.png)

Okay。Hi tell me if the screen share or the zoom or the setup is wrong and I'll try to fix it but yeah today's really exciting it's DNS Se when I was first making these lectures this is one of my favorite ones to make so hopefully you enjoy it too before I get started I should tell you what DNS is because we're going build on top of it today so remember the two big ideas that make DNS work where first there are all these name server floating around if you ask a name server for the IP address of a domain and it doesn't know the answer redirect you to someone else and the way that you traverse all these different name servers is you organize them in a tree structure you start at the top if it doesn't know the answer it redirects you to someone further down the tree until someone knows your answer。

Those are the big ideas from last time and then we talked about how you would actually implement this and we said that in order to have good caching performance I'm going to organize everything into records。

 every record has a data type and every record also gets sorted into one of these four sections and the reason why this is nice is because every record that comes back to me I can store it in my cache and then that way I can avoid having to ask repeat questions because that takes time and that puts unnecessary effort on all these poor name servers okay and then finally I guess final thing on this slide is that remember DNS is meant to be fast the reason why caching is good is because I want DNS to be as fast as possible people use it all the time every time they open up their browser you're running DNS so I better be fast and then we mentioned last time the DNS as we discussed it there was simply no cryptography at plate I never mentioned a single cryptographic protocol but I will today and so we're gonna try to stop all these attackers from last time today。

Remember there were malicious name servers who could send you bad answers daily book checkingck as a way to sort of prevent that so that they can only send answers that are within their domain like if I'm a doedduu name server。

 I'm an expert onedduu I can only send malicious records foredduu but I cannot send a malicious record for Google。

com and then remember network attackers it's kind of a similar pattern to TCP if you're on path or a man in the middle attacker you can attack ENS all you like there's no protection if you're an notpath attacker you have some stuff to guess but we mentioned that the Kainsky attack makes it more plausible for someone to guess okay。

So the reason why I'm telling you all that stuff from last time is because today we're going to try and take DNS。

 which we just saw is insecure against network attackers and malicious name servers and we're going to fix it we're going to add extra cryptography to it try and make it secure and I think this is really beautiful because it's going to take ideas from the first part of cryptography and then this DNS protocol and we're going to like put it all together in a way that I find very valuable okay so。

Here's our first attempt which is well didn't we like already do this so you're telling me that this DNS thing it's insecure against network attackers and we got to design something to secure it but like didn't you already spend a whole lecture telling me about how TlS achieves all the same goals and what you're kind of right and so one thing we could do is we could try to just use TlS I guess before we do that let's like survey the landscape and see what the goals are for DNSec so we already talked about the threats that DNS is not secure against let's think about the properties that we want so this is just like every time when we say okay here's a new protocol what does the new protocol need well I would like integrity because remember last time we kept talking about cash poisoning if someone gives you a bad record then you're gonna to cache it and then now you're gonna be fooled into thinking that this IP address mapping is correct even though it' malicious for as long as as it's in your cache so we want integrity we don't。

People to be able to mess with the record we want to get the true unmodified record but here's an interesting question。

 I guess it's not really a question as much as it's a slightly counterintuitive statement which is this is one of those cases where we don't really need confidentiality do we do we really need to make sure attackers can't read the responses like think about what's in a DNS request or response it says like this domain maps to this IP address but is that like top secret information well not really because if the attacker wants to know what the IP address of www。

go is they could look it up themselves because is a public name server answering anyone's questions and it's not really giving you any secrets necessarily right？

One possible counter argument that you might make is oh well maybe if they don't see my DNS response they don't know who I'm trying to talk to。

 but remember that even TLS doesn't provide anonymity so in general attackers still know who you're talking to so these records don't really need confidentiality and so this already is kind of a departure from some of the previous schemes that we've seen where we really cared about attackers not reading our data this is one of those cases where well depending on this particular threat model and the fact that we're sending only publicly known information who is confidentiality for this particular case I really just want people to not be able to poison my cat I don't care if they know what's being sent to me okay so that's kind of the highlevel idea。

Those are the goals that we want and so as I was saying before that slide so really interrupted me we've already seen something like this so you're like wait a minute all this stuff about attackers exist on the network and I want to stop them didn't you already show me a protocol to stop that called TlS as true I did So what if we just use that like forget building a new one we remember TlS is end to and secure That means that all the attackers along the way cannot stop you as long as the TlS connection is set up securely So who needs all this new protocol stuff What if every single one of these messages was a new TlS connection So these two servers the resolvers make a TlS connection and they send messages back and forth the recursive resolver makes a TlS connection to root and gets an answer back and so forth So does that work what kind of works why don't we do it well one reason is remember how we said DNS is supposed to be fast but what do we know about TlS from that like super long。

12 step whatever handshake that's kind of slow And so just to get a single message sent along one of these connections。

 you have to wait for that entire TlS handshake to finish and then send a single message so it adds on some overhead with the handshake and if you have to do this handshake over and over again every single time you connect to a website you can imagine that little bit of extra time like it adds up and so the designers of DNS said well it's possible the TlS is slow and that kind of goes against our goal of DNS should be as fast as possible so TlS could work in this application but it's not great because that super long handshake because I'm not a huge fan of it there's another reason that's a little bit more subtle so maybe you got the performance one but one issue that's a little bit more subtle is that TlS actually doesn't help me with that caching problem and so think about an attack where you make this beautiful TlS connection it's end ands secure nobody can tamper with it and it's perfect and beautiful and then。

Send you the record and you know that it's protected and then you put it in your cache what if you like then go to sleep and someone goes into your cache and messes with it are you gonna catch that it TLS gonna catch that probably not because the TlS connection is already finished right you made the TLS connection it sends you that piece of data you close the TLS connection what if someone messes with the data in the cache afterwards you're not gonna to catch that right final issue is does this really solve those malicious name servers remember that like endto-end security property only holds if you're talking to someone who you know is trustworthy but if you make a beautiful TLS connection to an attacker or a malicious name server they could still feed you garbage they could feed you malicious records so we haven't stopped them either okay we also haven't stopped the recursive resolver itself sending you bad information so maybe someone takes over the name server and feeds you bad information maybe someone takes over your recursive resolver and feeds you bad information so those are the three issues。

I see with DNS over TLS， we could certainly just outsource the issue to TLS and say you handle it it's to insecure。

 but it's slow， it doesn't help me with caching and it doesn't stop malicious name servers so there are some issues so maybe we should design something else。

That solves all of these issues and is really targeted toward DNS in particular okay this is kind of a digression that I'll say it anyway which is this issue with caching actually brings up maybe a more general idea and if you don't totally follow is not the key point of today so don't worry about it too much but basically this idea that somehow if I form a TlS connection the connection itself is secure but then when I store the data in the cache someone could still modify the data in the cache that brings up this contrast between object security and channel security and so the idea is that TLS gave me channel security it said this channel is secure anything you send over this channel is going to be protected。

And so that was securing the communication channel itself That's like making the channel itself secure。

 but there's another model which you can think of which is object security So here we're not thinking about making the channel itself secure we're thinking about securing the object itself and if I secure the object itself who cares where the object goes it can flow over some insecure transit channel I can store it in cache and the object itself is the one that's holding the security So it's kind of a subtle distinction。

 but basically TlS was thinking about whether or not the channel was secure and if the channel is secure then whatever you pass through the channel is okay but by contrast。

 maybe what we want today when we're thinking about DNS caching。

 we don't really care if the channel itself is secure we really want to think about the security if the object because if the object itself is secure then when I send it across channels it should be okay So it's kind of a subtle point you see it come up in different applications too so I just wanted to bring it up but it's definitely not the key point of today so it's okay if it。

Seems kind of mysterious at first。Okay so all of this is to say DNS over TLS it kind of sort of works。

 but it's not perfect， it turns out some people in real life actually use it I can test you on this。

 but some Firefox browsers or I think the most recent Firefox browsers actually do use DNS over TLS so it's a little bit slower Firefox decided that the security is worth it so they added it I'm guessing you can probably disable it somewhere but that's what this slide says okay I'm upset about that。

Okay so we tried something， we tried DlS， it didn't fully fit our needs。

 so today's job is to custom design a new protocol that's going take DNS and build on top of it to give me DNS sec which is going add extra security to it okay so the sec I guess stands for security extensions so we're gonna take DNS add some more features to it and remember I don't really care about confidentiality when we talked about our design goals I really just care that people don't poison my cash okay there's two really big ideas I briefly mention them there and I'll talk more about them on a couple slides but there's one functionality issue that I really care about so we already talked about from a security standpoint here's what I want but there's actually one really big design challenge that I really have to follow here which is that DNS Act has to be backwards compatible and what that means is I could just take DNS and say well this didn't work I'm gonna throw it out of here I'm gonna make my brand new security DNS thing and everybody in the world。

Please update your systems to use the new DNS Se and don't use the old DNS you could do that but now you are gonna have to go to every computer in the world and tell them to make that update and like have fun with that because maybe some computers are so old that they cannot do this update maybe some computers or some people are too lazy to do the update maybe some computers are configured in a way that they don't even accept the update who knows right so you could try and go and force everyone to make this update but we probably can't do that now you have these two different protocols it' complicated so this is a case where people didn't design in security from the start and so in order to fix it we're gonna have to design on top of DNS you cannot go back and break original DNS to make this protocol work we need to keep original DNS set working while building something on top so this is an update to DNS it is not a replacement of DNS because replacing it would be really hard if you don' want to try it go ahead but we're gonna build on top of DNS instead okay。

Here's a warning slide so what you're about to see and why I find this lecture kind of interesting is you're gonna see DNS basically in full like usually we'll leave out a couple details in the networking section or something because the protocols are kind of complicated and they're not all necessary for security but today's one of those days where I'm going show to you in full like gory detail I will leave out basically I'll spare no details and so it can get a little bit dense at times I'll try to like tell you when things are like little asterisks and not like the key idea but just letting you know some things are going get a little bit dense but I find it pretty beautiful because you get to see exactly how someone built a protocol on top of the existing DNS protocol you get to see all these full ideas intersect and also gives you a bit of an appreciation for what it's like to build this stuff in real life so hopefully you enjoy it but I'm just warning you that it's one of the denser lectures of all time okay。

So let's try and design it together I guess so I'll throw out some questions you can ponder if you want maybe in the interest of time there's no like you know take five minutes to ponder because I want to get through everything okay so one question is I know I need some sort of cryptography for sure but I've seen all these different cryptographic protocols I've seen like oh I have AES CBC chain mode and I have Hmac and I have digital signatures I have public key cryptography certificateates I have all these different things that I learned about in the cryptography unit and I don't think I need them all so which ones do I need and which ones do I not need that's a good question to start with so maybe one question I actually have not seen these less and al so I don't know what's gonna to happen okay okay so the first thing we can figure out is what do we not need I remember when I talked about design goals I don't need confidentiality on the records because the records themselves contain public information like the I address of Google that not private information so I can immediately take my list of crypptography。

Protocols and just throw out half of them all the ones that involve confidentiality。

 public key cryptography， EESCBC chain mode， CTR training mode。

 I will throw those out they're not necessary for today I mean they're useful but just not for this particular purpose so we narrow ourselves down to just the ones that provide integrity because that's why I care about and I'm left with two choices I could use max and remember the idea by handax is that we all share a secret key where everyone who needs to know the secret shares a secret key and then if you have the secret key you can generate Max and you can verify Max that's an option another option is we can go the public key route and in the public key route only the person with the secret key can sign something and everyone else with the public key can verify and so now you have a choice to make which one do you like better do you like the symmetric key where a certain number of people know the secret key they can generate signatures and verify and everyone else cannot or do you like the approach for one person has a secret key to sign something and。

One else gets the verify so can try to think about it， take a stab at it。

I think I like digital signatures here， maybe you disagree。

 but I like digital signatures here because when I think about DNSX or DNS in general。

 I want everyone to be able to verify the answer， I don't just want a small subset of people to be able to generate Max and verify Max I want one person the name server to sign the records and I want everyone else in the world to verify so I like digital signatures here。

 but you can see how we had to go from all of our cryptographic protocols and kind of use process of elimination to pick the one that I like best okay so if you were designing something like this in real life if you're designing Project two。

 these are the these are the kinds of questions that you get to ask okay。

Next question we chose a protocol we chose to use digital signatures so the next question is how do we use it。

 I know there's a signing protocol if there's a signing function。

 I know there's a verifying function， how do I use them。

 who uses which function so now I have to figure out how do you make sure if the record is correct that's our goal is to make sure no one taamppers with the record I know I have a sign function available I know I have a verify function available who should be doing the signing。

 who should be doing the verifying who calls what that's a question we have to answer so I think and you can try and predict what's gonna to happen we know that only one person can sign and everyone else can verify who is the one person well I think the name server should sign using their private key so no one else can sign but the person sending their record which is the name server and who can verify I think everyone else should verify using their public key so that's my choice I decide that a person signing is this name server everyone else should verify。

Take this protocol and then I decided how to use it right I have a protocol It's about these functions。

 This is my choice of how to use it Okay we're making good progress， we chose a protocol。

 we're gonna decide how to use it so let's take this idea we have a protocol we know how to use it let's go see what happens so the recursive resolver asks a question it says hey what's the IP address of E Stopberkeleyeddu and the name server says well what do they say we know that they're gonna have to do something about signing and verifying we just talked about that but what do they actually have to send here right like what's the answer going be I'm trying to predict do you want to take a sta by answering it like brave volunteers I don't know last semester I did this and everyone just like scared I me silence and I wasted like five minutes and I was like I'll forget I'll just spoil it。

No takers its like 5 pm lecture mode okay so I can think about it in your mind so you don't have to tell me okay so I think you still have to send the record itself hopefully we agree so I'm gonna send the record itself that's not good enough though because I know I have to do something to provide integrity so I have to send the record itself maybe I have to send something else I think I should sign the record and send it so the name server should take its private key。

 sign the record and then send the signature itself Are we done now do I just send these to what does the recursive resolver get it gets the record in the signature I it happy at this point as one missing piece try and like predict what it is because if the recursive resolver gets the signature how does it know if the signature is good Well it's gonna have to verify the signature and how do you verify signature you use the public key we didn't give the resolver the public key so the final missing piece is we have to give it the record you have to sign it and we need to give。

the recursive resolver， the public key to say here's how you verify so in English and I'll make it records later but for now just in English we're going to say the record just like last time no changes the IP address versus this thing here's a signature on the record so you know it's good but how are you going to verify the signature here's a public key that you can use to verify that it's correct。

Okay。There's a question？Yeah， question about certificates， hang on， it's coming soon。Good question。

So this almost works， there's an issue which I think you just brought up which is well there's still ways that this could be broken So one of the issues is what if this name server is malicious someone has taken over this name server well what can they do they could still give me a record they could sign it because they own the name server they've taken it over they know the private key and they can sign things and so I still haven't stopped that first issue which is what if the name server is malicious I think I'm stopping network attacker somehow but I haven't stopped the name server yet and then the second issue as you said。

 is what if an attacker on the network swaps out the record swaps out the signature to sign it with their own private key and then sends the attacker's public key well when I verify using the attacker's public key on the attackers generated signature it's going to check out and I won't know any better so this public key is still unprotected is the same issue as we talked about in the cryptography unit where we said public keys are great but when I send the public key how do you know if the public key is good。

And as you said this is a problem that we've already solved so we could go back and try to solve it from scratch。

 but when I look at this and I say this public key that I send it's not super secure right anyone could just fake their own public key so how do I make sure that the public key is good we've already solved it we use certificates it's going a whole lecture talking about how certificate solve the problem of distributing public keys so I'm just going borrow from that so I'm going to take DNS I'm going to take this idea of certificates I'm going to blend them together and then get this DNSec protocol that I'm looking for okay。

And so the final question that we have to come up with right so we've asked some questions。

 we came up with the design it was almost good but it still had these issues but then we realized that certificates solved them so the final question if we choose to use certificates is where does the certificate fit in the whole puzzle I found signatures I fit them into the whole puzzle by signing records now I've discovered that I need certificates of some sort because I need to somehow know what the public key is but if I remember from certificates like how does that fit in the puzzle what does a certificate anyway a certificate is someone's public key signed by someone else that you trust but who is the someone else that you trust where does certificates fit in the whole puzzle and so I think and I remember when I talked about certificates I kept drawing these trees and I said like oh the top of the tree and versus the next person in the tree and the next person in the tree and versus the next person in the tree and then I think about DNS and I'm like wait a minute DNS also has a tree so what if I just use the DNS hierarchy。

To delegate trust I kind of like that let's see what that looks like so I remember certificates I could build a tree and then I could start at the root and then distribute trust down the tree。

 but DNS also has a tree so maybe if I just use that same tree to delegate trust maybe everything works out so my certificate chain or my certificate tree is gonna be the DNS hierarchy and I'm going to have every parent name server sign the public key of the child's name server so I'm going say if you trust me I'm going to sign the public key of the next person using a certificate now you trust the next person that's where I think certificates fit in the whole equation。

So I'm going to use that tree。And everyone's going to sign the public key of their next person that's a certificate it's your public key signed by someone else and that's going to delegate trust if you trust me and I sign that next person's public key now you trust them too final question in certificates and DNS to fully finish the design is well we know that someone's got to be the root of trust this question is so simple that it might be like hard who is the root of trust in DNS sec。

I like the root so I'm gonna to make the roots of the DNS hierarchy。

 the root of trust in DNSec as well。 Everyone's gonna implicitly trust the root and they're gonna to distribute trust all the way down the tree Okay great。

 we didn't or I spoil a bunch of answers and maybe you thought about them and so now let's think about what the picture would look like for someone who is not the final name server so we know certificates fit in the equation so let's finish the whole design up by seeing what happens when I ask someone like the root for the IP address and remember the root doesn't know and when the root doesn't know what is it say in English it says I don't know but go ask the next guide that's still the same I didn't change it at all I just copy pasted it from the last lecture but here's the new stuff which is it's not enough to tell you go talk to the next person you have to say go talk to the next person and here is their public key signed by me if you trust me because I'm root you trust me and I sign the public key of the next server Eduu now you trust the next server too。

That's the whole point of a certificate if I sign the public key of the next person and now you trust them to and just like always when I sign something you need a way to verify so here's my public key where you can verify okay so that's the high level idea maybe he feels okay that we're kind of putting these pieces together and so now we're just gonna hammer it all out and then start to think about how to implement it but this is the high level idea of how you would approach it from scratch if you had to design this question。

The question was does the root server send the actual public key or the signature。

 I has a design choice or an implementation choice。

 and so later we'll see that they don't have to send the public key itself。

 but I guess in other designs you could it's a good question though if it didn't make sense。

 there will be pictures okay or diagrams。Okay great。

 we designed it from scratch So what's kind of cool about this the is that with the tools that you have。

 you could design this too， which I find really cool So if you didn't totally follow the design it's okay I'll give you like two big ideas just like in DNS that make the design work so the first big idea was we had to pick a way to secure the record and we chose to use signatures and remember the idea that the name server signs it only they can sign it because no one else has the private key everybody else has the public key so everyone else can verify if I do this properly I defeat the network attackers so I achieve my goal because a man in the middle contrive to modify the record but they don't know the private key so if they modify the record the signature will fail to check out if they modify the signature the signature will fail to check out if they try to modify both the record and the signature they can't come up with a signature and a record that actually check out because they don't know the private key that's all from like the cryptography unit so if I use digital signatures people on the。

Work can no longer tamper so I'm good with that I checked off one of my goals Also remember that whole like object security。

 What if someone messes with things in their cache Well I solved that problem too because when you store the record you can also store the signature with the record and then when someone wants to go into the cache and fetch a record they could check the signature holds up and so now I'm no longer securing the connection with the channel I'm securing the record itself by storing a signature on it and so wherever this record is I could put it in the cache I could store it with the file I could be sending it along a network anywhere I store it if someone tries to modify it。

 I will know because it's always got the signature attached to it which is kind of cool so that's the first big idea which is I had to choose a protocol for ensuring integrity I chose signing and it solve a bunch of my problems Okay second big idea is the public key infrastructure also known as certificates and so this is just taking the idea of certificates and kind of integrating it with DNS so I'm still going use the。

Same hierarchy that DNS used， no need to reinvent that。

 but instead of just using this hierarchy to say oh the root doesn't know， go talk to。edu。

edu doesn't know， go talk to berkeley。edu I'm going to use this tree to say root doesn't know。

 but if you trust root go talk toedu because they're a trusted child and the way that I'm going to give my trust to someone else that I trust is using a certificate I'm going to sign their public key and say you trust me now you trust them。

Anything signed with that key or the corresponding private key is trustworthy okay so that's straight from certificates we talked about how when we're doing certificates。

 we always need to start with a root of trust here is going to be the root name server because they're at the very top of the certificate or the DNS tree and this is going to solve the problem of malicious name servers if you trust the idea that everyone only delegates and give certificates to trustworthy children if you don't trust that we'll talk about it a bit at the end and it relies on realworld business relationships like we've seen before but if you trust the idea that I only sign certificates for people that I know are trustworthy then now if you're a malicious name server you probably should not be able to get a certificate because you're malicious you're not trustworthy in theory okay and that's one that we'll have to look at a bit later and think about business relationships but if you trust that idea then hopefully this feels okay。

Right those are the two big ideas if you like them or if you're happy with them then I think you have DNX at a high level here's a picture of what it looks like again in English just to hammer at home and then we'll try to implement it which will be really fun okay so I'm going to ask the same question I always do is never change the past two lectures I'm going to ask what is the IP address of e。

berkeley eduu my favorite question and I'm going to get back the same answer to start with which is I don't know go talk to the next name server here's where to find them here's their IP address here's their domain name all the same stuff but in addition it's not enough to tell me where to go I also need to know that the next person I talk to is trustworthy because who knows with this person is maybe they're malicious and so the way that I'm going to know the next person is trustworthy is I'm going to say here is a signature on theedduu name server public key that's the certificate it's gonna sayeddu's name servers public key is this I sign it so if you trust me now you trust them because I sign。

A certificate of trustworthiness for the next person， okay？

And so finally because I sent you a signature here is my public key for verification purposes so now you can check using the signature and check using my public key or sorry using the roots public key check the signature generated by the root now if you trust root now you trustedduu's public key you know for sure that this iseddus public key and you know a trustworthy so you can use that public key to verify stuff set byedduu and sign byedduu okay but I didn't get my answer I was looking for an IP address I got all this other stuff so I'm going to go to the next server and ask theedduu name server the same question my favorite question and I'm still gonna to get an answer saying I don't know go talk to the Berkeley doduu name server here's where to find them same old stuff as DNS but in addition it's not enough to say where they are I have to say that the next name server is trustworthy so the doedduu name server says if you trust me and anything that I sign is good like good for you or you know you trust it then I'm going to sign the Berkeley。

edu name。Servers public key， which is to say that if you trust me now you trust this public key and whoever owns it。

 which is the next name server and because I sent you a signature here's the public key so you can verify that the signature is correct。

Okay， but I still didn't get my answer so I keep going and I ask my same question to the Berkeley。

edduu name server and finally I get the answer， but it's not enough just to send the answer。

 I need to sign the record and then give the public key so they can verify the signature。

Okay and finally I got my answer， but not only did did I get my answer。

 I got a signature on it so I know it's correct and I know that it's correct because it was signed by this public key。

 how do I know this public key is good oh because this public key was endorsed by Eduu？

And do ED signed that public key， how do I know do Edu's public key is good Oh because rootot signed it and how do I know root's public key is good because it's root and I trust them so you can also verify the chain all the way back up。

But that's the high level picture okay， so it's the attempt number one because I wrote it in English and so my next step if you're all happy with the high level ideas and the big idea is I'm going to start implementing this in actual DNS。

 what do the records look like， how do I make this all work？That's not just like English。Okay。

Any questions on Zoom I realize I haven't been checking， okay。

Let's implement it Okay again here's your wording again because I'm about to implement this thing for real again there is some stuff that's just not super interesting but I'll bring it up anyway just for completeness okay and so here's one that's kind of interesting I don't really care if you know in total detail but I find the design task pretty interesting so remember that there are8 bits for flags in the DNS header So remember every DNS packet has to follow this format this is like think of it like a form that every DNS request in response needs to fill out this form exactly the way it's built right you can't go into the form and start adding other words anywhere you want if someone gives you a form you got to fill it out nicely got to fill in all the blankks。

 check all the boxes and so someone hands you this form you must fill it out in the exact format and so this particular form only has8 bits for flags there are eight flags each one can be on and off I haven't talked about what they mean but you can imagine they all correspond to some setting okay now I'm about to add DNS。

And so the problem is that in DNS there are extra flags that you need so in the original DNS there were eight bits for flags thatre all used up and in DNSec there's more flags to add I need a flag saying whether or not I support DNS sec or whether or not I want to use regular DNS so I need to turn on the flag if I want DNSec turn the flag off if I want regular DNS I also need other flags like do I care about verifying DNSec or because want to turn it on for fun but not verify the answers in other words there's like extra settings is kind of what I'm trying to get at but the problem is like look at this picture there are eight bits for flags and I have two more flags to shove in I can't extend that flag field it's eight bits everyone understands it's8 when I send a message with ones and zeros everyone agrees that these eight bits or the flags and so you can't just add two more bits for flags that's not backwards compatible if I add two more bits for flags then anyone speaking original DNS will not understand what those two bits。

They'll see those two bits and get super confused by them so I can't just add two bits wherever I want like that's not okay or that's not going to be understandable by original DNS is not backwards compatible all that's to say。

I want DNSec to be backwards compatible。 I cannot just shove into extra flags because original DNS will not understand those bits。

 So like what do I do I'm kind of stuck And so again。

 this is one of those things where I did not design insecur from the start so I'm stuck doing these awkward fixes and so the fix and I don't care if you know the exact fix I just find it interesting what the design solution was basically the actual fix is kind of hacky and it basically says I'm gonna add an extra record because I remember that I can organize things in records and I can have as many records as I want so I'm gonna add an extra record and the only purpose of this record is to store the extra flags and so I look at the DNS header the flags didn't fit so I added an extra record in here in the additional section to add the flag because there was no other reasonable place to put the flags if I was designing DNS X from scratch what I do this No I would just add more bits for the flags but because I need to make it backwards compatible。

 I cannot。That so I need to add the flags in the additional record section and it's kind of hacky as that's why people call it a pseudose and they have this extension mechanism for DNS all of it is because I cannot add more flags to the format the format is fixed so I have to add an extra record whose whole purpose is storing more flags do you find it ugly I find it kind of ugly and the reason why it's ugly is because I need to maintain backwards compatibility and because whoever designed DNS sec or DNS did not think about the security properties from the start so we're left with this mess I don't need you to meorize any of these acronyms but I do find the design task kind of interesting so now you know okay。

So back to our regularly scheduled Inscope stuff you might remember that the DNS records or the DNS stores everything in records every record has a data type and then it maps a name to a value and well one thing is like do you remember when we sent that DNS demo query from last time and we got like 13 answers and like 27 extra additional records like that's a lot of records Im I gonna have to sign every single one separately that would be kind of annoying and so one little trick that people came up with is like a lot of those records they were kind of similar they were just telling me that well if you want to dot youdu name server here's 13 to pick from and here's 27 IP addresses to pick from and like I don't want to sign those all the same separately and so maybe I want to sign them all at once and so to do so you can form a set of records formerly if everything has the same name in the same type you can group them together and just sign them all in a single shot and so all of this is just to simplify my signing my signing process so instead of signing every single。

EDU mirrorrr name server separately I'm just going to sign the entire thing at once and that way it's less for me to sign it's also less data to send so it's faster and generally nicer so that's a design choice that we made okay。

Now it's finally time to encode this extra stuff。 remember there was all this extra English that was written。

 but I didn't actually tell you how to store it in record format originaligin DNS said we're using records so new DNS with DNS I added we're still using records we can't change that so we need to introduce new types without breaking the old types in order to encode stuff like the signature and the public keys。

 those are all stuff that we need so let's introduce some new record types okay one type is called R Sig I don't need you to like memorize it it's probably a cheatche thing but if you have a record of type R Sig it is used to store the signature so I have a record I set the type to R Sig now I can put a signature inside and I don't just have to sign a single record I can sign a group of records to save myself some time remember there were all these statements like here's my public key for verification you can't write that in English So instead we're gonna create a new data type called DNS key if you set the type to DNS key you're storing a。

So that's how I send public keys， I make a record， I set the type to DNS key and then I send that over okay。

And the final weird one that I will' dig into some more is do you remember how we sometimes have to say here's a signature on the child's public key so if you trust me now you trust them。

 that's going to be called DS for delegated signer， it's kind of a weird record format。

 but when you want to delegate trust from me to somebody else if you trust me now you trust them。

 the DS record is going to help with that and we'll see what it looks like I guess in a couple slides。

Okay so I don't care if you know this stuff， but if you're really curious there's all sorts of stuff inside the signature just to make it work usually we abstract it away but since I promised you I tell you the whole thing with nothing oted there it is in full go detail so it's got like when the signature was made when the signature expires what's the time to live what signature scheme that I use that I use RSa that I use something else all sorts of the wacky stuff that is needed。

 but generally we don't really care okay same with DNS key there's some stuff I don't care。Okay。

 take away there's metadata in general we abstracted away。

 but if you're designing this stuff for real right like in project two you can't just wave metadata away if you're designing this stuff for real you too have to care about this but for the purposes of understanding the big ideas。

 I don't really care so they're blue okay。They're also not super interesting Okay。

 what is interesting is that Ds record what the heck was that how do you even store that and so remember the thing in English that I really want to get across is。

You trust me and so I would like to delegate trust to the next person so I need to sign their public key therefore if you trust me now you trust them how do I do that and so there are two things you have to send one thing you have to send is remember like with a certificate you're saying the next person's public key is this signed by you and so that statement the next person's public key is blah。

 blah， blah that's going to be stored in the DSs type of record so the DSs type record will say I' you trust me the next persons e to you here's their public key and then I'm going to send an additional record that signs the DSs record and these two together form the certificate so you don't send the certificate in one record you split it across two one of the records has the statement itself that you want to sign that says you trust me here's the next person now you trust them here's the public key and then the second record actually does the signature okay。

This is also the point， by the way， where because I promised I would show you the whole thing。

 stuff is going to get a little bit mysterious， are you about to ask about the hash？到S。

The DS S key yeah so we have for the public。I'm not trying I totally follow maybe it don'll make more sense once you see it all in total。

 but you will still need the public key because of maybe what I'm about to say So this is one of those points where like things start to get a little bit mysterious and even I can't really explain them so you just kind have to trust me and trust the way that this was implemented so one of the stranger things in this whole protocol is that the DS record I feel like it would work fine if you just sent the public key itself and then signed it。

 but for some reason the designers of DNSX chose to hash the public key before signing it why I wish I could tell you the true reason but I don't know if I had to guess I would say maybe the public keys are very long and by hashing it it's less stuff to sign but genuinely I don't know where they hash it but they chose to hash it so you don't really get the next person's public key you only get the hash of their public key and then you sign it why it beats me but these two records still the hash doesn't change the fact that these two records combined is still tell me what the next person's public key is and gives me a signature on it that way if you trust me。

You trust the next person， but the public key is thrown in a hash for reasons that are kind of beyond me。

Okay， I told you it was unfiltered DNS， okay？So here it is finally our second attempt where I'm not gonna to write it in English。

 but I'm gonna to write it in real record so you get to see them so I'm still going to ask my favorite old question no changes and so here you see the English but I'm also going to show you what it looks like in records so the English statement is I do not know please ask the Edu name server how do you write that in records use an NSS record and an a record literally the same as DNS from last time there are no changes in this first part use the NSS record to say who the next person is and what their domain is use the a record to map the next person's domain to an IP address。

 same as DNS no change okay this part is new here we have to say if you trust me now you trust the next name server here's a signature on their public key how do you do that we just said there's a pair of records that does it you first send the D record which is the next name servers public key with this mysterious hash and then you sign that record and in effect by signing that record you're signing the next person。

Public key with the weird hash thrown in and so this way I'm signing the next person's public keys and now you trust me now you trust the next person's public key with the weird hash thrown in and then finally because I sent you a signature this RIig is a signature you need my public key for verification purposes so here's the DNS key record or public verification purposes it's a public key you use the public key to verify that my signature is indeed correct。

Okay， so I took my English words， use my new found data types RIGS and DNS key to make them into records so that I can store them as records。

 cache them as records， send them using the original DNS。

Okay but I still didn't get my IP address there's no IP address of e Stopberkeley。

edduu so I go and ask again and I ask my same question。

 I get an answer that's basically the same so I'm not going talk through it all。

 but you get the same answer which is I don't know talk to the next name server this is exactly the same as original DNS you get the NSs record in the a record that tell you where to go but it's not enough to tell you where to go you need to also say the next person is trustworthy and remember the way to say the next person is trustworthy is to send the next person's public key in Ds and sign it with an RG and remember there's a weird hash for reasons that I don't understand and then finally I need to send a public key for verification because theeddu name server sent the signature so thedu name server has to send the public key so you can verify that their signature was indeed correct。

Okay final step， I go to the final name server and ask the question this time I get the answer。

 the answer is stored in an a record， no changes there， I want to sign the A record。

 how do I sign it， I store it in an R SIG record， I know that R SIig is used to sign records so there's the signature and just like always I send the public key so you can verify the signature。

So that's the top down approach of looking at it。 If you're still not super cofy with it。

 you can think about a bottom up approach， which is I've collected all these records and I see this answer how do I know this answer is good so I can actually work sorry work bottom up to see if the answer is good so I can start here and I can say this record I would like to know if this record is correct how do I know if it's correct this is signature on it so I can check the signature to see if it's correct how do I check the signature I use Berkeley do Eduu's public key to check the signature and if it checks out then I'm happy that this record is correct or am I because how do I know if this public key is correct what if this is an attacker's public key Well luckily for me I think back to my previous step and I say。

Is this really a Bkeley。eds public key and I go back here and well this person seems pretty confident that it's Berkeley。

edDs public key because they send me a hash of the Berkeley。 EDs public key so I can hash Bkeley。

 EDs public key check if it matches the hash and then they signed it and so I can check this signature to make sure that Berkeley。

edD use's publickey is correct or like as they claim。

And so I can check this signature and if it checks out。

 then I know that Berkeleyedduu's public key is correct how do I check this signature then who signed this the doteddu name server signed this so I need to use doteddus public key to check the signature if it checks out。

 then Berkeley。edduu name server's public key is correct。

But waitai a minute what if this public key is wrong How do I know that thist Edu name server sent me the right public key and is not some malicious one Well luckily for me this public key was signed by someone else so I go back again and I remember that the root sign the Edu name servers public key right this m this DSs record with the public key strangely hashed but I can still check the signature see if it matches and if it does then I know that the dot Edu name servers public key is good but here's another signature that needs verifying who signed this one this one was signed by root so I use roots public key to verify that the signature is correct and if it is then I trust Edus public key and then I trust B U use public key then I trust the signature on the final answer record so it seems like everything is good and then the final step is how do I check that the root name servers public key is correct oh wait this is root they' the root of trust so I trust their public key。

Okay， that's the bottom up approach， if you like it better， you can look at that one。

 the top down approach would look at how the records get sent。

 the bottom up approach is how you would verify them， but either is okay。Okay。

 that's the high level idea， I simply took the ideas from the first part of today and then made them into records so that I can actually encode them in DNS。

😡，Okay。I wish I could stop here and tell you that I'm done and like show it to you in demo form but unfortunately there is one more extra thing and this is the part where like DNSec just kind of starts to fall apart intuitively and I wish I could come up with an intuitive explanation but I can't so I'm not gonna like force you to memorize this but if you're interested and you want to see full DNSec I'll briefly talk through it and then we'll talk about some properties but if you need a break this might be a good time to like check out for a little bit because I'm gonna have to spend like10 minutes explaining this okay but don't like distract other people who are curious because I find a really cool its just things stop to make sense you know how like It know like high school middle school whatever they start telling you about like quantum physics or whatever and things start to be like oh this thing is a zero and one at the same time and it stops making sense like this is where I think we zoom in so far that things kind of stop to make sense at least to me I assume the designers of DNSec had a good reason but I don't know the reason so I'm gonna to make one up okay。

え？Here's my best attempt at coming up with the reason for doing all this crap I it actually the reason I wish I knew maybe some I'll email someone to get a confirmation but here's my best guess is blue because I really don't know if this is the right answer perhaps I've just been telling the wrong thing to Berkeley students for a couple years but here is my guess okay so my guess is that if someone has their private key stolen they would have to change the private key right so I think I think maybe this was sourced from somewhere like maybe I found this on a form somewhere and I thought it was like sounded convincing it sounds convincing to me anyway anyway if someone gets their private key stolen they're gonna have to change it and think about what you have to do to change your private public key pair not only do you have to swap out your private public key pair and like resign everything with your new private key because your old one got stolen you have to throw it away and come up with a new one but remember you're not the only person who cares about your key pair your public private keys your parent also cares because your parent。

Ne server needs to sign your record as well right or sign your public key so not only do you have to change out your private public keys you need to go to your parent and tell them like sorry mom like I messed up someone stole my public key you need to resign a new my new public key and throw away my old public key and that's kind of complicated right like。

Somehow that old one has to be invalidated， you have to throw it away if you have know multiple parents。

 you have to go talk to all of them if there are like multiple name servers at the higher level。

 you need to go to all of them and swap out your public key and so it's just like a lot of extra work and it involves multiple name servers communicating and it's just kind of annoying so it's like if you break something like your parents aren't home and you break something and you have to go talk to them I sorry mom I broke your favor whatever now they have to fix it and now they're not happy so it's just kind of annoying so the solution and like I told you things are about to get weird and so the solutions and not having to tell your parents when you break something is you're going to make yourself your parent okay that's not as weird as I thought it would so you're gonna have to somehow make yourself into your own parent because that way when you break something instead of going up to your parent and saying that you broke it you go up to your parent who is yourself and you say hey I broke something and I'm just like okay and that's it right like there's no one to get in trouble with。

You know like hey me I broke something and I tell myself okay you broke it I rock on right and though we're good okay I know it all sounds super strange and I'm not really sure it's total motivation but it sounded convincing enough to me and so basically the idea is that every name server is now gonna get split into two name servers so it's still one name server in real life but we're gonna split it into two and so that way each name server has an upper half and a lower half and so my chain of trust grows a little bit right and every name server becomes two name servers and so this way in a lot of scenarios the name server's parent is itself because who is the parent of the lower half it's the upper half and they're the same person even though we're going to treat them as two separate name servers and so now when the lower half breaks instead of going to talk to their parent who is someone else is going to get mad at them they can talk to their upper half who is themselves so that way it makes recovering from key compromise in theory easier that's my take。

I guess we'll see here's the example okay's here's what it looks like so everyone's gonna have two halves and so now instead of everyone having just a single public private key pair everyone's going to have two public private key pairs because every name server is going pretend to be two people they're going to like to associate and pretend to be two different people the upper halfs going to sign the lower half so we're going call the upper half the key signing key and the upper halfs going to endorse the lower half and then the lower halfs going to have a key pair called the zone signing key and then they're going to endorse the upper half of the next name server so we're going to go root upper to root lower and then root lower is going to use its zone signing key to endorse ED's upper half which is the key signing key Edu's upper half key signing key is going to endorse this lower half which is the zone signing key Edus zone signing key is going to endorse Bkely the EDs upper half and so so everyone gets split into two and so now a lot of the relationships are upper half of lower half and so maybe that makes things easier okay。

Here's the kind of chain of trust in slightly awkward diagram form so you can see that you know like everyone signs this was without right so every name server has a single key pair the root endorses the next person the next person endorses the next person and then we're done and then now we're going to double the chain right so the chain gets twice as long the upper half endorses the lower half of root lower half of root CSk endorses the upper half of org and the upper half of ors the lower half of org lower half of ors upper half of CS161 org upper half of CS161 endorses lower half of CS161 and having fun yet and then lower half of CS161s the final answer so the chain gets twice as long everyone has two keys instead of one okay so here's what it looks like in you know again in words it's a little bit more annoying but basically I'm splitting into two halves and so。

Here I'm gonna to ask the root name server it's upper half for the IP address The question is going also change a little bit just to make it more intuitive technically you can ask the original question and get everything back in one shot。

 but I'm going to ask this slightly modified question just because I think it looks nicer so I'm going to say hey root name server upper half what are your public keys and the root name server is going to say these things is's going to say well here's my public key KSK that's the upper half here's my public key for verification purposes just like always right everyone sends their own public key that has not changed and so I send my upper halfs public key but I need to now endorse my child so I'm going to say here's my child which is myself my lower halfs public key。

 the ZSK and then here's a signature on that DNS key so if you trust me the upper half I sign the public key of the lower half and now you trust the lower half too so these are the same three records in slightly different format but they still achieve the same thing which is here's the KSk the upper half's own public。

For verification purposes here's the next person's public key which is myself with my lower half and here's a signature on the lower half public key so if you trust me you look at the signature you check it out now you trust my lower half okay now I go to the lower half I asked the question the lower half says I don't know go talk to the next name server the upper half and the lower half of the same person so I didn't have to tell you to go somewhere else just go to the same person for the lower half but the lower half is going tell me to go to the dot Edu name server which is somewhere else so i'm going have to send the NSs and the a records to tell me to go somewhere else okay。

And just like before I'm going to sign the Edu name server as public key。

 so I'm going to use the Ds record and say here's the next person's public key。

 the upper half public key， the KSk signed by a Ds record and then here is the R SIG on the DS record to sign it and remember those two records together give me confidence that the do eD name server is trustworthy okay now if I go to the next name server ED and I ask the same question what are your public keys and it says well I'm the upper half so here's the upper half public key for verification purposes and I'm going to endorse my lower half and so to endorse my lower half I'm going to send the zsk which is the lower half public key and I'm going to sign it with the upper half private key this way if you trust the upper half the upper half sign the public key of the lower half now you trust the lower half and go to the lower half I ask the question the lower half says I don't know go talk to the Burke v E name server and as an A records just like always no changes。

Then I'm going to send a DSs and an R SG record that endorses trust to the upper half of the next name server。

 so the chain continues using a DS record and an R SG record that tells me that the next name service kSK upper half is trustworthy。

 I go to that half， I ask for its public keys。And just like before it says。

 well don't ask the upper half the lower half got all the data you care about so I'm going to endorse the lower half by sending the lower half public key。

 I'm going to sign it and then I'm going to send my own public key so you can verify finally I go to the lower half I asked the question and I get the answer with a signature and just like before I can check this backwards all the way back up this is signed by the ZsK of Berkeley。

edu which is signed by the upper half of Berkeleyedduu which is signed by the lower half ofeddu and you can run this all the way back。

To the root's upper half， which you trust implicitly because it's the root of trust。

Okay okay I realize that things are starting to make less sense。

 I know that that's usually what happens around here。

 I wish I could explain it better but unfortunately that's what we're stuck with and that's what people actually do in real life told you was unfiltered one thing that might help you remember which is upper and which is lower by the way is the key signing key if you look at these upper half queries they don't actually sign real records they don't sign NSS records to tell you where to go they don't sign a records that tell you IP addresses they don't sign answers at all the only thing that the KSK the upper half ever signs is its lower so that's why it's called the key signing key because it only signs the lower half and then the lower half is called the zoneone signing key because the zone signing keys is used to sign all the good stuff like R R SIG on a record on an answer record on NS and A records and so forth。

So the ZSK is used to sign the actual good stuff， and then the KSK is just used to sign the ZSK if that helps。

 okay。So the reason why I want to show this to you is because now I can finally run the DNSec lookup blockthrough just like last time but to do it I had to show you the two key approach because we need to see that here okay or because that's whats gonna to be shown okay I will try to keep a running of all the stuff that gets shoved in my cache so if you wanted what's there but I asked the question and I get this answer and again answer is kind of hard to read I guess one thing I will say really briefly is like do you remember how there was like 13 records but then there were 27 additional records and it was like wait a minute there's like one extra right and here again there's no authority records but there's one additional the heck is that was the ob pseudo section right this is the place where I put the extra flags so。

Like what's really cool about this like try find is that you can read all of this right it was all like gibberish you a week ago but now you have the power to even read this you even know that this is the pseudo section and the reason why it's here is because it did not fit in the original flags I had to make an extra record and show it in the additional section so it's kind of cool that you can even see that stuff showing up here I find it kind of amazing anyway。

Down here we get the two keys here's the upper halfs key and then we're gonna sign the lower halfs key here's the DNS key signature that signs the lower halfs key and so now if you trust the upper half now you trust the lower half now go to the same person 198。

41。0。4 did not change I'm talking to the same person but now I'm talking to the lower half and the lower halfs key me all this stuff and just like before it tells me the NSs and the A records in the authority section I have NSS in the a records I have the A records that tell me where to go next but the only two extra records that show up are Ds and R Zig and remember this pair of records like even if you don't get the two key approach you have to know this part these two records are the extra records that tell me here is the next person's public key technically upper half but their public key and then here is a signature on the above DSs record and these two records team up together to tell me that the next person's public key is trustworthy so even if you don't like the whole two key。

Approach you want to stick with one key you still have to know that this DSs key record gives me the next person's public key and then the R6 signs the above record and these two things together tell me this is the next person's public key and because I signed it now you trust them because if you trust me I sign it now you trust them and again there's a weird hash I don't know why it's there but it's there okay I go on I ask the Berkeleyeddu sorry the edu name servers upper half or stuff and it says well don't ask me ask my lower end here's my upper half public key I sign the lower half public key so if you trust the upper half now you trust the lower half I go to the lower half the IP address is still the 1921 did not change it all and I ask the same question all of this stuff is identical so I'm not gonna talk through it the only new thing the NS records are the same the a records is the same the only new thing is I need to endorse the next name server's public key so I say here is the Berkeleyedduu name servers。

Public key in the two key approaches their upper half in the non- two key approach。

 you can just think of it as Berkeley's public key。

 but in either case I need to send remember whatever in the upper in either case I need to send the upper half public key using the DS record is a mysterious hash that I don't understand then you have to sign it and then by signing it you are delegating trust if you trust me the EduU server's lower half now you trust them the upper half of the Berkeley Edu name server I go to Berkeley Edu ask its upper half for stuff it signs this lower half and then the lower half finally gives me the answer record but not only do I get the answer record I get an R S on it which is cool so I get a signature on the answer record and then later I can go into my cache and verify everything all the signatures all the way back up and then by verifying the signatures I can check that this signature or this record is signed by a public key that I trust which is in turn signed by a public key that I trust which is in turn signed by a public key that I trust all the way back。

Up to the root whose public I implicitly trust and finally we've made it this is full DNS sec you can literally run this in your terminal and understand every piece of it which I find kind of amazing okay but I told it was kind of dense so hopefully it was okay again I don't it's okay if you don't totally get the KSK ZSk part the important part that you do need to know is how you delegate trust from one person to the next and how I designed this in a way that's backwards compatible。

Questions before I talk about some final notes on how to make this all work。No that please。Fs。这气本好快。

有谢系。Its like what your office。course。We have to still learn why you' going。

Yeah it's a great question I think I get it every semester so the question was okay so your motivation isnt super convincing because if the upper half gets compromised they still have to inform their parent and so my only defense to this which I think is probably convincing but maybe not and not even though if it's totally accurate I think the idea is that the upper half it's only used to sign the lower half key so you don't really need to use it a lot it can be like a larger key maybe it's lower to run it can use more secure algorithms like a larger key size and you can also keep this key like stashed away and never to use it whereas the zone signing key has to be used all the time because if someone has a new record they want you to sign you need to pull out the zone signing key and sign it all the time so the zone signing key is more vulnerable to being compromised because you're using it to resign new stuff all the time and change in terms of whatever。

Whereas the key signing key is just used to sign the zone signing key once and then never have to use it again。

 and so generally I think the key signaning key is less likely to be compromised in that sense because you use it less often。

And the Z standinging key is the one that you have to pull out all the time to sign new stuff so use it more often。

 it's more vulnerable to being compromised。I yes， maybe it's convincing or more。Yeah。

 if the upper half key gets compromised， you do have to notify。Okay。

So for anyone who took a break you have to come back now because I have a couple interesting final design things we have to clean up so one of them is how do we say when domains don't exist this is one of those problems that seems like a footnote but the solution I find really cool so check it out okay so all of this is done we built it we did a great job for domains that exist we will always have this beautiful chain of trust back to roots okay but what if someone asks for a fake domain they're like I want to know the IP address of this domain but it is not a real domain it does not have an IP address how do you answer that query and so one option is to not sign it you just say like sorry that doesn't exist and then just send it without a signature okay but that's not great because now somebody could take your message and which has to be signed for an existing domain swap it for the oh sorry it doesn't exist which doesn't have to be signed and now they could like trick you into accepting that domain doesn't exist。

Not a huge fan of this approach so one approach is to say I will sign records if they are records showing me like real existing IP address to domain mappings。

 but for domains that don't exist， I will just say sorry it doesn't exist and not sign it but that's not super secure because now attackers can actually make a record say that it doesn't exist or rather take a record that does exist with its signature and you can't tamper with it but you can swap it for an unsigned doesn't exist message。

Okay that's an approach I don't really like it because it's not super secure。

 Here's a second approach which is I will sign the domains that don't exist on spot So if you ask me for fakeone dogo do co IP address as the name server the name server will say that doesn't exist and then sign that record and then send it back to you as a second option but there are a couple issues with this one issue is as we just said。

 you need to keep that private key around because people could be asking you all sorts of unexistent or non-existent IP addresses and domains and you're gonna have to sign every single one saying that it doesn't exist so one it means that you have to keep the private key close by and use it a lot which means that it could be compromised and secondly this is slow because now you have to generate a signature every time someone asks you a question and we'll see in like one lecture or so that that could actually lead you open to denial a service attacks you don't know what that is yet we' talk about it next time but。

The idea is that both of these are not great approaches Op one says don't sign and that's not good for security option two says sign up on the spot when someone asks you but that could be slow because now you can't prepare signatures ahead of time and now you have to sign in real time which is slow and it's not as secure because you have to keep the public key close by to do all the signing and that could leave you vulnerable。

Okay so I don't like either of these approaches I would like to be able to sign ahead of time and say that the domain doesn't exist so when someone asks me about a domain that doesn't exist。

 I can just hand them a certificate of like nonexistence I shouldn't say a certificate sorry I should say if someone asks me for a domain that doesn't exist。

 I can send them like a message saying this domain doesn't exist with a signature on it and they accept it but I don't want to have to sign onde signing on demand is slow and not secure so how do I do that well one option is what if I just sign every nonexistent domain ahead of time and I can just give them the record and the corresponding signature when they ask me for one of those non-existent domains but like think about how many nonexistent domains there are。

A lot right like exponentially many like if you want to list out all the domains that don't exist。

 you're gonna have a hard time listing them all up fake one fake two， fake3。

 fake four and that's just the ones that start with fake there's a lot of them and so I cannot sign all of those ahead of time it's too slow and storing all those signatures is also very slow and so the idea it's called N second I find it very genius which is don't sign a single domain that doesn't exist instead sign a range of domains that doesn't exist so instead of signing fake one doesn't exist Also fake two doesn't exist Also fake three doesn't exist and coming up with different signatures for all of these you're going sign an entire range of records and say that they don't exist so。

If I asked for nonexistent go co which I'm pretty sure doesn't exist。

 I could either ask the name server to sign onde a message Taylor made for me that says nonexistent。

google。com doesn't exist but that's really slow and so instead I could have the name server sign ahead a time say something like this it could sign a message saying there are no valid domains alphabetically between maps googlecom and onegogle co so mapsgoogle co exists onegooglecom exists anything in between alphabetically doesn't exist that's the message and I sign that message and so what's really cool is by signing this message you now have taken care of every single nonexistent domain in here and when someone asks you for a non-existent domain in here you send them this message with a pregenerated signature and then when they checked that the signature matches out they know that this came from the name server and so they are trust and if they trust the name server they believe。

That there are no domains between those pair of domains it's pretty cool right and so now how many records do you have to sign remember in the original approach you sign on demand you have to sign like infinitely many non-existent domains what about now？

How many records do you have to sign I have to sign one saying there's nothing between maps and one it's an empty void there's also nothing between one and web empty void anything between these two alphabetically doesn't exist and finally there's nothing between web and maps if I like roll around the alphabet from Z back to a there's nothing between webs and map either so in total there are three records and just those three records is enough to tell me that all other domains don't exist it's pretty cool right so it's a really cool approach like I don't think I would have come up with this but someone apparently did so good for them。

Okay， it's called NSEC， this is a way to deny that something exists in a way that has authentication that's signed。

Okay。There are a couple issues at this so one issue is that and this one whether or not it's an issue I would say actually kind of depends on your personal opinion so what if you wanted to know what all the valid subdomas are so like have you ever wonder like hey what are all the subdomains of Google they probably have a bunch that we know like Mapst goo co mailgogle co what if they have like a top secretec one for something that they're building right now or maybe they have one for like employees or something super secret that I want to use for a attacks tax what if I want to know what those domains are in general there's no way to know it you can't just go and ask Google maybe they won't tell you but maybe with this NSsec approach someone can find out because what if the query for a do go co which doesn't exist and I get back this record which says webgoglecom is real APgoglecom is real and nothing in between is real and so somehow by asking for this non-existent domain name I have actually learned two domain names that do exist which I might not have known before。

And that's kind of bad maybe and so I could also repeat this again and again and cycle all the way through the alphabet and I could say what if I try another letter like aPA。

google。com and I say does aPA。google。com what's the I address and the name server says that's not real to prove to you that it's not real I will sign a message saying that A is real A is real and nothing in between is real I'll sign that message to prove to you that APA。

google is not a real domain and so you're like okay thanks I believe you now but I have also learned which I might not have known before that apps。

 go。 co is real。So in other words， by running this by running a query or like making a DNS query for a non-existent domain using NSSec。

 I can actually potentially leak or learn domain names that do exist that are coming back to me because of the way this is built and you can imagine looping all the way through to find out what all the valid domain names are you can enumerate them right so I could ask for the one after apps and then I was tell me nothing things between apps and web and since I loop back to web I know I found long so that's kind of dangerous okay。

And so well one I guess like philosophical question is do you find this dangerous at all so some people will argue this is dangerous they'll say well yeah it' dangerous because what if Google has a secret domain like a subdomain like secrets。

go。com or like examsolutions。161。 org that they don't want students or employees or outside people to see and so if by doing this enumeration attack an attacker could find out domains that Google doesn't want people to see so that's one argument is to say this dangerous it leaves you open to a attacks another like philosophy that maybe you like better is to say like actually I disagree I think that if Google wants to keep their secret secure。

 they should not make a domain called secrets。google co they should call us something else that doesn't leak that information or like if you leak that website that website should be secure in the first place if someone knows that that website exists it's Google's job to make sure that they can't do anything bad even if they know the website so this kind of two schools of thought here and I think it's kind of up to you。

In your opinion which one you prefer so some people say this is an issue you shouldn't leak secret domain names other people say you can leak domain names who cares domain names were not supposed to be secret and it's your job to make sure the thing at the domain is secret which do you prefer I don't have an answer's your opinion okay but since some people agree that it's an issue they have attempted to make a fix and so the fix is called Nsec3 and the idea is just instead of taking every single domain name here web app and apps and alphabetizing them and then coming up with ranges in the alphabet I am instead going to take all those domain names and hash them and then alphabetize the hashes it's kind of a weird approach and so the new message instead of saying there's nothing between web and apps I'm going say I'm gonna to hash web I'm gonna to hash apps and like the order can change right like when I hash things they go to unpredictable places and so the order of the domains and their hashes could be different。

But I can still send a message that says something like this There are no domains that hash to values between this one and this one you can assume you order them in like hexadecimal or alphabetically or whatever but basically what we're saying is if you take non-existent Google co and you hash it if it falls in this range this statement tells you there's nothing that falls in that range of hashes So instead of coming up with ranges of words you're going to take all the words that exist you're gonna hash all of them and maybe the order of the words changes。

 but that's okay you just have to hash all of the empty space in between all the hashes of words So in NSec you're hashing empty space in between words in NSec 3 you're hashing empty space in between hashes of words and you're saying take your nonexistent domain hash it if it falls in one of the empty ranges you know it's not really and what's good about this is that reversing this hash is presumed to be hard。

O。And so that's an approach that fixes it if you would like to be opinionated you could say actually I think people choose real words for their domain names and so I think that brute force in this hash is actually doable because if the word is like secrets or exam solutions。

 I think I could brutefor that okay， maybe you think that's true， you know go invent Nec4。

 insect sec5， but I guess that's a possible opinion you can have okay so all this is to say that NS3 is a possible defense。

 if you find this to be an issue， although some people don't find it to be an issue。

 and if you think that brute force into hashes is an issue。

 then you have to go and design something different。Okay。So I'm almost done。

 I have three minutes to tell you how this looks in practice。

 I guess these were blue because I ran out of time last time and I guess I'm running short on the time this time as well。

 but I find these pretty important so I'll talk to you about them but I guess they can't test on them because it's only three minutes left so one thing that is really good about DNS sec or like something that's really critical to his design is that the signatures can be generated separately so as we saw in like NSec we don't want to generate signatures on demand because that's slow and it involves keeping the public key around which is kind of dangerous and so one thing you can do is you can like take your private key and like walk yourself in a room with no internet that's super top secretec secure and then generate all the signatures offline without being connected to the internet with the private key and if you do that nobody can hack in if you're doing this super securely and then you take just the signatures and then you give the signatures to someone else who is connected to the internet and then they。

The signatures to everyone else and so the great thing about this is it's efficient because you sign everything ahead of time and so when someone asks you for a record it's already signed that's great and then the second benefit that's really good is that this is good for security because now if someone compromises the name server and they try to like break in and they see all the secrets what do they find they find a bunch of signatures but they don't find the private key to generate more signatures because that private key doesn't live on the server connected to the internet it lives in that secret room in the back where you generated the signatures yourself offline so if you keep the signature generation system separate from the name server that's really great because now someone compromise in the name server does not actually know your private key which is great and then another really good thing is that you can take these signatures and give them to tons of different name servers like the mirrors where they all answer the same question and so this way of one of them goes down all the other one stay up and you don't have to give the private key to every single。

Nrred name server you are generating the secret keys or the signatures with the private key once offline and then giving it to everyone else and everyone else just has to have the signatures they don't need to have the private key so it's a really good approach in fact I've talkedgged myself that this is so good that I think you should know it so I'll make one slide in scope if that's okay everything else you can keep thatoscope is that okay no complaints okay offline signature generation is really important because this is really what makes DNS efficient is the fact that you generate things offline and then you distribute the signatures to everyone else okay sorry everything else I promise I'll leave thatoscope okay so one thing you can do is you can verify signatures in parallel。

Enough about that you need to be careful how you implement this stuff because you can mess up offset about that this happened once with like major streaming services apparently like they launched and then they like broke I don't even HBO go even like exist anymore I don't know that' because HBO go even like exist anymore I don't know but you need to be careful to implement correctly or else things can break one final thing which I guess has been in scope the whole time is that you need to be careful that you actually check the signatures because if you don't check the signature someone can still attack you and give you bad signature so you do need to validate the records in particular one thing that a lot of people do that's messed up in terms of incorrect DNS implementations is if we look at this diagram sorry I'll get you out of here in one minute okay one thing that people tend to do is they ask the recursive resolver recursive resolver please run the DNS that query。

Everything securely verify the signatures and then give me the answer and then when I get the answer I don't verify the signature well that's kind of bad because now the recursive resolver could give me a bad answer and I'd never know because I'm not the one verifying the signatures so if you choose to use DNSec you need to actually verify the signatures you cannot ask someone else like the recursive resolver to do all the work for you and then you receive the answer without verifying the signature because then the recursive resolver could be a man in the middle and give you a bad answer。

Okay。So that's it for DNS tech sorry if for're going a little bit over you can pack up I know it's a little bit of a dense lecture but again I find it really cool to see all the pieces work together here is your summary I'll talk through it for you next time Okay sorry it was one minute over see you next time。

嗯。

![](img/82d2df7f47e22d165c245fad27d5d270_2.png)