# UCB《计算机安全｜CS 161 Fall 2023 ｜ Computer Security at UC Berkeley》Calude-3.5翻译 p21 -21--CS161 FA23- Lecture 21 - DNS.zh_en -BV1YGbceREDs_p21-

嗯。

![](img/9a1fa253799891e5cfcc3e5468b19cf7_1.png)

Okay hello I kind of guess Project two is almost too so it's kind of empty here。

 but it's all good keep talking about networking I guess I'll give you a couple more since I think Project two is due today tomorrow。

 tomorrow I think probably plus some extensions so I assume most people are kind of like deep in coding one thing I will say for anyone watching the recording or anyone here is like if you have not started writing code for this project like you are behind there is code to write and code to debug so you really want to get on that like now you can walk out and start coding if you want to but this is definitely a time where we're supposed to be heavy in the coding phase and like getting your design down on paper on code and testing that it works one thing is like when you're writing code you're gonna to run into errors you're gonna run into debugging things and so my recommendation which like you don't have to fall you can debug in the way that you like but personally I have a hard time staring at code and figuring out what's going wrong I don't know about you if that's not of superpower that I have and so instead like I would recommend using any form of。

buer so we have a recommendation for the first time ever like shout out to Levy who is one of our Tas who wrote this so for the first time ever we are actually telling you exactly how to set up Abugger and it looks beautiful。

 it looks just like a debugger you've seen from like 6 and B or any other IDE that you've worked on you can inspect all the variables are you can step into functions。

 you can set breakpoints， all that fun stuff and so something's not working and you have this function like 10 lines and you need to know where something's going wrong you can set breakpoints say like this is halfway through the function。

 does everything look the way that I expect is it the first half of the function that's growth into the second half maybe it's all like debugging stuff you've heard before。

 but I just want to emphasize that like this is going to be more efficient in my opinion and faster than just like trying to shove and print statements or just staring at it really hard I hoping that you magically find it that's my take on it if you don't want to just use the one that we provided you can also pick your own there's like a lot of freedom here So if you don't like V code I believe there is something called goland。

As't like use that I haven't but apparently Goland is like the Jebrains equivalent of In from 60 and B but for go so if you want to use that。

 I assume it looks kind of similar to 601B In you can play with that too but I guess all I'm saying is like debugging tools exist theyre there to help and they're very powerful so it's kind of like at least a waste to not try it at least so if you're like stuck debugging that's what I recommend there's also some other tips just in this like advice section that might be helpful so like for example if you're in the writing phase at this point like it's going to be attempting to say oh the projects due tomorrow so I'm going to write as much code as I can like 500 lines and then running out the autograr and just hope that it passes you're probably going have a bad time if you do that like even though you know I know the deadlines coming up soon and such like it's still good to invest time and test as you go and I'm sure you've heard this before over and over again from other classes but I just want to say it like one more time just to like get it in your brains that。

Testing as you go we think it is a good idea you're investing time now to avoid debugging misery later and same thing with like writing helper functions and testing them in incremental pieces as you go I prefer it if you would like to write 500 lines of code and pray that it works that is your prerogative but is not what I recommend okay so that's my tip is' not really a tip for the project specifically but it's just a tip for like writing large pieces of code which is what this is so there you have project two questions shoot。

Noello。好的。Yeah it's a good question so what do the existing tests tell you all the basic tests that we provide are functionality tests so they pretty much tell you that say like if I store a file and I load back I get the right stuff like that but in terms of edge cases we don't have any of those coverage so it's up to you to cover them you can use the coverage blocks and help you get hint us to like how comprehensive your tests are we also don't cover any attacks so if you ask me like if the attacker modifies such and such will I attack it and cause an error none of the provided test check that that's all on you and I know it's kind of rude like no one likes hidden tests I get it nobody likes that every semester people are like to show us the test like whats this distribution I know it's kind of rude but the reason why we're doing right and I think it's in here too if you can read that but I know it's rude like multiple people have designed this project over the years but the reason why we've stuck with this after all this time is because attackers in real life do not walk。

upp to you and tell you here's the thing that i'm going to do as an attack right to defend like that's not what attackers do and so for the same reason we are the attackers we're not going to tell you what we're doing so you have to proactively come up with them like that's the design portion of this project Okay other questions yeah。

这第二是。Yeah the test coverage is not hidden so I believe this is also mentioned I know this be is long it's a lot of words I get it but I believe it says yeah so whatever whatever you get on gradeco that's your and if you hit all the coverage flags it's great it doesn't guarantee that your implementation is perfect it just means that you are thinking of all the same things that we're thinking of but not necessarily like exactly the same tests。

Okay， those are all great questions as you start coding these are kind of ways you start。

These are kind of the things that I think I start thinking about， at least。Okay， so yeah， good luck。

 it is a difficult project You do not have to get 100% of this project to pass the class like not even close。

 This is what the distribution has looked like in the past。 itles up and down every semester。

 but it's always something like this it is okay not to get full credit it's really difficult to get full credit almost no one ever does and so it's totally okay like we have five years of experience on this project you have four weeks so it's pretty natural that we're gonna have more attacks than you can defend against it's okay but yeah like code incrementalcrly write tests that you go check the same attacks that we're checking or try to check as many of the attacks that we think of and I think it'll be in good shape okay so I believe in you this is like probably the heaviestt part of the class I think it's downhill from here so good luck yall if you have Project two questions we're in office hours we're oned all that good stuff okay enough babbling about project too let's talk about more networking stuff so you remember the Tls handshake from last time it's really complicated I'm not gonna go through。

The steps but a good way to check your understanding is to ask yourself questions like what are the goals of TlS for example I want confidentiality and integrity on my messages how do I get that well the client sends a secret to the server in RSA version or the client in the server is diffyelman to get a secret in the diffy Heman version and then they use that secret and the random numbers to generate keys use those keys to encrypt and mac their messages that's how we have confidentiality how do we know who the server is the server sends a certificate which just tells me what their public key is nothing said about who they are just what their public key is and then in this exchange of the premaster' secret the server either signs their half of diffy Helman or the server attempts to decrypt the premaster secret that you send in either case the server is solving a challenge to proof that they know the corresponding private key so that's how we know who the server is and not like someone pretending to be the server and then finally how do we stop a replay attacks well remember that these。

ranandom numbers stop replay attacks from different connections and showing record numbers or timestamps。

 if you like to think of them that way inside the messages that I sent and encrypting those record numbers or timestamps is how I stop replay attacks within a connection。

Okay。All from last time we talked about the properties。

 It's really great gives you end to end security but there are some things that it doesn't give so no anonymity people know who you're talking to some availability attackers can drop your messages but at least if everyone between you and the servers a man in the middle none of those people can tamper with your communications however you're still talking to the person at the end and if the person on the other end is the attacker then all thats are around okay so that was DlS now we are done with the stack by the way so in terms of like the 1970s oldass models stack that we were going up and down we're kind of done with that to the point where I can't really use it anymore for these later topics but we're gonna go through a kind of clean up other things that we need to make the internet run and then maybe at the anglestructure like transition into some special topics but today's topic I don't know if it's like a side special topic it's really key really important and this is something that makes the Internet work so we have to have it it just doesn't cleanly fit into the layer diagram so if you asked me what layer DNS is at。

