# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P153：-Cryptography6, Video 9- Digital Signatures - Definition.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/ad02df6af10d1c989162f6c7967a72ef_0.png)

The second half of today is all about digital signatures。

We are now in the bottom right square of the cryptography roadmap。

 that means that we're looking at schemes that use the asymmetric key model and they provide integrity and authentication。

 not necessarily confidentiality。You can kind of think of these like the public key equivalent of max because they also provide integrity and authenticity。

 but they don't require Alice and Bob to share a secret key ahead of time。

 One question that sometimes people bring up during this lecture is the fact that the public keys can be tampered with。

 So what if when Bob announces his public key to the world， someone taampers with it。

 and the public key that Alice hears is different。 She doesn't hear the correct value of Bob's public key。

 You're right， that is something that can happen and we need to fix that limitation later when we talk about certificates and key management。

 but for now we're going to ignore it and we're going to assume that when Bob publishes his public key to the world。

 everyone hears the correct honest value of the public key。 And if that didn't make sense， it's okay。

 we will revisit it when we talk about certificates。

The public key signatures that we see all work in a similar way。

 So if I have a message that I want to send， I will sign it with my private key。

 and that means that I'm the only person that can sign the message only I know the private key。

 so I'm the only person who can sign this message that I created and when I send that message out。

 anybody can use my corresponding public key to verify that the message has not been tampered with and the signature should have the property that if someone tmpers with the message while it's being sent out or they tamper with the signature if either of those two values are taampered when someone tries to verify the signature with the public key。

 the verification algorithm should say no， this message has been tampered with the signature no longer matches the original message。

More formally， a digital signature is defined using three functions。

 and hopefully they are looking kind of familiar at this point。

 The first thing you need to do is define how the keys are generated when someone wants a key pair。

 how do you give them a public key and a corresponding secret key。

 so the key generation algorithm outputs those two values together in a pair。

Then the signing algorithm takes in the secret key because you sign with your secret key and it takes in a message and it outputs the signature on that message。

And finally， the verify algorithm， which you must also define。

 it takes in a public key because everyone can use the public key to verify。 it takes in a message。

 and it also takes in the signature on the message。

 and this function returns true if the signature is valid on the message。

And it returns false if the signature is not valid on the message。

 so in order to define a digital signature scheme， you must fill in these three algorithms。

What makes a digital signature scheme good， it must be correct if someone signs a message and it has never been tampered with。

 then if you take the message and the signature and you pass it into the verify function。

 you should probably get true because the message has not been tampered with。Efficiency， again。

 not going to be formally defined， but hopefully the signing and verifying algorithms are reasonably fast。

And finally， the security of a digital signature is that it is unforgeible。 This is pretty similar。

 if not exactly the same as the scheme we saw for Max。

 and remember the idea there was that an attacker can ask for the signatures of some arbitrary messages to try and learn how the scheme works。

 and eventually when they're ready， they must produce a message and a corresponding signature without knowing the private key。

 if they're able to do this， the scheme is not secure。

 an attacker is able to forge a signature that's valid without knowing the private key。 However。

 if an attacker is not able to do this， they cannot come up with a valid message signature pair without knowing the private key。

 Then we say that this scheme is unforgeible， it is secure。

 So it's the same definition as we used for Max， but now applied to digital signatures。

A couple final notes about digital signatures。 Remember that digital signatures are based on the same kinds of number theory that public key encryption was based on。

 and that means that there is a limit to the length of the messages that you can sign。 For example。

 if you're working mod n， you can only sign messages between 0 and n-1。

 That means you can't sign very long messages。 So to solve that。

 all you have to do is hash the message before signing it。 So you first hash the message。

 And when you compute the digital signature， you don't compute it on the long message itself。

 you compute it on the hash of the message， which is shorter and fixed length。

That's the fix you use to sign arbitrarily long messages。

And the final note about digital signatures is that they provide both integrity and authenticity under our threat model。

 So remember that when we talked about Mac， it was not always clear whether or not Max provided authenticity because if multiple people have the symmetric key。

 you don't know exactly who generated the message and the Mac。 However， in digital signatures。

 this is not a problem because only one person has the private key。

 So you know that the message must have come from the person with the private key。

 if the signature checks out。 So that means that digital signatures provide integrity。

 if the signature checks out， you know that the message has not been tampered with and it also provides authenticity。

 if the signature has not been tampered with then you know for sure that the message must have come from the person who held the private key。

 and that's just one person。

![](img/ad02df6af10d1c989162f6c7967a72ef_2.png)