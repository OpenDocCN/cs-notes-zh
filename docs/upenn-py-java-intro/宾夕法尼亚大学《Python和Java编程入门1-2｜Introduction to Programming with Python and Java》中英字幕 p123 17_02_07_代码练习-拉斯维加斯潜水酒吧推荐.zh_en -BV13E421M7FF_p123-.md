# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p123 17_02_07_代码练习-拉斯维加斯潜水酒吧推荐.zh_en -BV13E421M7FF_p123-

Let's do an exercise。How many total dive bars are there in Las Vegas。

You can assume a Yelp user assigned dive bars in the category 0 column or category 1 column。

Then recommend a random dive bar with at least a four star rating。To do that。

 look at the total set of dive bars in Las Vegas and filter for those that have a star rating of at least 4。

0， and then recommend one。

![](img/6e68898a1dae4f6b04edb96414a9785c_1.png)

Let's first look for all the dive bars in Las Vegas。So from the data frame。

 where the city is equal to。Las Vegas will call that condition L V。

And then cat0 bars is equal to the condition where category0 is equal to。Dive bars。

Then we'll create another condition for Cat 1， where Cat 1 is equal to dive bars。

 We'll call that cat1 bars。Then let's put those three conditions together to create a new data frame。

 we'll call that dive bars underscore Lv is equal to the data frame using these three conditions where Lv is true。

 meaning the city is equal to Las Vegas， and either cat0 bars is true or cat1 bars is true。

Once we run that， it's going to give us a new data frame dive bars Lv。

 We can get the length of that to get the total number of dive bars in Las Vegas。

 So let's get the length of dive bars Lv。 That should be the number of dive bars in Las Vegas。

 I could see there's only three。 Now we're going to recommend one of those dive bars with at least a four star rating。

Let's create another condition looking at only those dive bars with at least a four star rating。

 So from the dive bars underscore Lv data frame， let's look at the stars column and let's look at the ones that are greater than or equal to 4。

0。 We'll store this in a new condition called stars。 Let's filter our data down even further。

 We'll call this dive bars underscore Lv 4 star。Rating is equal to this data frame。

 using our condition。We can run that， and we can see。

That there are two dive bars with at least a four star rating。To recommend a random  one。

 I'm going to have to generate a random number。 So let's go ahead and import the random module。

 This will provide us with some additional functionality for generating a random number。

 I'll run that。Then from the random module， let's use the R int method to generate a random number between 0 and the length of the data frame-1。

 This will generate a random number between 0 and the largest possible index in the data frame will store that in a variable R int。

And then we're going to use this random number to get a slice from the data frame。

 So from the data frame， let's get a slice， the start index will be the random number itself。

 The end index will be the random number plus1。 So the slice will only have one dive bar in it。

 We'll call it Rand dive bar。So every time I run the code in this cell。

 I should get a different dive bar from this data frame。

 We'll go ahead and print out what the random dive bar is。 And I'm going to run this Huntdge tavern。

Moondogies。Hunridge tavern。Instead of creating a slice。

 we can also use the IO method to choose rows by position。So I'm going to copy this code。

 which generates the random number。 that's going to be the same。I'm going to copy it down here。

 paste it。We're going to generate a random number between 0 and the largest possible index in the data frame。

 And then from the data frame， we're going to use the I log method and then just give it the index of the row that we want。

 And that's going to be the R int， we'll store that in a random divebar variable again。

 And then every time I run the code。In this cell， I should get a random dive bar from the data frame。

Moondogies。Hundge tavern。Huntridge tavern。Moon dokeys。



![](img/6e68898a1dae4f6b04edb96414a9785c_3.png)