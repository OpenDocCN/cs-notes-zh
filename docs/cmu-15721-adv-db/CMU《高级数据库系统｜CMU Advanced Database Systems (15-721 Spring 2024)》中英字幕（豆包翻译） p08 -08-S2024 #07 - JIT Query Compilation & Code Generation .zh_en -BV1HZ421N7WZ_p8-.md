# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p08 -08-S2024 #07 - JIT Query Compilation & Code Generation .zh_en -BV1HZ421N7WZ_p8-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/7e2db76ed9b200ab5de16ef8036e8f31_1.png)

🎼。Let's get starting， it have a lot to discuss。Okay， so。This class。

 I'm going to try to jam as much as I can in talking about query calculation and cogeneration。

 and again sort of like the vectorization stuff， another technique we can use to make our queries run faster and run better。



![](img/7e2db76ed9b200ab5de16ef8036e8f31_3.png)

So in last class， we spent time talking about how we're going to use CID to vectorize some of the core database algorithms we have in our system so that when we run to sequential scans。

 we can achieve data parallelism where we allow the data system to execute the same number of instructions but operate on multiple tuples at the same time so again this is data parallelism or in query parallelism is's another way to describe this。

So the paper ahead you guys read today is from 2002011。

 and it's a really seminal paper on on query compilation cogeneration。

 It certainly was not the first。 It wasn't and it wasn't's sort of the modern error。

 it wasn't the first to say here's how to do it it is。

 but it sort of set off this investigations from multiple systems to multi researchers on using the LLVM to optimize things。

 So a lot of the papers in the early to mid-2010s sort of give the false impression that if you're doing vectorization。

 you can't do compilation， if you're doing compilation。

 you can't vectorization and the hyper paper you guys read。

 they talk about you don't need to do vectorization because they can do they can do this pushbased model and data datacentric optimizations。

But we'll see at the end these aren't mutual exclusive and you can do both。

So we showed this slide before that again， that since we're trying to execute sequential scans in our OLAPP database system。

 we have to rely on making the database system actually the execution engine as fast as possible so that we can get better results and make the system more efficient。

so we've gone through a bunch these already so how to reduce instruction count。

 reduce cycles for instruction and then parallellyze things。

 which again we'll cover more of that next week， but today's class we're going be focusing on this first one here now we care about reducing normal cycles certainly。

 but the compilation of the code specialization technique we're going to talk about here today is really about how to make sure that the database system does exactly what or only excuse instructions for exactly what it needs for that query。

😊，And then the idea zone is like hard coding a program to do nothing but execute that query。

Sove and then once we've already done this， as part of doing this。

 we can also design the cogeneration components in our system to be aware of what the CP wants and generate code for us that's going to be optimal for this。

So the reason why compilation cospecization query compilation is can be important is because if we're bringing all these files from disk into memory。

 and we assume that there's not gonna be any diss in while we're processing queries。

 we can do asynchronous I， we can let something in the background go fetch the data that we need。

 obviously there's a pause in order to get the first thing maybe we need into memory。

 But while we're crunching over these large parquet and orque files can think of them in hundreds of megabyte not not 4by pages。

 while we' we're crunching over those files， something else is the background is going go fetch the data we need next and bring that into memory。

 So that when execution engine comes around says okay， we do more work。

 the stuff you need is already in memory。😊，So we don't have to worry about disk stalls in this environment。

 Something else is going to sort of hide that those stalls for us。 plus， as I said before。

 the disk and network have gotten really fast。 So it's less of an issue。

So there's this great paper from Microsoft in 2011 where they talk about what would it actually take to build a database system to run orders of magnitude faster if you're just trying to reduce the number of instructions that you have to execute while you run queries。

And they made this observation that if you want your data assessment to run 10 x faster。

 then you need to execute 90% fewer instructions than you normally would。Seems like a lot。

 but that's actually doable， right， it's not far fetched that we could achieve this。

But if you want to build a assessment that goes 100 x faster。

 now you're down to really cut in the bone because now you got to execute 99% of fewer instructions than what you were doing for and there isnt there isn't a flag of Gcc like 100 that's going to achieve this for us it's gonna be through careful engineering and through this cospecization and compilation stuff we're talking about today is how we can actually achieve that And of course。

 as I said， it's not just reducing the number of instructions we also care about these cycles per instruction because we don't want we can actually fewer instructions but we keep stalling going out to memory because the things we need aren our LCD cache then we're not gonna get the benefit we thought we're gonna get。

So today's class is really about。😡，Although we're never to get this， get，99% for instructions。

 but we can do a pretty good job and get somewhere in the middle。

So first I want to talk about the background of today why to help moving。

 why we want to do cogeneration or query compilation and then we'll talk about sort of the two main techniques。

 There's the source of source compilation of transpolation that'll be from early work before the hyper1。

 I think the Hy paper talks about it basically how to write C++ code or Ru code wherever you want to generate another programming language code。

 and then you run a traditional compiler on that。And then the hyper paper you guys read。

 this is about generating literally like a low level representation like some IR within your database system for the query。

 and then using something like an embedded compiler like LLV un compileild that。

So at a high level at a high level they're the same。

 they're still achieving the same thing like they're doing codespecization for a query。

 but there's sort of two different ways to approach it and there's going to be engineering and compilation costs trade offs between the two approaches。

And then we'll go through a quick smattering of a bunch of different systems that are going to do these different techniques。

 and then we'll finish up talking about we can do a quick Q&A about how things are going with the projects。

Okay。So the， as already said， the way we're gonna be able to reduce the number instructions we have is through code specialization。

 And again， the high level idea here is instead of having in our database system。

 these giant switch statements that are going to check to see what the query operator type is the plan operator is or what the data type is or what expression you're trying to run in your where clause instead of having the switch statements to iterate over these things execute the exact piece of code you want。

 We're literally gonna hard code some sequence of instructions that do exactly what the query wants to do。

😊，And again， the great thing about SQL and the relational model is because everything' is declarative。

 we know exactly what the data looks like。 We know exactly what the SQL query wants to do。

 So it's not like we can roll the dice and get things wrong。

 we can look at the catalog and know exactly what we want。😊，And again。

 something like a parquet file an orc file， even if we've never seen the file before。

 we could look in the header and figure out， is this schema matching out what we expect。

 and then we could do code visualation based on that。So， the。One of the ways we to get。

 in addition to maybe hard coding things， Another big difference is that。

Theres's the way humans write code。That， as I said before。

 may not be the best way to generate code for a modern CPU， meaning like there's ways of setup code。

 like using volcano model as example， that from engineering perspective， it's great。

 it's easy to debug， it's easy to write， it's composable。

 we can move these operators around and not worry about what's below it， but as I said。

 all that indirection， all that branching is bad for a superscalealar CPU。

 So instead we can design our code specialization components in our database system to om code that no human whatever rights willingly。

 but is' going to be best when can it into machine code for the CPU。Right。

So if you do really sit book developed like this。 and again we're doing the volcano model。

 we have a threeway join on tables A B and C。 and you see roughly the query pin like this。

 you're scanning the leaf nodes are scanning， you do some aggregation。

 you do some filtering and there's a final join at the top。 So again。

 just assuming that it's the volcano model， the implementations of these operators would look roughly like this you're iterating over over each input tuple from your child。

 you're adding some predicate and you're pushing things up。 And again。

 whether or not this was vectorized or two out a time for our purposes here， it doesn't matter。😊。

So again， but in this case here， think about how youd actually implement C plus plus code。

 you would have a pointer to some root node in the query plan。 And then at runtime。

 assuming it's in C plus plus， there'll be virtual function table， look up to say， oh。

 at the very top， I'm doing a join。 So they call the join operator And even that you could have different types of joins。

 you could have you could have an abstract class with a join。

 And then you have specializations per team them。 But still there's gonna be function pointer lookups at runtime to figure out what you actually want to do。

😊，And that's bad for again， for our modern CPU。Same thing when we want to run expressions， right。

 Similarly we have this wear clauses in here inside of the nested query。

 Well that will be represented by some abstract expression tree。

 We have the different operators and then the inputs are corresponding to the different elements that you're accessing in the query。

