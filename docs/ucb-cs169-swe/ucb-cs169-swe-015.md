# 015：UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p15 15 CS169 15.zh_en -BV1UsB7YPEMj_p15-

There is about 16 people in the room。I guess it is the middle of the semester。

 so not too surprising so today we're going to continue with active record associations。

Some specific active record stuff there and then sort of a little bit on the theory of how we might think about designing what associations we should have。

 what relationships make sense， some tools to express them， if you are starting a new application。

The design decisions that you make at the beginning will have a large impact on how happy you are with yourself in four or six weeks and again how happy the mysterious people of the future are with your own decisions。

 which means that if you're working on a legacy project you get to decide how grumpy you are with past students which is to say that the design decisions here do matter。

 I personally think that they are some of the hardest but also most interesting decisions you get to make as a software engineer a lot of things that we're going to talk about don't necessarily have right or wrong answers but there are clear paths again that are。

Better or worse for certain situations and so this is a topic。

 a technique that you will get a lot of experience with as you continue building applications。

 but it is also one where a lot of the learn we'll give you techniques for how to start。

 but a lot of the learning， a lot of the intuition that you will build comes as much from experience as it does from theory。

Just keep that in mind。Reminder so there are some extra lecture videos that are on topics like exploring a legacy codebase。

 they're not up yet， they will be up later this week and or early next week we have to extract them fromedX which turns out to be a bit of a pain。

 they are technically in scope for future microquizzes and the second midterm but they're not super long it is related to material in the book so if you diligently read the book and you also pay attention to the videos you'll be good but we'll post a link when they're there。

And again， like other things we are going to do our best to focus on the big ideas and not just vocabulary that's the goal。

 all the vocabulary questions， of course， in fair game this is also just a fun image that every time I come across it is good if you've seen a'Reilly books they are a great technical publisher but so this is all the style and things that you will do as a programmer trying stuff to see what happens definitely been there done that copy and pasting from stack Overflow yeah happens。

😊。

![](img/0b01a30501fea891eb38872f66d2ae79_1.png)

You know just these are the things that you will also do this semester， so if you haven't seen it。

 this is not necessarily a class topic but。Is pretty freaking big news。

 which yesterday Google published a paper in nature claiming that they have the first case of quantum supremacy。

 so this is the idea that quantum supremacies， a quantum computer can do a task in a reasonable amount of time that a conventional computer cannot do。

There's a whole bunch of stuff that frankly， I do not understand because I'm not an expert on quantum computing and physics is not my domain。

 So don't ask me about the quantum stuff。 But it's in terms of momentous computer news。

 a really cool thing。😊，Google is making the claim that this is analogous to the Wright brothers first flight。

 so the problem that they solved is kind of esoteric but it's not a particularly useful case。

 but it is a problem that they believe they have solved correctly in a matter of minutes on a quantum computer that they claim in their paper would take 10000 years IBM claims that the problem that Google tried to solve would take two and a half days on the largest supercomputer in the world so two and a half days on the largest supercomputer versus three minutes on a quantum computer still a pretty darn impressive gain so that's some interesting news this image on the right is the actual processor which is kind of fun because if you look at it it actually looks just like any other processor so in some ways the things that we might see with quantum computing。

Might not look all that different on the surface but。This is a pretty big deal。

 so this is the link to the Google article， there's a ton of news stories and a ton of related links if you want to dive into that。



![](img/0b01a30501fea891eb38872f66d2ae79_3.png)

So to continue on with the topic， active record associations。

On Tuesday we finished up talking about just some database modeling。

 we talked about in theory how we could represent relationships。That we have movies。

 we have reviews that are things that。Or。They belong to a specific movie。

 I use that word intentionally because that's the term that we'll see an active record in rails。

 but what we've looked at so far are just modeling the relationships in the database by using this review ID。

 a foreign key， we have the ability excuse by using a movie ID which is a foreign key on the reviews table。

 we have the ability to tie a specific review to a specific movie and we could have multiple reviews of the same movie by having multiple rows in our reviews table。

😊，And so this is where he left off on Tuesday talking about what we can do in the database and what we can do in the database is all well and good。

 that's an important necessary critical step， but what is really awesome。

 one of the reasons that rails is still around， one of the reasons that I enjoy using rails that I hope you'll find is that active record makes manipulating。

 accessing just reading and understanding these associations so much easier than just rawSQL queries and so today is how we go through that soap。

😊，嗯。The goal is basically we have a relationship in the database。

 how do we expose this in code in a nice manner， how do we give us the tools that make it easy to set things up correctly。

 and then we don't have to worry about the SQL。Ruby code， we have our movie class。

 like all database backed models， it is an instance of active record base if you are on rails。

Optional in Ras 5 I believe， but Ra 6 and4， the class that it will inherit from now is application record which then inherits from active record base。

 so rails kind of keeps tweaking the exact object inheritance hierarchy but the specifics of that don't matter too much。

 this is what you'll see on a rails for style application。

 but essentially just giving us the tools that active record has so we can say something like a movie has many reviews。

😊，And so what does that allow us to do before we continue on with what it allows us to do。

 we can say that a review belongs to a movie and these two things here。

 we don't really need to build in the end effects。These two things here give us the ability to say in our database。

 we have this foreign key relationship of a movie ID on reviews now with just one method call in Ru so has many belongs to are just methods that rails gives us。

 we can now have access to all these super powerful features so what does that look like in practice。

 so reviews the table has a foreign key called movie ID。

