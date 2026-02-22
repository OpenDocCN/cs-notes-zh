# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p03 -03-S2024 #02 - Data Formats & Encoding Part 1 .zh_en -BV1HZ421N7WZ_p3-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/0e84ca3d38a5043bfbcc5c854cdb4e91_1.png)

。🎼again starting the bottom of the system stack of this conceptual data system we've been building and sort of work our way up to actually be able start running queries and producing results。

 so we're going to start at the very bottom of the system and describe what is the data actually going to look like。

😊。

![](img/0e84ca3d38a5043bfbcc5c854cdb4e91_3.png)

So the first way to understand again， just remind ourselves what workload we're targeting。Right。

We've been talking about these OAP systems and their workload is going to look different than an O toB system。

 And that's going to inform us how we want to design again the data。

 how we want to lay out data on the disk or in memory。 and then again。

 all the auxiliary things we need to do to support that。

 So the primary thing primary sort of access method or access pattern we're gonna to have in a OAP workload is gonna to be sequentialial scans。

😊，Meaning we're going to be taking large chunks of data and scanning some subset of the columns that may be in the table。

 but just again scanning large segments of them at a time。😡，And therefore。

 we're going to have to do a bunch of stuff to make sure that runs as fast as possible。

 there isn't going to be typically there isn't going to be a data structure like like a B plus tree or a skip list or other things we would do want to use to help us find individual tus because we don't care about individual tus in OLAP workload。

 we care about aggregate information。We care about sequential scans。

 And the only time we or ever going care about finding individual tus is that we had to stitch the results back together。

RightBecause we're going use a decomppositionization storage model or or column store right we're gonna break up the attributes for single tuple。

 And that's fine because a lot of the processing we'll do in our sequential scans will be， again。

 on a subset of those columns。 But at the end， when we need to produce a final result。

 We may need to go find the other tuples or sorry other attributes for a given tuple and put things back together。

 We're not going want to use a， again， a。😊，A B plus tree or an other data structure to do that for us hash table。

Again， just the contrast remind ourselves from last semester in O to be environment。

 O to be workloads， they care about finding individual things， like go find Andy's orders。

 go find Andy's bank account。And。In in that world， we want to use again。

 like something like a P+ tree， be able to go find those things efficiently because OTP systems also need to be able to support updates。

 inserts， updates， deletes。 These data structures have to be dynamic automatically resize themselves as we insert new new data we don't care about any of those things in our world。

 Yes we do the。This question is why would I have to do stitching at the very end。

 that's late materialization。Which will cover。Two weeks， yeah。But that's basic idea is that like I。

 I want to avoid having stitch the tu together for as long as possible because I don't know whether I'm going to need even that tuple as I'm going up the query plan。

 So if I can hold off actually， need to have to put it back together to the very end。

 then I avoid unnecessary IO。I think I misunderstand what the means。 so like again。

 it's gonna to be a calm sort。 That's what today's talks about。

 We're going break up two into different attributes。 We' got to put it back together at the end。

Stitch。Question question was just like if we are not like using disease at all over like the labloads。

 Yes like how do we if we go the sequential scan find the tus that we want we passing the two as we see it we want that or is it like later Yeah the question is like how we actually how could we stitch things back together Like what additional metada we need to know is like。

 hey， you part of this tu'll put that together We'll cover that later。

The basic idea is that you record offsets。Good， that's， that's the query processing。 That's later。

All right， so。Okay， so if。if all we're going to do for OE workloads is mostly run sequential scans。

 again， it's not entirely true。 sometimes there's smaller range scans。

 we don't scan the entire thing。 Sometimes you do need to go find individual tus And for all that。

 we would have additional things we could add to our database system for now。

 we're going to ignore that。RightSo if all you're to do is S central scans。

 how can you actually optimize it。 So this list here is basically what we covered a lot or we talked about a little bit about in the intro class。

 but a lot of these other things weren'ret talk about in this class。

 This is basically the menu what's available to us So today's class is about data encoding and compression。

 how to minimize the amount of storage space it takes to represent data， represent tus。😊，嗯m。

Prefeching is identifying what data I'm going to need as I'm scanning along the table and go ahead and bring those things into memory before the execution engine actually needs it。

 So when it goes and says， hey， I need this block，voila。

 it's already here in memory or already in a local cache for us。

Paraallizations gonna allow us to run multiple queries at the same time。

 And within that single query， run multiple tasks or query plan fragments or different portions of a query plan at the same time。

 Either across different threads， different processes， different nodes。 and it doesn't matter。

Cluing sorting is identifying that the data can be sorted in such a way that when queries go。

 start asking for data within a even range or something。

You can minimize the amount of data you have to look at because you know that within some range。

 it's located spatially close to each other。Late materialization is what he was asking about how do I can I can I delay having to stitch the tub back together till the very end because I don't want to pay the cost of going reading things from disk or you know from memory if I if I know I'm actually not going need it and I don't need to materialize know take up memory to put things together either。

Materialized views a result caching is basically identifying that I'm gonna execute basically the same query over and over again。

 therefore I could keep the result of that query around。 and that way when someone ask for it again。

 it's already there or materialized view is sort of a specialized case of this where you recognize that there's a bunch of queries that need to operate or process the same subset of data like give me all the orders within today's month or this month。

 So maybe I could precompute that portion of the query give me all the orders for for this month And even though the queries may do different things on that month's worth of data I've already done sort the basic work of getting the month。

 Yes the data。😊，It question is， how is it different than the dataC stuff So it's basically the same thing in the data cube world back in the day even now they're probably not all very dynamic。

 but like you basically have to manually refresh and materialize view at least the idea is that if I make incremental changes I can then refresh the view now in the ideal case you want to do recompit the entire query because that's the dumbest thing you can do like if I insert one tube do I want to re this one second query or 10 second query now there are some systems that can do incremental updates。

😊，Immediately， this is the part of data systems I know the least about。 This is super hard。

 and we're actually not going cover that this semester。 It all catchchings， obviously。

 you just do pattern matching on this string and say， it's the same thing and then reuse it。

This is not that common either。Data skipping is being able to identify before actually looking at the data that I don't need the data and not have to process it。

Data parallelization or vectorization。 This is going to be sort of specialization or regular parallelization or task parallelization。

 The idea here is that within a single piece of data or or yeah， a chunk of data。

 maybe multiple tuples， I can I use things like CD to do multiple to process multiple units at the same time or multiple pieces of data at the same time。

And then code specialization compilation well again， we'll cover this later in the semester。

 this idea is that since if I know the type of data I'm processing。

 I know what the query is going to be rather than have this engine execution to interpret what the query wants to do。

 I could just literally generate C code that does exactly what the query wants。

 compile that and then run that。😊，It doesn't have to be C。

 you could use intermediate languages and things like that。

 but this will be a big thing I'll cover later on。So again， for this semester。

 we're gonna not talk about materialized views and we're not going to talk about the preventtching one。

 And so for this class， though， we're going to talk about like this lecture today。

 I' going talk data encoding compression。 and then the data encoding part is going to then help us for next class to talk about how can we code data in such a way that we can get better parallelism through vectorization。

 Yes， can I get the summary materialized views again。😊，This question is。

 can I get the summary material views， The basic idea of a materialized view is like。

Think of like a regular view like a view is almost like a macro of a query。

 So instead of having to in case a view would say like know systemma select query。

 create a view for it。 Now any time that someone does any treat like like a virtual table and any time you do a select on it。

 the database system is basically replacing the name of the table with the nested query that's defined in your view。

 But in that in that world and regular views。Every single time you run the query。

 you're recomputing whatever the select query that the viewpoints to。

A materialized view basically says generate the result。You know。

 when when you clear the view and then any time anybody wants to query that that view。

 you don't have to recompute it。 You have the result already。 But then the thing you can do is。

You can you can find materialized views on maybe they don't exactly match with the query once。

 like give me all the orders for this month， but and then you define that as a materialized view anytime anybody inserts a new order for this month。

 you have to then refresh that material view and the data system will do this automatically。

