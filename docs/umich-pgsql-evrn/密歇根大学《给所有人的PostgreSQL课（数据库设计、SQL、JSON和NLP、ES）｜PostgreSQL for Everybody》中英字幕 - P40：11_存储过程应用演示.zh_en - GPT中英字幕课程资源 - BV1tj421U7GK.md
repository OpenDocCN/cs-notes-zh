# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P40：11_存储过程应用演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to another SQ L walkthrough。 In this walkthrough。

 we are going to talk about stored procedures。So if you take a look， for example， at our。



![](img/2cf6f06250134fbee2f39de780ad6e26_1.png)

Our favs。Slash D plus favbs。I'm sorry， I'm almost too my state。

I always keep it singular I keep my table name singular because there are you know it's a place that we keep a fab So if we take a look here。

 it's real common to create create at and update it at variables in lots of rows and we can make the default now but that's only when the data is inserted but sometimes you want to make it so that every time you updated at is automatically changed every time you change it。



![](img/2cf6f06250134fbee2f39de780ad6e26_3.png)

So。So let's go ahead and insert a row oops what's in here select。



![](img/2cf6f06250134fbee2f39de780ad6e26_5.png)

Star from Fab， let's see what I' got in here。

![](img/2cf6f06250134fbee2f39de780ad6e26_7.png)

Yeah， I got some stuff。 So I got like 9，99 in there。 so I can， you know。

 update fab set how much equals， how much plus one。Am I colon？For forgott to semi a con。

And so it's up now 1000 and the created date is still the correct created date。

 but the updated date didn't change。 and it's common that we want the updated date to change。

 Some database systems have a part of the create statement that you can say auto update the updated at。

 but it turns out that Postgress does not have that feature。

 So we have to use what's called a stored procedure and a stored procedure is a bit of code that you can sort of stick in the server that when the server receives its SQL commands。

 it can add some of your code to all the work that it's going to be doing。

It's way for you to extend the behavior。So Postgres the stored procedures are their own little language and I don't expect you to really write them。

 I didn't write this one， I Googled like how do you automatically fix the updated ad in Postgress and I found this and this is probably the most common thing people do partly because other databases I'll do this automatically but Postgres for some strange reason doesn't give you a feature to do this automatically。

So the first thing we're going to do is create some code， so create or replace function。

 This is like inserting code into the database and it's a little weird language P PgsQl it's there's a bunch of different languages。

 I prefer to write them in the Postgres native these things are not portable。

 they're very unportable and so you might as well just use the language you're going to use because if you say。

 oh， I'll use Python or JavaScriptscript because there's other languages you find that they have compromises and you're not allowed to do everything in them so tech with it just use the built-in stuff and don't fight about it So that create function put something in the database okay it put code in the database and now we have to associate it and so we're going to create a trigger triggers this bit of code that like as an event that when it sees something happening。

It like triggers our code， so it says we're going to make a trigger in the table post。

Each row that's gonna before you update each row run this code。 And this code is basically gonna go。

 Here's the new row。 And before we put this thing in。

 a change the updated at and then put it back in the database。 So this is like deep， deep。

 deep in the database。 There's no extra transaction。

 We could put our updated a over up here on this update。

 But this way we're going to make sure every time this data changes one way or the other。

 It's going run。 So this basically says go into the post table and mark a little event that says run my little bit of code right before you finish the update。

 It's kind of in the middle of the update。 The update is started。

 And then we're going run our trigger and then the update finishes。

 So between the time the update is sort of handled and the update is actually set in the database。

 And it's quite simple。 And again， I'm not expecting to write this。

 but I'm expecting conceptually understand what's going on here。

 And you have to realize that this just wrote code。 This is associating it with the post table。

So you only write the once， I'm going to put it on the post table。

 I'm going to put it on the fab table。The fab table。

And this would be something you'd probably do in your creation statements。

 and I'm going to put it in the。

![](img/2cf6f06250134fbee2f39de780ad6e26_9.png)

The comment table， so now I have these triggers。

![](img/2cf6f06250134fbee2f39de780ad6e26_11.png)

And so the difference now is when I run this update statement。



![](img/2cf6f06250134fbee2f39de780ad6e26_13.png)

You will see that the update time is now changed automatically， so I can do that again。

And then this update time will change again。 The crate time doesn't change， but the。

 the stored procedure。Has caused that update to happen。

 And so this I don't you will find situations where you want to write stored procedures。

 I tend to generally avoid stored procedures if I can help it。

 but in this particular situation it's the way you solve this problem of automatically updating an updated that column So it's not outrageous to use a stored procedure in this particular situation。

 So this is one I want you to know and you'll be you'll run into some problem and they'll say oh。

 this way to solve this in Postgress is use a stored procedure。

 they're not as bad as you think writing them is a skill that only advanced postgreors which I don't even count myself as an advanced postgresor so I just go find them and then I use them and I understand what it's doing and why it works and what。



![](img/2cf6f06250134fbee2f39de780ad6e26_15.png)

But I don't write them as a matter of course， I write a lot of SQL， but not so much star procedures。

Cheers。

![](img/2cf6f06250134fbee2f39de780ad6e26_17.png)