This allows us to set up or has many and belongs to relationships。嗯。I will warn you ahead of time。

 especially if you haven't。Played with your existing app yet that which table the foreign Keep belongs on is really easy to forget when you're starting out if you forget a few times if you set something up and put it in the wrong table。

 don't feel bad about it at all， the ruby and railils documentation is pretty helpful here but once you start just sort of setting things up。

 when you get practice with rails， you will sort of build the intuition for where things should go but it does take a little bit of time。

😡，So reviewss has this movie ID by specifying a movie that has many reviews。

 we get to say movie dot reviews。By saying a review belongs to a movie， we will get to say review。

movie， and basically what we're looking for with these is if a review belongs to a movie。

 we're looking for a column review。movie ID。With movie reviews。

 we're looking for the review table that has also the column movie ID。

 so in this scenario with one database column， we're going to express a bidirectional relationship between movies and their reviews。

And so。U。Basically， what we're doing is。We're just saying that using the stuff that's in our database。

 we're going to add support and rails to make this more clear。

When you do when you set up your database these。These columns are specifically foreign keys。

 which means they have a specific type in the database。

 which sets up the constraints that when we store some data in our movie ID field。

 it is actually a valid movie ID。 This is really nice。

 there's a thing that we won't talk about too much。

 but you may have heard this term called referential integrity， which is。

Does the data in our database make sense？Foreign key relationships allow us to accurately keep track at the data level that every review that has a movie ID。

 that movie ID is in fact a valid movie ID， and we can do all this with rails migration。

What does this look like in practice？We are creating a reviews table。

 we know that we want reviews to be of a specific movie so that when I review inception。

 that review shows up as belonging to inception。In this case， potatoes is our rating system。

 it's just one to five， I believe， it doesn't really matter what their scale is。

 but we have a rating。Oh。We use the word T dot references or the method references。

 So references says in an active record migration that this thing is going to be a movie IDd when active record creates the SQL query。

 it's going to say。This column has the name movie ID， the type is whatever type of movie ID is。

 so typically that's going to be something like a serial or an ID type or a big integer or whatever strategy you may use in setting for database the specifics really don't matter because rails handles all that for you and then we in this case we'll set up a second foreign key relationship on moviegoer。

 so this would be the person writing the review so that if you log into a rotten potatoesta app you could see all the reviews that you have left or if you want to view all the reviews by a particular user you would use the moviegoer reference there and so。

In this model， what we get is we get a reviews table with these four columns。

Two of those columns are foreign key relationships on different tables。

While you have the ability again， to customize everything， by using what's default in rails。

This movie underscore ID makes it very clear that the column that we are referencing here is the ID column of the movie table。

 the movie goer underscore D is the ID column of the moviegoers table and you will notice that the table names again are pluralized the reference the foreign key column names are singular rails handles all that for you it keeps those relationships those names consistent so if you ever see this。

You you will be able to sort of just in your code， if you're looking at database。

 realize what should be happening here， but for the most part。

 railils will do what we expect going along。 so we've set up our associations and our database we've used has many we've used belongs to now the real value of doing that is what that means when we work on our code in our models and our views so。

Movie has many reviews， this gives us the really exceptionally handy method movie dot reviews it does what you expect it to do it runs a query that finds all the reviews that have that movie ID then because rails is awesome make sure that those reviews are actual review model objects so you have access to all the methods of the review model you can do things to those reviews you can also in your views or whatever you want to just say four reviews in reviews render review and in like two lines of ruby slash hoel slash slim views you basically get to very quickly render all your reviews rails handles all this really awesome stuff for you and so。

😊，This is the real advantage of setting up our relationships nicely。

 So it belongs to gives us review do movie。 And again， this。You know。

 this is a real movie instance of a movie model， it has all the methods that our movie model would have。

 it's not just the data in columns， it's a full rubby object here you'll notice that。Has many？

Reviews is pluralized， belongs to movie is singular。For the most part。

 there are times where it will be confusing or counterintuitive。

 but rails is going to give you singular or plural methods depending on what relationships you specify with your data。

 so has many means that that instance that gets returned back is an array like thing。

 it's not technically an array but it is in anumerable object that you can loop over that is multiple reviews。

Reviews。movie is one single movie。😊，If you're ever trying to realize you is something pluralized or singular in rails。

 look at the relationship that the model has been set up if it has many where there's many。

 it will be plural and as a reminder， rails is pretty darn smart at pluralizing things so you know if you have a mice table and you have if something belongs to a mouse。

 it will be dot mouse and not dot mice， it knows how to properly inflect things which is nice at least it's nice if you care about the English language。

And so that's basically what we get in our rubby app or in our rails app。

 and so with that we can use all the methods that we have there。嗯。Basically。

One to many hassman and belongs to are going to be the。The two keywords and methods that we use。

 one to many are probably the most common relationships that you will be modeling in your applications。

But if you look through the active record documentation， there's one to one relationships。

 many to many relationships， and I guess the inverse of one to many would be many to one from the other direction but you can model all those you know in your railils apps depending on what you need so we define a relationships。

 we create a migration， we run it in the database and we have our data。

 so you may also this is just a handy bit of rake syntax。

