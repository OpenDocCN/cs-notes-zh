# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P75：11_PostgreSQL自然语言索引实践.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So that was pretty complex and I hope you learned some SQL and had a little bit of fun knowing that you did not have to depend on Postgress for your text inverted language aware。

 natural language index using Gin and all these other things but the reality is as we well know the easy way to do this it's just Postgres do all the hard work Postgress already knows all these languages and a away it goes so let's talk about the concepts required that you need to understand and then how you make these indexes work。

So there are two really important functions and there're actually data types as well。

There's this notion of a TS vector so that the TS vector is a text string vector。嗯。And。I don't know。

 I don't know if I should explain why they call it vector。

 I guess I will explain why they call it vector so the idea is is that they're trying to in N dimension if this if this next thing。

If what it makes sense to you， don't get too excited about it。

And just I'll just I'm not going to ask you this like on an exam or anything。

So the idea is is you have to you place a document in an n-disional space right here。

 I've got a three dimensionsional space because we got a little bad threedimensal space that I've written and so you can take and put things at various places in this three dimensionmensal space and then you're kind of looking for closeness in threedimenal space。

 and that's how you do it， but it's not just three dimensions。

 it's n-disal and so there's vector is the vector from where the origin to the particular document that you got and so you're trying to cluster in n-disal space。

 and if none of that made any sense to you。 don't worry about it。 It really doesn't matter。

 but that's why they call them vectors。 You could also think of it as it's a fancy array because a vector is sort of a fancy array So there is this function in Postgres called two Ts vector and you'll notice that it takes two parameters。

 the first parameter is the language that we're working。

 remember I told you how important languages and we all showed you that there are many languages that Postgres already knows。

 I'm just you havent used in English and then the string。



![](img/2fd9d36bd14e2b3bd6c990e02cd0adf2_1.png)

So that basically says， hey， that's an English string。Let's extract its features。

 let's extract the nature of that string stemming。

![](img/2fd9d36bd14e2b3bd6c990e02cd0adf2_3.png)

![](img/2fd9d36bd14e2b3bd6c990e02cd0adf2_4.png)

Case， etca， eliminating stop wordss， that's all in there right there is all the work we did with stemming and all that stuff。



![](img/2fd9d36bd14e2b3bd6c990e02cd0adf2_6.png)

It also keeps track of the locations and there's a whole chunk of waiting that we don't have to worry about。



![](img/2fd9d36bd14e2b3bd6c990e02cd0adf2_8.png)

But there's waiting and that might have to do with you want to wait the title of more than you want to wait the description you can even concatenate rows together I mean concatenate columns together to cr create metacolumns but really all it does is it extracts the features。

 the essential features of a phrase or a document of text right and the positions and so you'll see later when we get to ranking that the position matters a little bit and you can even have things like I want to search for Python followed by SQL or SQL followed by Python now in this particular that's probably a bad search but the ordering can matter and so these TS vectors keep track of the order of the things in the document if you watch the map cuts video you'll see that sometimes if you say Python SQL and it's closer together that actually means more than if it's farther apart so distance between the words if you're searching for more than one word。

And so that's what the TS vector does and that's the TS vector generally is the thing that we index on。

 so if we go back to what we did before we indexed on a string array。

 so we now we're indexing on this TS vector。And Postgres knows everything there is to know about TS vectors because they invented them and the indexes are very smart about TS vectors。

 okay？And then when we're going to do a where clause， we create a thing called a TS query。

 and the TS query basically says。Break， apply stemming rules， apply language rules。

 apply stop word rules， you can have more than one one word。

 this is a real simple one and you can see in this case when I do a select a TS query English teaching。

 you see that the result is a stem diversion of the word teaching so teaching stems down to teach and so you can see also let's you can also see that the STM happened from UMSI teaches Python and SQL。

 the stem that teaching the teaches stemmed down to teach。

 but then in the query weve got to stem it down as well turns out this whole idea of query stemming stemming of the queries。

 there's a technical term for that and it's in one of these Wikipedia things it's called conflation。

I don' exactly know why they picked that that's a cool word。

 I've never used conflation in a sentence， so the applying of the stemming rules from a TS query。

 from the input to the TS query to the output of the TS query is using conflation。

 so I get to use conflation in a sentence， so that's called conflation。

And so then what we do to make a wear clause is we combine a the most typical wear clause is to combine a TS query in a TS vector。

 you could actually say， is this TS vector equal to that TS vector that works too。

 but this double at sign operator is the cool thing and you basically say hey。Here's a query。

2TS query English Teaching is that sort of contained within the2TS vector in English of UMSSI also teaches Python and SQL。

 and in that case，It's true。It's true right so it says that query matches that text even though teaching is not in the string but teach is in the string and so you see how this sort of softer but clever matching is there so I think that's pretty cool and just show TS vector。

 takes any document， reduces it to its essence including position and then TS query takes any string and reduces it to its essence in a way that can be matched to a TS vector。

You did this the hard way in SQL， now we're going to do it the easy way in Postgres。

So we're going to create our same table， docs with just one column of a document and then we're going to create Gin using T2 TS vector that was that function that converts a column into a smart array with all the stemming etc etc and we have to tell it what language we're dealing with that's why you need to know which language these things are and you'll notice that this is actually simpler and the string one because I didn't have to say the operators and that's because like the Gin and the TS vectors are good friends and they know what's going on and it has there's some ops for it but it's like oh it's a TS vector I know what you're going to be doing you're going to be doing the double at sign operator I know exactly what you want to do here you go I'm taking care of it and so this isn' in a way the natural language is simpler than the string。

 pure string generalized index and we're just usingGin you could use just again going back to that just useGin unless you have a reason to use GISist。

So we throw some things in there and it fills up the index and then we're doing a where clause and we can say you know。

 do TS query， English learn。At@ to TS vector English doc。Again， if this didn't have an index。

 we would simply retrieve every row， compute the2 TS vector。

 and then check to see if it double added the TS query。But that's not what we want and of course。

 we find the row row two is the one that matches， they learn， right？So learn。

 and then if we do an explain on it。2 TS query， you know explain select ID doc from docs where2 TS query。

 English comma learn， double at sign 2TS vector English doc， that is where it's a where clause and。

The wear clause matches the expression that's in the wear clause with the expression that was in the index and says you know what I can use that index and so that's again when you fail and get a sequential scan。

 sequential scan is not our friend， no sequential scan， but instead we got a nice little index scan。

 heap scan。Anything with sequential scan in general is a success and so you again you're going to do this and you do these over and over and over in little sample examples until you get it right and then you're going to want to do and explain on every single query that you're using to make sure you sort of didn't fall apart right you didn't like add an an clause or who knows what it is that you're going to do okay？

So that pretty much gets us to the point where we have created a index and we can query that index and it was pretty easy up next we're going to see how you're going to rank the results again。

 kind of taking a cue from Google and the other search engines。

