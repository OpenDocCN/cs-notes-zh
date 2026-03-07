# 卡耐基梅隆【中英⚡未来数据系统研讨会系列｜Fall 2025, Future Data Systems Seminar Series】 p03 P3 DuckLake： Learning from Cloud Data Warehouses to Build a Robust “Lakehouse” ( -BV17pidBkEzr_p3-

But just want my peaces that pass God blessedless a friends。



![](img/e6dfc793c4f65a13598bb2b1e15b404b_1.png)

And check it out now I'm paying because it's bad friend。

Y it's time for Carnegie Mellon University's future data System seminar series This seminar is made possible by Google today to have Jordan deg。

 he's the cofounder and as his slide say chief Duck herder at Mother Duck I think professionally I think legally you're also the CEO possibly prior to that。

 Jordan has worked on many influential systems BigQuery and single like I said now he's as always questions for Jordan while he's given this unmute yourself and feel free to ask question anyt unm yourself post in the chat and I'll try to speak for and again Jordan thank you for being here you're in a appreciate you spending time with us making the effort to talk to us the floor is yours go for it。

Awesome， thanks so much' really excited to get a chance to talk to this group of people。

 I've been watching this seminar series for a long time and very cool to be a part of it So Andy already gave me the introduction I do want to show my awesome duckqueified photo this is what AI did with my headshot but yeah I worked on BigQury for a long time and I worked I was a storage tech lead so I built a lot of the kind of the core storage infrastructure on BigQury I got us to about an exabbyte worth of data and then most of it was completely rewritten by people that knew what they were doing so some of my knowledge is a little bit out of date but you know some of this you know。

Scas reasonably well， so I'm going to talk a little bit about some of that database history。

 but first I want to make clear some definitions Duck Lake is an open open data format and it includes the catalog that kind of takes what some of the other open data formats for lake houses are doing and I think goes beyond it in a more more elegant way。

 Duckdb is not duckuck Lake D DDb is an open source database been taking the world by store growing like crazy 35000 Github stars or something it's not directly related to Duck Lake in that you don't have to use DuckDB to use Duck Lake but they were created by the same people so DuckDb labs created DDB Hans who's on the call and。

And Mark created DuckDB at Duck Lake， and Mother Duck is a ventureback startup that we run both DuckDB and Duck Lake in the cloud。

 and so I work at Mother Duck。So how do we get here。

 I want to do just a little bit of history because I think it influences where I think what is so interesting to me about Duck Lakeake and kind of the evolution of some of these lake houses so the early 2010s and the rise of the cloud data warehouses。

 BigQury and Snowflake primarily and some of the big things we were seeing is we were moving data from sitting on local disks to object stores。

 object stores are immutable that changed a bunch of things。

 so much in database that had been used to dealing with spinning spinning disks and disk mutations some of that wasn't relevant anymore for analytics。

 we were switching from row stores to column stores so that's changing how data is being laid out and then moving from share。

Shared nothing where basically everything existed in multiple shards to share disk architecture。

 and this was really where the separation of storage and compute came about that really allowed massive increases in the overall size of data。

And the amount of compute that we were able to throw and we were able to scale those things independently。

So what was important for the cloud data warehouse storage so first of all file management became a problem because we had all of these immutable data files and if you kind of leave those alone performances going to degrade over time so we need to compact and coalesce in BigQuery we called had two different things one was a metadata operation reducing metadata the other one was actually reducing small files and then metadata management we wanted to make sure we had acid properties we were able to have metadata that that lived in a data warehouse or sorry lived in a database and then pointed to the latest objects and so objects would be immutable and then we were able to get snapshot isolation pretty easily。

Streaming data was also a problem， column stores in general aren't great at frequent updates。

 so essentially what happened was you know we built a buffer in that buffer in rowstore and then periodically would write those out to column store and then the buffer would also be queryable so so that you would get consistent consistent reads and then as data was getting bigger reading a lot of data is slow。

 even if you can read it highly highly in parallel it's still going to cost you a lot of money and so kind of the big thing that that became really important。

 kind of probably post 2012 was like hey this is really expensive we need to read less data。

And so implementing statistics and partitioning and et cetera， and the ability to read less data。

So in a parallel universe， we had sort of the data lake architecture and know people coming from the Hadoop world we had open data formats。

 you know parquet and ORC， infinitely scalable， you don't have to worry about your schema， et cetera。

 storing on an object store。But there were a lot of problems。 They turned into data swamps。

 It was hard to govern， hard to know which files you needed。Performance was kind of crap。嗯。

