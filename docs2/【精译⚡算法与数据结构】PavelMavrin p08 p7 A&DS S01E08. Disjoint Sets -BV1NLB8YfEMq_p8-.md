# 【精译⚡算法与数据结构】PavelMavrin p08 p7 A&DS S01E08. Disjoint Sets -BV1NLB8YfEMq_p8-

。🎼嘟推痛头。🎼。🎼The。So around today， we'll talk about the joint sets。



![](img/28c9233d5e4b13e38841e32339183a09_1.png)

![](img/28c9233d5e4b13e38841e32339183a09_2.png)

Or sometimes it's called union fine index structure。



![](img/28c9233d5e4b13e38841e32339183a09_4.png)

![](img/28c9233d5e4b13e38841e32339183a09_5.png)

Sometimes so called merch find， but it's quite rare solid。

 Usually it's called the joints or Union find。So it's not a special data structure。It looks。

Pretty straight， but， but it's。Surprisingly important in many algorithms we will discuss late in this course mostly in the next year。

 because we will discuss graph algorithms in the third semester it will begin。In in in the next year。

But maybe we'll use it in some other algorithms in the next semesters also。Mostly in this semester。

 we'll learn some data structure some ways， and later we use we will use this data structure to。

To make some efficient algorithms。少。

![](img/28c9233d5e4b13e38841e32339183a09_7.png)

So what is the drain sets？It's very simple little structure。It maintains the set of some objects。



![](img/28c9233d5e4b13e38841e32339183a09_9.png)

Let's say for simplicity that we have some M object。



![](img/28c9233d5e4b13e38841e32339183a09_11.png)

Oh， let's think you。1，2，3，4，5，6，7。

![](img/28c9233d5e4b13e38841e32339183a09_13.png)

![](img/28c9233d5e4b13e38841e32339183a09_14.png)

これら。So we have some seven objects。

![](img/28c9233d5e4b13e38841e32339183a09_16.png)

And these objects are grouped into some sets。So each， each object belongs to exactly one set。

 So we have some number of these joint sets。 So that's why， that's why it's called thesejo sets。 So。

 for example， here we we have like。

![](img/28c9233d5e4b13e38841e32339183a09_18.png)

Set of these three elements， these two elements and these two elements。



![](img/28c9233d5e4b13e38841e32339183a09_20.png)

![](img/28c9233d5e4b13e38841e32339183a09_21.png)

こ？So it's just just like we divide all elements into some sets in some principle。啊，哈哈哈哈。😊，No。

 we have no summertime in Russia。It was depreated a few years ago。それ。I have a Google calendar。

 if you are。If youre just， if you're afraid you may forget about it I have a Google column of my two teams。

Some you may just copy this calendar into your calendar。

To make sure we will not forget about future elections。我 was talking about。就这样 said。

 so we have some objects， these objects。啊。You can download this calendar from from the Titch description it is somewhere in the bottom of the twitch。



![](img/28c9233d5e4b13e38841e32339183a09_23.png)

诶。That's both。嗯，好。Here， so we have some elements。 They are divided into some sets。



![](img/28c9233d5e4b13e38841e32339183a09_25.png)

So what。What we want to do these sets。 We want to perform two types of operations。 basically。

 it's union and find。 Why the second name of this structure is union find。



![](img/28c9233d5e4b13e38841e32339183a09_27.png)

![](img/28c9233d5e4b13e38841e32339183a09_28.png)

![](img/28c9233d5e4b13e38841e32339183a09_29.png)

Show separation in this union。

![](img/28c9233d5e4b13e38841e32339183a09_31.png)

哎。Union is， it's bad for for programming because union is a resort word for for C plus plus。

 so you can't make。Function named union。 So I usually call it something like unite or join or something like that。

But here I will write union because I'm not writing the+。



![](img/28c9233d5e4b13e38841e32339183a09_33.png)

What this function does， it gets two arguments。 We have arguments， X and y。



![](img/28c9233d5e4b13e38841e32339183a09_35.png)

![](img/28c9233d5e4b13e38841e32339183a09_36.png)

![](img/28c9233d5e4b13e38841e32339183a09_37.png)

And it simply unite these two sets， so we take the set that contains element X。



![](img/28c9233d5e4b13e38841e32339183a09_39.png)

s is government tax。We take the element， the set， which contains element y。



![](img/28c9233d5e4b13e38841e32339183a09_41.png)

And we just unite these two sets into one big set。

![](img/28c9233d5e4b13e38841e32339183a09_43.png)

So we have these two sets， so we make one big set like this。



![](img/28c9233d5e4b13e38841e32339183a09_45.png)

![](img/28c9233d5e4b13e38841e32339183a09_46.png)

![](img/28c9233d5e4b13e38841e32339183a09_47.png)

That's the first separation， which I take these two sets and make one big set out of them。



![](img/28c9233d5e4b13e38841e32339183a09_49.png)

And the second operation is to find the set which contains element X。



![](img/28c9233d5e4b13e38841e32339183a09_51.png)

It's usually called fine。 I usually write get because。



![](img/28c9233d5e4b13e38841e32339183a09_53.png)

And know for for historical reasons， I think。Well， let's let's make a motion this， let's say find。アX。



![](img/28c9233d5e4b13e38841e32339183a09_55.png)

そう。So this function returns the set which contains element x。



![](img/28c9233d5e4b13e38841e32339183a09_57.png)

![](img/28c9233d5e4b13e38841e32339183a09_58.png)

That's all we have。 they have these two operations。

 First operation is just unite to two given sets into one， and second operation is return the set。

 which contains the given element。 That's that simple。



![](img/28c9233d5e4b13e38841e32339183a09_60.png)

That's on now I。

![](img/28c9233d5e4b13e38841e32339183a09_62.png)

In the second operation， we need to return this set， which contains the element。

 So we need some another class of objects， which represents the sets。 Yeah， so we have the elements。

 and also we have the sets of elements。 So we need like two types of objects。

That's not very comfortable， so we have two types of objects。



![](img/28c9233d5e4b13e38841e32339183a09_64.png)

So to make it more simple。We will do the following instead of returning the set。

 which contains the given element。 We will arrange on one。



![](img/28c9233d5e4b13e38841e32339183a09_66.png)

Special element of this set。 So for each set。

![](img/28c9233d5e4b13e38841e32339183a09_68.png)

![](img/28c9233d5e4b13e38841e32339183a09_69.png)

Do is this。これ一セ。We will mark one element and say that this particular element is the representative of this set。

 So for each set， one element is special， let's say this element like this element and this element。



![](img/28c9233d5e4b13e38841e32339183a09_71.png)

![](img/28c9233d5e4b13e38841e32339183a09_72.png)

So these three elements are special elements。And each set contains exactly one special element。

 this element is representative of this set。And now， instead of returning the special objects of set。

 we will return to this representative of this set。



