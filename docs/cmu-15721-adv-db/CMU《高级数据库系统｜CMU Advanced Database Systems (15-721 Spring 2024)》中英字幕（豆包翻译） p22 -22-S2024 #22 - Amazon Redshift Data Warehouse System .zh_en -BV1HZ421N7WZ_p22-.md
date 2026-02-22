# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p22 -22-S2024 #22 - Amazon Redshift Data Warehouse System .zh_en -BV1HZ421N7WZ_p22-

🎼Carnegie Mellon University's advanced database systems courses filmed in front of a live studio audience。

😊。

![](img/7cf1b1e00ceaa4b74c565ed591ecd77e_1.png)

🎼你。🎼last lecture of the semester we're going cover Amazon Redshift。

 and so the challenge of this lecture is like。You know。

 I'm not repeating myself because it's a lot of these things or systems are doing the same thing over and again。

 I'll talk a little bit about some of the pieces that make Redshift unique separately than the others。

 I mean， the paper is was a good paper in terms of like it covers a lot of stuff。

 but isn't cover a lot of stuff in detail how they do it。 It is like we do this， this this and this。

 So I can talk a little bit about what we know from them before we get to that。



![](img/7cf1b1e00ceaa4b74c565ed591ecd77e_3.png)

，What's on again to finish things up again the final presentations are going to be next Thursday in this room 9 a again I haven't checked what the vote callia is but go vote whether you want what you want for breakfast and so for this one again on the web page it'll say you need to email me your slides the final right up for the project and then this little JSON file we ask you to fill out what yeah we'll get that the little JSON file like your name is and your project GiHub URL and everything and then we use that to generate the showcase webpage that we then put on the website and then again。

I've had， I've had。People former students like they apply for a job and at a Davids company and they contact me and they want to know what you guys did when you're in this class and we have the showcase page we can show them and also too for people like if you're international student you need to get what H1B stuff or whatever visa you want to get later on。

 your lawyers will reach out to me， ask me to write a letter say what you did in my class。

 what the skills you learn and again， the showcase page helps me remember what you guys have done。Al。

 so that again， so， so all that's going be due Thursday morning at 9 AM。

 the final exam was going to be due。At the same time。 And I realized。

 and I forgot that I tried to do that last year and was a bad idea。

 So we bumped it now to be Saturday， May 4 at basically midnight。 Thank you。 Yeah， sure， yeah， yeah。

 No， I I should have not done it。 should remember that I tried to this last year in the state。 Yeah。

 so again， the prompt is on。😊，Is on Piazza， it's basically saying you have to retrofit a new system。

 or retrofit is an existing system， and here's a menu of optimizations that you could potentially do based on the things that we talked about throughout the entire semester and you got to pick three。

And you've got to justify why you want to pick those three over others。

 including with citations and other information that we've discussed throughout the entire semester。

So what is this- again， this is grad school， this is CMU。There are， how does it is？

I don't say there isn't a wrong answer， there clearly are wrong answers， but if you're debating。

 it's for to think about， okay， of fact， I only pick three what is going to give be the biggest bang for the buck in terms of getting the best performance？

and you have to also think about， okay， if I choose one optimization， does that mean， you know。

 doesn't actually do anything unless I choose this other optimization。

 therefore I got to choose two together。😡，And that takes away your choices。 Yes。

 is there something we're specifically optimizing for just like jazz performance。Yes。

 and you can ignore engineering costs。さオ。Because again。

 that's relative like if you don't have any experience in simply， oh， that would be very hard。

Firstersus like building it in the query optimizer。Which is hard for everyone， actually。Yeah， again。

You we post on Piazza if you have questions or additional clarifications。

 and then also I haven't posted this yet， we'll post the URL for the Google form you can fill out to say whether you use ChaGBT or not。

What that mean you want to copy the question into chat GT and say。

 write me a four page essay with citations？Go for it？That's fine。 that's an option when you。

 when you say， right， did I use chat to or not， And then to what degree you did。

Those haveAt most four pages and most four pages。And again。

 the justifications came because because Andy said it was a good idea， right。

 it has to be based on the readings and the basic of things that we discussed。Okay。All right。

 and then I can't spell course， right， course evaluation。

 I think we'll send out the reminder emails for everyone。All right， so last class。

 we we talked about yellow brick。 And as I said， it's not a well known system。 to me。

 it's very fascinating because like。If you just have really hardcore systems engineers on your team。

 you the sky's limit what you can do and the big thing that I said like they're doing all this。

 theyre trying to avoid the OSs as much as possible because it's always going to interfere with what the database system wants to do when to execute queries in terms of getting better performance and had the most control so they basically went around it entirely It's not a true unit kernel where like the kernel is running nothing but the database system the Germans are actually working on a project related to this。

 but it's about as closest as you can get， the system boots up， they make tens calls。

 get everything into user space and then let the OS only handle like logging stuff。

Are the basic things？Right again， so and that's super awesome。 I find it super interesting。

 I don't know to how much， I don't know how much the other， you know。

 systems we talked about this semester are doing the similar kind of things。

 I don't know if anybody's writing their own， you know。😊，Device drivers are the way they did。

All right so。Talking about now Red shit from Amazon。So the background you didn't understands that。

There is a long history of people of companies and open source projects trying to make distributed versions of Postgres again。

 Postgres came out in the 1980s out of Berkeley， it was traditionally a single node system in the 1990s there was a commercial version of Postgres calledlutra which is completely separate code basease as far as I know and the original academic version of Postgress didn't S SQL supporteded Qll and then some Berkeley grad students took the old academic version of Postgress at aQL sport to it that's why it's called Postgres QL is the official name and then as the 20000s came along。

 people were looking tried to make it distributed and so there's a lot of attempts to do this and the OB a side of things this Postgress XC StorDB which was based on Postgres XE but then they went under or they got bought by transla and trans lattice had their own thing Postgres X was maybe the one that what people were most excited about and that hasn't been updated。

