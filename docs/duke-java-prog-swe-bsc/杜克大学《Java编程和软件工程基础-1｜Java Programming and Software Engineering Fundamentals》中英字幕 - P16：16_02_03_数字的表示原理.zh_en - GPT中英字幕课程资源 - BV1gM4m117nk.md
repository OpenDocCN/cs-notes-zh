# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P16：16_02_03_数字的表示原理.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/2b1327de8843b0d2fbd1e8fbddd85d58_0.png)

Hey， Drew， I remember in the last lesson you taught us that everything in the computer was represented with numbers。



![](img/2b1327de8843b0d2fbd1e8fbddd85d58_2.png)

Sure， Robert， this is a very important principle in computer science。

 as computers can only compute on numbers。I remember， and it was really cool。

 You showed us that we could represent letters and logic with numbers。

 but I have so much more on my computer than just words。 For example， look at all of these images。

 Surely they're not just numbers。 Actually， Robert， if we were to zoom in on one of these images。

 we would see that it's made of many tiny little dots called pixels。

 Each pixel is a single color and is numerically represented by a red component。

 a green component and a blue component。 Each of these values ranges from 0 to 255。

 where 0 means none of that color and 255 means as much of that color as possible。

 Once we've represented each pixel as a number， we can represent the entire image with thousands or millions of pixels。

 meaning thousands or millions of numbers。😊，Wow， that's really cool。But if they're just numbers。

 we could do math on them。 If I had magenta and I had green， could I add them together。 Sure。

 let's see how。We can do math on colors because they are just numbers to answer Robert's question。

 if we took magenta， which has a red value of 255， a green value of0 and a blue value of 255。

 and added it to green， which has a red value of0， a green value of 255， and a blue value of0。

 we would get a red value of 255， a green value of 255， and a blue value of 255。

 which would be white。

![](img/2b1327de8843b0d2fbd1e8fbddd85d58_4.png)

![](img/2b1327de8843b0d2fbd1e8fbddd85d58_5.png)

![](img/2b1327de8843b0d2fbd1e8fbddd85d58_6.png)

![](img/2b1327de8843b0d2fbd1e8fbddd85d58_7.png)

![](img/2b1327de8843b0d2fbd1e8fbddd85d58_8.png)

In fact， we can solve a lot of useful problems by doing math on the pixels that make up images。

 we could make an image lighter， darker， reder or bluer。

 or we could compress an image so that it takes less time to transfer across the internet while still looking the same to the human eye。

 for example， a JPEG file。If you've ever heard of a movie codec。

 this is software that encodes and des video doing a lot of math to determine the images that make up each frame of the video。

That's really neat。 So do you think that I could write an algorithm that would replace all of this all of one color in an image with a completely different image。

 Sure， in fact， that's what's happening to us right now since we're standing in front of a green screen。

 The video software is iterating over all of the pixels in our images and replacing green ones with a different image。

 We could， if we wanted to give this lesson in front of dinosaurs。



![](img/2b1327de8843b0d2fbd1e8fbddd85d58_10.png)

Or even in outer space。That's really amazing。 I'm going to go write the green screen algorithm for practice right now。

Produced by Duke University online atduke。edu。