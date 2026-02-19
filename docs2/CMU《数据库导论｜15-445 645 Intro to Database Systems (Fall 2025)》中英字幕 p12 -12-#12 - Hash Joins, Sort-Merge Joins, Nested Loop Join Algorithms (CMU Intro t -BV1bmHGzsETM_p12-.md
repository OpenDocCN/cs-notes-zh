# CMU《数据库导论｜15-445 645 Intro to Database Systems (Fall 2025)》中英字幕 p12 -12-#12 - Hash Joins, Sort-Merge Joins, Nested Loop Join Algorithms (CMU Intro t -BV1bmHGzsETM_p12-

![](img/72d181f60751ca048bba849f015275d4_0.png)

🎼给我我。🎼生命叫。🎼我 game我。Think you'all forgot what rat sound。🎼still。

I' want to come today again round of Falls with D Cash。嗯。I should have asked you before。

 how's your money situation？It's game that。Getating better， okay。I mean， again。We pay you here。

 I know your radio show doesn't pay you， but still doing gigs for private party itself。嗯嗯，对 and对 two。

Why do you want money to hat？Yeah。So I had some crypto scheme going on that。Yeah。

 you lose your money on that。Just reouing， all right， that's fine。Blockchain and crypto is a scam。

 Blockchain is a terrible implementation or database。 We'll see that after the fall break。

 when we talk about transactions。that's his problem All right for you guys in the class again。

 next class this room same time we're having the midterm exam again the study guide is online the materials online on piazza everything all the notes are posted homework three solutions went out this morning so you can check that as well you need to bring your CM ID if you want to do logariths you can't do in your head bring a simple calculator your phone is fine and then a single page double side of handwritten notes again the idea here is again forcing you to like look the material and write down what you think is important rather than just trying like。

Take every single slide and make it a microfi and try to chunk it down as small as possible。

 yes in the back。😡，不一致。Yeah if you use a basic calulator phone that's fine yes because most of you don't have a regular calculator these days and then because my office hours are after class on Wednesday plus I gotta go travel I move my office hours to be tomorrow in the afternoon at 415 I'll post this some payalso as well okay so at least you want to talk to me you talk to me before the midterm。

Any questions about the midterm？Again its chapters or lectures 1 to 11 inclusive。

 so today's lecture and joins is obviously not going to be on the exam。😡。

All right and then project two is out， the recitation for that will be also Wednesday after midterm because I assume no one's going to look at it until till after midterm。

 so that'll be eight o'clock this Wednesday on Zoom。😡。

And then we'll' post the materials afterwards on Palza， yes。三超数も。The question is。

 is the real exam going to be like the pra exam where there were questions or all what sorry？Yes。

 roughly multiple choice， but some of them some of them will be if their multiple choice question isn't there。

 you can then fill in something else。It it'll look like that。好不。All right， again。

 if you can't get about databases， if you're addicted like I am。

 we have much more database talks coming up， today's talk will be at 4 30 pm on Zoom。

 that'll be from the cofoer Mother Do， the guy also was a engineering director at Single Store and prior to that he was also engineering director or lead developer at Google working on BigQury。

 and sort of the story， the Mother Dooc conductductDBs。From this guy's perspective。

 which I agree in some ways that instead center building this massively distributed database system。

 if you make the single node be as efficient as possible then that can take you pretty far so motherd is sort of pushing that story。

 then next week we'll have the spDB guys give us talk about vortex vortex as a replacement for parquet and then after that will be the guys from columnlumar。

 these are people that used to work on or do work on Apache arrow which is something we'll talk about when about distributed systems。

 but it basically is an in-memory representation of data sort of like parquets for files and disk arrow is for in-memory stuff so when to pass data between different systems they speak arrow they're compatible there' a columnar is a commercial sort of expansion of the project。

Right。All right， so today's lecture is be awesome because it's about joins and this is going to be for single No systems like DuckyB。

 this is where most of the time is going to be spent running your queries when you go distributed it with the shuffle operator。

 which we'll cover that later， but on single No systems joins as most extensive things we want to see what we can do to speed that up。

😡，So last class we talked about how to handle sorting and we again we made this emphasis on that if the database can't the database doesn't fit memory。

 the data you want to sort doesn't fit memory， then you would use a technique like external merge sort that allow you to write sequential files out the disk readquech files back in and still perform the sort operation and the high levell design pattern that we're going to that we took advantage of in sorting and we'll take advantage of today again in joins is this divide and conquer approach by taking a large problem。

 breaking up to smaller subproblems， solving those each individually as efficiently as possible and then putting result back together。

 right？And the way that the two level strategies we're going to use for both sorting and hashing and aggregations that we saw at in in the last class as well is either sorting or hashing。

 the nest loop joint will be like the dumbest thing you can do because it's just four loops。

 but with sorting hashing again these bit more sophisticated and under the right conditions can do much better than bunch of nest to four loops。

All right， so it sort of goes without saying because you did homework one。

 but why you wouldn't need to join， this will be the one slide that I pretty much only mentioned normal forms。

 this entire class， entire semester。😡，We used to teach it in the older versions of this course。

 the normal forms and Armstrongs axioms and all this stuff。

 But like in the real world nobody uses them。 And if you just use like you know if you write something in rub andveils or django or pick your favorite object later map or orM you basically end up in third normal form and that's good enough So I just want to mention this that these normal form that things exist you don't need to worry about them And then if you only end up building a query optimizer or do other more sophisticated things you may have to care about in the real world you don't need to know them。

 it's basically saying that it's a way to break up your tables into smaller tables or combine them based on some properties you may care about So first normal form be like if I take my database of all my students enroll in classes and the grades。

 I could put that in one giant table with all the columns put together that's called first normal form and obviously that's me very inefficient because a duplicating lot of data So you start breaking them out to like the students' table the enroll table in the course table that ends up being in a higher normal form。

And it's of it's a naturally way to represent data so the reason why we need to join is that if you start breaking your tables up from the first normal form of this one giant universal table into these separate tables。

 then I want to put them back together to get back to original data。😡。

That's what the joins are going to do for us， and so we want to have a join operator in our system that can reconstruct us back to the original data that we want without losing anything。

😡，Seems sort of obvious， but that's what we care about。😡。

So the join Act we're going to focus on in this class today and this semester are going to be doing what are called echojoins or inner joinins。

😡，And we're going to do this on doing binary operators。

 we need taking two tables and joining them together because this can be the most common join operator that would be executed or used in a database system。

 right taking two tables just joining them together based on something equals something something the first table equals something in the second table。

 that's the most common thing and that's what we want to focus on。😡。

Right and then we can tweak these the basic algorithms we'll talk about today to handle out things like left outer joins or four outer joins or。

😡，Doing like anti joins or like I want to see something doesn't equal something something is not in the table join those together so all the dis of we talk today can be used for handling these other type of joins they're called like theta joins but again we don't have to worry about that。

😡，There are algorithms to do what are call multiway joins。

 so if I have more than two tables in my query that I want to join together。

 there are some algorithms that can try to join them all at once but typically this is very hard to do。

 Microsoft had this in SQL server in 1998 but then they took it out three years later in 2001 because the performance was not that great。

 sometimes be really fast and sometimes it'd be actually worse than doing a simple binary join so most data systems you know about Prospace oracle My SQL pick your favorite。

 they're gonna to be doing binary joins taking two tables and joining them together。😡。

