# 022：CSE 12 - Basic Data Struct & OO Design - LE -A00- - Lecture 23.zh_en - GPT中英字幕课程资源 - BV1zJQHYcE8g

![](img/0bbf4f9b5869e4ed2c4049746524e28e_0.png)

All right。Let's， let's get started。 Okay， good morning。 This is Wednesday week。8， once a week，8。

I I do want to kind of make sure that we are aware of the plan next week。

 because some of you are asking me about like Wednesday， what。

 what we're gonna do on Wednesday next week， because it's the day before Thanksgivinggiving。

 I know some of you will have travel plans， okay， I was thinking about making it online。

 But if you think about it， it's the same thing。 right， if I're traveling。

 you can now go to online class either。 So what I would do is I would just host in personson class as regularly。

 okay。And then if you have to travel， you travel。 and then you can watch the podcast， right。

 We have all the podcast available。 So it's， just， so it's it's good for people who need to travel and people who will be on campus and want to come to live class。

 So be good for both。So that's the plan for the coming Wednesday。 There is no class。嗯。Next Friday。

 right， So this Friday， we have class， but not， not next Friday。嗯。

So what I want to do today is we'll look， look more about trees， okay。Because trees is。

 is a very important concept。Sorry， what we talked about last time was we。

 we wrote this contains method for trees。 It's just find something in a tree。

 We did it in the D F S way。 we did it in the B F S way。 We did it recursively。

 we did it itly in general， if you use a loop。 You create the own stack。

 It may run a little bit faster because recursion does have the overhead of function cause。

 Okay but it， I mean， technically， recursion is a little bit slower。

 but it's much easier to write right， So they have their point count。

I do want to reinforce this concept of a tree。Right， so if you think about the tree。

 this is the structure that you should realize in your head。

 You're writing the code for a node in the tree。 This node can be the root。

 If the parent is now for this current， then it is the。It is the root。 This note can also be a leaf。

 If all the children are now， then that is a leaf， okay。

And then the children that this node may have， they are the root of some other subies that are not just like a single node in your head。

 They should be a kind of。The rules of sub。 Okay， and this example。

 the other section we finish a little early。 So we'll look at this example。

 We didn't get time to look at it in our 9 clock section is， if I want to know for each node。

 how many。Descendant it may have。 In other words， what's the size of the subre it is sitting on。So。

 for example， if you look at this current node， you may have just， for example， three children。

And this is one child。 It has three children underneath it。 This one has 15。 This one has 8。

The question is。This。Notode， if you think about the the size of the subre is like。

This branch would contribute to 4 to this one。 This is 16。 This one is 9。

 It's always the number of nodes in here。 plus  one， which is this node。

They all feedback to this current node。 And then this current node would add one to whatever is count is and give it to the parent。

So what we are really looking at is when you try to think about three algorithms。

You are thinking about you start from the root。 And then you're gonna recur in general。

 you're gonna recursively go down until possibly the leaf level or at a certain position。

 And then you start to populate back。That's in general， how you do it， how you realize in your head。

Okay， and this kind of thinking is very， very important。 And what I。

 what we will do today is just to practice this thing。That's pretty much it。 Okay。

 if we finish things early， then we'll move on to binary search trees。

 We'll move on to binary search trees。Are there any questions before we get started in here。Right。

So this is what we're gonna do。We're gonna write this class called binaryary treee。

It's not a binary surgery。 It's just a binary tree。嗯。You wear Tn。Pote has a left， right value。

 has a constructor。 This constructor just initialifies the value。 So left and right it will be no。

 if you just create a node。哎。嗯。So this is the node class， the inner class for the tree。

 You have a reference to the root。You know how many node there are in the tree。

 You also know the height of the tree， the height of the tree。 how tall the tree is。O。

So we have to know the class。 Now， if you look at the the binary class。嗯。We say rules is now。 I mean。

 what I just to be more precise。 Let's assume the height is negative1。Sorry。

Let's update this a little bit。So it's a little bit easier。 If have a no tree。

 the height is negative1。 If have a single node， the height is 0。So update this part a little bit。

 I think you print out is 0， but this one should be 91。 But this would just create a no tree。

 There is no node。 The height is 91。The route is now， O。The first exercise， the first exercise。

