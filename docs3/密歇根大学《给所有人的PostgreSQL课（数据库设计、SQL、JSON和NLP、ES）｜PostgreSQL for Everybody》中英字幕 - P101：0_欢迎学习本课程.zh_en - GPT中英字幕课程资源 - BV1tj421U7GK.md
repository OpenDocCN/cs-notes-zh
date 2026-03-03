# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P101：0_欢迎学习本课程.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/2b3ac3ccc328464aa9623ce7c96b024b_0.png)

Welcome to Course4 in Postgres for everybody Now we're going to finally talk about how things work and sort of some of the meta issues around databases。

And you might say to yourself， why didn't I talk about this at the beginning。

 in some ways you I did start with history， I started to talk about how standards happen and really databases have been a big part of every application that we've built。

How they've changed as we in the market and the world has changed， how the internet changed。

 how the cloud happened。And so we're going to start with how they work。

 how relational databases work， and then we'll talk about what the strengths and the weaknesses are of relational databases and how we build and deploy relational databases and how we make them run at scale。

And then。Again， that scale has changed over the years from10 users。

 hundreds of users to thousands of users to millions of users and on up billions of users。

 the NosQL movement is kind of part of that story and you might think that the NoSQL movement in the relational database movement are like at odds with one another and the answer is in some ways very complementaryary。

 there are so many moments where the relational databases needed to step up to up their game a little bit and NoSQL was a good example of showing a weakness in relational databases。

We will talk about deployment， we'll talk about scalability。

 we'll talk about words like master master and master slave Replication， etc cetera。

 and how that works and how that impacts performance and what works and what doesn't work。

And we'll finish up by actually using a noSQL database。

 I've chosen to show you Elastic search it's one of many NoSQL databases where you pretty much talk to it in JSON the reason I picked Elasticse is that it is really common and has been common for quite some time to have a hybrid application that uses elasticasticse to support its search and then uses a relational database like mySQL or Postgres to do the rest of its application and so even if you work with relational databases for kind of the rest of your career it won't be you won't shouldn't be surprised if you eventually run into Elasticse so there's a lot of really nice stuff going on in this and I hope you enjoy the class。

