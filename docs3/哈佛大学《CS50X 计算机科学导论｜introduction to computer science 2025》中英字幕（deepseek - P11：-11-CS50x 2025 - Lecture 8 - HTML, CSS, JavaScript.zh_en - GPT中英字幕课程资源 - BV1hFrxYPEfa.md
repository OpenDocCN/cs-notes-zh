# 哈佛大学《CS50X 计算机科学导论｜introduction to computer science 2025》中英字幕（deepseek - P11：-11-CS50x 2025 - Lecture 8 - HTML, CSS, JavaScript.zh_en - GPT中英字幕课程资源 - BV1hFrxYPEfa

![](img/7b7b72accfa61f099248c5172dbf9456_0.png)

![](img/7b7b72accfa61f099248c5172dbf9456_1.png)

🎼Yeah。

![](img/7b7b72accfa61f099248c5172dbf9456_3.png)

Allright， this is CSs 15 and this week we begin to introduce web programming that is still writing code ultimately。

 but whereby the user interface is now going to be a browser or even a mobile device ultimately to do that we're going introduce you to first some fundamentals of how the internet works itself then we'll transition to a language not technically a programming language called HTML hyperpertext markup language followed by another language though also not a programming language quite yet called cascading style sheets and ultimately will reintroduce some proper programming so as to automate much of what will be now discussing but first let's begin with what underlies the world wide web or web for short which is the internet itself and it's perhaps simplest to think of the internet it's like the underlying plumbing that allows us to get data from point A to point B So there's lots of computers in the world nowadays they are all physically connected somehow or virtually connected with wires or wirelessly and if you can imagine each of those computers somehow being able to talk to one another that then is our internet。

ternetworked set of computers that can somehow intercommunicate， but it wasn't always that way。

 even though you and I take for granted the fact that we can all talk electronically nowadays online indeed early on there were only a few points of presence on this here Internet So for instance。

 here is the United States in 1969 when Apanet which was developing what we now know as the Internet and there were only a few locations here primarily on the West Coast and those universities initially were indeed able to intercommunicate sending the first emails for instance。

 even before there was a world wide web eventually some other universities came online Harvard。

 for instance among them on the East Coast of the United States and then East Coast and West Coast were suddenly able to intercommunicate as well as with emails and the like but in order to get data from point A to point B so to speak in this case West Coast to East Coast not to mention the rest of the world once more and more servers were introduced to this mix。

 we needed to somehow route the information and so one of our first terms of art today will be that of routers。

Routers are simply computers or technically servers whose purpose in life is to route information from one point to another。

 Now these servers might look a little different from your laptops and phones。 certainly。

 they might look different from your desktop PCs， but they're still just PCs computers that maybe have a different form factor a different shape。

 but that typically live in what are called data centers like big warehouses that store lots in lots of computers。

 Those computers have lots of cables that interconnect them with other computers there as well as other warehouses and data centers。

 much like the dots you just saw on the screen， but the software that those servers are running give them the ability to route information from one location to another。

 So if I hear and representing the server， essentially these devices need to decide when they receive some information in email a web page or the like Does it go this way or this way or this way or this other way and they use software to figure all of that out Now here we have a visualization in the spirit of using zoom from some of our former teaching fellows who acted this out。

😡，You can imagine a teaching fellow named Phyllis wanting to send say an email to a teaching fellow whom you might know。

 in fact， named Brian， well Phyllis might put that message in some kind of envelope here physical but think of it as virtual as well。

 and she's going to hand that envelope off to the next router near her and maybe it's above below to the left or the right。

 but generally this envelope is going to take some path from point A， Phyllis to point B。

 no pun intended， Brian， let's take a look。🎼Yeah。🎼The。

Wonderful so many thanks to CS50's team for making that visualization possible and how well it worked。

 getting the data up down left right from Phyllis to Brian ultimately but how were those teaching fellows。

 how were those routers making decisions Well in this case we actually practice quite a bit but in the real world it's all dynamically figured out via software in some form and the language that routers typically talk in order to figure out how to get from point A to point B is a language or really a protocol called TCPI which is technically two protocols together that each do a little something different and in fact let's focus on the one that's probably generally familiar to many of you namely IP so even if you're not a computer person odds are at some point you've heard of IP perhaps in the context of an IP address IP stands for internet protocol and you can think of this as a language or a protocol to be more proper that computers speak when trying to send information between each other and a protocol is really just a set of conventions and so for instance。

In the human world， much of it， if I were to extend my hand to you upon greeting you for the first time。

 most likely depending on where you're from， you would know instinctively to like reach out with your hand and shake my hand completing a human protocol so it's not so much a language that we're speaking but a set of conventions and indeed that's what TCP and IPR but IP is very specifically focused on addressing servers in the world so what do I mean by that well it turns out that every computer in the world that's connected to the internet has what's called indeed an IP address。

 a unique identifier that typically is of this format something do something do something do something where each of those something is a number。

 a simple integer， those integers are typically0 through 255 which is to say that you have four values in a typical IP address that's between zero and 255 if you're doing some mental math now you might recognize those numbers anytime you're counting from  zero to 255 you're using8 bits or one byte which is to say。

😡，An IP address as represented here with these hash symbols is 32 Bs in total or 4 bys。

 so your mind can immediately start to wander if you do some of that mental math to conclude that oh。

 it would seem that you can have no more than per past discussions4 billion IP addresses because two to the 32 power gives us 4 billion especially if we don't have to worry about negative numbers。

 which is to imply that there can only be 4 billion devices on the internet in total now that's a lot。

 but there's also a lot of humans in the world and there's a lot of humans with multiple devices。

 laptops， desktops not to mention all of those servers and Internet of things devices So the world not only uses this format nowadays。

 which is technically called IP version 4 there's also a new and improved version of IP addresses known as IP version 6 which is the world is starting to use especially some of the bigger companies and Internet service providers out there but odds are your computer in my computer still tend to use IPV4 this format so we'll focus on this。

One， if only because you're likely to see it in the near term in the real world as such。

 So how does this all work？ Well， this is perhaps the most cryptic looking diagram I could find that represents。

Exactly how IP works。 Now， this is sort of ASI art。

 and this is actually a diagram from the specification or RFC request for comments that defines how IP the Internet protocol is supposed to work and what this diagram is implying is that any time you want to send a message over the Internet using this protocol called IP you first have to make sure that you write an address on the envelope and you write another address on the envelope that is your sender address or source address And the way you do this。

 of course， is not something physical in an envelope but rather you use a sequence of bits that indicates what the source IP address should be。

 and what the destination IP address should be。 And then let me wave my hand there's a whole bunch of other bits being used anytime you send information on the Internet in addition to that source address and destination address。

 So this though is essentially written on the outside of this envelope in this here way。

 Now what does that really mean， Well， let me make this a little more concrete And just for the sake of。

Suppose that Phyllis， in our example， was sending indeed an envelope virtually to Brian from point A to point B。

 then let's suppose for the sake of discussion that Brian's IP address is a number like one do2 do34 So metaphorically what Phyllis would do or really Phyllis's computer would do is write that I address right in the middle of the envelope just like a human would when addressing a letter in the real world。

 But so that Brian could potentially reply to her either with new information or at least to acknowledge receipt of the same envelope。

 She's also going to put her IP address in the top left corner and maybe her IP addresses 56 do 78。

 Suffice it to say I'm making up these numbers to keep them simple。

 but they could be actual IP addresses because they fall into that format of something do something do something do something。

 And so now when Phyllis hands this envelope off to the person or the router next to them next to her that router can look at the same envelope realize。

 oh， this is going to address 1。2。3。4， I might not be physically next to Brian that IP address。

 but I can at least hand it off to some other router that might be closer to Brian and therefore know how to get it to him eventually and so what routing is all about is exactly that these servers passing off metaphorically these envelopes back and forth back and forth。

 ideally getting them closer to their destination Now unlike the real world where the shortest distance between two points is a straight line。

 you might recall that Phyllis didn't actually hand that envelope up into the right diagonally to Brian rather and up and down and it didn't necessarily follow the shortest path。

 but in the real world， routers might at least ideally route data in the fastest way possible So even though they might traverse geographically disparate routes sometimes because the servers are faster or less busy it might make more sense to spend a little more distance to get the data there based on how the servers are configured and also finances might be involved。

 There's a lot of big internet service providers in the world， the Comcast。😡。

Aizons of the world in the United States， for instance。

 they might have relationships with other Internet service providers so that they want to ideally keep data on their network so it's to not have to pay fees to route the data on someone else's network。

 so to speak。 So there's lots of ingredients that go into deciding how to get the data from point A to point B。

 But in general， it doesn't really take more than 30 hops so to speak。

30 passings of the envelope from router to router because at that point。

 it's probably stuck in a loop if it's going on for more than say 30 such hops。

 So what's really written on the envelope is more arcane information like this。

 but it's just patterns of bits。 So it's as though Phyllis was just writing patterns of zeros and ones on this envelope that it here to this pattern And then inside of the envelope is what Phyllis might actually want to send Brian。

 Now what might that be。 Well as you know the Internet is filled with cats。 And for instance。

 here is one such picture of a very happy cat。 Unfortunately， it's a pretty big picture。

 And if you can imagine this being maybe a video instead it would be。Big in terms of its file size。

 even more bytes。 And so what computers typically do is they additionally fragment information when they're sending it on the internet。

 so rather than try to shove this big cat inside of that envelope。

 what a computer would do though this feels a little sacrilegious would be to tear happy cat in two maybe even into four parts and then put each of these fragments inside of an envelope followed by another fragment inside of another envelope at which point to be fair。

 Phyllis had better address the second envelope as well。

 probably with the same amount of information So she would probably put1 do2。

34 on the middle of the envelope and 5。6。7。8 in the top of the envelope to indicate that this one2 is destined for Brian's IP address as well。

 Unfortunately， once we start chopping things up into fragments like this。

 it's no longer sufficient for the outside of the envelope to indicate only the destination because。

If they arrive in this order or maybe this order or some other order altogether after all。

 there's nothing stopping Phyllis from handing one envelope here and another envelope here so long as they eventually make their way to Bryan So he's going to need a little more information in order to reassemble this data at its destination and no ultimately just how many total envelopes were sent to him so how can we go about doing that well let me propose that we introduce another protocol as well that will help us guarantee delivery of this information So there's this other protocol TCP and it's typically written or set in the same breath as such that we talk about TCP but it's a separate protocol and TCP's perfect purpose in life is to solve a few problems for instance。

 among the problems that TCP does for us is it ensures that we acknowledge exactly how many envelopes were sent so for instance on the outside of this envelope we might write not only the destination and the source address but I'm also going to say something like。

One of four in the memo field of the envelope。 we don't often use this in the real world。

 but if you were to you could put it down there and then in the other envelope。

 I might write two of four and so that now Brian upon receipt of that can see that oh this is the second such envelope and I could keep doing this for number three and number four and what this allows Brian to do ultimately is not only confirm that okay I got pieces one and two and three and4。

 he can also infer if he's missing any pieces， lest he have a very unhappy cat that's missing an entire quadrant of that their picture so TCP accordingly can help Phyllis guarantee delivery by establishing an additional protocol on these virtual envelopes that dictates that we also keep track of the sequence numbers of these here envelopes so that Brian can infer if anything has been missed otherwise he can acknowledge Thank you Phyllis I got all four of these but there's another problem that TCP solves for us which is that the internet itself does so many different things nowadays。

've got email we've got the World wide Web more on that soon。 We've got video conferencing。

 We've got streaming media and so many other applications that run on top of the physical infrastructure that is the internet So what else does TCP do it also defines a convention for what we're gonna call ports a port is simply a unique numeric identifier for a specific Internet service and years ago。

 a bunch of humans decided to standardize what these port numbers are So for instance。

 a bunch of humans in a room decided that you know what to uniquely identify worldwide web traffic。

 let's use port 80。 So the number the integer 80 but if it's securely sent using not HttP but Https more on those also a bit later then it's going to use port 443 and there's other numbers as well 25 for instance is commonly used for email53 is commonly used for DNS and there's other integers as well much longer list than the two here on the screen What Phyllis can then do is if she specifically wants to request a web。

Of Brian， whereby Brian is now not only the recipient， but a web server that has pages of content。

 what Phllis can do on the outside of this envelope is add essentially a colon and then a port number。

 such that now the destination is still one。2。3。4 colon 80 and this indicates that when Brian receives this envelope。

 he as a server knows that this envelope is destined for， not the email server。

 not the video conferencing server， not the streaming media server。

 but rather for the web server that happens to be running at Brian's location and in fact this is because as an aside when we talk about a server。

 a server singular can actually do multiple things。

 a single server can handle email and web and video conferencing and more and so what these port numbers ultimately allow servers to do is to multiplex so to speak or distinguish which server or which which type of server should be handling this inbound request so that Brian replies with a web page and not for instance。

 an email or。Something that's inappropriate like that。 Meanwhile。

 if we want to get a little our hands a little dirtier with the underlying format of these things。

 even though I wrote it on the outside of the envelope as just colon 80 what's really happening underneath the hood is a little something more complicated like this whereby Phyllis would write not only a destination port but also a source port So it turns out even Phyllis uses a unique identifier so that Brian knows how to address his response to her specifically and there's that sequence number and the acknowledgement number that I alluded to earlier whereby TCP ins that we can keep track of one of42 a4。

3 or44 or4 So long story short， what TCP IP together allow us to do is uniquely address computers on the internet as by using IP addresses in a standard way and to guarantee delivery of data between two points by using these sequence numbers and as well as these port numbers to make sure that the data gets where it needs to go Now I'm using guarantee a little bit generously。

If the internet goes down， the power goes out， TCP is not going to get data from point A to point B。

 but assuming the internet itself is working， that is what these protocols。😡，Together do。

But to recap then with TCPI， we have this mechanism for addressing computers uniquely。

 much like we do already in the real world。 and in fact， Sanders Theater， for instance。

 is 45 Quincy Street， Cambridge， Massachusettss 02138 USA that is exactly what you could write on the outside of an envelope to mail it physically to Sanders The what we' were talking about then with these virtual envelopes is exactly the same idea。

 but in a way that supports servers sending the same data and it turns out that just dealing with numbers like IP addresses is much easier than full text like things on the outside of our own envelopes indeed imagine how much happier the mail service。

 the postal workers would be if all we were writing were very clean numbers on the outside of the envelopes and they wouldn't have to read messy handwriting with much more complicated strings of text All right so it stands to reason then that this seems to work。

 at least as I've told it here but of course none of us probably use IP addresses explicitly every day。

😡，In fact， when you go to a website you probably type Google co or c50。

 AI or other such domain names and yet here I am telling the story that underneath the hood Allah Phyllis communicating with Brian everything uses IP addresses not to mention port numbers and sequence numbers on the outside of these envelopes well suffice it to say your Mac。

 your PC your phone is somehow figuring out how to write those numbers on the envelope even though you and I is the humans are only typing in actual domain names like Google co CS50。

 AI and the like so how does that all work well in the world of the internet。

 there's other types of servers out there as well not just routers that route data from point A to point B there's also DNS servers as well domain name system servers and these typically live inside of your Internet service providers network or on your university's campus or in your company's office or somewhere in between you and the rest in the world and what a DNS server does in。

Short is translate domain names to IP addresses so that you and I as humans can type the more user friendlyriend version of Google co and cs5 Ai and you and I don't have to worry about or figure out what the underlying IP addresses are Now it turns out the implementation of a DNS server follows a familiar paradigm we've long talked about dictionaries now a abstract data type that allows us to associate keys with values Well in the case of a DNS server。

 they essentially have inside of their memory， a two column sheet or table the first of which is the domain name。

 the second of which is an IP address， technically those domain names are called fully qualified domain names because it might be something like Google co or www Google co or some other subdomain therein。

 So what it is you type would be in the lefthand column here and what it is that gets written on the envelope would be in the right hand column here instead。

 So now this table you can imagine it being very， very big。 I mean there's thousands。

 hundreds of thousands of millions。Of domain names out there nowadays and surely your phone in your pocket doesn't know about all of them。

 but that's okay because the design of DNS is actually to be very hierarchical so that your internet service provider probably has its own DNS server that can translate many domain names to IP addresses。

 especially if they're popular ones and therefore they have looked up the IP address already in the past for their customers but if you visit a random website that's not very popular and no one has visited at all or recently your Internet service provider can recursively ask another DNS server for the answer to the question。

 what is the IP address of that domain name and in fact around the world there are what are called root servers a small number of servers that for instance。

 know about all of the do cos and all of the org and all of thegos and similarly for other countries as well whereby those servers even if they don't know the exact IP address they might know the IP address of another DNS server who does have the。

And so long story short， if you've ever bought or really rented your own domain name before or if that's something you choose to do in the future。

 essentially what you're doing when you pay someone some number of dollars per year to buy a domain name is you're asking them to add an entry to their DNS server or someone's DNS server that associates that domain name henceforth with a specific IP address of your server or server So someone somewhere is doing that for you。

 but the whole process is indeed recursive because if your ISP doesn't know the answer。

 it can maybe ask another DNS server or maybe these root DNS servers as well your own Mac。

 your PC your phone might itself cash or remember these answers though too because it's a little silly in terms of design if your phone or your laptop or desktop has to constantly ask that same question every time you visit Google co odds are the IP address is not going change or at least it's not going to change that frequently However。

 again， if you've ever set up your own domain name if you removed it around or。

Has changed about it Sometimes you can break a website by changing its IP address because there's lots of servers in the world that have cached CA CHED or remembered the old IP address but thankfully the other feature that DNS provides is expiration dates so essentially the answer to the question what is the IP address for this domain name typically expires after a few seconds。

 a few minutes， a few hours， a few days unless you really mess things up and say don't expire this for a year then your website could in fact be a dead end somehow so this is worth knowing for future web developers doing things in the real world So DNS to recap then simply converts IP domain names to IP addresses and technically can go in the other direction as well and so when you as a human go to a browser on a laptop desktop or phone and type in Google co enter or CS50 AI enter what essentially happens is your device checks its local cache to see if it's already been asked that question before。

If it has， it just immediately knows the IP address writes it on the outside of the envelope so to speak and sends out your data。

 if it doesn't know the answer， your computer is can ask the local DNS server。

 which might ask another DNS server， which might ask another DNS server。

 but recursively you will eventually get your answer if that domain name actually exists and at that point your computer can indeed write the correct IP address on the outside of the envelope。

 add any sequence numbers， add any port numbers， and voila， it's on its way from point A to point B。

😡，So that then is DNS。 How about one other acronym that's a bit related here to that of DHCP。

 And let me assure that it's not really that important to memorize like what all of these acronyms stand for。

 but rather it is useful。 I think to generally know what they， in fact， do。

 So DHCP is dynamic host configuration protocol。 So there we have it another protocol。

 set of conventions， and the purpose of DHCP is to actually give your computer。

 an I address when it boots up。 This wasn't always the case back in the day。

 if you've had internet connectivity for a while， some technician probably would come to your house when you or your family signed up for Internet service。

 they would probably have a sheet of paper on which was your personal IP address。

 And if you wanted to connect your PC to the Internet。

 they would like type that I address manually into your computer so that your computer knows what I address to use when talking to other servers。

 That's not particularly scalable。 That's not particularly maintainable。

 You don't want the technician to have to come out。

To make a change or something like that and you probably want to be able to use multiple devices as well and so nowadays what most computers use is DHCP to dynamically figure out what is their IP address and so nowadays when you first open your laptop in the morning or boot up your PC or take out your phone if you haven't used it in a while and therefore it no longer has an IP address because these two expire after some amount of time your phone your device will broadcast a message like what is my IP address and hopefully on the nearby network in your home in your company at your university or in your Internet service provider more generally you will hear an answer oh use the IP address for5。

6。7。8 for instance in the case of Phyllis or 1。2。3。

