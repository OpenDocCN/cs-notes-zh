# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P70：6_SQL自然语言索引演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Okay， so now we're going to get a little more complex。

 We are going to take advantage of the naturalness of our natural language。

 And so let's take a look at the sample code again。This is in HttPS， wwwPg free。

 com slash lectures s05 full text。 sql， and you can download that and then。

So go search for stop words。So。Here we go， so the idea is is we're going to move everything to lowercase。

And we're going to have a set of stop words that are meaning free， like and and for and whatever。

 So let me go ahead and drop docs with a cascade option and then create the docs。 this。

 the structure is the same。 We could probably just delete the。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_1.png)

呃。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_3.png)

Delete the rows from it， but we'll recreate it just for yucks。Come back。😔。

And then we're going to insert some records。Insert the records in， so we got three records inserted。

 the same ones that we've been playing with。And so you know this same thing that we've done here。

 we can break the columns into know one row per word press a primary key with the select distinct with the unnest and string to array of the dock。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_5.png)

The dot column。But you see that some of these are uppercase and some of these are lowercase。

 and we want to kind of eliminate the uppercase and lower case。

 And so what we're going to do is the only change we're going to make is we're going to take the string to array and we're going to convert the document to lowercase before we split it。

 And that's all we've changed。 So we're going to lowercase at all。 So we're going to。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_7.png)

![](img/e67290a99fc24f23f63fcf0eb26b9f66_8.png)

Convert the doc column to lower case before we split it。

 And now you see all those keywords or lowercase。 that already is going to make our lives a lot simpler。

 Okay， so we're going to create our。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_10.png)

![](img/e67290a99fc24f23f63fcf0eb26b9f66_11.png)

Doc jin。Our Docs Gen table which is the same， it's got a keyword and it's got a doc ID that's a foreign key pointing to Docs ID。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_13.png)

And now we're going to create our table of stop wordss。

 So I'm just going to put one column in the stop wordss。

 It's a column called Word and then I' going insert into stop wordss I this an and we don't need too many stop wordss。

 but you get the idea。 So if you can go Google and stop wordss。

 you'll find there are lots of lists of very extensive lists of stop wordss。 We're going to。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_15.png)

![](img/e67290a99fc24f23f63fcf0eb26b9f66_16.png)

We're going to keep it real simple because our text is really simple。

So now what we're going to do is we're going to basically have a where clause and so you can sort of see what's happening here is。

We're going this is the creating of the inverted index。

 And so we're going to add a where clause to this thing we did before where the keyword is not in and then a sub select of select word from stop words。

 So we're going to split the documents into words， lower casing them。

And then we are going to throw away the words that are in the stop word list。

 and then we're just going to list them。So selecting distinct IDS keyword and from docs with an unnest and a string to array and where they're not in the stop wordss。

 so you see that now that we put that where clause of the stop wordss in， a lot of words went away。

 let me see if I can edit it so that I just don't even have that wear clause so I do this same thing without the where clause。

 this was what we did in the previous example。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_18.png)

Previous example。You see we had 22 rows and if we do it with a stop wordss， we have 18 rows。

 and so all the rows have been thrown away， we've also lowercased and so that lower is in there and away we go now all we're going to do is take that same select distinct and we're going insert that into our inverted index just like we did before so we're going to insert into docks gin and then the select distinct with the warehouse clauses so we end up with 18 rows。

 18 rows in the docs Gin。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_20.png)

![](img/e67290a99fc24f23f63fcf0eb26b9f66_21.png)

![](img/e67290a99fc24f23f63fcf0eb26b9f66_22.png)

And so we can do the same kind of a query now we do have to convert like lowercase。

 this query is the same as before。 All we did is didn't put as many things in the stop wordss。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_24.png)

![](img/e67290a99fc24f23f63fcf0eb26b9f66_25.png)

Okay， and so you can see something like。And do the same thing we did where you can do a multiword query。

 but let me go to this next one with a stop word query where I'm looking for a keyword of and and now I'm seeing no rows because in a sense。

 what we're doing is we're going through the dos gin looking up the keyword and then we are joining the into the docs。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_27.png)

Table from the dos Gin。 And because the wear clause doesn't find the keyword because the keyword isn't even in the docs Gin table。

And so we never put a stop word in the do， we did all the work of stop wordss as we constructed that table。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_29.png)