![](img/28c9233d5e4b13e38841e32339183a09_74.png)

![](img/28c9233d5e4b13e38841e32339183a09_75.png)

For example， here a for crawl。Find from element with say6。 It will return free。

And if you're called find。Of element and say 5。 it will on 5。



![](img/28c9233d5e4b13e38841e32339183a09_77.png)

So element 6 belongs to this set in this set，3 is a representative element。

 So we will shown three and element 5 belongs to this set，5 is the representative of this set。

 so we will on 5。

![](img/28c9233d5e4b13e38841e32339183a09_79.png)

![](img/28c9233d5e4b13e38841e32339183a09_80.png)

Important thing that the bread always return the same element。 So if you。

 if you call a fine from two elements of the same set， you will。

 you will get the same element each time。 So if you call like find。



![](img/28c9233d5e4b13e38841e32339183a09_82.png)

![](img/28c9233d5e4b13e38841e32339183a09_83.png)

From element to2。It will return the same element5。

![](img/28c9233d5e4b13e38841e32339183a09_85.png)

So this is how you may understand that two elements belong to the same set。

 So if you want to check if two elements belong to the same set。

 you call find from both these elements and check that this fine returns the same representative element。



![](img/28c9233d5e4b13e38841e32339183a09_87.png)

![](img/28c9233d5e4b13e38841e32339183a09_88.png)

![](img/28c9233d5e4b13e38841e32339183a09_89.png)

こ。You have to quiet today let's write something in the chats link。



![](img/28c9233d5e4b13e38841e32339183a09_91.png)

So I understood you everything is clear by now。啊。Let all we have these two operations。いや来ク。こ。Now。

Let's。First， let's discuss some very simple way to implement g sets。啊。Firsts implementation。

Very simple。

![](img/28c9233d5e4b13e38841e32339183a09_93.png)

Let's just make a rate， let's make a array P。And element in array P will be the representative of element x so each element of array。



![](img/28c9233d5e4b13e38841e32339183a09_95.png)

We have seven elements。喂。うんふんふん。、ととに。

![](img/28c9233d5e4b13e38841e32339183a09_97.png)

嗯嗯哼。せい。おった？So we make a array of size n and for each element of the array。

 we will maintain the representative of the set which contains element X。For element one。

 the representative is5。For element 2， it's 5。

![](img/28c9233d5e4b13e38841e32339183a09_99.png)

For three， it's3 for4。 it's 7。う。5。フ andセ。

![](img/28c9233d5e4b13e38841e32339183a09_101.png)

那'错。Now， let's implement these two functions。 Let's have this function find。 So how to find。



![](img/28c9233d5e4b13e38841e32339183a09_103.png)

How to find the representative of element X No it's quite simple。

 we just have the array of all representative of all elements， so we just look on this array。

 find the representative and the terms it's very simple。



![](img/28c9233d5e4b13e38841e32339183a09_105.png)

嗯。那走。Now， how to unite two sets into one。 So let see you of x and one。First， let's， mean。

 let's get a representative of these two sets。 So let's say X is the representative。Of the set X。

 And y is the representative。Off what。那。啊。what we need to do， for example， we have least two sales。

Is this X， this is Y？So what we need to do is just take all elements of one set。No， we need to first。

 we need to choose what element will be the representative of this big set。 for example。

 let's say that element Y。Will be the representative of this。You know of two steps。

 So so we need to take this big set。And set the representative of all elements and the set to y for for these elements。

 it's already y， but for these elements， we need to set the representative from x to y。

So we need to find all elements， which representative is element X and change it to y adjust。

Its there all elements。嗯， from不完了。It's quite uncommon to。Having in this is from one， but。

We started from one。 So lets， let's keep it。 let's from one to n and say if。

Representative of I equal to x， then set。Representative the white。That's all。So it's very。

 very simple realization of this。快点。哦，这里这里。

![](img/28c9233d5e4b13e38841e32339183a09_107.png)

No我。Let's go create the time complicated here。More is a tang mixture， No， for five。

 it's obviously constant。Anotherumber one。It's constantンスタ。And for union。

 it's obviously linear because we have this cycle， so we always make anys of these cycle。

 so it's big of。う哼。Yes， we will definitely blow over that on。That's just the first version。Okay。

 this is the simplest implementation of the digital itself。

 It's quite bad because union takes linear time。 We don't want to spend linear time。

Now let's talk here for a little， let's talk about。How many union operations can we perform in our。

デートソクョンふ。How fine is constant， we just look in the array and array look up， take constant。あ。

It's not a hash map。 It's， it's not even a hash map。 It's just right。

So we have very fast operation find， but very slow operation union。啊。だこかそうああ。

What I want to talk about is what is the number operation of union operation can be in your element。

😡，好吧。Since we only unite these sets into big ones。The number of union operation cannot be more than L minus1。

😡，So we cannot help。More than n minus-1 operations。

Well that's basically because in the beginning we have n sets and each union operation decrease number of sets。

 so we have one set instead of two sets， so we decrease in the number of sets。

 so in total we'll have no more than n -1。You my operationss。あ。そうなん？later。啊。

In data structures like this， then you know the total lifetime of your data structure。

 like if you know that number of operations is constant。

 so you start this sets and you only make n operations until you reach the final state of the data structure。

 you usually calculate not the single time of operation but the total of all operations。

So instead of calculating the time of single operation。

 we will usually calculate the total time of all unit operations。

That's more like amortism it's like the basic case of the amortized time when you calculate the amortized time you like divide the total time by the number of operations。

 but here you know the number of operations is already constant。It's's always will be end。

So if you just calculate the total number of equation divided by n， you will get the MR moreteta。

And in this case， the total time of all union operations will be。人と？So we'll be Nc。来吵。

That's all about this simple implementation。Nowレs moveと the somethingもも more。啊。Trustpiization。

Let's see what we're doing here。😡，Here we just it all elements。Which belonged to one set and。

Like move these elements to another set。 So we need to find all elements in array P equal to x。

And change it to white。So。Is it possible to iterate all elements with given value faster than just look on all elements？

can we just like in this array， we need to find elements with x equal to， let's say three？So。

 we need to find。These two elements。And change this to values 27， right。

Let's try to find these two elements。Without scanning the cho rate。

So how can we do this quite easily， We can just maintain the list of all elements for each value X。

 So so for each representative。Let's keep the list of elements。Which belongs to correspondent said？あ？

So1，2，3， I don't have。 I only have representative3，5 and 7。Let's get representative three。

 five and seven。嗯。So for free， we have elements， three and six。4，5， we have elements，1，2， and 5。

This list shouldn't be sorted， so have like for example， two， five， and one。And for seven。

 we have seven and four。And we also have empty lists for 1，2，3，4，5。ぞ。So let's maintain endlesss。

