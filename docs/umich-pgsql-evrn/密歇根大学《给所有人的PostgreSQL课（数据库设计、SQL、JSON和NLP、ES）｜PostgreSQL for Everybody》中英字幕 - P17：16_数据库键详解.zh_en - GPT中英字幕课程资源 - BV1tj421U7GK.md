# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P17：16_数据库键详解.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/8af8ea89e5ba9c0f6a2b7e03b13ca23c_0.png)

![](img/8af8ea89e5ba9c0f6a2b7e03b13ca23c_1.png)

So now we're going to talk about the different kinds of keys and what keys are is kind of connection points。

 we connect one row to another using a key， or we will go find a row in a database table using a key。

 and there are three kinds of keys。So each row in a table gets what we call a primary key。

 and that's like to give us a handle to say that row。 So that's like the AC row is number 42。

 let Zeppelin row is number 75。 C7 at Uish is number 120453。 those are the primary keys。

 and that's that single string and then this number is what we're going to replicate all over the place。

 So that's a primary key。 Then there is in most tables what we call a logical key and and the primary key is not something it might show up in URLs in your user interface or something。

 but the primary key is almost never something that you know what your primary key is。

 whereas the logical key is that's you right， And so that is your email address or the title of the track or the title of the album or the email address of the loggedin user or something like that。

 So if you think of the outside world saying I got to go。

Find a particular person or track or whatever， they use the logical key。

 Or if it was in a user interface， and there was like a search button。

 The thing you type into the search， that's the logical key。

 That's the thing that the world uses to find a row。

And then the other thing that's sort of internal to the database is what's called the foreign key。

 and that is an integer in one table that points to a row in a different table。

 and that's why we call it a foreign key that far away table is the foreign table。

 this is the local table。And we have a naming convention in different organizations and different pieces of software will' use different naming conventions。

 And so I've just chosen one of the more common naming conventions where in every table。

 and in this case， the album table the。ID field is going to be the primary key。

 and so we'll just know that no matter what we name our table。

 we're going to name the primary key field ID。Logical key will be whatever。

 and we use a convention of foreign keys and an underscore ID and the first part is the name of the table so I can look because of my convention that artist underscore ID points to a row in the artist table and when you go to an organization an important part of database is a set of rules and conventions that an organization uses to keep themselves s and so you will go in and they'll say。

 okay， this is how we name our fields and you're like oh wait I was in college in my professor named fields a different way。

 don't say that。 just say oh that's great。 I really like working here and then follow their rules because ultimately which rules set of rules you pick doesn't matter as much as being consistent within those rules so I've picked a pretty common set of rules and you'll go a lot of places and you'll see the same rules that I've picked but just because an organization uses a different set of database naming。

Database column naming rules doesn't mean that they're wrong per se。

So the primary key is a somewhat counterintuitive notion for a lot of people， you think to yourself。

 well， your email address is your email address and isn't why wouldn't use that everywhere and there are some database experts that might even tell you that's a good idea。

 but it's not a good idea those databases experts are wrong。The key thing is， is that。

The whole thing that makes this super fast， no matter what database system you're using。

 is this mapping from a string to a number。 And those people that would suggest that you could use a logical key as a primary key。

 meaning that you could put an email address everywhere。

 What they're really doing is using a database layer to kind of fake it to fake that。

 And there's still a number is just a number you're not dealing with。

 So you might as well go ahead and deal with the number。

And things like you and my addresses has changed here at the University of Michigan。

 you can come and you can get an account and you can get married or divorced or just not like your name because we make something up with your a bit of your first name and a bit of your last name and they don't all come out great right。

 so you fill out a form and you can change your logical key。But on the systems we have on campus。

 once you started registering for classes， we still want， we can change your logical key。

 And remember it's a string if the system is properly architected， it's exactly one place。

 not at the university， you might have like 20 large systems。 So if we change your email address。

 we got to get a hold of all 20 systems， and say this person's email address on this day is changing from this to this。

 and then the 20 systems all change it， but within those system， they have one place to change it。

 they change the logical key in the one table that is the user table or whatever。

 And so be careful about believing too much about email address is not changing。

 even though on average， they do change very slowly。

And so if you're using as primary key like a string rather than a number and people also use these things called GoUIDs。

 which are long strings of random numbers and they join on GoIs。

 those things aren't not as efficient， although in some databases。

 they kind of fake the efficiency and so the simple thing is just use integers， as your foreign keys。

 integers as your primary keys and strings or whatever as your logical keys。

 and then no matter what database you're using， you're going to run very effectively。And like I said。

 a foreign key is a key that points to the primary key of another table。

 and so if we are pointing to a row in the artist table。

 we would name that artist underscore ID and again。

 I'll just say one last time when primary keys are integers。

 then foreign keys are integers and matching them is something that systems can do very efficiently。



![](img/8af8ea89e5ba9c0f6a2b7e03b13ca23c_3.png)

So up next we're going to start using these foreign keys and these primary keys as connecting together。

 using what we call database normalization and we're going to like bring all of this together and actually start kind of writing code。



![](img/8af8ea89e5ba9c0f6a2b7e03b13ca23c_5.png)

![](img/8af8ea89e5ba9c0f6a2b7e03b13ca23c_6.png)