So the dumbest thing to do to actually run this would be again， traversing the tree。

 just walking down， evaluating every single node， looking up on whatever the context that's provided for the query。

 substituting the values， pushing things up and then going down the tree around like this， right？

So again， this is like would would be a naive implementation。 Some systems actually actually do this。

 But again。Pogre is a little bit smarter。 Other systems are a little bit smarter。

 But even even before doing compilation or code specialization。 But this is。

 this is roughly what you're doing at runtime。 the giant switch statements or function lookups to figure out what this is。

So， allright， well， this is is like， you know， it's， it's a 3，3，3 level tree。

 I that really big of the deal。 Always think of extremes and databases。

 if I have to do this for a billion tuples， as I'm scanning along table B。

 then this is gonna be super expensive to do this over and over again。Right。I mean。

 don't go to too much detail the Postcards as we'll see this in a second。

 they do Jit compilation now for the wear clauses prior to this。

 they were using a technique called direct threading thing of like it's an interpreter where you have this an array of pointers and they're calling to that but even again because they're doing it on a tube out of time that sucks if you're doing overlap lab。

And the Jit will help a little bit for that。All right， so the idea is that， again。

 we want to specialize code in our database system for anything that's going to be CPU intensive for anything that we know we going to be spending most of our time while we run a query。

 we want to or even other parts of the system， but for now we assume it's queries。

 we want to try to specialize that so that there's no indirect。

 no lookups to figure out what the type is， what the table is， anything like that。

 it's literally just hard coding as if a human wrote for exactly the query plan。

So you can do this for access methods like the scans， some systems will do this for store procedures。

 we's see if this in case of Oracle， they' they'll compile a PL SQL UDF into their version of C。

 like sort of it's called prostar C， something like CO here at CMU。

 like's it' restrictedive version of C， then they'll compile that to machine code。O execution。

 like the joins， the aggregations， all that you can compile。

Preddicate evaluation we just saw how to convert wear clauses or predicates inside your query convert this expression tree into actual program and then logging operations。

 I don't think anybody really does this， but the idea would be if I'm doing like recovery。

 could I compile the interpretation of log records for our class here this semester we don't care about this because we're not worry about recovery。

 but some systems can do that as well。So when we're actually going to do this for anything that's going to be focusing on queries。

 we're going to do code generation or code specialization when we have the physical plan。

 so a SQL query shows up， we go through the parser， go through the binder。

 go through the query optimizer， and then now we have a physical plan。

 then we convert that into specialized code。Right， because we want a reason about physical plans and not something more higher level or abstract for other things like store procedures。

 you you would do this compilation you know， when they call cr function or something， right。

So most systems are going to be doing this or some variation of pre evaluation， so we'll see Haiku。

 we'll see Hy， they're doing what we'll call holistic query compilation。

 so they're taking the entire query plan and then specializing that and compiling that。

Systems like Postgress， Spark， at least older versions of Spark and Ques EB a couple others。

 they'll be doing something like this because the idea is that you have an existing system that is doing interpretation for executing the query plan。

 but the where calls often is a most expensive thing。

 but then rather than rewriting the entire engine to be now do cogeneration。

 you just do cogeneration for for the wear clauses。

It's less of an engineering blast to make that change。I would say also， too。

 that theres we're not gonna have any security concerns in this for what we're talking about pretty much in the entire semester because I don't care about that stuff too much。

 Of course until they steal my credit card I care。 But it would be like I don't we're not worry about like someone doing code injection of like sending us a funky query that we then convert to C code that then can leak out SSH keys or something like that。

 we're assuming that somebody else has sanitize anything that we're given right we ignore all that。

 if you do care about those things， again， in the case of。In Heathton and Microsoft。

 SQLS serverver and Oracle， that's why they convert you to a restricted version of C to prevent you from doing stupid things。

 but again， we assume that the cogen code is written by us the database and developers of people building the systems and that we're not going to do malicious things in our own code。

So we can ignore all that。Alright， so some of this I've already said before。

 the way the benefits we're going to get is since we know all the attribute types a priori。

 we don't have to do anything again look up to figure out what the type actually is。 Like。

 we know at like this column at this offset， it's this type of this size。 And furthermore。

 if it's encoded and compresses certain way， we know exactly what the compression scheme is。

 There's no surprises in this。 because we know everything ahead of time。Likewise。

 we're going to know all the data types ahead of time and we can try to distill it down to the low level primitives like greater than less than equal to。

 which there hardware instructions for us to make that run really， really fast again。

 complex data types or user defined types sometimes could it more tricky， but we could ignore that。

And then we're going to try to avoid any function calls in loops as much as possible。 Now。

 we'll see in the case of vector wise and the system that do the pre capa primitives。

 they are going to have function calls and loops。But they're going to amortize that function called lookup cost or the jump cost because we' doing on batchs of tus。

If you have to do a first single tuple that would suck。

 but if it's a batch of8 tus or something like that， that's less of an issue。All right。

 so as I said before， there's basically two ways to do this and again at high level they basically look the same。

 it's just it's different ways to think about how to generate the code we want to then compile for our queries or preddicateates or whatever we're doing。

So translation is also sometimes called source to source compilation。

 and the idea is here that we have code in our database system that can generate other code。

And then we would just run a traditional compiler to， to generate the native code， which we or sorry。

 the machine code that we then link in and execute as if it was like， you know。

 shared object or is a shared object in in our system。 right， So oftentimes you'll see like。

 you know， have C plus code that generate C plus code， which you then compile。

Amazon Redshift is famous for this。And then the paper you guys read in for Hy。

 they're going to do basically have their own intermediate representation IR where they'll generate some lower level。

Low level implementation of the query， then they would compile that into native code。

 or in the case of hyperwe in aec， they actually can interpret it or generate assembly。

 they do crazy stuff that's in the later version that's umbrella。

 but they don't you know not taking typical Cli code。

 they're taking some lower level low level lower level representation。Again。

 and we'll see the trade offs between the two of these。

 So we'll go through translation first and then we'll talk about the hyper compilation next。

So sort of the first system in the modern era， when I'll say like the late 2000s。

 early 2010s that would do co civilizationization， a query compilation was this thing called Haiku and it was an academic system at a University of Edinburgh and so what they would do is for any query that shows up。

 they would have CL plus code in their system generate more CL plus code。

Then they would do a fork exec into GCC， which would then compile it into a shared object。

 and you would then link that into the database system process。

And the way it this will work is that you would have to have a。

 the program that you're generating for the query would have to implement a known function with a signature so that the data knows how to call into that。

To that shared object and run the code， right？That's look like a standard entry point。

 like think of the main function for N program without obviously calling it main。So the for this。

 they were just using an off the shelf compiler。 I think it was GCC。

 or they weren't trying to embed anything。 This is， This is a precursor two。To the LLVM。

So what's one big problem with this， yes？Compilation is slow， why？GccC slow， why。

It's translating to LLVMIR then。Now this is bi for LLVM。So it's doing a for gazette。

 so it's running the GCC as a separate process， what does GCC do when it starts？😡。

Goes read a bunch of config files and see what you know as if like you're running from the command line right it's not really meant to be run it wasn't designed to be run like in the critical path of any query or know in a database system。

 it's like a general purpose compiler。 So it does a bunch of stuff that a general purpose compiler would do like go look to see where my libraries are。

 Li those in parse config files and figure out what I'm allowed to do right。😊，And of course。

 it's a fork call。 So now you got to talk to the O， go spawn a new process and run that on the side。

 right' going GTC is going to allocate memory， do a bunch of stuff， right。So。

That's me one of the big problems with this approach。

 But we'll see why this actually is is from engineering perspective。

 going to be easier to maintain and debug going forward compared to the LLM stuff。