For each element X will maintain the list of all indices。Such that the value equal equal to X。

I go go back here， let's go here。So how can we rewrite this union？Let's say Excel， fine。X。

 y equal to find。我。Now we need to take all elements。😡，They have value equal to x。To do this。

 we just take the corresponding。This。We'll take these please。And it over these elements。

So we take these elements。Go in array and change these values to Y。呃。Let's go with the sentence。と？

So we take list of elements for value X。啊啊啊啊啊。So again。

 what is the change here instead of generating all elements。

 which rate only over elements with value equal to x。😡，So we don't need to make this check。

We only integral our elements with value equal to x and just change this medium。不位。うんLet'sそ。

 we also need to fix the list。 We also need to transfer these elements from this list。Do these lists。

 So this is X。 This is Y。So we need to generate all these elements。

Change the representative to Y and move these elements to this list。うんううん。

We also can clear this least， and they just。For simplicity。よ是。To free some memory。

 It's not important， but just。オッケー。That's从。No啊。Did we change something？In the tank complexity。

Let's think the find still works the same。 So the find function is still the same。

 So we just returned the value from R E。So it still works in constantantine。 What about the union？

Did we actually change the？とと。Time for the separationper。啊，不 wait wait it。It actually。

 it always can work in linear time。 so in the worst situation。Where， for example， we have。ああ。

One big set of elements。So we will iterate all elements here。ll iterate all elements of some big set。

 so the number of elements in this set can be linear。

 so this time the number of iteration of this cycle may be linear。嗯。嗯。Delete Mo。能吃吧Q mean。No。

 we never remove elements from the set and we never modify anything。To make two simple operations。

 We may unite to cells and。Check which set belongs to Gime。Maybe I don't get your question。一 go倍错。一。

What is什么啊我个。Again， let's think。This union function obviously may work in linear time。

In the worst case。This function may work many of them。But what is the total thing。

I is it possible that the total time is still in square？え？へへ。So is there a situation？When this。

Procedure is called n times， and the total10 complexity of all these ns is still about 10 squared。

Okay， let's do a think a little。while peace。O。啊。そう。

The answer is is possible that sometimes if you call this union function in wrong order。

 you may get a quadratic number of operations。For example， if you have an elements。

And in the first union operationeration， you unite these two elements。So the first union was。

So you call union from one and two。So unite these two elements。And you spend like， one operation so。

You need to change。啊。随变。そうい。So RA looks like this。So you called union for elements 1 and2。

 and you need to change the representative from one to2。 So you change this one to2。

And it costs you one operation。And now you call union for elements 2 and 3， for example。

So you need to change the representative elements from2 to three， so you change these two。Into free。

ワンエンジとこ。Free and free。And it costs you two operations。

And now you make Union of free and foreign and so。F free you need to change these three elements to force。

And it costs you free operations and so on。 So the total number of all operations will be about and square。

It is clearな。So we have this sum， the first operation costs to one operation。

 then it cost you a second second operation cost to two operations and so on。 so the sum of these。

Thankss。We'll be something like n multiply by M minus one divided by two something ahead。

So As big omega and square。よ。So it's not actually better than it we have here， so。😡。

We still have N square pattern complexity here。That's kind of said。Try to improve everything。

 but we have the same time complexity。ま。The good thing is that we actually can improve this by using the simple trick。

Let's look here， when you unite two sets， you have set containing X and second containing Y。

You may choose。Which elements。Which element will be x and which element will be Y？We have two sets。

Set X and set y。You may transfer all elements from x to y。

 so you may find all elements represent equal to x and change it to y， or automaticallyly。

 you can find all elements in this set and set elements set representative to x so you can move all elements from here to here or you can move all elements from here to here。

Let's look on the size of these two sets and let's make the x the smallest of these two sets。

So let's look on size of this list， for example。And if x is the bigger of these two sets。

 let we just swap them。So let's say if。Leastists。Of x size。Is bigger than。Listists of white size。

We just s them。And now x is always the smaller of those sets， so we always take the smallest set。

And transfer the elements to the bigger set。That's a whole trick。Quite easy， right？

Now was thing did we change something？第位啥。Let's look on the total time complexity again。 Now。

 this situation like here will not happen。Because， for example， if you unite elements  one and2。有嗯是了。

行我煮开火。Again， you have our AP P。 you have 1，2，3，4，5，6， and so on。

You make union of elements one and two。 so again， you check which which set is smaller and move elements from one to2。

 so you change this one， to，2。And now you make union of2 and three。

 but you see that the set of element3 is kept size1 and set of 12 have size 2。

 so instead of moving these element element from set two to set3。

 you move one element from set3 to set2 back。So we change these three。とと。

So it's always equal to one operation。Now again， you try to unite three and four。

 so you unite this to set， you have three elements here， only one element here。

 so it's faster to move this one element to this set。So you change this to two and again。

 cost to one operation。 So the total number of all operations will billion linear。嗯嗯哼。Yeah。Yeah。

Divorce case？Yes you。As you as we mentioned， the worst case is when we merge to sets of equal size。

 So when I have two sets of equal size。Then we need to go from one big set and transfer all elements to another big set。

These may happen。But。Let's think about the worst possible case。What is the worst possible case。

 Workors possible case is when you always merge to sets of equal size。

What will be the total time complexity？What will be is a little complex？Let's look on some element。

 Me you have one element。We have some element text。Let's look on the lifetime of these elements。

 Let's say how many time can we move this element from one set to another set。

So in the beginning we have element x in the set of for itself， so we have set of size1。Next time。

 when we will move the element to another set。Is when we will unite this set to with another set。

 So we have another set of size， at least one。So we willll combine this sets into one。

 It have set of size least two。え。Yes， and square or2 is the same as in square。 Yeah。

 no it's very complex。Here we we just get rid of full constants， So yeah。嗯，哼哼哈哼哈哼。😊。

The time texture of one operation is time texture of one operation is still linear。😡。

I'm talking about this total and complexity。Here and here。

 the time complexity of one operation in the worst case will be linear。 So we still。

 if we merge two cents of size n over2， So we have。One big set， another big set。

 we have N over two elements here， N two elements here。So in the worsts case。

 we need to transfer all these elements to this set， so we take N over2 operations。

 so it's still linear。Wort time time， time complexity from one operation is still in。 That's right。

But I'm talking about total time complexity。😡，So I want to calculate the total number of operations in all union operations。

うふん。嗯。And last time， the total total time was n squared。And I claim that now it's smaller。

 It's not not， now if we use this trick。The total number of operations of all union operation will be smaller than in square。

嗯哼。嗯。什么这给掰开。Let's try to calculate the total number of all moves。😡，そう。InIn the single operation here。

 what what caused the time complexity is caused the these for these， these loops in in each ho。

 we just move。 See this is one move operation。Let's calculate the total number of moves of all elements。