4 in the case of Brian's recipient address as well so the people who run these servers。

 the internet service providers of the world the system administrators at your company or campus they can come up with the rules via which these IP addresses are assigned or who gets what number。

But ultimately， DHCP is just another protocol that governs how your device gets its IP address。

 but that's not quite everything。😡，It's actually kind of neat。

 DHCP servers also tell your computer what DNS server to use。

 They give you the IP address of one or more DNS servers to ask questions of DHCP servers also tell you the IP address of your default gateway the router that you should use by default to hand one of those envelopes And this is indeed why Phil is probably new to whom to hand that envelope in the first place。

 because when she booted up， so to speak， she was assigned an I address。

 she was told what default gateway to use and the default gateway Aka router。

 these are just synonyms is the device to which she should hand off data by default in order to get it from point A to point B。

 So why do we focus on all of these acronyms all of these technologies。 on the one hand。

 there's sort of omnipresent。 And even though you might need not need to say these acronyms verbally all that often you're going to see them on occasion when something goes wrong。

 you're going to need to troubleshoot things like this。 But more importantly。

 they're sort of representative of very real world engineering problems that the world has had and encountered over the years。

They're relatively simple solutions there too， know I don't necessarily know how I could write code to implement a DNS server or DHCP server and perhaps neither you。

 but it sounds like a pretty simple idea。 If I have the ability and code to hear requests。

 I can respond to those requests by maybe using a dictionary and memory and in the case of a DNS server and responding to those answers。

 So this is to say all of the fundamentals， all of the ideas we've been talking about throughout CS50 really are used as building blocks to solve these very real world。

 very omnipresent technologies that you and I now take for granted。😡。

Every day let's now consider one other protocol that's with us every nowadays that of HttP hypertext transfer protocol。

 which is indeed itself a protocol， a set of conventions that governs in this case。

 how web browsers and web servers intercommunate it is very much related to Https which is literally the secure version of that somehow uses encryption somehow scrambles the data to ensure that when you're visiting a webage。

 you and only you can see that web page and no one in between you on the internet actually knows what it is you're looking at or the specific URL that you are visiting beyond the name or the IP address of the web itself。

 So even though you and I probably don't even bother typing HttP colon or https colon odds are nowadays you and I just type Google co enter CSs5 AI enter or you click on a bookmark underneath the hood this protocol is everywhere and those prefixes HttP and Ht。

YesColon are required when using a browser even though your browser automatically tends to insert those prefixes automatically if you the human don't bother typing them yourself so they're used of course in URLs you uniform resource locators which specifically are the addresses that we use to get to useful information on the worldwide web or web for short here for instance is one of the simplest URLs we can talk about I'm going use https deliberately to imply that you really do want to try to use secure sites alone nowadays but this domain name would seem to be wwwex co or that's the fully qualified domain name itself but let's tease apart what's going on here typically in your browser you might see a trailing so a forward at the end of it which just indicates albeit not obviously that you want the default web page at that domain name in particular you want to be able to access whatever the default content is for that website nowadays。

rowsers like Safari and Chrome and even others tend to hide these details just to simplify what you're actually seeing in your browser。

 But typically， if you click or double click on the URL bar in your own browser。

 you'll see more information including this trailing So if you only type in Google co enter probably your browser is automatically app the forward to indicate you want the default homeage。

 But sometimes there's more to the URL sometimes it path whereby path I just mean a folder or a file name or something along those lines and that's more specifically referring to like probably a directory on the server containing some web page specifically sometimes it's more explicit sometimes a URL might literally end in html which is going stand for hypertext markup language。

 One of the first languages we'll soon look at in detail。

 and that's the language in which web pages are written So with this URL indicates is that at the server called www example co there is a file called file htl that this user wants to see in their browser。

and it's not often the case anymore that you see these file extensions。

 the world decided years ago that these are just kind of ugly and not strictly necessary technically So sometimes you'll just see slash folder which just means there's a folder aka directory somewhere in the server whose web page content you want to see sometimes it's nested sometimes it's a folder and then a file inside of which is the web page content that you want to see So in short URLs generally follow this kind of format and there might be zero or more of these folders and maybe a file name explicitly or not but what else is going on here here we have the fully qualified domain name and just to toss out a bit more jargon technically when you say domain name typically you mean something like this just the example co because the wwW in this context is generally referred to as a host name it's like the name of a specific server at a company at a university that is providing some service like this the worldwide web aka a web server it is not。

Trictly necessary for a server to have a name of WWW just to be a web server for many years。

 MIt's website was web mit edu， whereas everyone else in the world was using www。

 but odds are many of you are probably not even the habit of typing www something do something rather you type in Google co and hit enter and the browser somehow automatically brings you to www do go co So the host name is the name of a specific server。

 the domain name is typically just something like the example co and let me justclaim that's a bit of a white lie because if you're Google if your're meta。

 you' any of these big companies， you don't just have one web server。

 So technically the www refers to a collection of servers。

 maybe it's two maybe it's 20 maybe it's 20000 servers。

 there are technologies that allow you to support that as well。 But lastly。

 there's one other piece of jargon that's worth knowing the last part of these fully qualified domain names is known as the TLD or top。

domainomain and that is what generally historically indicated what type of domain it is in the US co means commercialgov means government org means organization。

 However， there are so many more toplevel domains nowadays and in fact。

 they're not US centric and in fact just because you have co does not mean you are in the US it just means that you paid someone to use that there domain name。

 In fact， there's other TlDs2。 every country has its own U for the United States UK for the UK Jp for Japan and so forth。

 Anytime the TLD is just two characters that's a country code。

 And yet that's kind of curious because we're in the habit of using CSs50 AI。

 there are websites that use do TV there are websites that use do I O C50 included and if you'd like to go down that rabbit hole feel free to Google toplevel domain or TLD and any of those and you'll actually see that even though we are using CS50 AI to imply。

Artificial intelligence AI has nothing to do with artificial intelligence except that that is how you can abbreviate it in English as an acronym。

 It actually is a two character country code and that country and others have decided to actually monetize the TLD by selling it to really anyone who's willing to pay per year to use that there TLD So lastly within these here URLs we of course have the actual HttttP or Https and that dictates the protocol that is going to be used when a web browser requests a web page at that their address Now what does this protocol do It's similar in spirit again to sort of a handshake whereby a web browser when it wants a web page kind of like extending a hand hoping that the web server will respond and know what to do of course there's no such handshake physically here but rather metaphorically the web server should know how to respond so long as the web browser standardizes the message that it sends So what do I mean by that Well let me propose。

That inside of this envelope can be one of two messages。 and this is a bit of a simplification。

 But the first of those messages is get。 and what get means is literally get me a specific web page。

 By contrast， you can use post inside of these envelopes and post generally means to send information somewhere else。

 And this too is an oversimplification， but generally the word get is used by a browser。

 when it just wants to get information。 The word post is used when it wants to send information。

 often sensitive information like a credit card， an email address。

 a password or anytime you're sort of filling out a form。

 it's generally sent via the post keyword instead。 and these are indeed verbs like get and post or both verbs and English implying that this is some here action。

 Now do dot do means that there's other verbs that can be used inside of these envelopes as well。

 but let's be more specific inside of the envelope that's being sent from browser to server is more specifically a message like this。

 So if I with my browser visit www Harvardu。

![](img/7b7b72accfa61f099248c5172dbf9456_5.png)

The message that goes inside of that virtual envelope as we discussed earlier。

 is literally text that looks quite like this。 So the cat is gone。

 there's no more pictures of cats just yet。 if you're just requesting Harvard's own homepage but inside of that envelope is indeed get HttP2 for instance then host then the actual host name or fully qualified domain name that you are seeking and do do there's some other stuff there。

 but that's what's inside of that envelope hopefully what's gonna to come back from the server is another envelope inside of which is a response So whereas the first message a request to get something the response is indeed a response that hopefully contains the actual web page that you requested and you'll see that the response might look like HtP2200 and then content type text Hm which just means that the web page is written indeed in this language we're about to spend time with today Html below which is the actual content So how can I actually go about seeing some of this let me。

Go over to VS code and up until now we've been using VS code for the purposes of writing code。

 but we do have this terminal window and the terminal window gives me access to an underlying operating system。

 That operating system recall is called Linux and I have a command line interface here And up until now I've been using this command line interface for commands like CDd and Ls make debug 50 Python SQL lights 3 and the like but there's other commands that typically come on a system including this one that allows me to make internet requests as well。

 not even with a browser but textually Moreover， there's always been even though I generally hide it during class a second tab namely ports And if you yourself look at cs50。

 after logging in odds are you will see a ports tab among others and what you'll see here is that all this time CS50s own development environment has been using by default a TCP port number namely 1337 which is a very elite number for us to use And that is the port number that's used by C。

These customizations of VS code， our socalled extension uses that TP port number so that when our extension is talking to Vs code。

 it uses a standard port number on the outside of its own virtual envelopes， if you will。

 you as users don't need to care about that but that's why that tab all this time if you've seen it has had numbers in there and soon we're gonna see some additional numbers as well but if I go back to my terminal window here。

 I of course could type commands and one of the commands I could type is actually this let me increase the size of my terminal window let me go ahead and type curl which means connect URL dash capital I and now let me go ahead and type in https colon www Harvardvard edu I'm gonna manually type this into my terminal windows command line interface and see what comes back I'm gonna hit enter and I get a bunch of stuff back。

 that's why I use a dot dot dot on my slide a moment ago but in this output is some familiar text now we saw this line earlier on my slide HttP2 and then。



![](img/7b7b72accfa61f099248c5172dbf9456_7.png)

Number 200。 And then there are other lines here that I waved my hands at earlier because they weren't strictly necessary。

 including the hostline。 If this server is only doing one thing。

 we don't even need to clarify that this is www Harvard。

 But what then is this HttPlash2 and this 200。 Well。

 it turns out that the two is's just a version of HttP that my browser or my keystrokes we're using a moment ago。

1。1 is a common version number2 is a common number 3 is catching on over time。

 but this just indicates what version of the protocol， the browser and server are speaking。

 even though this browser has no graphical user interface。

 It's just a command Simulating HttP request to get back these headers。 And that's in fact。

 what I means Show me just the headers。 I don't want to see any cats or Harvard news。

 I just want to see the headers inside of the envelope。

 But it turns out all this time for as many years as you've been using a browser you could actually do this in your own browser is well。

 Let me open up another tab here。 and let me manually go to Https。

wwwharvardeddu enter and what I'll see here is Harvard's homepage as of right now today。

 it all worked as you might expect， but it turns out all this time you've had access to some powerful tools underneath the hood let me actually right click anywhere on this web page and select inspect and that's going open what are called developer tools in the context of my browser which is Chrome Most every browser nowadays Safari edgedge and others have similar looking tools though you might have to access them by a different menus and in fact in Chrome you can also go up to the do do dot menu and find your way to developer tools but there's a lot going on here but what I'm going to do is go to the network tab here for a moment and I'm going to zoom in just for the sake of legibility and notice here that when I clear this network tab this is giving me access essentially to a log of everything that you're about to see on the screen and notice it just undele it itself apparently Harvard is doing something behind the scenes every few seconds。



![](img/7b7b72accfa61f099248c5172dbf9456_9.png)

Why that row reappeared because indeed I'm trying to record my network activity。

 but let's go ahead and do this。 Let me clear that one more time and reload the page and so many rows just flashed across the screen。

 In fact， in the bottom left hand corner， you'll see that my browser unbeknownst to me may not one but 67 HttP request。

 That's how many envelopes essentially went back and forth between my browser and Harvardeddu a moment ago Here comes another and if we just keep this open。

 It's gonna come again and again， Harvard is kind keeping the page alive but let me zoom out and scroll back to the very top of this and focus on just the first page I requested and click on www dohar doeddu and let me click on headers here what I'm seeing is diagnostic information if you will about what I just did and you'll see that the URL requested was indeed this thing here。

 I used a request method of get unbeknownst to me get is what is used by default when you just type a URL and hit enter then the status code that came back there's that 20。

So it turns out that what web servers and browsers have done over the years。

 thanks to HtTP is they have standardized what these numeric codes are to indicate success or failure in the world of programs that you and I have been writing。

 we typically use zero to indicate success and maybe one or two or some other integer to indicate failure in the context of the web it's kind of the same idea but the web uses 200 to indicate success and other numbers to indicate failure or something else happening as well。

 Well， what else can those status codes represent。 well。

 let's take a look here notice that when I'm in my browser and I go to simply Harvard with no Https no colon。

 no www noing enter it all just sort of works and brings me to the intended place Now why is that Well at the lowest level。

 we can actually see this in our command line interface。

 Let me go back to my terminal window which I've still full screen and let me type this time curl capital I。

And then simply http colon shareddu so I'm going to help the program a little bit and provide it with the protocol。

 but I'm not going to provide it with the secure version and I'm not even going mention www let's see what comes back ideally it's a 200 okay because that's what means success but what I see here is weirdly that Harvardeddu has moved permanently and this time the status code coming back from an older version of http in this case 1。

1 instead of two apparently has a status code of 301 So it turns out that different types of responses indeed have different numbers associated with them and 301 means moved permanently a sort of redirection if you will and where is Harvard's new location。

 well if we scroll down among these headers， you'll see that oh the server is additionally telling me that the location to which Harvard has moved permanently is https colonhared so what this seems to indicate is that Harvard server really wants me to stay on the secure version of the website All right。

So let me go ahead and highlight and copy that。 Let me go ahead and do curl and that URL。

 So almost the same except for the https this time and the trailing s and hit enter But this time to notice and this time the server is using a newer version of the protocol。

 We're back to version 2。 It's still telling me 301 It's not berating me by saying move permanently again。

 but 301 is enough for me the browser to know oh Harvard's website is now at this location。

 wwwv do again using https And so let's do this one more time let me go ahead and copy that URL and do curl and that full URL and now we're back to getting a 200 okay So among the reasons that your browser is able to figure out what you want is because one the server might be telling it no go here No go here now you're in the right place。

 And frankly， browsers nowadays in cooperation with servers that are configured in a certain way will tolerate you typing in only。

Harv and just no proactively no no no no， you don't want that。

 You want Https and you want the www because the browser， for instance。

 has seen that response before from the server。 But at the end of the day it's really just the status codes that are enablinglabelling us to actually forge these responses。

 So we've seen a couple now。 We've seen 200 for okay we've seen 301 for move permanently there's bunches of others as well。

 including for instance， this one here odds are most everyone here has seen 404 at some point in their lives。

 I mean it's sort of in the human vernacular we all know that 40 means file not found like the URL is wrong。

 The file was deleted。 something is missing That's a little weird that we as humans have been acclimated to a fairly esoteric httP status code but that's all it is if you visit a web page that simply does not exist。

 you will get back not 200， not even 301 you'll get back a similar header like this saying 404 file not found Now you might see a web page and it might be a cute web。



![](img/7b7b72accfa61f099248c5172dbf9456_11.png)

![](img/7b7b72accfa61f099248c5172dbf9456_12.png)

It might be a black and white text only webp page。 It depends how the web server has been configured to show you that information。

 but 404 indeed means file not found。 And here's a non exhausthausive list of other status codes we've seen 200301 there's other 300 level status codes that generally refer to redirecting the user from one URL to another the 400s generally indicate user error like your fault。

 my fault So 401 is unauthorized 403 is forbidden like you haven't logged in properly。

 404 is not found 418 is actually in April fools joke from years ago I'm a teapot was sort of a funny joke among engineers more on that if you Google it if you'd like500 range errors means server error So someone screwed up maybe not you but frankly in a couple weeks time when you're writing webbased applications yourself anytime you see a 500 it is your fault also so you are both the user and the server in that their case but long story short the way these things work are simply underneath the。

via these status codes， which really are being sent virtually inside of envelopes like these。

 your browser is generally hiding that detail because normal users don't need to care about this level of detail。

 but you've always had the power of opening your own browsers developer tools and poking around and seeing these things and all I'm doing in my black and white window here with curl which connects me to a URL using a command line interface is showing you even more in detail what's inside of those envelopes。

 but it's just another way of viewing the same kind of information Now we can actually have a little bit of fun with this with a smile and a win to our students at Yale who are perhaps watching this now it turns out has anyone ever been to this URL here safetyschool org I'll zoom in here in a new tab has anyone applied to safetychool org or visited safetyschool org we love them equally but turns out if you go to safetychool org。

 you end up at this here website which。

![](img/7b7b72accfa61f099248c5172dbf9456_14.png)

![](img/7b7b72accfa61f099248c5172dbf9456_15.png)

By zoom back in is apparently https colon www yaleedduu。

 So what is going on there Well I could open my developer tools but let me use my newfound command line skills and do it here。

 curl I Http colon safetyschool org enter and you'll see that oh safetychool org has moved permanently to Yaleeddus on website So this is to a practical joke that has lived on the internet for years。

 there is someone out there I don't know who they are。

 they have been paying an annual fee for years now simply to have this esoteric joke for us computer scientists。

 there are ones for Harvard as well in all fairness but this is one that's perhaps been around the longest So somewhere there's a Harvard alum who's getting older and older but is still paying this bill year over year since the web was invented。



![](img/7b7b72accfa61f099248c5172dbf9456_17.png)

All right， we're back and we now focus on Hm hypertext markup language。

 which is the language in which web pages are written。 It is not a programming language。 and as such。

 we won't need to spend all that much time on it because the basics of Hl are fairly straightforward。

 even though it has a decently large vocabulary， different features that you'll pick up invariably over time。

 What Hl does have fundamentally are what are called tags and attributes。

 These are the basic building blocks of the language。 and what the language looks like is this。

 So here is perhaps the simplest webp page that I could come up with a hello world webpage。

 if you will。 and it's just text it is text that's typically stored in a file like index do hml for short。

 And in that file would just be these lines of code。

 and these lines here are going to indicate to the browser what it should do upon receipt of an envelope containing this message。

 Now， how are we going go about serving up this content。 Well。

 ultimately we just need to put this content on an actual web server。 Well， it turns out。

You already have a web server even though you haven't been using it as such in other words。

 when you visit cs50。 dev and use vs code in the cloud。

 you're obviously using a browser but you're less obviously using a web server that is serving up a copy of vs code to you in that browser but the caveat there is that by default you've probably been the habit of typing cs50。

 dev enter and you've probably noticed if not prior to today after today that the full URL ends up being httpsco cs50。

 dev and then maybe some other stuff after that but implicit in that URL is one of those port numbers that we saw in TCP either 80 or 443 because it's https it's actually the latter 443 which indicates implicitly that there must be a server on cs50。

 dev that is listening for requests and is serving up that version of vs code in fact we eventually redirect you to Githubs version of VS code aka code spaces but the idea。

The same and in that URL you have a web page that's being served up to you。

 but it's already running on port 443 and perhaps 80。

 which is to say if we want to come up with our own web server。

 we could like start up our own server connected to the internet give it an IP address and then communicate with it using port 80 or 443 but it's actually a lot simpler to embrace the reality that any server can have multiple server be it web or email or video conferencing and the like or heck two different web servers And so even though vS code in the cloud is already running a web server because that's indeed how it works there's nothing stopping you and me from inside a VS code starting a second web server so long as we choose a different port number a different TCP port that's not already being used by the server itself So how are we going to do that。

 well we're going to introduce you to a new command today called quite appropriately HttP server This is a command that you can run in your terminal window that will start your very own web server。

Default on port 80808080 isn't that special， but it tends to be a convention whenever you want to run a web server on a port other than 80 by default。

 you would just use 8080 as a go to。 but it could really be any number within a large range。

 Now this HB server command is going allow me to serve up some actual content。

 What might that content be let me go ahead and do this。 Let me go ahead and run code index Hml。

 and let me go ahead and whip up a very simple web page herein。

 And I'll explain in just a moment what these lines are。

 but let me go ahead and just kind of transcribe it in this here file。

 So angle bracket exclamation point doc type Hl closed bracket。

 Then I had Hl Lng equals quote unquote。 Then I had head then I had title and inside of that title I had hello comma title below that head。

 I had open tag body inside of which I had hello body。 So there's a lot of weird stuff going on here。

 if you've never seen this before。 but I think I have recreated the file。

