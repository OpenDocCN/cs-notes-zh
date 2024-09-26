# 加州大学伯克利分校 CS 186 数据库导论 Introduction to Database System (Fall 2020) - P10：Lecture 10 Iterators & Joins I - ___main___ - BV1cL411t7Fz

 Okay， look， it's awesome to see all of you。

![](img/61dd289783a605e30da0eca1ed23e63b_1.png)

 Okay， great。 Give me one second to make sure my chat window is visible。 Okay。 Awesome。

 So we are live talking about join algorithms and it traders。

 And I think Alvin and I decided that based on feedback from the core staff that we will。

 try to do announcements a little more into the class or at the end of the start the class。

 where some of you may end up joining late because you may have classes right before。

 So we try to do announcements somewhere in the middle of the class。

 Usually when I hand over the range from， I hand over the range to Alvin or and so the， range to me。

 So we try to do it then and if we are not handing over the reins， we'll figure it out。

 We'll try to still make sure the announcement is covered before the end of class。

 So we are talking about iterators。 And so we were talking about how the relation operators are all subclasses of this iterator。

 class。 And before we get to that， let's review what we covered the last time， which is that query。

 plan a sequel query looks sequel query would get compiled down to a query plan， which looks。

 like a tree like this。 And this tree encodes the flow of tuples。

 So basically the tuples flow from the bottom。 These are the relations and they flow upward。

 And so these edges in the tree encode the flow of tuples。

 The vertices in this tree include the operators and the source vertices in the bottom。

 And code the table access operators。 This could be scans or index lookups and so on。

 So that's how you would read a tree of the sort。 This is what you call a query plan。

 In some context， it's also called the data flow graph again for obvious reasons because。

 you have you are encoding the flow of tuples to through this graph， right？

 So it's a graph that encodes the flow of tuples and the operations that are done to the， tuples。

 And this data flow graph is not specific to database systems and is also found in other。

 big data deep learning and machine learning systems。

 And so this query executor component in a database system is responsible for instantiating。

 the operators responsible for creating instances of these operators。

 And the query optimizer is what is what selects which operators need to be run in the first， place。

 So this optimizer is responsible for selecting the query plan。

 The query executor will create instances of the operators which then perform the execution。

 of the query， okay？ So which execute the query plan。

 So the query executor runs these operators by creating instances thereof。 And so for every operator。

 every internal node， every leaf， you have a operator that is instantiated， by the query executor。

 So you have， and each of these are called iterators。 For reasons that will become clear shortly。

 So you have like， for example， an index nested loop join iterator or a projected trader or。

 a selected trader。 These are on the， some of these are on the fly traders like select and project。

 We discussed on the fly last time we'll quickly review that as well。

 And at the bottom we are accessing these relations using index scan iterator。

 So these are basically using an index to look up the tuples of this relation。

 And we'll see again examples of why that might be useful later。

 So each operator instance basically implements these， this iterator interface。

 It's a standard set of methods that each operator is expected to support so that there is a。

 uniform composability across operator。 So one operator can call on other operators and these operators can be composed together。

 to form this very plan。 So that's why this iterator interface is so important， so powerful。

 And each operator instance is responsible for basically executing the operator logic and。

 forwarding tuples to the next operator。 And this operate stuff flows from the bottom to the top。

 So the tuples will sort of go from the bottom to the top and the results are produced at。

 the root node。 Any questions so far？ All right。 Okay， so this， what's this iterator interface？

 So what is this， what is this common set of methods that all of these operators are expected。

 to support？ So an iterator interface is basically， it's a class that allows。

 that supports a certain， fixed set of methods。 It's an abstract class。

 it's supposed to fix set of methods。 One is the setup method which basically for every operator sets up the set of inputs。

 to that operator。 So these are the children of that operator。 Then there is。

 so this is usually standard and we are going to avoid talking about that。

 This is not very sort of unique to any particular operator instance。

 It's just sort of standard across the entire set of operator space。

 So we're not going to be focusing on this as much， we're going to be focusing on the。

 remaining three。 The remaining three are more interesting and they are different for different operators。

 And so the init basically sets up shop， right？ So basically it is。

 does some processing before you start the processing of the tuples for， that operator。

 So this is the invoke before you calling next。 Next is the one that is responsible for the individual processing of tuples。

 So this init operation is invoked before calling next。 It sets up some state。

 usually it initializes some variables， sets up some background before。

 you can start processing that operator。 The next operator is one that has a return type tuple。

 So it's basically a responsible for generating yet another tuple。

 And so this operator is the one that is sort of used by a parent operator to generate another。

 tuple from a child operator， for example。 And this is responsible for returning another tuple。

 And so by repeatedly calling next， you can iterate through the tuples that are produced。

 by a given operator。 Hence the term， iterator。 Okay， so that's where the term iterator comes from。

 The closed function is standard。 Again， this is usually invoked when this operator has no more tuples to produce。

 So you basically， in some sense， shut shop。 So you basically sort of clean up state。

 close sort of file handles and things like that。 So this iterator interface is a pull based computation model as opposed to a push based。

 computation model。 The root node starts the root node requests more tuples from the children node which in。

 turn requests tuples from each children and so on and so forth until tuples are being pulled。

 up from the leads， which are the relations all the way to the root。

 So the root in certain instances could be， for example， the console， the console could。

 call in it on the root operator of the query plan。

 The root operator and then subsequently ask for more tuples。

 So the next would be the function that's called to request more tuples。 If this tuple is not ready。

 the next request propagates down the query plan to subsequent， nodes in this query plan。

 each of which is an operator。 And then they are in turn， if they have not been instantiated。

 you would set them up by， calling in it。 And then if a tuple is ready。

 then it's immediately provided。 Otherwise they will again call their children operators and so on。

 So that's sort of how this pull based computation model works。

 It starts from the root and then bubbles down to the leads。

 And this init on next can be either supported in a streaming or on the fly fashion or a。

 blocking or batch fashion。 And streaming basically involves a relatively small amount of work for call while blocking。

 is usually reserved for operators that have to consume most of its children's outputs。

 before it can produce any outputs of its own。 So it does not produce output until it consumes its entire input。

 For example， a sorting operation is a blocking operation because you need to look at all。

 of the tuples before you can produce the results in a sorted fashion。

 So the great thing about this iterative interface and the fact that all relational operators。

 are implemented as subclasses of this class is that they can compose。

 So any iterator can be input to any other， since they all implement the same interface。

 The other interesting thing about this iterative interface is that all of the logic for a given。

 operators encapsulated within it。 So iterators may maintain substantial private internal state that is visible only to that。

 operator is not visible to other operators。 So they could， for example， maintain hash tables。

 running count， pointers， cursors， as well， as sorted files。

 So all of this are things that individual operators can maintain as state。 Okay。

 so let's work through a simple on-the-fly operator， which is a selection operator。 Again。

 this is sigma in a relational operator context in a relational algebra context。

 And this is an streaming or on-the-fly operator， which means it does a small amount of work。

 for every tuple that's produced。 Okay， so what does InIt do？ Well。

 so InIt for the select operator is called with a predicate as argument， which is the。

 argument that is the condition that is applied as a subscript of the select operator。

 And so it does three things。 First is it calls InIt on its child。

 So since a selection operator cannot exist by itself， it has to have a child。

 Usually this could vary actually。 So it could be a relation。

 It could be the result of some of the operators。 So this select operator calls InIt on its child。

 It sets up some sort of internal variable called pred using this input argument predicate。

 So this is a local variable storing state。 And then it has a local cursor called current。

 which is set to null。 Okay， and we'll see why current is valuable when we look at next。 Okay。

 so the next function has a while sort of statement。 And the next function says。

 as long as current is in the end of file and as long as the predicate。

 evaluates to false on the current tuple， fetch me yet another tuple from the child。 Okay。

 so basically this while loop instructs the child of this select operator to produce。

 more and more tuples until you can find one that either matches a predicate or you reach。

 the end of file。 Okay， so e of f is the end of file。

 So either you find one that matches the predicate or you will see end of file。

 Either way you return that， right？ As soon as you found one that matches sort of the predicate。

 you return that。 Otherwise you basically gone through the end and you reached the end of file。

 Basically what this means is there's nothing more to give from the child。

 And so you return end of file to the parent。 Okay。

 so that's how you produce yet another tuple that matches the condition theta that。

 or pred in this case that is specified as part of this operator。 And close does nothing surprising。

 It basically tells the child of this operator to close。 Okay。

 so let's go to a slightly more involved operator。 This is a heapscan operator。

 So this is usually involved as a leaf of a query plan。 Okay。

 because it's basically reading the heap file。 So the init for this heapscan takes as an argument a relation and then basically sets。

 up for a heapscan on that relation。 So it will open the heap file for the relation。

 And then it will try to look up the first page within that heap file that pertains to。

 this relation。 And within that page it identifies a first slot referencing the first tuple within that。

 page that it may want to read subsequently。 Okay， so that's what the init does。

 So once you've set up this state basically what you've done with the init is you've said， hey。

 this is my current page。 So this is the page that I'm reading from。 And within this page。

 this is a slot that I'm going to be reading from。 Then I get requested for a tuple from the next operator which is called subsequently。

 Okay， so what is the next do？ Well， if the current page is null， then you return an end of file。

 Basically this is reserved for the point where you've read all of the tuples is nothing。

 left to read。 Okay。 All right， so if this current page is not null。

 then what you end up doing is you initialize， this variable called current which points to the current page and the current slot within。

 that page。 Okay， so this is basically a record ID pointer。

 And this record ID is what is going to be our return value。 That said。

 we're not quite done because we don't want to simply return the record ID。

 We also need to figure out how to advance to the next record ID in preparation for the。

 next next call。 Right。 So it's not sufficient to just return this current page and slot ID and then move on。

 We need to figure out how to advance the pointer to the next record that we will get requested。

 for subsequently。 And so this logic is basically telling you to do that。

 The current slot is advanced。 So you call advance which is a function which goes from one slot to the next applicable slot。

 on that page。 If the current slot is null。 So this function returns null which means that there's no more slots to be read in that。

 particular page in which case you advance the page。 Okay。

 so you move to the next relevant page for this relation on the heap file。

 And if this current page is not null which means you've not gone past all pages， if it。

 is equal to null which means that there's no more to post left to read， if it is not。

 null that means that you're still dealing with a page whose tuples you've not yet read。

 And so current slot is initialized to the first slot within that page。 Okay。

 so this all of this processing is to just set up what you need for the next call， of next。 Okay。

 And so once you've done with that you return the current record ID which is a current page。

 in current slot pair to the parent。 Okay。 Any questions on this？ Okay， look。 Right。 So。

 the close again is not very surprising。 It's basically closing the file handle。 Right， so it's not。

 Okay， Sean， go for it。 Yeah， so I was wondering， like。

 we check if the current page is equal to null again in， the nested if statement。

 So let's say that it is null。 Shouldn't we also return end of file still？ Sorry， bad。 Bad。

 What do you want to add a turn end of file here？ So we advance the current page if the current slot is null。

 right？ Correct。 And if the current page now is null after we advance it。

 should we return end of file， there because we're still returning current in that case？ No， so。

 so think of it in the following way， right？ So current is referencing the current tuple that is going to be produced or the record。

 ID that for the for the current call of next。 And then the current slot and the current page is basically what is a next tuple that。

 is going to be produced。 And so if the current page ends up being end of file。

 that means you've gone past the， set of applicable records。

 you don't have any more records to produce， but you will detect， that in the next call of next。

 You don't need to worry about it right now。 You already have a record to produce right now。

 so you might as well produce that。 Okay， guys， thank you。 Okay， good。 Yeah。 Yeah。

 so is it reason why we pass around the record ID instead of the record tuple itself？

 So you could do that too。 This is just a pointer to the， this is equivalent， right？ I mean。

 you could reduce the record， the tuple itself too， and that would be equivalent。

 I guess this would depend on the implementation。 So there's no particular reason that we are doing a record ID。

 You could pull out the tuple and have that be produced as well。 That would be fine。 Thank you。

 So it also depends on what language you're with。 So if you see your C++。

 you might end up needing to copy stuff， but then if you just， record， you just return the record ID。

 then you're just returning a number。 Any other questions？ Okay。 All right。

 so let's talk about sorting。 Okay， and the variant that we're going to be talking about is a two pass sort。

 So this is just two passes。 And if I recall it was basically four times the ure。 Okay。

 so let's work through the example and then we can go into the complexity if it's needed。 Okay。

 So the init function for a sort basically takes as argument the keys with which you want to。

 sort the input by。 Okay， so this is what you're going to be sorting the child。

 the result of the child by。 So this is the one argument that this init function takes in。

 And the first thing that you do is you do all of pass zero。 Okay， so pass zero。

 which is responsible for producing the sorted runs on disk is all completed。

 within the init step itself。 And this is a blocking call because it's not producing any output and it's consuming a lot。

 of the input。 So basically you end up doing child dot init as always you initialize the child and then。

 you repeatedly call child dot next and then generate the sorted runs on disk。 Okay。

 Generated the sorted runs on disk until the child provides an end of file。

 At that point you know that you produce these sorted runs and you can proceed to the next， pass。

 Okay， so the next thing is you set up for pass one， right？ And to to for pass one。

 since we are assuming that this is a two pass algorithm， we are。

 going to assume that it has enough buffers to do the merge correctly， which means that。

 there is enough space to hold one page from every single one of the sorted runs on disk。 Okay。

 so you're opening up each sorted run file and loading one page per run into the， input buffer。

 So you're basically prepping for pass one by bringing in one page from every single sorted。

 run on disk into an input buffer。 And that's your init。 In it is already doing a lot of work， right？

 So the init is already doing a lot of work and it is basically setting up the stage to。

 do the merge pass of the mod of the sort。 Okay， so the sorting in terms of sorting into runs is already complete。

 We have already set up state for the merge。 Okay。 So the next function is basically doing the pass one merge and this is assuming that there。

 is enough buffers to merge。 So you already have one representative page from every single sorted run。

 So the output tuple that's produced is basically the minimum tuple across all the buffers。

 So it looks at all of the buffers which contain one page from every sorted run。

 It figures out what is a minimum tuple across all of them and then it produces that as the， output。

 If this minimum tuple was the last one in its buffer， then you basically replenish that， buffer。

 right？ So you fetch the next page from that run into the buffer。 And once you produce a minimum。

 you identify the minimum tuple and you've replenished the， pages corresponding to every single run。

 So you now have a representative again from every single run。

 You can return the output and then wait for the next call to next so that you can then。

 read another minimum tuple again。 Carson， you have a question？

 So since we're taking the minimum across a bunch of different values， what's a good， way to do it？

 You just build a min heap out of all those values？

 So you could do something more sophisticated like that。 You could store a min heap。

 Perhaps more straightforward would be to cycle through all of them and figure out what is。

 a minimum， right？ Yet another option is to， so yeah。

 so basically those two would be the sort of options。

 One is intelligent data structure that maintains a minimum as new tuples are added or new， our。

 pages are removed。 So basically as you exhaust all the tuples in a page。

 you bring in a new page and so that， would correspond to a new insert into this data structure。

 The other alternative would be to just go through。

 Usually you opt for something that is lightweight and so a priority queue may not be necessary。

 for this。 Carson， does that make sense？ Yeah， that makes sense。 Any other questions？ Okay。

 So the close function for the sort operators， again， not very surprising。 Right？

 You basically deallocate the runs files and then you close the child。

 So basically dismantle whatever state you have left。

 Let's move on to group by and we're going to take a special case of group by specifically。

 one on sorted input。 So we are assuming that the input to the group by is sorted。 Okay。

 so this could be for example after a explicit sorting operation and the group by。

 is consuming the results of the sorting operation。

 So turns out we can also do group sorting group by without explicitly sorting。

 So it doesn't necessarily need the input to be sorted。 But for this example。

 we will assume that the input is explicitly sorted。

 So group by is irrespective of the aggregate that we are computing a result for applies。

 a similar approach for merging the tuples in a group across a whole host of aggregation， functions。

 And so the typical recipe looks like this。 You initialize some state per group corresponding to each of the aggregation functions that you。

 need to produce a result for。 You operate on one tuple at a time。

 you merge it with this existing state and then you return。

 the result to pull when you're done with a group。 So let's take a concrete example。

 So if your aggregation type is count， then the state that you maintaining is this variable。

 called count internally that's initialized to zero at the start of a group。

 And as you see more tuples， you increment the count。

 So that's what you do when you merge in a new value。 Then at the end of it。

 when you've done seeing all of the tuples for a group， you return the， count。 Okay。

 so that's what you do when you finalize a group。 Some is similar。 Okay。

 so you have a variable called some。 You initialize it as zero。 If you see a new value， X。

 you add it to your current sum， you're running total。 And then once you're done。

 you finalize some as the output of this allocation。 So basically for each of these functions。

 you operate one value at a time and you can， increment it。

 You can merge it with the existing values。 Now let's talk about average and minimum。

 So what do we think the state would be for average？ What kind of state would we want to maintain？

 And how would we merge in the results for new tuples with that existing state？

 The sum and the count。 The sum and the count， right？

 So basically you would maintain both the sum and the count。

 You would initialize both of those to zero。 As you get new values。

 you would increment the count and then you would add the new value。

 to the sum and then when you are supposed to produce a result， you take the sum and divide。

 it by the count。 What about min？ So min is not very surprising either。

 So you would basically maintain the minimum value that you've seen so far。 When initializing。

 you'll initialize it as a very， very large value。 Okay， so you might initialize it as plus infinity。

 for example。 And then as you get new values， you'll check if the current minimum is smaller than the。

 value that you're examining or not。 If the new value is actually smaller。

 you'll replace the current minimum with that new value。

 And then eventually you'll produce the minimum that you've been tracking so far。 Okay。

 so that's how this looks like。 So the average is basically keep a pair of comment。

 the sum and the count。 And for the minimum， you will maintain your current minimum that you've seen so far。

 You initialize it to a very large value。 And if the current minimum is greater than the value that you're seeing。

 you replace the， value with it。 Okay。 Any questions on this？ So this is what we feel like， yes。

 Yeah， so since average uses like count and sum， does that mean that like， for example， if。

 do we actually then need to like do all this work of like creating and setting up a state。

 if it's just computing average or is it necessary to do all this like set up if it's just a simple。

 computation of two like two other ones that we already know？ Yeah， so if you just needed average。

 so think， see if you can figure out a better way to do， it， right？

 I don't know if a better way to do it that does not involve maintaining both sum and count。 Oh。

 okay。 Yeah。 I was wondering like I was saying that average itself need like do we need to maintain average。

 itself if it's just only relying on count and sum like a business？ Do we need to maintain？ Okay。

 I see。 Yeah。 So if so you could certainly if you knew that you were returning count sum and average。

 for example， you could maintain the sum and count and be done， right？

 You could use that for all three if that's what you meant。 Okay。 Yeah， that was my question。 Yeah。

 Any other questions？ Okay。 All right， so using this primitive。

 let's try to figure out how to do group by unsorted， input。

 So the init function for this group by operator is going to take a bunch of grouping keys。

 which is your group by and a bunch of aggregations that you want to produce。 Okay。

 So the next function is responsible for the heavy lifting。

 So the next function basically keeps assembling new values。

 So the next function is going to be the next function。

 So the next function is going to be the next function。

 So the next function basically keeps assembling new values。

 For a given group merges those values in when it's confident that it's not going to see。

 any more tuples for a given group， it produces a result。 Okay。 So that's an intuition。

 So you are your input is sorted。 Remember， and therefore given that your input is sorted。

 you are basically consuming the results， in sequence corresponding to a group。

 Once you moved on to the next group， you can produce a result for that group and then and。

 then start a new group。 Okay。 So， so you have this do while loop。 Again。

 let's not worry about result for now。 So result is set to null and we'll see why again result makes sense in a little bit。

 The current group which was originally set to null is basically pointing to the current。

 group that you're processing。 So this tuple is a variable that refers to the next tuple from the child。

 Okay。 So you ask a child for another tuple， you get it and that's your new tuple。

 And this new tuple， you check if the group that the tuple belongs to is the current group， or not。

 Okay。 Does it belong to the current group or not？ If it does not belong to the current group。

 that means you need to start a new group。 Okay。 When we started the process per group was null。

 So any tuple that you end up reading is not going to have a null group。

 So you will end up starting a group in that case as well。

 So if the current group is not equal to null， that means that you will be processing some， group。

 then you will go ahead and produce the results for that group because we know that。

 we moved on to the next group。 Okay。 So the result is basically going to be the current group。

 which is the current group and， finalizing all of the aggregates that need to be produced。

 Then we will re-update the current group， the current group that you're operating on to。

 be the group of the tuple and we will call in it on all of the aggregations that we need。

 to produce for each group。 Okay。 So that's what happens if you basically determine that you don't have any more tuples to produce。

 for a given group。 You will then also call merge on all of the aggregations。

 So basically merge the values corresponding to the current tuple for all of the aggregations。

 So this is called irrespective of whether you are producing a new group or you're continuing。

 on an old group。 And then as soon as this result variable is not null。

 so remember that it was initialized， to null， if this result variable becomes not null。

 that means you are ready to produce， the results for a group。 And so as soon as that happens。

 you exit this two-while loop and you return that as a result。 Okay。

 so as soon as you have a new tuple to contribute， which is basically a group and。

 all of its aggregates， you move to producing the result and you return that from the next， call。

 So again， child is not really surprising。 You're basically calling close on the child。

 So what's neat about this function， about this iterator is that it's really only maintaining。

 one tuple of partial results in memory at any given time。 So that's really neat， right？

 So it's basically maintaining some state that is constant irrespective of the number of。

 tuples that is being processed from a group by standpoint。 So that's pretty neat， right？

 So it's very lightweight。 Okay， so with these operators that we discussed， the heap scan。

 the selection， the sorting and， the group by， we can actually now start to sort of get a sense for water and overall。

 query plan might look like。 So a query plan， as we will discuss right now， is single threaded。 Okay。

 we'll see if we might want to make it multi-threaded later。 For now。

 we'll consider a query plan to be single threaded。

 And so if you can imagine a query plan is basically starting from a call to the root， a next call。

 to the root， so after the initialization up and down the root， up and down the query plan。

 you call next on the root， each next would then result in calls of next to other operators。

 down the query plan， which will then produce results which get bubbled up back to the root。

 So as an exercise， I encourage you to try to， for this particular query plan， it's not。

 very complicated。 It's a single table query plan。 See how， for example。

 if you call init on the group by， how does this init recurse down， the chain and return a value？

 And then sort of work through the mechanics of calling next on root and see how next work。

 works down the query plan and then return the two。 Okay。 So as we saw。

 some of these operators are blocking operators。 So for example。

 the sorting operator even during init does a blocking step of producing， the sorted runs。

 While the group by operator， since it's relying on the sorts output to be sorted is essentially。

 acting like a streaming operator as is the select operator。

 So both of these are essentially streaming。 So I encourage you to try this out。

 This is a good exercise to really get into sort of understanding the semantics of operators。

 and the iterator interface and how these calls sort of bubble down sort of from the root of。

 the query plan all the way to the leaf。 Okay。 So the。

 the other interesting thing here is that we're not necessarily storing each operators。

 outputs on disk， right？ Tupils are really flowing through the query plan。

 They're streaming through this call stack。 And certainly some operators may require to use this。

 So for example， the sorting operator did write out sorted runs to disk。

 But this is not exposed outside the operator。 At least from the iterator interface perspective。

 these tuples are being passed。 They're being streamed across these operators。

 And so the iterator framework itself is very lightweight even if individual operators are。

 more heavy weight。 Okay。 Any questions on this？ Okay。 So let's move on to binary iterators。

 Specifically， we'll talk about joints。 So this was a single table sort of query plan。

 We'll talk about joints。 So for talking about joints， we need to set up some notation。

 So R with square brackets is going to refer to the number of pages to store relation R。

 PR is going to refer to the number of records per page of R。

 R with these vertical bars is going to refer to the cardinality of R which is the number。

 of records of R。 So this is simply PR times square brackets。 And for our example。

 we're going to be using these two relations， our reserves and sealers， relations。

 And so the results relations are spread across 1000 pages with 100 tuples per page resulting。

 in 100，000 tuples in the relation。 And likewise for the sealer。 So you have 500 pages。

 80 tuples per page， so a total of 40，000 tuples overall。 That's a cardinality of that relation。

 I did， yeah。 Do you think it would be a good time to take up right now with your announcements？

 Good idea。 Okay。

