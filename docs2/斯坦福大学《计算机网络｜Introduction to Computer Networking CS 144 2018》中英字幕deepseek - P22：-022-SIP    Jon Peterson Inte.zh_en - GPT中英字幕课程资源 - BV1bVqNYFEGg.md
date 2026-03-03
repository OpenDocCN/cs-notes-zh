# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P22：-022-SIP    Jon Peterson Inte.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

So here I'm with John Peterson， who's an old friend of mine and actually a pretty important person in the internet and thought we'。

And so we thought you could sort ask John a bit about what's going on today。

 some particularly interesting topics， but maybe we should start with。

 so how did you get involved in internet governance？That's a good question。

 so I was lucky enough to be around in the early。com boom in the late 1990s and a small startup that I worked for in Boston was acquired by level three communications。

 they moved me out to scenic Boulder， Colorado where field actually was as well roughly the same time。

And level three， of course is one of the tier1 backbone providers of the internet。

 and they have a profound engagement with the Internet Engineing taskask force and the standards bodies that help make the internet to define how the internet works。

And when I got there， that was one of the things actually that most attracted me about this opportunity would be the ability to really work with the top minds who were out there。

 and so I started attending the ITF， I'd be on mailing lists and things like that beforehand。

 but I first started attending when I wrote at level three， and。

I just found it to be a fascinating community that had such intellectual rigor that just had so much interest in trying to find the right solution you don't go to the ITF and。

Represent a company you go there and you put forward what you think is the best idea。

 and it's really a place where there is a meritocracy of ideas。Once you get the bug for it。

 of course， you discover there are all these other dimensions to internet governance。

 if you're there at the ITF， you may end up dealing with the W3C if you work on applications as they have responsibility for the standards associated with the World W Web like HTML。

 you may end up working with ICAM with the people that do domain name assignments and I kind of made the rounds of these Internet governance circles and working on the intersection between technology and public policy tends to take you some pretty interesting places。

Well， so let thanks to the first work that you did with SP the session initiation protocol do you want to talk a little bit about this IP telephony and kind of what that path was and sort of where sip is today and what your part and it was Sure it's important to remember that in the early 1990s there really wasn't anything like voiceover IP there was some experimental technologies people had rigged up that worked in some of the unique environments in labs in California and so on but there was no commercial product you could buy that would let you talk to somebody else over the internet remember as well that you know in the mid-1990s you know a lot of computers didn't have adequate sound cards or wasn't adequate video capture。

And you network interfaces were spotty at best and the actual commercial services that you could purchase。

 especially at the consumer level to get enough bandwidth to communicate over the internet。

 something like Voice IP that didn't really exist so sometime around 1996。

 1997 we'd hit a sweet spot where the computing power was there， the network was there。

 computers tended to have the right interfaces to do this。

 and so we started to see the first commercial voiceice IP offerings around that time。

When I started working on this around then 96，'97， I worked on the infrastructure dimension of this。

 the startup that I worked for in Boston was focused on the particular problem of how you could take a traditional telephone switch。

 these telephone switches made by companies like Nortel and at the time Houstonend they were enormous expensive monolithic。

 special purpose devices that required a ton of operational oversight it didn't really fit into the internet software model or kind of the internet disruptive innovation that we all associate with technology today。

And so I was one of the first people to work on something called soft switching。

 the idea that you could just take a general purpose computer， take a sunbox， Uniix box。

 and put the control plane logic for a telephone switch on a box like that and is how they control telephone resources that actually handled switching literal circuits from one customer to another to handle those is dumb devices。

 and this created an extremely disruptive influence on the telephone switch market and today I think it'd be safe to say that it's become dominant paradigm and that you actually can't really buy things like these Nortel switches anymore except on the secondary market you own one and you need replacement parts today。

 you pretty much have to get them on ebay。If you like new blind cards and things like that。

Now once you build a soft switch naturally these sunboxes or other UniX boxes。

 they have internet access and you need to have ways for these switches to talk to one another to be able to coordinate calls that don't use the outdated S25 based SS7 systems they' used in the traditional telephone network and that's where tools like SP started to come into play so a lot of my early work on the session initiation protocol was on teley replacement was on how you would be able to not touch that traditional network but instead do all of this over the internet to be able to set up calls at to end and。

This turned out to be a pretty important dimension of adopting voice or IP protocol it's one thing to build a tool that lets you talk to anybody else who happen to have a good computer in the 1990s and similar technology that you have but very different matter to be able to call someone who's actually on the telephone network with a real telephone number and these saw switches became bridges between traditional telephone network and people in the voiceice for IP space and these have been essential going forward to how voiceice IP has become successful to the ability for programs like say Skype today to be able to call out from your PC to someone who has a normal landline Black。

