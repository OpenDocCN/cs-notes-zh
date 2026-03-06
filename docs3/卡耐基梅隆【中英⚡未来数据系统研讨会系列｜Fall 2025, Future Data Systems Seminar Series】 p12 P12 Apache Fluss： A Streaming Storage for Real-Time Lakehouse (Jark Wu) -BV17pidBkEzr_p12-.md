# 卡耐基梅隆【中英⚡未来数据系统研讨会系列｜Fall 2025, Future Data Systems Seminar Series】 p12 P12 Apache Fluss： A Streaming Storage for Real-Time Lakehouse (Jark Wu) -BV17pidBkEzr_p12-

![](img/e562a2c3f7352224ece08b9c085a057e_0.png)

But just one for my peaces that pass， God blessedless they friends。

And check it out 9 pound because it's bad bro。YIt's time for Carnegie Mellon University's future data System seminar series This seminar is made possible for our last session to host Ja he is a senior staff engineer engineer A Cloud and he's also the creator of Apache Flus about and always if you have any questions feel free to unmute and question at time and we appreciate getting up early It is currently30 the morning where he is so we appreciate him early to floor is yours go for it。

Hi， everyone。I'm Jack and good morning and good afternoon maybe okay Im thanks so much for having me here and excited to be on this stage to present Ruth and my title my session title is Apache Ruth。

😊，ASty story for your time cause。So a quick introduction of myself， I'm Jack Wu。

 current a PC member of Apache Frank and PPMC member of the Apache Fs。

 the original creator of the F CDC and Fs Project， printer I'm leading the Fs and Frankco F CDC teams at Alibaba Cloud。

And my career path is quite simple， I graduated from college in 2015 and then joined Alibaba。

And have been working in Alibaba for 10 years。I started to work on free projects as my first job since 2015。

When the project was doing a very early death。So my past 10 years experience is around the F project and stream processing。

 the F project was created under this background， so I have to introduce the f and string process first to help you better understand what is fruit。

So what is F in a short word， Apache Fnk is a distributed state for stream processing framework。

 it provides the interface， Java and Python APIs to build stream processing。

 so if you are familiar with Apache Spk Spark is a batch processing framework which processes bounded data and in contrast。

 Fnk is for stream processing which continuously process unbounded string。

Compared to batch processing， you started a job。And it processes the bounded dataset set。

 compute result， and then it finishes， so data is passive and query is actively triggered by user。

 but gene processing your start the job， the job runs forever and continuously update the results as new data arrives。

The query is passive， and data is actively streamed into the query to trigger the query to update the results。

The batch processing is very simple and efficient for daily reports and analytics。

 but the result is still until you run batch query and the computers for data set。

And if you need some real time， continuously updated results， okay。

 that's the use case of stream processing。And instead of to recomputing everything， inter。

Only the changes as they arrive， though this is also known as incremental computation。呃Wong。

One comparing real world use case of stream processing activities is the TikTok's realtime competition system in a published paper。

 they detailed how they built this system using a cutting edge realtime machine learning architecture powered by the streaming technology like Kafka and Srink。

The own Tiktok。You will see the next video， you see is's dynamically selected based on your most recent interactions。

 the like video or the will we watched videos。So this real time data is critical to their business and the state。

Deeply understand things so they adopted a streaming first data infrastructure strategy。

So we can see PTooks， the real time accommodation system is built on a streaming data architecture。

 it leverages the Frank and Kaka to make the feedback back loop in a streaming way from integrating the user's behavior data to dynamic future。

And online online model updates。And so this is one of the use cases of stream processing。

 there are also some other use cases like fraud detection， real time monitoring。

 alert and real real time analytics。The Frank is the most commonly used tool to build the data analytics。

This is also known now as the incremental materials wheel in database。

 so you can think Frank as the streaming computation engine for incremental materials wheels。

But in practice， you can define source and think tables in fco to Tier Flink where to read the changes wrong and where to write the changes to so for example in on the left side youll have a transaction table and on the right side you have a revenue table so there maybe post grade tables or Kafka tables。

