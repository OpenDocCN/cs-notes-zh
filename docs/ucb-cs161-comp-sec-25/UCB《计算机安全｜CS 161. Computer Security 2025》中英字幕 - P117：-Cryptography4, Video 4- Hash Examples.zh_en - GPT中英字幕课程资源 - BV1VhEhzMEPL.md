# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P117：-Cryptography4, Video 4- Hash Examples.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay here are some examples of hash functions。 So these are the actual algorithms that you would use if you wanted to implement a hash function and these are algorithms that attempted to provide one wayness and collision resistance some of them succeeded。

 some of them failed So a very old hash function that attempted to be secure was called MD5 but this is from。

 I think the 1990s and at this point people have found all sorts of attacks on M5 So if I give you an M5 output。

 you can break one wayness you can find an input that hashes to the same output。

 if I asked you to find an M5 collision， you could do so you could find two different outputs that mappeded the same input So although it was initially designed to be secure as of 2025 this thing is completely broken and if you use it it's not for cryptography people still use it as a hash function for other purposes like the fingerprint on the document or something but if your goal is to get integrity。

or one way in this or collision resistance， MD5 is not going to help you。

 it should not be considered secure anymore because it's too old。And in fact。

 here's an example where someone broke the MD5 hash， they found a picture that hashes to this value。

 so it's very bad。So MDD5 was the first attempt and it didn't work at all， so sometime later。

 something called Shaw1 was designed and this was secure for some time but attacks were found and as of 2017 you can't use Shaw1 anymore either for security if you do it's not going to be good for you。

 people can find collisions on Shaw1， they can reverse Shaw1 hashes given an output find an input that matches the output so Sha1 is also broken。

 although older systems might try to use it， you can't use it anymore it's no good。

So then they moved on to Sha2 and something I haven't called out yet is that the output size seems to be growing so I notice that now they're starting to provide outputs of 512 bits and hopefully that makes finding collisions harder as of 2025 Sha2 we don't think it's broken but who knows maybe in future years it will be although some variants are vulnerable to something called the length extension attack which you will see in your homework or you can look it up online if you're curious so there is an attack on Sha2 that doesn't break one wayness or collision resistance but there is something called the length extension attack that it is vulnerable to that is separate from those security properties that we talked about so Sha2 is an option in that its not broken but there are some subtle attacks that you can still play on it and for a lot of people this is what they use nowadays if they want to secure hash even better than Sha2 though is something called ShaW3 this is like the newer standard and it's a little。

different from shot2， the way that it works。 if you really open it up and look at the code inside。

 it's a little bit different， but shot3 also as far as we know is not broken。

 but I guess if you come back to this video in like 25 years maybe it will be。But for now。

 just know that some hashes that are older are broken because of research over the years and other ones are currently known to be secure。

 but maybe in the future people will find flaws in them。

Those are some examples of hash functions you might see in the wild。

