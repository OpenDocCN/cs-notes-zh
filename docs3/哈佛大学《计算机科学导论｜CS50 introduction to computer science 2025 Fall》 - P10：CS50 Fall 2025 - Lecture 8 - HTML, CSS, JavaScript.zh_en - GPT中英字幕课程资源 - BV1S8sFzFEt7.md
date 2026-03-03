# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P10：CS50 Fall 2025 - Lecture 8 - HTML, CSS, JavaScript.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

All right， this is CS 50 and this is already week8 and up until now of course。

 in so many of our problem sets like we've been writing command line code like a black and white terminal window and everything is very keyboardbased very textual but of course like the apps that you and I are using every day or in the form of a web browser on our phone and so today and really for the rest of the semester we now transition to using all of the building blocks that we've been accumulating over the past few weeks。

 but to redeploy them in the context of web apps and for your final project for instance if you so choose even mobile apps as well so today we're going to understand how the internet that we use every day actually works。

 We're going introduce you to a language called HTML。

 which is the language in which web pages are written， a language called CSS。

 which is the language with which web pages are stylized and then lastly ja which of those is the only actual programming language。

 but even though we'll spend quite little time on it。

 you'll see syntactically and functionally it's very similar to see to Python and languages indeed that have come before。

😊，If we could lower the amplification a little bit， that'd be great。 All right。

 so we use the internet every day So what exactly is it Well in the simplest form like we've got networks in the world and networks are interconnections of computers。

 whether with wires or wirelessly you have a network at home nowadays for the most part you certainly have a network on a campus like this in corporations you have network so interconnections of computers as soon as you start networking the networks if not networking the networks of networks。

 you have in effect the Internet， So this global interconnection of computers servers。

 devices and so many other things literally nowadays that we take for granted every day but how does it actually work and where did it come from if we rewind until like 1969 the Internet in its original form。

 really something known as ARPpanet for the advanced research projects agency project from the Department of Defense that was really designed to interconnect what limited supercomps we had back then that would otherwise geographically inaccessible to so many researchers and others the Internet or ARPAnet really。

😊，looked like this with UCLA and just a few other nodes so to speak interconnected somehow just a year or so later。

 did we have Harvard and MIT and others on the East Coast and if we fast forward now to today of course we can find and route data most anywhere in the world and in fact the world is now filled with these things call routers。

 a route， just a computer a server that routes data up down left right geographically and of course in the real world it might go out this wire here out this wire here out this wire or out this wire and in fact just to make more real what we're about to be talking about when we talk about networks of computers and eventually the internet we engage some of our teaching fellows over the past few years to perform a little skit of sorts for us using zoom if you will whereby each of the teaching fellows or humans you're about to see consider them as representing a router a device on the internet whose purpose in life is to route data and what theyre routing is what we're going to start calling packets packets of information which metaphorically you can think of as just like a little white envelope like this that we use to send things via snail。

Mail via the US Postal Service or beyond that internationally。

 so I give you in just 60 seconds or so what it means to send a packet on the Internet， for instance。

 from Phyllis in the bottom right hand corner to a familiar face， Brian at top left。

 if we could dim the light， if only to be dramatic。😡，So throughout thank you， sure。

 we can coap for that。And we actually should clap for that because you're seeing this sort of final version which looks kind of perfect。

 but they were all smiling and clapping because it took us so many damn takes to actually get the coordination of that correct。

 but for now assume that it was in fact correct， but notice what's among the takeaways from even that little skit is that the packet。

 the envelope from Phyllis to Bryan could have taken any number of pads it could have gone up and then to the left it could have gone left and then up it could have zigzag and the like and that's actually representative of how the world now looks because of so many wires and so many wireless connections。

 there's actually a lot of ways that data can travel from point A to point B。

 and it turns out it's not even necessarily going to be the shortest difference it might be the least expensive distance or perhaps just the result of how some humans or some servers have automatically configured the routes to get from point A to point B。

 So let's consider how the data is actually getting there。 So long story short。

 all of those routers and indeed all devices on the internet。

 including the ones in your pocket or on your laps， speak a language more technically a pro。😊。

Ca nowadays known as TCPI， and this is actually a pair of protocols。

 which is a set of conventions that governs how computers behave on the internet in the human world we have protocols as well。

 for instance， when I meet someone for the first time I very often instinctively sort extend my hand just sort of hoping that they too will extend their hand and shake and that's a human protocol in that it governs how to people in that case intercommunicate servers have the same kinds of protocols but it's all textbased or bitbased instead of of course physical but TCP an IP are two different protocols that solve two different problems and let's focus on the last of them first So IP short for internet protocol is simply a protocol that decides to give all of us a unique address in the world In other words。

 there are these things called IP addresses it's a numeric address that literally every computer in the world has in order to uniquely identify it case in point in the real world。

 we have addresses too for instance in this building here。

 Memorial hall wherere at 45 Quincy Street Cambridge， Massachusetts，02138 USA。And theoretically。

 that unique identifier should get an envelope in the physical world to this location from any other in the real world。

 IP as applied to the Internet， just means that similarly， do devices， Max PCs。

 phones and everything else on the Internet have a unique identifier as well known as an IP address。

 It's a number， but it's typically formatted and in dotted decimal notation so to speak。

 So it's something dot something dot something dot something and just as a bit of trivia。

 each of these number signs represents a value from 0 to 255 So there are four such values。

 apparently and just doing some quick week0 math if each of those values can be 0 to 255。

 how many bits is an IP address， presumably。So 8 bits per number， and how many was this？So 32 bits。

 because if you're counting from 0 to 255， well it's 256 total possibilities。

 that's 2 to the  eighth， which means 8 bit，8 bit， 8 bit，8 bits。 So IP addresses are 32 bits。

 little trivia that's germane only inofar as it does kind of limit how many total devices we could seem to have in the world。

 if you've got only 32 bits， how high can you count。😡，Roughly。就这个。So two to the 32 power。

 which we generally ballpared as 4 billion， which is to say you can have 4 billion devices total。

 it would seem on the internet， which is a big number， but there's also a lot of humans nowadays。

 and odds are almost everyone in this room has at least two devices to their name。

 maybe a phone and a laptop with which you're taking the course。

 maybe even more devices thanks to the internet of things like smart home devices。

 we have so many IP addresses being assigned to things So long story short the world is gradually transitioning from this version here IPV4 to IPV6。

 which instead of using 32 Bs is actually using 128 B。

 which is crazy large and gives us more than enough IP addresses for this foreseeable future to be fair。

 we've been talking about this for like 2030 years transitioning from V4 to V6 and it's still gradually in motion but for simplicity in the class and in general。

 we'll still use IPV4 if only because it's a little easier to wrap your mind around。

 Now this is admittedly a pretty arcane diagram。 but this is the diagram ASI if you will。

 it's in the official specification。Of what we mean by an IP datagram more colloquially this is what a packet actually looks like now what are we looking at well you're just looking at like a grid of bits so this here represents 32 bits total where this is bit0 and that's bit 310 indexed all the way over there and then each row represents 32 more bits 32 more bits 32 more bits which is to say anytime a computer like Phyllis sends an envelope of information on the internet it contains at least this information。

 a whole bunch of bits broken down into bytes now the only ones will really care about today or this one here source address which is to say when Phyllis sends that packet she writes her source address。

 her IP address， something something something something on the outside of the envelope so to speak and she also puts Brian's IP address。

 whatever that is something else something else thats something else thats something else on the outside of the envelope as well there's a whole bunch of other bits involved which are useful but will wave our hands at those for today but that really speaks to what's actually happening and if we do this。

horically in the real world， it's kind of like taking out that envelope。 and for instance。

 if Brian's IP address is 1 do2 do3。4 for the sake of discussion。

 Phyllis in advance of our filming that bit would have written something like1 do2 do34 in the middle of the envelope just like we would in the real world。

 but presumably she wants Brian to be able to reply to acknowledge receipt or send his own message so she's also going to put her IP address。

 for instance， in the top left corner of the envelope，5。6。7。8 for the sake of discussion。

 so that Brian knows when he writes out his own packet of information how to actually or to whom to reply。

 But at the end of the day， it's all just bits being sent in a specific pattern and there is formal documentation is' the order in which all of those bits will actually be sent out on the wire or wirelessly。

 So in short， IP ensures that all of us have unique I addresses via which data can go from us。

Or to us。 But that's only one problem。 nowadays， of course， servers can do so many other things。

 They can do email and chat and video conferencing， game servers。 and who knows what。

 And it would be nice if a single server certainly could do multiple things。 And in fact。

 that's very much the case。 single servers nowadays。

 and a server is just the term of art for a computer used to serve information to other people by contrast our laptops or desktops are generally clients because they only serve one of us。

 not multiple people， but these are just terms of art， we're describing at the end of the day。

 still computers， IP only ensures that we can uniquely address computers on the Internet。

 but there's another protocol in TCPI namely the TCP portion that allows computers to uniquely identify services that they're offering to the rest of the world。

 So， for instance， TCP allows allows a computer to distinguish whether it has received a packet that's an email or receive a packet that's a chat message or a piece of a video conference or the like。

 which is。😊，SayThere's more than just IP addresses on the outside of these envelopes。

 There are also what are called port numbers as well。

 similarly numeric values that are usually in the range of like 0 to0 on up in the low thousands and they're standardized。

 for instance， if you are requesting a web page using HttP colon with which all of us are presumably familiar unbeknownst to you on the outside of the virtual envelope that your computer subsequently sends is the port number 80 because when the server receives that it knows oh。

 this human is requesting a web page and not for instance。

 their email or something else or nowadays if you're using Https where the S toote secure in the URL you're actually using port 443 which is just an arbitrary number that a bunch of humans in a room decided on years ago to standardize what goes on the outside of an envelope so just to be more clear then when Phyllis is sending a request to Brian and if Phyllis。

 for instance， is the client just a human using a computer and Brian in this story is now a web server。

Better yet a secure web server that's somehow encrypting or is scrambling the information to keep it secure。

 Well on the outside of this envelope after Brian's IP address， which was 1。2。3。

4 Phyllis is also going to write the number 4，4，3 so that when Brian receives and opens this envelope he knows what he's looking at a request for a web page and not an email or chat message or something else。

 Moreover， we can continue the story just a little bit further。

 Phyllis also writes on the envelope not only her IP address 567 but some number as well in that top lefthand corner。

 whatever it happens to be， which is a port number via which Brian can reply to her in this way。

 Phyllis can in effect， have multiple tabs open be using zoom some chat software or something else running multiple programs on her computer。

 and the internet packets are all coming in， but her computer knows to which tabs or applications those packets belong so if you really。

You wantanna geek out。 Here's what this thing looks like。

 This is just the sequencing of bits for TCP as well。

 which is to say in addition to the dozens of bits we looked at a moment ago that standardize what IP is putting on the outside of the envelope。

 TCP is adding 16 bits that specify a port number， which means you can indeed have tens of thousands of possible port numbers。

 a destination port number and a bunch of other stuff， including this so-called sequence number。

 which happens to be a 32 B value， which is actually pretty important。

 because quite often when sending messages on the Internet， they're pretty large。

 and it would be nice if one person downloading a big image or one person downloading a movie or streaming a movie doesn't mean that no one else on the Internet can do something else at that moment in time。

 So for the sake of discussion， suppose that this very happy cat here is a very large Jpeg， instance。

 a very large graphical file。 it would be nice， let's say that if Phyllis is trying to send or receive an image as large as this It's not just in one massive envelope that's going。

Revent a whole bunch of other users from similarly using the Internet at that moment in time。

 So at the risk of a bit of heresy， we can actually tear this cat in half and fragment it really。

 and then inside of Phyllis's envelope or equivalently， Brian's reply。

 depending on where this cat is coming from or going to part of that cat can go in this envelope and now say in the bottom left hand corner of this envelope。

 Phyllis or Brian could write the sequence number in question 1 out of four，2 out of4，3 out of four。

4 out of four so that when this and hopefully the other packets arrive at their destination。

 the recipient's computer can check okay this was a really big file in this case。

 do I have all of the parts， Yes， it can be inferred from the so-called sequence number。

 which we've represented there in that memo field of the envelope。

 There's a bunch of other stuff that can go on here to including prioritization of data as well。

 but ultimately TCP just allow servers to handle multiple types of services。

And also allows it to receive data reliably because if， for instance。

 a recipient only gets two out of the four packets or three out of the four packets。

 the fact that there's a sequence number involved is enough information for that recipient to say to the sender。

 hey， I'm missing one or two or three or more packets， please resend them。 So in short。

 TCP guarantees delivery by just doing some bookkeeping on the outside of these envelopes。

 So in short， I allows us to uniquely identify computers and TCP guarantees delivery and allows us to multiplex。

 so to speak， among multiple services on the same device Que on the this jargon。😊，Thus far。

 because it is filled with acronyms， unfortunately。Questions IP， TCP or anything else。

 okay so seeing none， as promised let's do yet another acronym。

 So it would be pretty tedious if Phyllis and Brian and all of us humans had to write actually I addresses into our browsers when visiting websites and in fact。

 when most of us never do that instead we go to Google co or Harvard Edu or actual domain name so to speak。

 which were so much easier for us humans to remember then these arbitrary IP addresses that are either automatically assigned to computers or manually configured by humansconfiguring servers but there's another acronym in the world and there's another technology used on the Internet namely DNS for domain name system。

 and this is just a certain type of server that every home has even if you didn't know it every campus has every company has there's so many DNS servers around the world。

 but their purpose in life quite simply is to translate what you and I know as domain names like Google。

😊，Harvardedu and the like into their corresponding IP addresses。 And so in short。

 inside of these DNS servers are essentially like a two column table or spreadsheet。

 however you want to think about it whereby here's all of the domain names in the world here all of the corresponding IP addresses in the world。

 And so when your Mac or PC or phone being used by you is trying to access Google co or Harvardedu that device certainly when it's first booted up has no idea what IP address what the IP address is for that server it's not the case that Apple or Google or pre-installing billions of IP addresses inside of our devices but your device is smart enough to ask the local network at home on campus or at work what is the IP address of Google what is the IP address of Harvarded and then what your Mac PC or phone actually do upon getting that answer from one of these local DNS servers is it writes the corresponding IP address on the outside of that envelope So it's a wonderfully useful service that just makes the internet more useful。

