# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p42 12_02_06_使用diff比较输出.zh_en -BV1Kp42117vh_p42-

![](img/1271cda3254d61920a03f1a2122fc3a3_0.png)

In this video， we're going to show you a really useful Unix tool called Diff。

 which takes two files and compares them and tells you differences in them。

 You're going to use this in an upcoming assignment and in many other assignments to compare the output your program generates with the output that we've provided for you so that you can see if your output is right so in this upcoming programming assignment you're going to write a program which prints out some squares and take some command line arguments and print out a pattern of squares。

 So if I do Ls， I'm going to see that I have some files here called like ants 3582 Txt which has this little pattern of squares。

 and I've already done my assignment and compiled it into this program squares。

 So if I run squares with 3582 I want the same thing。

 So I can look at these they look pretty much right。Now for big， complicated things。

 it might be really tedious or complicated or hard to look at them and see if they're the same。

So what I'd like to do is redirect the output of my program to a file。

 so rather than printing it to a screen， it writes it to a file。

 you should have seen that in your readings about Unix。

 and I'm going to call it like my out do T X T。 So if I were to cat that file。

 I now see what's there。But if I were to run diF my out dot Txt with ants 3582。Diff says nothing。

 So that's good。 That means that we have exactly the same files。

 My output matches the expected output。 Everything is good。

But I've also made a version of this that's messed up called Squarequares Broken。So if I run that。

 so now it looks different。And if I di my out now with ants 3582。

 it's going to tell me that these are different now。

This output format from Dff may seem a little weird。

 What this means with less than s is these are lines that were in the first file that is this argument to diff。

 but not the second one。 And these were things that diff found in the second file， this one。

 That's why it's pointing that way。 and not that one。

We can get a slightly more readable version of this if I give it dash Y。

 whichll give me side by side output。 So it will show me that this and this are lined up。

 and this little line down the middle means that these are different。

 Now you might say but drew like。This looks like a blank line， and this looks like a blank line。

 They actually have different amounts of white space on them。

 We can tell diff to ignore white space and things like that。 If we read man diiff， remember。

 man tells us all the useful things about any command or library function。

 and we look for white space。There we go。 It's two words。

 We can see that there's a bunch of options for ignoring white space， including D W。

 which will ignore all white space。 So if they didn't want it to treat differences in spacing differently。

I can put D W。 That's a little dangerous because now it thinks that。This is the same as this。

 because they only differ by a space and thinks this line is in one file。

This line is this line is the same as this one。These lines， it thinks are the same line。

 but different， meaning it thinks the lines in both files but changed。

 And it thinks this line appears only in this file。

 So sometimes it interprets things a little bit weirdly， but it'll do a good job with that。

 We could use different white space options if we wanted。Based on what you need。

 So we might want to ignore only trailing white space， for example， or something like that。

 But in this case， we can look at these side by side。

 see what it thinks is different and figure out whether we've got the right output or not。



![](img/1271cda3254d61920a03f1a2122fc3a3_2.png)