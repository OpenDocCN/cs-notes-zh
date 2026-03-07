# 【精译⚡算法与数据结构】PavelMavrin p05 p4 A&DS S01E05. Binary Search -BV1NLB8YfEMq_p5-

。🎼嘟推痛头。🎼。🎼The。So today we'll start a new topic today we'll talk about binary research。



![](img/641da2c2a30cde79e2af58f13d637ad4_1.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_2.png)

So what is the binary， binary research is a basic technique you used to find something in the list of things。

啊。The first problem we solve is the following。 So it is one of the most common problem ones you use by research。

 You have a sort array。

![](img/641da2c2a30cde79e2af58f13d637ad4_4.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_5.png)

Let's have sort of3 a。Of some， let's say integers。 Let's say the red。25。



![](img/641da2c2a30cde79e2af58f13d637ad4_7.png)

WWho seeks it then。Well。In and 21。

![](img/641da2c2a30cde79e2af58f13d637ad4_9.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_10.png)

なことな。

![](img/641da2c2a30cde79e2af58f13d637ad4_12.png)

And we need to find some number in this array So the array is sort。



![](img/641da2c2a30cde79e2af58f13d637ad4_14.png)

And we need to find some number x， let's say x。

![](img/641da2c2a30cde79e2af58f13d637ad4_16.png)

Equal to， let's say。

![](img/641da2c2a30cde79e2af58f13d637ad4_18.png)

佢用 a件。

![](img/641da2c2a30cde79e2af58f13d637ad4_20.png)

And our task is to find the element of a array equal to x。



![](img/641da2c2a30cde79e2af58f13d637ad4_22.png)

五。

![](img/641da2c2a30cde79e2af58f13d637ad4_24.png)

So how can I solve this problem？No， that， the idea is。あ。To maintain a segment of the array。

Where may be the element X？

![](img/641da2c2a30cde79e2af58f13d637ad4_26.png)

So we will have two pointers。First point lesson。

![](img/641da2c2a30cde79e2af58f13d637ad4_28.png)

Second point， let's say here。

![](img/641da2c2a30cde79e2af58f13d637ad4_30.png)

And we will maintain the following property， we will maintain property that the element x is always between L and R。



![](img/641da2c2a30cde79e2af58f13d637ad4_32.png)

So X is always。

![](img/641da2c2a30cde79e2af58f13d637ad4_34.png)

In a segment from L to R。

![](img/641da2c2a30cde79e2af58f13d637ad4_36.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_37.png)

Now， what can we do， We will decrease the size of the segment。そ、そう。

Let's say we pick the element in the middle of the silence。



![](img/641da2c2a30cde79e2af58f13d637ad4_39.png)

B element。

![](img/641da2c2a30cde79e2af58f13d637ad4_41.png)

没有。Right in the middle of the segment， so if the segment this odd length。

 we just pick the middle element if it is even length we pick any of the middle elements。



![](img/641da2c2a30cde79e2af58f13d637ad4_43.png)

So let's say m equal to。

![](img/641da2c2a30cde79e2af58f13d637ad4_45.png)

L plus R divided by 2。

![](img/641da2c2a30cde79e2af58f13d637ad4_47.png)

Now we take a look on these elements。

![](img/641da2c2a30cde79e2af58f13d637ad4_49.png)

There are three possible cases。If this element， like in our case， this element is less than x。

So it felt this。 Let's say if。

![](img/641da2c2a30cde79e2af58f13d637ad4_51.png)

Element is less than x。

![](img/641da2c2a30cde79e2af58f13d637ad4_53.png)

If the element is less than x。

![](img/641da2c2a30cde79e2af58f13d637ad4_55.png)

Then since they're array sorted， so all elements to the left are also equal or less than x。

 all elements here are also less than x。

![](img/641da2c2a30cde79e2af58f13d637ad4_57.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_58.png)

So if we want to find element equal to x。

![](img/641da2c2a30cde79e2af58f13d637ad4_60.png)

We only should consider the element to the right hand disposition。

 So only element we need to search here is this segment。If there is an element x in this array。

 it must be in this section of the theory。

![](img/641da2c2a30cde79e2af58f13d637ad4_62.png)

So， we just put。He to position M plus one。い。You at this list than picks。



![](img/641da2c2a30cde79e2af58f13d637ad4_64.png)

elselse。

![](img/641da2c2a30cde79e2af58f13d637ad4_66.png)

If it is great doesn X。If it is greater than x， then again， we have element greater than x。



![](img/641da2c2a30cde79e2af58f13d637ad4_68.png)

Then all elements to the right are also greater than index。Because the area is sorted。

So we only need to find the element in the segment。 so this is L， this is oh， this is M。

 So we only need to find the element in the segment from L to M minus-1。



![](img/641da2c2a30cde79e2af58f13d637ad4_70.png)

So we just assign R R M -1。And if it is not less and not greater then it is equal to x。

 If it is equal to x， we just return。Po and。

![](img/641da2c2a30cde79e2af58f13d637ad4_72.png)

オッケ。That's how we shrink think the size of the rate Now let's add the first in inization so。



![](img/641da2c2a30cde79e2af58f13d637ad4_74.png)

In the beginning， we need to assign L that's say equal to 0 R equal to N， N， N， and N。And -1。And。

We do these separations while the size of the。Of the area we're looking in is greater than 0。

 So the size of this segment is L R minus L plus 1。

And while this size of this segment is greater or equal than one。



![](img/641da2c2a30cde79e2af58f13d637ad4_76.png)

We make depers。

![](img/641da2c2a30cde79e2af58f13d637ad4_78.png)

Okay。So that's our first binary search。 What will be the time complexity of this binary research？



![](img/641da2c2a30cde79e2af58f13d637ad4_80.png)

Let's see each time we go from segment of size n to the segment of size n divide by2。

 so each time we decrease the size of the segment at least twice。



![](img/641da2c2a30cde79e2af58f13d637ad4_82.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_83.png)

そう。The totaltal number of such operations is at most logar if of M。

 So total number of these operations is no more than。 let's say we go of log n。



![](img/641da2c2a30cde79e2af58f13d637ad4_85.png)

ど see thisす。Yes。Let's use something heavier。嗯嗯。This one。Okay。



![](img/641da2c2a30cde79e2af58f13d637ad4_87.png)

Yeah， what's better。

![](img/641da2c2a30cde79e2af58f13d637ad4_89.png)

Okay。That从。你是 clear啊。やと quiteトでい。共。プイそう。

![](img/641da2c2a30cde79e2af58f13d637ad4_91.png)

