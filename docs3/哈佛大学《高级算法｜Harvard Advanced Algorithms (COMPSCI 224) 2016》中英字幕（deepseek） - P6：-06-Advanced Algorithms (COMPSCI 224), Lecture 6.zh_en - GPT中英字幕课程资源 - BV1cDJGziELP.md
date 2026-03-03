# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P6：-06-Advanced Algorithms (COMPSCI 224), Lecture 6.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/f4720edd7a0ec564620c944f4a2d3a3b_0.png)

I guess I'll get started。Just a couple things。 One is I just put a poll on piazza。

 I meant to put this in PS at one itself。 Please let me know how much time you spent on piece at1 I want to monitor how much time things are taking。

嗯。Another thing is we did have a scribe for September 30th， which is a week from Tuesday。

 We no longer do。 so please someone take that slot if you have a later slot and want to switch and be earlier。

 that's also very good。Another thing is our videographer has asked if anyone wants the board shot differently or anything in the videos。

 please yeah let us know。Okay， so。Oh， and also， I， I fixed the。To。Bugs off by one in cuckoo hashing。

 and thelumni I didn't actually prove for power of two choices。

 It's fix in the notes so you can go read it if you want。Okay， so。

We're going to start a different topic today。嗯。We're not going to。

Operating Word RAM anymore at least for now， we're going to look at amortized analysis。Okay。

 and we're going to start off with data structures。

And the two we're going to look at are Fibonacci heaps。Well， we'll look at。

We'll look at something else right before Fibonacchi heaps another heap。

 and we'll also look at Sp trees。Okay。嗯。Okay。So I think people people who took 124 here。

 like people who were undergrads here， I guess you've seen some amount of amt analysis。

 well at least。One bit of it when we did Union find。Okay， but。We're going to say a little more。

 so what's the idea behind amortize analysis？So amortization。Or amortd bounds。We'll say like suppose。

Our data structure。ok。Supports。Some number of operations。Operations， you know， ABC。Then。We say。Li。

Amortized cost。Aortise costs。Of these operations。Or。Let's say T sub A， the time for A。

 T sub B and T sub C。If。Any sequence。Of。NA operations。And NBB operations， et cetera。

 and NCC operations。Takes time。At most。呃。And a T plus NBTV。Plus N CTTC。So the idea is。

 so usually we talk about worst case running times for say data structures。

 so a balanced binary search tree， a red black tree takes login time to do a search。Okay。

If we say that it takes login， amortize time to do a search。It means that。

If we do n searches in a row or some number some k searches in a row on on on a data structure of n items。

 then it should take us at most K times login steps total。

 So some of these operations can be expensive， some of them can even take linear time。

 but as long as the sum of all the time we spent is at most。As fall as this。

 then we say that that's our amortized complexity。Okay。And we're going to see。Some examples。嗯。Okay。

And a common way of。Giving proving amortized downs is what's known as the potential function method。

And we'll see this with Sp trees， sometimes。This can get a little。

Sometimes it can be weirder than other times， but so a common way to prove amortise bounds。

Is via the potential function method？So what is that？So。We define a potential function。

Let's call it capital。 Call it fee。It maps。States。State space。Of our data structure。Okay。

Into non negative reels， let's say。I don't know if that's the usual notation。

 somehow I feel like it should be at。Okay， and also。Phi of like an empty data structure。Is0。Okay。And。

So， let's say。Let's say that。We perform。K operations。With。嗯。Costs， actual running times。T1。TK。

 So here I mean， I don't mean we support K different types of operations。 I mean。

 suppose we actually have a sequence of operations on our data structure。 for example。

 K insertions or K searches or something。 And the actual running time of each operation of the I operation is T I。

Okay。And。The states of the data structure。Or。S0 before we start any operation， S1 up to SK。

So SI is the state of the data structure after the IF operation。

 S zero is before we do anything at all。Okay。So。Our amortized cost。Okay。Our amortized cost。

Of an operation。Is we define it to be。Defined to be。The actual time plus the potential difference。

Okay。And why does this make sense？So the total。Amortized cost。Oh， sorry， this is not the deficit。

 This is not。This is not what I wanted to say。 I guess what I wanted to say is so this is what I define the amortized cost of a sequence to B。

So， I'm going。So I want to say we'll show that this is the case is going to be is bounded by。

 let's say。The amort cost of one given operation is bounded by this， and why is that the case？

Let's sum this over all operations， so the total amortized cost。呃。Is。We're bounding it by。

The sum over TI plus the difference in potential。But this is a telescoping sum。

 and all we're left with is the sum of the actual costs。Plus， the final potential。

Minus the original potential， which was zero。If we started with an empty data structure at zero。

Which is certainly at least the actual。 remember that Phi maps into positive numbers。

 So this is at least the actual cost。对。So definitely if we。

If we define or if we bound the cost preparation as this thing。That will give us a correct。

A correct upper bound on the actual cost？So then we can say that the amortized cost。

