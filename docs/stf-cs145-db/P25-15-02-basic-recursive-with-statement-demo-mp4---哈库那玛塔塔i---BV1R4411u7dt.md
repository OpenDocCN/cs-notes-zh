# P25：15-02-basic-recursive-with-statement-demo.mp4 - 哈库那玛塔塔i - BV1R4411u7dt

 This video gives a live demonstration of the recursive constructs in SQL that we introduced in the previous video。



![](img/21534375bc2b413d811307b8b694e624_1.png)

 As a reminder， recursion has been introduced into SQL as part of the width statement where we can set up relations that are defined by queries that themselves refer to the relation being defined。

 And finally， we have a query that can involve the recursively defined relations as well as other tables in the database。

 The typical expression within a width statement for recursively defined relation would be to have a base query that doesn't depend on R and then a recursive query that does depend on R。

 We gave three examples in the introductory video， and those are the same examples that we'll be demonstrating shortly。

 The first one was to compute ancestors when we have only a parent relation and the family tree could be arbitrarily deep。

 Our second example was a case where we have an arbitrarily deep company hierarchy and we want to compute the total salary cost of a project starting at that project's manager and summing the salaries of the entire sub tree。

 And our third example was about airplane flights where we want to find the cheapest way to fly from point A to point B and we're willing to change planes as many times as we might need to in order to bring down the cost。

 We saw that all of these examples involved basically a notion of transit of closure computed as a recursively defined relation。

 The last portion of our demo after we see these three queries solved using recursion will introduce one more twist。

 which is what happens when we introduce cycles。 So in the airline example。

 we'll set up a case where you can fly from one city to another one and back。

 which is of course true in reality， and we'll see what happens when we try to answer our query in that setting。

 I've started by creating a table called parent of with parent child relationships。

 So we have Alice Carol Bob， Carol Carol， Dave and so on。

 You might actually want to write this down in a piece of paper to see what the actual tree looks like。

 but the query we want to run is to find all of Mary's ancestors。

 So we're going to of course have Eve as a parent and Dave as a parent and then Dave's parent is Carol and Carol's parent is Bob and so on。

 We'll get most of the data in our database in our query。 So here is the query。

 It's our first example of a recursive query。 Let me say right off that even more than anything else we've done in these videos。

 I am going to encourage you to download the script and take a close look at the query and preferably actually run the queries and play with them on the Postgres system。

 And we are using for this demo Postgres， a SQL item MySQL do not support the with recursive statement at this point in time。

 So anyway， here's our query and it is the form that we described in the introduction。

 It's a with statement with recursive that's going to set up a recursive relation called ancestor。

 So this is what we were calling our earlier。 This is our ancestor with the schema AD for ancestor and descendant。

 Our final query once ancestor is all set up is very simple。

 It just says take the A attribute from ancestor where a descendant is Mary。

 So that will give us Mary's descendants。 Of course。

 what's interesting is what's right here inside these parens because this is our recursive query and it does take the form we described of having a base query。

 That's the first line and then the recursive query with a union between them。

 So we're going to start by saying that whenever we have a parent child relationship。

 that's also an ancestor relationship。 So we're going to take from our parent of table。

 the parent and child and we have to rename them as A and D。

 And that says that parent children are in ancestor。 What else is an ancestor？ Well。

 if we have a top of an ancestor， an ancestor， and a descendant。

 and that descendant is the parent of another person， then the ancestor。

 the A and the ancestor together with the child from the parent of is also an ancestor relationship。

 So this is kind of doing the join， not just kind of。

 it's actually joining our ancestor as it's been created and extending that relationship by joining with another instance of parent。

 So you can kind of think of going down the ancestor tree adding relationships as we go down。 Again。

 I really can't encourage you enough to download this query and play with it yourself to fully understand what's going on。

 Let's go ahead and run it。 It's going to be rather anticlimactic。 When we run it。

 we do discover that these five people are Mary's ancestors。

 and if you draw on the little tree of the data， you can verify that that's the correct answer。

 Let's play around a little bit and try a few other people's ancestors。 Let's try Frank。

 We don't see Frank here because Frank actually happens to be a child of Mary。

 so we should get even more ancestors when we write that when we run this one。

 especially Mary should be included。 And in fact， she is。 There she is。

 And these are Frank's ancestors。 Let's try George。

 I think George was somewhere in the middle of the tree there。 Yes， George has three ancestors。

 And finally， let's try Bob。 I think Bob is at the root。

 so we should get an empty result and we do because again Bob has no ancestors in our database。

 Now let's take a look at our second example。 That was the one where we had a hierarchy of management chain in a company。

 and then we were interested in computing the total salary cost of a project。

 So I've set up our three tables。 The first one is the employee table。

 It just gives the IDs of the employees and the salary of each employee。

 The second table is the manager relationship。 So again， you might want to draw the little tree here。

 although it's pretty simple this time。 One， two， three is at the root of our little management structure has two。

 three， four as a subordinate。 Two， three， four has two subordinates， three， four， five， and four。

 five， six。 M three， four， five is another one。 So it's only a three level tree。 Of course。

 if we knew it， we're only three levels， we wouldn't need recursion at all。

 but we're going to write a query that will work for arbitrary numbers of levels。

 So that's our management structure。 And finally， our third table。

 the project table says that employee one， two， three is the manager of project X。

 So what we want to do is find the manager of project X in the hierarchy and then take that manager's salary along with the salaries of all of the managers。

 Subordinates recursively down the management structure。 And of course。

 that's everybody in our little database。

