# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P49：48_安全技术：加密与保密性.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

So the first topic that we're going to talk about is confidentiality encryption and decryption。

 and of course， this was what was going on at Bletchley Park in World War I。

 so the terminology that we'll use in this is plain text and cipher text and the idea is。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_1.png)

Whether it's text or other information， there is the information that we actually want to transmit。

 whether it's a credit card number or something else。

 And then there is the encrypted version of that。 And we'll call that the cipher text。

 And the cipher text is what we assume is revealed to intermediate parties。

 whether they are stopping it and changing it or they're just watching it。

 It's still the cipher textex is the stuff that we are。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_3.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_4.png)

Just by the nature of the communication， we are forced to reveal it。

 or there is a probability that will reveal it。 So it is hopefully unintelligible and hopefully it is difficult to go from the cipher text to the plain text。

 except if you are the actual intended recipient。

![](img/17f85cb2eb4b7a91af31df7971a30e4d_6.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_7.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_8.png)

Or impossible。Encryption is the act of going from plain text to cipher textext and returning the cipher textex back to the plain text is decryption。

 and there is a key， some kind of a key， which is really sort of some data plus a technique。

 plus an algorithm that goes back and forth。So there are two kinds of systems that we'll talk about in the upcoming lectures one is called a secret key and the other is called a public key The secret key is the one we talked about at the very beginning。

 the secret key was really used from the Romans and Caesar on up to World War I the public key encryption really is much more recent in the 60s in the 70s and we'll talk about that later on so the first thing we'll talk about is the shared secret or secret key the secret key is also calledsymmetric key which means that both parties have to be in possession of the same information you basically use the same key material to encrypt as you do to decrypt the public key is asymmetric which means you use it one key to encrypt in a different key to decrypt we'll get to that later。

And so the problem that secret key has that led to the need to invent public key is the fact that you need to at some point have a secure communication。

 whether you're sitting in room together and you hand each other codebooks， whatever it is。

 you have to have a way to distribute the key in a secure manner。The public key。

 which we'll get to later， has a way of distributing the key using insecure medium and you'll see when you're when you get there。

 it's like。So obvious and clever， you wonder why nobody thought of it until， you know。Very recently。

So here is the path， right， you have some plain text。

You have say the word candy that you want to send， you're going to encrypt with a shift where you just go to the next later letter so C becomes D。

 A becomes B and becomes O， and so now we have the DBO EZ that is the plain text coming from Alice Alice sends it in the dangerous。

 dangerous， nasty wide world of，You know， routers or radio with with Mors code or whatever it is we're going to do whatever is we're going to do where the message might be intercepted by somebody Eve now they're not intercepting the plain text we assume that this part here is secure in this part here is secure it's only dangerous while it's in flight somehow in the middle and we only worry about Eve getting it and。

And then at some point， because Bob has the key， which is subtract one。

 Bob goes from each of the cybertext letters back to the plain text letters and wila out comes the plain text again。

 And so Eve's problem is I'm Eve is only handed。Well， no， sorry， E is not Eve is not given the key。

 Eve is given the cipher text in nothing else and she must。

Like Bletchley Park must derive whatever it is， derive the key， derive the plain text。

 whatever it is， that's Eve's goal。The Caesar cipher。Is the kind of the oldest。

 most widely used forms of encryption， it uses the notion of a shift。The shift number is just。

 as I shown， a shift of one means a becomes B and X becomes Y and L becomes。LM L L becomes M。

 So you just take and move a fixed position down the L。

 This was used for a surprisingly long period of time。

 And there's some pretty good YouTube videos that kind of you can。

 if you want to see more about sort of the the how this works and the math behind it and how you break it's it's pretty fascinating。

 I mean， finally， it's just it's completely breakable and we'll actually going to break it here pretty soon ourselves。

 So the Caesar cipher。So I want to pause and let you see a YouTube video here from a beloved movie called The Christmas Story。

 where Little Raley gets his Little Orphaani secret decoder ring and Little Or Fanni sends a decod message。

 an encoded。Cypher text through the radio。 everyone can hear it。

 but only those people who have a secret decoder ring can decrypt the message and you can see that it is a Caesar cipher。

 It has a shift。 you'll note that the first thing they say before they say the encrypted message in the radio is that you're supposed to connect B in 13 or something like that。

 and then you rotate the two wheels of the secret decoder ring to the B13。

 And then you can read across the secret decoder ring and decrypt the message as it's decrypted。

 and then he slowly decryptps it， and then of course。

 there is the delightful moment where he realizes the crash crashas commercialism that。

Or the complete lack of interesting meaning in all of this so without further ado。

 let's take a look at Ralphfi and Christmas story be right back。So I hope you like that。

 hope you like that。And so off we go， we are going to have a secret decokota ring for this class。

 I would love to be able to send you all。Come down I would love to be able to send you all a little mechanical wheel to move the stuff back and forth。

 but instead I use the internet and I'm going to send you a PDF and at this point you might want to pause the video and grab this pf okay grab it secretecredecoder。

