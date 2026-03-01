# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p46 46_04_04_哪些国家出口：算法开发.zh_en -BV18U411U729_p46-

![](img/4a14a4c4944517842bb354642c3ccec7_0.png)

Welcome back now that you know a little bit about the basics of working with CSV files。

 it is time for you to solve a problem using them。Here we have a CSV file which shows export data for 218 countries。

 the columns are the country name， the main exports。

 and the total value of their exports in 2014 in US dollars。



![](img/4a14a4c4944517842bb354642c3ccec7_2.png)

![](img/4a14a4c4944517842bb354642c3ccec7_3.png)

A problem you might want to solve with this data is to find which countries export a particular item。

 for example， you might want to print all of the countries which export lobsters or all of the countries which export iron。

There's a lot of data in this file， way too much to look at by hand。

 which would be tedious and error prone instead you would rather write a program to perform this analysis for you。

 as always we will walk through how you write such a program using the seven steps。

Step one is to work a small instance of the problem by hand here we have cut the table down to four countries and only listed a few exports for each of them。

 which of these countries exports coffee。After looking at the table for a few seconds。

 you can see that Madagascar and Malawi export coffee in Macedonia and Malaysia do not。



![](img/4a14a4c4944517842bb354642c3ccec7_5.png)

Next， you need to write down what you just did if you just say I just looked at it and saw the answer。

 that will not help for step three instead you need to think through what you did in a more step by step fashion。

 how did you look at the table and see the answer？You probably looked at the first rose export column and saw that it did not contain coffee Next。

 you looked at the second rose export column and saw that it contains coffee。

 so you wrote down Madagascar。Next you looked at the third R export column and saw that it also contains coffee。

 so you wrote downMalawi。Finally， you looked at the Four Roses exports column and saw that it did not contain coffee。



![](img/4a14a4c4944517842bb354642c3ccec7_7.png)

Thinking through this in a step by step fashion leads to these 10 steps for this particular instance of the problem Now we are ready to look for patterns and generalize。

Notice how you are doing very similar things for each row。

 this similarity suggests you will eventually want to loop over each row， however。

 there are some differences in the steps for each row that you need to think through before you can express this algorithm in terms of for each row。

The first difference you might notice is that on line5 you wrote down Madagascar and on line8。

 you wrote down Malawi。Where did these particular words come from？

They are the value of the country column for the row you are looking at。

The next difference you might notice is that you do not write down the country for the first and fourth rows。

 but you do write it down for the second and third。

How did you know whether to write the country down or not。

 you made this choice based on whether or not the row contained coffee in the exports column。

Now that you have figured out how to operate on each row in the same way。

 you can write down the generalized steps in terms of for each row in the CSV file。

 generalizing over how many rows the file has。

![](img/4a14a4c4944517842bb354642c3ccec7_9.png)

Now that you have a general algorithm to solve this problem， it is time to test it out。

 here is a table of data which contains two countries。

 use the algorithm to find out which ones export lobster is this algorithm correct。

According to our algorithm， Brazil is the country which exports lobster oops， that's not correct。

 we should have gotten Angula。Did you test the algorithm carefully enough to notice this mistake。

 The problem is that our algorithm always checks for coffee。

 not for whatever export we are interested in。 We should have thought this through as we generalized。

 but we missed doing that。 This is exactly the sort of problem。 Step 4。

 Test your algorithm is intended to catch before you write code。

You can fix this algorithm by referring to the parameter， we'll call it export of interest。

 which indicates which export you want to look for。

 making this correction to the algorithm will have it yield the right answer on this test case Now that you have an algorithm。

 it's time to write the code。

![](img/4a14a4c4944517842bb354642c3ccec7_11.png)