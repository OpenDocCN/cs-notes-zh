# UCB《Linux系统管理实践课程｜UCB Linux System Administration Decal 2025》中英字幕（deepseek - P6：Lecture 6.zh_en - GPT中英字幕课程资源 - BV1wj59zGEMq

![](img/55a8f0d687a76a3601ed8f07942ec238_0.png)

Okay， yeah。Again， today's lecture is on web servers and DNS。



![](img/55a8f0d687a76a3601ed8f07942ec238_2.png)

Right。So so in last lecture， we covered basically basic networking， so what happens。

How this signal reaches starts from your computer， you know going through to all different layers and then it ends up you know to the server maybe on other side of the world and now we're going to we mentioned briefly about DNS and IPV6S4 addresses and we're going to look like look actually into you know how these addresses work in on the internet。

So we're going to go through DNS which stands for domaining system。

 we're going to look at structures of web servers and look into a load balancing so let's start with domaining system so what is DNS。

So basically when you go to sayocf。bikeley。edu， so you're typing in the domain that is readable by human because nobody you want to memorize you know a stream of IP address。

 so you go to so you send you typeping in a browsersing and you click enter this request is sent to a DNS resulter。

And this resolver is eventually going to tell you hey like OF。

ke got EduU is actually mapped to this address， this IP address and then with this IP address。

 knowing this IP address then your computer sends a request to this IP address HP request for example。

 to the actual IP address where the machine actually is and then that machine you know establish a connection and desktop direct you know transmit information so this is basically how it works but how do they what's actually happening what is the actually domain name system domain name system。

Yes。Okay， so。Okay， more about。Just what I said。Start here and then you type in O do you request that a record。

 which is going to go over later of what is what are the different records the recursive resolver is going to。

It's first going to okay。Right， so the recursive is over。

It's recursive because it searches recursively you know for all of these terms so it starts in the end from doteddu and then it goes to dot。

ocf and blah blah blah so it starts here and it starts with NS records for EDU domain so all dots Edu domains that's called a root server so go after you found out about that and then you go to you try to resolve for dot。

You've resolved。edduu and now you reserve resolving Berkeley。edu。

 which is going to give you a record and then eventually with that。

You know what is this cup ears I do not that oh't know go Bears joke many years ago I think before you came to Berkeley but okay and finally it gives the a record of the Of。

ke。du after resolving so that's why it's called a recursive rer right eventually you know concept to OCf and that maps the actual IP address。

呃。Right， so returns the Ichiats all the way back to the user here。呃。

Okay' going to look into more of all these terms we've looked at you know what is an and as what is a record what is TTL times you live etctera。

 so going to look into this right now so a records it returns basically IPV for addresses so address that look like this。

Yes IPV4 addresses and for a A it returns IPV6 addresses which are a longer so they're like that like or billion IPV4 addresses and theyre like astroronomicable number IP IPV6 addresses in the world so that's why we use both of them mainly IPV6 addresses we introduced recently because we can't we are having many many IP addresses and we keep can't keep up to demand CNM is the canonical name records so。

Basically。Uptime。ocCf。o for example it points to snap。heerrobot。

com so like it's basically just mapping one domain to other domain and then if you go to a website and a Cname record you can result this name records find like what that domain is mapping towards and then try to resolve that domain into your IP address so you can try right now OF。

IO would direct you directly into the OF website which is called OF now briefly by MX which is email records yes they're stored together with the other records so redirects email to your mail server。

NS stores the authorit name server for a domain， so the NS record points anS record error pointss。

Okay。More types of DNS records so TXG contains information about the domain site verification actually seen that like today when helping the students one helping one organizations they have a TXT record that iss like a token for Google verification it can be a lot more than this but a lot of times it's just site verification SRV。

Basically specifies a host and a port for specific services。

 so up to now like A records for AI records were mapping domains to IP addresses。

 SRV would map to a port under IP addresses。So for example， for services like instant messaging。

 you want to connect to a specific port， not just to the IP addressctors， and that's why you use SrV。

嗯。Anyway， so port is basically you know a computer has a server has many different ports and each different port would host a different service。

 so you can have a website running on one of the ports and another surface running another ports。

 a Mincraft server on the other port， etc cea， et cea， so that's port。

