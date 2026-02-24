# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P37：1 - Spring 2023 Discussion 08 Content Review.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发比哈比。🎼Ba。

![](img/0c180cf7bb30c63d5483ad9fc1ee2d5d_1.png)

🎼And。Hello and welcome to CS6 UNB B 2023's Walkthrough of discussion number eight。

 which is about Bearies， LORBs and Hashing。Before we get started。

 some quick announcements which once again may or may not be relevant to you by the time that you watch this video。

 but weekly Surve 7 is due on Monday， March 6， labb 8， which is about hash maps is due on Friday。

 March 10th。Project 2 a Nordnet is due on Wednesday March 8th， Project 2 B is due on Friday。

 March 24th， which is the Friday right before spring break and homework  three。

 which is a grade scope assignment that's meant to be midterm review is due on Monday March 13 and then I didn't put it on this slide but the midterm two for this class will be on Thursday。

 March 16th from 7 to 9 pm。Okay。So let's jump right into some content。

 we have a bit of a packed schedule for today， but first up let's talk a bit about bee trees。

 so bee trees are trees that serve a similar function to binary trees while specifically binary search trees while ensuring a bushy structure and as a check。

 think about why BSTs and binary trees don't generally ensure a bushy structure。😊，In this class。

 we'll often use bee tree interchangeably with two， three trees。

Each node can have up to two items and three children， which is why they're called two。

 three trees because the two stands for each node multi nodeode can have two items and then the three stands for each multi nodeode can have three children and there are variations where these values are higher known as two。

 three， four trees and beyond like for example， nodes can have up to three items and four children。

And all leaves are the same distance from the root which makes getting getting the operation take theta of log n time so in the average case it takes login time to find an element in our B tree so cycling back a little bit to this check that I put up here like why don't BSTs necessarily in bushy structure you'll remember or hopefully you'll remember that last week when we talked about binary search trees or BSTs even though they were really nice and they could be like these nice balance trees that would give us big O of log n runtime operations for operations we weren't necessarily guarantee that the BST would be bushy right as an example let's say we had the keys1。

2345 that we want to insert to a binary search tree if we inserted those keys inserted order so like we insert one then we insert two then we insert three4 and five we get something that looks a lot like a link list and not really。

😊，like a tree right so in that case we would call the binary search tree spindly where the operations like for like find。

 get put remove take approximately linear time in the worst case so that's kind of the motivation behind why we use bee trees and bee trees are like more part of or are part of a like larger kind of set of data structures that we call balanced search trees which basically keeps kind of like the properties of a BST a binary search tree but ensuring that operations take log end time as opposed to the binary search trees potential linear time when the trees spinly okay so。

When we add to a bee tree， we first start by adding to a leaf node and then pushing the excess items aka typically the middle element up the tree until it follows the rules that we discussed in the last slide。

 So bee trees here， we know that a node can have maximum two elements and maximum  three children per node So in an example over here。

 let's say we were trying to insert five into the be tree that we had over here。

 which was nicely balanced with the  three，7 node a  one2 node on the left a 46 node in the middle and a nine node on the right。

 if we tried to insert a5 we'd basically come down or we'd go through starting from the root node and see that five is between 3 and 7 so we'd come down to this middle child node。

 which is a leaf。 This multi nodeode is a leaf containing four and 6 and we tried to put the five into。

This leaf node leaf multi node down here right， however， this is going to create a temporary。

Multi nodeode with three elements。 And we know that in a B tree。

 we can have maximum two elements per node right so what's going to happen is that we push up the middle element。

 the five that we just inserted up one level。 So we're pushing it up into the parent node and when we push it up into the parent node we run into this issue again where we see that 3。

5 and 7， we can't have more than two elements per node right if we did。

 then we'd have four children here， which isn't allowed in a2。

3 tree right so we'd repeat this process recursively until we balance out our tree and it follows all a rules。

 So once again， we'd push this middle element， the five up so that finally we're left with this five as the of our2。