Saw in slide form a moment ago。 What I'm now going do is try to view this file inside of my browser。

 but to do that， I need to do this。 I'm going to go ahead and run HttP server enter and a whole bunch of stuff is going appear in my terminal window。

 some diagnostic output， a URL and the like。 But in particular。

 I'm going to get this little popup that's telling me， oh。

 my application running on port 8080 is now available。

 This is just a user friendly feature of Vs code specifically C50's zone extension therein that allows me to click open and browser I immediately get a second tab inside of which I see the content of my code space at this moment in time。

 Now notice to save myself some time today。 I've downloaded in advance a source 8 folder inside of which are a lot of today's examples if I so need them。

 And there's a file I literally just created called index Hml。

 What you're seeing here is a directory index of my current folder。

 So this is a dynamically automatically generated。

![](img/7b7b72accfa61f099248c5172dbf9456_19.png)

Page that's simply showing me in a web browser what is inside of my code space。 Now， what's my URL。

 Well， it turns out it's gonna be something that ends in Github do dev。

 which is a domain that Github itselfcontrol。 So that's gonna to be generated for me automatically。

 it's not a domain name I had to buy or sign up for。

 and it's really meant to be temporary because I'm gonna to use my code space as a development environment to develop web pages but most important for now is that indeed this server program is running on local host。

 which is a nickname for the local computer， no matter what its actual name is specifically on port 8080 And this is why I'm now seeing my folder。

 instead of Vs code， This tab has port 8080。 this tab would appear to have port 4，43。

 which is Github's own web server running at this domain Now I'm going go ahead and click my index do Ht And we will see what the simplest web page in the world might look likevoil there is my hello body。

 which is the only thing in this otherwise big white rectangular region otherwise known as the viewport of my。



![](img/7b7b72accfa61f099248c5172dbf9456_21.png)

![](img/7b7b72accfa61f099248c5172dbf9456_22.png)

BrowerAnd if I zoom in at the top here， you'll see that my title of my tab is indeed what we saw earlier。

 Hello comma title。 So long story short， even if you're completely new to developing web pages clearly we have the ability with this language called Hl to indicate what the title of a page should be in its tab and what the contents of its body should be as underwhelming and as black and white as all of this might be。

 Well， let me go back to my sample code here， and let's now actually introduce some building blocks herein。

 So what is actually going on。 the first line of code that I type that you see highlighted here is the pages socalled document type declaration。

 that's a silly mouthful。 but it's really just a standardized line of text that says hey browser here comes a web page written in H specifically version 5 of H。

 which is what most of the world is now using odds are this line of code will change over time。

 But for now this is what we have below that， things get a little more interesting and a little more symmetric if you will。

😊。

![](img/7b7b72accfa61f099248c5172dbf9456_24.png)

And no more exclamation points。 like you see in this first line。

 That's a bit of an anomaly down here， you'll see what I'll describe as open bracket， H。

 then the space， then Lng equals quote unquote E then closed bracket and by open and closed bracket。

 I mean less than sign and a greater than sign respectively。

 which you can type on your keyboard What this is doing is the following。

 This is the beginning of an HTML element as we might call it and the tag here for this element is called HTML。

 So anything immediately after a less than sign is the name of the tag And the way that browser's work is by relying on these tags to know what to do and where within the confines of the browser。

 So you can think of this first tag is saying， hey browser here comes some HTML。

 Now what is that HTMLl all about Well， this thing here highlighted Lng short for language indicates what human language is presumably going to be used throughout the rest of the page。

😊，All of the tags， all of the attributes for better for worse。

 are going to be in English because the language HTML itself was standardized by englishspe people。

 you can write web pages with your own content in any human language。 In this case。

 I have opted to write my page as simple as it is in English as well hellello title and hello body and the E attribute value here so to speak is just like a clue to the browser that in case you've got Google translate or any kind of automatic translation。

 this is a little hint as to what the human language is to facilitate automatic translation or search engine optimization Seo or the like but that whole thing started the HTML page now we have a sequence of other tags。

 Hey browser here comes the head of the page which metaphorically is like the very top of the page here aka the tab that we looked at a moment ago。

 Hey browser here comes the title of my page。 What's the title the title is hello comma title Now things are a little weird。

 The next line of text here is open bracket forwardlash title。Clse bracket。

 And whereas therefore I might call the previous tag， the open tag or the start tag。

 This one here now would be the close tag or the end tag。

 So there's a symmetry here that effectively conveying to the browser。 Hey browser。

 That's it for the title。 The title is now complete。 What comes next。 Hey browser。

 that's it for the head of the web page。 Nothing left in there。 What comes next， Hey browser。

 here comes the the body of the web page。 sort of everything else。

 the big contents of that white rectangular region is the socalled body of the page。 Hey browser。

 here's the contents of the body。 Hey browser， that's it for the body。

 Hey browser that's it for the Hml itself。 Now， notice the forward slash indicates the end tag or the closed tag。

 and you don't need to be super verbose。 even though my Hml tag started with a language attribute lang equals quote unquote E。

 You don't need to repeat the la。 You don't need to repeat the quotes or the E N。

 It's sort of obvious to the browser that。This is closing the previously opened HTML tag Now in general。

 the tags you're seeing should exist in one and only one place。

 you must use these tags in certain locations。 we will soon see bunches of other tags that you can use zero or more times to structure the actual contents of your own page So how do we get into that and what are we ultimately doing what we really have is in this HTML code a textual representation of a tree。

 one of our now familiar data structures whereby there's a root of this tree that has some number of children that might have some number of grandchildren and so forth and so depicted here at right is what you might call a document object model or dom do for short。

 which is actually what the browser is probably doing in its own memory or RA when it accesses a web page In other words。

 if you type in Google com and hit enter you immediately see the contents of Google's website in your browser what Google has probably done is sent。

😡。

![](img/7b7b72accfa61f099248c5172dbf9456_26.png)

Text that looks kind of like this， but more complicated than this simple example。

 that text is read top to bottom left to right by your browser and loaded somehow into memory using malloc or other techniques like that to create bunches of nodes in memory with a lot of pointers that somehow represent this tree structure in the computer's memory so that it actually knows what to display on the screen。

😡，So with that said， let me go back here to VS code and I'm gonna go do a sequence of examples now and I'm going go back to the code and then back to my browser to show you exactly what's going on。

 recall that at this moment in time， the only two things I have are a source 8 folder which I came with by default today in advance in case I need to copy paste anything an index H which I just created for the first time So let me go back to my VS code tab here and you'll notice that in my terminal window there's actually a bunch of logging information diagnostic information long story short。

 any time anyone visits a web server with a browser odds are the server is logging that visit In fact this is how companies know This is how Internet service providers know this is how parental controls know what websites you are visiting because all of this information is going back and forth between browser and server here because I am running the server via that HP server command I now get access to all of this juicy information including what's the browser is that the user is using what day and time they visited my page and so forth。



![](img/7b7b72accfa61f099248c5172dbf9456_28.png)

But for the sake of discussion， I'm not going really care about this diagnostic information。

 I'm gonna to hide this for the most part， but notice two under ports now。

 whereas previously I only had one TCP port in use 1，3，37， which is C50 specific。

 Now notice that VS code is detected that I'm running something else on port 8080。

 So you see a second port there and you might over time。

 if you open more and more tabs even additional ports as well that all happen for you automatically So for now。

 I'm gonna go ahead and hide my terminal window because I don't really care what's going on there。

 but that's still gonna keep HtP server for me running in the background。

 Let's go ahead and introduce some new tags。 So for instance， let me go ahead and create a new file。

 Actually， let me retract that。 let me open my terminal window。 And instead of showing the log。

 let me create a second terminal window with the plus icon。

 So I'm still running the other one with the command。

 but I still have the ability to run commands now in my here prompt。 For instance。

 I want to run a command code paragraphs Hml。 Let's go ahead and create a more interesting web page with actual。

Paragraphs of English or other type of text to save myself some keystrokes。

 I'm gonna be in the habit today of copying the hello world example as a starting point。

 perhaps and then just changing it as needed。 For instance。

 I'm going change the title of this here page to paragraphs。 And then in here。

 I'm gonna type out some paragraphs of text。 Now， what are those paragraphs。

 I wanted to save some time。 So in advance， I generated some Latin like text here。

 so I can copy paste three long paragraphs of Latin text， some lam Ipsum text here。

 Now it doesn't matter what this means it's sort of nonsensical words。

 but this is a web page that is going to have ultimately some paragraphs of text， not English。

 but fake Latin。 So let's go ahead and open this。 Let me go back to my other tab。

 I do need to reload this tab because I've created a new file that this browser didn't know about before。

 there it is paragraphs Hml。 Let me go ahead and click now paragraph Html。 and。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_30.png)

![](img/7b7b72accfa61f099248c5172dbf9456_31.png)

There are my three paragraphs。 Well， wait a minute。

 this is just like one big blob of a paragraph instead of the three paragraphs that I was promised。

 Well， why is that， Well， let me go back to my editor here。

 and you'll see that even though even if I hide my terminal here。

 even though I've got these blank lines， clearly， the browser is just ignoring me。

 And this is because HTMLml is pretty pedantic。 Like it is designed to only do what you tell it to do。

 And so if you don't tell it explicitly give me a new paragraph。

 it's just going combine adjacent text as we've seen already。

 So how do I do this it's actually pretty simple。 let me go into my body tag。

 and let me actually open a paragraph tag or P for short。 Now。

 notice VS code is trying to be helpful by automatically completing the rest of this thought by giving me both a start tag and an end tag in this case。

 that's not really helpful because I already have the text that I want to put inside of this paragraph。

 So I'm gonna go ahead and delete the closed tag manually。 And I'm gonna to move over here and。

this myself。 And just to be stylistically nice， I'm gonna go ahead and indent that。 Now down here。

 I'm gonna do one more paragraph tag P for short。 I'm gonna cut that out and I'm gonna paste this in here。

 And again， I'm fighting with the auto the auto formatting。

 because it is trying to understand what I intend， even though I'm going back and fixing this now。

 let me fix that， let me go down here， let me go ahead and fix this now， indent here and voil。

 Now we've got three paragraph elements。 And to be clear in Hl elements is generally everything between a start tag and an end tag。

 So I have three paragraph elements P for short。 Why is it only P。 Well。

 the designers of the H language years ago decided why write out paragraphs when open bracket P closed bracket suffices。

 So let's now go back to my other tab。 if I now nothing I see nothing changed。 But again。

 that's because I already receive the virtual envelope in my browser that contain the previous version of that page if I want to get a new。

Of paragraphs Htl。 I need to reload this tab。 and now I see the same text。

 but broken down into three separate paragraphs。 So this is just to demonstrate the point that if you want something to happen。

 you really need to tell the browser to do exactly that。 Well， let's introduce some other tags2。

 Let me go back to my editor here。 Let me go ahead and open my terminal window and let's create something called headings html。

 much like book much like an academic paper， you might have section headings like the chapter and the section and the subsection and so forth。

 We can actually implement this with some html2。 So let me kind of cut a corner here and copy and paste paragraphs html into headings Html。

 Let me hide my terminal window， let me change the title here just to be headings to be super explicit as to what's going on。

 and let me go ahead now and say H11 and down here let me say H22 and down here， let me say H3。

Now these are three new tags。 H1， H2 and H3 By definition， H1 is typically big and bold。

 H2 is typically not quite as big， but still bold。 H3 is not quite as big still but still bold。

 And these are the default stylizations of these here tags that come with Html。

 let me go back to my other tab。 let me click back。 So I now see my new file headings do Hml。

 let me click on headings Hml。 And now even though it's still nonsensical Latin like text。

 It least it's starting to look pretty， looks like a chapter of a book with some sections and subsections and so forth。

 that's because the browser now understands what it is I want of it。

 Now you could simulate this by just literally typing the word one in its own paragraph。

 the word2 in its own paragraph the word3 in its own paragraph。

 but it wouldn't be bigger and it wouldn't be bolder。

 And when it comes to the semantics of web pages， it's probably useful to use tags in this case like H1 H2 H3 because it kind of indicates the relative importance of the。



![](img/7b7b72accfa61f099248c5172dbf9456_33.png)

![](img/7b7b72accfa61f099248c5172dbf9456_34.png)

Like this is the beginning of the text。 This is maybe some finer detail。

 and then this is the finest detail。 It might actually help search engines or heck even AI nowadays understand that these are different sections in your text。

 and we'll soon see there's even other tags you can do to be even more helpful to the browser and search engines and AI。

 Well， how about something else。 Let's move away from big blobs of nonsensical text and let's do something with a chunk of nonsensical lists let me go into my terminal window。

 create a new file called list Html。 and let me copy paste my hello code from earlier。

 just to save some steps。 and let me go ahead and rename the title to list in this case。

 And let's just have a list of three things。 bar and Baaz。 if you've never heard these words before。

 there're sort of go to computer science words when you just want some random placeholders。

 they mean nothing per se but foo bar and Baz or go to default words like X Y and Z for mathematicians。

 All this looks like a nice pretty list。 I've indented it， which looks great。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_36.png)

Go back to my other tab， hit back and I click on list Hml。

 I think you probably know where this is going。 Just like the paragraphs。

 we just get one big paragraph of fo bar baths。 We don't get fo on one line bar on the next line Bas on the third。

 Well， why is that Well just as before the browser seems to be ignoring whitespace beyond single white spaces。

 In fact， I can try to be really explicit please give me some breaks between these lines。

 but if I go back to my other tab， click reload it just canonicalizes multiple spaces into a single space for better for worse。

 So if I really want a list。 I need to tell the browser that I want a list。

 And one way I can do that is as follows。 let me delete that temporarily and let me do U for unordered list。

 which means I'm gonna get a bulleted list with little circles next to each word。

 let me then use an tag for list item and type foo inside of the first。

 Let me type another li tag and bar for the next one and then。



![](img/7b7b72accfa61f099248c5172dbf9456_38.png)

![](img/7b7b72accfa61f099248c5172dbf9456_39.png)

![](img/7b7b72accfa61f099248c5172dbf9456_40.png)

With Bas。 And again， VS code is autocomplet， which is why I'm able to type the closed tag so quickly。

 But I've got now fobar and Bas inside of li tags， which in turn are inside of a U tag。 Now。

 let me go back to my other tab， click reload and now we have a bulleted list of items one at a time。

 Well， what if I want to number this list。 Well， I could certainly just go in here and start manually writing one and2 and3。

 but you could imagine that getting a little annoying over time。

 because if you need to reorder the list or add things to it。

 it's just minorly annoying to have to maintain numbers for list of things like this is what software is good at。

 this is an easy fix。 And you might guess where I'm going with this。

 if I want to move from an unordered list， which is just bullets by default to an ordered list。

 which is numbered， I can change the U to an OL in both places so that my start tag and n tag still match。

 I can go back to my other tab。 click reload and what's gonna happen by default now is I get one。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_42.png)

![](img/7b7b72accfa61f099248c5172dbf9456_43.png)

![](img/7b7b72accfa61f099248c5172dbf9456_44.png)

![](img/7b7b72accfa61f099248c5172dbf9456_45.png)

2 and three and long story short， there are actually techniques whereby you can change this behavior using attributes to not just be these Arabic numerals。

 but you can use Roman numerals or other symbols that browsers are designed to support。

 and it all just kind of happens for you， which is great because if you're writing something like an outline for a paper or the like。

 you don't really want to have to think about all of those numbers。

 just like Google Docs and Microsoft Word like the software should figure that out for you。

 And indeed， HTML can do just that。😊。

![](img/7b7b72accfa61f099248c5172dbf9456_47.png)

All right， How about one other here。 This time， let me go ahead and cut a corner and open a file I created in advance just to save a few keystrokes。

 Let me close most of those files for now。 And let me go ahead and copy from my source 8 directory a file I brought with me called table Hl。

 And let me open this up in its own tab and you'll see this file here that demonstrates a table And indeed。

 I know that because I have a top this file that I wrote in advance。 something called a comment。

 We've seen comments and see with slashlash。 we've seen comments in python with hash symbols in Htl a little weirdly you can write comments with open bracket exclamation point dash dash。

 Then you write your comment and you finish your thought with another dash dash close bracket but no additional exclamation point。

 Why these keystrokes。 Well， the humans who designed this probably figured who is ever going type that sequence of keystrokes like that's what we'll use for our comments tag as an aside。

 if you ever actually want to write those patterns of characters there's in a way to。😊，those things。

 as we've seen in other languages as well。 But let's focus on the juicy part here。

 What's inside the body of this here page。 Apparently something called a table and a table by that。

 we mean tabular data like in a spreadsheet or in a database table。 T R。

 I'll tell you a short for table row T R TD， a little less obvious， but it's short for table data。

 So it's kind of like the cell in that row。 And the fact that there are three table data elements inside of this one table row element means that there's gonna be three cells or really three columns from left to right inside of this row。

 below that is gonna to be another table row inside of which are three more cells，4，5。

6 as their content。 then 7，8，9， then curiously an asterisk， a0 and a pound symbol。

 So where are we going with this。 Well， if you're imagining your mind's eye。

 a telephone that has buttons and labels， It seems like I've just been laying out rows and columns of numbers you'd see on your cell phone or an old time。

😊，Landline phone。 Well， let's slow open this。 Let me go back to my other tab。 click back。

 now you see table Html。 and this isn't gonna be all that pretty， but it is tabular data。

 And if I zoom in with command plus here in my browser。

 you can see that this is laid out rather like a phone pad。 Now this is not a super compelling use。

 but you can imagine actual tabular data， maybe data that came from a database， maybe Google。

 in fact， when they implemented Google sheets or Microsoft。

 when they implemented Office 365 in the cloud for Excel。

 maybe that's how they're laying out all of your data in your browser as it is underneath the hood。

 they are using， of course， Htm， but specifically table tags like this。 Now as an aside。

 they're probably doing even fancier things than that nowadays but they certainly could use Tr tags TD tags and these table tags as well。

 All right enough about text， let me actually go back to VS code here， let's close table hml。

 and let's do something with an image。 In fact， let me go ahead and grab a file called maybe。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_49.png)

![](img/7b7b72accfa61f099248c5172dbf9456_50.png)

Bridge do PG， which is a portable network graphic version of the bridge with which you're now familiar that we ran the number of filters on in the past。

 and this is now in ping format because BM format which we used in a previous problem set tends not to be used on the web or supported necessarily by browsers but pings are Gifs R Jpegs R and potentially a few other formats as well。

 So I'm pretty good going with portable network graphic。 we're good to go。

 So let's create a web page that actually includes this image because at the moment。

 I'm just showing you the image。 I'm not actually embedding this image in a web page like Google or other websites would So let's do this。

 let's close that tab。 So's open a new file called I Hml just to save some keystrokes。

 let me copy paste my hello world example again changing the title to I and in the body of this page instead of any text let's actually put an image from Harvard University let me go ahead and use open bracket IM G for short。

