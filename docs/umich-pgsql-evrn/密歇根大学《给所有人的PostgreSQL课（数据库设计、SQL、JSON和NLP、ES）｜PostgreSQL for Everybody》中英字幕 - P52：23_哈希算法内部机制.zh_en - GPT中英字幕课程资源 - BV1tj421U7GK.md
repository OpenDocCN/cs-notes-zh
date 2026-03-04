# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P52：23_哈希算法内部机制.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/bf6d5a3f49ecc84723b98ef7cda1477a_0.png)

![](img/bf6d5a3f49ecc84723b98ef7cda1477a_1.png)

So now I'm want to take a little side jat and talk to you about hashes。

The key to why I like talking about hashes is I just want to be able to use it in a sentence and people think that hashes are magic。

 but they're not really magic。There's a lot of science behind hashes。

 their hashes have great they're critical for things like dictionaries and database indexes。

 and they're really， really important， so I want to dig in a little bit。

 not so much so you could build a hash function but so that you know how they're built so that you know they're not magic。

So a hash function is basically a function that takes a large amount of data from one character to a million characters and performs some computation on that data and end end up with a fixed length resulting。

Value。And it's not a random value， it is a value that is that if you take the same data and run it through the hash function。

 you'll get the same value， but the idea of the output of the hash function is a fixed size。

 it might be 64 bits or 128 bits or 256 bits but that's the idea now within that there is a whole bunch of science。

Now why do we need hashes So you send a bunch of data over a network and that network might have some flaw。

 it might confuse something。 it might flip a bit or something And so what we would do is we would send the message and then we compute a hash as we were sending the message and then we would send a fixed length 128 checkum in the message and so then we would receive the message run the same calculation on the data as it comes in we check the checkum if something goes wrong。

 it's thrown away Now the checkum is often done in networking on much lower level protocols like ethernet or w-fi they would automatically retransmit So checkums are not something you're going to see a lot in your use of networks。

 say in Python or whatever but in the underlying media like the w-fi or the ethernet or even the phone connection there's a lot of data checking going back and forth because Wifi is not perfect right Even ethernet is not perfect in phones phone modems。

arere also not perfect and if you're using sort of wireless on your phone， that's not perfect。

 And so when your data is being sent。Between your phone and a tower。

 there's a little checkum and then what happens is is the tower rejects it and says you know。

 I didn't get all that because you know somebody did something like a car started their engine or caused some interference and so it ate part of the message but it knows that because of this checkup so hashes are a checkum。

Another one is a cryptographic hash and so we can use hashes sort of for basic testing or we can use them for like checking a signature and in a sense when we're using a hash for cryptography。

 we hold it to a higher standard。And hash functions are essential to Python dictionaries and database tables and database indexes。

 and so it's really an important kind of underlying technology concept that I want you to understand。

So there's a couple of things that we look for in hash functions and there is a whole people spend their whole life researching hash functions。

 literally that it's an area of researching computer science， we don't have to know it。

 but we can be thankful that some people build these really good hash functions。

 so deterministic means that it's not a random number you put the same large amount of data in and the same thing goes out。

 sensitive means if you send 100，000 characters and you change one character。

The hash better be different。Right。So uniform distribution is kind of related to sensitivity in that you shouldn't just like generate if you just take a bunch of random data and compute hashes on all the data。

 you should hope that it uses all the bits。 So if it's like a 64 bit hash。

 It shouldn't just give you numbers from one to 10。

 It needs to use all possible combinations of 64 bits。 So just uniform distribution。

 So it's a pretty easy you take a bunch of random data。

 you run it through the hash function and they kind of see where where it happens and that's so that they don't cluster or they don't collide because you really want if you have a bunch of 100 character strings。

 you want them spread out in the hash。Sensitive again， any change in input。

 whether it's adding a character or changing a character should provide a change in output。

 One way means that you should not be able to derive the input looking at the output。

 You can't go backwards now。In a sense， if you have a million characters and it comes down to 64 bits。

 it's kind of impossible to go backwards， but sometimes you're hashing things that are pretty short。

 like passwords and actually hashing passwords is a common technique。

 so you're not storing the plain text password， but it can also get you in trouble。

