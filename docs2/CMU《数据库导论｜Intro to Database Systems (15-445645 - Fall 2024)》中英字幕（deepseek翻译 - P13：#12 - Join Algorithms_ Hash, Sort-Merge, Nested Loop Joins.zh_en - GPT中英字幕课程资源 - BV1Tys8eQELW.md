# CMU《数据库导论｜Intro to Database Systems (15-445645 - Fall 2024)》中英字幕（deepseek翻译 - P13：#12 - Join Algorithms_ Hash, Sort-Merge, Nested Loop Joins.zh_en - GPT中英字幕课程资源 - BV1Tys8eQELW

![](img/de84ad68707ab4cdae3ad8fafdff06b9_0.png)

Yeah。🎼Okay it's all right let's get started， we have a lot cover today。

So again administrative itself midterm exams from no surprise for anyone is this Wednesday two days from now in this room at the same time。

 I think everyone who needs accommodation to email me if you haven't yet， please do that。

 and then the study guide is available online along where the practice exam Project two will be due after the fall break on Sunday。

 October 27， but we'll be holding a recitation this Thursday at 8 PMm on Zoom will announce that on Piazza and then that will be recorded and will make that available on Piazza afterwards as well。

Okay。Who here has started Project two？Okay。A little bit okay， again。

 I really there's other exams there's other beyond this class。

 but you should really get started on Project two that way because because it's not really easy and you showed the recitation as harder questions。

 okay？はい。Beyond this， again， we have some Daviscos coming up today at 430 on Zoom。 we have parade Db。

 They basically took Postgres stuck data fusion inside of it first， got rid of that。

 now they put duck Db inside of Postgres。 And then they have this thing called Ttvi。

 which is sort of like Lucine。 when we talked about full text search indexes。

 They put all that inside of Postgres。 So that guy's giving talk today。

 And then when we come back from fall break。 there's another startup called spice AI。

 and they put data fusion。 they're using data fusion to do LM stuff。

 I think And so the beginning of a talk and then。😊，I'm assuming you pronounce this as Exxon。

 They're giving a talk about their tool using datafusion in the end of this month。

 If I had to up for one database startup to get sued for trademark infringement。 Itd be these guys。

 right。😊，I don't think I don't if Exxon Mobi is as litious did， but。You're asking for it。 So。

 all right， that's not our problem。 That problem。 Okay， any questions about the midterm。

 Any questions about Project 2。Allright， so let'sャベです。I mean， I say this every class like， oh。

 this would be great lecture， but this would be great lecture because it joins。 it's super。

 super important。 So last class again， we started talking about how we were going implement algorithms that our database system to start running queries to start processing data do essentially the relational operators that we we want to support to produce results for when people send us queries。

😊，And one of the key things that we talked about， which is again the theme of this semester is how to support data sets。

 either inte results or the base tables themselves as we're scanning them that are larger than the available memory that we have in our database system。

😡，And one of the techniques that we used last class and we'll see this over and over again throughout the Ti semester is this approach or this pattern called divideivide and conquer。

 like breaking up a hard problem to smaller problems。

 meaning breaking up something that doesn't fit in memory into smaller chunks that do fit in memory。

 and then divide that up and then slowly merge back together to produce the final result。

And we'll see the same strategy used today when we start talking about doing hash joins。

 if the data set doesn't fit memory， how do we handle that？😊。

And then the other key thing that we discussed last class is that we started off talking about external merge sort as a sorting in the data system and we showed how we can use sorting to compute aggregations。

 but then we also started talking about how to use hashing to compute aggregations as well So we're going to see the exact same thing today we're gonna see different approaches to do joins would one will be based basic for loops。

 one be based on sorting and that will be based on hashing。😊，Right。

 and these are basically the two main choices you have When you're designing a。

 you know data intensive algorithm， am I going to do something through sorting。

 am I gonna do something through hashing。And as we go along。

 we'll see the pros and cons of each of these。 But in general。

 the Sp for this lecture is going to be hash joins are almost always going to be the better choice。

 the faster choice。But we we'll go through this and understand why。All right。

 so should be sort of obvious at this point in the class， certainly if you did homework1。

 why do we need to join？😡，Well， in the context of our relational database system。

 there's this technique called normalization， which we didn't discuss because I'm trying to。

As it says， I don't think you need to know about normalization other than the know that it exists。

 a prior version of this course attribute to teach in normal forms。

 basically how do you take a table is's filled up to smaller components like foreign keys。😡。

I think of like the first normal form is like I put everything in a giant table and then I can split it up and and break it up to to car surface tables。

 dimension tables that we talked about before。 That's called normalization。

 And there's a whole theories background on it that you don't need to know because nobody uses that in the real world。

 So I'm saving you from that。But since we know our， our database we broke up into smaller relation。

 smaller tables， we obviously want to join it back together。 Oh。

 go get Andy's account and get all his orders。 Well， that's a join between the order。

 order table and the account table， over some over some key。😊。

So this join operator is going to be the mechanism is going to be the way that we can reconstruct the sort of full tuple or his original tuple for the full entity that we're trying to expose in our application。

 the join is how we're going to be able to stick these things back together。

 and we want to do this in such a way that we don't have information ball。😡。

Meaning if I I want to join Andy's account with Andy's orders。

 I don't want to miss some of Andy's orders， right， I want to have the exact answer。So that。

 that's the goal for today。The type of algorithm we're going to focus on in particular is going to be called a inner echojo。

So inner joinin just means I have two tables。 and I'm doing an exact match on them。

 And the echo joinin means I'm the join predicate is just going to be a quality。

RightYou can do less than greater than there's things called anti joins where something is not in something right。

 at a high level， some of those algorithms will be the same。 But for for simplicity。

 we just focus on inner echo joins。 And I'll talk briefly how we can extend that to like left outer join。

Those joins in the real world are going to be inner echo joinins most of the time。

 like when you write queries and re applicationsplication， it's gonna to be innerjos， In echo joins。

 Left outer joins is probably the second most popular one。 And antigerodes and semijos。

 These are like special case things we'll cover later。

So the other thing I understand is that we're going to focus in this class on binary joins。😡。

Meaning we're only going join two tables at a time。 Now。

 the query may reference multiple tables three or more。

 but the algorithm we're going to talk about can only take two tables and then join them together。

 And if you want to join another table and you take the output of the first join and you run the same join or the same binary join algorithm on the output with another table。

😡，There are techniques called multiway joins。😡，These have existed in the literature for a long time because it seems kind of ugly。

 So I want to join three tables。 why to join them all at the same time。 but in practice。

 nobody implements them because。The performance can be， can be variable。

 like Microsoft added this in SQL server， I think like991998。

 they took it out in 2001 because depending on the queries， depending on the workload。

 the performance could be all all over the map。So again。

 most systems that you can think about that you know of are going to be doing binary joints that we'll talk about today。

😡，There's another more modern category of joint algorithms called worstors case optimalable join algorithms。

 This is， these are used where you're doing a graph traversals， like think of like a network。

 representing a graph structure， like a like a social network。😊，These are rare。

 there's only a few systems that I know about Ubra， Cedar DB， out of Germany。

And then that relation AI people that came talked about before。

 they have a worst case optimal doing algorithm。 these are special case algorithms。

 I suspect they're going to become more common in the future。

 and we do teach these in the advanced class。 But for this class， we we don't need to know that。😊。

