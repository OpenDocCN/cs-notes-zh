# 卡耐基梅隆【中英⚡未来数据系统研讨会系列｜Fall 2025, Future Data Systems Seminar Series】 p01 P1 An Extremely Technical Overview of How Apache Iceberg Planning Actually Works -BV17pidBkEzr_p1-

![](img/659c32495e67d18c25a0a73fc678b54f_0.png)

But just want for my peace that pass God bless a friends。

It's time for Carnegie Mel University's future data system seminar series is made possible by let's get's a new semester and we're super excited today to kick it off with Dr。

 Russell Spitzer who is a principal engineer atflake working ice the seminar series this semester is about ice and related systems in the understanding how how these systems work and how they're all put together how are using them we went and got one of the main guys working in Russell we appreciate him for being and also appreciate him doing this with his wife impending second child in days so we appreciate him taking time out to talk about us database that's how important are as always if you have questions for Russell while he's talking。

 please unmute and you are and feel free to ask questions at any time and that way Russell。

s not talking to himself on Zoom for an hour again， Russell， it's a huge day you here。

 Thank you so much the forward jurors go for it。Yeah。

 well welcome everybody hi welcome to an extremely technical overview of that how Apache iceberg planning implementation actually works subscript in Java I'm only going to talk about the Java implementation right now。

😊，And the reason that I care so much about this is that this is a really crucial problem and it's something I spend a lot of time thinking about。

 But before we get into the details of that， a quick overview who I am。

 So I'm one of the Apache iceberg PMC members， if you're not familiar about how Apache about Apache projects work。

 the PMCs， the project management Committee。 So it's basically the people who have a vote in the direction of the project。

 I'm also a member of the Apache Polariis PMC， which is the same thing。

 but for incubating Apache projects， I've contributed to a lot of different Apache projects over my career。

 I currently live in New Orleans and I work for snowlink。😊，And like I said。

 the reason we're all here and the reason why planning matters is we want to read less data。

 regardless of whatever optimizations we figured out about vectorized execution engines。

 about crazy shuffle algorithms， whatever we can do will never beat out the fact that the fastest way to do a query is to read as little data as possible to solve that query。

 and we've got a bunch of approaches to doing that。

And the quickest one is to use metrics that are associated with your files to try to determine whether or not a file is relevant to your query。

 So for example， say I have a file Now there's a lot of different file formats out there。

 but almost all column file formats like Apache parquet have these metrics at the bottom of their file we'll basically say in this file I have several columns I have some schema and those columns have min and max ranges。

😊，And with that information， I can then decide whether or not I can I have to read a file based purely on those ranges in the query that I'm trying to run so。

For example， if I want a query where x is 2 and y is greater than 4 and Z starts with BA Z。

I can check the metrics in the footer of this parquet file and basically say， oh， well。

 two could possibly be in this file because it's between zero and 10。

Is y greater than 40 in this file。 No， never gonna happen。 I know for sure。

 I don't have to read this file now。 and then just for good credit。 you know。

 can a file or can a row that has bas starting here， Well， it can't because Z has between A and F。

 So there's possibly a B A Z string somewhere in there and I can do this for a whole bunch of different queries like if I have an in clause。

 I can basically play the same game， you know， if x is in 4，24 and 30。

 even though I know 24 and 30 aren't possibly in this file， I know4 might be。 So I can say， yeah。

 potentially I have to read this file and actually check to see if that row is there。😊。

And just one more example， you know I can say x is less than 50 and z's donut。

 both of those could possibly be here because x less than 50， well0 and 10 are all less than 50。

 so possibly have a hit there and Z equaling to donut well D is in between A and F so there is a possibility that a string donut is in this file。

Now at a file level， this is pretty great because I can just read this footer of the file and know whether or not I need to read it。

 but the whole point of the metadata formats and the table formats that have come up is that we can probably do better than this because the way that these systems were all originally designed is that we're on some file system where're checking the footer of a file is like super cheap we're talking about things like the Hadoop file system HDFS doing a footer check is really。

 really cheap I can do it very low latency and pretty effectively the moment we move to cloud file systems things like S3 or to Google Clouds version of that。

😊，We can't do that as efficiently anymore。 We're not charged per API call。

 So suddenly what used to be a relatively commonplace and simple thing listing files。

 checking their footers is now extremely expensive。

 and especially if we have to do it over and over and over again。😡，So because of that。

 we moved to the world of table formats and Apache iceberg as one of those。

What we're going to talk about today is basically how Apache iceceberg gets those metrics。

 puts them in a format that can be read without reading all those file formats and how we plan purries with that metadata information。

So here's a quick overview we're going to start by talking about what Apache iceberg actually is how it's architected。

 some of the key features that are required to know if you want to get to how planning actually works we're then going to take a queryrry pretending that we're in Spark SQL we'll talk about how that quarry gets broken down into things that actually go into the iceberg library we'll then talk about how those predicates and things that we extract out of the SQL quarry get applied to manifest list filtering which you'll know all about manifest after we talk about what iceberg is built we'll then talk about how manifest are then filtered and finally we'll talk about how deletes which are a relatively newer concept inside of Apache iceberg table。

 then get planned with those data files and tie the whole thing together and then finally I'll give you a brief hint of some of the things we're working on in the Apache iceberg community for V4 of Apache iceberg currently on V3 but we're looking in V4 to change some of these structures that I'm going to go over today pretty foundationally to hopefully speed things up even more in the future。

So to give another overview of what we're talking about。

 we're basically going to be in three different lands。

 we're going to start in this this engine specific land because all the code we're talking about is basically how do we get a query into iceberg and that's going to be dependent on the engine that you're using。

 So， for example， you could be using Spark， you could be using Trino。 you could be using snowflake。

 my employer， You're using one of these systems to write some kind of query in some language and that language then has to be converted into entities that the iceberg library actually knows how to work with。

