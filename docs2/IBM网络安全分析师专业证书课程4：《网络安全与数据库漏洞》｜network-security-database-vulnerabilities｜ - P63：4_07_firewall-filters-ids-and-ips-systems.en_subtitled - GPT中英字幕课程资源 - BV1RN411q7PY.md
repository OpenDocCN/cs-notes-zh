# IBM网络安全分析师专业证书课程4：《网络安全与数据库漏洞》｜network-security-database-vulnerabilities｜ - P63：4_07_firewall-filters-ids-and-ips-systems.en_subtitled - GPT中英字幕课程资源 - BV1RN411q7PY

![](img/fece4263b3fd2882e6041dd347c47ada_0.png)

Yeah。In this video， you will learn to describe intrusion detection systems， IDS。

 and how they are used to detect vulnerability exploits on a network。Describe intrusion。

 prevention systems， IPS， and how they are used to actively protect against vulnerability exploits on a network。



![](img/fece4263b3fd2882e6041dd347c47ada_2.png)

This is a symbolic representation of a juniper brand firewall。

 Many modern firewalls and network devices have a control plane and a forwarding plane similar to this。

The forwarding plane is in charge of forwarding all traffic and making all the routing decisions。

 the policy evaluations， the session matching and so forth。

This is done in a manner that does not interrupt the control plane。

 which is in charge of running the operating system， which controls the device and the routing table。

 If something happens to the control plane， the device will still forward traffic since the forwarding plane will still be running。

Let's talk a little about IDS or intrusion detection systems。

An IDS is a network security technology that is designed to detect vulnerabilities and exploits against targeted servers。

 applications， or a computer within our organization。By default， IS just listens to traffic。

 It doesn't take any action。In most cases， an IDS is a dedicated server that's connected to a port on a switch。

The switch forwards a copy of all traffic flowing through it to its IDs。

The I monitors the traffic looking for anomalous behavior。

 and when found sends an alert to the administrator。While， an I D S won't take any action by default。

 Moern Iss can be configured to run scripts that can send a command to the router to block an I P address if an anomaly is detected。

But normally， an IDS will just send an alert to an administrator to let the administrator know that something anomalous is happening in our network。

 and then it's up to the administrator to initiate any required action。Now。

 let's move on to intrusion prevention systems or IPS for short。

 The primary difference between an I and an IPS is that an IPS is designed to take action on its own when an anomaly or an offense is detected in the network。

 Another difference is that the IPS does not just listen to a copy of the network traffic。

 but all traffic must pass through it before it's allowed to move on。

One disadvantage is that it adds a delay to the flow of network traffic。

An IPS S is usually positioned right after a router， edge device or firewall。

 and some firewalls are designed to also function as an IPS S， Unlike intrusion detection systems。

 an IPS S is not a passive listener。 It's going to be an active listener and it can take action if an anomaly is found in our network。

IS and IPS systems commonly use one of four ways to detect threats。

 IS and IPS systems both maintain a database of signatures that are used for signature based detection。

 these signatures describe common patterns of network traffic that may indicate the traffic contains some malware which warrants raising an alert。

 anomaly based detection is another way to detect a threat in the network。

 Each network protocol goes about its work in a characteristic way。

 If we find traffic that does not follow the standards of its protocol。

 This may indicate a threat is present and an alert is raised。 For example。

 if there are a lot of halfop TCP sessions or HTTP traffic that's not arriving with a right header or arrives with an unexpectedly long header。

There are also host based intrusion detection systems or HS。

 These are software based applications designed to protect the computer they're installed on against attack。

 The HS listens to the traffic being received by and sent from the endpoint。

 which triggers an alert or actions is appropriate。

 A network based IS that listens to a copy of network traffic from a port mirror configured to the core switch。

 Well a network based IPS sits in the middle of the stream of traffic。

 both trying to find anomalies in the data stream。The main difference between a host based and a network based system is that the host based system is a piece of software installed on an endpoint machine。

 while the network based system is a piece of hardware that listens to all traffic that is sent to it or flows through it。



![](img/fece4263b3fd2882e6041dd347c47ada_4.png)