Another big thing that we're gonna that well sort of lightly touch on today。

But we'll talk more about this after the fall break。Is deciding what？In what order we should join？

And actually， what joint algorithm we should use。😡。

And this is what the query optimize is going to do for us and we'll cover that again after the fall break。

 But the idea is that I say my SQL statement， I want to join these two tables。

 I'm not saying what I want to join A first with B or B with A。

 and I'm not saying what joint algorithm I should use So join versus hashing or whatever。😡。

So all that's gonna to be abstracted away。 the cost model and the optimize will take care of that for us。

 But in general， as we see， as we talk of these algorithms。

 the rule of thumb is gonna be we want the， the， the left table。 we'll call the outer table。

 And I'll explain that is in a second。 That should always be the。The smaller one。

And we're gonna do this for performance reasons。 And again， when we show the algorithms。

 you'll see this。So we saw this last class， again， what is a query plan。

 it always usually represented as a tree。😡，It's usually usually implemented as a tree。

 Some systems can do it as a dag。 tree is obviously a special case of a dag。

 You want to use a dag if you can， but most systems don't。Again。

 the idea is that the data is going to flow from the bottom to the top。

 going from one operator to the next。😡，And then the output of the queries mean whatever the root node spits out for this。

So in this example here we see we have the join and R andS， we're getting data from R up into this。

 and the s goes through a filter first， and then it goes into the join and we join that。😡，Again。

 this is a logical representation of the plan。 I'm not specifying what this Jordan algorithm actually is。

 I'm just saying there is a joy。😡，And at this level two。

 you're not even specifying what is the inner table versus the outer table？😡。

We'll see that in a second。So there's two decisions we've got to make。😡。

One is what should be the output of our joint operator？😡。

And we talked about before like late materialization， early materialization。

 we I'll show an examples of this one in more detail。

And then the next thing we've got to worry about is how are we going determine whether one join algorithm is better than another。

😡，Well I just said that， oh， you typically want the smaller table to be the outer table。

I think on the left side of the tree， usually has represented。

 but the how do I know if I'm joining three tables， which two tables should I join in firsts。

 and then the third。So we need a cost model we need a way to understand which one is be better for us。

So in case of the first decision， it's that again， late imitization versus early materialization。

 So no matter what joint algorithm we pick， like what physical implementation of the joint operator we pick。

 the output is always going to be the same。Meaning joining RN S in this example here。

 it doesn't matter what I'm doing a hash join versus a Somers join。 the logical output is the same。

 meaning that the tuples， the unordered tus will be the same。 Now。

 then maybe physical properties that I'll care about later that will be different。

 Like Smers join will come， the data will come out sorted。

Because you have to sort it in order to do the joint， whereas hash we random。For that。

 we we can ignore we can ignore for now， but there's other design station we'll cover F midterm as well as like。

 are we sending out one tuple at a time， every tell me we invoked the joint algorithm or is it a batch of tus or all the tuples。

 where if we have to spill a disk， where does that go。Right， so the output。

 we could be logically be the same， but physically。

 it might be different depending what algorithm we're using。 But again， for this class today。

 we don't have to worry about this。So this is just a rehashing what we talked about for。

 the difference between early materialization and late materialization。 Remember。

 early materialization， the idea is that I'm going to construct the entire contents of the tuple at the moment I've retrieved it from whatever the source of data that I'm getting it from like a table or a file or some network storage。

 right。😊，So if I take this query here， I'm joining R with with S。 right。

 I'm going to produce the the logical output which should look like this， right。

 Here's R and all its attributes， Here's S and all its attributes。😊。

And then now when I compute this join in the query。Right， this whole thing is going to get from。

 you know， from this operator computes this。 and then that gets fed up into the operator above it。

 which is a projection， which is going to throw away the stuff that it doesn't need。Right。

And in this example here， because I got the entire context of the tuple at the bottom， do the joint。

 and then that join， basically mashing the two things together。 And that's going up the query plan。

 the the upper operators in in the query plan never have to go back and get more data。

Things are just passed along from one operator to the next。So in light materialization。

 the idea is that at the moment you retrieve the data from the underlying data source。

 you get the bare minimum you need at that moment for that given operator。😡。

So you can be a bit clever here and say， okay， well， I know I'm going to do a join later on。

 so I don't need to bring in these other attributes like name and then value and and date。

 I'm just going to bring in the ID and then I store the record ID that corresponds to where this tuple came from。

 And then that's what gets passed up from this join operator here。Right， so again。

 if I think I have 1000 columns or even something larger than that。

 then I'm I'm not passing around those thousand columns for the two tables as I go up。

 I'm just passing again the the bare minimum。So then when I get to this projection operator here。

 it then has to say， okay， well， I know I have these two tus coming into me and I need to go get the date field from the S table。

 so I'm going to use the S table's record ID to then go fetch whatever the pages are that has that date and then fill it in。

 yes。😡，So like projection， why don't we。Yeah， so question is why don't you propagate what fields you want at the bottom。

 And then when you do the join and pass them along， that's called projection pushdown， Yes。

 we'll get to that later。 Yes， but that is a classic that's the optimization you would do for this。

But again， it actually depends on like。Yeah， so what he's proposing is that going back here。😡。

RightI know I'm going to need the customer date， so at the moment I do the join instead of just throwing away the customer date。

 go stick it in this part of the tuple and then do the join and pass it up。

 So again depending on how your query plan is implemented， do I have the tree here， right。😡。

This could be over the network， And then to do the scan。

 and then you do the filter on another machine。 So maybe I don't want to pass over the network。

 the customer date because it it's gonna get filtered later on。

 So maybe I want to do another retrieval here before I do the join。

 But then I' as want to do it afterwards。 Like there's all the different 9 stitch you can make we're not there yet。

 but it's not as trivial as like， oh， I know I'm gonna to。 let me pass along because again。

 I may be passing a billion twoples and filter down to just a two。

 And I'm passing along customer date。 And it was a waste。

Like this stuff is like like figuring what you， the bearing you need to do the minimum of work is like super hard because be honest。

 your statistics are going to always be wrong。 So you're making guesses on bad data， which is hard。

Or obviously prone to air。Okay， so this is common in column stories because。

If your comms the different attributes are stored in separate files。

 why I go fetch those files is just stitch things together， only go get them as you need it。

AllAnd then the other design we talked about is how we actually determine whether one algorithm is better than another。

😡，And so say again， we're going to use this query as our running example throughout the entire lecture。

 is joining R and S on a simple ID lookup， RID equals SID。😊。

I'm not saying whether I think we actually RID is the primary key。

 and I forget whether I don't think SID is， but for our discussion today it doesn't matter。But the。

 the variables is going to use to understand the cost of doing these joints are going to be this M N and our big M and little M。

 Big M in little N。 So we have go with this M。And there would be M low case， two plus an R。

Pages and N pages in S。So that for this class and this lecture， actually。

 for the rest of the semester， the cost metric we're going to use to determine whether one joint operator is better than another is just going to be the number IOs we have to use to compute the joint。

Right。So we're going to ignore what's the cost of actually me writing out the result and get the spelled to disk。

😡，RightBecause be honest， that's gonna be the same for all our joint algorithms。 as I said。

 the logical output is gonna be the same。 They're always gonna produce the the。

 the same X number of tuples as their output。 So it doesn't matter what you're doing one algorithm as another。

 I got to spill out the disk If I have so many tus and run run a memory。😊。

