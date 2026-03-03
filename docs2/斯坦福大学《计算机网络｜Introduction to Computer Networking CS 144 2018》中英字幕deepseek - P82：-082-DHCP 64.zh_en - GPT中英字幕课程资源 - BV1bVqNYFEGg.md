# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P82：-082-DHCP 64.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

![](img/1265e6012f65545010d7103565ed734f_0.png)

So in this video on News and addresses， I'm going to talk about the dynamic host configuration protocol or DHCP。

 something which you probably use every day when you access the internet。

So if we take a step back and think about what do we need to communicate with IP with Internet protocolcol。

 there are basically three things that a host needs， it needs first an IP address。

 it needs an address which you can give to other nodes to send packets to and which it can put its own packets that nodes know to send back to it。

It needs a subnet mask， so it needs to know what nodes are on its own local subnet versus nodes it must contact through a local gateway。

It also needs to know the gateway router such that if the node is not on the local subnet。

 what's the IP address of the next hop or the first hop towards destinations outside the local subnet？

So these are the three things that you have to have in order to communicate with IP on the internet as a whole。

In addition， often it's very useful to have this fourth thing。

 which is the IP address of a domain name service server， or domain name system server。

This is basically where which allows you to translate names like www。cnn。tcom into an IP address。

And so you don't need this per se to communicate with IP if you just know the IP address。

 but it's very， very useful for most applications and for people。So there's this basic problem。

 you take you buy a new computer and you plug it into a network。

You need these three things and hopefully this fourth one， how do you get them？

How do you get these values？So in the old days， like actually when I my first year in college。

 you'd get them from your system administrator so you'd fill out a request for a network tap and then a couple days later you'd get a slip of paper which had your important values。

 it had your IP address。It had your subnet mask。It had your gateway address。

And it had the DNS server。And so you get a slip of paper with these four things on it and a sheet of usually a photocopy saying。

 okay， take these values and here's how you open up your control panel and type them in here。

And that was basically how you configure your machine。

 so this is hey I did it at Brown when I went there as an under graduate in 1995。

 by the time I graduated though they had moved on。So if you imagine on one hand， this can work。

 but its all kinds of problems if your machine moves。

 like if I take my machine and I move it to a friend's friend's room。

 it no longer works because that particular machine was configured for that particular top in the network topology。

So this question is how long this lasts， so back then when you filled out the slip of paper。

 it lasted a year。And in fact， if you didn't request it by a certain point in the year。

 you couldn't get one， so these addresses and configurations are given out on a yearly basis。嗯。

One final question is， how do you collect unused entries？

If I only want a machine plug in my machine for three days。

 does this mean that I have to allocate an entry for an entire year。

 the answer was yes And so while this works， it's remarkably inefficient。

So the approach that computers used today， and this is what was B star using by the time I graduated across the entire campus is something called DHCP。

 the dynamic host configuration protocol specified in RFC 2131。

Basically it is that a machine when it connects to a network can request its configuration from a DHCP server。

 and if you can just request your configuration， say what's my IP address， what's my sub mask。

 what's my gateway， what's my DNS server？This turns out to solve the three major problems I outlined if you move。

 well， you just do a rere， you're in a different part of the network。

 you need a different configuration。For the duration， how long it lasts。

 well when the DHCP server gives you a configuration it's associated with the lease saying configuration is this good for this lung。

 and then if you're nearing the end of that lease， you can rere the same configuration and usually the server will give it to you so there's a way to renew the lease。

These leases then make garbage collection very easy because if somebody doesn't rere it。

 you can reclaim， say that IP address。And so the basic interaction。

 the basic packet exchange that you see in DHCP， is there's a basic four step exchange。

 and then there's this optional release。So when a node first to ends the network and it had knows nothing about what's going on。

 it sends out a Disc message， I want to discover what DHCP server throughout there and what configurations they might give you。

So the client sends a discover。Then the DNS， sorry， the DHCP servers that can hear that discover。

 respond with an offer， so here are the servers。And more than one server can be connected and you might get more than one offer and they'll say here。

 I'm going to offer you this configuration。The client。

Then selects one of the configurations and sends a request to the originating DHTP server saying。

 well， I'd like to request that configuration you offered me。And then， the server。

Sense an acknowledgement saying I acknowledge you can have that configuration。

 this configuration is now valid for the duration of its lease and a client can release it early if it wants to。

 or if the lease starts to reach the end， it does a rere。

 so the request mechanism is both in response and offer but also a way to renew a lease。

So let's walk through an example with a client and two servers。The first step。

 a client connects to the network and it sends a DHCP discoverover message as a broadcast。

