# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P12：Chapter 1 11.Power Consumption of Digital Circuits.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Greetings， and welcome to the next exciting installment of digital design。

 The topic of this video is power consumption。😊。

![](img/fb0c29dfc6a0f6005b71d8f1179a16e3_1.png)

So you may remember from physics that power is the amount of energy consumed per unit time。

And power comes from two parts。 One is a dynamic power， and one is static。In electronics。

 the dynamic power comes from capacitors that are being charged and discharged as the circuit switch。

And the static power is caused from power that flows continuously， even when nothing is happening。

So let's first look at the dynamic power consumption。Remember that the。

Transistor gates look like capacitors。 They're formed from a metal gate。

separated by the insulating silicon dioxide from the conducting channel。And so。

 they have some capacitants。And the energy required to charge a capacitor from ground to VDD is C times the voltage square。

But suppose that this circuit is running at some frequency F。Meaning， F cycles per second。

And that the capacitor， on average， is charged alpha times per second。

Because discharging the capacitor from 1 to 0 is free。Than the power consumed。

Is the energy for each time that the capacitor charges that C V squared。

Times the number of times per second that it charges， which is alpha times F。

Half is the number of cycles and alpha is a fraction of the cycles where the transistor gets charged。

 or the capacitor gets charged。So the dynamic power is alpha Cv squared f。

Let's dive into activity factor a little bit more。Alpha is the activity factor。

 It's the fraction of cycles where the capacitor is charged。So， imagine。A system with a clock。

Running at some frequency， F。The clock rises and falls， once every cycle。

So if the period of the clock is TC。And the frequency is the reciprocal of the period。Venin。

Every period， the clock。Clocked capacitors charge once and discharge once。

 And so we have one charging event per cycle。 So the activity factor is one。On the other hand。

 consider we had some data signal that might be low。 It might be high。 and suppose on every cycle。

 it changes to the other。 So it is low， it rises if it was high it falls。

Now has some new value on the next cycle。 it changes again and so forth。Then on half the cycles。

 the capacitor is charged on the other half the cycle， it's discharged。

 So the activity factor is a half because we're only charging on every cycle。

Imagine we had truly random data。That data sometimes switches between0 and1。

 and sometimes it doesn't。So only on every other cycle。Do we see a switching event？

 Half of those switching events are charging， half are discharging。

 So only a quarter of the cycles do we charge the capacitor。 And so the activity factor is a quarter。

In a typical digital system， there is often some correlation between values on consecutive cycles。

 they might be more likely to stay the same。And in that case， the activity factor will be even lower。

And an activity factor of 10%。Is pretty common for digital logic。

Aes staticatic power consumption is consumed， even when no gates are switching。

This is caused by the quiescent supply current of current flowing from the power supply。

When nothing's happening， this is also known as leakage current。And in modern chips。

 the static power consumption is largely due to the fact that transistors have gotten so small that even when you're trying to turn them off。

 they don't turn off perfectly。 They might still have nanoamps or pico amps of leakage。

And when multiplied by billions of transistors on a chip。

 that still amounts to something pretty significant。

The static power consumption is the static current times the supply voltage。

It's helpful to review units at this point because chips tend to have tiny capacitances。

 small currents and very high frequencies。For example。

 the capacitances on a chip are often on the order of femmpto topeco ferrets。10 to the -15th。

 10 to the -12。So that's trillance or quadrillance of a ferret。

And the currents are also small microamps to nanoamps，10 of them -6 to 10 to the -9th。

Frequencies are quite high。 Mgahertz to gigahhertz。 That's a million to a billion cycles per second。

So imagine we had a mobile phone and you're feeling retrocho playing angry birds。

And we want to estimate the power consumption of the phone while you're playing。

So suppose the power supply voltage is 0。8 Vs。The capacitance on the chip that switching is。

 on average，5 nanofareds。The chip is。Blazing away at 2 GHz。The activity factor is about 10%。

And also that the static power consumption a static current is 100 millamps。

So the power consumption is the dynamic power plus the static power。

Dynamic power is the activity factor， times the capacitance。

Times the square of the supply voltage times the operating frequency， which gives us 。64 W。

The aesthetic power。Is the static current times the supply voltage。

Which is about an order magnitude smaller in this case。

 Usually a static power is quite a bit less than a dynamic。So the phone is drawing072 ws。Now。

 most of the time， your phone is just sitting idle in your pocket， not drawinging much dynamic power。

Suppose we wanted to know how long the battery would。The battery would last。

So suppose your phone had an 8 Wt hour battery。And we want to know the battery life。

We need to know the static power。That's the 100 millamps of static power consumption times 0。

8 V supply is 80 milliWts of static power。Then we can compute the battery life as the capacity of 8 W hours divided by the power consumption of 。

08 W gives 100 hours of battery life or four days if the phone was truly sitting idle。

 and we never touched it。

![](img/fb0c29dfc6a0f6005b71d8f1179a16e3_3.png)