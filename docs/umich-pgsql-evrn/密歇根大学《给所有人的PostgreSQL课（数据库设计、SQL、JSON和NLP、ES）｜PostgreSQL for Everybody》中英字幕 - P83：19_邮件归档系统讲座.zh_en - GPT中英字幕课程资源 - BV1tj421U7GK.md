# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P83：19_邮件归档系统讲座.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So the next Python sample that we're going to take a look at is working with some email data Now I've got some code free to download G。

pi myutils。 py and datecomp py we're going to play with some regular expressions we're going to do some indexing we're going to do some looking and we're going to again make some full text databases and do some clever queries so most of it's actually in the demonstration which had and I give you the Sql commands the basic idea here is we're going to retrieve again from an online sourcebox Dr。

chuck。 net slashsakchi deve and we're going to be able to pull a series of mail messages down and mail messages are in a format that's called embox。

Inbox has an interesting format， it starts with a from。

foollowed by a series of headers which are key value pairs which is like the key is up to the colon character and then the value is after the colon character in this case I went from four message4 through message6 so I got more than one message back the messages are delimited by a from space Now you'll notice the from colon is not the delimiter that's actually just one of the keywords of the header the other thing is that there is a header。

That there's a header。That is a series of the key value pairs and then there's a blank line and it's as simple as that there's a blank line and then there is a message text。

 blank lines can be in the message text， you know that you're in the new message when you see from in the characters now if there's from it actually kind of escapes that in the message body。

And so this sample code is pretty cool。 it's much more sophisticated that the key thing this is is it's like a web crawler and then it uses the database is like a scratch storage to spider it and pull the data in and out and it can be stopped it can be restarted if the server starts having problems you can sort of stop your crawling process and then figure out what's wrong or what's wrong with your network and then start it back up and it's pretty cool and the other thing that it's doing is it's cleaning up the data and so this is real email data that was just archived right off of a real email server and the header conventions and how addresses are represented they're a little bit differently and so one of the things we're seeing in this and' see in this code is the code to clean up different formats of dates and times in different formats of email messages etc using regular expressions and these are just things you can't do in Postgres but you can do pretty naturally now just I'll let you know that when you look at this code to see。

This Gma do Py this wasn't code that I sort of thought through for a few hours and then wrote for a few hours。

 This took weeks might tried two weeks of work where I was talking to the server and having things blow up and then I would evolve the code Now the code you're going to use is pretty pretty robust and a pretty resilient when it faces errors but I can't I didn't anticipate before it all started every error that I could possibly have made and so when you write this code you start writing a basic thing and if nothing goes wrong it works and you got your data and you do your analysis if you just find problems of data inconsistency or server unreliability or rate limits then you might have to adjust your code so some of these that I've written they get a special code when you hit the rate limit and you're likeoo saw rate limit stop might as well stop way today day and go get some more data or whatever So it's an interesting kind of programming exercise in that it's an evolutionary。

I mean exercise where you don't always know what's going to happen when you start talking to external data sources and then the part of the idea is to get all this data in a nice pretty consistent format。

 email addresses， dates， names， the headers， the body and all that stuff in a way that you can start your data analysis and not worry about all of those crazy vag so take a look at this me walking through the sample code。

 it's quite a long run through the sample code and then what we do with the data once we have it in a database。

