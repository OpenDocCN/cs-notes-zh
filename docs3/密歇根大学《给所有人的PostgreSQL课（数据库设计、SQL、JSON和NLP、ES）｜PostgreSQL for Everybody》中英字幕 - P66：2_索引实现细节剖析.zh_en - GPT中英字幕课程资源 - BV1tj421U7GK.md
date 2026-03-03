# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P66：2_索引实现细节剖析.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Now we're going to talk about indexes we just got done talking about rows and blocks and how a big file is broken into blocks and then within there we have free space little gaps to do inserts and deletes and sort of reorganize stuff without having to rewrite whole files that's really important random access is the critical element of databases。

Now I want to talk about how we。Limit the number of blocks that we have to load for a given query and that's the purpose of indexes。

And so assume that there's some kind of a logical key or maybe a primary key and we're going to look something up。

 maybe it's got a prefix， you know， like a like with a prefix。

But we'll just talk about logical keys and so if you could somehow store the actual logical key variable。

 the value of the logical key and then the block that it's in then。

And if that was so small that you could keep it in the memory。

 you could look in this little memory table that says， oh。

 here's a clue that says calling at Uish EduU is in block。21456 and boom。

 go get Black 21456 and away you go。And so that's what an index is， it's a key to block hint。

 and there's a lot of different kinds of indexes， but then you're storing like 30 characters per row instead of 2000 characters per row and then you make those really as small as possible。

And so that the basic idea of an index， right， is we have this little cheat sheet of quick quick ways to go get there。

A block and then the index informs a where clause and the whole goal of a aware clause。

 you don't think of a where clause like an is statement。

 think of the where clause as it's sending it to all the rows and then the rows respond where the where clause is true and what we're doing with the index is we're making it so we can in effect。

 ask the disk to send us a whole bunch of data and then throw away the ones we don't need or just give us the ones that we do need。

 so the less we ask of our disk drives， the faster our database system is going to be。

And so it's really small， and so that's what we're going to talk about is the different kinds of indexes that you can use in Postgres。

So there are two kinds of indexes， forward and inverted indexes。

 and there are a number of different kind of forward indexes。

You might call them normal and weird instead of forward inverted。

 but that's what we call forward in invertted。So the classic index that we use a lot and we'll talk about this is the Be treeree index。

 which is a balanced tree which is a tree that fans out and we try to minimize the depth of this tree so that even if we have to read some of the index off a disk。

 we don't have to do too many we sort of for a certain number of records。

 the amount of readeds that caused by the index is like one， two or three。

 and then you read one block and then there you go as compared to reading hundreds of thousands of blocks。

Another one we'll look at is called a binary range index and it's a gross simplification from the be tree but it's appropriate for certain things。

 hash is like hashing where you have this little table it takes instead of the key you take a hash of the key which is always much almost always much smaller and then go straight to the block。

 hashes just like in everything are great until they collide so the hash is supposed to spread this the keys out and if you can make a hashwork。

 you can make a hashwork and we'll talk about the different inverted indexes as well。

In the regular indexes where we're looking from a key to one or a few rows。

 you might as well just leave it default， don't even tell it what kind of index to use。

 let it figure out and it's almost always going to use Bre Bres good for string keys。

 it's good for number keys， it's good for date keys。

It's a great balance between the cost of insert and the cost of updating。

The br the block range index， that's actually a lot smaller and it's very fast。

 but it depends on data that's kind of sequentially increasing like maybe you do it on a date field or even a primary key where it's  one。

2，3，4，5 and then you have these blocks and they sort of have one through 10。

 10 through 20 and then you just keep the largest and smallest number。

And so we'll talk about the inverted indexes as well， but let's take a look at how a bee tree works。

You can read this， I'd encourage you to read it。 It's a pretty well written。

 some Wiki PD pages are harder to read than others。

 I'm going to pop this image up to make it a little bit bigger now the key here to remember is this is the index and the whole idea of a binary tree is that it reorganizes itself it moves things around and so for example let's just say and you can put many more of these things remember your keys are there and then it points to actual blocks so you could think of like this one is pointing to a block two is pointing to block these are all blocks that we know exist and these are the primary key values now in this top one where we start。

We have some number， and it's way more than four， but we're only showing four for example。

 and what it really says is that we keep track of。This has all this first leftmost one has the keys below seven。

 the middle one has keys between 7 and 16 and the far right one has the above it and so if we're going to insert a record say 22。

And we would go find a block on disk。And maybe it'd be in an existing row we don't know because all we want to know is which block the row that corresponds to key22 is we go through our B tree。

 we just add a little entry to 22 and then point that at the right block on the index and the same let's just say we're going to do 15。

 we'd do 15， we'd look in we find that we'd have to go in this middle one and we put it in 15 after 12 and then we would put the row and we keep track of which block we put it in so you can think of insert the row then insert the index entry to keep track Now let's just say that we are doing 10 Now let's do four let's insert four。

