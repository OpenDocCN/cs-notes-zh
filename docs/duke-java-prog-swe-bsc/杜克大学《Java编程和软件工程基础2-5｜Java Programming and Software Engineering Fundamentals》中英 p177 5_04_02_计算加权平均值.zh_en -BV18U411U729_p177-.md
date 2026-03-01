# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p177 5_04_02_计算加权平均值.zh_en -BV18U411U729_p177-

![](img/86e064644c7b96de59a921fbbad1dfc0_0.png)

Hi， in this part of the capstone project， you'll add a new kind of recommendation that will help make recommendations better for you than using simple averages。

 These recommendations will use information about your own ratings or for any rate given their ratings。

😊。

![](img/86e064644c7b96de59a921fbbad1dfc0_2.png)

Average ratings may be flawed。 Let's look at these ratings for four movies， Mission Imposible。

 The Martian， pitchitch Perfect2， and Star Wars， the Force awakens。

Using average ratings for the movies， as we shown here， treats each rater equally。

 But for recommendations for me， Morgan's evaluations might be better than Jesse。

 because I might be closer to Morgan in terms of movies I like for you。

 Sam's ratings might be better for creating recommendations。😊。



![](img/86e064644c7b96de59a921fbbad1dfc0_4.png)

This is the idea behind a different kind of average or recommendation。

 one called collaborative filtering。The idea is to create recommendations specific to a user or rater。

 rather than the same recommendations for all users。To do this， you'll weight rateers differently。

 valuing those rateers who are more like you in calculating averages。

To create collaborative recommendations， you'll need to make a few modifications to the averaging method you've already written。



![](img/86e064644c7b96de59a921fbbad1dfc0_6.png)

You'll need to find raters more like you and use their ratings。

 the U here will be a parameter to the method used to create recommendations by using weighted averages。

For example， Chris and I may both dislike the movie， Lucy and both like the movie Rainman。

 So Chris is close to me in some way because we have similar taste in movies。On the other hand。

 Sam might like Lucy when I didn't。 Sam didn't like rainman， but I did。

 So Sam's ratings should carry less weight than Chris's ratings because Sam and I don't see things in quite the same way that Chris and I do。

😊，So I'll value Chris's ratings more than Sam's in creating a new weighted average for getting recommendations。



![](img/86e064644c7b96de59a921fbbad1dfc0_8.png)

If Chris likes the movieA beautifulut Mind， and I haven't seen it。



![](img/86e064644c7b96de59a921fbbad1dfc0_10.png)

Then I might be it might be time to think about watching it。

 This is the general idea behind the new program you'll be writing。

Let's look at how to calculate these weighted averages。



![](img/86e064644c7b96de59a921fbbad1dfc0_12.png)

There are two conceptual changes to the code you've already written that makes recommendations based on averaging all user ratings in the table below are ratings from three Raers。

 Chris， Sam and Morgan。The first change is to only use ratings from rateers close to me or to the person for whom recommendations are being made。

The number of close rateers is a parameter， so you might use n equal to 10 to use 10 close raters。



![](img/86e064644c7b96de59a921fbbad1dfc0_14.png)

The second change is to weight the ratings by a measure of how close a rateer is to me or to the person getting recommendations。

 Let's look at this idea in more detail。Which of these movies has the highest average。

 so it's the most recommended movie for me。The fly has an average rating of 7 from the two Raers。

 Chris and Morgan， who rated it。Spiderman has an average rating of6。

The butterfly effect has an average rating of7。And beetle juice has an average rating of 7。5。

Given these averages， I should watch beetle juice， it has the highest average rating。

But Chris might be more like me than Morgan， so I should value Chris's ratings more。

 This will change how we calculate averages to get recommendations。

Let's look more closely at calculating the weighted averages。



![](img/86e064644c7b96de59a921fbbad1dfc0_16.png)

We'll use the closeness weight for each rater in creating averages for the movie ratings。

 as you can see in the table Chris's weight is 20， Sams is 10 and Morgan is5。

 we'll show how to calculate these weights next， for now we'll use the weights in creating average recommendations。



![](img/86e064644c7b96de59a921fbbad1dfc0_18.png)

We'll multiply each rating by this closest weight in calculating averages。