啊嗯。So this is the first binary the research。It's quite simple。

 but if you want to solve some more complicated problem。

 it's not the best way to write binary the research。

 There is now another way to write by the research， which is more universal。

 more easy to implement and。There's too many small details in this code you like here you have m plus one here you have m minus-1。

 here you have something strange， you here have three branches and if there are many elements equal to x。

 then you will find some of these elements or if there are。Like in Android A。

 if there are a sequence of elements equal to x。You may pick any of them， so you just。

The first time you pick one of the element equal to x， you will immediately return this position。

It's like kind of strange algorithm。 if you， if there are several different possible elements。

So now we will learn more。More more clear way to implement a binary research and we will solve。

Even more complicated problems causing this binary research。Let's go。

Let's solve little bit more complicated problem。 And actually。

 this problem can be solved using hassh mops。If you， if you just want to find the elements。

By the value， you can just put all elements in the hash map then get from the hash mapap。

 the index of the element， you don't need any binary search， you can do it in constant time exchange。

We don't have maps。In this semester later， but not today。

 bio research can be used for much more complicated problems。For example， now， let's say。

Let's smoke the poll problem。Just。Make it little bit more。



![](img/641da2c2a30cde79e2af58f13d637ad4_93.png)

Complicated。So what if we want to find not element equal to x， but the closest to x。

 So if there is no element equal to x， we want to find something close。Let's say again。

 we have some element X。Equal to， let's say something like。Free。



![](img/641da2c2a30cde79e2af58f13d637ad4_95.png)

And we're looking for the element which is close to x element close to x maybe from two sides。

 you can find elements which is slightly bigger than x or slightly less than x。



![](img/641da2c2a30cde79e2af58f13d637ad4_97.png)

Let's say， for example， we want to find elements slightly bigger than x。 So we want to find element。

Which is greater or equal to x。

![](img/641da2c2a30cde79e2af58f13d637ad4_99.png)

And from all such element grid roofs， we want to find the closest one。

 so we will find the minimum of such elements。Soフミも。Again， what we're doing here。

 we try to find the leftmost element， which is greater or equal to x。



![](img/641da2c2a30cde79e2af58f13d637ad4_101.png)

Okay。然后我就。Just the rest everything here。

![](img/641da2c2a30cde79e2af58f13d637ad4_103.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_104.png)

You can easily actually， you can update this algorithm to solve this problem。

It's kind of complicated， but you can do it。 you can。

 you can adjust adjust all all things here to find the element， which is greater equal to X。

But it will be complicated， so you always need to keep in mind that you want to find the leftmost element greater than x。

And here you find it here you have some M plus minus M minus1。You you， you can update this little。

 but it's。

![](img/641da2c2a30cde79e2af58f13d637ad4_106.png)

To complicate you will make a bug。 What I suggest is to build another algorithm just from scratch。



![](img/641da2c2a30cde79e2af58f13d637ad4_108.png)

そう。Another approach to the binary research。Its poem。Okay， so what， what was I to do。

 We'll have again， We'll have two pointers。L and R， like。



![](img/641da2c2a30cde79e2af58f13d637ad4_110.png)

Like before。We have two point understand N now。

![](img/641da2c2a30cde79e2af58f13d637ad4_112.png)

And these two pointers will point to some elements of the array。



![](img/641da2c2a30cde79e2af58f13d637ad4_114.png)

And we will maintain a simple property。

![](img/641da2c2a30cde79e2af58f13d637ad4_116.png)

I will maintain the seatel property that。Element L will be less than x。



![](img/641da2c2a30cde79e2af58f13d637ad4_118.png)

And element R will be greater go to that。

![](img/641da2c2a30cde79e2af58f13d637ad4_120.png)

How can we build these properties， or just build them from the task， So in this task。

 we want to find element greater or equal to x。So if you want to element greater equal to x。

 So we put one pointers， one of the two pointers to the element。

 greater or equal to x and another pointer to element， which is not the greater or equal to x。

 So here we have element greater or equal to x here we have element less than x。



![](img/641da2c2a30cde79e2af58f13d637ad4_122.png)

That's all。

![](img/641da2c2a30cde79e2af58f13d637ad4_124.png)

Let's look， so what's happening in here we have some elements。



![](img/641da2c2a30cde79e2af58f13d637ad4_126.png)

嗯。I don't like one fruit。 let's say a。do呢 free我。そうああ。



![](img/641da2c2a30cde79e2af58f13d637ad4_128.png)

恶手。Where can we put the left pointer， So we can put left pointer somewhere here。 So here are element。

 lesson X。And where you can put the right point， you can put the right pointer somewhere here。

 So here I element greater or equal there。

![](img/641da2c2a30cde79e2af58f13d637ad4_130.png)

So the left pointer is always somewhere here， and the right pointer is always somewhere here。Now。

 how how will we find the element which is greater or equal to x and the leftmost such element。

 We will simply need to pick the leftmost element from all the positions where pointer R could be。

 So we will put pointer R in leftmost possible position。 So the left most possible position。



![](img/641da2c2a30cde79e2af58f13d637ad4_132.png)

Here's the element we're looking for。That's all， that， that's the whole plan。



![](img/641da2c2a30cde79e2af58f13d637ad4_134.png)

そう。So left pointer is always over here。 right pointer is always over here。

 Now we'll put this pointer closer to each other and the leftmost position of the pointer R will be the answer。

This point。あれねつこ。

![](img/641da2c2a30cde79e2af58f13d637ad4_136.png)

共。Now， at first， we need to initialize both pointers。

 so we need to put some initial value to pointer R and to pointer R。

And the initial thought may be to put left point of the position zero and right advisorvisor and minus-1 like like before。

But it actually may not work because if， for example， all elements are less than x。



![](img/641da2c2a30cde79e2af58f13d637ad4_138.png)

So if all elements are less than x， then you put pointer R to R and -1。



![](img/641da2c2a30cde79e2af58f13d637ad4_140.png)

And you break this， this property。 So if， if you put0 or R and position n -1， this property may。

 may be not satisfied。And in other case， if all elements are greater or equal to x。

Then if you put pointer L in position 0， then this property will be not satisfied。



![](img/641da2c2a30cde79e2af58f13d637ad4_142.png)

So you need to be careful in this in series。 So if you put left pointer and right pointer in some pointer wrong conditions of the array。

 you may break this properties and your algorithm rule of work。



![](img/641da2c2a30cde79e2af58f13d637ad4_144.png)

First， my because it how much do you。嗯。I'm not sure what was your problem， the objection。

 I'll write the good implementation of pione research， like in a minute。



![](img/641da2c2a30cde79e2af58f13d637ad4_146.png)

🤧嗯。So what， how， how can I fix this， We'll fix this very simple way。 We will add two more。



