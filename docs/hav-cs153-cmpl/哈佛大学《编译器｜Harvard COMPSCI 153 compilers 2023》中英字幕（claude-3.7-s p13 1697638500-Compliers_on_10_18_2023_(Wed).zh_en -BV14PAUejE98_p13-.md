# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p13 1697638500-Compliers_on_10_18_2023_(Wed).zh_en -BV14PAUejE98_p13-

Homework 4 was released on Monday as well。 during about a little under three weeks。

 So no new announcements。Any questions about anything on the admin side Homes。 Yeah， homework Monday。

Isn't the due date？This Monday， five days away。Yes， sorry， that's what I was meaning due on Monday。

 the Monday that we have not yet come to yet， don't panic。Okay， thanks。Anything else？All right。

 so I'm very excited to introduce Dusha Prous， Dr。 Dsha Pust today who's going to be leading our embedded ethics module We've talked in the class already about how kind of the uniqueness of the embedded ethics program and the opportunity that we have this collaboration between philosophy and computer science to get the chance within a whole lot of technical courses to be able to embed an ethics module that's connected with the technical content that allows us to kind of take a step back from the in-depth material and think about the broader implications of the work we're doing and this is in part to make sure to try and make sure this is something we get habituated to that we get in the practice of thinking about the broader implications of the work that we're doing because when you're out there leading industry setting government policy。



![](img/d4fd854ae48c280f771639bb9e87eee5_1.png)

Creating a new startup running companies。It's very rare that somebody will actually say to you， okay。

Po is what you're doing Don't fix that bug just yet instead let's think about how what we're doing might have unintended consequences or impacts on society so on so through that we get to participate in compilers and that Dr。

 Proust is going to be leading the module on Dasha I'm sorry on essentially the open source ecosystem and how that affects compilers and also other projects that rely on open source and infrastructure。

Let me hand it over to Dsha。 Thanks so much。N to meet you all thanks for having me here and thanks all。

Sometimes a homework week。I know how it is， I took compilers 10 years ago。

It's definitely the hardest process。收。Steve， already introduced me but my name is Josh Schtz。Wow。

 something big inflat case。So I'm a postdoc and embedded up。

And I also have another hat that I wear over at the law school， so that's who I am。

My undergra in CS and I recently got my PhD history philosophy year。So I do interdisciplinary。

I researched technology as it intersects with issues of incarceration。The legal system。

So I'm putting my email and my。My website up here， I'm going to share the slides with。

Tonyone wants to reach out to me about anything we talk about today。I'm very happy to chat or meet。

 even if it's not related to。Steve already hinted up this in various ways。

 but why are we talking about ethics in a compilers class？So the first thing I'll say is that。

All of technology ras。其。Technology is made by people and for now， and because of that。

 it's going to be situated in some social political context。

There's going to be values going into the technology and once it's。Implemented in。

Some real world context， it's going to have some political and social consequences as well。

And with compilers， I think even though they're a very technical topic。

 they're so essential to computing that I think it's important to step back and think about some of the issues that are raised。

Because we really wouldn't have modern competing without。Compar to everybody。嗯。

And a lot of compilers are open source， but some of them are not。You might ask。

Should anyone be able to own a compiler？Or in virtue as being such an essential part of computing。

 should it be something that's a common good that everybody has access to for free？By comparison。

 for instance， nobody owns a apple。It wouldn't make sense for somebody to put a copy break。

So some compilers are open source like the ones。嗯。Some are not， so is that fair？

That's kind of the motivating idea going into the lecture。

And because a lot of compilers are open source。We can then ask。All right。

 so what responsibilities do the people in this room have？One。

 we're using open source software like users。So those are the kinds of questions we're going to be thinking about today。

So I passed along a couple of recommended resources for today。

I know it was a busy week because I don't expect that folks。all this stuff。

But just to give you some context on what the content was。

The video is giving some context on what's going on in the world of open source software right now。

 it talks a bit about the park lead vulnerability， which I'll mention later that I'd lecture to today。

 as well as the role of big tech companies in contributing to open source。

 which I think is a really interesting topic。And on the other reading， or this is a video。

- this is a reading， it's by a law professor and it's called the tragedyy of the Digital Commons and it's talking about what kinds of issues might come up when a lot of people are using a common good like open source software that are not necessarily contributing that。

And I'm going to talk about the idea of the tragedy that commons a little bit later on。

 but that's just the sort of context for the meeting。

And you're welcome to come back to it as well for the homework assignment。

So the agenda for today is I'm going to give a little bit of a back。What open source software is？

How did we get to where we are today， why should we care about any of those wises？

And then I'm going to pose this question of whether the freedoms of open source software the benefits that we get。

 whether those come also with responsible。And then I'm going to run through a couple of thought experiments with you all and we're going to have some small group discussion then we'll come back together as a larger class。

チが 먹で。At the very end， I'm going to mention briefly the assignment。

It's just a short writing assignment it should be pretty。So just to start off。

 I was really curious to hear。From you all。Maybe first just like a show of hands。

 how many folks have used open source off？Okay， good。

 I would expect to see every hand in the room go up okay， because every hand in the room went up。

 I means I can call on anybody and ask what kinds of open source software you use right？

So I'll let folks volunteer first and I'm just going to take these up。Who wants to alter。

じゃ the links。呀自己关。二时就识咩。呀自北关。GCC。Yeah， we've got compilers， we've got operating systems。