There's another class of algorithms or are modern variants of these multiway joins called worst case optimal joins。

 we're not going to cover that this semester you don't need of this class but these are algorithms that can do like threeway joins very efficiently and this is useful when you're like doing graph traversals in a relational database because when you join two tables the size of the output of the joins be much much larger than the original inputs and then you do another join to reduce it down further。

😡，I think like doing much of self-joins so we'll cover worst case Opim joins in the advanced class。

 most systems don't actually support this， the relational AI guys that came a few weeks ago。

 they're one systems that support this the Germans support this。

 but most pretty all the commercial systems don't do this so we don't need to worry about that。😡。

All right， so in general， the rule that we're going to have in all our joint algorithms that we talk about today is that。

😡，'re going to have two tables right we'll have the left table on the right table with the inner table on the outer table and we're going always going to want the smaller table of the two tables we want to join。

 were going to want put that as part of the outer table in our query plan。😡。

And we're not talked talking about query optimization just yet。

 we'll talk about this after the fall break， but it's being the Data assessments query optimizer to figure out which of the two tables are smaller and make sure we put these things in the right order。

😡，And again these algorithms today again are binary join algorithms。

 so taking two tables joined together， if I have more than two tables I want to join in my query plan or my query。

 then the optimizer I also can try to figure out what the order I want to do the join so I join A and B first followed by C or B and C first followed by A。

😡，And the way it's going to try to figure this out is based on some statistics that it's going to collect about the database system。

 about these tables， to try to make educated guesses on the right way to execute things。😡，But again。

 for this class today， we don't need where about we're really focused on what's the hour we're going to use to join the tables together。

All right so we saw this query plan last time and we said that the representation of a query plant is basically going to be either tree or a dag and it trees is a subset of a dag。

 but the idea is that we have data at the bottom from our source data for tables or files。

 whatever it is， and we're going to be feeding that up into the query plan for other operators to do whatever it is。

 the computation they want to do and then produce a final output that's in the root that we then send out to whoever's requested it。

 either a client or writing into another table， whatever you want， right？😡。

And so again we'll discuss after the fall break， we'll discuss how to what this data is going to look like is it going to be a single tuple a batch of tubs and so forth。

 and again， we'll worry about that later， but for today's discussionion。

 we need to talk about what the output of this joint operator is going to look like。

 and then how we're going to determine whether one algorithm is going be better than another。😡。

How's the data sense something going to say I want to use a Smers join over a hash join？And again。

 that's going then feed into the optimizer when it's try to then figure out， oh。

 I want to join table RNS， I want to use this algorithm and use that algorithm。

 but for us today we're not worried about that decision yet。

 we just want to know is how to determine whether one algorithm is going be better than another。😡。

So for the first one， the output， again， when we do a join。

 the basic idea is they taking a table taking tuple from one table and tuple from the other table that are getting matched on some join key。

 and I want to then match them together into a single new output tuple， right？😡。

And so what this output is going to look like is' going to depend on a bunch of different factors of how we're actually implement our system。

 but we already saw a little bit this last class when we talked about the difference between early materialization and late materialization。

😡，And now， again， we won't talk about sorting， but now in the context of joins。

 thiss going to matter because now we're going to assume the data that's coming out of our join operator is going to be used by another operator in a query plan or produces the final output so we need to decide what this should look like and how do we pass data along or whether to pass data along or not。

😡，So again， early meization is that the idea is that all the data we're going to need to do the join or anything else in the query plan is going to be given to us or fed up to us from the bottom in the leaf nodes。

😡，so now if I'm joining table tuos from R andS， the output tupo is again this is going to be a catnation of all the tus from R。

 sorry， all the attributes from R， all the attributes from S。

 and then we'll just mash them together in a system together like this。😡。

so that's what will get passed up after we do this join so I'm feeding twos up from R。

 feeding tus up from S， again I do a filter， but then if I match them on the join key where RID goes SID。

 the output result is going to be， again， all the comms for R for all the comms S stitch together。😡。

And so the advantage again earlyterization is that we never have to go back to our base tables RNS。

 to go get more data because everything's being passed up to us from the leaves。😡。

And then recall of that late materialization is that instead of passing up data。

 we're actually just going to pass up the record ID and then the bare minimum we need to actually to do the joint。

 maybe it the columns that are being used in the the joint expression。😡，So in this case here。

 I have the RID and then the SID because that's what I'm trying to join on in my own clause in my query。

 and then instead of having all the extra attributes for both these two tus or for these two tables。

 I'm just going to have the record ID。😡，And then I do my join， mash these two guys together。

 and then that's what gets passed up。😡，Then now with late materialilization。

 the problem is or the challenge is going to be that at some later point in my query plan。

 I need another attribute from table S， and that's not going to be passed along in the tuple that's coming as part of my output of my join。

😡，I can again go down， make a call down to whatever this base table is and go get that data。Right。

So the advantage of this in the context of column stores where joins are I'm not saying it's not that they're more common than OLAP queries。

 but sorry in the OLTP workloads， but in OLAP queries。

 you usually end up joining more tables than you would in an OLTP system。So again。

 in the column store system， I didn't have to go read the data from the other columns that I didn't need to do my join and furthermore。

 if my join is very selective， meaning I'm throwing away a lot of tuples because they're not matching my join clause。

 then I'm gonna have a win because the number of twoups I'm be passing up as quite small。

 then who cares if I have to go then fetch the remaining data that I need from the columns that I didn't pass up because these guys say down here could have been a billion tuples by end up with two after the join。

 and so therefore it's not a lot of data I have to go read to go complete the query。😡，Again。

 the main thing from the joint algorithm is that we're going to tape。😡，Attributs from one table。

 attributes to the other table， and they'll get mashed together。😡。

And you have to pass along the join key in order to compute that join。

 but whether or not you pass along the other attributes depends on the system or whether you're implementing late materialization or early materialization。

😡，The other thing we needed again to determine whether one algorithm better than another is the cost。

😡，So unlike in， I guess your algorithms class， it's usually like complexity defined in terms of the number of times I had to do a certain operation。

In the actual competition itself。😡，For us， when we do joins in this class。

 we're going to focus on the amount of IO I have to use for both reading and writing data。

 if I had to spill things at disk and write it back out。

 I got to keep track of those costs and then we' got to read it back in。

 I got to keep those costs as well we saw this again with the Ser mergege algorithm from last class。

So for today's lecture， we're going to that we're going to be joining tableables R&S and we'll say that for T R。

 it's going to have big M pages in the table and a total of little M twoples in the table。😡。

And then we'll have the same thing for S with big n for the number pages。

 a little n for the number twos right for this class here again。

 we're only focusing on diskIO because that's going to be the slowest thing for us。Therefore。

 we're going to ignore the cost of actually doing the actual join itself。

 like if we build a hasht where we're ignoring that cost， we get the probe of the hasht。

 we ignore that cost。😡，Last class we talked about comparing keys in the sort algorithm。

 we'll ignore that cost as well because the diskIO is going to be super expensive。

