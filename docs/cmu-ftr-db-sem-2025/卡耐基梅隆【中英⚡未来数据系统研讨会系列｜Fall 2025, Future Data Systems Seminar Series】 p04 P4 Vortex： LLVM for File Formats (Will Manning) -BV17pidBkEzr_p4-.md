# 卡耐基梅隆【中英⚡未来数据系统研讨会系列｜Fall 2025, Future Data Systems Seminar Series】 p04 P4 Vortex： LLVM for File Formats (Will Manning) -BV17pidBkEzr_p4-

But just want my peaces that pass God blessedless a friends。



![](img/7127562cbae335e449b5b64fde2a1899_1.png)

And check it out now I'm paying because it's bad friend。

YIt's time for Carnegie Mellon University's future data System seminar series This seminar is made possible by Google have Will Manning the CEO and cofounder of spD are the main company building theortex format which recently been turned to the anointed as a Linux project always the un to at any it's inoom in the office in New York City although there's other around you'll be so being the floors yours for thanks for having me I guess I'll start out quick agenda to cover some introduction and background on the ecosystem and where vortex fits in core concepts。

A of this talks like I'm trying to nail in the extensibility of vortex so I should actually go back to the title I originally called this LVM for file formats and then I was told that MLIR is the cool thing these days and so I had to correct it but you know then talk about the default components stuff like encodings we'll go through the file format by by byte and then we'll talk about some of the more interesting and novel stuff around how we do。

😊，Sort of compute pipelining and finally like some benchmarks and including thought。

 leave some time for Q&A at the end。So about me， I studied operations research。

 mathth and CS 15 years ago， did a reinforcement learning wave before it was cool it was a derivative quant and then I was a palanter for about 10 years I think I was。

Arguably or probably not even that arguably the senior most engineer at the company when I left I sort of one of the key folks behind Foundry。

 which is their Xabbyte scale data platform that's their main product these days I was at some point I think I ran every single team of the company that read or wrote bys in any form and then now I'm CEO and cofounder of spiral。

 which actually just means that I'm the worst systems programmer at the company。

So macro hardware trends。Because I think sort of， you， started the bare， a lot of the。

Software constraints actually just then the changes and data systems over time really come from shifts in the underlying hardware。

 So you know early 2010s， it was large pools of this like homogenous compute。

 It's like all CPUs are pretty fungible， lots of Ram。

 you know mesa So it's just pretend everything's essentially a giant single machine。

and there was a lot work of work around like， okay。

 we have this hierarchy of sort of RAM is faster than disk。

 which is faster than the network and that was like a totally immutable state of the work。Now。

Compfuseute heterogeneous like it's and it's probably never going back you know either the AI boom will continue and GPUs will continue to have more money behind them or it will explode and then GPUs will be abundant to but cheap in which case I expect data systems will incorporate them in other ways。

I think the speed hierarchy that I outline still holds for latency。

 but what's interesting now is there's been a flipening in that in bandwidth。

 so you know network cards on a P5 and AWS， you can get about eight times the bandwidth through the network cards that you can over the PCIUS to a GPU。

And you know， you're seeing this storage bifurcation towards objectvic storage， which is cheap。

 but high latency， effectively infinite throughput， and NVme when you care about things being fast。

And then。You know， a model I have， this is my model of sort of the evolution of data systems over the last couple of decades and all models are wrong。

 some are useful， but I think you know you sort of had。

30 years ago 30 little more you know Postgre was released the core thing there was it was an application database and the scale limits on the system sort of like it was determined by a human typing something into a keyboard somewhere。

 at least clicking a mouse。And then sort of the big data era was when we automated data collection and there was sort of this like monumental shift。

 I mean there was a Cambririan explosion， there was a big shift towards columnar analytics databases。

 you know all the web scale Mongo Phouse， everything else and then I think that sort of has culminated in the Lake house which you know I think as Andy and Michael Stonebreaker pointed out in their papers you know all this came around it's basically like oh yeah。

 we invented tables guys been around forever and then I think what's different now。

Seeing this sort of emergence with the heteroous hardware like we now have machine scale outputs。

 so you know big data was machine scale inputs， but human scale outputs will distill terabytes into a dashboard。

 but now I might need to stream terabytes per second to a GPU and that just looks quite different from sort of classical databases like you would never do that via JWBC。

The other thing is composibility， so obviously Apache arrow has been wildly successful for in memoryory sharing and sort of inter process communication。

 I think Ian from column is talking about。But the arrow file format is basically uncompressed。

 it like a it's justarrow IPC in a file， so it's not actually ideal for long term storage。

On the flip side， on the long term storage side， there's sort of iceberg and perquet。

 iceberg grabs up。 iceberg is a table format。 It's useful for。Essentially versioning。

 analyticsna transactions， transactional updates and for actually mainly consolidating metadata。

And I would actually argue that the primary reason iceberg is valuable is that it has been。

 it was a lot easier to add a new standard and wrap up parquet than it was to actually involve parquet。

 but parquet is what defines sort of how the bitetes are actually stored。

And you can sort of see this parquet predates， the other two standards， like you know。

 at least a few years。So。Is perquet good enough， it's why they supported some mature column or it's kind of reasonable performance？

Taking Honess's quote， the format is great compared to CSV。U， but again。

 Better Ri is a lot of headlines， you kind of know that my my response to as partK good enough is going to be no。

portline impossible to evolve， there are dozens of implementations outside of the perque project。

 I think the Wikipedia page list almost 20。The recent addition of the variant type happened。

 I can say that it happened， but it was， I think slow and very painful for all involved。

And then there are just a lot of deficiencies in terms of the metadata it's not you know。

 those are evolving over time， but they're not designed for object storage。

 it's ON in the number of columns that you have rather thanN in the number of columns you read so for very wide tables it's quite a lot of overhead。