This is a constructor that describe creates empty tree。 Now， I want you to build a binary tree。

 Again， another constructor， you are given an array。 you're given an array。

 And what this array really gives you is the a bunch of values。

 And I want you to build a complete tree， complete binary tree to hold this array。Okay。

Let me give you one example。 You can assume the values will now be now。 Okay。

 you have at least one value in there。 And this is what it looks like。 If the values is。

 is like this。3，2，2031，0。 If， if have something like this， I want you to build a tree。Like this。

Does that make sense。So that's the tree I want you to build。

 Can you build a complete tree using the data in this array。You can build nodes， and connect them。

I give you some time。 You can work with a neighbor or prepare yourself， How would you build this。

Treing here。So remember， this is like。You know， what you can also assume if you make your life a little bit easier。

 you can also also assume this thing is。1 index。To make your math， or it be easier if you want to。

AndBut if you're comfortable with zero index， that's also fine。It's basically a heap， right。

 You want to build a heap out of this array。What would you do to create this。Structure。

You can assume it's wine ducks， I think。Based on the， the rules we learned about hips。Should work。

ToHow to convert a array into a complete binary tree。Small hint。 You， you may need a queue to do so。

Give me a vote once you're done with it。So事。You're gonna you have to。I don't think you can recur。

 you can recurse， but not in this format。 So you， you might have to create a hopper method if you want to use recursion。

嗯。Remember， if you look at the complete tree， theres a parent child relationship。

 If you look at the I node， the children is at 2 I 2 plus 1。系。

That's the information you can use to help you determine who should be my left child。

 Who should be my right child。And you keep building up the tree in this way。If you are done both。

If you're done， you can look at your neighbor's code。They should be very similar。

If you don't use a recursion， if you use a recursion， it may。If you focus one more minute。

 then we'll write it together。We are， we are pretty clear where the route is， right。

 So we know where the route is。And then。We just need to kind of go through it， layer by layer。

And that would allow us to build the tree。All right。Let， let's， let's look at this one， Right。

 So if we assume the the arrays now now， then we can， we know the root。 Where is the root。

Ruddy is at what node。Location 1， index 1。 So that's where the route is。So say， in I equals one。

And then we'll create a a node out of this value。Where's the the Tn。 So's say Tn。

Reference equals to new。Tnote。Values。哎e。Right， the reason why I want to have a variable in here is so it's easier for me to determine the lesson。

 right Charles。And then what was say root。Equals to ref。Or， you can just say入 the Do you know。Sorry。

 we， we can just do that， but。嗯。Once I finish this thing。

I want to successfully insert the children's， right。 And if you want to go through layer by layer。

 remember， that's more like a B， F， S thing。 B， F S， So gonna need a queue。Of Tn。Q equals to new。

Linkked list。Right， we created this thing。And now， we are ready to。We're going push。

Do we want to have a Tnote queue or do we want to just have a。Vue。

 I think maybe we can just have an integer。嗯。Let's see。Maybe we， we just need an integer in here。

 We don't need a。Let me see。 maybe we should have a T note， sorry。

And then we'll just have a reference in here。 right， So this is what we have in here。

So we have Q do push。 we're pushing in this reference。And then the next thing is。

 while Q is not empty。So soon as it is not empty。What do I do in here？ What do I do。

What's the first thing we do when we do B F S kind。 So right now， we we have this node in the queue。

 right， We want to get rid of it。 We'll try to attach to children。To it， that's， that's the thing。

What I trying to do？So what's the first operation here？We want to attach。

2 children to this node in the queue。Whats the first operation going do BFS？And our members。

You're gonna pop， right， You're gonna pop the。The data in there。 So we're gonna say， Tnote。

Of current。Equals to Q dot pole。This one would get this node out。And。

 and now what I need to do is I need to determine。 I need to determine。This node， I mean， right now。

 this node would have。Note the I， the two children that I have is 2 I，2 I plus 1， right。

 Those are the the values。 In other words， for the route 3， I want the two children to be 2 and 20。

2 and 20。Right， so I would lay out。This node in here that would receive the value 2。

 And then I would also lay out a node in here that would receive a value of 20。

That's kind of how I want to lay them out。 And then I will move I to the next spot， to insert them。

ToIn them。 So we we obviously need to check because right now。

 this route definitely has two children， but it's possible。That this node may now have two children。

 What is the criteria that I should use to judge if this node would have。

A life child or right child of both children。What's the criteria for me to judge。Like， for example。

