# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P37：36_网络互联协议(IP).zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

Welcome back。 So I hope you enjoyed that。 Now I want to make it real clear that when I give you a 15 minute video of an amazing inventor and computer scientist。

😊，You don't have to remember every word that that person says okay。

 it's more important to get the gist of it， I try to cover the things I really want you to know in my slides。

You might want to listen to it more than once or listen to my slides and then go back。

 but you're not I don't want you to memorize it I wanted to give you smart people。

 I want you to hear from the smart people who did all this cool work in their own words。

 but when we hear from their own words they're sometimes pretty technical so just relax and enjoy listening to these people and understand that you're not going to get everything。

 but hopefully you'll come back and you'll get more and more later so。

The idea was that he really started with this idea of wireless。

 which was we're going to share one medium and the wireless and the wire。

 the Ethernet wire that he built， the coaxial cable that he built。

 was like a giant radio except it ran in the ceiling。

And so the design ended up really simple and that's been good for Ethernet over the years and later WiF is a variation of Ethernet。

 and so it turns out to be sometimes it's best to build something simple。

 but that just make it go really fast and make it really cheap。He also formed the company3com。

 which was one of the first manufacturers of PC cards。

 and so back in the day you would go buy a PC and you would go buy a threecom card and you plug it in the back of your computer and so there was a time when the San Francisco Stadium Candlesstick Park was named。

3com stadium in。Our friend Bob Metcalf， was involved in all of that。

 so he's done many things throughout his life and we're honored to have met him。So。

We started with this four layer architecture that says we're going to break down a big problem of cooperating applications across various kinds of networks。

We're going to break it down and we just got them talking about the link layer。😡，It's literally 20。

000 maybe 50，000 engineers have spent the last 20 years figuring out how to make this work because the layered architecture lets them think。

😡，Although it was informed， they had 20，000，50，000， I don't know， 20。

000 engineers that think about that problem and they ignore the rest of the problems， okay。

 they ignore the rest of the problems。That's great because they've gotten really good at this one problem。

Now we're going to go like， you know， I don't know how many engineers let's just make it up 5 k engineers think about this next problem。

The next problem is called， oh， my color's got to change， the inter network layer。

It is the notion of forwarding。😡，Each of the postcards with a from and the two address。

Forwarding enough times to get them all the way across the network that's the next problem we're going to solve We're going to stop thinking about the link layer we're just going to assume it works。

 it's just magic， that's what a layered architecture gives you you don't worry about the stuff above you。

 you don't worry about the stuff below you， you focus like crazy on the stuff that you're focusing on so。

😡，The link layer only works on one link right， it worries about one link and there might be 15 or so of these links。

But the internet layer worries about all the links and the proper sequence of links to follow to get from UM to Stanford。

That's a kind of complex problem。We're not even going to worry about reliability。

 we are just going to worry about I if I had a postcard with a frommin a 2 address， a packet。😡。

Can I get it there， How will I forward it？😡，I assume the link layer is perfect。

 so the internet layer is the first end to end because if you recall this vertical box the set of boxes is the host starting computer and this vertical set of boxes is the destination computer so in this little raspberry Pi all four of these things application transport IP and the link is all part of this one gadget okay。

So IP is best effort and it's okay to drop data if things go bad and that's one of itsing most charming features。

But what it had to introduce， in addition to the Ethernet addresses or the media access layerer Mac addresses。

 is an address of the destination。Now if you remember the Mac addresses。

 the addresses for the link layer come from the manufacturer。

 the moment this equipment is manufactured， it is burned in a serial number。

But these move all around the world。If this runs here at the University of Michigan。

 it needs one address to connect to the network。One IP address， if it runs at Stanford。

 it needs a different IP address， so we have to be able to change these。

 they're assigned differently。So it's the worldwide number。😡，That is your like postcard address。

 It's like a phone number right， so wherever I'm at， you call my phone and this gadget rings。

 so it's address。Now， that's actually kind of。That example， because I use the same phone number。

 Okay， ignore that。Phones use magic， they use crazy magic。🤧嗯。😊。

So in computers they're not as cool as phones， you have to change the address everywhere you go。

 we'll talk about how you change the address everywhere you go V IP addresses are based on where the station is connected。

They do get recognizedized once in a great while， but not very often。

 and you can even go to various websites on the internet and say IP address lookup is the most common search。

And it will tell you something about where you're coming from right and it would kind of be sometimes really weird because you might be at a Starbucks and it might send it all to St。

 Louis and it might say， oh， you're coming from St。

 Louis even if you're not so you can look it up and you can look up other address as well you can say。

 oh here's an IP address I'm going to look this one up first it starts by looking yours up but you can put in different addresses like in this particular one if I put a different address in here it will actually go look that address up。