So the high level looks like this。 So say this is that some simple query。

 It's like pseudo Python code。 right So for this gettu operation。

 if youre doing an interpretive plan， you would first go look what table my accessing。

 go look what the catalog and figure out what the schema is。

 Now you wouldn't do this on an a approachable basis。

 You obviously would cache this before outside the for loop， but you have to do it at least once。😊。

Then you're going to say， okay， if I want to go get this tuple within a page or the block。

 what's the offset， I na the look at the table size， and I got to return a pointer to the tuple。

 And then now in this if clause to evaluate the predicate。

 I'm traversing that expression tree that I showed before， pulling the values up。

 checking to see whether things match and then deciding whether to terminate early or keep going or short circuit things and then return true or false and maybe you have to cast things in the right data type as you go along based based on what the attributes you're looking at。

So again， this is like an over complicated at a high level。

Highlow explanation of what the query is actually going to do and maybe again some of these things you can cash up at least in this part here。

 but again if you're doing this on a pertable basis。

 it's a bunch of waste of work to do the same thing over and over again。

So what Haiku would do is they'll generate sort of stubbed code like this where you set up some parameters that are given to you at when you evoke this。

 think of this as a function for the query， and then now within my for loop。

 now I'm not doing lookups to say what's the size of the tuple or where offsets are。

 all that's baked into the code， like literally hard coded values。

And same thing to do the evaluation， same thing the compileo can recognize that some number plus one。

 it can fold that in and evaluate that once and not repeat it over and over again，Yes specifically。

This question is like， yeah， this eval predicate is like we extracted that out and we say， oh。

 it's plus one， and we hard code that in the program。

I a case where the expression tree is not able to be？His question。

 is there error a case where the expression tree cannot be expressed in C S。 No， why wouldn't it。

Because like literally like， yeah， I can't think of anything。I mean， for in clauses。

 you can't generate exec that you may not be able to use like。Not standard library。

 but like like I think everything you could use least standard library like in clause as arrays or vectors。

 you got to maybe use a SDO library for that， but everything else， you can get it down to me。

 it's exact instructions。Or again， think of like going back whatever that query was。

I didn't have a query sorry。Like if the expression was where you know。

Where value equals input parameter plus1。That plus one。

 you don't want to interpret it over again since you have the input value。

 like you can bake that into the exact C plus plus code。 And then now the equal sign is just， again。

 the W you sign in C plus+。And think compile knows how to go to town on that and optimize that as much as possible。

So is this personal from？Yeah， the plus1 to transform me SQel。 Yeah。

 maybe I might have removed the SQL query by accident。

The  query is like basic select star from table where value equals input parameter plus1。

And then whether or not the your query optimizer does that。

evaluatevalates the plus one before it gives Port actually runs it。

 it depends on the appizer implementation。Yes。For systems that use expression。Compilation。

Do they optimizers just like？Not too expression fallinging。 And just leave it to the。Yeah。

 it's questions an integral question。For the systems that do predicate compilation。

 do they their query optimizers not do any of this folding stuff ahead of time and they just punt on the compiler do that all for you for systems that they've retrofitted like the compilation after the fact。

 like I think Postgsses does this like they'll do that because they didn't have the other thing before。

 But obviously， if you know you're always gonna compile stuff。

 then you can just take advantage of that。As well as additional optimizations that the traditional source code compiler will give you。

I think there are some。This is where you following the constantly。Okay。

So what's interesting about the Haiku approach is that it's us as the data system engineer developing the cogen piece。

We can do anything we want in that。Meaning like we can invoke any other part of the system inside of our generated code。

Because that means like we could call out to the， the network code to send messages if we wanted to。

 We could， We could go get， you know， data in and out of the B pool manager if we wanted to run transactions。

 right， So we can be pretty much do anything we want because it's just， it's as if the。

 the code was re generating was shipped with the database system when。

 when it was being built by the engineers。Right and that means that we don't have to have any specialized bridges to call out to other parts of the system。

 We just invoke it as if it was， a function built in。

And you see this a lot in- it's not exactly code specialization。

 but you see this in a lot of the extensions for Postgres because they're just linking in shared objects for better or worse。

 they call all the parts of the database system。Because you can， because it's just C code。

Because you have to manage memory， that's a whole other issue。So the one key advantage， though。

 even though the compilation is going to be slower。

 a key advantage of of the translation approach is that debugging is going to be。Relatively easier。

 easier relative to the Jit complation from hyper。Because what are you generating C+ plus plus code。

 What if it crashes， What do you have， C+ plus plus code， you can walk through in a debugger。

 you have a nice stackax traces， you have nice symbols。

 you can figure out what what broke Now you got to do a little extra work to maybe annotate the generated C+ plus loss code or C code。

 whatever you're generating to reference back what part of the main system generated that code because again I don't want to debug the thing I just codeend。

 I want to debug the system that generated the code but you can put annotations in there to figure out where this thing came from So now you just take any off the shelf C+ plus program or whoever it is。

 and they know how to use DDb in theory， and they know how to can then debug your program。

 you don't really to specialized people have to understand LLDM or assembly to make all this work。

Right。And that'll be one of the things we see in Redshift。

 and when we read the photon paper later on from Databricks。

 they talk about the debugging of a LLM G comp compiled system is the engineering burden is very。

 very high and so they decide to avoid it。Alright， so I'm going show some results on the Haiku paper and they're going to compare it against for their implementations。

 So the first will be like a generic volcano style database system that is know using generic predicates or expression trees and evaluating them。

 So this is like the Viin  zero of any database system somebody builds like think of like bust。

Then they'll have type specific iterators using I think CL templates to inline as much as possible。

 then they'll have a hard code implementation sort of first pass written by a grad student。

 then you have an optimized version written by another grad student。

 and then you have the HaIQU code， the ones thats generating the CLS code。😊，Right。So。In this here。

 the measurement， they actually measured L1 cache misses， but it's so small。

 we're going to ignore that。 And it's， as you expected it， right， the generic implementation。

 the textbook implementation database system is gonna to be the slowest。

 But as you go along as you start adding more optimizations， things are getting better and better。😊。

So the thing that we really care about is this part over here。

 where the grad student was able to generate optimized invitation of again。

 handwriting the query plans， what this is TPCEH， I think， or this joint query up here。

And the number， the difference is quite small， but the haiku system is actually。

 is able to generate C plus plus code that's better than the， the hand generated code。Right。Again。

 and this is because the， you know， you think about it。 you only need to build the。

 the Co and piece once and you can put all the tricks。

 you know how to make the queries run fast within that one implementation， whereas。

If you're literally hard coding the queries， you' got to optimize every single one individually。

Right。So the optimized ones are just be fast because there's fewer branch misses。

s there's allocating less memory。 there's fewer memory jumps for functions because everything is almost like in line。

 yes。It's what。So how do you know when L2 cache occurs？Oh， how do you collect this data？😡，Oh。

 I didn't teach you guys about performance counters。 Basically， the CPU can track all this for you。

 CPU， every CPU has what call performance counters。 So they're in the inside。

 the CPU is maintaining all this information about your programs。

 And you use a tool like Intel has V tune the source implementation called Perf。 It's almost like。😊。

like if you ever use like Valgrime， but like Valgriimes instrumenting the code as it runs。

 this is like you don't do any instrumentation of the code。 The C just counts it all for you。

 And then you can turn on Perf。 There's a very little performance overhead and then dumps out like a perf file that you can then look through and see where the the cache misses were and so forth。

Yet， actually who here is familiar with Perf？All right， about half right。

 so maybe we can cover that in a week or two， just crash course on how to do performance debugging。

Yeah， CP is are great， CPU can measure all this stuff for you。H。And again。

 we can measure down at one。 But catchist is but we knowing that because it。

 it it would be way too small。Al right， so again， this paper is 13 years old， right， 14 years now。

 I think 2008， Yeah， 14 years old。 So this is running on a really old CPU that's obviously been。

 been exceeded by everything else。 a core2 duo。 But that that part I don what's that。😊，Sorry， no。

 it's， to the exact numbers I don't care about。 is's the relative performance difference that matters。

 right， And even if we had a moderate CPU， I would expect that it would still look look the same way。

