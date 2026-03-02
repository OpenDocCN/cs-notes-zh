# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P13：-13-Lecture 13_ Scalability and Availability - GPT中英字幕课程资源 - BV1D142147he

Welcome to week 7。 We are flying and there's only three and a half weeks left。

 This is what I keep telling myself every night。 I'm like just stay alive three and a half more weeks and then Arman and I have to grade everything from the quarter。

 So Some quick logistics Project1 is due tonight if you have any last minute questions。

 let us know on slack and we'd love to help you the week six exercises we' just released last night and they will be due next Tuesday So a week from today and this will probably be the last set of exercises。

 these ones are focused on channels since you really don't get any experience with channels in 110 you can use channels on the last project if you want to。

 but if you don't end up using them we just wanted you to get some small experience with them So these exercise there's only one problem。

 It's pretty small。 will be harder than last weeks。

 but it should take less time than all of the other weekly exercises。😊。

Then project two is coming out at the end of this week。

 not exactly sure when yet probably like Friday or Saturday。

 and that will be due at the very end of the quarter。

 so you'll have at least two and a half weeks to work on this project and it is going to be focusing on implementing a load balancer。

 which is something that we'll introduce today。As always。

 let us know if we can help if you have any questions。

 if you're having a really rough week and you need an extension。

 just let us know and we're here to support you。So this week。

 we're taking a step back and a step up actually。 So we're not going to be looking at much code this week。

 we're going to be thinking about design and architecture in the context of networking So what does safety look like when you start thinking about large systems that involve many high level components。

 We've been talking about safety at a very low level so far this quarter looking at like buffer overflows and error handling and a lot of things in code。

 but we're going to try to take this discussion a little level up and look at things from a bird's eye view of like how do we design network systems that are safe。

😊，How do you keep big systems running when when any piece of them could fail at any time。

 How do you deliver robustness in systems that need to stay alive。

 How do you keep information secure。 That'll be the topic of Thursday。

 And in preparing for these lectures， I felt kind of bums because there's just so much important stuff to talk about that I feel like people graduate with a Cs degree and then they go out and they feel qualified to build systems when and then very。

 very commonly people will make the same mistakes over and over again。

 And these are critical mistakes that endanger the information and sometimes lives of many people。

 So there's a lot of material here。 we're only gonna to be able to skim the surface。

 But we've kind of picked the parts that we feel are most important for you to get exposure to。😊。



![](img/c365a7f7139844c5800b2f1635777b35_1.png)

All right， so before we can really talk about。Networking at a high level， like systems design。

 We need to make sure that everyone's on the same page with some some networking basics。

 So if you don't understand all of the stuff that I'm about to talk about in detail， that is fine。

 we're not gonna be talking about any code and you don't need to you don't need to understand most of this 100%。

 the last project is going to involve implementing something from these slides。

 but we'll walk you through the process and it'll be fine。

 So don't feel stressed if if you don't feel like you understand all of the details。

 but please do stop me if you're like， I don't understand what he's talking about。

 I want to make sure that you understand some of。The concrete details of what is happening so that when we talk about abstract things。

 you have a sense of what's going on。Alright， so let's start with IP addresses what is an IP address Every computer on a network has an IP address that uniquely identifies it and an IP address is4 bytes it's 4 number 0 to 255 separated by periods。

 so 192。168。1。230 is a valid IP address 400。500。1。230 is not a valid IP address because 400500 don't fit within a single byte。

If you want to talk to a computer on a network。You need to know its IP address。

 That's how you specify the computer that you want to talk to you give its address。

How do you find an I address， Really， like anytime you want to contact any computer on a network。

 you need to know its IP address。 If you want to go to Google com， you need to know its IP address。

 I don't know Google's IP address。 It's it's too hard to remember。

 And so the way that we deal with this。Is your computer is sometimes hard coded with an address of a server known as a DNS server。

My zoom thing is blocking this。 Yeah， and， and that could be hard coded and。

When you want to reach Google do co， what you do is you you talk to the DNS server whose address you know。

 So you already know how to get there。 For example， there's a DNS server called 8。8。8。8。

 That's a very easy address to remember that。 I can remember that。 So you ask 8。8。8。8。 Hey。

 what is the I address for Google do co and and the server will respond And if you want to run DNS queries They're called on your own computer。

 There's a program called digig which does a DNS lookup。

So you can see you can put it in a domain name and say， hey， what is the IP address for。

 for this host name？So to give you a visual picture of what's happening， if I want to go to Google。

com， I send a request to this IP address that I already know and I say， hey。

 what's the IP address for this website and it will respond by saying well。

 Google is at this IP address and then I can go talk to Google and I can say， hey。

 can you give me the Google。com homepage and itll respond with with whatever HTML code I need in order to render Google's homepage。

Everyone could so far， does make sense？All right， so。When we talk about networking。

 you'll often hear these things called port numbers and I find that this is a very confusing topic for people who are understanding networking for the first time。

 so the analogy that I usually give in order to make port numbers make sense is imagine that every computer on the internet is an apartment complex。

