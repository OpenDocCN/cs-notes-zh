# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P52：51_安全技术：公私钥与SSL协议.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

So welcome to our lecture on public key encryption where we're going to go back to confidentiality and so here we go。

 if you recall， we've been having these two topics that have been our theme throughout just some grizz oh sorry I'm starting to talk in Ro 13。

 let's translate this back to nonroute 13 the terminology。

 the two kind of themes we've been following over the last couple of lectures in this lecture are confidentiality and integrity and confidentiality is hiding shielding information。

 not leaking information to people that you don't want to show it to and integrity is making sure that you know who you're dealing with and then the previous lecture we really talked about kind of real light approachable ways of ensuring confidentiality with things like Cesar cipher and then integrity using a simple message digest that based on a shared secret So the problem with all of those things that we just saw。



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_1.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_2.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_3.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_4.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_5.png)

Is that they require a shared secret and the problem in the world of the internet is its just really difficult for every one of us before we establish。



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_7.png)

Before we can make any purchases or whatever at Amazon that we somehow have to drive to Amazon headquarters and get a shared secret from Amazon。

 they'll open up a book and say， okay， hi Chuck， I see who you are and here's our shared secret and you walk away。

 and as long as you carry that shared secret where you go and if the shared secret is lost。

 it's a difficult to reviewvo so as the internet and frankly in general as security needed to be able to work at arm's length。

 meaning that you couldn't always bring everybody together and hand out shared secrets and then have them go to the far reaches of the world and communicate public key encryption was identified as a extremely elegant solution to this problem and so it was proposed by diiffy and Heman in 1976。

And it relies on two keys， it's asymmetric， meaning we're not using the same key to encryptpt as decrypt the way we were in the previous lectures。

 these are asymmetric。 there is a public key which is actually does not need any protection whatsoever in a private key and the idea is they're generated inside of a computer you generate the public key in the private key you send out the public key。

 the public key is used to do the encryption and then private key is used to do the decryption and they're related mathematically in a way that's well understood but difficult to compute for a key length that's large enough。

 so there's a public key and a private key， so I like you to take a look at this little video up on YouTube of diiffy Heman and Merkel the inventors of this。

And I think it's a great video， I would love it if this were my video。

 but I didn't produce this video， so take a quick look。

So one of the things about this public private key encryption is not that we know about it。

 it's like whoa， it's pretty obvious and frankly Caesar and the Germans and everybody could have used this idea。

 they just hadn't thought of it yet and another thing that's kind of interesting if you look into the story of this is that。

The first reaction people got when they start thinking about this is like it can't be this easy it's sort of both easy and hard but but the concept is real elegant and really beautiful and that is that we have this public key So the public key is part of a public private pair and it's used to do the encryption the beautiful beauty is it's computationally difficult to recover that private key from the public key and the encrypted text a key thing is it's not impossible and that's kind of one of the interesting philosophies of security that we started at the very beginning of talking about security the perfect security is kind of impossible to achieve unless you simply don't send anything。

And so。Public private key asymmetric keys is well understood as to how you would break it。

 Everyone knows how to break it。 The problem is is that computers aren't fast enough to break it and when computers get faster we'll just make the keys bigger。

 So the mathematics of this makes it impractical to break I mean， literally impractical break。

Now I think we can safely assume that governments probably have enough computation to crack these once in a great while。

 I mean if they're not cracking every transaction between you and targetrget when you want to buy something。

 but if they really have to they can record the encrypted transmissions and if they really had to and took a long time I have no idea how long it would be。

 they can break it， so that's actually kind of a neat way to think about this by revealing it all。

 frankly any computer scientist could make a name for them their whole life if they proved that there was something wrong with this by revealing the algorithm revealing the cracking technique。

 if someone can come up with a better cracking technique， it is like fame and glory forever。

 which means that we're pretty sure that there's no good way to crack this other than the brute force mechanism that requires a large amount of computation。

So。If you're going to use public private key encryption， you have to generate a pair。

And it starts by choosing two really large random numbers with hundreds。

 if not thousands of digits that are primeed。So you kind of choose a random number really big。

 and then you kind of look around for a nearby prime number and you choose two of those。

 and then you multiply them。Okay， getting an even larger number。And then through some steps。

 through some calculations， you compute the public and the private keys from that large number。

 the essence of this are those two prime numbers， prime numbers of course are numbers that you only divide by themselves in one。

 which means they have no factors， which means they're kind of like looking for a needle in a haystack。

And so the public and private key is really based on these two prime numbers if you could figure out what the prime numbers were。

You'd be okay， but the computational difficulties is finding the prime numbers that are extremely large and finding the right prime numbers that are extremely large。

