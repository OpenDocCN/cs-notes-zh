# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p175 3_02_02_平均评分.zh_en -BV18U411U729_p175-

![](img/8eead52fe895adc9cb216bb232489d84_0.png)

Hi， let's get some recommendations about movies。 The first thing you're going to do is take a list of movies。

 See if each one has enough recommendations for a meaningful average。 And if so。

 compute the average recommendation。 Since you are now proficient in the seven steps。

 We are not going to walk you through how to develop the algorithm。

 You should be able to do that on your own。 We will， however。

 work through an example to make sure you know exactly what you want to do。😊。

We'll use these amazing movies。 My blocklockbuster Cosera spinoff， dude， where's my code。



![](img/8eead52fe895adc9cb216bb232489d84_2.png)

The comedic adventures of Owen and Robert go to White Castle。

 the thrilling tale of Susan Roger and the Goblet of Java， and my personal favorite。

 Snow White and the Seven Step。😊，For Raiders， we have our amazing team from On Duke。

 who do a lot of the behind the scenes stuff that made this specialization possible。

Now let's look at the first movie in the list， dude， where's my code， Justin only gave it two stars。

Quinin gave it three。 Genevieve didn't rate it。Nick gave it four stars， and Mitch gave it two stars。

 So for an average， we have 11 divided by4， which is 2。75。For the next movie。

 Genevieve was the only one who rated it， and she gave it five stars。

 but maybe if there's only one rating， we don't find that reliable enough to make recommendations from。

 This is where the minimum rate' parameter for the method you will write comes in。

 How many ratings are enough to say you have meaningful data。In this example。

 we'll say we need at least two of them to have it rated so we don't include Owen and Robert go to White Castle in our results。

 Too bad because I heard it was a great movie。 In fact， the single rating for it was quite high。

Three people rated Susan Roger in the goblet of Java with an average of 3。33。

 and everyone loved Snow White and the seven steps， which has an average rating of 4。0。

 It doesn't get much better than that。So for this problem。

 the answer would be this list of three movies with the average ratings we just computed。

You hopefully noticed a lot of familiar patterns iterating over each movie， iterating over each rate。

 computing an average， and putting results into a list。 When you compute the average for each movie。

 your code will mirror these patterns。So now you understand the problem and are ready to go solve it。

 Don't get distracted by movies， though， when you're writing the code。

