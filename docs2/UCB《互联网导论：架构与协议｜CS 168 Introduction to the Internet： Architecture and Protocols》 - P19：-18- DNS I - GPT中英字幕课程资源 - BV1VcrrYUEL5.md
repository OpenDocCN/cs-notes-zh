# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P19：-18- DNS I - GPT中英字幕课程资源 - BV1VcrrYUEL5

But let's get started。So as usual， I wanted to start with a little note about today。

 March 17 in CS history， 31 years ago today John Bacchus passed away at 82 years old and he was a computer scientist of some note。

 he was a winner of the National Science Medal and the ACM Turing Award and various other awards。

 he led the team that developed Forttm， which was the first really widely used programming language。

Also， if you've taken a compilers class， you no doubt learn BNF as a way to describe context free grammars。

 and he's the B in BNF。And since this is a networking class。

 it's worth noting that parts of many of the protocols that we use are defined using BNF。

 for example， the specification for HTTP， the protocol underlying the web uses it heavily。

 here is how dates are represented in HTTP in BNF form。So not a bad legacy。Back to 168。

 let's take a quick look at sort of where we are in the course。

 we started out by talking about some foundations and principles behind the internet and those were things like packet switching and end to end principle。

We talked about the domain structure of the internet and routing within and between those domains。

Then we've done a pretty deep dive on IP and TCP。 We've looked at what those packets are actually composed of at L3 and L4。

 We've looked at the actual bits on the wire and what they're for。

And we've seen how to make an unreliable network act like a reliable one。

And all that is sort of you know establishing foundations and today we start at least a couple of lectures that start to have a bit more focus on the user。

😊，And specifically。We're going to start by talking about the domain name system or DNS as part of our remote learning。

 the plan is to break up the DNS material into a number of separate videos which we'll post individually and then we'll have some online interactions starting with Piazza and online office hours and we'll kind of see where things go from there。

So here's the outline for all of the DNS related videos。

We're going to start out with sort of an overview of the ideas and how name lookup works at a very high level。

And then we'll get into some of the details that support DNS's core mission we'll talk a bit about the API that you can use to interact with it。

 about the servers that support it and about the protocol itself。

We'll talk about the two most important types of information in DNS， the A and MS records。

And then we'll talk a bit about how domain names are actually created。

The next video will then go much broader and look at other use cases for DNS than its core one and the various record types involved。

Then we will have a little case study that looks at how Minecraft uses DNS to solve a real world problem。

Then we'll discuss availability， scalability， and performance of DNS。

And we will finish off our discussion of DNS with some musings on the subject of DNS sort of from a skeptical standpoint。

So with that， I'll conclude this introduction and you can move on to the overview。

So thinking back to the early internet， the three killer apps were basically remote terminal that is from a local machine you could log into a machine somewhere else。

 This is like SSH is today at the time it was a protocol called Tnet and you could do Tnet and then the remote host address。

File transfer pretty self explanatory， you did it with a command called FTP。

 which used the file transfer protocol and so on the command line you could do FTP and then the remote host address。

And then email where you want to send or receive messages to or from a user on a remote machine and you can do that using the command mail。

And， you know， numerical host addresses were not very nice for humans。 You know。

 nobody wanted to type tnet 46。0。0。10， for example。But that's all we've talked about so far。

 these numeric addresses。So the solution was to create an address book of host names and their addresses and this was maintained by Elizabeth Jocelyn Jake Feinler at the Network Information Center at S SRI of course being one of the first two nodes of the sort of nation Internet so if you wanted to host name then you phoned Jake Feinler and she'd enter it in a database that she kept and originally this was a human readable file basically。

 it looked something like this at the beginning of 1974 there were 85 or so hosts and I want you to take a look at the addresses and noticed that they are not IP addresses。

 they're really just a single byte。Also want to point out that UC Berkeley is here with address 98。

 and I think these lists were basically sent out as pretty much part of a newsletter。

So eventually this sort of transitioned to a standardized machine readable format commonly known as hosttt textex。

 and so everyone periodically used FTP to fetch host dot text from the neck。

So in 1983 the standardized hosts textext file looked something like this。

 there were now 480 hosts or so， I haven't shown them all here。

 but notice that they now have IP addresses and so there were a whole bunch of these 10 ones which are ones that had been migrated from the earlier ARPet addresses。

Again， notice that UC Berkeley is here。But at this point， Berkeley also had its own whole network。

 this 46 network。Notice that this is a Class A network。

 this is like a/lash A that's a lot of address space by 1986。

 they no longer had 46 and instead had transitioned to 128。

32 which is a Class B network and Berkeley actually still has this slash 16 team。

So with this host file， you could type Tnett UCBVX， for example。

 and UCBVX got looked up in the hosts file and it opened a connection to 46。0。0。10。

 the corresponding address， and this is a whole lot nicer than having to type in and remember the addresses yourself。