So that's like an image on a new platform。哦啊。Sorry， can you guys okay， well。

 hopefully you can hear me better now， sorry if folks in the back couldn't hear me well。Okay。

 so we've got like。Image editing software。 We've got a compiler up there， operating system。

 What other types of software can be open source。Firfox， y。For sure， Okay。

 let's get one more example， large language models。诶放7。Yeah， okay。That's an interesting。

Interesting case， which I'll actually mention really briefly later on because there is some debate about how open source large language models actually are。

 but this is not an AI class。 so we don't have to talk about it in detail， but it's， I think。

 a really interesting topic。

![](img/d4fd854ae48c280f771639bb9e87eee5_3.png)

Okay， so we just got a little list up there。嗯。Okay， next question is。

 has anyone here contributed to open source software？Okay， there's a few hands。

Not the full class anymore， but still actually more than I was expecting。 So kudos to y'all。

 what have you folks contributed to？I thought you raised your hand Yeah。

 just small button fixes to a tax editor I use called mouseusepat。Mousefi， okay？Yeah。

There's a thing called Z3 Z3。What is it？It's a formal verification tool， nice。I don't。

I was working at。Contri to there。特ちくで。Thanks， I'm just going to put bread out。Yeah。

What is the for quantum building。Nice， I don't know how that' spelled QIS。Yeah like the IT。IT， okay。

' awesome。Yeah， golden eyee， which is like a DNA and resilience tool。这て。



![](img/d4fd854ae48c280f771639bb9e87eee5_5.png)

P。All right， this is a decent list。Great， so we got a few。Different sets up there。

I did notice it's interesting that there was actually no overlap between the things that came up in the first list and the second list。

 but there is a fair amount of contribution going on。 So that's great and。😊。

I don't think what's happening in this room is necessarily representative of what's happening。

In a typical software development context where a lot of open source software is being used。

 not as much as being given back。

![](img/d4fd854ae48c280f771639bb9e87eee5_7.png)

嗯。So I just Googled that I think 97% of software relies on open source in some capacity。

 including proprietary software。So just interesting。Wい。Okay。

 I'm going to return to this tension in a little bit。

 but I just wanted to kind of get you warmed up thinking about that issue。Okay。

 so where did the idea of open source software come from？

So if we go zoom back in time to the early days of computing。

There was a culture of sharing software openly。 And this is the 60s and 70s。

 This is kind of influence of hippie counterculture era。

 A lot of that is also bleeding into computer science at the time。

 And this is before the era of big tech companies， of course。

 So there was kind of a general suspicion among early software developers towards large corporations。

 and there was this desire to make software that。

![](img/d4fd854ae48c280f771639bb9e87eee5_9.png)

Is not dependent on corporations and is freely publicly available to everybody。At the same time。

 in 1980， Congress passes this act， the Computer Soware Copyright Act。

 which allows software to be copyright copyrighted in the same way that literature can be strangely enough。

And this allows companies to start copywriting their code and limiting public access to it。

 selling it as a proprietary product。Okay， so the same year。

 Richard Staman is a programmer in MIT's AI La。He's writing code to make。

The print Q for his printer more efficient。 The lab eventually gets a new printer。

 He tries to find the source code online to re implementplement the same thing on the new printer。

 and he's not able to find the source code。 So he calls up Xerox and says。Yo， like。

 can you give me your soft your source code， please， And they said， no。This really upset Staman。

 So he then。Decided to found this pre software foundation and the Gnu project and ended upstarting this whole movement that ended up becoming。

Started as the free software movement and then became open source software。

 And I'll mention what the difference is between those in just a moment。So when I say free software。

 I mean free as in free speech， not free as in free beer。 This is also quote from Staman。

So just to give you a sense of what that looks like on the ground。

 here's the kinds of freedoms that are guaranteed by one of the standard free software licenses。

 the GPL， and there's a whole bunch of licenses， some are free software licenses。

 some are open source licenses， and I'll mention the difference in a moment。

 but just to give you a taste of what kinds of freedoms are guaranteed，Forreeddom 0。

 you can use the program for any purpose， even an unethical purpose。 if you want to。

 There's no limit on who can use the software and why。You have， of course， access to the source code。

You have the freedom to redistribute copies of the program to anybody else。

 and you also have the freedom to redistribute copies that you've then modified。

 so if you say want to do some add on， you can then redistribute that with the public in order to benefit everybody else。

There's an important restriction with this license。

 which is that any copies and alterations that you make。

Also have to be licensed under the free software license。 That's something called copypy left。

So basically you can't。Create， you can't take software that's licensed under this free license。

Fork it and make it proprietary。So you can't do that by contrast， with open source licenses。

 you get many of the same freedoms， and in some cases， all the same freedoms。

 but you are allowed to fork it and take the fork and make it proprietary in some way。

So that's the main difference between free software and open source software。

Are there any other restrictions on how you redistribute this software， like person like making it？

Commercially redistributing it it links all in。Yeah， good question。

 So you can have software that is free， as in。Free software。

 but but it costs money to use like some services attached with it。

 So those two ideas don't necessarily go together。 And on the other hand。

 you can have software that's。Free as in you don't pay anything to use it。

 but it can be proprietary in other ways。 So those two ideas come apart。Get at your question？系啊水啦。

Yeah， feel free to interrupt at any time。 I love that culture of Cs。

 which is peppering questions as you go。S bowl。嗯。Okay。Yes， I mentioned this already you can。

