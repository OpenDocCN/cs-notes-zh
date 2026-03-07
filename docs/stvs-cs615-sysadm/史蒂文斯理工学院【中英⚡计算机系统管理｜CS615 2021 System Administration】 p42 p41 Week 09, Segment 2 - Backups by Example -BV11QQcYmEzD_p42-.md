# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p42 p41 Week 09, Segment 2 - Backups by Example -BV11QQcYmEzD_p42-

Hello and welcome back to CS615 System Administration。 This is week 9， segmentund2。In the last video。

 we talked about core concepts in the larger topic of backups。

 things like full versus incremental backups， storage media and their properties。

 and the difference between long term archival backups and routine backups for data recovery。

As discussed there， the recovery from a disaster or systemic failure may have specific practical implications。

 But even for individual file recovery， we need to pay attention to a few details that will then define our overall backup strategy。

Specifically， we want to provide to our user some guarantees a deleted files should be able to be restored within a given time window。

From a pure usability point of view， users may expect the ability to undo changes and the normal behavior of the Uni tools to do exactly what is asked of them may at times confuse or frustrate users。

RM well， removes a file and doesn't， for example， move it into a special directory。

 So there is no inherent undo on the file system level here。So instead。

 we have to find a way to agree with our users what a realistic recovery point objective is。 That is。

 we define the time of window of data loss or the other way around the granularity of our backups。

We might for example， say that we perform nightly backups。

 meaning we can only restore data from an average around 12 hours ago， 24 hours ago worst case。

But once data is lost， getting it back is not usually instantaneous。

 even if it falls within the recovery point objective。

Which is why we have to define a recovery time objective， the time it takes to get back your files。

This will include staff availability and their overhead for example。

 if you have to fill out a support ticket to request a file restorestore then somebody has to get around to reading that ticket and then have time to act on it。

But it's also possible that if your T library is currently busy writing the backup of the current data set to tape。

 it can restore your data。This will be less of a concern in large scale enterprises。

 where hopefully you have multiple means of accessing the backup， but in smaller environments。

 this may be an actual concern。And， of course， retrieving data will actually take some time， too。

 if you lost one fire， but it's on a magnetic tape with a 20 teraby backup。

 you may have to go through several hundred gigte of data before you get your file back。Likewise。

 if you lost 20 terabytes of data， restoring those will necessarily take time。

 restricted by the tape performance and the IO speed the device you're restoring the data too has。

Now all of this makes restoring data a lengthy and cumbersome process。

 which is why it'd be even better if you could set up your backup system such as it allows for self service restorestore。

 where any user connects with the backups of their data themselves， but this isn't easy to implement。

 particularly at scale。We'll see some methods that help in this regard our next video， though。

Finally， it's worth mentioning that backups also have a surprise side effect。

Data that was deleted now is still available somewhere。And in some cases， that can be a problem。

 Sometimes when you delete data， you really want to make sure that it's gone and cannot be restored。



![](img/46a2156f493551f6301eb42707ef6450_1.png)

But let us look at a few practical examples。 One of the tools we'll use here is one that you've used already on a regular basis when you've submitted your homework assignments。

 the tarum a。

![](img/46a2156f493551f6301eb42707ef6450_3.png)

So let's have a look。Tar is a tape Archr and one of the Uni tools supporting a rather surprising number of command line options。

Some of which don't even need a dash。This is in part why tarar is often cited as an example of arcane Unix's wizardry。

 but it really is not all that complicated。 T is an old tool。 And back in the early days of Unix。

 many tools did not require a dash to specify options。



![](img/46a2156f493551f6301eb42707ef6450_5.png)

The overall use of tar really boils down to just a handful of commands。

 so I'm sure you'd be able to dism this bomb without a problem。But anyway。

TAR is a tool to create an archive of a file system hierarchy。

And generally was used to ride it to magnetic tape with a default device of。Deaf R S T 0。

So let's see how we can use TR for backup purposes。

Here is an easy two instance with a second volume attached。 So let's create a new file system on it。

And mounted under slash backup。Now let's create a directory time stamped after the current date。

There。Now we can back up our user local directory using TR by creating an archive and writing it into the file system。

There we go。So now we have our copy here on the extra disc。Whi is all nice and well。But。

Our backup disk is still local to this system。That is we really only have created a copy on another disc on the same system。

But since tar can write data with standard out， we can simply pipe it into any command。

And so we can simply write the data to a remote system instead。But of course。

 there's nothing that requires us to write the data back to a file system。

Recad that Ta is designed to create an archive， a file in a specific format。

So we can write this data directly to a block device instead of extracting it into a file system。

 as we did in the previous example。For that， we can use our old friend， the D D command。So now。

 checking in over here on the remote backup destination。

We can read the data back from the block device。And find。Let。Yep。

 we did get the archive written to disk here。So， now。Back on our original server。

If we accidentally deleted the data from this directory。We can restore it from our backup。

 on the remote system。Using this command。And there we are。

By using tarR and writing the data into a pipe。We can gain additional features too。For example。

 we can compress the data before we write it to the remote site。Like so。

But we can also add other data transformations。 For example。

 we can encrypt the data before we send it over。Illustrated here using the Open SSL En command。Now。

 to restore the data， we simply reverse the steps。First decrypt。Then， decompress。

Then rides to the file system。There we go。So that's pretty useful and the nice illustration of the flexibility of tarR is more than just a tool to submit your homeworks。

But to create backups， we have a few other tools。 One of the oldest tools here is the D command。

The D command is used to perform file system backups， and unlike T。

 it has some logic to determine which things it should back up。



![](img/46a2156f493551f6301eb42707ef6450_7.png)

Dump also distinguishes between what we discussed earlier， full or level 0 backups。

And incremental backups， meaning it can be used to only back up data that has changed since the last backup。

