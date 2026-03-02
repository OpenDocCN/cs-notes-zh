# 斯坦福大学《算法启蒙（第2册）：图算法和数据结构｜Part 2 Graph Algorithms and Data Structures》中英字幕 - P19：-19-13   1   Balanced Search Trees  Operations and Applications - GPT中英字幕课程资源 - BV1acVmzNEM8

In this sequence of videos， we'll discuss our last but not least data structure。

 namely the balanced binary search treat， like our discussion of other data structures will begin with the what that is we'll take the client's perspective and we'll ask what operations are exported by this data structure。

 what can you actually use it for。 then we'll move on to the how and the why will'll peer under the hood of the data structure and look at how it's actually implemented and in understanding the implementation we'll understand why the operations have the running times that they do。

So what is a balanced binary search tree good for Well。

 I recommend thinking about it as a dynamic version of a sortded array that is if you have data stored in a balanced binary search tree。

 you can do pretty much anything on the data that you could if it was just a static sortded array。

 but in addition， the data structure can accommodate insertions and deletions you can accommodate a dynamic set of data that you're storing over time。

So to motivate the operations that a balanced binary search tree supports。

 let's just start with a sorted array and look at some of the things you can easily do with data that happens to be stored in such a way。

So let's think about an array that has numerical data， although generally。

 as we've said in data structures there's usually associated other data that's what you actually care about and the numbers are just some unique identifier for each of the records。

 so these might be an employee ID number， Social Security numbers。

 packet ID numbers and a network context， etc。So what are some things that are easy to do。

 given that your data is stored as a sorted array。 Well， there's a bunch of things。 First of all。

 you can search。And recall that searching in a sorted array is generally done using binary search。

 So this is how we used to look up phone numbers when we had physical phone books。

 you'd start at the middle of the phone book。 if the name you were looking for was less than the midpoint。

 you'd recurse on the lefthand side， otherwise you'd recur on the right hand side。

 As we discussed back in the master method lectures long ago。

 this is going to run in a logarithmic time。 roughly speaking， every time you recurse。

 you've thrown out half of the array。 So you're guaranteed to terminate within a logarithmic number of iterations。

 So binary search gives as a logarithmic search time。

 Something else we discussed in previous lectures is a selection problem。

 So previously we discussed this in the much harder context of unsorted arrays。 Remember。

 in the selection problem， in addition to an array you're given an order statistic。

 So if you order statistic that your target is 17， that means you're looking for the 17th smallest number that's stored in the array。

 So in previous lectures we worked very hard to give a linear time algorithm for this problem in unsorted arrays。

 Now， in a sorted array you。I know the 17th smallest element in the array， pretty easy problem。

 just return whatever element happens to be in the 17th position of the array since the array is sorted。

 that's where it is so no problem if it's already sorted constant time you can solve the selection problem。

Of course， two special cases of the selection problem are finding the minimum element of the array。

 that's just the order statistic problem with I equal1 and the maximum element。

 that's just when I equals n。 so this just corresponds to returning the element that's in the first position in the last position of the array respectively。

Well， let's do some more brainstorming What other operations could we implement on assorted array。

 Well here's a couple more， so there are operations called the predecessor and successsor operations。

And so the way these work is you start with one element。

 so say you start with a pointer to the 23 and you want to know where in this array is the next smallest element that's the predecessor query and the successor operation returns the next largest element in the array so the predecessor of the 23 is the 17。

 the successor of the 23 would be the 30 and again in assorted array。

 these are trivial right you just know the predecessors is just one position back in the array。

 the successor is one position forward So given a pointer to the 23。

 you can return the 17 or the 30 in constant time。What else？ Well， how about the rank operation？

So we haven't discussed this operation in the past。

 so what rank is this asks for how many keys stored in the data structure are less than or equal to a given key。

 so for example， the rank of 23 would be equal to 6 because six of the eight elements in the array are less than or equal to 23。

And if you think about it， implementing the rank operation is really no harder than implementing search。

 all you do is search for the given key and wherever the search terminates in the array you just look at the position of the array and boom。

 that's the rank of that element。 So for example， if you do a binary search for 23 and then when you terminates。

 you discover it is there in position number 6 then you know the rank is 6 if you do an unsuccessful search。

 so you search for 21 well then you get stuck in between the 17 and the 23 and at that point you can conclude that the rank of 21 in this array is 5。

Let me just wrap up the list with a final operation which is trivial to implement an a sorted array。

 namely you can output or print， say， the stored keys in sorted order。

 let's say from smallest to largest。And naturally， all you do here is a single scan from left to right through the array。

 outputting whatever element you see next。The time required is constant per elements or a linear overall。