I don't know I think the 1970 diagram is just too old for this but this is still something really important that keeps the internet running so we'll talk about what it is for one half of the today then I'll tell you the security properties and how peopletulate okay so here comes DNS so you already know that computers are addressed using IP addresses so if I say I want to send a message my friend in whatever country I said last time well their computer has a unique IP address that tells me where they are in the world and how to route that message to them so that's how I send a message to someone it might look like that and so like well who is this number good for well this number is great for machines because the machine looking at this number can look at the number and to do something about where the packet should go how that happens is beyond the scope of our class they can imagine these numbers are useful for machines they contain useful information about where the packet should be going but from a human perspective that's not super useful like am I really going to remember the IP address。

Every single website I ever want to go to like when you type or like go on a web browser。

 do you type an IP addresses， I don't right you could but I don't know about you but I don't do that and so what do we do instead like when I open up a browser and I want to visit a website What do I type instead I type domain names something like that and so that's great for humans because we can read this it has meaning to us like we can understand the words and what they mean however this is useless for machines because if a machine looks at this they have no idea where the package should go and so there's a mismatch we speak one language which is the English human readable domain names computers speak the language of IP addresses and so we have to reconcile that that's what DNS is going to do for us one final note is that you might think that domains and URLs are like almost the same thing and they kind of are but remember the domain is just this part of the URL not the stuff before or after the stuff before and after is used that the web layer we are only a concern。

the networking layer or the networking stuff associated with the domain name。

 so I only care about who I'm contacting， I don't care what file I want once I get to that server。

Okay so what do I have to do between these two， I need a translation system basically I need to know if I have this human readable domain name what is the corresponding machine readable IP address that's what DNS is going to do it is a translation protocol where I can translate the human readable domain name to the machine readable IP address okay and so the terminology that we use is if you want to do this translation you're going to do like a lookup so you're can imagine somewhere out there someone knows all the mappings you're going to do a lookup you're going to ask someone what the mapping is and then they're going to tell you what the IP address is all of this by the way it's done over the internet so you're sending packets in DNS to figure out what the translation is and only after you're done with all the DNS lookup and translation you can then take this IP address and send the real data to them or whatever it is you want to tell them but today's goal is all about how do you make this DNS protocol run okay so as we kind of like alluded to。

Someone out there is going to have to remember all this stuff like our computer does not have all of these mappings memorized so someone out there does and so the people out there who have this stuff memorized they're called name servers and so a name server is a computer sitting on the internet just like a web server that's answering Google search or an SS server that's like letting you SSH for project one。

 whatever it is a server sitting on the Internet that can receive packets and send packets just like your computer just like the Google's web server so it's just some server out there but unlike those servers which are returning say Hm jascript this name server entire existence in life is to receive packets with DNS questions like please translate this for me and then return answers which says well you asked for the IP address of www。

google co I'm going to send you a response telling you what it is so this name server's whole existence in life is just to answer those questions and the way that it does that is。

Sits on the Internet ways for packets to come in and send responses and so what you can do then is you can send queries or questions to the server over the Internet the server is gonna receive that packet。

 do the translation for you send you a packet with the response and that's how you learn what the IP address is okay one thing that kind of confuses people at this point is that because the name server sits on the Internet the name server itself also has a domain and an IP address This is just like how any other computer on the Internet has a domain and an IP address。

 the name server has a name to just like everyone else but its purpose is to answer what other name to IP address mappings are okay so we could just stop right there。

 but there are a couple of problems， they're kind of similar to the certificate problems that we saw from earlier so maybe these sound familiar they come up all over the place so one of the problems of scalability you can imagine if there's only one of these name servers sitting on the Internet that's a lot of work for one name server to do。

To memorize every single mapping that's a lot of mappings and IP addresses they have to answer every request that's a lot of traffic that they now have to handle and what if the name server goes down like does the internet break that would be bad and so we can't just have a single name server that's not scalable just like housing certificates having a single source of truth was not scalable so instead。

We're going to try something different which is I'm going to split across several different name servers and so now there's not just one name server answering everyone's questions。

 there's going to be multiple name servers and everyone answers these questions。

 but now you have a problem which is if there's all these different name servers like who do you talk to？

RightSo we're gonna have to organize these name servers better and so we're going to organize them in a hierarchy and again these hierarchies we've kind of seen before but there are like two big ideas that I think make DNS run so they get you're set on DNS and everything else is just implementation trivia maybe not trivia it's good to know and the design is interesting but these are the big ideas that make it work so the first big idea is that if you ask a name server whose entire goal in life is to answer your question if the name server doesn't know the name server is prohibit it from just giving up on your query so the name server if they don't know。

 they guarantee that they either know the answer or if they don't know they're going to redirect you to someone else who does know so it's like I don't know if you go to office hours you ask a TA a question I don't know like maybe your Tas do this I hope they don't but like as a TA we've been told or we've been trained to not say like oh I don't know the answer okay bye go away we can't do that and so instead。

When we don't know like it's our responsibility to direct you to someone else who does know maybe it's maybe it's me maybe it's Ed but there's got to be somewhere else that we can redirect you to at least get you closer to the answer even if we don't know so that's the first big idea if someone doesn't know they need to direct you to someone who can help and then the second idea is that we have all these different name servers I'm going to organize them in a way that looks like a tree and when we combine that tree with idea number one we're gonna get DNS and so if I arrange these name servers in a tree。

 the idea is that if you don't know you can direct the person down the tree until they find the answer that one's probably going make more sense once you see the tree okay there's the tree and so this tree is kind of similar to what we've seen before if you have domains you can organize them in this tree hierarchy I have not really thought of a good way to explain this besides like looking at it right it seems reasonable that birthdayedduu as a domain is a subdomain ofedduu and like mit。

edduu is also a sub。I don't really know how to explain it。

 but that's the way that you build these hierarchies you look at the domains and which ones are sub domainomains of others and you build the hierarchy okay and so the idea is that you start at the top and if they don't know the answer they direct you down the chain or down the tree until someone does know the answer okay so。

Every box by the way， on this diagram represents a name server so if you're wondering what this hierarchy is the idea is that every box represents a name server and the label in the box tells me what that name server knows So for example this name server it's server who sits on the internet and its entire goal in life is to answer your questions and this name server has this own IP address own domain and this label tells me that this IP address and domain this name server it knows about edu queries so it's really good at answering questions like hey。

 what's the IP address of etopbri eduu this name server either knows or is able to redirect you similar but this name server kind of has no clue about things like co So if you ask it co you're kind of stuck you have to ask you should ask someone else okay so that's what usually of these boxes represents they represent separate name servers and the thing that I'm writing inside is not the name server like it's not where the server is this is not the160 server this is some other name。

Whose goal in life is to answer CS161。org queries， DNS queries。

So I think I'll just like go through the walkthrough and then maybe you have questions we can go through it。

 but this is one of those things where I think example is most helpful and so I'm gonna to look at the example okay and so here's you okay I want to know a translation and so let's walk through what I would look like So all the queries start at the very top so if I look at this big diagram and maybe I don't even know who these people are I don't have a list of all the DNS name servers and so maybe I don't even know where to find all of these people so I'm going start just by asking the one person who I know is for going to be able to answer my question or at least get me closer that's the root so I'm gonna go all the way to the boss because I know that they can answer anything they're at the top of the tree and their domain or sorry they're like zone is the dot so they can answer questions for any query out there so this is like a pretty reasonable first person to ask they know everything or at least they can direct me closer and maybe I don't even know where these other servers are so I'm going start at the very top and just go straight to the boss and be like。

Tell me what the IP address of this domain is and what's the root going say the root might know it but you can imagine the root's not gonna waste all of its time answering every single question so instead the root's gonna say actually I don't know what the answer is I'm too high up in the chain I can't answer these petty questions but instead I'm going to direct you down the chain to one of my little assistance who can help you and in this case the relevant next name server who's able to help is the doedduu name server is notorg because I didn't ask about a doorg query I asked for e。

