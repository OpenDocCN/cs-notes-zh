# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P54：25_索引选择与优化技术.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/de0749b54f02a3c884bc9bdb6257da4e_0.png)

![](img/de0749b54f02a3c884bc9bdb6257da4e_1.png)

So now we're going to get back to performance now that we kind of know about hashes and indexes。

 we're going to talk a little bit more about performance So the application that I'm going to play with is a hypothetical web crawler。

And the way web crawlwlers work is they， you know， a Python web crawlwler would grab a page from the internet。

 it would look through all the links in that page and then add links to a queue。

But we need to know the ones we've already seen because if we keep because a lot of web pages point to the same web pages because they got like a navigation on the lefthand side or something。

 So we need to know which pages we've already seen in our database And the other thing that you do in a web crawler is you want to use databases because you can't crawl the entire web or whatever you're doing into a dictionary and then do your database analysis。

 And so these processes of like scraping the web they take a long time and you want them to be able to be restarted。

 And so if if you retrieved 10000 URLls it might take you like 12 hours to do that because you might have eight limitations or whatever and you just don't want to have to start from zero all the time。

 So databases and web crawling are essential。 And so we're going have URLs。

And there's going to be a lot of tables and there's going to be just a lot of URLs and we've got to decide if we've seen them before。

And so。When you're building something like this， it's super tempting and incorrect to do something like saying。

 you know what？Depending on your application。But how long is a URL is a Vr 128 long enough with a unique index if we knew that URLs were only 128 characters？

Then this would be a fine way to represent the data。

 so we've got our page itself in the content field， and then you got the URL in the URL field。

And you could decide， you know， you're just going to treat all characters if you youre you're going to have your unique constraint just beyond the first 128 characters of the URL or maybe make it 1024 and you could do that。

 right？The problem is is in the real world， other than truncating URLs to 1028 or 2024。

 you just can't assume that URLs are long， that are you can't assume that URLs are a fixed length right and so the problem is if we sort of build something long that's too long and we tell it it's 128。

 we try to insert something that's bigger than 128。

Potgres just blows up and you could trunccate it and that's up to you that depends on your application and how much you want to know。

But it's often a lot easier just to say， look， the URL is a text character too。

 but then we have another problem， okay？And so if， if we do that and now I'm generating quite long URLs in this case。

 and so you'll notice。We're going to have this text be a 4000 long， so it's 4000 neon neon。

 neon neon， and we're going to have 5000 rows that are 4，000 characters long。

 and so that's what this insert into CR2 is doing we have an unlimited length text field for the URL。

And so we can insert these 5000 says like 5000 records times 4000 characters。

 and we end up with like about 5 mebytes in the relation。

 we don't have any index right So what we're gonna to do is we're going to basically create a unique index。

 which is a slight variation So you can create an index， which is a B tree， which allows duplicates。

 unique index is a B tree that doesn't allow duplicates。

 the the Bre sort of functions the same So unique just is a sort of a rule that says you're not allowed to insert the same thing twice and then something like this URL when that's our goal。

 we want to make it unique because then we can try to insert it and the insert blows up。

 We know something we talked about that before you can like on duplicate key kind of stuff。

So we don't have to add the index into the create statement， we can say create unique index。

 this is the name of the index on CR2 URL， that's the URL column in table CR2 and this is the name of the index and does it and then we can see because we already put the records in so it's going to make the index for the records and you can see that basically the database is a certain size and the index sort of tracks almost directly and that's because all these URLs every bit of the text。

 4000 characters long ends up in the index and so it's because the index wants to know a perfect match whatever we told it to do and these can get the longer these get the bigger this index gets。

Now we don't have any content any of these records， so ultimately if you started putting pages in。

 this would have grown a lot faster， the size of the relational data would grow a lot faster than the index size。

So one of the things that we do is I'll get rid of that one。

 I'll get rid of the CR2 unique index because you can get rid of the indexes too。

 and you can do this live even if you're running an online application now I'm going to create a different index。

 create a unique index on name the index CR2 underscore square M5， that's just my name for the index。

Create index CR2 M5 on CR2。 And I'm going to in this parent， this is the index expression。

 So I'm saying I want to compute the M5 hash function of the URL。 So this index is 4000 characters。

 The URL is 4000 characters long， but then we're going to end up with a 64 B or 128 B M5 result。

 and it's going to build a B tree based on that。So the Bea tree is much smaller and so you can see after we make this index。

 the index size is a lot smaller because we're only indexing the MD5 of the URL okay？

And so now we can do something like， you know， we can select star from CR2 where URL equals lemons。

With note。Oh， yeah。 So because this index is not on the actual column， This does not use the index。

 So it has to do a full table scan because our URL equals lemons。

 And the way you trigger the index is you say。Where the MD5 URL is equal to MD5 of lemons。

 and so now it actually uses the index to do that。Okay， so in the other one。

 it could it would have use the index for this URL equals lemons。

 but given that we made an index expression here， the away it goes， and so this index condition。

 that's the part that gets sent to the database engine to go look these things up。

So you have to kind of match in your wear clauses the expression that you use to do the index now this kind of looks arbitrary but it detects this it's like。

 oh sweet， this is the thing I got an index for so I know how to make make best use of that。嗯。

