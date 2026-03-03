# 哈佛大学《CS50x2024计算机科学导论｜Introduction to Computer Science》（中英字幕，豆包翻译） - P10：-10-CS50x 2024 - Lecture 8 - HTML, CSS, JavaScript - GPT中英字幕课程资源 - BV16k4y1X7KZ

![](img/e2286cf0b31bc83edb13a8b2f669b689_0.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_1.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_2.png)

All right， this is C S 50 and this is already week 8。

 but this is a CSs 50 bingo board from one of your classmates at Yale。

 Shohanna kindly sent this to us and she's apparently been taking close notice of certain expressions that I apparently tend to say quite a bit。

 some of which I'm aware of， but not all of them and the idea here she described it is that if and when I say any of these expressions on the screen you can sort of draw a line through that box and if you get five in a row you win a fabulous prize it seems only fair then if we maybe give away some cookies today if and when I actually do say five such things in a row perhaps it'll be all the more motivation to keep a wrapped ear against everything we're talking about today So if and when that happens。

 feel free to just yell out bingo and then police Carter during the break or after class for adjudication。

 right So today ultimately though week8 is about the internet and in turn， how it works。 and in fact。

 how we can start building software on top of it。 So up until now， of course we've experiment。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_4.png)

With scratch spent quite a bit of time with C only really spent a week plus so far on Python and about the same on SQL。

 but ultimately we're going to come full circle next week and tie all of those languages together。

 but we're going to do it in the context of the web and in fact to do that we're going to introduce three different languages today but only one of which is a proper programming language the other two or more about presentation markup languages so to speak and those languages are HTML and CSS commonly used in conjunction some of you might have done this middle school high school even if you ever made a personal website of sorts and JavaScript。

 a programming language that is very commonly used in the context of browsers to make interfaces that are all the more interactive but it can also be used server side and what you'll find that it's our goal this week like last week like two weeks ago is really to teach you ultimately how to program how to program procedurally and also with elements of what we'll call functional programming object oriented programming concepts that you'll explore more if you pursue more programming or higher level。

😡，Classes，But at the end of the day， you will exit this class， having learned how to program。

 particularly in a context that's very much in vogue nowadays， be it for the web。

 or be it for mobile devices and all of the ideas thus far will be applicable as we now begin to build on top of the Internet。

 So what is it。 So back in the late 60s，1970s。 It wasn't much of anything。

 This isn' an early diagram depicting a few access points on the West Coast of the United States。

 which represents what was originally called ARPpanet。

 And this was a project from the US Department of Defense to begin to inter network computers by enabling them to exchange data using what's now known as packet。

 packets of information back and forth。 wasn't too long before East Coast was eventually connected through Mit Harvard and others。

 And nowadays fast forward to present day， just a few decades later。

 everything it would see is somehow interconnected either with wires or wirelessly。

 But how do you actually get data from any of these points to any of these other points or all of the points that now exist。

 But let me stipulate for today's purposes。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_6.png)

That the world nowadays is filled with routers， simply computer servers whose purpose in life is to route information from left to right。

 top to bottom， geographically so to speak to just get data from point A to point B。

 but typically you're not gonna have a direct connection between point A and B。

 you might have C D E In other words， you might have many different servers between you and someone else。

 So if you have a friend at Stanford University and you simply send them an email while odds are that email is going be put inside what we're soon going to call a packet。

 and that packet might actually pass through the hands so to speak。

 of any number of routers typically more than one or two but typically fewer than 30 such routers。

 and it's up to the the IT administrators of the world to figure out how to route data between these servers and we have software nowadays that dynamically figures out the best path。

 It's not necessarily a straight line as it might be in the world of mathematics。

 but hopefully it's the fastest way to get data from point A to point B。 So the teaching fellow。😡。

Thanks to Zoom kindly put together in years past a demonstration of this。

 whereby each of the teaching fellows or Ts that you see on the screen here consider representing a router that is a device on the Internet that's pers purpose in life is to get data North south east or west between two points ultimately。

 And if we assume that Phyllis， for instance， wants to send a packet of information to Brian appear here at top left from bottom right。

 it turns out that by design， the Internet can send that data over any number of routes。

 it can go up into the left， it can go left and then up， it can double back a little bit。 Again。

 it's not necessarily a straight line。 And this is a feature not a bug。

 The intent of the Internet early on was to be able to route around down server。

 So if one router is overwhelmed。 or if one router is offline。

 the Internet can still adapt dynamically and just route it some other direction。

 So here for instance， is one representative route that our packet might take thanks to the team。

🎼The。🎼爸。🎼火火说。🎼Yeah。SoMy thanks to the team。 and if you never if you've ever used Zoom before。

 you know that you don't often see exactly the same layout that someone else sees。

 So it took us forever to actually get that right because no one actually knew to whom they were necessarily passing it。

 But if all of those Tfs and Ts represent routers。 Well， what is it they were handing。

 What is it that Phyllis wanted to send a Brian I called it generically a packet and a packet is like a generic term for some amount of information。

 but it's kind of analogous to an envelope in the real world if you're still in the habit of sending letters or postal mail you typically put your information inside of an envelope such as this and then you hand it off to the mail carrier you drop it into the mailbox and then humans in the case of the postal service actually get it from point A to point B。

 but Hoar goes through different cities in different countries even so you can think of that as roughly analogous to these things called routers。

 But the technical term for what it is the Ts were just doing is they were implementing a protocol that we know as TCPlash IP And this is actually probably a pair of acronyms that you've probably seen maybe on your Mac PC。

Your phone even if you haven't really thought much about it。

 but this is actually a pair of protocols， two protocols that the Internet generally uses nowadays and has for some time to get data from point A to point B。

 And let's consider each of these have。 So you have a sense of what it is the Internet is doing when you do send an email or do anything else。

 Well， first I stands for Internet protocol。 and you've probably even heard this in popular media since a lot of humans are indeed familiar with this notion of I。

 and they associate it typically with I addresses as you might So I'll stipulate for today that every computer。

 every internet work device in the world has an I address and Internet protocol address similar in spirit to like buildings in the physical world Here we are at 45 Quincy Street。

 Cambridge Massachusetts， USA 021，38 USA like that is a unique string theoretically that uniquely identifies this building similarly in the world of computers。

 we use a simpler mechanism just numbers of this format that。Uniquely represent computers。 Now。

 that's a bit of a white lie because there's actually a way to share I addresses and within your home。

 often within your dorm or your apartment， you'll actually have what appears to be the same IP address is your roommates or family members。

 But for now， let's keep things simple and assume that every Mac。

 PC and phone in the world has unique I address that's formatted like this number dot number dot number dot number。

 Each of these number signs represents a value between 0 and 255。

 And even though we haven't played around with this kind of arithmetic in some time。

 if each of these placeholders is 0 through 255， how many bits are being used to represent each。

Number。Think back to like week 0， week 1。 Yeah， so 8， in fact，8 B in total or 1 B。

 So I P addresses are generally 4 B or 32 B。 And the other math we kept doing early on is if you've got 4 B or 32 B。

 That's a maximum of 2 to the 32nd power total number of values， How many I addresses can you have。

 It would seem maximally in the world。EnEnough， actually。

 not enough would be a better answer nowadays， but roughly。

4 billion was the rough math that we typically did anytime2 to the 32 was involved。

 But it turns out with all of the humans and all of the devices， servers， clients， PCcs， Macs。

 phones and everything else。 Internet of things devices nowadays， even4 billions not quite enough。

 So the world is gradually in the process of transitioning from this format。

 which is technically IPV4 version 4 to IPV6， and then the world of IPV6。

 we've actually bumped things up from 32 bit to 128 B。

 which is a crazy number of possible permutations，2 to the 128。

 So you'll gradually see that over time。 But those are a lot messier of a format because there're so much larger。

 So we'll use the more commonplace ones IPV4。 Now， just to get into the weeds briefly。

 this is some ASciI art。 that is someone wrote this up decades ago in a text file to represent the layout of one of these packets。

 So think of this as like the digital representation of this here envelope。

 And even though we won't get。So the weeds of what this represents up here you just have some value saying that this is byte0。

 this is byte 10， this is byte 20 and this is byte 32 but zero indexed。

 So that is to say that this is just kind of an artist's reition of a grid of bits top to bottom left to right and what's going be interesting for us today is not most of these fields。

 there's a whole bunch of information that's encapsulated inside of any one of these packets。

 but we'll focus initially on these two source address and destination address。

 maybe the most important thing IP does is it standardizes how what you put so to speak on the outside of these envelopes It says that every computer is gonna have a unique address of that form。

 something something something do something And so just like in the real world if I want to send this packet from Phyllis to Brian and suppose that Brian's IP address is a number like very simply1234 what Phyllis would do is put that I address in the middle of this envelope just like you would address a。

In the real world。 but so that Brian could reply to her if only to confirm receipt。

 she's also going to put in the top left of this envelope virtually her own IP address。

 which for the sake of discussion is maybe5。678 in practice they won't be as pretty as that。

 but it's the general idea So you have a source address from which it's coming and a destination address to which it's going and that's what IP does it sort of standardizes in addition to a bunch of other numbers and values that need to be in this envelope too。

 it really just mandates that computers on the internet it minimally provide a source address and a destination address so that the envelope can get from point A to point B。

😡，That's not quite enough because it turns out。 And if you saw the bloopers from the TFs Zoom session there。

 you would see that it's very common not only for humans to physically drop an envelope like that。

 And frankly， even in the real world for mail carriers to like lose mail。

 occasionally undelivered to recipients。 And so it turns out that I alone is not enough to guarantee delivery because sometimes the packet just might not get to its destination more technically that might happen because like the router is overwhelmed it only has so much memory。

 it only has so fast the CPU， and if it's receiving way too many packets because so many people are on the Internet at some moment in time。

 it might just kind of get overwhelmed and metaphorically drop certain packets in the sense that there's just not enough room in its memory to keep up with the traffic。

 So the effect for the sender is that the packet just doesn't get through。

 And so there's this other protocol TCP that humans typically use in conjunction with I via their max PCs and phone。

That does a couple of other things for us。 One， it guarantees delivery or really guarantees delivery。

 and it does that actually， by doing this。 It does that by having Phyllis write on the outside of the envelope。

 not just the source address and destination address。 but also what we'll call a sequence number。

 So for instance， this would be packet one of two that she might be sending to Brian。

 So maybe in like the memo field， she could write one of two。

 And then if she happens to send a second packet to Brian， she might write similarly。

 a source address and destination address， but she might write two out of two。 because now。

 logically， if Brian only gets one of these， like that sequence number is enough information for him to know。

 Wait a minute， I need to ask Phyllis to resend number one， or maybe resend number  two。

 if both of them don't get through。 I mean， honestly。

 that's probably when Phyllis hits reload or resends the email。 But in general。

 the sequence numbers help with guaranteeing delivery。

But if Phyllis and Brian are each representing computers in this story。

 they can be doing different things。 They can be doing email， chat， video conferencing。

 direct messaging or any number of services on the Internet nowadays。

 So TCP gives us one other feature namely port numbers Because when Brian receives that envelope。

 assuming he's indeed a computer， how does he know that what's inside of that envelope is indeed an email versus a direct message versus like a little bit of video versus sound versus any other type of media ideally。

 the outside of the envelope would have a bit of a clue for him that indicates this is the type of data herein or more specifically。

 this is the program really that should open this envelope， the email program。

 the video conferencing program or whatever else。 So what Brian what Phyllis would typically do on the outside of this envelope lastly。

 in addition to the source address destination address and the memo field， the sequence number。

 she would。Also write a port number。 And it turns out two of the most common port numbers in the world of TCP are these two 80。

 which represents the web。 that is to say something called HttP。 more on that today。 or Https。

 which most everyone nowadays probably knows means secure。

 So it's some kind of secure version of H TtP。 And that number happens to be 4，4，3。

 There's no mathematical significance of these， they're just kind of arbitrary。

 but humans decades ago decided to standardize on these numbers。

 So what it means for Phyllis is that on the outside of her envelope。

 she should generally put a colon after the destination address。

 And then the number of the port that she wants to receive this packet。

 So if she's actually not sending an email， but maybe making a web request。

 And Brian is a web server and Phyllis is a web browser， she would write colon 80。

 or if she's using H Ttps securely， we would change that 80 to a 4，4，3。

 There's other stuff on the outside of that envelope， In fact， just like with I。

 there might be fields that look like this。 But just to give you a sense of。which is a TCP packet。

 you'll see that indeed sequence numbers are actually really big。

 They use all 32 Bs of this part of the picture， which is to say that generally computers are sending way more than one packet or two they might be sending dozens。

 hundreds， thousands even depending on the size of the data in question and there's some other features there'rein。

 including sourceport and destination port destination port is the 80 or the 443 that I mentioned earlier。

 but long story short Phyllis also gets to pick a source port to uniquely identify this particular request。

 but more on that another time for now， just know that TCP is the pair of protocols that the internet uses to get data from point A to point B IP standardizes how the addresses work and TCP guarantees delivery with those sequence numbers and also helps the servers like do more than one thing。

 helps some multiplex so to speak among email web video conferencing by using those port numbers。

The end of the day， everything， even now weeks into the class。

 it all boils down somehow to zeros and one or in turn， numbers。

 as we might think of them in this case。😡，Questions on any of these。Building blocks thus far。

Questions on any of these。Now， all right。 Well， on the outside of this envelope are just some arbitrary numbers。

1，2，3，4，5，6，7，8， That's obviously not what you and I in the habit of typing when we actually visit like websites。

 for instance， you and I are generally in the habit of typing Harvard E or Yale E or Google com or the like otherwise known as domain names。

 But your Mac， your PC has to at the end of the day， address those virtual envelopes。

 Aka packets with actual I addresses like there is no room for words。

 letters of the English alphabet in those pictures that we showed on the screen。

 it's just 32 bits here，32 bits here。 So it turns out on the Internet。

 There's another type of server that unlike routers which route information from point point B。

 there's another type of server that are all over the place。

 frankly in your home on campus in a company on the Internet more broadly known as DN S servers。

 domain name， system servers。 So what do these things do。

 This is just a type of server on the Internet whose purpose in life is。Answer questions of the form。

 What is the I address for this domain name。 So for instance。

 if you do pull up your browser on your Mac your PC or your phone。

 you type in Harvardedduu and hit enter what your device is designed to do。

 is to ask some local DNS server on campus on your mobile carriers network on your apartment or dorms network。

 what is the I address of Harvard Eu or Yale Edu， whatever you actually typed in hopefully there is a nearby DN server that will respond with a numeric address of the form。

 something that's something that's something that's something。

 and that's the number that your computer， your device will actually use on the outside of that virtual envelope。

 So you can kind of think as DNS servers honestly is fitting the model that we keep coming back to this notion of a dictionary or hash table more specifically whereby inside of a DNS server is essentially a dictionary。

 a two column spreadsheet or database table， if you will。 And in one column or domain names。

 Harvard Eu Yale E。Google co on the right hand side。

 right hand column are just the corresponding IP addresses， and that's it to be technical。

 if they're not generally called just domain names technically。

 it's a fully qualified domain name more on that another time。

 but domain names as we know them generally have different parts and we'll soon see how to tease them apart beyond the usual。

