# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P155：19_搜索算法.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

In the previous video， you explored sorting and were introduced to several sorting approaches that can be used for a data set。

😊，However， what if you need to search this data for a specific element in this video you'll be introduced to some of the various approaches to searching such as linear and binary。

 you'll also discover the steps involved in implementing both of these approaches and explore the advantages they offer。

In computer science， searching is a fundamental operation when provided with a collection of data。

 there may be a need to identify specific elements within this data。However。

 the exact description of the element does leave room for some interpretation from the onset。

 you might consider the question， given a hash table。

 is there a key value pair that matches this key。This is a simple。

 like for like comparison that will produce either the absence of a unique key or the return of a unique key。

Some considerations when making a search might include finding the largest number in this array or the smallest or to return the median number from this collection of numbers。

 However， what if the value does not exist。What should be returned。

 returninging a null value can interfere with an application's ability to run afterwards。

When doing a search， you need to consider what safeguards should be put in place when there is no value returned。

 You should also consider if the search is supposed to return the first instance of the value or the last。

In the additional reading at the end of this lesson， there is a link to a talk from Tony Hall。

 the inventor of Null， who refers to it as his billion dollar mistake。

 The simplest search that you can implement is a linear search。 If you have an array of elements。

 a linear search begins at the start of the index and searches through the array until an appropriate element is found。

 or there are no more elements to check。In this approach。

 the best case scenario would be O of1 and worst case O of n。

 as each element would have to be checked before its possible to say that the target element is absent。

In relation to data structures， it has been shown that some have inherent sorting tendencies such as a heap or a binary tree。

You can also take any data structure and apply a sorting algorithm to it before applying a searching approach。

Using a binary search will halve the search space at each iteration。On screen is a data list。

 A binary search will firstly check the halfway way point and determines if the element is greater or smaller than the target element。

 If the middle element is less， then the left half of the list is discarded。

 and the right half becomes the focus。😊，So。Now， only the right half of the list is queried for the middle value。

Again， if it's less than the target element， it is once again discarded。

 and the right half of that filtered list will be examined in this way。

 the algorithm halves the search space at each iteration。😊。

This approach is quicker than a linear search， but does require the data to be sorted before beginning the search。

It may not seem like a reasonable requirement to have this。

 but if your data is read more often than it is updated。

 then such a solution might be an appropriate implementation。😊，Again。

 as with the linear search you covered earlier， the best possible outcome from this approach is that the element is found in the first go O of1。

 However， the worst K scenario is less optimistic。 after the first search， the list isalved。

 If this iteration is not successful， it is halved again。 than after the third division。

 it is halved again and so on。 Therefore， it can be said that after J iterations。

 it is N over 2 to the power of K。 or in other words， O log N。😊。

This is considerably more efficient than a linear approach。 However。

 it is worth bearing in mind that any perceived gain in time needs to be offset by the time taken to sort the list。

 If the list is updated regularly， this can become a costly process。In this video。

 you explored binary and linear search functions。 The steps taken to complete these searches in how they work。

 You also learned how the application of big O can be used to estimate the efficiency of both。

 You've even learned how through some clever adaptations to a standard approach。

 It's possible to seriously improve performance。 Keep up the great work。 In the next lesson。

 You'll start learning how to work with algorithms。😊。



![](img/acfb86b7efe7b319573131ca3e246898_1.png)

![](img/acfb86b7efe7b319573131ca3e246898_2.png)