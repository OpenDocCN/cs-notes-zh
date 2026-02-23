# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p06 -06-1.6 Networks Under Attack.zh_en -BV1UMtueiEaA_p6-

Well， the next topic we want to cover in our broad overview of computer networking is networking security。

 Now there's an entire chapter of our textbook chapter 8 that's devoted to network security and so we'll get to that later and we'll be thinking about security throughout the course as we go through the different layers of the network architecture but for now there are two questions that we might want to keep in mind First。

 what are the kinds of bad things that bad actors can do in a network setting and we'll be focusing primarily on the network rather than the end systems and then secondly。

 what are the broad class of defenses that can be deployed to both prevent and mitigate and react to such network attacks and we'll want to keep the answers to these two questions in mind as we go throughout the course。

Well， let's start our discussion of network security by noting that the original internet architecture wasn't really designed with security in mind。

 and it wasn't as if they really forgot about security。

 but rather the original design vision was for quote unquote a group of mutually trusting users attached to a transparent network doesnn't that sound nice。

 obviously not what we have today but the designers weren't naive。

 it's just that security was not consciously a critical design criteria given the envisioned use at the time and so here we are today still sort of playing catchup in some sense on network security in thinking about network security will need to think about a few things First。

 how can the bad guys attack or compromise a computer network Secondly。

 how are we going to defend against some of these kinds of attacks and then finally。

 how might we design network architectures that are immune to attacks this is sometimes called security by design phrase that。

Love it means that the architecture itself is built in such a way to enable security。

 buildings are built that way， for example， to enable security by design。

 and so too can network architecture and this is an active area of research right now in computer networking。

 Well， let's start by looking at some of the ways in which bad actors can behave。Well。

 it's probably not a bad assumption to assume that a bad actor can get copies of packets that are whizzing by on shared media like a wireless channel。

 for example。 So for example， if we have a bad actor here at C。

 we should assume that C can read everything that B is sending to A along the shared media。

 And there are actually software tools called packet sniffs that can be used to do this。

 we'll actually use such a packet sniffer extensivetenly。

 It's called wirereshark in this class to capture packets on the wire。

 and for us to watch protocols in action。We should also assume that a bad actor can inject packets into the network containing any information they want。

 For example， here's a bad actor at C sending in a spoofed。

 that's to say faked packets to a with a faked source address indicating to A that the packet actually came from B。

 and this is conceptually the same thing as when you get a phishing email claiming to B from a bank colleague or someone saying that they've come into a multimillion dollar summon could you just help them deposit it into a bank account for your shareri of the loot。

 Well， you don't believe them。 And why should a piece of network equipment or piece of software believe what a packet says just because a packet arrived。

Bad actors can also launch denial of service attacks by generating so much workload that a network device becomes overloaded。

 An HTTP server could be bombarded with fake HtTP requests or a router could be continuously inundated with packets to forward or that require some kind of exceptional processing like those trace route packets we saw earlier。

 These kinds of attacks are often done by an actor who breaks into other hosts around the Internet。

 and then has then launched a coordinated denial of service attacks。

 sometimes called a Ddos attack on their victim。These are a few of the most important types of attacks that can be mounted by a bad actor。

 Now， what can we do to protect， mitigate or avoid such attacks？ Well。

 we can protect against spoofing by using authentication。

 forcing you to prove who you are before youre able to get some network service。

 A password is probably the simplest form of authentication。

 The Sim card in your smartphone provides a hardware identity and authentication。

 We can protect against data being sniffed by encrypting packet contents。

 We can protect against data being tampered with by using digital signatures。

 a technique that allows a receiver of data to know that the data was sent by a given digital identity and that it's not been tampered with on route。

We can protect against unauthorized use of network resources by adding access control by specifying who can take what actions and making someone again prove who they are before accessing these resources on the UMass campus。

 for example， you authenticate yourself to our campus wireless network before you're able to use it。

And then there are specialized pieces of hardware known as firewalls that are programmed to detect and mitigate attacks。

 Firewalls sit in both edge and core networks and can be programmed， for example。

 to only let certain users or certain types of traffic in or out of a network will cover firewalls and other so-called middle boxes when we get to chapter 4 and study generalized forwarding。

Well that was just a very high level overview on the topic of networks under attack and we really looked at two questions。

 we looked at the kinds of bad things that bad actors can do in a network setting and then we also looked at the kinds of defenses and techniques that can be deployed to protect to mitigate and to react to network attacks Now remember there's an entire chapter of the textbook that's devoted to network security and we'll come back to topics of network security throughout the course as we make our way down the network protocol stack。



![](img/ba69219ce3b9cfea3e015370452fda6d_1.png)

![](img/ba69219ce3b9cfea3e015370452fda6d_2.png)