😊，Equals quote unquote bridge do P G。 So in this case， we have a couple of new things going on here。

 We've got a new tag， of course， Ig， which is short for image。

 Why it was just faster to type for humans than image。

 So they called it three letters instead of five source is representative of another attribute。

 we saw an attribute earlier laing equals E。 Well， it turns out that the image tag if you read its documentation or listen to me now。

 has an attribute called source SRC for short that allows you to specified the source of an image that you want to display in the page。

 But somewhat differently here。 The image tag that I've written has no close tag。 No end tag。

 I could do this。 but frankly， open bracket image。 but frankly， this seems a little unnecessary。

 if not confusing， And it is technologically unnecessary。

 It turns out that some tags can be empty in the sense that they don't need a close tag。

 and an image kind of make sense。 unlike ahead of the page that。of a page。

 the body of a page that start over here and maybe end down here。

 an image is either there or it's not like you can't start showing the image and eventually stop showing the image like it's either there or it's not so you don't really need an end tag for certain start tags and image is among the examples。

 If now I go back to my table here and click back to see my directory index there is not only my ping but also my image html page and if I click on this it's not all that different from looking at the image itself。

 but apparently this is a pretty high resolution photograph that we took I haven't done anything to resize it And so what I'm seeing is a web page inside of which is this entire image so that's okay but I'm going to need eventually some techniques for shrinking this down and we'll come back to that in a little bit。

 Cs another language is going to be one of our solutions to that there problem but of course things can go wrong for instance suppose that I mistype this and I wrote bridge without the E and I go back。



![](img/7b7b72accfa61f099248c5172dbf9456_52.png)

This page in reload。 that's， of course， a typographical error。 And I see this broken icon。

 And you might have seen this on the real web。 sometimes images are broken because it's essentially a 404 happening underneath the hood。

 And in fact， the image just cannot be found。 So if I want to help the user with this for a number of reasons I can actually do this。

 let me add an alt attribute for alternative and say something like Harvard University In other words。

 in the event， this image can't be displayed。 go ahead and at least show the user some explanatory text better still if someone is if someone is blind or they are using a screen reader to help them here what is on a web page that they otherwise can't see the alt attributes value can be spoken allowed to someone with a screen reader so they know exactly what the image that everyone else can see so they can still appreciate what the content of this web page are。

 if I go back to my tab here in this case， it's still a typographical error but at least now people with and without screen readers can see what this image is supposed to be and even if I fix the type。



![](img/7b7b72accfa61f099248c5172dbf9456_54.png)

![](img/7b7b72accfa61f099248c5172dbf9456_55.png)

![](img/7b7b72accfa61f099248c5172dbf9456_56.png)

Graphal error and reload the page if someone can see the image， they now will。

 But if someone's using screen reader software， which for those unfamiliar a software that looks at a web page and tries to describe in English or some other human language。

 what is on the web page now we have helped that device be all the more accessible as well So you might have zero or one or now it seems two attributes on a given tag All what else can we do in terms of media well。

 there's something else we can do here。 And I'll just show you this one and let you play around with it online if you'd like。

 in my source a directory。 I've actually got a video file called video do Hl as well as video do m4 And if I open the former of those you'll see a page I wrote in advance that shows another technique about Hl the end of the day。

 we're still only have tags and attributes。 So like fundamentally。

 we've not really pushed ourselves too far here。 But notice that there's a video tag in Hml that does come with two attributes。

 at least one called controls。😊，Called muted the controls attribute just means please show the user like a play button and a pause button and maybe some other things。

 The muted attribute means literally that mute the audio by default。

 And that tends to be a good thing because nowadays。

 browsers are pretty defensive against advertisements and annoying advertisements like videos。

 autoplay on websites so you can ensure that your video will still autoplay。

 but without bothering the user so you can mute the volume， at least by default。

 But what's worth noting for our purposes is that some attributes apparently don't even need values。

 there's no equal sign， there's no quotes， but in some cases are necessary to specify the language of this pages in English。

 but some attributes indeed do not need values。 And if even if they do， you can use as in Python。

 single quotes or double quotes。 and sometimes no quotes at all。

 but I would get into the habits still stylistically of using double quotes for consistency as I have。

 But as for the rest of this， a source tag exists， which you can put inside。

Video tag itself has confusingly a source attribute， SRC for sure， as well as a type attribute。

 which indicates what type of video are you trying to play for the user。

 So I'll wave my hands at some of that media， but you're welcome to play that page and open it on your own and even unmute it to see what I've otherwise shown。

 But let's now make the web all the more interactive。 Let me close that example。

 Let me go ahead and open a new file called link do hml and start making the hyperlink with which we' all familiar。

 Clickable links in web pages， which is what makes the web the web itself。

 Let me cut some corners here and copy paste my hello worldld example into link do html。

 let me change the title to link。 so we know what's what。

 And let's actually make a page that has a genuine link to Harvards to maybe that image of Harvard called image Hm。

 I could say something like this。 Visit Harvard period。 Now this， of course， is just text。

 So this is not that interesting。 but just to make sure we're on the same page。 Let me click back。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_58.png)

Let me go to link Html and you'll see that I've called it link h， but there's no link there。

 I can click Harvard all I want， but nothing actually happens。 So let's make it a link。

 What do I want to link to Well I couldn't link to Harvard's website。

 but I already have a picture of Harvard let's try linking to a page relative to this one let me go ahead and open a new tag called the anchor tag a for short let me use its attribute called Href。

 which is a little arcane， but it stands for hyper referenceence the destination of this link let me add some quotes and say image Html close quote close tag and then notice VS code's trying to be helpful。

 but sometimes it doesn't know what I intend so I'm gonna delete the end tag move my cursor over and paste it at the end and finish my period there just because I want everything to be balanced and now even though this one looks a little more cryptic This is now the beginning of hyperlinking pages on websites If I go back to my other tag click reload now I see the familiar underlined。



![](img/7b7b72accfa61f099248c5172dbf9456_60.png)

![](img/7b7b72accfa61f099248c5172dbf9456_61.png)

which， of course， signals in many web pages that this here is a link。 If I hover over it。

 it's gonna be a little small， but in the bottom lefthand corner of my browser， which is Chrome。

 I can actually see that this will lead me to a page called imagetml。

 And indeed if I click on Harvard for real I get back to imagetl and the URL in my browser has changed from linktml to imagel。

 So this is what's known as a relative link whereby I'm linking from one of my own pages to another of my pages。

 They're in the same folder。 So I don't need to mention any folder names。

 The server just knows what I want。 So that's then a link。

 But what if I want to link to a actual URL and not just a relative page like Harvard's own website。

 that I can do too I can change the value of this h attribute。 and I could just do Harvarded。

 Unfortunately， this is not gonna work。 the values of H refs in a web page if they're gonna be fullfledged URLs have to be actual URL。



![](img/7b7b72accfa61f099248c5172dbf9456_63.png)

![](img/7b7b72accfa61f099248c5172dbf9456_64.png)

![](img/7b7b72accfa61f099248c5172dbf9456_65.png)

Protocol and all in this case。 And so I'm going to do https colon s www doharv u and heck。

 I'm gonna include the traillink slash， even though I don't strictly need it。

 and technically speaking I could omit the protocol if I want the same protocol to be used。

 but in general， I'm going link to the fullfledged URL of Harvard Udu here。

 I'm going to go over to my image tab I'm going to kick back to go back to my link tab。

 I'm going to reload to make sure I get the latest HTML in my browser and if I hover over this now。

 super subtle， but in the bottom corner of my browser now this indeed leads me to Harvard doed。

 And if I click that we should see the familiar forests that we saw a little bit ago。

 And now this is an external link， not a relative link that I've now implemented in this web page。



![](img/7b7b72accfa61f099248c5172dbf9456_67.png)

All right， let me click back and let me reveal one other feature now of those so-called developer tools。

 previously I opened up developer tools when I wanted to play around with HttP。

 the protocol that just gets the web pages from browser to server and back But now it turns out I'm going to use another feature of my developer tools by right clicking or control clicking anywhere on my page or going through the main menu。

 I'm gonna click inspect and now inspect makes a little more sense because now I'm literally inspecting the web page itself。

 notice at left here is a visualization of the underlying HTML of this web page and some of it's hidden but I'm gonna to click the little triangles to reveal the rest of it and you will see essentially at left here under the elements tab in Chrome a list of all of the elements that compose this web page and again an elements is everything between an open tag and a closed tag。

 So in this case I am seeing a very pretty printed version of my own source code and some things are broken out onto different lines just to make。



![](img/7b7b72accfa61f099248c5172dbf9456_69.png)

That here's some text， here's a link， Here's some other text。

 both of which are inside of this body tag and notice， too， as I hover over things。

 Chrome just to be helpful because if I'm a developer， I want some help here。

 I can see in light blue what I am hovering over in my Hl being mirrored in the actual body of the page if I hover over the body。

 I see everything to the body as well。 Now what I can take away from this is the following this here is my web page and it's very pretty printed if I close this tab。

 I can see my same code in another way。 if I right click or control click。

 I can also go to view page source。 View page source is a feature that's been in browsers for years and you can see the same code but exactly as it came from the server。

 I happen to be pretty nitpicky so it's all nicely indented as well but this is a static version of the page whereas the developer tools allows me to actually poke around with things。

 In fact， let me close this tab let me reclick again on inspect and watch。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_71.png)

![](img/7b7b72accfa61f099248c5172dbf9456_72.png)

![](img/7b7b72accfa61f099248c5172dbf9456_73.png)

If I want to poke around here， I could actually go into the developer tools and temporarily without even going back to my terminal window。

 I can click on or double click on anything in this page。 and I can actually change it in real time。

 Like it can change Harvard to Harvard University and then hit command enter。 And in this case。

 I can change the contents of the web page but curiously。

 that has not changed anything on the server， because this makes clear the point that once the browser has requested a web page from the server and downloaded that virtual envelope inside of which is the original version of Li Html。

 That's what the browser is going to keep in its memory。

 you can change your copy of that page all you want， but it doesn't affect the server at all。

 The browser gets a copy of what's on the server。 In fact， we can take this feature out for a spin。

 seemingly maliciously， but not in a way that has any effect。 In fact。

 let me pull up not just Harvard do you do， but specifically the admissions page for Harvard College and scroll down here and you'll see this advertisement toward the end。



![](img/7b7b72accfa61f099248c5172dbf9456_75.png)

![](img/7b7b72accfa61f099248c5172dbf9456_76.png)

![](img/7b7b72accfa61f099248c5172dbf9456_77.png)

Harvard will notice that if I want to see the underlying H of this page。

 I can see it in a couple of ways。 I can right click and choose view page source and it's gonna look like way more code than we've written to date。

 this is me scrolling through all of the Hl that composes the admissions websites Hl at Harvard There's a lot there but it's gonna follow that same pattern of tags and attributes or I can kind of pretty printed by going to inspect going to the elements tab and there notice is the exact same content。

 even though I was scrolling through it super fast but it shows you everything pretty printed So you can kind of poke around More importantly I can click on any part of the page with my control key or two fingers and select inspect and what's nice is that Chrome and really any browser will jump to the specific Hml in the browser's memory that corresponds to that part of the page the upside of this is I can actually infer how did Harvard make this web page How did they structure their HTML Now we haven't talked about all of these tags yet but notice that there's all of these div tags DV。

😊，A section tag， but there are some familiar ones。 Here's an H2。

 Harvard is using an H2 tag for Y Harvard Here's a UL down below for some kind of unordered list。

 but notice here I can be a little playful here and maybe we should nudge people to go to Yale instead let me change in the elements tab Harvard to Yale hit enter and now I seem to have hacked Harvard's website and it suddenly says why Yale instead but of course this changes nothing on the server because this two is a copy and the moment I reload Harvard's website I get a fresh copy of what's actually on the server so what's the value here well one pedagogically it's just a useful mechanism。

 these developer tools for understanding and learning how a website is structured if you want to do something similar yourself as a developer tool frankly sometimes it's a lot faster to just mock things up in the developer tools decide okay I like how this looks and then go over to your actual HTML and make the changes for real it's a faster way of iterating and it's also a helpful way of diagnose。

Certain problems that we might otherwise run into。All right， but there's still a danger here。

 speaking of Harvard and speaking of Yale， let me go ahead and close that tab there and return to the HTML of link do H。

 It turns out that the attacks with which you're familiar in the real world。

 namely phishing attacks are all too easily waged via H alone to be fish This typically means to receive some kind of spam email that's trying to trick you into clicking on a link that purports to be legitimate。

 but it's really taking you to some adversary， some bad guys website that's trying to steal your credit card information。

 your username， your password or something like that。

 and those emails in Gmail and outlook in other tools， they themselves are using HTML。

 anytime you get an email that's not just black and white text。

 but has colors and maybe images and formatting it's using HTML。

 So HTML is used not only for web pages， not only for mobile apps， but also for emails as well。

 and here's how easy it is to unfortunately deceive users suppose that I still have a link here to Harvard。

 but I actually change the actual。have to be Yaleedduu if I go back to my actual browser here and close my developer tools and click reload the page still says like the HTML visit Harvard period and this is super subtle but if I hover over this link in the bottom corner of my browser now I'm actually going to be led to Yaleedduu if I click this link In fact if I actually do thatvoil now I'm actually at Yaleedu So not a big deal in this case I'm just sending one student from one place to another but you could imagine making a website that looks like a bank's website that looks like Paypal's website that looks like something legitimate such that when I click on a link no one's really looking in the bottom left-hand corner of the browser all the time you could all too easily trick a user into visiting a page and maybe filling out form on a page that they didn't actually intend and we say this not to empower you to do such things but the opposite to detect when such behavior is happening and frankly getting into the habit of hovering over links that you're a little suspicious about。



![](img/7b7b72accfa61f099248c5172dbf9456_79.png)

probablyb a good practice， but for today know just how easily these threats can be waged and why there are so many of these threats to us online。

 it boils down to these basic fundamentals。

![](img/7b7b72accfa61f099248c5172dbf9456_81.png)

Now all that said， we haven't even done anything dynamically。

 Every web page we've made thus far has still been very static， like content I have made in advance。

 and you can reload， reload all you want。 it's always going to look the same from the server again and again。

 but how about we revisit how URLs work not just to serve up static content。

 but dynamic content as well。 it turns out that besides having folder names and file names at the end of URLs。

 you can also have a question mark in URLs。 and then key value pairs literally with equal sign in between them。

 We've seen key value pairs all over the place most recently in things like dictionaries for instance。

 but in this case here we have a canonical format for how you can actually provide input from a browser to a server typically that's typed in via a form So for instance。

 let me actually open up a brand new tab here and let me go to Google co just the main page that doesn't come with my browser and I'm going go ahead and type in something like cats。



![](img/7b7b72accfa61f099248c5172dbf9456_83.png)

Now ignoring the fact that there's a whole lot of autocomple going on here。

 let me hit enter and let me emphasize what my URL we can be distracted for a moment by the cute cats on the top of the page。

😡，But let's then zoom in on the top of the page here， where we'll see a very long URL。

 most of which frankly， I don't understand， and probably only Google employees want to understand what everything is in this URL。

 but let me delete most everything except the essence of this URL。

 and what I've left at the top of my browser is only htps colon s www do go do com slash search。

 which is the path。😡，Question mark， Q equals cats。It turns out way back in 1999。

 when Larry and Sergey founded Google and created their very first search page。

 they had a text box just like this one， but more simple in design。

 And if you filled out that text box with one or more words and hit enter you submitted a query to the server for which you want to search queue for sure and so all that form needs to do when you hit enter is change the URL。

 it would seem to take that user input in a standard format Q equals cats。

 something equals something something equals something In fact if there's multiple such parameters as these are called just like in functions。

 you can separate them with ampersands， but the question mark just means to the server， hey server。

 here come some key value pairs otherwise known as HttP parameters when I hit enter the search results are actually going be exactly the same most of the other stuff in the URL is probably for tracking purposes or goo trap what I'm searching for and what I'm clicking on but in essence if we distill the URL to just question mark。



![](img/7b7b72accfa61f099248c5172dbf9456_85.png)

Q equals cats after search， we have provided user input to this here page。

 and what's cool about that is the following。Normally the canonical URL might be as simple as this or it might actually have two key values and pairs which indeed can be separated by these here ampersands。

 I think I can take advantage of this here feature and implement like my own version of Google let me do this that's kind of it for HTML like there's bunches of other tags and attributes out there。

 But those are really for an online tutorial or book or reference or some other source to just pick up what more vocabulary there is at the end of the day it's just more tags and more attributes following this shared structure。

 So for now I want to make things more dynamic leveraging my knowledge of just that。

 let me go back into my VS code let me create my own page called search hl enter let me save a few keystrokes by copying and pasting my hello world code and changing the title to search Let me get rid of the body here。

 and let me begin to create my very own。😊。

![](img/7b7b72accfa61f099248c5172dbf9456_87.png)

Form using literally a form tag FM space。 And then here I'm going to close the tag immediately inside of this form element now。

 let me go ahead and create an input whose name equals Q and inside of this form element。

 Let me additionally at an input whose type equals submit and we'll see what this gets us first。

 let me go back to my other tab， click back to see my directory listing of files。

 click on search do html， and this is super simple。

 but I seem to have the beginnings of an interactive web form。

 a big text box and a submit button and by default that seems to be a form。 Unfortunately。

 if I type in anything to this cats and then click submit nothing actually happens。

 but if I go to my own URL here at the top， notice that I'm still on search hl。

 but question mark Q equals cat was automatically added for me by the browser as soon as I click submit。

 So let me go back and add a little more detail in my editable file。



![](img/7b7b72accfa61f099248c5172dbf9456_89.png)

![](img/7b7b72accfa61f099248c5172dbf9456_90.png)

![](img/7b7b72accfa61f099248c5172dbf9456_91.png)

![](img/7b7b72accfa61f099248c5172dbf9456_92.png)

Let me specifically specify that the type of this text box is text。

 but that it turns out is the default。 So I'm actually going enhance that and make this a search box specifically。

 Let me go back to my browser and reload and this is subtle。

 but if I now type in cats notice that I get this little here， which is just a user friendly feature。

 which means now I can click on the X to clear that box that is simply because I change the type of this box from generic text to a search box for which that feature is useful。

 I don't really like the idea of submit I'd kind of like my button to say something about Google。

 So let me go back to my submit tag here and change the value of that input to be quote unquote Google search。



![](img/7b7b72accfa61f099248c5172dbf9456_94.png)

![](img/7b7b72accfa61f099248c5172dbf9456_95.png)

![](img/7b7b72accfa61f099248c5172dbf9456_96.png)

Then let me go back to the page， reload， and now things are getting a little more interesting whereby I have a Google search button。

 it still doesn't do anything。😡，But let me be more specific。 When I submit this form。

 I want the method to be used。 the verb to be quote unquote get somewhat confusingly。

 the convention is to use lowercase here。 even though inside of the envelope。

 I've demonstrated with curl that it tends to be capitalized in the actual HP protocol。 but so be it。

 But get is actually the default。 So I don't strictly need that。

 but what I do want to add here is an action。 What action do I want this form to take when submitted。

 Well， I don't have a backend， I don't have a database。

 I have not searched the web ever with this here codespace， but Google has。

 So let me use Google's backend。 their servers and database to search for whatever Q is。

 let me change the action value here to be htps colon www Google do comlash search So just the beginning of that URL without the question mark Now let me go back to my search tab reload and now nothing visually seems to have happened。

 but if I type in cats now and click。😡。

![](img/7b7b72accfa61f099248c5172dbf9456_98.png)

![](img/7b7b72accfa61f099248c5172dbf9456_99.png)

On this new and improved Google search button， watch what happens not only to my URL。

 but the contents of the page。

![](img/7b7b72accfa61f099248c5172dbf9456_101.png)

I have just searched from my own web page for cats on Google com In other words。

 by nature of how HTMLml forms work specifically using the get method and the action of Google's own URL my browser knows how to assemble all of those ingredients into a brand new URL that contains as the value of Q whatever I typed into that box。

 And heck， I can do this manually now， even though no one searches like this。

 I could just search for Q equals dogs and now I get some adorable dogs as my search results here but that's just because I now understand what these URLs are doing for me and how they are structured if I zoom out and I go back to search Htl。

 I can actually make some improvements here to that same form。

 you might have noticed that when I typed cats the second time I actually saw it autocomplet as cats。

 there was a little pop over there。 if I don't want any autocomplete。

 There's an attribute for that autocomplete equals quote unquote off this will now disable the browser from remembering things that I've searched for before。



