# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P35：L35- Proving that divisibility is transitive - ShowMeAI - BV1Sq4y1K7tZ

![](img/d7f0fc6273eb823733d28b9ab71d68bb_0.png)

In this video， we're going to investigate the idea of divisibility。

 and then we're going to use that concept to prove various claims about divisibility。

 and it's going to help develop some of our proof skills。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_2.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_3.png)

So first of all， let's sort of get an intuitive idea of what's going on with divisibility。

 Let me take a number with lots of factors to it。 How about the number 12。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_5.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_6.png)

Then one thing I might say is this 12 is divisible。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_8.png)

By well， 12 is divisible by all kinds of things， I have about three。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_10.png)

En。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_12.png)

What I'm sort of meaning here is that if I take 12。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_14.png)

And I divide it by three， then I get the number four， and that four is inside of the integers。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_16.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_17.png)

Or if I want to sort of rearrange it， I can say that 12 is equal to three multiplied by four where this four is again something that's inside of the integers that's sort of what I mean by divisibility。

😡。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_19.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_20.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_21.png)

Or is a different example， I could say that 12。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_23.png)

Is not divisible。By5 okay and what I mean by that is that if I take 12 divided by 5， well。

 if I put that into my calculator here， this is going to be like some weird decimal。

 So for sure it's not going to be inside of the integer。 So I write not inside of the integers。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_25.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_26.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_27.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_28.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_29.png)

Or other way to say it is that。My 12 is not equal to five times some value P where P here is an element。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_31.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_32.png)

Of the integers。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_34.png)

Okay， so that's sort of my informal sense of divisibility。

 you have a number and you divide it out by something and then when you divide that out by something。

 it's either going to be an integer or it's not and that tells whether it's divisible or whether it's not。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_36.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_37.png)

I actually really like the bottom way of writing it。

 I like saying that 12 is divisible by three means I can write 12 as three times four Now let's try to be a bit more precise about this。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_39.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_40.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_41.png)

Because we're dealing with attempts to make all of our concepts that even if we've seen them for many years。

 we want to make them as precise as possible。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_43.png)

Note that there is an existential claim here when I say 12 is divisal by3。

 what I means is that there exists in integer4， there exists an integer4 that has this property that 12 is equal to three times 4 or alternatively 12 divided by 3 is equal to 4。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_45.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_46.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_47.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_48.png)

So I'm really claiming an existential， there exists this other integer that has this particular property。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_50.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_51.png)

So my formal definition is I've got a pair of numbers like 12 and three。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_53.png)

As long as that second one was not zero， I had to sort of put that in my condition。

 I'm beginning with integer， we're not talking about rationals and that the divisor here is not zero。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_55.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_56.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_57.png)

Then I'm going to mean this claim， which is n iss divisible by D， if I can find some other number。

 it's like the four I found before， if I can find some other number that is an integer and has the property that your end can be written as the divisor times that new integer。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_59.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_60.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_61.png)

And know carefully this little bit of notation， that's really what I'm defining this says D divides n and there's a whole bunch of different ways that we can say this in English the D divides n is the way that I like or you can do n is divisible by D or n as a multiple of D or D is a factor of n or D is a divisor of n there's a whole bunch of different possible ways that you might be familiar with it。

 but what I want you to be really clear about is that。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_63.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_64.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_65.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_66.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_67.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_68.png)

The order of the D in the N really matters， and depending on which way you phrase it。

 you might have different orders。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_70.png)

So when I use this symbol， which is my shorthand， I read it as D divides n and I mean it' something along the lines of three divides 12。

 so the big one is your n and goes on the right and the small one is your D and goes on the left that's what I mean when3 divides n。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_72.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_73.png)

But the way I just phrased it before was it was the big one came first， the 12 is Divisionisal ID。

 or the 12 is a multiple of three。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_75.png)

Or I can flip it back around again and say that my three is a factor of the 12 there's all these different ways to say it and the order matters。

 so just try to keep those clear in your head。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_77.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_78.png)

All right， so now I have a new theorem to prove it says。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_80.png)

If a is divisible by B。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_82.png)

And B is divisible by C。Then the A is divisible by C as well， something like that。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_84.png)

And if you want to， you could formally rewrite this using our notation。

 I'll say this is saying that my B divides A， my C divides B and so forth， my C divides A。

 but I don't know I kind of actually personally like it written in a slightly longer form。

 I don't mind whether you use a shorthand or not， and then we know that any point if we need to。

 we can bring out that formal definition that we are just talking about what does it mean to say that one thing is divisible by another。

