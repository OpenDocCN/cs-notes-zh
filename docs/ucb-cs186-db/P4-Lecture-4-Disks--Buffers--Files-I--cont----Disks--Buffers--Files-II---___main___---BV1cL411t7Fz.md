# P4：Lecture 4 Disks, Buffers, Files I (cont) + Disks, Buffers, Files II - ___main___ - BV1cL411t7Fz

 of 186。 So just a few announcements to begin with。 So first of all。

 the second vitamin will be released today after lecture that will be due next Thursday。



![](img/b5a5b3b541b188bb8f3a47a75d4449fd_1.png)

 The first project will be due this Thursday。 I hope you guys are enjoying and having fun and writing good sequel queries。

 And there will also be a project office hour and also party tonight between seven to nine Pacific time。

 So the project party is actually something new that we are trying out on the on the TA website。

 It's actually something that we try to encourage you guys to work with each other and also try to find project partners。

 So hopefully that might work。 And if you guys have any feedback about that feature。

 just let us know as well because that's something that is relatively new。 And as you may know。

 we try to post weekly announcements on PS sub in the beginning of the weeks。

 just to tell you guys like， you know， keep track of things and like， you know。

 mentioned deadlines and so on and so forth。 So please make sure that you also check that out as well in addition to announcements during classes。

 Okay， so going back to the material。 So last week we were talking about。

 different components in a database management system。 Right。

 So we have this kind of layered approach where you see all these different。

 top going from top down parsing the input query all the way down to managing disc buffers in the file system for which the data is actually stored。

 So we started off by talking about the lower the lowest the most the lowest component in a database management system。

 basically talking about the disk。 And then last Thursday。

 I was talking about this kind of hierarchy that you guys may already be familiar with right so we go all the way from the fastest kind of。

 data retrieval mechanism by storing things in registers that are local to CPUs all the way down to this right and even like you to take right if you can't give you a kind of old fashioned right。

 So the difference between the time that it takes to retrieve data is tremendous right you can see that here everything from 0。