For you and I to use because we can use names instead of I addresses as well。 technically。

 these things are called fully qualified domain names。

 where do they come from Well some of you might actually have your own personal website。

 you might have gone through this process。 It's actually not that hard to get your own domain name you can go to any number of what are called internet registrars and pay them some money and it's essentially on a rental basis。

 So you rent a domain name for a year or maybe three or five years at a time and they can automatically bill you the domain name might be as little as a dollar per year or thousands of dollars per year depending on whether someone has scooped it up and is maybe squatting or the like but all you do ultimately is pay someone money and they give you the rights to use that domain name and then what you do technically is you can figure some DNS server somewhere in the world to know what the eventual I address is for your server that's going to serve up your domain names web pages and long story short with DNS。

 I say that you have one in your home and on your work and on your campus because it's very hierarchical kind of structure like。

There is out there somewhere the so-called root servers that essentially know what the IP addresses are of all of the dot cos。

 for instance， or all of the doeddus or the like， but my Mac doesn't know that and so my Mac might actually ask that root server。

 what is that IP address but more efficiently my Mac is better still going to ask the local network first whether my home it asks my home DNS server which is built into the little home router that you've got somewhere in there or if you're on campus it asks Harvard's DNS server and this whole design is recursive to borrow a term from a few weeks ago in that if my computer doesn't know the answer。

 what's the IP address for this domain， if Harvard doesn't know the answer。

 it eventually gets escalated to those so-called root servers but then cached that is remembered by all of these other DNS servers along the way so it's a very elegant hierarchical design but at the end of the day its just doing this it's a big cheat sheet of domain names to IP addresses and the server is responding for us。

All right， one more acronym。 So how do I know what my max IP address should be。

 How do I know what my phone's IP address should be。

 How do I know what the IP address is of the DNS server of whom I should be asking any of these questions how do I know the IP address of the router to whom to hand my data off to like there's a lot of assumptions built into the story we've been telling and the answer is unfortunately yet another acronym DHCP is the solution to all of those problems and it wasn't always back in my day we used to have to manually type in what our computer's IP address was based on what some human told us it would be。

 We had to type in our DNS server type in our router address but now now DHCP is just yet another server running in your home network running on campus running in your corporate network whose purpose in life is to answer questions of the form what is my IP address which is to say when you boot up your Mac your PC your phone for the first time it essentially broadcast a message like hello world。

 what's my IP address and hopefully there's one such。

DHCP server on that local network wired or wirelessly that will respond based on how Harvard or Comcast or Verizon or someone at home has configured it to tell you what your device's IP address is。

 what the IP is of your local router， what the IP address is or are of your DNS servers and the like and so this is why things just work nowadays once you've connected to like a w-fi network or physically plugged in dynamicynamic host configuration protocol didn't always exist。

 wonderful that it now does。All right， enough sort of outside of the envelope stuff。

 Everything else today will be a deeper dive inside the inside of this envelope to look at what actually are the messages that we are sending。

 receiving， how are you structuring the web pages and designing everything that comes back from the server to the client。

 and let's dive in then to this acronym， H T TP， which you've been typing for years or seeing for years。

 even though you don't really have to type it anymore because browsers just assume that this is what you want。

 But H TtP is another protocol。 Hypertext transfer protocol whose purpose in life。

 is to request web pages and receive web pages as a protocol。

 it just standardizes like what goes inside of that envelope when you're trying to use the web。

 There are different protocols for email， different protocols for Zoom。

 different protocols for Discord and any number of other Internet services。

 will focus predominantly today on H TTP， which happens to use ports 80 and 4，43。

 among others as we saw So let's see what H T TP it。😊，Is all about or HttPS。

 the corresponding secure version thereof。 So here is a URL canonical URL in that it has a whole bunch of components。

 Let's consider what some of the jargon is that we're gonna start taking for granted。

 So if you go to Ht colon www example com s you are implicitly requesting the root of that website root just means the default directory。

 the default folder， if you will。 And that's what the yellow highlighted slash here just means like give me the default webp page。

 technically speaking， what you're going to receive in your browser unbeknownst to you is an actual file by convention it's a file called index do hml。

 maybe index hm or any number of other files。 But it would be pretty stupid if we as humans all had to type out the actual file name that we want So the server by default is just going return you the root of the website if though you're inside of a folder or you do actually click on a link that leads you to a file。

 you might very well have at the end of this domain name a full。Path as well。

 which might contain zero or more folder names and0 or more0 or one file names as well。 In fact。

 it could be explicitly file htl or slash folder slash orlash folder slash file htl。

 you've probably seen thousands of these over time。 even if you haven't really given it much thought。

 So we today onward will be creating all of this stuff here。

 but we need to understand what's going on to the left too So here's the socalled domain name or more properly the fully qualified domain name。

 And it has a few different parts too。 So this is technically the domain name as we all refer to it。

 something dot something dot com means commercial and that do co is more specifically known as a top level domain or T LD back in the day。

 there are only a few of these dov do co net do org Edu and a bunch of others Now there's hundreds。

 if not thousands of them。 many of them aren't really used prominently in the wild。

 but there are some not on that original list like C50 uses do I O a lot。

 which doesn't mean input output。😊，It's actually a twole country code that has been essentially rented to us and anyone else using that same TLD because in the Englishglishspeakingworl Io actually sounds kind of cool。

 It's kind of connotes， indeed input and output TV as another one that actually belongs to a country。

 but in fact， also sounds like in English television。 and so that too has been used as well。

 but in general， there are tople domains like these。 some of them now are full words。

 some of them are two characters denoting they belong to a country。

 They are the sort of tople indeed categorization of all of these websites。 Meanwhile， many URLs。

 but not all also have something to the left of the domain name known as a host name。

 which technically speaking refers to the name of the server that you're requesting specifically。

 it doesn't have to be literally one server， Www can refer to dozens of hundreds。

 thousands of servers。 indeed if you go to any popular website like Gmail com or the like even though you only have one domain name somehow or other technologically it is referring to clusters。

Hundreds or thousands of servers that ensure that they can handle all of the customers that might visit that site。

 And then lastly， there's this， the scheme or the protocol in you specifically。

 And for our discussion today， it's always going be HtPS。

 which is ideal because it's secure and encrypted somehow。

 but it can also be indeed HttP colon s So that's it like that's just the jargon with which you should familiar when it comes to URLs like these and what we'll be doing today is actually creating content that lives at URLs like that and serving it up to us。

But what do the messages ultimately look like that are going inside of these envelopes。

 What the URLs are doing are just getting us to the right place。

 But how do we express in some form of code that we want this file Htl from this server using encryption in this way。

 Well， inside of the virtual envelopes that Phyllis was sending to Brian and he would have ultimately sent back to her are messages that look like this get post and a bunch of other verbs。

 if you will。 So HttP supports a bunch of operations or verbs namely get post and a few others。

 and it was the first of these that Phyllis would have put inside of her envelope initially。

 in order to get a web page like a cat from Brian specifically inside of the envelopes。

 She would have had a textual message。 It's not code per se。

 there's no functions or loops or variables or anything like that。

 It's a protocol just in a sense that humans years ago。

 standardized what messages should appear inside of those envelopes if you want to get a web page from a。

So， for instance， if Brian in this story is now suddenly Harvard edu。

 specifically wwwdu Phyllis's envelope would have contained a message saying get in all capslash if he just wants the root or the default page from Brian server。

 the version of HtP that she's using。 for instance， version 2。

 And she would also specify just in case Brian is multitasking and serving up websites for different domain names on the same physical box。

 which actual host that she wants and maybe a bunch of other lines as well。 And hopefully。

 if all goes well， Brian would have responded with an envelope of his own containing an HttP response in answer to her HttP request and Brian's envelope would have contained a textual message that just confirms what version of HP he's using a status code。

 which is an arcane number that just indicates in this case that everything is okay all is well。

 And he would specify the type of content。 He's sending back to her in his own envelope because it could be Hl more on that to the later today。

 it could be a Jpeg， it could be。If it could be any number of other file formats。

 and this is just a hint to Phyllis' browser as to what's gonna be inside of that envelope she is getting back within her browser and then maybe a bunch of other stuff as well。

 So even though some of these details like these underlying implementation details might visually be new to you if you've never really thought about it。

 turns out we as aspiring programmers can actually see and poke around with these building blocks and ultimately today take advantage of them。

 So you're about to see a program that's called curl， which sounds for connect URL。

 it's installed in Linux systems like C50， it also comes with Mac and PCs quite frequently or you can easily install it。

 and essentially it's a headless browser that allows you to pretend to be a browser and grab the response from a server by pretending to by actually sending the contents of an envelope like this。

 So for instance， if I want to pretend to be a browser and request harbor ED。

 I can type this in my C 50。let me go ahead and maximize that size and do the following curl I。

 which specifically is only going show me the headers， the text that we were just talking about。

 and it's not gonna to send any of the contents of Harvard's website。

 Cur Itps www So if I were typing this into a browser I would see's home in this case。

 I'm just going see the contents of the as black and white text on the specifically only the first few lines。

 the socalled headers that the server is responding with as claimed Brian would to fill I hit enter。

 and there's indeed more lines than I had in my slide。 but you can see that everything is fact。

200 This is a convention200 means all is okays a bunch of other information here including the date and time in which this response came back。

 Here's that contenttml and then some other details and a whole bunch of other information as well。

 So that's one way of seeing what's going on underneath the。Well。

 what other responses might come back Well， it turns out that 200 okay is the best possible outcome。

 but there's a bunch of other outcomes that are possible as well。 For instance。

 sometimes you'll get not 200 but 301 which means moved permanently colloquially speaking And what does this mean Well。

 if a server response to a browser with a numeric code of 301 that means that the browser is supposed to go to this location instead it's sort of like putting a detour sign on the server that says there's nothing for you here。

 go over here to this location instead。 and now notice in this example it's telling the user to go to https colonlash www do that's actually what I type before。

 So I would not have seen that myself but if I go to back to vs code here。

 and let's run the exact same command but let's try to visit the insecure version of Harvard's website HtTP colonlash which just means that anyone else on the Internet can technical。

See what it is I am now doing with my browser， which might not be desirable。 En this time。

 Harvard server does not just tell me 200。 Okay， It actually says 301 move permanently。

 And if I read lower in these lines， there indeed， is the location to which I should actually go。

 And it's a subtle difference。 It's forcing me to go to H T TP S instead without actually showing me the contents of Harvard's website。

 So nowadays you and I don't even have to think about this， you and I are not even in habit。

 surely of typing HttP colon slash or H TtP colon slash。

 but the browser is in in this case that you are redirected。

 so to speak automatically to the secure version of that site instead。

 Now there's other status codes。 And in fact， even if you never realized it before now。

 what numeric code do you essentially you sometimes see on the Internet when something goes wrong。

404。 so 404 is a weirdly public arcane error number。

 error number or status code that just means file not found。 and we can simulate this as follows。

 for instance， if I ink my terminal window do curl htps colon www I'll suppose that Harvard has a whole department dedicated to cats。

 which it does not but if I enter here， you'll see that I get an http to 404 status code。

 which just means the website does not in fact exist。

 And if I visited htps colon www slash cats in my browser。

 I would presumably see some error page that may or may not show me visually 404。 but many websites。

 most websites for better or for worse reveal this number so much so that most everyone in this room is probably familiar with 404 even though its origin is this very lowlevel arcane status code buried in the htP headers inside of envelopes like the。

There's a whole bunch of others。 If you'd like some fun facts。200 is indeed okay。

301 is moved permanently。 There's a bunch of other 300 ones that all relate to go elsewhere。

400 generally means that you as the user have somehow done something wrong or next week as we start writing code that talks to web servers。

 maybe your code has done something wrong when requesting a website500s or really bad。

 It means the server is messed up somehow either it's not available or the programmer made some bug in their code。

 such that it's crashing with， for instance， something like an internal server error。

 we included 418， which is not actually a thing， but it was a fun sort of April fools joke years ago where a bunch of humans thought it would be funny to write up a whole specification for what it means for a server to respond with a number of 418 inside joke not funny at the moment。

 but it is sort of part of Internet lore nowadays We can have a little bit of fun with this。

 maybe at the expense of our dear friends down the road for years now。

Someone has been paying for the following behavior。

 Let me go back to VS code here in my terminal window。 Let me do curl I， HtTP。

 Col slash slash safetychool org。 Have you ever been。



![](img/4c54343641083e31267eb96a2dc6e4c4_1.png)

Ever apply， perhaps。 Well， let me actually go to HDP slash slash safetyschool do org。

 And just for fun， hit enter。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_3.png)

Oh my goodness。 Look at where we are。 So how is this implemented。 Well。

 if I finish what I began over here by just looking at the HB headers inside of the envelope。

 my actual browser just sent to safetychool org for like 20 years。

 presumably some Harvard alum has been paying the bill to rent this domain name just to have this trick implemented such that 301 move permanently is directing people ever since to Yale Edu。

 There's a bunch of others if you go down the rabbit hole looking on Reddit and the like Stanford Berkeley。

 there's a healthy competition on East Coast and West Coast。

 but it all boils down to very arcane understanding of how H TTP works。

 the protocol that governs how data is sent from Web browsers to web servers。



![](img/4c54343641083e31267eb96a2dc6e4c4_5.png)

Now， you can， of course， use curl for connecting to URLs in the context of something like CS S50。

 You could have been doing stuff like this all the time， though with your actual browser。

 So I'm using Chrome here for most any browser nowadays has the ability to give you developer tools natively。

 which is to say somewhere there should be an menu option that lets you use developer tools that are conducive to someone who knows a bit of programming to poking around underneath the hood of the browser and see what's going on。

 For instance， I'm going to go ahead and open up new window here。

 And I'm going right click on the background or I can go to the appropriate menu and Chrome's do do dot menu and I'm going go to inspect。

 which pulls up what we're gonna call developer tools。

 I'm doing an incogni mode for reasons we'll see next week。

 this has the effect of clearing automatically any of my cookies。

 my browser history because most any time I do something with the web browser today。

 I want to pretend like I'm doing it for the very first time so that the behavior is exactly as we suspect expect。

 So down here now。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_7.png)

NowThat I've opened up the Socalled developer tools in Chrome。

 and they look almost the same in safari and E and a bunch of other browsers as well。

 I will see a tab called El， which shows me all of the elements of this web page once it appears。

 including the socalled H code。 We're about to write。

 I can see a console where error message might sometimes appear similar in spirit to the terminal window in VS code。

 I can also see the network connections that the browser is making to the server。

 And that's where I thought we'd start our attention here。 Here I have a brand new browser window。

 I'm clicking on network over here。😊，Just to make sure we can see everything without it getting automatically deleted。

 I've clicked on preserved log and disable cache just so that it behaves exactly as expected。

 And now let's go up here for the first time in this incognito window and go to H T TP colon slashlash safetyschool org enter。

 and you'll see a whole bunch of output， including this warning in this particular mode。

 This is increasingly common nowadays for websites that do not support H T Tps。

 which this alum hasn't been paying for you'll get a warning typically that specifies you might not want to do this。

 because the whole world， at least the whole world between you and point B might know what it is you' accessing on the web。

 I can go ahead and pass through this。 In fact， once I do that。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_9.png)