So that's a quite impressive list of supported operations could we really be so greedy as to want still more from our data structure Well yeah。

 certainly we definitely want more than just what we have on this slide。

 the reason being these are operations that operate on a static data set which is not changing over time。

 but the world in general is dynamic。

![](img/579debd663da2b3a2acf87bcc9bcccd5_1.png)

For example， if you're running a company and keeping track of the employees。

 sometimes you get new employees， sometimes employees leave。

 that is we want a data structure that not only supports these kinds of operations。

 but also insertions and deletions。Now of course it's not that it's impossible to implement insert or delete in a sorted array。

 it's just that they're going to run way too slow in general you have to copy over a linear amount of stuff on an insertion or deletion if you want to maintain the sorted array property so this linear time。

 performance for insertion and deletion is unacceptable unless you barely ever do those operations。

So the rayon detra of a balanced binary search tree is to implement this exact same set of operations just as rich as that's supported by a sorted array。

 but in addition， insertions and deletions Now a few of these operations won't be quite as fast。

 we're going to have to give up a little bit instead of constant time to run in logarithmic time but we'll still get logarithmic time for all of these operations。

 linear time for output of the elements in sorted order plus we'll be able to insert and delete in logarithmic time。

So let me just spell that out in a little more detail。

So a balanced binary search tree will act like a sortded array， plus it will have fast。

 meaning logarithmic time inserts and deletes。So let's go ahead and spell out all of those operations。

So search is going to run in log in time just like before。

Select runs in constant time in a shorter array and here it's going to take logarithmic。

 so we'll give up a little bit on the selection problem。

 but we'll still be able to do it quite quickly， even on the special cases of finding the minimum or finding the maximum in our data structure。

 we're going to need logarithmic time in general。Same thing for finding predecessors and successors。

 they're no longer constant time， they go up to logarithmic。

Ran took us logarithmic time in even in as sorted array version。

 and that will remain logarithmic here。As we'll see。

 we lose essentially nothing over the sorted array if we want to output the key values in sorted order。

 say from smallest to largest。And crucially we have two more fast operations compared to the sorted array data structure。

 we can insert stuff。 So if you hire a new employee， you can insert them into your data structure。

 if an employee decides to leave， you can remove them from the data structure。

 you do not have to spend linear time like you do for a sorted array。

 you only have to spend the logarithmic time， whereas always N is the number of keys being stored in the data structure。

So the key takeaway here is that if you have data and it has keys which come from a totally ordered set like say numeric keys。

 then a balanced binary search tree supports a very rich collection of operations so if you anticipate doing a lot of different processing using the ordering information of all of these keys。

 then you really might want to consider a balanced binary search tree to maintain them。

One thing to keep in mind though is we have seen a couple other data structures which don't do quite as much as balanced binary search trees。

 but what they do， they do better。 we already we just discussed in the last slide the sorted array。

 So if you have a static data set you don't need inserts and deletes Well then by all means don't bother with balance binary search trees just use a sorted array because it'll do everything super fast。

 but we also saw two dynamic data structures which don't do as much but do but what they do they do very well。

 So we saw a heap。So what a heap is good for is it's just as dynamic as a search tree。

 It allows insertions and deletions both in logarithmic time。 And in addition。

 it keeps track of the minimum element or the maximum element。 remember in a heap。

 you can choose whether you want to keep track of the minimum or keep track of the maximum。

 but unlike in a search tree， a heap does not simultaneously keep track of the minimum in the maximum。

 So if you just need those three operations insertions deletions and remembering the smallest。

 and this would be the case， for example， in a priority queue or a scheduling application as discussed in the heap videos。

 then a binary search tree is overkill， you might want to consider a heap instead。 In fact。

 the benefits of a heap don't show up in the big o notation here。

 both have logarithmic operation time， but the constant factors both in space and time are going to be faster with a heap than with a balanced binary search tree。

 the other dynamic data structure that we discussed is a hash table。And what hash tables are really。

 really good at is handling insertions and searches that is lookups sometimes depending on the implementation。

 they'll also handle deletions really well also so if you don't actually need to remember things like minima maxima or remember ordering information on the keys you just have to remember what's there and what's not then the data structure of choice is definitely the hash table not the balance binary search tree again a balanced binary search tree would do fine it would give you logarithmic lookup time。

 but it's kind of overkill for the problem if all you need are fast lookups a hash table recall will give you constant time lookups so that'll be a noticeable win over the balance binary search tree。

 but if you want a very rich set of operations for processing your data then the balanced binary search tree could be the optimal data structure for your needs。



![](img/579debd663da2b3a2acf87bcc9bcccd5_3.png)