![](img/7b7b72accfa61f099248c5172dbf9456_103.png)

![](img/7b7b72accfa61f099248c5172dbf9456_104.png)

Also do this notice if I go back here。😡，To my search page and click reload。

 notice that with no hands on the keyboard， the box is there。 The button is there。

 but my cursor isn't。 I have to manually focus my cursor on that box and then it gets highlighted in blue and I see the blinking cursor。

 that's not the best user experience or UX So to speak why you're gonna make the user move their cursor and put the cursor where you want it to be anyway。

 So I can fix that。 let me go back to this same search box and let me add autofocus and I don't actually need to give it a value But if I now go back to the page and reload watch even without clicking on that text box。

 it's already highlighted and blinking because I've given focus so to speak to that their text box。

 Now what is this text box it's just a big white box。

 Well if you read the documentation for or listen to what I'm here saying about the input tag you can also have a placeholder attribute that can contain any text you want like query for instance。

 unquote if I now go back to this page reload once more now you see in。



![](img/7b7b72accfa61f099248c5172dbf9456_106.png)

![](img/7b7b72accfa61f099248c5172dbf9456_107.png)

![](img/7b7b72accfa61f099248c5172dbf9456_108.png)

![](img/7b7b72accfa61f099248c5172dbf9456_109.png)

ray text inside of the box， sort of explanatory instructions as to what I'm looking for。

 And as soon as I start typing CAAT TS query goes away。 So that。

 too is a feature you've probably seen in browsers that's just the result of someone having used the right Hl tags and attributes。

 Now I've been a little deliberate here， I have alphabetized all of my attributes。

 If only because it helps me personally skim things from left to right and know if I've missed something that I intended。

 but strictly speaking， there's no official ordering to any of these attributes。

 you can put them left to right， right to left， they don't need to be alphabetically sorted。

 but styllistically， this is indeed what I myself tend to do here。

 Let's take a look at one more use of forms that will allow us to introduce another feature that's present not only in Hm。

 but in other programming languages as well， including， in fact， Python。

 So let me go ahead and create a new file here called register Hl。

 And let's just imagine that we're trying to create a webp page via which someone can register for something a website。

 a sport or anything else。

![](img/7b7b72accfa61f099248c5172dbf9456_111.png)

And what I'm going to do in registered HTMLt is save a few keystrokes and copy my search code into register HTMLt and I'm going to change the title to register and I'm going to get rid of the form as a starting point here let me close my terminal and inside of this form let's just create the beginnings of a registration form but unlike the Google example I'm not going bother trying to submit this anywhere thatll be a goal for another time but let me go ahead and in this form。

 create an input for which autocomp is off like before for which the field is autofocused and you should only have one autofocus field otherwise the cursor doesn't know where to go let me specify that I want this input to be someone's email address because after all。

 I want this to be a registration page so the placeholder text I'm going to be using is email so they know what's to type and then the type of this field for now is just going to be text and then I'm going go ahead and have a submit button but it turns out you can have different types of buttons and one other way to express a submit button is literally with an HTML element called button for which the label here will be registered。

Long story short， there's different ways to implement buttons here is now a second way。

 Let me know go back to my other tabs。 Let's close the tats。

 Let's hit back to get to my directory index and let's now click on register do Html。

 So very similar in spirit to my search form。 but now I'm clearly asking for an email with the registration button。

 However， I could try to register with anything here。 In fact， if I'm not paying attention。

 maybe I'll just type my name like I always do in these examples and click register And even though nothing technically happened。

 notice my URL did change。 So the form was submitted because question mark email equals David is appearing there。

 but that was not an email address。 and it' would be nice if the browser says no， no， no no。

 that's not an email address， you cannot submit that form yet。 but if this is just a text box。

 it's gonna tolerate any kind of text。 but as you might know from Microsoft office and Google forms。

 you can certainly validate forms in those kinds of software， certainly we could do so in Hml。

 Well we can in a couple ways。 let me go back to my Hml and let me change the type of this。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_113.png)

![](img/7b7b72accfa61f099248c5172dbf9456_114.png)

Input to be not text， not search， but email。 And it turns out that this is one of the officially supported types of inputs nowadays where the browser will now know that。

 okay， before I can let the human submit this form， I better check that they're typed in an email。

 So let me reload this page。 Let me again foolishly try to type in just my name。

 not my email and click register and now notice I'm getting admonished by the browser。

 This is a default pop up that saying please include an in the email address， David is missing an。

 So obviously I've not typed an email address， So let me fix this。

 mail indu now the error has gone away。 I can click register and even though nothing useful happens again。

 the URL changed indicating that I did submit the form just to know where useful。 Allright。

 so that's all fine and good。 But it turns out that email is one of the relatively few types of fields that you can check for in addition to search and text more generally and a few others as well。

 But it turns out that browsers nowadays。😊。

![](img/7b7b72accfa61f099248c5172dbf9456_116.png)

![](img/7b7b72accfa61f099248c5172dbf9456_117.png)

Context of HTML support what are called regular expressions to help solve this problem。

 A regular expression is a pattern， otherwise known as a rex for short。

 that allows you to validate input from users and make sure that that input matches some pattern and this is a bit of a mouthful how you can do these。

 there's a whole bunch of documentation online not only at this URL。

 but in Python's own documentation and in other locations as well。

 but just wanted to give you a taste of the possibilities。

 because these are really everywhere in highlevel programming nowadays。

 as well as in this context of HTMLm。 Here is the symbology of regular expressions。

 We're not in a language， it's just a way of representing patterns， if you will。

 if you have a dot in a string of text， that's a regular expression that just means any character。

 It's like a wild card， any one character can be there。 a star is actually means zero or more time。

 So you can say give me a character， zero or more time。

 So there's either nothing there or there's one。😊，Or there's two or there's more you can use a plus which means give me one or more characters so not zero but one or more。

 you can use a question mark， which means zero or one character， but that's it。

 you can use curly braces unrelated to python and say I want this many occurrences of a character and you can have a range inside of curly braces give me minimally this many characters maximally this one and you can do other things too in square brackets。

 you can say give me any one of these digits0 through9 in this case but you could type anything in there that you want you can say09 to specify a whole range without having to type them all out you can type backlash d to indicate any digits so you don't have to type any of that out or you can do the opposite backlash capital D which means anything except a digit so long story short and I'm very much waving my hands at some of the details here there's this whole symbology that humans have come up with in different languages via which you can represent patterns So this is all。

Say that I could come up with my own pattern for an email address。

 even though it's not gonna be as good as the browsers own。 let me go back to VS code here。

 instead of saying email type equals email， let me go back to type equals text or heck I can go to the default and get rid of this all together but I'm going to use one other attribute we haven't yet seen。

 which is literally pattern equals quote unquote inside of this pattern value I can use a regular expression。

 a pattern that represents what kinds of values I want to accept。

 Now I'm going to keep this simple and therefore not very good。

 but remember that dot means any character plus means one or more of any character an at sign means literally an at sign another dot means any character another plus means one or more of any character then backlash dot Edu What's going on here Well we haven't seen this yet。

 but curiously if I want to literally have a period in。😡，The user's input。 well。

 I can't use dot because that means any character。 it was a wild card。 So just like in C。

 just like in Python， I have to escape certain characters。 So in regular expressions。

 if I do backlash do that means give me a literal dot in the user's input in actual period and then Edu means make sure that the user's email address in this case ends with do Edu。

 Now this is a bit of a simplification， because it is not the case in email addresses that you can allow for any one or more characters then an at sign and then any one or more characters and then dot edu。

 it's actually more formally defined than that。 So this is a very quick and dirty regular expression for an email address。

 However， if I now go back to my register page and reload and I again try to type in David and not invalid email address。

 that pattern will be checked and the browser will prevent the form from submitting at all。

 So I can express different patterns of things。 Now for email that's not the best thing because in fact。



![](img/7b7b72accfa61f099248c5172dbf9456_119.png)

I actually look at the official definition of an email address's regular expression according to browsers。

 it's actually this crazy long sequence of text using the symbols I showed you as well as some others but this just speaks to how complicated the definition of an email addresses pattern is so using type equals quote unquote email definitely the better bet but let me do something a little more reasonable if I go back to vS code here and let's suppose that we want to ask the user not for an email address but their phone number so let me change the placeholder to be phone for instance and then let me change the pattern to be that of a US phone number so here I could do this in a bunch of ways but I'm going use backslash D which means any digit and then curly braces three times than a hyphen then a backlash D curly braces3 than a hyphen then backlash D curly braces4 and this here represents a standard format for a USbased phone number three digits three digits4 digits so this is how。



![](img/7b7b72accfa61f099248c5172dbf9456_121.png)

![](img/7b7b72accfa61f099248c5172dbf9456_122.png)

![](img/7b7b72accfa61f099248c5172dbf9456_123.png)

![](img/7b7b72accfa61f099248c5172dbf9456_124.png)

I can now ensure that the human types in not an email address and definitely not their name。

 but a phone number that at least follows a certain pattern。

 maybe not very user friendly because do you really want to require the user to type in dashes。

 wouldnn't it be nice if they can skip those， maybe they want to use parentheses So there's better ways arguably still to do this The point here though is that web pages and other programming languages more broadly。

 do support these things called regular expressions which are wonderfully useful in the real world。😡。

But there is a danger here。 supposeose that even though this catches invalid phone numbers now register。

 it's telling me to match the requested format， unfortunately， as great as all these features are。

 these patterns are that I just introduced you as web developers now should never trust users input。

 Why the only thing stopping the user from typing in invalid data like their name and of their email or their name instead of a phone number or something else invalid is the code that they've downloaded to their browser but recall that even though when they view page source。

 they see exactly what came from your website， they can open their own browsers developer tools via inspect here。

 they can go to those elements and for instance， expand the form by clicking this triangle And if they don't like the pattern you're imposing on them。

 Well let me just go ahead in there， delete delete that hit enter okay watch what happens now I have modified the inmemory version of the web page I can。

😡，Register now all I want。 and I have just submitted D VId instead of a phone number。

 So this is to say， unfortunately that this week alone， we do not yet have enough skills。

 enough knowledge to correctly validate user input。 we can make the experience more user friendly。

 We can tell them right away in the browser you're doing something wrong。

 please don't submit this form yet， but we're also gonna to need before long a server side mechanism for defending against that kind of attack to So through phishing and in this case through modification of the actual dom and memory we've seen all to readily how adversaries can try to infiltrate art sites in some way。

 Now， in addition to the developer tools that come with your own browser it's worth noting that there is at least one official source via which you can validate your actual HTMLl。

 that is to say make sure that it is wellform and that it actually adheres to the HTMLl spec validator w3 org is a webbased tool that you can use to copy paste your hl even paste the URLs of Web。



![](img/7b7b72accfa61f099248c5172dbf9456_126.png)

Into and this is actually a tool that it will provide you with some feedback as to whether or not you've made syntactic errors with your actual code。

 All right， with that said， let's go ahead and take a five minute break and when we come back。

 we'll introduce stylization of these pages namely through CSS right we are back and it's time now to start stylizing these web pages so that they're not just these boring black and white pages that have structure to them but really no style and so for this what we're gonna to do is introduce another language called CSs or cascading style sheets。

 which is another language， but not a programming language via which you can specify how certain tags should be appearing on the screen。

 For instance we've already seen tags like H1 H2 H3 and I describe those as big and bold and not quite as big and bold and not quite as big and bold but what do we mean by bold and big it would be nice if we could actually use font sizes or pixel sizes it would be nice if we could introduce colors and other aesthetics and indeed CSS allows you to adorn the structure of your page。

With the last mile of detail， so to speak， the colors， the sizing， the spacing。

 the positioning and so much more Now， in order to do this。

 we're going to need to introduce one other term of art， namely properties。 And frankly。

 at this point， we're just coming up with different words for the same ideas in all of these various languages。

 but properties are sets of not surprisingly key value pairs。

 a property allows you to specify the color of something is this value or the margin for this something is this value or the height of something is this value。

 So properties is just the term of art used in the CSs world to describe key value pairs just like attributes is the word used in the world of HTML to describe their key value pairs。

 same ideas for as as far back as the dictionaries with which we introduce this here topic。 Now。

 where can you go about using properties and how can you go about using them。 Well。

 it turns out there's going be different ways of applying properties to elements inside of a web page。

 and you're gonna to have to specify as the developer。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_128.png)

Select those their elements and with the wave of a hand let me describe there as being type selectors。

 class selectors， ID selectors and attribute selectors。

 some of which we will see over time and all this means is that we're going to use slightly different syntax when we want to refer to different parts of a web page to do that though we're going need to tell the browser that we want to include some cS in our page So here again is that sample HTML that represents really the simplest canonical web page that we can create this one's just saying hello title and hello body and if we make room in the head now it turns out that there can be more than just a title inside of the head of a web page in particular you can have a tag called style which is wonderfully name because inside of that tag you can put some of those CSS properties key value pairs targeting specific elements inside of a web page alternatively we're gonna to see that instead of using a style tag you can actually use another tag up here namely a link tag which unfortunately。

I poorly named insofar as it doesn't refer to a hyperlink in the way that the anchor tag and the H ref attribute does that we described earlier。

 this one allows you to link in the contents of a dot csS file。

 which contains all of those same properties the key value pairs。

 But instead of typing them out in your actual web page。

 you can actually put them in a separate file and include them more readily。

 But turns out there's yet another way to stylize web pages。 And that's with style attributes。

 And we'll begin our story there if only because it's the simplest way to begin。

 But then as we often do， we'll try to improve， and improve， improve the design thereof。

 So let me go back to the S code here。 let me create a new file called home do Html and pretend like we're creating a home page for someone like John Harvard here on campus。

 Let me go ahead and save a few kstrokes as often by copying and pasting my hello worldcode into home do Hl。

 I'll change the title of the page。 I'll get rid of hello body and I'll hide my terminal windows we can now build a home page for。

😊，John Harvard， let me imagine this homep page as having like three big sections like a sort of header for the page with John's name。

 maybe a middle of the page that just welcomes people to his web page and then a footer with like copyright information or things like that。

 pretty common format for a web page， sort of something up here， something down here。

 something down here。 We just need a generic structure with which to play with some HTML and then some CSS。

 So let me do this。 Let me create a paragraph tag at the top of the page that just has John Harvard's name Let me create a second paragraph below that that says welcome to my home page exclamation point and then below that let me have a footer of sorts that's just copyright John Harvard in this way。

😊，Now， let's go about improving this in a few ways。 Well， one。

 this is a very quick and dirty copyright symbol。 It turns out as an aside that there's other ways to express characters in HTML。

 one of which is through what are called HTML entities because it turns out for some symbols that aren't easily type on your keyboard you can actually use some special syntax。

 and I'm going to use this ampersand symbol169 semicolon And here VScode is actually highlighting it colorizing it so I can see what's going on differently。

 This is an HTML entity using code number 169 which if you look it up in a book or a manual online you'll see that this means an actual copyright symbol So a little C with the circle around it so useful and commonly used here in the US not as easy to type on the keyboard。

 you could alternatively go Google it highlight copy it elsewhere and paste it in using UniIcode but HTML with entities are commonly used still to represent certain symbols like these Now let's at what this web page。

😊。

![](img/7b7b72accfa61f099248c5172dbf9456_130.png)

let me go back to VS code in my directory index。 Let me click on home do Hml。

 And here we have John Harvard's webp page。 But notice that there are indeed three paragraphs of text。

 although it's not really appropriate to call these paragraphs because they're really just different parts of the page or divisions of the page。

 So we'll come back to that。 But all of the font sizes are the same。

 Like there's no making John Harvard big and bold here。

 I don't really need to see the copyright as big as it is。

 So you might want to start stylizing content like this。

 but we have with H alone structured this web page。 So how can I add some style。 Well， first。

 I'm going introduce a style attribute before then taking it away。

 I'm going go to my paragraphs start tag here。 I'm going add a style attribute。

 and I'm going to change， for instance， the font size here。 So font dash size。

 colon large semicolon close Then on this tag here。

 I'm going to add another style attribute equals quote unquote font dash size。

 medium semicolon close。😊。

![](img/7b7b72accfa61f099248c5172dbf9456_132.png)

And then lastly， just to keep this going， style equals quote unquote font size colon。

 small semicolon close quote Now strictly speaking。

 I don't need the semicolonons in this particular case。

 I'm doing it just for uniformity as we'll soon see but they're kind of back just as they were kind of back when we introduce SQL in the end of those statements but here now I seem to have added some attributes。

 the style attribute to each of these tags that stylizing the aesthetics of this here page。

 So the structure is the same but now the aesthetics are different。 In fact。

 let me go back to my other tab let me reload the page and I should see now these new styles。

 and indeed it's a little subtle。 but the top line is bigger。

 the middle line is medium and the bottom line is indeed smaller。 Well。

 it'd be nice to kind of center everything。 So what else can we do with this page。

 Well let me go back to Vscode here。 and let me after the semicolon do something like this text dash align colon center semicolon and just to save some time。

 let me go ahead and highlight everything I just added。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_134.png)

![](img/7b7b72accfa61f099248c5172dbf9456_135.png)

And paste paste it inside of those same quotes。 So now notice， I have more properties。 And indeed。

 that's what we're looking at here。 This key font size has a value of large。

 The whole thing therefore is a property。 And I've used it in three different ways with three different values。

 large， medium and small。 This is another property over here。 Text a line whose value is center。

 And I'm using that again and again and again， separating them both again by semicolons。

 let me go back to my page here。 and you might imagine as soon as I click reload。

 Now everything is nicely centered。 So I've taking some baby steps toward improving the aesthetics of this page。

 but I dare say I haven't really done this in the best way。 Lets let's chip away at this further。

 So paragraph tags are fine。 but semantically， they're really meant to describe paragraph。

 And I'm hard pressed to say that John Harvard is a paragraph。 And copyright is a paragraph。

 but these are different regions of or areas of my page。 So I think what I'd like to do here。

 is just be semantically a little more appropriate。 So I'm。



![](img/7b7b72accfa61f099248c5172dbf9456_137.png)

![](img/7b7b72accfa61f099248c5172dbf9456_138.png)

Change my P tag to be a little more generically div tags， which stands for division。

 which is kind of a generic rectangular region of the page， which in some sense。

 is adding less information。 But we're going to improve upon this further。

 This is a very common way to structure pages。 In fact， when we glimpsed Harvard's Hl earlier。

 there were lots of divs divs divs divs in the page because someone who designed that page was kind of laying things out in rectangular regions。

 And even though there's no visible rectangles。 That's kind of what's going on here。

 It's one rectangular region on top of another， Three of them in total。

 But I don't think this is the best design still。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_140.png)

Why well let me go back to V S code here and even if you're brand new to CSS， let alone HTML as well。

 you might have noticed that I kind of copied and pasted and that generally has not been a good practice it suggests that I'm just doing something redundantly。

 but what if I did this What if I factored out that redundancy， that commonality。

 the text align center as follows let me go ahead and delete it here。

 let me delete it here and let me delete it here and let me propose that all three of these divs actually have a common parent from which they descend so to speak。

 namely the body tag So technically I could go up here and do a style attribute on the body tag equals quote unquote and then put text align colon center semicolon and the idea of again。

 the document object model with CSS is that that text alignment centering it will cascade down to the child elements which are div div div three of them in this case so that all of them are still centered me。



![](img/7b7b72accfa61f099248c5172dbf9456_142.png)

![](img/7b7b72accfa61f099248c5172dbf9456_143.png)

![](img/7b7b72accfa61f099248c5172dbf9456_144.png)

![](img/7b7b72accfa61f099248c5172dbf9456_145.png)

![](img/7b7b72accfa61f099248c5172dbf9456_146.png)

