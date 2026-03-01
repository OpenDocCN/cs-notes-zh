# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p111 05_01_03_导入与读取文件-使用CSV模块.zh_en -BV13E421M7FF_p111-

Python has lots of built in functionality for reading and writing files。Before reading a file。

 you have to open a file。You can use the builtt in open function。



![](img/ef79cd633b2f1d2973651c5e5c0733ca_1.png)

The format is as follows。Call open with a given file name and access mode。

 F name is the name of the file， including the file path。

 and access mode is an optional parameter indicating the mode in which the file is opened。

 For example， read or write or append。 The default mode is read or R。For example。

 here we open a CSV file in my file path in Read mode。

 This would create a file object for the My file CSV file in my file path， in read mode。



![](img/ef79cd633b2f1d2973651c5e5c0733ca_3.png)

![](img/ef79cd633b2f1d2973651c5e5c0733ca_4.png)

![](img/ef79cd633b2f1d2973651c5e5c0733ca_5.png)

When opening a file， the access modes are as follows。 R opens a file for reading only。

 This is the default mode。 W opens a file for writing only。

 this overwrites the file if it exists and creates a new file if it does not。

 A opens a file for app pending with the cursor at the end of the file and creates a new file if it does not exist。

 and R plus opens a file for both reading and writing。😡。



![](img/ef79cd633b2f1d2973651c5e5c0733ca_7.png)

The CSV module implements classes to read and write CSV files or files with comma separated values。

It provides a useful diict reader class which reads a CSV file and maps the information into a diict object。

 which is a Python dictionary。First， we import the CSV module。

Then we call the open function with a given file in read mode。Then we call CSV。

 died readerer with the given file object and that returns a reader object which we can use to read the data in the file。



![](img/ef79cd633b2f1d2973651c5e5c0733ca_9.png)

After reading a file， you should close the file。You can use the builtt and Close function。

This flushes any unwritten information and closes the file object。 After it's closed。

 there is no more reading or writing that can be done。

It's good practice to use the close function to close a file。For example。

 here we import the CSV module。Then we open a given file and read mode。

Read the file object into a reader。Do some other stuff and then call the close function to close the file object。



![](img/ef79cd633b2f1d2973651c5e5c0733ca_11.png)

You can also use the width statement to open a file and close it all at once。

Here we import the CSV module。Then we use the width keyword before calling open with a given file in read mode。

 and then we store that in a variable CSV file。Inside of the enclosed code block。

 we call CSV do dit reader with the given CV file variable。 Read the file into the reader variable。



![](img/ef79cd633b2f1d2973651c5e5c0733ca_13.png)

Do some other stuff。 And then we're done here。 The with statement will take care of closing the file for you。



![](img/ef79cd633b2f1d2973651c5e5c0733ca_15.png)