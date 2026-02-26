# 147：-Cryptography6, Video 3- ElGamal Encryption.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/6d1d8e7f689dc45cfed110ad0fa3743e_0.png)

The first public key encryption scheme we will see today is called Elgamal encryptncption。

In the cryptography roadmap， it is in the top right box because it provides confidentiality。

 and it uses the asymmetric key model。The Elgamal encryptncion scheme is inspired by the Diffyhelman key exchange。

 so remember that the Diffyhelman key exchange allows Alice and Bob to share a secret over the insecure channel。

 but there were two problems with Dffyhelman that we're going to try to solve One of them was that diiffyhelman doesn't actually send a message It allows Alice and Bob to generate a shared secret。

 but the resulting secret G to the AB mod P is just some random value。

 There is no message in the process of the key exchange。

 So Elgamal encryptncion is going to fix that so that it supports encrypting and decrypting messages directly and the second problem that we're going to solve is that diffyhel and key exchange requires both Alice and Bob to be online at the same time。

 Elgamal encryption is actually going to allow Alice to send messages to Bob even if Bob isn't online right now。

 So we're going to slightly modify the way that the diyhelman key。

Exchange works and the order in which we perform the operations in order to support Alice sending a message。

 even if Bob is currently not online， and then maybe Bob wakes up later and decryptps the message。

 So those are the two problems we're going to fix。 Dffy Heman doesn't support messages。

 Alga Mal does。 Dffy Heman doesn't support one user being offline。 Alga Mal does。

 So let's see how this protocol works。This slide has a lot of math。

 so let me walk you through it at its heart， I think of the Algaal encryption scheme like a diiffy Heman Key exchange。

 except one side is going to sleep through the whole exchange， they're going to be offline。

So the first step is the key generation step and what Bob is going to do is he's going to generate a private key by choosing a random number lowercase B and then he's going to generate the corresponding public key by computing G to the little B mod P and will denote that as big capital B So Bob has now generated a key pair。

 there's a private key that he keeps for himself and a public key that he publishedes to the world and you' might notice that these are the exact same values he would have generated in the diiffyhelman key exchange So basically what Bob has done is he has computed his half of the diiffyhelman key exchange ahead of time and published G to the little B mod P the public key for everyone to know ahead of time。

 So Bob has done all the work ahead of time he is now ready to take his nap Good night Bob have a good nap and now we're going to run the rest of the protocol while。

Bob is offline。So how does someone encrypt a message and send it to Bob who is off sleeping？ Well。

 it works something like this。 When Alice wants to encrypt a message and send it to Bob。

 Alice generates a random number R。And we'll say lowercase R here and then computes G to the little R mod P。

 which we' denote as capital R。 Again， this should look very similar to the diffyhelman key exchange。

 because that's what it is。 This is Alice computing her half of the diffyhelman key exchange。

 At this point， Alice is able to derive the diffyhelman shared secret because she knows big B。

 That's the disguised secret that was sent by Bob。 And she knows little R。

 which is her half of the secret。 So if she computes big B to the power of little R。

 that should give us the shared secret that we were looking for， which was G to the B R。

Now that Alice has the shared secret， she can use the shared secret to scramble up the message that she wants to send and we'll do that with a multiplication。

 so if Alice wants to send a message M， then she will take the message M multiply it by the shared secret G to the BR mod P and that is the ciphertex。

 So in total， the cipher textext that Alice sends is actually two values。

 one of them is the message encrypted with the shared secret that is M times big B to the little R。

 which remember is the diffy home and shared secret。And the second value is big R because remember。

This is all based on a Dffyhelman key exchange， and Alice has to send her half of the Diffyhelman key exchange to Bob。

 So Alice sends big R。 that's her half of the Dffyhelman exchange plus the message encrypted with the shared secret。

So at this point， Alice has finished her half of the Diffy Heman Key exchange by sending Big art to Bob。

 she has also computed the shared secret， multiplied it by M to encrypt the message M and sent that encrypted message to Bob。

 and all of this can be done while Bob is offline。Eventually， Bob wakes up from his nap。

 We hope you had a good nap， and he notices that he has received a message。

 and he would like to decrypt it。 So in order for Bob to decrypt the message。

 he needs to undo the operation that Alice did。 What did Alice do。

 She multiply the message by G to the B R。 And to undo that。

 we need to multiply the message by G to the negative B R。

 This is kind of like dividing by G to the B R。 but in modular arithmetic， we don't divide。

 We multiply by the inverse。If that doesn't make sense， don't worry too much about it。

 but that's what Bob is going to do， he's going to derive the inverse shared secret。

 think of it like the reciprocal， and we're going to multiply the cipher text by the inverse shared secret to get the original message back。

So how does Bob get the inverse shared secret？ Well， he knows big R。

 That's one of the values that Alice sent over as part of the ciphertext。

 That's Alice's half of the secret。 But instead of raising that to the B power。

 which would give us G to the B R， that's the shared secret。

 Bob is actually going to take that message， that big R and raising it to the negative B power。

 And by raising。Big R to the negative B power。 We end up getting big R to the negative B。

 and that's equivalent to G to the negative B R。 That is the inverse shared secret。

 So Bob has completed his half of the diiffy Heman exchange， but instead of using B。

 he used negative B to get the inverse shared secret。Now that Bob has the inverse shared secret。

 he can cancel out the shared secret and get the original message back。 So he will take C2。

 That was the message encrypted with the shared secret。

 multiply it by this inverse shared secret that he found if you expand all the terms。

 the Cyphertext the Alice set was M times G to the BR。 That's the shared secret。

 And we're multiplying it by G to the negative BR。 That's the inverse shared secret。

 Those two terms cancel out， and we get the original message M mod P back。

 So what Bob has done is he has completed the difffihamman key exchange by taking big R。

 raising it to the negative B power， obtaining the inverse shared secret。

And then he multiplies the encrypted message with the inverse shared secret。

 the shared secret and the inverse shared secret cancel out。

 and we get the original message back so ultimately what we have done here is just the diffy Heman key exchange but we changed the order around a little bit to enable Bob to take a nap in between and we also encrypted a message by multiplying it by the shared secret to encryptry and multiplying the ciphertt by the inverse shared secret to decrypt and that's the whole story for Elgamal encryption。



![](img/6d1d8e7f689dc45cfed110ad0fa3743e_2.png)