5 nanoseconds all the way down to like you know 20 milliseconds right so that's actually a lot of。

 substantial time difference between between these between different layers in the hierarchy。

 And then I also started mentioning about the different components of a disc which consists of platters and a simply of arms or otherwise known as these。

 arm assembly with disc heads and basically the disc has spin around as the platters go around it and then the area right or the or the circle that is basically marked by the by the disc has is basically known as the。

 cylinder。 Now each we basically talk about reading things from from in terms of sectors。

 So basically， as we spin to like a specific area that we want to read on the platter。

 Then basically lower down the disc head and then read data out underneath basically underneath that underneath the disc head and then the area that is the arc being swept right it's basically known as the sector。

 So if this is all like kind of sounding foreign to you。

 I mean one good analogy is actually the turntable which some of you may have already been really with right so in this analogy basically see that the vinyl disc right is our platter。

 This assembly is basically known also called the arm assembly and then you know and at the very tip of it right is basically the disc reading head。

 So it's actually this exact same thing that we have here。

 except that you can imagine now we basically growing 3D。

 So we have multiple layers of these platters right so that's what you see on the previous picture。

 So we again have the same set of platters we have the same setting， same armor， sample。

 same kind of disc head right except that in the in the old style right like you know we're talking about these vinyl records as opposed to。

 magnetic platters but the but the mechanism is pretty much the same so like how do we actually read right well we have to basically just like the turntable we have to basically spin。

 The arm assembly right to the right place move the head to the place that we actually want to read right and then lower the disc heads to basically touch the record。

 So the same thing also happens in the magnetic disc right so here。

 Basically we break it down to three different components in terms of the time that it takes to to read this block。

 First we have the sick time right as I said this is basically moving the arm right to the position where we actually want to read。

 Then we have the rotation of the layer because we basically need to wait for the platter to go to get to the sector that we actually want to read I mean just like in the vinyl record case right。

 And then finally the time that it takes to transfer data I once we lowered the disc reading head just like in good old fashioned turntables。

 Now the first the last part like you know in terms of transfer time we can't really control right because like you know we have to read the data off from the platter so that。

 We can't really control anything but the first two part here is what we would really try to minimize right because that's strictly overhead right we don't really need that in any possible。

 But then of course like things don't always work out that way。

 So these are the basic components that you need to know about magnetic disc when we talk about reading them。

 So how about flash right or solid this stripe right some of you already have probably like you saw this drive on your laptop for instance。

 So the technology is different here so first of all they are not organized into platters they actually organized into cells so one of them I highlighted here in red so that's basically a cell on a solid disc drive。

 And then with the current generation of technology using nandex。

 It's different in the sense that we can actually perform random reads and writes so we're not like the turntable thing where we have to wait for the platter to turn to the right place and then lower this cat and all that all that good stuff so that's actually gone。

 Except that the reads and writes actually at different granularity。

 So we can do really fine green weeds in terms of individual cells but then for writes it's actually preferable that we do like you know multiple cells at the same time。

 That's just like you know the background technology for solid this solid state drives。

 And another thing you need to know about this is that the route while the week is actually really fast because like again right we don't have to wait for the arm there's no arm assembly we're not moving anything。

 We're not waiting for things to be spinning around so that's great and it's also quite predictable right because we're just retrieving data from any of the cells and then all the cells basically have read。

 A mechanism attached to them already so we're not waiting for anything to be spinning。

 That's great but then right unfortunately actually it's not that predictable in terms of time。

 Why well it turns out that every single cell that we have on a solid state disc or flash drive actually can only be written。

 For its limited number of times the typical number that you get these days is around like 3000 times for instance before they would just fail。

 Fail in a sense of like not being able to erase it right because if we want to write it write something to it we first have to erase whatever that is on there and then like you know write the new values right。

 So turns out that like you know that is we can't do that infinitely we can only do that for a finite number of times。

 So when a cell actually dies right or like you know cannot be raised anymore。

 Then we actually need to find another cell that is available to write the data to。

 So that is a process known as we're leveling and just because of the fact that we can predict you know which cell is going to fail right so when we try to write a bunch of data we might actually ended up like you're jumping around。

 Quite a few cells before actually finding places for them。

 So that's why like right times actually it's not that predictable in general for solid for flash drives。

 Any questions so far。 I have a question。 Yeah。 So does that mean that solid state drives have like a very low lifespan then because I'm guessing between two and three thousand years like that that's going to happen in the story。

 Very low what。 Very low like lifespan like well they like if I have a solid state drive does that mean it'll probably fail within a few years。

 Not really because of the fact that you actually have tons and tons of cells and they saw this drive。

 And there's actually also redundancy built into it。

 So typically when they announced when they tell you that you know this is let's say one terabyte storage right there actually is typically more than cells that are enough to hold one terabyte of data because they will really have redundancy in place。

 So but yeah I mean eventually things will die off right because of the fact that like you know things cannot be we cannot rewrite them infinitely。

 Oh， cool。 Thank you。 Yeah。 Any other questions。 Hi does it cause lots of time to erase the information that we write on the SSD。

 So it depends on the technology that we're talking about for NAND GAKES。

 I mean usually it doesn't take that much time to erase compared to let's say like magnetic disks。

 And for the purpose of this class you pretty much don't need to worry about that。

 I mean just like you know need to know about the only thing that you probably need to keep in mind is just that like you know with them right can take different amount of time。

 And right in particular can be unpredictable。 Okay， thank you。 Oh yes I have questions。 Yes。

 Pansita。 Compared to the disk mechanical well which one would last longer in the same amount of use。

 So that's really hard to say usually flash drives like if you compare one individual cell I mean that's usually with tier with basically。

 tier down more quickly than let's say like a magnetic disk right if that's your point of comparison。

 But like with technology advancing these days it's really hard to tell because like you know we have newer generations of flash this every year。

 And also there are more and more redundancy mechanisms built into it so that like you know they actually can tolerate quite a bit of these errors。

 So it's really hard to say I guess that's the bottom line。 I see。 Thank you。 Cool。 Okay。

 so for the purpose of this class right that's all you need to know and as I said last time on Thursday if you're interested in this there's actually。

 quite a number of classes that you can take both in the computer science and also in the electrical engineering department here。

 You can actually go and design your own memory as well there are actually a classes that you can take to actually learn about those techniques。

 Okay， so like you know for us right we want to talk about this space management so now that you know like how they're like the technology fundamentals of this right how do we actually talk about managing this space。

 Well， so we first talk about writing and writing chunks of data right chunks of bikes basically。

 And as you can imagine writing things that are sequentially to a right mix to each other is usually usually the fastest。

 And they are actually for different reasons right for for a magnetic disc。

 The reason is because like you know we are literally waiting for the arm to spin around right think about the wine。

 the vinyl record again right。 So obviously we can read things that next to each other or we can write things that needs that next to each other that's great right because then we're not waiting for the for the armor assembly to move or and we're not waiting for like you know that this cat to kind of raise。

 Raise up and then like you're lower again right at the appropriate spot so that's why that's great and then for the for the right right I mean on and a similar reason for the right on。

 Sorry similar reason for reading sequential stuff on a flash disc as well。

 because reading things in a sequential way turns out to be faster than compared to let's say like if you need to write to。

 Non consecutive places in the flash this right just because of the fact that there's where leveling that I was talking to you earlier。

 So those are basically some of the principles， so what people usually do right is they basically try to predict behavior。

 Since we know that like you know reading and writing sequentially it's good。

 So how did you do that so they do that by basically trying to you know cash things that might be used in the near future so that's something called prefetching。

 They try to cash data that has been frequently used right in hoping that they might get reused like very quickly so that's caching。

 And then they also try to buffer rights right such that like you know we might end up even though initially we are seemingly writing to random this blocks but then if we collect enough of them。

 we might actually end up writing in a sequential way and that's great right so that's called buffering rights。

 so we'll see some of these techniques as we actually go for a long in the class。

 But then for for now like you know let's try to unify right because they're all these different this technologies out there。

 I mean like let's just try to come up with some common terminology。

 such that we can talk about them。 So we're going to use block as the basic unit of transfer for all kinds of different disc so it doesn't matter whether this is magnetic or whether this is SSD or something else。

 And you know typical numbers range from like you know 64 kilobytes and your book says like you know four kilobytes I mean that's somewhat arbitrary I would say。

 So every technology is different and every kind of device is different I mean for now we just want some common terminology such that we can talk about things together。

 And then like you know just to confuse ourselves right so people also use this term called page which is basically a synonym for block。

 You might see that happening in like you know different textbooks so just to just to be aware and some textbooks even use page as the unit of memory of main memory right so just to be even more confusing。

 But we'll make sure that the context is clear when we actually use this term in different in different ways。

 but for now we just treat these two synonyms。 Okay。

 so for a database managed system management system right what we call disk space management is really the way that we try to manage all these disks blocks that are available for us right to read and write data。

 It maps pages to actual physical locations on the disk right so the so the abstraction that we expose to the higher level is basically reading and writing on pages。

 But then underline the cover in the implementation we need to figure out right and you're where exactly are we going to write onto onto the disk and vice versa right we also need to be able to load pages by looking up like you're where a specific page actually lives on the disk and then load it accordingly into memory。

 So and so forth， so high levels and basically use this interface to read them write a page and they can also use this to figure out like how many pages to allocate and the so on so forth。

 So there are different things that we need to worry about for this space this space management。

 So here's like common mechanism a common medium for which we would use this component。 So here。

 let's say like you know sailors is the name of a table that we would try to put that we would like to read。

 So the way that we implement。 Or we utilize them this kind of like disk space management component is by first trying to start from a page inside of the sailors table。

 Let's say the very first page in the in the table because we want to read all the tools from it。

 We get to a page and then we basically go through a loop right that says like you know for each of the page that we read。

 We'll just do some processing。 This can be like you know filtering or whatever query that we're trying to accomplish。

 And then we just call next page to fetch us the next page that we want to process and then then the process goes on until we are done right done can be like you know the query has completed or we have written everything back to the disk whatever that means。

 The thing to notice here is basically that we are assuming here that next page right this call is fast。

 And that echoes back to what I was saying earlier right we're assuming that writing sequential pages is good for different kinds of this。

 So that's why the interface that we're exposed to the higher level in the system is basically this you know get a pointer。

 So like the first page or whatever page that we want followed by a bunch of next page calls right。

 So this is the API that we'll see and this is the common idiom that you also see when people try to utilize the space management components。

 That makes sense。 Okay， okay， so now let's talk about like how to actually implement right so given that this is what we this is the API that we're exposing to the higher layers I mean how do we actually implement the actual mechanism underlying the covers right。

 There are two proposals here that I want to mention for this class。

 So the first one is we talk to the storage device directly。

 So if we have a magnetic disk then like you know we just go and like you know figure out like you know how to move the arm you know how to how much to spin and then when to actually lower the the read head and then like transfer data for example right。

 So that's easy that's great。 In fact that's actually really good right if you actually know your device well。

 So you can actually implement your own device driver right specialized for the database management system that we're building。

 So that's awesome。 The downside however is that like you know each of these divide each type of devices tend to have their own API in terms of like you're moving arms or like you're reading a cell right on a flash drive or finding another one to actually put something to。

 So like you know you basically need to master all these different APIs and also implements it efficiently。

 So and then also right what happens if you add something new to it right so now we need basically need basically need to change our disk management component right。

 So that's one downside。 The upside of course is that like you know this is highly specialized so we can get really good performance of it if you know how to do that。

 So we can talk to the operating system。 When talk to the operating system because the operating system is already managing the file system for us。

 So in a sense we're kind of like shielded away from all these low level device like you know driver management issues right by using the operating system。

 So actually bypass the OS in the sense that we don't want the OS to be managing the files for us per se。

 because the OS might be actually you know writing back parts of the file or like you know reading or prefashing different parts of the file while we are trying to process a query。

 And the operating system probably doesn't know what kind of query or what kind of processing we would like to do right on a given file。

 Another opportunity another proposal to implement this management system here is to basically say that will bypass the OS by just asking the OS to just give me a humongous file on an empty disk。

 and then we pretend to be the owner of that file for the time being for the time remaining。

 So as long as we're processing queries we just pretend to the OS that like you look I mean we are managing that this like a huge huge file on our own。

 Don't touch it。 Don't we don't send anything back to the disk will do that explicitly by calling like you know the OS interfaces。

 And like you know don't prefetch anything will tell you what to that right so and so forth。

 So in some sense we're just like hijacking the OS in that sense by doing our own this manage this management。

 And this is this can be great right because now we have abstracted from like the low level device driver details。

 And we are just basically doing our own management at the block level at the page level if you will right for your basically management on file。

 So that's like another way you can imagine implementing the disk space management system。

 And you know this file right might as well span across multiple disk or even machines that we want to right as long as the operating system provides an interface to actually allocate for a file that looks that way。

 Then we just tell the operating system to just cut like you know shut up and then we'll just like you know manage the whole thing on our own。

 So in summary like you know just now what we're talking about is just basically some very simple technology about like saw state and also magnetic disk。

 And then I started talking about the cost of doing different things right so the thing to remember is basically that accessing the disk can be very dramatic in terms of cost compared to like you know read accessing data from the registered local to the CPU。

 And also we just talk about like very briefly about different interfaces that the disk storage manager can expose and also a little bit about how to implement them。

 And then that's it。 So now I'll switch over to a bit here。

 And if you have any questions please feel free to raise your hand。



