# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p135 15_03_04_代码实现.zh_en -BV18U411U729_p135-

![](img/8f186a6c3766310207a681c2ba4b2d1b_0.png)

Okay， so now you've developed the algorithm to sort earthquakes by magnitude。

 it's time to turn that into code。Here we've declared a method sort by magnitude which takes an array list of quake entries as its input and returns an array list of quake entries as its output。

 having written this over two lines doesn't make a difference it was just getting really long。

So the first thing we said to do was out starts as an empty array list。

 so we want array list of quake entries。Out is going to be a new array list。Of quake entry。

And then we said as long as in is not empty。 so remember。

 we talked about how a while loop is the most appropriate kind of loop for this type of repetition。

We want to know if n is not empty， so we might write something like n dot size is greater than0。

 but it turns out if we look at the documentation for array list。

 this is just the Java documentation for array list， we'll see that it has and is empty。

 which returns true if it contains no elements， so it would be a little better to just write。

As long as it's not empty。We want to find the smallest element and call it min element。

 so min element is going to equal something， we need to declare min element， it's a new variable。

 what type of thing would it be， a quake entry。

![](img/8f186a6c3766310207a681c2ba4b2d1b_2.png)

And。Finding the minimum element seems a little bit complicated。

 So we should write a method to do this。 We've already written one before Git smallest magnitude。

 which takes an array list of quake entries and returns a quake entry。

 This should be a very familiar computation to you by now。

 since you found the min and Mac of several different types of data across these past courses。

 So we're just going to make use of Gi smallest。Magnitude。

Which is going to take in and return minimumma。Now we want to remove that from in。

 so in dot remove min element。Again， if you weren't sure of this。

 you could look at the documentation and find that it has removed。Method in there。

And then we want to add min elements to out。t and min element， which will put it on the back。

 which is exactly where we want it， and then at the end out is our answer， return out。

So we're going to hit compile here， there are no errors， so that's good。

 We've already written a method here that will test this by reading in some data。

 sorting by magnitude， and then printing the result。 So if we go over here。

To our main blue Jay window。 And we make a new quake sort。And then we do test sort。

You'll see it printing out all of these different quakes。 And if you look at the magnitudes of them。

 you'll see。Starting up here at the top， there are lots of earthquakes。

The magnitudes are all very small， and as we go down。

 they get bigger and bigger and bigger until we get to the biggest earthquakes at the end。

 So we've sorted our earthquakes by magnitude， which is exactly what we wanted to do。