![](img/641da2c2a30cde79e2af58f13d637ad4_148.png)

Elements to the array。 So we'll add element plus infinity here and minus infinity here。



![](img/641da2c2a30cde79e2af58f13d637ad4_150.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_151.png)

Can you see them。No， you can。

![](img/641da2c2a30cde79e2af58f13d637ad4_153.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_154.png)

嗯，马几不的。Not much better。

![](img/641da2c2a30cde79e2af58f13d637ad4_156.png)

So add two more elements in the array。And we'll put。



![](img/641da2c2a30cde79e2af58f13d637ad4_158.png)

This pointers LLR to this virtual element。

![](img/641da2c2a30cde79e2af58f13d637ad4_160.png)

嗯。This is a typical small fix for problems like this。

 So it's quite common in problems in various problems when you need to find some element with good properties and you may not have any element of this good property。

 You just add the additional element of this property and put the pointer to this element。



![](img/641da2c2a30cde79e2af58f13d637ad4_162.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_163.png)

So this is happening sometimes in computer science really often。 In this case， what we can do if you。

 if you actually if you actually plan to implement this we can add this element just virtually。

 just don't put the physical elements in the array。

 but just imagine there are elements in these positions that will be enough。 But in some cases。

 you can actually put the actual element and put some very big number in this in the final element of the array or something like this。

 So in some cases， it's good to have this element。 But in this。

 in this algorithm who will not use this。

![](img/641da2c2a30cde79e2af58f13d637ad4_165.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_166.png)

Element， well just think of this element like it is here。Okay so。Now。

 what are the indices of this element。 So if the indices out of out of array are from 0 to n -1。



![](img/641da2c2a30cde79e2af58f13d637ad4_168.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_169.png)

Then index of this element is n。 and index of this element is minus-1。So， I will initialize L。

With -1 and R。

![](img/641da2c2a30cde79e2af58f13d637ad4_171.png)

That's all and now I'm making them by the research。Now we're making it again work a while。

Something I will write play that。We pick any element between L and R， so we pick m equal to L plus R。



![](img/641da2c2a30cde79e2af58f13d637ad4_173.png)

Divided by two。And now。Yeah， now we look on element position M。이 에어 만든 바지션 에요。

Is greater or equal to x。So then we can just。Pote the right point to this position。



![](img/641da2c2a30cde79e2af58f13d637ad4_175.png)

呃，一属。Have the elements。

![](img/641da2c2a30cde79e2af58f13d637ad4_177.png)

とと。とち？

![](img/641da2c2a30cde79e2af58f13d637ad4_179.png)

It would be placed element。So if this element is greater or equal to x。

We can just move this right pointer to position panel。



![](img/641da2c2a30cde79e2af58f13d637ad4_181.png)

And if we do this， then both this property will be satisfied because for the left point that it is still swipe。

 we didn't move it， and for the right point that we move it to position which has element greater or equal to x。

 so this property is satisfied。 This property is satisfied。Oh， there a lots of questions。嗯。



![](img/641da2c2a30cde79e2af58f13d637ad4_183.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_184.png)

Oh， here I again。

![](img/641da2c2a30cde79e2af58f13d637ad4_186.png)

And that's good dose system。If if you access the element and position -1。

 you will have some run time error or index out of bound exceptions like that。



![](img/641da2c2a30cde79e2af58f13d637ad4_188.png)

Let's let's need to。 you need to be careful here。 Yeah， that's， that's。



![](img/641da2c2a30cde79e2af58f13d637ad4_190.png)

And same thing here， if you try to access the element position N。

 you will have run runtime error or something like that。



![](img/641da2c2a30cde79e2af58f13d637ad4_192.png)

But the trick is we will never access these elements。そ。Let's see。 So here the element L。

Will be always greater than L greater。Greateater than L and less than R。



![](img/641da2c2a30cde79e2af58f13d637ad4_194.png)

So L we will only access the element in position M。

 we will never access element position L and R only in position M。

 and position M will be strictly greater than L and strictly less than R。

 so it will be strictly greater than minus-1 always and strictly less than n。

So we will never access these elements。Let不。It's just the small tricks。



![](img/641da2c2a30cde79e2af58f13d637ad4_196.png)

嗯。If you feel kind of not comfortable， you can always add real two elements，1。

 a really small element， one a really big element。 and you will be。Or always safe about this。そ。



![](img/641da2c2a30cde79e2af58f13d637ad4_198.png)

Okay， so if， again， we pick the middle element。If this middle element is greater or equal to x。

 we just move this right pointer to this position。E it is less。If it is less than x。

Then we'll move the left pointer because left point or points to element which is less than x。

 so put the left pointer。

![](img/641da2c2a30cde79e2af58f13d637ad4_200.png)

这从。And we do this until the pointer meets in the in in two neighboring positions。

 So we stop this while when we have two pointers in two neighboring elements of theory。

 So while R is greater than L plus 1。

![](img/641da2c2a30cde79e2af58f13d637ad4_202.png)

We do depers。Let错。So， in the end。When this process finishes， we have some。嗯，哼哼。Okay， let let's just。

Pite on this array。 So we put on R here here again， we pick the middle element。See。

 it is great as free， we again move to the right pointer here。

Here we have right here we pick the middle element， see is less than x。

So we put the left pointer here。

![](img/641da2c2a30cde79e2af58f13d637ad4_204.png)

So in the end we have pointers L and R in the two neighboring elements。



![](img/641da2c2a30cde79e2af58f13d637ad4_206.png)

So now we know that all this element is less than x， this is greater equal than x。

And now we just need to find the minimum element greater or equal to x。 So this minimal element。

 greater or equal to x is this element R， because this element is greater equal to x and previous element is less than x。

So we just the tongue。啊。好。That's all this hopeland。Now， what happens if。

There is no element we for by looking for some element greater or equal to x。

What happens if all elements of the rate are less than x。 for example。So， if x equal to。确题。

Then what will happen？ we will have again， we have left pointer here。



![](img/641da2c2a30cde79e2af58f13d637ad4_208.png)

Right point here。Now， each time we pick the middle element， we will pick element less than x。

So we'll go in this branch of the what if and we will move the left pointer。

We peak the middle element。Put the left pointer here。 Again， we pick the middle element。

 put the left pointer here。

![](img/641da2c2a30cde79e2af58f13d637ad4_210.png)

Repe the middle element， put less pointer here。인데요데요？Well have to point us。In this position。

 so the left pointer will be moved to position n -1， and Raport board will stay in position N。

Because each time we move the left corner， the right pointer will stay in position N。So。

 here we will return M。So here， let's see。If R equal to L。It means there is no element。If nor this。

