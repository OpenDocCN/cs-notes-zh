# 卡耐基梅隆大学 14-740 计算机网络 Fundamentals of Computer Networks（Fall 2020） - P17：Lecture 17 Plug-N-Play Networking; IPv6 - ___main___ - BV1wT4y1A7cd

 This is 14。740。

![](img/8f7ea6b6d1fa4dba8813add677ced6f3_1.png)

 Today we're going to finish up with the material in the network layer。 Almost。

 We have a couple more topics to come after the quiz that will sort of relate to network level stuff。

 Today is a data to do all the stuff we haven't done so far。 I call this the "Pokari lesson"。

 We just have a bucket of a couple of topics that go to get， well， they sort of go together。

 but frankly they're more in the same lecture because it's what's left to do。



![](img/8f7ea6b6d1fa4dba8813add677ced6f3_3.png)

![](img/8f7ea6b6d1fa4dba8813add677ced6f3_4.png)

 We're going to basically cover three big topics。 Two of them are useful for making the network plug and play。

 which has made it something more useful for all of humanity than otherwise。 Before we get into that。

 a couple of administrative notes。 Hopefully by now you know that there's a quiz coming up next week。

 So next Tuesday， the masses who are in economy do not need to show up here。

 Be in some place comfortable。 We'll do a quiz just like we did last time。 If you're in a canvas。

 you'll have 75 minutes to do the quiz。 It will be closed book， closed notes。

 And I wrote the first quiz。 I'm going to write the second quiz。 Better get on that。

 Probably the style of questions is going to be kind of similar to what you saw last time。

 I wouldn't expect any great differences in what's coming up。

 I urge you to take a look at the lesson objectives。 Those are。

 I think I posted the second set on to the website。 If not， I will get them there。

 But they're the lesson objectives that are in the slides at the end of each lesson。

 And those are telling you what I'm going to ask you on the quiz。 But I literally。

 when I sit down to write the quiz， I pick some of those lesson objectives， almost at random。

 not quite。 And then I just say， oh， you know， the lesson objectives say that the student should be able to do X。

 Let me write a question that tests whether they can do X。 Okay。

 so I'm not going to try to trick you by pulling in other information or things like that。

 They will be driven by those lesson objectives。 So， please take a look at this。

 Please let those guide your study habits。 There will also be a review session this weekend。

 There's a post on Piazza with the exact details of where to go and what times。

 So please allow that to help you with your study methods as well。 And of course。

 if you have other questions， we have some office hours between now and then。

 or we send the questions to Piazza will be glad to answer them。 You need to talk to us。

 send us an email， we can set up an appointment to do that as well。

 So whatever you need to help you out with your your preparations。

 please do it and let us help if you need help with us。 I also want to point out。

 keep an eye on the class schedule。 It's right after the quiz。

 There are a couple of paper views coming in。 We haven't done paper views for a while。

 a couple weeks。 And so， you know， just notice that they are there so that you don't forget to turn those in。

 And also I just posted homework to homework to is it's due in a month。 So， you know。

 no big panic right now。 However， it is a。 It's not a huge thing but you're doing some。

 you're using some software tools to examine a large data set。

 And it's not the sort of thing you can crank out super much at the last minute so it would help to set aside some time soon。

 And so， you know， it's not a big thing。 So， you know， it's not a big thing。 So， you know。

 it's not a big thing。 So， you know， it's not a big thing。 So， you know， it's not a big thing。 So。

 you know， it's not a big thing。 So， you know， it's not a big thing。

 It's just what 11 characters on a stream。 But these actually think are much more important than that。

 These are some of the technologies that have made the network really useful to ordinary people so that they don't have to。

 for instance， don't have to know what your IP address is。 And， you know。

 and just becomes more plug and play-ish because of that。 So， these are， I think。

 important protocols， important technologies to understand。 And so， we'll bundle them all up。

 Three technologies for today。 The first is DHCP。 You can tell because it ends in a P that it must be some protocol。

 And it is。 This is the dynamic host configuration protocol。

 If you are much of a computer geek at all， you probably have seen those letters together somewhere。

 You've heard that there is a DHCP server somewhere on your network， things like that。 Today。

 we're going to figure out what all that's about。 The mission of DHCP is to make the process of joining the network a much more easy and natural and automatic process。

 So the idea is that you want to have some bundle of configuration data that is necessary to operate in a particular network。

 And you'd like to get that data to a computer that needs it， that wants to operate in the network。

 So what do I mean by that kind of data？ Well， things like an IP address。

 The IP address is related to the subnet you're joining。

 You can't just have a random IP address and show up that statement， by the way。

 should be obvious to you because now you understand routing。

 And so that means you understand the hierarchical nature of it。

 you understand that the routers have to be able to find your IP address。

 And they do that by looking at the announcements of IP ranges of prefixes。

 And so if you just showed up， you know， if you landed from an international flight and showed up at CMU and open your laptop。

 you can't use the same IP address， because the network wouldn't have any idea of how to get to you。

 And so instead you need to change your IP address to be a local IP address。

 something that is accepted in this particular subnet。 And so DHCP allows you to do that。

 allows you to automatically get an IP address from the network itself。

 It's history starts way back with a protocol called boot P。 This was a protocol that Sun networks。

 They used to be a really big computer company that sold Unix workstations。

 And they were started selling these server lists， I'm sorry， these。

 Displist machines that would be very thin client， you know， you put them around in a network。

 And those guys didn't have a hard drive， so they didn't have a way to save any configuration data through a boot process。

 And so the boot P protocol was born as a way for those workstations。

 the thin client workstations to ask the server， hey， what IP address should I be using。

 It turned out it wasn't broad enough。 It was mostly aimed at that particular scenario。

 and only had a couple of pieces of information that you could transmit over it。

 And there needed to be a more broadly general protocol that would allow for lots more forms of information to be transmitted。

 because there were some other networks that needed to pass around different kinds of data。

 And so DHCP arose to fulfill that need， mostly to allow more than just IP address and server and router information to get around。

 It's worth pointing out we're going to talk about IPV six in a minute。

 the new shiny coming version of IP。 And for that， there is a version of DHCP that will handle the details of an IPV six network and pass those around。

 So how's this work？ You wander into a coffee shop。 Oh， remember those days。

 You wander into some other location and you open your laptop and you're the laptop。

 We can think of it as newly booted。 And maybe you did reboot it。

 It's coming out of hibernation coming out of sleep。 And the laptop looks around and says， hey。

 there's a network here。 I'd like to join it。 Okay。

 let me figure out when we get the information so that I can join。 What is my IP address going to be。

 There's also some other information that they may need。 I mentioned the next top gateway。

 That is a another very important piece of information because that's whenever your laptop sends information。

 It actually has to go through a router somewhere。 And so it needs to know on this particular subnet。

 what router am I connected to。 And so we need to know that piece of information。 There are others。

 Okay， subnet mask tells you basically how big the prefix is for this particular network。

 Finding out what DNS server you should be using。 Remember DNS。

 We had a local DNS server that you would， you would send your query to。

 That's bundled in this as well。 There are information as needed for the network。 There's。

 there are several pages in the RFC of the information that can be transmitted。

 Doesn't all need have to be。 But in some networks， you might need this obscure piece of information。

 And so DHC allows you to get it。 So the process this newly booted computer follows is it basically broadcasts a request。

 Remember， it doesn't know anything。 So it can't know which server to contact to ask for this information。

 Right。 Because how would it have known which server that is。

 So it's going to send out a request to everybody。 And most of the participants on the network will ignore it。

 But anybody who is a DHC server can go ahead and respond to that。

 And so the newly booted client will send out this request basically shouting， Hey。

 anybody know what IP address I should use。 And then some server somewhere will send an answer。 Okay。

 And maybe several in fact。 The server itself， the one who is answering these is responsible for ensuring that this data is transmitted properly that it has the right numbers to deal with for all these pieces of information。

 And then it does things like manage the IP addresses。 So a lot of the information doesn't matter。

 Everybody in the network should know what the next gate， the next step gateway is。 Right。

 Everybody should know what our subnet mask is。 But every participant in the network needs a different IP address。

 And so that's the server's job is to have a bundle of IP addresses and to pass them out and make sure that we don't have the same IP address being used by multiple computers in the network。

 The， it is possible to set up several DHC servers in a network that's typically done for redundancy sake。

 You'll have one like main DHC server and just in case that one crashes。

 You want to have another one also around。 Okay。 They both can answer queries。

 And we'll see how a client might decide which one to use or how to guide that as well。

 In a few minutes。 It's also possible to have a single DHC server managing multiple subnets。 So。

 I want to take a quick aside。 We're going to use the word subnet a lot today。

 And I just want to make sure you understand what we mean by that term subnet。 A subnet is a， well。

 it's a piece of a network， right。 It's a sub component of a network。 So it is a network。

 But it's a network without routers in it。 Or well， technically there's one router。 The subnet。

 maybe two。 The subnet is the， the， all of the network pieces kind of between routers。 Okay。

 You don't have any places where a subnet has a bunch of connections off of a router and then that same router has a bunch of connections off another like。

 Okay。 So for instance， we sometimes say that a subnet is a local area network。 Not entirely true。

 but that's the same idea。 Right。 You'll have a network that covers maybe。

 maybe here Carnegie Mellon。 There is a subnet that covers this building。 Okay。

 Now it's a piece of the overall network。 And that means that the administrators have a router somewhere。

 And there's one wire out of that router that comes to the machines here in the subnet。

 And that means all of the computers in the subnet are managed similarly。 For instance。

 they all have to have the same prefix。 Okay， they all have to have the same range of IP addresses。

 so that that router knows how to send packets into this， the subnet properly。 Okay， they all。

 you know， use the same router next step。 That is the router that they're going to get ahead to when they send messages out。

 Okay， so it is a， we're going to talk more about them when we get to the data link layer another way to look at it。

 It is a segment of a data link that is able to communicate to between servers or to a server between。

 sorry to a router or between routers。 Okay， so the subnet thing， right， we're going to。

 it is possible for administrative reasons to allow one DCP server to cover multiple subnets。

 So you don't have to necessarily， if you're building CMU's network。

 I don't have to put a different DCP server in every building or every subnet。

 whatever power they've decided to partition the network。 You could have one router somewhere。

 or I'm sorry one DCP server somewhere， and messages from a subnet can get routed through the router to that particular DCP server。

 if it's set up properly。 All right， so the DCP server is mostly a database of a bunch of data。

 right， you want to be on this network here's a bunch of data you need。

 and an allocation process for individual IP addresses。

 Now that allocation process for the IP addresses can happen in a couple of ways。

 The dynamic allocation is by far the most common。 The idea is that you have the server has a pool of addresses。

 and it will assign an IP address to a particular client to a particular host in the subnet。

 But it's only for a particular amount of time。 And the expectation is that that host will eventually wander away。

 right， think coffee shop， or think you economy auditorium， right， that host will eventually move on。

 And we'll want to recapture that IP address and give it to some other host at some future time。

 And so it's a reuse mechanism for some pool of IP addresses。

 Some of the IP addresses can be assigned automatically。 Basically。

 the server is set up so that when Dean Yahn's computer shows up in the network Dean Yahn always is told this is the IP address you should use。

 And this is a holdover from not so much needed these days。

 but it's a holdover from the 90s when IP addresses actually were used as an anti software piracy mechanism。

 And you would have software that was registered to a particular IP address。

 And so it would be important if you went into this network that you always get the same IP address so that you can use the software you you've registered using that。

 It's also possible for that process to be manual， right。

 the sys admins basically say this IP address goes to this particular client。

 Maybe because you may again， maybe for software registration purposes or some others。

 So it's dynamic so the top one up there the dynamic allocation is the most common use I said。

 the way that that works is there's a leasing mechanism。

 When the server hands an IP address to a particular client。

 They also specify a time limit for it they're basically leasing that IP address to that client。

 The reason is， before people leave the coffee shop they tend not to notify the network they're going to do it right they just shut shut their laptop and leave。

 or maybe， even if they intended to maybe they're laptop crashes。

 And it doesn't have time to tell the DHCP server， hey， I'm done with this IP address。

 you can loan it to someone else。 And so this leasing mechanism is an IP recapture mechanism。

 It's a way of having the server pass out an IP address to a particular client。

 And then that client can use that IP address， but only for some given amount of time。 Hey。

 you're allowed to use this for the next 30 minutes。 Okay， and if you after that time period。

 we're going to assume that the server is going to assume that the server can use that IP address again to give it to somebody else。

 And as possible for a client to say， hey， I'm going to be hanging out here in the coffee shop longer。

 And so at the 30 minute point， instead of just losing their IP address。

 they can respond back to the server and say， hey， I'd like to renew that lease。

 Could have it for another 30 minutes。 Okay， and of course the servers couldn't tell them that's okay。

 It doesn't make sense。 Basically just a simple timing mechanism to allow for the recapture of the these IP addresses。

 Now we haven't talked about the most interesting part I think of。 Well。

 it's a bootstrapping process right you come into a network。 And you'd like to get an IP address。

 And that IP address will allow you to send messages in the network。 But to get that IP address。

 you have to somehow send the message。 Right， you can't。 Well， you've got to you。 Well。

 what do you do， right？ How do you send a message the IP packet you know you've seen the header the IP packet requires that there be a source IP address in there。

 Okay， and also we don't know who to send it to。 Okay。

 so how do we go about coming into a network completely blind not knowing any information and be able to send information to a server to request the data that will allow you to send messages。

 Okay， and Stefanos has half of the answer correct。 The answer is we're going to broadcast it。

 There is a IP broadcast mechanism that lets you specify a broadcast IP address。 Oh， that's all ones。

 We talked about this briefly when we talked about IP addresses we said it's not a real broadcast。

 It doesn't go to everybody in the network， which is good because otherwise your computer would be getting messages from everybody in the world。

 Okay， instead this will go to everybody in the subnet。 So it's a subnet layer broadcast。

 a router who gets a packet for 255 to 5255 to 255 knows that it's a broadcast and the router will not send it on。

 Okay， it'll go to the router and then stop there。 The message itself it's DCP uses UDP as for its segment formatting。

 And it goes ahead and sends in its own DCP protocol it sends this message out to basically the world。

 And of course then we hope to get responses from servers。

 We hope to get a response from one or more servers it is possible to get many。

 Now the message itself， the actual protocol we're using the thing that's being put into the UDP segment data has is a DCP message。

 And it has a bunch of fields we're not going to talk about specifically how those are constructed instead we're going to just say it has this kind of information it needs to transmit。

 Right， it needs to well tell you what kind of message it's sending what is this thing。

 What is the type of this message。 And we have， we'll see some of these discover offer。 Right。

 so a client will send a discover message servers will respond with offer messages。

 There's a request and an acknowledgement。 And there is a release mechanism if you are leaving the coffee shop and are going to be nice person you can give up your IP address with that release message。

 There's a field for a transaction value。 We've seen this over and over again right。

 We're going to send out a request we're going to hear responses。 We got to make sure those line up。

 Okay， and so we're going to basically fill in a random value。

 And we hope that nobody else in the network just sent a message with that same random value。

 We have a field for some identifier value something that will say this is my laptop。

 This is who we're talking about。 Okay， and that often is just something like an internet Mac address or something that we think is is unique to us。

 It can be in a managed network it can be some opaque key something that says this is who I am。

 Or this is one of a bundle and this is bills laptop or bills backup laptop or something like that。

 It doesn't have to be a Mac address， which is good because in technicality we may not be sending this over Ethernet we may not have a Mac address。

 We were using some other data link technology。 Now there's a field for a server's IP address。

 That's who we're going to talk to。 And that lets us identify in a request which server it's coming from in a case where there may be multiples。

 There is also the your address。 Sometimes think you know maybe that should be in that address for Pittsburgh。

 This is the address we're talking about from the client。

 This is the one that we're asking for permission to use。

 This is the one that a server is responding to us and saying hey here's one you can use。

 And then tons of other data about that goes in the options。

 So if I was to put together a sequence diagram。 Oh， look。

 I have put together sequence diagram describing what happens here。

 It looks like the sequence diagrams we've seen before right it's going down the page messages being sent back and forth。

 I have three participants here， which is a little unusual。

 I'm showing a scenario where I have a client。 This is the computer that needs an IP address that's just shown up。

 And in this case we actually have two servers。 Okay， just to illustrate that it's possible。

 This isn't going to always happen exactly this way。 But if there were multiple servers。

 this is what would happen。 You'll also notice I'm trying to illustrate that these messages are broadcast messages。

 Right in most of the sequence diagrams we've seen so far。 Actually， I think probably all of them。

 The message is going from somebody to somebody。 And so there was an arrow on that saying I'm sending this message to that particular client。

 In this case we're not doing that these are broadcast things。 Right。

 so there's no real directionality about it。 And I tried to show that at the beginning with a bunch of arrows going out all over the place。

 That gets a little tiresome for the whole diagram。 So instead。

 I put these little chicken feet things on the end of the arrows。 Oh， they're not arrows anymore。

 Right。 They're broadcast messages。 And so there's no arrow head tip instead this chicken feet is supposed to indicate it's built。

 It's actually a broadcast message going everywhere。 Okay。

 So now that we have the ground rules of my picture down。 Let's see how this works。 Right。

 We have got a client that shows up and sends out a discover message。 Okay。

 So this is a D HCP message。 It's in a UDP segment。 It's sent in an IP broadcast packet。

 And the contents of that thing are well here's a source address。 I don't know who I am。

 So I'm going to put zeros in that field。 Got some some port number。 Here's the destination。

 It's a broadcast IP packet。 So the destination address is all ones。

 It's going to port 67 because that's the D HCP port。 In the D HCP。

 Message in the your address field。 I've got all zeros because I don't know who I am yet。

 And we've got some random transaction value。 Right。 So we randomly just decided， Oh。

 this is this request I'm making is 1987。 That goes out everywhere。

 Anybody else on the on the subnet's going to ignore it。 But we have two T HCP servers on the subnet。

 So they will respond。 And they get this message and they go ahead and send back D HCP offer messages。

 These offer messages。 Oh， you'll notice still broadcast。 Right。

 Why can't know we that server would know who they're talking to。 Right。

 Why can't they send a message that's not broadcast。 Well。

 because that client doesn't know it's IP address yet。 So you。

 you can't send something somebody who doesn't have an IP address。

 Another way of looking at this is that client doesn't know what IP addresses it should be looking for。

 So if it sees IP packets go back and forth， it needs to be able to pick them out and say， Oh。

 this one's for me。 Right。 And so it doesn't know that。 So these have to be broadcast as well。

 They are coming from a machine that knows it's IP address。 So you'll notice they have IP addresses。

 The destination IP is broadcast as I mentioned。 Each of them is offering up an address right 128 to 130 up 48。

 Is an off is basically the server saying， here's an IP address you could use。 Okay， here's。

 here's what I'm suggesting。 And you'll notice those are probably in the same subnet a lot of bits that front of those two addresses are the same。

 These DCP servers have been coordinated to work in the same subnet。

 The transaction ID matches the transaction ID of the， the discover message。

 That's so that the client knows， Oh， this one's for me。 Right。 Remember。

 this could be happening with multiple clients at the same time requesting messages。 Okay。

 So we got to make sure that those， those answers go to the right request。 Let's see。

 we've got a field for the server address we're sending。 That's that's in the DCP message。

 you might look at that and say， wait a minute， that's already in the packet。 And that's true。

 But the information in the packets going to get stripped out at the network layer。

 The packet segments going to get handed to UDP UDP is going to pull the DCP message out and and hand it to the。

 To the DCP application。 And so that application is going to be able to look at that this server information address field to know who to talk to in the future。

 And one of the options is the lifetime。 Right。 So they're saying。

 here's an IP address you can use for 3600 seconds or 420 seconds。 Okay。

 Don't know why these numbers happen to be there。 That's this assistant administrator who set it up。

 That's why probably looks to me like this is a main server and a backup server。 Right。

 And so you're supposed to take the request from the middle server。 But if that guy's crashed。

 then this other guy is going to give you something you can use for a little bit to to limp along until that guy rebuilds。

 The client then has two offers， looks at them， makes a decision。

 It can decide whichever wants to ask for。 Okay， it probably is going to ask for the one that has a longer lifetime。

 And so it will go ahead and send a request now。 Okay。 It's request。 So the first one is saying， Hey。

 I'd like to know what IP addresses I could use。 And it got two responses。

 Now with this request message， it's saying this is the one I'd like to use。 Is that okay。 Again。

 it's a broadcast message because we technically don't have permission to use that yet。 Okay。

 so we're saying， Hey， this is the one I want to use。

 It's still in an IP packet that has a zero for the source address because we don't know where they were allowed to use it or not。

 It's broadcast。 It's talking about this IP address we want the dot 48 one。

 Look at different transaction ID。 This is a different request。

 So we randomly generate some different number for that。 This transaction ID is 42。

 I'm going to send it to that particular server。 You know。

 this is the lifetime of the thing you've you've said。

 And that server responds with an acknowledgement says， yes。

 That thing you discovered is still available。 And I'm going to go ahead and allocate it to you。

 I'm going to go ahead and let you use it。 So I'm going to send back an act。

 act message for that particular address。 It has the same transaction ID so that the client knows which one can match that up to the request。

 And here the details here's the 3600 seconds， at least that that that the IP address has。

 It kind of makes sense。 Question。 So you said that the service can serve multiple subnets。 Correct。

 So let's say my computer is on one subnet and does a broad hash network and then the service not directly in that subnet。

 Correct。 Does and that sounds like the broadcast wouldn't get to them。 Yeah， I'm sorry。

 The router then。 Oh， let's finish。 See it。 Okay。 This is D H C P。

 I know how to route it directly to the D H C P server。 Yeah。 So for zoom people。

 the question is about my statement earlier that a D H C P server could serve multiple broad subnets。

 which implies that that server would not be on the local subnet。 Okay。

 so these requests were sending out your broadcasting them。

 But we're broadcasting them trying to get to a server that's not on my subnet。 Okay。

 And that conflicts with the statement I said a minute ago about how a broadcast only covers the subnet you're in。

 Okay。 So yes， if you have a situation like that， then the sys admins need to know that and they would have configured the router to know and to be looking for a broadcast。

 That is a D H C P message and would know to forward it on somewhere else。

 So that would be a special case that the administrators would have to set up to make it work。 Yeah。

 for that problem。 I'm sorry， the missing zoom questions。 Okay。



