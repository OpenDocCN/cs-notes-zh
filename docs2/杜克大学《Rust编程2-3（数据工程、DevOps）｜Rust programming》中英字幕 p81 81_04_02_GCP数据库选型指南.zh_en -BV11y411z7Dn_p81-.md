# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p81 81_04_02_GCP数据库选型指南.zh_en -BV11y411z7Dn_p81-

![](img/06a8e35ff2e3500a6b6d52095e0aa5ad_0.png)

An important part of using databases on the Google Cloud platform is to consider the tradeoffs of one type of specialized database solution versus another。

 Let's take a look first here at this Google cloud SQL option。

 It's a fully managed database service that lets you maintain a traditional type database。

 So a Postgress or MysqL or SQl server database。 But the option here is that it allows you to use the Google cloud infrastructure to do the heavy lifting for you。

 So this is really a good solution for people that already have deep experience with one of those common open source databases。

 Now big table is the next option here in that it can scale to billions of rows and thousands of columns。

 So for example， if you had petabytes of data。 this might be a good place to take a look first Now each of the rows is indexed and that value is a known roki。

 So it's a different type of solution。

![](img/06a8e35ff2e3500a6b6d52095e0aa5ad_2.png)

Here in that it's a single key data with very low latency。

 And so it supports very high read and writethput at low latency。

 And so it could be useful for mapre type operations。

 another one that's a very unique offering to the Google cloud a spanner。

 And this is a globally distributed enterprise database service。

 So that's one of the big differences here is that from the very beginning is designed to be global scale。

 And it's also nonreal horizontal scale or a relational database structure These are both options that are available inside。

 And it also gives you a very high SLA as well and enterprise grade security。

 So if you wanted to build a global scale system this would be spanner， a good solution for you。

 We also have memory store which is a managed Redis service。

 So this is a caching based system that allows you to manage a cachebased database。

 So this is useful for。😊，toring， let's say state in a game or storing things that potentially really need to be used at a frequent basis。

 but you don't necessarily need to change very frequently。

We have Firestore as well and Firestore is a NosQL document database that's built for automatic scaling。

 So this is almost a you know no server type solution in the sense that you're really building on top of a service versus managing the service yourself and application developers as well are you very strong candidates for something like Firestore we also have Firestore realtime database and this is a Jbased solution that allows you to build crossplatform apps for Google ios。

 Android jascript right so you can build things very quickly by using these highlevel services and then there's also open source databases as well so you could use Mongo。

 Maria Redis so in a nutshell here you have many different options and for example。

 in the spanner solution here this is global scale from the very beginning right and if you wanted to build something that was going to be let's say。

a news organization that was distributing news content around the world。

 maybe this would be a good solution if you already have a lot of Postgres solutions in your company and you're migrating to the cloud。

 maybe you would pick this cloud SQL option。It's very important to know the pros and cons of each of these choices and either pick one solution or maybe several solutions and combine those together to create a unique value proposition for your organization on the Google Cloud。



![](img/06a8e35ff2e3500a6b6d52095e0aa5ad_4.png)