This is a broadcast。Servey and serverver B， both here this message。

 there happen to be two DHCP servers that can hear the Discover broadcast and let's say both respond with offers for different configurations here's an offer。

Offer B and offer A。The client seeing these two offers decides that it wants offer B。

And so it then sends a request。To be saying I would like to request the configuration that you offered me。

 Silver B can then acknowledge and say okay， you have it。

 Silverver A doesn't hear a request for the offer， and so at some point then that offer will time up。

Now client A is configured， it has an IP address， it has all it needs to communicate。

If that the lease on this offer gets close to an end， it can re request。And。

Say receive an acknowledgement。And it'll do this know well before the lease expires so now the lease has been extended and then it can also optionally send what's called a release and say。

 oh， actually I'm done with this I'm practice clients often don't do this。

 they just let the lease expire， but sometimes you see it in your control panel you can say release and I'll show you this an example on a Mac in a second。

So here will be a basic DHEP sequence。Our exchange of messages。So I've said you send these messages。

 what do these messages look like， The issue here is you're trying to bootstrap IP you're trying to get the beginning IP configuration before you have any IP information。

And so the way it works is a client sends UDP packets to port 67， that's the DHCP port from port 68。

And it sends these packets， it doesn't know the IP address of the HCP server。

 so it sends them to the broadcast IP address and also makes them come from the broadcast IP address since it doesn't have an IP address。

In cases where the D super piece server is not on the exact same link。

 you can have relays that will forward it across links， and most switches， ettera。

 will actually just forward broadcast packets across all of their ports。

And so the way you bootstrap this is to use the special IP address， communicate using UDP packets。

 then once a node has received， its configuration it now can bootstrap with its own IP address。

And so this is then the message exchange that we see So you start with my imMac issuing a DHSP discoverer and it sends this。

 so here's my source Ethernet address 0454531078 E4 and it sends it to the Ethernet broadcast address so all ones。

The source address is  zero to0 to zero， the source IP address， the destination IP address is 255。

 255， 255 255。And you can see it's sending it from source port。

 UP port 868 to destinationation port 67。And if you look inside this message， right。

 thiss basically just the basic DHCP。Discover message。Send it once， doesn't hear anything。

 so it retries after a second， doesn't hear anything。

 so it retries after another two and a half seconds， then it hears two offers。

Which perhaps might be a response to these two different discoveries， who knows。

You say the same transaction。So this first offer is sent from 1033。0。2 to IP address 1033。1。94。

 the second one is 1033。3。1188。But if you look inside the ethernet frame。

 these are being sent from some device and they're being sent to my ethernet address。

 so these are offers。That are sent in response to my discover， you can also tell by the trans。

And so this is destined to this IP address because my node knows that it doesn't have an IP address。

 this turns to be part of in fact information。And so here here's the reply， the offer。

And there's all this configuration information that's basically saying there。

 I'm offering you an IP address of 1033。19。94， which maps up here at 10。33。1。94。

And same in the second one， you'd see that it was offering to 10。33。188。

 so you've got two different IP addresses you might want。

It turns of all kinds of options in this message， it's also going to tell me the subnet maskask 25555。

48。0， it's also going to tell me the router， 10。33。0。1。

 and it's also going to tell me the domain name server。

It's going to tell me that my domain name servers here are three servers that I can use， 17164，755。

 121 and 99。So it's going to tell you your domain name， oh， you're in Stanford。edu。

And so that's what these offers contain， all this information which I can use to configure my host when it starts up。

Then in response to one of these offers， I send。My device sends a DHCP request。

And so now it's sending again， here's from my address， sending as a broadcast。

 it broadcasts its request。And if we look， which IP address did it choose？

So here's all this information， all these flags， options。Prameter request list。

So I'm requesting a certain subnet mask router， a certain subnet mask， a certain router。

 domainminium， so， et cetera， et cetera， and so you can see here that my node ended up。

Requesting the first offer， so 10。33。1。94。And it also ended up requesting a host name， Phillips Iac。

So it's saying， hey， I would to respond to the request。

 I would like to request the offer that you made for 10 to 33。1。94。

Then the DHCP server acknowledges that and all is well。

And so now if we open up my network control panel。

![](img/1265e6012f65545010d7103565ed734f_2.png)

Oh look。Let's look at what。Configuration is。That's in fact what we see so my IP address is 10。33。1。

94 my sub mask is 25555248。0， my letter is 10。33。01 and if we were to check my host name would be Phillipsimac。

tanford。edu。

![](img/1265e6012f65545010d7103565ed734f_4.png)