So so if we look at a given type of operation like an insertion or a deletion or a search。Then。

It's okay for us to say that the amortized cost per operation of that type is what's the worst case of this quantity。

For that type of operation。Okay， so that was all kind of slightly abstract。

 So let's actually do this for something。So I said we're going to look at Fibonacci heaps。

 before that let's just refresh our memory on heaps。So。Example。Is heaps。

So a heap is an abstract data type， what does it support？Supports。Insert。呃。Let's say。Insert X。

Where it just inserts into the data structure， let's say that。X。X some。The values x。Are comparable。

So you can do less than and greater than on x's or some。Total ordering on them。You can also do。

Delete min。Okay。This。Returns。The min X。Let's say we have a heap， a heap H。The min X and H。

And then deletes it。And then there's decreased key。Which。

Takes a pointer to some item in the data structure。Say yeah。P is a pointer。To item。

And this k is a key， is a comparable element。Okay。And what this does is。Replaces。The key。At P item。

 at item P， PP is a pointer。With K。Which must be。At most。P's current key。

So this is just an abstraction of。The kind of data structure you would need to implement。

 for example， Dys's algorithm。Okay。Do youRemember Dexter's algorithm？For each vertex。

 we insert it into a heap。With key infinity。Except for the thing we're searching for。

 which we give key0。And then in a loop， we keep doing delete bins。

 and then the relaxed step is a decreased key， Basically。

 so you can go revise your memory if you forgot。But this is exactly what。Thankss for needs。嗯。

So diykstra。Single pair of short is passed with nine negative graduates。

The run time I mentioned this last time。Is。Oh of。N times， let's see。You do n insertions， you do。

And delete mens。And times， insert。It's say time to insert。Plus， time to decrease key。Plus。

 M times time to do a delete min。Where n is the number of vertices and M is the number of edges。Okay。

 so。What kinds of， you know， what's an implementation of a heap。So。

Implementation of the he data type。So we have binary heaps。That's due to Williams。In 64。

What does that give you all operations are worst case log end time？Insertion time。

And delete mid time。And decrease key。Are all O of login。Okay。We also have binomial heaps。

I think these are due to Gilamamine。A vamin。Oh yeah， and I should have checked。 I do have a scribe。

 right。Okay great。Okay， and what does that give you， So these are now worst case。

But if you're using your data structure inside some algorithm like this。

 you don't really care if your bounds are worst case or amortized。Right。

In mean worst case is a stronger property， but。Depending on your application， you might not care。So。

Good， so what does he get， He gets an amortized。TI being constant。And。Let's see， decrease key。

And also delete men。Login。I guess that's also， that's actually a worst case bound。

 So the other two are worst case。 So worst case。Tea deleteman。And T decrease key are both login。

Question。The bound。OhM times decrease key， sorry， yeah。Yeah。Okay。So this is。I guess a little better。

And the worst case， the worst case。Of T insertion， the time to insert is also login。

 So in the worst case， it's no worse than binary heaps。And at least up to constant factors。

 but the amortized insertion time is better。Okay， that's not enough to speed up Dykesworth's algorithm。

And then there are Fiminacci heaps。hing that's from 87。This is due to Fredman。And Tan。

You're going to see Tarjent a lot in this class。How did we see them already， now。

 I don't think we've seen Taarjn yet。But Fibonacci heaps s trees will also see him for cash replacement policies。

Okay， so what femino heaps， what do they give you？So they give you amortized。Insertion time。

As well as decrease key。呃。Delete men， sorry。No， no， no， decrease key。Okay， being constant。

And they give worst case。And also。What do I want to say， delete min。Is log in。

These are all amortized bounds。Okay， so diyketra actually gets faster because the login。

Doesn't multiply it。I'll say a little bit more。 so I'm going to assume you know binary heaps。

Or if you don't， then you can look them up， they're not going to be relevant for what I'm going to talk about today。

And they're not too bad to pick up。 I'm gonna actually。Cover binomial heataps， just because。

I think the best way of understanding Fiinacci heaps is an optimized version of binomial heaps。Okay。

 you'll see like once you see binomial hes， you'll see where feac heaps come from。아。

And then I'll cover for Menacchi Heaps。 There are two more things that happened afterward， which I'm。

Not going to cover， but I'll give you the pointers。One is Garret Brual。Okay。This is in soda。96。

What does he do？Gets all the same bounds。As Fiminacci heaps。But worst case。Not amortized。Okay。

And it's not and he uses。So， okay， so， yeah， so he gets that。

And then theres a paper by Broal Tarin and one other person whose now going dispel Lagogiians。

Then there's a brutalal。Lago Gians。And tarin。That's just two years ago， stock 2012。Okay。So。

They get the same。 They get the same exact bounds。 The thing is， theyre sort of。