😡，Questions though。On what DNANS server's purpose in life is or how this might work。No。Alright。

 so like how does your Mac， does your PC， How does your phone know what these I addresses are？ Well。

 they don't come from the manufacturer this way。 And there's this whole hierarchy in the world of DNS servers such that your phone。

 your Mac your PC will generally ask the nearest DNS server。

 which is usually owned by your Internet service provider at home in your apartment or by your university or by your company but it's a hierarchical system and it's kind of a recursive design in that if that local DNS server does not have the answer。

 it's gonna ask someone bigger， more important than it。

 if that one doesn't know it might ask someone again recursively for it and throughout the world there's a finite number of what are called root servers that essentially know about all the do cos in the world。

 all of the do e use in the world， all of the whatever is in the world And so someone at the end of the day knows about those systems and in fact。

 if you've ever bought or in the future might buy a domain name part of that process is paying someone to associate an I address for you with the actual server that you're going。

actually be using so your final projects， for instance， in CS50。

 it's sometimes common for folks to actually buy for personal use their own domain name for a few dollars a year typically so you're sort of renting it more than you're buying it。

 but among the steps you'll go through if you ever do that is to essentially inform the world what will be the IP address or IP address of your particular domain name that you thought for say that calendar year。

😡，Allright， so how does all this get started Well， back in the day when you arrived on campus here at Yale。

 anyone or in the world， you would actually configure your Mac or PC to know the IP addresses of your nearest router of your nearest DNS server。

 So literally like someone would come to your home back in the day when signing up for Internet server and configure your Mac or PC for you Of course。

 nowadays， I don't remember anyone really touching my computer recently to configure it for me。

 it all seems to happen automatically， And indeed， there's this other type of server now in the world。

 Another solution to humanmade problem known as DHCP。

 And I think this is among the remaining acronyms for today， dynamic host configuration protocol。

 it's not that intellectually interesting to memorize that。

 But what DHCP servers do is answer questions of the form。 What should be my DNS server and router。

 unquote So nowadays， when you turn on your phone in the morning if if you actually powered it off if you。

Your laptop lid for the first day of classes or the like， your Mac your PC。

 your phone is essentially broadcasting a hello world message unbeknownst to you that's just asking the local network hey。

 what IP address should I use for my DNS server and for my router and hopefully Harvard or Yale or your apartment or your home more generally has a DHCP server nearby whose purpose in life is just to handout answers to that question And what these DHCP servers also do is they tell your Mac your PC your phone what IP address your device should use because that too is no longer manually configured。

 So this all just nowadays happens automatically And in the case of a campus like this youre at Yale。

 it's because at the very beginning of your visit to campus you did register somehow you probably logged in authenticated against your Harvard account or your Yale account And that is what enabled the DHCP server henceforth and forever to recognize your particular computer。

Answer those questions for you。All right， so that's it for how the Internet works。

 At least so far as we are concerned today， we're gonna now start building on top of it。

 And undoubtedly the most popular form of the internet nowadays is something called HTTP。

 that is the worldwide wide web， though most people don't really say it that in long form anymore。

 but H TTP is just another protocol that governs how web browsers and how web servers speak just like IP is a protocol that governs how computers address each other on the Internet。

 and how TCP governs how computers keep track of sequences of packets from point A to point B and also multiplex among different services using those port numbers。

 And to be clear， what's a protocol。 Well you know in in the human world， it's very common protocol。

 And I can't reach any of you。 But if I were to reach over and say hi nice to meet you。

 you presumably if we weren't5 feet apart， would extend your hand。

 we would sort of acknowledge in this strange cultural convention。 But that's a protocol。

 I know how to do it， you know how to do it， I'm initiating your responding。

 And that's exactly what's happening。All the time on the Internet。

 you have a client like me in this case that's initiating a request。

 you have a server like you in this case that's responding to that request or analogously like if you're in a restaurant。

 you might be the client sitting down at the table。

 you want to order food and there's a server that serves you that food after you have requested it。

 So computers really on the Internet are implementing that same paradigm。

 So when it comes very specifically to the web， which is different， of course。

 from email and video conferencing at all these other services on the Internet。

 the world wide web uses this protocol。 H TTP， which standardizes what goes inside of those envelopes in order to allow a web browser to request and receive information from a web server。

 So we've talked about really the lower level details up until now， the outside of the envelope。

 let's now look inside of the envelope when it comes to actual web pages that you might visit or soon today you yourselves might design。

 So H TTP stands for hypertext transfer。to， which is another mouthful that again just standardizes how we're gonna get web traffic from point A to point B from browser to server and back。

 Https is literally the secure version of that。 And what that means for today's purposes is that the connection is somehow encrypted。

 scrambled using very fancy mathematics so that it is very， very。

 very unlikely that anyone who intercepts your traffic， your packets between point and point B。

 We'll have any idea what is inside of those envelopes。

 They might intercept the packet itself digitally， they might try to open it up。

 but it's going to look like metaphorically like random zeros and ones on the inside when using Https because of what's called encryption。

 But let's look at some canonical URLs。 like all of us are in the habit of seeing these and typing these all the time。

 let's actually tease apart some of the jargon here。

 So here is an example URL with all of the usual components。 So here， for instance。

 the yellow This generally means， even though。Rarely type it。 and you rarely see it nowadays。

 This means the default Web the default page for the website。 Give me the the root of the website。

 so to speak。 So this is to say this represents a folder like the default folder inside of which is presumably the default web page。

 and we'll see what that means more concretely in just a bit。

If though you're visiting a more specific URL， we're going to henceforth call this a path。

 So slash something is representative of a path， maybe a file， maybe a folder。

 just like in the world of Mac PCcs and cloud services specifically you might sometimes be in the habit of visiting an actual file。

 somethinglash file do html。 nowadays this is kind of very 90s。

 early200s nowadays most web servers hide the file extension， the dot htl。

 even if it's there on the server。 it just looks a little messy nowadays sort reveals information that's not necessary。

 So very often you won't see dot html。 even if there is actually a file ending in that suffix。

 you might instead see folder with a maybe not a maybe a but that generally represents a folder on the server。

 and sometimes they're of course files in folder。 So all of the stuff you're probably familiar with on Max and PCs and even Google Drive and the like those same semantics exist in the context of URL。

 So there's a mapping between this URL and something。On a hard drive somewhere on some server。

 All right， what about the other parts。 So this is the fully qualified domain name。

 So the full domain name， even though you and I， when we say domain name。

 we typically just mean this example dot com， for instance。 So technically。

 the WWW is what we would typically call a host name A host name is like the name of a specific server that live somewhere in that domain。

 And this is just a human convention， even though most URL still probably start with Www do something。

 that's not strictly required， that's just a configuration detail and historically。

 this was just a kind of signal to less technical people in particular。

 when you would see a URL and print， that， oh， this is a web address。

 This is an address on that new worldwide web。 WWW just kind of connotes that。 But decreasing。

 do you see websites using this。 I mean， some of C50's own tool。 It's just C 50 do。

 it's just C 50 AI， because most of us are now conditioned。To know that okay， that's probably a URL。

 even though there's no explicit WWW。 And in fact， even if you type the WwW using tricks that we'll soon see。

 you can redirect the user from one to another， essentially remove the WW or added it to the server to the address bar in that their browser This thing here is called the tople domain and many of the domain names that you and I are on the habit certainly in the US nowadays or end in do co which stands for commercial Eduu stands for educationalgov stands for US government。

 But of course， there's hundreds of country codes to that by convention or two letters So UK for the United Kingdom Jp for Japan and two characters for every other country in the world。

 But even those have kind of been used in clever ways。 So do TV， for instance。

 is actually a country code that's been used by a lot of the English speaking world to represent television for TV shows and the like do AI similarly。

 does not actually mean artificial intelligence。It's a two character country code that has been used by the world nowadays to represent AI Ly for Biley and CS 50 do Ly2。

 that's a country code that has been that allows people like us to essentially buy domain names in that subdomain。

 But long story short， back in the day， there only used to be a few of these tople domains now there are hundreds of them。

 So I do think over time it's going to become a lot less regimented as it seems to be now as to what URLs actually look like。

 Lastly， beyond the colon slash slash here is the scheme or the protocol。

 and this just means that this URL is going to be securely accessing the server thanks to the HtTPS instead of HTTP。

mouthful， but just to get some vocabulary out there。

 questions on these here URLs that we've probably been taking for granted for years。Go。

Really good question。 Who approves dot E D U。 So you have to be an accredited educational institution to use do E D U。

 I don't recall the name of the organization that does this， but it can't be anyone on the Internet。

 You actually have to apply and be a seemingly legitimate educational institution that is not true of a lot of domain names like anyone can buy a dot com。

 Anyone can buy a dot org， a do net。 not a dotgov， for instance。

 And then different countries might have their own policies over who can be in what domain or sub domain as well。

Alright， so now that we have URLs so defined， there's a couple of verbs with which to be familiar in the context of the web。

 namely get and post。 And that is to say there's two different ways to request information from a server。

 that is there's two different ways to format requests that go inside of this envelope。

 and the default， dare say and most common one is just what's called get like literally the verb。

 the English verb get。 And we'll see in a moment， what this means exactly concretely。

 but just know that there's an alternative that we play with over time。

 known as post and whereas get as the no as the verb suggests is all about just getting information。

 post as the verb kind of suggests is more about sending information。

 So post is used when you submit a credit card because you're sort of sending potentially sensitive information。

 post is used when you upload like an image to a website or the like。

 But get is used when you're just clicking on links and visiting web pages and not really pushing any information to the server。

 So for today， will focus primarily。On get。 So what does this mean， when inside of this envelope。

 Probably unbeknownst to you up until now is our messages that look like this。

 These are H TTP messages that are being put automatically in these virtual envelopes for you by your Mac。

 your PC for your phone。 So， for instance， if you were to visit H T Tps。

 colon slash slash www dot Harvard dot E D U。You would hit enter。

 what your Mac PC or phone is going to do is put a textual message that looks literally like this inside of a virtual envelope。

 address it on the outside to the appropriate IP address for Harvardedu using your own IP addresses the source address and then hand it off to some nearest router。

 But inside of this envelope is enough information to the server to know what it is you want。

 So for instance， get is the verbs So you just want to get some information the information you want to get is slash。

 which I defined earlier is just the default page on the website HttPlash2 just means what version of HttP we're talking about you'll see nowadays in the wild 1。

1 you'll see you'll start to see version 3 over time。

 but Ill use for all of my examples here and you'll see inside of this envelope2 what we're gonna start calling an httP header a single line of text that literally tells the server like what fully qualified domain name it's looking for。

 And this is important only inofar as nowadays， generally on a server you might have。

Multiple websites being hosted。 This is not going to be true。

 probably of Google or of Microsoft or meta or massive companies like that。

 but it's definitely going to be true of smaller enterprises。

 even places like Harvard that don't need thousands of web servers but maybe just a couple or maybe just a few So in this case this ensures that when the server receives this packet it knows to server up Harvardeddu and not Yaleeddu or some other website that by coincidence might just be hosted on the same server because both Harvard and Yale or maybe paying the same cloud provider to host their websites。

 So do do dot just means there's other httP headers but notice the call in here is just giving us yet another one of those key value pairs。

 the key is host the value is wwwdu there again or those dictionaries that I claimed we would continue to see all over the place。

 what then comes back from the server if this is what's inside the message from browser to server what is the server send back ideally the server sends back a message that looks like。

This an acknowledgement of what versions being used， a status code。

 which is gonna be an arcane looking number like 200。

 It's going then have another HtP header of its own saying what type of content is in this envelope。

 ideal something called text HtMl。 that is hypertext markup language which we're about to see。

 and then some other stuff。 That's what's coming back from the server to the browser and we can actually now see this。

 let me actually go over to vs code here。 Let me maximize my terminal window just so we can see more at once。

 And let me go ahead and type in this command curl capital I Https colonlash www do Harvard slash So complete URL that's secure that's got the host name of www and curl just means connect to a URL。

 It's a command line program that comes with Linux comes with Mac Windows might have to install it individually。

 And it just lets me simulate being a browser。 It's let me simulate sending a packet like this。

 without。ing what the website actually looks like。 So no pictures， no no images， no text， no nothing。

 just what's inside of the envelope in terms of the server's response。 And here's mostly dot dot dot。

 the ellipsis Igraved my hand out earlier。 There's a lot of these key value pairs。

 But if I scroll up to the top， you'll see that 200 is the status code that came back。

 And you'll see that the content type is indeed text slash Hml。

 And there's a whole lot of other stuff here Clearly。 a lot of this is diagnostic。

 It reveals information about the server that might be useful generally。

s a more technical people than me at this point in the conversation or maybe my Mac or my PC or my phone For now。

 we can focus really on just the essence of this response， which is this here。

But here's where even these arccadeane numbers might start to get a little more familiar。 In fact。

 supposeuppose that I want to see this in my browser。 Actually， let me do this。

 Let me go back to Vs code here。 Let me open up incognito mode here。

 which generally is to give you private browsersing so to speak。

 And we'll talk more about this next week。 and that in incognito mode or private mode。

 you have no history。 you have no cookies。 you have no sessions， terms will define next week。

 I'm gonna use it again and again today to make sure that my browser essentially starting from scratch freshly so that I don't have anything in my history from previous examples。

 And what I'm gonna do actually， first is open up via my browser's menu， So-called developer tools。

 These are gonna look a little different in Chrome versus edge versus Firefox versus safari versus other browsers as well。

 But almost any modern browser， whatever your favorite is nowadays。

 has built into it developer tools。 and you might have to click a different button to access it。

 But these are tools for developer。

![](img/e2286cf0b31bc83edb13a8b2f669b689_8.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_9.png)

Like web developers that want to not just use the browser to go places。

 but use the browser to develop their own websites and web applications。

 Now there's a whole bunch of tabs here。 and I'm gonna focus on the network tab initially essentially this is like diagnostic information kind of like debug 50 like a debugger。

 but it's specific to the web and the web browser here So with my developer tools open and with the network tab open。

 I'm going go up to the URL bar and type in Https colon www Harvard edu So the exact same thing that I typed in curl a moment ago in my terminal。

 I'm just typing in my browser like I would normally do。

 And if I hit enter what's interesting about developer tools and let me go ahead and drag them to the top and maximize the window is you see all of the HttP requests all of the virtual envelopes that just went instantaneously it would seem back and forth between my Mac here and Harvard's own web server。

 and notice it's way more than a single。It's way more than a single request why For now。

 assume that each of those rows of output represents maybe a sound that was downloaded a video an image。

 some text。 There's all sorts of media and web pagess nowadays。

 and they might actually be spread across multiple files。 browserrowers are designed， if you will。

 to recursively get all of the media for a single web page and download it automatically with we humans only typing the URL itself once。

 But watch this at the very top of this output。 I scrolled all the way to the top of my network tab。

 I'll see a request， a row that represents my original request for the website。

 And if I zoom in here， we'll see that 200 means apparently okay。 So all is well。

 here's the contents of the website。 But there's a lot， In fact。

 if I look at the very bottom of the window， Harvard E to use is composed of 91 separate files it would seem。

 And that's just the landing page itself not to mention everything else we might click on ultimately。