We're also going to ignore the computation and network costs for now。

 obviously doing the nested loop joint。 we'll in the second is the easiest thing to do and it has a low CPU cost because you're just just doing the loop for what your four loops whereas a hashstone you got a hash something thing and find a location and depending what hashing scheme you're using。

 you got to scan through that's be way more computation expensive but。😡。

We're just going to assume that the cost of going to disk is so much more than any computation we have to do。

Especially how hashit was going to be very well optimized we can ignore that。

The network costs were also avoid as well because again， at this point semester。

 we're still assuming our data system is running on a single box。

We'll talk about distributed queries later on， but you could do a join across multiple machines and now you got to figure out where the data is。

 where do you got to move it to， and that certainly needs to be expensive。But again， today。

 we' ignore that。 So it really comes down to how much IO do I have to do。

And then to simplify also discussion， we're going to assume that nothing is already in memory。

Becauseuse again， you can't account for that in your calculations like because depending on what other queries running at the same time。

 how much memory you have and， so much other factors， you can't， know。

 that's a moving target It's hard to calculate。So for our purposes here。

 we'll just assume that everything's on disk and what's the cost of bringing things in。

 and then we have to spill the disk writing back out。Okay。All right。

 so here's the menu we're going discuss today。 So we're going to first talk about the nest loop join。

 which is the most simplest thing you can do。 Then we'll see how we can do sorting to do sort merge join。

 but then we'll spend most more our time at the end talking about different variations of doing hash joins。

😊，Because again， these will be the most important， most important thing to do。

If your assessment is trying to support transactional workloads or O TTP workloads。

 as we talked about before， you typically implement index asset loop join， the one at the top。

Becauseuse it's like again， go and get Andy's account record。

 that's me one tuple and Andy's orders maybe 10 tuples and you'll have an index for those。

 fasts going be super fast， hash only is going to be too slow for this。

But if you're doing analytics of the OVt workloads。

 like deriving new information from the data you already have， youre going to want all of these。

And then the high end systems will for all of them， Postcards can do all three types of joins。

 hash joins， shortmer joins and instead joins， I think My SQL added hash joins about five years ago for a while they couldn't do that I don't think they can do shortmers joins。

I certainly like snowflake， databs and。But actually shift in all those the big OLAP cloud systems。

 they can do all these things， I think DDb can do all three as well。Okay。

 so let's start the beginning。s the most simple thing to do naiveness Lib join。

 We'll see why it's stupid。 And then we'll build from that。So again。

 this is the query we're going to target， joining RNS。😡，So the naiveness loop join。

Is just two forlips。 hence the name nested loop。And all you're really doing is just looping through all the tuples in table R。

 and then for everything single one tu in table R， loop through all the tuples in table S。

 if they match on our join key， like RID equals SID， then we're going to emit them as at our output。

And I have this admit function to say this thing has been qualified as the Jo predicate。

And it goes off， you， goes off to the next round。 and next operator。

 I'm not saying what what that physics looks like just yet。 We'll cover that later。

So I've been referring to this language between inner table and the outer table。

 Now you understand where this comes from。 it's like when you use the term in terms of joins， right。

 it has to do with the loops， right， The outer for loop is called the outer table and the inner loop is called。

 obviously， the inner table。And in most systems， they would represent in the query plan to your left。

😡，The table on the left of the joint operator is considered the outer table and the one on the right is considered an inner table。

😡，Some systems flippers。 I think snowflake flips this。And then I think SQL Ser puts it on the side。

 makes it horizontal， but in general， it's the outer table。

 typically people understand that to mean the one in the left。Okay， so got put the mark up。

 Don't do this。 This is stupid。Why。You've got to look through the second table a lot of times。

 He says， he' got look through the second table a lot of times。 And furthermore。

 we're not even taking an account that we're not storing data as a single records that we inside pages。

Right，So this is basically same for every single tuple， no matter in the out table。

 no matter what page it's in， loop through all the tuples in the inner table。

And then go get the next tuple in the in the outer table and fetch that page again。

 potentially and do the loop all over again。So again， it's obvious for every table in R。

 we're going to scan S1。RightAnd so the cost for this going back to the nomenclature。

 the syntax we're using before， the cost is m plus m times n。

 The plus M is because we've got to scan all the pages in the outer table once。

 and then we're going to scan all the pages， the big n pages in the inner table， little M times。

 So for every single tuple in the outer table， we're going to scan all the pages in the inner table。

😊，Again， it simply there's no caching。 Nothing's in a buffer pole。 right， This is。

 it's a very naive implementation。So if we turn these variables into numbers。

 we actually can see why this sucks， and then as we get better， how much faster we can make things。😡。

So say the table R and M R has 1000 pages with 100，00upples， S has 500 pages with 40，000 tuples。

 like not that big at all。😊，RightAnd then if you plug and chug these numbers in。

To taking the formula， we see that we're going to be 50 million IOs just to do this join for these two tables and let's say we have an SSD that can run in 0。

1 milliseconds per fetch， right？😡，It's going take 1。3 hours to compute this。Again， we're ignoring。

 you know， O S could be caching things。 Hard could be ignoring all of that Just assume it takes for every disk I O。

0 milliseconds。 This simple join takes。An hour。All right， well。

 what if I do the thing I said before would that you always want to have the smaller table be the outer table。

So what if I flip that RNS， make S be the outer table。😡，Now we cut it down by10 million IOs。

 but we're still in 1。1 hours。Right？This tables super small， right， I'm showing abstract numbers。

 but assuming we're doing four kill by pages。😡，Right。This thing6 megabytes。

That's going to live in L3 cache。On your CPU， that's nothing。Again。

 Harvard is going to be do a bunch of cashching and like it's not going to be as this bad。

 but like if you just do the stupid thing and say， I got a single tu at a time。

 it's going to be terrible， yes。Quickly repeat。We began。The question is， why do we add big M？

This question， why we add bigM， so going back here。

So my algorithm is for every tuple in the outer table， so that's an R。

 go fetch every single page once。😡，Then for every single page。

 then I'm going to go fetch all the essences pages every single time。All right， so this sucks。

But again， we know that the databases could represent or store data in blocks or pages。

So we can take advantage of that and do what's called a block nested looptin。

And the idea here now we have much more forlips where they have the outer loop。

 the top loop is getting every single block in R， the inner loop is going to get a block in S。😡。

And then now you just do the， the in memory in memory four lips on this。

 on these two blocks for every singleql2 beside them and check to see if I have a match。Right。

So now the algorithm is better because now we saw the big big M as the cost in the beginning because I got to scan every single block in。

InIn the outer table。But now I only scan the， the inner table。

 big M times because for every single page in the out table， I get all the pages in the inner table。

In this example， again， we are assuming that we have one frame for the outer table。

 one frame for the inner table。 We obviously have a lot more memory available to us so we can do better here。

Yes。配置ですね。So question but， sorry。平が先生。It question could a page you same？I think I said before。

Block and page are roughly the data might call it a page on the internals。

 but in Harvard might call it a block that basically synonymous。All right， so again。

For all these algorithms， we want the smaller table to be on theer outer table。

 because that means we can try to keep that in memory as much as possible。Right。