Weaker and weaker models of computation， like word Ram。 you saw you can do lots of stuff。 right。

 I have a question。 So these， I'm going to tell you that these data structures。

 these three are all comparison based data structures。 The only thing they do with items。

 the keys is compare their values。 Okay， so why can't you hope。For why can't you hope to get。

 you know， all of these constant， Why should one of them， Why should deleteman be logged in here。

Yeah， these are heap sort。 You could always， if you have n items you want to sort。

 you could always insert them all into a heap。And then repeatedly delete min。

 So if all your running times are constant or amortized bounds， even。

 you would have a constant time sorting algorithm。Okay， which is impossible in the comparison model？

But we saw that in Word Ram， you can do some things faster than in comparison， right。

There's this game and data structures of kind of getting bounds with the weakest model of computation。

So once you get something in Word RA， you can ask yourself， did I really need the power of Word RA。

 could I get it？In the comparison based model， Okay。

 or maybe all I need is like a random access in arrays and to array entries。

 But I don't actually need bit shifts and xhors， etc cea。Okay， so B solution uses， I think。

 random access in arrays。 I don't think it really needs more than that。 Maybe I'm mistaken。

 but this is actually just a pointer machine implementation， okay， so。They yet。呃。Same as above。

Just using。Pointers。With no arrays。Okay， so。I mean， as you're going to see。Well。

 you're not going to see that。You can implement this using an array。

 it makes indexing your parent and children a little easier。

 but you don't really need them here you're just going to see pure pointer raised implementations。

 yeah。Yeah， yeah。 so， right。 So we saw， we saw， I guess， fusion trees and。And Vanom de Boez。

 So they right， So the better of them。Gets。Basically， you can do every operation in， let's say。

 root log n。Yeah， you can use them to implement。Keeps。Yeah。

And all your operations would So if you take the min at the better of fusion trees and Vanom de Boez。

 you would get everything in root log n。Although what I you presented in class was a static fusion tree。

So it didn't support insertion or deletion。 it just supported。Querries。

 and I guess if you're just searching for the min all the time， it's not really interesting。

 but there is a dynamic implementation of， of a data structure achieving the same bound as fusion treess。

So I asked last time who had seen Fiminacci heaps out of curiosity who's seen binomial heaps？Okay。

So let me just。So some people have， but many haven't， let me tell you what binomial heaps are。

And then from there， we'll see how to get Fibonacci heaps。Yeah。Yeah。So take like。嗯能。Yeah。

 there's like the pre processing phase that could be expensive。Okay。Okay， oh， and what。 Oh yeah。

 okay， good so。Bomial heaps。And I want to say one more thing。

 actually just I'll put one more reference up here。嗯。Who are these folks。

 So there's also a paper on the archive just this summer。So。Kaplan。Tarin。And Zwick。On the archive。

This summer。So what do they do， So they don't actually improve any bounds。They just， so you're gonna。

 you're gonna see with binomial heaps。 So okay， so， so for the people who have seen who， who has not。

 who， who has seen binary heaps， raiseise your hand。Okay， so almost everyone， not everyone。

 but a binary heap is a tree。 It looks like a tree， okay。

As you're going see with binomial heaps and fibonacci heaps， they're not trees， but forests。 Okay。

 we're going maintain all our items in a forest today within a forest looking thing。

They show how to get the same bounds as Fibonacci heaps， where you never have a forest。

 like it's always a single tree。Okay， so just so there are like just different variations on。😊。

Making things simpler to implement or nicer for whatever reason。呃。

I'll just say also see that favor if you want，But there are no improved bounds in there。Okay。Yeah。

 I guess part of the issue is femonacci heaps are known as having。Somewhat you know， large constants。

 So you wouldn't actually use them in real applications。 So then now。

People are trying to simplify them in various ways and hope that one day they'll get Fibonacchi keeps people will actually。

Used all over the place。Okay， so binomial he。So， we'll maintain。So， sorry， okay， so each item。

Is a node？And。We maintain。These nodes in a forest。Okay， and also。If。🤢，X is the parent of y。

Then the key of x。Should be at most the key of y。Just like in binary heaps。So for example。

 you could have。You could have 5，722。But you couldn't have a seven up here and a five below it。Okay。

Now。For a tree。In our heap。It's。Rannk。Is the degree？Of its root。

And what we're going to maintain is that and also a tree。With rank K。We'll have。

Exactly two to the K nodes in it。Also。For each K。We'll have。At most。 So very soon。

 I'll start drawing a picture。 And then this will be very clear what I'm talking about for each K we' have at most。

1 tree。Of Raquet。And also。The root of rank K。Has K subtes。And each。And。And these are。Trees。Of ranks。

Yeah。Z，1 up to k minus1。Okay， so let's just draw a picture。So what does a rank zero tree look like？

A rank zero tree just looks like a node。A rank one tree。Well， I have degree one。Okay。

 the root has degree1， and this is now a rank  zero tree， which is just by itself a rank 2 tree。

It has a child which is a rank zero and a child which is a rank1， which means it looks like this。

And a rank three looks like this。That's a rank zero child。That's a rank one child。