And then you can define a insert2 select from query。In fco。

 so this query then be translated into a top bridge and executed by Frank to consume changes from left table and right change to the right table。

So this query is a Ma wheel maintained by Frank Sco and Frank SQL is just the computation engine to maintain Ma wheel Frank SQL doesn't hold persistent data storage。

 so you have to bring your storage for the Ma wheel， maybe postgs maybe iceberg or Kafka。

So Brink actually doesn't read a static snapshot of the table。

 but continuously reads the change logs of a table like the bin of My。

And all operators of Bco always work on change logs on and emit result change logs to the result table。

So the mat wheel computation is incremental based on the change log change log and the streaming change log is the key feature of the storage for f and the incremental mat wheel。

But here is the challenge。Because the fact is that there's no suitable storage for B S to build the incremental matrix wheel at a larger scale and in real time。

 possibly is not sc or high throughput enough for big data because it is designed for ATP workloads。

Kafka doesn't support updates or generate the change logs， and Kafka can store long term data。

 and it it typically retain data for seven days due to cost。

While materials will meet requirements months or even years of history for backfuring early competition。

And iceberg is not a real time storage system it provides。Latency of over 10 minutes。

 but we need millisecond therefore for latency。 and additionally。

 iceberg doesn't support streaming ratess or low level change logs。

 which are essentially for which is essential for the incremental materials wheel。

So that's the original motivation behind creating the F project to build a streaming table storage for F and work with Fnk Cco to deliver a better performance and experience for the incremental materials wheel。

The first provides three key features that are missing in previous storage systems。

 the first is it support law latency， streaming reads and rights。

 the law inter Smith Mexican latency for read and write operations。

And second is it supports multiple tables and can generate change log streams like the my brain logo or postgra equals logical replication。

So these change logs can be also read at a large scale in real time。

So first is a distributed storage system， it can be scaled up by adding shings or servers。

And third is Lakehouse is used as a historical storage in fruits to enable it and retain month or even as data for long term。

So your definition， I think the example you showed before it said。

He said milliseconds but you said 10 milliseconds， like tens of milliseconds is the target for you guys in this。

Yes， yes， and then and then that would be just be like a pen to pen to pen on the rights and not doing not doing in place updates。

don't get to get that in a second we also support in update。

So the update will generate to changer logs and the changer log can be consumed in milliseconds by the downstream brink。

Downstream Flink， okay， got it， thanks。Yeah， because spring is a streaming processing。

 such called low miniing computation based on the change log based on the stream。

So they can build a together， they can build a lowency， latency， incremental materials bill。

There's a question in the chat。Pksh， you want to go for it？开始。

So my question was like the materialized views require intermediate storage so is that also stored in flow or is that stored in fllink yes yes that is called the state of the materials wheel which is actually not visible to users so it is stored in internally in f called state backend usually it usesDb embedded embeddedDb and willll do some checkpoint snapshot to observe the storages。

So it is not used it is not it doesn't uses for the intermediate storage of the view it is used it uses it。

Okay， and so if the intermediate storage was queryable， is that does that not kind of。

Similar to similar functionality as what Fs has to provide。Is that。

Very different because intermediate storage there's not much of a difference between what the intermediate storage is and what the final storage is going to be。

嗯，呃。YeahThe intermediate storage is not visible to users。So you can't query it directly。

 so the intermediate state is like in this materials will query。

 Frank will store the name and sum state in Frank， so they can now what is when change log arrive。

 it now how how to accumulate some state based on the change log and images the final result。

But the state is not feasible to use Brink also provides down some mechanism to process or analyze the state in a programming way。

 but currently it can't be accessed by a SQL interface。Okay， thank you。Okay， I， I think I I。

Ps of the matrix。That I think maybe can be can help us better understand the F position because fruit belong to a new category that it doesn't exist before I think。

So consider a storage metrics that the left side presents。

Presents the operational systems and the right side represents the analytical systems bottomton is the badge systems and top is the streaming system。

 So for operational workloads with batchge query， you have MyQL and postQL SOLTP database。

