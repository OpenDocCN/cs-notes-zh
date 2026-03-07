# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p46 p45 Week 11, Segment 1 - System Security I： Risk Assessment -BV11QQcYmEzD_p46-

Hello and welcome back to CS615 System Administration。

As were slowly approaching the end of the semester。

 it's now time to come back full circle and focus on one of the topics that we had mentioned way back in our very first video as being essential to the job of a system administrator。

 system security。Throughout the semester， we have repeatedly hinted at security aspects of the topics we covered。

 and， of course， it's impossible to adequately cover in sufficient detail the topic as broad as security and just a few short videos。

But as previously discussed， we are aiming to provide just enough information on a given topic to give you an idea where to look for more to realize what aspects are the most important to understand。

 So let's talk about system security。Unfortunately。

 I first have to disappoint you as much as I'd like to。

 I won't be able to tell you how to make your system secure。 There simply isn't an easy formula。

 No free lunches。Throughout these videos， I hope that you will understand why that is。

I also won't tell you how to break into other systems， although of course。

 understanding how to do that is often more than just a side effect of understanding how to defend a system against compromise and of course。

 you will learn a few things that are going to make it easier for you to break other systems。

 such as the nature of systems secure。But， either way。

I obviously can tell you everything you need to know about this topic。

 You can take other classes that focus on many aspects of information security。

 You can get a degree or major in cybersecurity， and you can work for many years in the industry and still not know everything there is to know。

 So here， once more， we are merely scratching the surface。So what good are these videos to you。

 you ask。 Well， here are a few things that I will tell you that I hope you will be able to take away from this。

As I mentioned， I hope that these videos will give you enough information to start looking to give you the keywords and concepts that you will learn are critical。

I'll try to address a few of the problems with information security。

 the industry and how we apply security concepts。 And that is important to know about as well。

 And along the way， I'll try to throw in a few always and nevers。 that naturally。

 always always come with exceptions and thus aren't really always and nevers。

 but as rules of thumb rules of thumbs。Are going to be good for you to keep in mind in your career from here forward。

So why't we start out with one of these pels of wisdom， shall we？



![](img/7769e1757f9a9e83d63346bcf769ddae_1.png)

Here we go。 And this one's a dutyozy。 Security is not an end goal。

 I know I know not what you want to hear。Especially not if you're a cyberseity major or otherwise involved in infosec。

But it remains the truth。 Security is by itself， not an end goal。 It's not an outcome。

 It's not something that's valuable， all by itself。Instead， security is a property of a system。

 a property that may help increase your resilience against specific risks。

And this property comes at a cost so you are always trading off advantages against disadvantages。

We'll talk a bit more about this concept of specific risks in a moment。

 But perhaps we should begin by sorting out just where exactly this mystical security property is applied。



![](img/7769e1757f9a9e83d63346bcf769ddae_3.png)

Oh， I won't surprise you to know that security spends all the layers of the stack。

We had already mentioned early on that security is something that cannot be added on at the end。

 that it needs to be an intrinsic property， part of the system。 So， of course。

 we need to consider security at each layer。And we already did indeed do so， didn't we。

 Let's look back at the materials we've covered this semester。

When we talked about disks and storage solutions in week 2。

 we discussed the different storage models， and we noted how the abstractions from da to na to sands and finally cloud storage。

Incurred increased complexity and， of course， exposure of the data。

When we talked about local file systems， we noted that you can increase the system security by applying different mount options。

 such as mounting some file systems as read only， some with a no exec or no SID options and so on。

When we talked about file system basics and software types。

 we noted that even the firm were on a hard drive， the integrated device electronics that give the IE drive its name can be compromised。

And we played around with our shared file system looking to see it as what might happen if we used up all the file space or all the individual I nodes。

And of course， we discussed the standard properties of the UniX file system inherent in it being a multi use system。

 and thus requiring file ownerships and permissions。

 but also noting the availability of extended file system access controls or records。Following that。

 we discussed software installations， which， of course， is a topic rife for security implications。

 The separation of privileges by IVMs and containers。

 just like patch management and package integrity assurance are just some examples。

Talking a bit more about more to user fundamentals。

 we spend some time in class discussing different trust modelists， authentication methods。

 as well as how users might wish to raise their privileges， all of which can， of course。

 be abused and has inherent and obvious security implications。



![](img/7769e1757f9a9e83d63346bcf769ddae_5.png)

When we talked about networking， we illustrated the visibility of meta information in each layer。

 and we saw that simply by using TCP dumpm， we can view not only all the data on our host but also some of the data that is going by on the network。

Which of course， carries with it implications around what is possible if you on the same layer to network segment as an attacker。

We also talked about the physical nature of the internet and how the political landscape can shape what traffic is allowed to pass certain networks and whether or not the traffic can be inspected in transit。

After that， we talked about the DNS and of course， quickly realized that if you can control the zone。

 then you control just about every other aspect of the traffic。

 which is why attacks on the places where your name server records are registered it becomes so interesting。