RakeDB test prepare will set up a test database so that before we run it on a development environment you can see in a test in your test database on your computer what might happen。

 this is a good way of seeing and modeling do my relationships make sense you can also apply things to development database and blow away the changes RaDB reset is a really handy command。

 it can definitely be your friend at times， so you have the tools that rails has available for managing all the data so our first clicker question looking at these relationships。

So suppose that we have set up a foreign key movie ID in a reviews table。

 so our reviews as they call a movie ID， if we add has many reviews to our movie。

 what we do not add the belongs to movie in our review model what will happen。

 so we have our data modeling set up correctly at our database but the only relationship that we've told rails about is has many reviews。

 so which of the following statements are true。All right， 33， okay。Nice。

And based on quickly counting people in the room， it's probably not going to get much higher than this。

 So let's see how we're doing。 Cool。 So there's a wide distribution of answers here。So。

Talk to your peers and let's see in about a minute and a half if we can discuss what the right answer is here。

we don。I should how。之休出。I说。Okay。你。你接得。All right， take another 30 seconds or so and put in a vote again。

Another 15 or so seconds， see if we can actually get back up to 38。All right， well。

 we're right about 31， so that's close enough。Awesome， so we have a few more A's this time。

 that's good。Does anyone want to explain why A will work in this case， what's the reason why， sure。

 yeah， just go ahead？Like in the reviews table， we could still like have like a movie ID column。

 but just without the like belongs to Ed， we won't be able to call the review Do movie。Yep， yeah。

 so our data model set up correctly so in this case。

 what the belongs to gives us is the ability to say review dot movie， we didn't do that。

 so we can't call review dot movievie。So movie do reviews is the result of saying a movie has many reviews。

U。We won't get a database error when trying to save a review as long as we specify the ID of the movie that's present。

 so there is some data in our。knowIn our database our record that would work and actually depending on how we set up our database。

 a foreign key relationship could be optional， we don't necessarily need that to be present。

 but in this case， assuming everything works correctly， it skipping。

 declaring belongs to is not going to cause any errors in our database。Because a movie or excuse me。

 because a review has a movie ID， even without the has many。

 we still know what the data modeling is like， we still have the ability to get that review or excuse me that movie from that review and because of that a or D is not correct since C is not correct。

 also C and a cannot be correct in this scenario at the same time because if we can do movie reviews。

 we would at least have one half of the relationship and really the point here is that when we have bidirectional relationships。

as long as we have one side we have the tools to build the other direction so most of the time you're going to use hass many and belongs to together but you might not need to。

 you might not have to depending on the structure of your application you know it could be conceivable although I would say probably very unlikely that we have a view of a review that doesn't tell us what movie this review belongs to and we only know that by looking at the movie page in a scenario with reviews that wouldn't really make much sense to do because obviously review。

Really hinges on the movie that it's being applied to or that it's about。

 but there may be a scenario where this belongs to relationship is not needed in your application。

 so if it's not needed you could leave it out， but for the most part you'll probably want to have it so。

One more clicker question， and then we'll take some other general questions。

 why do you mysteriously stop working？

![](img/0b01a30501fea891eb38872f66d2ae79_5.png)

Oh， because what do we bet I clicker。 No， it's still， oh， it just stopped the session。 Good job。试试。

A we going， okay， it's working again， let's go back。



![](img/0b01a30501fea891eb38872f66d2ae79_7.png)

And let's not have it cover our question text。That's not very。There we go。

In a different scenario we have。Edual application， so we have a professor has many courses and we do not say course belongs to professor。

 so this is the model or the relationship that we've declared in rails。

 which of these do we need to set up in our database？So again。

 kind of looking at the similar scenario but from the opposite direction。啊。All right。

 that's a little less。Then we were before it， but cool。

A pretty good distribution of responses so once again take a minute and talk with your peers and just as a note like when we're thinking about this when you're working on your applications。

 sometimes it' will be easier to go a database model first and then understand what to do in rails。

 sometimes it'll be good to go from rails first and then understand what to do in the database that's sort of up to you with how much practice you have going in each direction but both are valid approaches to figuring out how to model your data and you'll probably want to do one of the other at some point so it's good to kind of experience figuring out you going from rails to database or database to rails making sure that you can go through both so。

Yeah。Talk with him here。Convince them that they are right or wrong。啊稍会。Oh。这个我体。要もとど。你 gentle。不是有责任。

All right， take about 15 to 20 more seconds and put in a vote。Use got really。

Our registration hasn't started。Ten more seconds or so。相差百事。关于 p图。Yeah。All right， well， it's lower。

 but we'll just continue on， more people voted for B， that's cool。

Because that is the correct answer every time the second vote is lower I wonder if people have just like fallen asleep。

 I don't see people leaving the room， so I know you're still here。

 but you can vote a second time it's okay if it's still not correct you know clicker points are for participation so just feel free to vote for anything although incidentally voting for the correct answer does tell me that things are going in the right direction so that is helpful so。

😊，B is the great option in this case， so with a has many relationship， so professor has many courses。

😊，This means that we're going to look for a professor ID on the courses table。

The reason that this is the right option is that。If we have a course ID on the professor's table。

That would give us a relationship where if our professors are only in the database once。

 we would only have a。A professor could only have one course and that would set up a sets up a relationship that lets us do a professor belongs to a course B also lets us set up the belongs to relationship if we want to but we don't need to do that in this case。

 so exact sort of same type of data modeling as the previous question just from the different side。

 we don't need a professor or we don't need a course ID on the professor's table because。