20 only has one left child， like 30 has no children。How should I judge。有。Right。

 so I just need to check， right， Do I have a location in the array for 2 I or do I have a location in the array for 2 I plus  one。

That's the idea， right， So we'll check if。Two times I。Is。Less than。Values dot length。 You know what。

 Let me also create another variable。 say int N equals to values。Do蓝。And just。

 so it's easier for us to。Right to this one。So。If this thing is less than an。So 2 I is less than。

 And it means this node would have a left child in the array。Right， if this array size is 7 and 7。

 So if two times I is less than 7， it means has something。 Then we do Q dot offer。

What should I push in in here。You know what， we should first build a note。 So we should do this。

 sorry， we say current dot left。Equals to new。Tnote。Values to I。

So well link a node in there before we push it before we push it。

So we'll let this node have this2 I with this value。And then similarly。

 if two times I plus 1 is less than n， we say current dot， right。Because a new keynote。Values。

Two times I plus 1。Right， so this is kind of what we have。 You can。Also， do in here。嗯。

I think we can also do this Q dot offer。Current dot left。And then close the bracket in here。

 you do Q dot offer。Current dot， right。This is what you can do。

 So you would create a node Let current dot left stay in there。

 and then you insert that node into the queue。Am I done。Am I done。What else do I need to do。

You should also do i plus plus。완전이갔다。This I plus plus would allow you to move to the next element in the array。

 and that next element in the array would match。呃。The corresponding value in the array。So。

 for example， in the first round， we build up a three。In the first round， we create a node of three。

嗯。And the queue would have this node 3 in there。This is when I equals to one。

This is when I equals one。And then we de this node。 we look at the two children。

Two times 1 is less than 7。 So we。Let the left side point through2 I， which is 2。

 And we're pushing a two in here。And then we LED to the right side。Stay with 20。

 Then we push in your 20 in here。3 is gone， right，3 is gone。Now， I is2。I is now 2。

 which corresponds to this second element we push in。 So if we look at2， you get two out。

You get this node out。 You look at each two children， the two children， 30 and1， so。嗯。The。

 they are both in bounds。 So youre gonna connect 30 to it and you push in the 30。

 You connect one to it。 You push in the one。OkayK。And now， I is 3。Is changing into 3。

You look at this node， which is third， which is 20， right， You look at 20 is coming out。

Once 20 is out， you look at the two children。 It only has one life child， right。

 because the live child is inbound。 The right child is not。 So 20 only have one life child。

 which is 0。So 20 would attach a 0 to it， insert 0。 and then we pop 30。30。

 both of the children are out bounds。 We don't do it。 and then one and 0。

 So the whole tree is build up。Does this make sense。So this is how you can build a tree。

 So if you say， I want to use the tree structure to represent the heap。

 This is what you can do to build it up。O。So we can do it in linear time， roughly speaking。快孙子。

You must be able to do this yourself。 You know， if you given an interview。

 write a complete tree out of this array。Personally， I like it to be wine index。 is just this math。

 in heres。 that's how I learned it。But if you make a0 index， you just do a -1。 should fine。

Should be fine。No。This is the constructor。Can you go backward？I want to print this tree。So， youre。

Given the route， I want you to print out the three level by level。That's what I want you to do。

So you are in a tree like this。I say，7，25。31， next 5， and。3，35， I don't know，11。

So you are supposed to print it out 7，13，5，31，95，11。That's what they are supposed to do。

 print out the data level by level。You know the root。Oh， I。

 I forgot to set up the size and the height of the tree。 We should。In the previous example。

 the size should be n -1。Okay， so。But in here， just print out the tree， I will update this part。

I say， size。Equals n -1。 Let's assume， there is a height。Function。

Assume there is a get height function。 that would。就是。Pasing the route。sure。

So assuming the height is gonna be updated。 The size is gonna be updated。不。嗯。

We look at the get height in a little bit。So can you print out this tree level by level。

This is slightly easier。It's like you are doing a B， F， S on the tree。 You are doing a B， F。

 S on the tree。ok。This shouldn't be new to us。 The other one is a little bit new。 This one， B， F， S。

 we should know how to do it。You're pushing the root。Your DQ， look at the two children。

 Does this node have two children。 If this node has two children， you push them into the queue。

 and you just repeat。Right， that's what you need to do。Can you do it。Pringned out to the whole tree。

