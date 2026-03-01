# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p91 25_03_04_ArrayList.zh_en -BV18U411U729_p91-

![](img/d9cf140833e6431d463c790fde19bf79_0.png)

Welcome back In this lesson， you'll learn about a new class。

 a very important part of Java that combines essential features of the storage resource class and an array。

 In fact， this new class， the array list is the foundation of how the storage resource class is implemented to motivate the problem。

 Think about counting how many different words there are in a file or a web page。

 But the same problem is encountered in finding the number of unique I P addresses that visit a website in a day。

 A key part of charging a company for online advertising。😊。



![](img/d9cf140833e6431d463c790fde19bf79_2.png)

![](img/d9cf140833e6431d463c790fde19bf79_3.png)

![](img/d9cf140833e6431d463c790fde19bf79_4.png)

![](img/d9cf140833e6431d463c790fde19bf79_5.png)

You've seen how to count the number of each type of nucleotide in digitized DNA。



![](img/d9cf140833e6431d463c790fde19bf79_7.png)

And you used an array to count the number of occurrences of each alphabetic character in cracking a Caesar cipher。



![](img/d9cf140833e6431d463c790fde19bf79_9.png)

These are first steps in counting how many times each word occurs in a file。

 how many times the occurs or cat or the word albatross。

 One important part of solving that problem is finding how many different words there are so that the counts as one word rather than 573 if it occurs that many times in a document。



![](img/d9cf140833e6431d463c790fde19bf79_11.png)

![](img/d9cf140833e6431d463c790fde19bf79_12.png)

If the image below。In the image below， there are only three different digits，4，6 and 7。

 even though there are hundreds of digits shown。 We'll look at storage resource as a way of solving this problem。

 First， we'll count the total number of words in a file or web page。

 The class storage resource makes this easy to count the words in a file or web page。

 you'll iterate over either a file resource or URL resource。 As you can see in the highlighted code。

 iterating over a file or web page using these resources uses nearly identical code。

 And here you see that simply calling the dot add method。

 adds each word to the storage resource instance variable。 My words。😊。



![](img/d9cf140833e6431d463c790fde19bf79_14.png)

![](img/d9cf140833e6431d463c790fde19bf79_15.png)

![](img/d9cf140833e6431d463c790fde19bf79_16.png)

![](img/d9cf140833e6431d463c790fde19bf79_17.png)

![](img/d9cf140833e6431d463c790fde19bf79_18.png)

![](img/d9cf140833e6431d463c790fde19bf79_19.png)

When done the dot size method will provide the total number of words read。

 the method dot gate count returns this number when called again。

 using the instance variable My words， which was initialized in the constructor and added to in the method read words。



![](img/d9cf140833e6431d463c790fde19bf79_21.png)

![](img/d9cf140833e6431d463c790fde19bf79_22.png)

As you'll see， it's easy to use storage resource to count the number of different words。

 not simply the total number of words。This code can be easily modified to find the number of unique or different words in a file or web page。



![](img/d9cf140833e6431d463c790fde19bf79_24.png)

The field， my words， whose type is storage resource can store all the words。

 as you've just seen and as shown in the code here。



![](img/d9cf140833e6431d463c790fde19bf79_26.png)

![](img/d9cf140833e6431d463c790fde19bf79_27.png)

The dot add method adds every string read to my words。

 but it's simple to guard the call to dot add with code that only calls dot add when the word is seen for the first time when it hasn't been stored in my words yet。

The dot contains method returns a buoan value。In the code here。

 this value is used to ensure that the dot add method is called only when the storage resource object my words does not contain a word。

However， the storage resource class is not a good choice for choosing elements at random。

 A key part of the story telling code G lids were working on。To choose an element at random。

 we must use the iterable interface that storage resource provides。

 This means we use a loop to access every element in the storage resource object。

 My words in the loop here， we'd really like to iterate as many times as the value stored in variable choice。

 because we want to choose a random element of the storage resource。😊。



![](img/d9cf140833e6431d463c790fde19bf79_29.png)

The code here returns a random string when the value of counter reaches0。As you can see in the code。

 the value of choice must reach 0 since it starts as a value less than the size of my words and is decremented by one each time through the loop。

 However， the Java compiler analyzes a loop with an if statement and doesnt know that it's possible。

 the if statement must be true at some point。The compiler indicates it's an error to be missing a return statement after the loop。

 even though that part of the code is never reached。It would be simpler to code and much。

 much faster to use a string array to get a random element as shown in the code here。

We simply generate a random in and use that as an index into the array。Unfortunately。

 we must specify the capacity of an array when we declare it。

A rays do not grow in the way that a storage resource object grows。

The class array list provides a solution and combines the best feature of storage resource and arrays。

 The class array list is from the Java。 U package。 the same package that contains the random class we've used。

😊，An array list expands its capacity as needed when its dot add method is called just like a storage resource object。



![](img/d9cf140833e6431d463c790fde19bf79_31.png)

And Raylist also provides access via indexing so that the zeroth or 10 firsts element can be accessed without iterating over all elements。

 just like an array。

![](img/d9cf140833e6431d463c790fde19bf79_33.png)

The storage resource class uses an array list internally。 In fact。

 it's simply a little easier to use than an array list。 but as you become more experienced。

 you're now able to use a list which stores any kind of object， not just strings。



![](img/d9cf140833e6431d463c790fde19bf79_35.png)

The basic syntax of the Rays class is shown here， but you'll see it used in a codinging example in the next lesson。

To declare an arrayless variable， you must include the type of object stored in the array list using the angle brackets as shown here。

Like any object， creating one requires calling new and providing the class name as a constructor to create and initialize the object that's shown here and assign to the variable words。

Then you can call the dot add method to add strings to the Arlist object。

 and you can call the dot get method to access a particular element via indexing。

 just like the bracket notation used within an array， but within array list。

 you'll use the dot get method。The dot set method can change or set the element at a particular index in the rayless object。

Here the first or zeroth index element is set to the string goodbye。

We'll see more examples as we go through a coding example with a rate list。

 The arrays class is more powerful than storage resource and can sort any kind of object。

 It will be an essential class in solving many problems with Java。 Thank you。😊。