And then the biggest problem is that the compression is slow， so you get good compression ratio。

 but it really leans on， especially these days Z standard to get a good ratio and Z standard has pretty limited throughput。

So what a spiral， I'm just telling you this for one second so you know why I care about this problem。

 I said。And you probably guess I put myself in that third bucket of databases。

 so we care a lot about stuff like data loading multimodal data into a GPU。

I usually say complex data machine scale is really。

I think data lakes are stupid like most people shouldn't use them why like why have files are a poor user interface it's better to have a database management system instead of every end user sort of building pro so the reason that people don't put video in databases is actually a。

Arguably at product efficiency rather than because they don't want sale or shouldn't。

The funny thing about spirals is optimized for throughput。So like I said。

 I sure my party trick is stuff like I want to stream this straight to a GPU。

We also do cuary analytics， but pre training is sort of probably the main use case。So。

Equs I think I mentioned this， this was earlier on the slide。

 but sharing files in S3 is sort of an infinite bandwidth way to share between systems and that's effectively the real key insight behind iceberg so you can transit systems between say snowflake and Databs。

But like for GPU data loading， as I mentioned， the network card has about eight times the bandwidth for the PCIE bus so the only practical is actually to stream by straight from object storage and parquet defines how the bytes are stored。

 so I care a lot about how the bytes are stored。Which is why we made forortex The idea was that sort of existing open source file formats were。

Not going to cut it。 I mean， perque is the one that I beat up on the most because it's the most common。

 but it's honestly the best of the breed。And we wanted to build one。And so a lot of this came from。

 there's been huge amounts of progress in the research community。

 and actually I think authors of a good chunk of these papers are on this call。

 neither from I annotated the ones from the FFF group at CMU， but also obviously。

Sort of Peter's group over at CWI has a few TUM has a chunk and there are a bunch of papers that I didn't even include on this list。

But the other thing is that industry was also far ahead of forK and tier one tech works basically just keep building perque replacements that are specialized to their use cases because it turns out there's too much upside in specialization to ignore。

So these' capacitor artists nimble， which is open source but。You pretty much only use it meta amiddi。

 which came out of Microsoft recently and then the other thing you could see is DBB has its own native format。

 Clickhouse has its own format， it turns out that storing these things in a sort of specialized way as I said。

 has like huge performance subs。So。As we were designing vortex。

 we thought could we obate the need for all of these custom file fragments can we make an open source alternative that is。

Kind of I think the equivalent of what data fusion is for specialized systems or what DDV is for say like Jo algorithms research it's like can you build the industrial sort of base and then if you actually want to make progress like how do you make it a harness or that progress。

 how do you make it extensible enough， how can even these industry closed source implementations。

 hopefully not start from scratch。I said it's open first forever， as Andy called out at beginning。

 we started it。Early last year and then we donated it to the Linux foundation earlier this year。

 so it's an incubation stage project at LFAI data， which。

Is the same sort of here as Delta Lake and which at least made me happy here's a fun quote from West it's like you I say the goal here is to put sort of the cutting edge research with an industrial strength sort of implementation。

So the project。We wanted to be extensible and super future proof that's actually the most important thing is I think you can see。

Goal number one is how do we stay at the cutting edge and then goal number two is how do we get to the cutting edge。

 but I think file formats last for a really long time。And you see this with parquet being again。

 it's 12 years old if we're going to replace it once it needs to last for at least another decade。

 preferably longer。嗯。And in general， future proofing。

 I guess we also mean preparing for stuff like GPP GPP compute。

And so that's sort of in multiple senses， like here are the hardwareships that we already know are underway and then preparing for。

 you know， avoiding the calcium kitchen basically。The other thing we wanted was just performance。

 so we benchmark every commit and every pull request against sort of the best available perquet implementations turned upductTP writes the fastest perque files that they write very weird perquet files。

Um， but yeah， our goal is， you know， and I think we'll get to the perforator at least 100 times faster random access。

We want faster scans， faster rights， the lowest priority of assess。

 like we want size to not be a deal breaker， but at least by default as long as it's kind of in the same ballpark。

 I don't think anyone's complaining that per k files are massively too large。

And then the last thing is， can you share what you mean can you share what you mean by like the D E writes the weird proque files because kind of goes like the Balkcanization of these implementation which I guess forex whatsoever so dev void they consolidate all of thes it's sort of stuff allowed by the spec but they consolidate all of the row group metadata so that you can get it in one read instead of writing the row group metadata alongside the group which I don't think I've seen in any other implementation and they also size it so that。

Every column chunk only has one page， so the row groups are sort of sized to get because they wanted to consolidate that metadata further so it's how do how do you align so that essentially the column chunk metadata applies to single pages so it was。

Certainly allowed， it was just a much more extreme interpretation of the spec than I think most any other implementation uses。

😊，And it's very fast to be fair， like those are good optimizations。Yeah。

 and then the last thing is we want to be in a row and I think we lean hard on arrow。

 so I sometimes try to describe vtex as the first sort of truly a native industrial strength。

 open source column file format。So we lean on and use error quite heavily throughout the project。

Sort of design goals as we' doing this， we wanted to move decisions from the spec writer to the file writer so。

That's another way of avoiding calification。 So we'll get to this later with layouts。

 but vortex files are actually largely self describing， and the file format itself is extremely。

Minable and so that lets us do stuff like should we have our groups is a decision that we can actually defer and it can be an area of open research like should it's really should the default writer have a groups or not。

The second thing was just fixing。The sort of known list of deficiencies in the metadata and perquet。

 it's like write a flat buffer， optimize the layout of all the metadata for topic storage to avoid lots of highlight sea reads。

