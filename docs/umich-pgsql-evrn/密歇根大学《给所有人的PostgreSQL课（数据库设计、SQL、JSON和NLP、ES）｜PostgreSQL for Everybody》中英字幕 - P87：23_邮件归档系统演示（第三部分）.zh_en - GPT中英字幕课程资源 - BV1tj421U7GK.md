# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P87：23_邮件归档系统演示（第三部分）.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Yeah。So welcome back to the part three of our email archive database full text searching。

 So we're in pretty good shape。 we've got our database all loaded。

 we've got a nice little gist index and we're able to do TS query where clauses Now I want to explore a little bit more of the kinds of things you can do with TSqueries。

 So far we've been doing single word queries like two TS query English Monday but now I want to add some things and so it turns out that this little TS query language is actually a query language and interestingly you can make syntax errors in it So personal and learning when you're querying for personal and learning you are going to find that says I need both of those words it' sort of a standard and operation So that says personal and learning have to show up in those rows。



![](img/82df915a66e997d0c38247160649c022_1.png)

🤧嗯。😊，So。So then we can select the words， but in order and this use the operator that is the less than dash greater than that says personal in learning。

 but personal has to come before learning and so that's ordering so that basically will give us a different set of rows。

I don't know quite know why there's no personal followed by learning， but it's not there。

 we found no rows。Let's see if it goes the other way， learning followed by personal， and there we go。

 we have one that has learning followed by personal。

 so learning followed by personal is the way that I read those。



![](img/82df915a66e997d0c38247160649c022_3.png)

You can add a not， I want learning and not personal。

 not personal exclamation point is not exclamation personal and percent learning means not personal and learning。

Just what you get for that。we got a whole bunch of learning without the word personal。

 so very few people are talking about personal learning or learning in personal in the same sentence。

 so that's that's one。嗯。So the2 TS query， like I said。

 is a language and I'm going to make a syntax error when I say parenthesy personalal learning。

 and that's because inside this string it's actually a query language of its own。

 and so this one is going to give me a syntax error。

Its me a semionee there so it says syntax air and TS query。

 and it just like it didn't like the syntax of it because I used a special character in there and in a way that it didn't like。

 And so if you're taking stuff from the user， you'll use this plane to TS query And so it's like well。

 whatever I I'm just going to throw away things I don't understand rather than blow up so I look at the person learning with a parenthees and it can work right and this is a syntax error from T2 TS query。

 but it's not a syntax and plane it just throw stuff away。嗯。We can。We can do。

We can look at phrase to TS query， I followed by think first we'll do it without phrase to TS query。

 that's what we see that is I followed by TS query and the phrase one is just kind of like a phrase and so it's I think。

Is a phrase， which is I followed by think It really is a transformation from this I space think to I followed by think。

And again， you could think of this as something where you're letting the user type something。

 but you don't want them to have to know how to type all these fancy things that2 TS query。

And if you have。If you have Postgres greater than 11， you can take a look at。

The this is a syntax that kind of came， this minus personal learning is a syntax that kind of came on a Google that is a way to say not personal and learning it's the same as this and so this is web search to TS query a lot of people are going to end up writing kind of grammars transformers that would take these Google style things and then convert them。



![](img/82df915a66e997d0c38247160649c022_5.png)

So that works， minus personal says not personal plus learning。Anywhere in the anywhere in it。

 And then the last thing I want to do is I want to show you something about text ranking。

So text ranking is。ItIt's important to know that text ranking is not really participating in the wear clause。

 All of our optimization and inverted indexes and all the stemming is to make the wear clauses go faster。

 to pick the the documents are going to see once the wear clause is thrown away。

 most of the documents， which is its goal， then the documents are retrieved and that rank。

Right the rank is a computation based on the retrieved documents and then you can order by I can order by TS rank descending and give me the most highest rank and the TS rank takes a TS vector and a TS query。

Cleverly you probably would want them to be the same。

 but it doesn't have to be the same as the where clause， but in this case。

 so what it's saying is like we did pick it and T the double at said that personal in learning were in this document but then we're saying how good were they were they closer etc cea。

 etc cea， et cea。 And so there's a couple of different ranking functions and you can read up on those but the TS rank is just a calculation on the retrieved documents so let's take a look at this and we're going to print the rank out。

So now this is this rank right and it's an ordered in descending order so this one here is the most seemingly most relevant about personal learning and I think if we looked at that one we would probably agree with it and some of these have less and less relevance as they go on so that's really cool and that there is there are more than one ranking algorithms there's those TS rank and then TS rank CD and you can read up on those in the Postgres documentation they both simply are computations on the retrieved record set and they just do a different computation I'm not sure in this case it even throughout some things that were in or out and that's because it does a different calculation and so is there's a whole bunch of research on how to do ranking etc。

 etc， etc。And so that's where I'm going to stop， I've got some stuff where you can use regular expressions and make indexes based on regular expressions and I'll leave that for another time and you can take a look at that that's sitting here in this 06 python。

 SqL Okay， hope you found all these demonstrations useful cheers。

