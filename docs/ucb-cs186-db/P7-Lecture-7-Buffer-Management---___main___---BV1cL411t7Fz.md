# P7：Lecture 7 Buffer Management - ___main___ - BV1cL411t7Fz

 Okay， I think it is being recorded。

![](img/8d64a543749ac3a1da9df3fba621e7d9_1.png)

 Okay， cool。 Okay， great。 So let's get started。 Hello， everyone。

 Welcome to Thursday's lecture of one 86。 So today I just want to wrap up the discussion that we had from last from Tuesday about B plus tree and then we'll actually move on to the next topic。

 which is buffer management。 So I just want to do a little bit of review。 So this is the。

 this is the first slide that we showed last on Tuesday about computing the computing the cost of different operations associated with indexes。

 So on this page， we're only showing the ones for heap file and sort of files as we talked about last week。

 The thing that I want you guys to remember is the fact that for one。

 we are interested in the average case cost because the worst case is always going to be just the same thing for he file and sort of file and also for indexes。

 So that's boring。 And the other aspect to remember is that both reading and writing to the disk will cost IOs。

 And then， like， you know， br and D are basically three different constants that we have defined earlier。

 Now， in terms of the index for this class， we're just going to assume that we have a clustered index。

 So everything is sorted。 And we are assuming a few factor of two thirds。 And then for fan out。

 which is this variable I'm defining here as F is basically the internal branching factor inside the tree。

 And that's also something that we have already talked about on Tuesday。

 And then unless we are talking about insertions and updates。

 otherwise we're just assuming that is a static index。

 nobody else is touching the index while we are trying to read it。

 So we have already gone through actually three， the first three types of operations on the third on the in the class on Thursday。

 So I'm not doing to repeat the first two。 I can， so but then let's try to revisit this problem of range search and then try to compute the cost associated with that particular operation。

 So as you recall， the way that we are going to use the index to do range search is as follows。

 The first step， we're going to use the index to figure out what is the。

 what is the corresponding heap file page that we need to read as the start。 So remember。

 in this case， we are trying to find all records between three and seven。

 which might perhaps span across multiple heap files， he file pages。 So therefore。

 we are going to first use the index to figure out what is the first page that we need to read。

 And then we are going to scan through the leaf pages in the index to figure out how many other heap file pages that we would also like to read。

 So remember in the index， we are only storing pointers。

 we're actually not storing the actual records， so therefore we first need to scan through the index。

 the leaf pages in the index to figure out what are the heap file pages that store records in this case between three and seven。

 and then actually go and read the corresponding pages from the heap file。 So in this case。

 you see that playing up in the bottom of the screen。

 So what is the I/O cost associated with these three steps。

 The first step is just basically going to be what we have seen before， right。

 so this lock number corresponds to the number of accesses that we need to go through in the index。

 in order to get to the leaf page， the first leaf page。

 So notice again that there's this plus one right because in this class we define the height of the tree to be everything except for the leaf level。

 So therefore we need to basically add back the plus one in order to account for the fact that we are retrieving the first page in the。

 the first leave index page right that corresponds to records with key value equals to three。

 The third step as we talk about last time is just going to be the number of pages where the number of pages here just corresponds to the number of pages that stores records between three and seven。

 In this case， it is going to be three。 And then the three halves figure that I'm showing you here is just to account for the fact that each of the heap file page is assumed to have to be only two thirds。

 Full right for the field factor so therefore we need to actually grab more key file pages in order to store the same number of records as before。

 So therefore that's why we have this three halves here。 And then finally。

 for the number of IOs associated with scanning the number of scanning the leaf pages in the index。

 I'm just going to over approximate that to be the same as step number three。

 This is definitely a gross over approximation because an index leaf page can definitely store way more pointers。

 way more information right then what the heap file was stored because the heap file is actually storing records。

 But then in this class we're just going to make that approximation to make the math looks simpler。

 So the sum of the total cost for this operation it's just going to be adding these three steps together。

 So you notice that in this case we actually need to subtract one right so why are we subtracting one with subtracting one in this case because we have over over counted the first leaf page that will read from the index。

 Right， here we add one because within an account for reading off the actual first page in the。

 in the leaf level in the index。 But then like you know for step number two right we actually going to read。

 we actually also counted that number as well。 So in order not to over count we actually need to subtract one just to make the accounting correct。

 So that's why we ended up seeing this number here that you are seeing on the right hand side of the screen。

 So this is a total cost here right so the total cost I'm showing you here is basically this number that I've computed from the from the previous page。

 Any questions about this so far for range search。 Cool。 So now let's go on to talk about insertions。

 So what do we do for an insertion right so let's say I want to insert the record 4。

