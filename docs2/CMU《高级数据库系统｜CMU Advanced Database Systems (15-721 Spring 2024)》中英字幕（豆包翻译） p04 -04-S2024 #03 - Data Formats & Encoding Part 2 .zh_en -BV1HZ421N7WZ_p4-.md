# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p04 -04-S2024 #03 - Data Formats & Encoding Part 2 .zh_en -BV1HZ421N7WZ_p4-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/fffc11365ff6938ed8a0d8509c0bf581_1.png)

🎼。Let's it started。🎼Bt of with us today and then we'll finish up talking about the proposal presentations coming on this week on Wednesday。

 Okay， so let's hold off any questions until then。All right。

 so today we're going to pick off where we left last class talking about。

what data files actually look like what actually data looks like and so recall from last class we talked about what these different storage models would have。

 NSM or row storage， DSM column like pure column store and then as I said everything is pretty much packs these days you're going to divide your table up into horizontal partitions to row groups and then within each row group you're going to lay all the bits or bytes for each column continuouslytiguously before jumping into the next column so you get the best both wells you get the column store contig values。



![](img/fffc11365ff6938ed8a0d8509c0bf581_3.png)

but also the spatial locality of a row store。We then talk about all right for the different file formats。

 what's actually inside of them， what additional things we're going to record beyond just the data itself。

 So we talk the metadata keeping track of what' always in the footer jumped to offset in the row groups。

 the format layout specifying again is it row store comm store what is the actual the nesting structure within that type system we sort gloss over quickly to say there's some primitive types。

 logical types codingding schemes we spend a lot of time and we'll talk about mostly today。

 different ways to encode the data， naive block compression or general purpose compression is taking whatever you produce from in your file from the lightweight encoding or these schemes here and then throw snappy or Z standard or Gsep at it。

 actually never use Gep snappy or Z standard Zmat B filters and then we rush through the shredding stuff So I'm gonna spend a little time in the beginning today going over that more detail because again I think this is a neat idea from。

The BigQuery Dr stuff， and we'll see these again later in the semester。

And then we'll kick off the conversation about today's paper。 So again， real world data sets。

 there's a lot of JsonN out there。 And if you're at Google， a lot of protocol buffers and。

If we distort the a JSO document。As a varchar as a text or blob inside of a column， you know， yeah。

 we can run Json functions on them to extract out the structure from it。

 but that's not gonna we're going to lose all the advantages of having a column store with packs layout and be able to vectorize execution。

 So instead what we want to do is is split up or blow up the Json document for every single tuple and store the paths within that document as separate columns。

 So。You know， the no SQl guys talk about， oh， this is these are schemaless databases。

 you can define your schema later。 And that just means that you don't have to call create table。

 And specify， here's exactly the columns I have for different types。 You just throw Json on it。

 But inherently， there's always a schema because it doesn't make sense to have like random applications。

 writing random documents into a table because then nobody can make make sense of it。

 So that the documents maybe be putting and， maybe not have all the same fields。

 but at least there'll be enough overlap in the structure that we can break things up and then stored as columns。

So again， I'm gonna focus on go through a walk through the record shreadtting from Drel。

 And then we can briefly talk about length and presence encod。

All so the basic idea of shredding is that we're going to store paths in our columns。

I sorry for each path， I want to sort it as a separate column and then we record how many steps DPR into a given document for that hierarchy。

And unlike in length and presence， we'll see in the next slide。

 if something doesn't necessarily exist， doesn't mean we need to always record that it's actually there。

 where in length and presence， you do。So there's going be two additional columns we're going to find。

 I think of these are just going to be integer columns that we then do all the encoding impression compression stuff we talked about before。

So adding additional columns， yes， that's more data restoring per attribute within our JSN document。

 but again， we can compress these things pretty well and avoid a lot of the bloat of the storage space。

So the first one' is going to examine into the definition level。

 and that's going to determine how many it's going to keep track of how many optical elements existed to get us to the current path we are in our hierarchy。

And the repetition level is going to say if it's a repeated structure。 like in our scheme up here。

 we have two repeated structures。 We have the， the repeated group name and the repeated group language。

 So how many times have we seen those， those repeated groups at that given level repeat。

So let's walk through the example of this simple document here。 Again。

 this is what roughly what protocol buffer looks like。 or think of， defining a schema on。

 on a Json document or XM L。So we're going to walk through this document here and we're going to scan through as if we were loading it into our database system and show how it's going to generate the attributes across the different columns in our shredded model。

So the very beginning it's easy right we have a document ID。

 so we have a table that corresponds to the document ID path that's at the root or the top of the document。

 so then we just insert a new record there， but at this point here there's no repeats before us so the repetition value is0 and theres nothing there's no other there's no other things in the path before us so the definition is zero。

Then now as we scan down， we hit the first nester structure， we have name and then within that。

 we have a group called language。 So now we see our first entry for the code here。

 So we're going create a new new column for our shredded document where we have the value that's being stored。

 the repetition value is set to0 because where' the first the first language。

Object or group that we've seen at this level in the hierarchy。

 And then we set the definition to two because it were， two levels deep。

They we get out the country and now we see that we can create a new column， The value is US。

 that's easy。 repetition is zero because there's nothing before us。

 and then now we're sort of three elements into our path。

Then we go to the next group for language And so again， we see a code。

 we insert that here where for the second again starting at0。

 with's the second repeated group within this hierarchy。

 So we set that to one and then our path to get here is two just like it was here because we got to go from name to language to code。

Then now we don't have a country。 So in this case here。

 because we at least have something at the grip level within the language。😡。

We have to put an entry here right again， the same as before， wherere one into the repetition。

 and then we have two elements to the path gethettos here。 but again， because there's no value here。

 we set it to two。Then we go down to the URL URL here。 And again。

 repetition is 0 because we're the first。First name in our group， just like we were in document。

 but then our death is two because it went from name and then to URL。Just as we were over here。

They we down down to this group。 This is just name with nothing else。 So we put， sorry。

 it's just a name with the URL and no other attributes for the the language。 So， sorry， So we。

 we add our entry into here。Right，Reetition one， because we're the second element in the repeated group。

 and the path is two to get get us there。But then now weve got to put placeholders here to say that there wasn't anything within the repeated group for language。

Right， so repeated group  one because we're the one。 This is the。

 the second group within the that level of the name。

 And then the definition is one to say the path is really one to get there。

 Like it's the same as the path as。Actually was that too， Yeah， because it's one down from name。

 So if you want to know how deep you actually are， as you follow along from this。

 you could then get that and see that you're actually three levels deep。Yes。We have current country。

 that have a definition of。And why country would have a definition more clean than theyre the same。

Yeah， his question is why is code going back here， Why is line the error doesn't line up PowerPoint as being stupid。

 So in this case here I add English US， the definition for the path is two。

 but then when I add the country， the definition passion is three， as he said， the code is required。

 the country is optional。Other questions， sorry。Yes。

 then why does the like null when we add like for the second definition of like the language？

We had known and that death was different。This question is why this example here。

 why is the definition2 if it's taking place， same place as the country。Because it doesn't exist。

 I think that's why。RightThat you're not moving down even farther。Yes， many。あそやってく。The question is。

 is it determined in the point of reversals do you have to go to？ the definition is like。

 how many steps are you down within the path that gets to where you're at， And so if it's not there。

 it doesn't count。It's my understanding of it。Yes， sorry is there any benefit from doing this sort of repeated indices versus like？