UmPap buffer is nice because the sort of decentsialization cost is closer to， you know。

 order number of reference columns。And then the last thing was。

We wanted to design just getting to this future proofing or supporting GPU CT。

 CPUU CD and Fast rate access so fast rate access read being。you know， I have an external index。

 I know that I need to look up row number 42， how can I do that as fast as possible？

And that meant all of those things actually have overlapping constraints。

 it basically means encoding should be lightweight。Avoiding data dependencies。

 and we have to cascade those encodings to sort of get a good compression ratio。All right。

 core concepts of Orortex。All right， first off it has logical types so arrow is great arrow has physical types the type tells you exactly the byte layout in memory and so for cascading compression that's actually really annoying because it means you would have to enumerate every possible permutation of these arrays and different arrays in the same stream sort of the same like a chunk one would have different data types so we had to implement logical types。

😊，It's not that exciting， 32 bit ins， UTFA。More interesting is we have a， which。Corresponds to arrow。

 let's support cascaded lightweight compression and a way to think about a is it's actually a way to defer computation。

It's like I have this array that is logically say fast pit packs。

 but I'm just holding the compressed fights underneath and I can do operations on that and sort of stack those up。

Computer push down。Related to what I just said we have a bunch of compute functions Funnily enough compute is sort of merging with the notion of arrays。

 you can think of it encoding because it such transformation on compressed bytes and so what we actually build up with arrays sort of a logical query plan talk about that more later。

And then layouts， which is pretty novel， so layouts are conceptually analogous to arrays that the data buffers are lazy and so they can live out of memory and the row count can be larger than memory to use 64 instead of use size and it lets vortex be self-deib so we write a layout into every file and that lets us see sort of how the bytes of the file relate to each other but it actually provides quite a general abstraction you could in theory fetch these bytes from sort of non filele sources so you have a layout fetches bytes from Redis if you really want or like some caching layer。

In sort of the vortex library。We've actually played around with。

Using vortex for column data in Postgres so it's like you want to back this with sort of 8 k pages。

 it's a little extra crazy。嗯。As I said， your arrays are waiteded for computation。

 layouts let you defer IO。So you can think of， in some sense。

 these are actually just both terms for essentially stacking up query plans in the query engine analog。

 but for a file format。嗯。The nice thing about deferring IO is we can figure out how to evaluate and prune what actually needs to be executed。

 and so this is sort of the basis of how we build filter selection and expression push down。嗯。

I've said this enough times it's like layouts make the files self describing so it's like we can decide you want to write all of column A before you write any other columns。

 you can inter leaveve them， you can have row groups， whatever that may be。

And they're composable there are also layouts for things like a shared dictionary so if I have a bunch of chunks or pages that sort of share the same logical dictionary can do that we have a layout for zone maps we're adding one for bloom filters it's easy to sort of add new layouts over time for especially different indexing structures or。

Were at one for sort of chunkier data types so like a German strings。

 you could actually prune sort of sub buffers， for example， from the layout。

The other thing is every single one of those four that I just described is an extension point so you can add new compute function kernels。

 you can add array encodings， you can add new logical types， extension types， new layouts。

 and the library has pretty good support for that and the file format sort of a hooks for all the sites。

So。Yeah。Not to beat a dead horse， but we've taken a fairly extreme approach to extensibility it's actually quite inspired even the title of this talk is inspired by Apache data fusion。

 which I know Andrew likes to call it LVM for query Es like I think we try to think of vortex as sort of。

The file format or like storage oriented complement to data fusion in a lot of ways。Okay。

That was a lot。 I'm going to jump to the defaults。 So this is we ship with a bunch of encodings out of the box。

 we ship with a default compressor， we ship the default layout and layout strategies。

 and that's how we get quite good performance， you know， batteries included。嗯。You know。

 as I said we have cascaded lightweight encodings， the sort of big workhors like we use。

 especially almost all of them are either classics。

 stuff like dictionary which has been around forever or latest stuff from CWI and CUM so fast lanes in all of its incarnations fast lanes bitpacking early and Delta ALP。

FST。Sa them all here。 We actually had a contribution。 I'll get into this later。

 We actually have a P code deck array and we have a Z standard array， which is kind of fun。

 It violates my earlier point about lightweight compression， but we can support them。😊，嗯。

But the default compressor doesn't use this and in general we're going for like data dependencies for the enemy。

And I'll hit this a bit later， but it turns out that if you want to support the kind of the constraints for GPU Cinti end up being the tightest and they if you can design the thing to。

Have good support for GPU CT， it tends to support CPU CD very well and again lack of data dependencies lets us do efficient sort of random of access instead of decompressing a whole block。

But again， avoid snap the NZ standard， we avoid traditional delta and run length and we prefer dictionary and all the Fast lane flavored ones。

 ALP and FT。This is just a plug for the fast lights paper just great。

 we also have an open source rust implementation， I know CWI has a C++ one。ALP ALP is actually great。

 it's really intuitive， turns out that decimals should just be converted to integers and then you can use integer compression。

This is a quick index of I took all of the arrays and dumped their decompression throughput on my MacBook pro so dictionary string is a categorical dictionary so it's。

Turs out that copying long ish strings gets you lots of throughput。

 but I think bitpack from fast lanes got about 53 gigabytes per second on my laptop you can see in general they're quite a bit faster than say Z standard is one to two gigabytes per second and so dramatically slower than say fast lanes。

Then what we did is actually you know in addition to all these encodings we have what we call a compressor compressor is you can there was like an encoding selection strategy ours was inspired by the sort of decision tree in better blocks it's not exactly the same because we changed a bunch of the encodings out so this is ours you know we have。

Our own， like you know， but it's it's heavily inspired by the better blocks when we just updated it with sort of newer compression codex。