5 into the into the into the database。 So notice that we also need to go through three steps。

 First step again we need to find use the index to figure out like you know which page are we actually going to modify in terms of putting in this record。

 Second step is we read the corresponding he file page and then actually do the modification。 Right。

 so in this case we're going to modify the page here in blue。

 And then finally we need to modify both the index leave page right and also the blue page that we have that we have highlighted here at the bottom。

 Right， so we need to update the leave page in the index because we have inserted a new record and we have we have to insert a new pointer right。

 And then we also need to update the key file obviously because we have inserted something new into the database。

 Right。 So what is the cost associated with these three steps。 First step same thing as before。

 We need to basically go up go down the index so that's just going to be the height of the index plus one right because we need to read the leaf page of the index。

 And then the cost for step two right it's just going to be one because we already know which file which he file we which part of the he file we need to read and then in this case we are only inserting one record so therefore we need to grab exactly one page。

 And then finally for step three， we actually need to do two IOS right because we need to both right back the modified he file page and also the modified leave page from the index。

 Does that make sense。 Sorry could you repeat why there to again。

 So two is because we need to go right back to he file page with your which you are seeing here in blue。

 and also the leaf page from the index right because we have inserted a new record into the into the。

 he file。 So the index leave page need to store where that record actually resides。

 So remember in this case we are assuming that we are not splitting the index we are not increasing like the level of the of the tree we're not increasing。

 We're not increasing the height so therefore like you know that is all kind of like you know ignored at the moment so we're purely just adding and other pointer at the bottom of the index for this in this case。

 Okay。 So， so the total cost is just going to be this number that you're seeing here on the screen right so just like you know。

 some of all three steps together。 And there we have it。

 So that's the cost associated with insertions， and then I'm not going to show the details of the lesions is basically going to the same deal right so we just go down to three and then modify the pages that we need to modify。

 and then right back the corresponding pages。 So， there was a excellent question raised at the end of last lecture right saying that I mean we really that。

 do we really need to be that meticulous and actually going through the actual details and doing all these different accounting。

 Right， to figure out like you know what is it， what is the actual cost。 The answers， you know。

 not quite right。 So we can actually just do this using big old notation that you probably have already learned。

 So if we abstract all of these using big O's you see the here like you know there's a very clear picture。

 Right。 So for instance if we compare with for equality search。

 you can definitely see that the using an index is actually way better than using a sort of file。

 Right。 The difference here is basically the base of this logarithm。

 And then if you recall from the last lecture right this number F is typically going to be a really large number。

 So it's typically going to be the case that for each internal note inside the leaf we can point to many different leaf notes。

 So therefore this F is going to be much much bigger than some， than something like to right。

 So therefore the cost associated with equality search is going to be much better if we use an index compared to if we use a sort of file。

 And of course also if we use compared to if we use a heap file。

 You can still see that in some cases like he file actually wins right for instance in the case of insertion he file is a constant cost right because we just attacked a pending a new record at the end of the he file and that's it。

 Versus for the cluster of the index we need to update the index， we need to search over it first。

 And then we also need to incur the cost of a pending right somewhere inside the he file。

 And then the cost here is actually going to be more。

 So that's why in this case like you know no one all what no one size actually fit all right so you know it depends on the use case and also the pattern。

 Now there's actually a reason why we actually talk about constant factors right when we're when I was showing you earlier like this kind of messy of arithmetic picture。

 The reason is because if you remember from the disk lecture。

 the cost of doing sequential IO is actually quite different from the cost of doing random IO。

 at least for the case of magnetic spinning disk right if you remember。

 So let's say the ratio is like you're one to 100 right so we do one random IO with them we can do like 100 sequential I was in terms of page reads let's say。

 I'm making this up obviously right but let's for for a sake of arguments。

 So what does that mean right so in the in a B plus tree right we need to go through these different levels in the tree。

 and each one of these internal note page reads right it's basically going to be a random IO。 Right。

 definitely not going to be sequential because we can be jumping all the way down to the tree。

 So therefore each one of these IOS is going to be random。 So if we find the argument here。

 then instead of doing that one single random IO we could have already done a lot of other sequential IO's right。

 in fact one to 100。 So what does that mean。 So that means we better be very selective when we try to read pages from the B tree right。

 because otherwise we can easily just could have done way better。

 If we do just let's say like he file。 So in fact in this case is given this ratio of one to 100 right it's basically saying that we better be visiting very few pages with random IO。

 or in other words， like you know this index right。

 hopefully it will not have a lot of pages that we need to traverse in order to go down all the way down to the lead。

 Otherwise it doesn't make sense right why we're using an index I mean just use a key file and just scan everything。

 So there's typically two ways to ensure this is the case。

 The first thing is like you know try to use a clustered index as much as possible。

 So that basically means we only need to encourage this in initial cost to traverse down the tree to figure out which is the leaf page to read。

 and then subsequently at once we land in the first page in the heap file then we can either just fetch that one single page if we are doing equality。

 or we can just do sequential weights in terms of solving for the case of range query right。

 So that's one possibility。 The other possibility you can call that a hack is to basically say just don't use spinning this right。

 You know use flash drives right in flash drives has the property that's sequential and random weights have the same cost。

 so we're out of the woods right in that case。 So it's not a trick that you can play here but that piece of only the two that I just want to mention to give you guys an idea about this。

 Roman you have a question。 Yeah you probably mentioned it but I somehow missed it what is a full table scan and like what isn't B plus tree is a data structure for a table essentially。

 So the tree is a data structure for the index right so when so for full table scan actually we don't need to use the tree right because we just scan all the heap files right so it doesn't matter if even if we had index we're not going to use it。

 So the only case that would make a difference is if we're actually doing any of one of these operations that was showing you on the previous slide here right。

 So let's say if I'm doing an insertion right。 So then having an index。

 we need to update both the index and the heap file。 So the extra cost incurred in that case right。

 And then if I want to do equality search likewise。

 Is the decision whether to use a heap file or sort of file user based or is it depends on the data。

 So that's a great question so in most database implementations that choice is actually kind of thrown back to the user。

 So as a user， we can actually define which we can actually declare which they which type of data structure we want to use to store the heap。

 the heap file like sorry to store the actual data。

 and also which data structures you use to store the index。

 So we can declare a cluster index we can declare an unclustered index。

 and that's up to us to define as the user。 And then we can really answer the question right because like you know that's just basically throwing throwing the user under the bus right it's basically saying that well you go figure it out。

 So in reality what usually happens is either the database administrator needs to already understand what the queer workload tends to be。

 So are we talking about insertion heavy workload are we talking about weed heavy workload right and if so you can choose like you know the right data structures you use based on this slide。

 So we just tune it over time。 So maybe initially we declared one clustered index on a specific attribute。

 but turns out that like people actually not queuing on that particular attribute that much so therefore we might as well use another attribute instead for the cluster index。

 So that can also happen。 Yeah， you have a question。 Please play again which mean by selective。

 Yeah so selective in this case just means like you know just don't read that many pages。

 It's it's not a technical term it's just basically saying that like just don't do a lot of random I was for the sake of argument because of the ratio that you see here on this slide。

 Okay， thank you。 So if SSDs have basically almost the same cost for random it's a country is that implying that like SSDs use like source or heat files。

 Is that like the case or the other like other structures that they use。

 So it just means that like it doesn't really matter in that case like which data structure we use right I mean all these data structures we are using is actually residing in software。

 So it's not like a hardware thing that we are doing all of these are basically software implementations。

 Okay， cool。 Yeah。 But of course as you know right fast drives are more expensive so you're actually paying a premium for doing this right so just to be aware。

 So in summary right so in this part of the course for the last two lectures we talked about you know different types of green structures we also talk about data storage at the TIA was basically mentioning about all these different types of indexes and how the actual data can be stored in a。

 file。 And then just now we also went through like you know the b plus tree and then also the cost model as associated with it。

 So obviously as you may know there are actually many different types of index structures out there not just be b plus trees。

 So， and so I encourage you to explore more if you're interested。

 And many of them actually domain specific and also create specific depending on what kind of pre use case you have。

 So， so if you're ready to hand if you have questions if not I'm just going to switch over in the meantime to the next lectures set up slides。



![](img/8d64a543749ac3a1da9df3fba621e7d9_3.png)

![](img/8d64a543749ac3a1da9df3fba621e7d9_4.png)

 Any other questions in the meantime。

![](img/8d64a543749ac3a1da9df3fba621e7d9_6.png)

![](img/8d64a543749ac3a1da9df3fba621e7d9_7.png)

 So， not then let me try to share again。

![](img/8d64a543749ac3a1da9df3fba621e7d9_9.png)