And then this is sort of the pre lakeakehouse days still so if you think of like the difference between that and the data warehouse。

 you know the performance degrading over time， there wasn't really a solution for that metadata management。

 we weren't able to do acid updates， streaming and small frequent updates weren't able to do that big data essentially able to just throw a bunch of you know leaf nodes at the problem。

So the Lake House came around to deal with file management or to solve a lot of these things。

 you know， file management， you know， was able to do compactions on write or compactions on read。

Metaadata management was actually able to provide acid updates。

 that was sort of the big the big selling point， still weren't really able to do small you know fresh data。

 but we' able to help reading large databases or large data sets by providing know pruning information so we wouldn't have to read so much data。

There were still some problems， storing data in metadata files meant the file counts exploded。

 data freshness was still a problem。Complex transactions that touch more than one table at a time were quite。

 quite difficult and some of the more。Ambitious catalogs are solving some of these problems， but。

 but also the read path was very long。 So in order to read data。

 you had to read from a whole bunch of different metadata locations in order to sort of get to get to the data。

 And so kind of your your。Latency was started out at a pretty high minimum。

But I think what we're sort of seeing is is a convergent evolution of kind of lakehouse architectures to to cloud data warehouse architectures with the realization that。

Tables are a better interface to use than files obviously you still have to get to files at some point。

 but really we should be thinking about tables and working on tables。

Datases are better place to store metadata than object stores coalescing in the background can be better than coalescing in the foreground and then。

Cooperative access control where kind of every engine has access to all the files is not a great way of doing things and so you want to have somewhere to manage all that access。

So Duck Lakeake is actually helping solve a bunch of these problems and helping with a conversion evolution by moving the metadata into the catalog。

 transactions work because it's using a metadata database which can do transactions data freshness works by inlining rights。

 and the repathlink is much better because all you have is a couple of database queries that lets you know where the files are and then you have direct access to the files。

So this is from one of the previous future data systems talks that was a couple weeks ago about iceberg and how one of the or the primary thing that the iceberg planning needed to do was they want to read less data so how do you read less data in I'm going to go through kind of BigQu iceberg and Duck Lake can kind of show what the architecture looks like in how similar or different so the challenge is we're going to take this query it's a fairly simple query that's on the right that does a filter between a couple of days it does an aggregation。

And takes the top few rows。And so what we want to we're going to really look at is file pruning so which is kind of removing the files that aren't actually needed to be needed to be read and one kind of key thing to note is like in file pruning if you return too many rows or too many files like you do extra like you're going to do extra work into query but it's not actually bad but if you return too few files and you're going to query wrong so you need things to be basically provably。

Provably not in the data files。So the way kind of partition elimination in BigQury works。

Is we basically had a bunch of metadata in Spanner， Spanner is you know， Google's。

OLTP scalable data store， we had a tables table and a storage sets table and a storage sets table had essentially kind of a commit ID so it's kind of MVCC information because it would also have the ending time as well and it would also have partition information and so we could filter out with essentially a SQL query Spanner didn't quite support SQL at the time。

 but which。Which storage sets were needed， the storage sets pointed to the files。

 it was relatively straightforward。Actually it's a little bit more complicated and this is one of the really cool things that was added in BigQury a few years ago。

 which is there's a separate table in BigQuery so a BigQury table that has metadata for the tables so this is sort of like an inception style thing and so the C meta table will have the。

😊，The column statistics for the table， and so what you can do is you can actually run a query。

 run a big query query that against that table and that filter it filters out the data that you the files that are actually needed in the query。

嗯。So what about iceberg now iceberg， you know， this is sort of the。

Picture of how the iceberg metadata is chained together everything above data layer is metadata and so in order to you know in order to to do the file printing in in iceberg you read the。

The rest catalog， you get the pointer to the metadata file， you read the metadata file， which is a。嗯。

JO file， and that's going to point to metadata list manifestif list。

 manifest list is an a file points to manifest files and manifest files point to sections of data files that are active。

 You read all those manifest files。 those manifest files have have the filters you need。

 and then you can basically apply those filters and figure out which which files you need。

 So in the real world， a lot of this stuff is going to be hopefully cached。Of course。

 when there's an update then you have to start reading again and then also the metadata may be really large and if you and like even so it may be hard to cache。

 you know， wouldn't it be nice to put this in a database？

