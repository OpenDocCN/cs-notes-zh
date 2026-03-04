# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P146：-146-Balanced Trees Chap8 Video 30.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

The best case would be trees that look like this one。

 This is a perfect binary tree in which all of the paths have the same length。

That's logarithmic in the number of nodes in the tree。

And even if we couldn't get the tree to be perfect。

 we want to shape approximating this perfect binary tree。 Well。

 here are some strategies for achieving balance。

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_1.png)

In general， what we're going to do is strengthen the weapon variant to require balance。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_3.png)

And modify insert to make sure that weaponend variant holds so that we get the balance。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_5.png)

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_6.png)

There are a few well known data structures for balanced binary search trees。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_8.png)

One of them is the two，3 tree。

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_10.png)

This was actually invented by our own professors， John Hopcroft。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_12.png)

In a 2，3 tree， all paths have the same length。

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_14.png)

That's guaranteed by storing either two subtes at each node or three subtes at each node。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_16.png)

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_17.png)

So that complicates the representation type a little bit， as well as the algorithms。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_19.png)

A little bit more relaxed of a rein variant than that is maintained by an A V L tree In an A V L tree。

 The rein variant says that the length of the shortest and longest path from any node differ by at most one。

😊。

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_21.png)

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_22.png)

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_23.png)

So unlike two， three trees， it doesn't have to be exactly the same。

 there's a little bit of discrepancy allowed， but not much。 they differ by it most one。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_25.png)

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_26.png)

Actually， the OcaMel standard library in its tree implementations。

 uses a variant of AVL trees in which the length of the shortsest and longest paths is allowed to vary by at most two。

 so that's even more relaxed of a weapon。

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_28.png)

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_29.png)

Finally， a red black tree has an even more relaxed rein variant。

 which says that the length of the shortest and longest path from any node differ by at most a factor of two。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_31.png)

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_32.png)

So the longest path could be twice as long as the length of the shortest path in the tree。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_34.png)

But it turns out that's good enough to achieve balance and to give us logarithmic time operations。



![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_36.png)

![](img/b04bf6efcfa2f7a91c305d2a2ae806b3_37.png)