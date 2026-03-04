# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P64：0_欢迎学习本课程.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/85fe5973cd8ba80e3bf4ec550162aaae_0.png)

Welcome to Course3 of Postgres for everybody。In this course。

 we're really going to focus on two topics and that is Tex and JSON。Computers。

Do numbers really well and that for example， is why we use numbers for foreign keys because 64 bit integers are something computers store efficiently。

 move around efficiently efficiently， compare efficiently。Et cetera。

But the large fraction of the work， the data that's being stored are strings， names， comments。

 blog posts， good are numbers， I mean you know we use them for like average weather temperature or something and so it's useful。

 I mean zip codes， they're not even numbers， they're like strings， phone numbers or strings。

So text is important and natural language is important。

 text that you know of conversations and search engines， et ce。

 and JSON is really the biggest thing to happen to relational databases in 2025 years and we I've been talking about it kind of all throughout the course about how important it is that databases do a good job with JSON。

JSON allows for applications to evolve so that the structure， I mean。We did data modeling。

 we talked about。Every column matters， a 64 character column versus a 2 million character column matters。

 we want that for efficiency for maximum packing。But at some point。

 that sort of prearrange contract of。You know exactly what columns they're going to be and exactly what size they're going to be is great。

But it's also limiting for some applications。Sometimes you just want to throw a little bit of data in。

 not something you're going to sort on or put in a wear clause or whatever。

 although you will see that with JSON， you can index pieces of JSON that make it so that it works great in wear clauses。

And so the flexibility that JSON gives us is really an improvement to relational databases。

 but then what we don't want to do is we don't want to give up all of the amazing performance that we get by a carefully constructed schema where we agree with the database system in advance how we're going to use it。

 and so this section is going to talk a lot about how unstructured data can be treated like structured data。

 so I hope you enjoy it。