berkeleyedu so the root's going say I don't know go find theedduu name server they're going have your answer okay so I didn't get the answer but I got closer so now I'm gonna to repeat the same process go to theedu name server ask the exact same question my question doesn't change I'm just asking a different person the same question and theedduu name server is again going to say I'm not dealing with petty stuff like answering the question I'm going to direct you to one of my assistants who can help。

In this case， the most relevant assistant is the Bkeley。edu name server and what is this。

 this is a computer sitting on the internet whose whole existence in life is answering DNS queries that relate to berkeley。

edu so I go and ask them and finally this Bkeley。edu name server is specific enough to answer my question and it says。

 okay， I know your answer， there's your answer and I've gotten my answer。Okay。

 but I did have to jump all the way down the tree Okay。

 I'll take some questions yeah so yeah it' a good question so the question was what what actually gets sent in two and four if you wait a couple slides you will see。

Good question other totally random question was in chat are coverage flags just for a functionality like Project two thing sorry context switch really quickly coverage flags also checked for it just checks parts of the staff solution and so if you hit lines in the staff solution and get coverage flags but I don't know if the lines necessarily correspond to security or whatever back to DNS sorry okay anyway so this is the kind of highlevel picture I'm gonna to add one little extra feature just to make it look like what DNS looks like in real life but this is one of those things that doesn't really change the structure or the big ideas is's just one little asterisk that makes it all match closer to what real life is actually doing and so the one little thing I have to add is that usually your computers not the one doing all this work I mean you could in theory go up and ask all of these name servers all the questions but in practice we're probably not going do that and we're gonna to be lazy and we're just going go and ask someone else on the network to do all the work for us。

And so this creates a model where our computers like the stub Rer where we're not gonna to do the work we're just gonna go ask someone else to do all the hard work for us and then get the answer and then somewhere out on the local network there's another machine the recursive resolver whose actual goal is to make all those recursive or iterative queries and thens send the answer back to you so here's what it looks like and we'll talk about why this is useful probably in a couple slides to has to do with caching if you want to preview but basically this is you now so you could certainly walk up to all the name servers and ask them all the questions but like I'm lazy I don't want to do that so I'm just going to ask the recursive resolver I want etopbroedduu do the rest of the work for me and so the recursive resolver will be okay and the recursive resolver does the same six back and forth messages goes to the root doesn't know goes toedduu doesn't know goes to Bley。

edduu gets the answer all of that is unchanged I just outsourced it to someone else and then the recursive resolver after doing all the hard work and getting the answer sends it back to me。

So I just added one step at the beginning， one step at the end， so instead of doing the work myself。

 I made someone else。😡，That's it small change。And we'll see why that's useful again。

 probably in a couple slides， the idea is that if multiple people last a recursive resolver。

 they're better at caing stuff， okay， or they can cash more stuff。Okay。

 I'll start talking about implementation unless there are other questions。

It has a really good question so the question was in this hierarchy if the goal is to not overload any server isn't the route just going get totally overwhelmed so in this like plain DNS yes but as soon as I add caching it will no longer overload okay so preview okay questions are there multiple root servers this something I think we'll see later as well there can be multiple root servers yeah but they will be mirrors doing the exact same thing。

Okay those are good questions though but anyway， this is the highlevel idea if you get the two big ideas which is if you don't know as someone else and arrange the name servers in a tree and go down the tree so you find the answer you're good with the highlevel DNS and now I'm just going start implementing it making it fast and everything else at that Time to implement it so one first question I have to ask is how do I send the packets back and forth remember when I move up the stack there are a couple of choice points I can make one of the choice points is when I get to layer for or I'm trying to ensure reliability at ports and all that good stuff I get a choice do I want TCP or do I want UDP remember TCP is the one that has all the sequence numbers acknowledgement numbers make sure everything gets sent and delivered on time and in the right order and UDP was none of that so DNS I guess the title of the slide spoils it uses UDP and so why would DNS choose to use UDP and so the main reason is because as we saw in the UDP versus TCPs。

A couple lectures back UDB is faster and DNS the designers of DNS that is they want DNS to be really fast like think about when you use DNS right if you go to your web browser and you type in a URL and want to navigate to it you have to run DNS every single time you go to a website you first have to run this DNS query to figure out。

Where you're going so if you want to like type in something you want to send an email。

 whatever you have to run DNS and so DNS gets run all the time like in almost every web query that you're ever going make and so because of that people who design DNS they find it a very high priority that DNS needs to be super fast because you're using this thing all the time it better be fast or else DNS being slow slows down like the rest of the internet and we don't like that and so given the choice between UDP and TCP the designers decided you know what TCP is good reliability but that extra handshake too slow I want this to be instant so I'm going to use UDP because it's fast and we'll see how to deal with the reliability thing I guess right now okay so I guess the trick as to why UDP works in this case is because you can fit the entire DNS query and the entire DNS response in a single UDP packet so that's what we'll do so we don't really have to worry about packets being reordered。

Whatever the DNS question is a single UDP packet the DNS response is a single UDP packet and so I don't have to worry about how do I split how do I deal with you know messages not showing up if it doesn't show up send the question again so that's why UDP works in this particular case and so now it's time to format my message so I know that if i'm sending a UDP packet I get the features that UDP provides which is this stuff up here this is the UDP header you've seen it and。

Just like we talked about back in UDP TCP we know that you have to choose ports right so my port can be whatever you want just like how my own room number at home I can pick whatever number I want no one cares for security reasons randomizing it might be useful but we'll talk about that later but just like we talked about with ports the destination port or the port on the server site the name server side that needs to be constant the number that people use in real life don't have to memorize but it's 53 and the idea here is again we need to know that the port 53 is where the name server is listening for requests and answering every question and not any other port so this has to be public has to be wellknow it's basically 53 okay and then these two don't really have to worry about but basically the idea is that for any UDP packet that you construct you have to fill in these fields and the sorts in the destination port are the ones that we hear about。

Okay， source can be random， destination needs to be constant when the server replies。

 they swap the two because the source is now them and the destination is now less。

Okay now we're gonna dig into the DNS packet itself。

 so this is the UDP header inside we can send whatever the heck we want with UDP right I could write a letter like hey dear name server tell me what the IP address is but like I don't think the name server understands that so we're going now set up a DNS packet format such that we understand how to fill these things out it's like a little form we fill it out in a very consistent way and then the name server responds in a very consistent way so we both speak the same language and the ones in the zeros that we send they have the same meaning so here's how we do it we're going fill in all of these fields and they're all mandatory we got to fill all them in and so。

The first one I'm going to fill in is an ID number and this is going to help me associate queries with responses so if I'd send two questions to the same name server and I get two answers back how do I know which one's which the ID number is going to help me do that and so I can say this first one is like request number 10 and this one is request number 70 I send them both off and when I get two answers I know which one corresponds to which okay and so the name server is got to pick the same ID number in the response that's how you associate which query comes with which response again for security this can be randomized and we'll see what that's useful later and then after that ID number there are some flags that I don't think we're talking about in this class and after that the DNS packets going to be organized using records and we're gonna to see what records is I think now but here we'll have a count of how many records there are okay so let's look about what the records are so after the ID number everything else is going to be stored in a record and so any data that I want has to be stored as a record。

And the records are name value pairs I think cookies think python dictionary whatever you like think hashmap right you need name value pairs for every piece of data so whatever piece of data you care about it's got to be organized in name value pair and again we'll see why this is useful for performance pretty soon but name value pairs are kind of what we're looking for here you could have designed this differently but they chose that this is how you must store data and so。