は。So again， as we said， what's the problem with this approach， it's the compilation cost。 All right。

 so how much time does that take？So in here they're comparing the highQ generated source code。

 the compilation costs for either running with O1 or O2。 and as I said。

 we don't ship database system software with O3 compilation because it might put things it might put things out of order and actually and running slower then it would just02 So O2 is what you want to ship source code with obviously when you use01 if if you're trying to debug something you run with01 but obviously O1 is gonna to be less aggressive on the optimizations So that's why the compilation costs is lower。

Right， again， old hardware back in the day。 But it just goes to show that like。I mean first of all。

 you see almost a 3 x difference in compilation cost between00 and 02。

 but again now we're talking in case for this query here， 600 milliseconds to compile it。

And for scale factor one， you can probably run this query in 10 milliseconds。20 milliseconds。Am。

So this is a big problem。if your query is only going to run for a fraction of the compilation cost。

 you might as been better off just not running the compilation step at all just run the old interpreter version。

Now， if your queryries are going to run for like five hours and it takes 600 billex compile compile。

 Yeah， who cares。 But again， the disk has gotten faster。 The network's gotten faster， CPUs。

Not as much， but like the。You know， with a well instrument well built execution engine， you know。

 you'll be able to get through some queries can finish in less than 10 milliseconds。

So your compilation cost is going to be a big problem。

Now the hyper paper you guys read doesn't solve it， they solved it afterwards。

 we'll cover that in a second， but in that case， again， because this is the for GCC，😡。

It's a much more expensive compilation process， yes。

What do they do after requires exposure do they throw up with a compile？his question。

What does Haiku do， what do people do Yeah， so his question is what do people do with compileald code。

 do they just throw it away and discard it or can they cash it？We'll see Redshiftiff in a second。

 they cache it， and they cache everything。And Haiku， it means an academic test I don't know。

 But you can obviously imagine it like。Because if I I can parameterize it potentially to just put it into like。

 you know a function make it a function where I pass in the maybe input value。

And I don't get maybe the constant folding that I would want。

 but at least now the compilation cost would be lessened。

 And then you essentially end up what vector Y is because that' what that's what they're doing。

 But they're precompiling everything when you ship the database system， not at runtime for queries。

But you， caching with help if it's a prepared statement。

 you can cache it because you you're gonna to see it over again， right。his question is。

 is that what Redshift Aqua is， Aqua is a harbor accelerator which we won't cover that。

Even before you get to Aqua。They cash things， yes。Okay。So as I said， again。

 the relational operators are a great way to reason about queries。

And we have these composable query plans， we can move operators down anywhere we want and not worry about what's feeding into what because they're just sending tus。

 but that's going to be problematic when we comes to time to execute it。

 if we do it a littleer translation of the relational algebra query plan into C laws or whatever we want to compile into。

 that may not always be the most efficient way to do this。And I said。

 there was a long copilation cost in C S， and in the case of Haiku。

 they were not supporting full pipe mining， they were still processing one tube at a time from one operator to the next。

And。because it's from 2008 and the vectorization stuff and the other stuff weve talked about so far。

 that came much later。Alright， so the hyper paper you guys read is not an easy paper to read。

 so hopefully no one spent too much time in the appendix on that hell of the IR stuff。

 I think I think it' said not to read it right。So what he's going to do in hyper is that， again。

 rather than generating C plus plus code， they're going to generate L ofium IR directly。

And then they would then go ahead and compile that into to machine code。

 So you end up again with the same you would end up to the same machine code in theory as the haiku approach。

 But you're not going to C loss and then converting that to a machine code。 or Of course。

 the GC is going put that in its own IR。 You're just going directly to the IR a bunch of C+ macros that then compose a query plan hand it off to LLVM。

 and then LLVM can go ahead and compile it。Now the challenges this paper also too is because。

And he's a genius， he's introducing two key concepts。

 he's introducing this code compilation stuff with LLVM。

 but he's also introducing the pushbase execution and that makes it seem like you can't have one without the other。

 it's not true， but he's showing you how to can design these using operating infusion。

 design these query plans be very efficient， try to ride tuples up in CPU registers for as long as possible and the pushb approach is how you do that。

So let's just look at a really simple example， so this is the  query we showed before。😊。

So we know how to divide up the query plan into pipelines。

 right there's a pipeline breaker that says that we can't start executing another pipeline until all the the tus are processed by the the child pipeline below it。

 Now we'll cover next class。 How do we take these pipelines and divide them up to task。

 We run them in different coreds and different nodes and schedule them that's next week。 For now。

 we'll just assume that the very simple dependency graph to know we've got to run run one and two can run the parallel。

 But3 can't run until two finishes and four can't run until one and three finish。

So what hybrid is going to do is that they're going to generate these。

Essentially much a nest of for loops。 right， It's the push base model。 So。

 so these nest of for loops are gonna be able to within when one pipeline do as much work you can for a single tuupple and then only go back to the next iteration of the for loop once you've done everything you can with that tuple。

Right， so you can think of the boundaries here are these pipelines like this， right， And at the end。

 you have this long pipeline for where you're just entering over to C， probe it into the hash table。

 probe into the second hash table， and then admit it when it's done。

And so in this case here for any two of that's going to match on the join clauses for the other two tables。

I'm gonna do all that processing up the pipeline before I go back。

 and I can keep they gonna be very careful keeping all the this data in like theP registers themselves rather than saying。

 hey， here's here it's in memory。 I hope it makes it。

 They actually be very careful try to put it in the registers and not put anything else in there until they have to go back and get another tool。

And again， these are just showing the dependencies between them。

So when you compare he's gonna compare against the initial version of hyper that he wrote the dude cogeneration that was like the highiku approach with C plus loss。

 And then he had his LLM based approach he's also going to compare against vectorwise。

 Mo A DB and hyper Again， this is what 2011，2010。 So these were sort of state of the art O lab systems at the time。

 Ca of Oracle showing like here's what happens if you have a volcano based system。

 it's not a column story It's like the worst case scenario。

 And I think he calls it DB database X in the paper right that's because Oracle has in their contract or license agreement that said you can't name them by name and what that I didn't know was。

It's oracle， yeah。嗯。So， but， the paper is 10 years old。 So who cares， right， Maybe they care。

 I don't know。 Why is it better than。His question is why is Oracle better than Q4？Yeah。

 that one I don't know。Yeah， I know。啊。I I mean it could be the query query optimizer。

 So this Moating at this point was maybe 10 years old。 Oracle was。30。35 years old。They've had。

 you know millions of dollars poured in the query appr whereas Mo DB was a small academic team。

 So it maybe the case MonDB is picking a bad query plan， but I don't know。 Well。

 I'll see bad query plans later on。So right in the case is here for Q2。

 I think vector wise vector Y crash and they didn't get a result。 So so again。

 I don't care about so much the difference between oracle and everything else。

 the thing we sort of care about is like the hybrid LM based version and everyone else And the case actually for Mo be。

 It's using it has an interpreter that's going to use op code that's gonna to look like like SQL light we'll see in a second。

 So it isn't just you know isn't doing function it isn't traversing the trees the query plan trees this the way we said before。

' a little bit better than that。 but it's still not again。

 it's still not know the exact program for for the query plan。😊。

So the reason why the hyper1 is gonna be better than say the++ version of hyper is that they're going to be more aggressive pipelining to try to ride tus up in CPU registers because they have low level control of what goes in those registers because they're generating the IR。

 whereas in C+ plus， you're hoping the compiler can figure that out for you and it doesn't always do that whereas in the LLVM stuff。

 you can have exact exact control。In the case of Q1， it's just a wear clause an in aggregate。

 There's no joins。 And the， the where clause is simple enough， but it's again， the。

Widing things up that single pipeline as far as possible is why they're going to get a better performance here。

