# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P22：-22-Advanced Algorithms (COMPSCI 224), Lecture 23.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/eb18e9ae16f07270876c68ee1da8e805_0.png)

So let's get started。Yeah， so first， sorry about all the bug fixes on PS at7 yeah。

Maybe not not a surprise。 a lot of your homework problems， I basically make you prove。

Various alums and results from old papers。As it turns out， one of these papers I drewmma from。

Wrote some stuff that was not quite right。 And I sort of trusted them。

 And then when I looked into it， I was like， this， this is， there's some mistakes here。

And I I emailed them and yeah， so it seems like there were some small errors in their writing。

 but yeah， like factors of M missing from places， etca。And problem two， okay。

 so I'll have to keep that in mind for the future。嗯。So today。What are we going to do。

 so let me move this out of the weight？We're going to finish。Ling cutries， well。

 I'm just going to give you the analysis。In class， I'm going to show you log squared n amortized per。

And on PS at8， which is out， there is a problem that asks you to improve this to log in。Okay。

Also notice on Pet 8。 I skimmed the Pet 7。 you know。

 how much time did you spend on this Pet and the numbers seemed kind of high。

 So right before I released PSet 8， I thought。Maybe I should tone this down a little。

You can do one of problems two and three， you don't have to do both。Finish and cut analysis。So yeah。

 so getting the log n is on the Pet I'm going to show you log square in。And actually。

 we're using s trees， if you remember， in the auxiliary trees that we're using to store preferred paths。

We used s trees。So to get log squared n， you don't really need to useplay trees。

 any kind of balanced BST is fine。But。When you try to get log in， it's easiest to do it with s trees。

 basically by using。Theplay access alema we approved in lecture seven。

If you remember we had a specific potential function for s trees and we showed a certain luma about its performance。

Do people remember this？We defined a weight function on the vertices and based on various weight functions you can prove different properties。

So if you define the right weight function for Sp trees。And then pop that into the PSAT。

 you'll get a login and advertise analysis。So we'll show this in class， log in on the PSet。嗯。

And then we'll。Say some things about Min cost max flow。

And there's a problem on the Pet related to this as well。

And then today is going to be the last day when we do flow。

 there are only I think three lectures left after this， so I'll tell you about some other things。这可。

So if you remember。嗯。Last time。The way we implemented access， we had this subrpine called Access。

Which was performed on the vertex。Basically， this thing it makes。The root。Vtex。Of the root。

Tree of ox trees trees。And it did this by repeatedly displaying V and then connecting it preferred to its path parent。

And then now sping again to make it the root of that。

 and it just kept sping it upward right if people remember this。

And then we had a couple other operations。We had， let me just write cut and link again， so cut。first。

 did access。So now what's the picture here？V is in。嗯。Vi is here。If you remove when you're accessed。

 you have no preferred child， because if you are the last vertex touched in your subte。

 then you have no preferred child。This is V， so it has no right children here， it just has some。

Maybe V is the path。Is a path parent to maybe some people， but in its ox tree。

 it doesn't have any right children， and then it had some left children。And then we cut this。Right。

 so。So at the end of a cut operation， V is in its own ox tree and a singleton a tree。Right， so。

VDt left up parent is none。And then Vdot left is none。And then let me write the last one link。

 I'm not going to write all the other ones。We'll just focus on these for the analysis。Link B to W。

So V is the root of its represented tree， and W is in a different represented tree。

And now W is parent is the parent of V。 We draw an edge from V up to W。 That's what link does。

So the way we implemented this was we did access。V access W。

Now both of them are the roots of their respective。Ox treee of ox trees。And then now we need to just。

Splice in V as a left child。So。V dot left。It W。And W。 parentent is V。嗯。

Remember that the ox trees are keyed by depth。RightSo the fact that W is my parent in the representative tree means that its depth is one less than me。

So he's on my left subre。Okay，What we said last time is that。The runtime of access。

Is proportional to。Maybe something like one plus the number of。Preferred。Child。Changes。

Let me call this PCC。Okay。Because we keep spplaying V upwards in this tree of ox trees， right。

 and how many times do we have to do that？嗯。umbNot the runtime of access。

 but the number of iterations。Of let's say， ss。Performed。During access。s something like that。Right。

Every time we have a preferred child change。We displayplay the upward we merge with that。

Would that new parent in the preferred path？And then we keep sping upward until V is finally at the root O tree。

So。What we have is。The rununtime。Of M operations。Is at most？The cost of displays。

The worst case cost of spray。Times m plus the total number of preferred child changes across all M operations。