Once you have a bunch of records you could also just like tape the records and just send them off in a big old pile but instead DNS says let's just be a little bit more organized and we're going to sort the records into four sections so there they are so for every record that you create you got to toss in one of these four bins or these four sections and where you put the DNS record depends on what the record represents so let's take a look I guess we'll take a look at what sections are in a little bit but the important thing is every record that you create gets dumped in one of the four sections okay。

Now let's dig inside and see what the record itself contains so as we said we know the data itself as a name value but each record also has a type and so when you think type think like data type in you know a language like Java or go or you declare something you have to say what type it is and so in the same way when you create a new DNS record you need to say what type it is and the type tells you what kind of data the record contains okay so here are the types that you can choose from just like how in Java or go you can choose like in you can choose string whatever here are the types you can choose you can choose a as your type a stands for answer I think and so that type would allow you to map domain names to IPV4 addresses so do we have an example okay maybe you'll see an example later but the idea is that the a record the name in the name value pair is the domain name like www Google the value is an IPV4 address so it's those four number separated by dots there's another type which is name server record this is the type that we're going to use。

We don't know the answer and we want to ask someone else what the answer is or we want to redirect you from to someone else so in this case we're going use this type if we want to say like I don't know but go talk to that other guy he's going to know or they're going know while the name server is going to be used whenever I want to redirect to someone else and we'll see what that looks like probably soon okay there's a lot of like flash forwarding in this lecture but it's true okay again there are other types all sorts of different types but these are the two that we really care about for now and。

Inside the record there's also metadata and most of them we don't care about they're just kind of fields to keep everything running The one that I do think is useful is time to live which tells you when the record expires so how long can you keep this record before it expires that one's gonna useful everything else I don't really care okay so we'll see what these record types are but you can think Java type they tell me what data goes in the record and then once I pick a type I put them in one of the four sections so the type and the section are actually two different ways to sort the record you first pick a type and then you put it in one of the sections okay。

Here's a slide if you really care what the different types are。

 there's all sorts of wacky types I don't really care。

 but if you ever work in you know like networking and stuff you'll probably see these but you don't need to know about them in this class okay let's talk about those four sections and how you dump the records in the correct section so if your record asks about the question then you put it in the question section make sense and so for example if I want to know what is the IP address of etopberkeley。

edduu I can't like write that in English and hope that the other side understands it I need to formulate it as a record and specifically the record type that I'm going to use is an a type record where I fill in the name which says etopberkeley。

edduu and I leave the value blank。Indicating that I don't know what that is and I put that in the question section that's how I represent in code or in this format the question that i'm trying to ask and then when the server responds they'll usually give you back the same question just to remind you like here's the question that you asked and here's my answer okay。

What in the answer section， this is where you would put anything that involves the direct answer so for example。

 if the name server knows， oh you asked me about the IP address of etopberkeley。

edduu and I know the answer and I want to send it back to you well then I can put that record in the answer section so I can write a little a record that says name is etopberkeley value is this IP address and the way that I will send it to you is I would stick it in the answer section that way you know what the answer is。

Okay and again this is usually an a type record and we'll see that and then these last two sections I actually don't know why the additional word is here and then it shows up here。

 but anyway these last two sections what they're going to be used for is that last thing we need which is where you don't know the answer and you want to ask someone else so the authority section is where we're going to say I don't know the glue ask that person because they really know about this subject so if I ever want to delegate authority to someone else then I'm going to write those in terms of NSs records and I'm going to put them in the authority section okay and then finally the additional section is where there's any other information that you need to complete the query and we'll see why this is useful once I put all the pieces together but the idea here is that if there's anything else you need like you want to give the person an extra hint as to where to find the next person or something you can put them in the additional section sometimes these records are called glue records because they like make everything work but glue the different pieces together。

Again I think this makes more sense once you see the sections in action。

 but this is a high level idea of what the sections are for， so you create a record。

 you give it a type to tell you what data is in the record and then you put the record in one of these four sections depending on what the purpose of the record is so for example if you have an A type record it could go in any of these sections。

 depending on if your a type record represents the question or the answer or some additional info but it can go in any of these sections。

Okay。So okay I guess I have one more thing to tell you before I can go and walk you through it which I think is the most helpful thing so the final thing that I think ties DNS all in terms of performance and we'll see this over and over again is we already mention we don't want to ask the root same question over and over because that would overwhelm the route we don't want to for example like have to resend the same questions over and over to anyone really not just the root and we don't want to bother the route too many times we don't want to waste time asking duplicate questions and so the way that we are going to make DNS really fast is we're going to cache as much as we possibly can so any record that comes back we cache until the time to live expires and instead of sending a request if I can ever find the answer in my cache as a record I will just go into cache and pull out the record that I'm looking for this is also why we chose to use records so you might ask well wait a minute what if I designed this different DNS where like instead of records I did the separate thing you could but the beauty of records。

that because every piece of data comes in a record。

 any record that I receive can be cached and I just have this cache that's a big list of records I can scan through it and find the thing I'm looking for so that's why the records are designed the way that they are。

Okay， but mostly'll catching more throughout the day。

Okay here is the walkthrough that I think puts all the pieces together so you roughly know what the message format is like now you get to see what the actual format is I find this pretty cool because you can actually go in your terminal and run this yourself so it might be some things that you have to do but I think for most people you can just type this in your terminal and see if it works all of our computers have DNS built in because when you go on your browser you got to run DNS queries and if you want to expose that raw DNS code you can use the dig command I'm going to add no recur because I don't want DNS to just go and ask all the questions and give me the final answer I want to step to the recursion myself so I add this no recurse flag and so let's go ahead and start sending some stuff okay。

And so this is just gal syntax I don't care if you know it it basically says I would like to know the IP address of e。

berkeley。edu the query I'm intensely curious about and here's what I'm going to ask I'm going ask the root name server how do I know who the root name server is this is the very top of the tree and so we're gonna to assume this thing is hardcoded everybody knows it it's just kind of common information so in the same way that like all of us know who the president of the United States is every computer knows what the root name server's IP address is it's hardcoded it's public info everyone knows。

But if I don't have any further info my cache is empty I gotta go to the root first and go to the boss and see if they know because I know the root can answer for everybody so I'm gonna to start by asking the roots okay this is the answer I get back I know it looks really gross but I find it kind of beautiful in that everything that you see on here is actually readable by you that's pretty cool so here's the response kind of looks garbagegy and so here's the header says header and if you look in the header we see all the things that we saw earlier when I showed you the diagram version so there's the ID number when I ran this my computer chose 26114 the ID number and the response came back and said here's the answer to question number 26114 so I got the ID that's cool I also got to count and the count tells me some interesting things like it tells me here's the flags I don't care about those for this class anyway here are the count and tell me interesting things like hey there was one record in the query section there are no answers in the or there's no records in the answer section there are 13 records in the。

Authority section 27 records in the additional section okay good to know so it gives me count of how full each of the sections are with records now I can go into the sections and check out what the records are i'm going to go to query first just to see what's going on there so here's all the records they're laid out for me i'm going to look in the query section see what the records are。

The query section has just one record there it is and it's kind of what I expect the data type is a when the data type is a it means that the name is the domain and the value is an IP address that's what the data type means when I put a I must put a domain here I must put a IP address here and so that's what this a means and what domain do I care about etopberkeley。

edduu what's the IP address is blank what does it mean to be blank it indicates that that's my question it's blank because I don't know so that's what the query is and the DN server sent back the question just to tell me that's what you asked okay。

