# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P134：7_时间复杂度.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

When developing applications or evaluating efficiency。

 it is always useful to have a metric or a lens through which you can evaluate fitness for function。

 Evaluation in computer science will often consider two aspects， namely time and space In this video。

 you will learn how to evaluate time efficiency or gauge performance by the time taken to complete a task。

 You can refer to this as the time complexity of a task。

 an application must return information within an acceptable time frame。😊，These days。

 people expect an instantaneous response when clicking on a website。 There might， however。

 be some extra scope afforded to more complex queries， depending on the user' needs and expectations。

 Big O notation is a metric for determining an algorithm's efficiency。

 But simply it gives an estimate of how long it takes your code to run on different sets of inputs。

 In this video， the amount of time and algorithm will take is considered。

 Some of the big O notation you will encounter include the following。😊。



![](img/f53cd65def9506344dad9b3693f09b8f_1.png)

O of1。O of log， log N。 O of log N。

![](img/f53cd65def9506344dad9b3693f09b8f_3.png)

O of N and so on。So how do you measure the quickest possible time that something can be computed。

 You make use of a constant time algorithm where it takes O of one time to compute。 But simply。

 it means that no matter what is entered into a system， it will only take one computation。



![](img/f53cd65def9506344dad9b3693f09b8f_5.png)

A simple example to illustrate this is to consider printing the first item in an array。

In this instance， no matter how many values exist in the array， the approach has a big O of1。😊。

Things can get more complex if you need to do a search。 consider that you have an array of 10 items。

 and you wish to know if a certain value is in this array。

You might apply a loop and check each item to see if the value exists。 In this example。

 the complexity is said to be O of n。This is called linear time。

 The search is going to be equal to the length of the array past。 The larger the array。

 the more time is required to search it。 So if in place of 10 items， you have 100 items。

 then the search will take 10 times as long。 Let's explore an example。

Each operation comes at a time price for time complexity。😊。

So O of one means it costs one single computation and O of n means it costs n computations。

 For example， you wouldn't say it takes 45 seconds。 You would say the complexity is n。

 So for every n action that is plus one on our final result of complexity。😊，If n equals 100。

 it is 100 checks。 The complexity is still O to N。 Only n means it is 10 times longer。

This means that your application speed depends on the size of the data being processed。

 Print array at position N is an example of an0 to1 operation。

 That means print the dock at whatever n is。 It doesn't matter how big n is。 The cost is always one。

 Let's continue to O of log N。

![](img/f53cd65def9506344dad9b3693f09b8f_7.png)

![](img/f53cd65def9506344dad9b3693f09b8f_8.png)

This search is less intensive than O to n， but worse than O to1 O of log n is a logarithmic search。

 so it will increase as new inputs are added， but these inputs only offer marginal increases。😊。

A good example of this inaction is a binary search。

 Imagine you are playing a guessing game with the following prompts too high， too low。 correctect。

 given a range of 100 to 1。😊，You may decide to approach the problem， systematically。First。

 you guess 50， and it is too high。 Then you guess 25， and it is still too high。

 You then decide to go 12 or 13。 It is still too high。

What is happening here is that you are halvlving the search space with each guess。

 So while the input to this function was 100 using a binary search approach。

 you should come upon the answer in under 6 or 7 guesses。



![](img/f53cd65def9506344dad9b3693f09b8f_10.png)

This solution would be said to have a time complexity of O log N。 Even if n。

 the range of numbers entered， is made 10 times bigger， It will not take 10 times as many guesses。

 Let's move on to O N squared。

![](img/f53cd65def9506344dad9b3693f09b8f_12.png)

O N squared is heavy on computation。 This is a quadratic complexity。

 meaning that the work is doubled for every element in the array。

 A good way to visualize this is to consider that you have an array of arrays。

 The first loop will equal the number of elements inputted namely N。

 The second loop would also look at the number of input elements。 N。

 So the overall complexity of running this approach can be said to be n times N， which is n squared。

😊，So how will you visually represent the problem， This graph displays the algorithm for time complexity。

 The X axis relates to the number of inputs， and the Y axis relates to the time taken。

Notice that as the number of inputs increases， it has a different impact on the gradient of the line for all cases。

 but O of1。😊，In this graphical representation of how N relates to the number of computations taken。

 the best time to aim for is O to1。😊，O of log N is still very good。 O to n is acceptable。

 and O N square is not great。 Of course， it is not always possible to tell how long an approach is going to take。

 Let's return to the example of looking for something in a loop。

 while you could say that to search a loop takes O to N time。 This might not always be the case。

 Consider that the item being searched for is the first in array。 Then the return will be in O1 time。

 Pretty good。😊。

![](img/f53cd65def9506344dad9b3693f09b8f_14.png)

Equally， the element might be missing， so every item must be searched。O N time。

The middle case would be that it is found around the middle of the loop O of N over 2。

When evaluating an approach， there are three definitions used。 Best case。

 worst case and average case。 To conclude in this video。

 the notion of time in relation to complexity was introduced。

 You have been given something to consider when implementing a solution to a problem。

 A good question to ask yourself before you start is how many computations Does my solution employ and is there a better way。

 Now that you use a metric to evaluate your solution to a given problem。

 You can start thinking of its efficiency in relation to time complexity。😊。



![](img/f53cd65def9506344dad9b3693f09b8f_16.png)

This is not the only way to consider a solution， and in the next video。

 the focus will be placed on space complexity。😊。