![](img/61dd289783a605e30da0eca1ed23e63b_3.png)

 So I， Alwyn， I did not find your announcement slide。

 So I'm going to just do the announcements from my notes in Slack。 Okay。

 So there are a few announcements。 The first is， I'll go in a random order。

 the most important one is that the mid-ton is coming， up。

 So I encourage you to try your setup out and come to us if you have issues。 Right。

 So Alwyn and my officers are relatively free。 If you have any issues。

 you're welcome to drop by for that。 And if there are specific technical concerns。

 feel free to raise a post on Piazza。 There's something that is concerned。 I would。

 and also related to the mid-term， this review session on Friday that I encourage， you to attend。

 Also valuable to attend this week is the discussion。

 This is going to be really important for project three。 Project three is pretty demanding。

 So I encourage you to attend the discussion this week。

 And if you aren't able to attend the discussion， I encourage you to try to make it up in some。

 way by watching the video， for example。 So you suggested that the vitamins release and deadline schedule wasn't really working。

 for you partly because you wanted to attend the discussions， the sections before you attempted。

 the vitamin。 And therefore we basically changed the schedule such that it's released on Saturday and due。

 on Monday the following week。 So this gives you a total of nine days and this allows you to attempt the vitamin after。

 having gone to the section。 So those are the announcements。 Any questions on the announcements？

 So as I did here， I was saying feel free to drop by office hours if you want us to like。



