# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p54 54_04_06_最高温度：代码测试.zh_en -BV18U411U729_p54-

![](img/41750a8384509d2773f5e330b216a44c_0.png)

Let's take a quick look at how the data is organized on the file system and what an actual file looks like。

 so we have a data folder and inside of that data folder it's organized into years and then within each year we have a weather file for each day。

 so there's 365 or six depending on sleep here of those files for each of the years。



![](img/41750a8384509d2773f5e330b216a44c_2.png)

![](img/41750a8384509d2773f5e330b216a44c_3.png)

So that's how it looks on the file system and then here's how an individual file looks so this in this case I've chosen January 1t。

 2015 as the one that I'm going to test the info file that I'm going to test and you can see we've got the column information up top and we've got the column data for each of those and we have two files loaded up in a spreadsheet because CSV files are easily represented as spreadsheets so this is a nice way to visualize them。



![](img/41750a8384509d2773f5e330b216a44c_5.png)

The other method that I've already included in a CSV max class is test hottest in day so that we can test our code to make sure that it's right。

 First line in there creates a file resource already set to January 1，2015。

The second line calls our hottest hour in file method that we just wrote， passing it。

 the parser that we created for that particular data set。

And then that returns us the CSV record that is the largest one。

 And then we print out that hottest temperature and the time that it appeared at just to see when that was。

And that's going to give us a sense of whether or not a program is is correct。

 So I'm going to compile our code。

![](img/41750a8384509d2773f5e330b216a44c_7.png)

And I'm going to come over to the Blue Jay environment and create a new CSV Max object。

And then call my test hottest day， and it says the hottest temperature was 51。1 at 251 pm。

 and if I go over to my Ada file and I look。At the temperatures。

 I see that they are in the 20s and the 30s，50，51。1， act on to 50 back to the 40s。And 42。1。

 So indeed， the hottest temperature was 51。1， occurring at 251 PM。Let's also check。

The second of January， just to try it on a second data file to see。



![](img/41750a8384509d2773f5e330b216a44c_9.png)

How we're doing， so I'm going to come over and change。That from January 1 to January 2。



![](img/41750a8384509d2773f5e330b216a44c_11.png)

I'm going to recompile。I'm going to go ahead and create a new CSv max。And call test how to stay。

 this time it thinks it was 54 at 12，51 pm。

![](img/41750a8384509d2773f5e330b216a44c_13.png)

And again， if I come over and I look at my temperature。I'm in the 40s。I'm now in the 50s， 51。1。

I have 54s and then back down to the 40s。You'll notice that theres actually four times when it was recorded as being 54 degrees。

 and we've recorded the first time that that occurred， 12，51 pm。

 as opposed to the last time that that occurred 3，51 pm。

So now that I've tested it on two separate files and I've seen that it worked for those。

 I feel reasonably confident that my code is correct。

 but I encourage you to test it on more files and try it out on your own and see what you get。



![](img/41750a8384509d2773f5e330b216a44c_15.png)