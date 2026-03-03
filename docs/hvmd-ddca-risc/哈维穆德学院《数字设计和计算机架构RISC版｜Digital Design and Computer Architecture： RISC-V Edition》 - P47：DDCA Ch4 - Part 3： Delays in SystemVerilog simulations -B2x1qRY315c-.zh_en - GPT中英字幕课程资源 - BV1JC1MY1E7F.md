# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P47：DDCA Ch4 - Part 3： Delays in SystemVerilog simulations -B2x1qRY315c-.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

We can specify delays in our HDL， but this is super important delays are only for simulation。

We don't specify the delays of the hardware itself。

 but these delays are specified for simulation so we can see cause and effect between signals。



![](img/f7a6211068207c85459973f0b4b7df18_1.png)

So here's an example， system Bar module， I'm called example， and it has these delays。

 delays are indicated by a pound sign and then the delay amount。

 so in this case this would delay one tick or whatever is specified typically like a P secondcon of delay。

But this is distant in simulation， so again that Pcosecon really doesn't have any physical value。

 it just helps us see our simulation and cause and effect in the circuit。

So let's dive deeper into this so here we see the simulation and we're going to see some delays between the signals。

 let's look at that in more detail。So here we have our module as inputs A B and C and output Y。

 and then a bunch of internal nodes， A B， BB， which are A bar， B bar， CB， C bar。

 and internal nodes N1， and 2 and 3。And so here we see a sign。

 and then we add this pound one indicates after one clock tick。This is again， simulation only。

Asign after one clock tick of anything on the right side of the equals of the sign statement changing。

Then， change。These signals on the left side。 so that pound one says anytime A， B or C changes。

One clock tick later change the values on the left side。So we can see that at time t equals0， A。

 B and C transition to low。And then one clock tick later， we can see this on the bottom。 we have one。

C tick later。You can see that a bar， B bar and C bar。Transition to one to the inverse of A， B and C。

Okay， again， this is in simulation only。And now we can look at the next the next lines so we have。

These lines here where we have this pound two， so again。

 whenever anything on the right hand slide changes。Two clock cycles later or two clock cycles。

 two clock ticks later， the signal on the left side should change。And so here， for example。

A and B changed at times equals zero， so two clock ticks later。And Su， and。

And then three should change。And so we can see that， in fact。

And two and three changed because it was an and relationship， we had zero and something。

 right because A and transition to zero。And so。That you know。

 they're in an a relationship here is zero and something zero and something。

 so the simulation tool could evaluate that and say， well。

 it doesn't matter what those other things are。嗯。We're going to that would force our。

Our outputs are and2 and M three values to0。And then。

This this statement here assigning N1 depends on inputs A， B， A bar， B B， B bar， and C bar。

 and so that responds to clock ticks after those change。Which is at tick clock tick 3。Right， A bar。

 B bar， C bar chain there， two clock later。And one changes。Now we have。

The final output of our module should change four clock ticks after any of these change and one and two and three。

And so we can see that N1 changed。Here and four clock ticks later。

Why changed because it's an oral relationship and one changed to one， we have one or well stuff。

Doesn't matter what those other values are， one or anything is one， and so why evaluates。To one。

Four oclock ticks after and one changes。

![](img/f7a6211068207c85459973f0b4b7df18_3.png)