And click on connect to site。 We'll see even more output at the bottom。

 and a whole bunch of output that's kind of overwhelming。 noticeice at bottom left here。

 just going to safetychool org resulted in 61 HttP requests in effect 61 envelopes going back and forth。

 I'm gonna focus though on the ones at the very top here whereby when we finally click through that warning。

 And I got back a response from the server having visited safetychool org here is Chrome's presentation of the same information that K was showing me in my terminal window the message that came back was 301 move permanently the protocol the ver being used was get。

 there's some mentions of the IP address in question here in a whole bunch of other stuff that will wave our hands at for today。

 So all of this time you can see the same。 And let's try this with some cats。

 Let me click on the little ghostbuster symbols to clear everything down in the developer tools。

 Let me zoom out。 and this time， let me go to Htps Collash www。



![](img/4c54343641083e31267eb96a2dc6e4c4_11.png)

Har you slashcas， which recall did not exist according to curl。 If I hit enter。 I do see a web page。

 It's interesting that Harvard has chosen to fairly arcanely reveal to all visitors 404。

 which means nothing except in soof far as the status code。

 But if I scrolled through all of the 59 requests that were involved and just displaying this very graphical page and go back to the top you'll see by clicking on the first row for cats itself that I used get to get it that URL slash cats in the end and it was indeed 404 not found。

 So you can sort of have all this phone on your own by just poking underneath the hood of what your browser has been hiding from you。

All of this time。All right。Any questions now before we dive in。NoAll right， well。

 that's the network tab。 Let's look at some of the others and see how we can start writing this stuff ourselves。

 Let me go to Stanford do you enter。 A whole bunch of things will fly across the screen。

 but this time I'm going to go to the elements tab And we're about to dive into is an actual language。

 not a programming language。 a markup language called Hml hyperpertext markup language whose purpose in life is just to tell browsers what to display on the screen。

 So here is all of the so-called Html that some human are humans or software at Stanford wrote in order to create Stanford's homepage。

 which as of today looks lovely like this The interesting thing though。

 about the code that Stanford has written to generate this website is that it's being sent to me as a copy。

 and this is quite unlike the code we've been writing thus far。 you wrote code in scratch。

 who was sort of there in the browser stored on MiT server when you wrote C code and ran it。

 it was inside of the code space and not given to any user who might access it。

 the way the web works though is a little bit different inside of those envelope。



![](img/4c54343641083e31267eb96a2dc6e4c4_13.png)

Are literally copies of what's on the server being sent to the browser。 And so it's your browser。

 the socalled client that's actually reading that code， Hl in this case。

 top to bottom left to right and figuring out how to display it。

 It's not executed on the server per se。 Now that story is going change a bit next week when we start using Python to dynamically generate Hl so that we're not writing all of this code by hand after this week。

 But for now， everything you see was the result of the browser executing code that Stanford wrote。

 The implication of that is that we can have a bit of fun with these same developer tools。

 For instance， if I control， click or right click on something like the word Stanford in the middle of their homeage choose that same inspect option。

 What's nice about these developer tools is it's gonna to jump to the very line of code that created that Stanford brand name in the middle of the webage。

 And this is a wonderful teaching and learning tool because in the days to come when you're trying to learn more and more HTML。

 you can literally do this for any website on the。😊。

And understand how it is someone implemented a design， for instance， that you really like。

 And you can learn from other websites how they've constructed the same。 So over here。

 you'll see that the word Stanford is just in the source code of this page。 and the socalled Hl。

 And you know， just for fun， I can change it to Harvard hit enter。

 And now Stanford's website looks like we've been there。 and rather hacked it。 Of course。

 it's not that easy to hack Stanford's website。 What have I presumably only done just now。😊。

I've changed my local copy of that particular website。 So if I just click on the reload icon。

 I'll actually see that West Stanford's website for better or for worse， still looks like that。

 But this speaks to now the control that we have within our browser to actually manipulate and learn from what it is that's going on underneath the hood。

 So let's dive into this language called Hl hypertext markup language。

 It's not a programming language， which means we're going to fly through it even quicker than usual。

 because it really just contains some basic building blocks。

 I do have some interesting intellectual design under them。 But for the most part。

 it becomes an exercise ultimately， and just like looking up other tags that exist。

 read the documentation and figure out how you can use them to do other features in websites。

 So let's take a look at perhaps the simplest of web page and specifically gleaned from them what tags are and what attributes are really the only two terms of art that are going be g for this particular language。

 No loops， no conditionals， no variables， no complexity， really。

 other than basic building blocks like these。 So here is Hml for the。😊，Simpst of websites。

 This is like a mini version of what Stanford's team presumably wrote on their server。

 but it's only like a dozen lines of code instead of hundreds or thousands。

 however along that website was Any web page written today。

 assuming it's using the latest version of Hl， which happens to be version 5 as of today begins with code that looks like this。

 This kind of code will presumably be stored in a file called file hl index hl Stanfordl。

 whatever the file is actually name This is simply what's going to be inside of the content。

 You could save this file on your own Mac， open it up and your browser would open it。

 but you're gonna be the only one in the world they can actually see the contents of that web page if it's just on your Mac or just on your PC So we。

 of course， are going to be writing hl on a server so that not just you， but in theory。

 especially for your final project， anyone on the world with an Internet connection can access the same So we within the context of C50 dev are going start using this new command HtP server。

😊，Purpose in life is just to serve up files via H TTP。

 Now there's kind of an interesting design going on here because if we use if we use C 50 do otherwise known as Github code spaces。

 there's already a web server running on that website because when you go to C50 and log in and get redirected some longer URL。

 You're using a web application， Aka VS code that allows you to write code in the cloud。

 Now that application by default is running on port 80 and 443。

 So it doesn't matter if you start HtP or Htps both will work。

 but that means that your code that we write today and you write for the next problem set or for your final project。

 can't live at port 80 or port 44，3 because Github。

 the company that hosts this is already using those default standard port。

 But we can use any number of other port numbers I claimed earlier there's tens of thousands of numbers that we could use。

 So that's what we're actually going to do。 So let me go back to Vs code here。 let。😊。

Shrink down my terminal window。 Let me create a first file today called for instance。

 Hello dot Hml enter。 And now I've got an empty tab as usual。

 I'm going to very quickly whip up the exact same contents that we just saw。

 So an angle bracket and exclamation point， doc type H TM L。

 then open bracket Hl closed bracket and notice the autocomplete kicked in for this particular language。

 So I don't have to type everything myself inside of this tag。 So to speak。

 I'm now gonna put a head tag inside of which is gonna be a title tag。

 I'm gonna say something like hello title just to be quick。 And then down here below those lines。

 I'm gonna put a so-called body tag inside of which is hello body just for some quick text and that's it。

😊，This is now a file inside of my code space and there's no command to just compile or run this in the terminal because the goal is going be to open this HTML file with a browser。

 If I want to do that in another browser tab I need to tell my codespace to serve that file via HttP So the simplest way to do this is as follows Http server enter。

 you're gonna to see a whole bunch of text on the screen。

 you're gonna see a green button hopefully pop up that says open in browser。

 which is going allow you to open up and I'll zoom in the content of the current folder with a web browser。

 My URL has changed to be different from what it was a moment ago I came in advance today with my own folder of code like we usually do source 8 which contains all of today's premate examples。

 but here is the file I just created a moment ago。 And if I click on that hello Htl what we're looking at at the moment is just a directory listing。

 a directory index of all of the files in my codespace right now。 I see the simplest of web pages。

 It's a little underwhelm。

![](img/4c54343641083e31267eb96a2dc6e4c4_15.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_16.png)

But clearly， here's hello body， which takes up like 95% of the screen， the so-called viewport。

 which is just the big rectangular region of the screen。 But theres the title in the tab up there。

 So if you've ever wondered or cared like where does the content in web page come from。 Well。

 here's the body content。 Here's the head or the title content。

 and then everything else is just sort of icing on the cake。

 So I've written at this point a file called hello do Hml。

 it has yielded this effect of having something in the head in the head of the page in the body。

 but let's actually tease apart what just happened。

 So at the start of any file written in this language called Hl， the latest version thereof5。

 it literally just starts with this。 And this is just the kind of thing you memorize or copy paste open bracket exclamation point dot type Htl closed bracket over there。

 It looks a little bit different because we're not going use for the most part。

 the exclamation point syntax anywhere else。 unless we're using an HTML comment。

 So Hl has comments just like Python C and other languages。

 But let's focus really on this juicier part。😊，Here we have what's known as an element in HTML。

 an element includes a start tag and an end tag or equivalently an open tag and a closed tag。

 So here for instance， is syntax that essentially is going to tell the browser when my browser reads this file top to bottom left to right Hey browser here comes the HTML of my page and the language in which the contents of this page are written are in English。

 So HTML all lowercase is the name of the tag so to speak and equivalently the name of the element Lng is what's going to be called an attribute which just modifies the default behavior of the element and quote unquote E is the value thereof。

 which is the shorthand notation for English and there shorthand notations for most every human language as well。

 So you have a tag name and an attribute with a value。

 and we've seen these things so many times these key value pairs in the context of dictionaries or hash tables or any number of other context。

 key value pairs in HTML are separated by an equal sign。With the value typically quoted in this way。

 doubleub quotes are single quotes， but being consistent。 Then notice at the end of this file。

 as per the indentation， there's something symmetrically down here that has the effect of closing the tag or ending the tag。

 and this effectively tells the browser。 Hey browser。 That's it for my H。 Meanwhile。

 everything else follows the similar paradigm inside of those two tags。

 Here is a head tag that says hey， browser here comes the head of my page。 Hey， browser。

 that's it for the head of the page。 Hey， browser inside of the head here comes the title。

That's it for the title。 Well， what is the title， Ho comma title just as I wrote in my code space。

 same story for body。 Hey browser here comes the body of the page。 the 95% of the screen。

 that's it for the body。 but what's in the body is exactly that the indentation is nice and pretty printed I've used four spaces as we commonly do not strictly necessary in fact。

 in my own code space I didn't even bother putting these on three separate lines I just did one line that's fine because as we'll see browsers typically ignore white space。

 but I've done it there as we often do just to ensure that things are pretty printed and therefore readable by us humans let me call your attention to one other thing on the screen until now before every lecture。

 I've been hiding a whole bunch of tabs in my terminal window but today I left enabled one that you've probably seen but not cared about before。

 namely ports and it's under this ports tab that you can actually see a real incarnation of a TCP port by default。

 when you run the command HtTB server It serves up my。ren folders content on its own web server。

 its own HP server， but not using the default port 80 or 44。

3 because Github is already using those on CS 50 do dev and their product。 But by default。

 we've chosen another common developer port number 80，80。

 which is interesting only inof far as it's 80 twice， but it's a human convention。

 but it could have been any number of thousands of other possibilities。

 but this line here is just telling me that I am some apparently running a server on port 80，80。

 And if I click on there too， I can manually open the same tab。

 But that's what the green button was doing for me， It was informing me， hey。

 you've just started a web server on this port， do you want to open a new tab with the contents thereof。

So。This is the picture we're now painting。 Let me pull back up the code that we just wrote and let me propose that what we've really done is built a tree in the browser's memory。

 So we kind of have come full circle with week 5。 when we talk about trees and other hierarchical structures。

 if we assume that the document can be represented with a node that looks a bit like an oval up here that just represents the whole contents of the file。

 Well， it starts with a single root element by convention。

 the HTMLl element and your page can have only one of those elements。

 But the H tag inside of it can be a head tag and a body tag。 And in this case。

 the head tag recall had a title tag as well as the actual text thereof， which was hello title。

 Meanwhile， the body had just the text thereof as well。

 And so when I keep saying that the browser is downloading the file for instance。

 hello do Hl reading it top to bottom left to right， it's doing literally that。 But somehow or other。

 it's using malloc or whatever language it's written to allocate node， node， node。

 node node and populating that tree in your browser's memory。😊，Or Ram。

 a data structure quite like that。 So it's all sort of germane to where we've been。Before。Before now。

 we take。I think a snack。Are there any questions？About what we've just seen。

Anything at all shouldn't have prefaced this with the only thing between us。

Is these questions and snacks？No， all right， snack time， all right， see you in 10， snacks。All right。

So we are back and pretty much everything we do here on out will look structurally like this。

 and we're just going to introduce a few more tags and a few more attributes to give you a sense of some of the basic building blocks of most any website out there and you'll find pretty quickly that it starts to get kind of tedious writing it out。

 In fact I will resort to some copy paste today just to kind speed things up but this is gonna motate indeed next week when we reintroduce Python as well as SQL to actually automate generation of H as well So all of today's websites and many of today's mobile apps are written in HTML but people are in decreasing writing this kind of stuff by hand。

 rather they are writing code that generates precisely what we're going to learn So understanding the fundamentals will still be useful so we know what code to write next week and beyond So let me go back into VS code here and what I'm going go ahead and do is open up another terminal window so that I can leave HP server running in this first terminal window and what I'm going go ahead and propose that we do is implement a web page that has not just a single line of text but maybe。

Some paragraphs。 So I'm going to call this paragraphs dot Hml。 that's going open up a new tab。

 And here's where I'm gonna save some time。 I'm going to go back to hello dot Html and just highlight all and copy。

 paste this as the beginning of this file。 But what I'll start doing is just changing the title of each page to match the file name。

 So this is gonna be my paragraphs example。 And instead of saying just hello body。

 Let's actually have a few paragraphs of text。 I'd rather not waste time writing even full paragraphs of text。

 So let's actually open up the duck。 And let's log in。 And for instance。

 just ask it for a quick helping hand here。 write three paragraphs about。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_18.png)

Computer science。 don't really care what the output is。

 All I want is some dynamically generated text to save me some keystrokes。

 And here we have an educational answer there， too。

 even though all we really care about today is the fact that this is three chunks of text。

 Hopefully that's all quite accurate。 Allright， I'm gonna go ahead and highlight all of that。

 go back into my paragraphs Htl tab， paste it inside of the body。

 it's so long the paragraphs that the text scrolls， I can at least clean this up slightly。

 I'm gonna go ahead and just indent it twice just so that at least it's pretty printed inside of the body。

 And now I'm going go back to my other tab， which represents the contents of hello do Htl。

 I'm going click back， which is gonna show me that same directory listing again。

 which now has a new file paragraphs do Html。 And I'm gonna click it so as to see these three paragraphs of text。

😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_20.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_21.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_22.png)

