# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P133：-Cryptography5, Video 4- PRNG Security.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

One thought exercise we can do now is think about PRNGs and whether they can be truly random。

 Can they be truly random like the lava lamps or any of those physical sources that we talked about and unfortunately the answer is no。

 and here's the proof that shows why。 So consider using a PRNG passing an S bits of initial seed。

 that's the true randomness that you pass in。 And because the PRNG is deterministic。

 Each possible S bit seed leads to the same sequence of outputs。 So if you pass in one S bit seed。

 you get one sequence of outputs， you pass in another S bit seed。

 you get another sequence of outputs and each seed maps to exactly one output sequence。

 that's what it means to be deterministic。 And because there are S bits of your seed。

 that means there are two to the S possible input see and for each input seed you get。

One output sequence， because it's deterministic。 So therefore。

 there are only two to the S possible output sequences that you can ever get from this PR and G that you've only seeed with S bits of input。

Now consider using this PRNG with your S bits of input to generate two S bits of output。

 so you want to generate output that's twice as long as the input well because again there are only two to the S inputs and each one generates a unique output sequence。

 that means there are only two to the S possible output sequences of length2 S that this PRNG can generate。

😡，But if this PRNG were truly random， it should be able to generate any length 2 S sequence and how many length 2 S sequences are there。

 Well， if the sequence is2 S bits and every bit can be a0 or a1。

 there should be2 to the two S possible different output sequences。 So in summary。

 if this PRNG were truly random， we should be able to generate any of the two to the two S possible output sequences。

 but because it's deterministic and we only fed in S bits of seed。

 we are only able to generate 2 to the S possible output sequences。 So as a result。

 this PRNG is not truly random， it is not able to generate all of the possible output sequences。

 it is only able to generate a small subset of them。So even though the PRNG is not truly random。

 we can say that it is as good as random for our purposes。 More formally。

 we define the PRNG to be secure。 if it is computationally indistinguishable from random。

 That's a term we've already used previously but to remind you what it means this means that if we give the attacker two sequences。

 one of them is truly random， we got it by flipping coins。

 and the other one was outputted from a secure PRG where the attacker doesn't know the initial seed that we provided。

 the attacker should not be able to tell which one is which which of these two sequences was random。

 which of these two came from the PRG the attacker doesn't know and we threw in the usual caveats。

 for example， the probability of guessing has to be greater than one half plus negligible for the attacker to win and we limit the attacker to reasonable runtime for example。

 polynomial time runtimes。of like some of the security games that we've already seen。

 but here they are distinguishing between PRNGs and truly random。

 and because they cannot distinguish， we say that the output of the PRNG is basically random for all intents and purposes。

An equivalent definition。 and you can show mathematically that these two are the same。

 You can say that the attacker who sees output of the PRNG。

 but doesn't know the internal state and doesn't know the initial seed is not able to predict future output of the PRNG with any nonnegligible probability。

 So if I give the attacker some PRNG output without showing them the input and I say this is the PRNG output。

 if I were to call generate more times what comes next if the attacker is able to predict what comes next。

 this is not a secure PRNG。 if the attacker is unable to predict what comes next。

 we say this PRNG is secure。 The bits that are about to be generated are as good as random from the perspective of the attacker。

 So that's how you define the security of a PRNG。Now don't forget that the security of your PRNG is only as good as your initial seed。

 If you pass in a bad lowenttropy initial seed to a secure PRNG the output is still going to be predictable so this is an example from a casino where suspicious players would go in they would put their hand over the slot machine lever wait for a very specific time and then pull the lever suddenly and a bunch of money would fall out and it seems like what was happening here was that the slot machines were being seeded using the current time for their PRNGs。

 So what that meant is that all that the attackers had to do was to calculate the PRNG for different times and find the time that generates a winning PRNG output and when that time came well they would pull the lever and they would win all the money and this casino probably went broke so this is an example of a secure PRNG being used in an insecure way and the result is still bad。

So don't forget， even if your PRMG is secure， you still have to pass in seeds with high entropy。

And there's other examples of PRNG bugs again coming from insufficient entropy。

 I won't read this one out loud， but it's another case where there's not enough entropy so the attacker is able to brute force and try out all the initial seeds and eventually guess your secret key。

 so don't forget， use high sources of entropy with your PRNGs。

