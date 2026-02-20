# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p02 -02-S2024 #01 - Modern OLAP Database Systems .zh_en -BV1HZ421N7WZ_p2-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/7820a5a5fc169f97132ecf8447c1c8ea_1.png)

。🎼P classes。🎼beginninginning of discussion of the lecture material throughout the semester。

 and it's still sort of a high level overview of OAP databases。

 but the idea here is that we will set the foundation for all the various parts of the systems and the papers we're going to talk about like how to build these individual components in a modern system and then obviously this is highly related to the projects that we'll be working on we'll discuss at the end but this sets the ground。

 this sort of sets the context in which we will build all the things that we'll talk about throughout the semester。



![](img/7820a5a5fc169f97132ecf8447c1c8ea_3.png)

So。And when to first talk about again， the basic background of how we ended up with the purveying architecture for a modern OLAPP system。

 we talk about some high level choices and issues in this space。I started early， sorry。Yeah。Swhere。

 yeah。Right， yeah， so the idea again， the idea is that we want to sort of talk about。

What some historical systems look like how we end up with what people build these systems today。

 and then we'll talk about the high level issues you have in building one of these systems and then we'll finish off with just sort of a quick overview of what a query goes through and what happens when you actually execute a query in one of these systems okay？

And again， this is a grad level class， stop me and ask questions as we go along，right。

 so if you recall from the interclass， we made this distinction between these operational databases or front end databases or OTB databases and these analytical database systems or OLAP online analytical processing systems。

And then the distinction was in an OTP system， that's really the thing that faces the outside world。

 either humans or computers， a little web interface or rest interface that's ingesting new information like you're getting new state。

 you're getting new changes and you want to store that as quickly as possible。

once you sort of accumulated a bunch of this data now you want to start extracting new information from it you want to extrapolate new knowledge。

 allows you make decisions or decide how to do certain things or provide justifications for whatever it is that you want to achieve in your business or your institution your organization or whatever so that's the goal we're trying to do this semester trying to take a bunch of data what you've accumulated and then run queries or run something on it to pull out new data that informs us about what our database actually contains。

But ideally find trends that we didn't think of as humans easily。So in the old days。

 people would run these sort of analytical workloads on what I call a monolithic database system。

 meaning a system that was had all the components and all the subsystems to actually execute queries and store data was's all built inside this one piece of software if you ever run like SQLL or likeductDB or MySQL Postgres。

 that's considered a monolithic system。For an embedded database is less so because they don't have threading and so forth。

 they like they of like Postgres you install Postgres， you put it on your laptop。

 put it on your server， you start creating tables on it。

 everything you need to do actually queries and store that data is inside of Postgress。

So these monolithic database systems was how people were storing the data in the old days and let's talk about what this means by centralized storage。

 but like a managed storage， basically the database system is completely in charge of thes what bits are getting written down the disk。

 where they're going and how to pull them back in。So the first set of work。I shouldn't say first。

 because there was tearada from the 1970s sort of built in the space。

 but people started really paying attention to analytical workloads in the early 90s， maybe late 80s。

But the prevailying architecture at the time for helping people built database systems was again the classic database system architecture we talked about the intro class。

 row store， pages on disks， it's a buffer pool fetching things in because that's how they were building for operational workloads a row store is exactly what you want if you want to adjust data very quickly whether in transactional manner。

But obviously if we want analytics， that's going to suck because now if you're doing OL queries。

 we only read a subset of the data， you're fetching in the entire page。

 you're fetching in the entire row， and there's going be a bunch of data you don't actually need。

So people realized that these were kind of slow， and so they started building what were called data cubes。

And you sort of think of these as like just like a materialized view or pre computer aggregation query。

 like group and so forth across bunch of different dimensions， and you would generate this。

There array more or less， store that in your database and then any analytical query that came along。

 you would then try to target that data cube because it's already done a bunch of computation for you。

 and you could store these things in an array manner that was better than a realtor。😡。

Right so these things were not automatic。 an administrator had to specify I want these precomputered cubes again。

 just like materialized views or regular views and then because materialized views are trying to certainly at the time before time the 90s definitely still now they're difficult to do incremental updates on you had to have a human say manually refresh like a SQL command to populate the data cube so like you would do something like a cron job at night。

 know run the refresh to build the data cube。So these were introduced in， as I said。

 in operational databases as a way to be able to handle faster analytic queries than which you would do over row oriented systems。

 So with the exception of tar data， and this is the logo for S base with Oracle boughtt and like。

I think 2003 or so， like SQel server， DB2， Cybase， Oracle informforms。

 all of these guys had their own sort of variation of data cubes。 Terra data did as well。

 but Terra data was primarily a ellse system back in the day。One of the first ones。

 actually the first one。So basic idea is this。 You have your OTB databases， your operational work。

 this is where you're getting new data。 And then somebody wants to run some you know。

 query like this where they have a cube function in the group I clause。

 And then all you're just gonna do again， just do a sequential scan in each node。😊。

Populate the cube for this。 And then when this query shows up， if you define this as a view。

 you would do the query on the cube。Just again， think of like precomp aggregations。

 that's all it really was。So what really changed and got us on the path towards where we're at today was in the mid earliest 2000s where people started building these specialized database systems called data warehouses。

 that were specifically designed for analytical workloads。

 so even though a lot of these started off as fork of Postgres we can go through that a little bit。

 but like even though they were mostly derived from row storage systems。

 they ripped out a lot of the storage internals， they ripped out of the executionion engine and replaced it with something that was targeting columnoriented column oriented data。

So all of these except for data Lero and Monet are forks of Postgres Par Excel is what as Redshift is based on。

 so we'll cover the Redshift paper later on， basically Amazon bought a license with the source code and then hacked up a lot and that became Redshift NoadDB was written from scratch out of CwiI DDB originally derived from MoonadDB there was a version of DDB before DDB called MonadDB light。

 and then they threw all that all the way and then they rewrote it asductDB。

Vertica was started by Stunbreaker and others back at MI and Brown that's a for of Postgres data Legra was hacked up was was middleware in front of Ingresss。

 Microsoft bought it for like I think a couple hundred million and they immediately threw away because apparently was garbage and then teas was early one。

 this was actually pretty cool。 This was a version of Postgress that had an FPG accelerator to do the accelerated sequential scans。

 Greenpllums still around today pretty widely used That's a fork version of Postgres so like these are all these monolithic systems where they were designed now to run in a little workloads in and control comp storage layer of the system and and they sort of used their own proprietary formats and that'll make more sense especially next class。

 but basically again they were in charge of what the bits look like on disk for the pages they were storing for the data。

The other thing to point out is that all of these were all shared nothing systems。

 we'll cover that in a second， but again， they were assuming that every compute node in your database cluster had disk。

 memory， and CPU， and each node was responsible for sorting some portion of the entire database。