What looks wrong？Yeah。And there's no paragraphs。 It's just one big blob of text。 It's the same text。

 but buried in there is the end of the first paragraph and the start of the next and same for the third。

 So what's going on。 Well， apropos of my comment earlier about browser is not really caring about white space。

 You can put all the white space you want there。 It's just going to ignore it in this particular case。

 All it's going give me minimally is a single space between each of these paragraphs of text。

 So H is very pedantic。 Like if you want there to be more paragraphs， you need to tell the browser。

 put a paragraph here， put a paragraph there。 And the way to do this， thankfully isn't all that hard。

 I'm going go inside of the body here。 And I'm going simply open a tag called open P for paragraph for short。

 notice that Vs code in this particular case a little annoying because it's trying to finish my thought。

 but it doesn't know that I already wrote this text。

 So I'm just going delete what it automatically generated。 And then I'm gonna manually indent this。

 and I'm going to do the same thing again for the other paragraphs up here。

 I'm going open the paragraph tag。 I'm going delete temporarily the closed tag so that I can actually put it below。

That chunk of text here indent this and then down here and this would have been easier if I just did it right the first time I'm gonna to do the same thing with the third and final paragraph。

 So now what we in effect have three times in a row is hey browser here comes a paragraph then the first paragraph Hey browser that's it for the paragraphy browser here comes a paragraph that's it for the paragraphy browser comes a paragraph So three times in total with open close。

 open close， open close now if I go back to the browser nothing appears to have changed yet but's because I'm looking at a copy that was downloaded a moment ago in that virtual envelope So this is why among other reasons we hit reload on web pages to get the latest version and vo now we have three actual paragraphs the whitespaces inserted automatically by the browser but it's at least prettier to the eye now So that then is the paragraph tag So useful of course if we have paragraphs of text what are some other tags we might introduce well maybe you're writing a paper or blog post or the like it's pretty typical to want headings of sections of the page maybe chapters and then section。

And then subsections or the like HTML can help with this too。

 so let me go into my terminal window again。Create a file called how about let's call it headings dot H Tml。

 And then in this file， let me similarly， go back to hello dot Html， copy paste it into headings。

 I'm gonna close paragraphs because we're done with that。

 And I'm just gonna change the title now to headings and inside of the body here what I'm gonna go ahead and do is know it would have been nice to have some of that same text。

 let me go back one step。 let me grab the paragraphs。 and paste that into this new file。

 let me rename it to headings to make clear which file we're in。 And now let me go ahead and propose。

 that wouldn't it be nice if I made clear that this is the first paragraph。

 So I'm gonna to use the H1 tag， which is the heading one tag。

 And I'm just gonna say one for the sake of discussion down here。

 I'm gonna say H2 and say two for the sake of discussion And down here H33。

 because I don't really care what these things are called。

 Just want to demonstrate the functionality if I go back to my other tab now back to the directory listing。

 There's my brand new file headings do Html。 and it's the same paragraphs。

 But now you have some big bold text。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_24.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_25.png)

Looks reminiscent of the chapter heading， the section heading。

 the subsection heading and the like or that you might see on a news site or a blog site or the like。

 So you've got H1 through H6 from biggest and boldest to smaller but still bold and the browser decides on all of those settings for us。

 but it also makes some semantic clarity to me that probably the most important thing on the page at least to begin with is that h1 tag and then everything else is like supporting paragraphs or arguments or whatever the case might be。

 There's a hierarchy implicit there。 All what are some other things we can do with web pages。 Well。

 let me open my terminal window again。 And why don't we code up how about a list of values because lists are everywhere on the internet。

 So let me open up list hl and then close my terminal I'll go ahead and start with that same file headings hl paste it into list change the name here。

 let's delete everything I did And again， the only reason I'm copying and pastcing is just to avoid writing the same boilerplate code again and again with the hl tag tag。

T and so forth。 Let's focus on the new stuff。 The new stuff in this example will be a list of values like the words foo bar and Bs。

 which much like a mathematician， might go with X， Y， Z is placeholders。

 computer scientists would typically reach for words like foo bar and Bas went nonsensical placeholders。

 And this looks like a list of three values， One after the other。 Of course。

 if I go back into my directory index， click on list。 How many list items am I gonna to see per line。

😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_27.png)

Yeah， well， it's gonna be just one big blob of text tier too。

 It doesn't matter if it looks like a list。 It is just going to be text after text after text。

 separated by a single space， not the multiple lines I have。 So here， too。

 we've got to be pretty pedantic。 If I want a list of values， I need to use a tag that conveys that。

 And the tag I use first， is gonna be U L for unordered list， which gives me a bulleted list。

 And then inside of this unordered list， I claim we gonna have a whole bunch of list items or L I for short。

 like foo。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_29.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_30.png)

Like bar， like Baaz or any other things that you want to put in your list。

 If I now go back to my other tab， reload now you get the familiar bulleted lists that you might see in any number of websites。

 Google Docs or the like， how does Google Docs do it underneath the hood while they're just using a U tag and some Li tags inside of that to give you the bulleted list that's just happening automatically。

 when you click the appropriate button in something like Google Docs， which at the end of the day。

 is just a website。 Well， what if I want to number these things。 Well， if I go back to Vs code。

 I can certainly just start numbering them like1，2，3， which is fine， but honestly。

 like computers can count and with loops pretty quickly， Also。

 it's a little annoying if I want to go back in later and insert something between some of those elements。

 I then have to renumber everything manually， I mean。

 this is one of the things computers are good at， So take a guess， if I want not in unordered list。

 but an ordered list that is numbered， what might you change。



![](img/4c54343641083e31267eb96a2dc6e4c4_32.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_33.png)

Yes， O L is a good bet。 Let's change both the open tag and the closed tag。

 Let me go back to my second tab reload。 And now we have it1，2， and 3。

 and you can actually use a whole table of contents。

 You can use sub bullets or sub numberumbering anything you can do in like a table of contents。

 H TL can do for you automatically here。 Well， what about tabular data laying out data in kind of rows and columns。

 Well， we can do that too。 Let me go ahead and open up a new file about table do Hml let me go ahead then in this file。

 copy paste as before。 just so I have some boilerplate。 Let's get rid of everything in the body。

 And then let's just manually whip up a little table like this。

 Open bracket table inside of the table tags， I'm gonna have a T R tag for table row inside of this table row。

 I'm gonna have a table data tag， which is gonna have the number one。

 I'm gonna give myself another to， another three。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_35.png)

Outside of the table row， I'm going to have another table row and I'm going to create maybe four。

 and now I'm going to do five and now I'm going to do six。

 and you can perhaps see where this is going。😡，After this， I'm going to do one more table row。

 How about a little tediously 7， How about 8， How about 9。And then lastly。

 just to make it look a little familiarm， final table row。

 how about with a TD of an asterisk and then how about a zero and lastly， how about a pound symbol。

 maybe any guesses as to what we're making in HTML here？



![](img/4c54343641083e31267eb96a2dc6e4c4_37.png)

Like a telephone keypad。 Yeah， so let's go back over to。 Let me close the old file。

 back over to the browser。 click back。 There's my new file。 table dot html。

 and it's not gonna be very pretty。 but I dare say that's exactly what you see when you pull up the phone app and you start dialing a number。

 It's sort of a numer keypad laid out automatically for me in rows and columns。

 Now this one's a little underwhelm， let me open up a file that I made in advance of class today。

 in my favorites file here， I'm gonna go ahead and copy a premate example。

 I'm gonna open up this file called favorite0 do html。 And what you'll see here。

 it's a slightly more complicated table。 still with a table tag。

 but this time with a T head tag for tablehead。 And then a t body tag inside of which are all of those rows。

 And I know this just by having't read the documentation。

 And then notice this inside of the first Tr in the T head。

 there are three THs table headings timestamp language and problem which might sound a little familiar。

 when we last collected data from。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_39.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_40.png)

One via that Google form。 Well let's go ahead and spoil what this is。

 Let me go back to the directory index。 There is this premade file favorites HTML and arguably a more compelling use of a table。

 Now we have an HTML table containing all of the form submissions that you all clicked in with the other day when we were asking your favorite language and your favorite problem It's not super pretty but indeed it's in rows and columns and so it's reminiscent of the HTML that Google is using in the actual Google sheet software to lay out a sheet of data for you in those same rows and columns All right well let's do something that's a little more visually interesting。

 let me go back to VS code here close out those first those last two and about let's do something with images Well I brought again inside of today's code how about our same bridge that we keep opening up in class and this is the weeks bridge looks a little somethingop looks a little something like this here though it's just the raw image。

 How could I include an image in a web page。

![](img/4c54343641083e31267eb96a2dc6e4c4_42.png)

That I serve up on the Internet。 Well， let's go ahead and try this。 Let me close the paning itself。

 Let me copy this and create a new file called tab about image hl hide my terminal。

 copy paste that just quickly change the title to image So we know where we are and inside of the body of this page。

 let's go in and embed that image so that we can include not just the image but if we want paragraphs of text around it headings as well heck maybe a table。

 any other features that we've seen already。 I'm going to say I amg which is image for short source Src for short equals unquote bridge do Pg and then I'm gonna to close the tag here。

 Now I'm going go back to my other tab go back into my directory index。

 Here's my brand new file image hl。 and this isn't going to look all that different from the actual image because I have no other content。

 but when I click on this you'll see that there is the full screen image and it's even a little too big to fit in my viewport in the body of the page but we can fix something like that later。

 I've embedded in this website precisely that image。 but I should do a little。



![](img/4c54343641083e31267eb96a2dc6e4c4_44.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_45.png)

bitBe here。 In fact， if the image is slow to load or if someone is visually impaired and doesn't know what they're looking at。

 it would be nice to have some alternative text that something like screen reader software could recite。

 So there's another attribute for this tag specifically called Alt for alternative。

 And I can put something like Harvard University to at least give the user a textual description of what kind of photo they're looking at。

 you'll also see that text。 if indeed， the image is slow to load or if it's broken。

 like missing altogether。 You won't see 404。 you'll see like a broken image icon。

 but at least with some explanatory text as to what the developer intended you to see at that point。

 It's not gonna to change at all。 if I reload here， by going back to image do Hml。 But again。

 a screen reader or an astute viewer would see that ultimately in the browser。

 But there's something different。 And this isn't a mistake。For once， what have I done differently。

 but apparently not wrong， I claim。Something new or noteworthy about this particular image tag， yeah。

Yeah， there's no like close tag， There's no like open bracket slash IMG。

 which is the pattern we followed for every other tag， like closing the Hl tag， the head tag。

 the body tag and so forth。 I just don't see any end tag here。 and it's just not necessary。

 turns out there are certain Hl tags that can be empty elements。

 which is to say doesn't make semantic sense to start an end an image。 it's either there or it's not。

 And so some tags just don't require an end tag if it's sort of obvious to the browser that the image should go there。

 So image is one such of those tags。 And then I noticed I'm missing the la here。

 which isn't strictly necessary because I've got no textual content， but just for consistently。

 let me go back and put that in as before。 Meanwhile。

 the image is exactly as it would appear in the screen。

 but it doesn't have to be just an image we embed。 we can do something with like video。

 So let me go ahead and open up a file called video Hl。

 Let me copy paste some of that starter code change this to video。 And instead of the image tag。

 as you might imagine， there's also a video tag。It's a little more involved。

 but per the documentation。 I know I can do this video。 and then inside of the video tag。

 I can actually have multiple sources， just in case the browser might want different versions or different resolutions。

 sort of qualities thereof。 And this somewhat confusingly is an actual tag called source not shortened but stupidly。

 this tag has an attribute called source， which is shortened that equals the name of the file you want to embed。

 And I came with today's examples a video file called videomp4。

 which is a small video that you can embed。 and I can tell the browser what type of video it is to be clear。

 And the convention here or content type is to say the type of this video is an MPg 4 video。

 There are other features， though， for the video tag。 In fact， when you see a video on a page。

 you can very often see like a play icon， a pause icon， maybe some other controls Well。

 it turns out you can put an Hm attribute on the video tag literally called controls that will enable those。

 if you don't turn them on there's no way to。😊，and stop the video or see rather those controls visually this way the user actually sees them。

 but this attribute is a little bit different from others。 It doesn't actually need a value。

 It just has to be present and the browser will know when it sees the word controls oh I should turn on the controls feature and for good measure。

 especially in today's world of advertisements everywhere if you want the video to play automatically potentially or at least not an the user you might want to mute it by default as well So another attribute per the documentation for the video tag is that you can start the video muted as well and only when the user clicks on it might you actually start to hear something but of course these are fairly basic examples of media inside of pages。

 let's actually do what the H is meant to imply in HTML the hypertext the ability to link from one page to another that is a feature we haven't yet seen so let me go ahead and do this and let me just for complete this let me go back into hello HTML because I completely forgot the language attribute even though that's really just there for。

SEo， search engine optimization， or for tools like Google Translate or the like that know therefore what language they're translating from。

 let me go into my terminal window here。😡，And let's create another file called link Htl。

 which demonstrates exactly that。 the ability to link from one web page to another。

 Let's go ahead here and change the title to link。 So I know where I am。

 and in the body of this page， let's go ahead and create what's called a hyper referenceence or hyperlink。

 I'll encourage people in this page to visit the actual Harvard website。

 So let's do visit how about Harvard period， just to demonstrate where we're beginning。

 if I go back into this directory index， click on link do Html， this， of course， is not yet a link。

 So I should probably make it one。 Well， instead of just saying visit Harvard。

 maybe I should say Harvard Eduu。 go back to the other tab， reload and it's Harvard Edu。

 but I can click and highlight it， but it's not click a bull， it's not underlined like a link。

 All right， well， maybe I need to do like www do Harvard Eduu reload still nothing happening。

 All right， well， maybe I need the full URL in the scheme。



![](img/4c54343641083e31267eb96a2dc6e4c4_47.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_48.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_49.png)

GGPS colon s/， and maybe the slash at the end。

![](img/4c54343641083e31267eb96a2dc6e4c4_51.png)

Reload again and nothing's happening。 So here too， H is pedantic。

 Like it will not create a link for you。 unless you tell it to create a link。

 And the fact that when you post on social media nowadays or in Google Docs。

 things are automatically hyperlink for you。 that's a feature implemented in code very often Python or jascript or something else where some human wrote code that looks for patterns in the input you've typed in。

 And if it looks like you've typed a URL， it will automatically link it for you。

 But what are those websites doing for you automatically， Well， they're doing this。

 if you want to have a a link here to Harvard's website。

 you use open bracket a for anchor H ref for hyperreence。

 set that equal to the URL to which you want to link close the tag and then in between the open tag and the closed tag。

 put the actual word you want to link to。 So now if I go back to this page and reload。

 Now I have what looked like my original attempt， just visit Harvard， but it's a hyperlink。

 and this is super subtle。 But if I。

