# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p01 -01-S2024 #00 - Course Overview & Logistics .zh_en -BV1HZ421N7WZ_p1-

🎼Carneki Mellon University's advancedance Data System course is filmed in front of a live studio audience。

😊。

![](img/a87615842ce341866d73f2c7b4028e53_1.png)

🎼You guys。Like I said， I can't be there for the first week classes， not here in California because。

Somebody needed my help and had to come and ask me to do something weird out here and so that's why I'm not in Pitsburgh the first week。

 right it's always。It's always something， oh， you know， like， oh Andy knows how to deal with。

 go have him help us out or like Andy knows some of about databases and go him help us。

But it is what it is so right now I'm out here in。parkingking lot with like a bunch of drifters and hanging out。

 but I figured now's the time to go through the class， let's plow through this。

So this lecture is not really going to be about the course material。

 it's really about the what the course was going to be about and then the logistics of。

Like how the project is going to work out because that's going to be a big component about 157 21 this semester。

 I don't want to spend time talking about that its supposed be different than everything， you know。

 the previous incarnations of the course。

![](img/a87615842ce341866d73f2c7b4028e53_3.png)

So。I said it's always every semester，hy should you take this course？

The straight answer is basically that databases are still in demand。

 that're super complicated to build， super complicated to maintain and optimize。

 and there's a lot of really interesting unsolved problems in data processing and running queries and analytics this course is going to prepare you for career or research into database management systems and the great thing about it is like even if you don't want to go down that path of like doing database systems work。

The things we're going to about learn about in this semester are going to be valuable throughout the rest of your life。

 so if you can write a code in a data system， you can write code and pretty much anything else。

 anything else that's going to care about performance it really needs to understand what data is what the workload is and how to have to take full advantage of hardware。

And the great thing about it is also too is people will pay you a lot of money for it part of the reason I'm out here in California to deal with all that best。

 and if you don't believe me， here's a quick overview of some of the students have taken 721 for the last five or six years or so and these are just the ones I can quickly remember off top of my head and they all end up at awesome places getting paid a lot of money to work on Dataway systems so hopefully if you come over with this this semester you we'll put your photo up next year。

And Databricks has surprisingly hired a lot of the best students more recently。嗯。

But everyone goes everywhere， which is always good。All right， so this course is really about the。

Understanding and learning about the modern practices of how people build a data management system and the techniques and the methods we're going to use to do systems programming to develop out those ideas and this semester we specifically going to talk about analytical workloads so so we're not really to talk about transactions or doing right- heavy workloads it's really about how do I have large data sets and run queries on them quickly to extract new information and new knowledge from the databases from that data and so the goal is in addition to understanding all the methods and techniques or how people build modern analytical database system youll learn how to write good code that's points and correct how to write documentation and testing plans for that code because it's not enough just hey。

 here's our project we're done we're going to have full-fledged testing methods and ways to ensure that。

Things are operating correctly， or things are producing the correct results。

There'll be a little bit of code reviews during the semester and then obviously working on a large code base。

 maybe not entirely true for at least the projects in the beginning。

 but since we're doing semester long project this year。

 your code base is going to get quite large by the end。

So we're really focusing here on studio art topics we're not going to be sort of rehashing stuff that we covered in the intro class or going through the textbook right it's really about looking at the latest research paper and the latest literature on building a modern system and then seeing how we can apply that to our own so at its core the the。

The overarching model of the database system we'll be trying to build or develop will at a high level look a lot like the stuff weve covered in an interclass classic database system。

 but it's really about how do we then infuse these ideas and these methods that enveloped the last 10 years or so to accelerate query execution。

Oh。So on that in that topic these are the topics or these are the main ideas or sections we're going to cover throughout the semester。

 so first we're going to talk about what the data actually should look like， the data formats。

 how we're going to do encoding compression in such a way that。

