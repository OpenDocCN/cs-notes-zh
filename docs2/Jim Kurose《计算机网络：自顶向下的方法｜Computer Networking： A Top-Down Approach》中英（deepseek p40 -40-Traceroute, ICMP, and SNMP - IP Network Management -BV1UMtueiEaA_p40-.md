# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p40 -40-Traceroute, ICMP, and SNMP - IP Network Management -BV1UMtueiEaA_p40-

In this video we discussed network management， including the ICMP and SNMP protocols。

Let's get started。

![](img/4274342614d5f94080da1e9bbf285fba_1.png)

In this video we're focused on the mechanisms used to manage IP networks We'll start by looking at ICMP。

 the Internet control message protocol and then proceed to looking at other management tools like SM&MP。

 the simple network management protocol ICMP is used by IP hosts to signal information about the network layer and is most commonly used for error reporting for example。

 host unreachable or network unreachable or messages relating to higher layers like a port unreachable or protocol unreachable message。



![](img/4274342614d5f94080da1e9bbf285fba_3.png)

We're probably all familiar with the Ping application which uses a specific ICMP message called Echo Request that triggers the echocho replyply message。

 so there are some diagnostic functions of ICMP that are not specifically error reporting。

It's important to note that ICMP is an in band messaging protocol。

 meaning the ICMP messages are carried inside IP packets。

So for errors that cause the IP layer to be disconnected。

 any resulting ICMP messages will not be able to get through either。



![](img/4274342614d5f94080da1e9bbf285fba_5.png)

There are many different messages within ICMP， but they all consist of a type and a code and since they are typically triggered by an IP packet。

 the payload of the ICMP message will be a quote containing the first part of the packet that triggered the error message。

Here we can see a number of type3 messages indicating that the packet that triggered it was destined to a network host。

 port or protocol that's not reachable， we also see the echo request and E replyly messages used by the PIing application and the TTL expired message。

 which is used by tracero。

![](img/4274342614d5f94080da1e9bbf285fba_7.png)

This brings up an interesting topic The Trero application is tightly coupled with the behavior of ICMP。

 however it is not using ICMP as originally intended Trero is effectively a hack that has been around for decades that allows the user to elicit some form of topology information about the path over which their data is traveling。

We've talked about traceroout before but we didn't have the details in place on IP Protocol and ICMP to really understand how it works。

 so we're going to revisit traceceroute and look at those details a little more so here we have a source and destination with a number of router hops in between of course we're ignoring any layer two devices that don't interact with the IP layer。

The implementation of tracer on different operating systems sends out different types of packets as probes。

 these can be TCP， UDP or ICMP packets that are sent out from the source Another variable is whether there is one probe sent per TTL or multiple probes sent per TTL。

 but in any case the first set of packets will have their TTL set to one。

 which means they will expire at one hop causing the first router in the path to generate ICMP TTL expired messages。

So the source sends out packets with the destination address of the destination。However。

 it gets back packets that contain ICMP error messages and those packets are from a router in the middle of the path。

 so this gives the source some information didn't know before that there is a particular IP address on an interface on a router in the middle of the path。

 So each chop along the way， the routers are decrementing the TTLs in the packet headers and when the TTL reaches0。

 the router is required to discard the packet and send back an ICMP TTL expired message。

The source IP address of the IP packet that that message is contained in will be an IP address of the router that sent it。

When the source gets this ICMP message back， it can keep track of eachH and this corresponding IP addresses。

In the particular implementation of tracerap being described here。

 we're sending three probes per hop and using the UDP protocol。

 so3 UDP packets with TTL1 should elicit three ICMP TTL expired messages from the first router。

 once those are recorded we can move on and send three UDP packets with TTL2。

 which will be decremented at the first router and forwarded to the second router and decrement it to zero at the second router。

 causing it to send back3 ICMP TTL expired messages。

The source proceeds sending three packets with increasing TTLs。

 and keep in mind the source does not know in advance how many routers are in the path or what their addresses are these packets are all sent with a destination address which is the host at the other end of the path。

So the source is able to discover routers that it had no prior knowledge about。

Eventually the UDP probes will arrive at the destination， however。

 the destination port on these UDP packets is intentionally set to a port number that is not expected to be used on the destination。

 so that port will be closed， causing the ICMP protocol to send back a port unreachable。