![](img/e2286cf0b31bc83edb13a8b2f669b689_11.png)

But 200 okay is a good thing。 And odds are， you've never actually seen that because it's indeed okay。

 So let's consider actually what else could happen when you make these requests。 Well， here。

 for instance， is a shorter request。 supposeuppose that I omit the Www。

 just because it's faster to type。 And honestly you and I are almost always nowadays。

 I bet in the habit of just typing something com or something Edu。

 We don't bother typing the Https the socalled scheme or protocol。

 We' probably don't bother typing the Www。 you can probably think of someone in your life who's very like pedantic like that typing it out and it's full。

 but you don't need to do that typically for a couple of reasons。 if I， in fact。

 go back to V S code here。 Let me use curl again to connect to another URL that's similar Https colon Harvard ED。

 Now notice before I went to www。 and that's indeed Harvard's preferred URL if you will。

 But Harvard do E will still work。 but watch what happens when I hit enter。

 I'm gonna get back the contents of the virtual envelope that Harvard just sent back to me。

But it's not okay。 It's not 200 anymore。 It's actually this number here，301。

 which actually means something specific。301 actually means that Harvard's website moved permanently so to speak。

 in other words， Harvard， Yale， any server can configure itself to redirect the user to another place if you'd prefer to canonicalize on some other URL。

 So by default for branding purposes， most website still probably use www do something do something So Harvard is in fact doing this。

 and for reasons we'll talk about next week。 there's technical motivations to do so related to something called cookies and sessions。

 but for now that just seems to be a different status code。

 But if I now open up another browser window and I'll do this again let's say I'll do this again in how about incognito mode just to start fresh with a brand new window let me open my developer tools again。

😡。

![](img/e2286cf0b31bc83edb13a8b2f669b689_13.png)

Let me go to the URL bar and only type Https colonhar edu enter。 I'm still in my network tab here。

 And if I scroll to the very top of this notice the top road looks a little different now It's not 200 anymore。

 and I can click on that here and what I'm now seeing in yellow is that 301 aka moved permanently。

 So this is to say you've been able to do this all this time in your browser。

 if you care to you can see what's going on underneath the hood， if you will。

 check that off I think underneath the hood So as to just understand what's going on Now for users this is not that useful or intellectually interesting but for developers。

 this can be very useful for understanding things and also diagnosing problems ultimately So that's just a few of a couple of these status codes that can come back not just 200 but perhaps 301 there's also this one now which humans generally are familiar 404 it turns out 404 is what happens when。



![](img/e2286cf0b31bc83edb13a8b2f669b689_15.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_16.png)

File is not found。 so I can simulate that here。 Let me go back to V S code in my terminal window。

 Let me do curl capital i https colon www because Harvard prefers that Harvard cats like let's see if there's a page about cats within Harvard's website I'm pretty sure there's not and so indeed when I hit enter whole lot of output a lot of HtP headers but notice at the top 404 its file not found。

 Now what you see in the browser is going to completely depend on the website。

 some websites just display like an error message or a status code number and that's why you and I have seen probably in the world404 messages。

 sometimes they're much more user friendly sometimes there are links back to the home page to help you out。

 It's entirely up to the server， but that status code indicates that something has gone wrong And in fact。

 there's a whole bunch of these status code， some of which you'll now start to see in the class200 is okay and it's a good thing if you never see that because it means everything's working404 is not found301 is moved permanently。



![](img/e2286cf0b31bc83edb13a8b2f669b689_18.png)

These that start with three relate to redirect long story short。

 There's different ways to redirect the user from one place to another。 as we'll see。

 as we saw from that location header a moment ago，400s are generally bad。 It means that the user。

 the browser somehow did something wrong。 like 4 or3 forbidden。

 Probably means you're not logged in500 and500， you're gonna start doing next week。

 Most likely500 is like the Seg fault of the web， if you will。

 So there's no pointers or anything like that。 but 500 means that you wrote some buggy code is invariably we all will next week。

418 is in April fool's joke from years ago。 Some servers honor this。

 but someone wrote up literally this long technical document proposing a response that says I'm a teapot for a server even though it was just a joke on April 1。

 some years ago。 So sort of geek humor， if you will。

 So those are then the status codes that are available to us。 let me show you one other。

 has anyone been to this URL here。

![](img/e2286cf0b31bc83edb13a8b2f669b689_20.png)

So you have， all right。 So without spoiling here， let me actually， well。

 let me go into incognito mode here。

![](img/e2286cf0b31bc83edb13a8b2f669b689_22.png)

Someone's pulling it up on their phone clearly， safetyschool。org slashent。 Oh my goodness。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_24.png)

Another box gets crossed out today， too， I think， so how is that working。 Well。

 if we actually diagnose this with curl， let me go into VS code， curl capital I HttP。

 and it doesn't support Https because this is an old website。

 Col s safetychool org enter all this server does is return in HttP 301 response with a location that literally refers us back to Yale Eduu。

 And this is amazing。 someone has been paying for this domain name for decades。

 and all it does is literally this。 Now I know for our friends at Yale who are watching this。

 It's not quite fair to poke fun。 turns out Yale got us even better。

 So later today we turn the tables a little bit。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_26.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_27.png)

All right， so let's go ahead and take a look now at what it is that composes this web page when it is indeed 200 okay。

 let's introduce another language here and actual language called HTML。

 which is not a programming language， but is a markup language。

 which is to say it's all about aesthetics like mocking up a web page so that you can see the information you care about。

 But H is not gonna have functions and loops and conditionals and all of that stuff we talked about in week 0。

 It's just about presenting information。 So here are some of the building blocks of HTML。

 You're about to see really only two vocabulary words。 H。

 honestly is the kind of language that like you learn in like 30 minutes。

 and then you're just kind of often running with online tutorials。

 documentation and the like I still remember years ago。

 just learning it from a teaching fellow who kind of give me a crash course and then you kind of fill in the blanks yourself。

 because it has relatively few concepts associated with it， even though in fairness。

 it can take years to get good at making pretty。Websites today。

 we can get good very quickly at making functional websites。 So that artistic disclaimer。

 So in the world of Hl， there's really two concepts， tags and attributes。

 And those of you who have played with Webs growing up。 might be familiar with some of these already。

 So here is some sample H TML。 Hl is just a textbased language， you type it out with your keyboard。

 again， it's not a programming language。 So you can't call functions or write logic。

 but you can mock up a web page。 And this web page， for instance。

 is quite simply going to say hello title in its title bar or the tab and in the body of it。

 the big white box， it's going say hello comma body just to distill this really into its essence before we make more interesting pages。

 So what's going on in this Hl is enough detail that the server can display the information for it。

 So in fact， let me go ahead and reveal this as follows。 I'm going go over to V S code here。

 I'm going to create a new。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_29.png)

Here calledlled， for instance， let's just call it hello do Html。

 And I'm gonna really quickly whip up that same web page for memory。

 So doc type Html Htl Lng equals quote unquote E closed bracket。

 Open head open title hello comma title and then down here， open body。

 and you'll notice I'm actually not quite as fast as I might seem to be VS code is configured to automatically finish half of my thought for me。

 So when I open one of these things that we're gonna about to call tags。

 VS code is doing some of the heavy lifting for me。 And in here I'm gonna to do hello comma body。

 But I think this is the entirety of the file that I just proposed in the slide version thereof。

 So this is clearly now a text file in my code space within VS code how do I actually view it with a web browser。

 So if this file were created on my Mac PC， I could literally double click it and Chrome or my default browser would open up and show me this web page。

 But this file technical。Is not on my Mac PC。 It's in the cloud。 It's in your code space。

 So all that we need to do is actually turn on a web server to serve this file to me or to anyone else in the world。

 In fact， and the command we're gonna run now is literally called HtTP dash server。

 This is a piece of software that someone else wrote that we preinstalled in everyone's code space。

 And by running this， it starts a server whose purpose in life is to listen for HtTP requests。

 And as soon as it receives one from a browser， be it mine or anyone else's it will respond with the contents of that file。

 So let me go into BS code here。 let me reopen my terminal window。

 And I'm gonna go ahead and literally run HtTP server enter。

And now you'll see a whole bunch of output， most of which isn't germane to our discussion yet。

 But here is this URL here。 And if I hover over it。

 I'll see a little open URL pop up that I can click on or on my Mac。

 I can command click on the URL itself or and that will open up a new tab this folder。

 So this is gonna look a little esoteric at first glance。

 but this is what's called a directory listing like it's just literally the content of the folder that I'm in。

 So I'm in my codespaces default folder。 I deleted everything from last week and weeks prior。

 your folder will， of course， have many other things that you've created and kept。

 I have a source a directory that I downloaded in advance because it's got all of today's examples made in advance。

 but there's the file I just created。 And there's some other information here like the date and time at which I created this file and so forth。

 But you'll see that this is just a web page that lives at this URL here。

 and this is actually somewhat specific to code spaces the infrastructure we're using。

 But if I zoom in up here。

![](img/e2286cf0b31bc83edb13a8b2f669b689_31.png)

You'll see that I am effectively running my own web server at this weird looking URL that Github dynamically generated for us for me。

 and you'll have a different unique one as well。 you'll see that baked into this URL is actually a port number and they're doing some trickery normally I would have to access this web server at port 80 or 443 or even 8080 And the reason for this is because CSs 50 that is to say codespaces。

 the tool that we're using in the cloud is obviously itself already a web server。

 and it's Github's web server that's listening already on port 80 and 443。

 So if I want to run my own web server on their web server。

 I just have to pick another port number And so what you're seeing in the URL here is a hint of that by convention。

 the program I just ran HttP server does not try to use 80 It does not try to use 443 it uses 8080 by default。

 And that's why you see it in the URL here and underneath the hood that virtual envelope actually contains port 8。

Because this is not an official web server。 This is not Cs 50 dev or Github。

 This is little old me trying to serve up my brand new hello Htl file。 But the point here is this。

 when I click on this file。 I should see the results of my hard work。

 And there is a big white box otherwise known as the viewport inside of which are the only words in the body of page hellello body if I scroll up further you'll see in my tab here hellello comma title。

 So this maps back to the code we just saw Here is the just in my browser And it is what told the browser what to do visually。

 let's walk this top to bottom。 this first line here is's the document type declaration。

 honestly you copy paste nowadays it meansy browser I'm using version 5 of Hm odds are in some number of years。

 this line change over time to indicate different versions。

 for now this means I'm using the latest version of this H language。

 That's kind of anomaly because you're not gonna see this。



![](img/e2286cf0b31bc83edb13a8b2f669b689_33.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_34.png)

Poin again everywhere else， you're gonna to see a lot of less than signs and greater than signs or angled brackets。

 so to speak， but they're almost always going to be symmetric as follows。 This tag here。

 this is an Hml tag says hey browser here comes my H TM L。 And this is what's known as an attribute。

 So anything after the name of a tag is what we call an attribute and attributes can have values。

 Those values that are associated with the attributes with an equal sign and typically quotation marks。

 single quotes or double quotes as in this case。 So here we again。

 have that paradigm of a dictionary， key value pairs， they're everywhere in computing。

 even though the syntax obviously keeps changing， whether're in SQL or Python or now HMl。

 This tag at the very bottom now means hey browser， that's it for my HMl。

 So when you see a tag that looks like another but starts with a forward slash And you do not need to repeat the attributes that would just be very annoying to have to type it here。

 and here， we keep it succint。😊，This is what's known as a closed tag or an end tag that conceptually corresponds to this start tag or open tag。

 So there're sort of symmetric。 inside of that are two children。 so to speak。

 So there's actually a notion of like a family tree type hierarchy here or a tree。

 as we've discussed in data structures。 The H Tl tag per the indentation here has one one child called head and another child called body。

 Everything between the start tag and an n tag here is what's also generically known as an element。

 So this is the head element。 This is the body element。 bunch of new vocab。

 but it's not that intellectually interesting。 It's just jargon that we'll use here means hey browser here comes the head of my page。

 So like the very top of it， which generally for now means just the title bar。 In fact。

 this means hey browser， Here comes the。Hey browser， here comes the title of my page。

 and then here notice there's no more angle brackets。 This is literally raw text。

 and this is why we saw in the actual gray tab of my browser。 hello comma title。

 This means hey browser， that's it for the title。 This means hey browser that's it for the head。

 Meanwhile， down here。 Hey browser here comes the body of my main page like 90 plus percent of the page inside of the socalled viewport。

 the big rectangular region。 Hey browser here comes the body。 Hey browser sir that's it for the body。

 What is in the body in this super simple case。 literally just hello comma body。 That's it。

 So HTML really is that pedantic。 It just tells the browser， start doing this。 stop doing this。

 Start， stop， start stop and that's how it knows what to do top to bottom left to right when actually reading the code therein。

😡，All right， questions about any of this here。HtM code。Yeah， I'm friend。Be considered。6。

Say that again。Consider code interpreter Oh yes， I think that's fair。 though interpreter。

 question is， can browsers be considered HL interpreters， Yes。

 I don't think people tend to call it that interpretation generally implies that you're parsing something that's logical in nature。

 your functions， loops， conditionals and so forth。 parser is a term you might indeed hear much more often。

 A parser is a piece of software that analyzes code I analyzes text top to bottom left to right。

 breaks it down into chunks that have semantic meaning like the tags like the attributes like the elements that were thought talking about。

 And then it displays them In this case。 There's not as much to interpret in quite the same way。

But that's reasonable， nonetheless， yeah。The frameworks， the think is worth learning。T。这是 using。

Really good question with all the frameworks out there。

 should you bother learning HmL and writing it from scratch or using frameworks like something called Boottrap。

 We'll spend a few minutes today talking about that very framework。

 but even frameworks like Boottap absolutely assume that you know something about HTML something also about something called CSS more on that in a bit and better still something about jascript if you really don't want to know and understand these things that's when you reach for like a third-party service like Squarespace nowadays or Wix where you really just click and drag and drop and create websites that are at the end of the day。

 still HTML， but the developers at Wix and Squarespace have automated the process with a graphical user interface or GuI of letting you create it。

 but even then most web developers or even just business people who want to create their own website and they're not programmers themselves or technical folks they might still like to know a little something about HTML。

 CSS and ja because then you can open like the advanced settings and configure things and indeed that's a frustration that you'll tend to feel if you can't quite drop。