And the way we're going to calculate this is based on the number of pages that we expect to have or the number pages we do have for our tables and not the number of two pools that we would have with them。

Remember， again， the data set is going to maintain a bunch of metadata in the disk manager。

About or the page directory， about forgiven table， here's all the pages that I have for it。😡。

Some of those pages might have empty slots。😡，Well， that still doesn't matter when I'm doing my joincause I。

 I may go get a fetch to go fetch a page， and it may be completely emptyca for one twople。

 I still had to go fetch that page。It doesn't matter how many tables actually have。

 It comes down to the number of pages I have。 That's what really matters at this point here。

And they said， we can be clever and say， okay， well。

 I know I have a bunch of buffer pool frames I can use for this。😡。

So I can use B minus- two pages for the outer table because again。

 I want to try to get the outer table as much as memory as possible because read that in once and then I don have to go back and read it again。

😡，And then I would use one page for the inner table because I can only do one examination of a page at a time。

 we're ignoring parallelism here。And then I need one page for the buffer for the output。

So you just change the setup like this， I'm getting B minus two pages for the outer table。

 one page at a time for the inner table， and then do the scan and as I said。

 block and page are the same thing。So again， we go back to our situation or hypothetical example before now the cost model is going to be big m plus the ceiling of divided m divided of b minus2 because it's the maximum number of pages I can get in B minus2 blocks or buffers and to multiply that by big M because that's again for all those pages。

So the batch pages I get for the outer table， I have to go fetch all the inner tables pages。

So now our  query they had before， right now we get it down from。

 I think we had 40 million IOs for the block of this loop join。

 or sorry40 million IOos for the9 this loop join switching the outer and inner table。

 now I get it down to 1500。Okay， well this is actually more realistic now， right？

And I can give this join in。So 150 milliseconds。That's reasonable。Not great， but reasonable。

So if we sort of change the parameters of what B actually is。😡，啊。You， say I 102 pages。 right now。

 now this calculation has has come into play。 Now we get it down to the 6000 i Oos or switch the outer。

 the outer in the enter table and we get down to 5500。So what am I essentially doing here。

 I'm basically doing a bunch of sequential scans on the， on the。

 I try to sequential scan the aer table once。 And then for each set of。

sort of a batch of pages I can bring the outer table in。

 I'm going do another sequentialial scan on the inner table。

Sometimes that might be the best you can do， and that'd be good enough if the data set is small。

But usually again， usually you do not want to do this algorithm。Al right。

 for this basically repeating what to said， right， The reason why it's bad is， again。

 you're just doing much of loops over and over again and。

Lindly searching's like a needle to a haytack to try to find a matching tuple between the inner and the outer table。

But again， the problem we have is get the squ of scans。

 But if we have an index that already exists on the table。Then we can use that for the inner table。

And then now we just do a scan on on the adder table as a sequential scan and just probe into that index to find that the match that we want。

And then now we don't do this this s scans over and over again on the inner loops。

So if you had an existing index， you can do this。 Some sessions will actually build the index on the fly。

 So SQL server does this。 They call it sppoing indexes。

 So it says I really would wish I had a B plus tree here to compute my join。 So you know what。

 I'm just gonna build it right now。 So Scho scan that the inner table once。

 build the index probe it for my join。😊，And then throw it away once the query' is over。Sel server。

 I think it can't even come back and give you hints and say， he hey， look。

 I keep building this index and do this join。 you probably should build it for me or tell me to build it。

Yes。So when does this。啊。Building index。喂。bring。His question is。

 when would you actually want to build an index on the fly and throw it away？Well。

 we'll see in a second。 This is what hash join does， right。But the。As I said。

 if the the data system can recognize， oh， I'm， I'm the best thing for me to do right now is。

Is a index that loop join because you can， you can calculate things like hypothetically。

 If I had an index， this thing would cost this amount of build and you can compare that against a hash join and server's join。

 And you say， okay， even though I start I have to build this index。

It's going to be cheaper for me to do this than doing the naiveness of loop scans or in the blockness loop scans。

Right， so so these have a some notion about。How much do you have what the query wants to do。

 and it can make that decision for you。 We'll cover that after the， the midterm。It's hard。

All right so index next loop join basically replaces the inner loop now with a probe to some index and I'm just calling this index。

 I'm not declaring whether whether it's a hash table or a B plus tree or try。 It doesn't matter。

 We have a way to do a point query look up to go retrieve a single tuple sorry for a single key。

 go get the one or more twoples that match for it。And then for each of those that match。诶。

Maybe additional qualification， then you would go ahead and admit it。

Right so you may be the case that in this example here it's joining our ID with SID。

 So we have an index on SID。 So it's an exact lookup to go fetch that one tuple or the one or more twoples。

 But it may be the case my join clauses also has additional predicates and the index doesn't doesn't have any information about those other attributes of my join clauses。

 So I still do the probe and index， get the， get the record ID go then fetch the tuple。

Then do the rest of the joint evaluation。 And if then it matches， then produce it as my output。

So now our cost is going to be M big M plus little M times C。

 and C is just some constant that says it's the cost of probing the index。😡。

RightIf it's a B plus tree， it's going to be a log n if it's going to be a hashable on average01。

RightBut we can't account for that because we don't know what the index actually is in in sort of theoretical theoretical analytical evaluation right now。

Right。So again， big M the scan all the outer table。

 but then for every single tuple in the outer table， go do that probe。😡，Al right。

 so with the main takeaways for next loop one， it's a building block we can use to start doing more complex joins in general。

 we're always going to on an appointment when put the outer table to have the smaller table of the two that we're joining be the outer table。

And we try to put as much as the outer table in memory as possible。

To reduce repeatedly having the scan it。Okay。All right。In the when the in has a loop join。

 we have a data structure available to us go find the exact matches that we wanted。Right。

 and that's part of the problem with the nestA loop join without that index。 You'。

 it's just sequential scans。So with sort merge join。

 the idea is that if I sort my data from the two tables， I'm joining on the， on the join key。

Then I can walk through and scan those sort of results。

 and I know in some cases I never have to backtrack because as I'm going down scanning down。

 I know that there isn't going to be some key on the inner table down below that's going to match on the other side and I may have missed it。

😡，Right， so the idea is that we， we sort everything ahead of time。 And then that simplifies our scan。

To then about allow us to not have to hunt and pack and try to find the thing that we're looking for to do the join。

So this is I say in last class， there's the external merge sort algorithm we talked about last class。

 and you can use that in the external sort merge join algorithm。

 So you would use external merge sort in the sort phase of the sort merge join algorithm。

Does doesn't think you sort of merge， it can be quick sort or whatever your favorite sort is。

 but you start in the beginning and then you do the merge。😊。

So I'm not going to walk through this algorithm and don't really like to show code。

 but the basic idea is that we're going to sort them both first。

 and then there's going to be this cursor that's going to walk through the outer table and the inner table and sort of in lockstep and they move down once they know that there isn't going to be a match anymore because the values are increasing or decreasing accordingly。

😡，And in the case of the outer table， we sorry the inner table。

 we at that backtrack because we missed something because the outer table moved down and repeated the value。

 but I'll show an example of that in a second。So again。

 here's that same query when you want to join RNS。So the join predicate is R I R do I D equals S I D。

 So we're gonna to sort both relations on the I column， right， So that's easy。 That's done。😊。

