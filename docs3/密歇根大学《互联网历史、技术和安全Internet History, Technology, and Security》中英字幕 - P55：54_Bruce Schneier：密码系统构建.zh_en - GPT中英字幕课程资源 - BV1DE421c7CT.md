# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P55：54_Bruce Schneier：密码系统构建.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

Yeah。🎼，🎼你是。🎼Okay。🎼好。🎼宝宝。One of the things we've learned from the Snowden documents is that cryptography broadly applied gives the NSA trouble at least at scale。

So the NSA does a lot of crypt analysis and they break a lot of systems， but well designed。

 well inent cryptography does stymie them。And it's important to understand how it does。

Because if the NSA wanted to be in my computer， they'd be in my computer， done period。

 no question about it。They would hack into my computer and they have a lot of tools to do that。

 If they are not in my computer， one of two things are true one。It's against the law。

 and the NSA is following the law。And two。I'm not high enough on their priorities list。

Now what cryptography does is it forces the attacker， whether the NSA。

 the Chinese government or cybercminals or whoever。To have a priorities list。

And depending on their budget， they'll go down the priorities list and the hope is。

You're not there right， you are below their budget line。Without cryptography。

An organization like the NSA。Can bulk collect data on everybody？With cryptography。

 they are forced to target。And that's extraordinarily valuable。

Because it means the FBI will go after the criminals and the NSA will go after the agents of a foreign power。

 the Chinese government will go after the US government officials that rise to whatever level they want to spy on。

 the cyber criminalmins will just go after a few of us and the rest of us are protected。

That makes cryptography a very important tool。Now， cryptography doesn't actually provide any security。

Because cryptography is mathematics， when we say we trust the cryptography。

 or we're saying is we trust the mathematics。And I think there's a lot of reason to say that I trust the mathematics。

 Everything I know about cryptography tells me the mathematics is good。

Certainly there will be cryptographic advances， certainly some things will be broken in the future。

 but by and large the math works。But math has no agency。 Math can't do anything。

 It's equations on a piece of paper in order for math to do something。

So I'm going has to take that math。And write code。And embed that code in a program。

And embed that program in some bigger system and put that bigger system on a computer with an operating system。

 on a network with a user and all of those things add insecurity。when the NSA breaks cryptography。

 by and large， they don't break the mathematics， they break something else。

 they break the implementation， they break the software， they break the network。

 they break the hardware the software is running on， and they do something somewhere else。

And again and again， we learn this lesson， the math works。But putting stuff around it is much harder。

Now there's an important corollary here。That complexity is the worst enemy of security。

What these things do is they add complexity， the more complex you make your system。

The less secure it's going to be because the more vulnerabilities you'll have。

The more mistakes you'll make somewhere in that system。And we learn again and again when we see。

Anaes of voting systems embedded systems， your cell phone messaging systems。

 email systems that it's always something around the crypto， something that。The designers。

 the implementers， the coders， the users got wrong。

And the simpler we can make systems the more secure they are。So what NISist is doing。

Is they're trying to build standards around as much as possible？

And so they have a standard for a crypto algorithm AES is the standard crypto algorithm。

 it was a public process where multiple groups submitted algorithms and the community as a whole。

Pick a winner。it wasn't dictated on high， there weren't secret criteria。

 the AES algorithm was the one that most of us thought should be AES。

 actually there were several we thought were good candidates， they picked one。

 but there's a lot of trust in the process because there's a very public open international process。

 right Shah3， the new secure hash standard， the same sort of process。

Now it's really fun as a cryptographer being involved in this process， I mean。

 I think of it as a great crypto demolition Drby， we all put our algorithms in the ring。

 beat each other up the one left standing wins， it was kind of like that， you know。

 we would all publish papers analyzing each other。And one of the ones left standing one。

But you that's just just a small part of what NIST does， they have standards ran another generation。

 they have standards for key agreement， for different protocols。

 I mean trying to standardize these components。So the implementers make fewer mistakes。

But still is a lot that you can't standardize。And those bigger pieces where you're going to still find most of your vulnerabilities。

 I believe that's where the NSA finds most of its vulnerabilities。

That it's out there recently we learned about vulnerabilities in the key agreement protocols that are used to secure a lot of the VPNs and Internet connections right and if you look at where that vulnerability was。

 it's because of a shortcut that was made and copy that allowed for a massive precomputation。

 the math work great if you want to make a standard worse。

 you make it super complex and you're just building in vectors at that point and this is why the normal IETF process for internet standards doesn't really work for security because those standards are。

Comproviss right let's put in all the options to make everyone happy。

 let's put in as much flexibility as necessary to make the system as comprehensive as possible that is sort of anti psy care security security needs as few options as possible。

As simple as possible， you don't want compromise， you want one group to win。Because that group。

Has a self contained vision when you have a piece of this and a piece of that and a piece of that。

 there's going to be some interaction you didn't notice and that interaction will be the interaction that breaks your system。

You didn't win AES， right， you were in it， you were in the demolition Derby with your helmet on。

 tell me a little bit about what it's like to be in the demolition Drby toward the end and what it's like to sort of not win the demolition deerby。

So AES was an interesting process to started out with 64 algorithms。

 which 56 met the submission criteria。Then NISist whittled it down to I think it was 15 or 16。

And then a next round whittled it down to five and then chose one。

 so it's a constant winnowing process。And two fish， which was my submission。

 made it all the way into the top five。And those top five were all good algorithms。

 I mean there was no bad algorithms there and the arguments were more about security margin and implementability in hardware versus embedded systems versus。

Constrained systems， 8 bit， 32 bit so we were making。

Distinctions about how we thought it would be used。And to me， it came down to。

 I think three algorithms that I thought these were all good choices。Two fish was one， Ringdal。

 the eventual wind was one， and actually at this point I forget what the third is。And。

What I said on my blog at the time is， any of these three are good。

And sure U been great to have been the winner， but there really know something there's a lot of value in this picking a non US algorithm。

By picking an algorithm from Belgium。It said to the world that NIST is picking what they thought was the best and not trying to pick American。

So。That was an important consideration I hadn't thought of at the time。

So I can't fault in this process at all， it been great to win。

 it actually was really fun to participate and I would do it again and I participated in the Shah three。

Competition， which again was picked by someone else won， my entry was called Scain。And， you know。

 these are lots of fun for cryptography results for students because they give students a whole bunch of targets。

One of the hard things if you're a crypto student is you have to break stuff。

 the only way you learn how to make things is by breaking things， it's back to that security mindset。

 anybody can create a security system that he can't break。

So if you show up with the security system and say I can't break this， my first question is。

 well who are you， why should I trust your attestation that you can't break it as something that's meaningful。

 what else have you broken？And these competitions give。A whole bunch of targets。

 so students can start breaking things that haven't been broken before， get papers out of it。

 get publications， get cred。In the field as someone who can break stuff and therefore as someone who can design stuff。

 it's a source of new problems， it's a source of new targets， but this is what I said to start。

 security is inherently adversarial。And that adversarial nature makes it different。

Unlike any other field in computer science， you go to a security conference， a crypto conference。

 and there are going to be papers of people who break each other's stuff。

And you have to get a thick skin， you have to understand that we are all learning， you know。

 if I produce a protocol and you break it， sure I'm unhappy。

 but I've learned something and so of you and so is everyone else。

And that knowledge is more important than my particular creation。Surviving。

And you have to understand that and accept that， and that has to excite you。🎼。🎼Yeah。

