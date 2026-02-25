# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p63 -63-Firewalls and Intrusion Detection Systems (IDS) -BV1UMtueiEaA_p63-

Welcome back in this video we're looking at operational security using firewalls and intrusion detection systems。

Within firewalls， we'll look at both stateful and stateless packet filtering。

 as well as application gateways。Let's get started。



![](img/827e3e6aa251e02514768e9ad77cefaa_1.png)

In this video we'll be looking at operational security。

 meaning firewalls and intrusion detection systems。

The name for these devices that we've used previously in the course is middle boxes。

 devices that look at multiple layers across the network stack。

 even though they sit out in the middle of the network。Statistically speaking。

 middle boxes and modern networks are nearly as common as routers。



![](img/827e3e6aa251e02514768e9ad77cefaa_3.png)

A firewall is a name for a middlebox that isolates our internal organization's network from the larger public internet。

And it determine that some packets should pass through and others should be blocked。

Usually there is a concept that those on the inside of the network are trusted and those outside the firewall are untrusted。



![](img/827e3e6aa251e02514768e9ad77cefaa_5.png)

So what are some of the attacks that firewalls try to prevent？

A common one is denial of service attacks。An attacker sending floods of sin messages or other messages designed to tie up resources on the victim host there also supports to prevent illegal access to internal data。

 so protecting intellectual property of some form，It could also protect things like the public face of the company。

Where a hacker is trying to replace parts of the web page。

 either to defface it or to use it for some nefarious purpose。

We can break firewalls down into three categories。Stateless packet filters。State full packet filters。

And application gateways。These are roughly an order of complexity。Where as you go down that list。

 the mechanisms of the firewall become more complicated and more CPU intensive and may also have a greater impact on the performance of the network So our first case is stateless packet filtering。



![](img/827e3e6aa251e02514768e9ad77cefaa_7.png)

These are where rules can be applied packet by packet。

 and they make the decision to forward or drop a packet based only on the properties of that individual packet。

Things like the sourceur and destinationest IP address。

 TCP and UDP sourceur and destination port numbers。ICP message types and TCP flags。

 so this is the most primitive type of firewall。And while it will catch many issues and block unauthorized traffic。

There are also things that it can't do and we'll see that when we look at the more complex types So for example。

 a Iwall might't be configured with a rule to block incoming and outgoing datagrams that are using TCP source or destination port 23。

 this is Tent and many organizations block Tent because usernames and passwords are transmitted in the clear and so they don't want their users inadvertently using Tnet to remote site and sending out of password。

 which might or might not be the same as a password that's important to the entityity or revealing even the username。

We also see that there's a rule in this fire while blocking IP protocol field 17。

Wwhich is the UDP protocol， so this farwall is also going to block all UDP dataograms and of course。

 the most common application to use UDP is DNS， so this is preventing users inside this network from accessing DNS servers outside the network。

 another common security policy。Another example rule might be to block inbound TCP segments with AC equals0。

Which is intended to prevent external clients from making TCP connections with internal clients。

But it doesn't apply this on outbound TSP segments so it wouldn't prevent internal clients from connecting to the outside。

However， given that we know that initial sequence numbers are randomized by modern operating systems。

This is likely to not be very effective。And it might be better to look at the S flag and act flag and make a decision based on those Here are some more examples of rules that we might use。



![](img/827e3e6aa251e02514768e9ad77cefaa_9.png)

If we wanted a policy of no outside web access。Then we could drop all the packets going to TCP part 80。

Of course， many websites are using HTTPS on port 443， so you would also have to drop those。

If we wanted to block incoming TCP connections so new connection establishments。

 accept those headed for the web server。We could have a rule that saysDrop all incoming TCP Ss。

 except for specific web server IP address and port numbers。