This time， we're writing data to a file on the file system on the remote host。

By piping the output of the dumb command into SS H and cat。

The dumb command will take a few minutes as it determines which files need to be backed up。

All of them in those iterations into performing a level 0 or full back up。

And then write the data over the network to the remote file。Now。

 D then keeps a log of which level backup it performed by writing to Etsy D dates。



![](img/46a2156f493551f6301eb42707ef6450_9.png)

Which specifies the disc。The backup level and the date， as shown here。On the remote system。

We find the complete level 0 backup file。Which tells us when this was written。

When the last time a full backup was performed。Here the epoch， since we never performed a backup。

As well as some other information。So now that we've done a full backup。



![](img/46a2156f493551f6301eb42707ef6450_11.png)

Let's see what an incremental looks like。

![](img/46a2156f493551f6301eb42707ef6450_13.png)

For that， we create a bit of new data by extracting our group project Git repository into user Local。



![](img/46a2156f493551f6301eb42707ef6450_15.png)

Now， let's run D again。This time， as an incremental。And writing the data to a second file。

Now note how our backup completed much faster than before。

 since it only had to copy the files that have changed since the last full backup。

And on the remote destination。The backup file is， of course， much smaller than the level 0 dumb file。



![](img/46a2156f493551f6301eb42707ef6450_17.png)

On our server， E dump date was updated to reflect the incremental backup。So now。

Let's simulate some data loss by removing a few files。No， no。Well， those fire are gone。Now what。Well。

 let's rest the data from our last backup。We do that using the restore command。

 asking it to extract the files for user local from the last incremental backup。Here we go。

The command tells us from when the data was。And then writes it into our file system。There we go。

 Data back。But we also had removed the E C RRC dot D directory。Let's try to restore that。

 that didn't work out。Etsy RC D was not found on the back in question。

 which is no surprise since the incremental only copied files that had been changed since the last level 0。

 but Etsy RRC D hadn't changed。So let's look at the full backup。For this。

 we copy the file over here so we can interactively inspect it。

Now we can run restore in interactive mode。Which drops us into a shell like prompt。

The information about the backup can be displayed like this。

 as the restore command provides a few simple commands for us to interact with the backup。

We can list the contents of the backup using the Ls command。Change into the directory。

 and inspect its contents。And then select individual files or directories to restore。



![](img/46a2156f493551f6301eb42707ef6450_19.png)

Then， we can extract the data。Set the permissions。And there we go。



![](img/46a2156f493551f6301eb42707ef6450_21.png)

Our last data has been restored， yea。So the D command supports incremental backups natively and restore letters select what data to recover。

 This is a bit different from our earlier example of using tar。

 but is there way to use other tools in a similar manner。Let's try again using TR。

 as we showed before， backing up the data from a directory is easy enough。



![](img/46a2156f493551f6301eb42707ef6450_23.png)

But。If we create new data here。And then， run the backup command again。

We are again copying all the data。 No incremental here。But what if， instead of using tar。

 we use a different tool。The arsing command allows us to sync a directory hierarchy to another location。

So let me run that。You'll note that even though it lists all the directories。

It does not actually copy all the files again， but instead， only the newly modified files。

So we can effectively perform incremental backups， although in this case。

 the incremental is directly applied to the remote destination and not kept as a separate Delta。

 as in the case of dump。

![](img/46a2156f493551f6301eb42707ef6450_25.png)

![](img/46a2156f493551f6301eb42707ef6450_26.png)

But now note that we have yet another use case。 Not only do we want to keep track of what files we have。

But we may also sometimes wish to ensure that a file that we have deleted on our file system is removed from the other side。

And while D is great at creating incremental backups。

 the incrementals really only contain the data of files that have changed。

 but no notess about which files have been removed。So。When we remove some files here。

And then run the arsing backup。 This behaves just like dump。

 and that the locally deleted files remain present on the remote side。



![](img/46a2156f493551f6301eb42707ef6450_28.png)

But ourcing has another option to ensure that we also sync file deletions。The dash dash delete flag。



![](img/46a2156f493551f6301eb42707ef6450_30.png)

With that， we were removing the files in the remote site when they have disappeared locally。

 And this is useful as it provides a functionality that our dump tool did not offer。

But now we have another problem。 How do we roll back changes made locally if we later add the files again。

We won't be able to get back to the earliest stage where they were gone。

Wouldn't it be useful to instead of only focusing on files added or removed to have a better way。

 a method to say， show me what file system looked like at the given time。



![](img/46a2156f493551f6301eb42707ef6450_32.png)

Well， we do have ways to do that， but I'm afraid you'll have to wait until the next video to discover how those work。

For today， we'll take a break and review a real quick what we've covered。

We've seen how tar can be used to create an archive of a P system hierarchy。

And how we can do a number of things with the data created in this way beyond writing it to a file。

We can write it to a raw disk device using D D， copy it to a remote system via SS S H and transform the data in the process。

 for example， compressed and encrypted。But as we've just shown in the last example。

 using TR implies the full backup as there is no support for incremental backups in TR。Now， a dump。

 on the other hand， does support incremental backups and integrates with a system more tightly that the F step contains a field to help dump decide which file systems need to be backed up and that the dump dates keeps track of the last time of backup and so on。

To get back the data backed up in this fashion， you can use restorestore either to restore all the data。

 some of the data or to interactively browse the backup。

And then we looked at our sync to show how it can incrementally back up data and unlike D。

 how it can even delete data from the data set。But we also mentioned that we are still missing out on some functionality that we'd like to be able to roll back time and browse the file system effectively as it was at a specific point in time。

How to do that will then be the topic of our next video。So until the next time， thanks for watching。

Geus。

![](img/46a2156f493551f6301eb42707ef6450_34.png)