And this is， we know this is definitely at most login。I mean。Wait， what's your question。

 why is there an M there， So I just summed over all operations， so this one became an M。在位。Let's say。

 preferred child changes。嗯。In this。Access。And this access call。

Whereas this is the total number of preferred child changes across the entire sequence of in operations。

So what you're if you， if you do that Pet problem， you'll see that。This is really the。

This is really kind of wasteful to say the worst case cost of a times the number of preferred child changes。

You're going to see that kind of the total， the amortized cost of all displays combined is kind of on this order。

嗯。So。We just need to bound。Okay，You just need to bound the number of preferred child changes and we'll show。

That it's。Oh， M login。And that's why we get the n log squared。So before I can do that。

I need to introduce one more。Kind of analysis tool。Okay。So before we bound。PCC。

I wanted to find something。This is called the heavy light decomposition。

So just like we had the preferred path decomposition， this is some other way to decompose trees。Okay。

But we're really going to use this。 So with a preferred pathy composition。

We actually use that to design our data structure， right。

 because our aux tree contains preferred paths。With heavy light decomposition。

 we're just going to use this as an analysis tool。 We're not actually going to maintain it in our data structure in any way。

嗯。So you know with display trees， we are getting amortized bounds。

 if you want to get worst case bounds， the ways that do that actually do maintain this explicitly in the data structure。

 but for us we're not going to we're just going to use it for analysis。Okay， so。For a vertex V。

Define。Size V。Is the。Size of its subary。The number of。

The number of vertices in its subt in the represented tree。And。Oh， do you have a subscriber today？Oh。

 okay， great okay。嗯。Good， so。If we have the representative tree here and there's some vertex that has some。

Subtre is hanging off of it。Let's call this V， let's call this U。So you as a child of V。We say。

The edge U。Is。Light。If the size。Of you。Is that most1 half the size of V？And we call it heavy。

If the size。Of you is bigger than a half the size of me。Is at least a half。Okay。So in our case。

Each charge。In the representativeatory。Has one of four types。It can either be light or heavy。

Or it be and it can also be preferred or not preferred。So just to set up some language。

Over the course of operations。嗯。We might create new。Well。

 of course of operations we might destroy some preferred children and create some new preferred edges。

 destroy some preferred edges and create some new preferred edges。Meaning if we access something。

If we access a vertex v， the root to V path is now the preferred path。Right。

 which means that all some of the edges above， which used to be preferred， are no longer preferred。

If they were hanging off a different subt。 So we， we say that we destroyed those。

Preferred edges and we created some new ones。Let's say if you know。UV。Used to be preferred。

It's called V is the parent。Of view。 So U V used to be preferred， but now。WV is。Then we say。UV。

Was destroyed。And WV。Was created。So the first thing is we want to bound PCC， so claim。Is that PCCC。

Is that most？I'll define these two。LPCC plus M plus N， where this is。Light。Preferred。Edge。Creations。

对。So I want to show you that this is true。 And then we can， then we just need to bound this。

So questions about anything？Oh， why am I calling it preferred child creation？

just so it matches the acronym。O。So let's prove this。So。First of all。

 whenever we create a preferred child。You know， making new preferred edge。

That new creation of this preferred child is either。A heavy creation or a light creation。

 right so I just want to make sure we're all on the same page here， so here's the root。

The root SMM path。Down to W。嗯。W used to have。OrI guess I called it V。

V used to have some preferred child U， but then we didn't access。Then we didn't access on W。Right。

 and then now。This is no longer the preferred child， and then this is preferred。

 This is the new preferred。Right， so we're all on the same page here。So I'm saying that this。

Was a preferred child destruction， and this was a preferred child creation。When we didn an access。

 so we did。We didn't access。Somewhere in W subree。Right。Okay。

 so this thing that so this is a preferred child change， so we should count it here。Now。

 it might either be this new edge that we just created could be either light or heavy， right。

 That depends on the structure of the representativeory on the various sizes。Now， if it's light。😡。

Okay， so proof。If。If WV is light。Great。Because we count it。It definitely gets counted here。

 it is a preferred child creation， and it gets counted here because it's a light creation。Now。

You know， what if。W V。It's heavy。제요。There are two cases。In the first case。Case one。

I'll say W is null。It might be the case that V didn't have a preferred child before。Right。

And then that we touch， now that we access something W subree， now W is the preferred child。

But how many times can this happen？ Well， how can it be the case that V has no preferred child。

Either， this is the very first time we're ever touching V subre。😡，Right？

But that can happen at most end times。Right， so either。This is。First， access。In V's subre。