For those of you who I'm done， can you also。Write a my third。To say。How tall the trees get height。

Youre given no， you're given the note。 You want to know how tall the tree is。Rightite the。嗯。Print。

Give me a vote once you are done。So take our time。You have to use a Q in here to print the level by level。

If are done， give me a vote，14 of us are done。This is very similar， like the previous one。

 You create a queue。Can you do it。Do folks one more minute。A we going start。Work on this together。

Print to tree level by level。In other words， you can compress the tree into an array。 roughly being。

 That's what it does。Right。Alright， so， let's work on this。 You're gonna create a queue， right。Q。😔。

Teennote。Es new linked list。And then， you。Put in the root。 I'm assuming the route is not empty。

 If the， the route is now， then you just。Return。嗯。And then， while， Q is not。Mmpty。Will pop this。

 So Tn。Current equals to Q dot pop or pole。get this note out。What should I insert into the queue now。

I should try to insert the left child and the right child of this node。 right So as they are now now。

 So if。Current dot left， isn't now。OrIn it into the Q， Q dot offer。Current dot left。If。Current dot。

 right。一阵疼 now。I say Q dot offer。Current dot rate。I forgot to print。

 So can system dot out print current dot value。系。And then。You're gonna insert them。

Just keep it going。Are we good。So that's how you're gonna go through the tree level by level。

If you change this queuee into a， a stack， you're looking at like a DF S on the tree。That's about it。

 You just you are going through the tree， but with a different order。Alright。Now。

 can I ask you all to look at the。Hight。Of the tree。 So， for example， let's write this function。

 See this is the in function。Got get height。And it's gonna give me a T note。Current。

Can you write a get height function to say， if I give you a note。

 you tell me what's the height of the tree rooted at it。 If I give you the root。

 then it's gonna be the oral height of the tree。 If I give you any other node will be the subre rooted at that node。

What would you do in here。For this one， you can use recursion pretty straightforward。啊。

You can also use BFS。But recursion is much easier。Can you write the height。I think in the last P。

 where you're gonna to write a binary search tree， you're going to write a height function。

 which is very similar， like a binary tree。Right。How to get the height of this node。The height is by。

 by definition to the furthest leaf from this snow。That's by definition。 right。

 What's the number of hops to go from this node to the deep leaf。Roed。In a soft tree。嗯。Of this note。

来 do。And this is a binary tree。 This is a binary tree。Reccurion is much easier for this one。嗯。呃那's。

Let's work on this one。 So if you think about it， remember。

 you are thinking about this as the current node。Right， you may have two may have。2 children。

How do I calculate the height of this node current。You may also have a parent。

How do I calculate the height， What's the height of this current？E goes's word。Let me also。

 if the height of this life laboratory is 20， this one is 5 was the height of this current。

Was the height of this node。The6。Or what， what's the height of this current note。Is gonna be 20。嗯。

Is it gonna be 20 or what。Or should be the height of current。 if the left sub height is 20。

 this right subre height is 5。21 right， should be 21。 So it's the tallest part， plus  one。

 whatever the tall of the two children。 And that's how youre gonna recurse for every node you're gonna recurse。

 When do I stop。If you hit a leaf， if you hit a leaf， the height。Of a leaf is 0。

 right Once you hit a leaf node。The high is 0。 or when you hit the now node。The height is 91。

 Eitherer rate is fine， right， depending on how you want to define the base case。 So you can check。

If current。Is now。Youll return 91。The height of a now tree is 91。嗯。Now。

 you will look at the height of the left subre。So， in。H1。Eals to。I say， get height。Current dot left。

And H2 equals  to。Get height。Current dot， right。And what do I return。I just return integer dot， max。

H1 plus1， H2 plus 1。 That's it。 That's the height。So recurse on the left side。

 you get the height of the left side。 You recurse on the right side。 You。

 you add one to either on them。 The bigger one of those two will be the height of this node。

So recursive code is much more succinct。Does this make sense。 So you're gonna rely on your children。

 right， your children is gonna get their height。 and then this height information is gonna populate all the way to this current node。

