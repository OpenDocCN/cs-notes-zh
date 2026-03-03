# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p40 19_06_02_向链表树映射中插入数据.zh_en -BV1v2421P7pt_p40-

![](img/f75089e0e62249d89e111e6af2a5fa6a_0.png)

So this is an entire lecture on the put method of our tree map。

And the essence of this is we're going to be simultaneously updating two data structures at the same time。

 I guess that's a definition of simultaneously。So just before we start。This is not easy。

I think it's pretty much impossible to do exactly what I'm asking you to do。

 just use a bunch of Google searches or asking your AI bot， maybe， maybe you can。

You need to really understand what you're doing。 And this is where a picture is so valuable。

 Once you understand it， the code should look very clean and very simple to you。

My put code as I was writing it。Was like broken。And like I tried to fix it。

And then it was broken again。Then I threw it away， and I wrote it again， and I drew a new picture。

And I wrote it， and it was broken， and I threw it away again。And then， like。Poof， it was perfect。So。

As you're writing data structure code， the notion of like it's broken， just accept that it's broken。

It's going to be broken。You're going to throw it away。That's the point。

Because you know that this algorithm is eventually going to work， the algorithm is not the problem。

 it's your implementation， that's the problem。Okay。

So if we take a quick look at the performance of foot and I've mentioned this。

 the binary search is log n， while asorted list search is order n， meaning that。

If you have a search list of 500，000 or a million， it takes， on average， 500，000 lookups to find it。

 whereas a million entry tree search， it take the log two of a million and get about 20。

And so the key thing is we're going to use the tree anytime we're searching。

And we're going to only use the list when we're iterating， but we're going to while we're doing put。

 we've got to maintain both the tree and the list。ok。😊，So。

We are going to have to be real careful to keep in our mind。

 and this is where I drew all those pictures。We've got to be able to insert into an empty list which is easy because root is null and you just put the thing in。

 then you've got to find a right gap， a gap to the right is something， and then find a left gap。

And then insert at the beginning， after you go down a bunch of lefts and go down a bunch of right。

 and then replacing is the easy part。 As we've seen and put， you just that you if it's equal。

 change the value。

![](img/f75089e0e62249d89e111e6af2a5fa6a_2.png)

Okay。So let's just take a look at our data structures and then we talked about these before we have simultaneously in the entry。

 we have a left and a right and we have a next because we are simultaneously maintaining。

A sortrded linked list。And a sordid tree。The tree map has a head and it has a root。

 and that's pretty much it so in our constructor we set the head to know。

 we set the root to know we' are empty， we don't have anything in the tree。

 we don't have anything in the linked list， so the empty list is easy。Right。

And so we have to scan to see if it's in the list， right？And， you know if。You know。First。

 we can just say， hey， if self head is nu and be the same as saying if self root is nu， well。

 we just point head and root。To the另外。Okay， because we're inserting h equals 22。

I'm going to insert these in order so the list so I don't run out of space on my PowerPoint slides。



![](img/f75089e0e62249d89e111e6af2a5fa6a_4.png)

And so。When we're done with this， root is going to point h equals 22。

 the left is going to point to null， the right is going to point to null。

 The next is going to point to null and head。Is going to point to the item。 So we have a valid。

Liked list。And we have a valid tree at the same time。



![](img/f75089e0e62249d89e111e6af2a5fa6a_6.png)

Okay， so again。This is not the whole put code， this is just the first part where we。

There's some dot dot dots in there where you're putting all the data in。

 putting the key in and setting next to null and left and allll， etc ce， so that's in there。

But the first one is pretty easy from the head and the root， okay？So we keep doing that for a while。

 let's just take we put some things in there and we've got our link list going correctly。

 you can just verify that， you run through， they're all in order。

 you can take your lefts and your rights and all the things that are less than H or to the left of H and all the things that are the right of H。

Greater than H。A way we go。So we're going to write some code and what we're really going to look for。

 and this is the tricky part。Is to find the item or the gap where the item belongs。