So the way you would use it sort like this is again you have your OTB databases now you have your giant data warehouse and the idea is that you wouldnt get all your operational databases。

 all the data from here back into your single data warehouse because now you have a single view or complete view of all the data across all of all your databases and so the way you would do this is using tools called extract transform and load or ETL tools and you just sort of get the change data capture or periodically getting updates from the OTB databases。

 doing some amount of changes to them to clean up the data like entity resolution if it's a Plo and AndDP。

 you can figure out that they refer to the same person all that sort of happens here and then you load this now into your data warehouse。

Right。But again， for this， because the data warehouse wants to have complete control of everything it's storing。

 youve got to set up the schema ahead of time， youve got a provision in the hardware ahead of time。

 everything has to be sort of set up before you start putting data into it。

And it was a shared nothing system， so if you want to scale the capacity of the system。

 you have to add more node and now you got to start moving data around。

 and that's maybe one of the limitations we'll see throughout the semester。So then we hit the 2010s。

 late 2000s， early 2010s is when these things took off。

 We entered this new era that we're sort in today of these shared disk engines。

And the idea here is that instead of having the database system manage its own storage layer。😡。

We're going to offload that to some other piece of software， some other service。

And in the cloud setting， it's going to be an obvious store like S3。All。

And the idea here is that because we no longer to be responsible for managing the storage of data。

 we can optimize the compute layer as much as possible。

We're still going to have proprietary data formats。

Meaning like if you're using snowflake regular snowflake was sort of the first ones in this space。

 Snowflake， when you store data into it， it's going to store it in the snowflake format that only snowflake understands。

 but it's going to store it in S3。喂。So that was the first generation of these systems like they're going to manage all the files themselves。

 the newer generation and what was in the paper that you guys read that sort of fall under this branding label or moniker of Lakehouse systems。

 the idea is that it looks just like a shared disk system row4 but now instead of having always using a proprietary storage format and only allowing data to be added to the database by going through the database system you allow anybody to write a bunch of files out on S3。

 tell the database system， the Lakehouse system hey， here's my files， here's what's in them。

 and then now you can run queries on top of that data。Yes。

So on each slide we have all these different products and companies I' what you say they mostly？めていく。

That that that。Why there's so many。So his question is。

 I'm showing much of these logos at the bottom here， why are there so many。

 what are they competing one？I mean， the reason why there's so many of them because there's so so much money in databases。

 right， like that'ss why there's a lot of this， you know， you know。

 there there's Linux and then what else。We had a lot of naism， right？😊。

So the key difference is going to be in， I think some of these will be hosted services that you can only get through a certain cloud provider。

 like an Amazon Redshiftft， you can only get Amazon Redshift on Amazon。With BigQuery。

 I think they have called Omni something or other， you can now run BigQury stuff on AWS and Azure and so forth。

But like for whatever reason， people start building database systems because they think they can do a better job than what already exists。

 And oftentimes， some of these projects are actually spin out of larger tech companies that decided。

 oh， we want to build this stuff in house and then turns out to be useful。

 and then they covered to an open source project and get people to use it outside of it。

 So Presto started that Facebook。 Ps started that at LinkedIn， Trinos and For Ca Presto。Drewid。

 I forget this came out of something as well， but。For whatever reason， people start building know。

 these various systems。 And I would say at a high level， for the most part。

 as we'll see throughout the semester。The high level are all going to be basically the same。

 The real differences is going to be the things that actually really matter。 in some cases。

 it's going to be the top layer， the front end， like what the user experience looks like and how good the query optimizer is。

 In my opinion， that's the part that really matters。

 All the stuff that we're talking about through the semester。

It becomes almost commoditized or comes table stakes。 Everyone has it。

 We still want to learn how how to build it and and why they do certain things and and why they perform the way they perform。

 like that part is still super important， especially if you want to work on the internals of these systems。

 but the。To the average user， it's really the top part that really matters。

So another way I say is like， are there too many databases？Maybe。は。But I said。

 there's still a lot of money that you know， in the marketplace for this kind of stuff。 And people。

These things don't die。Inala I didn't really take off as much as like Snowflake did。

 They're still maintaining Aalla， still people using Paula。

 but I recommend anybody starting off using Aala， no。But it's still there。Yes。

Are these the same or different from data lakes is what I read？あ、ゼロワスである。Yes。

 the question is is what I'm describing here the same as a data lake。

 The term data lake basically meant is that like okay。

 here's S3 anybody can store data in there right But then the lakehouse architecture see in a second。

 It does have the ability to ingest data through this lake house and keep track of things but also provides additional like schema control of metadata stuff as well。

 So like the data lake the idea was like okay dump your files S3。

 and then whoever did that is also responsible for telling the catalog here's my files with the lakehouse architecture supposed to be like a unified front end interface to the developer and say okay here's my new data and then the lake house can put it where it wants it or like you can tell it here's where it is and sort of keep track of these things。

 So it's not to say you couldn't build。Ignoring the incremental updates we'll talk about in a second。

 it's not that you couldn't do what a lakehouse does on a day like。

 they're essentially the same thing， there's more services to help you keep track of what's going on。

I was wondering when we said shared disc。認定六。So the data lake would just be like his question is。

 when I say shared disk， do I mean data like， I mean。

 share disk could be the distinction between shared nothing。

That you have the separate computing storage and you rely on the object store to store your data。So。

You could do that in some systems you know before like Databricks is likehouse stuff right。

 but the idea is like there's much more manual stuff you have to do like if you just dump about files in S3。

 but nobody knows about them， then you can't run queries on them。

But so that means you would have to update the files in S3 and then tell some catalog service。

 here's what my data is so they can then run queries on that right so it would be like a manual process the Lakehouse is trying to do all this sort of automatically for you。

It's a marketing term in some sense， right？The data like this means is like， okay， here's S3。

Put my fathers out。But the important thing about this is though。

What this allows you to do because it going to be a day lake or an object store。

 like I don't have to go get approval from the DBA to say。

 I want to store this data and I spend time setting up the schema and figuring out what's going to be in there and provisioning hardware。

 you just start uploading files。And then。You know，For better worse。

 like that makes it easier to put data in there。 But then now someone's got to figure out what's actually in there。

 right， So you're sort of pushing the burden of figuring out。

How to interpret the data in the contents。Later down the pipeline， and some cases that's a good idea。

 sometimes' a bad idea。And that's when it's like a philosophical discussion。

But the key thing here is that we're separating compute and storage by using a shared diskarative。

So if we go back to our sort diagram before。Now with OTP databases。

 they're going to send all their data to an object store and maybe there's an ETL thing or some kind of middleware here that's going to do some transformation before it puts it in there。