Now SOA stores administrative information about a domain， like the email address of the amin。

 when the domain was lapse updated and how long the server should wait between refreshes。Yes。

TTL records， so remember when we looked back here。We have TTL is equal to 300 seconds that's apparently TTL for OCF。

It's called stands for Time to Live。It tells the DNS record or the local resolver how long it should keep the record in its cache so basically when you try to access it access like a website sounds to the DNS servers would already have like say lfbreakkely。

b stored in your cache so that whenever you access in it you don't have to go down the recursive resolver it just tells you instantly so time to live is basically how long this cache should be kept there so the side effects is if you have like longer time to live。

 that means like if you have like when that is one hour so and that request of that DNS server is going to be instantly resolved so you don't have to go still recursively or one hour every one hour so it speeds up DNS resolution but what if you update that right so that that's going to take an hour for it to reflect in the DNS records so in a DNS servers so it causes update to the zone to take longer to propagate to users。

Okay， so theres。Type of attack， cyber attack DNS poisoning。呃。Just an example here。Basically。

 you state between like the DNS server and the。You know you so the hacker stays between you and the DNS server so again you go to DNS server and say like hey。

 I need a records forocf。lyu and DNS tried to send like the correct IP to you and then you know the hacker sends in the middle intercepts that and changes that message another IP address so youre just so you think you're accessing O。

brily but you're actually accessing this and then this going point you to some other website。

And guess some other concepts， that's what's called DNS poisoning。And theNS poison can happen。

In very different levels。So they could actually just sit on a DNS where they could you know。

 actually。B on the DNS server side so instead a request going to the DNS server request on how go to them so that's another way you've been doing this and there's so many different ways they could do this any layer here they could just mess this up they can be any layer here and then change life of the IP address and。

I you can see here， but。Let me see yeah， yeah， so。And of these levels。

 we have created a great firewall of China， so the big firewall that blocks。

 you know a ton of outside of China websites， yes， it happens at many different levels。Um。

 but I think that's it way way to click okay， yeah， best for doing。All right， now y observers。So。

What happens when you visit a website so you've gone you have like Joe said basically entered YouTube。

com maybe like the video URL into into your URL bar this YouTubebe bit so that to the D servers I guess theres there's a redirect and then YouTube。

 co like like watch question mark right and then that gets sent to a web server on somewhere in a Google data center and then you get back web a web page with a video thumbnail stuff like that so how does that bit does that all that work so。

So basically the way a web server works is it takes a bunch of。Pages， videos。

Like any any sort of files， it can also like stream data。

 but it'll just return that to you when you send a request。

It'll like it'll bind into a socket and like like receive all that data back。

 which I think have you covered sockets in this class？Yet。Unic sockets。

I guess like you'll probably get to that at some point but。Okay， missing anything。

 were we missing anything here， Joe sorry， anything you want to add？Oh， I think it's very。 Okay。

 find， okay。😊，Okay， so the question。Next is how do you Web a server scale so what if you have two he for one server and you have files on that server and you want to serve them to users like more than one can handle so the answer to this is horizontal scaling question mark。

Are we there yet？Yeah okay one machine okay so okay they're too ways to do this one way is vertical scaling so this is basically like literally just buying a beef here server with like more cores more Eastern nets they be being able to hand more through machine and then the next way is horizontal scaling so just buying more machines but the problem is horizontal scaling as we've seen with。

😊，DNS。Okay， not the。Basically okay you see like each of these machines is a different IP address right and each DNS record can only bind from one like like a record for example。

 can only bind from one domain name to one IP address so if you have multiple like servers all different IP addresses on your network and you want all of them serving the same service to many users how are they going to be able to access like each one at you know say like Googlecom right so the answer to that is what' can call load balancing basically putting a machine in front of those。

And just forwarding requests to those so instead of like。

Like let's say you have an HTP request and it's like a path maybe it think a result path and maybe there's like some like parameters like like if you like use Google like there's like the question mark Q equals that's like the search like parameter you're passing in right so what a load balance will do is basically it will not look at any of that and it'll just take that entire request and it'll forward it to the next box down the line so。