If they support automatic refresh in Postgres， you have to mainly refresh it and SQL server and other systems that will do it before you automatically。

 index you have a separate It question is， sounds like an index。 Yes。

 it's like a supplemental data structure。 Yeah， that's a subset of the data looking for。

 But the way the data maintains it it's just like a temp table。😊，But that if you restart it。

 it comes back。But the hard part is doing that incremental updates。 if I insert one two。

 say my views like the running total of the number sales for this month。 Well。

 if I insert a new order， I want to update that total， but don I know if I'm dumb。

 I'll just run the whole aggregation query from beginning the end。

 but if I'm clever about it and recognize， oh， well， this is just a sum of the total order amount。

 I know what this order amount is， just increment it。 but not every system can do that。Okay。

 so this class we'll talk about these two things and then how we do data encoding will influence how we can do data parallelilization vectorization later。

 and then we'll cover vectorization in more detail when we talk about query processing further along。

😊，But it's hard to try to avoid talking about Cdy， this lecture or vectorization， this lecture。

 next lecture that you'll read the Fast Las paper and it's all about it。

 but we'll see how to use vectorization for other things like joins and sorting and other stuff later in two weeks。

All right so today we just want to talk about storage models and then persistent data formats。😊。

I'm not going to talk about intermediate data formats。

 we'll cover that when we talk a little bit aboutarrow today。

 but we'll cover that in more detail when we talk about query processing It's really about these are the files that are on disk。

 whether it's an object store or local file system。

 it doesn't matter These are the actual bits that are getting put out in persistent storage。No。

Al right， so first thing we've got to discuss is what storage model we're going to use for these data files。

 And again， this this will be some somewhat of a。Repay we talk about in intro class。

 but it's important to go over this again more detail to understanding again what PACX is going to do for us later on when we start constructing the file formats。

So the storage model is going to find how we're physically going to store the tuples both on disk and in memory and again this is not the actual bytes we're actually storing it just says like okay。

 here's some tuple， here's some attributes for them。

 I don't really care what those bytes are in those attributes but how should I organize them in relation to the attributes within the same tuple and then across other tuples。

So the default storage model in most systems。 So what most people think about when they think about a data system is gonna to be the N storage model with row store。

 Again， this is what bus hub is。 this is what Postg my SQLite Oracle。

 This is what most people get decomposition store model is the sort of pure column store。

 And then the packs model will be a hybrid of the two of these。

 and you'll see that we' want to use packs because we'll have better locality for for attributes within the same tubple。

ll least be in the same block。😊，Again， so the easiestIS or not easiest of the default storage model that every system you can think most people when they think of data system they think about this storage model is going to be the nRA or the row store and again the idea here is that we're going to store almost all the attributes for a single tuupple continuously in our pages on our file or in memory one after another and I'm saying almost because again there are sometimes and some systems if you have oversize attributes like something more than4 kilobytes that it doesn't fit in a single page。

 they'll have an auxiliary storage。😊，Pogres calls this to storage。

 I think some system call a secondary storage， it's basically you just have a pointer to some other bb store thing that has the large attributes。

 but we don't really care about that。And again， this is be ideal for OTP workloads because in that environment。

 these applications， the transactions of the queries are mostly going to be concerned about getting single single tuples。

 like go get Andy's order record and because we're going to want to'ing new information from the outside world when to insert up and deletes it's really easy for us to take any new tuple that someone inserted。

 go find a free slot in some page and just write it all out there contiguously。😊。

And then when we want to commit the transaction or we later need to flush the journey page。

 assuming one tu fits in a single page， it's one disk right to put that out there。

So the page size in this wool is typically going to be some constant factor of4 kilobytes Postgres by default is 8 kilobytes oracles 4 kilobytes。

 although I think you can tune that DB2 you can tune this my SQ is the biggest one maybe at 16 kilobytes。

 there might be one that's32 kilobytes if you I forget which one but it's always going to be it's going to be measuring kilobytes like single digits kilobytes in this world because again。

 if you think about the workload they're trying to support， go get Andy's order record。

My record isn't going to be that big， it isn't going to be megabytes。

So it doesn't make sense for me to have these really big pages to store this row data because I got to go get that entire page and bring it in。

 I can't know in the NSM world， I can't bring in partial pages。

 I got to bring the whole thing because I need the header。

 I need whatever else the data is in that because I need to protect it in the context of transactions。

So the page sizes are only going to be much much smaller than well see for all networkloads。

And because again， because we're trying to do single tu of processing， for the most part。

 we'll want to use the iterator， the volcano processing model in this world。 Again。

 I don I don't want talk about too much about query processing， but that'll come later。

And obviously this sucks for OLAP， as I said， because in OLAP。

 we're doing largement scans on a subset of the columns for the most part。

 so if I have 100 columns in my table but now my crio only needs four of them。

 well I got to bring in the other 96 columns that I don't need because it's all packed into the single page。

So this is where the column store， the DSM decomposition storage model stuff came along where people recognize that。

 oh， for this different class of workloads， for O that workloads。

 doesn it makes sense to store everything contiguously instead you want to break up the tuple based on its attributes。

 then now you can store all the data for that attribute across multiple tus contiguously。

And that's going to open a bunch of advantages for compression and other things that we can take advantage of。

And when only we can do this because we' again we're mostly running reling queries。

 So we're not worried about how to do incremental inserts into our database。

 if someone weigh certain new data， know again some systems will handle that but oftentimes it'll be like a bulkload of like here's a bunch of results。

 a bunch of data we've gotten and then you don't have to worry about incremental updates。

RightBecause again， if you had to do a transaction and update this one record that had 100 sorry 100 attributes。

 if I'm doing the decomposition storage model， I got to update 100 pages at least and write them all out transactionally and that's going to be slow that's going be terrible。

So we don't have to worry about that。These file sizes are going to be typically larger。

 hundreds of megabytes now within this file will break it up。

 this is the row group stuff that you read in the paper。

 you'll break it up into smaller chunks and identify which of the pieces of the file actually need。

 but the overall file itself could be quite large。So just give an example of what this looks like。

 say we have a really simple table， three attributes， and six rows or six tuples。😊。

So what we're going to want to do is we're going to store all of the values for a given and column all within a single file。

 there'll be some metadata header at the front that maybe tell us additional information like what version of the data system we wrote this data。

 any additional statistics like the Z mapap stuff that we want to store for that。

 there'll be a null bit mapap to keep track of which of these attributes are actually null because we need a way to represent that。

But again， we'll just store a separate file for each of the three attributes。Now。

 we'll see why we need to do this in a second。 but we're going make sure that all the data we're storing has to be fixed length。

I'm going to think guess why or knows why from'm Le semesterster。

So you can compute the offsetSo you compute the offset。 So that going back to the stitching thing。

 if I need to get for the for row 0，2 plus 0， I need to get its data。 and I'm processing。 you know。

 I'm at this position here。 I know how to do simple ofrithmetic to jump down to。To。

 to the other column files， I know the length of the data that I'm storing each value。

 and I know what offset I'm math。 So I just do the simple math and jump to the right offset。

But of course， how we handle that for variable data， like strings， which are super common。

 we'll see that in a second。So fix all sets isn't the only way to do this。 It's the most common one。

 Thiss what pretty much almost everyone does， especially if you have a sort of pure OLAP system or an OLAP system that was designed from the ground up to be to run these analytical workloads that has a column store。

The alternative is to embed Tple I。 So for every single value in in a column。

 you have a little prefix that says Im know I'm twople 0，2ple1，2ple3 and 2ple4。

 And now if you ever want to find the corresponding data or attributes for that same tuple across other columns。

 you need an auxiliary data structure， like a hash table that says， okay。

 for this column for this Tple I， here's the offset you want to jump to。

 or at least very least here's the range or you should start at looking for it。Yes。条。We。

I his question is。If if I'm saying everything has to be fixed length， but then you have strings。

 does that mean you can't do this？No， we'll see how this handle it in a second。

 the answer is going to be。Dictionary coding。Because we want to convert anything that's variable length to fixed length。

RightThis is what I。The next one is going to be what I'm highlighting here。So。

Like guess said I'm only bringing this up the bottom one， like I'm saying don't do this。

 I only bring up because there are some systems do it。

 as far as I know it's only done in cases where it was like a row store system and then they added like a little specialized storage manager storage engine and say。

 oh yeah， we also have a column store piece and they need to be able to sort handle need to reuse some of the existing components that they had given a process on column store data so they add。