Down conceptually to that level。 All right， so just to make this a little more to give you more of a mental model for this。

 this indentation is not strictly necessary， kind of like in C where we care， we're style 50 cares。

 but not clang about what your code looks like， Similarlyly， browsers are pretty to。

 You can have all of this white space， all of this pretty indentation。 or you cannot。

 it's not gonna to care generally one way or the other。 However。

 this is certainly much more readable， but we'll see next week as we start to generate H automatically。

 it's not always important that the code you generate be pretty printed。

 but when you're writing in this format， it absolutely should be when you're collaborating or submitting to other people。

 So this， though， is what we would call a tree representation of this。 So here is that hierarchy。

 So if we think of the whole web page is what's generally known as a document。

 that document has a root element called the H element， which it's open Hl tag and its closed tag。

 It has， as I claim to children， the head tag。Has one child title。

 and then both of those leaf nodes or leaves to borrow the family tree vernacular have text nodes of hello title and hello body respectively。

 So this is gonna to be useful later today because it turns out with jascript an actual programming language we can start to modify this tree in the computer's memory or Ram and make the page dynamically change by essentially creating new HTMLl on the fly。

 even if that HTMLl didn't come from the server case in point。

 many of you use Gmail or maybe outlook generally speaking。

 you don't have to like reload the page to see if you've got new mail。

 It just magically appears at the top of the page in kind of a stack and it just keeps pushing old mail down。

 down， down。 Well that's gonna be the result of some jascript code updating this tree in memory and it has the effect of just dynamically generating more and more HTMLl that represents your emails inbox。

 for instance。Alright， so with that said， why don't we go ahead and actually try this out in a couple of ways。

 So let me go back to VS code here。 Let me propose to actually tweak my code here a little bit。

 So let me go into。

![](img/e2286cf0b31bc83edb13a8b2f669b689_36.png)

Let's see my VS code editor here。 Let me zoom out and notice down below actually all this time as I was clicking on hello do html。

 my http server program actually is outputting sort of the logs from a server。

 turns out anytime you request a page with a browser from a server。

 that server is probably logging a little something about you One。

 it's probably logging your IP address，2， it's probably logging the type of browser you're using Chrome or safari or edge or something like that。

 it's probably logging the operating system version you're using be it Windows or Mac or Android or ios or the like and maybe some other information as well。

 we won't dwell on this today， but there's a lot of information that will be logged about you。

 even if you are in incognito mode or private mode。 So more on that next week， And today。

 unlike all past lectures， even though by default， you see this in your own code space。

 you see here a ports tab， which for the most part is not that useful for us today but you will see。



![](img/e2286cf0b31bc83edb13a8b2f669b689_38.png)

This row here mentions HtTP server why because in my terminal， that command is still running。

 It is a server， and it's just there living to serve now by waiting and waiting and waiting for me to click on more of those links。

 and every time I do click on a link I'll see another line of output here。

 But it turns out that all this time in your port tab of Vs code。

 you can see all of the TCP ports for instance， that are in use。

 Now generally you haven't needed any of those， at least for your own work。

 but notice that HttP server is indeed listening on port 880 Cs 50 has some of its own customizations。

 And this is a bit of a geek Easter egg， but we presume to use port 1，3。

37 which perhaps those more comfortable。 We'll know what it means is like Lepeak。

 So it actually spells if you're cool and use a 17 and 23 so anyhow we chose that port number。

 but there are some conventions next week， we're gonna actually start using port 5000 which isn't in use at the moment。

 but long story short， you can see this stuff underneath the hood and indeed。

WeJust sort of peeling back some of these layers that have been there now for some time。 Well。

 let's go ahead and do this。 I'm gonna go ahead and create another terminal window using my plus icon down here in the console。

 Notice that at the right hand side of my screen。 I now have two bash shells bash is the name of your of your prompt。

 So to speak where the dollar sign is。 if I click on the first one。 there's H TTP server。

 It's still running。 And I want it to keep running today。

 but I'd also like to be able to run more commands in my code space。

 So I've simply created a second terminal。 And I can go back and forth by clicking it right。

 Let me go ahead now。 and copy hello dot Htl like that and create a brand new file called how about paragraphs do H TMl。

 And in paragraphs do H Tl。 I'm gonna first paste all of that。

 I'm gonna hide my terminal window now without stopping H TTP server。

 And I'm gonna go ahead and just create some paragraphs of text。 And in fact。

 let me go ahead and cheat here real quick。 I'm gonna go ahead and in my other window here secretly。

😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_40.png)

Open up a whole bunch of text so that I can grab some Latin like text to copy paste。 So now I'm back。

 And all I did was secretly copy paste a whole bunch of text。

 I'm gonna make a couple of changes to this file where I currently have just a title and a body One。

 I'm gonna rename this to paragraphs just so I can keep straight which file is which And down here。

 I'm gonna go ahead and paste in a big paragraph of text。 This is not actually Latin。

 It's sort of laum Ipsum text， which is Latin like random words that's meant to look like Latin and typpographers historically use this as sort of placeholders for actual text。

 But notice this is a pretty decently long paragraph。

 And so it's gonna make my web page a bit bigger。 So let me go back to my other tab where I have hello do Htl open from before。

 Let me click back and now notice in my directory listing。 I have a new file。 paragraphs do Htl。

 Let me go ahead and open that up。 invoila， there is a big paragraph of text。 Just for fun。

 let me create three。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_42.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_43.png)

Paragraph， I'm gonna kind of cheat temporarily and just kind of copy and paste two more times。

 But I'm gonna separate it with a blank line， as you would in like Google Docs or Microsoft Word for paragraphs in English or any language。

 And I'm going go back to my paragraphs。 Nothing has changed yet because H T TP。

 just like the exercise with Phyllis and Brian requires that we send packets back and forth。

 if we want to get updated content。 So I have to click my browser's reload button or hit control R or command R。

 depending on your browser or O S。

![](img/e2286cf0b31bc83edb13a8b2f669b689_45.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_46.png)

And notice that when I do that， I definitely get more text。But it just looks like one big blob。

 not three separate paragraphs。 What might your intuition be for why that is。

 even though I've clearly indented this and given blank lines between。Yeah。Yeah。

 so Html doesn't care about the white space or technically more than one white space。

 I can hit as many enters as I want。 All of them are gonna be ignored， except for a single space。

 It's gonna be normalized just a single space。 And general。

 this is useful because it means I can pretty print my Htl and indent things visually。

 even if I don't want to browser to indent anything manually for me。

 But here's where we're gonna need some more tags。 And it turns out the simplest fix for this problem is to use the paragraph tag。

 And for short， it's just open bracket P close bracket。 I'm gonna be a little pedantic。

 And even though VS code is being a little annoying because it's trying to autocomplete my thoughts。

 but I don't want to autocomplete just yet。 sometimes you have to fight with the text editor。

 So these autocomplete features are have upsides and downsides。

 But I'm gonna go ahead and put a paragraph tag， open and close around each of these paragraphs。

 And I'm gonna maintain my indentation just to keep it visually clean on the screen。

 And now I'm going to put this one last closed tag on this line here。And so it's a lot more verbose。

 but notice that it's effectively telling the browser， start a paragraph and a paragraph。

 start a paragraph and a paragraph and so forth。 So if I go back to my other tab。

 and I click reload now we have some semblance of what I expected。

 which is three separate paragraphs in this case。 All right， so that's the P tag。

 the paragraph tag P for short， because as you'll see many of these tags are abbreviated just because they're slightly faster to type。

 Let's do another example。 Let me go back to V S code here， I'm gonna copy this text。

 I'm gonna create a new file called how about headings dot H Tm L。 And I'm gonna to paste this。😊。

Close my terminal just to give me more room。 I'm gonna rename the title to be headings just to keep straight。

 which is which I'm gonna delete all of these paragraphs to make it。 actually， no， let's not do that。

 Let's keep the paragraphs。 but like a academic paper or a textbook。

 let's give these like chapter headings or section headings or the like。 Well。

 I could just do something like this， how about one， And then down here。

 I could put two and then down here， I could put3， but of course， if I reload this。

 It's not really gonna look as if I go back to this directory listing。 open up headings Hml。

 It's fine。 like it's not super pretty。 but it would be nice to give a little more prominence to these headings。

 And in fact， there's a bunch of tags for this。 I can use H1， for instance。

 for one really big heading。 and then let me close the tag over here and indent。 then down here。

 And again， whitespace doesn't matter。 So I'm gonna give myself a little bit of breathing room just so it's clear which of these is which for this。

 Maybe it's not chapter 2， but section 2。

![](img/e2286cf0b31bc83edb13a8b2f669b689_48.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_49.png)

So let me do H2 and then inside of this， I'm gonna go ahead and do two。 And just to be clear。

 I don't have to put these on their own lines。 I'm just doing that to be a bit pedantic。

 You can technically just do this and keep everything on one line。

 but I'll be consistent at least but other approach is fine。 And then down here。

 I'm gonna to use maybe a sub subse。 So let me delete this and do H3 and I'll just gonna write the word3 and then just to be neat。

 I'm gonna indent everything like this here。 So now if I go back to headings and I reload。

 I'm gonna get some default formatting。 It might not be the formatting you want。

 but it looks like it's big and bold， but in decreasing order。

 H1 is the biggest two is H2 is smaller。 H3 is even smaller and you can go down to like H6 and it gets smaller and smaller。

 And at that point if you've got like sub sub sub sub subsections of your book or paper like you're probably organizing it poorly。

 So they stop at some point there。 All right， Well， what else can we do in Hl。

 these things are omnipresent。 Let me copy this Hml and close that tab open my terminal and create a new file like。

Code list dot Hml。 And let's make a list of information。

 Let me just paste that Htl just to save some time today and change my title to list。

 Let me get rid of all of these paragraphs。 just to simplify things。

 So now I'm sort of back to where I began。 And then inside of the body of this page。

 let me go ahead and make a list like foo bar Baz。 If you've never heard these words。

 These are like computer scientists go to words like a mathematician might choose X。

 Y and Z by default Cs people tend to go with foo bar and baaz for historical reasons。

 So here's a list of three arbitrary words。 If I go over to my other tab。

 go back to my directory listing。 There's my new file。 Let's click on list do Hml same problem。

 It's a list， but it's not one after the other。 Last time， of course， we fix this with paragraphs。

 But you know， it'd be nice to make it a little prettier like a bulleted list。

 which are kind of everywhere these days。 So I could kind of try to simulate this。

 and you might be in the habit of doing this in some programs。 but of course。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_51.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_52.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_53.png)

If I go back to my other tab， reload， I'm just sort of making the problem worse， visually。

 but it turns out let me undo that。 there is an unordered list tag。 otherwise known as U for short。

 that I can put all three of these words in an unordered list。

 let me go ahead and indent everything consistently。 But to have three items in this list。

 I actually need another tag a list item tag。 And I'm gonna go ahead and add that tag there。

 list item here and there and then another list item tag here。

 And here's where of it's a stylistic choice。 I could move fo and bar and ba onto their own lines。

 but this is gonna start to get excessively tall like too much white space。

 So reasonable people would agree。 but this feels a little more readable to me。

 So I'm gonna leave it as for such， go back to my other tab。 And now when I reload。

 you get a nice bulleted list by default and you see these all over the web。

 What if I want to have a numbered list that is to say ordered list and instinct for changing these bullet。



![](img/e2286cf0b31bc83edb13a8b2f669b689_55.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_56.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_57.png)

It's to numbers。So OL is good instinct and indeed sometimes HTML makes perfect sense。

 as in this case， if I change UL to OL， I don't have to manually number anything because when I reload。

 it's going to use Arabic numerals automatically for me like this top to bottom And what's nice about this is if I go in and I insert things in the middle。

 I don't have to manually renumber things the browser is going do the counting for me。

 And if you're doing an outline， you can actually specify whether you want 1，2。

3 or ABC or I doublei triple I or so forth， there's different numbering systems you can use。

 but by default， we get our decimal numbers here。😡。



![](img/e2286cf0b31bc83edb13a8b2f669b689_59.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_60.png)

Alright， I'm going quickly， but like， it's hard to get too excited about like bulleted lists and such。

 But any questions on these tags thus far。Well， by design， try to escalate quickly momentarily。

 all right， so how about just a few other tags to make things more visually interesting。

 Let me go ahead here and cheat by opening up a file that I made in advance。

 that's going demonstrate what a table looks like。 So here。

 let me open a file that I brought with me called table Hl。 And because I brought it with。

 I actually included a comment at the top。 And in fact。

 if you download today's files from the website。 you'll see that they're generally commented like our C code and python code was。

 it's a little weird。 But here is the syntax for a comment in Hm。

 It's a less than sign or open bracket， then an exclamation point， then dash dash to hyps。

 then at the very end of the comment， it's almost the opposite。

 but not quite it's hyp hyphen close bracket instead。

 Why these symbols humans probably decided years ago that there's no way someone's gonna accidentally type rather intentionally type those characters visually。

 So let's use them for comment symbols as well。 If you really want to type them。 there is a way。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_62.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_63.png)

Around that。 But here is my table title。 And here is just kind of a little maybe a guessing game。

 Here is a table tag with a T R child。 And here's the closed child。

 And then is theres a bunch of TD tags。 So I'll give you T R stands for table row。

 TD stands for table data， Aka cell to borrow language from like spreadsheet software。

 Does anyone want to guess what this file is going to look like if I open table do Hl in my browser。

😊，What is this reminiscentopia？Yeah， so it's like a numeric keypad from like a phone。 for instance。

 if you're dialing someone's number manually。 So let me actually go to my other tab。

 go back to my directory index。 there's table do hl。 And it's not going look very pretty。

 but it is structured in the way I might expect。 And in my browser。

 I'm going go ahead and just zoom in command plus or control plus will generally do this。

 It does look like it's laid out tabularly in rows and columns with everything very nicely aligned。

 So that might be useful as we get to larger and larger datas。 Let me go back to v S code here。

 Let me create one more program。 for instance， in how about code image do Html。

 and just to save time。 let me paste that code and also let me secretly copy over a file that I brought with me that we've seen in the past。

 I me close my terminal。 I'm going delete everything about tables from this file。

 because I'm just saving time by copying and pasting。 but I'm gonna rename the top to image。

 I'm gonna get rid of the comment because it's no longer applicable But in the body of this page。

 I'm gonna link to maybe an image of the。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_65.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_66.png)

Bridge by the river， so I'm going to use an image tag IMG for short。😡。

And now it's obviously not gonna to be sufficient to just say image tag because like what image。

 So here is where attributes again get useful。 This attribute earlier。

 though I didn't quite highlight it seems to indicate that this page is largely in English as have been my past ones。

 the Latin one aside that attribute on the Hl tag is useful for like browsers that have Google translate or something similar built in and also it's useful for Seo search engine optimization。

 because when Google and Bing sort of automatically crawl my web page in the future。

 they'll know what language I intend for most of the content to be in。

 which might help them index it and keep track of it for search results。 So here for the image tag。

 I'm similarly gonna to need an attribute。 And that attribute is called source SRC for short。

 And what you put inside of its quotes for its value， double quotes or single quotes。

 is the name of the image that you want to include。 And I include it in advance in my codespace。

 a file called bridge do ping from week 4， when we played around with images。 And if I go ahead now。



![](img/e2286cf0b31bc83edb13a8b2f669b689_68.png)

And go to my other tab。 go back to my directory index and zoom out。

 you'll see now not only bridge do ping portable network graphic， which I manually copied in。

 but also image do hml， which I just created andvo here is that same week' bridge。

 It's a little too big for my browser window。 Well see in a little bit how we can fix things like that。

 But indeed， that's an image that's now embedded into the page。

 But notice if this image were ever broken。 or if I had visual difficulties such that might have screen reader software for accessibility installed。

 It's generally good practice to also make sure that pages are accessible as possible。

 And so some tags have additional attributes you can include like for an image here。

 there's actually an alt attribute that specifies alternative text to describe this image。

 This is what a human would see if they have a very slow interconnect connection And before the image downloads。

 they can see this alternative text。 or if I'm'm blind。 I need a screen reader。

 I could have these words recited to me verbal。