You can fork an open source project。Make a proprietary。 This happens in some cases。

 like Amazon did this with Mongo Db， for instance。So from here on out I'm going to start using free and open source software just as open source software。

 but you should have in the back of your head， there is this distinction that could come up in some cases I saw hand Yeah so if there is software that relies on the software a free requirement then are you're an not of charge for something that has dependencies on that as well like but exactly。

 so you can't use it in any proprietary software at all。So that's a major downside。

 or depending on your perspective， it's considered a major downside of pre software。Yeah。

 I'll have the。I think。Okay， I have it one slide after this。

 but I'll show the pros and cons of the different licenses。

 This is just to give you a sense of kind of what some of the existing open source software that falls into these different categories is。

 So I gave you some， some operating systems， some text editors， some compilers。So top rows free。

 open source proprietary， bottom rows， all Microsoft products。And this just came up in my answer to。

The last question， but。One of the cons or what's considered a con of free software is that you can't use it in proprietary software at all。

So I'm not going to dwell on this。 I'm just going to dwell on this briefly。

The way that kind of the spectrum works is on this side， the proprietary side。

 the software is close source， but because it's maintained by a paid team of developers。

 there's certain guarantees you can have。You would think about the quality of the software。

 like somebody is being paid to maintain and sustain Windows at all times。

 like you can be fairly confident about that。 whereas on the other end of the spectrum。

You have free software that has these freedoms。 and you can see the source code。 You can modify it。

 Well it's highly dependent on community maintenance。

 and that can run you into some trouble if the project isn't maintained。In the right way。

And open source is kind of the middle of the road where you still get these freedoms。

 although it depends a bit on the specific license， but you can use it in proprietary projects。

 there is， of course， the con that at any future time。These updates might become close source。

But we see in general now a big move towards open source across the board。Okay。So with that context。

We can think of open source software as basically a community resource where everybody's contributing to it in some way and everybody's benefiting from it。

Some way。And if we get the right。Levels of contribution， then we can sustain the project。

 But if we don't have enough contributors， then the project might collapse or there might be some other issue that arises。

 So that might be because of developer burnout， lack of interest。

 lack of time or resources being invested into it。And in light of that， you can ask， all right， well。

 what do I， you know。R on the mill software developer。

 what ethical obligations might I acquire from using open source software？And in particular。

 do I have some kind of ethical obligation to contribute to the project， so contribute。

In whatever way that is， whether it's labor， money， equipment， bug reports， and so on。

 So like on the LBM site， for instance， you can see that there's different ways that they ask you to contribute if you so wish。



![](img/d4fd854ae48c280f771639bb9e87eee5_11.png)

Okay， so。To explore this idea further， I'm going to use what in philosophy is called the thought experiment。

And the way that these run is。Basically， you come up with some scenario。

That might have seemingly very little to do with a scenario in the real world that you want to reason about。

 But there's some relevant analogy between them。And you can come to a conclusion。

In the imagined scenario。 and then draw an analogy to the target scenario you're trying to reason about and say。

 well， I came to a conclusion in this imagined scenario。 Therefore。

 the same conclusion must apply in， in the real world scenario。

 So that's called an argument by analogy。So I'm going to give you a thought experiment right now。

 And there's a couple of different ways that you can push back against a thought experiment。

You might say that the initial scenario is poorly posed。

 You might come to some conclusion and say it， well。

 I think there's some problem with the framing of the original thought experiment。Or you can say。

 the analogy is actually not so good between those things。

 I think the original thought experiment makes sense， but maybe the application to。

The target doesn't make so much sense。I'm going give you the thought experiment。

 And then we can think about whether there are any issues with the thought experiment。

 We can also talk about that， in discussion。But here's about experiment。Okay。

 so we're in Boston Commons and Barbie and Oppenheimer are。You know， enjoying the funds from。

They're successful movie careers。And they decide to start a side business where they're producing organic sheep's milk。

So they each get a couple sheep。 They start letting them graze in Boston Commons。

 this delightful common space that we all share。😊，And you know， the sheep eats some grass。

Barbie and Oppenheimer each contribute a little bit of labor to help maintain the grassy area。

 They might pull some weeds。 They might water the grass， whatever it might be。 and so far so good。

But suppose Barbie realizes， hey， Oppenheimer's doing a lot of work。Maintaining the plot。

I'm just going to put a few more sheep down and just use a little bit more resources。No big deal。

 Oppenheimer sees this and says， oh， well， if Barbie is going to send more of her sheep。

 then I'm going to do the same。And you can probably see where this is going。 Barbie sends more sheep。

 Op Heber sends more sheep。 They stop contributing。

 They start kind of free writing on this common area。And then we get the tragedy of the commons。

 which is that。All the grass in the commons dies， the sheep。Starve to death。

No more no more nice organic。Sheeps。I don't know， yogurt。For。For Barbie and Oppenheimer。

It's a very sad situation。Okay， so what does this have to do with open source software？

So this is a thought experiment。 Now I'm going to make the analogy。

 So the tragedy in this imagined scenario was maybe that the grass died and the sheep starved to death。

In the case of open source software， if everybody's using。

The software and not contributing back in some way。

 Then we might get issues like overuse and dependency。

 where a lot of systems are relying on an open source software that。

Maybe is not getting the maintenance that it needs。 You might get security vulnerabilities。

 I'll mention one in a second。And you might get long term maintenance issues。

 So maybe it's going become obsolete if nobody's maintaining it and then any system that's relying on it is going is going to have issues。

Now， you can probably already see some potential problems with this analogy。 right。

 Does anybody see any。Any kind of dis analogities。 Yeah， well。

 maybe one of them is that they're consuming some sort of like physically consuming device。

 Well let's say if you're using a compiler， you're not。Really。Like removing some fire mass。Yeah。

