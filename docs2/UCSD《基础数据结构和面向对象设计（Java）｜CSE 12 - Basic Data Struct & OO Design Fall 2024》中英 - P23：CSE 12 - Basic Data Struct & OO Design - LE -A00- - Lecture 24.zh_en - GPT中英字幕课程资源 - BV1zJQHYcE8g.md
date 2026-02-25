# UCSD《基础数据结构和面向对象设计（Java）｜CSE 12 - Basic Data Struct & OO Design Fall 2024》中英 - P23：CSE 12 - Basic Data Struct & OO Design - LE -A00- - Lecture 24.zh_en - GPT中英字幕课程资源 - BV1zJQHYcE8g

![](img/df732bace088052ea7f3aa639be05f76_0.png)

Alright， looks like the chairs in the room always get reconfigured every time we come here。

 I don't know what's going on with this room。嗯。So。It's good。 So。

 we have a different look every time we come here。嗯。The plan for today is， we'll finish the。嗯。

Bin trees。 And then get started with binary search trees。So today， we'll release the next P A。

 which is the last P。 Okay， and I know our regular due time is like Thursday night。

 but Thursday night next week is like。Thanksgiving， right。

 so we have decided to push the deadline to Monday night。

 So at least these folks can enjoy a few days of。Holiday。

 I know we push our USD students pretty hard， but。Once a year， we can take a small break。

So just for next week， right， we still have classes Monday， Wednesday and then。嗯。1， Wednesday class。

 if you need to travel， feel free to watch the podcast。 but I'll be here。嗯。

That's pretty much all the announcement I have。 Are there any questions。All right。

So the plan for today is we will look at binary trees just a little bit more， okay。

So last time we were playing with binary trees。 we say you have a ray。

 you build a complete tree out of it。 Or if you say you have a tree， you print it out level by level。

Technically， you can traverse a tree really easy， right， you， if you say。

 I don't care about level by level。 I just want to visit every node in the tree。

 That's kind of all you need to do。 if you want to print out a tree like this。

 I think the other section， we had some extra time。 So were playing with this。

 And I think this class， we should also do it。 So if it's just say I have a a current node。

 and I want to print out the thing。 you can just check if this thing is now， right。

 if this is a no node， which means you are at the level be beneath a leaf。So you just go back。

 Otherwise， you just print out this value。 then you recurse on the left， recurse on the right。

So this is a pretty easy DF S way to traverse a tree。 Okay。

 if you don't have to print it out level by level。And， and the last time， I think for this section。

 we were talking about this idea， right， I say if you are given a tree。

 let me try to find a spot that we have some empty space。How about we do it in here。

 So if you' are given the tree。And this tree may not be a complete tree。 It can be， for example。

 something like this。 And we want to know how many people each node is in charge of， like the。

 basically the number of subordinates in here。And so this， this is zero people。嗯。0 people，0 people。

0 people， one person。2，2， and then。six。Something like this。 So how do I summarize this information。

Quickly， just by going through the tree once。嗯。Did anyone figure out how to do this。

If you write this method and for example， this one。

 each node would also have this count of how many subordinates it has。 So a node would have a left。

 have a right， have a value and also have discount count。How would you do this。

If you want to summarize how many。Subordinates Ish know is in charge of。Any idea。有。H1 plus H 2。

Plus 2。呃。H1 plus H2， similarly for H1 H2。 But in in here for suborinates， basically。

 if you think about it， what was the question that I left for， for this section。

What was the question。Was it to suboringiness。O。So if you think about it。

 if you are writing the code for current， you have a P A。 This is the left。 This is the right。

We are basically saying the number of。Subordinates in here plus the number subordinates in here。

 plus 2。 right， That's kind of the idea。 So let， let's just implement this method a little bit。

 So say int。Subordinate。You are looking at a note， Tn。Current。What would you do in here。

When is the base case。When do I have the base case。When currently is now。Return 91， right。

 So if current is now。Return 91。Basically， you are saying this one is negative1。

 This one is negative1。Right， so once you add up91 plus 91 plus 2。

 thats that's gonna give it 0 for leaf node。And then。We'll recurse on the left。