And then we would maybe tell the catalog， here's the files that I put in there。

 and here's their contents， so here's maybe the schema that's in there。And then now if I run queries。

 the query engine on the side' not responsible for the storage anymore。

 so it has to go to the catalog and say what data do I actually have。

 and where are the files located in S3， and then once I have that information。

 then I can run my queries on the object store。So in this semester this box here is what we care about。

 this is the thing that we we're actually going to design， this is what we call an OLAP system。

 whether it's a lakehouse system that it comes with additional stuff that Databricks wants to sell you。

 but this is the thing that we described conceptually and how to build。Right。

And this is the way people have been really building these systems for about 1010 years。

 15 years maybe now that started off with like Drmel at Google and then Snowflake was the one that really commercialized it。

 Like this is the sort I want to call it a classic architecture。

 And I realized that you guys are in the 20s。 and I'm saying this 15 years ago。

 in the script of databases that's actually not not a lot of time。 Yes， about the of。😊。

Davis is to like。Da timetamp or his question is we were going to talk about like this this。

It's called change to capture like how do we get the updates from this into this we're not going to talk about that specifically like what the process to do that I can point you to some previous lectures that we've had guest speakers talk about this we are going to care about like what the data is going to look like when it goes in there and that's the next class like parquet and orc files right。

Yes。Just to follow up to that question。The paper mentioned that the lakehouse architecture addresses the problem of sta aid。

It。Updated frequently in the objects。Yes。Next slide， already sorry next slide， yes。So David is like。

 in the Lakehouse paper from the database guys， they talk about。

 oh a big problem with these data lake systems is that you get stale data because again。

 we're getting continuous updates from the operational side of things。

 how do we integrate that into our into our our database so that we're always trying to look at the freshest data And so what these data lakehouse systems provide also is the ability to do transactional updates creation deletion updates。

 insertions into this database。 And the way you basically do this is that it's the fracture mirror stuff we talk about less semester。

 You're just doing a log ofend to a file。 here's all the latest changes。

 And then there's a background job that periodically kicks that coal lessons that combines it removes out stale data。

 and then stores it now into parquet file for the case of data。😊。

In whatever the Delta Lake thing from Databricks， they'll take that thing parque file and then store that now into your object store and then update the catalog say here's the latest version of it。

 They also can keep track of if you make schema changes， they keep track of those things for you。

 it's providing more， as I said more infrastructure to make sure that the object store can keep track of what's actually in it。

So we're not going to talk about any of this this semester。

 Delta Lake is one one example of the system。 I don't know whether the paper mentions Hoy and iceberg。

 Hoy came out of Uber。 iceceberg came out of Netflix。 Snowflake has their own sort of thing。

 I think we call hybrid tables incremental updates。 they support iceberg as well。

 This logo without a。Without a name， it's actually Google Napa。 They have a paper on this。

 Google doesn't only put names next to Los。 It's really Amazon， too。

 Like how hows Amazon going to know what this is， right。So in their defense。

 that's actually an internal system。 they're publicly talking about it now。

 like we're not going these things this semester because we really want to focus on how do we run all that  queryries as fast as possible。

 And once we have that， then we can we can go beyond that and build this deelta update stuff。Okay。

So the paper you guys read， they make a bunch of different observations she mentioned them one about the stale data。

 but I want to point out the three things that we' going to keep in the back of our minds as we go throughout the semester to understand and guide us on how we make decisions on building a system and again。

 even though beyond the semester you may not go off and build data system internals。

 but these are the things you sort of think about when choosing maybe an OLAP system in whatever your next project is at startup or wherever you go next after you graduate here。

So the first thing to point out is that in a modern setting in modern organizations。

People want to execute more than a SQL queries。 Now， I realize as someone who's like a SQL maximist。

 where I think everything should be SQL。 This seems like heresy to me， right， But I'm not naive。

 I know that people you want to run pie torch and Tensorflow and all these other M workloads that。

Aren't you know that you can't easily express in SQL Now there's projects like Post SMl that gives you UDFs to make calls into Pytorrch。

 but most you aren't writing that， most you are data scientists that are writing stuff and notebooks。

And so， the access patterns for。ML workloads， for example。

 are going to look a lot different than O that queries or SQL queries。

And we'll see this later in the semester when we talk about the networking protocols for database systems that sometimes you want to do a bulk export of data without having a retreating exactly as it exists in memory from the database system rather than having covered it to a result format that you can then read as if you're going through JDBC or ODBC。

And so maybe you want to get things out of an Apachearrow format。

 which we'll cover throughout the semester。And that's relevant to the projects。

We'll design our system， most of the parts of the system。At sort the planner level or down。

Ml workloads are gonna look a lot like， you know， Python workloads a lot like SQ workloads。

 All that's gonna be the same。 It's the front end part to have was same before that that we only even expose different APIs for how people want to get data and run queries。

The other point thing is that， as I said already， that because of these shared disk architectures。

 that it's no longer having the data system having rigid control of exactly what data is going into the database and how people can get data out of it。

 because now it's just files in S3。And ignoring any governance or any security permissions of how people could get to those files。

 if it's just files in S3， then we don't always have to go through the front end of the database system to do anything with our data。

RightBut that doesn't mean we still don't want to track schemas and versions of the schemas and what files actually exist and the catalog is pivotal thing that makes us all work。

 but because now anybody can put things in S3 in theory。

 you don't have to go through that full bureaucracy that I mentioned before。

And the last one is that as they point out and just think of your own behavior on the internet。

 most data is unstructured or semistructured。So unstructured to be like an image or a video file。

 just I think most of the traffic the Internet is from YouTube or video video video files。

 And then a lot of it's also gonna look unstructured or sorry semistructured。

 So this means something like JO files or a combination of structured data like， you know， a tuple。

 But then there's some JO portion or maybe raw text from a from a log file。😊。

A lot of the data is going to come in this format。For unstructured data。

 we're not gonna to talk about anything about this this semester。

 like that's taking like a transformer or some ML framework that then extracts information about what's in an image or on a video file。

 right， But anything thing it spits out after you do that transformation is going be structured。

So for SQL purposes， it's not much that we can do for this for semistructure。

 this is going to be a big issue that we have to care about like because people are have to dump a bunch of JSON files in S3。

 even if it's in a structured file format like a parquet or orc file。

Wwhich we'll read about next class， then like we still have to be able to make sense of it。

 and this is a good example where we'll see some systems the different systems will do different tricks to make it work efficiently for this。

Snowflake， I think they assume that the data is always going to be there。

 so they generate columns for this， data bricks， I think they do parsing on the fly。

 there's a bunch of different ways to handle that and we'll see that how we do that throughout the semester。

So again， we， we want to design our system keep keeping these things in the back of our mind。

 and we'll see throughout the semester how we do each of these。

The other interesting trend that has come out in the last decade is that。