That will speed up data access and but also reduce the footprint of our database we spend talking about different methods to accelerate query processing。

 so doing vectorized query execution or cogeneration or query compilation， how to take a query plan。

 physical query plan and execute the most efficiently on the data。

Then we'll sort of look at a larger view of the system of how we handle scheduling within a single  query itself and across the entire workload。

How do you do？How to run join algorithm sufficiently， how do we handle network protocols。

 but between the nodes and between the nodes and the client。

When spend a lot of time talking about query optimization because again doesn't matter how fast we build our database system。

 if our query plan is suboptimal or just garbage， then all the stuff we're going to do before then doesn't actually matter。

 it's a waste of time。And then we're going to spend a significant third of the lecture a quarter of the lecture or semester talking about or looking at real implementations of Data systems and this by reading the papers from the major players in industry and startups and sort of seeing how we can then apply or how they're applying all the techniques that we've been discussing in their particular systems and we essentially former taxonomy。

 it'll say， okay， a system can do XYZ and we would then see how snowflake does things or yellow bit does things。

And so we'll cover that throughout the entire semester。So for this course。

 I'm assuming you've already taken the intertrocourse at CMU 15445。

 645 or something of equipment in your own undergraduate background like this is a graduate level course on modern database systems。

 really we talk about the classic algorithms， like how to do a hash join。

 but we'll talk about how to do it in a modern setting on today's hardware。

So there's a bunch of things I't need I'm not going to go over as background relational algebra storage models。

 basic memory management buffer pools and so forth。

 like all of those things we're not going to tell discuss I assume you already know them and it's really about okay how do you do a high performance modern parallel hash joint right as cache conscious or so forth so that's really the flavor for the discussion throughout the semester。

For the course policies and schedule， please always refer to the course webpage。

 I've posted that this week and these to be updated a little bit with some of the readings later in the semester will get changed up a little bit but for at least the first couple of weeks the schedule is pretty set and then we'll talk about what's required for you or deliverables throughout the semester but again I'll just say as we go along。

 obviously don't plagiarize， don't try to steal things。

 don't cheat and if you're not sure please come talk to me if we do catch you cheating in some kind of way。

 which again for a graduate level course this should not be an issue then we'll have to refer you to Warner Hall and that's not good for anybody。

I'm gonna to have my office hours twice a week immediately after class。

 330 or 430 and my office on the ninth floor in Gates if this time is not convenient for you。

 send me an email and then we try to figure out something else so you know I'll say this every semester。

 what can we talk about when you come to office hours with me。

 while we talk about you your status on the project。

 how that's going if you have questions about the papers and when I know more about that particular topic that go beyond the things we discuss in classm happy to talk about those things？

A lot of you going to want to get database jobs in the semester we talk about how we can facilitate that and like I said。

 like I know how to handle the police to certain extent， obviously if you're if you try to。

If you try to run from then， I can't help with that， but whatever， again， theyre involved databases。

You're going to be ending up in the parking lot teaching classes at some point or doing something you。

 so by all means talk to you before we have problems later on。

We have one teaching assistant this semester that's my number one PhD student William Zhang。

 so he's actually CMU undergrad， I think he graduated at 4。

0 he actually took this class when he's a sophomore and like crushed it in the way that's like suspiciously good for a sophomore but he's legit so we asked him to stick around and he's continued with his PhD after spending a little time at single store did his company and he's working with us now and he's fantastic so he's the TA for。

And as we get further along the projects， he and myself， either the combination to us。

 will be helping each group。With their implementations。He's Canadian。You know it's。It's fine。

 I mean theses been good to us， so there should be no issues with anybody in the course and if you have a problem with this。

 let me know。All right， all the discussion for the data operations of the course and just as we go along in the projects。

 you know we want to do the piazza， if you have a technical question about the projects or anything。

 again post everything on Piazza so we we can all contribute as a class。

 if any personal questions or anything that's not relatedlay the project， any logistical things。