We might want to block web radios by blocking UP packets。

 although most streaming media have migrated to run over HTTP。

 so that's probably not going to block much and as we see in that case if we wanted to still allow DNS。

 we would have to explicitly permit that。Another policy might be to prevent the institutional network from being used as part of a SmF doOS attack。

 which could be done by dropping all ICV packets going to a broadcast address。

And our last example is to break Tro， and this can be done by dropping all outgoing IMPTTL expired messages。



![](img/827e3e6aa251e02514768e9ad77cefaa_11.png)

So these rules are going to be implemented as a table commonly referred to as an ACL。

 an access control list。An access controllers have been around forever。

 and this is essentially what Openflowlow forwarding decisions are based on。

 only with more fields available in the Openflowlow case。

Now these rules are going to be applied in order， so the first one that matches is going to be applied to that packet and it will not see the rest of the table。

So for example， we're allowing any packet on this s16 address that's dust outside of that address where the protocols TCP。

 the source port is an ephemeral port and the destination is 80。

 we're going to permit that so these are outgoing web traffic。

And then we also have to allow the incoming web traffic， not new connections。

 but the responses to our outgoing connections， so we see that rule looks very similar but reversed。

 so it's allowing sources outside of the network to contact destination addresses inside the network。

 a protocol TCP where the source port is 80 meaning it's coming from the web server and it's deted to an eemeral port。

And it has the a flag set。You're also allowing UDP import 53， so DNS traffic and the responses。

And then we're denying everything else。So it's common for an ACL to have an explicitlicit deny at the bottom or an explicit deny rule。



![](img/827e3e6aa251e02514768e9ad77cefaa_13.png)

So here we get to the limitations of stateful packet filtering。

And it's primarily that the tool not very sophisticated。

 so there are still packets that can get through this rule set that don't make sense For example。

 we are letting through these acknowledgecknowledments。

 but there might not be a corresponding connection established。

 so it might just be scanning traffic that's been sent out with the ACbit set。

A stateful packet filter keeps track of the status of every TCP connection that's going through it。

So it knows when the connection setup happens， when the teardown happens。

 so it can determine when to remove these connections from the state that is tracking。

It knows whether it's an incoming or outgoing connection。

 and so if a TCP packet comes along that doesn't match one of these existing sessions and is not a new connection setup。

Then it can drop those packets， even if they would otherwise match a rule and be allowed。

The stateful packet filter can also time out inactive connections。

So even if an explicit fin has not happened， the host on one end or the other might have disappeared and so it can remove these from its table and no longer admit packets to them。

Of course， you can cause lots of issues for your network with a Staple packet filter if this timeout is too aggressive。

 such that long with TCP sessions get broken by the firewall。



![](img/827e3e6aa251e02514768e9ad77cefaa_15.png)

So now in our stateful packet filter ACL list， we have the same set of rules。

But before allowing certain packets， we're going to check that a connection exists。

 So in our first rule， we're explicitly allowing set of requests happens。

 so there doesn't have to be an existing connection because we want to allow the sin through with this rule。

 However， in the second rule， we're only trying to allow acts through not any random packet。

 And so these packets should match existing connections。

 So we're going to check it on the second rule。 Likewise with a third rule。

 we're allowing for initial DNS request to go out。 but the response back should match an existing session at that point established by the outgoing request。

 And if not， we're not going to allow those packets in。



![](img/827e3e6aa251e02514768e9ad77cefaa_17.png)

Alright， now we get to the most sophisticated version， which is the application gateway。

So we could think of the stateful packet filter as operating at the transport level it understands end to end flows。

And that there should be associations that packets belong to。

Application gateways go up another layer to the application itself and it understands how specific applications work and what should be allowed or not based on the rules of those application layer protocols。

So in this example， we want to allow some users to tell that outside。

So it's going to require all the Tnet users to tellnet through a gateway。

 instead of teleneting directly to their outside address which would be blocked by the firewall。

 they have to connect through the gateway and if the users authorize the gateway sets up a Tnet connection to the destination host。

 so this application gateway is always going to sit in the middle of the connection from a TCP perspective。