And this is a rank two child。Which means it has a rank zero child and a rank one child。Okay。

 so that's， and remember， these keys should be stored like as you go from。

 as you go from any node to its parent， numbers should decrease。Okay， so that's。嗯。

That's what it looks like。Good。Now。How do we do the operations？So decreased key is the easiest。

We're giving a pointer to some element。And we're told that we're decreasing its key。

 We do the usual thing with binary heaps。We change its key。

 and now it might violate the heap order property。 It might be smaller than its parent。 If so。

 we swap it with its parent。 And if it's still smaller than its parent。

 we swap it again and we swap it up the tree until it's in the right place。 So change the key。

Then keep swapping upward。As necessary。Okay。How about？Inserting an element。 we'll store， you know。

 maybe this is actually what our binomial heat looks like。 So we'll store all these roots。You know。

 in a linked list or something。In a double linked list。Okay。嗯。So what do we do， We take x。

And we just added onto this linked list， so now here's our value X。we just inserted X。

 but now we're violating our property that we should have at most one tree of rank K because now we have two trees of rank zero。

Okay。So what do we do？We basically do binary edition。So you can write a bit vector。

Where you have a one in the k position， if you have a tree of rank K and you have a zero otherwise。

And now we're like adding one。 we just added one element。

 so we're adding one in binary to this number。Okay so。One and you know， so currently。

 our data structure looks like we have a rank 0 tree。 We have a rank 1， we have a rank 2。

 we have a rank 3。And now we're adding one to this number。And that's going to give us 1-0，0，0，0。

so what's going on here， well， we're going to merge these two。Okay。

 so let's say X happens to be bigger than that element。X will get moved。Here。Oh， now we have twos。

 so now there's a carry。We have two。Rank one trees。 We need to merge them。

 One will be the child of the other， just depending on the roots。Okay， so。For example。

 maybe this guy。Hangs off here now。And then now we have two rank twos， there's a carry， we add them。

 et cetera， until finally this will all merge into a rank for tree。Okay。So。Add in you。Singleton tree。

Treat a forest。Then。Repeatedly。Merge。Trees。Of equal rank。And delete men。It is very similar。

 delete men。Is as follows。Okay， so one of these roots。Let's look at this picture。

 One of these roots is the minimum。 It could be any one of these roots。

So let's say that's the minimum。哎。So what do we do？We return it， we delete it。😡。

And all its children now become roots。All of these children become new trees in our forest。And again。

 it's like binary edition。So we have to merge things of equal rank。And what ends up。

 what trees do we have， Well， we have the trees that。Correspond to binary adding this number。

 namely so this is basically11 to what's left up top。So delete min is。Remove。The root。Of some tree。

 namely the minimum。And insert。All its children。As roots。In the main forest。Yeah。Well， I mean。

 so they're only， we're only shooting for a better amort band for insertion。

 And because a rank K tree has exactly two to the K nodes， we know that。

The highest rank possible is log in。And also because we know that there's only at most one tree of each rank。

That implies that there are most login。Trees in our data structure。So。You know。

 finding the smallest guy will take at most log in time。 we can just check all of them。Yeah。Okay。

 so good as roots in the main main forest。Now。Merge。Equal。Ran。Trees。Sure。Okay， good。

What's the worst case time？ So I， I said we're shooting for insertion， taking。Constant amortize time。

 What's the worst case time for an insertion？Log in， right。

 because we could be in a situation like this where。You know。

 we have a tree of every possible rank up to log n。

And then well have to keep repeatedly merg as we carry。As we have these carry bits。Okay， so。And all。

 it's true for all of the operations， in the worst case。All operations take log in time。

We want to prove a better amortized bound， and we're going to do it using the potential function method。

Okay。So。Remember， when we're going to bound the amortized cost preparation by the actual cost。Okay。

Plus， the potential difference。 So we need to define a potential function。

Which is always not negative。And。So it takes as input， a state of the data structure。Okay。嗯。If。

 if we're looking at a picture of the data structure， do does anyone have any ideas of。

Of a good potential function。Well， first of all， tell me this。

What's the time it takes to actually do an insertion？So I mean， login is the worst case。

 but say it in terms of what we're actually doing。The smallest。Rannk for which you don't Yes。

 that is true。嗯。That is true。Okay， so maybe。Right。Which is which is， yeah。 so I think that's。

 that's right， yeah。The number of。The number of trees already have。 That's right。 So， so let me。

 let me just say something。 So the actual cost， may say actual cost of an insertion。Is。嗯。Big O of。

The number of trees we have， let's say， yeah， so let's say t minus T， which is。Plus one。This is the。

Old number of trees。This is the new。New number of trees。Okay。So。

So I'm going to define the potential of the state of the data structure to just be the number of trees。

And now let's look at the cost of an insertion。Remember what I said it is， it's the actual cost。Plus。

 the potential difference。Okay。And let me see this big O is， let me just ignore the big O for now。

 There's some， say， constant times this。So I could put a constant on the outside of this and then put the same constant there that's not really going to matter so much。

