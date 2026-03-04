# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P48：19_数据库文本处理技术.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/f17632979a20121db61ac6e404d090ae_0.png)

![](img/f17632979a20121db61ac6e404d090ae_1.png)

We're going to talk about text and databases， but really this is much more than that after the first two lectures we've really been just using any excuse to teach you more in-depth SQL skills and you may or may not use some of these skills in text but they're just skills that you need so the first thing we're going to talk about is how to generate some test data in Postgres。



![](img/f17632979a20121db61ac6e404d090ae_3.png)

So we're going to talk for the first time。 I've been talking about performance all along。

 but now we're going to start talking in more detail and actually looking at how you decide about performance。

 So the problem is， is every all my little examples so far。 Like I put five records in。

 and I show you some queries。 But now I want to put some more data in。

 So the problem is is if you think about it。 you got to。

 let's say you need 10000 records or 100000 records or even a million records。

 So you can check to see how fast a query runs with various indexing options， et cea， et ce。

 And we're also going to look a little bit about how much space we start using as we make different decisions。

 So we'll get to all that。 But the first thing is a prerequisite is to fill your database up with data。

 And so。You could write a Python program and you could open some stuff up and you could write some for loops and then write stuff into the database or you could use Shell scripts。

 but it turns out that Postgres has some wonderful mechanisms that allow you to generate random data。

And so there's some functions。 and we'll look at each of these with some examples。

 but the the repeat function allows you to create long strings。 so you can just take a string like。

You know， ABC， say give me a1 thousand0 and that's like 4000 character 3000 characters， ABC， ABC。

 ABC kind of doesn't matter。 Then there's random which gives you a random number between 0 and 1 and we use functions like trunks so you can like multiply that by 100 and then trunk it and then get an integer between0 and 100 or you can say give me a number between 1000 and 9000 and then you get a bunch of four digit numbers so we can figure all that out。

Now， the one that's kind of cool is a thing called generate series。

 and it's a way to generate multiple rows。 And so generate series is how we generate a lot of rows。

 And so we'll look at each of these with a simple example。 So the first simple example is。😊，Random。

So basically random just gives you a number between0 and1 it's a floating point number right so I call it twice I get two different numbers and then I just multiply it by 100 and then I trunk it。

 so trunk says so that becomes like the random number between one and 100 that's a floating point。

 but trunk says convert that to an integer。Now the repeat one， right So I'm just taking。

 you know the word neon with a space and repeating it five times。

 So that's sort of a horizontal concatenation。 And so sometimes when you're building keys or whatever you just want them long。

 you'll see in a sec kind of we make you know， just put some random stuff in it。

 and then just a bunch of text。 And that's usually good enough。

 But this generates series is really kind of cool。 If you think about it from Python function。

 It's kind of like well， it's like the range function in a sense， if you think about Python so4。

 I in range 5， that actually then generates 5。 and so generates series 1 through 5。

 generates a series of numbers， but it also then if you concatenate it， it generates rows。

 So So these first two generated one row。 that's a random number， that's a long string。

 But this is five rows。 And so we combine all these things together to generate lots of rows of long data with some randomness。

 That's what we're going to accomplish。So here we see a select statement right so we're going to have a string vertical double vertical bars concateation string concatenation。

 so we're going to take you know Sql4 do co slash neon concatenated with a random number that's between zero and looks like a million cancatenated with repeat the word lemon five times and then to create more rows we also concatenate this。

 this is all one thing so this generate series is so cool it like explodes into the numbers one，2，3。

45 vertically and so that forces all these things to be calculated five times and so we end up with five rows with reasonably long bits of information and a random number and then a sequential number and so with these techniques you can construct a whole bunch of data okay so it's random trunk repeat and generate series and then you just insert these things in。



![](img/f17632979a20121db61ac6e404d090ae_5.png)

And so up next we're going to talk about， we're going to use this。

 and then we're going to talk about some of the text functions that we can do with data once we have it in the database。



![](img/f17632979a20121db61ac6e404d090ae_7.png)