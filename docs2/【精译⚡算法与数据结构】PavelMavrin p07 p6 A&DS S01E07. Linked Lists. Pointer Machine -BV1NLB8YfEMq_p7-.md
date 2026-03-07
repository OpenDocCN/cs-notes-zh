# 【精译⚡算法与数据结构】PavelMavrin p07 p6 A&DS S01E07. Linked Lists. Pointer Machine -BV1NLB8YfEMq_p7-

，🎼中。🎼The。So today we'll talk about linked lists。

![](img/569b6d62b660e28bb3f923aa74ec49d8_1.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_2.png)

But before we start to talk about linkedlists， I want to introduce another computational model as you may remember from the first lecture。

 we're talking about computational models。And we decide we will almost。

almostmost always use the R model。So in all previous data structures， we use RAM model， RA model。

s let's see I do so's。

![](img/569b6d62b660e28bb3f923aa74ec49d8_4.png)

The model when you have a realm。

![](img/569b6d62b660e28bb3f923aa74ec49d8_6.png)

一ち。Like a big array of data， and you can access any element of this data by index。こ。

And now we will switch to another computational model， it's called O inter model。



![](img/569b6d62b660e28bb3f923aa74ec49d8_8.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_9.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_10.png)

So what is the pointer machine pointer machine is a very simple computational model in pointer machine。

 all your data is stored on some nodes。

![](img/569b6d62b660e28bb3f923aa74ec49d8_12.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_13.png)

So you may have like big number of nodes。Each node。



![](img/569b6d62b660e28bb3f923aa74ec49d8_15.png)

Let's say， old X。

![](img/569b6d62b660e28bb3f923aa74ec49d8_17.png)

May have some constant number of fields， each field contains some data。



![](img/569b6d62b660e28bb3f923aa74ec49d8_19.png)

Like objects I know in Java， you might have some fields。

 each field contains some data like name or something。



![](img/569b6d62b660e28bb3f923aa74ec49d8_21.png)

嗯我's自会。I need to get the name of the fields， let's say I have field a equal to5。

 B equal to seven and so on。

![](img/569b6d62b660e28bb3f923aa74ec49d8_23.png)

Just some data stored on this stone。

![](img/569b6d62b660e28bb3f923aa74ec49d8_25.png)

And you may have some fields， which points to another node。 Let's say you have field P。

 which points to note y。

![](img/569b6d62b660e28bb3f923aa74ec49d8_27.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_28.png)

So we have another node why。

![](img/569b6d62b660e28bb3f923aa74ec49d8_30.png)

So this field is a pointer to this。No why。And you may have pointers to any node。

 you may have pointer to itself， you may have pointer which points nowhere to know something like that。



![](img/569b6d62b660e28bb3f923aa74ec49d8_32.png)

Let's late。

![](img/569b6d62b660e28bb3f923aa74ec49d8_34.png)

Mostly like you have classes in most programming language or classes in Java class in Python。



![](img/569b6d62b660e28bb3f923aa74ec49d8_36.png)

さなた。

![](img/569b6d62b660e28bb3f923aa74ec49d8_38.png)

That's all you have in the pointer machine model。

![](img/569b6d62b660e28bb3f923aa74ec49d8_40.png)

What operations can you make， no you may make like？Very primitive preparations like create node。



![](img/569b6d62b660e28bb3f923aa74ec49d8_42.png)

エユ。

![](img/569b6d62b660e28bb3f923aa74ec49d8_44.png)

No。よも薬セ です。

![](img/569b6d62b660e28bb3f923aa74ec49d8_46.png)

You may remove the node like if you need some memory and you may change the field of the node。

 let's say X do。

![](img/569b6d62b660e28bb3f923aa74ec49d8_48.png)

B equal to 10， or you may change it to point or now was second。

May change this point or field to point to another node Exp that we have another。Another note here。

 so you may change this pointer。

![](img/569b6d62b660e28bb3f923aa74ec49d8_50.png)

都 here。That so。

![](img/569b6d62b660e28bb3f923aa74ec49d8_52.png)

No， I dont not app， yeah， homelesss discussion is not appud to Duke for reasons。

It's only available on Titch， and。

![](img/569b6d62b660e28bb3f923aa74ec49d8_54.png)

There are reasons for it。

![](img/569b6d62b660e28bb3f923aa74ec49d8_56.png)

嗯。Cool， let's solve。Now， what is the difference， what' is the main difference between pointer machine model and array model？

啊。

![](img/569b6d62b660e28bb3f923aa74ec49d8_58.png)

嗯。The main difference is that in pointer machine model， you don't have arrays。



![](img/569b6d62b660e28bb3f923aa74ec49d8_60.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_61.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_62.png)

So in real model， you obviously have a race。呃有没。Create an array and access any element of the array by its index。

Y。

![](img/569b6d62b660e28bb3f923aa74ec49d8_64.png)

Obviously in remote model， you can access any element by index so you can create a segment of this Ramm。

 call it an array and access any element。

![](img/569b6d62b660e28bb3f923aa74ec49d8_66.png)

In point machine model， you don't have any array， you have only these node and each node have a constant number of pointers。

 so you can have pointers to each element of the array because a constant number of these pointers。



![](img/569b6d62b660e28bb3f923aa74ec49d8_68.png)

So in point of Msh models， you need to create some data structures which doesn't use any arrays。



![](img/569b6d62b660e28bb3f923aa74ec49d8_70.png)

啊，那走。

![](img/569b6d62b660e28bb3f923aa74ec49d8_72.png)

Yeah， I think that's we will。

![](img/569b6d62b660e28bb3f923aa74ec49d8_74.png)

It's little bit strange Why do you need to use pointer machine model when you can use RAM model and you may have the erasing RA model。

 so why should you use pointer machine model instead we will talk about later so sometimes it's good to have pointer machine model instead of some more powerful model like RA model So we will talk about later now we'll go to linkedlist。

