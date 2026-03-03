# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P93：29_PostgreSQL的JSON支持.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So now that we've talked a bit about JSON and JSON inside Python。

 we want to talk a little bit about how we store structured data inside Postgres So Postgress SQl support for JSON has evolved over time I kind of mentioned we'll talk a little more later about how it is somewhat a reaction to the emergence of JSON based no SQL databases and everyone seemed like JSsonN and like using JSON inside databases and traditional relational databases and Postgres before 9。

4 didn't support that and so people are like well you know I want to use JSON someone just leave Postgres Now Postgress has a lot to like and a lot going for it。

 but so the question was was the market going to all shift to no SQl databases or were the relational database is going to add support for JSON and so you can see the support for JSON sort of coming into Postgres sort of slowly。

 which I think is an excellent engineering strategy where they were put in things like eight store and then the simpler。

JON format and then eventually the JON B format， which is what we pretty much use today。

 so there are three supported column types and it looks a little weird to have all three of these column types。

 but if you think of it from a historical evolutionary perspective it's not really nearly as weird。

So the eight store column。Is sort of a precursedor to all this。 And I think it's a beautiful。

 beautiful structure。 In a sense， it's like saying I'm going to put a dictionary in a column。

 just a bunch of key value pairs。 And later we'll talk about the idea of do you really model every single thing in your UI and another column in the database or do you sometimes just kind of thrown together in one column because you're not querying。

 et cetera。 And H star is an excellent excellent way to take 40 columns and collapse them 40 columns that don't really need。

Weare clauses， but you can actually put wear clauses in each stores， too。 So it's a way to。

To also have an expandable schema so you can throw a new column in there。

 a new data element in there without actually altertling and adding a new column。

And that's not to say that everything should use H storeO or that you should never use H storeR。

 but there are times when it's really nice to just have a schemaless little corner of each of your rows。

So H star looks like you know a dictionary， a maps to one， B maps to two。

 and that's in one column it's kind of like an array。

 so Postgre has an array column and it also has a key value column and so that's kind of a。

That maps very well to list a dictionary， array an object and all this sort of linear and key value structure。

 so H store is great， it's kind of a good complement to erase。

But you can't do nesting in them right so you got one set of values and that's it。

 you could name your keys with X， Y，z something， something， you could get a naming convention。

 but you're not allowed to go deeper。So the first JSON that was in Postgres 93 earlier was really a glorified text field。

And there are things you can do with text fields and I'll show you in some of the demonstrations or some of the demonstrations you've already seen where I'm doing things like digging into a text field using a regular expression and building an index on that and then using a word clause with that same regular expression and having it do an awesome lookup It pretty it's amazing right and so at some point think of the JSON as just text and then you do sort of regular expression work inside that。

And then you build some functions to make some of that regular expression a little bit easier et cetera。

 et cetera， et cetera， and you have things like the generalized inverted index。

 the gin and you teach it a little bit about JSsonN these text JSsonN fields and the way you go and that's text so I could see how you'd put that in an early version because you could get that in earlier and quicker and then。

The JSON B， which is the really cool column type， is it's not a text field， it pars it。

 it knows that it's JSON， it keeps the key value pairs very nice and very dense。

 I just imagine all the cool optimizations that it can use storring JSON when it knows it's JSON it knows what's the rules are。

 and perhaps it even knows that there's a lot of similarity between some of this JSON。

So the JSON B in many ways has the advantages of the indexing and looking up and the dense storage of the H store。

 as well as the flexibility and the nesting and the coolness in general of JSON where you want to do the stuff that's sent across networks and JSON。

 etc。You can read up on the internet whether you should be using H store， JSON or JSON B。

 but I would just say when in doubt use JSON B because that's where the market is going to expect that Postgress will have to invest more and so if you want to want to use something that you know is going to be sort of focused on by the performance of JSON B is critical to the future of Postgres。

 the performance of H store is not nearly as critical because with JSON B。

 Postgress is competing with things like Mongo DB and you see blog posts like the ones I've got where people like I tried Mongo and I quit you went back to Postgres and that makes the Postgres people really happy and JSON B is the key thing that makes that happen。