![](img/21534375bc2b413d811307b8b694e624_3.png)

 Again， can't encourage you enough to download the script and run it for yourself。

 So here's our query to find the total salary of project X。

 And I'm actually going to give a couple of different ways of running this query。

 The way we've done it the first time is to effectively expand the management structure into a relation called Superior。

 So that's really pretty much doing the ancestor computation。

 which by the way is a transitive closure。 I should have mentioned that earlier。

 For those of you familiar with transitive closure， it's basically that operation。

 So we're going to compute these superiors so that we'll have every manager and employee relationship where the manager is arbitrarily above the employee。

 And then once we have that superior relationship computed。

 then we write actually a fairly complicated query。 So this is the final query of our with statement。

 And this one says we've got this recursive relation superior。

 We're going to sum up the salaries from the employee relation where the ID is either the manager of the project X。

 So that's the first half here。 Or the an employee that's managed by the manager of project X。

 Now this down here， I just want to emphasize this is not recursive。

 It just so happens to have that same structure of union。

 But there's nothing recursive happening down here。

 So this is just a regular SQL query once we have the superior relation。

 That's the transitive closure of the manager relation。 So let's take a look at superior。

 Superior here， this is recursive with the union says that if we have a manager and that's the M ID and E ID。

 then if somebody is managing someone else， then they are their superior。 Notice by the way。

 I didn't specify a schema here。 So the schema is implicitly going to be M ID E ID。

 So we're going to put manager relationships in。 And then if we have a superior relationship。

 so if we have an M ID managing an E ID in the S relationship。

 then we can add one more level because we join with the manager saying that if we have if X is a superior of Y and Y is the manager of Z。

 then X is a superior of Z。 This parallels exactly what we did with the ancestor computation in the previous example。

 Again， it's going to be rather anti climactic to run the query， but let's do it。

 And we find out that 400 is the total salary cost of project X when we count the manager of project X together with all of the people。



