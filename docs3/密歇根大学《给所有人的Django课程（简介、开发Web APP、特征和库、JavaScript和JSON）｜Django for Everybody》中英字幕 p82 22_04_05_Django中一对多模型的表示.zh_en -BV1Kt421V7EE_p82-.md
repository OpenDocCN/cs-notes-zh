# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p82 22_04_05_Django中一对多模型的表示.zh_en -BV1Kt421V7EE_p82-

So we talked about how we reduce replication by moving data from sort of one table with too many columns into multiple tables and then make links with primary keys and foreign keys。

 But we're really not going to operate at that level because this is a django class。

 And we're going to do this in Django。 And so we use data models in models do Py to do this。

 And so a lot of the model field types are characters or numbers or dates or long text fields。

 etc ce。 But some of them are special and used in this one to many foreign key， many to many fields。

 These are the fields that we use to do the linking in our Django data model。

 And so we'll take a look at how these all work。

![](img/b00d8113f3c70b5b53ccd6e71ee50d44_1.png)

So if we have our book instance that links to our book table and then our book table that links to the language table。

 we end up with special little lines。

![](img/b00d8113f3c70b5b53ccd6e71ee50d44_3.png)

In our models。 So most of this is pretty familiar。 that we got a language It's got a name。 Now。

 one thing about Django is it automatically adds the I field， and that's kind of nice。

 So it just you just assume that everything inside of a data model。

 every one of these three in a tables are going to have I fields。

And we don't even talk about the name of the foreign keys。

 even though Djanangle names them the way I just showed you with the Lang_ ID。

We have just a regular thing， so lang。Is suitable as a destination for a link because it has an I D column automatically added by Django every time。

 The book table has an I D column。 So it's suitable for the destination of a link。

 But then Tleniuspi there。 And then there's this language。 And that's the first one。

 And so this is where we're actually modeling the need to have links between the book table and the language table。

 So we're putting starting at the from or the start of the arrow。

 And we're saying there is we need to have a language。But the language is not a string。

 It's not a number。 It is a foreign key， and it's a foreign key into the table called Lng。

 And this table called Lng matches that table。 and then。We have a couple things。

 I'll talk about on deletete in a second， and then null equals true is whether or not it's required。

 And so what it's saying when N null is true is we're allowing emptiness。

 So that means it's possible to have a record in the book table that doesn't have a language。

 And so that's what we're saying we're saying null equals true。The instance table。Points to a book。

It's a foreign key to the book model。And it has a due back。 Now， the status was in there。

 And so I sort of shortened it a little bit。 But we have a foreign key that points into it。

 And so again， we're defining where we have the beginnings of the arrows。

 because the ends of the arrows is kind of implicit。

 Django gives us sort of the primary keys for each row in these models automatically without us having to say it。

 But you can put it in a Django model if you want to override the name of it。

 But you just want a column called I D， which everybody pretty much does。 You just leave it out。

 And Django puts it in for you automatically。

![](img/b00d8113f3c70b5b53ccd6e71ee50d44_5.png)

![](img/b00d8113f3c70b5b53ccd6e71ee50d44_6.png)

And so again， you see this from the point of view of the data model where we have the arrow between book and language that's a many to one。

 and then a book instance to the book is a many to one as well。

 and so those foreign key links represent the arrows in this data model。



![](img/b00d8113f3c70b5b53ccd6e71ee50d44_8.png)

![](img/b00d8113f3c70b5b53ccd6e71ee50d44_9.png)

Now， just to sort of review， you might have done already some of these migrations。

 So once you edit these data models and you get them right。

 you have to do a two step process to get them so that your database， it reflects these models。

 The first one is you have to make migrations。 And so the way the make migrations works is it looks through all of the applications that are registered in your settings Py。

 and for everyone one， it checks to see if the data model has changed since the last run to make migrations。

 So make migrations actually creates files。In your application， based on the models do Py。

 and it's a series of files that like 001 here， that's the first one。 there might。

 if we changed it and then run make migrations again， there be an002。

 And what it would do is the 002 is evolution beyond the 001。Now， the migrations are portable。



![](img/b00d8113f3c70b5b53ccd6e71ee50d44_11.png)