![](img/61dd289783a605e30da0eca1ed23e63b_5.png)

 let's say check on your video setup。 So I think Ethan already posted an example of that on Piazza about what we expect you。

 to be doing for the during the exam。 So if you have questions about that or you just want to check them。

 just show in office， hours。 So I think we're asking you guys to submit something if you want to get the bonus point。

 So basically just to check the setup。 But as the Piazza post was saying。

 we're not actually going to individually click on， each of the videos that you guys submitted。

 right？ Those because of privacy and also because we just don't have to staff to check all 600。

 of them。 So if you have concerns about whether yours in particular is compliant。

 just come to office， hours and show us。 That said。

 the intent behind recording is that during the exam is that we can check if。

 we want to and it also tries to minimize privacy concerns。

 So it's always a feel safe to encourage that basically good behavior。

 And we do want you wanted to be a fair exam and wanted to be as much like the real exam。

 as it would be。 So it would simulate a real exam experience。 Cool。 Any other questions， thoughts。

 concerns？ Okay， I'm going to start with the first variant of our joint algorithm。

 This is called the simple nested loops algorithm and we're going to be sort of describing that。

 for a general theta join。 And two notes before I get started。

 So I'm not going to be presenting iterative implementations for these algorithms。

 And also and this is just for simplicity just to be because these and algorithms are involved。

 as it is and presenting code is not going to help understanding any more than the intuition。

 that I'll provide。 But I encourage you to go try to sort of work through what the iterative implementations would。

 look like， right？ In it next and close calls for each of these algorithms。

 Also I in our convention would be that we are going to ignore the cost of writing out， the output。

 Okay。 The reason for this is that it's going to be a constant across the approaches。

 So it's not something that we're going to use to compare between various approaches。

 The result of a join is going to have the same size independent of which algorithm you， use。

 In many cases the output of a join will stream through it via next。 Right？

 So it may not get written out to this。 It may get consumed by the next operator。

 So for both of these reasons we are not going to sort of count the cost of writing out。

 We're going to sort of focus on the cost of reading in and the processing as opposed。

 to the cost of writing out。 Okay。 So the simple Nesal loop join is very straightforward。

 Basically saying let's do two nested loops。 One for R， one for S。

 For every record R small R in R and for every record small S and S。

 if the match the condition if the theta predicate is true then you add R comma S you basically。

 do the join and produce a result to the result buffer。 Okay。 So that's your simple algorithm。 Okay。

 So how does that look like？ Well， for every tuple so you can represent this in a X Y claim。

 So the tuples of R are along the Y axis the tuples of S are along the X axis。

 So for the one tuple R of small R of R you are cycling through all the tuples of S。 Okay。

 Then you do this for the second tuple of R then for the third tuple of R for the fourth。

 tuple of R and so on。 Okay。 So you do this for every single tuple of R capital R every single tuple small R of。

 capital R you cycle through all of the tuples of S。 Okay。

 And so given these sizes what would the cost of this algorithm look like any thoughts？

 Like N squared maybe？ N squared using these numbers how would we express it？ R times S。

 So that's part of it but it's not all of it。 Okay。

 So R times S is part of it but it's not quite all of it。 And let me work through why。

 So the cost basically is a cost of scanning through all of R once and for every tuple R。

 you are going to scan through all of S。 Okay。 So cost of scanning R once is basically the number of pages of R and you're scanning through。

 S once for each R tuple and so you basically take the cardinality of R multiply that by。

 the number of pages of S。 Okay。 And therefore the total cost is 50 million 1000。 Okay。

 So that's a total cost。 That's again you're scanning through all of R once plus for every one of every tuple of。

 R you're scanning through all of S。 Okay。 So it's cardinality of R times the number of pages of S。

 Okay。 So that's the first variant。 Right。 So a natural alternative would be to flip the order of these two。

 Right。 You go through all of S and for every tuple of S you go through all of the tuples of R。 Okay。

 So you change the order of these follows。 So what would the cost look like in this case？

 Well you scan S once and then scan R once per S tuple。

 So it's the number of pages of S plus the cardinality of S times the number of pages， of R。

 So this is around 40 million and this is a substantial difference from the previous。

 algorithm which was 50 million。 Okay。 All right。 So I started and also noticing some messages on chat about why are we going through all。

 of the tuples of S rather than the pages。 And that's really the intuition behind the next algorithm。

 Okay。 Okay。 So this is a pretty simple algorithm but it's doing a lot of unnecessary IO。

 So the next algorithm is going to be a little bit more careful in thinking about the fact。

 that the basic unit of retrieval from disk is a page。

 But before I get to that I did want to mention that there is a substantial difference between。

 doing R as the outer loop or SSC outer loop。 So the join orders do matter and we'll see another we delve into sort of how to figure。

 out the best order of joins later on。 Okay。 So how would we improve this already？

 There are some messages on chat that is the idea。 Right。

 The previous algorithm was pretty inefficient with respect to IO and so why not operate。

 at the cardinality of pages。 So basically the idea is that you have now have four。

 First for loop is cycling through all pages of R。 The second is around all pages of S。

 and then for every tuple in R in the page of R and every tuple in the page of S you then。

 do the join and produce output。 Okay。 So basically you're now operating at the level。

 of pages rather than the level of individual tuples。 So you would bring in this page and。

 this page and then you would do the join across all pairs of tuples in these two pages。

 So overall the execution looks something like this rather than doing the sort of scan through。

 all of S at the level of tuples you're scanning through all of S at the level of pages。 And。

 so you now have four scans through all of S in this simple example because there were。

 four pages of R。 So what does that cost look like in this case？ Right。 So the cost here。

 is basically the cost of scanning R once and scanning S per page of R。 Right。 So scanning， R once。

 So that is square bracket R plus square bracket R times square bracket S。 And。

 this is 500 K as opposed to 40 million from the previous simple nested loop algorithm。

 So this is the idea behind what we call the page nested loop algorithm because the granularity。

 that you're bringing stuff in is the granularity of pages。 Okay。 So a natural question is can。

 we improve this？ Right。 Can this be further improved？ Any thoughts on how？ Use a bigger。

 page or a buffer。 Yin has the right idea。 Right。 So the basic notion here is that you。

 want to minimize the number of times you are scanning through S。 Right。 Every time you're。

 scanning through S， you're adding another cost of S， S pages， square bracket pages to。

 the overall cost。 So can we minimize the number of times we are scanning through S。 And the。

 answer is yes。 Right。 So instead of doing the scan through S at the granularity of one， page。

 you could do it for multiple pages at a time。 Right。 So if you have B blocks in。

 your if you have B slots in your buffer， you might as well fill them up with as many pages。

 as you can of R and then do the scan through all the pages of S。 And that precisely is。

 the idea for the next algorithm。 And so traditionally， this algorithm is called block nested loop。

 joint。 But because we have used block in other context before， we are going to call it a， chunk。

 Okay。 So this is going to be called a chunk nested loop joint。 And this chunk nested。

 loop joint basically brings in a certain number of pages of R at a time。 This should be R。 Okay。

 And then cycling through all of the pages of S。 So for each chunk of B minus two pages。

 of R and for each page of S， you are basically finding all of the matching two posts between。

 this one page of S and the R chunk。 Hello。 Okay。 I think someone unmuted themselves by mistake。

 Okay。 So you basically do this join between the B minus two pages of R and this one page。

 of S and you produce all of the output， you added to the result buffer in this case。 Okay。

 So that is this idea behind chunk nested loop joint。 And so in this simple example， maybe。

 you can bring in two blocks of R and then cycle through all of the blocks of S。 So you're bringing。

 in one block of S at a time。 And you would produce all of the join join the two books。 And so again。

 in a pictorial X， Y plane representation， you basically in this case， you just do two。

 sweeps through all of the pages of S because you're bringing in pages of R at the granularity。

 of these chunks。 Y B minus two pages。 Well， our convention is that we have we are using。

 B blocks overall。 We have one block for S of B B frames overall in your buffer or B blocks。

 overall in your buffer。 You have one page for S， one page for the output。 And then the。

 remaining B minus two is what you're using for our。 Okay。 So what's the cost for this？

 So the cost for this is basically the cost of scanning R once plus you want to scan S。

 as many times as there are chunks。 And so how do we figure out how many chunks that are？ Well。

 it's basically R divided by B minus two。 And so B minus two is basically the number。

 of pages of R you can bring in at once， assuming you have a page for S dedicated and you have。

 an output buffer。 Right。 So those are the where the two comes from。 And here you be。

 a using the ceiling because you want to round up。 So the overall cost is the number of pages。

 of R plus the ceiling of our square brackets of R divided by B minus two。 This is the number。

 of chunks that you have if you're bringing in B minus two at a time multiplied by the。

 number of pages of S。 And in this particular case， if we assume for example， B is 102， this。

 overall results in 6000 IOs。 Okay。 So this is 100 X better than the page in a loop。 I'll。

 call it a little bit。 Okay。 So overall， this is a really frequently used join algorithm。

 especially for non equality predicate。 So if you have a theta join， which is an arbitrary。

 condition， not equality， a chunk nested loop join is usually a really good default as a， fallback。

 Okay。 So the other algorithms of block nest， the page nested loop or the simple。

 nest loop are not by the alternatives。 Okay。 So another alternative join algorithm that。

 I wanted to discuss is the index nest loop algorithm。 Okay。 So let's say we have an。

 equal join on with a condition， ri。 So the ith attribute of R is equal to the jth attribute， of S。

 So the index nest loop join procedures follows。 So just like you would in the sort。

 of basic simple nest loops join， you cycle through all the tuples of R and for every， tuple of R。

 you basically cycle through all the tuples of S for every tuple of S where。

 there is where the condition matches， ri is equal to SJ， you add r comma S to the result。

 buffer or you produce a joined tuple and added to the result buffer。 Okay。 So how do we find。

 the tuples where ri is equal to SJ and this is where the index comes in， right？ So to find。

 all of the tuples S that match this predicate， we do a lookup with this key， right？ Ri。 And。

 then you look up this index on S， this could be for example a B plus tree and you find。

 all of the pages of S that match， right？ And all of the tuples within those pages。 And。

 for every tuple that you produce， you join it with R and you add it to the output。 So what's。

 the cost of the index nest loop join？ Well， the cost is you're reading through all of。

 R so you still have the square bracket R cost plus the number of tuples of R times the cost。

 to find the matching S tuples。 And the cost to find the matching S tuples varies quite a， bit。

 Both depending on the number of matching S tuples as well as the alternative that you。

 use to encode the B plus tree。 So if you remember， we had alternative one， two and three。

 alternative， one was where the record was stored in the B plus tree itself and two and three were where。

 the B plus tree simply encoded pointers to the records which are on disk， right？ In a heap。

 file for example。 Okay， so if we used alternative one， then the cost for each lookup， right？

 For each tuple is basically the cost to traverse tree from root to leaf。 This could be anywhere。

 between let's say two to four IOs。 Okay， so usually the trees as we discussed are not。

 very deep and so there's not that many IOs that you would need to reach a leaf。 And this。

 could also be smaller if some of the pages are already in your buffer， right？ For example。

 the root page of your B plus tree is typically always in buffer just because it's so frequently。

 accessed。 For alternative two or three， again， going through the B plus tree is like two to。

 four IOs and then there's a cost retrieving the records， okay？ Using the record IDs。 Again。

 record ID is basically a pair of the page ID and the slot ID。 This depends on what type。

 of index you're using。 So if you're using a cluster index， you basically encode the。

 you sort of provide a cost of one IO for every page of matching as tuples while for an unclustered。

 index。 If you remember those pointers crisscross in an unclustered index and in this case you。

 can't avoid paying one IO for every single matching as to。 So there are pros and cons。

 for this indexness and loop join， right？ So if the number of matching as tuples is very。

 very large and you have an unclustered index， then sometimes the indexness loop join ends。

 up being costly enough that it's not a viable alternative compared to other join methods。 Alright？

 Any questions about this stuff？ Okay， so let's talk about sortma join。 So a sortma。

 join as the name suggests uses sorting as a fundamental component while doing the join。

 So it leverages sorting to do the join。 And so a sortma join is used when you have an。

 equality predicate。 So it is applicable when you're doing an equidjoin or a natural join。 And again。

 you can sort of get the hint of why。 Well， the attributes that you would be。

 using for an equidjoin or a natural join would be the ones you would be sorting by。 So the。

 two stages to a sortma join。 The first stage is you sort R and S by the join key。 Okay？ So。

 the attributes that you're using for the join， that's really what you're going to start。

 by sorting R and S on。 And so what this guarantees you is that all tuples with the same key are。

 in consecutive order。 And that allows you to consume these tuples in that order。 In certain， cases。

 you don't need to explicitly sort the tuples in R and S by the join key。 These。

 in the input might actually already be sorted。 For example， if you already had a sort like。

 a sort merge prior to this， which is your child， the input may be sorted， right？ So R。

 and S may be sorted for that reason。 Or if you're using an index scan， maybe the tuples。

 are produced in sorted order。 So in some cases， you mean not even need to sort explicitly。

 It may be already produced to you in sorted order。 The join pass is basically going to。

 do the merge。 So it's scanning the sorted partitions and then emitting tuples at match。

 Now the challenge with this sort merge join is that each tuple in R may match multiple。

 tuples in S and vice versa。 And so that's where things get a little tricky compared to a vanilla。

 merge sort type algorithm。 So you need to keep a little bit more state to ensure that。

 all possible pairs of tuples that can be joined are actually joined。 And so the way we do this。

 is we keep track of the start of each block of S tuples with a mark。 And then we sort of。

 use that mark to designate how much to rewind back once you're done processing a given tuple， of R。

 So this way we know better return for the next tuple of R。 So one way to think about。

 this is that R is kind of like an outer loop。 If you want to do an analogy to the nested loop。

 algorithm， R is kind of like the outer loop。 It only advances forward。 S is the inner loop。

 which sort of moves forward and then moves back up。 So it's sort of the mark is used to。

 designate the start of a block of tuples。 So this sort much algorithm is actually quite。

 involved and you may not get it the first time sort of you I walk you through the intuition。

 So I encourage you to sort of spend some time staring at this after the fact。 So it may not。

 be immediately obvious but in hindsight， I promise you it will make sense given enough， time。

 So before I get into sort of the mechanics， thereof。

 I want to give two separate intuitions and then I walk you through the code。 So if。

 I have these two tuples and I want to do a sort mark join and these are sorted。 So these。

 are sorted by in order of SID and I'm doing the join on SID。 So the tuples on the left。

 this tuple is going to join with these two tuples。 And then this tuple on the left。 So。

 this is R and this is S is going to join with these two tuples and then the subsequent tuple。

 lover two is going to join with these two and then finally rusty is going to join with。

 107 at the bottom。 So unlike a merge sort where you can simply go through these two sort of。

 partitions in order， in the S case you need to go down and then you need to go back up。

 So that's where things get a little tricky。 So here's the second illustration of the sort。

 merge algorithm。 Sorry， sort merge join。 So here I start with the pointers pointing to。

 the first records of both of these relations。 Again， these relations are in sorted order。

 and I'm going to push as I would do in merge sort these pointers flow down from the top。

 to the bottom。 I'll go down this list of sorted tuples。 Okay， so in this particular case I。

 will go down from the first tuple to the second tuple on the left because the tuple on the。

 right is larger than the tuple on the left。 Now I found two tuples that match。 These two。

 are ready to be joined。 So what I'm going to do is I'm going to do a mark。 I'm going， to mark this。

 It's the start of tuples corresponding to SID 28。 And then I can start producing results。

 So I'm going to produce a result corresponding to YupE 103。 Then I'm going to join YupE with， 104。

 And then now I'm done。 So there's no more tuples to be produced which have YupE on the。

 left hand side。 Now this is where the mark comes in handy。 I can now rewind to bring this。

 right hand side pointer back to the mark to start producing results for the next tuple， on the left。

 Okay， on R。 So I'll advance the pointer on the left hand side to 31。 I realized。

 that 31 and 28 don't join。 So I need to advance the pointer on the right hand side。 I'll advance。

 it to 31。 Okay。 And once again I have added a mark to indicate the start of a block of。

 tuples corresponding to a given value 31。 Now I can start producing output。 Right。 LABAR。

 will join with 101。 I can produce an output。 LABAR is going to join again with 102。 I'm。

 going to add another tuple to the output。 Now I've gone too far。 I've gone to 42。 42 doesn't。

 join with 31。 So I need to rewind back to 31。 And I'm going to advance the left hand。

 side pointer to LABAR 2。 So LABAR 2 is now going to join with 101。 Right。 I'm going to。

 produce an output。 LABAR 2 is going to join with 102。 I'm going to produce an output。

 Now once again， because I have a mark here， this black arrow， I can rewind back。 And I。

 know where to go back because I'm done with producing results for LABAR 2。 I can now advance。

 LABAR 2 to GUPY。 And in this particular case， there's no join tuples that will be produced。

 as a result。 And so I'll advance the pointer on the right hand side to 58。 Advance a pointer。

 on the left hand side to 58。 Now again， I have the chance to produce some output。 So I produce。

 some output and I advance pointer。 And that is the intuition here。 Okay。 Now with this， intuition。

 let's go through the code。 Okay。 So this is one。 This is the second illustration。

 I wanted to give you。 Let's go through the code。 Okay。 So like I said， this takes a couple。

 of times to go through。 So I would a couple of attempts to sort of understand the intuition。

 So I encourage you to set up this code after the class as well。 Okay。 All right。 So this。

 mark variable is basically encoding whether there's a blue arrow or not。 Right now there's。

 no blue arrow。 R is encoding the pointer on the left hand side。 S is encoding the pointer。

 on the right hand side。 Okay。 So right now there's no mark。 So I'm basically in this， if statement。

 I'm going to advance R if R is less than S。 Okay。 So R right now is less。

 than S because it's pointing to 22 while S is 28。 So I'm going to advance R。 I don't need。

 to advance S because R is not greater than S。 So now I've found two tuples that match， basically。

 Right。 I'm now going to start by adding a mark saying that this is the start。

 of the block of tuples for which I need to do a join。 So this is basically the start of。

 a block of tuples。 It's also going to remember where I need to go back once I'm done processing。

 a tuple on the left hand side。 So now I'm in the stage where R is equal to S。 Okay。 So。

 28 is equal to 28。 So I can now start producing output。 So I add R comma S to the result。 Okay。

 So the result is producing a temporary variable that's going to be referring to the result。

 that's going to be produced。 I'm going to advance S because I want to move to the next potential。

 tuple that I will that be used to produce result to pull subsequently and I'll produce。

 the result to pull。 Right。 The previous result to pull which was 28 and 103。 So that was。

 this and now my pointer is pointing at the next tuple that needs to be joined with the。

 upy and once again this mark is recording where I need to return once I'm done with processing， upy。

 So is there a mark or not？ Well， there is a mark。 So I'm not in this first if statement。

 is R equal to S。 Yes， R is equal to S。 So I'm going to add another tuple to the output so。

 that tuple is going to be instantiated as this result variable。 I'm going to then advance。

 S because I know that I'm done with processing that tuple and I'm going to produce that result。

 So that result is going to be produced as part of the next call to this to this algorithm。

 or this operator。 Okay。 So the next round of this operator basically I once again have， a mark。

 So the mark is still there。 So I'm still not in。 I don't match this if statement。 I。

 go to the next if statement which is is R equal to S。 Here I've advanced S too far。 So S is。

 no longer equal to R。 Right。 So this we are not not in this condition。 So I'm going to。

 go to the else statement。 So the else statement says， Hey， you've advanced S too far。 You're。

 not going to find anything more that matches。 So you're going to reset S to mark。 Okay。 So。

 you're going to rewind S to mark and you're going to advance R。 So you're going to move。

 R to the next one because you're done with processing all of the the joint tuples that。

 have yuppy on the left hand side。 So you move to lover。 Right。 Remember that you are processing。

 through all of the tuples in R in sequence R is kind of the outer loop in this case。 Okay。

 So you've advanced R and you're setting the mark to null。 Okay。 So you're basically getting。

 rid of this pointer because you're not started processing a block of tuples of S yet。 Okay。

 You'll do that in the next stage。 Okay。 So now we are in the stage where we don't have， a mark。

 Okay。 So we will go into this if clause。 We will then advance both R and S until we。

 have a likely match。 So is R less than S？ No。 So you don't need to advance R is R greater。

 than S than advanced S。 So you're going to advance S until you find 31。 Okay。 And now。

 you're going to do a mark at that point indicating that you're going to now start processing a。

 block of tuples on the right hand side R is equal to S。 Okay。 So this 31 is equal to 31。

 So that means that you are also going to produce an output。 So result is going to refer to that。

 output。 You're going to then advance S while remembering that the mark is always there to return。

 to if you need to once you're done processing LABBA and you're moving to LABBA2 and you produce。

 a result。 So the result is going to be LABBA and 101。 Now you had the mark， right？ So you。

 you skip this if statement and you move again to this if statement is R equal to S。

 Yes again R is equal to S and therefore result will get in instantiated with this pair， LABBA， 102。

 You're going to advance S。 So you're going to move S to 42。 Remember again the mark is。

 always there to return to when you need it and you're going to return this result。 Okay。 So this。

 result is going to be LABBA corresponding to 102。 Now another iteration of this loop。 Is there a。

 mark or not？ Yes there is a mark， right？ So you're not fully done processing that block yet or at。

 least you've not detected that you're done processing that block yet。 Is R equal to S？

 R is not equal to， S because 31 is not equal to 42。 So you move to the else statement here。

 Now this is when you realize， that you're no longer processing that block of tuples you need to rewind S。

 So you're going to reset， S to mark and then advance R because you're done processing LABBA。

 LABBA is no longer going to be the， left hand side of any joint to close from this point on。

 You're also going to set mark to be now。 Okay。 Next iteration。

 Now LABBA 2 is going to get joined with 101 and 102 in this and， subsequent iterations。

 You don't have a mark yet because you've not yet started processing a block， of tuples。

 You since R and S are equal you will not sort of fall into either one of these。

 wireless statements and then you set the mark to be equal to this 31-101 record。 R is equal to S。

 in this case。 Okay。 So you're going to produce a result that is corresponding to LABBA and 101。

 LABBA 2 and 101。 And then you can advance S while being sure that mark is always there if you need it。

 and LABBA 2 is going to be added to the result with 101 on the right hand side。

 Back at the top ready for the next iteration is there a mark or not？ There is a mark。 So you're。

 going to skip this if statement and you're going to go to the next if statement is R equal to S。

 R is equal to S so you're ready to produce another output and this time corresponding to LABBA 2。

 and 102。 So you're going to add that to this result temporary result。 Periodo。

 you're going to advance S。 S is now going to point to 42 and you're now ready to produce the result。

 Okay。 So the result is going to be LABBA 2 and 102。 So you're going to add that to the result。

 And now you're back at the start of the loop。 Do you have a mark？ Yes。 You do have a mark。

 And is R equal to S。 R is no longer equal to S。 You've gone too far on S。 Now you need to basically。

 stop the processing of this block。 So you basically go to the L statement。

 You reset S to mark so you， rewind to the start of the block。

 You advance R basically you've indicated that there's no more。

 two poles that are going to be produced with LABBA 2 on the left hand side。

 You set the mark to null， because you're not starting a new， you're not。

 you're completing that block so the mark needs to be， set to null。 Okay。 All right。 So next。

 you're at the start of the loop for another iteration。 There is no mark。

 So you're now going to figure out where to start the next block of two poles on the。

 on the right hand side on S。 You go into this if statement is R less than S。 R is not less than S。

 So you're not going to advance R is R greater than S。 R is greater than S。

 So you're going to end up， advancing S。 Skipping over 42 because 42 is not going to join with 44。

 You go all the way to 48。 You're now going to denote 58 with a mark。 Okay。

 This is going to indicate the start of a new block， of records。

 Now you're checking if R is equal to S。 R is not equal to S in this case。 So you're。

 going to actually move to this else statement。 Now you're going to reset S to mark。 In this case。

 there's no action。 It doesn't change。 You're going to then advance R。 So basically you're。

 determined that there's no two poles corresponding to copy。 You then want to set mark to null。

 and then you're back to the start。 So there's no mark。 So once again， you're going to go into this。

 if clause。 There's no need to advance either one of these because they are equal。 Mark is going to。

 be set to this last tuple in S is R equal to S。 In this case， R is equal to S。 So great。 We have。

 the ability to produce a result to go。 So you add that result to corresponding to this rusty and。

 107。 You advance S to the next tuple in S， which is basically the end of file and you return the result。

 Okay， then you back at the start。 So there is a mark。 So you go down into this if clause。

 and then you realize that you've gone too far in S and therefore there is no more tuples that can be。

 produced from this joint。 And so that's the end of your processing。 So basically that is a it's a。

 fairly involved algorithm。 But hopefully after going through it a couple of times， it'll become。

 clearer to you。 So really all that bookkeeping here is to ensure that you're going through all。

 of our in sequence and you're going through S in fits and starts。 So you start a block of tuples。

 then you go down and then you remember where you need to go back。 So you go back up there。

 Then you start the next you move S you move R down and then you go down again。 Then you figure out。

 where to go back。 So that the mark is there as a means to remember where to reset X as you're doing。

 this sort much。 Okay。 So I'm glad that Alvin is running a poll because this is a fairly involved algorithm。

 In fact， my intent to adding yet another animation as I was describing to Alvin earlier was to try to。

 make this a little easier to understand。 But it's still pretty non-trivial。 So when you。

 so what is the M condition when you find that you can no longer advance S。

 when either or R nor S can be advanced。 That's when you hit the end of file that you know that you。

 don't need to you don't need to do anymore。 You know that you're not going to produce any more。

 jointables。 So we got like 13 out of 70 people getting this。 So if like you know。

 can someone please ask a question？ Yeah。 And good questions。 Carson。

 So I have a question about the index nested loop joints。



