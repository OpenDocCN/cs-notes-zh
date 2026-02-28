# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p126 06_02_07_编写最近地震查询.zh_en -BV18U411U729_p126-

![](img/5f5c38ab6d08fb22ce82bd1ba5875059_0.png)

Hi， perhaps you'd like to know whether a specific location is a quake danger zone。

In this coding demo， we'll describe how to find the closest 10 earthquakes to where you live。

Or to a city where a friend lives。We'll write code for a specific location like New York City or Jakarta。

 Indonesia， but the code will work for any location。Our code will find the 10 closest quakes。

 but we'll be able to replace 10 with any number。You've solved a similar problem before。

 find the minimal or maximal element in a list of elements。 this is similar。

 we'll find the closest quake to a specific location。We'll then repeat the process， but first。

 we'll remove the closest quake from the data set。 Then the same algorithm will find the second closest quake。

 We'll need to remove the closest quake， but we don't want to change the list of quakes。

 So we'll need to make a copy to avoid removing quake data。And we'll use 10 and Jakarta。

 Indonesia in the demo， but you'll be able to find the 57 closest quakes to any city you choose。

The seven step process is implicit in what we're doing here。

Can you find the closest quake to a specific location。You've seen this algorithm before。

 finding the minimal or maximal element in a list。 We'll use the same steps here。

 We'll keep track of the index into an array list of the closest quake。

 The one with a minimal distance to Jakarta。 And each time we examine a quake entry。

 we update the closest index value， if we need to。

![](img/5f5c38ab6d08fb22ce82bd1ba5875059_2.png)

In solving the problem with paper and pencil， we'd cross out the minimal closest quake entry after finding it so that we could repeat the process and be sure we wouldn't find the same quake again。

In programming， we' remove the closest element to avoid finding it as we repeat the process of finding the closest quake。

 Let's write some code。As we look through the fine closest quakes method here。

 we see that we've created an earthquake parser on a array list of quake entries that we。

Filled with data using the parser， then。I've created a location variable named Jakarta。

 and I've used the latitude and longitude of Jakarta， Indonesia。I've called the get closest method。

 which is the one that we're going to write during this lesson。

I've passed it the list of data that I read from the parser。The location that I'm interested in。

 which is Jakarta and the number 10 so that I can find the 10 closest。



![](img/5f5c38ab6d08fb22ce82bd1ba5875059_4.png)

Earthquakes to Jakarta， Indonesia。The rest of the method here。Is based on printing out that data。

 If I run the program now by right clicking and saying find closest quakes。

We can see that data was read for 1，584 earthquakes from the USGS source， but none were found。

 and that's because I haven't yet written the method that we're going to write now。

 so let's look at that method。

![](img/5f5c38ab6d08fb22ce82bd1ba5875059_6.png)

The method we're going to write is get closest。We can see in get closest that it has three parameters。

 an array list of quake data。 That's the source of the data about earthquakes that we're going to use。

 The current location that in our demo is Jakarta， but could be any variable that you pass and how many。

 which is 10。

![](img/5f5c38ab6d08fb22ce82bd1ba5875059_8.png)

I'm going to write the code that you've seen before just to find the single closest entry。

 we've done that before， and we did that。By by tracking the minimal index。

 So I'm going to have a variable named Min index， which I initialized to 0。

 That's the location of the closest earthquake to where I am。

 And then I'm going to loop over all the other data by starting at one。

 going up to the parameter quake data。I will use its size。

And I'm going to look at each one of those entries。八。Obtaining the quake data from the array list。

Using the dot get method。And then I'm going to see if the current quake distance。Location。

 which is Jakarta。So this is called this is current。The Jakarta reference。 So I've used current here。

 which is not a good one。 So we'll just call this quake。 if quake is。Close to current。

 And if that's less than the distance from。My minimal index， which is Quakedata do get min index。

I'm working hard here to write this。Dot distance。2。Current， that's a long list to fit on that line。

 so I'm going to break the line to make it easier to read。

If the distance from the current quake here that I've read， Quake。

 if the distance from that to Jakarta is less than the distance from the smallest location to Jakarta。

Then I need to remember a new minimal distance， and so I will reset。

