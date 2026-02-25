# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p02 -02-1.2 The network edge.zh_en -BV1UMtueiEaA_p2-

![](img/2c47e6eaf695ec30c4b4121cf6484668_0.png)

In the second video， we're going to look at what's happening at the network's edge。

 and we're starting at the network edge。 Well， because that's what we're familiar with。

 is what we see。 It's what we use every day。 We're going to cover two topics here。

 We're going to start off by covering access networks。

 The access network is the network that connects the edge device。

 those amazing edge devices that we saw in the previous video into the first hop router into the larger Internet。

 In some cases， an access network connects a network itself。

 say a home network into this larger internet。 And then we're going to take a look at physical media will take a look at the copper wires。

 The fiber， the radio that's actually used to transmit bits from the input side of the link to the output side of the link。

 Now， to get started， let's remember the broader context。 Well。

 you see our graphical depiction of a network over here on the right In the last video。

 we talked about all of the amazing devices at the network edge， computers， smartphone cars and。😊。

Home and personal devices。 We noted that these edge devices are sometimes called hosts because they host or run network applications。

 A host might be a client that requests and receives a service or a server that provides a service。

 And we'll see in chapter 2 that client and server have very precise meanings in a networking context。

 In the last section we also talked just a bit about access networks and physical media。

 And that's what we're going to focus on here in this section。

 And we also talked about the network core， a set of routers that are interconnected to form a network。

 And we also talked about how these individual administratively scoped networks are interconnected to form an internet。

 And so that's the big picture context that we're starting with。

So what we want to focus on here are access networks， it's the network that connects the end system。

 the host， the device into the larger global internet。

 it's really that network that connects this device to its first hop router on a path from source to destination and we'll see that there are basically three types of access networks there are residential access networks。

 there are institutional access networks that are operated by a company by an educational institution by a municipality and then there are mobile access networks that are operated by cellular access carriers and also Wi-F networks。

And as we're talking about these three different types of access networks。

 you might want to keep two things in mind first， what is the bit transmission rate over that access。

 that is how fast is that network？And also， to what degree must one user share that network with other users？

So let's start our discussion of access networks close to home， well。

 actually in our home by first looking at cable access networks。

As shown in this figure here in a cable access network， I have Comcast cable access， for example。

 in my house， a physical cable connects multiple homes to a single cable head end over here on the right。

The signals to and from these houses are sent on the cable at different frequencies。

 signals sent at different frequencies don't interfere with each other。

 sort of just like FM radio with FM， different stations can transmit on different frequencies。

 and we tune into the frequency that we want。Cable access networks are based on the same approach known as frequency division multiplexing or FDM。

But there are only so many frequencies， and so cable users also often have to share a frequency with their neighbors。

We'll cover cable access networks and their standard known as Doxs when we get to Cha 6， for now。

 relax the idea to get the big picture here and we'll save the details for later。

Cable access networks are typically asymmetric， meaning that they're designed to transmit data faster in the downstream direction to the home rather than upstream from the home。

 and this asymmetry reflects the fact that we tend to be more consumers of data than producers of data。

Typical cable transmission rates are 40 me per second， up to 1。

2 gigabbit per second in the downstream direction and 30 to 100 mebit per second upstream transmission rate and of course。

 as the saying goes， your mileage may vary and of course your modem will often typically rate limit how fast you can send and receive basically you're getting what you pay for。

And note again that the cable network is a shared network。

 it really is just a shared wire that you can see often strung up on the telephone poles。

 this means that if you and your neighbor are sharing a frequency on the shared wire and your neighbors blasting away。

 transmitting and receiving a lot of data， that may be eating into the amount of data that you're able to send and receive。