So in Duck Lake what does this look like so these are the duck Lake file and duck Lake column stats are two tables that are used for for file pruning and and basically you can run。

This query， the top is just a CTE just to make it easier easier to read that filters out。

 you know by column ID， there's a couple of like hand waves and things that I skipped over here。

 but essentially， you know you basically just want to look at in the column in the column stats where you the files have values that overlap with the values that you're looking for in the query。

Also that the end snapshot is nu you may also want to like for snapshot isolation you may want to actually pick a snapshot ID and so there may be some other other details that aren't here。

 but one of the things is，This query looks a hell of a lot like the BigQu query。

If you just sort of like squint at it， I'm going to go back a couple slides like these two these two queries are very。

 very similar， so they're kind of doing the same kind of doing the same thing。So what about rights？

You know， read， you know， you have to be able to write also the key thing you want to do in a write is you need acid properties so you need to be atomic。

 all of the data should show up at the same time， you need to be consistent once it's done every read after that needs needs to see it or every operation after that needs to see the changes needs to be isolated so if you're running lots of these things at once shouldn they shouldn't collide with each other and then durable once it's committed it got to stay committed。

So in BigQury。You know， you basically step one， you create a job， then you run the query。

 and then the the results in Bigque get written out to Collossus and then you run a。

Start a transaction， you create a new storage set to point to those results。

 you update the table metadata to have some new information the last updated the row count。

 etc cetera， and then you add the new statistics to the C meta table and then you mark the query job is completed and then you can commit that transaction So it's atomic because the whole storage set shows up or it doesn't show up if there's a failure。

Guess garbage collected。It's being written in Spanner。

 so Spanner make sure that all the reads future reads can be returned if you run these。

 the only thing that can collide is the table stats update and that's easily retriable within that transaction。

Um， and it's durable， the data now lives on on Spanner or on Colsus and the metada in Spanner。

So in iceberg， what does this look like， well， query Engine runs the job stores the parquet files。

Then you write a manifest file， then you write a manifest list， then you write a new metadata file。

And then update the catalog to point to the new metadata file。So again， this is atomic。

 everything shows up or none， again， it's consistent。You know。

 relying on the object store consistency and the。The catalog consistency and isolation is tricky because I think this is where a lot of the iceberg right。

You know， difficulty comes in because if you're doing multiple rights at once。

 it's even more complicated if you're doing updates actually。

 but if you're doing multiple rights at once， you may end up having to redo a bunch of this work and then of course it's all durable。

So duckuck Lake on the other hand， so duckuck Lake you know you run the run the data creation task and then create a transaction so you need to create a snapshot and then you you know you basically insert some。

In basically some statistics， you update some table stats， you update the column stats。

 and then you commit the transaction。And so again， the whole snapshot shows up at once because this is all done in a database transaction。

It's all visible as soon as the transaction complete because it's done in a database。

It's isolated and you know similar to actually the BigQury update。

 the only things that there's only updates here， everything else is just an insert but again those updates can be easily easily retried and then of course it's historical because it's database So again this looks very similar to just a normalized version of BigQury know there's more tables here but but again。

 it looks pretty it looks quite similar maybe you're gonna jump maybe jump ahead like for mother duckuck's implementation of duck lake is it just a duck Db is it Postgress is like' what's the backing database system for the duck Lake data So it's duck Db and I'll get that I'll get to that in a few slides but thank you All right then small rights So in BigQury actually small rights get written to a special system actually now I think everything gets written to that system but it's in memoryory row store that gets periodically compacted。

But can handle very， very high rates of rights， you know， Duck Lake。

 we can buffer the data in Duck Lake in the catalog table。And a catalog table。And iceberg。

 we still don't have a support for small ride。So just going in for the case for Duck Lake， you know。

 so why do people want a lake house you know， these are I put quotes around these reasons because this is what people often say but I feel like these are actually secondary reasons like the openness of the format vendor lock in are things that people are generally willing to throw away if if there's a rationale the cost isn't actually。

Better。Often， and the performance is actually a lot worse。

But I think really what they want is they want to run more than one engine and often that's snowflake and data bricks they also there's a there's a warm and fuzzy that they get about sort of being able to sort of like。

Think that they can touch their data files and kind of understand what's in their data files。

 and the other thing is like there just hasn't been enough。

