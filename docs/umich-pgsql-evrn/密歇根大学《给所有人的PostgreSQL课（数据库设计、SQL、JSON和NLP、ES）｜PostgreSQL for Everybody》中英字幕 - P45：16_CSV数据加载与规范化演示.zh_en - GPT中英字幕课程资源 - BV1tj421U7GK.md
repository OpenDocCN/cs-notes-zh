# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P45：16_CSV数据加载与规范化演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Welcome to another walkthrough of SQL。 We are now going to work on something that takes all these techniques that we've been doing it this week and puts them all together。

 So what we're going to do is we're going to take a CSV file and we're going to load it and then we're going to automatically normalize it this is interesting technique because a lot of times what you're going to be doing is taking a large amount of data and then pull it into a database。

 but you want it to be fast and small and so you want it to be normalized Of course we're going reduce the vertical replication So here we have two things I'll just call X and y Zap A Z B12 So we got vertical replication in the second column and so we're going to make a one too many。

 not a none to many a one too many。We're going to make a one to many table out of all this。

 but we're going to do it automatically and we're going to use subseex and we're going to use。

We're going to use subselect and we're going to select Dis and you watch。

 it's a pretty cool technique。Okay， so the first thing you got to do。

 you're going to have to download this。 So I've got a。



![](img/318b5e8e186965090efce63c30aaa864_1.png)

Terminal running。This is just in my home directory and I can call W get。

And now I should have this stuff。嗯。And if I take a look at。

This file right here that I just downloaded。Which one is technique， CSV。3 tab Techs。csv。

We see it's a little tiny bit of data。 That's just the data we're already playing with。 right， Okay。

 so that's good。 So we've got it sitting there。 So now what we can do is we're going to eventually load this in。

 but I want to get that done first。

![](img/318b5e8e186965090efce63c30aaa864_3.png)

Right here， that's the load。Okay，And so I'm going to just type these even though they're not there。

 so it doesn't matter， and then I'm going to create a table。

 So the idea is that you load this into a table that matches the CSV。

And I'm going to have the x and the y， oops， don't do that undo。do whatever that was。

I want the two columns that just come in because I'm taking these in as text。

 eventually we're going to convert these into a foreign key relationship， but for now it's just text。

 and I'm going to hold a little spot to have that foreign key later so。



![](img/318b5e8e186965090efce63c30aaa864_5.png)

So I'm going to do a create table that's just to load it in。

 Then I'm going to load how to lookup table， which is just some text for the name of the thing I should probably put a unique in there。

 but I don't need it， but I could make that a vrj jar unique， but。



![](img/318b5e8e186965090efce63c30aaa864_7.png)

For now， I'm just going to make it be text。 I'm going to have a serial。 that's really important。

 and make that be the primary key。

![](img/318b5e8e186965090efce63c30aaa864_9.png)

![](img/318b5e8e186965090efce63c30aaa864_10.png)

So y has ID serial， a primary key of ID and y of text。

And then I'm going to create the actual ultimate table that I want this to be in。

 so it's going to have an ID column， which is a primary key， it's going to have the x value。

 which is the first column and then a foreign key。 Now I could set all this foreign key stuff up。

And I want to make basically say that I want it there's a uniqueness constraint between X。

 which is the text and y underscore ID so that there's only one combination of Zap and A。

 you can't put Zap and A in twice， so I'm making my uniqueness column my uniqueness constraint two columns y。



![](img/318b5e8e186965090efce63c30aaa864_12.png)

Okay。

![](img/318b5e8e186965090efce63c30aaa864_14.png)

So there we go So the first thing I'm going to do is I've downloaded this file and I'm going to use the PSQL command copy。

 so I'm saying put it in the table X Y RA parentheses X Y says here's the two columns coming from the CSV break it up with the CSV delimers。

 it's a CSV file so that should insert four records and I can say select a star from X Y RA。



![](img/318b5e8e186965090efce63c30aaa864_16.png)

So there we go， so I've got the data that came out of the CSV and why ID is currently empty because I didn't put it in this copy。

 the only thing we've done is loaded these things。

![](img/318b5e8e186965090efce63c30aaa864_18.png)

Okay。So then what we're going to do is use select distinct。

 Now Now remember distinct basically ensures that we only get1 row。

 So I got vertical applicationplication in this y column。

 So you'll notice that if I do a select distinct Y from X， Y R。



![](img/318b5e8e186965090efce63c30aaa864_20.png)