The live child will recurse subordinates。Current dot left。Right。Eals to subordinate。Current dot。

 right。嗯。And then you would basically now set current。Dot。Like sub， this variable equals to left。

Plus， right。Plus2。And also， you return。Current dot sub。To a parent。Right， so we just。

Just add up the left subordinateist， the right suborist。 And now。The count， plus these two notess。

Be the one for my parent。 That's how you can recurse。Any questions。So in this example。

 each node rely on its children。To get the information populated up。

You can also do something like this。 For example， I want to know the depth of a node。 Let me go。

当 little标 here。HowAbout the depth of a node。So。If you look at something like this。The depth。

Is how far away a node is from the root。That's how deep know this。 So0。1。2。😔，3，4。

That's how far away a node is from the root。 So assuming that each node also have a a depth。

How far away it is from the root。 Can you write a function that would update every node depth。

If you call it on the route。So this one can return in。 That's fine。

I don't think this one need to return anything。Wd， let's call the steps。Teennote。Current。

Assuming each node has a left， has a right， has a value。 now also have a depth variable。

 Can you update every node depth。Really quick。 How do you do it。Can write a code I like this。

How deep a know this from the root。Again， think about。This information。

 you are writing code for this current。Well you writing code for the current。

This current either relies on his parent or relies on his children。To get the information。Right。

So in this example， does currently rely on his parent or does parent rely on his child。

To get its depth information。Just naturally， if you think about it in this way。If you are done。

Give me a vote。You got done with。The code。This will be the last exercise we do for binary trees。

How do you find the depth of each。No。So I want to run this function on the route。 And if I do that。

 every node step is updated。Properly。Alright， first thing， let me ask。

 does current rely on its parent for its depth， or does it rely on its children。Rund this parent。

 right， So the current would rely children for height because the children would support height。

But current would rely on its parent to say how far away is it from the root。Right， so。

The basic idea is the depth of current equals to the depth is parent plus  one。That's it。

AndSo that's the basic recursive case。 Now， what are the basic cases。What are the base case。

when do I stop recursing or when do I know the answer right away。If the parent is rude， you know。

 if current is rude， right， if current is rude， how do I know if current is rude。In other words。

 he doesn't have a parent。If what。If current thought， P。Is no。I think probably we can do one more。

Then let me write it。 I will leave a little bit space in here， if。Current dot P is now。

I would say current dot depth equals to 0。Do I return right away。Do I return here， and I'm done。

Like you said， this is a root。 I said is。D to be 0。 Am I done with the whole tree。You're not。

 You are not。 So you， you should continue。 there shouldn't be a return。 There is another edge。

 There is another base case。So keep going down until your what。Until currently is not。

 once you hit the。The child of a leaf。If current is now。You return。You're done。

 You go back to a parent。嗯。And then we'll say， current。Thought。De。So if this is the route， I。

 I will do this， so。嗯。Else。I say， current dot depth。Eals to。Current dot P， A dot depth。Plus one。

Es to his parents depth。Plus one。And then you recurse on the left， you say depth。Current dot left。

Then you do depth。Current dot right。等 you要打。Right。So you are checking if it's the route。

 you said it to be 0， recurs left， recurs， right。 If it's non root， you update your。Thatb first。

 And then this information will be used by your two children。To update their depth。

As you can see a simple recursion。 In fact， it's a linear time algorithm that would。

Give you the depth of。Every node industry the tree。Any questions。

These are all fundamental skills Everyone of us should be able to do， right。

Without having to think too much。 And the way you should think about is your writing code for this one。

 rely on children like the height， rely on your parent， like the depth or subordinates。

 is similar like height。You can also do this。 So we， we don't have time to do it。

 but you can calculate the diameter of a tree。 Like， how what's the distance between 2。

40 snows in the tree。You do two rounds of death。 And then you will be able to find out。The diameter。

 nonetheless， we are done with binary trees。 We are done with binary trees， Other questions。O。

 so for binaries， we talk about how to build。How to traverse。How to find something in the tree。

How to figure out some of the basic properties of a tree。Now。

 we're gonna focus on a specific binary tree。Which is in here， its called binary search tree。