So， the actual cost。This is the actual cost。Plus， the potential difference。So the actual cost。

We said it was t minus t plus 1。And what's the potential difference？Oh， and what do you know？Okay。So。

That's it。And you could look at also the amortized cost of the other operations。

 The actual cost will be certainly at most log n。 I mean， for the others。

 we're just getting a log n bound。 The actual cost is certainly at most log n。

And the potential difference。I mean， you're never going to have more than log entries trees anyway。

 so you're going from some number less than log n to some number less than log n。

So the other operations。Also， with this kind of calculation。We're bounding them by login too。Okay。

 so that's。That's basically it for binomial leaves。Okay， so now I want to get into Fiminohi heaps so。

What Fibonacci hes trying to。Achieve。So they're trying to achieve constant time insertion and also constant time decreased key。

Okay。So the main idea of Fibonacci heaps is。To be lazy。Okay。

 which is the main idea behind a lot of amortized data structures and don't really do work until you're at the point where like you really have to do it。

Okay。So。One example of。Being lazy。Is so wait， so delete Minten is going to take log n。

 Deced key should take constant。 That's right。So one idea to be lazy is， first of all。Why。

 so as soon as we do an insertion。We enforce that。This thing holds， right？

We do merges as soon as we do an insertion。There's no real reason to do it。 I mean。

 if all we do ever in the data structure is insert。Then。Why bother doing any work。

 just like add that element to the top of a add it to a linked list， okay？I mean。

 the only reason we do this me thing is that the other operations are faster。Like for example。

 the elite men。So why don't we just make the delete min do all the work？

So there will be lots of nodes up in this top linked list， lots of trees。

 And when the delete Min need comes along， he'll consolidate everything And when， you know。

 when he gets called， the insertion doesn't have to do it。 There's no reason for that。So。

There's no reason。For insertions。To spend time。Time consolidating。Do all consolidation。

During delete Min。Okay。Okay。But it's not delete men。 we're trying to speed up。 It's a decreased key。

And it looks like decreased key is in bad shape， right？

If you're in a tree that has big rank and you're doing this bubble up stuff。

Then you're going the height of the tree， which is log n。So。

If someone keeps doing decreased keys over and over again in the large rank tree。

Then we're out of luck， right， and they can do that。So what's， what's something extreme， I mean。

 it's not going to work。 But just tell me something ultra lazy that you could do。

To implement decrease key。I want decreased key to take constant time， yeah。Yeah。

 just so if I wanted to decrease key。If I want to decrease key on like say this guy。

Let me do someone that actually has some children。 let's say10 key on this guy。All decreases。

 so first of all， I'll update him。and if he doesn't violate the heap order property。That's great。

 I don't have to do any bubbling up。But if he does violate the heap order property。

 I'll just cut this edge and just put him up as a tree。Okay， great。So。Really lazy decrease key。

But it's the right idea to， you know， first start off really lazy and then figure out if you need to do more。

 just do the bare minimum to get the job done。 You know， really lazy decrease key is decrease。

Decrease x is key。And if x now。Is smaller than parent？Cut X's tree。Out。And place。As a top level tree。

In our linked list。Okay， so。Unfortunately， being this lazy。

I's not going to get us the desired bounds。 It can be pretty terrible。Okay。And。The main reason is。So。

What was the actual cost in binomial heaps， What was the actual cost of a delete min or let's say a delete min。

 the actual cost of delete men。This is not a trick question。 So what was the cost of deleteman。

In a binomial heap。What does a deleteman do？It has to like look through all of those top level routes。

Find them in。So let's say that。The maximum rank in your tree is K。 It looks at K different roots。

 finds them min。Then deletes that out of the tree and then puts the children in and then merges things。

So in terms of K， what's the worst case running time？K， right， So of K。And。

What was the argument that we said for why， So what K is that most what， What's the worst case for K。

In a binomial heap。Log in。 And why is that， What was， What was the justification for that。嗯。

each tree sub size2 to the K， we only have n items。

 so we can't have a tree of rank bigger than log n。

But the problem is that start if we use this really lazy decrease key。Then。You know。

 we could have a tree。Of rank K。That has a lot of stuff hanging。O of it。 Well。

 I guess nothing's hanging off of that。But over here， a lot of stuff is hanging off。

And then we did a bunch of decreased keys on all these guys。 We decreased key all these roots。

Let me not。Decrease key them exactly， let me decrease key to their children。Okay解。

We decrease key all of these guys。And what we're left with at the end of that。Is a tree of rank K。

That has exactly K plus1 items in it。RightSo our previous argument that rank K trees are big。

 therefore the largest rank in our tree is small， therefore delete min doesn't take too long。

Is bogus now？And so really， what's happening is this guy。He's ranked Ky。

 and he thinks his tree is big。 But， you know， little does he know that he's losing all of his descendants。