Not every movie will get a rating from each rateer will use the weighted averages to get a recommendation specific to me or to any rateer whose closest weightings are used in calculating averages。

In calculating an average for the fly， we multiply 8 by 20 since Chris's weight is 20。

 and Chris's rating is 8。 Sam didn't rate the movie。 So no value from Sam。From Morgan。

 we get Morgan's weight of  five times Morgan's rating of 6 to get 30。

 This gives a weighted average of 95。That's different from the unweighted average of 7。

Spiderman's weighted average is 66。67 after multiplying each rating by the rateers's corresponding weight。

The butterfly effect has a weighted average of 83。3， and beetle juice has a weighted average of 60。

Given these weighted averages， it looks like we should watch the fly。

 Note that the best movie used on unweighted average is beetleju。

 and this is the lowest rateed movie using weighted averages。To calculate this weighted average。

 we need to calculate a weight。 how close a rateer is to me or to some particular rateer。

Well represent each rate by a vector of ratings to discuss how to calculate closeness。

 The vector is conceptually just a list of ratings for each movie。For example。

 here are seven ratings by a raider named Sam to help with this explanation were including movies that are not rated by Sam。

 These are represented by zeros。In the programs you write。

 ratings are stored only for those movies actually rated by Sam。Chris has shown with seven ratings。

 although Chris has only rated four of the movies， the non rated movies are represented by zeros。

My seven element vector shows I rated six movies。Let's look at how these vectors are used to calculate a similarity weight。

We'll walk through the calculation for seeing how close I am to Sam。

 We multiply the ratings for each movie， Sam and I both rate。Sam ratess this movie of five。

 I rated a6， the product is 30。The next movie， we both rate has a seven by Sam and a four by me。

 so the product is 28。For this movie， Sam gives an eight， I give a4， the product is 32。

The last movie we both rate wasn't liked by Sam， who gave it a one。 I gave it a6。 The product is 6。

 So the similarity weight between Sam and me is the sum of these values，30 plus 28 plus 32 plus 6。

 which is 96。The weighted similarity for Chris and me is calculated the same way。

 We have three movies we both rated。 We calculate the sum of 12 plus 42 plus 54， which is 108。

 So I am closer to Sam than I am to Chris。 since the weight is a measure of closeness。😊。



![](img/86e064644c7b96de59a921fbbad1dfc0_20.png)

This calculation is actually a dot product， a measure of mathematical closeness in a vector space。

 It's good to know there's a mathematical foundation for how we're calculating weighted averages。😊。

In this case， we simply calculate the sum of the product of each movie， two Raers rate in common。

In our actual calculations， we'll need to adjust the ratings to address the scale of1 to 10 where a rating of one means really。

 really don't like a movie， and a 1 means really， really like a movie。

We want the ratings that are on a scale of 1 to 10 to work when we determine closeness by calculating dot products。

 we want rateers who are close to rate movies similarly， both like or both dislike， for example。

 since this closeness is a measure of similarity。

![](img/86e064644c7b96de59a921fbbad1dfc0_22.png)

If we simply multiply ratings， how do two raters who rate a movie with a one and a two compared to those who give ratings of  eight and nine？



![](img/86e064644c7b96de59a921fbbad1dfc0_24.png)

![](img/86e064644c7b96de59a921fbbad1dfc0_25.png)

If we multiply， we'd compare 2 to 72 a huge difference， but these Raers have very similar tastes。

Giving a one and a two is the same as giving an 8 and a 9 in terms of similarity。

 Both rateers really dislike a movie with a one and a two。

 and both readersers really like a movie with an 8 and a 9。

 These pairs of ratings should contribute equally to a measure of similarity， but they don't。

We'll center the ratings by subtracting the middle rating of 5 from each one。

 So rather than using 1 and 2， we'll use 1-5 and 2-5 or -4 and -3 for the ratings of 8 and 9。

 we'll use 8-5 and 9-5 or 3 and 4。 We get a product of 12 for both centered ratings。

 And thus we get that the ratingrs are equally similar。

And this example will show syned ratings by subtracting5 from each one ratings that were originally 0 are shown with an asterisk。

 We won't use those in calculating a similarity score。 For example。

 here are seven ratings from Sam shown centered with their original noncented ratings。

 You see that zeros in the original are represented by asterisks and the centered ratings。

 Remember that in the programs you write， ratings are stored only for those movies actually rated by Sam。

