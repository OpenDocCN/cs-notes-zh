# P14：Lecture 14 Transactions & Concurrency I - ___main___ - BV1cL411t7Fz

 Okay， I'm recording to the cloud。

![](img/a35d787499b28aec4dd3ca25f0963939_1.png)

 Oh， so I was sorry。 Okay。 Hello everyone。 Welcome to Tuesday's lecture。

 I hope all of your midterms are over by now， hopefully。

 and you have recovering or you have already recovered。

 We'll say a few words about the midterm later on in the lecture。 So for today。

 the plan is to basically finish up what we have been talking about last week in terms of create optimization。

 And then we actually move on to the next exciting topic of transactions later on。

 So I'm just going to first show a bunch of slides that were from last week。

 And then if you have questions， just stop me at any point。 So again。

 our goal is to basically give an query to figure out the best way to exit。

 So the best way in terms of time， in terms of IO， in terms of memory。

 there can be many different criteria。 But for this class。

 we're now we're just going to consider time and IO to be the most important factor。 Okay。

 So here is the naive implementation of a clear optimizer。

 So we're just going to enumerate everything and then we're going to estimate the cost of everything that we have enumerated。

 And then pick the one with the lowest cost， whatever cost here means。 And as you can see here。

 we already have a bunch of problems， right？ And of course。

 the most interesting one or the most difficult one is the fact that we just have way too many career plans。

 So if we don't want to allow Kat to show up， right？ So how do we actually deal with that？ Well。

 we need a better way to actually select the different plans out of all the ones that we could have chosen。

 And also a smarter way to navigate that whole space of three plans without actually needing to enumerate every single one of them。

 That's why we started talking about select activity， as you may recall from last week。

 The whole goal here is to be able to ask them at the size of the intermediate tables。

 Why do we want to ask them to the size of the intermediate tables？ Well。

 we want to use that because we want we need that because we would like to compute the cost of each career operator。

 which as we recall consists of now two different parts， right？

 The first part about the IOs associated with bringing any data。

 any data that we need into main memory。 And that one you guys by now should be complete experts。

 right？ I mean， because we have already covered this pre midterm one。 And like， you know。

 we already had questions about that， right？ So that's the first part。

 The second more interesting part is about this term， right？

 Which basically is something that we ignored beforehand， right？ Early， we were saying that， okay。

 for this class， for now， you can completely ignore the actual CPU cost of processing any tuples。

 All we need to care about at that point was just the cost of bringing in all these tuples。

 It's a main memory。 And then everything else you can just forget about it。 Well。

 you guys are growing up now after having gone through midterm one， right？

 So now we can actually be a little bit more sophisticated。 So now we're going to talk about， like。

 okay， well， you can't really completely ignore the CPU。

 So we're basically going to estimate in terms of figuring out the number of tuples that we need to process after we've brought everything into main memory multiplied by some CPU factor。

 So that CPU factor is basically going to be some sort of fudge factor， right？ About how much。

 how much less say， like， you know， time that it would take to process each of the tuples after they have been brought into memory。

 Does that make sense so far？ Okay， so hopefully these are all review， right？ Okay， that's great。

 But then now here comes the problem。 We only know the size of the base relations because they are stored on the disk and then we can rely on the catalog to tell us the sizes。

 But then we don't know the size of the intermediates that we would produce as a matter of each of these queries in the。

 sorry， each of the operators in the query tree。 So that's why now we need to estimate the size of the intermediates。

 such that we can plug it in into one of these formulas。 So for this class。

 we're going to say that the output size of an intermediate table is going to be the input size multiplied by some selectivity factor。

 And that's why we started talking about selectivity。 And as you may recall。

 selectivity is basically a number between zero and one。 So worst case。

 the output is exactly of the same size as the input。 Best case。

 everything gets filtered or dumped away。 So we ended up with nothing。 So that's great。 Right。

 In terms of execution， of course， right， maybe not in terms of the answer that you might want。 Oh。

 does this formula apply to joins？ Yes， right。 So in the， in the case of joins。

 then input size is basically going to be the product of the two input tables。 And then selectivity。

 in that case， it's just going to be selectivity of the joint predicates or predicates。

 if there are multiple predicates involved。 So as you recall。

 we went through a bunch of different ways to estimate selectivity。

 So there was the so-called original system， our way of doing things， which， as you recall， you know。

 has a bunch of different formulas， right。 So in the case where the predicate is of the form。

 some column equals to some number or some value， right。

 We're just going to estimate the activity by one divided by the number of unique values of that particular column。

 So if we're doing the sets， this would basically translate to probability is the probability that any one to vote that regret from an input table actually matches the particular predicate。

 So， I guess， so just as a reminder， right， so the predicate in this case。

 it's going to be something like h equals to 21， for example。

 So what are the chances that we actually hit a to go with h equals to 21。 Well。

 if we have 100 unique value unique ages in the table， then it's just one divided by 100。

 So that's how system art did it。 And then in the case where， like， you know， we。

 the predicate has to form like some column equals to some other column， maybe like， you know。

 sailors ID equals to the rating， for example， then， like， you know。

 the formula that they used is one over the maximum number of。

 the unique values in both of these columns。 And we explained in class last week about like how that came about。

 right， so I encourage you to revisit this nice if you are confused。 And then finally。

 the form of the predicate being something like column greater than or less than for the same matter。

 some number， then it's just going to be the range that we are covering divided by the entire range as the denominator plus one。

 right， because of the fact， that we want to be inclusive of both people are nappa。 Actually。

 there's a typo here so the plus one should be in the denominator， not like afterwards。 Okay。

 So we also covered the histogram method right which like， you know。

 we also went through similar formulas。 So in the case for using histograms。

 the way to estimate the selectivity of something like， you know， again， right。

 calling equals to value is going to be the height of the bar containing the value that we interested in。

 Say， like， you know， age equals to 21， right， so then we'll be looking up the bar that corresponds to that contains age of 21。

 And then divided by the number of values that actually contained within that bar。

 So if the bucket consists of 10 different ages， then， like， you know。

 we'll divide up divide up the number by 10， the number here being the height， right， of the bar。

 And then if we only have five different ages per bucket， then we just divide up by five。

 So as you recall， right， this is basically something known as uniformity assumption that we're making here。

 So as you recall， that basically means that we are assuming that all the values within the same buckets is equally likely。

 So if there are 10 different values contained inside buckets， then we just divide it by 10。

 If there are 21 of them， then we just divide by 21。 So next， right， column one equals to column two。

 we basically broke this down into a number of disjunctions or or right。

 A bunch of different or's and then we have just going to check all different possibilities。

 We're going to say what if column one equals to one particular value and column two equals to the same value。

 and then march for it right up until we run out values to test。

 And then the overall activity is just going to be like， you know， applying this formula here。 Right。

 we just go through all possible values that the two columns can possibly match。

 And then finally for the case where it's greater than a particular value。

 then we basically sum up the heights of all the bars that matches this criteria。

 and divide by the total number of rows that we have in the table。

 So if you don't remember how we derive these formulas。

 you can just look at a histogram and then kind of convince yourself that this is this is indeed the case。

 right。 So you might ask which one is actually more accurate。 Well， in many cases。

 the histogram method is going to be more accurate。

 because we're basically keeping buckets of individual values of ranges of values。

 as opposed to just assuming that everything is uniformly distributed。

 To see why I'm just take the first formula here right column equals a particular value。

 In the case of system are we're just going to broadly assume that everything is uniformly distributed。

 So therefore it's just one divided by the number of things that we have in the in the in the table versus if we have a histogram we can actually afford to be slightly more accurate by looking at the bar right that corresponds to where the value of interest lies。

 Does that make sense to people。 But you can all obviously also criticize a histogram method by saying that well there are God be even more accurate ways right because。

 for instance， the uniform assumptions really just an assumption I mean there's nothing that says within a bucket of 10 different ages。

 everything has to be uniformly distributed。 You can definitely find kind of examples that way。

 And as we were talking about last week this is indeed an area of active research that has been going on。

 And also just to put a platform sections right so please attend sections and we'll basically also show you guys how to do with cases where the columns actually contain following points。

 So far all the examples that we've been using for lecture has been assuming that the columns of our of integer values。

 So if you want to learn about what happens if we are doing the flowing point numbers and please go to section。

 But then these are not the only forms of predicates right I mean these are the basic ones so after we learn about the basic ones we can now actually derive more complicated ones in terms of figuring out their activities。

 So， you know， the values of the form of a conjunction or content needing to predicates with an end right。

 So if we have to form like your P one and P two， then we just argue that the selectivity is just going to be the selectivity of the individual predicate。

 in the case of a destruction or an or， then we say that it's going to be the addition of the two numbers subtracted by the product of them。

 And as you recall from public from your probability class the last term is basically zero if the two events are actually completely non overlapping。

 So for instance if we're asking for the case where age is great and six。

 it's great and 60 or sorry here's another type of or ages less than 21。

 then like you know the chance of both of them happening is zero so therefore the second term of the zero so we just add the two things together in terms of selectivity。

 And then finally like you know the negative version right so if I say like not P one then it's the activity it's just going to be one minus the positive one。

 So all of these basically stems from the so called independence assumption。

 So we're just assuming that all these predicates happen completely independently。

 So it's not the case that you can predict， let's say like you know people's grace right by looking at like where they live for something right。

 which is obviously not always the case right as you can imagine but then for the purpose purpose of this class and also to make our lives。

 easy and sane。 Let's just apply these assumptions to make things simple。

 Any questions so far about this。 Yeah so that's all I wanted to say for selectivity so now that we understand selectivity you can basically go and block back into the previous formulas in the previous page to figure out the sizes of the intermediate tables。

 And then figure out the cost of the individual query operators involved in a query tree。

 So so far so good， but then now we still have the problem right or figuring out how do we choose the plan of quickly find out the plan with the lowest cost right because again。

 we cannot afford to enumerate every single plan， and then cost each one of them and then。

 see like you know which one is the lowest cost right。

 So that's why we talked about this principle of optimality otherwise known as dynamic programming。

 And as Kate was saying in the chat last week right it has nothing to do with programming really and I encourage you to look up what that really means or how it actually got the right where the name actually came from。

 if you're interested。 For our purposes however the goal is to basically understand that we are making a big assumption here that the optimal career plan the one with the lowest cost consists of the lowest cost in terms of the subplants。

 So in other words， the best way to join three tables here in on the slide A B and C consists of the best plan to join A and B followed by join C。

 or the best plan to join A and C followed by joining B and so on and so forth。

 And if you need the real life analogy， think of traffic。 So let's say you want to go from Burke。

 you want to drive in Berkeley to like San Jose or something okay。

 The best way or the quickest way right to get from Berkeley to San Jose may or may not right consists of the best way to go from let's say Berkeley to Fremont。

 Right， or the quickest way right。 It might be。 It doesn't have to be right maybe you actually need to take a long route to drive down to Fremont just to get on like you know let's say to 80 or something like that and not to go down to go down south。

 So that basically means that the best or the quickest way to get like you know to San Jose does not consist of the best way to to go from like you know some place in between。

 But again， bake a something here right I mean there's no proof of this is definitely not true in the case of an increase of query it's just like in the case of traffic。

 But for our purposes this would dramatically cut down the cost of enumeration of planning enumeration。

 which is basically what we are trying to achieve here。 How does this work in system are right so。

 as I said， we will basically assume that the best plans consists of the best sub plans。

 And therefore the way that we're going to apply this principle is the first try to figure out what are the best plans of heights one。

 Or in other words， the base tables。 What is the best way to access them are we using an index。

 are we using a full table scan are we doing something else。

 And then after that after we're figured that out the next thing that we'll do is to figure out what is the best plan of heights to which consists of the base table and something else。

 And then we have joint， maybe like you know with a selection operator so on so forth if there are no joints involved。

 And we're basically going to build up the query plan tree that way。

 assuming that the best plan that we have found so far consists of the best plans with the sub operators。

 So the illustration that we were showing earlier on the Thursday lecture almost was this right。

 So we need a way to keep track of all the tables that all the best plans that we have found so far。

 So we're just basically going to keep track of them using a scratch pad table。

 So here basically I've shown you two ways of combining two different two different relations。

 In this case a joint。 So between our and as the best way that we have found so far is to use a hash join for example with a certain cost。

 And then to join the tables are and then we might actually want to use merge joint for instance。

 So again imagine just keeping track of this table right so if there are more different relations involved and we just add more entries to this scratch pad table here keeping track of the best one。

 One thing that we also talk about on Thursday right is what happens with properties that might be generated as a side effect of doing these joints。

 And one thing that we already know about now that you guys have implemented all these fancy way of doing joints is ordering right。

 So you recall that some of these joints actually generate or as a side effect as a byproducts。

 They actually sort the two posts as the outputs so therefore we might actually leverage that later on。

 Let's say in the case where the query actually involves an order button。

 But then we have a dilemma right because on the previous scratch pad query as previous scratch pad table that we have been using to store all the query plans that we have found so far。

 We actually don't record all these interesting properties at all。 So what's the solution here。 Well。

 I mean just grow the table。 So we can now add in a second column right so now you notice that there are two great columns here the first first column corresponding to the tables that involved。

 And then the second column corresponding to any so-called interesting properties or interesting order that are generated as a result of running the plan that we have on the right hand side。

 So you notice that if we run a sort merge joint between our and s then we get as a byproduct that our dot a and s dot b will be sorted。

 Maybe because of the fact that in this case the joint credit involves those two attributes。 Well。

 there's some trade off here right because now we're adding a second column so therefore we are now incurring a higher cost in terms of using this dynamic programming algorithm。

 You know we can keep track of other types of interesting orders to I mean not just ordering。

 And doing that will basically introduce yet another column。

 which basically means that we are growing the size of this scratch pad table。 Right。

 So that's the trade off。 We don't have to do like you know we don't have to keep track of the ordering for instance but then we might end up losing the chance of actually finding a plan that can do sorting for us。

 Right， because in this case for instance if I ignore order。

 then I would have killed off the second row here。 Right。

 because the first row actually has a lower cost in terms of doing the joint compared to the second one。

 So if we ended up facing an order by later on in the query will be kind of screwed right because the only way that we will do that later on is to basically explicitly sort the output relation there。

 as opposed to using this as a byproduct。 You know。

 as you know right I mean I've already bought this up later earlier right this is yet another example of this principle of what。

 There is no such thing as a free lunch。 Yeah exactly right there's no such thing as a free lunch unfortunately。

 So it's definitely a trade off。 What is the worst case here。

 The worst case here is we don't throw away any plan we just keep track of every single plan that we enumerate。

 So therefore we just ended up with the exhaustive enumeration algorithm that we had from before we're not using any dynamic programming。

 So that's the ultimate trade off。 And you try to console ourselves。 I'll just pull out a cute。

 Rainbow in the corn picture for your enjoyment while I answers。 She rose question。 Yes。

 So I was just wondering， do we only consider interesting order when there is a group by or order by trust or we actually consider interesting order like in other cases as well。

 Yeah so like you know you can definitely consider out of types of interesting orders as well right so it's not limited to ordering。

 So that's really just using that because that's something that is very explicit and also relevant to any kind of ordering right if you have an order by in the query then this is definitely going to be useful。

 Another interesting interesting property that you might consider is where the things are hashed or not right。

 So that is also a byproduct let's say of the hash join。

 So why we want that maybe there's a unique thing at the end。

 So if there's a unique clause at the end that we need to basically do duplicate illumination。

 And if we have already have everything then that makes it very easy。

 Yeah so that's another thing that you might keep track of。 Any other questions。

 Okay so let's go through an explicit example just to kind of drive home the point right so here is a query between our now famous。

 Stailers reserves and books table。 So I'm just going to put out like these different ways of actually accessing the base tables here。

 So we have B tree indexes。 We can also access things by just reading off reading off everything。

 So for the first pass in the dynamic programming algorithm as I said。

 we'll try to find out the best way to access each of these base relations。 Okay。

 so for sailors and reserves we can do a file scan we can also use one of these be trees right。

 So at this point it's boring I mean it's just basically keeping keeping track of like which is the best way to access the base table so far。

 So the best plans that we can find after like you know the first pass of the dynamic programming algorithm might look something like this。

 So we might conclude that for sailors for instance there are two ways we can do either file scan or we can also do a B tree。

 So we can do a new way to access and then like you know I'm just eliding the actual cost here right so it's just basically going to be some number。

 But notice that we are already keeping track of the interesting orders right that we can we can we can find as a result of using these different access methods。

 So for the second pass right what are we going to do。

 We're now going to enumerate different ways to doing joints because in this case I think you guys might have seen that there are actually joints involved right。

 So we're going to consider pairs of different tables that are involved and then try to do enumeration and figure out what is the best way to do the joint given any two tables。

 And I have just enumerated a bunch of these different methods that you see here on the slide。

 So for instance you can consider doing nested loop joints by considering by using reserves as the outer relation and then books as the inner relation so on so forth。

 And you can also apply your most favorite joint algorithm if you like right so like you know I'm not going to exhaustively enumerate everything here。

 But the goal is to basically only retain the cheapest one out of all of these right for any given pair。

 Unless they are able to generate interesting orders as an example。

 So in this case for instance you notice that the best way to join between the books and the reserves table is to do a sort merge joint。

 I mean obviously I'm making all these up right so there are no actual iO numbers here but let's say that's the case。

 So we， but then and then as a side effect of doing that we also have the benefit of having the joint columns actually sorted as the outputs。

 And imagine there's another road that says like you know for the books and reserve table。

 If we don't care about the sort of orders， then there's like be another best plan that we can use right maybe using that to look join or something like that。

 So that basically keeps going right so for the third pass and beyond we basically try to use the plan to the past two plans。

 And then we do those plans that involve joining two relations。

 and then like you'll do the next step figure out how to actually add in the next joint and only retain the one that is the least cost。

 And then after we have enumerated auto joint plans and figure out which one is the best。

 then we'll just add on anything that we need to do afterwards。

 And since in this case there's a group by so we need to figure out whether things are already grouped together if so then we are done。

 And if not that we need to do an explicit grouping right for instance using hash based mechanism。

 And same thing for aggregation as well。 And then finally we just choose the best plan I love everything。

 That's it。 Any questions about this example。 And we're all experts， right。

 given that you have been working on project three。

 and hopefully already finished our implementation of the optimizer that way。 So。

 just to summarize right so why would why would you actually want to understand how the optimizer works。

 Well， first of course there's a practical benefit of we can you'll be able to finish project three。

 But beyond this class right it's also because you can actually try to influence the next optimizer is that you encounter。

 People understand optimizers would also understand how to write queries to avoid generating terrible plans。

 So next time when you hear someone complaining about oh I mean I write this query and then it ended up like you're performing poorly。

 The first thing that you probably asked right is like you know what plan did it choose。

 And why did the optimizer chose the plan that it uses to execute。

 I mean and now that you understand the quirks around like all the things that the optimizer is good and not good and doing。

 You can probably try to rewrite the query right to drive the optimizer such that it will end up in the in the better plans or even the optimal plan by navigating the search space intelligently。

 So that's all I want to say for queer optimization for now。

 and then we'll actually revisit this problem of queer optimization in the context of parallel databases。

 Otherwise known as what happens if we try to run a query across multiple databases at the same time and how would that complicate the picture of queer optimization towards the end of the semester。

 And while I did see a prepare for the next set of slides I'm going to take any questions that you guys might have regarding queer optimization in general。



