# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p84 84_04_05_BigQuery到Colab管道.zh_en -BV11y411z7Dn_p84-

![](img/d41d61ae5e7b12aae410d4fa00f39944_0.png)

Let's go through and build a very realistic data cleansing and visualization pipeline using Google BigQury。

 This happens quite a bit。 You have to go through multiple stages of looking at your data。

 cleaning your data and visualizing your data。 So let's go ahead and take a look at this page views here。

 you can see for Wikipedia。 It's got data hour wiki title views。 And if I wanted to query it。

 I could just select query and new tab， and it'll give me the beginning of a query。 Now。

 in my scenario here， what I want to do is actually look at some of the top views on Wikipedia and to start with。

 I can actually go through here and just throw in a query I've got。 So we have select views title。

 we're gonna look at this big query， page views 2023 table and I want to look at this particular date range right here。

 which is 4 18 and we want to actually look at the top， let's say  thousand views here。

 Now if I want to format it， we can go ahead and format it， just to make sure everything looks good。

And from here， we can actually go through and run。 All right。

 So once we go through here and run this， what we'll see is that the results do come back。

 but they're not exactly the way I want。 You can see here it's got cookie information， main page。

 So of course， people are going to be viewing the main page of Wikipedia。 that's nice to know。

 But look at this。 we have some results here like NoAirrus。 for example。

 I want to dig into that a little bit more。 So I need to clean this query up。 So how do we do this。

 Well， let's go ahead and go through and clean it up by making a more complex query。

 What I do as I say， look， I want to look at this date range。

 but I don't want to see these other types of titles， right， the main page special Wikipedia data。

 right， These are some of the things I want to exclude。 And if we go through here and we run this。

It's actually going to filter out a lot of the things that I didn't like before， right greats。

 Now we again need to look through here and find some ways to filter out the data because look at this。

 This shows up quite a bit。 And my impression when I've gone through andqueed it is it's also a main page in another language。

 So all we need to do is just tweak this query a little bit。

 We'll just say or title like and let's go ahead and paste this in。And then from here。

 let's get rid of this comma right there， let's go ahead and format the query perfect。

 and let's run it again。 So a lot of times you will need to kind of iteratively go through here and pick out the queries。

 and this looks a lot better right so we see this We've actually got you know a lot of results here that look pretty good。

And we could even go through and filter more and more and more。

 But one of the things that we can do next here， instead of only using SQL is we could actually go to explore the data。

 So let's go ahead and explore the data。 But this time with coab notebook and coab notebook allows us to query things in Python。

 So I could actually go through and filter。

![](img/d41d61ae5e7b12aae410d4fa00f39944_2.png)

What's happening by looking at it in Python。 So the first thing that I need to do is I need to run a setup and this will do some off code that gets me hooking up into here。

 and then we go through and we do that same query。 Now just copies that query which is right here。

 which looks good and then we can actually load this results set which we have the results right here。

 here's the exact same thing。 but this time it's a data frame and then finally we can go through here and we can look at the describe。

 And this is good。 But again， we need to actually go through and deduop this。

 So what we can do is I can also take some code here that I've got handy and we can filter this a little bit better。

 So one of the first things that we can do is we can actually say let's go ahead and group by title in some of the view。

 So all we to do is go through here and add another piece of code。Right there we say results。

 result group by summit， reset the index。 and let's go ahead and view it again。 there we go。

 So we have a lot better of a deduplication type view now that shows us what's going on。

 It may not be perfect。 but it's a pretty good start。 And all we need to do now is visualize it。

 So in order to visualize it again， we just add a code cell right here。

 and I can just use Cborn to coded up。 So first up。

 I'll go ahead and import Cborn import seaborn and SN S。 let's go ahead and do that。

 let's go ahead and get a top 25 result here。 So that's the next thing that we'll do so we'll go ahead and say code。

 we'll say top 25 perfect。 And then finally， all I need to do is create a barpl using Cborn。

 Let's go ahead and run that perfect SN S set white grid。

 let's go ahead and set this title top 25 most viewed Wikipedia pages on 418。😊。



![](img/d41d61ae5e7b12aae410d4fa00f39944_4.png)

Let's go ahead and query it。 What have we got aha perfect。

 So we have a pretty good view here of what's going on in the day of 418。

 we can see NoA Cyrus is a very big Wikipedia page。

 we see chatt GBT is a very big Wikipedia page we see other people as well。

 and this gives us a nice overview of how to actually look at what's popular in the world by using off thehe tools from Google BigQury as well as Coab notebook。



![](img/d41d61ae5e7b12aae410d4fa00f39944_6.png)