# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p15 -15-S2024 #14 - Query Optimizer Implementation 2 .zh_en -BV1HZ421N7WZ_p15-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/04a0e5d2919dbb25558fcbb02a1ed9f5_1.png)

🎼。🎼あ。Right actually I have one of the chips in my office for some reason they took me on a boat on Hawaii and they're like here's a burnt out chip from a spark that has you know oracle compression built inside of it I'm like okay。

 I have it， I don't know what to do with it anyway sorry enough。We go forever， right。



![](img/04a0e5d2919dbb25558fcbb02a1ed9f5_3.png)

Daatabases query optimization All right， so last class， we didn't get through everything。

 we'll go over this again again， I'll go a bit slower than maybe did last time just walk through what cascades is doing and then we'll finish up with randomized search before we jump into what today's paper is about。

 But again the things we discussed last class was going through this progression of how to do more sophisticated things with the query optimizers are starting from just if N else rules looking for patterns that then do some kind of rewrites which is which everyone uses when they first start out and then we saw how system are in the 1970s。

 introduce this costbased join search and that sort of the backbone of how the strified search and unified search came along and then randomized search will be。

😊，It's a variation of this so the distinction week we were talking about last time was again the stratified search and the unified search and as I was saying。

 the lines are kind of blurry were like okay cascades in SQle server is technically a unified search。

 but the way they invoke some of the rules the transformation rules as I'll see in a second。

 it's basically doing it without a costbased search like they're doing transformation that you always want to do first。

 and then they do something that is more exploratory search you see in cascades and so the thing that maybe matters the most is that we want to be able to define the transformation rules ideally in the same dialect or DSL。

 whatever you want to call it， they allow us to then be able to decide do I want to move stuff to be always in this front phase that I always want to run or the second phase we to do more exploration stuff。

😊，So the stratified search is having two separate phases， one with just heuristics。

 sorry one using the rules， but without a cost model the second one is doing cost base search and then the unified search is the idea is that you just do everything all at once and to avoid a bunch of expensive transformations or getting stuck in infinite loops。

 we saw again how the memo table is going to help with that。

So less so about maybe the stratified search versus unified search。

 the thing that really matters when we understand is the distinction be top down versus bottom up。😡。

RightSo the cascades approach is top down， meaning I start with the outcome that I want like this is the final output I want for my query。

 I don't know how I got there in my query plan， but I'm going to go down the tree and assemble the pieces or assemble the output I need to then feed me into to my final output。

😡，Whereas in the bottom optimization， which is what the systemR guys started with is that you start with nothing and you then add the operators you need to get you up to the goal that you want and again me standing up here and making hand gestures like this and this maybe doesn't really sink in and mean anything but there are certain optimization you can apply more easily in one versus another at a high level they are composable they're commative that you could use one versus another but there are some optimizations you can do in top down one that maybe you can't do in bottom up and likewise in bottom you can't do in top down Yes stratified always bottom up now his question is stratified always bottom up this is what I'm saying is cascades as described by Microsoft。

Is that stratified because they have a bunch of rules that you always run。

 then later on they run the cost base search and in that cost base search it's doing top down。But。

 the transformation rules are sort of。Sort of operating them sort the same way。

 They're generating these like logical plans at a top down man or two。

 but that that would be technically that that's a stratified search because you have something you always do。

 and then you have a call space thing that can be dynamic about。Right。

So most of the open source systems are going to be bottoms up。

 Even the guy that invented cascades said the way to。

The way you probably want to do career optimization now is start with cascades in sort of stratified manner。

 like run some initial rules， maybe not necessarily in the full cost based search。

 it wasn't clear it's this sort of offhand come made at a conference and then you want to do the bottoms up optimization to pick join ordering。

All right， so take in today's class， I just want to spend the first half going over again what we missed and rushed through at the end of the last class of the Unified search and Cascades。

 and then we'll see how we can then apply that randomized search and then I want to go quickly over some real world examples of what what close source and open source query optimizes actually look like。

 the main it's going be SQL over Calalcite OrCA and cockachDB。

And then we'll finish up with going over at a high level again the the un nestesting subquery paper you guys were under reading。

 Hopefully that wasn't too too dense on the racial algebra， but it's a。

It's one of the things where I think everyone should know it。

 we probably should teach it in the intro class， very few systems actually implement it entirely as far as they know onlyductDB  Ubra and Hy。

 my former student who took 721， she's at Databricks。

 she implemented almost all of it in databricks and but not everything but we'll walk through an example there。

 and unfortunately sake of time we're not going to be able to cover how Hyper does their。

So dynamic program approach or DP approach for finding join orders。

 but we can cover that offline if you want separately。Alright， so again。

 this is just to repeat what we talk about last class。

 where the cascades optimizers is gonna be the third version or third generation of a query optimizer。

 This guy Gertz graphy built Exodus came first then volcano。

 and it's the same volcano when we described the volcano model。

 this iterator thing in that system in papers， he also describes how to do parallel queries with exchange operator。

 and then he has this optimizer generator that he built the volcano。 And then after that。

 he then built cascades。 But as far as they know， he just wrote the paper in cascades。

 It's very heavy handed on object oriented programming because that was the hot thing in late 80s。

 early 90s。 And then as far as they know， nobody he didn't actually implement it except for being involved in this masters thesis a few years later at Portland State。

 But then Microsoft hired him to go build their new query optimizer because they were rewriting everything from their fork of ciase And that's why again Microsoft famously is using using cascades。

😊，So it's going a top down approach using a branch bound search and sort of the key idea。😊。

What makes cascades interesting and better than what came before was that they were doing the incremental materialization of the possible ways to represent some expression。

 which I'll say as a second， some operator in the query plan。

 whereas an volcano when you search down， you landed at some node in the tree。

 you immediately materialize everything which would explode your search base。

 even though you may run out of time to examine everything at that operator at that level of the tree。

 you still materialize everything， and so the memory cost of volcano would explode。

So the four key ideas of cascades as we talk about less class， again。

 everything is going to be represented as data structures， so within a task wed have。

 here's the pattern I'm looking for in my query plan， here's the transformation I want to apply。

 and you can have additional things like a priority that says this thing should be considered more quickly or sooner than another one。

And in the paper， you can actually modify these priorities on the fly， but in practice， again。

 I don't Karashibi does it， Microsoft does not。Then we have explicit definition of these。

 what properties we need our operators to have to ensure that if data needs to be sorted a certain way or data needs to come in a certain compressed form。

 we can make sure that any operator we would generate in a query plan at some level in the tree meets the expectations of anything below us in the tree meets the expectation of the parent we're feeding into。

And then we talked about this and you can reorder things on the fly to find the best pan more quickly based on what you know the query plan is done so far。

 and then this last one again， it's important that within the same search engine and the rule definitions we can do pattern matching and transformations of expressions and wear clauses having clauses or joint clauses。

 whatever， in the same way that we would search for converting logical operators to physical operators。

And this is nice gig again you don't have to do like one pass for the wear call is optimize that then a separate pass for the query plans themselves。

 all that's done in a single engine。Like I think my SQL。

 they treat the expressions and the wear clauses separately from the query operators。

 so they have sort of two optimization passes。All right so things the definition we care about in CaSKA is this notion of an expression。

 and it's just going to be some operation that we want to do in our query plan that is going to have zero or more inputs coming into us。

 it could be a leaf in the query plan or it could be some middle operator。😡。

