# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P73：9_基于GIN的PostgreSQL倒排索引.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So I hope you sort of found it a little bit fun to do the inverted indexes the hard way using only SQL statements inventing our own inverted indexes。

 but in reality you don't want to do that really the whole purpose of that well so that you understood inverted indexes better meaning that you could if left alone on a desert island with nothing but many to many table you could make this all work so but now I want to talk about the inverted index that we have built into Postgress and they can do so much more optimization than what we could do in that with the joints that we were using before and so it's always better to use these indexes and there's basically two primary inverted indexes there's a third one that's kind of like SP g which is for spatial data it's not really I want it to be like the special g but it wasn't it spatial for things like。

Data points in a three dimensional place or。Latitude and longitude。

 things like that So there's two of them， there's called the the gin， the generalized index。

 and then there's the gist generalized search tree。And just like in B trees for normal indexes。

 the preferred tech search type index is just g it has exact matches。

 it never looks at more rows than it needs to， just like bee trees。

 it's like this very like look find got a list of rows。

 pull them in those are the rows you need they're very efficient on lookup and search and they can be costly when inserting or updating data and so sometimes you sort of put all your data in and then you build the gin later that's a common common technique in these inverted indexes but if you're just inserting once in a great while it's not that bad and so it's not terrible the is so that so the gin is like if you have no deep understanding of how your index how you want your indexes to work。

 just use the gin be done with it the gist is a sort of reduced size it uses hashing and if you remember hashing hashing throws away information but it makes the calculations。

Simpler but then more than one thing can hash to the same place and so then you got extra work when the hash function doesn't spread stuff out the right way and so that it all depends on the nature of the data being hashed。

 how well the hash function works but the gist is smaller and it's quicker to update and so if you're sort of grinding if you're very update heavy insert or update heavy and the queries can the query performance is less important than the insert performance because a lot of like you're saying of building a blog how often do they put in new blog posts like once or twice a day fine the querying it and searching it you're going to do over and over and over again so the gin is the fact that the insert is a little more expensive。

The gin， but if you're doing something like watching sort of a Twitter feed or something and pulling data in and pulling data in。

 pulling data in and then once in a while you do a query。

 well then the justist is probably the better idea。

 so it's all really a balance of insert versus query and a lot of the things in database indexes are a balance between inverse and query the downside of the gist is that。

Once it passes a value through it， like a word through it。

 it will get a list of blocks to read and then find rows in that blocks and it might read more blocks than necessary the gin will not read more blocks than necessary。

 it will read blocks that have the rows that have the thing in it that you're looking for。

But what just does is if it's got extra blocks， it doesn't know that。

 but then it reads the blocks and checks the rows and says， yeah， because of the hash。

 I pulled in two of them， but it's really only in one of them。

 And so it doesn't actually give you extra rows。 You don't have to like add an extra wear clauses because within the wear clauses。

 it still discard them。 So you could think always the wear clauses is like the wear clause is like pull stuff in and discard stuff that we don't need。

 And so it just happens to read a bit more extra from the disk。 It doesn't change it so。

I'm not really going to spend a lot of time showing you examples of how you use just because it works exactly the same as the gin。

 you just use it and it's all under the covers and it's all about efficiency and so we don't worry too much about that。

嗯。😊，So as we'll see we'll see later， this concept of operations just in the Gen indexex know a lot about the data that they're indexing and again。

 just like anything in databases， the more precision with which we can describe to the database engine that things that we want to do the more efficient it can be and so one of the things that the inverted index do is they have what are called operations and so and they need to know what kind of things they're going to operate and they will build subtly different indexes depending on how it works both of them work on as which is sort of like。

Stuff that's long and has pieces within it。 That's the best way to think of arrays and they use this operator。

 this less than at sign， which is like contained within is this array overlap this array So if this array has one thing。

 two things or three things this other array can be very large and if it has those three things among any of those you know all the things if there's an intersection that's when it matches and so so let's take a look at how this works and and you also tell it oh this is an array of integers。

 this is array of text etc and the thing we're going to do is all based on text So let's take a little tiny example here。

That we did in that whole long demonstration before that we did it by hand and it all basically so we're gonna create the exact same table you can just drop these indexes or drop the tables I just start to start each one I would say drop table docs drop index gin1 if you wanted to when you rerun these over and over and over again semi samples have those actual drop commands in there but here's the important thing right create index gin1 on docs using gin parenthees and so there's an expression now the key is this the expression inside this index creation is got to match the expression that we're going to use in the wear clauses because the wear clause is the essential part where we're trying to give a hint to Postgres as to how to throw rows away more quickly how to go from I mean throw blocks away more quickly okay there's there's 10000 blocks in here but because I've used the index I'm going to pull in three and so this thing is like。

Thousands of times faster right but you got you gotta I mean I'll admit it took me a while to get all these things exactly right。

 but the thing that's important is that when you're making an index and you're making a where clause that these expressions match perfectly right it turns out in the select there's other things you can put as expressions in the select they're less significant and you can do more complex things when we see ranking we're going to see this the where clause is where the cost of SQL queries it happens so the where clause is very。

 very， very important so we're making a generalized index string to array on the column doc split by spaces and we're going to use text operators okay and that's just matching strings okay。

At this point we're not doing natural language， we're going to do natural language in a bit。

 okay and so this is really a very crude， very pure string based， kind of like a split。

 what you might do in Python to turn a stuff with blanks in it into literal strings。

 there's no sense that this is actual language， even though the examples I'm using our language。

 there is no understanding of language will see that when we do this next。

So we're saying okay let's make an index and let's insert some stuff and like always the index is just being built while the inserts are happening and the index magically happens and then we can do a select and the key thing to this select is it's using this less than at sign operator so we have to pass our constant as it were to say。

 oh here's an array so that。Curly brace learn curly brace is a one element array with the string learn in it。

 that's what that syntax is。 I mean， technically that's curly brace learn double colon text。

Open bracket， closed bracket， which is converting it to a text array， but it's an array of one item。

 so that's kind of like the serialized form of a text array and then string to array of doc。

This is basically。This is to say， oh， remember that index I just made？

You could run this on every row and then do the string to array on every row and check the wear clauses or the fact that you've got an index and it gives you a clue to what rows you're dealing with。

 right？So we can do an explain on this so if you do a query。

 it just happens and gives you the road that you're supposed to get with the word learn in it。

 the explain，And it doesn't， let's see how many how many do we have any other no。

 so you can do it explain and that tells you the query plan and the key thing when you're looking at these query plans。

Again， it takes me I'm going to debug these just because I have these done in an instant in these lectures doesn't mean that it didn't take me a while a little while and some Googling and some stack overflowing to figure this out。

 but what you don't want to see is sequential scan。When you see Que sequential scan。

 that means that you failed， that means that you made this cool index but whatever your wear clause was it didn't activate the index because that's what you're trying to get now Heap scan Recheck index scan all those are good things and that's what you want to see that basically says that you have successfully made an index and youve successfully made a query that uses those as index and if this thing matters you will take every query that you were ever going to use that you expect to use that index and you'll do an explain on it to make sure that you're getting it right so。

That's a lot of talk about very few lines， I mean if you go through this。

 it's just like two lines that matter， it's the cr of the index that and the array expression inside that index and then this theware clause that uses the less than at sign and so it's very simple it's very elegant you will find this so easy to use that you'll like use it whenever you need it and just say thank you very much Postgres for putting all this work in and so up'm next。

Up next， clear all that up next， we're going to start switching from pure string indexes to natural language indexes。

 okay？