And at that point， we can then use those constructs to actually perform a query completely within the iceberg code base and then finally get a bunch of file scan tasks where we actually actually read some kind of file from disk and then at that point there's actually even another layer filtering where we can actually filter out the row groups themselves I'm going to skip that part in this talk here because that's again file format specific。

 but basically the same lessons that we're going to learn about in the filtering of manifest list and manifest apply to file row groups as well。

 but again in a format specific way so parquet works a little differently than orRC that works a little differently than Avro and so on and so forth。

😊，So let's start at the beginning What is Apache iceberg I'm not going to go through the entire setup of what Apache iceberg is how it works in its history。

 I'm going to try to highlight only the technical concepts that are important for you to understand how planning works which means I'm going to constantly be glossing over things and saying this isn' an abridged version of this I'm only cutting out like a ton of things here I'm going to skip some details that are very important but are not actually relevant to how planning works。

Now at its core Apache iceberg is what we call an open table format。

 which the definition I like to go with is basically how do we treat a bunch of files like it's a relational database because at the end of the day。

 we basically want some way to separate compute from storage。

 still have asset transactions and then get a whole bunch of other things that we can do in a relational database with just a bunch of like parquet files So basically concepts for schema evolution partitioning like I said。

 we want to be optimized for this cloud storage and we want to make sure that at the end of the day。

 this definition of how you work with this table is in itself a open concept that we want everyone to be working on together。

 people from various vendors， various engines all working to make sure that it's interoperable。😊。

So that's basically in a nutshell what we're trying to do here。

And the way we do this and the way that almost all table formats do this is we have a bunch of data files and then we build on top of that some set of metadata。

 and you'll see between the different table formats and different ideas in this space that metadata is some accumulation of statistics from the data it's possibly a bunch of files it could be entries in a relational database。

 there are a lot of different ways to do this， but iceberg chooses to do this in a series of files。😊。

And the way that that's actually laid out is done in something called the Apache iceberg spec so the way that we keep this all kind of vendor agnostic engine agnostic is that the Apache iceberg project starts with this specification where you basically have to write out the rules for how you interact with an iceberg table so you can go to this website whenever you feel like it you'll see a very long document where we basically go through all of the concepts of how an iceberg table actually has to work。

And what's exciting about this is as you go through it。

 you'll see that there's really nothing engine specific or really even that language specific。

 we do have a few things tied to serialization that are tied to Java iss but。Basically。

 the definitions here are supposed to be broad enough that if you come to this spec from any perspective。

 you can basically build an implementation in your engine that can read an iceberg table without using the library that we have Now the library that we write for this is in Java and does follow all of these rules。

 but that's not supposed to be a necessity so that people coming in from other languages or other engines can do their own thing and still have something that's completely compatible without Apache iceberg tables work。

And the way that we lay this out。Starts with something we call a metadata file and this is basically just a J description of a table it's got a bunch of fields and entries we're going to go through some of them later。

 but the main thing to know is that it's got the schema and things that describe how the table is generally shaped。

And that metadata file is going to list several snapshots and those snapshots all point to something called a manifest list。

A manifestif list is a list of manifest files。AndA manifest file is， in turn， a list of data files。

 So this is things like parquet files that are actually a part of our table and also delete files。😊。

So our data files are then listed underneath this and delete files as well。

 and we basically have this whole hierarchy tree here where if you ever want to check whether you need to read the layer below you can look at the statistics in the current file so this trims down the amount of files we actually have to read to plan something significantly because we can go through our manifest which has statistics about our data files and then use that to determine whether or not a data file actually has to get read and the details for how we actually do that is what we're going to go through today in this talk。

Now， because I wanted to get a few other features in here before we go into the details。

 I'm going to first talk about quick how commits work here。

 So like I noticed like I noted previously， the Apache iceberg structure is basically this hierarchical tree you start out with a metadata Jasonson file it points to a manifest list which points to manifest which points to data files and the way that you do a commit is that you have this pointed to by a catalog。

 which is another system， So for example you can use a high metastore you can use dynamodb。

 you can use all sorts of things as basically a lock here。

 So it essentially ties a table identifier to a metadata do Jasonson file and when you want to transition between one state and another。

 you simply build a new tree So for example I would write a new metadata Jasonson file which points to a new manifest list but also points to the old one because my previous snapshot is still available for time travel so I can points to that previous one as well and then that new snapshot or that new manifest list points not only to the old manifest but to the new manifest with the。

Data files I'm adding， and I basically keep growing this tree sideways as I shift my catalog from metadata。

Jason's metadata。Jason。Now the quick thing I wanted to point out here is that this description of how iceberg works is a little bit old。

 so this is how catalog plugins which iceberg works with function basically a client produces this whole tree underneath。

And then talks to a catalog and says， hey， I've made a new tree。

 can I switch between the old tree and the new tree and then swaps that pointer。

We've entered into a new phase of the iceberg project。

 which focuses around something called the rest protocol， the iceberg rest protocol。

 which is a way of basically trying to separate some of that logic so the client doesn't have to know as much about metadata generation as before。

 So within the iceberg rest protocol at the moment。

 the client no longer has to produce this metadata Jasonson file instead it sends a set of table changes to the catalog and then the catalog actually writes the metadata Jasonson file and swaps the pointer。

 So this is better for a lot of reasons that I can go into them later。

 but the reason I want to point this out now is that we are moving that line even further down。

So what we've been working on a lot recently is how can we get this to the point where the client really only knows about the data files that's written and we can rely on the catalog itself to know all of the logic about how a commit is actually processed。

 so this is kind of the future of the project but this is my quick overview of how commits actually work and how we're kind of thinking about that。

The only important thing here for query planning is to note that each of these metadata。

Jas has a bunch of snapshots that it can point to， so one of the very first things we have to do in query planning is decide which of these trees are we actually going into because the metadata。

Ja has both the current snapshot as well as past ones。No。

There are a few other iceberg things we need to know about before we go into planning or else we're going to get into code and everything will be very confusing the first that I really want to talk about is like I said those snapshots next we're going to talk about schema which defines how the tables actually laid out what columns and fields are present and then something called partition specs。