We're also going to assume that everything's going to fit on a single machine。

 and therefore we do not worry about sending data over the network。

 when we talk about distributed databases， then that all comes back。

 the network costs become a big part of the cost。Because now you may be sending things across the world and that's super expensive。

 but again for this class here， we're just going to focus on diskIs。So the。

For all these algorithm as well， we're also going to ignore the cost of the output of the operators because they're going to be the same for one algorithm within the next。

😡，I have my say my hash joint algorithm and my nest loop join algorithm they're all going to produce the logically same logical result。

 it might be sorted in different order， but again relational model is unsorted so that's okay。

 but the number of two pool is going to be passing up is' going to the same so we ignore that costs as well。

😡，对。All right， so I sort of already said this but I was as well， like again。

 the an join is the most common thing we want to do。

 a common join operator we want to do in our database systems。

 so we're going to spend a lot of time to make that as efficient as a possible and that's what this class is all about。

😡，Sometimes you see some systems also support cross joins。

 there's not really much you can do to make these things work efficiently because it's just too stupid for loops you're just taking all the tus from one table and mash it together with all the twos from the other table building a hash table or sorting things ahead of time doesn't help you in any way you obviously can batch things to reduce sometimes times you to go back and fetch data but at the end of the day there really isn't anything you can make that work really efficiently so again we're just gonna to focus on doing the inner joins because that's one the most common thing and there we can do some techniques and some tricks and make things run faster。

All right so here's the menu for today we're going to go through the most basic album the nested loop join。

 this is what most people build first when you build a database assessment that need to support joins and we'll talk about three different variants of this then we'll spend a little time talking about the certain merges join。

😡，But then we'll spend most of our time talking about how to do hash joins because hash joins are going to be the most important joint operator you can have in your system。

 and this will be what if you want your joins to run fast。

 you'd want to build this first before certainers join。Right。Right right。

 so let's look at what I'll call a naiveness of join and this is sort of a way of like this is a straw man to say why here's a bad way to do a join and then we'll see how to build upon this and make this one faster。

 right？So we're going to join a join table RNS， it's called nested loop join because the actual implementation of this algorithm is just a bunch of nested for loops。

😡，So for every single tuple in R， we're going to go get every single tu in S。

 check to see whether our join keys match， if yes， then admit it as part of an output。😡。

So the parls well use or sorry the vernacular we're use for when we talk about it joins is the inner table and outer tables and this comes from these nest for loops so we'll say the outermost for loop is called the outer table and inner the one of the middle is called the inner table。

So even though people。Even for like a hashting algorithm， sometimes you know。

 it's not going to be doing nest of four loops， but people still maybe refer to these things as the outer table and the inner table。

And in most。Most diagrams of queryplan， the outers on the left， the enters on the right。😡。

Some systems， I think snowflake reverses it right just there's not like a specific term like specific way say like within a diagram。

 this is definitely going to be the innerverse of the outer。Different systems， for whatever reason。

 do different things in their。In their visualizations of query plans。So again， I've already before。

 I already say this just now， like this is bad， don't do this。😡，Why is it bad， why is it stupid？

What's that， he say it quadratic， yes？第二。The IO， absolutely yes。So this is like stupidly naive right。

 this is just saying for every single tu and R scan S in its entirety。

 go get every single tuple in every single page， read it again。

 and then get the next tuple in the outer table in R and do the exact same scan all over again。😡。

It's naively stupid and it's super expensive。So in this case here would be the cost of me bigM。😡。

Plus the big M is for the the scanning the all the pages in the outer table and then for all the tuples in the outer table。

 I got to scan all the pages of the inner table。 So little M is all the tus in the outer table and then big M is all the pages in the inner table。

 right。😡，So。If you just put some numbers to this， you'll see how terrible this actually is。 Again。

 this is like the dumbest thing you could ever actually do。 right， So if our table is kind of small。

 right， it has1000 pages and R with 10000 twoupples and 500 pages an S with 40000 twoupples。

If we didn't plug and chuug our numbers in， we end up with us having to do 50 million IOs and if we actually put a wall clock time to say how much is the cost for given for one IO this is running on SSD in a local box is 100 milliseconds is reasonable。

 it's slow but it's a ballpark number just joining these two tables。

 if you just go fetch every single page and ignoring like hardware caching or OS caching anything。

 if I had to go pay the cost fetch every single page for the outer table。

 sorry the inner table for every single tu in the outer table， that'll take 1。3 hours。😡，Right。

So remember I say before that in general we always want to put the smaller table as the outer table。

 so in this case here the smaller table is S that has fewer pages and fewer tuupples so if I just switch the order to them and now plug and chug I got the time down to 1。

1 hours。😡，So， you， I saved what 20 minutes， but it's still not that great。So in my example here。

 these two tables are ridiculously small， assuming I'm doing 4 kilolitte pages。

 then the size of this once example here is six megabytes。😡。

Like that'll sit in easily in your L3 cache， you don't go to the disk。

 you could easily do this joint entirely in CPU cachelan。😡，And that's me really fast。

 but if I had to go pay that disguo cost。😡，If I'm naively going getting every page of the inner table for every tu in the outer table。

 it's going to be hardlyrr， hardlyrribly slow。😡，It is like the dumbest thing you can do。

 but let's see how we can actually make this a little bit better。😡。

So one simple thing is to do what's called a blocknessal loop jointin， and this is again。

 because we know our tus are not just sitting by themselves on disk。

 they're in pages with other tuups that they're friends with。😡，Then when we go fetch a page。

 we want to do as much processing with all the tus in that page before we move on to the next page。😡。

So we has changed now our tune nest of four loops to be four nest of four loops。

 where for every single block in the outer table， go get a block on the inner table and then every single tuple and a block on the outer table do the join against all the tuples in the inner table。

😡，Then we can do a little better here， right？So now our cost is going to be m plus big M times little n again。

 big M is the cost of scanning all the pages in the outer table， but now for every single page。

 for every single one of those pages in the outer table。

 now we're doing a scan of all the pages on the inner table， rather doing it on a per twoupple basis。

😡，Now our cost can be reduced quite significantly， right？So again， this question yes。

Each one of the pages。So each one of the MPs were going。こ辺？His question is for every single。

Big M pages in the outer table scan all the pages in the enter table， yes。😡，Yes， so it's not easy。

There is just。The statement is， and they're correct that it's not asymptically better。

 it's just in practice the constants are better， yes， I said this earlier。

 constants matter in database world。😡，So again， we want the smaller table to be always on the outer table。

 and we would determine whether which one's smaller than the other。

 not based on the number of two pools。😡，But rather based on the number of pages。

 because that's the main cost for us of going to disk， it' going fetching pages。

 not going fetching individual tus。😡，うく。And obviously in this scenario here。

 I'm assuming I have only two buffer pages， bufferable pages to store data in a real system you would have a lot more。

😡，So in this case here， you want to try to store in a block nest loop join where you have multiple pages you can use to store the data as you scan it。

 you want to put as many buffers on the outer table in memory as possible。😡。

And then this leave one page for the input for the inner table， ring page in。

 and then another page to write the output after you do the join。😡，Right。

So it basically looks like this now for every single for B minus two pages。

 b is the total number of bufferable pages I have， scan all the data I can from R and then go fetch each individual page from S and then just do that scan of the joint of the twos。