I think since 20。15，16 or something。 right。 So that project basically has died out。

 Now there's there's systems like Ugabyte， for example。

 that that took the front end of Postgres then ripped out the bottom half and made that distributed。

 but it's not not exactly the same。 People are trying to do this， you know。

 natively inside of Postgres。And then there was a lot of systems that were doing this for OAPP as well。

 again， the mid-2000s when the sort took up， and this is when the first of batch of OLAPP systems came into place came onto the market。

 Green plumlum we talked about cius was based on extensions inside of Postgres。

That got bought by Microsoft and Vertica we talked about from Strernbroer and others。

 and then Par Excel is another one that was trying to do this。

So the parL one is interesting for us because this is what Redshift is based on。

And they're completely upfront about this， that this is the original history or this is the lineage of what started apart Excel。

And the sort of the backstory， the rumor is at least that in 2010 with sort of AWS。

 the cloud offering taking the services is taking off。

 they were looking at adding a data warehouse service that they could include in Amazon Web services and sell it as a product and then they had this big internal debate。

 whether they should just write a system from scratch or should they buy something off the shelf and use one of those。

 the problem though around this time all these， I think Cus just start in 2010。

 So maybe cius came up bit later。 but like all there was all these first wave of these special purpose Oap systems like the Greenpls vertics。

 park cells， astroadas。Data Lero， all of them have gotten bought up by this point。

 except for Park Excel， like Greenpl got bought by EMC。

 Vertica got bought by H data Lego bought by Microsoft， And then within， I think。

 half a year of looking at the code。 they said it was garbage and threw it all away。 So they paid。

$100 million dollars for something they' never used Assterada got bought by Terada。

So Park Se was the only the last one at the dance， like that hadn't got picked up yet。

And so what Amazon ended up doing was instead of buying them。

 they invested in them in like their series E or something like that。 And as part of that investment。

 they got， they got。They got licensed to the source code to use it anyway they wanted it。

 and I think they paid like $20 million for it。Which is again。

 for how much money Rship makes now is a steel。 Of course。

 obviously they put a lot of engineering effort to make it all work。 but they pay $20 million。

 get the source code versus like Vertigo got bought for like 100 million。 data Lego got bought for。

 know， these are all the hundreds of million。 They got it for 20 million。Cudos to them。

So this is what they did。 So and then they， they slapped it up on AWs and then started you know。

 set it as a service。 I think in 20， I said this is 2014， but I think it was maybe it lot sooner。

 around at the same time you think snowfl came out。So this is Redshift it's Amazon's。

 what Ill call flagship OLT database management system or database as a service。And again。

 the lineage is that it comes from Par Excel， which was a shared nothing fork of Postgres。

And so you'll see that over time has evolved to a shared disk system， right？They were， you know。

 they didn't originally start off with like the way Snowflake did of being completely disaggregated storage。

 they eventually had to add those pieces back in and they did it。

 they tried to do this in a couple of different ways。

So they added just I out a storage for S3 in 2017， and then they added recently support for serverless deployments。

 Basically now I don't need to provision my compute cluster ahead of time the way you would have to do in snowflake。

 at least an original version of snowflake， you just say here's my queries just thrown right at it。

 As far as you know big queries always been serverless。

 like that one you've never provision like I want these nodes。

 you you just say here's my credit card number， give me a string I can send queries to。

 And then if you want guarantee capacity， you sort of pay extra for that。

 But there's no no provisioning of machines。So I would say redSshift is going to be it's going to look like a more traditional data warehouse compared to BigQuery and Spar that we talked about before。

 even though it sort of fits in the category they're always compared with these other data lake or lakehouse systems。

 it's going to look more like a traditional data warehouse similar to yellow brickrick where they want to control all the data for you。

 so they're going to add the ability later on to be able to read data off S3 directly like parquet files or whatever you have down there。

 but by default， they want to put everything to what they call the Redshift managed storage。

So as part of this， the design goal， similar to what Snowflake was trying to achieve is that they want to remove as much of the management responsibilities from the user and have everything being controlled much as possible。

 and' the paper you guys read， they have a bunch of sort ML based or automatic based mechanisms to try to do this。

But I think the original implementation of it was。It was like the very first version of it was like basically Park Excel and you got exposed to all the internals things about Postgres or Park Excel these were the things that you had to deal with as a user of the service。

So what's sort of confusing about Amazon is that there's。There's two different versions of redshift。

 And then there's this other thing called Athena， which I don't think the paper mentions。

 But that's another O lab system that they support。 So Vi version， of redshift， I guess I said。

 I think came out in 2012， not 2014。And again， that was always being stored in。

There's a shared nothing system rest storing things on the compute node themselves。Then in 2016。

They took Presto out of Facebook and then they is rebranded as Athena。

 I think it's based on the Trino line now， not the which it was based on Presto Sego。

 not the Presto DB one from the Facebook still controls now。

They have what they have sort of this will be like morekin to a lakehouse query engine where you just。

 you just have a bunch of files on S 3 and you can read from it。 And again， that's what。

That's what Tresto was originally designed for。And then the spectrum extension to the original version of RedSshift came in 2017。

 and this is basically allowing you to have through the redshift interface。

 or front end query data that's on S3 without having to first port them， load them into。

Low end into the Redship managed storage。So。Again， so， so when you sign up now， I think you。

 I think you just say I want redshift。 And then like。

 if you end up querying data that isn't that you're not gonna suck into the managed storage that just sort of goes to this spectrum thing。

 I don't think you specify I want spectrum。 Where Athena is a completely separate service。

 And they said its just。They're just reselling and repackaging。I pressed up。

Which Amazon does a lot for a lot of systems causes。诶。

Causes problems with some from data spenders for open software because Amazon oftentime makes more money than they do。

 And then so what ends up happening is。These major companies end up relicensing the open source software to prevent Amazon from reselling it to elasticastic Pi。

 the most famous one that has done this where they had to change a license because Amazon was making more money on elasticastic search than the actual company Elastic was。

