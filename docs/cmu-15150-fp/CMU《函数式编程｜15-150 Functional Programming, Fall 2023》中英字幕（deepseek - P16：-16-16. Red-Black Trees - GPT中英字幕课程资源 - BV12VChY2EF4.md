# CMU《函数式编程｜15-150 Functional Programming, Fall 2023》中英字幕（deepseek - P16：-16-16. Red-Black Trees - GPT中英字幕课程资源 - BV12VChY2EF4

So red black trees， I promised you we were going to talk about an application of modules and red black trees are a really good one because what are modules good for they're good for abstraction。

 we can make an abstract type no one knows about other than us which means no one can go and mess with our nice shiny little Lego b okay nobody can mess up ourvaris so if we having an imvariant full structure and the structure with many invaris we want to carefully design it so that nobody can ever break it and red black trees are a really good example all right。

😡，Let's get started showmi so what we're going to do is in four parts we're going to talk about red black trees。

 the invariance of a red black tree， what a red black tree is will implement it in standardmal of course and then I'm going to finally show you a final trace of what it might look like to do series of operations on a red black tree okay and red black trees I think are like like。

😡，Not an easily testable subject in terms of like it would be kind of boring if I was just like what are the invaris of a red black tree。

 but critically critically you should understand like these invaris are really cool first of all。

 like really nice to implement in a functional language and secondarily just like a good example。

 but I've talked too much anyways。So last time we talked about generic dictionaries right that's steam last time we talked about generic dictionaries。

 which are dictionaries that take in arbitrarytyped keys and arbitrarily typed data and we can do that because punctors let us parameterize over type classes。

 we can parameterize our keys as instances of the ord type class an inch ord or a string ord or a pig Latin ord and we can have data of arbitrary type as well with polymorphism and we saw that we could do this better with puncctors because we might not mess up our comparison functions。

😡，And that's pretty much all that we did last time today we're going to be talking mostly about the red black trees and then the funcctors will be an after block。

😊，So what on earth what on God's green earth is a red black tree Well I don't know let's get into it so remember this signature this is the signature of polydict and so it should look pretty much the same as we it should look exactly the same as what we had last section right we want to support three operations empty insert and lookup I've removed remove like the repletion operation for brevity but we could do it fairly easily okay and you probably would want that to as well for like a really good like a basic dictionary interface but we're gonna to drop it but we want empty insert and lookup and that's pretty much what we need okay。

😡，And remember that our definition of insertion is that we just compare keys as we walk down the tree。

 that's how we traverse in a binary search tree， we go left or right depending on what that result is right until eventually we'll get to an empty at the very end of the tree。

😡，But I want to caution you against this idea because this is not the best thing we can do right and let's let's see it so so if I if I wanted to do a sequence of operations potentially I might start from what I'll say is the empty tree。

😡，All right， and then if I wanted to insert the key zero， what would I get I would get？😡，Zero。

 and I'm going to do a thing now where I when I do an insertion trace。

 I'm going to ask you which way we go， Okay， I'm going so if we inserted one。

 I want you tosha it out， which way did we go。😡，Right， so actually， let me draw again。Z one。

 and then I want to insert two， so where do I go？Right。Right， okay， so then we go again。

 and I'm just going to wrap around to a real fast。And now， okay， now what if I want to insert three。

 we go。Right， right， right Oh my God we just to have to keep going right and guess what the number of rights I'm going to tell you or you're gonna have to shout out is linear in the number of nodes that we've inserted thus far Now I don't know about you but I don't have the voice to keep going on for that Okay and by placing the burden on you now I've established a personal connection now you don't want to say right n times so let's figure out how we can do better so。

If I want to avoid this case， this pathological case for an arbitrary binary search tree。

 I want to make sure that my tree is relatively balanced today we'll talk about a scheme for doing so called a self-balcing tree okay so this is going to be called red black trees as I've already told you okay and we're not going to do the workpan super formally。

 but we can mathematically reason that the insertion and lookup in the worst case is going to be logarithmic as it should be right on a roughly balanced tree it should be o log n to pay per lookup。

😡，So。If we wanted to define a red black tree in Sanl。

 here's what it would look like okay and I'll give you a second to think about what this is saying when I show you code in this lecture。

 we're working like within a structure that we're going to define at the end of lecture so like this key dot T like just exists like assume that this key is like in the ambient environment all right but a red black tree is three things it is either empty。

😡，Or it's red。 And it has two subtes and a key and a value。 Or it's black。

 and it has two subtes and a key in a value。 Okay， a red black tree looks exactly like a tree。

A dictionary tree even because there's a key involved， but。There are two cases for its nodes。

 the nodes can be colored either red or black， hence the name red black tree， okay。😡。

So it's a particular kind of BSC and there are three invaris that we want to be assured of when we're working with red。

 black trees and they are as such。😡，The first invari is a red black tree is a BST that means what it means that as you showed on midterm1。

 if I take the in order traversal of this tree where it's defined you know kind of intuitively as what you might think it is if I take that in order traveral it is in nondeecreasing order right so like it would not be valid for me to have like a BST that's like。

😡，Zero left one right because this is not sorted with respect to its keys I need to make sure that the keys are sorted right so one is a BSC and then two。

😡，Any red node has black children okay， if you have a red node， the children must be black。

 you cannot have a red node that has a red child， we call that a red red violation and we'll talk about that in a second okay。

😡，And then three， the most important invariant。Every single path from the root node to any empty node。

 that means like。If I went like this from the root to empty or from the root to empty or from the root to empty or from the root to empty empty。

 right， when I don't draw the node， it means there's an empty node there。

 Any such path must have the same number of black nodes along it。 We call that the black height。

 That's an invariant that we're going to try and keep。😡，Okay， so with these three invaris。😊。

We're going to be able to， if any tree satisfies these variants。

 I guarantee you that lookup can occur in log n time okay log n where n is the number of nodes in the tree and we'll talk about why that is in a second。

 but as everyone have always written down in Israel relatively to nuclear on this。😡，Okay， cool。

 let just want to make sure we're moving forward。I also wasn't sure。 Yeah， okay， cool。 Alright。

 so let's think about why it should be log and insertion。 Okay。

 so if you know the three ingredientsvaris now， well。😊。

The black height in any path is the same right so let me let's think about that so if I have the worst case here oops。

😡，Think about if I had an arbitrary number of black nodes， like if I had just a bunch of black nodes。

😡，The maximum number of red nodes I can place on this path is just putting a red node in between each why because I can't put two red nodes together right so if I fix my black height。

 if I fix the length of black nodes on any given path，😡。

Any other path in the tree can be at maximum this length。