Right。So， again。Compared to other systems， you know， this is pretty significant。 Again。

 this is measured in milliseconds。 It's it' over 10 years over at this point。

 scale factor 1 is only one gig， So it' not that big。

 But you can kind of see how like we're getting to almost the bone。

 the bare bones of like how much better you can actually get in these systems。 Yes。

 the days we gonna get bigger。 But like if you have the process more data。You know， there's not。

 you know， there there isn't O 100。 that's going to make the number instructions that get the actually go away。

 So code specialization is gonna get us almost with the like bare metal speeds。

So these results are pretty good。So imagine now the compilation cost， this is not in。

 I this wasn't in the paper you guys read。 And this is not like a true scientific evaluation of these two approaches because I'm taking the numbers from the。

 the， the the Haiku paper and the numbers from the， the hyper paper， which came from。

Rning on different hardware at the time。 But again you can kind of see roughly the performance difference between the two systems right So again。

 Hiikku is doing translations。 So it's generating C code， evoking Gcc taking the shared object。

 linking that in and running it whereas in the LLVM hyper into the LLVM it's all in the same address space。

 a separate thread runs the compilation stop and you can initialize LLVM when the system starts up and you don't have to reitialize reinitialize it over and over again you see the compilation times are getting down into under 20 milliseconds。

 which is。Not great， but it's acceptable， yes。Performance comparison when you。

Let's say you just completely removed the whole convolation。はい、あでき。Between Haiku and Hy。

YeahI hyper still faster？That's this， so hypersthus is an approximation of Haiku。啊。

It's actually better than haiku because I still think this is。A。I mean， it's still too at a time。

 but I think he's still doing the push base model on this， I think。Right。In a case of vector Y。

 they're doingd primitives。But it is， it is actually doing vectorized execution。

 Now I don't know whether they're doing SD on this。 again， 2011， 2012。

 maybe be A V X2 or something like that， but。There's other factors as well。It's I say before。

 it's not always me a true Apple App comparison。The way hyper does fixed point decimals for Q1 is really efficient versus like。

 I think vectorized at the time was doing something similar to like Postgres。Right， in case of hyper。

 it's literally a120 bit number that is ripped through instructions through that。

 We't have to do any lookups or do casting of， know。

 v charts to figure out what the dec one point is。 So like。You know。

 this difference between this isn't title just because it's doing compilation。

 But I would say for these， it's the same data types。

 So it's a good good difference of the two approaches。O。So as I said， multiple times today。

 the big problem is going to be the compilation time。

 if you can do it ahead of time before the query runs fantastic， but know oftentimes in OLAP system。

 you've never seen the query before。 I think maybe that exact query So you go get to ahead and compile it in the case the hyper。

 they observe that the compilation time of a query is going to grow super linearly relative to the complexity of the query。

 So not so much how much data you're accessing It's like what is in the actual query like the number joins the aggregations。

 the prediates， the warehouse and so forth， right。😊，So for LTP。

 not that big of a deal because most applications be running with the exact same queries over and over again。

 maybe just parameterize， and the data systems can automatically convert them into prepared statements so we can compile it once and reuse it。

All that query is， as I said， if we've never seen the query before， then this is going me a problem。

And so the。I， don't think it's in the paper but。One of the examples that they told me was after Hyper got acquired by Tableau。

 they had to make it post as compatible because it was shipped in the Tableau product as like a query accelerator and。

What would happen is people would would you install hyper。

 And the very first thing they would do is hook up PG admin to it。

 which is like a a graphical interface， a web interface to Postgres databases。

 You can see all your tables， you can write queries and so forth。

 right And so when you turn on PG admin， the very first thing it does to figure out what tables you have is does queries against the catalog to figure out how these tables of this type and so forth。

 right And so just regular PG admin pointing it to regular Postgre database。😊，You know。

 queries would start instantaneously， but in case of hyper because it had to do all its compilation stuff。

 it would be like a 2 second pause for these again twos queries that aren't grabbing a lot of data。

 but it had a bunch of complex joins against the process catalog and the system again the administrative interface would pause or 20 seconds。

Right， so it looked like everything was unresponsive。20 seconds does seem like a lot。

 does not seem like a lot。 But again， if you're used to having instantaneous access to your postco database to P G admin。

 something's wrong。So then they came out with another approach of follow up to the paper you guys read in 2018 using a technique called adaptive execution。

And the idea here is that they're still going to do the same thing in the paper you guys read where they generate the L ofM IR。

 but then instead of not running the query until you finish the copilation step。

They're going to have this interpreter that they wrote， start interpreting the L of M IR。

 start running the query right away。😡，Then in the background。

 then they're going to run the LVM compiler that compile that IR into machine code。

And then if the compilation finishes before the query finishes。

 then they just slide in the shared object and replace the interpreter and queries then run super fast after that。

Right。And we'll see the paper you guys read next class the morsels paper。

 There's this natural boundary between the query task or the plan task where you process some chunk of data the worker thread process some chunk of data and then when it's done。

 it says， oh， is the next thing we're gonna to do for the same query and when it does retrieves that task I can go look up to see is the compiled version of that task ready for me And if it is and it just slides in。

 So it's not like you're interpreting and then you cut off middle bit of a for loop。

 Sos again when I'm done running my batch， I go get the next thing and I may be pulling a compiled version of that task rather than the interpreter version。

Right， so all this is done done seamlessly。So the over diagram here is going to show numbers that they reported in their paper。

 so they can sort of walk through how this all works。So the SQL query shows up。

 you run it through the query optimizer， for them that takes roughly 0。2 milliseconds。

Hyper also has one of the state of York query optimizes。 we'll cover that later。

 but that's a pretty good optimization time。Then they'll take the physical query plan。

 they'll run it through the co generator that's going to generate the LLM IR。

 and that takes roughly 0。7 milliseconds， right So this is pretty trivial to do this。

 you're measuring microseconds。All right， so now at this point， there'll be three different branches。

 and these can run in parallel。So the first thing is that you take this L I generated here。

 and then you're gonna run your own bytecode compiler that can then generate some some convert the IR to your own bytecode。

 And then they have an interpreter that they wrote that that that compiles， right？

 I think they told me they。All of this they wrote themselves， there were open source。

 I of them IR interpreters， but Thomas didn't like any of them， so he wrote his own in two weeks。

We imported our own German here。Well。Hes a busy master。 We got our own German。

 and it took him about a semester right the same thing， right， So it's not impossible。 can be done。

 And you， you don't actually have to implement your own all your。

 You don't think that all the L and IR right， You just need know。

 whatever this thing is gonna gonna generate and you control the whole stack。 you can do this。

AlSo then in the background， they're can also take this L IR。

 and they'll just run the L compiler take like running this01 or sorry00。

 And that's gonna generate some x 86 code。 And when that's available， we can slide that in。

 So the bikecode compile up there takes 0。4 milliseconds。 say this one takes 6 milliseconds。

 So the query start running 6 milliseconds。 you can slide that in。😊。

And then if this thing is really taking much longer。

 then you can kick off the more expensive compilation steps like running02。

 and that takes 25 milliseconds。 and then you do dis optimizations。

 run the optimized version of the compiler， and then you have more exccutable code there。Right。So。

 yes， isn't by code No think of like J J and bycode some。Some you know， it could just be L an IR。

 And our system we did L directly L an IR for what I， I think they wrote their own。Right。A。But I。

 but again， I I don't think it's like， it's， it's not doing like the heavyweight compilation。

 like hoisting stuff like that， like G C client to do， right。Am。So， the。

There's a couple benefits of this， obviously the speed， right。If my query is really simple。

 then this link might be enough， and this is basically what SQL light does。😡。

They have their own VM that interprets these op codes。But if the query didnt run longer， then。

 if I have to wait 6 milliseconds to get an machine code for this，s again， that's。

 that's a true amount of time。Am。The know the benefit， though， is that you're。

You now can actually debug failed programs more easily because you have this thing at the top。

 You have this interpreter for for your bycodes。 So if if you under the Kaab version and it crashes。

 you can then reverse that and figure out， okay what lines of the code generated that that there's op codes or whatever that fail the machine code that failed for me。

 and then I can step through with a regular debugger at the top and walk through and figure out。

 okay， here's what line of code am I tripping up on。Yes you using the。