JustSend those emails directly to me。All right so here's the breakdown for the grade to the semester so's me four parts and as you can see at the bottom the semester long project that's obviously the bulk of the grade and so if you're a Ph student this course counts for I think the software systems elective and this is the reason why because we're heavily focused on the projects so I'll go through eachE one by one but I'll spend most of my time at the end talking about the semester long project。

So for every class except when the groups are presenting their project updates and so forth。

 there'll be a assigned reading so in the if you look on the schedule there'll be one paper per class has this crown next to it。

 the icon indicate that it's the primary reading so this is the one that you're responsible for。

 if you want to go beyond the topics in the course。

 like if it's related to your project or you're just curious the other readings are considered optional and some of them I'll cover in in the lecture。

 but like the assigned reading is the main one that's sort of like the canonical。

Prorovvides like sort of canonical。对。Description of the technique we're trying to cover or the most important version of the technique we're trying to cover so for all these primary readings before class you have to submit a synopsis through a Google form at the URL there and the idea is here you just sort you would read the paper and then summarize what the paper is actually trying to tell us about what method is just trying to show us and by writing it down it forces you to really think about okay do I really understand what what the papers trying to say so the synopsis is not meant to be like a really long book report it's really just be like a quick summary of what the paper the key parts of the paper is。

So you have the first part is like three sentences both the main idea what context they're trying to describe this particular method and what are the key findings or takeaways from the paper and then like a one sentence description of like what system they're going to use in their evaluation in some cases it's obvious because it's like oh the paper。

 some snowflake， so they're talking about everything in context of snowflake or it might be like they hacked out Postgres or WDB and put it on that so like just understanding what was being modified。

 what's being evaluated that would be super useful and then the last one is describing what workloads or benchmarks they're using in their evaluation to test their particular ideas or method and the reason why this last one is's important because when it comes time to start testing and evaluating your projects。

 you know I don't want you to come be like hey what workloads should have use。

 you should know because you're going to see a bunch of these things over and over again throughout the entire semester in these papers。

So again， they had to be submitted before the class starts。And everyone is granted free。

 a lot of free skip workloads， skip free workloads。呃。During the。During the best。Okay。So again。

 for these， again， the whole point is for you to learn from you learn something from the papers so it doesn't help you if you just go take the paper and dump it into chatGT and that's what theop is right you don't get anything out about it so please don't do that if there's summaries of these papers that you find on the internet just don't copy them in don't copy from your fellow classmates again we will have to go turn anybody into the war at all。

If you get caught doing this， then don't be as stupid。哎い。

In addition to the synopsis for every class there's also going to be each students may required to write lecture notes think of this as like a longer version of the synopsis but also covering all the ideas and other papers we're discussing the class which may not have it included in the single paper assignment so the ideas like you watch the lecture and summarize the slides and the key things that were talking about into knit and I'll have examples what these look like we'll put everything on GitHub' put everything in the course website will make these available to both the current student in the class because that help them on the final exam but also the future years and people outside seeing you So again。

 these notes should just be sort of limited to the。Things that we discuss in the slides。

 oftentimes students will ask questions and I'll start seeing crazy stuff。

 that does not be included like anything about the slides is sort of the key thing there。

So every student has being assigned to do this once per lecture problem that we have more students in a lecture so I got to figure out how to handle that so right now there's an administrative spreadsheet。

 there's an assigned lecture date with everybody's Android ID that when we got to figure out how to load balance that accordingly I don't care who does what so if there's a you really want to cover you want to swap somebody else by all means do that you don't need to ask me to for permission to do that just go ahead and do it。

And for this one， you're allowed to use chat ET or whatever you want， right。

 because we don't care because it's really about like。

You you're using as an assistive technology to help you flesh out the core ideas or things you want to want to capture in writing So by all means like if you want to take the transcripts from the videos and put that into chatTPT and let us summarize for you but then use it as the starting point to then flesh it out further go ahead and do it but in the end you' you you as the student are ultimately responsible for what that lecture what the lecture notes are going say So chatTP because starts going off the chain and start saying things like actually one year ahead embedded I embedded column or stuff which is not true So chatt starts。