😡，And the two inner or four loops， yes。Could， and then its to also combine the certificate data。

The statement is I could admit also be honest to。Pages of data。

 but like I can only in this sort of simplistic example。I'm going to fill up one page。

 write that out。Then fill the next one up。Yeah。You knew asynchronous IO and therefore you need more keep it simple。

 yes。😡，All right， so if we go back now to our formula。

 assuming you have b minus two pages for scanning the outer table。😡。

Now our cost is going to be Big M， which again scanning the outer table at least once。

And then I can single for every M divided by b minus2 and take the ceiling of that。😡。

For all those sort of batches of pages on the outer table。

 I got to scan all the pages on the inner table。😡，And then plugging。

 chugging now with our simple formula we had before， assuming that we have。

 if everything can fit in memory， we can get this down now to the join of RNS from our simple exam of four down to 0。

15 seconds。So 150 milliseconds。So just by bashing things up and having taking advantage of the memory that's available to us in the buffer pool。

😡，We went from 1。1 hours to less than a second。hy is it。Why is it n plus n？So what's good？U。

Or because everything fits in memory。Then I read it all once， everything fits in memory。

 and then I join it。我你照。Why is it not the constant above because the ceiling M divided by b minus2。

 that's if like if I'm sort of have a batch where I'm reading things in and then for that batch of the outer table。

 scan the inner table。If I can fit if all the pages from the outer table and inner table fit memory。

 just scan it all， that's the M and the N， add it together and just do the join on that。😡。

So what I'm trying to point out here is even though the。Then the。

The nest loop joint seems kind of brain dead and stupid。If everything fits in memory。

 and maybe everything's already is in memory， this is actually pretty fast。Right。

And we'll see when we talk about hash joins。There may be the cases where you do。

Some of the join will be done with sort of using the hash building a hash table。

 but a small portion of it could be used using this sort M memoryory nestA loop join。😡。

Because you can rip through it pretty fast。So now if I only have b minus or b equals  one of2。

 then I'm get this down to。😡，6000 IOs。It's about 600 milliseconds。

 but then I I again switch the outer to the inner one， make sure the outer table is the smaller one。

 then I get it down to 5，500。Yes。If oil relations fit in there。的事情。They want sorry？

That the performance is not much。On the night version is just that。It's just whether you get to use。

Yeah， their statement isnt， they're correct that。If everything fits in memory。

 is it just the naiveness of loop join， yes？And if everything's to memory， that's fine。啊。And so。

When we talk about the hash joint， one of the purchase will be will be to one of the who's divide and conquer。

 well split things up in such a way that we can maybe try to keep everything in memory。

 and then the naiveness loop joint work the best。😡，If I have to go to disk， it's terrible。

 if everything's in memory， then I'm great。All right。

 so why is this so bad because we already said this again， if I had to go from disk。

 then I'm basically doing Scal scan over and over again on the inner table try to match things from the outer table。

😡，So we may say， all right， well sequential scans are not great。

 we spend much of time learn my indexes。😊，If I have an index。

 can I take advantage of that to make my that inner for loop on the inner table。

 make that go faster and answer yes， we can do this some systems like ZeL server we talked about before。

 well if you're doing a join or any kind of operational on a table and if the optimizer realizes。

 hey itd be really nice if I had an index for this for this table or run make my  query go faster。

 it'll build that index for you。Do whatever it is， the operation you want to do in your query and then immediately just throw it away and then also give you back warnings and say。

 hey， look， I keep building this index or this table for your queries。

 be really nice if you tell me I can have it no for good and keep it around。😡。

It human has to decide whether to do that or not。All right， so if you have an existing index。

 then you can modify the nestestlelib join algorithm to do what's called an index nestlelib join algorithm。

😡，Right and it basically is now the the the。The outer table you're still scanning through all the tuples。

 then for the inner table， I'm going to take a key that I extract from the outer table tuple and then do a probe into whatever the index it is that I have available to me and then see whether I have a match。

😡，And that's essentially doing the join for you。So the cost for this is harder to define because it's obviously going to depend on what your index is。

 like what data structure it actually is， and the size of it。So in general， though。

 we would say the cost now is going to be big M because can we wait to the scan all the pages in the outer table。

😡，And then for every single tuple in the inner table， sorry。

 every single tuple in the outer table will do some kind of probe into this index to again find a match。

😡，And again， we can't define this C easily because in this class here because it's going to depend on a bunch of different factors that can vary from one index to the next。

 whether it's B plus tree or skipless or try or hashable， right？😡。

But this is basically what the hash joint is going to do。So in this case here。

 assuming I have a P plus tree， I could probe a that and use that， make a nest loop join。

 index nest loop join。The hash join basically says I don't have an indexed。

 so let me be able to hash table now and then do the same kind of probe like this and then throw it away when Macque is done the same way that SQL server does。

😡，啊。All right， so the main takeaway is for theaib joinin。

If everything's a memory it's going be super fast and that's going to actually be preferable in many cases。

 but in general if we know I have to go Re disk， then I'm going want to make sure the smaller table is always going to be the outside to try to batch as much as I can on that adder table as I can in my buffer pool because thatll make things go up。

 make things run faster。O。So the the next one algorithm we're going to talk about is again certain mergege join。

 and this is going to be built upon the certain Mer sort or the sort stuff we talked about last class。

 and as I said before for1 to the 1970s， it was just back and forth between。

In the research literature about whether sorting algorithms are better than hashbased algorithms and then originally sorting was faster because the computers are really slow and hashing was really expensive and then hashing algorithms got better but then the hardware got better and sorting got better。

 the kidss going back and forth， then in general the hash joint is me preferable over the sortrMs join。

But you'd want to still want to have a sort merge join because if your query is the data is already sorted under your join key。

 or there's an order by clause where you need to sort the data。😡。

You can kill two birds while the stone by doing this algorithm and producing results that are sorted for you。

All right， so S Mos Join has two phases and again， the confusing thinking about this is that last time we talked about the external Mer joint algorithm。

And we're going to use that sort of merge sort in our we can use that sort of merge sort for our sort merge join algorithm。

 and we'd use that sort of merge sort as the sort phase in our joint algorithm。

 and then the merge phase in the join algorithm is different than the merge phase in the sort algorithm。

😡，Right。Im not trying to confusedfuse you， I'm trying to say like we can still use this sort of Mer sort。

 which has its own two phases。😡，In our Jordan algorithm， it's going to have its own other two phases。

Right。All right so the basic idea is that we have our two tables that we want to join。

 and we're going to sort them based on our join keys。😡，And then we're going to have。

 and that's what you do in this the first phase。Then the second phase you have these cursors。

 they' going to walk through your sorted tables and start comparing across to see whether you have a match。

 and if you do， then you emit them as part of the joint output and then you just keep moving the cursors forward marching through and producing results and the advantage because the data is being sorted。

😡，At least in the outer table， you know you won't the out table you wont have to backtrack up in the sort of results to look at tus over and over again in the inner table you may still have to do that。

 but again it's simple trick to keep track of these things。

 but the sorting allows us to identify that we know there isn't going to be any match at some prior point in the table once we reach a certain point with our cursor because the data sort we can't see magically a value that should appear up above down below us。

