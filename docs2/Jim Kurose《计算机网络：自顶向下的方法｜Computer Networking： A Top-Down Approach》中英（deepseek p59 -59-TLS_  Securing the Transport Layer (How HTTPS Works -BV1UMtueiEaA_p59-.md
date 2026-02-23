# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p59 -59-TLS_  Securing the Transport Layer (How HTTPS Works -BV1UMtueiEaA_p59-

Welcome back in this video we're looking at how TCP sessions can be secured using the TLS protocolcol。

 which is the underlying security mechanism used by applications such as HTTPS Let's get started。



![](img/282ea99168698aad04779f994534a631_1.png)

Welcome back today we'll be looking at securing TCP connections using TLS for Trans layer security。

This is the mechanism used to provide the HTTPS or secure HTTP service for websites。



![](img/282ea99168698aad04779f994534a631_3.png)

The TlS， because it supports HttPS is probably the most widely used security protocol that we'll encounter while early on it was primarily used for things like ecommerce-commerce sites or web email。

 it's become increasingly widely deployed to where the majority of websites use HTPS and it's supported by all browsers the service provides confidentiality using symmetric encryption integrity via crypographic caching as well as authentication via public key cryptography so it's combining the elements that we saw previously just like we saw with the email example you may also have heard the term SSL or SSL 2。

0 and that was an earlier protocol providing the same service which has been deprecated and replaced with TLS。

So it's important to note that even though SSL got up to higher version numbers。

 you might have seen SSL 2。0 for example， TLS 1。3， the current version is the technologically more advanced protocol and replaces SSL So as we've done with other protocols in the course。

 we're going to build up from basic elements and see what's needed to achieve this transport layer security。



![](img/282ea99168698aad04779f994534a631_5.png)

So we'll call our protocol T TLS or toy TlS， and it's going to have a number of elements when it is the handshake。

 using certificates， private keys， and so forth， will'll have key derivation。

Data transfer and then connection closure in a time sequence diagram we can overlay this on a TCP exchange。

 so we see that the TCP connection must be established first with the S and the SAC。

 and then we can send over our TtLS Hello， retrieve the public key certificate。



![](img/282ea99168698aad04779f994534a631_7.png)

And use that public key to encrypt a master secret key。 So the shared secret。

 And we're going to step beyond what we've seen so far in that the master secret key is going to be used to generate additional session keys for the Tls session。

 The one downside we see here is that we've now introduced an additional round trip time before data can be exchanged。

 So before we already had the overhead of the TCP session needing to do a handshake。

 But now we've added an additional handshake。And it can't happen until the TCP handshake is completed。

 so it adds additional time before the connection can begin。



![](img/282ea99168698aad04779f994534a631_9.png)

So just for reference it's considered bad to use the same key for more than one cryptographic function。

 and so in this example， we need to have different keys for message authentication。

And for encryption， though we end up needing four keys。

 encryption key for the data sent from the client to the server。

 the message authentication key for data sent from the client to the server。

And then we have a different encryption key for datacent to the server to the client。

And a different message authentication key for data sent from the server to the client。

 All of these keys will be derived from the key derivation function or K D F。

 This is based on the master secret。

![](img/282ea99168698aad04779f994534a631_11.png)

So now we have a technical consideration。TCP provides a byte stream abstraction。

 so it's just a sequence of bytes going from one end the connection to another。

 So the question is then do we want to wait for that entire stream to be finished。

Before we can decrypt it and provide the authentication or something else。 And so in this example。

We are going to break the stream into a series of records or blocks。

 There will be a known chunk size of data that's sent。

 and then the record will carry along the message authentication code created using the master secret。

 And so the receiver can be processing these records as they arrive。

 Instead of waiting for the entire stream to be over。

 Each record is encrypted using the symmetric key and then passed to TCP。

 So how could this be attacked。 Well， we have the issue of reordering。



![](img/282ea99168698aad04779f994534a631_13.png)

So because the TCP header is not protected by this mechanism。

A man in the middle could mess with the TCP header。

 reorder the data contents inside those TCP packets and then send them on。

 We could also be subject to a replay attack where the man in the middle saves the encrypted information as and able to send it later as we saw earlier with the authentication attacks so to protect against these。

 we're going to have sequence numbers within TlS so encrypted sequence numbers。



![](img/282ea99168698aad04779f994534a631_15.png)

And a no that won't be reused in later connections。

 We also mentioned that we were going to have a connection closing procedure。

So a potential attack is that the attacker might trunet the connection by forging the TCB connection closed segment。

Recall that TCP flags control when the session is closed and again that's not protected by this encryption。

So the solution to this is to introduce record types and have a particular type foreclosure。

And that type will be inside the encryption and so not subject to forgery by the attacker。

 The TLS protocol provides an API for applications to interface with。



![](img/282ea99168698aad04779f994534a631_17.png)

So from the perspective of HtDP， the original version of HTDP ran over TCP directly with no encryption。

Whereas HttP2 is able to use the TlS interface If you've also heard of HttP3。

 that's a slimdown version of HttP2 running over Quick and we note that Quick runs over UDP so there's significant changes there where the quick protocol takes on the roles of reordering and flow control and congestion control and runs at all over UDP instead of allowing TCP to perform those functions So for this discussion we're looking at HtTP running over TlS which in turn runs over TCP over IP So TlS and the version number in this case 1。

3 identify what we call a cipher suiteite or a particular set of mechanisms for key exchange and encryption and in fact it has multiple options for some of these functions such that during the handshake the two ends need to negotiate which schemes are going to be used for generating keys and exchanging them and so forth we note that compared to 1。

2 there are fewer options within the cipher suiteite and for example RSA has been removed as an option for keys。



![](img/282ea99168698aad04779f994534a631_19.png)

And only Dffy Heman is supported。 It then uses AE for encryption and authentication。

It then uses Shah 256 as its cryptographic hash function。 So here you have our TlS handshake。



![](img/282ea99168698aad04779f994534a631_21.png)

And the client indicates in its packet， which ciphersuits it supports。

 as well as the parameters for the Diffyhelman Key agreementement。

The server then responds back for a selected Cypher suiteite out of the available options that the client supports。

Confirms the key agreement protocol parameters。As well as its signed certificate。

 the client then checks the service certificate， by which we mean it decryptps it using the certificate authorities's public key。

 And as long as that checks out， it can then generate the master secret key and begin making application requests。

 Now， there's also the case where we could have a0 round trip time handshake。



![](img/282ea99168698aad04779f994534a631_23.png)

And this is possible if the client is resuming an earlier connection between the client and the server。

 so it already has some pre establishedlish information。

And so it's able to encrypt application data using the master Se from the previous connection。

However， this would be vulnerable to replay tax so we have to be careful with where it's allowed to be used。

 so that wraps up a discussion of TLS and HTtPS In the next video we'll look at IP Sec。



![](img/282ea99168698aad04779f994534a631_25.png)

Which we can think of as IP layer security， whereas what we were just looking at was transport layer security See you in the next one We hope you enjoyed this video If you found it to be useful please click the like button to be notified when more videos are posted for this class please subscribe to our channel and click the bell。



![](img/282ea99168698aad04779f994534a631_27.png)