Now I really wish I had an answer， but I don't and the root tells me there's no answer by leaving the answer section blank so I look in the answer section zero records okay DNS server from the root did not have an answer for me so what do I do now well now the DNS server has to tell me remember how in English we said I don't know but my friend over to there it's a do Eduu server they know so go ask that so this is what that gets represented or this is what the representation looks like in code so it's kind of a heavy duty section so I'll walk you through it in a a couple different ways so what do I have to know at a high level like forget all this text what do I have to know at a high level about the next person so when someone walks up to me and says I don't know but go ask that person did know your answer what do I have to know about the other names turns out there are three things I have to know maybe you can guess them by looking at this picture the first thing I have to know is well what is the human readable domain name of that other name server that I want to go to？

Remember every name service is on the Internet and they all have their own domain names I want to know what that other person's domain name is the human readable domain name I would also like to know what the other person's human readable IP addresses and I would also like to know what that other person can speak for is that other person under the route are they theedduu server that can answer e questions are they theedduu server are they someone else entirely I would like to know what this server is an expert on and what they can answer for so those are the three pieces of information that I have to know So one way you can think of this section as organized is well everything's a record everything's name value so how the heck am I going to get three values into a name value pair and the answer is I don't there are three values everything is a name value pair so the way that I kind of hack around that or solve that problem is I write two records in order to redirect me to somewhere else and the two records that I send one of them is this NS record。

So I indicate that the type is NSs and if the type is NSs it locks my name and value pairs into having certain data types。

 so when I say this is a type NSs my name must be a zone it must tell me that the person you want to talk to is a doteddu expert go talk to them and then the value tells me this is their humanreutable domain name a。

edduuservs net that's what you want to talk to okay。

And then the second record that goes along with the first record they kind of come in pairs。

 the second record says， well those are two of the three pieces of info。

 but I haven't given you the third piece of info which is the IP address and so here's the IP address you're looking for but I can't just send the IP address by itself I need to organize it in a record and the record that I'm going to choose as an a record because a records have IP addresses it's gonna to say a doedduu servers donet has IP address this thing 192。

5。6。30 so these two records in a pair they help me redirect someone else who can help me answer the question they tell me three things the next person you're about to talk to is a doedduu expert they have this human readable domain name they have this IP address and one thing that always trips people up at this point by the way why the heck is this donet remember this name server is just somebody sitting on the internet ready to answer your questions just because they are a doedduu expert does not mean their name has to end in。

EduYou can be a server whose name ends in dot net and still be a doedu wizard or like expert and that's what this particular server happens to be so that's okay sometimes it looks a little bit confusing the first time but that is what this pair of records does that's one way to think about it if you like it go with that if you don't like it another way that I've seen people explain this is well first I'm going to send the NSs record which basically says I don't know go talk to the doedduu wizard and the doedduu wizard lives at this human readable domain name if I just sent this one record and I sent no further records what would your next step be your next step would be okay the root server has told me go talk to this other person so I'm gonna go to8duu servernet and go find that other person except。

I don't know where this person is。 I don't have their ID address and so in order to figure that out if I had no other records。

 I would have to run another DNS query to figure out what the IP address of this name server is even though I'm already running a DNS query so I'm somehow running like another DNS query in the middle of my DNS query that's too much work I don't want to do that and so instead the root name server basically says。

 okay I'm going redirect you to my friend here who lives at a doedduuservs net but I know you I know your next question is going to be what is there IP address I know you're gonna ask that because you don't know so I'm just going to hopefully give it to you right here because I know and so that saves you a step so now you don't have to run like a DNS query inside a DNS query or something weird like that this additional record and maybe that's one explanation for why I'm losing the additional section you didn't have to give this to you if you didn't have this record you could certainly just go and like run a DNS query and get this answer and figure out who the A E。

ervers net IP address is or what that IP address is but thename server is kind of nice and it says。

 I'll just do you a solid do you a favor and give it to you right here as additional info that I think you would you would find helpful so that's another way of thinking of it but in essence these two records store three pieces of information so you can either think of it as a hack you need two records to throw three pieces of data as name value pairs or you can think of it as this is the true record that you need to redirect to someone else who knows and then this is just an additional answer as a hint that says by the way if you're going go find that person that's where they that's their IP address I knew you were gonna to ask so I'm just going to tell you right now so both of those are perfectly valid explanations for why this is the case the final question that I have to solve is why were there 13 records instead of one and why were there 27 additional records instead of one and the answer here is just that there are lots of different Edu servers living on the internet who can all answereddu queries so。

This is good for you know load balancing so instead of having one person answer there are 13 people answeringedduu queries 13 different name servers and also if one of them goes down you contact them and there's no answer and go talk to one of the 12 other ones so the only reason why there are multiple records here is for redundancy so I chose to use the first one here if you wanted to use the second one or whatever you can but that's why there are 13。

Okay。Great， so now now we know what this represents。

 I think this is really cool because it looks like total know like hacker gibberish。

 but we were able to break it down That's pretty cool anyway。

 looking at this whole answer it tells me I don't know the next person I should ask is aedduu servers net because they're aedduuwizard and expert and they live at this IP address so let's gonna find them so I'll take this IP address copy it right there my question didn't change I still want to know this eberrkeleyedduu IP address except I'm asking someone different now the root told me I don't know go ask this other guy so I'm gonna go ask the other guy and the other guy gives me this answer and it looks pretty similar so I'm not gonna waste time breaking it all down again there's an I number there's account of all the different sections and how many records they contain the question is fired back at me just to remind myself that's what you asked the answer section is empty because theedduu server is not going to give me the answer and theedu server is gonna to say go talk to the Berkeley。

ED name server where are they Well there's three of them you can talk to any of them All three are Berkeleyedduu experts they live at these three human readable IP addresses and because I know you I know you don't know the IP addresses corresponding to these domains I'm just gonna go ahead and give them to you right here so that I can save you a DNS query Another way of thinking of it is they need to give you three pieces of info Berkeleyedduu is the zone that this name server can answer for that's what they're an expert on that's their human readable name that's their machine readable name to give you all three they have to use a pair of records both are pretty reasonable interpretations all of that is to say I didn't get the answer I got to go ask someone else hopefully the query has told me that this is where I should go to find that last person so i'm going to go there plug in the same IP address my question didn't change and so this time I get this answer back and well good news because I look in the answer section is no longer blank it's got an answer so I look。

And it tells me etopbirthday。edu your IP address is this number I found the answer this name server was able to give me the answer okay。

 the final thing that I haven't mentioned yet， what is this number tells me that you can keep this record in your cache for 24 hours after that asking again because it might change later okay。

And so you can keep this record for 24 hours that's what the Time for live says and the good news now is that not only do you have this record so in the future if I ever load edoberkeley。

edduu again I don't have to ask all the I don't have to go to root andedduu and do this whole process the answer is already in my cache for the next 24 hours but along the way and this is what's really cool about DNS I picked up all of these records too and so if I ever have another question all of this stuff is in my cache and I can save myself queries to like say the roots so if I need to if I have another  query that'sedduu I don't have to go to the root and the root doesn't have to tell me whereedduu is all of these records get cached and I can go straight to theedduu person to ask and likewise here I can go straight to these berkeley。

edduu experts to ask about Brkeley related questions so along the way everything gets cached that's how I save myselflookup time for duplicate or redundant or similar queries and that's how I save all these poor name servers。

 the effort of answering my。Repeic questions， okay。That's the walkthrough， it's pretty cool。

 you can walk through it yourself at home， try different queries， whatever you like。

 anything else you would like to know about how DNS works before I tell you how to break it。Okay。

