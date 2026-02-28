# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p142 22_03_04_Comparator接口.zh_en -BV18U411U729_p142-

![](img/1117d480df6f793e0f594fc9d4eee9a6_0.png)

Finally， I've carefully designed and implemented a compare two method that will compare my quakes from south to North Pole order。

We can use that to sort the quakes for my important project。 Hey， wait， a gosh darn minute。

 This isn't right。 Somebody changed my compare two method。 Yeah。

 I needed to sort the quakes by magnitude from my problem。 So I change the code。

 I'm sure magnitude is a better way to order quakes anyways。

 It's way more important how strong they are。 But you just broke my code。

 I need to solve problems where they are ordered by latitude。 Wait。

 I don't like either of those ways。 I want to order the earthquakes by how far they are away from me。

 This is about me。 that way I can solve useful problems。

 like finding the closest earthquake or how many quakes are within a given distance of my house。 No。

 no， no， no， no。 I don't like any of these orings。 We should order quakes by time。

I want to analyze earthquake activity over time， so I need to know which are recent and which happened a long time ago。

 Okay， clearly， we cannot keep changing the compared to to satisfy all the different ways people want to order their earthquakes。

 Instead， we need another approach。 a way to specify an alternate ordering。Fortunately。

 Java has an interface for exactly this purpose， comparator， which sounds a lot like comparable。

 but is different。 The comparator interface allows a class to define orderings for some other class while the comparable interface allows a class to define its own natural ordering。

 The comparator interface promises one method compare， which takes two parameters。

 the things to be compared。😊。

![](img/1117d480df6f793e0f594fc9d4eee9a6_2.png)

Before we see an example of a comparator， it's helpful to understand how it's different from comparable。

 They seem to do pretty much the same thing Here， you can see two earthquakes。 quake 1 and quake 2。

 If you do quake1 dot compare to quake 2 using the dot Comp2 method promised by comparable。

 then you are asking quake 1 to compare itself to quake 2。

 The compare2 method lives inside of one of the objects being compared。

 The method inside of quake 1 will then look at the information it needs from itself and from quake 2。

 For example， their magnitudes。 and then make the comparison。



![](img/1117d480df6f793e0f594fc9d4eee9a6_4.png)

Now let's look at comparator here you can see the same two earthquakes。

 but now we make another object to compare them comparator a。

 When you do comparator a do compare quake1 quake2。

 you are asking this object Comparator A to compare these two quakes。

 The code for the dot compare method lives inside of this third object。

 not either of the ones being compared。 This code inside of comparator A gets the information it needs from the two quakes。

 This comparator looks at their location and compares them based on their distance to its location。

The benefits of comparators are that you can create some other comparator。

 such as comparator B here and ask it to dot compare the quakes。

 Comparator B could be a different type with different code in its dot comp method from comparator A。

 For example， it could look at their dates and order them based on which happened more recently。

 This is how we can solve the problem of everyone wanting to sort their quakes differently。

 Everyone can make a different class which implements comparator and use it。

So what would such a class look like here you can see an example of a comparator which orders earthquakes by their magnitude。

 noticeice that the class implements a comparator of quake entry this class can be used to compare two quake entries to each other here you can see the compare method promised by the interface as the interface promises it is public and returns an int。

Since this class implements comparator of quake entry。

 the interface promises that the parameters will be quake entries。

 The body of this method compares the two quakes by their magnitudes。

 This code is very similar to the compare two method that we change to compare by magnitude。

 The difference is that this method gets the magnitude out of both of its parameters。

 While the compare two method， got the magnitude out of its one parameter and out of the object that it lives inside of。



![](img/1117d480df6f793e0f594fc9d4eee9a6_6.png)

![](img/1117d480df6f793e0f594fc9d4eee9a6_7.png)

Now that you have seen an example of how to write a comparator。

 let's take a look at how to use a comparator to sort the collections do sort method can take a second parameter。

 which is a comparator When you pass this second parameter to collections do sort。

 it will use that comparator to determine the ordering of the object in the list。

Here we are passing in a new magnitude comparator。Remember that when a methodss parameter type is an interface。

 you can pass in an instance of any class that implements that interface here。

 magnitude comparator implements comparator， so it is fine to pass it in for this parameter。

 As you learned earlier， the code inside of collections do sort we'll call the right dot compare method based on what type of comparator is passed in by using dynamic dispatch。



![](img/1117d480df6f793e0f594fc9d4eee9a6_9.png)