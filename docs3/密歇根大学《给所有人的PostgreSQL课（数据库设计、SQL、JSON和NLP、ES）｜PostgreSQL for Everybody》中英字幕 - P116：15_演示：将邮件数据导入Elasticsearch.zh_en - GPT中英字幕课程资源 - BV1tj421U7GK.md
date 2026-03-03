# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P116：15_演示：将邮件数据导入Elasticsearch.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to another walkthrough for Postgress for everybody。

We are currently walking through the sample code called the El Ma。



![](img/a8f663f95896eb52ada4fd5190f84b82_1.png)

U and as always， you have to have set up your hidden values to get whatever your key and your secrets and your prefixes and posts and ports and all that stuff。



![](img/a8f663f95896eb52ada4fd5190f84b82_3.png)

嗯。And so this particular assignment， we are going to do something I did from Python for everybody where we have an archive of email list for the。

 the Sakai open source project and for 2005 and so this is some data that I used in all of my courses and it's on a super fastt server。

 it's on Dr。 Chuck。net I think I actually。

![](img/a8f663f95896eb52ada4fd5190f84b82_5.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_6.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_7.png)

Cshed some of the people。 So I made my own copy that's really super performant。 This is really fast。

 And so we're going hit this。 And so email is kind of nasty。 and so this is mailbox format。

 and this is pretty nasty stuff and there's all these headers。

 the key to a mailbox format is it starts with from space followed by a series of headers which are sort of key value pairs with a colon in a space and then a blank line and then the body。

And and so that's that's basically how email looks。 And so a lot of this code， unfortunately。

 is just crazy date parsing and crazy， whatever and different email systems and so。

I'm not sure how much value this all is， so but that's the data we're looking at。And we're going to。

 I guess let me just run this Python3 manage that under that that's from Jngle Python 3 elastic mail。

And I can go grab 10 messages and it grabs them And so it's retrieving， you know。

 this and it's parsing it and adding a document， putting the document over and over and over again。

 Som I'm effectively crawling an API full of data like this and I'm filling it into my elastic search so let's walk through the code。



![](img/a8f663f95896eb52ada4fd5190f84b82_9.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_10.png)

嗯。We're going to use the。We're going to use the elasticastic search client that's in Python some of the parsing has to do this parsse mail date。

 that's because different versions of Python have different mail parsers and this is like backwards compatibility。



![](img/a8f663f95896eb52ada4fd5190f84b82_12.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_13.png)

嗯。So we connect up， we're going to use the same index as our user， we're going to drop it。

 and then we're going to create it。And then we're going to start walking through these mail messages。

 there's the base URL and you can see that I can you know get 10 and I can get two more and so sometimes these are real long running processes and you want to restart it if you're really going to do this。

 you probably wouldn't drop this index this way I gave you away So let me just get out of here。



![](img/a8f663f95896eb52ada4fd5190f84b82_15.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_16.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_17.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_18.png)

呃。Okay， quit is not the right thing， so here's this elastic tool。

Python 3 elastic tool so I can say match。

![](img/a8f663f95896eb52ada4fd5190f84b82_20.png)

哦。So there's a bunch of things in there now one of the things you can do here。

 you could actually make it so that this would restart itself by commenting out as dropping and then if you wanted to restart it。

 you'd have to say delete。Because that would basically wipe out the index because now if I say match all。

There's nothing there。 Okay， And， and this delete， this delete command。

 this delete command here is the same as running this。

 but I'm making it simple so that when you run this over and over and over。

 it just starts over and deletes it。 So let me go ahead and start this back up。

 It's going to delete it。 But I also delete it it once over here， so。



![](img/a8f663f95896eb52ada4fd5190f84b82_22.png)

So I'll throw 10 messages in， get caught up with the 10 messages。



![](img/a8f663f95896eb52ada4fd5190f84b82_24.png)

And and so we're reading using requests， we're going to read a bunch of code to read that API if something goes wrong with that API。



