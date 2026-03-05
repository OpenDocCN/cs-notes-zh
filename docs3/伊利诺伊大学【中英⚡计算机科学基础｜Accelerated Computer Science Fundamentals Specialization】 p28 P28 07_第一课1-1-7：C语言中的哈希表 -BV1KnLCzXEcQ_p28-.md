# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p28 P28 07_第一课1-1-7：C语言中的哈希表 -BV1KnLCzXEcQ_p28-

![](img/43d2310667400a09d77ac0c736ef7ab3_0.png)

![](img/43d2310667400a09d77ac0c736ef7ab3_1.png)

In C++， a hash table is actually built in for us into the C++ standard template library。

 so we can use a hash table inside C++ with very minimal work。

One thing that often people use for a dictionary is a map inside of a hash table。

 and a map has several operations that work really， really well。 We have the index of operation。

 We have the insert operation。 We have the erase operation。

 We also find that we have these lower bound and upper bound operations。 And if you remember back。

 a map actually implements a dictionary。 but it doesn't implement a hash table。 A map， in fact。

 is implementation of a red black tree。 So these operations are going to have a log and running time。

 But instead， we have a different data structure side C plus plus to implement our hash table。

 This data structure is called an unordered map。😊，This unor map is different than a tree in the sense that in a tree。

 we have the ability to do an upper bound and a lower bound search。

 We have that range finding ability。 As we discussed previously。

 we have no range finding ability inside a hash table。Instead。

 we still have the same base operations。 We can still find， insert。

 remove and delete items from our hash table， but we have different functions because we have a hash function table。

The function we have in a hash table are getting things like the load factors。 So inside C plus plus。

 we can ask a hash table， how crazy big is it。Does have a load factor of 05。

 Does I have a load factor of 06， And we can do something really interesting。

 We can set what load factor we want our algorithm to target。



![](img/43d2310667400a09d77ac0c736ef7ab3_3.png)

So we can target a load factor of something as terrible as like 1。

0 when our algorithms performance starts to degrade terribly。

 So if you want to be really mean to someone， you can ask the standard template library。

 we can have them really set up a really， really， really terrible load factor。

 All of this gives us this ability to program some C plus plus code using an unordered map to implement a hash table to give us these0 of one guarantees as long as the load factor is corrected。

 So now you never have to write a hash table， you can just use what's one in C plus plus。

I look forward to seeing some of your code as you work on using some hash tables。😊。

I'll see you later。🎼。