Description of what you give up if you use some of these lake houses。

 you do get samplenled isolation， you do get multi-engine portability。

 you do get an near infinite scalability， but you do give up a bunch including a lot of performance and I think that's something that people don't always recognize and you also give up the ability to do fine grained access controls。

 which if you're giving people access to files it's very hard to say hey。

 we're going to give you row level access。What do what do you attribute that two to 10 x performance drop of these like lakehouse systems I think partly it's it's the the the the amount of metadata。

 I think partly it's also there's there's usually a tight coupling between。

The query engine and the data format， you know， in in big way， for for example， like you know。

 there were。Like the same format， the disk format was the same as like the hash table format so stuff could just be memcoied into memory also like there tends to be sort of like type mapping things that may be slightly different in parquet and like so there's just there's there's kind of a bunch of impedance mismatches if if the data format is not designed for the database。

My guess is that this will， you know， this will come down to sort of closer to closer to 2 x as you know some of these things get better and maybe with with more advanced。

Colum stores， you know will be， you know will be even better like was what was the one you？

You launched recently F3， but like that's a。That's a so of subject， but yes， there's botex。

 there's a three lance that not really compress press really well but yeah there's a bunch of these out there now。

Fast lane and Peter。Yeah， so maybe that will help get closer。

And then just one other thought on on just constraints， you know。

 I think often you know Id like to keep an eye out for when there's a design constraint that then something changes and that's no longer a design constraint。

 but sort of like，Something something was built around assuming that that there's a brick wall there that you can't pass。

 And I think one of the brick walls for a lot of these lakehouse formats was they didn't want to store any metadata on anythingse except cloud storage It like they had to operate without a separate service or system that was running and it's not just Hootie is also like I talked to one of the Delta architects at cider a couple years ago and it was like's like oh we have to we have to do this without having an external service but I think now everybody's adding these catalogs and I think you the DDB folks have pointed that out and it's like if you have the catalog then okay we have to run a database and so you might as well do database things。

In a database。So databases are great at transactions， logging and search joins。You know。

 largerger data than memory consistency， you know。They're bad being easy to be hacked together。

 you know sometimes it's fun， you know a lot of people do hack them together because it's fun。

 but you know you're probably better off using a database than building it。

So duckuck Lake replaces a bunch of。

![](img/e6dfc793c4f65a13598bb2b1e15b404b_3.png)

You know， other stuff with database。Now here is code that Hans wrote for that's a minimal spark connector just like just to demonstrate that you know it's not just you don't needductDB to do this you know and a lot of this is you know boilerplate you know setting up spark packages and I won't go too much into this but basically the you know what it's doing is it first aquaries for what are the files you need and then it tells Spk to to distribute those。



![](img/e6dfc793c4f65a13598bb2b1e15b404b_5.png)

呃。those files to workers and then this you know runs runs runs the query。

 so you know  34 lines including a bunch of boilerlate is all you need in Motherduck this is what it takes to to do something similar this actually creates a duck lake table using an external S3 path it creates a database then it creates a table we add a bunch a bunch of those files to the tables and then we can run a query this particular query is actually from the Dremmel paper and where they you know in 3000 nodes。

 read 85 billion they did word count on 85 billion nodes in about two minutes and so this is also about two minutes kind of showing that you know in a scale up scale up system you can still scale up pretty nicely。

嗯。And I'm not going to do the demo here， but I did do this demo at Big Data London a couple weeks ago。

Okay， so building a hosted cloud cloud duck lake。 Well， so first of all。

 why do you want to have a managed duck lake at all So first of all。

 like you may not want to actually。Run queries from your laptop you know you for instance。

 the bandwidth to your laptop is probably a lot worse than the bandwidth to you know within the cloud and within a region of the cloud。

 you may also have you know egress fees， the other thing is cloud tools don't know how to talk to your laptop and so if you're using you know cloudDBT if you're using a BI tool to host it in the cloud。

 you need it also to be hosted in the cloud。The other thing is outh。

 you know basically you can have a you know centralized。

 you can let the database choose the outh rather than use S3 for the offuth using S3 for the offuth is super tricky and then disconnects like what the actual things you care about sharing。

 which are kind of。Tables and databases from files。

And the other thing is sometimes it's just nice to have somebody else handle the management。

 making sure it's compacted， making sure it's database or data has been cleaned up that's not being used you can think of it as S3 tables。

 the Amazon offering， but for Duck Lake and the other thing is MotherDuck is a query engine that can be scaled up and down as needed and so you also have a built-in query engine to do a lot of the work you you can use other tools but you can also use MotherDuck as the query engine。