But as I said the compressor is an extension point。

 so Martin Lkaek who's the P codeak author decided to contribute an alternative compressor which we call compacts and so this is going for absolute size minimization。

 it mostly uses P codeak for numerical values and Z standard for all the rest。

You can see he ran on some chunk of the New York taxi data set actually。Default forortex is 433 MB。

 which is smaller than Z standard compressed perquet。

 but then compact vortex is sort of even smaller， Shaves off another 100 MBby。

The default layout strategy in vortex is loosely clickhouse inspired。

 but we're still playing with this， so what we do is we construct pages just a array chunks that have a multiple of 8192 rows that exceeds a megayte uncompressed。

 we compress those。And then we buffer a bunch of pages into what we call striptrie and so we flush pages once the compressed size exceeds two megabytes and so。

This actually works pretty well instead of our groups because we。It lets us get sort of。

ough locality and good enough compression chunks， but then for say strings。

 you might have many fewer values than you would for relatively low cardinality integers which pack extremely well。

when you say you're experiment with it， it's not so much experimenting with the layout because that's sort of fix in the file format you're experimenting with like the strategy It's like how do I choose the layout you know what layout do I write into the foot so this is like completely open here's my plug for this is great research topic if anyone wants to do research on top of vortex know the thing is we can also encode basically perquet Nick who's on the call know it's on his backlog of things he's dying to do and he has free time he does not because he has a form month old in the startup but like as to write vortex perque so you can actually pretty trivially replicate perquet with a chunk array a chunk layout ofstruct layout of chunk layouts where the sort of last the first level chunk gives you roadstruct splits it into column chunks and then the inner chunks pages。

And so。You know you can do that likewise， I think you can pretty trivially replicate lancees by layout as a vortex La。

Okay， so how do we do that？I'm gonna go to。This is the file format in its sort of minimal form。

 there's a bunch of data pages and then a postscript postscript is a few hundred bytes。

 it has a hard limit of 604 kilobytes， and then there's an8 byte and of file。

And so start with the EOF it's basically a version number so you can increment it over time and say like this reader doesn't support the new vertical file if we have to change something about the postscript there's and there's a postscript length that's actually just a hint it lets us make sure that。

We got the postscripts。In。If we didn't get it in the first read。

 we guarantee that we get it in the second read because we will always get the end of file in the first read it's  eight buts and in general we size the first read such that we always get the postscript because we know that it's less than 64K。

The postscript actually is quite amenable to both compression and encryption。

 all it stores is offsets and lengths， so it's essentially just byte ranges in the file。

Get to know the top level topology of the file and that's it so it has what we call a D type it's just the top level sort of schema of that corresponds to the root layout。

File statistics， which is really useful for sort of short circuit pruning like this is a partition to something can I skip this file entirely and the foot and then these postscript segments I say just offset length the alignment and then details for compression and encryption。

I guess sorry you sort of went through this what's important to note is those can be written anywhere in the file we write them by default towards the end like both because it's easier to write the writer that way and it's better for sort of IO coalescing optimistic optimizations。

 but you don't have to。This is the profile I'm going to zoom in on some sections。

 so I'm going to ski by this because there's a lot of information on this slide。So the footer has。

Arase specs， which is basically details about all the encodings used in the file， layout specs。

 details and multiple layouts， segment specs， which are again this offset length of alignment and then IDs for compression encryption which index into the compression spec and encryption spec arrayse and then you can see in the layout we actually use segment IDs and so the layout is basically pointing its's dictionary encoding you know what are the sort of actual byte ranges for all of these buffers within the file。

And so in this example， I have a structure array， loosely just a table with two columns named A and B。

 one is N32 and the other is UTFA。And then the way that gets sort of raified by the default writer。

Is that I have this structure layout。Wwhich will split it to columns the columns actually it's at the top is a zone map layout and our zone map layout is actually logically indexed。

 so it's every 8000 rows so it's again sort of click out that you can change that It's like easy to tune it if you want more granularity on the zone map。

And then， you know within that we have these sort of physical bite buffers on the data pages that are chucked underneath。

 so I abbreviate flat for those are all these sort of like flat layouts with a segment。诶。

This getting back to the Z maps what we store in zone maps is you can think of as per column statistics so or you think essentially the first row in that table will be the range of say zero to 8192 exclusive rows。

 what is the minimum what is the maximum for that data type。If it's nullable， what's the null count。

 course you can add other statistics over time， that's actually also a vortex array so it gets a little meta。

But it means that we can compress this， which is nice。And then the data pages， as I say。

 it's sort of this clickhouse inspired strikes layout bit full。Writing a verortex file。

 a user provides a stream of vortex arrays or can just give error record batches because we can actually convert essentially basically essentially any error array can be zero copy converted into the vtex equivalent。

And then we pass that to vortex rightite options， which is where you plug in all the stuff around sort of the compressor。

 which is the encoding selection strategy and the layout sort of selection strategy。

And so we actually have。Some folks that are writing their own there it's a relatively advanced use case。

 but if you really want to customize everything in the file and how it gets written like we're talking。

 they have like some very large JON payloads and what they want to do is basically fully shred them and then Z standard compress the original in case they need to display sort of you know the actual JSON in a UI。

And so， you know， they get to write their own sort of cu compressor and layout out strategy for that。

There's a very fun exercise for the reader， the answer is in our code base。

 it's like we parallelize the rights without using row groups， which was kind of a very fun。😊。

Exercise， the hint is it involves vector clocks and is kind of akin to how you can insert rows and columns into an Excel spreadsheet。

 but it was it was a particularly satisfying bit of work by owners T on our team。