😡，In the back， yes。The question is， can I play an example we're at the back， yes。

 let me give you a demonstration yes。All right let me just skip this is the algorithm again。

 I don't like to show code in class， but basically there's two cursors。

 you scan through till you reach the end and then there's a lot to say you whether one increments versus the other and whether you need to backtrack let's go through an actual example。

😡，So here we have our two tables if we want to join the RNS。

And so the first phase of the Sermer join algorithm is to just sort them。

 so we want to join on the ID column， so in both these tables。

 we're just going to go ahead and sort them。Then now when we enter the second phase to do our merge。

 we're going to have these two cursors that arere going to start at the beginning of their two sort of tables and start comparing with each other on the join key tos see whether we have a match。

😡，And to handle backtracking， we're also going to keep track of this last value that says here's the last value I saw when as my cursor on the inner table moves down。

 so that way if we then see we then see a joint key on the outer table that could have matched something up above in our inner table we know how to go back go and start the skin on that again。

😡，so we start at the very beginning， both two cursors are pointing to the first tuple。

 the joint key is based on ID， so in this case here 100 equals 100。

 so this is a match and we just produce our output like that by just mashing the two tus。

 the attributes and the tus together。😡，Now， in this case here， because we have out a match。

 we're going to just move the inner tables cursor down by one。😡。

And we leave the outer tables cursor where it is。Then it now we do a comparison， 100 equals 100。

 we have another match， and we produce that as an output。

And then now we're going to move down forward again on the inner table。 But now at this point here。

 the value that we're looking at is different than the last value we just saw。

So we got a record that is the last value that we saw。😡，So we saw 100 before 200。

 so we keep track maybe have 100。All right， so now at this point here， 200 is greater than 100。

 so we know that we need to move down the outer tables cursor by one。😡。

Because at this point here there isn't going to be another value on the inner table that can match with 100 where the outer table is pointing at。

 so we move the outer tables cursor and not the inner tables cursor so that comes down here we gets 200 can 200 equals 20 so we have match。

 we produce our output again and then we now we move the inner table down for ch that the last value that we saw was 20 because now we're seeing 400。

😡，And again， 400 is now greater than on the inner table。

 if 400 is greater than 200 on the outer table， so we're going to then move down the outer tables cursor down by one。

Now we see 200 again。And we check our last value， we see that， oh。

 we just saw 200 before we got to 400， so now we know we need to backtrack and move the the inner tables cursor back up to where 200 was so that we can essentially restart this process of scanning the data inner table for the new tuple on the outer table。

😡，So then now again， we have another match on 200， we move the inner table down by one now we get 400。

😡，This scans down， we get 300， 300 is less than 400。

 so we know we want to move down the outer table cursor because there isn't something we can match here on the inner table because we're already at 400。

Because things are sorted， we know that we're not magical going to see a 300 later on because it would have appeared before we saw 400。

 which and we didn't see that。So we move the outer table down by one， now we have match on 400。

 that's good， inner table moves down by one， now we have 500， keep our last values is 400。

We're pointing at 500 though 500 is less than greater than 400 so the outer table moves down。

 now we have 500 again， that's a match。😡，And now the the。Intertableable's cursor reaches the bottom。

 we still got to keep track of the last value for ourselves。

RightEven though we reach the bottom because we don't know what we're going to see。

 we might have another match on the。On the outer table again， but now we get 600。

 600 is less than sorry 600 is greater than 500 so we know at this point we can short circuit it because there isn't anything that we'll ever see that will match between these two joins so we just scan through and just say we're done just just finish up。

Question， yes。So only be pre to keep this last value。And go back。

Because many multiple twos from the second table can。Yes。

 and this statement he made and he's correct is that the reason why have to his last values is because there may be multiple tuples on the inner table matching with a tuple on the outer table。

 yes， now you can be smart about and say， oh， if I'm doing a join on columns where they' unique column or primary key that I know that I won't have duplicates。

😡，On the inner table for any match on the outer table。

 so in that case here you don't need to do any backtracking at all， right。

 but in general you may not be able to know that， therefore you have to maintain this。😡。

the second care room like to，10。The questionWhat if there was 2100s， so going it back up here？

Oh like。Yeah， so in that case here， you would have to keep track of like。W， you had two 100。

 so you see first one 100 here。So you do this， you would scan through， you would match that。

 that's fine， and then now the inner table would come down。

 you would keep track of your last value as 100。The outer table moves down， it would see 00 sorry。

 it would see 100 again。😡，At this point， it says， oh， okay， well that was my last value。

 let me backtrack the inner table， I don't want the backtrack on the outer table ever。😡，For this。

I to go back。Std is and the correct like when it backtracks it backtracks to the first 100 where this was I'm not recording the pointer but like it would keep track of that and again if the worst case scenario。

 if I only have one value in this column when I'm joining then I'm backtracking in the very beginning。

 but again there's no algorithm going to make that work for great。😡，Yes。Condition ist like a simple。

以服。Right I was trying to avoid that so its saving it as and he's correct。

 well this is an a equality predicate like Ejoin， what if it's not that。

 then you have to have additional lo to keep track of like could I see something based on my joint predicate is something going be above a belobe it's more complicated。

 but yes， you'd have to do that。Could you like figure out something。えのおケつ。TheSt the question is。

 could you figure out something in all cases， what do you might figure it out wing？做分说。

Or all sorts of。The question is， could you figure out a way to do starts join for all joint candidates。

 yeah， no you can do it for all of them if I'm saying the logic of backtracking is this way more complicated。

 right？Other questions。That's a nice way to end it that's nice， yeah good。O。So。

So what is our cost for this， Well， again， we have two phases with the sort phase and the merge phase。

 the sort phase cost is whatever our sort algorithm is going to be。😡，For both the two tables。

 So again， if I'm doing like the sort merges join from the last class。

 then it's the 2M times everything else there because again， B minus-1 buffer pages。

 So I have whatever my cost is for sorting two the two input tables。

 and then now the merge cost without any backtracking iss just reading all the pages。

For both the inner table and the outer table once。Backtracking complicates things because then but you'd have to know the distribution of the keys and how many duplicates you're going to have per key。

 so we can't obviously put that in our formula here。😡。

And this they are one of the recurren them when we talk about query optimization。

 they make a bunch of assumptions of what your data looks like because it simplifies these formulas。

Because otherwise， how could you know？So if I go back to with real numbers， again。

 sorting these two tables here， assuming I have 100 buffer pool pages。

 then the C cost for table R is 4，00 IOs， the C cost for table S is 200Os。

But then the merge cost is just again scanning the pages that have sorted once。

 and that's down to 1500 IO so the total comp cost is now to 7，500 IOs。

So in the case of the everything's in memory， that was 150 milliseconds。

 now we're down to we're at 750 milliseconds。And then we can still spell the disc if necessary。

This sound to look pretty good？I've already mentioned this now。

 but the worst case scenario for us or pretty all the joint algorithms is that。😡。

They' like you have the two tables， they're tryingn to join on。

 they have one value for all the twoples。In that case。

 there's nothing you can do to make that work well， it's like the worst case scenario scenario。

 but in general， data doesn't usually look like that。You wouldn't have a billion tus when everyone。

 you know， everyone has a。The same birthday and you want to join these two tables。