Wch basically describes how partitioning works inside of an iceberg table and I'll go through all of those in details。

 So again， our snapshots inside of our metadata Jason are literally a list of Jason objects。

 each of those is a snapshot itself which has a manifest list path inside of it。

 you'll see inside of this diagram I hope you can see my cursor here。

 we have a manifest list field if we had multiple or multiple snapshots。

 we would basically just have multiple Jasonson payloads here。

 Each of them points to their parent so you never modify a previous snapshot when it has a new child when you add a new child it just points to the previous parent and you'll end up with some kind of structure that looks like this where as you continue to make new snapshots。

 they all point to their parents you can branch between snapshot sorry you can branch like between snapshot3 and 4 and have two different branches that all go to the same snapshot。

😊，But this is basically our structure for storing states of the table that are accessible at this time。

The next feature that we need to go into。Is schema evolution。

 How does schema actually get stored inside of the iceberg table。 And this is really important。

 And for those of you who have worked with older systems。

 you may be familiar with systems that use basically what we call a schema on read pattern which essentially says when I read a table。

 I look at a file and that file tells me what the schema of the table is like I basically can determine how my table is is populated by looking at the files or by determining it based on the files that are in the table And the problem with this and the problem for schema evolution here is what happens if you drop a column and then add back column with the same name。

So if you're familiar with older systems or worth working with a table that's represented purely as parquet files。

 the answer here is that you resurrect that data if you delete a column。

 you're basically only deleting a logical representation that that column as part of the table and when you add it back you're adding back just that name as part of the schema which means when you then look at a file。

 that file when you dropped the column was still there， you didn't rewrite the file。

 you just rewrote this table metadata that described it。

So you end up with this problem you can't really evolve schema in these old formats because there's this strong tie between the name of the field and the table and the name of the field in the file。

 So they have to match all the time。 So iceberg gets around this with something called field Is。

So when we define the schema inside of an iceberg table， every single field not only has a name。

 which is basically how this column is visible to SQL。

 When I refer to this table and I'm looking for a particular column like Id。

 I look up the name field inside of the schema and I see I have a field named or a column named I。

 But when I actually go to the data file itself， I use the field I。 So the field I here is2。

 And the reason that I want to do that is that my file could be written when I had a completely different schema。

 So， for example， I might have a schema that was written when the table looked like this。

 It had three different columns。 One was age，1 was Uid and one was data。😊。

But the way that I write those in iceberg is that when I write this file。

 I map each of those fields within the parquet file with a mapping of field I D 2 column name so that if I ever want to know what column2 is or field I D 2 is。

 I can do that， and I can change the name of that column in the table without doing any changes to the file。

 So， for example， if I do have query where I'm selecting Id out of this table。😊。

The first thing I do is I look in my table schema and my table schema says the idea of the idea of that is two。

 and then when I go to my file， I can just say I'm looking for the file field with two。

 I don't actually care about the name of that field of the file。

 but if I match I'm only matching by I。 and again， this is really important because now if I want to change the name inside of the table from I to user ID or back to UI。

 I can do that without changing the underlying file because all I do is I change the name of the field。

 not the field I of the field。😊，So if I have another different file。

 I can have one written again with completely different names or with different columns。

 But as long as I have that mapping， I do the same lookup。 So in this case。

 my file actually was written where the column in the file is written down as I。

 But the important thing here is that the field I was two。 So again。

 I do my lookup where in the table， I get Id is two and then when I look in the file。

 I get two goes to back to I。 So again， Ive disconnected the mapping of the naming inside of the files from the naming inside of the table。

 and this means I can evolve my schema really easily。 So in this case。

 if I wanted to drop a field and then add it back， the new field would have a new field I。

 So even if it had the same name as the previous version of the column it wouldn't matter because the way that I actually look up the columns inside of my files is I do that by field I。

 So if there's a new field I， it will never match the old columns。

 even if they have the same name as my newly added column。😊。

This is real may I get ahead like how much？Like can you define like constraints on the schema for a column like you have required true。

 what about like unique uniqueness and other things like that。

 like things are eventually for planning you want to push down because you know more about what the data looks like。

Yes， so can we do those things Not yet。 So the initial spec for iceberg only allows us to do required and optional。

 So that that was our start in V 3， what we've just done， we've added in some new capabilities。

 One is defaults。 So now you can have a schema with default values as well。

 So you should say if not present， we should return some other serialized value instead。😊。

Or we can say that if this value previously was not set， this is the value you should use。

 So basically we have a way of adding defaults in the future we're looking to add further things like constraints on the column and things like that。

 one of our problems with uniqueness and I'm sure you'll see this in a bunch of other distributed systems is doing uniqueness in a distributed system is super complicated and we tend in the iceberg format to say if you cannot do this universally within all the engines that are working with this system we don't really want to implement it So uniqueness is one of those kind of tough ones where where I think every time we kind of bring it up。

s it's considered to be too expensive， but again， it's an open source projects that folks are interested we could introduce that in the future。

That's what about like the null semantics because you have to make that match across of different engines right Yes。

 so one of the ways that we handle all of our null semantics and things like that is that we actually have this defined in the spec we say these are the only ways that values are serialized This is how they're laid out So every type within iceberg is not engine defined they're iceberg defined So we say this is an integer an integer has this many bytes it as this max then midvalue。

So you get around the fact that， like， maybe your system has it 1，28， and my system has in 32 and。

That doesn't matter to iceberg because iceberg says I'm defining int this is how many bytes long it is this is the mini max value。

 This is where we we'll get to some more interesting things about this later。

 but basically that's our our system here we have strongly defined types They are defined for iceberg。

 Everyone has to take that and convert to your engine local version。😊，Awesome， thanks。酷。

Moving on okay， so the last concept we kind of need to go over is hidden partitioning and partition transform so this is another kind of complicated thing。

So within iceberg， if you're familiar with how other systems do partitioning like hive hive will partition by basically just making a directory and that directory will have a column name and then equal to a string version of the value of that partition so basically makes a directory structure where the files are placed in specific directories and if you're in a specific directory that means you have that partition value。