And then now in the second phase， when we do the probe。😊，Or sorry the merge。 we。

 we have this cursor that starts the beginning of breath relations。

 And then it's gonna compare across to see is the value from the outer table that my cursor is pointing at is at the same as the value that the inner tables cursor is pointing at。

 And if yes， we know we have a match。 If not， then we， we， we move， move down。

We move down based on what the values actually are。So in the very beginning， I say also too it。

 we we maintain some metadata on the， the in the inner table with this last value to say within the sort of last。

So the last batch or range of values that I looked at。

 what was that value in case I see that value again on the outer table。

 that I need to backtrack There's some additional metada to say。

 what's the offset to jump back into up that？ But for simplicity。

 we assume that we are keeping track。 I'm just not showing it here。So in the very beginning。

 the cursor on the En table is pointing at ID equals 100。

 the cursor on the inner table is pointing ID 100。😡，These are equivalent。 They're equal。

 So go ahead and mash the two twos together。 and then that's in the output of my joint。

And then now the inner table is cursor， It's going to move ahead by one。

We leave the outer tables cursor alone， the enter table moves ahead by one。

 and now I do the same check， ID equals 100， ID equals 100， that's a match。

 so I produce an output tuple accordingly。😡，Same thing now。

 the cursor moves ahead on the inner table， now I'm at 200。😡，And at this point here。

 100 doesn't equal 200。And 200 is greater than 100。

 So I know I need to iterate and move the outer tables cursor down by one。

Because I don't know what's going to come after this 100。啊。And I don't know what。

And I know whatever it is， it has to be less n or equal to 200 if I could ever have a match on the inner table。

😡，So I go ahead and move the our table cursor down， now we get 200。

 that's a match again to produce our output， and now we move the innercursor down by1， we get 400。

Now at this point here， now the value has changed on the inner table。

 so we go from we were we were at 100 because that was the batch above or the value above。

 Now we go to this next one here。 now we set it to the 20 because that's the last value that we saw before it changed。

Right。And then now because 400 is greater than 200。

I want to we't a match so that there isn't a joint here， a joint tual。

 Now we aerate the outerchiable cursor down by one。But now we see 200 again。😡，And at this point here。

 we recognize， oh， the last value I saw before I changed on the inner table was 200。

 so I want to backtrack。To where I was before， the starting point for when last I saw 200。

 because now there there's a bunch of tus that I didn't join with with the outer cables tuple。

So then now do the same thing， 200 equals 200， that produces an output。So that's fine。

 the inner table inner tables cursor moves down by1 now at 400， do the same thing again。

 the outer tables cursor is going to move down by  one because I've already moved down over here。

Now we get to 300，300 is still less than 400。 So I'm gonna keep iterating this thing going down because again。

 I know that I saw 200 above。 I'm at 400。 there isn't gonna There isn't a 300 on this side So there's no reason to backtrack。

 And this thing needs to keep moving forward until it hits 400 or greater than equal to 400 because I don't want to move the innercursor down before the outercursor moves all the way down。

 yeah。So now we're at 400， 400 equals 400 produce an output， innertable moves down to 500。

 again we set our last value to 40 in case we ever see 400 on this side again， right？😊。

400 is less than 500。 So this is going to move down by one。

5 100 equal 500 produce our output tuupple。 This thing moves down。

 Now we're at the end and we can just short circuit this。Well， actually know， take the back。

 You need to keep scanning down on at least one more time here because you you don't know yet whether this is going to be 500。

 and therefore you needed the backt。So again， once I see 600， you can just stop， you're done。Yes。

Are these I？when theyre sorting pictures are these stories。

 It means that we fetch like a page we might fetch like all the way from。Like5。

Your question is going back here， these are sorted。 Like， are these physically sorted on the Yes。

 Yes， the question is， are these physically sorted on the pages， yes。

Because this could be like again I scan the table scan table or a scan table S。

 then you do external Merchar I is going to write it out to a bunch of 10 files。

In the order that they're sorted。Yeah， I'm not showing page boundaries in this。

 but you can imagine like if I need a backtrack， I need to go back multiple pages that's why I didn't want to show the offset that says because it's not just like。

 oh， just jump to the third offset this， it's really the offset correspond jump to the page that corresponds to the offset going so many values back。

Yes，个。你个是应该。What do youて。It question， if I already had a if the data was already sorted。

 do I sort again？If it's sort of' join， know， it's already sorted。Yeah。

 but theed will not ensure that all the pages question uned an uncstered index will not guarantee that the data is sorted based on that index。

 yes。So your question is what if you have a cluster index？Like yeah， it's sorted。

 but the the locality is not there in un clustered right like this ensures that it's like has sos its going be insect also you question。

Oh， its what you just saying。If you have a cluster index， it could be within the slotted page。

 it's still not sorted。有。But that's not an issue because you would go over the slot。RightSo ph them。

 it might be stored in different ways， but the slot will be sorted by the value。

 So the iterator is really going over the curses are going over the slot offsets。

And that that'll still be logically sort of correctly， even if， physically， the bits may not be。Okay。

So what's the cost of this thing， Well，ing the store costs are R and S。

 that's just what we talked about last class。😡，Right， that's assuming doing external me sort。

And then the merge cost， assuming you're not doing backtracking， is just read all the pages of M。

 read all the pages of N once， and I'm done。😡，And I don't， it's not a multiplic。

 for every single page on the outer table， I've got to go read every single page on the inner table。

 as we saw in the N and loop join。 I I only have to go fetch the outer and the inner tables once。

The best case scenario is everything is all all the keys are unique and they're all sorted and on the backtrack。

 right。So if we go back to our example again， right now with。With， say。

 100 buffers that do our sorting。嗯。The cost of sorting R is 400， the cost of sorting S is 2000。

 adding mentioned together in the scanning unit all at once， the total cost is  7500 IOs。😊。

Much better than the naiveness of loop join， not as good as the indexness of loop join because the indexness of loop join just does the probe on the index thats super fast。

 and we weren't including the probe cost in our calculation anyway。So again， we went from what 1。

1 hours down to still7100 milliseconds， that's pretty good。

So the worst case scenario of assortments join is if there's only one value。And， you know。

There's only one value in each column， like all the Is are one。

RightBecause I'm end up sorting it and not not produce something different。

 And then I'm just going fetching and doing backtrack over and over again。Right。But in practice。

 sometimes it is very useful， especially if the query has an order by clause that just have to be the same thing as your join clause。

Because now again， kill two birds of one stone， I sort it to do my join。

 and then the output of the data of the join is sorted。

 and then now I on to run my additional auto clauses。😡，Or in the other way。

 if the data is already sorted on disk as he was asking about， then great。

 then I don't I skippped the first phase。 I skipped the sword phase and just do the join directly on those。

😊，Right。Doesn't always happen。Right，But if you can take advantage of that。

Then it's a huge win going back to the cause here。Right the the bulk of the cost here is from doing the sort phase。

 that's that's 6000 IOs。 So if I can skip this and just do this。

 then I'm basically get the index loop join。Right。Okay。

So the last I want going to about is Z hash one。😡，And the basic idea here is that we exploit the fact that。

When similar to how we were doing inserting to a hash table and then would you look up on it well if。

If things have the same the keys have the same values， then when I hash and。

 they're going to end up the same location。 So the idea applies now when I want to do a join。

 if I build my hash table on one table and then now I do look up on keys from in my join clauses into that table。

 if the values are the same， then I'm going to find a match。AndThen again。

 that's the equivalent of doing a lookup on the B plus stream。