Exactly。An open source compiler is not like a finite substance that you can eat up。 and yeah。

 exactly。Okay， any other issues that folks see？Yeah。

 it's not one person's decision to like use more of a resource。

 it's like many people's decision to like simultaneously use the resource。Okay， interesting。

 So here we kind of have this contrived scenario where it's just like two people， but in reality。

 it's like。A whole bunch of people。 Yeah， for sure。

I wonder what you mean by security vulnerabilities。Yeah， okay。

 so I'm going to come back to that in just a second。 Before I do。

 I'm going to respond to the first comment that was raised。

 So maybe we don't have a finite issue with。The actual software， right。

 But is there some other resource。Here that is finite。Program yeah， exactly。

 the labor of the programmers is a resource that is limited。

 There's only so many people that are contributing。

 and there's only so many eyeballs that are going to be looking at any piece at one time。

So maybe it's an imperfect analogy， but maybe instead of talking about the sheep that are dying。

Right， I'm gonna get confused with theity now。 But the， the thing that's finite might be the labor。

 right。So。Let's keep that in mind。 Okay， going to the security vulnerability question。Has anybody。

 I assume a lot of you have heard of the heart lead vulnerability。

 anybody feel like showing what that is？It's been a few years ago now。

It was like hot stuff when I was an undergrad。Maybe someone who hasn't shared yet。All right， yeah。

 good， well， I actually only know the XKCD version。那个一 can。

Send malform requests to web servers and ask it to give you maybe longer strings。

Then what you were supposed to be allowed to do and with that obtain information that not。おや。Yeah。

Awesome。😊，Okay， that's like a more detailed version than even I had up here I on a very high level。

So this is a vulnerability that was mentioned。 That's part of open SSL。

 which is an open source encryption。Software。It was used in a ton of web servers used to protect users personally。

So like a good。Very important piece of software maintained by four developers。

 one developer called it his full time job。So after the heart bleed vulnerability got discovered and got patched。

 I mean， I got patched in like a single day， even though theres only four of these people。

They still don't really have funding。 So kind of we're still in this scenario where。You know。

 a random。Person in Nebraskas thinklessly maintaining like a good chunk of the Internet。 So this is。

 this is a scenario that's happening still， even though we went through that security vulnerability and it became really high profile。

 So I personally thought that was interesting because I hadn't revisited the Harrpbleed issue in a long time。

 turns out still don't have funding， so。Just a fun fact。Okay。

 so we've thought about this a little bit。 What I'm going to do now is I'm going split folks into some small groups。

 And it looks like we're already lumped。Fairly well， but maybe I'll say people who are just two。

 maybe I can split you and send you off， I know I'm so sorry。

 I can split you and send you off to another table so that we have groups of maybe four。

 four or five or maybe you two could go join this group or two over there。Let's， let's take around 5。

7 minutes。 I'll see when the discussion starts peting out。

 But let's talk about what we can do to try to avoid。A situation like this one。

Like how do we avoid a tragedy of the commons in the context of open source software？And。

I want you to come up with three possible strategies to do this。

 I'm already going to give you one upfront， and you're not allowed to use this one。 And this one。

 my strategy is privatize everything like just charge people money to use the software。

 have a pay team of developers to maintain it full time。

But then it's not open source software anymore， right。

 So think about what other potential strategies we could use to avoid these issues。

Do you guys need help finding a group or your okay， sounds good， so let's take five seven minutes。

Yes。Right。あ。です。😀。

![](img/d4fd854ae48c280f771639bb9e87eee5_13.png)

There's one else。It this looks。I think it's how much I。So going free game out there， there's。

 although listen few things like three is why not。What time。Yeah。はです。doing。So。コ。な。you were running。

 let's take just one more minute and I folks don'll have three， that's okay one more minute。😊，😀。

maybe so。's not huge know， go the。All right， folks。

 let's come back together I hear more laughter than talking now。

 which is like the good litmus test for let's come back。All right， laughing group。

 I would like to hear what you came up with since。Can to give me a laugh too？Sure。

 I guess one idea we talked about a little bit is that like it seems。嗯。

You can't rely on companies necessarily to do。 It's not always in the best interest as a capitalist thing。

If they can use a piece of free software and not contribute to it that's just like better for the bottom line and so that if you like comply you can think of this as this is a place where pure capitalism isn't going to be enough to support this common good so then it seems like a in the branch might be helpful so one way you can do it is like to treat。

big open source projects like critical infrastructure。

 and in many cases the actually are if the government is like using one or something， and then yeah。

 just fund them the same way to。Mmhm。Yeah， and great， okay， so capitalism is the problem。Solutions。

Solution is have some kind of government regulation in place， did I get that right？

Yeah and actually the reading I assigned， if this is an interesting topic to you。

The reading basically makes this argument as well， and they also refer to open source as critical infrastructure。

Yeah， did you want to add？Oh， I thought I saw you。 Never。 I thought you， I thought I saw you Yeah。

 I don't have my last song。 Oh， you're fine。 You're fine。 I mean， like the only thing against that。

Its like。Technology changes so quickly in the sense that。

Deciding what infrastructure is critical can take a long time。

I don't know if there's an easier way to do it。You could just have it where it is open sourcing if that would be about for specific。

And you want to fix them。The resources for that in particular。So I guess started有。ial。Yeah。

 so relying on government could。Spifle growth or innovation in some way。

 that's like a common critique here。Yeah， what are other groups， Yeah， I see a handle。