There these two ideas， but this is what you want to do you want to use the fix length in parquet and workk。

 they're all going be fixed length。😡，And so basically what he asked me was how do I handle barrel length data。

 the answer is going to be dictionary， yes， question。So do you do you thought you running away。

So his question is statement is if I'm doing run length encoding。

 do I still have the advantage of fixed length， Yeah， why wouldn't you？Yeah， so。😊。

We won't tell how to process fun life encod today。 But the basic idea is that you do have to like。

 you'd scan through to know where to jump like， okay， I'm looking for this value。 I scan through。

 and I know that。If I'm looking for a two this offset。

 I keep scanning to I find the run life encoding entry that covers my offset。Yeah， you need to scan。

Right。So say as you just scan through all all the file again， we'll break this in pure DSM。 Yes。

 you would have that problem like worst case the worst case scenario。

 you have the skin to the very bottom because the thing you look forward at the very bottom this is why another reason why we're gonna to use packs because it's basically going to break things up to the row groups so that in worst case scenario。

 yes， we have to scan the entire column， it's early and compressed。But it's only going to be。

 you know， what 10 megs or something like that。 It's not that big。Right， again。

 so we we do use dictionary encoding。 and that allows convert very length data into fixed length files。

 And if you read the paper， you pick this up。 Parquet is very aggressive。 actually。

 on the dictionary encoding。 their en， everything。 even it already fixed length。😊。

ORC only does this for strings， for very long things。

But then it turns out parquet does pretty good still， because theres still。

 you can convert dictionary coding。 we'll in a second。

 it's gonna allow you to convert data that may be in a really large domain down to a much smaller domain。

 And then you can apply additional compression techniques on top of that。And you still get a win。

It seems counterintuititive。 I would want to compress floats says dictionary codes， but。

We found that it actually works。This doesn't solve the problem of how to handle semistructured data in this world because the dumbest thing you to do would be just treat semistructured data as as a text field。

 and have the query engine do parse the Json or whatever it is as it goes along。

 That's gonna be super slow。 Again， we'll see how to handle that in a second。

 Well we can convert everything to columns。And if there's string fields in the values of the NA data。

 the JSON values， again， we'll just dictionary encode that too。

 to treat it like a regular of a column。Okay， so as I said。

 the most Oette queries are never going to access a single column in a table by itself。 right。

 It's very rare to say， like select， you know， select sum you know。

 or average some single column without any where clauses， without any group I。

 without any sorting or anything like that。So I'm not saying that single column queries don't exist。

 I'm saying they're not that common or they're not as common as multi column queries。

So if we do the decomposition storage model， we're restoring single files per column。😡。

Then I'm gonna have to jump through different files。

 If I need to start putting things back together in order to process my query。

 like my where callss might reference four columns。

 Ive got to go jump to those four files at different offsets and go get the data that I need。

So we want a way to get all the benefits we get from having columnar data either term through know through getting better compression。

 We're also doing vectorized execution。 We want all， We still want all that。

 but we don't want the downsides of。😊，Of having separate files。

So this is where Pax is going solve Pax is going solve for us。 So this was invented。 actually。

 I think here。 So this is the paper is from Natasa Alammaki。

 She was the database professor before I was like she left before I showed up she was teaching 721 in 2006 then she left to go to ETFL and I revised 721 when I showed up but there is a paper she wrote in 2002 that basically recognized that。

😊，You know there is this problem if you have a lot of memory。

 then you don't want to pay this penalty of sorry， not that they have a lot of memory。

 They don't to pay this penalty having to jump between these different columnar files to put things back together。

 If you have enough memory to bring in a big chunk of data。

 you can still keep things in a columnar format。 But then now the data that's related to a single tuple will be close to each other。

Right， so again， we get all the benefit of clonear storage。

 but it still maintain the spatial locality of the row store。Right。

So the way this is going to work is that we have our example table before。

 so we're going to horizontally partition our table into row groups and the size of the row group will vary per implementation right for now。

 let's assume that it's some fixed number twos like three tus。😊，Then now within that row group。

 we're going to have a header， of course， that is going to tell us information on what's in this row group。

 but then now we're going to lay out the data for the single column or single attribute sequentially or contiguously。

 and then once we're done for all the tuples in that column， then we jump to the next one。

So we're going to call this piece here within the row group， we're going to call this a column junk。

I think the orc paper calls them or the orc system calls them stripes。

 row groupss and column chunks are what's in parquet， what has used that？

And then once we lay everything out for the first row group， that we do the same thing for the other。

And then in the photo we're going to have metadata that's going to tell us what's in this file， yes。

😡，So what's the reason that we have。Multiple row groups instead of just having different multiple filess。

This question， what's the reason for having different rowgue groups？

Versus having a rogue would be a single file。Yeah， so you could have a right， you could have。

 you could define your like parquet org。 You could say， I want my file to only have one row group。

Right， but then now you basically have a bunch of metadata that's that's very narrow just for that one row group。

 So the idea here is that if I put a bunch of row groups， the right amount。

 again what's probably it's empty complete problem。

 It's difficult to know the right amount of row groups to right the right granularity for the scope of the zone math and other metadata you're maintaining。

That's hard to know。 I guess my question is like what's the benefit of having these multiple within a single file file versus just having like just multiple files So I could have a zoneoo map in the footer the metadata that tells me within my row groups。

 here's the data that I have or I could have it for like you know I for a single some common say the date。

Here's the min and the max value for all the values in that single column。Across all the row groups。

 So why can you have that like the bottom data inside right now， what I'm saying is So now like。

 if I want to go， if I， I'm looking for all the orders from this month and my。

 my files are have been sort of sequentially based on time。Now， I just go read this。

 and I can figure out， oh， this， this thing contains all the orders from 2023。

 I don't need anything in there。 I'm looking for， you know， January 2024。 So I can skip it entirely。

 If I do what you're propossing， then I have to go read this header from every single。You know。

 from multiple files， so just gran to another level granular。

 but again I'm like like what's the right size？It depends， which is a cop out to answer databases。

 because answer a lot of things。 dependss on the query。 It depends on the data。

 It dependss on what you're trying to do。So is the ro group one single a row group when we one4 kilobyte or yeah。

 so his question is is a row group one4 kilobyte page， no， it's going to be tens of megawates？Yeah。

Again， it's the same thing he brought up。 it's the granularity of this。

 right I if I'm storing just 4 kiloB of data， but I have to have this metadata thing in。Then like。

 say the metadata is， I don't know， half a kilobyte or start a kilobyte。

 Then I can like3 kiloBtes of data。in a row group。 And now I'm just basically have a bunch of overhead of there metadata that I don't actually need。

Yes， then when there really is been moment of like you want each like stripe to be like at least one page that you pull in that column。

Like at that benefit are not like pulling in data that you don't need。

A subset of columns that you're  querying over。Your your question is， like， shouldn't the this。

 the size of the column group or the size of the row group be a certain size or what like a single stripe。

 like a single column chunk should be like at least。At least a page yes， yeah。Yes。😊。

So will the Zone map be in the photo of the entire file？we'll cover the zone map in a second。

 but there will be a zone map per row group in this metadata thing。 And then optionally。

 you can have a zone map that covers the columns in the in the metadata。

 This is actually one of the problems of parquet or because that like they added this later。

 A bunch of limitations don't actually support it。😊，So like， it's like in the specs as there。

 but it may not actually be there。Yes。The question is， a row group is random。

 what do you mean like random？The boundaries you mean？We'll cover that in a second。 Like。

 there's a sizing protocol that the that they have for these different formats， they'll say， like。

 I want my ro group to be least this size or this number twos and there's trade off for them for those choices。

Yes， these attributes？His question is are these attributes the same length that cause different chunks。

 yes？Let about that。I think you can actually have different within a row group。

 I think you can vary the encoding scheme you're using。So I think they could be different。

 but since I have my metadata， what encoding scheme I'm using， if I say I want2。 offset6。

 like logical offset 6， and I jump to this row group， I know it's in here。😡。

I use the metadata to then figure out， okay， the size of the attributes for this column is this。

 therefore I can do my math to go find that， so it could be different per row group and something different per file。