So we've got a bunch of computers on the internet and each of them have an address。

 so each computer has an IP address just like each apartment complex has a street address。

And there are things inside of these apartments like an apartment complex isn't just one address。

 there are many apartment apartment units within the complex。

And so in order to specify those to address those， we have this notion of a port number。

 which corresponds to a unit number for the apartment。So if you want to go to web。tanford。edu。

 what do you do， use dns to find web。tanford。eddu's IP address。

 then you go to that apartment complex and then you knock on the door for the apartment that runs the http service。

 which is port 80 for HttP if you want SS into My。tananford。edu。What do you do。

 you use DNS to find the IP address， you go to that apartment complex。

 and then you knock on the apartment that runs the SSH service port which is 22。

 And if you're wondering like where are these numbers coming from。

Do they mean anything Do they correspond anything and the answer is no。

 somebody just arbitrarily pick these numbers， but they are de facto associated with these particular services。

 if you want to get the SSH server running on a particular computer you knock on door 22。

 that's just what you do。 It doesn't have to be 22 if you wanted to run your own SSH server you could pick a different apartment if you wanted to。

 but then anybody connecting to your SS server would need to know which apartment to go to in order to find you。

 This is just a standard so that if we go to 171。67。2 and 5。200 and we want to SS agent into it。

 we just know because it's a standard that a I need to go to apartment number 22。

ThatThat's just how it works like if you want to sign the lease， you go to the leasing office。

But if you wanted to change things around， you totally could。

 it's just that anybody connecting to your server would need to know that aha the leasing office is actually in the garage or like wherever unconventional place you wanted to put it。

Does this make sense to everyone？My Zoom videos have disappeared， there we go。

I need to figure out how to position this thing so it doesn't block my slides。Okay， so。

Let's talk about how these connections work under the hood。

 like I mentioned this thing about sending a request and getting a response。

 what does that actually look like under the hood？So again。

 an apartment complex is or a host is like an apartment complex and a host， by the way。

 if I use the term host and that's confusing a host is just a computer。

 those terms are interchangeable hosts is just a term that gets used in the networking world a lot。

So each host is going to have one or more processes running on it， right？

So let's say that we have this PID 12，3，4 that's running on this host。

And right now we we don't have any network services running on this computer。

 So let's say that we want to set one up。 We want to create a network service that is able to receive requests from other computers on the Internet。

The first thing that you need to do is you need to pick an apartment to move into so like I was mentioning before。

 if you were wanting to run an HtTP server， you would want to pick apartment 80 just because that's the standard。

 if you were running an SSH server， you'd want to pick A 22 but you pick an apartment and then you set up shop and you move into that apartment。

So in in 110， I think next week， we'll talk about like what are the actual system calls that move into an apartment。

 But for now， we'll just call this whole process binding to a port。

 This is what binding to a port entails。 These are the steps。

In addition to setting up shop in an apartment， you also install a waiting list outside the apartment and whenever anybody tries to come to this apartment。

 they'll sign up on this waiting list and they'll say，" hey。

 like I would like to enter this apartment， here's my name on this waiting list and then when that way if you get flash mobs with like a thousand people trying to connect you can go down the list and invite them in one by one at whatever rate you're able to handle。

So this waiting list is attached to a file descriptor so that the process can see when somebody arrives and when you see this in 1-10 this also feels very intuitive。

 This is called the accept socket if you have seen this already in 1-10 if you haven't don't worry about it but people are like what is this accept socket like like what is this doing really it's just a file descriptor that's connected to the waiting list so you can see who has arrived at your apartment if you try reading from this file descriptor you can't actually call the cis call read on it you have to call this other cis call called accept but if you try reading from this file descriptor it will block until somebody joins the waiting list until somebody signs up and then you know somebodys outside the door。

 somebody's trying to connect to my server。You can also have other processes bind to other ports。

 so if I have another process on this computer， it can bind to a different port。

 it can move into a different apartment and install a waiting list outside of that apartment。

But you can't have two processes bound to the same port。Only one application per apartment。

If you wanted to， you could also have process bind to multiple ports。

 so this is very common in web servers a web server will very commonly bind to both port 80 and port 443 port 80 is for HtTP and port 443 is for HtTPS just by convention so if you wanted to run a server that is able to handle both HTTP and HTPS it's very common to do this where you can bind to multiple ports。

 but again you can't have two processes bind to the same port。Everyone， good so far。

 thumbs up thumbs down。I see some stuff in the chat， but I can't really see it。

 so if you have a question you can just unmute yourself and interrupt。

So what does the process look like for exchanging messages on a network。

 this is how you set up a server， but like if you have two computers that want to talk。

 how does that actually look？So let's say that we have a server that is bound to a particular port on a particular IP and on some other machine。

 some other computer， somewhere else across the internet， maybe on the other side of the world。

 we don't really know on some other computer， we want to talk to this server， this first computer。