![](img/b5a5b3b541b188bb8f3a47a75d4449fd_3.png)

 Perfectly clear。

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_5.png)

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_6.png)

 Yes， read things and sequences good yes。 Okay， can you folks hear me。 Okay， all right。 Okay。

 so carrying on where I'll then left things。 Okay， so we are talking about how now that we know what's happening at the bottom layer so basically in terms of a relation that may be stored across many different files managed by a file system。

 So given that abstraction from a database perspective you may imagine the following sort of subdivision so each table or each relation is stored in one or more OS files。

 And each file may contain many pages right so we talked about how pages and blocks are analog so each file would contain many pages of data。

 And each page contains many records。 Okay， so， and so again records a synonym for tuple。

 And so each page will contain many such records。 So this notion of pages or blocks is basically the common currency that's understood by multiple layers of a database system。

 On the disk it's sort of managed by this disk space manager it's sort of allocating pages to disks to to to to to files on disk。

 So these are read or written to these files on the disk。

 So this could be again a solid state drive disk or hard drive。

 In memory it's managed by the buffer manager。 Right。

 so it's managed by the buffer manager and higher levels of the database system beyond the buffer manager everything above operate on data in memory。

 So in order to operate on a data operate on a page。

 you need to first bring it into memory to operate on it。

 So the buffer managers role is to sort of bring the page in。 So once a page is in the buffer。

 it can sort of operate on it。 Okay， so next， let's talk about sort of how these how given relation is laid out across different pages in a given file。

 Alright， so let's talk about the single table for now so we can let's not worry about multiple tables the same ideas apply for multiple tables so a single table for now。

 And we'll talk about the notion of a database file and this is an abstraction that captures the information for a single table。



![](img/b5a5b3b541b188bb8f3a47a75d4449fd_8.png)

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_9.png)

 And here we're talking about a collection this file contains a collection of pages of blocks and each of these pages of blocks contain a collection of records。

 So， for higher layers of the database system， they basically can sort of use sort of。

 they don't need to worry about where the pages are on this they can use higher level abstractions to refer to information across pages。

 So， for example， fetch a specific record by referring to the quote unquote record ID and record ID is a pointer which is encoding the pair of information。

 which is the page ID and the location within a page。

 Another important API call that we may want is just can all of the records so and when you're scanning all of the records you may additionally have some conditions on the record should be retrieved。

 So， you want all of the students who is GPA is greater than 3。