Short passwords can become hashes， but then you can't go backwards and this is kind of one of the reasons that they want passwords to be really long because if you have a really long password。

 then it's longer than the hash and it's harder to reverse it and so we'll talk a little bit more about cryptographic problems。

So。I want to show you， I know it's just easy to learn all the read the Wikipedia。

 but I want to actually show you a hash computation， okay？

So I'm going to show you a couple of operators in Python。

That you probably will never use and after this you'll probably never see， but I don't care。

 I think it's awesome Okay， so what we're going to do here。

 me get you let me get this nice pointer thing。Remember I was talking about the actual bits right so this is the zeros and ones and this is the zeros and ones are how the computer actually stores the data and then things like 15。

 So this 11，1，11。 So this is this is 1，2，4，8，16 So this 15 is 8 plus 4 plus 2 plus 1 That's 1，1，1。

11 and that's 15。 And so that's how we represent digital integer numbers。

 And you can print numbers out。 So I got like x equals 15 and y is the ordi position of h which is 72。

 And I'm using this python format and is 0，8 B to say print this out print out x followed by x as an integer。

 but then I want to see x as bits。 And so that's why we see x 15 and then 00，00，11。

11 so I can print these things out And I'm only showing you this because I want to show you debugging。

Okay， so these operators shift， operate on the bits。 so left shift to one shifts these bits over。

 and exclusive or combines the bits in a way that if the bits。Are different， it becomes1。

 And if the bits are the same。 it becomes a 0。 So 1 plus 0 is 1，0 plus 1，0 plus 1 is1。

 and one plus1 is 0 and 0 plus 0 is 0。 So if they're different， it's a1。 and it's a way of doing a。

 it's kind of an addition， but it's a merging addition。

 So addition makes numbers get bigger all the time。 you can exclusive or two numbers together。

 and it's kind of a merger of the two numbers， but it doesn't get bigger。

 So if I keep adding 10 to something。And so it's a way of taking each letter and sort of merging it into the same width。

 so I could take just the exclusive or of a bunch of letters。

And and is what's called masking and and basically so if we take this 15。

 which is all one bits here and0 bits at the top， so it's 40 bits and 41 bits。

 it's a way to take this X which is 72 right here and it basically masks off and forces all the first four bits to be zero and then it copies those bits so that's an and okay so that's this and you can take a little time to understand this。

 but then I want to move on and show you how a hash function works。



![](img/bf6d5a3f49ecc84723b98ef7cda1477a_3.png)

So this is like a very simple hash function in Python， and you can grab the code for this。

And the only line that really matters is right here。And so we're going to enter a string。

 We're going to stick with ASI， but it sort of doesn't matter。

 I'll just get out of this loop if there's nothing there and this hash value is an accumulation。

And so what we're going to do。Is go through each line， each character。

And we're going to take the old hash value and we're going to left shift it one。

I'll show you this over here， then we're going to exclusive or it with the ordinal number。

 the integer number that's equivalent to the letter。

 and then we're not going to let it get bigger than 32 bits and so we're going to and it with0 x。

 that's a hexadeimmal digit， FFF F F FFF。6 f's。 and that just means this thing is going to get bigger。

 we're going to jam in。 so it's like we're taking a character， we're shoving it over to the left。

 we're merging in the next character， we're moving that to the left， merge the next character。

 move it to the left， merge the next character， move it to the left move over to the next character。

 move it to the left and then what we're doing is we're chopping it off anything that gets bigger than3 six times for 24 no。

little well， the stops at that size。And so then what I'm doing is if this hashve is list in 2000。

 I'm printing it out in the letter， the bits of the actual letter， the working running hash value。

 and then the letter itself that we're looking at。And hash value in integer。 So if you look at hello。