![](img/21534375bc2b413d811307b8b694e624_5.png)

 Underneath that manager in the hierarchical structure。 So when we think of recursion。

 we often think of transitive closure or expanding hierarchies as we've done with our examples so far。

 But if we step back for a second， we can see that there's quite a bit。

 quite a bit simpler way to express the query that finds the salary burden of project X。 Now。

 not only is this actually nicer to look at， it's probably much more efficient depending on how smart the query processor is。

 In our previous example， if the query processor X used the query in the straightforward way。

 it would compute the superior relationship for the absolute entire company hierarchy before it figured out which of those people were involved in project X。

 Now， a really good query processor might actually figure out to fold in a project X。

 but not necessarily。 Here's an example， and here's a new formulation of the query。

 where we're actually going to tie X specifically to our recursion。

 What we're going to compute in our recursive with statement here。

 so this is the temporary relation we're computing。

 is a relation containing just a list of the IDs of the employees who are involved in project X。

 Once we have all the employees involved in project X， the query down here is trivial。

 We just find those employees who are among the X employees， and we sum up their salaries。

 So let's take a look at the recursive definition here， and again。

 it's taking the usual form of a base query， union， or recursive query。 And here's what we do。 Well。

 obviously， the manager of project X is one of the IDs involved in project X。

 So here we find in the project the project named X， and we take the manager of that project。

 and we put that person's ID into XMs。 That's the first ID that's going to go in there that's going to seed the recursion。

 That's again the base query。 Then we add in our recursive step any employee who is managed by anybody who's in the X employees。

 So we'll take our manager relationship， our X employees relationship。

 and if the employees manager is in X， then that employee is also involved in X。

 So we seed the recursion with the manager of project X。

 and then we just recursively go down the tree adding all the employees that are underneath one by one。

 We don't have to know the depth of the tree because the recursion will continue until nobody else is added。

 I guess I should have mentioned that earlier in my earlier examples。 Again。

 the recursion sort of adds data over and over again until there's nothing new to add。

 and that's when it terminates。 So let's go ahead and run the query， anti-climactic again。

 but we get the same answer of 400 as the salary cost of project X。

 Now we use the same form of query to find the total salary cost of two projects， Y and Z。

 and that will also demonstrate having two relations that are defined in the with recursive command。



![](img/21534375bc2b413d811307b8b694e624_7.png)

 So we've added projects Y and Z to our project table。

 and they're both managed by employees who are already in the database。

 so they're a little lower down the hierarchy。 We should expect those projects to have lower total costs than for project X whose manager was at the root of our hierarchy。

 So here's our query。 It's a big one。 We're going to define YMs and ZMs exactly as we defined XMs in the previous examples。

 So YMs is a table of a recursively defined relation temporary that's going to contain a list of IDs of the people that employees who are involved in project Y。

 So we're going to put the manager of project Y as our base query。

 and then we're going to add to it in the recursion all of the employees who are managed by someone who's in the YMs。

 And ZMs is exactly the same。 We start with the manager of project Z。

 and then we add to it all of the people who are managed transitively down the tree by someone who's in the ZMs relation。

 And then our final query down here for the with statement is a union of two queries。

 The first one gets the total salary for Y， and it labels it as Y total。

 So it takes all the IDs that are in the YMs table。

 and from the employee table gets their salaries and sums them up， and similarly the Z total。

 So now we'll run this query。 It'll be slightly less anti-climatic。

 We do have now two tuples in our result。

![](img/21534375bc2b413d811307b8b694e624_9.png)

 We see that the total salary for Y is 300 and the total salaries for Z is 70。

 And if you cross check this result against the data。

 you'll see that these are indeed the total salaries when we take the managers we specified for projects Y and Z。