However， this arrangement was still not ideal。First of all。

 it was sort of an increasing amount of work for Jake Feinler and our team。

It was also an increasing amount of data transfer， you know。

 as the network grows as you get more hosts， first of all， the file size increases。😊，But secondly。

 the number of hosts fetching it increases。And the frequency with which you need to fetch it in order to remain up to date increases。

And so like in the absolute best case， this is like quadratic and there were starting to be a lot more hosts。

 you know， the early internet had been sort of characterized by like a few mini computers hooked up together。

 but we were entering sort of the age of the workstation and computer here and so there were suddenly being a lot of hosts that wanted to get on the internet。

😊，You've also got this problem where longer transfers are more likely to fail。

 and so you may end up with partial host files until you download the updated version a few days later。

So in short， you know， the centralized administration was becoming to be burdensome and it was clear that it was going to be even more so in the future。

And it was also sort of， you know， this centralized mixcentric focus was sort of counter to the sort of open and decentralized path that the internet was on。

And also the centralized distribution of the increasingly large file was also looking like bad news。

So DNS or the domain name system was developed to confront the problems being faced here。

 was developed by Paul Maccapets in 1983， and he was actually sort of given the task of pulling together several different proposals for such a system into a final one。

He kind of just developed his own one instead and without much change。

 that's the one that we still use today。So what are the goals of this system？Well， first of all。

 the primary purpose is to map from human friendly names to IP addresses。While it does this。

 it needs to be able to deal with scale， there are going to be lots of hosts and names。

 they probably didn't foresee this at the time， but today there are about 360 million domain names。

There's also going to be a lot of lookups， a lot of people who want to map a name to an address。

And there's going to be a lot of updates， we don't want to have a bottleneck like having to make a phone call to the N in order to add a new domain name。

We also want the system to be highly available， we don't want a single point of failure， for example。

 in the old scheme， if the NIC FDP server went down。

 then you wouldn't have any way to get an updated hosts。text pile。

And we want the system to perform well because， you know。

 lots of communication is going to start with a name lookup。

So how do you solve problems like these Well， we do it the same way we solve many similar problems in computer science。

 which is with hierarchy， or in this case， with three intertwined hierarchies。

So the first hierarchy is that the names themselves form a hierarchy。

You can take any node and just sort of trace it up towards the root and you get a name note that intermediate nodes make valid names too。

 for example e。berkeley。edu is a valid name you don't need to go all the way down to the leaf。

Secondly， authority is hierarchical。You have this way of sort of delegating authority， for example。

 EU cause， which is I believe a nonprofit is sort of responsible for all doedduu domains。

But then Berkeley is responsible forberkeley。edu domains。And finally。

 the infrastructure itself forms a hierarchy， you know the infrastructure is not just a single server that knows all the names。

 it's a hierarchy of name servers which all know about parts of the hierarchy。So for example， a。

educerers。net is a name server that knows about the name servers for alledu domains。Ans1。berkeley。

edu is a name server that knows about various stuff below Bkeley。edu。

And Es has its own name server ns。e。berkeley， which knows about stuff at or below e。berkeley。edu。

And note that like ADNs1。berkeley doesn't know anything about this stuff that NSs。mountholyoke knows。

So looking at the bigger picture here， we start with a root which I didn't put in the previous diagrams。

 and so the DNS root is controlled by ICN。Below that we have these top levelvel domains or TLDs and there's a whole bunch of them and these are controlled by various different organizations。

 like I mentionededduu is controlled by EucAuse， Verigncontrols。netin。

com there are these country code ones for all the countries and those are controlled by some organization that's part of that country and so on and so on and so there's about 1。

500 top levelvel domains today。And below that， we have all the other domains which are controlled by many。

 many different organizations。

![](img/3304b4151077cb72377f243d2cfbd7ae_1.png)

So we have this concept of a zone and so a zone corresponds to an administrative authority responsible for a contiguous portion of the hierarchy。

 for example， the name server ans1。berkeley。edu is responsible for bekeley。edu and pink。icechool。

berkeley。edu and www。berkeley。edu but then Bkeley has delegated the authority for es and below to a different name server so a different name server serves riseise。

e。berkeley and。😊，This means that you kind of have a choice about whether and where you want to delegate authority of children。

 and it basically means that ES doesn't need to coordinate with like main campus IT in order to make domain names for Es machines。

Okay， so how do lookups actually work？ Well， we've got this iterative resolution process where basically we start with the root name server。

We ask it for the name we want。If it has an answer， then we're done。Otherwise。

 it'll direct us to the next name server that we should ask。

And then we just repeat this process until we actually get the answer we want。So let's do an example。

 let's look up or resolve repo。es。berkeley。edu。So we ask the root server rootservvers。net for repo。s。

Now it's not going to know the answer to that， but because it's a root server。

 it knows all the top level domain name servers， and so it's going to tell us to ask one of those responsible foredu domains。

