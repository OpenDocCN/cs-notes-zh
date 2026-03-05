# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p01 P1 01_1-1-数组 -BV1KnLCzXEcQ_p1-

![](img/39289b2d96f969fa99a8c7d03707f100_0.png)

![](img/39289b2d96f969fa99a8c7d03707f100_1.png)

An array stores data in blocks of sequential memory will den an array visually by a large rectangle with many smaller rectangles inside。

On the leftmost side， well have index 0， which is the first element of the array。

 and every element that follows will have an in index that increases by one。

This entire array is placed in one sequential block of memory so that as soon as one element ends。

 the next element begins。Let's look a couple examples。

 An example of an array that has the first 10 prime numbers。 Is this first array right here。

 You'll see in index 0。 We have the very first prime number 2。

 and immediately following this in memory， we have the next prime number 3， followed by 5， then 7。

Arays aren't limited just having integers。 Here's an array that contains eight characters。

Let's see a C++ program that contains a basic array。In C plus plus。

 here's the syntax to create an array of a fixed size of values。

 We see the type of this array is integer， and it's going to contain 10 integers。

 Here are the first 10 prime numbers。

![](img/39289b2d96f969fa99a8c7d03707f100_3.png)

We can access each element of the array using square braces。

 So here values at 3 is going to access the third index in the array。 Remember。

 indices start counting from 0， So 0，1。2，3。And the third element is number 7。

 We expect this program to output 7。Let's see what happens when we run。



![](img/39289b2d96f969fa99a8c7d03707f100_5.png)

A raise example 1， moving into their raise directory。And moving into example one， running make。

You can see we've already made it。 So I'm going to make clean just to really remake it。

And run dot slash main。And here we see the output is 7。Awesome， so this is exactly what we expect。

 We expect the third element or the third index in array to be the value 7。😊。



![](img/39289b2d96f969fa99a8c7d03707f100_7.png)

Arays have a few limitations。 The first limitation is all data storedor in the array must be of the same type。

 An integer array can only contain integers。 A character array can only contain characters。

 A cube array can only contain cubes。 And because we know two facts about arrays。

 We know that all arrays are the same type， and we will know that all of a certain type is the same size。

 So we know the size of a type and we know all of the elements are the same type。

 knowing both of these things， we can calculate the given offset from any fixed starting point of the array。

 For example， if we look at this array， we know this an array of integers。

And if we want to know where index 5 is located at， Well we know it's 1，2，3，4。

5 integers past the start of the array。 If we look at another array， consider a cube array。

We can use a size up operator in C plus plus to ask the compiler to tell us how big a cube is。

So size of cube is going to return what the size and memory it takes to store cube in terms of the number of by。

 So if we find out that each cube is 8 by long， then we can actually calculate what the offset is to index 3 index 3 being right here。

 We know that it takes us three cubes to reach index 3 So three times 8 B。

 means we have to advance 24 Bs from the beginning of the array to access the third index。

 This is really powerful because we can use a simple equation to access the exact memory location we need to go to。

 Instead of having to jump to the millionth element by looking at each element in between。

 we know we want to look at the millionth index。 we do a million times the size of the data。

This is a really fast operation， And we're going to contrast this against other data types as we explore those。

 Let's build a C plus plus program that actually shows off the size of operator。

 as well as showing off the memory address。 Here's example 2。

 We see we have the same array of prime numbers。😊。

![](img/39289b2d96f969fa99a8c7d03707f100_9.png)

And the first thing I'm going to output is the size of an integer。

 So we want to know how much memory does it take to store an integer on your computer。

Computers are either going to take 4 or 8 B to store an integer。

 and that's going to largely depend on what kind of system you're on in other compiler settings。

 If it takes 4 by。Then we're going to see 4 byte printed out here。

 and then we're going to go ahead and calculate the offset by looking at the memory address where index 2 is stored minus the memory address where index 0 is stored。

We're going to look at how much memory is between index 2 and index 0。

So thinking about what we expect is if we expect the size of to be4。

Then the difference between index 0， index 2 is going to be two integers or four times 2。

 So if this number is 4， I expect the output of the offset to be 8。

Let's go ahead and run this program and see what happens。 I'm going to clear the screen。

Move into example 2。And run make。Then we're in dot ssh main。

The first number we see here corresponded to the size of an integer。

 So the integer on the system is 4 by large。The second number is a distance between the index 2 of the array and index 0 of the array。

 It's 8 by exactly what we expect。 So we know they exist sequentially in memory。



![](img/39289b2d96f969fa99a8c7d03707f100_11.png)

Let's look at another example。Here in example 3， we have three cubes， cubebe 11。

 cubebe 42 and cube 100。 We can now print out the size of a cube。When I ran this program earlier。

 I found out that my cube was 8 B large。 So story and Cuban memory takes exactly twice as much memory as story inthger。