So now that we've talked about the things that are not JON B and a bit of the history of JON B。

 went too far。Let's actually talk about the JON B， I'm not going to talk about each store much more JSON and so this I will do a nice walkthrough of this。

 but basically what we're doing in this one is I'm take going back to my iTunes export export。

 it came out as XML data。I converted it to CSV in an earlier part of the class。

 and now I'm going to convert it to JSO and we're going to load that all up into a JSON to kind of play with our first real JSON database。

And so we're going to make a table。That just is got a primary key， ID primary key。

 and a body that's of type Json B。And we got a clever little copy command。

 a clever little copy command。Is reading a file of JSON that has one。

 every line is itself a JSON object。We're reading it as CSV， but it's kind of tricky。

 we're telling it the quote character is something nonprintable and nonexistent and the delimiter character is something nonprintable and nonexistent。

 which means every line becomes。A column basically so we're going to end so that but it doesn't matter because we're inserting it into body。

 we're only looking for one column。 And so it's reading line， line， line line becomes row， row， row。

 row row with that column except it is JsonN B。 So that means as this is being parsed and put in。

 And if there was a type of a mistake in the JsonN or the JsonN wasn't pretty had this thing would blow up and say bad JsonN and believe me I've done this as I was making it all work。

 I blew it up a couple of times。 So the copy command loads in all that stuff。

And then we are going to play with some of the operators。

 the coolest operator is the I call it the double arrow。

 it's dash greater than greater than what that basically says is when we see select body arrow arrow。

Count and the count has to be in quotes because the keys。In this Json， R。

The keys are strings right the count is a string so you've got to look up the thing inside this JSsonN body under the key count and then this colon colon int that says convert it to an integer。

And we can do this in a wear clauses where the body arrow， arrow name。Is summer nights。

 so that's basically saying select the count， the number of plays from JTrack where the body where the name of the album。

 the name of the E track is summer nights。The other thing you can do in the wear clause is use the contains operator。

 the at sign greater than operator。This is particular to JON B。

 this equal operator for the body named Summer Nights， that was a string comparison actually。

 because we retrieved the name and then converted it to a string。

The double arrow converts it to a string， the single arrow body with one arrow。

 one look greater than that would convert it to JSON B， and that would make that equal not work。

But what you have on both sides of the at sign greater than is in effect a JNB document。

 and so it's really an intersection its saying，Does body intersect with a tiny little Json fragment of named summer nights？

So if name the key name goes to summer nights and so it looks through all the whole JSON and it looks to see if it overlaps。

 so is there a mapping does it overlap where there's an overlap， that's why it's contained。

 does body contain name summer nights？ThereAnd so that's what the at sign greater than is。

 and then the question mark actually simply says， does this JOB body contain a particular key？

And you can use these things in order by like， you know。

 select body double arrow name as name from JTrack order by body double arrow count， cast to integer。

 and then descending。So that's basically the major fun operators to play with that we have。

Create some indexes， you don't have to use gin indexes you can also just use B3 indexes so in the situation I can say look I would like you to create an index。

 I want you to look inside the Json and I want you to make an index for body double arrow name so that just that's no different in a way than a column you could actually pull that out and make a column called name and then index on it or you can just index right into the SQL and so I think that's really beautiful and you don't have to just have one of those things and so it means that wear clauses like。

This wear clauses would be optimized and use the。Use the index to speed themselves up。

We can have a gin， the generalized inverted index on the body， and that really looks for the tag。

 the key values， and that speeds up things like this question mark operator。

And then if we do the more richer inverted index and we do Chase on the path ops that looks at all of the key value pairs and gives you an inverted index of the key and the value and that's what speeds up things like this where body contains name summer nights and so these indexes we' play with those indexes and create those indexes and then run queries and watch their performance based on those indexes that we create。

And so Postgress really understands the JONB， it's very efficient， it's very fast。

 and it's a critical， competitive element of Postgres in the market going forward。

