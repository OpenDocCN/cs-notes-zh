# 027：UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p27 -27--CS161 FA23- Lecture 27 - Bitcoin.zh_en -BV1YGbceREDs_p27-

Thist dead。来电。Batteries charge。Okay。So welcome everyone。

 Perin recruited me to give my full Bitcoin lecture。

 so it's think of it as slightly less technical content and a lot more snark because I've been having to deal with this for a long time。

されてくらんです。也呃。Ohold on。Go it。

![](img/c3f70e0df0dd33026cc4ea03964da203_1.png)

O。Crat。They got go to the notice。

![](img/c3f70e0df0dd33026cc4ea03964da203_3.png)

Is there no else？There's no mouse because it's in keynote display mode。Oh， there we go。



![](img/c3f70e0df0dd33026cc4ea03964da203_5.png)

Got it。Okay， able to hide that。

![](img/c3f70e0df0dd33026cc4ea03964da203_7.png)

We are good to go。

![](img/c3f70e0df0dd33026cc4ea03964da203_9.png)

Oh， I have to share my screen again。呃。Where's zoom。Share screen。Share。呃。

Hide floating meeting control。Now。Yay， so this is a tweet back from when it was Twitter that kind of summarizes the space really well。

 you're not getting my rant on AI this time， but here's my algorithm for when I want to use machine learning to solve a problem。

I need to build a pattern matcher。I have no believinging clue what I'm supposed to look for。

When I'm done， I still have nobleeping clue what I need to look for because otherwise。

 I'm going to throw out the machine learning and code a pattern match。

 and it's okay to be hilariously gobmackingly， amusingly wrong some percentage of the time。

 As long as I have that， I love machine learning。😊，I'm a security person。

 I don't tend to get many cases where being hilariously wrong is considered a good thing， so。



![](img/c3f70e0df0dd33026cc4ea03964da203_11.png)

And also we have a sponsor for this lecture today， proudly sponsored by Sam Bateman Fried and FTX。

 who so glamorously said they were going to give $10 million in cryptocurrency to the athletic department to slap their name on the field。

I don't think that worked out so well。Although you do got to hand it to the guy。

For being an M I T student。And the son of two Stanford professors， it is a really， really。

 really good prank to force Cal to rename their field just before the big game。



![](img/c3f70e0df0dd33026cc4ea03964da203_13.png)

干嘛的？So why talk about cryptocurrencies？I'm ashamed to admit it。

 I'm actually an expert in the space of cryptocurrency。嗯。

It's been one of my research focuses for the past 9 plus years。

 And that's because I actually have a business model。Most C。

 S folks look at the cryptocurrency space， go， this is hot garbage and ignore it from then on。A few。

 look at the cryptocurrency space， see a way of making lots of money off of suckers by， oh， say。

 getting venture funding for privacy preserving machine learning on the blockchain。

 issuing a token and selling it to retail。And they become true believers。

There's very few like me who actually see the space for what it is and yet stick around。

 And I stuck around because I'm able to mine the comedy gold from the space and turn it into academic papers。

😊，嗯。I do， however， want it to die in a fire。Because there's no value to this space。

Private blockchains。A a 20 plus year old idea。 If your problem is solved with a private blockchain。

 the solution already exists in your Git archive。It's called your Get archive。

Public blockchains are these grossly inefficient， decentralized garbage that aren't actually decentralized。

Oh， and they don't actually solve any problems unless you want to implement a cryptocurrency。

And the cryptocurrencies themselves do not actually work as currency unless you're a criminal。

If you're like the North Korean Missile program， cryptocurrency is great。But if you're anybody else。

But come on， it's just not going。So let's talk about linked lists。

Ca a blockchain is literally a linkedless data structure。

It's a fancy word for aend only data structure。 that is a data structure where you can only add stuff to that causes people's eyes to glaze over and throw money in you。

That's the only advantage over any other appendon data structure is the mind trick。And。

In the mind trick， there's two splits。 There's the private or permission blockchain where you have some limited。

 articulated set responsible for validating things。

 And we've known how to build these for two decades， plus。

And then we have these public and permissionless blockchains where anybody can participate。

And for them， the difficulty comes into removing sybils。 That is fake users， fake validators。

 And we'll see later， there actually is no good solution to the sbel problem other than just identifying things。

And then cryptocurrencies， which don't work as currency。So hash chains are a great idea。

 They're a revolutionary idea from 1980。So the idea with a hash chain。

Is that we have some block of data。 And in that block。

 we have the cryptographic hash of the previous block。

 which we know as being effectively unique and immutable。

And so if I know this last block block N is valid through whatever means possible。

 I can thereby by transitive validate all the history in an O of N operation by just walking the linked list。

 verifying that each block has the right hash and going from there。

This also makes it easy to add blocks。 That's why it's a good appendon data structure。

 You just create a new block， put it on the front， hash the previous block。 Go on。 Have a nice day。嗯。

And so you just validate the head， sign the head with a signature andvo off your web browser uses hashchas all the time for validating certificates that the certificate authorities actually have a property these days where they maintain a hashcha of every certificate they've ever issued。

And that's a great structure。 It's easy to validate。 Ctificate revocation lists are also hasht。

And then we have Merkel trees。We've heard Bitcoin proponents go。

 Merkel trees are such a great invention。A Merkel tree is just a hash tree。

 It is a really stunning data structure from 1979。You want a lot of elements。😡，So's L1， L2， L3， L4。

 all sorts of elements， and you want to compute a cryptographic hash of all the elements。 Well。

 you just cat them all together。 cryptographic hash call it good。

 except that you want the ability to easily add more elements。 And so in the traditional way。

 you would have to rehash all the data。But if you want to make this hash easy to update。

 you just do it as a tree。So you've got your elements。You hatch the elements。Haash。

 the combination of the hashes and so on and so forth。And so to produce a tree of N elements。

 you have to do N log N hashes。And you have to do the longest hash。 Up is log in。

 So if you have to update an element， you just have to do the hashes up the tree。嗯。