Binary surgeries， there are binary treess with a special property。

So not all binary trees are binary search trees。 In fact。

 binary trees is much more diverse than binary search trees。 Okay， think about hip is a binary tree。

Right， there are many other version of binary trees， other than binary search trees。So a binary tree。

 a binary search tree in here is you have a binary tree where the key inch node must be greater equal to any key stored on left sub tree and less than equal to any keys stored in the rest sub。

In other words， if you think about this tree idea。If this is x。

 the thing to the left side is less than x。 The thing to the right side is we x。 if you don't assume。

There are duplicates。Okay， so everything to the left on the left side of a node must be less than。

 Everything to the right side must be bigger than。 This is totally different from a heap。A hip。

 for example， he a node。 if you like mean hip， a node in here must be smarter than its two children。

There's no requirement on the， the， the subre in here or left right。

 Theres no ordering horizontally for hip。 the order is vertical parent child for binary surgeries left right。

Kind of， and also vertical。So， it's。The requirement on binary surgeries or B， S Ts。

 they are stricter than the hip。对。Are there any questions。

B search trees is the foundational data structure for sets or maps in Java。 So in Java。

 there is this tree set tree map。 There is also hash set hash map。 We learn about hasing。

 right hashet hash map。 They， they basically implement the hash table as the data structure for tree maps。

 tree sets。 They use binary search trees as the supporting data structure。Okay。

 so all the data you have in three side treemap that are stored in a binary search tree。嗯。

Are there any questions about the definition of a B， S T。Alright， then let's look at。

This question here， which one of them is or are a binary search tree。Which one of them is。

Let's take a look。A lot of us saying E。 A lot of us saying E。

Which ones are binaryer surgeries is like if， if you look at lot thing E。Is， is a a binary or3。

Is this one a part tree。It is， right。 So this thing is bigger on everything to its left。

 This thing is bigger on everything to its left。 So it's like a link list。 And that's fine。

 That's part of。A kind of B SD， right， B， ST doesn't have any requirement on structure。

 It just has ordering。How about this B， is B a binary surgery。

This 42 is bigger than everything to the left， Smart than everything to the right。 So is this 55。

55 is speaking everything to its left。There is nothing to the right。 I B or B， ST。B is also a B， S。

 How about C。Pretty obvious。 not， it's not a binary。About D。Is the a B， SP。Yes or no。It's not right。

 D isn't。You say 42， if you look at everything to the left side，42 must be less than 42。

 And this thing is not。 So we not just look at one layer down， We look at the entire left up tree。

 the entire right up tree。 So D isn't is because of this thing。 So D isn't is right answer。

 A and B are B S T， not D。 Okay， not D。Later on， we're gonna look at one of the interview questions from Meta that was around the pandemic area。

 So one of my tutors， she got interviewed by metata。 And one the question is。

 you are given a binary tree， you need to verify if it's a B， ST。

That's what we will practice a little bit。She didn't end up going to matter。 She got it the job。

 although she made a mistake on this interview question。你地人。Do it correctly。

 But it's a good practice， right， So you， given a B， ST， you verify whether it's a B。

 youre given a binary， you might verify if it's a B， ST or not。No。

Can we do a practice on this exercise first before we look at that，So contains， right。

 So contains method， we have written the contains method for a binary tree。Now。

 can you write a contains hoper method for a B， S T now for a B， S T， What would you do。Right。

Wr this method。 You are looking for this thing。 What should be the prototype。嗯。So how do I。

Contains helppper。If you， if you look at containss， we were looking at is this value。

 the value I'm looking for the at the current。If its， if it is I'm done。

 Otherwise or recurs on the left。 recurse on the right， return the or result of。The left the right。

 That's what we did， right。Now， in here。Obviously， that version still works。

 That version of contains still works for B， SD。 B， SD is a binary tree。Can we do better。And that。

If any of us needs a handout， I think I should have some handouts in here。If you want to write。

So again。Has to be。Dist thing， Yeah， you can assume that distinct thing。Okay。

 or you can just return the first occurrence。And use these as exercise time， because。