We've gotten away from these monolithic database systems where now people are building services or individual components that are separate from the full system and it's basically how sort of laid out the project this semester that in theory。

 these different services could be developed independently long as they expose and maintain an API that the other services can understand and use and is stable then you could start swapping these things in and out or not have to build the entire system from scratch。

 you could use some off thes shelf tools to build a fullflged database system。 again。

 everything in Postgres or everything inductDB is or SQL light is written by those developers。Right。

 ignoring third party libraries for like， you know， SS。

 SL and things like that that's obviously I' not what I'm talking about。

 But like the query optimizes of the catalog and the parser， all of that is。

 is built by the the system developers。But now what we can do instead is in theory， use some。

 again off the shelf tools and collarbble them together and still make a full feature database system。

The challenge is going to be， though， obviously， the basic software engineering principle。

 the more abstraction layers you put in place， the more efficient inefficient the software will become。

Just because there's intimate knowledge about what the system wants to do at any given level and if you don't expose that information up and down the layers of the sulfur stack。

You end up doing the lowest common denominator。Yes。

 do we know how costly it is to like add these like like separation layers between the different components as opposed to having？

This question is， do we know how cost it is to start using these。

 these different services versus having everything bit written in scratch？ No， I mean。

 I mean hard to study， hard to study， though， right， Like it's like， hey。

 like have two teams build like a multi millionillion dollar。

Right projects just to see whether one's better at the end like this。I mean。

 some parts are super hard， too。 Like the query optimizer is' the hardest part of it is most people can't build that。

 and they do end up building it。 The first version is is is usually a bunch of heuristics。

 if N L statements is garbage。 And so in the case of Que optimizer。

 I we have a project going in this class， There's been two other attempts of built standalone services and query optimizers。

 there's there's Calcite from Luc Db。 And then that's probably the most common one。

 And there's Orca from the Green plum， the Mware people。

But like actually there is a paper about the effort it took to get orca to work in my sel。

 apparently was a huge pain。Because there's assumptions about these things。 I mean。

 this is my last comment here。There's a bunch of challenges in co these things together。

 it's not just like， you know here's the HTP protocol and everyone。

 every web server speaks and it's easy to combine these things together to if you ever use like a RE API from any service like oh。

 they want to data it this way but thiss other way becomes a trademark wreck real quickly。

And so making these things actually talk to each other and actually making it fast is nontrial。

So we'll see how it goes for the project semester。Another important thing that we're going to cover。

 too is what the， the intermediate representation of the IR looks like for。

The various parts of these systems that are talking each other。

 And so I'll show in the slide next slide what I mean。

 But like I've already sort mentioned this in the project right up that like， okay。

 there's there's there's the query optimizer and this can generate a query that it hands off to the scheduler。

 Okay， well， what is actually handing the schedule needs to know what's actually inside the queries in order to make sense of what goes where So how do you actually represent that。

And then now， like how does you actually represent data。

 what do the data types across these things need to be synchronized。 But again。

 if I'm using off the shelf components written by different projects and different teams。You know。

 they might have 32 bit ins one way and then all ins might be 64 bits and other one。

 fixed point decimals is another challenge， like how they actually store the data itself can become jumbled up and difficult。

We'll talk about file formats like this class， and again we'll talk about execution engines。And。

 like a little exction fabrics。 I think of like， you know， Apache Ray， like that kind of stuff。

 We'll talk about that later in the semester as well， but its。There's a bunch of these stuff。

People have talked about hey， there's all these existing things because I just cop together a Java database using all this Java stuff。

 none of them have really taken off， I think they've only been like toy exercises。

And this paper here that I'm referring was optional。 This is from the Facebook guys。

 the Voltron people， basically they're arguing that this is how people should be building data Sisms today have had these standalone components that interrupt。

All right， so here's a high level overview of what。

The internals of one of these OAPP systems look like， given the context that its describe。

 and essentially it's going to mirror how we're sort envisioning the projects are going to work out this semester。

So at the very top you have some user， they're going to send a query。

 assuming it's SQL to a front end part of the system。

And this will have like a language parker or a SQL parser that's going to convert the SQL query into a bunch of tokens that specify its form。

And then now we're to send this intermediate representation of the SQL query to some planner。

And the planner is gonna to have a bunch of different parts。

 I have the binder that's going responsible for figuring out like refers to it there's a token refers to a table name。

 did that table exist in my catalog， can I do some rewriting of the query to put it into a better canonical form and then I'll have an optimizer that could do a costbased search using cost models that are derived from the data itself to help figure out what's the most optimal plan。

And so for this part， the planner， we got to call to the catalog。RightBecause we got to say， okay。

 again， I have this token。 It's table Fo。 Is this really a table。 And what columns does it have。

 What's the data type， Where's this data actually being stored。

 Do I have any statistics about that data that I can then feed into to my cost models。

Then now I have。I now have a physical plan。That I can actually execute my system。

 I got to hand that off to a scheduler， again， represent it in some intermediate form。

 and the scheduler can look at that and say， okay， well， you want to run this。

 this plan for this data， Let me go to the catalog and figure out where the data is actually located physically or who's responsible in my cluster for actually executing that data。

And then I now dispatch it to an execution engine， ignoring how I distribute the query out。

 who's responsible for making sure the compute node are always running， all that we can ignore。

And then as I'm executing my query plans， my operators。

 I may have requests to go get data from storage。 and so I'd have an IO service that I would make requests to。

 and then that IO service is responsible for going out to storage。

 I'm not saying or defining what it is assuming S3 assuming some distributed file session could be a local disk doesn't matter。

 And then it's going to go fetch this box and then hand it back up to the executionion engine can then compute whatever it is that it wants to compute。

And then when I produce my final answer， then it goes all the way back up to the stack to the end user。

There other two things that are happening at the same time。 again， the catalog is super important。

 the execution engine as it's scanning data， as someone asked on Slack。

 should my query planner actually be responsible for looking at the files and figuring out what's actually in them No because then you have to have duplicate code or redundant code have the ability to scan data the execution engine can just do this because an analyze command in SQL is just a sequential scan but then it can update the result to to the catalog Now whether or not it goes through the scheduler or whatever the coordinator to send this back over。

Does doesnn't matter， but I'm just showing that the execution engine can derive new information that isn't just for the query。

 it's actually for the contents of the files and go to the catalog， yes。じゃあち八ます。

We know basically what statistics？Sure， yes。But who， but that's。I mean， it's it's a command， right。

 say I need， I， I have some files。 I don't know what's in them。Schedule。

 go tell someone to do it for me。It's another query。But the query is coming from this。

 not from somebody at their desk。Yes， so we're thinking about is put this。That's polling， stuff。Let。

 let's cover that after class。 Yeah， okay。Other questions。Okay， so again， same thing IO service。

How we actually going find out what files are in there。 again。

 you could have a command that go through the front end tell the catalog。

 maybe the IO services is seeing some stuff and can send it over， depends on the implementation。