😊，And I can do the same calculation。 How far away is the Cuba index 2 from the Cuba index 0。

Here we have 8 B blocks of memory。 So when we have two cubes， they each take 8 B。

 We'll see that we have to travel 16 B to access this second element。

 So what that means is even though we see the exact same syntax。

 this line of code did not change whatsoever。But because the contents and type of our array is different。

 it's going to advance by different offsets。 So what we expect to see is the first line to be 8 and the second line to be 16 by。

 different values because we have a cubeer array instead of an in array。

 Let's go to console and see if that works out。

![](img/39289b2d96f969fa99a8c7d03707f100_13.png)

Moving into the example 3 directory。Running make。And running dot slush main。

Here we see when we run Maine， the numbers 8 and 16。 This is exactly what we thought wed see。



![](img/39289b2d96f969fa99a8c7d03707f100_15.png)

Awesome， let's explore another limitation of an array。

 A second limitation of an array is that an array has to have a fixed capacity。

 So an array must sequentially store data and memory。

 and the capacity of the array is the maximum number of elements that can be stored sequentially in that piece of memory。

 So the size of the array is the current number of elements in the array。

 While the capacity is the maximum number of elements it can exist。

 Once we exceed the maximum number of elements in array。😊。

We have to resize the array to allow us to have more memory。 Remember。

 we can't just have an infinite amount of sequential memory because we're going to have other things in memory。

 So we' got to find a block large enough to store all of the elements we care about in the array。

 and we're going to request a block that's only large enough to store the data we care about right now。

 as the array grows， we'll resize it。 But as part of resizing。

 we have to allocate a new chunk of memory。When we do allocate a new chunk of memory。

 we may need to copy the data over。 So if the old location has 10 elements here and we want to add an 11th prime number。

 then we have to copy over all of the original elements。

Only then when we want to write another prime number 29。

 can we do that once we have space here at the end of the array。Until we have that space。

 if we wrote to the end of the array， we're writing in someone one else's memory。

 We saw earlier the standard vector， and the standard vector is something in the standard template library that implements an array as a dynamically growing array。

What that means is that internal to the vector， when the vector's capacity reaches the size of the array and it needs to add another element。

 it has to go about resizing itself。So all of the things you just saw is true about a vector。

 The vector has a fixed size。 The vector has a fixed capacity。

 Whenever the size reaches the capacity， Then we have to expand the vector。

 Let's look at a very last example that really dives into how a vector works and really see that it is exactly the same thing as an array。

 So similar to example 3， I have an array of three cubes。

 But instead of having a native C plus plus array， I have a vector。



![](img/39289b2d96f969fa99a8c7d03707f100_17.png)

The initial capacity of the vector is going to be outputted in cubes do capacity。

 This tells me how many elements can be stored at maximum， in my vector。

I'm going to add another element。 Then I'm going to say size after adding。

So we expect the size to be4， because initial size was 3。

 and then we're going to look at the new capacity。So it's very likely that the initial capacity of this array will be  three。

The new capacity of this。Aray inside the vector is likely going to be larger than 3 and， in fact。

 larger than 4， because we really want to make sure we have enough room to add again。

So I'm going to expect the。Capacity after adding to be about double the original capacity。

 and we'll explore why that is in a future of video。 So we expect that to grow from 3 to about 6。

 and we'll see what happens in just a moment。 And then we can do the exact same thing we did before and see what is the memory address of cubes 0 and what is the memory address of cubes at 2。

2 and 0。😊。

![](img/39289b2d96f969fa99a8c7d03707f100_19.png)

And we can find out what the memory separation is or the offset between those two things。

 Since we know every cube is 8 by long， we expect the separation to be 16。

 if they really are stored sequentially in memory。And then finally。

 we can actually search through the array to find out where an cube is at。

 So if we want to find cube 400， we can go ahead and go through the array using a for loop to say。

 hey， I want to find where my cube is at a particular index。 So we're looking for cubea 400。

 and we're searching for cubea 400 by going through the array 1 element at a time。😊。

Let's run this program and see all of this work together。 Go into the example for directory。

Running make。And then， running dot slash main。We see the initial capacity of our cubeert that had three elements is 3。

We then add an element， and the size after adding is 4。And as we predicted。

 the capacity after adding is going to be larger than the size。

 So it about it exactly doubled the capacity of the array。

We find the memory separation between index 2 and index 0，2 cubes wide is 16 B。 So indeed。

 the cubes are being stored sequentially in memory。And finally， we found the target at 2。

 So it showed that we can successfully use a for loop to find a particular index inside of an array。

So at this point， you understand the basics of arrays。

 We are going to go contrast this against another form of storage called a linked list or linked memory。

 And then explore why we might use one or the other。 I'll see you then。



![](img/39289b2d96f969fa99a8c7d03707f100_21.png)

![](img/39289b2d96f969fa99a8c7d03707f100_22.png)