![](img/8d64a543749ac3a1da9df3fba621e7d9_10.png)

 Cool。 Okay， so for the next lecture for the next topic that we want to talk about we actually want to talk about buffer management。

 And here's the big picture that you have seen earlier when we were starting this。

 series of lectures on database internals。 So we have already talked about the sequel client right so you guys have already played around with it since the first project。

 And you have played around with SQL likes or you know what a sequel client looks like。

 We have already talked about the disk。 We talk about a little bit of the technologies involved we also talk about how this actually organized。

 We talk about indexes right we talk about different ways to organize files and we also talk about different index structures。

 So now let's talk about buffer management。 So I'm assuming that probably not many of you understand like what do I mean by buffer management。

 It's actually just another level of abstraction。 Right。

 as the usual saying goes right anything in computer science can be solved with another layer of abstraction。

 So if we already have an abstraction for the disk I mean why not also have one for the buffer or in other words for the memory。

 So the analogy is the following。 So we have for disk space management we have the disk right we have we have the disk space management。

 which basically abstract away the disk。 And then now we're talking about how do we abstract away the main memory。

 Right， so in this case main memory is like ran right typically the case。 Okay。

 so that's what we are calling as buffer management。

 How does it actually work how is this structured。 So as you remember the disk space manager basically have all these different pages right inside is implementation。

 And then for the last couple of lectures we were basically talking about like how to bring pages into memory。

 So the abstraction that we have talked about for the disk is basically this like you know page structure as the finer as the lower at the lowest level。

 So for main memory we're going to do the same game。

 But let's call it something else right so that we don't confuse ourselves with this concept of a page。

 So I'm just going to use this term frame which is also what your textbook uses and the next uses as the abstraction that the buffer manager is going to use to represent main memory。

 So just like we have pages of data so we can also load in from the disk into main memory in these frames。

 So for instance in this case I've loaded three different pages from the disk into the free three different frames in the buffer manager。

 So just like the disk space manager， the go off the buffer manager is also try to create this illusion of somehow manipulating frames in of memory as opposed to needing to deal with。

 Are we talking about multiple hierarchy of Rams， are we talking about distributed or like you know local ram and all that stuff。

 So all that is abstract away with just frames and a bunch of it。 Okay。

 In terms of the API is actually very similar to what a disk space manager provides。

 So we call that the disk space manager provides this API of reading and writing a page。

 So likewise the buffer who manager is just going to also provide this API that says like you know。

 fast read a page or write a page or write a write yeah or write a frame for example。

 So typically operation works like this。 So the higher level in the database implementation is going to call the API from the buffer manager to basically say。

 I want to read page number one from the desk。 So the buffer manager is going to check with a page number one already exists in one of his frames。

 And it's this case in the since that's not the case。

 it's going to go and talk to the disk space manager。 So ask it to please fetch page number one。

 and then put it into the one of the frames that it has。 And then return to the higher level。

 Same thing， you know， if another request comes， if another request from comes for like reading page number two。

 so we just do the same thing right you know go to the disk because it's not already in memory。

 Bring it into one of the frames and then return likewise， so on so far。

 So you guys are probably thinking about like you know。

 what are the issues involved in like your buffer management right in this under this picture。

 Two things first， how do we handle 30 pages。 And second of all。

 what happens when we run our frames right exactly what Alex is saying。

 So what do I mean by 30 pages。 Well， so we are going to make modifications to the database right so let's say we update a record we insert something we delete something。

 So all these pages that we have brought into main memory is going to get 30 in a sense right so they have they have been modified。

 So we need to be able to handle them by being able to write them back to the disk right in order to preserve persistence。

 Well， how is the buffer manager going to find out which page actually 30 one solution is to always write out every single frame that it has to the disk right but that is wasteful。

 So let's keep a little bit of accounting。 So we're going to add a dirty bit to each page that has been brought into main memory in one of these frames。

 And then we're going to just mark the 30 bit to be one right if it's actually modified by the database。

 And what do we do with a 30 page， but we need to write it back using the disk manager right and that we have already discussed in the last lecture。

 And you guys should by now be experts in terms of figuring out what is the cost associated with with doing so。

 So one other one other question that two other questions that we that we might want to ask before going into the problem of like what happens if we want run out of frames right。

 The first one， what happens if there are multiple concurrent operations on a single page that has been brought into memory。

 How can that happen。 Well， maybe you have like two different queries running at the same time trying to update like you know different records or maybe even the same record right on the on the page that has been brought into one of these frames。

 Well so remember this picture that I showed you earlier。

 there's this kind of cross cutting module right called the concurrency control mechanism that we'll talk about later on in this semester。

 which is responsible for handling that particular situation。

 So hold your horses if that's what you have questions about。

 Also what happens right if the system actually crashed before the buffer manager able to write anything back to the disk right。

 That's also bad right because we try to insert a bunch of records you know in resize and memory。

 but then you know the whole thing crash before like you know it's actually persisted onto the disk。

 Well， so that's why we also have this other cross cutting component called recovery manager。

 which is responsible for doing that。 And these both of these aspects are cross cutting because of the fact that they pertain not just to the buffer manager。

 They also pertain to the disk management as well right as you can imagine the same situation。

 The disk manager tries to write something back and right before it actually land onto the data right。

 you know right before the data actually lands onto one of these platters on the disk。

 The whole thing crash right。 So what now。 Same problem right。

 And what happens if like you know multiple page multiple multiple API's get calls from the disk manager to try to write back like you know the same page to the disk right what happened in that case。

 So we have we need to have a concurrency control mechanism as well。 But as I said。

 we'll cover these extensively in the later part of this semester so don't worry about that for now if that's what your question is about。

 Yeah。 So my question is， how is this different from the buffer management in the operating system。

 Excellent question， just hold on to that and I'll try to answer that if not like you know racial question again。

 Okay， thank you。 No other questions。 Okay， so let's take a look at what is the implementation of a buffer manager really internally what happens。

 As I said， we need to keep track of a bunch of frames right。

 So the way that it works typically is the buffer manager just calls the operating system and try to allocate a huge amount of memory。

 So this also answer the question of the interest right so you know how is this different from the operating systems。

 It's very similar， except that just like in the this manager case if you remember the lecture that I had like you know to last week about how we can bypass the OS in terms of like you know。

 allocating a gigantic file and then claiming that we're managing it ourselves。 Same story here。

 We asked the OS to basically gives us as much memory as we need。

 and then we just tell the OS to please go away。 If you take 162 or any anybody from 162 here is like you know you guys might just like you know kick my butt right you know saying that you know the OS actually Mike also be able to manage that like why we doing this like you know inside the database manager。

 The DBS right and the reasons because in some cases we actually have more precise information about the workload。

 No better than the OS in terms of like you know when do we want a particular page to be written back to the disk。

 So therefore， for most implementations that we are aware of for DBS。

 We basically just try to take over the operating system by asking it to just allocate a whole bunch of memory just like for this manager case。

 So like this is not the only design， so you can definitely stop rely on the operating system if that's if that's what you want it。

 But then I'm just claiming that the DBS usually has more application knowledge or knowledge about how the workflow is going to be using these frames so therefore it might be able to make better utilization compared to the operating system。

 So that's the first part of a buffer manager。 So we need to keep track of all these different frames。

 And we need to do a little bit of accounting right so as I said we need to we need to somehow store this 30 bit。

 Right， basically whether each of the pages brought into the frame has been updated。

 So for that we're going to implement that using some smallish array or some hash table if you like right this is purely in memory。

 So this is just basically going to store for each frame。

 which this page do we actually have we actually fetch right if any。

 and then we're going to basically say like you know how many where is 30 or not。

 This pin count we're going to go into detail in just a second。

 Okay so for us questions so dirty basically just means where do we have modified a particular page that we have brought into main memory。

 So a typical operation is something like this right so like you know we have all these pages brought from the disk into these frames。

 Some of them will be modified by the database as part of an update or insertion or deletion。

 And then some of it might be read by the database because it's trying to answer query right。

 So in all these cases we don't want to get rid of that page right we cannot write that page back or like evake that or empty that frame because somebody else right is actually operating on it。

 whether it's right or read or whatever。 So that's where this pin count is actually coming into play。

 So the pin count is basically going to tell us that someone。

 somebody right some other query is actually operating on this page。 So please try。

 please don't empty it or please don't evake it yet。

 So notice that this is different from the dirty bit right。

 because a query can be just reading a page and not actually modifying it。

 And even in that case we don't want that page to be evicted。

 So it's definitely the case that if someone is making modification because of a right we definitely don't want to kill off that page right by like you know emptying it or like writing it back to this yeah right because the operation might not have finished。

 And the same thing also for a read right。 So we're just using this pin count as a way to keep track of how many queries are we actually is actually operating on a single page。

 And it's not enough to just keep a binary zero or one right。

 Why do you think that's the case I mean why do we actually need to count as opposed to just a binary bit to say that like you know whether zero or one right why do we need to actually keep track of it as a number。

 Anyone。 We need to make sure that all the users that are on the page are done before we eat。

 Exactly right so imagine the case where we have multiple queries trying to read a particular page right maybe page six right in this case。

 So even if one of the queries is done， we need to figure out that we need to make sure that the other query right is also finished before we can evict page number six right for example。

 So that's why it's actually a number is not sufficient to just keep that as a binary variable。

 Good job。 So what happens now then right so if a page is requested right so as I said。

 if we find a page that is not actually in the buffer pool then the first thing that we do is we basically try to figure out if there's a page that we can。

 that we can replace right maybe a page that is not pin for example。

 And then if the frame is actually dirty， then we just write it back to the disk and then we mark that slot to be available。

 And then we just read from the from the disk manager right and then that's it and then we just returned that after pinning it right because we now know that somebody is operating on that particular page that we have just brought into memory。

 Now it would be great right if we can somehow predict right what are the pages that is going to be a used。

 Same thing also for the disk manager right if we can prefetch them that's awesome。

 because as you remember all the things associated with sequential reads and all that good stuff right so we can perform sequential scans that's great for the disk。

 And it's also great for us at the buffer management as well right because we know how many slots we need to be able to allocate because we。

 because if that because we can predict how many pages will be operated on。

 So of course then the million dollar question is like you know what happens if the buffer pool is actually full。

 And besides that we need to basically evict some of the existing pages that we have right， and to。

 to be systematic about this， the way that we decide which page to actually get rid of is based on something called a page replacement policy。

 There are many different page replacement policies out there and for the sake of this class we just described two of the simplest ones that that is actually used these days and actual implementations。

 First one is something called least recently used or you。

 And there's an approximation scheme based called clock policy。

 which is basically a modification of you。 And then there's also something called MOU that we'll discuss in this class。

 Now all of these actually have huge impacts on the number of IOs as you can imagine right because depending on which page we will evict that will also take how many pages we can bring into memory。

 And how we are bringing pages into memory， depending on whether we are doing a sequential random I'll that we have already seen has a huge impact in terms of overall costs。

 So what is the MOU policy， it's pretty simple。 So we just basically try to evict the page that is least recently used right I mean as the name suggests。

 So we basically try to first of all we're not going to evict anything that is pinned。

 because we know that those are not available to be replaced。

 And then we somehow just track the time right that each frame was has elapsed since each page was last and pinned。

 And then we just pick the frame that was least recently used in terms of these this time in terms of the time。

 and then we'll just evict it。 So for example， in this case I've added this last use column right so this is again metadata that the buffer manager keeps。

 And then you know you see that in this case， which one should we evict we just evict the one that is like you know the least use here right so like you know for example like this 111 here will you。

 You will recall hopefully that this is actually something that has already been covered in 61 C。

 Right。 And just so we remind ourselves of what this means right actually went on to the 61 C course website and just to check it out right that this is actually covered to ensure that that's in the case。

 But this was in another context right so in this class they were covering it in terms of trying to figure out which of the cash entries to evict。

 So similar story here right except that we're not evicting cash entries we actually evicting pages or frames right from a buffer manager。

 some， some， it's basically the same thing。 And just so that we are we knew my thing you know I'm thinking up this some some some like you know ancient semesters actually something that was covered in the spring right just to ensure that we're all on the same page here。

 All right， so yeah as I said right so in this case we are going to evict the first one that was least used right so in this case frame number four because like you know based on the last use。

 Time that's like basically the least。 And then if we need a second page we're going to evict the second least use right in this case like you're the one with 15。

 This is obviously a very simple policy you can imagine。

 and it's also good for temporal locality just like what we have already discussed hopefully 61 C as well。

 But it's this actually can be costly right， because we need to always try to figure out what is the least。

 We least recently used page right in order to do that we need to not just keep around this last use column。

 and also run a query right so to speak。 So figure out what is the last used page right。

 There are different ways you can solve the problem for instance there are like different specialized data structures just to find the minimum。

 So like a priority heap for example， can be used， or we can always just scan all the pages right and figure out which one is the least used I mean you can use your favorite。

 algorithm here。 So， there's also something else that we can do which is an approximation。

 So let's say I don't want to keep account of everybody in terms of this last used number。

 but I still want to approximate least recently used。

 How can I do that we can use something called the clock policy。

 So here's the state of the buffer pool manager， as we were talking about earlier。

 what we are trying to use this clock thing for right it's basically an approximation scheme to figure out which is the least recently used page。

 Approximately speaking。 So， it's not always going to return the really least recently used it can return something that is actually not the most recently used。

 but then in terms of the overhead and maintaining this data structure。

 it will be actually something simpler。 So let's see how it works。

 So as the name suggests is called the clock， because we actually have a clock hand。

 which is basically the next page that we will consider as the candidate for eviction。 So。

 in each of the pages， we're going to add one other bit， called the reference bit。

 which is basically just something that we use to keep track of whether this is something that actually has been recently used。

 you see how that works in just a second。 So instead of keeping track of this number， right。

 of time right that it was least that was last used。

 I'm just going to modify this to just use one single bits right like just like what I was saying。

 And then we're going to keep this extra variable called the clock hand I was alluding to earlier to figure out what is the next page that we should check。

 So， the next thing that works is the following。 So let's say something now comes along and say I want to be able to read page number seven。

 which is not currently in the buffer。 So we're going to look at the clock hand and try to see if we should if this is if whatever page that is pinned that is currently pointed to by the clock hand is the victim that should be evicted。

 So this page is not because this actually has been pinned right。

 Somebody is actually looking at this page at the moment so we cannot evict that so let's skip that。

 So then so then we advanced the clock hand to the next page。

 So the next page now is going to do the same check right I mean is it pinned。 No， it's not pinned。

 but then this reference pin here is sorry this reference bit here is actually a sex。

 So it basically means that is probably something that was recently fairly recently used。

 So we're also going to skip that as well。 We're going to advance the clock and again。

 and then we'll find a page in this case page number four， which is not pinned。

 And also not set in terms of this reference bit， meaning that it's something that has been read or used fairly fairly far away in time right。

 So in this case， this is actually going to pay to be the page that we will replace with page number seven。

 So， but then right now that we have brought page number seven into the buffer pool we need to make sure that we're not going to evict that。

 like you know on the next cycle let's say right。 So this is by exactly setting both this pin because somebody is reading it and also set this reference bit that you see here。

 Right。 So in this case we're setting both the reference bit for page number seven because that basically signifies that we have recently brought us into frame into the main memory。

 And then we're going to be dependent because we know that somebody else is going to be using that and。

 and like you know after we return。 Right。 So we're just going to advance the clock because basically that means like next time when we need to evict another page we're not going to evict page seven immediately we're going to look at the next one。

 In this case page five。 And then we're going to return a pointer to page seven to the upper level and then we are done。

 Does this make sense to people who people have questions about this policy。

 I had a question about ref reference bit what can you repeat what's that all about。

 So the reference bit is basically approximation as to how recently has a particular page been used。

 Oh， so this is replacing the method where we count how many times is that we're not carrying anymore we're just using one single bit。

 So if we visit a page that was not pinned， but has the reference bit sets for instance in this case patient number three。

 We're not going to evict that because it's basically saying that is very recently used。

 But then we're going to unset that bit right because next time we visited it then is no longer recently used whatever recently used me。

 So it's basically an approximation。 So if you're traversing through these things and you're not using it you're going to unset the bit。

 And that's how they get removed。 Well， so a page needs to be first unset sorry a page needs to be first unpinned and then also unset before it will be considered as a candidate for eviction。

 I see。 So the unpinning is done when the query is done right so that's we understand。

 And then the unsetting of the bit is done by this clock hand。

 So every visitor page that is unpinned， but with the reference bit set。

 Then the thing that we're going to do is we're going to just unset that bit and then move on。

 We're not going to touch that page yet。 So that's the approximation here。 Felix。

 Is there anything like is it like convention that's just one bit or is there anything like stopping us from maybe using like two or three if like there's a lot of frames。

 Yes， sure。 So in fact it doesn't so the one bit is enough to basically notify the clock hand right that this this particular page has been recently used right。

 So now the question that you asked is like you know why not use more bits to represent that。 Sure。

 In fact， we can use 32 right。 If we use 32 bits， then we just reduce down to the to the our policy that we had from before。

 We're just keeping track exactly off like you know how recently something has been used we're just going back to the integer number。

 Thank you。 Yeah， makes sense right so we're basically just approximating that number 32 bits of 64 whatever we're just one single bit to approximate。

 So， you know， if there's a situation where all the pages are pinned。

 Is there any kind of like a way to for other pages that to come in。 Yeah。

 then in that case we really screwed I'm sorry。 If everything if all the pages are pinned right that means like you know some query somebody is basically touching them all like all of those pages at the same time。

 So we can the only thing that we can do is just like you know delay processing the next query。 Yeah。

 thank you。 I'll just buy more this。 Bye。 So this hand mechanism。

 Like how do you know which one will be next。 Yeah so it's somewhat arbitrary right so I'm just using this pictorial pictorial illustration of like a clock on rotating to basically go around and like you know check which one should be the next victim。

 But you can basically like you know use your own mechanism to figure out what is the way to to go around all these pages right。

 So obviously we don't want to always just visit one or two of the pages because that basically means like you know only those two will be evicted but like everybody else will not so that's bad。

 So we definitely want to go around everyone。 But then we regard to like you know what is the way to go around I mean that's somewhat arbitrary。

 Oh， and then H。 Sorry。 I'm not sure what your name is。 Yes。

 just curious like is the least frequently used data structure ever used compared to L。 R。 U。

 and like why is L。 R。 U。 much more popular compared to the L。 F。 U。 Oh。

 at least frequently used I see so it all depends right so in fact that's the next thing that we want to talk about right so when is something good for these two different policies right you can already see the difference here。

 So I would actually claim that for repeated access to popular pages this is actually good because for you and also for the clock policy。

 We won't evict those pages， but I'm not claiming that this is like the ideal case right it actually all depends on what is the access pattern that we have。

 Right。 But then at least in comparison between L R U and clock you can already see that for clock policies cheaper right because we don't need to find out the exact minimum in terms of the most recently。

 most least recently used。 And it's also less costly because we are approximating numbers with a single bit。

 Right。 And like you know that's basically one of the one of the ideas and then you can basically try to find cases where they actually different and I actually encourage you to do that right let's say you want to compare to L。

 F。 U。 or any other schemes。 But even in the case of you right there was already a problem for you and clock policies as well。

 And people think about like when these two policies is particularly bad。

 Maybe if you're like accessing things like a cycle but it's like。

 Yeah so like if you're accessing something and then like it takes a while before you access it again but it's like a repeated process you're just going to have to like read those stuff。

 Exactly right。 So what's it like that right so let's say I want to repeat a scan。

 What do I mean by that well I we see here at the bottom of the screen we have a disc manager of like you know seven different pages。

 So let's say I want to go through pages from one to seven in that order over and over again。

 Maybe we're running the same clearly over and over again right。 So let's do the experiment。

 So we have six pages in memory we have seven pages on the disc。

 If we want to first read the first page great we read it in bring it into the frame。

 Second page likewise right you get the drill。 We basically fill up this entire buffer pool with the six first six pages。

 But now the fun begins right with the seventh one because now we need to be able to evict something。

 Right so now we will miss every time right so why because we try to bring in right the seventh page。

 And then based on our you right we are going to evict the first one because the first page was the least recently used。

 Okay， so for the seventh attempt we are going to bring back bring in page number seven kill off page number one。

 But then in this case we have this repeated scan right we're going to scan through these seven pages from the disc repeatedly in that order。

 So we want to bring back page number one but unfortunately page number one is already out right is not in the buffer pool。

 So we need to evict something。 What is the next thing。 So we need to make it to page number two。

 Right， I mean you get the idea here right so in this case we're basically not going to get ever any cash hit at all。

 Right， because we always need to bring something in。

 And like you know the you know you get the you get the idea here right so we basically just need to just keep losing。

 A term for this because this happens so often is actually cost something is something called sequential flooding。

 We're just going to flood the cash with all these different rates but it's actually not doing any good for us。

 Not hitting the cash， we're not utilizing the all these different frames that were brought in right so we might as well just go to the disc manager every single time。

 So how can we get out of it right so there's zero percent cash hit in this case right。

 but like you know as I said right this actually can be something very common because of the fact that like you know it might be the same query getting executed over and over again。

 And in fact you see something happening like in when we process joints。 So how can we do better。

 So that's motivates for something else right call most recently used。

 So what happens is exactly opposite of what we wanted to do。

 So we stuck in this case again with six pages we need to bring in the seventh one。

 So for the seventh one， we're actually not going to kill off the least recently used。

 We're going to kill off the most recently used。 In this case。

 it's going to be page number six right。 Great。 We kill off page number six we're bringing in page number seven。

 And then we go around again， we need to read page number one and great right I mean page number one is actually already in the buffer pool。

 So page number one is already in the buffer pool I counted as a cash hits。 Right。

 you can call that a buffer head or like you know frame hit or whatever you want caught。

 So it's basically just saying that we don't need to go to the disc manager to bring in that page。

 Likewise right for a second page great I mean also got a hit right。

 So you see this count here kind of counting up right third page also awesome right it's also also already brought in。

 Fourth page to get the drill right so the only the only time that we need to bring in something is actually when we try to hit the sixth page right because in this case the sixth page is not there。

 We need to evict the most recently used。 And in this case that is going to be patient number five。

 So we're going to replace patient number five。 Great because the next thing we're going to read is patient number seven so that's again right in the buffer pool。

 So that is also going to be a hit right。 So you get the idea right so we're just going to repeat that。

 And then like you know we're just going to like you know kill off the most recently used and then we'll still get quite a bit off hit in the buffer pool because of the fact that many of the pages。

 Already residing inside the buffer pool。 So while I enjoyed doing like you know clicking all throughout this entire animation that I've made earlier any other questions for now about this policy。

 So in fact we can be a little bit more generic or try to do a little bit more math about this right so in this case what we had was we have B number of pages in the buffer。

 We have more pages in this case in the he file that we are trying to bring in。 Right。

 For sequential weed workload for the first and pages that we are going to bring into the buffer。

 We're going to get zero hits right because none of those pages is in the buffer we need to fill in the buffer so awesome right we'll just get basically get no hits。

 But then for the next and attempts right we're going to get everything except for the one of the pages as a hit。

 Right。 So you already saw that on the previous slide right so i'm not going to go back there。

 You already see that we only need to kill off one page right so that's great。

 And likewise right so that pattern is just going to be repeated for every like you know for a next read at hand for next and pages we're just going to do the same thing again。

 Except that the victim that got a victim it's just going to be a different page every single time but for all the cases that we had from the last on the last slide is just going to be one single page。

 So on average right we're just going to get b minus one divided by n for every single attempt。

 Right。 Because we get b minus one hits over and different attempts so on average we're just going to approximately get that many hit hit rates。

 So compare that with least recently used right where we got zero so this actually is pretty good。

 Right。 Because like you we are actually getting some hits so that's awesome。

 So we can actually even do better。 So if we can actually do profession right for example we know that this is going to be a sequential read query we need to basically just read all the pages。

 We might as well ask the this manager to just prefetch whole run of pages right so therefore we don't even need to check whether that's already in the buffer pool because we know that is going to be in the buffer pool。

 Right。 So an example in this case is just like you know if we ask patient but one to be read we might also bring in pages two to five。

 As I said how is this going to help is it's going to help us because we know that random IO is costly。

 And if we can do sequential read that's also great that's great。

 And other aspect of this is also because if we can both do reading of sequential pages while also trying to answer queries at the same time。

 So let's say if we have two different threats right for example。

 That also is going to be great because we can fetch things in the background while trying to serve queries with our other hand。

 But as I said right you know no one size fit all so unfortunately this is not also going to be the end of our problems right。

 In fact， I will claim that we need a hybrid because sometimes our view is actually better。 Right。

 let's say we actually want to do random access of pages so let's say we're not doing sequential reads of all the pages we actually just want to jump around。

 So in that case， our US actually better， you can try to work that out later on in class。

 sorry after class if you're interested。 And， and you actually is better in the case of repeated sequential weeds。

 And we have already seen cases where like you know that behavior would exist right let's say it's the same query that scans through all the pages over and over again and we're running that query for multiple times。

 So needless to say right people have come up with many different fancier policies right they go from completely random you know least frequently used right or not recently used or even use your favorite neural network right these days that's something that is really。

 hot right and very popular， but use a neural network to predict what is the next page that might be least used or like what is the next page that should be evicted and then go with that。

 There exactly it sounds like 285 top。 Right。 And but one thing to be to be worried about right is like you need to keep track of the cost of running these policies。

 The attractive bit about clock and now you for example is the fact that like you know they're really easy to implement。

 and they're also very like you know not that costly in terms of running it right I mean we just advanced the clock so we speak。

 And then we just check where the reference bit has been set and then with that we already figured out which page to make。

 If you do something as complicated as newer network right。

 then maybe the time that it takes to do inference。

 It's costly enough right that you might as well just like you're bringing everything from the disk right because remember random I can kill。

 Right， so that's something that you need to be worried about right if you do some complicated like you know bird or some kind of crazy neural network to decide in this case。

 So that's why even something like you know simple as random my also work because it's kind of like you screw it I mean I don't want to incur all these costs of like you're figuring out which page actually you make just pick a random thing right and just like you think that and then we're done right。

 Oh。 So that's all I wanted to say for this right so in summary。

 what I've told you guys about this is about all these different buffer buffer management policy is like you know this aspect of keeping kept keeping trial pin count。

 keeping trial 30 bits。 I think these two things we need that regardless of what policy we want it right because we need to figure out like you know which page is actually being used right now and which page is actually dirty because we need to write them back to the disk。

 So those two things I will claim we cannot avoid， but you know， just like。

 just like everything else there are many different policies that we can use to implement the actual page replacement algorithm。

 And I encourage you to check out on Wikipedia page right or even like you know go back to a 61 C slides to figure out to see other policies that are available。

 And just be worried right for instance in the case of databases that sequential flooding can indeed be a real problem because of the fact that queries tend to read all the pages in the case of let's say a select star。

 So in that case we need to figure something out。 Something better or at least being able to deal with sequential flooding as a problem。

 I have for buffer management。 Anybody have any questions for me。 Yeah。

 So do we know what the general access patterns like for database。

 What's the what pattern like the general just like the access pattern for database。

 Do we know what the access pattern is for database or。 Yeah。

 So it all depends on what application is actually using the database right or what are the users right。

 So if the if you have a single user and then if， if you somehow know ahead of time that what that person is going to issue in terms of queries then great for you。

 Right。 But that's not always the case that you can imagine so。 Yeah。 It's hard hard to say。

 but people are indeed like you know there has actually been a lot of research and trying to predict and also trying to study in terms of recognizing patterns and queries right so that they can predict。

 What are the pages that are going to be used。 Okay， thank you。 So， Yeah。

 because we need more like different ways that you can implement right so like you know。

 but we need a per page pin count and also a per page 30 bit。

 So you can store this as to get it with the frame you can store it as a separate table。

 you can store it in a ray and store that in a hash table whatever you like。

 but it needs to be kept somewhere inside the buffer manager。 Thanks。 Thanks。 Thanks。

 Great question so for the purpose of this class we're just going to assume that this is all like software software implementation。

 but there actually has been work trying to do this implement all these things inside the inside the hybrid as well。

 So you recall from 61 see that like you know cash management for instance right is something that is typically handled inside the hardware。

 How do you draw the line is completely arbitrary right so like you know somebody basically make the decision that caches as something that like you know all kinds of applications including operating systems databases we need to use。

 So therefore that's implement that into hardware because that's coming enough。 Right。

 But maybe there aren't that many like you know database servers out there or like the need is not high enough such that people actually want to bake that into hardware。

 So there actually has been work done in the past where like you know they tried to build what they call database machines in hardware。

 So all that machine support is basically related relational operations。 Right。

 everything that we talked about in 186。 So in that case it actually makes sense to try to bake some of these into the into the hardware。

 But of course you're going to ready to see the trade up right we bake something to the into the hardware just like in 61 see we can change it afterwards right unless you're willing to pay more。

 So it's a flexibility that we can actually try to change things if we want。 So choose your poison。

 I guess。 Cool。 Thanks。 Yeah， there's no thing is yeah no such thing is free lunch unfortunately。

 Was that time I said another question or。 Cool。 Okay。

 so if no other questions I'm going to switch over to a did yeah。