Greatreeater or equal to x。So that's how you can simply check if there is no elements what you're looking for。

こol。こ？

![](img/641da2c2a30cde79e2af58f13d637ad4_212.png)

So next， next， next， next， next， next， next。Now let's try to change it here we're looking for element greater or equal to x in the same way we can look for element less or equal to k to x。

嗯，So we can look for element。Slightly less than x。And if you're looking for element less than x。

 it's logically to find the rightmost elements。 So you find the max I。

So well find the rightmost element， which is less or equal to x。Let's see。It know，15。



![](img/641da2c2a30cde79e2af58f13d637ad4_214.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_215.png)

What will be changed in our code， no。

![](img/641da2c2a30cde79e2af58f13d637ad4_217.png)

You can start from this two invaris， so we're looking for element less or equal to x。

 so we will move one pointer to element less or equal to x。You will say less or equal。

And another point of the element， which is not lessical X。 if it's no slightly slightly。

 it then is strictly greater。

![](img/641da2c2a30cde79e2af58f13d637ad4_219.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_220.png)

Now we move here。Try to use this invariance in this code。What will change the。

 you'll change all only this。 So here you have element。If element is strictly greater than x。

 you move the right pointer because right point of output points the element is strictly greater than x。

 If it is less or equal， we remove the left pointer。That's so。



![](img/641da2c2a30cde79e2af58f13d637ad4_222.png)

因被。In the end， you will have again， if you have to point those L and R L points to element less or equal X to x and write points to element greater L than x。

And you want to find element less or equal to x。 So you need the point or L。这标。That's all changes。おと。

No。Let's move to the next problems。In the next problems， we will。嗯。Well get to top right， basically。

So in the first problems， we have this array sorted。And all problems was around this rate。

Usual when you have wine research， you don't have this sorry， you have some small complicated。



![](img/641da2c2a30cde79e2af58f13d637ad4_224.png)

I like this。What's。そでね。

![](img/641da2c2a30cde79e2af58f13d637ad4_226.png)

错。So the most common problem for binary the discharge look like this。 you have all like。



![](img/641da2c2a30cde79e2af58f13d637ad4_228.png)

Interger numbers。

![](img/641da2c2a30cde79e2af58f13d637ad4_230.png)

。お。And。For some numbers， you， you say that this number is good for some numbers。 He。

 you say number is bad。 So， so all numbers are split into groups like good numbers。



![](img/641da2c2a30cde79e2af58f13d637ad4_232.png)

Or bad numbers。

![](img/641da2c2a30cde79e2af58f13d637ad4_234.png)

And。There is a monotonous privacy。 So if some number is good。

 then all greater greater numbers are also good。 So if x is good。



![](img/641da2c2a30cde79e2af58f13d637ad4_236.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_237.png)

And y is greater than x then。Why was it good。

![](img/641da2c2a30cde79e2af58f13d637ad4_239.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_240.png)

Yes， and the task usually is to find， let's say， the minimal good number。



![](img/641da2c2a30cde79e2af58f13d637ad4_242.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_243.png)

That's the most typical problem for binary research。So how。

 how this looks when you see look on on the nu number end。 Sos have all this。



![](img/641da2c2a30cde79e2af58f13d637ad4_245.png)

Numbers on the line。

![](img/641da2c2a30cde79e2af58f13d637ad4_247.png)

Some numbers are bad。 some numbers are good。 So we go from left to right。 So this number is bad。



![](img/641da2c2a30cde79e2af58f13d637ad4_249.png)

Let's say if somebodys bad。Then at some point we'll find some good number。



![](img/641da2c2a30cde79e2af58f13d637ad4_251.png)

And all numbers greater than this good number are also good because you have this property。

So here we have some good numbers。Here you have some bad numbers。Here have someゴざます。

And if you want to find the minimal good number， you need to find these positive。



![](img/641da2c2a30cde79e2af58f13d637ad4_253.png)

So this is the minimal possible good number you want to find。嗯。

So usually in the problem when you have something like that。嗯。Oh。Usually。

 it's tricky just to check if number is good or bad。 So usually in the problem， there's some strange。

Some stretch tape， and you want to minimize some volume。

And what you need to do when you want to apply by the research is to basically check if this value is good or if the value is bad。

If you're given the answer， is the sensor good or is the sensor bad？Do it in in just a moment。



![](img/641da2c2a30cde79e2af58f13d637ad4_255.png)

Let's， for example， have the following problem。

![](img/641da2c2a30cde79e2af58f13d637ad4_257.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_258.png)

Let's have problem like this。You have。あ、ラクタドす。Of size， W by H。



![](img/641da2c2a30cde79e2af58f13d637ad4_260.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_261.png)

And you have and such smaller tends。Explainial that by the sketch。What is exponential search？



![](img/641da2c2a30cde79e2af58f13d637ad4_263.png)

What is exponential such， Not sure about this。那是我的你。Okay。



![](img/641da2c2a30cde79e2af58f13d637ad4_265.png)

🤧そレす。それ。

![](img/641da2c2a30cde79e2af58f13d637ad4_267.png)

Let's say we have n size rectangles。嗯。And you want to put all these yourtangles in a big square。

 So you want to find a square。Of size， x by x。

![](img/641da2c2a30cde79e2af58f13d637ad4_269.png)

And you want to put all these rectangles into this square。



![](img/641da2c2a30cde79e2af58f13d637ad4_271.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_272.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_273.png)

And the task is to find the minimal size of the square。



![](img/641da2c2a30cde79e2af58f13d637ad4_275.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_276.png)

So this is the typical problem when you can use the binary search。



![](img/641da2c2a30cde79e2af58f13d637ad4_278.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_279.png)

How can I use binary research here？let's say that， let's move here。 So let's say the number is good。



![](img/641da2c2a30cde79e2af58f13d637ad4_281.png)

Means that you can put these and rectangles into square of size X So。 Let's say the x is good。啊。

Will be， by definition， if you can put。on the rectangles。Neel Square。Of size x。



![](img/641da2c2a30cde79e2af58f13d637ad4_283.png)

M。

![](img/641da2c2a30cde79e2af58f13d637ad4_285.png)

Yeah， that's right。 that's the problem from our cold forces course， exactly。



![](img/641da2c2a30cde79e2af58f13d637ad4_287.png)

We use exactly the same problem in code forest scores。And how to， how to solve this problem。

 You'll start from。

![](img/641da2c2a30cde79e2af58f13d637ad4_289.png)

嗯。Let's say that number x is good if you can put all these rectangles in a square of size x。