Also think one of the things that you worked on in sort of the more refined versions of SI was its security model right how do you actually secure the signaling protocol so as I'm sure you can imagine given sort of some of the recent events in the internet respect to So Snowden releases this sort of interesting question like what is I mean do you see some。

Something about the implications of stuff like SI and security with respect to then PSTN。

 like wire are topping laws， all those kinds of questions。

 like where do you think this is going or how is it different？Big question yeah。

 so I do recall when we're building the RFC for RFC 3261。

 we basically kind of juice straws for who is going to do what parts。

 you know I got to write the overview of how S operated little one paragraph statement and I got to do addressing I got to do user agent behavior and then I drew this straw to do security。

And I like， okay， I have a bit of a security background。

 this shouldn't be too difficult and the initial plan one section on security and SIF actually ended up being four chapters of the RC and at the time this was the largest RC ever published since did not come out then。

And S security has always been a problem child。And these revelations。

Obviously it put the ITF and the people who developed standards in a very interesting position。

 you know， no less authority than Bruce Schneer， who wouldn' to say is one of the greatest minds taking to data about security has formally called on the ITF to drop what it's doing and to refocus all of its efforts and our upcoming meeting which will be in Vancouver this November on how we're going to resolve the problems that have been raised by pISM。

And。You know， we've studied the privacy properties of these protocols and the security properties of these protocols very extensively。

I'm as convinced now， I think as I ever was， that we made a lot of compromises in the design of SP security。

Because they were necessary for it to be adopted in the marketplace。

It would be great to be able to design a protocol that had and then security that can guarantee integrity and confidentiality between one end point that's trying to make a call and another endpoint that's trying to make a call as soon as intermediaries are playing some role in the delivery of that as soon as they need to help you to find the right endpoint and this dynamic capability that SI has to allow if I wanted to have five devices that would all register under my Sname。

 a desk phone， a cell phone， my iPad， various other devices。

They don't need to register to some server that lives in the network somewhere that's going to be responsible for routing traffic to it。

 the degree to which that server has access to signaling， has access to who's calling me。

 you know what are the media streams that are going to be set up and what are the IP endpoints that media is going to be sent between。

We could have done more to protect that boom design sip。And I think if we had。

 we would be talking about SP right now。Because it wouldn't have succeeded enough for it to even be noteworthing。

Also what are some can talk a little bit about so might be a protocol that most people don't realize that they're using or where it's being used want to talk a little about where it's been successful and where it's been really so I mentioned Skype。

 if you do Skype in or Skype out typically that is Skype's internal protocols converted for converted it intoSI for transfer to a gateway which would then go to the telephone network。

Basically， if you use a voice B IP service or a landline in your house that comes from either FIO or from a cable provider that's surely sent that is being used in the background。

 the third generation cell phones things through3G PP gates。

 all use S signaling inside them now I mean these networks especially when we talk about mobile phones and about the networks we see and the cable MSOs and so on。

 they use a version of sit that is relatively architecturally similar to the telephone network。

 they kind of apply the protocol machinery is set to generating a system that has many the same properties that the telephone network。

And this too is it's a fundamental trade off in anxiety of these things。

 I would love to see a sip that was。Much less dependent on the network elements shaping traffic and deciding that it was much more driven by the endpoints this is just kind of fundamental and then principle of the internet that you want to have the smarts be on the endpoints you don't want to have an intermediary in the middle need to understand what endpoints want to do it shouldn't get in their way it shouldn't prevent them from negotiating if if I may have a great new code tomorrow and I have a copy even you have a cop。

But since on our G machines， I don't want that thing in the middle of the network to have to know anything about that codeak to let us connect and to use it。

The realities though， of how these things actually get implemented。

 especially when you're doing something as complex as replacing the telephone network。

 replacing AA more than a century old system with its reliability constraints with its emergency services implications。

 so the ability you call 911， just getting the basic services people associate with this right。

It requires you to make compromises and I can't say I'm always proud in retrospect of the compromises we needed to make in order for this to be successful。

 but I do acknowledge in retrospect that if we had pushed back on some of those compromises。

 it certainly would have led to the depth of the protocol。And as people who design standards。

 this is a heartbreaking thing that you come up against again and again now we can be smarter about this and I think。

If there's a silver lining to these increasingly disturbing revelations they're coming up about。