This lets the tracerout application on the source host know that it has reached the destination address and it should stop probing at this point。

This tool is very informative for network operators or even end users trying to diagnose or understand performance characteristics of a particular network path。

It not only lets the source know how many hops there are and what the IP addresses are on those routers。

 but also indicates the round trip time between the source and each of the routers。

 which allows that user to make some inference about distance or also potentially observe that there is some congestion along the path。



![](img/4274342614d5f94080da1e9bbf285fba_9.png)

Following that brief overview of ICMP， which as we mentioned is primarily concerned with error reporting。

 we're now going to look at some protocols dedicated to network management and configuration。



![](img/4274342614d5f94080da1e9bbf285fba_11.png)

First， let's talk about what we mean by network management。

We've talked in the past about this concept of autonomous systems or domains that are a sphere of influence that manages their own network operations。

Within1A there may be hundreds of thousands or even a million components that make up their network infrastructure。

 not even counting the end hostss or mobile devices。

 Of course networks are not alone in the sense of being complex systems that require monitoring control and configuration。



![](img/4274342614d5f94080da1e9bbf285fba_13.png)

So here's a definition Network management includes the deployment。

 integration and coordination of the hardware， software and human elements to monitor， test， pull。

 configure， analyze， evaluate， and control the network and element resources to meet the real time operational performance and quality of service requirements at a reasonable cost。

What a mouthful， but defice it to say performing network management correctly is very challenging and there are many different ways to go about it Let's start by looking at some of the components of network management。



![](img/4274342614d5f94080da1e9bbf285fba_15.png)

We have a server that keeps track of the state needed and typically provides some interface that the network managing humans can interact with。

This server will be in communication with all of the managed devices。

 which can include layer two switches， layer 3 routers， and hosts， middle boxes， etc。

Each of these devices will maintain some state that includes its configuration， statistics on usage。

 and any operational data specific to that device。In between the management server and each of these devices we need some protocol to run to enable them to talk to one another。

 this protocol will define how queries and configuration messages and reporting messages are exchanged between the devices and the controller。



![](img/4274342614d5f94080da1e9bbf285fba_17.png)

Note that this could be as simple as a command line interface used by a human operator to log into the devices and configure them and read back statistics about their state。

And this is typically how the devices are initially configured。However。

 there are also more specialized protocols such as the Sple network management protocol。

 which uses a standardized format for sending control messages and reading back state and makes it easier to manage large sets of devices at once。

A SNMP specifically has evolved over the years， but it is a relatively simple protocol that has been in use for about three decades。

The information to be exchanged using SNMP is stored in MIPS management information bases。

 which are simple key based data structures。Netcom with Yang is a more recent development in network management。

 providing a higher level of abstraction and increased emphasis on managing groups of devices instead of individual devices。



![](img/4274342614d5f94080da1e9bbf285fba_19.png)

Let's look at SNMP next。There are two ways that the data in MIs get exchanged。

 one is for the server to query the device， so a straightforward request and response behavior。

 and note that traditionally this was performed over UDP。

 although today SNNP supports both UDP and TCP， and then there is also the trap message。

 meaning the device had a message triggered by some external event whether that's a timer or a particular condition on the device and so it's sending an unsolicited message to the controller。



![](img/4274342614d5f94080da1e9bbf285fba_21.png)

And here we have the message types we note that there are a few different types of get messages because in some cases the MIb can be quite large and may require the controller to send multiple requests to get through the entire MIb we also have set requests where the controller is changing the configuration of the agent and then the two different types of messages from the agent to the controller。

 the first being the response which is always sent in reply to either a get or set message and the last being the trap message which is initiated by the agent。



![](img/4274342614d5f94080da1e9bbf285fba_23.png)

Here we can look at the message format where we specify the type of message and ID for this request again so that the requests and responses can be matched up later on。



![](img/4274342614d5f94080da1e9bbf285fba_25.png)

Any error conditions， and then a sequence of key value pairs。

The trap message is slightly different in that it contains the type of trap message in the header as well as a timestamp。

 and then again a sequence of key value pairs in the body。



![](img/4274342614d5f94080da1e9bbf285fba_27.png)

So we mentioned that the agents store the data they're collecting in MIs。

 and there are many different specific pieces of information that can be stored。

Some of this is standardized in RFCs， but many vendors have extended this with their own proprietary information types。