![](img/e2286cf0b31bc83edb13a8b2f669b689_70.png)

By providing this clue。 so it's best practice to include this like photo of bridge so that all users can know what they're looking at clicking on or the like。

 So keeping that in mind too。 Allright， let's do one other piece of multimedia。

 let me close these two tabs。 Let me open my terminal and open up a file called video do Htm。

 let me go ahead and copy secretly a file called videomp4。

 which is a common video file format and close my terminal window and go ahead and paste in here some HTML from before。

 but let's now embed a video file as you might if making a videobased website。

 let me rename this one to to video， let me get rid of the old comment which is not applicable。

 and it turns out video are almost as simple。 there is a video tag。

There is a bunch of different attributes we can put on that， but I'll come back to that in a moment。

 but videos because you might want to have like high resolution。

 low resolution depending on people's bandwidth because these things can be big。

 they actually have source children and confusingly， it's actually S O U R C， not SRC in this case。

 and even more annoyingly， it takes an attribute called source SRC。 This is not good design。

 But this is what we're stuck with videomp4。 and then the type of this video。

 which you could generally look up if the browser doesn't recognize it videolash MP4。

 This is what's known as a content type or mind type。

 and then I can actually configure this and you would only know this by taking a class reading a book looking at an online reference。

 I can actually add some video controls to the website like a play button and a pause button and all of that。

 I can mute the video by default。 And so this is just gonna modify the behavior of this video tag。

 but this is anomalous for some attributes。 it just doesn't make sense to have values。

muted it sort of says all the information we need。 you know， we could do quote unquote true。

 but humans decided years ago not to bother with that。 So some attributes do not need value。

 So you do not need equal signs or quotation marks and you would only know this from say documentation Allright let me go back to my directory listing。

 let me go back here to this here you'll see that there's now not only videomp4 but also video do html。

 I hope you'll forgive me for this。 there's at least no sound， but when I click on this page。

 it embeds a video here which I can then click on the controls for and you see some short video file playing here albeit without sound。

 All right none of that let me go back here to my VS code。

 and let's play around now with what the web is really known for which is hyperlink。

 So hypertext markup language Hml is all about linking one site to another one page to another and nothing we've done thus far is interactive beyond this own video controls So let me go ahead and do this let me go。



![](img/e2286cf0b31bc83edb13a8b2f669b689_72.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_73.png)

Into for instance， my let me go into VS code here。And let me go ahead and create the simplest of files that just allows me to click on a link。

 So let me go ahead and copy this to save time， open up VS code's terminal window。

 code a file called link do hml。 I'll close my terminal， paste this code rename video to link。

 get rid of the actual video tag and in the body of this page， let's do something simple。

 like invite people to visit for instance， Harvard period All right。

 if I now go to my directory index and reload will'll now see link html and of course。

 this doesn't really do anything useful because I literally just use English text All right。

 well what if I do what you're in the habit of doing on social media and various websites。

 visit Harvardedduu period let me go back to the webage reload the text changes。

 but it's clearly not automatically linking like I still can't click on this。 All right well。

 maybe it needs to be wwwhareddu let me go back reload All right， still not autolinking。

 let me go over。

![](img/e2286cf0b31bc83edb13a8b2f669b689_75.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_76.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_77.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_78.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_79.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_80.png)

HereAnd maybe it needs HtB colon slash and a slash at the end。 like a full URL。 Let's go over here。

 reload。 and it's still not working。 Like I can highlight and copy it。

 but that's not very user friendly。 So what's going on。 Well。

 all of today's social media sites when you copy paste a URL。

 someone at the server side wrote code be it in Python or jascript or anything else to automatically notice and detect URLs and then wrap them with HMl tags that actually hyperlink them。

 So what I actually need to do here is this。 I'm going introduce an anchor tag a for short。

 the hyper reference attribute of which is the URL that I want to send the user to。 So H for short。

 I'm going close the tag， But then in between the start tag and close tag。

 I'm now gonna put the text that I want the human to see So it's a lot more verbose。

 But this is what websites like social media sites are generating automatically for you when。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_82.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_83.png)

Just detect with a pattern that you have typed something that indeed looks like a URL。

 Let me go back to VS code。 Let me go back to this tab here and reload。

 And now we actually see a working link。 And this is gonna to be super small。

 You're not going be able to see this quite well。 But if you hover over this link。

 you'll generally see in most browsers a little clue at the bottom as to where you're going to be directed before you click there。

 This can help if you're a little suspicious and might not want to click on the actual link。

 It's small on my screen， but hopefully more visible on yours。

 That's not generally the case on mobile in quite low the same way。 But notice that this very simple。

 primitive of anchor tags like this can pretty quickly be abused， unfortunately， in fact。

 let me go ahead here。

![](img/e2286cf0b31bc83edb13a8b2f669b689_85.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_86.png)

And go back to V S code and I could do something malicious like this。

 like actually trick someone into applying to Harvard instead of Yale by just changing the H to not match the text that the human is seeing。

 And if I reload the page here。 you'll see that it looks like I'm going to Yale。

 but notice super small bottom left hand of my screen。 It still says the real URL。

 but you can get even more malicious。 you can not just say Yale。

 you could literally say HDps colon s www Yale E s you can make it look like a real URL reload it。

 And now it's really quite malicious。 And this is representative of what you all probably know already as phishing attacks P I H IN G。

 whereby you're being socially engineered people are trying to dupe you into clicking something that leads you to your Paypal account typically so that you log into some bogus website now you've given them access to your account and you're out some money。

 It's this simple because of unfortunately， these building blocks of H TM L。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_88.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_89.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_90.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_91.png)

All right， with that said。Any questions on this？Now all right。

 How about just for one final flourish before snacks will be served。

 let me propose to introduce some final features herein。 it turns out。

 and I'll open some of these premade already let me open up Vs code and open up a file called meta zero Hm。

 has nothing to do with meta， the social media company。

 it has to do with meta data or specifically meta tags。

 it turns out that in the head of the web pages that we've written thus far。

 we've only had titles but it turns out there's actually literally a tag called meta that has a couple of attributes like name and content and this one here。

 it's a little arcane， but it's very common to copy paste these into the source code for websites nowadays because essentially this makes them mobile friendly instead of making the font。

 some default small size， it will take into account the width of the phone or the tablet and sort of scale the font proportionally。

 So there's some useful accessibility and user friendly tips like this。 There's other use cases。



![](img/e2286cf0b31bc83edb13a8b2f669b689_93.png)

For meta tagags like this。 Let me open a file called Me1 do Htl that I made in advance。

 Here are three meta tagags inside of this file。 They're using a property attribute with a content attribute as well。

 And this is a little more specific。 But nowadays to on social media when you copy and paste a URL into a message online and hit enter。

 you very often see a preview of that link， it' sort of automatically generated。

 it makes a nice pretty image and some nice fonts。 Where does that image come from。

 Where does that information come from from these meta tagags。

 Any web page can have meta tagags like this。 so that when this pages URL is copy pasted into social media sites or others。

 those sites know what preview to show to humans。 It comes literally from the values of these tags。

 So， for instance， this would create some user friendlyriend preview that says Cs 50 introduction to the intellectual enterprises of computer science and the art of programming。

 And in this case， it would show a picture of a cat as the default image for that particular page You have full control。

😊，As a web developer over those kinds of things。 Lastly， when it comes to features of Hm。

 let's go ahead and quickly reimplement Google if we made。

 So let me go ahead and create a new file here。Called search do H TMl。

 Let me copy paste some code to save time。 Let me go ahead and get rid of all of these meta tagags to make a different point with this one。

 Let me get rid of that comment， change this title to be say search instead and inside of the body here。

 let's do this。 I'm going introduce a form tag。 And now in the form tag。

 I'm gonna to create an input， a text input。 And let's go ahead and let's just say that。

 And now I'm gonna have a button that has let's say button that has a value of search。

 So super simple and not yet complete。 but let me go to my directory index and back。

 let me open up search do H TMl。 And I actually have the beginnings of a search form。

 an interactive form for the web。 But it doesn't actually do anything useful yet。 but let me do this。

 Let me go to the actual Google com。 Let me search for something like cat CAT T S。 And of course。

 we're gonna see。

![](img/e2286cf0b31bc83edb13a8b2f669b689_95.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_96.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_97.png)

bunch of cats here。 And we're gonna see that the search box was automatically populated at the very top of the page。

 Now， the URL that Google LED me to， even though I started at the very simple Google do com is actually pretty long。

 And I'm going frankly just delete anything I don't understand because I'm going to distill this URL to just this one here。

 It turns out that in URLs， you can also put user input in the form of key value pairs。

 So in any URL， you can actually have not only a path like we saw earlier。

 you can have a path with a key and a value prefixed with a single question mark。 And in fact。

 if you want to have two keys and values， you just interpose them with an ampersand instead。

 So this is to say there is a standard way in H Tml and really H T TP for sending input from a browser to a server And it's generally formatted like this。

 What this means is actually this。 let me zoom out， close that tab and open a brand new one。

 And let me manually go to， and I'll zoom in。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_99.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_100.png)

HttPS colon slash www do Google dot com slash search question mark Q equals dogs。

 Now it has to be Q because that's what Larry and Sergey of Google Fame decided two decades ago when they made Google itself。

 Q stands for query。 but they could have called that key anything they want。

 I'm gonna hit enter after zooming out。 And what you'll see is that I don't need Google do com to search for me。

 I can literally go to a URL of all of the dog search results manually。

 no one's normally going to do that that makes no sense but it does suggest how simple the mechanics of the web are。

 If you want to pass input to a server， you suffix the URL with a question mark key equals value Key equals value may be separated by these ampersands as I proposed。

 So what does this mean。 Well Google really did the hard part， the backend。

 the database They crawled the Internet and found all of these cats and dogs。

 but I can make the front end。 that is the user interface that still works for it。

 And I'm going to do this。 I'm going add an attribute to my form tag。



![](img/e2286cf0b31bc83edb13a8b2f669b689_102.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_103.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_104.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_105.png)

That specifies an action attribute of HtTPS， colon//www。google。com/search。😡。

And I'm going to specify that the method I want the browser to use is indeed get。

 This is inconsistent。 I've capitalized it as all caps before in Hml。

 you actually do it as lowercase。 but that's also the default。 So strictly speaking。

 I don't even need to specify that。 but I will just to be pedantic inside of my input， my text box。

 which used to look like this just a big white rectangle。 I'm going actually give it a name of Q。

 because I know that's what Google servers expects。

 And I'm also going to specify not just that for now。 Let me go back now and reload。



![](img/e2286cf0b31bc83edb13a8b2f669b689_107.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_108.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_109.png)

And it's gonna still look very simple。 but notice this。

 if I type in cats and click search in just a moment。

 I'm gonna be whisked away from my own codespaces URL。

 ending in search Html after zooming out and clicking search the actual Google com which prepopulates the URL with Q equals cats up top prepopulates this text box with the user's input。

 which is to say like the frontend of Google com is trivial as most every website It's as simple as these key value pairs and things like web forms like that。

 Now I can make this a little prettier。 And just so you've seen it。

 if I specify that the type of this input isn't text， which is the default， but is search。

 I actually get some nice features。 let me reload this now。

 And if I start typing in like dogs Now I get this little x to click， which clears it。

 So a lot of websites have that's a little bit of a nice city。

 if you don't know what you want the user to type in， you can actually be kind of explicit for them。

 And you can add a placeholder attribute that says。



![](img/e2286cf0b31bc83edb13a8b2f669b689_111.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_112.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_113.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_114.png)

Query or keywords or whatever you want to show them。 If I go back to the browser and reload。

 you'll see a gray out text that's not actually there。 it goes away。 if I type in bird。

 for instance but it's explanatory placeholder text for the user you'll notice that it wants to autocomple cats or bird or dog or anything I've typed before you can disable that。

 there is an attribute called autocomp whose value can be either on which is default or off which is can be explicitly specified and notice this too when I reload the page it's actually annoying in terms of user experience。

 before I can search for anything I have to move my cursor。

 I have to click in the text box and now it has focus so to speak it gets highlighted in some color usually blue that's not the best website like why are you making the users pick up their mouse or their trackpad just to click on the only thing they're gonna do anyway。

 So there's another attribute that's handy autofo which will just move the cursor there for the user So this is to say even a lot of websites don't do this There's a lot。



![](img/e2286cf0b31bc83edb13a8b2f669b689_116.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_117.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_118.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_119.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_120.png)

Funality that you can enable by just knowing the language all the more。 So with that。

 we now have a pretty useful feature。 In fact， heck， I can say this is Google search。

 change the value of that button， reload。 And now I'll go ahead and type in like birds enter and voila now we have a whole bunch of birds as well。

😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_122.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_123.png)

So that's a lot。 I think it's definitely time for a snack。

 so let's take a1 minute break for snack when we come back。 we'll make all of this look prettier。

right so we are back and it was brought to my attention during break that we were pretty darn close to clearing one of these rows and I will concede that your classmate。

 Darwin and Jude socially engineered me into saying one of the remaining squares that they needed and so I'm sad to say that bingo was declared during break。

 which Carter has already confirmed because I was tricked into giving a long answer to a short question so congratulations to those two I do dare say too that that whole bit with safetychool org probably isn't going over well in New Have so I'm pretty sure we can check off this box here。

 however as promised in fairness since we love them both equally thought it only fair to resume now with a look it perhaps one of the best Harvard Yale pranks that was actually on us with this two and a halfmin glimpse at how our classmates at Yale。

U praranked Harvard some years back if we could dim the lights now for this。🎼，や。the差。两个人。

This is for you， yale。hand the chip。送 down。あ3。しれ。It's gonna。Actually can happen。

What do you think of Yale？They don't think good。Does everyone have it。

 does everyone have stuff does everyone other stuff？'s like very small。いかと。I love it。What houses？

他姆你也吃他你吃。No， fo。make sure I want。よせ。AllAll the parties do。听得亮。すれ。天さ。し。さ？でレ。比赛预赛。

What do you think of your？小。おた。は。That goes again。So fairs fair there。

 So now back to some Hml and we will transition momentarily then to this other language CSS by which we can style things all the more。

 So there's this feature in HTML that's actually present in Python even though we didn't use it yet and that's present in jascript and really most modern languages known as regular expressions which is otherwise known as redxs。

 which is a way of using patterns to validate input or to extract information from strings。

 And so by that I'm in this， let me go over to Vs code here。

 let me go ahead and create a new file called register Hm。

 I'm gonna copy paste some code from earlier just to save some keystrokes。

 And in here I'm going go ahead and change my title to register And in my code I'm going go ahead and create a very simple form representative of a registration form now。

 So in this body I'm going do a form tag。 I'm not gonna bother sending it to Google or to any server in particular here I'm gonna give it an input tag with autocomplete equal。

