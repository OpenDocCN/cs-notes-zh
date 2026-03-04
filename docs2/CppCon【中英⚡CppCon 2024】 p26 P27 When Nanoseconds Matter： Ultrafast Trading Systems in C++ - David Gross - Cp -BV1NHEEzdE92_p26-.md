# CppCon【中英⚡CppCon 2024】 p26 P27 When Nanoseconds Matter： Ultrafast Trading Systems in C++ - David Gross - Cp -BV1NHEEzdE92_p26-

![](img/88608fa5ff6c3e01dca63f47340517dd_0.png)

Thank you all for being here， very excited to be here here we both of you in Denver Colorado。

 thank you for you know so that we're going to watch this video later online today we're going to talk about low latency trading system in C++ so I'm David I've been working in trading in the industry for about 10 years。

😊，I always adopt to a market maker before that， I was working on relatively similar systems in a very different industry in defense。

And today， we are going to talk about engineering， low latency systems。

 I' like to put the emphasis on engineering。Because it's not going to be a very theoretical talk。

 and we're going to be looking at actual problems that we want to solve。And throughout this talk。

 we're going to look at some principles along the way。

 some of them that I collected throughout my career that I found are important and I think that could help you and also some profiling techniques。

But before going into the technical details。Let's backt a little bit。By around 2，2 and500 years。

 where most things started， at least in the Western world， which is the antiquity。

We start with the hormoneman empire。And there are a few I mean。

 many things that are actually fascinating about the Oman Empire， but at least two of them Ma。

 which is it lasted for a very long period of time and it was already vast。

 it went from like the Haan world in modern UK to modern Iran。

 which is Persian and you like historians in general。

 do not agree on a lot of things about Omans for example， the reason of the decline。

But they all agree on one thing， which is the key to their success。

 is that they they were very good at planning things that are really good infrastructure and organized。

 They were very disciplined。Now， you know， what did the Romans plan， Well， a few things。

 And here have some example， urban food supply， military campaigns are really famous for their military achievements。

Now， something a little bit more fun to talk about than mini during achievements is festivals。

 Here you have pictures of Syracuse Maximus。😊，Which you can still see the rest in in the home in Italy。

And it has an estimated capacity of 200300000 people。 So they weren't organizing small parties now。

 And if you want， you know， if you， if you're getting such large events。

AndYou have an interest into planning things for your economy。So what the womans。Actually。

 I figured out And what they did is that they would actually go to， you know， farmers， you winemaker。

 et cetera。 You know， they needed some grains， some meat， all kind of things for the events。

 And they would ask them。A year from now， you know， what price would be would you be willing to sell。

 you know that drain。And by doing so， the woman invented very much， you。

 like early derivative trading。It was actually called homeman Fu Cons。

And so what the omens figured out is that like the world under certain uncertainty。

And so when I was preparing this stock， I actually learned about。

This index called the World Un Soty index。Now what you can see that know on that blue line。

 you mostly see relatively， I's say negative events， doesn't mean it's all bad。

 but it's mostly that us humans are psychological creatures and we attach more weights to potential loss than potential gains。

I think that makes sense， usually if you cannot sleep at night。

 it's mostly because you can actually lose something more actually， if you can make some profit。

 you can relate to that。And so back to the humans， they indeed find a solution to， you know。

 reducing the world uncertainty。By doing derivative training。

One thing that I didn't actually truly solve is usually when things are quite uncertain。

 you have also potentially a problem of liquidity。I think it makes sense to think that if there is a certain economic turmoil and there is a lot of uncertainty in the world at the same time。

 people would be less likely to actually agree on a price a year or even two years from now。

 because you know who knows what can happen。Now， going into you know， the modern world， I mean。

 that's why we've got market makers。And I like to， yeah， G that took into the editor。 and so。He。

 my reality haveve been working for 10 years for a market maker。 So that's。

 that's why we've got that。 There many different actors， of course， on the financial markets。

 And today， we're going to talk about low latency and many of these different actors have different requirements in。

 in low latency。😊，Will come to 다니 a bit。We say that market making is a losers game。

And so what we mean by that。Is。At effectively。You need to be consistently good。

 pretty much everything。 right It's not about this one silver bullet that's going to allow you to。

 to beat the market。You need to be constantly good at everything。And so effectively。

 what market makers know how it works is that you make some small profit。

And the small profits are from back to the Os， you know， you agree on pi a year from now。

 and you know most of the time there is actually， you actually got to pay for this small optionality。

can't be free because you have some risk。 You know prices might go up and down。

And you want to avoid big losses now， why would you actually lose a lot of money。

You're providing pices at any point of time of， you know，100 thousands of instrument。

And there is a news。 I mean， news come out over the time。 there can be a big news that comes out。

 And you know， what would happen if you just leave all your pies and change。嗯。Well。

 you would have actually， you know， stayed Pis and you would do actually a lot of bad trades。

And that's， that's what we mean by like a loserss game， consistently good at everything。Now。

 elaborating a little bit more about you know， why do we need low latency programming here。

 Im breakinging down this into two categories。 I think the first one is relatively well known。

 I think it's the most intuitive one， which is we want to。

 you know have we have a need for like reacting fast to uncertain events。

 that news that I just mentioned。That news that comes out。 We need to react。

 We need to effectively update our pies， or maybe just cancel our orders。

The second one is a little bit maybe less straightforward。

 which I'm going to explain on the next line， which is。You also need to be smart。 Now。

 like being smart is a very vague concept。嗯。So you need good motors and so on and so forth。

 but you also need to be accurate。And again， accuracy is inherent related to latency again。

 for the same idea of like you've got an information， information flow into your system。

And you want to， you want you to have like a pis。 You want to ingest this information。

So on this slide here， you can see what I would call relatively st modern trading system。

And the reason I put that slide here is like one of the question。

 And I get most of the time when I go to conference or like， in general is， you know， hey。

 we've got FPGs。 They are already fast。 So why do we skill care about software， You know。

 why do we think about reancy Cpress in that case。And so there are two answers with that question。

It's on that gov。You see the exchanges on the right。Ps are disseminated into the system。

 They flow into the system。And so indeed， you you've got that blazing fast FGA here。

 Can I say a bit more about it in bit。Why do we still need。

 you like to send orders even with software， It's just what I would say is cost benefit。

TheFPJ is expensive， not the card itself， but just the engineering time or just like operational it something more complicated to manage than software。

 softwareware is more flexible， so it's always going to be there It's kind of hand to hand。

 it's just you engineering your system properly on finding the right solution for the right problem。

So that's on the right now there is something a little bit deeper on why we need low latency。

A software， which is， you see the yellow boxes on the left。The strategies。

What the strategies are doing。Is that they send so called。 We call them rules to the SGA。

 The idea is that。For the FPG to be blazing fast， it has to be really simple。

I don't mean that it's a simple thing to engineer。 It's actually quite complicated。

 but functionally speaking。It's very simple。 It's seize bits， compare bits and send bits。

You can actually make it more complicated， but it's just a trade off， then it would be slower。

And so the strategy send is whole So what is the whole， very simple。 If pie is greater than 10。

 update my pies of console in my auto。And so now if you think about it， the strategies themselves。

 they have already low latency requirement， if， for example。



![](img/88608fa5ff6c3e01dca63f47340517dd_2.png)