So we're just talking about index maintenance so you know it's less than seven so it's got to go into this index field now youve got to rewrite some things because we know it's going to have to go between two and5 so what you have to do is you have to shove things so you sort of shove the 12 up the nine up the six from one block to the next and the five up into that block nope the five goes to here and then the four is inserted between the two and the five and then when you still have a block for the row and we keep track of that so this is how we balance it and you can imagine if we just ended up with you know way too many things in say the middle block and we filled it up we have to split it。

And at some point this tree can be more than too deep and we worry about keeping the depth of this tree constant。

 so there's many things there could be hundreds。Of entries in each one and each depth and so you have this tree and it goes out but the idea is with somewhere like three or four deep you can have hundreds of thousands of records and if you had to store these things on disk you would read the first one then you'd read second。

 third and fourth and then you'd read the block which is way better than 200。

000 blocks all having to be read and then scanned separately so it seems like a lot of effort。

And this bee tree is kind of beautiful in that。As long as you leave a little bit of free space in these index blocks。

 it's pretty easy to add new ones and every once in a while you have to kind of do a little reorganization。

 you might have to make the tree deeper once in a while。

 but it actually does that and it amortizes the cost the insert cost over inserts pretty well。

Every once in a while insert will be a little more expensive but most of the time the inserts are really cheap。

 the cost of updating the index is really cheap and the scanning cost is really good。

 so that's again why we kind of say hey， be trees are great， just use them。Now。

 let's take a look just for a minute at the brn， just to give you a sense that this is all about having a sense of where。

A hint as to where to find a block。 So the brn is something that's in a sense， unique。

 at least right now to。

![](img/8df71110744777876a03ddccac4f83bb_1.png)

It it's unique right now to Postgres but it's pretty cool， so the br is a little different。

 so it's like this linear list and each one of these in a sense points to， so we got four things。

 points to one block on disk。

![](img/8df71110744777876a03ddccac4f83bb_3.png)

And what you do is you scan the blocks and you look for the minimum and maximum in each of the blocks and then you have just two numbers。

 you characterize each block as two numbers， so this first block is number the key the values for our logical key are somewhere between one and6。

 the second block you look at it somewhere between nine and 12。

 third block you look at it 7 and 16 and then 18 to 21 the key thing to look at here is there is actually an overlap 7 to 16 is actually a bigger range than 9 to 12 which means if we are going to ask where block 10 is we would have to pull a record 10。

 we'd have to pull two blocks in。

![](img/8df71110744777876a03ddccac4f83bb_5.png)

![](img/8df71110744777876a03ddccac4f83bb_6.png)

![](img/8df71110744777876a03ddccac4f83bb_7.png)

![](img/8df71110744777876a03ddccac4f83bb_8.png)

![](img/8df71110744777876a03ddccac4f83bb_9.png)

![](img/8df71110744777876a03ddccac4f83bb_10.png)

![](img/8df71110744777876a03ddccac4f83bb_11.png)

![](img/8df71110744777876a03ddccac4f83bb_12.png)

![](img/8df71110744777876a03ddccac4f83bb_13.png)

We'd pull two blocks in because that's what the brn would tell us to do， it's reduced it from 100。

000 blocks， but's we still got to pull a bunch of blocks in。



![](img/8df71110744777876a03ddccac4f83bb_15.png)

And of course then what we do to figure out where 10 really is because 10 could be in either of those blocks or it could be in either of those blocks。

 then you got to read through the blocks， but remember the blocks are only 8K so it's not like the end of the world it's how many blocks you read。

 not what you do with the blocks and so if you say find 10。

 it might say didnn't find it or it might find exactly one copy of it and then if we think about updates。



![](img/8df71110744777876a03ddccac4f83bb_17.png)

![](img/8df71110744777876a03ddccac4f83bb_18.png)

![](img/8df71110744777876a03ddccac4f83bb_19.png)

都。If we think about updates。诶。Cl。Let's think about updates here， come back， right。

 so think about updating and you know， think about adding。

 so let's let's let' let's put some blocks down here。Some more blocks down here。



![](img/8df71110744777876a03ddccac4f83bb_21.png)

Some more blocks down here， some blocks down here。And let's just say that they're sort of partially full。

 right， so there's a little space in each one。

![](img/8df71110744777876a03ddccac4f83bb_23.png)

![](img/8df71110744777876a03ddccac4f83bb_24.png)

And let's say we're going to put blah record4 in here comes four so we'd look in the brn and say is there a reasonable spot to put that in and the answer is well we got this block here。

 it wouldn't even change the index if we put it into this first leftmost block so yeah you go ahead and you're write it you got some space and then you actually didn change the index you just extend that one it's kind of nice it's kind of like hashing except it's like a range。