But again， I just do the same orthothmetic that I before。 But in the column group。

 they all repeat the same size with the column chunk。Okay。

And I would say sort of his question is be there's a global metadata thats can tell me like what's in in my file。

 how things are encoded。You would think it's essentially the header， right。

 remember the slot of pages of stuff from last semester， that was literally in the header。

 the beginning bytes of a page。 They're putting this at the bottom。I going take you guess why。

He says the size is not fixed， the size of what。So the size of the midday is not fixed now。Again。

 these files are big。And I don't know what the metadata is going to be。 Like。

 what's the Min max value for all the data that I have until I process all the data。Right。

 and then also reason why they're putting it at the end and at the beginning。

 because this comes from the Hadoop world or HFS world from 10 years ago。

 which is the pen only file system。 I mean， I can't make in place updates to the file without rewriting it。

 So if I have now， if I'm bulkloading much of data to generate the parque and work file。

 I got to scan through all the data。 and I'm writing out these row groups incrementally And then when I'm done。

 alright， let me close the file。 the。The metadata， you can't go back and put it back up here because you've already written out at the beginning of the file。

S3 is the same thing， right you can't do in place updates。

 you have to basically overwrite something entirely。

And that would be expensive because then you basically， if I wrote out a 1 GB parquet file。

 I don't want have to go write it back out again， just to update。You know， the metadata。

 So they always put it at the bottom。The， the Zoom apps have actually in the bottom for parquet here。

 again， I think the paper talks talk about that was added。Wow， 2018， 2018。

 that was actually my student at Cloud Air added of that。She took this class。

 and now she's a Ph student at University of Maryland。So there's some connection there with 721。

All right。So。Up until again， 10 years ago， so yes。I at the end of the file。

 do if you're just ripping to the met model。け。What do you need to be？

You just go to the end of the file and bring the last couple of pages in get。 Yes， question is like。

 if it's at the end， how do I start processing the file？ Yeah。

 so the entry point for the file is the footer。So I think the way it works is that the last。

32 bits of the file is the length of the footer you read that and that'll tell you how much back you read to get the complete view of the metadata。

Yes， so you're saying this is kind of file it wass basically similar to an law structure pretty much。

ItsThe question that my saying this is like a log structure of merry， no， why would I say that？

you mentioned the context of。Ha doop and。So a penon means like like in Hadoop。

 the falseom only allows for like， like， open a file and there's a pen bytes to it。 So like that。

 but like Hadoop doesn't know what you're storing。 It just sees bytes。Right the。

This would be like this is not LSM。 This is literally like there's one version of a piece of data。

 Tupple， and I'm just writing it out sequentially as I go。

 but I'm going to organize it in this PAs format。Okay， so。Prior to 10 years ago。

 even the early column store systems， like the verticgos， the green plums and so forth。

They were they had their own proprietary data format， and then I mentioned this last class。

 like most data you think about SQL light， Postgres， MySQL， Oracle and so forth。

 when they put bits down on disk， the format is going to be proprietary to that database system。

Right like the system is designed to rewrite that data。

 Now there are some systems like likeductDB is really good about this。

 they can read SQL light database files， they can be other database files。

 but those systems don't do that， right。And so the problem of this is that since all these different data systems have their own proprietary data format。

 you can't share data across different disparate systems。

 Like I can't take a Postgre data directory files and plop it down。 I let My SQL read it。 Again。

 D DB is trying to be like a Swiss army knife kind of thing。 we can ignore that。

 But that's not not how most systems work。So that means the only way I could get data out of one system and put it into another system is to write a SQL query to dump it out and then convert it to a CSV。

 TSED or JSON XM file， some other format and then。😡。

Then do bulk insertion on for the other Navy system to then convert it into their own proprietary format。

But again， with the Hadoop and the cloud stuff taking off in early 2010s， you had now。

 as I showed in the last class， you had all these operational databases that want to start writing data out so that you could read it into your data warehouse。

 but again you don't want to do this conversion， I just wanted to put things out to my object store and not worry about having to do the additional conversions。

So this is where the， the parane orc stuff comes comes into play because they that's the problem they were trying to solve。

 They're trying to be a universal file format that。That you know。

 one application or some some other thing upstream in your application stack could could generate。

 and then you wouldn't have to do that conversion to be able to read it。

And you would get all the benefits of a binary encoding scheme that you would want in like a column store or pack layout without having to revert it to a text format like this。

 like CSC is the worst thing you can do because now basically all your binary data is converted into ASI characters。

And you got to parse that and deal with that when he load it back in， same thing with Jason。

So the idea is that you would define a spec of here's what the file format is。

 and then whatever system wants to be able to read it could either use an off thes shelf implementation of it。

 which they have questionable quality or write their own。Which， again， of questionable quality。

 right？So this is not it。Entirely a new idea， but it actually goes back to the 1990s in the high performance computing world of the scientific community。

 there was this thing called HDF5 and that means there was 4321。

 there was previous versions to this but five is the current one everyone still uses。

 but this was a binary format to store or compress multidimensional arrays and that you could have whatever random forchan program you had to do processing on the data from scientific instruments or satellite data。

 you could use this universal file format and use it for different experiments。😊。

But this is almost entirely ignored by the database of this community， right？So。2009。

 people recognized that， oh， Hadoop wants to generate a bunch of these files that we want be to use for for different purposes。

 And so the original version of the data format in Hadoop。

 with a thing called sequential sequence files is literally key value pairs。

 like serialized value strings that only the function of the Hadoop code and knew how to process like your application code。

 So there was no embedded schemechema information。 So they replaced this with this thing called Avro。

 And I think this came out of。Maybe Cloudder or the Hadoop project。

 but if this was still row oriented， so even though the column source systems existed at the time。

 Duke was still writing things out and processing data as rows， which sucked。

So then there was another version before Parquet called RC file， actually before OrRC from Meta。

 but then at the same time in 2013， Cloudlyon and Twitter working on Pala。

 they put out parquet and then metata put out OrRC for Apache hive。

 hive is basically a SQL engine or SQL queryery engine on top of Hadoop or Matt produce。

 so convert your SQLqueeryries has been Matt produce jobs is still around today。

You don't want to use it。So again， parque and orca is is the dominant ones。 But at this point。

 they're over 10 years old。And they're still widely used today carbonbon data is an extension of parquet from Huawei。

 it adds additional metadata for keeping track of the schema versions and so forth。

I don't know anybody who uses this other than Huawei。

 the open source version that we tried doesn't work， it doesn't compile。

Somebody's still working on it and an arrow again I mentioned this before。

 this is gonna to be an in memoryory think of this like almost in memorymory version of parquet and it's going to allow me to do change data between different processes over the network or in memory on the same box and this came out of Drmio and from the Pans guy。

So again， for this class， we're going to focus on these two。

And then there's a bunch of other ones I think mentioned in the paper。

 There's an extension or a newer version of orc called Dwarf from Facebook。

 And then there's this thing called Alpha that we've been talking enough about。

 So the next generation one， we can ignore all that。

 We want to focus on parking org because that'' that's what pretty much everyone's using today。

And it's not to say that these formats are the best and this is what every system should be using。

 is's just what。Is what's commonly being used like a SQL the best query language。 No。

 it has problems， but is it widely used and therefore， it's not going away。 Yes， so same thing。

 right Par in orca widely used。 we have to be able to handle them。Like on Huging face。

 you can get native data directly in a parque format directly。

All right so the thing we're going to talk about is when we design our file format is what metadata we want to maintain the layout of the data with T system we're going to support the encoding teamss or the compression schemes we would use for the data itself and then block compression is after I've done the encoding can I run like G zipip or something to compress it we talking about filters and then we finish up talking about the nested data So the paper had you guys read again。

 this is something that I wrote with my former student P student here。

 who's at shinghua and his P student and then the guy that embeddedted Python pandas who was at Voltron he and I have been talking about hey Parquet has some problems because he the event or arrow。

 he worked on some parque stuff too and realized that we wanted to investigate why。

What are the problems in the modern environment for these two the most popular storage formats？

