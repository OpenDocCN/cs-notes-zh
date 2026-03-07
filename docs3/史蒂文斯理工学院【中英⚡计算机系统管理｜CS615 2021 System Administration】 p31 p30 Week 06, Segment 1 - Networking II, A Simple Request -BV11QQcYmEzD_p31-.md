# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p31 p30 Week 06, Segment 1 - Networking II, A Simple Request -BV11QQcYmEzD_p31-

Hello and welcome back to CS615 System Administration， this is Week 6 segment1。

 and we're continuing our discussion of the larger topic of networking。In last week's videos。

 we looked in some detail at the global view of the internet。

 the governance of the IP space in the administration of autonomous systems。

 as well as some of the implications of the physical nature of the internet。

But while that is all nice and well， actually， to me at least quite fascinating。

We also have to better understand networking on a more local level。

 that is we want to understand how systems communicate specifically and how we even get our systems to talk to one another。

 how they know where to send packet and what those packets look like for the different protocols beyond the IP and IPV6 protocols we already looked at。

So in this week's videos， we'll be tracing a very simple request and use that as an example to illustrate these concepts。

Let's get started。What might a simple request look like The Hypertext transfer protocolcol or HETP is an obvious choice here。

 and as it' ubiquitous and easy to understand。So let's simulate a most basic HTP request from our standard AWS E2 dual stack that BSD instance。

We use the TE command to establish a TCP connection to WWWtoya Hotel Common port 80 and issue an HtTP head request。

The server dutifully replies with some information and the connection is terminated。

How is that for a simple request Does't get much simpler than that， does it？



![](img/5299aa121f71c67baabae8c4a043ac85_1.png)

So let's take this example and see what exactly happens under the hood。Superficially。

 it looks like while the local host makes a connection to the remote host。

The local host send some data。The remote host replies with some data。And we're done。

 classased as missed。Oh， you're still here。 All right， let's try to dig a bit deeper。

Let's focus on this bit here， just how exactly does the local host make a connection to the remote host。



![](img/5299aa121f71c67baabae8c4a043ac85_3.png)

For that let's repeat the simple request， but this time we're going to capture some information so we can then reconstruct in detail what happens on our system。

We start with a TCP dump running in the background。

We'll exclude all traffic to port 22 as is age traffic since we are connected via SSH and thus everything we type here and every output generated will lead to additional packets in the TCP dump output。

 so we'll exclude those。Then we clear our ap cache to ensure we start with a clean slateade all the way from the bottom layers。

Next， we rerun the same talent command from before。

 but this time we are wrapping it in the call to K traces。We， again。

 sent the same simple head request。And when we're done， we stop RTs feed collection。

And look at the packets we captured。

![](img/5299aa121f71c67baabae8c4a043ac85_5.png)

Looks like we've got a whole bunch here。Good。But so wait。

 we run the talent command wrapped in K traces。 What's K trace。



![](img/5299aa121f71c67baabae8c4a043ac85_7.png)

Hatres is a tool that you can use to trace other commands to let you see what type of system calls it makes and what IOE performs。

 for example。This allows you to really understand what happens when you run a command。

On other Uni versions you will find similar to such as Strs on Linux or Deedtras on say Om Neio。

The output from K tracece is in binary format， so we use the K dump tool to read it。

Here's what it looks like。As you can see here， there are all your different system calls the application makes。

You see it opening some shared libraries and mapping them into memory， open some files， etc。

Let's see what files it opens under Esse， since that is where we know we have many system configuration files。

Allright， so that looks interesting。 The first two are not surprising。

 since Turnnet is dynamically linked executable。The files we care about here are the next files。

Let's start with Enwitch， dot com。What does that file do。Well， we have a Uni system。

 so we don't need to guess nor Google。But instead can simply look up what this file does in the manual pages。

Okay， so the manual page tells us that this file controls how internal library functions look up certain pieces of information。

And as switch docon can specify certain sources where information can be found。

Such as other static files。Or an external service， like DNS。

The things in a switch that conf can look up。Include groups， hosts， user information， and so on。

So what does our NW confi look like？

![](img/5299aa121f71c67baabae8c4a043ac85_9.png)

