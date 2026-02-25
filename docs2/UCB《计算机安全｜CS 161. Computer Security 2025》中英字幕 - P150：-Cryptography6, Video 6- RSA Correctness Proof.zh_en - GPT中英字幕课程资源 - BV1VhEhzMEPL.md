# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P150：-Cryptography6, Video 6- RSA Correctness Proof.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/c5bd6c19117603987adb13b8ef54f315_0.png)

This is a one slide proof of why RSA encryption is correct， it's got a lot of math。

 so let's walk through it。Before we can do any proving。

 we first need to establish some theorems that are true。

 These theorems were proved in a prerequisite course like C S 70 at UC Berkeley。

 So we're not going to prove them again for now， you can treat them as fact。

One fact that is true is that if some number is Y mod P and that number is also y mod Q。

 then it must be true that the number is Y mod Pq So if you divide a number by P and you get y left over and you divide that same number by Q and you also get y left over。

 then it should be the case that when you divide that number by P Q， you still get y left over。

 that is something you can prove using the Chinese remainder theorem。

 although we will not do so here。The other fact that for now you should just accept is true is Fmatt's little theorem and that states that if you take any number。

 it doesn't matter what number it is， and you raise it to the p minus1 power and then you take that number modo P the result is always1 pick any number you want。

 raise it to the p minus1 power， take it mod p， the result should be1 and here we're assuming that p and Q are prime。

 so all these theorems you can assume are true for now。Once we have our theorems。

 we're ready to go and start proving things。So as a reminder。

 the way that we define D is this very specific equation。

 we said that d is the inverse of E modo P minus1 Q minus1 Why do we define D in this very strange way。

 let's rearrange some terms and see if we can come up with something interesting。😡。

So when D and E are inverses modo P minus1， Q minus1， that means that if you take E times d。

You should get1 modular p minus1q minus1 that's what it means for two numbers to be inverses in integers it's like saying5 and1 fifth are inverses because when you multiply them together。

 you get1 this is the same idea but in modular arithmetic， if D and E are inverses。

 then when you multiply them together mod p minus1q minus-1 you should get1。

Another fact you can then derive is that E D-1 is a multiple of p-1q -1。

 There's a couple ways to see this。 One ways to remember that modular arithmetic works like division and taking the remainder。

 So if you divide E D by p-1q-1 you should get a remainder of1。

 That's what 1 mod p-1 Q -1 means So if E D gives you a remainder of 1。

 then E-1 which is one less ought to give you a remainder of 0。

 which means that E-1 is a multiple of p-1q-1。Another way to see how that step works is to subtract one from both sides。

Then you get E D minus1 is equal to 0 mod p minus1， q minus1。

 and if something is 0 mod p minus1 q minus1， then we know that it is a multiple of p minus1。

 q minus1。So all we've done here is take the definitions of E and D and somewhat do some rearranging to get this useful fact that ED minus1 is a multiple of p minus1。

 Q minus1 shouldn't be quite obvious why we want that fact yet， but it's a fact that we have proven。

So at this point we have our two handy theorems and we also know from the definition of E and D that E D minus1 is a multiple of p minus1。

 Q minus1， and at this point we're ready to tackle the main proof。

So remember that the thing I am ultimately trying to prove is that RSA encryption is correct。

 Remember that encryption is raising something to the E power mod n and decryption is raising something to the D power mod n。

 and I want to show that anything that I raised to the E power and then the D power mod n gives me the original message M back。

 So my strategy for proving this will be to take M to the E D mod n。

 and I will try to massage that term as much as I possibly can simplifying it using my theorems and the fact that I showed earlier and try to get the original value M back So I could do this mod n。

 but mod n seems kind of tricky。 none of my theorem say anything about n。

 the fact that I proved from before doesn't seem to have an n inside。So here's what I'm going to do。

 I'm going to prove that M to the ED is equal to M in modD P land。