For operational workloads with streaming processing， you have Kaafka and Paa assymmetrictic cus。

For analytical workloads with batchge processing， you will have iceberg and a snowflake so they call a warehouse。

But for analytical workloads that require stream processing such as the incremental materials wheel。

 there has been no storage solution in the industry。

 the fruit fill this gap as a streaming storage system designed specifically for analytical workloads。

Besides， we can also observe that operational systems in the left side are all low based。

And in contrast， analytical storage like iceberg， North Africa are corn based。

Actuatry analytics prefer column formats， and this is also true for the streaming analytics。

Therefore， growth is defined as a column string storage and we will de dive that later。

Again is the overview architecture of fruits， the fruits is a distributed storage system where data is replicated and persisted in food service while using the object storage for data tiing to reduce the local storage cost and fruits can can be used a standard room but it can also integrate with a lakehouse to use the lakehouse as its historic called data storage。

 the system makes fruits as a real time data layer on top of the lakehouse So this also changes the lakehouse into a realtime lakehouse that provides both the historic data and the real time data in a unified table view。

Okay， then we can dig dive into the F concepts and architecture first and then discuss how it integrates with Lakehouse。

At the logical model level， fruits provides two table types， log table and primary table。

 log table is a table without prime key， It only supports paint only inserts and the table produce an pan only log string。

And the prime key table prime key table is a table set with a prime key。

 so it supports updates deletes by the key， all the insert update delete operations on this table will generate an aend only change log string with insert update before update after the events in it。

The append only lock and change lock are the foundational model and key features in F to provide the streaming rate capability for all the tables。

This is the detailed architecture of aer arocaster has two main componentss。

 the coordinator server and the tableid server， the coordinateator server act as the coordination layer and stores better data to zookeeper the table servers are the real time storage components。

 the CT code data to object storage like S3 to reduce the local storage cost and also used the object storage at the persistented storage for the Q stampshots。

Allside Bruce crossed her Sarah wrong。additional components。

The lake carrying service on the right side is not a required part of the cluster。

 but is still a food service。It works like a separated comparison service that moves data from the blue color and convert it into a lakeout storage like in iceberg formats and Paque files。

And F print on the left side provides read and write APIs for computation engines like Spark and Fake。

 and it handles the unification of the historical and real time data and the print interacts with both the F coordinators and table servers as well as we read director from the object storage。

The fruit is a distributed storage system， so a table is divided into shotss and spread evenly across the cluster service。

 at top level， the table is divided into parts， which are the logical groupings of data by partition column。

 the part is a similar concept in iceberg， the partition column could be a date or a country or a business unit column in in the table。

 but the partition is also an optional for a table。And within a partition。

 data is further divided into table buckets for a primary key table。

 data is assigned to buckets with by by h's prime key for log table data is distributed evenly or random across the buckets。

 The table buckets are the units of a reason for rights and widths。

And they can also and they are also the smallest unit for data migrationgregation and backup。

For lock table， each bucket is physically stored as a lock tablet in roof cluster for primary key tables。

 Each bucket has two tablets， a lock table， unlock lock tablet and akiwi tablet。

 The lock tablet serves as the change log string。Also as a write ahead log for the KV temperature recovery。

And each lock template consists of a sequence of log segments， which are log files do on disk。

or in the object storage。And each KV tablet is a rock TV instance。

 which support high performance updates and lookups in real time。 if I insert something？um。Insert。

If I insert something， it goes into the Kv tablet， but then also the log entry goes into the log tablet。

Yes， yes， I will go through the right path into next thread。Okay。

 we can take a look at the red path and the duability of the local table first。For log table。

 data is divided into log tablets and at the physical level by default。

 each log tablet has three rep cars with one liter and two for。

 those currents logs to the leader and the leaders the log to the local log segments on disk for persistence。

While， although it replicates the data to the two followersers， most data is replicated。

 The leader sends the acknowledgecknowment to the client to signal a successful append。 Meanwhile。

 the leader will also periodically care the local log segments to remote object storage to reduce local storage costs。