But again， going back to the comment I said before。

 the thing that's' responsible for actually knowing what's inside of the blocks that I'm getting from disk or my object store is going to be the execution engine。

Because otherwise， you have a bunch of redundant code， you have people running some stuff to go。

 you know， a bunch of threats up here started reading data。

 and that they interfere with what's going on down here。Right。

 I don't think we're reading any paper specific about the catalog。

 We'll see how as we go through that semester bump implement this like Snowflake uses a whole other database system。

 They use foundation D to do this。 This is basically a whole other database system。

 And all you want to be transactional。 You want to be fail safe。 You want to be high performance。

 this is a whole other problem in itself。 and I want to talk about how we do this first。 again。

 before we do the lakehouse stuff to do updates on top of that。😊，Because once you build this thing。

 then you can build that additional incremental update part。ok。So let's say what a highlight low。

 Okay， that's the context of the conception of what one of these systems look like。 Well。

 what actually happens when I execute one of these queries。So。For this semester。

 although we're going to be the high level context of what the system we're describing is going to soon to be distributed。

Snowflakes distributed， redshift distributed， all of these systems that showing。

 throw all scale out distributed database systems。But we want to walk before we run so most of the papers。

 almost all the papers we're going to read are really about single node execution because at a high level。

 distributed query execution is the same thing as you would do on a single node。

Moern CPUs have a bunch of cores， sometimes you have multiple sockets。

 and you have to care about pneummer regions where are the actual memories being located for each socket。

So all that is still going to be the same， which is when you go distributed。

 there's a bit more extra work to say， okay， well now I need to send data from this node to another node。

 well that's no different than sending from this CPU cord to this CPU quarter。😡。

It's obviously potentially slower。Then going going over the network。 But at a high level。

 the key concepts I'll be describing throughout the semester are the same on a single node as distributed node single node versus multiple nodes。

So the query plan is going to be ideally a dag of physical operators。So some systems。

 and data fusion is one of them， it's actually not a dag， it's a tree。

And we'll see later in the semester， well that's going to cause problems when we need do nest queries a subqueries because you want to be able to rewrite or maybe reuse computation from one part of the query for another query。

 but if it's a tree， you can't do that。 So ideally you want things to be a dag and not all systems actually do that。

And then the data system is going to look at the query plan， figure out what data it needs to access。

 where it's coming into an operator and where it needs to go next。

 and it's sort of going to figure that out all ahead of time so that when you run the query，😡。

It knows exactly how to orchestrate and schedule things and where to send stuff。

We'll see a little bit how we sprinkle some adaptivity in this process where we can make changes on the fly to the query plan and how we move data or maybe scale things up and down based on what we see in the data。

Because that's going to be a big theme throughout the semester。

 again in in this data lake or Lakehouse world with the object store world。

 you may not actually know what's actually in the files because you haven't done the scan on it yet。

 so your estimations might be wrong so maybe you underestimate or overestd different parts and you want your system to adapt a little bit。

Yes， be else can it be tree？Puscuss is a tree Yes what do you mean but what does the tree look like where the like a dag。

 you could have one particle or another one， Yeah a tree where you only have one parent。嗯。Or dad。

 you can do some competition here for like a nesttic query and then send it to two different parts of the tree。

Or of the qua plan。Okay。So this again， this will be a high level overview of what。

This is going to actually happen now in the executionion engine with the IO servers when we actually executeed queryium。

So again these are our worker nodes， they'll have local CPU， local memory， local disk。

 and then they're going to retrieve when the query starts。You know。

 think of the leaf node of the query plan， like sequential scans and so forth。

 that's going to go at what we're we're going to call persistent data。

 And These is the underlying tus that are in our tables in our database。So again。

 whether this comes from the IO service through local disks or from the out store， at this point。

 it doesn't matter。So all now the worker knows they're going to do some computation for our query plan。

 and they're going to produce intermediate results。😊，So these iterate results again。

 are the artifacts that the operator generates that needs to go to the next stage of the query plan。

 and again， we're going talk about this throughout the semester。

We'll assume that the unit of work for our worker nodes when we actually to query is going to be a pipeline。

And then we have to obviously stop at a pipeline breaker and then potentially distribute data around as needed。

So the way we would distribute data around is one way to do this is through shuffle notes and the idea here is that you hash whatever some partitioning key is on the data that you're scanning that you're producing immediate results and then you distribute it across them to these shuffle nodes。

And then this is sort of again， this is think of this as the pipeline breaker。

 And then now the shuffle nodes are responsible for distributing this data to the next stage of the query plan。

 the worker nodes。 right So there's really no computation being done here。

 It's just basically in and out， like storing things as a key value pair in memory and then sending out to the worker nodes。

I'm saying this is optional because most not all overlapAP data systems do this。😊。

BigQu and Drmel is probably the most famous one that does this。 And Google does insane stuff。

 They actually have specialized hardware on these things to keep everything in memory and runs as fast as possible。

 And it allows them to do a bunch of tricks for scaling things in and out because now you have this pipeline breaker。

 You can go and I thought the data is gonna be to this size or this amount。

 But actually have this amount， Do I need more nodes or less nodes。

 Should I change anything up in the query plan。 Yes。

 so this like pipelineer place insert adaptability into your query Yes。

 statement this as a pipeline breaker I this a good。😊，就。I'm saying stop point。

 it's a point in the query plan where you can say， okay。

 let me reassess what is coming into me and do I want to change anything upstream so Google does that here。

Yes。So this idea some of this ideas comes from the mapreduce world。

 they would have explicit shuffle phase， but the difference is in the mapreduce world if you' familiar with things like Hadoop。

 which you I don't recommend using， you don't want to use that anymore but like in that world it was all batch base meaning you had to accumulateulate all the in results of the shuffle phase before you can start the next phase in a modern overlapap system。

 you can use in a streaming manner。 So as the data arrives。

 you can start pushing it to in a streaming fashion up to to the next worker notes。

 start executing right away。 having this sort long pause。😊，The other thing point out too。

 for the simplicity of sharing this in PowerPoint， I have the same number of worker nodes as shuffle nodes。

 you don't need to do that， like you can scale things up and down accordingly。

Because sometimes the amount of intermediate data could be larger than your persistent data。

And we'll see this later in the semester。 when you do worst case optimal joins that the energy data balloons to be much much larger than the persistent data。

 even the final result will be much smaller， but this thing can get quite large。And then now again。

 we do the next phase， these worker nodes produce more intermediate results。

 and then we send this now to some final node to do some final coalescing or aggregation to produce the final result that we send back to the user。

And so I'm not showing this here， but the thing that's above all of this。

 keeping track of what's going on， what workers are still alive， what stage they are in execution。

 how much data they're generating， that's the scheduler in the coordinator， all above this。

