# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p85 085_03_05_分割与连接.zh_en -BV13E421M7FF_p85-

Split is a useful string method used to split a string into a list of multiple strings。

 Here we define a variable colors and store a string。😡，Since the string has commas in it。

 we can use the split method to split the string into a list of strings using a comma character as a separator。

Color's list will be a list of strings。The third string or color in the list will be green。

Conversely， join creates a single string from a list of multiple strings。

Here we join the list of strings using a separator defined as a comma character。

New colors will be a string containing all three colors。In a previous example。

 we tried to update a character in a string， this wouldn't work。

We can first convert the string to an actual list。But calling the split function with an empty string will throw an error。

 So this won't work。 Instead， use Python's built in list function to convert the string to a list。

 Now， we can update the third letter。 Then convert back to a string using join。😡。



![](img/3f46a8ed84e1834d08a5e3f9025e0621_1.png)

![](img/3f46a8ed84e1834d08a5e3f9025e0621_2.png)