![](img/8f7ea6b6d1fa4dba8813add677ced6f3_6.png)

 This is once again， we have a protocol that grew up kind of in the good old days。

 And there's not a huge amount of security on it。 And in some cases it's hard to figure out how you would get security。

 Okay。 How do you get an encryption key to a client who doesn't know who they're allowed to talk to。

 Right。 It's a， it's a tough security question to ask。

 And that means that we have problems that couldn't show up right it's possible to run a server。

 Right。 You know， D C P is an open protocol。 You could run a server on your laptop right now in this in this situation。

 And when I show up and open my laptop。 And send out a D H C P discover you could answer。 Okay。

 In managed network situations。 That's one of the ways that those opaque keys are used is to be able to communicate a little bit more information。

 but that has to be something that's set up ahead of time。

 So that your laptop knows to send that and what not。 It's also possible to be a， you know。

 there's nothing in here that authorizes or checks that a client machine is allowed to be on the network。

 Okay。 And so that does mean， for instance， if you wanted to， you could。

 you could go ahead and keep sending requests and collecting IP addresses。 Okay。 And you just， you。

 you probably want to change the hardware address field of the requests。

 but you could pretend to be 30 different laptops and take all the D H C P。

 Use D H C P to take all of the D H C P allocated IP addresses for coffee shop and then you get to use it。

 Nobody else does。 If you wanted to。 Here's what I think I think D H C P is fantastic。

 It is one of these technologies that is made the network so much easier to use。

 You guys have grown up with this network where you do just walk in a coffee shop and open your laptop。

 Okay。 There was a time before you were born where if you wanted to be part of a network。

 you needed to have the information given to you。 Right。 Many times back in the 90s。

 I'd moved to a new house。 I'd get， you know， call it my ISP。

 They'd have to send some guy around to my house to install the network， the internet into my house。

 And in some cases， they would say， well， here's us， you know。

 here's some software on the CD you have to run this to get set up to the network。 Right。

 Or at the very least， here's the index card that has your IP address and the guy would type it into your computer。

 Or you'd have to know how to get to the right screens administratively to do that。

 And many users are not going to be。 I don't want to say capable of that。

 but not going to want to or know how to go through those hoops to set up the network。

 And so D H C P is really open that up a lot， which is fantastic。

 Second plug and play technology that's really helped from the network level and that's not network address translation。

 So network address translation。 Also works on the problem of how to manage that P addresses that we're given。

 It does it in a slightly different way。 And it's one where we're using that as a mechanism to present to the network to the public side of the network。

 a single IP address。 But to have multiple devices that can respond to that。 Okay。

 so think of your apartment or， you know， my house。

 I've got 60 or 70 different devices in my house that all are。 Want to send network messages。

 That means they all need to have a unique IP address。 Okay。

 but instead of taking 60 or 70 of the available IP addresses and making those globally unique。

 Instead， my house is behind a network address translation device。

 And so the rest of the world thinks that my house has a single device in it。

 And that is just that net device。 Okay。 This is sometimes called spoofing or masquerading。

 Because we are doing something a little bit differently， right。

 where the IP address is supposed to identify the destination。

 As a globally unique destination for an IP packet。 And now we're kind of changing that。

 We're saying this device is going to be。 The whole， you know， the destination for that IP address。

 but then it's going to go ahead and translate that into the actual IP address to send it to the actual device。

 On the private side of that network address translation device。 Kind of a address mapping mechanism。

 All right， so why do you love this？ Well， some people do some people don't。

 One of the things that it is really done for us。 It has helped to handle the exhaustion of IP addresses。

 You know that IP addresses are 32 bits long。 Which two to the 32nd to 30 seconds about 4 billion。

 Right。 How many devices are there on the Internet today？ You think it's more or less than 4 billion。

 It's way more than 4 billion。 How is that working？ Right。

 How do we get more than 4 billion devices in a network where every device is supposed to have a globally unique IP address。

 Well， not devices or how that happens。 Okay， because we're not using each device doesn't need to have a globally unique IP address。

 Each net device has to have a globally unique IP address instead。 I mean。

 it does allow for some simple address allocation mechanisms。 Right。

 So this is another one of those things that you probably you've grown up in a network where this isn't a big deal because net devices happen a lot。

 But let me tell you again a story from the old days right back in the 90s。

 I remember trying to convince my Internet service provider that I should have a second IP address because I had a second computer in my house。

 And at least the customer service agents had never heard of such a thing。

 Why do people have two computers in their house？ Right。 They thought that was weird。

 And I guess at the time it was。 Okay。 And so they wanted me to buy a business account。 Okay。

 So then I could have a second IP address。 Right。 And it was a big rigamarole and it was a mess。

 Right。 Instead with a network address translation device， my whole house has a single IP address。

 If I want to add a new device to that， I don't have to contact my Internet service provider。 Right。

 And man， the less I have to contact those guys the better。 Right。 I just show up， you know。

 I bought it， you buy a new device。 Hey， I got one of those new brands。 Very fine。 Keep word things。

 No big deal。 Right。 I just bring it into my house。 DHCP gives it a IP address。

 The rest of the world doesn't know about it。 It just is behind my net device。

 I have a single IP address for my whole house。 Fantastic。

 Some people also think that this is a security benefit。 Maybe， right。

 The idea is that you can obscure your whole network behind the network address translation device。

 And so。 The， so an attacker on the outside would not be able to look through my network and find out。

 Oh， you know， is there a vulnerable machine in there we can go looking for。 I put this in quotes。

 I don't think it's that useful a thing。 And many of you taking this course are security people are going to be security people and can recognize that you know that's some security technique that's not great。

 And if I'm going to communicate to the world anyway。

 I'm going to have to indicate something about my presence there as I send those messages。

 So whether or not there's a net device there。 I don't think it should。

 it should not be thought as a real security device。 I don't think。 All right。 So how does this work？

 The IP addresses to inside in the private side of my network。

 I still have to have IP addresses for all these machines。

 Every device inside my house that is going to send an IP packet needs to have an address to do that's got to be able to fill out the field in the IP header。

 And that's so that when messages come back， they can hopefully get the responses。

 So all of the devices on the private side of the network。 Use。

 we call them non routable IP addresses， they use IP addresses from one of these ranges， right。

 I don't know， you know， right now I think， in seeing you were all using the 172 16。 ranges。

 and my house and many places， I've been many hotels and airlines and things like that。

 You'll look at your IP address since 192。168。 That's something。 Okay。 Wait a minute。

 that means when I'm in a hotel， I have a 198， 192， 168 thing but also my house， I have 192。

 168 thing。 Yes， that's true。 So no longer are all of the devices on the internet assigned a globally unique IP address。

 In fact， many of them are going to duplicate。 I'm going to guess that there's several million devices that are 192。

 168。1。1。 Okay。 They're not globally unique。 These are， we call them non routable devices。

 They are non routable addresses。 They are useful within my network。

 but no router should ever take an IP packet that comes into it with 192。

 168 something something and pass it through the router。 So， we're going to stop there。 And that's。

 that's what we mean by non routable。 And that means that there's， you know， why， why is that？ Well。

 if the router was willing to do that， then we would have IP packets out in the middle of the network out in the core of the Internet that have this address。

 So， there's a million machines that we go to， where should it get routed to。 Okay。

 so no router should ever have 192， 168， 00 things in its forwarding table。

 Those should just get dropped。 And that device， I'm calling it a router here， it's going to。

 and I'm doing that because it's often included in the router thing， right。 In my house。

 I do not have a separate box that's a router and a separate box that is a net device and a separate box that's at the HCP server。

 You， you spend a hundred bucks， you get them all in one box。

 That device that's doing the net translation， it shows the outside world a single IP address。

 And then it has to keep track of the translations it's doing。

 And whenever a packet comes from the inside from the private side of the network through this net device destined for the external world。

 That packet has to be rewritten the address in the source field is going to be 192。

 168 something something or one of these other non routable addresses。

 So that net device is going to want to change that it's going to want to say， Oh。

 that number I'm going to use。 Well， I'm going to use the external IP address that the rest of the world knows the network has。

 So it's going to rewrite that。 It has to keep track of where things came from。

 because we're going to send this IP packet out into the world。

 Presumably there's going to be a response that comes back。

 That response will come back to the net device and the net device then needs to go ahead and change the packet and send it into the private network so that it gets to the right place。

 And so it has to somehow keep a track of which devices on the inside got rewritten in which ways so that when these responses come back。

 we can figure it out。 Okay， and so there's this rewriting process that's going to go on。

 And there's some state in this device that has to keep track of how the rewriting is happening。

 That process， the details of the rewriting and the state that are kept around are different in different net devices。

 There's no， no standard that says this is how you do not。 Okay， instead。

 there are several different versions and depending upon the state kept what what that internal table looks like。

 There are going to be different capabilities。 Okay， early versions of that would only allow。

 for instance， certain mechanisms， and would get in trouble if you had， you know。

 several devices on the inside talking to the same server， for instance， or things like that。

 So I'm trying to be a little general about this。 Please don't take my example as the only way this is ever done。

 It's intended as an example to kind of show you how this rewriting process might happen。

 So I have an example here of an internal network。 I've got three hosts on the left side of the picture that are all using privately routable or privately non routable IP addresses。

 right， those 192 168 addresses。 There's a device in the middle， my router symbol。

 that guy's going to do network address translation。 And I have the cloud， right。

 there's this bubble out there that's the internet that we're communicating to and in particular we're communicating with one server。

 So I'm going to show you what happens when somebody inside the network sends a and IP packet to that server at the end over there。

 who then responds。 So， first， let's take a look。 I'm not going to start at step one。

 I'm going to actually start at step two。 What would happen。

 what would you expect to happen if a device talks to a server and gets a response。 Okay。

 that's what step two and three are。 Right， so it's imagine that that that device in the middle wants to communicate with that server。

 Right， and so the device in the middle is going to send an IP packet。 Okay， to that servers。

 IP address right it has a destination of two two one four six sixty because that's that server over there。

 It has a source IP address of it。 Right， one 128 that two zero that 250。 That's it's its own local。

 you know， it's own IP address there on the external side。 So， we're sending it to a particular port。

 So it's sending to port 12，000 one。 I'm sorry， it's sending to port 80。 So web traffic。 Right。

 And it has a source port of 12，000 one。 That's a number that's been chosen on that net device。

 just like you would choose a port whenever you need to send something right you open up some ephemeral port and made that choice。

 So， of course， then response with whatever response it's going to send back。

 And it sends that back in an IP address where these two values are basically reversed right everything that was a destination has become the source and everything that was the source has become the destination。

 And that should surprise you at all right that's normal how we do responses， you know。

 to some web server for instance， right you send it to some port and they send you back。

 So everybody should have that part easy。 So， the， the issue is how do we add on step one and four here。

 Okay， because we don't have that network that the network address translation device doing all of our web traffic right。

 we actually， you know， in my laptop in my house， or on my local network here I want， you know。

 on the inside here on the left。 I want to actually talk to the server not have the net device talk to that server。

 So when I do， I'm going to send out something using my IP address and the destination of where I wanted to go。

 Right， so， so block number one there is IP packet。

 It has the source IP address of the actual internal device。

 And whatever ephemeral port it has chosen。 And it's going out to destination to to to dot whatever come 80 web traffic。

 And by the way， is normal right that's exactly what would happen。 I just， you know。

 everything I send out I send out using my IP address and then ephemeral port。

 I send it to some destination that I've gotten from DNS。 Right。

 and some port number based upon the service I'm asking for。

 Notice that means I don't know that I'm natted at all。

 The internal device just is using its IP address， sending as normal。 Nothing has to change。

 All of my packets that I send from the private network have to go through that router anyway。 Okay。

 that's the first router， you know， out of my subnet。

 And so that router is going to now take my packet and rewrite it to become packet number two。

 So what changes did it have to do？ Well， it had to take out this local address。

 this non-routable 192。168 address。 It has to take that out and it rewrites that with its own address。

 Right， so if you compare number one and number two， right。

 the source IP address has been changed from an internal address to that external。

 worldly visible address。 What else has changed？ The destination has not changed at all。 Right。

 we still want to send it to that server。 So the destination address and port number have to stay the same。

 You'll notice though we've also changed the port number。

 And this is really the key for making general purpose network well。

 That we've changed something from port 1987 to 12，001。 Why？ Well。

 that port number allows the net device to identify the packets that were sent。

 And thus be able to map the packets that come back their responses to know when I get a response。

 So when number three comes back， the net device will look at that port number 12。