Like students potentially can talk free open source software students。

 certainly can you speak students so for example。If like you know we contribute a couple of commits to like。

 oh， yeah， we should get like， I made it。Do we do。Something like that， you know。

 makes sense possibly create built software that's their final project。Okay。

 so outsource the labor to students。I like that， I like that free labor， Excel。Okay。

Other other ideas。 Yeah， some of the open source licenses。

 the ones I know is like I'm real engineer the engine game management。

which are like free open source to use except from for like I say I think anything where you use it with over 100。

000 users or other users and then you stop paying like a license fee and'm trying to blend be。

Oken So's free idea with also like larger corporations。

 people who are using this as a shortcut to when they have the tools that they could make their own system。

 be able to come back so the development team can actually maintain that。That's really interesting。

 I didn't know that。What is the license call？open。Yeah， anything where you make $100，000。

 I think a year， you occupy feet and then un is no other source， but that a similar pricing home。

Okay， so maybe。Some pay as you go， or maybe like large parties or corporations maybe have to pay to use it。

 but just like Joe Schmo， programmer doesn't have to use。Yeah。I think would be like like one。

thinging that could help is that corporations kind of encourage employees to spend some time working open source things I know like。

Maybe it's just for image purposes， but as you know some companies in give employees like time。

E time to work online。Like maybe the company open source software。

 but maybe also external open source stuff。if the public can put some sort of pressure on the company。

全在か。M。Yeah， okay so。Yeah， get corporations to give back in some。

More organized way than just like expecting them to do it， like require。

10% of employee time to be contributing to open source or something。Yeah。

 basically similar to my interested， but like see open source。

Communities has some type of equity order。The companies。If a company uses to open source off。

It causes。They're starting to go up， the amount of money that the community has。嗯哼，这好。

ll this result for better。Yeah， good。Yeah， another model that hasn't come up is the foundation model。

 which is what Linux uses， which is like。Having a separate nonprofit， essentially that。

Supports the development directly。So I had the corporate sponsorship idea come up。

 and I had a couple of things to say about that。 I'm conscious of time。

 so I'm going to just raise a couple of points briefly。And。

Hopefully we'll have time to discuss as a small group for a minute or two and in large group。So。

 okay。嗯。There were a couple of ideas that came up that are implemented already。

 but largely the solution we see for tragedy of the Commons today is。Corporate sponsorship， right。

 so big tech companies are really the major contributors to open source， both in terms of labor。

 So the idea that came up with。Employees devoting some amount of time to open source。

 that's actually something that Google does。As well as finances。 So on the financial point。

 just to give you a couple of examples。Microsoft acquired GitHub a few years ago。For$7。

 a half billion dollars， IBM acquired Red Ha。And。This is happening across the board。

 So if you watch the video that I assigned， you're gonna to see like more statistics like that。

 like how invested big companies are in open source now。

 which is really interesting if you know a bit about the history of open source。

 because as I mentioned at the start， this movement emerged really as like an anti corporatepo。

 like hippie movement。😊，And big companies used to be really opposed to open source software。

 like back in the 90s， there was this memo that was leaked internally from Microsoft where high-ups at Microsoft we're calling open source software。

 like communist and unamerican comparing it to cancer it's a fun memo， you should look it up。

 And of course， like now Microsoft is one of the biggest contributors both in terms of money and labor to open source software。

 So you might ask what happened， why was there this big shift in attitude， you might think。

 you know companies are just being altruistic and they know that open source is where the innovation is。

 And although I mentioned the security vulnerability。

 I don't know if this is what you were hinting at。 But actually open source has a reputation for being very secure。

 because there are at least for big open source projects， there's so many eyes on it all at once。

 And this is something that's desirable for companies。

But there's kind of different reasons that companies might contribute to open source software。

It's like already mentioned this， recent innovations， quality of the products， save costs。

 so other developers are doing some of the work for you and you can use that software in your own proprietary software because remember open source software you can fork it in that way。

You can gain competitive advantage in some cases。IBM， for instance， acquired Linux in 1999。

 I believe， in order to take away some competitor advantage from Microsoft。

 So that was like a move to try to take up some of the market space。

 We see other cases like this more recently， as well。

Companies might promote the adoption of their own software。

 so I'll briefly mention a case on the next slide， but the idea here is basically creating large open source environments that are highly compatible with proprietary products。

 So you kind of like hook the customer in with the the open source part and then once they're hooked。

 you give them the proprietary piece。And then you can also sell complementary products or Fork can reimplement as a proprietary product。

So this is happening， potential downsides。 This is a quote from the paper I assigned。

 which I really liked。When paid contributors are the only developers on a project。

 then the tail begins to wag the dog， and the project is more likely to support the company's profits over the public's best interest。

So if we go back to the idea of the commons， we might worry about whether the commons are really the commons anymore。

 if this is the scenario on the ground。嗯。Okay，2 second example， just like example from I Ds。

 So visual studio code is。An open source IDE， and it just happens to integrate really well with other Microsoft products because it's developed by Microsoft。

When Microsoft developed this IDdeE， there was already a leading open source IDE called Eclipse。

 I have no idea this is like a commonly used IDE anymore。 It's what I used in my undergrad。 No。

 I'm seeing like some nods， some shaking heads。I feel old。 Thank you。

So why did Microsoft do this well。A common interpretation of this is。

That by releasing a competing open source IDdeE， they were able to both set the standard for kind of what's the quality of IDEs out there and to shift the developer community over to an IDE that just so happens to also integrate pretty well with Microsoft products。

