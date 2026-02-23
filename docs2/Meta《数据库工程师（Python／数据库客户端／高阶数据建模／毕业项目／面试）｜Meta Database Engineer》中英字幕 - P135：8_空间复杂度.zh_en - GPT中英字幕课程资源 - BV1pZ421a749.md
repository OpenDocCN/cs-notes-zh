# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P135：8_空间复杂度.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

In the previous video， you learned that the time spent on an algorithm depends on the problem complexity and data structure。

 Another consideration when evaluating suitability is space。

 How much memory will a given solution take。 This is often a trade off with time。

 The selection of this data structure will pivot on what your priority is。 speed or compactness。

 Some algorithms like the hash tables you learn about later in this course provide very fast look ups in O of one time。

 However， to work efficiently， they must have a look up for every element stored。

 This results in a space complexity of O of N。😊，The big O notation for space complexity is the same as for time。

O of one。O of log， log N， O of log N and so on。In all these notations。

 N refers to the size of the input。This is often measured in bys。

Different languages have different memory costs associated with them In Java， for instance。

 an integer requires four bys of memory。A blank array will consume 12 B for the header object and an additional 4 B for padding。

Thus， if n refers to an array of integers size 4， then the total memory requirement is 32 bytes of memory。

When discussing space complexity， you have to consider what the increase in input size has on the overall usage。

 The space complexity of a problem can be broken into two sections。 namely auxiliary and input space。

 Auxiliary space is the space required to hold all data required for the solution。

It refers to the temporary space needed to compute a given solution。

Input space refers to the space required to add data to the function， algorithm。

 application or system that you are evaluating。😊，Consider when you are learning long division。

You may have been taught using a methodical approach that involved breaking each computation into simpler steps To achieve this。

 you would create a table to hold the temporary calculations。

Some complex problems require the same additional allocation of space to hold their workings temporarily while the solution is being calculated。

😊，Big O' space complexity allows for the auxiliary space required for coming upon a given solution。

So it can be said that space complexity equals input space plus auxiliary space；

 that is the space required to compute a result。😊，Remember that you calculated the space complexity where an integer requires 4 B of memory。

 You added the 12 B of the header object and the 4 by for the padding。 The total was 32 B。 However。

 consider that the size of the array is doubled to 8 integers。

 Space complexity is now computed the same way， and the total will be 48。

 The space complexity is higher。Adding additional input did not increase the size of the auxiliary space。

 So when computing the big O， you can discount the auxiliary size if it is not impacted by increasing the input size。

 knowing that each decision made in computing a solution requires memory。

 It is worth noting the aspects that can increase memory usage。

Some common memory actions could be assigning variables。

These can be temporary variables when computing a solution， as with the long division analogy before。

Creating a new data structure。Some solutions require that a new array be created to contain the values or a duplicate array that retains index locations。

 creating a new data structure instance has an O to n auxiliary memory cost function calling and allocation also have additional memory overheads。

 It is worth bearing in mind how space is being used when designing an application。

 creating a new variable to contain a value in place of overr an existing one will impact your space efficiency。

😊，This impact is greatly increased if you needlessly copy arrays or complex data structures with high data overhead。

😊，Additionally， writing functions that use complex structures when simpler。

 less intensive structures will suffice， can incur a penalty。

 particularly if these structures need to be duplicated in computing a solution。



![](img/3f85b7e4605ed9dec9ce98797d648661_1.png)

In conclusion， in this video， the concept of Big O was expanded from one focused on time consideration to one that includes space complexity。

😊，It was highlighted how there is often a trade off between speed and memory efficiency。

 Additionally， there were some observations on the efficient use of space when designing a solution that is worth bearing in mind。

😊。

![](img/3f85b7e4605ed9dec9ce98797d648661_3.png)