So it's easy to do some calculations in one direction but not in another， so for example。

 what are the factors of 55124，159？

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_9.png)

Quick， but if I simply ask you， what do you multiply 70919 to get that 55 million number？



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_11.png)

That's easy。 You do a division， and it turns out that you can find out 69，61 really easy， right。

 So if I just say what are these two numbers。That's hard。If I say given this number。

 what's the other number， that's trivial， so you can think of this as。

The decryption is where the receiver of the message knows kind of half of the calculation。

 whereas the world doesn't know either half of the doesn't know the calculation。

 so it has to figure out both halves， whereas the receiver only has to figure out one half。

 And so that's how asking the question of what are the factors versus given one， what's the other。

 So it takes a problem， it's easy， makes it computationally nearly impossible， but again。

 not impossible， just nearly impossible。Okay， so here's the notion。

 so you're about to type your visa card into a credit card into like Amazon's web page and so what happens is is that Amazon will has a public key and a private key that they retain and they will send you the public key across a medium the internet they're going to send this to you somehow。



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_13.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_14.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_15.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_16.png)

But。The bad guys， Eve or Charlie or whoever they are。The bad guys， this is。



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_18.png)

Tals and Bob。Even Charlie are always looking， so even Charlie kid intercepted and you assume that they can。

 this is the key， don't try to pretend they can't， even though it's very difficult for them to do it。

 but you assume they can， so the public key comes across it is simply sent to you as part of the beginning of establishing a secure connection and the bad guys see it too or gals。



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_20.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_21.png)

![](img/4e5ff96b8e8eacebf67d4e0714cd7910_22.png)

They see it too， so the public key comes to you， and then what you do is you encrypt。



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_24.png)

Using that public key and create some encrypted text， ciphertext。

 which you then send back across the danger where Eve and Charlie are watching。

 and it comes across they intercept the encrypted text they've intercepted the public key and they can try as hard as they like with supercomputers to derive this and frankly。

 like I said if they had months and months and months and really fast computers。

 they could okay but because Amazon is in sole possession of the private key and it never left Amazon servers。

 it is a very simple matter for Amazon to be crypt and get your plain text that happens very quickly。

 just like if you kind of no half of the prime number calculation。

 figuring out the other prime number is really really easy。So so again。

 these people see all this information and yet is computationally virtually impossible for all practical purposes to do it。

 and so it's beautiful because there was no need to protect the public key we never had to get in the same room and away it goes so you just Amazon just blast out its public key and we encrypt using Amazon's public key。

 we can't decrypt it， but we don't need to decrypt it。

 All we need to do is send it to Amazon andvoila， it works so the beautiful thing is is the public keys can be distributed they can be intercepted and it does not matter。

So。With this notion of public private key encryption in general， we made a change to HTTP。



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_26.png)

A layer， a mini layer is in the data model。 If you remember way back。

 perhaps you even forgotten about the layered model。 Remember that layered model。



![](img/4e5ff96b8e8eacebf67d4e0714cd7910_28.png)

Application， transport， Internet。Remember， this is sort of one computer and this is the other computer。

 these are the routers， routers， these are the hops。There's like 15 of these。 Remember。

 remember all this。So it comes back now on us okay， so if you recall。

 just sort of to briefly remember the transport layer is responsible for the retransmission。

 it gives us the appearance of a reliable ordered connection between our application and the FAR application。

HtTP is one of the application protocols， and so there is a little mini layer that is layered in sort of seamlessly on top of the transport layer。

That basically takes plain text and encrypts it and turns it into cipher textex。

 and then cipher textex on the way out and turns it back into plain text。

OkayAnd so what happens is is these applications just send plain text and out comes plain text and there's a little bit of extra glue in the middle here that's sort of a secure transport secure sockets layer。

 this is this thing here is often called a socket S OCK I'd be good if I could spell socket So this is a socket and then the red part is a secure socket。

So the applications kind of don't encrypt the data at all， there is a library that encrypts it。

 and the other thing is is that all the rest of the internet， the internet， the link layer。

 the routers， nothing， the ethernet， the fiber， they don't even know the difference betweened text and noned text because the encrypted text wanders around fully encrypted。

Adddresses are not encrypted， and so it stays encrypted all the way through the entire network。

It actually， if you then think about the fact that this is the moment that it leaves your computer。

The only thing so the plain text comes in here gets encrypted here， encrypted comes down。

 the only thing that leaves your computer is encrypted text， and it makes it all the way across。

 the encrypted text goes into Amazon， so this is Amazon。This is you。The encrypted text。

Find its way through all these things。And it comes in encrypted。

 and it actually doesn't get encrypted。Until it's sort of right at the point where Amazon's web server that's going to actually charge a credit card。

 So this is actually beautifully elegant in that。The rest of the network is blissfully unaware。

