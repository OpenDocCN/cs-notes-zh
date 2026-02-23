# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P141：14_哈希表.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

At this point of the course， you have been introduced to several different data structures。

 and you've discovered that there's not a perfect way of storing information。 Instead。

 there is a wide variety of approaches， each of which is an appropriate solution。

 depending on the problem。In this video， you'll learn about what a hash table is。

 its structure and inherent features and how it works。

 You will also explore some of the advantages of using hash tables and discover what is meant by collisions in hashing。

😊，A hash table contains several slots or buckets to hold key value pairs。

 It requires a hashing function to determine the correct bucket to place the data into。



![](img/b2d3b51edc938ca8e34613e532879269_1.png)

![](img/b2d3b51edc938ca8e34613e532879269_2.png)

A hashing function is any algorithm or formula that is applied to a key to generate a unique number。

😊，Each data item to be stored must have a key and a value。😊，The key is taken。

 and the hashing function is applied to it。Such that it is reduced to a fixed size value。

There are a variety of hashing functions one could apply。

You may be familiar with them in relation to compression。

When you want to send information over the internet。

 you might first compress the size of it to a manageable number of bytes， send it over the internet。

 and then decompress it on the other side。This is an example of how hashing works。

 It reduces the key to a small， manageable size， which then acts as the index indicator。

What information is used to generate the index is dependent on the application？

It might be the data itself if it is small enough， or it might be the last four digits of an employee ID D number。

 or it might be a key in a dictionary。Most programming languages have built in hashing functions like MD5。

 SHA or CRRC 32。😊，So implementing a hashing function is a straightforward job。

 When discussing big O notation， the idea that speed and space are often at odds with one another was introduced。

 This means that you can reduce the time taken to retrieve an item， But in doing so。

 you add overhead to your application。😊。

![](img/b2d3b51edc938ca8e34613e532879269_4.png)

![](img/b2d3b51edc938ca8e34613e532879269_5.png)

Hash tables prioritize speed over space and can retrieve an item in O of one time。

 recall the discussion on arrays。When you want to check if a value exists。

 a search must be executed that checks each element of the list and makes a comparison with a target value。

Worst case scenario， this will take O of end time， or in other words。

 if the element was at the end of the array， it must make end checks。😊。

Hash tables offer an alternative approach to storing and searching data。



![](img/b2d3b51edc938ca8e34613e532879269_7.png)

This is done through use of an index to achieve this。

 you must implement an algorithm that takes in a key and maps it to a value which is stored in an index。



![](img/b2d3b51edc938ca8e34613e532879269_9.png)

Then when a new key is presented， the algorithm need only run the same function and determine where in the index the value lies。



![](img/b2d3b51edc938ca8e34613e532879269_11.png)

Much like an index in a book， this will drastically speed up the time it takes to identify the location of some data。

You are likely to find hash tables used in caches， dictionaries， database indexes and sets。😊。

Consider a scenario where you have an array of 10 keys， which are numbers 0 to 9。

 You will elect to employ a hashing function to decide where in memory to store these numbers。😊。

You opt for a simplistic approach of applying the modulus of 20 to the numbers。

 So for each key from 0 to 9， you apply your hashing function。 Start with 0 mod 20 equals 0。

1 mod 20 equals 1，2 mod 20 equals 2，3 mod 20 equals 3 and so forth。 In this way。

 you would generate 9 unique values， which are used to represent in memory where the data associated with those keys is placed。

 This example is simplistic， but illustrates the mechanism behind creating hash maps。😊。

The issue arises when the number of keys to be stored grows beyond 20。Remember，1 mod 20 equals1。

 but 20 mod 21 also equals1。 Let's move on to collisions in hash tables。



![](img/b2d3b51edc938ca8e34613e532879269_13.png)

What are collisions in hash tables， A hashing function will apply a clever algorithm that will reduce the size of the key to a manageable size。



![](img/b2d3b51edc938ca8e34613e532879269_15.png)

Some approaches are more intricate than others。 So what happens if the result of two hashings is the same。

To expand on this idea， it is worth pondering on von Mis's birthday paradox due to probability。

 Sometimes an event is more likely to occur than we believe it to。In this case。

 if you survey a random group of just 23 people， there is actually about a 50。

50 chance that two of them will have the same birthday。😊，This is known as the birthday paradox。

Say there are 24 employees in a company and a clever hashing function has been applied that takes the date and month of their birthday and uses this as an index。

😊，With only 24 employees and a hash table of 365 index slots to hold a reference to them。

 you may think the probability of any two employees sharing a birthday is unlikely。In fact。

 it has been shown that it is over 50 per cent likely to occur。Next time you are at a party。

 be sure to check if any two attendees have the same birthday to check for yourself。😊。

What this illustrates is that there will be duplicate hashes generated when the hashing function is applied to the key and that allowances must be made for it。

😊，There are a few solutions to the issue。One solution is to grow the table every time a collision occurs。

 then increase the complexity of the hashing approach， redistributing the values to new addresses。



![](img/b2d3b51edc938ca8e34613e532879269_17.png)

In this way， a table will grow organically to match the size of the data required。

 Another is to create a linked list at the point of collision and simply store the additional values。

 So in the event of a collision。 Instead of storing a value。

 you would instead store a linked list of values。 In this video， you discovered what hash tables are。

 their structure and features and how they work。 You have also learned that hashing is a very clever approach to generate O of one time searches using a hashing function and an index。

😊。

![](img/b2d3b51edc938ca8e34613e532879269_19.png)

![](img/b2d3b51edc938ca8e34613e532879269_20.png)

![](img/b2d3b51edc938ca8e34613e532879269_21.png)

You explored collisions and how they can be used to inform the size of the table。

 And you even learned that if you are at a party with more than 24 guests。

 it is more likely than not that at least two will share the same birthday。😊。