It's different than like the orchestrator in like Kubernetes because Kubernetes is just like seeing is the pod still up。

 doesn't actually know what's going on the inside of it。

 That's you have to build that ourselves in our data to keep track of like， okay。

 what are you actually doing？Because Kubernetes again， can't see inside the query。

So I've already sort of said this， but the distinction is between persistent data and metter data。

 persistent data is the source of record for our database， again， could be bunch files in S3。

 it could be private proprietary stores that the data manage itself， one key thing though。

 is that all these modern systems because you assume you're going to run on something like S3。

And S 3 is immutable。 And I can't store file or object in S3。

 and then go back and make in place updates to particular by。 If I want to do that。

 I got to overwrite the entire thing。And so that means they're augment using sort of pen only architectures for how they design the data encodes and stored formats。

 That's sort of the thing I mentioned the Lakehouse before， like log structured bunch of changes。

 I think it might distort as JSON and then they batch it together and then store as parquet because it's one right out to the outdoor store。

For the intermediate data again， these are shortlive artifacts that we're going generate as we execute the query and because they are only really useful for the lifetime of the query itself。

 we don't have to worry about durability and fault tolerance and the same way with persistent data Now with persistent data because again assuming we're running on an object store。

 they handle all that fault tolerance and resiliency for us， which is again。

 one less thing we have to worry about as we build a database system for the intermediate data。

 we're responsible for maintaining it， ideally， we don't want have to store it on S3 because that's slow and cost money So we'll try to keep this in local caches。

 either in memory on disk but again but if like a node goes down we can handle that we don't have to wait make sure we store a good jillion copies of ind data because who cares when the query is over。

 we throw it away。There has been some research in maybe reusing intermediate results from one query to the next。

No system， as I know， actually supports that because if you wanted to do that。

 then you just define a materialized view because it's basically the same thing。Yes。

 when you say little to no correlation， the amount of persist in data you。

Operator like is there not like a strict upper bound or the amount of data you could generate from weight？

The data。His question is， I haven't got to yet that。

 there's a comment here that says that there's no correlation between the amount of intermediate data a query generates。

There's no correlation between the size， of the persistent data that they're reading in or the execution time。

 So this， this， this result comes from the snowflake paper from22 or three years ago or last year。

 but they looked at all their all the queries they actually executeded in snowflake。

 And they saw that this wasn't the case at all。 right？ And so your statement is， oh。

 could it just be an upper bound。Where I know that the max limit of the amount of de I could ever generate。

 Well， no， right， because my query， I can do anything。 I can do， you know。

 look a billion times and generate a bunch of random stuff。It costs you money。

 you be stupid to do it， but you could do it， right。And the challenge is going to be， again。

 for query optimization is to know when this is going to happen。

 when like you have an operator that's going to generate。

More intermediate results than the data going into it， because you want to use that to figure out。

 okay， what join algorithm should I use， worstors case optimal or a hash one。 Again。

 I keep saying this we' covered。Pated this measure。 I mean， hopefully， again， I I。

I remember when I was taking classes back in the day。

 like the professor would say a bunch of stuff in beginning。 like， what the hells he talking about？

 And then later on you see oh， yeah， like you learn all that stuff and it clicks。

 So I'm bringing this stuff up now because when we hit those lectures oh yeah。

 that's what he meant by this。 worstors case optimal joins。 Okay。

 now I know what that is's it's a prelude for what's the common。

 hopefully you see I'm getting excited because Davis is awesome。😊，So the。

The other thing that they consider now to in our system architecture is。

The way in which we're going to transfer data between different operators the nodes and it's really going to come down to where that persistent data is actually going to be stored。

 and again， the highlo details like if it was a shared nothing system which we covered in a second。

 you primarily you push query to the data in a shared data system。

 you would think of primarily by textbook definition， pulling data the query。

 but we'll see in a modern setting， these lines get blurred very quickly because for the8 results。

 you actually want to you push the query to the data sometimes in other cases you want to in some object stories you can actually push the query to the data down to the actual object store other cases you start moving things around like it can get jumbled so there's not really clean divide between different models。

 which it's going to understand them in the context of the system that we're trying to build conceptually in our minds。

So the push approach again is that the idea is that the query itself。

 either the SQL string or the intermediate representation of the query plan。

 is going to be much smaller than the data， so why transfer a bunch of data over to the node just to execute it。

 why not descend the query which is much smaller over to where the data's actually being stored。😡。

And I can do the processing there and and then send back the intermediate results。

 which ideally should be smaller than the persistent data。

And so this made a lot of sense in the old days when disk was super slow and networking was super slow。

Right and usually the network is always considered much slower than the disk。

 that's not really that true anymore。 The hardware has gotten really good。

 So the challenge in this space， though， is that you may not have the computational capabilities on wherever the data's actually being stored to do any processing on that side。

Again， you think of using S3。If you ignore the select operator， we'll talk about in a second。

 like it's just the APIs get put and delete。 you can't say， oh， by the way。

 also execute this part of the query plan for me。 you can。 we'll talk about in a second。

 Like that's usually what the API is exposed to。 actually in Google， that's all they exposed to you。

So you can't do any competition there， so you can't push the query to the data。

 instead have to pull the query to the data。You bring the data that you need。

 do the processing there， generate enemy results， and then send it to the next stage。Right。And again。

 the idea is， again， the size of the query relative to the size of the data that you're processing is going to be much smaller。

 the largest query I've ever heard of in the pure SL string itself was 10 megabytes from Google。

That's a huge as query。 It's big。 But like the processing terabytes of data like it's not even close or order the magnitude difference。

So in the old days， this was considered the primary way to do it。

 especially in the shared nothing architecture， but in shared disk。You actually。

 if you just in ignoring the extra features， you can get from object stores， you would do this。

And so the extra features I'm talking about are in things like S3。

 they have a select operator where now you can basically send what looks like a SQL query down to S3 when you make the get request。

 and you can say， here's run this filter on this data。

And S3 actually knows the contents of what your objects actually look like。

 So it's not like a dumb key value store。 We say he here give me this bucket and I don't just give me the by stream。

 I't care， what's in it， like as they say here， they know that it's a CSV or JSON if it's parquet and they actually can process that natively where the data is actually being stored。

I don't know how they charge you for this， whether it's just the fetch command or they charge you the runtime because it runs as a Lambda function。

 I actually have no idea， but again， this allows us to do predicate pushdown and a shared disk architecture。

 which according to the textbook， you would not be able to do。Microsoft has their own thing。

 I don't know whether you get SQL， but you can kind of see like you pass in some kind of query there。

And again， as far as I know， Google doesn't have this。

 So I didn't look this year but last year they didn't have this as well。 So again。

 this is why I'm saying the lines get blurred because you can do some。

 some predi get pushed down and other things and projection pushed down as well。All right， again。

 yes。His question is do you always want to do predicate pushdown if the option is available。

 no because it may be the case that the block of data you need it's going use over and over again。

 but a bunch of queries that have different predicates。

 so therefore I'm making now multiple requests to S3 to get different portions of that same file whereas it would have been cheaper just to go get it once。

 cache it， then do all my filtering locally。Right。But how to figure that out。It's hard。Right。