And then I will show that it is true in mod Q land。

 and then I'll use this handy fact up here that says if two values are equivalent mod P。

 and they're also equivalent mod Q， they must also be equivalent mod PQ， which is n。

So first I'm going to do this massaging in mod P land， then I'll do it Mod Q land。

 Then I will show that it is true in modd N land。 So that's my proof strategy。 Hope you followed it。

 I take M to the ED。 I massage it to M mod P， then I do the same massaging mod Q。

 and then use the Chinese remainder theorem to finish up。So that's my outline of how the proof works。

 now let's do the massaging together。I start with M to the ED， and I'm working in modD P land first。

So the first thing I'll do is I'll take m to the ED and I'll rewrite it as m to the ED minus1 times M。

 This is just your basic exponent rules， I can rewrite m to the ED minus1 times M as M to the ED minus1 plus1 that gives me the original M to the ED back that's just exponent rules。

 nothing to do with mods in particular。

![](img/c5bd6c19117603987adb13b8ef54f315_2.png)

But what's great about this rewriting is I have this term ED minus1 here。

 and in the fact that I showed earlier， I also have ED minus1， that's great。

So instead of writing E minus-1， I can use the fact that I came up with earlier and say that actually E minus-1 is just some multiple of p minus-1 Note that if anything is a multiple of p minus-1 Q minus-1 it must also be a multiple of p minus-1。

 so I have just written that instead of E D minus-1。

 that is just some multiple of p minus-1 who knows what it is。

 So I have rewritten my original expression to now be M raised to some multiple of p minus-1 times m。

Now that works fine， but writing English in expressions is not very cool。

 so let's be more cool and write it as math。Another way to write some multiple of p minus1 is p minus1 time C for some arbitrary value C that's the same thing as some multiple of p minus1 so this is just me rewriting it to look more like actual math。

Now if I stare at this some more。What do I have here。

 I have some number M raised to the p minus1 power mod P。Wait a minute。

Fmatt's little theorem says if you take any number and you raise it to the p minus1 power mod p。

 what do you get， you get1。 So M to the p minus1 mod p。 that's just one。

 And if I take one and raise it to the C power Well1 to the anything power is still one。

 So this entire term collapses to just one。 And now I have one times M， which is just M。

 So we did it， we took M to the E D and we used all three of our facts and our theorems to massage it to become equivalent to just M mod P。

That's pretty cool。we're not done， we also need to show that this is true modD Q。

 that was our original strategy， we broke this up into MoDP and MoD Q lands。

So to show that this is true mod Q， we simply have to do all the same steps。

 but replacing all the P's with Qs。So the first step is to take M to the ED。

 rewrite it as m to the ED minus1 times M， that's just exponent rules。

 it works in modD Q land as well。Then we can write that E D minus1 is sum multiple of Q minus1。

 taking the P， replacing it with Q E D minus1 is also a multiple of Q minus1 as we showed earlier。

 and now we're working mod Q。So now we have M to the Q minus1 times some value C。

 and here I'm just rewriting some multiple of Q minus1 as Q minus1 times C because that's actual math and not English。

And again， I use the same for a mouses little theorem trick。

 any number to the Q minus1 power mod Q must be 1， so M to the Q minus1 mod Q must just be1 and1 to the C power is still11 times M is M It's the exact same reasoning。

 just take every single P， swap it with the Q and you got it。So that's it。 We're done。

 We showed that M to the E D is equal to M in mod P land and we showed that M to the E is equal to M in mod Q land。

 and because this fact is true in mod P land and it's also true in mod Q land It must also be true in mod P Q land。

 which is mod N land， so therefore we are done we have shown that if you encrypt something raise it to the E power mod N and then you decrypt it。

 raising it to the D power mod N， you get the original message M back。

 therefore encryption and decryption work as intended， and we are done。 That's it。

This is probably the most mathy slide in the entire class， so if you need to。

 you can pause and stare at it for as long as you need and hopefully we didn't fry your brains too much。

