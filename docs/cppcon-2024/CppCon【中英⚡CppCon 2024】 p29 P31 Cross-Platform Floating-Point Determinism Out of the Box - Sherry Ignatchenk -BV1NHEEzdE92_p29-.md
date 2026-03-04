# CppCon【中英⚡CppCon 2024】 p29 P31 Cross-Platform Floating-Point Determinism Out of the Box - Sherry Ignatchenk -BV1NHEEzdE92_p29-

From game development to high frequency trading， thanks to QDC， the QuaDevelop C。Okay。

 my name is Sherry and today I will be speaking about cross platform floating point。



![](img/bece6fecb6936a273ad59aa7cd89476e_1.png)

Those of you who know me already。

![](img/bece6fecb6936a273ad59aa7cd89476e_3.png)

Probably knows that。

![](img/bece6fecb6936a273ad59aa7cd89476e_5.png)

The term is in general is。A subject I'm genuinely obsessed about。So。

 and when speaking about the terrorism。There actually is I see it as a pretty level field with two big holes in this field。

😊，One of the holes is multi sing。Achieving the was multi rating is。Extremely difficult。

But fortunately， we won't need to discuss it today and as be in determinism is cross from floatingian point determinism。

 which is exactly the subject。

![](img/bece6fecb6936a273ad59aa7cd89476e_7.png)

Of this talk of mine。啊。First of all， I should say that this research is actually。

Not only mine that there were seven people involved in it， there was a lot of work。

And all of us come from the company。Which is nicely named。Six impossible things before breakfast。

And I see that the company name is quite relevant here。

Because achieving cross platform floating and point determinism。Was a deemed to be impossible。

At least for 15， 20 years。So we see it as one of those。S impossible things。

We are claiming in our name， that achievement it is one of those six impossible since we are claiming in our name。

Okay。Here' is the talk outline。 First， we will discuss。What is the Terminism？And why it is important。

Second， there will be some quotes from people who tried。

To achieve crossper from floating points determinism in the past。

Then I will describe our first attempt， which actually was a failure。But we learned synco3 out of it。

 so it was useful。Then we will discuss our new approach in working versions。

 actually there are six of them。Then I will come to the question of performance。あ。

Determinism doesn't come for free。 It comes for a price。 So performance is important。

And then we jump to conclusions and to our C plus plus standard proposal with regards to。

Floion point， which surprisingly still has chances to get into C+ 26。O。First。

 let's define what we are speaking about。Actually， the termminism has several possible definitions。😊。

And。We will be concentrated on three of them at this time。

So the first definition is that we tell that program is deterministic if given exactly the same inputs。

 it the same the very same excutable behaves exactly the same。😊，This one is fairly easy to achieve。

Saving for things such as initialized variables and multi trading。The second definition of。

Determinism is that executables which are built from the very same source code。

 but built for different platforms， behave exactly the same given the same inputs。

This one is possible for。Uual arithmetics， eventually it's possible for pretty machineinism besides floating point。

 for floating point， it becomes。A very difficult task。

 which as far as I know nobody really solve before us。

The third definition of deter is actually even more important。

It means that the same function behaves exactly the same way。In different contexts。And apparently。

 especially for Loian points。 and given that we are living in in wineine or road。

 it doesn't necessarily stand。The same as the very same floating point function can return a different results if it's called from two different places in the code。

 and this is a big problem actually。So why those determinisms according to different definitions are so important。

Well， the first one， which is the same executable determinism。

 is important because we want to preserve general inceanity。

And also because we want to have the stability。If when HR around we produce different results。

 it's very difficult to make a reasonable test for it。The second definition。

 which is cross platform determinism， is extremely important for distributed simulations。

Including online games， especially Rs。Just yesterday。There was。トク。By Eds， who is present here。

Who described his own。Game which was using， which was relying on the determinism to reduce amount of traffic which goes between server and clients。

And these ideas indeed very solid， however， for it to work his in his context。

 he had to rewrite all his simulation to fixed point。Because otherwise。

 he won't be able to achieve determinism across different platforms， which was his。

That's a definition。And actually there's a suit definition， determinism in different contexts。😊。

Is even more important because it goes to algorithmism brightness and avoiding the terrific consols。

Actually， we learned about it as a hard way。At some point。We had。

An algorithm which was working which was operating into this space。

 and we are ran into a situation when there is a line and there is a point near the line and near means that sometimes the point fell within。

Within around in margin。 So it was really gross。And for the purposes of algorithm。

 it was it wasn't important where the line， the point was on the left side on the line。Os。

Or whether it was on the right side of the line。

![](img/bece6fecb6936a273ad59aa7cd89476e_9.png)

What。Our algorithmism did not like is when it appeared on the both sides of the line at the same time。

At this point， algorithms started to fell apart。And it happened exactly because we called the same inline function from two different contexts。

 and it was providing subly different results in different contexts in spite of arguments being exactly the same。

And more generally。More， generally， we found that。There are our Christmas out there。

 which are solid mathematicalally。😊，Which has solid when we consider this them as fixed point algorithms。

 but which fall apart when we consider them from floatingian point of view。

And this is fairly obvious。 if you think about it。It is， because。In floating point world。

 unlike in mathematics and unlike in a fixed point。There is no such a thing as。

Asivity with regards to addition。Whenever we are making additions in floating Pointfield。

 there is an and implicit rounding after each addition。

And the surround in operation is not linear compared to the is not linear with regards to addition itself。

 so order of additions really matters in fluid in point view。

 and it is not the case in the mathematics and because not the case in V speaks point。

Most of the time， such algorithms can be rewritten。

To make it solid even in case of floating and point， but to make them so that we need to。