It doesn't happen that often。Or at the scale where this would be a huge issue。So again。

 as I already said， Smer's join is going to be good for us when the data is already sorted on the join key that we want。

😡，Or the output of the query， the final output is there's an order by clause that's also on our join key。

😡，Because again， we can just do the sorting for either both the joint and the final output。

 and we don't have to do as a separate step。Right。Yes。Yes。

 question the statement is and theyre correct， the merge cost coming back here of M plus n is the best case scenario。

 yes with no backtracking。Alright， so there's number to the good one， the hash join。

So the basic idea is again we have a TL in R， we have a two S， we want to join them together。😡。

And the idea is that we're going to use the hashing mechanism。

 hash function as a way for us to find that the matching people from one side versus the other。😡。

And we can base it on this nice property， the hash functions is that。Given the same key。

 it'll produce the same output， same hash value， so if my join key is the same as your join key。

 we want to join together， then we'll end up hashing to the same location。😡。

In either a hash table or a partition， right？And in the same way。

 when we talk about hash tableables of like a way it took a hash。

 you're sort of randomly jumping into a linear array of slots。😡。

Where we may have to look around to find the data we want because you have to sort of scan through if we find the slot that has the data we want or an empty slot。

😡，The idea is the same is that with hashing， we'll land in a location where the data that we could have a match if it exists will be nearby。

 and therefore we're not having to do a complete linear scan of all the data or sequential scan of all the data as we did in NISTA for loops。

😡，So a basic hash join algorithm on a single node has two phases。

 first phase that we're going to take all the do a sequential scan on the outer table。

And then build a hash table using some hash function。

And then the second phase we're going to scan the inner table， use that same hash function。

 look up the hash table to see whether we have a match on our join key。

So we can use whatever our favorite hash table we want that we discussed earlier in the semester。

 in practice most systems are going to use linear probe hash table because they're so simple and so fast。

 even on a distributed system， it's going to work pretty well。And then inside the hash table。

 we'll have to at least include we have to include the join key because again。

 we may hash to some location that may have an entry in that slot。

 but because the hash functions are not guaranteed to have collisions。

 have still do comparison to the Jo key to say whether we match or not。😡。

So the basic joint algorithm looks like this， we have two four loops still。

 but they're not nested anymore， there's separate and executed and serial order。😡。

So the first I'm going to do is allocate some memory someone've got a hash table。

 scan through the outer table or what we call the built side of the join， use a hash function。

 populate the hash table， then do a sequential scan on the inner table。

 also called the probe side of the join， scan through probe inside the hash table。

 see whether we have a match or not。😡，Right。Pretty basic。It works really， really well。Because again。

 it's basically divide and conquer， I'm taking a otherwise would have been in the sequential scan and narrowing down the scope and amount of data I have to look at because I'll land my hash table and find the thing that I want and obviously I want to make sure my hash table is appropriately sized so that I'm not doing the worst case completely sequential scan of all the keys if my hash table is too full。

But in general， this is going to work really well， yes。Yes center or index。The question is。

 what is it between this and index S loop join， nothing？At a high level。

In excess loop joint has an existing index， I'm going to use that。

 this is I'm building the hash table just to do the join。😡。

Most indexes in real systems aren't going to be hash deals though。Most like if you call C index。

 by default， most systems， nearly all systems， you'll get like a tree， a B plus tree。

And so the BeaLtry is great， probably not is probably it is the most important data structure in the world。

 but it's not going to be the best thing for joins。😡，We're doing a lot of joins。

Because if my hash table is large enough and I don't have a lot of collisions。

Then I'm doing01 lookups。And for a billion two bowls， that's a big deal。

 that's going to be a huge difference to performance。First， the log n Terrsal in a B Street。

So one easy optimization we can do to make our hashtrains go faster is。

They actually built a balloon filter。As we're populating the hash table。

And then now when I want to do my probe， I check the bloomlo filterer first。If there's a match。

Then I then probe the hash table， otherwise， I don't probe the hash table。

RightSo this is sometimes called sideways information passing。

 some systems will call these bloom joins， the basic idea is all the same even though it has different names。

 so say that now I'm going to build my hashable on R this will be the build side so as I'm scanning through R I'm populating the hashable。

 but then I'm also going to be building a B filter。

And then now once the hash table is done and now want to start scanning S to do the probe into the hash table。

 I'm basically going to pass along the balloon filter over to this guy and say， hey。

 before you check the hash table， go check the balloon filter。

Because the idea is that I stuff the hash anyway to probe into the hash table。

But then landing has and then doing the scan and doing the key comparisons。

 that can be rather expensive。We're just doing the boser look up， that's way faster。

So this is great when my。My predicate， my joint keys are very selective。

 meaning most of the tu thats I'm examining aren't going to match on the join。

 and I'm throwing most of them away， then this is going be a huge win for us because doing a look on the balloon filter is super cheap relative to the hash table。

😡，So this is a weird thing for like kind of violates the notion of like in our query plan where we're sending data up from one up to the next。

 because we're taking information that we collect on R and having this side channel thing we pass over to S。

😡，But again， the win is。I going to be quite significant like in some and really sector joins。

 this can to be like a 2 x performance improvement， but just building the bloom filter。All right。

So the exam I showed before for the simple half she has joined was kind of like the naive nestestle loop joint where like you assume everything's in memory and kind of rip through it。

But if everything's not memory， then we need to be able to still be able to handle that。

And we don't want to maybe build a giant hash table。

For our to do our join because the hash table is not going to fit in memory。

 and now we're doing random IO to different locations or different slots in that hash table。

 and that's going to be terrible for us for performance。😡，So we're going to rely on and again。

 that same divide and conquer approach， where we're going to split the data set we want to join up into smaller subsets and potentially build hash tables for those smaller subsets that do fit memory and then rip through that very efficiently。

So this idea goes back to the 1980s， I think the textbook calls the partition hash joins。

 the sometimes you'll see in the literature they're called grace hash joins。

And this is named after a seminal work in the 1980s out of Japan building this database machine called Grace。

 and they had a paper sayingHeylo， we have this great database machine called Grace。

 and here's the hash showing we're using， and so the grace database machine obviously no longer exists but the legacy is this hash join that pretty much everybody uses today。

So like the other algorithm we' talking about it's kind of have two phases。

 we have the partition phase， we're going to go through both tables， hash the join keys。

 and then divide it up into partitions and the buckets。

 and then in the second phase for each partition level we're going to again scan through the data and just do the simple hash join that resides in memory that we saw before。

😡，Who here has heard of the term database machine before， probably nobody。

It's basically specialized hardware that people built for specifically to run database systems。😡。

This is why data systems is the most important piece of software， think of like other thing。

 you know。Crypto stuff he was doing like other than people building specialized hardware for crypto or maybe like you know graphics and things like that or machine learning people have been building specialized hardware for databases for a long time。

So this one of the earliest ones from one of the early days called IDM。

 I just like this picture because the guys like in a suit working in a database。

 this is what the future was going to look like， but they were building pressize Harvard to do sorting。

In network。as well and this again， this from 1980s that companys obviously no longer there。

 but there's a bunch of companies around today that' will sell you。Daatabase appliances。

 instead of calling data called appliances， that again customized hardware or tuned hardware to run database workloads。