And so this is a great little structure for being able to do a cryptographic hash quickly and update all the data。

 It is also patented in 1979。😊，So let's build a trivial private blockchain。

We have a single server S with a public key and a private key。We could all build this。

 This isn't a project， too， because it's too easy。And we have a Git archive， which we fixed to you。

 Sha 2，56。 Okay， so this is a 61 B project now。So we fix our git to use a real cache function。

And whenever we issue a pull request。The server validates the pull request。

 meets the allowed criteria， looks at the criteria。

Excepts the pull request signs the hash of the head of the revision。 And that's it。There you go。

Your private blockchain implementation。That's。Git is， by definition。

 already designed as an appendon data structure。 And so by signing the new head。

 we have the ability to authenticate the entire archive。Because hash to hash to hash to hash to hash。

 and it just goes back。And this is why anyone who talks of a private blockchain revolution。

Is a bullshit。And I speak of bullshitter in the technical sense of somebody who doesn't care what they say is true or false。

Because it literally is anything that would benefit from an append only limited writer data store already has it。

 We've known how to build these for a generation。So what's a cryptocurrency？

A cryptocurrency is a tradable cryptographic token。

 and the goal is to create irreversible electronic cash with no centralized trust， so。

Make up a currency。 Qua lose if you're a sci fi geek。

If Alice wants to pay Bob 200 qualus to pay off the losing bet on the green thrall。

 there should be no one else who can block or reverse that transaction。

And so it's basically a public ledger。 There's a public， global shared document。A big。

 giant Google sheet。That has everybody's balance。And this magic Google sheet has this property where we can only add things to the Google sheet。

 not remove it。So the big idea is given this giant Google spreadsheet。Alice writes a check。 I， Alice。

 pay Bob 200 quatlus， cryptographically sign it， add it to the ledger。

 And now Alice is up 200 quatlu。Or Alice is down 200， bos up 200。And so the idea is pretty simple。

 Alice sends Bob a check。Bob checks in the public ledger to make sure that Alice's balance is good。

 depending on the details in the ledger， it's either looking at the old checks or looking at the balance。

 But Bob goes， Alice's balance is good。Now Bob gets that added to the public ledger and now Bob's up。

Alice is down。And so what is a blockchain， well these public permissionless blockchains？Well。

 the idea there is everybody gathers up the copy of the loose checks。And for each check。

 you validate that it's valid， that there are sufficient funds。

 We bundle all the checks up into a block， Staple them together with the hash of the previous block。

And now everybody just does a lot of useless work， just basically goes。What amounts to number one？

Change a number。Check the hash。 Change the number。 Check the hash。 Change the number。 Check the hash。

 If you get lucky enough。That basically gets added to it。

 And you now publish the new stack of checks。And now。

 everybody knows that the sign the new checks are now validated。

 And so they start processing the next block。And that's how you get this decentralized append only data structure。

And so basically， everybody creates a a check to pay themselves。

 keeps tweaking the check until the hash matches。 And once one guy gets lucky。He goes， okay。

 I'm lucky， I now publish this block and now everybody else goes。So what's Bitcoin。

Bitcoin is just the first widespread development of the idea。 There's been a lot others。

 Bitcoinco wallets do not store cryptocurrency。 They are just cryptographic， private key stores。

So you've got your private key， you've got your public key。

 it's all good and spending Bitcoin is simply writing a check and broadcasting it。

 So this is an actual Bitcoin transaction pay the Rosselbrich legalg defenseense fund he was the guy who started the first Bitcoin drug market and signed by this Bitcoin address。

 which。That's me， that Bitcoin address I created by having a 16 core processor that I needed to break in。

 so I had it generate arbitrary Bitcoin addresses and I got one that started with the appropriate text。

And indeed， you could look up this Bitcoin transaction because it's now in the public ledger。

And there are nice little services that can allow you to look it up as well。

 So you can see this is me。Paying the Rosselbrich Legal Defense Fund。 And oh。

 this was just after he was convicted because I felt sorry for his mother。So what's Bitcoin mining。

 It's just how Bitcoin protects the history。 There's a lot of ways you can do it。

 But Bitcoin just does Shaw 256。You've got some fixed capacity。So Bitcoin as a system。

 only supports three to seven transactions per second on a worldwide basis。Yes。

 the future of money can only do three transactions per second。

If everybody in this room wanted to do a Bitcoin transaction， it would take a minute。😡。

And then you just do the proof of work calculation。

 which is just basically create Shaw hashes until you get one low enough。

 because if the Shaw hash starts with enough zeroes。

It's clear that you had to do two to that many zero bits worth of hashes to find one。

 but it's easy to verify。And then you broadcast it。So remember， proof of work， Sha 256 looks random。

 so I tweak one little bit on the input， the output looks totally different。

And so if I present you with a string of n0 bits。I。

 or the collective consciousness that was all trying to do this had to do two to the N hashes。

So with a single hash calculation。Data， hasht has enough zeros。

 You can verify that I or a collective group of eyes wasted so much resources。嗯。Unfortunately。

 this has some problem。The first one， this causes bloat。In order to verify that Alice has a balance。

 you have to potentially check every transaction going back to the dawn of time。

 So you have to maintain history。And so this is amazingly inefficient。

Every full bit node has to potentially access the entire transaction history。

Likeight wait notes still need。The headers and the ability to query。

 And this is common to all blockchains。 All blockchains suffer from huge b issues。

You can try to prune it， but it doesn't work。And this also means that if you have 10000 people all maintaining the blockchain。

 not only do you have this big。Multi terabyte data structure。

But you have thousands and tens of thousands of copies of this multiterabyte data structure。

This is not an efficient way to run a system， is it。But there's also a capacity problem。

In order for Bitcoin to limit the growth to just one megabyte of block。

 that is one megabyte of data every 10 minutes。😡，There's a transaction limit。

3 to seven transactions per second worldwide。Which means any Bitcoin takes over money requires trusted。

 centralized entities that maintain a centralized database that has everybody's balance in it。

 And we've known how to build this for a generation， It's called a B bank。