So what you see is that we first character is this that's a H and the hash value is just the first character。

Then we get this E。 So what happens is the current hash value gets shifted left1。

 and then we combine using exclusive or into that left shift so the E affects all these bits。

So we're like shift， merge， shift， merge， shift， merge， and you see this thing growing。

 Now eventually it will stop growing because we're only going to let them get as long as this。

We are only going to get them this long okay so but I'm only showing you the first part。

You don't have to fully understand this， you kind of see this shift merge， shift merge。

 shift merge with a maximum length and cuts part of hash functions that they're a maximum length。

And so if I if I end up with hello， the hash result is 1711 I and this is a sensitivity。

 I change one character。The uppercase H to the lowercase H。And then the hash result is 1199。

 So one character change needs to change the resulting hash。 Now， if I just flip two characters。

 E and H， that also changes。 So this is the same characters， but in slightly different order。

 And so this is 047。 And again， that's why you shift， then merge and shift and merge。

 So if you put in an， if you put in an H， then shift and merge in E。

 It's quite different than putting in an E and then shifting and merging the H。 So order matters。

 length matters。 the characters matters。 upper lower case matters。

 What I' am showing you is a lousy hash function。Okay， but it's one that if you take a look at。

 you can kind of understand， you can run the code and you see this shift， merge， shift， shift。

 merge mask， shift， merge mask， shift， merge mask。Okay。

 now a thing you might want to try is can you come up with two strings。

 just short short strings that。Come up with the same hash。 So so far， I've shown you no collisions。

 right， but a hashing function is bad If you can take two input strings that come to the same hash value。

 This one's not too hard because it's a terrible hashing function。

But it is the essence of how hashing functions work， okay？

So designing real hash calculations is serious work。

 there is this organization called the National Institute of Standards and Technology called NIST that runs multiyear competitions when new hashing algorithms are needed。

Now， what happens is we have a hashing algorithm。 Somebody comes up with it。

 Maybe they publish a paper in the old days。 They just like， here's my hashing function。 I go like。

 yeah， that looks pretty good。 And then everyone start using it。 And then someone would。😊。

Do research on what's wrong with that hashing function。 And we call these flaws。 And we're like。

 well， I have these two strings， and I run them through your hashing function。

 So my hashing function is highly flawed。 All you have to do to kind of discredit my hashing function。

 This one here。 If you find two strings。And it's not hard if you find two strings that come up with the same hash that are different。

 then you're like， that's a lousy hashing function。And so what happens is this is。In some ways。

 some of the purest computer science research because a hashing is a beautiful。

 simple algorithm that's easily expressed and I can put it out there。

 and then another person can find the flaw in it and they just say here's the two strings that crash your hashing function is flawed or I fix your hashing function and I think mine is better than yours。

 So what happens is is a NISist will have competitions where teams from all over the world will propose new hashing functions。

 and then they have so everyone has to sort of like put out their hashing function for the new hash the new technique and then all the teams go attack each other's hashing function and so then they like so you got 30 teams doing it。

 you're one， you put yours in and then you go attack 29 of them right and then if you and so you have 29 people beaten on your code to try to find out what's wrong with yours right and then they have。

und where they okay， here's the top 10， these 20 or everyone blew those up。

 So then and then what they do is have another round of those 10。

 So they maybe let them change them a little bit from the learning of all the all the things that were wrong with them。

 So they tweak them a little more。 And then they have a series of things。

 and this takes more than a year and they have conferences about it。And it's really。

A super fascinating thing， because when it's all said and done。

 it's a little tiny function that we call。MD5。Okay， so tons of research。

 lots of people M5 is the Iranian is the next one， Schh 256 is the one that is a multiy。