So we ask a dot。EDuservverers。net for repo。s and。It doesn't know either， but it knows about bekeley。

edu and so it knows a name server that we should ask， and so we ask that name server anS1。berkeley。

edu。And it doesn't know either， but it knows that we should ask ns。e。berkeley。edu。So we ask Ns。ex。

And it actually tells us the answer that we're looking for。So this may be kind of obvious。

 but I wanted to make a little side note we already walked through how the domains are broken down into top levelvel domains and so on。

 but that was really talking about the names themselves but there's also this sort of parallel hierarchy for the infrastructure too。

 the actual name servers and so people often classify the name servers by which part of the hierarchy they're in。

So at the top， the root server knows about top level domain servers。

And then we have top level domain servers which know about that particular top level domain。

 like there are servers that know about doedu， like Berkeley。edu and Mountholyoke。edu。

But they don't know anything about like es。berkeley。edu。And then we have authoritative servers。

 and these are ones that actually like do the named IP mapping。

 they know about the stuff that's in their zone。Okay， so back to the lookup process here。

This has raised three important questions。And so the first one is who actually does this multi step lookup process？

And originally， back in the '80s， it was likely that a host did this directly。

 that is the host would query the root server， get the response back。

 query the top level domain server， then query the authoritative servers。

 and eventually get the answer。Today， things work a little bit differently。

We usually have what's called a resolving name server。And so basically， the host queries it。

And then it makes the same sort of you know iterative queries that the host would have made in the past。

 and then it returns the result back to the host。And so this is called a recursive query。

And these are the same non recursive or iterative queries that we've had the whole time。

So to go on a little rant here。You know， I've never liked the name recursive。 you know。

 if it were a recursive query， I would think everybody would do the same thing。

 So like the host would query this server， which would query this one。

 which would query this one and this one in this one。

 and then the replies would go back the same way。And then you would have gotten the response and I mean。

 this works logically， but practically speaking， this doesn't actually end up happening because these servers along the bottom generally don't support recursive queries。

 you know， like recursive queries take them more work and they're all really busy and in particular。

 like the root servers don't support recursive queries。

You know you could also imagine some scenario like this。

 maybe the Berkeley name servers for whatever reason had been configured to support recursive queries and so you could imagine that you might get some sort of combination where you've got a recursive query here and you've got iterative queries here and then you've got another recursive query here and so I mean again this works logically but practically speaking this never happens。

 you always get sort of that first scenario basically where the。😊，The resolving server。

 which is generally provided by your ISP， like in this case， a Comcast server。

 is the one that's responsible for doing all their iterative queries。So。

Just to finish up my rank here， I really think this should be called a delegated query right because if it's you know just this one sort of delegated query and then it's all iterative queries after that。

 the name recursive just doesn't make sense to me。Okay， rant over。So。

When a server gets request for a normal non recursive query。If the server knows the answer。

 then it returns it， right？If it doesn't， then it returns a reference for the next server to query。

When a server gets a request for a recursive query。Then if the server knows the answer again。

 it returns it。And in theory， it could perform a recursive query on the next server。

But it's more likely that this server does the iterative process itself。

 and so that would be know truly recursive， this one would be not really recursive。😊。

And it's even more likely that it's still going to return an error saying that it doesn't support recursion。

Because usually it's only these specialized resolving servers that actually support recursive queries。

Like I said， these servers are often provided by your ISP and they generally aren't authoritative for any domain。

 you know they don't have specific named IP mappings that they're responsible for。

 they're really only used for lookups。So going back to you know our sort of classification of types of DNS server。

 we could add you know， the resolving DNS servers， though it's worth noting really。

 these aren't really part of the hierarchy in the same way as the other ones are。

And so that answers our first question of who actually does the lookup process， a host can do it。

 but it probably delegates it to a resolving DNS server， and so that leads to our second question。

 which is how do I know the address of my resolving DNS server？



![](img/3304b4151077cb72377f243d2cfbd7ae_3.png)

And one possibility is that you do it manually。More likely possibility is that use DHCP or the dynamic host configuration protocol。

 which we're going to talk about in a future lecture。😊。

But I do want to point out that you can have more than one name server， you know。

 depending on the OS and the configuration， it may cycle through them all or it may switch to a later one if an earlier one fails or something like that。



![](img/3304b4151077cb72377f243d2cfbd7ae_5.png)

Okay， so this could be manual， but it's probably through DHCP。

And so that leads us to our third question， which is how does anyone know the address of the root DNS server？

But before I get into that， I have to come clean about a little fib I've been making。

I've been talking pretty much like there's one root name server and like Berkeley had one name server and so on。

And I want to point out that this is actually。Already somewhat resistant or rather resilient to failure。

 You know， Berkeley's name server could code down and that wouldn't affect UCLA， for example。