So what do we do？First， the client is going to try to find the server。

 If you specify an invalid address that doesn't exist on the internet， you won't be able to find it。

 but if you can find it， the client sort of walks over in metaphorical terms。

And it registers itself on the waiting list if it finds this destination and it finds a waiting list。

 it could be the case that say， for example， in this picture。

 say that youre trying to connect to port 22 on the server。

 The client might walk out and it might try to establish a connection and then it's like， hey。

 there's no waiting list here nobody's here on this apartment it's completely vacant and in that case it will go home and you'll get an error on the client that says like Econ refuse or something like that。

But if it does find a waiting list there， it will add itself to the waiting list and remember the server is reading from a particular file descriptor that's connected to that waiting list so it will see that hey。

 somebody just added themselves to this file of sorts。

And it will take the client off the waiting list。😊。

And then it creates a new file descriptor that is connected to the client this is called a socket。

 don't be intimidated by the terminology， it's just a file descriptor that's connected to the client。

 but it is a bidirectional file descriptor， so I'll come back to that in a moment。

The client having been successful in being invited into this apartment is going to go back and the client is also going to create a file descriptor that it can use to talk to the server。

 So both of these hosts have a new file descriptor now and you'll notice in the open file table this is a read writeite file descriptor So you can both read to it and write to it unlike pipes where you can only really send direction in one way。

 if you send direction if you send information in two directions。

 the information will get jumbled up and it won't be useful if you want to have two directional communication with pipes。

 you need two pipes。 but with these network sockets。

 it's just one file descriptor that you can both read from and write to。

And if the client writes to its file descriptor 3。That message with like whatever string of bytes it writes will be sent through the network to the server's file descriptor number4。

 and if the server reads from that file descriptor。

 it will read this sequence of bytes that the client wrote and similarly if the server writes the file descriptor4。

 that will be readable on the client's file descriptor 3。Does this make sense to people？

Any questions about how this is working because I think。If this feels vague or ambiguous。

 I want to stop and talk about it now because some of the higher level stuff may not make sense if you don't understand like。

What is happening under the hood when we talk about networking？Awesome question。

 like what exactly is happening with these green and red lines？The answer is it's really complicated。

 I just had a midterm before this class。In for CS244。

 which is like a networking research papers class， and I can confirm it's really complicated。

Did not do too hot on that exam yeah so we'll talk a little bit about that towards the end of this lecture。

 but you'll get can I'm also happy to talk about it after class。

 but if you are interested in this take CS144 CS144 spends an entire class talking about what is actually happening in between these two servers。

😊，The answer is that a lot of this complexity is abstracted away and so you end up with this file descriptive abstraction that you could just write to and read from and it works really。

 really great。 and that is the level of understanding that you need for this class。

 That is the level of understanding that you need in order to use networking practically。

But there is a lot of complexity that's hidden away。Any other questions？Yeah， sure。Great question。

 Yes， they can both read and write at the same time if if they wanted to。

 so both of them could be writing at the same time。

 and that's why I kind of drew this as like a separate green and red line。

 it's kind of creating two separate communication channels over the network that just get aggregated into a single file descriptor So if a server is writing that kind of goes over one half of the channel。

 And then if the client is writing that goes over the other half of this internet pipe。

 but they are kept separate。All right， oops， it's going to play my animations again， that's great。

All right， so we're going to。Take a step back and think about network design here up until this point。

 this is the material that you learn in 110， but we're going to talk a little bit about how do you design systems on top of this and we're going to talk about two properties today。

 The first one is called scalability。

![](img/c365a7f7139844c5800b2f1635777b35_3.png)

And what does scalability mean， Scalability refers to a system's ability to grow as demands increase over time。

So if you have an unscalable system， it's not going to grow very well。

 it would be pretty nice if let's say that you have a system that is capable of supporting 100 users and you want to be able to support 200 users。

It would be nice if you could just double your resource to say that you're using one server。

 if you could now use two servers for that。 That would be awesome。 That's very scalable。

 That's linearly scalable。 if you want to get like 10 x， the number of users。

 you just add 10 more servers。 That's pretty good。 Even better would be subline。

 So like let's say that you wanted to support 10x， the number of users If you only had to double the number of servers that would be incredible So that's subline scaling。

 but unfortunately， a lot of systems don't scale like that。 And in fact， some systems。

 no matter how much money you throw at them。 they won't scale at all。

 like the maximum number of people that you can support is 1000 or whatever it is or the maximum number。

 the maximum amount of data that you can process at a time is like1 gigab per second。

 there's some limit on how big you can scale and that's an uns scalable system。😊。

So we want our systems to be able to scale， obviously， we also want them to be available。

 availabilityability says how well is a system able to stay online and avoid downtime？

Does it stay available？And as you scale a system。This becomes very difficult。

 I wouldn't say these two properties are at odds， but they do conflict with each other sometimes because as you make a system more scalable。

 oftentimes it will become more complex， which makes it more difficult to stay available。