Iceberg does this very differently first iceberg says whenever we write files we're going to associate a couple of partition values with that file and that's based on what we're calling a partition spec。

 which is a collection of transforms for different columns in that file that produce a value so the example I've given here is a bucketing transform。

So for those who aren't familiar bucketing is essentially you take a hash of your value。

 you apply some modular to it and get an integer out and the way we define this is we say a certain source ID is used as input to this and we define this transform itself with a certain field ID so when we write it to files。

 we know where it is。And we use that then when we produce data files。

 writers will use this to make their own files。 So in this case。

 we could have the output of this tuple being one。 we only have one transform。

 so we take the bucket function we apply it， we see that it's one and then we put files with that tuple associated with them or we could get different files where those when you plan has function you get two and we associate them with a different partition tuple。

 This is independent of the position where the file actually resides in the table instead we need this mapping of what spec was used to make it and then we can use that to figure out what the tuple values mean。

And I note that we are again talking about source I here because as I mentioned before。

 we want to make this name independent， So this is tied to the field ID of the schema entries and not the actual column names。

 So this， when it says it's working on source ID too might be working on a column that we've defined as data but has a field I to。

 but we don't actually use that we use the source ID when we compare all these things and connect them back together to avoid renames destroying other parts of the table。

 So when we rename a field， we don't actually have to change our partition transforms。

 they remain exactly the same。So we have a lot of different transforms that we can use。对。

Just a quick overview of them here， one of the ones where I think Andy was kind of noting how do you deal with different serialization and issues truncate is an example where this comes very。

 very complicated because truncating different types ends up being very difficult when you get to strings and things like that because you might want to get min and max values of truncated strings and if you get into something like unIcode that ends up being actually kind of tricky because not all code points are valid so you can't just do like bitewise truncations and stuff like that anyway。

The the main point I want to have here is we basically have these explicitly defined within the iceberg spec。

 So again， we say exactly how you do all of these functions inside of the specification。

 So every engine that's attempting to find a。😊，A value effort's been transformed。

 uses the exact same function， so our bucket transform is actually defined as a very specific Brer three implementation that is then used modulo。

 the number of buckets you're trying to use， but anyway。

 all of this is extremely well defined so any engine looking at this or any implementer can remake these transforms and get the exact same answers given our data types。

😊，All right， I know that was a lot of stuff， but I promise all of these concepts are going to come up again and again as we go through how the planning actually works because we actually have to know how to figure out what our partitions are and we have to know how to figure out what our fields are as we go through all of this。

🤧So let's start。In Spark SQL and I'm going to talk briefly about the data source V2 API but if I went through this entire part of the code path which exists completely within Spar that would be another like hour or two hours of talking so we're going to basically say a lot of stuff happens and at the end of the day we enter into the iceberg Spark plugin which has something called a Sparkcan builder this is part of the data source V2 API but is basically where Spark talks to its data sources and says here's the stuff I know about your query。

Do something with it and give me back a bunch of rows。So。

How do we get that stuff that's in Spk and make into iceberg stuff so Spark is going to give us two specific things that we're going to use for our planning。

 one is in the form of a function called push Proddiates which we're going to use to make our iceberg filter and one in the form of a function called prune columns which will give us what information we need to do our projection as we are looking through our files。

So both of these get passed into iceberg code and they're implemented in a pretty straightforward way。

 So for example， the Spark API is going to call push predicates on the scan object that it's making inside of our iceberg code and it's going to have a bunch of spark predicates so at the top of this function we have we have this sparkk method called push predicates which takes a bunch of spark predicates and returns a bunch of sparkar predicates but the important thing to know here is that what we need to do is with this input we need to know what we can push out so the first thing we do is we convert these from the data source V2 expression language inside of Spar into the iceberg expression language。

So that's our convert function that first line there Spkv2 filters do convert the important thing to know here is that the input is a spark class and the output is an iceberg class so our conversion happens there we basically have a one to one mapping if you have a data source V2 filter that's an equal we have an iceberg equivalent equal operation。

😊，Once we do that， we then try to see whether or not we can actually push it down。

 and that's where this fun little bind thing happens。

 which is the first point in which we're going to get back to why those field Is are important。

 So the expression we get from Spark doesn't know what the iceberg field Is are right It's written in terms of this query。

 It just knows hey， there's some X in this table。 I need to push down some kind of predicate for it。

😊，The unbound predicate inside of the iceberg code base represents one of those predcateates where all we have is a name。

 we have maybe some literals and we have an operation。

 but we haven't actually bound it to a specific schema inside of iceberg。So when we try to bind it。

 we can actually determine whether or not this fits the schema that we currently have。

 so is this app predicate we can actually handle or not and we do this by looking up the field IDs and determining is there a inside of our schema。

 is there a field with the name X that we can bind this particular expression to？

Because once we've done that， once we have the field ID tied into the expression。

 at any point later we can look at any data file which may have it bound to a different name and use that field ID to get the correct call。

So we do this little test to see whether or not we can bind it because if we can bind it。

 we know we can actually do this kind of metric lookup and if so we add it to the list of expressions。

 we're actually going to try to push down inside of the iceberg API and the rest of the little fun stuff we do here with pushable filters ad and postcan filters ad that has to do with communicating back to Sp what we were actually able to do and what we were not able to do the reason that we have that sort of stuff is that Spark has its own optimizations where if you say。

 hey， I've completely handle handled a particular predicate， Spk can then say。

 oh then I won't reapply it in the compute layer this is actually well， I'm going say new。

 but like new to me because I've been working in Spk since like Spark09 and for a long time。

 Spark would just always double double compute So basically if you had a predicate and you pushed it down Spark would still apply that predicate again at the compute layer just because they were like yeah we don't know for sure but this was added it as a mechanism later to say。

There are certain prediccateates we know we can completely evaluate and there's some that we know we can。

So the question that chat，'t the API or doesn't the API know if the query includes a as of for time travel to pick the right field ID for bounding？

