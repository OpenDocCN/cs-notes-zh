# 【计算机网络 CS144】斯坦福—中英字幕 - P135：p134 9-1 Jon Peterson Interview -- SIP and Security - 加加zero - BV1qotgeXE8D

 So here I'm with John Peterson who's an old friend of mine and actually a pretty important person in the internet。

 And I thought we'd。 And so you're not。 you could sort of ask John a bit about what's going on today。

 some particularly interesting topics， but maybe we should start with。

 so how did you get involved in internet governance？ That's a good question。

 So I was lucky enough to be around in the early。com boom in the late 1990s。

 and a small startup that I worked for in Boston was acquired by Level 3 Communications。

 They moved me out to scenic Boulder， Colorado， where Phil actually was as well at roughly the same time。

 And Level 3， of course， is one of the tier one backbone providers of the internet。

 And they have a profound engagement with the internet engineering task force and the standards bodies that helped make the internet to define how the internet works。

 And when I got there， that was one of the things actually that most attracted me about this opportunity would be the ability to really work with the top-line sewer out there。

 And so I started attending the ITF。 I'd been on mailing lists and things like that beforehand。

 but I first started attending when I worked at Level 3。

 And I just found it to be a fascinating community that had such intellectual rigor。

 that just had so much interest in trying to find the right solution。

 You don't go to the ITF and represent a company you go there and you put forward what you think is the best idea。

 And it's really a place where there is a meritocracy of ideas。 Once you get the bug for it。

 of course， you discover there are all these other dimensions to actually get governments。

 If you're there at the ITF， you may end up dealing with the W3C。 If you work on applications。

 if they have responsibility for the standards associated with the World Wide Web， like HTML。

 you may end up working with ICAM， with the people that do domain name assignments。

 And I made the rounds of these unit-covering circles and working on the intersection between technology and public policy tends to take you into some pretty interesting places。

 Well， so， the first work that you did was with SIP， the session initiation protocol。

 Do you want to talk a little bit about this IPs left any， and kind of what that path was。

 and sort of where SIP is today and what your part in it was？ Sure。

 it's important to remember that in the early 1990s。

 there really wasn't anything like voice or variety。

 There were some experimental technologies people had rigged up that worked in some of the units environments in labs in California and so on。

 But there was no commercial product you could buy that would let you talk to somebody else over the internet。

 Remember as well that in the mid 1990s， a lot of computers didn't have adequate sound cards or certainly wasn't an adequate video capture。

 And network interfaces were spotty at best。 And the actual commercial services you could purchase。

 especially at the consumer level， to get enough bandwidth to communicate over the internet with something like voice or IP。

 That didn't really exist。 So sometime around 1996， 1997。

 we hit a sweet spot where the computing power was there， the network was there。

 Computers tended to have the right interfaces to do this。

 and so we started to see the first commercial voice right through the offerings around that time。

 When I started working on this around then '96， '97。

 I worked on the infrastructure dimension of this。 The startup that I worked for in Boston was focused on the particular problem of how you could take a traditional telephone switch。

 These telephones which is made by companies like Nortel and the time Lucent。

 they were enormous expensive， monolithic， special purpose devices。

 They required a ton of operational oversight。 It didn't really fit into the internet software model or the internet disruptive innovation that we all associate with technology today。

 And so I was one of the first people to work on something called soft switching。

 the idea that you could just take a general purpose computer， take a sandbox， a Unix box。

 and put the control plane logic for a telephone switch on a box like that。

 And just how it controls telephone resources that actually handle switching little circuits from one customer to another to handle those as dumb devices。

 And this created an extremely disruptive influence on the telephone switch market。 And today。

 I think it'd be safe to say that it's become dominant paradigm and that you actually can't really buy things like these North Wales switches anymore except on the secondary market。

 You own one and you need replacement parts today， you pretty much have to get them on you then if you like new buying parts and things like that。

 Now once you build a soft switch， naturally these sun boxes or other Phoenix boxes。

 they have internet access and you need to have ways for these switches to talk to one another to be able to coordinate calls that don't use the outdated X25 based SS7 systems。

 They're used in the traditional telephone network。

 And that's where tools like SAM certificate to come into play。

 So a lot of my early work on the session initiation protocol was on telephony replacement。

 was on how you would be able to not touch that traditional network。

 But instead do all of this over the internet to be able to set up calls at the end。

 And this turned out to be a pretty important dimension of adopting voice array protocol。

 It's one thing to build a tool that lets you talk to anybody else and happen to have a good computer in the 1990s and similar technology that you had。

 But very different matter to be able to call someone who's actually on the telephone network with a real telephone number。

 And these soft switches became bridges between the traditional telephone network and people in the voice-by-piece space。

 And these have been essential going forward to how voice-by-piece becomes successful to the ability for programs like Safe Skype today to be able to call out from your PC to someone who has a normal。

 grant-line， back phone。 Also， one of the things that you worked on in sort of the more refined versions of CIP was its security model。

 How do you actually secure the signal protocol？ So as I'm sure you can imagine。

 given some of the recent events in the internet with respect to the SNODIN releases。

 This is sort of an interesting question of what is， I mean。

 do you see something about the implications of stuff like CIP and security with respect to then PSTN。

 like wiretapping laws， all those kinds of questions？

 Where do you think this is going or how is it different？ Wow， big question。 Yes。

 I do recall when we were building the RFC or C3261。

 we basically kind of drew straws for who's going to do what parts。

 I got to write the book overview of how CIP operated。

 the orbital one paragraph statement I got to do， addressing， I got to do， user-age behavior。

 And then I drew the straw to do security。 Nothing。 Okay， I have a bit of a security background。

 This shouldn't be too difficult。 And the initial plan。

 one section on security and CIP actually ended up being four chapters of the RFC。 And at the time。

 this was the largest RFC I ever published。 CIP did not come out then。

 And CIP security has always been a problem child。 And these revelations obviously have put the IT app and people who develop standards in a very interesting position。

 You know， no less an authority than Bruce Schneider， who I would say。

 is one of the greatest minds thinking about security has formally called on the ITF to drop what it's doing and to refocus all of its efforts and are upcoming。

 meaning to be in Vancouver。 And then we started to think about how we're going to resolve the problems that have been raised by Prism。

 And， you know， we've studied the privacy properties of these protocols。

 the security properties of these protocols very extensively。 And I was convinced now， I think。

 as I ever was， that we made a lot of compromises in the design of CIP security because they were necessary for it to be adopted in the marketplace。

 It would be great to be able to design a protocol that had an end security that can guarantee integrity and confidentiality between one point that's trying to make a call and another endpoint that's trying to make a call。

 And as soon as intermediaries are playing some role in the delivery of that。

 as soon as they need to help you to find the right endpoint。

 And this dynamic capability that CIP has to allow， you know。

 if I wanted to have five devices that would all register under my Sydney， my desk phone。

 the cell phone， my iPad， various other devices， they only need to register to some server that's that isn't a network somewhere that's going to be responsible for routing traffic to it。

 And in which that server has access to signaling， has access to who's calling me。 You know。

 what are the media streams that are going to be set up and what are the IP endpoints that media is going to be sent between。

 We could have done more to protect that design CIP。 And I think if we had。

 we wouldn't be talking about CIP right now because it wouldn't have succeeded enough for it to even be noteworthy。

 Also， what are some can talk a little bit about？ So， might。

 it might be a protocol that most people don't realize that they're using or where it's being used。

 You want to talk a little bit about where it's been successful and where it's been really adopted。

 Sure。 So， I mentioned Skype。 If you do Skype in or Skype out。

 typically that is Skype's internal protocol is converted for。

 it converted into CIP for transfer to a gateway which would then go to the telephone network。

 Basically， if you use a voice-by-piece service or a landline in your house that comes from either a file or a cable provider。

 that's surely sent that is being used in the background。 The third generation cell phones。

 things that are 3G PPGakes all use CIP signaling inside them。 Now， I mean， these networks。

 especially when we talk about mobile phones and about the networks we see and the cable NSOs and so on。

 they use a version of CIP that is relatively architecturally similar to the telephone network。

 They've got to apply the protocol machinery of CIP to generate a system that has many of the same properties that the telephone network has。

 And this too is， it's a fundamental trade-off， the design of these things。

 I would love to say a CIP that was much less dependent on the network elements shaping traffic and deciding how they do as much more driven by the endpoints。

 This is just kind of fundamental and then principle of the internet that you want to have the smarts beyond the endpoints。

 You don't want to have an intermediary in the middle of need to understand what endpoints want to do。

 It shouldn't get in their way。 It shouldn't prevent them from negotiating。

 If I may have a great new codec tomorrow and I have a copy of it and you have a copy of it。

 it sits on our two machines， I don't want that thing in the middle of the network to have to know anything about that codec to let us connect and to use it。

 The realities though of how these things actually get implemented。

 especially when you're doing something as complex as replacing the telephone network。

 or placing a more than a century old system with its reliability constraints。

 with its emergency services implications， the ability to call 911。

 Just getting the basic services people associate with us right， it requires you to make compromises。

 I can't say I'm always proud and retrospective to compromise as we needed to make in order for this to be successful。

 but I do acknowledge and retrospect that if we have pushed back on some of those compromises。

 it certainly would have led to the fact of the protocol。 As people who design standards。

 this is a heartbreaking thing that you come up against again and again。 Now。

 we can be smarter about this。 I think if there's a silver lining to these increasingly disturbing revelations that are coming up about widespread state surveillance of the Internet。

 it may create a political will to see a change in what we can get consensus for。

 and hopefully in what people will be willing to deploy。 I believe when you go to the ITX。

 since it is consensus-based， there are things we can get consensus to do。

 that I think would be very radical at this point because the people who go to the ITX are still well informed。

 they're so energized， they're so interested in individual liberties。

 I would hate to see the ITX though become an organization that is developing standards that never see the light of day。

 because it is swung too far in this direction。 It's very difficult for us to understand what the right course is for us to chart at this point。

 Interesting。 I would like to wind back a little bit。

 Were you mentioned about how building the first soft switch or devices and all the logic was in the general computer？

 At that point， it was pretty hard in the sun box。 Do you see a parallel between that and software to find that we're looking today。

 where we see that transition may be happening in the internet？

 Are there all some of them that occur behind SDM？ I certainly see many parallels there。

 I'm not sure those parallels will play out in exactly the same way because the companies like Cisco and Juniper。

 that would stand to be disrupted by this， the way that say your channel and you sent were in the 90s。

 they are more agile companies。 They are companies that are taking these technologies and trying to figure out a middle path。

 I guess。 For example， there is the I2RS， the interface to the routing system。

 standard proposal circulating in the ITF。 Now， it's a bit different than the very low layer software to find that approach that we see saying in the Open Network Foundation。

 but it's nonetheless a way that software can interact with the FIB and help higher level routing decisions get made。

 I think the routing vendors view this as one tool among many that will help decide how packets are going to be forwarded。

 They are figuring out ways in other words to subsume this that will allow their device to take advantage of the strengths of this。

 without necessarily eroding the market control and the lengthy install base they have。

 maintenance tools and so on that have proven so successful through the internet in the past。

 I don't know that core routers have to the degree that old telephones which was did。

 impeded innovation in the network as well。 That was another real driver for doing soft switching was that these traditional telephones switches。

 were so model that they had no program ability。 There were no realistic interfaces that you could use to alter their behavior without doing open-heart surgery。

 The situation is very different I think for core routers but the parallels， they do stand。

 I certainly wouldn't dismiss it at hand， and I certainly know people who work for major router vendors who you find them at the bar at the right hour will cry on your shoulder。

 Not exactly， you know， their concerns about this。 It is a real challenge for that business。

 If we were to look at all the different pieces of work。

 how many working groups are in the AETF today？ Off the top of my head I'm not sure I could say。

 Or the order 100。 Also if you were to think what's the sort of suggest to somebody， "Hey。

 this is maybe something you should keep your eye on。

 is what I think is some of the most interesting work going on in the internet。

 It is currently in progress and might really significantly change what the networks like in three or three years。

 Where would you suggest looking？ Actually that I2 RS group would be a very significant one that I put into you right now。

 There is a new effort that's just been spun up。 It's unclear if it's going to be a working group or not。

 It's called Perpass which is the IETF forum for discussing PRISM。

 If we're discussing how these security things can be addressed。

 there are already some proposals that are circulating there。

 that are really about structural changes to how the IETF process would work。

 For should standards have to be the new bar basically in order to。

 obviate the very real concerns that are increasingly coming to light about all of this。

 If you were coming to Vancouver this time， these are two things I certainly come to。

 There are things I personally happen to be working on。

 I think they're very interesting and impactful。 You know might not essentially exactly that level but I continue to be very interested in CDNs and the degree of internet traffic。

 that is now being directed by content distribution networks。

 We're doing a lot of work today on interfaces for understanding how CDNs can express their coverage areas。

 and how CDNs can advertise services that they provide in order to allow collaboration or peering houses among CDNs。

 to make more optimal selections of CDNs。 I think this will have potentially a tremendous impact on the efficiency of internet traffic or alleviate some of the bottlenecks。

 that people protect that's more and more video moves on to the internet。

 That's a personal pet project of mine。 I am also still working on some things related to the intersection of the telephone network and the internet。

 One thing that's been I think a major issue in robocalling has become an increasing problem as the internet。

 and the telephone network have become more interconnected。

 Right now I'm looking at ways that perhaps we can do better identity services。

 It's harder to spoof calls。 It's easier to find out who's responsible for a telephone call coming off the internet。

 before it hits the PSKN。 As the numbers for this are just going up and up and up。

 The FTC and the FCC are profoundly interested in finding a solution for this。

 This is what is being discussed in congressional subcommittees already as it's going on in the ITF。

 That's a good place for I think we can really make a difference。

 It's something that is hurting consumers and we'll be a big deal going forward。

 If we stop receiving robocalls then we have you to thank。 Great。 Thanks for coming back。

 Thanks for your time。 No much pleasure。 Thank you。

