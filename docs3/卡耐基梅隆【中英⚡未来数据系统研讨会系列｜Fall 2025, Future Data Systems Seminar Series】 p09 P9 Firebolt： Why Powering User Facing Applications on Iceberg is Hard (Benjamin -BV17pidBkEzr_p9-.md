# 卡耐基梅隆【中英⚡未来数据系统研讨会系列｜Fall 2025, Future Data Systems Seminar Series】 p09 P9 Firebolt： Why Powering User Facing Applications on Iceberg is Hard (Benjamin -BV17pidBkEzr_p9-

![](img/86624f3239d8ac2467c61039d1adac2d_0.png)

But just one for my peaces that pass， God blessedless they friends。

And check it out 9 pound because it's bad bro。🎼Y it's time for Carnegie Mellon University's future data System seminar series seminar is made possible excited to have Ben Wener who is the VP engineer or director of engineering what is your title V but should say also this title at age 22 which is very impressive I like how youre introduction is Bens super smart actually Germany for some reason wasn't good enough has high now he's in we appreciate him calling and giving always if you have a question Ben while he's talking about Fire interrupt any time and feel free to ask your question he's talking himself in this hotel room for an and as always Ben here The floor is yours go for it。

Pleasure to be here thanks Andy kind thanks for having having me and kind of letting me talk about our iceberg support and Firebol and yeah please like interrupted any time kind of happy to answer any questions that come up we do have like I don't know I think the deck is pretty long so we have a lot of things we can talk about yeah and look fundamentally I think the goal for the talk today right is sharing some of our experiences is adding iceberg support to firebol and kind of yeah explaining our perspective on why this is surprisingly hard things we learn in industry kind of things we built into the system to make it really fast and yeah let's go for it awesome。

😊，So。For those of you， right， kind of who haven't heard of iceberg before。

 I assume many of you do kind of very quick kind of overview of how it works。Fundamentally， okay。

 you might know a data lake you have like 10 million perquet files kind of lying around on S3 do you think with the parquet file。

 right like it gives you no rich metadata on top of that。

 So if you might want to ask which parquet files make up a table you can list all of them and hope for the best What if you want to delete something What if you want to delete something and still be able to do time travel what if you want to kind of have asset transactions on top of all of that if that's something of raw data like with parquet or whatever other five format you'll use doesn't really give you and this is where iceberg comes in。

 which basically it this opentable format for analytic data sets and it's built on top of your raw data files could be perquet could be avro on S3 and basically gives you rich metadata on top of that meaning you can do things like schema evolution adding columns dropping columns you can do things like time travel reading old snapshots you can do asset transactions It maintains things like table part。

ingFor you and a lot of other things。At the very top of your iceberg kind of hierarchy is the thing called an iceberg catalog。

 fundamentally that just points to a hierarchy of metadata files。

These metadata files could be stored anywhere。 your local disk HDfs most common nowadays。

 and this is also what you will see with most companies。

 These are stored on object storage So S3 on AWS GCS on GCP Azure B storage。

 something like that and then you have this hierarchy of different metadata levels So at the very top your catalog points to a metadata file that points to the history of snapshots and each snapshot is represented by another file which is a manifest list and then the manifest list points to a set of files which are the manifest files。

And each manifest file then points basically to a set of objects on object storage again could be parquet。

 could be Aro that are called data files， and that means if you now for example。

 run the transaction insert a new parquet file into your iceberg table what's basically going to happen is a new data file will be created a new manifest file will be created pointing to that parquet file a new manifest list will be created that respects the newly created manifest file and then finally there's a new metadata file being created which basically contains the old snapshots and a pointer to the new snapshot and the new manifest list you already set up。

All right， cool so that's basically iceberg 101 the methodadata files manifests list manifest files。

 they are actually in different formats as well， so some of those are Avro some of those are Jason and yeah kind of that's now you basically know how iceberg works。

Cool， so now my talk is today is focused on what we call user facing applications and kind of maybe word if you haven't word about that if you haven't heard the term before。

 when we talk about user facing applications， we usually mean there's a company collecting massive amounts of data kind of maybe historically。

 they would have used a data warehouse internally in the organization。Nowadays。

 it might be a data product company or a non datata product company that has some form of a data product where all of the data they collected is exposed back to their own customers。

Right， so basically have a kind of massive data lake kind of a large set of data and you need an analytical query engine that can power low latency and high concurrency applications on that big data you're seeing that pattern more and more A with data product companies right in fintech。

 gametech kind of marketing techch and so on because all of these verticals nowadays are incredibly data intensive and you have a lot of products where that data is basically exposed back to the in many cases。

 customers of our customers and you also see more with actually traditional companies that might want to show certain data experiences on top of the data they've historically only collected internally。

And so at Firebol， we basically built a proprietary file format and metadata layer to be able to handle these types of applications。

 so low latency， high concurrency kind of queries over big data and what we've been spending now more than a year on basically is trying to figure out how can we bring as many benefits of that high concurrency。

 low latency analytical query engine。Two iceberg tables and yeah。

 so this is what we'll talk about for the rest of today and there's a bunch of challenges here and we'll talk through them one by one。

Awesome， and so here's a kind of screenshot I took from a paper by Dominic Dna。

 Victor Li and Thomas Neiman exploiting cloud object storage for high performance analytics from VLDB two years ago。

 it's a very fun paper to read。 I actually recommend all of you check it out and they basically wrote a great paper on。

😊，What do you have to do to build software that uses modern object storage as well as humanly possible。

 right， because object storage can have high access latency reading a single object can have relatively low throughput。

And now you might want to write the database system that works utilizing the entire network bandwidth of your AWS instance。

 which might have 200 gigabits at this point and read with that bandwidth from object storage。

That's surprisingly difficult and kind of part of that is pretty much what you're seeing on this plot So first of all。

 accessing anything with low latency on object storage is difficult even if you have a tiny object access latencies pretty often are maybe around 25 milliseconds with tail set latencies going above 100 milliseconds so it's not like the things you might be used from your SSDs where you have basically microsecond axis。

As your object gets larger， reading the object takes more and more time， so you can see to the right。

 for example， that reading a4 megabyte object is going to take you， let's say up to 300。

 400 milliseconds and even in the median it might take you 100 milliseconds kind of to get the first by and then 150 milliseconds to actually read the entire object。

And that makes it really hard to build truly low latency applications on top of iceberg tables because when I talk about low latency or we talk about low latency。

 we usually mean let's say sub 100 milliseconds sub 200 milliseconds now I already took you through this hierarchical metadata set and the problem is each of these pointers kind of in the hierarchy。

 you can only resolve after reading most of the previous object right so even just resolving the metadata you basically after jump to the catalog resolve the metadata file read the metadata file。

 resolve the current snapshot， jump to the manifest list。

Read that jump to the manifest files now you've done like four hops and you still haven't read a single byte of actual user data in the end you need to read all of the data files as well and yeah kind of at that point if you basically start adding it up。

The math just doesn't work out for low latency apps basically is like you need， let's say 0。

1 seconds which is kind of conservative to read all of these files in the hierarchy。

 you can't parallelize those because again you need to resolve them sequentially you don't know what manifest list to read before you fully parsseed and write themet data file so at that point kind of assuming your data files are a bit bit bigger you're kind of at 0。

5 seconds and that's pretty much the limit of what you can do if you really go through the catalog in the beginning and then have to resolve everything and read everything from object storage。

Yeah， and this is where things become fun right like this is why we're database engineers and where we've been spending a lot of time figuring out how we can get significantly below these0。

5 seconds。😊，Cool， yeah。 and look， all of your database experts， right。

 So just to kind of very quickly highlight the many query engine challenges you have to make this work。

 You have data access itself， right， So you basically need to figure out how do I as fast as possible get to the right data kind of within my parquet files and within my overall files。

😊，You need to figure out joint planning， here's a TPCH or a query on TPCH schema。

 how do you decide where your orders， customers and nations comes in your joint plan？

You need to do data pruning kind of to be able to use your selective predicates in the query to read as little data as possible you want an efficient runtime and at the end of all of that you actually probably want scalable query plans because if you have iceberg tables with hundreds of terabytes or  petabytes of data。

 you'll want to compute those on a cluster of machines to get to reasonable latency。All right。

 and so now we'll basically talk through all of these kind of。

 I'll tell you how we're thinking about solving these problems on firebol and again。

 please ask questions at any moment。Cool， so we chatted about the 0。5 seconds earlier， right。

 kind of in that this is pretty much the theoretical minimum of how fast you can make your first query on an iceberg table when you have to resolve everything。

To get below 0。5 seconds， we need to get this entire hierarchy of resolving data files out of the hot path of a query。

 right as long as it's in the hot path of a query， you won't be able to get things really。

 really fast， so what we're doing is we're basically caching an iceberg snapshot。

 meaning we're caching the actual list of data files that make up a specific snapshot。

And then we allow users to define a certain stayness allowance。Meaning a user can basically tell us。

 hey， I really want that iceberg table as of the most recent state。

 in which case we'll go to the catalog and kind of actually resolve the most recent snapshot。

Or you might be able to say I'm fine reading up to 10 seconds stale data， 30 seconds stale data。

 10 hour stale data， really up to you as the user， and at that point we can basically use the cached metadata that we store in main memory to be able to resolve the data files of the current snapshot without ever going to S3 to resolve metadata。

These snapshots are then asynchronously refreshed in the background。

 right kind of meaning if you have a stainless interval of five minutes on a table， for example。

 will just refresh in the background every now and then to make sure you never hit the methodadata resolution path when you run low latency queries。

Questions so far。Alright， good so I think these are the easy parts。

 kind of let's start getting kind of progressively fancier about what we can do Now the second thing is。

 and we talked about it briefly already that iceberg itself is this open table format that provides also certain metadata on your underlying data lake tables right so think about having a million parquet files in your regular data lake again。

 now if I go to you and ask hey， how many rows are there in your data lake。

 what we'll have to do Okay， you'll have to list all of the parquet files。

 you'll have to look at the photos of all of these parquet files and then you'll have to basically use the metadata to add all of that up。

😊，Iceberg makes this pretty easy because things like row counts are actually maintained in these hierarchical metadata files。

 manifest lists and kind of manifest files by iceberg， and as you resolve the metadata of your table。

 you can really read things like the row counts or even file level and Max values that you can then leverage in your query engine and duringuring query planninging to make things faster。

😊，All right， cool， so if we have a query like the one I showed before again on TPCH to make things easy。

One thing we can do which I think is pretty neat， is basically to get the cardinality estimates of the underlying tables。

 we turn this into a SQL query again so basically internally our query engine will run a SQL query to get the method of these queries and it pretty much looks like this so it looks like select the sum of the record count from and we have this internal TVf which we call this iceberg files where you for example point at the orders location which is basically just saying hey。

 there's a catalog hosted here this is how you can access it。

And we use the same staleness that we got from the user query。

 and at that point there is basically an underlying cable our system exposes。

 which lists the iceberg files that make up the current snapshot and contains metadata from these files。

And so getting basically the current record count is pretty much only the sum of the record counts over that metadata table。

 which internally exposes the current snapshot。This is actually a funny thing to talk about for a second because when I study database at university。

 I never really appreciated the power of like using your query engine and SQL queries to solve other problems in your database kind of I thought always okay like we're database engineers we let's say build in rust or we build in C++ and kind of anything that happens under the hood like a cardinality estimate is basically written in raw rust or Ro C+ plus the cool thing is if you build a composable system with clean abstractions。

😊，At some point you basically wake up one morning and you realize oh damn actually I can use my own query engine to run this computation in an easier way and this is what we're doing with the joint planning meaning again query comes in we basically run all of these queries in the background these pretty much always work over cached main memorymory tables right there is no kind of metadata being resolved in most cases when we list the iceberg files because we cached it in the step before and then we run that sum over the record counts and basically start feeding that into our cardinality estimator。

For all of you who took and query optimization classes。

 you know there's a lot of other things you really want to have when you do joint planning right you might want to have countering sketches。

 you might want to have histograms kind if you want whatever information you can humanly use in order to make cardinality estimation accurate because you probably will get it wrong most of the time anyways and then at least kind if you should take your best shot at。

One problem with iceberg is honestly beyond the record count。

 it's very hard to leverage other iceberg metadata in order to make very planning more efficient。

 you can build some form of histogram from the Max information you get out of the kind of iceberg hierarchy。

 we currently don't do that which means right now for our giant planning we do heavily used the row count。

 but beyond that there's actually not that much information we can use。

So for a firebo firebot runs off like native firebolt tables。

 you guys are doing sketches or histograms to classic like classic summaries and then maybe you'll get to in a second so then when it comes down to the query optimizer you wrote it for a system where you assume you had native control of storage and like what changes in maybe the query optimizers's algorithms the cost model certainly changes are you changing the strategies for finding join orders and things like that given now you have like。

Weaker statistics than you had before。 so great question。 And so to kind of， first of all。

 answer really the first part， we can look at our docs if we look at。

Let's see which one is it automated column statistics。

 So what we actually allow our kind of customers to do is basically define on which columns they want which stats。

 So if you do a regular create table， there are certain things we always collect out of the box things like Min Max values kind of row counts of course。

 etc。 If you want something like a prox count distinct statistics we've had into the optimizer you can write SQLqueries such as kind of adding a statistics keyword to the specific column and we'll start collecting more under the hood at the moment。

 this only works for these managed tables where we basically a full control over these storage layer and also the metadata layer Mo I gave a talk I think like a 10 minute flash talk in the past about our metadata layer we're doing a lot of things there to make all of these things as efficient and low latency as possible And so we haven't brought these features over to iceberg at this point for iceberg where usually like honestly the situation is even worse and I'll talk。



![](img/86624f3239d8ac2467c61039d1adac2d_2.png)

![](img/86624f3239d8ac2467c61039d1adac2d_3.png)

That a bit later， because you're usually kind of。At the whims of the creator of the iceberg tables。

 which means in some cases you might get great par key files and you might get metadata which is nicely structured where you have very accurate information In other cases。

 you might get a terrible looking iceberg table basically with a bunch of tiny files with certain parts of the metadata missing and you always have to make the most of it。

In our case， kind of when we use the iceberg metadata for joint planning。Honestly。

 to estimate things like predicates， theres very few， I think super smart things we do at the moment。

 there are certain filters on partition clauses， for example。

 which we can estimate more efficiently because we might be able to pre prune on your files and then update the row counts。

 but beyond that， we're not doing that much。One thing we do is kind of defensive query planning。

 I briefly touched on that in my flash talk two weeks ago。

 where we basically propagate upper bounds based on the worst case estimates that kind of we can guarantee based on the plan and then we have。

 but this also works on managed format。Basically like this risk minimization pass almost at the end of joint planning。

 where if we see that we made， let's say， a potentially controversial choice because we can actually guarantee that the pretty small table can be put on the build side of a join。

 we always do that and networks also for iceberg and basically in some cases protects us from very bad decisions。

Does that answer your question， Andy， yes， awesome。Cool， now the interesting next thing becomes。

 and okay， now we can chat more about joint planning， right。

 we might use more metadata to also choose things like physical plans。 So for context， first of all。

 Postcur compliant。 second of all we're scale out query engine。

 meaning you can run your queries on a single node engine and if engine is our unit of compute。

 you can scale it up as much as you want to So we do believe actually and kind of scaling up before scaling out and we give our users that flexibility but as data becomes very big what you will see in many cases。

 you might have a user that says， hey， I need to run this big batch job in less than an hour to hit their SLs and actually kind of make their business work you don't have any other option and scaling out in many cases。

So now let's say we join orders online line item， very classic join O order key onto L order key。Now。

 the interesting thing is that iceberg might contain partitioning metadata。

 and you might have something like bucket partitioning。

 which is very common on O order key and L order key。Now， traditionally。

 if you have these two large fact tables which you would join。

 what would happen is you basically assign a shard to every node in the cluster。

 you do a shuffle on the join keys， meaning basically it's like all to all network communication where you align the matching rows with the same O order key and L order key on every node。

Then you do a local join and then you move on to the next part of the query Now this basically means that in this case。

 all the rows of orders and line items would be read on a specific node。

 then they would get shuffled then there would be a local join there's a bunch of network traffic here。

What we can do in these cases is we can see that these two tables have the same partitioning scheme and build a physical plan which basically co locates the partitions on the different notes。

So in this case， we would basically do iceberg level file assignment to the notes of hey。

 let's say note1 reads bucket。 Let's take a。Just to make the math easy 64 node cluster。

 node 1 takes bucket 0，1，2，3 node 2 takes buckets 4，5，6，7 node 3 takes buckets 8，9，111。

 kind of you get the picture。 And since we assign the same bucket I to both node。

 we can at that point build a plan which doesn't have any shuffle to computer join。

 So basically kind of each node reads a chartard of the table from object storage。

Does a local partition join， and then we go from there。

Same trick can be done for aggregate queries right and if there is well kind of now that you understand the bucket partitioning tricks you can pretty much do the same thing if we have an aggregation query by El order key and with see bucket partitioning you' don't even need any keys to be aligned。

 we can choose a basically pre-partition plan which avoids a shuffle for the distributed aggregation。

I think there might have been some queries in chat， Andy， I don't see the chat。

 so if there's something there， feel free to also ask。

So Matt says says this is storage partition join in Spark with V2 data sources， for example， iceberg。

Yes， so exactly Spark also supports these storage partition joins。

 We work with some customers who move from Sp to firebol。

 kind if there are certain cases that Spark actually doesn't handle super well， but to be honest。

 I don't remember all of these cases anymore so I'm not the best to go super in depth onto that。

It can also be a bad choice， by the way， like there as well right like if you end up having 64 nodes。

 but only two buckets are populated， you might end up kind of with very heavy skew across the nodes。

 which is also why we allow our users to choose this so there's some default behavior and then if you want you can basically overrite that and decide。

 hey， I really want to force a partition join here or I really want to make sure there's no partition join happening in any way。

And this always assumes like doing the match on the previous slide。

 it assumes you have like the far key information。Right like you have to know the order key and line line item order key of the like they're point to the same logical thing。

But if they don't you can't do this right it doesn't matter that much as soon as your joint predicates looks like this right kind of as soon as you know I'm joining on order key and L order key。

 the kind of actual constraints don't really matter because the transformation is logically correct in any way and that's also how we do we basically do a pass and our optimizer over the joint predicates kind of try to extract what partition plans would be possible and then match that against the iceberg metadata so there don't need to be any extra kind of like foreign key relationships or anything like that being specified。

Got it thanks like things always get a bit nastier once you start looking at kind of specific outer join variations and so on because then you can't always scale these things in exactly the same way and they also start to get really complicated once you have more kind of dejunctive preddiicates or anything like that at which points honestly in many cases what these scaleout engines will just do they'll just gather on wellload and run like a complex denctive predicate there。

All right， cool good so yeah， final thing in terms of using metadata right we can use iceberg metadata to basically skip data files。

 which is also pretty nice if we have a filter like oh order date kind the 1s of January 1998 we can look at the iceberg metadata which usually contains fine level minute max values per column。

And use that to actually do phi level pruning。Here as well。

 the same nice trick of actually using your query engine to do kind of internal steps of data pruning within your kind of overall。

 let's say query evaluation flow。In our case， we basically take the user predcate and we turn that into what's called like the falsifiable expression。

 which basically means you take the plan and you turn it into a rewrite that doesn't touch the actual data。

 but only touches the Min Max metadata。And then you will evaluate that pre kit at a fine level。

 And afterwards， you basically get a set of qualifying files。

So if I have a filter like O order date equals 19981t of January。

 I can basically say I only care about those files where the 1 of January 1998 is between the o order date minimum and the o order date maximum of the respective file and then if those are the three files we have we'll basically see that orders1 has an o order date minimum of 2024 so there's definitely not going to be a row with 1998 in there in the same way orders2 has a maximum date of the 2 of April 1970 so there is well basically the above falsifiable expression will return false。

Only for the third parque file， we get true because here， okay， the minimum is before 1998。

 maximum is after 1998， that file could have qualifying those。Here as well。

 the logic starts to get more complicated once you have more complicated expressions。

 so we can do it for equiities， inequalities， conjunctions， disjunctions。

 we have some special cases if you for example， do something like where lower of a text column smaller than ABC。

 for example， there's some more complex rewrites you need to do there but in principle you can basically turn your SQL expression into a falsifiable expression on the metadata and then run that falsifiable expression over your snapshot to figure out the current files that qualify for that specific query。

Cool good， so now kind of moving on， I think you kind of understand how we integrate with metadata in our query planning level so we can do things like joint we ordering。

 we can choose the right physical plans based on partitioning metadata we can kind of eliminate certain files or partition based on the predicates in the query let's start going deeper into actually our runtime and query execution stack to understand what else we're doing under the hood。

Now what happens if you run a query like this right。

 kind of a join of orders customers nations afterwards in aggregation kind of by the nation name and you basically get the number of records per nation and the sum of the order prices in that respective nation now one thing we do under the hood and we have previous tech talks on that as well that's actually pretty cool is we can in a consistent way。

Cash basically artifacts your inquiry run time。Keep them in main memory and then reuse them for future queries and a prominent example where we do that is actually for hash tables。

So in this case， we choose the joint plan of joining customer and Nation first kind of and afterwards we join orders onto that here build side is on the right side and know that part is always confusing。

 so basically first join customers on N， build a hash table on that， scan orders， filter orders。

 probe the previously build hash table and then do the aggregation in the end。

Now we basically fingerprint the entire query plan kind of with this current snapshot in mind。

 so basically think of you start at the bottom of the tree for every scan node。

 you build a kind of cryptographic hash based on or fingerprint kind of based on your current snapshot。

 and then you start propagating it up your query plan。

 which means each join also has a unique fingerprint， each aggregation also has a unique fingerprint。

And then when we do a hash join in our runtime and we see we actually aren't under a lot of allocation pressure and we have spare main memory。

 we basically say， hey， I might have to use that hash table again in the future and we put it into a thing we call the fire cache。

 which is indexed by that fingerprint Now when the next query comes the physical plan has these fingerprints annotated all over and basically for each fingerprint。

 we go check into the fire cache first of hey， can I use an artifact of a previous query to make this new query fast。

The runtime doesn't really need to understand the snapshots in a deep way。

 it only looks at fingerprints and the queryry planner is the entity that does all of the fingerprinting。

 and then there's an L UA Victor that over time basically purchase things that become stale or arent really use anymore。

Cool thing here is we integrated all of this with iceberg。

 so basically today already in firebol initially we supported our manor storage layer only today all of that works with iceberg there is well。

 the big trick is even if you have a fast changing iceberg table， if you define your staleness。

 you can basically keep the fingerprints alive for a longer time right。

 if you define a staleness of five minutes， your planner will basically make sure that for similar prairie patterns。

 even if your underlying iceberg changes all the time。

Your fingerprints stays stable and you're actually still able to do a lot of that subreard reuse kind of in production for your iceberg tables at that point。

If I read this plain frankly， it looks like you guys are doing early materialization， right。

 so if the projection output changes。Like the wear clauses are the same the joints all the same。

 but like you're adding an additional column your fingerprint will not match correctly is that correct exactly which and like there as well the interesting thing right is like in many cases you might say hey。

 let's probe for an additional column so you projecting additional column can if you do probing in that case all of your fingerprints on the build sign might be exactly the same right basically like only in the subparts of the query plan that you project the additional column through your fingerprints actually start changing。

Oh so you're saying your fingerprint， you just ignore。

Would you say Jerry maybe Munder you say you ignore certain project columns in the fingerprint Yeah so let's say like you also here don't just group by the nation name but also some orders column now in that case basically your fingerprints starting in the scan up to the filter and then the join upwards would change。

Since you don't have changed anything about the projections on the build side here though。

 nothing changes about the fingerprints basically， so in many cases you might have significant changes in your query text and also project more columns。

 kind of reorder things， but your fingerprints actually stay relatively stable。

Can you share in production what percentage of Fireboat customers queries hit the cache hit the fire cache Great question so that's the next slide data is basically a bit old so that's I think kind of because we didn't refresh the slides so I apologize for being a bit lazy here that was earlier on when we rolled it out kind of since then we've added a lot more coverage to the fire cache so there's more kind of more operators being covered now more query patterns being covered but yeah so back then if you basically look at the ratio of time saved and spent kind of in many cases we basically actually kind of for the cash entries spend about 10 times or saved about 10 times more time than we spend so another way to look at this if you have the hash table that's being reused it's usually being reused 10 times on average。

Yeah， and so you see time saved and time kind of build time spend here on that slide。Again。

 kind of nowadays， the numbers are probably a bit higher because we just added more coverage。

 but yeah， didn't refresh the slide。I think there was another question on chat。Yeah。

 Stephen Moy from the Steven Moy Foundation are keeping it real asks。

 how does the youth to determine a value for max stillness if the business logic doesn't directly dictate this stillness like a bank transfer。

 for example， a five minute stillness covers 9% queries versus a 10 minute stillness covers 00% of queries。

Rather than set and observe， is there a simulation of back testing mode？

I'm not sure I fully understand the question， I'll do my best to answer it in the way I understand if it doesn't properly answer it。

 kind of just ask again and clarify。It goes into our like also just philosophy on designing firebol right is like kind of we believe that kind of if you're an engineer building these data products and kind of customer facing applications。

 you don't want a system that abstracts all complexity away from you。

 you basically want the system that makes things easy for you to get started。

 but gives you a level of control that really allows you to well leverage expertise。

 you build up in that system over time right like if you learn about firebol kind of like for a month to take your production kind of your workout to production。

 there should be some benefit of spending time with the system。

 and at that point we give you more control， which means that for the max staleness， honestly。

 we don't dictate anything kind of we say hey， if you're a user firebol。

 you're smart enough to figure this out yourself， you know your business constraints。

 and you figure out what your staleness is， if you have different staleness requirements for different queries。

 it's no problem at all。You can have a single compute cluster that run some queries with a staleness of five seconds。

 some queries that aren't stale at all， and other queries that kind of have a staleness of one hour。

 but we aren't prescriptive here and we also don't give you recommendations because it fundamentally just depends on the business problem you want to solve and we usually don't know about that。

I think he's asking like， if say I said it your stimulusless is10 seconds here。

And then you're running queries， you guys have a way to collect the telemetry and report back and say。

 you know， 9% of your queries are hitting the cache results。

 but if you change the interval to 20 seconds， 00% of the queries will hit the cache Okay gotcha。

 so that type of thing you can reconstruct from the telemetry we expose。

 but we don't have like an in product feature that shows that to you。Makes sense， go for。Co嗯。Good。

 yeah， so time kind of time save versus time build honestly kind if we're pretty happy with those numbers yeah。

 exactly cool so now let's start actually to go deeper and deeper into our runtime and kind of one thing that I actually think is quite interesting is now hierarchical metadata you read a bit of Jason you read a bit of Avro。

 it doesn't seem that complicated。😊，If you actually look at our scanned pipeline under the hood。

 there's a lot of things going on and again kind of think through the case that we're actually in many cases on a multi nodeode cluster and especially when we're on a multinode cluster。

 we probably touch a lot of data and we want to be very， very efficient。

So the first thing we do is basically there's a primary node for every query within the cluster。

 different nodes can actually be the primary over time and there might be multiple primaries for different queries running at the same time now there are certain things we can't scale out very very well and that's fundamentally everything that gets to the point of figuring out the right objects ID that are part of your current snapshot right so basically the pointer to the parque and Avl files that make up your current iceberg snapshot。

Everything before we resolve these happens on the primary node。

 the primary node reads kind of goes to the iceberg catalog， gets the current snapshot。

 reads the manifest list， which is the second piece in that iceberg hierarchy and then from the manifest list it basically gets the manifest files and denies thing is the manifest list already contains partition information for each of the manifest files。

 so it basically tells you the minimum and maximum partition value in each manifest file。

And we do a first partition pruning pass kind of based just on the manifest list。

 which means if there's only one partition that qualifies in your query。

 we're not even going to look at all of the manifest files。There as well， to be honest。

 that's something we only learned over time， our initial implementation and if when we didn't have a lot of experience with real- worldor iceberg workloads yet didn't have to step。

 we thought okay， well'll just read the manifest list we'll read all manifest files and then do minm pruning based on that and if we have customers and prospects that have iceberg tables with petabytes of data where iceberg metadata can grow to like tens of gigabytes and in many of these workloads you will see very aggressive partitioning just to keep things under control and then we basically had cases where initially it might have taken us I don't know1 hundred seconds to just read through the iceberg metadata and we invested a lot into just this whole metadata pipeline afterwards there。

Cool， now the manifest list reading and partition pruning I think at the moment is pretty much single threaded。

 remember this is just a single file， things only start blowing up in terms of data volume once you get to the manifest files。

The cool thing now is becomes even on your primary node， that pipeline is fully multi threadread。

 meaning kind of different cores get assigned different manifest files。

They load these manifest files， they parse the manifest files。

 they do min max pruning on these manifest files。And one thing that's actually quite interesting is this is pretty much。

Textbook moresal-d parallelism at this point。 So if you know the kind of multithreaded morsal-dri parallelism papers that's basically how you can multithread your engine and assign different units of works。

 we're doing exactly the same thing here just the unit of work is basically one manifest file at a time and different cores basically just pick manifest files that come from that partition pruning pass and then do local magax pruning on top of all of the actual data files that are referenced in the manifest files。

Now this is when we can start scaling out right basically so so far things run on a single node。

 we resolve the metadata， we make that fast by multithreading the expensive metadata operations now we're left with the object IDs after partition pruning right so maybe you have a billion objects and object storage we now figured out these are the 10 million objects you want to read。

At that point， we shuffle the object IDs to the different node， which basically means we tell。

 for example the first node， hey， you're responsible for these 100 objects， we tell the second node。

 hey， you're responsible for these 100 objects， we tell the third node。

 you're responsible for these 100 objects， and so on。Here as well， again。

 kind of just something I want to point out now when we built our shuffle。

 we built it to handle actual data， right like we built it to handle user data and things that actually pass through your query plan。

Nowadays， we use our shuffle layer for a bunch of metadata as well。

 so you actually bake a lot of this metadata pipeline。

Into your query engine primitives that you use for regular data processing and this gives you great scalability and just also great multithreaded performance right because we design our shuffle for high performance。

 we design our runtime for efficient multithreading and that basically means that at that point if you have a million object IDs。

 our shuffle will crunch through it happily because it was built to handle way more data。😊，Cool。

 at that point on every node you just start scanning the data files right so let's say node one gets these data files1 to 100。

 then it starts actually going to object storage， reading the parquet files。

 kind of loading them into main memory parsing them and producing the actual kind of data that your query touches that's then flowing through the query engine for your actual query plan。

阔。One subtlety here that might not be super obvious。😡。

The way this shuffle works is actually really really important because the shuffle fundamentally does your work assignment for the cluster now if your shuffle does a bad job on your partitioning function and you send everything to node one。

 you'll have stragglers because node one is going to take longer to then compute the pipeline afterwards or stage afterwards then the other nodes。

So within our shuffle here， we actually use another queryie engine building block。

 which is we build a custom window function that can actually do kind of bucket assignment and is built to equally allocate files across the different nodes to get to a point basically based on the data size where load is balanced nicely across all nodes。

 so here as well， just kind of the neat trick we do under the hood where we leverage a custom window function to actually do the file assignment to the different nodes。

嗯。Pool question so far。All right， good， then let's go deeper into this data scan part at the bottom here。

 right like how do we actually read the perque file？

Now if you've never thought about kind of how a parquifi looks。

 here's our CMU seminar attendees parque file， fundamentally it's pretty simple。

 there's a parquet footer at the end of the file， there's a page index kind of before that parquet footta。

 these things together contain things like format versions and codings there are row counts in here in theax indexes note these are different row counts and min indexes。

 then the ones we mentioned in the iceberg metadata right so some things are basically scored ordered bit redundantly and then there's a bunch of pointers to other parts of the file which basically point to certain row groups or columns or data pages。

The parquet file internally is broken up into a set of row groups。

 if you look at many readers there's just going to be a single row group in the parquet file。

 but in principle there could be multiple row groups。

Think of a row group as basically a slice of your rows right it's basically a set of the rows that are put into the parque file stored in the column layout。

In the row group， you put one column after the next。

 internally it's organized into individual data pages that then contain the binary data。Yeah。

 so far so good， I don't want to go too deep into parque filess here right now。

 but I think things get pretty interesting when you actually look at how we scan perque under the hood So initially in the early days of firebol。

 we had a pretty I would say。Primitive parquet reader that was basically using the S3 library under the hood to read from AWS。

 and then the arrow libraries in C++2 DD parque reading because there is great actually libraries for reading parque coming out of the arrow ecosystem。

Now over the past year， we actually fully rebuild our parquet reader to be native to firebol and handle things really。

 really efficiently， and there's a few cool things that I want to mention here。So first of all。

 all of the parquet files are actually buffer managed and that's something that's not very common in industry engines today。

 usually most engines for queries on iceberg will just always go to object storage and if you query the same files over and over again。

 kind of you'll basically always return to object storage。In our case。

 we actually have a buffer manager which can cache parts of the parquet files both on SSD and in main memorymory。

 the caching here is sparse， right， meaning that you don't cache a whole parquet file at a time。

 if you only access one row group and two out of10 columns， for example。

 only those will actually be read from object storage and then stored within the buffer manager。

The nice thing is all of these iceberg scans basically are fully co-routine based so we use C plus plus corouts to basically build the entire parquet reader and when you start a query and you basically start getting a set of tasks we create a bunch of different tasks that are basically nested co-routines that will do the actual data reading so think about you start having 100 tasks。

 you start setting up a bunch of sorry 100 files， you start looking at the parquet foot。

 you understand what grow groups exist， you understand what row groups you have to mean。

Read and you basically start setting up a variety of co routines that are then driven by a scheduler to read as much as possible and to read with the highest bandwidth possible。

 So one thing that's important here is that basically these tasks are grouped into task families。

 for example， all the columns you read from a row group come from this might be stored in the same task group。

 even though it's 10 different tasks if you start touching 10 different columns。

Once you start working on a task group， that task group gets priority。

And that basically means that we try to maximize the concurrent work on that task group。

 which basically means we might have to read， let's say 20 row groups at a time in order to really saturate the underlying network bandwidth or two row groups at a time to saturate the underlying SSD bandwidth but we try to read as few things as possible while we maximize bandwidth to basically pass data downstream as quickly as possible because one thing you really don't want to do is if you read a million row groups。

 you don't want to read all of these row groups in parallel and basically make slow progress on all of them because what's going to happen is that you will start stalling your query pipeline that comes after your scan and in many cases the scan isn't super CPU intensive because you might be waiting on as three most of the time so you really want to get into a state where you start pushing data downstream as quickly as possible。

Overla your IO as much as possible with， for example， a downstream filter and pre aggregation。

Should I， should I understand these cover routineines as similar to the morsels architecture。

 like your。Like's they're all getting scheduled to these task groups whatever like as part of like the morsels design pattern。

 I think Firebolt uses as well， right。And you're saying the scheduling is slightly different。

So for parque readers， then they would be for scanning native titles exactlyact and so the actually for native data it's different as well。

 the fundamental thing I think is if you build like a main memory morsel driven engine。

 you know that when you pick a morsel for your table scan。

 your CPU can get to work right away right because basically main memory is fast to access has very low latency。

 you just start pumping data into your kind of CPU caches and start going crazy。

That module breaks down for object storagebased table scan and you need to make sure that you can create enough concurrent IO on your underlying layer。

 be it disk or be it object storage and object storage is much more difficult to fully saturate bandwidth on that and that's fundamentally what's going on here right basically like you might you don't want to have a morsle。

 which is， for example， read this row group because you might not be able to actually create enough outstanding loads for your underlying object storage to be able to then saturate your network bandwidth So if we can read a single row group and we saturate network bandwidth。

 we'll be really happy if we can we actually go in like almost this overdrive mode where we start predictly fetching more and more data to keep the network bandwidth fully utilized and kind of that's where the core routineouts come in because basically we can have more ongoing。

Streams of work then we have CPU cores and we basically make sure we always work on things that become available as soon as possible kind of I think with a traditional morsal driven model where you might say。

 hey， one chord does one row group now， it will become super hard to actually fully utilize your hardware。

Got it。 And then Matt asks， are you are you doing any page level pruning or just row group level。

 curiousious about downloading an entire row group with sparse selectivity。 Yep， so good question。

 at the moment， we do row group level pruning。 we don't do any page level pruning。

 a lot of de key files you take a look at also don't have a lot of data page indexes right if that's the other part。

 the other thing which is honestly just a mess。 These data pages don't have to be aligned over column groups。

 So there might be row group0。 and there's column A and column B data page 0 on column A might have row 0 to 100 data page column B data page 0 might only have the first five rows。

 And at that point， if you do really data page pruning level。

 you need to do a lot of work to actually start stitching these things together again。

 and that's something we don't do at the moment。And then at DS。

 what's the performance implications of using cover routines over doing manual multiprocessing and synchronization Yeah so good question Look I think fundamentally。

 first of all， the architecture actually becomes really nice with the coroutines you could probably just start the000s threads have them go crazy kind of like reading from the underlying object storage and you might be fine from the performance perspective kind of we actually built prototypes for both because we didn't have any co-routines in our system before and we were a bit worried like hey now we need to all become coroutine experts kind of is it worth it doesn't actually end up kind of becoming a mess and we had quite a few concerns about a dead in the end where're really happy with how this entire stack actually ended up looking now and it's just nice to reason about in terms of these tasks tasks families and the abstractions and where you start waiting on your underlying IO stack for example so I think you can probably also。

Fas with traditional multi threadreading， the reality is just from a software architecture perspective。

 I think our stack is pretty cool and we're pretty proud of it。The last part， maybe， is。No。

 I forgot no， there was the second thing I wanted to mention， but I don't remember。

And thank you again。Cool yeah， so last thing， by the way。

This whole IO urine Co routine kind of buffer manager stack。

 but also use it for Avro but we don't have any fancy read strategies for Avro because well we read it kind of once at a time。

 I think we actually still use thearrow library to just kind of parse those so theres well we can read with high bandwidth from S3 and we can kind of buffer manage all of it efficiently but then there's not something super fancy going on in our Avro reader。

Cool yeah so this is basically the kind of summary all of that so yeah I think we talked through all of it。

 we use asynco routines for these format readers we throttle kind of the control flow based on the inmemory bytes per core so there as well basically there's some rate limiting going on where we start seeing hey memory pressure starts building up because for example I have a bunch of task families from very large row groups we start throttling the scan again and we basically slow down while making sure we don't deadlock to not get into a point where we basically exceed main memory。

One thing about our buffer manager because that might look a bit different from traditional buffer managers for diskbased systems。

 we use fixed- sizeized blocks of two mebytes and when the buffer manager fetchs from object storage。

 it reads at at2 megabyte granularity and that's basically based on the work of the paper I mentioned earlier by Dominic Dna on kind of using highperform cloud object storage。

 two megabytes is basically a very nice size to read from from S3 because it's very cheap it's still as high performanceform and you can nicely saturate your network bandwidth once you get enough outstanding requests and basically the whole buffer manager is built to just make the most out of modern object storage。

If you like compared to buffer managers for this space systems like OA， for example。

 you will often see that they have kind of very fancy variable size page setups and so on。

 and yeah we just took different design decisions since our basically cold storage is object storage。

All right， cool so I'm starting to run out of time honestly I don't think this part is very kind of interesting I basically just talking about the diskbased caching and the main memorybased caching we don't have to spend a lot of time on it and do want to quickly show you all of this in action basically and we set up kind of a data set that Andy knows really really well because he's one of the co-authors on that paper so we scaled the amP data set to a terabyte and we basically just yeah added some dimension tables to run SQL queries on top of that and we have all of this stored in unity catalog on databricks and I just want to show you how actually then our SQL support for all of this looks in product let me quickly zoom in here。



![](img/86624f3239d8ac2467c61039d1adac2d_5.png)

![](img/86624f3239d8ac2467c61039d1adac2d_6.png)

So one thing I mentioned before is that thing you have basically which are called locations and you will see that we for example pointed a rankings table。

 user visits table and this is basically where you store your databricks credentials so you basically say hey here and pointing to this databricks locations。

 these are the credentials to access it and then firebolt can resolve it we have pipe syntax which is quite nice so here you can actually see all of the different locations and kind of the different DDLs associated with those locations。

And now we have this thing we call the read iceberg TVF， where you can basically say， hey。

 read the user visits table stored behind this Databricks user visits location and we can add a limit 10。

And now what you will see is that this kind of compute comes fresh up。

 So there's nothing on SSD cashier。 Your first queryie actually takes a while。

 And this is exactly what I meant with this hierarchical metadata。

 So the underlying table here is a tery。 This is why it takes a bit longer than the 0。

5 seconds we mentioned earlier as the theoretical minimum limit because there's quite a few files in that metadata table。

When you run it the next time， even without staleness， if we go back to the catalog。

 you will see that it's already quite a bit faster。

 so it becomes subsecond and this is basically our disk cache and kicking in because now when we read。

 we go to the catalog， we never have to go to objectject storage and then you can basically start reading from SSD or iceberg table。

If you anti staleness or for example，5 seconds at five minutes， sorry， you will see as well。

 first query is fast because we have thing on SSD。Second query is super fast and basically only takes 10 milliseconds on the query execution side because we can use our result caching at that point。

 this also uses the subreult infrastructure。 We are basically fingerprinting the whole plan and realizing we still have that results already ready you can do the same thing with the rankings table。

 you will see initial  query takes a while not as long because the table is smaller。

 Second query comes back pretty much instantly。 Now things become interesting when you actually take some of these ammpp queries from that original benchmark definition and start running them。

 This is one of the heaviest ammpp queries， it basically does a join between user visits and rankings does some filters and finally does an aggregation and we basically look at the ad revenue per country So we do a join on visits and rankings over the URLs add some filters by a visit date add some filters by a page rank and then the country。

Code aggregation。And what you will see at this point is that we actually start touching more and more data。

 so here as well the initial query will take a bit because we have to go to object storage。

 we have to read a bunch of data from object storage and start loading it onto SSD so this query now took about 8。

5 seconds which is again honestly ajo on a table with a terabyte which is pretty nice and you can see that at this point data pruned and kicked in right we only had to actually scan 17 or 18 gigabtes out of the underlying terabyte。

And we have 95 result drills。Now you might say hey 8。5 seconds。

 that's quite a long time to read 18 gigabytes， honestly not really。

 because if you look at it it's about2 gigabytes per second。

 I looked at the network bandwidth of the underlying instance that's running here before that's about 15 gigabytes per second so we're pretty much reading at the network bandwidth here。

 there's just honestly I don't think this query can run faster on iceberg basically。

Now things become cool when we start making changes to that query。

 So let's say we have all of these country codes now and we actually have the total revenue all over the place。

At this point， we might want to add something like order by total revenue descending。

And just look at the top revenue countries。If I run this。The query comes back pretty much instantly。

 and we don't even touch iceberg or S3 at this point。

 This is subre ca and kicking in because we can push the subre reus through or kind of cardinality preserving operators。

 We basically see， hey， we computed the same result。 without the order by clause before。

 Im still within my staleness allowance。 And now I can order by the revenue descending and everything comes back super quick。

Now to show Subre review and all of the iceberg caching in action。

 we can also change the date visit date we're filtering on。

 so let's say we go from the 15th of January 2000 to the 16th of January。Now at this point。

 what you will see is we have to go back to S3。So the query actually starts scanning at least some data again。

 which in this case，340 megabytes and we take about a second， but things are still really。

 really fast because half of the table was or the join we do was actually cached in my memory So this is where you actually see this join subrard reuse kicking in where we can see that under the hood we basically can accelerate these joins even if your pre has changed and And this also answers your fingerprints So even if your query text changes right。

 kind of fingerprints might be similar。Last query I want to show you just because I think it's pretty cool is that even if we change the group by key。

 so we initially only group by country code， but now if we add the language code as well an order by total revenue descending again。

You will again see that kind of while the query takes a bit of time and it scans about 400 mebytes now fresh from S3。

 we're still able to run in about a second， even though basically the underlying qualifying roles in the iceberg table are still about 20 gigabytes。

So yeah， that's basically the whole thing in action and fireball。

 I think there were a few questions now。Right， so yeah。

 we're short on time I'll'll ask Matt's question and then I open up to the audience。

 I it is Fireball doing any sideway sideways information passing for the buildside。

 the probe side scan or is that not a good idea if you're trying to reuse scan data in a cache and don't want to prune data that might be useful across other queries Yep。

 so great question。 We do it only on managed of storage at the moment。

 there we do it quite aggressively， we don't do it on iceberg at this point。😊，Got it， okay。

 all right， we're over time， we have time for maybe one question about the audience。

 if someone wants to go for it。So yeah， while we're waiting for any question。

 there's two last things I want to mention I'll be super quick here。

 I don't want to go through all of the details， but maybe for you to take away in terms of our industry learnings。

If you build an iceberg reader， like we do a lot of smart things， I think under the hood。

 but we're fundamentally at the mercy of the writers。

 kind of if the writers don't create good looking iceberg tables，We can't get incredibly fast either。

 And we've seen a lot of cases at this point where there's just weird stuff being created。 So。

 for example， one wellknown vendor， when we looked at their iceberg tables。

 they actually created Boolean kind of parque files with Boolean encoding that we couldn't get any mainstream reader to read we like tried it for a couple of days we couldn't get any kind of reader to actually read them at that point。

 there's very little you can do。 there's also a very wide- ranging spec， there's a bunch of things。

 kind of config options， etc， that make it very hard for you to actually at any point tell whether your iceberg support is really good and we still run into new things every now and then。

 So for example， just now we ran into the case that you can have partition definitions in your metadata without the partition columns and storage。

This isn't there in the main icebergs spec， but it's there in this spec for high two iceberg cable migrations。

 which is a sub spec， which then allows that behavior if you run into it and a customer wants to do it。

 you need to add support to it。Yeah， any kind of closing questions？All right， so I'lls that last one。

So唉。Can you share what the access patterns look like at the sort of parquet file level。

 I understand you cache the metadata stuff and you're caching the buffer pool and the buffer is caching the parquet files。

 but I mean at that point the parquet file is hot because it's in your buffer pool it's in in memory or SDD I mean at that point in theory you could run analyze on it and start collecting I know you guys don't support it yet but that would be an obvious thing to do you want to analyze on it because now it doesn't cost you do S3 to get because you already have it locally so I agree with it there as well。

 I think it's like from a system design perspective not something we'd want to do because we really care about plan stability and compute in our world is kind of ephemeral right like if you stop an engine and you start it again once your pastures are hot we really want to guarantee kind of predictable query performance now if you start doing smart computation during your engine runtime to make your plan smarter。

Then you shut down your engine and you bring it up again。

 your plans might go back to being really really bad performanceformance just becomes unpredictable and it's a mess we are working on adding more stats for iceberg and maintaining some things on our end for us these are usually always pretty large engineering projects because we care about retaining information across compute clusters and across the lifetime compute clusters to just guarantee plan stability。



![](img/86624f3239d8ac2467c61039d1adac2d_8.png)