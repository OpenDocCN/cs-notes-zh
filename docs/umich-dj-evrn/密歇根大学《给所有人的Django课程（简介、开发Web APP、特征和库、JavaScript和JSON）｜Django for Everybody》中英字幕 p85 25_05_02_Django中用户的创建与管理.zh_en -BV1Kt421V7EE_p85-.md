# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p85 25_05_02_Django中用户的创建与管理.zh_en -BV1Kt421V7EE_p85-

Our next topic is to talk about log in and log out Now just in general。

 I have this GitHub repository called DJ free samples and every once in a while you ought to see if I've found some bugs and fixed them。

 so go over to your samples and do a gett pull so every once in a while just do that。



![](img/4f8eb14e86bc106f8436bf1eeb574046_1.png)

![](img/4f8eb14e86bc106f8436bf1eeb574046_2.png)

So Django like in lots of situations comes with the builtin login logout system。

 there's lots of ways to do it， you can read up on it。

 it has a way to create users has this nice admin interface and so one of the things we like about Django is that we don't have to build some of these basic maintenance things it has permissions in groups。

 we use this in the local library application but we're not going to use that so much in our applications and passwords。

 etc， and it has a way to store these things in various techniques and so the first thing that you'll probably encounter when you're doing this is to create a super user and so you have to log in to your system。

 you create a super user give it a name an email address。

 the email address is for password recovery even though you can log in and you can change create super super userer password anywhere。



![](img/4f8eb14e86bc106f8436bf1eeb574046_4.png)

![](img/4f8eb14e86bc106f8436bf1eeb574046_5.png)

And then you do it now there's a great XKCD cartoon for so many things this is one guy says make me a sandwich and the other one says what make it yourself and then says SUDO make me a sandwich and the other person says okay so what SUD means is it's a Linux command to switch to the super user and do a command so if you don't have permissions to do a command。

 you can say pseudo a command and so that's what this XKCD so that's what we call super userer that's the user that has all permissions doesn't need to get any special permissions。



![](img/4f8eb14e86bc106f8436bf1eeb574046_7.png)

This might be a good time to review what you're going to do when you wipe out your database when you create that superus it just adds a row into a table in your DBSQL light and you can wipe this out anytime that's why I like using SQL light for development in Django if you remove it。

 you've removed all the tables， all of the tables created by migrations。

 the migrate command is what creates tables， the make migration actually creates migrations with your Python code。

So you're going to start fresh。Remove the DBSQLite file that's got rid of all your users。

 all your super users， any data you've put in， it's gone and then you have to wake it back up with a bunch of empty tables with a managed。

 PI migrate and you'll see all those things lots of lines come out at that point I didn't include them and then you're going to have to create your super users again。

 so just if you wipe your database you got to recreate your super users。



![](img/4f8eb14e86bc106f8436bf1eeb574046_9.png)

Once you have a superus， the rest of the users are put in using the admin interface。

 you just go in and among all the other models that you might have in your application。

 the groups and the users are just models， they're models that happen to be built into Django and you don't have any responsibility for building them and so like I said。

 the groups and permissions is useful and you can read up on that and maybe your application needs to use those but for me I pretty much just make users and and call it good later we're going to learn how to use like social login so we'll use GitHub to log people and so you don't have to create any users other than your admin user but in the short term we're just going to use what are called local users which are stuck in a database kept in the database and easy to create easy to maintain but you tend to have to manually maintain them a little bit。



![](img/4f8eb14e86bc106f8436bf1eeb574046_11.png)

![](img/4f8eb14e86bc106f8436bf1eeb574046_12.png)

So next we're going to look at now that you've got a user。

 how do we in our application code log in and log out users？



![](img/4f8eb14e86bc106f8436bf1eeb574046_14.png)