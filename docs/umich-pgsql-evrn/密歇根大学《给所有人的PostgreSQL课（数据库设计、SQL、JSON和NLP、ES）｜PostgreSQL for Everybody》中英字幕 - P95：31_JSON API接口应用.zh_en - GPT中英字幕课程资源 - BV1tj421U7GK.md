# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P95：31_JSON API接口应用.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So the next sample code that we're going to look at is a bunch of code that is going to actually pull JSON from an online API in particular。

 the Star Wars API， which is a fun little thing that has data about Star Wars films and characters and kinds of creatures。

 etc， and so we're going to do this in a way that's a little more complex because。

We're going to spider and we actually don't know what data we're looking at。

 It's not like the email data where were going 1，2，3。

45 we're actually going to retrieve a document then you read the document to see links to other documents and then you retrieve those links and you put them in our database as to be retrieved so this is an application that maintains every time it it maintains a to- do list of URLs to retrieve that's kind of a spider web crawlwler aspect so the table that it's using is a little more complex we certainly have a primary key in some JSON。

We have the URL we've retrieved， we have the status of it， whether or not it's been retrieved or not。

 and then we have some created and updated that stuff， and so like I said。

 this works like Google search and that it looks to it finds URLs and eventually it retrieves them all。

 which is a few hundred。So when we run this program。

 it starts by inserting a few known URLs as the starting points。

 and then it goes and grabs 10 more documents and you can see。

The 200 is the fact that it's successful。And。And then it retrieves retrieved 2200 characters and it counts the to do list at the end of each run。

 so there's only two in this to do list now there's 34 because it found some more and the two list to do list goes up and then as it retrieves things it goes down。

 goes up and it goes down and eventually you this loaded 10 documents and ultimately it had 35 more to go but we can stop this database persists from job from some run to run and at that point you can take a look in another window you can look at your Postgress with your PSQL client。

 you can see where it's at because again this is just Python is one client and PSQL is another client。



![](img/a4788747a08c71621b375f8fd8a85c9a_1.png)

![](img/a4788747a08c71621b375f8fd8a85c9a_2.png)

![](img/a4788747a08c71621b375f8fd8a85c9a_3.png)

So then you can start it back up and at the beginning it says yeahep， I'm back。

 I've still got this database， I've got 35 to go， give me five more， five more， five more， five more。

 and eventually there's about 200 plus documents and then when you get loaded we will start playing with that retrieved JSON by using SQL we'll make some indexes and review a whole bunch of ways to use JSONB。



![](img/a4788747a08c71621b375f8fd8a85c9a_5.png)