That happens at most n times across all V。Acroscro all time。This happens at most n times。Or。嗯嗯。

Or the last access in V subte。😡，Was either to V itself？That's why it has no preferred child。

 or it had one， and then we cut it off in a cut operation。Or。Last。Access。呃。In V subree。Was to V。Or。

We could。The previous。Prefer a child。I guess actually another thing about it。

 the way that cut is implemented。嗯。Then it would also be the last access in the subid。

V would be the last axis in its sub。 So really， it's only this case。But。Then。

Whenever we do an access on a vertex， we can imagine after we finished doing the access on that vertex。

 we hand that vertex a dollar。And then the next time that vertex v is ever in the situation where theres a heavy edge creation。

Then we could spend that dollar to pay for this。And and the amount of dollars we're spending is them。

 one per， one for access。Does that make sense。Basically， we charge。

We charge this to the last access on V。If you look， Trump， is there any question？The last act。No。

 I'm charging。So we're this heavy- we're in this case where we're creating a heavy preferred edge。

And what I'm saying is。If we're creating a heavy preferred edge。And。

And our parent doesn't already have a preferred child。Because its last access was to be itself。

Then we'll charge this heavy edge creation to that last access to V。

And each and each access will only be charged at most once in this way。Because next time。

 the next time we see V。It will have a preferred child， namely W。Unless there was another access。

In which case， that access would get charged。So we actually didn't really need this because there's an access in there。

So。We charge。To the last。Access on me。Okay。In case two。These two is again going to be dischar。

You as not no。So it actually had a preferred child before。So this edge WV is heavy。😡。

What can you tell me about U？Can a vertex have two heavy children？No， right。

 Because what does it mean to be heavy， The size is strictly more than a half。

 This subte has strictly more than a half of the children of of the descendants of the。

So it can only have at most one heavy child。So。This implies。We destroyed。Some preferred light edge。呃。

UV。Yeah， representative， that's right。No。It can have many light children。

RightYou can have lots and lots of like children， but you can only have one heavy child。

Or you have no heavy children， that's also possible。Right。

 but how many times can you destroy a preferred light edge。Well。

 it had to have been created at some point for you to destroy it。

So you can charge it to the time when it was created。So that's why I have a factor of two here。

 do I that factor of two？Right。Okay， so that's that。So now that we have that in hand。

 let's look at the cost of cut link and access。🤧。やたか。Oh。Because I want to。

🤧When does it charge the last access？RightSo in this way。And okay。

 so I want to charge the last access， and then now the question is。

How many times can any particular access be charged in this way？At most once。

It'll be charged by the next heavy edge creation， heavy child， heavy preferred child creation。

So each operation。Is being charged in this way at most once。 They are M operations。

 So that's an extra additive M。Is that， is that okay。So now let's bound。LPCC across。You know， access。

Li。And cut。So。Access。🤧Note access。Doesn't change the representative at all。

Access only changes what's preferred and what's not preferred。

So what's light and what's heavy doesn't change。Only preferred and not preferred changes。

So as we walk back up the tree。Changing these preferred child pointers。

We just need to count how many of those new preferred child pointers is light。

Because we're only counting light preferred child creations。Now。On any。Root。

On any path but on any route to the path。In a。In the represented tree。Number of light edges。

Is that most what？How many light edges can you have in a path from the root down to some vertex？

Not log of the log of something。 log of what。But yeah， so log of something。 So what's the point。

 right？ So first of all， how big can the size of a sub be， What's the， you know。

 what's the mean any upper bound。No， no， just in period。 So you have this represented tree。

 You have a vertex in the represented tree。 It has some size parameter， right。

 The size is the size of its subtre in the represented tree。What's an upper bound on that。

 That's always true。N， right you can't have more than N people in your sub。🤧看。

And if you're following the light edge， the size is decreasing by a factor of  two。

So in any path from the root down to anything。The number of light edges you traverse can never be more than log in。

Right。When you're doing an access and and you're changing。

You're changing preferred children going upward toward the route。

 You're changing it along this preferred path。Some of those are heavy creations。

 some are light creations， but the number of light creations is at most log n。

Because they're only at most log n and light edges on a path。And。Okay， then related is log n。And。

What's light versus what's heavy doesn't change。During access。That's it。So so that's giving us。

Remember， the bound we're trying to get on PCC was M log N。

So we know that there are at most M accesses， each one is having at most login light preferred child creations。

So that's M log N。 That's fine。So now let's look at link。Okay。🤧So。So what does Link do。

 the first thing Link does。Is it does two accessorieses， right， So let's say link on VW。