Okay so at a high level， this is what Redshift is going to do for us。 So again。

 a lot of this is going be the same as team before， Sha disk go to storage again。

 even though it started off as shared nothing， but then they switch moved to share disk pushbased specized query processing I'll talk about this in a second。

 but they're going to be doing intrinsics AVX2 and Cdy code written by hand by Amazon engineers。

What is novel about what they're doing for cogen than the other systems is that they're actually going to do both。

They're going to do the vector wise style pre compileile primitives。

And also do the holistic source of source compilation that we saw in highQ。

So they're actually going to be doing both these things。Theyll have compute side caching。

 packs columnar storage will be their own proprietary storage。

 I think they' doing they can do sort merger and hash joins。

 another interesting aspect is that they're going to have their own sort of hardware acceleration layer and they're up front about it。

 this is what it's actually doing where it's like BigQuery， for example。

 they don't publicly talk about the in-memory shuffle。And as far as the。

 snowflake doesn't have anything that they do， and then they have a stratified query career optimizer the paper mentions like that's how they're going to be able to do to handle the one- off issues that they have for queries by having their own sort rewr layer。

So for today I'm going to mostly talk about this one and this one。

 but then these other things will come up as we go along。

So this is the diagram from the actual paper itself。You know。

 you can see all the different bits and pieces that that make up the overall。

Overarching reshiftft system So at the bottom you have this storage layer here and what's sort of confusing is that you have sort of S3 here and then you have this reshift Man storage next to it as far as I can tell they are they're actually like EC2 instances themselves and locally attach storage who can then also spill over and write readrite data from the S3 as well。

There's this aqua thing that the hardware excelator we'll talk about in a second。

 but that could be something that stands in between the compute nodes and the red managed storage。

They have these other spectrum nodes here again， I think these are just。I don't know if they're。

 I understood these things just to be like it's software they can then run in here in the actual compute node of the worker notes with running queries that can then just know how to go read data down from S3。

Yes， two questions what exactly so spectrum just an isolated thing， is it actually talking to anyone？

The question， question is spectrums and isolated things， Yeah， there's no error。

 So this is what I'm saying， I don't。IMaybe I misunderstanding what in the paper and Ipricrat gave a talk last。

 I don't think he mentioned this。 Like I thought this is just software because it's just like， okay。

 you want to read some data on S 3。 My worker node knows how to go do that right from what I understood from his talk this year was that his basically moved stuck from the the arm nodes are just S 3 nodes with some more software on that。

And like the spectrum from S3 to So your question is like like for the R stuff。

 these are just S3 nodes with the extra stuff。 yes。

 and then move into this it Amazon I thought that spectrum node are just just compute right because because you can join like the RMS data with the S3 data right So like we'll see slides in this in a second。

 but like。😊，And so therefore， like， okay， if you're just doing query processing。

 that's going to be done up with a compute node anyway。 So。

 I don't know what the separate spectrum nodes actually mean。Am。

And then the like the compute isolation clusters versus retro compute clusters， this is just like。

How you've sort of provisioned it do I want to have some organization in in my company have access to a compute cluster that they can only use and therefore it doesn't interfere with it doesn't get slowed down if people are sort going at the general pull for the organization。

 but they also have the ability to scale up automatically if you specify to say hey go bring some digital nodes because these things are meant to be stateless although I think they also do have a local SSD cash as well。

And then the compilation service， we'll talk about that in a second， but that is basically again。

 the thing that's going to run GCC to do thepoation， the compilation of the queries has to go along。

And what's also confusing about the redshift managed storage and how it relates to like compute nodes is when you provision Redshift。

You specify you want the instance type to be the Redship in managed storage and so that sometimes the literature makes it sound like okay。

 well it's the node itself just knows how to go talk to sorry you get a single compute instance。

 but there's also another instance that spins up that has this redshift managed storage versus as you saying is it just something sitting around above S3 it is three nodes with additional code yes okay。

O。So so when they execute do a query， the actual engine itself is going to be push based。

 The example that they show in the paper looks like it'd be pool based and they even call this out。

 but they talk about how。That would be too much state to maintain in a pullbased model that they switch to push base。

 but they'd be careful about they sort of where they do certain operations to avoid blowing out your CPU registers。

 so there's a lot of the same things that we talked about before in the hyper paper when they were doing compilation that they're trying to be worried about but one thing they do differently is that to help reduce compilation costs。

 the compilation time of the queries themselves that they're still going to rely on some pre-complied primitives to do vectorized scans and in filtering and other things so they're not going to do full precomplied primitives a vectorwise was for the entire query plan is just for the lower portions and leaves they're going have things that are the pre-complid that been in line into the compile program and as I said that the code that they're generating is not going to rely on auto vectorization for any of these primitives everything is going to be written from hand。

Using intrinsics。Another technique that they're going to rely on in these scan loops to avoid stalls is that they recognize that。

You don't want to do some operation on the tu you're operating right now and then loop back around in sort of the scan kernel and then face a stall because the record you want to retrieve is not in the CPU cache or the CPU registers So they're going to use software prefeshing which I think we talked about with vectorization you basically construct the CPU to say go fetch this these next memory addresses bring them into I think it lands in L3 or maybe else who I figure which1 but basically go fetch the next thing I know I'm gonna to read from memory into my CPU caches and it's timed in such a way because they control again those that they're running on they're controlling the code that they're generating so they have heuristics to figure out at what point you want to invoke that software pre-fetch command so that when you come back around and actually need that tuple it's actually ready for you and they basically use a circular of buffer to place these things So。

Like the query plan is the source， and then you emitm a more source code for it。

Versus like the hypertyle was like taking the query plan and think of the source and spitting out the IR directly。

Yeah。RightSo I think we talked this for with the relaxed operator fusion approach where we were introducing buffers in between and our pipeline。

 that wasn't exactly a pipeline breaker， it was like a pipeline breaker。

 where I could sort of fill up a vector and then once that's full。

 then move on to the the next stage within my pipeline and so the idea was that within that sort of soft pipeline breaker。

 you would inject the pre-fetch commands so that you can do a little bit of work。

 the hardware gofees， the pre-fet is the thing you need。

 and then when you come back around the data is available for you。