At the same time， unbu us， Microsoft was actually doing the same evaluation。

 same experiment experiments that we were。 Their paper came out， I think。

 in October and ours came out like November。 So like we dodged a bullet。's。

 they approached the problem differently and did different kind of evaluation。

 So they're complementary。 I'll talk a little bit about with them。 But the main。

 the main takeaway I got from them is their findings corroborate what we found in ours。

 So I felt good as a scientist that it worked out。😊，Alright， so the first thing is when again， the。

 the metadata， what metadata we want to put in the in the， in the file。

 So I already mentioned the Z map stuff。And but the basic ideas is for parking network。

 these are meant to be self- describingib or self containedtain file formats。

 meaning everything I need to know to interpret what the bytes mean in my file or be contained in the file itself。

😡，RightAnd as as opposed to like thinking like in a system like bust or Postgres or MySQL。

 you have a bunch of files that keep track of like the catalog there's blocks and the catalog keeps track of the scheme of the tables。

 what the types are and so forth。 and then you have pages for the actual data。

 So in order for me to understand what's in my data pages。

 I got to go read the pages for the catalog。Oracle is the only system that actually packs everything within the page itself for like disaster recovery。

 So that way， if your oracle database gets destroyed your disc gets destroyed and you can recover some pages。

 you can still interprettert those bytes because everything you need to know what are in those bys。

 what those bytes mean or actually in the page itself。

But then there's other limitations of an Oracle， like you can only have 1 thousand00 columns in Oracle。

Not just because they' self contained， there's other reasons why they had that problem。Again。

 the bottom line is everything we need to know in the file is in the file itself。

 we don't need to go read some external catalog or external data。

And so we'll keep track of the table schema and the way they're going to do this in is to basically serialize。

 heres here's my columns， there are this type and this size and so forth and additional annotations about them。

 And then within the row groups I keep track of like how it's being encoded so that when I read the file。

 I know how to then process this bytes and put it back to its original form。

never hear used thrift or Phototo buff？One few my put above is from Google Thrriifft is from meta。

 sorry， basically again， you define like a schema almost like like a great table statement。

 you define like here's my here's my columns， here's the types and so forth and their names。

 and then they have a way to then generate a binary encoding for what that what that schema actually is。

😊，And so they basically just piggyback off of this， serialize the bytes。

 and then embed that in the file and then metadata。The big problem is going to be， though。

 if I have a really wide table and say I only want to learn about two or three columns of 100 columns。

 I have to decsialize the entire protouff or the threat message to convert that。

So that's gonna be a big problem for these file fls as well。

 There's newer versions of like there's better versions like flat buff flat buffers from Google。

 there's other， there's better versions of these things。 but at the time。

 this is what this is what existed。 and the file flus carry carry with that legacy。

The row group alls in length， we talked about this again。

 this is going to give us a direct to tell us how to jump in the file to find the beginning of each row group。

 and then there'll be some basic metadata like the number of two bowls that I have in each row group what the zone maps are potentially。

And that can use this information to determine whether I need to even read the rest of the file。

so the format stuff we've mostly already talked about， we're going to use packs for this。

 and then we're going split it up based into row groups and that'll contain one or more column chunks and the question has come up is like how what size of the row group should we use？

In the case of parquet， they're going to use just on the number of tus you that you have。

 and you can change this you can specify as you're creating the file。

 the guy I want my row group to be a million tus or 10 million tus or so forth。

 But it's always based on the number of a number of tuples。OrRC takes a different approach。

 and they specify it based on the size of the data。So the default， I think， is 250 megs。

So what are some pros and cons are about these？We already talked a little about this， yes。Massive。

Yes， he if the tus are massive， we're like， if I have a lot of attributes。ignore like storing blocks。

 if I had to save about 10000 columns。Then a million two bolts with times 10。

00 columns it can be a pretty big rogue group。So what happens in that case？Why is that bad？

Well even fit on storage。😔，AtNo point， sorry his his statement is。

Will even fit in your storage at no point this semester should we ever say are we going to run out of disk right I mean S3 for our purposes is infinite like long as your credit card keeps you know long as Amazon keep charging your credit card。

 you're never gonna run out of storage right and if you're at the point where like they start running out of storage。

 they will call you and be like， hey， who are you， what are you doing right？Storage and infinite。

For us， yes， could it be the data split across multiple pages they say they could be split across multiple pages。

 that's assumed， right， like page size of 4 kilobs and hardware， but that's assumed。

Your zone map become less helpful。 He says your zone become less helpful。 Yes， that's one。 Yes， like。

 again， the granularity， the scope of the zone map is so large that like anything like anything I look in there be like。

 oh yeah， your， your value range for this number is 0 to an infinity。 Great， Like， that's useless。😊。

Missing a key thing， one more。I had to bring in the entire row group。😡。

So if I have a massive row group， then I'm just going to have this huge thing of memory that I got to bring in in order to start processing and understand what's going on。

Right。The benefit though， is that I can size this in such a way that I'm guaranteed to or at least I can maximize my chances to do vectorized processing that I'm always going to have enough data to put in my SIdy lanes or scan across have multiple threads process and paralyze it。

Yes， when you're pulling for S3， would you be putting the entire partK file anyway。

 David is if you're pulling for S3， would you be pulling the entire parque file， No， so like again。

 in S3， you can do byte offsets and length。So I jump get to the header， sorry， I get the footer。

 get the metadata。 I know what row groups I have。 and then if my Zoom appss are selective enough。

 I can then say， oh， I don't need this row group and this row group。

 let me go get the by ranges that I need。When do using work？各位来 the心理。

When would you not have enough value？It question when would you not have enough data to put in your skin these so again。

 say if I have a really wide tuple？😡，With a lot， a lot of attributes， then I only have。

 this is an extreme example。 I only have four tus in in my row group because it's just so huge。 Now。

 maybe Sdy lanes is maybe too fine a greater laity。

 but just think if I'm processing those multiple threads。I don't think again， think。Again。

 I'm jumping ahead to what we're talking about the semester。 But like， don't think in the bust world。

 where like one thread is running this one operator go gets one page for memory and then does whatever wants on it。

 Think of like， I'm gonna have some other。Pce of the system。

 the I scheduler or whatever you want to call it it's going to say I need this file。

 you go get the blocks in and then maybe some coordinator figures out okay， yeah。

 we do want to process this。 And oh yeah， it is。 It's half half a gig。

 So this thread process the first half。 the thread process the second half。

So I wantna have enough work for everyone to do。 Yes。

 the decision on like whether to use like number of two pools or physical storage size like its efficiency is predicated on like the size of the two pools。

 Yes， like people like what like like hybrid systems where like you choose which one you use based off of like what data youre。

Like specific。So his question is， it？Again， the cop answer in database is it depends。 So clearly。

 it depends on sometimes this is good。 this is good。

 has anybody try to do a hybrid solution you support both。

 Well that's going be another theme we'll see as we go along， although a a short in time。

 the increasing the complexity of the file format means that when you're actually processing tus。😊。

Then you have to like， you have branch predictions because now you different codes consider。 Plus。

 there's the engineering complexity now to support both。

So Parquet does this or does that we see there's other things too like bringing for like a transactional system。

 should you flush the log buffer when you've written so many transactions or when the log files a certain size or when you've run for a certain amount of time。

Yeah， those pros and cons， all those different choices， but from the engineering perspective。

 it's just easier to pick one， or should I use two phase locking or OCC。Yeah。

 there's times we went one versus the other， but it went to just one。

 it's so hard to build the whole system， why avial complexity。Yes。

Could you just come back to what's the mean disadvantage？All the road group in。The first。

 not being able to stitch it together is one。His question is why is not being able to put a row group entirely memory a bad idea？

😡，So I got to go fetch it from somewhere。 I bring it to the node that's going to process it。

 I don't enough memory for it。 Where does it got to go。To disk。

to process the entire group His statement is that could you。

Could you break up the ro group and execute it incrementally， Yes。

 but then it's another request you're get getting more data as they need。はい。

So this is just a diagram from from databricks showing sort of tutorial what parque looks like。

 And you can sort of see in all things we talked about here。 Here's the footer。

 There's these row groups that are numbered。 And then within them， you have a column chunks。

 And within the column chunk， you would have。😊，Additional page metadata for the encoded as and so forth。

 right， the the exact distinction of how we're gonna lay out those internal parts versus parking or。

 I I I I don't care that much about。 But again， the idea that like。

