# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p174 2_01_04_读取与存储数据.zh_en -BV18U411U729_p174-

![](img/482fb728fd9fefc55aed4662e1688247_0.png)

Let's discuss how the rating data for creating recommendations about movies is stored and accessed in the programs that you'll be writing。



![](img/482fb728fd9fefc55aed4662e1688247_2.png)

![](img/482fb728fd9fefc55aed4662e1688247_3.png)

You'll be creating a sequence of recommendation programs as part of this capstone。

 The first step in creating programming recommendations is to get data about items that can form the basis of the recommendations your program will generate。

 you will need to write programs to read the data into structures your program can access and process to make recommendations。

 Although you won't be using Yelp or Netflix data to generate your recommendations。

 you will be using Twitter data about movie recommendations to write your own recommender program。

You'll do this as part of a sequence of exercises we've designed for this capstone。

 You'll be using programming and design concepts from all of the courses you've taken as part of this specialization to create these capstone Java programs。

 You'll have access to a large number of ratings for thousands of movies。



![](img/482fb728fd9fefc55aed4662e1688247_5.png)

You'll be using recommendations for movies that have come from Twitter posts via a project calledMovie Tweetings。

 We've curated the data to provide a good learning experience for this capstone。



![](img/482fb728fd9fefc55aed4662e1688247_7.png)

![](img/482fb728fd9fefc55aed4662e1688247_8.png)

You can get access to all of the data from the website associated with this URL。

 all the data will be updated frequently based on new tweets。



![](img/482fb728fd9fefc55aed4662e1688247_10.png)

The data you'll use is stored in CSV files， so you'll be using the packages from the Eduu。

duke librariesr and Apache CSv project to access this data。



![](img/482fb728fd9fefc55aed4662e1688247_12.png)

![](img/482fb728fd9fefc55aed4662e1688247_13.png)

You'll read the data and store the rating movie data in collections your program will access to create recommendations。



![](img/482fb728fd9fefc55aed4662e1688247_15.png)

![](img/482fb728fd9fefc55aed4662e1688247_16.png)

You'll start with simple storage techniques， and as you create more sophisticated recommendations。

 you'll use more efficient data structures using the software design principles you've learned in this specialization。

You'll use plain old Java object or Pojo to store the movie data。



![](img/482fb728fd9fefc55aed4662e1688247_18.png)

The movie。java class mirrors the CSV file storing the movie data。



![](img/482fb728fd9fefc55aed4662e1688247_20.png)

![](img/482fb728fd9fefc55aed4662e1688247_21.png)

That CSV file contains one line of comma separated value data for each movie。



![](img/482fb728fd9fefc55aed4662e1688247_23.png)

The text shown here is a single line in the CSV file。

 Each line of the CSV file stores eight items of information about each movie。



![](img/482fb728fd9fefc55aed4662e1688247_25.png)

The first item is an IMDB or Internet movie database ID number for the movie。

The title of the movie is the next one on the line， followed by the year in which the movie was made。

The country in which the movie was made， though， sometimes there is more than one country。

Then the genre of the movie such as comedy， A， adventure， horror or more。

There can also be more than one genre listed with the movie。Then they're the movie's directors。

 followed by the length of the movie in minutes， this movie lasts about 126 minutes。And then finally。

 a URL for a poster image of the movie， such as the one you see here for the drama Goodwill huntinging。

 created in 1997。You'll read the CSV file and use the Pojo class we've created to store data for each movie。

The movie。 Java class has a constructor and several getter methods for accessing data about the movie Once a movie object is created。

 it doesn't change。The get methods include get title， get ID， get year。

 and more to access information about each movie you'll read this data using theedduu。

du file resource class and the Apache CSV parser you've had practice with using。

In addition to movie data， you'll need data rating each movie。



![](img/482fb728fd9fefc55aed4662e1688247_27.png)

Another CSV file will store ratings for many movies。

 These ratings have been curated from the Twitter posts。



![](img/482fb728fd9fefc55aed4662e1688247_29.png)

Each line in the CSV file stores data for one rating that is one rate on Twitter writing about a specific movie。

 Each line stores an ID for the person creating the rating。

 the IMDB movie ID for the movie being rated， and the rating given to the movie on a scale of 1 to 10。



![](img/482fb728fd9fefc55aed4662e1688247_31.png)

![](img/482fb728fd9fefc55aed4662e1688247_32.png)

![](img/482fb728fd9fefc55aed4662e1688247_33.png)

![](img/482fb728fd9fefc55aed4662e1688247_34.png)

The CSV file also stores information about the date and time。

 but we won't use that number in the recommendations you'll be creating。



![](img/482fb728fd9fefc55aed4662e1688247_36.png)

![](img/482fb728fd9fefc55aed4662e1688247_37.png)

The movie ID is key in obtaining information about the movie being rated。

 It can be used in the data structure you'll create when reading the movie CSV file we've already discussed。



![](img/482fb728fd9fefc55aed4662e1688247_39.png)

![](img/482fb728fd9fefc55aed4662e1688247_40.png)

The Raer class supports several operations， so it's more complex than a pojo。

 which would support only simple get operations。

![](img/482fb728fd9fefc55aed4662e1688247_42.png)

You'll be able to determine if the rateer has provided a rating for a specific movie that's a parameter to a boolean method has rating。

You'll be able to obtain the rating for a movie specified by a movie ID using the method get rating that returns a double。

You'll be able to add a rating which you might do when reading the rating data CSV file， for example。

And you'll be able to get all the movie IDs rated so you can write code to iterate over all movies with ratings。

See the Ra。t Java class file for details。Let's summarize the three classes you'll be using to read and store data to create recommendations。



![](img/482fb728fd9fefc55aed4662e1688247_44.png)

You'll use movie。 Javava， Ra。java and rating。 Javava in creating programmatic recommendations by reading CSV files and storing data in a list in this first part of the capstone project。



![](img/482fb728fd9fefc55aed4662e1688247_46.png)

![](img/482fb728fd9fefc55aed4662e1688247_47.png)

![](img/482fb728fd9fefc55aed4662e1688247_48.png)

The Raer Java class stores movie ratings for one Raer， this might be ratings for several movies。



![](img/482fb728fd9fefc55aed4662e1688247_50.png)

![](img/482fb728fd9fefc55aed4662e1688247_51.png)

Each of these rating objects stores the movie ID and the rating for that movie in an instance of the rating Java class。



![](img/482fb728fd9fefc55aed4662e1688247_53.png)

This makes both movie。Java and rating。Java Pojo classes。

Each has a constructor to create an object and get methods to access information about the movie or the rating。

The Raer not Java class supports queries about ratings made by one Raer。

 like what movies have been rated and what the rating for a specific movie is。

That's an overview of the first part of the capstone project。

