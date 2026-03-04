# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P106：5_第一代云计算应用（第一部分）.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So I want to talk about the great disruption that led to in a sense the NoSQL movement and started changing database architectures forever。

 so prior to this， let's just pick 2002 you know everybody had their own relational database everybody bought a $40。

000 computer if you had a big school like the University of Michigan everybody bought a $40。

000 computer and ran your database for your HR on a 40000 computer ran your database for your mail on a $40。

000 computer and just vertically scaled it and it worked because the software worked in this environment。

 the hardware worked in this environment， it was not cheap to do it but it was something we needed to do in a away we go and so again。

 a lot of what I'll call pseudocloud vendors used this as their technique and that is to just make a bunch of databases they put them all in Amazon and they put the application in front of them and then switched between databases and claimed we're cloud the answer is no we just collected all of the individual ones。

And put it together in one building or in a couple of buildings in the case of Amazon。

 so that's 2002。And what happened？Is Google so Google is going to search。

 they're going to write a database crawler and they're going to crawl the web and they're going to make a full copy of the web and they're index that full copy of the web and they're going to look at like connections between it。



![](img/a96f7f3b64d28cf2d20af523566e1a62_1.png)

Sounds like a perfect thing for a database because it's all about connections just like relational。

 right？And then of course you have Gmail that comes quick on the heels right 2009 and that is here's Gmail now Gmails are not just a read only thing well read mostly thing but Gmails read right we're going to log in and check our mail all the time and send a message and delete it and that and the other thing and so Gmail is very much like a typical application that would use a relational database going back to how universities were doing it in 2002。

 but it could not， it just couldn't Google was not going to give everybody their own domain even though these days they've changed that but we' let go back to 2009 everybody just use Gmail。

com。

![](img/a96f7f3b64d28cf2d20af523566e1a62_3.png)

One of the things that was nice about Google was that they really chose applications that didn't exactly need transactions。

 that that eventually consistency was fine。So think about Gmail， right。

 you got 100 million users and they're just logging in。

 but they're kind of logging into their own little data silos。Right。

 and so the eventual consistency wasn't that I'm going to delete a message from your mail。

 I couldn't do that， I could only delete messages from my own mail。

 and then I would send and receive mail， but that was just kind of this ever little mail sending thing and it was all nicely client server and so my little corner of the world would send your little corner of the world a message and then you know a couple seconds later。

 your corner of the world would see my message in vice versa and you'd reply。And so Google。

Worked in these cloud scale applications and it was a chicken and egg problem in that they wanted to build these really cool scalable cloud scale applications。

 and so they couldn't do certain things。 Now you'll notice in the early days of Google。

 they didn't have charging。Because then you like， do you really want any eventual consistency on an accounting system。

 I don't think so， you want to even know I build them or I didn't build them right you know。

 or you want to be able to like if the bill came and you got an email about the bill you want to be able to log in and see if what the bill was right。

 but oh it's an eventual consistency so the bill's not perfect yet。嗯。

And even writing to Gmail was widely distributed right， I mean， like I said。

 there's just these little pockets of data in the early days of Gmail they would migrate your data to a server that was closer to you like if you went to back home to Europe on a Christmas break the data would sort of creep over to servers that are there and your little island of data would just move around and then all of a sudden be really fast so there was this data migration。

 your little silo of data might follow you around the world as you travel。

And so the early Google applications were not Facebook， they were not Twitter。

 they were not connection oriented， they were just like here's a thing for you and whatever。

 and so these systems used cleverly name files， used hashing right you can hash an email address and that could be like a folder that has a bunch of files in it。

 then you take the folder names and you hash them and then you basically make it so that when you delete a file it just rewrites that folder a little bit right？

And they even could use little bits of relational database if they felt like it's something like SQL Li。

 which really reads and writes one file on disk。 it's not great for multireader multiwriter。

 but if there is one database for each user， then SQLite could be a good little database right So sharding is the idea of slicing a problem across a bunch of servers。

 and then you sort of have your particular view。 It's not like like a read replica where you could go to any of them。

 Now you had your email address and your data was on this one server， that's your shard。

 And so youve been you've been sharded So your data is not on all the servers， it's just on this one。

 and unlike the stuff I showed you before。 There's only one。 That's a shard。

