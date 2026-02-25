# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P111：-Cryptography3, Video 11- Comparing Modes.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， before we go， we'll quickly compare the two modes that we just saw。

 So there's actually different tradeoffs and which one is better depends on what you're trying to optimize for。

 So maybe you want an algorithm that's really fast。 Well。

 then maybe CTtR is the one for you because you can parallelize in both directions。

 And remember in CBC mode， you could only paraize in the decryion direction。

 So maybe if you want the ability to run these encryptions really fast maybe CTR mode is the one you want。

 Maybe you're really paranoid instead， So if you're paranoid。

 maybe CBC is better because we saw that if IVs are reused。

 CBC only leaks the first few blocks being the same。

 and CTR leaks the entire thing the X of both of the messages。 So maybe if you're paranoid。

 you want to use cC because it fails a little bit more safely and it leaks less information when it fails compared to CTR mode。

 but that's a tradeoff you can make。 So it's not that one is better than the other。 It's more。

You get a choice of which one you want to use， depending on the things you're trying to optimize for。

