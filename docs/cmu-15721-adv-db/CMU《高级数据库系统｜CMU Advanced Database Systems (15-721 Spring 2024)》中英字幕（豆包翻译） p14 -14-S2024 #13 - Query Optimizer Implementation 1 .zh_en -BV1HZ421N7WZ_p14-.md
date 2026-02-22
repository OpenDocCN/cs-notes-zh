# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p14 -14-S2024 #13 - Query Optimizer Implementation 1 .zh_en -BV1HZ421N7WZ_p14-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/93438a71e08cecb0cc116364d8b8281b_1.png)

🎼。🎼So today's class， I' going try to get as much as I can into today's lecture。

 It might spill over it in a little bit into next class。 but this is it。

 We've been talking about this for a long time。 We're finally to discussing how we actually want to build the query optimize。

 which is the arguably most important part of a database management system。

 Every year I debate whether to even bother teaching 721 and just teach a topics course on query optimization。

 admittedtedly， this is the part of databases that I know the least about for people that actually working on the query optimizer here。

 the new project。 at this point， you guys probably know more than I do。

 But this is the hardest piece because obviously， like we can build the fastest engine。

 But if our query plans are terrible， then it's it's all wasted。😊，ok。



![](img/93438a71e08cecb0cc116364d8b8281b_3.png)

Okay， all right。All right， so this refresher last class。

 we were talking about networking protocols and again the main takeaway from this discussion was it looks and smells a lot like when we talked about storage on disk if we have a our applications are run on queries that really care about a small number of twoples then a row oriented API or network protocol that's going over a row oriented or row oriented API or roworiented network protocol that's being accessed through a row oriented API。

 the ODBC or GDBC， that's going to be sufficient。 but when we start doing queries that want to get a lot of data out of the data system or doing B export。

 then we want to use something that looks that's columnar。

 take advantage of all the things we talked about before。

 And as I said thearrow database connectivity library。Is one to facilitate that。

 and I think that's the future of overlap systems are all going to support this if they don't already。

And so as I said already， the next two weeks is really to talk about query optimization。

 So today's class and next class will be talking about how you want to implement the optimizer itself at a high level like how you going define the rules。

 how you then do the search to figure out what transformations you can to apply to optimize things We'll talk a little bit about query re writing and obviously plain immigration as part of this Co models will discuss more next week。

 next class will be sorry next week we then talk next class will be further into the the dynamic programming approach that's used by hyper and Ubra from the Germans and then on Monday next week。

 we'll talk about do adaptive query optimization like the query runs for a bit and you make decisions on the fly。

 whether to change things。 and then that'll feed into the cost model discussion next week。

 So the next two weeks is again purely on。😊，On query optimization because again。

 it's super important。So what do we care about in this scope。 So this is。

 this is obviously a refresher from the intro class。 But the goal of the data system query optimizer。

 sometimes called the query planner， sometimes called the query compiler。 If you're。

 if you're an older system or the old person， right， because that that's a remnant of the 19。😊。

Early 1970s， when the Ra model came along， like the idea of taking a high level language like SQL and converting it into a low level。

 not assembly， but exrusion instructions to run the query。

 they saw that being akin to writing a high level language like C because C was considered super high level back in the day and converting that into a low level assembly or machine code。

 so the idea of the query optimizer is that。We want to generate a for a given query。

 We want to generate a correct physical plan that will execute that query ideally with the lowest cost。

And I'm underlying the word correct here because obviously it doesn't matter if we have this super fast query plan。

 if it does not actually produce the result that we want， then and it's useless for that one。

 we can ignore approximate query processing stuff， we really want an exact match we're given SQL query。

 we can to produce the exact output。And the cost is in quotes is because as we'll see next week。

 this is going to be a relative term that's going to change depending on the system itself。

 that's actually implementing this。So the cost is going to be some internal metric that we can use to compare one plan to another and decide this one's better than another based on number tuples red or CPUs instructions used or network traffic。

😡，Again， that's going to change from one system to the next。 And typically。

 this cost is not usually mapped to something in the real world like like runtime。

Some of the enterprise systems， I know DB2 can do this where they're actually spit out。

 this query is expected to run this long。 but the area look like Postg is output of explainplain analyze or SQL light or other systems。

 It's always gonna to be some number that that's meaningless outside of that system。

So as I said before， this is gonna to be the hardest part of the system。

 just picking the join order is proven to be， I thinkmp hard。

 but the whole problem of furing out what's the optimal query plan is MP complete。

 And so that means that despite the name optimizer。

 we're never almost never gonna really find the true optimal plan if it's something really stupid。

 like select one semicolon that usually doesn't get past the optimizer some systems will recognize that immediately send you back the result。

 doesn't even execute it like little short circuitcu。嗯。But for。

 for things like looking up on a single index on one table， like， yeah。

 that'll be optimal because we know how to find exactly what we want。 But once we start adding joins。

 that's when things get really tricky。And so because wet find we can't do an exhaustive search to find optimal plan。

 we're going to have to use a bunch of methods to trim down the number of choices we have to consider and try to guide the optimizer towards a good plan because we can't prove that it's going to be optimal。

And then because it' too expensive for all these possible choices we could have to actually run them to see whether they what their cost actually is。

 this is where the cost model is going to help us speed things up。

 but it's going to be an estimation of what we think the system is actually going to do when it encounters real data that you're targeting。

So this is going to be super super hard and I'll try to sort break it down and walk through the different approaches that were discussed in the paper you guys were assigned and the old joke for query optimization is like if say you want to be a rocket scientist sorry。

 other way around， if you want to be work on query optimizes and you can't hack it and doesn't work out。

 then the backup plan could be rocket science because query optimization is considered harder than rocket science。

Of course， databases don't blow things up in the air， so maybe that's debatable okay。

So the important thing number1 semester two is the distinction between the logical plan and the physical plan。

 and the terms are going to be。Sometimes's conflated in the earlier optimizer implementation we're going to see because they may not even have logical plans。

 they'll go immediately from a SQL query into physical plans。

 but the cascades approach and the stratified search from Starbrst， that we'll see in a second。

 they'll have a clean distinction between the logical and a physical plan。And so the idea of。

 the logical planet is the， it's the high level。Operators we want。

 we want to execute for a query based on something that looks like relational algebra。

 Like I want to scan this table。 I want to join these two tables。

 but it's not specifying what actual algorithm you want to use to execute those different operators。

So the optimizer is going to take the parsse tree from the SQL here that shows up。

Do some transformation to convert that into logical plans that represent what that SQL query was trying to do。

 And then now it can do further optimizations or further transformations of those logical plans into new logical plans。

 or it can convert the logical plans into physical operators a physical plan thatll define how we actually want to execute things And this physical plan can oftentimes will depend on what the data actually looks like on disk Do we expect things to be sorted。

 Is it going to be compress a certain way。And you， itll specify also again what algorithm you want to use to produce that result。

So we're not always going to have a one to one mapping from a logical operator to a physical operator like you could have a logical join and a logical orderbike could be combined together into a physical sortmers join。

 But once you're in a physical form， you typically don' a physical operator form you typically don't don't convert that back to logical。

 That doesn't make sense。 and that sort explodes the search base if you actually want to consider stuff like that。

 So it's mostly logical logical or logical physical。😊，AndThis I've already said。

 but again the cost estimation is how we're going to use internally to figure out whether one query plan is going to be better than another during our search process again we'll talk more about this next week。

 but basically it's going to be a combination of these different metrics like how much data I think I'm going to read from disk or read from my child operator。

 how much data I'm going to spit out based on the selectivity of the cardinality of any operations I'm doing on that data as it comes in。

Is the data skewed， is it compressed where it's actually physically located。

 all of these things we have to consider to have a true cost estimate。

 but it's never going to be exactly perfect。 And the paper your guys read next week from the Germans will show you that once you do like two joins。

 then all these estimates get way out of whack and the query optimizer。

 the cost model estimates are going to be woefully underestimating the amount of tubs that are coming out。

