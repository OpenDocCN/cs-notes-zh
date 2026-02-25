# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P89：-Cryptography1, Video 12- History - Substitution Cipher.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/7df6c63c8b58cc548249589c30029c01_0.png)

So the Cs cipher， it was good， but that's so 2000 years ago。

 So let's do something a little bit more clever。 Let's say that instead of counting up for each letter。

 So A becomes C， B becomes D， that's too easy to guess。

 So what if we actually created a mapping of every character to every other character。

 And it's totally random。 So， for example， A maps to N and B maps to Q and C maps to L。

 And these letters that I'm choosing N， Q， L and so forth。 totally random。 I don't have any。😊。

There's no order to them。 It's not like there's Q and the next ones R。 There's no order to them。

 And so now things are a little bit more tough to guess。 So it's not like the Caesar cipher。

 You can now put any letter in any of these boxes over here。So as before。

 we have to think about the three functions you need to define this scheme。 So the first question is。

 how do Alice and Bob generate a key。 Well now the key is no longer a number。

 You can't say the key is two。 What does that mean， Now the key is actually this whole table。

 So the key itself is this entire table that maps letters to letters。

 And Alice needs a copy of the key， Bob needs a copy of the key。

 but nobody else in the world has a copy。 So the symmetric key is this entire table belongs to Alice。

 Bob， no one else。 How do you encrypt， You go to the table and you look up the letters in the forward direction。

 So dog becomes Z PV， How do you decrypt， You take the cipher text and the key。

 you need the key to decrypt and you check the mappings in the other direction。

 So if someone gave you。Z PV， what you would do is you look up V， that G， look up P。 That's O。

 look up Z。 That's D。 and you get the original message back， which is dog。So again。

 it works kind of like you'd expect if you wanted to write it as a formal mathematical scheme。

 you would do so with something like this。Now how do you break this。

 We could try the attacks like before。 So what if Eve did not have the chosen plain text attack and she had to do the brute force attack。

Could you do it， She could try。 She could try one key and decrypt it and see if it works。

 She could try another key， decrypt it， see if it works。 How many keys does she have to try。

 If do a little bit of math。 there's 26 possible letters that can go here。

25 letters that could go here。24 letters。 There's 26 factorial possible different keys。

 And if Eve has to try every single one。 She has to try two to the 88 possibilities。

 That's going to take a long time。 That's like life of the solar system。

 So this is an example of an attack that is possible in theory。

 Eve could certainly try all the possible keys。 But this is not going to happen in real life。

 By the time Eve is done。 The sun has swallow the earth。

 and we don't longer care that much about the message dog。 So this will work。 but it's way too slow。

 So it' not something that we need to consider in the N CPPAA game。

But what if Eve has the chosen plain textex attack Well now Eve is more powerful。

 she can trick Aliceison into encrypting things。 So what if Eve tricked Aliceison said。

 can you please encrypt the message A， B， C， D， E F all the way to Z。 Well。

 if Alice takes this message and encrypts it， what does she output， she outputs N Q L， Z K R。

 she's basically outputting the whole key to Eve。So if Eve has ability to perform the chosen plain text attacks。

 she can trick Aliison into encrypting the alphabet and she gets all of the mapping。

 and now she has a copy of the key， so the chosen plain text attack is powerful and we have to defend against it。

And it's not something we'll talk about in this class。

 but you could maybe do some analysis and reason about common characters， for example。

 E is a very common character， but Q is very uncommon。

 that's an area of cryptography that we will not really go into in this class。

 but in older times when people are doing cryptography by hand。

 that's something that people would do。Not something we'll talk about here。

 but in case you're curious。