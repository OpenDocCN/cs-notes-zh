# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P49：20_文本处理函数应用.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/369f55114b22912d825bc3eeae2132f9_0.png)

![](img/369f55114b22912d825bc3eeae2132f9_1.png)

So now we've got some text in our database， we're going to talk about the kinds of things we can do manipulating functions。

 where clauses， etc。So there's a couple of things that are standards in here and I'll try to call out the things that Postgres does a little bit differently。

So we've already looked at where clauses that have equal signs， equality。

 those are actually really important because they are the most performant。

 especially if you have an index on a string column。

Like is like a simple wild card that you can put a few characters in。

 similar to is a kind of like a regular expression most people don't like using similar tube because。

I know regular expressions are a little bit hard to learn we're going to cover them。

 but once you know regular expressions， they actually translate not just in Postgres。

 but actually in Uniix and other things like Linux you can use use them and so I don't think don't think similar to as much of a good idea and it's not even particularly standard like is actually more standard across databases like post my SqL and others and then you have。

Your basic equal s greater than less than greater than equal to all that stuff in between and in in is gives you a set of things。

 So you've put them in square brackets。 So like if the where this column in this comea this of this come this in square brackets。

 Then you can manipulate the select results like lower lowercase uppercase。

 taken out a substr and you can put these in where clauses too。

 And so we'll talk a little bit about know part of the performance I've always been talking about the performance where you either sort of it either kind of goes into the database engine and the database engine optimizes or ultimately you've got to pull back all the results。

 loop through all the results and then apply the where clause there。

 So we'll hit some really good examples of those coming up。

So Postgres has an outstanding documentation on these things I really like how they did it there's just two pages and they've got little simple examples and like yep。

 I got it so I'm not going to sort of read all these things you can go into the Postgres documentation which is of course free and online because Postgres is an open source project and so you can you can just look at this stuff and I'll cover some of the ones I want to cover one thing he'll notice and I don't quite know the history of this is that there is a bit of commonality between Python string method names and and the Postgress call so that they're a little easier kind of like that generate series kind of feels a little bit like range。

So。We're going to start out and do a couple of things。

 And so I'm going to make this table called text fund that's got a。

Unlimited length text field we'll talk in a bit about the length of these things and then I'm going to do an index just make an index on it and that basically allows me to go quickly to various things with equality This by default is a B3 index that's why you named it underscore B is's a B3 index and B3 index are good for sorting they're good for exact lookups and they're good for prefx lookups and ranges and so they're kind of like to go to index in most databases we'll talk a little bit about hashing they're sometimes take a little less space。

 but they have their own compromises and so when you just say create index。

 Postgres will generally make you a B3 index and you basically say it's in this column of this table So here is a couple of cool things that we're going to start playing with a little bit so you get and this is all about tradeoffs space versus speed tradeoffs Pg underscore relations size basically it says how much data is what's in this currently。

This Re taking。And then how much size is the index。

 So what you'll notice is I've just created this table and there's nothing in I've put no data in。

 but the index is already taking up some space。 and index is kind of the whole idea of an index is you're trading off space for speed and so don't get too grumpy about the space。

 and especially in modern computers and disk drives space is generally not your problem。

 but speed is your problem。 And so I will call attention to these。

 but don't think to yourself that your goal in life is to make these as small as possible。

 actually when you're using indexes your goal is to make it fast， whether it's fast for inserts。

 deletes， updates or reads And so but this is really cool And if you're working on something way more complex than this。

 you can say， hey how much is this taken up and how much is the index taken up but like I said。

 don't get too concerned because the reason you're doing an index is to go fast。Okay。

 so so we start here and so now what I'm showing you is this from the previous section。

 this random generation。 and so this is one SQl statement， you'll notice there's no semicone here。

 so I'm going to insert into text fun and then this this is the columns that I'm going to insert。