3 tree3 is the left child 7 is the right child and then we redistributed。

The the respective children of three and seven appropriately according to their values in comparison to the roots of these smaller subtes。

 okay？So。LL RBs or left leaning red black trees are a representation of bee trees that we often use because it's easier to work with in code in an LL RB。

 each multi node in a 2，3 tree is represented using a red connection on the left side。

 So I would just like to quickly note that you could do like。R LRBs like right lean red black trees。

 but for the purposes of this class we pretty much only talk about LLRBs and there are red black trees more generally。

 but we don't really get into the details of that。But basically what this slide implies is that there is a one to one there's like a one to one mapping of a unique LLRB to a unique2。

3 tree， so how we represent or convert between an LLRB and a B tree is let's say we're giving this B tree over here each multi nodeode we want to break it up so that the left like the lesser element in that multi nodeode is a。

Is。A left child of the right element connected by a red link。 so what we mean by that is let's take。

 for example， the root node over here， we have this multinode with three and7 because three is the left element in the multi node。

We're going to make three the left child of seven， but we're going to denote that they're part of the same multin by making that connection from parent to child with a red link。

Likewise we're going to do the same with all these other multi nodes so we're going make twos red left child one six is red left child4 right because they're part of the multi node and then elsewhere where you see black links that's just a regular connection from parent to child in ourB tree so you'll see here that sevens right child it's black it's a black link to nine and then three has a left and right connections that are blocked to two and6 so you'll see that up here in the original representation of the two3 tree three was indeed part of the parent node of the two node and the six node okay。

So there are a couple of invaris that LLRBs must follow so first off。

 the LLRB must have the same number of black links in all paths from a root to null link this is not the same thing as root to leaf and this is like a concept that is like pretty confusing and I'll talk a little bit more about it in the next slide which I copied straight from Josh's lecture because it is like a pretty like weird concept to wrap your head around so don't like Fred if you don't understand it fully right now I'll talk about it in a bit the second invariant is that a node may not have two red children so by children two red children I mean it may not have two children that are connected by red links。

And then we also stipulate that because this is a left leaning red black tree。

 all red links should be left leaning。😊，Number four， the height of the LLRB， akaA。

 maximum the maximum number of links in the path from root to leaf can be more than approximately two times the height of its corresponding 233 and we say approximately two times because I believe that it can cap out at I think like2 x plus1 where x is the number of links in the corresponding 233 and lastly。

 we insert element as leaves with red links to their parent node。

So all these invaris together mean that sometimes our LLRB becomes unbalanced， for example。

 it violates one of these rules， so we need some way to fix that and we'll talk a little bit more after I discuss point number one in depth。

 but we'll talk about the balancing operations in a little bit。And as a quick side note here， two。

 three，4 trees which we very briefly brought up in the Bre slide correspond more generally to regular red block trees。

 but our focus in 61 B is on LLRBs which have a one to one correspondence with a unique 2，3 tree。

 okay？So to address this point up here， the LLRB must have the same number of black links in all paths from route to num。

 which is not the same thing as root to leave let's take an let's take a look at an example from Josh's slides about balanced search structures I think this is in like。

I don't remember I think it's like lecture 18 or something like this you can like dig it up in the slides but in in the past and even when I took it as a student I was mistakenly taught that the number of black links to any leaf must be the same in an LLRB but there's like a very niche like edge case that makes it so that the correct invariant must be the number of blacklink to any null link must be the same and as an example。

😊，Josh provided a tree here that's in an invalid LRB under this new definition of the correct invariant versus the old definition which stipulated that the number of black linkss to any leaf must be the same under this under this like proposition this is a perfectly valid LLRB but when we convert it to a two3 tree something doesn't look right right like if we convert this like fake LLRB over here to a23 tree it's missing a child this is not a balanced two3 tree like in fact like you can try it out on your own you can try like putting in the keys B G A an X in any order you want and you'll find out that it's not possible to get a tree that looks like this okay so we basically had to update the invariant to say that in an LLRB the rule is that the number of black links to any null link must be the same。

