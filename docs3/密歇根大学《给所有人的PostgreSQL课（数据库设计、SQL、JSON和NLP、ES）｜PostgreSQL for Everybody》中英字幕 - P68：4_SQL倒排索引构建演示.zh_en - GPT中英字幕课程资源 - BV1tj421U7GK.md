# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P68：4_SQL倒排索引构建演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to a walkthrough on building inverted indexes using SQL。

 So this is sort of an extension of the lecture。 we're going to go into some more detail。

 Now the key is is there is this file。The sample SQL commands for this lecture that you can be working with。

And that I'm expecting it to have and here's the URL for it， wwjpgfree。com/s/05foldtext。sqL。

And so I'm going and this you can go through this yourself because these commands just work every once in a while you might have to delete some rows or do whatever。

 so I'm just going to go through and narrate these starting with this strings ands and rows and I've got a Jupyter notebook that's already in the PSql client so I can you know I can do s Dt and see I got some tables。

 So I'm starting now with a pretty fresh I've got rid of a lot of stuff cleaned it all up。

 So let's take a look at some of the commands So the first the first thing that we do is explore the string to array function。

 And that basically is like split in Python and it basically gives you an array of strings from a string and a delimiter。



![](img/d3d291188f9a1470e9d53a0ffdb24458_1.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_2.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_3.png)

And then unn， this is really a lot of things happen that are cool like this in so if we say select unn string to array hello world with a blank is a delimiter。

 we end up with two rows， one hello in one world， so it takes a array that's kind of an horizontal idea or kind of in a single column and it expands it vertically generate is another there's we did this in when we're building。

Fillling things up。

![](img/d3d291188f9a1470e9d53a0ffdb24458_5.png)

Those two things， the string to array and unnest are the keys that we're going to do so what we're going to do is we're going to make a table。

 we're going to create this docs table and it's just going to have two columns serial which is a primary key and then a document which is a text of unknown length and then we're going to throw three documents into this just documents are text documents and where these are strings。



![](img/d3d291188f9a1470e9d53a0ffdb24458_7.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_8.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_9.png)

So we just inserted the values， this is Python and SQL and teaching stuff。

 So three lines have been inserted so so the idea documents are sort of big column text columns full of lots of stuff。

 we're going to start with smaller things okay。

![](img/d3d291188f9a1470e9d53a0ffdb24458_11.png)

So this first breaking the column into one rope per word and a primary key， we can run this。

 I'll run it， and you will see what it does。

![](img/d3d291188f9a1470e9d53a0ffdb24458_13.png)

And so。We're going to select the ID and the keyword。And so so basically we're going to go from docs。

 we're selecting from docs， and then we're going to take D dot doc。

 which is the document and then convert that pars it using string to array and then unnest it vertically。

And then we're going to name that column that we get from this unnesting as keyword。

S dot keyword order by doesn't mean much。 And so in the original select I'm getting the ID and this S dot keyword。

 which is sort of the vertical expansion。 So what this really does is this expands vertically each row and concatenateates the ID and the word So row 1 has this the next word is is and then row two has you know more people and you can see and so we've basically turned it into from a table it had three rows into a select statement that gave us。



![](img/d3d291188f9a1470e9d53a0ffdb24458_15.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_16.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_17.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_18.png)

Os。24 rows， which is one row for each word。 but we haven't lost the document I D。

 And that's the key thing that we're going to take advantage of when we do this。 Now。

 there might be duplicate rows because the same。

![](img/d3d291188f9a1470e9d53a0ffdb24458_20.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_21.png)

This the same。The same keyword might be in。One document twice。

 but and so all we're doing is it's the we're getting them mapping an ID。

So I'm just going to add distinct。And then that just discards any duplicates where those words are twice。

 and so I still got 22 rows， but this select distinct is a cool thing now。



![](img/d3d291188f9a1470e9d53a0ffdb24458_23.png)

I am going to make another table。Doxygen。Which has a keyword。

 which is a text field and then a foreign key into the dock I D。

 So you'll notice that this text gin that I'm creating is exactly matched to that little select statement because it has a document I D in that previous select statement and a keyword。



![](img/d3d291188f9a1470e9d53a0ffdb24458_25.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_26.png)

And so then what we're going to do is the old basic trick of taking an insert。

And then following it with a select， so we're going to insert a series of rows into the dosgen and using that selecting distinct that expands the document vertically。

 but then not losing the ID The order by doesn't really matter here。

 select DocG and then select distinct， really combining the last the previous。



![](img/d3d291188f9a1470e9d53a0ffdb24458_28.png)