And then I actually have a select statement。 This is a continuation。 And this is this normally。

 you'd say values。 blah， blah， blah。 Here what I'm doing is I'm actually doing a select statement。

 which is generating a set of rows。 And then those rows are going to be insert it into text funds。

 So this is an expression that generates a row。 and then it inserts into content。 So here。

 here's another syntax， the case statement。 So you can't do if then else in。SQL。

 because it's a procedural， it's not a procedural language。 FN L is like loop， if， loop if。

What you have to is write this in a statement that's sort of for all rows true or false。

 So they don't give you an if statement。 They could give you an if statement。

 And you just say it's there's a loop implied around it， but they didn't。 They call it when。

 And this is universal across all S Q L， they don't call it if。 So when random is less than 0。5。

 then this。Else that。 So this whole case bit from here to here with the end。

 this part and parentheses right here from case to end， that generates one of two strings。

 It either generates this neon string or this lemon string。

 You see my racing car sort of sneaking in here in some of my thematic stuff。 So that is like。

All it's saying is half these records that I'm generating are HtTP， blah， blah， blah。

 the other half are HtP， blah， blah， blah， and then I cancatenate that with generate series from 100000 to 200。

000。 so this is going to basically generate 100000 records。In one statement。

 so that that's how you do it， so using those things from the previous section。We generate the stas。

 and now you can see that that we got。6 meg here。 and the index is even larger 8。5 me。

 And one of the problems here is we're using a big long text field。

 And the problem is that if you're using a bee tree， it wants to be able to know for an exact match。

 it goes down the tree and it finds the record and then it checks to see if it's true。

 So the thing that's being indexed， the columns being indexed content ends up being completely replicated in the index。

 So there's two copies of these strings。 and I didn need even make these particularly long， right。

 there's just a lot of these now。 these are a lot。 and I could have made these much longer by concatenating more repeat。

 like on repeat or something on here。 Would I take blah bla。

 blah bh blah over and over and over again。But you'll just see that the index grows faster than the data。

 Now in a normal world， in a normal world， you would。

You' would have a lot more columns here and the actual content of the database would hopefully be much larger。

 I'm just doing this with one column So you kind of see how the database grows a bit。 I mean。

 the index grows a bit。 and in this case it's larger than。

The actual data that's stored in the database。Again， don't be concerned。 we're trying to be fast。

 but actually just indexing a big long text field is not necessarily the best idea。

 So if we look at the first five of these records， we kind of see our our randomly generated stuff。

 some are H TtP， some H Ttps and they have kind of a different string and this we're going to be doing some text functions and that's why I came up with this stuff。

 and and so we can see the sizes of these indexes。And so that's how we did that。

 So this is just once those things are set up。We can use a light clause。

 so the light clause uses percent as a wild card character。

 kind of like we think of as asterisk and some wildcard。

 This matches any number of characters that matches any number of characters。

 So what this is really saying is 1，5，0，0，0，0 anywhere in the string。

 You can take like the upper case of this。 You can take the lower case of this。

 This is the same light clauses you can there's a whole bunch of chopping functions。

 like give me the four right characters， the right four characters。

 which gives you the end the four right characters and give me the four left characters。

 And so you can get that。 So these upper lower， right and left。

 they can actually be used in where clauses as well。So。Here's another one， yeah， that's that one。

 so you can like ask where stirpo。This actually born like C。 This is actually not Python。

 This actually looks a lot like P P2 Stpo。 within this string， tell me where the T T P S starts。

 And that's in position 2。 This is pull out a substr from it。 Give me starting at character 2。

 go for character。 So you get H T T P S。 There is a way to split it。

Now it's not a thing where you split it and then loop through it because you there's no looping。

 right， so you have to tell it， I want the fourth part after splitting it into slashes。

 So there's a slash slash。Slash slash， so this is the zero part， the one part， the two part。

 the one part， 2，3， four， and so out we get is neon。Now， this translate。