Reading is totally different， so reading is we actually instead of implement having every query engine implement a file reader。

 we implement an absurdly optimized scan operator。That we want to be used by every query engine and so that means that it can be fast everywhere it also means we're spending a lot of time optimizing the scalar compute we don't do joins。

 but it means there are parts in the vortex library that look。

Or use a lot of techniques from a query engine。So a way to think about this in the limit is the query engines that we're working with。

 I actually want them to push down everything that can be pushed through a join it's like how do I yield you sort of the。

The like the scam， so I send you as little data as possible。

And as like much sort of transformed as or close to the sort of target desired input for your join or aggregation as possible。

And you know， I call this moving the interface it's actually inspired by your rod from Tiger Beetle he gave a talk systems distributed and you know his whole thing is if you want to improve sort of by orders of magnitude。

 you have to change the interface。W what what like what do you what the what is the。

What would the calling query engine that invokes vortex pass down is it like a expression tree is it does it look like the arrows expressions as something sits vtex custom we haven read expressions。

 it's pretty easy to make an injection for sort of data fusion or any other ones like we have it forductTV2 they're pretty vanilla it's actually that we have a subset of expressions that you would have in a you know sort of a full query engine it's like I'm not going to support join。

But yeah， it's essentially you just configure a scan with a relatively small number of sort of like builder options and here's an expression to represent the query。

So。Table scan runs over layouts and it returns a stream of arrays， as I said， no requirement that's。

Tied to a file。It orchestrates the bare minimum amount of IO required for filter and projection expressions。

And it runs the bare minimal amount of compute required for the filter expression。

But then it runs zero compute for projection expressions like the thing here is you get the stream of arrays。

 each of which is lazily evaluated and you can think of these arrays as essentially a tree much like a logical plant。

That we might have optimized， but is wrapping compressed whites。

The most common function on these arrays is what we call canonicalizing。

Canonicalizing is turning it to a form with's zero copy to arrow。And so in general， you know。

 we'll push through。We can we can push down a lot of operations I'll talk about that in a second。

 but then in other query engines so for example in DTB we can yield native vectors。

 we can give it a dictionary vector but we can even give it like an ALP vector because it turns out that both we and DDB use ALP for floating point numbers and so we can defer all of that decompression and just give it sort of the native form and then。

Ditto for sort of coUDF so as you start moving on to GPUs， it's like it's a different target。

So we have lots of types of pushdown as I alluded to we a filter pushdown。

 can think of as pruning rows based on maybe the zone maps， for example， projection pushdown。

 pick column A， drop column P。Expression pushdown is sort of functions on columns。

 so it's like add one， for example， to every valueized column。

And then there's also selection push down so that's sort of the same as expression pushed down。

 but if I have a mask and so I might have masked out some risk and then what's fun is behind these sort of operators。

 again thinking that like a compute engines plan， we can actually implement different notions of compute so you can have sort of kernels for GPU C and also for CPUU CD。

嗯。Yeah， the fastest way。To do any work， the best form of optimization is to not do the work at all。

So this is what I said earlier， especially for DDB because we sort of both。

By default is the CWI phylogenetic tree of encodings， we can just pass them sort of encoded data。

The next fastest is to produce n factorial handwritten fusesed kernels， no one's going to do that。

But the middle ground and this won't be a surprise to most of this audience is to do things can sort of mo ADV and the classic sort of vectorization。

 like can we just hang out in the L1 cache as much as possible？

So we're implementing sort of pipeline compute over 1024 elements at a time。

 reuse allocations the goal is to have essentially zero extraneous allocations from the initial read into the target buffer so in theductDP case ifductTB gives us a vector。

 can we just not have any intermediate allocations at all。

 you just have some like reusable scratch space copied into the target vector it rips along does its work grabs the next one。

Um。We then can handfuse sort of the most important comment kernels stuff like frame of reference with the Packing dictionary of。

And then， you know， because。Everyone who loves vectorization。

 there's also the people who love compilation， it's like should you jit it for CPUs。

 we're not jiting it。But for GPUs， we jet everything and so this in theory kind of works the same way as the pipeline CPU compute construct these pipelines from the plan and iterate over 1 thousand24 element batches。

 but KUuda basically has its own。I think NVRTC is NviIDA real time compilation。

 it's actually pretty normal in Kuda land to just jit all your code。

Because there's so many different hardware architectures， well they're all in video， but。

10 different versions， 12 different versions now。And then we also target WebGPU。

Turns out most of the same to egg supply。Some of the work we're doing right now and this is should land soon because can we do the pruning in the orchestration and from a file on the CPU and then can we have the data buffers skip the CPU entirely to just read them straight over the network like through the NIC to the GPU device and so then you can do decompression without having to pass the sort of data through the PCIU bus because as I said earlier。

A lot of the sort of high end GPU Michigans have an order of magnitude more bandwidth through the network cards than they do through the PCA bus。

 which is sort of a fun fact。嗯。I've really abused this horse or hinted it too many times。

 but turns out that GPU C。Overlas with CPU C in terms of what makes it work well。

 I think in practice， GP C has the tightest constraints。 So if you meet those constraints。

 it's trivial to basically make。Make it work nicely on CPU Cd and random access reads are even more trivial。

So here's some bits on vortex from Out the Wild， as I say。Any blocks。

 which one best research paper at the LDV last month。

 I would paraphrase any block as the best way to make parquet fast is to embed a WSM build of vortex it turns out that WASM Cindy is not far off native performance and you get just dramatically faster foring parquet which。

This was kind of fun for me because we obviously used some the toUN research and then this just appeared I had no idea they were doing it。

Liquid cashash it's work by U Wisconsin Madison Shang Pg is great。

 we're actually sponsoring this year of his PhD alongside influx and I think Bel plan because he's just great and does great work this is integrated with data fusion。

