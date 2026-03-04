# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p82 12_PHP数据库库.zh_en -BV1Lr421A75d_p82-

![](img/55ab2087ba8aaa5805f249fc13b572c1_0.png)

![](img/55ab2087ba8aaa5805f249fc13b572c1_1.png)

So now we bring things together， we've talked about SQL， we've talked about PhP。

 and now we're going to connect them together， and this is where my favorite picture in the whole world really starts to come together and that we've got a request response cycle that sort of comes back and forth and all that stuff and we'll get that figured out。

 but now what we're going to do is we're going to actually build a request that goes into PhHP。

 PhHP is going to make a database connection and send SQL commands。



![](img/55ab2087ba8aaa5805f249fc13b572c1_3.png)

S Q L's going back and forth across here。 And we've been doing this。 We've been talking S。

 Q L through P P。 might have been straight to this thing。

 But now we're going to make it so P P creates and sends the S Q L。 S。

 Q is going to do the same thing。 Select， read， update， delete all that stuff。

 and then send us back what's called a record set。And then we're going to read through that as if it were a file。

 It's a sequence of records， basically， and we're going to do something to that。

 we're going to write some HTML out。 Then we're going to produce the response。

 And then from that point on， it goes into the dom， and then we see the Dom。

 So this is the part we're going to focus on today。 And we're going to use a library called PO。

 the portable data objects， which is part of PhP 5。 It was introduced in PhP 5。

 And at this point where PhP5 is kind of the older version of PP7 is the modern version。



![](img/55ab2087ba8aaa5805f249fc13b572c1_5.png)

![](img/55ab2087ba8aaa5805f249fc13b572c1_6.png)

And like I said， we've been doing all along。 We've had this database server。

 and we have been acting like the database administrator by using PhP Mydmin， sending SQL。

 and then it just shows it back on our screen。 And again。

 now we're going to use PO to do this where the user talks to our PhP code。

 we as the application developer write some SQL， send it and it goes back to the end user So our job is to write some PhP to do database。

 We don't let the user talk to the database because then they could see things they're not supposed to see。

 I mean， our job here is to sort of give them the view of this data that we are supposed to give them。

Like I mentioned， we're going in we're currently in PhP5 and we're going to PhP7。

 but in the PhP4 and earlier， there was another way that we did this。

 And one of the things that everybody absolutely loved with PhP was how easy it was in you know even like 2。

3 and 4 version to access SQL。 it was just built in。 you had these routines。

 these are the legacy routines， was is this is you know less than5 in the legacy theyre my SqL underscore。

 and so as we went from PhP4 to PhP5， they decided。

 oh we could do all kinds of things now it turned out that in PhP4。

 you would have like Oracle underscore。An SQL light underscore。 And， and basically。

 you'd have quite different routines for each of。Each of the different databases that you would talk to。

 and these weren't SQL light was built in， but the other ones weren't， and my SQL was built in。

And a couple things happened。 They wanted to build this object oriented version of this。

 So what happened was is everyone had been using these for like 15 years。

 and we really got used to them。 So as P P5 came out， they went and did two things。 First。

 they moved an object oriented one。 And it turned out you could only have one connection。

 You couldn't even connected to debateated databases。

 unless you connected to one then disconnected from that one and the other。

 There was a lot not to like about this。 other than the fact that we knew them really well。

So they wanted to do an object oriented version because then you could open a connection to one database and open a connection to another bit database and have an object for each of those connections。

 And then when you want to talk of this database， you do this object and you have simultaneous connections。

 So that was really nice， right。And the idea was we didn't know if people were going to want to use the patterns from these mysql routines。

 And so they made a new thing called mysqL I squarely， I think is how I would pronouncednoce that。

 And it's an object or version that has exactly the same calling sequences to our beloved mysql underscore routines。

 kind of like you see date underscore。Add in the O lecture。

 which we did that stuff and you just say it like you know dot dot dot dot add。

 so it was like redo the non object journey routines as object routines。So they did that。

 And then they also said， let's build from scratch looking at other languages and how they had done some really pretty things。

 and they looked at all the different my SQL and an oracle underscore and theyre like。

 what are some of the prettiest patterns And so they made a whole new thing that had done new API。

That didn't try to be look like the old one。 And so we didn't know。

 We didn't know which of these two we were all going convert to when we went to PhP5。 Now。

 the old ones would work， but they're tacky and not very not very well liked。 And so， you know。

 I was teaching classes during this point in time。 And I for a little while。 I mean。

 I thought to myself， okay， I've got all this source code， all this sample code。

 and I'll just use my SqL I。 But I quickly ruled that out。

 because there are so many wonderful features that make writing Sql so much easier in P。

 And so there was a debate for a while， but I think at this point， we're pretty much P。

 And in this class， I just use P。 And given when I just said all the stuff that I just said。

 you can debate for a while， but I think the debate is kind of over and P has won the debate。

 And so I just want to show you some sample code， because you may run across code。 Okay。

 And so the old classic my SqL， you can always。

![](img/55ab2087ba8aaa5805f249fc13b572c1_8.png)

![](img/55ab2087ba8aaa5805f249fc13b572c1_9.png)

This because it always starts with my Sql underscore。 It's like， oh， okay。

 this is basically less than PhP5。 It's not object oriented。And has all kinds of sort of flaws。

 but it's flawed from an architectural perspective。

 but it's beloved from a sort of beloved from the fact that we've been using it for over a decade and got really good at it。

 And then there's the minusqL I。 You see that it's like new， it has this thing。

 and it's only does myqL and the query minusqL underscore query becomes minusqL arrow query。

 And this is really just a one to one translation for the except it's O0 and it's O syntax。

 and it has the advantage of you could make more than one database connection to if you have an app and you have connection to two databases。

And then you can do that。 But I think very few people have ever used that。

 And so what we end up with is P。PDO is an object or pattern， has a new thing， it does this stuff。

 and it tells what database it's going to use， et cetera， et cetera， et cetera。

 and then we run queries， and then there's a slightly different thing so the difference here is not only is this P object oriented。

O stands portable data objects。 It also has a different API pattern。 And so I， like I said， I。

 you know， I thought I'd like this。 And， but now I just love this。 and I don't like this。

 And I don't like this。 And so here we are P。You might see this stuff right。

 so be ready for it and whatever it is， ultimately the goal of all the PhP is to create this string of SQL and send it to the database and then get some records back and then loop through those records。



![](img/55ab2087ba8aaa5805f249fc13b572c1_11.png)

So up next， we're going to actually talk about how we insert data through PhP。



![](img/55ab2087ba8aaa5805f249fc13b572c1_13.png)