そう。In pointer machine model， you don't have a race。

But you you usually want to maintain the list of elements。

 So how you create list of elements when you don't have a arrays。啊。



![](img/569b6d62b660e28bb3f923aa74ec49d8_76.png)

And。The link to at least work fit。

![](img/569b6d62b660e28bb3f923aa74ec49d8_78.png)

You have。A number of nodes。

![](img/569b6d62b660e28bb3f923aa74ec49d8_80.png)

Each note contained one element of the list。And you have pointers to the next element of the list。

 So each in each node， you have one special field。

![](img/569b6d62b660e28bb3f923aa74ec49d8_82.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_83.png)

Let's go to the next。Which is the pointer to the next node of the list from here you have a pointer to this element Here you have another next。



![](img/569b6d62b660e28bb3f923aa74ec49d8_85.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_86.png)

For this element here， you have another next。

![](img/569b6d62b660e28bb3f923aa74ec49d8_88.png)

And also in each node， you have some important data like here you have some data。



![](img/569b6d62b660e28bb3f923aa74ec49d8_90.png)

That is the data you use in your algorithm。In addition to this data， you have this special field。

 which is used to create this linked list。

![](img/569b6d62b660e28bb3f923aa74ec49d8_92.png)

And also， you need， I think， I think you need the point over the first column。



![](img/569b6d62b660e28bb3f923aa74ec49d8_94.png)

Go up to here first。

![](img/569b6d62b660e28bb3f923aa74ec49d8_96.png)

And from here， next points to now。

![](img/569b6d62b660e28bb3f923aa74ec49d8_98.png)

对。

![](img/569b6d62b660e28bb3f923aa74ec49d8_100.png)

응 느림 느려？こ。

![](img/569b6d62b660e28bb3f923aa74ec49d8_102.png)

That's all。 That's how we create a linked list in pointer marshmal。So how to use this list。

 what can we do？With this linked list， for example， we can it our all elements。



![](img/569b6d62b660e28bb3f923aa74ec49d8_104.png)

What you do it when you have arrays， you do something like that， like 4i from0 to n minus1。



![](img/569b6d62b660e28bb3f923aa74ec49d8_106.png)

Bring element。Like this。

![](img/569b6d62b660e28bb3f923aa74ec49d8_108.png)

So that all happens when you need to iterate all elements of the array。Here。

 we don't have a delivery。 We have this link list。So how to it our all elements of the linked list。



![](img/569b6d62b660e28bb3f923aa74ec49d8_110.png)

We just go from the first element on each step of this cycle， we go to the next element of the list。

So， let's say。We have current element equal to first。



![](img/569b6d62b660e28bb3f923aa74ec49d8_112.png)

And now we just jump to the next list to the next element of the list。 So while。Obs then X。まてことな？

We just print。Eleement X， and then jump to the next one。



![](img/569b6d62b660e28bb3f923aa74ec49d8_114.png)

Something like that。

![](img/569b6d62b660e28bb3f923aa74ec49d8_116.png)

That's all this， that's how you it all elements。Of the link please。



![](img/569b6d62b660e28bb3f923aa74ec49d8_118.png)

Okay。

![](img/569b6d62b660e28bb3f923aa74ec49d8_120.png)

那。What else can you do it， what else you can do in the linked list comparing to a race？Obviously。

 what you cant do in linked list， but you can do in the race is access the element by the index。

So if you want to find the element of index I。You need to go from the first element and use these pointers until you reach the element of the index I。

So to access this element， we need to start from the first element and get to this element from left so will you may need up to end time to find this element in the linkIn linked list。

And in the array， you can access any element of the array in constant type just by using this indexation。

Okay。But what can you do in linknkist， but you cannot do in race？



![](img/569b6d62b660e28bb3f923aa74ec49d8_122.png)

Now， one more obvious thing you can do in this list is to insert a new element。In thelinist。

For example， if you want to insert new element between two elements to existing elements of the list。

 like you have these two elements。Let's say we have element， X and element。Why？

And we won't insert new element here， so on。This new elemental is called the Z。

And you want to insert this elements then between at least two elements。When you have a array。

 you cannot do it fast because you if you have a array and you insert the element in in the middle of the array。

 you need to like shift all the elements to the right and here you can insert the element in constant time because all you need to do is to move this。

Liinnk to here。This link to here and remove this。Thank you them。What's right。응 왜릴て？Well。

 let's have procedure like Ed。After。X， Z。こ。So we need to add element Z after element x。

 let's say y equal to x next。then 우리 또。X， next。To that and that next。why， right？不错。



![](img/569b6d62b660e28bb3f923aa74ec49d8_124.png)

That's how you add a new element。都都플。And you can add element to any， any position of the link list。

 They on the different， they on the difficulties that if you want to add。

That in some position on linked list， you need to have point enter to this element X。

So you need to have from somewhere， you need to have pointer to this element X。

And if you have this pointer， you can add new element after this position。Okayay。哦。



![](img/569b6d62b660e28bb3f923aa74ec49d8_126.png)

studio is。Not thats stable。喂。Next。How to remove elements from the linked list？

If you need to remove the element。Let's try here。不。

You need to move the pointer from the previous element to the next element。 So you need to。

Move this pointer to here。And to do this， you need to know the previous element in the linked list。

So if you want to remove this element X。You need to find the previous element in the linked list。

So if you， if you know the pointer to the previous element， then it's fine。

 You can just get the pointer to the previous element and move this next pointer to the to this element element after。

But if you don't have the pointer to the previous element， that's complicated， so you can adjust。



![](img/569b6d62b660e28bb3f923aa74ec49d8_128.png)

In this realization of linked list， you can remove element just by having the pointer to this element because you also need to have pointer to the previous element。

