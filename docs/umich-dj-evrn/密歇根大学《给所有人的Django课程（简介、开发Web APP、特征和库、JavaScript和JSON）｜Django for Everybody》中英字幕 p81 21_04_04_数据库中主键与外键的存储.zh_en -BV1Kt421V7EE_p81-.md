# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p81 21_04_04_数据库中主键与外键的存储.zh_en -BV1Kt421V7EE_p81-

![](img/3f978019f939cb299534d9fe83423576_0.png)

So now what we're going to do is we're going to talk about how we can represent links in a database。

 And so up till now， I've just been drawing arrows and just assuming that you know how to do them。

 And so here's some arrows， right， we got some book instance rows that can somehow magically connect to some book rows and some book rows that can magically connect to a language row。



![](img/3f978019f939cb299534d9fe83423576_2.png)

And so there's a way that we do this and we put what we call a key column in every one of our tables。

Key column， we call this the primary key。We often call the name of the column the IDd。

 there is a way in the database to make it what's called auto increment and primary key and you index it。

 So it's really fast。 And so thats that then becomes the handle。

 The primary keys are like the destination endpoint of the arrows right So that's that's how we say the English becomes。

Language number one and Wi of crowds is book number one。

 and introduction to networking is book number two。

 And so the Id is something that we then can use throughout the rest of the system。

Integer replication is not a problem。OkayAnd so then what we do is we put columns in that we call foreign keys right。

 And so those foreign keys are the starting point of the arrows。 right。

 So book underscore Id Now by convention， we name these by the name of the table followed by an underscore。

 followed by the word I。 These are called foreign keys。Foreign keys。

 And so by having a foreign key everywhere we need to start an arrow and in a primary key。

 everywhere we need to end an arrow。 Not really， we pretty much put primary keys on every table so that every row of every table has a primary key。

 Now， in this example， I just got one foreign keyer table。

 But you can have more than one foreign key or table。

 There could be another column here that points off to another table。 But that's it。

 that's how we do it。 We just simply add these integer numbers。

 And then we then we kind of maintain them and put them all together。



![](img/3f978019f939cb299534d9fe83423576_4.png)

So like I said， the primary key is that column。That we add and that is our handle for the rows。

 and then the foreign key is the column that we add to a table so that we can point to something。



![](img/3f978019f939cb299534d9fe83423576_6.png)

So basically once we create these foreign key columns and the primary key columns。

 we start being able to build using these links， we can build the links that replicate the data model that ends up being our picture okay and so that's how they work up next we're going to talk about how we represent these links in Django。



![](img/3f978019f939cb299534d9fe83423576_8.png)