That means that that's an equivalent way of me saying the worst case for paths in the tree is twice as long as the shortest path。

 or rather it's at twice as long as any other path in the tree。😡。

No plus one because you can do this thing here， you can add this one here。

Is that relatively clear to people so let me let me try to say again right so if I if you if I give you an arbitrary tree。

 I tell you it's a red black tree， there is a black height right there is a height a number of black nodes on any given path。

😡，Then if I want to make the worst if I want to think about the worst case path length。

 given that black height， at worst， it'll be me， it'll look like this。😡。

No other path can be longer than this is everyone， Does anyone get why like no other path can be longer than this if there are exactly three black nodes。

Okay， so at worst we're looking at two times that length and I believe that we can come up with a bound。

 which is。But the depth of the tree。Is upper bounded by。Two logs of two。N plus one。

 this is not like a math fact you have to be able to memorize or anything like that。

 but the point is that it's roughly two times the log of the tree， which means that it's like。

 you know basically look at this as like an upper bound that's constant in log。

 which is what we usually like to see right like usually our depth ideally is less than equal to log of logs of two of n in the first place。

So this will be a pretty good bound and if we have this thing true。

 then we can do a red black thing okay， oops is everyone clear on this？😡。

Because these invaris are important to know about because the rest of our lecture we spent not on thinking about the invariance。

 well， but with preserving them， really， which entails thinking about the imvariance。😡，You know。

 whatever， okay， cool， all right， so if we're assured that we can do logarithmic cost operations。

 let's move on。😡，So I already told this to you but yeah equivalently at twice the length of any other path。

 all right asymptotically， this will be loggged。😡，So how do we maintain invariance， let's do it。

That was a short section one Section two is going to be more detailed。

 How can we make sure that those three invaris are never broken in our tree Our mantra for today is going to be。

😡，Break the invariance， then restore them， break the invariance briefly and don't try to you can sort of apply this rule to the rules in general in your life like break the rules briefly。

 but then then don't okay which works sometimes but when we maintain these invaris basically we're going to want to be able to think about each of the functions like insert and look up specifically insert inserts the big one。

😡，Okay， so if I want to traverse in a red black tree。

 I can't avoid having to traverse the path that's the same as in the BSC right so for instance。

 if I have。😡，This is a red black tree。Well， okay， it's 0。5 okay， if I want you to insert， say， okay。

 you know， I'm going to change this。Three and two。If I'm given a given tree。

 even if it's rare a black tree or a regular tree when I insert I have exactly one choice of where it codes right because I if it's a BSC I can't avoid。

 oh if I'm here it has to go to the right of that and if I'm inserting one it has to go to the left of this and if I'm inserting one it has to go to the left of oh I'm empty I have to put it there so when I'm want you to picture in your mind is for any given tree for a given key or're inserting there is a destined。

😡，Position that you should put in it， okay。But and that might mess up our invariance。

 but only briefly because we can we don't have a choice of where we put it。

 but we have a choice of what we do with the tree afterwards that's called a balancing scheme so we'll show you how we do balancings right so。

😡，Self balancing trees are where we're going to be able to put it in the tree。

 but then we'll move the tree around a bit， we're going to move some of these nodes so that we ensure that the tree is still balanced afterwards okay。

😡，That's the idea of a self balancing trait， okay。😊。

If I were to insert into an arbitrary red black tree， I have a choice right I have to put it here。

 right I have to put the one note here， but I can choose to color it either red or black。😡。

And that's going to be a very important decision because what decision we make might induce a violation。

 like suppose that this node was read。😡，If you recall by our second invariant。

 I can't have a red node and having a red child， so I can't。😡，Color this red。

I'm going to show you this in pictures a little bit here。Oh yeah。

 I'm worth not also that this this slide deck was is 2000 lines of blood。

 So I hope you appreciate the the colorful pictures。 analogologies。 Okay。

 so suppose I have this red black tree。 And let's first verify that it is indeed a red black tree。

 right， so。😊，What is the black height of this tree， Well，1，2。And then I reach empty，1，2。

 and then I reach empty。One， two empty， one， too empty， bh bhlah， blah。

Do you see how on every path from root to an empty node， I have two black height， so that's good。

 and then does any red child have a red parent here？Just red。

 we only need any two notes cannot not be atop each other and both be red that's the only color restriction other than the black height one。

 I guess。😡，Okay， so this is a valid red luxury。😡，And again。

 if I wanted to insert one into the tree I have no choice。

 there was exactly one place where this it makes sense to put this node right I can't put it to the right of two I definitely can't put it to the right of three so there's a destined place I must put one but I've kind of colored it this kind of strange stripy red right because what I'm saying is what do I color this node right let's think about it so。

😡，Either red or black， Well， does let going see a problem here， What happens if I do black？

Is there any effect whatsoever？If I insert at black， we're going to break the black height invari。

 yes， so we don't want to do that here， we can't do that here， it's impossible。😡。

If I insert at black here we go， black height invariant has been broken。

 red chawl invariant is good though， but we see on this blue path here versus this magenta path。

 the black height is different， three versus two okay so let's not insert at black let's try to insert nodes as red nodes okay in general all right。

😡，So if we color the node red， we're going to get this tree and now we can see， okay。

 it must be the case right， I can't have affected the black height of my tree if I inserted a red node right so that will be a general statement we can't possibly affect this imvari。

😡，If we insert that red， and hey， it looks like we're good here too because the child does not have a red parent。

So does that mean that we just insert always our red， we're all good， no problems ever。

 and of lecture， what do you think？😡，There's a。Its like an hour lecture lecture indeed。

 this is not the case because why I want to hear it from you， what is the problem here？

What happens if I insert in general as a red note always？😡，I got two invaris， I got well。

 I got three invaris， but I got two invaris that matter to us right now because we're assuming that we're inserting right。

 if I insert always at red。😡，If I have this tree， for instance。

 and you can take a second to verify for yourself that it's a red black tree well。😊。

If I want to insert with a key of two， let's do the same thing I just said。

 which is I'm always going to insert at red always， well。

 we're going to have an issue here right and actually let's let's no。

 I'm going to make you do it All right， you already saw our work goes， but let's insert two。

 Sha it out。😡，Left。Right， left well， okay，2。 Okay， so let's color it red。 Well， red border again。

 he didn't quite do well enough because look at that。

 We have this red note here signaling a red red violation。😊，Red red violations are real bad。

 Border control control doesn't like it when you do that。 So let's try to fix this。

 Let's try to make sure we don't get this， but we want to make sure that we can still insert at red。

 So what we're gonna to do is the black heightened variant。

 we try to always keep we're always going insert at red so that we maintain our black height and variant with the caveat Sometimes we will break our red child invari We break the rule。

 but then we restore it okay so we're gonna to be okay with breaking this red child imvari because what we're about to do is fix it All right。

