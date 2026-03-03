# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p39 18_06_01_使用二叉树作为数据结构.zh_en -BV1v2421P7pt_p39-

![](img/c8d5a6e714e94686b6e7884dc680b8b9_0.png)

So up to now， we've done all the easy stuff。So it's time to do the linked。Tree map。

Which it really is kind of a modern flexible key value store。

 This is a nice key value store that you would want to use if you were a software developer。

 Our linked treem is ordered。Like Python ordered dictionaries。It stays sorted。

 meaning that not only does it stay in order， it stays in sorted order。

 we insert things and they go in in order like a Java tree map。You can be iterated。

Like a C++ map or an ordered dictionary， but not a Java tree map this just boggles my mind why you can't well。

 we'll talk about actually why they didn't do it， but it's not that hard why they so。

And we're going to have fast lookup， so the problem with a list map is it's got a lot of nice features and we can make a sorted list map and we're going to in this section。

But the problem with the list map is lookup is slow and so we're going to actually pretty much use the tree part to do fast lookup and you can see this in 6。

5。2 of the textbook so we are going to do something that's pretty common in data structures and as we are going to maintain two whatever the entries and they're going to maintain simultaneously asorted linked list through the entries and a binary tree and so we're going to look at them separately and then we're ultimately going to find them together we're going to put them together。

So。

![](img/c8d5a6e714e94686b6e7884dc680b8b9_2.png)

Let's talk about what a tree is a tree is a。Structure。

That the tree mapap entry you see has a left and a right。

So the things to the left are things where the key is lower than the current right， so H equals 42。

 The question is where would。A go， well A goes to the left。 where would T go。

 Well T goes to the right。 So the idea of the tree。Is that whatever entry you're in。

 there's a key in that in the entry， and then you can either go left or right based on the comparison of the key。

And instead of having a head and a tail， there is just a root。

 so the root is the top entry of this tree， and then there's a series of left and right choices that you make。

 and each entry has a left and a right。And the treem entry has a key value pair。

 and we're going to keep key in value as public because this is just an entry。

 but now there is no next right this is why we are using abstraction because we are not even going to give them a next。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_4.png)

We're going to have a left and a right。Okay， and that's we're not going to show that。

 we're not going to let people see that we're just going to give them a set of methods to mess with our treem and we're going to deal with all this stuff and we need a left and a right to do it。

So just taking a look at how it works is let's just say we're going to。

 in this current tree that I've sort of built， they're not always balanced。

 I happen to balance it just because it looks better on PowerPoint slides。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_6.png)

But let's just say we're going to insert in this tree a G equals 25。

 so it's got a key of g and a value of 25。So what you do is you start at the root and you compare it and you say。

 oh。G is less than H， so we're going to go down the left hand side。

 so you can think of it as you're walking down the left hand side。

 then you are encountering D equals8。And then you're like， okay， G is greater than D。

 so we got to take the it's like driving a car。Turn right at intersection D。

And so we do and we're working our way down and now we have we're looking at intersection F and we've really got to go left or right and so F G G is greater than F。

 and so we're going to go to the right， not the left and so we do。

 and so that basically is the path that we took and so to insert G into the tree。

 we find the greatest，How you less than， which is F and you're kind of inserting it if you think about it between F and H right so it the next higher one in the tree is H and the next lower one in the tree is F and that was the trip we did。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_8.png)

I like to think of this sort of sort of trickling down the tree and making these decisions as almost like a pe chinko machine where you hit the balls。

 they goinginging it's not random of course， it's very precise。

 but it is kind of like you stop at the top and you make a bunch of you know binary left right decisions and eventually you find yourself somewhere at the bottom。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_10.png)

And so if we kind of look at。The tree map put。And we are going to start at the root。

And then we're going to do a comparison。And if we find it。The comparison is going to be zero。

 we update the value。And if we don't find it and it's less than。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_12.png)

We're going to go left。 And if it's greater than we're going to go right。

 And so this is basically the idea this while loop will trickle down the tree going left and going right。

 and it will either。Find the value if if there's a match， like if we're looking for F。

 we'd have found it and we'd have stopped and we would returned if we're looking for G。

 we won't find it， but we will find where we're supposed to insert it。Okay。

 so the last thing that we talk to， which G will find its way down to the right of F。We will find。

