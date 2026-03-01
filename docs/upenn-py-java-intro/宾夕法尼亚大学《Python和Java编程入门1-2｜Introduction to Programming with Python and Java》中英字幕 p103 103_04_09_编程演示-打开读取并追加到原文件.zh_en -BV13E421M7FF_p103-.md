# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p103 103_04_09_编程演示-打开读取并追加到原文件.zh_en -BV13E421M7FF_p103-

Now let's create an open Read append same file function that opens and reads a file and appends to that same file。



![](img/df85529d5d23e43731eaf055397a66da_1.png)

Let's go ahead and define the function。 to open， read， append。To same file for a given file。

Opens the given file and reads all lines as a list。Appends lines to same file。

We're going to read and write to the same file， so we need to open the file。In the R plus mode。

That's reading right。So open the file for reading and writing。And we're going to store that in F。

Read all lines into a list。Relines。I'll call that LST。Read all lines into a list。

Before appending back to the same file， let's make some changes to the list。So LST dot insert。

 we're going to insert a line into the list at index 0。

 So that's the beginning of the list or the top of the list。I'm going to insert a new line。

 just a blank line。 LST dot insert again at the top of the list。 Here is some new text。

And then let's add another new line。 So I'm putting blank lines between my new text and X0。Again。

 another new line。So here we're updating list before appending back to same file。Now。

 let's write the lines back to the file。 Give it the list。 And since we're in readr mode。

 this will append the lines。Back to same file。😔，And then let's close the file。Qu file。Close file。

Let's call our function from the main function。Go ahead and comment this out。Open， read。

 append same file。 Let's use news again。run that。Reading writing files。If I go to my news file。

 I can see that it actually appended。

![](img/df85529d5d23e43731eaf055397a66da_3.png)

The same lines to the same file。

![](img/df85529d5d23e43731eaf055397a66da_5.png)

Here is the new text I added in the middle。 If I run this again。I'll see that。

 It actually appended it again。

![](img/df85529d5d23e43731eaf055397a66da_7.png)

And in between， it added the here is some new text， and then the same lines。



![](img/df85529d5d23e43731eaf055397a66da_9.png)