# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P134：-Cryptography5, Video 5- PRNG Rollback Resistance.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Another useful property for PRNngs to have is something called rollback resistance。 Now。

 this property is actually different from the security properties that we've already talked about。

 It's separate， but it's an additional security property that's good to have。

 So think of it like a bonus。 if your PRNG has rollback resistance it's even better but it's a separate property from the computationally indistinguishable from random that we talked about earlier。

 So intuitively the rollback resistance property says that attackers cannot run the PRNG in reverse。

 and more formally， what that means is that if an attacker is able to compromise the internal PRNG state。

 they learn all of the internal variables and they learn what it's doing。 for example。

 by hacking into the machine， they are unable to run this PRNG in reverse and learn about the previous outputs that this PRNG generated。

 So rollback resistance is more about not running the PRNG in reverse。

It doesn't have to do with the security properties that we talked about earlier。

 but it is a nice bonus if you have it。 So one example where a rollback resistance might be useful。

 let's say that Alice uses a PRG to generate a secret key。 And then a week later。

 she uses the PRNG to generate some other stuff as well。 And later。

 mallllory is able to hack into the machine and learn what the PRG is doing。

 so she can see all the internal instance variables of this PRG object。

 if the PRNG is rollback resistant。 That means that mallllory is unable to figure out what previous outputs this PRG produced such as the secret key from last week。

 However， if this PRG is not rollback resistant。 That means that mallory is able to run this PRG in reverse and she can figure out what secret key Alice generated last week and all security is lost。

 So rollback resistance is a nice property to。But do be aware it is separate from the previous security properties that we talked about。