And so again， it'll lead it to choose an incorrect plan。

So today we try to get through all 500 approaches you could have。

 we'll see how far we can get we don't get to randomized search as fine because nobody actually does this except for Postgres and Postgres only does it what if you have 13 tables in your join in your query but we'll cover that next class if you're out the time the main two ones that we're going to focus on are the middle three So again we're going to sort of walk through in order of complexity from simplest to hardest although stratified and unified are essentially equivalent and we're gonna walk through like here's how people implement these different these query optimizes。

 what are the pros and cons of them， what can't they handle and then how sort of the next approach as we go down tries to solve the problems for the previous one。

😊，And we'll sprinkle the discussion a little bit about how can real world systems do this？

AndBut the TLDR is going to be stratified search and unified search are going to be the most common approaches。

All right， so say you're a brand new startup。And you're branding a brand new database system from scratch。

 you're not like 14 Postgres， you're just literally running starting from nothing。

 The heuristic based optimizer is probably what most almost everyone builds first because it's super simple。

 it's a bunch of FNL clauses that look for patterns in in the SQL query and then apply some transformation to convert them into a better form。

And the reason why this works is that it's based on domain knowledge about what we know as humans about query optimization and queries in general。

 and we're basically codifying that in code could always apply those changes without worrying about whether the right thing to do or not。

 Yes， As far as I have to double check。 I don' I don't think they have a cost space optimizer。

The way Bong of D works is that they generate all the query plans。😊，Run them all。

 When everyone comes back first， that's what they pick。Because that's what it was a year or two ago。

I so you don't run like， like you generate all the query plans。 you pick one， you send that up first。

 see how long it takes。 Next time the query shows up， pick the next one， run that。

 Then you pick which one。You laugh， but it， it's pretty simple。 it works。

 And then after you like 20 iterations， they'll try again。はいで、すね。

Theyre not states but you're running the same period。

As David is the MogoG approach works if you assume the queries are going to be very similar to each other。

 maybe just different input parameters， that yes， you could do that。

 and in the OTB world or operational workload that Mongo initially targeted， this works。😡，Right。

Because again， it's like， go look up Andy's record。 go， go look up Kyle's record。

 It's the same query， just different imp parameters。I I want to get too bogged on a Mongo。 And again。

 I'm not knocking them。 Im saying it's cleverly simplistic。

RightThere's other things to bang on them about like Mmap for this one， when I was like， oh yeah。

 I could see why you would do this because again， what did I to say at the beginning。

 this is the hardest part of database systems， They're trying to get a system up and running right away。

 They're getting huge growth。They got that far without a query optimizer。

Right so again this heuristic based stuff is going to be it's going to be ifNL statements that like look for patterns in the query plan and then applies some transformation to put it into a different form so the most obvious thing you can do is always do the most restrictive selection first because you're just trying to filter their things out soon as possible because we know is humans if why spend time copying data from one upper to the next if I know I'm not going to need it。

 so let me go ahead and try to throw things out as soon as possible。So that's predicate pushdown。

 limits， projections， and so forth。For join ordering， if you're lucky。

 they'll have rules that look at actually cardality estimates and maybe say， oh。

 this one's bigger than the other one swap them。 We'll see the case of the oracles。

 Their first im didn't do that。嗯。So the two out of the three first relational data systems built in the major relational data systems built in the United States in the 1970s all did this。

 so Ingress did this up until the mid 80s， Oracle did this up until the mid-90s。

 but in case the other major one system are out of IBM research。

 like they're actually going to do a call based search， which we'll see next。Again。

 most new database systems， unless you can reuse something like Calcite or OrCA or an existing query optimizer like Li Postgress。

 this is what pretty much everyone does。And long term， it's not sustainable。

The reason I qualify is the two out of three first relational datas in the US because there was another one in Sweden con Myer Sequel。

And there's a German one called Ada Bos， but I don't know what those guys actually did。

 so there are other relationship at the time， yes。問題かば。Sternbreaker built ingress， yes。

Why is it called Postgres， because it's post ingresss？Yeah有。He built Ngra。

 it stands for something interactive。Graphical， it was they got a grant to build it for a like a G I S application。

 And then they started building it out to be more general purpose。Right。Yes。

So about the last bullet point， I thought Carinality as missions。

His statement is on cardinality estimates considered part of the cost model。

 but the difference is going to be like there isn't a search process where I I'm in newver different plans to say is this one better than this。

 It's literally like if I have a join and the card down estimate is this one is greater than this one。

 flip them。It's literally all it is。again， back in the day， datas that are small。You know。

 you didn't have CTEs， you didn't have window functions。

 didn't all this other stuff we've been talking about。 So this would get you pretty far。 And for OTP。

 again， this will get you pretty far。So let's look at some basic optimizations as you can do with this。

 So these again this is our refresh for from the intro class。

 but I want to show you these because this will be what some of the heuristic rules will look like when we look at the stratified search and the other stuff because again。

 this is you can do this without a cost model and for a pure heuristic based approach。

 this will generate a plan you can then run but the idea when we do have a cost-based search we want to use these transformations to guide us and push us towards what will at least be a starting point in our search for our reasonable plan so we're not like blindly starting from the most stupidest query plan and then spending all our search time just getting us into a basic form that we've could have gotten instantaneously using one of these rules。

All right， so say we have a query like this it's three way join on， artists appears an album。

 and we're going to look up all the people， all the artists that are on my mixta right so the first thing you do is just split conjuncor prediates。

 so splitting any filter on the an clauses to break them up into separate filter operators。Right。

So you identify that I， I have a filter operator within that filter operator's expression。

 I have ans。 I split on the an and I create additional filter operators for that。Right， again。

 I don't need to cost to do that。 I know I always want to do that。

So now if I have these different filter operators， I can easily do now predicate pushdown to push the filter D below any join operator because again。

 why do I join when on table on data I I'm going to throw away up above。

RightSo I just push all them down， I said to be right above the join in this case here。

 but I guess they're below this joint up here。 So these are the filters that combining to two tables。

 After I do the Cartesian product， then I do the join or sorry then applied the filter。

Then the next up， obviously， we want to get rid of the Cartesian products。

 so we just convert the we recognize that we have an equality predicate right above us so we can convert any Cartesian product into an inner join or equiquajoin。

That， that's always gonna be faster。And then depending on the system。

 I may also want to do projection pushdown whether I have a cost amount decide whether the size of the table I or the data that I'm pushing up between one operator to the next is really big or not。

 But I guess recognize that rather than copying all the data that know I'm not gonna to need。

 I'll just push down the projections would be below and any join operator。

 So I'm only passing along the minimum amount of data from one operator to the next。

So all these were these four or five steps I showed right here。 again。

 these are logical transformations that I can do without having to have a cross model and it didn't specify what joint algorithm I'm using or how I'm accessing these tables。

 I can operate directly on the logical plan to do this。

 And again we know this is always me faster than when I started that with whichizard' is like in the canonical form of converting SQL into relation algebra。

Yes， I think there are actually some edge cases where the pre creditdator is really。

 really expensive。As David is there are some cases where predicate。

 the evaluation of the predicate is very expensive from a computational standpoint。

Then pushing down the predicate is a bad idea。Yes。But we're not there yet。

You don't know that at this point here。Right， because how do you weigh like the number of。

Tupop is going in to the filter。Right， that's a projection。

 like how do I know the number two is going in to the join is going to be say it's this one here。

 say this comparison is super expensive。 How do I know that the number two is going in would outweigh the cost of applying this for everyone versus above。

After the joint。You don't know。이 cosmo。If you need to cause money use statistics。In the very end。

 didn't have any of that。All right， so let me show what Ingress did back in the day。And again。

 this is like kind of the Mongo to be one where I was saying like it's。It's delightfully stupid。

 meaning like you would never want to do this today。

 but given the constraints that they had at the time and the harder they were working with。

Without having a cost model and a query appizer。It's actually kind of clever。

So the dirty secret about ingras least the first version of it is it actually couldn't do joints。😡。