RightAnd we can sort of group them together， say， here's here's a higher level thing that we want to do。

 and we'll represent that as an expression。 So， for example， if I want to join A。

 B and C on simple Ids， I could have a logical expression that says I'm going to join A with B。

 then join that with C。😊，And then if I flip the order。

 then that's considered another expression as well。

And then I can have a physical manifestation of that expression by actually specifying here's the scan method I'm going to use or X method I'm going to use for that given table。

 and here's the join algorithm I want to use。😊，AndThen now I'm going to combine or group these together the equivalent expressions based on what we know as the relation to algebra rules into what is called a group。

 and the idea is here's that within one container or construct or entry in our system in our query optimizer。

 we would say here's the output that I expect A join B join C。

 then here's all the equivalent logical expressions， permutations of the joint order。

 and then here's all the equivalent physical expressions。

 so within one entry in our system we could say here's everything here's all the different possible ways we could actually execute。

 produce the output we would need for a single group。So the entire thing itself is the group。

 and then these are all just the equivalent expressions。

 and they also embed additional information about like here's the properties that I need to have coming into the data that I want here。

So then we can combine expressions even further into what's called a multi expressionpression。

 and this is just basically a placeholder that says there's some expression below me in the query plan。

 and at this point at this group in my search tree， I don't actually know what it is。😡，Right。

 but I'm just gonna keep track of like， I know something below me can tell me how this thing would actually be executed。

 So， for example， if I need to join A， B and C， I could have a a multi expression that says。

I'm going to join A and B， I don't know how and I don't know in what order。

 but then I'm going to join whatever the output of that is with C。😡。

And then you have the various combinations of the joint order and so forth， and likewise。

 the various combinations for what algorithm we're going to use to join it。Right。

So if it's a bottoms up approach， you're basically starting with like the smallest atomic multi expression you could have like go read A right and then you go add the pieces or the components to that going up toward the optimizer the final output in this case because we're at the top going top down we start with this multi expression says I want some output of A join B join C。

And then I'm going down and then filling in specifications or the exact details of how to do that。

Again， this is how they're going to get away with not having to materialize everything all at once when you land say in a group as you search down the tree。

 because now you say I have a placeholder for A and B。

 someone below me is going to tell me how to handle that。

 but right now I can just reason about whatever expressions I'm looking at within my group directly。

And then likewise， you can make further decisions based on those priorities as we talked about。

 like if I'm， if I'm。Trying to get center， should I go look at what A happens when I join A and B。

 should I go when I scan C， you can decide dynamically as you're going down the tree。

 which of these paths you want to look at first。So this we've already defined again the rules are just ways to convert logical operators to logical operators or logical to physical。

 and in the end the database system needs physical operators because that tells you what the system is actually going to do when it executes things。

And then within a rule， we wouldd say， here's the pattern that I want to match on。

either in the logical special or a physical special。

 and then here's the transformation I want to do to put the query plan that I'm looking at or the group that I'm looking at into a new form。

So this is the example we saw before， I have my pattern to identify when I have two joins across three groups。

 and then I would have say a logical plan that looks like this。

 and note here again I have the mal expression that says I'm joining A and B。

 but then down below me nowuncesing join A with B， and then below that I can specify how I'm accessing the data。

😊，So I could have a transformation rule that says this rotate it left to right。

 or I could have an implementation rule that says convert all the equijoins that I have in here into a ser join or hash join or an essay loop join and so forth。

Right。And as we said before， to avoid having to get stuck in infinite loops because I could go like left to right and right the left and Im just doing this transformation and over again。

 we're going to use a memo table to keep track of have I。

Do I know something about what the outcome of this transformation will be。

 and therefore I don't need to apply it because I've already seen it。😡。

So rather than than doing that on every individual rule for every single possible state of the query plan。

 my memo table is just can keep track of like， okay， I know that for this multi expressionpression。

 I have a cost for it and I don't need to go look at what happens when I make that transformation if that transformations cost is going be the cost in the query plan after that transformation is worse than the best I've seen I don't need to go look at it。

So as you said the memo table again， the different way to implement this。

 I think Microsoft puts this as actually inside the groups themselves。

 I think cockroach G maintains this as a separate hash table。

 but it's basically again some table that's going to keep track of for a given given a multi expression。

 here's the best。😊，The best physical operator I've seen for it and here's its lowest cost。

Youll also keep track of like the properties that I care about。

 whether the data is coming up with this operator for giving multi expression with again。

 what physical properties and I can know that if I'm looking at something differently。

 even though I'm looking at a different，MIf I'm looking at a different operator me in the group。

 if it has a different physical property， I can then maybe still evaluate and go further。

 and you would do these things like if the best cost I've seen so far is a sequential scan。

 but I know that for the given group that I'm at， I really want data to be sorted now because that'll change my cost expectations。

 then if the multigroup below me does not enforce that property or provide that property。

 I could still go down and look look for other things。😊。

So the basic idea how this is going to work not to it too theoretical radical is this idea of the principle of optimality and all it says is that if we have what is the true optimal plan。

 then any subplan of that optimal plan is going to be optimal。It's sort of theology。

 sort of like self definingfin like if I have the optimal plan。

 then any portion of of that query plan is going to be optimal because if it wasn't optimal。

 then that wouldn't be the optimal plan。So because of that。

 this is how we're gonna be able to do branch and bound search to identify that if the。

If I'm at some level in my search tree， if the cost to traverse down to my query plan as I go below is now worse than the best plan I've ever seen so far。

 then I know I don't need to go down and look further because there's no magic way that that cost is now going to go become less because as you go down the level。

 you're adding more physical operators， you're accumulating more cost estimates and that's this a sum。

 so you're not magically going to get faster。😡，So we just cut things off and avoid having to search further。

So this is the example that we have before before again， we want to join AB and C。

 So at the very beginning， we just start at the root and we apply logical transformations to generate different logical multiexpressions。

 and then say rather than materializing a bunch of all the logical multi expressionpressions。

 What is jump down to the first one we have and see what the cost is。 So now we come down here。

 do the same thing。 We have the multi expressionpression A B。

 We do a logical transformation to convert it into a multi expressionpression on A。

 joined by multi expressionpression on B。 But now we need to get the cost of these。😊。

These inner multi expressions。 So we go down here。 and this is doing the access on a。

 There's nothing other than just get a。 There's there's no other logical multi expressionpress。

 So then will materialize the different physical multi expressionpressions。

 So either sequential scan on a or index scan on a for brevity I'm not showing you like okay。

 what index I'm actually using， but you can imagine for all my possible choices of indexes you would have additional would have multiple or for each index I could use an index scan on a table。

 I would have an entry for each of those。And then again。

 you can do ranking in priority lists and say， well。

Only consider the indexes that rank the order in which I value the indexes in my bulk expansion list here based on the selectivity of them or which ones cover the most columns that I need in my query。

 there's a bunch of different rules you can do to figure out I'm just blindly looking at all possible indexes。

All right， so now that we have these two different physical multi expressionpressions。

 we do some cost model look up and say， okay， well the squal scan is going to be the fastest。

 has the cost of 10， so we add the multi expressionpression on a into our me table and with the best physical expression we've gotten for with the cost of 10。

😊，Then we go back up at the tree， do the same thing down on a B， same thing。

 we convert that to physical multiexpressions， we end up with an sequentialial scan and next down on a B。

 sequentialial scan is' still faster， we get a call of 20。

 and then now we bounce back up to our multipression on AB。

We do further transformations to now flip the order of the joints， now B is joining A。