Go back to my other tab here and reload。 And even though nothing has changed visually underneath the hood。

 I have factored out that commonality and applied text align center to all three of those same elements。

 Now， technically， there's other ways to do this。 if I didn't want to stylize the whole body。

 especially if this is a bigger page that has other elements inside of it。

 I could actually introduce a parent of my own。 It is perfectly reasonable to create a parent div。

 which after all， is just sort of a generic container there。

 let me close it all the way at the bottom here and indent it accordingly。

 and then let me go ahead and indent all of these three divs inside of that new div to make the point that if I don't want to apply a style to an entire body of the page that's fine。

 I can similarly just do text align center right here and that too would achieve the same result。

 And indeed in Harvard's page， we might have noticed there were lots of divs， not only side by side。

 but nested inside of each other， perhaps it would seem for similar reasons as well。

 Now strictly speaking， I don't have to do it this way。

 let me go back to the body approach just to keep it simple。



![](img/7b7b72accfa61f099248c5172dbf9456_148.png)

But let me propose that as useful as these divs are as these containers whereby each of them describes a different region of the page I could probably help the internet I could help search engines I could help AI I could help screen readers for accessibility they understand a bit more about what I mean for each of these divisions of the page to be so instead of just generically saying div what I'm actually going to do instead is use three semantic tags and by semantic tags I just mean HTML tags that are not as generic as div or paragraph or P for short I'm going to specify that John Harvard is actually in the header of this page and I'm going to close that tag accordingly that welcome to my homep page is in the main part of the page and I'm going to close that accordingly and the footer is actually in a tag called footer itself and I'll close that one as well now these are not tags I'm just making up these are officially in the HTML specification but they mean exactly what they say the header for the page is probably useful it's kind of informational where。

whosese web page this is， But the main part of the page is generally the juicy part that has actual information that isn't just logos and and headings like that。

 The footer， though， typically tends to be less important。 It's got useful stuff。

 but it's probably not as important as the header and or the main part of the page So these tags capture those semantics and the upside is when Google or Bing show you sample search results or when chat or some future technology is learning about what this page is saying it could logically give a little more weight to the header and the main part and less weight to the footer so you don't see excerpts from the footer which might not generally be nearly as useful But what else can we do now that we've introduced these tags let's actually take a step toward improving the design of this page to generally speaking。

 it's not the best practice to combine the structure of your page with the aesthetics thereof In other words it's not the best idea to combine H with CS all in the same place because when I glance at this。

It would be nice if my Hl really did just structure the page and then somewhere else。

 maybe in a different file altogether， all of the aesthetics are why， because this way。

 maybe I could use different CSss properties for night mode for dark mode and for light mode so that depending on the time of day。

 the colors of the website might be a little bit different。

 I could maybe use different style sheets for different devices or different types of browsers or the like。

 So itd be nice to kind of factor out the stylization from the web page itself。 That said。

 this is sort of a swinging pendulum in industry。 there are technologies that actually do combine CS with Hl。

 the argument being that the closer they are， the easier it is to maintain the code and understand what is affecting what So you'll find arguments in both directions when it comes to the separation of HTML and Cs。

 but let's take a step towards separating at least for our desktop and laptopbased purposes here。

 Let me do this。 I'm gonna go ahead and delete all of these style attributes。

 which is unfortunately in。😊，the aesthetics of the site and make it very generic as before。 However。

 I'm going to reintroduce those properties in a different place。 As I proposed earlier。

 we can make room in the head for not just the title， but a proper style tag。

 So not an attribute but a tag and inside of that style element。

 what I'm going to put is a few different properties。

 But the way I'm going to do this is by selecting parts of the web page that I want these properties to apply to。

 So when I said earlier， there's these different selectors in the world of Cs。

 This is a fancy way of saying there's different syntax you can use to apply automatically certain properties to certain tags or certain types of tags。

 So let me go back to Vs code here。 And what I'm going to do inside of my style element is this。

 I'm going to specify that any tag called body which happens to be one and only one should have all of its text aligned in the center。

 semicolon。 Unfortunately， curly braces are back when using CsS in this。😊，Not unlike C。 but again。

 we're not programming。 We're really just defining key value pairs。 Any tag called header。

 I want to have some slightly different properties。 font size， colon large。

 any tag that's called main。 I want to have font size， colon medium。

 and then any tag that's called footer， I want to have font size colon small。 Now。

 even though this is we taking way more lines of code。

 it is a step toward keeping my styles separate from the content of the page。 And eventually。

 if if you are on the same page as me here where this might be leading。

 we can probably copy and paste all of those styles into a separate file。

 then two people can work on the same website at once。 One person can do structure。

 One person can do style， we can do the whole light mode。

 dark mode thing by having different files for different times of day feels like a design opportunity and all we've done though。

 is select tags by way of their names here in this particular case。 If I again go。😊。

BackTo my other tab。

![](img/7b7b72accfa61f099248c5172dbf9456_150.png)

And reload the page。 it's actually not going to look any different， but underneath the hood。

 it's indeed been structured and styled slightly differently。

 And here's where we have an opportunity to actually reintroduce those developer tools for yet another reason。

 let me right click or control click on the page。 let me click inspect。

 and as before you can see all of your HTMLml at left under elements。

 But notice at right all this time， even though I didn't mention it before。

 you can also see styles for things as well。 So for instance， if I click on the body。

 watch what happens at right。 I will then see a summary from my browser of all of the CSss properties that are being applied to the body of the page。

 One of them is apparently text align line center。 And then there's two others。

 even though I didn't type these out， display colon block margin colon 8 pixels and that's the user agent style sheet long story short。

 there are certain default properties that browsers have be it Chrome or edge or safari or Firefox or the like and what I'm seeing in italics there for the body。

😊。

![](img/7b7b72accfa61f099248c5172dbf9456_152.png)

Some of the default stylizations and this is why therefore some browsers will render the exact same HTML slightly differently unless you try to standardize it somehow with your own CSS but what's nice about Chrome's developer tools and any of these browsers is here too instead of going back and forth and back and forth between VS code and my browser tab and reloading each time I want to see a change I can change things in real time not permanently but in the browser's memory so if I'm just curious and I want to see what this text would look like when aligned to the left I can type in left and notice it immediately jumps there if I delete that all together notice that Chrome actually shows me a dropdown menu All autocomplete of all of the possible valid values for the CSS property so it's a great learning technique too I don't have to constantly look things up or watch a video online I can let the browser tell me what are the possible values if I'm learning or I just forget what I can possibly type there I can go ahead and undo that go back to having things centered but I can actually play around。

A bit further here。 Suppose I want to change the font sizes。 Well。

 let me go down to header here and notice what we meant was font size large for header。 Well。

 honestly， reasonable people are going disagree what small medium and large means。

 certainly across Google and Microsoft and Apple and other companies。 So what is large actually mean。

 Well， I could be more specific。 if I really want this to mean something I can say something like 18 point which you might be familiar in the desktop publishing world。

 I can change this to maybe 24 point to make it even bigger。 or I can even deal in pixels。

 I can say something like 36 px for pixels。 and I can get really crazy like 360。

 And you see that now it doesn't even fit on the screen， but look how nice it looks。

 because it's being dynamically size。 So I can just kind of play around with these various styles in the Intor itself。

 So in short， within Google's developer tools。 And again， almost every browser has this nowadays。

 the network tab showed us the underlying HttP stuff。 The elements tab shows us the underlying Htl。

 And now the styles tab shows us。Underlying CSss。 And there's so much more。

 but so wonderfully useful when trying to modify or learn this here stuff。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_154.png)

Let me go back now to VS code。 And let me propose to introduce another way of selecting elements。

 previously， I mentioned there is this whole list。 and what we've just done is select things by way of their type。

 The type of the tag was body or header or main or footer。

 But there's these things called classes in CsS2。 It's not really the same thing as classes in Python or Java or other languages。

 if you're familiar。 But classes in Css are our own keywords that we can invent and associate our own properties with those keywords。

 So， for instance， if I wanted to reuse styles like textal aligned center and font size large and font size。

 medium and small。 I don't have to associate them with specific tags。

 I can create my own nicknames for these， if you will。

 Let me say that any time I want to center something。 No matter what tag it is。

 I'm going to use a class。😊，Called centered。 Anytime I want to make something large。

 I'm going to use a class called large。 Anytime medium。

 I'm going make a class called medium and anytime small， I'm gonna make a class called small。

 Now why the dots the humans who invented CS needed to come up with some way to distinguish the types of tags or the names of tags from classes。

 And so you simply use a dot to indicate， hey， browser here comes a class whose name I'm making up on my own。

 So anything with a dot represents the start of a class name。 How do I use these， Well。

 let me scroll down to the bottom of the page。 And now there's no association yet with any of those class names with this Hm。

 But what I can introduce now is a class attribute where I can specify， okay。

 I want John Harvard to be large。 And I want the main part of my page to be medium。

 And I want the footer of my page to be small。 And by the way， I want all of this。

To be centered so you can create these reusable words and you can invent the words subject to a few constraints on what characters you can use。

 but now you have a set of classes。 so to speak， that you can use on these tags and maybe bunches of others They're not that useful at the moment because this web page is so darn simplistic but you could certainly imagine in Harvard's web page and Yale's webp page and Google's web page where they have so many darn tags might be very useful to use these classes and reuse them so you don't have to copy and paste any of that text as we saw before。

 And in fact let's take this one step further。 It's a little silly that I keep scrolling up and down。

 let's just move all of this Cs to its own file。 so let me highlight that and cut it let me get rid of my style tags altogether。

 Let me create from my terminal window a file called Styles cS though I could call it anything I want Let me paste those lines in there。

 and VS code nicely left aligned everything for me。 that's it out of sight out of mind。

 let me close that file and then inside of the head of this page instead。

Style tag let me do in link Hf equals styles do css and the re tag for the relationship here is that of style sheet。

 It's generally the only one you'll use and this is the kind of thing you might have to look up or copy paste。

 but HR refers to the file that you want to link in essentially copy paste but automatically like an include and see or an import in Python and the relationship of that file to this one is that of what's called a style sheet。

 a sheet or page of properties。So。Let's now perhaps use these techniques to make things that are a little prettier now and a little more visually interesting。

 Let me go ahead and do this。 Let me close out this homepage here。

 let me go ahead and create a open up our old file called link Html。

 which previously looked like this when we left it at Yale。

 let's actually undo that phishing attack and change it back to Harvarddu for consistency with before。

 And let's try to bring this link to life in a slightly different， more colorful way。

 if I open this page recall， we did see the link。 if I close my developer tools go back to link do Hm。

 notice it was underlined by default， which was great because it made very visually clear that it is a link and not just text and it was purple。

 which is the default color in most browsers to indicate， yes it's a link。

 but it's one you've already visited So purple means youve visited it before and blue typically means it's a link but you have not visited it before。

 So that's a default。 but suppose I want to override that in and make things more crimson or red in nature。

😊。

![](img/7b7b72accfa61f099248c5172dbf9456_156.png)

![](img/7b7b72accfa61f099248c5172dbf9456_157.png)

Well， let me go back to VS code here。 and in VS code。

 let me go ahead and just for the sake of discussion。

 let me take one step backward just because it's easier and more efficient during class to reintroduce our style tag。

 But if you're convinced you could and probably should move this stuff to a separate file。

 that's indeed the best practice。 But I'm going to keep it simple in the same file。

 Let's go ahead and start to stylize this anchor tag as follows。

 my anchor tag abbreviated a is going to have the following property associated with it。

 a color of how about red semicolon， And now let me go back to the tag here。

 reload the page and indeed it's now red and underlined here。

 if you want to get rid of the underlying。 you can I could additionally inside of these curly braces。

 say text decoration， which is another property。 we haven't yet seen whose value is now going to be none。

 if I go back to my browser tab， reload the page it's still red， but not underlined。

 And that's fine and that's pretty common。😊。

![](img/7b7b72accfa61f099248c5172dbf9456_159.png)

![](img/7b7b72accfa61f099248c5172dbf9456_160.png)

![](img/7b7b72accfa61f099248c5172dbf9456_161.png)

Nowadays， but here too， for accessibility's sake， you should be mindful of the fact that depending on the quality of someone's vision。

 they might not be able to distinguish red from black or red from some other color。

 So in terms of accessibility， you should make sure that if you're removing telltale signs of links like underlines make sure there're sufficient contrast between the colors that you're indeed using。

 So in fact let me go ahead and leave that alone for now。

 but let me propose that I'd like to at least show when a user on a laptop or desktop hovers over the link let me at least underline it then this is less useful on mobile because on mobile you don't really hover as much as you do tap or not tap。

 but just so you seen how in CSs this is done， I can do this too I can have a selector that says a colon and hover which is a special keyword that the browser knows about which means when I'm hovering over with my cursor and anchor tag change the text decoration temporarily to actually being underlined。

 And if I go back to my browser tab reload notice。

![](img/7b7b72accfa61f099248c5172dbf9456_163.png)

![](img/7b7b72accfa61f099248c5172dbf9456_164.png)

![](img/7b7b72accfa61f099248c5172dbf9456_165.png)

![](img/7b7b72accfa61f099248c5172dbf9456_166.png)

That I get now some interactive behavior。 Anytime I hover。

 you can see the line appearing for better or for worse。

 This is how you can implement a bit more dynamism then with your hair content。

 And the fact that it's an anchor tag means that it's going to apply to any of the anchors。

 any of the links in this here page。 if I don't want that to be the case， let me propose this。

 let me propose that instead of doing this， I want to define some properties as follows。

 Let's go ahead and undo this。 And in this page， let's suppose that we have a visit to Harvard or a visit to ahf equals hdps column s www do Yale Eduu close bracket Yale。

 So the page is a little longer now， but the sentence now reads visit Harvard or Yale with two different links。

 How can I now stylize these a bit differently。 Well， let me go ahead and do this。

 inside of my style attribute。 let me specify that I want the Harvard link to be red。 How do I do。



![](img/7b7b72accfa61f099248c5172dbf9456_168.png)

I'm I'm actually not sure I can just yet， but what if I do this if I know I want to stylize this tag。

 let me actually give it a unique identifier。 There's different ways to do this。

 but perhaps the most deliberate would be give this Harvard give this anchor tag a unique identifier called Harvard or whatever you might want to call it and let's do the same over here let's add an ID to the second anchor tag that calls this tag Yale and I'm using lowercase by convention What this allows me to use is yet another type of CSS selector not type or name。

 not class but IDd， I can create a unique identifier that allows me to say target the Harvard element how do I express that Well instead of using a dot。

 I actually use a hash symbol here and I say hash Harvard and then inside of those curly braces。

 I can say color red and I can do hash Yale and then inside of those curly braces I can say color blue。

 and actually just to bring back memories for better or for worse of hexet Eimal notation。

And Photoshop， as we discussed when we discussed multimedia representation thereof。

 I can actually use hexadeadeciimmal codes。 So instead of saying red or blue or any other color。

 I could say hash symbol here， unrelated to the hash symbol next to the class name。

 Now we are combining color codes with CS。 I can do this FF 0，0，0，0 which is a lot of red， no green。

 no blue down here I can say hash symbol， no red， no green。

 lots of blue and those represent essentially the same colors down here。

 I still want to do I'm gonna not bother actually with the text decoration anymore。

 let me go back to my page here。 let me reload。 and now I have now it's getting a little prettier a red Harvard。

 a blue Yale with those two links targeted specifically Now there's yet other ways to a third way would be to target a element based on the value or presence of one of its attributes an。

😊。

![](img/7b7b72accfa61f099248c5172dbf9456_170.png)

![](img/7b7b72accfa61f099248c5172dbf9456_171.png)

Tbute selector， but I'll wave my hand at that since surely。

 you'll see eventually in documentation elsewhere。 if you go down this road with web design。

 how you might target those as well。 But we don't have to do even these selectors。

 Ids are meant to be unique。 So maybe it would be better to say anytime I have something related to Harvard。

 Let's use a class called Harvard。 Anytime I have something Yale related。

 Let's use a class called Yale。 So here then。

![](img/7b7b72accfa61f099248c5172dbf9456_173.png)

![](img/7b7b72accfa61f099248c5172dbf9456_174.png)

Instead of saying Id， I can say class equals Harvard and class equals Yale。

 And now even though it's not relevant for this simple example。

 I can use that class on different elements again and again。 An Id is meant to be unique。

 and it is a mistake on your part or my part。 if you use it in multiple places。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_176.png)

![](img/7b7b72accfa61f099248c5172dbf9456_177.png)

Alright， so much like with HML， which really only had tags and attributes as its basics， Similarlyly。

 is CS relatively simple in design with just these properties。

 And it2 has a much larger vocabulary of things and features that you can use throughout your web page。

 But we'll wave our hand at that so that you pick up that vocabulary over time by online references or the like。

 But for now， let's just focus on how you can really leverage Cs to take up a notch。

 the aesthetics of your page and make things much prettier than I myself have been doing thus far。

 Let me go back to Vs code。 and let me copy from the code I brought with me today。

 phone book example that gives us the simple form of a phone book with three people。

 Let me go ahead and open this file as it's already been made and in this file here。

 after I close my terminal window is this a phone book that is apparently made up of an H table inside of that table is a couple new tags that I'm introducing for formalitys sake here。

 One is called Thead for tablehead inside of which is。😊。

Heing of the table with a table row T R with two TH tags， table heading for short， long story short。

 even though the table I made earlier to mock up the visual of a phone keypad is perfectly correct structurally it turns out if you want to distinguish the header of your Hl table from the rest of your Hl table。

 you can do so by introducing T head up here and T body down here So implicitly what I was doing earlier was treating everything is the table body with no fancy header up top But what is different here is that by using T for the table heading here instead of Td it's a clue to the browser that this actually has some semantic meaning。

 this is the heading of the table and maybe it for instance should be boldfaced by default。

 but we've seen already we can start to override that As for the body of this table。

 it seems like it's a phone book with three people。 Ulia。

 David and John with our now familiar numbers each implemented in table row。

 If I go back over to my directory index and reload， I'll now see phone book Hl。

 And even though the data is there。

![](img/7b7b72accfa61f099248c5172dbf9456_179.png)

It's not particularly pretty， if you will。 In other words， within this file here。

 I've got all of the data I care about， but certainly no CS。

 And while I could go in and start using some selectors and adding some CSS。

 some key value pairs for properties to make this prett or maybe with some borders and the like I bet I can do better by standing on the shoulders of someone else who's made a third-party library who's thought about what would be the prettiest way to display an HTML table and this gives us an opportunity to discuss what are called frameworks in the world of web development in particular。

 a framework is really a library written by some thirdpart that just makes it easier to frame your own project to sort of structure your own project so that you don't have to implement a lot of basics。

 particularly the aesthetic that so many other people have had to deal with as well better to focus on the problem you actually care about the business you're building the product you're creating rather than worry too much about the aesthetics thereof and among the more popular frameworks in the world of HTML and CSS is something。



![](img/7b7b72accfa61f099248c5172dbf9456_181.png)

![](img/7b7b72accfa61f099248c5172dbf9456_182.png)

![](img/7b7b72accfa61f099248c5172dbf9456_183.png)

Caed Boottrap， which is a library that anyone can use and incorporate into their websites。

 really by just including one or more HTMLml tags and suddenly everything would seem to look prettier。

 And in fact， let me go ahead and do this Let me copy an example I brought with me as well This one。

 a second phone book example if we open this new and improved version of phone book hl notice a few things in the head of my page I've included a link tag this time。

 but it's not referring to a file of my own like styles css from before。

 but rather it's referring to an absolute URL that ultimately per the end of this URL points to a file somewhere in the cloud called bootstap min css where min is just saying that this is a minified file。

 which means a lot of the white space has been deleted from it just to shrink the file ultimate size。

 but it is in fact a cS file Meanwhile， lower down in this file if I close my terminal window here we'll see in the table tag that I've used a class attribute the value of which is table Why is this Well according to boots。