Okay。So that's stop words， now another important aspect of natural language is what's called stemming。

And in stemming， we convert， we we transform certain words into their stems。

 And so we in in this particular thing， Im I'm going to say that teaching is is stemmed down to teach and teach is is stemmed down to teach。

 and teach equals teach， right？ So these are all words that we're going to take that are sort of slightly marked。

Complicated or， you know， flowery ways of the same concept。

 And so teaching and teacher the same concept。 And so we map them from the words。

You know we could say instruct maps to teach even but so what we're doing is we're stemming so I'm going to insert two tuples right。

 I'm insert first I got create the table of the stem table with a word and a stem。

 so the word the first column is the original word and the stem is kind of the reduced version of the word and the idea is it works if multiple words mapped to the same stem。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_31.png)

So let's go ahead and make that， so I've got two rows in my docs underscore STM table。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_33.png)

And so we're going to do the word extraction and we're going to move it into a sub queryry just to make it a little clear what's going on。

 we got this select ID keyword from sub query， select distinct， etc。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_35.png)

And so。There we go。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_37.png)

And what I'm going to do is I'm going to join that， right， I just wanted to show you that。

And so when we select so we've got this select distinct ID from keyword。

 right that gives us the IDs and the keywords， the stop wordss have already been taken out and by taking that as an as K。

 what that creates is something I can join on and then I can join with what's called a left join onto the stem table。

As S just gives me a nice thing to say， I'm interested in the keyword in the gin table matching the word。

 which is the leftmost column。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_39.png)

And so it's probably just as easy to show you this because we're going to get three things。So。

 so what's cool about a left join， right， So I looked up all of these。

 these things Id and keyword are from the docs g。 And then you see stem over here。

 If this was not a left join， it would only show me the rows where there was a match。

 So what I did was I looked up in the stemming table。 what the stem was for the word teaches。

 and I looked up in the stemming table what the the stem was for the word teach。

 and they're both teach。 But the rest of them are blank because and and other and。

From and should they didn't have stems， not just because I didn't make stems。

 but you can see this left join allows us to do a conditional look up without losing all the data。

 And then what we're going to do is we're going to， in a sense， prefer the stem over the word。

But and and fun and is and other and Python have no stems。

 So theyre we're just going to use those words Okay so we're going to look this up if it's there and if it's there。

 we're going to use it， we're going to look teach up， if it's there， we're going to use it。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_41.png)

So let's take a look at how we do that。To this。嗯嗯。So now instead of just selecting ID keyword and stem from the two tables。

 I'm going to say select ID and then a case case when STM is not null。Give me stem else。

 Give me keyword。And as awesome gives it an alias。And then I'm going to also pull out the keyword in the stem and the rest of this left join and all that that's from the previous example。

So。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_43.png)

So。Os， yeah， there we go。So awesome is in effect， a derived column from keyword and stem。

When stem is not null， take the stem。 So in this line here， we're teaching line， I use the stem。

In the line like stuff right above it， there is no stem。 And so I use stuff。

 And so this is the way case when stem is not null。Then stem L keyword。 This is sort of if then else。

 But it's a， it's a data flow based if then else。's， I love this。 It's really a cool way。

 It's not like if， do whatever。 It's a case。 It's like when this happens， chooseose this value。

 when this doesn't happen and apply it to every row， just like most things in S， Q L。

 there's an implied loop。😊，Okay， so that's one way of preferring the stem over the keyword。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_45.png)

Okay。And there's even a prettier way to do that， and it's using a function called coalescing。

And the idea of coalescing is that it's a function that takes any number of parameters。

 and it returns the first non null parameter。 So if I say select coalesce null null U MI。

Now let me just grab them both， let me grab them both and run them both just to show you how they work。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_47.png)

So if you say select null null UMSI， it gives you to UI， if you say select Cos UMSI null SQL。

 you get UMSI， it returns the first non null value and ignores the rest of it will go through as many not null values。

 discarding them as you like。And then find a non nu value so we can actually express in a bit more elegant way。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_49.png)

In this next query， select I D coalesce stem and keyword。

 So what I'm basically saying here is coalesce stem keyword。 The keyword's always going to be there。

 and stem might be there， but stem might be null because I did a left join on dock stem。

 So if the stem is there， I'm going to knit stem， if stem is not there。

 I'm getting a null because the left join gives me a null in rows where there was no match。

 And so coalesce just sort of flattens that down preferring the stem with a back fallback to the keyword。

 You can almost think of this as like a get in python where you have a default value。 But it's not。

 So this is a very， very。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_51.png)