Okay， so。We need to somehow convey。We need to somehow like convey to this guy that he's losing his children。

Okay， or his descendants anyway。Okay。So here is the one extra thing that Fibonacci Heaps do。Okay。

Which is。If。So if P loses， let's say if node。P loses。One child X。Due to decreased key。No problem。

Okay。But if P loses a second child。We cut P out of the tree， too。And we make peas tree。

A top level tree。Okay。Yeah。Do we also copy。Yes， this might recurse。P itself has a parent。

And P might be the second child lost by its parent。

And its parent will then cut itself out of the tree。Okay。Yeah。Yeah。Also， not。Ch。Yeah。Yeah。Do this。こさ。

Oh， so yeah。 okay， so to answer your question。 So let's say P loses a child X。

 that's the first child Okay， and now loses another child Y。

 So Y subre is now a main tree in the in the top level。And then separately。

 P and what's left under P will be another tree at the top level。

So P and X will P and Y will no longer live together in the same tree。

 Does that answer your question。Okay， so now let's take a look at。Let's take a look at。

What a tree of rank K can look like？In a Fibonacci heap。Let's say the rank。Is 0？Okay。

' look like this if the rank is one。It looks like this。And。

This is what it would look like if it were a full rank in tree， like in a binomial heap。But then。

 you know this。We can we can't then cut out any children because it wouldn't be a rankin tree anymore。

How about a rank two tree？Well， it has two children。And this one is a rank one tree。Okay， and now。

This is what we were looking for we're full。But we could have done a decreased key。

At some point in the future， we could have done a decreased key on this element。

And then now this gets cut out and made a top level tree。

 So we could it's possible then to then lose。 is this visible。

 I don't think this thing is that visible。It's then possible to lose。This， this part。

So let's say the size。Of a rank。Of a rank K tree， the size here is 1，2，3。 How about a rank。

Three tree。So that's what it would look like if it were full。

But then we could start cutting things out。So maybe this guy got decreased keyed。Okay。And now。

 maybe this guy here got decreased keyed。 So we lost all of this。Now。This guy， this guy here。😡。

We can't afford to decrease key him because then this guy would cut himself out of the tree because he lost two children。

 and then the rank wouldn't be three anymore。Okay。So I think this is the most that we can cut out of the tree and still keep it a rank3 tree。

And the number of nodes left is one， two， three， four，5。Let's just do one more。

 habit if we had a rank four tree。So it has four children。This guy looks like this。

 this guy looks like this。And this guy is a rank three tree。So he has。One here。This is a rank 2 tree。

呃。Did I do that right？I have one more node than I'm supposed to have。

Where did I insert an extra node？This。So this should have been a rank three。So this is a rank too。

Okay， good， so contract the a yeah， okay good。So。Okay。は。😊，Okay。

So now that's a proper rank for a binomial tree。Okay。

 so now let's try and cut out as much as we can cut out and still keep it a rank for a tree。

We can cut this out。We can cut this out。We can cut。All of this out。And we can cut， I think， this out。

I think that's all we can cut。And we're left with。1。2，3。Four， five。6，7，8。Okay。

So there's a pattern here。Okay。呃。Right， as you might have guessed。A rank K tree has。Well。

 it depends on where you start indexing Fibonacci numbers。

 but it has at least the K plus2 with Fibonacci number。As its size。Okay。So great， so anyway。

 we need to put all of this together。Me it actually prove something， okay。

 instead of just talking about。Ideas of how to be lazy。Okay， so the claim。For amortized。

Amortized T of insertion and T of decrease key。Are both constant。And T of delete min。Should be。

Oh I bloglog yet。Okay， and。You know， how do I know that。

A node should be cut out when it loses a child。 So for each node， I'll just keep track one bit。

 Have I lost a child yet or not。Okay。And， when I do cut myself out， I'll reset that bit。Okay。

So it doesn't stay。 so that's usually called mark the mark bit。

 if you read the paper or read other people's descriptions of Fibonacci trees， Fiacci。Yeah。

 heaps or whatever Okay great so proof。So first of all。Just some notation。Let。嗯。Let's say。Mark of X。

Is one。If x has lost。A child。And zero otherwise。Okay。Then I'm going to define a potential function。

My potential function。On some state。Will be。The number of trees。Plus。

Two times the number of marked items。Let me just call this， I don't want to keep writing this。

 let me just call this。Trees of H。And let me call this number of marked items of H。

That's gonna to be my potential function。So where do these potential functions come from？Usually。

 you just try to。Mean。Usually theyre just engineered from trying to make a proof work。 Okay。

 so you look at what you do is you look at the state of the data structure and you say after I do an operation。

 what changed， what changed after that operation。 Well。

 the number of trees changed and some things that weren't marked now get marked and some that were marked get unmarked because I cut them out。

And then you try and engineer these constants or engineer some function here to make everything bounded by what you want。

 Okay， so。It's。It's something that will make sense， I guess， in hindsight。