诶。The Tered log segments can also be fetched directly by its client using the3 API。

So when the fruit kind reads from a given offset to read from the offset in the stream。

If the offset is still on local disk disk， the template server will return the lock bades from local disk if the offset has been tailed to obvious storage。

 the template server will return metadata for the corresponding tiered lock segments。

 so it allows the fruit client to read source segments directly from a3。Theist design。

 is especially to。Oloads the rate of workload from blue servers during catch up rates。

 which are very common。When you want to backfuring or recomputing a much view。

And the right path for prankky table， because prank key table have a has a。

Different API because it is a multiple table， so for rights it supports ups or deletes via a putKV API and for reads it supports the change log scan or KV lookups on the table。

The put KV API accepts our KV batch contains a。A set of key records and the request is sent to the keyV table leader。

 and we can see that each bucket of a prime key table。

 the leaders of the keyV tablet and the log table are co located together to avoid distributed as transactions actions as we must guarantee the consistency between the log tablet and the keyV table。

for each record in the TVV badge， it first reads from RoDB to generate the change log since the change log must include the before image of the update。

And it applies the change log into its log tablet and waits until the log is replicated。

 Once the log is replicated， it means the transaction is committed then since the tablet server makes both the change log and K records visible to users。

Finally， it assigns the acknowledgement to current the two signals a successful keyput。

And regarding durability， the QV table will regularly and incrementally upload the lockxDB snapshot files to optical storage。

And the change log acts as a writer ahead log for the Q tablet。 So if a server stiff builds。

 the state can be recovered by downloading the light TV snapshot and replaying the change log from from the corresponding next offset the next offset is stored with the Q snapshot when we performing snapshot on the log TV。

Those KV tablets leader can have zero or one or two photoss。

Which is opener can be configured at the table level。So if a borrower exists。

 it maintains a hot rocky instance that can quickly take。

 take over the leader when its original leader is failed。

Without waiting to download the snapnshot files and re tender rocks。

A you're using zookeeper to determine do leader election。

 but then are you using zookeeper to determine the commit order of transactions and are these multi statementment transactions like I can modify or insert multiple keys and that can commit atomically or is it like one keys one key pushes one transaction。

We use Zookeeperper for coordination and met data storage。

 but we didn't use Zookeeperper to do the replica leader selection so leader selection is done by the coordinator server。

Got it。Is that coordator sort diseases raft？It currently is steady the ver because we put all the states in zookeeper。

 but in the future we want to remove the zookeeper。

 so Corator will be state for using a roughft protocol。Got it， thanks。Yeah， and the。Okay。

 the red parts of the arm key， we have mentioned that a f can then the QV lookup request to the QV templateid leader。

Which are then will be translated into Ro CB lookups。

 so it is very efficient to do some QB lookups on the prime key table。

And it is also possible to scan the change log of a primary key table， but in most cases。

 users want to first scan the largest snapshot of the table and then switch to reading from the change log with consistent guarantees。

And in this case， the first client will ask us a coordinate server for K snapshot files。

And the change log of that they corresponding to， then the first client will download the logT snapshot files and read the snapshot records after inizing the log Tb instance from those files。

And finally， the first kind will switch to reading directlyy from the log templates。

Startting from the opposite of the snapshot。And the change log reading follows the same pattern as the reading the front log tablet we mentioned before。

Okay， so we have finished the read right pass and durable pass and I mentioned that。

The analytical workload prefer corn formats and actually streaming analytics is the same。

 therefore fruit has been designed as a coronal string since day one。

 making the streaming analytics very efficient。The fruit store log table batches in a columner format to enable projection push down at the file system level so can you can see log table become a realtime columna string the fruit current will first accumulate records into batches and summarizeize each batch into arrow vectors using thearrow IPBC streaming format。

And scan send those arrow badges to log tables， the log table will append those arrow badges from network to log segment files on disk in a zero copy way and this arrow badges are selfde with an arrow metadata header that allows file readers to fetch only the requested column from requested current from the disk and arrow arrow is current format that stores the data column by column。