![](img/8d64a543749ac3a1da9df3fba621e7d9_12.png)

 Any folks hear me。 Yeah。

![](img/8d64a543749ac3a1da9df3fba621e7d9_14.png)

 Okay。 All right。 Okay， so we're going to be talking about relational algebra now and。



![](img/8d64a543749ac3a1da9df3fba621e7d9_16.png)

 So I know the slides for relational algebra not on the website yet I wasn't actually anticipating getting to cover relational algebra but we managed to rush through buffer management so we have a chance to tell you about relational algebra today so that's great。

 So the slides will be up shortly after lecture。 Okay。

 so what have we learned about database systems so far。 Well。

 we've talked about the disk space management we've talked about buffer management as we saw today。

 We've talked about how files and indexes are managed right。

 And we've also like we started at the very start by talking about SQL clients right and how you would be issuing queries to database for our DML and D D L queries that allow you to define your schema and then modify your data。

 Okay， now we're going to be talking about stuff in the middle。 Right。

 So the query parsing and optimization as well as relational operators。

 So today specifically we're going to be talking about relational operators。

 And we're going to stay at the logical level。 So we're going to be talking about the definition of the relation operations will be talking about the implementations subsequently。

 And this is going to be interesting because it's going to be really going to be understanding how a database system internally reasons about a SQL query。

 Right。 So SQL query is just a representation for users。

 It's what the user communicates to the system。 The database system operates at a different level and that's the level that we're going to be talking about today。

 Okay， so let's talk about before we do this。 Let's talk about what happens when you have a SQL query and how does this gets translated into this internal representation that we're talking about。

 So it goes to several phases。 The first phase is， let's say a user inputs a SQL query。

 We sort of have this query parser and optimizer that transforms it into a representation that looks like this。

 So this is called a relational algebra expression。

 This relational algebra expression gets translated into a logical query plan which basically describes the sequence in which these operations are performed。

 Right。 So in this particular case， we'll talk about these operators specifically。

 but in this particular case you're doing a join between reserves and sailors and then you are sub selecting some tuples at maximum condition and then you're deciding that a certain set of attributes are displayed to the user。

 Again， don't worry about if you don't get what what these symbols mean these Greek symbols mean that's going to be our focus today。

 Okay， so we went from relational algebra to this logical query plan。

 The final step is this physical query plan， which is what is actually executed physically。

 What are the physical algorithms that are executed on the data。 Right。 And again。

 the data is going to be basically from the pages which are brought into memory via the buffer manager and then each of these pages you operate on again。

 There's a lot of stuff that I'm covering in this slide。 It's totally fine if you don't get it。

 I just want to give you a bird's eye view into what is going to happen。

 Starting from a sequel query to what is actually executed by the database。 Okay。

 So overall the database system will end up creating a so called physical query plan which involves physical operators that operate on relation instances。

 Okay， so again， this is very high level。 At the， at the， at the sort of 10，000 feet view。

 You start with the sequel query， which is basically a user saying they want this result in this particular case they want to do a join between reserves and sailors based on some conditions。

 And it's a user says they declare that they want to see this。 They don't specify how it's done。

 That is a job of the database system and internally a database system is going to come up with a sequence of operations that represents the result of the sequel query。

 And then come up with a sequence of operations， which is basically this sequence of operations is called a query plan。

 Okay， and the system is going to execute this query plan and produce a result for the users。 Okay。

 All right， so what is the difference between sequel and relational algebra。 Okay。

 so there are two different representations for us to think about。 The first is sequel。

 which we've already covered and this is what humans express right humans like sequel。

 because it's declarative you say what you want you don't say how you're going to get it。

 And the job of the system is to figure out how to execute it right so you don't be when we talked about sequel we didn't actually worry about whether it's going to be an efficient query or not right where how quickly is a database system going to be executing that。

 And even how is it going to be executing it that's not wasn't a concern for us at all。 Systems。

 So the database system internally is going to use relational algebra to represent the sequel query and then compose a result for the sequel query and the relational algebra expression looks something like this with these Greek symbols。

 And the relational algebra is easier for a relation for a relational database system to manipulate because operational it's describing how stuff is manipulated in order to compute a query result。

 So overall database systems internally transformed sequel into relational algebra expressions manipulate and simplify it。

 and then figure out the best operational mechanism to compute the sequel query result。

 So this is going to be the focus for the next several lectures。

 Well let's talk about relational algebra in particular because that's going to lay the foundation for the internals of this query processing and optimization stuff that we're going to be focusing on。

 So algebra is basically an algebra。 So it's a very sort of it has a very formal sound rigorous foundation so it's an algebra that operates on relation instances so these are instances of relations。

 So there's just like any other algebra like if you're high school elementary algebra or your linear algebra right in elementary algebra you had variables that you were manipulating in along with sort of arithmetic。

 And linear algebra you were manipulating matrices right so you could do matrix multiplication and so on。

 So just like that relational algebra operates on relations at a time so you compose expressions。

 And then you compose expressions on those expressions it's sort of a compositional sort of framework that allows you to compose more complicated expressions from simpler expressions。

 So in this particular sort of example again I'll talk about these symbols later but as there is something happening to RNS so these are two relations some expression is being computed on RNS。

 And then some other expression is being computed on that result and finally this last sort of operation is performed on the result of that so that's a sort of an algebraic expression in this case relational algebraic expression。

 So what are there are some nice properties of this algebra so the first property is that the result is also a relational instance right so it's also a relation。

 You your input is a relation your output is a relation。

 This allows us to compose these relational algebra expressions right so you can for example take two expressions and union them together join them together or apply take an expression and perform a selection on top of it again we talk about these operations in a second。

 So this is just like what you would do with relation algebra right as a sorry a linear algebra right so linear algebraic expression on matrices returns a matrix。

 right， and you can it is compositional so you can take an expression and then multiply。

 that expression is another expression and compose even larger larger expressions and the result is closed right so the result that you get is still a matrix。

 So this is an important property that an algebra gives in this particular instance is that the input schema the schema the relations that you operate on determines the output schema。

 And this is very important because you can statically check whether queries are going to be legal or not so you don't actually need to look at the data to test whether a query is going to be legal or not you can just look at the schema to determine this。

 So I mean you have the same study for linear algebra as well right so the input sizes the rows and columns determine the output sizes so it's not very different for relation for linear algebra as well。

 So pure relation algebra actually has set semantics okay remember that we talked about set semantics is a bag semantics when we talked about SQL pure relational algebra actually has set semantics that are no duplicate tuples in relation。

 And this is going to dominate most of our discussion we're going to be focusing on set semantics SQL of course as we saw has bag semantics or multi set semantics。

 We will talk about multi set semantics as it pertains to sort of the system discussion discussion so as we're talking about these operators as they relate to SQL we will talk about the connection to multi sets。

 Okay， so relational algebra operations come in various flavors there are a unary operations which operate on a single relation sort of binary operations that operate on multiple relations。

 And so we'll talk about unary operations first there are three fundamental unary operations。 Okay。

 so the first is projection。 So this only retains desired columns of your input relation。

 So it's basically doing vertical selection。 So the next operation is the selection operation this selects a subset of rows。

 So it is a horizontal operation。 So it's basically keeping a subset of the rows。

 Then you have the renaming operation which basically allows you to rename the attributes of your relation as well as the relation name itself。

 Okay。 And so， whoops。

