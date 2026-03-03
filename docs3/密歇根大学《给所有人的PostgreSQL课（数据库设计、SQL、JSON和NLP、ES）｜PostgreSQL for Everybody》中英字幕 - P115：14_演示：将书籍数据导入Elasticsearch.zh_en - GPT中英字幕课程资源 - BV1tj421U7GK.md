# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P115：14_演示：将书籍数据导入Elasticsearch.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to another walkthrough for Postgres for everybody。 Of course， today。

 we're going to play with the code for elasticse， which is in effect to compare and contrast。

 So we got a number of different bits of sample code。And I'm going to start with elastic book。

 so let's take a look VI。Elastic book got P Y。

![](img/e5a4177a7f6989df650e9136f7aa6331_1.png)

So elasticbook。pyy makes a connection and fills up a bunch of stuff with elastics with reads a book text from Gutenberg and then fills it up So the first thing you got to do is you got to put your credentials。



![](img/e5a4177a7f6989df650e9136f7aa6331_3.png)

Oops， that would be my hidden one。

![](img/e5a4177a7f6989df650e9136f7aa6331_5.png)

Hidden disk has some sample credentials， and it's important that you set the elastic here。

re in this particular example， we're using the same user and index。

 So we're going to have an index that's the same as the user name and whatever your autograder or whatever will' give you these details to place in here。

 So you copy this into hidden dot py。 and then you edit and put the real values in。

 So you will notice that in the beginning of elastic book dot py。

 you see that it's going to import hidden。

![](img/e5a4177a7f6989df650e9136f7aa6331_7.png)

And then later， it's going to grab the elastic search secrets， and then it's going to create。



![](img/e5a4177a7f6989df650e9136f7aa6331_9.png)

An elastic search client。

![](img/e5a4177a7f6989df650e9136f7aa6331_11.png)

And then we're going to actually use in this case the same index as for the user we' reuse one index over and over and over again。

 So if I take a look at the basic outline， it's going to wipe out the index which is like dropping a table and then it's going to recreate the index and then it's going to read through these paragraphs and do some parsing so I'll come back to that because it's going to take a while and so I want to go ahead and start this Python 3booked Py。



![](img/e5a4177a7f6989df650e9136f7aa6331_13.png)

![](img/e5a4177a7f6989df650e9136f7aa6331_14.png)

And it asked me for。T X T， so you'll see it's going to drop。o。Oh， don I type wrong， oh， 14091。txt。

 what I type？14091， LSP1，4 star。

![](img/e5a4177a7f6989df650e9136f7aa6331_16.png)

Start at TXT。Oh， PG 14091 do Txt I forgot the G， so let's go ahead and start it。Clear。2 two。手。P G1，4。

09，1 dot T X， T。Okay， so it's going to drop the index。 So it did that。 and it started the index。

 tells us something about the index。 And now it's off and running。 So we'll come back to this。

 It's got a bit of work to do。 So it's filling up the elastic search right now。 So let's take a look。

 We saw it。

![](img/e5a4177a7f6989df650e9136f7aa6331_18.png)

![](img/e5a4177a7f6989df650e9136f7aa6331_19.png)

Open the book file。Get our secrets， set up an elastic search instance in Python using。

 and again you have to do a PP to install this elasticastic search library once that's installed in your virtual environment or whatever。

 you're good to go。

![](img/e5a4177a7f6989df650e9136f7aa6331_21.png)

![](img/e5a4177a7f6989df650e9136f7aa6331_22.png)

And then we're going to basically just read。And we're basically looking for blank lines and we're going to concatenate these lines together。

And make a paragraph out of them。

![](img/e5a4177a7f6989df650e9136f7aa6331_24.png)

Okay。

![](img/e5a4177a7f6989df650e9136f7aa6331_26.png)

Here we are concatenating the lines together， it's a bunch of blank lines。

 so let's just take a look at the file。

![](img/e5a4177a7f6989df650e9136f7aa6331_28.png)

ThePG 14 text。

![](img/e5a4177a7f6989df650e9136f7aa6331_30.png)

So what I'm doing if you look at this is I'm taking。



![](img/e5a4177a7f6989df650e9136f7aa6331_32.png)

Taking and reading all these lines， looking for a blank line and then concatenating these so that they're one long line。

 which means I'm getting rid of the new lines at the end。 I'm concatenating to run a blank in。

 So you see， I read a line， I trim it， Then I read the next line。

 I trim it and concatenate it with a blank。 and then at some point， I get a blank line。

 and then I insert this whole paragraph。 this whole paragraph。



![](img/e5a4177a7f6989df650e9136f7aa6331_34.png)

![](img/e5a4177a7f6989df650e9136f7aa6331_35.png)

![](img/e5a4177a7f6989df650e9136f7aa6331_36.png)

Gets inserted at this point in this body dock， right？