嗯。AtThese points are like hard code index。I don't get it。What is comfortable techniques。

Not sure about public。There's no like indice here。 So it's like it's more like well。

 like there are some some entities you have like。PoinPoiner is something which allows you to get information about this note。

It's how how it is realized in the real system。 it may be complicated。

 So in in the real in in the real computer， it may be implemented in various ways。

 usually you have like usually in real computer。 let's go。 Usually in real computer。

 you have something like cr model， usually。So you害。InMost computers。

 you have some RAM and you have something like Ram model。

So when you try to implement something in point model， you need to。

Some somehow simulate this point machine model。 So you have some。Elements that stored memory。

 and you have these link。 these links are kind of ind in the。 But you may， you。

 you may implement it in various different ways。 So you may move these objects。

 So you move move these links and just at least as long as if you if you maintain this structure。

Somehow， you're good。 And there are various ways to maintain this structure。

Let's have the different good properties。I'm talking so much。We will talk about later。啊。嘿嘿嘿嘿嘿嘿嘿嘿嘿。😊。

Yes， a little bit later we' talk about why you may want to use for machine mode instead of。😡。

A red model。嗯。What I was talking about。别 먹 왜走。If you want to remove the element。

 you need to point out the previous element， so usually if you need to have a list which can be used to remove and you want to be able to remove elements from this list。

 you use not list like that， but you use doubleub link list。What is double Li list？

It's the same linked list， but you have pointers to previous element to next element and to the previous element。

So， in each。In each note of the link list， you have two pointers。

One pointer to the next element and another pointer to the previous element。嗯。



![](img/569b6d62b660e28bb3f923aa74ec49d8_130.png)

So this pointer is a pointer to the previous element in the linked list。嗯哼。😊，うふん。不。This is not。こ。はい。

So let's modify this。Procedure first。So if we want to add a new element in the double linked list。

So we have new element， Z。So we need to have pointer from here to here， from here to here。

 from here to here， from here to here。So we need to modify these four pointers x next to Z。

 Z next to y。And also。Why。Prave to that and。That。ButF2 x。

And here already I made my first mistakes because。1月。Here。No， not here。

 but here I I don't know why here。Here you may have a little nu point or exception。

Why you may have now pointer exception here， Because if you add a new element after the last element of the right。

 So if this x is the last element there of the list。Then white is now。So。Here you try to。呃。

To access the element of the null pointer， and you have a null pointer exception here。So to avoid wh。

 you may just write something like。Let's say， if why is not now。Then y per f equal to Z。

 and Z is not now。 X is not now。 So it's fine。Something something like that。How to remove elements。

 Let's remove some elements。 So we have this element X。 We want to remove it。 Let's have previous。

 next， previous next。Let's call this element why this element is it。

So if we want to remove element X， let's find the pre in the next element。And move this。

Poiners we need to Y next to Z and Z graph to y like this。But both of these elements may be now。

 so let's say if。If aze is not known。です。Use the same attention。So if that is not now。

 then I put point of prayer to y。If why is not known。Then we move the next point of the。And also。

 if wise is now， it means that。We need to move the first pointer we also have this pointer first to the first element of the rate。

And if we remove the first element of the array。嗯嗯。Let's say if X it go to first。

Then we need to move first to the next element。で。嗯。嗯。Why is that broke。So I have this element X。

 the previous element is Y， the next element is it。是。So're here， this one's white， this is Z。

So that perhaps to y， Y next to that。 No， it's not fine。That's all。

So this is how you remove the element from the double linked list。And as you may see。

 we already have even for these simple functions。We have many if statements。

 So we have two mining statements。 we have if here， if here and if here。

 And when you have too many if statements in your program， it's not a。Good thing。

 because if you have too many if statements， you need to test all of them。 Yes， and if some。

 if some of this as if the statements does work， you， you may have some bugs in later。

 So it's usually， it's usually better to have program which have not so many if statements。

 So how can we。do it here啊。One of the tricks， which can you make when you have a linked list。

 is to add special two special elements in the beginning and in the end of the linked list。そう。

What就 me do。哦。Is to have two additional elements。You have these elements。Of your linked list。算来て。

And you add two additional elements。Additional element here。And another additional element here。

And you put link across this element。And the lost of the。That's all。

 And now you have something like deck， basically， So you can access both the ends of this linked list。

 You can add some elements here。 You can add some elements here。 You can iterate or all elements in。

In either direction。 so you can go from left to right， you can go from right to left。

 You can add anything to remove editing and you don't have these if statements because you don't remove these both and elements。

 You can only remove elements in the middle。 And for each element here。

 you have the pointer to the previous and next element。 you always have these two elements。

 So you don't need to check if you have no pointers there。没财务错。And also。

 you don't have this if statement， because。least why should。きけなけの。彭松。啊。You can even have more。

Simple structure。 let's see。 So in this first element， we only use this next pointer。

 and in this last element， we only use this previous pointer。

So instead of having these two additional elements， we may have only one additional element。

So we may add one extra element here。And from this extra element， we put the next pointer here。

And the bring moment take here。So we have somethingcyclicists。啊啊啊啊啊啊。Yeah。

 and basically actually one of the most。Common ways to use the link list。So again。

 how to use linked list， you have this each each list is identified by this element。

 so if you want to have like a pointer to the list， you have the pointer to this element。

So this is the point of the list。From from somewhere here。So if you want to access this list。

 you use this point or go here。 and then you can do anything。 Yeah， So you can。

 you can iterate from left to right。 You can iterate from right to left。 You can go somewhere and。

It had some additional element and so on。没错。Nice。What else can you do with linked lists， For example。

 you can concatemate to linked list。 So if you have tool structures like this。ぱつ。

Let's have another structure here。哦。If you have another structure like this， or you have another。

Element like this。 and you have some list here。Soそれ doublelinク and。