The host established a TCP session with the application gateway。

 and the applicationplication gateway established a new TCP session。With the end destination。

 and by the way， this application gateway has to be allowed through the firewall to get there。

To the router blocks all tele connections that didn't come from the gateway。

 which simplifies its rule set。

![](img/827e3e6aa251e02514768e9ad77cefaa_19.png)

All right， we have some limitations when dealing with firewalls and gateways。

Number one is IPpoofing IP addresses are not validated in any way。

 and so lots of entities on the internet or even on the local network could change the source IP address to someone else's and send out packets。

Another limitation of application gateways is that you need one for each application that needs special treatment。

It's difficult for users to adopt a new application that needs to get through the firewall。

And even the creation of an application gateway may lag far behind the popularity of a particular application itself。

And then the client software for that particular application has to be able to configured to talk to an intermediate gateway。

 the gateway is not transparent。As always， there's trade offs with the degree of security required and the usability and inconvenience applied to hosts on the network。

And even with all of these mechanisms in place， many highly protected sites still suffer from attacks via other vectors。



![](img/827e3e6aa251e02514768e9ad77cefaa_21.png)

Now we move on to intrusion detection systems or IDSs。

And we note that there's a more advanced version of these called IPPSs or intrusion prevention systems。

In general， an IDS or an IPS works on the basis of deep packet inspection。

 so it's looking at the packet contents， not just a few fields in the headers。

 and it can check these contents against all sorts of things， For example。

 known virus signatures or known attacks strings that cause overflows or SQL injection attacks and so on so it could ignore what port number this is supposed to be going to。

 what application it claims to belong to and say is anything in here look like something I already know is bad。

It can also look at a string of multiple packets for correlations or even do reassembly。

 so some of the attackers may be more sophisticated and break up their attack across multiple packets。

And an ID may put those back together before looking for its signatures。

Other types of correlations are things like port scanning。

 so a sequence of packets to a particular destination that's running through a bunch of different ports。

 which isn't typical behavior for legitimate applications or things like network mapping。

 so things that look like Trar either coming in or generating lots of TTL expired messages going out。

Or denial of service attacks， where packets from many different source addresses。

 whether sofed or otherwise， are destined for a single victim IP address。



![](img/827e3e6aa251e02514768e9ad77cefaa_23.png)

We also note here the demilitarized zone commonly known as the DMZ。

It is typical for organizations to put any server that needs to be accessed from the outside into a separate network from their internal network。

And since these machines are more vulnerable because of access from the outside。

 it then helps prevent them from being used to attack the internal network in the event that they get compromised。

The IDS sensors may reside with the firewall， but can also be placed at multiple vantage points around the network。

And should typically sit between the DMZ and the internal network to detect compromises in either location。

However。We wouldn't most likely want to put an IDS outside the firewall because then the IDS will have to process lots of attacks that may be blocked by the firewall anyway。

 and it's much computationally cheaper to block these things with a stateless or stateful packet filter rather than having the IDS be exposed to all of these illegitimate packets。



![](img/827e3e6aa251e02514768e9ad77cefaa_25.png)

So we keep the IDS behind the firewall。This brings us to the end of our chapter on network security。

We started off looking at basic techniques， including cryptography。

 both symmetric and public key cryptography。The concept of message integrity and endpoint authentication。

 and then we saw a number of applications of these。

 and of course these are not the only applications， but some of the most common ones。

 including secure email， TlS for HttPS and other end end encryptryed TCP connections than I S commonly used in VPNs and then just brushed the surface of wireless security。

Seeing how encryption is negotiated for 802 to out 11 and 4G and 5G cellular networks。

And wrapping up with the middle box security mechanisms of firewalls and intrusion detection systems。

I hopepe this has been useful and that's all for now， thanks。



![](img/827e3e6aa251e02514768e9ad77cefaa_27.png)

We hope you enjoyed this video， if you found it to be useful please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

