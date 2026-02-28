# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p123 03_02_03_类之间的关系.zh_en -BV18U411U729_p123-

![](img/b0cb96dc31afe4eaf77195a6c96a44ec_0.png)

Hi， in this lesson， we're going to talk about a few concepts related to how classes are used together in object oriented programming in general。

 and specifically when using Java and the earthquake programs and classes you'll see。



![](img/b0cb96dc31afe4eaf77195a6c96a44ec_2.png)

![](img/b0cb96dc31afe4eaf77195a6c96a44ec_3.png)

![](img/b0cb96dc31afe4eaf77195a6c96a44ec_4.png)

The Quake entryry class created in Quakeentry。java encapsulates the basic characteristics of one earthquake。

Where the quake occurred， the quake's magnitude and depth。And a title for the quake。

This makes quake entry what's called a pojo or plain old Java object。

 This means a quake entry object is not much more than the characteristics of the earthquake。

Creating a quake entry object requires providing all of these characteristics。 For example。

 it doesn't make sense to talk about an earthquake without knowing where it occurred or how strong it is。



![](img/b0cb96dc31afe4eaf77195a6c96a44ec_6.png)

![](img/b0cb96dc31afe4eaf77195a6c96a44ec_7.png)

It's not possible to create a quick entry object without supplying all the parameters to the constructor。

 which makes this different than what some consider a plain old Java object or Pojo。As we'll see。

 quake entry objects are created when data for earthquakes is read and parsed。

 Cating a quake entry object requires supplying all the information for a quake， the latitude。

 the longitude， the magnitudeitude， the title， and the depth。

A quake entry object represents the data for an earthquake that has occurred somewhere in the world。

 So it's immutable and doesn't change once constructed。

Accessing the state of a quake entry object is done using getter methods， as you see here。

Get location returns the location of a quake。Get depth， returns， the depth of the quake， and so on。

A quake entry object also has a reasonable dot two stringing method to help with printing information about an earthquake。

An earthquake occurs at a specific location， and so we'll use a location class for that。



![](img/b0cb96dc31afe4eaf77195a6c96a44ec_9.png)

Location classes have many uses outside of the quake entry class。 we're studying here。

 smartphones use locations， Web browsers use locations and many other applications do as well。

We have a choice between creating a location class that's simple that we could use and study for this course。



![](img/b0cb96dc31afe4eaf77195a6c96a44ec_11.png)

Or we could use an industrial strength class that would be tested and useful in other contexts。

We have adopted the location class from the Android platform。

 This gives us the best of several options。 We can be confident that the class is well tested。

 and the licensing of the source code allows us to use and adapt the code as we need to。

 We'll see more about this later。

![](img/b0cb96dc31afe4eaf77195a6c96a44ec_13.png)

Location objects are created from a latitude and a longitude。 These specify one location on earth。

Typically， these values might come from your phone。

 which get data from GPS satellites or your web browser。

 which can determine location based on your IP address。

The Android location class has a dot distance 2 method to determine the distance between any two locations。

 A and B。 This will allow you to find earthquakes close to where you live。

This makes the location class more than a plain old Java object or Pocho。It has state。

 the latitude and the longitude， but it also has behavior。

 a method to determine the distance between locations。

Classes in Java can have both Ha and uses a relationships。

 The earthquake parser class creates quake entry objects when data is read and parsed。

 This blue Jay class diagram shows how the parser uses quake entry objects by creating them。



![](img/b0cb96dc31afe4eaf77195a6c96a44ec_15.png)

A quake entry object also creates a location object as seen in the diagram。



![](img/b0cb96dc31afe4eaf77195a6c96a44ec_17.png)

The Quake entry class creates a location object by passing the latitude and longitude to the location object。

This creates a new location object using these data。

The location object created is stored in instance field My location。

 When one class has a or contains another class， we call this a H relationship。

 The location class implements comparable。 We'll discuss this at another lesson。



![](img/b0cb96dc31afe4eaf77195a6c96a44ec_19.png)

![](img/b0cb96dc31afe4eaf77195a6c96a44ec_20.png)

![](img/b0cb96dc31afe4eaf77195a6c96a44ec_21.png)

As you can see in the Blue Jay diagram， the earthquake client class also uses a location object。

 Loations are used to determine which earthquakes are closest to where you live or to where I live。

 We'll see this in a coding demo。The location dot distance2 method helps in writing this code。

A quake entry object is also used by the earthquake client class。 For example。

 this allows client programs to find all quakes of high magnitude using the get magnitude method of the quake entry class。

 happy programming。

![](img/b0cb96dc31afe4eaf77195a6c96a44ec_23.png)