5 right so that could be a condition that you may have on the records that are retrieved。

 So this is the read API the then you have the update API so you may want to insert delete or modify records。

 So we were talking about a single table for now and a single table could span multiple operating system files and in fact even machines。

 but let's not worry about all of that for now let's talk about a single file which contains multiple pages of records。

 So， before before we get into the details of how these pages are laid out。

 there are multiple different database file structure so information for a given relation could be stored across multiple different modalities。

 And we're going to be talking primarily about one modality for now which is the on ordered heap file。

 And the unordered heap file is basically has no real constraint as to where the records are placed across pages it's kind of unordered。

 Again， remember that relation is a multi set so this kind of matches are sort of abstraction of a multi set。

 And then if you want to make access a little bit more efficient。

 you could for example cluster your data based on some meaningful ways to the records and pages are grouped in some meaningful way。

 or you could be even more strict about it and sort it based on some attribute for example。 Right。

 so for example you could sort the student records based on the Calnet ID。

 In addition to sort of storing the records themselves。

 you could also have index file these are typically auxiliary structures that allow you to retrieve records or pages more efficiently。

 And so they may in some cases contain the records themselves or point to the records in other files。

 Okay， so for now we are not going to be worrying about these other three modalities of cluster sorted and index files you'll just worry about the unordered equals。

 We'll come back to indexes in the next class。 Okay。

 so on order he files so this is basically the abstraction that we want is a collection of records in no particular order。

 This is not to be confused with a deep data structure that you may have learnt about in your algorithms class just trying to ensure efficient max and men and maintain this max and men in the face of inserts and delete so this is not what we are talking about here。

 So don't confuse the two。 So this is basically a collection of records in no particular order。

 And in such a file you have allocation and the allocation of pages as the file strings or growth so as new records are added or deleted you may have more pages added or deleted。

 And so to support sort of actions that are happening on within a relation we need to do several things。

 We need to capture where all the pages exist for a given file。

 We need to capture the amount of free information that's present in a given page so that we can figure out whether to insert a new record or not。

 And we need to keep track of the records within a page。

 So let's start with the highest level of abstraction。 So let's talk about the pages within file。

 So a heap， heap file and let's say we are implementing this as a list。

 So for implementing a heap file as a list， we may consider having one special header page is basically the start pointer to your list。

 And then this header page is the， so the location of the heap file。 So basically this entire file。

 as well as the where the header page is within that file could be stored somewhere as quote unquote meta data。

 So this could be stored as data about the data in a place that's called the system catalog。

 So the database system catalog is just a location where you store data about your data。

 So for example， you may store information about schemas for various relations you mean the store information about。

 for example， things like this。 So how does a page。

 how which files are referenced in your fall for a given relation and where does a header page exist。

 for example。 Right。 So this could be one possible location to store where this header page exists within this file。

 Okay， so the header page is basically just telling you the start of this link list and then you have two separate link list。

 one link list of pages that are full。 So this is this link list， and another link list。

 which are pages that are have free space。 Okay， so again。

 and you might want to have forward and backward pointers so that as pages are added or deleted。

 you could sort of maintain that correctly。

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_11.png)

 And so this header page has pointers， sorry， to the start of the full page list as well as the free page list。