So how many have heard about El Salvador using Bitcoin。As a currency。Well。That's a lie。You see。

 El Salvador's dictator is a nukin。But one of the things he got into his mind is， oh， Bitcoin。

 it's the future of money。Now， El Salvador doesn't actually have its own currency。

 El Salvador runs on dollars。As a way of making sure that the crazies in charge of the government don't print money and collapse the economy。

So he declared Bitcoin will be a parallel allowed currency alongside the dollar。

We are going to do a new app， the Shivo wallet that everybody can get on their phone。

 And when you get it， you get $20 worth of free Bitcoin to spend。And。

Everybody spent their bit and then never touched it again。But the fun part is。

Nobody actually ever used Bitcoin for this， they were just transferring balances from Shivo wallet to Shiva wallet in a centralized database。

😡，The other thing is is Bitcoin has these price shock problems。The price of a transaction。

 when it's less than the block capacity， transactions are cheap。

 when it's greater than the block capac， prices spiral up。

 and people have caused price spirals for the laughs of it。Ethereum suffers the same thing。 Ethereum。

 it's cheap， it's cheap， it's cheap， suddenly somebody does mutant ape， slurp juices。

 and the price shoots up for the next day and nobody can transsact unless they're willing to spend five times more than they would before。

Bitcoin in particular， has a power problem。It bounces around。

 I think it's back up to Netherlands level， but basically Bitcoin burns 2% or so of the world's power to do3 to7 transactions per second worldwide。

And this is because proof of work creates this red queen's race design。

As long as there's potential profit to be had， you get an increase in capacity。

So if I snapped my fingers and suddenly all the computers on the planet use1，100th the power。

Jeff Bezos is going to be incredibly happy because suddenly his data centers cause nothing to run。

But what happens if I do that to the Bitcoin mines。

Is suddenly all the Bitcoin miners now buy100 times more mining rigs。

 and it's back to the same place it was before。There's no way to reduce Bitcoin's power consumption without either reducing Bitcoin's price。

 reducing the block reward， or changing how this validation occurs to this model called proof of stake。

 where you just basically have a literally try he who has the gold rules rules。Because indeed。

 is it actually the waste of energy that protects Bitcoin？

Bitcoin securities based purely on burning the energy of Thailand。

But the reason why it's so bad is because of the civilbel problem。

There's a lot of talk in the cryptocurrency space about consensus。

 how the system agrees on the common view of history。But so much of the problem is not consensus。

 but civil prevention。Somebody just spinning up a gazillion node going， I've got a gazillion votes。

And。The solutions， the cryptocurrency come。Folks have come up with are not good。

 It's either burn the amount of energy a major country。

Or literally enshrine a system where he who has the cryptocurrency， runs the cryptocurrency。

 literally enshrine that。😡，There's an easier way to deal with Sybilts。You don't。

It's called the C ID approach to civil prevention。So。Let's take human based agreements。

 identify M trustworthy individuals。In the end， only half of them and plus one need to be honest。

 They all get together。 They all maintain the central ledger。

And you could basically do a system like Bitcoin on M Raspberry Pi computers。

Burning nine orders of magnitude， less power。Why aren't cryptocurrencies doing this Well。

 first of all， a nontri number of them are lying and actually doing that under the hood。

Anytime you see a trusted validator or something like that in the design， you have these hidden。

 trusted individuals。But the reason why the cryptocurrencies don't do this is if you want to be a money transmitter that is transmit value from one person to the other。

 there's all these pesky laws， you know。Like you shouldn't do payments for drug deals or you shouldn't allow payments to rush in ransomware。

You shouldn't give money that goes to the North Korean nuclearar weapons Program， all these pesky。

 pesky， pesky laws。And that's what the cryptocurrency folks are really all about。

 is avoiding those pesky laws。The other problem is cryptocurrencies are irreversible。

 there's no mitigation method。And so a challenge I have to people buy $1。

500 worth of Bitcoin or Ethereum now。Transfer it to a public key。 you control now。

 without either dropping 1500 bucks in cash。Transferring money to an individual and having them do the risk or having a pre existingist business relationship with the exchange。

 You can't。PayPal says you can buy Bitcoin with PayPal。Right。You can't。 You log on。

 you buy with buy the bit。 They're going to hold on to it。

 They won't allow you to actually take possession of the bit。

And that's because everything electronic and modern finance is designed with reversibility。That way。

 you can do mitigation。 You can do detection and response。Without that， you can only do prevention。

And so the seller of a bit， somebody selling you Bitcoin， must either take irreversible payments。

 cash only。Yes， the future of money you want to buy bring cash。嗯。

Either have an established relationship so they can safely extend the buyer credit。

 So if you have an existing account on exchange， you might be able to buy the cryptocurrency and move it off right away。

 maybe。Or you take the deposit from the buyer and wait a couple of days。And so， for example。

 this individual， I believe there's a room in soda hall named after him。

 lost $70000 because he didn't follow these rules。He got some free Bitcoin a long time ago and then decided to sell it。

 and he sold it to somebody who used PayPal， and it turned out to be a stolen credit card。

 and he transferred the Bitcoin and got ripped off for $70，000 bucks。I think the wass can afford it。

 but the rest of us can't。But this also makes it easy to steal。 You compromise the private key。

 and it's so easy to take。 There's a great article I wrote about8 years ago。

 How to make money in Bitcoin in 10 easy steps。There's actually 11 steps because off by one error。

But the result is you can't store a cryptocurrency on an internet connected computer。 In fact。

 the best way we found in practice that works amazingly well to know if somebody breaks into one of your computers。

Is half some small， unprotected Bitcoin wallets lying around。And just monitor the balance on them。

And if the balance ever goes to zero， congratulations。

 you found out your computer just got compromised。This is not a joke。

 We actually were use this to discover a compromise in our research group。

Cause we had some Bitcoin while it's lying around that we were monitoring and one grad student's account got compromised。

 and it got stolen。 And we knew about it right away。So you can't store Bitcoin on your own computer。

