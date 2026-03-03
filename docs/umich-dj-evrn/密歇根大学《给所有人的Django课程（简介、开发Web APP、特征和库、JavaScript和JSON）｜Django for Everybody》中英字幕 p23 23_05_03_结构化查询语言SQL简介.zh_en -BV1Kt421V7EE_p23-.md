# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p23 23_05_03_结构化查询语言SQL简介.zh_en -BV1Kt421V7EE_p23-

Okay， so now we're going to actually play with a little bit of structured query language SQL now you can grab at this URL。

 you can grab the instructions that I'm using so you can cut and paste it in。

Now the key thing that you've got to do is you've got to find your way to a shell。

 if you're using something like Python anywhere， you go ahead and open a command line。

Now for reason Python anywhere， most of what we're doing is running Dngo applications。

 but you can really just use Python anywhere as a use Python anywhere as a UniX platform。

 and so get to a dollar sign prompt， these commands can run on a Mac， they can。

 I don't know if you can get them working on Windows but any Linux system but you can also run on Python anywhere。

So there's a command to Linux called SQLite3 and then you give a file name， so SQLite as I mentioned。

 is a very simple database because it does all of its work in one file。

 it's not a slouch as a database in terms of its performance and scalability。

 what it's not good at is handling hundreds of people hitting it at the same time in having the database software。

Resolve all those simultaneous accesses。But if you type SQLI。

 you end up in a command line where you get this prompt SQLite arrow。

 and there's commands you can type like dot tables says， hey， in this database。

 which is in this case， zip。t SQLite3， in this database。

 what tables exist and it says there are no tables。

And then you create some tables now this is our first SQL statement and so you learn something about SQL as it looks a little different than other programming languages and so you say create table。

 that's one statement you can create things other than tables and then you have a table name and then you have some parentheses right and then you have a series of statements about the table that you're working with。



![](img/a06bc6611df71b1b31470302b4487c2f_1.png)

AndSo there's just this little language and there's the name of a column。

 so these are three columns that we're putting in ID name and email， and we have a type。

 this is an integer， varcharR means variable length string field。

Not null means it's required primary key means that it's an auto increment meaning it's going to be supplied by the database it gives us like a handle for every row and then v chart 128 says it's up to 128 characters now a key of this is that。



![](img/a06bc6611df71b1b31470302b4487c2f_3.png)

We're making sort of a contract here and so when we say youve got to do this with 128 characters。

 you can't put 129 in， you can put it up to 128 and if you put the 129，Your database query blows up。

And you're like， oh， that's not very nice and the answer is。

 well you told it 128 so it could optimize how it's going to store the data on disk if you've made it this a00。

 it might start in a different way than if you store 128。

And so the key is is you can make any contract you want but you've got to live by the contract that you make and so it's not the database hates you。

 it's you said I'm going to do 128 and when you do 29 it says you're violating our contract and so it's up to you。

So this whole create table ending in a semione that is a single SQL statement and so we type。

 we can type it in multiple lines and you can kind of see how SQLites using this dot dot dot thing to tell you that it's in a continuation and then finally you finish it all and you put a semie at the end then it does it and then we can ask using dot tables we can say oh。

 is there a table and yes it says yes， it's users。

![](img/a06bc6611df71b1b31470302b4487c2f_5.png)

AndThen there's a an SQLite command called dot schema and that says tell me the schema of users now that's in case you hadn't just typed in the create statement。

 it tells you what create statement it would be。Part of what the database stores in this file SQLite is not only the data for this table called users that you just created。

 but it also stores the schema and so you can say hey what schema is it。

 so if I sent you one of these files like you might upload to my auto grader for example。

 I can inquire into that file using SQLI and I say what schema。

 what tables are here and then I can start looking at the tables and a matter of fact that's how I grade these assignments inside of the computer。



![](img/a06bc6611df71b1b31470302b4487c2f_7.png)

嗯。AndSo this is just sort of going through some， there's a lot of SQL。

 but the basics is actually surprisingly easy to understand and so insert into one of the things that SQL does is it tends to use more than one word and it wants to be something I've met people who have used SQL in their jobs and they just like type it and they don't realize how amazing what they're doing is it is they're like。

 well just insert or I delete some stuff or I select it to read it。

So it was designed to be easy because if we go back to the basics of SQL it was like look there's a lot of complexity down there。

 we want to hide that complexity。 you want to hand something easy to users and I write a lot of very complex SQL and it's a very sophisticated skill but simple SQL is something I think literally everybody should know how to do so insert into then you have a table name and then you have a parenthey list of the columns now these are the columns that you named in your create statement and then values is a keyword and then there's a one to one correspondence between the values that you're going to put in the columns and these happen to be strings so we have little quotes around them。

 they could be integers， they could be dates they could be all kinds of things floating point numbers etc cetera。

 and then this has to meet the schema you can't go putting a number into a string field or a string into a number field and again so that would blow up if you can make all kinds of errors you can either have syntax errors like you forget the word into or something or you can have errors that are bad that your data is bad so。