Rails in this case， as long as we have one of those foreign key relationships。

 we have the modeling that we need to find the data and if a professor is going to have multiple courses。

 there would be multiple unique courses with the same professor ID so that gives us the has many and as long as we are specifying a relationship with has many belongs to we're not going to talk about has one but it works similarly as long as we are specifying that relationship in our railils app。

 we do need a foreign key somewhere without a foreign key relationship then。

There is no linking at the data modeling level in our database。

 and so we always will need to have some sort of relationship in our database now。

You could do it without specifying a foreign key， you could just specify some random column name and write the SQL yourself。

 and that would kind of be annoying， but in theory you could set up your data model in other ways。

 but it does need to exist in the database。Moving along again， so these are our methods， we have Mo。

reviews reviews。movie within those we can access all the methods that we would want on those objects。

😊，MovieMo。t reviews will give us reviews that belong to that movie that we could then save we。Just。

 you know， however we want to build our objects， rails will give us the ability to do that。

 but these reviews are either existing reviews， new reviews that rails will in its own relationship automatically tie to this movie ID。

 So if you're ever going from an existing movie to a new review。

 Rails will set up that relationship for us once it's saved railils will find it based in the movie I we have。

Ability to。You know to use everything that we would have within just a single model， so movie。

reviews。ware is finding all the reviews where in this case a certain rating applies。

 whatever other methods we might need， we could use those so we've talked about this a little bit but suppose that we have foreign keys in our database。

 really did this。ok。

![](img/0b01a30501fea891eb38872f66d2ae79_9.png)

This is a terrible application。

![](img/0b01a30501fea891eb38872f66d2ae79_11.png)

啊。Okay。I think it's back。 So suppose that we have our foreign keys。

 our data model set up in our database， but we haven't specified the。

That has many and belongs to relationships in our rails application。Which of these is possible？

Are they both possible or are neither of them possible， only one of them？Well。

 people are waking up again， that's good。All right， so that's about where it normally is。Cool。

 so most people voting for C， a few A's， a few B's。1 E and just a couple D's。

 so' I'm not going to have people re just so we can get through some。

 but who wants to make a justification if you voted for A B or C。

 why one of those things is possible。If you voted for C， you can choose whether to justify AirRB。

 if you voted for AirRB， justify why that one is a possible thing that we can do。

A lot of people voted， the answer is C， so a lot of people got this correct。

 so your intuition is good， why is it actually possible？Anyone。No。Oh， someone。Does anyone want to go。

 okay？The reason so the reason that this is all possible is that even if we don't thank you even if we do not rely on active record。

 we can write whatever SQL we want to write in our application Act record doesn't restrict us from doing that you have the ability to write rawSQL at any time but really what active record job is it is a better easier interface for SQL。

 it writes queries in an optimized way so that you don't have to write them， it also lets us。

Mannually construct or I shouldn't say necessarily manually。

 but it lets us construct similar queries so I could say movie doware or excuse I could say reviews dotware movie ID one to find all the reviews with movie ID1 so I could go in and manually construct with active record those relationships。

 and if I can construct them with active record then I could just write that SQL myself。

 but you really don't want to do either A or B， in most cases。

 you really probably won't need to write much RossQL at all in most railils applications。

Though every once in a while there's a need， so these are all possible but they do require the data model in the database to be set up correctly。

 but if you don't use active record to do it， you can still you know do it yourself。

So questions so far on before I get to the next kind of associations。

 questions so far has many belongs to those kinds of things。Nope。So。嗯。

So far we have a direct relationship to a a movie and a review， and that's great。

 we can model that really nicely now sometimes what's going to happen。Is we need to get。

Some other information。Through another object。In this case， our initial data model。

 our table had a review that had a movie goer ID。 So what if I wanted to answer the question。

 who are all the people that have reviewed this movie？I could。

 if I wanted to set up a second database table that actually stores a specific relationship between a movie and a movieer。

 but it turns out by having a reviews table with a movie goer ID。And a movie ID。

 I can answer the question， who are all the people that have reviewed this movie without storing any additional information？

Sue。A movie， a moviegoer has many reviews。A movie has many reviews as well。

 so each of these is just using the existing foreign key relationships right here that are just directly in the database now what I want to say oh before I get to where I want to go。

 we could say that each of these things belong to a movie so going the other way。

So how do I get all the reviews by all movie reviews by some moviegoer， so we do has many through？

So again， we have those。We can say a movie。嗯。We have movie dot reviews， moviegoers， dot reviews and。

Now what we can do。Is a moviegoer has many movies through reviews。

 so if I say how many movies have I seen， what movies have I seen I can get to that through the reviews class。

A movie has many moviegoers through the reviews class so I can answer the question。

 who are the people that have seen or reviewed this movie。

 and each of these I'm able to express relationship。That exists naturally in our data。

 but is not necessarily a single table with a direct link。This gives us the same type of method。

 so we still in rails have the same type of。Designs with our methods， so we get to say moviegoer。

 movies， we get to say movie do moviegoers through these two relationships。

 so they work exactly like regular has many methods。

 you know same way that everything we can do with movie dot reviews we can do with movie do moviegoers but what we have told rails is the way that you find these moviegoers is through this other table。

😊，And so。How does this work in SQL so again， we haven't covered SQL yet， so I don't expect anyone to。

