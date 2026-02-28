# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p127 07_02_08_总结_1.zh_en -BV18U411U729_p127-

![](img/3487291ea330a94d8b8eefe69860c72e_0.png)

Hi， you've seen code and concepts for developing and using classes to search earthquake data。



![](img/3487291ea330a94d8b8eefe69860c72e_2.png)

Often， classes use other classes with HA and uses relationships。

This means storing objects in instance variables or as local variables in methods。

 these are standard object orient design concepts that apply across all object oriented languages。

 not just Java。

![](img/3487291ea330a94d8b8eefe69860c72e_4.png)

In our examples， we processed streaming data data that might change each time the program runs。

 We treated parsing as a black box， relying on Java libraries to parse XML formatted data。

We developed the XML parser relying on standard Java APIs。

 and you developed earthquake code relying on APIs for standard Java libraries。

 as well as those we provided。To help with debugging。

 we also use data store locally rather than streamed。 This allowed for smaller。

 repeatable debugging runs。We touched briefly on software licensing。

 an important part of software development。 We used the location dot Java class from the Android platform。

 This helped in knowing that the code was robust and well tested。



![](img/3487291ea330a94d8b8eefe69860c72e_6.png)

The location class is licensed with an Apache 2。0 license， a standard open source software license。

This license allows us to modify the code to suit our needs outside of the Android platform。

 We could license the modified code using other licenses， but we chose the Apache 2。

0 license as well。In other courses we've developed。

 we use the Apache Commons CSV class to parse comma separated value files。

 This code is also licensed using the Apache 2。0 license， although we did not modify the CSV library。

As you processed quake data， you practiced programming and design skills。

 The programs you saw and wrote include those for searching for quake data。



![](img/3487291ea330a94d8b8eefe69860c72e_8.png)

![](img/3487291ea330a94d8b8eefe69860c72e_9.png)

Data that satisfies properties related to magnitude and location。In searching。

 filtering data entailed returning an array list of quake entry objects。

 object that satisfied criteria such as being close to where you live。



![](img/3487291ea330a94d8b8eefe69860c72e_11.png)

![](img/3487291ea330a94d8b8eefe69860c72e_12.png)

In searching for the closest 10 or 20 quakes， rather than all those within 1000 kilometers。

 we used different but similar techniques in particular we made a copy of the data being searched since the code we wrote modified the data in the process of searching。



![](img/3487291ea330a94d8b8eefe69860c72e_14.png)

![](img/3487291ea330a94d8b8eefe69860c72e_15.png)

These concepts and skills are a foundation for further work in searching and sorting data。

 happy programming。