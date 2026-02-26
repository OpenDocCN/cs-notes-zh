# 085：-Cryptography1, Video 8- Using IND-CPA to Prove Security_Insecurity.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， so we now know what the N CPPA game is。 We saw it in action。

 So now let's go through and make it more formal so that it fully matches our definition of confidentiality。

 So before， when we talked about the game intuitively。

 we said that Eve wins if she can reliably guess whether or not it's cat or dog。

 and Alice wins if Eve is unable to guess whether or not it's cat or dog。

 But let's make that more mathematically concrete， What does it actually mean for Eve to reliably guess whether or not it's cat or dog。

 So if we go back to the game， what is the stupidest strategy that Eve can possibly do here。😊。

That's going to work at least sometimes。To me， the stupidest strategy that Eve can do is just guess zero or one。

 like flip a coin， if its heads gets zero， histails， guess one。Is that a very smart scheme， no。

 does it break anything about the encryption， no， so that's the very stupid scheme that Eve can do。

 and if Eve just does this very stupid scheme that doesn't involve any effort whatsoever。

 how often is she going to be right？Roughly half the time。 she's flipping a coin。

 half the time she will guess the right message that Alice encrypted。

 half the time she will guess wrong。 So when we say reliably guess。

 what we really mean is Eve should be guessing better than random。

 If she plays this game many times with many different words， maybe once it's cat and dog。

 maybe the next time it's to other animals。Then if she can reliably win this game with probability greater than one half。

 it means she is doing better than guessing。 and if she's doing better than guessing。

 it means she must have learned something about this encryption scheme that she should not have。

 This game must not be very secure。 She must have been able to use her powers and look at this message and realize this looks like dog or this looks like cat。

 And if she can do that， it means this game is not secure。 So E starts to win with high probability。

By contrast， if Eva is never able to beat 50%， she can try any strategy she wants。

 she can ask ChaGBT which one is encrypted， she can do whatever she wants。

 and if her guesses always come out with probability 50% of being right and she plays this for a long time and she never ends up winning a lot then that's a sign that the scheme is secure whatever Eva is doing。

 she must not be doing a very good job of breaking the scheme because her guesses are not accurate at all。

 they're as good as guessing so to really formalize this scheme what we should be saying is that。

Even if Eve is able to exercise her power and trick Alicea to encrypting messages。

 if she is only able to guess with probability one half， then we say the scheme is secure。

 She's not learning anything about the encryption scheme or the key。

 her guesses are no better than random。 By contrast， if she can do better than random。

 She's guessing with 70% accuracy，80% accuracy， that must mean that somewhere in this scheme。

 something is broken。 And Eve is exploiting that to win with a high probability。

 So if that's why we have this probability one half here。

 it's to model the fact that even the stupidest attacker can guess with probability half。

 So for Eve to really win， she should be guessing with probability greater than a half。

 That's what the game looks like。 And remember， the reason we play this game is to reason about whether a scheme is secure or not。

 Eve winning means it's insecure because she can guess a lot and guess correctly。

 Alice winning means it is secure because Eves guesses are no better than random。Okay。

One final note about NCPAA。That I think is kind of interesting。 So so far。

 we've talked about the fact that if Eve is able to guess， then she wins。

 And if she can win with probability greater than a half， she's doing better than guessing。

 And that means that the Cyphertex was leaky。 It leaked information。

 And one thing that I think is kind of interesting about the scheme is it doesn't restrict Eve to any specific strategy。

 So Eve is actually able to do whatever she wants。 She can go on the Internet and search for what message was encrypted。

 She can look at the bits and shuffle them around。 She can do anything that she wants。

 She can try any algorithm to crack this game any strategy。

 She can even try strategies that haven't been invented yet。

 And if you're able to prove that something is in CP secure。

 Then what you're saying is that any attacker or any strategy that Eve uses is never able to do better than guessing。

 So for our scheme to be secure。 it doesn't just have to stop one attacker。

 it has to stop all of the attackers。 Our scheme wouldn't。

Veryry good if it only stopped really stupid attackers but more clever attackers are able to break it。

 So when we prove security， what we're trying to prove is that any attacker。

 whether it's Eve using a very dumb strategy or Eve using a very smart strategy or Eve using strategies that we don't even know about that haven't been invented yet it doesn't matter what Eve is doing to prove security。

 we have to say that all Eavs in the world that are out there cannot do better than guessing that's what it means for a scheme to be secure no matter what Eve is doing the scheme is secure and what's really cool about this is that it means that。

So what's really cool about this is it means that you are defending against attacks that haven't even been invented yet。

 so even if their Eve is using some attack that you've never heard about before。

 if you are able to prove that the scheme is secure。

 you're saying that an Eve that doesn that you don't even know about will still not be able to do better than random。

 so I find that kind of interesting that you can prove schemes to be secure。

 even against attacks that you haven't seen before。

That's the power of using proofs to check whether or not schemes are secure。