So the IP address format， it's four numbers that are separated by dots。

 each of the numbers can be between one and 2 255， and it's just a representation of a 32 bit number back in the day they kept the numbers small because didn't want to use all the computer memory。

And so this is an example of an IP address。Four numbers between 0 and 255 separated by dots。Okay。

 now。The concept， the address is broken into two parts， there is the network number part。

Which is the prefix， and then there is the computer number within network。Okay。

 and it's kind of like phone numbers were before cell phones where the area code。

Was where the phone was and then this was within that area code where to find it and even the older days these were actually geographic too right so these numbers would be neighborhoods or whatever。

 these days it's all electronic so that the precise mapping of a phone number to a geography is less precise and that's why you get a cell phone number and you move to a whole new state you keep your old cell phone number because it's become electronic but in the early days when it was actually relays and switches making a phone numbers work。

 they actually had to do with where。It's actually kind of fascinating how phones work。

 I to teach a class on like how phone switches worked in the 1800s， actually quite fascinating。

Because they were surprisingly simple， that's the interesting part is how simple。Turn of the century。

 well turn of last century phone numbers were。Let's get back to IP addresses。There's four numbers。

Some part of those four numbers is a prefix， we call that the network number。And。

When the packet is in the middle of the network it doesn't really look at these numbers。

 it only looks at the prefix so it kind of thinks of all the packets going to a piece of University of Michigan as 141211 star star and then we assign these numbers within Michigan and then this number is assigned to us by the internet authority that assign numbers so we say。

 hey， we need some more and they give us a prefix then within that prefix we get to set up all the other things。

So。This network number， which is the prefix of the IP address。

 is the way that a packet is routed through the internet as it progresses through the internet。

And so it's sort of like， if I start with。If I start with。My computer here at UV M。

 and that's my number， that's my actual number， and here's a Stanford computer and that's its number。

And I send a packet and I say， okay， I'm going to send it from 1412 11， 144， 188 to 69， 67。

 149 yada yada as soon as the packet enters the network，It doesn't throw the data away。

 but it stops thinking about it， it only looks at the prefix。

 and so it simplified greatly simplifies what the routers have to do as it goes across the hops and the internet。

 it's greatly simplified because it only looks at the first part。

 it doesn't have to look at the whole thing。And then it starts making decisions as to how to get there。

 so says， okay， I'll hop it over here。Then it's like in Kansas City and says what am I going to do here and I'll pick one of those two links and I'll go over here and then as it exits the network it dumps it somehow onto Stanford's campus and then it finds its way oh it didn't find to this one it found its way to that one there you go unpredictable computers it so within the Stanford campus these numbers mean something in the Stanford campus uses those numbers to get the thing to the actual real computer and so it sort of use this prefix you know it has a real number but then it uses the prefix in the middle and then the real number reappears at the end。

 so that's called a network number and it greatly simplifies。It's complex enough。To be in the middle。

And have to worry about all these things coming from。

Kansas City and Beijing and like where these things go to have to look at each one and know where every computer is is crazy。

 so that's why they call it the internet protocol because it says there's one network there's another network and the only thing I care about is the network number and I am the Inter network protocol I internet network protocol I'm just getting these things from one network to another network and then it's up to that network to figure out how to get the darn thing to the right computer within it and it's up to Stanford to figure out how to get it to the right computer at Stanford so these things are called the network number。

It's the prefix of the IP address。Now， the key thing that it's really a beautiful， beautiful design。

The center of the network is both exceedingly complex in one way that it's so big and so fast。

 but exceedingly simple in the other， it just has to move the data from point A to point B。

 and if you think about it it's even simpler。If we look at it from the perspective of this router。

 the router here I've got circled。It just received a packet， it looks at the network number。

 and it actually doesn't even care to some degree where it really belongs。

 it only has one of two choices， it's going to go this way， it's going to go that way。W one's better？

And it turns out if you look at it。Either one would work。Turns out this one is better。

 but if I went this way would just take an extra10 of a second or something right so it turns out the decisions that are made don't even have to be perfect。

You can make the wrong decision and the network automatically corrects that's part of the goal of the network and so it really simplifies and limits the need for each router to understand the entire network which makes these routers。

 I draw them small on these diagrams on purpose because we think of them as small and fast and only solving a really tiny problem but doing it really super awesome。

 so routers maintain。What we call router tables。And they maintain a list of network numbers and the best outbound route。