Just as a quick background on MotherDuck， you know MotherDuck has a ten model where every single user gets their own scale upductDB instance。

 and then we can assign those in 100 milliseconds we generally use hotter storage so that so startup can be very fast and then they shut down when they're not being used so they scale down to zero very nicely。

The other thing to mention is。Our client is DDB， so if you're running DDB on your laptop。

 you can connect to MotherDuck in the cloud and then in our webUI， for example。

 we run DDB in WASM in the WebUI， and that lets us do things like the In SQL where you can get instant instant feedback。

 instant query results。So running a managed duck Lake can mean a whole bunch of different things。

And this is something we've sort of we've sort of struggled with is there's is like who manages who owns the data。

 so there's the bring your own bucket case where like you say hey。

 I want you to host my duck Lake database， I want you to host。The metadata。

 but I'm going to own the data， or you might say， hey。

 I don't even want to have to bother creating an S3 bucket。

 like I want you to own the S3 own the S3 bucket。Then there's catalog ownership like somebody might want to run Duck Lake catalog on Postgress but then run the actual query execution on Mother Duck。

There's offuth， you know， does Motherduck do the o or is the user going to do the offuth and then who actually does the kind of the maintenance of the data？

And almost all of these things are actually valid states。

 but the thing we're kind of optimizing for is is the sort of the fully hosted version so this is what essentially looks like so the client remember remember runs runs DDB。

Tals to a user facing DuckDB instance， which is the user's duckling， so there might be， you know。

 there are 100 users in your organizations each one has their own duckling and for Duck Lake。

 there's also the Duck Lake catalog database。Which is itself a duckling。

 so which is itself so we sort of have hybrid here in three steps in three stages where we talk to a third duckling。

I'm sorryrry， second duck link with a third DDB， and the reason that's a separate DDB instance is basically so that we can point a bunch of different users up the at the same Duck Lake catalog。

And and have that all run isolated and then also that shuts down when it's not being used so basically you know the cost to run a duck lake。

嗯。Catalog is very， very low like our smallest instance sizes， you know， are you know。

 we only only charge for race for CPU cycles and shut down and shut down you know instantaneously。U。

呃。So I just wanted to also mention that sort of like。呃啊 a。U。

Comparison to if you think back in BigQury， we had the BigQu metadata。In BigQu。

 and here we haveductDB metadata。Andduct T B。Um。You can also use other engines so for example。

 let's say you want to run Spk we're building a post Postgress API。

 which means that Spk will basically think that this is a Postgressduct toB catalog and and then we will do credential vending so。

You know， the we can basically instead of returning the raw。Daluck Lake the raw Estutri。

Path we will return signed URLs that give access just to the files that are needed in the query。

 so we can securely give access to the underlying data to external query engines。

Can you share what the internal protocol is from the user facing ductDB the user duckling and then you talk to the DDB catalog database is that like I mean DTB is going to send out SQL queries right and then are you sending back arrow or are you just sending back like whatever like protobuuffs or what so we're sending back you know serialized ductDB。

Vectctorors so it's not it's not arrow， but it's in it's inductbs internal internal format this is part of the sort of the hybrid execution which we we send up serialized query plans and then we return you know we return then。

You know， results that are。So it's the same as the client like if I'm on my laptop。

 I run the Mother D extension and when you guys send part of the query out to Mother Duck。

 that's basically the same thing you're doing for this except that you they're running they're co locatedating the same sort of VPN or whatever。

Yes， exactly got it。 Okay， awesome， cool， thanks。😊，And it's grRPC， you know。

 not that it matters that much， but。we tried actually。

 we initially experimented with our hour flight， but we had a lot of。

Kind of performance and manageability problems and like it was just easier to use useductDB's internal native。

Seralization and GRPC。rightThat's actually an interesting little conversation because the  aero flight guys are coming giving me talk for a few weeks as well so。

Yeah， I like to learn more of that， but keep going Sure was a couple。

 that was a couple years ago got， okay， yeah so， you know， fully managed duck Lake， you know。

 we can do external all through credential vending。

 we can do fine grained access control and this is still something that we're we're working on by basically giving partition access So so it's like you know you can do role level access control you can't like if you're giving somebody access to files。

 you can't do pure roll level access control， but if you if you're doing the filter on the on a partition then you can guarantee that you'll only have single。