😡，So how do we fix it well？How well， this tree doesn't look very good to me in the first place。

 right， like look at it。If I wanted to look up like five I would go one。

 two and if I wanted to look up two I'd go twice that length here like this doesn't look very balanced and to be fair this is like fine because it's a very small tree like imagine if feel it was like slightly more elongated right if we had three rain to rewrite this tree however we liked。

😡，What's another scheme we could come up with for how it looks？😡，DoesZ anyone have an idea here？

Like if I could make this tree still have the same data。

 but weigh the data out in a little bit different of a format so that's more friendly to what I'm trying to do here。

 how would I do that， how would it look？😡，Yeah。Right because it's kind of interesting where like three is or two is between yeah two is between one and three right but here we have to see the three before the two which is kind kind of silly right。

😡，So let's try to fix that if I had free range to transform the street， I'm going to say。😡。

Probably we would produce this one right so let's take a look see Emma the four and the five are the same。

 but what I've done is I've taken this one，3， two， I tossedss the two up and I put one to the left of it and three to the right of it and I had to do that because of our BSC invari right？

😡，So。Here we're going to put it at  one，2，3， but notice I've taken away the colors I've taken away the colors because if we maintain the same colors as it was before。

 well actually I think we'd be fine in this instance。

 oh no we wouldn't it would be a sium red and red， but I'm going to say that right now we have free re to recolor it however we like we're going to do a rebalance and a recolor。

😡，and this is kind of an interesting case where we can think about how we want to recolor this。

When I was thinking when I was writing this lecture I wanted to write it in a way where you could almost like rederive red black trees by yourself without like me telling you oh this is exactly how we'll do it this is one of those places where I kind of have to say trust me what we're going to do is we're going focus on these three nodes okay we're not going we're not going the tree doesn't have anything else in it don't think about it but these three nodes are the key okay。

😡，This is what I call a triad right so if I had this。😡，For an arbitrary。

 I don't care what the keys in the data are， suppose that this is like a thing in my red black tree。

😡，What are the possibilities for what I could color it？What do you think。

 what are the combinations that would work？Yeah。So let's think about that， Phil actually， oh okay。

 oh yeah， all black is fine， all black is fine。In isolation， all black is fine。

But I'm going to say that we're going to discount that in the context of what we're doing。

 but you're correct that wood work in general， I saw hand here。😊，我。Read to them one， yes。

 so you're saying this and lets stop drawing those out。Yes， that's true。

 that is one thing we could do。What's another one？ERR， I like that。

And are there any other side I really care about here？No that I care about least。

 I don't really care about that one either， but it's also worth not that that's one thing。Okay。

 actually， no， no， this is， it's good to count this up。 Okay， so let's say these are the only ones。

 I'm pretty sure these the only ones， right， because we cant。 And if you're not not clear with this。

 we don't want to break the red， red violation， right， So if I color this red， these can't be red。

 so on and so forth。 So when we focus on these three， these are a pretty easy case。😊。

But what happens if I transplant black， black black in here？I get。A violation。 but how。

3 is not equal to 2。 Well， that's， that's true。 But oh， no， I see what you're saying。

 I thought you're talking about the nodes。3 is not equal to two in terms of。The height。

 the black height， if I do black， black black， now I've introduced one extra black node on my way to the empty right And if this was the case that like every path had the same black height earlier。

 well now I'm going to be in trouble， right。😡，So let's not think about this one。

 but these two both are pretty good right， and these will introduce if you think about me transplanting either or actually you don't need to think about it because I did it。

😡，So let's do it this is one red root black children Okay that's one of the triads we can do and we're good in this case I'm going to tell you right because look at this I have one。

 two da da one， two one， two right so if I work through the past I see that they're all of black height too and I only have red one red node in the whole thing and it doesn't have any red children okay so we're good。

😡，Good on black light。 Good on red children， but。And there is a but I'm going to push back on this idea for a second okay and we'll see why oh and actually I'm sorry this is a good one let's say good。

 but the next one works too and I'm going to push back on this one All right this will still work in terms of our invariance。

😡，For this tree， but I'm going to show you very quickly an example where this is not true okay。😡。

Does everyone agree that both colorings， this and this are good for red boxes trees per this particular tree。

😊，I can go back and forth。YeahAll right， I turn my slides back and forth。

Let's insert again on a tree that looks pretty similar。

 but here's the kicker it's got another node in it so looks like this right here's the new node that I've inserted into this tree and now we want to insert to yet again allright so we're gonna to go left right right left already already this and it's going to end up here it'll be destined to end up here but now we've got a red red violation because remember when we insert we insert at red so we need to balance again by the same thing that we did in the last slide okay I'm just doing the exact same thing but now zeros along for the ride。

Well， if I wanted to rebalance this， I would want to do the same thing I did where I moved two up and I move one left and then three say there。

 right that would be my ideal。😡，But note how zero is in the equation now。

 it was easy to think about how we wanted to reformat the tree when zero wasn't here when it was just the。

😡，But what I'm going to say is all we're going to do is we're going to keep the relationship of zero and1 okay so when I move two to here and I move one down。

 I'm going to keep zero as the left child of one and in fact I'm forced to do that because of the BSC invariant okay。

😡，So what I mean by that is we're going to have this right I have the same triad。

 but one' child is still zero as everyone clear on this。

 like we only really have the choice to do this here。If we want to rebalance in this way， okay？

So I have no choice but to put zero there， and then we're going to have the same choice where we can color。

😡，And we'll be one of these two， but let's try it well。With the red children。

 now I've induced the red red violation easy， because look at that。One has a child， which is0。

 which is red， because zero was along for the ride because I recolored one from black to red in the transition。

 right， because when I went from。Hereear to there， right， one used to be black， now it's red。

So this coloring with this schema is going to be problematic。😡。

We don't really want to do this because it's not going to be able to work in the general case。

But the red black black is looking pretty good。Right and in fact， you should be assured that。

Here's a question for you Is it possible Imagine there were other children here right can you visualize sort of like if my tree here if we if my original tree had had children of zero or sorry。

 children of three or two or whatever or just three actually they would be along for the ride two when I rebalance。

So there might potentially be children here as well， but if I color these two black。

 can I have a color violation from this edge the same way I had one here？😡。

And I'm heavily leaning into that the fact that the answer is no。 and if the question is unbounded。

 I'll expand more in a second。 But what I'm trying to say is that if you rebalance such that there were subre here。

They would have some color， color it red， call it black， but these are black。

 and black has no restriction on its children， the color of its children。

 So coloring leaf nodes black， coloring nodes black can never induce a red， red violation。

 It can only ever induce the black height violation， but。

