# IBM网络安全分析师专业证书课程4：《网络安全与数据库漏洞》｜network-security-database-vulnerabilities｜ - P85：26_04_port-mirroring-and-promiscuous-mode.en_subtitled - GPT中英字幕课程资源 - BV1RN411q7PY

![](img/4a6eff4309a28f52c0dc970ebb848762_0.png)

That。In this video， you will learn to。Describe what is meant by port mirroring and how it is used。

Describe promiscuous mode and its legitimate and illegitimate uses。

 The last thing to cover in this lesson is port mirroring。



![](img/4a6eff4309a28f52c0dc970ebb848762_2.png)

Port mirroring very simply is when a switch is configured to make a copy of all the traffic traversing one or more ports on that switch and send the copied packets out to a single destination port。

 Port mirroring on a Cisco switch is generally referred to as switch port analyzer or span。

 There is also remote switch port analyzer or R span。

 which allows the destination port to be remote or on a switch other than the one that's doing the collecting。

 Different vendors use different names for port mirroring3com， for example。

 calls it wrap for roving analysis port。 The benefits of being able to make and use a copy of all network traffic crossing a switch for network analysis purposes。

 or to debug errors on a network are obvious。 But I hope by this point。

 your instincts will tell you that this can also be very dangerous。

 Imagine the trouble it might result if an attacker could access a major switch within an organization and set up port mirroring to send a copy of all network。

ffBack to their own servers for exploitation without being detected。 Most of the time。

 the mirrored packets will be sent to an IS or intrusion detection system that's connected to the destination port for analysis。

 The Is will be configured to monitor all the traffic in real time and send alerts if any anomalies are detected。

Remember that an IS is off to the side working on a copy of the network data only。

 This means that the Is will not slow down the network。

 but it also means that it cannot act directly on what it's found like block the delivery of a packet。

 but it can only send out an alert to raise the alarm about what it's found。

 The endpoint or server that's being fed the mirrored data has to have a ni or network interface card that's running in promiscuous mode。

 so that it can read all of the frames it's receiving。

 Remember that these frames all have destination Mac addresses pointing to other systems。 So a ni。

 not in promiscuous mode would simply ignore them。 Just to reiterate for an Is or other network analysis tool to work。

 It must have a nick that's configured in promiscuous mode so it can read all of the frames that are sent to its incoming port。

 Otherwise， it cannot read the frames and perform its analysis。

 When you use a port s sniffer like wire shark wire shark will put your ni in promiscuous mode for you so it can capture all of the traffic that。

Across its interface， Thank you。

![](img/4a6eff4309a28f52c0dc970ebb848762_4.png)