You know understand the full query， if you've taken 186， this will be right at home。

 we will have a lecture on a bit more of SQL later in the semester where you might need to use it where you get into some advanced stuff。

But this is the real benefit of rails and of doing these things is that you don't have to write this yourselves。

Although you could。But。So how do we get a user so this should really be a moviegoer movies Well。

 we select all our data from our reviews we're joining so again joining expressing the relationship at the database level with the moviegoers table and we're looking for things where our moviegoer ID。

aligns with the reviews that moviegoer I column so this data here aligns with this data and what we've done now is we have joined a second table so now we have not just reviews and moviegoers。

 we have reviews， moviegoers and movies and so we get to we get to now have rails associate all of these things together for us and so when railils gets that data back it has all the data it needs to create our models in memory。

Many to many associations are something that is possible in here so students have many courses。

 courses have many students， what you will do is you would probably create an enrollment model。

there was a question in the midterm， so we're going to release that pretty soon that was asking how do we model a watch list of movies and there is a lot of different ways that we can model many to many relationships。

 but generally the trick is that when we have many to many relationships。

 we'll create another table that models that relationship， so an enrollments table。

Would be course ID， student ID， although。Yeah pretty much that's just all we need enrollments is a really common term for this stuff so a grade scopepe has a very very similar structure。

 B courses， which is open source if you it's a pretty well structured rails app although because it's very large does a ton of crazy things but has a very similar structure to this and with a many many relationship we get to specify still that you know a student could belong to a course。

😊，Course has many students， a user。If we want to model in a second application that they have many friends we could create a friendship model which just links two different user IDs together。

 so if you wanted to rebuild a Facebook like social network application。

 you could have a friendships table， at this point。

 Facebook of course is so large that they have a bunch of different ways of handling this data。

 but you have all sorts of abilities there so。This looks like it should work again。Cool does okay。

U so。When we are modeling some data， when we have an existing movie receives a new review from an existing moviegoer。

 what tables are modified？So we are adding a review for a movie that already exists and we are a user which because we're adding the review。

 we already exist。All right， let's see if we can get just a few more votes in。All right。Cool。So。

Again， for the sake of time， we'll just go through this together。

 but then want want to explain why we need to only modify our reviews table in this case。

 so I want to take a guess at why that's the case。Oh yeah， so it's looking on the other idea。

 go ahead。😊，Because。The user already exists。already exists。And all you're doing is just adding a new。

Yeah， absolutely。 So since everything already exists。

 the only information we need about that user and that movie is those IDs。

 And if this were a typical rails app， we would already be logged in So the application knows our user ID if we are on a particular movie page。

 Well， we know that that movie exists。 So we have that movie I and all we need to do is add a。

Add a record in the reviews table to store that review。

 and this is the really great thing about specifying relationships using foreign keys through a table that even though we have a bidirectional relationship。

 we only need to store that data once so。If for whatever reason we want to display a list of all reviews by a particular user。

 we only have to do one action to update our reviews table。

 the relationship from user to reviews gives us the ability to find all their reviews without storing that data in two places and that makes things a lot easier on us as application developers and makes things easier on the database because we're not storing duplicate information。

So it's a great thing that we can do that question。Do we not store the review Is？嗯。

We don't need to if we have the movie ID on the reviews table。

 so the reason for that is movie dot reviews。movie reviews that actually yeah so a has many relationship in rails is if a movie has many reviews。

 what it's always going to do is so on the movie model it's going to look at whatever it has many of。

 it's going to look at that table and look for the movie ID column you could choose to model your data in a different way like you could store an array column on a movie table of review IDs and not on the reviews table。

It turns out in practice to be a lot messier to get that information because if we like the reason that we want to do this in this case is。

If we want to answer the question， what review is this movie for？

It's much easier if we have that movie ID on a reviews table。

 if we have the movie ID on the reviews table。Then we could。

Duplicate that information on our movies table， but we don't need to， and so it's generally。

Sort of it's a waste of effort， but it also leads duplicating data in your database leads to additional challenges。

 So if you have data that's duplicated， then you risk things being out of sync at some point in the future you will run into applications where for performance reasons。

 it is necessary to duplicate that data stuff like this exists in grade scope and。

For the most part we've figured everything out now。

 I don't think we have any bugs as a result of duplicating data， at least I sure hope not。

but you know， in the process of development， when you sort of cache things in a separate place。

 when you store that relationship in a second direction， whenever you delete。

If we were to delete a review， then we'd have to also update the movie that stores that review ID too if we were to delete a movie。

 then we might also well in this case we might still want to delete those reviews or we might not。

But。Whenever you have information only one place， you're in sort of a much better position in terms of preventing bugs from happening and preventing inconsistencies。

 so if we can store things only once， that's really the best option for us going forward。嗯。Again。

 so we're not going to go through all these methods。

 This is examples of this exist in the active record documentation。

But the really nice thing is that you have all these methods available to you when you when you use the active record relationships so we can find things we can build and work with new models you know。

 basically what I'd say is don't worry about memorizing all the things that you can do at once as you need to model a relationship as you need to do something with。

😊，You know， a review from my movies class， go through the Ruby En Ras guides because they list in great detail all the。



![](img/0b01a30501fea891eb38872f66d2ae79_13.png)