If you store it on a hardware device， well， what happens if that hardware device breaks， well。

 it's gone for good。If。嗯。You have the hardware device and a pass or seed phrase that's basically 256 B of random garbage and a safe。

 Well， if that ever gets lost， it's lost。 But at the same time。

 you can't trust anybody else to store your bit。Because let's face it。

How many people thought good old Sam was so trustworthy， hey， his parents are Stanford law profs。

 his mom actually specializes in ethics， I know we can keep my cryptocurrency with Sam。

 we can trust Sam。And this is actually a big problem。

 You can't reliably store cryptocurrency with somebody else。 You can't store it with yourself。

Security experts cannot deal with this。 How do you expect normal people to。It gets even better。

How many have heard of this program called Metamass？For those of you who haven't。

 thank your lucky stars， because this is one of the most awful programs ever made。

 It is a browser extension that hooks up your cryptocurrency accounts。

To or your cryptocurrency keys to the Internet。And so you can do things like buy a receipt for an ugly Jpeg of an ape。

And Meam Masask handles the currency transactions。Unfortunately。

 Measkasks user interfaces best described as awful。

Somebody click treat tells you to click on the wrong thing， you click OK。

 and now all your cryptocurrency is gone for good。Millions of dollars have gone this way。 In fact。

 it's probably about at least 100000， if not a million dollars a day is stolen from people who click on the wrong thing using that mask。

However。There is good tech support。 If you just mentioned Meam maskask on the shitter site。

 that's how you pronounce it， right， Shier。You get so many helpful suggestions on provide your seed phrase and will'll help you out and everything else。

 it's amazing。😊，So what good are these things。 There's one thing cryptocurrencies are good for。

 And that's censorship resistant。That is， there is purportedly no central authority that says。

 thou shalt not or thou shouldn't have。Well， actually， they do exist。

 It's these central authorities don't actually want to do their job and don't care about your drug deals。

If you believe there should be no central authority on payments。

 cryptocurrencies are the only game in town。If you honestly believe that。

Cryptocurrencies are the only thing that provide electronic payments。 and so。

Most of the faculty who work in this space and are pro cryptocurrency， I don't。

They rub me the wrong way。 But there's a few that actually believe in this philosophy。

 And for those that do， this is the only solution。But the problem is， is this enables drug dealing。

 money laundering criminal criminal payments， gamblings， attemptsemp to hire hitman， the number of。

Dollar value of attempted and hires is in the millions。They're so easy to steal。

 because that's why cryptocurrencies are so easy to steal。 because the bank doesn't say， oh， no。

 I'm not going to transfer that。嗯。Ransomware and extortion is costing billions a year。

Enabled purely by cryptocurrency payments。So how ransomware works is the bad guys in Russia break into a business's computers。

Enncrypt all the data with public key encryption and say， pay me or you'll never see your data again。

Now， if you're a bad guy in Russia。And you want to get。$5 million from， say。

 colonial pipeline or a health network or something。You have three choices， bank transfer。

 cash or cryptocurrency。You can't do a bank transfer because no way is a bank going to allow a $5 million payment to Russian criminals with Russian criminals for the purpose of extortion on the memo line。

 It's not going to happen。Okay， so the bad guys could take cash。Well， the problem is。Cash is heavy。

$5 million in 100 bills。Is a blob of stuff that weighs 50 kg。

This is two full weight international checkback。So not only does the Russian bad guy have to drag these two suitcases from the point of exchange。

 But yeah， you see that hill over there。You're gonna get an extra little gift。 It's 3，0。

8 caliber from that Marine because you pissed us off。So the bad guys only have cryptocurrency。

And that's only because of censorship resistance。There are some minor good uses。

 so there was payments to Wiki page and back or Wikileaks and back page， Oh wait。

 Russian front criminal enterprise。But they don't work unless you need censorship resistance。

Any volatile cryptocurrency requires two currency transaction steps because it's the only way to remove the volatility risk。

 The price is bouncing up and down。So how many have seen Company X is proud to say we accept Bitcoin？

And then quietly， six months later， they just suddenly disappear the offer of accepting Bitcoin。

But during that six months。They never actually took Bitcoin。Instead。

 with the exception of a few occasional companies run by complete lunatics。まし。Sorry。

Frog in my throat。They don't。 Instead， they use a service that takes the cryptocurrency immediately sells it for real money and hands off the real money。

 In fact， that big stadium deal that the Cal athleticletic department proudly negotiated with F T X to pay for the naming rights in cryptocurrency。

 asterisk cryptocurrency will be transferred to the intermediary in charge of the rights and immediately turned into actual money for the football team to lose with。

But if you believe in the cryptocurrencies， you actually must never spend your cryptocurrency。

 Bitcoincoin's economics is best described as even more demented than the computer science。

It's designed to be deflationary。Now， if you don't believe in Bitcoin， you never want to use it。

 If you do believe in Bitcoin， you never want to use it because the price is only supposed to go up in the future。

 So every year， the cryptocurrency community celebrates Bitcoin pizzaizz day。

When somebody bought two pizzas， I think Papa Johns， oh。With Bitcoin。Of course。

 they didn't actually pay for the pizza from Papa John's。

 They send the Bitcoin to somebody else who actually paid with their credit card。And the problem is。

 is that pizza。Comes with a pretty big helping of regret。

Because that's millions and millions of dollars worth of Bitcoin now。Of course。

 anyone in hold onto to it would crash whatever。 But the basic model is。

 if you have Bitcoin and some other thing， if you don't believe in Bitcoin。

 why do you have the Bitcoin， if you do believe in the Bitcoin。Don't spend your bit。

 You cannot make a viable currency that way。And so all the promised financial applications。

 cheap res， etc cea， can never apply in a volatile cryptocurrency。

If the cryptocurrency is not anchored to real currencies like dollars or ys。

 it will never actually work and， oh， we've had electronic money for two generations now。

And so bit's only appropriate for buying drugs， paying。Titman finding out that you paid fake hitman。

 finding out that you paid the FBI， who is faking a hitman， etca， etc cetera。Because otherwise。

 you use PayPal， Venmo， Zella， and Pesa， Square， etc cetera， et cetera， et cetera。嗯。

