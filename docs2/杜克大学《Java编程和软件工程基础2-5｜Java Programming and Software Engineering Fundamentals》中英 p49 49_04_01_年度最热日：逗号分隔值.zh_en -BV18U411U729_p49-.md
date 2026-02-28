# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p49 49_04_01_年度最热日：逗号分隔值.zh_en -BV18U411U729_p49-

![](img/174d8a9b771b3031644bb6754805e08c_0.png)

Welcome back Now that you know a bit about working with CSV files。

 It is time to learn how to analyze numerical data in those files。 For example。

 here we have a CSV data file about the weather at the Raleigh Durham Air for January 1，2014。

 We have this data for every day in a couple years with one CSV file per day。

 Each row contains information about one hour of weather and there are a variety of columns such as the temperature in Fahrenheit。

 the dew point， the humidity， etc cetera。 If you are studying weather patterns。

 you might want to analyze this data and ask a variety of questions。 Of course。

 the techniques you will learn are applicable to other types of data too。

 so you may find them useful in a variety of other fields as well。😊。

One question you might want to ask is what is the maximum temperature that is， when is it hottest？

If you are doing this just for the data on one particular day， you could just look。

 there are only 24 entries or use the max function in a spreadsheet。However。

 what would you do if you wanted to find the maximum temperature over many days。

 such as for an entire year， you certainly do not want to look through all of the data by hand and importing 365 files into your spreadsheet would be quite tedious for something like this。

 you would want to write a program to do the work for you。In this lesson。

 that is exactly the problem you will solve， finding the hottest day of the year。

For the purposes of this example， we are going to say that the hottest day of the year is the one with the highest maximum temperature。

 A related but slightly different problem is to find the day with the highest average temperature。

We're not going to walk through that problem， but you could certainly do it after this lesson。

The plan to write this program is to start by learning about dealing with numerical data。

 the CSV parser will read the data as strings which have to be converted to numbers once you know how to convert strings to numbers we'll start with a smaller piece of the problem just finding the maximum temperature on one day we'll walk through the algorithm and the code development with you。

You will want to test your code to be confident that it is correct before proceeding once you are confident in your code to find the maximum temperature on one day。

 you will want to build on it and find the maximum temperature for many days。



![](img/174d8a9b771b3031644bb6754805e08c_2.png)

This will let you find the maximum temperature in a year， so let's get started。