😡，During the lifetime of this day destruction。So we start from elements of sets of size one。

 so each element belongs to a special set containing only this element and each time we unite two sets into one big set。

So in total， we have rank -1。Union operationss， I want to calculate the total time complexity of this n -1 union operationss。

う哼ん。And I claim that it is smaller than and square。Becauseしで。Why it's small lemon square。

 Let's look on some element。Let's look on element X。

Let's see how many time we can move this element here。😡，そう。For each element X。

 let's calculate the number of times we move this everywhere。

 So we change the representative for element X。 So So how many times。嗯、ま。2 timess。

This P of x changes。So， if we calculate this， well calculate total time complexity。起こす。

title this total time complexity is central from this part。 And in this part。

 we just move element from one set to another。 So we change the representative for this element。

 If we calculatelate a total number of times， we change the representative for the given element。

 orll calculate total time。嗯。Pだ。So let's go back。So we have element X。In the beginning。

 we have the set of one element x。Now each time we move the element X。

 element X is moved to some set with bigger size。😡，First， we have element X in a small set of size 1。

Next time we move element we merge this element x of some another set。

 so we have element x in some set of size， at least two。Next time when we will move element X。

 it means that element x belongs to some set which is smaller of this to set。

 so when we will move this element X next， we will merge this to set and another set of size of least two。

😡，So element X will belong to some set of size， at least four。And so on。

 next time when we will move element X， it means that element X belong to， smaller of these to set。

So it means the theory。Unite our set with another set。We have size at least four。

 So we have some another size set of size， at least four。We make another union。

So the size of this set is at least eight。And so after each union。

 which causes the element X to move to another set。The size of the set， which contains element and X。

 is increased at least twice。So the total number of times when we move element x from one set to another is at most log of hand。

And that is true for each element。 So each element of our data structure is moved from one set to another at most low ma times。

说的多动呢。The total number of moves。Is the same as the complexity。I big o Ologgan。とえるな。Again。

 the you' required。Just say something。From time to time。Let's on。And this is actually。あ？

This is actually a quite important technique。😡，Especially so most of you come from school forces so you learn some competitive programming it's quite important technique when you need to make some mergeable data structure so if you have some data structure and you can like insert elements one by one and you want to make mergeable data structure you want to be able to merge to the structures into one。

So the easiest technique about to do this is just to take a smaller data structure and put elements one by one in the bigger data structure。

And if you do this， the total number of moves of elements from one this structure to another structure will be in loggan。

And you can see this in some task and for example， you have some tree and you need to calculate something on this tree。

 so for each you may take data structure from one of you need to unite all children into some big data structure。

 you have data structure for each child of the given node and you need to merge this data structures into one。

So you can do it by taking the biggest of the data structures and just moving all elements from other data structures to this bigger data structure。

And if you do this， just if you always move elements from small distort to big dis。

 the total number of moves will be elegantgan。え嘿。😊，For example， if you have a binary hip。

 like we discussed on on the second lecture， think binary hip and you want to be able to merge to binary hips。

You can just copy all elements from small binary hip to the big binary hip。So in total。

 you will have N log n moves from one hip to another hip。

 and you can move element from one hip to another in log different time。

 So total time complexity will be N log square something。Mmh哼。😊，うhu。Yes。

 we'll talk about me I'm spinningning tree next here。😡，But yes。We have this in the blend。

It's long course， will。We'll discuss many data structures before。オッケー。Cool， now on the front。

 the final part。Now we'll finally build there。Cool instruction。

So this role is a very important basic action。 So if you， again， again， this technique。

 like discussed here here。It is very important when you need some nuable data structure。

 if you have some data structure which you can move for elements one by one。

 you can make mergeable data structure with total cost like en loggan。嗯。Now。

 I will erase every and just everybody it from scratch。オッケー。は。1。后8。

Now we'll discuss actually how to make this data structure first and log at in time。The idea is。

The idea is to get rid of this log。 so logarithm is a pretty small function， but still quite big。

 so we will make another data structure which do the same operationss。

 which works faster than in logarithm time。あまsこ。So what will be the idea？Okay。え。



![](img/28c9233d5e4b13e38841e32339183a09_109.png)

嗯好。What is the idea， Again， let's have some sets， some sets，1，2，3。4，5，6，7，8。

So we'll have some sets like here。Here and here。So we have some sets of elements。



![](img/28c9233d5e4b13e38841e32339183a09_111.png)

In each set， we have one special element representative element。

 we have representative representative and representative。We will maintain these sets as trees。

For each tree of the root element of the tree will be the representative of the site。For example。

 for this set  one，2，4， we may have three like this。2。Let's have one here and before here。

So these three represents this set。そ通。The root element is the representative。

And all elements have links to the parent of， of this element in the dream。For this set， for example。

 we may have something more than say we have。 We have different ring。 We may have like three L here。

 we have。5， and here we have 6。Oh me her through like these。



![](img/28c9233d5e4b13e38841e32339183a09_113.png)

So this tree represents this cells， again， element3 is the root of the tree and each element have a link to the parent element in the tree。

And here we have eight and seven with eight。そよ。that's how you represent this set。



![](img/28c9233d5e4b13e38841e32339183a09_115.png)

How to how to implement this very easily。

![](img/28c9233d5e4b13e38841e32339183a09_117.png)

To implement these， we only need to have links from each element to the parent element。So again。

 we need only one array。In this array， we will maintain the pointers from element to the parent element。

So we have RA。P of x is the parent。Of element X。Now， for example， here what we have Her B。う。ああ、そのワ分そ。

It's tall and。有。2 for five， it's free。4，6， it's 5。こしればいち。啊。

What should we write as a apparent element for the roots of these trees？

It depends on your implementation。 You may write something special， something special here like -1。

 but actually， it's。Easier to write the pointer to itself。いと一ポイントトイツき。If you do it like this。

 the code will be simpler。We'll write the quote later。I believe the whole code will be here。said咩。

So it will be too free and。够。ね？

![](img/28c9233d5e4b13e38841e32339183a09_119.png)

![](img/28c9233d5e4b13e38841e32339183a09_120.png)

Now， let's implement the two operations we need， so we need operations fine and tuneion。

Let's start with operation， let's say find。

![](img/28c9233d5e4b13e38841e32339183a09_122.png)

![](img/28c9233d5e4b13e38841e32339183a09_123.png)

So how to find the representative of the set， So we start from element X。

And we go to the root of the tree using these link， so we go from element X to its parent。

 then to each parent and so on until we reach the root of the tree。



![](img/28c9233d5e4b13e38841e32339183a09_125.png)

う知了。little bit like this。Let's say， if。너 리릴 값래。

![](img/28c9233d5e4b13e38841e32339183a09_127.png)

Let's make a another calculation name。 So let's say while。Parent of X。Is not equal to x。

 like move to the parent。