Because if you think about it if you do too much work。

 then the data might get evicted by the next time you start using it。

 if you do too few work inside that before you prefetch or after you prefetch。

 then when you actually then need the data that's not available and again because they're doing all the compilation stuff themselves they' generating the code。

 they have ways to figure out I'm this far along and therefore I should inject my prefetch prefetch commands。

So the one thing that also that came out of the paper too。

 is that given from all the other systems we've talked about。

They appear to be less aggressive in in being adaptive compared to BigQury and Snowflake and others。

 right， like Snowflake was trying to do aggregate pushdowns。

I think photon and Big Cr were trying to figure out on the fly what the right data type they should be using。

 So what they really only talk about is that they have the ability to choose。

 choose a vectorized implementations of different string functions。

Like upper or lower comparisons and things like that for for when it's ASI data。

 And then if that's incorrect， then they fall back to a slower version that operate on Unicode。

But that's， that's a。Sort of the same trick that the others were doing。 You know。

 they're not really reorgan the  query plan themselves。 And the other one they talk about is。

If you for the join filter， doing subways information passing。

 when you you're building the balloon filter on the build side of a hash join。

 they can recognize that if the。If the hasht was getting too large and it's spilling the disk。

 then you you can size the bloom filter to be a little bit larger than you normally would。

 because that'll increase the likelihood that you don't have false positives and you don't end up touching things from disk。

 But that's really the only two adaptivity parts that they talk about other than scaling up。

 But the scaling up thing is。Is more like on a per query basis。

 do I need more compute nodes because my current compute nodes are running other queries？All right。

 so the compilation piece of this is very fascinating as well and this is。

It's similar to what Yellow brickrick was doing where Yellowbrick talked about。

 instead of having the worker nodes be responsible for compiling the queries themselves。

Amazon is going to have a separate service that's running on the side with with dedicated node to basically call GCC and compile things。

And the idea is that。TheYou'll have caching different layers of caching within within the system。

 So you have a local cache， we have precomp query plans or fragments。

 And you identify that the thing you're trying to compile right now has already been compile for。

 you just reuse that。 But then they have ability， which is。

Having think ingen to maintain a cache across the entire fleet of machines across all of Redshift so now like the idea is that if you come across a query that your cluster has never seen before。

 it doesn't have the compiled query plan in its cache and go look this global cache。And see。

 did somebody else have something that's very similar and be able to reuse that， that shared object。

 that pre compileiled or that compiled code。And again， from a。From a security standpoint。

 there isn't any issue because it's not like there's running， it's running arbitrary user code。 It's。

 it's literally like scan this table on this type with this kind of filter。

 And so it doesn't matter whether your table contains， you know。

 banking information and my table contains blog information。At the end of the day。

 a column is data its a column of data， and they can reuse that。

So they talk about how the cash hit rate is like 99。95% across all queries across the entire fleet。

And then in the cases where if you don't have the precomp segment in your local cache。

 87% of the time that when you go to the global cache， it's going to be in there。

So this basically negates the cost of compilation， the thing we were worried about before when we were talking about how to use this technique and again。

 when we talk about IQ and MsQL and other systems that fork is like GT。

 we talked about how it's gonna to be seconds to actually compile things even hyper in some cases。

 it was going to take hundreds of milliseconds to compile things。

All that goes away because everything's cached， yes。This question is how big is that cash？I mean。

 it's not to be petabytes。But like， it's probably a couple hundred gigs， sure。But。

 but who cares is your Amazon， right。Like how big， how big is the S3 total amount of S3 storage。

Right。I don a lot。So who cares if you have these cash query plans？Right。

 and then from their perspective， also too， like。It's a win situation because the customers are happy because thequeries runt faster。

 it's less computationalally expensive to fetch something from the cache than recoile it。Right。

 so for them， it's， it's this is an no brainer。 And again。

 this is which you can do when it's in the cloud。 Like again。

 if you're running hyper and it's local on your on your box， you can't phone home to to say。

 you know。Do you have this compiled query plan because you sort of not designed that。

 but when it's a service running in the cloud， where you control everything。

 you can do this kind of trick。So I saw a similar idea from。啊。

It's a sort of commercial JVM company called a Zul A Z UL， and they now have compil as a service。

 similar like this， So like if you're running your Java program。

 you can have their compiler the local compiler or the local JVM say。

 oh I want to you compile version of。Of this jar file up the run on this on this hardware。

 you can call the service and get， cash binaries from them。Yes。

 what I'm most pressed about is that the level of indirection of going to the cash is less costly than actually comping。

So your statement is you're more impressed that the cost of going to the cash is cheaper than just combined locally because you't combined locally just like 10 milliseconds。

Seconds。SecondYeah。还是一个。How large are these pre？let's say in like source code。

Are they more than like question0s because like if it's like pre compile operators？

It one operator is not going to be more than like。So David is like。

 how big can these programs actually be because？Like， you know， if it's。

Because if you're using some precomp primitives for certain parts of the lower leaves。

 but what about everything else， how much can that be？I could mean in the thousands。

 right like for really big queries with a bunch， just just specifically for the pre。

The precomp primitives are usually pretty tight everything it's all the scaffolding around it that then calls into the precomp primitives。

 that's what they were trying to avoid compiling that。

So what's the point of having the pre compile His statement is why have the precomple primitives if you're going to be able compile everything？

I think the paper talks about how。They come back and they keep saying that I think it's reduce compilation costs。

Oh yeah， let。But it makes， I mean， I think it makes sense because you can imagine like。

here's this one piece of code that I'm going to keepiling over and over again。At their scale。

 if you can compile it once and reuse it， I think it makes a huge difference。

And they talk about again， there's this overhead of。As we saw before， if the pre co primids。

 invoking a function is not free at runtime， obviously because it's a jump call on the CPU。

 but if you do it on a batch of data in a vector， then it gets amortized。And it becomes neorable。