Where to put it。 So as long as the tree is correctly maintained。

 you will either find a match or you will find the right place to insert it。

 and the tree will it's not guaranteed it's not guaranteed to be balanced。

 There's further algorithms that can make the tree balanced。

 but the key thing is is that the order will be right。 so so by inserting。

 following these rules following this algorithm。 The order will be right。

 and you will always find the right place to put it。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_14.png)

Or you will find a matching place and think about how dictionaries work， right， you say x sub。

Hello equals something。 Well， there's either going to be a hello key in there or not if there's not。

 we're going to put it in。If there is， we're going to update it， and that's what this code does。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_16.png)

We're going to create a new tree map。We're going to put h equals 22 and then we're going to do h equals 42 which replaces H right then we're going to do D equals8 then we're going do B equals 1。

2，3 and then we're going to do F equals6 it turns out I'm kind of doing this in order so it doesn't get too long on the page and then I'm going to do a dump and remember how important a debug is when I first wrote this code you can dhar willll bet you that I had map dump it was map put map dump。

 map put map dump map put map dump so I could like see what it does and so the map the dump if you look at the dump。

Then then we put in K and M and J， and then we dump it again。

And so what I've done is if you look at the map output。

 you see that the map output has these h equals 42。

 and then it's kind of trying to give you some sense of the treeness of it， okay， meaning that。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_18.png)

The B equals 123 F equals 6 and d equals 8， the number of vertical bars tell you how deep in the tree you are。

 and so you can see that the immediate child nodes of H and the second dump are D and K and the child nodes of K are J and M so you can draw this all up and so the idea of my dump code is I'm trying to sort of draw you a tree。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_20.png)

![](img/c8d5a6e714e94686b6e7884dc680b8b9_21.png)

So here is the dump code， now this is very， very different。And literally， this is the first time。

Well I talked about recursions and functions， talked about stack frames and stuff like that。

 but if you go all the way back to Python for everybody。

I delay talking about recursion until there's a real value for it， and it turns out。

This is a beautiful use of recursion。And if you didn't write this recursively。

 you'd probably have to write your own stack， and that would be like a bummer because we we're going to recursively go down the tree and we're going to keep track of the depth。

 And the idea of the depth is it tells me how many vertical bars to print。

 So we come in and we're pointed at a particular place in the tree， maybe the root。

 maybe the top one。

![](img/c8d5a6e714e94686b6e7884dc680b8b9_23.png)

And depth is going to be zero。And so if cur is no we're done。

 a key thing to recursion is you've got to have a way to get out。

So if we get to the end of some tree subt and we get to a null。

 we go left or right and that it's a null， don't print anything out just you're done。

 you've gone one beyond the leaf of the tree and Curs null， so just return。

Then what we do is we have a for loop depending on depth that prints vertical bar space。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_25.png)

That spaces it over。And we're going to go down the left tree。

And then we're going to come back and we're going to down the right tree and this is what's called a depth first search for those computer science nerds right。

 and so we're going to go down the left。And you'll notice that when we go down the left。

 if the left is not equal to null， we are going to dump the tree on the left。

With depth equals depth plus 1， and so if we start with a depth of 0， that's going to become 1。

 and then if we recursively get down further then it's going to be 2。And then if and then that。

When that recursion comes back。If cur right is not equal to now we're going to dump the tree on the right。

 so what you see is。

![](img/c8d5a6e714e94686b6e7884dc680b8b9_27.png)

Dump the tree on the left recursively， which means go all the way down the left then come back up。

 then dump the right node， then come back up， go up again and dump the right node。

 and so you see this like how the order， this is a depth first search of H， we're going down past D。

Then we're going even further past B。And then we're coming up from B and we're going back down from D to F。

 we're coming up from F， then we come up from D， then we go across H， and then we go down to K。

 but then we go to the left of K， which is J， we go back up， and then we go to the right of K。

 which is M， and then we go back up， we go back up， and we're done。

So the calling sequence to this is tree map， dump tree， self root with a depth of 0。

 I will say this when I wrote this code the first time I had printfs all over the place。 Now。

 I pretty much know how to do a depth first search of a tree， but still。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_29.png)

You。In a debugging， sometimes sometimes you make your tree incorrectly and your debugging is like，h。

 that doesn't look like what I thought it was gonna to be and so I don't be ashamed if you have to put print statements in all over the place。