Yes， so that part I kind of skimmed over here when I wasn't going to go through exactly how the snapshot selection works。

 but yes， there's basically a part of the API that parses out a as of and that gets set through yet another API and then pushed down into the scanBuilder and then when it selects which snapshot it starts from。

😊，That that's where that kind of gets picked in so you pick a snapshot the snapshot has a schema ID associated with it this is another thing I gloss over we actually have all of the schemas that have been used in the table in part of that metadata do Jason so we use that ID then to look up which schema we should be binding to which lets us correctly bind to the schema as of that snapshot as opposed to the current schema but that's a really good question I was skipping that part。

All right， any other questions or should keep going？Keep goingwn， all right， all right。Okay。

So how do we do our schema pruning as noted by the questioner we actually do have to determine what schema we are looking at based on what snapshot we are loading。

 but I'm skipping that part here basically we have yet another function called prune which is going to take in a spark definition of what columns it wants the iceberg schema of the table and then output an iceberg schema that matches the requested columns。

 the only additional important thing to see in this bit of code here。

 this is in that second block this schema equals whatever。

Is that we have to include the filter expression here as well。

Because one of the really important things here is that we may have a predicate that involves a column that is not actually required to be projected by the query。

 So for example， I could select X where Z is greater than5 in that particular query。

 I don't actually project the column Z for reading I'm projecting it only to evaluate my predicate。

 So in those cases， I might have to extract columns out of my predicate in order to know that I actually have to surface those columns back up to Sp。

😊，So again， at the end of the day， I take a spark construct。

 I apply some functions and I get back out an iceberg schema that I can use in the rest of my planning。

With field I again， because we need our field I this whole time。

 So now that I've got my iceberg specific objects， I have an iceberg set of expressions。

 and I also have this iceberg schema that I want to read to。

 I can start going into the iceberg specific code。😊。

Which means the first thing I do is I have to read that snapshot so as noted before。

 the snapshot I'm reading is described by another part of this spark SQL dialect or you can do it programmatically。

 but basically that's going to give us a snapshot。And our snapshot is， as I said。

 associated with a specific manifest list。That manifest list has within it a bunch of data manifests and delete manifests I'm going to read that file that's what's happening here in the snapshot to data manifestif Io and deletemanif。

 IO and basically reading through that file and getting particular things out of it there's a cache behind this so it's not actually reading through the file twice。

😊，And I end up with two objects， my data manifest and my delete manifest and this is all I need to actually pass into my code that actually does the planning and that's manifest group do Java。

 which is where we're going to spend almost the rest of our time talking about how iceberg does this。

Which is where all the real work happens and where all the real complexity lives here。

So the first thing we have to do once we are reading this manifest list is we have a list of data manifests and we have a list of delete manifests。

We need to determine which of those manifests are actually important because there is a possibility that a manifest only contains entries for data files which could not possibly match our query。

😡，Now the only thing we can do to check a manifest list entry here。

 a manifest row is the partition summary， so a manifest list is composed of these rows。

 there's a bunch of information there like where this file is。

 but the important thing for us are two things。What is the partition spec I。

 which tells us which set of partition transforms were used for all of the data files in this manifest。

 and the other is something called partition statistics。

 which says for those tuples within this manifest file。

 what are the min and max bounds of those topples， and this means that we can actually do filtering for all of the data files within a manifest if we can filter for their partition。

😊，So I'm going to go through this a little more concretely because I know this is a little more complicated here。

 but essentially， we might have an iceberg expression that says we're looking for a timestamp that's happened before。

😊，November 5，2008。 Now， our partition spec may apply some kind of transform to that timestamp column。

 So our partition tuple doesn't actually have a timestamp in it。 It has something else。

 like perhaps we were using the day transform。 So our tuple doesn't actually have a timest。

 It has a days from epic that represents the day from epic of all of the rows within that data file。

 So I have to take that iceberg expression and project it and bind it to the partition the specific partition spec that was used for a manifest。

 and that basically converts my expression from timestamp less than some particular timestamp to the day timest field of that partition summary has to be less than the day version of that timestamp。

 which ends up being an expression that looks like day timetamp is less than days from epic version of that particular timestamp。

😊，So once I have that expression now in terms of the partition summary。

 I can actually go through all of these partition summaries and check whether or not this expression is true or not。

So the way that we do this is something through something called a visitor pattern if you took some fun Java or objectoriented classes at some point you'll be familiar with this but basically we define some kind of tree structure and we define how we go through it based on each node type so in this time in this way we make a visitor that says okay if you reach an and node。

 the way to compare an and node is to look at all of its child nodes and make sure that all of them are true and then iterate through your child nodes and call the visitor again。

So in this case we would visit and and would say visit all of my children make sure all of them are true。

 we would then visit the first greater than， greater than would then have a specific implementation to describe how you figure out whether x is greater than5。

 you would then visit the greater than again and then finally you' visit a starts with and you would then go to the starts with implementation which says I need to have some specific way to find Z within this partition summary and evaluate it against BAS。

😊，And to make this a little more concrete， let's go into one of the actual codes of this because it's a lot more simple。

 it's a lot simpler than I described。😊，So we start by basically saying if we have no statistics。

 well our rows might match， we must have we might have some file and some manifest within this some file within this manifest that might have rows that match because we have no statistics。

 so in that case we fall back and we just say you better read this manifest。😡，Alternatively。

 we enter into this visitor。Wwhichch will then visit all of my nodes and on each node do that specific code So for example。

 this is the less than node code on the right and it's pretty simple here we basically say if in that statistics structure。

😊，If its lower bound is less than the literal， then we know that there can't be any。

 any matches here， because we know that there are no rows less than。This inside of the manifest。

 Otherwise， we know that there might be some hit， and we then have to actually go into that。Sorry。

 we know that that part of the expression is true。So basically。

 we have a version of this for every single operator which says if the stats do lower or do upper or some combination of the two has some comparison to the literal that we're trying to compare it to。

 we either say rose match or rose can't match。And again， remember。

 we have already bound this particular expression into the partition specs。

 so we know that we're matching apples to apples here。

 Our literals here are now transformed to match specifically to the statistics that we are trying to compare them to。

