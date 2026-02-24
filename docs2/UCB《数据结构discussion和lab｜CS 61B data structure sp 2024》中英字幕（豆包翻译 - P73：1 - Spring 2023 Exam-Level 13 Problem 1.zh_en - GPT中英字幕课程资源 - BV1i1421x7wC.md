# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P73：1 - Spring 2023 Exam-Level 13 Problem 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

That's what makes you good。Hi everyone this is the CS61b fall 2022 exam prep 12 walkthrough and i'm Sherry in this part i'll be going over question one a sorting caper just as a heads up I'm a little bit sick right now and so I might be coughing in this video luckily coughing isn't contagious over the internet so let's get started。



![](img/7fc1420d92147b2b223b20d9fe0e4db0_1.png)

In this problem we'll be looking at intermediate steps of sorting algorithms and trying to identify which algorithm is in process this is a pretty common exam question。

 so it'll be good to get some practice with questions like these。

The possible sorts that we have are insertion， selection， merge， Quick， and Heap sort。

So let's start with part A one pattern that we can see very clearly is that if we divide our list in half so that would be right around this point。

 we can see that the haveves don't really interact until the very end where they start to get merged together so if you look at the very end here we see that everything kind of is sorted but is still remaining in its own half this is very characteristic of a sort that we know which is merge sort。

And this is kind of the two steps of merge store right we have our recursion where we split everything in half and then everything kind of stays in its own half until we start merging at the end。

And then part B is a little trickier。It doesn't look like there's like a super clear pattern just by looking at it so my trick for this kind of question is that when I don't see a very clear pattern。

 I just test really quickly if it's Quicksortt so let's try that The question tells us that Quickst uses the first element as the pivot so our first element would be 1429。

We can see that in the first step， everything is pivoted around 1429。

 everything to the left is less than 1429， and everything to the right is greater than 1429。😊。

Then we would pick 1337 as our pivot and if we look at the next step。

 we can see that everything is correctly pivoted around 1337。😊，And then our next pivot would be 192。

 and again， we see that the left and right halves of the array are correct。

 so that pretty much confirms that it is quick sort。Heart C has a very obvious pattern。

 we can see that the array doesn't change at all except for the first couple elements。

 so if we compare this to our starting array， we can see that here the end of the array is still exactly the same as it was in the beginning of the problem and only the beginning few elements have changed。

And if we look at steps two and three， we see a similar pattern where the end of the array is kind of remaining this untouched。

 but the beginning of the array is being swapped around。

 so we can tell that this is insertion sort because as a reminder insertion sort you pick a starting element and then you swap it forward as much as possible you move on to the next element swap it forward as much as possible and so in insertion sort。

 the front of the array will change but the back of the array isn't going to change until the very last step。

Finally part D is also a little bit tricky if we look at steps two and three we can see a very clear pattern that the max element keeps getting placed at the end of the array so this is a sign that it's heap sort but step one doesn't really fit with our theory because if we look at the last element we're not placing the maximum at the end but if we go a little bit deeper we have to remember that there's two parts of heap sort that I listed here the first step is that we need to heapify everything so we to turn it into a heap。

And then we can actually pop off things and put them at the end once we have a valid heap。

 so if we look at this again， we can kind of assume that this is the heapplification step and that's why the maximum element isn't at the end yet。



![](img/7fc1420d92147b2b223b20d9fe0e4db0_3.png)

And so this is actually indeed He sort。That's it for this problem here's my weekly exam tip for identifying sorts。

 look for the easy ones like merge S and heap S and insertion So。

 all of those have very clear patterns。But some of the ones that have less clear patterns are probably quick sort。

 so good luck in the rest of 60 on B。