But what's different here is that we're going to build the hash table on what we'll call the outer table。

😡，And then probe it with the inner table， whereas like the thislib join。

 you would probe the index on the inner table。But a high level conceptual。

 they're doing the same thing。So a simple hash joint algorithms have two phases in the build side of the build phase。

 you scan through the outer table， you're going to has it some hash function to build a hash table and use whatever your favorite hash table implementation you want。

 cuckoo hashing， linear pro hashing， chain hashing。

Lar Probe is usually going be the fastest one because it's so simple。

You build that hash table based on that joint key。And then now in the second phase。

 you scan through the inner table and just probe that hash able to define a match。 and if you do。

 then you prove that as the output。So concept just looks like this， again， it's two fourlibs。

 but now they're not nested because I'm going to loop for every tuple in the outer table。

 build my hash table， loop for every single tuple in the inner table。

 and then probe the hasht and producing any outputs。😡，So again， first phase， I scan through R。

 just hash it， fill out this hash shape， but that's going。 It's just sitting in memory。

 It's not back by the buffer pool。😊，Because we don't want that because it's random Is。

 we want this to be a memory。And then now I'm going to scan through S， do the same thing， do a probe。

 and find any matcheshe that we want。Pretty simple， right？

So one optimization we can do is something we actually talked about before。

 I think when we talk about chain hashing， we talk about how you can put， you put a balloon filter。

In the bucket array， so before I scan along the chain， which ends up being a sequential scan。

 I check the balloon photo to see whether my key could even exist in the chain。

And then if it doesn't， I know， I don't keep going。 If it does， then I do， do。

 I do check the the chain。So I could essentially do the same thing now for my join。

So as I'm building the。The hash table on the build side， the first day is for the outer table。

I can also build a blend filter。And then now on the probe side and the second phase。

 as I'm scanning through S， I first probe the filter， see whether I have had match， if I don't。

 then I just ignore drop that tubple， if I do， then I do go check the hash table。Right。

 and the idea here is that the cost of going up doing a probe in the， the blend filter is。

 is way less expensive or costs way less than the cost of doing a probe in the hash table。

 And so if my joint predicate or my my joint keys are。Or unlikely to match。

 then this is going be a huge win for us like if I know that I don't really have for for the outer table for the join 8。

 there isn't a lot of matching tus in the inner table。

 then if I can throw it as much as I can away with the Bfo in the beginning without touching the hash table。

 then that's going be super fast。Because the bers are using in a sit in CPU cache。 Yes。

 So is this hashing only better if like the original key is long and we are trying to use it like we are trying to trade from the with the computation of has to like the actual。

Actually， comparing long composite keys。your question is。

 when you say hashing the hashing foot into the blueprint or hashing into the hash。 your question is。

😊，Is hash joint preferable？When the join key is very long and therefore I don't have to do like like a bitwise comparison of things。

 you still have to do that bit wise bit by bit comparison bite by bit comparison。

 even if you match in the hash， right， So you point yes， if I hash and I don't find a match。Like。

 if the hasht was mostly empty， then yeah， that's gonna be fast。

 But if I had to start scanning down and because linearno probing and start comparing keys。

 I still have to do that full key comparison。 I can't just check hashes because because I could have collisions。

 like two different keys could hash the same thing。 So I always have to compare the full thing。Yeah。

 so we are basically trying to use like the trade off here is we compute hash for everything to like eliminate keys that doesn't have a hash collection because if the hack does not match No。

 so statement is。That。So your question is like are we doing a hash drawing because we can eliminate things when hashes don't have matches。

 I couldn't understand why we have to pay the computation for hash instead of just trying to compare this。

All right， so the question is， why did they pay the cost to do a hash。 let's go back here。

 Nor the balloon filter， okay。So back here。Your question is。

 why should I pay the cost on the probe side to hash the key。

 then do look them and hash it and find that my match versus of just comparing the keys。😡。

How do I find the keys， though， How do I find the keys on the built on this side。Right。

key ID equals 1，2，3，4。😡，Right I want two th over here， one thie over there。

 how do I find it for that key over here， How did I find it in this？This is unsorted。

 So I have to do a sequential scan。 That's your nest loop joint。 That sucks。

So this is basically an index for us that we're building on the fly so I can jump to some offset or some location in my hashable that may not have exactly the tubable that I want to do my match。

 but it puts me ideally in the proximity of it。So then when I start looking around to try to find it。

 I'm looking for less things。Yes， just to clarify the biggest difference between this and the index version is that there we already have something built in here we're doing it just temporarily His question is the difference between what we're describing here versus what I said before the indexness a loop join is that because this thing we're building on the fly wheres indexing is a loop join。

 you're using an existing index。嗯。😊，At a high level， yes。

 but we'll see how we can take this further and handle spilling the disk。

 whereas like in the indexing Slib join，' they can't do that very well。

There's optimization we'll see in a second， but like the hashable for joins if if it's in a quality predicate is almost always going to be preferable to an index or a B plus3。

Right， again， it's， there's no free lunch， right， We have to We have to find matches。

We either sch scan or we build a data structure to do it for us。Or use an existing one。

 So here's how I'm showing you how to do this with a hash table now。Okay， again。

 so this technique is putting a b foot in front of it。

 Sometimes some systems are called the sideway information passing because the idea is that I'm passing information on this side of the join to my my sibling that's joining with me on the other side。

 And you think of relational model with these tree data structures， conceptually。

 you're not really just a route data from this guy up to the join and back down to the other。😊，Right。

But it's an obvious technique you can do and it doesn't violate the relation model relational algebra。

Okay。So in the simple hashel one I has showed you， the hashhe will fits in memory。That's easy。Right。

Cause it's not， it's not， it's not random I O。 we're not gonna never going to disk。

 We're just probing this hash table in memory。 And things are fine。嗯。But if it doesn't fit in memory。

 then we don't want our buffable manager to start swapping things out to disk because since the hashing function sort of randomizes the locality of data or the keys that we're trying to join on。

 I'm probing to different locations to my hash table。

 and and any time I could be thrashing moving things back and forth。Right。

 so we media better our approach again， to avoid this random IO and try to maximize amount sequential I O we can do and still do a hash join。

 Still use a hashable to to speed things up。Right。So we're going to rely on that same technique we saw at the end of last lecture where we broke up when we were doing the aggregations。

 we broke up our table into buckets。Have those spell of disks needed。

 But then when we do now this sort of the second phase of the algorithm。

 we bring those buckets in one at a time so that they fit in memory。

 And now since we we've sort of hash and partition things at the first， the first phase。

 we know that the data that we need to join on has to be within the same sort of set of buckets at our level and not some other random location。

So this is an old technique called partition hash join。

 you'll sometimes see this referred to as the grace hash join。😊。

And then this is a classic technique from the'80s， pretty much every system implements this of how to do has joins when things don't fit in the memory。

Again， the two phases are partitioning things up， breaking out the buckets that can a memory。

 spill a disc， and then we bring those buckets in incrementally and just do the joins based on those。

The reason why it's called Grace hash joinedin because it was invented by this group out of Japan who built this thing called a database called Grace。

 and in one of the seminal papers out of this group was they talked about doing the Grace hash joinin。