There's as higherarchical nature to the file， and we can store additional metadata as we go along。

And the right size of each part again， depends on a bunch of different things。

All right so we're at CMU and they love T systems in the PL group。

 so we have to worry about that about a little bit， so TS is going to define in our file format。

 you're shaking your head yes。😊，the type system is going to define how we actually can store the types themselves and what are the bytes going to look like so there's the physical type and that's the lowest level representation we have for a given value and for this we're not going to anything special for the most part for integers and floating point numbers we're going to use the I2 at least 74 standard and that specifies what how our hardware should represent the data you can think of like if a declare integer in 32 on C slot。

B 74 standard that's what I get， because that's what the hard rate gives me。

 We'll talk about strings in a few more lectures。Again。

 there's some tricks we can do to speed that up。 And then the logical types will be built on top of the physical types。

 and it's basically define how we would map some logical type to a physical type。 So for example。

 if I want to store timestamps what is a timestamp。

 It's just the number of secondsd or milliseconds or nanoconds from some starting point。Well。

 that's just a number。So I could distort that as a physical type as an in 64。

 and then I have a notion of a logical type that says how to parse the bits within that physical type。

So parque and orRC have different complexity to their type system。

 and then that determines how much work you have to do upstream is the thing actually generating data for these file formats or actually consuming it。

 how much work you have to do to have to interpret the contents。

So in parque they have the bare minimum of types， right， they only have n32 in 64 and 696。

 and then the 750ier standard and then the byte arrays and then they don only have strings because you would interpret that as a byte array。

 right。So it's interesting they don't store。You know，8 an in or 16 bit ins， right。

 So if you declare I want an8 an in or 60 minute in， but still going to sort as a 32， 32 bit in。

And the reasoning is that， okay， well， yeah， there's a bunch of zeros in my bits that I'm not using。

 well a lot of this compress out。And that reduces the complexity of what they have support。

ORC is much larger。They have， you know， all these various different types。 Some of these are logical。

 Some of these are physical。 They don't really make distinction。 But you know， they， you can find。

 you know， way more things than you can with than in Parqueette。

I'm not saying one is bad versus the other， it's just how they chose the implementent things。

Al right， so now the encoding seems going to specify for a given physical and logical type。

 Yes because if you have types you can do different question is why isn't orRC better because if you have more types you can do more things en codinging them？

😊，So the par AB will say you just represent as logical types。

And you extend the file format it that way。Have've ever taken tightism class。

 this is my understanding。啊。All right， so again， the coding schemes can specify for the physical logical types。

 actual bis themselves， how can we actually store them for contagiguous or related tus within our column chunk？

😊，And the paper talks about a bunch of different schemes that we've covered in the intro class。

 I don't think I mentioned frame a reference in intro class。 it's basically like delta encoding。

 but instead of having like in Dlta encoding， it's like what's the difference between the value before you you pick some starting point like maybe the min value of a column chunk。

 And then now you're restoring the delta from that global value。😊，Right it's sort of variant of。

The variant of Delta encoding。 And then there's partial frame of reference coding。

 which I think the paper mentions P 4， as basically for any if you have any outliers that would wreck your encoding scheme。

 they have a way to handle those separately。 we can ignore that。

The one I want to spend time talking about is actually dictionary encoding because one。

 this is the most common encoding scheme that most data systems support。

 thats where you get most of the win for getting compression and for the different schemes here vary not in how they implement it。

 but more like when it's triggered。Like in orRC， they're very aggressive using RLE。

 like if they see three or more particular values， then then RLE kicks in。 if you're in parquet。

 it has to be8 or more and you can't change that。 And so you know if probably by dictionary encoding because because you can then take the results of the dictionary encoding。

 the compressed column and then apply all these other things on top of it and get it compressed even more。

dictionary codingd。 again， this is the same thing with in class。

 The basic idea is that we're going to replace values that that occur often in our column with some smaller fixed length dictionary code from a smaller domain。

 And then we use that at run time to figure out， okay， if I see this dictionary code in this column。

 I can do reference the dictionary to figure out what what the actual value should be。 Again。

 this is how we convert very length strings of very length data into to fixed length values that we we can store in our。

😊，A。In our columns， it means the metadata is going to be now arbitrary length because all the strings that were variable length in our column are now being stored in the dictionary。

 which is stored in the header of the row group。So the code dictionary codes could either be positions within the dictionary and therefore you have to maintain a hash table to figure out how to find that position or in the dictionary。

 or we could do offsets within the dictionary， assuming it's like everything contiguous bytes。😊。

We can also optional sort the values in the dictionary and that'll help us get some additional benefits for during compression in some cases。

 and then we can further compress the dictionary or encode in columns to reduce them even further again。

 using RE and other techniques。So in the different formats， they handle。

 know they have to handle the case when the dictionary becomes too large because there's too many unique values and therefore I'm losing all the benefit of dictionary and codingd。

 Like if I have my my column is just monotly increasing values from one to a billion then it doesn't it's kind of stupid to store dictionary code for。

A billion twopos that are all unique because I'm going have a billion dictionary code。

 So now I have the original column that's diction encoded with a billion unique values。

 and I'm storing the billion unique values in the dictionary。 So I'm double the size of it。

So they have various techniques that figure out， okay， this is not working out。

 I don't want to do dictionary encoding。So in case of parquet。

 if the dictionary gets larger than one megabyte， then they just stop。

 and then everything comes after that point it' just stored as regular the plane encoding。

 original values。In the case of ORC。They compute the number of distinct values ahead of time。

 but basically they have a look ahead buffer where they can say。

 let me look at the when I'm starting to write out a chunk of data。

 let me go look ahead like 512 values or 500 values。

 go figure out whether there's enough distinct values。

 And I think the rest of the data is gonna look like that and doesn't make sense to do dictionary coding or not。

If they get it wrong， then they do the same thing as barquet。

 they basically stop encoding and just store data in this native format。

So here's a really simple example。 I have some column of a bunch of strings in it。

 if I'm doing an unsorted dictionary， then the values of the strings that I'm trying to compress will just be in the order that they appear as I'm scanning through the column and I can either store the position in in the dictionary again so the first one here was was William so at offset one。

 then I position one I would find the actual string that I wanted or I can store this as an offset。

 So if I take treat this as bytes， so I know that if I look at my dictionary。

 I need to jump to the seventh byte and that's going to tell me where the starting point for for my entry will be。

😊，And I don't need to maintain a hash tablebook。Yes， his question is。

 what are the advantage disadvantages？Hashable， right， So we'll see arrow later on。

  Ar does it this way， because then you don't have to serialize the hash table。

 they're going to presort everything and then jump into it more easily。Obs。As it in its index。Oh no。

 that doesn't work。yep， okay。And you have a sort of dictionary， again。

 get all the dictionary bad ahead of time， and then you sort them。And then again。

 it's just like before you you have a position into the dictionary or an offset， the bite offset。

 right？But you can kind of see now like here in this example here。

 like I have Andy repeated a bunch of times。 Well， one is now I've heard things to， to。

 to integers in my dictionary codes。 But now I have repeated values。 So then I can take this and say。

 oh， I have， you know， four twos in a row。 Let me compress that with R LE。Or I could do， you know。

 delta encod or partial sort frame reference。 where now I just say， okay， these are all integers。

 They're all in a small domainca I only have four different unique values in my dictionary。

 I can then compress these things。Yes。When we talked about like doing compressing。

Variable length values in like a single column we talked about like the way to do it was like dictionary compression。

 but what happens if like the number of distinct values like extremely high for like variable length strings do you like。

Like indirects to like somethingiliary Yeah， its question is， okay， So if I。

 if I recognize that I have a bunch， I have bunch of random strings and I can't do。

 I can't do a dictionary encoding。 But now have bunch of very like data。 How do I handle that。

 You have auxiliary data。 And then now you're just throwing the offsets into that lob。😊，Okay。

So a couple of design decisions we have to make is what data we actually want to compress with data encod。

 I think we're running short time。 Sorry， it's a lot we way to get to。 Sorry， So， as I said before。

 perquet， they compress everything floats， integer， strings， dates， They have， again， smaller types。

 They compress all of that in orc， they only compress strings。😊，And this seems。

