# 139：-Cryptography5, Video 10- Secure Color Sharing (Analogy).zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/6531f4f57b38232f294c6ba673e2d625_0.png)

The second half of today is all about Diffy Heman Key Exchange。

 so far when we've talked about symmetric key schemes。

 we have always assumed that Alice and Bob have been magically blessed with the secret key that no one else knows。

But how do they actually get this secret key over an insecure channel。

 that's the problem we are about to solve。In the cryptography roadmap。

 this isn't really any of those four boxes， we're not designing a scheme that provides confidentiality or integrity。

 but this is a necessary building block that we need to unlock all of those symmetric key schemes that we talked about because all those schemes require Alice and Bobob to share a key。

 and we are now going to design a scheme that actually allows them to securely share a key。

To understand how diffy Heman works， let's start with an analogy In this analogy。

 Alice and Bob want to share a secret color over an insecure channel。

 so Alice can't just send the secret color over the channel to Bob because then Eve would also know the secret。

So what they're going to do is they are going to disguise the secret using some common paint that everyone knows。

 So we're going to start with some common paint color， which here is yellow， Alice， Bob and Eve。

 everyone knows the common color is yellow。 This is just to help us disguise the secret。

Now Alice is going to generate her half of the secret， which is red。

 and instead of directly sending a red across the channel because that would spoil the secret。

 Alice is going to disguise the secret by taking her half of the secret which is red。

 mixing it with a common color which is yellow to get something like orange。

 and now that Alice has orange， a disguised version of the secret。

 she can send that disguised secret over the public channel to Bob。

And Bob's going to do the same thing。 He's going to generate his half of the secret。

 which here is teal， and he's going to mix his secret teal with a common color yellow to get a disguised version of his secret。

 So if you mix teal and yellow， I guess you get blue。

 and Bob is going to send blue over the channel to Alice。And now。

 once Alice has the disguised version of Bob's secret， she can mix in her own secret。

 and the result is a mix of red， which is her half and teal， which is Bob's half and yellow。

 which Bob mixed into his half， to get that common secret， which is some gross looking color。

 but it's a secret。And Bob will do the same thing。 He has received orange。

 which is a disguised version of Alice's secret， and he will mix in his own secret， which is teal。

 And the result is the same thing。 It's a mix of red， which is Alice's secret。

 the common color yellow and teal， which is Bob secret and Bob also gets that same gross looking color。

 So that's how it works。 The final color is a mix of Alice's secret。

 Bobs secret and the common paint， And when they exchanged secrets。

 they use the common paint to disguise their secrets。 Now， if your eve and your eavesdropping。

 What do you see， You see the orange， which is a disguised secret。 And you see the blue。

 which is a disguised secret。 And the trick that makes all of this work。

 is to assume that it's hard to separate out paint colors。

 So even if I know that the blue is a mix of yellow and something else。

 there's no way to separate out the paint。😊，And remove the yellow to get the original color back。

 That's what we're assuming。 And likewise， if Eve sees the orange。

 she doesn't know how to undo adding the yellow to get the original red back。

 So she has no way of recovering those original halves of the secret。

So that's what the color based analogy looks like。

![](img/6531f4f57b38232f294c6ba673e2d625_2.png)

Let's restate the color sharing scheme one more time with some slightly different colors for reasons that will become clear soon。

The first step is for Alice and Bob to generate each half of the secret。

 So Alice generates her half of the secret， which is amber， a for Alice。

 and Bob generates his half of the secret， which is blue B for Bob。 Also， Alice。

 Bob and everyone else knows about some common public color， which here is green。 Now。

 when they exchange their secrets to each other， they' are going to first disguise the secret using the common color。

 So instead of Alice directly sending amber across the public channel。

 she will first disguise it with green to send green amber G A across the secret channel。

 And Bob is likewise going to take his secret， which is blue。

 disguise it with the common color and send green blue or G B across the channel。

 So the values that are exchanged across the channel are G A and G B and Eve knows these values。

 But even though Eve knows these values， it is very hard for her。

ToSe out the green to get the original amber or blue if I show you green amber。

 you don't know that the original color was amber and if I show you green blue。

 you don't know that the original color was blue。Now。

 because each side has their own secret and the disguised version of the other side secret。

 they are ready to combine them to form the overall shared secret。 Alice has received G B。

 a disguised version of Bob's secret。 If she mixes in her own secret， which is A。

 the result is green amber blue G A B。 It's got the common color and each of their halves of the secret。

😊，And likewise， Bob received the G A over the channel。 That's a disguised version of Alice's secret。

 He mixes in his own secret B， And the result is also green amber blue。 It's the common color。

 Bobs secret and Alice's secret。 So Alice and Bob have successfully negotiated a shared secret。😊。

Now if you're Eve， you might try to get clever， maybe you saw G A and GB and you want to mix those colors together to try and obtain the secret yourself。

 but even if you try to mix green amber and green blue your resulting color would be something like green amber。

 green blue or G A GB， there's too much green in there。

 it's not the same as the color that Alice and Bob obtained。

 So the analogy is stretched a little bit here， but you can see that Eve。

 even though she knows G the common color and G A and GB。

 the disguised versions of each half of the secret。

 she is unable to obtain the shared secret because separating paint is expensive So that's it for the color analogy with some apologies if you are colorblind but coming up next we will do all of this in actual math。