😡。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_86.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_87.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_88.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_89.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_90.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_91.png)

And if I'm going to sort of think about how this is working， okay。

 I know that four is a divisor or four divides that number 12。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_93.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_94.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_95.png)

And then I also know that two divides the number four。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_97.png)

And indeed， it's for sure the case that two divides the number 12。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_99.png)

So I've only just done one example here， but I just want to illustrate that， yes。

 my intuition is indeed matched for this example。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_101.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_102.png)

All right， so let's go and try to write out。Our proof。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_104.png)

First step is to state what our assumptions are。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_106.png)

So let us have it be the case， so I'm going to suppose or let。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_108.png)

That indeed， it is true that B divides a。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_110.png)

And that C divides B。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_112.png)

So that's the translation of my statement， my if is one thing and another， right。

 my if is a conjunction， it's an and statement of two things that I've written down here in their shorthand。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_114.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_115.png)

Now our next step is going to be to take these shorthands and apply for us that formal definition that we had。

 namely， we need to say that there exists this other number。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_117.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_118.png)

Such that what we have can be written in this particular way。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_120.png)

Okay， so let's give some names for them。 How about S and T， those can be my other numbers。

 So in other words， for both of these two different components of my hypothesis。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_122.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_123.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_124.png)

I have to go and make an existential claim about some other number and maybe we'll call them S and T。

 So in other words， I am claiming that there exists an S and a T。😡。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_126.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_127.png)

That have the nice property such that your A is equal to S times B。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_129.png)

And that your B is equal to T times C。So that's my claim。So I think I've stated my assumptions。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_131.png)

And then I have applied that definition to my assumptions and rewritten them in this way。

 maybe the only final thing I'll note is that the S&T。

 those are both need to be integers if I want to do it precisely。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_133.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_134.png)

All right， so I've written down my assumptions and I've used my formal definitions to translate them。

 and now I need to do some sort of manipulations that get me to my conclusion。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_136.png)

However， I don't actually think I've done quite enough of the plane around that I'm quite convinced as to what I'm supposed to do next。

 so maybe I'm going to go off on the side for a little bit， it's not part of my formal proof。

 but I'm going just do some computations see if I can figure out what's going on here because what I want to conclude。

😡。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_138.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_139.png)

![](img/d7f0fc6273eb823733d28b9ab71d68bb_140.png)

Is that A is divisible by C， so really what I want to get。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_142.png)

At some point is I want to get that my A is equal to what I've used up ST， let's go up to U here。

 I want to have that my A is equal to C times u for U being some other integer。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_144.png)

So that's kind of what I'm hoping for and then if I look at what I have。

 so that's what I want to have， but what I do know is that my a what do I know about a oh here it's an expression about A A is equal to S times B。

 so a is equal to S times B。😡。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_146.png)

And then I know something about the B here， right I know that the B is equal to the TC。

 so B is equal to TC， and I have to put my s out the front here， So a is therefore equal to S TC。

 In other words， it's equal to C times some other stuff and oh look at that that other stuff S times TS T were both integers。

 that's gonna to be an integer as well。😡。

![](img/d7f0fc6273eb823733d28b9ab71d68bb_148.png)

Okay， so I think I've got enough here my manipulation that I can continue my proof。

 maybe I'll leave the purple there for a moment to look at if I need to。

So now I'm going to continue my proof and I'm going to say then， allright。

 I want to get that my A is equal to this。 So let's do that manipulation。

 Then the A is equal to the S B。 It's what I just had。Which is equal to the S times。TC。

 that was me substituteutd in right there。Which is the same thing as saying C times ST。

 I've just rearranged the order， these are numbers， I'm allowed to do that rearranging of order。

In other words， what I claimed is that a is equal to C times S。

 where the S is for sure inside of the integers。 It is something as label as S。

 but it's an integer because both an S individually were and the product of two integers is again。

 an integer。 So what can I can claim。😡，Therefore， my final conclusion is that C doesnt D divide A。

 and that was what I wanted to get over here， A is divisible by C， C divide A means the same thing。

And then I got rid of my scrap work that I had up here that was for me it was part of my computation。

 wasn part of my proof， I've reproduced it in the right way down here in my proof。

 and I have this really nice fact that you can chain up divisibility in this way。

 and this serumem is sometimes referred to as transitivity of divisibility。😡。



![](img/d7f0fc6273eb823733d28b9ab71d68bb_150.png)