Becauseuse those work better。But censorship resistance is the fuel of crime。So before Bitcoin。

 they had Liberty Res， and the bad guys have Web money。 Webbb money only works in Russia。

 So it doesn'ts not something the US can shut down， but it's also not something US crooks can use。

And Liberty Reserve got shut down。Prosecute。So， as I said， the only thing is cash。

 And so the cryptocurrencies are the only game in town。Trug dealers back in 2013。

 when Silk Road first hit。Hated Bitcoin。There was an interview with a guy。

On the run from the Feds doing a phone interview， describing how he'd have to fly to Las Vegas。

To exchange his bitcoin for suitcases full of cash。

And you do it in a casino because that's the safest place to do it。Now。

 there's this notion of a stablecoin。Which requires eliminating volatility。

 not lowering the volatility， but eliminating it。So it just， basically。

 you need an entity that takes dollars， converts them to tokens and goes back the other way。

We've known how to build this for generations。 This is literally a bank。

Get out the piece of paper in your pocket， you see that it's actually called a bank note that's because in the old days。

Banks would just take your coin and print paper for it。Okay， so we've have a centralized entity。

That is responsible for moving money to and from dollars to the crypto tokens。

 So why do we need a blockchain？I know we could instead have this centralized entity keep what S Q L database I heard they're called。

And just update people's entries and forget all this blockchain stuff， yeah。

The other thing that you see are things called algorithmic stablecos。

 These are basically Ponzi schemes into thees that blow up hilariously。😊。

But there's a choice for a bank。Either you become as regulated as PayPal and Vi， in which case。

 what's the whole point of your cryptocurrency crap？

You have a Wildcat bank where the bank is printing unbacked banknotes。

Or you end up in jail like the folks who ran Liberty reserveserve because you're doing a money transfer system that is going to be used by the crooks。

Bick your poison。The biggest stablecoin out there， Teer。It's a fraud。Basically。Alameda research。

Which was the trading arm of the F T X fraudulent crypto exchange。Somehow。Over time。拨。

$40 to $50 billion worth of tether。Where'd they get the money。Probably。They borrowed the tether。

Bought Bitcoin。And now thetether is backed by loans to alameda research， holding Bitcoin。嗯。Basically。

 bit's only value is speculative。 Somebody else in the future will pay more than you paid today。

And there's a supply and demand。 New Bitcoin in gets matched by new dollars and new fake dollars。

And the bubbles have always been driven by fake money。Back in 2013。

 the first Bitcoin bubble was created by fake money on the Mount Gox Exchange for the trivia buffs out there。

 the first big high profile Bitcoin exchange that imploded spectacularly was magic the gathering online exchange。

2017， Tether blew up the cryptocurrency。And 2022， it was again tther until FTX blew things up。

It's just so blatantly a fraud。But the printer keeps going。 So hey。Practically。

 every other cryptocurrency is a me， too， with some ri。There's a lot of cryptocurrencies。

 they all basically work the same。My favorite lightco was Bitcoin with a catchy slogan。

 one of the first major alt coins。B lightcoin silver to Bitcoin gold。 Ain't that a great slogan。

Dogeco， Bitcoin with what used to be a cool joke。😡。

One of the two founders of Dogecoin says the entire cryptocurrency space is awful and should burn on fire and is even higherer critic than I am now。

Ripple is basically centralized Bitcoin with unrelated settlement and security fraud as a business。

Iiota is a fun one。 This was centralized Bitcoin that for a while rolled their own hash function。

 What has Per told you about coming up with your own cryptographic algorithms。😊，They did。

It gets better for some reason， they think。Tinary。There are one0 kind of people in the world。

 those who understand who don't understand triary， those who only understand binary and those who understand binaryary。

 For some reason， they think that the number system based on 1，0 negative one is somehow better。

We're eventually going to build computers that run on primary。 Oh。

 and it's supposed to be used for the Internet of things。

Because you want your light bulb to do a micro payment to a central service when you ask it to turn on。

 don't you， This is all what you're crying out for， right， right。

Mero is Bitcoin with better pseudonymity。 They do mixed transactions。Zcash is。

A cryptocurrency that has literally money laundering is a first class feature。

That's what anonymity is in electronic payments， is money laundering。

Ethereum is Bitcoin with unlicensed security and million dollar bug boties。They're great。

 we'll get to that sack。But like， there's this dream of this space。 decentralization， trust nobody。

 The entire system is trustworthy， but each actor is not。 First of all。

 this requires that there never be a small group that can change things。Now。

 it's an article of faith among the cryptocurrency advocates that decentralization is good。

I disagree because I like the easiness that central authorities do。

But the only real thing that decentralized buys is basically no legal obligations for the central authorities。

But the reality is they're about as decentralized as。A rock。

Code is inevitably developed by one or a few groups， and they will change it capriciously。

 So the Ethereum community loves to shout out code is law。

 The notion that what the program says is the binding contract。

Until early on in the days of Ethereum。10% of all Ethereum got tied up into a bad piece of code that somebody went up to and said。

 hey， code， give me all your money。And the code went， moki doke。And。

You would think that Co's law would mean you'd respect the honesty of the noble hacker who came up to the smart contract and second it。

 Of course， they didn't。Come on。 Youre kidding me。 They instead stole the money back by changing the underlying code of Ethereum。

Rewarded mining centralizes。Basically， the miners are hostile。 So the Ethereum network。

Deliberately acts against users。嗯。And several things are not just to see centralized at all。

 You've got trusted coordinators。 If you have an ability to overfide or freeze assets。

 it's not decentralized。But wait， I hear you say， what about all the venture money， Well。

 first of all， it's gone away over the past six months。

And the reason why is because the SEC has woken up。Because。It used to be。If you're a venture company。

 what you do is you invest in several companies。One or two of them end up thriving。

 and you sell them off。嗯。Most of them fail， but that's the cost of doing business。