But now we need again to do the same thing and get what is the cost of actually accessing these different tables。

 Well， when we go down to these lower nodes here， we will see that we've already done this costing for us because it's in our memo table So we actually don't even do the do traversal。

 can at this point here， we can just go look up the memo table and say what is the best cost for scanning B and scanning A。

And then we reuse that。So now again， say it's only A join and B and B join A。

 so now we generate all the physical multi expressionions and then again using our cost model。

 we then figure out that the hash joint is the fastest。

 so the cost of the hash join plus the cost of the scans on A and B produces the cost of 80 and that goes at our memo table。

And then we bounce back up now go to on the other side of C and do the same evaluation。

 yada ya out and so forth until we then maybe exhaust the search for the different join orders we have for A B and C。

 and we end up with the lowest cost of 125。So it is clear。So this is what Cascade is doing。

 again you you're starting with in this case here。 I'm going to join A， B and C。

 not specifying the order， not specifying how I'm actually accessing the tables。

 not specifying what the join algorithm I'm going to use。

 And I traverse down and use the memo table to keep track of the best cost I have。 Yes。

 so this is cost base。 But you said there were a few rules that tries to apply every single。😊，Yes。

 so how would that。work So would it first build a table and then or would it do it somehow before So like like the。

Like what I showed here， like， okay， I have get a。 and then I take the logical multi expression and convert it to physical multi expression Like the rule could be like you would say if I land here。

 I know I'm accessing the logical expression on a scan or accessing a table So let me always run the transformation rule。

 implementation rule that spits out different physical multi expressions。 sequential No， no no。

 what I'm saying is that you always generate the multi expression that are sequential scan and all possible index scans on a that always gets fired。

 then you do a cost based search to say selection， which one of these is the best。 Now。

 whether or not you materialize all possible physical multi expressions depends on the complexity of whatever it is that you're doing because that might balloon up be huge like the joiner up above。

😊，So you could have a ranking say to previously， I think I should look at these join orders first。

Yes， what was the difference between this and volcano Volcano was exhaust question。

 what's the difference between this in volcano。The difference is that when you land in， say。

At the very， very beginning， so back up here。I generate all the logical multi expressions and all the。

 the physical multi expressions。And again， it seems kind of obvious that you wouldn't want to do that。

 but I don't know if it was the 80s and 90s， right？Theyvolcano didn't have priorities。

 volcano also didn't have。I don't think you could evaluate the wear expressions in the same method as well。

All right， question this。In later slide。When you pop with physical expressions， you still have。A。

Like these are logical groups， right？You mean this right here？Right like the his question。

This is not like a physical。There's no physical， it's saying like， and。

 we need to be joined together。こタチプ。Yeah， it great to saying I want to join A and C together。

 but here， you're not defining how to do it。 You then go look up the memo table and say。

 what's the best way for me to have done that。Yeah。Whathy do we say we are applying the rules？

Before if you're doing it while we're doing all the cost estimation。

 so this is still entirely unified right there isn't a set of things that you're doing before。

You're doing this entire thing altogether， where you're applying these transformations。

 also estimating the cost， picking the best one and then going back up。 So， yeah。

 so his question is like。Yeah why？How can I say that you could use cascades to do a two stage approach。

 So like， think of like the。When you first show up， you convert the AST from the par SQL query into。

😡，you have like a group like this， I know I'm going to access A。

So you can start populating those things。Right， and then without。

I don't know how Microsoft actually does it， whether they can。You know。

Inject themselves at any point of the tree and start doing transformations。

 or they always start the top and go down， but there's like。You could say。

 I'm going to traverse the tree and only apply these rules。😡。

To put me into a form that when I do a cost based search。

 I'm kind of pushed in the direction where I know is going to be a better plan。

And the second was building on Oconno's question， which is you said in volcano。

 it won't do everything exhaustive， but in the diagram we've made like four different I put dot dot dot right。

 like whether it's PowerPoint， like whether or not it looks at all of them。It is exhaustive。 No， no。

 because So again， we， we talked about the determination rules。 It could be a timer。

 It could be like how many transformations I've done。 It could be like。

 I haven't seen nothing better。 Well don't have I mean， they all had some kind of timer。But again。

 whether or not you would。Again， materialize all possible things。😡。

IHa of time before eating look at him，  Volcano did not do that。

There's other object or programming and stuff which， again， we don't care about。

I was going to asked what data is like on limits to make these estimations with like， for example。

Like when you like page information， like the something like the aggregate information for a page。

 that allows you know if you're going to skip it or not。

Maxine and stuff and you're doing like scans over stuff like for the cost。That's next week， right。

 that comes later， but like you would。In a traditional database system。

 meaning like you have statistics you've collected by running analyze or whatever you would。

You the cost model would tell you what the selectivity of you know。

 a little level operator like this wouldn't be， like how many data。

 how much data I think I'm going to read。You， if it's just a straight s scan versus like an index scan。

 this is all data that you have to have collected a。

 you're never going to touch the data when you're creating them。Like this。

When you touch the data because it's a difference between running there's only certain things you can know after you run the query obviously but like this analytics comes from either previous runs or estimations correct。

 statement like these causal estimates as I'm describing here are done mating using summarizations or sketches or whatever you will call it of the data that you either derive from previous runs or your own own analysis。

I would also throw a third category and you'll see on Monday next week is sometimes there's just a sample of data that's local and you could run like run the where on on that sample data just to see what the SM is going to be right SQL ever does that but like。

All that is it abstracted away from this part through the cost model。Yes。

Why might one want to prefer？Do join watering bottom up。This question。

 why do you want to do bottom up versus top down？Yeah， so good question。

 so there's some weird things like。You may not be able to do the。

Do all the branch of bounding stuff that we want to do because I got to get to the bottom first。

 meaning like， I can't say， okay， well。I'm at this point here， and I know that。

OrMaybe maybe I'm farther up the tree。 Like think of like doing a lot of joints。 Like。

 so I'm up here and。I can't do any pruning of the search tree below me until something gets at the bottom and produces what I think is the best possible plan。

😡，So you always have to generate the full plan。 Then you can start pruning other things。

 And then sometimes like you can't。 you do have to do the materialization of the logical to physical because。

I don't know。 I can't do cost estimates or I can't get the。

 can't get the lower bound if it's if's just a logical expression。

 I got to convert it to the a physical operator to know what are the true cost is going be。

 There's some tricks you can play around like like doing estimates of like you know。

 working getting scenario things。But in the if you're going bottom to the top， like along each step。

 I have a physical operator and I can cost things right there。😡。

It's better because starting from the bottom。In some way it gives you more options and it also allows you to materialize physical as you go。

Ma is what physical。There's other optimizations you can do。

 which we don't have time to cover from the hyper guideides of grouping things together in hypergraphs and just costing those things separately from other pieces where this looks at everything all at once。

Am。Yeah， I I can。It's like 2006 paper， it's in the reading list。

 I might mention I don't have time to cover it， but they show that in practice they find the optimalna faster thanjo ordering faster than cascades。

Even know Microsoft has put a ton of effort money into it，Yes。

 the question is how how does like the data properties come come into play in any of this would be like say that say that I've picked here。

 I'm going to merge join， say so not a sort merge on a merge join。

 So I assume that my inputs have to be sorted。 So as I traverse down。

 then I could say don't give me anything that that's not sorted。

RightAnd then I could record that actually in my memo table to say， okay， for the scan on B。

 here's the lowest cost with these set of properties and here's the lowest cost for this other set of properties so then I can decide。

 if I need those properties， I can check the memo table to see whether that operator is providing enforcement me。