It does access on V and access on W。Right。The LPCCs for the Aes are already covered by item1 here。So。

 we first。Do access。V。And access W。And then now what do we have？嗯。And then。What do we do。呃。

Let's look at the representativeatory。So。W is somewhere。In the representativeatory。F me。

 how should I want to write this。There's W。It has some subrees hanging off。

And then we also now hang off V。And what's the preferred？What's the preferred？Path here。

What are the preferred paths， this path is preferred because we didn't access on W。And。嗯。

That actually goes all the way down to V。Okay。🤧Good， so how many。And so what I want to say。嗯。Now。

 what can we say about so this so we really did the axis on V and already did the axis on W right that's already taken care of。

 but then after we do those two accesses， then what do we do， we add this edge right here。Right。

So what changes now is light versus heavy。😡，Right。So in particular。All the yellow edges here。

Got heavier。Right。And all of the old preferred children that used to hang off here。Got lighter。So。

Maybe because they got lighter， that counts as you might say does that count as a light edge creation。

 well it's not a preferred child。😡，Right。Other other edges hanging off。gott lighter。

But who cares because they're not preferred？They're not preferred。

But the yellow edges that got heavier， that might result in some heavy edge creations。

But we're not counting heavy educations anyway， so we don't care either。Okay， so。

So this bullet can be the source of heavy edge creations， we don't care。

Heavy preferred edge creations， but we don't care about heavy preferred edge creations。

 This could result in light。Edge creations， but they're not preferred。

So we also don't care about them。So this。This final edge that we draw is basically free in terms of counting LPCCs。

We only had to pay for the two accessorieses on VNW before we did that linking before we added the edge。

 yeah。哦。No， they might not be heavy。white。嗯。Oh， so。This was already made preferred by the access。😡。

So the access paid for that。Okay， and。If it's still light now。

 it was definitely light before when we did the access， so the access paid for it。Right。

Does that answer your question？Oh， so maybe there's one more。But that's an Arab one Iarch。Good。

It's actually， I guess， technically the way that we implemented link。Was。How did we。诶。Yeah， actually。

 technically， the way that we implemented Li。This wasn't even in the preferred path either。

Because we didn an access on V， then we didnt access on W。So V might have some preferred childs。Oh。

 so now V doesn't even have a preferred child because the last axis in V sub was to V itself。

So that's actually the picture after a link。Does that make sense？So that's that。

Now we just need to handle cut。嗯。What does this do， remember？Cuts off。V from。It's parent。

W in the rep tree， representative tree。So what's the picture there？So。

The first thing we did was we did an access to V。 So let's， let's again， draw this。

Let's draw this representative tree。Okay， so。That's W。V is hanging off， used to hang off here。

And V has a subt。And then we cut that off。Okay。So again。After the access。We just change。呃。

After the access， we change what's light and heavy。Right by cutting this edge。Okay。So。What changes。

 So some of the things here that hang off here。So edge just hanging off。This yellow preferred path。

Go heavier。But they're not preferred。So we don't care。Even if they were preferred。

 I guess we wouldn't care because we don't care about heavy edge creations。

But the edges in the yellow path now got lighter。😡，They got lighter because we cut this out。

So there might be some number of light preferred edge creations along this yellow path。Okay。

 our people will。Belieieving me。But there can be。How many can there be？Log in because again。

 it's a path， it's a root to leave path。So。In total。呃。TheN of LPCCs。Across。M operations。Is of。

And log it。好的。So that's it for the log squared and amortized bound。Are there any questions about？

Throughout this。Secondly， I guess you should also there were a bunch of other operations。

 there was find root， find men， all those other things。I mean。

 there's not much to say for those you can go through and look at it yourself if you want。

These are the three， I think， ones that require the most work， and they weren't even that much work。

🤧P。Yeah。Yeah， so this implies。And operations。Take time。Oh。M log squared n。Plus， I guess n log n。

 because the number of PCCs are multiplying log n。对。Right， so I mean this is。

But this this is kind of a sloppy Well， it depends on how you're using your link cut trees， right。

 if you're using them in say blocking flow。Then the very first step you're doing is you're doing N make trees anyway。

 So， you know， this is the dominant this is the dominant thing here。Because in blocking flow。

 Amazon number of edges， so it's bigger than N。So M log squared is going to be bigger than M log n anyway。

But yeah， it turns out as you see on the PAT， this log squared can get improved to log in。

Same data structure， just better analysis of using Sp trees。Any other questions？Okay。

 so that's all I wanted to say for。Forlin countries。So if there are no more questions。

 then I'll switch to the second topic， which is in cost Maxwell。Yeah。だなあ。Yeah， so I didn't yeah。