Yes， Vi ingress in like 1974 ish，3ishh5， couldn't do joins。God these important。

They couldn't even do that。给婚。Yeah， all three be stuff back in the day。

'll see how like but they they went to support the query like this。

 The example they always have in the old papers is like employer。

 employee salary like like or department like。Yeah， they're all pulling， let's how they do this。

 So say we had the same grade before， It' a three way join on artist Apps at album。

 but now Im want to throw in this order by clause for the artist ID。😊。

So the first thing they're going to do is they're going to rewrite the SQL query into single value queries。

 meaning the second case of the first one here， I take the first query。

 I extract out and move out the lookup on an artist and appears。

 and I have a single query looking up on the album based on the album name。

But then I'm going to materialize the output into temp 1。SomeSome table here。

Now I'm going further decompose query2 into two new queries where the first one does a lookup on appearss and in a join with T 1。

 and the second one is going to do a look of an artist and a join with T2。

 and again this one is materializing the output into T2。

So now we're going to do is're going to run the queries one by one。

 starting from the top to the bottom， and whatever the result is。

 I then inject that into the next query I'm going to execute。😡，So if I run this first query。

 query one， look up the album based on the name， it's going to produce album ID 999。

So then I take that， map that into the rewritten query on the Apps table and substitute what would have been the join clause on the artist table or sort of the album table。

 and now inject 9999。And then this thing produces a result， two results here。

 And then I'm going do a fourth loop on that and run each of those queries one by one。Yes。

Going back here。TheQu 2 got rewritten into So Que 2 had a freeway join or two other two artisan peers。

 and that gets rewritten into three and four。Any question yes， of？I it just wanted。

 what is the definition of a single value query to。Like one tuple for one table， yeah。So like well。

 in this case here， you would run it。Well it could be for one table so you would get this query would run once。

 you get two results， they could support multiple tus in the output。

 and then now you take these two values and just expand that out into different instances of the same query。

What attitude。I mean what。One table queries， single table queries。😡。

So I'm doing this at the SQL level， but they did this all at the logical level with just logical query plans。

 And then they would just sort of run this。 And so why I say this is like stupidly clever is。

You're actually running the query optimizer every single time you generate one of these queries。

 so for whatever reason， if for this artist ID equals 1，2，3。

 if there was a better way to execute that than doing look 4，56。

 you could actually support that because you would take this query plan running it through the planner and might choose a different execution path than this other one here。

😡，And because it's choosing on a purd single value within， you know， the lookup。

 What's the best thing to do。 So it's sort of an early example of adaptive query optimization。

 which we'll see you next week， but like。Because you're running the optimizer on a perque basis。

 but obviously this would be super slow， you wouldn't actually want to do this。Right。So again。

 it's a nice。To me it's a nice historical curiosity so there is a big optimization it's the easiest implement into tobu because again it's just a bunch of fNls。

 this pretty much everyone does and for simple queries。

 you're not going to get any faster than this because you don't mean obtain any state。

 you're not doing any look up in the queries against the cost model do estimations。It's like boom。

 boom， boom， and then here's the queryr and run it。Obviously。

 the downside is going to be this is going to be a nightmare to expand when you want to start do more complicated things。

 it's going to rely on magic constants to say how much better really is something than another if you start weighing in like the number tools this operator is going to spit out if you're flipping one versus another and then anytime you have like a nesttic query and this becomes a train wreck。

Right。And most， most obviously， actually， not just nest square here is in you have joins to figure out what's the right join ordering would be a total nightmare。

goinging back to this one here， the reason why we started with， with query 1 on on the Al might D。

 because that's the only input we had to the query。 we know what the starting point is。

But if it was just a join across the tables without any input。

 then you have to pick what is at the starting point。

 which is the first table you want to put be part of the join， and then it all falls apart。So I said。

 this is roughly what Ingress and Oracle did back in the day。

 System R will see in the next few slides， they're gonna to have a costbased search for at least for the joins。

 If you read the unofficial biography of Larry Eson there's this nice little paragraph here somewhere where Stberger talks about Oracle's queryry optimizer。

 again this is about the mid19 this book came out the 1990s but he's talking about the race between Oracle and Ingress in the 1980s。

 and he talks about how Ingressss actually built a query optimizer that's going to look like IBMs。

 but Oracle was kept going on how that was actually the wrong way to do it and the right way to do is what Oracle did and that instead of calling it like a Heuristicbased optimizer。

 they called it a semantic optimizer because they couldn't do costbased search so to figure out the join order So the join order was whatever the order that that the tables appeared in the actual SQL string。

😊，And they call that Larry also called that a semantic optimizer。Right。So good marketing。

 and then like I said， or Oracle' is going to be right there in the 1990s and make it more state of the art。

All right so at the same time the InGgress and Oracle guys were building their heuristic- based optimizes。

 IBM researcher， IBM was building system R and they ended up building the first cost based query optimizer。

 and the idea is that it's going to use a heuristic stage just like we saw before where you can do the logical logical optimizations。

 but then they're going to do plan enumeration and transform physical operators。😊，Actually。

 that's backwards should be logical to physical and not physical logical。

 They would transfer transfer logical to physical operators and try to find one with the lowest cost。

 right。And obviously to do this， you need a cost model。

 you need estimates what each operator is going to spit out。

But you can't guarantee that you're going to find the optimal plan。

 but there's things they do would try to at least get to a good plan。

 like only choosing left deep trees instead of bushy trees if they're going to cut down the search base。

So this is what System R did in the very beginning。 This is what IBM DB2。

 at least in the early 1980s because that was the first commercialization of a relational database at IBM。

 They did something based on this。 And then most of the open source database systems are out today。

 Postgres， MySQL SQL light， They're going do something that looks a lot smells like this。😊，So。

For this one， actually， just skip。 but basically converting the query plans。

 logic operators and physical operators like to do this correctly。

 we need to understand like what what the table is going look like。

 what the inputs are going to be to this given operator， where the data to be located。

 All this is related to the cost model stuff that that we talked about before。

 And we'll talk about more next week。So to enumerate the plans that basically there's two categories and this is going to be similar to the debate between do I want to partition my hash join or not like the people go back and forth on this。

 but for query optimization the question is going be do I want to enumerate plans and build things up the physical plan from the bottom of the query plan to the top or from the top to the bottom or another way to think about this am I want to use a generative approach or a transform transformative approach。

 so a gene approach would be I start with nothing？😡。

Like I have no physical operatorsors in my query plan。

 and then I'm going to it assemble and inject new physical operators to work myself up to the final output。

 the root of the query plan that's going to produce the final result。😡。

And I can do cost based selection as I go from one level to the next。

So this is what system R is going to do， this is what Starbursst。

 which is theque optimizer that IBM built later on in the 1980s， early 1990s。

 this is what they're going to do as well。Right？The alternative approach is to do the top down of transformation where I start with the goal that I want。

 which is the root of the query plan， I want my final output of my query plan to look like this。

I'm joining these tables， it's sort of this way or whatever it is that that's what I want。

And then I'm going to permute it。The query plan going down and adding new operators that will then feed into my root to then produce the final result that I want。

😡，And it sort of seems like I'm justm making hand gestures and going going up and down like doesn't make any sense。

 but it does have implications for the scope in which you can examine and operate on the query plan when you apply different times of transformations and how you're actually going cost them。

 In the end， they're both kind of doing something that is they're doing a dynamic programming approach。

 it's just the way they're doing the costing and pruning things， will different。All right。

 so let's look at the system R optimizer， let's see an early version of a bottom up approach。

And then we'll see how that gets expanded into a little bit at Starbrss and as I said。

 next class we'll go into more details of the state of the art approach of bottoms up plant enumeration that the Germans do in hyperper。

 and I think Duck EB does the same thing as well。So the way systemR is going to work is thatqueries is going to show up and they're going to break it up the query plan into blocks that have logical operators for each block。

 sort of thinking of a block could be like a pipeline breaker or it could be a nested subquery。

 it's going to be some subcomponent or subplan of the overall query plan。😡。