So the director of the Eclipse Foundation responded to this。

 anyone who's relying on visual Studio code is also then going to be dependent on future investment by Microsoft into the ongoing development of the product。

 so this is another issue like now we're also dependent on a private company to maintain this public system。

嗯。This is tangential， same issue happening in open AI right now。

 A very cool article just released about this topic。 If you're interested， I recommend taking a look。

Okay， so。We can come back now to the tragedy of the commons idea and complicate it a little bit。

So I'm calling the scenario the tragedy of the sort of commons， where the commons are functioning。

 Everybody has access to it。 Everything's running smoothly because Barbie Corporation and the Manhattan Project are contributing strongly to maintenance of open source software。

 But the open source software is now also。Highly compatible with these two like proprietary tools that are developed by all。

By Bob and by Barbie。And this might be okay， but suppose you're allen and you come along and you have a sheep。

This， this analogy is starting to get a little bit thin， but suppose like。The sheep， the sheep here。

 I guess， are now helping not only eat the commons but like they're also doing labor。

 they're maintaining the commons as well so Alan wants to contribute a bit of labor his labor is not going to count at all compared to these giants like Aen is really small anything that he does isn't really going to change the state of affair as much in the common space and also really there's very little space left that's not taken up by Barbie and Oppenheimer。

 so he's probably going to have to pigeon ahole himself into one of these environments that's controlled and highly compatible with corporate interests。

 which Alan， you know if he's a hippie he might not be into that。



![](img/d4fd854ae48c280f771639bb9e87eee5_15.png)

![](img/d4fd854ae48c280f771639bb9e87eee5_16.png)

So what's the tragedy of the sort of commons and this is just a term that I invented。

 so don't cite me on this。 It's technically open source。

 but it's controlled and maintained by large tech companies。And the public。

 in order to engage with that open source software。

 has to also engage with the company's products in some way， maybe they don't have to。

 but it's highly convenient and likely that they're going to do that。

 which is then going to benefit the company。And also。

 small contributors like Alan don't really get a say in the direction that open source software is heading。

 So maybe it's common in the sense that you can still access it。

 but you can't really determine the direction of the development of open source software the way that you might have been able to say。

 30 years ago。So。You know， I guess I would pose the question to you all， is this a problem。

And if it is， what's the potential strategy we could use to mitigate。

The problems that are going to be confronting somebody like Alan in the scenario。嗯。

So I'd like you to go back with your groups。 Let's do three minutes。 This will be a short one。

Let's think about what strategies might。Mittigate the scenario and。Conversely。

 what unanticipated consequences might that strategy have。 So let's take three minutes。

 Let's keep it brief。And then I'll come back together。Shere what。可。 I mean。

 like he can just's just how。Okay， I thought we had less time。 We can take five minutes for this。

 sorry to rush you all。that like engagement。also things show that away。あのほらちゃあげてね。So Microsoft yeah。

download website website actually。还有。how it working people outside of the companies。😀。not。

Anything I don't。think like。It's yeah， I're awesome that。Microsoft saw handle at that point。

他那 force大。All right， let's come back together。いせ？Okay， how did people fare with this one。

 that this thought experiment was this two out there， people are okay with it？

 I'm curious to hear what folks came up with。How do we help Aen we're talking about some of the Fors projects that like。

D Google or see。Thanks so。发。嗯。But one downside of that is that it does make some very serious。然后呢在这。

That。Compans parts of the good， but because at least on open source it' always an option。

Thank you For can do。嗯哼。Okay， so you would have a lot of collective effort from would these be people within Google or folks outside of Google。

To that average small user。If there's a group of them don't like。Have the option。Okay。

Collective resistance from some group external to the company to。Decorrate。Some piece of software。

That's a cool idea。嗯。Do you think there are any unanticipated consequences from that and somebody else from your group can feel free to answer if you want？

Well I guess one thing is when it is really tightly bound to the company's ecosystem。

 the proprietary parts can be。Cs off for that。Open source。Right。た。Linux， who did that。

 Red Ha did that。 Yeah， Oh， okay， so you have like some insider fire。😊，Yeah。Yeah。

 very interesting idea。 Probably hard to scale， I would imagine。

 but I would guess in some individual scenarios we could probably。

Try to just forcefully take back a piece of software that's been captured by。A big company。 Yeah。

 cool idea。 I liked it。Yeah， what did other groups come up with？I mean at the very last moment。

 we suggest like having a council of sorts that democratically the like life。

Like which changes should be made to code？嗯。I I didn't really like have enough time at the end to like talk about consequences。

 but I thought maybe when was that like。If like you need like a body to like enforce the changes。

 right， and it's also it's possible that a company might like try to buy out。

The governating body or like try to influence。Their decision may hand in some way。

That's a really interesting idea。Okay， so have like a mini。怎么。Democratic system。嗯。

So like most language a lot of blame have that。So I guess something like this happened me。

Thanks plus plus。嗯。如果 want to。Take the line them a certain way， and they did。You got carbon mine。

Yeah， steering councils。Representatives of maybe。Companies and then representatives that。Mhm。Yeah。

And are there potential？Yeah， UC didn't have time to think about it， but what do folks think？I mean。

 that prevents， I guess， like corporations for maybe being。First place， but like。啊。

With like poing and stuff， what company wants to。Make this change again。They can always just been。それ。

And then you kind of have that same where there's a version that is maybe better because it's tightly mono with these。