Maybe he's like storing like a list of pointers。His question is。

 is there any advantage of doing this， storing the structure as columns versus storing pointers？

YouNo， feel like we have this click。啊。オルピー？Is this better than just like storing？😔。

Some sort of like very small。Column that has just a list of pointers to go to the next part。

What are these pointers， sorry？Some way to get them other。I guess it is a similar book。

It's representing a list as just。😔，the idea is that think of it you had a query。

 the reason why I was restoring this structure here is that we want to be able to go through the column itself without having to go back to figure out how we actually got there。

😡，When we do a select query。 So， so I don't have a select query here。

 But think of like select star from table where name dot language dot code equals。ENUS。

So I can just rip through this column here。 I don't need to refer to any any of the other ones。

 And when I find my matches， I can then use that to figure out。

Where do I need to go jump back in the offsets if I want to stitch things back together？

So is there any overheadheaded like trying to reconstruct？We joining more。Back together。

say steady again So again。 I what I， I there significant overhead and trying to join all of these column original This question is what is。

 is there a large overhead of if I have to then reverse this shredding。

Taping it back together to go back to the original form。 Absolutely， yes。

 But the advantage is that is that when we when we want to do lookups。

 it's already broken up in a form that we can find things very quickly。

So if you know that you're going to be looking at these very specific things。

 why don't you just break out the column them？Yeah， this is what they're giving us。

Some asshole developers， I'm going to you JO， and we've got to handle that。喂。

We haven't talked about how we're going to handle the type either。Right， like。

 and we'll see this in snowflake。 Snowflake， actually try to figure out。

 oh I see these bunch of strings。 Let me I'll， I'll keep your original Json， but also make a。

 I'll synthesize a string column for you。 A v chart or whatever the type is。

Or is this something just about the execution？His question is does SQL know about JO， I mean。

 the SQL standard has JSON， yeah。Has Json construct or data types。 But like， but again。

 that's the sequenceequ at the logical levels。 sequenceequ that the programmer sees underneath the covers。

 right， we， the data system is free to store data anyway that it's once。

 And Drmel made the decision to do it this way， because they want to optimize for the common case of just doing lookups down paths。

 right。Extreme example is everything's J。 Everything's a blob。

And then I have to parse it everything when I to run a query。 This avoids all that。

 You're basically materializing as if you parse it ahead of time。Okay。So in the sake of time。

 I don't want to spend too much on this， but you kind of get the better general idea that we're breaking this up。

 we're generating columns， and we can use that to figure out the path as just scan through。

He's been the ENGB one。This question is the Great Britain one。We're now here。

RightSo we now have a new name。Right there。We have name is， is is repeated group。 And group。

 we have the the country。 Now we have Great Britain here。 Our repetition is one。That might be wrong。

That's actuallyYeah， this is from the Drreel paper。 I had to fix some of these things。 Yeah。

 I think is the are incorrect the paper because paper had like different values So the second row the E because isn't defined。

😊，How many times repeated the level or language repeated all we'll fix that later so yeah。

 the typo here is that the number of times the group have been repeated length at that level yeah。

Again， load load details。A lot of details。啊。Maybe not entirely matter。

 It's the idea of like taking JON， taking something breaking up because we can do this at the physical level。

 and that'll make queries run faster later on， and the application programmer doesn't know doesn't care。

right， again， in the sake of time， I'm going to skip past。Length and presence。

 basically the idea that you're justoring。哎。You' you can always walk down as if for each level。

 you're just going to record whether something exists or not。Right。The Drreemel paper we later on。

 there's specific experiments they showed that the shredding one is better。Okay。

So let's get back now talking about the the where we left off。 last class。

 talking the big picture of these these barque or showing how they have different levels of sophistication and complexity in the。

 in their implementations of how they encode things。 but the。

These file formats are really designed from a different hardware era like 10 years ago or 12 years ago now。

 parquets in Or 2011， 2012。Back then， the network scene was always the slowest thing。

And then disc was slow。 And then memory and everything and the CPU stuff all that fast。 So you。

 they were making a trade off to， to use heavyweight compression schemes like。

D standard like Spy because that would reduce the size of the block。

 they were fetching for data files。But now the hardware has shifted such that network is actually really。

 really fast。You can get on Amazon， I think 100 gigabyte Internet connections for instances。

 and this is not that much。So the trade offs and design decisions that the parkingane or people made。

They're not wrong as if they were doing something stupid。

 it's just the Harvard landscape ship is so much that we need to revisit what they were doing。

So there's a couple other problems in these formats that are going to be a problem for us when we want to start doing。

You know， vectorizing the operations on our。You know， inside of our engine。

 so the first is that parane or going to generate variable size runs。

they're making decisions on how to encode different things at different parts within a column chunk。

 and that means as you're scanning along， trying to decode it to find data you're looking for。

 you have to have these conditionsals that figure out is my data this way or that way and then sometimes that might be a certain size versus another size。

Right。Well， that's bad for Cindy。 Does everyone know Cindy is。 Is everyone taken 4，18，16。

 because who here doesn't know Cindy。Okay。In the paper， okay。呃。

WellLet me give you a quick crash course。Everything you need for this， everything you know。

 All right， single instruction， multiple data。 So its these class CPU instructions。

 that you can get a modern processors that allow you to do multiple things。 Sorry。

 do the same operation or multiple pieces of data at the same time。

Contrast this with CISD in plane's taxonomy， single structure， a single piece of data。

 like x equals 1， that's a single structure and that value1 put into a register over x， right。

So the say when to start doing things like matrix tradition， right x plus y equals z。

So the way we typically write this using S instructions is you would have a little for loop。

 We just iterate over all the elements of I or sorry elements of x。

 assuming that x and y are the same same length。 And then I'm just going to add them again and sort in Z So with Cs。

 again， you're just literally running through the for loop。😊。

And in each loop you're adding one by one。 Yeah， you can unroll it， that'll speed things up。

 whatever， but it's still at the end of the day it's doing single instruction per each level within vectors。

So that with Cdy is that I can break out the the pieces of data I'm trying to operate on into chunks。

 lanes that I can store in these Sindy registers。 So in this case here。

 really simple to say I'm sorting 32 B integers。 And then I have I'm putting four。

4 values in a single register。 So I have 120 bit registers。 the current。

The largest register you can get now is 512。 The fascinating paper talks about a a hypothetical 1024 Sney register。

 that doesn't exist。5，12 is the state of the art。 And we'll cover that more later on。

 So now what I can do is within a single instruction。

 I can just the CPUO will take this register and that register。

 add them up and then write it out to another register。And now that's one instruction。

 do the same thing for the next block or the next portion of the data， again。

 another Cindy instruction to go add it up。So what was？Before this， excuse me。

 just counting the number addition instructions，8 instructions to add the X and Y together。

 I can now do this in two。I'm ignoring the cost of getting things into the register and out of the register and we'll see problems of AVX 512。

 where actually the CPUO will slow itself down when you start using AVX 512 in some cases so it's not magically magically free。

 There is some work to actually do this， but that's the general idea of what Cindy is。

And we'll see more about this next week。And then a few lectures after that as well。Okay， so。

But as I said， these registers are always going to be like 128 bit，256，5，12。

 and it's going to have every element within within that I'm storing in a lane has to be the same size。

 So I have variable length and codingding。 I got to put everything now to the same length the same size before I can load it into the register and that's expensive。

The other problem with these formats is that， as I said before。

 they want to eagerly decompress everything。 so they don't expose to you the dictionary into the executionion under your database system to allow you to start to look up on the dictionary itself。

 when you iterate over a column chunk in Parquet and or， they give you back the decompressed values。