I mean， I'll just mention you can do those things using。

Basically by augmenting the binary research tree you're using inside of a trees。Right。

RightSo how should I let me give you？So for example，So your question is how do you do things like？

Add subtract flow。So maybe I I'll say something about it， and I won't go into all the details， but。

The heart of it is basically augmented BSTs。Which you'll use inside of your ox trees。

 your ox trees will be augmented。I went to binary search trees。So suppose， for example。

Suppose they have。And items。Which are。You know， key value pairs。Right。

 and I want to support operations like。Operations like， say， sum of K。Returns。Some。Of all。Values。

Corresponding。Two keys that are all at most K。Right。

And you want to support also insertion of key value pairs， deletion of them and these sum operations。

 predecessor， et cetera。 So you can do this kind of thing with BSTs by basically augmenting the nodes to contain subre sums。

Right and then as you're walking down the tree， you can you can use these subtre sums to get answers for this。

 so using this kind of idea， you can also implement those operations and the ox trees so the basic idea is it's not going to be sum like the thing that you're applying the operation you're applying is not sum it's like a min operation。

 for example。So if you want to keep track of like min capacity。So。

Kind of each node will contain the minimum capacity of all nodes in its subre。

 And by manipulating these augmentations， you can， you can handle all that。 So yeah。

 you can think about it as an exercise， but I don't want to spend too much time on it。

Any other questions？Yeah， good question。Becauseuse I completely skipped it。Okay。So Min cost Maxflow。

So that's it for basic flow， max flow， right so remember we got into this whole link country business because we were trying to speed up block flow。

So how about another twist on Maxflow， which is Min cost max flow？So。Min cost。Max flowlow。Each edge。

Has。Not only。Not only。A capacity。I'll call it U of E。But also。A cost C of E。

 which is possibly negative。Possibly or zero。So it's any real number， let's say。Actually。

 I'm going to。At some points， let's just write capacities。R in。One up to U， capital U and costs。

Are in minus C up to C。 So let's just say they're intes。From minus capital Z to capital C。And。

The goal。Is to find。A max。S T flow。Which minimizes。The cost and what's the cost？

Let's call this flow F。Which minimizes the cost enough。Which is the sum overall edges。

Of the flow on that edge times the cost of the edge。So just so we're clear。Consider all flows F。

 which are max flows。 So we definitely want our flow to be a max flow。And amongst those。

 choose the wine whose cost is minimal。And let me just write a little note here。

In the residual graph。The reverse。OfG。Has costs。 So remember what the residual。

 I'll fill this in right now。 But remember what the residual graph is supposed to to us when represent for us when we're doing flow computations。

It's representing to us that we can push flow， we can augment flow along certain paths。

Right so for example。If we had an edge with capacity too。And。So far in the flow we've built up。

 we're pushing one flow along that edge。Then in the residual graph， it's still left with capacity 1。

 and the reverse edge is also now there with capacity1。

Because we can send back that flow that's currently on it。So when you're dealing with costs。

 you have to， you know， be a little careful about costs in the residual graph。

 So what do you think the cost should be， right？ So if you have an edge E that's appearing in the。

Original graph。 and there's still some residual capacity left on it。

It'll still appear in the residual graph with that with the same capacity with the capacity that's left。

 as well as whatever the cost was。But the reverse edge will also appear。

It'll appear with whatever amount of flow we're pushing on it because we can send that flow back。

 but with what cost。Yeah， the negative， right， because if you push that flow back。

 then you retrieve the cost that you paid。So just keep that in mind， it has cost minus CM。Okay。

So a related problem。Is a problem called Min cost。Circulation。What is a circulation？

Circulation is a flow。F， such that。Flow in。So let's say inflow of the。Equals outflow。

Of the for all the。So there's no source and sync。Okay。You're just pushing flow around in cycles。

That's the circulation。So。What I want to say about these two problems。嗯。Yeah so。Okay， so claim。

Min cost max flow。And Minco circulation。Efficiently。Reducuce to each other。

So you only really need to focus on one。S proof。Suppose you can do。Suppose you can do mincom flow。

Why does that imply that you can do minco circulation？So， this is。This is an easy one。Maybe。

I give you a graph with capacities and costs。 I tell you find me， I tell you。

 find me a minimum cost circulation。If you have an algorithm that already solves Minco max flow。

 why can you solve Minco circulation？What would you do。So someone gives you a graph G。