![](img/8d64a543749ac3a1da9df3fba621e7d9_18.png)

![](img/8d64a543749ac3a1da9df3fba621e7d9_19.png)

 So these these operations also have symbols right so there is pie which is the projection operation Sigma which is a selection and row which is a renaming operation。

 Okay。 So these are all unary operations。 We also have binary operations right so binary operations happen on pairs of relations。

 So the first version is， or the first operation is union。

 And simply tuples that are in one relation or in the other relation set difference which are tuples in one relation but not in the other relation。

 And cross product or Cartesian product which allows us to combine two relations by taking every combination of tuples in the two relations。

 Again， you may， as you're， as you're going through this you may immediately see analogs to sequel and I'll try to connect back to sequel as much as I can。

 As I'm describing these operations。 Any questions so far。

 And this is the symbols here are straightforward you have a cup or a u minus for set difference and an x for cross product。

 Okay， so what do why do we mean when we say relation algebra deals with sex。

 This is the formalism right so we're talking about an algebra and the algebra is typically defined in a set context of course in practice。

 Since sequel is a multi set assumes multi set semantics people certainly sort of switch to my discussing what it means to operate on relations which are multi sets right to the same operations on multi sets what would they look like we'll talk about that as well。

 Any other questions。 Okay。 You also have other operations that are not part of the basics of operations but these are derived operations these are what I would call macros for the six operations above that allow you to express certain frequent operations。

 Right。 And so one example of that is intersection and certainly you may have sort of realized this that intersection can be expressed using unions and differences。

 And so intersection has this operation which is the inverse you。

 And then there is there are the join operations again we've talked about joins in in in sequel。

 And so joins are expressed using both eyes and there are several flavors of joins。

 We'll talk about all of those flavors subsequently。 Okay。

 Joins as the name suggests is combining relations while also satisfying certain predicates right so we talked about natural join we talked about inner and outer joints。

 Those are all flavors of joints that we'll talk about。

 We'll also add in theta joints and equid joints as special cases。 Okay。

 so this is a bird's eye view for the operations。 So these are the basic operations these six operations。

 And these are the derived operations that are shortcuts for frequently used expressions that can be composed using these basic operations。

 Any questions so far。 I'm not sure if this is totally in scope of what like we covered but how are we like like defining arguments for like selection and projection。

 Yeah， so we'll talk about that right now。 As in when I cover the when I cover these operations in more detail。

 So this is not going to be the only time I mentioned these operations。

 I'll talk about examples and I'll talk about a set of what are the formal foundations for these operations。

 Okay。 Any other questions。 Okay， so let's start by talking about projection or pie。 Okay。

 so here's an example of a projection。 So let's say I have my relation instance， S2， and I'm doing。

 So S2 has four attributes， S ID， S name rating and age。

 and I'm doing a projection and I'm listing S name and age。 Okay。

 what this essentially means is I want you to only give me。 S name and age as part of the output。

 So I'm sub selecting S name and age from S to。 Okay， so the output is going to be S name and age。

 And so， if， if this seems familiar。 Well， yes， it should be familiar because we talked about this earlier in SQL。

 This is basically the select operation in SQL right so select operation allows you to list the attributes that you want to see as part of the output。

 That's essentially what the projection operation is doing as well。

 So the schema is basically determined by the schema of this attribute list。

 So basically by listing S name followed by age， it basically saying。

 I want the output to contain these two attributes in this order。

 So the names and types correspond to the are basically this list that you use is selected from the input。

 So the names must correspond to names from the input and the types are inherited from the input as well。

 So the input to S to here。 So you're basically doing a vertical selection of a subset of columns in this particular operation。

 Okay， so there is a subtlety here， which is what happens when there are when there are duplicates。

 Right。 So since relational algebra assumes set semantics。 If you did a projection of age。

 you end up with a multi set as an intermediate result。 Right。

 So you basically threw away these columns and you've only kept this column， which is age。

 Now you have two copies or three copies of 35。 So the final result for this projection has to transform this multi set in back into a set。

 So this is the right result for doing a relational projection as you mean set semantics。

 So the set semantics with projection often results in fewer rows。

 especially if you have duplicates after having projected out some columns。 So， of course。

 as we saw with SQL， real systems don't remove duplicates。 Right。 And it's。

 it's cheaper to not remove duplicates and also because this is the semantics that users expect with SQL。

 Right。 How would you remove duplicates any thoughts。 This thing。 Right， but that is the query。

 but I am thinking more about the algorithm。 What algorithm would you use to remove duplicates。

 So some folks have mentioned using a hash。 Well， that is one approach。

 Another approach is to use sorting。 Both of these are valid approaches。 Right。

 But it's both of them are expensive。 Right。 So you can certainly use hashing to try to determine if multiple tuples hash to the same value。

 Or you can do a sort of all of these， all of these tuples。

 output tuples to determine if there are two tuples。

 There's a sequence of tuples that are identical in which case you retain one copy and throw out the rest。

 Okay。 Okay。 Okay。 So I think I will stop at this point。 And I will cover the rest in the next class。

 Do I have any questions。 Is it a whole different， like relational algebra when it's dealing with multi sets with just different definitions for everything。

 Yeah， essentially， I mean， there are parallel analogs of the operations and the semantics and also。

 as we will talk about， there are analogs for the rewriting rules that would apply to。 Right。

 Different rewrite rules may apply for the set semantics and for multi set semantics。

 So it's important to sort of keep the distinction between the two。 By rewrite rules。

 I mean basically taking an expression and simplifying it right like you would simplify algebraic expressions or。

 sorry， elementary algebraic expressions or matrix expressions。 Again。

 here we want to simplify these relational algebraic expressions and different rules for those simplifications apply for sets versus bags。

 Oh， so that's actually， actually， let me ask a trivia question right so why do you guys think these are the Greek letter names that we use for these operations。

 So for instance， why is projection pie。 For pie。 Yeah， Greek alphabet。

 Exactly so what do you think like you know， this。 What is it that what is it doing。

 It's actually a very good， it's actually a very good new model。 Yeah， way of actually， yeah。

 demonic， yeah sorry， it's actually very good， demonic。 Select right。 Yes。 Yeah。

 I thought that I thought that more is like the where clause in the sequel。 So， but yeah。

 I guess that makes sense。 With the proper yeah the proper relational algebraic term is selection right。

 Yeah。 So what is very confusing and I think we should。

 Given that beer over time we should we should stop what is very confusing and I'll mention this again in the next class is that selection which is sigma doesn't actually correspond to the select clause in sequel。

 And that is just an unfortunate unfortunate choice of names right so the select clause in sequel response to projection。

 Essentially right and but the where clause corresponds to selection。

 So that's all a little confusing and this is something for us to discuss next time。 Yeah。

 and then Franklin's that's good that kind of them go right I mean hold on to your thoughts I mean we'll see what actually happens later on in the next lecture actually but。

 Okay anyway so that's the end of my trigger a question。 Maybe we should stop recording just。 Okay。

 that's the question that's right。 Thanks everyone。 Bye。



![](img/8d64a543749ac3a1da9df3fba621e7d9_21.png)

 If you have questions please stay。