So for example， consider a table with many columns from A to Z。

 the data is stored column by column in a formatmat on the file system。

 so now suppose we have a address real query that group by column A and computes some B and Mac C。

 so this means the query only needs to read three columns A and B and C。

So the Ma wheel will send the log which request to servers to and the request include a column projection to。

To signal the server， it only needs to read A and B and C。

 and this projection is and this projection is pushed all the way down to the file system level。

 As a result， all unwanted current are during the disk read。

 These are for unnecessary network I O and need to this rise。

And also F is the need to decide on used currents on the client side。

Which will improve the screwput and reduce the CPU cost infr。

And we benchmarked many production workloads， so if you have a materials view read only 10% of the coins。

 you can achieve 10 times higher throughput and have 90% less network traffic。嗯。But meanwhile。

 you still have the millic deterency for the reader right。

And current project pushdown is not the only benefit of using thearrow IPC format as the log format。

We are also developinging a predicted pushdown to leverage the current statistics in each arrow batch to filter batchges based on the query predictiondants。

 and more importantly， using the arrow as the data interchange protocol will greatly enhance growth integration with query engines。

 because rules is just a fuel storage， it doesn't。Prorovdes computation ability so it it query engines to do the computation。

 so it enables a query engines to do some analytics directly on the Corron strings and this capability is a building block for real lake we will discuss next next。

The fruits introduced the streaming cause concept。And this is a unification of ski storage and li storage。

Where fruit stoves as a real time data layer on top of lake。As mentioned earlier。

 throughs include a lake service that will periodically convert through data into Lake cost format and retain through data only for a short period。

And then the proofs and then the recall act act as a historic data layer for the streaming storage to responsible for storing long term data with minuteise second minute minute latency。

 and on the other hand。The streaming storage act as the real time data layer for for to store a short term data with second level。

 millise secondcon level。Latency so these two layers share the data with each other but exposed as a single unified table view when performing a streaming read。

 the lakehouse provides historical data for efficient catchup ratess and reduce the storage cost for storing such a long term data and when runninging a batch query。

 the streaming storage Sur bridge data within minutes within minutes to the lakehouse to turn the traditional batch analytics into a real time insights。

So we call this capability， the union grids。And at the user API。

 the first table and the Lakehouse table are exposed as a single unified table view。

 all the read right and update operations are performed on the same table object。

The fruit table stores hot data on localies。And the core data in S 3 and the long term historical data is stored by the lake hall table in S3。

So the unified table will stitch data from。Different storage layer and different storage format together to transparently export user under a single and simple abstraction。

 it is just like a database systems that have multiple data layers， the hot， warm and cold layers。

 which。And each layer resides on different storage media and videos different formats and the database system will ensure the data integrated across all the layers and present a single table of to users。

 so user don't need to worry about the underlying storage details。But I mean。

 there's performance implications of like going to one versus the other， right？

If it's just as equalQL interface or you don't expose any mechanism to say。

 I'm okay with go get like go get the latest data from the flus table versus。

I'm okay with getting stale data from the Lakehouse table， which actually might be faster or。

Because you don't how to reconcile the log。Yeah， we still have the API to specifically read from F T or just directly read from the Lake House table。

But we can also expose a single table object and you can seamlessly help you to unify data。Yep。

 got it， thanks。Okay the key to the storage identificationification is the lake house carrying and the unified table view。

 so we will discuss the unified table view first。So iss the first current component that stitches these T together providing a unified view of the real time and historic data。

 the first trend will translate the reads into a unit read combining the historical read result and the real time read result。

The reason why we implement the union rate on the current side rather than on the server side is to achieve the best performance because it can fully leverages the La API such as the parallel reading and the projection filter push down without adding any overhead to the F servers。

And we will deep dive the union read later。 beside Union read， the Lake House table。

Resides in users' La system。 not， it is not an internal format of toolss。

 So it can also be accessed directly by La query engines like Bar or snowflake can query directory。