Then let's go here。 Let's check this property。 If a number x is good and number Y is bigger。

 doesnt mean that number Y is also good。 It does。 because if you， if you take the bigger technical。

Take the thing one way by way。You can still put all these square rectangles in in the square of size y by y。

 So， so this bigger rectangle is also good。 So if number X is good and number Y is bigger then number Y is also good。

 So these properties holes。😊，No。How to use binary search from sector that。

Exactly like we did in the race， we'll have two pointers。

 one pointers will point to some good number and one pointer to some bad number。



![](img/641da2c2a30cde79e2af58f13d637ad4_291.png)

No here and are here。嗯。Let's， let's go function。 Let's go function。 Let's say good。

Of L will be false。

![](img/641da2c2a30cde79e2af58f13d637ad4_293.png)

And。Good of our will be true。Now， what do you do， You try to again。

 you try to move these pointers close to each other until they met in their neighbor important。

 So while。R is greater than L plus 1。 You pick the element。

L plus R over to check if this element is good。啊。Then you move the right point。As。Youも the that。

That's exactly the same quarter as before。Like only here。

 we use the the function good to check if number M is good。

 like to see which of two pointers we should move to this position in the end。

 we need to find the minimum would number。 So will be in the point of R。 So here we will turn R。你走。

Now we need to implement this function route。Let's try to keep。请不用。

So how can we check if we can put n rectangles in a square of size x by x？嗯。Now， let's see。

 what is the optimal way to put rectangles in a square。 It's like this。

 you use this great layout just to put this。Squarees and lines，1 by one by one。

Let's see how many rectangles can be put in square x by x。そう。So here each rectangle has equal to W。

 So the number of rectangles。In in this， we will be x divided by w。エックスデバイル。X。X divided byだ or。

And the number of rectangles in this。So' like will be x divided by H。

Now we'll multiply these to various， and we will have the maxim possible total numbers of rectangles we can put in this in this square。

 If this number is at more at least m。Then the squares would。嗯。嗯哼。え嗯。啊。X， divided by W。

Multipliied by x divided by H is greater than equal to n。And if you's some problems。

 maybe you also need to use some BBN or something like that。So we just not working for someone。

 I don't know what。滚。That's all， that's how you check if， if the number is good。

 So usually in the problem in in in the real problem。

 the only thing you need to think about is how to write this function。

 because this code is only the same。 You， You just make the。Usual binary research。

 the only thing you can think about is to implement this function good。

If actually which checks if this number is good or bad。

 sometimes it's the most tricky is's always the most tricky part of these problems。こ体 was talkingきまヒ。

In the beginning， before we start binary research， we need to find some initial values for L and R。

So here we need to initialize L some and errors。So we need to find some good number and some bad number。

What can we do here， for example。To find some bad number， we can say， for example， if L equal to0。

If l equal to0， then we have empty rectangle， we can add empty square。

 we cant put anything in the empty square。For number R。

 it's a little bit more complicated because we need to find a big enough square to be guaranteed to guarantee that we can put all these rectangles into its square。

One of the way to think is just to take a very big rec just to put some really big number here。

But what will be the big enough number， It's usually complicated。In this case， for example。

 we can say。あ，不。If we take the maximum of W N H。And multiply it by n。That will be totally enough。

 because。If you take the maximum of two dimensions of of the rectangle multiply by a number of rectangles。

 you will have big enough sides just to put all rectangles involved in one row。 So it it will be。

Perfectly enough to fit all the rectangles in this square。But if you， if you take number。Here。

 if you have two big number here。Yeah， yeah，不 no。If you， if you have two big number here。

 you may have a lot of integer orflows problem。If you don't use Pyton and if you have sp。

 you have other problems， usually。Like time limits。

So if you dont use emon use some another language which has some limits for integer types。

 then you may have a lot of integer upper flow problems when you use too big number here。

So you always need to be careful。For example， here， what may happen is if。This number n is big。

 These numbers are big。Then this multiple this product will be big。

 And here you will have product of two big numbers。 So you have an even bigger number。So in this。

Place of your program， you may have。有有 lot。🤧う。Okay， very big， let's say。

s very big probability of the internal flow pre of interior flow errors in places like this。😊。

So how to avoid interior earth flow？There is no short answer about this。

 there are different techniques which may help you to avoid in flows。

One of techniques is just to think about it just。YeahEvery time you try to calculate what may be the maximum number in this place。

 So you know， youll look， for example， Let's know let's， let's just。So you just look， if。

 for example， you have。For example， you have an。No greater than than0 power of 9。 and both。

W and H are not greater than the power of9。Then what will happen here here we will have maximum W and edge multiplied by M。

So this R is not greater than 10 in a power of 18。And here you multiply two such numbers。

 you going lie actually by two it by age。So both these numbers are not greater than of1 power of 18。

So when you multiply them， you'll have them in power of。36。

So you just think what can be the max possible？But then you think if， if this R is big。

 maybe this x over。Wuble will be small。 And you think what， what can be the biggest number here。

 And actually， the biggest number here is when one number is big， one number is small。 So if。我 say。

So if w equals to 10 power of9 and h equals to， let's say one。Then you will have。

R equal to 10 power of 18。And here you have。10 power of18。Divided by the power of 9。

 So here you will have something like 10 and a power of 9 here you have 10 power of 18。

 So you multiply these two numbers and the get long long overflow。

 So you just need always to think about what what happens if I give some big or small numbers in any position。

 What will what can be the maximum value of this product and so on。テストト大しとかなとあ。What is the most？嗯。

I can decrease the quality， for example， that's， that's it's2 it's。I can't modify the quality。

I upload the videos on which in maximum colors then to which。Somehow。确认质行。啊。What was theの？嗯，来。

There are different ways to fix this。 One of the ways to use a Python is always。

 but you'll get time limit in some other place of your program。

 Another way is to use the flow point numbers instead of integers。

So when you have the flow points in the numbers， you will not have integral flows。

 but you will have some accuracy problems with points pointers。So it's not always the good。

 The most safe way， usually is not to pick the biggest possible value here。

 but put some small enough number as the right borderer just。

Try not to pick the very big number for number R， but to to to find some small。

 good number as the initial value of R。 How can you do this。Well doing the all way。

 We'll try to find small good number， so let's stop， so we'll suffer r equal to1。

And then while this numbers。Not good。We will just inclusive device。Like this。是。So again。

 we'll use the same function。This function good。To check if number are as good。

So in the end after this file， we will find some good number R。

And this number R will be small enough because it will be at most twice bigger than the the。

Element we're looking for。We start from Els，1，2，4，8，6， and 32，64。And we check if that was good。

 this is this summer's bad， bad， bad， bad， bad， bad， good。