Most famous of these is probably going to be Oracle exadata and then the Teradata stuff right they're thinking of like massive data warehouses。

 each one of these racks is like $5 million and then maybe double that now。

 but then you pay a million dollars a year for support for this。

 like this is what you would run at like for high end workloads。And inside there some like。

 Oracle controls all the hardware and the OS， they'll have like I think。😡。

FPGs and things like that inside this make run faster， right？

One of the companies that I' be giving to talk with us in a few weeks it' called Ylow brickrick。

 they start off selling a database appliance against thinking like specialized hardware customized for running a database workload。

嗯。And they still make a lot of money doing this， right？

And it said like just goes to show people are trying to do specialized hardware for data for a long time now the current trend to see how we can leverage GPUs。

 there's a bunch of companies that' have been doing this for。about 10 years now。

 we had a seminar series in 2018 where a bunch of the GPU Davis vendors came and gave a talk。

I have obviously they're competing against getting GPUs from the MLAI people。

 but there's a lot of like， you know。One generation order GPUs that people don't want to use for training anymore over ML stuff that you can still use in databases and run efficiently。

We're not going to talk about GP Daviss in this class， that'll be in the advanced class。

Let's just say that it's people been trying to do this for a while。

 but it doesn't always pan out part ofly the when the data business sheets in the 1980s didn't really pan out either because。

In the early days of computing， like by the time it took you to design specialized hardware fbit and then ship it to customers。

 you know Intel or Motorola or whoever was putting out new CPUs that were pretty significant jumps of performance because of Moore's law and the performance benefit you get from specialized hardware just was negated pretty quickly nowadays unless you can get on Amazon or in the cloud。

 people don't really care about running specialized hardware because it just。😡。

You want everything to be sort of come out of that。Anyway。

It great has join was an early database machine and there's a lot of work done in this space it's the whole degree of our databases like I have specialized Harvard to run my database system and run faster that would be fantastic no one really has seemed to sort of crack that nut yeah。

Okay， so the way partition hashing is going to work is sort of like that partitioning phase we saw went our aggregations last class。

😊，So I'm going to scan through all the table my outer table， use a hash function。

 put everything into buckets， scan everything on the inner table， same thing。

 put it everything in buckets， and then now I'm going to be able to spill these out the disk if my buckets get too big。

😡，But then now when I want to do the sort of the second phase of do the join。😡。

I only need to examine the data within one bucket and do that comparison across the two tables within one level at a partition。

 because I know that there isn't going to be a key that got hash into partition zero at the top for R that's going to get hash into this bottom bucket down here because the hash function doesn't work that way because the same hash function the same value。

 they'll end up in the same level。😡，So then now when I want to do my probe to do the join。

 I'm going to do one level at a time， bring those pages into memory， build a hashable for that。😡。

Then at the same level， read all those buckets from the outer table S。

 and then do hashing to this hash table， just again now everything's in memory， find my match。

 produce my output， and then once I'm done probing on the S side I throw the hash table away because I don't need it anymore because there's never going to be another match at any other level and I just do the same thing all over again。

😡，Yes。😊，お。I guess like， are they。Like， how do you choose the。Likeブれはい。可是。So the question is。

 how do I choose the number of bookss I have and how do I are they just pages They're just pages I'm just app to them right And then the size is determined by the database system either through a parameter that you can control as a human like the operator of the administrator so you can tell like Postgres like you're allowed to use one megabyte of memory to do hash joints or something like that right so someone someone is telling you how many pages you get to do this right and the。

And then if the s decides that's not going to be enough， you recursive partitioning。

 we'll see that next。😡，Me is finite， so I just can't say I'm going to use to all my memory。

 something above is it' determining how much resources you have。Yes。Why does this produce like。

いといかです。Ro one。All and Oliver。The question is， how is this producing a correct join， non collegent。

 correct join？Because your statement is because you could have rows that in one level partition。

Youre saying matchch to another level？That can never happen。

Because if the join key on table R and table S， if it's the same values， when I hash them。

 same input to the same hash function because it's deterministic will produce the same output。

I mo that by the number or whatever K here， how many levels like my partitions I have。

 they're going to end up the same level always。😡，If they don't。

 then something's wrong with hardware and that you know， but David has can't handle that， right？

But like I don't it's like it's like the sort merge software where like because I've sorted the data I can't I know I can't see something that I should have seen earlier down below because it's been sorted if my sort algorithm is wrong then I have a bunch of other problems right so if my hash function is acting all weird and that's that's。

😡，You're in trouble。In general， the algorithm will work。Yes。请问也是。

When US time like the same number budget。You ready we have some other。

So you're asking what if I have， I think basically， what if all the。

What if these buckets get too full， yes， next slide。Okay。So if the partitions don't fit in memory。

 which they were asking about， then I just recursively partitions again。And I keep and again。

 if everything thing still doesn't fit in all memory， partition again， now again。

 in the degenerative case， if all the values are the same across all my keys or all my tus。

 Denvercur partition doesn't do anything for us。Again。Don't do that but the end of the day。

 there's nothing you can do。 There's no algorithm magic to make that go away。

So eventually I' was going to keep sub partitioning my partitions until they fit in memory。😡。

And then then do my join。In practice， you only had to do one extra level of recursive partitioning in real systems。

Again， it's the gender case， there's nothing you can do。But then if you identify that the。

That you're going have a lot of keys that that are going to be values of the keys are going to be the same。

 then you just fall back to do the block blockness of loop join Or if my partitions are actually going to be small enough。

 I don't maybe want to build the hash table we'll see in a second I'll just do the。😡。

I'll just do the in memorymory N loop join because that's me really fast to do as well。

So let's say we this is the table we want to partition。

We have a bunch of buckets k minus-1 and then say for whatever reason a bunch of the keys are going to are hashing into the bucket in level one so I'm think of this like just every single time the page gets full I read out of the disk I make another page so I'm keeping track of the metadata of how many pages I have at each level。

😡，So there's some threshold to say， okay， this thing is getting too full， everything is too skewed。

 so then now I'm going to do another hash around a hashing。

 pick another hash function or take another seed for the hash function I'm using。😡。

And just partition the data at that level all over again into a bunch of more pages。😡。

Or much more buckets。And then for the ones that didn't that weren't too full。

 I just carry them along at the next phase because I don't need to rep partition them。

 I don't care about them。So then now as I do my scan， the same scan on the outer table。Sorry。

 the entertainment。If they hash to the two bottom ones， that's fine。

 I don't think anything special there and then now I just do my memory hash join as I did before。

 but if I recognize that if I'm hashing to one of these ones that got overflowed。

 then I know that I need to call the second hash function to hash them again and then now they'll land up and aligned with the keys coming from the outer table。

😡，So。Just like the index probe cost in the index sense loop joint is hard to quantify。

 recursive partitioning is also hard to quantify because it depends on the key distribution。😡。

So in general， we're just going to say to estimate the cost of a hash joins is going to be this formula ofly here。

 so three times m plus n。Right because it's。One scan in for M plus N， write it out。

 and then one scan back in to take the partitioned buckets and then do the hash join and everything's in memory at that point。

So using real numbers， now we can get our example table before down to 450 milliseconds。

So Smer's join was 70 milliseconds in memory Nea loop join was 150 milliseconds。