001 and look it up in my table to figure out who this one should go to。 Right。

 the net device has a problem because it has multiple possible destinations for any particular packet that it's receiving from the outside world。

 It has to figure out， you know， hey， this packet is number three packet has just arrived。

 Which one of my three computers should this go to？

 It's going to have to rewrite the IP address back。 So it's coming back with the IP address 128。2。0。

250， the external IP address。 It's got to figure out which of my internal guys should that be。

 And so it uses that port number。 It looks up 12，001。

 which it was able to choose and looks up in its table and says， Oh， 12，001。

 That was this row of the table。 Right。 12，001， maybe the combination of 12。

001 and the destination IP address。 Maybe something depends on how the net device is designed and how it's managing its data。

 But that allows it to find a particular row in its internal state table and look up， Oh。

 who should this go to？ That one should go to 192， one， one， that one， two。

 And I know that because I rewrote it on the way out。 So I know how to undo that on the way in。

 Does that make sense？ Understanding this is kind of the key to understanding all of that stuff。

 Question。 So question is kind of okay。 This mechanism we're using by using a port number here。

 That's going to have some limits。 And what are the edges of that。

 I think is probably where you're headed， which is great。

 Depending upon how you handle that and what those numbers mean， you have。

 you may have different edges。 Okay。 So， for instance。

 early devices only did IP address translation didn't think about using port numbers。 Okay。

 And so that meant that。 Well， that meant that there was going to be a one to one of the internal IP address and the destination went to。

 Okay。 And that meant that only one computer on internal could talk to the same external server at the same time。

 which may or may not be a problem。 It's certainly a problem here， right。

 because you all are talking to the zoom server。 And I'm sure we're natted at some point。

 And so it would be inconvenient if we had a net mechanism that wouldn't let anybody on the inside or let multiple clients on the inside talk the same place on the outside。

 Okay。 And so it will depend so the real answer is it depends on exactly what you're using to do that translation。

 Okay。 And it varies and we call them different things depending upon what they are。

 And it's pretty typical nowadays to have something that's， you know。

 on the symmetric side or definitely down the list a little bit such that you have better capabilities。

 you have the way the opportunity to。 You know， for a internal computer to talk to multiple servers on the outside。

 for instance， or for multiples to go or things like that。 There are some issues that net devices。

 These are， you know， if I was engineering a net device。

 I'm not sure I would have spotted this originally。

 but I would pretty quickly discover that some protocols did not work。 Okay。

 and the issue is we're changing an IP address in the header of the IP packet。

 And if there are any other places in the data where that same IP address appears we should change them。

 Now you might look at me strange and say， why would there be other places in the data that have the IP address isn't that a network layer thing。

 And shouldn't， you know， that be only visible on the network layer and I would say， yeah。

 that probably should be the case。 But there are protocols where it's not the case。

 FTP file transfer protocol is a very commonly known mechanism where this is an issue。

 And the reason that's an issue is because FTP actually makes two different TCP connections when it's trying to transfer a file。

 One of which it uses to send the data to actually do the file translation or file transfers。

 And the others a command channel。 And the idea is that in the middle of transferring a whole bunch of data you could。

 for instance， still want to communicate to the far end server and say， oops。

 I didn't actually want that。 You know， let's instead of waiting for that six gigabyte file to come to me and then be able to send your response。

 let me immediately interrupt it or something like that。 And so they wanted two different channels。

 The problem then is they have to be able to tell the other side which channels go with each other。

 right， because you think about from the FTP servers perspective。

 he's just getting multiple TCP connection requests。

 And needs to know this command goes with which data stream。 And so。

 part of the FTP protocol uses the IP address to do that。

 So we actually send the IP address as a message。 And not in the TCP header， but in the payload。

 actually not even in just its payload in the TCP segment payload。 Right。

 It's part of the FTP protocol。 And that means the net device is going to have to detect。 Oh。

 this is an FTP stream that is going through this device。

 And I've got to be able to look through and find and understand the FTP protocol enough to be able to find that IP address and rewrite it as well。

 Okay。 And there are other protocols。 SIF is another protocol where this happens。 Okay。

 we've got to be able to go into the actual data at the application layer。

 And change that to match the IP addresses we're using later on。 That means， by the way。

 what happens if those packets got fragmented。 It may mean that the routers got to， you know。

 it's going to be receiving some fragmented packets。

 It's going to have to put them back together and then be able to look at it and say， Oh。

 this is FTP。 Here's the， the correct place to put this back together。 Not a big deal。

 but more more complexity than you might want in a net device。 And further。

 encryption is a big problem。 Right。 If that FTP stream had been encrypted。

 then that net device doesn't know the keys can't look inside， can't find the IP address。

 doesn't know how to rewrite it。 Okay。 So there are some issues here with with what the net device has to do and some limits on what it's capable is。

 Another limit we have is that the data that table is initialized when somebody on the inside sends a packet to the outside。

 Right。 That's when the net device figures up what the translation should be and stores it in the table。

 Okay。 And that often is what we have right when I send a request to a web server somewhere。

 I'm initiating it from within that internal network。 But it's not all the cases。 Right。

 In some cases， we have a device outside my network that would like to connect to somebody on the inside。

 Okay。 Say， for instance， I've got a buddy， I want to play a peer to peer direct game。 Right。

 He needs to somehow， you know， he's starting up。 He needs to send a packet to me。

 But if the net device gets this packet without anything having gone out， it'll come in and say， Oh。

 I'm sending to the address of the house。 And please， well。

 that net device doesn't know what to do with it。 Right。

 It doesn't know which of the computers on the inside wants to play that game。

 And so it doesn't know how to actually rewrite that to an internal IP address。

 And so port forwarding is the is one solution to this。 Okay。

 The idea is that you from an administrator standpoint， you go into the net device and you say， Oh。

 any time you get some traffic for this particular port number， send it to that particular machine。

 Okay。 So， you know， anytime I'm going to play that particular game。 You know。

 hopefully we'd figure out what that port number is for that game and then we'd send it to， you know。

 bills， the only one in the house is playing that game。

 I don't know what you do if you have multiple kids who are playing the same game。 It's a。

 it's a solution， but it's a sort of working solution。 Right。 It means， for instance。

 the inside my house， I can only have one public web server。 Okay。

 Because I couldn't have multiple computers on the inside all wanting port 80 requests that were initiated from outside the network outside the public。

 There are other solutions。 Okay。 There are， we call them connection reversal solutions。

 There are other algorithms that can make that happen。

 Usually by having a third party server that we communicate to at some point。

 and that third party server can do the， connection between them。 But yeah。

 just not devices complicate the process of making that happen。 All right。

 So that device is sound like they're great。 Right。 And everybody should love them。

 And that's not the case。 All right。 So there are some real。

 There are some objections to the use of that devices。 First off， hey。

 that devices are there to solve an addressing problem。 We don't have enough IP addresses。

 What's the correct solution to not having enough IP addresses。 So， let's move to IP V six， right。

 IP V six， as we'll learn in a minute has plenty of addresses。 Right。 And in fact。

 many people would credit the rise of network address translation as the thing that has slowed down adoption of IP V six。

 And it's not possible for us to keep going with IP V four， which。

 if you're an IP V six person that's a bad thing。 If you're。

 I just want my network to work person it's not necessarily bad。

 It also violates the end and principle， right， then the end principle basically said the stuff in the middle of the network should be as dumb as possible。

 All right， let all this stuff happen at the end。 Okay。

 but now I have this device in the middle that's actually keeping state around。 Okay。

 and working to do something that maybe shouldn't be done there。

 There shouldn't be processing packets higher than network layer， right， my， my NAT device。

 which is typically in this router。 Right， is a network layer device。 But what's it doing。

 what's dealing with port numbers。 It's looking into my FTP protocol to rewrite stuff。

 Those are transport and application layer processes and it should happen at those other layers。

 not in the network layer。 And that's a good thing。 Also， we're addressing a host。

 we're actually telling this particular computer over there that piece of hardware。

 and we're using a port number to do it。 Right， the network address translation device is。

 is receiving requests， all of which have the same IP address。

 And that's a figure out which of the internal machines that should go to。 Okay。

 that also seems to be violating a layer property and not working things properly。 Okay。

 so you make your own decision， right。 I can look at these and I can say， yeah， you're right。 Yeah。

 yeah sure。 Okay， yeah， I agree to all four of these。 These all four are。

 are objections that are true。 And yet I still have in that device in my house。

 because I want to have 60 or 70 devices inside my house and I don't want to have to buy the business network to have 60 or 70 different IP addresses。

 All right， so on to our final today， IPV six again， wow， should be more important than that。

 There we go。 Big IPV six right。 There are a couple things to talk about about IPV six。 First off。

 the reason it's here is this address exhaustion process problem right。

 Maybe four has 32 bit addresses that's four billion devices as early as the early 90s。

 when there were way less than four billion network devices in the world。 At that time。

 people were looking around and saying， Oh， we've got a problem coming。 Now。

 a lot of that problem was because of the class full nature of how the IP addresses were managed。

 I've mentioned this a few times before before 1996。 If you wanted to get a range of addresses。

 you were limited to a slash eight， a slash 16 or a slash 24 prefix。

 And there were a lot of cases where slash 24 was too small and slash 16 was too big。 Right。

 If I had a company with 300 computers in it。 That's too big for a slash 16。 Okay。

 I'm sorry that's too big for a slash 24， but a slash 16 is huge。 Right， it's like 16 has 65。

