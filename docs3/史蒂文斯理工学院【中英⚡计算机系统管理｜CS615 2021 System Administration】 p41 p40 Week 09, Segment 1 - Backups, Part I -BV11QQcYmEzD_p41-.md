# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p41 p40 Week 09, Segment 1 - Backups, Part I -BV11QQcYmEzD_p41-

Hello and welcome back to CS615 System Administration。This is week 9， segment 1。

 And I think it's high time that we talk about a topic that makes every su nervous because they don't quite know whether they're prepared。

 And I mean， really prepared for when disaster strikes backups。

When was the last time you backed up your data， when was the last time you verified that you could restore your data？

I know I scared you just now， didn't I。Go ahead， verify your back up。 then come back here。 I'll wait。

All good。 Your backups are working。 All right， good。 So where were we， Yes。

 I was going to tell you that in the next few segments we'll discuss the topics of backup ups in some detail beginning with this video。

 where we cover the general concepts and talk about basic principles。

In the following videos were then illustrate by example a few common backup strategies and tools。

 including file systems snapshots and related considerations。But don't drop off the video just yet。

 I know。 I know Back ups are boring。 It's like brushing the teeth or washing your hands or wearing a mask。

It's tedious。 You have to remember to do it。 You have to build up a habit。

 and you can't stop doing it just because， well， you know， it's been a while。

 You no longer feel like it。I know。 I know。 Nobody likes backups。 Nobody gets excited about backups。

But you know what people do like what they get really excited about。

People love to be able to restore data that they thought they had lost。 People love restores。

 love them。 They go nuts about them。Have you ever accidentally deleted a file and then remember that you had a backup copy of it somewhere。

 And isn't that just the best。So yeah， people really do love resource just as much as they find backups boring。

And so it's important to approach the topic of backups not as something that's an objective in and of itself。

 but rather as a means to an end。Nobody cares about backups because backups are not what you want。

 what you want is the ability to recover lost data to be able to restore data。

And backups are just a way to enable this capability。So keeping this primary objective in mind。

Let's take a look at some of the core concepts， some terminology。

 and some broad considerations on the topic， I'm sure you've heard many of the terms we' be using here before。

 but it's worth clarifying what we're talking about before we dig in deeper。For starters。

 they are different types of backups， starting with the most obvious。 The full backup。

 This is pretty much what most people think of when they hear the term back up。

 a complete copy of all the data。But there are also incremental backups。

 That is a backup that only copied the data that has changed since the last time a backup was performed。

 as well as so called differential backups， which are quite similar to incremental backups。

 but define that here we take up only data that has changed since the last full backup。

 We'll see the distinction of these three types in a minute。

But we also have to talk about how we're backing up data。

Whether we are copying individual files or whether we are performing a copy of the raw disk blocks。

 whether and to what extent we care about file metada of both the file and the file system。

The distinction to the file data and how we may handle， for example。

 open files or data that is written to while we perform a backup。

This circles back in many ways to the fundamentals of fire system that we covered earlier on in week  three。

And then brushes upon the distinction between journaling file systems and data replication on the one hand。

 and file system snapshots， for example， On the other。

 as both can be viewed as a form of protecting against data loss。

 even if that may not necessarily serve as a traditional backup strategy。

We'll see the use of5 system snapshots in a later video， by example。

We'll also talk about extremely businessy terms relating to disaster recovery and having a business continuity plan with a defined recovery point objective or RPpoO。

 as well as a recovery time objective or RTO。I no， this all sounds terribly boring。

 but as often these fancy terms translate into very simple terms。

A recovery point objective really is just the fault tolerance window you are willing to accept。 or。

 in other words， how far back you have to go to get back your data。So for example。

 if you perform backups every night at midnight and you lose some data at 8am。

 then obviously you can at best get back the data from the previous night's backup。Likewise。

 if you lose data at 11，59 PM， you still only can get back the data from the previous nights back up。

So your recovery point objective here would be 24 hours。

 You are aiming to be able to restore data from 24 hours ago。If your RPO was say 10 minutes。

 or then you'd have to run backups every 10 minutes。