Yeah， the mammo table， I'm not showing here because it's the PowerPoint。

 but you would keep track of what properties， a given multi expression and the best expression for it provides。

 and then you can decide whether that's going to give you what you need or not。

What are some other types of properties other than sort？So what is the most common one。

 you could say compression。😊，I'm not showing like。We we're not showing projections， obviously here。

 but like I need these columns， stuff like that。 And then that can change based on it like a column store or a row store because row store could always shove it up at a column store。

 if it's like disaggregated across different nodes， it becomes more complicated ask because。

Would you have to store every single？Some set of properties for every single combination of tables。

The question， would you have to sort， So if you just think you're like sorting this obvious want to deal with。

 right， is this one if you like， no， like be sorting me like sort of on what column。Oh yeah， that。

 Yeah。 So you， you got to keep track of like， I'm accessing this this data and it's coming into me。

 It's going to be sort in this column。 or I can then do a transformation to say， all right。

 well I'm looking at a merge joint here。 Therefore， I need my data sorted。

 So you would then have a transformation rule can then say， okay。😊。

Populate the thing below me to make sure I'm looking at things being sorted or not。

Or you can pass hints down and say， okay， I， at this point here， maybe I don't。

 I don't want things sorted。 So don't know considerate。

 So is this me table generated at the beginning of everything or is it like。Sorry。Are there。

 let's say maybe combinations of tables that we may want to exclude from the memo table at the very beginning？

Especially is are there combinations of tables we may want to exclude from the memo table in the beginning？

Like for example， like if I want to sort on。If I have a table with a five column。

 I only want to start one column Yeah， so Microsoft does this。

 Microsoft will prepopulate the memo table in this first stage。

And then sort of seed it with things that it knows it you should probably consider first。

 and then that way when you do this search， you may prefer things that I already know about。Yeah。Yes。

 building on his question。Can I say that we all we need to do bottom up if you want to do adaptivity。

 I know we're know not that it' probably next week's topic， but like if you want to adapt。

 you will definitely do bottom up This question is if you want to do adaptivity。

 you have to do bottles up adaptivity when。Like while thequaery is running。Why。

 why would you have to do it you have to go bottoms up because if your bottoms up。

 you start with like a sequential scan and then you can。

Or you want to switch to an index scan that's your adapt aspect of it right in that case if you're doing it bottom up。

 wouldn it be likely more easy to control what's happening as opposed to having to go explore。

All the way from the dock。His statement is， if you want to be adaptive。

 it would be easier to do bottoms up versus tops down is your point because look we're overriding example。

At some point you say， oh， like maybe index exam is good。Let's pun this next week。

 Let's see how they do it。 the g a way you do one purchase we'll see the do adapt for  query execution is you just inject a new physical operator。

 Oh， see that's We don't want do that Why is that bad Because if you're injecting it。

 you're continuously adding more costs。😊，Injecting another operator in the middle of this。

 you're adding cost to what goes above， right？这个通ル。And know。The physical operator is like a。

I don't want use the word Sentinel， it's basically a gate that checks is the data coming out what I expected it to look like。

And then if not， you then make a decision。It's like a trigger。In the query plan。

 it has no substantial cost to the query plan because it literally is like。

 is my selectivity what I think it's going to be， what I thought it was？

Is that really applicable about it？Yeah， that's next class， that's Monday， yes， he's jumping ahead。

But to your point， like it depends on the implementation like you could。

Like whether or not you inject the activity pieces。

 why you're doing this like generating the query plan or like you just say I got my physical plan。

 you embed now in the operators， your cost estimates， cardal estimates， and then you say。

 okay well here's my leaf node scan， I'll now inject that trigger check。😡，Right above it。

 And if I see that the data coming out doesn't match what was in my scam below me。

 then I don't do something else， but you don't need to do that potentially for the call space search。

You can imagine a scenario we say。You could include in your cost estimates to say。

This is going to be more expensive to do， but I'll add this trigger check to make sure that I don't this be this can be really expensive to do。

If I。If I get it wrong， so let me add my trigger check to make sure I that I don't get it wrong and then choose the thing that's more expensive。

 So you can like do play games like that。 Let， let's pun on that until next week。

Most of the systems that do adapt will be simple。Pushdowns of certain operations。

 So snow snowflake will push down an aggregation to a remote node above， know。

 above a joint or something like that。 If it see certain things， other other triggers would be like。

 this is， this query plan is just terrible。 stop。Throw everything away and go back query appizer。

 And then the other ones can be more， more clever about like switching plans on the fly。

 But nobody does that in practice as far as I know， they'll do like simple movements now。Okay。

 other question。So there's a bunch of im of cascades， again， cascades is the name of the paper。

 as far as they know there was no implementation of it。

 likevolcano far as I know there was a system and code based called volcano that people were using。

The actual implications that were out there in the early 90s was this thing called plus plus out of Wisconsin I think Jgnesssh's office mate worked on this when he was Wisconsin because he did his PhD there and then Portland State was with the Columbia Columbia system again that was Gers Grray was involved with that Gers Grray's Ph advisor was also Jgnesh's Ph advisor like this guy David Dewit who invented in a lot early parallel Shi Davis stuff。

诶。Green Plum built this thing called OrCO， which we'll cover in a second that actually。

 know that's sort of like calcite， where's like a standalone optimizer as a service similar to what we're trying to do for optD。

 and then here's a bunch of the other ones that are implemented in actual full systems。

So let's come back to Cscades。Other invitation， let me go actually hold up。 Yeah。

 let me do more cascades before we go to。Randomized algorithms。All right， so the SQL server。

 So the cascades paper is like 94。 the Microsoft hires good G to start building this in SQL server in like 95。

😊，There is a single codebase there was a single codebase for the cascades optimizer。

 but my understanding from talking Microsoft is like they forked it many。

 many times and basically all the major database products that Microsoft cells on premmin in the cloud like whatever synapse we' cover later。

 cosmos DB， they're all using scope is in the one， they're all using some derivation of the original cascades optimizer。

 everything's written in C+ loss， there's no DSL， and then to do transformations of the warehouse expressions。

 all that is just doing if then else clauses and not rules running in the search engine。

So as you said before what their Ca case is going to do is that they're going to have separate stages that are going to find。

 here's the rules I actually want to consider at each stage and the idea is that you start the ones that you know you always want to run you almost always want to run predi get push down maybe always want to run like one equals two convert to false and things like that and then so you always do these transformations at the very beginning and then at some point you get to this point where you think I want to do the cost based search and that you can tweak and specify here's the priority for some of these transformations based on what I saw in the earlier stages that I evaluate。

So in the very， very beginning， you just do basic simplification and normalization。

 so this will be doing logical tree to logical tree transformations。

 so the subquery stuff we'll talk about in a second。

 they have their own rules to do that outer joins， inner joins predict get pushed down and then empty result pruning like select star from table where false you can throw those things out。

😊，They you get to what they call pre-explation， and this is doing not the actual cost base search。

 but this is applying rules to populate the memo table with things you think we want to look at as you go down。

😡，Because the idea again， you don't want to blindly search in the beginning。

 you can see the memo table with like， here's the things that are going to be interesting and guide the search towards those。

So trivia plan shortcut select1 or select star from table limit zero， things like that。

