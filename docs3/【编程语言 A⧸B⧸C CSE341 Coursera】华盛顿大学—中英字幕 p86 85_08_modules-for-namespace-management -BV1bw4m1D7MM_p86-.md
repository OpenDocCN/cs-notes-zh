# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p86 85_08_modules-for-namespace-management -BV1bw4m1D7MM_p86-

In this segment， we'll start our study of Ml's module system。 This is a pretty big topic。

 It'll go on for several segments， even though we're just going to scratch the surface and get the basic ideas of what we can do with the module system。

 So the motivation here is that so far all of our programs have just been one top level sequence of bindings。

 we might have help our functions or local bindings inside of functions。

 but we've just had that one sequence。 and this is really not a good organization for larger programs you might write and M realizes this and like many programming languages。

 it has more support for organizing larger programs。

 So the main thing we'll focus on are M's structures。

 a structure defines a module where you can have a bunch of bindings that are separate from other modules and their bindings。

 So in this segment will just go over the syntax and discuss the basics and then we'll move on from there。

The main construct we'll have in this segment is the structure binding。

 so you say structure the name of your module， it's conventional to start with a capital letter。

 but it doesn't really matter， equalsstruct， then any bindings you want， any kind of bindings。

 data types， exceptions， variables， functions， and then end。And then inside a module。

 that sequence of bindings is just like we've been seeing at top level。 You evaluate each in order。

 Later ones can use earlier ones。 And then after you've defined the module outside the module。

 you can use those bindings， but you can't use them directly syntactically。

 if there's a binding in there called binding name。 you write module dot binding name。

This is probably not surprising to us because we've already been using some of the modules in the standard library。

 And that's why when we used a function like string dot2 upper。

 it was the two upper function defined in the string module。

 So what we're learning here is how to define our own modules。

 So I have an example here that I already have written out。

 This is a structure that I've highlighted right here。 It's just a silly example。

 I've called it my mathlib。 And in it。

![](img/d4ab63c078f0ca9221aeed4ae606fcb0_1.png)

I've got three bindings， a little factorial function， a variable that's initialized to half of pi。

 noticeice I'm using the math library here， which is already defined pi and then a little function that doubles its argument and now that's the end of my module here and then outside the module I'm continuing my program and I can use bindings in the module so I could say v pi equals my mathlib do half pi plus my mathlib do half pi and v 28 equals mathlib do doubler of 14。

 so we can evaluate this program just like any other program。

 we can say namespace management do sml and if we do that we'll see that the repel is telling us that there is indeed a structure my mathlib that has in it a fact binding a half pi binding and a doubler binding then at top level we had pi which turns out to be 3。

14159 and 28 which has value 28 I just want to emphasize。Here what is in our environment。

 We have things like mathlib dot fact。 That's a function from in to in。

 We do not have in our top level environment fact。 that's simply not bound。

 nor do we have a variable。 My mathlib。 These structure names are not variables。

 They're different thing in M。 We have these modules， but we have to use the bindings in them。

 We can't use the whole binding at once。 Like you see here。 There is no such thing。 my mathlib。

 That's just part of the module system， which is a little bit different from the rest of the language。

Okay， and of course we can， you know， let's say my math lib。Ma my math Lib dot half pie plus  one。

 And that will work just fine except that I have to say 1。0。 and then it will work just fine， okay。



![](img/d4ab63c078f0ca9221aeed4ae606fcb0_3.png)

So。What we have done so far is what I'll call namespace management。By using modules。

 we can keep the names for different binding separate。

 and this makes it much easier when you have a large number of functions and variables in your program。

 you can even have a whole hierarchy Ml supports defining modules inside of other modules and this is great so that a list library could have a map function and a tree library could have a map function and they don't have to worry about calling them list map and treem。

 each one can have a map in its module Now this is very important for larger programs。

 but it's just not very interesting。 this segment is only a few minutes long and it's kind of all that I have to say about it。

 Yes， you should use namespaces and we're glad that languages have them so to finish up this segment。

 just one optional feature because people always ask about it。

 Sometimes people want to know is there a way to say I want to be able to use everything in a module without having to type out the module name and you can it's with this open feature that is supported in MLl。

 you can put this inside a modules you can。In the Reple。

 I'm not a huge fan of it because it tends to take all those wellname things that were nicely in a namespace and then open the whole module。

 which often has more than just what you want。 But nonetheless。

 let me show how it works and how it's really not very necessary。 For example。

 if I thought I was going to call half pi a lot。 I could just say Val HP equals my mathlib dot half pi。



![](img/d4ab63c078f0ca9221aeed4ae606fcb0_5.png)

And this works totally fine， and now I can say half pipe at HP plus 1。0， and it works fine。Now。

 if you really did want everything in a module， then you could say open my math lib。

And now I have a top level bindings for fact half pi and doubleubr and fact is now in my environment。

 I think this is really useful in the repple when you're testing out a module， but other than that。

 I don't find it particularly useful especially if you were thinking。

 oh I really want to use fact a lot and you forgot that the module also had a binding doubleubr。

 you're actually when you say open going to shadow any doubleubr that might already be in your environment。

Nonetheless， if you want to use open， you can it's NM。

 it's in there for a reason people find it convenient。

 I consider it an optional topic and that's our introduction to module systems and using them for namespace management。



![](img/d4ab63c078f0ca9221aeed4ae606fcb0_7.png)