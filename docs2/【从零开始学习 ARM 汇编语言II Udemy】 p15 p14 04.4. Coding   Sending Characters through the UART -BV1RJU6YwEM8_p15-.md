# 【从零开始学习 ARM 汇编语言II Udemy】 p15 p14 04.4. Coding   Sending Characters through the UART -BV1RJU6YwEM8_p15-

![](img/c7a34747b511647d7bcfff9d3319c533_0.png)

Hello， welcome back， so we are going to write a simple subroutine to help us transmit。



![](img/c7a34747b511647d7bcfff9d3319c533_2.png)

A character through the U art。Were simply going to pass the input to register r0 and this input is going to be sent through the UR。

 and we're going to spin， we're going to sort of create a spin loop if the transmit PIO is full because sometimes if you are transmitting the PIO getful you've got to wait for it to be。



![](img/c7a34747b511647d7bcfff9d3319c533_4.png)

![](img/c7a34747b511647d7bcfff9d3319c533_5.png)

![](img/c7a34747b511647d7bcfff9d3319c533_6.png)

Not fool before you can send if you catch the drift。 Okay， so I'm gonna come down here and。



![](img/c7a34747b511647d7bcfff9d3319c533_8.png)

I'll give the subbriine a name， you at。😔。

![](img/c7a34747b511647d7bcfff9d3319c533_10.png)

Undersco write， character， write chart， or call it。😔，And what are we going to do？😔，Sorry about that。

This is the return of this subroutine。😔。

![](img/c7a34747b511647d7bcfff9d3319c533_12.png)

BXLR。😔，Okay。So。😔，First of all， we've got to read the。😔，The U add status register。😔。



![](img/c7a34747b511647d7bcfff9d3319c533_14.png)

So I'm going to load that over here， I'm going to say load。😔，Lo R1。😔，Because。You add2 SR。😔。

St register， we already have that register， we created it。😔。



![](img/c7a34747b511647d7bcfff9d3319c533_16.png)

And once we floated into our， we're going to do。

![](img/c7a34747b511647d7bcfff9d3319c533_18.png)

We're going to rate it content and store it in register R2 by doing。Lord R2。

Load the content of the address found in Reg R1 into R2。O。Once we have that。

 we've got to check the flag， we use the end operator。😔，And operation， I should say and。😔，R2。

 which is the content in R2 with。😔，Our Tx， we created a constantantinoous Tx buffer flag。

 we've got to compare this。Like this。

![](img/c7a34747b511647d7bcfff9d3319c533_20.png)

Right， and then。😔，After performing this end operation， the result is going to be stored into R2。

 and we're going to compare using CP compare。

![](img/c7a34747b511647d7bcfff9d3319c533_22.png)

Tea Re， which is stored in R2 with0。

![](img/c7a34747b511647d7bcfff9d3319c533_24.png)

And then we're going to use the branch， if equal instruction， B， E Q， we want a branch to。



![](img/c7a34747b511647d7bcfff9d3319c533_26.png)

I'm going to create a label here called O loop， meaning output loop。



![](img/c7a34747b511647d7bcfff9d3319c533_28.png)

And I'll put a here or place a here， meaning just come back here if it's zero。😔，Right。

 so it would keep spinning here until it's not zero。Right。If it's not zero。

 then we want to load DM the data register。We first zero extended by before we load the data register。

 so I'm going to do UX TB。

![](img/c7a34747b511647d7bcfff9d3319c533_30.png)

R1。

![](img/c7a34747b511647d7bcfff9d3319c533_32.png)

I0。And then。😔，LDR， load R2。😔，Of course。

![](img/c7a34747b511647d7bcfff9d3319c533_34.png)

You add to data register。And then we write to the data register by doing install。R1。



![](img/c7a34747b511647d7bcfff9d3319c533_36.png)

Because when we do the zero extent。The result is going to be stored in R one。



![](img/c7a34747b511647d7bcfff9d3319c533_38.png)

Remember the character we want to send this in register r0 with zero extent and store it in R1。

 and now we take what is in R1 and then we' put in the data register so that it can be sent。



![](img/c7a34747b511647d7bcfff9d3319c533_40.png)

To the other U device， waiting to receive it。

![](img/c7a34747b511647d7bcfff9d3319c533_42.png)

Soll do R1 over here and then R2。And then PxLR。

![](img/c7a34747b511647d7bcfff9d3319c533_44.png)

Right。So this would allow us to be able to send characters。

 so I'll align over here and put it in directive。

![](img/c7a34747b511647d7bcfff9d3319c533_46.png)

Right， so this is our U at right character， so routineout。



![](img/c7a34747b511647d7bcfff9d3319c533_48.png)

U。So in the next lesson we would write the， the test code for this。

 we write we'll create a loop here to send some characters I'll see you in the next lesson have a nice。



![](img/c7a34747b511647d7bcfff9d3319c533_50.png)

![](img/c7a34747b511647d7bcfff9d3319c533_51.png)