We see that this is actually maintained and it will be maintained， yes。😡，2的。Does different。

4 to5 is different than 40。好。然后。One，2 empty， one， two， or is say one two empty。

Like so like find zero， it would take the approach that。Well， in this small tree。

 it looks like a big difference。And again， like like we could construct this tree in a way where the worst case path is going to be twice the length of like the right path。

 for instance， we could have this like scaled up by like an arbitrary number。

 but we're not bothered by that because logarithmically we're going to ensure that the depth of any given access is still at maximum the same figure I gave which is constant in the logarithm of the number of nodes so like like I'll reiterate again because it is worth knowing but like under the scheme the maximum depth on any path of the tree is less than equal to function of two logs of two of n plus one。

Is， and you can。If I have time at the end of lecture， I'll explain why this is。

 but it's not super important， you can just accept that like if the path length is at maximum place length of any other。

 you can imagine the cost is not too bad and it will end up being algorithmithic。😊。

I haven't done AL trees in like five years， but probably yes oh yes， AL trees。

 I believe the difference is like one or two between each given zero or one between the given nodes。

 Yeah， AL trees is a little bit more strict but you don't need to be because red box trees in practice are very fast they're very fast but because we don't really care about paying an extra two times cost every now and then if our maintenance work is less Yeah so in practice these red box trees are really good And if you don't know what an AL tree is good。

 it implies you probably didn't take 122 or you weren't paying attention in 122。

 which is also a fine outcome All right so let's move on shall we all right so what I'm trying to say is we have we have a survivor competition right and at the end of the at the end of the competition only this guy gets the。

Marshmallow I have never watched the I don't know what I'm saying the point is that we voted all the other ones off the eye All right。

 so red black black is gonna be our go to triad for this scheme and you should be assured that like this will maintain both red height or sorry both red children and also black height okay and we can think about that for a second but' you can also just take it on my word for now and then we'll see more examples in a bit okay。

Okay， we're done。Are we。Because I don't need you to point out the example that's bad button I show it to you all right。

 so our scheme will all so let's recap again okay， step one。😡，Insert the node。According to the BST。

According to the BST property， a given note has only one place that's destined to go in a given red black tree。

 so first insert it according to that two。😡，Color it red。Why。

 because we don't want to break the black heightened variant。

 and we would definitely break the black heightened variant if we colored it black。3。Re balanceance。

If。If we've just inserted a red red violation with this insertion of red。And when I say rebalance。

 I mean like if there's a given node I have that I just inserted my new node to。

 so this is the new node。😡，And this is definitely red because I said we inserted at red。

 this could be either black or red right， well those are the two cases， but I'm if it's black。😡。

I'm not bothered， I don't really care right because I haven't broken to any laws here okay。

 there's no rule that says a dog can't play basketball， but if this is red。😡，Now I've got a problem。

 all right， now the feds are after me， so I got to rebalance okay。

 so in this case we will do the rebalance。😡，But there's still problem here。

 I'm going to show you exactly what that is， okay。But before I show you how that is。😊。

There's also we also have to do some casework， right？😡，I want to think about red， red violations。

 like the different formats I could have inserted this into， and it turns out there was only four。😡。

Okay， let's think about this one， all right？Imagine that this bottommost node is the one I just inserted。

 okay？😡，And you should be assured that if I just inserted it and there's a red red violation。

 there's only four cases， why， because I can not be the left node of this guy。

 the right node of this guy。😡，Were this guy itself？Should have a parent。

 We might also be at the root， but I'm going to save that for for later。 Okay。

 so like assume that we， we have a grandchild， a grandparent， if we have a grandparent。

Can this guy be red？Is there a case where I read why， why can my grandparent。

 after I've inserted this guy， the guy at the bottom， not be red？Inductive leap of faith。 Yeah。

 yeah because。In particular my invariance， which I already work so hard to preserve if I'm inserting into a red black tree。

 that means that this thing never existed and this was the way it was before I inserted。

 So if this was red and red， I wouldn't have inserted it into a red black tree。

 I would be breaking my precondition and I don't care about what happens when I insert into a red black tree。

 So assuming a red black tree， this must be the picture I must have a black grandparent and my and we're assuming that we're talking about red red violations So if Ive read red violations。

 I only have these two cases or four cases。😡，Any questions on why these are this is an exhaustive casework on what could be happening。

 the state of the world right now？😡，Okay， if you trust me that these are all the cases。

 we're going to solve them， okay？😡，I'm going to say that right now。you know。

 given three nodes with these ways， it'll always be this and then we're going to fix it with the rebalance。

😡，So how can we do that well？If ISo assume that we have all these cases here well。😡，I call them X。

 Y and Z， I call them X Y， and z because that's their relationship in terms of the alphabet。

 so I don't care about what they are， but they're related as x is less than y is less than z。😡。

I'm going to tell you that right now the way that we solve this is we turn it all into the same looking tree We're going to turn all three of these cases into。

😡，That guy。Where x is on the left z is on the right y is the root and then one， two， three。

4 which are subtes that are along for the ride are related in this way okay this will be the canonical rebalancing scheme and please ask a question if you're confused over why this should be valid in terms of preserving red black tree invariance okay but this is kind of an extension of what we saw with the previous example I'm just saying in general we can do it even if our insertion looks like this as opposed to that。

😡，Yeah。Yes，That's the case that we're going to be breaking in a second year。

 that's the case that's the bad case， but for now。We're going to push our problems up in a sense and what I mean by that is like。

😡，Yeah， we're gonna。We're going to solve our problems locally okay and we're going to break it for the tree above us。

 but the the great thing about this is that the guy above us now it's their problem and they can go solve it and they will solve it and then recursively we're going to keep doing that all the way up to the root I expand it a little bit okay。

😡，嗯。So we can only ever produce this and then this is going to be impossible to produce a red red violation for 1。

2，3，4 by again， my previous logic， which is that black or red。

 this does not induce a red red violation， neither does this induce a red red violation and also if we do this based on the scheme。

😡，If you if you can' do the casework， like  one， two， three， four。

 all of these cases they have exactly one black node to either one， two， three or four， right？😡。

That means that if we preserve that there's exactly one black node on the way to  one，2，3，4。

 we're good， right？😡，And here we have， because this is black， this is black， one， two， three， four。

 okay？The black heights invariant being satisfied here is a little more subtle。

 Does everyone get that like one black node before。

 one black node after I ensure the same total black height of my subtes， yeah。Yeah。

Because we only have one black grandchil or grandparent。

 there's only one black node in this given rooted subtre that goes to any of these subes。😡。