![](img/61dd289783a605e30da0eca1ed23e63b_7.png)

 So regarding the cost of that， there's one part of it that's dependent on the total number of。



![](img/61dd289783a605e30da0eca1ed23e63b_9.png)

 records。 Yeah。 Where does this part come from？ This R you mean？ The second R yeah。 Yeah。

 So that so basically I mean think about it in the following way。 You're reading through all。

 of R so you have all the pages of R as part of the cost。 So that is the square bracket spot。

 And then for every tuple of R， so that's where the cardinality of R comes in， you basically look。

 up all of the tuples of S。 Oh， right。 Right。 So for imagine if you have 100，000 tuples of R for。

 every single one， you're going through this index。 So you have 100。

000 times the cost of going through， the index and retrieving the matching as tuples。 Right。

 So that's where the cost comes from。 So are we stopping here for today and then let everyone go if you don't have questions or if you。

 do then please stay and ask or are we continuing？ I think we should stop and let's the start of the。

 next lecture。 I won't go through the algorithm again because it's like 50 slides of animation。

 but I can answer specific questions that students have。 So I'm happy to answer any questions about。

 any aspect of the algorithm that wasn't clear and then I'll continue from there on。

 And if no one has any questions by the next lecture。

 then we will go through the same animation again， and again until you guys get it。 Alright， anyway。

 thanks everyone。 See you Thursday。 Have you have questions？ Please stay。 Oh。

 I do have a quick question。 So it seems like in this class， when we analyze the time cost。

 we mainly focus on the IO， like not the time of the wrong time of the algorithm。 So is it because。

 the IO cost just dominates the， let's say the wrong time of the algorithm？