But rights are more complex， the fruit current will route all the rights and updates to fruit table。

 however， direct rights to the lakehouse table are not allowed as seats will break the data consistent guarantees。

Therefore， the first table of。As the single right entry point for the unified storage and the tiing service will continuously move data and convert data from route table to the La table。

But in the future， we plan to restrict only the latest petitions to be written through the fruit table while allowing the older petition to be written directly to the Lakehouse table。

 this will support sales cases like requiring overwritingiding historic data to the iceberg。

And the Lakehouse Caring service is a set of stateless workers that perform the carrying tasksers。

They are deployed outside the F cluster to avoid impacting fruit servers because they do some heavy works。

These works are designed to be stateless and is horizontally and vertically scalable。

 but making the tiing service easy to operate and also can be out scale when the traffic changes。

When a tearing service does it was to request a tearing task from or server。

 a tearing task specifies a table that needs to tearing and the starting log offset to T for that table。

And the emator then splits the task into a per bucket tearing units and dispatches them to tearing writers。

 The each tearing writer will read the arrow badges from from the starter logo fit and convert them into p files using。

Arrow native library， so it is a direct convert fromarrow to Parkque， which is very efficient。

If the arrow bads contain catalog records， this may also generate some delete files。

OnceOnce all the Tering writers finish， the committee will create an iceberg snapshot with the analog offset as the snapshot properties today will return into committee into Silons catalog。

And this log offset in this snapshot property is very important because it is a cut off point between real time and historical data。

 and the client will use this point to stitch them together。And finally。

 the comm will also commit the snapshot and end opposite to full commuter to ask the carrying state to know to let the system now the next carrying opposite。

And the monitornior will also notify T servers of the T offset information。

 and the T server can then expel data before source offsets to keep a small data set in the real layer。

So this is the lifecycle view of different Ts as I mentioned earlier。

 one of the key motivation for storage identificationification is to avoid duplicate storage either the Lakehouse table resides in user' Lakehouse system and is node managed by rules。

 so it has its own lifecycle and TTL typically mouse or even ears。

The fruit table had a separate life cycle and T TL configured directly on the fruit table。

 So the life cycle are deco。 So this means they can have a data overlap between the late cost table and the fruit table。

 but the overlap is very small and only introduce a little cost。 In practice。

 we usually configure the overlap a few hours。This overlap data is as a core data influence。

 and it will serve as a failure tolerance the window for the batch wheel if a wheel fails for hours when it recovers。

It need to continue consuming logs from the last process offset in a in a sequential fashion。

 So reading from the tailed log segments in the real time layer。

It's more efficient than reading the data from the iceberg table because the iceberg table is usually already sorted by othering screen keys and no longer maintain the offset order。

Okay， then let's talk about the un rate the un rate is the key to the real time and it is the un rate that provides a unified view of the real time and historical data there are two kinds of unit read unit rate for streaming query and un rate for batch queries。

For stream queries， Uni enabled efficient backfiing because it uses a Lakehouse as historical data source。

And this give users a long term storage and efficient pushdown optimization to pe down necessaryces data to reduce the network I。

For batch queries， the Uniary delivers real time insights for all lab on lake because it uses fruits real time as the real time data of the lake。

The traditional lakehouse analytics typically works on data that is 10 minutes or hours delayed。

 but with the batch unit read， you can get secondly for freshness。

So this is the workflow of how streaming Uni rate works they imagine you are building a real time much as will like calculating live use matrix you need to start from historical data and then continues to process the new events so so first Bruce kind will fetch the largest iceberg snapshot。

Along with its log offset stored in the snapshot properties。

 the log offset tells us where to consume where to resume the reading from foods。And secondly。

 it reads the iceberg snapshot directly from S3， leveraging the projection filter pushdown and file level par reason for efficiency。

 so this give us a highest through and no interruption to flow servers and also can access a long term period data。

And。Then it will switch to reading the F log or change log。

 starting exactly from the log update stored in that iceberg snapshot。

 so you can get a complete exactly one's view of the historical and new time data。

With no deals and no missing data。So this works fine without to merging change logs into the historic data to just image the change logs to downstream。