Likewise， if you're using block compression like a naive scheme like Z standard or Spy。

 you can't see anything or the data system can't see anything inside of that compressed data because it's opaque to the database system because Z standard and snappy to have their own encoding scheme and we can actually interpret any values within the。

Within the compressed data。The other problems are going to be in some encoding schemes like specifically Dltacoding and runline encoding。

 that there will be dependencies between the adjacent values in our column chunk。

 and that means also we can't use CD because there's no way to pass data from one element to another element if they're in the same register。

Delta codings is taking the difference between your neighbor， the preceding value in a column。

 So if you load that up in the semime register， you can't do that Delta edition very easily。

And the last one is going to be which is not really that big of an issue for us at this point in the semester。

 but the port ability of the implementation because all theres there's a lot more hardware out there。

 a lot more vendors between arm and risk 5 and GPUs， T Ps and Zons that。

even actually within just neon or arm and Zions themselves。

 there's all these different versions of the ISA that have different features of Cindy Cindy capabilities and there's no guarantee that if you write low level and transit code like the low level instructions to do Cindy that one system is is always going to work on another system。

 So ideally want to rely on the compiler to figure out how to vectorize the stuff for us。

 But a parque and orRC because the certain design decisions they made， they can't do that。Yes。

 is there some kind of library that would just？You can use like these agnostic functions。

Representing some， the library would then dispatch to this ISA this way。His question is。

 are there libraries like Lib S D， Yes， are there libraries out there that can abstract away the low level details of certain operations and therefore。

If you write your code against that library， then whatever ISA you land or whatever harder you land on。

 they can do it for you。Yes， but I'm not aware of anybody actually using those least in databases again we have friends on the inside I ask them whether they're using intrinsics or some kind of abstraction layer。

 everybody's writing intrinsics。I don't know what DrB does though。

LikeThey are trying to be very portable， so we could look at to see what they do。Yes。

 why are dependencies between adjacent values？So his question is why dependence mean Jason value is bad because thing of like。

 if I have。So I should go back to my SIdy example here。So go back here， right say that。

These are just raw encoding， uncompressed。 But say it was Dlt uncoding， right。

 And so starting starting at the top， right， it's 8。 And then the next one is 15。

 right because it's 8 plus 7 or something right， So if I。

 I can't load that in my register and have it do arithmetic right next to it the thing that's next to it。

 You can you have to copy into another register and start know， shifting things around。

But it doesn't pho sort of solve this。Yes， we're getting there， yes。😡，啊。

You a bad movie writer because like you basically give give the the end， know。

RightIt's like telling the ending of the story to the beginning。 get this set the mood。Yeah。O。Yes。

 the answer is fasts did solve this particular problem。Right。

 so I'm gonna talk about three different schemes today and。

The better blocks and the fascinating ones， these are brand new these papers just come out in the last year。

 Biweaving is an old idea from Jagnesh Patel， the other data here that came out almost 10 years ago。

 But I still think it's worth looking at because it's a completely different way thinking about how to store data。

 So I want to cover that a bit。 But the way they about is better blocks is going be like parque plus plus It's still going be in the sort of the same。

Overall flavor of parcade just with better lightweight encoding seams。

 and they'll do nesting in with a sort of recursive algorithm tries to figure out the best nesting scheme automatically。

 fast names the paper how you guys read again it's just a different way thinking about actually how to store data in a way that people really haven't considered that much。

 people have been sorting data all the time that's a trick。

 like to purposely go out of your way to store it almost arbitrarily random order because that's the best way to then decode it at runtime again。

 that's it's not a common way to think about how to build data systems。 And again。

 the main takeaway from all of this is gonna be the Sgel layer。

 the application programr doesn't know what we're doing underneath the covers get all the benefit。

 things will be faster and cheaper and more efficient but they don't have to rewrite anything in their application code because SL is just gonna run just fine that the data system will handle all that for them。

All right， so we're going to do each of these one by one。

So Better Blocks is a PACspace file format out of TU Munich。

 we're going to read a lot of papers from the guys at Munich。

 they have a system called Hyper and a new one called URA。

 they have very good data professors there that probably some of the best people in the world。

 so this paper came out of their group last year。And so the idea with better blocks is that it's going to do more aggressive nested encoding schemes than with parquet and or。

 Parquet only did dictionary encoding for strings， but it didn't try to do any additional optimizations for the codes that came out of them or try to be more sophisticated and have at least for integer columns and try to figure out should I compress it this way versus that way。

 but it was basically static heuristics。And so when better blocks。

 what they're going to do is they have a more or less a greedy algorithm that's going to figure out for each column chunk。

 what's the best encoding scheme。By looking at a sample of the data。

 I let's talk about how they generate that sample， and then then they apply that encoding scheme。

 which may produce more columns。 and as long as they're of a fundamental type。

 you then go back and run the same algorithm and figure out what's the best encoding scheme for those derivative columns that came out of it。

And so you're still going to be able to do the。You basically get almost all the benefit of something like Spy and Z standard。

 but you can still natively operate and decode the columns without having tocode decompress everything And so that means the purpose they're going to not use Spy as Z standard for this same thing with fastl。

 they're not going to touch that stuff because it's too slow and hides everything with the data system。

Now， interesting interestingly， better blockslocks makes the argument that they don't want to store the metadata。

 the schema and information about what's in the file in the file itself。

 And they said that's better left to some some management service。

 but that breaks the portability capabilities we talked about before。

 you just give someone a parque file and there's everything you need to decipher what's inside of it is in the file itself。

 I would chalk this up to more of a philosophical design decision argument rather than like oh my gosh。

 like they're wrong or the right。 Some cases make sense in cases that doesn't Yes。3设百。いやご全で。

His statement is。If you're saying if it's embedded that you're safer or you're not。I mean。

 so the metadata is corrupted and do。呃。Right， but but so yeah， so his's argument is like， okay。

 if the if the file gets corruptpeded in some way and it trashes the metadata because it's stored in the file。

 you can't do anything。 But the flips I would be if you're storing out your metadata as separate files and some other service or it's just there's more moving parts that could cause problems？

 Furthermore， again， we say we're storing an object store， Amazon's replicating all that stuff， like。

 know， I think three or four times or six times like So the。The likelihood in all honesty。

 like the file is going to get truly corrupted and I have no。And， and it can't recover。

 if it' was mission critical， then I have， I have allsite backups。 I'm I'm doing， you know， if it's。

 if my company fails and my， my business fails because this like one file gets corrupted， then like。

 that's my fault for not like making sure that like， you know， it's written stone， you know， I mean。

So I think value would the argument there。Yes。Since this uses multiple encoding algorithms。

 does it not have the same issues as Oc where？ごち調整。あチこで。Yes， so she's correct。

 the the thing we talked about last class was in OrC。

 they had a bunch of different encoding schemes and as you ran your。You know。

 as you're trying to decode things， it's trying to figure out like on the fly which decoding scheme should I use't going to start the same problem My understanding is though within the column chunk they're picking one encoding scheme。

 whereas OrC is trying to be clever on smaller runs。

And I will say the only compare against parquet in this paper they don't compare against org。

And then we。We didn't for our experiments in our paper， we didn't compare against this。

 but that's an open question。Yes，Thanks the。So comment is the argument that they're making this paper about why they want to store the metadata as a separate file is that it allows them to retrieve the file。

 which is much more than the actual data and then look at the zone maps and information and figure out whether even need to look at the file。

 but as we said last time like with S3， I can go get a range。

 So whether whether getting that metadata is the footer of the file or。

