# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p143 23_03_05_基于距离的Comparator实现.zh_en -BV18U411U729_p143-

![](img/05a42f0b4bf2184267cdeaa2238b4f32_0.png)

Hi， we're going to write a distance comparator。 We want to sort the earthquakes based on their location from a specific location。

 So I've already started this class here called distance comparator。

 It's going to implement a comparator of quake entries。 You can see that。

We're going to have a variable location called fromware。

And we've already got the constructor that we're going to pass in the variable where and set from where to where。

 and now we just have to write the compare method， so that's what we're going to do here。

 we're going to take two quick entries and we want to compare them。All right。

So what we're going to do is first of all， we're going to get the distance of the location of the first earthquake to our variable from where our parameter from where。

So we'll create。A variable called distance1。And we'll look at Quake Enry Q1。

We'll need to get its location。So we'll call the get location method。

 and then from there we need to calculate the distance to。From where。

And then we're going to do the same thing for the other quake， so we'll create another variable。

 this one what we call distance2。And then we'll do pretty much the same thing we'll need to look at Q2's location。

Use the get location method and then distance to。And so now we know for each of the two earthquakes。

 Q1 and Q2， how far they are from our specified location that we're going to compare all the earthquakes to。

And then we just need to compare them now。 So what we're going to do is we're going to call the compare method。

呃。Double dot compare。With these two distances。So we'll compare distance  one and distance 2。

And that is going to and will return that value， so that will either return that they're equal by returning zero or a return a positive number or a negative number。

 depending on which one is bigger。And we'll compile this。

It looks like it compiled and now we want to use the distance comparator so we can sort our earthquakes based on their location from a specific place。

 So I have a second method here， a second class here called Dis sorter。

 which I've already started and again what we're going to do in here because we're going to read a bunch of earthquakes in。

 I have a specific location in there， what you can change it I've got the location set to Durham。

 North Carolina and then what I'm doing right now is just printing out all the earthquakes。

 but I would like to sort them first。Based on their distance to Durham， North Carolina。

 So I just need to add in one line here。So that we can use。The distance comparator we just wrote。

So I'm going to add in， we're going to use collections。 sort。

And we're going to sort our list of quake entries， which is called list， so we'll pass that in。

And then we're going to specify that we want to use our comparator we just wrote。

 So we need to create a new distance comparator。And whenever you create the distance comparator。

 you need to pass in one parameter， which is some location that you want them all sorted based on their difference to that location。

 And so we're just going to pass in where which happens to be in this case， Durham North Carolina。

And so that should sort all the earthquakes based on their distance of location。

 and then we'll print them out。 and we should see that。 So let me just see if this compiles。Okay。

 so we did good， no syntax heres， we can then run our program， we'll go to Blue Jay。

And we'll just create a new distance order。And we'll run the sort by distance method we just modified。

And now we're getting all kinds of data。 Let's see what we got， so。呃。If we look at this。

 you can see that they're all sorted because they're close to。 these are all in Indonesia。

 We're going to scroll up。 These are in Japan。 Now we're going to slowly get closer to Durham。

 North Carolina。 Now we're looking at Greece。 we're looking at Alaska， we're looking at Hawaii。

Keep going。And let's see what we get。A lot of earthquakes in Alaska。Now we get California。

 lots of earthquakes in there， and then finally Oregon。We're going all the way up。And then finally。

 we see there was one earthquake in North Carolina，1 in South Carolina，1 in Georgia。

 But you can see the first ones are the ones that are closest to Durham， North Carolina。

 So it looks like our earthquakes are sorted by their location from a specific place。 All right。

 happy coding。😊。