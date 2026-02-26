# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P110：-Cryptography3, Video 10- Dont Reuse IVs.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， minor terminology note because it is a little bit confusing for some reason。

 the two schemes have two different names for the random values。

 but both of them serve as random values that are different every single time。

 So for the purposes of this class will use them interchangeably。

 there are technically some very subtle differences between IVs and nonsenses。

 specifically one of them， you can predict ahead of time and it's okay and the other one you can't not the most important detail in this class。

 but just know that IVs and nonsenses are two different names for something very similar。

 It's a value that you can only use once。 you come up with a different one for every message that you encrypt。

 and you should never reuse them。 Sometimes you leak some information like the first few blocks being the same。

 Sometimes you leak a ton of information like in CTR mode where you leak the Xor of the two messages。

 but regardless of what you do don't reuse IVs。 It's a terrible idea and you'll lose all the security that you previously had。

So whether you call them IVs or Nos， don't reuse them。So if you do reuse IVs and nonsenses。

 then you have to think really hard。 So if you want another argument for why you don't want to reuse IVs and nonsenses。

 if you do choose to reuse them， you're going to be stuck for a long time thinking about what you leak。

 So we use CBC to show that IVuse leaks limited information and in CTR mode leaks the Xor of the two messages。

 if you reuse IVs， you now have to think really hard about specific attacks。

 So they are all these complicated attacks， you have to think about if Is get reused。

 And I think an even better approach is to not use IVs twice。

 And that way you never have to think about all these subtle attacks。 So if you don't reuse IVs。

 you get the security guarantee and you don't have to think is hard。

 and I like not having to think hard。 So I don't reuse IVs。