Engines because it is a streaming query， because the incremental materials wheel works on analogs as we。

 as we mentioned as the beginning。However， batch queries expect a static snapshot of the data and we need to merge the change logs into historic data for batch query。

But this will make things very complex。So if。If it is a log table。

 there's no change logs and no need to merge， the batch union Read works the same as the streaming union Read。

But Prime key table generates the change logs and all the batch query engine expect no change logs。

 so we have too merge change logs with historical tables。

There are two approaches first merge on reading。Mge onread is a widely used approach in OAP system to merge base files and the deelta files at sub time to avoid rewriting entire files during updates。

 so we use this approach with Py data format together to deliver an efficient batch unit read and the second approach is based on deletion vector but this is still working in progress。

Before introducing the merge on Read approach， I would like to briefly introduce the Aache Pimo Apache Pimo is another open table format like iceberg。

 but optimizeized for streaming updates。It adopts eymetry architecture which is highly efficient for ice throughput updates and widely they used in many TV storage。

So in P all Part key files， data files are sorted by the prime key and organized into an L symmetrymetry with a think comparison to compare files from L 0 to L5。

This makes the merge on red on P more super efficient。

 and the red record output is already sorted by the prime key。

So here is the merge merge on read mode of the patch unit on the left side you have。

Historic data in Pmon with records for Jack and Judy in the latest snapshot and the log of in that snapshot point to a position in the flu screen。

 And after five offset that0 two change log entries and insert of Timor and a delete of Judy。

 So when a batch query runs the engine read the read reads the base data from Pmon。

Samp short and raise the change log from fruit starting at that opposite。

And then it performs a salt merge in memory。The historic data is already sorted by Prime key in P。

 so we only need to sort change log by prime key in memory。

 and since the change log covers just a few minutes of data， it usually fits into mini memory。

And now we have to sort the listers and we can work same efficiently and output the final result。

But yeah Mer Readed has done performance limitation for batchqueries。

 so many data lake formats and our lab system introduce the deletion vector as a more efficient way to do batch query。

 so iceberg doesn't provide prime key salted me Readed。

 so that is only a feasible way to support batch only read own iceberg is leveraging the deletion vectors。

I will introduce this approach at a high level to share the core ideas， but still working progress。

 the many design may change in the future。In As， a dele vector is a compact bit map that marks which roles in data file are logically deleted。

Allowing the query to skip them at free time instead instead of to merge the change log。

So we have three de vectors in this mode。 iceberg iceberg D in gray color is stored in iceberg marks deletes on the base data files。

 The log D in pink color is stored in fruit marks the deletes in realtime change log stream。

 and the lake D in yellow color is stored in fruit as well。

 marks the deletes applied to the base data files of the latest iceberg snapshot。

The log TV and like TV are maintained in fruit in real time for every table updates。

Bruce builds an index that maps primarily key to the iceberg file position in fruit K store and uses and uses index to update the lake D in real time。

 So when generating a new iceberg snapshot， the lake D will also be flushed into the iceberg D。

So now consider this example， you have a historical data in iceberg with records like Alex。

 Judy and Jack in the latest snapshot， Alex is marked as deleted in iceberg D。

Then an insert of Tmo and a delete of Judy arrive。 Ro will record the change logs and mark Judy as deleted in the lock D or the change log and also mark Judy in the iceberg data and also marks Judy in the iceberg data file as deleted in the Lake D。

Then when a batch query runs the engine reads base data files from iceberg snapshot and reads the change log from Fs starting from the offset。

 and the engine will also read the three deletion vectors and apply the logD on a change logs。

 apply both the LakeD and iceberg D on the base files。

 and then we can get the final result sorting and merg。

Frus and iceberg are still to separated systems， so we have they have their own met data storage。

 so the last challenge is all to keep metada in sync between them。We don't use。

I think rise met data are updates to avoid conflicts。Instead， we use a simple blocking approach。

 for example， when adding a column。We first apply the changes to iceberg catalog。 So if it succeedes。

 we update the ruless on metadata。 If that also succeedes， we notify the crimes and temporary server。

 otherwise we will roll back the iceberg catalog change。