Quite pretty short that's going to be better。Correct what statement it is。

 am I saying that if your query is short？Is the Bcode compiler going to be better than doing anything down here？

Or like not doing any fancy stuff and just。I mean， it's not simple plus。s do codes。

 It's like the GNM app codes。 but we are doing shit here。Yeah， like this is the jet step。

Like if the  query's running shot， don't generate an e recorded on。What kind of code？

Machine code or S+ code， what are you saying？The aircraft run bus。 they don't do any of this。

How does bike？To just like not doing any poor generation at all。

Oh his question is how does if I did this， don't do any cogen？Sorry say if I。

 if I just have like a bus tub interpreted cell system， I don't do that versus having this step。

 Is this step always gonna be better。 Well， I mean， for like maybe really， really。

 really simple queries， select one。Maybe。😊，But like when things are running more complex things then I want this。

 absolutely。But like you think of like。This will handle the short things without going through this expensive step。

But then when the bigger queries， more complex things show up， bus up is going to choke。

 this thing's going to rip through it。So it can handle both。

You're saying you can switch from fight to bike code。逆成にせ。

His question is can I switch it from the bikecode Xcur on the fly， yes？

Think of like I take a query plan。 I break it up。It's a pipelines。

 and I'll have different instances of those pipelines running like a task instance or and each one' is gonna to process 1000 tus。

 So I'm running， my thread's running this bytecode version of it。 I process 10 twos。 When I'm done。

 I go check to say， hey， is the Kab version ready for me If it is。

 Then I just slide that in and process the next thousands。😊，And the logics is exactly the same。

 so it's not like there's going to be like any difference in the data that's generated or results generated from the Btecode version versus the capodd version。

 it's all the same。Yes。Complex。would be， and then choose some of the branches。Yeah， her question is。

Can we can the optimizer be smart enough here and recognize， oh， well this query is select1。

 I know I don't need to read any data or do anything expensive， so to skip all this， yes。

But when you do start doing joins and we'll see this in a few weeks。

The optimize is going to be way off。So， like。A simple threshold might be。Like do this。

 we always have to do this， and then maybe always do the background。

 but then maybe some trigger says， okay after 20 milliseconds， that's enough let we run this too。

 right。Yes， so can I say that on the average case， it's like building on his point and I say on the average case it might be worse。

 but on the worst cases it will be really good His statement is。

 can I say that on the average case it might be worse， but on the worst cases itll be be better yes。

But where that， where that cut off between like on the。In that best case。

 is the interpreted system do better than compilation？It depends on the hardware。

 it depends on what you're doing， right？H。Yes。like。For what sort of。张为我。

like the difference in milliseconds actually matter。His question is。

 for what kind of companies would milliseconds matter No one for one。

Let's say the difference is 20 millisecond。Yeah， so the question is like， why do people care？So。

 all right。On the extreme case or the high frequency trading guys。 right。

 those guys like their snort cocaine， the run around fiber on the river。 like those guys。

 they want to be， they want to measure queries in microseconds。 But is this an like this could be。

 you could use this for both， right， But like so so the high trading guys care a lot， Right， for。

 for us mortals。😊，The conventional wisdom is 50 milliseconds。

And that's usually for like a transaction。 And that number comes from Internet advertising auctions。

 So like when you go visit a web page and you're not using a blocker。

 you know the hosting company sends or whoever is running the ad， say it's Google。

 They send a request out to the different advertising brokers。

 the auction houses to say here's this user visiting this web page and here's everything they know about you。

 they bundled that into the request。 And I think you then the contract is。

 you have to respond in 50 milliseconds what your bid is for turning the ad。

 it might have gone down to like 4030 milliseconds。 but that's roughly what it is。

 So the response time you have to get back is 50 milliseconds。 So so now， assuming around trip time。

 So maybe some listen that。 So you got to run a query to go look up and see whether I want to sell an addd to this person。

Within that time。There's another number， too， I think from Amazon says for every 100 milliseconds that the Amazon product page is slower。

 they lose like a million dollars。 like it's some， I mean， I don't know if that's apocryphal。

 but it'ss some correlation between like slower pages equals less sales。Yes。

Just to add to this you think that this query will be a small part of a big system right so like if this has more latency then other people get less time to play with so everyone has to optimize。

Yes， I've never been anybody says， yeah， my my queer run slower。 Yeah， great。 right Now。

 if and certainly there， there's a， there's a cost element， too， right， you can pay， you know。

 millions of millions of dollars to get that micro set， you know。

 sub microcond or sub millisecond latency。😊，Those you don't need that where the right trade off depends。

 but like。哎。Like嗯嗯。Everybody would benefit from this， I think。Okay。So in terms of the performance。

 you can get from these different queries again。 So you have the， the three different phases。

 the byte code version， the unopimized LVBM and the optimized LVM。 And again。

 you can see how the this is log scale。 But you know， there's a pretty big jump between the。😊。

The bikecode version and the sort of simple LLV and pass one and then depending on the complexity of the query。

 the gap between00 and 02 between the diversion will be slightly different， right？Again。

 scale factor one， this one， all the queries are running a single thread for the queries。

 so you can use the other threads to compile do the compilation of stuff，Again。

 but it's not just about performance， it's also the debugability and the maintenance of the system。

All right， so I want to do a quick。Sort of quick run through although a bunch of different systems that are doing again different variations of of co compilation or query cogen or query compilation。

 And I set up broken up loose to four categories。 This is not scientific definitions。

 It just what I think an easy way to categorize and understand things。

 So the translation would be source of source stuff。 We talk to begin with highQ。

 The custom one will be although actually hyper should be over here。 on the other side。

 But these will be different systems are doing different things。 Sometimes they're using LO VM。

 Sometimes they're not。😊，Or the CLR， if it's on Microsoft stuff。

 then there's a bunch of Java databases that are doing just in time calculationlation for JVM。

 and then here's all the ones that are using LLVM。And than the skull and bones mean these systems are dead。

 so we've killed two at CMU。Not proud of it but happened。All right。

 so the very first system that did code specialization was one of the first relational database systems。

 and as oftentimes in databases。😊，IBM data first， So the very first relational data well。

The the first major relational data system they were building。 There was。

 there was a precursor the system R out of the UK called。Peter Peterer Lee relational test vehicle。

 which sounds like a tro rock band。 but that was like a prototype And and the money view that built that one then went to go built system R。

 But system R was the first real one。 So back in the 70s。

 they had an early implementation of cospecization or cogeneration for for running queries。 Again。

 think of like 1970s， the hardware was terrible。 the CPUs were slow disk was slow。

 everything was terrible。 So if you had to then interpret the query plan on this really slow single threaded CPU。

 that would just it would take forever。 So what they would do is they would have after the query came out of the optimizer。

 they would then cogen IBM system 370 assembly。And have then thes put that together and run that as as for the query plan。

Right， and's sort of putting out a bunch of code templates to， you know。

 do scans and do joins and so forth。 Yes， What I， this is the 70s。 I I have no idea right。

 must have been as well。So at the it must have been high then。Yes， except like well。

 the function calls were always expensive because the CPU sucked。

 most of the engineering reason was why they abandoned this。So they built this in system R。 again。

 the way they did my system are was it was a groundbreaking project。

 Ingress was being built at Berkeley the same time。 Oracle came a little bit later in the 70s。

 But in system R， they got a bunch of like8 people that all this brand new PhDs and like mathematics and C S。

 they took Ted Co's paper and then tried to actually build it。 So they had one person， you know。

 one woman built the query optimizer， The first like cost based query optimizer。

 two other people went off and built design SQL。 and like one dude built nothing but this cogeneration step。

 right。😊，And so when when the system R project ended。

 they did take some bits and pieces out of the codebase and put it into the two commercial relational data systems that IBM was building。

 SQL Ds and DB2 but they didn't carry over and this code gen stuff and there's this retrospective paper from I think came out of 81 So at that point system R was8 or nine years old and they talk about how they decided to then do this cogeneration stuff in the early version of system R。

 but the problem was every time since it was like a brand new system。

 everything was always in flux any time like an API change in one part of the system。

 then you that would break the cogeneration step and you had to go then rewrite all of that So it came too much of engineering overhead to change this thing over and over again plus then you have to have to deal with like engineers when the query plan failed because of some bug in the cogeneration code。

 you had no easy way to link that back to what was this is all assembly what was the。