And says finally me the Minco circulation， what do you do？Yeah。おわ。So， okay， so back to okay。

 let me let me make sure I'm using the right words for things。 So a flow。A flow is just。Or let's say。

 I don't want to say this。哎。不で。Yeah， but cost can be negative。Right。You have。Their capacities。 Yeah。

 so even if there are negative cost cycles， it doesn't mean it doesn't mean that the problem minus infinity or something。

 Their capacities involved。Right，So okay， so if you can solve min MCC， how would you solve min。

 if you could solve min Cosmax flow， how would you solve min cost circulation。

Like how would you call this as a subroutine to solve this？First of all。

 this needs a source in a sink。To call it， right， the definition of the problem involves a source in a sink S And T。

 There's no source in sync here， right， So what do you do。You could。

 or you could just add a source and not connect it with anything。

And you could also add a sink and not connect it to anything either。

So the max flow in this graph is0。any ST flow in this graph is a circulation。

And then you just find the min cost max flow in this graph， and it's a minco circulation。Okay。

How about this one， If I could solve Minco circulation。

 why does that mean I can solve Minco max flow。嗯。Right， so， okay， so yeah， you're saying。

Add an edge from T to S。And try to find a Min cost max flow。And then。If you saturate that edge。

 it means you can achieve this flow。 So I'll up the capacity by one。 And if I keep。

 if I keep being able to saturated it， I could just keep increasing the capacity， Right？ So， so yeah。

 I think that's。嗯。A good answer。呃。So that says that if you can solve。Minco circulation。

 you can solve this by calling this subroutine many times。

 The number of times we need to call it would be proportional to。To the actual max value。

 But I claim there' there's a way to do things we only call it once。Yeah。嗯。Yeah。

 I think that actually。 so， yeah， maybe that's so。Add。嗯。Oh， is that actually what I want to do？

So actually， no， so actually now I'm not now let me take back what I just said。

So the problem is when you're calling the MCC algorithm。

It doesn't really care about putting flow on that edge at all。

 It's just trying to find a circulation a minimum cost。 So taking that， taking that circulation。

 which goes as the T and comes back， right， it might end up having some。Positive value。So it might。

 might not want to use it at all。 It might instead want to use some other cycle in the graph somewhere else。

Right。I'm sorry。Yeah， I mean， it might not want to use this edge back from T to S。 So yeah。

 there's no， it has no incentive to create a max。嗯。

Now that might be fixable by basically making the T to S edge have a very negative cost so that it really likes to use it no matter what。

I think that I think that can work。 So another thing that you can do is you can say， look。

 the very first thing I'll do。 so maybe I should have written。Max flow plus MCCC implies this。

 So the very first thing you do is like， just find any max flow。 Don't care about costs at all。

 Just find a max flow。Okay。And now in your residual graph。😡，Find a Minco circulation。

And when you do that。Add that back to the original flow you found。So one thing you could do is。So。

Add T to S edge。With very。Negative cost。And infinite capacity。That's one thing you do。

 or another thing you could do is。Find。Any。Max Flow。F in G。Then， find。MCC。F star。So， notice that。

The difference of any two ST T flows。Is a circulation。Okay。The same S& T。Oh， the same flow value。

 Yeah， sorry， that's right。 Any two S T flows of the same flow value。

 there are differences of circulation。So。That means if theres some other flow F star。

 which is the actual Min cost max flow。Then。F star minus F。Will be a valid circulation。

In the residual graph。And。And then you can find it and then add it back to this。Back to that。

 so find MCCC。In a residual graph。Then add it。Okay， so。Okay good， so now let me look at MCC。So claim。

So we want to be able to now find MCCCs mean cost regulations。And one way to do it is。You know， find。

 so let me propose an algorithm actually for MCCC。And then we have to prove that it's correct。

While there exists。A negative。Cost。洗个。In the residual graph。Augment。Along that cycle。但是后。

How would you actually implement this algorithm？You need to figure out if there's a negative cost cycle and identify it。

 How would you do this。Do people remember？S algorithm， building forward。So， you can implement。

Negative cycle。Finding。In time。Oh of。Mmen。This is Belman Ford。

You can also do it even in O of M root and log C。Essentially， by some scaling algorithm。

 this is due to Goldberg。In。95， I believe。So all the costs are between minus capital C and capital C。

I believe it's a 95。 whether I write it。🤧K。This is also。With many hints， this is。

Problem two on the current PSet。Actually， I mean， this is what this is。

Shortest this is single source shortest paths in in graphs， in general graphs。

 where there might be negative edge weights。So Belman4 gives you MN。

 Goldberg gives you M root N log C by a scaling algorithm。It's a little tricky。

 but I think I gave a lot of hints and there are many parts。Okay， great。So the only question is。

 so this is the algorithm。So there's a question of how fast or slow is it。What's the runtime？

