# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P67：3_使用SQL构建倒排索引.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Now we're going to take a look at inverted indexes， like I said before。

 inverted indexes are generally used for tech search。

 so let's just say you're going to build a blog or you're going to have a bunch of blog posts in your database and they have a bunch of words in them and you want to have a search box。

that's the classic thing， and we will see as we go further sort of these inverted indexes have other uses just text。

 but text is the easiest thing to start。Inverted indexes have been around a long time。

 long before Google and even search engines and even the web。

 it's a sort of computer science concept。But certainly the way search is become so important and so enmeshed in our use of the internet and the web。

We have learned a lot and so in a way it's nice to think about how Google thinks about searching and how Google thinks about keywords and how Google thinks about matching and there's a lot of innovations that Google has added on top of the basic inverted index so it's kind of nice to see I've got a couple of presentations here。

That give you a little sense of Google's take on search one is the Google IO 2008 keynote by Marissa Meyer。

 I was at that conference in the audience it kind of blew my mind it was in 2008。

 Google decided to show a lot of its magic up to that point they've been very interested in saying oh Google's all magic。

 don't worry about it， but they wanted to get us as developers to begin to make use of Google products as developers and so they started talking about it it's a great talk。

 I've got a short link right into it where you can go right into the part where she talks about search it's only about a minute and a half and then there's another one by Matt Cus that just tells about keywords and inverted indexes and how they all work and how once they have an index and how they order and rank and that really is a nice outline about the things that we're going to talk about in this class。

So the first thing we're going to do is we're going to build an inverted index without using the built in features of Postgres。

Postgres has some wonderful built in features， but we're going to first build it by hand so that we better understand the magic so we can understand how to tune the magic and how to make better use of the magic stuff。

As I mentioned， inverted indexes work on columns that are。

Sort of a multiple thing so like an array or and so so basically what we're going to do is the first two functions are going to make a big difference in how we can do all this stuff and so the first array is the string to array function and what it does is it takes any string it's like split in Python and it just splits it based on a delimiter and gives us back an array and so we can think of a blog post after you split it is a bunch of words split it based on white space is a bunch of words so string to array is hello world Now this also shows you the syntax of arrays。

 curly brace hellello world is sort of the pretty syntax of a string array doesn't need quotes it's a little bit of a weird syntax but when you see those curly braces it's an array of something in this case it's an array of strings so string to array is a function。

The other function that's really important that what we're going to do here is unNest。

So unNestt is similar to the generate series things we did in the pre the textbased lecture where you say generate series 1 through5 and that would actually make rows 1。

2，3，4，5 and if you concatenated it with a neon generate series 12，3，45 it be neon 1， neon 23，4。

5 and so this unNest is one of these things where if you use it it takes an array and expands it into rows and it's a kind of like a join in a way where it's reintroducing vertical replication it's turning something that's horizontal into something that's a vertical and that's why it's called unNest I might call it。

Vertical to horizontal， I mean， horizontal to vertical actually， Okay。

 so if we take a look at the string to array hello world and we unnest it， we get two rows。

Now with those two things， we can build an inverted index。

 well what is an inverted index when an inverted index takes a bunch of documents。

Pulls all the words of those documents out and then ends up basically with a mapping from the keyword to the document。

Those are the key the keywords of document1， the keywords of document  two and the keywords of document three。

 that's what the inverted index is， and then what we can do is we can look forward through that by going down and finding a keyword。

 maybe SQL， and we find that document one as SQL document two as SQL and document three as SQL。

 it's not surprising in an SQL class at all three of my documents have the word SQL in them。

Once you can parse a sort of complex column of text and you can split it based on spaces and you can turn each of those spaces into the rows。

 into rows， you end up in a situation where we just have to do a few select distincts because remember we can select and we can insert from those selected things and so we're going to basically take a simple。

Text document management system which has a primary key in a text field and we're going to put some documents into it then we're going to create an index which has a keyword。

 not unique because remember the keywords have to point to many documents and then a foreign key back into the documents called Doc ID so we'll create that and then dot dot dot I'm going to give you a whole lecture showing you all the gory detail of how all those select distinct work。



![](img/3a48c3a2dca9ed2c761fe610241588a1_1.png)

And when it's all said and done， we're going to have this table called DocsGin， which is a mapping。

Which is a mapping。Between。All the keywords in the document， based on limited words in the document。

 I'm not worried about punctuation or anything。I didn't put punctuation in otherwise I had to do something about the punctuation。

 and it just basically says that there you go， the word the SQL is in document one。

 SQL is in document  two and SQL is in document three。way we go。

 and then what we can do is we can use a wear clause to look things up here and then use that to get a set of rows and then that set of rows works its way to a set of blocks and so that's what we're going to cover in the next thing and then the thing we'll do after that is once we do it the hard way。

 we will show you the easy way to do it， leaning on all of the Postgres SQL builtin text processing capabilities which are way better than the manual stuff。



![](img/3a48c3a2dca9ed2c761fe610241588a1_3.png)