😊，O as before I'm gonna have auto focus on as before I'm gonna give this form field the name of email this time instead of Q。

 I'm gonna give it a placeholder of quote unquote email just so that the user knows what they're supposed to type and it turns out that browsers have not only type text or search but also type email whereby you can rely on the browser to ensure that the human is actually typed in an email address Now I'm going go ahead and have a button that this time will be called register and now let's go over to my other tab reload my directory index there's registered HTMLm and we'll see a relatively simple form field now but it's prompting me to register with some email address if I go ahead and sort of type in just my name and try register you'll notice that the browser sort of yells at me with the builtin error message saying oh please include an at in the email address and it's pretty good in that if I do mail an at but nothing more which is also not valid and try to register it's telling me still that it's incomplete So built into browsers is some defense against。



![](img/e2286cf0b31bc83edb13a8b2f669b689_125.png)

Use incorrect user input in this way if I finally do type in like mailland@harvard。

edduu and click register， then the form would be submitted successfully to the server if though I want to tolerate only doedduu addresses because I'm making like an education themed website for students in the US I can actually add another attribute here which is actually quite useful too I can add a pattern attribute and inside of its value I can put one of these things called a regular expression or a rex that is an actual pattern that the browser should match the user's input against and make sure it indeed matches and this is going to look a little cryptic but I'm going go ahead and do this dot plus at dot plus backslash dotedu。

😡。

![](img/e2286cf0b31bc83edb13a8b2f669b689_127.png)

Now， this looks a little weird， but it turns out I'm using certain building blocks that will just scratch the surface of today。

 but it's an incredibly useful and powerful feature in programming languages more generally。

 because in the world of regular expressions。 There' are certain patterns that mean something。

 And here's a really good URL of some documentation。

 therefore in the world of the web and jascript specifically。 And here's kind of a short cheat sheet。

 some excerpts thereof it turns out in the world of regular expressions or patterns。

 a dot represents any single character except line terminators like backlash n a star or an asterisk represents0 or more times plus means one or more times a question mark means zero or one times a number inside of curly braces means n times or n occurrences。

 And then two numbers in curly braces， n comma N means at least n times。

 but at most M times or occurrences。 And then there's a few other actually So what does that mean。

 Well， let me go over to Vs code again， and let me zoom in on。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_129.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_130.png)

Pattern I used and it would seem that in this case a dot represents any character plus means one or more。

 so one or more characters to the left of an at sign then literally the at sign。

 then another dot plus means one or more characters to the right of the at sign。

 but the whole thing has to end in dot EDU but there's this additional backslash before the last dot and why might that be intuitively。

😡，Even though I've not said because I want a literal dot， a literal period。

 not any one character there。 So I escape the period to make it have not special significance per this cheat sheet。

 but rather a literal period。 So what this means is if I go actually back to V S code here and I try to claim to work at like mailin at harbor dot com and click register。

 That's a valid looking email address。 But when I click register now， whoop， sorry。

 it went through because I did not reload the page after making the change。 So I screwed up。

 let me go back to the register dot H T M L URL。

![](img/e2286cf0b31bc83edb13a8b2f669b689_132.png)

Let me reload the page and type in mailin atharvard co for instance and even sorry let me type in mailin@harvard co and even though it's a valid looking URL it does not in fact end in edu so the browser can defend against that in this way but the more important takeaway for now is that as useful as this is as user friendlyendly as this is this is not generally the best technique for validating user input and protecting against invalid user input why browsers can't be trusted or more generally clients can't be trusted why because the way HTML works as we've seen it thus far is that everything is happening on my own Mac or your own PC or your own phone locally per the envelope story we told earlier your browsers downloading the HTML reading a top to bottom left to right and then displaying it on your computer but we've already seen that my computer for instance。

 has built into it， these developer tools and they're among the tabs here or not just that network tab。



![](img/e2286cf0b31bc83edb13a8b2f669b689_134.png)

Actually go to the elements tab， which we haven't seen previously in the elements tab。

 you actually will see a pretty printed version of the same Hml。

 But what that means is that you can not only see the Hml。 you can actually change it。

 Now you're not gonna be able to change it on the server。

 But I can absolutely change my own copy thereof。 So suppose I'm now a hacker in the story。

 And I really want to register for this website， but it's apparently restricted it to people with do Edu addresses。

 I don't have a do Edu address。 Let me propose。 So that's fine。

 Let me actually go into the developer tools。 Let me just double click on the attribute there。

 highlight it and boom now gone is that pattern entirely。

 The web browser now will let me register with mail in it Harvard do com because the developer tools give you fullfledged access to the underlying Hl。

 So if I change the Hl。 the defense is no longer in place。 Now。

 what's the takeaway then is client side validation is wonderfully user friendly。

 but it's not secure。 It's not。

![](img/e2286cf0b31bc83edb13a8b2f669b689_136.png)

So next week we'll spend more time server side at making sure that even if someone messes with my H or my website。

 they still can't actually get through and do anything bad on the server。

 and this is true in general too， let me actually just for fun。

 go to maybe let's say Harvardeddu let me open up my development tools and for instance。

 let's see where I might go here。 suppose that I want to hack into Harvardedduu。

 Well notice that I'm on my elements tab and there's a lot of HTML that composes this page and notice that these triangles indicate that it's most of it's been collapse。

 but if I expanded them I can see more and more of the tags and attributes but suppose I'm now a hacker and I want to maybe delete this menu notice that you can also right click or control。

 click on any element in a web page typically with these developer tools click inspect or some similarly named menu option and you can actually be whisk away to the actual HTMLl tags that implement that feature of the web page One。

 it's wonderfully useful for。

![](img/e2286cf0b31bc83edb13a8b2f669b689_138.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_139.png)

Learning how things were teaching your new tricks and even fixing problems here， though。

 I'm going to try to use it maliciously。 And I'm going highlight this tag here。 div tag。

 as it's called I'm going delete it and watch what happens at top right gone is the menu。 Now。

 of course， if you go to Harvard right now。 the menu is still there。 If I reload Harvard。

 the menu is back。 So it's only my own local copy， but this does speak to how you should not trust anything happening client side because someone can be mutating that same code。

 Now， it turns out there's other patterns that you can use in regular expressions。 For instance。

 these are what are called character classes。 You can， for instance， specify in square brackets。

 some number of digits or characters that you want to match against。

 This is a range of characters 0 through9。 So it's effectively the same thing as that but easier to type。

 Theres certain shortcuts backlash lowercase D means any decimal digit backlash capital D means anything that's not a decimal digit and dot do dot there's bunches of other patterns。

 you might use the。To maybe validate a phone number in a web page if you want it to be formatted in a certain way for better for worse。

 but long storyory short， regular expressions will be someday your friend。

 as you try to solve certain problems with data as an aside it does escalate quickly So this is typically the regular expression that browsers nowadays use to validate email addresses。

 it is way more complicated than dot plus at do plus why because you can't have at ateddu or you can't have there's certain characters you don't want to allow。

 there's certain characters you do want to allow so long storyory short。

 this is in a much larger regular expression that is more correct when it comes to valid email addresses All right so with that said。

 there's one tool with which you should be familiar and that is at this URL here validator w3 org and this is a free web service from the world consortium which is the group that essentially standardizes this h language。

And if you go to their webpage， there's a few different ways to validate your own code。

 essentially check it for correctness by typing in its URL。

 otherwise known more generally as a URL by uploading a file or by direct input。 So just for kicks。

 for instance， I'm going go into VS code and grab my Hl that I just made I'm going go back to validator W3 org and paste it into the direct input box and click check and it's just a nice handy website that if I scroll down in green。

 you will hopefully see this。 no orders or warnings to show。

 So it's a handy feature just to make sure that at least syntactically your code is correct。

 even if it's not behaving the way that you might want。 Allright， with that said。

 the second of today's three languages。 and we'll just scratch the surface ultimately of jascript to give you a sense of its capabilities。

 But CS is something that's worth understanding some of the basic building blocks thereof。

 So let me propose that there are some additional terms to know in the world of CS where again。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_141.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_142.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_143.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_144.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_145.png)

Have key value pairs in this world， they're called properties instead of attributes。

 why it was invented by different people， but it's the same kinds of ideas in the world of CSs。

 you're gonna have ways of specifying different selectors as they're called that is to say we're gonna be able to specify the font size。

 the color， the margins and a lot of aesthetics when it relates to tags in our web page and there's gonna be different ways to select those tags as we'll soon see in an HTML page like this。

 This is our super simple one with which we began。 It turns out that you can also include a style tag in the head of the page that has some of your stylistic decisions font sizes colors。

 margins and all of those kinds of aesthetics We'll also see another approach whereby you can relegate all of that stuff to a separate file like Sts css or something css and you can link to it in the head of the page link here does not mean a like ideally our anchor tag before would have been called a link but it's not this just means that these two files are linked in some way。

Conceptually， allright， so that is to say we can use these kinds of tags now to enhance our own code。

 So let me propose that we do this。 Let me go into Vs code here。 Let me go ahead and create a very。

 very simple homep page for someone like John Harvard by running code of how about home do Hml and in home do Hml。

 I'm gonna copy paste some of my starter Hl from before。 And now in the body of this page。

 I'm going to do a few things。 I'm going to have a web page with a paragraph up here that just says John Harvard is the title thereof another paragraph that says something simple。

 like welcome to my home page exclamation point and then like a footer at the bottom and a third paragraph that's a copy say John Harvard。

 for instance， So super simple but representative of like a header。

 a main part of the page and a footer thereof。 if I go into my other tab。



![](img/e2286cf0b31bc83edb13a8b2f669b689_147.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_148.png)

And reload my directory listing。 I will see now home do Hm。 and it's gonna be pretty bare bones。

 right， It's the same text， same font size。 It is three separate paragraphs。

 but let me start to stylize this a little bit differently。

 Let me make like the top bigger and bolder， perhaps or rather the top bigger and centered and make this text shrink thereafter。

 So I'm gonna go ahead and do this。 It turns out that you can have not necessarily a style tag。

 but even more simply a style attribute on certain tags like this。

 I'm gonna add a style attribute that has a font dash size of maybe large and how about a style attribute here。

 a font size medium and then maybe down here， whoops close quote and then down heres。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_150.png)

Thank you。 Okay， I you some cookies。 Allright， So style here of font size， small。

 So relatively simple ideas。 and here is just another stupid syntax for key value pairs。 Again。

 left hands not talking to right hand in CsS cascading style sheets。

 which is the language we're now talking about， It's key colon value in Hl。

 it's key equals unquote value is just different techniques for the exact same dictionary like idea。

 All right， if I go back to my other tab and reload。 notice that it's a little subtle。

 but it is large， medium and small。 I didn't center things yet。 So let me do that。

 It turns out that this thing collectively， It's what's called a property and a property is defined by like a key value pair。

 If you want to have multiple properties or key value pairs in in CsS。

 you separate them with semicolonons。 So those are back。

 And if I want to center the text I can do text align colon center。

 I could now end my thought with the semicolon， It's not strictly necessary。

 but I'll keep it just so。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_152.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_153.png)

I'm consistent， but it's only necessary if you have more than one。

 I'm gonna go ahead and center everything though。 So I'm gonna to go down here and add a semicolon after medium down here and add a semicolon after small。

 So I align text line center center center for all three paragraphs。

 if I go back to this other tab and I reload now it is in fact centered。

 but here's where we can start to have a conversation about maybe design。 So I claim this is correct。

 but is this perhaps the best design。 Well， maybe not。 I mean。

 these aren't really paragraphs first of all， semantically like it's not even complete sentences。

 but there are sort of three different divisions of the page right like the header up there。

 the main part in the middle and then the footer So it turns out and we saw a glimpse of this in Harvard source code。

 there's another tag instead of div instead of P for paragraph called div for division And even though this is actually not gonna to have much of a functional effect at first。

 it's maybe semantically a bit better because again， these aren't。



![](img/e2286cf0b31bc83edb13a8b2f669b689_155.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_156.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_157.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_158.png)

Paragraphs。 so if I really want to nitpick， I do have three divisions of the page。

 So div is a very common way to give yourself just like a rectangular region of the page to style as you see fit。

 If I go back now and reload， notice that it does tighten things up。

 The paragraph tag gave me some vertical white space for free。 So I've lost that。

 but I could add it back if I really wanted to。 But now let's come to this question of design。

 what's redundant about what I've done thus far， even if you've never seen CS before。



![](img/e2286cf0b31bc83edb13a8b2f669b689_160.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_161.png)

Yeah。😊，Yeah， I mean， I had to center all three divs， which is just sort of stupid。

 it would seem copypy pastse has generally not been necessary even though I'm doing it to save time today in general。

 when the results are copied and pasted， ultimately like this has not been good practice in any of our languages So it turns out I can do this。

 Let me actually delete this one and I can keep or get rid of the semicolon get rid of it for parodity with our first version I'm going get rid of this one too and you know what here's the C and CSS cascading it's more like a waterfall effect And if I go up to a parent tag here like the body is the parent of all three divs I could put the style attribute here and say text align colon center there and that has the effect of cascading down onto all three of the children that are nested inside of it So now it's sort of better designed because I've only said text align center once if I go back to the webp page and reload。

 it has no functional impact visually， but it's better designed because if I want to align it left or right or center I can change it in one place。



![](img/e2286cf0b31bc83edb13a8b2f669b689_163.png)

Not three independent places。 All right。 What else might I change after this here， Well。

 it turns out。That I could do something a little clear as well。 This copyright symbol。 I mean。

 it's just sort of like homemade with two parentheses in a C。

 It turns out that there are ways to get special symbols in H。

 and you can use what are called Hl entities。 You would only know these by looking them up or memorizing the numbers。

 But it turns out that number 169 is the special Hl entity for an actual copyright symbol。

 So let me zoom in here and then reload， and you'll see that the parenthetical C actually becomes the proper mark for copyright。

 So marginally useful or you could copy paste it from some other website， for instance。

 if you didn't know how to type it on your own keyboard。 So that's an H entity。

 another feature with which to be familiar。 But having three dibs on a page isn't necessarily ideal nowadays。

 especially for search engine optimization Seo for screen readers for accessibility。

 because at a glance， I don't really know which of these divbs is the most important arguably the footer is generally for the human reader。



![](img/e2286cf0b31bc83edb13a8b2f669b689_165.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_166.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_167.png)

The least information bearing piece of content。 So why don't I try to signal as much to the browser to the screen reader to the search engine。

 So it turns out there are what are called semantic tags nowadays。 indeed。

 we're up to version 5 of Hl and one of the relatively newer features is instead of using generic divs。

 you can actually use actual names of tags like header and main and even footer。 And here too。

 the visual effect is going is not going be any different if I go here and reload but there's more semantic information underneath the hood so that again。

 all of those different types of services that you browser the screen reader and the like just know a little more about the page and maybe a screen reader now would focus on the main part of the page before reciting all of the fine print and the footer。

 for instance， to the human。 All right， Well， what else could we do here。

 What it would be nice at some point， to be able to reuse these styles。

 And if I find myself making one page but two pages or 10 pages or 100 pages。

 it's kind of annoying to。

