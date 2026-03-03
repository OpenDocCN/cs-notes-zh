# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P18：17_数据库规范化原理.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/baa6e8b3bd6fdeba7d01dc4842a62229_0.png)

![](img/baa6e8b3bd6fdeba7d01dc4842a62229_1.png)

So now that you know about primary keys， logical keys， and foreign keys， let's start using them。

So remember， our goal was is to be able to keep track of all this stuff and so we're going to have a track table。

 a artist table， an album table and a genre table， and we're going to get these little numbers。

 and then we're going to use these numbers to keep track of all this stuff because we're going to have to then reconstruct it from those numbers to create the vertical replication of the string data in the user interface just like our designer asked us to do。

So。You literally could spend months reading the concept of database normalization。 Feel free。 Okay。

 I took a database class when I was in grad school， and it just went totally over my head。

 And I thought databases are a dumb idea。 There's wait too much complicated tech theory here。

 And then I went to work in a company。 and I SAT in a room。 And by by noon on one day， I'm like。

 I love databases。 And that's because they taught me how you really do it。 rather than the theory。😊。

And I'm not saying theory bad， The is awesome， that's why they're so fast。

But from a technique perspective， it's pretty straightforward。 First， don't replicate string data。

 Reference the data， pointant data。 It's a form of compression。

Then use integer keys for your primary keys and for your references and put that primary key in each column in which we've talked about already。

So rows end up in these columns and so when we're going to put AcDC or lead Zepeellin in。

 we just say， okay， here's lead Zeeppein and lead Zeepelin for all intent purposes everywhere else in the system is going to be stored in a column called artist underscore ID and then that number goes in there。

 So lead Zeeppelin is one ACDC is two and once you insert them for pretty much the life of the system。

 although you can change them later if you really want in general。

 you will just use two to indicate ACDC and one indicate lead Zeeppeelin from that point forward in these foreign key columns Now you can have many sort of one primary key and you can have many foreign keys pointing to it。

 this just in our data model it's pretty simple。 So each of these little arrows that we drew just kind of scribbling on the board become sort of this pair of numbers。

 a source number and a destination number or a parent and child is another way to think about it。

 So we take this logical schema that we built of what belongs to what which we just。



![](img/baa6e8b3bd6fdeba7d01dc4842a62229_3.png)

Talking and brainstorming。And getting our data spread into more than one table。

 and now we're going to actually reconnect them together。

 And so we ended up with this picture that had these albums connect belonging to。

 and this was just thisil logical data model and it doesn't even have to look all this elegant。

 but you have to take this data and split it into some number tables in our case 4。

 and now we're going to show about the mechanics of making all these connections。



![](img/baa6e8b3bd6fdeba7d01dc4842a62229_5.png)

And so it's pretty simple。You've got this arrow， and we have to have a way in the arrow。

 there's no like in a database。 we say it's an arrow。 They need columns。

 We need to have a column in there， and that column is an integer。 So we add the columns。

 So we augment。The primary key。 and we add a primary key field to each one of the tables。

 And then we have a logical key。 And the logical key is just another column， except we。

Distinguish it。 We just put a little astropiite。 say this is special。

 This is the one we're going to use when we have many rows to look up a particular row。

 Once we get to that row， we'll find things like the rating length and count right。

 And so the database by us telling that the title of the track is going to be something we're going to look up on。

 the database actually does stuff in how it represents the data by building what are're called indexes to make it more efficient to look those things up。

 right， We talked about those indexes before。 And so the logical key simply says something that we would like you to make an index for because we're going to use it a lot。

 and the faster you're capable of responding to look ups by title because we're not going to spend all that time looking it up by rating。

 We might sort by rating or whatever。 But the thing we're going to look up and we expect to be really fast is the logical key。

 So logically， just a column。 It's a string column of our jar or whatever column。

 And these are just integer columns。😊，But then to model the picture。

 And this is what's called a many to one relationship， many to one。

 And there are many tracks that are on one album。 And it's like another way to think about this is somewhere between 0 and infinite number of tracks per album。

 So that's also a way to think about the many side of this arrow。

And so on the many side of the arrow， on the one side of the arrow， we just put in this primary key。

 and on the many side， we add a column。And we call it album underscore Id。

 where the first part of that is the name of the table。

 And the second part of that is our our little memory technique to realize， oh， that's a foreign key。

 and it's in the album table。 And so that's how we sort of in abstract way， draw arrows。

 So we take and we map these arrows。And we turn them into columns。

 so it's a pretty mechanical process， literally once you got it figured out。Pick the logical key。

 add the primary key， and add any necessary foreign keys based on the arrows that you've got。

And so when you finish this over and over and over again， we had four tables。 We had three arrows。

 And so we end up with。One， two， three。Four primary keys， we end up with a logical key in each table。

 tube。And then we had three arrows， so we end up with。3 starting points。

 And then we put foreign keys at the starting points of those arrows and away we go。

 And so it's it's。

![](img/baa6e8b3bd6fdeba7d01dc4842a62229_7.png)

Once you have the picture， you're kind of like， file the technique。

 I I can write these things super fast， and then I can read them。 They're really pretty。 And again。

 I go back to the fact that I've used a convention to build all this stuff。

 And I can look at this as like， oh， of course， that's a foreign key。 And it won't take you long。

 and you'll start seeing the exact same thing that these are foreign keys。

So now that we've sort of built the structure， now we're going to start typing some SQL commands so that we can insert。

 create these tables with these special fields and then start inserting some normalized data。



![](img/baa6e8b3bd6fdeba7d01dc4842a62229_9.png)

![](img/baa6e8b3bd6fdeba7d01dc4842a62229_10.png)