The second major type of residential access is what's known as digital subscriber line DSL。

 DSL networks use the existing phone line， sometimes called a twisted pair because there are two copper wires that are sort of wound around each other that you to or maybe still do carry phone service to your home。

 These DSL wires connect you directly to what's called a central office。

 So you're not sharing transmission capacity or bandwidth with your neighbors between yourself and the central office。

 Now， light cable networks。 DSL lines are also asymmetric with a 24 to 52 mebit per second downstream transmission rate and a 3 and a half to maybe 16 mebit per second dedicated upstream transmission rate。

 and these transmission rates depend very strongly on the distance between the central office in your home。

 And indeed， if you're too far away， generally more than about three miles。

 you can't actually do DSL to the central office。And now let's take a look at the home itself。

 This is what a typical home network might look like。

 There's a DSL or cable link coming in from the local telco or cable network。

 and then there's a cable or DSL modem， modulator demodulator on the house end of that link connected to the cable modems or router that has both wired and wireless links to devices within the home。

 Now， these links are typically wired ethernet that runs typically at 100 Mbit or gigabbit per second transmission rate and wfi。

 which runs at tens or hundreds of megabits per second。 Often， the router， the modem。

 Wifi and ethernet are all combined into one box。 And then， of course。

 we've got the home devices themselves， the hosts and the end systems that we talked about earlier。😊。

Since we've already mentioned Wifi networks in the context of home networks。

 let's take a look at wireless networks first。 Now。

 all of Chapter 7 is going to be dedicated to wireless networking。

 So we're just going to look at the big picture here。

 And one way to think about this is there's basically two classes of wireless networks。

 There are the local wireless networks， Wifi， for example。

 And then there are the wide area networks corresponding to 3G4G and soon 5G cellular networks。 Now。

 for both the local case， the local wireless networks as well as the digital cellular networks。

 There's an entity， a base station and access point to which the end devices transmitting data and receiving data from。

Well， the first broad class of wireless networks are known as Wifi or wireless La WL networks。

 We've already seen these in the context of home networks。

 but they're also widely deployed within municipalities with companies and other institutions as well。

 they tend to operate in the range of about 10 to 100 meters if you're lucky at 100 meters and they operate at different speeds from 11 to 54 to 450 mebit per second。

 These protocols are actually standardized by the IE under the family of 802。11 protocols。

 they're not standardized by the IETF。The second broad class of networks are the 3G4G and Zm 5G cellular networks。

 These networks are operated by the mobile cellular operators。

 and they tend to have a transmission distance measured in the tens of kilometers。

 and they can have transmission rates anywhere from1 to 10 to multiple tens of megabits per second per user。

And finally， there are enterprise networks and we might think of some enterprise networks sort of like home networks on steroids。

 an enterprise network could have a mix of ethernet。

 wired ethernet and wireless Wi-fi links and one difference from a home network is that an enterprise network would typically have multiple switches and routers to handle the large number of devices that would be connected to that enterprise network another type of enterprise network that doesn't look at all like a home network are data center networks that connect massive numbers of servers to each other and to the Internet at hundreds of gigabits per second will cover data center networks in detail in chapter 6。

Well， that's all we're going to say for now about access networks。

 And we're going to come back to this in great detail when we get to chapters 6 and 7。 For now。

 you might want to just think about the physical media that we've been talking about。

 the copper wires， the fiber optics and the radio links。

 and And we're going to get to that in just a second。

 But first I want to say a few words about packets。 I've used the phrase packets of data。

 and we've talked about how as sender sends a packet of data into the access network。

 What does that really mean。Let's take a look at this host here。

 which is sending data to a first hop switch here and consider it sending operation。

 the highest level， the host has some data it wants to send， say a large file。 What is the host do。

 Well， the host is going to take the data it wants to send and break it into smaller chunks of data known as packets。

 and as we'll see， in addition to the data itself， itll add some additional information to each chunk of data in what's called a packet header。

 a protocol will dictate exactly what information is added into this header。 A packet。

 the data plus the header will have a length of say L bits typical value for L might be 1500 bys。