And just to emphasize how hard this is， let's say that you have a server that is available 99。

99% of the time。So over the course of an entire year。

 that server would only be down for less than an hour per year。 that's pretty good。

 That's not bad at all。 If you have a server that's 99。990% available， that's not bad。

But if you try to create a system using1 thousand of those servers and you aren't careful to engineer that system for fault tolerance。

So what that means is that every one of those  a thousand00 servers is necessary in order for the system to work if that's true and the server failures are random。

Then your system will only be available。When all of those servers are available and the probability of that happening。

 it will only be available 90。48% of the time if I did the math right。Which is not good at all。

 that means that you're down for many days of the year。And， and so some， this is， this is not okay。

 And we need to be able to build systems that if they involve multiple servers。

They need to make sure that they can account for a server failure。Does this make sense to everyone？

Alright， so， yeah， there are many more properties of networked and distributed systems that we won't talk about today。

 but these will be the two main focuses。So this is how this is just a little diagram of how。

A simple server would work on the Internet。 You have some client， and。

The client looks up the server's IP address， and then it opens a network connection。

 so does the thing where it creates a file descriptor and like goes out over the network and and signs up on the waiting list of the server and whatnot。

So connect to the server's IP over the network， the client and server each create a file thescriptor to talk to each other and life is good。

So。Wops。Is this a scalable setup？Why or why not？Yes， we only have one server in this picture。Oh。

 I'm sorry。 I I misunderstood。 So it's not one server for every client。

 I didn't do a good job of showing this in the diagrams before。

 but you can have multiple clients connect to a server。

 So if you have five people that like sign up on the little waiting list the server can read five times from that waiting list and it can create five new file descriptors to talk to to those five clients。

 and it can do that in parallel if you want， it's easiest for it to be in serial， serial， whatever。

 but。B。It's almost universal that you use threads with servers， so for example。

 you'll see this a lot in CS110 over the next few weeks where you assign one thread for each client that's connected。

 It's a very common model。Yeah， the internet is definitely scalable。

 but let's say that with this setup right now， you have a server that is able to handle a thousand people at a time。

So 1 thousand00 people can be connected to this server at any one point in time。

 maybe this is a video streaming server， so like you're streaming video to 1000 people and everything is working great and then let's say that your startup starts to take off and now we want to be able to handle 2000 people streaming at the same time。

What would we need to do。Given this architecture， in order to be able to support 2000 people at the same time。

 if our server is only able to comfortably handle 1000 people。Awesome， you're thinking ahead。

You're absolutely right。 in the grand scheme of things， we'd probably want to add another server。

 but let's say that we our code is just designed for one server。 We only want to have one server。

 how do we do this？ Well， the answer is you upgrade your server。

 like get a more powerful machine if you have a machine that can handle 1000 people and you want to be able to handle double the capacity。

 Well， just double your the number of like cores in your machine and double the amount of memory。

Does that sound good？Why might that not be great for us？Great point。 So so it could be a waste。

 In practice， a lot of servers are rented。 They're at least from companies like Amazon and Microsoft。

 if you ever heard of Amazon AWs， that's like the most common。

 It's called cloud infrastructure where you just borrow some capacity that Amazon runs a huge server farm with tons of servers and you could just borrow some of their servers if you need to So you could say。

 okay， I'm gonna to rent this， I don't need it anymore I'vegrown it。 you can take it back。

 but can you give me a bigger one。 So that ends up not being too big of a problem。

 but there is still a really big problem with with saying。

 let's just double the number of cores and double the amount of memory。😊，That's exactly right。 Like。

 find me a computer that has 20000 cores in it because you imagine trying to scale like Netflix capacity with one server。

 It's just too much demand。 And really， this comes down to individual computers aren't scalable。

 It becomes much more expensive as you try to upgrade performance。

 Like the jump from2 to4 cores might not be that big。

 but the jump from 16 to 32 cores is quite a bit more expensive。

 and it would be much cheaper if we could just use two machines with with commodity performance。

 like normal performance。 It's a bunch of like quad corere machines rather than one machine with 64 cores。

 It's going to be extremely expensive。 And in fact， Internet traffic has grown so fast。

 you can't even find a single machine that can handle handle it。 Like I mentioned。

 there is no one machine in on this planet that can handle the amount of traffic that Netflix gets。

 Hard can't keep up even if our wallets could。😊，And this comes down to what Ben was saying at the beginning that really you don't want to scale up your machine。

 you want to scale out instead of having bigger machines。

 you want to have more machines of the same size， This is one of the philosophies that Google followed very early on。

 I don't know if you know this， but the Google the original like computers that powered the Google search engine were just like really crappy commodity computers that were stacked together with Legos。

They were not like your enterprise grade servers。 they were really crappy machines。

 but they did a very good job of scaling out using crappy machines rather than depending on single very expensive machines And the other thing that Drew just mentioned is this is not available either like it introduces a single point of failure and you can have a server that crashes that like runs out of resources it could fail。

 the dog could eat the power cable like who knows what could happen。