So what that means here is this would make this LLRB in or this proposed LLRB invalid because the null link you can kind of think about it as like a link to a child that doesn't exist so for example B would have a right null link because B doesn't have a right child and likewise X could have a null left and a null right link which。

Like because x doesn't have left or right children right so when we count up the number of blacklink to any null link。

 if we look at the path from like G to X， for example。

 we'll see that G to X and then x to null there's only one black link on this。On this path right。

 but if we look at the path from G to B to B's no link right child there's no black links on this path right。

 there's only a red link So this is just like a very teeny tiny edge case that you need to think about when you're determining whether something or is an LRB or not just like。

Just like something that was like a big point of confusion in the last couple of semesters。

 including on staff because many of us were taught the wrong andvari so don't worry if you don't fully understand it right now we will get there okay anyways so previously were talking a little bit about the fact that our LLRBs because we have all these rules they must obey they can become unbalanced right so let's talk a little bit about the balancing operations that we can have。

So first up is rotate left so we need to rotate left because one of the rules of the LRB is that we cannot have a right red link so in this example tree or subtree over here if we have a right red link from a to B we need to rotate left on this parent link so a has a red link from a has a red link to B and so we're going to rotate left on a which is basically going to make B the new parent or yeah it's going to make it's kind of going to like split the role a little bit where B is the parent of a。

And B has a left red child linked to A， and A's right child is now C。Okay。

 next we have the rotate right operation and this is the motivation for this is because we can't have two plus consecutive left red links so in this tree over here we have a left link from A to B and then a subsequent red link from B to D and they're both left links but we can't have two consecutive ones so we'd rotate right on the a node over here and the result of that would be that it would give us B as the parent of D and A and it has a red link to D and it has a red link to A and then A's left child is now C。

😊，Lastly， we have color flip and the motivation for color flip comes behind the fact that we can't have both child links of a node be red so in the example sub over here we have that A's to children are both red connected by red links So if we color flip on this node a this is going to flip all of the colors associated with the links that are connected to a so you'll see that both of A's child links which were once read are now black and then the。

😊，Link from B to A， which is A's parent is now read。So。😊，If you look like really。

 really closely on this slide you'll realize that hey wait a second after we rotated right didn't we just run into this issue where we have bees both of bees'es children being connected by two red links well that that like kind of trickles down into the color flip pace right and so if you think about it like if you think about the balancing operations as a whole they actually。

Can possibly cascade into each other。 So this slide doesn't show it exactly。

 but oftentimes well see that a rotate left operation will cascade into a need for a rotate right operation and a rotate right operation will cascade into the need for a color flip operation。

 which is like what we see here on the slide。 And if we will see very shortly in the worksheet。 Okay。

Okay， so we just covered B trees and LRBs and we're going to shift gears like massively and talk about hashing I'm like so sorry about the like sudden shift in topic it's just that we have to make the discussion content schedule align even though the topics can be pretty disparate at times。

😊，Anyway， so hash functions are functions that represent objects as integers so we can efficiently use data structures like hashet and hashmap for fast operations like get or put an ad so previously when we had things like a link list we found out that the addd or the delete or the get operations took like linear time or in the worst case with respect to the number of elements that were in our list right and we discovered that hashets and hash maps allowed us to look things up like very quickly or like find out whether something was contained in its set very quickly right and we considered that constant time that's only made possible because of hashing。

😊，So that's kind of like the motivation behind why we even have hashing the first place so once we have a hash for our object we use modo to find out which bucket it goes into if this isn't making a whole lot of sensor now that's totally okay we'll walk through an example very shortly and also I think that lab8 in particular is super。

 super helpful because it's all about creating a hashm from scratch anyways so for example if we create a hash function for a dog class by overriding objects hash code function like this let's pretend like we represent a dog in a hash code by returning 3 37 times the dog size plus 42 so you'll see here that we represented this which is a dog object as an integer right hash code returns some number。