So again， you can do unexplain and you can do the analyze and the difference between the analyze is the explain just tells you what it would do to figure it out and what it's going to ultimately do。

 But then the analyze says tell me how long it runs and so this is going to do this is the one that's using the index and it's。

0。14 milliseconds， and this is the one without the index because it's not using MD5 here。

 and so it's about。Yeah it's 100 times slower， that's because I only got 5000 rows。

 so I didn't put quite as many because in the previous ones I was showing 100000 rows。

 but this is the difference between the explain， analyze and just the explain it actually analyze causes it to run it and tells you how long it actually It does does the query and tells you how long it takes。

Now， a technique that I've used in these situations is that I've created this M5 myself and and put that in a column and then use a hash index on that。

 So it turns out that M5。 There's this data type called UUid that is exactly the width and a very small column that is exactly the width of a M5。

 it's kind of designed to be part of M5。 The fact that I call this URL I'm going to be 5。

 that's just the name I gave it。 Uud I is a data type and I want that to be unique。 So this URL。

 I'm actually not going to create an index on this。 I'm going to create an index on this。

 but then I'm going to set that up。 So here's how it goes where I'm going to insert into this making my 4K long 5005000 rows 4000 in each row。

 and then I'm going to an update statement where I'm going to calculate this this M5 column based on taking the M5 URL。

This is a cast statement， Col colon UID is casting it to a UID type that turns out to be right that works。

 and so then it stores these things， but as it's storing in this update statement。

It is actually computing this， but then creating an index。

 And now you can see that I've got a little larger amount of data here because I've got this extra column。

 not just that column， but I've got this extra column。

 but the index size is smaller because it's doing a unique B tree index based on this。

 And so I haven't told it to a hash index yet， but it's a B tree index。

 And you can see as long as I'm doing the same thing。 Now this is my column that I've computed。

 And I know that this is an M5 column。 So this is what I'm looking the string I'm looking for。

 I do M5 of lemons and then convert that to a UI。 And then it knows that that's what's in the index。

 And so I can do that particular query with an index scan。

 and it's scorchingly fast as you would expect。So if we kind of compare these index strategies。

 we see we we use just the URL as text with no index， we get a relation size of 5 meg and it's 1。

7 milliseconds to read it， I do a basic B3 Bree index of MD5， it's smaller， this is a little smaller。

 the relation size doesn't change and the select is 10 times faster。

And then this one here is where I'm manually doing it。

 so you see the relation size is a little bit bigger， but the select is super fast。

 So you see like there's another speed up。 So these are the kind of things where you can look at the alternatives and decide amongst yourself how much space you're willing to give up and how much speed that you're going to try to do。

 So there's no sort of one thing it all depends on your application and how often you're going to do selects。

 often you're going to do inserts， et cetera， et cea， et cetera。

 But we've got a mechanism to look at these。So again， the B tree maintains order。 It's the default。

 It helps an exact lookup， prefix lookup less than greater than ranging and sorting。 So that's a lot。

 It the one thing it doesn't。 If you're doing like wild cards that are anywhere in the string。

 hash is only good for exact lookup and in earlier versions of Postgress， it was really kind of。

If you read the warnings， you just don't use it， but Postgres Ken did a much better job and made it so that it does stuff so if it blows up halfway through the index doesn't have to be rebuilt。

And so I'm going to just show you one little example of using a hash。

 so here's here's my stuff so I've got just URL content。

 no special column and I'm going to make CR4 underscore hash and using hash that this is where I'm adding right here normally that would be using B3 I mean if you just let it do it or don't say using it all it's going to use BTe so I'm going to force it to use hash okay。

So now I'm gonna that the data is all in the same data that I've been using up to this point。

 the relation size is5 meg and the index size is2m which is the smallest we've seen for an index size so far and if you do a look for URL equals lemons you don't have to do the MD5 thing because it just it is doing a hash on the URL I don't know if it's using an MD5 internally。

 it might be using a shot 256 we don't care we don't need to know and so this is a very small index with a very fast lookup time and we don't have to do any fancy bit we just have a wear clauseuse you'll notice it's equality greater than less than or like with a percent at the end would not speed up on this one so that's the danger using it only speeds up one thing but if you're looking for exact match in our little database crawling we kind of are looking for exact match and there's no sorting advantage on a hash as well。

wentnt wrong way。So if you look at the hash versus Bere。If you look at the hash versus the bee tree。

This was sort of my fastest and cleverest way of doing it and I had to do a little bit of work with this。

 the relation size got larger because I made my own explicit column but it was super fast。

 but I also then made a hash just let Postgress make a hash based on the URL and so then the index size is much smaller。

 the relation size is much smaller but this particular one。

 I don't quite know you know I would want oops。I would want this to be faster。

 but I'm going to guess partly because I'm using I think Postgres 11 in this that hash is not as widely used。

 so they probably have something that just runs better on a bee tree than a hash。

 but hash saves you space and is roughly the same。 in this case， it's 1。5 times slower。

 but I think if you made bigger data， it wouldn't be quite that much。



![](img/de0749b54f02a3c884bc9bdb6257da4e_3.png)

So that's sort of another ro through looking at different index choices and different index techniques and now up next we're going to talk about regular expressions。



![](img/de0749b54f02a3c884bc9bdb6257da4e_5.png)

![](img/de0749b54f02a3c884bc9bdb6257da4e_6.png)