It's not good to have such a single point of failure。

 So really what we want to do is we want to distribute our system。

 We don't want to just run it on one machine。 We want to distribute over a large number of servers so that we can get scalability and availability。

These servers will need to talk to each other so they'll need to use networking to collaborate on whatever problem it is that we need to solve。

So how can we split this functionality across multiple servers， Like we want to add another server。

 but it's not quite so simple as just。Duplicating our existing setup。

And the reason for this is if you think about what these servers are actually doing。

 if you have an extremely simple service， you might be able to just add another machine and call it a day。

 but most services need to store state， they need to store data like who is currently logged in what emails does a user have。

 how many times has somebody loaded a particular page。

 there's some state associated with what you're doing and then there's of course the logic of what you're doing maybe you need to like process a particular image or compress some uploaded video or just serve some like take read some bytes from disk and send it to the file descriptor that goes across the network。

Whatever it is you need to do， there's some logic associated with that。

 So we can't just duplicate the servers because then our data is going to be split across the two servers。

 And like one server might think that user X is logged in and the other server might think that they're not logged in or one server might have most of the emails。

 but not all of them and then the other server might have the rest of the emails。

 We need some way to rectify this。 And it's actually a very hard problem。

 But it's one that most people don't need to deal with because。There is existing database software。

 for example， some common ones are MysqL Postgres， Redis。

 Mongodb I don't know if you've heard these terms before， if you haven't doesn't matter。

 but these are database frameworks that have already solved this issue of being able to scale so they come with functionality where you can shard them across multiple servers。

 sharding is the term for like splitting up the data across multiple servers for redundancy so that if one of the servers fails。

 you don't lose the data and also for performance so that if you're getting a ton of requests you can distribute some of that load across multiple servers。

 if you want to know how this is implemented， it's very interesting but you can take CS245 or 244b that talk about databases and distributed systems。

Hey Ryan real quick there's a question in the chat I think Courtney wanted to ask well I think I'm going to like reinterpret the question a little bit because I think your question was more about like what like isn't there a limit to how many how long the waiting list can be for a single computer and if you consolidated one single computer to be the gateway for all the other servers what would that look like and how would you get around that issue is that is that a fair interpretation of your question Courtney。

Great question， I'm going to come to that in a moment。You're also thinking ahead。So。

We can solve this data issue by delegating it to databases and it's pretty interesting how these work if you want to be a very large scale service like Google。

 for example， you need to implement your own databases Google spends a lot of effort building distributed systems for data storage and there have been many new databases that have come out of their engineering efforts because the existing ones didn't work for the amount of users and the amount of traffic that they have to handle but for most people you can just use one of these commercial existing databases。

Which means that we're just left with stateless logic and compute and because it's stateless。

 it's very easy to replicate across multiple servers， you can just have multiple server here。

But there's still a problem。Which is that we're trying to have multiple servers。

 but only one IP address。Like Googlegle。com resolves to a single IP address。

 how do we distribute that across multiple computers？One thing you can do。

 which I think is what Courtney was getting at is you can actually introduce a new computer here whose sole purpose is to take incoming connections and distribute them across your computes servers。

 which do the actual application logic。And。So when a client opens a connection to this IP address。

 it hits the load balancer and then the load balancer selects one of the compute nodes to distribute the request to。

If the client sends a message， then the load balancer just replicates that message and sends it to the compute node。

 and then if the compute node responds， then the load balancer just relays that message back to the client。

There's a variety of ways that you can select which node to relay to， but for our purposes。

 let's just say it just randomly picks one and that's the strategy that you'll implement in Project two。

It， it doesn't do anything else。 There isn't a whole lot of like。Of heavy work that it needs to do。

 all it's doing is just reading from this waiting list as soon as somebody connects。

 it takes them off the waiting list and opens a connection to them。And and then it。

 it like forwards any messages。 So it it it's doing a lot of networking traffic。

 but there's not much compute that needs to happen here。

 And it's not like reading any data from disk or anything。So as a result。

 they can handle a very large number of concurrent connections。

And to answer your question about the waiting list， yes， the waiting list is bounded。

 The clipboard on the front of the door can eventually run out of space。

 but if you're continually pulling people off the waiting list very， very fast。

Then the waiting list usually doesn't end up being a problem。

quick question though like wouldn't one possible solution be to like save things to disk if that overflows or is that just considered horribly efficient thats it's not possible because the waiting list is actually implemented inside of the Linux kernel and it needs to be very fast and the kernel has no option to save the waiting list to disk。

But usually it it's not an issue as long as your computer still has some resources。

 you can still be pulling people off the waiting list and into some in memoryory queue。

If your queue is so long that you need to save it to disk， you have bigger problems。