![](img/4c54343641083e31267eb96a2dc6e4c4_53.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_54.png)

Over that underlined word， which is blue by default。

 you'll actually see in the browser's bottom left hand corner where you're gonna be whisked away to。

 even though that's all too subtle。 But this now looks like I intended。

 an actual hyperlink to Harvard。 In fact， I could link it to the full URL。

 But it would be a little redundant。 And even though this looks like you shouldn't have to do this。

 This is indeed how Hl works。 The H attribute is where you're going to go。

 the text inside of the open and closed tag is what the user will see。

 So if you want them to see the full URL， you got to put it there。

 And now I can see the full URL to where I'm being LED。

 But here's where you can actually introduce discussions of like cyber securitycur。

 How could this feature be abused， might you think。



![](img/4c54343641083e31267eb96a2dc6e4c4_56.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_57.png)

This stupid， simple feature， yeah。Yeah， you could have a display one thing but lead to somewhere else and it wouldn't be that hard for the adversary who's maybe tricked you into visiting their webage to say you're actually gonna to go to Yale。

edduu instead of Harvard， but if I reload the page。

 it doesn't look any different unless the viewer is a student enough to look at this tiny little text in the bottom of the screen or just click on the link and be whisked away to the wrong destination。

 that can be problematic like this is a nice haha sort of prank but you could certainly imagine doing this with like Paypal co addresses or any number of banks or anything where you're trying to collect personal information from someone and if the resulting website looks quite like the one you're actually create it looks quite like the website they're expecting but it's actually your copy thereof it's all too easy to wage what are called phishing attacks P IG which means to lead someone to what looks like the real site but is not typically to get their username their password。

 their credit card information or something else。 but it boils down to just。



![](img/4c54343641083e31267eb96a2dc6e4c4_59.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_60.png)

Basic building blocks like this。Questions then on any of these building blocks that we've seen thus far。

 yeah。Sure。Oh， good question。 How did I get it to open up。 So let me rewind。

 So the very first thing we did after creating hello do Hl was open a terminal window and specifically I ran a command which was HttP server HtP server which starts my own web server in my code space but not on the default port 80 and 443 because that's what CS50。

 dev is already using instead it chose by art design 8080 which is commonly used by developers when making websites。

 then I just kind of hid my terminal because it's not interesting to see constantly then。

 but thats web server is still running in my code space and any time I'm saying let's go back to this tab I am now visiting a different URL that was the result of my clicking on that green button which led me to my own website if you ever get lost or close that T by accident。

 no big deal if you go to the ports tab of your terminal you can actually hover over this and click on that same URL and open up the contents of your own site instead。



![](img/4c54343641083e31267eb96a2dc6e4c4_62.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_63.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_64.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_65.png)

Fuffy meme， yes， these are randomly generated names by GitHub。

 which is the company that hosts VS code in this way。

 and they do this to ensure uniqueness without it being some arcane sequence of random letters and numbers。

 they concatenate random English words together。A good question。Allright。

 so what else can we do here， Well， let me propose that there's a bit more you can do with even these URLs Here。

 of course， is the scheme and the host name and the domain and the TLD， but after the URL。

 things can get a little more interesting than just folder names and file names。 In fact。

 it's quite common to see URLs that have somewhere in them a question mark and then a bunch of other key value pairs。

 which is this omnipresent computer science thing it seems including in the context of URLs。

 whereby if you want to pass a input to a web server。

 one means by which you can do that is literally in the URL itself。😡，So， for instance。

 if you visit Google com and you want to search for something， you and I are all in the habit。

 of course， of just typing into a search box。 But how is that search box actually getting the data into Google's servers。

 it's via these URLs。 And if there's not one input but two inputs。

 the URL might be a bit longer and there might be one or more ampersands in the URL that just separate more key value pairs。

 And it turns out we can see this in the real world as follows。 Let me go back to VS code here。

 let me open up a new tab。 and let me open up Google com。

 and I'm just gonna hit enter on the shortest way of saying it。

 So I get to Google's home homeage here。 even though notice， I ended up some longer form of the URL。

 In fact， I'm going to delete everything else from the URL that's not relevant to us today。

 It's still forcibly coming back。 So Google is somehow trying to track me by putting that in there。

 That's fine。 All I'm going do is search for cats。 Now there's a whole bunch of other functionality that's clearly happening like autocomplete and it's trying to figure out what results or words I might want。

😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_67.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_68.png)

I'm gonna go ahead and hit enter。 And this is all to say that notice if I zoom in on the URL at the top of my screen。

 It's a crazy long URL because Google probably is doing a bunch of tracking and advertising and analytics technologically none of which is relevant to us today。

 But notice after WW W Google com there'slash search， which is the path on their server。

 the search program that someone there has written。 There's a question mark。

 And then there is an HttP parameter as these things are called the more precise name for key value payers in URLs。

 This is an HtP parameter。 It's value after the equal sign is， in fact， cats。 All this other stuff。

 I have no idea what it is。 I'm gonna just delete it and hit enter and it stays gone。

 but I still get cats in my search results。 So this。

 I would argue with sort of the canonically shortest form of a Google URL that's useful。 In fact。

 if I want to search for dogs instead。 I don't have to use the search box。

 I can literally manually make my own URL hit enter。

 And if I zoom out there are Google search results。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_70.png)

About dogs。 So this URL， too is sort of the essence then of how URLs work。

 and specifically the get verb， which was that keyword in all caps that I claimed was inside of the envelope。

 And it's what Phyllis's browser was sending。 and it's what my browser has been sending through all of these examples。

 But here's where things now can get interesting。 If I know how Google's server works。 Its backend。

 the part that knows all about cats and dogs on the Internet。

 I can implement my own front end by just knowing a bit of Hml。

 So let me actually go back into Vs code here。 Let me go into my second terminal， which is blank。

 and let me go ahead and create something called search do Html。

 I'm going go ahead and copy my original code， closed link and paste it here。

 hide my terminal Call this thing search。 and then inside of the body of this page。

 I'm gonna make my own version of Google here。 I'm going use a form tag。

 And I'm going to in that form， specify an input tag whose name is going to be exact。😊。

equalqu to what I saw Google uses Q， which happens to the stand for query。

 I am then going to add another one inputs the type of this button。 Actually。

 let's say the type of this box。 this input is gonna be text。

 The type of this next one is going to be a submit button。 And then that's it。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_72.png)

Let me go back into my other tab， go back into my directory listing， click on search html。

 and this is not pretty， but it is the beginning of my very own search engine。

 Unfortunately if I type in cats notice what happens my URL changes such that it search htl question mark Q equals cats。

 I know nothing about cats， I don't have a database of cats。

 I haven't done any backend work just the frontend the frontend is what the user sees the backend is what provides data to the frontend。

 but why don't I tell this form not to submit to me。

 but let's say that it's action should actually be go to go to Htps colon s www Google do com s search which is the URL that I saw in my browser I'm just inferring how Google works。

 I'm gonna to be pedantic even though this is the default。

 I'm gonna say the method I want my form to use is get confusingly it should be lowercase here even though inside of the envelope it will be all caps。

 and then I'm going go back to this page。 reload after going back。



![](img/4c54343641083e31267eb96a2dc6e4c4_74.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_75.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_76.png)

And you'll see the same exact box。 But when I search now for cats submit。

 notice my URL changes to Google's own。 It's like voila。

 like I just implemented my own Google without doing the actual hard part。

 I've actually just done the more simple front end。

 And there's a few other things I can do here that are sort of nice。

 I can change the type to be a search box。 I can change the value of my button not to be the default。

 which notice was submit。 I can say Google search。 And I can keep tweaking this to make it even prettier and prettier here now。

😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_78.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_79.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_80.png)

In my version is now a box that has cats。 Notice that it's trying to complete my thought。

 I can actually go back into the form。 I can say auto complete equals off to turn off that feature。

 So now if I click in this box and。

![](img/4c54343641083e31267eb96a2dc6e4c4_82.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_83.png)

嗯嗯。Autcompte equal goes off。

![](img/4c54343641083e31267eb96a2dc6e4c4_85.png)

Why is it still there。Did I forget to refresh？Oh thank you。 I forgot to refresh。 Hence my point。

 So you always have to reload after making a change。 And now the autocomplete feature is off。

 and this other little thing， it's subtle。 but this little X that will just clear the whole thing。

 that is simply the result of having changed text to search for the type of that box。

 There's other things you can do too for accessibility or user friendlines。 I can do auto focus here。

 for instance， without any attribute or without any value。

 if I now reload this page notice that the cursor is automatically blinking in the text box。

 which is a marginal change， but much easier for me to now type cats without having to stupidly click in the box in order to actually foreground it so I can type input。

 So suffice it to say this is not really the business that Google is in。

 they do much more on the backend than they do on the front end。

 but with just these basic building blocks， can I implement the beginnings of the same website。

 In fact， let me do one other flourish， you'll see that text box is blank。

 not clear what I might want to do。 Well there's another attribute I can use placeholder equals something like query。

 I can at least tell you。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_87.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_88.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_89.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_90.png)

or what to search for if I reload again now I see in gray text query instructions so that I roughly know what now to type so all of these things that you see every day on websites are really as easy as just coding up some HTML like that but what else can we do with HTML Well it turns out this is a topic for another longer day too there exists in computing what are called regular expressions which is a fancy way of describing patterns which are quite useful when you want to validate input for instance。

 if you want the user to have to type in an email address with the at sign with the TLD and so forth it would be nice to make sure that they get a warning if they try to skip that field or they mistype something in it as well with the world of regular expressions in short as redxs you have a whole bunch of documentation here that in a nutshell we introduce you to some pretty powerful syntax that we won't spend much time on it all today but it's syntax that exists not only in the world of the web but in Python in so many other languages as well so consider this just a quick crash course。

If you want to define a pattern and say a website that ensures that the user types in a email address。

 you can use these textual building blocks whereby in the world of regular expressions。

 a single dot represents any character if you don't care what the character is dot confusingly doesn't represent a period it represents any character star represents zero or more times plus means one or more times question mark means zero or one times if you want something to be there or not curly braces with a number means this many times n and you can even have a range of values instead and then you can use square brackets in some other syntax to say I want the user to type in any of these characters or digits in this case or you can do ranges like this。

 I want them to type in any decimal digits between zero and9 or backslash D represents any digit backslash capital D means anything that's not a digit long storyory short humans over the years have come up with shorthand notation known as regular expressions via which you can define patterns this is useful because if I want。

To make a web page that does， in fact， require that someone type in， say an email address。

 I can enforce that to some extent。 If I go back to my browser here and into VS code。

 let me go ahead and create a new file called say register dot H Tl to be representative of registering for some website。

 I'll change the title here real quick。 I'm going keep the form。 But in this case。

 I'm not gonna bother with Google anymore。 So let's make it a bit simpler than before。

 And let's go ahead and do this inside of the form。 I'm going have an input。

 I'm going have the name of this input be email because that's what I'm collecting。

 I'm gonna have a placeholder be quote unquote email so the user know what's to type in。

 And I'm going go ahead here and have something like how about。



![](img/4c54343641083e31267eb96a2dc6e4c4_92.png)

This。A pattern as well。 So actually， let's say let's say type equals text。

 but I'm gonna specify additionally a pattern。 So the pattern。

 I want the user to type in in between these quotes is gonna to be any character one or more times。

 that is to say their username then in that sign。 then any character one or more times。

 then literally a period and we didn't see this on the screen。

 but just like in see when you want to escape special characters。

 if you want literally a period in their input as the like the dot in Harvard doedduu。

 you can say backlash period to mean a literal period and then the word or Tu。

 So I think now what this means。 and let me go ahead give myself a button and just so you've seen it there's also a button element in Htl。

 which is similar in spirit to the submit button we saw a moment ago。

 Let me go back to my directory elisting， go into register do Htl。

 and let me go ahead and just type in like mailin as my name register。



![](img/4c54343641083e31267eb96a2dc6e4c4_94.png)

You'll see， please match the requested format so I have not satisfied it properly until I actually type in something like mailin atharvedduu and now it's happy。

 alternatively it's a little tedious to actually type in these patterns so there are some shorthands for them I can actually get rid of this pattern and if I read the documentation for Hl there is actually an input of type email which just does all of that pattern matching for you but the scary thing is that it's actually pretty involved to validate email addresses。

 I did a very simplified version of username at domain do tlD this is the regular expression that some browsers use to validate email addresses because even though mine is relatively simple mailin@harvardedduu turns out there's a crazy amount of syntax that is valid in email addresses and this is where regular expressions get scary but for our purposes today they're a thing that exists you might find them useful in HTMLl you might find them useful in Python they're incredibly useful when it comes to extracting information from web pages。

 if you're analyticallymined， you like the world of data science。



![](img/4c54343641083e31267eb96a2dc6e4c4_96.png)

You'd like to gather and analyze data， you can use regular expressions， not just to validate data。

 but to patterns of data in actual websites or documents and extract that data so as to perform operations or analysis on them。

 so wonderfully useful， if complicated tool。😡，The catch。

 though is this noticeice that here I'm still required to type in a valid email address， register。

 and I'm getting even more explicit information this time because I use the type equals email。

 the catch though with web pages is that they're not to be trusted。

 Insof far as this Hl came from the server and is downloaded onto the users's Mac or PC or phone where they have a copy thereof I can open up developer tools as I did before。

 by right clicking or control clicking and choosing inspect or whatever the menu option might be。

 I can go into the elements of this page， literally the Hm。 And if I don't want to type in email。

 I want to just type in any old text and see if I can break your site， I can just change it。

 And now there is no such warning， which is to say even though you will encounter not just today。

 but over the coming weeks as you play with HL。 certain features。

 they are not to be trusted in general when it comes to security And just like our discussion in the world of SQL and SQL injection attacks。

 this is one of the attack vectors。

![](img/4c54343641083e31267eb96a2dc6e4c4_98.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_99.png)