Now the problem is is we're going to have to link these things back up when we are just doing a tree。



![](img/f75089e0e62249d89e111e6af2a5fa6a_8.png)

It was easier。Because you would either find the item or find the place to link it。Okay。

So trees are easier。To easy to maintain the linked list is harder to maintain because you've got to keep track。

Of the。Item that is the largest item less。And the smallest item greater and that's what I call the gap so this left in this right are to as we're walking down the list。

 we're going to keep track of the greatest the smallest greater item and the largest less item okay and that's what this left so we got cur。

 we got left and we've got right。And you can think of。

Left and right as like bread crumbs like we're going。Throw breadcrumbs when we turn。

 when we're going to turn to the left， we're going to remember the right， when we turn to the right。

 we're going to remember the left and you'll see it in action， so here we go。



![](img/f75089e0e62249d89e111e6af2a5fa6a_10.png)

Here we go。So we got this tree。G equals 29， we're going to insert it。

So then what we do is we compare it to H equals 42。And then we say， oh。That's a turn to the left。

So now we know， at least at this point， the greatest value。The smallest greatest value is H。

 and so we point right at H as we are moving down the tree。And you see that you do the stir comp。

 you see what it says， if comp is less than0， we're going to turn left and then right is going to point at cur where we were。

And now the next time when we're going to turn right， which is what we're going to do next。

 it's going to remember where're left so we're now comparing G to D and G is greater than D。

So now we're going to turn right。

![](img/f75089e0e62249d89e111e6af2a5fa6a_12.png)

But now we're going to update left， so D at this point in our search D。

Is the largest number less than are the largest key less than G And H is the smallest key greater than G。

 So you see how left and right are like bread crumbs as we're sort of to chining our way down this tree。



![](img/f75089e0e62249d89e111e6af2a5fa6a_14.png)

So then we compare G to F。And G is greater than F， and so we're going to take a right turn。

 and whenever we take a right turn， we update left。



![](img/f75089e0e62249d89e111e6af2a5fa6a_16.png)

So now we have actually found the place that G belongs and if you look。

 left and right are perfect for the linked list。

![](img/f75089e0e62249d89e111e6af2a5fa6a_18.png)

Because now we know that left next is going to point to G。And G next is going to point to H。

So so left next。Won't point at H anymore， it's going to point at G and。

Gene new next is going to point at H okay so when we do this because we've got left and we've got right。

 we just link them in and then we insert it into the tree in away we go and so now you look what we have done is we have now left and right we're just temporary variables that we had during this tree map put code。



![](img/f75089e0e62249d89e111e6af2a5fa6a_20.png)

But if you look at this and look at carefully， we have a。

Correctly formed linked list that's sorted in order， and we have a correctly formed tree。

And we use the tree to get to F fast， and we used left and right so that once we got to the right place。

 which was to the right of F， we could just hook it into that linked list with no additional cost。

Okay， see how pretty it is， so now let's take a look at some other of these things。

 so let's take a look at inserting J。

![](img/f75089e0e62249d89e111e6af2a5fa6a_22.png)

Well。Jake is going to go right when it sees H because it's greater than it's going to go left when it sees K because it's less than。

I mean， I am， I'm inserting I not J。It's going to go left when it sees K and it's going to go left when it sees J。

 and when it's done you've got left is H and right， the right value in the the。



![](img/f75089e0e62249d89e111e6af2a5fa6a_24.png)

I shouldn't even these's left， I should call them be。Smallest， wait a sec。

 the largest value less than and the smallest value greater than that would probably be a more mnemonic name is largest value less than and smallest value greater than instead of left and right。

 I'm thinking of it as the thing It's like a bracket。 You got a gap。 And what's your immediate left。

 And what's your immediate right。

![](img/f75089e0e62249d89e111e6af2a5fa6a_26.png)

And so now we know exactly where this belongs and we know how to update both the link list and the tree。

 so wink， update the link list using left and right， and then update the tree using cur。

RightAnd so away we go and we've got ourselves in that gap。 and so we can insert to the left。

 we can insert to the right Now， remember， remember， remember。