And that's why people pay a lot of money for databases because they can do that all for you。

 I actually don't know how many systems actually do that， this trick though。

 I think Reshift does it because they obviously built it but I don't know whether the snowflake does it。

All right， so again， share nothing architecture， this is what we covered in the intraclass。

You know classic textbook definition actually comes from Stonebreaker。

 This is something that he coined in the 1980s， and this was the prevailing architecture for distributed databases。

 both for OHTP and OL systems for 30 years until the 2010s again。

 each node itself it's going to have its own local CPU locally attach a disk and and memory and any time you want to send information get data from another node。

 you got to go over the network and send PCP or UDP requests。

So we'll call each of these things as a single data to some node。 So I think of like EC2。

 you get an instance that we're talking about that。

The databases will being partition disent subsets across the nodes right again picking like a partitioning key you can either range partitioning or hash partitioning to divide them all up evenly across the different nodes。

 And then now since the data is being stored by the data as local。Then I can just use a Posix API。

 I can use Cis call， skill， get F read or F open and get the file the data that I actually need because everything。

 again， it's just files on disk that I control my file system。嗯。Yes。I'm going to add a new node。

You gently move data or ask。完全。Yeah， so his question is， if I add a new node。

 do I have to move data immediately or do I move data as it comes in。

 So this is going to be one of the big problems we're going to face and share nothing is that if we want to increase capacity here。

 then I have to add a new node， but then that node when it gets added doesn't have any data in it。

Countrys NFS miles。So he says，Can't you use NFS mounts？

But then NFLFS has to be like a central storage， right？

It cant you can't do like a peer to peer file system。Right，AFS， same thing， right。

 It's it's central sort。 So that's a shared disk architecture。 The difference is going to be， though。

 is that in something like AFS or NFS the。The location or the distribution of the data physically is transparent to the database system because it's a Poss API。

 you just call FO and FRead， you don't actually know un the covers where that data is actually being stored。

So unless you now somehow explicitly tell NFS to like partition things a certain way and so that when you read this range versus that range。

 you know that only certain pieces of data that get it locally，But again。

 it's as opaque storage that you don't understand。data service that tells you where the building data is。

But through NFS。NFS doesn't expose you that， so does that to you？

But then you got to get that information out of NFS。

And now you're basically building a database system like why bother you we don't know。

You don't want to run your data NFS。Right， these scale like this。 must say like people do that。

 People run the sands all the time， Rebut file systems， but like。We can do better。

 The data can do better if it knows exactly where the the data is actually maybe not physically stored because if it's S 3。

 all that's abstract away from you too as well。 But like it's。How do is？

The object store versus NFS would would give you roughly the same interface， except that。

You would have better control of。What can you control。

 You have control of things that like georeplate or not。 And NFLFS hides that from you。

 You get more metadata out object stores guess I'm aware。教しれてる。Cassandra is like a medio lear。されてくら。

That's the catalog。You're talking about the cat So statement is， oh。

 some systems use use Cassandra as the metadata layer to keeps track of like where the data is actually located。

 That's the catalog。 Again， I mentioned snowflake。 the use Foundation need be right I can't think anybody off hand they uses Cassandra for this and databases。

 But yeah，s the same idea。 But that's separate database to keep track of the metadata。

That's not best yet， right？Okay， so in the shared system。Again。

 we have the separation between computing storage。 You have the compute layer。

 There're still locally attached disk that we yes。Just very different question about。

What of the notes good？F就。yeah， thank。 Yeah。 I got sidetrack。

 Sorry for Stephen is if one of the nose goes down， do you lose access to that data， Yes。

 so therefore you have to replicate it right and again this was going back to the same before。

 It's now managed storage that the data controls and they're in charge of replication。

So they have to handle all that for you in S3 object store。Amazon handles that。 Google handles that。

 I don't know how they do it。 They guarantee a certain amount of reliability， and you know。

For our purposes， is good enough。 Yeah， so like in this world， we have to manage it。

 And then the question was， if I add another a new node or I take a node away。

 do I have to reshuffle data。 Yes， and the data has to do that。

 And you want to do this in a transactional manner based in your catalog so that you avoid false false negatives。

RightSo in the share this system， again， we have the compute layer and we have the storage layer here。

 and we just access this through a some kind of API and in the cloud world。

 instead of using positives API because there' not。

 you don't want to use like afuse file system to talk to S3。

 you instead use whatever the userspace API that the cloud provider provides for you like Amazon gives you a bunch of libraries to talk to S3。

😊，Some data go to extremes and throw that all away and rewrite it themselves。

 we'll see one in a second， but like that's how we're going to interact with these things。

 And so now the way to think about this is the compute nodes are stateless。Like am I share。

 am I shared nothing system going back。I she pointed out。

 I partitioned my database and now each node ignoring replication is responsible for that partition of the data。

And so if I want to take a note away， well， I got to copy whatever's in it and send it to all the other nodes to redistribute it。

But in a sharedD system， if I want to take away one of these compute nodes， well， okay， that's fine。

Because the data is down here， so I could theory kill this thing。

And then not lose any data or I could turn turn them all off。Not pay for the compute costs。

 And then you know all my data is still retained。 whereas in a shared nothing system。

 I got to keep the CPUs running because if they go away， then the data goes goes away。Yeah。

 you can check Mon to EBS and all that。Yes， like if we shut off the compute layer。

 we'd lose like any IR stuff。8岁。So his statement is。

His statement as and he's correct that if we shot shot up either in the shared nothing or shared disk。

 if I'm literally running  querying at the time， then yes。

 there is aphemeral state for that query that I would lose， yes。

 if we can talk about how to handle fault tolerance later on for that。But typically the way， again。

 you say ignoring unexpected failures when you do a shutdown。

 you basically you announce all the knows， hey， I'm going to shut down。

 finish whatever jobs you're doing。 And then once the last queries or plan frame is to leave the queue。

 then you can shut it down there's a step， the process of doing that。It's not not nothing fancy。

 It's not hard。Okay。A。Again， we'll see this later in the semester。

 But like there'll be a catalog service that keeps track of。

this data actually here still can be partitioned， even though we see this thing people went to files and S3 and I could keep track of my catalog。

 which of my compute notes is responsible for those files And then if I increase or decrease my capacity I have to run then some kind of update to my catalog is say okay these new nodes I'm now responsible for this other technique and then for that one in case like snowflake。

 I'll just use consistent hashing to avoid having to reshuffle everything all the standard techniques to apply here。