Two people are working on a website， one person is implementing the database stuff。

 one person' is implementing the HTML and the database persons like， oh。

 I don't need to worry about escaping characters because we're doing're using the pattern attribute in the HTML。

 bad idea because it's this easy to hackle website disable features that have been written for the site by just literally deleting them in your own copy。

 So we'll see next week how we can defend against this on the server side。

 but the point now is just not to trust the user's input at all。Al right。

 how can we be sure our H Tl is right。 Well， there's a bunch of ways。

 But one tool that's worth knowing about is this one here at validator do w3 dot org is a website by the group that essentially standardize is this and other languages。

 if I click on there， validate by direct input tab。

 And I quickly go back into VS code and let me grab the simplest of my examples。 Hello do Hl。

 I can just copy paste that into their website。 click check and they have written code to validate that the Hl I have written is。

 in fact correct。 Anything I've opened that needs to be closed has been closed。

 I don't have any stupid typos or missing brackets or quote marks。

 This is a wonderfully useful tool just to validate that your code is syntactically correct。

 even though it might still look like a mess visually on the screen。

 This will at least check for you。 The underlying HM L。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_101.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_102.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_103.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_104.png)

Allright， so up until now， everything I've done has been pretty boring。 It's black and white。

 The pages are fairly simplistic。 turns out we can take things the final mile using another language altogether。

 namely something called Css， which is the second of our three languages today。 This too。

 not a programming language。 although curiously， they keep adding more and more features that are making more and more like a programming language。

 but more on that another time。 This stands for cascading style sheets。

 and whereas HTML is all about the skeleton of a website， the structure thereof。

 Css is like the skin， the aesthetics thereof， the final mile that actually allows you to control the positioning of things more precisely the colors。

 the font size is all of the aesthetics， it lets you do the finer touches on the website。

 And with CsS， we have slightly different syntax， but frankly。

 it just boils down to even more key value pairs。 And as with Hl will'll give you a taste of the basic structure and principles underlying CSsS。

 there are so many key value pairs that are possible that。😊，We certainly won't do them justice today。

 but it's the kind of thing where you ultimately look it up in a reference， a book。

 a website or the like to pick up even more than these techniques。 Well， let's do this。

 Let me propose that in a moment， we're gonna see what are called properties。

 This is CS is jargon for key value pairs。 Why do we have yet in another words because different group of humans in a different room came up with this language versus the other people。

 But it's just key value pairs known as now as properties instead of as attributes in H itself。

 There's gonna be different ways we can define properties。

 and this is kind of a laundry list of some of them and we'll see them in context。 But in short。

 CS is just going to allow us to slap a whole bunch of key value pairs on our Hl elements to make them hopefully look prettier or be more precisely controlled aesthetically。

 So in my Hml thus far， we've generally had something that looks like this。

 turns out if I want to start using some CS。 I can introduce。

 as we'll see a so-called style tag in the head of my page and inside of that style tag I can put these socalled key value pairs。

 or as we'll soon see too。W to factor them out and put them into a separate file。

 I can actually use a link tag， which confusingly has nothing to do with hyperlinks or clickable text。

 but just links in another file in this case， Sts do css。

 The relationship of which shall be that of style sheet。

 is the sort of copy paste stuff that you do where the only thing you really care about is the developer is the name of the file in which you're putting your styles。

 Allright， let's do this。 let me go back over to BS code。 close out register html。

 open up a new file this time called home do html。 and let me purport to make a simple homep page for someone like John Harvard。

 I'll copy paste myboerplate。 I'll change the title here just to be let's say home。

 And then inside of the body of this page， let's do the simplest web page possible for someone called John Harvard。

 I'm gonna say here's a paragraph of text。 when John Harvard is going to be the person's name。

 Here's another paragraph of text。 We to my home page will be in the middle of this page。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_106.png)

And a final paragraph of text inside of which is like copyright C about John Harvard down here。

 So it's a basic website。 It's just three paragraphs。 It's not gonna be pretty。

 but let's make sure I haven't done anything wrong。 Let me close my developer tools。 Click back。

 Click home。 and there we have it。 The simplest of pages for John Harvard。 We to my homep page。

 copyrightpy John Harvard。 Let's at least start to exercise some control over this。

 Let's change the font size and the alignment of the text。 So back in V S code。

 Let's go ahead and add for now， actually， not even a style tag， but a style attribute。

 I'm gonna go ahead here and type in style， equals quote unquote， font dash size large。

 And then text， dash align colon center， semicolon。 And I apologize， but semicolons are back in CS。

 Then in my next paragraphs， Open tag。 Let's do something similar but different font size。

 colon medium for medium text， text align， Col center。



![](img/4c54343641083e31267eb96a2dc6e4c4_108.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_109.png)

Semicolon。 and then lastly down here， let's do style equals， quote unquote， font size。

 colon small because it's the footer。 So who cares text aligned colon center。

 semicolon strictly speaking at the last key value pair。 otherwise known as a property。

 You don't need the semicolonons， but just for consistency。 I'll keep them for that。 Allright。

 let's go back to this page。 reload and watch all of the text a moment ago was left aligned and the same size。

 now， it's a little subtle， but it's clearly centered but it's large， medium and small， respectively。

 even if you've never seen CS before， what rubs you wrong about this design， though。



![](img/4c54343641083e31267eb96a2dc6e4c4_111.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_112.png)

Based on all weeks past。Yeah。Yeah， for every line I've been repeating myself with text the align Center。

 text align Center， textal line Center。 And if we really want to nitpic。

 these aren't really paragraphs， there's like no phrases or full sentences， let alone paragraphs。

 So it turns out there's a whole bunch of tags we can use to lay out a page。 And in fact。

 I'm going transition to one that's a little more generic than paragraphs， namely div。

 which is just gonna create a division in the page for me。

 And this doesn't have any functional impact。 but semantically。

 it's a little nicer because it means I've got the division here for the header。

 the division here for the main part in the division down here for the foot。

 It's just a different way of thinking about it。 Its just different rectangular swaths of the page。

 But I like your point that text line center is kind of stupidly duplicated all of these times。

 Let me actually go ahead and first reload this change because there is one side effect that we might want to get back when I reload now using divs instead of paragraphs。

 there goes the nice white space in between my text。 divs just give me rectangle after rectangle。

 and as an aside。 Let me control click or right click open up developer。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_114.png)

Yet again， and notice this other trick with your elements tab。

 whatever you hover over at the bottom of your screen will be color coded at the top of the screen。

 So if I dive into the body by clicking this little triangle。

 let me zoom in at bottom left I can now see my own Hl much more pretty printed and colorful down here。

 if I click on this one or hover over it， you'll see that the first div。

 the rectangular region is highlighted。 Now the second now the third that's all we mean by divisions of the page。

 This allows me to see my copy of it in the browser as opposed to in the original file。

 So just another technique for developer tools。 All right， but I don't like this duplication。

 but here is now the C in CSs cascading style sheets means that if you want one property or key value pair to sort of cascade down on all of the other tags inside of that one。

 you can do that。 for instance， in the body tag I can add my own style attribute here and put all of that text aligned center there。

 why because div div div。

![](img/4c54343641083e31267eb96a2dc6e4c4_116.png)

The three children of the body tag to borrow a vernacular from family trees and from trees more generally。

 so this too should work because textexalline Center should cascade down now on all three of those children and indeed if I reload the page。

 nothing visually changes but it's arguably now better designed。😡。



![](img/4c54343641083e31267eb96a2dc6e4c4_118.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_119.png)

All right， what more could we do here？ Well， how about this。

 It would be nice to make clear to servers out there like search engines like what's going on in the page semantically。

 And the term of art out there nowadays is the semantic web。

 which essentially is about putting more hints in your Htl so that servers like search engines kind of know more so what they're looking at。

 this is pretty generic right now， div div div。 But presumably the top of the page is among the most important things because that's effectively like the header of the page。

 then the middle div is kind of the second most important because it's like the main part of the page and the footer is like the least important。

 So it turns out there are other tags in H， besides paragraphs and div。

 there are literally tags like header， which allows me to define the header of the page。 main。

 which allows me to define the main part of the page， and then even footer。

 which allows me to define that too。 So now if Google and Bing and other search engines are sort crawling my website once it's public。

 they know that John Har's important because it's in the header welcome to my homep page is important because it's in。

😊，they're probably not going to care as much about the copyright because it's in the footer。

 so it's just providing more hints to these kinds of services。 Moreover。

 we can do some other things here。 This is kind of a hackish way to implement a copyright symbol。

 HTML also has what are called entities where if I can do this magical incantation here。

 Ampersan hash symbol 1，6，9 semicolon notice that VS code recognizes this as an HTML entity。

 if I go back to this page and notice my first approach was just parenthesis C parenthesis。

 if I reload now having used that HTML entity， which I only know by having looked it up now I get the copyright symbol that actually comes in the font that's being used here。



![](img/4c54343641083e31267eb96a2dc6e4c4_121.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_122.png)

Al right， so let's transition now to this approach whereby I claimed before that you can actually use a style tag。

 And why might we want to do this， Well， looking back at my code here。

 this is sort of hinting it potentially bad design。

 even though there are different arguments for and against this right now。

 I'm sort of commmingling my data with my presentation thereof like John Harvard。

 welcome to my homepage and copyright such and such is sort of the data I care about but I'm sort of mixing in the stylization of all this stuff by putting CS and Hl in the same place。

 So to be clear， all of the green stuff and well。Everything we've seen thus far。

 The tags and the attributes。 That's all Hml syntax。 Everything between the quotes is now CS。

 And this is the first we've seen this before only in the sense that we've used SQL inside of Python code here。

 we're using CS inside of Hl code。 But the CS syntax is everything thus far inside of those quote marks。

 Wouldn't it be nice to kind of factor that out so that I can see it all in one place and better still factor it out ultimately to another file。

 And I can do this as follows。 Let me in my home dot Hl get rid of all of these style attributes and really go wow the page down to its essence whereby I just have the header main and footer tags inside of which is that content。

 It's already easier to read at least for me the human inside of my head tag now， though。

 let me go up and say style and inside of this new style tag。

 Let me show you another approach for stylizing the page up here is where we can actually select elements to operate on using what are called。

😊，Selectors。 so if I want to modify the style of my page's body， I can do that by typing body。

 and then I'm afraid curly braces are back in CSS2。 I can put text aligned center up here。

 And the fact that I've put the word body before those curly braces just means all of these key value pairs。

 One in this case will operate on the body。 Meanwhile， down here。

 I can say the header is going to have font size colon large。

 the main part of the page is going to have font size， colon medium， and then lastly。

 the footer of the page is going to have font size colon small。 definitely more lines now。

 which isn't the best。 But the effect now， if I go back to my browser and reload visually is pretty much the same。

 I've just relocated all of those key value pairs elsewhere。

 But as a stepping stone now for doing something a little smarter。

 whereby I now can lay the foundation for putting this in another file altogether。 But first。

 let me note this too。 the fact that I've put all。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_124.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_125.png)

Of these key value pairs associated with specific H TM L tags doesn't really make them very usable or rather reusable。

 And so when I alluded to earlier， that these properties can be applied to different selections of H Tl type selectors。

 class selectors， I D selector， attribute selector。 Let's just give you a little taste of this。

 What do we mean， Well， suppose that I want to generically be able to use。

Text align center without associ it only with the body。

 Maybe I want to use this for a larger project where I want to center many things on the page。

 I can define my own keyword like the word centered。

 which doesn't exist per se But if I prefix it with a dot。

 what I've just created is what's called a CS class。 and a class is just a set of key value pairs。

 Pro that you can associate with any Hl tags。 Meanwhile。

 if I want this key value pair to be associated with the notion of large。 I can define dot large。

 I can define dot medium， and I can define dot small down here。

 the motivation for which is that now in my page if I want to center the body let me fix my own typo。

 if I want to center the body， I can say please use the class known as centered on this tag。

 and then on the header， I can say please use the class known as large on this tag。

 And then please use the class called medium here。 And then lastly。😊。

The class called small here so now in the spirit of a lot of the modularization we did in scratch and see in Python of making your own functions。

 classes aren't functions， but they are a way to encapsulate one or more properties and use or reuse them anywhere you want in a web page's not over it's not that impressive here in this short one but it lays the foundation for doing much more interesting thing soon down the road。

 In fact， let's take a step in that same direction。

 Let me go ahead and now highlight everything I've put inside of this style tag。😊。

And cut it onto my clipboard。 I'm gonna get rid of the style tag altogether。

 I'm gonna create quickly a new file， comb do css。 And I'm just gonna paste all of that stuff in there。

 and just to be nitpicky。 I'm gonna deindent it。 So it's all left aligned。

 So all I've done is just move everything I just wrote into a new file called home do CsS。

 I'll close that out of sight out of mind。 But when I'm gonna do now in the head instead of a style tag。

 which contains all of that clutter， I'm gonna say link aref equals home do css。

 And then this rel tag， which just means the relationship of this file to this one shall be that of a style sheet。

 And this tag2 does not need to be closed。 It just is。

 And now if I go back here and reload still no changes other than tweak the font a moment ago。

 Still no changes。 But now it's better design with that file completely separate。

 So where are we going with this。 Well， just to kind of circle back to something we did earlier。

 Let me open up my terminal window and recall earlier。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_127.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_128.png)

We had this file like favorites0 do Html and this contained all of the data from a couple of weeks back that we solicited by that Google form and recall a bit ago when we went into favorite0hl I mean it was just kind of an ugly table structure but it turns out in the world of in the world of HTML and CSS there are also what we're gonna to call frameworks which is a fancy word for library but a framework is sort of a way of doing something by using someone else's library and to do it there way you just read their documentation and then you adopt their functions in the case of code or you adopt their CSS classes in the case of this example so one of the most popular frameworks out there nowadays and among the simplest and best documented is one called bootstrap which is a set of CSS classes and other features that you can use because it's open source in your own code in fact all of the documentation is that this URL here I read the documentation before class and I copied really the one line of code that I need to make。

Favors do Htl， even prettier。 So let me go back into VS code。

 and let me copy my premade example from earlier。 And you'll see that in favorite favorites1 do Html。

 I have all of the same code。 all of those lines of everyone's submissions。

 But notice I've added now this link tag。 And it's a little longer than the 1 I wrote。

 it's referencing a thirdparty website Js deliver， which is a CdN content delivery network。

 which is to say a server that just serves up content for other people to use。

 But I copied that from bootstrapps on documentation。 And what I did here is the following。

 I added a class to my table tag specifically with a value of table and followed by a space table striped。

 I read bootstraps documentation at that previous URL。 And I liked the look of their tables。

 because it lays it out with nice stripes like white and gray and white and gray and it sort of formats everything quite a bit nicer。

 So if I go into this version in my second tab by going back first。 And now。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_130.png)

pening up favorites1。ht， same exact data。Two lines of change。 Andvoila， now we're talking。

 This looks much more like a table that you would see on any pretty website。

 like your Gmail inbox or the like， all by simply changing the CS and not really the HTML at all。

 So the motivation for introducing those classes a moment ago was so that we can have reusability of code and better still。

 we can start to stand on the shoulders of others by using code that other people have written in order to improve the aesthetics of our own websites。

😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_132.png)

As well。Al right， How about a couple final flourishes with some style。

 Let me close out these examples here and let me propose to go into how about that same link example from earlier。

 So let me reopen do html， which recall had this phishing attack at the time。

 I'm gonna revert this to the safe version and just say visit Harvard at Harvard's actual URL。

 supposeuppose I wanted to stylize this link beyond the default。 Well。

 let's see what it looks like by default， if I go back into link do htl。

 This is what it looked like before， blue and underlined by default per the browsers decision But I can override that and any number of ways to keep things simple。

 I'm just gonna stay in my same file now， rather than be pedantic about moving it to another file。

 And if I want to stylize the anchor tag just as before。

 I can say a and then in some curly braces here， I can do something like this color colon red。

 if I want to make it crimson like instead， let me go back to V S code my other tab click reload and now we have a red tab。

 I can really geek out。 And if you remember your hexet。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_134.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_135.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_136.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_137.png)

Eimal codes from our discussion of images a few weeks back， I can do hash F F 0，0，0，0。

 which is a lot of red， no green， no blue。 And if I go back to my other tab， click reload。

 same exact thing。 You have that much control over even the color codes that you might use。

 Maybe you don't like the underlining in this particular case。 Well， that's fine。

 I can do something like text decoration。 None。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_139.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_140.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_141.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_142.png)

Per the documentation。 I can reload and gone is that underline。

 Maybe it'd be nice to hover over the word and then see the underline。 Well， I can do that too。

 turns out I can have these pseudoseors whereby I say the name of the tag， then a keyword like hover。

 which browsers know to recognize。 And when I hover over in anchor。

 what I want to do is change the text decoration to underline temporarily if I go back to this tab now。

 reload looks the same。 but as I move my cursor over。

 notice that it's underlining it for a visual effect。

 Let's see what's going on with my developer tools。 If I right click anywhere and choose inspect。

 notice a detail I haven't showed us before is not is under the elements tab here。

 notice if I go down to my link here and let me just make the righthand pane here a bit bigger。

 all this time， but ignore it up until now has been this part of the developer tools。

 whereby I can actually see all of the CS that applies to the element I have just selected。

 namely this link。 And I see here in nice pretty printed fashion that I'm using this color。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_144.png)

F00，00 text decoration none， Why is this useful well1。

 if you want to learn from another website how it's doing its thing， you can just look at the CSS。

 but also if you want to be able to iterate more quickly and just kind of tinker with things。

 I can actually turn the color on and off by just hovering over the inspector here and just turn it on and off by clicking or not clicking。

 let me get rid of that message there。😡，Clicking and unclicking。

 And if I want to just play around with maybe maybe Harvard should be 0，0， F F 0，0 enter。

 I can make a green instead。 so you can temporarily change the browser's copy of your own H Tl or C S。

 just to tinker and iterate quickly， just like I tinker with Stanford's own website。

 or at least my own copy thereof。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_146.png)

Lastly， how about in terms of these selectors， these are using type selectors that is selecting the name of the tag。

 If I want to actually affect one tag specifically， a very common convention is to give an H element。

 a unique Id。 for instance， I'm gonna to call this Harvard and by honor system。

 I should not give any other element in this page an Id of Harvard。

 The motivation is that I can now uniquely identify this tag by， for instance。

 changing this to hash Harvard， which is just the convention for specifying that it's not a class now。

 it's instead an Id， you do not put the hash though in the actual value down here。

 and what I can even do down here is something like hash Harvard to scope that as well。

 if I now reload。 We're back to the red version and the same functionalities before。

 and it's just a more precise way now to target your CS properties to a very specific。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_148.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_149.png)

Element instead。Okay， that was a lot。 Any questions on any of this。Thus far。No， that clear。

 All right Well， one last language for the day。 And。

 and we do mean what we say like that is the extent to which you will learn formally H and Css。

 like everything else just follows those exact same patterns， It's different classes。

 It's different attributes。 It' different tag names。

 all of which can be picked up through practice through osmosis through references。

 but that's really it for the fundamentals。 And so our last focus today is on an actual programming language that will just scratch the surface of if only because it's so darn omnipresent nowadays。

 most every website you use is made from not only HTML and Css。

 but if it's in any way interactive odds are it's using jascript。

 a programming language that is very commonly used client side whereby humans write the code on the server。

 but then your browser as before downloads it to the client and it then runs in your own Mac。

 your PC or your phone that said jascript is also very popular on the server nowadays。

 it's not just a browserbased language in jascript。

 what you have most powerfully though is the ability in。MemoryTo mutate this tree in real time。

 In other words， think about even your Gmail inbox or your outlook inbox。

 typicallyyp you see email after email after email after email odds are per today。

 What HTML tag is creating that UI of row after row after row。😡，Which tag？What。Table tag。

Like the table tag probably write table row， table row， table row， But it wouldn't make， well。

 actually， this is the way things used to work in my day back in the day when you visited not even Gmail before it existed。

 but your email inbox， you would download from the server。

 a web page containing a table tag with table rows and table data elements。 And that was your inbox。

 if you wanted to see if you got new mail， you just reload the whole page and it would download new contents from the server and show you the new H with jascript though。

 which just come onto the scene over the past 20 plus years。

 you have the ability to download the data once initially。

 then use code to just grab some more data every 30 seconds or some more data pretty much any time in email arrives。

 And if this picture here represents not our super simple hello title hello body page。

 but a whole bunch of table rows for your existing email。 The moment you get more email。

 you can use jascript code to add another node to this tree。

 another node to this tree represents the table row tag the table row tag again and again。

 So in short， with jascript， you。😊，HaveThe ability to change the tree。

 otherwise known as the document object model or dom for short dynamically in order to evolve the web page。

 So let's take a quick tour of what jascript does have syntactically。

 And then I'll just demonstrate some of the capabilities thereof without dwelling today on syntax beyond this。

 So in scratch， which is looking pretty good now， you have conditionals which look like this in jascript。

 it's pretty much the same as C the curly braces are back at least two or more lines。

 but indentation doesn't matter except for the style thereof in contrast with Python。

 If you have an if else， it's going look the exact same in C if you have if else if else you have the exact same thing in C different from python because this if in Python now we're back more verly to else if as in C variables in jascript。

 Well here in scratch is how you set a variable to0 in jascript， there's a few ways to do this。

 but the most reasonable for now is to let counter equals 0。 so you don't。Spify the type。

 This is more of a polite way of asking the browser。

 Please let a variable called counterexist and set it equal to0 by default。 semicollonons are back。

 However， that's not strictly true。 browsers are smart enough to know where semicollonons actually matter。

 but for our purposes， assume that they're always there。

 How do you change counter by one Well you can do it the pedantic way， which is a little vervose。

 you can do the plus equals trick or nicely back in play is the plus plus in jascript just like in C。

 but not in Python loops in ja。 Well and scratch， if you want to do these three times。

 here's how you would do it in jascript， it's pretty much the same as C。

 except for not mentioning the data type， instead you use the keyword let here。

 but otherwise this is exactly the same as in C if you want to do something forever for whatever reason in ja。

 you can say while true， which is exactly how we did it in C。

 if you have a web page like this meanwhile， and you want to insert some ja to it。

 you can do it in a few different ways。 you can。A script tag just like the style tag in the head of the web page this can get you into trouble though。

 for reasons you might encounter whereby if you put your jascript code up here and you try to use it to modify the web page。

 but the web page isn't defined until down here you can get into some race condition really where the data does not yet exist So instead of putting it there or even in another file it's actually pretty common too to avoid that all together by putting your script code or your script tag at the end of the page just before the end of the body to ensure that all of the web page exists already this is similar in spirit to the de issues we saw in Python or the prototype issues we saw in C there's bunches of solutions though to this here problem But let's now take some jascript for an actual spin and use vS code to write some of it as follows in VS code let me go ahead and close link Htl open up my terminal temporarily and let's improve my actually let's just improve the very file hello。

That I have here in front of me and actually have it be more interactive and give me sort of a popup on the screen when I type in my name。

 So let's start as follows。 First， let's go ahead and change this just to hello just for short。

 and in the body of this page， let's give myself a form。 And in this form。

 let's give myself an input。 will turn off autocomplete just to avoid distractions。

 will turn on autofo to save me a click。 I'm gonna give this Hml element and Id uniquely of name a placeholder also of name just so the human knows what to do。

 and the type of this field shall be text。 In other words。

 I want to create a program week1 in week 0 where I type in my name and see hello such and such。

 I'm gonna give myself an input a submit button with input type equal submit。

 don't really care what the button says， but I do care now when I go back to my other tab close my developer tools。

 go back into hello do H， I now have something looks like this。

 it looks similar to our search example for cat。 but now I'm asking the user for their name。



![](img/4c54343641083e31267eb96a2dc6e4c4_151.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_152.png)

Along with the submit button， but what I want to have happen is when I type in David and click submitm。

 I want to see hello David somewhere on the screen Well how can I do this Well few different ways。

 but JavaScript allows me to do things like this and for upcoming problem sets you won't necessarily have to write JavaScript like this so consider this a whirlwind tour not so much something to ingrain。

😡。

![](img/4c54343641083e31267eb96a2dc6e4c4_154.png)

Here I can add a new attribute to the form tag called on submitubmit， which as the name suggests。

 means call the following function when this form is submitted。 Well。

 what function do I want to call， I'm going to call it a greet function， and that's it for now。

 how do I define a greet function。 Well， I could among other places put this inside of the head of my page in a script tag I can define a function in jascript。

 I literally saying function。 and then the name of the function and then in parentheses。

 any arguments there too。 I'm not gonna to have any。 And then in curly braces。

 I can actually define the meat of that function。 And for instance。

 I can do this let name equal the following document query selector And now what I want to do is this document is a global variable that just comes with ja in the browser that allows me to write code involving the whole document。

 the web page itself。 Que selector is a fancy name for a function。

 that lets me select specific elements of the page using CS selector。😊。

Very same syntax we saw with names and with dots and with hash symbols a moment ago are back in play for jascript here。

 So if I want to create a variable that stores the name that the human typed in what I can do is pass to query selector a selector for that element which is quote unquote hash name or hash just means ID But the reason I'm using name is because the unique identifier I put here is name if I change this to fo nonsically that's fine I just have to change this to foo appear here。

 So I'm in full control over what is called what but if I want to get the value that the user typed into that box。

 I now do value and if we've seen these dots before and see they were for accessingstructs in Python they were for accessing contents of objects So this just means use the document global variable use the query selector function or method inside of it get the element whose unique I is name and then go inside of that text box and give me its value So it's a very long-wined way of saying store the user's input in a variable called name but what's。

Now， even though this is going to be a bit ugly is I can then use a built in JavaScript function called alert。

 and I can say something like hello， comma， close quote， then plus。

 which we've seen before in Python and can patentate with it， that names value。Now。

 this isn't quite complete And for reasons I'm gonna wave my hand at。

 I also need to add annoyingly returned false down here because otherwise， if I click submit， yes。

 the greet function will get called， but the browser will still try to submit the form to a server。

 which is gonna interrupt my own code。 So long story short。

 this is a bit of a hackish approach for now So just making sure that the only thing that happens when I submit this form。

 is that my function is called。 Now， if that innstruew anything up。

 I should now see after reloading this page， a prompt for my name。 I'll type it in。

 And when I click submit， I should see an ugly but functional alert box pop up with dynamically generated text namely hello comma David。

 I say it's ugly because by convention Chrome shows you the full URL or the domain name of the website in question。

 which is my randomly generated one， which does look stupid。 So we can do better than this。

 But the point is now that I have written code in jascript to listen for the submission of this form。

 And when that happens， call that their function。 And this is generally the paradigm。



![](img/4c54343641083e31267eb96a2dc6e4c4_156.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_157.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_158.png)

Of jascript there exists in the context of websites。

 a whole bunch of events that can happen And this is a word we haven't used since week 0 in scratch。

 recall that in Scra， you have events like when green flag clicked and when the green flag is clicked。

 you can do something in response。 same thing in the world of web programming here are just some of the events that can happen in a web page like the user can change something click on something drag something key put the keyboard up。

 put the mouse down or other things What I'm listening for is the submission of a form which is cool because in jascript then you can essentially write code that listens for any number of these events and then does something when it happens。

 consider after all in Gmail， if you click the little refresh icon within Gmail itself to get new mail it runs some jascript code。

 it turns out to talk to Google's servers， get more email and update your site。

 if you click and drag on Google maps to see like higher up geographicalally what's happening。

 some ja code is listening for your mouse going down and dragging so as to go fetch more tiles。

 more rectangular pictures of the map。😊，Wherever you're trying to drag。

 So anything that's interactive in websites nowadays like that is using jascript by just listening for things that you or someone else might actually do。

 Well， let me go ahead and start opening some premade examples。

 just to give you a sense of the other syntax that is in use today with ja。

 I'm gonna go ahead and open up a version of this hello program called hello to do H。

 which is different in that， I'm practicing what I preached earlier by putting the script tag at the bottom of the page just to ensure that the form and everything inside of it already exists for sure by the time this code executes。

 Moreover， what I'm getting out of is the business of using the on submitit attribute。

 So just as I tried to get my cS out of my H and put it elsewhere Similarlyly。

 I'm trying to get my jascript code like the greet function out of the H and putting it down here Now why is this useful。

 This is a big mouthful， but it just follows a general pattern as follows document query selector quote unquote。

For is just getting a reference to the actual form element in the page。

 So if you imagineagin in your mind's eye that this is drawn out as a tree in the computer's memory。

 this is just getting me a pointer to the form node in that tree。 haven't seen this before。

 but it kind of does what it says add event listener is a function or method that you can call on any element that just tells it to listen subsequently for this event and when that event is heard。

 submit in this case， call the following anonymous function otherwise known as a lambmbda function。

 but long story short， this syntax just means when submit happens on that element。

 execute the code between these curly braces。 What happens alert hello quote unqu document query selector name value。

 I didn't bother with the variable this time。 this does exactly the same thing。

 but is a purely jascript solution without using the unsubmit attribute。

 And we show you this only because especially for final projects。

 you might want to do something like add event listener to make like maybe a dropdown menu or some interactive clickable thing in your website。

