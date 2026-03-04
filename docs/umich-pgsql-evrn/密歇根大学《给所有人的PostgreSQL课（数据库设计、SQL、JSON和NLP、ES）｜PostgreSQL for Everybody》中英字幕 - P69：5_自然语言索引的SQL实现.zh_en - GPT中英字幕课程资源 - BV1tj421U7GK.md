# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P69：5_自然语言索引的SQL实现.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So up to now we've done inverted indexes that just treat strings like strings。

 but the real inverted indexes if what we're searching is natural language。

 we've got to do some stuff that we can take advantage of some of the realities of natural language to make our indexes smaller and more efficient So what we're going to do is just like we did before first we're going to build it by hand using SQL and then we're later going to just do it with Postgres and of course Postgres will be easy and the main reason to do it by hand is to better understand it。

So the whole idea is that we're going to take advantage of what natural language is and the fact that the queries are supposed to have meaning right。

 when's the last time you went to Google and typed in the and but if。

Who right those words we have in language and they're important for the structure of our sentences。

 but they're not important for the meaning of the sentences because we use an and but and who in so many sentences。

 but they don't contribute to the meaning they contribute to the structure of them and so it turns out those words are in natural language search queries effectively useless so why would we index them and the term for those words is stop words。

 which I don't know why they're stop wordss it's not like that we stop I would go it'd be better to call them ignore words for all we care。



![](img/bfdfee65ddb31621d4dad8ae9fcd68c9_1.png)

So we just do ignore words and we'd say here are the words to ignore。

 but we technically call them stop words and that's that。

So stop wordss is one natural language optimization。

 the other optimization we're going to do is just make everything lowercase。

 so stop wordss reduces the size and again generally。If someone types SQL uppercase or SQL lowercase。

 they generally mean the same thing and so teacher with the first letter capital T or teacher with not the first letter capital T。

 the meaning is the same whether we start or if you're looking for teacher stuff or teaching stuff。

 you don't care about capitalization， so we're going to lowercase at all。

And then we're going to make stopboards。So if we take a look， for example。

 at this one query I've got sitting here， this select distinct ID doc from docs。

 and Im searching for search for lemons and neoons， you can see the uselessness of the stop wordss。

 and so it found things that had the word and in it。But had nothing to do with lemons or neoons。

 So there's sort of stop words and meaning words。 And so we did this without stop words and we got a bunch of。

False positives in a way because the meaning the meaning of the resulting returned row and the meaning of the query didn't match at all and the other thing we're going to do is what's called stemming so the idea of stemming is where you have a whole series of words so car and cars。

Do you really want to separately index car and cars or auto and automobile and so these are their stems or lexs words that basically what is the real word so we don't separately indexed so it both makes our index smaller but it also means that when we do it to the query and we apply the same thing to the query where we take automobile and auto and make it be the same stem we're actually making it so it matches more documents because of the meaning and so stemming is words with equivalent meaning so a word and it ST you map all the equivalent words down to the same stem and then that also reduces things so。



![](img/bfdfee65ddb31621d4dad8ae9fcd68c9_3.png)

![](img/bfdfee65ddb31621d4dad8ae9fcd68c9_4.png)

What we're going to do in this one is we are going to。

Build our own manual index in that manual index we are going to add。



![](img/bfdfee65ddb31621d4dad8ae9fcd68c9_6.png)

A table of stop words。And then we're going to add a table of stems that map words in our text documents to their stems。

 We're going to have to map that both for the creation of the index phase and for the query phase。

 And then when we're all said and done， we're going to make a much better inverted index。

 So we're going to make an index that still has things like you know SQL is in three documents 1。

2 and 3。 But case has been removed and there are no stop wordss。

 So how would we build on inverted index that maps everything to lower case handle stop wordss and handle stems。

 And like before。In this in this。And this dot， dot dot part。

I'm going to show you that in another demo。So I'll show you the whole dot dot dot。

 we'll walk through it all the way， we'll see everything and that will get us to the point I'm just showing you where it's going to go。

The stemming and the stop words very much depend on which language and so you'll notice in this next part when we're going to do it all with Postgres SQL。

 it's really important to say which language it is Now this little next select that just shows you which possible languages you have in select CFfG name from PG_ TS underscore config。



![](img/bfdfee65ddb31621d4dad8ae9fcd68c9_8.png)

![](img/bfdfee65ddb31621d4dad8ae9fcd68c9_9.png)

![](img/bfdfee65ddb31621d4dad8ae9fcd68c9_10.png)

I think TS stands for tech search in this， this shows in a default installation with Postgres the number of languages that are precomputed。

 have precomputed stemming rules， etca， etc cetera， etc cea， etc cea。

 stop wordss and stemming rules and many other things right we're doing a very。

 very very simple implementation， but like always Postgres already has our back covered and has a bunch of things in there for us。

 but it does mean as you create data models you got to remember what language it is because you might have to create different indexes for different information in different languages。

 so that's what we're doing is we're switching to like if it's natural language and we know what language it's in we can build much more efficient indexes。



![](img/bfdfee65ddb31621d4dad8ae9fcd68c9_12.png)