Projection normalization， how to identify the stats。

 sorry projection normalization again cleaning up what's in the select output。

 They do an interesting thing where they identify at this point here that they don't have all the stats they would need in their cost model to give good estimates they actually stop stop the query planning。

 go tell the system to go over run analyze now， collect the data that it's actually missing imagine the very beginning you bulkload the table。

 you need something。 and then when that's available。

 then they can come back and start doing some initial cardnet estimates and then join collapsing when possible。

Then they get to the costbased search and this can instills me multistage where they're going to have sort the first group of transformations that they're allowed to consider and then over time as the number of transformations that they' that they've applied because that's how they're keeping track of how long the search engine are going but then expand the set of transformations that looking at to do more complicated things so in the very beginning it's for dealing things like trivial plans like lookups on a single table where there's primary key index and stuff like that and then if you still don't find the optimal plan then you expand that out to a quick estimation on how to a parallel parallel plan again now you may be looking at joining multiple tables it's more than looking up single tuple and then if there's still more time in the clock as you go along。

 then you can open up to do a larger search for the full plan。And then in the last eight step。

 and this is still within the cascade optimizer rules for all the different database engines or systems that they're trying to run support through cascades。

 they would then have engine specific transformations that they can apply so for example I think for synapse is like the distributed data warehouse based on SQL server we'll cover the end of the semester like you want to do distributed joins or broadcast joins and so forth like all those things get applied separately in this last stage here because that's building upon the plan you built up so far Yes for this costbased searchization and the pre exploration phase。

sure I understand how you're going to decide how to。

I assume you miss the memo table you operate to help guide your search。

 like how do you really need predict is it based on your analysis？

His question is how do you pre populate the memo table to see the search ahead of time so like it would be be populating the memo table but also populating like the groups you've sort of generated right say for this multi expressionion on this this。

say joining three tables， if I know something in these early stages about like。

 I always want to have this be the outer table in the inner table。

 so I'll see that transformation ahead of time。And then if I had the estimate at this point。

 getting past this step here， then I could put that cost in the me table right away。

So as I said before， the， the timeouts are always be based on the number of transformations。

 not the wall clock time。 and then。What's nice about this as they bring up is that。As I said。

 no matter what hardware you're running on， you could， you could still。

 you can always generate the same query plan， given the same the database。

 And then if the system gets overloaded because again， in this environment， it's not a。

You knowIn traditional sequenceQs server， it's like a single system where like the optimizer runs in the same box and the same hardware as the execution engine。

 so if the system gets overloaded， then the time it takes to actually optimize the query。

 it's going to take longer because the threads are burning up。

 running queries or doing whatever and so。If you base it on wall clock。

 if I run the query today and it's the system that overloaded， I run the same query tomorrow。

 I may get a different plan if it's overloaded if I'm looking at wall clock time because just everything was so much slower。

 so this guarantees that no matter what I I always get the best plan or the same plan。

And then as we said before， you want to pre populate the memo table with useful join orderings。

 again， this is just your rules， rules to make sure that things land sorry that you seeding the search in a way that you find the best the best join earlier。

 and as this is very similar much of the oracle one the order that they appear in the Sequel query is the order that that'll get seeed into the memo table。

Which sometimes makes sense， which Oracle did for a long time。Al right， calcci and orca。

 I don't want talk too much about， but this， I think everyone here is is aware of them。 right。

 These are separate。These are standalone query optimize optimize as a service。

 Calalcite is way more is used way more than Orca。 It written in Java So that limits how many who actually want to use this。

 but the。😊，It's。Calsize energy be because I think they have their own they have connections to be able to run queries and things like that。

 like it's more than just the query optimizer， but most of are for the SQL parser and then the query optimizer。

 but you basically have to define it comes with much of existing rules。

 But if you want to then extend it to whatever system you want to support。

 you can then define through their Java code， here's the rules I want to transform things。

 here's how to do cost model estimates and so forth。😊。

So this originally came out of a Uhiin system called LucidDB， this went under。

 and then I think it was a startup and then they took the pieces out of this and that became calcite。

AndAgain it these are a lot of systems。Green pump is the equivalent to calcite。

 but maybe the less it's the less。诶。Plugable focus or like with calite， you say you can have like。

 here's my snowflake dialect。 Here's my post dialect。

 It supports a bunch of different dialects going in and bunch。

 I think a bunch of different dialects going out。 Orca is is more focused on new pure query opposition。

 So this is originally written at。😊，I keep track of。

 I lose track of who bought what Green P got bought by E C。 E C got bought by。Deo。Or VMware。

And then VMware。Now EM Greenplump got by EM C。 then VMware bought another company called pivotal。

 and so EMC had a database products， and then VMware had database products。

 and they didn't know what to do with them。 So they merged the two they spun out those two divisions of these two companies。

 and then they form pivotal。 and then pivotal eventually got bought back by VMware。

 Jacknesh was that there for a while because his startup grab bought by them。 anyway。

 So they were supporting Greenpl， which is still is us today is widely used。

 It's a fork of Postgres like distributed run that queries。 And then they had this thing called Hawk。

 which is their version and the hive， which is sQel top Hadoop。

 But then rather building a separate of query optimize for hawk and query optimize for Greenpl。

 They decided， let's build a single optimizer as the service。

 and support both Hawk and Greenpllum and whatever says me want to hook up to it。😊。

Hk is still around and nobody actually uses it Greenplump still around。

 And so that's the primary user of work。 But it's like Calalcite where again you have this API or you have to implement。

 here's here's what my catalog looks like。 Here's what my logical plans and physical plans could look like Here's the rules I want you to support and you plug out it in and you can use it We looked at this almost 10 years ago to use it and system we were building and the time they had like zero documentation was like you send a bunch of XMl files and it would spit things out we decided not pursue it。

 but it still it's actually maintained it， but again I don't think it's anywhere outside of Greenpl。

 Calalc more common。So there's a paper that they wrote on Orca and they talk about a couple interesting things think that are relevant for some of the discussions you've had maybe this is of an issue if you're running you're not running less of an issue if you're running on the cloud because you control the machine。

 you control everything， you can see everything。 but at the time for onprem this was tricky。

 So if someone's running your software their hardware。

 if you're optimizer crashes or produces a bad query plan。

 how do you actually then try to debug that and improve things So if someone sends us port ticket and say。

 hey， my query went slow。😊，You know you don't they can give you the SQL query。

 but if you don't have the right environment if you don't have the right data and you don't know what choices the optimizer made one was doing the search。

 it's hard to debug this。 So they had the ability to have the optimizer spit out a complete state of its search for a given query and then send that back to the home base for the developers to then almost like walk through exactly。

 here's all the decisions that the optimizers made when it generated the query plan they can use that to figure out why it made certain choices over another。

Again， if you're running in the cloud。You control everything you can figure things out and you dont do this。

 but now interesting thing me to do is make sure that the cost model estimates are accurate。

 they would do this thing where they would run take a SQL query。

 run it through the optimizer and they would keep track of the best plan and the second best plan or maybe the top 10 best plans and would and then in the background they would run all of them。

And then see that the relative ordering of what the aas model thought was the best plans actually matches up with reality。

 when you actually run the queries， and they would use that then to tweak things and improve things。

 Yes's the would。😊，Yes， but like。But Monga didn't have like is is Mongodb doesn't didn't have a cost model。

 It literally was just like， here they are， run them and then whatever they come back， right。

 This is trying to see whether your cost model is predicting the right， you know。

 physical costs and they they adjusted of itself。Right。So yes， at a high level。

 it's the same as Mongo， but Mongo is not trying to verify whether the cost model estimates are correct。

 they're just running it。Again， I should go double check this is still what Mongo does today。

