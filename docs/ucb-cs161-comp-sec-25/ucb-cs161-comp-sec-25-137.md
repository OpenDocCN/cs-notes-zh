# 137：-Cryptography5, Video 8- Stream Cipher Definition.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/520732d34db5636fbbe12df0399ef0a8_0.png)

Okay， actually I li in the last video， I know I said we were going to Diffy Human Key Exchange and I know you were excited to get to that as well。

 but before we finish PRNGs altogether， let's talk about one more application called a streamream cipher。

So remember that when we talked about one time pads。

 we said that one time pads are secure as long as we never use the same pad twice and just now we saw that PRNGs allow us to cheaply generate lots of random output so what if we use that cheap PRNG output as the pad to a onetime pad if we combine these two ideas we get a symmetric encryption algorithm called a stream cipher and it works something like this？

This is a symmetric key scheme。 So we're going to assume that Alice and Bob have a key that no one else knows。

 So what Alice will do to encrypt the message， she will seed the PRNG with her secret key。

 She will generate as many output bits as she needs。

 So if this is a really big files she can generate 1 million pseudoran bits and the PRG can do that。

 and we'll take the plain text will' exor with the PRG output and we'll get ciphertex just like in a onetime pad。

 then we'll send the ciphertext over to Bob。 and then Bob will do the exact same thing to generate the pad。

 he'll take the PRG seed it with the same key and remember PRngs or deterministic So now when Bob asks to generate 1 million Bs of PRG output。

 he will get the exact same PRNG output as Alice did。

 he can exhor that PRNG output with the ciphertext and get the original plain text back。

 And if you are an eavesdper like Eve。You don't know the secret key。

 so you are unable to generate the PRNG output， so you are unable to decrypt this message。

 so that's what the stream cipher looks like。One problem with our construction so far is that it doesn't allow us to encrypt multiple messages。

 If Alice now tries to encrypt a second message， she's using the same seed。

 so the PRNG will generate the same output。 and she is reusing the pad in a onetime pad。

 And we know that is bad。 So to fix this。 we have to actually introduce an IV and the resulting scheme looks something like this。

 When Alice wants to encrypt the message， she will first generate a random IV and she will seed the PRNG with not just the key but also the IV for this message。

 And only after that will she generate the random bits that she needs out of the PRNG。

 and then Xor those random bits with the plain text to get cipher textex。

 And now the ciphertex that Alice sends to Bob。 It's the cipher textex from the one time pad。

 but it's also the IV。 So the IV also has to be sent to Bob。

And now to decrypt Bob takes the IV that he just received， it's a public value。

 and he sees his PRNG with the secret key， which is the same every encryption and the IV。

 which is special for just this encryption that's the same seed as Alice used so he will generate the same pseudoran bits and then he can use those bits to Xhor with the ciphertex and get the original plain text back so to encrypt multiple messages we have to introduce IVs and remember to use a different IV for every message this works just fine。



![](img/520732d34db5636fbbe12df0399ef0a8_2.png)