😊，So then when we try to put the dog into a hashet， the hashet code might look something like this。

 we'd basically want to look for the target bucket based on the dog's hash code。

 which we overwrote over here， moded by the number of buckets that we used to represent the underlying hashet。

 and then we would add the dog to the target bucket that we found。

So a little bit of a note on the modo over here。 So why do we need to use modo Well。

 the issue is that。I think the labs eight slides do a really fantastic job of talking about the motivation behind this。

 but basically integers in Java can be like integers between like due to like number representation constraints like for a 32 bit system。

AK like an eight byte system。Oh sorry not an8 byte a four byte system my bad the number the the integers that can be represented in Java range from something like negative 2 billion to positive2 billion like roughly and the idea is like okay like if we。

We totally could or。Intuitively， we might think like oh。

 we could have a bucket for every single one of these integers that Java can represent right but that takes like up like an absurd amount of memory and I don't even think that like a regular laptop could handle that so it's like not necessarily the greatest idea so the idea behind like hashing and buckets is that we instead of having like 4 billion total buckets。

 we can have like a much smaller number of buckets。And then basically take this hash code and mod it。

😡，By the number of buckets so that the resulting target bucket falls in some number that is between zero and the number of buckets that we actually have to represent our hash hashm in its underlying like array or something like that okay so that's kind of like the motivation as to why we use modulus here。

Okay。So in each bucket we deal with having lots of items by chaining the items and using dot equals to find what we are looking for so cycling back to what I just said about like using the modulus so。

In a perfect world we could have like 4 billion buckets。

 but that's not really feasible on someone's computer right so we would have a much smaller number of buckets and this means that because there's a much smaller mapping of numbers to which the modulus can give us a result in right it's some number between zero and the number of buckets not including the number of buckets right。

😡，Because like the modo limits the space or like the range of numbers that are like target bucket can take on we're inevitably going to have like collisions right we're going to inevitably have elements mapped to the same bucket and so we deal with this with something that we call external chaining and typically we deal we implement external chaining by having like an underlying array and then the indices of the array represent like the bucket that we hash to and then in each position in the array。

 we have some kind of data structure like maybe like a linked list or like a hasht or something something that is just like a collection of elements basically so in a hash mapap specifically we're specifically concerned so specifically we're specifically concerned with the equality of keys and key value pairs versus in a hash that we only have a value to compared to right？

So as an example， if this was our hashm and then each of these things in the brackets is like mapping a key to a value so the key would be Astro and the value would be jetty in this case。

 let's say I wanted to look up I wanted to look up the value associated with the key tofu so basically what I would do here is I would hash the key tofu and we run some kind of like hash code on tofu and we mod it by the number of buckets we have so we have four buckets here and presumably after I I call my hash code on tofu and then I mo it by four it's going to tell me that we want to look in bucket number two for the value that tofu is associated with okay so I'm going to come down to bucket2 and I'm going see that we have this external chain right it's just like a list or it's a hashs some kind of data structure that stores a collection of our key value pairs。

😊，So basically what I'm going to do is i'm going to iterate through these key value pairs until I find the key that I want right so i'm going to come up here to this very first entry in bucket number two and say okay I'm looking for key tofu this entry has key opal that doesn't seem right to me I don't think these keys are equal so i'm going move on to the next element so when I come to the next element I'm once again i'm going to say I'm looking for key tofu what's the key of this key value entry and i'll see that oh I did actually find tofu this is great so once I found tofu I check the equality of the keys I'm going to return the value associated with that key which is Alexander so that's basically a very quick way that we can look up。

We can like look up and have operations in our hash maps and hashts with hashing right so。