And then for the logical operatorer within a subplan or a block。

 they're going to generate the set of physical operatorsters that could possibly implement it。😡。

And they're primarily going to be focusing on join access paths。 So figuring out， you know。

 how can I scan this table an index or sequential scan and then what sort algorithm sorry。

 what join algorithm I'm gonna w to use。And again， to reduce the complexity of the search base。

 they're only going to look at left deep trees。 So they're not going to sit right deep or bushy trees。

Again， this is a relic of the 1970s and Olympic computing hardwareor。

 But a lot of systems still today make this big assumption。As far as I know。

 left deep and right deep are always going to be equivalent。

 but sometimes you do actually want a bushy plan and they're not going to be able to find those。

And so they're going construct this left deep joint tree。

 and they want to choose the one that's gonna have the， the minimal cost。At the end。

 again based on some cost model estimate。So we go back to our  query panel we have before。

 so in the first step we're going to choose the best access paths for all the tables that we're touching in the query。

 so independently we're going decide oh， we want to do a sequential scan on artist and appearss。

 but then we identify that the best lookup for the album table will be on the index we have on name。

So all of those are occurring independently of how we're actually going to do the join。

Then we're going toumerate all possible join ors for the tables and this literally is just a Cartesian product of all possible combinations or a combinatorial combination of all the possible ways we could do a join。

 different joint algorithms， different join orders。

 whether or not we even do a Cartesian product the simple thing system are is going to do is sort of what I showed in the beginning is recognize that I'm almost never going to do a Cartesian product。

 so I can immediately throw all those away。And then now I'm going to do this bottom up base search for all these different combinations that I have to figure out what the join order is that I want to be。

So again， in this diagram here， think of the top as the final output。

And the bottom here is my starting point， so my final output is I wanted to have joined Art Appears in album。

 but at the bottom here I haven't joined anything。And assume also too。

 I've selected for each of these individual tables， as I showed in the previous slide。

 I've already selected what access method I'm going to use。

 So sequential scans for artists and appearss and then the index look up on Apple。So again。

 they're going to do a bottom approach。 So starting here at the bottom， they're going say。

 here's all the possible join combinations I could have for these three tables。

 because it's PowerPoint and for simplicity， assume it goes all the way on the other side with all possible combinations。

 I'm tru getting here in the second of time。😊，And then now these physical operatorsters then produce an output that's going to choose one of the two tables to be joined together。

 and then the third table is just waiting to be joined after this so I can do hash joins。

 merge joins and so forth。And then now for all these possible paths up to the next level。

 I'm going to choose for each of these next nodes at the next level above。

 what's the path that has the lowest cost？😡，So for each of these。

 I'm going to choose one of them as as the best one based on my cost model estimates。

 and then now again， proceed at the next level to do the exact same thing for each of these possible choices here。

 choose the different physical joint operators that then get me to my final result that I want。

And then once I've done that， do the same thing， choose along which one of these has the shortest least cost。

And then now， since I've reached the top of my query plan。

 I know this is the final result that I want， now I just recurse back and figure out which of these is the cheapest path。

And that's what I'm choosing is the optimal query plan for us。Yes。If you're already。

Just to clear it up。this example。So is this bottom up constructive like that？

The at least piece of the grape it's only worth。Or is it going to do all this for？Different。

Well I don't know if there's many choices for like I filter。I're going to try like the filter here。

 filter here， is's going to iterably construct all the other。His question is like。

When do other optimizations that apply like predicate push down here， for this approach in system R。

 they're only going to depict this and joint ordering。In the case of in Hysy next week。

 they're going to do DP just for joint ordering。The way you would handle the additional things that you're talking about is that you would define those additional transformation rules in a stratified search and you apply them potentially with the cost model as well。

 and then you do this DP search。Cascades will integrate everything all at once。

So this approach where you iterly try all the physical operator possible。

 is this am I correct in saying this is only practical？Join orderary。

And that if you weren to do something I could。Some other more advanced optimizations。His question is。

Would you only want to do this bottom approach， would you only do this for join ordering， yes？

Becauseuse again， like you're trying to like march through if I have to do recognize， b。

 I want to predicate pushdown。 You have to go back， insert it in somewhere and then then go back up。

 be kind of funky。QuSo I think you mentioned that。それはいはい。So is there special handling？Aggregation。

So there' special handling for aggregations， you would treat the aggregation as a block。

And you could subsidivize that further。I。Think of this as a query block and so yeah。

 well in this case the aggregation would be if it's no nest aqueries。

 the aggregation is the final output， so it would be a gray block above this yes。Yes。

And then the same thing， you could choose what aggregation algorithm I want to use。

Most it's going to be hash joinedin or the hash aggregate。Yes。

So you first select how do you access the tables， would it be possible that for a different join ordering。

 different access methods would be better。ToSa as I said at the beginning in this approach here。

 you first pick the access that they're going to use， then you pick join ordering。

 Is it possible that there would be a different access method would be better for different join order。

 Yes， like if I'm doing if I recognize that I have an index and I should be doing nested lip join instead of a hash join right。

😊，But if I， if I'm picking。To always do English join before I took my join order， yes。

 would I have a disconnect between the access method and the join order for this approach， yes。

 that's the problem。The stratified search and unified search will fix that because we'll get everything all at once。

So what's one problem with this query here？It's actually not correct， right。

 because my original query said I wanted to join these three tables。

 but I also wanted to do an order by on the final output。

And so in the original implementation of system R， this dynamic programming search piece had no notion of physical properties of data。

So I'm choosing to do a hash join， if I go back here。One of my choices could have been you know。

 a certain merge join。 So maybe in the case where my， my。

 I would have been better off doing the certain mergege join because then my， my。

 my my data would already been sorted。So the way IBM handles this or the systemr handle this is that David keep track of the best plan they've seen with and without a physical property like the sort order。

And then so they would have that。 they would have two plans at the end。 and then they would say。

 okay， my data needs to be sorted。 So if if I have an estimate what the sort cost is going be。

 if I add that on to my unsorted data query plan， is that gonna be less than the cost than of doing the sorting directly within the sort merge join And if still less。

 then you pick that one。 So it's sort of like an afterthought。

 they had they had to add this additional step to deal with physical properties of the data because they had no way to to handle that natively in the search Yes what you're talking the two alternatives are you do the sort just part of the join do the sorting as part of the join。

 or you add an order by like a sort note above yes correct Yes so statement is what I'm talking about in this case here because the query wants the data be sorted by artist I if I did sort merges join on artist Id here then。

This， the output of this would have been sorted on the way that the query wants。

 So you keep track of this query plan。 And then because it says it's the best one of all the ones that are sorted。

 then you keep track of the one that you pick that is not sorted。 And then at the end at the end。

 you do this final step to say， okay， if I add or sort operator on the unsorted hash join。

 I that gonna be less than choosing the path of merge join。 If yes， then I choose it， If no。

 then I then I revert back to my merge join。Yes， simple looking at the saving as the doubt。

It said downfall， it's not again， it's not bad。The reason why this is maybe insufficient for what we need is that they can't holistically look at all the possible choices you could have for the actual query。

Right。In addition to the heuristic step that they had in the beginning。

 is they actually going to look a lot like the thing we saw before with InGgress and others。

 not how Ingress it joins， but those logical transformations are to be written as FNL clause。

These transformations have any like idea like the underlying like algorithm rooms because if you have like let's like all your tables you to start or sorted if you have like。

preserve。Is it able to like propate that up so it knows not to like kind of sort later。

Is it possible these transformation rules to understand what the data ofs properties look like so that and account for that in its decisions。

 system R does not， the later ones will。Right。Yes， so if you wanted to do jurisdictionals。

 you would probably do it after building up the tree。

 right because otherwise you wouldn't have anything the tree。

Your statement is if you want to still do heresic rules， you do this after this search thing， No。

 you do this at the end。 Yes， you can go back and touch it up。What Post does？

After you do this search， then they go back and do some other additional optimizations， potentially。

