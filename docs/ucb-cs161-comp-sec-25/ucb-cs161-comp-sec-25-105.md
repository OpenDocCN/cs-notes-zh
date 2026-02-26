# 105：-Cryptography3, Video 5- CBC Padding.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， one thing I haven't explicitly called out either。

 but it's something we have to deal with is that sometimes messages aren't an exact multiple of 128 or whatever this block size is。

 So when we said that the message was 256 Bs。 Everything was great。

 You took the first half and put it here and you took the second half and put it here。

What if the messages is 257 bit。 Well then you'd have 128 B here，128 B here。

 you'd have one lonely leftover bit here。 So one question we have to ask is。

 does this encryption work if my message length is not a multiple of the block size。

 which I'm saying here is 128。 So for example， this block is full， This block is full。

 We have one lonely by here。I can try running this， but now I'm asking to encrypt the single byte。

 so I have to take that one by Xor it with 128 B of cipher text。 What does that even mean。

 How do you encrypt how do you Xor128 Bs of cipher text with one bit of plain text。

 The arguments don't match。 And then I have to pass that thing into block cipher encryption。

 But remember， block cipher encryption expects 128 B and you're feeding it one bit that doesn't work。

So you can try to pass in things that are not a length of the block size or a multiple of the block size。

 But this protocol is just not defined。 It doesn't know what to do。

 It's not clear how you would do this Xor or this encryption。 So you're stuck。

So the fix is to add padding bytes。At the end of the message。

 So add a bunch of dummy bys until the message is the correct length。 So in this case。

 because you have this one lonely by， you might add 127 more dummy bys so that now this block is all filled up。

 It's1 hundred 28 B。 You can ex it with the cipher text safely。 The result is1 28 B。

 You can pass it into the encryption。 So when the message isn't an exact multiple of the block size。

 We need to apply something called padding。 And those are dummy bys。

 They're not part of the actual message。 We are just adding them to get the message to be the correct length。



![](img/64b54f5abe48efd34c02b9f2b40a6bf1_1.png)

So what dummy bites should we actually use， What bites do you fill in as the dummy bites。

 You actually have to be really careful here。 There are some traps you can fall into。

So one idea might be to just put a bunch of zeros at the end。 So if you have one here。

 then start adding zeros all the way until you reach the next multiple of the block size。

 But now we have a problem， What if your message already ends in a0。

 So maybe you have a message that's like give me $100。

 So you have 100 and then you pad a bunch of zeros。 Well， then when Bob decryptps the message。

 he has to remove the padding， how does he know where to chop off the zeros。

 What if he chops off too many zeros and now it says pay 1 instead of pay 100， that's not so good。

 So if the message ends in zeroes and you also pa in zeros。

 it's not clear where the message ends and the padding begins。 So it's ambiguous。 We have a problem。

You could try padding with the number one， but you have the same problem。

 What if the message says pay Bob $211， and then you pat a bunch of ones。

 How do you know which ones to remove。As part of the padding， what if you remove too many ones。

 And instead of saying 211 in the message， now its says 21 or2。

 So padding with zeros or ones or any constant number has a problem of ambiguity。

 It's a very subtle trap that you can fall into。 So to fix it。

 you have to be a little bit more careful。 There are some different schemes that work。

 and you'll actually get to explore some of these in your homework。 But that's something you can try。

 So one example， and you'll see more of it in your homework is to pad by the number of bys you added as padding。

 That's kind of clever。 And it turns out to work unambiguously。 Although I have proven it here。

 So just know that padding is easier set than done。 And there are some traps that you can fall into。

😊。

![](img/64b54f5abe48efd34c02b9f2b40a6bf1_3.png)