![](img/61dd289783a605e30da0eca1ed23e63b_11.png)

 Yeah， so that is， so certainly you could have a， so in classically， this used to be a lot slower。

 than computation。 Okay， so and therefore， IO used to be the dominant factor in costing in database。

 systems。 And that is a convention that we are still following。 In modern times， this have gotten。

 a lot faster and so you could technically do a more balanced costing that involves both the cost。

 of the computation in memory as well as the IO's。 So you could have a have a more sophisticated。

 cost model for simplicity。 We are doing just the disk part， so the just the IO's from disk。

 That is a pretty large cost， but I wouldn't say that it is the only cost。 I see that makes sense。

 Thank you。 Actually， also， if you remember from the lecture on on sorting， yeah。

 on actually on the heap files and different types of files， right？ So remember that we talked。

 about all these different operations， right， like insertion， deletion。

 and then equality predicate and then range predicate， right？

 So remember that if we actually look into， complexity， like they're all boring complexity。

 they're all polynomial or they're all like n， squares or n log n or something。

 So that's like actually very boring。 Same thing even for joints， right？ So like， you know。

 if you look across the different algorithms that we went through today。

 they're all like just second order。 They're all n squared algorithm。 The details actually all in。

 the IO costs in terms of like the constant factors that get added to it。 Like what I did the other。

 same。 So that actually turns out to be the more dominating or the more pronounced thing that you。

 see if you actually do this for real。 Yeah， God， thank you。 But if you look at like Postgres' cost。

 sort of model， for example， you'll see that it's a lot more sophisticated than the simple ones。

 if you present it。 For example， I encourage you to go take a look at sort of some of the open source。

 systems and that costs。 The index costs？ No， just in general， how do they do costing？ And I'm happy。

 to provide resources if you're curious。 Sure。 So I had a question about the iterator portion of。

 the lecture。 And when you're calling next， are you calling next on like the next like record that。

 you're supposed to be looking at？ Or are you calling next on like you're going from like the project。

 operator to the select operator？ Like how you distinguish between going from one operator to another？



![](img/61dd289783a605e30da0eca1ed23e63b_13.png)

 So by the way， Alvin should be stopped recording。 Maybe we should。 [BLANK_AUDIO]。