If any encryption is happening， it's just moving the data， so this did not require any change， again。

 the beauty of a layered architecture did not require any change sort of below the transport layer。

 and as a matter of fact， all of the sequencing and retransmission that happens in the TCP layer that happens with the encrypted stuff too because it's just encrypted。

 it's just text it's gibberish text， it's not the original visasa card number that you're sending。

 you're sending one，2，3 and out comes you know Wx Y， the WxY just goes it retransmitted。

 all this crap just works it's like。Beautiful， it's a beautiful thing。

 It's absolutely beautiful thing。And it's just like this mini layer kind of between the app it's like the top slice of the app transport layer that's how I'm drawing it right here it's like this little kind of top extra little thing says you know what we're gonna transport but actually help you out and give me some encryption while we're at it and there's all kinds of cool stuff that goes back and forth the public and private keys get exchanged that's all kind of stuff we don't worry about we just send data and get data back。

Pty cool啊。So this really solves the problem of the fact that we basically should assume that everything between our computer and the destination computer。

 this is you。This is Amazon。Right everything here， this is all dangerous。

 there's some like terrifyingly scary individual that's watching everything doing packet sniffing。

 this might be Eve， the eavesdroper。This looks like a little heat。

 It looks pretty tough right and so that even the wireless， right， This is the wi-fi connection。

 the w-fi is dangerous。 Now， the reality is is these things aren't all that dangerous。

 The Wifi is probably the weakest link of these full things。

 But we have to assume that it's dangerous。 we want to assume that the only thing that's safe。

 and unfortunately， if you put viruses in your computer， then they can get at the plain text。

 if Amazon loses its data somehow。 then they get the plain text， right， but but basically。

 you know we want to distrust all of this。 So this concept is called transport layer security。

 also called SSL also known as Https， HtTps for secure。

And it's kind of like between the TCP layer and the application layer or the top half the TCP layers the way I like to think about it。

 it's because it's based on public private key encryption， it's difficult but not impossible。

 normal people don't have the kind of equipment to break it and even governments if they can break it。

 I don't even know I'm not an expert， I don't hang out with the government。

 so I don't really know but assume that if they really put their mind to it in a very narrow situation。

If you become really interesting， they will find your credit cards。

 probably there's easier ways to get your credit cards than by decrypting your text。

 so it's hard to decrypt。And as I mentioned， because of the layered architecture， the TCP layer。

 IP and link layers are completely unaware。So you see this in the form of URLs that start with HTTPS。

They start with HtTPS。Wfacebook。com versus HtTP， and there was a time a few years back where you know they were it used to be a little more expensive inside of the servers to do HtTPS。

 that still is。And so some sites would try to do some of their activity without using secure protocols and others would use non secure and secure it and flip you back and forth。

 like if you're typing your password， the problem was is that there was actually still sensitive data being sent even across the insecure。

 and there was quite a famous thing where people could install a Firefox plug in and watch Facebook。

Non-sure Facebook things go back and forth across like a Starbucks and then we just show you all the people's Facebook accounts and you could log in as them and post as them And so you've seen a situation where companies are just starting to use HttPS for everything you as a user have to be aware to see if you're typing anything sensitive。

 never  type it into a URL that doesn't say HttPS okay never do that， you're typing password。

 credit card number， any kind of personal information。

 make sure you're doing HttPS and make sure that。That you know what it is。

 we'll talk about that in a bit we'll talk a little bit more about that in a bit so if we take a look and we think about where the bad guys are at。

 the bad guys are kind of everything and the secure TCP runs is the one part of the layer of our architecture that runs from within your laptop to within the server and so then if we kind of assume the worst the backbone is pretty safe。

 the w-fi is probably the most dangerous。Right， but when we do secure system TCP secure system to system TCP。

 we are doing the encryption right here inside your computer before it leaves。

 and we're only doing the decryption right when it comes back into computer。

 So the decryption and encryption are happening inside of Amazon's computer and inside of your computer and nothing else。

 So secure sockets is pretty good。 Now， the place where you're still danger。

Is there might be a virus that's watching your keystrokes right。

 this is why virus checking is so important because at some point you're typing it into your computer and the greatest danger you have to losing in your data is really。

Two things， one that you've got a virus or B， somebody has redirected you not to talk to E Amazon instead of Amazon。

 and that's what we'll talk about in the next lecture。How to know。

 how does these browsers really know they're talking to the real Amazon。

 and that is not confidentiality， confidentiality is stopping the bad guy from seeing what you're sending。

As their eavesdropping Eve。Is eavesdropping。Okay now the next thing is the question of is this the real Amazon or is this a fake Amazon。

 so we'll talk about that next。