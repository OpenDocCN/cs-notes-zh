# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P15：14_关系型数据库设计（第一部分）.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/7784028ae2567156d4d16c21c6601836_0.png)

![](img/7784028ae2567156d4d16c21c6601836_1.png)

Hello and welcome to relational database design。 This is a a really interesting topic。

 and it's a topic that I think you can learn pretty quickly， but it's。

 it's sort of like the the artistry of what databases are。

 And so what I'm going to be teaching you is a。😊，Kind of techniques。

 And I'm going to assume that at some level you're going to not think that you're a great database designer and you're going to get better the more you do it。

 And it also really helps to do with other people。 I know that when I learned to do database design that I did it with a group of people and I was in a conference room and we had a whiteboard and we were drawing pictures and people who knew more than me were drawing pictures and I was able to get it by drawing pictures。

 So I'm going to simulate that in this lecture， but at some point for you to get really good。

 You're going to have to work with people who know more than you who can mentor you and then it comes to you pretty fast so。

The basic idea of database design is you're going to end up drawing a picture of the shape of data。

And so you're going to end up with something that looks like this picture。

 this is a picture from a database for software that I write that I use for learning technology that I build for auto graders for classes。

 etc ce， and this happens to be a database that's thinking about students。

It's thinking about courses， it's thinking about memberships in those courses。

 it's thinking about roles， it's thinking about different courses and so。

Eventually I have to draw this picture and so we're going to try to get you to draw pictures and they have lines between them and each of these boxes on the picture is a table and the lines are what are called foreign keys。

 we'll cover all this in a bit， but you end up drawing a picture of your data and then you translate that picture into a set of database commands and shapes to create it。

And if you go into a large project。Sai is another project that I am part of。

 and this is just a small part of it。 you will often notice that the project has like a data model like on the wall in a giant you know5 feet by three feet diagram。

 and that's because this becomes kind of like the core essence。

 the soul of an application is the data model the way you store the data and so it's very。

 very important。So the idea is in building a data model is that you can't always just read through a file in sequence。

 you want to be able to sort of bounce around in that file and in a way it's a form of compression through connection。

 if that makes any sense。And so if you have an email address， you know， c7otum。edduu。

 and you're going to have all kind of places in the data of this application where something is owned by c7otumish。

edu， the basic rule is， and this is a form of compression is you don't put that string。

In your database more than once， you put that string in once and then give it a key， like a number。

 And so if you were using this on Coursera， for example。

 you might find that when I logged into Coursera for the very first time。

 I was assigned a user number， like 116421。And instead of putting my email address throughout the Corsera data model。

 they just put that number。And so we need this number and if I author a discussion forum post。

 then we use the number to indicate that I was the author of that， if you comment it。

 we use your number， we don't use your email address， if all goes well。

 we should have one table and one field and one copy of your email address in a database。

And so one way to think about this。 And this is the way that I first learned how to do this is。

You take an application and you have to build a data model from a mock up of the user interface to the application。

 And so you can kind of imagine you're at a start。 I was building educational system for Ford Motor Company when I first learned to do data modeling many years ago。

 and so we knew what the designers thought they needed in terms of this is the user interface and then we have to come up with a database。

 Now you might think， oh， I'll just make this a CSV file doesn't look like it's all that much data。

 The problem is is that。If you just make it a CSV file for 100 entries。

 it might be fast and for 300 entries， it might be fast， and then for 3 million entries。

 it's not fast and then for 300 million entries， it's not fast。

 And the interesting thing about databases is you can have 300 million entries and it still can be fast。

And the the basic flaw in a CSV file。 And I don't know if you've ever tried， you probably haven't。

 but a lot of people have tried to like make a spreadsheet of all of your music。

 And it's easy to type this stuff in， but you end up with what I'll call vertical replication。

So when you're typing these things in。You you know。

 you type in a track and then you type in you know the artist and the album and the genre。

 and then you type in another track and then you copy and paste these pieces and you copy paste。

 copy， paste， copy， paste， copy paste。And that seems like it's okay。

 but if you start thinking about this。It's kind of frustrating。 You still need to know that these。

Are part of an album and part of an artist and part of a genre， you still need to know that。

But then let's just say you want to go in and edit it。

 and let's just say that as you were putting this in。

 you had a typo and you have many albums by black Sabbath。

But you made a typo and you kept copy and a pasting。 And now you got to fix it， fix it everywhere。

 in this simple one， it seems simple enough。 But if we're talking millions and millions of records。

 then it's impossible。 And that's why ultimately， we want to come up with a data model where the word black Sabbath ends up in one table one time。

 And then there's some number。42， for example。 and then everywhere we want to。

Mark something as belonging to black Sabbath， instead of。There we go。

Instead of putting in black Sabbath， we put in。42，42，42，42，42t da da dat dot。

 And now if I made a typo。 And so this somewhere else in some other the table is black Sabbath。

 and 42 is the number。 and I made a typo， I just fix it here。 and somehow magically。

 all this changes。So you could go get a whole PhD in database。

 What I just described is the single most important concept in building a data model。

 and I'll say this over and over， vertical replication of string data is not what we want to do。Now。

The thing we don't want to do is go back to our user interface designers and say。

 you know what I don't do you realize how bad vertical replication of data is because I took a class。

 And my professor said， I shouldn't do vertical replication of data。

 So you need to make a new user interface。 and that's wrong。 The interface should be what it is。

 if this is the interface。 and now we can see all this because this is pretty convenient as a user。

 I kind of like this， right， I can sort these things up and down and up and down。

 And I do want to see this。 And I want to be able to search for black Sabbath。

 I want to search for all these words。 And I want to see all this replication in the user interface。

 I just don't want to have it in the database for efficiency purposes。

 So we accept the user interface and its needs as okay。We don't fight that。

 but what we have to do then is make a data model and then reconstruct from that data model the user interface that they want。

So the idea is as you find sort of each string number， each piece of data。

 and then you decide whether you're going to put it in in which table you're going to put it in。

 sometimes you have to build new tables and then you build these tables and then you draw lines in between the tables and you end up put those pictures that I talked about before。



![](img/7784028ae2567156d4d16c21c6601836_3.png)

So we'll stop here， but then when we come back， we're going to go through and build such a table。



![](img/7784028ae2567156d4d16c21c6601836_5.png)