In that don't， they're not specific to the MySQL database， the SQLI database， etc ce。Now。

 the migrate reads those migrations and then updates the actual tables in the database。

 and so the migrate is mapping the portable representation of what's supposed to be in the database into the actual physical representation in the database。

 Now you'll notice if you run these both twice once they work。

 they'll say no changes detected because in the case of the make migrations。

 it looks at your models and then looks at what's in the migrations alreadyances it's a perfect match。

 and then in the migrate， it looks at what's in the migrations and what's in the database table and says。

Everything's there， everything's been done。So this can be confusing because。In my documentation。

 I'll say run and make migrations and you say no changes detected。

 Now there's another reason why you might get no changes detected and that is that you have to add it to the settings py file before you can it's going to be detected so you might have edited a model py file and changed it。

 but if it's not the application is not in the settings py then it won't be detected。

 So make migrations is reading through all the applications listed in the settings py checking for differences。

 deviations between models py and the migrations。 It might be a little easier just to show you these things。

 well， that's coming out I'll show you those in a second。



![](img/b00d8113f3c70b5b53ccd6e71ee50d44_13.png)

If we look at what the migrate does， the migrate creates the SQLite file。

 and so we can take a look at this file， you don't have to。

 but you can take a look at this file after you've run the migrate。

And you see theres so I have a tables book 1 print a percent that's actually a wild card because the like statement that's like the like statement in SQl。

 So that says show me all the tables that start with book1。 And you see that there's three of them。

 book 1 underscore book book1 underscore instance and book1 underscore lay Book1 is the application because Django has project and then applications within project and book1 is is the application that we're doing。

 and then instance book and layng are the three models that we've specified in our database in our Model Py。

 So if we take a look using the schema command of book1。

 we can see how the migrate statement produce the table。

 And so we created a book1 do underscore book。 It has ID auto increment。

 all that stuff from the SQl stuff it's got a title it's got IPN and then it's got this L I that's the foreign key。

 So it's actually building the foreign key the right way now。



![](img/b00d8113f3c70b5b53ccd6e71ee50d44_15.png)

In SQLite， there's one way of building foreign keys and mySQL there's a different way of doing building foreign keys and so that's all something that the migrate operation understands how to build。

And if you look at the language， you just see that there's an ID column that's automatically produced and then a name。

 and then if you look at the instance， you see an ID and a dude back， which is date and then。

And then you see the book ID， which is the foreign key into the book table。

 and so you can kind of see how these tables implement the links as described in the picture。



![](img/b00d8113f3c70b5b53ccd6e71ee50d44_17.png)

Now， I was telling you that about this on delete。 So the problem is。

 is what happens when you have a row in one table， like in the book table that's pointing to a row in a language table and you' got records that are pointing there。

 So you've got two books that are pointing to English in this situation。

 And then you delete the English row。 What happens to the rows。

 And you there is a couple of different things that you can do。

 But the two common things are is cascade and what cascade says is that you're going to delete all the rows。

 if you delete those rows， you're going to delete all the rows that have the matching language Id。

 and set null basically instead says， oh， that's okay。

 we're just going to wipe out these and make them null。 And in this English， I mean。

 in this language， if we delete a language from the language table。

 we probably just want to set it to be null。

![](img/b00d8113f3c70b5b53ccd6e71ee50d44_19.png)

![](img/b00d8113f3c70b5b53ccd6e71ee50d44_20.png)

Okay， and so if you look， you'll see that the relationship between。The book and the language。

 which is right here。 If we delete one of these things。 we set it to null。

 We set the corresponding language to null。 We just throw away these links in a sense。

 and that's okay because books are allowed to not have languages。

 And so languages are allowed to be null， null equals true， languages are allowed to be null。

 But if on the other hand， we get rid of a book from our books table。

 then we probably want to wipe out all of the instances that are related to that book。

 And so that's why we in here， say on delete cascade in the book foreign key entry。

 And we don't say null equals true。 And so set null requires you to be able to say null equals true。

 So you have to say， I I am willing to allow nulls in this column。 oh， and by the way。

 if the thing that this column points to is deleted， then set it to null。

 which means don't delete the row， Cascade means if if the thing we're pointing to is deleted and delete this row。

 because we don't want inconsistent data。 We don't want those little things pointing off。



![](img/b00d8113f3c70b5b53ccd6e71ee50d44_22.png)

![](img/b00d8113f3c70b5b53ccd6e71ee50d44_23.png)

Absolutely nowhere and making absolutely no sense。So up next。

 I want to go into a little more detail on models， migrations。

 and databases and how they work at a bit of a low level。

