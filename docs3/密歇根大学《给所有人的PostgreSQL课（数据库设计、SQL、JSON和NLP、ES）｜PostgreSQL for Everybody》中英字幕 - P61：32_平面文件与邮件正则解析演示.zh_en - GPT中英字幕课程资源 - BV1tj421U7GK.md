# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P61：32_平面文件与邮件正则解析演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to another SQL walkthrough。So we're going to now grab a flat file that's just a flat text file and read through it as if we are going to- we're going to load it into a database。

 we're going to make one column， put each line in the column。



![](img/e93034aa19f2b906bb4095f4d29efcaa_1.png)

So we're going to make a line， we' could a table call inbox。

 and we're going to read it in as a line of texts。

![](img/e93034aa19f2b906bb4095f4d29efcaa_3.png)

Right。And so the data we're going to look at is from my Python for everybody class。

 the mailbox short， and we're going to be reading through these records and we're going to use things like regular expressions to pull things out of these records。

 So we're going to write SQL that's just kind of like reading a flat file。

 So a select is going to read this whole thing。 But first we've got to get it loaded in。

And so there's a couple ways that we could get this loaded in。 We could do a W get。

 We could pull it down into our local directory， and then we would copy from embok short TXT。

This file off our home， our local directory and with this telelimiter。

 And so what's going on here is。Naturally， the copy reads this line by line。

But we actually don't want to split it。 We want the entire line all the way from the beginning to the end to be into one column。

 so it's going to split by new lines。

![](img/e93034aa19f2b906bb4095f4d29efcaa_5.png)

And so what you pick is you pick in this case， we don't want it to split。

 so we're going to say we're not going to use delimmers at all。

 so we're going to use a delimiter of a bell， and that's a character that doesn't appear anywhere in this file。

And so I could do that， but I want to do something even more awesome。 I want to say copy inbox。

 which means load Mbox。🤧嗯。From program。And we're going to run W get Now these are some parameters。

 this is quiet this is the send the output to the standard out and this at sign is an extra parameter and then that says retrieve all this stuff and feed it in the background into copy and with delimiter E007 so let's go ahead and just run that one。

Who's come back。So that did it， it loaded it， it pulled it off the internet。

 and then it put it right into Mbox so I can say select star from Mbox。人们。5ve。嗯。Of course。

 I wouldn't hurt if I could type selector right？So there we are。 there's our five rows。

 our first five rows of it， and it's just this exact thing stuck in。 Now we could do tricky stuff。

 we could pull things out and we could create foreign keys for some of these things but for now we're just going to play with it from a regular expression perspective。

So let's take a look at all the lines in the inbox， where line starts with a letter from Anna blank。

So that showing these things。 There are 27 rows， and that's the actual lines that start with from and blank。

 And so that was one we can ask。 We can say， you know what。

 I don't just want the line I would like you to scan up to。The first at sign。

 and then go up to the next space。So what we're going to do is we're going to pull out this email address and so what we're going to do is we're going to look for the substr line。

 so line is the whole thing and we're going to pull out the entire email address right there。

And so we're going to look for， we're going to pass the line through the following regular expression。

 we're going to look for a blank。Start extracting。Than any character one or more times。

 followed by Nats sign。Follow by anything but a blank。 So this is a bracket。

 So it's a single character， But the cart in the beginning is not。 So that's not a blank， plus。

Appends to that， says one or more times。 in the parenthesesis says stop extracting， Fo by a blank。

And so this is we're going to apply this to the lines that start with from space。

So we're going to pull out the email address from each of those lines。

 and so now we've got the email address and we're using regular expressions。Okay。

 this is kind of a mess because this whole little substr line where we're extracting the email address。

 we got to repeat it a couple times because we're going to do a group by。

And we're going to group by in effect the entire email address and we're going to order by the count of the email addresses。

 we're going to select the email address and the count of the email address it's kind of like running select distinct but counting the ones as you're throwing them away where line is like from starts with a from space group by the email address order by the count of the email address descending。

So let's run that and it is going to make us a count。 Look at that Shenwen lien everything。

In Python for everybody， Chenwen is five times， appears five times。

 and so she had five email messages in the first month or so of 2008 in the Sch project。

 which is where this all came from。

![](img/e93034aa19f2b906bb4095f4d29efcaa_7.png)

OkayAnd so we can do the same kind of thing by if we really wanted to not repeat the substr line and regular expression。

 we could have done this as a subselect so right this here is that this string。

But there's no select distinct。 So that's all of them。

 So you can think of this subselect as producing a one column table right So that subselect produces a one column table and then what I can do is is get the email and then count the email again。

 this is like a virtual table from the subselect group by email order by count email desks this is a more succinct way to say it because I'm not replacing I'm not repeating the substr over and over and over again。

 So this is gonna to give you that same count but you know most developer database folks will tell you don't use subselect if you don't have to and what I would say is。

Don't use subselect and online things。And you can use sub selectlect in data mining applications as long as you don't have to wait too long for them to run。

 If it's the difference between 4 seconds and 6 seconds， as long as you got to run it not too often。

 you're probably okay。 So there you go。 We've turned。 We've turned this flat text file。

 we retrieve it automatically right on the copy， Turn it into a bunch of rows one column。

 And then we played with it with regular expressions。 Hope it helps cheers。

