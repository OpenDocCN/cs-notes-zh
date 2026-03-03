# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P42：Chapter 3 15.Metastability.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Medicability occurs when the input changes within the aperture time。

 so when the dynamic discipline is violated。

![](img/40df75c3b2f3a5a82b04e0270b281fda_1.png)

So when does metaability occur， it occurs when we have asynchronous inputs， for example， user inputs。

 we don't have a clock that determines when we can press our keyboard， for example。

And it would be ridiculous anyway because we can't react within nanoseconds。So here's。

 someone pressing a button and that input。Could be going into flip flop。 And well， it could be fine。

 right， Here's the the after time of the flip flop。And it could change before right。

 this D input could change from 0 to 1 before the clock edge after the clock edge， no problem， case2。

But case three is a problem。 Now， do you happen to press that button right within that setup and whole time。

So now instead of getting right， if we draw our internal picture of our flip fl， L1 and L2。

And clock is zero。A one is sampling into that internal mode and one。And maybe。

It just got up to instead of getting up from know， from zero to one。

It only had time to get up to half。Instead。And so now we have a problem because what gets sampled when the clock goes from low to high now is。

Half instead of a one or a0， we get half or three quarters or something not this not one or zero。

 and again， remember those are voltages。And so meicability actually occurs whenever we have a bis stable device。

So with a flip flop， we have two stable states， the one where Q is1，q is zero。

But we also have a meta a stable state between them。

And if the flipflop lands on another stable state， it could stay there。

Or an undetermined amount of time。Could be a very long time， could be a short time。

But it stays there for a long time now we have instead of one volt or a zero volt on the output of our flip fl。

 we have half a volt or something。That's that's not one or0。 And the problem is。

 this driving commercialatci logic。And some of that combinational logic may interpret that as a one。

 and some may interpret it as a zero， and so now it's not going to function at all like we expected。

 and maybe this is controlling an X ray machine。And now the dosage isn't the right amount because our circuit malfunctioned。

Or maybe it's controlling the kid's toy and you turn on and off again and it works again。So。

But you know in the medical application or other applications， driving， et cetera。

This is a critical problem。So remember that a flip flop is built from an SR latch。And it's。

Internal circuitry， which in turn is built from cross coupled Nor gates。

And so when it's in the memory state。The SR inputs are both zero。And we get。

Zero or something turns out to be。No， Q。It's just Q inverted as Q bar。

And so these nargateates that have the zero connection basically get rid of those。

It's basically two inverters。They're cross coupled。Make we get Q coming over here。

 Q or zero is just Q convertedver to this Q bar。The Q coming down here is just the inversion of Q。7班。

And if we redraw these， we've redrawn these before。I like this。I have this。This output Q。

So have a queue。And speaking back to the input of the。Other。Inverter。And this。Output。

Sing back to the implant of。The top and ver。And then we can redraw it so we've redrawn it this way and this way and we can redraw it again。

Well， two inverters back to back is just a buffer。嗯。And so you know we have the output here。

 we have the input。Here。And we can draw what happens。 So well。

 just any buffer has some DC transfer characteristic and the input on the X axis。

 the output and the Y axis， this is the voltage。And a buffer。

 let's just draw this transfer characteristic without feedback。So if it gets a low input。

Inspect a low output。It's a high input。 We expect a high output。AndThere's some。

Transfer between those two。And so what happens when we have feedback。

 so this is essentially what we have。And we're in the memory mode has some value， and it has a one。

For example， well， this is a one output， it's going to feed back to the input。

It's going to come around and become the input。S。And in。Hi， yep， this still output high。

 just kind of stays there， right。No problem。But if it was zero， what happens there， will it see zero？

That becomes the。Coms around here and becomes the input。Great。

 we get an output a zero and it stays there。So what happens when it's neither of those。

 What if it's somewhere in between and what if it's like。no。😔，About a quarter or a third。Instead of。

Having a one or zero。Instead， we have now like a third。That's our output。Heres our output。Which。

 let's say， a third。It comeses out back and becomes the input。So now we go to our input。

 which is about here。A third， And it drives it to。Some other place， looks like maybe。4th or a。你觉得。

Output is driven here。😔，Instead of being a third no and down to my fifth。

And then it comes back around that fifth。Its the input， which is maybe here。😔。

And that drives it even further down， I don't know。20th or something。And so。

It does have feedback so it actually drives it down to the rail to zero and same thing would happen for driving it up to the rail。

If it were not one or zero， but it were close。It would drive it somewhere。

Some are close to the rails。So now let's see what happens when。It'sSomething like this。

And we have this feedback on here。😔，What happens if it's somewhere like where we have some line？

The slip of zero。Or it's exactly zero， exactly equal。And so let's see if that。No， maybe that。

This is one， this is zero me roots of like。0。4 point or something。Or even doesn't have be， but。

Let's say it's 0。6 or something。And so that output 0。6， that becomes the input。0。6 output still 0。6。

 So now it's here。 is it this meta stable point where it's like， oh， yeah， we're good， we're good，0。

6， y。That gives me that same thing as the output， okay， that becomes the input great。😊。

So now we're stuck here at this metable point or something very close to it。

Or guess it could also get stuck there。As abyss is our meta a stable point。So。

It becomes a metal stable signal if it has a result of one or zero。

And gets sent to the restling Circuit called Nationalal Log。

So this means that if the input changes at a random time and specifically during that afterture time there the probability that the output Q is metastable and that probability is stated like this。

 so the probability that the resolution time is greater than some time that you've waited。Is。

T0 over TC e the minus t over tau or t and tau our properties in the circuit。

 and T resolution is the time to resolve to a1 or a0。

I probably that time was greater than the time you actually waited。

C in that equation E to the minus T over tau。AndIts given by that equipment。So intuitively。

 TOta over TC is the probability of the input changes at bad time。So if you have some after time。

 so TO is related to the after time， if you have some cycle time。

And you have the after time around around that cycle time。

 while the probability that you're going to write the cycle time。

 you could also say that cycle time go from here to you know that next after time starting。

I'm around the clock edge。Well， that probability is basically TA over TC。

A probability that you're going to press it right in here versus， you know。

 sometimestime outside of the average time is just the the time， you know， the ratio T A over TC。

 which is。So TA is related to T n。So that's the probability that you're pressing it at a bad time in the first place。

And then this tau is that time constant， right， basically how fast。

It can either get driven up to a rail or if it's below that midpoint being driven down to the ground rail to the zero rail。

So if a flip fl samples and metatable input， if you wait long enough。

The output will have resolved to a one or zero just because of that feedback。



![](img/40df75c3b2f3a5a82b04e0270b281fda_3.png)

With high probability。Never 100% but with high probability。