But actually， everyZone always has at least two name servers， replicas of each other。😊。

There's no real reason why this has to be true for like some strong technical or theoretical reason。

 it's really just true because the IETF said so and people follow what they say。Um， so， you know。

 the main Berkeley Zone has at least these three u name servers， ADNS，1，2， and three。

Eduu has 13 name servers， at least you know a。edjuservverers。net and b。edjuservers。net and so on。

And the root also has 13。 It actually has more and we'll come back to this later。Okay。

 so how does anyone know the address of a root DNS server？嗯。So you we know that it's named a。

rootservvers。net or B。rootservs。net and so on，Where do look that up to actually find its IP address。

 right， we've got like a bit of a chicken and egg problem here。

And so there are multiple ways that you might do this。

 but a pretty decent solution isn't too complicated and is generally how it's done and basically the program that does the name resolution ships with the root server IP addresses like hard coded or in a configuration file that were current when the program was shipped。

And basically the program tries to query each of those preconfigured addresses until it finds one that works and then it asks for an up to date list and this is called a primine query。

 and this works as long as at least one of the preconfigured ones still works。So。

How does one know the address of a DNS rootot server， preconfigured addresses。

 which are then used to get updated ones through the process of priming？

So a final note on lookup is remember that host textext file from the preDNS world。

It actually still exists on systems today， but there's usually not much in it。

 but you could put things in it if you wanted to， for example。

 override how a particular domain name gets resolved。So continuing our discussion of DNS。

 I thought we should get into some of the details and so we'll talk some about the APIs。

 we'll talk about the servers， we'll talk about the DNS protocol itself。

 and then we will finish up by talking about how a domain is born。All right。

 so the usual API functions。Our GiHost by name， which you does pass a domain name and you get a result back which you can use to get the address This is really old。

 it's been deprecated for many years， I think maybe like almost 20 years it's super common in real code anyway it's really big drawback and the reason that it's been deprecated for so long is really because it only supports IP4 it doesn't support IPV6。

So its replacement more or less is this function get ater In。

 you can pass it the name and then it has a couple other parameters which you don't necessarily need to pass in and then you pass in a pointer to a value that gets the result。

So this is modern， it's not limited to IP4。And。Both of these are available in both。

 you know like the C libraries on Uni like systems and on Windows。

 and they're also both available in the Python Socket module。嗯。Usually the implementations of these。

Don't know how to make iterative queries， they only know how to make that first query to a resolving DNS server。

So talking a little bit about servers， the gold standard DNS server。

 which I think is also far and away the most popular one is a server called Bd and Bd was also actually the first DNS server written for UniX and it was written by four Berkeley grad students in 1983。

 like the same year as the DNS RFC was written and so there's a paper from back then by its original authors about bindd。

So it stands for Berkeley Internet name domain Ser。

 I always thought this was a super awkward name like why not call it Berkeley Internet name Demon？

So side note。Demons， some of you may already know this， but for those of you that don't。

 many network server processes are called demons。 Sometimes it's pronounced Damon。

 both seem to be pretty well accepted， you know， the main program of bind， for example。

 is called name D。 that's not named， it's named demonmon。 and you know if you're familiar with SSH。

 the SSH server is usually called SSHD。嗯。You know， this isn't strictly just for network servers。

It's really just processes that are sometimes referred to as background or noninactive processes so that's sort of misleading you know like a name server is certainly interactive。

 you know you send it requests and it sends you replies。

 but you it's not generally run or used like directly from the command line as part of like an interactive session。

So sort of roughly， and this is sort of a vague term， a demon is a server process。

 they're generally long lived and they're generally communicated with through some sort of an inter processcess communication or network mechanism。

😊，The equivalent programs in the Windows world are generally just called services。So why， why demon？

And this goes back。To， you know， thought experiments， at least as far back as Descartes。

 And so he did this thought experiment that had this demon， this entity。

 which was basically working tirelessly to deceive you about like the nature of the world about reality and。

😊，So Maxwell's demon is one that was used in a thought experiment in physics。

 and it was maybe this one which was actually the direct inspiration for demons in computing Maxwell's demon sortded molecules in such a way as to defeat the second law of thermodynamics。

And so you know， really in a thought experiment， it's it's just some entity that has some particular job that just keeps doing and so you know I think in computing the analogy is really just that like this entity kind of works in the background to do some ongoing task。

😊，So given that it was Berkeley students that wroteBnd and Berkeley has been involved in DNS since the very beginning。

 perhaps it should not be too surprising。The Berkeley。

edu is actually the oldest eduu domain on the internet。All right。

 so let's talk a little bit about the DNS protocol。It is a client server design。嗯。

The client is often a user host but it could be another server like in the case of recursive queries。

 right， it's like that second server that's actually acting as a client for the Romanian servers。

So the client ends a query。The server sends a response。

So the server typically listens on the well known UDP port， port 53。And so。