I guess you'll find out。It looks like that they might be trying to do stuff actual。ok ，自。

And when I when I talk to them before the pandemic， they didn't have like。

 They didn't have like any logical physical operators， which is like。

Here's the Json stuff panic it right Co G rewrote wrote from scratch their query optimizer。

 there's like everyone else， they started with something that was based on heuristics and then they wrote one that based on cascades。

 everything's written and go they're more pure to the cascades modeled they maybe Microsoft was because they would have a DSL that the specify here's the rules and the transformations and in some cases where you can't do the transformation entirely through their DSL。

😊，You could escape into go code so here's basically what their rules sort of look like right so you have like the matching that you want at this DSL and then other things you may want to apply and then this then gets trans pileed into go that then run into the system。

Alright， mean， we're out of time again。Let me rush through randomize really quick because again。

 this exists， Postgres does this。So rather than doing top down or bottom up。

 what do you if you just did a random walk。 So you got to start with some some query plan。

 and that one， you can just straight conversion of of the AST phological plan into physical plan and just permeute that。

 But the idea is that you you。Look at a bunch of different possible query plans。

Pick where everyone has the best cost。Keep track of that。

Throw away the ones that are the lowest costs， do some kind of randomization and a permutation on it to then change things and then do another round and check a live again So you're sort of randomly walking to try to see whether you stumble upon the best query plan。

So there's an early paper in 1987 that does this with simulated and kneeling again。

 the idea is that you just swapping operators and the join ordering of two tables randomly if the plan makes it worse。

 then you flip flip away to coin and see whether you should keep pursuing down that path otherwise you flip it back Now there's a bunch of rules。

 you got to right to make sure that you don't do things like' a left outer join where you have to care about one being joined before the other。

 you don't put things in the wrong order， so you have to check to see whether the random change is actually still a correct plan。

 but then if it doesn't get violated， then you can flip things around right。Nobody does this。

What people what Postcodes does do is uses a genetic algorithm。

 I think this was introduced in the mid 2000s。 So there going to use a genetic algorithm where they're going to have these different generations of the different query plans。

 Can you pick which one is the best， throw away the ones that are worst。

 then promotemute the best ones to try to。trying to find the traits or the genes of the query plans that make it a good query plan and then hope that you sort of stumble upon the best one。

So Postsg does this， but you only get it when you have you give it a query that has more than 12 tables that you're trying to join in a single query。

There's a flag you specify by what that cutoff is， but by default。

 you don't get this unless it's a 13 way joint or higher。So it looks like this。

 say we have some random query， we have a bunch of random combinations of join orders and join algorithms。

 you pick first you cost all of them。😊，Keep track of the one with the lowest cost up in the corner which keep track of the best one I've ever seen。

 throw away the one that has the worst cost and then permute some portion of the query plans are the ones you keep around and then the next generation you populate those。

😊，Do the same thing。 Check which one has the lowest cost。 This one does。

 So that's not near our best cost。 throw away one， throw away the the weakest one。

 the weakest of this generation， permute them and then and so forth。 right， Yes。

 these costs are estimated， These estimated costs。 Why would you realized。

I like theyll pick these random queries and then run each random one and then pick the best is like。

 this is all within the query optimizeizer only Mongo does that like runs everyone this is like using the Comod as supposed'll talk about next week in this case。

How does it come with the first generation The question is how do you come with the first generation。

 it's random。Even the first generation the first generation development， after that。

 it's specifically picking things that could。So I know I had to join RS&T。

So it lead different joint owners， different physical operators，Try it out。

So I know in the case of Postgrets， they make sure that the random permutationations is deterministic because you don't want to be。

 if you throw the same query at it again， you want to end up and you're using running this and you want to end up with the same permutation。

 right？嗯。Yes， this seems like a good idea。 seems like a good idea。

 Why is it not used It's a good idea because if you have 13 joints like like that's a lot of them。

 So going from a randomite rather than you know， approaching it from like。😊。

They almost exhausted a the tree top down view or bottom of one is just too slow and you're unlikely to get the right joint for every single one of them。

So if you go from a random， you' have to hire。Is that not true。

 I I just bit pullinging in around on this side？From a first inition。

 it seems like this should work right there's an engineering cost to making sure that you don't permit things incorrectly right so now you're maintaining code to do that and that's again。

 that's pretty much ifN else rules for very， very large tables a large number of tables。You know。

 the。A greedy search p would be better。Again thing of like joining 30 tables， 40 tables。Yeah。

 doing randomized seems so much better for that because you stop from around because there's so many possibilities。

So。Yeah， so this is a talk from the guy that actually works on this on the app from Postgs a few years ago。

 he basically said that the one in Postgres lease is broken。

 it's not truly randomized as much as it should be。

 or I don't think they're not incorporating the traits that that are best from one drainage and the next。

I think that。I don't say it's a hack， but I think that the。

you don't have time to cover the hybrid one。 The hybrid one is the better way to do this if you。

They have basically an adaptive algorithm that can figure out like if above a certain number of joins。

 a greedy based search is actually better。We cover this in the reading group， we can cover it again。

 I'll mention that next class。I don't have slides work。So again， nobody actually does this。All right。

 with 20 minutes ago， I have any question before we switch over to the paper reading。

As said' question about the randomization， do they randomly like because like s degrees are highly structured。

 do they randomly make the choices from the top down to generate like just a random？

And do they do it over the logical plan first？Insert the physical components were。

His question is like how are you populating this， so you have a logical plan？嗯。

And then you could just use。The order and the tables， they appear in the SQL query。 that's the order。

 that's your initial ordering。 And then like you're just flipping things around。

 But but plan already has like structure。 So getting electrical like not truly random。

 even though like you have like a different equiological plan。

You could get something completely different than might have better red right you， you。

HisStavid is like the logical plan has some structure， yes， and again。

 depending on if it's an inner join， those things are comm， you can swap them anywhere。

 but like if it's an outer join or one of these correlated subqueries like that you got to be careful about so you got to make sure you don't violate that。

But like if things are commutative， then。You can take the logical plan that say，Jo R on S and T。

Like you'll have that tree other and you just commute that。It's the random of walk。😔。

Yeah I see you're going like one， you're choosing one thing to。No， in the very beginning。

 it is like you have to generate this first generation's。Like all these changes like just one team。

So what do you mean all the like all these changes are like just changing one part of the tree， yeah。

 they're changing the entire thing every single time correct， yes， because the idea is that like。

Like in this case here， I somehow figured out this hash showing on the hash showing where s followed by R or S as the outer r is the inner。

 you don't know whether that's the y made this one the best so you want to carry that over to the next one in this case up here that and then you promote maybe other things about it so that if it truly is the reason why your costs are lower then that trait will get carried over time。

Okay。So let's see how far we can get through。So queries， okay。Okay， this me surprise everyone。

 subqueries are important in SQL。 It's wild。 you can put them anywhere in your SQL query。

 I wasn't able to I tried to last night。 I wasn't able to get it into a NA query into my order by clause no proco so that you put in the order by clause。

 but I don't think it actually does anything I was trying to have it return a string thats the name of the table Why I want to look up and it runs it。

 but I think it just getting converted to true so you you can put a order by clause in the select statement I' sorry in the order you can put a select statement inside the order by clause in some cases。

 but I don't think it actually works。😊，RightAnd the way to think of a nest query or subquery is that it's basically like a function that has some outer query I'm going tovoke into it and maybe pass in some information or not about what the outer query is the two I'm looking at on the outer query。

 and then I'm going to produce some result that I can then use for my out query and this is important because this allows people to write more expensive things in a single SQL query rather than have to run multiple queries。

 stage it and temp tables or whatever。😊，And then put it all together at the end。

