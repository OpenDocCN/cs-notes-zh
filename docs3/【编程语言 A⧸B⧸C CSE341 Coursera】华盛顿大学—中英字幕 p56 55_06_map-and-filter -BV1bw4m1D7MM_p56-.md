# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p56 55_06_map-and-filter -BV1bw4m1D7MM_p56-

In this segment we're going to write and use two more high order functions。

 which we will call map and filter and these examples are so famous。

 so important I like to joke that if there were a Hall of Fa for famous high order functions。

 these would be in it。 These are not functions I made up。 I didn't make up their name。

 In fact they're part of the common vocabulary that computer scientists and software developers use all the time。

 so it's important to understand when map and filter are the right thing to use。

 and it's great that in a language with high order functions。

 we can easily define them for ourselves over data structures like lists。😊。



![](img/cd48b843c2d0e738b86319fd2bd6b47a_1.png)

So let's just do that。 I've just got a blank file here and we'll do map first。

 So we're gonna do map over a list。 map takes a function and a list。

 And what it does is it computes a new list that is like the input list except F is applied to each element。

 So it's got the same shape and size。 the ifF element of the output is the if element of the input with F applied to it。

 And once you know how to write high order functions in a language like Ml。

 this is actually very easy let's just case on x's。 if we have the empty list。

 then the result of mapping F across all of those elements is simply the empty list。 Otherwise。

 we'll have a non-empty list and what we should do is create a list that's f applied X cons on to mapping。

F to x is prime。 That is the entire thing that for map。 And if it looks a little familiar。

 it might be because it's on the course logo， you've seen every time you've participated in this course。

 Allright， Let's see how to use map in a couple different ways。 One thing we could do。

 I'm just going define a couple variables here。 is we could map the increment function take x return x plus one across a list of integers。

 maybe 4，8，1216。😊，Or we could， let's say map the head function。

 notice I'm not unnecessarily wrapping it here across a list of lists。

 You're going to have to have a list of lists because we're going to apply head。

 which requires a list to every element of a list， so we do need a list of lists here。

 I'll make my list of lists list of list of integers， and there we are。Allright。

 and now let's save this and try this out， use mapand filter。sml， and sure enough。

 x1 is the list 591317， and x2 is the list 13，5， which is what you get if you take the head of these three lists here。

The type of map is quite interesting， and let's talk about that just a little bit more back here with the slide。

 so here you see the code we wrote for map。

![](img/cd48b843c2d0e738b86319fd2bd6b47a_3.png)

And the type that we saw from the Ritaval Pri loop is that map takes two arguments and returns something That's definitely true。

 The first argument can be a function from any type alpha to any type beta Aarrow， B。

 the two types don't even have to be the same。But there are some constraints。

 the second argument to map has to be a list of alphas。

 so whatever the element type is of the second argument has to be the argument type of that function F。

And what map returns is a beta list。 A list whose elements are。

 Whatever type this higher order function takes is its argument。

 So it's very elegant to understand map。 You need to understand its type。

 It's an alpha arrow beta star alpha list to beta list， Al and beta can be the same。

 in this first example， where we incremented every element of the list。

 We instantiated both alpha and beta with int。 But in this second example where we still have map of the same type。

 Alpha is int list。 Head takes an int list。 and beta is int。

 because that's what head returns when given an int list。 So that is map。😊。



![](img/cd48b843c2d0e738b86319fd2bd6b47a_5.png)

![](img/cd48b843c2d0e738b86319fd2bd6b47a_6.png)

Once you've learned it， once you've seen it， you end up using it all the time。

 it's very often good style to use map because it communicates to the reader of your code。

 What I'm doing here is a map operation。 I'm applying the same function to every element of some collection to produce a corresponding collection right In fact。

 it's so common it is predefined and standard ML standard library。

 although it has a slightly different style。 it doesn't have quite the type I've shown here because it uses this thing cur that we're going to get to in a few segments。

 but it's a very similar function that also performs mapping。😡，Allright， so that was map。

 I promised you two Hall of Fa high order function， so let's do the second one， this is filter。

 It also takes an f and a list of x's， but F works differently here here we expect F to return true or false and what we're going to compute is a list that's a subset of the elements and x's in the same order and what we're going to do is we're going to filter out any elements of x's for which F returns false。



![](img/cd48b843c2d0e738b86319fd2bd6b47a_8.png)

So once again， we need a case for the empty list and a case for the nonempty list。

 and if you don't start with any elements， no matter what there will be nothing to even potentially filter out。

 you'll just end up with no elements， whereas if you have a non-empty list。

 Well whether to include x in the output or not depends on what f of x returns。

 If F of x returns true， then we want x in our output and the rest of our output should be the result of filtering F with x is prime。

Otherwise， we just want to have F of x is prime。There are other ways we could have written this。

 for example， we could have written if if Fx then and tried to append the result。

 but this is probably the most elegant way and it says pretty directly what it is we're trying to do as before we can write a couple simpler examples of this instead of actually showing examples that process actual list how about we define some functions that use filter as a helper function so for my first example I'll write this out with a top levelvel function so it's a little easier for you to read if we wanted to take a list of integers and return only the even numbers out of that list。

 then I could write a function all even that just called filter with that is even function I just wrote and x's here's a more complicated example that's going to use a more sophisticated anonymous function just because I thought it would be fun。

 let's take a list of pairs where the second thing has to be an integer。

And return the elements where that second thing is an even integer。

 So I'm using a little pattern there in my anonymous function。 need to write the fun keyword here。

Okay， and X's。 And I have two few parentheses。 How about right there。 I think that's right。

 Let's go over and try this。And sure enough， all even is a nice filter function from int list to int list。

 let's try it out real quick， all even of three comma 4， comma 6， comma 0， comma 13。

And we get back the list4 comma 6 comma 0， I'll leave it to you to test out all even of the second things of pairs if you're interested in that one。



![](img/cd48b843c2d0e738b86319fd2bd6b47a_10.png)

So filter， which you see here on the slide is also one of these very famous functions。

 it's just part of the vocabulary of computer science。

 also in the standard library using that cur feature we'll get to。

 but let's finish up this segment by looking at the type of filter。

It does take a list of alphas and it returns a list of alphas， unlike map。

 we're not computing anything based in terms of the elements。

 What we're returning is a subset of the elements， keeping the same order。

 and so the alpha list for the argument can be the alpha list for the result。

 We could pass an in list， string lists， list of list events， whatever。

 but the output list will have the same type。And the argument for F that F argument has type alpha arrow bo。

 we definitely pass elements of the argument list to F。

 so it has to be the same type that F expects and that the elements of the list have and F needs to return a bo because we use it right here in the position between if and then and we know from very early in the course that for an if then else to type check the result of this expression after the if has the have typepo。

 so there you are probably two of the most famous functions in all of computer science map and filter。



![](img/cd48b843c2d0e738b86319fd2bd6b47a_12.png)