000 computers in it and I'm using 300 of those addresses。

 And so that's one of the solutions to this problem that was worked out was we went through this assless inter domain routing process which meant upgrading some protocols to allow us to have a slash anything in a prefix。

 Okay。 However， and that helped for a while。 It didn't help entirely as of 2011。

 There are no outstanding IP addresses just sitting around waiting to be used。 And nowadays。

 if you want to buy an address， or if you want an address， you have to buy from somebody basically。

 So， back in the 90s， the decision was made， we should make a new version of IP so that we can have bigger addresses。

 And as often happens， people said， well， we're going to break this protocol。

 We're going to have force a bunch of stuff to change。

 So let's go ahead and clean up a bunch of other things we want。 Okay。

 so the header that streamlined a bunch。 The option stuff that had never worked super well and I P before was changed a little bit so that it works a little bit better now。

 There's a self configuration mechanism we'll talk about that lets computers decide their own IP address as well。

 And， you know， makes sense to solve those pile all this in。 So first off is the addresses。

 32 bits is too small。 Right， let's go ahead and change it， not just a little let's change it a lot。

 So the IP V6 addresses are 128 bits in size， which at least right now seems like a huge vast number。

 Right， not just actually bigger than that， bigger than huge。

 It's a really monstrous number of addresses。 Right。

 it's 340 billion billion billion billion addresses。 Okay， two to the 128 is a big number。 Right。

 people typically this is compared to the number of atoms in the universe。 Right， and said， oh。

 this is a bigger number。 Okay。 And， and， you know， I'm sure back in 1970 somebody said， oh， 32 bits。

 That's a really big number。 We should actually hold this for a while。 And， you know。

 we're saying right now 128 bits。 That's a lot。 That'll probably hold this for a while。 We'll see。

 I'm sure I won't have to live。 I won't live until it's a problem。

 We write the addresses a little bit differently。 Just so we know these are different from IP V4 addresses。

 We can look at an IP six address。 And because it's written differently。

 we know it's that's what it is。 Okay， and， you know， I mean underneath it's still a bunch of bits。

 Right， we just choose to represent it in this way。 We represent it in hex decimal。 Okay。

 which means I've got digits plus ABC， D E F in it。 And because it's a long string。

 we put a colon every four characters。 Okay， and so that address that I'm listed there， that is a。

 IP V six address。 Okay。 It's huge。 It's big。 Hard to remember because it's got 128 bits backing it up。

 Some of the things we do this that help us not have to write so much stuff。 Is first off。

 if there's ever leading zero in any of the packets of four， the little four character chunks。

 you just don't write them。 Okay， so if you have zero one， two， four， you just write the one， two。

 four。 Okay， and the colon's help you know。 Oh， that should be four characters。 It's just three。

 There must have been a zero at the leading piece of that。 And then further。

 anytime there's a string of a whole bunch of zeros。

 The longest string of zeros in the number gets collapsed and we just throw it away and we write our two colons with nothing in between。

 And now I was careful about that I said the longest string。 It's possible to have two different。

 you know， you got eight zeros over here and 16 zeros over there。

 Because we have so many available in that case I'd still。

 I'd collapse the 16 and I'd still have eight zeros I have to write。 Okay。

 And so that helps us get down to more manageable notation for these。

 There are different classes of addresses some set of addresses that are set aside for different purposes。

 kind of like we've done with IPV six addresses。 So for instance。

 all zeros is unspecified so you're not allowed to use it for stuff。 Okay。

 I mean you're not allowed to assign it to a client。 Okay。

 there are some cases where you use it like we used all zeros for our DHP a few slides ago。

 Cold cold one so that's 127 zeros and one one。 Right。

 that address is a loop back address kind of like the 127。0。01 address。

 That means the same computer I'm on。 If it starts with eight ones it's multi cast。

 If it has 71010 we call that link local。 Okay， that basically means this address is a non routable address outside of our link。

 And there's also a site local， which means it's non routable outside of some network size so that's allowed to be routed from router to router to router。

 So for instance Carnegie Mellon would spec would make sure that something that was generated on the inside of Carnegie Mellon's network with this address never went outside of Carnegie Mellon。

 So that allows for instance Carnegie Mellon to allocate those addresses however it wants。

 because they only get managed within Carnegie Mellon。 So here's the header then it has to change。

 Right， and there's a bunch of changes that show up here things to cleaned up as I mentioned。

 and we have humongous addresses。 So here's our IPV four header to remind ourselves what that looked like。

 And there over there's the IPV six header。 All right， got some boxes， more boxes。 It's bigger。

 What's going on here。 Well， once again we start off with a version number。

 And the first four bits same as version four， except now the bits are 0110 because it's the number six for version six。

 Next thing up is a traffic class。 Okay traffic class。

 And the flow label the next two these are used kind of。

 They're available for network operators to do stuff with。 Okay， kind of like the type of service。

 what were the， there was another one in I。 Yeah， type of service field in IPV four。 Right。

 that never really has a global definition， but you can use for different stuff。

 There's a payload length。 Once again， every time we see length。

 we should ask ourselves two questions。 One of them is length of what。

 So this is the length of the payload of whatever this header is describing。

 It does not include the length of the header。 And it。

 and the second question is what's it measured in what units and that units are bites。

 The next header field， this is kind of like the upper layer protocol field。 Okay。

 this specifies when somebody receives one of these headers。

 I'm sorry one of these IPV six packets and is looking through this header。

 Who should they hand it to？ Who should this data go to？ The thing that's in this。

 It's called next header。 Because if you think about the。

 the bytes that are put together in this packet。 If I think about that data field。 The date。

 the first thing in that data field is going to be the header of some transport layer thing。 Right。

 because that's what's in there。 That's what's encapsulated in an IP packet。 Okay。

 so the next header is telling us what the type of data that we see next coming up this。

 And we'll see that this gets expanded a little bit in an interesting way。 Okay， as well。 Oh。

 I guess I have it on the slide right。 So， so we have numbers like 17 and six that do the upper layer protocol that saved the next header。

 The thing in the payload here is， is a UDP or TCP packet。

 We also have other values there that let us put options as a encapsulated piece of the payload that would then get chained on to another header。

 To handle the actual data。 And not sure I said that super well。

 So let's imagine that I have some option I want to specify。

 I want to do something different with these packets。 Okay。

 what you do instead of having a separate options field like we did an IP before。 We just say， Oh。

 that thing。 That's going to have all the data about your options。

 We're going to put that as the first thing in our data payload。 Right。

 the first thing there will be the structure of this option。

 And we will tell you the next header is you option number 17 or option number 649 whatever that option is。

 We're going to have a number up there that specifies， Oh。

 the first thing in this field is going to be that option。

 That can then chain on right that option then would have， you know。

 maybe there's 32 bytes of data there related to this option， whatever that option thing does。

 And then following that would be a TCP pack a TCP segment。 Okay。

 well the option then would tell you in some field there in the option would say， Oh。

 the next header that's coming up is a TCP segment。 Okay。

 so it's a little cleaner mechanism for options processing。

 We've renamed time to live into pop limit。 Okay， we've taken out the idea that there's any time related to this every time you go through a new router you're going to subtract one。

 And then of course we have these huge addresses 128 bits each。

 which means our header is now huge 40 bytes in size。 Okay。 But a lot of it's cleaned up。

 There's a lot of fields that have， oh， there are a lot of fields that have disappeared。 Yeah。

 you'll notice there's no fragmentation stuff there。 We mentioned earlier that in that。

 we didn't fragment packets。 Okay， well that means there's no need to have that fragmenting identifiers and offsets and whatnot and flags in our header to make that happen。

 And the last thing to quickly talk about is， there are many cool things in IPv6。 Okay。

 so I've chosen one that I think is particularly cool。 I'm sorry， question here。 Yeah。

 the check some header has been removed and that's partially that's because the mechanism we normally do to handle that when IP is handling TCP and stuff like that is that there's a combined checksum。

 I haven't talked about it in this class， because it's not。 I mean， it's a real world thing。

 not really a theoretical thing。 This is not quite right。 So in reality。

 what is often done is if you know you're running TCP over IP。

 you run the checksum over both headers at once， instead of calculating two different checksums。

 Okay， and so we call， we say we create a pseudo header and we。

 we calculate the checksum overall of that。 The reason I say that's not theoretically the thing is because the layer architecture you don't know that TCP is actually running over IP。

 And so you should be doing it separately， which is kind of the way I've taught you。 Okay， for IPv6。

 we could look at it as if， well， I guess there's no checksum there。

 So there's no integrity here in real life what's done is， well。

 you're sending a TCP segment that's going to have a pseudo header checks。 As well。 Okay。 One。

 One thing I quickly want to talk about is the sort of configuration mechanism。 It's kind of cool。

 The idea is that you can be newly booted， know nothing about the network。

 and still be able to send data immediately， instead of having to go through a D HCP process to be able to come up with an IP address to use。

 The requirement for that address is that it's unique。 Okay。

 and how do you guarantee that uniqueness？ Well， you've got to have some other mechanism that you know is going to be unique。

 but that's pretty common。 Oftentimes have things like Ethernet， Max。

 a MAC address that we know to be globally unique。 And so let's just use that data as a mechanism for helping us build a。

 our IP address that we know will be unique。 Okay， so if I。

 especially if I have some simple like I don't ever expect to send packets outside of my local network。

 I can do this。 And， you know， I've given an example of a printer that's commonly the case that your printer only talks to machines locally。

 and there are other devices， and maybe some of them we'd like， you know。

 we'd like our Alexa devices， maybe to only be local or I don't have something like that。

 This is called auto configuration。 Okay， and the idea is if you have this number that you know to be unique。

 Okay， you go ahead and put it into what's known as a link local。

 IP address to create an IP address that you know that is unique to your own local environment。 Okay。

 so this is， I showed you that that link local address prefix earlier it's an anything that starts with seven ones and then 010 that pattern in it。

 You know that is only going to be used on this particular subnet。 Okay， and so therefore I can。

 as long as I use something that I know won't conflict with anybody else on the subnet。

 I can go ahead and put whatever value I want for the remaining 128 minus well that's 10 bits。

 the remaining， 118 bits。 I just have to make sure they're unique from everybody else on my local network。

 I could probably choose a random number， as long as everybody was choosing randomly that would work instead what we typically do is just take your email Mac。

 which is 48 bits and use it as part of this address。 Okay。

 and now I have an address that I can use if I'm a printer to talk to anybody around。

 and that's fine。 Or I can use this as a starting address and then go ahead and go through a DCP like process to ask for what my real IP address should be。

 Okay， so today we've done a quick spin through three different technologies that are all related because they're network layer technologies。

 but none of them was big enough to have their own lecture sort of thing。 Well。

 I guess I could have done a big lecture on any of them but we don't have time for that so we showed them all together into into one lecture and describe these three different pieces that hopefully see our vital technologies to making the network work like it does today。

 And then as easy plug and play capabilities， and someday IPV six will take over。

 and we'll be able to easily communicate with。 All right。

 thanks very much everybody are we good on some questions。 Okay。 All right， thanks everybody。

 We'll see you all next time， not in economy， right。

 you'll be in your own location will be taking quiz。

 And with that let us know if you need any help with the preparation if you have any questions。

 please throw them on piazza。 Go to the review session， but the TAs， ask them。 Questions then etc。

 Okay。 All right everybody， have a great day。 Goodbye。



![](img/8f7ea6b6d1fa4dba8813add677ced6f3_8.png)

 See you。 and you can。