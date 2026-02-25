# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P14：-Intro1, Video 14- Design in Security from the Start.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/886cc38c3bb1cc2a8cfe38a57279ee14_0.png)

No questions。Okay， this is the last one。 So design in security from the start。 When you make systems。

 it is very tempting to say I have this fancy new thing I want to build。

 I'm going to start writing code like there's no tomorrow。 you write 500 lines of code。

 the whole thing works and you release it and you're done。

 And then people start attacking it and they start attacking it and that's not good。

 So really important if you want to build a new system。

 It's important to think about security from the start。

 because what happens if you don't think about security from the start is you've built this beautiful。

 complicated system， but there's no security。 Any can attack it。 Now you have to go back and fix it。

 and the fixes could be really awkward。 You have to I have to insert security hack here and another security hack here and a little patch here and a little patch here。

 So your system is gonna become really gross and ugly and hard to use if you don't think about security from the start。

 because you have to go and fix all these little holes that happen。 So it's kind of like maintenance。

 instead of know like building。Something and then using it and then fixing it when it breaks。

 Maybe when you build it， you should build it securely so that it doesn't break to begin with。

So this is actually something that comes up a lot when we talk about the web and the networking units。

 Web and networking were actually not built with security from the start。

 So when people first built the Internet， it was。Like researchers building it。

 And so they didn't really think about security。 They were like。

 we're just going to use the Internet to exchange research papers。 Who cares about security。 Well。

 then turns out the Internet kind of became a thing。

 And so now we have to build security on the Internet。

 And you'll see that we have all these different patches that we learn about， And you'll be like。

 why is this code so gross。 Why am I learning about inserting these things that don't fit。 Well。

 the reason why is because the Internet was not designed in with security from the start。

 So a lot of the Internet design is really gross。 And if you want to avoid code that's really gross。

 you should think about security from the very start。

So you got to keep all the security principles in mind whenever you start writing code。



![](img/886cc38c3bb1cc2a8cfe38a57279ee14_2.png)

Okay， I'm almost done。 So give me like one minute summarize and then you can all go home like one minute one minute early。

 Okay so to summarize today， we talked about 10 or 11 one day all'll accounted security principles。

 So the security principles are philosophies that we got to think about when we are designing secure code and we'll see them pop up over and over again in this class。

 We talked about understanding your attacker， What resources do they have。

 what resources do they not have， Why are they trying to attack you。 We talked about human factors。

 we have to make our systems usable for humans。 if it's not usable。

 they are going to turn the security off because they don't know how to use it。

 security is economics， we got to think about cost benefit analyses。 We got to think about detection。

 and if we're not able to stop the attack， we should at least be able to detect and respond to it。

 We talked about layering multiple types of defenses。

 Those were the walls and we talked about defense and depth。 We talked about least privilege。

 make sure that you only grant the permissions that are needed， do not grant un。

cesary permissions in case the program is malicious。 talked about separation or responsibility。

 the two keys make sure that multiple people collude to exercise something that is sensitive。

 complete mediation。 don't let the cars drive around the gate。

 don't let people withdraw too much money。 make sure that all the access is monitored and cannot be bypassed in space or in time。

 Shannon's back， make sure the enemy assume the enemy knows the system。

 Don't rely on things being hard to find that does not count as security use fails safe defaults。

 make sure that your systems fail in a safe way。 there can be a balance between security， usability。

 And finally， design insecur from the start。 Think about all these things as you go through the class and build systems。

 Okay I guess I'll let you go two minutes early。 So have a good Wednesday。

 and we'll see you next time。