Let's start breaking it so this is the DNS security portion like the second half okay so the first thing that we're going to talk about or I guess the overall like structure of the attacks all of them have the same flavor which is that the thing that I want to attack is the cash right so my computer stores a cash or my resolver stores a cache and it maps all of this useful information I really want to get malicious information in there because that's how I cause the client to mess up the mapping of IP addresses or domains to IP addresses so all of my attacks kind of fall into the same idea which is cash poisoning and what is cash poisoning good for will imagine if somehow I don't know how yet but somehow you are able to get the victim to accept an a record that's incorrect we know the right answer should be etop B that Edu maps to whatever number we saw earlier but what if I'm able to send or somehow get the victim to accept and cash a malicious。

That says Etop Bkeley that Edu maps to this IP address if I'm able to convince the victim that this is true then the victim stores this in their cash and then the future when they want to go to etop Berkeley that Edu what do they do they look in their cache or I know the answer already I'll send my etop Bthrough that Edu messages my password whatever my homework to 6。

6。6。6 and if we assume that's the attacker now the attacker receives all of my messages。

 they can change them before forwarding it to the real Berkeley and so this makes the attacker and man in the middle so if cash poisoning succeeds the attacker can become a man in the middle and that would be bad so we don't want cash poisoning to happen okay there are other attacks out there but this is kind of the main one that we're focusing on because we do not want DNS records that are incorrect to be accepted and cashed that would be bad okay so here are a couple of ways in which that could happen so one way that we could make this happen is maybe I have somehow hacked into a name。

S all these name servers are sitting there answering questions if the attacker somehow takes control of one of those servers like they break in they run a buffer overflow and they break in or they somehow like steal the password of the name server and they can break in well now they can answer they're still going to get the questions they've broken in other people are still going to send them questions and now they can send down malicious responses that would be bad and so。

Miicious name servers they can lie and supply malicious answers we don't like that and so that's one possible threat model that we have to deal with And so for example。

 if I ask the Bkeleyedduu name server hey what's the IP address of e。

berkeleyedduu and that name server gets hacked and is malicious they could give me the right answer they could also give me the wrong answer but what other thing they can do is they can also attach other records like well here's the answer to your question you asked about etopberkeley here's the answer。

 oh by the way， the IP address of Google is 6。6。6。6 cash that too and so next time you want to know what the IP address or you want to talk to Google co talk to this IP address and so now the attacker has made themselves a man in the middle for Google Bo queries that's something they could do so if your name server is malicious or has been attacked not only can you poison queries like this and say well you ask IP address of etopberkeley here's the wrong answer I could also throw in additional。

Stuff and poison the cash in all sorts of other ways that's kind of bad and so。

We asked the Berkeleyeddu name server some questions it gave me this bad answer for Google and so that's kind of bad right now this malicious name server can poison anything at once。

 but if I stare at this a little bit doesn't it seem kind of weird why did I ask this Berkeleyeddu expert name server and get an answer that's about Google shouldn't I be kind of suspicious when I see that and the answer is yes。

 you should be suspicious when you see that the Berkeley expert name server has decided to tell you something all about Google why is it telling you about Google and I shouldn't right and so the defense that we're gonna add that's going to limit the damage of DNS malicious name servers we can't stop this entirely because if a name server is hacked and you ask them a question they can always lie about the answer there's no way around that but we can at least limit weird stuff like this or they try to also give you other records that make no sense or that are totally unrelated and the way that we're going to do that is're gonna to ask something called bailluic checking and the idea is that。

The resolver is only going to accept records that are relevant to whatever zone this name server is in It's kind of confusing。

 I think the examples make it more clear if you have a name server who is an expert at answering Bkeley。

edduu questions you should only accept records that are relevant to Berkeley。

edduu for example the IP address of ebrokely。edduu I have to accept that because that's what ask for that question but I do not have to accept answers that have to do with mit。

edduu because thatshuberkeley。edduu speaks for and same thing like theedduu name server can answer any of theseedduu queries but if theedduu name server starts feeding me gocom info I'm going just be like I don't think that's what you're here to speak for I'm not going to accept that and the root name server can answer for anything because it's at the very top and it can answer for anything and so you can imagine if someone compromises the root name server things would go quite wrong so people put in a lot of work to make sure no one compromises the root okay that's what the hierarchy and the bailbook looks like。

It's kind of a weird word， apparently it's like a lawyer term like legal stuff and it means one's fear of operations like I'm going to test you on that but if you're curious it basically says everyone kind of has their own things that they are an expert on and they can speak for and so while I can answer all of your questions about this class if you come up to me and I start like feeding you you know like CS162 data you might kind of want to be suspicious and know I don't know about that okay so that's what bail checking is。

Okay。It doesn't defend against all the malicious name servers。

 but it at least limits the amount of damage that a malicious name server can do， okay？

So that's what happens with name servers now let's think about network attackers what if someone is a man in the middle attacker well this is kind of like the TCP section where I asked well what happens if a man in the middle exist in TCP remember in the TCP lecture there was no cryptography I never mentioned confidentiality or encryption well just like that in today lecture there was nothing about confidentiality encryption integrity。

 no such thing and so for the same reason as TCP DNS is totally insecure against the man in the middle attacker if they're a man in the middle they can receive the DNS response change whatever they like and then send it over to you and there's nothing you can do of it there's no integrity you have no idea that this has been tampered with or dropped or modified okay。

So against the man in the middle you're kind of cooked there's nothing you can do what about onpath attackers again kind of likeTP again there's no security I can't do the man in the middle thing where I just change the message but I still have the spoofing power so the attacker can spoof a response right so I send a request and technically the birth of the Edu name server supposed to send the response but instead I could spoof an answer saying from name server to resolver and feed it a fake answer and then if that gets their first same old race condition we've seen over and over again if the malicious answer gets their first the recursive resolver will accept that one because the recursive resolver is not expecting two answers someone gets the first limit will accept it and cash it and now again you're kind of in trouble okay？

And so that's the onpath attacker they can spoof an answer and if it gets their first it gets accepted same old attack we've seen before what about offpath attackers Well the offpath attacker can also spoof a response but let's think about what has to go in the response so here's what the I sorry the DNS packet structure looks like let's think about what has to go in the response and in particular just like in TCP with a sequence numbers。

 there is one thing that the offpath attackers have a hard time guessing it is the ID number right because the offpath attacker needs to know what the right ID number is if the recursive resolver says question number 260113 is IP address of8 stop Eduu I send it over and then the attacker spoofs the response like the answer to query number two was this well the recursive resolve is gonna be like but I didn't ask you number two I asked you number 260113 and the recursive resolver would not accept because the ID numbers don't match so the offpath。

Atacker now has a challenge which is how does the offpath attacker know what ID number to put in the response field when they spoof they kind of don't have to guess it and so that's kind of tricky and this is why randomness is needed with the ID number you need to put something random here so that the offpath attacker has a hard time guessing it is the exact same structure or like idea as why in TCP we need the random sequence numbers because we want to at least make the offpath attackers' lives a little bit hard we want to give them something they have to guess in TCP is the sequence numbers here it is the ID number and just like in TCP the on-path attacker does not have this problem because they can read the messages being sent back and forth they can see the ID number and just write the correct ID number so on-path attackers have no guessing they have to do offpath attackers do。

Okay， so what do they have to guess they have to guess the ID number it is 16 bits long and so their odds of guessing correctly are one in 65000 well if you think about all the other numbers we've seen in this class like what numbers have we seen like one in over two to the 128 like astronomical numbers or like one over two to the 256 like even the NSA is never going to worry about this kind of numbers。