So we just have to induce an overhead， literally there's a black node over our heads。

 and then we'll satisfy the invariant， all right。😡，Cool okay。All right， so let's move on then cool。

 so again， we go back to this idea of are we done and then see identified we are not。嗯。

Before I okay so notice how this one goes right， the grandchild goes our left here rather and thus if we wanted to turn this and this into that。

 you can visualize we kind of shift it right weta turn it right because Z goes to the right here and y stay to the top or here we kind of like shift right where Z goes right again right so we call this a right rotation I'm making this distinction because these are going to be two different functions so this is what I call right rotation because we turn the tree right to go here to the nice tree that we want to get。

And I call this a left rotation because this is the other two cases where I turn it left and x in particular goes left。

😡，And then we produce the same tree， Okay， right rotations and left rotations。

 and it turns out that we're going to。Implement functions that are named the opposite。

 So elect rotation corresponds we function called restore right and we'll see what that is's not it's not my choice。

 Okay， this is how it usually goes in this course。Okay。Cool， so let's do the other example here。

I've got this tree。Which is the same as the previous one， but now the root is red。😡。

And let's insert two。上有。Where do I go。Left。Right。L so i'm going to end up here oh cool I got it right if I start two Im destined to reach this place and as before we color it red immediately。

😡，And then I want to rebalance why I identify these three nodes。😡。

Right because I'm in this case where these three are the shape of my red red violation。

 if you look at it， it should match the four pictures I gave you earlier in particular one of them。😡。

If I rebalance according to what I just said， I shift it left。

 so one goes left here to occupy zeros place， three states where it is and two goes up。😡，Okay。

 so now I've got my same rebounds， if you follow me。

 this is exactly how I said we would do the rebalancing scheme， but what's the problem？😡，Red red。

 oh my God。We have a red red violation here and you can see this edge is red as well to signify that a red child in variant is messed up to put it lightly。

 okay。But here's a neat note about red black trees。

 and you should be able to assure yourself with this。My root can always be black。

If I have a red root， I might as well not have a red root， okay？Which。

I don't see a point in not explaining to you， but like if I have like right because my root is the root of everything。

 which means if I color it black， I add one to every black color。😡，But I don't care。

 and if it's black， definitely it cannot induce a red red violation。

So we're going to color it black because why not？😊，Cool， now we've got a red black tree。

And that's for free， but here's the question， do we get lucky by this。

 did rebalancing once and then happening to end up at the root。Just make us get lucky。 Well。

 in a sense， we're gonna have to keep doing this because this might not have been the root of our tree right This could have been the subtree to a bigger tree in which case we need to think of a way to solve this problem if we consistently end up with a red red violation after doing our burstary balancing。

😡，So the idea is continuously rebalance， push our problems up if I have an insertion at some subte here。

 okay I can rebalance and then my root of that will be red right by what I told you this rebalancing scheme is always my induced subte my new subtree is always having a red root which might be subservient to a bigger。

😡，Red node， which might be subservient to an even larger tree。

 But we're going to push these red red violations up every single time by taking this。

 treating it as a red， red violation again。And rebalancing here。And then that in turn。

 might induce a red root a little bit higher up in which you might have to rebalance。

 but the key here is there's another invariant going on， which is the invariant of our rebalancing。

 is that the red red violation always goes up in the tree。😡，And if our red。

 red violation always goes up in the tree， eventually。Willll end up at the root。

And then we can either we or we don't have to rebalance up that bar， that's also a possibility。

 but if we end up at the room。Then we just colored the root black and we're fine。 Okay。

 so there's kind of like four invaris floatinging around here。

 the invariance of the red luxury and the invariance that we have when we push up our problems， Okay。

 remember， when we have problems。😊，Hand them to your rehearsal call。 They'll deal with it。All right。

 or your caller， maybe all right，quiz time。Get up All right。

 let's move on what we're gonna to do is we're going to now that we're a shirt is everyone like okay。

 temperature check who is good on the theory， like like， yes， we're gonna do things in this way。

 I just need to see like theoretically and then we're code like up down left like the theory makes sense invari how we're going to preserve them how we we might break them。

😡，And then 70% of you are in the abyss and not present， yes。Indeed， yes。

 we'll see that in a second here。 Okay， cool， sounds good。 All right。

 let's implement red black trees。So I'm going to formalize this notion of red black tree insertion by giving you a new notion called an almost red black tree and an almost red black tree is almost a red black tree in the sense that it has the same properties。

 but。😡，Its root may be red and a child one child of that root might be red。Okay。

 that means that we'll see， that means that an ARBT。😡。

Is allowed to break the red child by invari a single time at the root。 So this。Is。Well， yes， well。

 no it's not。 you have three have to add this because oh， this isn't either please， okay。

 this is an ARBT。All right， see all these restrictions on red black trees。

 it's hard to even construct the one that's like pretty unbalanced right this is an ARBT because I have a red red violation right here。

 okay？😊，And we're going to see why that is because this invariant is that we're going to push these ARBTs up。

 we're going to make it such that the subtrees are continuously ARBTs until the root is， okay。😡。

Here's our specification for these two functions we're going to write called restore left and restore right。

If I and remember， I call restore right on these conditions， okay。

 I call on these to fix the red red violation， so restore left for these upper left two and restore right for these upper right too okay。

😡，Restore left takes in a red black tree， and you must have that either this is a red black tree or it's a black tree where the left child is an ARBT。

Because the left child has to be an ARBT because that's the thing we're trying to fix right that's all it requires so we require this condition and we restore left because the left child has to be an ARBT all right and the right child has to be a red blood as well。

😡，But I ensure that restore left always gives me a red black tree okay and you should this should follow because I showed you that if we rebalanced like we did earlier。

 we always get a red black tree at the particular subtree we were at but that might not be true generally up because we might have a red red violation okay so is everyone clear on like why again。

 like is everyone clear on why restsoring left or restsoring right as I previously said should produce an RBT？

😡，And you agree that left here is an ARBT and the right here is an ARBT。Okay， all right。

 so if that's true， let's implement it。😡，Or actually it's not implemented first first notion which is just that oh yeah when they implement restorelect restore right we are sort of like kind of ambiently inside the puncter like I haven't defined it for you yet。

 but we are which means that when I when I define restore left and restore right I'm going to be able to say oh those aren't going to be visible to the moduleular user at the end of the day all of the things we're doing right now are hidden behind the curtains and then some you know program in Cambodia two months from now is going to thank us profusely for our nice red blacktre library okay but they're not they're not going to know about restore election and restore right all right。

😊，Cool， okay， I wasn't supposed to show if you had。 Let's do it。 Okay， so。😊。

What I want to do is I want to put in code this idea。😡。

There's a two of two word phrase I'm looking for of how I'm going to do that， which starts with。