You're gonna see questions like this in the final。 You gonna see questions like this in your interviews。

So its， it's important that you don't have to think。To write these methods。The standard practice。嗯。

Alright， so do I have to use a recursion。You can， if you want to， right， for this one。

If contains helppper， like if you start from the root。You can do this。 So keynote， current。And then。

 value。That's say E， the key I'm looking for。So， if。Current equals to now。Or return。False， right。

 is's the same as before。And then I would compare， if。Current dot。data。Thought equals to this key。

A return。除。And then what。You have found it。 And then。If you want to utilize the。

 the properties of a B， SD， what would you do。To look for something。

Do I have to go through both sides。No， right。 I don't have to go to both sides anymore。

 What would you do。Right， if Qdo compare to current dot data。Is less than 0， for example。

 less than 0 means key is less than the data。The key I'm looking for is lesson data。What do I do。

Do I focus on the left or focus on the right side。The left side， right， And you can recurse。

 contains helpper。Current dot left。The key。 and one common mistake I've seen people make in here is you forgot to return。

This recursion call。嗯。If you， this return is more like a relay。 once you hit something。

 you're gonna pass this back all the way to the very top without this return， this。

You're gonna go down， But the value that you find out actually will never populate back。

So this return statement is very important。Else。You will do the other way， return。Contains helper。

Current dot， right。Were the key。Does this make sense？So if it's less than 0， if it's bigger than 0。

 now， you only focus on one side instead of two sides。Can I ask you all。

 what's the run time for this one。What's a run time to look for something in the worst case。

 in asymptootic notation N is the number of nodes in the tree。Can we vote on that， please。

What is the runtime for this one。The worst case， run time， the worst case， run time。

You have nose in the tree。The most popular choices。Wrong， okay， the most popular choice is wrong。

 Can we have a quick discussion， Turn around， Talk to a neighbor。 What did they vote for。

What do you you vote for。We definitely need to make sure this is clear。What what's your answer。

Howk your neighbor。 Turn around。Talk over a discussion。What do you do， What do you do get。Alright。

 the answer is a， okay， The answer is a is not B。 A lot of us voted for B。

 The most popular choice was B。 A， he changed。 So looks after the discussion， we， we got better。

 The answer is a， Why is， why is the answer a。When will the worst case happen yeah。Right。

 it's something like this。 And I'm looking for something smarter than this。

Theres there going to keep going to one way。 Is this only worst case。Is this the only worst case。

Any other worst cases。So s to the left and then ske to the right other than these to any other worst cases。

In the other worst cases， yeah。Right， so any configurations， you can also see Z exact。

 something like this。keep walking down。Because B， S Ts don't require any structural restrictions。

 This whole thing can just become a linked list of some sort。And this kind of issue is。

Basically it degene into a link list。 So the worst case the link list is big O。

 And here' is also big O N。And we really hate it。 This， This is something you want to avoid。

 Do we have the same issue in hips。No， hipaps is a nice， balanced， complete tree。

So the height is always log for he。 but for B， SC， the height can be n。

Which is really bad because the behavior of a tree a lot of times depends on its height。

 The bigger the height is， the worse the runtime is。Right。Are we good on find。

 So the worst case of find in B ST is。Bgo。嗯。Okay。All right。How about build。

 I want to insert some node into a B， S T。So can you try to insert。These values into a B S T。

 assuming there are no duplicates， assuming there are no duplicates。 How do you do it。

This is what we have。Take your time， Okay， insert them。 How we are gonna insert， How do you insert。

Inertion is not too bad for this one。嗯。Remove is annoying。嗯。How about we insert 42。

 Where do we start insert in a tree。In the BSD。We start on the route。Where do we insert on a heap。

Inser at the leaf。 right， So there is a difference。 Do not confuse。

Those two different kinds of tree structures。 So were gonna start at the route。 We。

 we try to insert 42。 So 42 is already here。 Well done。Nothing changes。 How about if I insert 10。

 you also start from the root。It， it's like you are trying to do a find。 Youre trying to do a find。

 So if I I'm sitting here， I compare 10 with 42 is less than 42。 Which side should I go to。Go left。

