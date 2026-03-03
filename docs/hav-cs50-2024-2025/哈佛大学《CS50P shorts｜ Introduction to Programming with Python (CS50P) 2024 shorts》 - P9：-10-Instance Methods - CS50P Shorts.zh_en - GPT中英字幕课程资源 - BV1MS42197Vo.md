# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P9：-10-Instance Methods - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

![](img/2749873fe240ad6c6aff3cb9929078a9_0.png)

Well hello one and all and welcome to our short on instances Me now we've seen in prior shorts on defining classes and instance variables。

 ways to define some template for some object and ways to instantiate individual instances of those templates to refer to encode code and access their various instance variables or a traits of each of those individual in this case packages so we have here again a class called package that encapsulate some information about packages in general we say that every package will create will have a number like an ID。

 a sender， a recipient and a weight to it， and we then define here the various instance variables whenever we create a new instance of this class。



![](img/2749873fe240ad6c6aff3cb9929078a9_2.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_3.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_4.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_5.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_6.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_7.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_8.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_9.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_10.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_11.png)

downown below On 11 and 12 we actually create these instances we have here On 11 a package whose number is one。

 whose sender is Alice， whose recipient is Bob and whose weight is 10 and then finally down below on line 14 we have some code here that actually accesses the instance variables to print out in a more pretty format the package information itself so let's try running this and see the output down below once more I'll run Python of packages。

 pi and we'll see thanks to the code that we all have here we're able to print information on these packages while to encapsulate and combine the information in a more organized way。



![](img/2749873fe240ad6c6aff3cb9929078a9_13.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_14.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_15.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_16.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_17.png)

Now it turns out that I can use classes to not just encapsulate or combine pieces of information。

 but to also encapsulate functionality that want to be common across all individual packages。

 and I can do so by defining in this case what I might call an instance method。

 a method that can be run on any instance of this particular class。



![](img/2749873fe240ad6c6aff3cb9929078a9_19.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_20.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_21.png)

Now when I say method here， I'm really referring to a particular kind of function that is part of a class。

 and I want to show you one that you might find handy， one called Dunder STR， D St。

 so similar to Dunder in it， Dunder Sts， a special instance method that can be called when if I were to print some package。



![](img/2749873fe240ad6c6aff3cb9929078a9_23.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_24.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_25.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_26.png)

Now down below here， on line 15， this is a long line of code， but wouldn't it be nice。

 let's say if I could simply print a package like this print package and get let's say the same format I have down below right now this will not be the case if I run Python of package。

 pi I'll see this just not very pretty at all， but I could add an instance method called Dunder STR to actually improve the output of in this case what I see when I call print on any given instance of my package class。



![](img/2749873fe240ad6c6aff3cb9929078a9_28.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_29.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_30.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_31.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_32.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_33.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_34.png)

So let's go back up here and to define some new instance method。

 well I can simply drop down a line and define some new function that's part of my class and because this one is a special method defined as some special functionality by Python itself。

 I'll use these double underscores and then STR， in fact the double underscore which as Dunder。

 they tend to refer to these special method that Python attaches some special meaning to in this case。

 Dunder stir is actually called every time I call print on an instance of my individual package。



![](img/2749873fe240ad6c6aff3cb9929078a9_36.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_37.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_38.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_39.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_40.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_41.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_42.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_43.png)

So by convention， D St takes as input in this case。

 the instance of the class itself that we refer to as self。



![](img/2749873fe240ad6c6aff3cb9929078a9_45.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_46.png)

And within Dunder St， I can return some string that will be printed every time I call print on an instance of the package。



![](img/2749873fe240ad6c6aff3cb9929078a9_48.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_49.png)

So just as a test here， why don't I say？

![](img/2749873fe240ad6c6aff3cb9929078a9_51.png)

Why don't I say this is a package， this is a package， so every time I call print on a package。



![](img/2749873fe240ad6c6aff3cb9929078a9_53.png)

Hopefully y'all see this is a package， I'll go ahead and run。



![](img/2749873fe240ad6c6aff3cb9929078a9_55.png)

We ahead and run Python of packages。 pi。

