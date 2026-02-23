# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p11 -11-2.4 The Domain Name System (DNS).zh_en -BV1UMtueiEaA_p11-

![](img/4ce8b3f1c0a4f1371df881eecb0393e9_0.png)

In this section， we'll cover the DNS， the domain name system。

 the part of the internet that's responsible for translating host names like Gaia。cs。 umass。

edduu to  IP addresses like 128。119。40。186 and we'll see that the DNS is this amazing distributed application that's able to perform its services at massive scale and with pretty amazing performance。

 Now we're at the application layer and so you may be asking yourself， well hey。

 why are we studying a core internet function like name translation up at the application layer And the answer to that is because the DNS is an application layer protocol and service It's built on top of and uses the services of TCP and UDP So it really is an application level service。

 Well， we've got a lot to cover here and what we're going to do is we're going to start off by talking about the structure and the functioning of the DNS。

We'll look at the process by which queries are going to be resolved。

 and then we'll take a look at DNS records and also the message format of the DNS protocol。

 so we've got a lot to cover， so let's get started。Well as the name domain name system would imply。

 the DNS is all about names and identifiers and as a person。

 I have many identifiers associated with me， I have my name， my Social Security number。

 I've got my passport ID I've got my Umass employee ID associated with me and we've already seen that internet hosts also have at least two identifiers associated with them。

 they've got a name like I。cs。ummass。edu they've got an IP address like 128。119。40。

186 and as we'll see， the role of the DNS is to provide translation between names and services and IP addresses。

The domain name system， the DNS is a distributed database。

 The contents of this database are the records containing information about the translation among the host names。

 services and IP addresses。 the DNS itself as a hierarchy of servers spread around the Internet services that communicate with each other to provide this name translation service and it's important to note that the DNS is implemented as an application layer service It's implemented by servers that sit at the network edge rather than at routers and switches inside the network。

 and this reflects an Internet design philosophy of keeping the network core simple and putting complexity at the network's edge will see this design philosophy coming up again and again as we dive down into the transport layer and then the network layer。

The DNS provides a number of different functions。 The one we've heard about the most is this IP address to host name translation service。

 but it provides a number of other important services as well。

 provides an aliasing function that is translating from externally facing names like mail cs。ums。

edu to some internal host name that's much more complicated than that。

 It also provides service resolution， for example， returning the IP address of a mail server associated with a domain and finally performs load balancing。

 There may be a number of IP addresses that are able to perform a requested service， for instance。

 a web server， for example， and the DNS will rotate among those possible IP addresses。

 returning one of those as the primary service and thus performing a kind of load balancingan function。

Given the DNS takes a distributed decentralized approach， you might ask yourself。

 why didn't the designers of the DNS take a more centralized approach。

 and there are several considerations here。A centralized approach represents a single point of failure。

 and we've seen that the DNS is critical infrastructure， given the loads on the DNS。

 a centralized approach would create a tremendous concentration of traffic。

And given how important performances， member milliseconds count when resolving a DNS query。

 placing it at one location would necessarily mean long RTT delays to some places on the planet。

 and this is all to say that a centralized approach simply doesn't scale with trillions of queries a day。

 Akama alone handles more than a trillion DNS requests a day。

 a single centralized service doesn't have the computational capabilities the resiliency or the performance that one can get with a decentralized approach。

Well， before diving into the technical details of the DNS。

 let's summarize here in terms of how to just even think about the DNS so you can think about it as a highly distributed。

 highscale high performance distributed database。 That's a tough problem。

 but at least as we'll see the records are relatively simple。

 and you want to think about it in terms of performance and scale。

 also needs to be able to handle literally trillions of requests mostly reads that come in every day。

 and it has to do so with really high performance。 milliseconds are going to count and then organizationally。

 it's also highly decentralized。 They are literally hundreds of thousands of organizations that are going to be responsible for their pieces。

 there are records within this distributed database。 Is this an easy problem not really。Well。

 we said that the DNS is a distributed hierarchical database。

 So let's take a high level look at this hierarchy。 The root of this tree。

 we have the root DNS servers。 The next layer， we have the DNS servers that are responsible for all of the dot com or Eu or net domain names。

 These are known as the top level domain or TlD servers。

 And then we have the authoritative name servers。 these are the servers that have the ultimate responsibility for resolving names within their domain。

 For example， for all of Umass do Eduu， all ofnyu do Eduu or all of Pbs do org。 Now。

 if a client wants to resolve an address， say for Www do Amazon do com。 Here's the basic approach。

 client could first contact a root DNS server to get the name of the T LD server for all of the dot com。

 The client then contact the T LD server to get the name of the authoritative name server。

 for Amazon com。And then finally， the client contacts the authoritative name server for Amazon。