So you have a list link to this element， linked to this element， and you want conate this list。

So what you can do is basically remove one of these additional elements。Pooo link from here to here。

From here to here， from here to here， El on。So instead of two lists， you have only one this big list。

 so you can continue two lists in constant number of corrections。And not very very stuff like this。

 you can split list into two parts， you can concateate to lists and so on。こ。嗯。はい。那。

Let's go back to stacks and Qs so on previous lecture we discussed what is stack what's the Q is two important in structure。

 and they both can be implemented in point of our machine model in a very simple way。So if you have。

 for example， step。So last lecture， we used a array。

 used a array to maintain the elements of that stack。And now， instead of array。

 we will just use the linked list。So how to implement step value？Only half。Link placed。那么清。

So what kind of the elements of this deck？So let's say this is the last edit element。

 so this is the top element of this stack。You may have a double ended list like here。

 but actually you don't need this。It's enough to have a single direction in place。

So in what directions do we need pointers in this linked list to be able to maintain this step？

It looks like how to think about this。 So listen in what direction we need links from left right or from right to left。

When we need to link to another element of the list。

 when we need to go from one element to another when we。Remove these top。

 So when we make a pop operation in our stack。We need to move this top pointer to the next element to the left。

So we somehow need to be able to jump from here to here when we make pop operation in the stack。

So we need to have pointers from right to left。Like this。And that's actually all we need。

 we'll never use the pointers from left right。So we will maintain the single directional link list and we will maintain pointers from right to left。

Okay。啊。哦。Let's implement both operations of the stack。 We have only two operations。

 Let's implement them both。 so in。Where么 need to。酷ush。I want to push new elements in this stick。

So we create new element here。嗯哼。😊，Make this point from here to here and change top to here。

That's all。 That's how you。Wch element in this stick。What is that just X next？とト andト equal to X。

Yeah， basically， that's how you push elements in this neck。And how you pop elements from the stack。

Well like before， we have the pointer to the top element of the stack。

 We need to move this pointer to the next element in the list。And then return this evidence service。

嗯。Just remember the previous stop， move top to the next element。에 네 늘렸죠。This dress。

That's all very simple。AllIt's。No， it's not surprising it's simple because it was simple even when we had a race phones。

So it's so surprised likely that it's not much more complicated for Inter model than it was in realM model。

It was very simple in real model like we had one line per。For functions， push and pop。

 and here we have almost of the same so we have some。A small number of operations for education。

That's how you make stacks using Linked list。ha ha and kill。How do you create cues in in。

 in the point commercial model， It's almost the same。So， we have。Some number of elements。

We have the pointer to the head element。Of the Q and to the tail element of the Q。And we need。

In what direction do we need to have pointers？Well， let's think about it。

When we add new element to the Q， we just add element here and。

We need to move from this element to this element， so we don't need any pointers we just move tail to this new edit element。

And when we remove element from the Q， we remove this element head and we need to move head to this next element in the queue。

So we need to somehow to jump from here to here， so to be able to do this。

 we need to have pointers to the next element of the Q， so we need to have pointers like this。

From left to right。예？35 minutes worth experiment since we started， yeah， it's about。

It was pretty quick， actually，Okay。Okay， let's do it。 So what happens when we add new element？

ALittle bit more complicated when you may have emptyule。 What happens when you have an emptyq？😡，嗯。

R two2 two that you may have。Both pointers equal to now when you have an empty。

Or you may have additional element here。And like when， when Q is empty。

 you just put all the pointers to this to this。Additional element。嗯。Let's loose in the hub rate。

Let's say that if Q is empty， then both these pointers are pointed to the nu。

so how to add new element。So we just add new element here and here if the queue is empty。

 now always will need to have these e。 so if Q is empty。嗯。

Then we just create new element X and make a Q of the single element。こち。嗯。咩。ねえ、こちら。

I have this new project us too。For lighting， but。疲いです。嗯。What I was talking about。

When you add a new element， if the queue is empty， then we add new element and make a Q of the single element。

And now if the queue is not empty。Then we just add new element here。

Move this link and let me think here。So we say from tail equal to x。Fill next。

To x and tail equal to x。Looks fine。 that's how you add new element to the k。

How you remove elements and the from the key？ね。

![](img/569b6d62b660e28bb3f923aa74ec49d8_132.png)

Which country from from comes from Russia and suppose to and from ATO。して。Please don't ask。

 ask questions in Russia。You all just bought me。Under Russian and English in the same time。啊。



![](img/569b6d62b660e28bb3f923aa74ec49d8_134.png)

哦。I switch to Russian for a moment and one go fine， so how to remove element from it from the cuben。

So again， you take this element head， remove this element and then move to the next element here。ha。

Yeah。Again， let's remember the position of the head。Now， we need to move ahead here。And。😊。

We need to check if the cube became empt。 So if， if cube contains only one element。 So if had。

Equal to tail， then we remove this element and make an empty heap。And， if not。Yeah。

And we just move ahead the next level。Looks fine。嗯。Is correct。6か to明。That's all。

 that's how you implement the stack and cues in the point dimension model。Pretty simple。

 you just have a single item list and you make the procedures like that。嗯。Looks fine。嗯哈。奥さ。Okay。

 let's。Go to the next topic， so。Why you may want to use pointer machine model instead of standardium model。

😡，嗯。Because you might want。The trick is that sometimes when you have more simple computational model。

It's easier to analyze it because it's simple， you have simple operations。

 you always have it structure， so you have all these pointers。

 so it's easier to check what parts of your data structure may be changed by your algorithm。

For example， in in in Ram model， you have some。Segment of of， of your memory。

 and you may have someone else here to access your memory just by index。 So if。

 if someone have index。In the U， he may just change the elements here by just by having the index of this element。

啊。In rare model， it cannot happen。 You only can change the fields of the node by having the pointer to this node。