Here we see the default configuration for the Standard C library Rer。

 telling us the different application wants to turn a host name into an IP address。

 it should first look in the local files， and then if that doesn't yield the result。

 fail over to the domain name system or DNS。Okay， so what's the next final or application looks up。



![](img/5299aa121f71c67baabae8c4a043ac85_11.png)

We see it opening at sea hosts。 What does that fire do。



![](img/5299aa121f71c67baabae8c4a043ac85_13.png)

Again， the manual pages provide the answer Etsy hosts as the host name database and was indeed before the domain system was introduced the central method to look up a host name。

You're probably familiar with it and know that you can add entries here to point a name to an address and because this file takes precedence over the DNS。

 your application will use whatever information it finds in that file。



![](img/5299aa121f71c67baabae8c4a043ac85_15.png)

Our file looks like this。By default， this file only contains entries for a local host。Now。

 Etsy and Switch dot co told us that if we don't find an entry an Etsy hosts。We should ask the DNS。

How do we figure out the NS server to use。Looks like our application looks an Etsy resolved at Kth。

 So once again， let's bring up the manual page。As you may know。

 it's a result that Kf now specifies how DNS lookups are to be done when an application called one of the resolver functions。

Most importantly， this file contains the IP address or addresses of the DNS server or servers that the system should use。

Now， our Esy Re con looks like this。Looks like our name server is 10 100 to 2。

 So if we are given a host name that we couldn't map to an IP address via Etsy hosts。

Then we should go and ask this server。Let's see what we find out now km trace output。

If we look forward what circles， our application opens up。

We see that over here it opens the socket in the IP domain of type Datagram and then connects to the IPV4 address 10。

10。0。2， our DNS server。The data it sends below is to know our first DNS query for the name www。

yahhoo。com。And the response we get back is shown in a few lines below。

We then see a second connection to the DNS server。And after that。A new socket。

In the IPV6 domain of Ty TCP to this IPV6 address here。After that。

Tealnets print some information to the terminal。Reads input from the user。

And then sends that data over the socket to the remote host。

A bit further down then we see how we are receiving the data from the remote host。Okay。

 so we saw that a simple step of connecting to a remote host actually broke down into a few steps。

Namely one step where we take the given host name and turn it into an IP address。

 and one step where we are making the connection to the remote system and communicate with it。

But of course， we then also saw that the step of turning the host name into an IP address broke down as well into several steps。

Namely， at first， a step that determines just how exactly it's supposed to convert the host name into an IP address by asking at cnswitch。

comv。Then by looking up the host name and Etsy hosts and upon failing going to the DNS。 But for that。

 it first needs to look at Etsy resolvedsol at K to determine what DN S server to ask。

Then open up a UDP socket to that server， send our query。

 and hopefully get a reply before we can then connect to the remote host。

And so a simple request like the one we started out will suddenly doesn't look quite simple anymore。

 especially when considering that so far we've really only looked at what happens on our local system and have not yet looked at the network packets we're sending。

Remember， we had initially captured TCP dump output as well， but we never looked at that。

But don't worry， we'll make up for that in next video that we will then trace those packets。



![](img/5299aa121f71c67baabae8c4a043ac85_17.png)

Before you move on to the next video， though， here are a few exercises for you。

Repeat this exercise in the Uunto Linux， a Ra Linux and an omniio instance on those systems you will need to use a different tool from K tracece。

 which is a BSD tool on Linux systems you should find the tracece command an Omniio。

 the D trace command。They both behave a little bit different， but provide the same information。

 letting you trace an application to see what exactly it does。

But eachOS will also use perhaps different configuration files and make sure you can track how exactly the host name is resolved in the connection made。

In our example， we saw connections being made to IPV4 and IPV6 systems。

 but it might be interesting to compare to an IPV6 only system。

 Configure an instance to be a V6 only system and see what's different。

We mentioned that host name lookups start Etyhosts verify that you can circumvent a DNS lookup by adding an address in that file and tracing the application。

And finally， if you look at the K tracese output， you might have noticed that we made two separate connections to the DNS server。

 but we only resolved a single host name， didn't we， Why is that。All right， with all that。

 as promised in our next video， we look at the network packets we captured using TCP D。Until then。

 thanks for watching。

![](img/5299aa121f71c67baabae8c4a043ac85_19.png)