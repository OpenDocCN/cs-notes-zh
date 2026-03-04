# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p150 9_07_class-definitions-are-dynamic -BV1bw4m1D7MM_p150-

In this segment， I want to show you how Ruby is a very dynamic language just about anything can change while the program is running。

 We've already seen that with instance variables that we can take any object and add any instance variable to it just by assigning to it in some method of the class。

 Now I want to show you that classes themselves can have their definitions change while the program is running。

So the idea is that any code running a new rubby program or anything you type at the Reple can add change。

 replace methods at any time during program execution。

 Now I don't particularly love this feature because it makes programs pretty much impossible to analyze it lets any code break any abstraction just by changing the definitions of methods but it does have some interesting even convenient uses。

 for example， if you really wish that some common class like string or array or number had some super useful helper function。

 you could just add it， and then it's like it was in that class definition all along。

 I'm not saying this is a great idea for large programs。

 but it's an interesting feature for scripting languages and it's certainly something that people enjoy using for art purposes here it really just helps me emphasize the idea of object oriented programming that every object has a class and a class determines its instances behavior and since classes themselves are just objects we can model。

ify those objects by adding or removing methods。

![](img/f35922c9770f8c39a2904b9753a03b38_1.png)

So let me show you the idea just over here in the Reple with some examples。

 I have all this in a file as well。 Everything would work in a file。

 I will post that file with the lecture materials， but suppose that I start by loading the larger example I had from a couple segments ago with my rational numbers so I can make myration for sort of non-coma 6 and that is the fraction3 slash2 the repple is calling the 2 S method for me that's why you see over two being printed by explicitly converted to a string you see it that way。

 but my purpose here is to emphasize that while I have an ad method you know I can say x plus x and get three boy that's super inconvenient。

 I really wish that instances of myration had to double method for doubling themselves and it's simply not defined if you go back and look at the code I wrote in that class it's not there。

Well， let's just change it。 The way you change a class definition in Ruby is you just make a class definition with the same name and you add more stuff to it。

 So here， class myrational。 Let's make a method double。

 What I could just do is take the object itself。 So this is going to be part of an instance of myrational。

 So self will be some fraction。 and call the plus method on it with itself again。Close the method。

 close the class。 And now if I made a my rational dot new， maybe three comma 4。That's fine。

 I could still convert it to a string。 I could still call plus with it。

 but I can also now say double。So three fourths double to three/ hves if I said y do double dot double。

I get three because self plus self ended up returning the object itself。

 That's how our addition worked and so on。 If I did it one more time， I think I would get 6。

 All right， now。Here' is the cool part。X， which I define way up here。😡。

Before class my rational even had this method can double itself too。

 And that's because every object has a class。 Once the class changes。

 objects of that class see the reflected changes。 That's an interesting semantics。

 It's fairly natural， and it lets you change the behavior of objects that even already exist。

 In fact， let me show you something else。 If we like this doubling so much。

 How about we add it to numbers， too。So， you know， things like three have class fixed numb。

 I have we'll just try that again。I think I forgot。Punctuation somewhere。There we go。

 that time it took， Remember，3 dot class is a fixed nu， So now3 knows how to double itself。In fact。

 so does 42。And so on。So people think that's neat。 I'm just using it to teach object oriented programming。

 Let me show you one other thing。 We know we can define methods at top level。

 So how about I just define a little method here that always returns 42。

So it turns out that this just added a method to the object class because that's where top level methods go。

 It turns out that here in the repel， I really am part of the object class。

 and so now all objects have this M method。 So if I say x do M， I get 42， if I say 56。 M， I get 42。

In fact， I really did just add it to the object class because if I say 56 dot methods。

 you will see in this list somewhere M， and if I said nil dot methods。

 you should also see in here somewhere M， I won't try to find it right now and in fact。😡。

If I did it the more explicit way and said 43 instead。Now。

 I've replaced the old M method from a minute ago with this new one。 and now I get 43。

 no matter how I call that method， even at top level。

 I get 43 because I just replaced a method that was already there。 Now。

 replacing methods to behave differently is obviously rather suspect。

 And what I thought I would do to finish up my IB。 I purposely save this to last for reasons you'll see in just a second。

 Suppose I took the builtin fixed numb class and to changed its addition operator。

 so that it still takes one argument， X。😊，But when you call it， it just returns 13。😡。

And what apparently just happened is I just crashed and you're seeing all sorts of weird stuff on my screen because when you change a definition like plus IRB。

 which is itself written in Ruby and calls all sorts of Ruby code。

 starts doing all sorts of strange things， so that's why I saved that to last。



![](img/f35922c9770f8c39a2904b9753a03b38_3.png)

Okay， so。The moral of the story here is when you have a very dynamic language。

 some interesting semantic questions came up。 One of the things I showed you here was what happens if you create an instance of some class。

 replace its method M and then call the method。Do you get the old method since the object was created before the class change or do you get the new method because you look up in the class as it's currently defined。

 It turns out in Ruby， you get the new method that's considered the more useful semantics。

 but my real point is in languages that are less dynamic that don't have this sort of ability to change classes at runtime。

 This question never comes up。So more dynamic languages tend to introduce more questions of semantics that a language definer。

 someone designing the language has the answer， because this is a semantic question that you have to answer in your language。

 but if your language doesn't have such a feature，Then it's an irrelevant question。

 and your language implementation might be easier or even faster higher performance because it doesn't have to deal with such situations。

 and that's an interesting thing in Ruby， dynamic class definitions that's unlike many of the object oriented programming languages you may have seen previously。



![](img/f35922c9770f8c39a2904b9753a03b38_5.png)