MD5 is a very early hash that was。Beovved right it's 128 bit hash。

 which means you get 128 bits out no matter what。 And so when you go look at hashing you know you go start reading up on hashing in Wikipedia you'll see these pictures right and so what we're basically doing here is these are shifts combinations and exclusive Rs okay and so that's what's going on here。

 there are things that are being this is like exclusive or this。

 So this is like that old HV value before and after because I wrote a loop that goes through every character and this is telling you what to do when you encounter a character and I think this is going through four characters at a time ABC and D and it's doing something to those characters and shifting it and exclusive oring it and doing a whole bunch of stuff and so that's what's going on here and and so somebody came up with this it's a loop just like the one I showed you except the middle parts a lot more complex because it's actually going through four characters at time。

And I don't know the year， but this has been around a long time。 and it's widely implemented。

 There's a function inside Postgress called MD5 that takes any string and gives you back the shortened version of M5 will'll show you that in a second。

 widely implemented， but it was also ferociously broken for cryptography。 Now。

 people will tell you that MD5 is terrible And for like if you have100 documents and you want to check which ones are unique。

 M5 is fine for that。 The problem with cryptography because because the people making those documents aren't trying to construct the documents to cause a hash collision。

 if you're just looking at documents that are not intentionally trying to break M5。

 it's actually not that easy to break M5。 turns out there's whole conferences these days I'm breaking M5。

 which is， I think， wonderfully fascinating it's all been broken。

 but now they're trying to break it faster。And if it's cryptography and you know you are sending data to a trusted source。

 two trusted sources， and I can grab your data and I can twiddle with it and then move it on and the signature verifies that's when it's broken for cryptography so if I'm it's going by you signed it with MD5。

 I grab it， I alter it and I keep the same MD5 signature then can I can fake your data。

 and so that's why MD5 is broken。In those situations where someone with an intention to alter your data in transit can do so。

 the other problem that happened with MD5 that's kind of funny and fun is MD5 is not technically reversible。

But because people used MD5 to hash password， so they would take your password， which is Puppy 1，2，3。

 they would run through MD5， which get this random of number。

 they would store that in the database and then when you type your password，Puppy 12，3。

 it would hash that and check the database， and that way they're not storing your plain text password in the database。

And so you think， oh， that's great because M5 is not really reversible to do all possible combinations of all possible passwords。

 but the problem is is that the way we do passwords is there's a lot of common things there's a lot of you know sequences of numbers like 1。

2，3， the word puppy， the word puppy with the you turned into something and so what's happened is is the world has collected。

A lot of plain text passwords and then run an MD5 computation on those plain text passwords and end up with terabytes of data。

 but if you type in an M5 that is a in the strings that they've precalculated you can in an instant get the string back so it's not really running the calculation backwards。

 you can't sort of run the calculation backwards but if you run the calculation forwards on a large enough set of input strings。

 you can then do a seeming backwards calculation back for those strings and for passwords in particular so you can go rainbow tables and you can create an M5 of a puppy 123 and then you can go backwards。

 go to rainbow table and then type in the hash that comes out and it'll come back with puppy 1，2。

3 and so。Again。It's broken for cryptography， whether it's check sums for signatures or whether it is storing data in a table。

 But it turns out it's not entirely broken for things like uniqueness。

 And so we can use it for things in。Now theh was the hash function。

 that's the shot2 family of hashes that started in 2001 and took a couple years to build。The。

 the shot。2 is various length。 and Sha 256 is a 256 B version of it。 And again。

 you see this picture of like taking stuff and shifting and maing and oring and doing and moving and shifting and doing this that and the other thing。

 right， with exclusivevos。 and it's very complex。 and there was many hashes that competed to be the Shah2。

 And so Sha 256 is built in。 And so you see it's a longer hash。 The M5。

 you can do M5 function on any text that we have inside of Postgres and shot 256。

 And this isn't just in Postgress。 There's all kinds of places that have functions like M5 and shot 256 to compute these things。

So that's a little bit of how hashes work and I just want you to basically understand hashes and up next we're going to talk about how we use hashes and other kinds of index to really speed things up。



![](img/bf6d5a3f49ecc84723b98ef7cda1477a_5.png)