So this number will be at most twice bigger than this number。So we know that for this number 32。

 we don't have any integerarrow flow here because for this number 32， we have the value less than n。

If you have very less N， you don't have in vote because N is small。So for this number。

 we have at most twice this x then this numbers。 And so we have at most twice here most twice here。

 So this product will be increased most four times。So we'll have no more than4 and in this。Product。

And if any is small， then this brother will not have indeed any in fls。

So this find the most safe way to use binary search when you don't know the good right border。😡，Okay。

Oh。Any questions？This is exp search， okay。Next one。Next problem we'll talk about is the following。

 Again， it is the same as in the code forces course， you can。

You can just go to the code forces course， and。I will do the same thing again。

 Next problem will be following。 We want to。Oh let's？A story picture。

Let's have the following problem。We have a straight line。



![](img/641da2c2a30cde79e2af58f13d637ad4_295.png)

And there are some and people living on these lines。people。Liveing in some positions on this land。嗯。

嗯。嗯。你说对吧。For each one， we know。It's coordinate。Soで。こじない。Is X y？And we know it's speed。嗯哼。ピン。

He needs a double right。

![](img/641da2c2a30cde79e2af58f13d637ad4_297.png)

Mximalスす。So then moving over this straight line to left to the right with some speeds no more than this。

And these people want to gather in the same point。And。嗯，赢。The same。多いんで。And you。

 your task is to find the minimal time we need to spend together in some in， in simple。



![](img/641da2c2a30cde79e2af58f13d637ad4_299.png)

嗯嗯。嗯嗯。That's all。How do solve problems like this？Again， let's say that number is good。😡，If it is。

Let's say。嗯。L have X here， let's say no。No。W。Tea is good。衣ve。They can get the same point in time。嗯。

い1 seconds。Nice， so we will say that number T is good if the people can gather in the same point in three seconds。

Then again， let's check check the property we used we used in in the binary search。

 We need to check if number number is good， then all bigger numbers are also good。 that's true。

 if we can gather in two seconds， we can gather in bigger number of seconds so we just move to the same point and stay stay until we reach the table so。

This property is good for the binary research。The only thing。

We need to do is to implement function good， so we need to check for number T。

 if we can gather in the same point in two seconds。Goで playで。不。

So how to check if we can get it in the same point in0 seconds。Oh， let's see。



![](img/641da2c2a30cde79e2af58f13d637ad4_301.png)

Let's take some someone。

![](img/641da2c2a30cde79e2af58f13d637ad4_303.png)

And let's see where can it moves。 So let's， let's take one of them and see where。

Can he moves after this1 seconds。So if we let him move for 40 seconds and it won't coordinate。

 can he end？呃。He can move to the left。2 position， X， I minus。T multiplied by V， I。

Or he can move to the right。To position X I plus T multiplied by。🤧。

So we have this segment of possible positions。4our each of them。Mmhm。😊，So now we will have this。

Number of list， number of segments。Havelf segments， L。All right will。L， I equal to X。

 I minus t multiplied by V I。And are equal to X plus the。Now all we need is to check if there is a。

Point， which belongs to all the segments。So， we have some。Number of segments like this， this。

This and so on。This segment。This segment， this segment and this segment。

We need to find some point which belongs to all the segments for。

This point belongs to all four segments。🤧嗯。So how can you solve this problem？ No， it's easy。

 Actually， what， what has mean that point belongs to the segment。 It means that the。

Point must be greater or equal than L， and it is less or equal than R。

So we have this set of inequalities like this， central inequalities like this。

 and we need to all inequalities。It is the same。As if x will be greater equal than the maximum。

Of all， left border and。Less or equal than minimum。Of all of the right borders。啊啊啊啊啊啊啊。

Are they moving such manner？If it is possible， yes， they're actually trying to meet。 Yes。

 they want to meet in the same point。They are moving in using some speeds and they want to move in the direction to me。

Yeah， this is a good point。This value not in will changes a little bit later， yeah。That's。

 that's a good point。Let's move back。 So how to check if if number T is good。

 we will build all these segments。Then calculate this maximum。

 calculate this minimum and check that there is some point between with maximum and this minimum。

So what we need to check？Ease。I'll just write some silver code。Oh we need to check this maximum。

Maximum of all。X， I minus T multiplied by V， I。Is less or equal than this minimum。

X I plus team of play。Good， so now we implement function good。

Next next big change is the following this number here。😡，Can be not integer。

So sometimes its the optimal answer is to not integer for example。We have some 2，2，2。

2 people in in integer points， we can move some directions。 So this point will be not integer。 So。

 and this time。Lbin of integer。So how can we make binary surge when we have not injured about  floating point。

Values。Oh， let's say。ちょと決めてめて。ょですちすよで。The basic idea is the same。 We have two pointers。

 one pointers to the good value and other pointers to the bad value。So in zero seconds。

 it's not possible to meet， let's say in。10 power of 10 seconds is possible to me。

Now we will move this pointer close to each other each time we pick the pointers in the value in the middle of LNR and put to L to M or L to M。

And we do this。These until these two pointers are very close to each other。

There are different ways to think about it。 easiest way to implement this is to write something like。

 It's not a good way to write it， but you can do it。 Yeah I greater than Epson。

And say epsilon equal to 10 in power of， I don't know，-9。

So you just move the pointers close to each other until they are so close。

 then it's good enough for you。 But it's always， there's always some。

Howrry in accuracy in this because when you need to return some flows in point value from your algorithm。

 this plot value can be calculated exactly so when you output some flows in point numbers。

 you always have some in accuracy。If this。Epsilon is good enough for you。

 Then you can put this epsilon here and make these operations until these pointers are so close to each other and it is good enough for you。

And that's a good point。Why it's not a good way to implement binary research？Because， sometimes。

You can't have these pointers close to each other。Because what happens？嗯きな。そストレスです。What would happen？

If the value you're looking for is big。 So if this value， if is minimal T， is about 10 power of 9。

 let's say。And you have epsilon about 10 power of minus-9。

Then you actually want these two numbers are that close to each other。

 but both these numbers are that big。So you actually want to have like 18 decimal digits in your floating point numbers。

 but that's too much。 thats double values can have that many decimal points。

 So okay okay you have this value L and R， they are safe in in in computer， something like that。

 So you have some pointer real。And so on。 and in another way， this is L， this is R。

And so on and you have。Some numbers here and some numbers here here and when。

 you have something like a no。Here you have something like。

And both these numbers multiplied by 10 power of night。



![](img/641da2c2a30cde79e2af58f13d637ad4_305.png)

And the number of digits in this representation for double is about。呃。Not sure about this。