So once we've done that， we now know which of the manifest files we actually have to open up。

But once we've opened up our manifest files， each of those has a list of data files and we don't want to read all those data files again we need to check for each of these entries within a manifest。

 do we have to actually open that data file and read the data within it to answer this query？

So we can do even more exhaustive filtering on these because like I mentioned for Manif lists。

 all of our entries only have this partition summaries。Within a data file entry inside of a manifest。

 we have a lot more information。 So again， a manifest is basically this relational file it's bunch of avro rows right now。

😊，Which has a data file construct within it， which gives you a partition。

 which gives you the actual partition used for this data file。

 There's no upper or lower bounds because you have a specific partition toppled for every data file。

 We then have for every other field that we're recording metrics from the value counts。

 how many total values are in this column， the null value counts。 we have a na value counts。

 I skip that here。 and we have a lower and upper bound。 and those are the most important things。

So all of this is populated when the iceberg table is written。 So when you write a parquet file。

 one of the last thing that happens within the iceberg right path is that we aggregate all the metrics up for all the different row groups and store that into this entry。

 So all of these statistics are basically directly extracted out of the footers of all the files that we've just written。

😊，But now they're available here as a row in a file。

 so we don't actually have to look at the footer to get them out。

So how do we actually compare all of this？Like I said。

 we have this nice type structure for our partition tuple which matches to some set of transforms in a partition spec so for example。

 we might have fo comma1 and using that partition spec ID we can basically say， oh。

 that was written with the partition spec where we're truncating and only getting the first three characters of column v and we're taking the identity of ID again we're actually doing these all by field ID but I'm just using names here just to make it a little clear。

And then for our column metrics we're keeping these maps and the map is a map of field ID to the serialized binary representation of the min or max value。

 So this is bad for a few reasons and this is one of the things we're working to fix in column in table format V4。

😊，The first is if I gave you these maps where it's a field ID to binary。

 can you tell what the type was that was used to serialize this？And as noted before。

 since we have different schemas in the lifecycle of the iceberg table。

 we actually can only do that if the type has never been promoted because if the type changes。

 then the representation of the Min and max value might change and we have none of that information here。

So that's a little bit of a problem you'll notice that inside of the spec we have this whole thing about a lab promotions。

Where we only allow promotions where we're able to actually look at this length of this binary and determine what the type was。

And then one of the issues here is this is also not really great for wide tables。

 If we're storing tons and tons of metrics here in a map。

 if you're familiar with how maps are stored in parquet or other columnar types。

 the only way to get a particular field out of this would be to read all of the keys in all of the values。

 They're not stored in a way that's actually pushed downable within a columnar file format。

 So maps are also not great if we want to use a column or file format because we get no pushdown ability。

 we can't read only the metrics for a few columns， we have to read them for all of the columns。😊。

But this is what we have to deal with right now because this is how it's currently laid out in iceberg V1 V2 and V3。

So when we want to actually compare this， we enter into the manifest reader， so the manifest group。

 when it begins this filtering process will then start reading manifest using manifestifreader。

 Javava。Manifest reader do Javava has a bunch of initialization code。

 but eventually you get down to this function called entries， which filters each of our files。

 each of these data file entries based on two things you'll see we've got an evaluator here that's eval the partition and we have something called metrics evaluator which is evaluating the file class as a whole and it's actually doing all those columnmetric comparisons so our first our first partition evaluator here is basically using a class called evaluator Javava evaluator Javava takes an iceberg expression and evaluatings a struct against it。

😊，So that's why we use that there。 And then we have this other class called inclusive metrics evaluator。

 which we use for evaluating all of those different serialized maps of min and max value， which has。

 you know the code to do that Basically， it says given an iceberg expression。

 do we have some way of actually。😊，Determining whether or not the metrics held within this file are valid。

 And again， we return either rows might match or rows cannot match。

 We're never making a decision that row definitely exists， although we can do that for partitions。

 but we still don't do it。 We're always saying either these files need to be scanned by the engine or they don't need to be scanned by the engine。

 We don't ever make a a strict determination that there will be a correct row。

So the way that our partition evaluation works is， again， we have another visitor。 So basically。

 we have an expression visitor， which similar to。😊。

The one we saw before has a definition for each of the different operations。

 We take our iceberg expression。 We bind it to this particular partitionstruct。And then with that。

 we then run our evaluator， which will basically just do the exact same thing as we saw before。

 but with a little more complicated extraction because now the way that our expression is written and the way thestruct is constructed might be slightly different。

 So we use an evaluator to extract out the proper part of thestruct that we're matching to this literal value。

 and then we check whether or not it's less than zero。 But again。

 we're basically doing a mapping here of names to field Is to make sure that everything lines up correctly。

When we're doing column metricss， we are basically doing the same thing。

 We have taken the stats object out of the data file。

 and we're going to check the various stats that are within it against the iceberg expression。

 So here's an example of greater than we start by checking our nulls because we can check if we contain only nulls。

 We can check if we contain only Ns。 If so， we know that there's no rose that canmech。

 because you can't be greater than those。😊，嗯。And then if not， we actually check our upper bound。

 So there's a lot of magic baked into this line where T upper equals upper bound of term。😊。

This is a place again where I didn't want to go into the strict details here。

 but basically the different types of terms we have so we can have a function。

 we could have an actual column value。 We can have an actual metric can all be defined differently here so that we can actually use this same logic against。

 say， the a generated column or an actual column in the table So there could be an expression that we need to apply to this upper bound before we can compare it to our literal or we might be able to use it raw if we're actually checking the value of the column against a literal。

😊，Anyway， the the log of the shorter of it there is we again are just basically comparing that upper bound inside of the filestruct to。

The upper bound in our expression and。If it works out， we say the rows can match and if it doesn't。

 we say the rows cannot matchsh。And we put those all together。

 and we end up with an answer for a particular file of either rows might match for this file or rows don't match for this file。