Like the separate file from our perspective it's the same。Yeah， yeah， yeah， yeah。O。

So let's look at all the encoding scheme that they have a bunch of these we've already seen two of these we'll cover more detail so we've already know about run like encoding one value is like the extreme example or like literally your column of 64。

000 tus has one value right you just store that once again， it's like the extreme case of RLE。😊。

Frequency encoding we didn't talk about。 but this comes from IBM's DB2 blue system from a few years ago。

 Basically， it's like you store the。You look at your column and you figure out what's the most common value。

 like what's the one value that appears most often， store that separately。

 and then you have a bit map to say how many times where it occurs in the column and then all the other values that are not that top value。

 you just store them in an uncompressed uncompressed way。

 but then you feed that back into the encoding scheme to compress it further。I think like。

What's a good example of this。系。You know。You're at a。Yeah。Everybody loves for like one person。

 So you just store everyone。Lo goes yes， store that name of bitten of where that occurs。

 And then for the few people that don't like。You destroy that separately。

 right It's a stupid example， that's a basic idea。framera of reference a bit packing we talked about last time again。

 it's like Delta coding， they're not going to do a delta coding。 this is the variant of it。

 where you just store what's the min value of within a column chunk and then distort the delta from everyone's delta to that global value。

Dicctiontionary codeium covered pseudo decimals， we' talk about fixed point decimals。

 but the basic idea is that they're going to convert floating point numbers into integers by just figuring out where the decimal point is and store the integer version of that and then what power of 10 you need to convert it back to a decimal。

Right。I'll briefly talk about these in a second。 but this is basically FSST comes from the Germans and theductDB people that allows you to do compression on strings。

 But instead of doing dictionary encod where you have a code represents the entire value of that string。

 you can do separate codes for individual bytes。IThink of you have a column of a bunch of URLs and all the URLs start with HTTPS so I could store the separate code just for HTPS and then additional codes for the other parts of the URLs。

s in a second。 And then roaring bit mapps is a way to do basic compressed bit maps。

 But they're gonna use these for nulls and exceptions like， like the。

The frequency encoding of I'm keeping track of when what locations is the most freaking about it occurs。

 I have store that as a wrong pit map and again， we'll cover that in a second。So again。

 no doubt on coding because it's not CM friendly， but then again the fast people will fix this。

So the selection algorithm works like this。 So basically that you're going to collect some sample data from your column。

And recall in case of OrC， OrC was using this run ahead buffer to look at the next 512 byte to figure out。

 okay or sorry， 512 values and figure out what's the next encoding scheme I should use。

What they're going to do is assuming you have the entire column chunk ahead of time。

 and you're going to sample from that uniformly and then use that to determine what's the best encoding scheme for this given column chunk。

Right， but you just can't do random sampling by just jumping in different locations because that'll make run length encoding look look terrible。

Because you're gonna to miss that continuity or repeated values in a sequence。Likewise。

 if you just then grab the first 100 values。Then it's going to make other schemes look bad because。

 again， you may just hit a bunch of repeated values in the beginning and therefore run like the code it looks great。

 but that's actually not the most optimal scheme。So what they're basically going to do is theyre going do they're going to jump to 10 different locations in a column chunk。

 which is 64000 values。s basically 1%。 And then when they jump to that location。

 they're going then grab 64 values。So that gives you sort of the spatial randomness within the column itself。

 but also the continuity of contiguousness that you need to figure out whether early makes sense。

So then you run the algorithm， figure out what the best encoding scheme is， and then， as I said。

 sometimes the encoding schemes produce more outputs。

 and then you can just feed those outputs back into the next encoding scheme。Yes。

 is there something very special about the？Is there something special about the greeting algorithm as opposed to what？

Are they trying certain compressions， theyre trying all of them？Yeah。

 so like so say my original data is this integer of this vector of strings。 So this's column strings。

 So this is the algorithm， right， it's an integer。 So they're literally going to try all of them。

on the sample， and they say roughly it's about 2% overhead of the compression cost。

Presumably this all don't really we load the data。Expenive just in at the start。

Right so his comment is。Because basic question is when are we doing this。

 It's when we're loading the data into the database right。

 And so the encoding is an expensive cost because that we're willing to pay that cost upfront once because that's going to make the common case of running queries run faster。

 Absolute yes。So they're saying the running this algorithm is a 2% overt。

And I think that's fair trade off。Right。Right， so in this example here， again。

 they can can just be raw uncompressed encod。 Theres sort of invitation to do。

Vectctorize a partial frame of reference and then bit packing one value we talked about and then dictionary。

 So let's say this my stupid example here， it picks that run length encoding is the fastest。

 Well then again this is can produce out two columns now， one for the actual values。

 and then the next column is the actual length And again they'll recursly try three times So every single output as long is it something that can be compressed again。

 they'll feed it back into the algorithm and try it again。Up to three tries。

In the case of v lamb with like bit packing， there's nothing you can do after that。

 the algorithm terminates。So my example here is for integers。

 but then they have basically decision trees for strings and doubles。

And that's those are the core data types that we care about in databases， yes。Know him， yes。

Does it ever go back and correct it seems supposed like the sample is like way off？His question is。

 do I ever backtrack and say， oh， after recursly applying。

 it turns out that what I'm doing is the optimum choice is actually another path down now。

Not even it's like the sample is not represented at all。But how do you know it's not representative？

Once actually they started。Oh oh yeah so like David is basically if I started encoding and I realized this kind of sucks。

 this is not way it's working， it's not working out as well as I thought it was going to。

 do they ever go back and try it again， I don't think they do。But。I don't know。That's the same， okay。

I guess it's also like what is the cost savings of like only looking at 10% of the data they're looking at 1%？

So% looking at the whole data， flying all of them exhaust search phases across the entire data set。

Yeah， I mean， like it's exponential fairlyly， but we're just sampling up like % anyways。

Under time is slower。Wait， I want to block a load one。One terabyte of data you want to。

It only one terab。No， would say one tearab ride。嗯。Think no， extreme。 It's1 petabte， right， Like， So。

 so， yeah， that's not feasible。Right。And also， too， someone's got to pay for the compute。Right。So。

 I'm。Again， it's a trade off。I'm going to pay this computation overhead。

2% seems reasonable to me in order to make queries run faster。

 And so if you do his example or your example of like just try everything or backtrack。

 am I gonna get another， know， what is gonna be that that percentage improvement。

 Probably not worth it。Yes。ncludinging is。我哋噶 they they老。When I was running the code。

 there were some messages that oh this enco produced more。不さん。missionary。Yes。Unpress the data。そで野ろ。

So his statement is when he ran the code locally because sort like they try encoding scheme and then they start encoding it。

Like。Like how far into it will they go like before。For example，Yeah。And then if it's kid。No know。

 but but so so to you， you be saying basically that you set set the recursion to death the， the。

 the default is three， but then it's， it's it。It's the based on the sample， right。

 not like he's saying if you scan the data and realize you got it wrong。The sample said one thing。

 the real data looks something different。 Do you then roll it back。 they don't do that。

 You're basically saying on the sample itself， they can roll back。Which is fine。

you the but on the sample of the the real data。 O， they robot back the whole thing。 Oh， okay。嗯。Again。

 their column size is  64，000 values， so it's not that big， you can do everything in RA。Okay。

All right， so going back， these are all the coding schemes that we had。

 I want to briefly talk about FSST because we'll see this when we talk about DDB and we'll see this in。