You would be sort of forced if you wanted to do things after。The joint search。

M your physical and logical。Because this generates physical operators。

Transformations on logical things。Lo transformations need to happen for this。

And then once you have a physical plan， you get new additional physical transformations on it。

Psco says if you look at the Postco code， they do the drone sort。

 they pick they do a bunch of transformations at the beginning。

 then they do there's cost based drone over ring。Then they go back and touch it up and do additional physical optimizations。

 So the touchups would be physical physical correct， The touch ups will be physical and physical。

 yes。Okay。So。As I said before， this is an MPQ complete problem。 We could run this forever and。

 and you may not， you know， actually find the the， the true physical plan。

 So we need a way to know when we should we should stop。 So we need a notion of search termination。

 And this will both arise in， we need this for for actually so far and system R。

 but we'll need this in， in the stratified search and the unified search to cat kids。

So the simplest thing you to do is to do wall clock time。

This is basically what Postcards and other systems do。

 you can set basically a timeout of how long you want the query optimizer to actually run based on a physical walk clock time。

You can set a cost threshold where you recognize that if I generate a a the first plan that I see has some kind of cost estimate。

 and then if I run for。A certain amount of time。 And I produce a plan that's maybe 10% better or some some member like that。

 Then I just say， all right， that's probably good enough。 and you stop。

Of course now because you still need the wall clock time because this thing could be unbounded because maybe you never find actually anything better。

 so you still need to account for that and maybe cut things off， right？You know。

 you can try to be dynamic on this， right。If you can estimate the complexity of the query and say。

 okay， well， it's a 20 table join。 So let me go ahead and like give it， you know。

10 seconds versus like a 1，2 table join。 You know， maybe give it， you know。

 half a second or something like that。 But that's a really hard problem because you're essentially trying to predict how long a query is gonna run before it actually。

He actually knew what the query plan is going to be。It is possible to recognize that。

I there's no more things for me to examine。 Let me go ahead and stop。

 So you can do this on the subplan or within the group we'll see in cascades。 Like。

 if I know that there's nothing ever， there's no other permutations I didn't even consider for some subplan。

Let me just go ahead and stop and don't keep spinning the wheels， trying additional things。

The last one actually comes from Microsoft， which I think is actually really clever。

 and it seemed in itss。U。And it seems obvious after they sort of say it。

 where they found that instead of specifying any of these other other metrics like， you know。

 the wall clock time， which you really care about is the number of transformations that you've actually considered。

And that's what they use to is determine whether to stop or not。

Becauseuse the idea is that some transformations may be cheap to apply。 Some may be expensive。

 So I want to know， like， get a rough estimate of like。

Of how long you think a trans is is going to take。On average， and the number changes I need to apply。

 And then you sort of calibrate that to see， okay， this is when I see most of the benefit for。

 for the queries that I'm showing throwing into it。

And then now that's independent of actually the hardware。

 So no matter whether someone is running on a cell phone or a really expensive， you know。

 high end server。To get the right query plan， it's the number of transmission you apply rather than the wall clock time。

Yes， when you see number of transformations， you just said that like somewhere easier it's more harder to apply。

 are they like waiteded so that like it's like not necessarily just the。Waied in terms of like the。

 oh， the count， actually， I don't know。I don't think they mentioned。Whos they in their talk， Yeah。

 they don't imagine it。All right。The pros and cons of this。

 this actually works pretty well in practice。 And as I said。

 most most systems are going to use something that that looks a lot like this。

And you can do additional rules， again， to filter out things like only looking at left deep joins to prune the search base to limit the scope but how long things are actually going to take。

The downside is going to be like if you start throwing away things like bushy joins。

Then you may be just completely missing what the actual two optimal plan is going to be。

Because you're making these decisions to print things out without considering anything about cost。

And as we said， in the case this our case， you got to do extra steps to deal with the physical property。

So。The two approaches that Ive shown so far。These are typically written in。

Embbedded inside the database system， as I was saying， as more or less if then else clauses。

 if my query plan looks like this， then do this transformation。

And if you ever looked at the Postwes code， at least with the query optimizer and the sub subplanner function。

 it is like I do these， check these things， and then I check these things and I check these and when you go look in them。

 there are more or less， if then else clause that are looking for queries of a certain pattern。

But the challenge is that is that of this approach。

It's really hard to write a query app browser in this style coding because you're writing it in procedural code and you're gonna make mistakes or you're got to deal with a lot of duplicate logic to identify patterns and so forth and then apply certain rules and then check to see whether the rule you just apply。

 break some some other assumption you have about the query plan。Right。

So a better approach to do this and what people figured out in the late '80s and what is used in state of assessment today is that。

Instead of writing the code for here's actually the check I want to apply。

 and then the change I want to make， you write the pattern。In a high level DSL。

That's looking for queries of a certain you know a certain type with nodes operative a certain type。

 and then the transformation rule ideally in a DSL。

 but not always the case because you can't do that。

 And then you you then have a optimizer or you have your system generate the code that does those pattern checks and transformations for you。

 It's very similar to the J or code and stuff we talked about for queries。So in the late '80s。

 early 90s， there was this big movement on what are creating what are called optimizeizer generators where again the idea that you declare in a high level language。

 here's the patterns I want to check for， and then here's transformations I want to apply when those patterns match and now I can build these I can then convert these into in a cogen into actual code that I put inside my database system and I only do this when I'm actually compileiling with thing and not like on a per query basis。

And then now I can then build the search strategy or the search mechanism to then look for those patterns and apply them independently of the rules themselves so one team can go ahead and build the search engine。

 another team can go ahead and define the rules， and now even in a single location。

 I have all my rules defined and I can easily extend them and expand them over time。

So this is what we're gonna to see in all the new approaches。

 either doing stratified search and unified search。 these all be based on optimizer generators。

 and the two big projects at the time that sort of led this idea was IBM Starbursst。

 which is still used in DB2 today and or the first version was Exodus。

 which was a precursor the volcano， which is a precursor to cascades。

He ended up building the guy built three query optimizers， Cascades is the last one he ended up on。

Right。So again， the idea is you're coju the query optimizeizer's patterns based on some higher level language。

So the two ways to approaches are going to be a stratified search and a unified search。

 And I've already started talking about this already。

 But like a stratified search is that I'm going to do a bunch of transformations in the beginning。😊。

Based on heuristics， things where I know I always want to apply certain rules。

 and then I go ahead and do my cost based search。The unified search is try to do this all at once。

And for， another way I think。It's not exactly always going to be top down versus bottom up。

 But you think Cascades is unified search， and that's a top down approach because everything's all in the mix and you're trying to figure things out。

And then Starburst and others are gonna be stratified search。

 But they're primarily gonna be using the bottoms up。 But you could do this in a。

In sort of a stratified search， you could do a top- down search and stratified search。

 Like basically， that's what Microsoft does。 They have a bunch of rules that you know you always want to apply like product could push down。

 And even though they're defined in the same DSL that you would use for the costbased search。

 they sort of fire those at the very beginning。 And only at the end， later on。

 then they do the unified search to do to clean things up further。Yes。

 what would a cost site be considered？Okay。Calite， I think they claim they're based on volcano。

 but they claim that， but I think when we look at it， the lines get blurry。They claim the volcano。

 but it looks like cascades when I look at it。 And as far as I can tell。

 I think they're doing stratified because they're doing a bunch of rules you't want to apply。

 and then they do a cost base search。But I might， I may be wrong。

 I haven't looked at the code in a long time。Yes if you're applying。

 nobody always want apply and then。And that just strified？

That's what I'm saying the lines get blurred。 So cascades is a unified approach。

 The way Microsoft implements cascades is。A stratified plus is the heresistics then the search。Yes。

 so with the DSL， would you convert work the logical plan into some。Like DSL languages。啊，这。

This question is， you convert with the DSL， would you convert the logical plan into？

Then you apply the rules and then you compile or it something No。

 the DSL would say like I want to find。I want， if I see these。

 high level construct or definition just say， if I see。

