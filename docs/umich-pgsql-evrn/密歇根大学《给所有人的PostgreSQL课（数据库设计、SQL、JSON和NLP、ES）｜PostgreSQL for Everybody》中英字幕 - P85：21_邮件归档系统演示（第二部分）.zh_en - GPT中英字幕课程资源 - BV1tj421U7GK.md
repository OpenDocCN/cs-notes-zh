# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P85：21_邮件归档系统演示（第二部分）.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome back to our in progress demonstration of handling email data。

So what we've done so far is we've actually run the program and we've got 463 messages you can just do however many you want。

 you just keep on going， there's actually thousands of them。

And then what we're going to do is we're going to start doing our indexes and so we're just I'll just start this index because sometimes it takes a little while for the index to run。

 so I've created an indexes index name message G in the messages using the generalized inverted index and then the computation that is producing the array that's being indexed or is the 2TS vector using the English dictionary on the body。

 so we're only going to do an index on the body and so that that's running right now。

And so let's play a little bit and do some review。 Let's see actually this vel run is the explains that take a while。

 So we're going to look at the Ts vector and that shows what the index is being made with。

 So select2 Ts vector English body from messages limit one that is basically showing the stemming。

 So we see all of the stemmed words like notifications is not organization is organ please has been stemmed product is stemmed。

 So you see the stemming。 and so simply running the function on the body is very different。

 we get a very different thing。 So if we look at the whole body So if I say select the body。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_1.png)

From。Messages。Limit one， oh yeah， the perceptive reader will realize that I mistype from which I do all the time。

 So there's a whole bunch of stuff， right， so there's a whole bunch of stuff in here and the stemming and it through way semicols and throughway parentheses。

 you know， I stormed somewhere in there。 And so so the index is really built based on this great greatly reduced stemmed set of words。

 And that's the inverted index。 and the gin basically says for every one of these words in here。

 the stemmed case fixed words are going to point at。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_3.png)

If I say select ID comma body。

![](img/4fd243abd4c3962caf8b7cd58d968d3b_5.png)

I D come a body for messages limit one。 All those stemmed words are going to point at one so that you can。

 if you ask where golden is， it'll say， well， golden is in message1 along with all the rest of the messages。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_7.png)

So that shows our stemming。嗯。You can see I can do the2 TS query。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_9.png)

The two TS query， you know that that is the stem of easier， easier is， so can I change that to easy？

So easy turns into the TS query is in effect taking the where clause。

 the thing that we would do the comparing to and making sure that it whatever word is in your where clause or the thing you're looking for matches whatever things。

 so like notifications， so notifications should go down to Not。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_11.png)

![](img/4fd243abd4c3962caf8b7cd58d968d3b_12.png)

so that does it， so that makes sure that we do the stemming process before we create the thing that we're going to look up in the inverted index because notifications is not in the inverted index at all。

And so now what we can say is we can make a we can find whether or not a query in the double at sign。

 so here I'm saying select ID2 query， English neon， double at sign to query English body。

 and so that's taking asking the question is neon。Appropriately stemmed， et cetera。

 in the body in English。 And I'm going to look at the first 10 messages。 Now。

 I'm going to guess that neon shouldn't show up anywhere there。 Yeah， false， false， false， false。

 false， false， false， false， false， right？ So there we go。

 And so it's it's all falses because the word neon is not in there anywhere。

 But if I can look for the word English。And' now I'm just printing whether it matches so we can kind of understand how where clauses work and so if we see easier。

't that didn't show up， put let's look for something that we know in here that's going to be there easier wasn't in any of the rows。

 but let's put notifications。Because it's in all of them， true， true， true， true true。

 Let's look for golden to see if golden， the Ts query of golden is in the in the TS vector of body。

And so we got a true message one is true and the rest of them are false。

 And that f Cla Glenn Golden wrote message one。 So that gives you a sense of how we use this。

In a where clause now what I'm going to do is just so I can keep track of things。

 I'm going to actually add a column that wasn't in the original database。

 alter table messages add column sender as a text column。