😊，When we talk about how to like。PasPas intermediate results from one operator to the next。

 this will come up and then roar bitmps， this is just a better way to do bitmaps。

Right so FSST again comes from this 2020 paper， it's the fascinating guy， Peter Bos。

 it's Victor Lyce from But Better Blocks， and then Thomas Norman is probably the best data research in the world who read a lot of his papers those three got together and decided let's go build a compression scheme for strings that allow for fast random access。

And again， think of like dictionary encoding， you're taking the entire string and representing with a single code。

 but now you can't actually do partial lookups on that code to find prefixes and other things because you have to go look at the entire string itself。

So the idea here is that they're going to replace frequently occurring substrs up to 8 by with 1 byte codes。

 And so all the values once they are encoded in these， these， these。In the FSST symbols。

 they' all going still be the same length。 And so you have to do。

You have to do some tricks to figure out to record like this is the end of the string。

 therefore don't look at any more symbols。So the way they're going to generate the simple table is actually kind of interesting right。

 because it it's sort of an MP complete problem to figure out what's the optimal。😊。

The optimal set of symbols that will produce the smallest number of codes and the most compression benefits。

 So rather than try to do like they mentioned cent dynamicyn programming or something more fancy。

 they just use what they'll call evolutionary algorithm that anytime you think you have a good symbol edge you're constructing the symbol table。

'll they'll put it into this hash table If an entry's already there。 they kick it out。Right。

 so it's not like the。The linear scan or linear probing hash tables that we talked about before or the chain hash table you can if someone's in your slot。

 you keep going till you find a free position， they immediately kick out whatever's there。

 the idea is that as you're constructing the symbol table。

 if the things that actually really matter a lot the symbols that could provide a lot of benefit。

 if they keep getting kicked out， but then they're still used again。

 then they'll at added it back and that over time you end up sort roughly with a reasonably good set of symbols。

 yes。Is the output fixed length？啊。For the yes， the bike codes to be， the codes are one byte。

But the substr could be variable length up to 8 by， which is fine because again。

 the columns of be fixed length。Right， so we know exactly the number。 you know。

 And so the question is like， if what if you have a。

You know what if you have a symbol like HPS and so you have a bunch of URLs that use that same code。

 but then someone's got a weird URL that it's just HPS。

 then you need to keep track that this thing is only。

 you need a way to denote that the string is actually terminated。

 so don't interpret any other bytes remaining in my fixed length portion of the value。

Because otherwise， you could go look up and add start adding more symbols that arent actually in the visual string。

So again， this is just a better way to do or it's actually the。

This is basically what Z standard is or L Z 4 or snappy。

 They're basically doing the same thing inside of their， you know， in their compression scheme。

 But again， it's opaque to the data system。 This is now an explicit scheme where we can expose the symbol table to the data system。

 And we know exactly what the the。How to match the codes to strings。

AndSo you can do all the same tricks， you can do dictionary encoding to find prefixes and other stuff by just looking at the symbol table and actually looking at the real values for some types of queries。

Yes。cursive and that like if you have like a fight that you get out of the symbol table。

It could also encode code like a substr。So has like 16バ。The question is。

 is it possible to have a code refer to another code like that contains code。

Oh his question is could you have a situation where the inside the symbol table is another code。

 so don't interpret all of the bytes in in the original string as as the string itself interpret some of them as actually another code that you'cur lookup。

 then how do you record that you should go that portion of the string know should be another lookup。

I was asking that's something。So a lot of the design decisions that they made for this is。

 is like this example of like， okay， you don't do the linear probing to find a free slot。

 You immediately kick out whatever's in there。 They did this because you can now you can do this all in Cindy。

Because you can't have conditionals， you can't have loops in CMD。So by just doing everything like。

 okay， here's the exact instructions I're always going to do if someone's there， kick it out。

 just overwrite them。Then like you can， you can vectorize all this。 So in your thing。

 you would have to have some bits that somewhere that says， oh， by the way。

 at this offset for this string， don't interpret it as a varchar。 don't as an ASI character。

 It's actually a code。 You want to feedback back into it。 You wouldn't be able to do it with。Okay。

 again， I don't have a demonstration of what this looks like。

 I can post something on Slack when Peter gave a talk a few years ago。

One thing that is cool that does show up a lot in data systems now these days are called Roaring bit Maps。

 at of curiosityity who here has heard of roaring Pi Maps before。Yeah， very very few， right。

Basically， it's a way to store a bitmap index in a。

With different data structures based on the the the。

How often bits are being set to true within some portion of the range that we're trying to record。

 right， So again， a bitmap index can tell you something that just at some position is a bit set， set。

 yes or no。He can uses a bloom filter， like a foret membership and so forth。

So the dense chunks were to store these as uncompressed bit maps because there really isn't any way to make that better right literally just the bits where you can then turn back and recompress it again with nest encoding with RLE。

 we'll ignore that for now。 and then the sparse chunkunks will just store them as bit packed arrays of 16 bit integers right。

So there's a lot of implementation of this and pick your favorite programming language。

 There's a lot of different data systems out there that are use this。

 Plosa is the open source version of a system called featurebase。

 and featureb basically stores almost everything as a lot of data as roing Bimps。😊。

U in the biteizing techniques， we'll see in a second。But here's the basic idea。

 So say again we're going to split up the range of values that we're going to support into in this case here。

 I have four chunks so for every single key I want to set to true or look up to see whether it's set to true。

 I'm just going to divide it by2 to the 16 and that basically tells me which path I want to go down and then within the container within that range。

 I'll just I could set something to true based on how it's actually being stored。Right。

Then what happens is in the default setting， if the number of values that have been set to true within that range is less than 40。

96， then you just store it as uncompressedor array。

 otherwise then stored as a bit mapap right So say I want to set to key equals 1000 I'm gonna to divide it by 2 to 16。

 I land in this partition here。 And then now I keep track of the number of bits that are set to true in this container。

 at this point at 0。 So I'll just store stored as a bit packed or 16 bit integer with Vi value。

Now I'll say I want to store this key here， do the same thing divided by2 to 16。

 I land in partition 3， but now I see that this is being stored as as a bitmap。

 so I just do the math and say， okay what offset within that range should should I set my bit to true？

So in this case here， just doing the math like this， you get position 50。

 so you just go jump in here and set bit of 50，一即。So you， as you delete and insert things。

 it'll just back and forth between what data structure you want to use， yes。

Having you stored an array？What is the overhead？So question is。

 what's the overhead of storing everything is a bit map。So in this example here。

 what I have two to the 16 different values。 So I need a bit and you need to store 2 to the 16 Bs that I can said to true。

That's expensive。喂。because I I say 20 16， and I now go beyond that， I'll just remaloc how to start。

You could do that sure， but then it's。What？You could do that， but for some values like if。

You're treating everyone the same。And so it may be the case that your data structure is sorry the domain range is wide。

 but within that， it's sparse， right， So now I'm jumping to different cache lines or different chunk of memory just to go see why this thing set true。

 Where this is a bit pack array， which I can then compress it again。This is better。Yes。

s this is from a French Canadian guy， Dana Lemre， and it's used in a lot of systemss use this。

For bitmaps， right？I get a bit。 it's a。It's actually it takes inspiration from。