We saw that the DNS is used for all sorts of side channels。

 providing additional information oftentimes with an authentication context。

 and we noted that unfortunately the majority of DNS traffic is unprotected and unauthenticated。

 but we did hit and some of the methods to remedy this， such as DNSec。

 DNS over TlS and DNS over H TTPS。Which gets us to H TTP。

 which we noted as the universal entry point across our networks。

We discussed how HETP nowadays is no longer just static documents。

 but codynamically executed both on the server and the client side。

 with all the security implications， and we talked about how outsourcing your traffic to say your CDN can have both security and privacy implications。



![](img/7769e1757f9a9e83d63346bcf769ddae_7.png)

Knowing how we can observe plain HDP text using TCP dump and thus seeing traffic on our network。

 we then talked about HDDPS and TlS to encrypt traffic and transit。

Leading us to authentication of the service via the PKI sitting on top of a surprisingly large number of certificate authorities。

And we briefly hinted at some of the force we encountered in the development of the Tella protocols。

When we talked about SMTP， we covered email as an attack vector itself， spam and phishing。

 which uses or other app uses how the simple mail transfer protocol works as it was developed in an era of open networks from where we then go to discussing the use of start Tls and the opportunistic approach to encryption it uses and again the various related DNS records attempting to provide another layout security and authenticity。

 not included in the original protocol。In class， we then talked about developing tools。

 writing code and programming in assessment context where we can utilize automation as a protective mechanism。

 but need to be aware that choosing the wrong tool may lead to critical security issues。

 requiring us to understand our languages and frameworks and striving to reduce our attack surface by focusing on simplicity。

 since inevitably all code we write will include bugs and we need to be careful not to introduce security vulnerabilities as we deploy our automation。



![](img/7769e1757f9a9e83d63346bcf769ddae_9.png)

When we talked about disaster recovery and monitoring， the connection to system security is obvious。

 as some of the disasters we have to prepare for include security breaches。

 But on a more general note， of course， any data loss is a security failure we talked a little bit about malware that may infect the backup system or the backed up data itself and brush upon the concept of encrypting data at rest as part of our backup mechanism。

In a monitoring context， it is obvious that our ability to detect undesirable events are critical to system security。

 and our defense capabilities， and we need to remain aware of the sensitivity of the data we are logging。

 as this may contain passwords or other confidential or otherwise private data。

Which may have implications on your ability to outsource monitoring to a third party provider。

Finally， in our last videos， when we talked about configuration management systems。

 we illustrated the user roles and service definitions which may allow us to provide more fine grain access controls and service profiles。

 but we also noted the inherent power and thus risk in using a configuration management system。

 where the CA theoryorem may have direct implications on the security of our systems。So yes。

 as promised at the beginning of the semester， we really did include some aspects of security in every single class。

And if you go back to the earlier videos after we have concluded our mini series here。

 you'll hopefully find a lot more ground that we did cover here as well at a lot of areas where you may now see further need to deep dive into the security related aspects。

As we found out， system security really touches everything， every topic， every problem we face。

 and every solution we develop。

![](img/7769e1757f9a9e83d63346bcf769ddae_11.png)

By wait。 So what is security anyway， I know。 Let's ask the dictionary。



![](img/7769e1757f9a9e83d63346bcf769ddae_13.png)

Of course， first of all， we find that security is defined recursively as well being secure。 So yeah。

 thanks a lot， collaborative international Dictionary of English。



![](img/7769e1757f9a9e83d63346bcf769ddae_15.png)

But okay， Webster down here has a better definition。Freedom from risk。

That's a pretty good tourist definition。Now， within a computing context， there's a bit more to it。

 though。

![](img/7769e1757f9a9e83d63346bcf769ddae_17.png)

Specifically， we see a good breakdown here in this entry。And you。Confidentiality。Integrity。

Authentication。Access control， non repudiation。

![](img/7769e1757f9a9e83d63346bcf769ddae_19.png)

Availability。Privacy。Physical security， operational security， personnel security。System security。

And network security。It also mentions that encryption is one of the methods we may use to achieve some security in some areas。

 which I like quite a lot because it's important to not equate encryption with security。Oh， and。

 of course， we shall note that theres a town called security in Colorado， population almost 30000。

 but。You know， that's really not relevant here。But okay， so this is actually quite useful。

In the next few videos will actually break down several of these important aspects。

 But I do want to go back to the first useful definition we had seen。Freedom from risk。

 This is the second time we're seeing this emphasis on risk。

 So perhaps let's go and see what risk is。

![](img/7769e1757f9a9e83d63346bcf769ddae_21.png)

Okay， so hazard， danger， peril。 that sounds about right。More specifically。

 risk is defined as a source of danger。A possibility of incurring loss。And that's really important。

 Risk is not a guaranteed disaster。 It's the possibility of something terrible happening。