an example is， is like， for example， if you have。A tree like this。For example， if this is the tree。

 youre gonna start at this root。 You're gonna start at this root。Youual recurs on the left。

 recurs on the right。You， you get whatever the height is。 And then when you recurse over here。

 you're gonna to first figure out you're gonna to recurse to the left。 When recurse to the left。

 What do I get。The left side of this node in here。It's a negative1， right， get a negative1 back。

 So my H1 is negative1。Now， I need to recurse on the right side。 So he's gonna keep going down。

 And this one would recurse on the left for this one。Is H1 is 91。 H2 is 91。

 You add one to both of them is gonna give you a0。 So this one would return 0 back over there。

So the left side is 0。How about the right side， The right side is 91。Right。

 so you add one to both of them。This one would return one back。m sorry， yes。

 this one with return one back。So now for this node。

 it's gonna return the bigger of negative1 plus 1 and one plus 1， which is a two。

Did that means a level。I don't think it。So one level。2 level。 So this is a two。Back in here， right。

 And then for this side， you're gonna recurt on this side。 you're gonna keep seeing。啲。N1 on the now。

And this part would be a 0。 This part would be a one。This part would be a two。 This part would be a3。

And this。Let me see 1，2，3， and this part will be a four。For hop。

 did let mis account somewhere in here。Lets see。😔，So this is 0。 So this one would give you a0 back。

sirir。I say0， negative1， negative1， this one is the 0。So the sum of these two， youll return it back。

 So this is 0， negative1。This would give you a one back。Wen。Add one to it to give you a two。

Why is this one give me a two， which should be 3， right？

 I think this one is the left side is three hops。 The right side is4 hops。 The right side is good。

How about the。Or did I miss a count on the right side。N1，91， that's a0。Add one to it。 There's a one。

Add one to it。 There's a two。 So two hops away。3 hops away，4 hops away。哦，O。So， this part is gonna。

So I， I basically go to the return value wrong， right， So I， my return value。

Should be written like this。 So this one would return 0，1，2 and 3。 You add one to both of them。

The maximum is four。I think that's how I I wrote to the return I in here。

 This return value is given back。So the height of this tree is 4。

 If you write this called which makes sense， right， the right side is。Is a 4，4 hops。

 The left side is three hops。Are there any questions for this one。

just annotation is a little bit off。So this is gets the height。How about this。

What if I give this tree。Also， a listening teacher。Integer。呃。Subordinates。How many。You。

 if you think about this tree is like a hierarchy of USD， right， So we have the。

The chancellor and then down beneath there's this very deep hierarchy。Now。

 how many people am I in charge of， Like， for example， if we think about this thing。

These people are in charge of zero people。That in charge of one， this is2。This is three people。

 and this is like five people。How do I。Is this three people。 Did I always make a mistake in here。

So two people in charge of it， three people。The number， the size of the subre。

 So they are in charge of two people。嗯。So this is in charge of zero people。W。2 people。

And this one is 0，0。 So this is 2。This is。嗯。He's in charge with three people。Then this one should be。

6。Should be 6。7， there are 7 people。 Don't know how to count anymore。7。

 the left side is three people。 The right side is four people，7 people。

 If I need to get this information。How would do you do it。

I want to know how many people each person is in charge of。What would you do。

And you just need to go through this tree once。We don't have time to write it。 but what。

 what's the general idea。You look at this current node。As a parent。How do I do the math in here。嗯哼。

so。Alright， so basically， I'm gonna have to rely on my children， right。

 If my children have their information， I will do something。 like， for example。

 if this child is in charge of three people， this one is in charge of five people。Then my current。

 how many people is this current node in charge of。Is it going to be worth。The turn。

So this there are four on this side。 There are5 on that side。

 So it's basically whatever the trials information adds to。高o B。

What the current node is in charge of。 So it's very similar like the get height。

 Except you are not gonna return the maximum of H1 plus 1 and H2 H2 plus 1。

 And it simply returned there are some。H1 plus 1 plus H shoe plus  one。

That's gonna be what you return。 So all these examples， really。

 I want to reinforce this concept of recursion。 you gonna go all the way down to the leaf level。

 Then you populate back up。嗯。Questions。Alright， so we are done today。

 I think that's all the time we come forward。Coming back on Friday， we'll look at binary searchries。

 binary searchries。No hear David。Because like God is。We job 6 participations。

 We job 6 participations。 Yeah， so， it's not gonna。 did you miss more than six classes early。どせの。No。

Then you should be good。 Okay， all right。

![](img/0bbf4f9b5869e4ed2c4049746524e28e_2.png)