Straps own documentation， they just told me if I want to use their stylization， their style sheet。

 be sure to add a class of table to your own HTML table so that they don't presume to change the aesthetics of all of your tables just the one to which you've added this class。

 Meanwhile， the documentation also advised me to add Spe Es column and Soppybook column to two of these table headings up here。

 But otherwise the data itself is exactly the same。 So let me go back to my browser tab here。

 which previously looked like this with no CSs whatsoever。

 and honestly even if I'd added my own CSS you've probably been an underwhelm this to how pretty my own pages look probably would not have looked much better but simply by including bootstap CSS file and adding those attributes that I pointed out notice what happens when I now click reload on this newly stylized phone book。



![](img/7b7b72accfa61f099248c5172dbf9456_185.png)

Suddenly， it looks much better。 Still black and white。 So if you' were expecting even fancir。

 you're not gonna get it， but its still black and white。

 but notice the font is no longer the default。 It's no longer some serif font。

 but it's some sense serif font with less decoration。

 notice that name and number have been automatically boldface。

 Not that clearly there's more padding or spacing among all of these values。

 So arguably it's easier to read， notice that there's the gray lines separating each of the rows from each other。

 And long story short， it's just prettier。 it's nicer to look at。

 but you and I don't have to figure out how to adjust the white space， how to adjust the bold facing。

 how to adjust the font size and all of that， the library takes care of that for you。 Moreover。

 there's other features you can include here。 If I read the documentation。

 It turns out that I can also add table dash striped to the class attribute。

 So we haven't seen this yet， but it turns out that the class attributes value can be one word or two or three。

 so long as they're separated by spaces。 So if I read the documentation turns out I can。😊。

Ply two classes to this table。 The second one now being tabletried and watch what happens when I now reload the page。

 I now see that every other row is very beautifully striped， slightly more usable。

 slightly prettier to look at。 And maybe more helpful then to discern what data is on what row。

 And let me wave my hands at the rest of this。 But suffice it to say that by way of frameworks like Botrap。

 you can actually make your website faster and better and prettier without having to reinvent lots of weird yourself。

 That said， if you're particularly artistically inclined and want to fine tune things。

 you can create some or even all of the Css that you're using。 But for more on bootsottrap。

 all of its documentation is that this URL here。 And in fact， in many of C50' zone projects。

 do we ourselves use bootstrap。 And its classes， So we don't have to figure out all of the aesthetics thereof。

😊。

![](img/7b7b72accfa61f099248c5172dbf9456_187.png)

Now with all that said， just one language remains this one a proper programming language that for better for worse is going to bring back functions and arguments and loops and conditionals。

 but before we get there， let's take a five minute break and when we return for the final time。

 we'll dive into jaright， we are back and we now take a look at the third of our three languages today that of ja but specifically one that's a programming language and by programming language I did mean that we'll get functions and arguments and loops and conditionals and more back but let's take a quick tour through ja just as we did Python much more quickly because what's ultimately important to us today is that you have a sense of what ja can do。

 but we will really only scratch the surface of this here language not only can ja be used in some of the ways we'll see today but it's also increasingly being used on the server as well to generate entire websites and applications and more so we'll give you a sense really of some of the basic syntax and basic capabilities but ultimately。



![](img/7b7b72accfa61f099248c5172dbf9456_189.png)

Defer to your future endeavors， your own final project。

 perhaps to apply jascript and explore it all the more。 So just as we did earlier。

 let's consider the simplest of web pages here in Htl alongside its own dom or document object model which represents again how that Hl might be structured in the computer's memory once the page has been downloaded anded by the browser。

 Unfortunately， what you're looking at here is a very static web page one that simply says hello title and hello body but wouldn't it be nice if that dom could evolve over time。

 after all， in C and then in Python， we experiment with data structures via which we can add and remove data dynamically based on user input and more In fact。

 and most any web page you've used nowadays， has some form of dynamism involved such that it's rare for it to be a static website odds are something is changing case in point。

 if you open up your Gmail inbox or outlook inbox and just sit there staring at it。

 odds are for better or worse， more email will appear more email will appear and previously we described those kinds of。

Boxes as stacks， which they rather are underneath the hood。 But visually。

 how are those stacks of emails being implemented in H， Well。

 we've seen already that it's probably some form of tabular data。

 a bunch of Ts Ts Ts one for each email that you might receive。

 But if it's coming from the server once how can you possibly get more emails So long story short。

 thanks to server side technologies， Python among them and client side languages like jascript among them。

 Can you actually behind the scenes get more and more data from the server in order to update the web page and in turn the underlying dom。

 So how can we go about doing this。 let's see what some of the things are that jascript can do We have conditionals in ja whereby such as in scratch。

 when we had X less than y is a Boolean expression and jascript here that kind of code is now going to look like this。

 Unfortunately， the parentheses are back the curly braces are sometimes back。

 but this is perhaps the simplest way to think about the structure。

Of a jascript version of a conditional， it actually looks at a glance exactly like C。

 If we consider an if else in scratch here right now with jascript would be exactly the same。

 just as we saw， in fact， in C and similarly， if we have an if else if else if that too might look exactly like this。

 But unlike Python， which rather abbreviated else if in jascript and in C。

 it is else if with a space in between。 All right， what about variables in jascript。

 if you actually want to be able to store something in your own variable。 Well， in scratch。

 recall that we might have set a counter equal to an initial value of 0 like this in jascript。

 there's a few ways to do it， But the simplest way to describe this is by using a new keyword let。

 which is like a very polite way of asking the browser to give you a variable。

 let me have a variable called counter and initialize it to a value of0 semicollonons though。

 are now back。 Now that's a bit of an overstatement because jascript can actually tolerate the absence of semicollons。

 at least。😊。

![](img/7b7b72accfa61f099248c5172dbf9456_191.png)

![](img/7b7b72accfa61f099248c5172dbf9456_192.png)

Many cases， however， for consistency， we and I will continue to use them here。

 How about if you want to increment that counter by a value of one。 Well， in jascript。

 you can do this by setting counter equals to counter plus1， the equal sign being， of course。

 our assignment operator from right to left you could also do counter plus equals one just as in C and in Python And if you like this in C plus plus and minus minus are now back。

 So in jascript you can do that to increment or decrement a variable respectively What about loops while in scratch。

 we might have had something like this to repeat three times in jascript。

 it's similarly is going to be very similar to C。 But instead of saying something like int for integer C。

 we indeed say let in jascript to create a variable like I do this say three times while incrementing with plus plus I along the way What else might we now do Well。

 we might have a forever block here in scratch that does something of course， forever jascript。

 you can also say while true where true is back to being lower case here and that。😊。

sure that whatever is between those curly braces will happen again and again。 Meanwhile。

 if we revisit the canonical form of this HTML， where can we actually put jascript code。

 turns out there's a few different places。 and there's a few different reasons to use one place or another。

 but just so that you see in the range of possibilities。

 especially when you then see suggestions in online documentation for ja libraries。

 you can put a script tag in the head of your page just like we put a style tag or a link tag up there as well as the title。

 And inside of that can go some raw jascript code typed out by you。 Of course。

 I've proposed that it tends not to be ideal to commingle one language with another。

 And so there's other ways to do this too。 you can actually have a script tag this one with a source element that will allow you to specify another file name or even another URL from which you want the ja itself to come。

 What's a little weird though about the script tag here。

 even when used with a source attribute is that youll see that I've closed the tag。Nonetheless。

 with open bracket slash script close bracket tag at the end of this line to make clear that there's no javascript inside of this element。

 Indeed， it's only coming from that same source。 As an aside。

 you will also see and there are also reasons to sometimes put a script tag in the body of the page that is below most everything else in the page or a script tag with a file reference there in。

 even at the bottom of the page just because order of operations can indeed matter。

 but these are sort of subtletiess that we'll try to avoid for now。

 simply focusing on really what ja itself can do。 And in fact。

 what's perhaps most powerful about jascript and what nicely brings us rather full circle back to where we started the class in scratch Javascript in the context of browsers can be very much event driven。

 So just like in scratch， when we actually had actual event and even a block。

 if you discovered it called broadcast where you could have one sprite somehow signal to another。😊。

In jascript， and specifically in the context of browsers。

 there's just so many events or things that can happen。 For instance。

 you might change the value of a field in a form。 You might give something focused by clicking on a text box。

 you might drag something from one place to another。

 You might put your mouse down or mouse over something on a mobile device。

 you might put a finger down thereby touching down on the device。 So long story short。

 all of these keywords that you see here represent events that happen inside of a browser that jascript as a language can be used to listen for and respond to。

 And as such， you can use jascript to make very interactive and responsive web pages whether that's to go get more emails from the server or to grab more of a map。

 if you're clicking and dragging while using Google Maps or the like So let's begin to scratch the surface today only of what jascript can do。

 Let me go back to VS code here。 Let me create a new file here called hello do Html。And in that file。

 I'm gonna go ahead and save a few steps by first copying as a starting point。

 Some of my earlier code。 let me close my terminal window， change my title。

 as always to just hello and get rid of now that default body。

 And let's go ahead and whip up a very simple interactive page that just says hello to someone more interactively。

 Idely letting them type in their own name。 just as we've done in so many languages prior。

 Let me go ahead and create a form tag in here。 And inside of that form， let's give myself an input。

 And just to practice what I've been preaching， let's turn autocomple off as before。

 let's turn on autofocus。 So I don't have to click in it manually。

 let's give this input a unique identifier for reasons that well soon see like name。

 Although I could call this thing anything I want。 But I do want the person's name。

 Let me use the placeholder text of name。 So it's clear to the user what I'm prompting them for。

 And the type of this text box， even though this is the default shall indeed be text。

 What else do I want to do。 Well， let's give it simple and just have an input type。😊。

Equal submit so that I get a button， which you've seen in a couple of different ways。

 Let me go back to my other tab。 Reload the page。 and I see now hello dot Html inside of this file。

 I see a very simple form。 If I type in my name though and click submit。

 notice that my URL has changed。 if I zoom in up here。

 And there's indeed a question mark which suggests that something was submitted from the browser to the server。

 but there's nothing after that， there's no something equals something。 And why is that。 Well。

 even though I gave the text box an Id of name， I didn't give the text field a name itself。

 In other words， I did not say， if confusingly， name equals quote unquote name。

 just as I did name equals quote unquote Q or name equals quote unquote email。

 And that's fine because you we've certainly seen inputs before。

 that don't actually send anything to the server， they just result， for instance。

 in the case of a button in the form itself being submitted。

 So this is to say that if an input in a form does not have a name。

 it's simply not going to be submitted to the server。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_194.png)

![](img/7b7b72accfa61f099248c5172dbf9456_195.png)

![](img/7b7b72accfa61f099248c5172dbf9456_196.png)

But that's okay because my goal at hand today， at least for this example。

 is to say hello to the user， but not server side。 we don't yet have the means yet until we reintroduce some Python to generate content server side。

 I want to do everything client side。 And so just to be clear just as Hl is downloaded from the server to the browser。

 CS is downloaded from the server to the browser Javascript as we are currently using it will also be downloaded from the server to the browser and executed client side in your own Mac。

 your PC or your phone， which is to say that any of the data we get from the server has to come all at the get go until then it gets executed client side。

 So if I want to greet the user based on what they type in type in their name as I need my client side jascript code to go grab that name from the form and display it on the screen for me。

 So how can I do this。 Well it turns out that the form element can take another attribute that we've。

Not yet used。 That's actually reminiscent of those keywords on this list here。 Indeed。

 notice on this list is a submit event。 and indeed in HTMLm。

 I can use an unsubm attribute in my code to do most anything I want。 For instance。

 supposeose I want to call a function。 I'm going to call a function called greet。 However。

 I don't want this actual form to be submitted I actually want to return false here as well。

 after a semicol and just to make clear that what I want this form to do is no longer to submit to the server。

 but rather greet the user by calling some function called greet and then return false and return false per the documentation for how browsers and jascript works。

 just means that the form never goes to the server。 So how can I go about using this here code。

 Now this greet function doesn't actually come with jascript。

 but I can create it myself just as I could create functions in scratch in see and in Python。

 In fact， let me go up to the head of the page and keep things simple， create a script tag。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_198.png)

![](img/7b7b72accfa61f099248c5172dbf9456_199.png)

Above my title。 and then inside of that script tag， let's go about defining a function in jascript。

 It's a little different from C。 It's a little different from Python。

 but the end result is really the same。 In jascript， you literally write the keyword function。

 which means hey， browser。 Here comes a new function。 You then give that function a name。

 I'll call it greet。 you then specify in parentheses。

 whether or not that function takes any arguments And for now I'm going to say no none。

 And then inside of curly braces， I can implement the actual function。 Well。

 what do I want to actually greet the user with anything for now， let's keep it simple。

 Let's actually use jascripts built in function called alert and just say something like how about hello comma world。

 close semicolon。 So the alert function， unlike does come with the language here I'm going go back to my browser reload the page。

 type in D I。 and now I'm going to click submit and notice what happened。

 I now get a fairly ugly popup， which is built into the browser。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_201.png)

But toward the middle of it， it indeed says hello， comma world。 Now。

 that has nothing to do with the name I typed in， but we can fix that。 Let me click， O。



![](img/7b7b72accfa61f099248c5172dbf9456_203.png)

Go back to VS code and before I sayo hello world， let's do this。

 Let's create a variable called name and set it equal to the following function。

 though it's admittedly a mouthful document， dot， query selector， quote unquote， hash name。😡。

Dot value semicolon。 There's a lot to unpack here。 So what's going on。 Well， recall that from Python。

 you can change certain things together and recall from C and Python。

 you can use the dot operator to go inside of structures or objects。

 So that's a lot of what's going on here。 So it turns out there's a special global variable when using javascript in a browser called document。

 which refers to the document itself， the dom， if you will。 And if you go inside of the document。

 It comes with a method aka function called query selector capital S lowercase Q。

 And what query selector lets you use funny enough。

 is the exact same syntax that Cs uses to select elements。

 So you can select elements in the page by way of their name or type like body or header or main or footer。

 you can specify you can select elements by way of classes or by way of their Is or other techniques as well。

 Now， recall earlier that I did give this。😊，input and name an I of quote unquote name。

 And so if I want to refer to that I， recall from CS that the symbol is the hash symbol and then the name of that identifier。

 So what's happening here as I'm saying go into the document。 use the query selector method。

 Look for the element whose unique I is name and please grab its value。

 that is whatever the human typed into that input and store it from right to left in a variable called name Now all I have to do is include it in my alert to the user and just as in Python。

 there's different ways to do this。 What I'm gonna go ahead and do first， is there our old friend。

 the plus operator after a space inside quotes and a pen to or cancateate to hellello comma space。

 That person's name Now， notice too， but I've deliberately done here is the following in the world of C double quotes are what you use for strings and single quotes are what you use for characters in the world of Python double quotes or single quotes can be used for strings otherwise known as Sts in ja。

😊，Same thing is true。 Doub quotes are single quotes。 I will say conventionally。

 probably most jascript programmers use single quotes for better for worse for strings。

 So that's the habit I'm gonna adopt here。 if only to be consistent with that。

 let me now go back to my other browser page reload type in again。

 my name David and notice now when I click submit now I get if I zoom in hellello comma David So I've created a string there dynamically notice once I this by clicking okay。

 if I go back up to the URL bar。 notice that I have not actually submitted the form。

 No question mark， no key value pairs have appeared in the URL。

 all of this is indeed happening client side Now what more can I now do with this this arguably is not the best design because as before with CS I'm of commmingling one language with another。

 and I've kind of baked into my H， some very explicit jascript code。

 Can I get rid of this Well I can in fact do that in a couple of different ways。



![](img/7b7b72accfa61f099248c5172dbf9456_205.png)

![](img/7b7b72accfa61f099248c5172dbf9456_206.png)

Go ahead and do this。 Let me go ahead and get rid of the on submitmit stuff。

 leaving therefore just the form and the two inputs inside of it that I had previously。

 just to be to avoid a problem， let me go below this now and add a script tag after getting rid of this one up here。

 So I'm going to deliberately move everything to the bottom of the page for now just so that this works without creating a problem。

 And what am I now going to do。 Well， turns out in ja。

 you can actually use ja to query the dom for specific elements。 And then。😡。

Listen to events that might happen with those elements。 You don't need an onsubmit attribute。

 You can do all of this in code， So how might I do this， Well let me do this。

 Let me create a javascript variable called form set it equal to document dot query selector and then let me go ahead and select the one and only form in my page with quote unquote form。

 I don't need a hash symbol， I don't need a dot because I'm selecting that element by its type or its name which in this case is form。

 All right what can I now do with this variable。 I can now use form dot and a new method that we haven't yet seen。

 It turns out in a web page once you have a variable or some other value that represents an element on the page。

 You can call a method called add event listener and as the name implies that allows you after the page has been created to start listening for some special event on that element that event being drawn from a list like this one here。

 including the submit event。😡，How can I do this， Well， this function takes one argument。

 which is quote unquote the type of event that you want to listen for。

 and I could listen for any number of things， but the one that's relevant for a text box in this case or one that's relevant for a form with this text box is going to be quote unquote submit and then I can call a function that actually gets called whenever that form is submitted Now greet again does not yet exist because I deleted it earlier。

 but notice what's happening here， which is not something we've done much before except a little bit in Python。

 I am calling the form variables add event listener function。 a method。

 I'm telling it to please add an event listener on the submit event。

 And whenever that event is fired or triggered， please call this function greet。

 So I'm passing in the name of the function。 I am not using parentheses after the name of this function because I don't want to call greet Now I want to register greet as an event listener so to speak So it's called later by its name by the。

For me。 Now， how can I go about implementing greet， I can do something as before。 So above this code。

 So before I use it， let's say function， greet， open per in close per in。

 Then inside of this function， let's do something similar to before。 Let name equals document。

 dot query selector， quote unquote。Hash name to get at the element with that unique name with that unique I do value。

 And below that， let's go ahead and use our alert function saying again。

 hello comma space plus use the concatenation operator， that particular name。

 Now there's one other thing I do want to do here because by default when forms are submitted。

 they indeed get submitted to the server， but that's behavior that we wanted to preempt。

 the way we prevented that last time was by adding return false inside of the event handler。

 But there's actually a better way to do that。 It turns out that when adding an event listener using a function called group。

 you're actually going to be passed in an argument， whether you want it or not。

 that I can refer to as event or E for short， but I'll be more explicit with event And it turns out that that argument that gets automatically passed in for you whenever that event is triggered allows you to call event dot prevent default。

 which is a more programmatic， less hackish way than previously whereby I just returned false This is。

😊，Literally telling the browser when you get this event。

 let me do my own thing by alerting the user hello， so and so。 but prevent the default behavior。

 which we know now to be submitting the form itself。 So if I haven't made any mistakes here。

 and I go back to my browser， reload this page， type in D Id again and click submit there we have it again the browser has shown me hello comma David。

 but this is getting a little verbose honestly， and in fact。

 there's more jascript like ways to do things like this。 and let me propose to do this。

 Not that I am one using a variable called name here。 and then only using it in one place。

 that's totally fine and very reasonable。 but we know from C and Python that's not strictly necessary。

 So if you're more comfortable， you can get rid of that whole variable like such and then just concatenate to hello comma space。

 the return value of that same function。 Now this fits on the screen nicely。

 it's still pretty readable。 I would wager that this is reasonably well designed。 But if this line。😡。



![](img/7b7b72accfa61f099248c5172dbf9456_208.png)

![](img/7b7b72accfa61f099248c5172dbf9456_209.png)