So this would be， I mean， we'll talk about this at the end， but like Amazon's not stupid。

 they have all the metrics and telemetry across their entire system。

Like they can identify here's the part where it's super inefficient for us and they can introduce caching and other things to speed things up。

So it's not like they designed this because they thought w， that's fun。 Let's go do this， right。

 They did it for a reason。嗯。And so like to your point， like， yeah， who cares about compiling the。

 same five line function over and over again？Think of looking again on Amazon scale。

 you're doing this a billion times a day that starts to add up。And so this probably saves them。Again。

 millions of dollars a year to have this。And as I said， like the customer is happy， too。

 because like now queries are super fast because you're just stitching much of precoul stuff put together。

I don't think a paper talks about this， but I know that one of our students did an internship with them and worked on this project。

They basically keep keep track in the cache。 Like here's all the source code。

 and then that they've ever generated。 and they have different compiled versions of it for the different versions of Redshift they've deployed and the different hardware that's out there because Amazons always putting out new instants and so forth。

 they don't really tell you exactly what the CPU is。 That's all hidden from you， but。You know。

They obviously upgrade things over time。 So they have the ability to。

To to have background workers go through， look in the cache， grab the original source code。

 then recompile it for the the new versions。 So its it's not just like for this fragment。

 But here's exactly one binary version。 There's additional。

Additional qualifiers you would have to select what version of the binary you wanted。

 and we saw the same thing with the yellow brick。All right。

 so the other thing that paper talked about， although it's rather short。

 but we can discuss a little bit， is that they have this hardware acceleration layer called Aqua。

 the advanced query accelerator for Redshift。As far as I can tell。

 this is just for reshift and not spectrum。Because spectrum is kind of trying to go against directly S3 storage。

 but I might be wrong with this。But basically， they introduced a additional。Cashching。

What they call it what computational storage layer that sit in between the worker nodes and the storage layer that has a bunch of FGAs that you can do predicate push down and aggregation push down into these devices and do a bunch of computation on them before you hand it off up to the worker。

So let's say that the worker says， I want to get some data。

 I don't want with this predicate like this。And so instead of going talk directly to storage。

 you go to Aqua and you say this is the data I want to I want to process。

 here's the warehouse I want for it， and then this thing goes down to the storage there and just makes the raw get call to S3 or whatever to get it。

 brings it back into this side， does the processing on it and the FGA and then shoves it back up to to the worker for the computation。

Right？AndThe paper talks about how that this layer is not actually tied to。your cluster。

 your workers， you know your sort of data warehouse instance。

 this is its a global service that can be reused for multitenor across any possible cost。

 similar to the compilation service was across all the entire fleet of Amazon Redship users。

 Same thing for this。 that this was like used by anybody。Am。And they talk about how。

One of the advantages of having this additional separation between the storage layer and the work layer。

Is that you can down do cluster resizing the worker worker level and not worry about having to shuffle things around because this thing is sort of independent of it。

 I think that's a little bit of them being a remnant or the artifact of them Vi starting off being a shared nothing system。

So this was introduced in 2021。which is not that long ago three years ago and the paper is 2022 so they're talking about it。

 but the paper was written in 2021 by the time it came out in 2022 And then I think around 2022 people noticed that you could no longer enable this feature and I think the response was。

 oh yeah， it's just always on but。As far as I can tell。

 as far as I know without having to cut anything here， that this was phased out。

 they actually got rid of this。But they just didn't publicly announce it。 And instead。

 what they did was at the at the storage layer， they have these。They mentioned nitro。

 the Nitro is the Nitro is not a single thing， but that's their sort of their。

What they call the project of running their own hyperadvisor。

 the specialized harbor that they're running for all the different instances on Amazon。

 and they have custom silicon on these nitro instances to do do networking。

 do additional processing for EBS and storing things and so one of the things that they've added is hardware acceleration through Nitro and additional card to do the kind of stuff that they were doing originally on the FPGA。

Right？So， the。You know， so this aspect is unique， but this sort of seemed like this was like a。

Not an afterthought， how say this。Snowflake didn't。Didn't really do this。

 It's basically doing trying todicate push down to the storage and。

But instead of adding much and more stuff down here， they just had the extra layer in the middle。

 Yes， does shuff with FPGs Drmel bit。 Yeah sorry， Oh no I said I thought you said Drmio。 Yeah， sorry。

 Drreemmel。 Yes， but that's like on the shuffle nodes and cells。 not like the storage layer。

RightI think what Amazon has done is push this kind of stuff down to the storage layer down here。

 And so instead of having a separate Samone service which this was。

 it's all in enough now just down here。You can see this with S3， like they have an S3 select。APpiI。

 like you can basically do wear clause on S3， independent of Redshift。

And I suspect that how they're relying on the same kind of mechanism。

But there wasn't really big announcement。 This awkward。And sort of disappeared as far as I can tell。

Without acknowledging that it's been removed。All right， so with the query Advd。

 then they don't really say much。I know that it's still based on it's always been heavily modified over the years。

 but it's still heavily based on in Postg query optimizer。

 so there's going be a bunch heuristics and rules in the very beginning to do some rewriting as part of what this piece down here does and then they're going to do something going to call space search to figure out the optimal join ordering and again unlike in Drmel and unlike in databricks where they assume they're not going to have query statistics in the case of a REshift if it's on reshift managed storage they'll run analyze and collect the data and build statistical models that them feed into the cost space optimizations。

For spectrum queries that are running after raw data， going after raw data on S3。

 as far as you can tell， the only thing they can do is go extract the metadata in the headers or footers or parque or files and try to push down filters based on those zone maps basic Minmax clause and things like that and I think that gets cached up into in the compute layer。

 so you're not always going to reading S3 for every single file。