A paper from the Germans called art， which're not going to cover。

 It's basically adaptive Redx try where they， they can keep track of the the population within some path down in the try or they'll change the size of of the note。

 It sort of the same idea。 Yes， someone tried to repeat this exact thing。 but down as well。

 So you have top。part。The question is because anybody tried to do a hierarchical chunking， yes。

 there is hierarchical bit maps， you get screwed on super scalealar CPUs。

 whichs just too much indirection。I I， I have a slide for that， but not。

 we're not covering that this。 It's like an idea from the mid 90s。 No one does that anymore。

In that case， also two， which you're proposing， why bother doing the extrasher level。

 just make the top level larger。Yes， so especially how I interpret the bit。 It's Bimab index。

 right so。😊，So you would you want to say is is 50 set is this key set set to true。

 So after doing the division to figure out I'm going down this path。

 I know that whatever the position is， what bit position in this is the offset to get the original key is。

Is， is this value plus the offset to reverse the back。

 not the key the actual the starting point of the range。Right， so now within this can so say。

 I forget how many things I have in here。 But if I want to know， is position 50 set to true。啊。Like。

 sorry， at position 50， I know that corresponds to my key here。

 I can then check whether that bit set the true or not。In this， I mean， it's a PowerPoin。

 I don't know。Yeah， but that's it's a bit meex。 I think we covered in in the interclass。

 where basically， again， if I want to know if， is the value at 2ple 5。A a given set to something。

 we' knowing how this actually gets mapped to something。

 I can then look to see whether a bit that corresponds to position 5 is set to true。

And then some higher level part of the system then interprets， what does that mean。His question。

 is this a rudimentary version of a b filter？But so a B filter is a probabilistic data structure where you can get false positives。

 This， you don't get false positives。 You want to know something's in there。 This will tell you。

 yes or no。Could you have more than one data value？あしせ。This question。

 can you have more than one value mapped in the same index？No。

Because we're dividing it by 2 to 16 to figure out what part we go to， and then we take the mod。

 which is basically the remainder of that to figure out what bit it within that。

 so you won't have any to overlap。What if the value comes again。

His question is what if it the seem key again， again， what are you trying to do with it？Again。

 so think of like I'm storing the， the null bitm。I can store it as this。And then I don't， you。

 you know， I'm not gonna set the， you know， the tu， tu， I'd offset set 50 no multiple times。

't make sense。RightIt's not trying to do。 It's not accounting data structure。

 It's just a set membership。O。All right， so。But better blocks parquet and org generate variable length runs of values。

 but better blocks is less susceptible to this， but you could still have that within across the column chunks。

And then Betterbox explicitly avoided doubts on coding because again。

 you have this problem where the the value of one given tuple would depend on the preceding value。

 And again， you can't use S for that。So in the case of better blocks。

 they're always going to use run encoding the vectors。

 even if if the data is the which you end up encod is smaller than the number of lanes you have in the in register。

 And so think of like if I。If I in my Cindy registers， I can put 16 values。

 but I only have 12 values。 They're still going to use all 16 positions in the Cindy register and then the last forge is garbage and they'll clean that up afterwards。

嗯。And in the case of fast lane， we'll you in a second。

 they align things such a way that you're always guaranteed to always be doing useful work in your C registers。

So fastAs is not a complete file format in the same way that better blockslock is。

 it's just a lowlecod scheme that is going to achieve better data parallelism through reordering the two in such a way that you're always guaranteeing or always maximizing the amount of useful work you're doing in your Si registers or CM instructions。

So they're going to have all the same encoding schemes as better blocks， but again。

 with the addition of Delta encoding。And what's really wad about these paper is that， as I said。

 they were rather than designing it for one。You know。

 instance or or configuration of of Cdi for one CPU vendor， they basically say， hey。

 we're gonna make our own virtual IA。And that's gonna have 10 to1024 C registers， again。

 even though that hardware does not exist。 well they allude to like。

 I think M1 has 1024 cache lines and so forth。 right， It's a way to， you know。

Ptending or or seeing for seeinging the foreshadowing the arrival of 1024 Cdi Regs。

 I remember seeing some talk from somebody at Intel saying why this was not happening anytime soon。

 but that was a few years ago。 maybe things have changed。 But But again。

 the idea is they're going to define all the operations on basic constructs on these these virtual IA。

 And then they can show how you can then map that to either scale or C code。

 which apparently still runs really well， or an existing Cdi instruction set。

So the key code thing that they're doing is with this uniform transpose layout。And again。

 the idea is that you're going to reorder。The， the values in a column。

 the two% in a column in such a way that you can do as much work as you can entirely on Cdy。

And the reason why we can get away with this， as I said before。

 is because we had this independence between the physical layer and the logical layer。

 The relational model is based on unored sets。So you， as the application program。

 when you put data into a database， you should not expect that the data will be inserted in the same way that you or data will come back to you and your queries in the same way that you inserted it。

😡，RightMost of the times， you' actually， for some cases， youll you know， depending the system。

 you'll usually get that。 But in case of Postres， soon as you run the auto vacuum。

 that's going to start moving two around。 and there's no guarantee that you end up with the same。

 the same ordering。 If you cared about ordering， you would explicitly have an orderbi order by calls。

Right。Because I'， if you think about it too， like what's the optimal ordering for a。

For a set of column， for one given column versus another。

 that could depend based on what the query actually wants to do。

So instead they're going to make the choices， we'll store this in the best way for us to process the data and then let the query engine above it figure out how to do stitch things back together。

If you wanted to record the order that things were inserted。

 you could add a selection vector that basically keeps track of the position of tus when they arrived。

 but the overhead of that negates and the benefits you're getting。So again。

 all the algorithms that are going to define are going to be based on this virtual ISA。

 and then they just either emulate it on AX 512 or scale instructions。So in the sake of time。

 I'm going to show one example of how this works using a column that will convert into run length encoding。

 and then we'll convert that into dictionary encoding with Dltas。

And we'll see how to do everything in a vectorized way with a reordering。

So see it is our original column with a bunch of extreme characters here。

And so we can first convert this to run length and codingding。

 so we have original dictionary values here， CBCA， or BBA。

 and then for each of those you specify the run lengths as separate integers and the numbers on the bottom just telling you the positions within the vector where they correspond to。

So for this one now， we knew Del onco。So we would have the starting base value here at zero。

 and then you can sort of read this as going across that we're just adding taking the delta。

 whatever the preceding value for us was。And then the index vector then tells you how to。

Take to think of this as materialization after you've done the reverse the de on coding to then tell you what are the actual symbols that you want to get back。

Right。So they'll set things up like this。 but then they go ahead and take this delta encoded vector because the index vector you't actually use。

 You just materialize it。 Sorry， you just materialize it and then do the delta encoding on it。

They then order things in such a way that the。The contagious values aren't going to be one after within the original data set aren't going to be one after another。

 They're going to be in this example here。You know，F elements away。

So now you want to decode this vector like this， because its des oncod。

 we have the base vector is going to be now four elements instead of just one as before。

So as I start off， I take these four elements。 I do the Sdi addition now to apply it to this vector here。

And then I produce the output here， and they're doing some extra steps to make sure that things are written out to the output in memory at these different locations。

 because these correspond to the positions that they exist in the original index vector。Right。

Because if I， if I just have them be， you know， this is right next to this， right next to that。

 then that's going to screw up all my ordering that I need for。

 know the offsets to jump to other columns。So even though things are coming out incrementally。

In atom order， we want to space things out so that it goes back into the right order and they talk about the bit shifting and other operations they do in Cindy to make this work。

Again， so now we slide over the window to look at the next operations， and then in this case here。

 we're taking the output of that was generated from this or these values here。

