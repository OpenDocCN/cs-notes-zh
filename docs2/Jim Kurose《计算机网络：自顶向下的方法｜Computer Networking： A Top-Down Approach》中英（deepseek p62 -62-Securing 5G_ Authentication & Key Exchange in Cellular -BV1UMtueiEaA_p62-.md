# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p62 -62-Securing 5G_ Authentication & Key Exchange in Cellular -BV1UMtueiEaA_p62-

Welcome back in this video we're looking at security in cellular networks。

 specifically 4G and 5G networks。Let's get started。



![](img/2194ced3d6c077dedd334f25e1db36b8_1.png)

In this video we'll be continuing to look at security and wireless and mobile networks。

 focusing on cellular networks。

![](img/2194ced3d6c077dedd334f25e1db36b8_3.png)

In chapter 7， we saw a bit about how authentication works in cellularul networks。

 but we didn't talk about the encryption aspects at all。So as we saw then。

 the arriving mobile unit must associated with a base station。

And authenticate itself to the network as well as authenticating the network。

Just as we saw in 8 or211， there could be rogue cellular base stations trying to entice mobile devices to authenticate with them and reveal sensitive information。

So some notable differences from the WiF scenario is that we have a Zoom card in the mobile device that provides a globally unique identity and contains shared keys。

Also， one of the key drivers for correctly authenticating mobile devices is so that it can be matched up with the service plan that the user is paying for and offered the specific paid services that are included in that plan。



![](img/2194ced3d6c077dedd334f25e1db36b8_5.png)

The mobile device and the base station used a derived S key to encrypt communication over the wireless 4G link。

Then it's up to the mobility management entity in the visited network to communicate back to the home network。

 to the Home subscriber service where the ultimate authentication happens。

So there must be a preexisting business relationship between the visited network and the home network in order for this to work。



![](img/2194ced3d6c077dedd334f25e1db36b8_7.png)

So initially we have the mobile device attaching to the base station and then that request getting forwarded onto the mobility management entity。

The MME then generates an authentication request， including the MZ number。

 as well as the Vi network information， and sends that to the Home subscriber service。

The MME will know which home network to connect to based on the MZ number。

 which resides in a global database pairing these unique identifiers and home networks。

So then the HSS will make the decision about whether or not this connection is authorized。

Meaning both the authentication information is valid and whatever level of service the subscriber is paying for includes roaming service on this visited network。

The HSS also knows what keys are on the mobile SimM card。

And so it uses that pre shared key to derive the authentication token and the expected authentication response to the token。

 then sends back the authentication token and response token and session keys to the mobility management entity Note that the Home subscriber service does not send the initial shared secret to the MME。

The visited network is not trusted to the same level as the home network。

 the visited network does not get to know the secret key that only the home network and the mobile device know。

So the visited network only receives the tokens that are generated based on those shared secrets。

The authentication token is also encrypted using this initial shared secret。

 and so the mobile device is able to validate that it came from the home network。So at that point。

 it's not authenticating the visited network， but it is authenticating the fact that the Vi network was able to get an authentication token from the home network。

 and therefore the visited network should be trusted。

So the mobile device has now authenticated the network by proxy because it is able to communicate with the home network。

 and the visitor network keeps the authentication response token for later use in the exchange。



![](img/2194ced3d6c077dedd334f25e1db36b8_9.png)

So the mobile device generates the authentication response and sends it back to the visited network。

 and the visited network is then able to validate it because it knows what the authentication response should be thanks to the home network sending it in Part B of the exchange。

At that point， the mobile is now authenticated by the visited network。

 and the visited network can generate session keys for the base station。At that point。

 the mobile device can also perform the key derivation。

And now the wireless channel has a shared symmetric key that can be used with the AES protocol。



![](img/2194ced3d6c077dedd334f25e1db36b8_11.png)

How did this change going from 4G to 5G？In the ForG scenario。

The MME in the Visit network makes the authentication decision， whereas in 5G。

 the home network provides the ultimate authentication decision。However。

 MME is still involved in this and can still reject the authentication。

There's also a change to the key sharing in that the keys are not shared in advance for IoT devices in 5G。

Lastly， and a major privacy concern in 4G is that the device is transmitting its MZ number in clear text to the base station。

So anyone can listen and record the M numbers that mobile phones are transmitting all the time。

And recall that M numbers are unique identifiers， they are not changed or obfucated over time by the device。

They're like a globally unique serial number。 And so it's been the case that people are trackable by their handheld devices。

 and this limitation was noted and addressed in 5G where the M Z numbers are now encrypted using public key cryptography。

 even in the initial exchange between the mobile device and the base station。



![](img/2194ced3d6c077dedd334f25e1db36b8_13.png)

So that was a very high level overview of security in wireless and mobile networks。

And this is an interesting topic that it may be worthwhile to go back and revisit with some more detailed videos in the future。

In particular， seeing the history of the progression between 1G， 2G， 3G and so on。

 there were significant security oversights in that progression that have been addressed today。

So it can be helpful to understand how that progression occurred。

 but that's a topic for another video。 And in our next video in this series。

 we'll be looking at operational security， meaning firewalls and intrusion detection systems。

 So we'll see you on the next video。 Thanks， we hope you enjoyed this video。

 If you found it to be useful please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。



![](img/2194ced3d6c077dedd334f25e1db36b8_15.png)