I think it's about 16。Not for about 16 or 15。 It's about。So I have about 16 digits。

So if you have these two very close to each other。Then difference between this L R and L。

Will be about so you have one multiplied by 10 out of9， multiplied by 16 dig。

 so it will be something like。喂。We have -16 plus 9。It's complicated minus that seventh grade。

So this difference between L and R is bigger than1 number of minus-9。

 and you can do anything about it。 You cannot have any longer double numbers between these two。

 So these two numbers are like closest possible to double numbers you can do in your computer。

So if you， if you hear your phone PP M equal to L plus or divided by two。

 you will get one of these numbers because there is no any double number between。

It's like mostly likely integers like when you have two neighboring integers。

 here you have two neighboring doubles。So how can you fix this。

 There are several possible ways of fixing this。One way to fix this is just to detect these situations。

 So if you， for example， put the element M here。And here you see that element M is equal to L or R。

Y equal to L or。M equal to R， then it means that you have situation like this， you just break。

That's one of the ways to solve this problem。Another way to solve this problem is just a actually more safe way to do it。

 It's one of the most safest way to implement the binary search is just to have the fixed number of durations。

So instead of doing all this。And thinking about these problems。

 you just make like hundred deters of binary research。他 doesn enough。Okay。

What is the good about the for cycle？It's never give you an infinite loop。

 so this cycle is always making00 iteration no matter what。

 so you will never have an infinite loop when you have four cycle。Very good property。

Will0ts will be enough， now let's see what happened after 100 generationerations。

 the difference between L and R will be each time divided by2。So。嗯。After 100 durations。

 the difference between L and R will be decreased by2 in power of00。that's。About， let's say，200。

The free。oh 때는。That's big enough。 So usually usually this much is enough for any problems。

 so even with this problem， so here I have difference equal to 10 power of 10。

So when I divide this by this， I will have 10 power of minus 20， minus 20 is good enough。

For any problem。Because you don't have BB batteries in in in yellow double， in your double numbers。

So usually con generations is more than that。In real life， if you have double numbers。

 you need something like about 50 operations to achieve the maximum possible accuracy。

00 is safe enough if you just want to write a save binary research。

 you can put hundred here it will not arrive in infinite loop and it will give you a good enough accuracy。

 it sometimes may give you a time limit。Because hundred， maybe to， two big number of operations。

 you can change it to 50 or something like that。嗯嗯。O。Oh。WellAlmost all。

The last thing I was talking about is the term research， let's talk about term research。

If you want to find more implementations or more， more applications of the binary search。

 you can check out the。Lessson in the code forces section do section。It's more contestient oriented。

 so I have more about more different types of problems which can be solved using binary research。

 so if you're interested you can check this lesson。嗯。



![](img/641da2c2a30cde79e2af58f13d637ad4_307.png)

そう。

![](img/641da2c2a30cde79e2af58f13d637ad4_309.png)

The last thing we'll talk about is the Java research。



![](img/641da2c2a30cde79e2af58f13d637ad4_311.png)

Imagine you have something like that。 You have some function， and you want to maximize this function。



![](img/641da2c2a30cde79e2af58f13d637ad4_313.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_314.png)

Very typical situation。 You have something， and you want to maximize this something。



![](img/641da2c2a30cde79e2af58f13d637ad4_316.png)

Like your income。And this value depends on some variable， you have one variable x。

And you have some function of variable X。 and this function。



![](img/641da2c2a30cde79e2af58f13d637ad4_318.png)

Behead like this。 So at some， first， it is increasing。And then it is the。

So we have at least maximal value。

![](img/641da2c2a30cde79e2af58f13d637ad4_320.png)

Now thiss functional F X。And you want to find this maximal value of your function。So again， again。

 the par looks like this。

![](img/641da2c2a30cde79e2af58f13d637ad4_322.png)

Here， function is increasing。

![](img/641da2c2a30cde79e2af58f13d637ad4_324.png)

And here， this decrease me。

![](img/641da2c2a30cde79e2af58f13d637ad4_326.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_327.png)

嗯。That's all。

![](img/641da2c2a30cde79e2af58f13d637ad4_329.png)

That that's the whole problem we have。 You have sound function。

The only thing you can do is just to call this function and calculate the value of the function。

 so you have this function F， you can call it and just calculate the value。

And you know that the function behave like this， so it is increasing and then it is decreasing and you want to find this。

Middle position。So if you跟。嗯。How it's cold。

![](img/641da2c2a30cde79e2af58f13d637ad4_331.png)

お前の那个は。So if you can check that function is increasing or decreasing in the given point。Yes。

 you want to find the peak here if you can check if the function is decreasing or increasing in the given point。

 then you can just have a binary the search。So if you can pick a point and check if function is decreasing or increasing。

 then you can have one pointer here， one pointer here。呃， check。pick something in the middle。

 check if functions is decreasing or increasing and move on with the pointers。

 But in some situations， you can check this。 You can only calculate the value。

 So you can check if function is increasing or decreasing。

 You only can calculate the value in some given point。



![](img/641da2c2a30cde79e2af58f13d637ad4_333.png)

オ。So the algorithm works like this So you have。At， at any moment， you have。



![](img/641da2c2a30cde79e2af58f13d637ad4_335.png)

2 pointers。啊。At any moment， we have two pointers， pointer L and pointer R。



![](img/641da2c2a30cde79e2af58f13d637ad4_337.png)

And we maintain the following property。In this point， the function is increasing。

So here a function is increasing。

![](img/641da2c2a30cde79e2af58f13d637ad4_339.png)

And here the functions decreasing。Again， we cannot check if function is increasing or decreasing， so。

To find the initial values of L and R， we need to get some intuition about this。

 so we need to go to the problem and check if we can find some small enough and big enough value for L and R to function be increasing here and decreasing here。

But that's all。那火最多。

![](img/641da2c2a30cde79e2af58f13d637ad4_341.png)

Let's speak two middle points， let's speak point。Here。And1 end point here， M2。For example。

 let's say that they are on equal distance here。 So M1 equal to L。Two L plus are divided by3。



![](img/641da2c2a30cde79e2af58f13d637ad4_343.png)

And M2 equals to L plus 2 l divided by5。

![](img/641da2c2a30cde79e2af58f13d637ad4_345.png)

Let this。So we pick two middle point like split the whole segment in three equal parts。



![](img/641da2c2a30cde79e2af58f13d637ad4_347.png)

Now let's calculate the function F in these two middle pointss。😡。



![](img/641da2c2a30cde79e2af58f13d637ad4_349.png)

What great。This function， the F of M1。And these will be very your if of M。