And so I want you to watch a couple of videos， you can either watch these on YouTube。

 this is an hour long keynote， I've got a much shorter version of it that you can watch。

 this is Marissa Meyer。Google Ao 2008， I was actually in the audience when she was giving this talk。

 and I will tell you that。My mind was blown as she was talking。

 you know I go to a lot of conferences and I'm always sitting with my laptop in the conference and I'm like get some code done。

 yeah whatever they're going to say dumb things right I mean I'm enjoying it and I'll clap once and on the lift and then I'll go back to coding。

As she hit this part of the speech that I've cut out， my jaw has dropped。

And and and you're going to watch it here in， you know， 2020 or later and you'd be like。

 why was that so amazing and the answer was that。In 2008， Google， prior to this。

 this is the first Google IO conference， it's the GoogleDevelop Conference。

hich I encourage you to go to， they're kind of repetitive after you've gone to one or two of them。

 I've went only to two of them and stopped going because they're so repetitive。

Google from a developer perspective， just crap， they just come up with an idea and then they throw it away just like two years later。

 so Google is really not stable enough for me to like as a developer like Amazon。

I like Microsoft if you're kind of into that closed source kind of thing， but at Google just。

Someday I'll just go be president of Google and I'll just slap those people， I'm like， quit it。

 quit it。Sorry， sorry， sorry， that Mercimere， great keynote。

Google Io was like opening the covers to what had been for almost a decade at that point。

 completely the most secretive way of building fast systems。

 And I walked in thinking as a high performance computing person that thought that a million dollar computer was the way to solve the most problem And once she showed with this gather scatter technique and this is like。

 oh no， she has a bunch of thousand dollar computers and they go so much faster than my $1 million dollar computer。

 and she can add as many thousand dollars computers as she wants。 And I'm like， yeah。

 that's pretty dang and cool。 So so this it was revolutionary。 So please watch it。

 put your mind in the sense that this was to me the first time that Google was showing how it was able to do search cost effectively and not charge you for it because if I had a built search。



![](img/a96f7f3b64d28cf2d20af523566e1a62_5.png)

In 1997- 98， Adamta built it out of really expensive hardware and Google did not build it out of really expensive hardware。

A year later。They started showing some of their actual techniques for how they build virtualizable hardware。

And this is amazing again， before this time， I would see rumors about。

Google this is how Google does it， it was a big secret right and what happened was in 2000 it was a big secret by 2009 what people realized was with the energy crisis and all these concerns about the footprint of the energy costs of these systems。

And the fact that they would throw these things away after one or two years and so everybody's Google and Facebook and Twitter and Amazon。

 they realized that。For the greater good， they ought to share some of their best practices on how to do all these things efficiently。

And so they started having summits and so again， when I first saw this I'm like。Jaw drop， I'm like。

 that's their secret， holy mackerel， I can't believe it。 It's amazing。

 I would have never thought of it。 That is not how I would have built Google， not me。

 that's not how I would build it。

![](img/a96f7f3b64d28cf2d20af523566e1a62_7.png)

But then you watch it and you're go like of course， what a good idea right and again。

 acid and base are the essence of this and I was an acid kind of guy right and I was looking at this base world I'm like dang。

 that's really cool。😊，And then I also want you to see， and so you see this is 2010。

 so you see Googles kind of opening up their secrets to the world， how do these even search work？

So this is the Matt Cus mark 2010， it's a beautifully done production with animation and but it's also think of it from a acid versus base perspective of how they can use a distributed set of computers to go through the web to pull the web down to index the web and then to run searches。

 so I really want you to watch these three videos you can either watch the short versions that I provided or you can watch the long ones。

 the Marissa Meyer。

![](img/a96f7f3b64d28cf2d20af523566e1a62_9.png)

Is the only one where the long one is an hour and my short one is like three minutes and so you got to catch the part where she talks about how to do searching。

 but the Mac cuts one and the Google container tour those if you watch the long one。

 they're not that much longer than my succinct versions of them so please watch those and then come back and we'll talk a little bit more。

