# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p134 14_03_03_算法开发.zh_en -BV18U411U729_p134-

![](img/290f42bfb912eab88a6b5b20d4fb7c33_0.png)

So how would you go about sorting data， There are many ways to sort some more efficient than others。

 as with all things， you can use the seven steps to devise a solution of the problem here we start with a small example using numbers。

 sort 56，17，4 and 33， even though you want to sort earthquakes。

 you can design the algorithm by working with numbers， then adjust it to extract a particular data。

 magnitudes， distances， depths， or whatever that you want to sort by。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_2.png)

![](img/290f42bfb912eab88a6b5b20d4fb7c33_3.png)

![](img/290f42bfb912eab88a6b5b20d4fb7c33_4.png)

![](img/290f42bfb912eab88a6b5b20d4fb7c33_5.png)

![](img/290f42bfb912eab88a6b5b20d4fb7c33_6.png)

Working through this small instance by hand is fairly straightforward as the list is small and it is easy to see how to put the elements in order。

 however， as always， you must be careful to do it in a step by step fashion and not just write down the answer。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_8.png)

![](img/290f42bfb912eab88a6b5b20d4fb7c33_9.png)

![](img/290f42bfb912eab88a6b5b20d4fb7c33_10.png)

Now that we have done this， let us go back and carefully think about what we did and write down those steps。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_12.png)

First， let us name things in and out to make them easier to refer to clearly。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_14.png)

You should also explicitly note that out starts as an empty array list。

 that is an easy step to mentally gloss over， but it is important to include when you translate to code。

The next thing we did was find the smallest element in n， which was4。

Then we removed4 from in and added it to out。Next we found the new smallest element in in。

 which was 17， so we removed 17 from in and added it to the right end of out。

Now the smallest element in in is 33， so we remove that from in and add it to the right end of out。

Finally， 56 is the smallest element in in， so we remove it and add it to the right end of out。

Now you are done out has the data sorted the way you want it， so it is your answer。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_16.png)

Now you have these 14 steps to sort this particular data set。Of course。

 you'd like to be able to sort any set of data so you want to generalize these steps into an algorithm which works on any set of data of any size。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_18.png)

As usual， you can see repetition in what you are doing， but as is also typical。

 there are some differences between the similar steps。

 you need to find the patterns in these before proceeding。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_20.png)

The difference between these similar steps is the particular numbers in each group here。

 whatever you found for the minimum element in the first step of the group is the number that is removed from in and then added to out in the other two steps。

 As usual， you should give this a name and use that name to make the repetitive steps completely uniform。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_22.png)

Here we have named this element， this value， min element， and made the steps uniform。

We are almost ready to express these as repetition。

 but there's one last detail we need to think about How do we know when to stop repeating these steps。

 unlike many algorithms that you have seen before， we are not doing for each element of the input。

 not only are we not going through them in order， but it is generally a bad idea to try to do for each element while removing items from the array list。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_24.png)

Let's go back to where we worked this problem by hand to think this through。Going back through this。

 you can clearly see that we are not doing a for each element repetition as we are not working with each element in order。



![](img/290f42bfb912eab88a6b5b20d4fb7c33_26.png)

Now that we are done， it's pretty clear that we are done。

 but how can you tell it is because in is empty， since this is how you can tell that you are done。

 it is also what you should express in your algorithm。With that observation。

 you could write an algorithm that looks like this。

 noticeice how we express the repetition based on what we just thought through。

 you want to repeat these steps as long as in is not empty When you go to translate this to code。

 what kind of loop would this be。Hopefully you remember while loops from before。

 they are the best way to express this kind of repetition。As usual。

 it's a great idea to test out your algorithm before you translate to code。

 try this algorithm out for this input， 9， negative 3 and0。Did the algorithm work correctly， great。

 it's time to turn it into code。