We spent a lot of time talking about TCP， and so why UDP， why is UDP the right fit for DNS？

And so one answer is that it saves an RTT for the TCP connection establishment， right？😊，Also。

 you know， TCP requires servers to keep state per connection and there are potentially lots of connections。

 especially like think about like the root servers。And you know， just in general。

 there's no real need for that sort of ordered stream abstraction that you get with TCP， you know。

 like for these quick queries and responses， like a single packet is often just fine。

And so you may be saying but like wait， UDP isn't reliable。

 so what if packets are dropped and basically DNS deals with that just with this sort of simple timeout and retry mechanism。

 it varies from OS to OS it can be fairly slow， some OSs are much more clever like if you have multiple DNS servers setup up。

 it will you know like when it retries， it will send it to both of them and you know to try to maximize its chances of getting a reply quickly others are not nearly so clever so again it really just sort of varies system to system。

😊，But it can be fairly slow like it can be on the order of like seconds if a packet gets dropped。

 but you know， you have to keep in mind like your DNS resolving server is often provided by your ISP。

 so it's generally pretty close to you and you know you're generally pretty well provisioned for that。

So you know， the chances of losing a packet between you and that resolving server are pretty low。

And later， we'll kind of see why that's often good enough。So some DNS servers also use TCP port 53。嗯。

It's not usually used for normal queries， it's primarily used for what are called zone transfers。

 which is when you're replicating the name database and you know kind of the notion there is that you this is much more data than like a normal query right if you're copying the entire database you know and with this larger amount of data。

 the threeway handshake likely becomes negligible and sort of the reliability and ordering that TCP provides you becomes important for doing these big transfers。

😊，We'll talk some more later about some additional variants of the protocol。

So all messages share the same basic format， the messages can be either a query。Or a response。

 and this is determined by a QR bit in the header。Quries can also theoretically be of several different types。

 there's the IQu， but this was obsoleted in 2002。😊。

The RF that obsllated had this note that Iquery has not been generally implemented and has usually been operationally disabled where it has been implemented。

 so not extremely successful。Theres also the status type， which was never really defined。

 there was a proposed standard in 2001， which you nobody got around to trying to define until 18 years after DNS was defined and this proposal was not even accepted。

And so it's really just this query type， which is used for basically everything。

 so we're kind of going to just ignore the different types of queries。😊。

There's also a bit in the header that determines whether recursion is desired。

 it's how you express that you want a server to do a recursive lookup。

If you're interested in more details in the actual protocol。

 you can either see the text or look at the RFCs。So the actual data that's stored and transferred in DNS is held in resource records and resource records are basically a tuple。

And the first value in the tuple。Is the type and there are many different types of records and if you remember that the primary goal of DNS is to map human friendlyendly names to IP addresses。

 we need two types of records to do that and the first one are A records。

 which are address records and the second one is NS records which are records telling about another name server we'll talk about some more types later。

The name field of the Tupple is basically just the name associated with the record， for example。

 in A records， this is the host name of interest like www。google。com。

The value is the value associated with the record for a records。

 this is the IP4 address associated with the name。The TTL is how long in seconds this record is valid for。

When I write out tus going forward， I may omit this value。And then there's the class。

 And basically the idea here is that DNS can actually be used to store。

 you know information for different types of networks besides just the internet。

 And so the class specifies which network type you're talking about。

 I don't think this was ever actually used very much。

 So class is almost always equals Internet in this particular class it will always be that。

 So I'm just going ignore it moving forward。😊，So let's do another example this time with the actual protocol in mind。

 and this is actually based on a real query that I did by hand。

So we start by querying a root server requesting the a record for ischool。berkeley。edu。

 we want to know its IP address。And the server。Sends back this NS record。And of course。

 this is not what we asked for。But it's basically its way of saying。

 I don't know the answer to what you want， but here's a name server that knows something about domain names ending in dot Eddu。

So。😊，Now we know about this other name server to ask。The server also sends back an A record for k。

edduservs。net this is in the same packet。And it didn't really need to do this。 We didn't ask for it。

 but it's useful， right， Like assuming that we want to continue with our query。

 we may well need this I address。This may have been our next query anyway if it hadn't included the answer already。

So this is called an additional record。Also， I only wrote one NSS record here。

 but in the same packet， it also returned a bunch of other name servers in random order。

 And so that way I can try other ones if the first one doesn't work or something and if every client starts by just asking the first one that it gets。

 then the load will get kind of spread evenly across them。

So next we're going to query that new name server that we found out about k。educ servers。

 requesting the A record for ischool。 Berkeley I Iu。And。

That name server is going to send us back this NS record and again this isn't what we asked for。

 but you know basically it's saying here's a name server that knows about things ending in Berkeley。

edu。And again， it's also going to return an a record for that new server so that we know the IP address of that server。

Which we're going to use to query it， asking it the same question， we want the a record for ischool。

