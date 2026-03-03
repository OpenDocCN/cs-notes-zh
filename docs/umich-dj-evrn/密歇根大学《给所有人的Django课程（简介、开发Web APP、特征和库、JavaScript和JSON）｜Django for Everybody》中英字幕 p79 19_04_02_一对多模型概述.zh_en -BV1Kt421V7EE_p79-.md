# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p79 19_04_02_一对多模型概述.zh_en -BV1Kt421V7EE_p79-

Hello and welcome to our lecture on data modeling。 We're going to have a couple lectures on data modeling。

 This first one is sort of the one to many， which is the easiest to understand And then we'll have another lecture on many to many just to give you sort of。



![](img/80eeec48e1790ad65004c48c058ec196_1.png)

![](img/80eeec48e1790ad65004c48c058ec196_2.png)

We're still sort of building a Django application one piece at a time and we haven't built a whole Dngo application。

 but basically we're really focused on model dot py and a little bit more on admin to inform so model Py is where we define the structure of our database and。

We see this database through data models， data model objects。

 and we can register our data models in admin。 Py。 There's not too much in this admin Py。

But we really， and so we're going be talking to things like the shell。

 or can even run scripts in here。 So the whole thing。

In this lecture we're not talking much about the routing or the views or forms or templates。

 so we're really focused down in this area of our Django application and it's okay we'll get to the rest of them and we're just kind of talking about the data modeling now。



![](img/80eeec48e1790ad65004c48c058ec196_4.png)

So。I came to databases late in life。 I saw him a little bit in grad school。

 which is a very long time ago， and I didn't like relational databases as much。

 and I went to a job and that I had learned relational databases for the job。

 and I actually was pretty pretty advanced program at that point in time and so they taught me how to do data model design and I picked it up really fast and I like totally fell in love with databases。

So model design is an interesting problem to solve。

 that the basic idea really comes down to efficiency of storing and retrieving data。

And it just comes down to like if you build an online application like Facebook and if you're not clever about how to store your data and somehow every time you logged into Facebook。

 you had to read all the Facebook's data to find you log in，Yeah， we really literally cut take you。

2 to 3000 hours to log into Facebook if it had to read all of its data。 Now， obviously。

 millions of people log in per second in Facebook。 And so obviously。

 they're a little faster than that。 So somewhere between。

 days and days and days to read the data and can read the data million times a second in there is where databases win。

 And so at times， it seems like like when were in data model you're like， oh， this is so difficult。

 Why are we working so hard。 And the answer is， you just can't scale。 I mean。

 you can read through your data for simple data mining things， But databases are really important。

 And especially when you're building interactive online application， speeds important。

So it turns out that like most things in database， you can learn the basics pretty quick and the rest of it is sort of an art form that you learn as you go。

And so the goal is to figure out the data that you want to store in your application and then draw a picture。

Spreading that data across multiple tables and then creating links between those tables。

 So you kind of start with a sample data set。 Now this is where we're going to end up。

 And this is the model for the data for this local library application that we're building。

 and this is the thing we're going to keep coming back to over and over。 So this is the destination。

 But we're not going to hit this destination， we're going to start more with the data。

 Now different application when you work different organizations。

 you're going to find that the data model is very important。

 So this is the data model of my autograder， which is based on a framework I've built called Suie。

 And so if you were to learn this thing early on， I say。

 oh and here's our data model and here's how we store stuff。 and here's this。

 that and the other thing and this data model took a lot of time to get right。

 and it's a real important part of the application and another project I work on it's calledschi it It's a learning management system that's open source。

 And this is a tiny fraction of the data model。 But if you want to work in this application you want to improve something right。



![](img/80eeec48e1790ad65004c48c058ec196_6.png)

![](img/80eeec48e1790ad65004c48c058ec196_7.png)

You got to figure out this data model because where the data goes。

 it shows up kind of flat in the user interface， but eventually it's stored in very specific locations and linked and that's why you see all these little boxes but then lines。

 the lines are also the links between the various tables。



![](img/80eeec48e1790ad65004c48c058ec196_9.png)

So there's a whole bunch of theory about database normalization and it's important， it really is。

 and if you take some time， go ahead and read about it。First normal form， second normal form。

 third normal form， third normal form， version A and stuff。I'm not really into the math。

 I don't really wantan to explain you to the math to you。

The key thing about database normalization ultimately that it can be sort of distilled down to don't replicate string data and whatever I mean by string data is like names and URLs and things like that so in a system ultimately。



![](img/80eeec48e1790ad65004c48c058ec196_11.png)

🎼If if my email address is stored in text in that system， it literally should be stored once。

 there should be no email address， email address， email address。

 What you need is to have the email address one place and then kind of give that email address and number and all the places you want to indicate about that email address who use the number。

 And so these integer numbers are the key。 So we create keys which are the lookup handles and then we point to those keys。

 and we use integers to make links between the tables because integers are fast。

 They're the thing that computers understand better。

 They understand computers understand and move integers around。 They use less data that calculate。

 they compare really fast。 And so it's very integers are very important。



![](img/80eeec48e1790ad65004c48c058ec196_13.png)

![](img/80eeec48e1790ad65004c48c058ec196_14.png)

So up next， we're going to take a look at some example data and then we're going to design a data model for that data。