But the intuition is basically a lazy binomial he。ok。So now let's bounce some costs， question。Okay。

Insertion。So。What's the actual cost， what do we do for an insertion， do people remember？

We're being super lazy here。We're just adding it to the top level linked list。 So the actual cost。

Plus， the difference in potentials。So the actual cost is a constant。And the difference in potential。

Well， we have one more tree。The number of marked items hasn't changed。So this is one。

So this whole thing is a constant。How about delete Min？Again。

 we have the actual cost plus the difference in potential。So now。🤧But。What's the actual cost？咋了？

Se in。So。Yeah， yeah。Comp。Oh right， so yeah， yeah， so you have to go through the entire list。

 and also I should say in Fiminacci heaps。We'll keep track of where the men is as well。Okay。

But I guess that won't。 that won't。 We don't actually need to do that because we're spending that amount of time anyway。

 But， so， yeah， the number of trees。 So let's use this notation。Okay。So we have to spend T time。Okay。

🤧And。Good， so what's now the difference in potential。I'm sorryrry。Okay， I have a question。

 So how much the number of marked items， how much did that change by。They almost zero。

 so the guy we just deleted might have been marked。Maybe I don't know。

 So it might have gone down by one， but that's like， that's lucky。 I mean， yeah。

 so let's just say it's， it certainly at most 0。So the difference in， let's say。

 plus the difference in the number of trees。Plus， the difference in the number of mark items。

 this is certainly at most zero。No one's marked， no one's being marked or not gets changed by deleting the in。

 And the men himself might have been marked。 Who knows。 Okay， the number of trees， though。Yeah。

That's t minus t。So。This is going to be。At most， let's say this is。Oh， of。U。Small tea。Okay。

 but so remember， when， when we actually do the consolidation during a delete min。

 we will enforce the previous binomial heap constraint that at most one tree of a given rank exists。

Okay。So we know that we have at most one tree of each given rank， and we didn't prove it yet。

But we're going to prove that sizes grow like the Fibonacci numbers。Okay。

 and Fibonacci numbers grow exponentially。Okay so。This will be O of log N。

Because if we have a rank K tree。That means the tree has size at least f sub k plus2。

 which is exponential in K， so K should be at most log n。Notice I didn't actually， you know。

 that's just the picture。 I didn't actually prove it formally。'll， you know， it's a very short proof。

 We'll see it。At the end of this。And now decreased key is the last thing。So case1。嗯。X doesn't。Yeah。

Cut out。Because maybe the new key we gave it doesn't actually violate。The heat border property。

Then the actual cost is a constant。The difference in potentials， we don't change the number of trees。

 We don't change the number of marked items。Actual cost。Is a constant。

 plus the difference in potential。Is zero， so this is just a constant。Now， case two。As we do。

Some number。I didn't really have to split it into cases like this not I think about it。

 but we do some number C bigger than zero。Of cascaded cuts。When I say we do see cascaded cuts， I。

We cut X out of the tree。And then now because。Its parent was marked。 We cut it out of its tree。

 and then its parent was marked。 We do the C times。 There are sea levels of cuts that we do。🤧Okay。

 so。What's the actual。So the actual cost plus the difference in potential。

 We can split that into the difference in the number of trees and the difference in the number of marked items。

 So plus the difference。And the number of trees。I said T of H。Plus， the difference。

 twice the difference in the number of marked items。So what's the actual cost？是。😊，Say O of C。

And let me just skip all these those， so see。What's the difference in the number of trees？

The difference the number of trees is C。Right？And how about this thing？So okay， so first of all。

 yeah， so what's that？So yeah， so this is， if you include the two。Minus2 c。

 let me just think for a second do I believe that。Is there's， am I off by one， So -2 C。

 but I feel like I might have to add。So， if I cut。I cut an item。It's。No I see， so if I cut one。

 I clear here's Mark Bit。But then， yeah， I think there's an extra of one， maybe or something。 right。

 Like， let's say that， let's say I cut X。 And that's the only thing I cut。Okay。maybe plus two。

Let's say C is1， I cut X， and he's the only guy I cut。So now。

That means his parent was not marked before。So his parent is now marked。😡，But now x is marked bit。😡。

Can get cleared。Okay， so I haven't actually changed the number of marked items。Okay。嗯。Right。Oh， yeah。

 yeah。 Sorry。 So， but yeah， So So yeah， I move X， but its' market gets cleared when I move it。Wait。

But it might have been。I just want to say it's at most。Yeah。So yeah， oh， and what do you know？Okay。

So yeah， that's Fiminacci heaps， there's not really anything else to say。

Questions about anything yeah。Deleteman worst case。Yes。

 it could be linear because we could have done n insertions。

 and our whole data structure will be a linked list。That's right。Yeah。Ohs。I mean， okay so。

So you're asking， how do you design potential functions？Okay。

 so what you should think of potential functions as doing are when we do work at some point in the future in the data structure？

