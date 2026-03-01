# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p131 11_02_04_MatchAll接口.zh_en -BV18U411U729_p131-

Suppose that you wanted to make a filter for your earthquake data that combines several other criteria。

 For example， you want to find the earthquakes that are in a certain range of depths and close to a particular location。

 And at least a minimum magnitude。 You could just go and write one big， complicated filter。

 which would look like this。 It would have a big condition that adds together all of these criteria。

 It would also have a lot of instance variables and a constructor with a lot of parameters。

 which we don't show here。 This approach would work。 but it's not a great way to solve this problem。

 Why not。It duplicates code。 You already wrote and tested filters for each of these criteria。

 It would be much better to make use of those。 So if you already have filters that check each of these criteria。

 could you write another filter that combines them together， making use of their existing code。

To make the result even better， could you make this combined filter generic so that it could combine any set of filters and check if an earthquake matches a criteria for all of them？

If you could do this， you could write some code that looks like this。

 You can make a match all filter， the class we want to write。

 then add a filter for the minimum magnitude to it and then add a filter for the range of depths to it。

 and finally add a filter for the distance from a location to it。😊。

Then you could use this match all filter to filter your earthquakes。 This approach looks great。

 You can reuse the filters you already made， and if you want to combine other filters。

 you can use match all filter to do that。😊，But how do you write match all filter。

Here is half of the code for match all filter。 We'll see the method satisfies in just a second。

 It just doesn't all fit on this screen at once。Here you can see that we declared the match all filter class and said that it implements filter。

 This is just like you learned for any of the other filters you wrote。

 This class has a field for an array list of filters。 Can you make an array list of filters， you can。

 which is another great example of composability。 Filter is a type。

 and you can make an array list of any type。 So this works just as you expect。😊。

Next there's a constructor that initializes the array list to a new array list and a method that takes a filter and adds it to this array list。

Now， let's look at the code for the satisfies method in this class。

 Like all the filters we have seen， this satisfies method takes a quake entry and returns a buion。

 However， this filter makes its decision differently than the ones you have seen so far。

 rather than examining the earthquake itself。 It iterates over each of the filters in its array list。

😊，For each of these filters， it sees if this quake entry satisfies that filter's conditions。

 Remember that this call will be dynamically dispatched using the dot satisfies method inside whatever type of filter was actually created。

 If that filter returns false。 Remember， exclamation mark means not。 Then this filter returns false。

😊，After iterating through all the filters， if none of them rejected this quake。

 then this filter returns true。So now you have seen how to make the match all filter。

 which can combine any set of filters and see if an earthquake matches all of their conditions。

Its dot satisfies method is implemented by using a for each loop to check all the filters that it has stored in an array list。

 You could also write other combinations， for example。

 if you wanted to write a match anyy filter that tested whether an earthquake matched the conditions of any of a set of filters。

 you could do that with the same principles。😊。

![](img/d6c55e8edec12958e4547712f7eca401_1.png)

Have fun filtering the earthquake data in search of that ultimate quake。



![](img/d6c55e8edec12958e4547712f7eca401_3.png)