So。Back in the '80s， there was this big movement called for Data machines。

 think of like community was so slow that everybody was trying to build these sort of specialized accelerators for databases and they called them Datad machines。

Grace wasn't the first one。 There's a lot There was a lot of different versions of this。

 So one of the first ones here， this is from I DM。I like I like this photo because it shows this guy like a suit working on a database。

 which is obviously how we work now。 But they would sell you special hardware that do sorting and memory because sorting was so expensive So you buy this this appliance database system and it had the specialized hardware to do this one aspect of queries that was super expensive because again。

 when you think about the number of different operators are things you can support in a database system Its not you don't need a general purpose CPU because you're not gonna be Bitcoin mining in your database system or doing some other random stuff It's gonna be regional size selection of relational algebra operators So you can start specializing some of the more expensive things。

😊，And get a huge win。So in the 80s again， people。Since the 80s and 70s people are trying to do this。

 And even now today， there's a bunch of different companies that they'll sell you different appliances。

 Terraada will sell you something。 Exada is probably the most famous one。

 Oracle sell you these giant box units that again have like infinna band。

 especially hardware to do things IBM had this thing on a Tsza was basically FG that did projections or did scans or filtering directly on the hardware and would feed it through the FGA。

😊，There's another company also now in Yellow brickrick from a few years ago。

 built solid in appliance。 that's basically their data warehouse running in a system。

Butterada and exada are probably the most， the most widely used ones。

 Like these things are expensive。 Each of these boxes is like $5 million， right， And that's like。

And then you have to pay whatever multimillion dollar year support contract for them， right？

The reason why this stuff usually doesn't pan out stuff definitely in the '80s。

 is because by the time it took you to design whatever specialized hardware to then fab it and then put it out for your customers。

 intel motor roll that put out a new CPU because of Moore's law and all the benefits you eventually got evaporated。

But again， people are still trying so this is like the Holy ground database like specialized hardware to make databases go faster。

 There's GPU databases， there's people use FAs a lot to still today。😊，But yeah。

 like something better than than just a X 86 CPU would be a huge win for databases。Okay。

 so let's see how we do the partition hash run。😡，So just like before。

 when we talked about aggregations， we're going to break up R and S into K buckets。

And so this just scanning through sequentially on， on the outer table。

 hashing it and writing it out into a into the buckets。 But this is gonna be。

You can sort to think of this as as like a a chain hasht。 we're just we're just putting things into。

 to。To a list of values。Then I'll do the same thing on， on the other side。Scanner and fill in and。

For the inner table， and then now when I do the second phase。

 I just go read the corresponding levels of the buckets from the outer table and the inner table。😡。

And then do my join and I could build another hash table in memory。

 right like when we tell the simple hash table and on the outer and the inner and do the join that way。

 or I could just honestly do a block nest of loop join。

Because everything's always is going to be in memory and it's going to be really fast。

Then now once I'm done the first level， I go to the next level and I know there isn't going to be a tuple。

 say on this side here， on the inner table， that's going to match something on the outer table in this other level because I've already hash it and made sure that it lands in the right bucket level。

😡，And I scan through down， and then I'm done。Right。So。What's one problem we could have？Well。

 what if now as I'm hashing the in the sort of first round and my。And I've swed my data skewed。

 and a lot of the keys are ending up in the same bucket。

 And now that that bucket doesn't fit in memory。Right。

 I think the whole thing didn't fit in in the first place。 But now when I part it again， the bucket。

 that bucket doesn't fit in memory。 Well， I just do this again。 do do another round recursively。

 I take the bucket that didn't fit in memory， hash it again， using a different seed。

 make more buckets and do the join once， once everything spills the disk again。😊。

The degenerrate case， the worst case scenario is theres like one join key that has like gajillion values and no matter if I hash it again。

 it's still going to end up in it's all going to up in the same bucket level anyway。

 So if you recognize this happens， you just fall back to a blocked nest loop join and just do the join just for that one subset side of keys that has to spell a map disc。

Right。And then， yes， the block and nest loop join sucks compared to a。know，Comp to a hash join but。

By avoiding random I O， right， you know， yes， it， it's going to be slightly slower， but it's still。

Itscring almost always sequential I O at this point here。 And this is。

 this is like the extreme case of like， I have one person that has。

 say you have an account and orders。 There's one person that has a million orders or a billion orders for。

 for whatever reason。 And it doesn't fit in memory。All right。

 so let's see how to recurs a partitioning so again， same thing the first phase。

 a hash all everything on the outer table using the same hash function with the first seed。

 but let's say this key here， whatever key is landing in this bucket here level1。

 and that's getting completely full。😊，So then now in the second phase。

 I just pass through the other buckets that they didn't get full like0 and came minus-1。

 they didn get passed over to the next round， don't have to copy anything it just say it just gets moved over。

 but then I use a different C for the hash function again。

 and I go through a second pass over this data， hash it up， split it up to smaller buckets like that。

😡，And then now things have evenly spread out， now things can fit in memory。

So then now on the probe side， yes there's some additional metadata got to keep track of if I hash a key and it lands in either the first or the last bucket。

 I know that wasn't rely partitioned， so I know I can just jump to the right bucket offset and that has the data that I want。

 but if I hash a value now that goes into the bucket that I've crystally partitioned。

 then I know I need to do another round of hashing to go find the exact location that has the data that I want。

😡，哎。So what's the cost of a？Doing hash join。But I don't need to do recursive partitioning。

Then it's going to be3 times m plus n。Right because in the partition phase， I got to read all of the。

But the outer table and the inner table once， write it out once， hence the 2 m plus n。

 but then now in the second phase， I can read them all back in every page once。And it's M plus n。Yes。

So we hash the inner table， How do we know which blocks have to go through recursive passion。

His question is， if I hash if I hash the inner table， how do I know in in this case here。

 How do I know that if I hash a bucket one， I should go for cur partitioning。

 So you just pass the metadata over to say you say here's here's the buckets and the first round of the hashing that it got split。

 therefore you do another round。 Like I can forcursly partition this infinitely。

 you wouldn't want to do that in practice one is usually one additional round be would be enough。

 But it's easy metadata。😊，All right， again， going back to our table four。

The cost analysis will be three times m plus n， so I got to read a to 100 IOs for the outer table。

 fit the iOos for the inner table， sorry 100 IOos for the outer table， 500 for the inner table。

 add them two together， multiply that by 3， and it gets 0。45 seconds。😊，So better than Stmer's join。

 Somer's join was  7500 IOs。Again， obviously there's number of cases where this won't work。

 but the me algorithm sort joint algorithm would have the same problems if one key has all the values。

 all the matches。So there's one additional opposition we can do called what's called a hybrid hash join。

😊，And so this idea has been floating around for a while， as far as I know。

 nobody actually implements this because it's really hard to get this correct。

Because you have to know something about the data ahead of time that you may not be able to know。

And the idea here is that if you recognize that。There's some key that's going to be super hot。

 meaning I'm gonna have to。On the on the。On the inner table is going to be a bunch of probes and hit this key over and over again。

Then rather than just spilling it to disk in the first phase。

 spilling all the buckets to disk in the first phase。

 I'll just keep one bucket or a small subset levels that I know are hot。 Keep those in memory。

 let everything else spill a disk。 And then now I don't have to worry about reading that back in over and over again。