The paper makes a big deal about this query rewriting framework QRF。

 and they aren't describing what it actually is， as far as you can tell there's no documentation about it because again。

 it's an internal thing， but they talk about how it's a DSL based approach where you can basically specify the patterns that you're looking for and then the transformation rules if you match a pattern。

 which is what we even talk about all before for query optimizers iss basically how they work。

 but they claim that they。Their implementation of it。

 their method of doing this is really easy for anyone to come along and extend it。

 they mentioned interns could use it get it working in three days or make changes in three days。

So this sounds like what the yellow brick people were talking about in the last class where they rather than make making principal changes to the internals of the query appizer and how it actually wants to do searches and en numers and other things that they have these sort of one-off rules where they try to patch things up for queries as they come in based on to sort of force the query plan in the form that they want。

So another interesting thing that Amazon does and their documentation for Redshshift is actually really。

 really good。They have a whole documentation page on how to make queries run faster。

 especially running on Redshift again where you don't have statistical information so they have a bunch of guidelines。

 I'm not going to read them all， but like they talk about how okay well if you know you're running on a star schema then you should put your fact tables and S3 and all your dimension tables in redshift managed storage because in that case you can least get statistics for the redshift managed storage data and then that' they're optimized will be smart enough to recognize okay well that maybe where I'm going to build all my hash tables and I just have this giant pipeline where I probe all those hash tables with my fact table。

They talk about how you should write queries in a certain way that you know that these things can be pushed down into the storage layer based on them being simple and whatnot。

YouX can actually also define statistics on these external tables or S3 tables。

 and that I think what happens is Amazon then goes and reads that data in， collects the statistics。

 and then stores it as if it was a regular table。So I've found this kind ofed。

Tllling you what you should be doing as a user to deal with the fact that you may not have any statistics on S3 data and instead's to preempt any problems that come later on。

All right， so we've talked about this already， the rich for nano storage again。As I said。

 I think it' separate node， as he said， they're running an SS3， or sorry S3。

 and they're going to have local attached SSDs。That。If they then fill up。

 then they spelled spelled S 3。 So this is why I don't think they're pure S 3 knows。

 I think they're separate。Like not EC instances because they're their control。

 but I think it's something separate that's just my understanding。

And I think the computer node also have their own local SSD cash as well。

But when you put things in Redshift managed storage， it's not going to be using parquet。

 it's not going to be using an open source file format。

 it's going to be using their proprietary format， and similar to what we saw in snowflake。

 yellow brickrick， and others。That spectrum or relativeshift spectrum。Do that chip。結こねす。Where。RMSMS。

 it would have to load into the proprietary format first and then they could on queries so Redshift just like calls。

pectrum。I can work in the native format， but work in all that honest。Yes so what she said was。

 for spectrumrum， it has the ability to read data on S3 in any possible format and then feed that data into the regular compute nodes。

But again， going back to my original point， I don't think they're separate nodes。

 I think it's just the same compute nodes。I did I shift the computer。Like the workcan。

 you pay for them， and you provision them separately。They get provision。Transpar。

Based on your query pay as you。Okay。That's helpful。 thank you。嗯。Again。

 because they want to manage everything， so when you create a table schema that they're going you can specify exactly what compression schema and coding s you want to use。

 these are assembled them and then they talk about how they have their own proprietary one called AZ64 that they claim is。

Comparable compression to something like snappy， but is' faster。

 but as far as know there's no public documentation that talks about it。 I'm sure there's a patent。

 but we don't want to re patents in academia。So it's for plausible deniability， patents， Yeah。

 you don't want to read patents。if you're a researcher。

 don't read patents because then if you you end up inventing the same thing。

 they can't claim that you saw their ideas because you didn't read the patent。Right。

 it prevent you from certain， you know， from maybe reselling or doing it， you know， monetizing。

 but it's it won't it isn't like。This I have to cut， what was the point of the story？😀Yeahは。Don't。

 don't read patents。 There you go。 that's the point of the story。Okay。So。

Here's here's the paper sorry here's the graph in the paper。 they show how much faster things are。

 So this is running TPCDs on free terabyte data set and so they have what they call the autoom box experience mean like just bulkload some data and then immediately run your queries at it and then here's the performance you're getting relative to redshift and then the tune one is like if you actually go add indexes。

 add compression properly。 actually spend time to actually tighten things up。

 Here here's what you can do。 they reading a series of papers and they that says look we're better than everybody else。

Well， this I we showed yellow brick last time， Right， right， So， I mean， so yellow brick is faster。

 This yellow bricks not in here， but like they yellow brick had。

Snowflake always as being a number two， right， I think。

 but yellow brick had anything resh if slower than yeah， snowflake and well， yes。Y。

 what's funny is this server is even less accurate because they're just doing TPCDs ontime than one。

2，3， four sorry， it's relative to reshift， sorry they didn't actually give numbers。

So thats I think it's forth。 it's rare to see absolute numbers in there just because， again。

 you don't want your competitors using your own numbers against you。 So maybe this。

Sades is actually legitimate， right？And maybe， you know。I'm not saying it's not legitimate。

 I'm just saying like， there's many different factors。 But say， you know。

 snowflake really was slower， and then they add new features。And to get it， get this number down。

 So now they can point to say， you know Redshift got this and we got back because we added this new feature So they wouldn't avoid all that。

 And they said， yellow brick， that paper is great because they put roll numbers in。 No one does that。

 But there's no way like Amazon Legal is going to let you put anything out like that。So。Again。

 I hopefully， again， you guys are are skeptical。 It sounds like everyone is。

 which is good about like what these numbers actually mean。 And they're actually， you know。

 the telling us anything other than to say， like， despite all their efforts to make everything be。

Serverless and try to remove the the need for a human to come and tune things。 you know。

 clearly it makes a difference。 Again， this number is not this number。

 right these are these are two separate know baseline。But going from this to this for bakery。

 that's a pretty big drop， right？Because I can't imagine the other ones got significantly slower and bigque is just the same if you're doing yes。

So when I see data like this。Should I look at to try it what information？

Try to objectively get from this， should I say， oh。

 this means redshift is really good with large data sets。Like careers like TBCPS， or should I say。

 oh， maybe it's the relative scale that I should think about。我是在这个位。