![](img/f75089e0e62249d89e111e6af2a5fa6a_28.png)

![](img/f75089e0e62249d89e111e6af2a5fa6a_29.png)

That if we， if our key was J， we'd have found it。 And then all wed done is updated the value。

 So remember， I I， and my brain does this a lot when I'm looking at this code， I'm like。

But will I find it and will I find the right one， What if it's already there， Well。

 already there's the easy part。Okay， so there we go。

So let's take a look at inserting a equals 17 and how this works， remember the use cases。

 I've got to do the beginning， the end left gap， right gap。Empty list。

 and then pretty much we'll have it so a equals 17， that's going to end up all the way down。

So we are going to compare it and we're going to turn left to the left to the left。

I think there's a song and a dance about that。And so we remain remember right。

 which is the smallest number greater than and it's not going to be right。

 it's not going to stage equals 42 because we're going to compare A and D。

And then we're going to go left again。And now rightright is going to follow us。

 and then we're going to compare A and B。And we're going to go left again and right is going to follow us。

 Now the interesting thing is left is now null。

![](img/f75089e0e62249d89e111e6af2a5fa6a_31.png)

We have found the place we are going to insert to the left of B。

But we're also going to insert through the head because we know that left is null。

 which means that we just found the lowest thing in the current something lower than anything in the linked list。



![](img/f75089e0e62249d89e111e6af2a5fa6a_33.png)

So then we just hook A in before B。Right after head。

And then we hook it in to the left of the B going with a larger than anything else that's in there。

 we're going to end up with this at the end of the link list。

We're going to compare x to H and going to go right。And remember left。

The largest value less than for now， we're going to look at k。

 we're going to go left again and left is going to be updated to be K。

 the largest value less than then we're going to compare x to M and x is still greater than M。

So we're going to go right again and left is going to be m equals 67。

 and you'll note that the thing we detect here is right equals0。



![](img/f75089e0e62249d89e111e6af2a5fa6a_35.png)

Which means。We have no value greater than X in this list。



![](img/f75089e0e62249d89e111e6af2a5fa6a_37.png)

So we just say x next， x the current thing of next is null。And the cur next is you know。

Points to the x entry， and then we hook it in on the right side of the M equals 67。

 and then we are done。

![](img/f75089e0e62249d89e111e6af2a5fa6a_39.png)

So if we're going to do a replacement， remember， I told you this was the easy one。So and again。

 in by Brian， when I was writing this code， I'm like。But what if it's already there， calm down。

 that's the easy one， okay？

![](img/f75089e0e62249d89e111e6af2a5fa6a_41.png)

So we're comparing F to H while it's to the left。We're going to keep track of right。

 but we're not going to use them because we're going to find it and then we have a match and then we just see it and you go like。

 oh， fine。F is 16。 we're done。 Life is simple。 if they're equal， we found it。

 you know we don't have to keep looking， we found it， we just change it and again。

 think of how fast Now how fast this works when it's the key's already there。

 It's like nothing to allocate no links to make you just change the value。



![](img/f75089e0e62249d89e111e6af2a5fa6a_43.png)

And you're done。哇。So it's important。To test all of these cases。

 and I just went through every single one of the cases。And。

Showed you what they're supposed to look like。 And I will tell you that you will make mistakes。



![](img/f75089e0e62249d89e111e6af2a5fa6a_45.png)

I will tell you that asking Google for help， as long as you read what they say will inform you。

 that I doubt that Google is going to just give you the whole code of something that is as intricate as this。

I would say a simultaneous sorted linked list to in a tree at the same time。

 maybe it can do that because that's what you're really doing。So what next？

We're going to go back to the beginning and go back to Python for everybody to wrap things up。



![](img/f75089e0e62249d89e111e6af2a5fa6a_47.png)

🎼Yeah。

![](img/f75089e0e62249d89e111e6af2a5fa6a_49.png)

🎼。

![](img/f75089e0e62249d89e111e6af2a5fa6a_51.png)