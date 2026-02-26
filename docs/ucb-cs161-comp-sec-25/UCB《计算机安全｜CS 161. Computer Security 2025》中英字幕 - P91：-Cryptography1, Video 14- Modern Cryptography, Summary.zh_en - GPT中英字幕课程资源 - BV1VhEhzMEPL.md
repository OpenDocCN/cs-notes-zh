# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P91：-Cryptography1, Video 14- Modern Cryptography, Summary.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay now we skip forward to the modern era。 So nowadays cryptography is all done by computers。

 no one is sitting down and manually encrypting dog and cat。 And so after World War II。

 we now have the modern era and one of the classic research papers that really spearheaded the modern era of cryptography was this paper in 1976 these two guys won the Tring award for the paper I forget which one is which I think this was diy this one's Heman。

 and if I'm wrong， I apologize to them but this is the era of cryptography that we'll be focusing on so although rotors and plug wordss are very cool we will be thinking about cryptography done in software on your computer using code but I hope this section was still helpful because it gave you some practice with the definitions that we saw chosen plain text attack。

 encryption decryption algorithm Krkoffs principle So although I don't care about any of these specific stories or encryption schemes。

 hopefully you got a little bit of practice with the cryptographic definitions and hopefully that's。

well as we start talking about more specific cryptographic schemes。



![](img/4af31d2cff34389012cefd52d36ee991_1.png)

So to summarize all the definitions before we go， we started with the basic definition of cryptography。

 which is to communicate securely over insecure channels。

 And one very important thing we said is that you should never ever tried to write your own cryptography It is much too complicated and we are not showing you enough for you to go out and write your own cryptography it's really sensitive。

 a single book of bring your whole system down。 So please use existing libraries that are well vetted instead then we went through a lot of definitions。

 we talked about the characters Allison Bob sending messages。

 we talked about Eve the Eavesdpper and Mallory who can tamper messages。

 we talked about the three properties， confidentiality integrity。

 authenticity and the way that you would ensure confidentiality using encryption and integrity and authenticity using tags on messages。

 We also said that there are secret keys and Kirkhos principle says you need to assume the attacker knows the entire system and all of the code that you're using。

All of the secrecy comes from only the keys， that's very important。

We also talked about various threat models， and we focused on the chosen plain text attack。

 where Eve has the ability to trick Alice into encrypting messages that she wants。

 kind of like those allies in World War I。And finally。

 the most involved topic today was in CP security。 and to resumorize this definition in one line。

 it goes like this。 even if we confer the extra power to Eve that she can trick Alice into encrypting messages of her choosing。

 and that was encoded in the game by giving Eve a chance to trick Alice into encrypting any message that Eve wants。

 even if we give her this power。If we then run the challenge where Eve sends two messages and one gets randomly encrypted。

 Eve is unable to guess which one was encrypted with probability better than guessing。

 If her guesses are no better than random the scheme is secure。

 it's not leaking anything If she is able to guess better than random it's a sign that we are leaking things and the scheme is not secure and this definition holds for any possible strategy that Eve used even strategies that have not been invented yet and this game the reason why we're doing this is not because Eve Alices are actually real people playing games。

 it's because we use this game to test if a scheme isncPA secure or not and if you come back next time well actually take some real schemes and plug them into the game and see if you can win them。

 so you will be Eve I'll be Alice and we'll see if you can win them And remember there are three edgech cases we need it to fully finish this game NPA schemes can leak length So N0 and M1t have to be the same length Eve is limited to polynomial time algorithms because we don't care about a attacks that take。

The length of the universe to finish and Eve's advantage must be non negligible so that it can be converted into a real attack。

So those are the three edge cases that we talked about。

So that's it for this set of videos and if you come back next time。

 we will start talking about our very first symmetric cryptography schemes， so see you then。



![](img/4af31d2cff34389012cefd52d36ee991_3.png)