So it goes back to that I think that Reddit post I showed before。

 question is what should your takeaway from this。 It goes back to that Reddit post where I said before like you can simplify a decision like if you're already got much of data on Amazon S3 then you probably just be user to use Redshift or something that can access the raw files if your company where it's your job responsibility。

 to figure out which one you can use and money location of what cloud platform you can is' not an issue。

 you just don't look at it say， oh I'm gonna use this there's the whole process where you do a poOC they have solution architects help set up your cluster if you're signing for millions of dollars of years of service because you're also not paying monthly。

 you're paying youre prepay ahead of time to get a discount So you have solution architects that help set up the environment take a sample your workload running on whatever software you have now data you have now and then they'll run experiments for you。

And give you feedback。So it's， it's。For you， as a student who。I don't know you。

 I'm saying you't have any money but like，Yeah。I know I' was just seeing you calls。

So like for you as a student。An。Honestly， again， simplicity is what I would aim for。

As you said before， you can not cook the books。They can add a bunch of career rewriting rules。

 to say， oh it's TC， yes， make it do this one， make it do this one trick because I know that's gonna to make make a huge difference in performance。

 So you got to take all this with a grain of salt the。

Nobody' is gonna be making major at sort of corporate level enterprise level。

 making major decisions about choosing one or another based on like benchmark results like this。

This is just for them to brag in the paper， the word faster。point is a bit comparable and that's it。

Compar in terms of what。point， that's I'm going to say this in a second。 that's my end， my end。

My sort of glding remarks for the semester as Zach usually said， given that you know。

 here's all the optimizations that I can do， we saw through the last couple weeks of how they're all doing vectorized execution。

 they're mostly doing push based stuff， they're all doing some precompile primitives or holistic query compilation。

 they're all doing what you should be doing to get a high performance of lab system。

Good question Redshift only does the primitive doesn't do the hol。 Yeah， they do both。

 That's the whole thing。They code Genocce plus loss that where they inject the precompile primitives into it。

Right， that's unusual， nobody else does that as far as I know。Yes。business is point of view。前は。

Felfully I it break out like。Sucful because redshifts are syns and big like they're all based on。Yes。

 good question， so his question is。How can snowflake be successful as it is when it's competing against。

Microsoft， the Googles and the Amazons。And the answer is because they got there early。So as I said。

 in 2012 or 2013 when they put out Redshift， it was basically Park Excel slapped up on there and the idea was an Amazon's famous for this。

 they put it up there， if no one uses it， I wouldll just take it down。

 no big deal if people start using it and they start making money then they throw more money into it make it better so but snowflake came out of the gate probably getting if you compared 2013 snowflake or 2014 S versus 2014 Redshift。

 snowflake was probably faster。Can't prove it。 And I'm this pure speculation。 And， but over time。

 you know， Amazon threw a ton of money and do all this stuff stuff。 make it faster。

 But like Snowflake was at the right place at the right time and early enough， there there。

 there wasn't any other competition。So that's why they were able to succeed and grow as much as they did。

So now you may say， okay， well， what about the， the clickhouses， the Drmos， the， the， the druids， Ps。

 all these other ones that that like are coming， coming to the party a little bit later。嗯。You know。

 how are they going to compete against the。You know， against。

 the giants and the incumbents like snowflake。 it's， it's hard It's uphill battle。

 Ands got to figure out what the， you know， it's up to the companies to figure out like what's so one thing that they think they can do much better than。

What the big queries of the world can do。It is hard， yes。大看子。Correct， yes David is。

Say you have this amazing new idea。 like， how are you gonna Amazon is。You。

 throw a ton of money and implement it， yes。Now， big companies they're giant ships。

 takes a while like to move things， right this is sometimes called the innovator's dilemma。

 like you're making so much money on what you currently have which at the time maybe state of the art。

 and then something new comes along but it radically changes how you approach things。

 you're not really incentivized to go make that change and therefore the upstart can come and come beat you。

 That's basically what snowflake did OrRC already had andterday they already had cloud you're starting that cloud Vi they already had like enterprise grade overlapap systems that they could have sold on the cloud。

 but they were making so much money on Prem that' they didn't invest in that maybe early that they should have。

Terday is like the best example of this， right， or DB2 is another one。Um， so。

This what I maybe seen early in the semester， too， that like， oh that systems now。

 more than become the core engine， the kind of things we talked about in the China semester。

 they basically come and commoditize now you have something like veloc or data fusion where like you can get a high performance。

OAP execution engine out of the box。You know， you know， free。

 And then you sort of build something around it， to then you know。

 run queries and do other things and so。What makes maybe Snowflake unique in 2013 isn't enough anymore。

 and it's all about the user experience it's all about how good the query planner is。

know how well can you readate in that three without crying users to do a bunch extra of stuff like those they're harder to measure from a scientific objective because there's like qualitative aspects of the system。

 but I think those are going to really matter a lot。

I would say so the one area where you see like the Pnots and others trying to differentiate from these other guys is that this is not really meant for real-time queries like if I ingest data。

 know I want to be able to get query like almost immediately that you're not going to be able to do that with these systems that well and so they'll call real-time OAP systems where they're either doing heavy indexing something like Rocket does this Pot does this or you're doing automatic materialized views。

 thiss what materialize does so there's systems where upon ingesting of the new data。

 you're building some additional data structures that you can then query almost immediately。

In a way that you can't really do with these。These traditional overlap systems in the cloud。

But snowflake's not dumb， they know people want to do that。

 so they're adding their own kind of stuff take care of these things。Right。So that's。

It's hard it's hard to measure how good someone's experience with the system is versus another way。

 because you have to talk to humans and humans don't know what they're doing。