So this helps a lot。 It helps a lot with scalability。 There's a technique called auto scalinging。

 which is you can just look at the current load on your network。

 And I mentioned that many of these these things work in least data centers you can just borrow more servers if you need to。

 And in fact， these systems are so efficient， you can just borrow nodes on the fly like you can write a program that if your compute nodes get too overwhelmed。

 you can just ask Amazon like hey， can you give me another instance and within like five minutes。

 they'll give you a new rented server that you can use and log into and set up So it's very fast and very efficient And if there are more clients connecting。

 we can just add more compute nodes so we can just borrow another server from Amazon。😊。

Or from whatever post we're dealing with。And then we can update our load balancer and the load balancer will distribute the load to this new node as well。

 It also helps a lot with availability。 So if one of these nodes fails。

 the load balancer can detect that hey， this node isn't working anymore and it can stop sending traffic there so it will only distribute traffic amongst the nodes that it node are working well。

And this is beautiful because the client is just sending requests to this one IP address。

It has no idea that there's all this complexity happening inside of our infrastructure。

 We might have 1000 compute nodes， but we don't have to expose 1000 IP addresses and if we like if we're having a really rough day and we need to add more servers。

 we can just add more servers and update our load balance so the client doesn't need to know about it。

Does this make sense to people？Are we done yet？Go ahead and ask them。嗯。Yes， it definitely should。

 It definitely should。 That's the typo。So is this good enough？

Have we solved our scalability and availability issues？Yeah， for sure。

 So that's an availability issue。 if， I mean， our load balancer now introduces a single point of failure。

 So if it goes down， we're in trouble。There's also a scalability issue。

 like every connection is a file descriptor。What happens if you run out of file descriptors。

 it turns out you can have a very， very large number of file descriptors on a system。

 but at some point you can still run out if this is a single machine and you have tons and tons of connections barreling through at some point you're going to use all your CPU resources and you won't be able to scale anymore。



![](img/c365a7f7139844c5800b2f1635777b35_5.png)

And really， we need to find some way to load balance our load balancers because this has only deferred the problem。

We have managed to come up with a way to divide our traffic across a bunch of machines。

 but now it's just spread out a bit and if we scale， at some point。

 eventually we're going to hit the limits of our load balancer and we're going to have to figure out some way to deal with that。

So we've only put off the problem in some sense。

![](img/c365a7f7139844c5800b2f1635777b35_7.png)

Yeah， so we can't use just a single load balancer like YouTube right now during coronavirus。

 YouTube is accounting for 0 15% of all internet traffic。

 There's absolutely no way that you can find a single machine that is able to handle that much traffic。

 It doesn't matter if the machine doesn't have to do anything fancy with compute It just can't handle that much traffic。

And then again， you have a single point of failure。This is worth mentioning。

Like in large scale systems， anything that can go wrong absolutely will go wrong。

 If you have a race condition in your code， it will hit that race condition。

 If there's a possibility for， for machine failure， like hard drive failure。

 network interface failure， CPU failure， fire， like。

Network links that work half the time and not the other half。

 absolutely anything can go wrong in large scale systems。

 and so you need to be prepared for the worst。So one solution for load balancing load balancers is to use a technique called round Robbin DNS。

 and I kind of implied that DNS returns one IP address for a given host name。

 but it turns out you can list as many as you want if you want to list 10 IP addresses as you can。

And what you can do is you can implement the DNS server that returns a list of IP addresses。

 shuffling the order every time so the order is randomized and then when a client receives a list of IP addresses。

 it will try connecting you to the first one if that doesn't work it will try the second one that doesn't work itll try the third one and so forth。

So you can specify multiple load balancers， potentially in different data centers。

 and the clients will get these and it will just go down the list one by one until it finds one that works。

So Reddit actually does this， if you look up the IP addresses for Reddit， it returns me for。

 and then I tried it again a bit later and I got the same addresses， but in a different order。

So this ordering is important because it distributes the load。

 somebody else is going to get a different order than me。

 and so the first load balancer they try will be a different load balancer。

And that helps for load balancing the load。Makes sense。There are some downsides。

 and so many people don't rely on this technique because it's not very intelligent。

If you have a load balancer that is getting hammered more than others。

 it would be nice if we could direct traffic away from that load balancer， but with DNS。

 it's returning a random list of IP addresses， it's not too smart。

Also DNS infrastructure has a whole lot of caching， I haven't talked about how DNS actually works。

 I think we'll talk about it a little bit in CS110。

 but there are many DNS servers along a particular path and you might ask one DNS server which asks another DNS server and then cache is the response so that when you get it you didn't actually communicate with the origin DNS server。

 you just got a cached copy of the response and so as a result it's hard to consistently rotate the order of the IP addresses because a DNS server will give some response of four IP addresses in some order and then that address gets saved in some cache somewhere and then now anybody who's reading that cache is going to get the same order instead of a randomized order and so they're going to hit the first IP on that list harder than the other Is。

So it's hard to distribute load evenly and then maybe the biggest problem is this is really not good for failover if one of the servers on that list fails。

 DNS is going to have no idea the DNS server will just keep happily announcing its IP address and the clients will try to connect to it eventually they will succeed because they're going to give up on that IP address and they'll move down to a different IP address on the list。

 but they're going to spend some time first trying to contact the dead one and so this will increase the latency to establish a connection。