Something that that's really important to note therefore and you'll notice that I talked about like the equality of keys right it's really important that your equals function matches the result of comparing hash codes。

 So if two items are equal they must also have the same hash code so basically if you override the hash code for。

😊，If you override the hash code for some object you define。

 you should probably also override the equals method or else bad things may happen and vice versa。

 if you override the equals method， you probably also want to override the hash code method otherwise like you might not be able to find。

The objects that you necessarily want， okay？No。Let's talk a little bit about what happens when our buckets get too big or the the chains in our buckets get too big。

 so the idea behind hashing is that even though we say that hash maps and hashts they have like approximately constant time operations for like get put remove etc ce。

 it's constant with respect to like。Repeated calls to these operations in the sense of like。

In the example back here in our hash map， we saw that in bucket zero。

 there were three elements in bucket one， there was one element or in in bucket zero。

 there were three entries in bucket one there was one entry in bucket two。

 there were two entries in bucket three there was one entry and the idea is that we want to keep these。

😊，The chains in each bucket approximately equal in length because that allows us to have like constant lookup times with respect to repeated operations to this like hash mapap right because let's say we hash something to bucket zero like if we're trying to find a key it's going to take approximately the same amount of time that it's going to take us to look in like bucket to if the elements are like nicely and evenly distributed right however if we get to a point where our chains are too long we need to resize right and so the load factor tells us when we should resize we calculate load factor by dividing the total number of elements or entries in our hash or hashmap。

Oh， this should not see added Oh no， this should say we divide the total number oh oh wait no actually it should say added my bad。

 I just midread this we should divide the total of number of elements added to our hashmap or hashet by the number of buckets that we currently have。

So when we resize up if the load factor exceed some threshold。

 we increase the number of buckets that we use in the data structure so for example going back over here we currently have four buckets right and let's say that if we exceed a load factor of 75% that means we should resize up so in this case this was not like。

😊，The greatest examples to go off of I'm realizing now but let's say like this was an empty hashmap and then we put in three elements and if we tried to add a fourth element we would resize basically that's what it means like when our load when we exceed our load factor because there would be four elements in our hashm of four buckets right so the number of elements divided by the number of buckets would have exceeded our load factor and we would have one and size。

😊，So basically resizing helps us keep our runtimes relatively constant assuming that we have like a good hash code。

 which we will talk about in like an itty bit， but something that you need to consider when we resize is because all elements initially placed into buckets werere initially placed into buckets based on how many buckets we' previously available right like we hash a key and then we take the modo of that hash according to the number of buckets that are currently available to us in our underlying data structure。

 we also need to rehash all elements into a potentially new destination bucket when we resize。

 otherwise subsequent calls to get may fail。So what I mean by that is that let's say like let's hypothetical scenario back here。

 let's say we decide to resize our hashmap over here and we resize this to be an underlying array of length eight。

 but we don't actually like move we don't actually move。😊。

The the entries over in our hashrap aka we like literally just like made a carbon copy of what was in index zero and x12 and3 and we copied it over to our new length data rate so let's say one more time。

That I'm trying to find tofu I'm trying to find the value associated with tofu in my hashmap so what I'm going to do when I'm trying to get tofu is I'm going to hash tofu right because tofu is my key and then I'm going to mod it by the number of buckets that I currently have。

But now because we have a length8 array， I have eight buckets。

 that value that tofu got hash to mod8 is not necessarily the same as the value as tofu hashed mod4。

 which is what we were previously doing right So basically if we do tofu mod8 we're not tofu the hash code of tofu mod 8。

 when we do a lookup into the particular index， we're not guaranteed that it's in the same bucket that we were originally looking for right。

 which is why we need to rehash all elements in our hashmap or hashet when we resize to guarantee that get and put。

And remove actually run accurately okay a quick caveat though is that resizing because we need to rehash every single element when we resize up it sounds a lot like a linear time operation with respect to the number of elements that are in our hashmap or hashet right and when we think about how that runtime affects the runtime of our operations。