Your recovery time objective then is how long it takes you to restore the data。

 since that is not usually instantaneous， and the type of becca performed may play a role。

So let's go ahead and take a look at the three main strategies。



![](img/c1a3d45c1cfb3dc567a9cea310cf68cb_1.png)

First， there's the simplest and most obvious approach to backups。

 You perform a full copy of all the data at regular intervals。So， for example， we start out。

Backing up data on Sunday and copy all the data we have。 save 7  TB。 Then the next day。

 you simply do the same thing and create a second copy of all of the 7  TB you have there。



![](img/c1a3d45c1cfb3dc567a9cea310cf68cb_3.png)

And then you repeat this regularly， creating full copies of all of the data every day。

 so that after one week， you have backed up 49 ters of data。



![](img/c1a3d45c1cfb3dc567a9cea310cf68cb_5.png)

That's a lot of data， but it sure makes restore easy because all you have to do。



![](img/c1a3d45c1cfb3dc567a9cea310cf68cb_7.png)

Let's go and fetch the latest full data dump。 And there you go back in business。

So the full backup strategy here。Has a drawback that it' obviously slow。

 It takes time to copy 7  TB of data every night。 And， of course。

 you then need to actually shovel all the data around and store it somewhere。 But on the bright side。

 recovering from the data loss is easy。Now let's compare this to a differential backup。In this model。

 we change what we make up each night， but of course， at some point。

 we want to start with a single full backup。Then the next day。

We only back up whatever data has changed since the last full backup ha and Sunday。

 So let's assume here that this is the data that's changed。 So we copy two  TBytes。The next day。

 let's pretend that only the orange data blocks had changed。So we then back up those blocks。

 but also the ones that had changed the day before。

 since we are only comparing data sets against the last complete backup。The next day。

 let's pretend the green data blocks changed， so we add those to what we back up。The next day。

 let's say nothing you changed。 But since our promise is to back up everything that changed since our last full backup。

 we again copy the same data。And if data then changes the next day。

 we copy that and that on Saturday。So while we didn't have to copy 49 terabytes of data as in the full backups everyday model。

 we brought the total data down to 31 terabytes。

![](img/c1a3d45c1cfb3dc567a9cea310cf68cb_9.png)

Now if we want to restore data。We need to combine only two data sets。

 the data from the original full backup and then overlay the data from the last differential。

 since that includes all the changes since the last backup。



![](img/c1a3d45c1cfb3dc567a9cea310cf68cb_11.png)

So this approach improves the backup performance and stores utilization。

 but makes the recovery a little bit slower than from a full backup since we have to overlay data from the second set。

On the other hand， regardless of what data was lost， we always only required most two data sets。

 the last full and the last differential。

![](img/c1a3d45c1cfb3dc567a9cea310cf68cb_13.png)

So that's not too bad。 Now， let's compare this to the incremental backup strategy。

This model will initially seem almost identical to the differential approach Since here too we don't copy all the data but only well incremental changes。

So after our initial for backup on Sunday， we might then back up the same block as on the differential model on Monday。

But now on Tuesday， we'll see a difference。 If， again。

 we assume that there were changes only in the orange blocks， then in the incremental model。

 we will only back up just those blocks on Tuesday。 and similarly。

 with only changes in the green blocks happening， we then only back up those blocks。Now。

 if no data changes at all on Wednesday， then we won't pack up any new data。

And on Friday would only back up what's changed then。Just like on Saturday。

So it should be obvious that in this model we are backing up significantly less data。

Only the data that has changed since the previous incremental backup。

 So the total in our example here adds up to only 13 terys。 So that's pretty neat。

what does this mean when we want to restore in this model， and we want to restore data？

We have to start with a full backup from Sunday， then overlay the data from Monday。

Then that from Tuesday。Then that from Wednesday。Friday。And finally， Saturday。

So the difference to the previous two approaches then is that in this case。

 we maximize the backup performance and storage needs。

 as we really only copy the minimum amount of data。

 but that comes with a penalty of a much more complex restore process。

And note that this is also somewhat increases the probability of a failed restore。

 as our complete restore now depends on the full chain of all previous backups。Once again。

 there is no free lunch and there is no simple correct solution。

 but it's important to understand these different approaches。

