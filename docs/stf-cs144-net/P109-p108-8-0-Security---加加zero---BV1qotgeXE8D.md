# P109：p108 8-0 Security - 加加zero - BV1qotgeXE8D

 So in this unit we're going to be learning about network security。

 Usually when we read about the internet and networks in the newspaper， it's because of。

 some security vulnerability that's been exploited or found。

 Of course we read about them with these exploits and software， but sometimes you read about。

 them at the infrastructure itself。 And these are usually exposed because an individual。

 a company or a country is attacking， someone in order to be able to discover or tamper with their data。

 We're going to start by learning about the types of attack that are quite common。

 There are many ways to attack a network and you're going to be seeing a collection of。

 methods that work in a variety of different ways。 The first and most common one is to simply eat。

 swap or listen on someone else's communication。 In some of networks this is surprisingly easy and you're going to be surprised at some。

 of the methods that I use and can be used。 And we'll even demonstrate some of these to you。

 You can either eavesdrop on a broadcast network like a wireless network or you can。

 force the network to expose or broadcast in a way that will make it easier for you to， hear。

 Another type of attack is to masquerade or behave as if you're a piece of the infrastructure。

 that is providing information back to a sending host。 For example you can forge up responses。

 you can spoof the response from a DHCP server， or from a DNS server and cause a client to send data to a place other than it was thinking。

 of sending it。 So you can either get the data redirected to you where you can look at it and then pass。

 it on which is often called the man in the middle attack or you can make it impossible。

 for the sender to communicate with a particular part of the network and essentially censor。

 or block a portion of the network。 Sometimes you're actually able to hijack an entire end host and masquerade as an end host。

 and therefore completely terminate the communication。

 For example to get someone's credit card information when they're performing any kind。

 of an e-commerce transaction。 Another thing that you can do is to prevent someone from being able to communicate at all。

 This is usually called a denial of service attack by overwhelming the sender or overwhelming。

 the piece of the infrastructure so that the communication can no longer take place。

 The internet is dangerous。 We're going to learn the three principles that you can use to actually secure your network。

 despite the fact that the internet itself might be insecure。 The first is confidentiality。

 Is the idea that we'd like to be able to communicate securely that is hidden from everyone else despite。

 the fact that they might be able to see what we're saying。

 So if you have confidentiality then you can communicate with another party， other people。

 can observe this communication but not be able to know what you're saying。

 Second principles integrity。 So confidentiality lets us communicate without people know what we're saying but people could。

 still meddle with it。 With integrity then we can be sure that our communications aren't tampered with such that。

 the message say that makes sense to me was actually the message that makes sense to me。

 It wasn't that somebody fussed with it in between。 The third principles authenticity。

 Can I actually be sure that the other party I'm talking with is who they say they are？

 And it turns out there's some ways to do this。 But the basic techniques for both confidentiality and integrity and authenticity that uses。

 cryptography is our mathematical tools and secrecy in codes。

 It's the idea that if we use the right cryptographic tools then we can have secure communication。

 even over an insecure network like the internet。 And so you're going to learn about some basic cryptographic tools such as cryptographic hashes。

 such authentication codes， symmetric cipher， public key cryptography， certificates and signatures。

 which are all used in the internet today。 And so by the end of this unit you should start to have a sense as to how you should secure。

 your network going forward。 [BLANK_AUDIO]。