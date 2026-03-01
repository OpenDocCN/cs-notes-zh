# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p110 21_02_01_引言_4.zh_en -BV11y411z7Dn_p110-

![](img/b63abf4e854a4ce80268016b173ab49f_0.png)

Let's take a look at logging and monitoring strategies and specifically push versus pull and also retention policies in the particular case of pushing and pulling well it depends on what's your end goal what's your end objective are you going to be deploying perhaps containers then maybe a pull strategy might make sense versus a push strategy and what is a pull strategy well that's when a monitoring system will go and fetch that information from endpoints or various different system so it will go and retrieve that information back to the monitoring system so for containers thats solid strategy and we'll take a look at why that is and why it makes sense for specifically for containers and then well move along as well for push strategies when you have systems that will be actually pushing that information over to a monitoring system and again we'll also see why why。

I that a good idea in what situations that might work well and how to actually roll out and implement one and then we'll take a look at retention policies and retention policies are useful because perhaps you don't want the granularity from five years ago。

 but you do want to compare data from five years ago and perhaps seasonality and you want to see you know what's the difference between the seasonality that we're having today versus two or three or five years ago and we'll explain what are those differences and when you may want to consider having less granularity and have some sort of like an average so that you can compare your data specifically when you're doing monitoring。