![](img/28c9233d5e4b13e38841e32339183a09_129.png)

嗯，不な。So we start from element。Go to the parent until we reach the element who's parent equal to x。

 And this element will be the root of the three。Because only root have paint pointers itself。

So we go to the root and then stop and the return x。Oh， how to make냐。So first again。

 let's move to the representative of both elements only。Or x equal to phi of x。AndY equal to find。我喂。

Now we move to。Two old elements。So we have X here and Y here。

And now we need to combine two trees into one。And the simplest way to do this is just to make point from one route to another route。

So we'll just move this pointer from x to y here。This pointer。We just move it to。能从。Now。

 if you start to find the root element from any element in this tree。

You follow these links and you go to element X， then use this link and go to element Y。

 So from each element in this set， you will go to element Y and from each element in this set。

 you will go to element Y。 So why is the representative for all elements in this victory。In fine， we。

 yes， we have pointer to the node。 Usually you， you just have the array。

 So all elements are just inerated with integers from one to n。Something like that。So usually。

 they are just inummerated by integer small companies。You can do this point a machine， I believe。Yes。

 I don't see any problems， you can do it in pointer machines。Yes。啊。But here I just。

 I just assume I Kevin Ray。But I believe you can do the same in the pointer machineshroom。Yes。

 we don't need any special from array。 Yes， we we， we。

 we can use just just the elements and pointers。Easal balanced， that's correct。That's correct。

 we'll get to it little bit later by， by now in this implementation。

Let's calculate create time complexity。First of all， the term complexity of this union。

Is composedos of these two filess？So the complexity of this is same as for fine decor and。

Here you have like constant number of here， so the union is pretty fast。

So the only thing we need to optimize is operation fight the operation fight may be slow a bit later。

 but union makes some two fines and then constant number of operations。Let's go to find。

 what is the time complexity of the find？😡，啊。It depends。

 So we start from some element and use these things to move to the root。

Is it possible that the number of these jumps will be linear？😡，No。

 it actually can be it can be linear。 So if you merge these to trees in the wrong order。

 like we did before， so if you start from element1 and merge to element 2。

Then not these three with element free。And then merge the sphere of element for。

You will have this bamboo tree， So you start from。 So this fee becomes some one big path。

And in the end， if you call fine from this node。You will need to follow all these links up to there。

わ thatな。So in the worst case， this find may work linear time。That's not good。We all this lecture。

 we tried to avoid this situation。 So how to avoid this situation here。

 So is it possible to make this fine work request。And quick answer is yes。

 and there are two different strategies。 how to improve the time complexity of this fine expression。

First， the idea。 let's try to avoid situations like this。 So let's try to avoid these long paths。

And to avoid situations， we need to kind of make the tree balanced。

How to make the tree balanced there are different strategies。あ。

Simple explanation is what you usually need is again， like in previous recommendation you need to。

Link the small tree to the big tree。 So if you have two trees of different size。

 you need somehow to pick the small tree and connect it to the big tree。Mh哼。😊，I will use the rank。

 but you can there are several different a which works as well。 so I will use the rank。

 So what is the rank。嗯，6几克 I think。Let's maintain for each element， its rank。

Ran is basically the maximum possible distance to the leaf in this node。

 So so for we have for each element。X。We find the longest pathth in this tree。And。

The length of phase strengthth will be the ramp of elementment X。Look， for example， here we have。

We have element2 have rank equal to one。These elements have around zero。This came around 0。

 it's not to1， and this element 3 have rank equal to2， right？So here we have rank two。

 here we have rank one， here we have rank zero。ご万からこ0なす。So each element has the ramp。

 which is equal to the length， like this is called the height of the tree。

 so it's a maximum possible distance in this tree。Good。And now what we will do。

 we will try to connect three with small rank to three with the bigger rank here。

Let's say x will be the element of smaller ranks。 So if。我说。Of x is bigger than a rank of y。

 Then well just swap them。And then connect。エクストバイ。And now we need to recalulate the ranks。

 how to recalulate the ranks if you connect to trees。嗯，哼分。嗯，哼嗯。

If you have to drink of different ranks， sorry if rank of x is smaller than rank of y。

And you'll connect it like here。So you have some per here， some path here。

What will be the longer path in this？big three， which do I see。 So here this path， this path。

We'll have length rank of x plus1。And this path will have length。Rnk of white。

And if rank of x is less than rank of y， they're integers。 so rank of x plus1 will be less or equal。

's right here。There一かフワイ。う哼ん。そう。The maximal rank or the maximal length of this pathth will be just rank of y。

嗯。嗯哼。😊，嗯哼。😊，Yeah， rank is the distance。So the father is leaf in the soil。嗯。嗯，哼。Sorry。😔，Yeah。

 that's correct。 we need to find the maximal distance industry。Again， again。

 if you merge to three of different rank。😡，Then a rank of x plus  one will be less or equal than rank of y。

 So the maximum possible distance will be still rank of y。So this will be no greater than this。

And if you merge to trees of the same rank。Then the maximum path will be a rank of x plus1。

 so the rank of the y will be increased by1。If you have the same distances here。

Then the maximumim distance will be this。So rent will be increased by one。Yeah。

 it's the same at the height of the tree if you know what what is the height of the tree。

 it's absolutely the same。Like here， you here the rents of old notes。So if ranks are equal。

We need to increase rank of y by one。て。Re。どうだなどうだな。There's the holistic song that's the whole trick。

别走。No。I claim that。These aistics will。こうし？This fine aspiration works in a little bit different time。

So I claim if you do it like this。Then the maximumim distance you can travel here is log from a family。

Why it is true wasn？我行。Let's see。 if you have element of front car， you have。

That you have some three。嗯。や。I claim that the number of elements in this。

Is at least two in the power of rank of X。Like here you have element of rank 2。

 it means that this tree contain at least four elements， at at least four elements。For example。

 this land why， this tree contains at least two elements， it contains at least two elements。変そ。啊。

Op number of children。 No， no， you， you want to have maximum emotional。 So it's。

 it's never bad to have many children。 because first of， if you have many children。

 it means that the death of is smaller so。You always go up to the roots。 you never go down。

 So the big number of children is not problem。有。Again， let's go back。What I hope？

 what I want to prove。 I want to prove that the rank is。呃。Never more than little bit more family。

That's what I wanted to prove。How to prove this very easily， let's look on element x。

 let's prove that the number of elements in these three is at least two in power of Or of x。

Why is it true Because by construction， so what happened here？

When you combine two trees of different ranks。Then a rank of Y will be the same。

And the number of elements will be more。T than before。 So we increased the number of elements。

And the rank is the same。 So this property is still satisfied。

And when you merge two element to two trees of the same rank。😡。

Then you have like no less than two in power of R elements here and no more than two elements of R here。

 So total number of elements will be at least two in power R plus one。

