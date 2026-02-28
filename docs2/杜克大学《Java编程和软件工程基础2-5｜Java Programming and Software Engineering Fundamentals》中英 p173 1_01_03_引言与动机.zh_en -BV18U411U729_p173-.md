# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p173 1_01_03_引言与动机.zh_en -BV18U411U729_p173-

![](img/e6f2197270ba192565e199f163532667_0.png)

Well， now that we're done producing all those Courra videos， it's time for some fun and relaxation。

 Let's watch something cool on Netflix。😊。

![](img/e6f2197270ba192565e199f163532667_2.png)

Hey， I made cookies last night， help yourselves。

![](img/e6f2197270ba192565e199f163532667_4.png)

So what should we watch， I don't know。It's been so long since I had any free time to watch anything。

Well， Netflix had some suggestions。 Maybe one of those could be good。

 How do you think they come up with these recommendations， I mean。

 it seems like it would be a pretty complicated algorithm requiring lots of data。Yes。

 Netflix has something complex and proprietary， but the basic concepts aren't that hard。

I bet any of the learners that completed our Coursera courses could implement one。

Speaking of your Cosera courses， you all aren't quite done yet。 You still have to make the capstone。

 The capstone。 so much for movie night。Hey， I bet a recommender system would make a great capstone。

 Yeah， the algorithm has real world uses for our learners。

 and they can make a web page to go with it and let everyone see what they can do。😊。



![](img/e6f2197270ba192565e199f163532667_6.png)

Let's get to it。I'm excited to provide a bit of background for our capstone project。

 a D I Y or do it yourself recommendation engine for finding recommendations and information about current movies。

 When you first visit the Coursera co website， you'll see recommendations like the ones you see here。

😊，Recommendations for every learner that include data science， Python， machine learning， and more。

How does Coursera make these recommendations， do they show you popular courses that might increase the number of learners who participate well and completely？

Perhaps they show you different recommendations based on what your browsing history is or what websites you visited。

 they might be able to do that if they partner with a business that knows information about you。

In this capstone， we'll write code to recommend movies based on different criteria。

 criteria based on user ratings of those movies。 You might want to learn about programming from Coursera。

 you would ask the website for recommendations by searching for programming， thus。

 filtering all the recommendations available to roughly 375 recommendations based on the query programming。

 How does the engine behind the creation of this web page decide what courses to show。

 I it based on ratings， Some other criteria， Note， the third recommendation is for the first course in the specialization for this capstone。

You can also get restaurant recommendations rather than programming recommendations。

 Suppose you're going to be in San Francisco and you're looking for Asian food near the financial district。

 You could use Yelp and app and website for getting recommendations from users that is diners。

You could filter by location， as I've shown here， finding Asian food near San Francisco。

 These restaurants all have four stars。I filtered to find restaurants near the financial district。

 but you could filter based on price or other criteria。You can use Yelp in cities around the world。

Diners from many countries can contribute ratings through Yelp so that other users can use these ratings to find information about restaurants in cities ranging from San Francisco to the Hague in the Netherlands。

You may want to sort the data so that good recommendations appear near the top of the results。

Sometimes these ratings are sorted by criteria other than how many stars they have。 In this example。

 you can see the first restaurant has fewer stars than the third restaurant。

You can search by whether a restaurant is nearby or by recent ratings instead of total ratings。

All this talk about restaurant tradings is making me hungry。Instead of restaurants。

 you can also get recommendations about movies， and this is what you'll write cap for this capstone project。

The website， Twitflix。com minds Twitter for tweets that include comments about current movies。

These comments are turned into ratings that are made part of the input to your program。

To use these ratings， you'd have to get them， parse them。

 and write a program to determine which movie someone should watch。Rather than using Twiflix。

 we'll use another Twitter based source of data that's easier to parse。

 and you'll be able to use these collected tweets to explore recommendations。

Instead of relying on your peers， you might decide to rely on movie critics who have more experience rating movies。

Instead of using your friends or regular viewers to decide whether to see a movie。

 you could rely on so called experts。These are critics who see movies and then rate them。

 The website Roten Toes aggregates these professional review and ratings and makes them available to everyone。

This site uses average ratings as the basis by which to make recommendations to a user。

You'll be able to replicate some of this functionality in this capstone experience。

You'll also be able to make recommendations by filtering based on genre or co stars or by any other criteria。

Those were recommendations based on critics， rather than on viewers， you know。

 or your own ratings of movies。 You might want to know what viewers like you watched since the like you means that these people likely share some of your tastes in the kinds of movies that they've watched。

Netflix makes this easy， for example， by showing you recommendations based on what viewers like you are watching。

You'll be designing and writing classes to implement a recommendation engine that makes recommendations along the lines we've just discussed。

Your program could make recommendations from many sources， food， movies， books or more。

 It just depends on the data that you read in。As we've told you。

 you'll be making recommendations based on crowdsourced movie comments and ratings from Twitter posts。

Your recommendations will take several forms。This is the URL for the web service that provides live data that we're using。

 but you'll also be able to obtain all the ratings from our specialization website。

 Dukelearunderprogram。 com。

![](img/e6f2197270ba192565e199f163532667_8.png)

You'll write code to parse the recommendation ratings and movie data so that your program can make recommendations。

 Your recommendations could be like those found on Twitter or Yelp based on ratings and averages of those ratings。

This is a useful and straightforward coding exercise。Al。

 ratings and recommendations could be based on what Netflix and Amazon do。

 find viewers or buyers similar to you and provide recommendations based on what these buyers purchase。

In this case， you'll be able to find users like you or like another viewer as part of the code you'll design and implement。

Let's get to it。