The distance the minimal index variable。2 k。When I'm done， I need to make sure that I store。

In my return array， the location。That's closest to Jakarta， which I get from saying quake data。

Dot get min index。Let's see if this code compiles。There is no distance to method。

That's because I've forgotten the name of the method。 So I will use the handy control space。

 which tells me that。The names of all the different functions that I can use on the location variable。

 And we can see here that that is the quake entry class。

 And I've made the canonical mistake of forgetting that I need the location variable。

 not just the current quake， but I need the quake location。 So I will set location。

To quake do get location。And then I will use Lo。Dot distance 2。And。Get。Location dot distance 2。

 That's a mouthful。 So I'll go over it to make sure once it's compiled。 the program has compiled。

 and I will now run through it very quickly to make sure we're all on the same page。

My minimal index will remember where in the。Aray list quake data。 My closest location is。

As I loop over all the data， I get the quake entry。Sttored in variable quake。I use quake。

get location。To get the location of the current one I'm iterating over。

And then I'm comparing the distance from that location。

 which is the one I'm iterating over in this loop。I compare it to the closest quake I've seen so far。

 that's what Min index is， the closest quake I've seen so far。

And I do that by asking if this distance is less than。The distance to current which is Jakarta。

 Then I will remember and reset Min index。 If I run this program by coming out here。Right clicking。

 creatingating a new object。And then invoking the find closest quake。

I will see that the closest quake found。Is 223 km from Jakarta， And this is where it is。

 It found one。 If I want to find the 10 closest quakes。

 I'll simply need to take this loop that I've done here。



![](img/5f5c38ab6d08fb22ce82bd1ba5875059_10.png)

And put that in another loop that iterates how many times。I can do that simply。

By putting a for loop around this。Let me make sure that that is down here。And taking all this code。

And indenting it。Let me just make clear what I've done。This is the code I'd already tested。😡。

That loops through all the arrays。Quake entry objects finds the smallest one。

And adds it to the variable I'm returning。If I repeat this over and over again。

 I'll find the closest quake， then the next closest quake， and then the next closest quake。

 The only problem is， once I found the closest quake， I'll keep finding it over and over again。

 We can see this。By running the program。Find the closest quakes。

And we see we found the same one over and over again。 not surprising。 We found 10。

 but we kept finding the closest one。 That's a simple thing to fix。 After we find it。

 we simply remove it。From quake data。 So array lists have a remove element。

 and I will simply remove the element after I get it。 So quake data remove min index。

After I've obtained the closest quake， I'll remove it， so I never find it again。

Compiled that program。Create a new closest quake object。And。😔，Find the closest 10 quakes。

I can see here I found one quake that's 223 kilometers away and the 10th closest quake。

 which is more than 2000 kilometers away。 I'm reasonably confident my program works correctly。

 I'd like to verify that by running it through some real data。

The only problem I have is that right now after finding the10 closest quakes。

 I've removed them from quake data， that would be a simple fix to make。

 create a copy of quake data and use that copy。To show you how that would work。

 I'd simply say create a qua entry。Name copy， make a new array list。

And construct that from quake data。Now simply used copy。Everywhere in my code。

 instead of using quake data。 so that I know I'm not modifying my parameter。

 instead of quake data dot size， I'll use copy dot size instead of quake。



![](img/5f5c38ab6d08fb22ce82bd1ba5875059_12.png)

Data dot get。That one's fine down here。 I'll use。Copy， and here I'll use copy。

When I compile that program， there are no syntax errors。

 I want to make sure I'm not using quake data anywhere， I'm looking through my code， I've used copy。

 I've used copy， Quake data， I need copy there。

![](img/5f5c38ab6d08fb22ce82bd1ba5875059_14.png)

![](img/5f5c38ab6d08fb22ce82bd1ba5875059_15.png)

And now I'm set to go。One last run。Find the closest。And there they are。

 I found 10 closest quakes to Jakarta， Indonesia。Let me just remind you of what we did there。

 I took my standard code for finding the closest。Quake to one that was specified by the parameter current。

And once I tested that and found one。I took that code and added this loop around it so that I could repeat it this many times。

 how many？I then realized I was modifying my parameter and so I made a copy。Happy programming。

 don't get too close to an earthquake。