P and ends with matching。It's called pattern matchingshing。You see。

 I don't think that's a word what we're going to do is we're going to use pattern matching to be able to look at this can somebody actually write to me what it sounds like to express this subt。

😡，In words and it might have it might have a subre so I haven't label， but one， two， three。

4 are still around， Okay， how would I write this in pattern matching form？😡，喂。

Black blue red red I Yeah， well， yeah， there's a few things in between。 that's the idea， right。

 So black of two children and a thing inside。 And you said that red because my left thing is red。

But then this guy I'm focusing on right now also has a red left tree， right？Okay。

 and then now I'm here and then these are whatever right I don't really care， but I do care。

 but I care only to give them names， so let's call it x1， let's call it way。😡，No。

 I think I' called it T1。X， that's it， and then T2。So that means that there's going to be a T1 here。

 T2 here and x is my。😡，No， N。And then， well， okay， this is one subree。

 Then this red subte has itself an entry。 Let's call it Y。😡，Okay， and then now we're here。

 so this has a right entry， let's call that T3。😡，And now this is a tree， right？

So I need to resolve this black one right because the black needs another middle and the right。

 so we're here， so the black entry call it Z。😡，And then we'll say that this one's T4。😡。

And if you equals and if you think about it， and let's see whether or that's painful to go back all the way to show you well in retrospect。

 I probably should have put it there。Yeah， there we go。😊，See this one，2，3，4。

 so with these subtrees I have here this is the exact same thing X Y， z，1，2，3。

 but they would correspond to t1 through t4 and XYz here okay that's how we put it in panm form。

 but we want to get here， we want to get to this tree。😡。

How do I write that in a pattern matching form in SL？Yeah。对。Thanks so like keep on。Did you say T3？

Excellent， excellent， good。 Okay， yes， that's exactly how we put it in Pederme form。

 and we need other people to start gaining these high choose。😊，Os， sorry。Okay， and actually。

 you know， I always do this on the board， but like my my slides are strictly prettier。

 but it's because I want you to like see me writing it and like think about it as we're doing it。

 which is a shame， but not back， back up， back up。😡，We have a nicely colored here。😡，Black， red。

 red for black， red， red， and then red of black and black for the diagram that's no longer on the screen。

 Okay， so this is what it looks like。😡，Okay， next up， let's do the next case， what about this one。

 who else wants to tell me how I should write it？😡，其咁咁讲，系系咪话。Oh sorryrry on right。Lets me why。

I guess why？Or。Did no red。诶。迟超。Y， T3， Okay， and then z。诶 keyboardboard。Exactly。

Keep in mind the friends it's hard to keep track of， but basically Black root has a red left child。😡。

I think I need I'm missing a appearance here。他是。One two the yes， thank you。Yeah， mind of friends。

Unfortunately， there's no syntax highlighting on a blackboard if we that outture。

Black root with a left red child， which is this whole guy。

And then that thing in turn has a red right child right and T1 x Y z actually it's going to be a theme that like this is always gonna to be this order T1 and then T2。

 T3 T4 and XY z somewhere in between there Okay it kind of actually has to be for the for our BSE scheme to work and I'm going to say what is the equal to well I'm not going to write it up for you because。

😡，It's this。If we wanted to， we could isolate that and write a helper function that does it。

In the old notes of this course， they didn't do that， so I didn't feel the need to do that， but yeah。

 same。It would have to be inside， yeah， because we'd have to do in each case Scous。

And that's this to this， right， or I do have a picture for you right， for about。😊，That's not to that。

 right， by。Well， those are my two cases， that's it。

What I'm going to say is we're going to call this function a lot and if it's not a red red violation。

 I don't actually care so to make things super clean，😡，A variable called other。Equals other。

This is a function that pattern matches only these two trees。

And then otherwise it just keeps it the same， it accesss to the identity function。

 and we'll see how this works later yeah。😊，It will make our future code a little bit more clear。

 We could definitely do that。 In fact， you could argue that maybe it's just as clear， but。

It's a little extra work to do all for ones。But I think it makes code look a little bit nicer。

 but yes， you're correct， we can pat much on all four at once because they're discrete cases。Yes。

 okay， cool， alright。Let's move on。First of， let me tell you we're sort right。

 we're going to do this case first， like so B R and then R left。😡，And if you don't have the picture。

 I'm not sure if you're going to be able to do this to school。

 but anyone want to volunteer for this one。Yeah。我 so black。Oh sorry， I went went too deep。 Yep。

 Ukraine Z T4。And then I think another one。Well， equals same again。

 right because we always go to the same target。😡，I chew as promised。well啊哈。啊。

It's called meta programminggramm anyway。One last one it's。This case， black， red， red， all right。

 wants you give a shot。re can定。😊，No， someone else I ever heard from。F。😡，Yeah。Are you re up theides？

Are you reading up the slides， Okay， cool。Why， which is the middle one yep。

And then a right child is again red。And let me just finish it off here later。2，3。One，2， three， four。

Equals。There's like just enough room for this to be uncomfortable to do with a Jesus there's just enough room for this to be uncomfortable to do at like my normal writing pace。

 but yes， it's also on the side so。Well， we already did over so left。So it's this right。

 black and then red， and then the left of that red is red， and then we go the same thing。😡。

In this case， black， but my red has a red right child goes here okay， refer back to this。

 it looks a little nicer than what I have on the board because it has the highlighting， but yes。

 okay， equals same。😊，All right， now for a high chief who wants to tell me this case， no。

It's going to be symmetric， we're going to do other， goes to other again。

We don't care about cases that are not red， red violations at the root or at the child of the root。

 okay。Oh， another reason for that。😊，It makes the specification of restore right and restore left nicer。

 that's what I was thinking of let's look here。restoretor left in particular takes in a T where the left child is definitely an ARBT and a right child is an RBT if you combine both now you're likeT is a black tree。

😡，Where the left child is an ARBT and the right child is in RBT or T is a black tree where the right child is in AB it's gross casework。

 I think that's I think iss the point， the specification is cleaner with separation concerns。😊，Okay。

 that's the side， anyways。Cool， this is how we write R restoring functions。😡。

And now I have the privilege of erasing all of them because we're going to move on and we're going to do insertion Okay so okay。

 we are equipped with these restoration functions now。

 which means that we can fix these red red violations。

 but we got to do the insertion thing in general okay and here's how we're going to achieve it okay when we write our insertion functions。

 we're going to run two functions remember that thing about。😡，How when we induce a red red violation。

 we move it up， but do you remember that example where eventually we had a red red violation at the root like eventually after our rebalancing it looks like this and then we were like oh。

 it's red at the root so just color it black。😡，Because we only want to do this at the true root of the tree where we have to isolate this into a different function。

 so we're going to write a recursive function called ins that does like the regular insertion rebalancing rehecursively and then a single wrapper function on the outside for the entire tree。