So when you combine two trees of the same rank？The total number of elements。

Will be at least two power of R plus one。And you increase the rank by one。 So if before this union。

 you have two trees of size， at least two in power of R。 Then in the end。

 you have big three of rank R plus one and the total number of elements is at least two in power R plus one。

 So if the property satisfied before the union， it is satisfied after the union。

 And in the beginning of the destruction， we have all elements。

We have single elements of rank 0 and element of rank 0 that。Yeah， the size of this tree is one。

 so it's two in power of 0。 It's satisfied。 So this property is satisfied in the beginning of the structure and it is satisfied after any union operation。

 So this union operation not't break this property。So。

In each moment of the length of the data structure for each element x。

 the size of these three is at least two in power of rank of x。And this is not pepper fl legss。

 And this is no more than N。It means that rank of x is no more than log of。That's on。うん。

In the next semester， we'll talk about balanced trees。

 That's actually what happened usually in balance trees。 So when you have balanced treess。

You have usually some proofs like this。 Instead， when you when you want to prove that something is aative。

 you make the inverse situation and prove that this part is up to exponential of this。さたち。Okay。うふん。

そう。That was the firsturistics。You just maintain the ranks of all elements and link this tree with small rank to the three of the big rank。

And if you do this， you keep your tree balanced。 So the ranks of all elements are up to logarithm。

 So here， when you make find you fall to the root and the length of this per will be no more than logarithm。

 That's all。 That's the first basic characteristics， how to maintain this tree balanced。초。

Second isリィフラント。What we can do？We can improve this fine functions。

So this technique is called path compression。What's best kid meaning？Imagine you have。This fine。

 you call this fine operation。😡，And it takes long time， So， you have some。

Very long trips to the route。So you quote fine from here。

And you need to follow all this route to the root element。What you can do， You can。

Improve your tree for future goals。 So when you call this find in the same element next time。

 you already know that you will end up in this element。

So what you can do is you might change your pointer to the parent element。どうだろうだろうなそれまき。

Change at this point， to here。So next time when you will call the fine from this node X。

 you will go strictly to the root element， so the next call will be working in constant time。

And also， you may do the same for all elements。In this route。 So for each element。In the path。

 you can change the pointer from the current one to the root。 So you may change all pointers。

あでそ俺ちょっとね。ドロータだてフライクです。That's called pet compressing。So again。

 what is the difference every time you call the。You follow this route to the root element。

And when you go back， you change all the pointers。😡，Do the。Instead of the。别走。That's the whole idea。

So let's modify this find。あふふふは。怎么我的天都都。You want to make it take gar for on gar？That's。

That's a matter of taste solutions。Let's make it on recursive just for。To make it interesting。

 So again， we follow to the root。 Now we have X to to， to the root。あ 운取ま。So let's move to the root。

 let's make why here so listen。Y equal to x， while。P of y not equal to y。Y equal to B of y。

 So move for the root and then move again and change all pointers to the root。嗯。

I always do like here。W。P of x not equal to X。とりあえずパパパン。I want to move here and change the pointer。嗯。

Says z equal to p of x。P of x equal to y， and then x equal to。It's over complicated， but。てこ的な。

It's much easier when you write it recursly， when you write recursly。

 you just call a recursor function for the parent， the recursor function will build everything here。

So in the end， we just go back from the and change your pointer to the root。Its liked。

22 two lines of code。But this still works。诶嗯嗯嗯嗯。嗯。Okay， no question stop for me。 okay。Let's all。

So what is the idea again， again， What is the idea。Every time you call the find。

You not only find the root node， but you also change all the pointers on this path to the root node。

So next course of defined will work in constant time， So if you。IfAfter the separation。

 you again call the find from any of these nodes， you will go directly to this root node。😡。

So each each next call will cost you constant time。This ideaiom。嗯哼。Okay。嗯。No， the results。

 the results。So what will happen if you use this technique？

If you use this technique without their rank。If you use spread compression。

And without any other heuristics， you just just use something like this in， and。

Connect any trees in and。 So you may have this long bamboo trees， but。

You always make pack compression。 So these characteristicss alone will give you longer different time for the fine version。

 So the markedized time of this。F。We'll be at Logan。Yeah。And。



![](img/28c9233d5e4b13e38841e32339183a09_131.png)

The more interesting fact is that if you use both theuristics。 So if you use spread compression。

And some other risks， which maintain your tree balanced。 So if you。

 if you use pathth compression on some balanced tree。

 like we did or when we have like rank characteristics。 So if you， for example。

 use path compression plus rank characteristics。That time will be even less than liberty。

The amortized time of the find。Will be actually the O of inverse like function of M and N。

So what is this。Of these。怖いファシ。So it's called an industrial acuman function。

Here you have two arguments。 So N is the size of the tree。it's the number of elements in our sets。

 if human， you may think about it in terms of sets or in terms of three sets。

飛できたあアンエ is the number of a。Number。Of fine Of course， ofフ this function of fine。

So if you call this fine de M times in total。Then time complexity will be something like that。

And the interesting about this function is that if you if end is increasing。That function will be。

Also， increasingly。And if M is increasing。 So if you increase。The number of。Cos。

 this function is actually depriing。So it became smaller。That actually makes sense。

 So if you have some structure of your tree and you make a lot of fine des。

 then the more operations you make the。Shorter the pads became。 so after each fine operation。

 the trees kind of improved， so this length became shorter and shorter。

So if you make many fine operationss， the tree became something like that。So all operations。

 all future fine operations will cost you constant time。That's interesting。嗯哼。そう。

So this time complexity actually depends on number of operations you make on this data structure if you make more operations。

They actually work faster than if you have small number of questionss。そした。

We will not talk about this function today， I'm always planning to have a special lecture about this。

 but I never have enough time。😡，That's interesting。

 so we may have special lecture about it at some point。

 but the problem is you need to spend like an hour to explain what is the function means。

It's might be not an hour， but like。Hery meals just to explain what is that indoor sacrament function。

It's kind of complicated。Soう。Instead of this， we will prove some。呃。

Some more simple upper bound on on on this time complexity。 we will prove。

Like the worst case for this situation in the worst case。In the worst case， M equal to n。

 So if M equal to n。Then。This enormoustacrament function became。デイライトトーダです。啊。

And we will prove this up above。What is the iterated log？嗯嗯嗯。Okay。The iter is a little bit different。

Very simple function， actually。Also， how many times you need to get logo of this integer until it becomes small。

 so let's look on some integer2 in power， let's say 655。36。Let's take log reform for this element。

 So， so we take log reform for this number。 You have。B in the power of 16。Then again。

 you take over from this number。You have two you have 16，16 the power of four。