😊，Values。Or values that match in the partition and so you know we can do fine grade access controls by giving access to partitions。

 there'll be a Postgres compatible endpoint that makes Mother Duck makes and make DDB look like Postgres so any Postgres connector can connect to it and then we also have sort of built in very inexpensive。

 very fast query execution。mSo so all the also， like remember correctly。

 the original duck like schema doesn't have any notion of。Like who can read what just like right。

 so that's something you guys have added extra tables to duck Lake to manage this and then your your platform then enforces that。

Yes， mother dog ads， which were adding。We're not adding tables to it， but it is you know， we do have。

User management and data sharing got it， okay， thanks。

So kind of finally the is Zen of data management， you know。

 the best way to make your queries faster is to read less data。

 especially if there's lots of data around tables or a better interface than files and if there's things you can use databases for you should use them instead of reimplementing pieces yourself。

That's it， thank you。嗯。Yeah。Awesome， I will pop behalf of the audience again if we have time for questions。

 so Praksha， I know you want to go for it， so let a rip。

Jan so at some point you talked about small rights being written to a buffered in the in the metadata catalog database so how are theyque so the mother duck Indian can query them I guess but I'm sure Spar cannot。

So they're part of theduct Lake specification and so you know a naive implementation would not where would not read those。

 but and more fully you know so a naive implementation wouldn't necessarily do you know might not do。

有。Pruning based on column statistics， a naive implementation might not do partition pruning and a naive implementation might not read the buffer but a more fully featured one would and it is part of the duck Lake specification。

And I think the other way to make it easy is you can。

 you link in the DDB extension and the DDB extension can handle all that stuff。

 all that stuff for you， and you can even do that in a parallel each of your Spark workers you can link in and DDB to do that to do that reading。

And do the spark workers read the data files through the DDB extension or is this a standard format？

嗯。It's they can， but I think its it's Hos is actually on the call。

 so he probably knows he knows better， but it is's the format is specified as part of the DuckDB spec or the duckuck Lake spec。

Okay。Thank you。All right， other questions？Good I'll use the time。 All right， awesome。

 is there something that the the bigque catalog had that you wish Duck Lakeake had and then for those gaps are those the things that like Mother Duck is adding to the platform。

😊，嗯。I don't think that there's， I don't think that there's much。 I think actually the duck lake。

 I think one of the things is like duck Lake。I think because it's created by database people and is it has a lot of the advanced stuff already。

 like being able to reap like remap columns and like things that I think， you know。

Are now in the iceberg spec， but I think took a took a while to took a while to get in there and like and were kind of you know relatively difficult like I think you know those are things that。

You know we're built right off right off the bat yep yeah， one% that agreed yes。Matt asks。

 how does Duck Lake help help the betterada caching issues or does it whether my better is in files or in object store or in a database。

 if my query engine is hammering the betterada， what is what difference does？Duck like make。

I mean I think first of all it's it's in a I mean databases can do can do buffer buffer pool management。

 you know the data can be you know you you don't have to read as much of it。

 you know I think one of the you know because，呃。You know， just like I said， like。

You can run queries faster if you have to read less data。

 the same thing applies to metadata and so with if data is in a。

Is if the metadata is been in a database， you have to read less of the metadata。

 you have to have less of it in memory， you can keep more of it actually paged out。Um， you know。

 more， more frequent things just tend to stay tend to stay cashd versus having to sort of build build all that stuff on your own。

Awesome。Yeah I think fascinating talk I had a couple questions on the types of workload that you see when people are running mother duck and duckuck Lake obviously these transactions are presumably way different than traditional OLTP like transactions that Or probably runs and stuff like that so can you give some flavor some idea about like the work that people are using these transactions for is it like up and only workload or dumping streaming data or what are the use cases that you've seen where it is really stressing the transactional limits？

So it's very early， which is one of the reasons I didn't go more into into sort of some of the things that we were building so I think you know there are people running duck Lake in production but it's not it's not a huge hugely widely used yet and so I think but I do think it's it's similar to the things that people are doing are doing in other other lakehouse formats I think it's also you know it adds partitioning to DDB and so it helps actually scale the size of data that you can handle inductDB because。

Especially if you're doing like time series analysis。

 you can just look at the most if you're just looking at the most recent， you know， days。

 weeks of your data， you don't actually have to pull in nearly as much data or metadata。

