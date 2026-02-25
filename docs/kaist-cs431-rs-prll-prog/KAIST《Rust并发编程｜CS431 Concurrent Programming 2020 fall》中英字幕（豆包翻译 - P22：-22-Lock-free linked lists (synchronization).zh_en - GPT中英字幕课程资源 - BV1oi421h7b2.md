# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P22：-22-Lock-free linked lists (synchronization).zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

![](img/da8eee4551f15da1a3bc09e75d5c6a09_0.png)

So in this code， we are going to see how the axis to the shared memory locations are annotated with which orderings。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_2.png)

In order to do so， we search for altering here。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_4.png)

Okay， so far as so good。And for the drop， we don't need to annotate anything with re wire or release。

 The reason is that。At the point that at the time that a data structure is dropped。

 then we completely own。We fully own the linked list。

 so we don't need to synchronize with each other。 I mean。

 we don't need to synchronize with other threads。 but that's the reason why we can just use relax here。

 There's no release or acquire in order to synchronize with the other threads。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_6.png)

And now the next thing to do is the。The Harris is find。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_8.png)

Okay， now let's understand why the next pointer reading the next pointer of the current node must be acquired。

So recall that the cursor is consisting of two pointers， the previous node and the current node。

 pointing to previous and the current node。And in the next itation。

 we are going to move the window of this and the current node is becoming the new previous the the new previous node and the new next in the next node is becoming the new current node。

The reason why this must be is that。In the， in the next tieration the， the， the。

 the this next is becoming the， the next iterations current pointer。

And this current pointer is the referenced here， it is referenced here。

 and each value is actually red here。So that's basically what's going on in this implementation。

Next pointer is read and it is becoming the next corner node。

 and it is in the next iteration dered here。That's the reason why it must be acquired。

 so in order to see the latest value of the key， for example。

 or at the later stage of this algorithm， key and value。We need to。 We need to make it an acquire。

In order to acknowledge the latest information on these key and the next values。

So that's the reason why this is a acquired。 The reason is， in a sense， to exploit the invariant。

By acknowledging the latest information。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_10.png)

So the same thing happens for this as well， it is it trading。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_12.png)

In the fine Harris Michael strategy， almost the same thing happen。

 we need to read the next pointer and it must be de referenced at the nextite duration。😊。

That's the reason why it must acquire。This is the same as well。

 this must be a cho for the same reason that we iterate through this linked list and to see in order to see the latest information on this next pointer in the next iteration。

 it must be a。The same reason， for the same reason， it must be acquired too。So far。

 I explained why some of the orderingance must be acquired that is in order to establish the invariant in the erect operations。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_14.png)

On the other hand。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_16.png)

We are also writing something with release。Why。The reason is that we are overriding the pointer value to this previous note。

This is basically the previous nose next pointer。And we are overriding some value to this pointer。

And the overr value is the current pointer。And we have to guarantee。

 we have to establish the environmentvari that all the pointers， the new pointers of the Seelta pref。

 which is pointing to Seta current。😊，We need to make a guarantee that the release view of this right is greater than equal to the information。

 the latest information on the self。 curve。😊，And the latest information is already acquired here。

In this loop， we used acquire acquire read and as a result。

 at this point of time in this this thread has already acquired the latest information on the self dot current pointer。

And as a result， you can just do a release here。By doing so， we are releasing the information。

 the latest information on this current pointer to the message of this self that pref。😊。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_18.png)

So in other words， it is effectively establishing the reestablishing the invariant that this pointer。

 its release view is greater than or equal to the latest information on this current node。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_20.png)

![](img/da8eee4551f15da1a3bc09e75d5c6a09_21.png)

The almost same thing happens in this release as well。

 So you can see that the code is almost the same。 and that's the reason why it must be released。😊。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_23.png)

And also， yeah， that is the reason。We don't do a release right here because in fine Harry Hols。

 I mean。In the Holily Shabbish strategy， we are not going to fix the list by updating the linked list。

So we are not overriding the point of value in this strategy。

 so that's the reason why there is no release rights。

And that's basically particularly the reason why it is weight free。 it， even though it。

 it doesn't have a comparison swap。 So it will always succeed in it trading through the linked list。

 And that's the reason why it is not the。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_25.png)

It is faster than other traveral algorithms。It the that maybe the other threats may suffer or more performance problems。

Okay， stop right second good。And you may wonder why this be relaxed。

The reason why this is relax is that。In the。In this implementation。

 we are only reading the point of value。Actually， we are only reading the pointer tag of this next pointer。

😊，We are not referencing the next pointer。That's the reason why it doesn't need to be acquired。

 we are not accessing the next pointer's key value next pointer。

 so we don't need to acknowledge the latest information on the next node。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_27.png)

![](img/da8eee4551f15da1a3bc09e75d5c6a09_28.png)

We just want to know the pointer value。Especially the tag value。

 That's the reason why it can be just relaxed。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_30.png)

So， for a second。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_32.png)

And， yeah。Here it can be relaxed because we are accessing the fully owned node。 It。

 It is not shared with the other threads。 So we are not synchronizing anything。😊。

We are just writing some value here。 So that's the reason why it can be relaxed。

It must be released for the same reason then。The previous comparison route must be released。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_34.png)

And on and on and on。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_36.png)

So。I I guess that you may be able to reason why this should be it can be relaxed rather than released。

 for example， and please hit home， please analyze why all the order rings are are safe and enough basically。

Okay， so first second go。And as I just said， please list up all the ordering， acquire。

 release and relaxed， and for a release， please understand why they must be acquire or release。

All orderings have a reason。 The reason is to establish the environmentvariant。

So with respect to the invariant， please justify why they must be or acquire or released。

 why they should not be just relaxed， please understand that at home。

And if you understand some of those drawings are why such defined， please ask a question。

As preciselyly as possible。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_38.png)

And further， for this relaxed ordering， please understand why these kinds of orderings can be relaxed。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_40.png)

What I， I already explained that some of them are relaxed。

 they can be relaxed because of some reasons。 So please understand them for all the all the relaxed order drinks that is presented in the in this code。

😊。

![](img/da8eee4551f15da1a3bc09e75d5c6a09_42.png)

![](img/da8eee4551f15da1a3bc09e75d5c6a09_43.png)

So that's basically the， the， the explanation of the order rings inside this code。



![](img/da8eee4551f15da1a3bc09e75d5c6a09_45.png)

![](img/da8eee4551f15da1a3bc09e75d5c6a09_46.png)