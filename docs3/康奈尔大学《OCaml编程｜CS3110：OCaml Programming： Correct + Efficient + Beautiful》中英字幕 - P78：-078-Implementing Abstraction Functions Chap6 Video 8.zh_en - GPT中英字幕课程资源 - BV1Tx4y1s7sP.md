# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P78：-078-Implementing Abstraction Functions Chap6 Video 8.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Do you ever implement the abstraction function？The answer is mostly no。

 it is just a mathematical function that's in our heads rather than a programming function。

But there's something that comes really close to it。

 which is to string in Java or any kind of function that produces a string representation out of a data structure。

That's because when we produce a string representation。

 we're trying to convey the same idea as that abstraction function usually。

 we're trying to say here abstractly， mathematically is how you should think about the concrete value of this data structure。

 let's practice that idea by implementing some string functions for our set data abstraction。



![](img/0479bdc4f84123f645985f54f0abacd5_1.png)

We'll pause here。I'm not committing to much in the specification for this string function。

 I'm not saying exactly how I will represent the set as a string。 If my user cared。

 then I might need to go ahead and specify that For now。

 let's just say it's good enough that it is some kind of string representation。

I've made my code compile。Always be compiling now I'll go back and improve the code to provide some better functions to implement string。

The first thing I've done is to factor out a function to represent a list as a string。

 because I know I'm going to need that same function in both of my implementations。Of course。

 there's a difference between those two implementations about duplicates。

 I might as well go ahead right now and take care of that。

I'm starting to be unhappy now because I've got duplicated code There's a notion of deduplicating all of the elements in a list before using one of these set operations on it。

 I might as well make that a function in and of its own right。😡。



![](img/0479bdc4f84123f645985f54f0abacd5_3.png)

![](img/0479bdc4f84123f645985f54f0abacd5_4.png)

There， I have improved my implementation of both those functions by using my Ddoop helper function that I factored out。

The DDop helper function is documented here for the implementers or maintainers of this codeb。

I put Dduop here outside of list set dupes just to demonstrate that I could have a helper function outside the body of that module。

 If I wanted to hide the helper function， all I would need to do is turn this into a compilation unit by providing a sets dot MI file。

 Now， it's time to finally implement this function to convert a list into a string。

Let's start by putting curly braces around whatever elements are in it and writing a function to convert all those elements to strings themselves。

So I'm a little stuck here， what I'd like to do is use map to convert each of the elements of the list to a string。

But I need to pass map a function that knows how to convert elements of type alpha to strings。

I don't have such a function because I don't know what alpha is。

I'd better make that a parameter to these functions。Okay。

 so I've added in a function to the string specification here。

String now needs to take in that function that says how to represent elements as strings。

 so the function has type alphapha arrow string。And we'll use that in this function that converts the interior elements of the list to a string。



![](img/0479bdc4f84123f645985f54f0abacd5_6.png)

Now I do have a type checking error here， and the problem is that I haven't yet finished my interior function yet。

 it's producing a list of strings now rather than just a single string。

So let's use fold to collapse that list of strings down into a single string。Did I get it right？

One way to tell， let's load the code into Utah and see what happens。



![](img/0479bdc4f84123f645985f54f0abacd5_8.png)

So my first attempt failed here。 but that's because I failed to pass in the function that string now needs。

 It needs to be told how to convert elements to strings。 Of course， I can do that with string of。

And now we get a string representation back， it does have 43 and 42 in it。

It's got this a little annoying thing here that there's an extra comma at the beginning。

 I should probably go back and take care of that by making a special case for the first element of the list。

So in the case that the list is empty， I can return a string representing the ID set。

 but in the case there's at least one element， then I can treat that first element specially by not putting a comma in front of。

Now I get a nice representation and my duplicate。List representation。Also works quite nicely。

 The one difference is that because I use Dduop， I'm sorting the elements of that set。Oh well。

 order of elements in a set is irrelevant anyway， and my specification made no promises about the order in which they would be produced in the string representation。

 sometimes there are other ways in which we implement the abstraction function， for example。

 if we're implementing a map abstraction， maybe we could write a kind of abstraction function that converts that map into an association list。

 which is another representation of the same underlying idea。

Or maybe we even drop pictures one time I wrote some code that in order to represent a tree abstractly actually produced output that was graphical depictions of the tree based on the underlying data structure used to represent。



![](img/0479bdc4f84123f645985f54f0abacd5_10.png)