So to be able to change the element here， you， you must have the point of this note。😡。

So it's easier to like。To check what， what other elements have access to your node。 So。

 if you have some notes， you may just have the list of all pointers。To your note。

And always know which nodes can have access to your node， something like that。

Why it's maybe important because。You may want to make something like。Gnerage collection， for example。

 how the garbage collection works in Java， let's say you have some。Classes， each are some objects。

And these objects have links to another objects。Mostly like it's done in pointer marshmal models。

 it's a little bit more more the complicated pointer marsh model you may have a race in Java。

 obviously。But the idea is pretty much the same so。

If you have something like you have some objects and you have links to this。

From one object to another。对。And so on。And if。At some point。You'll find that， for example。

 you change this link to here。So you remove this thing。If at some point， you find out that this。

Object cannot be accessed from another objects。You may understand this object is not accessible。

 so it can be safely removed。So you got judge， So you just erase this object from the memory。

 and it's safe because no， no other objects can access the elements of。This object。 So you just。

You just remove this object and all objects depend on material if you have any other objects here。

Then garbage connector will also remove all these objects as well。And you can do it the magic plan。

You kind of check it my then。In Java garbage collector will just find out this situation。

And automatically remove these objects from the boundary。That's how it's working。啊。

And now the example is， for example。不道 the类。When you want your data structure to work for several。

Trereads in parallel。 So you heard from some some concurrent data structures。

Then it's much more easier to have very simple computational model because if you have a computational model like this。

 like pointer model。Again， if you have several threads。

 which concurrently operates on the same data structure。

Then you want to be sure that if you change something， no other thread can access this。element。

And what you can do in point mar model just to maintain the set of all nodes which have a pointer to your node。

 so you always know which other nodes can access your node。

So it's all part parallel operation become much， much， much easier。

 So there are a lot of different strategies how to how to maintain parallel。Opers in。ポイントましも。啊。

And the final thing which we' will discuss today， I will not talk about parallel data structures and I will not talk about garbage collection。

 but what I want to talk about today is how to make persistent data structures in pointer machine model。

8。What is persistent structure？嘿嘿嘿。😊，What can I raise？Let's raise this。哎哎。



![](img/569b6d62b660e28bb3f923aa74ec49d8_136.png)

ThereSo what happens usually when you have data structure， you have some data structure。やそ。

This is data structure。てて。Sun blade structure。You make some operation on this data structure like。

 add new element， remove some element。Change some element and so on。

 so you make some impression which changes the state of the data structure。A duration。

And data structure moves to another state， so this is the state of the data structure before decor。

 and this is the state of data structure after decor。

So what usually happens usually happens that you only have this right version of de。

 so you make de so you change something and you forget what happened before。

 so you forget this state and you only have this state of destruction。In persistent structures。

You want to maintain all the history， So you all want to maintain all the previous states of the data structure。

😡，Thatつ。So you may have access to this version and also to this version of this structure。

That's the idea。Why you may want to access the previous version of that structures。

 There are reasons for this。For some algorithms， it's good to have states of the。

For different reasons。Like you have graph and you add。Adges one by one。

 And you want to have to access the graph， which was before we edit these nodes。

 and we want to have access to another graph， which have all these nodes and so on。

So in some algorithms， it's good to have some pure version of data structures。Not。

 not clear enough what it's。I believe we will talk about persistent trees in next semester。

 not today。Let's talk about just sometimes it's important， sometimes it's good。

 it's good to have access to the all previous versions of the。Yes。

 you may think about like a version control system like the Gio or something like that， yeah。

It it theギ orチ。I think it's。要是。啊。That that's what we will try to do。

That's what we will try to do now。啊。Interesting result that almost every data structure。

 which is built in point commercial model can be made a。P systemsem。

Without any additional asymptootic cost。そ。です。Almost。

 almost any data structure built in pointer machine model can be automatically transformed to another data structure which do the same operationss。

 but it is persistent。We will not talk about this universal process。

 but we will talk about some data structures and how to transform these data structures to persistent data structures。

For example， let's have a persistent state。So we have this stick。



![](img/569b6d62b660e28bb3f923aa74ec49d8_138.png)

And we want to make it persist well。So for example， now we have some state of the stack like this。啊。



![](img/569b6d62b660e28bb3f923aa74ec49d8_140.png)

那事 so。So we have this version of the stack。Let's have it。 Let's take it。はい丈。



![](img/569b6d62b660e28bb3f923aa74ec49d8_142.png)

And now we make some operation to the stack。 For example， we push some new element to the stack。

Let's put some values here。

![](img/569b6d62b660e28bb3f923aa74ec49d8_144.png)

Let's have some like baby。C。嗯。And let's push something， so， let's push。嗯。一。

Pour some element E to the stick。So how do you push elements in the。For inter model stack。

 so we' just create element E here。And like going through here。



![](img/569b6d62b660e28bb3f923aa74ec49d8_146.png)

And now you move the top pointer to this new element。嗯哼ん。

And if you want to maintain both versions of this stack。Dcussion to。



![](img/569b6d62b660e28bb3f923aa74ec49d8_148.png)

You just maintain these two pointers to the top bottom。

 so you maintain two pointers to the top elements of the stack。

 so this will be the pointer to the top element of the version1 stack。The top one。And these will be。

The pointer to the top element of the version two stacks。

And now on this picture we have both versions of the stack at the same time。

 so if we start from the element and D， you will get the stack before we push this new element E and if you start from here。

 then you have the stack after we add element E。So you have these two stack simultaneously。

So this stack can be accessed by accessing this top element of one。

 and this stack can be accessed by this element top2。So lets let's have some operations。

 so you start from this version two and then pop this element。

So what what happens when you pop element from this stack when you simply move this top point to the next element in the list。

So you want to move this top pointer back to this elementD。And let's get version free here。