![](img/21534375bc2b413d811307b8b694e624_11.png)

 And finally， our last and most fun example， the one to find how to fly from point A to point B when all we're concerned about is cost。

 and we don't care how many times we have to change planes。

 So here's the little flights table I've set up， and I used A and B so we can literally fly from point A to point B。

 All of our intermediate destinations are actually real airport codes， and I've put in some airlines。

 although they're not actually going to be used in our query。

 And then I've put in the cost of the flights。 You might want to draw yourself a little graph so you can see what's going on。

 and we can fly from A to Chicago for 200 from Chicago to B for another 100。

 or we can go from A to Phoenix。 And then Phoenix to Las Vegas and Las Vegas to， oh。

 I don't remember what this is， C M H Detroit Cincinnati somewhere in the Midwest。

 and from there to point B， or we can take a nonstop from A to B on good old jet blue for 195。

 So clearly we're never going to be going through Chicago for a total of 300 with that jet blue flight。

 But I've set up the data as you're probably not surprised so that there's a long route through Phoenix to Las Vegas and somewhere in the Midwest is in fact going to be our cheapest way to go。

 So now let's take a look at the recursive query that's going to find us our route from point A to point B。

 or at least find us the cheapest way to get from point A to point B。

 So the first query I'm going to show actually gives us all the different costs of getting from A to B just so we can see those enumerated for us。

 and then we'll modify the query to give us the cheapest cost。 So here's the recursive query。

 and we're going to use a recursively defined relation called root。

 And root says that we can get from an origin to a destination for a particular total cost。 Okay。

 so we again in our recursion have the base query and the recursive query。

 This is exactly what you'd imagine。 We can certainly get from point X to point Y for a total cost if we can take a direct flight from point X to point Y for a given top cost。

 So that's our base query。 We start out with all of the direct flights in our root relation。

 and then we start adding roots by doing the join of a root with an additional flight。

 So basically what this joint here says is if I can get from the origin in a root to the destination。

 and then that destination is the origin of another flight， then I can add that flight。

 I can start with my original origin， final destination。

 and the cost of that is going to be the total that I already had plus the cost of the new flight。

 and that's my new total。 So again， this is another transit of closure like recursion。

 It's very similar to the ancestor recursion， very similar to expanding the company hierarchy。

 The only real difference here is that we're also accumulating these costs as we do the recursion。

 So once we've done this recursion， then we have a complete specification of all the roots within our flights database all of the ways we can get from A to B。

 And the total cost。 Now one thing I should say is this is not actually giving us the ways of getting from one place to another。

 If we wanted to accumulate the actual root that we take。

 so the flights and the costs and the airlines and so on。

 we'd have to kind of use a structured structure inside our database to accumulate those。

 There are ways of doing that， but I'm not going to demonstrate that here。

 I'm just going to demonstrate the basic use of recursion and computing the total cost。 Okay。

 so let's go ahead and run this query。 So we've computed all of the roots and then we're just going to start by finding the roots from A to B and what the total costs of those are。

 So we'll run the query and we'll find out that there are three ways of getting from A to B。

 The first one happened to be that direct jet blue flight for 195。

 The second was the flight through Chicago for a total cost of 300。

 You can go back and look at the data and verify these。

 And the third one was that complicated rooting where we stopped several times。

 but we save a lot of money。 Well， $20 over the direct flight by going through those cities because the total cost is 175。

 I'll leave it up to you whether it's worth $20 to stop several times versus the direct flight。

 So now since my actual specification of what I wanted to know was the cheapest way to go。

 then I just say min total instead of star in my final query。

 And I run that and my answer is that 175 is the cheapest way to get from A to B。

 Now here's an alternative formulation of the same query that essentially parallels the alternative that we looked at with our project costs where we built in project X into our recursion that simplified the recursion in that case。

 In this case it's not simpler， but it could potentially be more efficient。

 We're going to build in the fact that we're starting from origin A。

 So instead of finding all roots from any point to any other point in our recursion and then finding the roots from A to B。

 let's create a relation recursively that says starting from point A。

 I can get to a particular destination for a particular total cost。

 So this is going to build up roots starting from A。

 the base query is going to of course start by looking at direct flights where the origin is A and it's going to put the destination and the cost into our relation called from A。

 So that starts with that first gives us direct flights from A where we can get on the direct where we can get to and how much it will cost us。

 And then our recursion is going to add flights to that one。

 Again it really parallels what we did with the project X。 Our recursion is going to say， okay。

 we know we can get from particular， we can get to a particular place from point A for a certain cost。

 So that's our destination。 If we add one more flight。

 so the origin of that flight is the destination where we can get。

 then that will also be a destination that we can get to from point A and we'll just add the address。

 And we'll just add the cost of the additional flight on。 One more time。

 a strong suggestion that you download and try these things for yourself。

 Once we've found all the places we can get from A。

 then we'll use that to figure out the cheapest way to get to point B。

 But let's just start by running with the width statement where all we do is see the places we can get to from A and the total cost of getting there。

 So here we go， and we can get to Chicago Phoenix， we can get to be a couple of different ways。

 three different ways actually， as we already knew。

 we can also get to Las Vegas and this mysterious CMH I wish I remembered what it worked。

 So now if we're interested in finding the cheapest way to get from A to B。

 then we'll add where the destination equals B on here and we'll add the minimum total cost。

 And hopefully that will be our good old 175 and indeed it is。 By the way。

 we can do the same basic idea about backwards， instead of finding all the places that we can get from city A。

 how about if we find all the places from which we can get to city B。

 So here's the query that does that。 To be is going to be a recursively defined relation that's going to give us the origin。

 the place from which we can get to be and the total cost of getting to be from that place。 So again。

 the structure is exactly parallel。 We start out with our base query saying if we have a direct flight to B。

 then we can get from the origin of that direct flight at the cost of the flight to B。

 And then we recursively add flights on， but you can think of if you're going from left to right。

 adding flights from the left。 So if we know we can get from a place to B and then we can go from。

 take a direct flight from somewhere else to that place。

 then we can get from that somewhere else to B。 Anyway， so we do that again by joining。

 so we're going to take our origin from which we can get to B。

 We're going to find flights that take us to that origin。 We're going to add the cost of that flight。

 and that gives us a new way to get to B。 And then let me start by just writing the query that finds all of the places from which we can get to be in the cost of getting there。

 We'll run the query and we can see that we can get to B from point A in three different ways and from our other cities in our database as well。

 Similarly to what we did previously， if we're particularly interested in getting from A to B。

 whoops， let's make that our origin， then we add where origin equals A。 And if we want the minimum。

 it would be our minimum total， again paralleling exactly what we did before。

 we run it and good old 175 comes out。 Now we're going to have some real fun because I added another flight to our database。

 And this flight takes us from Columbus， I now know it's Columbus。

 to Phoenix and creates a loop in our flights。 So that means that we can fly from A to Phoenix to Las Vegas to Columbus back to Phoenix and then to Las Vegas and Columbus again。

 So we're going to have arbitrarily， actually unbounded。

 actually infinite length routes that we can take now。

 Now obviously those routes aren't going to ever be the cheapest way because as we take those routes it's going to get more and more expensive。

 None of them are negative costs paying us to take flights。

 But if we just do our naive recursion where we generate all of our routes before we take a look at our final query。

 then we're going to be generating an infinite number of routes。 So here's our original query。

 the first one we wrote where we were just finding all of the costs of getting from A to B by computing all of the routes in the entire database and then looking at those from A to B。

 Now with our additional flight that creates a loop we run this command and nothing happens。

 Actually if we wait long enough we're going to get an error。 Well okay， we waited for a while。

 It appears that the user interface we're using isn't going to show us the error。

 But if you try running this in Postgres command line interface I assure you if you wait long enough eventually it'll tell you that the recursion effectively overflowed。

 So it is trying to compute this unbounded number of routes in the recursive part of the with statement and never even gets to the query that we want to execute。