And then now we can do CD to apply it to this next one to produce the next set of apples。

 and likewise， we do this going down the line like that。Yes， so on this we store the top right block。

His question is， we sort this topic the yellow one。 you sort the whole thing and then the yellow。

 yes。Isn't that much worse than what we still around le coding income？けられコす。So this table is。

Isn't this much more than run encoding because the size is smaller。 Yes。

 but faster the the decoding decoding is faster。 Yes， again， classic computer science。

 compute versus storage。 So I can store less data， but it's gonna make more work for for me to come to。

😊，To decompress it。Again， nobody does this as far as least there's no。

Oome source system that stores data like this。 This is wow。嗯。And。You knowAgain。

 the paper type other ways to handle this for other different encoding schemes， but again。

 like the basic ideas that we we're sort of spraying bits out onto in these vectors so that when we go to decode them。

 they line up nicely into into our C registers and we don't have to do this scatter gather stuff to like move things around to put it in the form that we actually need。

So you can't actually decode this the run length encodecoding with Cindy right。

 because you basically need conditional loops now to say， okay， I look at the run length here at' 7。

 Let me loop through in Cindy seven times。You can code int and do it。

But we'll see this in a week or so that like co Jen brings a whole bunch of other problems that make lives harder。

Could you also compress the de。新对。The David is， can you also compress this？啊。So better blocks would。

 I don't these guys don't。Because， if you do run the conco on this， you're back to this problem。Okay。

All right， I want to finish I talking about bit slicing bit reading real quickly。

All these teams we've talked about sophoir， parade， orc， better blocks， Fast lanes。

They are all about- you scan a column。You're looking at the entire value for each tuple in its entirety every single time。

😡，啊。And that means that you can't， you can't short circuit the， the。the scan or the filter。

 if you recognize early on that this data is never going to match。So I mean。

 you can do this for strings。 if the string is decoed。

 Like if you ever look at like the string compare operation or ellipy。

 it's just a for that looks at every single little net。

 And then if it doesn't match the thing you're looking for， then it breaks out in the loop。

 that's what short circuiting is。But if we're comparing two integers。It's ignoring Cindy Cdy。

 it's a single instruction。 is this equal to this？You're at the lowest level of the hardware。

 youre looking at these primitive data types。You can' you can't do any tricks to say， oh。

 I recognize that the first bit of these two values aren't going to match。

 so why compare the other 31 bits。😡，Because that's the interface that the Harvard provides you。

 the API that Harvard provides you。So but we're data table， we can do every， right？

So what if we could do this， is there a way to be able to recognize that we can just look at a subset of a value。

And do comparisons based on that and only look at the rest of the data for for that value。

 if we think'， it's going to be meaningful so match if， if we need to。

So this basic idea is called bit slicing。This is an old idea from from the 1990s。

 There was a system called Cyibase， I because it's still around Cybase IQ that does this。

 the pelosa or feature based system I mentioned does this Now。

 The basic idea is that we're going to store instead of storing the actual dis integers all the bits contiguously。

It's like an extreme case of the column stores。 So the column store was taking the rows。

 a row and breaking up to column storing all the columns contiguously。

 Now it bits slice that we're gonna to take the bits within a value within a column and store those things contiguously。

 So the first bit for every single value for all tus store that contiguously and then so forth。

 the other bits。So let's see an example here。 So there's all places I lived my life。

 I grew up in Maryland 21042。 know it's Compton， it's Pittsburgh。

 I live in Wisconsin a bunch of places。 So we're gonna to take say 21042。

 convert it to its binary form。 And then now we're gonna to store a separate column of bits for every single one of those single one of these positions。

 Now these are 3 g ingers。 I'm showing 17 bits because it has to fit on PowerPoint or whatever。😊。

So then we always have a null bit mapap， but then we just can scan along。

 look at all the bits and now store them across in separate vectors。

And we do the same thing for all the other ones like this。Again， think of these as again。

 these are contiguous bitmaps。 And again， I can use ro bit mapps now to represent this。In some cases。

 make the the least significant bits， maybe those are not those are those are sparse。

 but the most significant bits are dense。Right。So now want to do look ups like queries。

 Select star from a customer table where zip code is less than。151，5，2，1，7。

I can now walk across each slice and construct a result bitmap to see what tus at different offsets at the bit level are matching my predicate。

And then I can determine if I don't see any more matches as I'm going along， I stop。

So this is the bit representation for 1，5，2，1，7。So say some simplicity。

 maybe I just look at the first three bits because these are all zeros。

So that means that if there's any tuple that has a bit set in these first three vectors。

 that I know it can't match my my tuple because it's going be greater than1，5，2，17。

 So I know I don't need to look at that that position anymore。Right。

That's the basic idea of bit slice。The original algorithm was all scale instructions。

 We'll see bit weeding in a second that can do do this in Cindy。

But this last thing can you can do some other interesting things。 like some some queries。

's like aggregate queries， There's actually really simple operations to compute these things quickly。

So if you want to compute the sum of， of integers。Well。

 I could use the hamm weight or the caming count for just counting the number of bits that are set to one in in a column。

And you know， Intel and Cdy， Intel provides instructions to do this very。

 very quickly using P count right， So there's one instruction to go compute the number of bits that are set within some。

 you know， some vector。So now I just count all the the bits in the first slice and then multiply that by 2 to the 17。

 go to the next slice， count all the bits， multiply by 2 to the 16 and two the go all the way down。

 And then I end up with the aggregation for， for all my。For， you know， for all my columns。

Or for my column here。Again， that's way faster than just doing integer instructions to and add the sum together。

So bit sing extent there was original ideas from 1990s。

 Jake Nash was exploringing this topic in the previous decade。

 and I'm think he's looking at it again now this technique called bitweeding。

The idea here is that it's an alternative coding scheme for column databases that's me predicated on this idea of bitlicing。

 but you're going to do it in such a way that will you can maximize the amount of CD prospects opportunities that you actually have what's wild is that he did this work in 2013 when CMD the8x2 didn't have all the scatter gather features or the8x512 stuff we'll see in two weeks And so the horizontal bit weaving approach'll see it's entirely scalar。

 but then for the vertical one， it's basically same thing as bit slicing。

 but it shows you how you can use CD for this even though back in the day they didn't have all the CD capabilities that we have now。

So J Nash was building this in a project called quickstep， Think of this as like DDV forductDB。

 like was an embedded OLAP engine， but it didn't have a SQL front end。

 It was just like a storage manager that can run OLAPqueries and it stores things column our data。

 So think of like almost rocks Db but for OAP queries。And so he spun off as an Apache project。

 but I think it died in 2018， the code is still there， I think he's still working on it roughly。

 I think， right somebody's working on it。I don't think the bit weedaving stuff is actually in any of this。

 but the academic the open source version did not have it。 the academic version did。

But as far as I know， no other system implements this。Allright。

 so there two ways the two differentcoing scheme that they propose。

 the horizontal one is basically a row storage at the bit level。

 and the vertical one is going to be like bit slicing。

 But you'll do this in such a way for that you can be clever about how to get better parallelism through vectorization。

😊，So I'm kind kind of rush into this， but I just want to give you the flavor of what's going on。

So with horizontal storage， the idea is that here's all our tros we want to store。

 And here's the bit representation of the values。 and the red is their values。

So we're going to break this up into segments， can think of this as like a rogue group within our。

in our data file。And then within a segment， we're gonna to store the data in。

In order going from the top to the bottom。 So this is in the first vector， we'll have t 0。

 second vector the starting point is t1，2，3， and then wrap around and 4。

