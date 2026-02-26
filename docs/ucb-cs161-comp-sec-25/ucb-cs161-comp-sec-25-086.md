# 086：-Cryptography1, Video 9- IND-CPA Edge Cases.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， so we now have a definition of NCPAA。 There are a couple of edge cases we have to do to make this mathematically rigorous。

I don't think they are the most interesting thing， but because we want a mathematically rigorous definition。

 we have to do them。 So let's talk about three edge cases that we have to cover to fully finished our definition of NCPA One edge case is length。

 So it turns out that in practice cryptographic schemes are usually allowed to leak the length of the message。

 So earlier we said that the scheme should not allow Eve to learn anything about the message。

 but usually in real life， we make an exception for length and to see why let's imagine a case where you have to hide length。

If you have to hide the length from the attacker， you have to make sure that every ciphertex has the same length。

If some cpher texts are short and some cpher texts are long， Eve can use that to deduce。

 This was a short message。 This was a long message。 If you want to hide that。

 you'd have to pad every single message to the same length。 So if a message is really short。

 you'd have to add some garbage bys so that it's the same length。

 And so Eve cannot tell which message is longer and which message is shorter。

So if all messages have to be the same length， what is that length， I could choose a short length。

 like 16 by， But if all messages and all cipher text are 16 by。

 now I can't encrypt longer messages if I have a video that's probably way bigger than 16 B。

 I am no longer able to encrypt the video。 That's not great。

 So maybe the other option is to make the messages all really big。

 all of my messages are one GB long。 And if I want to send a small message。

 I have to pad it with garbage by until it reaches the total length of1 GB。

 this allows me to hide the length from the attacker。

 But now this means that if you send a text or a tweet。

 what do they call them now if you said an X or something。 Well， you still need one gig of bandwidth。

 that's really impractical。 Imagine sending a little message like hello world and it requires sending one gig of data across the network。

 that's not practical。 So in reality， hiding length is possible。

 but it ends up being very wasteful because you're adding all this pad。

To hide length from the attacker。 So in reality， what we usually do is we make an exception and we say it's okay if Eve is able to learn that my message is short or long。

 As long as she doesn't learn anything else about the message。 And if you want to hide length。

 you have to add your own padding。 That's not something that the scheme will provide for you。 So。

To make a long story short， cryptographic schemes are usually allowed to leak the length of the message。

 So this means we have to go back then adapt our game to account for this edge case。

 because right now， our game doesn't account for this edge case。 You can just。Send a short message。

 send a long message and she can figure out which one was encrypted and that doesn't take into account this edge case so to fix our game。

 to take into account this edge case， we are going to enforce that M0 and M1 the two messages that Eve chose。

 they have to be the same length。 for example， you send cat。

 you send dog they are the same length you can't send a short string and a long string and use length to distinguish that's cheating to break in CPPA you have to learn something else besides length because we are allowing length to be leaked so that's the very first edge case it's the fact that it's okay to leak length so therefore in NCPA you have to leak something besides length so you have to send two equal length messages and be able to distinguish something else of them。

Okay here's a second edge case。 There are some schemes out there that are vulnerable in theory you can write out an attack。

 but trying to execute that attack is going to take really， really long。

 and I'm talking about life of the solar system kind of long millions of years So there are some schemes out there where you can't actually attack them and someone has written up an attack but someone trying to execute that attack would not finish it for millions and millions of years。

 And remember all of the cryptography， the cryptography that we're doing is based on modeling attackers So one question we have to ask ourselves is do we really care about an attacker that's going to break into our system in1 million years I certainly don't And so if it's the case that we don't care about these attacks we should also change our game to account for the fact that we don't care about attacks that take an unreasonable amount of time to complete。

 So in the NCPA game， we're going to say Eve cannot take。Forever to break the scheme。

 If you have a scheme and Eve is able to break it， but she takes a billion years to do it。

 that's not an attacker that we realistically have to worry about。

 we should only think about the attackers that are limited to some practical runtime and what practical means depends on your threat model What do you consider practical if someone can break it in 100 years is that practical。

 So it kind of depends on your threat model。 The way that we will formalize it in our class is we'll say Eve's algorithms all have to run in polynomial runtime。

 So whatever it is that Eve is doing behind the scenes to try and break the scheme and win the game。

 the thing she's doing have to be polynomial time algorithms。

 O of n squared is okay O of n cubed is okay but O of two to the n is not okay that's exponential time that's just one of many ways to formalize the fact that。

Some attacks out there do work in theory， but take way too long so we don't care about them。

 they will never happen in real life。That's our second edge case。There is one final edge case。

 There are some strategies out there that work with probability one half plus a really。

 really small number。 For example， Eve might have some strategy that wins with probability one half plus one over2 to the 128 so she is winning more than half of the time。

 but if you play this game in real life， are you really going to notice Eve having an advantage not really this number is like 50。

00000001%， it's as good as 50%。So in order for Eve to win and for us to say that the scheme is insecure。

 Eve has to have what we call a non negligible advantage。

 And we're not going to define this mathematically for now。

 but you can imagine something like twotds is nonnegligible。

 She is winning with significantly better than 50% probability。 But something like 50。000001%。

 that's negligible， we don't particularly care about that。 because yeah。

 maybe Eve is winning more often than random。 but that kind of advantage is so small that it cannot be converted into any real attack。

 So even though she can win the game， she can't actually execute any realistic attack with these kinds of odds。

 So we're not going to worry about attackers like this。

 that can win with just slightly better than half。They are not relevant in our particular threat model。

 So this is the third edge case and to give you a concrete example of something that might work with this kind of probability。

 maybe there's an attack where Eve guesses the key and if she guesses right then she can decrypt the message。

 find out if it's cat dogg and she wins。 That's a strategy but it's not a very good one and it's not going to work in real life most of the time just guessing a key。

 so we're not going to worry about a case like that。

 because even though the strategy of guess a key and C if it works does give Eve better than one half probability the advantage is so small that it cannot be converted into any practical attack。

So to summarize， those are our three edge cases， One is we don't care about length to fix that。

 we change the game to restrict Eve's challenge messages and 0 and M1 to the same length。

 Second edge case was we don't care about the run， we don't care about attacks that take forever and that have really long runtime。

 so we restrict Eve to using polynomial time algorithms that finish in a reasonable amount of time and the third edge cases we don't care about attacks that are we don't care about advantages that are so small that if they cannot be converted to practical attacks。

 So Eve has to win with better than 50% in a nonnegligible way， something significantly。

 And if you care about the definition， I've listed it here but you don't have to know it for this class。