This seems like common sense because。Most of the variability you can see is or the randomness you will see in values are going to be mostly or sorry。

 the repeated values will be in strings， not in。Not in integers and floats。

But when we did our analysis， it actually turns out to be theway， sorry， the parquetway is better。

Next question is， what do you do， Can you compress the encoded data， So parquet is pretty simplistic。

 They will just do R and bit packing。 Again， bit packing is just saying， oh， I recognize that。

My dictionary codes are 30302it integers， but my values are within0 to 20 so I can use 8 bit integers for that or even some smaller amount。

 And now my column gets compressed even further。 I if I have repeated values， I can do RLE on that。

 But again， they RLE only kicks in if you have eight or more values。In OrRRC。

 they have a bunch of different things you could do RE delta encoding bitpacking frame of reference。

 and they basically have a greedy algorithm again they look ahead in the buffer。

 they're trying to figure out what the data looks like。

 run some heuristics to figure out which of these approaches is the best it always tries to use RLE first。

 and then if it can't then enjoys Dlta then if it can't do that。

 it uses either bit packing or frame of reference。And then another design decision is the dictionary that's being generated for these encoded values。

 do you expose that to the outside of the file format or the library that's prosecuting the file？

Let me tell guess why you'd want to do that。So if I go back here。So say I want to look up。

 find all the。My query is。My query is。Sck count from the table where name equals Andy。So。

If I can then look at the dictionary。😡，I can almost as like a Zoomac。

 I see whether it's anyze mean there or not。Right， or select more simple。Whats that？

sortctionary a range dictionary。 It's a range query else， either we have a sorted dictionary。Yeah。

 you want to count all the unique values within a given range。

 I could do that by looking at the dictionary， as' another example。So parque or do not do this。

 So in the library implementations， when you say scan some column。

 you basically get an iterator to their library， and that's going to give you back the columns that you asked for in their original form。

So underneath the covers， the library is doing all the decoding depressing for you。Right so again。

 that means that you can't really push down predicates all the way down to the lowest level of looking at the file itself。

 you do have to do whatever whatever the library spits out back to you。

So this is been recognized as a problem， So there's a paper we're not going to cover from Google for a system called Prisilla。

 This was developed in house for YouTube to process do analytics。

 but also serving data online manner， which we don't want to care about right now。

 but there's this little blurb here they develop their own file system or so file format instead of using or and parquet called artists and one of the advantage they talk about in artist is that oh they actually expose the dictionary to the query engine so that you can do the predicate pushion that you want to do。

Right。So this is something as I mentioned before， this is the known problem proque work。

 and then the newer stuff that people are looking at once solve this problems that's exposed to you what the dictionary is。

Becauseuse then now you can do， you can do evaluation directly in compressed data by compressing your predicate and then comparing your predicate versus the compressed data rather than decompressing everything first。

All right， next thing is do block compression。And this is basically taking off the shelf， naive。

 general purpose， compression algorithm that just take the blocks of the row groups and just run that and compress it。

Right， and the the paper talks about， parquet and org， I think the default is snappy。 the modern。

 the best question I going we want to use right now is actually Z standard from Facebook。

 There's a newer version that's not out yet。 It's called something different。

 That supposedly is better， but。Parkane or， again， they come with snappy because that was the thing back in the day when those pho fires are invented。

So there's this the things you have to consider whether you actually want to do this or not is whether you're willing to pay the computational overhead of compress or decompressing the data the blocks when it comes back。

Even though it's already been encoded with one diction andcoding other schemes like you can still get some some compression benefits。

 But now it's gonna to make processing the data much slower because you have to do this extra step to decompress it because these are opaque compression schemes。

 meaningan if I run something through snappy or or Z standard， the bytes come out。

 the data system doesn't know what those bytes mean。

And I can't jump to arbitrary offsets within them to go find data I'm looking for。

 I got to decompress the whole block。And again， this made sense in 2013， 2012。

 when these file formats were designed because disk was slow， net was slow。

So if I can reduce the amount of data， I have to go read know， from some some local stores。

And then bring to my memory， then I'm willing to pay that CPUU cost。

But things have changed a lot now， the CPU is actually one of the slower things。

So this actually doesn't make sense anymore。はい。So the additional me we can keep track are the filters。

 so the only two type of filters that they would have are zoneoo maps and balloon filters again。

 even though the paper calls it a page index， what's the difference between an index and a filter。

An index tells you where something is and what if it exists。

 a filter tells you something could exist or does exist。 doesn't tell you where it is， though。

So Zoom app is going to say， here's my Min max values。

 I'm trying to find something within in a given range。 if it's in that mini Maxax range。

 then it exists， but I don't know where it is。 I got to go a squ scan to find it。

Whereas a B plus G would say， hey， you're at this offset right， which we don't care about。

So we were already to write zone maps。😊，And again， my default par or're going to store the Zoo maps in the header each group。

 you can store it in the file level， but I don't think that's on my default。

And then for bloom filters within each row group， they can keep track of whether a value could exist for a forgiven column。

Again， a B filterer is a probabilistic data structure。

 it can tell you definitely that something does not exist。

 but it going to tell you that something may exist。

 that you can get false positive but not false negatives。Yes， does it matter value？

The question is why does it matter whether values are cluster for a bloom filter？😊，Because the the。

How to say thisす。Yes，'s a good question。I don't know worry about that。ItDoes doesn't matter what you。

Because you hash it and it's scattered。Multiple bloom filters like in different parts of。

So if you have a cluster then。Goud Google around。You know。This might be this might be for this。

 right， yeah， sorry this is a type of this should be for this Z map。

 It matters if the cluster because now the range will be much smaller and I can throw things out。

 right if it's 0 to infinity， then that's a useless zone map。 Yeah， sorry， this should be for this。

 Thank you。 real quick。 the slip filter is basically a way to instead if your bloom filter so many so many bits instead of having your hash functions look at any possible number of bits。

 you basically narrow down to a block of subset of it。

 And so and that means you can bring within a single cache line。 Well cover cacheline stuff later on。

 But like a way to just reduce the keep everything in like L1 to run as fast as possible。😊，All right。

 this part's a tricky。 I'll do I can on the time， but the nest data structure is also really important。

 We'll cover the Drreemmel system later on。 But there's this paper from from。I think 2011。

2010 about the system called Demmel， which's a precursor to what it is the Drmel's the internal name for BigQuery。

 So we'll read those papers， but they talk about how back back then that like Ive Google when they were building Dremmel。

 They had all these applications generating these protocol buffer data that's all nested and semistructured and inconsistent schemas and they needed a way to efficiently process them。

So the Dremmel paper talks about using this technique called a record shredding。

 which is mentioned in the paper you guys read， and this is an alternative considered a better approach to what orRC does and other systems do call length of presence encoding。

So we can cover this again later if necessary， but the basic idea with shredding is that。Again。

 instead of storing the the semistructure data that I have as a single bb in in my as， you know。

 a blog column that then at the parse every single time I want to do processing on it。

 I'm going split it up。So that。Every level in a path is now treated as a separate column。

AndNow I can rip through those columns and say， you， if I need to find like， you know。

 for a given field in my my， my Json file， does it have this attribute set to a certain value， Like。

 I can rip through that column and find it without having to parse everything every single time。

So the idea with shreddings is that。Instead of keeping track of the explicit hierarchy of a tuple of a document for a given Tupple。

 I stored some repetition and a definition column that tells me whether this thing exists for some tuple at some offset for as I'm scanning along。

RightSo the basic idea is that say I have some protocoluff definition like this。

 there's always a document ID at the top level， so I have a separate column for that and that's always going to be there。

 And therefore the repetition and definition is always zero because it's the only one integer and one doc ID per document。

 there's no repetition and then there's no definition saying that there's other things I need to look at from the other nest of columns。

😊，But then you see here that the， within the， the， this name field， I can have a language。

 I have a code。 I always have this optical string URL。

 and then I can define now a separate column for all these things。

 And this is telling me the repetitions like for how many tuples after。

 after the run you're looking at。AmDo I belong to the tula or original tula that was created at the top of the hierarchy？