Asmbly code that generated that。So again， when they built when IBM went off， built the new systems。

 they threw that away。 Yes， why did that not deter the Germans。The statement is。

 why did that not deter the Germans because they wrote their in abugger。 get better in a second。Yes。

So。What inspired them to one？standing from the paper was that most of the advantages of this come with OLAP series where the disc overhead is less important and more so the bottleneck is。

So what possessed them， I guess， to say， okay， we really need query compilation now in the '70s。Well。

 first of all， like there were no other relation systems built at the time。 It's not like， you know。

 there was any， you could look at this way well just follow them。 they were literally inventing this。

 right， And again， you're all used to like cell phones and like everything being super fast。

 This was terrible in the 70s， right， Like your cell phone is is like know hundreds times more powerful than what they had back in the day。

 So everythings super， super slow。 If you then have to do literally like look up， say okay， you know。

 interpret the query plan， look at the types and switching and something。The queries run forever。

So they're kind trying to make do with the hardware that they had at the time。

So I think it's a perfectly plausible approach why they did this。It's just， again。

 it's hard to maintain。All right。Vectual wise we， we keep mentioning this over again。

 But I want to bring this up。 So again， what they're gonna do is they're not gonna compile queries or pre on the fly。

 Sorry， they're not gonna be could on the fly。 Instead。

 they're gonna pre generaterate all possible combinations of anything you would want to do on data and query plans for any possible data type ahead of time。

 So think of like hundreds of individual。It function to do things like。

For a vector of integer in 32 integers， you know， here's the less N version。

 here's the grade n version， here is the greater than equalversion。

 They're going to pre generaterate， I think， you， using a bunch of scripts， all these functions。

And then they compile all of that and then we ship the binary and then your data system binary just has them all in there。

and then at runtime， your query shows up， you look at the query plan， you know， okay， well。

 it's in 32 column running against a less than some constant。

 here's the precoal primitive that I want to use for that。😊。

And then you just basically make now an array of function pointers to generate the pipelines for the queries。

 and as I said before， jumps to functions are bad for modern CPUs。

 but if you're passing on these batches or vectors of tuples。

 then that function jump cost is amortized， right？So basically it like that。

 So say you have some query like this， and then you have a simple filter。

 you have a string column equals aBC and it comm equals4。

 So then you would literally have a some kind of pseudocode thing like this that is in your source code that you then compile and you would have one for the string one for the integer and then at run time sorry at runtime you're literally calling these one after another and passing the vectors along and then you can maintain the offset vectors of like here's here's the tuples that actually match now you wouldn't allocate the memory inside the function like I'm doing here but you would pass this along and keep track of like what tuple is actually matched and then you all the Cdy stuff we talked about before deciding whether you want to keep processing refilling or make changes。

😊，They， I don't think they shifted in the commercial version， but there's a paper。 It。

 am I studyinging it and see。Yeah， this micro paper。 They have a paper where they。

They would take all their primitives and run all different possible compilers on them， ICC。

 GCC Kang with a bunch of different parameters on them。And then at run time。

 they would run basically like an optimization program to figure out like。

Which one is gonna perform the best for， you know， for some， you know。

 for the CPU that they're running on so they could switch out what implementation or what machine code implementation or comp compiled version of the primitive at runtime。

 But again， I don't think that ever went into the commercial version。

Alright so redshift is going to do the Haiku approach of a query compilation。

 I think actually the Amazon then hired the Haiku guy from Edinburgh。

 I think it was there for a while。 So what they're going to do。

 they're gonna tovert query plan fragments into template C+ S code and they push base execution with vectorization And then since the compilation cost of like4kme Gcc is so expensive。

 they're going to cache everything。😊，And not only are going to cache for whatever your database is for all your queries。

 they're going to maintain this giant global cache for any queer that anyone's ever ran on any database running on Redshift。

So this， this is amazing because this is a completely different way to think about how to do query optimization or cogeneration。

 right In the case of hyper and posts and all the other systems。

 like they're starting cold every single time。 know like you turn the system on start putting data in it and start running queries。

 It has to， know warm up its own local cache， just figure out how to cogen that and compile it and so forth。

😊，So Amazon basically says， well。Instead of I was co Jenning all these primitives ahead of time。

 let's just take queries as they show up。Generate the s code for them。Cash that。

 then as new queries show up， we see whether we have an existing compile version of that plan fragment for that query。

 and then we just use that。So think the paper， they say the hit rate for the global cache from every single spreadshift database in all Amazon is like 99。

95%。 So no matter what query shows up，99。95% of the fragments are going to be in the global cache for your local cache。

 the hit rate like 85%。 but then you can go fetch things from the global cache。Right， and again。

 in the cloud， you know， in the cloud is a different way of thinking about how to optimize things because you。

 you can see everything and you can， you can share information across different customers。 Now。

 when you think about it， the， the single code they're generating doesn't have any proprietary information where you could leak things from one customer from the next。

 right， again， going back to the prim stuff and vector wise。It's， you know。

 you have in a column integers。 You want to do less than on some constant。

 It doesn't matter whether it's your database。 has like banking information or my database that has。

I don't know。 a blog application at the end of the day。

 it's just ripping over integer or inger columns with constants。

 So there's no issues reusing those caches， those cache compile query plans。Right。

They do it the extra work like every time the version of the system changes similar to the problem that that system are had where they have to maintain compatibility。

 but in the cases where it breaks its compatibility。

 they just have a background service that just prewar the cache because they have all the C code they generated it before。

 and then when a new version comes out， see whether it breaks and if not。

 they recompile it to the new version to just fix it automatically。Right， guess。

Wching from the global trash as possible。His question is fetching it from the global cache faster than compiling yourself？

Yeah， it's a never call。It's way faster than running user GC。Right。And again。

 you get the same benefit， like now when things crash。

 you have the monthly false code and you can debug that。All right， so Oracle as far as they know。

 does not do any query compilation or prediiccate compilation。

 I bring them up because they do something interesting， as I said。

 where they'll take store procedures that are written in PL SQL。

 which is like PLPG SQL It's like it looks like Ada it's it's the SQL standard of how you write UDS will'll cover UDS later in the semester but they take those PLSQL UDS or store procedures and they transpole them into pro star C。

 which is their internal version of C。 and then they go ahead and compile that native code and because the C dialect is restricted you're not worried about them like jumping to some arbitrary locations and memory and trashing the database system。

 you can run this as a shared directly。We're not really talking about new hardware。

 but back in the day in the previous decade after Oracle bought Sun microcrosystems。

 some was shipping the Sp CPUs， which I don't think exists anymore。

 but they started putting like database operations inside the silicon itself。

 like for compression and insecurity and other this stuff like that。

 So like this is the better than codegen right， This is literally there's an instruction that does exactly what your data system does。

嗯。But it was only for oracle stuff， but again， they don't sell that anymore。

So Heathton is not an OAP system， it's a transactional engine， but this is what they were doing。

 they were compiling both store procedures and SQL， and they would compile it using。

 I think into C code， which they would then link into with the CLR。

 which is Microsoft's version of the JVM and as I said before，In this case here。

 they do have a bunch of checks to make sure that somebody doesn't try to do like buffer overflow of stuff in in in the C codes generated。

 I don't know if of other systems actually do this or not。 But what was cool about that also too is。

 as I said the。Since everything is just linked as a shared object。

 you can have the generated code invoke other parts of the system。

 So in the case of where where you can think a hekaton is like like a storage engine for SQL server。

 So the same way like MysqL， you can put in rock DB， you can put an N DB。

 Hekaton was like something you could put into SQL server。

 So then the generated code and then talk to other parts of SQL server that maybe weren't running a hekaton。

