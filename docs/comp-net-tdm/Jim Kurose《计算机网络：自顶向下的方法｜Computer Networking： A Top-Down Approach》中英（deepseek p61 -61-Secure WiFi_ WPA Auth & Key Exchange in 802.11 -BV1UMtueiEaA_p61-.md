# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p61 -61-Secure WiFi_ WPA Auth & Key Exchange in 802.11 -BV1UMtueiEaA_p61-

Welcome back in this video we're looking at securing Wi Fi or wireless lenss Let's get started。

In this video we'll be looking at security and wireless and mobile networks， in particular。

 80211 or WiF networks。And in a follow on video， we'll look at 4G and 5G cellular networks。

 which is of particular interest because of the shared nature of the wireless medium。

It's much easier for an attacker to surreptitiously record and or transmit in a wireless domain as opposed to a wired network where tapping a fiber or even a copper cable requires more access is more likely to be noticed and is just generally harder。



![](img/fabd12b9aff1d7d89f7714e73bf10153_1.png)

First， we'll look at Wifi or the 802。11 standard。Back in chapter 7。

 we saw how a mobile node would associate with an access point。By looking for known SSIs。

 making the association request， and so on。And that's still the first step in this process， however。

 after it's established the basic means for communicating on the wireless domain by associating with the access point。

It then needs to exchange credentials in order to authenticate to the network。



![](img/fabd12b9aff1d7d89f7714e73bf10153_3.png)

And the first question is what type of authentication is needed。

 This is advertised by the access point itself， broadcasting what forms of authentication and what encryption methods it supports。

When the device associates， it can request specific authentication and encryption mechanisms。However。

 the mobile device does not yet have the encryption keys needed to communicate securely。

As with other security schemes that we've seen， a shared secret will not be used as the encryption key。

 so the mobile device and the access point must negotiate a shared symmetric key。

 and they will do this based on the shared secret such as a password。

The handshake also includes nonsenses to prevent replay attacks， remember。

 all of this exchange is being broadcast over our wireless domain and so an attacker can easily overhear it。

 and attempt to replay or other attack。These messages also include cryptographic hasing to ensure that the message integrity is maintained。

And assuming this is successful， the mobile device and access point are able to authenticate each other。

Note that this is a mutual authentication。Because another type of attack is standing up rogue access points。

Because the SSID is in the clear， it's easy to create an access point that uses the same SSID as ones that the mobile device has seen before。

Once this mutual authentication takes place， the authentication server and the mobile device derive a symmetric session key。



![](img/fabd12b9aff1d7d89f7714e73bf10153_5.png)

The most recently standardized security protocol for 802。11 is WPA3。

 so we'll look at the handshake for WPA3。WeStart off with the generation of anOs by the authentication server。

 which is sent to the mobile device， both of which know the initial shared secret。

The mobile device generates its own nos and generates a symmetric shared S key using the two nos and the initial shared secret。

It sends all of this back in a cryptographically signed value to the authentication server。

The authentication server then derives the symmetric shared S key in the same way that it was derived derived by the mobile endpoint。

Note that this key KM AP is never sent across the air。

 both sides derive it independently from the same fundamental elements。



![](img/fabd12b9aff1d7d89f7714e73bf10153_7.png)

After the shared key is derived， the authentication server must provide it to the access point because the encrypted session is just between the mobile device and the access point。

 the traffic is not going to be tunneled all the way through to the authentication server。Of course。

 in practice， the authentication server may reside in the same device as the access point。

 but these are logically distinct functions and may be residing in separate devices。

 especially in the case where many access points are being supported by one authentication server。

Once the mobile device and the access point both have the shared S key。

 encrypted communication can commence。

![](img/fabd12b9aff1d7d89f7714e73bf10153_9.png)

We've mentioned this communication between the mobile device to access point and the authentication server。

And of course， that itself cannot take place in the clear。

 so we have the extensible authentication protocol。

 which defines an end to end request response protocol between the mobile device and the authentication server via the access point。

So we see that on the wireless side， we have EAP over land or EAPol running over 8 or 2。11， however。

 between the access point and the authentication server， it's using the radius protocol。

So the access point will communicate with the authentication server via radius。

And so the authentication server may be commonly referred to as a radius server because it supports the radius protocol。



![](img/fabd12b9aff1d7d89f7714e73bf10153_11.png)

That wraps up a discussion of security in wireless lenss or 8 to2/11。



![](img/fabd12b9aff1d7d89f7714e73bf10153_13.png)

And in the next video， we'll look at security and cellular networks， see you then。

We hope you enjoyed this video， if you found it to be useful。

 please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

