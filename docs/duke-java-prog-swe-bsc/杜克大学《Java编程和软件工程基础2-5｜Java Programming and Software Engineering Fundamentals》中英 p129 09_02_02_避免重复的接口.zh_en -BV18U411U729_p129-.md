# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p129 09_02_02_避免重复的接口.zh_en -BV18U411U729_p129-

![](img/2b3ec9b84ffd4411a18ce38eb7d42ce6_0.png)

系。To start， let's take a look at two filter methods you might write and see the similarities between them。

Here is a method that filters earthquakes by their magnitude。

 placing only those with at least a certain magnitude in the answer。

There's nothing special about the fact that we wrote public array list quake entry on a separate line from the method name。

 It just makes it easier to fit on the screen。 The line break is not important to Java or to most other programming language。

This method proceeds in a straightforward way。 It simply makes an empty array list for the answer。

Then has a for loop to examine each earthquake in the input parameter array list。

And for each quake that matches its criteria， the magnitude being at least magmin。

 that quake is added to the answer array list。 You might have written this exact code if you applied the seven steps to this problem。

Here's another method which filters earthquake by their distances from a particular location。

Notice how similar it is to the previous code， in fact， there are only three differences。

The method name has been changed to reflect the task that this method does。

The parameters are different。 This one takes a maximum distance and a location。

 whereas the magnitude filter only took a minimum magnitude。

And the condition to decide whether to add the current earthquake being iterated over to the answer array list is different。

Whenever you have this much similarity in code， you might want to find a way to avoid duplicating the code。

In particular， whenever you find yourself wanting to copy and paste code， and then to make changes。

 you should generally think about whether there's a different approach。

Here you can see a different and better approach。 This method is a generic filtering method。

 which takes a parameter， filter F that specifies how to determine if a particular earthquake should be included in the output list or not。

The code then calls F dot satisfied on each of the earthquakes being iterated over and uses the return method of dot satisfied to make a decision as to whether the earthquake is included。

This approach looks great， but you are probably wondering how do you make filters with different dot satisfies method？

The answer is that filter is an interface， not a class， you can see its declaration here。

Notice how the declaration says interface。Where you would normally write class。

Writing interface here， instead of writing class tells Java that filter is not a class。

 but is an interface， instead of defining the behavior of methods， an interface is just a type。😡。

A type that promises that certain methods will exist in all classes which implement the interface。

Here， the filter interface promises one such method。 Public Boolean satisfies Quake entry Q E。

Once you have declared an interface， you can write classes that implement it。

When you write a class that implements an interface。

 you must define all of the methods promised in the interface specification。



![](img/2b3ec9b84ffd4411a18ce38eb7d42ce6_2.png)

Objects of the class can then be treated as the interface type。

If you write a class that implements filter， objects that you make from that class can be assigned to variables of type filter。

😡，Or pass as parameters to methods that expect a filter。 Let's look at an example。

Here's the Minmag filter， a class that checks if an earthquake has a minimal magnitude。

You can see the declaration of this class says implementples filter。 When you write this。

 Java will check and make sure the class has all of the methods promised by the filter interface。

 If one's missing， the class won't compile。😡，This allows you to treat midbank filter objects as filters in the code you write。

Here you can see where this class has the promised dot satisfies method。

 The method simply checks that the past in earthquake's magnitude is greater than equal to magmin。

 the minimum magnitude which is stored in an instance variable of the object。

Notice how similar the body of this method is。To the condition you saw earlier when we looked at the code that filtered by magnitude。



![](img/2b3ec9b84ffd4411a18ce38eb7d42ce6_4.png)

This class can also have other members beyond a specified method。

Here there's an instance variable to hold the minimum magnitude。😡。

And a constructor which initializes that instance variable from its parameters。

These aren't promised in the filters specification。If needed。

 you could write other methods in the class too， you just must writeSfies。😡。



![](img/2b3ec9b84ffd4411a18ce38eb7d42ce6_6.png)

At the top， you can see the code we wrote earlier for the generic filtering method at the bottom。

 you can see how you can assign a min Mag filter object to a filter variable and pass it to this method。

The right hand side of this first assignment statement makes a new minm filter passing in 4。0。

 It creates an object whose dot satisfies method will test if an earthquake's magnitude is at least4。

 The object has type min mag filter。 The left hand side of this assignment statement is a variable of type filter。

 Even though the types are not the same。 This assignment is legal because minm filter implements the filter interface。

 The next line passes F， which is the object to filter by， which is a magnitude at least four。

 to the generic filtering method you saw earlier。If you had another class that implemented filter such as distanceance filter。

 you could assign an instance of distance filter to the variable F as well。



![](img/2b3ec9b84ffd4411a18ce38eb7d42ce6_8.png)

And then you would find out if your world。Is being rocked by quake。



![](img/2b3ec9b84ffd4411a18ce38eb7d42ce6_10.png)

Close to you。I'm feeling my earth move right now under my feet。



![](img/2b3ec9b84ffd4411a18ce38eb7d42ce6_12.png)

Happy programming。

![](img/2b3ec9b84ffd4411a18ce38eb7d42ce6_14.png)