com to get the IP address of www。amazon。com。Well， since we like to study things top down。

 let's start at the top of the DNS hierarchy and that's with the root servers。

 The root servers are a place to go when servers not actually able to resolve a name。

 you can think of it almost like a contact of last resort， and in fact。

 it's not really a contact of last resort because it's not going to actually provide that translation service。

 but it's a place to go to get translation started。Well。

 this is obviously an incredibly important function for the Internet。

 almost like the central nervous system of the Internet。 And as such。

 security is going to be very important。 Now， the root servers and much of the infrastructure associated with them is the responsibility of Ican。

 the Internet corporation for assigned names and numbers。😊。

There are 13 logical route servers around the world。

 but each of these logical route servers are themselves actually replicated。

 So corresponding to these 13 logical servers are actually close to 1000 physical servers around the world。

 There are more than 200 physical route servers in the US。Moving down a level from the root domain。

 we find the T LD， the top level domain， and each of the servers and the top level domain is responsible for resolving one of the addresseses that have an ending like dot com Eunet or do org。

 The associations that are responsible for managing these T LD domains are known as internet registries。

 These internet registries are also the place that you'd go。

 If you want to register a new dot com Edu ornet name。

 The authoritative name servers are responsible for resolving names within an organization。

 and such a servers are authoritative in the sense that， as the saying goes， the buck stops here。

 This is the DNS server that has authority over the organization's names。

 and what this server says goes。And lastly， there are the local DNS servers。

 Every host on the Internet has an associated local DNS server。

 and this is the name server that a host is going to contact when it wants to resolve a name。

 The local DNS name server is then going to respond immediately to the requesting host if it has that name to address translation pair cached locally。

 Otherwise， it's going to start the resolution process。

If you're interested in finding out the host name of your local DNS server。

 you can type in one of these two commands into your computer under MacOS， type in SCUTIL。

 minus minus DNS， or under Windows IP config/ all， each of these commands displays the name of your local DNS server。

Now let's take a look at an example of DNS name resolution in action。

 suppose the requesting host is at engineering。nyu。edu。

 and it's going to make a request to resolve the name Gaia。cs。ummass。

edu Well here's how this unfolds the host at engineering。nyu。

edu first sends a dns query message to the localnyudns server let's say dns。ny。

edu The query message contains the host name to be translated Gaia。cs。ummass。edu。

Now it's the job of this local NYU DNS server to resolve this name It begins by forwarding a query message to a root DNS server The root DNS server takes note of the dotedu suffix and returns to the local DNS server。

 a list of IP addresses of TLD servers， top levelvel domain servers responsible for doedu The local NYU DNS server then resends the query message to one of these TLD servers。

The Tld server takes note of the umass。edu suffix and responds with the IP address of the authoritative DnS server for the University of Massachusetts dns。

ummass。edu Finally nyu's local dnS server resends the query message again to dns。ummass。

edu and umass's authoritative name server responds with the IP address of Gaia。cs。ummass。edu。

In order to get the mapping for one host name， eight DNS messages were sent for query messages and four reply messages。

 we'll see soon how DNS caching can reduce this query traffic the type of querying that we've seen in this example is known as an iterated query because the local DNS server atnyu is iteratively querying a sequence of servers until finally the Gaia。

cs。umma。edu name is finally resolved。A second form of query resolution is known as recursive query resolution in recursive query resolution。

 rather than responding to a request with a， I don't know。

 But here's who to try next type of response that we saw with iterative queries。

 the name server takes it upon itself to resolve the query and return a definitive reply In this example here。

 which shows a cascade of recursive queries。 the local DNS server at NYu again queries the root server In this recursive case。

 however， the root server queries the T LD server who queries the Umass authoritative name server。

 who replies to the T LD server， who replies to the root server who replies to the local DNS server at NYU。

 who replies to the querying host。Because this form of recursive querying puts the burden on the servers at the upper level of the hierarchy。

 it's not often used in practice and instead iterative queryings adopted by the local DNS server。Now。

 we've seen that a lot of work can be involved in obtaining the DNS record for a name to address translation bear。

 So it' would be great to somehow leverage that work。

 And remember that's to say cash that record locally for some time。

 in case another request comes in for this same record。 So once a DNS server learns a mapping。

 it's going to cache that mapping for some amount of time。

 If a future request comes in for that mapping， it can immediately return the cached reply in response to the query。

 So we see that caching improves response time and it takes load off the DNS infrastructure。

 A double win。😊，Cched entries will eventually time out and disappear from the cache after some amount of time。

 the time to live。Note， however， that it's possible that if a DNS record changes。

 the cached entries will then be out of date。 However。

 the DNS doesn't worry about stale and out of date cached entries。 they'll time out eventually。

 even if in the meantime， there's a bit of inaccurate information floating around。 For example。

 if a named host changes its I address， that change won't be known Internet wide until all of the T TLs expire。

 What's gained here。 however， in this well best effort approach to name to address translation is that there's no need for costly and complicated mechanism to locate and purge out of date information from caches。

