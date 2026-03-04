# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P39：10_存储过程开发实践.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/1e1b10cc730232b92a6f064c076114e2_0.png)

![](img/1e1b10cc730232b92a6f064c076114e2_1.png)

So now we're going to talk about start procedures， Start procedures is another one of those topics that you can start a conversation in a coffee shop about start procedures and people will often have strong opinions。

And I'll share my strong opinion with the understanding that it just an opinion。

I tend to avoid store procedures at all costs。And the reason that I don't like stored procedures is I tend to move from one database to another。

Now， you know， if you're working for a company and that companys a Postgress company。

 then you they're not going to be nearly as opposed to star procedures。

 but if you're moving from Oracle to to Postgress my SQL to SqL light and youd start using store procedures too much。

 they're generally not portable at all。 even what's possible to be done in star procedures has slight variations from one database to another。

 But if you're a company that is a Postgre company and you're building an online system and you have some query that if you did it all kind of run a query。

 run a query， read the results， run seven more queries， then do this other thing。

 and you had to do that for like your main screen， that would be so dog slow。

 it'd be so horribly slow that you'd be like， can we please make that main screen be a star procedure and someone like me be like。

 oh man， I really don't like star procedures， but our company's going to w a business if we don't take these。

Nine SQL statements with some if statements in the middle and just tu them in a historic procedure。

So from a performance thing， they're pretty awesome because they take multi step processes that are full round trips between an application like PGSQL and your database and then do them all in one database transaction。

 so the fewer SQL trans statements and fewer round trips between your application and the SQL database。

So they're both wonderful and scary。 And so I just， I don't say I never use them。

 I just tend to use them kind of in I like to isolate them and have a real strong reason why I'm going to do it。

 like said。Strong reason to use the store procedure。

 You're solve a major performance problem because they're harder to test and they're not portable。

 And， you know， maybe there's some rule that you can enforce on a great statement。

 like a constraint or a unique key。 The one time I wanted to do this。 Although Postgre did it was a。

A key word this instead of being saying this field has to not be null。

And this field has to not be null， I wanted to say one of these two fields must not be null。

 but it's okay for either field to be null as long as the other field is not null。

 and there's no way to express that in a crate statement。

 and the only way to do that is to do a stored procedure。

The way I ultimately did it was I didn't use a star procedure。

 I just made sure I never put records in that violated my rule of2 nulls。 Ba， I didn't allow2 nulls。

2 two columns，2 nulls I wasn't allowed to do。 So that's kind of a rule that must be enforced。

 And as we as a software developer， I would much rather have been able to enforce that rule in case I as a software developer。

 made a mistake。 And when I am told by my database that I violated S I write some SQ in a violated rule。

 I'm not mad at the database because it was my rule that I put in there to catch myself and keep myself for making mistakes。

 We do that a lot when you're writing， trying to write really reliable software。

 you make rules that when you break， you get stopped。

 So you at least find when you're making mistakes。 if you， well， whatever， will just let it go Well。

 then you don't find your mistakes。 So that's the whole idea of a stir procedure that's like double checking something to say。

 don't be doing this。So。I'm going to go back and talk about one store procedure and has to do with the updated at in the updated at field here in our favorite table。

 So the updated at sort of from a semantic perspective is going to capture the moment that this was last modified。

 So created as when it is first inserted and updated at。

 And if you recall the default now says at moment of insert。

 pick this current moment in time and store that in the database。And so the problem is， is that。

If I want to do this and I have this updated at， then every time I'm going to do an update statement。

 I can't just do the update of the thing I want to update。 I got to say updated a equals now。 Now。

 I don't know if that you consider that to be like。A really terrible task。

 But other databases actually do this for you automatically。

 You just have a little different thing that you say right there。 and you like。

 make just update this every time from minus' the thing I want， right？ But you can't do that。

 You can't indicate on a create statement that you want updated at to be automatically changed upon update。

The right way is using store procedure。 and it's a super simple store procedure。

 And so it's the one one， the one star procedure I'm going to show you I don't expect you to write a lot of store procedures。

 but I just do want you to know what they look like， so。

The way we're doing this is we're going to create a trigger function。

 What is the trigger function is like when something happens， do this。

So when we're going to make a function， we're going to give that function a name。

And it's going to be called trigger underscore a set timest。

 This could be Gp for all we here that just happens to be a pneumonic name。

 trigger underscore set timestamp。This function we're making is to be used as a trigger in that there are other ways to do it。

 You can make， you can make a trigger。 You can make a statement。

 There are various other things that you can do。 You can have a function， a trigger or statement。

 but this is a trigger， which is a bit of code that's going to run。

Either before or after some SQL statement is going to run。

And so what we're going to do is this beginning and end is the actual code of our stored procedure。

 and all we're just saying is。Whenever we're going to do whenever something happens to this record。

 that's what the new is， we're going to set update it at Tiby now and we're done。

 And so we're we're sort of manipulate。 there's a record about to be put into the database。

 and right before we put it into the database， we're going to sneak the current time and update it at so when it goes into the database。

 it's going to be changed。And then thiss all just syntax， double dollar sign and PLLP， SG。

 that's the weird language。Postgres supports more than one language， I don't like story procedures。

 but if I do start procedures。I prefer to use the built in language。

 You can use like tickle T K and Pearl。 None of those things seem appealing to me。

 P P G S Q L doesn't appeal to me， but at least it it's the most powerful of the store procedure languages。

 So I just say ifm， if I'm living in Postgre land， then be like the Postgressreors。

 And if I'm a biggest store procedure， do it through Postgres people do。

 because no one really wants to do a tickle T K， and it's not going to help you all that much， right？

 So。This is just like a create table， but it's actually creating a function。

 which is kind of expanding your database。 Like when it creates a function that makes a little space。

 I mean， a create table， it makes a little space for that table somewhere on the disk。

 Now we're going to stick somewhere a function that can be pulled up and loaded up。

 The next thing that we do is we actually create the trigger。

 Now we're saying is this is kind of like when an update statement happens。 i。e。

 before an update on the table fave。 for each row that is about to be updated。

 run that row through this little trigger。 So if there's one row。

 it's going to come in here and it's going to have its updated。

 then it goes to go back And then if there's a second row， it's going to come in。

 So remember update statements with where clauses could do many rows。

 So that's why it's for each row。 This update statement is going to change。 execute this trigger。

 which allows us here comes a row to the database。😊，Jump in front of it， tweak it。

 and then let it continue back into the database。So now when we say set how much equals how much plus 1。

 implicitly updated data is set to now。And so like I said。



![](img/1e1b10cc730232b92a6f064c076114e2_3.png)

Stored procedures can be very simple or very complex， I tend to use them for very specific reasons。

This seems like to me a good reason， because I just don't want to say updated a equals now on every single update statement。

 because I like it。So up next， I'm going to try to pull a lot of these ideas together and do a demo of reading and parsing files and actually computing primary keys and using subses and making database administrators crazy。



![](img/1e1b10cc730232b92a6f064c076114e2_5.png)

![](img/1e1b10cc730232b92a6f064c076114e2_6.png)