berkeley。eddu。And so this name server is actually authoritative for ischool。berkeley。And so。

It sends back the A record。Including the IP address， which of course， is what we wanted。

I didn't draw it up in this tuple originally， but it also includes the TTL。

 and in this case it sends 10，800， which is three hours and so that's basically telling us we can use this IP address record for three hours。

So that's how a lookup really works at the protocol level。Moving on。

I thought we should talk about how a DNS domain name gets created in the first place。And。So。

You can imagine maybe you just created a company， example industries。

 and you get a block of IP addresses from your ISP， like maybe 192。0。2。0， and it's a/lash25。

And so you go and register example。com with a registrar and the biggest registrar。

 I think by a pretty large margin is one called GoDaddy。

 and this is an organization that ICN has delegated domain registration process to。

And so registeringexle。com probably costs you less than like $15 a year。

 actually you can't register example。com。😊，It has been sort of set aside to use for examples in networking things。

 but in theory， you register domain it costs you about $15 a year。

And then you run two authoritative name servers for your domain or you have someone run them for you。

 I believe GoDaddy actually offers this as a service that you can pay for。

 even like cheap web hosting plans will generally serve as your name servers for you。

And you give the addresses of your name servers to the registrar。

The registrar inserts a pair of records for those into the TLD name servers and those are things like an NS record that says for this domain。

 this is the name server that you should use and then an A record telling what the actual IP address for that name server is so it would do that for both or however many replicas you have。

And then you put resource records in your name servers， for example， put an a record for www。example。

com and you know this costs you like basically nothing to create like as many subdomains as you want。

 it's your own server， you can just put in whatever records you want。

So now what if I want my own top level domain， you know what if I want my email address to be Murphy at awesome cs168 And to do that。

 you talk to Ican you can get your own top level domain like CS 168 for about 185000 So kind of expensive in comparison but people do this if we look at the number of topleve domains over time。

 when they started selling more of them， you know， originally they just had you know like calm and gov and then all the country code ones and so on。

 but they started letting people sort of buy those top level ones and you can see when that happened。

 there was sort of an explosion of people buying them though it's kind of leveled off over the last few years。

So up until now， we've looked at the most essential aspect of DNS。

 which is resolving host names and IP addresses。In this segment。

 we'll look at some other use cases for DNS and dig into some of the record types that facilitate those。



![](img/3304b4151077cb72377f243d2cfbd7ae_7.png)

So to start out with， you might have multiple A records that have the same name。So。

Here you can see that I'm using this tool calledDig， which does DNS queries。

And when I query for yahoo。com， I actually get back a handful of A records and every time I do it。

 they come back shuffled。

![](img/3304b4151077cb72377f243d2cfbd7ae_9.png)

This allows a sort of coarse grainin load spreading。

 Yahoo is running multiple servers all serving their web page and different users get a different list from the name server and so if they just contact the first one。

 then different users get sent to different servers。

This can also be used as a simple resiliency method， for example。

 if Google Chrome gets multiple A records and the first one doesn't work。

 it'll try the next one and so on。You may have noticed that everything we've looked at so far has been focused on IP4 addresses for IP6。



![](img/3304b4151077cb72377f243d2cfbd7ae_11.png)

You just use the AAAA record type instead of the A record type and so here you can see I used digig to look up the A record for Google and got an IP4 address and then I looked up the AAAA record and got an IP6 address。



![](img/3304b4151077cb72377f243d2cfbd7ae_13.png)

Now， another thing I might want to know is assuming you've got an IP address doesn't have a host name associated with it and what is that？

And this is facilitated by pointer records。And so the value stored in these records is the host name。

The name part is a little bit trickier。 the the one that you actually look up。

 And so basically it's the dot quad IP address listed backwards。 So if I want to look up 138，1101200。

Then I start with 2001，110， 138。And then， I append。Dot iader。tarpa。

And so here you can see I've done a query using dig for this IP address and I put pointer at the end of the query to say that I want pointer records and you can see that this particular IP address is associated with NSs。

matholyoke。edduu， which is Mattholyoke's name server。There's a similar mechanism for IP version 6。

 where instead of adding inader。ArRPpa， you're add IP6。ArRPpa。



![](img/3304b4151077cb72377f243d2cfbd7ae_15.png)

We talked about how you can have multiple IP addresses associated with the same name by having multiple A records and you can actually do sort of the opposite where you have multiple names associated with the same A records or actually what's really happening is that you map from one name to a canonical name and so essentially this is just creating aliases of a name and this is done with the C name record type。

So here you can see aqua I ran using digig for www。berkeley。edu。And what I got back is this。

 and you can see here that it's a Cname record， and basically what this is saying is that www。

berkeley。edu on the left should actually refer to this really long name on the right。

And notice that the canonical name is actually an Amazon Web Services host name。

 so I guess we can conclude that Berkeley uses AWS to serve its main web page。