So there's this key distinction that's going to matter a lot between uncor and correlated soques and the TLDR is that uncorrelated ones are easy。

 most data systems will be able to handle those， it's the correlated ones that are going to cause problems。

😊，The unrelated ones basically means that whatever my subquery is doesn't depend on anything on the outer query。

 meaning I'm not using any information or any attributes。

 any tuple data from the outer query to run that inner query。

 So I only need to logically execute this inner query once。

 whether or not the data system is smart enough to do that depends on the implementation。

 but the ones we will look at， we can talk about will handle this。😡，Right so in this example here。

 I want to get the all the students that have find me the student the name of the student that has the highest grade in some class or across all the students。

 So this inner query on the select max score from students doesn't rely on anything from theer outer query on students so I can run this once。

 materialize result and and and be able to substitute that in for every tool I'm looking at on the outer query again。

 I think for most systems that they should be able to handle all cases for this。😊，Actually。

 that's not true。 There are some cases where they can't。They can't hit on thecor sub grids。

 The basic idea what you're trying to do is basically you want to move this up and get this to be joined up above。

Yes。Which one？Yeah， this， it does not。 Thank you。 Yes， it will fix。Allright again。

 correlated subries is the ones we care about， again。

 this is where the inner query the subquery is going to reference something in the outer query here。

 so now if we do modify a query to say give me all the students that have the highest grade in their major across all the students in the same major。

 then the basic idea is that for this I'm going to have a four loop that's going to be the going over every single tuple in the outer query。

😊，And then for each of those tus， I need to do a complete sequential scan or scan on the the the inner table。

 the inner subqueries results。So let's say if I start my outer query。

 the first one I'll look at is with the first table were Ja in these major computer science。😊。

So then now when I invoke the inner query， I'm going to scan through and then now do that join where I take the Adderqueries major。

😡，Match it against the innerqueries major and then get the max score。

 so I'm going to run this entirely and produce a max score of 90。

And I'm going to then populate this as my output result here。Next for the next one。

 againIS also on Compci， do the same thing， start from beginning scanned again。

 get max score 90 that doesn't match what the RIS score is RIS score so therefore that does not produce the output for ODB。

 he's the only one majoring streets， so again start beginning to scan through。

 it matches producing my output like that。Right。So what I just showed here is like the worst thing you could possibly do because for every single tuple in the ater table。

 I'm rerunning that join query over again in the inner table。Yes， is this to happening？We个厉害。Yeah。

 his question is like， can you have this inner query in a where clauseuse given and anywhere？

I can have it as a from clause， I can have it the projection output。I reference to the audit。Correct。

 yes。I can put again， you can have it in limits， you can have it in can necessary queryries in limits。

Actually， don't if I't if you can reference to the a query。

 I't if you you can have correlated sub queries in limit causes the having can do it like anywhere。

You can't have correlated one in f either， right saying in f， how could it be later joint？

It's basic same。Alright， so the paper you guys read we'll get see how they do it in a second。

 The goal is begin to basically， we want to lift up。

 this inner query to be at the same level of the outer query because then we can then convert it into a join。

 and we know how to run those officially。 We know how to optimize those。

 And then we know how to give what we talked about last two classes。

 We know how to pick the best join order for these things as well。 So for this query here。 Ily。

 we want to move the we want to move the inner query to be now be in the join clause and the from clause against the the outer query here。

 And now we got to be mindful that。😊，Yes， we need the score of the students that should not be S2 give it a that sorry but now we want to group by major because that's how we're going to do our joindown here because we want to see is for my。

 what's the best score for my outer twoal？Car major， and is it my score？Right。So for this example。

 yeah， we can look at this and can say， okay， we could write something reasonably。

Easily to do this kind of manipulation you know they're saying since these nest queries can appear anywhere and in this case here it's a straight quality predicate。

 you can imagine like equals any exists less than greater than antijos。

 semijo like you can have all different kind of combinations and it's very difficult to write the rules to capture everything。

😊，But this is what basically people have been doing for the last 30 years。 Yes。

 quick question in the paper。Specify join like they don't actually use a join keyword。

 I that just a different syn The question is in the paper。

 don't they don't specify join they're equivalent Mo S standard says shows you use join， but like。

 yeah， you could just have this be。You comma， and then it's just a wear clause。From， from the。

That's that normalization step that I talked about in。In in like SQL server， like。

 they'll figure out what's in the where clauses and move what's in the where clause that should be part of the join and move that to be part of the join clause。

But they're quite of that。All right， so again， for the last。

I think the first paper on N queries is like 83，84。

 I think the SQL standard ended it I think is SQL99。

 but since then people will writing much of rules to handle all puzzle these different combinations that they're aware of right so this is from the SQL server paper from 2001 that roughly defines the rules that they apply。

 I'm not going to be through all of them but this is how they decide what to when they can derelate nest queries in SQL Ser look at the documentation。

 they basically have well up to 22 rules， it's bunch of this like if it does this and this and this and this right。

😊，This defines how they're going to do。You know， un nestesting。But again。

 all of these are going to be based on heuristics and rules。

 So on the plus side is these are somewhat somewhat easy to write if you know the pattern that you're looking for。

And because you can have complete control of like when things get moved and how they get moved。

 but as I'm saying handle all possible educations that you got to deal with all possible wear causes and kind of combinations of these nest queries。

 lateral joins is another thing that's complicated。

 then writing these rules by hand is simply to an effective。

So this is where the Germans show up in this paper in 2015 so there's actually two papers in the read list。

 this is the first one there's a fault one in 2017 that covers more about how they handle joints or other things。

 but I just wanted to focus on this one because it's an easy read is on how to do these correlated subqueries。

😊，But they actually provide as far as they know， the first general purpose method to be able to take all correlated subqueries and rewrite them into regular queries。

You know，Without the nesting and the goal is basically we're going to convert all of these these these subqueries into。

Joints。Record like innerjoins， outergens， whatever it supposed to be because again。

 we know how to optimize those and the best case scenario。

 we can go from something doing something really stupid like running that nest query for every single tu in theer outer query。

 which could be n squared cost and a nest loop join。

 we can now convert this into at ON hash joint lookup。

So let me quickly go through one example and again we can cover more of the hyperst next class。

 So here's that same query that we have before。 We want to find all the students and their major if they have the。

😊，If they add the highest grade for their major。 So the key idea that they're going they're going to have in this paper is they're going to introduce this。

 this logical concept or logical operator called a dependent join。

And it's basically crossproduct join or cross join。

 except that there's a demarcation or it's a marker to say this thing is specifically being used because I'm doing a correlated subquery。

 and the whole goal what the process thing we're going to do is try to get rid of that dependent join。

 convert it regular to regular joins and then optimize it like it normally would。

So in this case here， just the outtic query itself is a projection with a filter and a scan。

 but inside this filter clauses， we have the subqury inside of this。So。

If we take this and expand this， we can convert it into a dependent join because now we have on the the the right hand side is the。