pdf Drchuck。com/secreddecoder。pf and download it and you might even want to print it out because we're going to at this moment。

Do a code breaking exercise， okay？And so let me tell you how to use this secret decoder ring。

So the top line here is the plain text。And if you recall， Caesar Shi has a shift number。

And so to encode， you go from a plain text， let's say I want to do Chuck。

I want to encode Chuck and I want to encode it with a shift of two。

So a shift to two means we select this。And we basically go C is our plain text。And then down。

 we go E， so then we go E is our first letter， and then H。Is our second letter？So we go down。

 and that means H becomes J。Yeah， and so you。Becomes W。So now I'm doing my encryption。

 so EHW is the encrypted Cytext， so let me clear that。And right back down here， do。

 me different color。E HW Now to decrypt， remember， you need to know the shift。

 so we somehow communicated separately and securely what the shift was。

 And so now we want we have received our cipher text。嗯。

We received our cipher text and we need to decrypt it。And so we know that the shift is  two。

 so we go to E， we go in the shift row。And then we go up to the plain text row。

 and that says the first one is C。 Then we go at H。 We go to the。Encoded text row。

 and we go back up to the plain text row， and so that's an H。 Oh wait， wait wait。It's not HW。

 What am I thinking， this should have been a J。 I got this wrong。 Sorry about that。 So that's wrong。

 Here's a J moves up to the H。 Then the W， let's see if I got W， right。 Yeah。

 So W is my last ciphertex。And it goes up to the U。Okay， dot dot dot dot dot。

 so you see the pattern that our encoding is plain text down to shift position and our decoding is shift position back up to plain text。

so this is our secret decoder ring， so go grab it and download it so that you can participate in the next exercise。

So now you are going to be cast in the role of。Bletchley Park。Okay， ready。

 So here is your first code breaking exercise。O。So here we go。🤧嗯。😊。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_10.png)

So you're bletchley parked， right， You just intercepted this cipher text， you be。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_12.png)

Now UBTU。

![](img/17f85cb2eb4b7a91af31df7971a30e4d_14.png)

Whoa， it's encrypted， it's clearly meaningless。So how are you going to decrypt it， Well。

 the technique is。

![](img/17f85cb2eb4b7a91af31df7971a30e4d_16.png)

Take a look and decrypt it with all the shift numbers right， you're going to do this by hand。

 you're going to be a computer yourself， you're going to do all the shift decrypting。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_18.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_19.png)

And just like in Blesschley Park， you know you succeeded when the plain text makes sense。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_21.png)

When the plan textex makes no sense。

![](img/17f85cb2eb4b7a91af31df7971a30e4d_23.png)

Then you haven't succeeded， but at some point the plain text makes sense。

So what you need to do is take your secret decoder ring。

And you need to decrypt it with a shift to one， a shift to two， a shift of three， a shift to four。

 and if you have your family members around， you can print out multiple copies of the secret codeder ring and you can assign different shifts to different family members so you have to decrypt this 26 times。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_25.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_26.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_27.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_28.png)

You have to decrypt it 26 times， and then you look at all the 26 decryptions and then you decide which one makes the most sense。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_30.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_31.png)

ok ，就。Don't peak。Deryptus one。

![](img/17f85cb2eb4b7a91af31df7971a30e4d_33.png)

I made it easy on you。Okay， so we'll stop now and give you a little bit of time to decrypt this one。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_35.png)

Don't start pause until you actually have decrypted it， okay？



![](img/17f85cb2eb4b7a91af31df7971a30e4d_37.png)

![](img/17f85cb2eb4b7a91af31df7971a30e4d_38.png)

Okay， this is your last chance for spoiler alert， so here we are， we're about to decrypt it。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_40.png)

Here we go， I did make it easy on you， it was a shift to one。😡，Its a shift to one。

If you started at 12， you're kind of foolish right， So you started at one and you go like， oh， great。

 So now I'm going to decrypt it。 I'll start at one。 here's the plain text。 that should be PP。

 That's the plain text。 So I'll start with you if it's one。Then I go up and it's T。

And the second one is P。So I go up and it's O T O， keep going， it says toast。So you say to yourself。

 well， that's a word， so it must be it。Well， hellello。What are you doing here？

Don't say I have my students？This is a gap。This is eticare。He likes to come up into my office。

And look。So do you know anything about encryption？嗯。😊，You don' think about encryption。

 so you use a shift of one。And then you go from the encrypt text up to the plain text。Well。O。

You are clearly not interested。In my lecture， so that was my cap hello。Sorry。

 can't open a window for you because I'm doing a lecture。O。嗯。so。

You're going to like just keep buggging that window until I kick you out of the other room I aren't you。

 so you're going to have to get kicked out。Sure。How do。He was going to keep hitting there。

I'm going to keep hitting that until I opened it for them。Okay。

 so so now you have broken this code and again， just like in Bletchley Park。

 you only knew that you broke it if it made sense and so luckily in Bletley Park。

 the messages were longer and they were often looking for canonical things that they would say every day。