Then againくテロリフテトンパオフトテフト powerフワてトンパし。Now， let's calculate the number of times。

 We take logar from until we have small number。 For example， here， we start from this number。

 take logar from logarith logar logar roof until we until we are here。 So we take logarith from like。

five times。So iter rated logarithm is the number of times you take logarithm of the number until it becomes small enough let's say here is small enough。

Let's say that it rated global of n of of， of this number。It's a fire。Sometimes it's plus plus or -1。

It depends on where where you want to end。 So if you end here， at then， it's 5。

If you want to make one more step， then it will be six， its not a big deal。ok。

So this is deter log different function。 It is very slow。 It grows very slowly。 So even for this。😊。

Big number， it's up to five， so it's extremely small。WellActually。

 if you have these many elements in your data structure， then。

You have much more interesting problems。 For example。

 you don't know how to store this elements because there is not enough atoms in the universe to store this elements so。

You most。You usually don't have this。Many elements in the structure。 That's what they want say。

At least by now， maybe physicists will learn something about how to store these number of elements in the future computers。

 but in normal computers by by now， which you don't。You have no。

No chance to have this big day structure。别走。No。What I want to prove， I want to prove。😡。

That the time complexity。Of fine operation。아말 때 상시。Is a big O of it rate log different。我感。

That's what we look for right now。That's not that fun as this upper bound。

 because this is much more interesting。But it's good enough。

 so we will prove that the temp complexity is pretty small。嗯。そ。そ什么？How to prove this to prove this。

 again， this is the amortized cost。😡，So to prove that at scores。

 we need to calculate the sum of time complexities of all fine functions。So we have this tree。

And we call the fine operation several times。So again， you have situations like this。

 so you start from the structure and you call union， then you call find。

You another call another find you。And so you make some number of operations like emration。

And I want to calculate the total time complexity of these operations。😡。

And then I will divide by M and get there。Thank you this one version。まずか？

So how to calculate the tank complexity， let's look what happens when you perform a defined operation。

So you have some element text。You move from here。どうだろう？

So the time complexity is equal to the number of these jumps。

 so you start from element and x and then move to the parent until you reach the root of the tree。

 so the time complexity is formed by this by the length of this pad。What will calculate。

 will calculate the total length of all these paths。Okay。First。Let's look on this last edge。

 So this last edge is。Special。Let's calculate these edges first。

We have one last edge in each fine operation， so the total number of these last edges will be M。

 so let's just calculate these last edges separately。あ、そう。So total diamond will be。あのも。

So in each fine operation， we have one last edge， so let's calculate it a separate thing。😡。

At least it will be a little lost， lost interest。Nice。Now let's calculatelate these ages。

To calculate these edges， we will split all edges into two groups。We will have。



![](img/28c9233d5e4b13e38841e32339183a09_133.png)

Like short， how to call them。I don't know， I don't know correct。哼。

Let's go on small jumps and big jump。

![](img/28c9233d5e4b13e38841e32339183a09_135.png)

![](img/28c9233d5e4b13e38841e32339183a09_136.png)

![](img/28c9233d5e4b13e38841e32339183a09_137.png)

No I I I I I want to。'ss not， even if the term is correct。It's used only in this proof， so。

As soon as the proof is correct。That's fine。Okay， let's look on some node X。 So you have this node X。



![](img/28c9233d5e4b13e38841e32339183a09_139.png)

Let's look on this edge from expert parent。So this isスパラトフクス。We will say with like small jump。

イ the rank。Of the bar。E。Let's say less or equal than 1。9 in the power of rank of text。



![](img/28c9233d5e4b13e38841e32339183a09_141.png)

And we say we have a big jump。Let's say， lesss。いや。

![](img/28c9233d5e4b13e38841e32339183a09_143.png)

イ服ラ。Of the parent is greater or equal than 1。9。哎こまや。



![](img/28c9233d5e4b13e38841e32339183a09_145.png)

So again， we look on this edge from x to the parent of x in the tree。

And if rank of the parent is big enough。We say that this is the big jump。

And if the rank of the parent is small。We will say that this is small jump。That's all。Now。

 let's go the number of。Why it's 1。9 Because I need some number less than two。 Actually。

 I need some number less less than two， but quite close to two it。We'll get this。Right now。

 we'll get to it in in a minute。啊。Hse first。Let's calculate a number of big jumps。

I claim that number of big jumps。😡，In each fine operation is about iterated log。そう。

We have M log iterated of M， big jumps。

![](img/28c9233d5e4b13e38841e32339183a09_147.png)

AndNow like this plus this。Why is it true， because you start from element and X and each time you have a big jump。

😡，You move from element to the element of rank， something like that。嗯哼ん。



![](img/28c9233d5e4b13e38841e32339183a09_149.png)

い一フ。If you have two here。You will have exactly something like that。 So youll start from。

 you'll start from element。They run zero。Then when you have a big jump， you go to element rank 1。

 Then you have another big jump。 You go to element rank 2， then to rank 4 to round 16 to rank。

2 in power of 16 and so on。 So each big jump moves you from element rank x to rank2 in power of x。

Okay。So you may。Make it at most。It rated log difference。Ner of jumps。Here I have not two but 1。9。

 but it's not a big deal if you make two big jumps。😡，So if you。

Move from element X and you make one big jump。 So here you have two power of x and you might make another big jump。

 then you two in power tool power of x。啊 one point nine啊 sorry系系系。So move here， it's 1。

9 in power of x， and you move here 9。9 in power of9，1。9 in power of x。

So this will be greater equal than 2 in power effects。So it's essentially the same。

If you make two big jumps， you move to the vertex with a rank。😡，At least two in the power of x。

And you may have no more than itererate log difference number of。Jumps like this。Clear呢。Again， again。

 this is the same。 So it's a very log number of times you make a。 make a from the given number。

And here you make the opposite one。 you go from number to the number two in power of x。

So if you go from right to left here， you make start from here and each time you move to the integer。

 which is2 in the power of x。The number of jumps from here to here will be up to its rate logarith of n。

Is clear enough。Okay， that' so。Well it's actually's quite intuitive so if you look on these big jumps。

Then if you make a big jump， it means that you go from number from some very big number。

So you move from number X to some number two in power of x。

 and you can't make too many of jumps like this， even after like。5 operations， you go to the number。

 which is。Extremely big。Okay， so number of big jumps is at most iterated logarith for each fine operation。

 so total number will be something that。That's all， and finally。

 let's calculate a number of small jump。To go a time of small jumps， let's walk on some some。

三 in三三 node x。哎嗯哎。いや。ItIt's big enough to to this proof。

Whatましたかあ let's look small jobs let's the number x。No， number X like or loose from element X。

So let's look on the edge from the x to its brand。Imagine we let's say x not here。

 x is somewhere here。So we start flying from here。Go to element X。

 then use this edge and go up to the root。Every time if the x is not the final h。

And were already calculated these final edges。 So if this edge is not the final edge。

