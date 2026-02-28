# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p137 17_03_06_算法效率.zh_en -BV18U411U729_p137-

![](img/b5ed7f854999d63a1c687cd855393285_0.png)

This sorting algorithm has a name selection sort， because it selects the smallest element and then adds it to the end of the output。



![](img/b5ed7f854999d63a1c687cd855393285_2.png)

One of the great things about this algorithm is that it's conceptually simple。

 Many people would come up with it themselves via the seven steps。

 and it is relatively simple to implement。However， as sorting algorithms go。

 it is rather inefficient。 If you were to use it on a small data set。

 This would not be a big problem since computers are fast。 However， if you had a very large data set。

 it would be quite slow。So are there other approaches， Of course there are， In fact。

 there are dozens of sorting algorithms。They generally fall into two categories。

 The first of these are simple to understand and implement in code， but slow。



![](img/b5ed7f854999d63a1c687cd855393285_4.png)

Selection sort is one such algorithm， as our bubble sort and insertion sort。

 Their running time is quadratic in the input size。 If you double the size of your input。

 the algorithm will take four times as long to run。

The other category of algorithms is those which are more complex to understand， but much。

 much faster。 Examples of such algorithms include Quicksort， merged sort and others。

 The algorithm used in the Java library collectionions dot sort is a variation of merge sort called Tim sort。

 The runtime for these algorithms is close to linear。 If it were linear。

 Doubling the input size would only take twice as long。

 These efficient algorithms grow slightly more than linear， but are very close to linear。

For the simple and slow approach， the runtime grows quadraically。

 So these are called n squared sorts。 Both selection and bubble sort are n squared sorts。

 They have the same general shape， and the algorithms are easy to understand。



![](img/b5ed7f854999d63a1c687cd855393285_6.png)

Here you see a graphs of the runtime for two of these n squared sorts taken from sort timing Java。

As you can see， these algorithms are reasonable for 20，000 strings。

 taking two and four seconds respectively。For small lists， this might be acceptable。

 but for large lists， the other category of sorting algorithms is much， much better。



![](img/b5ed7f854999d63a1c687cd855393285_8.png)

Let's look at the timings for even more elements to understand why n squared sorts are called inefficient。

This graph shows the n squared source from 10000 to 70000 strings。

 Time and seconds is labeled on the Y axis， and the number of elements being sorted is on the X axis。

 How long would it take to sort many， many more elements。

We can use a quadratic fit of the bubble sort， the first equation shown to extrapolate the sorting for a million or a billion elements。

So how big a difference is there？To sort a million strings would require 6。4 hours with bubble sort。

 using collection dot sorts Tim sort function requires less than one second to sort the same million strings。



![](img/b5ed7f854999d63a1c687cd855393285_10.png)

![](img/b5ed7f854999d63a1c687cd855393285_11.png)

To sort a billion elements would require 738 years with bubble sort。

 We can actually time collections of sort and see that it takes fewer than 20 minutes to sort a billion strings。



![](img/b5ed7f854999d63a1c687cd855393285_13.png)

Fortunately， many languages have an efficient sort built in as part of their standard library。

Of course， such a sort should work on a variety of types so that programmers can get the most use out of it。

 In fact， it has to work with data types that the sort's author didn't think about specifically。

 For example， you want to sort earthquakes。 Do you think the author of Java sorting library was thinking about earthquakes when he wrote that sort。

 Probably not。

![](img/b5ed7f854999d63a1c687cd855393285_15.png)

And certainly， he was not thinking about the particular earthquake class you wrote。

So how does this work？Remember interfaces， you saw these already as a way to write generic code。

 An interface is a type that promises certain methods。 code such as the sorting library。

 can then use the interface type and call the method it promises。

Other code can make can then make instances of classes which implement the interface and pass them to the sorting library。

For sorting， there are two important interfaces， comparable and comparator。

 which you will learn about shortly。In Java， this built in sort is called collections。 sort。

 and it is quite efficient。 It is what you should use any time you need to sort data。