got much longer。 We probably do want to go back to the version with an actual variable。

 But we still want to prevent the default。 But what about this line here。

 Notice that I'm calling a function called greet。 even though even though I'm only doing that once。

 So we can actually do something in jascript that's kind of neat that we can't quite do in the same way in see or in python at least not nearly as elegantly。

 It turns out that if I'm only using the function greet once。

 I don't really need to give this function a name。 In fact。

 let me just kind get rid of that there and get rid of this here。 and let me propose this。

 this will look ugly at first， but I'm gonna grab this whole function。

 and I'm gonna literally copy and paste it as the second argument to add event listener。

 I'm gonna go ahead and clean it up a little bit to be little conventional here。

 I'm gonna move my curly brace of this line， I'm gonna get rid of this space。

 But now this is actually pretty compact。 Let me get rid of some of the blank lines and notice what I'm now doing。

 I'm still using a variable called form to get the one。😊，Form in the page。

 I'm then telling that form to add an event listener for the submit event。

 But because I want to tell it what function to call what you can do in jascript。

 which you can actually do in Python 2 is you can pass in an anonymous function。

 otherwise known as a lambmbda function that still might take an argument but does not need a name。

 Why because if you're using it only one place why bother even giving it a name。

 So the only thing I've done is I've deleted the name greet and simply calling it function and then passing in the specifying the argument it should take But the next two lines are exactly the same。

 And the only thing you have to be careful about is notice I've got the close curly brace here。

 and then the closed parenthesis， the first of which closes this curly brace。

 the second of which closes this first parenthesis。 And if you really want to tighten things up。

 we don't really need the form variable， let me get rid of that line of code and change that variable to be this one liner。

 And so even though this is getting a little complicated visually for those unfamiliar with jascript。

 this is fairly。Conventional syntax for doing a whole lot of things at once in this particular language without unnecessarily using variables and the like。



![](img/7b7b72accfa61f099248c5172dbf9456_211.png)

Now let me demonstrate that still this here works。 If I reload the page and type in my name David and submit。

 we do get that popup， but let me do what I did previously。

 which was to put this whole script tag inside of my head tag at the top of the page So I'll make room for it up there same exact code but now the script tag is above the form tag Let me go back to my browser here。

 click reload type in D VId and click submit and dang it we're somehow back to the broken version where still my name because I added that name attribute earlier is getting submitted to the server。

 but I don't want this getting submitted to the server。 What is now going wrong。

 Well let's see if we can't diagnose this， let me go back， let me right click or control。

 click and inspect and show you one final tab today， which is that of the jascript console。

 It turns out that in the console tab of your developer tools you can see error messages from languages like jascript。

 and if you see anything read like this odds arm。😡。



![](img/7b7b72accfa61f099248c5172dbf9456_213.png)

![](img/7b7b72accfa61f099248c5172dbf9456_214.png)

![](img/7b7b72accfa61f099248c5172dbf9456_215.png)

You messed up。 or in this case， I messed up。 And let's see if we can infer what's wrong。

 Can read properties of null reading ad event listener。 Unfortunately， just like clang。

 just like Python， the error messages in the computer world are not always that clear。

 especially for first time programmers， but it at least seems to relate to line 7 character 43 of hello dot H TM L。

 So let's go back to this line here。 Line 7 here is in place。



![](img/7b7b72accfa61f099248c5172dbf9456_217.png)

Why might the form be null？ Wellll notice that this global variable here is referring to the whole document。

 Queery selector is selecting some element from that document。

 But if that element doesn't yet exist this function call here。

 which I've highlighted will return null。 So this is kind of like saying null event listener。

 which just like our time from C， kind of makes no sense， you can't dereference null。

 you can't do anything with null， So something is gone wrong。 Now， why is that well。

 much like Python， much like C， these languages are typically read top to bottom left to right。

 And unfortunately， if you define the form on line 16， but you try to access the form on line 7。

 it's just not going to work。 And so what you're seeing in jascript's console here is that it's null because it hasn't yet been read。

 Now previously I avoided that problem by moving the whole script tag to the bottom of the page。

 just sort of avoiding the problem but there is another way to do it and you'll see in lots of libraries。

😡。

![](img/7b7b72accfa61f099248c5172dbf9456_219.png)

![](img/7b7b72accfa61f099248c5172dbf9456_220.png)

It's a bit of a mouthful。 Let me go into hellello do HTML here and add one more event listener。

 which I'll type out myself， document dot add event listener。

 and I'm going to listen for a very special event that you have to capitalize just right Dom content loaded quote unquote and then I'm going to go ahead and call another anonymous function that simply does all of this stuff together at the very bottom of what I just added。

 I'm going to add another whoops。I'm gonna add the close curly brace and another close parenthesis to now close this curly brace up here that I just added。

 and this parenthesis here that I just added。 So this too is more of a mouthful。

 but what is dom content loaded， I mean， it kind of does what it says when the doms content。

 the entirety of it has been loaded， then can you go ahead and execute these lines of code。

 How do you know what lines of code to execute， Well here too。

 I've defined an anonymous function and jascript， which just allows me to contain inside of these curly braces。

 the lines of code that I want to execute。 Not now， but eventually， when the doms content has loaded。

 So this is to say that even in these simplistic examples we've seen already。

 jascript very heavily tends to use these anonymous functions。

 or really people who write jascript code tend to heavily use these anonymous functions。

 if only because it tightens things up and typically。

 once you have some experience with programming in this or other languages， you'll get more and more。

With this， even though at a glance for the first time。

 this admittedly looks way more complicated than the problem it's actually trying to solve。

 Now that said， just like with CsS， we can get rid of all of this stuff。

 Let me highlight and cut that out。 Let me delete all these new lines。 Let me go into my script tag。

 and let me pretend for the moment with a source attribute that I have a file called scripts do Js。

 And I could imagine now， going into a file called scripts do Js pasting all of the code I just cut out of this file。

 and then just like Cs， allowing one file to refer to the other。 So in other words。

 you can ultimately go ahead and implement that same paradigm of separating one language from another in jascript as well。

 All right， that was a lot。 but let's now focus not so much on writing as much code like this。

 but looking at some examples that I brought with me to demonstrate what more we can do with jascript。

 in my terminal window。 Let me go ahead and grab a fifth version of this file from my sourcea directory。

😊，That's going to look a little something like this。In hello do HMl now。

 which I wrote in advance this time， we have some very similar code such that I'm listening for the Dom content to be loaded。

 I am defining a variable in this case called input。

 because I wanted to find a textbooks on the page。 And I'm using another event listener。

 and we've seen it on this here list not just submit。 But for instance。

 key up when the human finger comes up from the keyboard just after having type something。

 let's see for the moment before we dive in further to how this event is being used what this page now looks like。

 If I close my developer tools and reload the page， notice that the submit button is gone。

 but I still have a text box。 and watch what happens when I start typing like the letter C or a or T。

 or if I delete delete delete W O R LD delete delete， delete delete。

 And then there's a default value here as well。 So notice now it's sort of automatically updating the dom of the page as I'm typing。

 In fact， let me do this， let me reopen my developer tools with In， let me go to the element。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_222.png)

![](img/7b7b72accfa61f099248c5172dbf9456_223.png)

Page by default and notice the P tag here at the moment in the browser's memory is the phrase。

 Hello comma， whoever you are。 Let me start to type my own name now。

 instead of cat or world or anything else。 D， and notice that not only am I seeing hello comma D on the screen。

 notice that the dom as represented by the elements tab has been dynamically updated as well。

 if I type in now in a notice what happens in both places too。 The dom gets updated again。 V ID。

 notice that and it's flashing to draw your eye to it。 I'm updating the dom in memory。 Meanwhile。

 if I close this and open up the page source recall that this is a static version in here。

 There is no mention of D V ID in the actual Hml， that's coming from me the user So if we go back now to VS code。

 let's look at how this works。 again， online 10， I created a variable called input that just uses query selector to find the input element。

 The text box。 then。

![](img/7b7b72accfa61f099248c5172dbf9456_225.png)

![](img/7b7b72accfa61f099248c5172dbf9456_226.png)

I registered an event listener on that text box for key up。

 So this thing responds as soon as the finger comes off the key。

 I want this function anonymously to be called whenever that key goes up。

 inside of this function to find a variable called name。

 and I use the query selector to get another element on the page called P。 Well。

 where did that come from， well， let me open the page source again。

 and notice at the bottom of the page， is not only the form， which is super simple。

 no submit button even but there's also an empty paragraph tag that I just put there as a default element to fill with my content。

 let me go back to V code here， and notice that once I've got that。

 I've got room for the person's name。 So what I'm gonna do is this if the input has a value。

 If the textbook box has something typed in， I'm going do this， I'm going go inside of that name。

 The socalled paragraph。 I'm gonna change its inner Hml Capitalization is important here。

 Lowercase In all caps。😊。

![](img/7b7b72accfa61f099248c5172dbf9456_228.png)

Tml and I'm gonna change it to be hello comma something more on that in a moment else。

 if there's no input value。 That is its blank。 So this Boolean expression is false。

 let's just change the innerhtml to be hello comma whoever you are that's the default value。

 the last thing to tease apart then is what is going on here。 this is horrible to look at。

 I will admit， and is the ugliest of the syntax we've seen。 But just like in Python。

 we have those format strings or F strings where you can put the F。

 and then quote marks and then curly braces inside to interpolate the value of some variable jascript has something similar。

 except it's much more ugly to look at specifically you use back ticks which vary in their location based on whether you have a US English keyboard or something else。

 but a back tick at the beginning and a back tick at the end and inside of those back ticks if you want to interpolate the value of some variable you do use curly braces。

 But you also use。A dollar sign。 So it's like Python syntax， but worse， but it's the exact same idea。

 There's nothing really complicated beyond that， other than remembering or Googling the syntax for that technique。

So at the end of the day， the result is that we get this sort of automatically updating page that updates one keystroke at a time based on what the user typed in this time based specifically on the key up event instead of submit Well let's do one other。

 let me go back to VS code here， open up my terminal after closing hello do hml let me copy from my source directory today。

 something called background do hl and now let's go back to my directory listing here reload and see background do hl and click it this is very simple but let's see if we can infer how this works。

 I've got three buttons and they're not rectangular as much as they are square but that's just because the labels R G and B are so short。

 but watch what happened R turns my background red green turns it green B turns it blue Well how is that happening Well let me go back to VS code here and let me actually open now this file background do hl and notice what's going on here inside of my body I've got three button。

😡。

![](img/7b7b72accfa61f099248c5172dbf9456_230.png)

![](img/7b7b72accfa61f099248c5172dbf9456_231.png)

![](img/7b7b72accfa61f099248c5172dbf9456_232.png)

![](img/7b7b72accfa61f099248c5172dbf9456_233.png)

Each of which has unique Id， red， green or blue， and each of which has super short labels， R。

 G and B in all caps。 But then I have a script tag。 notice first。

 I'm creating a variable called body that's just grabbing the element from the page。

 the type of which is body。 and there's only one of those。 and then notice this。

 I've got three nearly identical lines of code starting here I'm going into the document using query selector to find whatever element has a unique I of red per the hash symbol on that element。

 I'm adding an event listener for the click event， which is， again。

 on our list of events that you can list for in Javascript。 in addition to submit。

 and in addition to key up here then I'm listening for click and I'm calling this anonymous function when that R button is clicked And when it is。

 I execute one line of code， and here is where today kind of comes together in full circle。

 I can inside of my web page。😊，Using jascript， modify the CSS of my page too。

 I can go into that body element， access its style attribute。

 which is a variable inside of the body and that exists because that's how browsers work and I can access the background color property inside of that body tag style。

 It's like accessing its style attribute， if you will。 And I can set it equal to quote unquote red。

 or I could do hash Ff 0，0，0，0， but I kept it simple with quote unquote red。

 The next three lines of code or the same thing， but for green。

 the last three lines are the same thing but for blue。

 The only thing that's weird here is where did background color come from because it's lowercase B in capital C。

 Unfortunately， this is maybe not the best design historically in in CSS we saw text line。

 we saw color， we saw a couple of other properties as well。 Unfortunately。

 there isn't CS a CSsS property called。😊，Background dash color。

 I just didn't happen to use it just yet。 Unfortunately， CS uses background dash color。

 Javascript necessarily uses background color with capital C。 Y well， in jascript。

 you can do math like in most languages。 and unfortunately， the dash is already used as a minus sign。

 So unfortunately in jascript。 if you wrote this property as background dash color。

 this would be like trying to subtract color from background。 So background minus color。

 which makes no sense。 So lefthand in right hand weren't really communicating it seems So the solution was just to use camel case。

 so to speak like a camel with a hump and capitalize the C， but get rid of the hyphen。

 And there is a mapping therefore from CSs properties to jascript attributes in this way。

 So that's all that's happening And in fact， we can see this again in our inspector。

 Let me reload the page to go back to white。 let me again open up the developer tools。

 let me click on the body of the page， which currently has no attributes and at right。

 there's no styles being applied to it other than the default。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_235.png)

From the user agent style sheet。 But watch what happens now under element style and on the body tag itself。

 when I click R， a style attribute will suddenly appear programmatically on the body tag with a value corresponding to background dash color colon red notice over right here too we see a summary in Chrome's developer tools of exactly that if I click on G if I click on B I can see exactly the same thing happening for each of those colors。

 So here now we have the ability with jascript not only to alter the dom of the page。

 the contents of it what the user is seeing but also it would seem the CSs thereof What more can we do。

 let's look at one other example that sort of evokes a tag from yesterear。

 let me go into my source directory and grab an example called blink hm and show you in this code herein if I hide my terminal window we've got a function in this file inside of my script tag called blink。

 which apparently toggles visibility。

![](img/7b7b72accfa61f099248c5172dbf9456_237.png)

Of greeting。 But what does that mean， Well， let's try to infer here。 There's a variable called body。

 which is set equal to the return value of query selector。 And we're checking this question。

 If the visibility of that element is hidden， then change the visibility to visible。 else。

 change the visibility to hidden。 Now， this， too， is one of these left hand and right hand。

 we're not intercommunicating， I have no idea why the opposite of visible is not invisible。

 but the opposite of visible in CS is hidden for better or or worse。

 So what's really happening here is we have a conditional。

 And if else construct that's saying if the visible is hidden， make it visible， But if it's visible。

 make it hidden back or forth。 How is this being used， Well。

 here is another function that comes with javascript， there's a global variable called window。

 which refers to the browser window itself。 that comes with a method called set interval。 capital I。

 That function takes two arguments。 the first of which is the name of a function to call。

 Notice again。Not using parentheses because I don't want to call blink online 22。

 I want to pass the name of that blink function to the set interval function。

 and 500 is the second argument that refers to a number of milliseconds and what set interval does。

 as you might imagine， is it will now call the blank function。

 every 500 milliseconds or half a second。 So the effect。

 if I go back to my browser tab close my developer tools and click now on blink Hml is a resurrection of a tag that actually existed when I was growing up。

 whereby you could literally do open bracket blink close bracket and you could make your web pages text blink like this。

 even worse， there was a tag called marquee that would scroll your text across the screen very hideously So And in fact。

 among all of the features of Hl among the few that have been removed over the years are exactly those two tags。

 But what jascript we can bring them back now in this way。

 the point of which really is to demonstrate again how much control we now have over ja over our。



![](img/7b7b72accfa61f099248c5172dbf9456_239.png)

![](img/7b7b72accfa61f099248c5172dbf9456_240.png)

And our web pages， thanks to jascript。 Let's do one final example here。

 Let's go back to Vs code here， open my terminal and let me copy in one last file from today's distribution code called autocomplete do Hml。

 And let's go ahead and open up。

![](img/7b7b72accfa61f099248c5172dbf9456_242.png)

Auttocomplete Html here in VS code。 Well， what's going on here。 Well。

 it turns out that there are there's a body of this page which just has a text input that's of type text with a placeholder of query below that there's this empty unordered list with nothing initially much like there was an empty paragraph tag previously so I could put hello so and so。

 Then there's this file here using a script tag referencing large do js。

 So I actually need that file too， that's in today's distribution to。

 So let me grab large do js which if we open that up might look somewhat familiar it is a jascript version of the dictionary from problem set 5 where you implement the fastest spell checker that you could。

 So there's100000 plus words in this file， but notice there're structured as a jascript variable called words all caps to make clear that I mean for it to be global It's using square brackets as on line one because that it turns out much like Python is how jascript indicates。

In array。 But in jascript theyre again called arrays instead of lists。

 And then I just have this comma separated list of strings using double quotes。

 but I could have used single quotes for all hundred thousand0 plus of those words。

 So by including this file， this means that my script down here has access to that words variable。

 What am I doing， Well， I'd create a variable called input and set it equal to query selectorss return value。

 just so I can get a variable pointing to that text box。 Then I'm again。

 as before adding an event listener listening for key up So the finger coming up。

 and whenever that happens， I call this anonymous function。 I first in that function。

 set an HTML variable to quote unquote So the empty string， nothing。

 because what I want to do is build up a list of words that match。

 whatever the human has typed in and you'll perhaps see where this is going in a moment。

 If the user then has type something in， there's a value in that textbook。

 do this iterate over that array of words。 So for each word of words here too is a。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_244.png)

Javascript specific feature， but it's similar in spirit to Python sort of similar in spirit to see。

 but the preposition I'm using is indeed of and I'm saying for each of the words of this words array。

 it's a little weird the English， but this is how you can iterate over every element in a jascript array if the current word that we're iterating over starts with capital W so this is a function that comes with strings in jascript that input value。

 So in other words， if the word word' looking at in the dictionary starts with the same letters that the human has typed into the text box。

 let's do this。 let's concatenate onto the HTML variable。

 which is just an empty string initially the following HTML Now this too looks weird。

 but remember that the back ticks mean that you can interpolate variables inside of curly braces So this means add to that HTML variable another li tag and another close li tag inside of。

So is the word that has matched the first few characters and do that again and again and again and plus equals here just means cancateate。

 cancateate cancateate。 So we're essentially building up in jascript more and more and more and more HTML dynamically based on the humans keystrokes。

 and the very last thing I do is this I ask the document to query select the UL element。

 which previously was an empty unordered list but change its inner HTMLm to be equal to the li tags that I've been creating creating creating in one big variable So if I go back over to VS code here if I go back to my browser tab here and click back and I now go into autocomplete H as the name suggests this is the essence of how autocomplete exists in Google in Bing and in applications more generally on the web and in some mobile devices If I type in C I see now an unordered list of all of the words that start with。

C in this dictionary， If I type A， nothing seems to happen， but that's because the list is so long。

 if I type CA now notice I get every word that starts with CA， if I type in S。

 now I get just four words， including ketchup， but the end that starts with CAATTS。 Meanwhile。

 if I open up the web pages source， notice none of those words are in there they're in the large do Js file。

 but not in this page if I instead close that and open up the inspector again and I go to the elements tab。



![](img/7b7b72accfa61f099248c5172dbf9456_246.png)

And after having typed in cats notice， there are indeed four li elements there。

 But watch what happens As soon as I delete mention of cats here。

 all four of those lis disappear And now I'm back to the U alone。 So this is to say with Html。

 we can structure our web pages with Cs， we can stylize our web pages。 And with jascript。

 we can dynamically update and modify our web pages and via jascript。

 Can we therefore implement applications like Gmail and Google itself and Cs 50 Ai and so much more because it makes what's otherwise a very static experience in the browser suddenly dynamic。

 And indeed， what jascript can even do is make more HttP calls to the server to get more and more data more and more tiles from a map more and more emails from the server。

 But today， we've seen just the fundamentals through your coming problem sets and perhaps final project。

 where you have an opportunity to apply all three of these technologies together。😊。



![](img/7b7b72accfa61f099248c5172dbf9456_248.png)

Build the web applications and the mobile applications that you and I already use every day。😡。

That's it for CS50， we will see you next time。

![](img/7b7b72accfa61f099248c5172dbf9456_250.png)

![](img/7b7b72accfa61f099248c5172dbf9456_251.png)