Well， that's all we want to say about the structure and the function of the DNS。

 but there are still two more things we want to take a look at。

 we want to take a look at the resource records that are inside the DNS and we want to take a look at what DNS protocol messages look like。

DNS database records are a fourtuple with a name， value， type， and TTL or time to live field。

 There are a number of different types of DNS records。

 but here are four popular ones when the type is a that is an address record。

 the record contains a host name and its I address and this record is used for name to address translation when the type is NSs。

 a name server record， the name is a domain name like UMassdo Eduu and the value is the host name of the authoritative name server for that domain a C name record is used for name Alia saying and an Mx record is used to give the name of a mail server associated with a domain。

Let's next take a look at the DNS protocol message formats。

 Both the query and the reply message have the same format as shown here on the right。

 Remember that the DNS is a query response protocol。

 The I D field here is a 16 B number chosen by the queryier when a response is sent in reply to a query。

 that response takes its I D value to be the same as that of the query。

 to indicate that this is a response to that particular query。

 The flag field is used to indicate whether this is a query message or a reply message。

 whether the recursions being requested If it's a query， and if it's a reply message。

 whether the reply is authoritative。 The next four fields are used to indicate the number of questions and response is in the remainder of the protocol message。

In the case of a query， a question， say resolve a host name to an I P address。

 the host name would go in this field here。 In the case of a reply to such a query。

 a resource record of type A。 Remember， containing the name and the I address of a host would be inserted in this field here。

 RF C 1035 defines all of these fields and resource records as well。

To help put together the pieces of some of what we've learned about the DNS。

 suppose now that you create a company。 It's called network Utopia。

 It's got a network and you want an Internet presence。

 You want your company's services to be reachable by others on the Internet at your site。

 network utopia co。 What do you need to do。 Well， clearly。

 the DNS is going to be involved since in order for users to reach your network。

 they'll need the I addresses of the servers in your network。

 And even if the name network utopia do com becomes fabulously famous。

 No one's going to know the I addresses of your servers。 So， of course。

 you'll need to use the DNS for that。 First， you register your name。

 network utopia do com with the DNS registrar like network solutions。

 a company that's a registrar that we mentioned earlier。 you'll need a set of I addresses also。

 we'll discuss in chapterpter 4 how you get those。 So let's assume for now that you've got a range of I addresses for your servers。

 You then need to give the name and address of your。😊。

Aoritative name server to the registrar the registrar will insert your name server's name in an NSS record and its IP address in an A record into the global DNS database that's all that needs to be done with the registrar。

 The addresses of all the other servers in your network will be provided by your authoritative name server to queers who know the host names for those services。

 And lastly， you need to bring up your authoritative name server and populate it with resource records for the servers in your network。

And let's wrap up here with just a quick word about DNS security。

 Now that you understand what the DNS does， you can see how absolutely critical it is to the functioning of the Internet。

 If the DNS stop working， itd be impossible to contact any host unless you knew its I address。

 which means practically never。 And so it's critical that the DNS be protected。

 The DNS is protected against the N of service attacks primarily by firewalls。

 The DNS also needs to ensure that records that are entered into the database are from authorized sources。

 and so authentication services will play a critical role in protecting the DNS will look at authentication services when we get to Chapter 7。

So that wraps up our discussion of the DNS an absolutely critical network function that has to work at amazing scales and also at amazing performance we took a look at several things here we talked about the function and the structure of the DNS we talked about how names are actually resolved and we took a look at the resource records inside the DNS database as well as the DNS protocol message formats Com up next we're going to take a look at another highly decentralized highperform distributed application video streaming。



![](img/4ce8b3f1c0a4f1371df881eecb0393e9_2.png)