Mart services has all the money and then there's the community volunteer version。H。Yeah。

 let's hear from you。I don't know。 I feel like I'm picking on this table a lot。

 If other people want to chime in and I'm not seeing you just raise your hand a little bit higher。

 Yeah， one other thing I don't want to open source models like a lot of open source projects either operate on like a semide thing or likeneent dictatorship model and like one pro of the latter models that like development happens faster。

啊。So in this like democratic one， it's like。It depends on what level of like decisions your counsel making。

 but if it's like every PR your five people have to come together and then like。You know。

 project development is probably。嗯。Okay， yeah， so speed is definitely consideration。

Did you want to add something as well Oh I was going to talk aboutneent figures too。

maybe in terms of bureaucracy， if let's call， these companies end up being the majority on this council。

你 doesn是佢稍等啲。对 yeah so I do you't want there should be need这个 certain parties。比如说s。Okay。

 so it sounds like there's a lot of implementation questions there。But potentially。

 potentially good solution。It would be tricky to iron out the details。Yeah。没有。Great suggestion。

What what did you folks talk about。Over here， we were talking about was it like make a For and repo get like community like and they disagree？

And yeah， talked about the consequences where。A private company， but usually like have。

Sort of proprietary parts that are actually required to make a function that you may not get。Mmhm。

Yeah， okay， so similar conversation to。 we can fork， but maybe we have limits in how。

Scalable that is or how much it's going to apply to every part of the code base，Yeah。

One thing is that。随面呢。Sometimes sometimes it's just like natural check in that like if the community of people who disagree with like company open source projects is large enough。

The people who like。Just like the existing projects are also usually the people who are willing to contribute to like third party software or like other software。

 interesting point， especially because sometimes the corporate version。

Like something like VS code probably appeals to like。

So if someone is really passionate about their code editors。

 then they're also probably passionate enough to like dedicate some small amount。

Like labor or like money to whatever other project that they use。Interesting。

 so we might run into the same issue， but now instead of。

Who's contributing and maybe who's willing to volunteer to like。

Be part of like the steering committee or。Yeah。Or in your case， though。Yeah。

 run into similar shoes with who's going to be sustaining like the forked version。

So maybe we're just kind of like punting the tragedy or we're giving up the tragedy of the sort of commons。

 but we're returning to the tragedy of the commons。that。The fairway。

I don't know if that's too too many， too many tragedies。Ped on top of each other。But yeah。

 it kind of seems like we're in this trade off。Right， which seemss tricky。

What did other folks talk about？Like we' here， we've heard steering committees forking and kind of decorporatizing some open software branch。

Did anybody talk about government solutions at all？I think we talked about like。

Maybe doesn't seem as bigger than deal。Big corporate companies are like controlling big projects just because like at the end of the day。

 you can choose what you're using and stuff and if you don't like you。

nge it but I think like a big problem is like sort of projects that are sort of evolved like Ya itself rather than switching parts of the project so like if it's something that is not commercially oriented。

 there's less of an incentive to develop those projects so those that can government，相关。嗯。

I'm thinking like something along the lines of what， for example， evaluating。W models。嗯。

Ma sure they all。there any questions？Yeah。Interesting that did other。

 So I want to go briefly into your first point， and then I'll return to the second one。

 Did other folks also have the intuition that。Like， so what， Like this is。

 this is actually fine like。I don't know if the hands are you want to say something or you're disagreeing。

Anyone want to chime in？Yeah， I guess we have one one thing I says。

By electing to publish software with an open source license。嗯。Is a choice that the developers made。

acceptccepting the issues that come with it。And you can always。

Come up with a more restrictive license or if like。嗯mm。Right。

But if open source becomes so ubiquitous that it's in everything。

 then it may not really be a choice like if I'm。Using like no matter what。Web server I'm using。

 it's going to have open SSL in there somehow。Maybe I don't really get an essay。

 at least as a consumer， maybe's a developer， you get a choice。Just push back a bit。Yeah。

 but to the second point of kind of the philosophy behind。

Like the origins of open source maybe is like being decoupled from corporations and allowing you also to develop software that doesn't have an obvious。

Monetary component。 I think there's something important there。

 At least like my intuition tells me there's something important with that kind of like philosophical。

And open source， you know， is distinct from free software and that it does permit this。

Relationship with proprietary software。I still think there's like attention there。 that's。

 that's at least like interesting to me。Did anybody want to regulate tech companies？

嗯We briefly好得 about。嗯。But we didn't think it was particularly feasible。

 like trust doesn't really seem to very optimistic they can。Mds feel a lot more ambiguous than that。

可以平留呢度你啦即。To have this be open soly， technically， there's nothing wrong than just like making。

So project a lot more well integrated like corporate solutions as it's still open。

 so it's feel like college corporations could that effectively litigate their mail out。Mmhm。Yeah。

Yeah。Turkey question， I know。It remember， I don't remember off the top of my head。

 I think there was like a duoppoly scenario when Google acquired Android。And。

 but I don't think it ever proceeded to litigation。 But I think like this， this issue of like。

The monooppoly questions。Definitely relevant。Yeah。All right。

 did we get any other ideas that haven't come up in discussion yet？The folks in the back。

Come up with did your ideas already come up from another table， yeah。Okay看。Cool， well， in that case。

 I will。Tell you a little bit about the assignment， and then I'll hand it back to Steve， unless any。

Last kind of burning thoughts folks have about this fabric。All right。Okay， so just。Wrapping up。

 what do we think about today？So open source software comes with some freedoms。

 which I mentioned in the beginning when I talked about GPL， so you have access to the source code。

