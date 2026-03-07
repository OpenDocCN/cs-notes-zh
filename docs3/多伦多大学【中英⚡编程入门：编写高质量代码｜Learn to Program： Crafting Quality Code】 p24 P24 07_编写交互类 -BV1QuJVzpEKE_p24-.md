# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p24 P24 07_编写交互类 -BV1QuJVzpEKE_p24-

You now know how to create your own types Next we're going to create two types that are related to each other。

I've already defined a song class， it has an artist， a title。

 and a duration measured in minutes and seconds。

![](img/9ade050f4701ae106a1a289353c2ece5_1.png)

![](img/9ade050f4701ae106a1a289353c2ece5_2.png)

In addition to the constructor， there's one more method that returns to the string representation of the song。

At the bottom of the file， there's the little program that uses this type。

 it creates two songs and prints them。

![](img/9ade050f4701ae106a1a289353c2ece5_4.png)

![](img/9ade050f4701ae106a1a289353c2ece5_5.png)

Now we'll define a playlist class to keep track of a playlist of songs。

We'll begin by defining the constructor， which sets the title of the plainlist。Initially。

 the playlist won't contain any songs。Let's add an example to the do string。

The title will be passed as an argument to the constructor。Initially。

 the playlist won't contain any songs， and we're going to use a list to represent the songs in the playlist so that list will initially be empty。

To implement this， we create the two instance variables， title and songs。Next。

 we'll define an add method that will add a song to the playlist。It will have two parameters。

 the playlist and song。And we're going to need to use that song type that we created earlier。

The song class is in Somed do pi， so we need to import the song module， lowercase SONG。

Then we need to specify that the class definition can be found in the module song。

Now we've got the song and we're going to add it to this playlist using this new method。

Song's instance variable is a list， so we'll use the append method to append the song to the list。

Finishing off the example in the Dot， we expect the first song in the Canadian artist playlist to betoumpba。

Before writing any more code， let's take a moment to run the doctors。

No news means that the tests have passed。Now let's write a method called get duration。

 it's going to return the length of the playlist measured in minutes and seconds。For the example。

 we start by creating a playlist。And then we'll add two songs to it。

And get the duration of the playlist。 The total length of the playlist is the sum of the length of the two songs。

 So this playlist is 8 minutes and 18 seconds long。We're going to use two accumulators。

 one to keep track of the total number of minutes for all songs in the playlist。

 and another to keep track of the total number of seconds。

We'll look up a song's length using its minutes and seconds instance variables。

So for each song in the playlist， list of songs， we'll look up that song's instance variables。

 minutes and seconds， and add the values that they refer to to the total minutes and total seconds。

After we add each song's duration to the total duration。

 we want to return the number of minutes and seconds， but it's not quite so simple。

s possiblessible that when we sum the length of the songs in the playlist。

 that the total number of seconds ends up being greater than 60。

Imagine that we have a long playlist and the total number of seconds is 135。

That's equivalent to two minutes and 15 seconds。If we take 135 and divide it by 60 using integer division。

 that gives us the two minutes part。And then if we take 135 modd 60， that gives us the 15 seconds。

Rather than simply returning total minutes and total seconds。

 we'll take the number of seconds and add any full minutes to the total number of minutes。

And take the remainder， which will be a value between 0 and 59。

 and return that as the number of seconds。Last but not least。

 we' implement the underscore underscore stern method to。

Generate a string representation of the playlist。It will include the title of the playlist and its duration。

 as well as the name of each artist， the song titles and their durations。

The only argument that this method takes is the playlist。And it returns a string。

The first line of the string contains the playlist title and its duration。

 so begin by calling the get duration method。That returns a topple with minutes at index0 and seconds at index 1。

We want the string representation of those numbers。Also。

 seconds could be a single digit or a double digit number。

We'll use a method called our adjust to make sure that the second string will always have a length of two。

If right now the number of seconds is a single digit， then a zero will be placed to the left of it。

 creating a two digit string。If the string already has a length of two。

 then the R just method simply returns that string。So we'll call our just on the second string。

Now we'll start to accumulate the string representation using the result variable。

And it will initially contain the title and the duration of the playlist。Next。

 we need to add each song from the playlist， its artist， title， and its duration。

We can loop over each song in the list of songs。And add the string representation of the song to the playlist。

We'll put a new line character before each song so that each song's description will appear on its own line。

Let's add one more thing to our string representation。

We'll add the song number so that we'll know which order the songs appear in the playlist。

The variable song nom will refer to the song number for the song about to be added to the string next。

We'll add the song number to this string， along with a period and a space。

 and we'll thencatenate that to the song's information。Next。

 we increment the song number before moving on to the next song in the list。

Once we've built up the string， we can return the result。

Let's put everything together and write a little program to print a playlist made up of three songs of Canadian artists。

The call on print uses the stringern representation of the playlist， so we'll see the playlist title。

 its duration， and then information above the three songs in the playlist in the order that they were added to the playlist。



![](img/9ade050f4701ae106a1a289353c2ece5_7.png)