😡，writing out in the first case。So say for whatever reason， there's some key。

 they're all hashing to this first bucket here。😡，So what I'll say then is， okay。

 well this level here， this is going to reside in memory and I don't go through that second phase。

 I just do the join as it happens as I'm doing the probe and then everything else that'll spill the disc and I'll do the second phase of bringing it back in the memory one bucket level at a time and then you do the join on that。

Again， the reason why this is hard because you kind of want to know what's going to be the hot key ahead of time。

But you may not have any metadata for that。Most data systems will keep track of the heavy hitters。

 like what's the most common key？But that's， you know， that's just within one table。

 But maybe the hottest key in this in this table may not be the hot key you're going to join on in this table。

 So you basically has to take statistics from two different things and try try to combine them together。

 which is not easy to do。It gives you have an incomplete view of the two tables。

AllSo hashs the inner table can be any of size。😊，But ideally。

 if I get my outer table to fit entirely a memory， that's fantastic because then I don't have to spill thing as a disk。

😊，If I know the exact size of the outer table ahead of time。

 then we can use a static size hash table。😡，Hi。That is sort of almost perfectly is it。

It's exactly the size that you need， things hatch your exact location。😡。

And then there's less overhead to do the join， but typically you don't have this。

And so what happened is like you're。in most instances you say when I run a query。

 I allow the query to allocate this amount of memory for my hash tables， and I hope I get that right。

And then if I get wrong， and I have to resize it， then I have to do the thing where you lock the whole thing and double size and load it back up。

 But that's gonna to be super slow。 And we， we won't avoid that。All right。

 so here's the summary of all the joint algorithms that weve talked about here today and roughly with their IO cost。

😡，And again， in general， the hash join for really large data tests is almost always going to be preferable。

呃。Even though it seems kind of crazy， like， I'm building this data structure on the fly and then immediately throwing it away after I run the query。

Well， yes， but that's going to be better than。诶。Then doing winter random ios or doing doing sequential Ios over and over again。

 I paid the sequential I O cost to build a hashable once。And thenm if I need a build as disc。

 I can handle that。 but then now I don't have to do a bunch of random I Os to do the joints。

Because I sort of reduce the locality of where data could actually exist。Okay。Yes。

Yes next look drawing very。Because you don't know the value。

 the question is why is index net joint variable， because you don't know what the value the C is。

 it could be a B plus tree， it could be a try， it could be a hash table。So you said if it's log。

If the people you could put a log in there。Well， it's also variable too， because it' it's。

Like if I have a one to many join， meaning like for one key on the outer table。

 I have multiple keys that'll match on the inner table that I might pro my index and then scan along a bunch of leaf nodes。

To get all the matches for that。 So you don't know what that's going to be。

 at least at this point when we're talking about this because it depends on the data。

 It depends on the schema and it depends on the query。

So even though it's still in a quality preddicate， it's like for one key。

 me multiple one key in the outer table， give me multiple keys on the inner table， it says variable。

Whereas like in a block nest loop joint， you basically scanned the whole thing。 I mean。

 you can be clever in some cases， like if you know。If you know it's one to one。

 which is not always the case， then like when I'm doing my block and as a loop join。

 if I say I know there has to be exactly one and only one match on the inner table。

 as soon as I find it， then I can break out of the inner loop。Right。But you have to know that。Yes。

 how accurate do these numbers actually end up being after。I can't like CPU cost。E question。

 how accurate these numbers actually be when you take account of CPU cost。Am。These numbers are okay。

😡，Right where do you have problems are。How are you gonna。Like these formulas are OK， right？😡，It's。

 it's these ones are going to be the problem。 the M plus N because let's say。

 again say I'm doing a three table join in my query。 How do I， how can I predict。

 I'm going to have trouble predicting what's the number two thats are going to come out of the first join。

Then feed into the second join。 So that means my M or M is going and M M or M is going be off。

That's just for two joins。 What if I have1000 joins where some queries actually do。 They're not， not。

 they're not super common， but they do exist。 But now you're basically building like crappy statistics all for crappy statistics all crappy statistics。

 and the numbers get way off。Yeah。And then we'll see this again after the midterm。 But。

 the one thing is that。Allmost all the data systems are going to。Underestimate。

How many twopo are going to come out from a joint operator？

Because they're going to make a bunch of assumptions about predicates like they're going to be non correlated。

 even though they will be correlated， so the c the estimates get way， way off。Yes。

larify about the sort one。 It has to be not just sorted， but also like cluster。

 right if we're just using a B tree on the main index。Of a table， it's still sorted。

 but there's going to be a lot of thrashing。Going through it in a sorted order。

 because his question is for the next Luke join。诶。That it's not enough to say that the start。 your。

 your concerned about things thashing。For the sorting or in sorted mergejo you said that if we already have something sorted。

 we don't have to restart sort right， Yes， but like the index of the tables already sorted。

 but we can't use that。Data can be sort of without an index。Right， so。

Like when we talk about these parquet files where like there's the source file format like I could have my front end application make me a bunch of files from from the front end database and then it becomes basicallym。

 but I could sort them as I store it and then I don't have an index for how it sorted。

 just I did externalmer and wrote it out。😊，So eaten。

 So it doesn't always have to have index be sorted。 So then your other point was。

 if you did have an index， though， is it the case that the， the。

Could you still have thrashing because now as your。

Becauseuse you're doing random probes into the index。 Well， no。

 because if it's clustered on the if the data is clustered， you don't need to the probe of the index。

 you just walk through， you need an iterator or your cur to be able to walk through the pages in sorted order。

 but you don't need to refer to the index for that。Yeah， if things are sorted ahead of time。

 it leiates a bunch of these things， but most data it's not reed。And again。

 like a B plus tree will be log in， a hash table could be a one。

And so the probe due to hashwing is still retention much faster than doing a probe into a B plus tree。

So then you say， okay， what if I have a hash table？😡，And I want to do an NX andS loop join。

 is that the equivalent as basically a hash joined？Sort of yes， but the。Again。

 you lose the flexibility of being able to do that recursive partitioning thing we' talked about before。

So I don't think I I， I， we think we can go check。 But I。

 I think if you have a hash index and you do a join。

 Postcuss won't try to pick it up to do an index loop join。 but I'm not sure about that。Okay。Alright。

 so hashing is， as I said， it was always going be better than the than sorting。 And basically。

 as I said before， there may be cases where things are already sort ahead of time or you need the results be sorted。

 the servers join algorithm actually might might be better。😊，But again， the。

 the good data systems that that can support these different operators。

 they'll make decision on the fly for you。 which one actually should be using。O。All right。

 next class， day term exam。I'm that bad。These databases， right， it's good stuff。😊，Okay， yeah。

 next class， mid exam。 Any questions， email me post on piazza。 And then I said。

 I have have additional office hours tomorrow at 1 PM in my office。 if you want to sort of。😊。



![](img/de84ad68707ab4cdae3ad8fafdff06b9_2.png)

🎼Check anything right before the exam Okay So I refreshing when I can finish manifest to call a whole bowl likeiff one and my hip hop related myoxicrics quick won summer waves pick rotate too quick duplicate Mikeahren when tight when in night starts to I heat the down I heat up a just let the rise to cool it off or saying a。



![](img/de84ad68707ab4cdae3ad8fafdff06b9_4.png)

🎼Yeah。