But not only do we need to think about how we're backing up data。

 we also need to think about where we're backing up the data too。So let's talk about storage media。

Now， obviously， this goes back in many ways to our week two videos in some ways。

 but let's quickly jot down the different storage media we might use and this properties that are relevant to us in this context。

So first we have magnetic tape， the original data medium。

 and you may be surprised to find still a dominant storage medium for backups using large robotic tape libraries and enterprise environments。

But of course， just like we can use hard disk for data access by systems using say storage area networks。

 so can we use them for data backup purposes？Just like we could use solid state drive backed storage networks。

 And so you see how this closely tracks what we already discussed in week 2。

 And just as we mentioned then， you can， of course， also store your data in the cloud， Why not。

Then how do we pick the right solution here， Of course， the properties of these are different。

 But which ones matter and how do they matter in comparison to when considering any type of storage media。

One obvious factor is， of course， IO performance。For your backup destination。

 you probably want a highly performance solution， although you probably want to optimize sequential xes of large objects since the backup operation generally does not randomly write a few byte C and then a few bytes somewhere else。

You want to focus on reusability and longevity of the storage medium。

 you probably want to be able to store your data there for a long time。

 and you may even consider using a medium that allows writing the data once。

 but that does not allow you to override it。DVds or ridriable Cs are examples here， but of course。

 those are pretty terrible storage devices as they degrade quickly。

 but enterprisepri Kves also nowadays offer right ones read many solutions back by solid state storage。

In addition to this sort of protection of your data。

 you may also consider adding compression or encryption of the data right in the storage solution。

Or evaluate options to save space via data de duplication。

All of those are factors to consider when looking for storage solutions for your backups。

 and I think you will note that these are somewhat different from those you might consider when choosing storage media for your live file systems。

Another factor that comes into play is what the purpose of the backup is。 And now。

 we already said the purpose of a backup is to be able to restore data。

 But within that larger objective， they are still at these two distinct use cases。

We have long term storage or archival， and we have the rapid recovery from data loss。

These two use cases are notably different and will require you to determine separate solutions。

The first long term storage is something that you likely want as part of a disaster recovery plan。

 or perhaps as part of certain restrictions or requirements mend it by your business or even the Government。

Consider， for example， operating data systems for any public office with a mandate to preserve communications and records or a newspaper archive。

 for example， here， long term storage really means long term on the order of not years， but decades。

This then has a number of implications。For starters you need a complete backup。

 any incremental backups do not help you here， so youll probably want to make sure to keep these separate from your regular ongoing backups。

What's more， you'll likely want to keep this data in a separate location from your normal operations。

And accessing such data stores then may incur performance costs since you may have to physically travel or otherwise suffer a layer retrieval penalties。

By doing full backups for long term storage， you will also most likely only have cost granularity。

 You can store all the data for long term storage every minute。

 but probably need to take snapshots in time every month or so。

And then if you are thinking long term storage， really do think long term storage。

 which means you have to consider what medium is suitable for storage of data for decades and how will you get to the data？

Suppose you took a long term archival snapshot in the year 2000。

 and you start the data magnetic tape and then shipped it to a storage facility somewhere。Now。

 over 20 years later， you want to access the data。Do you still have a tape library that can read the tapes。

 Do you have the right cables to connect this library to your 2021 laptop。

 I'm quite sure that T library doesn't have a USBC connector。Similarly， if you encrypted the data。

 make sure you also are able to decrypt the data 10， 15 years later。

 who has access to the decryption T？How did you store that？

So you see that this archival of data for the long term brings with it a whole bunch of considerations that do not even come directly into play when talking about regular backups。

 which we generally think of as protecting against sudden data loss。

And even that is not a uniform case， and different causes for data loss may lead you to develop different protection mechanisms。

For example， if you want to protect your users from themselves。

Then the way to consider data restoration is by and large on an individual file level。Similarly。

 software bugs that lead to data being deleted， overwritten or otherwise lost also require granular file level restoration。

