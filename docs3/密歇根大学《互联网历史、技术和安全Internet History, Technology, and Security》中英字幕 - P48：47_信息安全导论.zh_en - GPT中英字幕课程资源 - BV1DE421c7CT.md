# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P48：47_信息安全导论.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

Hello and welcome to our security lecture I'm Charles Severance and I encourage you to grab the PowerPoints and remix them and use them in your own courses。

 use the videos， use everything in your own courses。

 you don't have to teach this whole course it's quite a bit so。

So let's start out by meeting some nice people， these people are Alice and Bob and they simply want to communicate some information。

 you know， left to their own devices and they don't want the rest of the world to know about what they're communicating and so they want to encrypt it some way Now in thep cryptography world。

 they allll call these two people， the good people Alice and Bob and they simply are A and B。

 kind of a very computer eque variable names A and B and Alice and Bob and then there's some bad guys right there's the bad guys。

 and and often they are called C like Carol or Carlos or Charlie or something like that they're even Chuck even Chuck is a bad guy are Dave or Eve Eve for the Eavesdropper and the idea is somewhere in the middle here。

Somewhere in the middle， you have some person with bad intent here。 we have Trinity from the matrix。

 and she looks she looks as bad as you can look， right？

 So Alice and Bob seem to be real happy people and they're just trying to get you know。

 get things done and send some information without being bothered。

 And then and the Trinity's there eavesdropping。 And but there's other things。 You can eavesdrop。

 You can sort of redirect the message and change it。

 There's all kinds of things that the bad guy in the middle is going to do。

 And so Alice and Bob are far away from each other and they have to communicate securely。

 and it's a literal gauntlet of problems that they have to face。

 And various people with bad intent with bad purposes。

 sometimes just wanting to see what's going on versus wanting to change what's going on。

Versus completely redirect communication。 So Alice， Bob。

 and then a whole series of bad guys with various bad guys and gals with various evil intent。

So it's always fun to talk about security because the question is is you and what does security mean to you and what does it mean to me？

And whenever you you're thinking about security， you got to figure out sort of who is out to get you and why are they out to get you？

And for us， average people。We are so boring that literally pretty much the only thing the world wants from us is they want to steal our。

You know，They want to steal our credit card numbers and then buy stuff with them for just a couple of days before the credit card company shuts them down。

Now if you're running for public office， there's a whole bunch of your opponents that are going to want to break into your email and that happens right those kind of shenanigans happen。

 so if you're interesting or influential or running for public office you have a different problem than if you're just kind of a mere civilian like us。

And so。At the end of the day， you can worry about security and you can kind of wear tin foil clothing or something。

 but at the end of the day， you and I are so boring that nobody really cares。

 but it's good to assume that they're ought to get you right that you try to be as secure as you can and be aware of your environment and be as secure as you possibly can with your information and with your communications。

So who is out to get us？Well。The government， so now we're going to actually turn the tables。

 right in the very first lecture， we were the good guys。

 The good guys were the ones who are trying to break the carptography and the bad guys were the ones that are trying to hide their their their bad messages and the government were the good guys in Bletchley Park and they they broke the codes and they they saved Western civilization。

 Yy， good guys。 Well now。We're the Germans。We're the Japanese， we're trying to communicate。

People watching。And guess what Here's the same people government government's most likely interested in what you're doing Again。

 most of us are so boring the government doesn't really care at all。

 but the government has probably the best security breaking equipment on the planet right now better than the criminals。

 And so it's just an interesting flip of a model right where now we are trying to communicate and the government with all of their bombs and little rotating devices sitting in some。

Warehouse somewhere that we don't know is taking our private communications and they're trying to break them。

And we are in a war trying to make our communications more and more secure while the government says。

 whoa， we have to invent like electronic computers。

Because we have to have bigger computers because the people at us us good guys now who are doing the encrypting。

 we are trying to come up with more and more clever ways to encrypt and the government has to keep coming up with ways to decrypt and you could cast this as criminals versus good folks。

 you could cast as governments versus governments At the end of the day。

 it's an arms race and it's rather symmetric as to which side you're on right， I mean。

 we started out with the people trying to hide the information we're the bad guys and now we're the good guys Why are we the good guys because it's us as soon as we decide it's us We're the good guys。