But if I had to spill a disk in this case here， I can get it down to 4 to50， so that's pretty good。

So one。Semi- easyy， but not always easy to implement difficult to get right optimization is used what is called a hybrid hash join。

 and this was something that was invented early 1980s as an extension to the Grace hash join stuff。

 and this was invented by the other data professor Jeanx Patels。

 his PC advisor invented this I think with Jim Gray， one of the Turing Award winners in databases。

 back in the Dam。And so basically what happens is if you recognize that a bunch of the data。

 if your data is skewed and a bunch of the。😡，A bunch of the two bowl are all going to the same partition。

You'll just keep that partition in memory， spill all the other ones out the disk。

 and then just do an Emory hash join or Emory nest loop join for that hot partition。

 and then just do the regular grace hash join algorithm for the other partitions。😡，All so again。

 soon we have， for whatever reason， all the keys are hashing this one here。Right。

So I would recognize， okay， this thing's to be hot。

 so I don't want to maybe spt the disc if it's not that big and I can keep it in memory。

Let me go ahead and just do that。 So I how to keep this level in memory， take all the other ones。

 Sp those out the disk。And then I just take now， while this is already in memory。

 build the hash table for this， maybe not even do the bucketing phase that switch it directly to the hash table。

😡，And then now populate it as I'm scanning along， and then this guy can then do the joint directly against it。

Right。I think it's called hybrid because again， instead of doing the hash table part at the top level here。

 you could just do the nestestA loop joint because it's already in memory so you're kind of doing both algorithms together。

😡，This is a challenge to get right because like。Again。

 how do you know whether something's going to be the hot partition or not。

 are you just better off using the extra memory to keep these things keep more of these pages in memory rather than going to this hash table thing？

So Postgret says this， a bunch of different commercial systems do this。

The language is confusing because sometimes they'll call this the hybrid join。

 sort of the hybrid hash join， so finding out who actually does this is not always clear。

And like I said， sometimes just better using the pages for。Uh。

 for the partitions you're building rather than， you know specializing in one of them to be the hot one。

All right， so finish up so for our hash joints， the probe table can be sort of really any size。

 but in general we want it to fit in memory because again we don't want it to do much of random IO on disk that's going to be the death to us right？

If everything fits a memory， then。The probe can be really fast。

 you' just sort of scanning through once and don't do any partitioning。

If you don't know what the size of the table could be。

 then you maybe want to use the extendable hashing or the linear hash table that we talked about a couple classes ago。

😡，Most systems don't do that because again， those data structures are less efficient because there's more machinery to them than like a linear probe hash table。

 so when we talk about query optimization， as I said a couple times already that like they're going to try to estimate how much data or how many tubs you're going to have to put into your hash table so that you can sort of size it correctly and not the spill or resize it later on。

 but getting that correct is super hard to do。😡，It's hard not to do it for base tables themselves。

 like I'm reading the tables， but then try to do estimates of the size of data after I do multiple joins。

😡，Everyone gets that wrong and Har's wrong。You know， it's。The only way to handle is is to be very。呃。

You over allocate the memory for your hash table to avoid that problem。Of course。

 that makes you less efficient because now you're using memory that you're allocating memory you may actually need for your hash joint could it be used for other things。

 but again， you're just trying to avoid having to spilled the disc。All right。

 so here's the summary slide of the。OfThe different algorithms we talked about again， in general。

 the hash join is going to be preferable。If you don't already have an index and you don't think the data you're trying to join。

 it will fit in disk。Yes。You make comments on。So then we have Xr。呃。Yes。Yes。That database system。えぱり。

By。So the question is， I mentioned different。I mentioned a bunch of different scenarios where one Jordan algorithm will be better than another。

And so the first question is do database systems implement different joint algorithms， yes。

 do database systems then try to figure out which of these joint algorithms they should use at runtime when your query shows up。

 yes。That'll be query optimization， that'll be after the fall break。

 roughly the formulas they're going to use to try to figure this out looks like this。😡，Right， now。

Onere the common ones that are there。And they tried to。これが。なるんです。So。哎。

The question is of this menu here， which ones they are going to have， the goodins have all of them。😡。

Posgres has all these， right， OracA has all of these。Db2， duck Db， you have to have all。

My SQL didn't have hassh joins until like oh 30 25 years later like they didn't it until 2019 and I don't think they have I don't have servers join still right but that's okay because they're focusing on like not analytical workloads it's an OTP system。

😡，Right right。So。I was just trying to say like the the the。If you're better at data from scratch。

 when you have to implement your join， the first thing going to implement is basically you blocking that loop join because it's the easiest thing to do。

😡，And then after that， you're probably going to implement。😡。

The hash drawing because it's going to be way more efficient。

And there's a bunch of different observationss and tweaks you can do for all these。

 like there's a bunch of variations of these things。You can have different hash tables。

 based on the data you're going to join together， the Clickhouse has 20 hash table implementations。

 like theres within these general categories algorithms。

 there's a bunch of different optimizations you can do。😡。

And that's what that's going to be what distinguishes the enterprise expensive systems from from like you know the open source ones now with that said DDB and Postcards have a lot of these things thatre pretty good DDB is probably pretty state of the art right。

But the challenge is always going to be in the query optimizer to figure out which of these one of these ones you should use。

😡，And in practice， again， said the estimations are always made really bad。

 so the hash joint is usually。The fallback。Yes。Does see again。

The question is what's the C index in electron， that's the constant cost of probing the index。

Unfined because it depends on what the index is and what the data looks like right it also depends on what the join is if it's echojoin you know in the case of B plus street it's all going to go to the bottom。

 but if it's like they were asking well actually if the key is not unique in that index I may traverse the bottom and then scan along the leaf nodes。

 how many you have to scan depends on what the data is and what the query is so that we just say C。

But when we talk about query optimization， it don't know at that point。

 you'll know what the query is， you know what you want to do。

 you know what the data roughly looks like， you know what data structure you're hitting up so that query optimization time when you take a SQL query and convert to the actual plan you execute。

 that's when you fill in C。😡，All right， again， so the main takeaway from right here it should be hashing is almost always be preferable to sorting unless the data needs to be sorted as part of the output。

 then you just piggyback off that。Even then in some cases sorting you know doing the hash join then sorting it still might be even better again it depends on the hardware depends on the query。

 depends on the data so and related to his question， the good systems， good in quotes。

 will have pretty much all of these techniques and a bunch of other optimizations。

 but these are the general three algorithms you can do you can either have nest to four loops。

 hash things or sort of things， there isn't anything else。Okay。All right， what's next class？Yeah。

 that turn， okay。So again， make sure have your notes。

 your CMU ID don't do any weird things like one year one kid brought his wet laundry don't do that like I won't be here。

 but my Patche students will be will be。Maning for us， okay？



![](img/72d181f60751ca048bba849f015275d4_2.png)

Hmen， hit it。🎼what我 that chance。😊。

![](img/72d181f60751ca048bba849f015275d4_4.png)

🎼说你会最帅走不见。

![](img/72d181f60751ca048bba849f015275d4_6.png)

🎼Thank。🎼what。🎼我再从不见。🎼Yeah。🎼我你最最帅走不见。😊，Get the maintain my the。



![](img/72d181f60751ca048bba849f015275d4_8.png)