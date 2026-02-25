# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P71：-MemSafety4, Video 12- Canary Analogy.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， here is our second memory safety mitigation that will make the attackers life harder。

 but not impossible。 So before we talk about this one。

 let's go back to the picture of putting together an attack。

 we earlier saw that nonexecutable pages targets step 5。

 It makes it harder to execute shell code because the attacker can no longer execute shell code that they wrote themselves they have to use existing code which they have to chain together or do other clever tricks with in this defense。

 we are going to target step 3。 We're gonna make it harder to overwrite the RP with the address of shell code using a defense called stack canaries So before we talk about what this defense is and how it works。

 let me tell you a quick story about where the name of stack canary even comes from。

 So back in the really old days， I don't know if they still do this。

 but legend has it that in the old days， theyd be these miners and they'd work in these caves。

 and it's really dangerous because if any toxic gas bill。



![](img/3dfcb5a143e5e1cc9bbd78976941f567_1.png)

![](img/3dfcb5a143e5e1cc9bbd78976941f567_2.png)

They're all trapped in this enclosed cave， and they could all breathe in this toxic gas。

 and that's really dangerous。 So what the miners would do is they would bring in a canary。

 And a canary is a small little bird makes a lot of noise。

 And so what happens is if toxic gas starts to build up the canary is going to start chirping and complaining。

 and it might even fall over dead。 And if the miners are working and they noticed that the canary has fallen over Well then that's a sign that all the miners need to pack up and leave because there was a toxic gas leak。

 So what happened in this story is this canary。 We didn't really expect it to survive the whole story as kind of morbid。

 but it's true。 The canary was really sacrificial。 We brought it into the mine not because we wanted it to survive。

 but because we wanted it to be a warning for all the other miners to leave。

 So this poor canary fell over and died。 But by doing so。

 it gave all the other miners an alert that something has gotten wrong and all。

Mers are able to evacuate。 So all of their lives got saved。 This is a pretty depressing story。

 But the takeaway is we're going to try to do the same thing on the stack and we will not harm animals in the process。

 So what we will do is we're going to try to use the same idea of a canary。

 which is a sacrificial value。 we don't really care if this survives or not。

 but we want it to be in the cave with us so that if it falls over dead。

 it's a signal for the actually valuable things like our own secret data to。Be saved， so。For example。

 and this will make more sense once we show you the actual canary and how it works。

 but basically our canary value will be very similar to the canary animal。 It will not be meaningful。

 We don't care what the value is。 the code's not going to use it， but if the canary falls over dead。

 that's a warning sign that our code has been messed with and it's going to give the code a chance to crash and alert the user that something wrong has happened。

 So that's the story it's a little bit depressing， but hopefully when we talk about the real canary。

 things will be happier。