Chris is shown with seven ratings， all positive because Chris likes movies。



![](img/86e064644c7b96de59a921fbbad1dfc0_27.png)

My seven element vector shows I rated six movies。Let's look at how these vectors are used to calculate a similarity weight。

 We'll walk through the calculation for seeing how close I am to Sam。

 We multiply the ratings for each movie Sam and I both rate。 Sam writes this movie is 0。 I rated to1。

 The product is 0。😊，The next movie we both rate has a 2 by Sam， a minus1 by me。

 so the product is minus2。For this movie， Sam G Ze3， I gave a minus1， the product is minus3。

The last movie we both rate wasn't liked by Sam， who gave it a-4。 I gave it a one。 The product is -4。

 So the similar weight between Sam and me is the sum of these values，0 plus-2 plus-3 plus -4。

 which is -9。The weighted similarity for Chris and me is calculated the same way。

 We have three movies we both rated。 We calculate the sum of -3 plus 12 plus 4， which is 3。

 So I'm closer to Chris than I am to Sam。 Since the weight is a measure of closeness。

 Remember that in the original noncented ratings。 I was closer to Sam。 So this makes a difference。

 you can see in the ratings that Sam and I don't really agree When I like a movie， Sam doesn't。

 And vice versa， since all the products are negative。😊。

This technique is standard in calculating similarities， but it's easy to forget。

Similarity weightings will change if ratings on an all positive scale like 1 to 10 aren't centered in this way。

Let's look at the Java code for calculating these weighted similarities to find the rateers near me or near to any Raer。

 we'll call the method get similarities that you'll complete for this capstone。

The parameter ID is the rate for whom similar ratings will be calculated。

A class Rar database will supply access to each rater given a Raer's ID。

 This class is similar to the movie database class you've already used。

The Raer database class also supplies access to all Raiders。

 just as the movie database class supplied access to all movies， though the movies could be filtered。

In this loop， you'll call another method to calculate the dot product between me and the Raer R。

This dot product value will be paired with Ra Rs ID in a rating object and added to the array list being returned。

Before returning the array list， the code will sort the list so that first rating is that of the rate with the highest weight。

 The one closest to me。 we can do that by calling collections。

 sort and passing a comparator that's part of the Javavaat U collection class。

This comparator reverses the order of the rating compared to function。

 so that list will store highest values first。Once you've got the weights for each rateer。

 you'll be able to calculate a weighted average to get recommendations。



![](img/86e064644c7b96de59a921fbbad1dfc0_29.png)

This method is similar to get averages， but is for a particular rate whose ID is a parameter。First。

 the weights for all raters are calculated by calling the method get similarities we've just discussed。

As with the get averages method， this code loops over Raers in the Gi averages method。

 the loop was over all Raers， and we checked to see if each rater had rated the movie whose average was being calculated。

Here we loop over just those rateers who are close to me。

 those for whom weights are stored in the array list name list。

 We use only the first norrators entries and list， where norrators is a parameter。

The idea is to use just the top 10 or 20 or 100 rateers who are closest to me。

You'll need to be careful in ensuring there is no bad indexing and getting ratings from L。

 After accumulating a weighted sum， the weighted average will be added to the array list being returned。

 just like the code and the unweighted get average method。You'll return the list of movie ratings。

 you may want to sort it first。After getting collaboratively filtered recommendations。😊。

You'll need to write code to present these to the user。



![](img/86e064644c7b96de59a921fbbad1dfc0_31.png)

You'll need to decide whether you should provide recommendations for movies already seen。

This is a list of recommendations for me。Based on 10 ratings I created for movies I've seen this year。

Movies I rated are shown with asterisks in the output。

These ratings might help me calibrate the results since I liked these movies。

 seeing them in the list of the top 15 makes sense to me。

 even though I don't need a recommendation to see them since I've already seen them。😊。

Should we print more than the top 15， Should we print all the recommendations。

Should we print the weighted average？You'll also decide whether you should print more information than just the movie's title。

You could print the year， the genre， or more。You could generate HTML output to display the recommendations in a web page。

 have fun finding recommendations。