Now the next thing that you'd probably be interested in knowing is what the IP address for that AWS host name is。

 and it turns out that the server actually included it as an additional record and included the A record in the response and that's what this head on the command line is about I trimmed it off。

So while the C name record type always maps to a single name。

 there's this similar record type called a D name which maps like a whole part of the DNS tree to another part of the DNS tree。

 so for example， if you try to look up something like blah。food。com， it'll resolve it to blah。bar。

com instead。

![](img/3304b4151077cb72377f243d2cfbd7ae_17.png)

So another interesting use case for DNS is email。 you know， if you send an email to Murphy@berkeley。

edduu， I end up reading it on Google docom right And this is the same for all of you too。

 right since Berkeley outsources its email to Google So like how and why does this happen， I mean。

 how does it get to Google， if anything based on what we just saw。

 you'd think maybe it would get to Amazon。😊，Even in the past。

 it was really common to have a separate email server called something like mail。berkeley。edu。

 for example， but nobody wants to type an address for an email to like Murphy@mail。berkeley。edu。

And so the way that this works is that when email servers are delivering mail。

 they look up an MX or mail exchanger record for the recipient domain。

 and this basically tells the mail servers to use that domain name instead。

 so if you look at Berkeley's MX records， it actually has several and they all point to some Google machine。

Another interesting type of record is the text record originally these were meant for like human readable information。

 but I don't think they were ever really used very much for that。More recently。

 they've been used for sort of a grab bag of things。

 but a pretty important one is for doing what's called site verification。

So if we look at some of Berkeley's text records， you'll see several which mentioned verification。

 and the idea here is basically that some company like Adobe or Zoom or Google or Facebook gives you some magic value and you put that in a text record on your domain。

And then that proves that you have control over the domain because not just anybody should be able to modify your domain's DNS records。

The other company then unlocks capabilities for you regarding your domain， for example。

 Google has this feature called search consolesole。

 and it'll let you see how often sites that you control show up in search results。And Facebook。

 you know how like when you share a link， it creates a preview with a title and a screenshot。

If you're the owner of the site being linked to， then you can edit how those previews show up。

 but other people can't。The last record that I'll mention is the serve record we already looked at the MX record which was this sort of like special purpose redirection used for email。

 but what about other services besides email instead of having like every service need its own special record type we have serve records。

😊，And。So what you do is if you want to connect to some service。

 then you look up this specially formatted name where basically it starts with an underscore and then the service name。

And then it has an underscore followed by the transport protocol name like_ TCP。

And then it has the host name where you want to look up the service。The values for these records。

Have a target host name to use instead of the one you looked up。

 similar to how we saw the MX record gave a different host name than the one we looked up for email。

And the value also has a port number to use to contact the service。

 and this means we don't need to set aside a specific well known port for every service and we don't always need to use the same one。

 it can be looked up dynamically。So notice that it's like really easy to create more services。

 you just need to add a record with the appropriate name。

 you don't need to define a whole new record type and try to get it standardized or anything。

There's another video where I dig into how and why serve records are used in Minecraft。



![](img/3304b4151077cb72377f243d2cfbd7ae_19.png)

And so putting aside record types for now， there's a million different ones and we could go on about them all day。

But let's talk about a sort of conceptual capability of DNS。

 that is we've been talking about a lot of specific things that DNS does。

 but I want to take a little step back and look sort of at a way that it's used and that's as sort of a general indirect layer。

So starting with a really simple example， you might imagine you have some website and it maps to some address that was given to you by your provider。

But imagine that you switch providers and in order to not break aggregation。

 your new provider gives you a new address from their prefix。😊。

And if users were using these addresses directly， this would be a real pain， right。

 they'd need to like change all their bookmarks or remember a new address to type in or something。

 but with DNS， all you need to do is update the A record for www。example。

com to the new IP address and like most users will probably never even notice。

And we can actually put this indirect mechanism to even more clever use。 for example。

 maybe you run a company that provides video streaming and you have three servers with different IP addresses across the country。

😊，But you could use the same name for all three of those servers。

And then we add a little brains to our DNS server。So when the server gets a request for that name instead of just returning all 3 a records in shuffled order like we saw earlier for Yahoo。

 we could try to be a bit clever So in the request。

 you know the IP address of the requester shows up in there and we can use what's called a GeI database which is essentially a mapping from IP address to their actual physical location。

 these aren't 100% accurate， but they usually get you within the area。

And so we could have the DNS server return the A records ordered by which ones appear to be closest rather than just a shuffled order。

That's a pretty simplified version of this technique and doing it well actually requires some subtlety。

 but this is like one of the underlying ideas behind a big business called content delivery networks and there are lots of variations of this。

 for example the smart DNS server may actively monitor server performance and direct clients to the least loaded ones instead of the physically closest ones。

