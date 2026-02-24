# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P146：10_基本数据结构.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Having a knowledge of data structures is useful for any coding interview may encounter from basic data structures like strings。

 Booles or arrays to more advanced data structures like collections， graphs and heaps。😊。

Understanding the data you're working with and the most appropriate structure to use can be very beneficial。

😊，In this video， you will be introduced to data structures。And the two main types。

 mutable and immutable。You will also learn what to look for when considering a given data structure in your own applications。

😊，A data structure models an object so that it can be stored and organized easily in computer memory。

😊，It can be a simple， immutable structure that does not change after creation。

 or it can be a mutable structure that facilitates operations to be performed on the contents。😊。

Operations might include updates and queries to be performed on the contents of the structure。



![](img/6f57e65d01843b2cb688e41f7bb7368e_1.png)

On the surface， it may seem that a mutable structure should always be used。 However。

 mutable structures require time and effort to model。

 and some objects are very complex and not easily modeled。

Other concerns such as space may be a factor。😊。

![](img/6f57e65d01843b2cb688e41f7bb7368e_3.png)

Understanding the underlying mechanics of data structures can be a great advantage because decisions to use a particular data structure can have far reaching implications on a project's progress。

😊，While the implementation and capabilities of a data structure can range between various programming languages。

 the overarching architecture generally follows similar patterns。😊。



![](img/6f57e65d01843b2cb688e41f7bb7368e_5.png)

Here is a universal classification of data structures that categorizes the different types of structure into two main branches。

 linear and nonlinear。😊，This relates to how the elements are stored within the data structure。😊。



![](img/6f57e65d01843b2cb688e41f7bb7368e_7.png)

A linear structure relates to how the information is stored。

 The elements of the structure are arranged one after another， or sequentially。



![](img/6f57e65d01843b2cb688e41f7bb7368e_9.png)

Reflecting the order that they were inputted。Examples of linear structures are arrays， cus。

 stacks and lists， and it infers that each element is attached to the element that precedes it。😊。

Some languages will demand that only similar types of data are stored on the same structure。

Therefore， you will have integerists or string arrays。Other languages will allow for mixed arrays。

 This would mean that storing an integer and string in the same array is not prohibited。

This easy approach can come at the cost of error handling down the line。 For example。

 imagine you have created an array and want to find the sum of your values only to discover that the total is three pineapples and one apple。

Once a simple structure has been created， such as a list or array， it will contain an index。

 An index is a way of accessing elements that may not necessarily be the first or last instances。

Generally， use of an index is done through appending square brackets and the location of the item as an integer。

😊，So array 4 would indicate that the required element is the fourth item of the array。 However。

 programming languages are predominantly0 based， which means that the count will start at 0。😊。

Therefore， array 4 would actually be the fifth item in the array。😊。



![](img/6f57e65d01843b2cb688e41f7bb7368e_11.png)

Accessing an array through the use of an index can throw an error if index location 8 is requested。

But there are only7 elements in the array。A common feature of these structures is that most languages have a built in length method that will inform as to how big an array is。

 An example of this would be calling a dot length in Java or placing it inside a length function in Python。

 While the mechanism of how to retrieve the length fair。

 It is possible in most programming languages。

![](img/6f57e65d01843b2cb688e41f7bb7368e_13.png)

Arays and lists are typically first class objects。 This means that all functionality that is available to other variables is available to them。

This definition generally indicates that a data structure can be passed as a parameter to a function returned as a result or assigned to a variable。

😊，When passing a list or a to a function， care should be taken that the structure is actually passed and not just a reference to the structure。

😊，This can be a memory saving device used to prevent copying the information。 However。

 such instances can cause an error if a change in the structure inadvertently affects the array in the calling environment。

In this example， a string has been added to a list of integers。

 and because the new list points to the initial list， the initial list is also changed。Therefore。

 it is better to make a copy of the array and pass the copy to the function。

 Another memory related issue to be mindful of， is memory leak。 Memory， as previously mentioned。

 can be arbitrarily allocated。 If this memory is not used。

 then it is good practice to delocate the memory location as a result of careless programming or other issues。

 It is possible that a program makes repeated calls that result in excessive memory being allocated and not then delocd。

😊，Over a prolonged time or through repeated calls， this can cause the application to run out of memory and crash。

😊，Most compilers have sophisticated algorithms for detecting and delocating memory to avoid this issue。

😊，In contrast to linear structures， there are nonlinear instances such as trees or graphs。

 These structures do not allow you to traverse the data in one smooth motion。 Instead。

 you can investigate certain paths。 The makeup up of these structures。

 means that they can include natural sorting， which makes querying for specific data very quick。



![](img/6f57e65d01843b2cb688e41f7bb7368e_15.png)

You will learn about different types of sorting later in the course In this video you had a general overview of data structures。

 including their two main types， linear and linear。



![](img/6f57e65d01843b2cb688e41f7bb7368e_17.png)

You have also learned about some of the considerations that should be made when deciding the type of data structure you should use。

As you progress through this module， you will explore these structures further and learn about some of the individual strengths and weaknesses。

😊。