![](img/21534375bc2b413d811307b8b694e624_13.png)

 Okay so here's my first attempt at fixing the problem。

 We know that we're never going to want to take an arbitrarily long route。

 We're never going to want to go around a cycle lots of times as our cheapest way to get from point A to point B。

 So what I've done here and I'm not going to go into this in great detail but I've added a condition in the recursion that says I'm only going to add a new route。

 a new route into my recursively defined route table when the total cost of that route and that's defined as the cost plus total here when we added is less than all of the ways。

 we can already get from that place to that origin to that destination。

 So in other words I'm only going to add cheaper routes than the ones that are already there。

 And by the way if there are no routes already from the origin to the destination then this will be satisfied and we will add that first route then after that only adding cheaper ones。

 So let's try running this query and see what happens。 Well we got an error。

 Now this is not a runtime execution error。 This is actually an error that says we're not allowed to refer to our recursively defined relation in a sub query within our recursion。

 The SQL standard actually might allow this particular use but I don't know that any implementation actually handles it。

 It can be fairly difficult to handle a case where you have the recursively defined relation in a sub query as well as in the outer query here。

 So that's obviously not going to solve our problem。



![](img/21534375bc2b413d811307b8b694e624_15.png)

 Now there's actually a feature of basic SQL that can help us here with our problem。

 There's something called limit。 We actually didn't discuss this in the SQL videos but that says just give us this number of results。

 So let's say that we're going to have our recursion here for the routes but down here we're going to say I only need up to 20 results for how I get from point A to point B。

 And the Postgres system actually makes use of the limit command in the final query to restrict the recursion。

 It's a nice feature and it was added specifically for this problem of possibly infinite recursions where we actually don't want it to be infinite because we only need a finite number of answers。

 Okay so let's go with that here and we'll see that great。 Everything worked well。

 We got our routes from A to B and I do have 20 routes。 So they're getting very expensive。

 Down here I'm going to go around and around the Midwest lots and lots of times but that did limit the recursion。

 It did stop unlike our query where we didn't have the limit and it just went on indefinitely。

 So that looks pretty good with one unfortunate problem which is if we still want the minimum we're going to again get a infinite execution。

 So the old result is still sitting here but now the system is chunking along because the limit here is applied to this min to the number of tuples in our result。

 That's not going to limit the recursion。 We're always going to get only one tuple in our result。

 So even if we said limit one here we'd still get the infinite behavior。

 So we haven't quite solved our problem。

