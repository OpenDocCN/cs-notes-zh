# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p27 P27 06_第一课1-1-6：哈希分析 -BV1KnLCzXEcQ_p27-

![](img/91e43ead324de3ba44f21b46146ceaac_0.png)

![](img/91e43ead324de3ba44f21b46146ceaac_1.png)

So as we talk about hashing， let's talk about some big picture items。

One thing is we might want to determine what the better strategy to use is。

 did we want to do separate training where we have a linked list of nodes or do we want to actually put the data inside the table itself？

😡，And we find that depending on the application you're using a hashtake before。

 the right answer is different。If you have large piece of data that are going to be take a lot of time to copy inside the array itself。

 you absolutely do not want to use an array。 You'd rather use a pointer。

 a linked list to store that data somewhere else。 So if we think about having big records。

 we're going to want to use something like separate traininging to handle big records。

 So using separate traininging for big records。Means that the other solution is probably better in some other way。

 And， in fact， double hashing is great for structure speed。

 Remember that array operations are memory optimized because they're sequentially located in memory。

 So if we care only about raw structure speed。 and we know our data itself is going to be fairly small。

 We can use a close hashing technique such as linear probing or double hashing。😊。

To actually run in a really efficient data structure。 So for structure speed。

 we're gonna to want to do something like double hashing。 So the structure。

 what structure does the hash table replace， might the next question we asked That structure is going to be a dictionary。

 So an AVL tree also provides a dictionary implementation。 And as we discuss AL trees。

 AL do a great job with range finding a nearest neighbor。

 a hash table does an absolutely terrible job with that。 You can't say what value is near 42。

 because 42 hass to one particular spot in the array and the value around 42 may have nothing to do with 42 inside of the actual final array because 41 and 43 may hash you an entirely different spot in the array。

 So it's absolutely essential that we have the right algorithm for our right application。

 because if we need to do nearest neighbor on a hash table。

 we're gonna to see ourselves running an o of in time。So which structure does a hash table replace。

 it replaces a dictionary。What constraints exist on a hash table that's not like a BS T as we just went over。

 the constraint that really exists is the idea that a binary search tree has a great nearest neighbor approach。

 While we have no ability to do nearest neighbor and hash table。

 So when we think about what algorithms to use， we want to use a tree like structure。

 if we ever need range finding or nearest neighbor。 We want to use a hash table。

 If we're always going to have the exact key。 If we're always doing lookups。

 hash tables are phenomenal。 Hah tables are gonna run all of one lookup times。

And hash table and AVL trees are going to run login lookup times。 But when we want nearby neighbors。

 it's logins doing an AVL tree order in to do on a hash table。

 The very last bit is why do we talk about BSTs at all and we talk about BSTs both in an introduction to addictionary structure and because some of the most interesting problems that we're going to solve are not going to be solvable by a hash table。

 A hash table is a fantastic general purpose data structure。

While an A VL is going to solve particularly great problems。 If all you care is a look up。

 the hash tables the algorithm for you， we're going to start using hash tables to build even more complex algorithms as we discuss more complex algorithms next week。

 So I hope you guys have enjoyed learning about hash tables。

 It's one of my personal favorite algorithms。 And I'll see you next week for a number of new videos on an entirely new data structure。

 I'll see you then。😊，🎼。

![](img/91e43ead324de3ba44f21b46146ceaac_3.png)