32 go left。And then 30， I need to go left。 And then this thing is a now。 that's when I insert。10。

 right， So when you try to insert， you have to be careful， I think find is easy。 right。

 You' gonna keep looking for things when you hit now， you， you return false and， and that's it。

 But when you try to insert， it's very similar like find， but you cannot go to this site。

 because when you try to insert your current pointer。Has to sit at 30。 You say。

 I need to go left on 30， but I can't。 That's when you insert 10 as a left child of 30。

 So you cannot jump over to this now and then oh。Where should I insert 10。

 You have to remember the parent。 You have to remember the parent。

In order for you to do the insertion correctly， does that make sense。

When you write this insert method， that's what you have to do。Inert 80 is not too bad。

42 go to the right，65。 I need to go to the right， and I don't have it， so。

That's when you insert A0O over there。A we good on insertion。嗯。闹。Can we write it。Can we write it。O。

So we have to add method。 as I give you a value。 If this thing is now， I just throw the exception。

 And then if route is now create a new node with this a， I'm done。 Otherwise。

 I just call this return add how helppper to say， give it the route you have to add。

 Can you write it down。Okay。Can you write down this addd method。 It's part of your P， know so。嗯。

It's good to practice a little bit。If you are done， give me a vote for this question。 Okay。

 if you are done。You will vote for this question。 and this question may help you to think about。

How do we want to add。系。Add the data iss guaranteed the route won't be now anymore when you first come in。

Right。It means， did we successfully add something。If you add a new node， you return true。

 If you say already find the duplicate。In there， you return false， It means I didn't add。

That's what it does。To use this opportunity to practice， please。嗯。Take our time， think about it。

 right？You have to do the comparison。To decide if you want to go left， if you want to go right。

The left side insert， right side insert is basically the same。Right。

The vote I see for this question is over the place。Well give folks another 30 seconds。

 and then we're going to start。Wr it together。Orbert， this is the last thing we can do。And on Monday。

 we probably will be able to finish everything。About BST。All right， so how about。嗯。Which one。

 which one of them is the base case。Is current truth is now， is this a base case。

I think you are overshooting a little bit。 If you， if current is already now。

 you don't know who your parent is because if you look at now node， you。

 you do not have access to your parent。 So that's A is not。 A is overshooting by one level。

 B is right。 So you， you， you find a match。 So if you do if。Current route。到依口到data。到 equals。To add。

You return false。You don't add anything。 And that false means there is a duplicate。 So just return。

Now， if it's not the same， then you got to look at the left， look at the right。Right， if。

Current route。Dot data。Dot compare to。To add。Well assuming there are no now data。

 or if there is no data， you still have to。Then the ordering can be problematic。

 So if this thing is sorry， less than 0。Which side should I focus on。So my data is less than to add。

I should focus on the right side。If the current rules say is less than to add。

 I need to focus on the right， Do I just recurse to the right immediately。No， you don't。

 If you do that， we' are in trouble。 right， So you got to check。 Do I even have a right。

If current dot， current root， dot right。Is the same as no。 In other words。

 I don't even have a right child and。This right pointer is the position you're gonna insert this new node。

Right， so you're gonna say current route。Dot， right。Equals a new Tn。To add。And then， I would return。

Chu。If it's not now， what do I do。You will recurse to the right。So you， you say add helppper。

Current dot， right。To add， Am I missing anything。Or recurs to the right， yeah。I need to return。

 right。 Don't forget。 if a recursive function returns something every time you recur， re recursse。

 you have to call return to give back that value。 right， And that's it。 So this is the left side。

 And then the sorry， this is， this is the left side in here。 You will write it by。 But this is。

 we insert to the right。 We insert to the left。Does， does this make sense。

 The code is pretty standard， you know。嗯。All right。I think we can stop here today， okay。

Once we come back on Monday， we'll talk about remove。And then。Tversal， the three other traveral。

 well done with be with B SD at that moment。So enjoy your weekend。 I'll see you on Monday。

 I see you on Monday。

![](img/df732bace088052ea7f3aa639be05f76_2.png)