![](img/e5a4177a7f6989df650e9136f7aa6331_38.png)

Okay， so it's accumulating it。 And then when it finds here a blank line。

 then it says it counts how many paragraphs it is， puts content in。 Now。

 one of the things that's important for a。

![](img/e5a4177a7f6989df650e9136f7aa6331_40.png)

Elastic search strategies， you do want a primary key。And so you could。

 there's a couple of ways I could do primary keys here。 I could have them just go up 1，2，3，4，5，6，7，8。

9，10。 That'd be fine。 I could pick random numbers， but I've chosen instead to actually compute a predictable hash of the document contents。

 And so this， I'm going to do a Sha 256。

![](img/e5a4177a7f6989df650e9136f7aa6331_42.png)

I'll do a shot 256 on this whole thing。And what this means is I don't know if this is what you want to do。

 but it's what I wanted to do is I want each paragraph just to be here。

 and now I am keeping track of the where it's offset into the document， so I'm making this document。



![](img/e5a4177a7f6989df650e9136f7aa6331_44.png)

A Json document in this case， it's just a dictionary。 So we have the offset。

 which is how many which paragraph and the content and then I'm going to insert it and have a primary key。

 which is a big long hex number， but it is it's a hash。

 it's a really well built hash because it's a shot 256 hash。

 And so what happens is is if I'm going to use the primary key here and I'm sticking into the index with that primary key。

 it does mean that if I have。

![](img/e5a4177a7f6989df650e9136f7aa6331_46.png)

Exactly identical text。

![](img/e5a4177a7f6989df650e9136f7aa6331_48.png)

I will only get one copy of the paragraph。 Now， you could do something different。

 You might decide that you want to make your primary key just be 1，2，3，4，5。 Now。

 one of the things you don't want to do is you're not supposed to change the type your primary key。

 So this is a string。 If we used U U ID of4 hex digestig will give me back a string。

 you Uid4 will give me back a string。 Pecon will give me a number。 And either of those would work。

 Just don't change it once you start building it。 And so we are adding these documents， you see it。

 say added document。 It's still busily， busily adding documents。

 I don't even know how many it's done。 See how far it is。2000。

2000 paragraphs have been added to our go to the end。



![](img/e5a4177a7f6989df650e9136f7aa6331_50.png)

There we go。 We gotta wait till it's all done， right， So 2200 still loading。 Let's see。

 iss there anything else while we're waiting。Oh， let me tell you about the index refresh。

 So one of the things that we do is。It。Elastic search sort of delays its index processing。

 And we've seen this in other databases where the index processing is delayed。

 And this says stop now and refresh your index。 This is not something that you want to do all of the time。

 You want to say stop and let's recompute the index。 Now。

 if this was a highly scalable server with a whole bunch of clients。



![](img/e5a4177a7f6989df650e9136f7aa6331_52.png)

You wouldn't want to do this index refresh， You certainly wouldn't want to do it every time we're going through this loop right this says lets let's wait and catch up with the index and that's what's going on here。

 And if I was going to start doing some reading of it I would have to do a refresh to recompute the index before we did it so let's see how we did here okay so there we go we loaded 2600 paragraphs。

 17000 lines and 875 875000 characters。So I mean， I built a little tool that we'll cover in a separate video called Elastic tool。



![](img/e5a4177a7f6989df650e9136f7aa6331_54.png)

3 elastic tool。Because there is no PSQL or anywhere that's a client。

 So I built one and this knows from hidden dot Py。 that's type help here。

 This knows for hidden dot P Y。But went and grabbed that index， I can say match all。

And that will actually not match all of them and we'll just get a bunch of them and so it's showing you the documents。

 the first five documents。And so like， okay， we can， then we can see like I can say search for。

Penmanship。And that will find me a list of a number of the documents that have penmanship in them。

 right。

![](img/e5a4177a7f6989df650e9136f7aa6331_56.png)

Right， so I can search for repose。Now one of the things is we've got these IDs here。

Now if everything goes well， I should be able to。

![](img/e5a4177a7f6989df650e9136f7aa6331_58.png)

Do a get based on the primary youth， not penmanship。

I should be able to get a document based on its primary key。 Let's see if that works。



![](img/e5a4177a7f6989df650e9136f7aa6331_60.png)

Boo there we go。 And so I just retrieved a document based on its primary key。

 So that primary key is the Shah 256 of that data right here。 I probably you it。

 whoop should trim the left there。 it's not perfect， so。

That's what this does you can also just wipe out the if I type delete it will wipe out the entire index。

 which I don't want to do， but that's it， so I think that's pretty much all I wanted to show you for this elastic bookloader and so you it's just a parsing of a lot of data and pushing it into a。



![](img/e5a4177a7f6989df650e9136f7aa6331_62.png)

![](img/e5a4177a7f6989df650e9136f7aa6331_63.png)

Elastic search database， so cheers， hope this helps。