![](img/a35d787499b28aec4dd3ca25f0963939_3.png)

 Any questions so far。

![](img/a35d787499b28aec4dd3ca25f0963939_5.png)

 Okay， it's all yours。

![](img/a35d787499b28aec4dd3ca25f0963939_7.png)

 Halvin do you want to take Ethan's question or you want to take it。

 Sure so we have to consider all possible passes to options in the outer like yeah so。

 But then at that point we won't be breaking down the past two plans and so like the cons constituent individual relations right we'll basically be considering the output of the two way join as the as the outer。

 for example。 If that makes sense。 Yeah， so the past two plans would have already been built dynamically so we would have already。

 So that's why we use the create the cost estimation right we'll estimate the cost and the out and the sizes of the outputs from the past two plans and then use that to choose。

 which one to combine with the past three ones。 Okay， okay so let's start with announcements。

 So the first thing that you probably have already noticed is that the mid term grades are out。

 And so the median。 If you didn't notice is around 50%。 So。

 so I would say this was a hard exam it was not an easy exam but risk a hard exam and that's why the median is around 50%。

 But rest assured I mean there are like this is only one component of your grade right and so。

 And if you did badly then likely other and looks like others in the class of certain badly so it's I mean it's not it's not going to unduly influence your grade。

 So I want to sort of allay any fears around that。 And there's also the club policy that allows us to sort of pick the midterm that you did better at so that we help you get the better grade。

 Right， so， so that's I think I think we learned a lot from this midterm we will try to take all of that feedback into account for the next midterm。

 But I also want to say hey， I mean it was a it was a moderately hard midterm。

 But I think a lot of you did well so be very happy about that。

 The other thing that I wanted to say is even though this the median of the midterm was around 50% and for some of you who have not taken upper diff classes like this。

 this may come as a shock that hey you have you got just 50%。

 Turns out this is not that abnormal for 186 even last last semester for example。

 one of the two midterms the median was less than 50%。

 And I think it's pretty typical for the medians to be around this much maybe slightly higher in some cases。

 So， certainly something for us to work on and trying to make sure that we set a exam that's fair and and test the material well but。

 And if there's any feedback that you have with respect to what we can do better in terms of the midterm。

 please don't hesitate to let us know with the survey that's the purpose of the survey just let us know。

 Our goal is to not stress you out right I mean yes。

 the median was around 50% but that doesn't mean that we are we want to we want to beat you with a stick and then force you to get a feeling great right that's not our intent you want you to learn the material。

 Yes， we asked hard questions but we don't want to penalize you and you for not knowing something right so we want you to learn the stuff and and do well。

 And so if there's any way we can we can make that happen better for you let us know。 So。

 in this spirit of sort of being flexible we extended the part two deadline for project three。

 given that there were many requests for this we also added a slip day last week on Friday。

 When we realized that there were a lot of students who are still having debugging issues part one。

 On that same note we are experimenting with various office are related changes so we are trying to do our very best to ensure that your debugging questions are being answered as quickly as possible so you don't have to wait for hours on it。

 We are also trying to help students who are in other times so if you are in an Asian time zone for example。

 you log in and the queue is already very long and you don't get help。

 And so we've recognized that this is an issue and so we are trying actively to help with both these types of issues。

 Of course we are open to feedback so we are going to try various things and see if they work or not for example one of the things that we're trying is clearing the office are cues so that there's not a long backlog。

 And so we're going to try doing that。 And if you folks have any other suggestions feel free to weigh in and mid semester survey。

 So I know the mid semester survey is really long， it is very long it's been many pages but it's because you want to get very high resolution feedback from you all about various aspects of the class what's working well what's not working well so that we can really adapt to it and try to make sure that。

 we do our very best by you。 So any questions about administrative stuff。 Yeah。

 I want to echo at the T。S。 comment about like you know the fact that like some of you might be bombed by the midterm it's already about that。

 We'll also try to take that into account when we designed the next midterm and also define exam and also how we actually want to create everybody in the class。

 So look， I mean we all understand that this is a crazy semester this is a crazy time right I mean I don't understand why I'm staring at the screen right now。

 I'm looking out to a bunch of zoom windows as opposed to green you guys in person for example。

 So it's crazy equally crazy for the core staff just like it is for for all of you guys so， Yeah。

 so we just have to kind of figure out as we go because like these are issues that nobody ever has actually encountered unfortunately。

 So it's not like we have some magic bullet that can just solve all the problems and we wish we can so yeah some of these like time zone issues some of these like office hours stuff。

 We actually go through we have actually gone through extensive discussion within like the staff to try to figure out what is the best way to do this and then we still couldn't come up with the best solution。

 So the best thing that we can do at this point is to basically try different things out and then let you guys tell us which one works and which one doesn't work。

 So yeah， I mean anything is basically good on the table。

 If you guys like to put it out and we're willing to try it if there's enough support for instance。

 Yeah， so that's what I wanted to say。 Yeah。 Thanks， everyone。 I mean。

 the only thing you ever can do perhaps is just make the lectures as fun as possible and then like you know。

 making sure that you guys are actually in for a treat as opposed to all the other people who ended up like watching the play back or even not showing up right so they are basically missing out。

 I mean that's all I can tell。 Yeah， maybe we should start with some TikTok videos。 Okay。

 I actually don't want to be a bad idea if you guys want to share something maybe we can have an anonymous link for you guys to submit something and then the cop best one wins and then we'll take a big break。

 you know， in between every lecture for two minutes just to watch something fun I mean yeah。 Yeah。

 so I want to sort of also reinforce the stress point our goal is to not stress you out there's something that stressing you out let us know right I mean and and we will try out it very best to help you with that。

 Okay， okay。 Yeah， we should definitely have a thin stuff for video on TikTok for sure。

 You don't know maybe is there ready。 Maybe there is one。 Okay。 All right。

 So we are switching gears a little bit and we're going to be talking about transaction so in some sense is this topic is fairly different from the previous ones that we're talking about so in some sense it doesn't require as much background which is good so。

 if you're stressed about even more query optimization you're query optimization is a fairly involved topic right I mean there's the selectivity estimation that is the operators there's figuring out what the joint the plan tree looks like。

 And so yeah it is a little overwhelming it takes a while to get used to that so I and you're getting hands on experience building query optimizer so I think I think you'll by the end of this will be real experts at this。

 The good thing is that mean you can sort of keep that aside and focus on a new topic now so this transaction stuff is new。

 It's it's very different from the other stuff that we've been talking about so far。

 Okay so exciting news we finished our database class。 Well not quite so we finished。

 All of the stacks all the end to end database stack that we've been talking about so far right so we started with sort of sequel and we talked about this space management buffer management we talked about files and indexes。

 we talked about operators and pretty processing and optimization right so we really finished the stack。

 The downside of the stack has limited utility right can't really support multiple user accesses and it's not very reliable to failures and we talked about what types of failures I'm talking about。

 So this is the focus of today's lecture how do we support multiple users interacting with the database in a in a correct and error free and failure and failure and failure。

 a failure free manner。 So that all of that is the role of the transaction manager the transaction manager and some sense sits on the side of the database system stack and is responsible for ensuring various correctness and safety properties of your data。

 Right so and the transaction manager helps with concurrent accesses so making sure that multiple users can interact with the database and ensuring that your data is reliable。

 So it sort of stays there for the long run and there are two components here the lock manager and the logging and recovery component and lock managers helps with concurrent accesses logging and recovery helps with reliability。

 So stepping back for a little bit I mean pretty much any service that that maintains some kind of state as data today is an application that's running on some database system。

 Right so think you're right sharing apps your travel booking apps。

 although enough us are doing any of that these days。

 But that you're purchasing product purchasing apps your bank apps or even tick tock and specifically the tin stuff or videos and recording the clicks to it。

 I don't even know what the acronym is。 Sorry， I will have to remind me yeah tin stuff。 Okay。

 Yeah so recording clicks to that recording likes all of that is going to be done by some database system right so it's an application that's running on some databases。

 Okay so what do we want from the database system on behalf of these applications right so obviously we want to support single queries and updates。

 So this is the sort of stuff that you've been trying to optimize as building as you're building these internal sort of。

 query optimizers for a database right beyond that these real applications also have multiple SQL statements that are generated by user behaviors。

 Right， so for example， you want to transfer money from checking to savings。

 These are two separate SQL statements that are in some sense one unit that need to be done on the database system together。

 Also many users work on work with the application at the same time right there could be at any given time there could be millions of users and tick tock right or tens of thousands of users who are requesting rights on left。

 Right。 And so you have to deal with these accesses and do so in a manner that these individuals changes these individuals queries don't interfere with each other。

 So that's a two parts that we're going to be talking about today the first is concurrency control and concurrency control is all about ensuring correct and fast data access in the presence of many users who are concurrently accessing and modifying the data。

 And so this is done via interleap processing so it's not like as users make requests it's all done in sequence it's actually done in an interleap manner internally。

 but to a given user， you get the illusion of no interference。

 So if I'm looking up my bank account information it feels as if I'm just doing this without anyone else sort of interfering in my transaction。

 If I'm moving things from checking to savings I'm doing it without anyone else interfering with me。

 So the recovery component is about ensuring that the database is fault all right so and there are many different types of faults so this could be the level of the application it could be at the level of the database system it could be a power failure or media failure all of these are different types of failures。

 that we want our database system to be resilient to and that's a the focus of the recovery component。

 And so in some sense this is ensuring sort of some kind of guarantees storage guarantees persistence guarantees for mission critical data。

 right， and for a lot of these applications that make money off of their data。

 Their data is absolutely mission critical。 And， and fundamentally both of these types of sort of properties that we are ensuring or guarantees that we are providing is about easing the burden on the program。

 Right， so the system provides these guarantees and the guarantees in turn allowed the app developers the program is to rest a little bit more easily。

 Right， so they can be like look， I know the database system is handling this for me。

 it can handle for example multiple user accesses it can handle sort of fault tolerance and reliability。

 So it handles all of this for me so me as an app developer I don't need to worry about this when I'm developing my app。

 So that's kind of really extremely powerful from a usability standpoint。

 So why do we want to enable concurrent execution and there are actually two separate sort of reasons for that。

 So far from concurrent execution standpoint it's about ensuring multiple queries that are run concurrently in a system。

 And like I said there are two types of advantages the first advantage is to do with throughput。

 So this is measured as queries per second。 And so overall we want to increase the utilization of both the processors as well as discs。

 And so for example if you are on a single core machine。

 most of us are not but if you are on a single core machine one query could do some computation via the CPU while another is reading to or writing from the disk。

 So you can do a multi core machine which is much more common these days。

 you would want to scale the throughput scale the number of queries that you're processing in the number of processors processors rather than processing the queries sequentially。

 Right， so you want to be able to do things in parallel。 Okay。

 so that's one thing that we want increase throughput。 The other thing that we want is lower latency。

 Right， so this is basically measured as the response time per query。

 And by ensuring that multiple queries can run at the same time you basically ensure that you're not waiting on any given query to finish before you can start executing your query。

 Right， so one query's latency is not， may not be dependent on an other unrelated queries finishing before it can start processing。

 Right， so like with queries， for example， may not be。

 may not be bottlenecked by more time consuming queries。 Right， say for example。

 I was just looking up my bank account。 This could happen in parallel with a more expensive query that's generating a report of the total amount of money saved across all accounts。

 Right， or at least that would be the hook。 Right， so you want by doing things in parallel。

 doing things concurrently you have the ability of reducing the latency and increasing the throughput。

 So these are both very powerful advantages。 So both of these are important。

 So let's start by talking about why managing concurrent accesses is important。

 So let's take an example where I'm trying to move my budget from the advertising category or the marketing category to inventory and sales。

 Okay， so I could do this via these three sequel queries。

 I subtracted some money from the advertising category。

 I added it to the inventory category added to the inventory category and then 300 to the salaries category。

 Okay。 And so let's say I want to run this query on the site so another application。

 Another client is requesting this query to be run。 Now。

 if this query is done before or after the sequence of queries， then we are good， right。

 because money is conserved。 You get the correct picture of the budget。 Right。 However。

 if you run it in between here or here， then you get an incorrect picture because you are mid flight。

 right， you moved subtracted money from the advertising part。

 but you've not added it to the inventory of the salaries part。 So if you。

 if this query executes somewhere in the middle of the sequence of operations。

 you're going to get an incorrect response。 So in the， in these cases， the money is not conserved。

 So that's not ideal。 So there are two issues that emerge here。

 The first issue is that the order in which these operations happen and they are interleaved matters for correctness。

 Okay。 And the second issue that emerge emerges is that users need to sort of provide a specification of what success acceptable from an application standpoint。

 Right。 For example， can the right hand side query view the budget in between these update statements。

 right， where in the budget is not the total money is not conserved。 So。

 so these are the two issues that we need to solve via the notion of transactions。 Okay， whoops。

 All right。 I lost。 Stop sharing my screen。 Give me a second。 Okay， so let's stop。

 Talk about the various problems that could happen。 So the。

 the previous one may have been an issue of semantics。

 But now we can talk about more serious problems that emerge if we don't have someone。

 the system mediating these concurrent accesses。 So let's start。

 start by talking about the first problem。 So here you have a user。

 and this user is basically taking all of the products from within this product relation。

 And those that have a price less than or equal to 0。99。

 They're inserting it into this dollar products relations of having a separate relation for all the products with a price less than $1。

 And subsequently they're deleting these products from the original product relation。

 So they basically in some sense move the products from their original place in the product relation to this new relation called dollar products。

 Now， like our previous example， let's say there's another user who is issuing two queries one is count star from product。

 and then count star from dollar products。 So， if this issue。

 this user's queries are executed such that one of them is executed before the start of user wants queries。

 And the other one is executed after the end of the second query that user want executed。

 And then user to is going to have read data that is inconsistent right internally。

 the data that is being read by these two queries is not consistent with each other。

 And so in this particular instance products are double counted。 Right。

 so it's counted both in the original product。 So， this is an instant of instance of an inconsistent read right a read that's inconsistent because if you've read the same information twice you're getting two different results。

 So that's not good from a semantic standpoint。 So， let's talk about a different type of problem。

 Right， so here I have a user one that is updating cool toy type of product by reducing the price of cool toy by 10。

 I don't。 Okay， and so user to at the other hand is increasing the price of or also decreasing the price of cool toy by multiplying it by point six。

 Now， what if both of these users read the price and then proceeded to make that changes independently。

 Right， so both of them read the original price。 So P one， and then。

 and then user one did made that change and user to make that change separately。

 One of these changes would be recorded in the database system， while the other changes lost。

 because both of them ended up reading the same value of price。 Right。

 So this is a case where one of these updates is lost rather than a correct execution of these queries where you might want user wants change to be complete and then user to change to be applied。

 or user to change to be applied first。 And then user wants change to be applied。 Right。

 So in this particular instance， one of these two updates is lost。

 So this is an example of a lost update。 Right。 So one of these two users。

 their query executes correctly， but they're， but their changes are not reflected on the database。

 Here's yet another type of problem。 Right。 So let's say I made a typo in my user one made a typo in their update statement。

 where they basically said， Hey， I'm going to set my account information by changing my amount。

 the amount that is stored in my account。 And changing it to $10 million。 Right。

 User to looks at that same account， and then sees this $10 million。

 and then proceeds to go ahead and make a bunch of purchases。 Right。 They're like， wait。

 there's $10 million in this account。 Now I can go buy my million dollar home。 I can buy a yacht。

 I can purchase a small island。 So I can do all of this。

 because I saw this information in user ones update。 However。

 user one realizes that that's not what they actually intended。 And they aborted that query。 Right。

 So it's either aborted by the system or bought it by the user。 And so。

 user to ended up using an information that was actually not reflected in the database。

 It was a data that was quote unquote dirty。 Right。 It was a。

 and this problem that people refer to here is called a dirty read。 So user to user to square。

 he ended up performing a dirty read of data that's not actually persistent in the database。 Okay。

 So these are all sort of potential problems that can arise if you have incorrect interlebenes of different users。

 accesses and changes to the database。 Any questions about this so far。 Okay。

 So let's talk about the notion of transactions。 Right。

 So transactions are a solution to the problem that we've outlined earlier。

 So there are two aspects to the transaction。 One is the user facing concept。

 So how does the user think about a transaction， as well as a set of system implementation techniques。

 So how does our database system provide this notion of a transaction to users。

 And so transactions are a tremendously important component of database systems and are critical for most applications。

 If your date， if your application is ever planning to use， have more than one user。

 then you better have a notion of transaction support。 So as an aside。

 there have been multiple Turing awards for database systems over the years。

 And I want to point out that one of these awards to Jim Gray。

 so the four awardees are Charles Buckman， Edgar Card， Ted Card。 Jim Gray。

 as well as Mike Stonebreaker。 Right。 And Mike Stonebreaker famously spent a lot of his career and did a lot of his influential contributions at Berkeley。

 So Jim Gray won a Turing Award。 He was， if I remember correctly。

 he was the first PhD student from ECS at Berkeley。

 And so Jim Gray won the Turing Award for transaction processing。

 So this is such an important topic that is one of four Turing awards。

 that have been given in database systems。 So what's the notion of a transaction？ Right。

 So a transaction is a sequence of multiple actions that are specified by a user that are meant to be executed as an atomic unit。

 So it's meant to be executed in some sense， all of it on non-effect。

 And either all of the effects of a transaction， all of these actions。

 their effects have to be reflected on the database on non-effect has to be reflected on the database。

 not halfway。 So the application view or as to how you would express this in SQL would be you would use some sort of break begin transaction statement。

 You would issue a bunch of SQL queries and then you would say end transaction and that's when you that's the end of a transaction。

 Right。 So this is a unit。 It's executed as an atomic unit on your database。

 That's a guarantee that database systems provide。 So an example here would be if you're transferring money between accounts like the example that we saw earlier。

 those two queries where you're deleting from one adding to another would be executed together as one unit。

 Added the begin transaction and transaction blurbs before and after the queries。 Likewise。

 we wanted to book a flight hotel and car together and Expedia again this would be begin transaction book。

 book flight book hotel book car and transaction。 Right。

 So all of these things are grouped together as an atomic unit。 So。

 what's a transaction model that we're going to be working with so a transaction often abbreviated as TXN or X Act。

 So if you see either one of these abbreviations know it to mean transaction。 So a transaction。

 the way that we are going to be viewing the notion of transaction is via an abstract view of what the program is trying to do or the activity that the program is trying to accomplish。

 And this is going to be viewed as a sequence of reads and writes of various types of database objects。

 This could mean pages， tuples， relations， but we're not going to worry about that as much。

 We're going to be thinking more about the conceptual independence。 So。

 it's going to be a bunch of region rights。 And then this batch of work， right。 So this unit of work。

 which is basically a sequence of updates， either reads or writes that that entire batch of work must either commit。

 which means it must complete， or it must be aborted， right。

 or in which case it's effects are not reflected on the database。 This is all done as an atomic unit。

 A transaction manager， the component that we saw earlier in the sort of stack。

 control the execution of transactions。 The program logic。

 the application logic is invisible to a database system。 And in fact， the。

 you could have arbitrary computation that's performed。

 The database system and the transaction manager in particular is only going to be seeing changes at the level of these reads and writes。

 Okay。 So it's only going to see things at the level of these reads and writes and it's going to use these reads and writes to determine how to interleave various types of queries or transactions together。

 So as an example here， if I have this transaction that's trying to transfer $100 from R to S。

 and I have this sequence of operations in my application。

 Some start transaction statement read our subtract 100 from our right， read S， add 100 to S。

 write S， and then in transaction。 These changes， these specific changes are not seen by the database transaction manager。

 All of the transaction manager sees at the reads and writes。

 These changes could very well be happening within application logic。 Right。

 So all of the transaction manager sees is， Hey， are you reading something or are you writing something。

 Right。 So that is what it sees。 The semantics of the changes are not seen by the transaction manager。

 So transactions provide several guarantees。 Right。

 So the guarantees that transactions provide are the so called asset guarantees。

 So these are guarantees of properties that are fairly high level properties that these that transaction notion supports。

 And so， asset is is a mnemonic。 So it stands for atomicity， consistency， isolation and durability。

 The notion about Thomas city and we'll talk about each of these in sequence and we'll delve into each of them with examples。

 The notion of atomicity basically says， either all of the actions in a transaction happen。

 or none of them happen。 So a transaction is an atomic unit。 Consistency basically says。

 if the database starts off in a consistent way， then at the end of the transaction。

 it also is consistent。 So if it obeys some properties。

 the start of the transaction at the end of the transaction and obey those same properties。 Right。

 And we'll talk about what those properties will look like later。 Isolation basically says。

 I can imagine each transaction to be executed effectively in an isolated way from others。

 So the execution of each transaction is isolated from others。

 There's no interference from other transactions for the execution of a given transaction。

 The durability property says， if a transaction commits， then it's effects persist。

 That means that I know if a transaction commits， then it's going to stay in the database。

 It's effects are going to be reflected in the database。 So。

 they're going to each of these properties in sequence and we'll go in a different order。 So。

 we'll start with isolation。 So isolation is all about concurrency。

 So it's about the first of the two aspects parts that a transaction manager supports。

 So the isolation property basically says， a database system interleaves the actions of many different transactions and these actions could mean reads or writes of various types of database objects。

 The database system will ensure that two transactions don't interfere。 Right。

 So it's each transaction executes as if it is run by itself。

 So it is isolated from other transactions。 So concurrent accesses have no effect on a transaction behavior。

 So a transaction can execute without worrying about having to think about synchronization with others。

 So， we have an application standpoint that's a nice powerful guarantee， right。

 this guarantee of isolation。 And so the net effect of all of this。

 this isolation guarantee is that it's sort of is like executing these transactions in some serial order。

 right。 So that is that effectively the kind of guarantee that is provided。

 If you ensure that each transaction executes as if it ran by itself。

 And then the thing that we're going to do is we're going to do this again is that users and programmers have provided this guarantee and they don't need to worry about interference。

 Right。 They don't need to think about interference from other transaction。

 They can think about transactions in isolation。 So， concurrency， of course。

 introduces some challenges， right。 And this is what we need to develop solutions to handle as part of our transactions mechanisms。

 So， for example， if you have this transaction T one that is subtracting money from all and writing it into S。

 and you have another transaction T two that's reading both R and S and taking their some。

 If T two executed in between the rights of our and the rights of S。

 it's going to end up seeing a low value for our plus S than if it was executed before or after T one。

 Before after T one， right。 So either before T one starts or after T one finishes。 So in this case。

 if T two executes on my here， he to see state in between T one's changes。 Instead。

 we wanted to run either before T one entirely or after T one entirely。

 So isolation is easy to achieve by executing one transaction at a time。 Right。

 But we don't want serial execution。 Right。 Serial execution is not desirable because it's slow。

 It's， it's not making good use of resources。 Right。

 So we want to interleave transactions while also providing the guarantee of isolation。 Okay。

 So let's treat the two more properties， atomicity and durability together。 Right。

 So a transaction ends in one of two ways。 It either commits or it aborts。

 So commit basically means that a transaction has finished processing。

 So you issue a commit when you've completed all of the actions of a transaction。

 So commit is kind of a contract between an application and the database saying that the changes that the transaction made need to be reflected on the database in a persistent manner。

 right in perpetuity。 So that's what you get if you say commit。

 That means that I'm done with my transaction。 I want you to ensure that those changes are reflected in the database。

 And abort is can be requested either by the application or the transaction itself could be avoided by the database。

 So the database management system after having executed some actions。 Right。

 So the abort could happen after you halfway through a transaction， you could say， Hey。

 I want to abort between said you want none of that transactions effects to be reflected on the database。

 A system crash is also equivalent。 If a system if the database system crashes。 If you lose power。

 This is treated as an abort。 If a transaction is in progress。

 treated as an abort and you want to undo the effects of that transaction。

 almost as if the transaction never took place。 So the two key properties that we want for a transaction that we're talking about now are atomicity and durability。

 So the atom city property basically says， either execute all of the actions of the transaction。

 which means the transaction is committed on， none of them。

 which means the transaction has been abort。 The durability guarantee basically says that if a transaction has been committed。

 then it must survive failures。 Right。 So it must be reflected in the database。

 It must be persistent。 Right。 It must be there in perpetuity。

 So database system ensures both these properties， atomicity and durability property by logging actions。

 So it。 Then a performs undo and redo to ensure correctness。

 It undo the actions of aborted of failed transactions to remove their effects。

 And then redo is the actions of committed transactions that have not yet been propagated to disk when the system crashes。

 Okay， so undo and redo。 These are the two actions that we will be taking on on the log to ensure that we provide the durability guarantees and atomicity guarantees。

 So as an example here， I have my familiar transaction。

 which read R and then subtracted some money and then added it to S。

 If a transaction field is the transaction field here。

 This is a case where money will be lost right you're left with an inconsistent database。 Right。

 So you deducted money from all but you've not added to S。

 The database system will need to ensure that the updates of this transaction。

 which is partially executed are not reflected in the long term。

 The durability property basically says that， hey， if the user hears that the transaction has been is complete。

 it's being committed， then they know that 100 in this case hundred million or hundred dollars were indeed correctly transferred from our。

 transaction。 Right， so it has been transferred。 They don't need to worry about that change being undone。

 If the transaction has been committed， it's when it's complete。

 The last property of the asset is the consistency property and this is a little bit more indirect。

 I'm not going to be focusing on it as much as the other properties。

 but it's still worthy of descriptions。 We are dealing with acid。

 The consistency property basically says that transactions preserve database system consistency。

 And so if you have a consistent state in your database。

 then the effects of a transaction would produce another consistent database state。 Basically。

 it moves the database from one consistent state to another consistent state。

 And so consistency usually is expressed in the form of constraints。

 Various forms of declarative constraints。 These are high level constraints that that provide some form of integrity。

 We've already seen examples of these types of constraints。

 the primary key constraint or a foreign key constraint。

 These are all examples of referential integrity constraints。 We could also have type constraints。

 So this is another example of a constraint。 There are other types of constraints that we didn't cover in this class。

 but constraints that cover assertions or sort of invariants that you want the databases to obey。

 Transactions that violate integrity。 These integrity constraints are aborted。

 So the database management system ensures that only transactions that don't take the database to an inconsistent state are allowed to proceed。

 Okay， so we've seen an overview of the transaction concept。

 Transactions provide the notion of asset guarantees that essentially improve performance by a more concurrent interactions and really programmers of worrying about correctness concerns。

 So you sort of hide the concurrency， the sort of interactions across transactions as well as handling failures。

 There are two issues that we're going to be covering as part of these lectures。

 The one is concurrency control by two phase locking and recovery via logging。

 Right ahead logging specifically。 Okay， let's talk about concurrency control first。

 but if there are questions， I'm happy to take them。 Shiro。 Yeah， so from a。

 like a application developer perspective， usually this transaction is given by the database as an interface that they will be using。

 like directly or is that something， some other way of form。

 So like how do they get access to the fashion。 Yeah。

 so precisely right so the way an application developer would use a would call a database would be to start a transaction perform some updates and then end the transaction。

 So that would be the sort of like way applications interact with the database to ensure that if for example。

 their change involves many different sequel queries， then you're treating that as a example。 Right。

 so you don't want， for example， money to disappear when you're doing a transfer。 Right。

 so usually like say， say， if there is a bad database that doesn't implement the transaction。

 then there's going to be like no access to the transaction at all。 Right。

 So most database systems support transactions。 So。

 are you talking about different applications that have different。

 so I'm not sure I follow your question。 I'm not， I'm just like thinking this all over say if there's a bad database that like the person who implemented the database。

 Or like just like too lazy to implement the transaction。 Yes。

 so I mean you need to have the transaction concept to be able to use it right so a lot of no sequel systems。

 the new family big data systems。 A lot of them don't support the notion of transactions， right。

 and they only support the notion of， let's say， individual key value inserts to be atomic。 Right。

 so they don't provide any other guarantees beyond that。 What does that mean？ Well。

 if I have a multi step insert， so I have to insert this， I want to insert that。

 I want to insert that and I want to delete here。 So if it's a more complex program。

 the application programmer has to deal with all of that baggage， right。

 they need to deal with the factor that could be many different applications。

 many different users that are accessing the database at the same time。

 And they would have to add controls as part of the application logic to make sure that there's nothing funky going on in that data。

 Right， there's no corruption。 There's no violation of consistency。

 All of that will have to that's a burden that the application developer would have to bear in this context。

 That makes sense。 Thank you。 Okay。 Any other questions？ If not， we can move to concurrency control。

 All right， so let's talk about concurrency control。 Okay。

 so the goal of concurrency control is to provide the illusion to a transaction that it's the only one running on a database。

 It's providing the guarantee of isolation。 One way of providing concurrency control is to simply do serial execution。

 Right， so there's no concurrency at all。 Each transaction runs one at a time。 This is safe。

 but it's slow。 So you want the execution to be interleaved for better performance。

 And to figure out how to do that in a principal manner。

 we need to define a notion of correctness and ensure it。 Right。

 so what types of interleavings are allowed if we want to provide this isolation guarantee。

 So let's formalize the notion of concurrency control。 We'll begin by talking about schedules。

 And these actions include a begin transaction， read something， write something， commit or abort。

 Right。 So one representation for a schedule could be a tabular representation。

 where each column refers to a transaction。 So this is T1。 This is T2。

 And you have the the the the actions for each of these transactions listed as rows。

 So in this tabular representation， there is a single action on any given row。 Okay。

 so because it's meant to be read from top to bottom。

 So there's also a string representation where you basically line it in a linear way。

 So you hear you would say R1A means a transaction one red A transaction on the road A and so on。

 Okay。 So in the string representation by convention。

 we only include the committed transactions and omit the beginning and commit statements that you might find in the tabular representation。

 So to reason about correctness in the face of interleaving， we need to provide a starting point。

 So what do we know is correct？ A serial schedule is correct by definition。 Right。

 So basically each transaction runs from start to finish without any other interleaving actions from other transactions。

 So in this example， you have all of T1 stuff first before all of T2。 Right。

 So this is a complete isolation。 Next， we'll talk about the notion of equivalence。

 So two schedules are deemed to be equivalent。 If they involve the same transactions。

 each individual transactions are ordered in the same way。 So within a transaction。

 they are ordered in the same way。 And both schedules leave the database in the same final state。

 Right。 So both transactions have the same。 Sorry， both schedules have the same eventual impact on the database。

 Okay。 So if these three properties hold， then these schedules are deemed to be equivalent。

 So to continue with our notion of correctness， we know that a serial schedule is correct because it provides complete isolation。

 So a schedule is deemed to be serializable if it's equivalent to some serial schedule。

 And so basically， if you have this schedule， which has interleaving between T1 and T2， this。

 if it is equivalent to a serial schedule where T1 is before T2 or T2 is before T1。

 then we say that this schedule is serializable。 Okay。 Any questions about this notion？

 So let's take an example。 Right。 So let's have， let's say I have this serial schedule。

 And with T1 transferring $100 from A to B and T2 adding 10% interest to both A and B。

 So if I have a serial schedule with T1 and then you have T2。

 basically the final outcome is A is equal to 1。1。 So you add a 10% interest times A minus 100。

 Right。 So you do the subtraction and adding first before you do the multiplication。 And B is 1。