![](img/e2286cf0b31bc83edb13a8b2f669b689_169.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_170.png)

To type out all of the same styles。 So wouldn't it be nice to start to factor this stuff out。 Well。

 I can do that， too。 Let me actually go ahead and do this。

 Let me get rid of this attribute and this attribute and this attribute。 And honestly， too。

 as I do this， I would argue that the code looks just a little cleaner now， like it's more obvious。

 what is a tag and what the actual data of the pages， metadata and data， if you will。

 but I've lost all of my styling， but wouldn't it be nice to preserve some of the styling by doing what I proposed earlier。

 which is using not a style attribute， but a style tag。 And indeed。

 you can put a style tag in the head of your web page where you can put all of those same properties。

 And you need a little more syntax， a a few more keystrokes， but I can say this。

 if I want to center the entire body of my page。 I can actually do so by specifying text align colon center。

 semicolon here， the semicolonons are going be generally necessary。

 especially have you multiple properties。 next， I'm gonna say header and。Of these curly braces。

 font size large， unlike C， where you could get away with no curly braces。 If there's a single line。

 you do need them in CsS in the main tag。 Let's go ahead and style with font size medium and then in the footer tag。

 let's go ahead and style with font size main with font size small。

 Now this looks a little worse because it's just kind of blew up and is a lot longer。

 but it is a step toward factoring this out。 And honestly when it comes to web pages。

 I'm not the best artist in the world like I can make the data display。

 but friends of mine are certainly better it making things really pretty and pixel perfect。

 so to speak。 So it's kind of nice if I can kind of isolate all of the style to one part of my file and all of the content to another because maybe I can now collaborate with someone else。

 So if I go back to now the other tab and reload functionally no different still。

 it still looks exactly the same。 but I'm starting to make it a little better design。 And in fact。

 there's another way to do this。 suppose that I find myself in the habit。😊。



![](img/e2286cf0b31bc83edb13a8b2f669b689_172.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_173.png)

A very often centering text on a page。 And honestly。

 it's just a little annoying to have to type this out for every tag that I want centered。 Well。

 I could create what are called classes as well in CS。 It turns out you can make up your own words。

 but I'm gonna choose some reasonably named ones by prefixing them with a dot or period。

 And if I want to call this set of properties， even though there's just one centered。

 I can literally write dots centered there instead， I can write this dot large。

 I can call this dot medium， I can call this dot small。

 And what this means now is I have reusable sets of properties kind of like containers whereby anywhere I use the word centered。

 it's going to get those that one textalline center property applied。

 anywhere I use quote unquote large， it's going to be made large。 And so if I scroll down now here。

 I do need to reintroduce another attribute， but it's a very common one in the world of HTMLm now。

 that of class So class equals large down here I'm。Do class equals medium down here。

 I'm gonna do class equals small。 and it's getting a little more verbose。

 but I'm not polluting all of my HTML with the actual styles。

 I'm just kind of having this layer of indirection and abstraction。

 if you will on top of those very specific properties。 And then for the body I can do the same idea。

 class equals centered。 And if I go back to my web page here and reload still looks exactly the same。

 but I've kind of centralized where I can do things。 And frankly。

 I could do something like this color red semicolon， I can package up multiple properties。

 go back to the page here and reload。 And now that has applied to everything。

 So I have a reusable set of properties， even though centered is maybe not the best name now because it also makes things red。

 but I can come up with reusable sets of properties。

 And honestly one final flourish here would be let's not assume that my buddy。

 whether it's my project partner or colleague in the real world。

 it's kind of stupid to try to edit the same file because like invariably we're gonna break things on each other。



![](img/e2286cf0b31bc83edb13a8b2f669b689_175.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_176.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_177.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_178.png)

So I could actually do this。 Let me take all of this。 and I'll get rid of the red。

 Let me go ahead and highlight everything I just did and cut it to my clipboard。

 I'm gonna get rid of the style tag altogether， but I am going to go into VS code and create how about a file called home CsS。

 just so I know what's what。 And in this file， I'm just going literally paste everything I just made。

 But I'm going go back to my home page here。 and I'm going add that other tag I proposed earlier link Hf equals home csS。

 and I need one weird attribute to the relationship of this link is that of quote unquote style sheets。

 And that's just the way it is according to the tag。 And now one last time if I reload this page。

 the red's gonna go away because I deleted that but the font sizes and centering are still there。

 But what I've done was introduce some basic building blocks in this language I claim is called CS that's going to allow me to now centralize all of the style。



![](img/e2286cf0b31bc83edb13a8b2f669b689_180.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_181.png)

The aesthetics now of my web page。Alright， let me pause here and see if there are。

Any questions on these techniques thus far， it's just more key value pairs。Questions on this。

All right， so here's where things can get prettier quickly。

 Let me go ahead now and close these two tabs。 Let me go into a file we created earlier called link do html。

 which recall looked a little something like this。 And now we can make this web page behave a little more like the real world。

 Let me undo the phishing attack and just literally say Harvard down here。

 But let me go ahead and start to style the anchor tag as follows。 previously。

 this page looked a little boring like this。 The link was blue originally。

 but because I visited Harvard do Eduu by default the browser change it to purple， which is fine。

 but maybe you don't want that。 Maybe we want something that's a little more crimson for instance。

 So let me do this。 Let me go into the head of this link do html page。 Let me add a style tag herein。

 And in there， let me style the anchor tag as follows inside of this anchor tag。

 I'm going do color colon red。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_183.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_184.png)

And let's go ahead and leave it as such for now。 let me go back to the link page and reload。

 and it's gonna be a little subtle。 but right now it's purple。 and now it it's definitely read。

 so I've modified that。 Now underlining links is good for accessibility。

 but a lot of websites choose to not underline them and instead underline them when you hover over them。

 So that is an effect we can achieve， even though it might not be ideal。

 but let's at least demonstrate how websites are doing that。

 I can specify that this link should have text decoration of none。

 Now I would only know that by having taken a class， read a book at onlineline reference。

 the default is unders。 the default is underline。 but I can override that by saying none。

 So if I now go back to my page reload， it's still going be read。

 but it's now not going to be underlined， but notice if I hover over it。

 it changes to a little pointer finger if I zoom in here。

 but it's clearly not underlining So that's okay because there's another way of selecting tags here。

 I can say a colon。

![](img/e2286cf0b31bc83edb13a8b2f669b689_186.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_187.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_188.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_189.png)

Hover and then inside of this CSS， I can say text decoration colon underline when the anchor tag is being hovered over with the cursor。

 If I go back to my tab here and reload still looks the same but watches Mike mouse gets close it now underlines as a lot of websites do So it's a relatively simple idea。

 it's not as compelling on mobile especially because it doesn't do anything if you hover your finger over the glass of your phone。

 but it does work on laptops and desktops in this way even though it's perhaps a little pass now to do this kind of technique。

 but there's other ways to select tags on a page。 and in fact， let me go back to this one here。

 and in this page， let me propose that you can go in one of two places visit Harvard or ahf equals https colon www Yale edu and then Yale's website So it's getting a little long So I'm going hit enter because the browser won't care that there's some whitespace。

 but at least now I have two links on the page if I reload this。



![](img/e2286cf0b31bc83edb13a8b2f669b689_191.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_192.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_193.png)

See that both of them are red or crimson， which isn't quite right， but that's okay。

 I can actually distinguish these two somehow。 One way to do this would actually be to add one more HTML attribute that we haven't needed or used before that of I I can use any almost any name for this I that I want and I'm going say quote unquote Harvard is the unique I of this link and the unique idea of this link is quote unquote Yale for instance。

 and what I can now do up here is I'm going to get rid of this color red because I don't want all anchor tags to be red but I do want Harvard tags to be red So I can say hash Harvard and then color red and then I can do hash Yale and I can say color blue for instance。

 the hash symbol here represents an ID the dot we saw earlier represents a class and when you don't have a symbol before it represents literally the name of the tag So when I mentioned these various selectors earlier type selector is just the name of the。



![](img/e2286cf0b31bc83edb13a8b2f669b689_195.png)

ag class selector is the dot I selector is the hash。

 And there's also ways to select attributes specifically。 So if I go back here in VS code now。

 I've added a bunch of Css here properties。 but if I reload now。

 one of these should be red and the other is， in fact， blue。 So in short。

 just by way of these style attributes in these style tags。

 we have a lot more control over how we can actually stylize our pages。

 And here's now where this gets interesting。 And you asked about bootstap。

 a popular framework or library， they're do indeed in the real world exist a lot of thirdpart frameworks that a lot of smart people have've just figured out what would make our web pages look prettier。

 And they've come up with design patterns for us that make it way easier and way faster to make pretty looking forms。

 pretty looking tables and the like。 And one of these products is indeed called bootstap。

 it's freely available。 and you can see its own documentation get bootstap com And what I've done in advance is I've actually prepared some of our past data to actually be format。

😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_197.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_198.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_199.png)

A little more prettily。 So let me actually go back to Vs code here。

 and I'm going to open up a terminal。 and I'm going to cheat and copy a file I brought with me called Phbook 0 do Hml。

 And if I open this file， you'll see that it looks like this。

 It's a big table that has two columns now called name and number And I've added some other tags。

 which are not that interesting， but I didn't need them before。 but in this table。

 there's a table head and there's a table body。 So there's like a special row at the top。

 and then all of the rest of the data like in a CSv or a spreadsheet and you can probably infer from this table row from this table row from this table row。

 it kind of looks like indeed a phone book。 So if I go back to my browser here。

 go into my directory listing and open up phonebook 0 Html。 It's not the prettiest thing。

 but it is tabular and notice that the browser is automatically put in bold the name and the number。

 and everything's in columns。 but it's not very pretty But what if I do this。



![](img/e2286cf0b31bc83edb13a8b2f669b689_201.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_202.png)

Let me actually go into V S code here and let me borrow another file I came with called Phbook 1 dot H T M L。

 And that file。Is going to look a little bit different than the last in that。

 I've included a link tag in the header。 Now I've not linking to my own CSss。

 I actually went to get bootstrap do com。 I read some of their documentation and I'm linking now to bootstrap Css file。

 which is actually really， really big。 And in fact， if I open this file here。

 let me actually open this up in a tab and visit this URL here。

 The folks at bootstap have written a crazy amount of properties by defining their own classes and other such keywords and you and I and really anyone on the internet is welcome to use all of this css。

 and the documentation makes clear what all of this does。

 a normal person would not need to read through any of this in that way。

 But I've included this file called bootstrap min do css and min just means they got rid of most of the whitespace。

 And if I now go back to my other tab and go back to phonebook 1 do html， it's the exact same data。

 but thanks to that link tag。

![](img/e2286cf0b31bc83edb13a8b2f669b689_204.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_205.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_206.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_207.png)

It now looks much prettier and I didn't have to figure out how to move things over to the right。

 I didn't have to figure out how to draw these gray lines。

 I didn't have to figure out how to format things in precisely this way。

 Botrap wonderfully in most of that for me Now this is still a very static table it's not interactive I can't sort by names or columns or the like so let's revisit one other program that we made an events together and this one is actually a new version of the search program So if I open up this program search version to hml and close my terminal window you'll see that I've borrowed some of the same content before。

 let me go to the essence of it here is the form and the action that I used earlier but I've added a whole bunch of classes to it and this is the essence of these thirdpart frameworks。

 they generally create a whole bunch of classes that you can use and reuse but they figured out all of the relevant properties So for instance for my Google search button I've given it two classes。

 a class of button。

![](img/e2286cf0b31bc83edb13a8b2f669b689_209.png)

And for sure and button dash light， these are not standard HTML or CSS things。

 These are bootstrap names that they invented just like I invented centered and large and medium and small。

 I've also specified that there are a whole bunch of other classes associated with pretty much every tag in this file。

 So if I zoom out here and go back to my directory index and open this the first version of search it was super。

 super simple because it only contained the HTML form let me go ahead and open up search2 HTMLm and the essence of the form is exactly the same therein is the query at the bottom of the page but thanks to CSS I now have a button that looks a little more interesting it's gray and it's rounded I also have an I'm feeling lucky button which will send a different request and show me by default the very first search result So in short the file that I just opened even though I made it in advance it's only 55 lines and most of that is white space and it did take me a little bit of time to figure out the classes and read the documentation。



![](img/e2286cf0b31bc83edb13a8b2f669b689_211.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_212.png)

But most of the work is done by this third party framework or library of CSS classes and properties that someone else made for me。

😡。

![](img/e2286cf0b31bc83edb13a8b2f669b689_214.png)

And so as C S goes， like that's kind of it for the basics。

 It's just a bunch of more key value pairs in the form of these properties。

 whereby you can select elements of a web page by way of their Id or classes or even the names thereof。

 And here's something that's kind of neat too。 Let me go to Harvard do Edu again。

 let me go ahead and open up the inspector as before and draw your attention to one final feature of these developer tools under the elements tab。

 So under the elements tab here is all of the Hl that composes hardware do Edu as of today。

 But let me go ahead and expand this right hand portion。

 It turns out you can also see all of the CS that is being applied to the website as of now。

 So for instance， if I go to a page here。 let's go to， give now。 might as well。

 let's give them a plug here， under give now。😊，Let's see if this is gonna go well。

 Let's go ahead and highlight this part。 Supp they really want to draw attention to give online。

 and I right click on that。 I choose inspect as before。

 and here now notice that the developer tools jumped right to the Hl tag that represents that particular line of text。

 If I zoom in， turns out it's an H1 tag。 It's big and bold。

 suppose though I want to change its color。 Well， if I go over on the right here。

 you can see all of the CSss properties that currently apply to that specific tag。 and most of these。

 we haven't even talked about line height， margin bottom， font weight。

 margin top and a bunch of other fairly self-explanatory things。 But if I want to kind of experiment。

 I can go up here in top and say color， colon red。 and I can literally change that on the web page live to see how it looks。

 it's not changing the server。 it's just changing my copy but I can at least make that change。

 you can do even fancier things where if you click computed， you can scroll down and figure out okay。

 wait a minute， it's white right now， that's the same thing as this RGB 25，52。



![](img/e2286cf0b31bc83edb13a8b2f669b689_216.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_217.png)

25 that's the same thing asFF from weeks prior， but I can click this little arrow and it will even show me where in Harvard CSS that white color comes from so if it's actually my site I can actually figure things out and make changes as well so in short。

 if you find that you like the world of web development in your own browser that you've had all this time there's so much darn functionality built in and it's just up to you now to start experimenting with it exploring what you can actually do with it。

😡。

![](img/e2286cf0b31bc83edb13a8b2f669b689_219.png)

But let us use our final moments today to introduce you to a final language called JavaScriptscript。

 which is itself a proper programming language。 And you're about to see a bunch of syntax that's kind of new but kind of familiar and the goal here is not to teach you jascript per se。

 but to begin to lay the foundation for you yourselves learning a new language on your own by the end of CS S50。

 you will not have learned all that is out there， certainly and the goal here。

 ultimately is to help you have a sense with a support structure in place be it the humans or the duct involved that you can ask questions of along the way。

 Let's go ahead and do this in my directory index， I'm going go into the source8 directory where I've got all of today's examples ready to go。

 I'm gonna go into VS codes Exp where I can see all of those files and in my source8 directory。

 Let me go ahead and open up hello version 1 Hl recall that the last time we played with hello do H。

 it was literally just Hm。 but here's an example。

