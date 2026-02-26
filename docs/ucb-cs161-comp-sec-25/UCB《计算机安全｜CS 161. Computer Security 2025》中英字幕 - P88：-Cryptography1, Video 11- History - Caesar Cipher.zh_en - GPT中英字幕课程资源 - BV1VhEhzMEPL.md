# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P88：-Cryptography1, Video 11- History - Caesar Cipher.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay now that we are armed with all of these definitions about cryptography。

 what it is and how you analyze schemes for their security。

 let's go through a brief history and see how cryptography has evolved over the years and along the way we'll get a chance to apply some of our definitions to schemes from many。

 many years ago and we'll see how secure they are， how insecure they are so that's our goal so we're not going to test you on any of these really old cryptographic schemes。

 but it's a good chance for you to apply the definitions that you've seen so far and see if they make sense。



![](img/dc68a47616d6138648e454e30b722143_1.png)

So let's go all the way back to thousands and thousands of years ago before computers were a thing。

We are talking prehistoric times now。 One of the very first cryptographic schemes。

 according to legend is the Caesar cipher， It a very simple scheme。 And remember。

 when you define a cryptographic scheme， you define it in terms of the encryption function。

 the decryption function and the key generation algorithm。

 So even though I could tell this to you in English。

 I'm going to use our definitions so that we get a chance to practice with the definitions that we've seen。

😊，So the first thing I will do is define how Alice and Bob agree on a key。

 All they have to do is pick a number between 0 and 25。 Those are your keys。

 So Alice might say my key is 13 and Alice and Bob agree on 13 or Alice and Bob might say the key is 24 and they agree on 24 is the key That's how you generate a key。

 Alice and Bob know the sacred number， no one else does。That's the。

Now we'll define an encryption scheme， the encryption scheme takes in two arguments。

 one of them is the key， that's your number between 0 and 25， and the second thing is the message。

 which is for now we'll assume it's some English word。

And the encryption scheme works like this for every letter， you increment to K times。 So for example。

 if you have the plane tax dog theres a lot of dogs today and the key is3。

 you would just take D and you count three letters up E， FG。 So D becomes G O。 You count3 up。

 It becomes P， Q， R。 And then G， you count three letters later becomes H， I J。

 So encrypting dog becomes G R J。 That's the scrambled Sephert that you send across the channel。

 That is the encryption scheme。 And we showed it to you in this very mathematical way。

So what's the decryption scheme。 You just do the thing in reverse。

 So you take the cipher textex and you count each letter3 backwards in the alphabet。 So， for example。

 G R J。 Well'll start with J。 and I count three backwards。

 So practice setting your alphabet backwards。 It goes J， I H G。 So the J becomes a G。 And likewise。

 the R becomes an O， the G becomes a D。 So Bob is able to recover the original cipher textext dog。

 So this is how you define a scheme using the functions that we've talked about。

 It's a very simple scheme。 but more complicated ones while becoming later。

So how do you break it Well， let's say Eve is an attacker and she sees this sign for text。

I don't know what that says。 I don't know what the key is。

 Eve doesn't know if the key was 0 or 5 or 25。 So when she sees this。

 she doesn't know how to decrypt it。 That's the goal of cryptography。

 We don't want Eve to be able to read what this message says。

 So if you're Eve and you need to break this scheme。 What would you do。

 One very simple thing you could do in this case is try all the different keys。

 So try decrypting this with key1。 And。To decryptto with key1。

 you take all the letters and you count backwards by one and you get Ibegeman Dius。 Okay。

 so maybe that's the message。 Maybe they were using some old language， but I don't think that's it。

And then you can try with key2， countable the letters， two letters back， and then try with key3。

 key4， key5， key6， and what you do is you just write out all the possible decryptions with every different possible key。

 and maybe that gives Eve a clue as to which is the correct plain text。

 What do you think is the correct plain text here。I think it's vwaa quaz G， I don't think so。

 what is it？I think it's He Caesar because that's the only one that is intelligible English。

 So here is the case where Eve is using a little bit of existing knowledge and reasoning that that's probably what Alice and Bob meant to send。

 But what we're showing here is that one possible attack that people might try is a brute force attack where they try every possible key and see what the possible plain text star that's what was achieved here So this game is not very secure。

 It is vulnerable to an Eve trying 26 different keys。

And I think that's the original message unless they were talking in some alien language。

We can also try a different attack， so remember our chosen Platex attack model and remember the chosen Pla textex attack model says that Eve has an extra power and the power is that she can trick Alice into encrypting any plain text she wants if she sends a message to Alice。

 Alice has to faithfully encrypt it with the key and send it back to Eve。So what if？

Eve exercises this power and she says， Aliceice， I want you to encrypt AAA。

 and Alice has no choice but to take the message AAA， faithfully encrypt it with her secret key。

 a number between1 and 25。And give the value back to Eve。 So Eve says。

 please encrypt AAA and she gets back the answer CC。

Doesn't this give Eve a clue as to what the key is， if Eve knows that AAA encrypts to CCC？Well。

 she can reason that to start from A and go to C， you have to increment by 2。

 That must mean that the key is 2。 And now she doesn't even have to brute force。 She has the key。

 She can decrypt the Cypher text。 So if you have the ability to attempt a chosen plain text attack。

We're giving Eve quite a bit of power so you can do things like this。

 and if your schemema is not very secure， you might end up leaking the key to Eve。

By giving her these plain text， ciphertext pairs。So this is why chosen plain text attacks are dangerous and why we want to protect against them。



![](img/dc68a47616d6138648e454e30b722143_3.png)