Pretty。嗯。I do there。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_53.png)

Yeah， so this is a very pretty way。 This coalesce is a prettier way of grabbing the index basically。

 And so you'll notice that learning and。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_55.png)

No teaching teach shows up several places and teach was never in our original thing because we use teaching and teach is and mapped them both to teach。

 which is their STEM， so the idea now is we've got we can sort of go through and look up keywords with STs。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_57.png)

So now we're going to do is we're going to take that select statement and we're going to insert it into Docs chin。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_59.png)

And so we're simply going to take this stemmed， we're going to make a reversed index of stemmed words。

 not the original words， stemmed words， stop words are gone。ra。Yeah， I think in this yeah。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_61.png)

No， stop words are not gone。That's going to insert just the stemmed words。

Now we're going to actually I probably just I should take that out。Really。

 it's most fun if we do the stop wordss and the J。Stock wordss and the stems。

 so I'll just delete from Docs Jin and I'm going down to the one where I'm doing the stock wordss and the stems。

Insert in the Docs J。Select ID coalesce stem keyword from this giant subselect。

 and this subselect has the where St keyword not in select Word from stop wordss。

 subselect within a subselect。Whi that's going to throw away the stop words and then we're going to take that whole thing as k and then we're going to left join it into the stem that is going to and then we're going to coalesce the stem and the keyword together so that we'll end up inserting stemmed words。



![](img/e67290a99fc24f23f63fcf0eb26b9f66_63.png)

So this is stop words and stemmed words， all in one glorious， coalesced left joined。

 sub selecteded magnificent awesomeness。So now if we say select star。From oops。From。

Docs underscore gin。10。We will see stemmed words， we will see stop words handled and stemmed words and sign off we have Doxgen has our inverted index。

 which is a pretty， pretty thing。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_65.png)

![](img/e67290a99fc24f23f63fcf0eb26b9f66_66.png)

Now the key is when we're building a where clause， we if we are looking for a word。

 we have to also look for the word or the stem of the word and we have to prefer the stem of the word。

So if we look at this select coalesce and then we have two parameters。

 the first parameter is a whole subselect。I might remind you that subss are inefficient。

 but we're data miners。 So we're less concerned about efficiency and more concerned about awesomeness and really getting ninja warrior good at SQL。

 which we're doing。 So you can see this coales has two values。

 and one is a look up to see if there is a stem for the word SQL， we're mapping into the lowercase。

 And if we don't find a stem， fall back just to SqL。 So we've we've got the stemming here。And。

We got the stemming and the going to lowercase all happening， and so that particular one had no stem。

 so SQL has no stem。But if I do the same thing。With teacher。You see that I get the stem， so coalesce。

 select stem from docs square word to lower equals teaching。

 and then fall back to lower the lowercase version of teaching。I've been coalesced in teach。

 So this way， I am using the stem if it's available and using the word if the stem is not available。

Now we don't actually have to worry about stop wordss because stop wordss have already been removed before we created the inverted index。

 So it's never going to find a stop Word。 Stop wordss will judge they're just there' as if they never we didn't pull them out of the documents in the first place。

 we'll pull them out of the documents， but then we didn't put them in the index。

 So that's how stop wordss work。 They just block things。

And so if we want to do the stem in some queries， we can just do a select from the docs。

 join through the docs G where the keyword is， and then this coalesce statement to do the stem look up and prefer of the stem。

And so we find three rows。We find three rows that match the。Oops。

And if we do the other one with select。Select distinct。Id。

Doc where the keyword is the coalcent of the stem for teaching or teaching itself， in this case。

 the ST is going to work。And we're going to find the ones that match the teaching stem。

 but the original documents have the word teaching in them and teaches。

And so that way we looked for teaching， but we also found teachs。

 and that's because we stemmed them down to the same word in our index。

 and then we reconstitutute it at all because we're looking at the original documents。

 not the post stem documents。

![](img/e67290a99fc24f23f63fcf0eb26b9f66_68.png)

Okay。The technical term for converting stems， search terms to their stems is called conflation。

 I've always wanted to use that in a sentence。So I hope this has been helpful to you in understanding how stemming and stop words work when building natural language inverse indexes。