Its just another you may or may not ever find or thing for it。

 but there is this translate is actually from the UniX TR command and it gives you two translation strings and it allows you to do a one to one translation so T lowercase T goes to uppercase T。

 lowercase H goes to uppercase H dot goes to exclamation point P goes to uppercase P and slash goes to underscore again。

 this is completely silly， but the H's H H's T's and p's are all uppercase。

 the slashes are underscores and the dots are exclamation points。Why you want to do this。

 I don't know， I'm just showing you how the TR and so there can be one or any number of characters。

 but this second string has got to have the same number of characters as the first string because it's like a character translation map that is you know each character goes from the one to the other。

So let's talk a little bit about how this performance works。

And this is the first time that we're seeing this explain idea， so select content。

 this is SQL statement。And in this case， we're going to use a light clause in prefix。

 So that says it's got to start with racing， and this is actually something that works really well in be trees。

 And but instead of running it， we're going to do explain analyze those are。

I'm not sure they're SQL commands， but they are commands to Postgres to say， you know， run this。

 but tell me a bunch about it。So so here's a couple things to look at the output and I've taken a little bit of this output out。

 this is an index only scan and that's the kind of thing you want to see。

 you don't want to see a sequential scan on the whole thing。

And so it's using that index text fund B that we define that's our Bre index underscoreco B is just my way of remembering as B3。

 And then you look so I talk about what happens when you like look at all the records versus what you send into the database engine and so what it's really doing is it's turned this like into a an index condition that says look for records that are greater than or equal to racing and less than or equal to racing H race in H so that's going get so the greater than are equals than less than this was constructed by Postgress right and so it's like to racing to race in H and that is actually the racing ones because it's less than race in H and they know they're ordered and again that's the whole idea of the Bre that they're ordered and you go from here to hear and then you get the records that you want and this has got whatever 100000 records in it and this explain analyze there's a way to say without analyze and it just tells you its strategy but explain analyze actually。

Runs it and tells you how long it took to run it。 So that took 10th of a millisecond and a millisecond is a0th of acond。

 so that's1，10000th of a second。 so that's pretty fast okay。

 to get a row from our database and that's the kind of speed that we like to see。

Now if I only change one thing and I make it so that it's racing anywhere in the string。

 not racing at the beginning， then you see this in the explain as soon as you sequential stand。

 you go oh， I failed， I've written a a bad query right and so what it basically says is the oops。

Is the filter？Is we're going to check for this in the text and we're going to read all these things and it read all those rows。

 it actually couldn't do it in the database using the index it just had to pull all the rows back and look through all the rows and it was thrown them away and it's like。

 okay I'm going to throw away it had to throw 100，0001 rows away because it didn't find any rows because none of these rows in this database look like racing at all。

 they're not in there it's got neon and lemons and other stuff like that。And it took that 10。

271 milliseconds now。That's actually， let's say 1。 that's 1 hundredth of a second。Now this。

 and you might say， w， who cares right， well， the problem is is this is only 100，000 records。

 there's lots of things that have more than 100000 and the other problem is is these are short records。

So as you， I have one column in them， that's it， I might have like 40 columns。Way more。

 And so this problem is， is that this kind of stays the same as your data length and width grows。

 and this gets bigger as your data length and width grows。 And so， so this， if you go here， this is。

I think this is a thousand times slower。RightA sequential scan in this tiny database is a thousand times slower than an index lookup。

Right。Sog。Yeah， here's the creating index。 And so here we go。 Now I like says ignore case。

 and I don't quite know why it's so bad， but it's three times worse。

 So if you're going to ignore case so。You know it's really beautiful to write these things。

 So as you're writing as a database developer or a software developer， you write these and you think。

 oh， they kind of do the same thing。 And the answer is no。

 one of these is scorchingly fast and the one is slow and the I like which is ignore ignore case it has to sort of get the data。

 change its case， change the case of the of your wear clauses through string and then do do the searching and even though this is a prefix it doesn't do much good So its not it's not good And so you got to just this is where and it's so easy to run these right you just make your select statement and they say explain analyze and you not to always look at these numbers but you just what you're trying to do is avoid sequential scan。

 although for me I'd be like okay I put a percent at the beginning I'm gonna to get a sequential scan I mean after a while you kind of know this stuff and I said Bearies are good for sorting they're good for exact match look up and they're good for prefix look up。

 which means they're not they don't help you I。you， but they don't help you。 they take up space。

 but they don't speed you up if you're doing like sort of not prefix matching。

 which is the example that I'm using right here。So this is fun， I guess I call it fun。 Okay。

 so the thing I want to show you here is how these sequential scans work。

 And so this is an example where we have two sequential two sequential scans。

 This is the one we did before where it's a sequential scan because it's a like that is in the middle。

