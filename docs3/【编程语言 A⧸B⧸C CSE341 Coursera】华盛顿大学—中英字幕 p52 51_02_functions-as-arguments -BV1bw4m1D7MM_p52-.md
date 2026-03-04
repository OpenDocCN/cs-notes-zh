# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p52 51_02_functions-as-arguments -BV1bw4m1D7MM_p52-

In this segment， let's get right to studying probably the most common use of first class functions。

 which is passing one function as an argument to another function。

So I want to emphasize that there's nothing really new here in terms of language features。

 We just never thought to do this before。 So we could define a function binding in MLl。

 say F that took as one of its arguments， another function G and then inside the body of F G would be a variable that when we look it up。

 we get a function and so we could call that function with some arguments。

 And so we could use F in one place calling it with H1。 and in another place calling it with H2。

 So that makes F more useful， more parameterizable because different colorss of F can pass in different functions。

 This is going to be a very elegant strategy for us。

 we're going to be able to take common pieces of code and abstract them out。

 which is one of the best things to do when you're designing software。

 And the way we can abstract them out is instead of having n very similar function。

 we could have one function that has all the common parts。 and then。

Pass in N different shorter functions that just describe in their bodies and their computations the parts that are different。

 So really， the rest of this segment is going to be over in Emax， showing you a good example of this。

 a simple example of this to give you a sense of how this might work。



![](img/859f02438a2d8b62b09e5e77a73e009f_1.png)

So to start with， I already have written here three ordinary non higher order functions。

 plain old first order functions we call them， but they all have quite a bit of similarity。

 which we'll see So they're a little silly， but bear with me this first one just takes two arguments。

 n and X and increments X n times。 So if n is0， it just returns x otherwise it turns returns one plus the result of incrementing x n minus1 times。

 Now this really is quite silly。 This is an addition function。 It's just taking x and adding n to it。

 but but that's okay。 This second example is a bit less silly。

 There's no built-in operator for an Ml。 It takes a number n and another number x and it doubles x n times put another way。

 if you're a little more familiar with their math， it's two to the n times X right the way it does it is it says if n is0 return X otherwise multiply by two。

 the result of doubling。XN -1 times。The last example doesn't necessarily work with numbers at all。

 it works with lists， takes a number n， and a list x's， and it takes the n tail， so for example。

 if you pass it3 and the list 4， comma 8， comma 12， comma 16，Then you would get back the list 16。

 because if you take tail of tail of tail of that input list。

 you end up with the list holding just 16。 Okay， How does it do it， if n is 0。

 then just return the entire list， Otherwise take tail of the n tail of n -1 and x's。 All right。

 So three simple functions， we could have already written ourselves。

 but hopefully it pains you to see so much similarity between these functions。

 All of them take two arguments， if the first argument is 0， return the second one。

 otherwise do something to the recursive call with x or xs and n-1。

 So somehow we'd like to separate all this out， So we don't have to write all that stuff three times And in general。

 these might be bigger and more complicated。 And the only way we can do this without first class functions。

 which would be some uglycc where we had some flag， do I want to be increment or double or n tail。

 and that's not extensible。 What if there's a fourth function that comes along that is like this。

 But first class。Functions do this very， very well。

 So what I'm going to do is write a function n times that。

 in addition to taking N and X takes another argument。

And that F is going to capture the differences between the three functions above。 So in every case。

 I want to say if n equals0， then just return that second argument。Otherwise。

 I definitely want to call n times with the same function n minus-1 and x。

 and then what I want to do to that recursive result， well that depends。

 and it depends on whether I want to do doubling or incrementing or tailing， but in all cases。

 we'll just have the collar pass in an F that does what we want。😡。

So that is our useful higher order function， and now let's see how we can use that to do incrementing and doubling and tailing。

 so let me first just define a couple very simple and very short helper functions。Like this。

 there are various ways you can double。 There's one。

 And now what I can do is use n times in various ways。 So if I wanted to double 7， four times。

 then I would just do that。And if I oh， sorry， x1 equals， there we go， and if I wanted to increment7。

 four times。Then how about I make the exact same call， but I pass in increment instead。And similarly。

 if I wanted to take the tail， say maybe two tails of a list like 48， 12，16。

It'll work just like that and sure enough， if I come over here and run it。

Functions as arguments do Sml。You'll see that x1 is 112， x2 is 11， and x3 is 12 comma 16。

 so we saved a lot of code reuse here。 We got a lot more code reuse。 All we did here was use n times。

Increment double， which are very short and then use it in different ways。 Now， you might be thinking。

 well， that's great。 But， you know， callers， you know。

 users of my code shouldn't have to go to this extra work。 But， of course， they they don't have to。

 right， If I want to write my own increment function that takes n and X。

 And how about I change its name since we know this is really just addition as long as n is greater than or equal to 0。

 None of these functions work for negative N， I can just define this like this。 right。

 The function that takes n and X and increments X n times can be implemented by calling n times with increment N and X。

 And similarly， double n times could be better written as。😊，This body。And finally。

 en tail and comma X can be written as this。 and as always。

 callers of these functions don't need to know and don't need to care that we've implemented them using the same common code n times under the hood。

And then finally， suppose we did this， we were very happy with ourselves。

 we can now go up and really get rid of， or for the sake of simplicity here。

 I'll just comment out all this repetitive code， so all we have now。😊。

Is n times and these three helper functions。 And then maybe sometime later。

 you realize that that pattern， that reusable code。

 that higher or function n times is even more useful。 Maybe you come along。 And you realize that， oh。

 you need to triple some number n times N comma X。 And you're like， oh， well。

 I'll just call n times with a little helper function triple that I'll write an n comma X。

 And of course， I need to define triple here and'll be three times x。All right。

 and this is all wonderful and let's go back and make sure we got that all right。And sure enough。

 what we now have are functions additional addition and double n times。

 both of type instar int arrow int。 We have n tail of type instar alpha list。

 arrow alpha list and triple n times of instar int arrow int。

 So n times which fundamentally just takes function and an n and an x and ends up returning F of F of F of F n times of those applied to x is a generally reusable。

 beautiful high order function that we can reuse by passing in different functions in that position for F。

 So that seems like a great example， the only thing that might be a little confusing to you is this type of n times。

 which looks a little complicated in polymorphic。 And so let's talk about that a little bit more in the next segment。

😊。

![](img/859f02438a2d8b62b09e5e77a73e009f_3.png)