First get your dump working， just make sure your dump works because then you can debug everything else with the dump and it gets pretty simple。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_31.png)

And we've got the default， weve got the key， and we've got the tree。

 so we're going to start a while loop where we're going to go down left， right， left right。

 left right， right， so we're going to start at the root。

We're going to compare the key to the key we're searching for the current key。If。They're the same。

 then return the value。We could do this recursively。

 but that you don't do recursion if you don't need to。 if the current key。

 if the key we're looking for is less than than the key we found， we're going to go down the left。

 And if the current key otherwise we're going to go down the right。

 And so you can see this thing is just going to pe chinko its way down。

 ding ding ding ding dk to the right spot。 And if it gets to null。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_33.png)

Then we return the default right。 remember， this is like a dictionary。

 If the keys not there on a get， we return the default。 You can see why。Gidto Van Rassom。

In Christmas。1987。Created a function called Gt， which looked for a key and took a default value。

Because this code is what？Well you， you write， what I'm going to return Noll and then I have an F statement。

 Heck， no， just passing a default if you get to the bottom of the tree and you haven't found it return the default。

If I want it to be null， I can make the default null right， away we go， so this is beautiful。

This is beautiful。So。From that beauty。Both the dump are beautiful and the get is beautiful。

Iterator is a pain。You just can't easily build an iterator for a pure tree if you have nothing more than that tree。

So a。List map can support an ordered iterator we saw before a hash map can support an unordered iterator。

 but a tree map cannot support an iterator without building some kind of a stack and the。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_35.png)

The problem is， is that。The concept of current is just so complex。 When we're doing recursion。

 the concept of current is。Just so implicit， it's actually in the call stack。

 the notion of current because there's really。When you're doing the dump。

 you have a call stack of currents and then when you go back up the call stack。

You're getting a different current， so you're switching back and so you either have to make your own stack of currents。

 you could build a iterator for a tree， but you'd have to build a stack。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_37.png)

So a lot of folks sort of don't want to do that。We could build a stack， but we're not going to。

 so what we're going to do is we're going to do a technique for our iterator。

That is a common technique。When you have a data structure that almost does what you want and then you have another data structure that does what you want。

 you combine them。 so if you look at this tree， there's a lot of nice things for searching。

For replacing， for inserting and it does all that very fast because it's actually log in because the height of the tree is log base two of the width of the tree right the number of items in the tree so it's log base two is so it's super fast。

 all my trees are small， but if these trees get big。They're super fast。

 It goes down the pe chinco its way down to the bottom really fast。

 but I can't easily build a iterator。 So what I'm going to do is I'm going to add to this a linked list。

But I'm going to have the link list simultaneously working。With the tree。

So each of these items is going to have a next and a preve and a left and a right。

And we are going to almost write the code mentally independently for the tree code and the linkless code。

Okay，So we're ultimately going to combine these things together。

 there's not a separate linked list in a separate tree， it looks like this in a linked tree man。

So think of each one of these things having a next and arieve and a left and a right。

And we maintain them in such a way when we're doing inserts that everything works perfectly。

 So we're going to simultaneously maintain with the same entries。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_39.png)

A tree and a list， but we're only going to use the list to build the iterator。

And we're going to make this asortred list because these things are in order。

 The tree is helping us quickly find the place to put it， but also where to put it in order。

So let's take advantage of that。So this is a sortrded， ordered dictionary。In Python lingo， okay。

 so just remember that these entries， these list tree map entries are simultaneously participating in a tree。

And at the same time， in another layer as it were， participating in a linked list。The tree map。

 which is the tree map structure。Has a head and a root。Because at the same time。

 TreeMap is both a tree and a linked list。And the map entry is going to have a next。

And a left and a right and again。

![](img/c8d5a6e714e94686b6e7884dc680b8b9_41.png)

You just almost keep these things separate， right in your mind。When we're doing tree things。

 we're going to use left and right and root， and when we're doing list things。

 we're going to use head and next。And these are things now by now that should be sort of。

Familiar to you。So this is the structure that we're going to build and maintain。And up next。

We're going to build the put code。Or this。Combined two layer data structure that has a tree and asorted linked list all at the same time。



![](img/c8d5a6e714e94686b6e7884dc680b8b9_43.png)

🎼Yeah。🎼Yeah。

![](img/c8d5a6e714e94686b6e7884dc680b8b9_45.png)