😊，Like what did that make our operations linear in some cases well that's why we talk about hashmap and hashet rent times in amortized cases right so basically the idea is that like 99% of the time when we are doing operations that involve hashing like a we like get from a hashmap or we put into a hashet。

😊，Those operations take constant time on average and occasionally when we add something to our hashmap we're going to exceed our load factors so we're going to have to resize and that involves rehashing all of our elements right but if you take that into the larger context of how like 9090% of the time it's a constant time look up and the other 1% it's linear then it kind of like averages or amortizes out so that we get constant time operations which are with our hash maps and hashets okay。

😊，So。I briefly talked about like a good hash code distributing elements evenly。

 but let's we need to back up things a little bit。First。

 we need to talk a little bit about the properties of a valid hash code in the first place。

A properties of the valid has code there is only three。 The first one is that it must be an integer。

 right， we need to hash some object to some integer。Secondly。

 the hash code for the same object should always be the same AKA should be deterministic。

 so as an example， let's say I have a dog Fido， no matter how many times I hash that same phyto dog object。

 it should give me the same hash code。😊，And lastly， if two objects are equal。

 they have the same hash code， so we talked briefly about this right the motivation behind this in a couple of slide ago。

 but just to like recap it's really important that if two objects are equal they have the same hash code because like let's say you're doing a lookup in a a hashmap right and we know that when we are doing a lookup and a hash mapap we're hashing the key and then within the bucket that the index we within the bucket that we hash to we are going to look through that external chain for an equal key so we can find the value associated with that key right so if two objects were equal and they didn't have the same hash code that would be really bad for us because we might have like two objects hash them separately。

😊，And they get hashed to different buckets and so when we're trying to look up an object in our hashrap。

 we might not even be able to find it even though the two objects are equal so。😊。

As a quick thought exercise， what about the rivers。

 Is it important that two objects that have the same hash code are equal？

I'll let you much on that for like five seconds， you can pause if you'd like to think about it on your own。

 but now let's come back and think about is it important that two objects that have this is it important for two objects that have the same hashag to be equal？

Well， that's not necessarily true at all so coming back to the example over here we'll see that Astro and as an example right Astro and R2 these two keys got hash to the same bucket right there was a collision they're both in bucket zero。

 but they're not the same they're not equal at all right Astro is definitely not r2 so it doesn't really matter if two objects have the same hash code they don't need to be equal。

😊，so those are the properties of a valid hash code but what are the properties of a good hash code there's really only one that's important and it's that it distributes elements evenly and like what does that even mean right okay well actually a good hash code first of all needs to also be valid but there's like a distinction here because just because you have a valid hash code it doesn't necessarily mean that your hash code is going to distribute elements evenly so as an example let's pretend like。

😊，We have a hash code implementation that always returns zero。Okay。

 so let's go through and see is it a valid hash code first of all。

 it must be an integer zero is an integer cool， we tick off checkpoint one。😊，Check point2。

 the hash code for the same object should always be the same。 Well。

 trivially it's true because like no matter what we hash to， it always returns zero。

 So check we have number two。 What about number three， if two objects are equal。

 they have the same hash code Well， it doesn't really matter for us here because all objects that we hash with this hash function are going to return zero。

 So equal or not， they're gonna have the same hash code， it's all gonna be zero。

 So we check off point number three。😊，Returning zero is a perfectly valid hash code。

 but it's like a horrible hash code right because it does not distribute elements evenly at all。

 it is always going to hash us into bucket zero， which makes our which makes our chain super。

 super unbalanced right so we're going to explore this a little bit more。

And I think yeah question two and question three of this worksheet。

 but it's really important to have a good hash code to keep hash maps and hashets and any data structure that involves hashing it's really important to have a good hash code so that we keep their runtime relatively fast and constant okay and I think that's it for content yeah。

😊。

![](img/0c180cf7bb30c63d5483ad9fc1ee2d5d_3.png)