And so that made our inverted index。 So that just took that that select distinct and it just inserted it into a table right。

 So now we have this table and I'm calling it my generalized index。

 and I can just do a select from Docs Jin。

![](img/d3d291188f9a1470e9d53a0ffdb24458_30.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_31.png)

And you see the exact same thing now we have a mapping between keywords and document IDs。



![](img/d3d291188f9a1470e9d53a0ffdb24458_33.png)

And so now I can ask for all of the documents， I'm going to add a select distinct doc from docs。

I'm going to join on Docs Gin where the ID matches and then look for a keyword。

 So this where clause is looking down the keyword column in the in the index and it's throwing rows away and then I'm matching so this will give me。



![](img/d3d291188f9a1470e9d53a0ffdb24458_35.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_36.png)

Actually， I should add an ID on that， select Dis。Id Comoc， that would make that one better。



![](img/d3d291188f9a1470e9d53a0ffdb24458_38.png)

So now we see the documents that have the keyword UMSI in them。

 and so we used to join through that little Gin table， the Dos Gin table。

 because we have a foreign key from Docs Jin into Docs。



![](img/d3d291188f9a1470e9d53a0ffdb24458_40.png)

We can also use the in instead of the equal sign so we can say G keyword in fun and or people。



![](img/d3d291188f9a1470e9d53a0ffdb24458_42.png)

And then that allows us to have more than one any of the above。That's what the the in operator is。

 it's like here's a set and it's kind of any。 you could think of it as any。



![](img/d3d291188f9a1470e9d53a0ffdb24458_44.png)

So part of what I'm doing here is I'm giving you lots of excuses to learn a little bit more SQL。

And so I can even send a whole phrase right， so if I say in this next one。

 any string to array I want to learn broken into spaces。

 then what that does is that that string to array an array of words。

And then any is any of these words。 It's kind of like。

 oh it's a little different version of the in clause。

 And so I can actually have a whole phrase that string to array is going to break me into pieces。

 And so we can find。

![](img/d3d291188f9a1470e9d53a0ffdb24458_46.png)

![](img/d3d291188f9a1470e9d53a0ffdb24458_47.png)

AnyThe word I or want or to or learn， and we can find the rows that say that。Now。

I'm going to do the same thing， except I'm going to search for lemons and neoons。

 And this is like why stop wordss are important。 And you'll notice that I'm looking for the meaning of searching for when I say search for lemons and neoons。

 The and doesn't contribute to the meaning of my search， right？

 I really was looking for the meaningful words where maybe search probably lemons and privately neon。

 And I bought got two lines。

![](img/d3d291188f9a1470e9d53a0ffdb24458_49.png)

I should probably add an ID on that one too。

![](img/d3d291188f9a1470e9d53a0ffdb24458_51.png)

you。I'll add an ID to that select distinct on the side with this that can go sideways one。



![](img/d3d291188f9a1470e9d53a0ffdb24458_53.png)

And so we found some documents。 But what they were matching is the word and。

 they didn't match anything else。 They match the word and， Ca I。

 it's any of those words in search for lemons and neos。 So we're going。

 we're going to do stop words next。

![](img/d3d291188f9a1470e9d53a0ffdb24458_55.png)

And so that's that's basically we've made an index in this。

 I keep doing this join Doxgen so that the document ID is equal to the Dosgen document ID and that connects the documents。

 but then I use aware clause to only pull out the things in the docsG so we could let let me add another little select statement here and let me just do this one here。

And a select statement。Let me do the just without the join。ちち。ID a keyword。From。Docs gin。As G。2。

So here I'm saying select distinct ID keyword from docsgens G where G dot keyword equals UI。

 this basically is telling me all of the documents。That mention U MsI。Oh yeah。嗯。

IThat's called doc ID in that one。So one of the things I do when I'm coding is I edit things in a text editor and then I go paste them back and forth。

 and then I'm always getting them right， select key flip the order of that keyword。Commonoc Ie。

So my ultimate query is select keyword commdoc ID from Docs underscore Gen as G where G dot keyword equals UMSSI。



![](img/d3d291188f9a1470e9d53a0ffdb24458_57.png)

Okay， so you can see I got these keywords， but really I've got the doc ID and so that this is where I'm using a join。

 I'm doing the wear clause reducing what I'm seeing from the Dos Gin table with the wear clauses and then I'm saying。

 oh here are the documents and then I just go use a join to pull the actual documents out because I have the ID from the doc docs underscore gin。



![](img/d3d291188f9a1470e9d53a0ffdb24458_59.png)

And so there we go。