Let's just make let's stick an order by on that order。By。Why。It's like distinct X， Y raw。Order own。

 no underscore。There we go， so now it's even sorted， nice and pretty。



![](img/318b5e8e186965090efce63c30aaa864_22.png)

Now， here's the cool thing， we are going to use a select sub selectlect。Insert into why。

Into the Y column， which is that text field， right？And then select distinct。

 This isn't exactly a subquery， but it kind of looks like we could make it be a from in a subquery。

 It kind of looks like a subry here。 So this is， well what it does is it selects distinct y from x Y R。

 which is exactly what we did。 I'll throw an order by on that for yucks before I run it。

 But then we're going to take that the results of the select distinct。

 and we're going to insert that into the table。

![](img/318b5e8e186965090efce63c30aaa864_24.png)

Im going to do order。Why， why。Now I can say select star。From。Why。

So what we really did because we did a select distinct， we only got one of each。

 that's the key and then because we have a serial column we got the one in the two。

 so we got one maps to A and two maps to B， that's the key。



![](img/318b5e8e186965090efce63c30aaa864_26.png)

Now we have another sort of tricky subselect。

![](img/318b5e8e186965090efce63c30aaa864_28.png)

So we're going to update X Y R， so let's do a select star。To refresh our memory。From x， Y oops。R。

So right now this has the string and it has an empty Y ID。

 so we're going to use an update statement to populate this ID。

 and we're going to do it by setting it to another query。

 so it's going to go through every one of the rows in x Y raw and set its ID to be。



![](img/318b5e8e186965090efce63c30aaa864_30.png)

Select Y dot ID， which is this little ID number from the Y table。From why， where why not why？

Whi is that A in the B equals x Y R， so it's like joining this up。

 connecting this 1 a row to both of the rows that have A and sticking the one in there。



![](img/318b5e8e186965090efce63c30aaa864_32.png)

![](img/318b5e8e186965090efce63c30aaa864_33.png)

It's probably just the easiest to run it。

![](img/318b5e8e186965090efce63c30aaa864_35.png)

It's pretty cool。Now I can say。Select star from X， Y R。 So look at that。 So you saw how this。

 that statement。That update statement。Set the corresponding these now match， right。

 but what's happened is this Y has become redundant。



![](img/318b5e8e186965090efce63c30aaa864_37.png)

So I can insert this again。 I can pull just the X in the Y IDd from X Y raw into this X Y table。

 which is sort of my ultimate destination table。 that's got only the foreign keys Does't have the Y bit。

 So I'm kind of converting it into a pretty little table。 but mostly I'm just throwing away the Y。

 I could do this with an al table， drop column Y， Al table X Y raw drop column Y。

 there's two ways to do it。 So now if I did a select star from X Y。



![](img/318b5e8e186965090efce63c30aaa864_39.png)

It's so pretty。 It has this。 It has the track or whatever。 The X thing。 Each row has a primary key。

 and it has the corresponding boring key that points properly。 Select star from this Y table。 right。

 So it works perfectly。 And so we can like write an awesome little join。😊。



![](img/318b5e8e186965090efce63c30aaa864_41.png)

![](img/318b5e8e186965090efce63c30aaa864_42.png)

So we select star from。X Y joined to the Y table on the foreign key XY doY IDD equals the primary key from the Y table。

 which is exactly what we would do if we are looking at a one to many。

RightAnd so we're seeing all these things， so we've reconstructed our data and we've used the join。

 we even see the join values here in the y underscore ID and the underscore ID and so this notion that we can use select distinct and then the probably the most the three most critical tricks here other than the copy to load the stuff in the first place are the select distinct。



![](img/318b5e8e186965090efce63c30aaa864_44.png)

Insert， you know just this one here。 Select in insert into Y， Pre Y， select instinct Y from X Y R。

 which is the thing that removes the vertical duplication and then assigns the serial number for each one of those things。

And then to go through and， in effect， use the string in the X。

 Y raw to look up the I D and put that into X， Y R。

 And then the next bit is just to get rid of the redundant parts of X。

 Y raw and creates a nice little table that makes all the sense and is properly normalized in a way we go。

 so。I hope you found this useful， I kept this as simple as possible with using really small variables。

 you're going to do some homework that does this over and over and over again with a couple of different examples。

 I hope you found it useful。

![](img/318b5e8e186965090efce63c30aaa864_46.png)