😊，Whose role is literally just a color of the root red or a black？

I'll show this you in code and then it'll make more sense。

 but that's the way we're going to do it because we can't do it in the recursive helper because then the recursive hit helper would do it in every century。

 but here's how we'll do okay。😡，So if I want you to insert。Well actually no sorry。

 I'll show you the schema so first of all， these are our trees our functions。😊，To insert。

 I take a key in a value and I take a red black tree。

 and this is the true insertion function it will ensure our invariance hold， I get in an RBT。

 I get out in RBT， but with the new entry。😡，The ins function is going to be the recursive one ins is going to。

Do the same thing where it takes into RBT， but now。It might return ARBT。

That's why we introduce this concept because remember when I insert I leave I color my root red。

 which means that I might have a red red violation。

 okay or rather I color the things left my red yeah okay。

 so ins is going to satisfy this specification and we'll use it so that eventually at the very end insert colors the root to the true root。

😡，Buck。😡，系。啊嘛。And this is what it'll look like， okay， so insert is going to be。😡，First。

 I have this insertion function， which I ins function， which I'm not going to define pre yet。

 we'll do that in a second。😡，But when I run ins， I get out either a red tree or not a red tree If I get out of a red tree。

 I just colored the root black。 Does that make sense pictorially as to what we did earlier with the same example where I inserted。

 I rebalanced and then I colored the root black Sam deal here。

 That's the only reason why this distinction exists because that's what insert does。😡，Let's do ends。

 which is going to do the recursive thing。😡，Okay， okay。

 and one note also I'm going to not have it taken K comm by I amm going to have it taken K come B。😡。

Whatever， all right。I said I wasn't going to， I think that's the type of， but whatever， okay。Well。

 what are my cases？I'm not doing insertion of a tree， but what do I do， I immediately pattern match。

😡。

![](img/01f42000cdf61919969ac4bb22a1b8f9_1.png)

Tell me what this is。Red， why red？We you're only putting in red， exactly。So red of empty。

K come and B。Empty。And then now I've got a bunch of other cases。 Okay， well， I got two cases here。

 right， because this is a red black tree， not just a tree。

 so I can insert into a black tree or a red tree。 Let's do the black case first。😊，Black yes。

 and then we're going to call it。阿 l。K， prime， be prime。R。Well it's a BST， don't forget that， right。

 so I want to do the same thing I did before。😡，Which is what？I'm going to compare right。

 and we're going to use the ambient key that's floating around I mentioned earlier So case key dot compare。

K and then K prime。And this is going to get long。Okay， if they're equal。

 well I just replace this guy right that means that my entry should live at my root。

 I don't really need to do anything else， so I'm going to say this。😡，K comma V， which is my new guy。

R。😡，Yeah insertion we're replacing oh yes sorry I guess it wasn't clear because I said earlier at most let's do insertion as replacing in the scheme yeah it's nice。

😊，Actually， yeah， you definitely should have to replace because otherwise you'd have multiple entries in the same dictionary and if you put it lower。

 look， imagine I I had。😊，Yeah， yeah， yeah， so we want to replace， yes。嗯 ok 。So equal， I just do this。

 is it possible for this to not satisfy my specification。

 like could I have made in not RBT from this？😡，No， because I didn't touch the colors。

I just touch the data doesn't actually matter in these case are literally the same， so no big deal。

 okay I not to worry about that， but less is interesting。😡，And then here's what， okay。

 so in intention， what I like to do， I would like to insert into this guy， right？😊。

So let's say let's keep the same tree。Let's keep the sand tree。With a conspicuous space。

And then we're going to keep our same entry as here，s。啊， ok 。I'm going to write。

I think it's going to be hard to see otherwise， okay。Okay。Okay。

 I put K prime and V prime and then R here also， I don't touch those， all right。

 if everyone's clear my forehead。But remember what insertion does。

 which it might reproduce an ARBT this guy might be an ARBT， which means it might be right right。

 a red red or it might be red gray。In which case says's bad burs。

 right now we've induced a red red violation。But what do we have that fixed is red。

 red violations that are near our root？啊三就行。We pass that into restore left indeed。

 that's why it's called restore left， we call it in the left case。Wow， there was a point to that。

With a conspicuous space in the list。Okay， cool， and then let's do the greater case。

 but the greater case is going to be pretty similar。😡。

I think I'm going to finish just on time here Okay， again。

 I'm going to do this thing where I do black。😡，And this time， I'm going to。Undersco， underscore。

 okay？Undersco， underscore。And then we're going to do ins。K prime， B prime， Oh sorry。

 that's included。 Ama ins。K comm a V R。Makes sense to for everyone。

 this is me inserting into the same tree heaping up the same， and then what do I do？

What Michaelchael。😊，Retor I indeed。And it would be it would be。

Be wasteful for me to call restore left here right because I won't do anything by my invariance。

 restore left， this is not a valid trait for restore left。😡。

R Wright only deals with the case where this guy produces an ARBT， same invariance。Cool。Okay。

 is everyone clear on why this should fix my？Rebalancing why I should this should make the rebalancing work because again ins can produce an ARBT。

 but because I produce it here， I end up in the case where I now satisfy the specification for a store right where my child in particular my right child could be an ARBT if it is I rebalance it if not I keep it the same。

😡，These preconditions slide neatly into each other yeah。The red bilate root。嗯。

That's going to be difficult for me to remember exactly， but it'll look like this。Yeah。

 it looked like this。And we insert this and the other cases all matter okay。

 but I assume there's something else that makes this an RBT so do you if I have this tree and the other associated metadata and I inserted here。

 I have a red red violation here I have a rooted subree that's like one of the bad cases here right because this is red so I produce red。

 black， black。😡，With red。So in this case， actually where we are here。😡，This is our。Ins， okay。

 this is our red， and we insert into this and cause it to be R R。 Then this guy one step up。

 we were sort left out to get this guy。😡，系。That's the idea， okay。U yeah。Yes。

 and the it may return AirBT， it doesn't have to okay。😡。

And I'm going to do it partly on this board and by that again。

 I'm going to literally write this case out here。😡。

But it looks similar right because red is just like pretty much ailmorphic two of my black right。

 so we do this。And now I've got to erase this stuff on this board。

 but we're going to do the red casess。😡，Now here's a question。

 how complicated do you imagine this is going to be？

And I realize this' is actually going to be a hard question to answer because it's not all obvious。

 but what we're going to write is same deal。😊，I write the same stuff。Where I compare K and K prime。