And so the best you can really do is mobile performance numbers。So as I was saying with Redshiftev。

 this is a good example of a system that has evolved organically over the time because。

 know Navy Start as a sort of shared nothing system。

 even though things moving into the cloud as we talked to them entire semester。

 you want to be dis guyed to storage。But then they， they've changed their。

 their architecture and add additional features based on what they're seeing。 And again。

 they collect telemetry on everything。Every single query， they collect image， all these patterns。

 and they analyze it。To figure out， here's the things that they they need to optimize。

 or here's the things they can make things run better。 I don't know the paper talks about this。

 But Ipricratus gives this example all the time。 The guy。

 the Se alum who who works on Russia ship now， that they looked at their telemetry and saw that。

Update queries were actually running really slow。 And there was a lot of them。

 which is not something you would think about if you're trying to build like an OAP system。

 because you think would mostly read only data。So they they went ahead and optimized update queries。

 and that made a huge difference and reduced their costs， made their customers happier。

 and they can do that because they have the telemetry。

 So going back to this compilation of service or。Oh， this aqua thing they added。

 They didn't add it because they thought it was cool。 It had a bunch of FGA sitting in the closet。

 they had to get rid of。 They did it because they saw the measurements from the data they've collected that this。

 the bottleneck， let's go try to add a new component， add another layer to make things run faster。😊。

Right。And that's that's the， you know。That's another advantage of being in the cloud where you see everything versus onprem where you throw over the firewall。

 hopefully somebody then comes back to report and says this is what ran slow， yes。

Since we're at the end of the almost course， I had a question。

 why is it that all the academic papers were looking at DCH？

And all of these industries are looking me CP。His question is。

 why are all the academic papers looking at TPCH and why all the commercial systems using TPCDS？呃。

I would think， so TPCH is obviously easier to get up from running。 It's 22 queries。

 whereas the TPC D S is 11， or sorry is 100 queries。And there's CT TEs and things like that。

 So I mean， the Germans can run TPC D S。 I don't know what they report numbers。

 but the the amount of the amount of work you have to do to get TPC D S running versus TPC H is much higher because you got to do CT TEs。

 I don't think it's any wind functions than TC D S， you got to make the query appr better。

 It's a higher bar from academic standpoint to get that running。

A classic another example would be if on the O TB side， there's TPCC， that's from 1992。

 and then there's TPC E。 that's from 2006。 Thats supposed to be the successor to TPCC。

 but nobody runs TPCE。 Actually， nobody in the commercial side usually runs it too because it's the pan ask actually write the code and get up and running everybody is runs TPCC。

I think so I think it's just from a complexity of getting the thing actually running。

There's a lot of open source implications up for TPCD S as well。 But for TPC E， there's nothing。

 There's not much。I thinkSo yes， I think it's just complexity of that。All right。

So as I said beginning， Amazon makes billions the B on Redship each year， right。

 They don't report this publicly。 but I think AWS makes like I think it' 100 million sorry。

 100 billion a year。And I know that Redshshiftiff as the paper talks about was the fastest growing service that they added in the AWS that I think got replaced by Aurora。

 that was the newest fastest growing one and for all and else off。

 I don't know what happens happening there， but theyre making a ton of money on Redshift。

But like Park Excel， they got acquired by Actin in 2013 for not much。

And then acting then rebranded as this thing called Act Ma。 But then they killed off in 2016。

 So as I said in the beginning， Amazon bought the license to park sell。For maybe 20 million。

 and they're making billions per year off of it。 Now， again， there's。

 there's obviously hardware costs， there's labor costs to build this。

 But I would say from their perspective， that was， that was cutthroat。

That was a gangsteroo in their part。Who here has heard action？

Nobody acting in is what ingress became or so ingress is。 So ingress， went public in。

Again InGgress is one of the first racial systems it' before Postgress， they went public in the 80s。

 got bought by computer associates， got handed off， passed around over a couple of years。

 they end up being a new holding company that they then change the name from from Ingress to actium。

 and then now they basically buy a bunch of these databases that are kind of in maintenance mode。

 Park cells in one of them， they actually bought vectorwise， that was in a maintenance mode。

 that was actually。They were attracted to trying to do something real with that。 But they。

 they bought pervasive。 they buy bunch of these older databases and they sort of milked maintenance fees。

 Then they got bought by another holding company out of India。 And so they still sell inggressss。

 I think they， I don't know whether they I think they still called ingras。 I might be wrong。

 But anyway so。Park sale again， sold off for 20 million， so sold a license for 20 million。

I don't know how much they got bought for， but I don't think it was that much， and then it died。

 and then Redshiftiff lives on。Again a lot of money database。All right。

 so that's it for the semester。 This has been fun having you guys。

 This is the first semester where we've only had one person drop the entire semester。😊。

And it wasn't for。know， for reasons outside of their control， so again。

 appreciate everyone being here。Thursday， next week， we'll do the final presentations。

 it will be random order this time。Hey， random's random。And then I would say， I didn't pick Redshift。

 I didn't pick Redshift last for any reason because it was like， you know， the greatest whatever。

 I didn't think it just covers a bunch of stuff that that we've already covered。

 And I want to make sure I include it because， it'， it's a large system。😊。

I don't have office hours today because I got head to the airport but send send any emails if you want to talk personally this weekend or send me emails of it like know you want additional information about your what your presentation should be。

 And then the final team again， the PF is on piazza。

 if you have any clarification questions post that in in Piazza below okay。



![](img/7cf1b1e00ceaa4b74c565ed591ecd77e_5.png)

All right guys， good luck with rest your classes。 See you。

you got a to get the 40 else get a grip take a sip and you'll be picking up models aining the puzzle because because a more man of town the 40 and my short got short。



![](img/7cf1b1e00ceaa4b74c565ed591ecd77e_7.png)

Sting the back on the table and I'm able to see St A on way。

No short with the cross you know what got them， I take off the cat but first' tap on the bottom。

 don about three in the freezer so I can kill it， cat full with the bottle baby don fill it。

 cose nice and says the pain off went， you can't get down with the guy little wild test。

 take back the pack of nuts。vo some same now to T to the， Billy De and to Chief the delicate weak Go。

 be a manic get a kind of same time。