These three operator nodes next to each other are in line， then apply this rule。

 so' like you're defining what you want to see in the data structure of the query plan。

And then the transformation rule， ideally， if you can write that into the DSL。

 but nobody actually does， that's usually going to be C+ loss or something that's the same language that the system is written in。

So the transformation you actually apply。t the original definition of these Opmat generators did not define it like that in practice everyone does。

I think in Coroach DB， I think have it for the rules themselves， they have it in their TSL。

 but you can then escape that and fall back down to go。Yes。Soう。

ItI is the difference between these two。That in unified search。

 they're all written in the same DSL and stratified search， they're defined separately。 No。

 so his question is， is the key difference that the unified search and stratified search is that。

These are all written in the same DSL， and these are all written separately， no。

It's like are you going to apply a bunch of transformation rules without a cost model。

Or do you do everything all at once with a cost model？😡，But SQL server， you said。

 doesn't it apply to how the cost model or end up？They're using cascades。 The cascades。

 that's what I'm saying the lines are blurry，I'm working on about top downward at the bottom up。

 How about that， okay。So。So again， stratified search， anything we've already talked about。

 you first do all the transformation rules on the logical plans。again you don't consider cost。

 and you basically as the programmer the system， you define here's the rules I always want to consider。

Now， you can search engine could be clever and figure out like， okay， well。

 I know the properties of the query plan and I would have enforcer rules in my in my。

first the rules is that make sure the properties are being or maintained when go from one plane to the next。

You can have all that in the mix， but the idea again。

 we're doing these transformations without any kind of cost model。So it's not an exhaustive search。

And then I do the call space search to figure out the logical plan。

 convert the logical plan to a physical plan。So Starbust was the first one that did something like this and again。

 you see the basic the two stage or just the rewrite stage where just like before in system R I'm breaking down the giant SQL query into blocks in this case here they're actually converting the query plant into relational calculus。

 not relational algebra。It's。Take a little fine。It's like existential qualifiers and things like that。

It's less，'s less， doesn't map easily to excutable code。 It's more mathematical。

I don't teach relational cs anymore because unless you go work on query apprs。

 what she is going to do。 Sorry， like most of you don't need this。嗯。We used to teach it。

 We don't teach normal forms that there's a bunch of stuff like in the text where we just don't teach。

Basically， again， it's more higher level expressiveness for relational algebra in relational calculus。

I don't。I don't know if cod invented it， it's from the 70s though。All right。

 so they've converted this high level form， do a bunch of these rewrites。

 then they convert that back to a logical plan or the choreograph model they call it。

 and then you do a systemr style， bottoms up dynamic programming phase to figure out the joint additional optimization。

So this is what DB2 still even uses today。Am。And as far as I know， again， again。

 the lines get blurry is calcite technically doing str search？Yes。

 but I don't think anybody converts to relational calculus other than IBM。嗯。And so。

So in for this exact invitation of like relational calculus into then the logical plans and then logical and physical in the step step here。

 as far as know only DB2 does it。 But the tricky thing is DB2 doesn't do this or all， sorry。

 I doesn't do this all versions of DB2。So this mean I mean， I know this。

 There's actually different four separate code bases of DB2， right， There's DB2 for Z O S， DB2 for。

The a a 900 thing from the 70s。 And there's then there one for Linux， Uni and Windows。

 And there's a fourth one I'm forgett， right， but they're all completely separate code bases。

And the one that they built for Linux and UniX is actually derived from an earlier project called OS2 Data Manager。

Who heres ever heard of OS2？One， the operating system that IBM built in the late 80s。

 early 90s to overtake windows before windows became huge right because IBM was IBM made the first personal PCs。

 but they made it over a commodity hardware。 everybody started cloning them。

 So if you look at old magazines， they talk about like。

Pcs being IBM PC compatible or clone compatible because they're just redoing similar things that IBM did。

 IBM wasn't making any money off of that。 So they they got back in the operating system business for personal computers。

 they O2 Windows killed them By， so they had this database management system that they built for O2 they then went to the port renamed to DB2 and port this。

 but in this great blog article from James Hamilton James Hamilton basically helped set up all Aws like infrastructure and cloud computinging stuff he's a big deal there。

 But he has this great blog because he used to work on IBM and actually SQL server as well。

 but talks about how in the early 1990s they had this crappy implementation of a database system in O2。

 but then they went to IBM research and got the Stars co optimize and put that in So the links the slides。

 It's a really good blog article。😊，Yes， are there any general advantages too？

I to relational calculus or relational algebra。Tran。That refine，His question is。

 what are the advantages to operating on relational calculus rather than philological operatorsators？

I don't know off of hand， like I'm sure there are。Yeah。

It might be just a higher form that you then can apply additional optimization on， I don't know。嗯。

Again， outside of Starbursst， I don't across anything that's outside of theory in data systems that operate in glal calculus。

Alright， and the sake of time， we'll just skip this。 But like the I've read or ground practice。

 But in the， I don't think the paper you guys read talk about this。

 But in a lot of the followup papers from IBM， they talk about there are struggles of writing the。

The the engineers struggle with writing the transformation rules in， this DSL that IBM had。 Again。

 I think part of it is because you're operating on inflational cculus， which is unnatural。 Again。

 we can cover that further if you want offline。All right。

 so the last 20 minutes I'm going to try to cover cascades。

 let's see how far we can get with this okay so again unified searches that logicalological and logical physical are all within one giant stage。

 of course the challenge is going to be is that there going to be a lot of transformations that we're going to generate as we do this and so we're going to try to're going to use memorization as a way to keep track of what we've done in an efficient manner and try to reduce the amount of redundant work or redundant computation that we're doing。

😊，So let me show what volcano does。 and then we'll see the deficiency of that。

 and then we'll jump into cascades。 So so again， the confusing things is there's a volcano approach。

 The dude is legendary。 So there's the volcano project of the system。

Des the iterator model that we all know about， defines the exchange operator due do parallel computation。

 but then he's also about a state of their optimizer generator that could be used for these things as well。

As far as they know， nobody does this， although Calcite claims they do this， they's based on this。

 but this is one of the first approaches to doing a top down on search to generate query plans。So。

 again， in the top down approach， you start with the top。 you start with like。

 this is the output I want。 They're going to work down from the bottom and assemble the pieces you need to get back to that top。

So you're basically going to evoke all these transformation rules that you have to generate new physical nodes and logical nodes based on where you're at in the query plan right So here's all the things combinations I can have just like before leading down to the individual scans on each of the tables。

So in the first step here， I apply transformation rules to convert the。

The physical join or sorry the logical join artist appear as an album into a merge join on two of the tables and then have a third table just being fed into it。

So then I traverse down here， and then I say， okay， well for this physical operatorer。

These are the logical operators that fed into me to get me to this result。

 So then I applied transformation rules to then generate the physical operators that produce the result that I was fed into them。

And as we going down， I'm estimating the cost， which I'm not showing here of each of these physical operators summing up the total back to the root。

 And that tells me the cost to， you know， where I'm at at this branch in the search stream。

And then I get down to here and say， what F didn get me into this and then I'm not showing here。

 but you could pick then the access method for each individual tables。Go back up here。

 traverse down the other side。 Here's the merge join for for the other two tables to produce this。

 Same thing I'm costing as I'm going along， right。You just keep doing this and over and over until you produce the final result。

And again， because we care about what the sort order is for the table in the output。

 I have these additional for rules that I'm defining to make sure that any data that's being fed into me from operators down below is putting the data in the physical property that I need or expect。

So in this case here， because if I care about the data being sorted by artist ID。

 if I then apply a transformation rule， that generate a hash join in this case here。

 that hash join cannot guarantee that data is sorted。

 so I can go ahead and cut this off and I don't need you any further traversal down into that branch。

Likewise， if I say， okay， I have a quick sort operator。

 well that'll get my data sorted the way I wanted， but then if I come down here。

 expand it out now to say well， what was the physical operators operators feeding into me。

 if I then say oh I could do a hash join below and now the cumulative cost of the quick sort plus the hash join is greater than maybe the lowest path I've seen down to the bottom。

 then I know I don't need to expand this any further。 and I can cut off this branch right there。

