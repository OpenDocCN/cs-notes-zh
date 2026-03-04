# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P30：1_表结构修改技术.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So the first topic I want to talk about is after what we do after a create table。



![](img/b8de8a5a9c80a08b613e580eb8ebf35b_1.png)

And so up till now I keep talking about like， oh， the create table and it's a you got to get it right and if you get those columns too short。

 then you're in bad shape。That's not exactly true， right， You can absolutely make mistakes。

 Like in this one， the content I'm making some blog posts and the content I make 1 thousand characters。

 and you might make a database table and think， well。

 my little little paragraphs are going to be 10 characters。And about that much。

 text fits nicely into 1000 characters。 But then some times more and you're like， oh。

 crap 1000 characters is not enough。 And you're like， oh， now what do I do， Well。

 it turns out that this alter table capability in most competent databases is amazing。

 meaning that you can't change the schema。😊，And it will auto convert all of the data to the new schema all while the application is running。

 And even though we're doing data mining。 So you're not always working with a live database， Li。

 if you are building an online system， because you might actually be talking to a database where there is a front end to it。

 But you're like talking to the back end。It can do an altar table while it's live。 now。

 and you got to be careful because if you're like taking a column out or adding a column in。

 then if the application starts。Sending data to a column that you just removed。

 Then that part will blow up。 But in this case， I made my content of Rchard 1024。 And it's like， no。

 that's not right。 But I could easily fix that with an altar table。

 Another kind of thing that you might do is you wouldn't name your column oops。

 but you might be copying and pasting。 And I do this all the time。 You might be copying it。

 tasting your create statements。 And then you leave something in， like in the favorites。

 And so the comments， there's a text area。 And the favorites is a number。But I copied and paste。

 I was't too much of a hurry。 And so I left the text thing in， but I forgot to add a number。

And I'm like， am I doomed。 And actually， the application has already started。

 and it's actually starting to load data。 And you got to fix it。 Well。

 the good news is that's the altar table。😊，Right， we make a mistake and a schema。

 or the schema is going to evolve。 And so we create it。

 And even though these two look like they happen one right after another， I mean。

 Al table drop column oops could happen days or weeks or months later。

 And once the database starts altering it and doing that work。It's fine。 And again。

 if if nothing's looking for or storing stuff into this column， oops， then we're good， right？

 And so again， you can do this on live databases。 And so that the little mistakes I made is I added a column So you can drop a column。

 I had a column called content It was varchar 121024。

 And it really needs to be text so it can be unlimited length。 And I forgot to pet the column fab。

 which is how much you like something。 and it's an integer。 So you can add a column。

 you can drop a column you can change a column。 And it doesn't all have to be columns。

 If you have like a foreign key relationship and you got it wrong or uniqueness constraint。

 Sometimes you make uniqueness constraint。 and you need to have two of your columns unique instead of one column。

 And you just like change it。 then you got to like drop the constraint sometimes and then add a new constraint。

 But go talk to stack overflow and say how do I change a constraint in a Postgres database。

 And they'll be like al table or sometimes drop constraint or whatever。 So And like I said。

I love the fact that it can run on a live database。

Another technique that we're going to use is the basic notion of reading SQL statements from a file。

 And so I can hand you， and I do hand you some of these files。

 usually when I'm giving you the main file for the lecture。

 I kind of want you to cut and paste and see what each thing does。

 But what if I'm going to load 1000 records。 Well， I'll just give you the insert statements in a text file with 1 thousand0 insert statements or an insert statement with 1000 values。

And you're like， I want to run this file and so you just say backslashI and then you give the file name。

 in this case you would have downloaded it into the same folder as you are running your PGSQL command。



![](img/b8de8a5a9c80a08b613e580eb8ebf35b_3.png)

Okay， so that's changing the schema and running scripts。

 and up next we're going to talk about how we handle dates。

 Ds are a real important part of databases。

![](img/b8de8a5a9c80a08b613e580eb8ebf35b_5.png)