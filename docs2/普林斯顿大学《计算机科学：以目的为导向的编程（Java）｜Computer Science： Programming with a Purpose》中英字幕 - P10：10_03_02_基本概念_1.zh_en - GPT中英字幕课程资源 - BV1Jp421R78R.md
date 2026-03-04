# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P10：10_03_02_基本概念_1.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/7fbb47527a841d438bac565a390df416_0.png)

Today， we're going to talk about a Java language construct that's going to help us write programs that process large amounts of data。

 and it's very easy to use。 It's called the array。So we'll begin with some basic concepts about what arrays are。

Now this is adding to our basic building blocks for programming。

 we're up through conditional and loops and our next construct that we're going to talk about today is arrays and what that does is give us the ability to store and process huge amounts of data we're going to see lots of applications throughout this course。

 and fortunate this is a very natural and easy construct to use。It's our first data structure。

 what's a data structure， it's an arrangement of data that helps us efficiently process it in a program。

An array is defined to be an index sequence of values of the same type and we'll take a look at what each of those ideas mean。

 so here's an example of an array it's 52 playing cards in a deck that's the example that we're going to work with for a lot of this lecture so some cards in the first position and other cards in the second position the AO Hars in the third position and so forth given an index then we can immediately get to the card that's in that position in the deck。

But there's many other ideas where you might use an array。

 so you might have a lot of students in an online class and again you can get to each one quickly through an index。

 or we're going to look at digital images， there might be a billion pixels in a digital image and we want to be able to quickly get to each one of them。

Or biologists studying DNA， there might be nucleotides in a DNA strand and many。

 many other examples showing that you've got data elements of the same type and you have a huge amount of them and you need to structure them so that you can process them efficiently。

So our main purpose of the array is to facilitate the storage and the manipulation of this kind of data。

So what does it mean about processing many values of the same type。

 so here's an example that we could write after the first lecture without using arrays at all。

 in this case maybe we have 10 items of data and we just name them a0 through a9 if we want to refer to the fifth one we could say a4 equals 3。

0 or the  ninth1 a8 equals 8。0 and so forth and even use them in experiment in arithmetic expressions。

NowBut after a while， you can see that it would be very tedious and error prone to have code of this sort。

A much simpler way to do it is using an array， this is equivalent code using an array instead of declaring all those things of the same type separately。

 we just declare in one statement that we're going to make an array and we'll talk exactly about how those first two statements work in just a second。

And then if we want to refer to the fifth one， we just put that index inside square brackets or the eighth one。

 whichever one we want， and we can use those that array name followed by an index in square brackets。

 just the same way we use any other variable of that type since they're all of the same type。

 the Java compiler can keep track of them and check the type and that's convenient enough with 1 values。

 but what this does immediately is it scales， say to a million values。We have a huge amount of data。

 it would be indeed tedious to give them each one of them a different name with an array we have this shorthand where we just use the brackets to refer to individual pieces of the data。

 it scales to handle huge amounts of data。So what's an array look like in the memory of your computer well。

 since an array is sequence of values of the same type。

 it makes sense to take advantage of the fact that the computer's memory is also an index sequence of locations and we might as well we'll talk about this in a lot more detail later on。

 but it's easy to think of the memory of the computer as just a long sequence of locations and we're going to store the array contiguously in the memory。

Since every type value for primitive types like double and in for now。

 it's going to occupy a fixed number of locations， however， depending on the type of the data。

 if we store the array values in contiguous locations。

 that gives us what we need in order to be able to do efficient processing。

The critical idea is while we start indces at  zero。

 and that's just a convention that makes the computation a little bit easier。

 But the real critical concept is if we have I， then we can quickly access the value of A of I。

 We just have to know how big the thing is multiply by I added to the memory address of the beginning and then we're there。

Now for simplicity in this lecture， we're going to write the array name with an arrow pointing to where it begins。

 so thinking of the array name as a memory address of the first location， actually in Java。

 it's just a tiny bit more complicated and we'll get to that at some point later in the class。Now。

 one way to immediately， one really critical concept that derives from this。

 if you're using a name to refer to the array， if you make an assignment B equals a。

 you're making them point or refer to the same array。 And we'll look at that in more detail later on。

 But it's important to point that out right at the outset。

So you might think that it would copy the array the way that we do with values of variables of a primitive type。

 but it doesn't。Okay， so let's look at Java has some built in language support for arrays。

 they're so useful there's some aspects of the Java language that are built in to directly support arrays。

So declare an array， we have to declare a variable， we have to declare its type。

 in this case we have to declare that it's an array and then we have to declare the type of all the values。

 so double says it's an array of double values in the brackets say it's an array。

Now how do we create an array for variables of primitive types。

 we don't actually have to create anything， but for an array we have to tell the system that it's time to find the memory for that array so what we do is use the keyword new and that keyword new says create us a new array。

 double is again the type and then inside the brackets is the length of the array。

So this variable A has been declared to be an array of doubles。

 and then this statement here creates an array of a different length and then assigns that to A。

Refer to an array entry by index， we already went through that。

 you just use the array name and then in brackets， and then you can put anything that evaluates to an in。

Refer to the length of the array， you just say a dot length and in lots of programs that we write we want to be able to refer directly to the length of the array Now the most complicated thing is getting started and so we'll look carefully at each of the ways that you might want to initialize an array。