All the things that you could possibly want to do there the other thing that's really useful about the Ruion Rails guides is a side note。

 they have their own consistent example so throughout the course we've been using the Roten potatoes application or variants of it for examples the Ruyion Rails guides are pretty consistent about using a bookstorelike application that has books。

 authors and reviews and so it is a second good example of seeing a consistent data model through various places that you might want to do in a Rails app and they express very similar relationships of data of things that we might want to do restful routes。

 all that kind of stuff So the Ruion Rails guides are also a good place to look there Que on through relationships。

Cool。

![](img/0b01a30501fea891eb38872f66d2ae79_15.png)

UmSo。Moving right along with wrestle routes for associations so this is I think one of the hardest things to feel like you got perfect so don't worry if your first attempt at this is not so great it's something that you will get practiced with over time。

But it is something that when done right， makes applications much easier to maintain。

 makes APIs if you are a developer interfacing with an application easier to use。

 And the great thing about them is when you sort of do this in a standardized way。

 it makes the experience of using or building applications more consistent。

 So you can start you know， jumping into another rails app， where even though it's a new set of data。

 a new application domain， the models operate in a consistent and expected way。 so。😊。

We have through associations， so we might have a course as many students through enrollments。😊。

Would be sort of one example that we could use sort of， you know。

 you can imagine that there's lots of these so。The question is if we create a new table。

 so this intermediate table， sometimes this is called a join table。

 if it exists as a model in a rails application， the documents also use the phrase a join model。

 which is saying this is expressing a relationship that joins two other things together。

The question is， how do we keep them？How do we keep our API our routes consistent and easy？诶。Yeah。

 we already have things like a new movie path， which we get just by doing resources dot movies。

 So what do we do when we want to add things that。A that we express sort of nested or through relationships。

 So in rails， one of the things that we can do is we can nest our routes。

 So if reviews belong to a movie。Then we can do resource movies。

 we can say within there there is resources reviews and rails will do a bunch of really cool stuff for us when it generates our routes。

But it's going to give us a structure that not just in our data model， not just in our controllers。

 but in the interfaces， the URLs that you build that other users might access have a consistent way of。

Of operating。 So another thing that you'll notice if when you look at URLs is。

You'll see like in B courses you have courses and it slash some ID slash assignments and there's an assignment ID that is representing a nested relationship so when we do this。

 what do we get back。What do we get back from rails， well。

 we get a bunch of methods and a bunch of routes。There are。Again。

 what is this seven or so methods that are routes that rails gives us for the resources command？

You'll notice that we have the same。The same sort of structure。 So we have our new path， our。

Our aPa or excuse me our new routes， our edit routes， our delete routes。

 but what's different about all of these is that they now specify in the route。

 the movie ID that this review belongs to and whenever we're working with a specific review we have a the review ID in a route as well and so。

The question or the。Challenge here in Rails is when we have two model relationships in our routes。

 we have movies and reviews that we are working with in the same example。

 one of them is named movievie ID， the other is named just ID。嗯。😊。

And this is the Rails convention and for the most part it works pretty well once you have your app set up。

 you don't have to think about this too much， but the review ID or whatever we're nesting at just ID route as the parameter is always the most nested resource here so prams。

 ID or prams colon ID is our review ID in this case，And our movie ID that if we're looking for。

 we're using that is going to be movie underscorecrD so the same as our column name。

 the same sort of consistent name and whenever we nest routes and rails with regardless of whatever two models we're nesting together this is the structure will get rails will let you infinitely nest your models and routes I cannot think of a good example off the top of my head for oh okay yeah so let's say a good example off the top of my head because it's one that I've worked with in gradecope。

 you have courses， you have assignments in a course。

 you have assignment submissions on an assignment so we have three levels of nesting and so our routes。

 if you ever like look at your midterm results you'll see the route structure reflects this which is also why it's like easy enough to tell you this because now that you know how rails works you can go look at the URLs that。

Greatcope provides and figure out how we implemented grade scope mostly so we have three levels of nesting The rails documentation recommends that you not go beyond two levels of nesting to keep things sort of nice and clean。

 It is a good recommendation。😊，Three works okay in practice。

 but really don't do more than three levels of nesting。

 Rails will happily be beaten into submission and it will nest things five or six or 20 times if you tell it to。

 all following the same exact pattern， so you have that flexibility。

 but in general try and stick to just one level of nesting if you need maybe two in some cases。

 but that nesting helps you express these complex relationships that gives you models that have access to everything。

We have our reviews so in our reviews controller， what will this look like。

 well when we went to find the movie of a if we're making a new review right。

 so before a review has its own movie we have to specify the movie that it belongs to so our create method in this example。

Is something that we'll be looking for that movie ID the nice thing is we can find it by the parameter in the route。

 so if we always stick to nesting our routes in a consistent manner。

 we'll have the ability to get this movie ID parameter。Then when we create our new review。

We can say movie。 reviewss do build or we depending if we want to use create with whatever prams we need there so we could have。

A review pram， a potatoes parameter， whatever。Options may exist in this method and the rest of it looks。

Pretty similar。You， this would be sort of a standard。Create method if it's saves successfully。

 we'll redirect you somewhere if it's not successful， we'll take you back to the new creation page。

 This is a pattern that you'll see frequently in rails apps but the new stuff here is representing this relationship and what's whoops didn't mean to tap there。

 but what's nice about this is，Again， with a relationship in a rails application we have nicely named path。

 so we have a movie reviews path for a movie， that is the page that lists all the reviews that belong to that movie。

 by passing in an instance of our movie model rails figures out the right ID to put in that path so it happens to know based on methods based on the models that are passed in what the final structure of that URL is and so。