![](img/641da2c2a30cde79e2af58f13d637ad4_351.png)

Let's go collect these two values and compare them。So， if。Y。F of M1 is greater than F。Of M度。



![](img/641da2c2a30cde79e2af58f13d637ad4_353.png)

What does it mean。It means that on this segment at some point function was decreasing because we have bigger value here and than here。

 that means somewhere here function is decreasing。And we know that if functions is decreasing。

 then it is decreasing to infin it to the right。So if we have decreasing in function at some point here。

 it means that the function was decreasing here。At point M2 function is decreasing。

If function is decreasing here， we can move the right point of to position M2。If not。

Then function was increasing at some point on this segment。

 and if function was increasing somewhere here， it means it was increasing in point M1。

 it means that I can move point L to position M1。

![](img/641da2c2a30cde79e2af58f13d637ad4_355.png)

That's all。 that's that's how we。啊。Do the talking research。So what is the time complexity again。

 each time we split the segments into three parts and remove one of the parts。

 so we either move this R to M2 or we put L to M1。Each time we decrease the size of the segment in like。

Fre first。Free。No。The scale we have two thirds of the size of the whole segment。啊。That's all。

 so again， the number of durations will be logative of the accuracy we need to get。



![](img/641da2c2a30cde79e2af58f13d637ad4_357.png)

That's all that's how different actually work。What are the tricky parts the tricky？



![](img/641da2c2a30cde79e2af58f13d637ad4_359.png)

How to pick this number， M1 and M2。If the function is increasing， but very slowly。Like you help。

Like very is slowly increasing and then there's very slowly decreasing and you pick two values here and here。

The value of the function may be almost the same。

![](img/641da2c2a30cde79e2af58f13d637ad4_361.png)

So sometimes it's tricky to check it through So。 if you put this what you want to do to make the algorithm faster。

 you want to move these positions and one and too closer to each other。

 So because if you move these two pointers closer。

![](img/641da2c2a30cde79e2af58f13d637ad4_363.png)

Like here。

![](img/641da2c2a30cde79e2af58f13d637ad4_365.png)

Then you， you will move this pointers L and R farther away。

 So the size of the segment will be decreased faster。But if you move this M1 and2。

 too close to each other。You may have accuracy problems because the function will be almost the same in these points。

 No you have if you have two points here， like a1 than two。



![](img/641da2c2a30cde79e2af58f13d637ad4_367.png)

And theyre almost the same。 So the difference between a function of n1 and 2 will be almost 0。

 So you have accuracy problem here。 you may。え要要么呃。Just remove the wrong segment。

 So you want to remove one of the segments， this right segment or this segment。

 So you may accidentally remove the wrong segment。And get the wrong answer in then。ニットビキャフォーヒア。

Any more questions？Okay， let's have the final one the asked photo。



![](img/641da2c2a30cde79e2af58f13d637ad4_369.png)

For the end。What I want to tell you is how to make this even even faster。

 So how to make journal research even faster。

![](img/641da2c2a30cde79e2af58f13d637ad4_371.png)

You can do it the following way。 So let's try to do the following。

 What is the slowest part of the journal research， Actually。

 the slowest part is calculation dysfunction so。usually when you do the binary research or the chart research。

 you spend the most of time to just calculate these functions。



![](img/641da2c2a30cde79e2af58f13d637ad4_373.png)

So what we're doing here， we calculate function twice。

And decrease the size of the segment in twohirs。

![](img/641da2c2a30cde79e2af58f13d637ad4_375.png)

We can do it more of way。We can do it in a more ob。



![](img/641da2c2a30cde79e2af58f13d637ad4_377.png)

Let's see。So we have this push out， this push up。

![](img/641da2c2a30cde79e2af58f13d637ad4_379.png)

What we can do。 Let's calculate the function in this two pointss M and。

 So we calculate it this value calculated this value。



![](img/641da2c2a30cde79e2af58f13d637ad4_381.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_382.png)

。And let's say， for example， if this is less than this， we go to this right segment so no one。

Want to move L to position M1 and go to second from M1 to R。



![](img/641da2c2a30cde79e2af58f13d637ad4_384.png)

When we go to this segment。Well again， we want to split the segments。In the three parts。

And calculate some this value and some this value。そう。

Let's move these pointers in1 and2 in such ensure that this point of this smaller segment will be in the same position in this point M2。

そう。一对。

![](img/641da2c2a30cde79e2af58f13d637ad4_386.png)

W。そう。What can we do， Let's say listen， please。Secondment。We split the segment。In summaryeration。

 So let's say the size of this。Second， for example， is alpha multiplied by R minus now。



![](img/641da2c2a30cde79e2af58f13d637ad4_388.png)

![](img/641da2c2a30cde79e2af58f13d637ad4_389.png)

What do I want to do？Is to pick such alpha。Then I can reduce the electrical quality values。

 so I want when I move to this segment。I will need to calculate。Some this and this point。



![](img/641da2c2a30cde79e2af58f13d637ad4_391.png)

And I want this point to be the same as this point。If if two these two points are the same。

 then I can reuse this value of the function from M2。And in this recursion。

 only calculate this new value because this is already calculatedd。Optimization。



![](img/641da2c2a30cde79e2af58f13d637ad4_393.png)

Let's all now， let's find， let's find the good value alpha。

Let's say here we have alpha arm minus style。嗯嗯嗯。So the size of this part is。Alpha， multiplied by。No。

 it's not。 It's Ar cell multiply right now。It's1 minus alpha multiplied by R minus L。



![](img/641da2c2a30cde79e2af58f13d637ad4_395.png)

So， size of。This part is。Again， it's1 minus alpha。Multipliied by this。

 So it's one minus Santa square， multilyied by our minus cell。So I want this to be equal to this。嗯啊啊。

うマナティスあそう。I need 1 minus alpha squared be equal to T。Great。

So this part is alpha multiplied by R mono cell。And this is1 minus alpha a square because of here is 1。

1 minus alpha and 1 minus alpha。 So it's5 alpha square。嗯。Looks right。Now you just saw this quality。

 it's something simple。 It's one。-2 alpha plus alpha squared equal go to alpha so。

Alpha squared-3 alphapha plus 1 equal to 0。So just solve for this in quality， get the value of alpha。

And it will be the good ratio when you can reuse the qualitative values in the next iteration of the journal research。

 So each time in this journal research， you only need to calculate one of this value。

Another way will be getting from the previous situation of the journalism research。

And this will increase your the speed of your children search at about twice。

 because instead of coulating。Function wise， you calculate only in one point。That's the whole trick。

I think it's all for today， do you have any more questions？🎼。🎼うん。