![](img/b5a5b3b541b188bb8f3a47a75d4449fd_13.png)

 And each page， each data page has a pointer to the next page in the list as well as the previous page in the list in this case。

 and this is the first page points back to the header。

 So why have I split this up into full pages and free pages？ Well。

 the benefit of doing that is that if I want to insert some new record。

 I only need to look at these pages as opposed to these pages， right， so that I allow。

 I sort of don't need to look at these full pages because I know that I won't be able to fit my new record within that。

 I can only fit it within those that have free space。 Yes。 Question。 Oh yeah sorry。

 you kind of just answered my question but I guess another question is once a page fills up on the free space link list。

 Do you have to move that up to the full pages and what's like the kind of cost associated with that。

 Right， so， so the cost associated we haven't really talked about the cost but I mean。

 we can talk about conceptually what would that look like right。

 So well you would have to if you have if you if you have a data page that was originally in the free space list and you want to move it to the full。

 full pages list， you would have to basically sort of make sure that the pointer is now point to the right thing。

 Right， so for example， if I wanted to move this page to the full pages list。

 I would need to update the pointers for the previous page， as well as a page that's next。

 And then once I find an appropriate space to put this in。

 I could put it at the end of this list or I could put it at the start of this list。 Again。

 I would have to update the pointers for the page before and after right so it's sort of basically I would say you would need to update order of four pages and their pointers in order to make this change。

 But let's talk about why this is actually not a great solution。 Okay。

 so why is this not a great solution。 Well， if I wanted to find a page that has enough data to store a specific record。

 And then I have no option but to go down this list of pages with free space until I can find one that has enough space to store my specific record。

 And I have no way out right so and that's basically the only way to do this if I have this simple link link list implementation。

 So， so that's the downside of this approach。 Well， so how do I。

 how do I think about this one one downside here is that I am sort of treating I am looking at the pages with the data to determine whether there is free space or not。

 but I can pull that information， about which pages have free space into a separate sort of page。

 which is called a page directory。 Okay。 And so this page directory can have multiple such header pages。

 Each page encoding a pointer to a given page as well as the free space that exists in that page。

 So it's encoding pairs， the pointer and the space。

 And so this directory can have many such header pages， each of which have basically these pointers。

 Okay， pointers in the space information。 Now the benefit of doing this is that you can pack a lot of information about a lot of pages within a single header page。

 because you're not storing any data in these header pages you're simply storing information about the pages。

 the pointer to the pages in the space in the pages。

 So there can be multiple such header pages these header pages are actually access pretty often so they may be in cash more often than not so they will be in memory。

 And finding a page to fit a record requires far fewer fewer page loads than in the link list。

 Remember the link list I just had to follow the chain of pointers until I found a page which had enough space。

 Here， I have one header page that can reveal the free space of many pages。

 So it has basically information about a lot more pages。

 but I'm not storing any data in these header pages。

 I'm just storing the amount of free space for a bunch of pages。

 You can in fact sort of push this idea even further by organizing this page directory in a more quote unquote optimized way so you can try to compress it。

 you can order the pointers based on the amount of free space in each page。

 But all of these approaches don't necessarily offer a lot of additional benefits beyond this simple idea of using a page directory and header pages。

 So page directory and header pages are often sufficient for our purposes。 Okay。

 so the highest level of abstraction here is a table is encoded as files which are collection of pages。

 and then a page directory provides locations of pages and the free space in each page so that we can basically add new pages。

 So we can add new records to those pages if we have it。 Let's talk about the page layout then。 Okay。

 And to talk about page layout， I need to talk about how we will be able to depict a page given that we have limited screen real estate。

 And so in memory or disk data is stored in linear order。

 And you can remember that as you're reading things from your disk head it's reading things in a sequential order along the circumference right so off the off the of the bladder or the sector。

 And that's how it's sort of read。 Now this information doesn't necessarily fit nicely and screen because I don't have the ability to go horizontal so the my cue is I'm going to turn this linear order into a rectangle so it's going to be basically this way。

 and then I'll go to the start of this and so on。 Okay。

 so I'm going to just this is just a convention for us to be able to represent these pages without me having to go off the page off the page in the sense that it's off the slide rather than a page。

 All right， so let's talk about how a page looks like so the first part about a page that we need to think about is the header。

 So the header is talking about is encoding information about what is contained within a page。

 And again this is meta data because data about the data so it may contain various bits of information like what are the number of records in this page with the amount of free space。

 You may have a next or last point or you may have a pointer you may have a bit maps and slot table we'll talk about how whether any of these are needed and which of these are needed as we go on。

 But the first thing I wanted to just say is that we may have a header just like we had header pages in the in the page directory。

 which are pointing to pages we may have a page header that encodes information about the records within a page。

 And in the sense， like as you go drill down， you still maintain that same sort of like structure of there being a header portion which is encoding metadata about the data。

 Okay， so we have some decisions to make the first decision to make is whether we have records which are fixed length records or variable length records。

 And we've been updated to you but there are ways to sort of encode a variable length field into a fixed length field and we'll talk about that later。

 But for now let's talk about whether you have fixed length records or variable length records as a possible decision that has been made and given to you so for example。

 if you don't have any strengths it's just integers and floats。 So。

 this is a record that is fixed length record because you know the amount of storage required for each of those fields。

 On the other hand， if you have a lot of strengths it would be available length record。

 especially if you use VARCAER which is syntax that we learned about when we talked about the data definition language。

 Okay， so that's a first decision which is the record length。

 The second decision is whether we want to use a packed layout which is basically the records are packed together or it has free space between the record。

 So that's the second decision packed on that。 And so the kinds of considerations that we have are we want to be able to find the records based on a record ID and record ID is encoded as a page and a location within the page and we'll talk about what this location means for each of these page structures that we're going to be considering。

 And we need to make sure that we can add and delete records efficiently and the overhead involved in each of these。

 Okay， so let's consider the first alternative。 So the first alternative was to pack records in a dense way。

 Right。 And this is for fixed length records as opposed to variable length records is actually the simplest possible scheme that you can have。

 So if you have， if you're packing records densely you basically have this page header and then you have the first record and then the second record the third record and the fourth record and so on。

 It just laid out in sequence。 So what is the record ID look like well the record ID is basically encoded as two parts of page ID in the location on the page。

 Here the location on the page is basically can be captured entirely using the information corresponding to the record number in the page。

 And once we have the record number we can actually figure out exactly where the record is going to be within the page by using simple arithmetic。

 Right， so you use an offset from the start of the page to figure out where that record is going to be in the page。

 So it would be basically the header size plus the record size times n minus one if I am trying to find the nth record in the page。

 So for example， the first record begins here so it's basically header plus record size times one minus one which is zero。

 Right， so it's just a header and the second record will be， sorry， second record would begin here。

 third record begin here and so on。 And simple arithmetic to get to that point。 Okay。

 so how do we deal with additions and deletions。 Well， additions are easy。

 we simply append at the end of the page if we have free space。

 If you have a free space we can just add a new record at the end of the page。

 Now deletion is a bit more challenging。 So let's say we delete page two。 So this is page two。

 Page two record three， right， which means I want to delete this record。 Okay。

 so I can go ahead and delete that record now on a free space。 Since this is a packed layout。

 I need to reorganize。 Okay， so this record which is page two record four。

 now need to move back and become page two record three。 Right。

 since this is a packed representation。 So the pack representation means that I need to rearrange and the record ID which originally I was talking about page two record four。

 now needs to be updated to page two record three。 So now the downside of that is that if I'm using page two record four as my identifier for that record and I'm referring to it in other files。

 I now need to update that。 So that's not ideal。 Right， so if that information is in other files。

 I need to go and update that information in those other files as well。 Okay。

 so that's a downside of this packed representation。

 Now let's talk about the unpack representation and see whether that helps alleviate some of these issues。

 but before that， do I have any questions。 Shiro。 Yeah。

 I just want to make sure so the page here we're talking about does it has anything to do with the actual page in the memory。

 where there's like page tables and to all these and stuff。 No。

 so this is basically we are talking about like the granularity at which you are writing and reading information from disk。

 Right， so， so this is the page and that's sort of the common currency that both the sort of the upper layers of the database system as well as the lower layers from the disk manager is going to talk in。

 So it's basically the currency that you're going to be talking about。 Okay。

 so it's the same page as in the operating systems page。 Right。 Yeah， yeah， okay， it depends。

 but yes。 Okay， for sure。 Thank you。 So you said that when we're doing the heap that it like checks all the pages and goes and it does this whole inefficient kind of check through。

 but does that mean that it's also a very like inefficient storage structure just in terms of space because I could see a scenario in which。

 the page isn't completely full， but it would just keep not being able to be written into because there's not a space in it。

 but if we rearrange the data in a different way kind of like you were talking about with the packing thing。

 It could fit so does that mean that he was just like inefficient in terms of storing things as well。

 So， are you talking about the， the， the heap file in general。

 Are you like the way that when there's the header file and then it split into two and then there is the free pages and the full pages and the free pages seem like an inefficient way to store things just in terms of like。

 the space， I could see a scenario in my head where there'd be a lot of space that we wouldn't use that otherwise we could allocate differently。

 Yeah， so there could be benefits that you could， for example。

 gain from periodically reorganizing the information in the free pages。

 especially if there's a lot of sort of deletions。 So you could。

 you could gain some sort of benefits from doing that we're going to be actually talking about some defragmentation issues and fragmentation issues in a little bit so hopefully we'll come back to that concern。

 I don't think necessarily that that is an issue that only affects that particular scheme I think it affects the page directory scheme as well。

 So， you have， if， for example， you have a lot of data， so for example。

 if you added a lot of records， and so you allocated a lot of pages。

 and then you deleted half of those records now you have， let's say half of those pages being empty。

 each of those， pages that you originally allocated are now half of them are empty。

 or rather sort of like half of the records in each of those pages are now deleted。

 you could have sort of compressed it down to half as many pages， but you can't because you。

 unless you sort of decide to do this， to be a defragmentation。

 right so that scheme is not going to be unique to the。

 the link list scheme I think it's going to affect this scheme as well。

 the page directory scheme as well。 Awesome， thank you so much。 Yeah。

 so I have one question about the delay， so like you mentioned before。

 so if we delay the page to record three， then we're going to rearrange the page to record for rights。

 So how about the record like the page to record five， because now we have。

 arranged the record for now help us to record five。

 do we also rewinding the record file to become the record for because yes so that's my question。

 Yeah， so so basically if you end up deleting a record。

 the record IDs for all subsequent records in that page need to be updated， right。 And therefore any。

 any other information that's stored in other pages that refer to that record ID also need to be updated so you're right。

 So basically not just record for record fire record six。

 any other records in that page also need to be updated。 Okay， thank you。 Felix。 Hey， so Jerry。

 partially answered my question but considering deletion， is there anything stopping us from like。

 kind of like just patting that area I'm walking as invalid or does the page layout like required that like records。

 like， records must be like， like valid records must be consecutive。 Okay。

 so basically the idea that you're talking about is what I'm going to be talking about next so just hold that thought。

 Thank you。 Okay， all right， so I guess that's it in terms of questions if there are any questions from the chat that require answering。

 Please raise your hand。 I'm not following chat that closely。 Okay。

 all right so following up on Felix's suggestion， which is to basically indicate that record has been deleted。

 Let's not by indicating that that record region has been that record has been deleted。

 We don't need to necessarily move the other records up。

 And thereby avoid having to update the record IDs of all of those records so using that idea。

 How do we actually implement that well one way to implement it is to have a bitmap。

 which is encoding whether or not a record within a page。 Again。

 we are talking about fixed length records， whether this record is valid or not。

 So that's what this bit map is encoding。 And so a bitmap is denoting these slots。

 each slot corresponding to a record。 And a record ID is well then correspond to again page ID location and page in the page location page here is going to be talking about the slot ID。

 So inserting is simple。 We find the first empty slot in the bitmap。

 And then we insert a record there。 Deletion is also simple。 We simply clear the bit。

 So in this case， if I wanted to delete record three， I would simply clear this bit。

 And I have now deleted my record。 Now the benefit of doing this is that all of these records record four record five record six。

 seven， so on。 They don't need to be moved up。 Their record IDs don't need to be updated。

 And so therefore no reorganization is needed。 So it's basically just indicating whether or not a record is valid。

 And you may get that in a very efficient bitmap。 So bitmap is just a zero one can be stored extremely compactly。

 Okay， so this is the unpack representation for fixed length records。

 Now let's talk about variable length records。 Now what happens with the variable length records well。

 you also need to understand how long a record is going to be。

 And so we are going to try figuring out how to encode variable length records。

 We've already seen that fact is in great for fixed length records。

 So we're going to consider the unpack case。 And so here are the considerations that we need to worry about。

 Well， we need to figure out where each record begins。

 And we need to figure out how long that record is。

 We also need to figure out what happens when we add and delete records。 Okay。

 so to figure out how to deal with variable length records。

 The first thing that we're going to do is to move the metadata。 The header to a footer。 Okay。

 so we're going to move it to the end。 We'll talk about why this makes sense in a little bit。

 And then we're going to have slots。 Okay， so this is a slot directory。

 The first slot in the slot directory is simply a pointer to the start of the free space。

 So it's basically saying from this point on。 You have free space。 Okay， so that's a blue arrow。

 And then you have a bunch of slots。 So this is record ID one record ID two record ID three record ID four。

 Okay， so this is page two record four， for example。

 And that each slot is encoding two bits of information。 It's encoding the size of the record。

 And it's encoding the pointer to the start of the record。

 So here record four starts at this point and then has， let's say， 12 bytes。 Okay。

 so two bits of information， the length and the pointer to the beginning of the record。

 And you are storing these record IDs in reverse order。 So it's increasing in this direction。

 So this is one， two， three， four。 And so the record ID is simply the length， the location。

 the slot table from the right。 Let's talk about deletion。

 Let's say I want to delete the fourth record on the page。

 I simply get rid of the information in that particular slot。 So it was this lot。

 And I get rid of this zero of this record， for example。 So I don't need to。

 I set the pointer for this slot to be now。 So it doesn't point to anything anymore。

 Now the benefit of this， this deletion approach is that I don't need to update the pointers to any other records。

 There's no internal reorganization needed。 I， if I delete a record。

 I don't need to move the locations of the other records。

 And now do I need to update the any other external pointers。 So the same。

 I can refer to the record IDs in the same way without having to worry about these deletions。 So。

 after I delete this record ID， which is record ID five is still going to stay record ID five。 Okay。

 so record page two record five。 Okay， how do I do an insert。

 So one approach is to simply put it at the end of this or the start of this free space。

 So remember that the start of the free space is indicated by this blue arrow。

 So I can just put the record here。 The second thing that I need to do is to find a slot。

 Here I had this empty slot。 And then add a pointer to the start of that record。

 And also encode the length of that record。 So I create a pointer link pair in the next open slot in my slot directory。

 I also then need to update my free space pointer。 Right。

 so the blue arrow which was here previously， now needs to be whoops。