So in version3， we have the same stack， but the point of total element point here。一直。Okay。Yes， you。

 you need to do it starting from the first version。 So you start from the empty stack。

 and on each it， you add your element and maintain this version。

 you only need to maintain the top elements of the versions， you will need in the future。

 So if you need all versions in the future， then you may need some lists of these top elements。

 something like that。 If you need only some of these versions。

 then you may have some pointers to the first， if you know that in the future。

 you will need access to this version， two of the。呃。Auttiistic。

So you just save the pointer to this element top two for future。

 and then in the future when you need to access this version， you go back。How access2。Now again。

 we have this free version， we have version one， version， two and version three。Now。

 if we want to access version to。We take thisポント。Which points do this element E。

I point of position to。This is the top top elements of the version two stack。

And let let's have branch here。 So if we branch from these element， for example。

 So I want to move back to the version2 and then， for example， pushing another element。

And here we go是 four here。Then what will happen， I have this element E。I add another element。お。

By click here and make up。For to this。Now I have four different versions of this stack and let's make it interesting let's push some element here。

 So if I push from version 3 some element。Gan。Pversion 5。

Then I need to take the head element top element of the version3， it is D。Then add element G。

More mark。And connected to the top elements of the version  three， so I have version 3 ended here。

 so I have connection here。And camera。Top five points this。Letal。

So you have something like tree here。 So so it's like three of elements。

 which was added to different top elements of different versions of this stack。

But this tree contains all the states of the stack。 So if you want to take， for example， stack free。

 you'll take this stack。Find the top element of the stack3。 So from here。

 you have the state of the stack3。And from here， you have state of the stack file and so， so from。

Or any version。 So again， again， you need。To have the pointer to the correct to your version。

You don't have arrays in the pointer machine model。

 so you somehow need to have pointer to the version you want to use。的吵。That so this hard works。

 that's the persistence deck。So thisec is one of the simplest persistent data structure， actually。

Some these structures are much more complicated。But the system deck is quite simple。

Let's move to the queue。Can we do the same with the queue？Can we just use the same technique？

なプライトできよ。It looks like it's not big a difference。But it actually is。

What is the big difference between stake and the。嗯。不懂。L， don't get here。We have tail here。

What is the difference？ So imagine you have this version。this is social one。

And then you add another element。To the queue。 So we move here。 This will be tail 2。

So tail two will be here and head2 will be here。Let's try to use the same technique like remember these pointers to the elements we need to use when we move to the next version。

 So for each version we'll have two pointers， the head element to the tail element。

 that's what we need to maintain the Q， right。So for each version。

 let's remember these two pointers to the head element and to the tail them。啊。B of， when we add。

 let's get here we。So here we add another element to Q。So we have head points here， tail points here。

What will be the problem？The problem will be when you will try to add another element to the version 1。

 So if you want to take this version 1 and add another element instead of this。

 So if you want to branch here and add。And not element。

Then what you need is to have another element here。And make a point here。

But you can do it because you already have pointer to this elements。You don't。

 you're not able to have two next elements for this data element。I guess。

 you only have one point of the next element， obviously。So you can do it。That's the problem。啊。But。

There are various ways to solve this problem。 Well， just hit。嗯。

Do't have enough time to talk about this？Not sure about this。嗯。

One of the simplest way to solve this is to build a curve on top of the stacks。啊。Last lecture。

 we discussed how to build Q from two stack， right？Just last lecture。

 so you may remember that what you can do， you can make a persist mistake。

So you can take two persistent takes。Sticks， sticks。And make a queue out of them。

That's one of the obvious ways to solve this problem。Like， okay， I know how to make persist stick。

So let's take two precisions， sticks。And make a cure。And that's almost。不如。ま乗ってくさくて。

What is the problem， Why can you just take two Ver text and make a queue？嗯。You can。But。

It will be slow。 Why is this slope， Because persistent tech， Because the stack。

When you create a Q out of two steps。It has constant time of operation。

 but it's called constant amor time。Soあ。So， if you。エテク stickくセ。So if you make Q out of two steps。

 you will have Q with constant time of operations， but it's constant amortize time。Yeah， like。

You can watch the previous lecture。언業도不 있어。It was pretty nice。

 So you have and here here you have constant amortized time。

And when you have the amortized time of the operation small。

 you cannot just create a resistant data structure。Because what will happen。

 so you have some versions of your data structure。And the amort time is small。

 What What does mean the amort time is small， It means that if you have some long duration。

Then the potential function of your structure is decreasing like。お。Yeah。

 we just got this last time which just I believe you remember this。😊。

So imagine you have some long operation here， so this operation is very long。

But it decreases the potential function， so you have potential function is big here。

 but it is decreasing here。So this long time is compensated by decreasing of this potential function。

So the total time余 time is small。ドルマまです。Okay， okay， okay， I'm going you remember single last day。

So what will happen when you have the precision data structure。

 you may want to make this long operation。And then go back。And make another long operation。

 so you may go back to this version and make another long operation。

And the potential function here is also small， so this operation is also one。

And you can do it many times so you can you can go here， then go back。

 then make another one operation go back， then make another one operation go back and so on。

 so all operations alone。So the amort tank will not be small。That's what happened。

So I mean's that's what will happen if you have， if you try to make persistent data structure from there。

Iorize the destruction。And yeah， the way of solving this is by using notmatize structure。

 you can make a queue out of stack with constant time， not with real constant time。嗯。

Not today I think， but you can read about this， you can make you out of steps with real constant time alters。

It's a little bit more complicated than more test time。 So you need， again。

 you need to have one input stack， one output stack。 And when this stack is emptypt。

 you need to transfer all elements from this deck to this stack。

 but you can transfer not all at the same time。 but one by one。 So only operation。

 you transfer some elements to the new stack。But there are some difficulties you can transfer elements because you will add more elements。

 so you need to have some buffer stacks and should transfer them into these buffer stacks then transfer into the next stack and so on。

 so you may build the nonmarized queue from like five stack。I know how to make from six steps。