And so then what I'm going to do is I'm actually going to do a substr。

 let's just do a select on this。Select。Substr headers and then a complex。Regular expression。And。嗯。

Messages。Limit。

![](img/4fd243abd4c3962caf8b7cd58d968d3b_14.png)

10。OkayAnd so this is pulling out those email messages。

Email from names and then I'm going to do an update statement so that I get a new column I'm populating this new column。

 the sender column， and I'm populating it by running through and parsing all of the headers。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_16.png)

And so that actually built the sender。 So I can say select now sender。From messages。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_18.png)

Limit 10 and I'm just going to put that on so I can instead of having to put this sub string headers everywhere I put that。

 I'm not going to index it because that would be I want to show you other techniques。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_20.png)

Okay， so if I take a look now this just just allows me to throw the sender on various selects。

 select subject comma sender from messages where it's on about a Monday。

 so where TS query Monday is in the TS vector of the body and so this is showing now I can easily see the messages and their subjects and who sent them and so senders just there so that these look a little prettier。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_22.png)

![](img/4fd243abd4c3962caf8b7cd58d968d3b_23.png)

So now we can take a few things。Let's check to see if our index is working by using an explain analyze on the TS query of Monday into the TS query of the body。

Oh that was a sequential scan。

![](img/4fd243abd4c3962caf8b7cd58d968d3b_25.png)

So now we've waited a little while and we do the explain analyze and we do see we get a nice uses the messages in scan and away we go and now you'll notice that for example。

 we never made a Spanish index。 So if we take a look at the explain analyze Spanish it actually can do this right it actually it actually can run the Spanish select。

 it could actually pretend these are all Spanish but it's a sequential scan right So if I just run the if I just run the select。

 you see that it's capable of understanding， I mean this is really checking to see。



![](img/4fd243abd4c3962caf8b7cd58d968d3b_27.png)

Doing a sequential scan by looking in Spanish now， of course， Spanish doesn't tell us much here。

The key is this2 TS query Spanish is is a just code that runs2tS vector。

 so what it's going to do here it's going to retrieve all the bodies。

 it's going to compute the 2tS vector of Spanish of all the bodies sequentially。

 then it's going to do the 2 Ts query of Monday in Spanish with stemming and all that stuff right so we could see what2 TS query of Monday looks like。

 but it's probably going to look exactly like English， but you can kind of see that。Yeah。

 so it's just doesn't。 the Spanish doesn't change anything。 The point is。

 it runs through all of them sequentially。 Does the computation， the where clause works。

 The difference is， is because it's I never made the gin for Spanish。 It's not fast。

 And so it's not like you can't do things。 the the。The index just really makes things faster。

OkayAnd so the last thing I'm going to do here is I'm going to just switch between gin and jest。

 I'm going to drop the gin index boom， and then I'm going to create a gist index。

 which is using jest in the same thing to TS vector。And so now we've created a gist index。 Now。

 to review the difference between a gin index and a g index has nothing to do with the queries。

 It has to do with the size of the index， the cost of maintaining the index and the performance of the queries。

 And so gin is a simpler and more dense a simpler。But hash based index and it's because it's hashing。

 it's somewhat lossy， but it keeps it smaller and it's easier to maintain。 So the gist is smaller。

 easier to maintain。 But then when you do selects， you might get extra rows。

 but then it does actually check。Even with the just index， if you do something。

 it's going to maybe under the covers， pull too many rows out。 Don I forget my semie。

 under there might have been rows that it found that don't actually match the2 Ts query of English of Monday to the2 Ts vector of English body。

 It might。 But then it throws them away。 And so it just， it might actually retrieve。

 but not hand to you。 So beforehand it to you， it only sends you the exact messages。

 And so ultimately， gin and j do the same thing。 They just have different performances。

 And everything in indexes， you were always trying to trade off insert performance。

 size of index and performance of select。 And And so that that's a trade off。

 I just did this is just to show that it pretty much does the exact same thing， so。

We'll stop now and then come back for the third bit of this discussion。