That's the same thing。 How fast or slow is it and is it correct？Okay。Okay， so correctness。

Say we have some。Cirulation， some current circulation F。And optimal。Circulation。In terms of cost。

Is an F star。Okay。🤧So。And let's say that。Suppose。The cost。

Of F star is strictly better than the cost of F。Then what can you tell me about？F minus F star。呃。

F star sorry， F star minus F。 what can you tell about F star minus F？

Or what are a couple things you can tell about F star minus half。Yeah， it's negative cost。

 So if we augment buy it。Then we'll decrease our cost。Right。And what， what else can tell me about it。

 Well， I'll just tell you， it's a circulation。If you take two circulations and subtract them or add them。

 you get back of circulation， right。So。Is negative。Cost。Circulation。

And it's feasible in our residual graph。Okay。Great， so if we're not at the optimal thing。

 it means our residual graph has a negative cost。It has a negative cost circulation。

But we're not just looking for negative cost circulations。 We're looking for negative cost cycles。

Right。But I claim that any circulation decomposes into。Kind of a。M cycles， basically。

Basically just like you can decompose flows into paths。You can decompose circulation into cycles。

Start at any edge that has some positive flow on it。And then follow it around in a cycle。

And then when you get back to the end of the cycle。

 record what the minimum capacity was on that cycle。

And then extract that cycle out with that minimum capacity。 Now， what are you left with。

 You're left with。 again， what you're left with is a circulation。With one less edge。

 because definitely at least one edge got saturated。 right。

 So you can just keep doing this over and over again， pulling out cycles。

 You're decreasing the number of edges by one each time。So you can decompose any circulation。

Into a collection of M cycles。And if the circulation in total is negative。

 it means one of those cycles is negative。Right。So if you search for a negative cost cycle。

 so there will be a negative cost cycle， and you could augment by it。In fact， I mean。

 they had better all be negative， right otherwise there's no point in including it in your circulation。

Cirulation。Decomposes。And set cycles。So one of them is negative， we'll find it， great。嗯。

So what's our actually let me just write it right here， what's our runtime？So in each iteration。

 we need to run， say Belelmand Ford。Or if you can run the other one。

 how many iterations can there be？I mean， give me any valid bound。M C， only think， is that right so。

Yeah， because you're saying。We decreased the cost by at least one。

So I think you need to add something else there， not just MC， but MUC， maybe。Right。

 so every time we do this augmentation， we decrease the cost by at least one。

You know how low could the cost possibly be？Well， there are M edges that each have capacity at most U。

 and the cost is at least negative c。So the number of times we can decrease the costs is at most MUC。

So I think all the men times M UC。So this is a pseudo polynomial tiny algorithm。

Kind of like the Ford Fulkerson of。Min cost circulation。So let's try to do better。Before I do better。

I wanted to find something。So， definition。A price function。Ely。P， which maps the vertices。

Into the real numbers。呃。Induces a。Reduced。Cost。Function。So let's say we have an edge UVV。Okay。

It's reduced cost。Is the old cost， the original cost of the edge。Plus， the price of V。

Minus the price of U。嗯。I which I want to tell you。OhActually， plus P。

So the way to think about this is。Let's say that we are。Buying gold at vertexU。Okay。

 so we have to pay to buy it that costs whatever the price of gold is that vertex you。

We have to pay to ship it to V。And then when we sell it at V， we make money。

 which means negative cost。So that's how you should think of this。And。Claim。啊。F is an optimal。

Min cause circulation， if and only if there exists a price function。P衣。In the residual graph。

 let's call it the residual graph is G subF。Such that。All reduced。Costs。Are non negative。So， proof。

So let's do one direction。Suppose。There exists。Such。

Such a price function such that all the reduced costs are non negative。I have a question for you。

 what's the cost of a cycle？Using the original cost function versus using the reduced cost function。

Is the same， because。These PUs and PVs cancel along the cycle。

So costs of cycles don't change when you use reduced costs。

And we know from before that we're optimal when there are no more negative cycles。Right。

In the residual graph。So if there is such a P。Well， every reduced cost is not negative。

 which means that the reduced cost of a recycle is not negative。

Which means that the cost of every cycle is not negative。How about the other direction？Suppose。G。

Has no。Negative cycles。So I'll just tell you what you would do here。Introduce。A new vertex。S。

With zero cost edges。It's everyone。Now define。The price of you。

As just being the shortest path distance under the costs from S to U。

This is theest shortest path link for S you。That's well defined because there are no negative cycles。