HereHere's a little picture I took a couple of years ago when I visited Bletchley Park this actually led to the video a year and a half later and in this my friend who works at the Open University who also does massively open online courses that's Joel he's now retired。

 he's the tour guide there in a dearer and personal friend and and another of my dear and personal friends whose face you can't see is right here。

 his name is Chuck， he currently works at Chizam in London and he and I just got away for the weekend and went up to Bletchley Park and took a tour not just just a little interesting connection I sort of mentioned in a previous lecture about the Matrix so you noticed that Chuck here is wearing a jacket from the movie Matrix I mentioned he was the one that wrote the hacking scene with Trinity。

So here we all are together， we're at Bletchley Park， Alan Turing had an office in this。

 this is one of Aent Turing's offices at Bletchley Park， here's Joel open teachingching and Learning。

 here is Chuck worked on the matrix and here's Trinity。Right。

Except that not Trinity is our enemy instead of our friend。

 although in the movie we are rooting for Trinity， but we are the ones trying to protect what we're doing from the Trinities of the world we're the good guys now and Trinity is the bad gal okay she's the bad lady trying to break into our stuff and we're protecting ourselves against Trinity so tables have completely turneded okay。

So。Before we go too far， you know， you'll run into your organizations with lots of people who are like security experts。

 and I find security experts generally very。Annoying。

Because they like think they're smarter than they are。

Security experts have this theory that more security is better。And the reality is。

 is that perfect security is unachievable if you want perfect security。

 like lock yourself in a room and whisper to somebody。

 oh wait a sec and then the guard will come in and hear you or whatever， there'll be a microphone。

So the notion that perfect security and that your company can spend more and more and more money of its budget on security just because the security expert thinks that you should is really kind of a fallacy。

Security is a cost benefit analysis， and so if you think of credit card companies。

 you know what's the security of this number？I won't show you the number。

 but what if I lose this number， what's the consequences。

 I've had many credit cards that got compromised I don't exactly know how they've got software inside of the computer companies that catches like when all of a sudden I live in Michigan and a bunch of charges at the New Jersey Walmart are showing up and I never got on a plane。

I'm amazed at how rare it is that your identity actually gets lost permanently。

 So I'm really impressed with how the banks are capable。

And so they have this number that makes it real convenient for us to buy。

 we can type it into a web form， we can do all these things and one in a zillion times it gets compromised and so they lose 50 bucks。

 but billions of dollars of commerce happens so there is always a security versus cost if basically for me to use this credit card I had to have sort of a personal guard from the company with me all the time。

 it'd be very expensive for me to buy stuff on Amazon and how to ship to my house and so understand that when you start getting into conversations with security。

But professionals， sometimes they're the kind that understand that security is naturally imperfect and everything is a cost benefit analysis rather than more security is always better。

 so more is not always better。That's just my little speech about security in case you get stuck in a conversation with some pompous security expert。

 they're mostly pompous。So。Daabase administratorr Pomp is too。

 but hope you're not a database administrator， security expert。But。

The best security experts that I've ever met are the ones that understand this and they can characterize every issue in terms of a cost benefit analysis。

 and then you know that you've run into one that's really smart and bright。

So the terminology that we're going to use for the rest of the segments of this lecture。

 we are going to be solving two basic problems。One is confidential confidentiality and the confidentiality is the leakage of information so if I was to want to send this credit card number to one of you watching right now without the rest of you seeing my credit card number the mere revealing of that information is the problem so I want to come up with a way to send it to you so that no one except the one person that I want to see it gets it that's confidentiality。



![](img/e864b38eb2c44a12ceff3f0c71c83cd6_1.png)

The other problem is one of integrity， and that is， in a sense， knowing that a。

That the information that you've got comes from who you thought it came from。And B。

 that it wasn't modified on the way。So there are things like digital signatures that sort of fall into this category and other mechanisms that we'll talk about so these these two themes of confidentiality and integrity will run through the rest of the lectures that we have on security okay。

 so coming up next we're just we're going to start diving right in。



![](img/e864b38eb2c44a12ceff3f0c71c83cd6_3.png)