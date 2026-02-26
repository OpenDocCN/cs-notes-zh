# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P145：-Cryptography6, Video 1- Public-Key Cryptography.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/dd57636e1ad87725ac05762e67c7b13d_0.png)

Hey everyone， I am still coming to you from a soundproof booth， it's getting a little stuffy in here。

 but that's okay because we're talking about public key encryption and digital signatures today。

As a quick refresher from last time， true randomness is expensive， so we designed the PRRNG。

 which is an algorithm that takes in a little bit of true randomness and is able to efficiently generate a lot of random looking output and the PRNG is secure when it is computationally indistinguishable from truly random bits from the perspective of an attacker。

 and we showed several different constructions of the PRNG such as one based on HMAC。

In the second half of last time we talked about the diffy homan key exchange。

 Alice chooses her half of the secret A disguises it and sends G to the a mod P to Bob。

 Bob chooses his half of the secret B disguises it by sending G to the B mod P to Alice。

 and each site takes the disguised secret that they received。

 raises it to the power of their own secret， and they both derive G to the A B mod P。

 and the discreteet logar problem ensures that an attacker like Eve is not able to deduce the shared secret。

 However， some issues。 we said it is not secure against a man in the middle。

 it does not provide authenticity， and both of these points were shown。

 when we showed the attack where Mallory was able to get Alice and Bob to derive different keys and in particular different keys that Mallory knew。

 And the other issue is that both parties have to be online at the same time。

 So that's a quick reminder of what we talked。About last time。

Today is all about public key cryptography。So if you look at our cryptography roadmap。

 we are now in the right half of this table。 We're going to be looking at schemes that use the asymmetric key model。

 Some of these schemes will provide confidentiality and others will provide integrity and authentication。

In all of the public key cryptography schemes that we will see today。

 everyone has two keys and they form a linked pair。

 so everyone has a public key that everyone knows and a private key that only they know and the keys come in pair each public key corresponds to exactly one private key you cannot swap keys。

 everyone has a single pair of keys。 A lot of the schemes that we'll be seeing in public key cryptography involve a lot of number theory。

 things like modular arithmetic factoring large numbers and the discrete logarithm problem that we saw last time One benefit of public key cryptography is that we no longer have to assume that Alice and Bob magically share a secret ahead of time these schemes will work just by using everyone's public and private key。

However， one major drawback of public key cryptography is that it is much slower than symmetric key cryptography。

 remember that in symmetric key cryptography， we were just shuffling bits around and that's something that computers were really good at by contrast in public key cryptography we're using all this fancy number theory things that you might have seen in CS70 and I don't know about you but I never finished any of the CS70 exams I took I was run out of time so maybe that goes to show that number theory is quite slow compared to symmetric key cryptography。



![](img/dd57636e1ad87725ac05762e67c7b13d_2.png)