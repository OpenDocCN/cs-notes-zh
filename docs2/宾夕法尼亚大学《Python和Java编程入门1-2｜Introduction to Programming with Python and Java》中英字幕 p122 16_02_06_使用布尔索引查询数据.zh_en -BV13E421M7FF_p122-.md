# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p122 16_02_06_使用布尔索引查询数据.zh_en -BV13E421M7FF_p122-

To filter a data frame using Boolean indexing， you first create a series which is a one dimensional array。

 Each element in the series has a value of either true or false。

And Boolean indexing compares each value in the series to each record in the data frame。



![](img/5d9353a9cc05dbab9537955d56b2c3cb_1.png)

Let's see how it works。 What if we want to select the businesses in Pittsburgh， Well。

 let's create a condition from the data frame where the city。Is equal to。Pittsburgh。

That's our condition。 We're going to store that in a variable pits。

If we run that and then see what the type of that is。We can see that It's a series。

Now let's see what's contained in that series。Pets。

I can see that it's basically a sequence of true false values。 Now。

 what I want to do is compare these true false values to the data frame itself。To do that。

 I'm going to filter the elements in the data frame。

By providing the name of the data frame and then in square brackets， put the condition。Pits。

 and what this is going to do is filter the data frame based on the true false values in the series。

 pits。Now， I only see the records where the city is Pittsburgh。



![](img/5d9353a9cc05dbab9537955d56b2c3cb_3.png)

Does the Dr Chinese cuisine offer takeout to answer that question。

 we need to filter our data and look for the business with the name the dragon Chinese cuisine。

 So let's create a condition。From the data frame where the name is equal to the dragon Chinese cuisine。

We'll store that condition in a variable， and then let's filter our data frame using that condition。

There's one business with that name。 I could see here that the takeout value is true， right。

 that it does provide takeout。 But let's see if we can get just that column。 So from。Df。

Given that condition， let's get just the takeout column。True， it does provide takeout。



![](img/5d9353a9cc05dbab9537955d56b2c3cb_5.png)

Let's select just the bars in the data set。 And to do that。

 we're going to use the user defined business category columns to create some conditions。

So from the data frame， where category 0。Is equal to bars。

 meaning a user assigned that category to the business。Or where category 1 is equal to bars。

 So either category 0 or category 1 could be set to bars。

 We're going to look for businesses with one or the other。Let's store this in a variable。

Category 0 bars。And then we'll call this Cat 1 bars。

 And then from the data frame where cat 0 bars is true or using the vertical pipe。Cat 1 bars is true。

 And what this is going to return is those businesses where either category 0 is set to bars or Cat 1 is set to bars。

These are the businesses。Where either category 0 is bars or category 1 is bars。Now。

 let's select the bars in the city of Carnegie to do this， we're going to add a third condition。

 So here are the previous two conditions where Cat 0 is set to bars or Cat 1 is set to bars。

 Our third condition will'll look at the city。 So from the data frame where the city is equal to。



![](img/5d9353a9cc05dbab9537955d56b2c3cb_7.png)

Carnegie。Store that in a variable。Call that Carnegie。 We're going to use these three conditions。

 We're going to put them together。 So from the data frame。Where。Cat 0 bars is true。

 or using the vertical pipe。 Cat 1 bars is true。And using the ampersand。Carnegie is true。

 and this is going to return the businesses where either category 0 bars is true。

Category1 bars is true， and Carnegie is true。We run that。 These are the bars in the city of Carnegie。

Now， let's select the bars and restaurants in the city of Carnegie To do that。

 we're going to update our conditions slightly。So let's check if the value in the category 0 column is in a list to do that。

 We'll use the is in function。 And then we're going to provide a list of possible values。

 meaning the value in the category 0 column is one of the values in this list。

 It's either going to be bars。Or。Restaurants， it's one of those values。

And then we'll do the same for Cat 1 is the value in the category 1 column in the list。

 bars or restaurants。Store these in variables。Cat 0， cat 1。 And then our third condition is the same。

We'll call it Carnegie。Where the city。Is equal to。Carnegie。

 and then let's put the three conditions together using the data frame。 Either cat 0 is true。Or。

Cat 1 is true， and。Carnegie is true。 So this is going to return the businesses where Cat 0 is set to bars or restaurants。

Or cat 1 is set to bars or restaurants， And the city is Carnegie。



![](img/5d9353a9cc05dbab9537955d56b2c3cb_9.png)

If I run my code， I can see here that these are the bars and restaurants in the city of Carnegie。



![](img/5d9353a9cc05dbab9537955d56b2c3cb_11.png)