You can show just by basically triangle inequality that this thing is a valid price function。 I mean。

 not valid， but this thing as a price function will satisfy that all of these things are straight are not negative。

That's the triangle inequality。Okay， so。I'll let you think about that offline。

Tranel inequality implies CP is at least zero。Everywhere。So you can work better。Okay， so now。嗯。

So now let's look at faster。Min cost Max well。So simple case。Let's say there are no negative cycles。

 negative cost cycles。And all capacities。All edge capacities。A one。So this U is what？Actually。

 let me make it even simpler。And let me just say。There are no negative edges at all。

Here's going to be an algorithm。Find the shortest ST path。According to costs。

 using costs as your edge length。In a visual graph， an augment along that path。

So a claim is that this thing is correct。So first of all， the runtime。Andmost N iterations。

And you can use dik straw in each iteration because edges are going to be non negative。 Well。

 they're definitely non negative in the beginning， And we're going to see that even in future iterations。

 they're going to remain non negative， even in the residual graph。

 Remember that we negate costs in the residual graph， right。

So it's not clear a priori that they remain non negative in the residual graph。

But we're going to see that that is true。Of emn foreration。This is Dyke straw。

So that implies that the total time is O of Mn plus n squared log n。

Dykester with the Fibonacci heaps。So。So the claim。Is that there would never be。嗯。Negative cost edges。

In the residual graph。What's the proof？So remember， this is a unit capacity graph。Right。

What's set prices？S PV is the shortest path distance from S to V。And the this is。

I should say negative。Native cycles。Okay。Okay， good。So。So， any。Edge。We。Augment along。

Is in a shortest path。We only augment along shortest paths。And。if an edge is part of a shortest path。

 if the edge U is part of a shortest path。That means that the weight of the edge UVV。Plus。

 the distance to U is equal to the distance to V。RightThat's the property of shortest paths。

 me basically。Move this over here。The distance to V， if U V is part of the shortest path to V。

 then the distance to V is equal to the distance to U plus the cost of the IUV。

Which means that the reduced cost is zero。so any edge we augment to along is in the shortest path。

 which implies that its reduced cost is 0。And when we augment along it。

That means that it's saturated because it's a unit capacity graph。

 and the reverse edge will be put in the residual graph with， with negative cost。

But negative of zero is zero。Okay， so the edges that we introduce。嗯。

The new edges that we introduce into the residual graph will never be negative。So in fact。

 we'll never even have negative reduced cost。Negative reduced costs。

That's what I really should say we'll never have negative reduced cost of residual graph。

Implies that。When we add。Any。M edge。To the residual graph。It's。The reverse。Of a saturated edge。

Which implies that it's reduced cost to zero。So any energy on the residual graph will never be。

We' never be negative， and I think I'm out of time。嗯。There's not much more to say。

 but I think I'll just augment a couple of paragraphs at the end of this in the notes。

And you can look and look at the notes。For the remaining part of the argument。

No questions about anything I set up to this point。

And then one of the Pet problems is going to be using scaling to basically。呃。

Let you use not just unit capacities， but arbitrary capacities。I'm sorry。Oh， you're saying。

 what if the graph originally does have negative cycles？

So if the graph originally does have negative cycles， basically what you do。

Is first you find any max flow。Okay， and then now you just need to find a minco circulation。Right。

So that graph， now you need to find cost circulation。 It might have some。

 it might have some negative cycles in it。 In fact， it better have negative cycles。 Otherwise。

 there's no point in finding cost circulation。 So we're gonna to do is just look at any negative edge。

Forget about cycles。 Just look at any negative edge and just fully saturate that edge with flow。

That's not going to be a valid circulation。So now you need to turn this into a valid circulation。

But by fully saturating certain edges， what you've done is some flows have extra flow coming in and some flows have extra flow coming out。

And you need to fix that， you need to basically send the flow back to where it came from。

So you'll do is you'll create a new source in sync。

Conect connect the source to everyone who needs to push flow out of them。

And then everyone who needs to push everyone else， you push， you connect them to T。

And you set up the capacities in such a way that the capacity is equal to exactly how much flow I need to push out of me。

 And now you try to find a min cost max flow in that graph。

But that graph has all positive costs or non negative costs。 And then you can use basically this。

 So I know that went kind of fast， but。嗯。No， you'll end up with。And unitac graphs？

You won't have this terrible MUC kind of runtime。You'll have something that's actually strongly polynomial。

But you can speed it up using scaling。 but then you have like a long U dependence。

So the scaling by you you'll see on the PSet。And I'll complete this in the notes。

 I think we're very out of time。