I believe it can be from some like four text。So it's possible， but。ノトで。啊。

What I want to talk about is little bit more a little bit different thing sometimes you don't actually need things like this。

Sometimes you need to have persistent data structure。Thisive some linear order of the versions。

 so you only make these operations in linear order so you only modify the last version。

Sometimes it's happens， so sometimes in your algorithm you need this that structure。

 but you know that you will never go back and modify this version。

So you don't have situations like this。You have some linear order of your operations。

It's kind of strange for the queue because in the queue， all operations modify the queue。

But if you have some data structure which have operations which don't modify the data structure。

 like some queries， like how many elements we have what is the minimum element？you some statistics。

 but do not change the current state， so you may want to have something like this， so there are。

So there are some versions。And you only want to modify the last version。おかし？1，2，3，4。

You can access any previous version and find some statistics about this。

 but you only modify the last version of data structure。 that's the idea。

 So let's call the partial Per data structure。O。In partially present structure。

 it's okay to use amortizeized structure。 You will never have situations like this。Sorry。

 but you you you， you don't have problems。 and you have。Some long operationss。啊。まで不作けど。Yeah。

 but for Q is not it's not very interesting because in Q。

 all both operations like add element removal element changes the state。

 So it's for Q is not interesting let's。Talk about。Liinked list。

So let's have a partially persistent linked list。In which you can add elements， remove elements。

 and iterate overall elements。So I want to now I will build a link list。

APartially persistent things list with like， let's say free operations。We will add element。

 let's see it after again， after。啊。😮，嗯 응。We will。That's about remove element。And。

Let's say we have iterate or all elements。え。The iterate will just iterate all elements of the list。

 something like that。You make me make have more complicated earthquake。

You want to be able to go in both directions of this list you you may want to have from some from left bottom to the middle and go back。

 something like that。So you'll want to be able to walk along this list in both directions。F。

So how to create a partial consistency list。哼。Let's write the right again。So that is everything。



![](img/569b6d62b660e28bb3f923aa74ec49d8_150.png)

What is the idea first， let's enumerate all the versions。



![](img/569b6d62b660e28bb3f923aa74ec49d8_152.png)

So every version has some number assigned to this version。そう。

Since this structure is partially persistent， we have some linear ordering on the versions。

 so we have some old versions and we have some new versions。In fully precise structure。

 it's not true because if you have like this version and these two versions。

 so which one of them is older， which one of them is newer。

 so there is no connection between these two versions， but if you have partially precision structure。

 you always can compare to version， so this version is older in this version and so on。

Let's use this and enumorerate all versions all versions of the structure from left to right。こ。



![](img/569b6d62b660e28bb3f923aa74ec49d8_154.png)

Now how how to add new elements in the middle of the La list let's have some elements。



![](img/569b6d62b660e28bb3f923aa74ec49d8_156.png)

Let's have some element X。Let's go this element。That and we want to add new element y between that。

So you have something here。Something here。And so on。Yeah。So you have。This part of the en。

 and you want to end。New element wise。

![](img/569b6d62b660e28bb3f923aa74ec49d8_158.png)

I want to add it between element X and Z。And let's say now we have versions。Let's say还有 version。5。

So we have some previous versions。

![](img/569b6d62b660e28bb3f923aa74ec49d8_160.png)

And our current isization like this， so we have like previous versions and now we have version 5。

 so this is version 5。And after we're at element， why we will have version six。What looks like。系有咩。

Why we have version six。

![](img/569b6d62b660e28bb3f923aa74ec49d8_162.png)

![](img/569b6d62b660e28bb3f923aa74ec49d8_163.png)

嗯。And we want to be able to access these go versions。

 so we want to be able to move along this list and to move along this list。

Which includes this element way。How can we do it？Let's maintain so let's maintain two versions of these two nodes。

 So for these two nodes， X and Z， we will maintain two versions of this node。

One version is before we add elementement Y and another version。嗯。啊。Which you based is not like。

我 this。And the same for this note set。We'll have another version of this node。

Which knows about this notebook。And the idea is like this。 when we， when we are in version 5。

We use these pointers to go。In this version 5 list。And then when we have version6。

 we use these pointers， so we have this list which includes element Y。嗯哼ん。😊。

But how can we how can we check check what version of element to X is to to use when we walk along this list。

 Ins very example， we use by the index of the version。 We know that this new version is。

Wai when version is from six or if current version is greater or equal to6。

Then we use this new version of mode X， and if version is less than 6。

 then we use this previous version。So we maintain two versions and this number。

 this number saying that if the current version is greater or equal to 6。

 then please use this version of node X and before version 6。

 please use this version of node X and same thing here So this。New version is used only after。6ix小时。

Let走。嗯嘿。That's so， so how？Again， how do you use this linked list？You have like global variable。

 which is current version。😡，And like current node。And when you need to move to the next element。

You check the current note， it has two versions。Which version can you use this all of this。

 so you check what is the current version？And select one of these versions of the note and then use this pointer to go to the next node。

 And so let's go to here。How is X connected to previous El， please bye bye？

T by by by the same pointos。 Yes， a little about this like So yes， this picture is looks cool。

 but it's not not well describe what's really happening here。 So in in pointer mar model。

 you don't have something like like nested nodes or something like this。 Yeah， so this is like。

This is like a scheme。 so what's really happening here。啊。YouYou may have two versions。One version is。

There are two different techniques。 how to apply this in real point machine model。 first way is to。

Just have this big note X。Okay。Which have two set of。Fields like you have these fields。

Like previous one， next one。And some data one。We also have some data， right？So we have these fields。

For the first version of node X and another set of the same fields。