And then we have the same thing for the other segment， but because we don't have additional entries。

 we don't need to store other vectors。Right， and so in my demonstration here。

 I'm showing the these are 8 bit vectors。 but this would be like a processor word， which I think for。

X 86 is 16 B because it's from the 80s， arm is 32 B。 Basically， this is the。

The sort of large representation that the processor can operate on。 so then now。

 in addition to destroying the values' three bits， there's going to be this padding value here that's going to use as a place to record or given operation。

 was it true or false。So when you store things in this bit waitinging approach。

 you always have to have this extra space， so you're paying a one bit penalty per tubple to store it in this manner。

But that's going to allow us to do Sdy operations or do operations where we just store what happened to you know。

Whether again， the filter or whatever you're trying to do， if it applies to true。

 we'll store it here rather than some other location and memory。So let's see an example here。

 We we have a query。 We want to find in our table， find all the values less than 5。

So say we'll just start with the first vector， so that's going to have T0 and T4。

And then we have now our encoding for the value 5 is this 101。

 so we'll have repeated versions of that or repeated values or instances of those bits。

Corresding to all the lanes up above for the tuoss they' trying to compare against。

And then there's some mass vector where they define formulas that specify how to actually do this arithmetic。

 just using bit operations， bit level operations， So I guess to do addition。

So whatever this formula is here， it says all ones。

Then now I can just do and do the operation produces the selection in vector that determines whether。

The predicate evaluated true if the padding bit is set to 01。So in this case， here。

 t 0 is what is one。 So that's less than 5。 That's set to true。 And then T 4 was What is that，7。

 And so that's set to that is less。 That's greater than 5。 So that's set to 0。Or six， sorry。嗯。

RightYeah。So what's nice about this is that it only requires three instructions to evaluate a single word。

So I can compare two values within a single instruction。

 whereas if I'm just running this in a columnar data， ignoring compression。

 all that other stuff and coding seas。I would basically say， okay， is one less than five。

 true or false， iss five less than6， true or false。

But even without I can Cindy and vectorize that make that run fast。 even without Cindy。

 if I if I store the data in this Biweed pattern， I can just use regular cyst instructions to get the same kind of data parallels we would get otherwise。

So now we got to， though， you know， if you apply to all our vectors。

 we're going end up with a bunch of these different。These selection vectors， right？

But now we've got to put this back together to get back the offsets of our tus in our column that actually were set to true orre satisfied to our predicate。

So to do this， all you need to do is just bit shifting to slide。

 I think everything over so many steps， and then I can then collapse it with an or operation。

To generate the selection vector that corresponds to whether the tu match had a given offset。

And then if I need to go back to the original value， I can use that to figure out。

I' go get the original tuple。The problem is that the vector is that it's just bits， right。

 We need a way to reverse that and say， what position is the bit set to true。To know again。

 what offset in our original vector matched the true。

So the easiest thing to do is just iterate like a simple4 loop。

 if the selection vector is set to true， then add it to an output buffer。But that sucks， right。

 that's a for loop。 That's slow。 again， just to convert bit offset into， to values。

 As far as you know， there isn't a Cindy instruction。 There isn't a。

 CPU instruction to do this for us。So the alternative is to use a trick called came from the vectorctorwise paper from Peter Bos and the paper you guys read next Monday。

 we precompute all the positions。So you pre compute all the selection vectors ahead of time。

And then now you just have a simple array that says， okay， well。

 if I take this binary encoding and convert it to the actual number， in this case is's 150。

 I jump into my array at offset 150， and then now I'm storing my selection vector they tell you what positions are set to true。

And again， in my simple example here， the size selection vector is a bit。

 so with 2 to8 possible values， this thing is easily sitting in L2 cache。

So not's not this big chunk of memory I got to maintain just to convert bit mapps into values。

All right， last one， bitwe vertical。So for this one。

 we're going to store the bits that are all within some offset contiguously。Right。

 so we're gonna to have one vector for all the bits of position 0 and next vector of position position 1。

2 and so forth。 right And then now we get down this other segment here because it only has two values。

 we still have to put we start have to record the entire vector。

 but we just have bunch of zeros in there。 So it's wasted space。

 It's in a waste instructions the way that the fast guys don't like。

 But it makes makes our life easier when we want to do the calculations。😊，Right。

 so this is vector here and so forth。 And again， same thing as it' a process of word。

 But now we don't have this padding bit anymore。Right， to be able to record things。

 we can do everything。 We do everything here in Cindy。

So I'm going to do a look up and say find me all the twobos were value equals 2。Again。

 two is just that bitm like that。I take the first vector。

 I generate a mass vector that that I'm going to use for my comparison because0， these are all zeros。

 I want to see whether these are sets are true across this。 and I get my selected vector like this。

And then now I run pop count and say， is there at least one bit at the1， if yes。

 and then I keep going， if there's no bits at the zero， then I short circuit it， I terminate。

Without having to look at the other vectors。So I only need to look at the subset of the data within a given given value at the bit level。

 in this case here， there's some bits at to one。 So I go down to the next vector。

 now I do comparison my mask that saysFind me all the values that are equal to one at different positions。

 Now my selection vector is all zeros。 So I know there's nothing else that could ever match my predicate and I stop。

RightSo in this stupid example here， I have three bit values。If I had 64 bit values or 30 bit values。

 I could stop early。And I'm comparing multiple， again， within the instructions that I'm doing Cdy。

 I'm looking at way more values than I would otherwise if I was looking at the entire values of integers。

So we do all the early pruning。 we did like a bit slicing Again。

 skip last last vector of all the bits produce 0。 And then the algorithm has a bunch of the paper has a bunch of algorithms to。

 to handle all the other operations you wantan to do。 I kind of I rush this， but its want。😊。

We're not going to see this technique used in other papers， but again。

 it's just a different way to think about how to actually store data and database， which I like。

All right， so I said there's multiple times throughout today's lecture。

This is really showing you that again， the logical and physical data independence is super important。

Right， he was starting to say things like， oh， would do you have pointers to to to data And that that like as a someone who like adheres the facial model。

 that gives me nightmares like pointers to what， why， like， that's a bad idea。

 We want to be able to use to fix length all sets and do anything we want underneath the covers and not worry about。

You know， be able to not worry about explicit points or different things。

And not worry about how programmers actually see those pointers。 right。

 Everything's done underneath the covers。And that way， they can use write SQL。

 or write whatever Python code that they want， operates on our system， and nothing changes。

And then the data parallelism through SIMD is we a really important tool we'll see throughout the entire semester。

 the paper on Monday next week will be the precursor to using SMD for stuff is written in 2006 or7。

 So SIMD wasn't as useful for databases as it is now。

 but it's designing the query processing monitor the database in such a way that you can vectorize a bunch of stuff。

🎼Okay， but we'll see albums how to do joins， filters and other things using Cdy going forward。



![](img/fffc11365ff6938ed8a0d8509c0bf581_5.png)

![](img/fffc11365ff6938ed8a0d8509c0bf581_6.png)

Sts and six packs on the table and I'm able to see saying I was。No short put the cross。

 you know what got them I take off the cat but first' tap on the bottom。

 don about three in the freeze it so about the killer。

 cat full with the bottle baby whoop don' feeling it coa nice to says the pain nice way you don't get down with the guy in。

Take back the pack of thugs， itvo you some same now to trick to the thuds。

 Billy Des to trees to tell him weak， gosh， be a man to get a can of thing time。