For each of the network numbers。Now the other thing that they do is they pass routes back and forth and this is how they adapt to errors right。

 they get updated dynamically， they ask each other for the best place。

 if they see a network number they haven't seen before。

 they ask their neighbors then their neighbors neighbors and they go oh okay。

 I got a good way to get to 67， 149 and so there's all kinds of communication。

 but it's relatively slow and it doesn't have to be perfect。

And so it's router tables are what routers have， but they're indexed by the network number of the packets。

 not the host of the destination。 So that's an amazing。

Amazing improvement in the performance and efficiency of the。Internet core， the Ip core。

So it's really quite simple， right， you basically have a local area network on your campus。

This might actually be your house too。House is kind of like a campus。

And you can do all the crazy things you want， hundreds of computers。

 hundreds of servers and thousands of laptops， and you get one address that is the address。

Of your campus。It's the network number of your campus to the rest of the world。

 and then all over the world people can send to you。And by simply looking at the prefix。

 data makes it to you。Keeps this really simple。And really fast。Okay。😊，So it's beautiful。

That's with a network number， one area code， one network number。

 it's the only thing has to be kept track of a whole UM campus can be characterized within the core of the network as basically a single network number now and the reality is it's usually a few of these because they get given to you in smaller chunks so you end up with you know 20 or 30 of these things for your campus if you're a medium to large campus。

Okay。So now I want to talk a little bit about。The problem of computers that move around。

So you have a laptop。And you use it at your local coffee shop。

And then you close the lid and you go home and open it。And it works at home。

 and then you close the lid， and you go to school and you open it and talk to wireless at school and it works。

I was like， hey Dr。 Chuck， you just told me that I have to have this address and I can't talk on the internet if I don't have the right address and the packets are routed based on the prefix of this address。

 why is it that I can be three places， coffee shop， home and school。

 and it seems like everything works well？That's because。

While your computer has an Ethernet address that's baked in at the factory。

Most computers are configured when they first open up and connect to a WiF to ask。

 instead of having an IP address configured in your computer， they send a request out to say，Hey。

I'm new here。Is there anyone who will give me an IP address that I might use for this particular location？

And。If there is an access point， say at your Starbucks， it says， sure。

Use this one you're at Starbucks that's a good number for Starbucks now it turns out that the prefix of this is exactly the prefix that the world sees all the traffic to Starbucks。

 so it's actually kind of a real address。And it gives you an address。

OkaySo you ask when your thing comes up， it asks what can I get and then it's told what address to use。

 so using one address while you're at Starbucks， a different address at home and a different address yet again at school。

So that's called the dynamic post configuration Pro。Now it turns out。With schools and homes， and。

There's just too many computers。To give every computer a real address。

And so we have these special addresses。They're called the non routeutable addresses。

So you'll probably notice if you go to one person's house， you will have IP address of 192。168。some。

 something， go to different person's house， it'll also be 192。168。some。 something。

And they go to your house， and's 192 to168 that something， that something。And you're like。

 how can that work？I seem to have the same address well。

That's because of a technology called network Ad Trans。

Where each of the home routers actually has a unique and distinct address， but you're not seeing it。

 it's giving you a temporary address， an address that really can't run at all on the internet。

 it only lives within the house， but then as your packets leave the house or leave the Starbucks。

The real address is put in and then when it comes back the real address is taken out and your local addresses is put in so they're called non-routable addresses because if they ever escaped into the real internet。

 they'd be like， oh those are for your house， they're only for they're not supposed to go very far and I don't even know where they go。

 they go nowhere。In the core of the internet， but they go properly inside your house。

So the way this ends up working。Is if you are at your coffee shop， the coffee shop has an address。

You associate with their base access point。It gives you a non routeable address to use locally。

 and then as your traffic gets sent。This address is changed to that address， that address。

 you never see this happening， it's done as the packet goes through the base station。

And then when the packet comes back， it comes back with this address。

 but then as it goes to the base station， it switches back to this address。

So even though this address is not the real address the network sees。

 they see you having this address here。So if you would do an IP lookup from a coffee shop。

 the coffee shop will be identified， you will see the IP address here。

 and if you looked at your laptop， your laptop would not have that same address because it's being translated。

In the access point。So then you go home。And at home。Your access point has a different address。

But your computer asks your access point for an address。

And it gets a local address that's generated locally and again theres a mapping。

 it's called NAt NA NA network address translation so as the packet goes through。

 it takes out the one address and puts in the second data comes back it takes the address out and puts the local one in and the same thing happens at school right so you're at school finally and you get a different address theyre not the same but you look and the prefixes are the same it's like they should be the same place but they're completely different because your school has a different address and there's a translation that goes back and forth as the data goes around and round。

 so just for the distance of the local w-fi or whatever use these 192。

 168 numbers and then they're translated to the real numbers by your network access points。