But the new model pioneered by Anderson and Horowitz is securities fraud as a business。

 You invest in several blockchain startups， like the blockchain startup that promises privacy preserving machine learning on the blockchain。

This said startup issues a token promising that these flower named tokens are going to be usable someday for privacy preserving machine learning on the blockchain。

I know you don't actually want to do privacy preserving machine learning on the blockchain。

 but somebody else will。 So buy our flower themed tokens now。And then when it goes up in value。

 you can sell it to somebody else who actually wants to do this service。This is securities fraud。

A 16 Z also gets a ton of these tokens， and they also dump on retail。If the SEC ever wakes up。

 this is latent securities fraud based on。Security law that's a century old at this point。

Almost a century old。And。If the S E， ever does wake up， well， A 16 Z didn't yet。

In trouble because they arent the ones who committed the securities fraud。

It was the founder and the startup that committed the securities fraud A 16 Z just advised them that。

 hey， issue your token for privacy preserving machine learning on the blockchain。And so， the。

This is why all the venture money went into the cryptocurrency space。

 It's not because they believe in this bullshit。 It's not because this bullshit does any good。

 It's that this bullshit allowed them to create a gig economy of securities fraud。

 where it is somebody else doing the actual crimeing， and if the S E doesn't wake up， they walk away。

 If the SEC does wake up。 Oh， it was the startup over there that was committing the crime。

 we just suggested it to them， we helped them out。 We took。

But its were as innocent as the pure driven snow。So what about the non cryptocurrency applications。

Put a blockchain on it。Private or permission blockchains，s， as we already mentioned。

 are 20 plus year old ideas。The only value of saying blockchain is idiots go， take my money。😡。

Commercial private blockchain stuff falls into exactly two categories。1。

Consultants looting the company because， hey。It sounds good。And，2。Okay， boss。

 I need $5 million to redo our backend infrastructure。 We need new database server， new database。

 bunch of software， blah， blah， blah， blah， blah， How does the boss react。い。However。

 if you go up to the boss and say， hey， boss， I need 5 million bucks to provide a Bitcoin and or a blockchain enhanced solution to our workflow。

And then， you spend。4。999 million on all the previous boring stuff you listed。Take the output log。

 cryptographically sign it， throw it into your Git archive， and go blockchainlock。

 and now you get the funding to do that back end infrastructure and you need it to do。

That's what it's good for。And the other thing is， is those promising blockchain don't actually understand the space。

Solve voting electronic medical records， food security。 name your heart problem with a blockchain。

 They never say what data， how， what formatments， what honesty， what enforcement， How do you correct。

 What's the sensing involved， they。Just goes over their head。And。This is a concrete example。

One thing that's frustrated me。Is there have been repeated blockchain classes here at Berkeley？

I attended one session of one of these one time to give a short rebuttal。 This was back in the day。

2017，2018。When I wasn't quite so hostile to it， because there was a still more amusement value。

 the two outside experts presented on how they do stuff with blockchain were delusional。So。

Concrete example， one of these guest lecturers confidently said。

You can solve the cold chain problem for vaccines in India， with blockchain。So。These days。

 we all know about the cold chain and vaccines。 You got to keep the vaccine cold。

 not like it too hot， etc cetera。 But you could forgive somebody in。2019， for not knowing this。

And so he goes， well， if the vaccine gets too hot， it's no good。

 And so we can solve this with blockchain。And my response internally was， know you fucking imbeciil。

 You sell all of it with these things。 This is what's called a warm mark temperature label from shockwa。

😡，It's basically a label you stick on the package。And if it ever gets too hot， it changes color。

That is how you solve the supply chain problem for vaccines。

 is you put shockwatch labels on the boxes。No blockchain involved。

And this was when I formulated my iron wall blockchain。Blockchain solves exactly one problem。😡。

When someone says you can solve X with blockchain， they have no clue how to solve X and you can safely ignore them。

Never underestimate the value of having a zero false， negative， zero false。

 positive bullshit detector。This is a 100%， no false positives， no false positive bullshit detector。

When somebody says this。You know they're bullshit。There is one innovative new stupidity。

 smart contracts。 How many have heard of smart contracts。Okay。So let's start， idea。

 contracts are expensive。Says somebody who's never signed a contract。

So let's take things that are written in a formal language。

 Contracts are written in a formal language。 It's called legal elite。 It looks vaguely like English。

 But if you try to treat it like English， you're in for a world of her。嗯。

Let's replace that with a horrid language that looks vaguely like JavaScript， only has 256 bit ints。

And these contracts are fixed， when it's released。And， okay。

How is this supposed to make things cheaper to start？Standard contracts are cheap。

 because they're standard。Oh， and let's ditch the exception handling mechanism。

 Standard contracts have this really robust exception handling mechanism。 It's called the courts。

But if you can steal from a smart contract， are you actually committing theft。

 It's actually in the contract。 The contract says you can do it。

If you ask anybody responsible for smart contracts， they'll go whose money is it， is it yours。

 it's not theft， if it's mine， it's theft， it's kind of strange that way。

 but the idea for these immutable contract programs on the blockchain came to Viic Buting because World of Warcraft Neweared his spellcaster。

How much grief and money would have been saved if World of Warcraft didn't nerve his spellelcaster。

 blood siphon， I think it was。呃。The horrors of the world。Makes you wonder if you have a time machine。

 what do you do， Do you go back and kill Hitler or do you go back and change world of warcraft so that they don't nerve blood siphon。

And killed him。More funding。But the reality is， they're basically financeable。

Small programs that run on money。Now， we've had finance bots for generations。

 for basically two generations now。For example， I am a savvy investor。And by savvy investor， I mean。

 I throw it into index funds and ignore it for a couple of decades。

And my investments are run by finance bats， small programs that are basically acting on money。

The difference is。The smart contracts are finance bos running in public。嗯。

And they're not distributed。And so the predictable result is million dollar bug bounties。So。

10% of all Ethereum。And a smart contract got stolen before they stole back。

The parody multi signature wallet。 This was responsible for millions of dollars in losses due to a coding bug。

 actually two coding bug。The first coding bug is somebody could go up to the wallet say。

 you belong to me now。 O， give me all your money。 and it would。

