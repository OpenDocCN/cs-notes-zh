# 【基于LLVM和MLIR构建编译器】 p20 How to build a compiler with LLVM and MLIR - 20 Future Roadmap -BV1vi421Y7P1_p20-

![](img/93732049f2f15dec71f31f73a0d2ffd3_0.png)

Hey everyone。Good see you back and welcome to episode number 20 on how to build a compiler with LLVM and MLI。



![](img/93732049f2f15dec71f31f73a0d2ffd3_2.png)

嗯。Today episode is a little bit special because I'm not going to talk about anything technical like my original plan for this episode was to talk about tablegen。

 but a couple of weeks ago something happened to me that made me change my mind。



![](img/93732049f2f15dec71f31f73a0d2ffd3_4.png)

So far。In this video series we created a bare bone and really simple compiler with a minimum set of features that is capable of just in time compilation and ahead of time compilation。



![](img/93732049f2f15dec71f31f73a0d2ffd3_6.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_7.png)

It has all the major pieces and components in place， even though they have。

Pair bone features like minimal set features， but they're connected to each other。

 they're wired up and they work together just fine。



![](img/93732049f2f15dec71f31f73a0d2ffd3_9.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_10.png)

We talked about the LLVM MLIR， and like some of the concepts associated with them like past management。

 we created our own。

![](img/93732049f2f15dec71f31f73a0d2ffd3_12.png)

MLIR dialg， we get the chance to actually lower that to LLVMIR we talked about the GT engine。

 how it works in details， coregen and some of some other concepts around LLVM and MLIR。

 even though we didn't have the chance to talk about core fundamentals of a compiler like CFGs data flows or DAs sync to that sort。



![](img/93732049f2f15dec71f31f73a0d2ffd3_14.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_15.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_16.png)

But we talked about AS3s， semantic analyzers and really， really basic stuff。

So so far we covered a basic compiler and like our current design。

Is kind of a typical design for a static compiler。

![](img/93732049f2f15dec71f31f73a0d2ffd3_18.png)

Two weeks ago， actually I had an epiphany like while I was working on the。



![](img/93732049f2f15dec71f31f73a0d2ffd3_20.png)

During compiler， I realized that the current implementation， as I mentioned。

 is really suitable for a static compiler and not for a dynamic compiler。

 dynamic language like Serene。

![](img/93732049f2f15dec71f31f73a0d2ffd3_22.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_23.png)

So。While we like right now when the compiler puts， we start a new J engine engine on the side and we can communicate with it and use it to do things like micro expansions or anything dynamic that we want for the compiler。

 but that's not what I'm looking for， like I want something truly dynamic。



![](img/93732049f2f15dec71f31f73a0d2ffd3_25.png)

嗯。So。

![](img/93732049f2f15dec71f31f73a0d2ffd3_27.png)

Basically like it's been only two weeks， I didn't have enough time to refine my idea。

 but I looked into other implementations of lis and like commonly some other some variants of scheme and some other languages and I've decided to make some changes to our current design and the main and the most important change would be to。



![](img/93732049f2f15dec71f31f73a0d2ffd3_29.png)

kindind of build everything around the ging engine itself so in like the ging engine would be the very first thing that puts up and it like I'm going to use it to do everything like from parsing from co generation like OR generation target code generation runtime linking and everything basically。



![](img/93732049f2f15dec71f31f73a0d2ffd3_31.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_32.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_33.png)

It's going like this decision by itself is going to make drastic changes in our design。

 but so far whatever we discuss is going to still hold and if you're working on a static language or a static compiler。

 you don't have to change your design at all。

![](img/93732049f2f15dec71f31f73a0d2ffd3_35.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_36.png)

But if you're like me and you want to use a dynamic compiler， you want to create a dynamic compiler。

 you need to make the changes that I'm going to make as well。



![](img/93732049f2f15dec71f31f73a0d2ffd3_38.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_39.png)

So。With that being said， and since we're on episode 20， it's a round number。

 it's a good time to actually wrap up part one of this video series。

I hope it's been like this video series was fun and useful to you so far。



![](img/93732049f2f15dec71f31f73a0d2ffd3_41.png)

But for the part two， since I'm going to change the design， for the part two。

 we're going to talk about some of the core compiler fundamentals that we missed from part one。

 we have to skip over because just we wanted to have like a wired compiler like very basic to actually implement our ideas on。



![](img/93732049f2f15dec71f31f73a0d2ffd3_43.png)

So this is our chance to talk about them。And I'm going to make sure that we talk about the things that we want like we need for the future。



![](img/93732049f2f15dec71f31f73a0d2ffd3_45.png)

We're going to create some basic tools to actually help our tools。

And utilities to help us with our journey to learn more about LLVM and MLIR。

 we're going to sharpen our skills on LLVM and MLIR create some dialects， some pass managers。

 some passes， sorry， some optimization and things like that。



![](img/93732049f2f15dec71f31f73a0d2ffd3_47.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_48.png)

嗯。For the past two years， I've been a studying about type systems。

 especially the mathematics of type systems like they're pretty old in compared to like the computer science itself。



![](img/93732049f2f15dec71f31f73a0d2ffd3_50.png)

So I I read so many papers， books， something things like that around mathematics specifically around the type systems。

 So kind of I wanted to start a parallel video series to this to this one。

 So I get to actually talk about both at the same time。

 but I don't know whether that's a good idea or not。



![](img/93732049f2f15dec71f31f73a0d2ffd3_52.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_53.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_54.png)

I am still under fence about that， but。Nevertheless， part two。

 I hope like I find enough time and my study goes in the right direction so I get to talk about the mathematics subtype systems while I'm covering the part two。

 it's going to take a while but while I'm covering the part two。

 which is heavily focused on the compilers， the like the generic idea of general idea of compilers。

 I get enough time to actually finish the design and I start the ball rolling on the new design like the implementation of the new design so I have more material able to cover on part3 and focus more on the certainage on part three。



![](img/93732049f2f15dec71f31f73a0d2ffd3_56.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_57.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_58.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_59.png)

![](img/93732049f2f15dec71f31f73a0d2ffd3_60.png)

So that's a plan for the future。I hope like again I hope this video series was one and useful to you please do share your feedback with me like it can help me to improve my content quite a lot and if you're interested in working with me alongside me on Ser please reach out to me and see you on the part too。



![](img/93732049f2f15dec71f31f73a0d2ffd3_62.png)