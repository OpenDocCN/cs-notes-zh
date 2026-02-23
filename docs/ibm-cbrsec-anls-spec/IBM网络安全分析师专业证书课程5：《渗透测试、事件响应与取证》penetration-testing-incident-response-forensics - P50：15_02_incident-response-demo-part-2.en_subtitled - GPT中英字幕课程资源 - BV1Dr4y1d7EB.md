# IBM网络安全分析师专业证书课程5：《渗透测试、事件响应与取证》penetration-testing-incident-response-forensics - P50：15_02_incident-response-demo-part-2.en_subtitled - GPT中英字幕课程资源 - BV1Dr4y1d7EB

Welcome to Incident response demo， part 2。Brought to you by IBM。

Cator offenses are created when a rule is triggered and the action is set to create an offense。

As you can see， we have free offenses listed in the curator interface now。

This is the curator Ats interface。Inside the curator offense interface it lists out any offenses that the curator rules engine has alerted on。

 we have a few different ones here， the quickest way to determine priority is by the magnitude。

And we can look at that by just placing our mouse over the bar graph， as you can see there。

 the first one's a magnitude five。Second of magnitude4。These are all going be the same。

And then this last one's a magnitude 3。 So let's go ahead and check out the magnitude5。

After we click into the offense， we're given a summary page on the summary page it gives us。

All kinds of different details， including the top five source Is， the destination Is。

 which log sources were involved in the event。As well as the categories of the events that were used to create the offense。

One of the main things to look at on this page is the top five annotations。

The very first one there is malicious URL detected For this instance of Q radar。

 we actually have a role that。Is built to compare DNS queries against a reference set。

 and that reference set has multiple malicious URLs in it。

If we wanted to drive down further in this event， we can click on the events。

And we can see the different events that were triggered。So it was the DNS in progress。

To the D server。And once key radar seen that， it compared it to the reference set。

 it created its event and also created the offense。

Al it's now that we've seen the events that caused the offense。

Let's go ahead and search this DNS name out on X4 exchange。And see if it is rated as malicious。

 which it should be since it isn't a reference set。Im那生。

Some things have happened and somebody else is now hosting that site or somebody else now owns it。

Right away out here on Ex Force exchange， it's listed as a risk 10。This one does have a collection。

I've already opened it up here， so we just got like put over to it。And for this URL it's。Useed。

As part of a malware ex frustratingrating credentials via the NS attack。

And one of the command and control service for this is。Wever。co。Readデです。Those appear to be malicious。

I just on back the the key radar and seeing。So now that we've confirmed that it is malicious DNS。

Quary， we're going to jump into those events again。And。Infirm that。The query actually didn't happen。

Right away， I see that the destination IP is one that's not in our private network。是在聪明的但。

The N S address was resolved。And it results back to the 192203230。

10 address at this point I would kick off the incident response process beginning with step two since I've already prepared my asset list as well as my shareholders to contact。

And the events to figure on。Alrighty， so I want to ahead and put on my incident response form here。

 this is just a template and to be honest they all look different。Some of them actually are in open。

The first thing here is the type， the type of incident the type of incident。 I want to put。

DNS query to known bonnenet。I have the detection source with key radar。The environment was the land。

The host name was live PC2。Sing the IP address。In this case， it says multiple。

 but the reason it says multiple is because the workstation queried the DNS server。

 and then it queried the secondary DNS server， then those DNS servers queried the outside world to resolve that DNS。

So we want to pick the workstation IP as it's the one that's affected。

And then lets know if it's a web server so。Oh， the system。Is a workstation。In the public IP。

 fortunately， our lab doesn't currently have a public IP。So for the public IP。

 I'll just make up one and let's use Google's DNS server。

The next step is to start writing down the time we find information and we complete part of the incident response process。

So the next thing that we do is begin recording what time we found information。

So the first thing that we。So the next thing that we do is begin recording what time we found information。

So the first thing that we， we determined was that。It was a malicious DNS query。No that was was Dina。

Well go aheadt copy that in there and then。Continue on。

 so we found out the DNS query came from our workstation so we can put workstation and then the IP of the workstation。

We able to host name in there if we know it as well。Identify the asset That is。Being malicious。

 identified that it is a malicious URL， we identified that it did actually go out。Make that request。

And that the request was successful， it was resolved。The next step would be to。

Go ahead and disconnect it from the network， so to do that， we would want to submit a ticket。

And have them disconnect the workstationationss switchboard。Or if it's something that's physical。

We can walk over and unplug it and then circle back with the network team to have them。

Disable that port So once we submit that ticket。them they disable it。

Then we can go ahead and get started。With the antivirus scan， and。Closing up the incident， if it's。

It doesn't need reimd。However， in this case， since it did reach out to a botnet。

Even if the AV scan comes back is clean。I still think it's a good idea to go ahead and reimage it。

fin。One of the reasons that wed want to conduct a AV scan。

Thein with this is to determine if something else is already on there。

Maybe OES isn't actually detecting。嗯。The virus。And it just needs a full scan to be detected。Once the。

Switchboards disabled with and。Kick off our AV scan。So once we have our ENS skin kicked off。嗯。

We want to go back and we want to tidy up this document， just going to pretend like that。

Maybe skin come back。It was clean。After that， I would go ahead and make the call to。

Through even just a device since it is a known bo and control network。

So we don't want any chances of that being part of our local network。

 we don't want it to infect other hosts。Or become part of that bonet itself。

And since it is just a workstation， it's not anything。Super critical。It can be reset。

 reimaged pretty quickly， and no harm'm done。And after that， I would send this information up。

Allow them to process it， and。Archiive it。So we have it。 We know what。

 what had happened on this stairs。Once we're completed our investigation。

 we want to go and close the incident。We can。Go and select a response。

And we can paste our incident response form in there。And close the ticket， close that offense out。

Once it's closed， it will no longer show up in our active offenses。

And then we can move on to the next offense。So since these all three are the same magnitude。

 we definitely want to check out the older one。In case it needs a faster response。嗯。

W out and click on the offense on the summary tab again， we can see the offense source is。

This IP address， which is a workstation as well， is actually the same workstation as the last defense。

And we can also see that。The long sources that were part of the offense was Q radar as well as the firewall。

And we can see the events。That we used to create this offense。

We're session open and session closed events。And in the innotations， it says that it's a possible。

DD U attack。So we definitely want to check this one out。 We'll go into。Events。

And since this is a a local to local attack， it's a little less。

Relevant typically when you see local to a local。De also attacks， its， it's just a user that's。

Doing his daily job。For instance。This user is actually。Working with this server。

To develop an application using an API。 So it's expected to see multiple 4。

43 session open session closes to that system from that workstation。So therefore。

 this incident would be a false positive。A false positive is triggered。

 even though the events are typical， they're you know， normal traffic。

 it might just be something that's。Beginning to happen or maybe it's a new server that stood up。

And the roles just arent here， the rules haven to been modified。In that case。

 we would want to go ahead and just tune Q radar that means that we can go ahead and make it。

We can go ahead and close the offense。And。We're going to close it as a non issue。

 a non a false positive just because we want that rule to stay in curator。Once we modify the rule。

 we want to come and make a comment。To say that the threshold was increased。

If that's how you modified that rule to lessen the amount of false positives you did。



![](img/f212447a5197576333845a3fe2c57874_1.png)

You'm going to click OK， he closes that offense out。



![](img/f212447a5197576333845a3fe2c57874_3.png)

![](img/f212447a5197576333845a3fe2c57874_4.png)