By nicely nesting our routes， this is something that rails gives us u。Not quite for free。

 but pretty close to it。What would our new method look like。

 so remember new is the thing that's going to show us a page with a form。That lets us set things up。

Well， because this would be movies， slash movie ID， slash reviews， slash new。

 we know that this review belongs to。Whatever movie is in the Pram's movie ID？

We can set up a new instance。Of a review object so that we can do whatever we need to with that。

And then when you we can make sure that it all exists in memory and there's a few ways of doing that。

 but what's nice is that we have access by nesting routes when we create a review。

 it's clear what movie that review will be applied to so when you're designing user experiences of things that belong to existing data having access at creation time to to the movie that this review belongs to will be really helpful so that as a user when they go to their page。

 they see that they're reviewing inception， they know that they're leaving a review on the correct movie or whatever movie they happen to to be reviewing。

So having access to this data here is really useful in this case。You can also if you want。

 move all of this logic to or a lot of this logic to before filters。

 so a really common thing that you'll see is wherever you have these find whether it's find by ID。

 find whatever particular method you use you might say before filter before action， load movie。

 and depending on what you want， you could specify which specific methods it applies to。

 if the movie can't be found， you might in one place decide to。You know set an error message。

 redirect to an appropriate place， all that kind of stuff。

 so both these are techniques that you'll see in your rails applications。

 you can do it directly in a method。But a really common thing that will sort of again。

 dry out your code will be to use a before filter that does this logic for you。 And so one place per。

系。One place per controller that loads that data。So I've mentioned this a little bit so far。

 but in our views， we'll have access to our data as well。嗯。

And you know a lot of this is about providing convenience for methods that you'll use so as long as we have set up a review instance。

 we can get access to that so even if it hasn't been persisted in our database。

 we can still have a form that access is at review when it sets up all the information there。

We can specify links to the right。To useful places。

 so movie Review path again would be a method that rails gives us by nesting things and so。

This is something that the particulars are。There are kind of a lot to talk through。

 but when you are you？Oh no， it worked。My remote is not working quickly， but it's open now。You know。

 the reviews are kind of a lot to talk through or the reviews。

 the particulars of the path names of the Ul schemes are， you know， they have their own details， but。

When you get into Rails app， when you have experience。

 it does feel remarkably consistent and that is one of the nicer advantages here。

If we also have moviegoer has many reviews， can we use Mogoer Reviews Pa？All right。

 so that's pretty close to where we are okay， got to 38 seems to be the number today。Couple E's。

 so that makes sense， but some good disagreement between A and B， so take a minute。

 talk with a partner and then let's re。这样子。错系。也是。看到。嗰啲位先。嘢啦。All right， take another 30 seconds。Yeah。

Perfect。YeahOkay。同我嘅时。All right， give it another 10 seconds or so。关佢。Can we get above 30？We got 230。

 can we get above 30？Okay， we got above 40。Cool。Looks remarkably similar to last time。

 most people settled on B and B is the correct answer。😊，You might argue that it should work。

 It does say the word should there。 So there's there's room to argue with the answer option。

 The reason that this doesn't work automatically is。The paths that rails sets up。

Are based solely on the routes do RB file。 So if we have a has many relationship。

 if we have our belongs to relationships， we would have to set those up in both places and。

It is perfectly okay to say a movieer， resource moviegoer do resource reviews and have nested routes in two places。

YouIf this makes sense for your application you where you're going to have。

Two different ways of accessing the same data， then you might want to specify two different ways of getting at that data from the user interface because。

If you're going to have a moviegoer reviews path where you list all the reviews by that moviegoer。嗯。

Then you'll want to have access to that information。

 you'll want to have those routes that structure defined for you。

 especially if you're using things like rails generators where you are。You know。

 goinging to have rails for the first pass help you out and generate some of those views。

 it can be really handy to。You know to have those functions available that。诶。

That would give you the data that you want。That is that is an option。 I will say that so。

D is not correct because you can do it， it can be confusing to overuse nested routes in multiple places in your own when when you nest reviews under multiple resources。

 then in your controllers you'll have access potentially to multiple different kinds of parameters。

 so it is possible but you don't want to overuse it。😡，And there so routes， nesting things。

 questions on that so far。So again， this is one of those things that takes a lot of practice to figure out what the right structure for your application is。

So it's something， especially if you're starting a new application。

 new applications have the advantage that they don't yet have any user data that is important and critical and while you're testing things。

 you don't want to spend your entire semester fiddling with your data model because then you'll never be productive but until that application is deployed in production。

 you have the freedom to tweak your routes your model relationship so。

If you feel the need to do that。Go ahead and do that because chances are code that gets refactored can be improved。

Tools and techniques for understanding， visualizing the relationships that we have。UML。

 the universal modeling language， is a way of diagramming the relationships in object oriented systems。

 and what we have is essentially boxes that represent the entities of our application and some ways of using arrows and other cryptic symbols to describe what those relationships mean。

 so in this case，We have a car， which is a subclass of a vehicle。

 so this little open arrow in this case represents an inheritance relationship。

Model car inherits from vehicle might be something that we see in a rails application。😊。

And then we have a closed arrow which represents components。

 so an engine is a component of a car that is a component of a car。

 this lists some methods that it might do start and stop your engine。