Just listens for one of these events to happen before actually executing some code。

 Notice I've been conventionally using single quotes in javascript because that's just a thing in the javascript community to generally prefer single quotes over double quotes why。

 Well， it means people in jascript are hitting the shift symbol like much less than the rest of the world to get double quotes。

 it's just a convention So long as you're consistent either is fine conditional not having actual apostropphhees and text and such let me show you one other convention。

 instead of putting my code at the bottom of my page just before the body ends。

 it is also alternatively conventional as in hello3 do Hml to do this。

 to still maybe put the script tag at the top of the page。

 But to additionally have this magical line whereby you add an event listener before you do anything else。

 that listens for this crazy， weirdly named event called Dom content loaded。

 But now that you've heard Dom briefly， Dom is document object model just means the tree and memory。

 This is just a fancy way of saying when。😊，Tree is loaded。 Go ahead and do the following。

 And this ensures that when a browser reads all of this code top to bottom left to right。

 This code won't actually be executed until the whole dom is loaded into the computer's memory。

 That whole tree is built。 So that's all that's being referred to there。

 The rest of the code is actually exactly the same。 What more can we do。 Well。

 just so you've seen it， I can delete all of that code， move it to a file called like hello dot Js。

 And in the fourth version of this example， I'm back to just H Tl。

 because I can put all of the fancy complexity inside of my script tag here。

 factoring that code out into hello 4 do Js。 But the code is otherwise， I claim unchanged。😊。

All right， this is a lot。 I know it's quick， but do the general principles make sense。

 like just listening for events and running some code in response。

 That's really all we're talking about， Allah， week 0。With scratch。Alright， well。

 let me let things escalate just a little bit。 And this time I'll open the demo first。

 let me go ahead and open up Hello 5 dot H T L， which I wrote in advance， which O。

 is definitely starting to look like a mouthful。 But in a moment， it'll make a bit more sense。

 Let me go ahead into my other tab here。

![](img/4c54343641083e31267eb96a2dc6e4c4_160.png)

Click back， go into source 8， which is all of my premate examples。 And I said we're in hello 5 now。

 And in hello 5， there's no submit button because watch this fancyness。

 When I search for something like C or David as a full fledged word there。

 Notice it's just happening inside of the web page。 Moreover， if you poke around。

 let me right click on the page， let me inspect to open my developer tools。

 Let me expand the body down here。 and actually， let me reload the page。 So notice by default。

 this is what my web page looks like。 It's just got an empty paragraph tag for some reason。

 But watch what happens at the bottom of the screen， and I'll zoom in a bit more。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_162.png)

When I start typing my name， like D。And then let me expand this triangle。 You see at beginning。

 A V I D， when I say that jascript can mutate the dom， the actual tree in memory。

 like that's what you're seeing。 you're seeing the HTMLml pretty parented color coded version of that tree in memory。

 and how is it working。 Well， if we go back to the code here， Well。

 let me wave my hands at this first line， this just means don't do this until the whole dom is loaded。

 let's look at this line， which means give me a variable called input and set that equal to Okay。

 the input tag on the page。 the text box。 and then do what。

 well take that input add an event listener， that's forever listening for key up like my finger going up off the keyboard。

 And when that happens call the following function， which has no name。

 But that just means call these lines inside of the curly braces。 Well， what happens。

 inside of those curly braces。 Well， here's a variable called name。

 And this is just pointing at the paragraph tag， apparently， I'm checking this question。

 if there's if input dot value。 So this is like saying if input dot value does not equal。

 quote unquote。Just implicitly， go ahead and set the inner HTML of that name。😡。

Variable equal to hello， quote unquote input dot value。 Now this is crazy syntax。

 And I'm showing it just because you'll see it in documentation online。

 This is similar in spirit to Python's F strings。 It's ugly syntax with dollar signs and curly braces and worse yet back ticks。

 However， this is a manifestation of really the jascript community。

 presumably deciding that if you want the language to evolve。

 you have to make sure you're backwards compatible with old versions of the language。

 So they chose characters in syntax that probably do not appear already in the wild。

 that's why sometimes things look uglier。 I would surmise than otherwise。 But long story short。

 this just means if there's input there， go ahead and say hello comma input。 Otherwise。

 it says by default。 hello， whoever you are。 And in fact， if I go back here and delete my name。

 Watch what happens， it goes back to that default。 So here's just an example of listening for keystrokes going up and down and making sure that the page responds accordingly。

 How about something else。 Let me go back into my directory list。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_164.png)

Let me open up background HTML， which I wrote in advance。 It's super simple。

 but this is the first of like an interactive website that has three buttons labeled R， G and B。

 as you might imagine， clicking on R does that。 G does this。 B does that。 Well。

 how is this working This is the first example now where you can use ja code to alter CSS dynamically So let me reload the page So it's back to white。

 Let me open developer tools。

![](img/4c54343641083e31267eb96a2dc6e4c4_166.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_167.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_168.png)

And watch what's happening now on the body tag specifically。 initiallynitially。

 there's no stylization on the body other than the browser's default margins and whatnot over here。

 But watch what happens at bottom right， when I click on the R button。 You see that all of a sudden。

 background color， Col and red was dynamically added。 Now it's green。 Now it's blue。

 And notice the Hl at bottom left is changing too。 So somehow I am listening for clicks。

 and then changing Cs in response。 So if I go back to V S code， let's close hello 5。

 let's open up source 8 version of background Html。 And in here， it's a bit of a mouthful。

 But the Hl is simple。 here's three buttons。 And because I wanted them to be uniquely identifiable。

 I gave them all ideas of red， green and blue， respectively。

 And then this code is a bit of copy paste。 And frankly。

 I could probably avoid that if I were more elegant， but just to be pedantic。

 Here's what's happening。 Here's a variable called body， that's just getting the body element。

 The node in the tree at that moment in time。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_170.png)

And then these three lines of code， their purpose in life is to handle the red clicks。

 how well we're telling the document to select the element whose idea is red。

 Listen for the click event。 And whenever that happens。

 do this body which is the same variables before。 dot style， which we haven't seen before。

 but any element can have a style property associated with it in jascript。

 background color equals unquote red and the other blocks of code or exact same thing for green and for blue。

 the whole point here is we're now listening for clicks on buttons and changing not the contents of the button。

 but rather the style thereof of the whole page。 As an aside， this is curiosity。

 This is what's known as Caml case。 whereby like a camel has a hump in the middle。

 this word has a hump in the middle， like capital C。

 all of a sudden to separate the two words in CS recall it was a moment ago。

 background dash color Anyone want I guess why this is not how you write it in ja。😊。

Anything with hyphens in CSS is changed to Caml case in JavaScript。It's not related to comments。

 simpler than that yet。😡，Yeah， right like left hand wasn't talking to right hand。

 And people were like， oh， damn it。 like this now means background minus color。

 which is not a thing because minus is indeed just like in CNN and Python， a mathematical operator。

 So the world decide to reconcile this problem by just capitalizing the character that would otherwise be where the hyphen is little C trivia。

 All right， What else can we do。 How about a couple of final examples here。

 So what more can we do with CS。 So back in my day， we had a tag called the Hl blink tag。

 which is among the few tags in the world of Hl that has actually been deprecated that is removed from language。

 like no one removes things from languages generally。

 But the blink tag was so hideous followed only by the marquee tag where by my own home page is like a freshman had welcome to my homep page。

 just moving across the screen like this from left to right for no good reason。

 like an ugly marquee and like a digital signage nowadays。 But we can bring it back as follows。

 So if I close out my developer tools go back into my sourceur a directory。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_172.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_173.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_174.png)

up blank。 This is what the blink tag used to do back in the day。 Now。

 this version is implemented instead in jascript code as follows。

 I have a function here called blink， which I'm apparently calling every once in a while how is that happening。

 Well， let's scroll down。 Here's my Hl， super simple， literally just as hello world。 But notice this。

 There's another global variable we haven't seen in jascript called window that refers to like the general window。

 not necessarily the content of the page where you can call a method called set interval。

 and you can tell that method set interval to call a specific function。 every number of milliseconds。

 So if I want to call blink every 500 milliseconds， that's the line of code that I use。

 if I scroll up to now this function， let's see how blink is implemented。

 both now and perhaps back in the day。 Well， body is a variable here。

 that's just pointing to the body node in the dom。 and this is a big mouthful。

 But if that body's styles visibility property in CS is quote unquote hidden。😊。

Change that body's style's visibility property to be visible Otherwise。

 change it to be hidden instead here too， don't understand why left hand and right hand weren't talking to one another。

 You would think that the opposite of visible would be invisible， But in CS。

 the opposite of visible is hidden。 Just have to memorize stupid things like that。

 But what's this really doing， It's just changing the CS from hidden to visible。

 hidden to visible every 500 milliseconds。 So， in fact。

 what you're seeing here in the blink is if I inspect this page2。

 And now notice it's kind of fun just to watch it， you can see the Htl at bottom left and the CS at bottom right just automatically changing because I'm doing that every 500 milliseconds。

 All right， how about one other well autocomple。 Well。

 we saw a step toward this with my hello comma David example a moment ago。

 super common though in Google and like every website now to automatically try to finish your thought。

 How is that happening。 Well， that's not just Htl and CS。

 that is also some jascript thrown into the mix。 So for instance。



![](img/4c54343641083e31267eb96a2dc6e4c4_176.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_177.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_178.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_179.png)

Let me go into my terminal and open up source8s example called autocomplete do Hl。

 And here I am going to borrow a file called large do js， which is just a massive version。

 I'll open that to if you're curious large do js is just a huge jascript array。

 a raisezor back containing all of the words from problem set5 the spell checking problem set where you had100000 plus words in in a file given to you now we've converted that to jascript by using global variable like this。

 in the code here， what's happening Well， apparently there's gonna to be a text box at the top of the page that we see。

 Then there's an empty unordered list So an empty bulleted list and then there's this code down here。

 I'm apparently creating a variable called input that's referencing that text box。

 I'm then listening for key up just as like we've done before。 And then I'm doing this。

 I'm setting a variable called Hl equal to quote unquote nothing。

 So an empty string and then I'm checking。Does the input text box have any value implicitly， If so。

 what am I doing， This is kind of cool。 It's a bit of Python and C together syntactically for each word in the words array。

 jascript uses the keyword of instead of in like Python。

 but so be it what I'm doing now is in jascript I'm saying if that current word and that big file of 100000 words starts with whatever the user typed in go ahead and add to that HTML string using plus equals。

 which is just concatenation， we've seen plus before。

 the following an li tag inside of which is that specific word And so in effect what you're seeing now is what almost every website nowadays does。

 they're not manually writing HTML like we've been doing much of today。

 they're writing code that dynamically generates HTML because the programmers understand what HTML is they understand that unordered list have li children and so using this string that I've highlighted。

 they're creating li element after li element for the purpose of。

Changing the inner H TM L of the UL element to be the value of that variable。

 And this is a very long way of saying how is autocomplete implemented in general。 Well。

 just like this， if I search for cats by typing in C。

 There is every word in that 10000 dictionary that starts with C A T S and there is every word that starts with C A T S。

 Meanwhile， watch what happens underneath the hood。

 if I open up my inspect tab again and I go to my body inside of this is the empty U。

 But watch as soon as I start typing something like C。 Now I can expand the triangle。

 because there is an L element that's been created for every one of the words that match as I do A T S now I've got just four of them and there is cats。

 There is Cat skill and so forth。 So anytime you go to Google do com like we did earlier。

 we went to Google do com and started searching for CAT T S。

 where all those search results coming from。 someone wrote。😊。



![](img/4c54343641083e31267eb96a2dc6e4c4_181.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_182.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_183.png)

Javascript that's listening for keyup or the like and then dynamically populating an unordered list or in this case。

 a much prettier list of the matching results。 And the final example that we thought we'd leave you with。

 And again， the whole purpose of introducing jascript to give you a taste of its syntax and it relative familiarity but with the power that you can the power with which you can leverage it to make website so much more interactive。

 And in fact， with bootstrapap， you don't just get CSs you can use。

 you have a whole set of jascript functionality So you can have dropdown menus and the like for instance。

 for instance， among the things you'll use for an upcoming problem set and perhaps your final project。

 something that looks a little like this in bootstpped Hml。

 here's a whole bunch of code that I literally copied and pasted from Botraps documentation and it's just like boilerp code for a corporate website that has features with pricing and disabled menu options as well。

 just for the sake of discussion。 And then here if I go back into this example you'll see fairly simple website that looks like this。

😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_185.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_186.png)

A socalled nav bar with all of the main menu options of like a corporate website and notice if you start to resize the window。

 which I'll do here and put it into sort of mobile mode because it's so narrow now。

 thanks to jascript， it's listening for clicks on this hamburger menu and revealing the menu options that way。

 This is quite like how C50's zone website works in so many other websites out there But the last one we thought we'd use is you're so in the habit of using Google Maps or Uber Es or any number of apps that need to know your location that too is exposed through jascript quite simply let me go ahead and in geolocation Hml open up the following code。

 whereby super simple even though some new functions。

 there exists another global variable in jascript in browser called Navigator which has a property an object called geolocation which has a function called get current position that takes an argument which is just an anonymous function。

 which means call this code when you're ready to know the coordinates because it might take a while to figure out your GPS。



![](img/4c54343641083e31267eb96a2dc6e4c4_188.png)

![](img/4c54343641083e31267eb96a2dc6e4c4_189.png)

coors， and once you do， this simple example is just going to write to the document。

 That is the rectangular page， the positions latitude that comes back and the positions longitude that comes back。

 So to see this in action， let me go ahead and open up that second tab， go back into geoloc。



![](img/4c54343641083e31267eb96a2dc6e4c4_191.png)

It's notice for privacy's sake。 It's asking me to approve this。 So I'm gonna to say， allow this time。

 There are apparently my laptops GPS coordinates。 And if I go to Google Maps do com。

 I can actually paste this in here， enter。

![](img/4c54343641083e31267eb96a2dc6e4c4_193.png)

And。Looks like if we zoom in in in。 okay， I'm not technically outside。

 So it's only close to a degree of precision， but it's probably mapping to one of the w-fi access points that's on that corner of the building。

 So we're pretty darn close， pretty much close enough to get me my food or my ride here。

 And a final note now that you've seen a little bit of jascript。

 let me go ahead and open up just 60 final seconds of just how how much effort it took us to put not only this lecture together。

 But particularly that example of the teaching fellows passing packet。

 Everything we like to think is very finally flourished here。

 But here's a little bit behind the scenes and these final 60 seconds together。

 If we could dim the lights before we adjourn。😊。

![](img/4c54343641083e31267eb96a2dc6e4c4_195.png)

And if we could crank the music up high。🎼어디 here？Offering， okay。🎼よし！🎼全だ。ふ。Mon no， oh， wait。

That was amazing， Josh。🎼啊。🎼The。🎼So big。🎼对。🎼没 think。That was perfect。🎼Okay。は。🎼I think I。🎼第。

Over to URL。🎼Oh thanks。🎼はい。That was amazing Thank you all Oh good。All right， that's it for CS50。

 we'll see you next time。