# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P83：-083-Bugs Chap6 Video 13.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

This notion of bugs is a kind of unfortunate piece of historical terminology。



![](img/be99be7dd1ed25d339595843b1371086_1.png)

Because a bug maybe suggests that something just wandered in。



![](img/be99be7dd1ed25d339595843b1371086_3.png)

Here's a picture of the first bug found by Grace Hopper。



![](img/be99be7dd1ed25d339595843b1371086_5.png)

It had flown into relay number 70 panel F and gotten trapped there。

 This was the first actual case of a bug being found in a computer。

 of course this was back in the time when computers were huge in the size of rooms。



![](img/be99be7dd1ed25d339595843b1371086_7.png)

![](img/be99be7dd1ed25d339595843b1371086_8.png)

![](img/be99be7dd1ed25d339595843b1371086_9.png)

But the fact is， bugs don't just wander into our programs。



![](img/be99be7dd1ed25d339595843b1371086_11.png)

We put them there。So here's a better way of thinking about the terminology surrounding books。😡。



![](img/be99be7dd1ed25d339595843b1371086_13.png)

![](img/be99be7dd1ed25d339595843b1371086_14.png)

This comes from ITEE Standard 729。A fault is the result of human error in software。😡。



![](img/be99be7dd1ed25d339595843b1371086_16.png)

Maybe the most common kind of error like that is you or I make a coding mistake。😡。



![](img/be99be7dd1ed25d339595843b1371086_18.png)

Other ways in which those kinds of errors could occur is maybe you implement something that doesn't match the design for the software system。

 maybe the design doesn't match the requirements that the human users have for the software system。



![](img/be99be7dd1ed25d339595843b1371086_20.png)

![](img/be99be7dd1ed25d339595843b1371086_21.png)

![](img/be99be7dd1ed25d339595843b1371086_22.png)

In any case。Falultts might make themselves visible or not。



![](img/be99be7dd1ed25d339595843b1371086_24.png)

They might just remain latent and hidden。They might never appear to an end user。😡。



![](img/be99be7dd1ed25d339595843b1371086_26.png)

For example， maybe you write a line of code that has a fault in it， but。



![](img/be99be7dd1ed25d339595843b1371086_28.png)

No one ever manages to trigger that line of code， so the fault isn't expected。



![](img/be99be7dd1ed25d339595843b1371086_30.png)

![](img/be99be7dd1ed25d339595843b1371086_31.png)

A failure is a violation of a requirement。Which is to say a requirement that an end user has for how the system should behave。

😡。

![](img/be99be7dd1ed25d339595843b1371086_33.png)

![](img/be99be7dd1ed25d339595843b1371086_34.png)

So when a failure occurs， this becomes visible to the end user。

 they notice that something has gone wrong。😡。

![](img/be99be7dd1ed25d339595843b1371086_36.png)

![](img/be99be7dd1ed25d339595843b1371086_37.png)

Notice the chain of events here。There's a human error。😡。



![](img/be99be7dd1ed25d339595843b1371086_39.png)

That leads to a fault。And the fault might eventually lead to a failure。



![](img/be99be7dd1ed25d339595843b1371086_41.png)

This is a better way of thinking about errors and software systems than the word bug。



![](img/be99be7dd1ed25d339595843b1371086_43.png)

That being said， it's a widely established piece of terminology。

 I'm going to probably immediately slip back into using it。

 but it's good to know these terms nonetheless。😡。

![](img/be99be7dd1ed25d339595843b1371086_45.png)

![](img/be99be7dd1ed25d339595843b1371086_46.png)

![](img/be99be7dd1ed25d339595843b1371086_47.png)