wideidespread state surveillance of the internet it may create a political will to see a change in what we can get consensus for and hopefully in what people will be willing to deploy。

 you I believe when you go to the ITF since it is consensus space there are things we could get consensus to do that I think would be very radical at this point because the people who go to the ITF are so well informed they're so energized we're so interested in individual liberties。

 I would hate to see the ITF though become an organization that is developing standards that never see the light of day because it is swung too far in this direction and so it's very difficult for us to understand what the right course is for us to chart at this point。

Interesting， interesting。So I'd like to wind back a little bit where you mentioned about how building sort of the first soft switch or devices and all the logics in the general computer at that point。

Harens from sunbox， but。Do you see a parallel between that and then software defined networking today where we see that transition may be happening in the internet and sort of all some of the momentum occurring behind SDN？

I mean， I certainly see many parallels there I'm not sure those parallels will play out in exactly the same way because the companies like Cisco and Juniper would stand to be disrupted by that's the way that' say Lotel and Luccent were in the 90s they are more agile companies。

 they are companies that are taking these technologies and trying to figure out。A middle path。

 I guess， for example， there is the I2RS， the interface to the routing system standard proposal circulating in the ITF now。

 it's a bit different than the very low layer software defined network approach that we see saying in the open networking foundation。

 but it's nonetheless a way that software can interact with the FIb and that help you know higher level routing decisions get made and you know I think the routing。

Vendors view this as one tool among many that will help decide how packets are going to be forwarded。

 They're figuring out ways， in other words， to subsoon this。

That will allow their device to take advantage of the strengths of this without necessarily eroding the market control and the lengthy installed base they have of maintenance tools and so on that have proven so successfully an internet in the past。

I don't know that。Coor routers have to the degree that。

O telephone switches did impeded innovation in the network as well。

 and that was another real driver for doing soft switching was that these traditional telephone switches。

Were so monothic， they had no programmability， there were no realistic interfaces that you could use to alter their behavior without doing open heart surgery。

嗯。The situation is very different， I think for poor routers， but the parallels， I mean they do stand。

 I certainly wouldn't dismiss it out of hand and I certainly know people who work for major router vendors who you find them at the bar at the right hour will cry on your shoulder and not exactly there are concerns about this and it is a real challenge for that business。

Well if you' were to look at all the different pieces of work。

 we say how many working groups are in the IETF today？

O the top of my head I'm not sure I could say order 100 so if you were to。

Think what's the sort of suggest to somebody hatey this is maybe something you should keep your eye is what I think is some of the most interesting work going on the internet of stuff which is currently in progress and might really significantly change what the network's like in three or so years where would you suggest looking but actually that I RRS group would be a very significant one that I put to right now there is a new effort that's just been spun up it's unclear if it's going to be a working group or not it's called perpas which is the ITX forum for discussing for and we're discussing how these security things were to be addressed。

 there are already some proposals that are circulating there that are really about structural changes to how the ITF process would work for should standards have to need a new bar basically in order to to obviate the very real concerns that are increasingly coming to light about all of this if you were coming to Vancouver this time these are two things I certainly。

There are things I personally happen to be written on。

 I think are very interesting and impactful of that you know might not。said to exactly that level。

 but I continue to be very interested in。In CDNs and the degree of internet traffic that is now being directed by content distribution networks。

 we're doing a lot of work today on interfaces for understanding how CDNs can express their coverage areas and how CDNs can advertise。

Services that they provide in order to allow collaboration or clearinghouses among CDNs to make more optimal selections of CDNs。

 I think this will have potentially a tremendous impact on the efficiency of internet traffic will alleviate some of the bottlenecks that people protect。

 more and more video moves on to the internet that's a personal pet project of mine。

 and I am also still working on some things related to the intersection of the telephone network and the Internet。

One thing that's been， I think， a major issue。In rovo calling。

Has become an increasing problem as the internet and the telephone network have become more interconnected。

And right now I'm looking at ways that perhaps we can do better identity services。

 so it's harder to spoof calls it's easier to find out who's responsible for a telephone call that's coming off the internet before it hits the PSTN as the numbers for this are just going up and up and up the FTC and the FTC or profoundly interested in finding solution for this。

 this is work that is being discussed in congressional subcommittee it's already as it's going on in the ITF that's a place where I think we can really make a difference and something that is hurting consumers and will。

forward if we stop and we have you to thank Great well thanks for comingbar thanks for your time my pleasure yeah。

 thank you。😊，Bye。