It scales to  petabytes versus terabytes or tens of terabytes in a pretty nice way。

I think the also you know some of the you know the buffer data。

 this sort of streaming stuff is pretty new and I don't know whether there's much of that usage yet。

 but I also think that it's to great addition to you know to the lake houses you know。

 to give you the ability to you know actually just sort of fire off a bunch of small rights and not have to worry that you're going to explode the metadata。

I guess a related question is if you're using it with Mother duckuck。

 then do you how do you scale out， like I know you guys do terabytes。

 but do you guys see a way to scale out too well beyond that to the types of things you were seeing in BigQury。

 are you starting to see people approaching the scale limits with what you can do with the process model inductDB and you know how are you approaching that？

So we're mostly focusing on scaling up， so we have you know we our largest instance is you know 192 cores and a terabyte and a half a Ram。

 which you know is roughly the amount of hardware in a snowflake 3XL。

 which is a million dollars a year。There's not many workloads that need more than that and I think the other thing is our tendency model means that every single user every single workload gets their own instance and so you know you can have like one of the reasons you often need a very large instance is because you have a lot of you know users hammering it and。

And so when you have when you have。More instances you don't need the instances to be quite as large and then finally I think Duck Lakeake is sort of the sort of the last piece in it which is you if you really。

 really do need to you know restate all 10 years worth of your data or you run ML training over you10 years worth of you massive amounts of data and you need to do it fast。

 then you can always run Spk， you can always get physical access to the underlying underlying files。

And maybe one last question， do you guys see the need for integrating with storage and glacciier and things like that or like what does your how far in the S3 layer do you get into and messing around with different storage optimization methods So we are I think what we're mostly interested in is hotter storage like I guess colder storage is also interesting that's you know really I think a cost optimization play but but for you know for hotter storage being able to get I mean being able to try to。

呃。Close the gap between， you know， you know， rawduct Db performance and and duckuck Lake performance and you know like for for example。

 in Mother duckuck when you don't store data in duckuck Lake， you know， we store it。

 we have a tiered。Tered storage where itll be you know， memory。

Local SSD remote SSD object store and and that lets us do really fast startup and and can get。

 you know really good performance you know， we're looking into like how do we apply that to。

Apply that to duck Lake as well and being able to cash， you know use that as a duck Lake cash。

 you know perhaps there are some things in you know in just the place in AWS in the AWS family of offerings like in S3 like the you know single zone that。

It could be helpful with lower latency or at least for caching。

 but we haven't gotten too far down that path yet。Again。

 duck like has only been around for for a couple of months These are great answers also like perfect technical CEO answers you like put in this just a right z in the right places so nicelyly done I have one more question but I know yessh under the hand so let him go first and a ask it Let me Steve Moy question Steve Moy ask definitelyput is a catalog So he basically wants to know。

😊，What is the specific methodology that MotherDuck is using to allow multiplay or multi user mode for the DTB catalog？

It's essentially a routing problem and so you know we。SoductDB。

 you know right now only supports single， if you have a database open for right， it only supports。

 you know， it takes any exclusive lock on the on the data and so you would。

Only be able to run one of those processes at once and so effectively what we're doing is we're having the catalog database and we would route all of the requests to the catalog。

 but basically all the catalog requests should be relatively small and lightweight。

 the only alternative the only exceptions would be the inline data and I think we may have to do something special for the inline data。

Got it。 All right， ya， your turn。Thanks， if I understand correctly what you're saying is that all the metadata per duck Lake is stored in a standard SQL table or a center SQL table and that's the openness of it。

Are customers wary of this because if the service provider is providing the SQL execution model for the mandate as well？

Are they worried about transitioning from one to another compared to an open table format where they have all their data in their own object store？

I have not heard any concerns about about that being in， you know， being in SQL tables。

 especially because there are multiple like you can use， you know。

 you can use your own Postgres instance， you can use your own you know it the。

The standard or the duck Lake standard was defined to be implementable in virtually any databases it needs sort of very few specialized fancy database things。

I。So you it is it is quite open and I haven't heard any any concerns with with that I think okay。

 I guess the the portal is trying to。Get more about his like。

If I'm running a duck likeake warehouse and let's say it's not provided by another duck。

 but maybe data virtual or snowflake or someone， who owns the metadata in that sentence。

 is that running as part of like a snowflake table or a data breaks equivalent table or someone or is it why as a customer running my duckflake data have my own SQL table and running my metadata in？