Then it means that we will change this point or to the point or to the root。

 So we if we go from here。Then we will use path compression and we will change this point or two here。

Mmhmm。It means。The pointer is moved to some element with bigger rank。The rank of the road。

Is strictly bigger than the rank of the parent of element X。This is the root。Again。

Before we make this fine。The pointer from x was to to this element， the parent of x。😡。

And when we make this fine， we move this pointer from this element to the root。

The road have bigger rank than this element because rents are strictly increasing。

Each parent have bigger rank than the children。嗯。嗯。Yes， yes， this edge will became the last edge。

 but not for for us。 So it will became the last edge。 but then we can like。

Make a union so this or whole tree will be connected to South Ma。

 so these edges will no longer be the last edge and so on so on。Last edge is not final。 So Sa。

 if the edge is final， that we can then unite this set with some another set so we connect this route to some other routes。

 So these edges will not be final anymore。It's not like the final pointson。if the a is final。

 it's not final until the end of the data structure， it's just final by now。好。嗯哼ん。What type。

 so one x， if， if this no， if this edge is not the last edge on this path。

 it means that we will reconnect this x from here to here。

And this node have bigger rank than this node。Well，'s now let's look on on this。不 you go。

Let's look on this failure。Acade each time you move。Across this。A node X。

 this value will be increasing。 So each time if， if this x is on your path from。

 from this fine operation。This value will be increasing each time。In increasing。

 it's increasing because we move this pointer from here to here and this element have bigger rank than this element。

 so this parent was here and now it's here， so this element have bigger rank。

 so this value is increasing。Now， how many times can we increase this failure until this。

X became the big jump。So let's take element X。もま。Okay， let's make it slow again what happens。

 You have element X。It has some pointers here。

![](img/28c9233d5e4b13e38841e32339183a09_151.png)

You have some fine operationss which access element X。 so you have some fine operation from here。

Each time when this fine operation access the node X。

You will move the pointer from parent to some another node。 So if you go here。

 then you move the pointer here。Next time if you go here， you move move pointer even even further。

 So each time you access node X， you move this pointer up to up to to the row5 to3。嗯哼ん。😊。

So let's calculate the number of such operations after this。

 this jump from x to its parent will became the big jump。4 x。We need to make。At most。1。

9 in power rank of x operations。안치を。安其。啊。Until the jump from x to parent of x became。え？你看。

There big jump。哎。O你问到。さ？What I want to say。Each time you go through this element X。

 you move this point up up up to 3。So。When you make 1。

9 in the power of rank of x operations like this。呃，在。

The ranknk of this parent node will be bigger than 1。9 in the final rank。

 because rank is always increasing。 You always move pointer to some node with bigger rank。

So after this number of operations， this jump from x to its experiment will became a big jump。

Because rent of x is constant。And rank of its parent is always increasing。That' all。

 Now let's calculate the total numbers of pressure like this。 I want to calculate the sum for all。

 for all nodes。啊。1。9 in the power of rank of x。 So this will be the total numbers of a which access all elements。

 Yeah， so for each element X。We go through this element at most this number of times。

So now let's go the sum of all this。呃， values师。How to create this sum it's actually quite easier。

We will group all notes by the rank。So let's say group all knows by rank。嗯。Multiply by。1。9。

 So let's group all node by the rank。Until K， the sum fall all nodes of the same rank。

What will help here？How many nodes may have the rank car？😡，So imagine you have the tree。

 you have several nodes of the same rank。If you have several notess of the same。

Then for each sub three。You have at least two the power of R。呃， notes。And in total。

 you have end nodes， so the number of these elements。Hes no more than n divided by2 in5 of half。え，嘿嘿。

Yes， it's a little bit complicated to get it from the first time you may need to wash it again some delay。

Maybe it's not the B explanation for this part。I think it's quite clear。

 but it's not the easiest stuff。不给。大夫ばけ。Finally， that's the finish。What we have here？

I want to calculate the total number of small jumps。 Yeah， let's look on some node X。

 We make some small jumps from this vertex X。From vertex x。

 we will have up to this number of jumps until this jump became a big jump。

So the total number of small jumps will be something like that。

Now we calculate this sum by regrouping all the sums in the groups of nodes of the same random。

 so we take all the node of rank R， calculate the number of nodes。Of what this is the number of。

Numb pair of notes。呃。嗯。一口 to2。So we take all nodes of the same re。😡。

Get the number of nodes multiplied by this three。this便。那そ。

This's just just a regrouping of elements of this sum。😡，And this。

 and the number of elements which have than R is up to n divided by。嗯，算。

And divided2 in the power of R multiplied by 1。9 power R。This will be n multiplied by this sum。嗯。那个走。

And this sum is。Constant， So this is big over and。痛苦。So here we have。啊。Plus edges。

 big jumps and plus and small jumps。So the total number of operations in all this。

Fs will be m log n plus n， and we will assume that M is bigger than M， of course its。あ。Yeah。

 so the total bank will be。I to be。嗯。Maybe not， maybe not the clueest。Explanation button。Okay。

 the first name expanded in English。That all that's why this dye structure workss it right。

And the interesting part why is it important because of this？This function is。

ExGir was extremely slow。And also all the operations we used are pretty fast。

 So if you look on the code， then all operations in it coast are first。

 we just we just look on the array， go to the link， go to the link and so on。

 so we use very simple operations and time complexity is slow。

 So this implementation is actually very fast。Just this one of the fastest data structure you may use and。

It's actually almost the constant working time。收益。Like in average， you have like three operations。

In this little。So it's it's， it's， it's quite cool。 It's really it's really useful。

 You can use this in in， you can use this in in the real context， in real contexts and so on so。😊，啊。

Later， we will use some。Maybe we discuss discuss next week in in the home task。

It can be improved not only to， to maintain the sets。

 but also to calculate some functions in the sets， we will discuss it in the home task， I believe。

 So it it it can be modified to be able to calculate some different functions on the paths in the trees。

So it's why in the。So that's， I believe it's all for today， so thank you again for joining me。

See you next time。嗯。🎼，🎼あ。🎼嗯。🎼，🎼う。🎼へ。🎼，🎼，🎼，う。🎼，🎼うん。🎼う。🎼，🎼，🎼，🎼Yeah。🎼う。🎼。🎼The。🎼，🎼Byあ。🎼，🎼，へん。あ。🎼，🎼。🎼Yeah。

うん。🎼，🎼，嗯。🎼Yeah。🎼あ。🎼The。🎼。🎼，🎼The。🎼，🎼，🎼うん。🎼，🎼，🎼嗯。うん。🎼。🎼う。🎼Yeah。🎼，🎼う。🎼Yeah。🎼，🎼，🎼，🎼あら。🎼，う。🎼。🎼あか。🎼，🎼，うん。🎼。

うん。🎼。