![](img/b5a5b3b541b188bb8f3a47a75d4449fd_15.png)

 Okay。

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_17.png)

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_18.png)

 Sorry， I didn't want to go here。

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_20.png)

 Okay。 All right， so I needed to update the blue arrow。

 which was my pointer to the start of free space to the end of this new record that I just added。

 So that's why I needed to update this free space pointer。 And as I mentioned previously， I for this。

 this slot that just got filled， I need to provide a pointer to the start of that record and also fill in the length of that record。

 Now one issue is that if you delete a bunch of if you keep adding records to the end。

 So basically at the start of the free space， you could have a lot of records that got deleted previously。

 and they still occupying space in this page。 So how do we deal with this issue。

 so this is an issue of fragmentation。 And so one approach to this issue of fragmentation is to basically recognize the data on the page。

 Right， so you basically move this record， which is occupying this space to this location。

 if there's space in that location。 And if I move that record to that location。

 I need to update the pointer for that record in the slot directory。

 as well as the start of the free space。 Okay， so that's how I would move this record and basically deal with the fragmentation issue。

 Now this movement is actually okay， it's safe because the only thing that it's affecting is this particular slot。

 It's only affecting that slot。 Any other slot is fine， because the record IDs。

 at least externally refer to the page number and the slots and the slots are not changing。

 And therefore， it doesn't impact any external files。

 So now one question is when should I reorganize。 Right。

 so one option is I reorganize and basically defragment on every delete。

 Or I can wait until the fragmentation is so bad that I can't add any additional records and then I reorganize。

 So usually this approach， which is kind of a lazy approach is preferred。

 And especially if the page doesn't get a lot of new records。

 So this sort of lazy approach of just doing it when you absolutely need to is often preferred。

 rather than reorganizing on every delete， which is very aggressive and often not necessary。

 especially if the page doesn't get more records。 Now what if we need more slots sometimes when you try to insert a record and you're。

 you have only let's say five slots in the slot directory。

 where would you add these new slots let's talk about that。 So to track these slots。

 we need additional metadata in the footer。 The first bit of information is we can store the number of slots in the slot directory here we are storing five because there are five slots。

 And we are going to also be able to tell based on the number of slots and based on what is present in each of these slots whether they're empty or full。

 Right。 If the full slots is basically equal to the number of slots。 If every slot is full。

 And you need to add something more than you extend the slot directory。 Right， so in this case。

 I decided to extend the slot directory because I added an additional record I had five slots I wanted to add one more。

 So I added an additional additional record。 Once again， as always。

 I point to the start of the record and then I encode the information amount of bytes for that record so let's say 16 bytes。

 And so that's what is stored in my slot directory。 And I updated the。

 the start of the free space pointer case so all of those have been updated。

 The last thing that I need to update is this number of slots information and so I can update that and I can add six。

 So to extend the slot directory it's pretty straightforward。

 The slots grow from the end of the page inward。 While the records grow from the beginning of the beginning of the page inward。

 So once they meet in the middle， you know that you can't add any more information to the page。

 So this records growing down slots growing up allows both of them to grow with some latitude。 Right。

 so if you have a lot more slots than records then or the records are fairly small you have the slot directory cannot buy more space。

 If the records are fairly large and you have more records the records can occupy more space。

 So basically you have these， you have the direction of growth from both sides。

 allowing you to sort of give latitude to growth from from the record standpoint as well as from the slot sample。

 Okay， there's a question。 Yes。 Again， with asking a question right。

 I was asking a question about when we like earlier on in more about how we recognize the slots。

 So things when we're doing and let's see if we're doing like a fixed lens slots and if something is free like how do we keep track of which slots are free to have a big map or what。

 Yeah， so you could， for example， encode a bitmap to encode which slots are free or not another approach which is a bit more crude is to just go and check at the pointer for that slot is now the pointer for that slot is now then you can determine if that slot is empty。

 Right， so the bitmap approach is a perfectly fine approach like you said。

 or you could just go down the list of slots and then and check。 Okay， thank you。 Yeah。

 so a lot of the sort of trade offs and costs and benefits of these different strategies seem really reminiscent of memory allocators。

 That's a memory allocators。 Would you say that's like a fair comparison to compare to allocating records on a page versus allocating like this lots of memory on a memory page or does that statement miss some trade offs that are different between those two cases。

 So I think it's a fair statement to make and it is， it is sort of。

 it's no surprise that it should be reminiscent because in some sense one thing that is notable about database pages is that we use the same layout on disk as it is in memory。

 Right， so the same information is encoded in the same way in memory as it is on disk。 So。

 so in some sense the same considerations apply right so thinking about in memory allocation is very applicable here because we are treating the information in the same way whether it's in memory or in disk。

 And the benefit of that is that we don't need to pay any serialization deceralization costs as I will mention later to encode information on disk separately from how it's encoded memory。

 So， this again like I said this currency of thinking about the page as a common unit which is treated in memory just as it is in disk is a fair metaphor。

 And like you brought up that's why in in memory pages are treated just like they would be in disk and so memory allocators。

 and that's a fair sort of point of comparison because the idea of fragmentation defragmentation all of that and garbage collection all of that applies as well。

 Great thanks。 Any other questions Felix。 Any other questions about this in this model。

 because it's just like， it's just our assumption that like the footage only consists of like slot directories the freestack pointer and like the slot directory counter because like in the picture it kind of looks like it's overriding something。

 Like is there like no no sensitive mad at so left of like the slots。 And I didn't follow。

 can you repeat。 Oh， so in this model is， are the only things in our footer like the slot director。

 the slots the freestack pointer and the slot directory counter。

 because like in the picture you kind of see it's like kind of like shifting to left。

 So are we all right， is there any sensitive data left or no。 So， so I mean。

 so the thing here is that I'm not dictating where my records and where my footer begins and that's a benefit of the scheme。

 And so that's all automatically captured。 I don't need to pre allocate this much amount of space for the record just much a model space for the footer。

 And that dynamically grows as we add or delete records。 And so that's kind of the。

 so there's no pre allocated area that is that I would say is the footer so there's nothing。

 even though in my picture appears as if 16 is overriding something there's no such thing。

 I mean 16 was allocated in an area that was free prior to this otherwise it wouldn't have been allocated otherwise you would have never added an additional record here if there wasn't space。

 So that's how I would think about this does it make sense。 Yeah， that helps a lot。

 I guess that connects to my same question。 So is there like， I mean。

 perhaps we're going to cover this like in the next slide or something。

 but is there anything like we have to do like， in regards to like handling when we don't have enough space in our footer or for a footer like slides of a record。

 We expect。 So we， so we would ensure that the footer would never collide with the record so we would never insert a record when there's a danger of that happening。

 And if we end up with a case where we wanted to insert a record is no free space left in that page we may consider based on the number of null pointers we may consider reorganizing the reorganizing the page right so basically defragmenting the page。

 So to ensure that there is this all of the free space at the end of the record list as opposed to in between。

 So on the other like on the other example if we had a bunch of very small records is there and we fill up our footer like spots。

 Can our footer expand。 Yeah， so this is going to be a really。

 really corner case right because I mean it's rare that records are going to be that small that the footer is going to be larger than the records but yes certainly photo the photo can expand。

 Right， the photo can and will expand as records are added certainly as new records are added you would expect the record the area that's allocated for the records in the area that's allocated for the footer to both expand。

 Because you're adding additional slot you're adding additional records both of them are going to expand。

 Right， thank you。 Okay， so I think I should keep going because I'm running out of time。 All right。

 so that's what I wanted to say about growing slots。 I think I already covered this。

 So this is the summary for slotted pages。 So this， this。

 this idea is known as slotted pages because a page with slots。 Slotted pages are great。

 It is sort of a good compromise for variable length records for sure but also for fixed rank records。

 And this is because fixed length records often have null fields。

 And if you have null fields these null values can be squashed and sort of indicated using a flag avoiding the full attribute length storage。

 So if you have an int but that it can be null， you might want to sort of compress that and store it using a flag instead of storing the entire thing as this occupying the same amount of information irrespective of whether it's a null or not。

 If you have only non null fields that can be benefits to this fixed length format without the overhead of the pointers and so on because the bitmap approach is often cheaper in that particular special case。

 Okay， so we went from files to pages pages。 We talked about pages and records within pages。

 Now let's talk about how a record looks like。 So， each record in a table or a relation has a fixed combination of types。

 This is determined by the schema。 And so the， like I mentioned also earlier to a question the relation database is used the same page format for data on disk or in memory。

 And this is because you want to save cost of conversion this serialization deserialization cost of converting objects in memory to disk you don't want to pay that that cost。

 The other bit that I wanted to say here is that the system catalog the database system catalog is storing the schema and therefore it's storing the combination of types per relation。

 That way you can avoid storing the type information with the records and thereby save some space。

 So you don't need to encode the type information of the record you store that separately store it once you're done。

 This system catalog usually in most database systems is just another table。

 And if you're interested we can sort of share the table names for that I believe in SQLite it's called SQLite Master。

 So what would be our goal for encoding this record format what are our objectives the first thing is we want to access fields quickly。

 So why do we want to access fields quickly well often you're not interested in the entire record you're interested in components within the record。

 So if you say select GPA from student you're interested only in the GPA not the rest。

 So you want fast access to the fields。 The second goal is that you want the record to be compact so as much as possible you want records to be compact so that you can store more records on a page and store for your pages right in a file。

 So we talk about two cases the fixed length case and then the variable length is a fixed length case is easy。

 So that's a good one to start with。 So if you have a fixed length record。

 So let's say an integer a double boolean another integer in a character with length seven。

 So even the I feel is easy right we can just do arithmetic and then you can retrieve the I feel so for example。

 if I want to retrieve this boolean value I can skip over the first 12 bytes and then get to this。

 So I can make it more compact in certain cases so if all fields are non null I have no way of compacting right if the fields are do admit nulls then I have to apply variable length scheme so it feels have nulls。

 It's essentially like variable length。 So let's talk about the variable length scheme。 Okay。

 so what happens if the fields are variable length so in addition to your car and in int and int you also have bar car so this was our way of encoding variable length strings。

 So one approach is to store it with padding right so you basically store this Bob and pad it such that it occupies a string of some predetermined length let's say 20。

 And then this big street which is the Bob's address presumably is fired up to length 18。

 So you've determined upfront that 20 and 18 is enough as a cut off for the length for these two strings。

 Now the downside of this is pretty straightforward。

 The first is that you have to firstly account for the largest possible string more strings may not be that large so this is going to be wasteful。

 Or you are more conservative or you're more aggressive but you'll end up having to rearrange as soon as a larger string comes so this is going to be inefficient。

 So this approach of padding is not a great approach。

 Another approach that you may consider is a use commas so some delimiter to separate these these fields。

 The downside of that approach is that it's harder to determine where one field ends and then the other field begins。

 So if you want to look up the I feel it's a lot harder。

 And it's also hard to ensure sometimes that commas are not part of the string so if commas are part of the string then you need to find a way to escape them and it's more painful。

 So how do we deal with variable length records well the approach that we're going to be using is a per record header。

 So record header which is going to point to the start or the end in this case the end of each of these variable length fields。

 So here you have one pointer to the end of the first variable length field。

 And here you have a pointer to the end of the second variable length field。

 And so using the fact that you have some fixed length fields followed by variable length fields you know exactly where this variable length field begins and ends。

 And this variable length field begins and ends because you have you know the length of the fixed length portion and you know when each of these strings and all these variable length fields。

 So this is the approach that we're going to adopt which is a record header approach。

 This record header approach gives easy access to fields and is almost as compact as you can expect。

 Expect modular the header to the fixed length fields are encoded as is the variable length fields you do and go to a little bit of extra information in these pointers。

 And the same approach can be used to squash fixed length null fields with many null values as well。

 So， even so when you think about fixed length fields。

 If you allow now they essentially end up being like variable length field so you can use the approach for squash in them。

 So here's the overview of our approach for representing information。 So given a relation。

 These relation is encoded in a file， which are represent one or more files on disk。

 Each file contains many pages。 And a given record is represented using this encoding encoding format with a record header and as well as fixed length and variable length fields。

 The header allows you to point to the ends of these fields。

 And then bringing both of these together is the slotted page idea。

 which is basically encoding a page level header， which is encoding information about where the records lie within this page。

 And the one thing that I've not shown here is a page directory。 So that is another bit of metadata。

 which is encoding information about which pages have free space。

 So overall that is the summary of the representation portion。

 The way I like to think about it is at every year of extraction。

 there is a notion of a header and a notion of the details。 And if you think about it in that way。

 it becomes a lot easier to understand。 So， like I said。

 a database file contains pages and records within those pages and we talked about these heap files to unordered records。

 And you have the page directory allowing you to locate these pages efficiently。 The page layout。

 we talked about the fixed length approach， both packed and unpacked。 And for variable length。

 we only talked about the unpacked approach using started pages with intra page reorganization once the page becomes full。

 for example。 We also talked about the record format。

 allowing access to the field and also the dealing with null values。 Any questions at this point。

 Ian。 Yeah， so on every slide where we talk about the record formats for variable lengths record。

 So you mentioned that we could store the data with delimiter， like commas。

 but it's not a good way to do it。 So can you kind of elaborate on how we would do it with commas because it doesn't make sense to me。

 Sure。 So imagine if so let's see。

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_22.png)

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_23.png)

 Okay。 So here you could， for example， and could this as Bob， comma， big treat， and then you could。

 if you wanted to be， if you wanted to add some more indications that this is the start of a string and of a string could use quotation marks。

 And then you could do M 329。 For 703 or something， right。

 So you do need to have a way to distinguish that this comma is different from this comma。

 this comma is a delimiter while this comma is part of a string。

 So one way to do it would be to escape these strings with quotation marks earlier lost whatever I wrote。

 But yeah， so that's one way to do it。 There are other ways， of course。

 but it's basically you want to ensure that there's a unique way to read a record。

 The downside of this approach is fairly obvious right if I have Bob， comma， big street。

 Comma something something something I don't know where within this record to look at if I wanted to find the second field。

 right。 So basically in this byte representation。 I don't know that this is where I need to start reading and then I need to read this long。

 This many bytes to get the second field so that's harder to do in this representation。

 So using comma， we still have to scan sort of the entire scene。 Yeah。

 you still have to scan through the entire thing or you need to find another way of encoding the location for each of these fields which ends up looking like a header。

 right， and in which case you might as well just use a header you don't need the delimiter is anymore。

 Okay， thank you。 Lewis。 Lewis， you're still muted if you want to ask a question。 Okay。

 I think we should probably not start the next topic。

 If any of you still have questions feel free to hang back。 Thank you all for showing up。

 Thanks everyone see you Thursday。 [ Silence ]。

![](img/b5a5b3b541b188bb8f3a47a75d4449fd_25.png)