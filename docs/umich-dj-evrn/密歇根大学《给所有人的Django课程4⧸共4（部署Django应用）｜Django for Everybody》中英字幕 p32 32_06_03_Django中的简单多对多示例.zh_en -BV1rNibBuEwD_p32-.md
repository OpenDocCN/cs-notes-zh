# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p32 32_06_03_Django中的简单多对多示例.zh_en -BV1rNibBuEwD_p32-

And so the many to many is a situation where you have sort of somewhere between one infinity and somewhere between one infinity on both sides now。

What we need to do to model this is we can't really model many to many in a relational database。

 so what we do is we break it into two one to manyies and we have a junction table。

You could call this the author book table。 Later， I'll call this the authored table。 Like， you know。

 who are the authors of。 you could call it authors of。 And it's a table。 that's a very short table。

 And it really just says this author authored this book， this author authored this book。

 This author authored this book。 And then within that， you can say for for this book。

 who are all the authors or for this author， what are all the books right。

 So we call a connection table， we call a join table， we call it a junction table。

 And in D django terminology will call this a through table。

 But its purpose is to have two outbound one to many relationships instead。

 and that basically is just our way of capturing one to many。

 And that's why I said one to many plus one to many equals。Many to many。

 two to many would be sound good， but。

![](img/d77055d5399f830ea496aad796e6e9c1_1.png)

Many too many。So here we are and here are our two many to many relationships in our local library application。

 so a book can have many authors and an author can have many books and that's what we're characterizing with this little1 dot dot star。

1 dot dot star。

![](img/d77055d5399f830ea496aad796e6e9c1_3.png)

And the same is true like a genre can have many be associated with many books， and interestingly。

 the zero dot dot star， that's special where the book connects to genre and it zero dot dot star coming out of the book。

That means it's a minimum of 0。 And all that's really capturing is that。A book can have no genres。

But a book must have at least one author。 and whether that's true or not。

 that's what this data model is saying。 This data model is saying。All books have at least one author。

 but they have zero or more genres， but they have one or more authors。

 And that's the the subtle difference between0 dot dot star and one dot dot star。

 And that's the kind of clever little application features that these。

Applications and these data models can capture beautifully。

 and we'll see in a second how that turns into a Django model that is then a business rule for the data。



![](img/d77055d5399f830ea496aad796e6e9c1_5.png)

And so this is how it works。We're going to create two tables。

 the book table in the author table and every table every row is going to have an ID auto increment primary key column。

 and then we're going to have these outbound foreign keys from authored again the authored table is the start of the arrow。

 so it's the one that has the foreign key column in it and the destination of the arrow is a primary key in that other table。



![](img/d77055d5399f830ea496aad796e6e9c1_7.png)

Now， what we're going to do is and we'll see how this works is that Django allows us to create these kind of virtual。



![](img/d77055d5399f830ea496aad796e6e9c1_9.png)

Attributes， and we'll name them cleverly。 The name of them doesn't matter。

 but we'll basically say inside of author， we're going to have an attribute of books。

 which is automatically going to be populated by all the books the author wrote。 And in book。

 they'll be this little virtual thing。 It's actually computed。 It's not stored。

 It's actually computed。Based on reading the authored table。It'll be authors。

 which is a list of all the authors， and so this is a convenient way because in Django they kind of want to hide this middle table it exists。

 and as a matter of fact。You can write， oh， drop my pen。my pen。Pick the pen back up。

Make sure the audio is still working， the audio is still working。

 yeah it is audio still working life's good。Sorry about that slight interruption。

So Django tends to want to hide this through table and you can actually define models where you don't even give that a name and it makes one up。

 it still exists and exists exactly like it's shown here。

 but I would rather in my data models show you this table so you have a better understanding。

 but if you see other data models where they don't explicitly mention this and just have a many to many and it actually makes this table up for you。

It don't don't get all freaked out if you see a model that doesn't have the through table explicitly modeled。

 I like to do it， so here we go， so here we have some models so we have。



![](img/d77055d5399f830ea496aad796e6e9c1_11.png)

The book field， the titles just a bit of the book， then authors is a many to many field。

Going toward the author table， that's the far one， but the through table is authored。

 So the intermediate table， the junction table， the through table is the authored table。

The author is on the other side， It has the author has a name and it has books。

 which is this books is this kind of virtual set in there that's a manyto many field derived pointing at the book table with a through table of authors。

 So the junction table we mentioned the junction table the same in both of these right So this is going。

 you know， from one to the other。 and this is kind of going back。 and these are like virtual。

 it's not data that's stored in the row of each row of the book。Table。

 it is data which is derived for you if you ask for it， when you retrieve a book， you can say。

 what are the authors of this book， it's a convenience in a way。



![](img/d77055d5399f830ea496aad796e6e9c1_13.png)

And it also is telling Django about the foreign keys and where to store the foreign keys and the fact that it's a many to many field that's all setting up。



![](img/d77055d5399f830ea496aad796e6e9c1_15.png)