Compared to those numbers， 65000 is kind of dinky is it kind of small right like compared to all those large numbers and so this is too small compared to some of the other guarantees that we've seen in this class is it true that someone probably is not going to get this lucky yes。

 but if an attacker is persevere persevere is that a word I don't know if the attacker tries a lot they could certainly try a lot of different times and maybe eventually they will get lucky and 65000 is just not that big of a number compared to some of the astronomically large ones so this is actually something we have to be kind of worried about we can't just let it go and say 65000 is kind of large in this particular threat model it's not large enough okay。

I guess it does depend on your threat model， but I would say in general is not large enough here is a slide if you're not convinced about ID numbers being random。

 I'm not going to talk through the whole thing， but it's kind of here for your reading pleasure。

 it basically says if you somehow can force the DNS name server to make or sorry the victim to make two different queries one of which you can see and one of which you cannot well then maybe the one query that you see has ID number like two and then you know the next query has ID number three because they are incrementing and they're not doing things random so you have to be a little bit careful that's all we're saying here okay so maybe you can trick the victim into making a DNS query to somewhere that you know like maybe you control a name server and the DNS or the victim makes a query to you with ID number two and then you ask the victim to make an ID a query to somewhere else and that one has ID number three and you know that it's ID number three even if you can't read the packet because you know the victim is incrementing ID numbers by one this is a hypothetical。

If the victim was incrementing IDs by one， then you can do a attacks like this。

 so please make them random and if you do you don't have to worry about stuff like this。Okay。

We finally arrived at the most confusing and strangest part of today this one always takes me forever to explain and I'll do my best but it's confusing and so if you need a couple looks over it or like when I ask me questions about it。

 kind of go nuts， I guess before I launch into this which is kind of heavy duty。

 anything you want to know about the attacks so far， miicious name server。

 bailluic checking men in the middle on path off path。

It's all good okay here comes the weird thing and so one thing that see okay I thought I had a slide on this maybe not okay so one defense that I will mention that I guess maybe I haven't hasn't been mentioned yet is that one other way you can get this number to be a little bit larger is you can randomize the sourceport as well as the ID number remember the sourceport give me any number right when I'm at home and I choose to give my room a number。

 give me any number right and so I can pick any number here and it would work and so one way to increase the amount of stuff the attacker has to guess is to make this number random as well now the off path digger has to guess the sourceport and the ID number I swear I had a slide on this someone may have to delete it I don't know anyway the idea is called sourceport randomization and the idea is that you take this source part also randomize it and so now the attacker has to guess two or sorry they have to guess 32 bits with success probability one over2 to the 32。

That is something like 4 billion so it's at least better than 65。

000 now an attacker has to try 4 billion times in order to guess the source port and the ID number correctly that's pretty good questions。

Yes。Yeah， there's other ways to do it so the question was could I also just maybe add extraneous records that introduce more randomness I think it's possible one thing that people do that's kind of weird that we're not going to talk about is since case doesn't matter like capital lowercase you can also just like randomly capital uppercase a couple of letters in your query and make the attacker gets that too but there are different creative ways to change it but ultimately your limiting factor and there's something we'll talk about with Kaminsky is that this DNS packet is like set in stone you cannot change this format you cannot choose to oh let me add a longer ID number because this is the format that everyone is using and if you would like to update it half fun going around updating every computer in the world this is what everyone speaks and so just changing the amount of bits in the ID number is not going to totally work so source for randomization at least gets this thing from 65000 to 4 billion okay。

And so for most people4 billion is probably good enough。

 but there was one person for whom4 billion was not good enough and that was kinsky so what did he come up with。

So he came up with this idea and it's really kind of strange and I'll try to talk you through it and it basically says that you can actually change the character of the race condition so that instead of trying once and being walked out you can try as many times as you want until success and that's going to make brute force attacks much more plausible so。

You can read this if you want， I think people have oh there's the source for randomization where were you earlier Okay so there's the slide if you wanted it from earlier。

 it basically says randomized the source for as well total guessing is now two to the 32 there are other ways to increase entropy as well like adding a random letters okay so where were you earlier so this is the kinsky slide I think we wanted to clean it up and come up with better slides instead of just one because it's such a strange topic so I'll try to talk through it I think I might have draft of new slides somewhere if you want to like experimentally stare at them but here's what I want to like get across basically I'll try to kind of wing it sorry so we already know that there is a race condition in place whether you are on path or you are off path there's a race that has to happen which is。

The recursive resolver makes a query and then the attacker would like to inject their answer and make it get their first before the real answer gets there so let's think about what the winning case and the losing case look like so if we're thinking about offpath attackers because those are the people we're trying to defend against right on path and man in the middle we're kind of screw anyways or whatever but the offpath attacker what is their like winning scenario right the offpath attacker wins if they get their answer there first their answer gets there first and they guess the ID number and possibly other stuff correctly so two things have to happen for the attacker to win they need to guess the ID number and they have to get the answer to show up those are two show up first win the race so in order to win overall and get your cash poisoning through and poison the resolverss cash you need to a。

Get the answer there first win the race B guess the ID number correctly two things have to happen if you win like if the attacker wins the cash is poisoned and this resolver is totally screwed however。

 what about the lost case think about what happens if they lose and by loss what do we mean it means either they lose the race so the real answer got there first and their answer gets ignored or they got there first but they guess the wrong I those are the two losing cases right and so if either losing case happens think about what happens Well in both cases。

 the attacker's answer is rejected， the real answer is accepted and what happens now。

 the real answer gets cached and if the real answer gets cached。

 what does that mean it means that the recursive resolver for the next like week they're just gonna look in the cash anytime they want to know the I address and the attacker doesn't get to race again So it's like no more racing and guessing for you you got one shot you lost。

The recursive resolver now gets to keep that record in their cache for know a week or however long the time to live is and the next time you get to race is a week later and so the idea was that and the thing that made most people kind of comfortable with numbers that were small like two to the 16 and two to the 32 was basically this idea which is well yeah two to the 16 to 65000 it's kind of small but maybe it's okay because if the attacker guesses and they lose they have to wait a week to try again so I guess the thing I'm trying to convince to you is that precommminky before this guy came along we all agree that if you win the race you poison the cash as the attacker but if the attacker loses the race they are locked out from trying again it's like a timeout they have to wait for the cash record to expire before the resolver is gonna make this request again and then they can race again to try and poison the cash with the answer。

Okay hopefully we all agree that that's the thing okay and so that's the problem or that's the thing that makes the attackers's life hard and so for almost everybody for basically many。

 many years， everyone was like well 65000 is small but it's okay because of this idea except there was one person for whom the 65000 was not really satisfactory that was our friend Dan Kainsky I think it was Dan Dan Kaminsky and so his idea the key of it I think the slide is I don't know。

 I guess maybe if it makes sense it does but the key idea that I want you to take away from this slide and it was like a lot of different words but the key idea that I think is super important is right here which is that instead of racing by using domains that are real where if you win the race you poison the cash if you lose the race the real answer gets cash and you can't try again for another week Dan Kaminsky is a key innovation that I think is really important on this slide is what。

If instead of the victim making requests to real domains。

 the victim made a bunch of requests to fake domains like these I don't know about you。

 I don't think any of these are real now let's think about again the win in the loss cases if you win against one of these racists what can you do well the attacker sorry the victim makes a request and says what is the IP address of fake1goo co the real answer is doesn't exist forget about it's there's no actual answer but if the attacker wins they can inject these two records they can say well I think give you kind of whatever they want but the key is that the answer can contain this why can the answer contain this like what licenses the fake spoof response to contain this record it is the fact that well if you think about who's answering this query probably someone from Google some Google name server is answering this query and so even though the original question was fake go co。

