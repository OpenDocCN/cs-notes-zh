# IBM网络安全分析师专业证书课程4：《网络安全与数据库漏洞》｜network-security-database-vulnerabilities｜ - P13：12_地址解析协议.zh - GPT中英字幕课程资源 - BV1RN411q7PY

![](img/ec71b52ce862e8227017779f79aad6ff_0.png)

Yeah。In this video， you will learn to。Describe the address resolution protocol and how Arc tables are used in network routing。



![](img/ec71b52ce862e8227017779f79aad6ff_2.png)

Let's go a little deeper into Ap。 the address resolution protocol。

 This protocol is really quite simple。 Ap takes an I P address's input and returns the Mac address of the computer that the I P address is assigned to。

We're going to take a look at the ap table on the Linux router。

But you can see the ap table on your own Windows， Linux or Mac OS S X system by running the Ap minus a command in a terminal or command prompt window。

This Linux router has its own set of commands to show this information。

 So I'm going to run an I neighbor show command。This displays all of the Mac address information there is on this device for this IP P address。

1，72 do 16 do 52 do1 is connected to E NP 0 S 8。And it has a logical or Mac addresses as shown here。

And we can see that ENP 0 S 8。Is within the broadcast domain or local network。So this is E N P 0 S 8。

 And you can see that 172 dot 16 dot 52 dot 101 is the cider range。

Let's say that we want to ping a device within that network。

 but we don't have translation of the I address or Mac address working。

 Let's see what actually happens。So I'm going to start a TCP dump on the interface， E NP 0 S 9。

On another screen， to capture traffic information。We're going to pipe this to a Pcap or packet capture file and then leave it running。

Before we do anything， let's quickly recheck our arc table。Now。

 let's ping a device that's not listed in our a table。1，92 dot 1，68 dot 52 dot 100。

 And then let's see what happens。We can see that that ping is successful。

Now it's time to stop the capture and see what we caught。Transferring that Pcap to my desktop。



![](img/ec71b52ce862e8227017779f79aad6ff_4.png)

Okay， great。 Here it is。So the first thing that we're going to see is that before Ping can be successful。

 the computer needs to get the physical address of the target IP address because a packet is never delivered to an IP address。

 but always to the physical or Mac address。So the first thing a computer does when trying to ping an IP address。

 192。168。52。100。Is to try to find its Mac address。 See your computer queries。

 All other computers on its local network。 You can see the source addresses here and the destination is broadcast。

 So this frame will be sent to all other device in its broadcast domain。

 Whoever has the address 198 162t 52 do 100， is supposed to let us know if that device exists on our network。

 i。e。 who is this Ip address。 And this is my computer，192 do 168 dot 52t 4。

 that's initiating the ping。 The address you need to respond back to。



![](img/ec71b52ce862e8227017779f79aad6ff_6.png)

If I go again to the router， I was logged into and inquire。 You will see that this is my I P address。

 So this is me asking， who has this I address， I'm trying to ping。 And fortunately。

 for the sake of this demo， we do receive an answer。



![](img/ec71b52ce862e8227017779f79aad6ff_8.png)

The answer here on line too comes from the computer with this Mac address。

And the message is sent to my Mac address， which you can see here。

So the message says 192 do 168 dot 50 do 100 has this Mac address。

Once we have our own arb table populated with that translation， then the p can be transmitted。

Here you can see the Internet control Mesage protocol or ICMP Echo request。And an ICMP reply。

So this is how the address resolution protocol works to translate IP addresses into the Mac addresses needed for systems to communicate。

Here is an example of an ap table from a Windows machine。On a Windows machine。

 you issue the command Ap minus a in a command prompt window， and you will see the ap table。

We can also see this data on a wire shark packet sniffer。

 You'll see the same thing we saw earlier when showing the live packet capture。

This is an example of a response， which we can see here。If I select this packet。

You can see the address， resolution protocol， and the reply。As you can see， this is IPV4。

 and this is the source Mac address for this packet。 This is the source IP P address。

 and this is the destination。 In this case， it's our router。

 and you can see that it has for a destination， our I address， and also our Mac address。

Something important to keep in mind。 the Mac address of the destination is only required to transmit data within the same broadcast domain。

 When we're sending packets to a different broadcast domain。

 the only Mac address that we need is the Mac address of our default gateway。

 which in this case is our router。 For this reason， Let's look at the routing table。



![](img/ec71b52ce862e8227017779f79aad6ff_10.png)

![](img/ec71b52ce862e8227017779f79aad6ff_11.png)

In this case， our default gateway address is 10。0。4。2。If we want to ping Googleogle。com。

 we do not need to find the Mac address of Google。com。

 but we do need to get the Mac address of our default gateway。Which is 10 dos，0 do4。2。

Justre a double check。Yes， we have it。So to sum up。

 the ART protocolto works to find machines within the same broadcast domain。



![](img/ec71b52ce862e8227017779f79aad6ff_13.png)