1 times B plus 100。 Right。 So this is the final outcome in the serial schedule。

 This is another serial schedule in which， oops， in which T2 happens before T1。 And in this case。

 the final outcome is A is 1。1 of the original A minus 100 and B is 1。1 of the original B plus 100。

 This is a different schedule。 Right。 It is a different schedule， a different serial schedule。

 but still understandable from a user standpoint， both of these make sense。

 Now let's talk about schedule three。 So this is a schedule where the actions of T1 and T2 are in the lead。

 This is not a serial schedule， but it's because it's not true that all of T1's actions are before all of T2's actions。

 all of T2's actions are put T1's actions。 But in this particular case。

 this is equivalent to schedule one。 It leaves the database in the same state。

 And therefore it is serializable。 And to see this。

 note that T1 does its processing on A and then T2 does its processing on A。

 And so things are correctly sequenced in a way that guarantees the same final result。

 So this is a serializable schedule。 Okay， so now as a means of enforcing serializability or checking serializability。

 it's often tricky to check this property of leaving the database in the same state。

 How do you actually ensure that？ That's actually not easy。

 So we need an easier test to check if a schedule leaves the database in the same final state as a serial schedule。

 And so what we're going to end up using is a more conservative test。 So this has no false positives。

 but has some false negatives。 So in certain cases， it will conservatively say， Hey。

 this is not okay， even though it is okay。 So it'll sacrifice some concurrency for an easier correctness check。

 So what is this this equivalence test going to rely on？

 It's going to rely on the notion of conflicting operations。 Right。

 So operations where one of the operations read and the other is the right。 Or both are rights。

 Right。 So basically operations that conflict with each other。 So two operations conflict。

 If they are from different transactions， they are on the same object and at least one of them is a right。

 So what is the scenario where these operations conflict with each other。

 So I'd like to encourage you folks to think about this and justify to yourself。

 The order of non conflicting operations should actually have no effect on the final state of the database。

 So if you have two reads， for example， it doesn't matter in which what order you did them， right。

 because it's just two reads。 On the other hand， if it's a right and a read or a right and a right。

 it does matter what， especially to the same object。

 It does matter in what order you've done those two。

 So that's why we're going to be focusing our attention on the order of conflicting operations。 Okay。

 so I will stop here since we are。 At the end of lecture， I'm happy to take questions。

 I will continue with the notion of conflict， serializability in the next lecture。 Well， yeah。



![](img/a35d787499b28aec4dd3ca25f0963939_9.png)