This didn't wipe out everybody because somebody else white hat goes， give me all your money。

 give me all your money， give me all your money。 Okay， I'm gonna give it back to everybody now。

And then there was another bug later on， like a week later where， hey。

 smart contracts that runs everybody's wallet， you belong to me now。 Oh you no， Oh crap。

 ay smart contract， selfdestruct， no， no， no， selfdestruct and now nobody can access their money anymore。

And the guy who wrote this， the lead developer， was the guy who invented the frack and programming language。

My favorite though is the explicit Ponzi schemes。And then we have these centralized autonomous organizations。

 Hey， let's get together and create an organization organization where everybody invests。

 Everybody gets a vote。 Yes， this is something we invented five centuries ago in China。

 It's called the Joint stock Corporation。嗯。But let's do it on a blockchain instead。

 So if anything screws up， Oh， well， and let's not actually do the paperwork to be a corporation。

So literally a decentralized autonomous organization that does the paperwork。Is a corporation。

A tao that does not do the paperwork。Is an unincorporated general partnership。

 And this has this notion of what's called joint and several liability。

 which means everybody is on the hook for the Dows screw ups。 So if。

 say your dow is in charge of a money laundering operation like tornado cash。

All the participants in the tornado cash Dow。Are potential criminals。Does this make sense to you。

Don't make sense to me。Do your paperwork。Everything else is speed running。

 half a millennia of bad economics。So the cryptocurrency exchanges are fraudulent。Even coinb。

 I consider fraudulent。It's full of marketing things that basically are fake。We've got Ponzi schemes。

 Ponzi schemes， more Ponzi schemes， some explicit， some implicit。

Teer is almost certainly a Wildcat bank。Every tradedable ICOO， they're unregulated securities。

 We know about these being a problem back from 1720。You've got。Fun ones。 Like this was a fun1。

 I had a choice between Aids cure on the blockchain and alchemy on the blockchain with its IPO or ICO O。

 Sorry， I went with the alchemy on the blockchain I CO。😊。

Your cryptocurrency will be able to turn base metal into platinum。Rare twolip。

 we've actually had two runs through the Ethereum blockchain， so this was cryptoitties。

 this was basically the predecessor to the board apes。They're kind of demented little things。

 total tulip mania。And finally， because I don't want to see that anymore。 Oh， and gold bugism。

 if you want to make an economics professor cringe， ask him to explain the gold standard。

My cat doesn't like this either。And now we have the rebranding， the Web3 rebranding， hey。

 let's bring the unstoppable censorship blockchain power to the web。Keep in mind。

 this diagram that I'm going to use is from a proponent of this。No。

So the current web is what's known as distributed。 You contract with the DNS provider who does the name to I P mapping。

 you contact to the web posting provider and you pay a few bucks。 If any of those object to you。

 they'll toss you， they'll say you violate the terms of service， we get rid of you。

But you can always find a friendly hosting provider unless you're truly， truly awful。

 unless you're something like child porn or something like that， child sexual abuse material。

 you can find a hosting provider。Actual Nazis have plenty of presence on the World wide Web。

 They just don't host in Germany。And then the computation in the current web is a distributed computation between the web browser and the webserv that the web browser is running jascript。

 It's a distributed computation。So let's improve it with Web 3。

Let's see what the improved Web 3 techat looks like。Well。

 I still have to have the centralized hosting。 I still have to have the DNS infrastructure。

I did not manage to remove any gatekeepers at all。But we still。

 you end up depending on more centralized providers because。

You are going to access this blockchain directly。 Instead。

 you're going to use a service from the graph。 They're going to use Metamask。

 which uses other services。 So we've added in。More central authorities that can end do。Censor stuff。

 The only thing that's happened now is。You transfer a little cryptocurrency from Meammask。Okay。

 more central authorities。More complexity。Damn it， I hope this Ethereum world computer is going to be super duper powerful and cheap to use。

Worth it for this restructuring of my stuff。 Wait a second。You can see where this is going。😊。

There's a global minute for Ethereum of 2 million gas per second that this is how much computation the system does to keep itself from going bloated。

Any computation on Ethereum takes some gas on the virtual machine。 It's a deterministic。Computation。

 so all the copies are running the same computation on the same inputs to the same outputs。

The EVM itself is a stack machine that makes the Java virtual machine look sane。If you ever take 164。

Ask about the JVM。Oh， and it takes 11  TBtes of storage。The simplest computation。

 let's think about it is a 256 B addition。 That is three gas。So Ethereum blockchain。

You can do 600000 editions per second， to。And the cost bounces around。

 but it's about 100 bucks a second to use Ethereum ass a computer。My raspberry Pi4。

That can do 3 million No， sorry。Hhousand million， oh， billion， oops，3 billion。

256 bit editions per second。Okay， so the Ethereum world computer is。1。

500th as powerful as a raspberry pie。Oh， and it costs 45 bucks。One time versus。W。This is how crap。

These systems are。So basically， this space is dis。The values non exististent。

 the societal harms are great。Unless you like。Being humiliated by a son of Stanford Law professors。

I don't know。 The athletic department might like that。 They， They do seem to lose a lot。

 so they might be happy at that time。And so basically。

 either avoid it or make it d theifier because it is just。So questions on the ran。すろでし。

Zero knowledge proofs are actually a really cool idea。 They date back 30 years as well。 In fact。

 you can think of RSA as being a zero knowledge proof。

 There was a great proof by Manuel Blum 30 years ago that you can prove any proof as a zero knowledge proof。

😊，So he could prove that you can prove every proof as a zero knowledge proof as a zero knowledge proof。

U。Zero knowledge proofs are a really good idea， and they're not new though。嗯。

What has been new and interesting from the that's been derived from the blockchain use。

Is the smaller non interactive zero knowledge proof。 So prior。

Prior zero knowledge proofs were very big。And the big innovation， mostly by the Zcash folks。

 was coming up with these smaller zero knowledge proofs。Now。

 they're quite good for their intended application of money laundering。

