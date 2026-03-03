# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P35：6_子查询技术解析.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/6595f21cbd06d2629aa3355d001d9d21_0.png)

![](img/6595f21cbd06d2629aa3355d001d9d21_1.png)

So here's something that you can just try， so go have coffee with a really good person in databases。

And sit down and basically say to that person， say like。

 and I'm kind of a beginner in databases and I just learned this great technique and for me it really makes databases great。

 I love subqueries。 They are awesome。 I can really express what I want so nice。😊，And then。

 just watch what they say。You probably you'll see theyre like like in cartoons where they start to get red and steam will come out of their ears like subqueries。

 What do you mean。 So let me talk you about I'll first， I'll tell you what subqueries are。

 And I will explain to you why they make database administrators so freaked out and angry。

 Most cause they went to training that says subquaries are evil。 here's a key， though。

 that you got to be careful。 if you're doing data mining。

 certain things that are bad in online systems are not necessarily bad in data mining。

 because if data mining is about convenience。 And if it only takes you5 seconds instead of one second。

 that's no big deal。 But if you're an online system and it takes you 5 seconds versus one second and there's a million people doing it。

 that is a big deal。 okay。So basically， what is a subquery。

 is really a query within a query that allows you to replace。

A value or a set of values inside of a query with another select statement。So here is， you know。

 we'll go find。You know， this account record that has Ed in it。 and we got。

 and we find out that that's 7。 And so we can say， you know。

 go find content from comment where IDd account equals 7。 And sort of to do this。

 unless we used a join。 But let's ignore that for the moment to do this。

 you sort of have to run two queries。 You have to do this and get the results of this and then feed that in。

 And so maybe you're writing Python code or something that is running a query looking at it or maybe you're typing at yourself and then you cut and paste that number and put it into the second query。

 right， So somehow that number 7 moves from the first query。

 the result of the first query into the second query， I'm like， well。

 wouldn't it be nice if we could just do that all in one statement， and you can。

 And so you just put this parenthesesis。And then you throw in a select。

Now this particular sec is selecting to get a number because there's exactly one row that's going to make it and there is and it's where account ID equals is expecting a number。

 and so it's like out comes the seven and then these two things basically are then equivalent as long as the number is7。

And it turns out that what if there's two things that came back from this select statement。

 There's actually an in here。 There's another operator that if this is a set。

You can say where account I D in select blah， blah， blah from where， blah， blah bh。

 And So this might be 40 of these things come back。

 And this wear clause is smart enough because that's kind of like an array of Is at that point。

 And the wear clause is smart enough to see if it's in there， right？

 So this is a very convenient way of expressing a whole bunch of things， really。

And if performance doesn't matter， sometimes pretty is more important than performanceant。

Although most database administrators will encourage you to find a way to do what you want to do without using subQury。

 and this is the reason why。The reason why is because when you send a query to the database。

 whatever that query is， and I started to draw this with my hands and say。

 like here we send this query and the database is like so smart and it knows about all these things and knows where the data is and it has indexes and it's doing what's called optimization。

 later will'll talk a lot more about performance optimization。

 but it's able to take the abstract question of please get me this stuff。Sort it this way。

 order it this way， group it this way， distinct， whatever， but I don't care how you do it。

The problem with subqueries is you're kind of telling the database how to do it。

 What you're saying is I have two things I want done and you have got to stop。

 You can optimize this part and make this really efficient。

 but then that part has got to produce some output。 and that becomes input。

 and then you can optimize this part。And so the database administrators are like that's two queries。

 it's as if you did two queries。It's actually better than doing two queries because you don't have to go from your Python code or your web server to the database twice。

 And so it's actually better than two queries。 But it becomes a slower  query。

 And one of the problems database administrators don't like is slow queries in general。

 So they might say， no， I'd still you slow down because you're such a bad designer that you're doing subqueries。

 you go ahead and just do the two queries。 And I get I as the database see two。

More optimizable queries among the thousands and thousands of queries I'm getting per minute or per hour or whatever。

 And so it， it produce， it produces this sort of。Stops the optimization analysis from the outside to the inside。

 But I'll be honest， I mean。That's only， you know， so said it has to do everything inside this parenthesesis before it can start looking at this。

 And so it sort of sees this as one optimization， runs this， gets the result。

 and then sees that as another optimization。No whoho knows databasease is an abstraction。

 This is just an expression of what we're asking for。 And the result could come in any order。

 as long as we got the same result， no matter how the database tried to do it， It's just for now。

 databases have chosen to treat that inner select as a select that writes reads from the database and writes into like a temporary table and then the outer select kind of reads from the temporary table and then among and then all the other table。

 So this second select you'd think there's sort of two tables involved。

 There is this comment tableops comment table。 And then there is this table created by the inner select。

 And again， that's what the database administrators don't like。

 is that temporary table thats sort of part and parcel of how these subqueries are supposed to work。

 So that's the the basics of subqueries。If I go back to the having clauses and remember the having is kind of like the second wear clause that happens after the group by。

 so the where clause happens before the group by， then you have the group by。

 and then you have the having clause， which is a wear clause and so you can only talk to look at this count in the having clauses you can't do it in the wear clauses because the where clause is what helps produce。

This count value。That's from before。Now， if we didn't have having。You'd be like， oh。

 that's pretty bad。 I think most databases do have having。 This actually is really。

 once you understand it， I think this is very elegant， but let's just say you didn't have having。

You could do this with subqueries and some unhappiness on the part of your database administrator using this SQL。

 So the subquery remember is you start with parentheses so we have kind of an outer selectlect in an inter selectlect the inter selectlect happens first and we're kind of making a temporary table。

 It's like stop everything， run the inter selectlect。

 take those results and put them in a table and those tables have columns on top of them right and so this select count arev from where group I。

 well then that produces a little table。And this temporary table。

 we're going to call zap temporarily。 And then then we're from that from that inner table。

 when that work is done， it's going to select count and areave。 right， Now the count， the reduction。

 the distinct the group by that all happened in the inner query。 So it's a rather small table。

 But now we're going to select count and a breatheve from that temporary table with a where clause。

 it says where counts greater than 10。 So it's the same thing that's having happening and happen， I。

Happening in having， right， And then it does it and then does another thing。This is a lot cleaner。

 And there's a chance that the database might be able to optimize this because we're doing a better job of expressing what we really want because here we're kind of expressing procedurally do this first。

 make a temporary table and do the next thing based on reading the temporary table。

 So we're kind of making it be steps。 And we're saying， do it in order。

 which means it's harder for it to optimize。 whereasas this could be optimized。

 We don't know if it's going to be optimized。 But by not using a sub queryry。

 we have to give the database potential to optimize it。 And so。



![](img/6595f21cbd06d2629aa3355d001d9d21_3.png)

That's why database administrators would rather you write this line than the subquery line because maybe they can look at this and they can find something inside the database that they can make this go faster。

 but then they can't do something inside the database to make this go faster and so。

That that amazingness that is the database， The database administrator can be part of that amazingness because they can do things like a indexes。

 change indexes， recreate this or that they're remove data around。

 there are things they can do behind the abstraction that make these queries run faster and a more abstract query like this one has a better chance of being optimized with the healthier database administrator than this one。

 And so that's kind of why they don't like them。So the next thing we're going to talk about。

Is concurrency， concurrency really only matters if you're kind of an online system in these transactions like banking transactions are coming at the same time。

 but it's still an important concept in case you're going to run into it。

 and that's what we're going to talk about next。

![](img/6595f21cbd06d2629aa3355d001d9d21_5.png)

![](img/6595f21cbd06d2629aa3355d001d9d21_6.png)