This stuff， so that Django， when you start putting stuff in these tables。

 Django automatically puts the right stuff into those tables。



![](img/d77055d5399f830ea496aad796e6e9c1_17.png)

And like I said， here's the through table I called authored。 I thought that was kind of clever。

 and the through table is modeled as foreign key this way， foreignign key that way。

 And so that's not a many to many。 It's a foreign key， but I've named these。

 and I match these things up。 Now， the ondte cascade。Is the same as the other one。

 these are now just these are two one to manys right the through table has a one to many going this way and one to many going that way。

And ondelete cascade and so just the whole idea of a book author combination is if if the authors are deleted。

 if you delete an author， you want to delete all the entries in the authored table that correspond to that author if we do to delete a book you want to delete automatically all the entries in that and so that's what ondelete cascade means in the authored table and that's clean this table up if things are deleted but from the outside two table。

 so that automatic cleanup is done for us， which is quite nice and we just request that with this ondelete statement so。



![](img/d77055d5399f830ea496aad796e6e9c1_19.png)

![](img/d77055d5399f830ea496aad796e6e9c1_20.png)

I don't know。That's a beautiful thing。That is a beautiful thing。It's so pure and so simple。

And I don't like it when you don't put the authored table in there because you can sort of do this and then it'll make the authored tabled up。

 but then there's certain things that don't work as well and I don't like that。Okay。

So let's just say we created this models。poy file， of course in Dj4 samples if you checked it out and you ran make migrations it run makes them all。

 but let's just say this is the first time you'd run make migrations and then you'd see that it's creating the migrations and then you do the migrate which of course as we talked about in a previous lecture that is what takes from the migrations and then updates the database and both the make migrations and the migrate are checking to see which ones have already been done so make migrations is looking for changes or deltas in the models。

pyy file and the migrate is looking for deltas in the migrations。



![](img/d77055d5399f830ea496aad796e6e9c1_22.png)

And again， remember that the list of the things that both of these is looking at is based on the settings py file。

 and it's the installed apps variable in the settings py file。

 So I put this note in because students are always saying my make migrations didn't do anything。

 Well， there's one or two reasons it either is not in the settings py file， or it's already done。

 So I don't know which of those it is， but those are the two things to look for if you think you're running and make migrations。

And it's not running， it either already ran， which is fine， that's totally fine。

 or you forgot to add it to Setting。 Py。

![](img/d77055d5399f830ea496aad796e6e9c1_24.png)

Okay。So here's just a few things that we can do in the shell right again， Python 3 managed Py shell。

 you got to run this from the folder that has managed do Py in it， which is the。

Project folder projects have many applications。And so because the Man PY shell starts up in preloads。

 again， the managed PY shellll reads all of the apps that are in Se。

pyy loads their models and a few other things from those preloads them。

 and so that's why book many dot models exists at the very first line here because Django in a sense has woke up and preloaded all of the classes and things that are there。

 so it's in a Django application not just in a Python shell。So we import book many as the。

Name of the application and the models are book author and authored。

So some of this whole starting to look familiar to you， we create an object of typebook book model。

 the titles networking， and then we save it， remember saves a thing that transmits the in-memory object into the database and populates that ID field and when you start linking these together。

 populating the ID field is very important， we do a raspberry Pi book and we save that and now we're going to make an author for Kristen and save that and author for me and we save that and so at this point we have made two authors and we made two books。

 but now we have to connect them together and so what we're going to basically say is we're going to create an authored record a record in author with a book a connecting book B1 with author A2 and save it。

 then book B2 connect it with author A1 and save that。

 book B2 connecting with author A1 and save that， so that's throwing three records into the author table making those connections。

Setting the foreign keys like it's just reading the ID field from these A1 a2 and B1 B2 and that's like inserting records into the author table in the book underscore ID and the author underscore ID。

 right？Now， remember that in book， we have this virtual set called authors and in author we have this virtual set called books。

Again， that's not actually stored in the book table or the books table。

 it is generated by reading through the appropriate things in the author table。

 that's how it's generated。So， if we。If we say for book 1 dot authors。

 this is like that little virtual thing。 and it reads all of the corresponding authors from the author table and then values just says actually go retrieve them。

 And so now we see that the authors for Book 1 is a list of just one author named Severance。

 Book 2 authors's values is a list with Kristen and me。And then author one。

 who's at author one is Kristen。 What books did she write？ Well， she wrote the Raspberry Pi book。

 We co-rote that book， and then author2， what books did he write， Well。

 he wrote the networking book by himself。 and he's a coauthor with Kristen on this other book。

 And there's all kind of other things that you can do。

 but you kind of get this idea that you know you can you don't have to do too much with the authored table。

 but and then once you got things all set up， you can sort of like walk the authored table without actually knowing it because we preset these things when we made when we made the data model and said what the through table was。

 And so the through table is sort of。

![](img/d77055d5399f830ea496aad796e6e9c1_26.png)

Magic thing that's useful， but we don't really explicitly deal with it too much now next I'm going to show you a different example of many to many just to sort of bring this home a bit。

