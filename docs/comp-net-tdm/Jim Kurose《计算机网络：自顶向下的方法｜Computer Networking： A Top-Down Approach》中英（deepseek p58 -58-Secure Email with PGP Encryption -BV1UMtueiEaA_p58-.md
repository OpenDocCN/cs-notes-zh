# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p58 -58-Secure Email with PGP Encryption -BV1UMtueiEaA_p58-

In this video we're discussing secure email and looking at how emails can be either signed or encrypted using public key authentication Let's get started。



![](img/921e0e971ccf2b90c498f509b36bfe24_1.png)

Allright folks， welcome back Now that we've gone through the basics of authentication and message integrity we're gonna see how those apply to the practical example of securing email So if you think about your usual email usage yes you have to log in with username and password to your email service or you may give those through a client on your phone or on your computer so that it can log into the service so the service is authenticating you at that point and then you can write your email and send it off but you're still trusting your email service provider with the content of your email you have not protected it in any way and if they were a malicious actor either at your service provider or at your recipient's email service provider they could change the content of the email or just intercepted and read it and you haven't used any mechanism to mitigate that so what we're talking about now is not how you log into your email service but how you would actually protect the contents of a message so in our first example Alice wants to send a confidential email not just sign it but。



![](img/921e0e971ccf2b90c498f509b36bfe24_3.png)

The content from being intercepted and read So how does this work Alice has her plain text message M。

 and as we know， encrypting large amounts of data with a public key encryption algorithm is not very efficient。

 so she's going to use a symmetric key algorithm to encrypt her message and protect it from being read。

 but that means that she has to get the shared key over to Bob somehow。 So to do that。

 she's going to encrypt the symmetric key with Bob's public key This way she can send both the message KS of M and the shared key in its encrypted form over to Bob together。

On the receiving side， Bob can use his private key to decrypt the sheared key。

And then used a shared key to decrypt the message。 So we've achieved confidentiality over the internet。

 The message was encrypted， and the shared key was transmitted in a secure manner。 However。

 what we haven't done is authenticate Alice to Bob。

 anybody could have generated any shared key and used Bob's public key in this manner。

 So while Bob can read the message， he's not able to confirm that is， in fact。

 Alice has sent it to him。 So this is where integrity and authentication come in。

 So Alice isn't concerned with confidentiality。 Now。

 but she wants Bob to know that the message came from her and that it hasn't been changed in root。

 So in this case， Alice hashes the message to get the message digest。

 And she encrypts the hash of the message with her private key。

 that now provides the integrity and the authentication。

 because while the message is sent in the clear， Bob can decrypt the message digest。

 using Alice's public key， which shows that the message digest was encrypted with her private key。

 Likewise， Bob can hash the plain text of the message and make sure that what he gets matches the encrypted message。



![](img/921e0e971ccf2b90c498f509b36bfe24_5.png)

![](img/921e0e971ccf2b90c498f509b36bfe24_6.png)

🎼Digest that was sent with the message。 While it's not always easy to set up。

 standalone email clients usually have a mechanism for providing a public key pair to the client that can be used to encrypt or digitally sign messages。

 We' stop there now that we've covered securing email and in the next video we'll look at Tl。

 which is the mechanism providing the security for H Ttps。 See then we hope you enjoyed this video。

 If you found it to be useful， click the like button to be notified when more videos are posted for this class。

 subscribe to our channel and click the bell。

![](img/921e0e971ccf2b90c498f509b36bfe24_8.png)

![](img/921e0e971ccf2b90c498f509b36bfe24_9.png)