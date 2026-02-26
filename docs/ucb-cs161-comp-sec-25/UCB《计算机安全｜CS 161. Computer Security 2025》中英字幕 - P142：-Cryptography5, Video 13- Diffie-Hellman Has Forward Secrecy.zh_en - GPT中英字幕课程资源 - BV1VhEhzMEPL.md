# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P142：-Cryptography5, Video 13- Diffie-Hellman Has Forward Secrecy.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

One useful property of the Dffy Heman key exchange is that it is ephemeral。

 Ephemeral is a fancy word， and it means short termm or temporary。

 and the reason why Dffy Heman is ephemeral is because you can throw away values as soon as you're done using them。

 So for example， once Alice and Bob finish the exchange and they derive G to the A B mod P。

 they can now throw away their original halves of the secret A and B， they are no longer useful。

 And likewise， if Alice and Bob are using G to the A B mod P as a shared key。

 once they're done using that key， they can also destroy the key because they don't need it anymore。

 and for that reason K is sometimes called the session key So you use it for a single session to exchange messages and encrypt and decrypt them and once you're done and Alice and Bob log off。

 they can both destroy K。So why is it useful for diiffy Heman to be ephemeral？ Well。

 that's because of a property called forwardward secrecy。

 forwardward secrecy is the property that a future attacker who hacks into your system cannot decrypt past messages。

 So the scenario goes like this。 Let's say that Alice and Bob right now。

 use Diffffy Heman key exchange to agree on a shared secret and then they encrypt a bunch of messages using that shared secret。

 If you are Eve right now you're unable to break Alice and Bobb's encryption scheme。

 You see G to the A， you can write that down。 you see G to the B mod P。

 you can write that down as well。 and you see the messages that are encrypted using the shared secret。

 you can write all this stuff down， but you're not able to decrypt any of this stuff right now because you can't generate the shared secret and you can't break the encryption scheme。

 So Eve right now is stuck。The forward secrecy property says even Eve in the future。

 if she's able to hack into our systems will still not be able to decrypt these recorded messages。

 so let's say a week from now Eve breaks into Alice's computer and steals all of her secrets。

Because diffy Heman is ephemeral， A， B and K have all been destroyed。

 So that means that Eve is unable to decrypt the recording that she made last week。

 and that means that Dffy Heman does have forward secrecy because it throws away any values that it is done using a scheme that doesn't have forward secrecy would allow a future attacker like Eve to steal some secrets and then use those secrets to decrypt things that were previously recorded and we don't want that to happen。

 So one useful property of Diffy Heman is that it provides forward secrecy and an attacker who hacks into our system in the future is unable to decrypt messages that they previously recorded。