This is classic branch of bound surgege， nothing fancy here。All right， so let's jump the cascades。So。

The， the reason why I don't have you read the original cascades paper is that it's actually not that great。

Have you guys read it？It's it's not like he keeps banging it on how great his stuff is object oriented because that was the hot thing in the 90s and and volcano exodus were not。

 right， But you can'， you can actually can't take this paper and actually implement it right。

 The best you could do is this thing from it's a masters thesis from 1991998 at a Portland state where the first 30 pages It tells you actually what Cascades is actually doing way better than the original paper is。

 So if you want what Cascades is you could read again。😊，Pages 1 to 31。

 and I'll tell you how to do it in there。But this began to be a quick crash course on it。So again。

 just like in volcano， we're do a top down approach with background chaining。

 but the key thing is that now we're going support rewriting through these direct mapping functions。

That can iterly generate the transformations， apply them to fan out the search tree rather than doing them all at once。

So I didn't show in the case of volcano because it's PowerPoin。

 but every time I went down to another node， I immediately applied the transformation rule to generate all the possible combinations below me。

And then I would iterly look at them one by one。 Of course。

 now that would be super expensive to do if if a really complex query plan。

 because now the search base is going to balloon and you're going run and run out of memory。

So the key idea they're going to do is that they're going to introduce placeholders to say here's what the data should look like below me at this part of the tree。

 but I don't actually know what the right way to execute it just yet is。

 so I'm just going to have a placeholder for now， and then only when when I care about going that further。

 then I can expand it out， but now I can expand it incrementally。

Based on a priority that I can define to say， here's the things actually I should be looking at first。

And you define that all within the construct of the DSL that you're defining these rules。

So the four key ideas， one is that all the optimization tasks are going to be self-contained data structures。

 so know that then analysis think of these likestructs or objects to say here's the pattern I want to match in my query plan and if you match apply this rule and the additional metada to specify like what are the properties I need to guarantee or that I'll generate from this transformation rule for this operator and what priority do I want to give it。

😡，And his priority of can interesting is now as I'm traversing down， I can dynamically change。

 although Microsoft doesn't do this， but in the original paper they talk about or at least the master's thesis。

 you can as you look go down and you recognize my query plan is looking a certain way， I can say。

 well， I want to apply these transformation rules because I think that's going to help me out better than just picking one at random。

Right。And then the other key thing is that， although Microsoft doesn't do this， but cockroachGB does。

 is that when you think about doing optimization on the where clauses。

 the expressions of the predicates inside the query plan，😡，Well， that's just another tree。

And so within the same search engine or in the rules engine。

 you can do optimizations for the whereCa expressions in the same way you can do optimizations for the operator tree。

So simple things like I can identify where one equals  two。

You could have a rule that then gets fired to say， convert one equals2 into false。

Instead of having to do these optimizations separately。All right， so yes。Question。

 go to the second ser， so。So basically， you define in the implementation of the optimization task。

 like a pattern plus a transformation role， you define in that within directly。

 here's the properties that I need you to enforce。And then the surgeon can recognize， okay。

Something feeding into me is gonna violate that。 So therefore， I can't。

 I can't choose anything below that。And the second one basically says。

If I recognize as I'm going along， I'm trying to have an example here。Yeah a media example。

Ifm as I'm traversing， I may want to consider some transformations。More sooner sooner than others。

 like， for example， if I know my， if my， my operator above me。

 say is an index and asset loop join when I go down below rather than than look at all possible transformations from logical to physical like。

Choosing a s scan and then adding a sort。I may want to just choose the index probe first。

Because then that gives me the data in the right order that I need going up。Yes， yes。

 this is what the priority。 it's generated on the fly。 Well， so the case of Microsoft。

 I think they just like hard coded it。 So yeah， it's part of the task itself in the original paper。

 which I， which cockro would you be， I think。Think they said they actually do actually actually I don't know whether anybody does this。

 but in theory， you could dynamically change this as you go along。

So even though you may revisit the same。You may come back to a same group later on。

Because you didt maybe evaluate everything， you could change the order you evaluate stuff。Alright。

 so this part being confusing me because I use expressions typically mean like the predates and wear clause。

 but in cascades， expression is gonna to be some some operation within the query plan that's going do something do some amount of computation in the query plan。

 So a logical expression could be three way on A B and C where I join A and B and first followed by joining C。

 But then the physical expression could then be I do a hash on on a sweat scan for this sweat for that。

 then to do thisle join on index probe on this。 So it's defining like some set of。😊。

I' to say operators， but tasks within our query plan that we want to then transform into physical operators。

Right？And so the key thing that we're going to exploit is obviously equivalency rules in relational algebra because we would know that。

You know， we could switch the order of a join B to B join A。

 and that'll still produce you the same correct result that we would want。

 And so we we use that and define when we do our transformations。

 if we're permuting things a certain way that we're not violating any of comm properties or other properties we care about later algebra。

So then now we have the definition of a group， and that'll be for a given expression。

 it'll be all the logical and physical expressions that are equivalent to some output that I expect。

So in this case here， I want to produce the result of joining A， B and C together。

 and my logical expressions within that group will be all the different permutations of doing those joins。

 and then the physical expressions will be all the actual implementations of that。So again。

 this's all the logical forms and then all the physical forms that can be derived that。

From these logical forms。So the entire collection of these things is the group。

 in addition with the properties that we need to be enforced going into this。And then we have all。

 again， all the equivalent expressions for the logic and physical。

And then now we're going to find a multi expression， which is sort of confusing。

 but that's basically meant to be as a placeholder to say。Here's some expression that I have。

 but I don't know exactly the details of what's going on inside of it。

 and it's a placeholder to say there's something below me in the search street。😡，So for example。

 I want to join AB and C so I could have oops sorry。

I could have a multi expressionpression to say okay， there's a join an A and B together。

 I don't know what order in which way logically， and then I join with C or I could join B and C。

 and I don't define again what way I'm doing that， but it's just a placeholder to say something below me in the tree is going to be tell me how to do this And the idea is that we're using these multi multiexpressions as a way to reduce the number of unique operators we have to look at in this giant search stream。

So the idea， again， because we're top down， we can make decisions by looking at this placeholder at this point at some level in the tree without having to go all the way to the bottom in the case of a bottom of optimizeizer。

 you're enumerating all the multi expressionpressions one at a time and putting them together。

 going up to the top。So in that case they have not been materialized yet because you're starting from the bottom or to the top in the case of the top down one。

 you assume sort of roughly that you have the path going down to the bottom。

 even though you don't actually at this point。So this we've already talked about before。

 but basically the transformation rules， logical logical， logical physical， in the cascades parlance。

 they'll say a transformation rule is logical logical。

 and the implementation rule is to be logical physical。

 and then they'll have this pattern defines the structure。

 the logical expression that you want to look for， and then you have a substitution to define the rule of the new structure you expect to see after you do this。

Now， in some cases that you don't actually want to maintain the previous history or the previous plan you' permitteded or transformed the plan into because you know it's something you always want to do so for example like。

Like converting one equals 2 into false。 I don't want to maintain that history of like， oh， yeah。

 I did this transformation to convert one equals to to the false because you never you never want to go back。

And so there are ways to just。Always apply the change and then not keep a history because you don't want to balloon up your history space。

Alright， so here's here's looking at a example of a rule。

 So my pattern is that I want to have two echojoins with a with a right， deep， right deep join tree。

 So each of these nodes here are corresponding to groups because I'm not defining at least at at the rule level。

 What actually is going on inside of this group， right This could be an index scan。

 It could be another join could be whatever。 It doesn't matter。 It's just some group。

 It's a placeholder。We have to have a distinct echojo， at least a logical operator in this case here。

 that I'm joining two tables together。So say this is my plan that matches this。

 so again you see that I have my multi expressionpression at the top join A and B。

 but I'm not defining how I actually want to do this。

 but then when you traverse down and below it says I'm joining A andB and below that we have some get operators corresponding to the axis method the way you're actually reieving this data。

