# 【计算机网络 CS144】斯坦福—中英字幕 - P141：p140 9-7 Sanjit Biswas CEO of Meraki (interviewed by Nick M) - 加加zero - BV1qotgeXE8D

 So， I am here today with Sanjay Biswas， who is the CEO of Meraki， which last year was。

 acquired by Cisco。 Sanjay was a Stanford undergraduate。

 and that's how I met him originally before he escaped。

 to MIT and then started a very famous research project in wireless networking called the。

 Rufenep Project， where they built and then operated a peer-to-peer network wireless system。

 across Cambridge， Massachusetts for MIT students。 And after that。

 Sanjay and his colleagues started Meraki， and Sanjay was the CEO for， the duration of the company。

 and they built cloud-managed Wi-Fi networks。 The Wi-Fi network in the Gates Computer Science Building at Stanford。

 and at many universities， is based on Meraki。 And so it's a delight to have you here， Sanjay。

 How are you？ Great。 Thanks for having me， Ned。 So let's get stuck in with some questions。

 In Unit 7 of the Introduction to Computer Networks class that we teach CS144， the students。

 learn some of the basics about wireless networking， in particular they learn about how a wireless。

 network is very different from a traditional wired network。 And the channel is different。

 interference， multipath， shadowing， and so on。 It means that connections come and go。

 that data rate is always changing。 Now， you learned a lot about these things in the roofnet project。

 and you had a lot of， practical experience。 So can you give us a quick overview of the roofnet project at MIT and some of the things。

 that you learned when you were deploying a real operational Wi-Fi network？ Sure。

 So the basic idea behind roofnet is we were trying to build a research prototype network。

 that we could use to provide broadband to students across Cambridge， which is the city。

 that has both Harvard and MIT in it。 It was called roofnet because we were installing these antennas on students' roofs。

 writing， mesh networking software that would route packets through the network， and essentially。

 provide bandwidth from a small number of sources on campus。

 What was interesting about that project is it was very much real-world。 So we had real-world links。

 as you mentioned， so we saw very interesting wireless behavior。

 that was very different from what we saw in simulation。 We had routing protocols。

 we had to write and deploy in a production environment， and then。

 we had real students with real traffic。 And all of those were interesting factors。

 So I think you touched on some of the most fascinating things that we saw， which is that。

 links behave differently than people originally thought。

 I think the belief at the time 10 years ago was that links either worked or they didn't。

 So if you could receive an advertisement that a link was operational， then you could route。

 traffic over it。 What we discovered is many links would deliver 30% of their packets or 70%。

 And that number would change over time， it would change by modulation， it would change。

 by interference。 So if there was someone else in the network transmitting at that time。

 a link that used， to deliver 80% of the packets would only deliver 20%。

 So there's self-interference。 So those are kind of fascinating link level issues。

 As we kind of moved up to stack， we noticed applications actually had a big impact on。

 how the network behaved。 So you'd have a student running BitTorrent。

 and all of a sudden 100 other students were， affected because that one person was downloading a gigabyte file or something like that。

 So I think you had a kind of layering of issues which made it for very fascinating research。

 I think that's what led us to a lot of the conclusions that you saw in the papers， how。

 do I MIT in the rooftop project。 So your first product， if I remember right。

 was a mesh network where the packets were carried， from。

 essentially from laptop to laptop until they reached the edge of the network or reached。

 a point where they would connect to a wire line into the public internet。

 So that's how roof networked and then the first products of Meraki。

 It was pretty unusual at the time。 People had talked about that for a while。

 And is that idea persisted？ It has。 So the meshing concept is still in the product。

 What we noticed is over time that that was considered novel， especially from research， perspective。

 As we commercialized what we built， we were getting asked to do other things that would。

 be on the scope of mesh networking。 So for example。

 making the network just simply easy to deploy and manage。 And that's IP addressing， user management。

 remote monitoring， all that kind of stuff。 Is that where we ended up spending a lot more time？

 But our products， even today， still have a mesh built in。 And so if I remember right， very early on。

 you were essentially managing other people's， networks for them。

 I seem to remember you telling me that there was even a monastery somewhere in Tibet that。

 you were managing。 So you really learned about how to remotely manage other people's networks for them。

 Yeah， exactly。 And that's， I think that actually started with the roof net where we were the IST。

 And we as a strong word， there were only three of us who were grad students at the beginning。

 The team didn't get that large， but we were writing software， managing the network， teaching。

 kind of doing all those things。 As we started in Marakti。

 we were doing that on behalf of some of our early customers as， well。

 And that's where we ended up building up a tool set that ended up being really valuable。

 to network operators because we could appreciate the kind of problems they had。 So nowadays。

 if I understand correctly， most of your customers， their network is managed。

 remotely or at least configured remotely from one of your data centers in Sunnyvale and various。

 other places around the world。 So what benefits do your customers get？

 What benefits do users get from having this sort of centrally cloud managed， Wi-Fi network？ Yeah。

 you know， when you have a single device， management is not really a big concern。

 You configure it once， you set it and you forget it。 That's it。

 That's typically most home routers like the Linksys or Netgear， Apple Airport fit that。

 kind of concept。 When you have tens of devices， hundreds of thousands of devices。

 the configuration and， management keeping them consistent between different access points or switches or routers。

 ends up being a big deal。 So that's really the benefit is the consistency and then being able to see what the network。

 was doing even if you're a thousand miles away。 So a lot of our customers today are in their schools with large campuses or their university。

 or sorry enterprises who have branch sites around the world and for them to have centralized。

 ITB able to very easily deploy managed network is compelling just from a practicality perspective。

 They just don't have enough hours in the day to go， you know， SSH to remote devices and。

 try to configure them and cross their fingers and hope the thing works。

 So if I'm a big company like， I don't know， Ford Motor Company that has many offices around。

 the world， it allows a central IT organization then to manage and maintain。 That's exactly right。

 So from Detroit， they could manage all their dealerships and make sure they have consistent。

 guest Wi-Fi， they have consistent policies。 If they have a security update。

 they can deploy it very easily。 Those kinds of things which in kind of previous years have been a real pain for a network。

 administrator。 So technically， how is that different from a traditional or a typical Wi-Fi network？

 Yeah， so I think the biggest difference is in the implementation。

 So traditional Wi-Fi networks have what was known as a controller。

 So in a appliance that we would install in a data center or a rack somewhere in the back。

 of the office， that controller provided that centralized management configuration。

 That works fine if you have a single site。 If you have dozens or hundreds of sites that sort of breaks down。

 And so what we did is by essentially providing a virtualized web service that did all that， for you。

 we eliminated that piece of complexity。 The other is we handle all the upgrades。

 all the software management。 So as we were coming out with new ideas。

 new traffic shaping policies and rules， all of， our customers benefit from that。 In the past。

 that would have required upgrading the controller appliance， which often just， didn't get done。

 So networks would kind of get stuck in time at the point they were installed。

 And with the way things are changing so quickly， a new iPad gets released and you need a new。

 form of traffic management so you can provide a good experience for it。

 That was breaking down and becoming very brittle。 So that's really the big difference。

 It's very practical。 I see， so if I understand correctly。

 all of that functionality is in the access point。 That's right。 And then the access point。

 the only other entity is that the access point is connecting directly。

 back to the manager back in the。 Exactly。 So the data plane。

 all the traffic is being forwarded directly to the internet。

 All the kind of high level management reporting， statistics collection， that's all done in the。

 cloud。 And then the firmware on the device can be upgraded on a regular basis of perhaps once。

 every few months。 And that kind of gives you the software defined nature down at the edge。

 So if you come up with a new policy or， you know， a new firmware feature， you can easily。

 deploy that。 If we have a new UI feature， we can deploy that within a day and everyone sees it。

 I see。 So with you having that sort of access or your servers， having that access and control to。

 everybody's Wi-Fi access points， presumably some people get a little nervous about security。

 and privacy and things like this。 Right。 So is that a common concern and how do you overcome those concerns？

 Yeah， it is a common concern。 I think it's a good one for customers to have。

 We're not the only cloud service most businesses use。 In fact， you know。

 whether they're using Gmail or Salesforce。com or one of these other， services。

 I think customers these days are becoming wise to the ways of the cloud and asking the。

 right questions。 So how do you retain your data？ How much of this data is going into the cloud？

 Who can see it？ Where are your data centers？ How are they managed？ All those kind of questions。

 So what we do is we just try to shine a bright light on it and be as straightforward as， possible。

 So we have a little website at moraki。com/trust and the customer can learn about the architecture。

 of the system who runs our data centers under the covers and all that kind of stuff。

 And so from a technical point of view， how does that work？

 So presumably you secure the connection between the access point and your server。

 You can think of it as an IPsec tunnel。 It's running the equivalent of Google protocol buffers over it。

 So the amount of bandwidth is very small。 It's about a kilobit per second。 And that's in aggregate。

 It's all of the kind of statistics collection and so on。

 The real difference is that it is encrypted in the same way that you would expect with。

 public key encryption。 Yeah。 Okay。 All right。 And that's kind of interesting。

 So with all this sort of interest in SDN and in class， we， Martin Casado came and gave a， talk。

 And he runs up to speed on software defined networking。 So many， you know。

 many people believe more and more that networks are going to be managed。

 remotely by software running at least outside the physical data plane。

 They may not be running in the cloud or at the， maybe not be managed in the cloud， but。

 they can be managed from somewhere outside of the data plane。 You seem to be doing that already。

 Do you think that all networks will be cloud managed in the future and that the software。

 will be sort of this clean separation between the software control and the data plane。

 Is that kind of inevitable to think for Wi-Fi networks and， you know， network development？ I think。

 well， so networking is such a big market segment that it's hard to make a blanket， statement at all。

 But I think most certainly will be。 And it's really again kind of practicality。

 We've seen people move from an on premise based email approach with Microsoft Exchange or， you know。

 running their own SMTP and IMAP servers and all that kind of stuff to moving， things to， you know。

 Gmail or hosted approach on email。 It makes logical sense that things like managing network infrastructure will move to the cloud。

 as well。 And what we're hearing from a lot of our customers， it could be big or small。

 They just find it simpler。 So I think the world tends to prefer efficiency and simplicity。

 So the short answer is yes。 I think most networks over the next five。

 ten years will move to this cloud managed model。 And if I understand correctly。

 it's not just Wi-Fi access points。 It switches physical switches for wired networks as well。

 That's right。 So switches and also routers or security appliances。

 so kind of the gateway device that connects， between the service rider and the local area network。

 So what we discovered is originally we started out building wireless products。

 We built in-order outdoor products。 We were kind of coming out with every shape and size。

 And then customers were saying， this is wonderful。

 I have a tremendous amount of visibility management on the wireless network。

 But I also have a lot of wired devices， whether they're PCs， point of sale terminals， printers。

 security cameras， phones， that kind of stuff。 Could you provide that management over the wired network？

 So now we just do all of it。 And it works really well together because consistency is really what people are looking。

 for。 They want to set a policy and then just have it go across the entire business。

 So do you think this will start being the way that my home network， my Wi-Fi and general。

 home network will be managed in the future by outsourcing the management to the cloud？ I could be。

 We didn't address that specific use case。 The kinds of products and the way that consumers buy is a little different than the way businesses。

 buy。 So we ended up focusing on the kind of enterprise or campus use case。

 I do think we will see more consumer products managed from the cloud。

 So I just recently installed a Nest thermostat， which I think are becoming pretty popular。

 It's a really cool experience being able to remotely change the settings of your temperature。

 And if you go on vacation， you can turn it down and all that kind of stuff。

 It might make sense for people to do that with their bandwidth as well。 It's only a matter of time。

 Hang on， I'm just logging in here to change the temperature。 Let's hope they're good。 It's a kid。

 Yeah， exactly。 So we're looking forward when you're thinking about some of the problems that you have to。

 solve not only for Meraki， but networking in general。

 And you're part of Cisco now and part of a big company。

 What do you think are some of the interesting problems to work on？

 You've clearly been working on a fascinating new problem for the last few years。

 What do you think some of the interesting problems in networking are over the next few， years？ Yeah。

 it's fascinating。 Networking evolves so quickly。 Between the time that we started Meraki。

 which is about seven years ago and today， our， products have gotten roughly 100 times faster。

 which is pretty incredible。 That's more as well in action。

 The other thing we've seen is the number of devices connecting behind our networks has。

 grown considerably。 And in 2006， the iPhone was just coming out as primarily PCs and laptops that would show。

 up on these networks。 Now it's really all these mobile devices。

 So I think the way things are headed is that's not going to stop。 In fact。

 we talked about the Nest earlier， but you see things like the Fitbit scale and。

 other products connecting the Wi-Fi network。 It's only a matter of time before lots and lots of devices are connecting。

 And I think that's going to be interesting because these are devices that may not have。

 a UI attached to them， where you can click on the network and type in a password。

 So I think that's going to lead to interesting questions about how do you authenticate these。

 sort of UI-less devices。 That's going to lead， of course， to capacity issues。

 When you have a thousand devices on a single network， there's always contention。

 So I think there's going to be interesting problems there。

 And then I think people always want these networks to be faster and more manageable。

 So all of these problems， what's going on is the scaling of number of devices， the amount。

 of bandwidth， the number of sites， all that kind of stuff。

 So whenever you see that such rapid expansion， I think it creates a lot of new research problems。

 and problems for industries as well。 So we have 200 people in the CS144 class at Stanford this year。

 So there's going to be lots of people sitting there that are going to go on to be entrepreneurs。

 and start their own businesses。 Some successful， some probably not。

 From your vantage point now with the experience that you've had as a researcher becoming an。

 entrepreneur， starting a company， being a CEO and then taking that company to be very， successful。

 What's the advice that you would offer to students sitting in class who would be thinking about。

 doing the same thing？ What would have been the advice that would have been useful to you to have heard at that。

 time？ Well， I think that the most interesting thing that I noticed about the journey was that。

 we were able to figure out the challenges at every step along the way。 You just outlined， I think。

 what it takes to go from a startup to a company that has。

 a significant amount of revenue and sales and so on。 Every year the challenges were different。

 And I think the way we learned to think in grad school and even in undergrad is we were。

 learning about these kinds of problems。 In engineering classes。

 it ended up applying to the way we built the business。

 So essentially figuring things out from first principles。 I remember。

 I think I was in your CS244 class where we had to write a TCP stack and FTP clients。

 and just make it work。 And that's kind of what you're doing when you're building a business。

 You have an idea of what you're trying to build。 You have an idea of what the interfaces are。

 And then you need to build an implementation。 And a lot of times I think students think， oh。

 I need someone who's been to business school， or I need an expert in the field。

 And the reality is folks at Stanford and other schools of similar caliber are very， very。

 smart and you'd be surprised when you can figure out on your own。 So I wish I'd known that。

 but it wasn't going to be impossible。 In many ways， we also got lucky。

 but it certainly worth trying。 And I think it's a great experience for everyone to give a shot。

 So have confidence in your own abilities and don't worry too much about others who have。

 been struggling at the same problem for years。 Just buckle in and buckle down。 Yeah。

 and it's almost like don't look too much at the related work。

 Just go try to do something on your own and figure it out from first principles and you。

 be surprised。 I think a lot of people think that there's a lot of mastery required。

 And if you think about most of the very successful companies in Silicon Valley， a lot of them。

 were founded by students who had never done it before。 So you definitely can be done。 Wonderful。

 That's great advice。 So thank you very much。 Really appreciate your time， Sanjay。 Great。 Thanks。

 mate。 Bye bye now。 way now。 [silence]。