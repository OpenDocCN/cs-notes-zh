# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p141 21_03_03_按震级排序地震.zh_en -BV18U411U729_p141-

![](img/7fa12c1f118e39ad2fda2cd186835f0b_0.png)

Hi， we're going to sort some earthquake data so that we can have a better understanding of。

What the quake data means are there powerful earthquakes， less powerful earthquakes。

 Are there earthquakes close to where we are and more， So I've got quake sorter demo。

 which is a very simple program。 I'm creating a parser。

 I'm opening up the data file that we've already saved。 I'm going to fill that data file。

 I'm going to read that data file and fill the list with quake entries。

 I'm going to call collections do sort， which is a very fast builtin sorter in the Java do ule package。

 and then I'm going to print out the entries。 So I've got my quake sort demo。

 I'm going to create a new object。And then I'm going to run the test sort。Now。

 that's a lot of earthquake data。 And as I look through。

 I was hoping that we would have the earthquake data so that I could see the powerful quakes that had a high magnitude and then the less powerful quakes earlier。

 But as I scroll through here， I see I've got 4。4 here and 5。3 here。

 This quake data is kind of all over the map。 And now I realize that looking over here。

 it's the latitudes of the quakes that are increasing。 So I've sorted from the south polele。

 which is a very low latitude all the way to the quakes that might be near the North polele。

 And we can see that， for example， that at this quake， whose latitude is 66。

 they're all up near Alaska。 So this is not the way I want to sort。

 I want to sort based on magnitudeitude。 So I'm going to have to go into the quake entry class。

 because as you know， the。Objects being sorted implement a comparable interface。

 So I can see here that quake entry implements comparable。That's right here。

I'm going to look at that compare two method。And I can see that this quake entry is sorting based on the latitude and the longitude。

 and that's not what I want。 What I want to be able to do is sort by magnitude。

 Now I'm going to have to modify the quake entry class。

 which means I'm going to lose the functionality had here。

 so I should make a copy of this code to make sure that I don't lose this sort by latitude functionality。

 And in the next lesson， we'll see that we can sort by many different ways at once。

 but not using the techniques I have here， which is simply change and compare to。 So I'm going to。

Comment out all of this code， which， as a reminder， returns a negative  one or a 1 or a 0。

 So I'm commenting that code out completely。 And I'm going to look at my magnitude and the lokes magnitude。

 And if。And I can come up here to remind myself， my magnitude。Is an instance field。If my magnitude。

Is less than the lokes。Magnitude。I'm going to return a negative one。

Because the sort dot compared to method， that interface has a requirement that when one object is less than another。

 it returns a value less than zero， and now I'm going to have to say if my magnitude is greater than the magnitude of the other object。

I'm going to return positive one because I'm greater and that's what the contract calls for。

And we can see using kind of laws of mathematics that if it's not less than and it's not greater than it must be equal to。

 so I'll simply return0 in that case， meaning they must be equal。

 I don't have to check because I know if it was less than I would return negative one if it's positive。

 I'm going to return positive one if it's greater than So cannot find symbol。

 get magnitude so I can look in here and see it says get magnitude right there。

 and the problem is that this is a lo and it says get magnitude without the parentheses。

 so I better make sure I call that method。Not get magnitude by itself。

 but get magnitude with parentheses， that's an easy thing to forget。Class compiled no syntax errors。

I'm going to take my quake sort demo。Compile it。Make an object。And invoke。That shorter。

As these have gone scrolling by， I can see this gigantic earthquake of 7。

0 that occurred in the Solomon Islands is the last one I see。And their early quakes all have teeny。

 tiny magnitudes， negative 0，0，0。 These are all very small quakes。

 So the quakes sorter did work the way I wanted it to by putting the smaller quakes first and the larger quakes at the end。

 As a reminder， what I had to do to make that happen was change the compare two method so that if my magnitude is less than the others。

 I return negative one。If my magnitude is greater than the others， I return positive 1。 Otherwise。

 I returned0， as it turns out， because these are all doubles。

I can actually shorten this code by saying， let's return double dot。Comparareed to my magnitude。

And the other magnitude。So I'm going to。Remove this code。By deleting it。See if that compiles。

And the Java dot line do double cannot be dot compared to。 So apparently。

 I've named this one incorrectly， which I often do。So I will use my handy。

Replacement function in blue J to find the name of the method that I want。

And because I'm failing to do that。There we go。Double do compare， not compare to。

 so I'm comparing these two。I just did not know the name of the right method to call。

I didn't read the documentation as I should have， so now I've compiled quick sorter demo。And。

I need to。😔，Make sure I get that one right。Make a new object。Run it。

And I still get the magnitudes as they're supposed to be。 So just as a reminder， I rewrote that code。

 relying on code that already existed， which is a good thing to do in general。

 rather than reinventing the wheel。 Sometimes you forget what's already done for you。 That's it。

 sorted by magnitude， smallest to biggest。 Let's write some more code later。