So here we go。And so that's the breaking of that one。

And it turns out that shift to one was the thing that we did。So here is your second task。

This one's longer and it's not a shift to one。

![](img/17f85cb2eb4b7a91af31df7971a30e4d_42.png)

And so。

![](img/17f85cb2eb4b7a91af31df7971a30e4d_44.png)

So this is a situation where you really would have to get your whole family going on this， right。

 where you got to do 26 decptions of this。And it will you know make sense to you。

 you decrypt it 26 times， right， and so this one's going to be harder。

I guess you could just decrypt one word， but it's just not a shift of one。

But now we're going to do another trick。ok。So I don't want you to try all 26。Because there's。

 there's a mistake in this。 There is a。Lakage of information that makes it so that you can figure out what the right decryption to try might be。

 So this is English。This is an English sentence。So stare at for a while and find a more optimal way to decrypt it than trying all 26 shift patterns Okay。

 so there's a way to optimize this， a way to cleverly figure out。

What might be the best shift or how not to have to decrypt the entire message 26 times to reduce the complexity。

And that's because we've leaked some information here that should be pretty obvious to you Okay。

 so let me give you a moment to break this one， it shouldn't take you too long and you shouldn't have to force your whole family to decrypt this stuff okay。

 so here we go give you a chance to decrypt it。

![](img/17f85cb2eb4b7a91af31df7971a30e4d_46.png)

Okay， its your last chance before the reveal， you're ready， here we go。



![](img/17f85cb2eb4b7a91af31df7971a30e4d_48.png)

So here is the decrypted text。The ship turns out to be。13， it's a shift to 13。

And the weakness of this whole thing。Is this right here？In the English language。

What is a single character we're not encrypting the spaces you'll notice because the spaces come across。

So what is the one single character word？That we have in the English language。That。Capitalized。Well。

 that's usually I。I need a jet， money and a jet。 What is the one。

Thing that we do in the English language。 That is a single character word。That is all lower。

 That's lowercase typically unless at the beginning of the sentence， and that is the letter A。

So basically you didn't have to decrypt the whole message。

 you see some weird pattern and you go like this， I just have to figure out， and then you go look。

And you look in the row 13， the plain text。And you go like， oh。

 where does you go look at the eye because you guessed to the plain text and then you just look down until you see the V。

 and within seconds， literally within seconds if you do it right， within seconds。

 you know it's a shift to 13， and then it's a trivial matter。To convert。

So you could figure out the shift code within seconds and this was how Bletchley Park figured it out and this is why the known plain text was so important because you'd only have to figure out like one letter if you knew what the plain text was and often they would know by length。

And certain other things， oh， this is I think we can guess what this plain text was that this particular operator would send and this has to do with the leakage of information。

 it's not the mathematical perfection or lack of perfection in the security key。

 it's some other leak， it's some other thing where they're going like oh way a sec I can take advantage of something it was just equally encrypted as any other message but because I gave you this clue of an uppercase single character word and a lowercase single character word。

Upper lowerercase single character word and uppercase single character word。

 I greatly reduced the amount of effort that you had to put in， okay？Now， what's cool about this？😡。

And you can go to this website， wwwro 13。com is that long ago before Facebook and before Twitter and before all these things。

 we had these things called news groups。And they were kind of this weird kind of collective email list that we had。

 and this was like in the 80s。And it was even used in St forward networks where it was kind of like Facebook and stor forward networks。

 meaning that it might take。4our hours for you to see the status update。

 But we kind of would subscribe to these collective things。

And there was one that was basically the dirty jokes。

And the thing about dirty jokes was part of what we were trying to do in this thing was you weren't supposed to swear。

 and there was software that would filter out swear words。诶。

From if you put a swear word in to a dirty joke。It would not forward the message。

 and so we had to have a way to encrypt messages that included swear words。

So that we could tell dirty jokes to each other for those who wanted to subscribe to the dirty Jo list。

And so they came up with this wrote 13， so we came up with a simple Caar cipher with a shift of 13。

 13 beautifully of course is 26 divided by 2， so it's a symmetric shift。

 the shifting in by 13 is the same as shifting out so of all the C Caesar ciphers， a shift of 13。

 the encryption in the decion are exactly the same calculation。

And so we would type our dirty joke into Ro 13 and convert it to Ro 3 and we would send it in Ro 13 and then we would if we wanted to decrypt it。

 but what became funny after a while was we were so used to reading Ro 13 that it almost became like a second language right we could read second we could start reading the dirty jokes in Ro 13 and we would laugh before we translated them out so Ro 13 as an interesting sort of historical thing and you go to Ro 13 and sort of like encrypt whatever you want to say and I'll probably have some questions to ask you where you will have to do some Ro 13 encryption。

And so that's the end of this lecture where we talk about Caesar ciphers and the various techniques and how Caesar ciphers work。

 and so we'll be back and talk about cryptographic hashes。