嗯。And you have to ask yourself， like， what is going on if I try looking up Google and there's only one I address。

 Like definitely Google is not using this technique because they're only listing one I address。

 but there's absolutely no way that Google could be using a single load balancer。

 Google is just too big to be able to do this。So there must be something else happening in this picture。

Round Rob and DNS can't be it。And this is actually another DNS hack。

 so this website is a pretty useful website for checking what DNS returns in different parts of the world。

And if I look up Google。com。Apparently， it's banned in Brazil。 I didn't know that， but。

In all these other places， you'll notice that it is resolving to different IP addresses。

 which is very interesting and very unusual because most smaller scale websites don't need to do this。

 but what's happening here is Google actually has many。

 many data centers distributed across the world。And the DNS servers can respond with the IP address for the load balancer that is closest。

To the client。 So say that I'm somebody in Chicago and I send a request to Google's DNS server saying。

 hey， can you give me the I address for Google do com。Google's DNS server will say， oh， hey。

 I have a client that is connecting from Chicago。 I'm going to return to them the IP address for the load balancer in Google's Chicago data center。

And what that means is。When you try to connect to Google。com， you get a server that is closer to you。

 which helps to decrease latency。 you don't have to go all the way across the world in order to get to Google data center。

 you just go to the one that's a couple hundred miles。

 less than a couple hundred miles away and it also helps to distribute traffic because instead of everybody in the world going to one data center they're being spread out across multiple data centers that Google operates。

It doesn't fix availability。So what happens if I'm in San Francisco and the San Francisco data Center goes down？

I'm getting routed to an IP address in San Francisco， but if that data center goes down。

 then does Google go down for everybody in San Francisco， everybody in California？

That seems suboptimal。 It seems like even if a data center fails。

 we still want Google to be available。Does that make sense？So this is my last。Bit here for。嗯。

Availability， there are many more tricks that people pull out of the bag in order to make services available。

 but I just wanted to give you a high level overview of what's happening。

 And this one actually starts to get fairly into the weeds。

 So the way that I've been talking about IP addresses。

 I said IP addresses identify a single computer on a network。 and usually that is the case。

 when we talk about IP addresses， that's how we usually think。

 But it turns out that there are some hacks that you can pull in order to make an IP address correspond to multiple computers。

And also as a quick note， I've drawn this as like a data center， only having one load balancer。

 people will also pull more tricks in order to have multiple load balancers in a data center so that if the load balancer fails。

 it's not like the data center becomes useless， they'll have spare failover load balancers that can be swapped in very quickly。

So yeah， let's say that。We have Google with two data centers， one in SFO and one in New York City。

And what's going to happen is both of these data centers is going to announce that they own a particular IP address。

And and tick。Explain what is actually happening here like I've been drawing these diagrams with this cute little cloud to represent the internet。

 but in order to understand what's happening， we actually have to look at what is happening inside of the internet and this is going to reference some material at a very high level if you're interested in what's actually happening。

 take CS144 because that's when we talk about how this works but。

The internet is composed of a bunch of routers and when you send packets to router。

 it figures out like what is the best way that I could deliver this packet to the destination。

 what is the best path that I could take to get to the destination。

 and then it sends that according to that path。So what's happening here is Google is going to have a router inside of their San Francisco data center and they'll have a router inside of the New York data center and both routers are going to announce to the rest of the internet that。

 hey， if you want to reach this IP address， send me your packets。

I guess I shouldn't use the term packets because we haven't really talked about what packets mean。

 but just like send me your bytes， send me your information。

 if you have requests that you're trying to send to this IP address。

 you can send those requests to me and I'll deliver them for you。

And usually these announcements come with some particular cost。

 so let's say that the cost has to do with distance。If we're trying to minimize the cost。

 we're trying to minimize the distance so that when the Stanford router delivers a particular connection。

 it sends it to whatever data center is the closest。

And so when these routers send these announcements。

 the Stanford router internally is building up this routing table saying that， oh。

 if I want to reach this IP address， I should deliver these connections to the San Francisco router。

 and if I do that then that will impose a cost of 10， just I'm making this up。

But that corresponds to distance， or I can also deliver connections for that IP address to the New York router at a cost of 100。

 it's a bit further away。And then what happens is when a client tries to connect to an IP address。

 so say that you're on the Stanford campus， if you try to connect to that particular IP address。

 what your computer is going to do is it's going to open a connection to the Stanford route and it's going to say。

" hey， I want I'm trying to connect to this particular IP address。

The router is going to look in its routing table and it's going to say， oh hey。

 I know where that IP address is， I know how to get there， in fact。

 there's two ways that I could get there， I'm going to pick the one that's cheapest for us。

 that's the one that's closest。And so it is going to select the SFO router。

 which is going to end up delivering this connection to the SFO load balancer。

 and the load balancer will pick one of the compute nodes and deliver it there。

