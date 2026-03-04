# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P10：9_PostgreSQL数据类型详解.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/f3bff3082a23fe92e79b2b0ab8883aa0_0.png)

![](img/f3bff3082a23fe92e79b2b0ab8883aa0_1.png)

So we talked a little bit about how different kinds of commands do the crud operations and wear clauses and things like that now we're going to talk about what kind of data types that you can define in the schema of your tables。

So we've got some text fields， we've got binary fields， sometimes those are called blobs。

 numeric fields， and then auto increment fields。Varcharr was the one that we did before。

 and that's an efficient storage for characters of varying length from。

 you know one character up to 128 or whatever。 char is a fixed space usually we use these for shorter strings。

 I mean， once your string gets above 64 characters。

 you might have a character that has a bla b b bla b it ends and you don't want to waste the time for that。

 but there are certain times places in databases like for a goodids globally unique identifiers that you know they're going to always be like 64 characters and so char is used for that。

 I tend to use char when I know like I'm gonna store hash。

 which is exactly 64 characters or a Guid which is exactly 64 characters when you can do that database loves you。

 especially if gonna to fill it all up if you're not filling it all up you're not doing yourself any favors。

 but if if you have 64 and it's always 64 and it's never lower。

 then a database actually kind of loves you if you can say that So use var cha unless you really know that it's kind of a fixed thing。

 Sometimes you have fixed things that are only like。Two characters long。 It likes that too。

 so you would never say varchar too I don't know somewhere between 64 and 128。

 I would always use varchar， say above 64 just kind of my own whatever and the way allocates it is the varchar has a count and then the actual data so you can pack it in a lot more tighter whereas the charge is just。

Chunk， chunk， chunk， which means it's kind of uncompressed in a sense。

 but if you're going to fill it all up， there's no way to compress it okay。Text fields。

This is what I talked about before is if you want a text field and you don't want to have the database enforce a length on you。

 well it just called a text field and these can be short medium or long。

 there's a count at the beginning， but the count it's not that big of a deal。

 The key thing is is that you generally don't use these for indexing and sorting so you don't use these in order by you don't want to use these in aware clause。

 you might use them in a like clause knowing that it's going to be a full table scan So if you're doing like a blog post and comments or even whole web pages that you're stor because you're building a spider to read web pages。

Text is great and Postgress only has one which I really like。

 Lots of other databases have like a whole long list of different kinds of text。

 but basically you kind of have the things where you know the length and the things that you don't know the length。

 And so that I think is a really simplifying notion that Postgress has and it also has a character set what it means when I say both char v char and text have character sets。

 that means that they are not simple8 bit characters。

 And so the sort of traditional Western character set that we generally call Latin one or ASI that has 127 characters and it fits into 8 bits and that's called a byte。

 which we're going to see in a second and so you know that it's very efficient whereas when you have characters outside of the Latin character set which might be like a sillia or Asian character set those are longer than。

😊，8 bits and so those are sometimes as from they can be 8 bits。

 they can be 16 and they could even be 32 bits and so。If you have。啊。You know。

100 characters that have a character set that could be up to 400 bytes。And so。

 but the nice thing is is that we humans， when we're typing into forms or typing comments in a blog post。

 we're typing in those character sets。 And so you can't just say， well。

 I'm going to write a web application that doesn't accept Asian characters web application that doesn't accept Spanish characters that there's only like the ASII characters So it's really important for databases to know the things that have character sets and also in different character sets。

 the sorting is different。 So these are all the things that the database people have figured out for us so character sets are very important indexing。

 sorting end user input and so cha， var cha and text handle character sets。

Now why do I make such a big fuss about that， you also can store things that don't have character sets now。

You could do this for like a goid。Global unique user ID which you know is just letters and numbers and letters A through F。

 which could fit in one of these things and you know that it's a string that has up to 128 different characters and each one so this byte A is the place that we store data that that we're not letting the database know its' character set。

 and so you can store blobs of information， small images， etc。Integer numbers。

 there's a couple of different integer sizes， the normal integer that we use is a 32 bit integer that's 2 billion that's used for most situations and then you can save space with a small integer。

 but then you're limited on the range and big integers are much larger than 2 billion and so but mostly we just make integer columns。



![](img/f3bff3082a23fe92e79b2b0ab8883aa0_3.png)

You can have a number of different floating point columns real is a third2bit floating point that has seven digits of accuracy and what we mean by accuracy is it has seven accurate digits。

 but you can put the decimal point anywhere in there and for this is not really real is sort of。

And we've always had these 32 bit real numbers in all of computation from the beginning of time that 32 bit number with  seven digits of accuracy is really only good for approximate computations。

 know if you're taken like an average of the weather temperature over a long period of time it's probably good enough。

 but if you're doing some real precise stellar calculation where you're calculating forces is like stars smash into each other real is not good enough because then the errors creep in because it's only got seven digits accuracy So that's where double precision。

 we call double precision because it's twice as big and usually for scientific computations where you're going to do more lots of computations over and over and over again like in asim you always use double precision Now it turns out that neither those are good for money because the way fractions are represented in real and double precision are there fractions with powers of two in the denominator And so it turns out that like if you have like in America you have dollars and cents well there's 100。

So a cent is $1100th of a， but that 1100th is not accurately represented in real or double precision。

So we have this numeric thing where you say， okay， I would like two digits and I'd like 14 digits with two digits of decimal。

 and then it's perfect， so you can't represent money and there's lots of movies that like talk about like what happens when you can't represent money accurately where people like take the fractions of interest that are not represented in Rio and whatever。

 but if you're doing money， use numeric。Dates。

![](img/f3bff3082a23fe92e79b2b0ab8883aa0_5.png)

Lots of things are important in dates， there is sort of a date and a time。

 but the thing we tend to use a lot is a thing called a timestamp。

 a timestamp is a 64 bit number and it represents minutes and seconds from 47。

13 BC this big long AD years ago this was a 32 bit number and we had this problem that the UniX time which was the number of seconds since January 1-1970。

 and 32 bits and that was going to run out of space in 2038。And so here's another XKCD。

 there's an XKCD comic for just about everything nerdy and so clearly Postgress has switched to 64 bits for their timestamps。

And if they hadn't， if they stayed with 32 bit timestamps in 2038。

 all the Linux systems and all the databases were going to blow up。 but when they go to 64 bit。

We can go to almost 300000 a without running out of space。 and I'm。

 I'm not going to worry about that。 Okay， like 2038， we're getting to 2019 in 2020 and 2022。

2038 was common， but。They just went to 64 bit and all these computers are 64 bit and all these databases are 64 bit。

 so we don't have to worry about timestamps running out of time in 2038。



![](img/f3bff3082a23fe92e79b2b0ab8883aa0_7.png)

So up next， we're going to talk about the things I've been talking about all along。

 about how these things work with performance and how fast they go， et cetera， et ceter。



![](img/f3bff3082a23fe92e79b2b0ab8883aa0_9.png)

![](img/f3bff3082a23fe92e79b2b0ab8883aa0_10.png)