Distribute it。 You can make。Copies that you've modified。

And that makes it an important community resource。But that model requires contributions in order to be sustainable。

And。We talked about one possible scenario that， that happens if the contributions。

Ar't happening in the relevant way， which was the。The open SSO。Security vulnerability。

The paper that I assigned as recommended reading， talks。At length about this issue。

 not specifically with heartbleed vulnerability， but with。

Just like security vulnerabilities in general。 So if this is a topic that's interesting to you。

 I highly recommend that paper also came out this year。 So it's like very。Timely。Okay。

 so then we talked about who should make those contributions， is it？

Maybe individuals who are using open source。Are we just going to leave it to the dedicated individuals who are passionate about it？

Should large corporations be the main contributors and is that a problem？

Should governments help sustain certain open source initiatives that are maybe not for a monetary end？

And I guess I'll just like leave。You with the thought。Which one do you think is best？And I would ask。

Okay， so for the assignment。I want you to write。Respond briefly to this prompt。

 which I think should be fairly easy based on our discussion。 But if part of it isn't clear。

 feel free to ask me now or feel free to。Email me as well。 again。

 I'll share the slides with Steve Dan。So here's the prompt。嗯。In the context of public lands。

Sometimes。A tragedy， the Commons is prevented using some kind of。Like a government intervention。So。

For instance， if we want to prevent overfishing from a lake in a national forest。

We might require the purchasing of permits to fish so that we can limit how much each individual is fishing and also make them contribute some financial amount。

嗯。So。If we make an argument by analogy to open source software。

 we might conclude that the government ought to put limits on how individuals or big tech companies use and contribute to open source software。

 That might be the conclusion we come to。So do you agree with this conclusion？Why or I not？

 And actually， the version of the assignment I have， I forgot to change it in the slides。

 but I actually。The way that I frame the final question is， do you think it's a good analogy？

And then do you agree at the conclusion？Because we might think the analogy is good or not good。

 And we might think the conclusion。Is agreeable for independent reasons。So， so again。

 this is kind of an example of a thought experiment where here the thought experiment is。Overfishing。

 like， we want to prevent the problems of overfishing and it's public。

Like a lake in a national forest， so we're going to institute。Permits。

 and that's the best way to monitor to prevent this problem。 So the conclusion is basically like。

 we should have permitting。And then the analogy is to the open source context。

 and you would then come to the same conclusion， which is that we should use permitting to solve this problem。

So。喂。Source， kind of thought experiment， target。 And we're making this analogy and transferring it。

 So is that a good analogy。 And should we agree the conclusion。This is going to go up， I think。

 on canvas as well， so no need to。Track it down， but I just wanted to explain it before you face it on your own。

Okay。Well that's all I have for y'all it was really nice to chat with you for a little bit do folks have any final questions or thoughts for me before I let you go？

Or should I hand you off to Steve， Do you， Do you need to if there any final questions。 Yeah。

 maybe let's two final questions。 and then。Take it away。Yeah。

 do you have thoughts on cases like Re where like it was initially like a private software and that it was made public？

I。I don't personally know， yeah， but we can pose that question to other folks。Yeah。

Does anyone want to comment on that？React。Private one public。This might be a bit tangial。

 but what do you think about like big companies acquiring the open source the platforms on which open source software is host？

Mhm。Yeah， I think that's a really interesting case。 And I'm。

 I'm not completely sure what to make of it， but I guess I tend to have some of a critical stance where I think this。

There's probably multiple ways that this is going to benefit Microsoft。

 but that also benefits everybody else， so。Yeah。出ie。But yeah。

 I don't have anything super smart to say about it。 I to clarify， like。

 I also don't like study this topic， but I think it's really interesting。

And I have a friend who wrote a great paper about Open AI。

 which is how I started thinking about this， which is the paper that I include。

And it's really interesting and you should all read it。Okay， I'll hand it off to Steve。Great。

 we'll post this assignment somewhere in grade scopepe or canvass along with the due date and the exact wording。

 so you don't need to worry about writing this down or looking at it。

So we'll announce that and appreciating that you have a few assignments out so we'll make sure that you have enough time to fit it in to everything else that's going on although it's a smallish assignment Thanks very much everyone Thank you especially for making efforts shop in person and engaging the discussions。

Yeah， have a good weekend， good luck with Homeook three， Homeook4 and see you on Monday。😊，そ力かす。我是。

我他す。Okay。No but like no but like it has to be。那这个第。

And they have to be mergeed and like you get merge and they are they were them。こじ。す。You're like。出てと。

Yeah。我我们还。It interesting I was like the pass。Lasts time we're here from。

take to that and actually that。What is this whole ecosystem， when is it the way it is？不一样。

So since I was this is a bad seat， right。I was so shocked that nobody uses acclaim sauce。

I used to use it and it's just getting so heavy weights。😊，And the as photos as links。

It's actually a real。Really nice things and just a much better。What they exchange？ちとき。Well， not real。

So strange， I hope people were able to super text Yeah， it's actually whatever it is like 2。

21 screens and so controllable in various ways is one large thing。27 individual inputs。

I'm not fan2 not fan hurt Yeah， I like hard well also it's like a large portion in the room is kind of off on its still like。

This is like over there。I was finding where I was figure right now。で。

thatd be an issue with the projection。Yes。Yeah， both for both your slides and for community slides there。

他 was接。The acoustics are really bad， too， I find， don' you， don't you think Stephen。

 I'm the acoustics？

![](img/d4fd854ae48c280f771639bb9e87eee5_18.png)