An earlier version of liquid cash， there was an issue that tickled me。

 which was it turns out that even having an in memoryory cache。

 it doesn't guarantee that you're faster than reading Fort textex for S3 because we've optimized living daylights out of it。

U。We did a talk in April with Microsoft and Lance， so you plug vortex into Spark， this was TPC。

I think its TCDS use less storage， this was just converteding one to one perque files in an iceberg data to vortex and then。

For CPCH， we got a sort of full like 30% reduction in runtime。

 I think that would be more now it's like six months later and the product has gotten significantly faster since then。

 but pretty good speed up even in Sp which has tons of overhead。This one made me happy somosaic。

 which is now part of Databricks， has this popular streaming data loader。

 so it's read a file from S3， load it into a GPU。It has its own custom file format。

And vortex was just 2 x faster with no tinning。U。And then this one is I had someone who recently moved from Lance and we were two and a half times smaller and about 10 times faster in terms of scan throughput。

We also had a。Startup who I won't haven't asked permission to name。

 but tell us tell the story they came up to me and they they have a data fusion backed API that was using perquet and they moved to vortex and it was a full 10 x speed up in their P 99 query time。

 which was pretty cool。

![](img/7127562cbae335e449b5b64fde2a1899_3.png)

Turns out we're not the only new file format。I took Andy's you nice screenshot of Andy's comment on hacker news。

 there's a bunch， there's sort of this whole phylogenetic tree campy an explosion of。File formats。

 so there's nimble from meta， CWI has fast lanes， we have vortex and then obviously the sort of recent FF F3。

I think。You know， there's a lot of overlap between this work。

 like I will happily say vortex uses done like almost all of the same encodings in the Fastlands file format and we looked heavily at Nimble when we were looking at some of the like flat buffered metadata for the file is like in the file layout stuff。

And then F3 obviously it's like you guys use some of our encodings。

 hopefully we'll pull a bunch of the F3， has some stuff back into vortex。

 I don't know this is a nice thing about open research。😊，Anyway。

Benchmarking we run really extensive benchmarking on every commit and on demand on every pull request on dedicated instances in AWS。

And so， you know， this is my if anyone wants。That ismackdown about their bio formatmat， I'm ready。

So for random access， actually， we benchmarked against both proquet and Lance we're the fastest way。

137 x compared to per k， this is Z standard compressed per k sitting on NVME and it's grab six arbitrary rows spread out throughout the New York Tax dataset set。

嗯。Compression throughput to right speed where we write about five times faster。

 take the geometric mean。Its certain geometric mean percate divided by vortex against this is taxiy data plus a good chunk of the public BI benchmark data sets and then full scanandy compression。

 which just gave it to me asarrow。It's about 18 times faster than per k。For compression size。

 we're in the ballpark， you know， for some data sets。

Or half the size for some data sets were 50% bigger。

The mean across the ones I benchmarked like the geometric mean was 1。16 so a bit bigger。

Click bench we。Pretty much just destroy all the other file formats DDB is the fastest my personal favorite is that DDb vortex is faster thanductDB native。

When queried from DDB and so you know that's sort of a fun。

 I think we benefit from the fact that we don't have to make these files sort of uptable in place is the only guess I really have and otherwise there's a lot of similarity in overlap。

You can see that for data fusion。You know， we end up being。

Quite a bit faster you know suddenly like reduce the runtime by 3040% here and then lance is six times slower it's not even not even really in contention Was that was it was that it between vortex of vortex compact that's the one that uses P codeak and Z standard so it's the alternate compressor strategy。

Yeah， so。这样子。For。TCH， this is backV3。It's actually funny。

 Vertex Compact does a little better than vanilla vortex。

 and I think it's because it's smaller and just downloading all the data from S3 is faster。

Like you basically it reduces to I can just download all the data and then decompress it。

But still faster than perque。You know。This is again， sort of TPCH， this is on NmbME。

 not quite as fast as WB native now， but still competitive and much faster than the other formats。

All of these have， by the way， I should have said that the X multiple is using click benchch scoring。

 so geometric mean of query time ratio to fastest with a 10 millisecond shift it' a weird metric。

 but a common one。And then I take total runtime because we look at both。

So to recap I think Fortex' state of the art gives pretty optimal performance。

 like I said for basically any metric you care about。

 I don't think there's another column for file format that。Beat it at a moment。

 then outform specialized file formats like it's faster rate of access than Lance。

It's faster for sort of GPU workloads than MDS， and then we'd have this sort of notion of extreme extenensibility。

 which will probably make even more extreme。If we add the F3 stuff， it's2p native。

 industrial strength and implementation， it's open source， you know， contributions welcome。

And this was the goal I said sort of earlier in the talk，s。

 can we obviate in end for all these custom file formatments like kind of to coal sense。Very。

 very excited to collaborate you know as I said I want it to be sort of what LLVM or MLAR for compilers with data fusion is to specialized databases and what DTV is for research so can we sort of make this a good harness for file format research because I think then we can you know move those insights rapidly back into something that benefits the sort of actual practitioner community。

And it's already used in F3 and MA blocks， hopefully in more places。Trying to， you know。

 I'm very happy to sponsor grad students， especially in the IO stuff。

We have integrations with lots of frameworks， we have bindings in Python， Java。Little C++。

 we have integrations withductPB data fusion， Spar boatload of Python frameworks。

Like you don't have to build this build this with us and then you know if you're want to do experiments。

 especially again for the the researchers out there more than happy to like。

Put our benchmarking infrastructure， you're welcome to use it to write your papers like basically I'm happy to bankroll that。

So。Whether you're in industry or academia， we want to you。To build the future。

All rightI will applaud on behalf of everyone if you will the awesome talk we have time for questions if you want to go for it to unmute yourself and fire away if you can't speak just post in the chat and I'll read for you。