So who owns the I mean it？I mean， if it's running and if it's not running in Mother duckuck。

 anybody can own anybody can own it so any Postgress like you could have your own Postgres that's that you're hosting yourself and as long as that Postgres is accessible from the you know from the Spk job or from wherever whatever you're running running it from you know you' you'll have access so like。

Okay， yes， you might it might be， it might be somebody else it might be an Amazon RDS instance。

 but like。I don't know， do you not trust Amazon RDS to you know。

 be to be open enough like I there's if you're you know。

 if you're super paranoid and want to run you know。

 every line of code based on open source that you own， then yeah。

 you can run your own Postgres server。Make sense I guess I guess I got a situation I was curious about it's like if you have you have snowflake。

 you have datarick you wanted them to interoperate your room to talk to each other。

 So that's why you would use like the iceberg offerings right they write all these manifest files they write these parquet files and they can read each other's data they both commit will maybe not both commit but they can they can at least both read right so in a situation where let's say duckuck Lake was part of the iceberg expect and they were both speaking duck Lake how would how would that work would it be I guess it's expected that the user would host it separately or。

Well， so I don't know about Duck Lake becoming being part of the icebergs back。

 but I don'm not exactly sure how that work， but if like but let's say Snowflake implemented a duck Lakeake connector and Spark implemented a duck Lakeake connector。

 which I think should be in the works and we're starting to work on a sparkk connector just because we believe that that's something that should that should exist even if it doesn't you use Mother duck we believe that you we all win when if duckuck Lakeake becomes ubiquitous and becomes usable from any engine。

 all it takes is is implementing an open source connector and all of these things and then they can all share the same data and metadata。

 they just need access to whatever the D Lake catalog endpoint is。

add you I would I will add that Ben and Yash are sitting at Snowflake right now so they can go implement they can do it Of course that would be a great idea Yeah All right。

 super ask what access control model is implemented in duck Lake and does its fine grain design allow embedding or enforcing access control primitives within individual files？

So Duck Lake does not have any access control as part of the as part of the spec but mother duckuck has added access control it's relatively relatively basic it's just you know as and and the。

You know and and it's actually quite course grained right now as echoles on databases I you know was describing a you know partition level access control that is something that we are。

Working on， we hope to launch that in the next couple of months。Got it so my next question is。

Are you guys running a separate analyze path to fill in all the column statistics。

 are you assuming that whoever is telling Duck Lake？

Here's the files I have and we'll fill that in for you。

I think it depends and this also gets a little bit beyond my knowledge of duckuck Lake。

 but if you're using the if you are。I think if you are writing the data out and you can collect that data as you're writing it。

 then you don't then you can then you can basically you can run a set of you can run the duck lake。

Update queries on your own to provide those the DDB extension the DDb duck Lake extension has has a set of functions that you can call that will go and and generate whatever whatever metadata is is necessary from the from the underlying files it had to be clear so sorry but is mother duck I'm asking whether you guys do that like。

We will do that when。We use the we use the DDb duck Lake extension and so and so yeah we will add add those if you if people don't provide them themselves got okay and as as we're writing them。

 yes we do we do add add those things so yes。And then is there anything anything？

Propriettor is not the right word， but anything that's custom to Mother duckuck。

 you guys are storing in extra stats that like the。

 say the regularduct Tb duck leg extension doesn't do。No， I mean。

 there's a bunch of stuff that we had to do in hybrid execution to sort of。Uh。

 to make it to make it work nicely， but nothing that's like specific that's going to make it run run faster or better。

Got it， okay。All rightAny last questions with the audience？All right， so my last question would be。

 if you had a magic wand and you could solve any engineering problem at Mother duckuck or Duck Db。

 but you know， if you want to think about Mother duckuck， that's fine。

 what would that be And you maybe think of it like what a oney magic wand fix and then what's like a fivey thing you would you guys tackle right away。

嗯。呵呵。😊，WellThat's a good question。😊，呃。I don't know， I feel like we just have a bunch of duck Lake。

Roadmap work items that that are all queued up and like I would love， you know。

 if those could those could just sort of magic， you know， all the stuff that I've described be。

 you know， be magically shipped completely， but you know， it's going to take a little while。



![](img/e6dfc793c4f65a13598bb2b1e15b404b_7.png)