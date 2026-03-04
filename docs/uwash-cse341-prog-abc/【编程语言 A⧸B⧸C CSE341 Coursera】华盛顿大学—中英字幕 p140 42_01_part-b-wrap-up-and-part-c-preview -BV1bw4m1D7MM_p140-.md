# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p140 42_01_part-b-wrap-up-and-part-c-preview -BV1bw4m1D7MM_p140-

Okay， in this last video for Part B， I want to congratulate you on g to this point and set the context of where we've been and where Part C will allow us to go。



![](img/83fc92ec5c1c38c3e0d8c99268a81e2b_1.png)

So here's kind of the overview of where we are after part A we had seen the basics of functional programming in a statically typed language including pattern matching and function closures and things that are a little more MLspec in terms of how it does modularity and type inference and then here in part B。

 you've seen the corresponding dynamically typed approach to several things we focused a lot on delayed evaluation and things like streams and then we learned how to write interpreters and even implement our own language with function closures and then we were able to discuss the difference between static and dynamic typing。



![](img/83fc92ec5c1c38c3e0d8c99268a81e2b_3.png)

So are we done Well， we're certainly done with Part B。

 but what I'd like to do is spend just a couple minutes explaining how part C really helps us finish the story。



![](img/83fc92ec5c1c38c3e0d8c99268a81e2b_5.png)

So Part C has two more modules section7 and 8， and what they do is focus still on dynamic typing like racket。

 but on issues related to object oriented programming and on comparing and contrasting that with functional programming。

So in section 7， we'll have to do a bunch of things to get started with Ruby。

 but in addition to just the objectoriented programming basics that that will involve。

 we'll do some other ruby specific things as well， including its approach to things that are very close to closures the way it treats arrays in a very flexible manner and a number of other things and then in section 8。

 I think a lot of things will really come together and we'll learn how in objectoriented style and a functional style in fact。

 are so opposite in the way they decompose large problems that they're really two elegant ways of looking at the same thing just from sort of something that where it's such an opposite perspective。

 it's more similar than different and then we'll be able to take on some more advanced objectoriented programming topics。

 things like mixins and double dispatch we'll learn what those are when we get there and then be able to compare fancy approach to more flexible type systems。

 kind of coming full circle and going back to the static typing。

With things like the difference between generics and subtyping。



![](img/83fc92ec5c1c38c3e0d8c99268a81e2b_7.png)

So let me sort of argue that I hope you continue to part C to sort of finish the story of what we're trying to do in this course。

 Now some of you and somewhat understandably may say， well。

 you know I already have a lot of experience in OOP and object oriented programming。

 I kind of came here for the functional parts I've learned a lot and I don't think I'm going to get as much out of part C。

 and I appreciate that perspective， but let me tell you how part C might not be quite what you expected it to be。

 First of all， as we approach objectoriented programming in some ways like you've never seen it before。

 we're going to do it in a way that's deeply analogous to the way we approach functional programming and the way I believe studying the material we have so far in a piece by piece fashion with crispP definitions of what each component means。

 I think similarly studying objectoriented programming in that way。

 will give you a better foundation for how to think about objects and。

Classes and methods and things you may have seen before In particular。

 we will build up to giving a precise definition of how you find what code to execute when calling a method on an object and see that it's actually a bit more complicated than the rules associated with function closures。

Now， I will say that as you get into the two modules in part C。

 a lot of people may find the second one more compelling and more interesting than the first one The first one needs to be self-contained even for people who haven't seen objects before and if you've already programmed in Ruby or a similar language a lot of it may seem old hat。

 I should also add that the homework for that section is a little bit different。

 What we basically do is make some small modifications to code that's already given to you。

 What I like to do with that is give you that experience which is a lot more like programming in industry aren open source projects is often like and again。

 there's kind of a bit of a divide there， people who have already done a lot of that find it a little less motivating but people that don't often find it really interesting their ability to go into a language that they may have never used before。

 and with a little bit of background， namely the material in the section of the course are able to go into a full program。

And change it in fundamental ways to make it more flexible and expressive。As a last thing。

 this course focuses a lot on functional programming and therefore it can kind of see anti objectject oriented programming that's largely not true in part C。

 I like to give OOP its do， but we do focus on some things where functional tends to work out a little better or following an object oriented perspective turns out to be a bit awkward and what that's really letting us do and what I'm hope you're excited to see is actually learn more about functional programming by being able to contrast it with object oriented programming so let me finish up with some of the things that we're going to see in part C that really are about functional programming。

😊。

![](img/83fc92ec5c1c38c3e0d8c99268a81e2b_9.png)

First， we'll see how you could implement object oriented programming on your own in racket。

 at least in a particular way。 It turns out rackcet has classes and objects and we could have just done part C in rackcet。

 but if you had nothing in racket other than what I've already shown you。

 it turns out there are some clever ways to implement object oriented programming on your own and seeing that can explain OOP in a pretty fascinating way。

 Second， we'll do， as I mentioned before， this way to think about how functional programming FP and object oriented programming OOP decomposed problems in exactly the opposite way and how that makes them more similar than different and then the last homework of the course。

 homework 7 in part C is again， a more challenging one。

 challenging like homework 5 is and what we're going to do is we're going to take some code in M we're going to go back and look at M and port that code to Ruby and as we do it。

 we're not just going to translate it over。In the same style。

 we're going to convert the style to be a fully OOP committed to objects。

 way of restructuring the program。😊，And the program we're going to port is another interpreter。

 so you get experience with interpreters again， except instead of focusing on closures。

 which we already did here in Home 5， we're going to do it for a little geometry language which will let you see how the idea of interpreters is useful for things other than conventional programming languages。

 it'll be about different geometry objects and intersecting them and things like that。😊。

And then lastly， we'll be able to look all the way back at ML's type variables。

 those quote A's that we saw in the types of functions like map and filter and compare that to how languages like Java and C sharpp do provide an analogous thing which is generics。

 but also a very different thing which is subtyping。

 so we'll get back to static type systems and see how they're related to both FP and OOP。

 So with all that congratulations on finishing part B of the course。

 you've done a tremendous amount of work， and I hope to see you at the beginning of part C very soon。

😊。

![](img/83fc92ec5c1c38c3e0d8c99268a81e2b_11.png)