Okay， so this to finish up with the distinction again， in the shared nothing。

 it's hard to scale capacity， potentially it is faster。Because now everythings sort of local。

 But the engineering benefits and the operational benefits benefits you get from something like a shared disk architecture is why basically every overlap lab system built in the last 10 years uses this technique。

 And even systems that started off using shared nothing like yellow brick have have converted to this because the benefits are are so significant。

 And again， like。Amazon's improving Ss3 all the time， so as they make those changes。

 your data rise along the wave and gets all those updates and new features as well。

Because when S3 first came out， it didn't have that select command。 now it does。

 So that's something they've added that you can then take the benefit of without having to do any engineering for yourself。

 And S3 is pretty cheap。That's actually really cheap。Compared to EBS and other things。

 it's not the fastest。But then that's okay。 We're database。 We know how to do caching。

 Its basically a buffer pool manager， right， We know how to do caching and avoid those long latencies of doing disac so we can do all of that to hide the round trip times from facility S3。

Right。So again， this semester we're going to focus on this implementation。So this is not a new idea。

 again， I sort of showed like oh， these things became  Vogue in the 2010s。

 but it actually goes back to the 1980s and traditionally these things were terrible。

 these shared disk data systems， but because of the cloud stores because of all these every vendor has their own version。

 there's local things like SeF and other stuff or Gucester FS。

 like there's local object stores you could use。Like these things are so prevalent。 But every again。

 every system is based on this。 So just give an example of what a nonclo version of a shared disk architecture would look like。

 That's old。 This is Oracle Exadata。 So when you buy Orac Ex data， again， it's millions of dollars。

 They ship you a rack or a bunch of racks。 And it's basically a shared disk architecture。

 that's going over like infinnaman or fiber channel from the compute nodes to the storage nodes。

RightI think they can do predicate push down on the storage size as well。 and again。

 this is all running in the same rack instead of like on the object store over the public network in Amazon。

But again， just showing you that these ideas have been around for a long time。All right。

 so let's talk about the object stars again from the portion that we care about。So。Again。

 from the Davis's perspective， it's disk。And instead of going， again， we're not using Posits API。

 we're not using LipsC calls， we're using whatever the API the cloud vendor is providing us。

 but we're going to be responsible for what we're actually storing in it。

And then whether it's going to be in a proprietary format that's custom to the database system or a open source format that we'll cover next class。

 again， it doesn't matter。So in most of these systems。

 they're going to be storing it in the PAs format。Again， think of that as it's a columnar format。

 but the table has been divided up into row groups or blocks， big blocks of data。

 and then within that block， all the data for a single tu bowl is going to be located in it。

 but it's just going to be stored in a columnar format。

And that's different than like the really early column store systems， like in Verttiica， for example。

 I think they stored the entire column as a separate conigous file and every column was its own file in the Pa world again。

 you combine things together so that all the tus are spatially close to each other within the file。

 even though they're stored in columnar format。Again， and we'll cover this next class。

 but there'll be someone got a header a footer for all these files that's going how to get to these offsets because everything has to be fixed length to get to the different two posts that you need。

 how things are being compressed， any additional sketches or indexes or metadata we want to store what the data is which again we scan through the execution engine and then feed that into the catalog that the planner can use it。

 again all of this will cover in the next class。And again。

 basically what happens is you retrieve either the header or in case of parquet and or it's always the footer because it's an independently of storage。

 you start writing up the file and then you realize， okay。

 here's all the data I just stored and you put that in the footer so you can use your object store to go just retrieve the footer of the file and then figure out what's actually inside of it。

 right。And I can say they all have their own version I put get and delete。

 So this is the this is the one system we're to cover later in the semester。

 But I'd bring up now because it's like， it's wild what they did so。

yellowellow brick was originally an on-prem database system that was shared nothing。

 It was an appliance。 like you would buy these custom hardware that they would put together。

 that was tuned for the database system and you run this onprem。

 they switch converted to a cloudbased database system like a snowflake or like a redshift and others。

 but they found that when they convert it over to to run in the public cloud the object store which is so much slower than they were used to in their on-prem version of appliance version。

 So they end up rewriting a lot of things that Amazon provides you or the object system provides you and everything's all custom。

 So for example， throw away the Amazon libraries for their own libraries to call S3 using Intel DBDK so it's doing kernel bypass。

 which will cover late semester， basically do fast lookups to S3。

 get the contents or get the data you need and not make a copy in the kernel to immediately pass it up in user space。

DBDK is a nightmare。 We'll cover that why in later in semester。

 or like instead of running over TCP I， they they wrote their own network protocol over UDP because it was just so much faster for them。

 So they rewrote an of stuff， which say they wrote their own PC E drivers Like who does that Data these people。

 right， It's awesome So。😊，You know， there is， like even though I said S3 is slow or you know relative to local disk。

 there's ways to make it faster and again， caching is also going to help us hide those long latencies as well by relying on the local attached disk on the compute nodes。

Okay， so to finish up today again， was just say me vomiting a bunch of database stuff at you to as as a preview for where we're going to go this semester。

 And we're basically going to start from the bottom layer。

 We're not going talk about how S3 works because that part we don't really care about。

 But we're going to talk about what the data is actually going to look like in that we're gonna put in S3。

 And then we'll start building layers on on top of that。AndTo be able to execute queries。

 so the opposite direction of what I showed in the beginning and going top down。

 we're going to go bottom up。嗯。The idea really is about how to what stated of our implementation。

 state our methods， techniques and algorithms to do all the things that that we laid out ahead of time。

 And that's the papers that I've picked for you guys are really designed to。

Expose you to here's a certain way of how people approach these problems。

 but then we'll also cover other papers that are related to the area or other techniques。你看。

All right， so next class， the paper you guys have reading is actually something that I wrote with my former PGA student。

 basically it's a survey of the internals of Parquet and OrRC。

 it's going to talk a little bit about GPUs at the end。

 we're not going to cover GPUs or FGAs this semester， although that's a whole another line of work。

 we're only going to be focused on how we do X2queries on CPUUs for now。Okay。

 and then so next next class will be parking or in some most widely used open source file formats。

 And then the following class next Monday will be here's， here's the。Here's new variations。

 new implementations， of a file format that supposedly are better than Par Aor。

 So it's like sort of the next generation file formats that are coming out， okay。



![](img/7820a5a5fc169f97132ecf8447c1c8ea_5.png)

Any other questions？

![](img/7820a5a5fc169f97132ecf8447c1c8ea_7.png)

Steps and six packs on the table and I'm able to see saying I on the way。No short with the clutch。

 you know what got them， I take off the cat but first' tap on the bottom。

 don't about three in the freeze so about the killer， cat full with the bottom baby who snow feeling。

 Cose nice says the pain nice way you drink't get down with the guys in。Take back the pack of ths。

 andvo some now for trigger to the ths， Billy De to chief to tell weak，Go。

 be a manic getator can of thank God。