Same B and you put that in there and turn it as lecture notes。

 well no you didn't vet that and youll be doed for it right so obviously again be smart using modern technology。

There'll be a final exam and that'll be take on long form I'll give out the questions at the the last day of the class and then you'll turn it in when we we have the final exam final presentations during finals week and again this is not meant to be。

It's not going to say， you know the question not going to be like， okay。

 what does this paper say about this particular thing。

 The idea is to see whether you can synthesize a bunch of different ideas from the various materials we talk about in the throughout semester and then。

Put them in a new context work a new theoretical system or something like that to see again you understand not just how individual ideas work。

 but how they all sort of fit together into a larger system。

 which is sort of the key thing that we want to focus on here。All right。

 so the big part of the semester is going to be the semester long project and the idea the high idea of what we want to do is we basically want to start building a。

You know， a new database management system here at Carnegie Mellon。

 both myself and the other professor J X Patel。 And so the course is going to basically be the。

The sort of starting point for fleshing out some of these coupons we would need in this larger system。

And so one of the overarching themes we're going to have for how we design things going forward is。呃。

Is adaptivity so not just the idea is like can the system automatically adjust a query why it's running it dress itself why it's running based on the data that sees or different characteristics of the hardware and can we do that incrementally over time And again I'll explain what that is as we go far that long。

 but that's the overarching theme is sort of in that direction We decided to do everything in rust the semester like I said I did not know Rus before the semester and as I send the email to you guys I know a lot of you don't as well So we're not going to teach you Rus we'll just sort of pick it up as we go along。

We don't know we havet a name for this system yet， which is always one of the hardest things to do in computer science。

 but the idea is that we could take all these components of the different projects。

 put them together and make a fullF system maybe next semester in the fall or the summer。

I have a waiter kind of name systems but it's right now。You know， its names to be determined。

So the way we're going to do this is that every group is or every student is going to be assigned to a group and we have groups of three。

And then there'll be five topics or components of this larger system we end up building and the idea is that we have roughly 30 students。

 we would do three groups of 1， sorry10 groups of three。

 and we would have two groups assigned to build the same component。

And so they'll have to collaborate a little bit， make sure that they figure out what the specification of that component is。

 but then they're also going to compete with them try to build a faster。

 better implementation than that。And at the end， we'll have a vote decide who gets which component of the two。

 the same topic is， which implementation of the same component in the same topic is the winner and we'll use that going forward in future research and future projects。

So everything I said here is true except for the optimizer group and' why that's different。

 but the basic idea is because the query optimization is so hard and we only have a semester。

 it's unlikely anybody's going to build a query optimized in a single semester。

 so whereas the other components we could build a working prototype fairly quickly in a small group。

 so the idea is that we will for the optimizer team they'll have to collaborate together more so than the others。

All right so five， as I said there five project areas our project topics。

 the first four here are the ones where again， they will have two groups and we try to implement the same thing and compete against each other。

So the first is going to be a scheduler， this is the part of the system that figures out。

Here's the queries I need to run， how do I break them up and send them to different nodes and then as the queries are running。

 how do I keep feeding or as queries are running， how do I keep feeding tasks？

To the noses that keep them saturated and always busy。

The execution engine are the parts of the system that's going to take those tasks for the query plans and actually start executing processing data to simplify things。

 we're going to assume that the execution engine will be a single node。

The next component is the catalog service and this is going to be the internal database files and keep track of the database files and the schema and this will then be fed into the query optimizer and the scheduler to figure out。

 okay here's the data I have， here's the tables I have and how to generate the physical plans for those。

And the last one here will be the IO service， the thing that's actually responsible for going out to disk or an object store。

 retieving the blocks of data that are needed by the system and then distributing them to the various needed。

 then also can maintain its own local ephemeral cache so that we don't have to do expensive calls to the object store。

 read right things from local disk。And I says as the query optimizer， for that piece。

 the idea is that SQL query shows up and then we want to use a combination of roll basedase optimizations or heuristics and a cost based search to determine the best physical plan for that query。