So we're going to into an interesting case here， let me just up a stage for you L。Okay，Com on V。

 I replaced the entry here。Otherwise， if it's less。Here's I'm going to claim， all right。

For the restore left function I just erased， unfortunately。😡。

Do you remember what color the route was？Blalock。If I write this， which is the thing I have to write。

 right， red？Ins K comm a V L。And then I write what is it。K prime， B prime R。

Is what happens if I pass this into restoreor left？😡，It's sell。

I don't have to call restore left here。 I could。 It will be useless。

 but I could because they accesst any function because where we are here is where I a。😡。

whichhich is the same thing I just had， okay， but suppose I inserted here， okay， I'm here right now。

 you are here。😡，And I'm certain to this， and I get a different tree here。😡。

But if I call my rebalancing thing， I don't care about red here。

 I care about if this is red and this is black。😡，I only care to rebalance when I'm at the black grandparent because that's when I have access to all my subtes and I get to change them all so in this case here in the red case I'm in maybe in the middle of something that produces something that gets rebalanced by my parent。

 but right now I don't need to restore left because it's not going to do anything it can't do anything because this has to return to me a red node。

😡，Does everyone see how that makes sense？嘅。This is basically this must be a red node because I put the red here and therefore restore left on it would do nothing that's main that's the main kicker okay。

😡，And then the greater case is going to be。The exact same except where I'm going to insert into the right instead。

L， K prime， B prime。Ins K comm a V。R okay， one other note also because because I'm in the context of this K comm a V from the insert because word're it here。

 I didn't have to pass in the K comm of V because I could have just like kept it in the environment that doesn't really matter。

 but it could have made the code a little bit nicer it's just I put it in the size I had to commit to it。

Okay， and then finally， after Is runs on the entire treaty， whoa， it's been that long okay。😡。



![](img/01f42000cdf61919969ac4bb22a1b8f9_3.png)

After Is runs on the entire ARBT or the entire tree。Then I just case it of red or black。

 and I recolor the node black if I need to， okay？😡，All right。嗯。And that's it。 That's the whole thing。

 I only need to restore left in this case， or restore right， right only in the black case， yes。就是。

Right here， so if I'm here， this means that I just I was I was here。😡，I was here then on my left guy。

 if you look at my code here in the red case， so that means I go here red because this is red。😡。

And then I compare and we're go left because we inserted left and we're going to see something。

 I don't care what， but we're in the last case， so we insert here and this guy turns on this so we're not here。

😡，And now what do I do， well， now I've called this and then I return just this， I return just this。😡。

Ins returns justly。But then insert， intercepts it because this is the final return value。

 so we go here and in case this of red， is this red？Yes， so let me tell her black。Painted black。

 yeah。Yes， but we'll continue receiving the balance Think about this way。 Okay。

 and I will show you an example that Ill make this very clear at the end of the lecture。

 But the idea is simply that。😊，I've only showed you cases where we rebalance like once or twice or once and then we get to the root you could have the case where you have to rebalance like three times n times okay but the point is that at any given subree。

 very low the tree， I can rebalance， but recursively how did I get here？😡，Recursively。

 I got here via the ins function。And the ins function has all this stuff it has left to do after it calls ins in particular。

 after it inserts to where I am， I'm here， maybe it will immediately restore left on any black。Subre。

Which means that after I insert， if I have a violation， I rebalance。

And then this guy is itself another Is call。That might be subservient to a larger tree that has a black node that we then call restoreor left on again or restoreor right so the point is that like we're it's something called weaponization of the call set I call it okay basically meaning that like the way that we have these calls set up such that recursively I have work left to do after this。

😡，That will ensure that I always when I make a change。

 I then rectify it and then larger I make that change and I rectify it up and up and up the tree okay we kind of unwind the call set if that makes sense。

😡，好。Indeed， but in a kind of a different way because you're trusting your color。

 which is kind of a peculiar way of thinking about it， I guess it's both， but okay。

I will show you with trace now， which will make it very clear all right and then the lookup function also I'm going to show you I'm not going to implement it for you because it's very boring。

😊，It's the BSC thing。This should look like BSC code。

 the one thing that's new here is something I wanted to show you very briefly。😊。

This shouldn't look like real syntax cube because this or is inside of this perens it's something called an or pattern in an or pattern you can match either case so long as they enter here in either case so long as they bind the same variables of the same type it's just because like the red and black cases I look up the same so I might as well do the same thing so this is an extension of SMML in the SMLJ compiler called or patterns but we can make use of it and it will we don't have to copy pastes code twice or isolate it to a helper。

😊，Yeah because it's either red or black and it binds all the same variables。

 I can run this code safely， but you can imagine if this pattern bound X and this pattern on y。

 then like if we went into the x case we might use Y and if we went to the y case we might use X this is definitely an aside let's move on because I'm almost out of time。

ok。So that's the lookup function and then remember I said we were kind of ambiently in a puncter so this is the final thing Everything we've been talking about this whole lecture is down here okay he exists out here and we're going to do the same puncter thing this isn't stopping electron modules okay this is still a lecture on modules but we're in a functer that takes in this key structure so that we can produce red black trees but red black trees on our arbitrary keys okay and then so on and so forth this is our definitionlah blah blah right？

😡，If this is true。That's our entire code， but we're not done yet because I'm going to show you the final trait real pass okay。

😡，We got this tree， all right， gaze upon it， baask in it。Now let's figure it out。

I want to insert two。 All right， let's hear it，2。Next。Right， left， left， cool， Okay， I inserted you。

 but what do I have here， What is this called？Red red violation， oh my God。

 what's going to happen is when I insert this guy ends the here is going to call restore right。😡。

And what do I get？Red， red violation works looking at this triad。

And ins is going to call restore right here or actually， wait。That's where we sort left my be， no。

 it's the restore right Em， I guess confusing doesn't matter。

 We call the restore restoration function and you agree with me this is the right triad for that。

 but we recallcol it the same way red， black， black。But what have we got here？Right red violation。

 But how did I get here， I got here because I called ins on this guy， which does nothing。

 but how did I get here， I called ins on this guy。😡，So we identify this triad。

 which is in the restore left case。😡，That then see， oh my God， I can turn it into this rebalance red。

 black， black， but then finally ins returns， ins finally returns its final value。

 and it sees why the root is red， in this case is's actually fine， but might as well be black， right？

😡，Recursively， everything works out and look at how much code be produced to do this。😡。



![](img/01f42000cdf61919969ac4bb22a1b8f9_5.png)

This much code and this looks like a picture， this looks like the picture。😡，Picture programming。

 I disagree， I could have isolated this into a helper， don't play code golf with me， I will win。

 okay。😡，Anyways， recursive leap of faith， red， black trees， thank you。