So these are illegal inside this network， so if it ever saw a 192 168。

It would just throw that packet away。They're only for very local connections。So with that。

I'm wondering if by now。You know why？This is funny。I'll give you a minute。Okay。

 so the reason this is funny is she traced the killer's IP address and it had a prefix of 192。168。

Which means the killer had to be within a relatively short radius using likely the same Wifi access point。

 which means it was close。😡，Very scary。I hope you think it's fine。Of course。

 XKCD is never exactly bunny， but it hopefully makes you smile a little bit。So up to now。

I've been talking about。So up to now I've been talking about。

This cloud network that's magic and the packets take different routes and we don't know but they show up remember the mailbox like they just show up or don't show up right so it turns out that sometimes we as engineers want to take a look at what's going on inside the internet。

And it turned out that there was a feature they added early on to help diagnose problems in the internet that we still use today。

 and it's so convenient that it's built right into your operating system。

You Macintosh or Linux trace route is built in and if you have Windows。

 you've got to install trace routeute， so just say Windows install trace route and you'll find something。

But。There was a problem， so if you recall， I said that。

Each router sees the world very narrowly and simply sees a packet and makes a decision one place。

 so let's say that。Here comes a packet on the way to Stanford。

 and these routers are sort of strangely configured。This router thinks it should go there。

 this router thinks it should go there and this router thinks it should go there well it comes in and goes like。

 oh well I know where that one goes there so if you end up with this misconfigured router situation。

You end up with your data going round and round in circles。

It would actually like crush the network because it's like a whirlpool。

You can't even notice that it's happening because there might actually be， you know， 10。You know。

 there might be a bunch of them and then it comes back and you send it around again。

So you're filling up all your bandwidth， it's never going to get there unless something changes and something crashes is not going to change because these routers think that's the best thing to do。

 they're mistaken， but they are， they can be mistaken because they're operating with imperfect information。

So how would you solve this problem？It's like routers are imperfect。

So they solved the problem with a thing called the time to Live field。

So much like the network address translation tweaks the addresses on the way in and on the way out。

 the time to live is a field that routers change every time a packet goes through a router it subtracts one from this field。

And it starts with a number between 25， it can be as high as 255， but it's usually like 25。

And what happens is is every time the packet goes through a router， the number goes down by one。

 so if it was， it would be come in here as 255 then it would go through here 254 and 253。

 it would come back at 252， and what would happen is eventually it would get。

To one of these guys in a hit zero and they would decide， okay， you've been running around too long。

 we will throw you away so the number goes down and it always goes down。But then when it hits zero。

 they throw the packet away， they say you have been through 255 hops， chances are good。

 you're never going to get to your destination。So。The trace route command。Sort of cheats。

 normal packets are sent with a TTL or time to live of like 30， 30 hops or 40 hops。

But what trace Route does is sends broken packets。It turns out that when a router throws away your packet。

 most of the time it is courteous。And it sends you back a notification says hi。I got your packet。

 I decremented it， subtracted one and it got to zero and I threw it away sorry about that' here's who I am I mean I really feel bad about throwing your packet away maybe you want to figure something else out I don't know something must be messed up can't be my fault but I threw it away。

So what trace routeute does is it first sends a packet with a time to live of one。

 so the first router goes like whoa， this has been around a long time， sets as zero throws it away。

 then sends a note back， then trace routeute sends a packet of two across。It goes hop， hop。

 and it gets thrown away and little note comes back。

So you can kind of build a map by sending enough packets and getting kind of a return rejection from one of the routers。

It would have got there， so if， for example， I do a trace route from the University of Michigan to Stanford。

If I did it now， it'd be a different set of things。I get this output。😡，And if I take a look at this。

 this is the hop， so there's the first one， two， three，4， through 14， 14 hops。

 so it takes 14 hops now interestingly again I don't remember what the hop count was in the store and forward days。

 but it's quite a few and that's because it's optimizing geography。

And so you can see the first top is on my campus。Then the second and third hop are bouncing around my campus some more。

 now we don't quite know where this one is， but now it's on a national network called Internet2。

 Internet 2， internet 2， this is probably going across the country and then it ends up on Scenic。

Which I think is sort of California's network， it bounces through California a couple times。