While hardware failure， such as a head crash on a hard drive or other physical failure。

 tends to lead to all the data on the drive to be lost。Hence， requiring recovery of the whole system。

 not individual filess。This is similar to how security breach generally leads you to having to reconstruct the whole system since you can't trust the individual tools or files any longer。

But you also have to prepare for even bigger events which will eventually hit you。Natural disasters。

 for example， I'm sure many of you may remember Hurricane Sandy a few years ago。

 which really did a number on all the enterprises with data centres and hosting located in lower Manhattan。

So in cases like this， where you lose all your data。

At least all your data in one admittedly large geographic region。

You are going beyond the general concept of backups and towards disaster recovery with data application across diverse environments and providers。

 again， intersecting more with the requirements of long term storage and archival。Now。

 all of this is， as usual， a topic much too broad to be covered here。

 but the concept of a business continuity plan or BP。

 all of a sudden doesn't seem quite so boring any longer when you prepare for the worst outcomes。

In a way， you have to treat your backup strategy like insurance。 Yes， it's boring。 It's annoying。

 and it costs you a lot of money。 And the weird thing is， you really。

 really hope you will never need it。But you do sleep a lot better knowing you have it。

So let's at least think about recovery from a system failure for just a moment since we look at more granular recovery from individual data loss and on next video。

A system or hardware failure will in all likelihood lead to the loss of the entire system。

 which then also generally leads to at least some downtime。

Now obviously you should have your systems and services structures such that there's no single point of failure and any given system is replaceable。

But you still need to take down the system with a failure to recover。Now， under some circumstances。

 you may have already have some protections in place。 Ra， as we discussed in week 2。

 can provide some protection against individual hydr dryophilia， for example。

 and allow you to recover without downtime。 But if your system has indeed failed completely。

 then the recovery will take at least some time as you have to rebuild the whole system。

Depending on your backup schedule， this may then even require you to retrieve the last complete backup from some archival storage。

 and in some cases， at least some data loss may be unavoidable。

The best rule of thumb to protect against data loss year is to follow the 32 one rule。

 which requires that you keep at least three copies of your data。

On at least two different storage media。With at least one copy at an offside location。

With this approach， you are minimizing the different failure options。

But do make sure that you are preparing for the applicable disasters。

 Offite can mean a different office on the other side of town。

 or it can mean a different data centre on the other side of the country。

In the case of large natural disasters， the latter can help you when the former could not。

 although that， of course， also depends on the size of the country we are talking about。

But let's say that you did deploy your best backup strategy following all advice。

 You still have a few more things to worry about。The integrity and correctness of your backups。

 as well as the tools you use to perform the backups。 Because， hey， guess what？

 If you want to back up all your data， the tools and processes that do this need to have access to all your data。

And there have been attacks on backup software and other solutions that LED to data compromises。

Which is a problem because if you， for example， manage to get some malware deployed on my system and I then perform a backup。

 I am backing up your malware。 And if I later restore from that backup， I may play back your malware。

So it's important to keep in mind that the data you have on your backups is only as trustworthy as the data that you copied initially。

Similarly， to restore data from a backup， you have to use only trusted tools if you suffered a security breach and you believe your system is compromised。

 then you can't use the tools on that system to restore data。

 even if you know that data your backup is correct。So all in all， it's actually pretty important。

 but not often consider aspect of your data backup strategy to regularly verify the authenticity and integrity of your backups。

😊，That is regularly try to restore random sampling of your data sets from your backup。

This will verify that A， you have the tools to do that。B， know how to do it。 C， can actually do it。

 And D， that your backups are actually worth anything at all。If you can restore data。

 your backups are pointless， worthless， and a waste of your time and resources。

And with these wise words， and hopefully， having scared you a little bit into checking and validating your own backups。

 we can take a short break here。In our next video， we'll take a more practical look at some of the tools we use for individual backups on the file level。

I recommend that you try out the exercise linked here to get an idea how to use these tools and to get you thinking a bit more about performing backups。

We'll talk more about the outcomes and objective of this exercise in the next video。For now。

 go ahead and check your own backups， make sure you can restore data from them。

You do have backups of all your systems， don't you， I thought so。See you next time， G。



![](img/c1a3d45c1cfb3dc567a9cea310cf68cb_15.png)