That's the insert statement， and that adds a row to the end of a table。

The delete statement says delete from。And then a table name and then a where clause we're going to see where clauses a lot in SQL and the key thing is is that every there's I sort of mentioned in the very beginning that there's kind of no loops in SQL and that's one of the reasons that we sort of love SQL is you don't have to write loops and that's because there's kind of an implied loop at the beginning of these commands so when you say delete from users that means delete。

All rose。From users， right， delete all rows， delete everything from users。

So if you don't put this wear clause on， if you don't put that wear clause on it actually deletes everything in there because it's like delete all the rows from users。

 that's the way you know you can kind of phrase it that way。

 delete all rows from users now the all rows part isn't really there but that just means that it's really important to have a where clause so that you're not actually deleting all the rows。

 it's saying delete all the rows from users where the email is equal to TED at Umit EU。

And so what that is is there is an implied loop of all rows on this delete statement and the wear clause reduces that down to actually one or a couple of rows。

 depending on those rows where this isn't like an if statement。

 so this whole thing is like a loop with an if inside of it that's how it works and this is why a lot of people like it is because you don't have to write loops because these things sort of like our loops they have loops built in but this would delete one or a couple of rows depending on whether we had more than one row in this where the email was TedD at Uish study to you。

Update is really kind of cool， you can really zero in。

 you can zero in rows and columns and again update users。

 which is the name of the table set is and then name equals。

 which is the field name and new value and so you can get any you can do all the columns you can do one of the columns you can really zone in on this and then there's a where clause because if you don't put a where clause on the update。

 it implies that this is for all rows and you don't really want to set the name to be Charles for all the rows。

 you just want to set the name to be Charles where this is true because again this you could think of this as like update all rows。

All rows in users set where and so you just always got to be thinking that they're's。So， then。

So the reading is done with select， I wish that it would be create， read， update， delete。

 the C is insert， read is select update is update and delete is delete select is the way that we read stuff out and so select basically takes a list of columns like select name comm email or select star and from and then a table name so this select star from users is quite the almost always the first thing you type select star from users select star from look select star from whatever you can also put a where clause on a select because this again has this implied all rows kind of a thing going on and so select all rows from users where email equals C7 image study and that reads much better when you kind of add that all rows logic to it。

Daases are good at searching， we can do things like add indexes to the databases that make searching and ordering even better。

 so we might say that email please， while you're maintaining this data in addition to maintaining the data。

 maintain an index that has a sense of the order of these records so if I want to sort them as sendingending or descendending。

 then I can get that and I can get that to be efficient。

 and so the order buy is just a thing you throw on the end。

 you can add aware clauseuse here as well and you can have ascending and descending sorts and it worked great。

So this is sort of the first 60% of any SQL is the basic insert， delete。

 update and read and so that is not hard and the beauty is is this essence of SQL。

 the middle part of SQL is portable across all the databases that I just described because every one of those databases that's a modern database was invented after the invention of SQL and so life is pretty good now there are differences because when they first build SQL and like I think 87。



![](img/a06bc6611df71b1b31470302b4487c2f_9.png)

![](img/a06bc6611df71b1b31470302b4487c2f_10.png)

I don't know， forgot that time but when they first built it。

 they did not realize how powerful they were going to be and so there's a bunch of features that got added by the vendors that were extensions and some of them were sort of a standardized there's another round of standardization but then there's a whole bunch of features that are a little different but they have because of competition they have conceptually the same ideas like there's like a limit clause that limits the number of rows or starts after a certain number of rows and it's a little different from one database to the other but this is just a summary you should know this you should just know this forever and ever and ever and then as you run into a different database then you'll learn different features for that。

A tool that you might want to install on your laptop if you want to start playing with these SQLite files and not just using the command line is called SQLite browser。

 you can download it， it runs on lots of different systems。

 you can then open these dotsQLite3 files and you can do stuff to it including execute the SQL commands right in there and so a lot of people find this a more interesting and easy way to interact with these files。



![](img/a06bc6611df71b1b31470302b4487c2f_12.png)

And so that kind of sums up our really quick introduction to single table SQL up next we'll talk a little bit about multiple table SQL and relationships and then we'll also talk about how we connect this all to Django through an object relational mapper。

 so see you soon。

![](img/a06bc6611df71b1b31470302b4487c2f_14.png)