Okay， so once we've done this， we've basically evaluated whether or not a data file has to be read from our engine to actually find rows for this query。

 except I've skipped one important detail， which is delete files。

So iceberg has this concept of delete files which basically say for an existing data file。

 I'm allowed to mark certain rows as no longer existed。

 and I'm not going to go into the full details of how that's built out。

 but basically we need to know if a delete file applies to a data file in our query because if so。

 our engine that's reading needs to apply those deletes as it goes through the data file。

So we do that in something called a scan task， a scan task puts together both the data file that needs to be read。

 along with the delete files that need to be read with it in order to get the actual data from that particular file。

So we do this again inside of manifest group， so again we're doing more work inside of that the all the slides that we've talked about previously populate that term entries that've I've linked there as the output of all of our hard work so far so that's basically all the data files we need to actually process。

And then we also attach to it this thing called context。 deletes for entry entry。

 which I haven't talked about it all before because when did we ever talk about delete files Well the only time we did was way at the beginning when I mentioned we have some delete manifests that we need to read。

Now the problem is when we initially implemented deletes， this came in V2 of the iceberg format。

 we needed a way to associate those deletes with the data files that we were reading。

 but we made slightly a few complicated ways of actually associating those deletes with the data file。

 so we have a slightly complicated mechanism for associating them back once we've got our data files we want to read。

😊，So we have this thing that we call the delete file index。Now。

 the delete file index is made from the file index builder。

 The delete file index builder is initialized at the exact same time that we initialize our manifest group with that list of all the delete file manifests that we need to read。

 when we do all of our configuration to put various filters onto our manifest readers reading out our data files。

 we do the exact same thing to our delete manifest。 So basically。

 everything you do to a data manifest。 We do the exact same thing through delete manifest。

 We check its upper and lower bounds。 We check our partitions。

 it's in and we end up with a list of only the deletes that are applicable to a particular set of files。

😊，And at the moment before we start actually planning our data files， we build this index。

 So right before we start going through all of our data files。

 we're basically ready to assign all of the appropriate delete files to each of those data files as we build our scan tasks and the end of the day。

 basically we have built up a set of maps Now by partition we have made up a map of all the quality deletes all of the position deletes。

 and then we have this last fun thing where we're just mapping the position of the path of the data file to a specific position delete and the reason for that is that we've recently introduced the ability to associate delete factors with specific data files。

 you can also do this with position delete files， which is another concept that I don't want to go into the detail lab。

 but basically it's another way of looking up what delete files are relevant for a specific file。😊。

So inside our delete file index， when we call for entry。

 it's just going to go through those maps and basically determine what is the correct set of deletes for a particular data file since we're running a little bit low on time I'll go over this just kind of briefly the first thing we do is we figure out if there's any equality deletes that's what happens in the first two lines of global and equal partition those lines are basically saying I'm looking for any equality delete so it might apply to this data file。

 the only way we can do that is either we have global equality deletes that apply to every single data file or we have ones that apply to files in a specific partition the other argument to those function sequence number is something that I purposefully skipped talking about here。

 but it's a Laport's clock that basically says when files were added and we use that to determine whether or not these delete files actually apply at this particular snapshot。

The next thing we do is we look for delete vectors， that's a new thing in V3。

 you can only have one delete vector for one file， so finding them is very quick。

But if you don't have delete vectors， we have to check for these things called position deletes。

 which is another type of delete that we add， which is essentially a parquet file。

 which has a list of rows and paths and you have to associate those paths with data files and then the row identifiers that you get there are the ones that you have to delete so you basically get like。

😊，Out of data file， A， delete row 1， out of data file， A， deletete row 2 out of data file A。

 deletete row 3。 So you basically get a row for every row that you're removing。

Deelete vectors are different， it's just a bit set， which is the rows that you're going to remove。

All right， so once I have all of that， I then do one final step before I give my beautiful scan task back to the engine to actually do work and that's I have something called plan tasks。

 which is in tablecan U， which is basically a way of saying I might have a defined split size。

 I only want to read a certain amount of data in a particular task at my engine level and you can actually specify that to to the iceberg API and when you do that it will basically take multiple scan tasks and either split them up because they're too large because the data files is too large or combine them because the data files are too small and you want to read more data in a specific sparkar task or something like that。

😊，So。Once we've done all that， we're ready to go， we can basically take our tasks。

 serialize it out to Spark， and then there we'll be spark specific logic to take this information about a data file and a parquet file and read that into a spark specific memory format。

 but we've completely done all of our planning and at that point。

 any files that get to Spark have to be read by Spark with a small caveat that if you have limits or things like that you can potentially terminate before reading all of the tasks that have been planned for you。

😊，Now， a few notes on this， I've skipped a bunch of things。

 but hopefully this has given you at least a very high level picture of how this actually works。

 along with the actual code and places you can look to learn more about how it's actually built。😊。

But the big caveat for all of this is what not all engines use all of this code pass。

 some only use the planning part and do not use the task part， the task building part。

 others skip this entirely and just build their own implementations from the spec。

And the slightly bigger sad note is that we're planning on changing a lot of how almost all of this works so。

What are we trying to do in V4 of the iceberg spec to make a lot of this information I just told you no longer relevant？

The first thing is that we're looking to expand the way column stats are stored so as I mentioned before。

 we are storing them right now as these maps which are not very good for columnar types and they're also untypeped so we actually don't know we don't know what they were written as so that makes type promotion basically impossible inside of the iceberg format for anything other than type widening。

And the other big thing we're looking at is removing manifest lists entirely。

 so one of the things you might have noticed is that almost all that logic we're doing to deal with a data file is an expanded version of what we're doing on a manifest list。

So the question has been raised and the proposal is out now by me and a bunch of other people in the community about why not't we just make the manifest list itself just another type of manifest。

 because it already has all of this logic for basically comparing column aggregates and this logic for dealing with partition transforms。

 we might as well just make that logic universal and have a manifest that points to more manifests。