Like there are multiple strategies for doing that like the most popular one is around Robbin they're other ones too that are like usage based but yeah that's the basic idea of load balancing if you've I mean you guys probably familiar with the concept of trees but you can you can set things up in a tree so you have like one like front load balancer and it'll go to like maybe like five more and then all your actual web servers like posting the service are like behind like。

Those five， for example。Okay， yeah， and that's， I mean， I do。嗯。Okay。So， okay。

 I guess I described this already。😊，Yeah， so。I can can sure if you want， okay。

So here like different algorithms we use for low balancing so Michael just said like round robbing so basically we just the first request we send it to Sur one second request send it server two and we go like around and until it goes comes back to server one so make sure like everything is equally allocated there's something called IP hash in which you know maybe you're log into one of your web apps and you have like a session and when you log out of your web survey when you web browser when you close it you still want to access that data so。

You have to have that data on the other side in a web server。

 but if you have 100 different web servers， that would mean that hey you need to sort that your data。

 your data need to be stored across these 100 data servers which is going to be costly and really complicated to synchronize database so there's something called sticky session in which once you can allocate it to a web server to a specific server with a low balancer。

 you'll always be directed your IP address， whenever it' your request it will always be sent like to that specific machine so that your information is only kept on that machine and that is doing through like hashing IP。

And these are like static load balancing so they don't really check what's happening with the servers。

 they just check like what's coming through and then they just allocate it。Yeah， like is that。

To expound on that like means like not inspecting the contents of the request it's like anything you can anything you can do without like like modifying like。

Data like on I guess on the web surf the service slash like whatever database you might have connected so it's like it's it's some it's something you can do without like。

Inspecting the request usually like like I think I'd be hashing a good example words like you're just looking at like the source and not actually like reading what the user is asking for。

And the reason is because like load balancers need to work across like many different kinds of services so I mean i think learn about like N X Apache those will use like everywhere right I mean you kind of want to like their designs in a way that doesn't like bias them towards like a certain use case like specifically having a customer database or like storing sessions or something like that so like they're all like these are all like pretty。

I guess you'd call like high level or like generalizable features。Overload downs， okay？

And they're dynamic ones which well it's pretty straightforward so like the load balancer just check like which server is responding the quickest and just send a message directly to that it dynamic because you know you're checking the server's response there connections to see likey how many connections were allocated to that specific server so that the next one you know I give to the second server which has less connections yeah just stuff like that's just general dynamic slip。

呃。And health checks basically they just check say like HP endpoint to see like if the machine is down we don't want to fully request that machine right。

 so before sending they make a health check make share like whatever requires your forwarding that machine is alive and capable of you know processing the requests。

And I think that' is there enough？Yeah， that's it。Okay， so yeah。

 one last question added like today because when I was prepping for the lecture。

 I was always there was one question on my mind like。

Hey like why don't load balancers be overwhelmed right if there are so many requests that like think about go。

com maybe talking about thousand and thousand requests for second won't that poor load balancer be right so I think Mike already touched it on that before but we have a tree so。

So first of all， there are load balancers before load balancers to make sure load balancers do not。

A single low balancer do not take too much stuff， do not have too much work to do。

And a lot of like different strategies is DNS load balancing。

 so when you you know when you like try to resolve the IP address from DNS right。For Google。

com that is operating in many， many different countries whenever you send a request to DNS the DNS itself is going to do kind of for load balancing so it checks like hey this request is coming from say Japan and this request is coming from Australia we're not going to map them to the same IP address you might to different addresses which probably corresponds to different low balancers then to like more servers so that's another way of having DNS low balancing。

And I also found there just something called anycasts。诶。Lad balancing， so it's basically。It's like。

Almost it's literally having servers。Havingaving load balancers with the same with the same IP and then one like the single send out and then you have you have routers。

 the specific router called B BSG routes， I think they basically check like which router is which corresponding server is fastest from where you are right now where the request was sent and then they direct you to that。

So there are many different ways that people do to prevent low balancers itself from being overwhelmedwhelms。

 but that's mostly it yeah and I think that's the news， right？



![](img/55a8f0d687a76a3601ed8f07942ec238_4.png)

Great， thank you。guess wishes yeah。All right， we you have any questions about the lab just around here。



![](img/55a8f0d687a76a3601ed8f07942ec238_6.png)