![](img/21534375bc2b413d811307b8b694e624_17.png)

 Okay so here's what we're going to do。 Eslitically maybe it's not the absolutely best solution but I'm going to argue that it's a pretty reasonable one。

 We tried limiting our recursion to only add new routes that were cheaper than existing routes to and from the same place。

 We weren't allowed to do that syntactically。 The recursive with statement didn't allow the sub query with the recursively defined relation in it。

 So we're going to do a different change here where we're not going to add new routes to our flight when the length of the route。

 in other words the number of flights contributing to that route is greater than or equal to ten。

 So how do we do that？ We're going to add to our recursively defined relation route the origin destination and total cost of that and then we're going to add the length。

 And so that's going to put in each route table how many flights were involved in that route。

 So let's see how we do that with our recursion。 We still have the base case here and the recursively defined union。

 In our base case we're going to be adding to our route the nonstop flights so we'll have exactly what we had before and then we'll have the constant one to say that this nonstop flight is just one flight。

 Then when we do our recursion we're joining our route relation that we're building up by extending it with an additional flights exactly as before。

 But there's two changes here。 One of them is that we're going to compute our new length by adding one to the existing length of the route for our new route because we're adding one flight and then we're only going to add tuples to the route relation when the length of the route that we're adding is less than ten。

 So now let's see what happens。 I'm going to start again by looking at all of the costs of getting from point A to point B and then we'll take a look at finding the least。

 So we'll go ahead and execute the query and we see that we have one to three or five ways of getting from A to B where the length of the route。

 the number of flights involved， is less than or equal to ten。 We see our friends here。

 This was the nonstop flight。 This was the one through Boston。 Here's our favorite one。

 And there's a few more。 So these are going to go through that cycle a couple of times。

 But once we get to the length of ten we're not going to add anymore。 So we got termination。

 And if we want to change it to find the minimum cost flight then it's just the min total as before and we'll find good old 175。

 Now what's unesthetic about this is that we're actually limiting the amount of recursion。

 So the whole point of writing recursive queries is when we don't know the maximum number of computations that we need to do to get our answer。

 So maybe it would so happen to turn out that the more than ten flights were required to get the cheapest。

 And if that was the case then we wouldn't get our right answer。

 Of course we could change it to 100 and we'd still get the 175。

 And honestly we could change it to 10，000。 And you can't see it happening here but it is actually recomputing that 175 even when I put in 10。

000。 I can even do 100，000 and it's still going to work for me。

 So if we presume that nobody wants to take more than 100。

000 flights in order to get from point A to point B in the cheapest fashion。

 this would be a reasonable way to bound the recursion and get the answer that we want even in the presence of cycles in our relation。

 [BLANK_AUDIO]。

![](img/21534375bc2b413d811307b8b694e624_19.png)