We want to charge the work we did to some previous operations。Okay。So we want to say the reason。

 So like for delete min。You know， we might spend N steps doing a deleteleting in。

But we can only do those N steps in delete min if there were N previous insertions that caused us to this。

And once that delete min happens， everything gets consolidated。 So basically。

 we want to say that that those end steps in delete min are charged to n different insertions。

So you should think of maybe the potential of the data structure as like a bank account。Okay。

 and when someone does an operation。They might deposit money into the bank account。

Which is what an insertion does。 An insertion like deposits one into the bank account because it increased the number of trees。

 And then later， people are allowed to spend。Some of the money that's been deposited。Okay。

 so they don't have to pay for it themselves。嗯。So I think maybe that's the right way to think about potential function arguments。

Right， so I guess insertion increase increases the number of trees and。Delete men。Spends that。But。

 let's see。I guess decrease key both。哦。Sometimes decrease key deposits， marks as money。

 and sometimes it spends the marks。RightIf there's no cascading， it deposits a mark。

And then it can spend it in a future decrease key。Yeah。系い。Why。Oh， but I mean， we still want。

 So the cost of an operation is。What's what's the worst case that this could ever be。

 What's the worst case that the actual cost plus Delta P could ever be。Okay， and in the worst case。嗯。

It could be that。C is 0， and then it's constant。Does that answer your question。Sees like we never。

Yeah。So。So。With coefficient of the two。 I mean， as long as you pick something that's at least2。

It would work， that's right。Are you worried because this looks like it could be negative？It's I mean。

 it's somewhat arbitrary。 There's not just， there's not just one right potential function。

 The main thing that we needed was that in the potential function。

 this coefficient should be at least twice that one。Yeah。Yeah。Yeah。ごなさい中う。媒。Right。Right。RightYeah。

 it's not a problem that could be bigger than Tuesday， right。Right。Any， any， yeah。I mean。

 then we'll say that the amortized of this operation was negative。 but I mean。

 usually when when we say that a particular kind of operation has。Adortize cost b。

We mean that in the worst case， the amortized bound will be blah。So in the worst case。

 C could be 0 and the amortized cost would be a constant。Okay。Yeah， or did you have a question？他さ。えさ。

いなか。Yeah， so every， so everything， all the actual costs have big O's here。

 which would hides some constant C。 And then you would multiply this whole thing by C。 Yeah。

 that's right。对人。More questions。Yeah。So， I mean， before， so， you know。

 what did we argue in the beginning about potential functions about this amortized analysis stuff。

Basically， to make it work out， we only needed that。Phi of the empty data structure is0。

And fee is always non negative。As long as those two things hold。

 then your amortized bound you prove will be an upper bound on the true cost of the sequence of operations。

Yeah。Besides this one。You mean， other than changing the coefficient in front of that。嗯。

So I wouldn't know how to formalize the statement that this is the only one that works。No， I don't。

You mean， something else that looks sensible， but is somehow conceptually different。

I don't know one off the top of my head。Yeah。Other questions。Okay， so。We have two minutes。

 I guess I'll just say next time we'll look at s trees。That's a kind of binary search tree。

 It gets the same job done as like a balanced binary search tree in terms of login time per operation。

 but it will be amortized。So in the worst case， play trees could take linear time。To do a query。

 but in an amortized sense， it will be log in， but they have a bunch of other。Amazing properties。

 one such amazing property is what's called static optimality。Okay。

So people who have taken 124 who took it last semester have seen it。 Otherwise， maybe you've seen it。

 maybe you haven't。 Suppose I give you N keys。And for each of the un keys， I tell you。

The frequency at which that key is searched for。Okay， and then I tell you， build。

A binary search tree which minimizes serving queries on this set of。Items with these frequencies。

 Okay， so you can do this using dynamic programming。 You can build the best tree。 Like。

 what do I mean by that， so。So a tree like this。A perfect binary tree is great in the worst case。

But if you have additional information。If you're told that。

If you're told that I always search for one of these two items。Then， you know， let me color them。

Then those people should be at the top of the tree， right？Okay。

 and then everybody else you don't really care about， they can be wherever you want， I don't know。

And you can make funny shapes， you can make it be like a perfect path。

Or like you can make it look like this。So it's really， really imbalance。

 just kind of going down like that。 are There are like sets of frequencies where you know。

 this is the optimal tree to build for that set of frequencies。Okay， so。

The amazing thing about Splay trees is that if you keep doing queries on them。

They keep adjusting themselves after every query， they don't know the future。😡。

Just given the clear you just ask， I'll adjust themselves。And if you ask。

 what's the cost of serving an entire sequence？They'll do just as well up to a constant factor as the tree you found using dynamic programming。

 which was optimal for that。For that。Set of queries。 Okay， so they they。

They balance themselves to achieve this what's called static optimality property。

 but they have other properties too。Okay。Great， so we'll see Spplay trees next time and I guess that's everything。

And please sign up someone for September 30th described that's a week from Tuesday。

And fill out the poll on Piazza。