I will that was a great talk and a quick question about the scan operator which makes such ton of sense so there are two parts of the question on the earlier part you mentioned that in many ways all the multimodal data that you see can be encompasscomped in a structured file format like this how far did you think you want to take that you want to replace file systems with that might be storing video objects and image objects with this or would you go that far and then I have a followup question I think it depends so I think in most。

At least most real world use cases， even with files， there's， you see a lot of。

I'm going to say like loosely relational operations on their metadata to say like this is the video I want and so you know it might be like filter or filter to audio files that are more than 10 seconds and then actually push down a function that's like give me the first three seconds so。

Some of those might be externalized again， like there's been a ton of work on video codex。

 and it's not clear to me that we're going to immediately do better than the video codex。

 but I think there's a lot of value in。sortrt of making the metadata freely queryable so that you can do these sort of relational queries and then for the video you either externalize it and then internalize it depending on what the sort of data system being built needs。

And so。That's like it can kind of go either way， I think there was a very cool paper though。

Called frequency store that we saw that was essentially doing a War transform on images to decompose them I would the intuition I got from it was it's roughly like a Taylor series where the more you can decompress it into columnar form and the more columns that you choose to sort of mash together the higher the resolution the image and I think there's a bunch of actually very cool work that could be done especially for sort of GPU oriented queries where we see this already with folks doing image data where they they essentially create projections like here's one where I decompose out this channel or it has like this sort of peerramiditive resolutions like the ultra high resolution 15 gigy satellite version and all these downsampled versions and it's like I think we could potentially encapsulate that in the data system with something like frequency store and put those columns to the vtex and do something compelling。

O that is great and then the second part of the question is as you're looking at feeding all this data in a efficient fashion to the GPUs you still have a ton of bandwidth left in the GPUs or are you able to saturate that by having a whole bunch of scan operations going on to different files like how do you still keep the GPU that busy there's a ton of bandwidth there right the trick is I think I think the best we can do is you have。

😊，Relatively high concurrency being orchestrated by the CPU that's opening a bunch of files at once。

 like again， S3， you get lots of like lots of bandwidth by having many connections。

 like you get about 500 MBbytes per second from a single connection。

 And the way you scale it up to get terabbits per second is just having boat loads of connections。

 And so those could be against many files instead of just a single file。 It then becomes like。

It's a database problem，' like which which ranges of which files do I need and that planning I think happens on a CPU and then it's like you just pass just pass the sort of encoded buffers to the GP。

Over the network。Cool， okay， thank you， awesome talk。P。Thanksville， for the nice talk。

I hope you can hear me well I have a small need to just to not to confuse And's database of databases。

 you mentioned that Monetbi was the database system that was manipulating data in chunks of 1024 that is not correct。

M to be as a called at the time system， so if your table would have a billion columns。

 it would actually use the gra of a billion， it was vectorized that was creating the notion of a vectorized query execution。

So not not Thank you for the correction I will fix that before the next time I in Will's defense the title the system is Mo to be slash X 100 right Yeah it's I was thinking of the paper more than the system but。

😊，P clarify now a real question， a real question。 You mentioned in the benchmarking section that。

That TurkeyB was either faster or slower in its own format on the clickbes with vortex。呃呃。

Was either faster or slower than fortex in its own format and but there were kind of two experiments the first one was the second one was on MVme and the first one on MVme vortex was slightly slower than in O negative format what was the first experiments referring to clickbech but we rate it againstBme because official clickbech runs against EBS which has really weird latency properties it looks like S3 the first time you request something and it looks like as slowish SSD the second time you request something So we run clickbench on MVme so you get sort of stable IO performance。

So in that， so that's that's in Amazon on。 Okay， Yeah， this is about Amazon。

 So we're running at a metal instance。 So official clickbench runs on E B， in fact。

 prior generation E B， it's really weird like G2 E B from the like G。

 explanation of that because that has to do probably with the amount of。Fets that you have to do。

 And basically with the way metadata is organized or is because I， I imagine， Yeah， Yeah， my。

 why does why does， why does Fortex profit more from E B， S。fromme yeah。

 I didn't I think we profit more from NVM was basically when it came out like we were faster on NVMme I think on official click an official click benchnch we're a smidge slower but on my on the click benchch we run on every commit it's against NVM like it's modified to run on NVMme and vortex ends up being a bit faster so I think we have more would be what would be the reason for that。

We haven't tracked it all the way down， but I assume it's like there are some differences in IO like we tend to have longer sort of runs of a given like form of compression。

 So， you know our pages might have many more elements or as I think WB compresses every 2048 if I recall correctly So there's like somewhat of a different granularity of sort of the compressed buffers and you know there's different IO planning。

 So I'm not sure that。I don't the short answer is we haven't debugged it or like profiled it quite far enough to know exactly what the difference is。

 but that's sort of the intuition as I think we gain in some cases by if you have a long run you know we might actually more compressed like if you bit pack integers we might bit pack 256000 integers into you know two bits each with like F4 And so I can just rip through that pretty fast。

 The other difference is I mean to be fair vortex uses fast lane bit packing andduct B last time I checked uses mirror doesn't do as that use slower a slower bit Yeah use a slower bit So it could also just be the bit packing。

Because we use so much bit packeting。Right， final question， sorry to monopize this。

 you kind of praised the approaches like any blocks and F3 that propose to use Vaasin。

 but is Vaasin not kind of a complete blocker for running fast on a GPU？Oh， it is。

 The The value for Wm is actually， I think， purely in forward compatibility and shipping changes to the file format。

 So it's nice for means that old readers can read the the newly written file slowly instead of being able to read it。

 Not at all。 Like you would never depend on a Wm thing。 right， Like I don't think we would ever ship。