😊，And so this one's actually going to match， right。呃。This one's going to match， but watch this。 oops。

 it has to read all the rows because it doesn't know if the first row or the last row is going to match。

 Now， we know， given that these have between 100000 and 20000， there's only one， right？

 So in this case， we've added limit1， right？ So what happens is it as it's going through the data。

 If it encounters it。Then it can stop。So this is where if you know in your mind。

 there's no way the database can know that there's only one in the case that you're looking for 150。

000 anywhere in it， it doesn't know when it can stop because it might find  zero， it might bind one。

 it might find 1000 and it has to read the whole thing。

 so it takes 1914 milliseconds to read the whole thing。

 but if we can tell it limit one because we kind of out of band knew that we generate these things。

Well， that's actually halfway through。 And so you can see that it drops it to 8。

732 milliseconds from 14。 And literally， depending on the number that I picked。

 if I made this 100000， it'd be really fast。 And if I made it 1999999。

 well then it be 14 milliseconds because it really is a sequential scan and the sequence is not necessarily sorted it just the sequence that we inserted them。

 which happens to be in order。So these sequential scans can be improved by adding a limit one to them。

So。So here's the in clause， remember I told the in clause I just want to show you an example of in so explain analyze select from text fund where content in this is a set it's you can almost think of this as where it's equal to this or this or this or this or that and so this is just two things right？

And so this is either we don't know if it's an HDP or an H to remember 50% of them have it one way or the other and so this in clause。

 and so if you look，And you say， how's this going to work， Well。

 the good news you see right away is index only scan right？

 And then this is kind of when it's saying the index condition。

 it's sort of translated to how you expressed it into how the database engine is going think about it。

 But the database engine has access to that index。 So it's like I'm going to do two probes to the index。

 And so you see that this is this is a little slower than one probe to the index。

 which was a aware clause that's equal， but or a prefix like clause。

 but this is like it knows it's going to have to do one for the first one and one for the second one。

 but that's it。 So this is took a little bit more time。

 but it still some some scalable now the uparrow there。

 So this one here is yet another advertisement for why it is that you're not supposed to use subse。

 So you might decide that you're going to sort of do something like， oh， this the in clause is great。

 So I'm going to do select content from text。😊，Fun， wear content in。

 and then I'll have a subselect to get those two records， right well。So here's a sub selectlect。

 And remember， I talked about subselect。 The subselect runs。

 It produces a nice little two record record set in this particular case。

 And then the outer part runs really fast。 The in clauseaws runs really fast。

 but the inner thing ran really slow。 And that's kind of what it's telling you here that inside here。

 it's doing a sequential scan。 And then the second， the outer part。

 And so this is likeca this was a subselect， right， And then this is the select。 And that was fast。

 but this was horribly slow and it's still 14 milliseconds。 right So it's 14。

 a little higher because it does two little index look ups at the very end。

 But it took you so much to figure out what those two strings were。 It's like， no， you lose。

 you can't do it。 So again， this is just an advertisement for not using subse。😊。



![](img/369f55114b22912d825bc3eeae2132f9_3.png)

I'll have plenty of advertisements for not using subs like syn in this class So we talked a bit about text and text functions。

 and up next we're going to talk about character sets。



![](img/369f55114b22912d825bc3eeae2132f9_5.png)

![](img/369f55114b22912d825bc3eeae2132f9_6.png)

![](img/369f55114b22912d825bc3eeae2132f9_7.png)