The host then transmits this L bit packet into the access network at some transmission rate R measured in bits per second。

 and as we've already seen， R varies from one type of access network to another。

 We saw that using wired ethernet， a host can send it gigabbits per second。

 but over a 3G or 4G network， it may be constrained to a few megabits per second or less R is best thought of as a link transmission rate。

 but it's sometimes more informally referred to as the link capacity or the link bandwidth。

 If one wants to send an L bit packet into a link at transmission rate R。

 than the amount of time it takes to send those bits into the link is the number of bits to send L divided by the transmission rate R and we'll come back to this later。

Well， we're going to wrap up here by taking a quick look at the physical characteristics of different transmission media and but before doing so。

 I want to say just a quick word about our depth of coverage here。

 there are tons of interesting topics that we could cover here in terms of modulation and coding and things that have to do with the physical transmission of bits but there's only so much that we can fit into a course and so here we're going to go over this pretty lightly。

 if that's the kind of thing that gets you really excited。

 you want to learn more should definitely take another course and you should pick up another book on this。

 We're going to be looking at the physical characteristics of different transmission media at a rather high level。

 we're going to be concerned about what are the bit loss characteristics， how do signals interfere。

 what do propagation delays look like but we won't get down into the details of how different physical transmission media work if you want to do that pick up some more material。

 you know it's really a question of。Then this is of course， on networking。

 we're going to start from here and work our way up。Okay。

 so here are some very basic facts about physical media。

 remember what we want to do is send digital bits over some physical media from sender to receiver。

 The physical media could be what's called guided media that some kind of physical wire or cable may be made of copper or optical fiber。

 or it could be over unguided media where signals propagate freely like radio or acoustical waves。

Twisted pair used to refer to the real twisted pair of wires that carried with your grandparents telephone signals into the house。

 but now refers also to Ethernet or ADSL and runs it hundreds of meabbits per second and sometimes gigabbits per second。

 They can be susceptible to electromagnetic noise。 you've probably seen ethernet cables like this in your home or office or school。

Coaxial cables used to carry cable network access into your home and operates at hundreds of megabits per second。

 old fashioned ethernet actually used to run over cables like this， but not for at least 20 years。

Fibber optics cable carry light pulses and operate at hundreds of gigabits per second and higher and have very low error rates。

 so in some sense， they're really ideal for communication。

 but the transmitting and receiving components tend to be more expensive than that for traditional copper wires。

With a wireless link， bits are modulated onto a signal carried in some frequency band in the electromagnetic spectrum。

 There's no physical wire， and transmissions tend to be broadcast。

 meaning that any device near the transmitting device may be able to receive the transmitted signals。

 And this obviously raises eavesdropping and also interference concerns。

 Wire is a notoriously harsh environment for transmitting radio signals fade over distance。

 depending on the frequency signals can be reflected off of objects or blocked by objects。

 or at other frequencies， they can just pass right through objects like walls。

 They're subject to noise generated by motors， microwaves and other devices that emit RFf signal。

 So transmitting bits over wireless requires a lot of work at the physical layer。

 and that's why there are entire courses devoted to this topic。

There are many types of wireless links that you're probably familiar with。

 We've already discussed Wi-fi networks that can transmit at up to hundreds of megabit per second。

 maybe over tens of meters distances，4 gcellular networks transmit data at rates of tens of megabits per second over distances of up to say 10 miles。

 many of you probably use Bluetooth which is used as a cable replacement technology and operates at relatively low data rates。

 say one or2 mebits per second max， and over a relatively short range。

 usually not more than5 or 10 meters。 And here are other forms of wireless networks。

 there's terrestrial microwave that operates at tens of megabit per second point to point。

 And that's about the same transmission rate for satellites。 In the case of satellites。

 there's a noticeable propagation delay。 That's the time from when a bit is sent at the sender to when it's received at the receiver a noticeable propagation delay of 270 milliseconds。

 between a sender or a receiver and a geosynchronous satellite。

While that wraps up our initial discussion of what's happening at the network edge。

 hopefully you've got a better high level understanding now about access networks and physical media Next up we're heading into the network core。



![](img/2c47e6eaf695ec30c4b4121cf6484668_2.png)

![](img/2c47e6eaf695ec30c4b4121cf6484668_3.png)