Does that make sense so far？So let's say that the San Francisco data center fails。

 there's a huge fire， catastrophe， disaster。 we want to make sure that Google stays up。

If a client tries to connect to the Stanford router and the Stanford router notices that the San Francisco the Google router in San Francisco isn't working anymore。

 it will take that route off of its routing table it will say hey this route appears to be dead traffic isn't working there anymore and then when a client tries to connect it will send it to the New York router instead。

 so the client has absolutely no idea that this is happening the client is just like hey I want to connect to this IP address。

 please help me open a connection。But the internet has a lot of mechanics inside。

 this is a protocol called BGP。 if if you want to read more about it。

 it's an interesting protocol with a rich history of security vulnerabilities because imagine that like you have a data center that's not a Google data center and it announces to the internet。

 hey， I can handle traffic for 171。67。215。200。You can imagine that would be a disaster because then then people will start sending traffic for Google's load balancer to a non Google data center and this actually happens sometimes it's fortunately not super common。

 but every single year this happens with some high profile company but this is what's happening inside of the internet and。



![](img/c365a7f7139844c5800b2f1635777b35_9.png)

Essentially how it works。 So I'm over time， but I just wanted to mention really quickly。

 this interesting thing that Netflix developed。 It's an interesting philosophy called chaos engineering。

😊。

![](img/c365a7f7139844c5800b2f1635777b35_11.png)

And Netflix basically said that to design reliable systems。

 we have to assume that everything can fail， but it's hard to predict how things will fail until you see it fail。

You don't really think about like into a system that has a ton of moving parts。

 you don't think about what will happen if each individual part fails until it actually fails and then you're like。

 oh crap， I forgot that I need to handle that case。So how do you do this？

You intentionally induce failure， you intentionally crash pieces of your system。

 but you do it in a controlled environment instead of at three in the morning when it wasn't expected。

So they， they created this series of tools。 The first one was called chaos monkey。

 And what chaos monkey does is it it like。Intentionally crashes your servers。

 It will take one of your servers and it will just bring it down in production。

 like they're doing this in production all the time。 And in fact。

 they have other tools that bring down entire data centers。 Not only that。

 there's a tool called chaos Kong that brings down an entire region。

 So it will take down all of the data centers in Chicago or all of the data centers in New York。

 It's absolutely ridiculous that you do something like this。

 they're doing it in production all the time。😊，And there's some interesting blog posts that you can read here if you're interested。

 but somebody who ended up using the system for a different company was like。

 raiseise your hand of where you work， someone deployed a service that randomly kills services and processes in your server farm。

Now raise your other hand if that person is still employed by your company。

 like this sounds like a terrible idea， but it has actually worked very。

 very well for Netflix and as a result， Netflix is one of the most resilient services on the Internet。

 it's interesting that Netflix of all services would be so reliable like can't let streaming go down。

 absolutely crucial but they've done a really good job in this area and if you want to read a bit more about it。

 I have some links here。Thanks for coming and this's all I have for today stay after if you have questions。

 otherwise I'll see you on Thursday， have a good rest of your day。



![](img/c365a7f7139844c5800b2f1635777b35_13.png)

Great question。Here， so。Yeah， so what does it do？

![](img/c365a7f7139844c5800b2f1635777b35_15.png)

It just seems like such a counterintuitive idea， but the reason that they did it is they're rational is basically things are going to fail anyways。

 servers are going to fail。 it's absolutely going to happen。

 We just don't know when and what often happens is like the most crucial parts of your system will end up failing at three in the morning when everybody is asleep and nobody can respond and then some poor onca engineer has to like try to figure out how to resolve the issue and at minimum it'll take multiple hours。

😊，And so their thinking is， if we have a problem， let's discover it when everybody's awake and when everybody's prepared so that。

First of all， we can fix it。 Like we had control in the first place。 We might have broken something。

 but we broke it。 and like we know exactly what broke because we broke it and we can bring it back。

 So if there truly is a problem that we can't respond to。

 at least we can fix it by like restoring the server that we took down， the server that we took down。

And then we know to fix that problem so it can't happen again in the future。

So part of it is the fact that everybody's on call。

 The other part is it encourages engineers to build reliable systems。

 like if if you know that your production environment is failing all the time in spectacular ways。

 it's not even like random failure， it's intentional failure。

 if you know that then you're much more incentivized to build systems that are able to tolerate that kind of failure。

Such that real failures of servers like when a server actually goes down， that's just noise。

 it's just noise in the system because that happens all the time， it's a noneven。

 we don't really care because we've been testing for that all along。Does that make sense？It's a。

 it is。One of the most creative and bizarre ideas I've ever heard of。In distributed systems。

 But it's one that has been quite successful。 And originally。

 it was just this one tool that would kill servers。嗯。And now they have this entire suite of tools。



![](img/c365a7f7139844c5800b2f1635777b35_17.png)

There's if you look up at the Wikipedia page for this thing。

 there's like at least 10 chaos tools on the list。Any other questions？