So this plan here， a logical plan would match to this rule。😡。

And I could have two jobs of transformations。 like I two types of permutations。

I I don't need transformation because that a type of rule。

 but I could do a transformation rule that converts me from from a left deep joint to a right deep join。

 just rotating the tree so that the joints are coming down the right side。 But again。

 this is is converting a logical operators to another set operators。

Or I can have an implementation rule that converts all the equijoins into。

T to be all startners joins。Or hash joints or whatever I want。Right。So again。

 these are what the patterns are going to look like。 and then we would match on this。

 and then we do these additional we can do these changes based on that。In this case here。

 you can see how like the， well， in this case， we we've joined with A and B on the servers joined。

 But again， in this one here， we have to have the placeholder for the multi expression because that's feeding up into it。

What's one obvious problem with this top one here？Because I'm going logicalological。

So you have another plan that does right to left。What going to end up with？

Well same plan infinite loop， you just keep flipping it back and forth。

So this is where the memo table is gonna help us out because we can use that to keep track of， oh。

 I've already have applied this transformation because I know the cost of of。

 of the query plan at this point to avoid getting stuck in in these infinite loops。So the memo table。

 at least in the original implementation or definition of the Columbia paper。

 talks about being a separate data structure， but you could actually embed this information into the groups themselves。

Yeah， and the sake of time， this is too heavy to go into for like。え。The last three minutes but。

Let me show one example now， and then we'll come back to this。 We'll。

 we'll start next class with this all over again， which is I I it's all this build。

 I at least want to show what it looks like。So say this is a query plan going it look like again the memo table just keeping track of for any multi expression。

 heres the best here's the best physical expression we've seen with a given cost。

 So in the very beginning， then we sort at the top we want to have a join team A B and C and we have no physical properties because we're not doing the order by for simplicity so I could do a a logical transformation to convert the。

Transformation rule， apply it to my output to generate a multi expression on A and B joined by C。

 So now I want to start crossing this decide whether is it worth pursuing further inspection of this of this multi expressionpression。

 by traversing down to the query plan say now my output to be join A and B。 Well。

 I could join the one way to do this is join A followed by join B。

 And the reason why A and B or multi expressions is because I'm not defining how I'm actually getting this data。

 I'm not defining what the access method is So to get further information about what this possible subplank could look like。

 I have to go down down to the tree now。AndNow in this case here。

 the only way to access A is to do a logical operator called get A， that's not interesting。

 I can't cost that because it doesn't tell me how I'm going to do it。

 but I could then do implementation rules to transform this into either a sequential scan on a or an index scan on a。

But then let's say for whatever reason for this data。

 whatever this query plan is the sequential scan is faster。

 So now in my memo table for for the multi expression on looking up a。

The sequential scan is the best physical operator I have with this， and then the cost is 10。

I do the same thing I bounce up back up here， do look on the other side of the joint。

 and I do look at the B multi expression， same thing。 I have a logical operator B。

 and I can transform that into a sequential scan on B， index scan on B。

For whatever reason it square to sell faster。 then I update my， my memo memo table here。

So now I bounce back up here。And now I just， now a transformation ruler to go from。

 know to swapping swapping the order for B And A。 And that's commmutative， that's a allowed to do。

 But now when I would do the same thing， Id say I have this multi expression on B and a multi expression on A。

 I got to go down to the groups below me and forget what the costs of those things are。Well。

 I've already done that right， because I can go look up on my memo table。

 recognize that I know the best operator for B and the best operator for A based on what's up in here。

So I actually don't need to do that traveral because I have this information already。

I just have to do look， look up on the memo table。Right。So now。

 since I've exhausted all my logical expressions or transformations that I could do。

Then I start generating all the physical expressions。 But again， I would do this incrementally。

 I'm showing this four。 But again you can think of like all possible combinations of join ordering and all possible combinations of of different join algorithm that I want to use。

😊，So now， say， for whatever reason， when I cost this， the hashstream between A and B。

Itns out to be the best， the fastest。 So then the cost of this now multi expression is just the cost of accessing a。

 the cost of accessing B， plus the cost of doing the hash join。

 again these are all just made up numbers。And so it's the summation of all of them。

 and now the cost is 80， so for the multi expression AB。

 the best physical plan is the hash showing on A and B。

 and the cost is 80 and now I bounce up the top and do the same thing down on the other side and so forth。

So this is what basically cascade is doing。Again， the devil's in the details about how you actually apply these transformation rules。

 I'm not sure anything about priorities， I'm not sure anything about properties。

 but this is the high level， this is what the search looks like。😊。

And then I produce my final cost here。And then now if I do any other traversals for maybe other physical operators or other joins。

 I stop the search once I see a cost that's greater than 80。Or I greater than 125。All right。

 so let's stop here Any quick questions， and we'll pick up this when we left off。

Predict wrong did rebuild the entire amendment。What am you I predict wrong？

If you let's say during execution， say， oh。the cost of getting B is like actually index where been way better。

 Did to rebuild the entire minimum cable。 So His question is。

 which we'll talk about next week addivity stuff。 like， what if my estimates are wrong。What happens？

Most systems， nothing。You just keep going。We'll see ways to put hooks in the query plan to say， okay。

 if I'm getting wrong， go back and replan things。We'll see cases like an IBM and other systems where you get feedback from like。

 hey， you told me this is this， but it's really this when I ran it again。

 So the next query comes along， you can get updated on this。But in general。

 all this memo state gets thrown away when the Wood square is done。

Which is why I don't want to do this in our optimizer。But then this thing is huge。

 how long should that be maintained for？Right？Also， when I'm not showing in these multi expressions。

 like I'm not showing what the original  query is like。

Though it's the question can on cost of 10 on a， but what's the predicate， what's the wear clauses。

 that could be different from one recruit to another。

 you'd have to account for that in your memo table as well。

So that you potentially could reuse it across different。You have different queries。Okay。

 I'm always over ambitious of what I can try to cover。In the in the last class。

 or in this one lecture。 So let me just say we'll pick up next class on we'll go through cascades again because we sort of rush that。

 Then we'll talk about randomized search for like in Postgres and others。嗯。

I debate whether I actually teach that because like I said， nobody actually really uses it。

 And the Postg one was broken。 Last year， I put together this playlist on YouTube。

 These are all the talks from the various companies over the years have come up with theirqua optimizers。

 The  one I can cannot recommend enough is is the one from Microsoft on SQL server because again。

 in my opinion， that's the。😊。

![](img/93438a71e08cecb0cc116364d8b8281b_5.png)

Other than the way hyper is going to do joint ordering。 this is the best one。

 and this is a really great talk。 The next best one is probably from Becca from Coroach Db to talk about how she built their query optimizeizer。

 which is based on cascades。 And they do some of the things that Microsoft doesn't do。 So。

 next class will be finish up with cascades。 finish up with random algorithms。

 We'll see how Germans do un nesting subqueries and how Germans do dynamic programming through hypergraphs for for picking join ordering okay。

😊。

![](img/93438a71e08cecb0cc116364d8b8281b_7.png)

![](img/93438a71e08cecb0cc116364d8b8281b_8.png)

All right guys， see it。

![](img/93438a71e08cecb0cc116364d8b8281b_10.png)

got a bounce to get the 40 l get a quick take a sip and you'll be picking up models ain't the puzzle cousin because I' more man I telling the 40 and I so he's got Thor cans。

Steps and six backs on the table and I'm able to see San I on the way。

No short with the cl you know what got them I take off the cat but first I tap on the bottom。

 don about three in them freeze it so I can kill it。

 cat full with the bottle babyop don't feel it coa now to insane the pain off way。

 you trick it down with the God and wild pet， take back the pack of nuts。

 and go get you some samen to trick it to the th， Billy de and to teeth to tell weak God。

 be a man to get a can of faint God。