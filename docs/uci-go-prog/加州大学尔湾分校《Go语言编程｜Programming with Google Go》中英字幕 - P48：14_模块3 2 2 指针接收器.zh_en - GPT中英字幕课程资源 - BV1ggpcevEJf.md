# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P48：14_模块3 2 2 指针接收器.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 3， objectject orientation and go topic 2。2。0 receivers。



![](img/9e98e23af03e9c4c70319ffef1a81893_1.png)

So we've been talking about methods， defining methods for and associated with types with different receiver types。

So there are a few limitations of this process that we may need to overcome。

 So remember that this receiver type。Is implicitly passed。

 the receiver object is implicitly passed as an argument to the method。

 So even though it's not explicitly passed， it is implicitly passed。

 And remember that argument passing and go is copyied is passed by pass by value， copy call by value。

 So that means that you can't the method can't modify the data inside the receiver object。

So as an example， let's say we had some methodical offset x。

 and it should increase the x coordinate of a point。

 right we want to add some constant to the x coordinate of some point。So in our function main。

 we say ps p colon equals 0。3 comm 4， we make a point， now we say p that offset x。

 and we pass it5 is the value that we want to add to the x that won't change the x。

 it can't change the x coordinate。The reason why is because this offset X is being passed a copy of P1。

Not appointed to P1， a copy of P1。 And since it gets a copy of P1， it can change its copy。

 So it gets its own P1 do x copy。 It can change that from 3 to 8。

 But that goes away as soon as as soon as the main is as soon as the function is done executing。

 So it's offset its X is done executing that goes away because it's in its environment is gone。

 So what we want to do is to be able to change what we want in this case is's to be able to change the actual values inside P1。

 But you can't because methods they get the P1 the P1， the object is actually passed by value。

 Another problem with that is if the receiver is large。

 a lot of copying happens when you make a call。 So when you call by value and the object gets the receiver object is passed as an argument。

 the whole thing has to get pushed on gets copied onto the stack internally。

 And if it's a large receiver object， then that's a lot of copying。 So in this case。

 I got my type image。And this type is 100 by 100 array of ins。

 which is actually small for an image okay？So that's like 10，000 ins。

 so when I call this blur image which is some method that's associated with whose receiver type is this image when I call blur image。

 the I1， this image actually has to get past to the blur image to the blur image method and that's 10。

000 ins that you've got to copy onto the stack and that can take a long time and images actually are sort of worst case because they can get gigantic right 100 00 is not even big。

So that can waste a lot of time。So this is a problem。So what do you do Well。

 we do what we did before with with with method argument。

 with not even with method with regular functions， we can just pass instead of passing。

 calling by value， you can call by reference， so you explicitly pass the aer to the object rather than the object itself。

So the way you manage this is when you declare the function。Like we're seeing here。

 we declare offset X。

![](img/9e98e23af03e9c4c70319ffef1a81893_3.png)

See its receiver type to the left of the name of the function。 So in parent it says P star point。

 I say star point this time asterisks point right instead if I say p point。

 then I'm passing the point call by value。 But if I say p star point。

 then now P is a pointer to a point So now when I implicitly pass this p value to offset x is's going to pass a pointer to to the point object that to the point type that we're talking about。

 So now now inside the function， I say p do x equals p do x plus v。

 and that'll actually work because p do x is now since p is actually a pointer to this structure。

 P do x actually refers points to the actual x value in memory so you can actually modify it now because you're doing call by reference。

Thank you。