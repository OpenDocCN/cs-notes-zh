# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p176 4_03_02_推荐结果过滤.zh_en -BV18U411U729_p176-

![](img/e15599e34eacc2c4e18e208d847d1f24_0.png)

Hello and welcome to the next part of our capstone project。

 You'll leverage the power of Java interfaces to make things more efficient and more general while using software design principles you've seen before。



![](img/e15599e34eacc2c4e18e208d847d1f24_2.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_3.png)

You wrote code to find recommendations for all movies。

 although you could specify the number of raters used in calculating averages。

 using all movies is too general。 Suppose you just want recommendations for new movies like those after 2012。



![](img/e15599e34eacc2c4e18e208d847d1f24_5.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_6.png)

Or for action movies or romances or comedies。Or even for movies under two hours directed by Steven Spielberg。



![](img/e15599e34eacc2c4e18e208d847d1f24_8.png)

In this part of the capstone， you'll be able to get just such recommendations。 At the same time。

 you'll make the code more efficient for accessing movie information and rating information about movies。



![](img/e15599e34eacc2c4e18e208d847d1f24_10.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_11.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_12.png)

You'll use a hash map rather than an array list。 This will allow your program to find a movie given its ID immediately rather than looping through an array list in making your programs more general and more efficient。

 you'll be using Java interfaces， and you'll practice the open closed principle of extending the program while ensuring the modifications aren't externally visible whenever that's possible。

😡，The first modification you'll do is to refactor the Raer dot Java class。

Refactoring means you won't add new functionality， and you'll make minimal or no changes to the external interface。

 what's called the API of the existing class。

![](img/e15599e34eacc2c4e18e208d847d1f24_14.png)

Reeffactoracting is an important part of making code more readable， more efficient。

 and more maintainable。The current code in Raer。 Javava stores rating objects in an array list。

To find the rating for the movie， whose ID is 120-1607。

Or even whether there is a rating for the movie with that ID。The code in Raer。

t Javava loops over the array list of rating objects。



![](img/e15599e34eacc2c4e18e208d847d1f24_16.png)

This will be inefficient with thousands of Raers who each might rate hundreds of movies。

 so we'll work to change this approach while minimizing visible changes to other parts of the program that use Raer objects。

The first step in refactoring is to create an interface rather than a class。



![](img/e15599e34eacc2c4e18e208d847d1f24_18.png)

To create an efficient rate while minimizing other changes will first create this interface rather than a class。

We'll make a copy of Raer。t Java and we'll call it plain Ra。 Javava。

 We'll need to change the code in that class so the constructor is named appropriately。



![](img/e15599e34eacc2c4e18e208d847d1f24_20.png)

Then we'll create an interface out of Ra。t Java by removing the method implementations。

 leaving the interface you see here with just the method declarations。

We'll see what else needs to change in our recommendation framework after creating the Raer interface。



![](img/e15599e34eacc2c4e18e208d847d1f24_22.png)

Programs rely on Ra as a type in reading data and creating recommendations。

 that code will largely still work。

![](img/e15599e34eacc2c4e18e208d847d1f24_24.png)

The code to rate make recommendations， for example， calls has rating and get rating。

 those calls will still work。

![](img/e15599e34eacc2c4e18e208d847d1f24_26.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_27.png)

The code to read rating data will need to change。😡。

The creation of the Raer objects will need to use plane Ra in creation。

 but assign the reference to the new object created to a variable whose type is Rar。



![](img/e15599e34eacc2c4e18e208d847d1f24_29.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_30.png)

This single line is the only change needed to make the code work。

 We've minimized the changes to client programs by creating an interface。

 The program was open to extension with minimal modification。



![](img/e15599e34eacc2c4e18e208d847d1f24_32.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_33.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_34.png)

Now we can create an efficient Rar。 Java class and use this new version in the recommendation framework。

The interface will be the same， but has rating and get rating will be efficient because they'll search in a hash map for a rating ID rather than looping over an array list。

The only line we need to change is the creation of an efficient radar object。

 which is assigned to the Ra you see here。We've used an interface to make code efficient。

We'll use the filter interface to get better recommendations。



![](img/e15599e34eacc2c4e18e208d847d1f24_36.png)

You've seen an interface like this filter Java before in searching through earthquake data。

 We'd like to filter movies like getting those created after 2012 or those over three hours long or those that are action adventure movies。



![](img/e15599e34eacc2c4e18e208d847d1f24_38.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_39.png)

How will we create filters like the year after filter shown here？Or a genre filter shown here。

These constructors look minimal， but well need to think about how the satisfies method works。

In a filter class that you implement。How will the Saisfies method look up a movie given the movie's ID。

 to determine if the movie meets the filter specification。

 like whether the movie was created after 2012？The year here is an instance variable。

 but how will the movie with a given ID be accessed？

Access to movies must be given via a filter's constructor or access some other way。

To keep things simple and efficient， we'll create and use a movie database class that allows efficient queries given a movie Id。

This will be both efficient and easy to use in our filter classes。

 as well as by the other classes in our recommendation framework。

The class movie database is an efficient， though simple class that helps in writing code to access movie information。



![](img/e15599e34eacc2c4e18e208d847d1f24_41.png)

The class is designed to be easy to use， but also very efficient in these ways。

 it's similar to a simple database。

![](img/e15599e34eacc2c4e18e208d847d1f24_43.png)

The same concept is used in efficient radar in which a movie's ID is a key in a hash map to access movie information used in the movie database class。



![](img/e15599e34eacc2c4e18e208d847d1f24_45.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_46.png)

The movie ID is the key， but now the movie is the corresponding value rather than a rating。

 as was the case in efficient rate do Java。

![](img/e15599e34eacc2c4e18e208d847d1f24_48.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_49.png)

All the methods in the movie database class are static。

 so no movie database objects are created using new。 Instead。

 access to movies is provided via static methods， just as math that square root and other math functions are used without creating a math object。



![](img/e15599e34eacc2c4e18e208d847d1f24_51.png)

Conceptually， the class is like a real database， supporting queries based on movie Is as keys and returning one movie are all those that satisfy or pass a filter。

When you've made all these recommendations， you'll have used filters， interfaces。

 and created efficient database classes。

![](img/e15599e34eacc2c4e18e208d847d1f24_53.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_54.png)

In the new recommendation framework， movies won't be accessed via an instance variable that's an array list of movie objects as you did before。



![](img/e15599e34eacc2c4e18e208d847d1f24_56.png)

![](img/e15599e34eacc2c4e18e208d847d1f24_57.png)

Instead， the static movie database dot filter by method is used to get all movie Is that satisfy a filter。

 This method returns an array list of movie Is。To get all movies。

 you'll pass a filter that always returns true。 so every movie satisfies this filter。

In the code you start with， this is the true filter class。

You'll be able to get other kinds of recommendations by looking for averages of something like romance movies created on or after 2012。

You can create a year after filter， for example， as shown here。And a genre filter， as shown here。

 to find romance movies。Then these filters can be added to an all filters object that combines several filters into a single filter。

After adding the genre filter and the year filter， the average recommendations shows romance movies on or after 2012。

 as seen in this list of recommendations。These recommendations are generated by using the power of Java interfaces and refactoring code to help ensure that already tested programs continue to work even in new contexts。

Adding more efficient code is an extra bonus here。Happy programming。