One of the important features of Java to remember is that it'll default initialize array elements to zero for numeric types like double or in or short or long。

 so if you say a equals new double 1000， you get a brand new array that are all doubles and all initialized to 0。

0， so you don't have to write code like with a four loop assigning each array value， the value 0。0。

In many languages， you need to write code like that。And in fact。

 most of the time we declare create initialize in just one statement just to make the code more compact。

 so this one， just like we do with variables， this one says double brackets A says a is an array of doubles and then the right hand side says create a new one of size 00 and initialize them all to 0。

0。Now it's important to remember， this is a compact statement。

 but it takes time proportional to the length of the array because job has to go through and initialize everything to zero。

So in certain points will have to be cognizant of that fact。

 you can write a small amount of code that might take a long time because Java has to go through and initialize everything to zero。

So that's the language support， and that's really all the code that you need to know in order to be able to write interesting and effective code that uses arrays。

Oh， one other thing initialized to literal values， you can write that x as an array of doubles。

 and then you can put a bunch of values inside curly braces and it'll create an array of exactly that length and initialize the array with those values。

 and that's useful for arrays that aren't long or large to get to get started。Okay。

 so that's the language support that we need。 Now， let's talk about this idea of copying an array。

Now if we have an array that's got some values in it。

 and maybe we need a copy of that arrays because we're going to perform some operation on it。

 but we still are going to need the original values later on。

What you need to do is create a new array。So in this case we create a new array B。

 we declare that it's going to be an array of doubles and then on the left hand side and the equal side we create a new one。

 how big should be the array B B， it should be the length of A。

 so we put a dot length inside the brackets， create a new array of doubles of a dot length doubles。

So， and it'll get initialized to 0。0。 I didn't write those in because we're going to overwrite them immediately。

 So what we're going to do is for i from 0 to 8 at length。

 we're just going to say B of I equals a of I。So we just assign the first one that's be of zero。

 be of1， and so forth。We go through and explicitly copy every value from A into B。

 And then once we've done that， we have a new array。And again， if you write the code B equals a。

 it doesn't do that。 It just makes B and A refer to the same array。

 You can write B equals new double a dot length， and it'll do that。 But then if you say B equals a。

 it just resets B to be the same as A and forgets about that new array that it created。

That's copying an array。 So here's some typical examples of programming with arrays。 Actually。

 we've already used one and that is accessing the command line arguments。

 there's a system array called AGs that contains the command line arguments that you type and we've been accessing those just by putting the first one zero inside brackets and so forth。

 So we use that in our gambler ruin simulation last time。Now， for all of this code。

 just to keep it brief， we're going to assume that the variable n got sent to A at length and B at length。

So here's copying an array， that's the code that I just gave with that caveat。

Here's an array a code that creates an array with n random values。

We create a new array A of doubles and of size n， and then for eigs0 to n。

 we just fill it with mat that random， a different double for each array entry。

Pnting the array entries is one per line， that's something that we do inside a for loop。

 so we're very often with a for loop running through an index I and then using that index I to access the I element of the array。

We're going to look at more complicated code later on。

 this is just to get used to the idea of using arrays。

 This code here computes the average of array values， so initialize sum at zero。

 go through the array adding in each array element and then declare a double variable average and that's sum divided by n。

And this is similarly finding the maximum， initialize a variable max at a of0。

 and then for the rest of them， if you find a bigger one then the current maximum then reset max。

 So these are typical examples of simple computations that you might want to perform with arrays just to get you used to the idea of writing this sort of code。

So here's a quick pop quiz， study this code and try to figure out what it's going to print。

We make a new array， A， B， and then we go through and B of i equals I and print out the two things。

And this is， again just a quick test about copying， I hate to overemphasize。

 but everybody gets burned on this after you say B equals A B and A are referring to the same array。

 so no matter what you do to A， you're going to do the same thing to that array to B。

 because it's the same array and so that when you print it out you're going to get the same thing。

They point to the same array。 Okay， so typical bugs when we program with a。

 So one is array index out of bound。 So when you define an array of say， size 10。

It's only creating 10 elements starting at  zero so the index must be between 0 and 9。

 if the index not between 0 and 9， then you're going to get an array index out of bounds here in this case I goes to 10 and there's no 10 in this particular code should go from zero less than 10 and then it would get the 10 elements with the right indices So array index out of bounds。

 if it's negative if it's bigger the length are bigger then that's going to be out of bounds。

Here's another error that we all get， we say in the first line that a is a variable declared to be an array type of doubles。

 but that's all we do， we never actually create the array so in this code will is buggy because the reference A of I the array never got created。

 so get an error message on that。Or the other extreme is forgetting to declare the array and just say。

 well a equals new double10， it should know that what a is but in Java everything itss type every variabless type has to be declared before it's used so a compiler doesn't know what type of data a refers to in order to check that you're doing what you want to do so that's typical bugs that we have to get through and you're encouraged to type these in and take a look at the error messages that you get when you try to compile this code it's always a good idea to look for error messages under controlled conditions rather than trying to figure out what they are when they happen to you unexpectedly。



![](img/7fbb47527a841d438bac565a390df416_2.png)

So that's the basics on programming with a race。

![](img/7fbb47527a841d438bac565a390df416_4.png)