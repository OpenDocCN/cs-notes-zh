# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P148：-Cryptography6, Video 4- ElGamal Security, Malleability.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/166474b4c72e90f6d87532a9ee2ea602_0.png)

The argument for why Algamal encryption is secure， is quite similar to the argument we made for diiffy Heman。

 which makes sense since Algamal encryption is based on the Diffyhelman key exchange。

 So remember that the diiffy Heman key exchange was secure because of the diffy Heman problem。

 which itself was based on the discrete log problem and the diffy Heman problem goes like this。

 If someone gives you G to the A mod P and G to the B mod P。

 it is hard for you to recover the shared secret G to the A B mod P。

 That's what the assumption says and we assume that to be true。

 because the discrete log problem is hard。 and no one has found a good way to solve this problem besides discrete log。

Now Elga Ma sends these values over the insecure channel， so if you're thinking about Eve。

 these are the values that Eve can see。Eve can see Bob's public key because that's published to everyone。

 and Eve can also see the ciphertext that Alice sends across the channel and remember that the ciphertex is actually two values。

 its big R to complete the Diffy Heman key exchange。

 and then is the message encrypted with the shared key。These symbols are kind of confusing。

 so we can actually write out what they represent。 Big B is G to the little B mod P big R is G to the little R mod p and the message is encrypted with G to the B R mod P the shared secret。

 Now if we look at this， G to the R mod P and G to the B mod p。

 Well that's exactly the two values given in the diiffy Heman problem and the diy Heman problem says even if I tell you these two values G to the B mod p and G to the R mod p。

 it is hard for Eve to derive G to the B R mod P。 And because she can't derive G to the B R mod P。

 she is unable to reverse the encryption and obtain the original message M。

 if Eve wanted to get the original message M， she would have had to multiply this value by G to the negative B R mod P。

 but she doesn't know that value。Because she's only given G to the B and G to the R。

 she is not able to derive the shared secret， so she cannot cancel out the G to the B R to get the original message back。

 So this is not a proof， but it's a rough argument for why Eve the eavesdpper is not able to recover the original message in algamal encryption。

Egamal encryption provides confidentiality， but it does not provide integrity。

 One attack that attackers can do on Algamal encryption is something called malleability In this attack。

 Mallory， a man in the middle attacker who can tamper with messages is going to change the message and cause Bob to decrypt something that is predictably different。

 Now， that's kind of a subtle point。 So let's go through an example。

 Let's say that Mallory sees some cipher text and she doesn't know what the cipher text says。

But based on the malleability attack， Mallory is able to modify this cipher textext in some predictable way so that when Bob decryptps the message。

 the message that he decryptps has also changed in some predictable way。 For example。

 if the malleability attack is used to double the value of the message。

 then what this means is that if Alice sent the message 25 and Mallory executes her attack。

 now when Bob decryptps the message， he ends up seeing 50 a number twice as large or if Alice's original message was the number 70。

 then when Mallory executes her attack， and Bob decryptps the message。

 Bob will see the number 140 which is twice the original value it doesn't matter what value Alice sent originally。

 and it doesn't matter that Mallory doesn't know what the cipher textex says。

 she is able to execute an attack so that no matter what the original number was。

 Bob is always decrypting a number。That is twice its value that's the malleability attack it means even if you don't know the cipher textex。

 you can cause Bob to get a message that is predictably different， for example。

 twice the original value。All that being said， Elgamal encryption is vulnerable to an attack like this。

 and as an example， we can show you how Mallory is able to cause Bob to decrypt to a value that is twice the original value。

So if we go all the way back to the encryption scheme。Let's say that Alice sends the cipher text。

 which is two values， it's the big R value， which is part of the diffyhoman exchange。

 and then it's the message multiplied by the shared secret。

Now if Mallory takes this cipher textex intercepts it and she replaces C2 with two times C2 so whatever value it is in cphertext。

 she takes that value and she doubles it well then what's going to happen when Bob decryptps when Bob decryptps this value is now twice its original value and if you go through all its math。

 there's an extra factor of two here， there's an extra factor of two here。

 there's an extra factor of two at the end。 So when Bob decryptps the message he ends up getting two times the original intended message so algamal encryption is vulnerable to this malleability attack where mallllory takes not the first but just the second part of the cipher text multiplies it by2 and now it looks like the message being sent is not M but2 M and when we go through all the decryption steps we can also see that Bob ends up decrypting a value of2。

And。So to make a long story short， algamal encryption doesn't offer integrity。

 attacks like malleability are possible， and one final word of warning is that Algamal encryption as we've presented it。

 actually is not INDCPA secure there are some very subtle points that we haven't really talked about that cause the scheme that we've shown to not be secure。

 So if you want INDCPA security with Algamal encryption。

 you have to add some additional subtle points that we're not going to talk about。

 so just remember that the scheme we've shown is not quite INDCPA secure but with some modifications it can be made to be INDCPA secure。

And that's it for alol encryption。

![](img/166474b4c72e90f6d87532a9ee2ea602_2.png)