![](img/8df71110744777876a03ddccac4f83bb_26.png)

![](img/8df71110744777876a03ddccac4f83bb_27.png)

![](img/8df71110744777876a03ddccac4f83bb_28.png)

![](img/8df71110744777876a03ddccac4f83bb_29.png)

![](img/8df71110744777876a03ddccac4f83bb_30.png)

And that's let's say， for example， that this block was all- let's say the second block was full and the third block was full。

 and then let's just say we are going to do， I better clear it。



![](img/8df71110744777876a03ddccac4f83bb_32.png)

![](img/8df71110744777876a03ddccac4f83bb_33.png)

Let's say we're going。We got some blocks。

![](img/8df71110744777876a03ddccac4f83bb_35.png)

Oh， come back to pen。There we go， we got some blocks， got some blocks， got some blocks。

 got some blocks， got a block and we got four blocks for the four brin things。



![](img/8df71110744777876a03ddccac4f83bb_37.png)

And let's just say these9 through 12s are all full， right。

re both the 9 through 12 and the7 or 16 are full and we're going to put 10 in。



![](img/8df71110744777876a03ddccac4f83bb_39.png)

So you can kind of imagine what's going to have to happen， you might come in here。

 you'll decide to come in here and you're like， ohC it's full。

 you might check this second one and say it's full。

 so then what you would do is be likem I don't know what I'm going to do I'll make a whole new block。



![](img/8df71110744777876a03ddccac4f83bb_41.png)

![](img/8df71110744777876a03ddccac4f83bb_42.png)

![](img/8df71110744777876a03ddccac4f83bb_43.png)

![](img/8df71110744777876a03ddccac4f83bb_44.png)

And what you might do is pull a few records from one block。

 block the second block and the third block pull records。

 put the10 in there and create a new br entry that properly reflects the ranges and so this might be9 to10 in the leftmost one there might be 11 through 11 through 12 and this one might be you know 13 through 16 so you can kind of see how it might be adjusted and then you got to shovel things。

 shovel things around， et cea etca， et cetera and so that's kind of the update process for the brn but the nice thing is if you have numbers if if you're building blocks that are kind of sequentially growing and the index is like a primary key the thing you're indexing is a primary key or a date these brs just kind of add on at the end and then it just kind of works and then you just come in in the queries are super fast and the size of the br is really。



![](img/8df71110744777876a03ddccac4f83bb_46.png)

![](img/8df71110744777876a03ddccac4f83bb_47.png)

![](img/8df71110744777876a03ddccac4f83bb_48.png)

![](img/8df71110744777876a03ddccac4f83bb_49.png)

![](img/8df71110744777876a03ddccac4f83bb_50.png)

![](img/8df71110744777876a03ddccac4f83bb_51.png)

![](img/8df71110744777876a03ddccac4f83bb_52.png)

![](img/8df71110744777876a03ddccac4f83bb_53.png)

![](img/8df71110744777876a03ddccac4f83bb_54.png)

![](img/8df71110744777876a03ddccac4f83bb_55.png)

P tiny so there's a lot of data mining applications potentially for a brn index that that might not be I mean。

But that just gives you the sense that Postgress has these capabilities and when in doubt。

 we will use the B3 by default。Now， there are two basic categories of these indexes。

We have forward indexes and inverted indexes， and I don't even like these words。

 I would rather the forward indexes word like normal indexes and。

Aray indexes the forward indexes like I know there's a key value。

 it represents a column and from that key value I will find the row it's like a logical key or a primary key and I've indexed that logical key or the primary key that's a normal index that's what we've always done for indexes。

Bee treeses， brs， ice Sams， they're all variations of I got a key。

 and the index actually sort of stores the key。So inverse indices work in situations where you have a column and in that column there's more than one thing。

You could think of it as a Python list of things or an array of things。

 or you could just think of it as a document that has lots of words in it。So in a sense。

 these columns don't have a single key。 They like， have an explosive number of keys。

 And what we're interested in is not necessarily to finding one row。

 but more interested in finding the entire set of rows。

 So if I'm looking for all the rows where S Q L is mentioned。

 and you could think of this as like it's sort of like a wild card per S Q L。Pcent。

 how could we do that efficiently， will you have to break the string into pieces and then index all the pieces and keep track of。

All of the words in any row。And which rows I。e blocks have those things in them。

 and that's what an inverse index is， okay？And so we have a couple of inverse indexes。

 we have a Gin index， which is the generalized reverse index， the G index。

 which is a hashing oriented index， and then there's this SP just which I want I't really want it to be the special one。

 but it's actually spatial Ie for longitude and latitude or for threedisional points or things like that that have some kind of a spatial spatial clustering and so the classic use case we have for inverted indexes is tech search and up next we'll take a look at the kinds of things that we use indexes for and starting with Google search。