![](img/2749873fe240ad6c6aff3cb9929078a9_57.png)

And for both of those within my list here， this package and this package。

 we'll see this is a package which is helpful but only a little bit like ideally I'd show some information on the actual instance of the package I'm talking about so to do so I can again access these instance variables and return let's say something like an F strings it's in the same format we had down below。

 I could say package again and then self dot number colon。

 maybe self dot sender to self dot recipient and then comma self dot weight KG just like this。



![](img/2749873fe240ad6c6aff3cb9929078a9_59.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_60.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_61.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_62.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_63.png)

So this is the same F string we had in that for loop。

 but now I've encapsulated that same F string inside of my package class within this instance method called Dunder stir Now ideally when I run Python of packages。

 pi we'll see some more information on this package。

 but much more simply now we can simply call print package I'll run this。



![](img/2749873fe240ad6c6aff3cb9929078a9_65.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_66.png)

And we'll see that same information now part of some instances method called Dunder St。

 so pretty handy here。Now what else could we actually use instance methods for we want to maybe attach functionality that seems pretty core to the idea of being a package。

 maybe one thing we want package to be able to do is calculate the cost of shipping them so I can imagine here defining another instance method。

 maybe one called calculate cost that allows a package to figure out how much it costs itself to ship so I could here define here maybe a new method called calculate cost and these instance methods by default again。

 take as input as the first argument， the instance itself that we refer to as this variable this argument called self。



![](img/2749873fe240ad6c6aff3cb9929078a9_68.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_69.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_70.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_71.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_72.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_73.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_74.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_75.png)

Now， as another input to calculate cost， maybe the cost changes and maybe a cost per kilogram。

 but I could specify as input to this particular method here。



![](img/2749873fe240ad6c6aff3cb9929078a9_77.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_78.png)

I'll type a colon， and within this particular function body。

 I can then define this instance method called calculate cost。



![](img/2749873fe240ad6c6aff3cb9929078a9_80.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_81.png)

Let's first see how to use this instance method， though。

 maybe instead of going down here and just printing the package。

 I could do something little more fancy， I could say。

 why don't we print the package itself as part of this F string。

 but then also say that it costs it costs some amount。



![](img/2749873fe240ad6c6aff3cb9929078a9_83.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_84.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_85.png)

Now that I have this function called calculateulate cost， it is yet unimplemented。

 I could use it as follows for each instance in this case we're calling package in this4 loop。

 I could call calculate cost by typing a dot and that function the actual method name so calculate cost and now as input to calculate cost could I actually type in the input I'm expecting cost per KG so I'll say cost per KG and why don't we say it's about a  two US dollars per kilogram to ship some given package。



![](img/2749873fe240ad6c6aff3cb9929078a9_87.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_88.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_89.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_90.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_91.png)

This this is how we want to use calculate cost， but now let's implement it up on line 11。



![](img/2749873fe240ad6c6aff3cb9929078a9_93.png)

Well I want to make sure to return here the total cost of the package I actually know the cost per kilogram so to do that I think I need to do some some multiplication I could maybe find the weight in kilograms and multiply it by the cost per kilogram so I could say maybe self self dot weight again accessing some instance variable and multiply that by the cost per kilogram and we'll make the assumption here the user knows that weight should be in kilograms so we'll go ahead and say this is calculate to cost it takes the weight in kilograms multiplies it by the cost per kilogram and that is the cost of shipping this particular package so let's try it down below why don't I go ahead and run python of packages pi and now we'll see package1 Alice to Bob 10 kg cost 20 and package2 cost10 probably improve this a little bit。



![](img/2749873fe240ad6c6aff3cb9929078a9_95.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_96.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_97.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_98.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_99.png)

And then you add a dollar sign here to say this is in US dollars， run packages do high again。

 and now we'll see some pretty good formatting here。



![](img/2749873fe240ad6c6aff3cb9929078a9_101.png)

So this was our brief foray into instance methods， there are some special ones like Dunder St。

 allowed to say how a instance should be printed as we saw down below。

 and we can also add some functionality， en capsulate functionality in this case。

 like one to calculate the cost of shipping some given package。

This then was our short on instance methods and we'll see you next time。