For the second version of this though。And you also know know this version yes。Soう。

So you want to you may just create from each this element， something like that。

 so you create this like a big node with two sets of fields and another field which says this version。

Well， that's perfectly legal， I think。You just extend your note twice。So it's。

 it's still constant size no。Another way to do it is like to create like。

Really two versions of this node X， This is the x prime three x。

 and like another small node like helper node， which have simply version。

And to pointers to here and to here。So here you start from this helper node。

Check what version you need and then go to either of these versions of the X。So。

 this block just can be implemented like this and like this， not a big deal。

What is the crucial part is that we will never have more than two versions in this block。

 so in each block like this we will only have maximum two versions。

We will never have more than two versions in the single block。

So you can implement it like this or like this。That's， that's。That's important。No。What happened。

This is a simple situation。 We add element here， but you have many operations。

 so at some point you may want to add another element here。

So you will try to add another version of block of elements set。

And you already have two versions here， so there is no room for the third version。我떻不。

Let's write it here。系。Oh what's hurt themselves。ちょっとラズで。So what may happen again？

You try to add another node another node Y here。You want to add it between nodes， X and Z。And nodes。

 X and Z already have some previous versions。So there are two versions of node X。Something like that。

 And there are like two versions。Of note。ざ。And two versions of this node and two versions of this node and so on。

This might happen。What can you do in this situation again you want to be able to move along this list using these pointers and also do some other pointers to walk this and go from x to the y and here。

And there is no room for any extra pointers here。 so what we'll do， we will create another note。

So we will simply copy this node x to another node。Let's本 her。Yeah。Just have another note here。

And move these pointers to this。And the seat for the nodes。

Just create another node and make theポント of this。那为你读。Create pointer from here to node X。

But there maybe be already two versions here。 So if there are two versions in this node。

 then again we copy this node。No greatlist。And we do it to the left until we reach node。

 which have no second version。 So we go to the left。Until we find some note， which heavenly won。

And when we find this node， we add second version to this node， so we take this node。

 add the second version to this node。Yeah， do something like that。pencilそ。

And the same thing on the right so we look on this node， it has two versions it called Fab nodes。

 we have F node here， so we just copy this node to the new node。

 go to the next one if it is fed we just copy it to the node to the new node here。And go to the next。

 And when we each。First。Not fat no。We add second version to this node。And makeポント here。嗯。Let's all。

If all nodes to detail have two versions， then we'll copy all the notes。 Yes。

 it may happen that we reach the end of the linked list and copy just just copy all the notes。

 It's fine。 then we just copy all the notes till the end of the list。Yes。

 the idea is that never have more than two versions in each node。

 so each version each node have no if except at most two versions。Yeah。

 now let's calculate the time complexity。 What is the time complexity， No。

 worst case time complexity is obviously linear。 So in worst case。We may add new element。

 All elements of the list have two versions。 So we start from here and need to copy all elements to the next element to to do these next two to copies。

These may heaven。But let's calculate the amortized cost of de。I claim that I'm up this coast。

Of operation M。いか。Why this room。嗯。Because it partially correct。

 the progression is partially persistent。So we only modify the last version of the structure。

So let's have some potential function。Let's say that again again。

 how to find the good potential function。To find a good potential function。

 we need to look on the long operation。 What happens when we have a long operation and we have long operation。

 We copy all these nodes to these new versions。 So we just go to the to the closest node f node and then copy all these nodes to these new versions。

And now when we find how the lung operation works， we need to find the potential function。

 which is decreasing when we make this long operation。嗯哼。

So we start from here and try to find the function。

 which is decreasing when we move from this state to this state。Normally now it's quite obvious。

 so we want to find something which is decreasing and what is decreasing is the number of fnot。

So we will say that potential is simply the number。All fake notes。

So when do you copy these elements here。 So if you copy， let's say。So if you corpi K elements here。

Then you spend the K operations to copy these notes here。

 and the change of the potential will be minus k。Plus two。

 so we have these two two new ftanyls plus2。So the amorttan complexity will be two。

Why cant we stack on each node。They can have two version traditional？嗯。Because。哦。

Why do we have only two versions in each node， if you have more than two versions。

 if you have the list of versions？😡，If you have list of versions。

 you want to be able to find the correct version。 So how to iterate over this list。

 So when we iterate over this list， we so imagine use you are now in some node。X， no X。

So imagine you want to iterate all elements of the list and you now stay in node X and node X have many versions。

Now you want to go to the next。Element of the list。 So you want to find the next pointer。

And to find that pointer， you need to find the correct version you want to use。

So you need to find some way to find a good version in this list of versions。

And there is no way you can do it in constant time。You what you can do actually。

 you can maintain a balance search tree of these elements Yes you can make a binary search tree of this over these versions and find the correct version in logarithmic time。

But this will add a logarithing factor over all time complexity。

 so you will be able to maintain this operation is rate noted in end time。

 but n multiplied by a logarithm of number of versions。

But if you want this iterate to work in linear time。

You need to be able to pick the correct version in constant time So each time you go to some node。

 pick the correct version， go to the next node， pick the correct version， go to the next node。

 and to be able to pick the correct version from this list， you need to getmic time。

That's why we only restricted to have only two versions when you have only two versions。

 then you can pick the correct version in constant time， so total time will be reed。嗯。Okay。

 hope it's clearな。嗯。That's actually all what I tried in yesterday today。Maybe we have some special。

 we need some special students to discuss some topics which。Just didn't fit in in this course， but。

It's really fun， for example， to discuss how to make this this non amortized queue out of six steps it's a fun data structure so maybe we'll have some additional streams about this。

 not sure about this。Maybe at some point。Okay， I think it's so for today。

 so thank you for joining today。🎼，🎼，🎼，🎼The。🎼，🎼，🎼，🎼，🎼，🎼The。🎼。

