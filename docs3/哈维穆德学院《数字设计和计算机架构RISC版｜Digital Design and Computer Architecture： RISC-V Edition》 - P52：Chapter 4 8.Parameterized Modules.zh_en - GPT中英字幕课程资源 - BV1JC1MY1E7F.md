# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P52：Chapter 4 8.Parameterized Modules.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Let let's talk about parameterized modules， parameterized modules help us reuse modules using the principle of regularity。



![](img/2e72a70d59898723fd3bb7dc6fd8e9ed_1.png)

And so here we have the parameterized module for two to one mus。

And it looks very similar to our prior two to one marks， but in the prior one。

 we had something like three clonee zero， yet a four。three co zero a four bit width。

on the data and the output。But now we have this this word or this。Name width。

And that's the parameter， so we defined the parameters with pound parameter width equals8。

 this is the name， this is the default value， so8 is the default value。

And now instead of using a number here， we use that parameter width minus1 to zero。Instead of 7 to 0。

For example， and same thing for the output。And then the function of the circuit looks the same as before。

So we could instantiate one of these， a MX2， this is the name of the module and our instance name。

 my MuX。And because we't any， we didn't specify what that parameter should be。

 it eases the default value， which is eight。So this is how we instantiate an eight bit。

Why the two to1 maxs。But if we want to instantiate a different width on the bus， for example。

12 bit bus， we could do this so mu2 and then we。But we specify what that parameter should be pound parentheses 12。

And then， you know， the。Inputs and outputs for that。ForFor that mux and instance's name。

Notice that this pound we've overloaded that symbol， so we used it before for delay。

 depending on the context， we're going to use it for either delay or for specifying a parameter value。



![](img/2e72a70d59898723fd3bb7dc6fd8e9ed_3.png)