😊，And encoding in WSM only form， we would ship an encoding where you say it's readable since you know some older versions that doesn't include that encoding and so I say I will bundle a WSM thing of you know encoding X new encoding X and the API would be it will decompress into error like it just decompresses that buffer straight into it like arrow IPC and so it's a dumb function to take opaque。

Like what to the old reader is an opaque buffer， it's like basically run the WasSm function and get some arrow and then you could manipulate it。

So it's just a way to ship new encodings without breaking old clients。Okay thanks。

 we'll get back to you on the sponsoring minutes， bye bye， thanks for the time。Thanks， Peter。

 other questions？Its fun out the wasm is like it's like kilobytes per column right it's not it's not massive and it's its meant to be as a backup solution Yeah I mean any B does it completely differently any B does like a 70 megabyte make up a lam build of vortex。

But yes， okay。I have a lot of questions。Have you done the performance comparison of vortex on the running on the GPU versus like？

Kuta Ras like they're， they're， they're。They're an in house written implementation of a parque reader。

We don't have all of the encodings yet， but at least on the sort we have reasonable implementations。

Of all the fast lane one which are we reported essentially Peter and his seems were they had a Fast lane GPU and ALP and we're working there was a recent thesis from T delt and like some papers on a variant of SSSST for GPU decoding that we're working on so we don't have we don't have all of the encodings yet and it's like that's the thing that we're basically we're filling in that matrix right now with a bunch of GPU kernels。

The， I mean， again， the sort of core bread and butter， simpler ones ignoring strings， we get。

 you know， hundreds of gigabytes per second， which is like quite a lot faster than sea standard on。

On a GPU。And then one one of the challenges of course is like with the just time compilation systems is debugging them。

 right， but I guess in your case， because you're only combining like a small kernel。

 not the full query plan right it's actually a lot easier to isolate。Got it。 Okay， and then that。

 and then the the just an ail basically gives you。Compatibility with whatever。

Version of Nvidia you land on Yeah because it's for all the NviIDdia GPs it's like， you know。

 you can think about it of GPUs have many more sort of tiers of memory access and sort of complexity of compute and so we might say like there's this version for you know Nvidia version9 and up which is like。

Blackwell， I think， which has like an extra tier of memory access effectively。Got it。

And then can you comment on like what sort of methods or strategies you guys have adopted or would like to adopt to ensure like the long term compatibility of both the vortex file format。

 but also the actually the APIs as well because you mentioned that like。

You know some startup is or somebody is has this JSO stuff and the writing custom layouts so that if that API breaks in the future then they're kind of screwed as well right so the file format I think we have good backwards compatibility guarantees right now so any file you've written will still be able to read that's the only guarantee we have right now turns out for like APIs we keep we're kind of preserving the optionality to break APIs but I think。

There， it's just like active engagement with the community of people， like the number of。

I don't think your average individual is going to write their own layout strategy for a production system。

 it's like a relatively low cardinality of these startups are investing pretty deeply in their storage engines and I think I know all of them and so there it's more just like help them migrate it's I mean like data fusion breaks。

 APIs literally every release and that's why they do major versions every release。Yeah。

 has hundreds of projects using it I think you know we it will。

It's more like the incremental rate of breakage is decreasing over time。

 but's it's not going to be zero， I think on the API stuff file format back and back guarantees we have to maintain and there。

 but for now we don't have。I mean， we don't have a sort of strict forward compact。In any way。

 so it's like that's something to add， you especially if you have like a custom layout or something that's going to be a。

Thing where you have to link in the code that purses that layout now there's not sort of a WASM I mean we could write a WASM equivalent for that at some point in the future like again akin to F3。

 I think all of these kind wasSm。We thought about that I think we pass on I forget why though it gets quite early I think the API service area for layouts is like yeah larger yes。

 and then you I don't know if you mentioned this or not。

 but like vortex is written in rust what are you guys doing to dissuade？Again。

 randoms from the internet writing their own Python Fortex reader or C+ work I mean fortex reader like the avoid that's sort balkcanization like parquet suffers from mostly just get good bindings like we have good Python bindings。

 we have good job bindings， we have good C++ bindings， we have data sources again we。

We benefit a lot from the arrow integrations。 like it turns out in Python。

 you can integrate with like several dozen different frameworks just by implementing the piarrow data set API。

 So we have P。 and then we have again， we have sort of。Special case bindings for。

The engines that we carry like， you know， want to invest more deeply in or partner more deeply with。

 but we have good catch all ones that we sort of do via era and then。And it was equal plus。

It turns out what I think if you can get。Rust C+ plus sort of like nice interchange pretty easily。

 And so I think that covers， that's like the only。Compelling case for reimplementation。

 I think is from C++ land because any other reimplementation is almost surely going to be much slower Like C++ is going to be the only performance competitive one。

 And so there I think the strategy is like have good C++ bindings We even talked to like the snowflake folks about integrating it into snowflake and therere a big C++ shop when they were pretty happy with let's improve the binding rather than we'll reimple it Yep got it all right my last question is can you comment on how vortox might work with the me has recently announced open ZL like data where compression framework that came out last week。

I didn't look at it closely enough， but it seems like they construct a dag based on the structure of the data。

 I mean we could right you have a open Z compressor and a bunch of open Z arrays。

 I think the hardest thing would be。I think we would probably need arrays to represent the sort of leaf or like all the different component compression steps that they support。

 and then you could just use it like it would just work like we can have an open Z compressor like we already have the Z standard array so you can read Z standard encoded data So I think we would do something kind of similar。

And it should just work， its new encodings， new compressor。



![](img/7127562cbae335e449b5b64fde2a1899_5.png)