glecom name server can answer with this Google co IP address and mapping right seems reasonable And so there are kind of like I think two things here that really make the Kainsky attack work so one of them is that we're gonna to start asking for fake records instead of real ones and when I ask for a fake record the win case changes a little bit so in the original case if I wanted to win I just send a spoof response with a bad answer this case when I want to win I send a spoof response but I give the answer not of the fake domain because I don't care about poisoning the fake domain I care about poisoning the real domain and I put that in the additional section and it's okay because we know the additional section gets cached just like any other section and we also know that this query is getting answered by a Google name server a Google expert and so the Google expert should also be able to answer for this so paleic checking is not going to stop this particular attack That's the win case。

O。So the character of the wind case changed originally in the win case someone asked for are you win case okay originally in the win case the recursive resolver asks whats the IP address of Googlecom the Google name server gives the IP address of Google。

com and then or the true name server wants to give the answer。

 the attacker spoofs the wrong answer of the exact question that the recursive resolver asked but the win case is changed now when the Kainsky attack because in the kinsky attack。

 the recursive resolver asks hey what's the IP address of fake。

goglecom a thing that doesn't actually exist and then the answer that comes back from the attacker can contain the IP address of Google or www。

google。com and why is that okay that's okay because the recursive resolver or sorry the name server should be an expert at Google and therefore should also be able to answer this Google query I realized I have three0's is not Google Google。

Thanks。So the wind answer changes a little bit or the case where the attacker wins changes a little bit because you are now。

Ther is sending out fake queries and the attacker is sending back a different answer than what the recursive resolvesolr asked for。

 but it will still be accepted because there's an additional record。Okay。

That's the win character So what makes this seem so powerful Like the thing that really makes this powerful and the second piece of the puzzle is the lose case What happens if you lose the race right before we already know the original precominsky era if you lose the race you're locked up for a week the real answer gets cached but what about in this case guess I'll bring back okay what about in this case imagine if you lose this answer doesn't get there first or the I in there is wrong。

 what happens if you lose the real answer gets there what is the real answer say the real answer says fake one go co is not a real thing okay maybe that gets cached maybe it doesn't do I care not really because I was never concerned with the fake I addresss in the first place I was always concerned with the ultimate target of www。

 Google that's what I want to poison and so the fake answer the true response going back for fake1。

go co does not stop me from trying to attack。Yeah。Right so I am no longer block that for a week while the true answer gets cached because nothing useful gets cached the most useful thing that gets cached is fake one is not a real IP or a real domain okay I don't care that was not the thing I wanted to poison and so the lose case no longer has that property that en locks the attacker up for a week while the record is cached now the attacker can try again the attacker can say well the next time the recursive resolver asks for fake two well nothing is cached so I'm still gonna have to make this new query and if I win then everything is good at poison www。

 go's IP address if I lose fake two is now not a real thing okay whatever I'll wait for fake three I'll wait for a fake three query and then race again and so。

The takeaway of the punchline is that we have gone from racing once per week and if you lose you have to wait a week to come back and try again to racing as much as you like within a time frame as long as the victim continues making all these queries I can keep racing over and over again as fast as I possibly can until I win and so it goes from once per week to unlimited tries as long as the victim keys making these requests and that is what makes 65000 go from probably good enough to a very scaryarily small number and so final thing before I take questions is how do you make the victim make all these queries because maybe the average victim is not going to be sitting there typing in all these things into their browser。

 all these state queries so one extra thing you would need to make the Kaminky attack work is you'd have to trick the victim into making all these DNS requests but from the web unit。

 maybe we're already convinced that that's doable for example。

 go on a form use all these image tags and now the browser。

has to go find the IP address of all these things make all those DNS requests there's lots of different ways to do it。

 but kind of the key here is that one extra thing you need to unlock the Ka attack and make it work is you have you need to have the victim make all these requests and we've already seen the attacker forcing the victim to make some requests is a doable thing。

Okay。Did can answer your question？Awesome， okay， I thought ahead of you for once students with like future questions for once。

 okay。So that's the Kainsky attack I am not going to lie。

 It is probably one of the more confusing things in this class and you might have to step through it a couple times but the two things that I think really make it work are one you are now asking for fake domains instead of real domains right and so this unlocks the property that if you lose the race either by guessing the wrong I or by losing the race condition if you lose as the attacker it's okay the attacker can try again because no useful information got cacheed and so the next time the victim queries for fake two fake three fake four all of those queries will actually be made as actual DNS queries as opposed to just looking in the cache and that allows the off that the attacker to continue racing to their heart's content until they win one so that's the first thing that really makes this work is by asking for fake queries you go from if you lose the real thing gets cash you're screwed you can't guess again for another week if you lose nothing useful gets cash you can just try again right away and then the second。

That really unlocks this is that if you ask for a fakeone。google。com mapping。

 you're probably going to be asking someone who is a Googleogle。

com expert and so it is okay under bailliic checking that's a really weird circle it's okay under bailliic checking to return this。

Record with www。gogle so even though the victim was never asking for the IP address of www。

gogle it's still okay for the attacker to include this in the smooth response and it would still be accepted by the end user because you're probably asking a Google。

com name server expert Okay I'll take quick questions then I have one more slide to show you i'm done yes。

Yes。你不在那边你该，但是不知。25个。Yeah， it's a great question。Yeah that's a great question I guess I should spend a minute talking about it and so the question was when I go down that chain。

 doesn't the Google docom name server get cached and that's true but something really important is the Google docom name server is someone whose whole existence is answering Googlecom queries the Google docom name server is not www。

google。com they're two different people the www。google。

com is the web server who you would ask for like jaqua than HTMLml the Google docom name server who probably has a completely different domain name is the person answering the DNS queries so that's a key distinction people always mess it up so invite brought don't know。

Okay yeah great question so basically the Googlecom name server is not the same as the www。go。

com web server they are different people Okay I talked about Soforce I'm not gonna to talk about it again one possible defense against Kaminsky records that people have tried is don't catch the glue records so if something shows up in the additional section don't trust it right away do another DNS check just to make sure it's good so it costs you a little bit of time but might help you stop Kaminsky attacks and so if you get a glue record in the additional section do another query just to double check your work and that can possibly help you stop some kinsky attacks。

 but ultimately the Kaminsky attack is a fundamental problem to DNS there's no way to magically solve it unfortunately it's a fact of life the best you can do is try to use glue validation try to use sourcefor randomization to make the 65000 number into like 4 billion and that's kind of the best you can do unfortunately if you would like to be evil and make money。

DNS that's what you should do but don't actually do it because it's not legal here's your summary so we talked about the high levelvel idea yout know ask someone else we talked about the message structure every record has a data type and gets sorted into one of the more sections and then we talked about the cache poisoning attacks I think the strangest one that really deviates from kind of like classy TCP style attacks is the kinky attacks and the idea is that you query fake domains because that way if you lose the race nothing useful gets cached and secondly。

In the fake query you can still inject answers to real records or you can still inject a real record or a real answer to the query that you really care about because you're still asking someone who's responsible for answering Googleo。

com queries okay that's it so I hope you found the Kainsky attack you know somewhat comprehensible I know it's one of those things that are kind of confusing if you beg me hard enough。



![](img/9a1fa253799891e5cfcc3e5468b19cf7_3.png)