![](img/a8f663f95896eb52ada4fd5190f84b82_26.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_27.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_28.png)

Counts to failures at Prince the URL and how many things we've got， right， so I just retrieved。

22400 from that URL，  24，34 from that URL。

![](img/a8f663f95896eb52ada4fd5190f84b82_30.png)

Then it's looking for from space and again， that's if we were going to retrieve more than one at the same time。



![](img/a8f663f95896eb52ada4fd5190f84b82_32.png)

Then it's going to do some bra to get the email， get the email with a couple of different formats。

 then we're going to get the date， hack the date。

![](img/a8f663f95896eb52ada4fd5190f84b82_34.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_35.png)

Then we're going to take the headers and split them and the headers again。

 are all of these guys from here to there with the colon space。

 So you'll see I'm you know going to split things based on colon。



![](img/a8f663f95896eb52ada4fd5190f84b82_37.png)

So that says， let's use a regular expression， go find everything that's。

Not a colonous space up to including a colon a space and then extract all that stuff out。

 so we're extracting two parameters or're extracting everything up to and including the colon space with a regular expression。

 and then we are extracting this second half with a regular expression。

And then we're cleaning all this stuff up， converting an all lowercase。

 and then making a big giant dictionary of key value pairs where this is the key。

 and this is the oops， oops oops oops， oops the value， not including the colon， I believe。

 so that'll be the key。Because it's not， it stops。At that point。

And so now we have in this dictionary， we have the date， which is separately parsed。Okay。

 and so now we're going to actually insert this stuff， so we're going to make a document。

We're going to have the email address。 We're going to have the headers。

 and we're going to have the body。 And then we are going to put that in， store that into。嗯。

St that email into the Elastic search index。

![](img/a8f663f95896eb52ada4fd5190f84b82_39.png)

Then we're going to print out for our own debugging。

The fact that we've added the document it was created oh and here we go that's to position Now I'm using in this case I'm using the starting start。

 which is the number goes up by 1，2，3，4，5 because I want to be able to restart it and so I want to know that I'm on the fourth email message or the 50th email message and printing out the sent。



![](img/a8f663f95896eb52ada4fd5190f84b82_41.png)

And every hundred0th。

![](img/a8f663f95896eb52ada4fd5190f84b82_43.png)

A document。I can see that I added it， come back， I added it， and it was successfully created。

 and then every 100 document， so if I do like 100 more。



![](img/a8f663f95896eb52ada4fd5190f84b82_45.png)

It pauses or 200 more in it'll run。

![](img/a8f663f95896eb52ada4fd5190f84b82_47.png)

Okay。And so this is a lot of code。I mean， this is the nature of scraping imperfect data where you just don't know how good the data is。



![](img/a8f663f95896eb52ada4fd5190f84b82_49.png)

And so let's see that's run in I'll let that run for a while。 So in elastic tool do Py。

 now I can do a match all。And you see that there's a bunch of stuff in there。

 and I can do a search for like Gen Gen Kn。And you see some mail messages from Gen and you see in this case。

 you see the index that it's in， the ID now is an increasing integer and then the source document is got these headers so you'll notice that the headers have been turned into a series of key value pairs which is really just a the headers are a JSsonN object I'm trying to give this to El search in in a way that can be the best possible way。

 and then of course the body is the actual mail message that Gen sent to in this no actually Glen send it to。



![](img/a8f663f95896eb52ada4fd5190f84b82_51.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_52.png)

ItMt be he sent that from Zen to or mentioned Zen in it somewhere。So there you go。

 so I guess you would just hit enter and we get out and so this can repeatedly just go and retrieve and retrieve and retrieve and then put it into an elastic search database so that's a quick walkthrough of the elastic mail code and I hope that you found this useful cheers。



![](img/a8f663f95896eb52ada4fd5190f84b82_54.png)

![](img/a8f663f95896eb52ada4fd5190f84b82_55.png)