Additionally， one of the things we want to do is say。

 what about all of those child manifests in the current setup。

 there's basically a lot of churn because whenever I want to change one of those child manifests。

 I basically have to delete the whole file and write a new version of that file with the new rows in it。

What if instead I could also apply delete vectors to my metadata。

 so basically I can start deleting things out of my metadata with also without actually removing and rewriting those files。

So there's two big new things that are coming that will throw into turmoil a bit of the stuff I'm working on or the stuff I've described today。

 but the key thing that's going to probably remain the same is the way that manifest evaluation works。

 we're just going to expand that concept to work with even more things and it hopefully will not have a special set of logic than where manifestists get treated completely differently than manifests。

So those are some big things happening in V4。 I don't want to keep everyone super late。

 So my last thing I'd like to shout out to everybody is the Apathy iceberg community is an open source community。

 open governance。 Anyone can be a member， anyone can work on the project and I encourage everyone who's paying attention here join us we have a devil list that's very popular we have a personal iceberg Slack that you can join off of our website we have tons and tons of community events and talks。

 keep attending things like this， learn more about the project。

 we have Github issues that you're welcome to come and contribute to and I think we're probably gonna have another big conference in 2026 and everyone should attend so with that I know I've covered a lot of different things I' would be glad to take any questions and go into more detail if anyone needs。

😊，My mouse is not working for some reason。So if any questions， I'm to go for it。

There' there's a question in the comments。Let me see if I can load the chat all right。Yeah。

 I can read it too if you want。Oh I got I'll read it over here， Okay。

 where do we get to the first one？呃。Its it's just the last question Okay yeah is all predicate push down first go through partition checks in the five days docs warning I ever writing quiries that require a function that makes the engine unable to skip files using partition values iceberg seems to say as long as it knows how to resolve a function call back to the derivative of the partition value can still skip files and the answer is yes。

 so iceberg will take any expression that is convertible to something that can work against partitions and do so So basically if you do a predicate on timestamp。

 which is one of the examples I went through we'll actually take the partition metrics and convert them to match that So if we only have a day partition but you do a predicate that's based on the timestamp value we'll convert that to make the appropriate partition expression So this is the hidden partitioning part of iceberg Basically you don't have to know how the table was partition if there was a way to take your predicate and apply it to the part。

😊，We will do so。And like I said before， you can even have your table。

You can have your table in tons of different ways， different partitionings。

 and we'll always use the partition spec that that particular file was used was partitioned as as our expression base。

😊，Okay， so other questions， you， if you want to ask question， let's mute yourself and go for it。

I have a question。There's this thing called puffin that I heard。Do you know anything about it， Yeah。

 so I did not talk about puffin files in this as well。 Thanks， Kevin。

 Kevin is another member of the iceberg community。 So thanks for joining。 So puffin files。😊。

A another kind of recent addition to the iceberg spec。

 The only thing you have to know about puffin files for planning at the moment is it's the place where we store delete vectors。

 So if you're looking into how delete vectors are actually stored in the iceberg format right now。

 they're stored within these separate files called puffin files。Other than that。

 we can store additional metrics inside of puffin files that can describe other aspects of the table。

 for example， the number of distinct values， you know important things for doing join ordering and stuff like that。

But those are currently not actually required for planning itself。

 but they are surfaced up to engines through other APIs。

 so the way that Spark handles this is Spark has another data source V2 API that you're allowed to implement which basically says Spark will call and expects to get back a statistics object and the way that iceberg deals with that is iceberg checks this puffin file if the Pin file has the statistics it will then return those to the source。

All right， so I guess I'll finish on my last question， are there aspects of like the other systems？

You know iceberg iceberg is the dominant one are there aspects of other systems like the Hoies maybe Delta Lake I understand Polariis is a rewrite of the iceberg spec are there other aspects of these other systems that you're like you wish that iceberg would have and you eventually want to add them Oh yeah so I mean iceberg being an open format we get things from a lot of other places just a quick clarification Polariis is an iceberg rest catalog implementation and not an iceberg spec implementation but got it Thank you that's super helpful yes yeah。

So one of the things I think we've talked about a lot， especially in this。

 like as AI is becoming more and more important， we see wider and wider tables because people want to store feature sets everywhere and one of the most common problems people have with really wide tables and these table formats and file formats is that the way parquet is constructed the way orRC was constructed。

 even though they have column or representations of your data so you can read columns of the block。

 you have to keep all of the column vectors for the same row group in the same file。

 So that means that if you have 10000 columns and each of those columns is like I don't know。

10 megabytes， you only get or say a row is。😊，I'm getting bad numbers here。

 but basically you end up with very wide files that have like a single row in them you have this problem where。

That means you can't actually get the column or benefit anymore because your columns。

Your files are very wide and your columns end up having to be very short so that they all fit in the same file。

So there's a lot of different formats that are kind of attacking this and trying to figure out different ways to deal with this so Lance is one of those and then there's different table formats that have different solutions for dealing with this like basically adding i've been calling them like sister files so basically you'll have a main file and then you can also have other files that have additional columns that are for the same set of rows but are in a different file so those are concepts that I think are important and I think that's the thing that i'm most interested coming up soon。

😊，But I'm not sure whether or not it's something that should live in the table format itself or if it's something that should actually be a part of the file format and described there。

 but watch this space， we have additional right at this very moment we have major proposals in the iceberg community on trying to make the file format part of iceberg pluggable。

 which would start opening the door to trying out some of these ideas in an open way。

Something that hoodie does is they let you do these sister files so you can also like update a file by adding a single new file that just has new a new column and basically have it overrite it read time This is something we we've kind of tried to stay away from inside of iceberg because I think it ends up being a kind of complicated problem as well to do that merge and're we're a little。

😊，The iceberg community is very focused on making engine compatibility a high priority so anything that ends up looking like it might be hard for some engines to do we we've stayed away from so sometimes you'll see features that appear in other formats that we don't have yet just because we're like well we don't know how Trino would do that or we don't know how Ray would implement that so we don't want to add that in right away。



![](img/659c32495e67d18c25a0a73fc678b54f_2.png)