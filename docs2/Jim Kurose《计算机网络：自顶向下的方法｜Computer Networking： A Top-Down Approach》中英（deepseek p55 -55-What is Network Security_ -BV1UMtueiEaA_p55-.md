# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p55 -55-What is Network Security_ -BV1UMtueiEaA_p55-

Welcome back， today we'll be asking the question what is network security？

We'll discuss what we mean by network security as opposed to other types of system security or specialized fields like cryptography。

Let's get started。

![](img/41d19ca37ae559e8576e2c950fe10e2f_1.png)

So welcome back， it's been a little while since I recorded one of these videos and a number of folks had asked if or when I would do some topics on network security。

 so that's what we're starting on today， I'll do four or five lectures covering the Kroa Ross chapterpt 8 and as before we're using the slides provided by Krosa Ross。



![](img/41d19ca37ae559e8576e2c950fe10e2f_3.png)

Before we get started on specific topics included in chapter 8。

 I wanted to give a little more context about what we mean by network security。

So we need to recognize that we're picking and choosing specific topics in which the networking context plays a larger role in the way the security aspects of the system are implemented。

And there are many other aspects to creating a secure system。

Everything from physical security to details of cryptography。Application design。

System architecture itself avoiding critical points of failure。

As well as enumerating all of the different types of attacks and challenges that may constitute the threat model against which we design these security systems。

So in this chapter， not only is it network security。

 but we focus on just the most commonly used aspects of network security。

And there are additional more advanced topics that the Kserros chapter doesn't really get into。

 but I also have a list of those and may do some follow on videos on topics like wireless network security。

So with that being said。Let's look at the topics Curs and Ros have in store for us。

First we're going to have an overview of cryptography and we should note that the networking field is essentially a customer of the cryptography field。

 there are experts in designing cryptographic protocols that make and standardize these things and then network protocols implement those cryptography standards。

 so we're not going to be looking at the details of the math behind the cryptography。

 rather we're going to be looking at how we use cryptography in the networking context。

Then we'll look at authentication as well as message integrity。As a side note。

 message integrity means that the message can't be changed without the receiver knowing that it's been changed。

 messagesage integrity does not mean that third parties can't read the message。



![](img/41d19ca37ae559e8576e2c950fe10e2f_5.png)

Once we understand those basics， we'll go on to look at specific examples of network protocols and applications and how they implement security primitives。



![](img/41d19ca37ae559e8576e2c950fe10e2f_7.png)

In the rest of this video， we'll just cover the basics about what we mean by network security。



![](img/41d19ca37ae559e8576e2c950fe10e2f_9.png)

Probably the first thing that comes to mind when we talk about security is the idea of confidentiality。

 which means that third parties should not be able to read the messages sent。

 only the sender and the receiver should know the contents of the message。

This is achieved by encrypting the message at the sender side and decrypting the message at the receiver side。

And the mental model is that we have bits that make sense on the send side。

 they get scrambled into something that doesn't make any sense to a third party that may be observing the message sent across the wire。

 and the process reversed at the receiver side。However。

We have to note that in order for this to happen， there must be a shared secret between the sender and the receiver or the encryption key。

And that is where network protocols tend to get into trouble is in trying to exchange that shared key in a manner that it cannot be intercepted by a third party or that they don't otherwise weaken the security of the encryption。

We also have authentication if you're familiar with the term AAA security。

 authentication is the first A。This is the idea that we want to confirm the identity of one of the actors。

 the sender or the receiver。The other A's of the AAA security， of course。

 are authorization and accounting， which are concepts that we don't think about as often today。

 but in practice are used all the time。For example， from the service provider perspective。

 they want to authenticate that the user is the person paying them for service。

And then they'll check using authorization to see what services that user is eligible for。

And finally， account for how much of those services the entity uses。Okay， but back to basics。

The third application common to network security is the idea of message integrity。

And that we might not care if this message is read by third parties。

 but we want to make sure that it actually says what it's supposed to when it arrives at the receiver and that no one's been able to change it along the way without us discovering that。

We also have the issue of access and availability。And the trick there is that it must be available to all users。

 including non technical users， so these security mechanisms must be seamless and automated。

In a way that anyone can benefit from them。

![](img/41d19ca37ae559e8576e2c950fe10e2f_11.png)

So now let's see some examples。Here we've got Alice， Bob and Truy。

So Alice and Bob want to communicate with each other securely。

 and their definition of securely means their messages are kept secret。

Our attacker here at Trudy can accept， delete and add messages as they pass across the network。



![](img/41d19ca37ae559e8576e2c950fe10e2f_13.png)

Now of course， Alice and Bob aren't just real life people named Alice and Bob。

 they represent all different entities that might be connected to the network。A very common one。

 of course， is e-commerce， the electronic transactions where purchases are made。

 where credit card information or other forms of electronic payment are transmitted over the network。

 and if a third party were able to intercept those。

 they may be able to steal from the user financially。Another example is online banking。

 where private details about the user's financial state are communicated over the network and exposing those details might also expose the user to financial loss。

Another application that doesn't get nearly as much attention as it probably should is DNS servers。

While many people are not familiar with the idea of having end to end encryption when communicating with websites and looking for the green HttPS or lock or whatever it is in the browser。

 what they don't realize is that before that connection was made。

 their computer sent out a DNS request for that particular website and that DNS request was sent in the clear。

 as we've seen with the DNS protocol， it does not provide any security。

 and so not only did their ISP and anyone else who was paying attention on the path know what website they are planning to go to。

Even the answer could have been changed， so a malicious actor could rewrite a DNS reply and send the user to a different IP address than the one that the DNS server actually provided。

And so this is a large vulnerability， we do have the DNS S protocol。

 but it's not nearly as widely used as something like HTTPS。

Another example might be routers that speak BGP exchanging routing table updates。Again。

 that's an example where if they were not encrypted。

 a malicious actor might be able to change them and use that to tack traffic in some way。

And we can think of many other examples， something like a whistleblower that needs to get information out without being detected。

Or a reporter or other social justice actor that needs to be able to communicate without having their messages either changed or read in transit。

And of course， the list goes on and on。So we keep mentioning these attackers or bad guys what have you。

 but we haven't really said what our threat model is， right， what is it that the bad guy can do？

And the answer is quite a bit。The simplest is probably edropping。

 just intercepting the messages and reading them。A more advanced capability would be to insert messages into the connection。

And beyond that， perhaps impersonation， actually faking source addresses so that messages appear to come from someone they didn't。

We also might think of hijacking， so not just intercepting the communication of the ongoing connection。

 but actually taking over one end of it and replacing the sender or receiver。And lastly。

 we have the denial of service。Not meaning a Diddos attack， specifically。

But any action that prevents the connection from being able to continue and achieve its desired service goals。



![](img/41d19ca37ae559e8576e2c950fe10e2f_15.png)

Okay， that wraps up our brief introduction and in the next video we will look at the principles of cryptography。

 see you then。

![](img/41d19ca37ae559e8576e2c950fe10e2f_17.png)

We hope you enjoyed this video， if you found it to be useful。

 please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