So， the left hand side， maybe it's right。 The left hand side is the the look up on on the outer table。

 And then now on the other side and the right hand side， this is actually the inner query。

 And it's going to be referencing in in its filter or for its where predicate。

 be referencing the thing on the other side because that's what makes it correlated。😊，So as I said。

 this dependent join isn't actually a new physical operator。

 it's not something we actually implement in the system。

 it's just an extension to relational algebra in our query plan that allows us to reason about we know we're doing certain transformations in our query optimizer because it's a correlated sub query。

Again， so you could just convert this to like a cross join and add a little flag and say hey。

 by the way， I'm using this for keep track of dependencies。

 but keep it clean they define it as a separate operator right So again all you're doing is that for every single tuple in the left hand side。

 you're going to readrun whatever it is on right- hand side and populate the output and so forth right。

So again， it' just like a crossbo。So what they're going to want to try to do now is try to push down the dependent join to the right hand side of the query plan where we have our in query。

 and you eventually want to try to get it to the bottom and then convert it into a regular join。😡。

And then how you actually do this is going to depend on the semantics of the query。

of the inner query to determine how you actually do these transformations。So in this case here。

 I have， again， the scan on the left hand side and the anchor on the right hand side so I can move the dependent join down one。

And then now just do a join， a regular join on the adder query。

 and then whatever's coming up to me from the right hand side here。So for this particular query。

 make this work。😊，I had to introduce an additional scan that's basically going do duplicate elimination。

 Think of like a select clause where the all the projection output list is also my group I。

 So there's guarantees that I'm always gonna have distinct set of set of attributes or set of values coming up for all the attributes for given Table。

Right。So now with this， this this eliminating all the duplicates on this side。

 when I do now a dependent join on this side， then this guarantees that I'm only spitting up now the the output that I need to do the join without duplicates as if I was running the right hand sign query once per tuple on the。

On the outer table。 because again， what am I doing。

 I'm doing a max on the student score looking at my major。 So all I really want is for every major。

What's the max score？So it would avoid duplicates of like， okay， because there's， you know。

 there's two people in computer science。 and I don't want tona have two entries one you know。

 with the same values of computer science and then score the duplicate inlinmination scan When I do my join will will remove all that for me。

Again， this is just a logical operator。 is keeping track of what the dependencies are from the right hand side to left hand side as I'm going down。

So I want to keep pushing down the pen join。 so at the next stage。

 I can get rid of the going back here。 I want to get it below the aggregation。

 so I'm going to move my duplicate diminish scan down with me， but then put the aggregation above me。

Right， and again， at this point， nothing has changed。

 You think sort of what the output is going to be， like everythings still the same because。

What am I doing here， I'm giving all the the unique students by， by score and major。

 and then I want to join it with the。With the scan on the student' table here。

 so this is going to produce you know for every single student every single major here's the highest score and then when I feed that out of my dependent join thinking that this is a cross product。

 when I now do my group I here on the major， I'm going to get for one major I'm going to get the max score for it。

Yes I think the interesting thing is how did we come up with the fact that it's supposed to be group by because in the previous leg the group by was not there。

Yeah， so you have to identify to because you have lawers say， okay， I know that I want to get the。

I only want to get a single score per major right， so the equivalent thing you would do here like by putting the aggregation above。

 well， I need to make sure that I only get one student per major or one score per major。

 and then you add the group by to make that happen。Yeah。

 so there's logic to be a reason about what the。What the innerqua actually wants when you do the join up above to make sure you don't have duplicates。

I there a way to standardize that because that。It's his question is is the way to standard that it's in the original paper。

 And then it varies based on what the warehouse clause is， right。

 This is like something equals something。 If it's less than or greater than null complicates things to。

 right， this makes everything harder。We're well over time， so you have to go， please go。

We can do what we did last time we can pick up in this last class and the beginning of your next class。

All right， so。We pushed the aggregation above again we want to go further。

 we want to get this dependent join now below this filter。

 well that's easy to do right because there isn't actually any changes we need to make because whether or not we put the filter before after the join。

 that's the same thing if it was a regular query。😡，Right。

Like you can do a join stupidly without a warehouse clause and it's just a carteian product and then above that then you do the filter。

 same thing here， right？So in this case here again it's just a Cartesian product for every student unique major。

 Im going to join every unique major and a score， I'm going to join against all the students table。

 it's going to produce all the output I want all possible combinations and then this is going to filter out that I only get where the student from this side equals the major of the student or the major on that side。

Al， so now at this point here， my dependent join is as far as it can go。

 I can't go below these guys because it doesn't make any sense because these are the leaf nodes。

 I'm scanning the tables。 right So now I want to actually do further optimizations to actually put into a physical form or sorry put into a form that I know how to optimize like any other query。

 So again， these are all still at the logical level。

 We're not doing none of these are physical operators So I can convert this dependent joint into what it really is。

 which is just a cross join or Cartesian product。 So there's no where clauses， which。😊。

Just everything combined with everything on the other side。But then now I have。

 as I was saying before， I have a filter above a join that's just an error join。

 So now I can collapse these two to a single join operator and just move these guys up。😊，Right。

I can go even further and recognize that， well。You know。

 this is basically just for every single major。For every single student get their major。

 That's all this is doing here。Because my group I is going to handle removing the duplications。

So I can then I can then convert this now into just a scan on the table S by itself。

 but now to make sure that I have to rewrite my join that I had up here because I was referencing that the deduplication scan on the major I need to get rid of that so I can now also have a filter above that too so I can just combine that now into a single join where it's the major on this side。

 joined the major on that side and the score on this side equals the max score that I produce as my output here and because I have the group I the major clause。

 I'm guaranteeing that for every single major I have one score。😊，So this， this is the easy case。

 And again， there's some details And I I'm glossing over。 For example， he was asking。

 how do I know that I need to push up the group I， again。

 it depends on the examination of the where claws in in the expression trees。

So this can then be extended for all possible combinations of correlatedre queries。😊。

Convert everything into joints。Okay， we're well over time。As I was saying， only hyper， Ubra and DDB。

Can do this fully。 Databricks can do some of it。 I don't know about other systems。 I haven't seen。

 whether they make these things as well。So like this is if you're gonna to build a new system today。

 this is the way to do it。 paper lays out exactly how to do it。 Again。

 we will cover the other some cases in next class。 we'll cover also then how they're handling joint picking joint orders。

 But the other big thing we already alluded to today is like， okay。

 all the things I've talked about is like， hey， you have a cost。

 that's gonna to tell you whether one plan is better than another。

 What if your cost estimates are wrong。😊，Or you just don't know because you haven't even looked at the data before in a lakehouse environment。

 some new followship about S3， you don't know what's in them。What do you do？

So that that's what we'll cover on next class right， how to do adapter pre optimization。

 So and the T LDR is going to be， I got to generate something。

 I got to generate some query plan say I got to run something。

But again I can put in hooks that keep track of whether my estimates are right or wrong。

 and we'll see how to again get feedback from when we scan the table。

 feed that a across models and see whether that helped or not。



![](img/04a0e5d2919dbb25558fcbb02a1ed9f5_5.png)

Hi guys， enjoy the weekend， see you。

![](img/04a0e5d2919dbb25558fcbb02a1ed9f5_7.png)

S and six back on the table and I'm able to see St I on the way。No short put the crush。

 you know what got them， I take off the cat but first I' tap on the bottom。

 don about three in the freeze it so I can kill it。

 cat full with the bottle babyop don' fill it co nice and says the pain nice way you drink't get down with the guy in bus。

Take back the pack of good。' just some same now to trick it to the sun。

 Billy De and toil keep the delicate weak guys， be a man to get a kind of same time。