But to assess the impact of a given risk， we then need to determine what specifically is at risk。

 there really is a number of things that we might be in danger of losing， such as access to data。

 such as in the case of ransomware， or might be concerned about the integrity of our data。

 worrying that somebody might have changed it。While we might worry about the availability of our data。

 think denial of service。Anything bad happening to our data might also bring with it indirectit consequences。

 such as the loss of your reputation， meaning you'll likely lose users and clients。 And， of course。

 money makes the world go round， and we might fear the loss of our sweet sweet dollar bills due to any of the above。

And in some cases， we might even be concerned about the physical value of certain things。

 And in the data driven tech world， that's an entirely different threat compared to the value of the data access or integrity。

But so you see that there are clearly different things that might be at risk。

 and each one is equally clearly put at risk and thus should be protected in a different manner。

So in order for us to make any progress in our F to secure something， we kind of have to。

As boring as it may sound， perform a risk assessment。I know。 I know。

 That sounds like a Turner could put you to sleep all by itself。 but stick with me here for a minute。

What do we mean by risk assessment， Well， first of all。

 we need to determine exactly what it is that's at risk。 As we just said， that it is we identify。

Would we want to protect our assets。Each asset has different threats。

 so let's go ahead and identify those for each。 That is。

 we need to determine for each asset just what exactly might pose a danger。

Each threat may manifest itself in different ways。 We call these ways vulnerabilities。

 I eat weaknesses in a system， a way to abuse a protocol， a tool or even a human behaviour。

But each of these vulnerabilities being exploited not a given and not each one when exploited necessarily leads to a complete compromise。

Which is why we need to determine， or at least estimate the probability of the damage。

 including whatever possible mitigations we may have put in place。For example。

 if we are concerned about data loss， but we have a file system that takes snapshots every minute。

 the probability of actual data loss somewhat reduced。On the flip side。

 we have to also consider what we do。When we do suffer for damage。

How do we recover What do we have to do to get back up and running。Do we have to rebuild systems。

 replace hardware， run ad campaigns to try to reassure our users of our trustworthiness。

All of this gives us an idea of how bad things might be if such a disaster were to happen。

 So then we need to go around the other way and ask ourselves。

 how much would it cost to protect against this threat。 Could we protect against this scenario。

 What if we had unlimited resources， What are the costs of mitigating strategies to put in place。

So with that cost calculation， we then come up with a few rough numbers。 The cost of a disaster。

 That is how much it would cost us if it were to happen。

 the probability of it happening and the cost of defending against the scenario。

And with these numbers， you can then make a fairly reasonable logical decision and determine whether it makes sense to invest in the defenses for the given scenario。

So in other words， the way we determine risk is to assess the likelihood of a threat successfully exploiting a vulnerability and the estimated cost or potential damage。

 both in the short and long term， you may incur as a result。And that's a risk assessment。

 And it sounds straightforward。 And sometimes it really is。 But， of course， oftentimes。

 it takes some practice to really identify all the relevant and eliminate the irrelevant factors here。

But the key takeaway here is that a risk is specific， quantifiable。



![](img/7769e1757f9a9e83d63346bcf769ddae_23.png)

And most of the time， when we are facing discussions around security in the abstract sense。

 and it's also too easy to form into the trap of only talking in a hand wavy kind of way about very vague theoretical problems。

There's a lot of fear uncertainty and doubt that can enter this discussion。

 So always keep in mind that in order to be able for you to address， mitigate or minimize a risk。

It needs to be specifically scoped， well defined。Only then is there anything you can do about it？



![](img/7769e1757f9a9e83d63346bcf769ddae_25.png)

So how then do we secure a system。 Well， the answer is， you can't。

 There's no such thing as a secure system。 since as we mentioned at the beginning。

 security is not a property of a system， and we rather need to be specific about what we mean。

So instead of trying to make a system secure， we can only minimize or address specific risks in a variety of ways。

We can try to close the attack vector。We can try to eliminate the vulnerability that allowed the threat to manifest itself。

We may try to reduce the attack surface， even if we can't eliminate the vulnerability or close the attack vector。

Or， and this is another powerful mechanism that very often overlooked。

 we can change the economics for the attacker。Because remember。

 just like we perform a cost benefit calculation when assessing our risk。

 So do attackers perform a cost benefit calculation whether it is worth their time to attempt to exploit the given vulnerability。

 for example， And if we can raise the cost for the attacker。

 then they may pursue a different venue or be forced to retreat altogether。

But in order for us to be able to do any of the above here， we need to not only understand our risk。

 We need to understand our attacker， their motivation， their goals， as well as our own capabilities。

That is， we need to develop and utilize a threat model。

 which is a formal way of assessing just who exactly is likely to try to pursue which attack vectors to which ends。

But more on that in our next video。Thanks for watching， Tith。



![](img/7769e1757f9a9e83d63346bcf769ddae_27.png)