Let's see HR LAX， that's Los Angeles。This is， I don't know where that is Los Angeles。

 now it looks like it's making to Oakland。I don't know。

 there's probably some meaning to these things， so it's making it through Oakland and then it's going to Stanford from something Oakland。

 I don't know。But now it's on the Stanford campus and now it has three more hops to get across the Stanford campus to the Stanford campus'es web server now what's also going on here。

This is's keeping track of how long it's taking， it sends each one a couple of times。

 and so these are milliseconds， so milliseconds are thousands of a second。

 so 534 milliseconds is a half a second。490 is a half a second， so these are like half a second。

 half a second， oh wait， no no， sorry， not a half a second that'd be 4000 well。

1000 milliseconds would be one second， so I got that all wrong。

 so 049 milliseconds is like half of a thousandth of a second， so that's bad。Fast。

 six milliseconds is6，10th of a second。76 milliseconds， which is nine hops away。

That's 7600s or 7100s。So it takes about7100s。So， like。77 over1 thousand0。So no7100， sorry。

7100s of a second。It' less than a tenth of a second。

To get through 14 routers from Michigan to Stanford。Less than10th of a second。Pretty impressive。Now。

 if I do a trace route from Ann Arbor。Michigan to East Lansing， Michigan， Michigan State University。

 we have a very close connection I mentioned the Mer Network where we've had a close connection for a long time。

So not only is it fewer hops， it's only eight hops to get to Michigan State if you look at the hops here I'm bouncing around the campus for。

Three， I'm bouncing through the state for two and bouncing on the Michigan State campus for three。

 so it's a total of eight， two hops to get three hops to get across my campus。

 two hops to get across the state of Michigan and three hops to get on campus and it's really fast。

 it's nine，100th of a second which is。Less than1 hundredth of a second so really fast you can kind of see it now if you ran this trace route more than once。

 this might change， doesn't change too fast， but legally it could change I mean there's no guarantee it's going to be the same it's highly likely it's going to be the same because the most efficient way is not going to change within a few seconds but if you start in the middle of the day and you do it the next day it might change quite a bit so be something to play with。

Run it。Print it out， run it again at midnight， run it in this noon。

 see if your trace route is different， right， be interesting。

So here's an example of a trace route from University of Michigan to Peking University in China。

And so it's， again， you know， it's。It bounces through the state of my campus for a couple of hops。

My campus for a couple of hops， it bounces around the United States for a couple of hops。

And then it starts crossing the Pacific Ocean， it goes this there's traffic actually went through Seoul Korea and then it ended up in Beijing now the interesting thing is you can see that it looks like it's taking about 61。

00s or 6100s。Just over a。Just almost well half the  tenth0th of a second to get across the country and then it starts taking longer and then by the time it's going all the way to China and back。

 it's doing 256 milliseconds， which is about a quarter of a second。Now the big difference here。

Is likely not traffic。It is likely the speed of light。

It is how fast it takes light to get across the Pacific Ocean。😡，So it takes a while。

The reason I think it's most likely to these numbers。Iri。Happy。There。系哋俾。Yes。See the link。

It's low traffic because these are very consistent。Yeah。你国。

prettytty much all the time so that suggests that we're not waiting for any traffic。

 we're getting through as fast as we physically can。

 which is some combination of the speed of the length and the speed of light。So。

We just got done talking about how we add to every packet， this global number， the IP address。

It has the prefix of the network number in the internet part。

 the inter network where it's really moving data from one network to another network and leaving it up to those destination networks。

 how to move it。We end up really simplifying the postcard and the postcard ends up being a really apt example。

But the key thing， especially when thinking about the four layer architecture that the reason that I think TCPIP succeeded was in this real complex problem of moving data between billions of computers。

 it kept the part in the middle real simple。It doesn't try to be perfect。

 it doesn't try to retransmit data， doesn't try to store it。

 it doesn't try to keep it in the right order， it doesn't try to say that if this packet went here。

 I'm going to make sure the next one goes there the two packets one if one gets ahead。

 we don't really care。It means it really fast and really scalable and by keeping it simple and really fast。

It solves really an amazing problem， but we yet have other problems to solve。So I want to close。

This lecture。By introducing you to another person。So Vintsf was a graduate student as the whole notion of packet switching was being sort of examined both in the federal government at the Defense Advanced Research Project Agency。

 DARPA。And in higher education。Both in the United States and Europe， UK and elsewhere。

And so Vinturf was kind of at the right place at the right time and we could be very thankful for that。

 his credit as being one of the fathers of the Arpanet。Which of course， begat the internet。

And so Vint is going to talk to us。In a sense， going back even free aRPpant and bring us up packets and what packets mean。

 and then how that all flowed into the apant and how the aRPpant evolved。To become the Internet。

Enjoy。