I'm going this to this way fast。 we can cover this more next next next class。 The basic idea is。

 again， the I have some additional metadata， these additional comms I'm using。

 keep track of that I can use to reverse and figure out what where I'm at in my hierarchy。

The easier one is is the length of presence。 This one basically says that。

I'm scanning through my document， I'm generating the data that if a tuple doesn't have an attribute。

 then at a given level， then I'll just set its presence to false and leave a blank space。

 so I'm always putting in blank spaces for optional data to know whether this given tuple as I reconstruct things exist or not。

And that way I can just do the offsets and say， okay well。I know as I'm processing along。

As I scan through， you know how to reverse use the presence to tell me reverse back to where I'm looking for because the offenses are going to match up again。

And butchering thats going me through fast， but basically again。

 the main takeaway here is that I can split things up based in the past in my JSON document and then run all the encoding compression stuff that we did before。

finish up quickly， I'm gonna to show one experiment from the paper you guys read what we basically did was rather than just looking at synthetic data like from TPCDS or these other benchmarks you guys are gonna see in a bunch of papers and the Microsoft people guys used we said。

 okay， let's go find bunch of real data Let's go find random parquet files or random data sets。

 load this up in parquet in org。😊，And then understand are the design decisions that these file formats make are these good for real data。

 right？So and I said， there's a bunch of par or file or sorry not work。

 a bunch of parque files you can find on GitHub on the internet through Hging F。

 we basically download a bunch of these things and then loaded it up。And so for our evaluation。

 for the most part， we're going to usearrow superfl implementation of Parque and org。😊。

Even though parking or the original file library， the support libraries to process those files and create them。

 it's all written in Java because the Hadoop world wrote everything in Java from 10 years ago。

 You know， we wanted to have the best performing implementation you could have。

 So we use C plus plus the problem is like。The the file specs for Per and north。

 they have all these new things that they've added over the years that are defined as optional。

 like the page index for the Z map in the footer is optional。

And so the various implementations of these formats are sort of these processing libraries。

Some of them implemented things， some things didn't。

 And then there's just the implementation of things that are required。 How。

 how high performance were those。 And so in the case of Parque and or， when we looked at like。A。

You know， like stuff and rust and other imations， they didn't have Cdy support or like parquet was really good。

 but org was really crappy。 like it was really hard for us to find like a sort of true apples。

 apples comparison between these different formats。

Because everyone just sort writes their own thing over the years。All right。

 so the first question we need to ask is， okay， well， how well do these things actually compress？😊。

And the X axis is just showing multi different workloads that we generated for based on real data sets and see you see that for the most part。

 parquet is better for the logging and the ML workload than over parque。

 like because you want lower is better because these are these data sets are mostly comprised of floating point numbers。

All the weights from some M model they're all floating point numbers。

 And because parquet judge dictionary encoding for floating point numbers。

 you actually get a big win。 Again， that seems counterintuitive。

 this was surprising to me that like floating point data actually compresses really well through dictionary encoding。

And then the。ORC is going to do better for the classic workload and the geospatial workload because they mostly contain strings and parque sorry。

 OrRC is more aggressive in compressing the dictionary and codes。

 It has that four different schemes that can use after you've already done the dictionary encoding。

Allright。 So， so the file size， you know， these aren't huge wins。

 These aren't mind blowingly different。 These are， in my opinion， the margin of error， right。

 It's not like one's 10 x larger than another。And he having just said， storage is infinite。

But now when you actually run the queries on these things。

 simulating what an actual query engine would actually do for scans and range scans or full switch of scans and then partial selects and point queries。

 you see parquets would be faster because。😊，It's going to mostly use bit packing and for the。

For some of these workloads， there isn't a lot of repetition that are for contiguous values。

 There's repetition within the column， but it's not like you see 1，1，1，1 over and over again。

 So R doesn't doesn't have a big win for this because again。

 the only R only kicks in in parquet if there's8 or more repeated values。

And so OrRC is more aggressive for R LE。Again， three or more。

 But the problem is when you use rung length encoding， you can't vectorize that very easily with SD。

And I don't think the error implementation of the or processing library that we had。

 none of that was vectorized， so we basically left doing CD operations or CISD instructions on columnar vectorized data。

RightThe other thing problem we saw with the case of orc， and again。

 this would be a recurring theme throughout the entire semester is that the additional complexity of supporting four different encoding schemes for the dictionary codes or dictionary compressed columns is that at runtime as you're to written through the column。

 you got to keep checking， okay， for this column chunk， hows it actually being encoded？😊。

And then now you have this branching in your code to say。

 if I look at my head or it sets in encode it this way。

 then I want to use this this function to decompress it if it's this way use this other function and all all that indirection or conditional clauses causes branch mis predictiondiion in the CPU。

 which and again the modern architecture with a superscalear CPU architecture is terrible。

We' you got to flush the pipeline and pauses and all that garbage right， So for that reason， parquet。

 because it's much more simple。Works way better。And we'll see in some cases when we talk about sequential scans and actually applying prediicates。

The stupid thing of like just always applying the predicate。

So always copying the tuple as like always copying the tuple into your output buffer。

And then apply the predicate actually works faster in some cases， then checking the predicate。

 and then if it matches， then put it in your output buffer。

 so always copying seems like be the wrong thing to do。

 but on super scale of CPU use when everything's in memory you trying to rip through as fast as possible。

 turns out to be the better choice。And this is why the compilation。

 the specialization stuff we'll see later on is going to help us as well because now we don't think like the giant switch calls that says if I'm in 32 through this。

 if I'm floating point do that， which again if you ever look the bust code or a postcards and all that。

 that's basically what it looks like when they process types。😊，So if you can specialize all of that。

 then you avoid that indirection。 So that's why parquet simplicity is， is going to help it here。

I'm well over me finish quickly。Main takeaways of this。 diction encoding is effective for all types。

 not just strings。 And again， to me， this is surprising。

 The the encoding scheme is actually is better for modern hardware。 As I just said。

 And then because the hardware landscape has changed so much。

 where network has gotten so much faster。😊，诶。Then diskIS has got much faster too。

 then we just want to avoid using snapping Z standard entirely。

The the sort of native encoding schemes or diction encoding， R and all lot， that's always me better。

I've already said this horrors changed and then even though they's been widely successful。

 they're used everywhere， there's a lot of things that are missing in Park and North。

 they didn't consider when they first designed these things。

That would help us if you want to process OLAP queries， so there's no statistics。

There's just zone maps and tuple counts and bloom filters， no histograms， no sketches。

 nothing about what's inside those columns that I could use for。For cardinality estimations。

 and I query optimizer。I can't incrementally decsize the schema， I have 10，000 columns。

 I got to decsize that proto buff thing at the very beginning， all at once。And then as I said。

 there's a bunch of implementations and pick， whatever programming language you want。

 there's a parquet library for it。But like it doesn't they're all， I'm saying they're all garbage。

 but like they all， all none of them support exactly what's in the spectrum。Even the job one doesn't。

Okay， so next class， you're going to read fast lanes。 We'll cover better blocks。

 These are going to be sort of modern encoding schemes that。Go beyond the things we talk about today。

 and that's going to be really designed for modern hardware。

And the fascinating one is W is basically saying，y if you don't put things in the order that they in memory in the way that they're found somebody inserted them。

😡，You knowNot even sorting it， you store things a certain way that because you know it's being processed with Cdy。

Then you can get much better performance。

![](img/0e84ca3d38a5043bfbcc5c854cdb4e91_5.png)

It's pretty wild。Okay， any last questions？got a bounce to get the 40 get a quick take system and you'll be picking up models ain't no puzzle because more man of telling the 40 young got Thor can。



![](img/0e84ca3d38a5043bfbcc5c854cdb4e91_7.png)

Stpped the six snacks on the table and I'm able to see St I on the way。

No short with the cross you know what got them， I take off the cat but first I tap on the bottom。

 I about three and the freeze it so I can kill it， cat full with the bottle baby whoops still feeling it because they nice and says they' pain I way you drink't get down with the guy in my head。

Take back the pack of th， and go to some no for trigger to the suns。

 Billy De the silly chief to tell him weak guys， be a manic kid the can of save time。

