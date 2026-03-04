# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P65：1_PostgreSQL数据块分配机制.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to our lecture on Postgres Fulltext Ines so you can get this material online the PowerPoints。

 I've only got PowerPoints for the diagrams in case you want to reuse them because I basically switched my style in this particular lecture from to get all in PowerPoint to taking what I usually build as my lecture notes and just recording those and giving you my lecture notes rather than making lecture notes。

 turning them into PowerPoints and then giving you the PowerPoints I hope that you will find this to be more useful I'd be curious if you like this format compared to the all PowerPoint format。



![](img/77bcaf1035ce123f7d9f962561958748_1.png)

So can get these materials online and add whatever you want。

So first I want to talk about row layout and we've been talking about the create table and how schemas and how important it is to be precise about。

 you know if this is a short text column or a long text column， et cea， et cetera。

 and that schema becomes a contract because that's the way that Postgres can very efficiently store the data。

 and the amount of data that you scan is the sort of the thing that determines your performance。



![](img/77bcaf1035ce123f7d9f962561958748_3.png)

And so now I want to talk a little bit about how a schema is represented on disk so here we have a little tiny a messages table when we've used for a couple of examples or we have an email message。

 a timestamp and then some relatively large bits and you see that you know the ID is small。

 it's exactly four bytes of memory and the timestamp is eight bytes and then these other things are kind of long and we don't exactly know what their length is now remember we can insert and then we can update these and so you might have an email address that's four characters are 20 characters and replace it with a email address this 10 the size of a record can go up or can go down by on updates。



![](img/77bcaf1035ce123f7d9f962561958748_5.png)

And when we modify data， we don't want to rewrite the entire file because that's。

 let's just say a minimum a gigabyte file takes about two seconds， even on the fastest hardware。

 writing or reading a gigabyte takes several seconds of time。

And so Postgres organizes its disk files with free space on them。

 and they're organized into blocks of fixed length and by having blocks of fixed length。

 typically 8K，8192， 8 k blocks。

![](img/77bcaf1035ce123f7d9f962561958748_7.png)

They。They're able to sort of compute a block offset really easy so they don't pack the blocks in either they make fixed blocks。

 so they can read the entire block in memory， the block is often a unit of blocking the block is often a unit of caching so one of the things the database does is like actively used blocks end up sitting in the memory and so if you're hitting a bunch of queries at the same time and they keep using little blocks of files then those blocks will stay in the memory and so。

Everything that the database environment is doing is making it as efficient as it possibly can be。

And so for transactions， which we briefly talked about， they're often the unit of locking。

 so we think of locking a row and a block has， you know somewhere between 50 and five and 50 rows。

 maybe or even。Less than five， maybe two and 50 rows， but it doesn't matter， so let's take a look。

At the shape of a block right？ So here we have an 8K block。

 And remember that 8K blocks are they're all 8k。 and so they're a place on disk and they're stored one after another on disk and within the block there's some header stuff and other things that's in there。

 But the basic idea is the rows are inserted into this block sort of from the back to the front。

 Now each of these rows has columns， some of varying length and different rows have overall different length and the columns are in there。

 So then you insert another one and you insert another one and and the rows grow from the end of the block forward。

 and then all they have is little these offsets are like probably two to three bytes。

 probably two bytes and what they are is they're just like an array of where within that block。

 the start of a row is。

![](img/77bcaf1035ce123f7d9f962561958748_9.png)

And so they're small， the whole block comes in and then you can quickly go to each row。

 you can read them in order， you can read all of them。So and then the middle here。

 which is really not to scale on my picture is the free space so you have going from the end of the block。

 the rows， you've got going from the front of the block， you've got the offsets。

 now the rows are generally way bigger than the offsets now。

Think about this from an update perspective where we are so if we were going to just take this a row and there's like 10 characters and an email address and we're going to replace it with a 15 character email address。

 we can shift just a little bit of data， you know， five characters we're going to shift everything。

 five characters to the left and then we got， we make 15 characters and then we put the new email address in where it belongs。



![](img/77bcaf1035ce123f7d9f962561958748_11.png)

And so and then we just rewrite the whole block and we've lost some of the free space。

 same thing would happen if we rewrote an email address with a smaller email address。

 we'd shift everything。Actually we might not shift everything at that point。

 but the point is is we can make small changes to this now again。

 in my picture free space is not to scale because you don't want to make free space in my picture it kind of looks like it's 70% of it。

This is a block being filled up， but the idea is is that we can make tiny little modifications and then change these offset values and then rewrite the whole block to disk the whole block right in。

 we fiddle with it in memory which is a very cheap operation and then wewrite it back out to disk now you might say。

 well what's the best idea a block size and they go round and round and round and there's a lot of things in Postgres where just accepting the default is probably what you want to do and so 8k is generally the default。

If you have a block that's too small and then your rows don't fit well。

 you sort of fit like one row in a block then you got kind of a wasted free space if you fit like if you have two larger blocks then you're pulling too much information in and out just to like read one row and you start using up all your memory。

 you're caching can if you have 8K blocks or 16K blocks you can cache 50% of the blocks。

 50% fewer blocks if they were 16K。And so you can go read up on that。

 say what's the best Google and say what's the best block size for Postgress and they'll tell you that it's probably 8K and the next best block size might be 4K and it has to do with the fact that solid state disks unlike spinning disks。

 so spinning disks have rotational delay and then once you get to the data on the spinning disk pulling in 8K is smarter than pulling in 4K because the rotational delay is by far the greater consideration in SSD disks there is no rotational delay and so then what happens is the thing that dominates is the actual amount that you transfer。

And so that would advocate for smaller block sizes on SSDs and larger block size on hard drive drives。

 The problem is if you make the block sizes too small。

 then you get fragmentation and you can't do some of those dynamic things where you're either inserting a new row or you're taking some data you're updating a row and so the too tiny of a block size and then you get either too much free space because you can't fit enough rows in a block or you get too little free space and then you know you pack rows in and you run out of space and you do an update and then you got to move stuff all around in your database and it's not good So there's a lot of different ways to think about this。

 but the key point to take away from all。Of all this is that that we entire。

 we read entire blocks into memory， so we don't really know where a row is exactly on disk。

 but we do want to know where a row is with in a block we know that this row is in this block then we read the block in and then we scan through the block and then find the row so we can't go straight to a row。

 we can go straight to a block。So indexes， which is what we're really talking about now， indexes。

🎼Our。Are basically a set of hints。That map from a row that we're looking for to which block those rows are in。

 and that's what we'll talk about next。