We do have an existing prototype now that a student worked on last semester called OpD。

 it's a fork of data fusion， which we'll explain that is as we go along to the semester。

 so it follows the data fusions internal format for query plans。

 but it doesn't rely on them data fusion that do。Join join ordering and other things so again。

 the inquiry optimizer super super hard we're not going to get。

 you know tall we're not get too far in a single semester and so the idea is like set up having two groups。

You know， build redundnant things for this part here。

 it makes sense for them to collaborate different parts of the system。

 different parts of the optimize， but working on a petition at a single code base。

So for all the other projects we want to implement this from scratch。

 we're okay with you taking heavy inspiration from open source things like data fusion。

 is one thing we're looking at in particular if's another one Blocks from Facebook or meta for their executionion engine。

 but that's the S lawsaw， so we're okay with you just looking these things and discussing them。

If it's open source and if we figure out how to borrow those ideas and put it into it。

So for that this semester it will be four projects sorry four milestones。

 so the first one coming up we January 31st it will be the。

It be the project proposal excellent second， then'll be two status updates once a month and then at the end of the semester whenever we're assigned a final date。

In May， then we'll have the final presentation and then everyone's be required to do the code drop on GitHub to turn in the systems。

But again。The idea here is that by having these incremental updates and even in some classes at the end。

 we have extra time， we can sort of discuss how everyone's the progress everyone's doing on the projects and anything that is coming up any problems and issues amongst everyone and that way it's not like everyone disappears without any feedback and then they show up at the end of May and be like hey here's my project how did I do like everyone's gonna to know how everyone else is doing and we sort of see how all these things sort of fit together。

So right so the first thing coming up on the 31st is in two weeks will be the project proposal and this will have three parts it'll have a plan。

 like one or two pages of a markdown file describing how you're going to actually implement the thing the part of the system you're going to be working on and then you give a five- minute presentation of the class and say here's the high level ideas of what we're trying to do and a key thing what you want to describe is also not only how you're going to build your thing and what ideas of what libraries and so forth you're going take advantage of but actually how you're going to test your implementation to see if that is actually correct。

 make sure there's no errors and problems that you go along。

In addition to the project proposal itself， you also have to turn in a specification proposal for what the API of your components is going to be。

 So you can sort of think of these five projects as all sort of microservices and there' an internal API that's going allow one project team to call your。

 you know your service to get whatever it needs sort of like if the。

 if the executiontion engine team， they obviously need a physical plan。

 so the query optimization team or the schedule team is going to have to give query plans in a format that the execution engine team can actually use。

So we want to be up front and figure out what the API is ahead of time so that everyone knows how to talk to the parts。

 other parts of the system。So the API should cover like what are the commands or operations you're going to expose。

 what are the input and output andcoding is going to be so I for example I said queryrry plans or like you know if it's the IO service。

 what are the data blocks actually going to look like is it going to be parquet formats or something else right and then how we're going to handle status quo and error handling。

For these， I'm not going to care about authentication or any security stuff。

 again this is just you a prototype for us so all those things we don't have to worry about。

And so now what's going to happen also too with this API specification is that the two groups that are building the same component have to implement the same API。

 so the way this is going to work is，Each group is going to have to say designate one person as a liaison that's going to talk to the other group and they have to get together to decide okay。

 here's what the API needs to be and so that way if you decide to choose one project versus another at the end of the semester they'll implement the same API and everything will still work。

And then the liaisons when maybe talk to liaisons and other groups make sure that they understand what is expected of the data or the outputs that they're generating。

And so for the APIs rather than write everything from scratch because it certainly two weeks is not enough to figure all this out。

 especially for some of you that are like coming at us from first time thinking about these things。

 we want to reuse as much existing APIs as possible so example would be the catalog service to just reuse the Apache iceberg API and just expose that same interface and that'll say a bunch of trouble so for co optimize team Cal site would be another choice an API we could choose for Exion engine we could follow Vellox or data fusion right so by all means reach out to the Ill discuss this in class reach out to the Ts and。

