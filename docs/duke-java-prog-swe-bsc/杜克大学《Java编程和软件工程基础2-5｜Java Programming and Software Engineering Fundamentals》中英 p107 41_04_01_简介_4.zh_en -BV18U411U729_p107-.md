# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p107 41_04_01_简介_4.zh_en -BV18U411U729_p107-

![](img/f12e8111580b9c60aaf73d31afe3988d_0.png)

Welcome back。 You have already written code to read a web server log file。

 parsing each line into a logatory object and creating an array list of them。

Now it is time for you to write some code to analyze the data you have read。

The first problem you're going to solve is finding out how many different people visited a website。



![](img/f12e8111580b9c60aaf73d31afe3988d_2.png)

You don't want to just look at how many elements there are in your array list。

 since some people may have visited your website multiple times。

 so you need some way to distinguish requests from different places。

You can use the IP addresses recorded in the log file to tell where the request came from。

Using the I address is not perfect， since you cannot distinguish between different people using the same computer。

But how many different IP addresses you see is a very good estimator for how many different people visited the site。

As you might recall from programming and the web for beginners。

An IP address is the address of a device on the Internet。

Whether that device is a traditional computer， a mobile phone， or something else。

So what you are going to need to do to solve this problem is take the array list that you have read the log entries into。

And find out how many distinct IP addresses are in it。 Have fun。😊。

