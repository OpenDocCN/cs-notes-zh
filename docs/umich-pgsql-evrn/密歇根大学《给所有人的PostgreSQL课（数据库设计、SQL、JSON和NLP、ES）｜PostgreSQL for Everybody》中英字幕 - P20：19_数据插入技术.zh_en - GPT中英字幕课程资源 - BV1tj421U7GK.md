# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P20：19_数据插入技术.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/7ba8b8188d7f47bdc69880364d6577c8_0.png)

![](img/7ba8b8188d7f47bdc69880364d6577c8_1.png)

So now that we built all of our tables， it is time to actually insert some data。

So here's the first thing that you're going notice。

 I mean this very first line is really important because you'll notice that we've always always done insert into table name and then we have the values。

 we have the columns in the values that we're going to use but we don't have the ID field right So remember the ID is a serial field so we do an insert。

 We do another insert and the ID values are automatically generated for us So lead Zeppelin gets number one AcDC gets number two So remember I mean I've only said don't replicate string data。

 we're going to use numbers。 We have now assigned for as long as we're going to run this database lead Zeppelin is number one and ACDC is number two。

 that's not really a value judgment about rock and roll that is a primary key that's generally internal to the database。

And so then we have to make these connections， right。

 so we want to connect the albums to the artists。 Now， we have to know this。

 and I'll show you a couple of different ways to remember these little numbers， but we basically。

We can't tell it easily how to set these artist Is。

 They're not automatically set in the same way that the Is are automatically set。 So in this one。

 you'll notice there's no I that we're inserting。 And so we have a title in an artist I。

 and we had to remember。You just kind of write on a little piece of paper or something when you're doing it by hand。

 And that's exactly how I do it。 I'm like， when I insert it on that previous screen。

 I remember that lead Zepppeellin was one， and ACDC was  two。 and then I construct these by hand。

 And later， we will see quicker ways to do this once we know a little bit more S Q well。

And we're going from the outside of these trees， right， So we got track。 We got album。

 and we got artist， and we got genre， right， and we're kind of working our way in from the outside to the inside。

 And then eventually， we're going to get to track。 So really。

 we're just establishing what the primary key for rock and metal are so that we don't have to use those over and over So it's not too bad。

 Now， this starts to look complex。 But this is part of where if you've been having conventions all along。

 You just， I type this really fast because it's just following a pattern， right。

So we've got ID that's going to be taken care of automatically。

 we've got the title and then we got our length rating account that come in and these are in the same order these the values are in the same order as the columns and then we have two primary keys because here on track we point to album and we point to genre and so that's what these things are doing and so we just know which album it is and which genre it is。

 which album it is， which genre it is and we just know those numbers and when you're doing this particular following along hopefully you're just cutting and pasting these things。

 but if you have to from scratch， you just keep track you have a little table that is the album IDs。

 the artist Is in the genre Is， little piece of paper and then you can do all this stuff。Okay。

So that's like a whole bunch of fuss just to not replicate。These strings， right。

 we effectively create。Rs that represent those strings once。

 And then we get primary keys for those things。 And then we use these primary keys in foreign key columns to make the connections。

 In a way we go it。 So we've built the relationships that we need in our data。

 And it's really just numbers， it's not that much more complex。

 So once we've spread this data across all these tables。

 Then we're going to actually have to reconstruct it because。



![](img/7ba8b8188d7f47bdc69880364d6577c8_3.png)

Our graphic designer who designed this UI didn't really want numbers to be shown to the users。

 And so we still have to reconstruct this。 And we want to do that efficiently in。

All these numbers are also a form of compression， strings are bigger than numbers。

 and if you have millions of them， it matters， and so we're going to take this compressed data that's all now links。

 relink it together and produce the output that we want。



![](img/7ba8b8188d7f47bdc69880364d6577c8_5.png)