Instructors we'll figure out， okay， here's the University of the API you should be trying to follow。

 please guide you towards somebody to look out。嗯。The other cool thing I should do if the two project teams also implement。

The same API， then you could do end to end high level testing and use the same infrastructure so for example like。

If the API is the same， then like the catalog sort。

 you could have like you get me this table metadata。

 like you could have testing code that could be reused for both of those teams long as they implement the same API。

So then throughout the late in the semester we'll have two status updates and this is just a five minute presentation of class to everyone to say here's the setup for the project like here's how far we've made it。

 here's what's changed in our plan since the last time we presented。

 what are some of the surprises you've encountered of either how hard or how easy certain things going to be we'll talk more about this as we go along but we'll have to have we'll enable testing coverage checks and make sure your tests are actually writing code that's actually being verified and checked in through tests。

 so we want to know what your coverage number is and then if people have demos that's always super exciting to share this as well。

And then as part of this also again， you just keep updating your design document to say you know how things are evolving over time。

 so you'll want to basically mean this is what you have to turn in the end semester so just keep maintaining this document as you go along so that it's not like you go right different from stretch when it comes time for like fair finals week。

And again， the liaisons are going want to talk to each other and say say here's how I're going to implement。

 here's I can implement certain benchmarks and tests because at the end of the semester we want to actually do comparisons in some way。

 either the correctness or for API coverage or performance of these different parts。

 so how are you actually going to compare these guys。And then during the finals week。

 we'll have a final presentation and talk about here's what you implemented， what you accomplished。

 and then how to measure the performance differences between the two different implementations。

And so for the final benchmarks that compare your implant against the other groups。

 we have nice dedicated machines here at CMU that you want to use for these evaluation。

 so we'll coordinate this later， but the liaisons will be responsible we' actually scheduling the time and running those benchmarks。

 so we have a true apples apples comparison between the different groups。

And then lastly is that we're not going to say any project is completed until we get a final code drop and that means all the comments and other code reviews issues on GitHub all been addressed。

 we have all proper test cases， we make sure everything's sort of working and we have nice documentation and comments in the source code so you can essentially hand it over to the next class and let them pick up where you left off or in some cases some of your students are doing masters thes is or captionstone projects。

 when you come back in the spring semester or sorry the fall semester。

 you would have something to pick up on and know how to keep continuing things。

So this one Justin goes without saying， don't want to plagiarize。

 don't copy code that's not yours without getting permission from instructors。Again。

 for some things like parts of an executionion engine。

 you can go look at data fusion and see how they do certain things。

 I'm not saying they do everything correctly for the best way， but if you want to sort of。

Pick high level ideas of how how they set up the code。 that's okay。 But you know。

 obviously just don't wholesale copy things and try to pass it off as your own we make sure that we know that the lineage of the。

Any source code they we werere adding to this project， know where it came from。

And make sure it's under the right circumstances。All right， so that's it for now。

 the sun's coming out， I got it get going so for next class we'll have the first lecture on the first paper on sort of modern analytical systems。

 so this'll be I think from the data of describe guyss describing what they do。

Youll want to submit the first reading review for this game before class starts and then use that link there and that'll take you to the Google form to fill it out and we'll also talk a little bit more about project logistics I'll post on Piazza again if you're not in a group。

 how to find a group and beginning the process of running your project proposal as doing the 31st and then for the lecture notes again go check to see what your signed node data is and for the ones that are。

we we have more students and lectures， again we'll figure out some alternative or something else to do to spread the book out evening。



![](img/a87615842ce341866d73f2c7b4028e53_5.png)

I guys， hope that。See you in class of Monday next week。



![](img/a87615842ce341866d73f2c7b4028e53_7.png)