And so to sum up this segment， we've looked at a lot of things DNS can do。

 we've seen how having multiple A records for the same name can spread load across servers and provide some resiliency。

We've seen how DNS accommodates IP6。We've seen the mechanism by which DNS lets you map from an IP to a name instead of the usual way around。

We've seen how we can have one name as an alias for another using Cname records。

 we looked at how DNS relates to email。And we saw how site verification features are tied to DNS text records。

And we glanced at a sort of general name to service mapping mechanism using serve records。

And finally， we've looked at using DNS as a useful indirection layer in general。Okay。

 so I thought we'd do a little case study on DNS serve records in Minecraft。So as a reminder。

 we looked at MX records which provide an indirection specifically for email when you send an email to the addressfo@example。

com， the mail server looks up on MX record on examplele。

com to figure out the actual email server where it should be sent since the mail server probably isn't running directly on example。

com itself。And that works great for email but doesn't help us with other services。

 so rather than have a special record type for every possible service。

 the Ser record was developed which can be used for lots of services。😊。

In addition to a host name redirection like MX does。

 the Ser record also lets you specify the port to connect to。

So let's look at how this is used to solve a specific problem。

So I imagine I don't need to tell you this， but Minecraft is a popular open world video game。

 and users can run their own server， which normally listens on TCP port 25565。Inside the game。

 a player can enter the address of a server to connect to， and this can be an IP address。

 but as we saw earlier， it's pretty cheap and easy to get a nice domain name and people like to get ones that are memorable or funny。

It's also the case that lots of people want their own Minecraft server。

 but they don't want to actually run it themselves。

 they don't want to use their home internet connection and their home computer or pay for an expensive dedicated server in a data center or whatever。

 and so they pay a game hosting service to do it for them。

And these hosting companies often want to run multiple games on the same physical server since it probably doesn't take an entire machine to just host a few players。

But if the server only has one IP address， all these nice host names people registered would all resolve to the same address。

 and this means you need to run the different games on different TCP ports。

 not the default Minecraft port number。So now other players would need to enter the domain name plus the port number。

 which is not nearly so nice if you're going to have an arbitrary string of numbers in there you might as well just be using the IP address probably。

So a hosting company could assign many different Is to the same physical server。

 which would solve this problem， you'd register your own host name and then create an A record pointing at one of those Is and you'd be done。

But IP4 addresses are a fairly precious commodity these days， so that's not really a great solution。

And so the succinct problem statement here is that we want to run games that all have nice host names。

 but they all need to be able to refer to the same IP address with different ports。

And serve records store exactly the necessary information。

 you create a serve record where the name is created by concatenating the service name and the transport protocol and your nice domain name。

And then the value in the record tells you the target server name and port number to connect to。

The Minecraft code does exactly this for you automatically。So。😊，Let's do an example。

 let's consider two Minecraft servers，0hub。dk and capy。pw。



![](img/3304b4151077cb72377f243d2cfbd7ae_21.png)

And so I'll start by looking each of their A records up with Dig。

And we can see that this one actually has two A records。

And next I'll try actually connecting to the IP addresses in the A records。

 I'm using a command line Minecraft client here instead of the actual game。

And so this is just using the default Mincraft port number。

 and we can see that the first one doesn't work。I have I look at the second one。

It doesn't work either， fails in a different way， but they both fail。

And so next I'll look up their serve records and again I create this special name where I put an underscore and the service name Minecraft。

 and then I underscore and the transport protocol， which is TCP for Minecraft。

And then the host name that I'm interested in。And here's the Ser record。

 it's got the TCP port and domain name where the server is actually running。

So I'll use this other tool calledHos to look up the IP address。

 it's really similar to digig but has slightly more user friendly output。

And so here we see that the server is actually running at 8899-151100。

I' look up the other Ser record for0hub。dk。And again。

 we see the port number and the target domain name and。In this case。

 this is kind of illuminating because infrequent group is a Danish Minecraft hosting service。

And again， I'll use hostst to look up the IP address。



![](img/3304b4151077cb72377f243d2cfbd7ae_23.png)

the first thing to notice here is it says there's an alias， so this is a C name。

And if we look at the A record， we'll notice that it's the exact same IP address as the other server。

 so they're running on the same physical machine， but different ports。

And so now we can try connecting to one of these servers using the port number。And it works。

 And so here's one of them。 And then we can kill that。

 Let's try connecting to the other one using its port number 2，5，5，7，3。And that works too。

 we get a different welcome message presumably in Danish because it's a different game。And again。

 the actual Minecraft game does all this for you automatically。So to tie this all up。

 this works by aquaium for a serve record that contains the name of the service that you're interested in。

And the record that you get back tells you the host and port to actually connect to。

And it's really easy to support different services， you just create more serve records。

And so that's it for today， we will pick up talking about availability。

 scalability and performance on Thursday。

![](img/3304b4151077cb72377f243d2cfbd7ae_25.png)