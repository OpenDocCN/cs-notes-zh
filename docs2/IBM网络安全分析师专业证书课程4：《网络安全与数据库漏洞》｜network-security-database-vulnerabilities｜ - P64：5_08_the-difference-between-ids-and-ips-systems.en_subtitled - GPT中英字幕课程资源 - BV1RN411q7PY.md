# IBM网络安全分析师专业证书课程4：《网络安全与数据库漏洞》｜network-security-database-vulnerabilities｜ - P64：5_08_the-difference-between-ids-and-ips-systems.en_subtitled - GPT中英字幕课程资源 - BV1RN411q7PY

![](img/88deed3765f7bc1009e4b86bad7729e9_0.png)

Yes。In this video， you will learn to describe the difference between network intrusion detection and prevention systems and the advantages of each。



![](img/88deed3765f7bc1009e4b86bad7729e9_2.png)

Let's review some of the differences between an IDS and an IPS。

First is the placement of the device in the network。

The IPS is going to be directly in line in the middle of the stream of network traffic。

The IPS will be tapping our communication while the IS is outside the direct line of communication。

Meaning it's offline or just receives a copy of all traffic sent to the interface。

It is listening in what's called promiscuous mode and analyzing the traffic。

Most of the time this won't cause any delay in network traffic， an IPS， on the other hand。

 is an active system type， meaning it is usually configured to actively monitor network traffic and to automatically defend the network if a threat is found。

For example， automatically creating an ACL or access control list to block traffic that's been identified as malicious。

In passive mode， it acts more like an I D S。 If a threat is found。

 it will notify the administrator and it will then be up to the administrator to take action。

 An I S willt normally take any action other than notifying the administrator of a threat。

An I D S might have a web interface where the administrator can see what has been found。

 I D S and Ips S systems both use the same detection mechanisms。

 They both can use signatures to detect malicious traffic。

 where signatures are basically patterns that can be found in the payload of traffic。

Both types of system can also use anomaly based detection。

 They will detect if a protocols standards are not being followed， indicating a threat。

 or in the case of signature detection that someone is trying to exploit a vulnerability in the network。



![](img/88deed3765f7bc1009e4b86bad7729e9_4.png)