Because what you do in Zc is you put your money in a pool。And then some time later。

 you publish a non interactive zero knowledge proof that proves that you would。That you put money in。

 that you are withdrawing that money， but not time。 What is the exact money。

 So money laundering is a service。嗯。They're good mathematically。 They're interesting。 The problem is。

 is there， there's a real question of how much utility there's been outside the cryptocurrency money laundering space。

 So technically， they're really cool。Socially， I'd love to see an application that isn't money laundering on a blockchain。

Other questions。你怎知道。You can find out for yourself。

But the asterisk is assumed that Intel S G X works， which is not a safe assumption either， so。

The privacy preserving stuff is kind of bogus too。I didn' really understand what you。没ち那个。big。

On the blockchain， wouldn should you be able to just manipulate。By making a bunch of big trends。呃。

When you mentioned like all summer。

![](img/c3f70e0df0dd33026cc4ea03964da203_15.png)

Oh， the。Oh， so what happens is it's the transaction fees go up， so this is a market。

 the fee market design for the cryptocurrencies is a inelastic supply。

 elasticastic demand market because there's only so much supply。

And once you get to the too much supply and demand or too much demand and demand starts to exceed supply。

 you get price spikes and price spirals very quickly。嗯。

And so what ends up happening is the prices go out of control very quickly and in the space of say 10 minutes。

 the price per transaction can quadruple or quintupple and the only thing that really stops it is that the price will actually grow exponentially on Ethereum say。

 until enough people go and give up。Because of the yeah， because of the limited capacity。

That limited。Limited supply in elastic supply markets。

Tend to get price shocks whenever the demand exceeds the supply。So I guess like。Like。嗯。

I think do that actually。So write to the S E and encourage them to keep enforcing the laws。

 So the S E， over the past year after the F T X implosion。Has gotten much more aggressive。

 So they're suing coinb because coinb。Partially owned by a 16 Z has this strange habit of listing new cryptocurrencies that happen to be ones that a 16 Z invested in。

And。As soon as you actually have to follow the rules。

It basically means your value proposition goes away。 So like finance， the Bitcoin exchange finance。

 just basically， the head of B is basically getting away with financial murder。

 He's looking at maybe 18 months in club Fed to walk away with half a billion of his own money。

I don't know about you， but I'd take that。 Thank you。But finance the company。

Is probably dead over the next year because they actually have to enforce things like money laundering laws。

 They have to not trade on registered securities。 Basically。

 as soon as you have to follow the existing laws。They basically shut down and go away。

 And so I've been basically one of my big arguments to policymakers is you don't need new laws in this space。

 You just need to enforce the existing laws。嗯。That。

Because that's what ends up disrupting the ecologies very quickly。You ist coin in based。个说。Okay。

 coinb in the old days。Was trying to be the reputable cryptocurrency exchange that only had a few like Bitcoin。

 Lico and a couple others。Even back then， they were problematic because， for example。

 their trading of lightco， their support of lightcoin started just after the guy who created Licoin joined。

95% of the traffic in lightco was him trading with himself。

And he sold all his lightcoin and walked away。 He got prosecuted for this。

 I don't know if it was criminal or just civil， but this is the kind of thing that Coinbase should have caught right away。

 It's the sort of thing that Coinbase should have never allowed。More recently。

 coininba started listing。What can best be described as shit coinins。So。Cryptocur tokens。

That are newly issued with this securities fraud as a business model。 and strangely enough。

There's a strong correlation between what they issue and what a 16 Z and the like are invested in。嗯嗯。

And so I view them as corrupt， Gemini。As cryptocurrency exchange go。Is slightly less corrupt。

 but not by much。 So what happened with Gemini is they created a product called Gemini En。

 where you could earn。5% interest on your cryptocurrency。

By having them loan it out to trusted partners， the only trusted partner being Genesis that dumped it all into somebody who is investing in a ponzi scheme。

And the Gemini folks knew that this was going down and did nothing to protect their customers。

And these are the reputable companies in the cryptocurrency space。嗯。And basically。

 as soon as they action。 And that's why they're so afraid of the S， E。

That the cryptocurrency folks always go， We want regulatory clarity because the S E had been doing hands off。

 But as soon as the S E wakes up， not that regulatory clarity， because it inevitably is。

You're selling unregistered securities， you're a broker dealer， exchange， et cea。

 There is a reason why the securities laws require that these are separate institutions。

But the cryptocurrency exchanges， by basically ignoring those regulations。

 are repeating the mistakes of the 1920s。Quite willfully。In their behavior。

And so I don't trust any of them。我以。Why hasn't it imploded yet。

 I don't know there is a saying on bubbles， the market can stay irrational longer than you can stay solidnt。

Bubbleles always last longer than you expect， but when they implode， they implode spectacularly。嗯。

I think that a lot of it is fake right now， that if anybody really tried to get a large amount of cryptocurrency and turned it into real money。

 the system would crash。Because everybody's basically， as long as you pretend it's worth something。

 it's worth something。 But as soon as you try to cash out， it fails。

The 1 I'd be watching is the Bitcoin miners themselves。

Some of them have been managing to basically do fraud on electric rate payers instead。

 so like Ri blockchaincha has made more money by not mining Bitcoin than by mining Bitcoin because of deals that allow them to be paid to not burn power kind of thing。

I don't know how much unsold Bitcoin there is in the miners。But that's。

 that's what I think will trigger a collapse。 But I thought it would have gone collapse a year ago when SF imploded things。

嗯。It's a self assembled Ponzi scheme， so。There's， there was no intent in Bitcoin to create a Ponzi scheme。

 but it basically acts like one。And people make money in Ponzi schemes。

 as long as you get out before other people do， you make money。

 It's just it's a zero sum or negative sum game。 So in the end。

 you have more net losers than winners。So。SBF got rich by stealing money from people。

A lot of the others who've made money in cryptocurrency， basically， they made money by being lucky。

And so you have a huge amount of survivor bias or by getting somebody else to do securities fraud for you。

 like the A 16 Z folks do。