There's also a data definition language called SMI。

 and here's a few examples of particular MIs that we might store for the UDP protocol。

So in this case， we have a number of counters keeping track of how many UDP messages were seen。

How many port unreachable messages， how many UDP messages couldn't be delivered to the port specified。

 note that these are the messages that would cause IC&P port unreachable errors to be generated and how many UDP messages couldn't be delivered for some other reason。

 for example， if the internet checksum and the UDP header failed。

It's also counting the total number of UDP datagrams sent。Then we have a different type of MIb。

 the sequence， which is a list of all the UDP port numbers currently in use。



![](img/4274342614d5f94080da1e9bbf285fba_29.png)

Now let's look at some of the differences with the netcal protocol。

The goal of Nutcomf is to take a more active approach to management。

Where SNNP primarily deals with reporting back static snapshots of information。

NetCOf defines a number of actions related to configuring the devices， for example。

 setting a new configuration and then activating it。

And allows for actions to be performed across multiple devices at once。Whereas with S&M。

 the protocol only deals with interacting with a single device at once。

 and it would be up to an application running on top of S&M to aggregate functions across multiple devices。

But NtCoff also includes the ability to query operational statistics and data from devices。

 and this is able to replace the SNMP protocol in that respect。

Netcom follows the RPC paradigm and encodes its protocol messages in XML。

These are exchanged with encryption over top of TCP。



![](img/4274342614d5f94080da1e9bbf285fba_31.png)

So let's look at an example net conflict Exchange。We have our controller running on a server interacting with an agent on the far side。

The endpoints will first exchange a low message and then be in their sequence of remote procedure calls and replies。

 and we also see that the agent has the ability to send a notification which is analogous to the trap message in SNP。

When the session is complete， a closed session message will be exchanged。



![](img/4274342614d5f94080da1e9bbf285fba_33.png)

Here' are some examples of the operations that can be performed we have retrieving a configuration from the device。

 getting the state of a particular value， modifying a running configuration。

 locking or unlocking parts of the data store。And creating new subscriptions to event notifications。



![](img/4274342614d5f94080da1e9bbf285fba_35.png)

As we mentioned， the RPC messages are encoded in XML。

 so here we have an example that is editing the running config and it looks like it is changing the MTU on a particular interface。

Things to note are that we again have a message ID so that the reply can be matched up with the request on the controller side。

 we've identified that we're changing the configuration。

And that the particular configuration that we want to change is the running one。

And here we've identified a particular interface and then set the MTU on that interface to 1。

500 bytes。

![](img/4274342614d5f94080da1e9bbf285fba_37.png)

The structure of these messages is specified by Yang， which is a data modeling language。

 so for example， a yang description of a device can generate an XL document that specifies the capabilities of that device。

And this is the information that is stored in the device and the controller database as well as exchanged in the messages。

Formalizing this allows constraints or dependencies to be expressed。

 such that the configuration must satisfy those constraints。



![](img/4274342614d5f94080da1e9bbf285fba_39.png)

And with that， we are wrapping up our discussion of the network layer。

In this chapter we've specifically looked at the control plane。

 including controlling routers and the traditional routing protocols OSPF and BGP。

And we've also looked at the alternative control plane known as softwareft Def Networking。

 where the controllers are implemented centrally instead of being distributed across all the routing devices。

And then in this video， we wrapped up by looking at ICMP and network management。

This brings us to an important layer boundary in the network stack。

So far we've been looking at protocols that span the network edge to edge。

 whether it's the application， the transport layer or the network layer。

 all of these look at the communication from end host to end host。Even though at the network layer。

 we also have a number of concerns that are addressed top by hop to the network。However。

 when we move to layer2， we're now looking at much more localized views of the network and really starting to look at technologies that do not span the network from edge to edge。

 but address specific localized concerns， for example。

 one part of the network may be running wired ethannet。

 while another part is running a wireless cellular link layer。

But the IP network layer spans both of these with a common unified protocol。



![](img/4274342614d5f94080da1e9bbf285fba_41.png)

So in the next video， we'll begin looking at some of these layer 2 technologies and how they are suited for specific use cases。

 See you then。

![](img/4274342614d5f94080da1e9bbf285fba_43.png)

We hope you enjoyed this video， if you found it to be useful please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