![](img/e2286cf0b31bc83edb13a8b2f669b689_221.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_222.png)

A language called jascript。 And this page is going to work as follows。

 If I open hello1 do Htl on my page， I have a very simple form。 Let me zoom in。

 Let me type in my name。 for instance， D I and hit enter and， this is not a very good user interface。

 but you can see that this web page says quote unquote hello， David。

 So how did I get this form to trigger a pop up。 Well， if I go into V S code here。

 you'll see a web form But I've added another attribute namely an on submitubmit attribute。

 And the world of ja of Hl on submit allows you to write a tiny bit of javascript code inside of the quote that will be executed whenever the user submits this form。

 So what this is saying is call a function called greet。 and then return false。

 And what return false means is that don't actually submit this form to the server。

 like keep the user on this page。 So we can just see a pop up。 So what is this greet function。 Well。

 it turns out in the world of Hl。 There's not only a style tag you can put in your。



![](img/e2286cf0b31bc83edb13a8b2f669b689_224.png)

Of your page， but also a script tag inside of which is jascript code。

 the syntax is a little different from Python and from C。

 but it's maybe a little closer to Python instead of de last week or two weeks ago。

 we'll now use function literally to begin the definition of a function。

 And if I want to call this function greet， so be it。

 JavaScriptscript comes with a function called alert。

 And so if I literally do alert hello comma unquote And then plus something else。

 just like in Python that's going to concatenate or join the two things left and right。

But here's some functionality that comes with your browser too。

 It turns out per the notion of this whole page being a document you can call document do query selector。

 which allows you to select any of the tags or elements in the page specifically you can select the tag that has an idea of name So CSS and jascript use the same syntax。

 if you see hash something that is referring to the I of a tag that you created if you then after selecting the element of HTMLml with that unique I want its value。

 you just do dot value。 So we saw dots a lot in Python and and C to go inside of structures。

 you can go inside of that text box and get its value So notice here。

 if I scroll down not only am I using autocomp an autofocus and so forth。

 I also for convenience gave my input box a unique I of name So what's effectively happening is when I click submit my jascript greet function is called it queries for that text box。



![](img/e2286cf0b31bc83edb13a8b2f669b689_226.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_227.png)

Goes inside of it and gets its value and then using this plus operator， just like in Python。

 concatenateates the two together and passes them to this alert function for an underwhelming but functional。

😡，Alert in the window。All right， how else can we do this？😡。

This is generally frowned upon to use on submitit in this way。 Like generally speaking。

 the world does not like mixing attributes， rather javascript code with Hl so closely as this。

 So let me show you another variant of this， even though it's gonna look a little bit cryptic。

 but at least it will be representative of how else you can solve this problem in hello2 do Hl we have this code。

 notice that at the top of my body now is the form But at the bottom of the body is this script tag。

 So I've just moved it from head to the body of the page because I'm gonna then instead do this。

 if I want to tell the browser to listen for submissions of that form。

 I can use this fairly cryptic syntax， but you'll see it again and again over time as follows go intoops go into the document select with this query。

 the form tag and then call this special function that comes with the browser called add event listener。

 So tell the browser to listen for a certain type of event。For this form。

 What event you want to listen for， the submission of the form。

 So quote unquote submit What do you want to have happen whenever that event is heard。

 you want to call this function here。 So this is what's known as an anonymous function。

 The syntax is a little weird， but I've not given the function a name。

 It apparently takes an argument as input called event。 but that's per the documentation。

 And what these two lines of code do essentially， is they still call the alert function。

 They still output hello comma space。 and they still query the Hml for the Id name to get the value that the human typed in。

 And then just for good measure， we prevent the default behavior for any form with this line of code just so that it doesn't actually submit anything to the server。

 It keeps the user actually here。This will be a little scarier too。

 but just so you've seen it in hello 3 do Hl， This is actually a more common technique。

 whereby you can add listen for one other special event。 It turns out when you load a web page。

 lots of stuff has to happen。 It's got to be read top to bottom left to right。

 It's got to download other files， the images， the sounds， the videos and so forth。

 If you want to wait until the whole page has been read into memory essentially。

 you can use this event as well， Dom content loaded。 that tree we dreww earlier。

 is what's called the Dom document object model， which is just a fancy way of saying a tree in the computer's memory that represents the web page。

 So this is the syntax that you'll find that people use to tell the browser， once the whole dom。

 the whole tree has been loaded， then go ahead and execute this code。

 And it means that no matter what the whole web page will be ready in order to before this code is actually executed。

 And this ensures， for instance， that even though this script is at the top of my。😊。

And my form is at the bottom of my file， none of this code will get executed until the whole DOm is ready。

 All of the HTML has been read top to bottom。😡。

![](img/e2286cf0b31bc83edb13a8b2f669b689_229.png)

Left to right。Alright， well let's go ahead and make this a little more interesting just to show you some of the capabilities of jascript within a browser nowadays。

 So if I open up maybe this one here， background hm let me open it up in the browser and this is going be super simple in terms of user interface。

 but here's a big white viewport， big body that's just white in color by default but there's three buttons at top left and if I click R it makes the background red G makes the background green and B makes the background blue What's interesting about this demo sort of underwhelming as the user interfaces is it demonstrates that you can modify CSS using jascript and HTMLl。

 CSs and jascript are therefore very intertwined in the context of a browser how here's the raw HTML here are the three buttons and I've given them three separate Is red。

 green and blue just so I can refer to the specific buttons and notice what I've done here。



![](img/e2286cf0b31bc83edb13a8b2f669b689_231.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_232.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_233.png)

I've declared a variable in ja， which uses slightly different syntax of let as the keyword。

 instead of int or char or string， you can use the keyword let。

 which essentially means let me create this variable called body。

 and this is just how using query selector， I can select the body element from the web page because I'm gonna to use it three separate times。

 What do I want to do three separate times， for instance， this。

 I want to go into the document and select whatever element has the unique idea of red。

 I want to tell the browser to listen for this event。 click。 So we saw submit before。

 you can listen for clicks as well。 When the click happens on this button。

 I want this function to be called。 What does this function do something super， super simple。

 All it does is it changes the bodies， styles， background color to be unquote red instead。

So what's going on here， we didn't see this earlier， but it turns out in CS。

 there is actually a CS property called background dash color， and I can see it as follows。

 Let me reload this page， open the browsers inspector。

 open up elements and if I hover over the body here notice that there's no background color by default。

 But if I do in say， sorry， lowercase， background color， colon yellow。

 it immediately changes the background to yellow。 Unfortunately， in JavaScriptscript。

 you can't do background dash color， why might this be。😡。



![](img/e2286cf0b31bc83edb13a8b2f669b689_235.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_236.png)

Yeah。It thinks it's minus or subtraction right So I would wager there was a human at some point in the room designing jascript where they realized like damn it like we shouldn't have used a hyphen in CSS because it's now gonna to be misinterpreted as a subtraction operator in jascript So the way the jascript world solve this was whatever has a hyphen in it as background dash color you change it in the jascript version thereof to be camel case so to speak whereby there's this hump in the middle where it's a capital C no hyphen instead of a lowercase C instead。

 and I do this here and I do this here So as to essentially listen for a click on any of those three buttons so that the end result is that it changes it from red to green to blue based on what I'm clicking。

 and here's where the developer tools get kind of cool。 notice it bottom right here。

 notice that as I click on this the CS of the page at bottom right is changing to match whatever is happening。

 So you can really see and understand what's going on underneath that hood there。 All right。

 we have time for a few other demonstration。

![](img/e2286cf0b31bc83edb13a8b2f669b689_238.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_239.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_240.png)

Back in my day， when I learned HTML， there was a bunch of hideous tags still in circulation among them was a blink tag。

 which literally if you used blink and put words in between its open tag and close tag you would get text on your screen just kind of doing this Even uglier was what was called a marquee tag which would actually scroll text across the screen like this。

 and like no self-repecting website tends to have like blinking text or scrolling text in this way because it's just tends to be ugly。

 however， even though it is the blink tag is among the few tags that's ever been removed from the language。

 you can bring it back with a bit of jascript。 So here， for instance， as an example in blink Hm。

 here's a super simple page， the only thing in the body is hello world。

 but there is a script tag up in my head of my page here。

 and let's see what's inside of this script tag。 Well。

 I've defined online8 downward a function called blink。 What is a do Well。

 I first declare a variable called body and I get the body element。Using query selector。

 I then ask this question if the body's styles visibility property。

 which we haven't talked about yet is quote unquote hidden then change the body's styles visible property to be quote unquote visible else if it's not hidden that is it's visible change it to hidden instead and here too。

 this is another one of these left-hand righthand situations。

 I do not know why the opposite of visible is not invisible， it is instead hidden。 So again。

 arguably poor design， but this is what we have how is this useful。 well。

 there turns out in your browser， there's a jascript function called set interval that's associated not with the document per se。

 but the window which is another global variable that you just get atmatic access to in the browser that allows you to call a function any number of milliseconds again and again and again。

 so if I want my text to blink every half a second or 500 milliseconds。

 I just use windowet interval to call blank every。Hund0 milliseconds。

 and notice is very important not to call blank here as with parentheses like in C or Python because I don't want to call blank at this moment in time。

 I just want to inform the set interval function of the name of the blank function。

 So I just pass in the name blank。 And if I go back to my directory listing， I open up blink H Tml。

 you'll see what I used to see like in the late90s when Htl1 was all the rage like the beginnings of very ugly website。

 including my own personal homep page at the time。 my own personal homep page at the time。

 which is probably findable somewhere online and the archives it was back in the days where like you wouldn't just show people the content of your page。

 you had to click a enter button to enter the web page and just really ridiculous。

 There's a lot of things in tech that you can do， but should not do。

 And the world has learned this as the hard way。 Allright。

 let's do a couple final examples that are now representative what modern websites do and what you and I take for granted on web apps and mobile apps alike。

 for instance。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_242.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_243.png)

This feature of autocomplete case in point， when I went to Google do com before and I started searching for cats or dogs or birds。

 it was trying to finish my thought and populating a dropdown with a bunch of different suggestions。

 I can actually do that myself in jascript as follows。 Let me open up a file called large do Js。

 which is a file that I made based on spellers own dictionary。

 recall that we gave you a big list of words like 100000 plus words。

 I copied those into this jascript file， but I formatted them in what's called a javascript array。

 So jascript has arrays， They're more like Python lists and they are like C arrays。

 the syntax as square brackets。 is my keyword to say give me a variable called words。

 which is all caps because I'm going to use it globally。

 and here is a00000 words from that dictionary in this file。

 Allright Now let me close this file and open up the actual Hl file。 Autocomplete Hm。

 Let me scroll down to the bottom。 and you'll see that in this page。



![](img/e2286cf0b31bc83edb13a8b2f669b689_245.png)

In the body are two things， one in input。 So a text box。 so I can start typing words。 and then two。

 an unordered list that's empty。 So there's no actual list items in that in that unordered list initially。

 But there is a lot of jascript。 Here's how I'm including the large dictionary and here's how I'm implementing autocomplete。

 So let me first show you what this does， let me go back to my directory index。

 click on autocomplete do Hml， I'll zoom in。 And if I type in C。

 I immediately get an unordered list of all words starting with C。 if I type C。

 it gets filtered further， but we can't see the difference because there's so many word starting with C C。

 the list is changing C S， the list is changing and notice that if I were to open my developer tools。

 What gets really interesting is you can see this list being made in real time。

 let me delete it notice that the U at bottom left is now empty。

 But if I type in suddenly cats notice that the triangle appears and there。



![](img/e2286cf0b31bc83edb13a8b2f669b689_247.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_248.png)

Are all of the list items that my my jascript code is apparently dynamically chant of creating。

 And indeed， how do I do this， Well， this one's more of a mouthful， but here's the idea。



![](img/e2286cf0b31bc83edb13a8b2f669b689_250.png)

I use the query selector function to get that input text box。 I then add a listener to that input。

 listening for what's called key up。 turns out you can listen for the finger going down or the finger going up So I'm waiting until the user lifts their finger off the keyboard Aka key up When it hears that event。

 it should do the following。 It's going to create a variable。

 the temp variable called HTMLl equal to quote unquote nothing。 in jascript doesn't decide。

 you can use single quotes or double quotes for whatever reason styyllistically。

 jascript programmers tend to use single quotes。 I can then say if human if that input has a value because the humans typed in one or more letters。

 then iterate over all of the words in the dictionary。 and we've not seen of before。

 but it it's javascript's equivalent of Python's for loop。

 if that word starts with whatever the input value is。

 go ahead and add that is concatenate to the HTMLl variable and open tag L I。

 then whatever the word is using this jascript specific syntax and then close the tag。AndThen lastly。

 using query selector， grab the UL tag， go into its inner HTML so to speak inside of it and change it to be this HTML I just created it。

 And so in this way using ja I can dynamically add to and subtract from the HTML in the page There' are so many other events here to clicking。

 submitting key up， dragging and dropping and so forth。

 this is just some of the events that web pages and mobile apps can listen for but we'll do one final one which speaks to the power of browsers nowadays and even the implications for privacy if I go into geolocation HTMLm。

 It turns out you can figure out where in the world a user is with like three lines of code nowadays assuming they've turned on location services and opted in on their device here albeit be a cryptically is a final global variable that comes with browsers today called Navigator。

😡，you has a geolocation object associated with it， which comes with a function called get current position。

 You can then specify or figure out the user's latitude and the user's longitude。

 And all I'm going to do is write these to the screen so I can see this demonstration live。

 So our very final demonstration here of Javascript is going to be this one here for geolocation to show you how easy and how invasive Even code can be。

 if I click on geolocation and wait。😊。

![](img/e2286cf0b31bc83edb13a8b2f669b689_252.png)

There are my GPS coordinates， latitude and longitude， and to confirm as much roughly。

 let's go ahead and open up a browser， paste in those coordinates。

 click on the Google Maps result that comes up first， Zoom。😡。



![](img/e2286cf0b31bc83edb13a8b2f669b689_254.png)

In in， turn on satellite mode。 And in。 and I'm not quite in that corner of the building。

 but I'm presumably close to an access point that Google has known about and associates with my GPS coordinates。

 It's that easy when you actually use something like Uber or Lyft or the like to figure out where the user is by just asking their browser via code like this。

 So that's it for Hl， C S and jascript in the problems that you'll explore all of these one more lecture to go in。

 which will combine all of these， But until then， we'll see you next time。어떻게。🎼Offering， okay。🎼よし！

🎼Wow。不。🎼あぶ。🎼Pentmon no， oh， wait。🎼That was amazing， Josh。🎼啊。🎼So飞。🎼あ。🎼没 think。That was perfect。🎼喂。はは。

🎼I think I。🎼G areL。🎼Oh， nice。はい。🎼，🎼う。That was amazing Thank you all Oh good！