😊，And again， you can do this because everything's linked together。All right。

 so SQL Bte is the most widely deployed database system in the world。

 and most of you don't know this， but they're doing some variation of cogeneration。😊。

So they're going to convert your query plan into these opt codes for this virtual machine that they design or the one guy designed。

 and then at runtime， again， they're just going to literally interpret that the VM is going to interpret those byte opt codes as if it was like the JVM。

Right。If you ever use SQL lightte， if you runex， you don't get you don't get a query plan tree like you would normally in any other data system。

 you get this list of optical and instructions with nice little commentsas to tell you what it's actually doing。

If you you want to get the actual query plan tree itself。

 you have to get to call explain plan and then the SQL statement。

So the reason why he did this is because。They want to run on any possible hardware。

Right embedded devices， cell phones， laptops， any kind of ISA， they're certified to run on airplanes。

 your airplane is actually running SQL light， there satellites in space running SQL light。

 And so when you want to port the database system to a new platform。

 a new new environment instead of having to modify all other parts of the system。

 you just have to modify the VM。And he has test cases to make sure that this actually works。

You don't care about what actually generated the op codes。

 that's always going to be the same from one architecture the next。 I mean。

 there's files some stuff you have to deal with and so forth。

 But it's vanilla forco that or actually it might be in C。Yes。

 it's vanilla C code that's not doing a lot of specialized stuff。

 All the specialized stuff would be in in the VM here。

We asked him once too also like could you build like an FPGA to actually interpret these op codes。

 and he says it changes from one version to the next， so it probably wouldn't work。Okay。

 so the hyper was the earlier version of a system the Germans built after got bought by Tableau。

The tablet owned the source goes So that went away。

 So then Thomas went started building a new system called Ubra。

 We'll talk a little bit about about that again throughout the semester。

 But what's amazing about Ura is that。😊，Rather than than generate the IR the L IR。

 the way that that they did in hyper， he's instead going to generate。

An IR that then gets converted into assembly。Directly。

 so its punch these C+ macros can take the I and generate X8 assembly。

 I think he supports arm as well， right And then now you have this assembly。

 you can then run the bycode interpreter or bycode a compiler， You're just run an asseler。

 which is even faster because it's literally translating the assembly instructions into into machine code without any additional optimization passes so。

😊，Then they do the same thing we talked about before where they run the query on the assembled version。

 then in the background they do the more extensive compilation， and then when things are available。

 they slide it right in。😡，So they have a followout work called a number called Flying Start。

It came out two years ago。I debated whether to read this paper versus the paper you guys read before。

you know， paper guys are before。 it's the seminal one。 But you know， it， it's， it's a bit dated now。

 And this is probably the better way to do this。 So A is the better way to do if you're gonna go down this path。

 But another way to think about this is like， they basically built their own compiler。

In the database system， as well as the database system itself。 right， Who does that。Germans。

 so it's insane。 right， then as I was saying before。

 you still have the problem where if a query crashes。

 you are living in assembly world where you don't have any provenance on what generated that code。

 So then they wrote their own debugger hooks for R R。

 And they have a whole other paper on this that is explicitly designed for taking crash query plans or trying to debug query plans that are generated using this code generation technique and linking them back and walking through the the。

The query while it's running and showing it that same time， like。

 here's the code lines that generated it， right。So the papers call it on another level。

 which I think I said to them， I was like this on another level。

 and then they put us the title of the paper， right？I can share this。 there's a video they show me。

 it's insane， right。Right， so。Redshift doesn't have to do any of this because they have the giant query cache of every possible query plan as before in the single node approach。

 you don't have that， and then this is probably the better way to do this。All rightSo quick。

 everyone' to talk about Java databases because it's very much similar to the LOM so we talked before。

 at a high， it's doing the same thing。 But instead of generating LM IR。

 you're generating JVM bytecode。 and then you let the JVM hotspot compiler or whatever iss called now。

 just compile that to machine code if it decides soon。😊，The one I want to bring up。

 who I to bring up is Spark and Que DB。 And so the reason I'm going to bring up the Sp one is because as I said。

 they're going to abandon any cogen and query compation stuff in the newer version photon。

 but this is a precursor to do this。 And then the paper you guys read。

 they'll talk about how the things I was saying where。😊，If you're doing cogeneration。

 you have to have people that have really no compilers and no low level assembly and bycode stuff in order to optimize things where if you just build a vectorized engine in CL S there's a larger number of people that actually can work on those things and they found that even though this may actually run faster in the short run in the long term you can have more people try to optimize the vectorwise code that you have and you end up getting better results and better maintain a system。

So what they would do in 2015， they introduced this new tungsten engine where they would convert the warehouse clauseuse expression trees into abstract syntax trees written in scala。

 and then they would just hand that off to the GVM GVM then convert that into byte code and then you invoke it as a function and do that natively。

 Well'll see also too in the paper you guys read they'll talk about how in some cases really complex queries。

 this AST would get massive and the GVM would choke on it and say this is too big。

 I can't run this query or I can't compile it for you and then they to fall back to the interpreted engine。

 and if you switch over to。If you hititch number to a vectorized approach。

 you don't have this problem。Another Java based database that does cogeneration is the thing called Que EB。

 and so it's a time series column database out of the UK。

 actually this is actually written by former HFT guys who know how to optimize Java code and they they set to build a database system So what happens is the query shows up。

 they just compile the wear clauses， but they're going to generate an IR in Java code。

I to use ASM Jit， which is sort of like a lightweight version of the L VM。

 then compile that into machine code and run that。 And so this is from a blogger they wrote where they show two optimizations that they made they converted the system to be multi threadreaded from single threaded and go from a giit system to a nongiit system。

 So the original version was single threaded with no jit。 And for some query here。

 it takes 33030 seconds。 But then if you do jting， you shave off about 10 x you get it down to 3。5 x。

 But then if you turn on multithreading and no jit， you actually do even better than with the J。

 But then the combination of the two of them get the best result。 for me。

 this is curious that the first thing they did was they built the jit part first So so the Jit came first。

 then they did multithreaded a year later。 And to me。

 that seems surprising because the first thing I would do was obviously build parallel queries。😊。

I don't know why they did that， what was the case but。In my opinion。

 you should do multi thread first， and then if you want to do gy second。

 And then because this result clearly shows the difference and combination to them can make a difference。

All right， we're way over time。Let me see if there's anything else I want to quickly show。嗯。Yeah。

 maybe we'll cut it off here and we can pick up a little bit of next class。

 because we want to talk about the project as well。But。I didn't get to the single store。

 I'll bring this up next class。 But the single store approach is the probably the better way if you do。

 you do jet compilation。 It basically， it's like， it's like the。😊。

It's like the hyper approach where you with this interpreter。

 then they can compile it and then you can have an additional meered step that allows programmers to work through and figure out what's going on。

 there's a failure and then the flying Start one is amazing。

 but you have to be German to actually build that kind of stuff and nobody else does what they're doing generating assembly。

 which is insane。All the newer systems， though， are going， for the most part。

 are going to choose to do a vector Y style approach。 again。

 for the reasons we'll see in in the photon paper from databricks， okay。All right。

 so next class we'll do query test scheduling， maybe I'll cover some of the cation stuff that we missed and then the paper you guys reading is from the Germans again。

 this will be morsels， even though it's going to be on a single node。

 the idea of how you break up the query plan tasks into these morsels based on the data that's going to be the sort of key idea we want to build in our system。



![](img/7e2db76ed9b200ab5de16ef8036e8f31_5.png)

Steps and six packs on the table and I'm able to see saying I on the way。

No short put the cl you know what got them， I take off the cat but first' tap on the bottom。

 don about three in the freezer so I can kill it， cat full with the bottle baby don feeling。

 cose nice says they' paying nice way， you don't get down with the guys little。

Take back the pack of thugs， evo to some now for trigger to the thugs。

 Billy De and the teach to tell him weak，Gosh， be a manic kid can of fake God。🎼。

