# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p44 44_04_02_CSV数据：逗号分隔值.zh_en -BV18U411U729_p44-

![](img/07bc9870f24e12291d4c9b0b9b215db0_0.png)

Hello and welcome to this introduction to using Java to help find trends patterns and make conclusion about information found in data。



![](img/07bc9870f24e12291d4c9b0b9b215db0_2.png)

You see here two screenshots of spreadsheet programs that have been used to analyze data over many。

 many years on the left is a screenshot of a Google Doc spreadsheet that you can use today This program analyzes data and runs in the cloud it is accessible via a browser or mobile app on all kinds of devices all over the world on the right is a screenshot of VisicAC。

 the first spreadsheet program that launched in 1979 and ran only on Apple2 computers。



![](img/07bc9870f24e12291d4c9b0b9b215db0_4.png)

In general， spreadsheet programs work on data formatted in rows and columns， tabular data。

 you'll be able to write Java code to analyze such data as well。

Spreadsheets revolutionized so many industries and launched new ones by taking seconds to model what if scenarios that had previously taken days to perform the link here is to a podcast describing the development of Visicalc and the industries that were transformed by these programs。

Today， data that can be analyzed by software programs is often made publicly available through government and nonprofit websites。

Typically， data is produced in CSV files， files in which the different data values in each row are separated by comms。

 thus the name comma separated values。You're going to learn how to write Java programs to analyze data stored in CSV format。

Using spreadsheet software is a great way of finding patterns， information， trends。

 and visualizing data， but sometimes a spreadsheet program isn't enough to solve every problem easily。

There are many different spreadsheet programs， so a common format is useful。

 the CSV format makes it possible for data to be portable between different types of software used to analyze data Furthermore。

 you can write your own Java programs to analyze data using the CSV format。

Common formats often have standards， for example， the Internet protocol or IP standard determines the format for the packets that transport information across the internet the IETF or Internet engineering T force that made the IP standard also created a standard for CSV files。



![](img/07bc9870f24e12291d4c9b0b9b215db0_6.png)

Other groups have made different but related standards for formats used in different software programs。

In this lesson， you will learn how to use an open source software library， the Apache CSV parser。

 as you learn more about Java programming。This software library will allow you to solve problems that would be really difficult to solve using just a spreadsheet。

 Let's get started with this。