We could list more methods and properties in these diagrams。

 but it can get a little bit unwieldy so method there could be methods and things here this very simple one they've been omitted。

 but these open and close arrows denote differences in those relationships。

 so here is a slightly more complicated UL diagram。The style is a little bit different。

 but it represents。Essentially the same thing， so at the center of this we have a voucher。

 we have some items， we have types of vouchers。And they have a few more symbols。

 so we still have our open and closed arrows， so we can still say that a voucher inherits from an item。

We have it's。Hard to see in this example and they're not showing up really well。

 but this is an open arrow which I don't know why it's not showing up very well or excuse me an open diamond。

Which means that a child can exist independently of its parent。

 so we could have this account code which exists independently of an item and we could have a closed diamond which says that this thing can't survive without that relationship so an item cannot survive without the relationship of a customer we're not going to quiz you on the specifics of these arrows because they're easy to forget until you like read a ton of UML diagrams which you probably will not be doing in this course。

 they're easy to forget。But they are useful in that they help express specific relationships。

The other really useful thing is at the end of these arrows they have。0。

 star or one which specifies whether or not there can be zero or more of these things or whether there can only be one so we can have let's see and。

An item can have only one customer。But a customer can have zero or more items associated with it。

This。The numbers here express the amount and the quantity of the relationships that exist。

 If you're working on a legacy app， there's a link here to a gem called Rails ERD so another term for UML diagrams is entity relationship diagrams which I think is a more descriptive name because we have entities and the relationship between them you can run so if you add rails ERD to your gem file the Github repo gives you the exact rake test to run。

 but the really cool thing is that it outputs a diagram for the exact application that you're looking at so if you're taking over an existing application and you're open up and your first question is what the heck is going on here。

 which is say valid first question to ask when you get to any new application。😊。

Oh but creating a UML diagram， an ERD diagram of the models and the relationships can really be a useful way of understanding that application。

 even if you don't want to worry about the specifics of what the arrows mean what，You。

 a UML diagram for for a mature application will tell you is the models that have lots of arrows going in and out of them are probably the important pieces of your application。

 so if you're working on you know。An educational app and you have an assignment and you see that there's like lots of arrows going in and out of this assignment thing that tells you that that's probably an important and critical piece of the application that you're working on and that might be a place to start exploring。

😊，They do have cryptic syntax， so again， the goal is not to necessarily memorize all the syntax。

 but to recognize that these things are a tool。That can be a good way to start exploring what an application does that help you remember how things work。

 and again， depending on the structure or the tool that you're using。

 you may list some of the most important methods or properties of these items within each box。

 or you may leave some of them out depending on what you want to do as well。

You can also take this to the extreme and there are tons of different ways of formatting this。

This is an example where。This is a lot of data modeling that's going on for an application。

 it takes a while to read and go through the salt， but we can see this still has arrows。

 describes the inheritance relationships， but that's Oop taken to。To another level。

That is a tool that you can use， but the Rails ERD gem is a really useful thing， for the most part。

 add it to your gem file， bundle install and run the command and you get some nice visual output for understanding your application。

So the other question is， ERD diagrams help us understand the models。

 the relationships that we know exist。The question is。

 how do we know which models and relationships to build， what things？Should work together。

This is a technique called class Reibility collaborator so these cards take in an object or not really take in。

 they describe an object so we have for this application which deals with movie showings。

 we have a showing， we have a ticket， we have orders。

And we list the responsibilities that that object has and what other models in our application they need to collaborate with。

嗯。If we have an order， we can say the order needs to compute its price so whatever data the order has。

 maybe it has a particular time of day， so a mat A versus a night time showing will have different prices so maybe the order needs to know how to sum things up。

诶。That may be a thing that it just knows how to do on its own。

 but we can also see that it knows how many tickets belong to an order。So。An order。

 if it needs to know how many tickets belong to it， it will need to collaborate with our ticket。

A model or class。 an order might also know its owner。 So this is not modeled here。

 but we could assume that there's some person or some user that might exist in this application。

 So the owner collaborates with the the person。 So all we're really doing here is。We're saying。

 what are the things that this object needs to do， Those are its responsibilities。

 What are the models， the， the classes that。It needs to collaborate with that it would need to have some defined relationship to those go in the collaborators's column and these really simple cards are a way of deciding how should we model our data。

 what relationships should we describe as has one belongs to and so on so a really useful trick for deciding if you're trying to figure out what do we need to model。

 how should we model it。Is。To go through and look at our user story。

 so you've hopefully all had a chance to meet with a customer， you've hopefully written down。

Some user stories。And you know。We have some scenarios here that would actually test them。

 but we're just going to start with the basic feature at the top。

 so adding movie tickets to a shopping cart as a patron so that I can attend a showing of a movie。

I went to add tickets to my order。So what are the nouns？In here we have patrons， we have showings。

 movies， tickets， orders。We didn't show our patrons or person class here， but we have showings。

 tickets， orders， you can assume somewhere that we have a movie in our application and those are the pieces that you can put together to build these cards so that's really the goal here is it's just one technique of going through and helping you understand how to model that data and。

With that， I think you have everything that you need to start modeling data in your own applications。

 but again， it'll take some practice， so give it a try， mess up once or twice。

 try again all perfectly normal things。And we'll see you Tuesday。



![](img/0b01a30501fea891eb38872f66d2ae79_17.png)