It is a bit tricky since the process is not atomic and transactional。

 but since the metadata updates are very infrequent。

 so this approach works well in practice and we may improve this in the future。嗯。😊。

The some culture load maps。The vision of real time curves actually relies on the un weight supported by variousqua engines。

 including Spark， trainno，ductDB， Starro， and so on。

And we're also working on the de vector mode of the union read to deliver a better performance for batch union read。

 and finally， we want to better unify the metada to allow Uniri can work directly on the iceberger Ri catalog。

Okay。Bruceal was。Donated to Aache for Software Foundation half a year ago and now is incubating on the Aache incubator。

 so it is an open source project。 you can get the source code from GitHub if you would like to explore the technology。

Okay， that's all my talk。 Thank you。All right， thank you man。

 I would applaud behalf everyone else thank you for doing this we have time for a few questions with Ja。

 if you to want to meet yourself and go for it， feel free to do that。Mmhm。😊，So。

Would with the overall architecture of。Of flus， be the same in terms like the tiered storage piece。

If you didn't have the support。Basically iceberg right is iceberg making you do certain things I understand like the catalog update that's an issue there to make that atomic that' that's hard。

 but like would the over architecture change if you didn't have to write out to iceberg or Pamon。

Right that like flus was like the flus was the final story of all the storage。Yeah。

 fruit can be stand long without the lakehouse pet storage。So。

 so the core data will tell to object storage and the data can also be fetchd from there as well。

 But we lose the long term storage and more efficient rate for the historic data because we still store the data inarrow batches but。

 of course， is a more compressed way for the data storage and more efficient way to to to。

To pruning the data， I mean， you have to go through the 1000 arrow batches in a data file， but you。

 you need to fetch a single footer of the parquet if it is a parquet。So basically。

 like instead of you having write your own compaction piece to write it out， you know， to parquet。

 do you just let iceberg do it for you。Yes， got it and then would。Fre what was going to say。

How pressing is the need to get off the zookeeper because that just， I mean。

 I understand for legacy reasons， it' it's there because Flink uses it。

 a much of system use it like how hard of a lift would be to get off that。

Or how many how many times it like hasaz zukeeper cause problems for how you design the overall architecture？

Yeah， yeah， we have the plan to remove the zookeeperper， but I mean， I mean。

 will not be a very difficult thing to do this because there are a lot of a mature raft libraries to do that to embed the raft protocol in the cornea server。

 but in the early stage of the project we want to have more workloads on thes and Zookeeperper is not a problem of the project right now what we want what we want to verify vi of the project is the projects position。

And the key use cases like the railtan house and the zookeeper is not current a high priority of the project。

itBut it which is not a difficult thing to remove it。And so my earlier question what I was saying。

 like， can you target the the log storage versus like the key value storage versus or sorry like the log hot data versus going down to the。

You know to the lakeout storage piece like this seems sort of reminiscent of like the Google Nepa project where the Google Ne system where you you were this tradeoff between performance of the query versus like the freshness of the data they had another aspect I think in their their sort of the triangle metrics was was was cost right and obviously that's not not your issue but like。

In some ways， again， this seems have medicine， but it sounds like what you're saying though do most of the people prefer the Union read and they just kind of want all of the data and not worry about。

 are they looking at the latest data versus like scale data？USo u， so you want to ask， yeah。

 like do most of you just use the Union read capability to get all the data versus targeting the hot data versus the cold data？

So I think it depends use case for streaming queries as the core data。

 the history data is just used for back viewing。Yeah。

 to re the long term history data of months for years。But for the， yeah， for。Bgequeries。

 it will of course will add some more latencies compared to the director analytics on recall。

So it is a chat for users， if he want more real time data insights。

 he may need more additional 2 30% latency of the query。

if he's fine about the10 minutes latency data， so he can directly query the records。



![](img/e562a2c3f7352224ece08b9c085a057e_2.png)