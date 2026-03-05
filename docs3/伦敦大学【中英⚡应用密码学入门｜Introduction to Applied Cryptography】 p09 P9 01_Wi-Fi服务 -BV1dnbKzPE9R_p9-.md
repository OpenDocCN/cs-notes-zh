# 伦敦大学【中英⚡应用密码学入门｜Introduction to Applied Cryptography】 p09 P9 01_Wi-Fi服务 -BV1dnbKzPE9R_p9-

![](img/ddf7a3762f01a30cb15718b2a56fb947_0.png)

🎼So what we're going to do， well you're going to do mainly。

 is go through the biggest six applications and identify which security services they need。

And really， this would just be an exercise of going through the main security services we talked about。

And providing an argument as to whether or whether or not that particular security service is required。

So what I'm going to do is go through the first one， give you an example of the kind of reasoning。

You might want to apply to the others， I'm going to go through Wifi。

And think about the different security services it needs。And then the others。

 I'm going to leave to you。So before we quickly run through the services for Wifi。

 let's just remind ourselves why we are securing Wifi at all with cryptography。

And remember that in the past computers were connected using wires。

Wifi allows the connections to take place without these wires。

And so that's the frame of reference we should keep in mind when we're thinking about what security services might be needed。

So let's just run through the main ones， let's start confidentiality。

Should we provide confidential for a traffic pass over a wfi connection？The answer is absolutely yes。

 this is a very important security service。When computers were connected by wires。

 you couldn't access the information unless you tapped that wire now you can tap wires。

 that's possible， but it's hard work。On the other hand， as soon as they go wireless。

 it's very easy for anyone who's got a scanner just to listen in。

So the security of wires has been replaced， the physical security of wires has been replaced by nothing。

 and so we need to put the wire back in a virtual wire and cryptography is going to be used to provide that so confidentiality absolutely very important。

대이전 살지。Do we need that well once again， it's possible to mess up information on a wired connection。

 but it takes a bit of work， you have to tap the line then you have to insert traffic and it's possible but a bit messy。

But nonetheless， the wires are preventing that attack by and large。As soon as we go wireless。

It would be easy to modify a traffic that's being passed across the network。

 so we definitely do want data integrity。The question is might we want even more， what about data。

 origin authentication， would we want that？So do we want to make sure we can also be confident that？

The traffic that's being passed across is coming from the other end of the Wifi network， yes。

 probably we do we're exchanging a lot of data on Wifi。So yes， we wanted integrity。

 but we probably want that stronger version of it， we want to be confident that。

The data is is arriving safely from the devices connected to the network and likewise stuff that's being passed over from the router is not modified。

 So yep， data origin authentication for the same argument as confidentiality。

 we had that property when we had a wire。We potentially lose that property when we tear the wire away so yes。

 please， so in fact we want data origin authentication。What about even stronger non repudiation？

So how to think about this， well， is it possible， think of your home Wifi。

 is it possible that you end up in a dispute？Between。

Your laptop or your phone connected to the wfi and the router about who sent information where。

I don't think that's very likely in that environment。

It seems very unlikely there's going to be a big argument as to who sent， what， when， where， when。

 how。So nonreudiation seems to be a bit much and I think in fact it would be unreasonable to expect nonreudiation is's not something we're going to want on Wifi Now notice I'm not saying we're not saying that there aren points at which you would want nonreudiation when you're exchanging data on a Wifi network。

But what we are seeing is that if you did want that。

 that should be provided at a different level somewhere up in the application layer of an application。

 so for example。If you are。Exchanging a contract over your wfi or using the wfi the data is passing over there and the contract needs a signature。

Then yes， that should well be digitally signed， but it's not the wfi that we'll offer that that will be offered higher up the application level。

So wifi itself。Doesn't need non repudiition， that's too strong。So confidentiality， yes。

 data origin authentication and yes， non repudiation unnecessary。

What about entity authentication now remember entity authentication is this of who's out there question being answered。

So is it important we govern？Who has access to your wfi network absolutelyly So we need rules to make sure that your wfi is only accessed by authorized devices。

 authorized people， authorized devices， So yes， we definitely want to authenticate devices connecting to your wfi。

Is it possible you need to identify that you're speaking to the appropriate router base station？Yes。

 yes， absolutely。 Now the interesting thing here is that when Wifi first came out。

 people didn't think that was the case and so。En authentication was only provided of devices connecting to the Wifi。

 but subsequent to Wifi being released and used， there were all sorts of attacks that were launched because。

You know，Res were not authenticated as well and so the generally good practice when you involve entity authentication is as a default。

 authenticate both ends of the communication and there may be arguments in certain settings with us。

not needed， but I think the lesson people learned in Wifi was that that is necessary。

 so in fact we want mutual and authentication devices should authenticate or' talking to the right network。

 the network should authenticate devices that are connecting to it。

So that's the run through confidentiality， yes， definitely integrity， yes， in fact。

 the stronger version of data origin authentication， yes， non repudiation。

 too much not really needed。And stiff education， absolutely。That's the security services for Wifi。



![](img/ddf7a3762f01a30cb15718b2a56fb947_2.png)

🎼。